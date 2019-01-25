# Select field

This is a HTML `select` & `option` selection list field. You can only select one item.

## Special properties of field

| Property | Default | Accepted values | Description |
| --- | --- | --- | --- |
| `values` | _none_ | `Array` or `Function` | List of items. It can be an array with items, or a `Function`, what is resulted an array. The item will be a `String` or an object with an `id` and a `name` properties. |
| `selectOptions` | {} | `Object` | Settings to select component. See details below. |

### `selectOptions`

| Property | Default | Accepted values | Description |
| --- | --- | --- | --- |
| `noneSelectedText` | `<Nothing selected>` | `String` | Change the text for the no selection option. |
| `hideNoneSelectedText` | `false` | `Boolean` | Hide the noneSelected item |
| `value` | `id` | `String` | Used to select any properties from object in `values` to use as actual value to save in model. |
| `name` | `name` | `String` | Used to select any properties from object in `name` to use as display in the list |



## Usage

#### Select field with array of strings:

```js
{
    type: "select",
    label: "Type",
    model: "type",
    values: [
        "Personal",
        "Business"
    ]
}
```

If you select the first item, the `value` will be `"Personal"` in the model.

### Select field with object items:

```js
{
    type: "select",
    label: "Language",
    model: "lang",
    required: true,
    values: function() {
      return [
        { id: "en-GB", name: "English (GB)" },
        { id: "en-US", name: "English (US)" },
        { id: "de", name: "German" },
        { id: "it", name: "Italic" },
        { id: "fr", name: "French" }
      ]
    },
    default: "en-US",
    validator: validators.required
}
```

If you select the second item, the `value` will be `"en-US"` in the model.

