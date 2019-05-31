# 128 - CommonJS, AMD, UMD

## Common JS
```js
var module1 = requrire('module1') // .fight
var module2 = requrire('module2') // Imported function

function fight() {}

module.exports {
  fight
}
```

- People using commonJS are available to share theirs programs.
- Module are loaded asynchronously, that mean JS have only one callstack, if module take a long time to load, 
  we will waiting there, that not ideal for browser. => they can slowdown pages.

Solutions ?
ex: Browserify => understand dependencies modules, create them and add them to one sinle file called bundle.js.
  it's called module bundler. => No global name space pollution and order doesn't matter.

## AMD: Asynchronous Model Definition.
```js
define(['module1', 'module2'],
function (module1Import, module2Import) {
  var module1 = module1Import // .fight
  var module2 = module2Import

  function dance() {}

  return {
    dance
  }
})
``` 
Was design specifically for browser, => load scripts asynchronously.
But people come with differents because of no standards.
Build with require.js


## Universal Module Definition: 
Just simple if / else statements to identify module system or module style that the current environment support
and then just load the commonJS or AMD version of the code.

# 129 - ES6 Modules

Just add export keyword
```js
const harry = ""
const voldemort = ""

export function fight() {}
```

1. Make available on browser
```html
<script type="module">
import { a } from 'm';
</script>
or
<script type="module" src="file.js"></script>
```
2. use live-server