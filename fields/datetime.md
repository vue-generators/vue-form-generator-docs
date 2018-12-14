# dateTimePicker field
This is a dateTime picker field for date/time/datetime values. 

> Please note, this field depend on the following library:
- [jQuery](http://www.jquery.com)
- [BootStrap](http://getbootstrap.com/)
- [bootstrap-datetimepicker](https://github.com/Eonasdan/bootstrap-datetimepicker)

## Special properties of field

Property      | Default  | Accepted values    | Description
------------- | -------- | ------------------ | ----------- 
`autocomplete` | _none_   | [see doc](https://html.spec.whatwg.org/multipage/forms.html#autofill)        | Indicates whether the value of the control can be automatically completed by the browser.
`dateTimePickerOptions` | `{}` | `Object` 		| Settings to dateTimePicker. [Read more info from options](http://eonasdan.github.io/bootstrap-datetimepicker/Options/)
`format`	  | `null`   | `String` or `null` | Format of the value of model. If `null`, use the Unix timestamp format (eg: 1462913010557). If a `String`, format the Date with `moment` (eg: `format: "YYYY.MM.DD"`).
`max` 		  | _none_   | `Number` 	      | Max value (need to use `validators.number`)
`min` 		  | _none_   | `Number` 	      | Min value (need to use `validators.number`)
`placeholder` | _none_   | `String` 	      | Placeholder text for input field
`readonly`    | `false`  | `Boolean` 	      | If true, the input field is read only

### dateTimePickerOptions
@TODO
## Usage
#### Field for date-of-birth with min, max limits and age calculator.
```js
{
    type: "dateTimePicker",
    label: "DOB",
    model: "dob",
    required: true,
    placeholder: "User's birth of date",
    min: moment("1900-01-01").toDate(),
    max: moment("2016-01-01").toDate(),
    validator: validators.date,
    
    dateTimePickerOptions: {
        format: "YYYY-MM-DD"
    },			
    
    onChanged: function(model, newVal, oldVal, field) {
        model.age = moment().year() - moment(newVal).year();
    }
}
```
#### Date and time picker
```js
    {
        type: "dateTimePicker",
        label: "DT",
        model: "dt",
        dateTimePickerOptions: {
            format: "YYYY-MM-DD HH:mm:ss"
        }
    }
```
#### Time picker
```js
    {
        type: "dateTimePicker",
        label: "Start time",
        model: "startTime",
        format: "HH:mm:ss",
        dateTimePickerOptions: {
            format: "HH:mm:ss"
        }
    }
```
The value will be formatted as `"15:28:43"`.