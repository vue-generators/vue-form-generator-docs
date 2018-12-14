# Label field
This is a text label for non-editable values (e.g. timestamp, creation time...etc)

## Special properties of field
There is no any special properties.

## Usage
```js
{
    type: "label",
    label: "Created",
    model: "created"
}
```
Or you can format the value with `moment`:
```js
{
    type: "label",
    label: "Created",
    model: "created",
    get: function(model) { 
      return model && model.created ? moment(model.created).format("LLL") : "-"; 
    }
}
```
