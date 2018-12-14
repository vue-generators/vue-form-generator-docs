# Image field
This is an image input field. You can set an URL of image, or upload from computer. In this case the value of model will be an base64 encoded string.

## Special properties of field

Property      | Default  | Accepted values | Description
------------- | -------- | --------------- | -----------
`autocomplete` | _none_   | [see doc](https://html.spec.whatwg.org/multipage/forms.html#autofill)        | Indicates whether the value of the control can be automatically completed by the browser.
`browse`      | `true`   | `Boolean`       | If `true`, the file browser input field is visible.
`placeholder` | _none_   | `String` 	   | Placeholder text for input field
`hideInput`   | `false`  | `Boolean` 	   | Hidden the `link` input field
`preview`     | `true`   | `Boolean`       | If `true`, the preview is visible.
`readonly`    | `false`  | `Boolean` 	   | If true, the input field is read only

## Usage
#### Image field with browse and preview
```js
{
    type: "image",
    label: "Avatar",
    model: "avatar",
    required: true
}
```
#### Image field without browse
```js
{
    type: "image",
    label: "Avatar",
    model: "avatar",
    required: true,
    browse: false
    preview: true
}
```
