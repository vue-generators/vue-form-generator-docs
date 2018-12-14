# Installation

### NPM

You can install it via [NPM](http://npmjs.org/).

```
$ npm install vue-form-generator
```

### Manual

Download zip package and unpack and add the `vfg.css` and `vfg.js` file to your project from dist folder.

```
https://github.com/icebob/vue-form-generator/archive/master.zip
```

### Core vs Full version

VueFormGenerator come in two version : core and full.  
Core is a more minimal version with only half the fields.  
Full is core + other fields.

* Full bundle: 75 kB (gzipped: 19 kB)
* Core bundle: 39 kB (gzipped: 11 kB)

If you don't know what to choose, don't worry, the full is the default version.  
If you want the slim down version, here is the changes:

```js
// the "core" way
<script>
  import VueFormGenerator from "vue-form-generator/dist/vfg-core.js";
  import "vue-form-generator/dist/vfg-core.css";
</script>
```

### Dependencies

VueFormGenerator use [fecha](https://github.com/taylorhakes/fecha) and [lodash](https://lodash.com/) internally.

While core fields don't need external dependencies, optional fields may need other libraries.  
These dependency fall in two camp: jQuery or Vanilla. You can find almost the same functionality in both flavor.  
That way, it's your choice to depend on jQuery or not.

| Field type | jQuery | Vanilla |
| --- | --- | --- |
| Address autocomplete | N/A | [googleAddress](googleaddress.md) |
| Color picker | [spectrum](spectrum.md) | N/A |
| Date picker | [datetime](datetime.md) | [pikaday](pikaday.md) |
| Masked Input | [masked](masked.md) | [cleave](cleave.md) |
| Multi Selection | [selectEx](selectex.md) | [vueMultiSelect](vuemultiselect.md) |
| Slider | [slider](slider.md) | [noUiSlider](nouislider.md) |

You can find details about dependencies in each field page.

