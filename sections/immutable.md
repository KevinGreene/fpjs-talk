## Immutable.js


### Mutation sucks

Distracts the developer

Complicates the functions

Slows performance


### Immutable.JS Maps

```javascript
var map1 = Immutable.Map({a:1, b:2, c:3});
var map2 = map1.set('b', 2);
assert(map1 === map2);
var map3 = map1.set('b', 50);
assert(map1 !== map3);
```


### Immutable.JS Arrays

```javascript
var list1 = Immutable.List.of(1, 2);
var list2 = list1.push(3, 4, 5);
var list3 = list2.unshift(0);
var list4 = list1.concat(list2, list3);
assert(list1.size === 2);
assert(list2.size === 5);
assert(list3.size === 6);
assert(list4.size === 13);
assert(list4.get(0) === 1);
```


### Lazy Sequences

```javascript
var oddSquares = Immutable.Seq.of(1,2,3,4,5,6,7,8)
  .filter(x => x % 2).map(x => x * x);
// No work has happened

var oddSquare2 = oddSquares.get(2);
// 6 calculations have happened
```


### Can't have everything

Doesn't always play nice with Ramda / Underscore

Have to transpile down to ES3 for compatibility


### Other libraries

Mori - Clojure collections in plain JS
