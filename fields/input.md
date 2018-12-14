# input

A single HTML field for all input type.

> **Note**: This field is not recommended for `button`, `file`, `image`, `radio`, `reset`, `search` and `submit` type.
>
> It is best to use other build in fields that provide more control and features.


## Special properties of field

Property   | Default  | Accepted values       | Description
---------- | -------- | --------------------- | -----------
inputType  | _none_   | String                | Type of input field

See "attributes compatibility" at the end of this page.

## Usage
#### Text field with 50 characters limit :
```js
{
    type: "input",
    inputType: "text",
    label: "Name",
    model: "name",
    maxlength: 50,
    required: true,
    placeholder: "User's full name",
    validator: validators.string
}
```
## Attributes compatibility
Since attributes depend on the `type` of `input`, here is a table showing the compatible attributes for each field type.  
[Source](https://www.w3.org/TR/2012/WD-html5-20121025/the-input-element.html)

|                | Hidden | Text, Search | URL, Telephone | E-mail | Password | Date and Time, Date, Month, Week, Time | Local Date and Time | Number | Range | Color | Checkbox, Radio Button | File Upload | Submit Button | Image Button | Reset Button, Button |
|----------------|--------|--------------|----------------|--------|----------|----------------------------------------|---------------------|--------|-------|-------|------------------------|-------------|---------------|--------------|----------------------|
| id             | Yes    | Yes          | Yes            | Yes    | Yes      | Yes                                    | Yes                 | Yes    | Yes   | Yes   | Yes                    | Yes         | Yes           | Yes          | Yes                  |
| value          | Yes    | Yes          | Yes            | Yes    | Yes      | Yes                                    | Yes                 | Yes    | Yes   | Yes   | Yes                    | Yes         | Yes           | Yes          | Yes                  |
| accept         | ·      | ·            | ·              | ·      | ·        | ·                                      | ·                   | ·      | ·     | ·     | ·                      | Yes         | ·             | ·            | ·                    |
| alt            | ·      | ·            | ·              | ·      | ·        | ·                                      | ·                   | ·      | ·     | ·     | ·                      | ·           | ·             | Yes          | ·                    |
| autocomplete   | ·      | Yes          | Yes            | Yes    | Yes      | Yes                                    | Yes                 | Yes    | Yes   | Yes   | ·                      | ·           | ·             | ·            | ·                    |
| checked        | ·      | ·            | ·              | ·      | ·        | ·                                      | ·                   | ·      | ·     | ·     | Yes                    | ·           | ·             | ·            | ·                    |
| dirname        | ·      | Yes          | ·              | ·      | ·        | ·                                      | ·                   | ·      | ·     | ·     | ·                      | ·           | ·             | ·            | ·                    |
| formaction     | ·      | ·            | ·              | ·      | ·        | ·                                      | ·                   | ·      | ·     | ·     | ·                      | ·           | Yes           | Yes          | ·                    |
| formenctype    | ·      | ·            | ·              | ·      | ·        | ·                                      | ·                   | ·      | ·     | ·     | ·                      | ·           | Yes           | Yes          | ·                    |
| formmethod     | ·      | ·            | ·              | ·      | ·        | ·                                      | ·                   | ·      | ·     | ·     | ·                      | ·           | Yes           | Yes          | ·                    |
| formnovalidate | ·      | ·            | ·              | ·      | ·        | ·                                      | ·                   | ·      | ·     | ·     | ·                      | ·           | Yes           | Yes          | ·                    |
| formtarget     | ·      | ·            | ·              | ·      | ·        | ·                                      | ·                   | ·      | ·     | ·     | ·                      | ·           | Yes           | Yes          | ·                    |
| height         | ·      | ·            | ·              | ·      | ·        | ·                                      | ·                   | ·      | ·     | ·     | ·                      | ·           | ·             | Yes          | ·                    |
| list           | ·      | Yes          | Yes            | Yes    | ·        | Yes                                    | Yes                 | Yes    | Yes   | Yes   | ·                      | ·           | ·             | ·            | ·                    |
| max            | ·      | ·            | ·              | ·      | ·        | Yes                                    | Yes                 | Yes    | Yes   | ·     | ·                      | ·           | ·             | ·            | ·                    |
| maxlength      | ·      | Yes          | Yes            | Yes    | Yes      | ·                                      | ·                   | ·      | ·     | ·     | ·                      | ·           | ·             | ·            | ·                    |
| min            | ·      | ·            | ·              | ·      | ·        | Yes                                    | Yes                 | Yes    | Yes   | ·     | ·                      | ·           | ·             | ·            | ·                    |
| multiple       | ·      | ·            | ·              | Yes    | ·        | ·                                      | ·                   | ·      | ·     | ·     | ·                      | Yes         | ·             | ·            | ·                    |
| pattern        | ·      | Yes          | Yes            | Yes    | Yes      | ·                                      | ·                   | ·      | ·     | ·     | ·                      | ·           | ·             | ·            | ·                    |
| placeholder    | ·      | Yes          | Yes            | Yes    | Yes      | ·                                      | ·                   | Yes    | ·     | ·     | ·                      | ·           | ·             | ·            | ·                    |
| readonly       | ·      | Yes          | Yes            | Yes    | Yes      | Yes                                    | Yes                 | Yes    | ·     | ·     | ·                      | ·           | ·             | ·            | ·                    |
| required       | ·      | Yes          | Yes            | Yes    | Yes      | Yes                                    | Yes                 | Yes    | ·     | ·     | Yes                    | Yes         | ·             | ·            | ·                    |
| size           | ·      | Yes          | Yes            | Yes    | Yes      | ·                                      | ·                   | ·      | ·     | ·     | ·                      | ·           | ·             | ·            | ·                    |
| src            | ·      | ·            | ·              | ·      | ·        | ·                                      | ·                   | ·      | ·     | ·     | ·                      | ·           | ·             | Yes          | ·                    |
| step           | ·      | ·            | ·              | ·      | ·        | Yes                                    | Yes                 | Yes    | Yes   | ·     | ·                      | ·           | ·             | ·            | ·                    |
| width          | ·      | ·            | ·              | ·      | ·        | ·                                      | ·                   | ·      | ·     | ·     | ·                      | ·           | ·             | Yes          | ·                    |
