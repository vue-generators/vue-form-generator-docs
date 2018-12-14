# noUiSlider field

Lightweight JavaScript range slider.

> Please note, this field depend on the following library:
- [noUiSlider](http://refreshless.com/nouislider/)

## Special properties of field

Property 		| Type 			| Description
--------------- | ------------- | -----------
`max`             | `Number`      | Largest value that the slider can select.
`min`             | `Number`      | Smallest value that the slider can select.
`sliderOptions`   | `Object` 		| Settings of slider component. See details below.
`values` 			| `Array` or `Function` 		| List of items. It can be an array with items, or a function, what is resulted an array. The item will be a `String` or an object with an `id` and a `name` properties.

### `sliderOptions`

For more details, see the official [noUiSlider documentation](http://refreshless.com/nouislider/slider-options/).

Property    | Default        | Accepted values                                     | Description
----------- | -------------- | --------------------------------------------------- | -----------
connect     | `"lower"`      | `"lower"`, `"upper"`, `Boolean`                     | The connect setting can be used to control the (green) bar between the handles, or the edges of the slider. Use `"lower"` to connect to the lower side, or `"upper"` to connect to the upper side. Setting `true` sets the bar between the handles.
margin      | _none_         | `Number`                                            | When using two handles, the minimum distance between the handles can be set using the margin option. The margin value is relative to the value set in 'range'. This option is only available on standard linear sliders.
limit       | _none_         | `Number`                                            | The limit option is the oposite of the margin option, limiting the maximum distance between two handles. As with the margin option, the limit option can only be used on linear sliders.
step        | _none_         | `Number`                                            | By default, the slider slides fluently. In order to make the handles jump between intervals, you can use this option. The step option is relative to the values provided to `range`.
orientation | `"horizontal"` | `"vertical"`, `"horizontal"`                        | The orientation setting can be used to set the slider to `"vertical"` or `"horizontal"`. **Set dimensions!** Vertical sliders don't assume a default height, so you'll need to set one. You can use any unit you want, including `%` or `px`.
direction   | `"ltr"`        | `"ltr"`, `"rtl"`                                    | By default the sliders are _top-to-bottom_ and _left-to-right_, but you can change this using the direction option, which decides where the upper side of the slider is.     
tooltips    | `false`        | `Boolean`, `formatter`, `Array[formatter or false]` | noUiSlider can provide a basic tooltip without using its events system. Set the `tooltips` option to `true` to enable. This option can also accept [formatting options](http://refreshless.com/nouislider/slider-read-write/#section-formatting) to format the tooltips content. In that case, pass an array with a formatter for each handle, `true` to use the default or `false` to display no tooltip.
animate     | `true`         | `Boolean`                                           | Set the animate option to `false` to prevent the slider from animating to a new value with when calling `.val()`. [More details](http://refreshless.com/nouislider/slider-options/#section-animate)
range       | _none_         | `Object`                 | Overide the `min` and `max` properties for more complex range behavior ([Non-linear sliders](http://refreshless.com/nouislider/slider-values/#section-non-linear)). [More details](http://refreshless.com/nouislider/slider-values/)
pips        | _none_         | `Object`                                            | This feature allows you to generate points along the slider. [More details](http://refreshless.com/nouislider/pips/)

## Usage
#### Simple slider:
```js
{
  type: "noUiSlider",
  label: "Volume level",
  model: "volume",
  min: 0,
  max: 100,
  required: true,
  sliderOptions: {
    connect: "lower",
  },
  validator: validators.required
}
```

#### Stepped slider with custom scale:
```js
{
  type: "noUiSlider",
  label: "Volume level",
  model: "volume",
  min: 0,
  max: 140,
  required: true,
  sliderOptions: {
    connect: "lower",
    step: 10,
    pips: {
      mode: 'steps',
      density: 5,
      filter: function( value, type ) {return value % 4 ? 2 : 1;},
      format: {
        to: function ( value ) {
          return value + 'dB';
        },
        from: function ( value ) {
          return value.replace('dB', '');
        }
      }
	}
  },
  validator: validators.required
}
```
#### Vertical reversed non-linear slider with scale:
```js
{
  type: "noUiSlider",
  label: "Vertical reversed non-linear slider with scale",
  model: "power",
  min: 0,
  sliderOptions: {
    connect: "lower",
    orientation: 'vertical',
	direction: 'rtl',
    range:{
      'min': [     0 ],
      '10%': [   500,  500 ],
      '50%': [  4000, 1000 ],
      'max': [ 10000 ]
    },
    pips: {
		mode: 'range',
		density: 3
	}
  }  
}
```