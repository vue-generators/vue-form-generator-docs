# pikaday field

A refreshing JavaScript Datepicker — lightweight, no dependencies, modular CSS.

> Please note, this field depend on the following library:
- [Pikaday](https://github.com/dbushell/Pikaday)
- [Moment.js](http://momentjs.com/) (see [issue #59](https://github.com/icebob/vue-form-generator/issues/59))

## Special properties of field

Property 		| Default | Accepted values | Description
--------------- | ------- | --------------- | -----------
`autocomplete` | _none_   | [see doc](https://html.spec.whatwg.org/multipage/forms.html#autofill)        | Indicates whether the value of the control can be automatically completed by the browser.
`placeholder` | _none_   | `String` 	   | Placeholder text for input field
`pikadayOptions`   | `{}`    | `Object`        | Settings of component. See details below.
`readonly`    | `false`  | `Boolean` 	   | If true, the input field is read only

### `pikadayOptions`

For more details, see the official [Pikaday documentation](https://github.com/dbushell/Pikaday#configuration).

Property 	                    | Default           | Accepted values       | Description
----------------------------    | ----------------- | --------------------- | -----------
`bound`                        | `true`            | `Boolean`             | Automatically show/hide the datepicker on `field` focus (default `true` if `field` is set)
`position`                      | `"bottom left"`   | `String`              | Preferred position of the datepicker relative to the form field, e.g.: `top right`, `bottom right` **Note:** automatic adjustment may occur to avoid datepicker from being displayed outside the viewport, see [positions example](http://dbushell.github.com/Pikaday/examples/positions.html)
`reposition`                    | `true`            | `Boolean`             | Can be set to false to not reposition datepicker within the viewport, forcing it to take the configured `position`
`container`                     | `undefined`       | DOM node              | DOM node to render calendar into, see [container example](http://dbushell.github.com/Pikaday/examples/container.html)
`format`                        | _null_            | `Function`            | The default output format for `.toString()` and `field` value (requires [Moment.js](moment) for custom formatting)
`formatStrict`                  | `false`           | `Boolean`             | The default flag for moment's strict date parsing (requires [Moment.js](moment) for custom formatting)
`defaultDate `                    | _null_            | `Date`                | The initial date to view when first opened
`setDefaultDate`                 | ?                 | `Boolean`             | make the `defaultDate` the initial selected value
`firstDay`                       | `1`               | `Number`              | First day of the week (0: Sunday, 1: Monday, etc)
`minDate`                       | _null_            | `Date`                | the minimum/earliest date that can be selected (this should be a native Date object - e.g. `new Date()` or `moment().toDate()`)
`maxDate`                       | _null_            | `Date`                | the maximum/latest date that can be selected (this should be a native Date object - e.g. `new Date()` or `moment().toDate()`)
`disableWeekends`               | `false`           | `Boolean`             | Disallow selection of Saturdays or Sundays
`disableDayFn`                  | _null_            | `Function => Boolean` | Callback function that gets passed a Date object for each day in view. Should return true to disable selection of that day.
`yearRange`                     | _null_            | `Number` or `Array`   | Number of years either side (e.g. `10`) or array of upper/lower range (e.g. `[1900,2015]`)
`showWeekNumber`                | `false`           | `Boolean`             | Show the ISO week number at the head of the row
`isRTL`                         | `false`           | `Boolean`             | Reverse the calendar for right-to-left languages
`i18n`                          | `{}`              | `Object`              | Language defaults for month and weekday names (see internationalization below)
`yearSuffix`                    | `""`              | `String`              | Additional text to append to the year in the title
`showMonthAfterYear`            | `false`           | `Boolean`             | Render the month after year in the title
`showDaysInNextAndPreviousMonths`| `false`           | `Boolean`             | Render days of the calendar grid that fall in the next or previous months to the current month instead of rendering an empty table cell
`numberOfMonths`                | `1`               | `Number`              | Number of visible calendars
`mainCalendar`                  | `"left"`          | `"left"` or `"right"` | When `numberOfMonths` is used, this will help you to choose where the main calendar will be. Only used for the first display or when a selected date is not already visible
`theme`                         | _null_            | `String`              | Define a classname that can be used as a hook for styling different themes, see [theme example](http://dbushell.github.com/Pikaday/examples/theme.html)
####Internationalization
The default `i18n` configuration format looks like this:
```js
i18n: {
	previousMonth : "Previous Month",
	nextMonth     : "Next Month",
	months        : ["January","February","March","April","May","June","July","August","September","October","November","December"],
	weekdays      : ["Sunday","Monday","Tuesday","Wednesday","Thursday","Friday","Saturday"],
	weekdaysShort : ["Sun","Mon","Tue","Wed","Thu","Fri","Sat"]
}
```


## Usage
#### Simple datepicker:
```js
{
  type: "pikaday",
  label: "Simple datepicker",
  placeholder: "User's birth of date",
  model: "date",
  validator: validators.date,  
  pikadayOptions: {
    position: "top left"
  }
}
```