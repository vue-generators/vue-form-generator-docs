# TextArea field

This is a standard HTML `textarea` input field.

## Special properties of field

| Property | Default | Accepted values | Description |
| --- | --- | --- | --- |
| `autocomplete` | _none_ | [see doc](https://html.spec.whatwg.org/multipage/forms.html#autofill) | Indicates whether the value of the control can be automatically completed by the browser. |
| `max` | _none_ | `Number` | maxlength value \(need to use `validators.number`\) |
| `min` | _none_ | `Number` | minlength value \(need to use `validators.number`\) |
| `placeholder` | _none_ | `String` | Placeholder text for input field |
| `readonly` | `false` | `Boolean` | If true, the input field is read only |
| `rows` | 2 | `Number` | Number of rows. |

## Usage

```js
{
    type: "textArea",
    label: "Biography",
    model: "bio",
    hint: "Max 500 characters",
    max: 500,
    placeholder: "User's biography",
    rows: 4,
    validator: validators.string
}
```



