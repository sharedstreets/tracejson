# TraceJSON

TraceJSON is a GeoJSON extension for expressing GPS path data. It is designed for simplicity and compatibility with existing geo tools.

## Format

TraceJSON is a valid GeoJSON Feature with a LineString geometry. An optional `timestamps` property is added containing an array of UTC epoch millisecond timestamps. If a `timestamps` property is included with a feature, it must have the same number of elements as there are positions in the `coordinates` array for the LineString geometry.

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
