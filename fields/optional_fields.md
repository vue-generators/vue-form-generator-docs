# Optional fields

These fields are availble in the full version of VueFormGenerator. Some of these also have external dependency.

* [`cleave`](cleave.md) - Format input text content when you are typing
* [`dateTimePicker`](datetime.md) - datetime picker with bootstrap-datetimepicker component
* [`googleAddress`](googleaddress.md) - Format input text content when you are typing
* [`image`](image.md) - Image select field \(URL or upload in base64 string\)
* [`masked`](masked.md) - Masked text input field with maskedinput component
* [`noUiSlider`](nouislider.md) - Lightweight JavaScript range slider
* [`pikaday`](pikaday.md) - A refreshing JavaScript Datepicker
* [`selectEx`](selectex.md) - select list with the bootstrap-select component
* [`slider`](slider.md) - pretty range slider with ion.rangeSlider component
* [`spectrum`](spectrum.md) - Color picker with "The No Hassle" Spectrum jQuery Colorpicker component
* [`staticMap`](staticmap.md) - Display a static map from Google Maps.
* [`switch`](switch.md) - Switch field \(toggle two values \(on/off, yes/no, active/inactive\)
* [`vueMultiSelect`](vuemultiselect.md) - Probably the most complete selecting solution for Vue.js

## External dependency

Depending on whether you want to use jQuery, we tried to make the same kind of functionnality available with or without it.  
Here, vanilla mean that a third party librairy is needed and that third party don't use or need jQuery.

| Field type | jQuery | Vanilla |
| --- | --- | --- |
| Address autocomplete | N/A | [googleAddress](googleaddress.md) |
| Color picker | [spectrum](spectrum.md) | N/A |
| Date picker | [datetime](datetime.md) | [pikaday](pikaday.md) |
| Masked Input | [masked](masked.md) | [cleave](cleave.md) |
| Multi Selection | [selectEx](selectex.md) | [vueMultiSelect](vuemultiselect.md) |
| Slider | [slider](slider.md) | [noUiSlider](nouislider.md) |



