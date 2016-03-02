Musiqpad Client API
=======

To Do :- Add Description

*Current version: 0.5 Beta*

This is a list of all the public functions available in the API.

## API.example

### Example function

Parameters:

  * callback

``` javascript
API.example.runExample(function (err, data) {
  // doSomething();
});
```

## API.room

### getInfo

Parameters:

  * callback, optional
    * If provided will return the data from a new socket request.
	* Otherwise will return the data that the client currently has.

``` javascript
API.room.getInfo(function (data) {
  // doSomething();
});
```
