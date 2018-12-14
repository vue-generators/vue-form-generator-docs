# checkbox field
This is a standard HTML checkbox input field for boolean values.

## Special properties of field
Property        | Default  | Accepted values       | Description
--------------- | -------- | --------------------- | -----------
`autocomplete` | _none_   | [see doc](https://html.spec.whatwg.org/multipage/forms.html#autofill)               | Indicates whether the value of the control can be automatically completed by the browser.

## Usage

```js
{
	type: "checkbox",
	label: "Status",
	model: "status",
    default: true
}
```
