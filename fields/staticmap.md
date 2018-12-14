# staticMap

This is a Google Static Map service field. It's only show a static map.

> Please note, for this field you need internet access to http://maps.googleapis.com site & maybe Google Maps API key!

## Special properties of field

Property      | Default  | Accepted values | Description
------------- | -------- | --------------- | -----------
`staticMapOptions` | _none_   | `Object` 	   | Settings to static map link. [Read more info from options](https://developers.google.com/maps/documentation/static-maps/intro)

### staticMapOptions
Property      | Default  | Accepted values | Description
------------- | -------- | --------------- | -----------
`lat` | `lat`   | `String` 	   | Name of latitude key in model
`lng` | `lng`   | `String` 	   | Name of longitude key in model
`zoom` | `8`   | `Number` 	   | Zoom level of map
`sizeX` | `640`   | `Number` 	   | X size of image
`sizeY` | `640`   | `Number` 	   | Y size of image
`scale` | _none_   | `String` 	   | Scale affects the number of pixels that are returned
`format` |  _none_   | `String` 	   | Defines the format of the resulting image. By default, the Google Static Maps API creates PNG images. There are several possible formats including GIF, JPEG and PNG types. Which format you use depends on how you intend to present the image. JPEG typically provides greater compression, while GIF and PNG provide greater detail.
`maptype` |  _none_   | `String` 	   | Defines the type of map to construct. There are several possible maptype values, including `roadmap`, `satellite`, `hybrid`, and `terrain`
`language` |  _none_   | `String` 	   | Defines the language to use for display of labels on map tiles.
`region` |  _none_   | `String` 	   | Defines the appropriate borders to display, based on geo-political sensitivities. Accepts a region code specified as a two-character ccTLD ('top-level domain') value.
`markers` |  _none_   | `String` 	   | Define one or more markers to attach to the image at specified locations. This parameter takes a single marker definition with parameters separated by the pipe character (|). 
`path` |  _none_   | `String` 	   | Defines a single path of two or more connected points to overlay on the image at specified locations. This parameter takes a string of point definitions separated by the pipe character (|). 
`visible` |  _none_   | `String` 	   | Specifies one or more locations that should remain visible on the map, though no markers or other indicators will be displayed. Use this parameter to ensure that certain features or map locations are shown on the Google Static Maps API.
`style` |  _none_   | `String` 	   | Defines a custom style to alter the presentation of a specific feature (roads, parks, and other features) of the map. This parameter takes feature and element arguments identifying the features to style, and a set of style operations to apply to the selected features. 
`key` |  _none_   | `String` 	   | Google Maps API key
`signature` |  _none_   | `String` 	   | This is a digital signature used to verify that any site generating requests using your API key is authorized to do so. Note: If you enable billing, the digital signature is required. 


## Usage
#### Show address on map by geolocation coords
```js
{
	type: "staticMap",
	label: "Map",
	model: "address.geo",
	visible: false,
	staticMapOptions: {
        lat: "latitude",
        lng: "longitude",
        zoom: 6,
        sizeX:640,
        sizeY:640,
        scale: 1,
        format:"png",
        // maptype:"satellite",
        language:"FR-fr",
        // region:
        markers:"color:blue%7Clabel:S%7C43.107733,4.541936",
        // path:
        // visible:
        // style:"feature:road.highway%7Celement:labels.text.stroke%7Cvisibility:on%7Ccolor:0xb06eba&style=feature:road.highway%7Celement:labels.text.fill%7Cvisibility:on%7Ccolor:0xffffff",
        // key:
        // signature:
    }
},
```