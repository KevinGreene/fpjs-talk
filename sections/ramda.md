## Ramda

Like Lodash, but better


### Functions First

When currying, functions first helps the most

Data last allows you to compose functions more easily


### Map Functions

```javascript
var objects = [{id: 1, name: "This"}, {id: 123, name: "That"}];
var getIDs = R.map(R.get('id'));
var ids = getIDs(objects);
```


### ToDo in Plain JS & _

```javascript
// Plain JS
var incompleteTasks = tasks.filter(function(task) {
    return !task.complete;
});

// _
var incompleteTasks = _.filter(tasks, {complete: false});
```


### ToDo in Ramda

```javascript
// Just a function
var incomplete =  R.filter(R.where({complete: false});
```


### Functions over Data

Functions first let you build reusable components

Easily adapt and expand to requirements


### Get Active ToDos

```javascript
var groupByUser = R.partition(R.get('username'));
var activeByUser = R.compose(groupByUser, incomplete);
var sortUserTasks = R.compose(R.map(R.sortBy(R.get("dueDate"))), activeByUser);
```


### Complete List

```javascript
var incomplete = R.filter(R.where({complete: false}));
var sortByDate = R.sortBy(R.prop('dueDate'));
var sortByDateDescend = R.compose(R.reverse, sortByDate);
var importantFields = R.project(['title', 'dueDate']);
var groupByUser = R.partition(R.prop('username'));
var activeByUser = R.compose(groupByUser, incomplete);
var gloss = R.compose(importantFields, R.take(5), sortByDateDescend);
var topData = R.compose(gloss, incomplete);
var topDataAllUsers = R.compose(R.mapObj(gloss), activeByUser);
var byUser = R.use(R.filter).over(R.propEq("username"));
```


### Resources

http://fr.umio.us/why-ramda/


### Lodash vs Ramda

Ramda focuses on the collections part of Lodash

Lodash stil provides lots of compelling utility functions

Underscore and Lodash are becoming ubiquitous
