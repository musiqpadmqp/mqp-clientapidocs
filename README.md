Musiqpad Client API Functions
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

  * callback | optional
    * If provided will return the data from a new socket request.
	* Otherwise will return the data that the client currently has.

``` javascript
API.room.getInfo(function (data) {
  // doSomething();
});
```

### getUser

Parameters:

  * user_id | integer | optional
    * Will pass back the current logged in users information if this parameter is not provided.
  * callback | function | optional
    * If provided will return the data from a new socket request.
	* Otherwise will return the data that the client currently has.

``` javascript
API.room.getUser(123, function (data) {
  // doSomething();
});
```

### getUsers

Parameters:

  * is_array | boolean | optional
    * Defaults to false if not provided.
	* If is_array is set to true then the users will be returned in the format `[{user_object}]`
	* If is_array is set to false then the users will be returned in the format `{user_id:{user_object}}`

``` javascript
API.room.getUsers(true);
```

### getRoles

Parameters:

  * is_array | boolean | optional
    * Defaults to false if not provided.
	* If is_array is set to true then the roles will be returned in the format `[{role_object}]`
	* If is_array is set to false then the roles will be returned in the format `{role_name:{role_object}}`

``` javascript
API.room.getRoles(true);
```

### getHistory

Parameters:

  * callback | optional
    * If provided will return the data from a new socket request.
	* Otherwise will return the data that the client currently has.

``` javascript
API.room.getHistory(function (data) {
  // doSomething();
});
```

### getMedia

Returns media object

``` javascript
API.room.getMedia();
```

Musiqpad Client API Objects
=======

## Media

``` javascript
{
	mediaObject: ""
}
```
