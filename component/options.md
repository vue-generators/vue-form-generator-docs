# Options

Available options for vue-form-generator


Property               | Default    | Type        | Description
--------------------   | ---------- | ----------  | -----------
validateAfterLoad      | `false`    | `boolean`   | Execute validation after model loaded
validateAfterChanged   | `false`    | `boolean`   | Execute validation after every change
fieldIdPrefix          | _none_     | `string`    | Prefix to add to every field's `id`. Will be prepended to ids explicity set in the schema, as well as auto-generated ones.
validateAsync          | `false`    | `boolean`   | `validate()` method returns a Promise, refer to [validation](/validation/custom-validators.md#asynchronous-validators)
validationErrorClass   | `"error"`  | `string`    | CSS Class attached to elements which are invalid
validationSuccessClass | _none_     | `string`    | CSS Class attached to elements which are valid
validateDebounceTime   | `0`        | `integer`   | Amount of time in milliseconds validation waits before checking, refer to [validation](/validation/README.md#debounce)
