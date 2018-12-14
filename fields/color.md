# color field `deprecated`
This is a standard HTML5 color picker input field.

_Please note! This field type is deprecated. Please use the common [`input`](input.md) field type!_

## Special properties of field

Property 		| Default | Accepted values | Description
--------------- | ------- | --------------- | -----------
`autocomplete` | _none_   | [see doc](https://html.spec.whatwg.org/multipage/forms.html#autofill)        | Indicates whether the value of the control can be automatically completed by the browser.

## Usage

```js
{
	type: "color",
	label: "Background color",
	model: "backgroundColor",
    default: "#000000"
}
```
