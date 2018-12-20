# cleave field

Format input text content when you are typing.

> Please note, this field depend on the following library:
- [cleave.js](https://nosir.github.io/cleave.js/) ([github](https://github.com/nosir/cleave.js))
- [cleave.js phone lib (optional)](https://github.com/nosir/cleave.js/blob/master/doc/phone-lib-addon.md)

## Special properties of field

Property 		| Default | Accepted values | Description
--------------- | ------- | --------------- | -----------
`autocomplete` | _none_   | [see doc](https://html.spec.whatwg.org/multipage/forms.html#autofill)        | Indicates whether the value of the control can be automatically completed by the browser.
`cleaveOptions`   | `{}`    | `Object`        | Settings to select component. See details below.
`placeholder` | _none_   | `String` 	   | Placeholder text for input field
`readonly`    | `false`  | `Boolean` 	   | If true, the input field is read only

### `cleaveOptions`

For more details, see the official [cleave.js documentation](https://github.com/nosir/cleave.js/blob/master/doc/options.md).

Property 	                 | Default           | Accepted values 	 | Description
---------------------------- | ----------------- | ----------------- | -----------
`creditCard`                   | `false`           | `Boolean`         | Enable to trigger credit card shortcut mode. It detects credit card type dynamically and automatically by checking card IIN.
`onCreditCardTypeChanged`      | _none_            | `Function`        | A callback triggered after credit card type changes. The unique `String` argument type is the type of the detected credit, which can be: `amex`,`mastercard`,`visa`,`diners`,`discover`,`jcb`,`dankort`,`instapayment`,`uatp`
`phone`                        | `false`           | `Boolean`         | Enable to trigger phone shortcut mode. This phone mode has to be used together with `phoneRegionCode` below.
`phoneRegionCode`              | _none_            | `String`          | Indicates the country region code for phone number formatting. You can find your country code in [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Officially_assigned_code_elements) list.
`date`                         | `false`           | `Boolean`         | Indicates if this is a date input field. Enable to trigger date shortcut mode.
`datePattern`                  | `['d', 'm', 'Y']` | `Array`           | Indicates the date pattern. Since it's an input field, leading 0 before date and month is required. To indicate what patterns it should apply, you can use: 'Y', 'y', 'm' and 'd'.
`numeral`                      | `false`           | `Boolean`         | Indicates if this is a numeral input field. Enable to trigger numeral shortcut mode.
`numeralThousandsGroupStyle`   | `thousand`        | `"thousand"`, `"lakh"`, `"wan"` | Indicates the thousands separator grouping style.
`numeralDecimalScale`          | `2`               | `Integer`         | Indicates the numeral decimal scale.
`numeralDecimalMark`           | `.`               | `String`          | Indicates the numeral decimal mark. Decimal mark can be different in handwriting, and for delimiter as well.
`blocks`                       | `[]`              | `Array`           |  indicates the groups to format the input value. It will insert delimiters in between these groups. This option is ignored by `creditCard`, `phone`, `date` and `numeral` shortcuts mode. When delimiters array is defined, single delimiter option is ignored.
`delimiter`                    | a space or `/` or `,` depending on context | `String` | Indicates the delimiter to use in formatting.
`delimiters`                   | `[]`              | `Array`           | Indicates the multiple delimiters to use in formatting. This option is ignored by `creditCard`, `phone`, `date` and `numeral` shortcuts mode. When delimiters array is defined, single delimiter option is ignored.
`prefix`                       | `null`            | `String`          | Indicates the prepend string. It can't be removed or changed in the input field.
`numericOnly`                  | `false`           | `Boolean`         | Indicates if it only allows numeric letters (0-9). Ignored by creditCard and date shortcuts mode, the value will always be true.
`uppercase`                    | `false`           | `Boolean`         | Indicates if it converts value to uppercase letters.
`lowercase`                    | `false`           | `Boolean`         | Indicates if it converts value to lowercase letters.


## Usage
#### Credit card number formatting:
```js
{
  type: "cleave",
  label: "Credit card number formatting",
  model: "credit",    
  cleaveOptions: {    
    creditCard: true,
    onCreditCardTypeChanged: function(type) {
      console.log("onCreditCardTypeChanged", type);	
    }
  }
}
```

#### Phone number formatting:
```js
{
  type: "cleave",
  label: "Phone number formatting",
  model: "phone",    
  cleaveOptions: {		
    phone: true,
    phoneRegionCode: 'FR',
  }
}
```
#### Date formatting:
```js
{
  type: "cleave",
  label: "Date formatting",
  model: "date",    
  cleaveOptions: {
    date: true,
    datePattern: ['d', 'm', 'Y'],
  }
}
```
#### Numeral formatting:
```js
{
  type: "cleave",
  label: "Numeral formatting",
  model: "number",    
  cleaveOptions: {
    numeral: true,
    numeralThousandsGroupStyle: 'thousand',
    numeralDecimalScale: 2,
    numeralDecimalMark: '.',
  }
}
```
#### Custom formatting:
```js
{
  type: "cleave",
  label: "Custom formatting",
  model: "special",    
  cleaveOptions: {
    blocks: [0, 2, 0, 3, 4],
    delimiter: ' ',
    delimiters: ['(', ')', ' ', '-', '-'],    
    numericOnly: true,
    uppercase: false,
    lowercase: false
  }
}
```
