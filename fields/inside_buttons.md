# Field buttons

You can also add buttons to fields.

![Buttons screenshot](../assets/vfg-buttons.png)

## Properties

| Property | Default | Accepted values | Description |
| --- | --- | --- | --- |
| classes | _none_ | `String` | CSS classes for the button |
| label | _none_ | `String` | Caption of the button |
| onclick | _none_ | `Function(model, field)` | Triggered when click on the button |

## Example

The below example uses two buttons to read the location of the user and clear the location value.

```js
{
  type: "input",
  inputType: "text",
  label: "Location",
  model: "address.geo",
  buttons: [
      {
          classes: "btn-location",
          label: "Current location",
          onclick: function(model) {
              if (navigator.geolocation) {
                  navigator.geolocation.getCurrentPosition(function(pos) {
                    model.address.geo = {
                      lat: pos.coords.latitude.toFixed(5),
                      lng: pos.coords.longitude.toFixed(5)
                    };
                  });
              } else {
                  alert("Geolocation is not supported by this browser.");
              }
          }
      },
      {
          classes: "btn-clear",
          label: "Clear",
          onclick: function(model, field) {
              model.address.geo = {
                  lat: 0,
                  lng: 0
              };
          }
      }
  ]
}
```



