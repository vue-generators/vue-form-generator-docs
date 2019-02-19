# Model
The model is a native JSON object. VueFormGenerator will modify this model if the values of the fields change. Model can be a multi-level object. In this case the `model` of field will be like this:

```js
model: "address.country"
```

## Example

```js
{
    "id": 1,
    "type": "personal",
    "name": "Rozella Hickle",
    "username": "Kelton.Dicki",
    "password": "adGlGG8hTq",
    "email": "Dessie_Metz37@gmail.com",
    "address": {
        "streetC": "343 O'Conner Stravenue Apt. 183",
        "city": "East Traceyfurt",
        "country": "Nepal",
        "zipcode": "17779",
        "geo": {
            "lat": "-21.0406",
            "lng": "86.5714"
        }
    },
    "phone": "031.053.8042 x33435",
    "website": "abraham.net",
    "dob": -196498331535,
    "time": "02:47:20",
    "age": 53,
    "rank": 7,
    "role": "user",
    "avatar": "https://s3.amazonaws.com/uifaces/faces/twitter/saulihirvi/128.jpg",
    "skills": [
        "ReactJS",
        "CSS3"
    ],
    "language": "it",
    "status": true,
    "created": 1461100485088
}
```

## Merge & multiple models

If you would like to edit more models, first you have to merge these objects to a work object. For this, there is a helper function: 

```js
VueFormGenerator.schema.mergeMultiObjectFields(schema, objs)
```

#### Parameters

- `schema`: schema object with fields. Merge only the `multi: true` fields
- `objs`: array of models

#### Return

Returns the merged JSON object like this:

```js
{
    "time": "02:47:20",
    "address": {},
    "status": true
}
```

The function only set those value of properties, where multiple mode is enabled `multi: true` in the fields and the values in every models are the **same** value.

## Create new empty model

You can create a new model with default values. For this use the `VueFormGenerator.schema.createDefaultObject` function. The first parameter can be a base object.

#### Example with a generated ID:

```js
let newModel = VueFormGenerator.schema.createDefaultObject(schema, { 
  id: getNextID(), 
  created: new Date().valueOf() 
});
```

Result:

```js
{
    "id": 6,
    "type": "personal",
    "created": 1462972235132,
    "status": true
}
```

> **Note**: `type` and `status` field have default values in the schema.
