## _


### Underscore vs Lodash

While Underscore was first, Lodash is best

Huge list of differences at https://lodash.com/#features

Underscore has had some semantic versioning issues

When I say "Underscore" from now on, I mean Lodash


### Process a List - Bad Way

```javascript
var someArray = generateArray();
var processedArray = [];
for(var i = 0; i < someArray.length; i++) {
  processedArray.push(processArrayItem(someArray[i]));
}
```


### Process a List - Good Way

```javascript
var someArray = generateArray();
var processedArray = _.map(someArray, processArrayItem);
```


### Filter a List - Bad Way

```javascript
var someArray = generateArray();
var filteredArray = [];
for(var i = 0; i < someArray.length; i++) {
  var arrayItem = someArray[i];
  if(predicateFunction(arrayItem)){
    filteredArray.push(someArray[i]);
  }
}
```


### Filter a List - Good Way

```javascript
var someArray = generateArray();
var filteredArray = _.filter(someArray, predicateFunction);
```


### Currying - Explained

```javascript

// Non-Curried

var f = function(a,b,c) {}
var val = f(1); // Undefined

// Curried
var f = _.curry(function(a,b,c) {});
var val = f(1); // function(1,b,c);
```


### Color Function

```javascript
var getColorBetween = function(transitor, color1, color2){
  // average the 2 colors
  return (transitor * color1) + ((1-transitor) * color2);
};

var getMiddleColor = function(color1, color2){
  return (0.5, color1, color2);
}
```


### Currying - Applied

```javascript
var getColorBetween = _.curry(function(transitionFactor, color1, color2) {
    //..
});

var getMiddleColor = getColorBetween(0.5);
var getFallColor = getColorBetween(0.25);
var getSpringColor = getColorBetween(0.75);
```


### Plenty More

* Processing collections with `find`, `where`, `reduce`, etc.
* Function improvements with `bind`, `memoize`, `once`, `partial`, etc.
* Every `is*` function you will ever need
* Lots of string operations
