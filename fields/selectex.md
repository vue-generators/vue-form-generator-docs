# selectEx field
This is a select list field for multiple selection.

> Please note, this field depend on the following library:
- [jQuery](http://www.jquery.com)
- [BootStrap](http://getbootstrap.com/)
- [bootstrap-select](https://silviomoreto.github.io/bootstrap-select/)

## Special properties of field

Property        | Default  | Accepted values | Description
--------------- | -------- | --------------- | ----------- 
`multiSelect`   | _none_   | `Boolean`       | If `true`, you can select multiple items. In this case the value will be an `Array`
`values`        | _none_   | `Array` or `Function` | List of items. It can be an array with items, or a function, what is resulted an array. The item will be a `String` or an object with an `id` and a `name` properties.
`selectOptions` | `{}`     | `Object` 		| Settings to select component. [Read more info from options](https://silviomoreto.github.io/bootstrap-select/options/)
### selectOptions
@TODO
## Usage
#### Multiple select list with array of strings:

```js
{
    type: "selectEx",
    label: "Skills",
    model: "skills",
    multi: true,
    required: true,
    multiSelect: true,
    selectOptions: {
        liveSearch: true,
        maxOptions: 3,
        size: 4,
        selectedTextFormat: "count > 3"
    },
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

#### Simple select list:
```js
{
    type: "selectEx",
    label: "Country",
    model: "address.country",
    required: true,
    multiSelect: false,
    values: faker.definitions.address.country,
    default: "United Kingdom",
    selectOptions: {
        liveSearch: true,
        size: 10
    },
    validator: validators.required
}
```
