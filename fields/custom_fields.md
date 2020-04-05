# Custom fields

If you are not satisfied with the available field, you can create your own custom fields.
There is only a few steps:

1. These custom fields are like any custom components except you need to use `VueFormGenerator.abstractField` as a mixin:

   ```html
   <!-- fieldAwesome.vue -->
   <template>
       <input
           class="form-control"
           type="text"
           v-model="value"
           :disabled="disabled"
           :maxlength="schema.max"
           :placeholder="schema.placeholder"
           :readonly="schema.readonly" >
   </template>

   <script>
      import { abstractField } from "vue-form-generator";

      export default {
            mixins: [ abstractField ]
      };
   </script>
   ```

2. Register the new field as a global components. The registered name must validate this RegExp: `(field)[A-Z][A-z]*`.

   ```js
    /* main.js */
    import Vue from "vue";
    import VueFormGenerator from "vue-form-generator";

    // Register my awesome field
    import fieldAwesome from "./fieldAwesome.vue";
    Vue.component("fieldAwesome", fieldAwesome);

    Vue.use(VueFormGenerator);
   ```

3. Last step is to use it in your schema

   ```js
   var schema: {
      fields: [{
          type: "awesome",
          label: "Awesome (custom field)",
          model: "userName"
      }]
   };
   ```

If you decide to release your custom field into the wild, please [open a new issue](https://github.com/vue-generators/vue-form-generator/issues) so we can add you to a list on the README.
Please try to use this naming convention for your custom field : `vfg-field-*`
Exemple :

* `vfg-field-myfield`
* `vfg-field-calendar`
* `vfg-field-awesome-dropdown`

This way, it will be easier for everyone to find it. Thank you !

