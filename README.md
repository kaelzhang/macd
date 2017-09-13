[![Build Status](https://travis-ci.org/kaelzhang/macd.svg?branch=master)](https://travis-ci.org/kaelzhang/macd)
[![Coverage](https://codecov.io/gh/kaelzhang/macd/branch/master/graph/badge.svg)](https://codecov.io/gh/kaelzhang/macd)
<!-- optional appveyor tst
[![Windows Build Status](https://ci.appveyor.com/api/projects/status/github/kaelzhang/macd?branch=master&svg=true)](https://ci.appveyor.com/project/kaelzhang/macd)
-->
<!-- optional npm version
[![NPM version](https://badge.fury.io/js/macd.svg)](http://badge.fury.io/js/macd)
-->
<!-- optional npm downloads
[![npm module downloads per month](http://img.shields.io/npm/dm/macd.svg)](https://www.npmjs.org/package/macd)
-->
<!-- optional dependency status
[![Dependency Status](https://david-dm.org/kaelzhang/macd.svg)](https://david-dm.org/kaelzhang/macd)
-->

# macd

FinTech utility to calculate [MACD](https://en.wikipedia.org/wiki/MACD).

**MACD**, short for Moving Average Convergence / Divergence, is a trading indicator used in technical analysis of stock prices, created by Gerald Appel in the late 1970s.

## Install

```sh
$ npm install macd
```

## Usage

```js
import macd from 'macd'

macd(data)

// which returns:
// {
//   MACD: <Array>,
//   signal: <Array>,
//   histogram: <Array>
// }
```

## macd(data, slowPeriods, fastPeriods, signalPeriods)

- **data** `Array.<Number>` the collection of prices
- **slowPeriods** `Number=26` the size of slow periods. Defaults to `26`
- **fastPeriods** `Number=12` the size of fast periods. Defaults to `12`
- **signalPeriods** `Number=9` the size of periods to calculate the MACD signal line.

Returns `MACDGraph`

### struct `MACDGraph`

- **MACD** `Array.<Number>` the difference between [EMAs](https://www.npmjs.com/package/moving-averages#exponential-moving-average-emadata-size) of the fast periods and EMAs of the slow periods.
- **signal** `Array.<Number>` the EMAs of the `MACD`
- **histogram** `Array.<Number>` `MACD` minus `signal`

In some countries, such as China, the three series above are commonly known as:

```sh
MACD       -> DIF
signal     -> DEA
histogram  -> MACD
```

## License

MIT
