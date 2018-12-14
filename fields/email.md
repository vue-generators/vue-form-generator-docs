# email field `deprecated`
This is a HTML5 `type="email"` input field.

_Please note! This field type is deprecated. Please use the common [`input`](input.md) field type!_

## Special properties of field
Property      | Default  | Accepted values | Description
------------- | -------- | --------------- | -----------
`autocomplete` | _none_   | [see doc](https://html.spec.whatwg.org/multipage/forms.html#autofill)        | Indicates whether the value of the control can be automatically completed by the browser.
`placeholder` | _none_   | `String` 	   | Placeholder text for input field
`readonly`    | `false`  | `Boolean` 	   | If true, the input field is read only


## Usage

```js
{
	type: "email",
	label: "E-mail",
	model: "email",
    required: true
}
```
