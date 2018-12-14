# Creating Custom Validators

Custom validators are just functions which accept the following parameters:

| parameter | type |  meaning |
| :------------- | :------------- |:------------- |
| `value` | String | The current value of the field being validated. |
| `field` | schema.field object | The schema for the field being validated. |
| `model` | model object | The relevant model. |


> Note: If you don't need all the parameters, your function doesn't have to use them.

## Synchronous Validators


This is a simple example of a synchronous US Zip Code validator function, that just takes the current value:

```js
zipcode(value) {
  let re = /(^\d{5}$)|(^\d{5}-\d{4}$)/;

  if (!re.test(value)) {
    return ["Invalid Zip Code."];
  } else {
    return []
  }
};
```

> Note: There's a [built-in regular expression validator](built-in-validators.md#regexp) that you could also use for validating zip codes.

## Asynchronous Validators

Asynchronous validators are also supported. This allows you to perform validations that might take a long time: a complex calculation, or validation via AJAX, for example.

These are very similar to synchronous validators, but they should return a promise, which resolves to an array of errors:

```js
let customAsyncValidator = function(value) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      if (value)
      resolve();
      else
      resolve([ "Invalid value from async validator" ]);
    }, 1000);
  });
};
```
