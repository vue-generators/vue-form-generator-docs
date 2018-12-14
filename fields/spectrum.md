# spectrum field
This is a "The No Hassle" color picker  component.

> Please note, this field depend on the following library:
- [jQuery](http://www.jquery.com)
- [spectrum](https://github.com/bgrins/spectrum)

## Special properties of field

Property        | Default  | Accepted values | Description
--------------- | -------- | --------------- | ----------- 
`autocomplete` | _none_   | [see doc](https://html.spec.whatwg.org/multipage/forms.html#autofill)         | Indicates whether the value of the control can be automatically completed by the browser.
`colorOptions`  | `{}`     | `Object` 		 | Settings to picker. [Read more info from options](http://bgrins.github.io/spectrum/)
`placeholder`   | _none_   | `String` 	     | Placeholder text for input field
`readonly`      | `false`  | `Boolean` 	    | If true, the input field is read only

### `colorOptions`
@TODO
## Usage

```js
{
    type: "spectrum",
    label: "Color",
    model: "favoriteColor",
    colorOptions: {
       preferredFormat: "rgb"
    }
}
```
