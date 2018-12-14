# rangeSlider field

This is a range slider input field.

> Please note, this field depend on the following library:
>
> * [jQuery](http://www.jquery.com)
> * [ion.rangeSlider](https://github.com/IonDen/ion.rangeSlider)
> * ion.rangeSlider.css
> * ion.rangeSlider.skinHTML5.css

## Special properties of field

| Property | Default | Accepted values | Description |
| --- | --- | --- | --- |
| `autocomplete` | _none_ | [see doc](https://html.spec.whatwg.org/multipage/forms.html#autofill) | Indicates whether the value of the control can be automatically completed by the browser. |
| `max` | 100 | `Number` | Max value \(need to use `validators.number`\) |
| `min` | 10 | `Number` | Min value \(need to use `validators.number`\) |
| `placeholder` | _none_ | `String` | Placeholder text for input field |
| `readonly` | `false` | `Boolean` | If true, the input field is read only |
| `rangeSliderOptions` | `{}` | `Object` | Settings to slider. See details below. |
| `step` | 1 | `Number` | Set sliders step. Always &gt; 0. Could be fractional. |

### `rangeSliderOptions`

For more details, see the official  [rangeSlider documentation](http://ionden.com/a/plugins/ion.rangeSlider/demo.html).

| Property | Default | Accepted values | Description |
| --- | --- | --- | --- |
| `type` | "single" | `String` | Choose slider type, could be single - for one handle, or double for two handles |
| `from` | min | `Number` | Set start position for left handle \(or for single handle\) |
| `to` | max | `Number` | Set start position for right handle |
| `step` | 1 | `Number` | Set sliders step. Always &gt; 0. Could be fractional. |
| `min_interval` | _none_ | `Number` | Set minimum diapason between sliders. Only in "double" type |
| `max_interval` | _none_ | `Number` | Set maximum diapason between sliders. Only in "double" type |
| `drag_interval` | false | `Boolean` | Allow user to drag whole range. Only in "double" type \(beta\) |
| `from_fixed` | false | `Boolean` | Fix position of left \(or single\) handle. |
| `from_min` | min | `Number` | Set minimum limit for left handle. |
| `from_max` | max | `Number` | Set the maximum limit for left handle |
| `from_shadow` | false | `Boolean` | Highlight the limits for left handle |
| `to_fixed` | false | `Boolean` | Fix position of right handle. |
| `to_min` | min | `Number` | Set the minimum limit for right handle |
| `to_max` | max | `Number` | Set the maximum limit for right handle |
| `to_shadow` | false | `Boolean` | Highlight the limits for right handle |
| `prettify_enabled` | true | `Boolean` | Improve readability of long numbers. 10000000 → 10 000 000 |
| `prettify_separator` | " " | `String` | Set up your own separator for long numbers. 10 000, 10.000, 10-000, etc. |
| `prettify` | `null` | `Function` | Set up your own prettify function. Can be anything. For example, you can set up unix time as slider values and than transform them to cool looking dates. |
| `force_edges` | false | `Boolean` | Slider will be always inside it's container. |
| `keyboard` | false | `Boolean` | Activates keyboard controls. Move left: ←, ↓, A, S. Move right: →, ↑, W, D. |
| `keyboard_step` | 5 | `Number` | Movement step, than controling from keyboard. In percents. |
| `grid` | false | `Boolean` | Enables grid of values. |
| `grid_margin` | true | `Boolean` | Set left and right grid borders. |
| `grid_num` | 4 | `Number` | Number of grid units. |
| `grid_snap` | false | `Boolean` | Snap grid to sliders step \(step param\). If activated, grid\_num will not be used. |
| `hide_min_max` | false | `Boolean` | Hides min and max labels |
| `hide_from_to` | false | `Boolean` | Hide from and to lables |
| `prefix` | _none_ | `String` | Set prefix for values. Will be set up right before the number: $100 |
| `postfix` | _none_ | `String` | Set postfix for values. Will be set up right after the number: 100k |
| `max_postfix` | _none_ | `String` | Special postfix, used only for maximum value. Will be showed after handle will reach maximum right position. For example 0 — 100+ |
| `decorate_both` | true | `Boolean` | Used for "double" type and only if prefix or postfix was set up. Determine how to decorate close values. For example: $10k — $100k or $10 — 100k |
| `values_separator` | " — " | `String` | Set your own separator for close values. Used for "double" type. Default: 10 — 100. Or you may set: 10 to 100, 10 + 100, 10 → 100 etc. |
| `input_values_separator` | " ; " | `String` | Separator for double values in input value property. |

## Usage

#### Simple slider with one value

```js
{
    type: "rangeSlider",
    label: "Rank",
    model: "rank",
    min: 1,
    max: 10,
    required: true,
    rangeSliderOptions: {
        grid: true
    },
    validator: validators.integer
}
```

In this example the value will be a `Number` like this:

```js
rank: 6
```

#### Double range slider

```js
{
    type: "rangeSlider",
    label: "Income",
    model: "income",
    min: 0,
    max: 100000,
    rangeSliderOptions: {
        type: "double",
        prefix: "$",
        step: 1000
    }
}
```

In this example the value will be an array of numbers:

```js
income: [5000, 9000]
```



