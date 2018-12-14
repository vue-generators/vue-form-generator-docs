# googleAddress field

This is an input field that auto-complete address with Google Address.

> Please note, this field depend on the following:
- [Google Maps API](https://developers.google.com/maps/documentation/javascript/places)  
eg. https://maps.googleapis.com/maps/api/js?key=YOUR_KEY&libraries=places

## Special properties of field

Property         | Default  | Accepted values | Description
---------------- | -------- | --------------- | ----------- 
`autocomplete` | _none_   | [see doc](https://html.spec.whatwg.org/multipage/forms.html#autofill)        | Indicates whether the value of the control can be automatically completed by the browser.
`onPlaceChanged` | _none_   | `Function`    | Will be called when the user select an address from list. Parameters of function: `onPlaceChanged(value, place, rawPlace, model, schema) { }`
`placeholder` | _none_   | `String` 	   | Placeholder text for input field
`readonly`    | `false`  | `Boolean` 	   | If true, the input field is read only