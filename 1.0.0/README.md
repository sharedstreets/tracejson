# TraceJSON

TraceJSON is a [GeoJSON](https://geojson.org) extension for expressing GPS path data. It is designed for simplicity and compatibility with existing geo tools. 

## Format

TraceJSON is a valid [GeoJSON Feature](https://tools.ietf.org/html/rfc7946#section-3.2) with a [LineString geometry](https://tools.ietf.org/html/rfc7946#section-3.1.4). An optional `timestamps` property is added containing an array of [UTC epoch millisecond timestamps](https://currentmillis.com). If a `timestamps` property is included with a feature, it must have the same number of elements as there are positions in the [`coordinates`](https://tools.ietf.org/html/rfc7946#section-3.1.1) array for the LineString geometry.

## Collections

GPS data is often used in bulk. Collections of TraceJSON may be expressed as GeoJSON FeatureCollections or as [GeoJSONSeq](https://gdal.org/drivers/vector/geojsonseq.html) line delimited features. Line delimited features are highly encouraged for simplified parsing of streams of data.

## Example

```json
{
  "type": "Feature",
  "properties": {
    "timestamps": [
       1564011260021,
       1564011261801,
       1564011262345,
       1564011263968,
       1564011264112,
       1564011265883
     ]
  },
  "geometry": {
    "type": "LineString",
    "coordinates": [
      [
        -122.4108213186264,
        37.75107907205886
      ],
      [
        -122.41099298000334,
        37.751104521219816
      ],
      [
        -122.41120755672455,
        37.751053622889174
      ],
      [
        -122.41160988807678,
        37.751032415241085
      ],
      [
        -122.41179764270781,
        37.75092637690943
      ],
      [
        -122.41169571876526,
        37.75056160388812
      ]
    ]
  }
}
```

## Implementations

- [sharedstreets-js](https://github.com/sharedstreets/sharedstreets-js)
- [trip-simulator](https://github.com/sharedstreets/trip-simulator)
- [trip-flows](https://github.com/sharedstreets/trip-flows)

## Related

- [GPX, an XML based GPS format](https://www.topografix.com/gpx.asp)
