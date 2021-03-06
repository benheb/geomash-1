# Geomash

A node.js module for building geohash aggregations in LevelDB. 

## Usage 

There are 2 ways that you can use geomash: on the command line and as a node.js module. 

### Command Line

To use geomash as a command line utility you have to install it globally first

  ```
    npm install geomash -g 
  ```

This install an executable called `geomash` that you can use to create some aggregations. 

  ``` 
Usage: geomash -i [id string] -f [input file] -o [output file] -p [precision number]

Options:
  -i  [required]
  -f  [default: "none"]
  -o  [default: "none"]
  -p  [default: "9"]
  ```

### Node Module 

To use geomash as a node module you also need to install it via `npm install geomash`. Then in side your node app you would do something like

  ```javascript 

    var geomash = require('require')

    geomash.add(id, feature, precision, function (err) {
      geomash.dump(id, function (err, agg) {
        console.log(agg)
      })
    })
 
  ```

## Docs 

Geohash exposes three methods: 

### Add
 
Adds a feature to a geohash aggregation. 

`geomash.add(id, feature, precision, callback)` 

### Clear

Clears the geohash aggregation for a given id. 

`geomash.clear(id, callback)`

### Dump

Dumps out the geohash aggregation for a given id.

`geomash.dump(id, callback)`

