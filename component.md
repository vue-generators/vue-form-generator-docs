# Component

```html
<vue-form-generator :schema="schema" :model="model" :options="formOptions"></vue-form-generator>
```

## Properties

| Property | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| [schema](schema.md) | `Object` | `none` | The schema object with fields |
| [model](model.md) | `Object` | `none` | The model/target JSON object |
    | [options](options.md) | `Object` | `{`<br/>`validateAfterLoad: false,`<br/>`validateAsync: false,`<br/>`validateAfterChanged: false,`<br/>`    validationErrorClass: "error",`<br/>`validationSuccessClass: ""`<br/>`}` | Options for the VueFormComponent |
| multiple | `Boolean` | `false` | If true, we only show `multi: true` fields |
| isNewModel | `Boolean` | `false` | If true, we won't run validation after load |
| tag | `String` | "fieldset" | Change the main HTML element of VueFormGenerator |



