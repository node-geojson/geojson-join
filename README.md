# geojson-join

Join a stream of GeoJSON against a dataset.

## install

    npm install -g geojson-join

## usage

* againstField: field/s in the dataset to join against geojson
* geojsonField: field/s in the geojson feature properties
* `format`: format of the dataset. can be json, csv, dbf. default json.
* `type`: type to cast a field with in the dataset. type can be string, int, float.

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

```sh
$ geojson-join --format=csv \
    --type=population:int \
    --type=area:float \
    test/against.csv \
    --againstField=id \
    --geojsonField=id < test/random.geojson
```
