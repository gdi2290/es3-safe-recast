# es3-safe-recast

Recasts all [ECMAScript 3][1] reserved words to their safe alternatives.

## Before

```js
ajax('/asdf/1').catch(function(reason) {

}).finally(function() {

});
```

## After

```js
ajax('/asdf/1')['catch'](function(reason) {

})['finally'](function() {

});
```

## Before

```js
object = {
  catch:   function() {},
  finally: function() {},
  default: function() {}
};
```

## After

```js
object = {
  'catch':   function() {},
  'finally': function() {},
  'default': function() {}
};
```

[1]: http://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-262,%203rd%20edition,%20December%201999.pdf
