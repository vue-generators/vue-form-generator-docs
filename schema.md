# Schema

The schema contains the [fields](fields/README.md) of the form, optionally in groups.

## Examples

### Simple form without groups

This simple form will have a text input for Name and a numeric input for Age.

```js
{ 
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
```

### Simple form with groups

This form will have two sections:

  - A "User Details" section, with a text input for username and an email input
  - A "Preferences" section, with a select input for color and a numeric input for timeout

Sections are currently output as `<fieldset>` elements, with a `<legend>`.

```js
{ 
    groups: [
        {
            legend: "User Details",
            fields: [
                {
                    type: "input",
                    inputType: "text",
                    label: "Username",
                    model: "username"
                },
                {
                    type: "input",
                    inputType: "email",
                    id: "email",
                    label: "Email Address",
                    model: "email"
                }
            ]
        },
        {
            legend: "Preferences",
            fields: [
                {
                    type: "select",
                    label: "Color",
                    model: "color",
                    values: [
                        "Red",
                        "Green",
                        "Blue"
                    ]
                },
                {
                    type: "input",
                    inputType: "number",
                    id: "timeout",
                    label: "Timeout in Seconds",
                    model: "timeout"
                }
            ]
        }
    ]
}
```

It is also possible to have a schema with some fields grouped and some ungrouped:

```js
{ 
    fields: [
        {
            type: "input",
            inputType: "text",
            label: "Name",
            model: "name"
        }
    ],
    groups: [
        {
            legend: "User Details",
            fields: [
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
This form would have a text input for Name, followed by a fieldset for "User Details", containing a numeric input for Age.

> **Note**: any ungrouped fields will be output first, followed by any groups.


[Available field types](fields/README.md)

