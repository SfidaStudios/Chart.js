# Chart.js

[![Build Status](https://travis-ci.org/nnnick/Chart.js.svg?branch=master)](https://travis-ci.org/nnnick/Chart.js) [![Code Climate](https://codeclimate.com/github/nnnick/Chart.js/badges/gpa.svg)](https://codeclimate.com/github/nnnick/Chart.js)


*Simple HTML5 Charts using the canvas element* [chartjs.org](http://www.chartjs.org)

## Documentation

You can find documentation at [chartjs.org/docs](http://www.chartjs.org/docs/). The markdown files that build the site are available under `/docs`. Please note - in some of the json examples of configuration you might notice some liquid tags - this is just for the generating the site html, please disregard.

## About this fork

We implemented a (dirty) bugfix that address the tooltip cutout problem. This works with a fixed value, so, if you play with the `tooltipXPadding` value, the result can differ.
Also, there is a new option:
```
// Boolean - Whether to show labels on X axis
dataShowLabels: true,
```

On `false`, this not only hides the X row labels, but also compensates some paddings

## Todo

This is the code that adds some extra margins to avoid the tooltip cutout.
```
this.xScalePaddingRight = lastWidth/2 + 14;
```
```
this.xScalePaddingRight = this.padding + 14;
```
`14` could be in fact `tooltipXPadding * 2`, but the options are not available on this function. We need to follow the code flow to inject those values.

## License

Chart.js is available under the [MIT license](http://opensource.org/licenses/MIT).
