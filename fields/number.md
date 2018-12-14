# Number field `deprecated`
This is an input field for numeric values.

_Please note! This field type is deprecated. Please use the common [`input`](input.md) field type!_

## Special properties of field

Property      | Default  | Accepted values | Description
------------- | -------- | --------------- | ----------- 
`autocomplete` | _none_   | [see doc](https://html.spec.whatwg.org/multipage/forms.html#autofill)        | Indicates whether the value of the control can be automatically completed by the browser.
`max` 		  | _none_   | `Number` 	   | Max value (need to use `validators.number`)
`min` 		  | _none_   | `Number` 	   | Min value (need to use `validators.number`)
`placeholder` | _none_   | `String` 	   | Placeholder text for input field
`readonly`    | `false`  | `Boolean` 	   | If true, the input field is read only

## Usage
```js
{
	type: "number",
	label: "Age",
	model: "age",
	min: 18,
	max: 100,
	placeholder: "Age of user",
	validator: validators.number
}
```