# Installation

### NPM

You can install it via [NPM](http://npmjs.org/).

```
$ npm install vue-form-generator
```

### Manual

Download zip package, unpack and add the `vfg.css` and `vfg.js` file to your project from `/dist` folder.

```
https://github.com/vue-generators/vue-form-generator/releases/latest
```

### Core vs Full version

VueFormGenerator comes in two versions: core and full.  
Core is a minimal version with only half the fields.  
Full is core + other fields.

* Full bundle: 169 kB (gzipped: 50 kB)
* Core bundle: 143 kB (gzipped: 45 kB)

If you don't know what to choose, don't worry, full is the default version.  
If you want the slimmed down version, here are the changes:

```js
// the "core" way
<script>
  import VueFormGenerator from "vue-form-generator/dist/vfg-core.js";
  import "vue-form-generator/dist/vfg-core.css";
</script>
```

### Dependencies

VueFormGenerator uses [fecha](https://github.com/taylorhakes/fecha) and [lodash](https://lodash.com/) internally.

While core fields don't need external dependencies, optional fields in the full package may need additional libraries.  
These dependencies fall into two camps: jQuery or Vanilla. You can find almost the same functionality in both flavors.
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

