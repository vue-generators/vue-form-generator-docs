# submit field
This is a simple `<input type=submit>`.

## Special properties of field

Property               | Default  | Accepted values | Description
---------------------- | -------- | --------------- | ----------- 
`buttonText`           | _none_   | `String`        | text of submit button
`onSubmit`             | _none_   | `Function`      | Will be called when you press the button
`validateBeforeSubmit` | `false`  | `Boolean` 	    | If true, run validation after the button click. If validation is successful, call the `onSubmit` callback from the schema

