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