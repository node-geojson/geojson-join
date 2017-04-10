# geojson-join

[![Greenkeeper badge](https://badges.greenkeeper.io/tmcw/geojson-join.svg)](https://greenkeeper.io/)

Join a stream of GeoJSON against a dataset.

## install

    npm install -g geojson-join

## usage

* againstField: the field in the dataset to join against geojson
* geojsonField: the field in the geojson feature properties
* `format`: format of the dataset. can be json, csv, dbf. Default json.

Accepts GeoJSON on stdin and the joined-against file as an argument

```sh
$ geojson-join test/against.json \
    --againstField=id \
    --geojsonField=id < test/random.geojson
```

```sh
$ geojson-join --format=dbf \
    test/against.dbf \
    --againstField=id \
    --geojsonField=id < test/random.geojson
```
