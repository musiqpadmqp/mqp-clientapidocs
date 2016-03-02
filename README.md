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

Returns a [user] object.

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

Returns array of [user] objects.

Parameters:

  * is_array | boolean | optional
    * Defaults to false if not provided.
	* If is_array is set to true then the users will be returned in the format `[{user_object}]`
	* If is_array is set to false then the users will be returned in the format `{user_id:{user_object}}`

``` javascript
API.room.getUsers(true);
```

### getStaff

Returns an array of staff [user] object.

Parameters:

  * callback | function | optional
    * If provided will return the data from a new socket request.
	* Otherwise will return the data that the client currently has.

``` javascript
API.room.getStaff(function (data) {
  // doSomething();
});
```

### getBannedUsers

Returns an array of banned [user] object.

Parameters:

  * callback | function | optional
    * If provided will return the data from a new socket request.
	* Otherwise will return the data that the client currently has.

``` javascript
API.room.getBannedUsers(function (data) {
  // doSomething();
});
```

### getRoles

Returns array of [role] objects.

Parameters:

  * is_array | boolean | optional
    * Defaults to false if not provided.
	* If is_array is set to true then the roles will be returned in the format `[{role_object}]`
	* If is_array is set to false then the roles will be returned in the format `{role_name:{role_object}}`

``` javascript
API.room.getRoles(true);
```

### getHistory

Returns sorted array of [media] objects.

Parameters:

  * callback | function | optional
    * If provided will return the data from a new socket request.
	* Otherwise will return the data that the client currently has.

``` javascript
API.room.getHistory(function (data) {
  // doSomething();
});
```

### getMedia

Returns [media] object.

``` javascript
API.room.getMedia();
```

### getTimeElapsed

Returns the time elapsed of the current song in seconds.

``` javascript
API.room.getTimeElapsed();
```

### getTimeRemaining

Returns the time remaining of the current song in seconds.

``` javascript
API.room.getTimeRemaining();
```

### banUser

Parameters:

  * user_id | integer | mandatory
    * The id of the user whom you wish to ban.
  * duration | string | mandatory
    * The duration which you would like to ban for. Pre-defined durations are available in the [Data API].
  * reason | string | optional
    * The reason for the ban. This will be shown to the user who gets banned.
  * callback | function | optional
    * Returns once the action has been completed on the server.

``` javascript
API.room.banUser(123, API.DATA.USER.BAN.DAY, 'Ban Reason', function (data) {
  // doSomething();
});
```

### unbanUser

Parameters:

  * user_id | integer | mandatory
    * The id of the user whom you wish to unban.
  * callback | function | optional
    * Returns once the action has been completed on the server.

``` javascript
API.room.unbanUser(123, function (data) {
  // doSomething();
});
```

### setRole

Parameters:

  * user_id | integer | mandatory
    * The id of the user whom you wish to ban.
  * role | string | mandatory
    * The role to set the user to. Must match the role name from [API.room.getRoles].
  * callback | function | optional
    * Returns once the action has been completed on the server.

``` javascript
API.room.setRole(123, 'role name', function (data) {
  // doSomething();
});
```

## API.queue

### join

Parameters:

  * callback | function | optional
    * Returns once the action has been completed on the server.

``` javascript
API.queue.join(function (data) {
  // doSomething();
});
```

### leave

Parameters:

  * callback | function | optional
    * Returns once the action has been completed on the server.

``` javascript
API.queue.leave(function (data) {
  // doSomething();
});
```

### modAddDJ

Parameters:

  * user_id | integer | mandatory
    * The id of the user whom you wish to add to the queue.
  * callback | function | optional
    * Returns once the action has been completed on the server.

``` javascript
API.queue.modAddDJ(123, function (data) {
  // doSomething();
});
```

### modRemoveDJ

Parameters:

  * user_id | integer | mandatory
    * The id of the user whom you wish to remove from the queue.
  * callback | function | optional
    * Returns once the action has been completed on the server.

``` javascript
API.queue.modRemoveDJ(123, function (data) {
  // doSomething();
});
```

### modSwapDJ

Parameters:

  * user_id_1 | integer | mandatory
    * The id of the user whom you wish to swap with user_id_2.
  * user_id_2 | integer | mandatory
    * The id of the user whom you wish to swap with user_id_1.
  * callback | function | optional
    * Returns once the action has been completed on the server.

``` javascript
API.queue.modSwapDJ(123, 321, function (data) {
  // doSomething();
});
```

### modMoveDJ

Parameters:

  * user_id | integer | mandatory
    * The id of the user whom you wish to move.
  * position | integer | mandatory
    * The position you would like to move the user to.
  * callback | function | optional
    * Returns once the action has been completed on the server.

``` javascript
API.queue.modSwapDJ(123, 5, function (data) {
  // doSomething();
});
```

### skipDJ

Parameters:

  * position | integer | optional
    * The position you would like to move the user to after being skipped.
    * Will 'Lock Skip' the user to the position specified.
  * callback | function | optional
    * Returns once the action has been completed on the server.

``` javascript
API.queue.skipDJ(5, function (data) {
  // doSomething();
});
```

### setLock

Parameters:

  * lock_status | boolean | optional
    * If specified will attempt to set the lock status.
    * If not specified will toggle the lock.
  * callback | function | optional
    * Returns once the action has been completed on the server.

``` javascript
API.queue.setLock(true, function (data) {
  // doSomething();
});
```

### setCycle

Parameters:

  * cycle_status | boolean | optional
    * If specified will attempt to set the cycle.
    * If not specified will toggle the cycle.
  * callback | function | optional
    * Returns once the action has been completed on the server.

``` javascript
API.queue.setCycle(true, function (data) {
  // doSomething();
});
```

### getDJ

Returns the [user] object of the current DJ.

``` javascript
API.queue.getDJ();
```

### getDJs

Returns an array containing [user] objects of the queue.

``` javascript
API.queue.getDJs();
```

### getDJ

Returns the [user] object of the current DJ.

``` javascript
API.queue.getDJ();
```

### getPosition

Returns an integer for the users position in the queue.

Parameters:

  * user_id | integer | optional
    * If specified will get the position of the provided user in the queue.
    * If not specified will get the position of the current user in the queue.

``` javascript
API.queue.getPosition(123);
```

Musiqpad Client API Objects
=======

## Media

``` javascript
{
	
}
```

## User

``` javascript
{
	
}
```

## Role

``` javascript
{
	
}
```

Musiqpad Client Data API
=======

[API.room.getRoles]: #musiqpad-client-api-functions-apiroom-getroles
[media]: #musiqpad-client-api-objects-media
[user]: #musiqpad-client-api-objects-user
[role]: #musiqpad-client-api-objects-role
[Data API]: #musiqpad-client-data-api
