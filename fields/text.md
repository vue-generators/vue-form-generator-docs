# Text field `deprecated`
This is a standard HTML `input="text"` input field.

_Please note! This field type is deprecated. Please use the common [`input`](input.md) field type!_

## Special properties of field

Property      | Default  | Accepted values | Description
------------- | -------- | --------------- | -----------
`autocomplete` | _none_   | [see doc](https://html.spec.whatwg.org/multipage/forms.html#autofill)        | Indicates whether the value of the control can be automatically completed by the browser.
`max` 		  | _none_   | `Number` 	   | Max value (need to use `validators.number`)
`pattern`		  | _none_   | `RegExp` 	   | RegExp pattern for validation (need to use `validators.regexp`)
`placeholder` | _none_   | `String` 	   | Placeholder text for input field
`readonly`    | `false`  | `Boolean` 	   | If true, the input field is read only

## Usage
#### Featured and required name input field, where the length of name must be between 3 and 50 characters:

```js
{
	type: "text",
	label: "Name",
	model: "name",
	featured: true,
	min: 3,
	max: 50,
	required: true,
	placeholder: "User's full name",
	validator: validators.string
}
```
#### Text field for website address with url & string validator:
```js
{
	type: "text",
	label: "Website",
	model: "web",
	max: 255,
	validator: [
		validators.string
		validators.url
	]
}
```
#### Text field for phone number with regexp validator:
```js
{
    type: "text",
    label: "Phone",
    model: "phone",
    pattern: "^\\+[0-9]{2}-[237]0-[0-9]{3}-[0-9]{4}$",
    placeholder: "User's phone number",
    hint: "Format: +36-(20|30|70)-000-0000",
    help: "You can use any <b>formatted</b> texts. Or place a <a target='_blank' href='https://github.com/icebob/vue-form-generator'>link</a> to another site."
    validator: validators.regexp
}
```