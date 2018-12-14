# Handling Validation Events

The `vue-form-generator` component emits a validated event, if validation is executed.

The event parameters are: `isValid: boolean, errors: Array`.

## Example:

You can create a method to handle this event and bind it like this:

```html
<vue-form-generator @validated="onValidated" />
```

```js
methods: {
  onValidated(isValid, errors) {
   console.log("Validation result: ", isValid, ", Errors:", errors);
  }
}
```
