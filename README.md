# geocoder-proxy

## Consuming various geocoding services through a unique GeocodeJSON API

Assuming that `geocoder-proxy` is listening on `localhost`, port
`8080`, you can geocode a random address through these URLs:

* `http://localhost:8080/google/?q=15+rue+lacharriere+PARIS`
* `http://localhost:8080/openstreetmap/?q=15+rue+lacharriere+PARIS`

In these examples, `google`or `openstreetmap` are *services* which are
configured locally with custom settings and API key (see:
[`services.example.js`](services.example.js).


### GeocodeJSON: a standard proposal for geocoding request/responses

Most geocoders offer an HTTP JSON API for geocoding. The XML format is
also widely used, but heavier to implement. Some services offer both.

The [GeocodeJSON spec](https://github.com/geocoders/geocodejson-spec)
aims to have *standard geojson responses from geocoders*. GeocodeJSON
extends the GeoJSON standard, adding geocoding-specific attributes.

More info here:
https://github.com/plateforme-nationale-geocodage/geocodejson-spec/tree/master/draft/README.md



### Use case: French benchmarking of geocoding services

the [French National Geocoding Platform](http://www.plateforme-nationale-geocodage.fr/)
.... link to spec
.... talk about node-geocoder (credit)
link to PIA PNG


## Setup and run

First, you need [NodeJS](https://nodejs.org/en/download/package-manager/) and
NPM.

If downloading from GitHub, you also need a Git client.

Installation:
```
$ git clone https://github.com/plateforme-nationale-geocodage/geocoder-proxy.git
$ cd geocoder-proxy
$ npm install
```

Configuration:
```
$ cp services.example.js services.js
```

Then, edit `services.js` with your favorite text editor. Refer to
[`services.example.js`](./services.example.js) for information.

Run:
```
./geocoder-proxy
```

## Credits

* `geocoder-proxy` itself was written in 2016 by
  [@jfgigand](https://github.com/jfgigand), as part of the French
  National Geocoding Platform project
  (*[Plateforme nationale de géocodage](http://www.plateforme-nationale-geocodage.fr/)),
  founded by the French government.
  
* The program is largely based upon the NodeJS library
  [node-geocoder](https://github.com/nchaulet/node-geocoder),
  written by Nicolas Chaulet
  ([@nchaulet](https://github.com/nchaulet)), which handles the actual
  requests to upstream geocoding services.

