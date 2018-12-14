# switch field
This is a switch/toogle input field for any values. It can toggle true/false, yes/no, on/off values.

## Special properties of field
Property      | Default  | Accepted values            | Description
------------- | -------- | -------------------------- | ----------- 
`textOn`	  | _none_   | `String` 	              | Visible label if the switch state is on
`textOff`  	  | _none_   | `String` 	              | Visible label if the switch state is off
`valueOn`     | _none_   | any primitives or `Object` | Value if the switch state is on
`valueOff`	  | _none_   | any primitives or `Object` | Value if the switch state is off


## Usage
Simple example with active/inactive labels
```js
{
    type: "switch",
    label: "Status (switch field)",
    model: "status",
    textOn: "Active",
    textOff: "Inactive"
}
```

Example with male/female model values
```js
{
    type: "switch",
    label: "Sex",
    model: "sex",
    textOn: "Female",
    textOff: "Male",
    valueOn: "female",
    valueOff: "male"
}
```


