# WMTS

[![Build Status](https://travis-ci.org/DenisCarriere/wmts.svg?branch=master)](https://travis-ci.org/DenisCarriere/wmts)
[![npm version](https://badge.fury.io/js/wmts.svg)](https://badge.fury.io/js/wmts)
[![MIT licensed](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/DenisCarriere/wmts/master/LICENSE)

<!-- Line Break -->

[![Standard - JavaScript Style Guide](https://cdn.rawgit.com/feross/standard/master/badge.svg)](https://github.com/feross/standard)

> Flexible WMTS scheme for Javascript applications.

## Install

**npm**

```bash
$ npm install --save wmts
```

**web browser ([ES5](https://kangax.github.io/compat-table/es5))**

```html
<script src="https://unpkg.com/wmts/wmts.min.js"></script>
```

## Quickstart

```javascript
const xml = wmts.getCapabilities({
  url: 'http://localhost:5000/WMTS',
  title: 'Tile Service XYZ',
  format: 'png',
})
//=xml
```

```xml
<declaration version="1.0" encoding="utf-8"/>
<Capabilities xmlns="http://www.opengis.net/wmts/1.0" xmlns:ows="http://www.opengis.net/ows/1.1" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:gml="http://www.opengis.net/gml" xsi:schemaLocation="http://www.opengis.net/wmts/1.0 http://schemas.opengis.net/wmts/1.0/wmtsGetCapabilities_response.xsd" version="1.0.0">
  <ServiceMetadataURL xlink:href="http://localhost:80/WMTS/1.0.0/WMTSCapabilities.xml"/>
  <ows:ServiceIdentification>
    <ows:ServiceTypeVersion>1.0.0</ows:ServiceTypeVersion>
    <ows:ServiceType>OGC WMTS</ows:ServiceType>
...
```

## API

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### getCapabilities

Get Capabilities

**Parameters**

-   `options` **Options** Options
    -   `options.url` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** URL of WMTS service
    -   `options.title` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Title of service
    -   `options.format` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Format 'png' | 'jpeg' | 'jpg'
    -   `options.minzoom` **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)?** Minimum zoom level (optional, default `0`)
    -   `options.maxzoom` **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)?** Maximum zoom level (optional, default `22`)
    -   `options.accessConstraints` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)?** Access Constraints
    -   `options.fees` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)?** Fees
    -   `options.abstract` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)?** Abstract
    -   `options.identifier` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)?** Identifier
    -   `options.keywords` **[Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)&lt;[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)>?** Keywords
    -   `options.bbox` **BBox?** BBox [west, south, east, north]
    -   `options.spaces` **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)?** Spaces created for XML output (optional, default `2`)

**Examples**

```javascript
const xml = wmts.getCapabilities({
  url: 'http://localhost:5000/WMTS',
  title: 'Tile Service XYZ',
  identifier: 'service-123',
  abstract: '© OSM data',
  keyword: ['world', 'imagery', 'wmts'],
  format: 'png',
  minzoom: 10,
  maxzoom: 18,
  bbox: [-180, -85, 180, 85]
})
```

Returns **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** XML string

## License

MIT © [Denis Carriere](https://twitter.com/DenisCarriere)
