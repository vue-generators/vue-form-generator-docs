# Groups

A group in the schema groups related fields. Groups are currently output as a `<fieldset>` element, with a `<legend>`. For example, this schema:

```js
{
    groups: [
        {
            legend: "User Details",
            fields: [
                {
                    type: "input",
                    inputType: "text",
                    label: "Name",
                    model: "name"
                },
                {
                    type: "input",
                    inputType: "number",
                    id: "current_age",
                    label: "Age",
                    model: "age"
                }
            ]
        }
    ]
}
```

would produce (simplified) HTML output something like this:

```html
<fieldset>
    <legend>User Details</legend>

    <label>Name</label>
    <input type="text" />

    <label>Age</label>
    <input type="number" />
</fieldset>
```

## Tags

### Default

You can change the default `fieldset` tag by passing the `tag` property to the `<vue-form-generator />` component in your markup.

```html
<vue-form-generator tag="div" :model="model" :schema="schema" :options="options"></vue-form-generator>
```

### Per group

You can also change the `fieldset` tag per group by adding a tag to the group definition:

```js
{
    groups: [
        {
            tag: "section",
            ...
        }
    ]
}
```

## Subgroups

You can create a subgroup by adding a `groups` definition inside of a top-level `groups` definition. This is useful for grouping sections of large forms.

```js
{
    groups: [
        {
            legend: "User Details",
            fields: [
                {
                    type: "input",
                    inputType: "text",
                    label: "Name",
                    model: "name"
                },
                {
                    type: "input",
                    inputType: "number",
                    id: "current_age",
                    label: "Age",
                    model: "age"
                }
            ],
            groups: [
                {
                    legend: "Location",
                    fields: [
                        {
                            type: "input",
                            inputType: "text",
                            label: "City"
                        },
                        {
                            type: "input",
                            inputType: "text",
                            label: "State"
                        }
                    ]
                }
            ]
        }
    ]
}
```

would produce (simplified) HTML output something like this:

```html
<fieldset>
    <legend>User Details</legend>

    <label>Name</label>
    <input type="text">

    <label>Age</label>
    <input type="number">

    <fieldset>
        <legend>Location</legend>
            <label>City</label>
            <input type="text">

            <label>State</label>
            <input type="text">
    </fieldset>
</fieldset>
```

### Bootstrap Vue Example

Using custom tags, subgroups, and the `legendAttr` option, forms can be grouped using custom Vue components. The `legendAttr` option will render the legend text into the attribute you specify. The below example uses bootstrap-vue to render subgroups in tabs:

```js
{
    groups: [
        {
            tag: "b-tabs",
            legend: "Additional Info",
            groups: [
                {
                    tag: "b-tab",
                    legend: "Location",
                    legendAttr: "title",
                    fields: [
                        {
                            type: "input",
                            inputType: "text",
                            label: "City"
                        },
                        {
                            type: "input",
                            inputType: "text",
                            label: "State"
                        }
                    ]
                },
                {
                    tag: "b-tab",
                    legend: "Demographics",
                    legendAttr: "title",
                    fields: [
                        {
                            type: "input",
                            inputType: "number",
                            label: "Age",
                            model: "age"
                        }
                    ]
                }
            ]
        }
    ]
}
```
