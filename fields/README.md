# Fields

A field in the schema defines an input element to a value of model. For example, if you want to edit the `model.selections` value with a select field, you have to create a field with `select` type, what looks like this:

```js
{
    type: "select",
    label: "Selections",
    model: "selections"
},
```

Each field has its own options, so be sure to check out their documentations.  
For example, input field need an `inputType` to be specified as well.

```js
{
    type: "input",
    inputType: "text",
    label: "Name",
    model: "name"
},
```

## Available fields

### [Core fields](/fields/core-fields.md)

These fields are available in the core version of VueFormGenerator.

* [`checkbox`](checkbox.md) - Checkbox for boolean values
* [`checklist`](checklist.md) - Checkbox list to select multiple values
* [`input`](input.md) - Common input field `NEW!`
* [`label`](label.md) - Static text \(e.g. timestamp, creation time...etc\)
* [`radios`](radios.md) - Radio buttons to select `NEW!`
* [`select`](select.md) - Select list
* [`submit`](submit.md) - This is a simple submit button
* [`textArea`](textarea.md) - Text area field

### [Optional fields](/fields/optional_fields.md)

These fields are available in the full version of VueFormGenerator. Some of these also have external dependency.

* [`cleave`](cleave.md) - Format input text content when you are typing
* [`dateTimePicker`](datetime.md) - datetime picker with bootstrap-datetimepicker component
* [`googleAddress`](googleaddress.md) - Format input text content when you are typing
* [`image`](image.md) - Image select field \(URL or upload in base64 string\)
* [`masked`](masked.md) - Masked text input field with maskedinput component
* [`noUiSlider`](nouislider.md) - Lightweight JavaScript range slider
* [`pikaday`](pikaday.md) - A refreshing JavaScript Datepicker
* [`selectEx`](selectex.md) - select list with the bootstrap-select component
* [`slider`](slider.md) - pretty range slider with ion.rangeSlider component
* [`spectrum`](spectrum.md) - Color picker with "The No Hassle" Spectrum jQuery Colorpicker component
* [`staticMap`](staticmap.md) - Display a static map from Google Maps.
* [`switch`](switch.md) - Switch field \(toggle two values \(on/off, yes/no, active/inactive\)
* [`vueMultiSelect`](vuemultiselect.md) - Probably the most complete selecting solution for Vue.js

### [Custom fields](custom_fields.md)

You can create custom fields too. [Check here how you can do it](custom_fields.md).
