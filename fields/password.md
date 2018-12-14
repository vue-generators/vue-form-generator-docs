# password field `deprecated`
This is a `type="password"` input field.

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
	type: "password",
	label: "Password",
    model: "password",
    min: 6,
    required: true,
    hint: "Minimum 6 characters"
}
```


