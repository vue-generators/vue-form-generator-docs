# Field properties & methods

## Common properties of field

| Property | Default | Accepted values | Description |
| --- | --- | --- | --- |
| type | _none_ | `String` | Type of field |
| label | _none_ | `String` | Label of field |
| model | _none_ | `String` | Name of property in the model |
| id | _auto-generated_ | `String` | `id` of the field. If not set, will be auto-generated from the slugified version of either: `schema.inputName`, `schema.label` or `schema.model`, in that order. If the [`fieldIdPrefix` option](/options.md) is set, it's value will be prepended to both manual & auto-generated ids. |
| inputName | _none_ | `String` | set `name` attribute to `input` field. You can use it to generate normal HTML Forms and submit the field values to server-side. [Example](https://github.com/vue-generators/vue-form-generator/tree/master/examples/post-form) |
| featured | `false` | `Boolean` | is it a featured \(bold\) field? It can be a function too. |
| visible | `true` | `Boolean` | if `false`, field will be hidden. It can be a function too. |
| disabled | `false` | `Boolean` | if `true`, field will be disabled. It can be a function too. |
| required | `false` | `Boolean` | if `true`, must be fill this field \(need to use validator\). |
| multi | `false` | `Boolean` | if `true`, it will be visible only  if `multiple` is `true` in component attributes |
| default | _none_ | any | Default value of the field \(used when creating a new model\) |
| hint | _none_ | `String` | show this hint below the field |
| help | _none_ | `String` | show this help if mouse hover the question icon before the caption of field. _You can use HTML elements too._ |
| [validator](/validation/README.md) | _none_ | `Function` or `Array` | Validator for value. It can be an array of functions too. |
| [validateDebounceTime](/validation/README.md#debounced-validation) | _none_ | Amount of time in milliseconds validation waits before checking, refer to [validation](/validation/README.md#debounced-validation)
| styleClasses | _none_ | `String` or `Array` | custom css style classes. They will be appended to the `.from-group` |
| [buttons](inside_buttons.md) | _none_ | `Array` | Array of button objects. This is useful if you need some helper function to fill the field. _\(E.g. generate password, get GPS location..etc\)\*_ |

## Common methods of field

| Method | Description |
| --- | --- |
| `get: function(model) {...}` | A read formatter function where you can format the model value to the field |
| `set: function(model, value) {...}` | A write formatter function where you can format the field value to the model |

## Common events of field

| Name | Attributes | Description |
| --- | --- | --- |
| `onChanged` | `(model, newVal, oldVal, field)` | Triggered if the value of field is changed. |
| `onValidated` | `(model, errors, field)` | Triggered if validation of field is executed. |

## Example

```js
{
    type: "input",
    inputType: "text",
    label: "Name",
    model: "name",
    id: "full_name",
    readonly: false,
    featured: true,
    disabled: false,
    required: true,
    default: "Anonymous",
    hint: "Please enter your full name",
    help: "This is an other longer help text",
    validator: validators.string,

    onChanged: function(model, newVal, oldVal, field) {
        console.log(`Model's name changed from ${oldVal} to ${newVal}. Model:`, model);
    },

    onValidated: function(model, errors, field) {
        if (errors.length > 0)
            console.warn("Validation error in Name field! Errors:", errors);
    }
}
```

## Dynamic visibility

With the `visible, disabled, readonly` and `featured` properties, you can also show or disable fields dynamically.  
Those properties can take a `Function` with a `model` parameters and expect a `Boolean` in return.

```js
{
  type: "select",
  label: "Type",
  model: "type",
  values: [
    { id: "personal", name: "Personal" },
    { id: "business", name: "Business" }
   ]
},{
  type: "text",
  label: "Company name",
  model: "company.name",
  visible: function(model) {
    //visible if business is selected
    return model && model.type == "business";
  }
}
```

## Generated `values`

For fields [select](select.md), [checklist](checklist.md), [selectEx](selectex.md) or [vueMultiSelect](vuemultiselect.md), the `values` property can be a `Function`. In this case, you can dynamically generate the items.

```js
{
    type: "select",
    label: "Item",
    model: "item",
    // values gets model and schema as parameters
    values: function(model, schema) {
        switch(model.category) {
            case "Fruit": return ["Apple", "Peach", "Orange"];
            case "Vehicle": return ["Car", "Bicycle", "Ship"];
            case "Animals": return ["Lion", "Dog", "Cat"];
        }

        return [];
    }
}
```

## Custom properties

You can add custom properties, such as `data-attributes`, to fields by using an `attributes` object. To add properties to the input field itself, simply specify the attribute names and values in the model:

```javascript
{
  type: "input",
  inputType: "text",
  model: "first_name",
  label: "First Name",
  attributes: {
    "data-toggle": "collapse",
    "title": "Some Tooltip Title"
  }
}
```

You can also specify the attributes of the surrounding wrapper and label:

```javascript
{
  type: "input",
  inputType: "text",
  model: "first_name",
  label: "First Name",
  attributes: {
    wrapper: { "data-toggle": "collapse" },
    input: { "data-toggle": "tooltip", "title": "Some Tooltip to be displayed by Bootstrap Tooltips" },
    label: { "custom-attr": "custom-value" }
  }
}
```
