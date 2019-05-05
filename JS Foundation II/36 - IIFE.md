# IIFE (Immediately Invoke function expression)

```js
// function like this
(function() {})(); <=> (function() {}()); // JS Design pattern.
```

**Place All library code inside of local scope to avoid namespace collision.**

```html
<script src="jquery.js"></script>
<script>
  var script1 = (function() {
    function a() {
      return 5;
    }

    return { a };
  })();
</script>
<script>
  var script2 = (function(jQ) {
    jQ("h1").click(function() {
      jQ("h1").hide();
    });
    return {
      jQ: "hi"
    };
  })(jquery);
</script>
<script></script>
<script></script>
<script>
  console.log(script1.a()); // => 5
  console.log(script2.jQ; // => "hi"
</script>
```
