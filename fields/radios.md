# radios

This is simple list of radio buttons to select

## Special properties of field

| Property | Default | Accepted values | Description |
| --- | --- | --- | --- |
| `values` | _none_ | `Array` or `Function` | List of items. It can be an array with items, or a `Function`, what is resulted an array. The item can be a `String`, `Boolean`, `Number` or an `Object` (with an `value` and a `name` properties). You can change `value` and `name` \(under `radiosOptions`\) to select any properties of that object as value or name. |
| `radiosOptions` | {} | `Object` | Settings to radios component. See details below. |

### `radiosOptions`

| Property | Default | Accepted values | Description |
| --- | --- | --- | --- |
| `value` | _none_ | `String` | Used to select any properties from object in `values` to use as actual value to save in model. |
| `name` | _none_ | `String` | Used to select any properties from object in `name` to use as display in the list |

## Usage

#### Radios field with array of strings:

```js
{
    type: "radios",
    label: "Very best friend",
    model: "friend",
    values: [
        "James",
        "Nadia",
        "Paul",
        "Christelle",
        "Marc",
        "Marie"
    ]
}
```
#### Radios field with object values:

```js
{
    type: "radios",
    label: "Choose you product color",
    model: "color",
    values: [
        {name: "Deep Pink", value:"#FF1493"},
        {name: "Peach Puff", value:"#FFDAB9"},
        {name: "Dark Orange", value:"#FF8C00"},
        {name: "Light Green", value:"#90EE90"}
    ]
}
```




#### Radios field with custom object values:

```js
{
    type: "radios",
    label: "Identify the dolphin's name from the photo",
    model: "dolphin",
    values: [
        {common_name: "White-beaked dolphin", binomial_nomenclature:"Lagenorhynchus albirostris"},
        {common_name: "Peale's dolphin", binomial_nomenclature:"Lagenorhynchus australis"},
        {common_name: "Northern right whale dolphin", binomial_nomenclature:"Lissodelphis borealis"},
        {common_name: "Common bottlenose dolphin", binomial_nomenclature:"Tursiops truncatus"},
        {common_name: "Long-beaked common dolphin", binomial_nomenclature:"Delphinus capensis"},
        {common_name: "Pacific white-sided dolphin", binomial_nomenclature:"Lagenorhynchus obliquidens"},
        {common_name: "Pantropical spotted dolphin", binomial_nomenclature:"Stenella attenuata"},
        {common_name: "Chilean dolphin", binomial_nomenclature:"Cephalorhynchus eutropia"}
    ],
    radiosOptions: {
        value:"binomial_nomenclature",
        name:"common_name"
    }
}
```



