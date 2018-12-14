# Range field `deprecated`
This is a HTML5 internal range slider input field.

_Please note! This field type is deprecated. Please use the common [`input`](input.md) field type!_

## Special properties of field

Property      | Default  | Accepted values | Description
------------- | -------- | --------------- | -----------
`autocomplete` | _none_   | [see doc](https://html.spec.whatwg.org/multipage/forms.html#autofill)        | Indicates whether the value of the control can be automatically completed by the browser.
`max` 		  | _none_   | `Number` 	   | Max value (need to use `validators.number`)
`min` 		  | _none_   | `Number` 	   | Min value (need to use `validators.number`)


## Usage
```js
{
	type: "range",
	label: "Rating",
	model: "rating",
	min: 1,
	max: 10
}
```