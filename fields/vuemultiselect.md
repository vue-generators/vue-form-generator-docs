# vueMultiSelect field

Probably the most complete selecting solution for Vue.js, without jQuery.

> Please note, this field depends on the following library:
>
> * [Vue-multiselect](http://monterail.github.io/vue-multiselect/)

## Special properties of field

| Property | Default | Accepted values | Description |
| --- | --- | --- | --- |
| `values` | _none_ | `Array` or `Function` | List of items. It can be an array with items, or a function, what is resulted an array. The item can be a `String` or an object. You can use `id` and `key` \(under `selectOptions`\) to select any properties of that object as value or name. |
| `max` | _none_ | `Number` | Number of allowed selected options. |
| `selectOptions` | `{}` | `Object` | Settings to select component. See details below. |

### `selectOptions`

For more details, see the official [Vue-multiselect documentation](http://monterail.github.io/vue-multiselect/#props).

| Property | Default | Accepted values | Description |
| --- | --- | --- | --- |
| `id` | _none_ | `Integer` or `String` | Used to identify the component in events. |
| `multiple` | `false` | `Boolean` | Equivalent to the `multiple` attribute on a <select> input. |
| `trackBy` | _none_ | `String` | Used to compare objects. **Only use if options are objects.** |
| `label` | _none_ | `String` | Label from option Object, that will be visible in the dropdown. |
| `searchable` | `true` | `Boolean` | Add / removes search input. |
| `clearOnSelect` | `true` | `Boolean` | Clear the search input after selection. Use only when multiple is true. |
| `hideSelected` | `false` | `Boolean` | Hide already selected options |
| `allowEmpty` | `true` | `Boolean` | Allows to remove all selected values. Otherwise one must be left selected. |
| `resetAfter` | `false` | `Boolean` | Reset internal `this.value`, `this.search`, `this.selected` after `this.value` changes. |
| `closeOnSelect` | `true` | `Boolean` | Enable/disable closing after selecting an option |
| `customLabel` | _none_ | `Function => String` | Function used to create a custom label |
| `taggable` | `false` | `Boolean` | Disable / Enable tagging |
| `tagPlaceholder` | `'Press enter to create a tag'` | `String` | String to show when highlighting a potential tag |
| `optionsLimit` | 	1000 | `Number` | Limits the options displayed in the dropdown to the first X options. |
| `groupValues` | _none_ | `String` | Name of the property containing the group values |
| `groupLabel` | _none_ | `String` | Name of the property containing the group label |
| `blockKeys` | `[]` | `Array` | Array of keyboard key aliases to block when selecting |
| `internalSearch` | `true` | `Boolean` | Decide whether to filter the results based on search query. Useful for async filtering, where we search through more complex data. |
| `selectLabel` | `'Press enter to select'` | `String` | String to show when pointing to an option |
| `selectedLabel` | `'Selected'` | `String` | String to show next to selected option |
| `deselectLabel` | `'Press enter to remove'` | `String` | String to show when pointing to an already selected option |
| `showLabels` | `true` | `Boolean` | Decide whether to show labels on highlighted options |
| `limit` | `99999` | `Number` | Limit the display of selected options. The rest will be hidden within the limitText string. |
| `limitText` | ``count => `and ${count} more` `` | `Function => String` | Function that process the message shown when selected elements pass the defined limit. |
| `loading` | `false` | `Boolean` | Show/hide the loading spinner. |
| `maxHeight` | `300` | `Integer` | Sets max-height style value of the dropdown |
| `showPointer` | `true` | `Boolean` | Enable/disable highlighting of the pointed value. |
| `onSearch` | _none_ | `Function(searchQuery, id, options)` | Emitted after the search query changes |
| `onNewTag` | _none_ | `Function(newTag, id, options, value)` | Emitted after user attempt to add a tag |

## Usage

#### Simple select primitive:

```js
{
  type: "vueMultiSelect",
  label: "Country",
  placeholder: "Select a country",
  model: "address.country",
  required: true,
  validator: validators.required,
  values: faker.definitions.address.country,
  selectOptions: {
    multiSelect: false,
    closeOnSelect: false,
    searchable: false,
    showLabels: false
  }
}
```

#### Simple select object:

```js
{
  type: "vueMultiSelect",    
  model: "library",
  label: "Libraries",
  placeholder: "Select your favorite library",
  required: true, 
  validator: validators.required,
  selectOptions: {
    multiple: false,
    key: "name",
    label: "name",
    searchable: false,
    closeOnSelect: false,
    allowEmpty:false
  },
  values: [
    {
      "name": "Vue.js",
      "language": "JavaScript"
    },
    {
      "name": "Rails",
      "language": "Ruby"
    },
    {
      "name": "Sinatra",
      "language": "Ruby"
    }
  ]
}
```

#### Select with search:

```js
{
  type: "vueMultiSelect",    
  model: "library",
  label: "Libraries",
  placeholder: "Select your favorite library",
  required: true,  
  validator: validators.required,
  selectOptions: {
    multiple: false,
    key: "name",
    label: "name",
    searchable: true,
    customLabel: function({ name, language }) {
      return `${name} — [${language}]`
    }
  },
  values: [
    {
      "name": "Vue.js",
      "language": "JavaScript"
    },
    {
      "name": "Rails",
      "language": "Ruby"
    },
    {
      "name": "Sinatra",
      "language": "Ruby"
    }
  ]
}
```

#### Multiselect with search:

```js
{
  type: "vueMultiSelect",    
  model: "library",
  label: "Libraries",
  placeholder: "Select your favorite library",
  required: true, 
  validator: validators.required,
  selectOptions: {
    multiple: true,
    key: "name",
    label: "name",
    searchable: true,
    clearOnSelect: false,
    closeOnSelect: false,
    limit:2 // limits the visible results to 2
  },
  values: [
    {
      "name": "Vue.js",
      "language": "JavaScript"
    },
    {
      "name": "Rails",
      "language": "Ruby"
    },
    {
      "name": "Sinatra",
      "language": "Ruby"
    }
  ]
}
```

#### Asynchronous select:

```js
{
  type: "vueMultiSelect",    
  model: "countries",
  label: "Countries ",
  placeholder: "Type to search",
  required: true,  
  validator: validators.required,
  selectOptions: {
    multiple: true,
    key: "code",
    label: "name",
    searchable: true,
    localSearch: false,
    clearOnSelect: false,
    closeOnSelect: false,    
    onSearch: function(searchQuery, id, options) {
      if (searchQuery.length === 0) {
        this.countries = []
      } else {
        this.isLoading = true
        setTimeout(() => {
          this.countries = countries.filter(function(element, index, array) {
            return element.name.toLowerCase().includes(searchQuery.toLowerCase())
          })
          this.isLoading = false
        }, 1000)
      }
    },
  },
  onChanged: function(model, newVal, oldVal, field) {
    model.selectedCountries = newVal    
  },    
  values: [
    {
      "name": "Vue.js",
      "language": "JavaScript"
    },
    {
      "name": "Rails",
      "language": "Ruby"
    },
    {
      "name": "Sinatra",
      "language": "Ruby"
    }
  ]
}
```

#### Tagging:

```js
{
  type: "vueMultiSelect",    
  model: "library",
  label: "Libraries",
  placeholder: "Type to search or add tag",
  required: true,  
  validator: validators.required,
  selectOptions: {
    multiple: true,
    key: "code",
    label: "name",
    searchable: true,
    taggable: true,
    tagPlaceholder: "Add this as new tag",
    onNewTag: function(newTag, id, options, value){
      const tag = {
        name: newTag,
        // Just for example needs as we use Array of Objects that should have other properties filled.
        // For primitive values you can simply push the tag into options and selected arrays.
        code: newTag.substring(0, 2) + Math.floor((Math.random() * 10000000))
      }
      options.push(tag);
      value.push(tag);
    }
  },
  onChanged: function(model, newVal, oldVal, field) {    
    console.log('@tag: ', newVal);
  },    
  values: [
    {
      "name": "Javascript",
      "code": "js"
    },
    {
      "name": "Monterail",
      "code": "pl"
    },
    {
      "name": "Open Source",
      "code": "os"
    },
    {
      "name": "Vue.js",
      "code": "vu"
    }
  ]
}
```

## CSS

You have to include the vue-multiselect CSS somewhere. It can be added as a static asset to your application, or inside a component. See [here](http://monterail.github.io/vue-multiselect/) for details.

For example, to include in a component:

```html
<template>
  <!-- template here -->
</template>
<script>
  // Script here
</script>

<!-- include the vue-multiselect CSS -->
<style src="vue-multiselect/dist/vue-multiselect.min.css"></style>

<style>
  /* your styles here */
</style>
```