# Creating Isochrones with Python and Distance APIs

## Assumptions

* [pipenv](https://github.com/kennethreitz/pipenv)

## Installation

### Install Python dependencies

```
pipenv --three
pipenv install
```

## Running the notebook

```
pipenv shell
jupyter-notebook Isochrones\ with\ Python\ and\ APIs.ipynb
```

## Geocoding an address

### [U.S. Census Bureau Geocoder]()

If you just want to geocode one address really quickly, the U.S. Census Bureau Geocoder has a [web form](https://geocoding.geo.census.gov/geocoder/locations/onelineaddress?form).  They have [another form](https://geocoding.geo.census.gov/geocoder/locations/addressbatch?form) that lets you geocode all addresses in a CSV file. 

There's also an [API](https://geocoding.geo.census.gov/geocoder/Geocoding_Services_API.html) that lets you geocode individual addresses, or a batch of addresses as CSV.

This API is free to use, but only works for U.S. addresses.

It also seems to be broken right now.

### Texas A&M University Geocoder

If you just want to geocode one address, there is an [interactive geocoder](http://geoservices.tamu.edu/Services/Geocode/Interactive/).

## Some API options

### Google Maps Distance Matrix API

[Developer's Guide](https://developers.google.com/maps/documentation/distance-matrix/intro)

Pros:

* Supports transit

Cons:

* Can only be used to display information on a Google Map
* Have to make multiple queries to query distances along a radius to build isocrhone

### HERE Routing API

[Quick Start Guide](https://developer.here.com/documentation/routing/topics/request-isoline.html)
[API Reference](https://developer.here.com/documentation/routing/topics/resource-calculate-isoline.html)

Pros:

* API returns the isochrone itself

Cons:

* Only supports car and pedestrian modes of transport

### Mapbox Distance API

[API Documentation](https://www.mapbox.com/api-documentation/#matrix)

Pros:

* More permissive uses than Google's API

Cons:

* Have to make multiple queries to query distances along a radius to build isocrhone
* Doesn't support transit

#### Mapzen Isochrone Service

[Service description](https://mapzen.com/products/isochrone/)

[API documentation](https://mapzen.com/documentation/mobility/isochrone/api-reference/)

Pros:

* More permissive uses than Google's API
* Supports Driving, Cycling, Walking and Transit
* Response is GeoJSON

Cons:

* None that I can immediately think of.  This seems pretty sweet!

## Thanks

To Sahil Chinoy who made these awesome [isochrones of leaving metro areas for the weekend](https://www.washingtonpost.com/graphics/2017/national/escape-time/?utm_term=.ab11d1c99c62) and told me about the HERE API.
