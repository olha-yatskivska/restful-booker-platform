Link: https://github.com/mwinteringham/restful-booker-platform/issues/63    
Summary: No handling for bookings in a deleted room   
Status: Closed 


 When you have an booking in a deleted room, when located via search the app fails to load. A GET to room/[room_id] returns a 500. An error of TypeError: Cannot read property 'toString' of undefined is thrown.

To reproduce:

Login as the admin user
Either create a room and a booking, then delete the room you created. Alternatively delete room 101 if the default database is currently being used.
Using the search feature, search for the name used in the booking which will be visible and then click.
Result:
The above errors are thrown and the app fails to render.

Expected Result:
Either deleting a room should destroy all bookings, or bookings without rooms should error when accessed.

Comment: Search has been removed in a previous story and bookings are now deleted when rooms are removed
