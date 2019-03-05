# Schema

Events emitted by the [VFG Component](README.md)

## validated

This event is triggered whenever the form has completed validating.  It provides the `boolean` result of this validation, any errors that may have occurred and a reference to the VFG component which triggered the validation.

Internally, the event is triggered with 

```js
this.$emit("validated", isValid, this.errors, this);
```

`isValid` will contain a `boolean` value indicating whether the form is valid, `true` indicates the the validation succeeded.  `false` indicates that it failed, and the errors array will contain any error messages from the validation rules.

You can listen for this by attaching to the `@validated` (`v-validated`) event on the `<vue-form-generator />` component.


## model-updated

This event is triggered whenever the the model attached to the form has been updated, usually due to user interaction.  It provides the new value and a reference to the property name for the field which was just updated.  This event is triggered each time a field is updated.

Internally, the event is triggered with
```js
this.$emit("model-updated", newVal, schema);
```

`newVal` is the value that was just updated, and `schema` is a reference to the model's property name found in the [field schema](schema.md).  `schema` will only contain the individual property name, and not the full schema.  This allows you to identify which field was just updated.

You can listen for this by attaching to the `@model-updated` (`v-model-updated`) event on the `<vue-form-generator />` component.