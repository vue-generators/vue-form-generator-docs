# Checklist field
This is a checkbox list for multiple selection. The value will be an `Array`.

## Special properties of field

Property   | Default  | Accepted values       | Description
---------- | -------- | --------------------- | -----------
`listBox`  | `false`  | `Boolean`             | If `true`, render the items as a listBox. If `false`, render as a comboBox.
`values`   | _none_   | `Array` or `Function` | List of items. It can be an array with items, or a `Function`, what is resulted an array. The item can be a `String`, `Boolean`, `Number` or an `Object` (with an `value` and a `name` properties). You can change `value` and `name` \(under `checklistOptions`\) to select any properties of that object as value or name. 
| `checklistOptions` | {} | `Object` | Settings to checklist component. See details below. |

### `checklistOptions`

| Property | Default | Accepted values | Description |
| --- | --- | --- | --- |
| `value` | _none_ | `String` | Used to select any properties from object in `values` to use as actual value to save in model. |
| `name` | _none_ | `String` | Used to select any properties from object in `name` to use as display in the list |


## Usage
#### Listbox checklist field with array of strings:

```js
{
	type: "checklist",
	label: "Skills",
	model: "skills",
    listBox: true,
    values: [
        "HTML5",
        "Javascript",
        "CSS3",
        "CoffeeScript",
        "AngularJS",
        "ReactJS",
        "VueJS"
    ]    
}
```

#### Combobox checklist field with `values` function:
```js
{
	type: "checklist",
	label: "Skills",
	model: "skills",
    values: function() {
      return [
        "HTML5",
        "Javascript",
        "CSS3",
        "CoffeeScript",
        "AngularJS",
        "ReactJS",
        "VueJS"
      ]    
    }),
    validator: validators.array
}
```
If you select the 2nd and 4th items, the `value` will be `["Javascript", "CoffeeScript"]` in the model.

#### Checklist field with object values:
```js
{
    type: "checklist",
    label: "Roles",
    model: "roles",
    values: [
        { value: "admin", name: "Administrator"},
        { value: "moderator", name: "Moderator"},
        { value: "user", name: "Registered User"},
        { value: "visitor", name: "Visitor"}
}
```
If you select the first and last items, the `value` will be `["admin", "visitor"]` in the model.

#### Checklist field with custom object values:
```js
{
    type: "checklist",
    label: "Ingredient",
    model: "ingredient",
    values: [
        { uuid: "a11e3f4b-d4f1-45ed-87fc-4eabda4e667e", name: "Cherimoya"},
        { uuid: "5ceb59c6-efe6-4c8a-a4bd-0ef621cd1e5d", name: "Pummelo"},
        { uuid: "39f05038-39ba-4cb9-8508-720806dcb20b", name: "Jabuticaba"},
        { uuid: "94adbe8d-f9db-481c-97c0-7198d5f3d810", name: "Kiwano melon"}
    ],
    checklistOptions: {
        value: "uuid" 
    }
}
```
