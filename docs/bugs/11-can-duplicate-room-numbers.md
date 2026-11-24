Link: https://github.com/mwinteringham/restful-booker-platform/issues/64    
Summary: Can duplicate room numbers    
Status: Closed Not a bug


There is no uniqueness check on room numbers, and as a result rooms can be created with the same room number.

To Reproduce:

Login as the admin
Add a room with all valid options and a number of [SOMENUMBER]
Add another room with all valid options and a number of [SOMENUMBER]
Result:
Room created

Expected Result:
Should error and enforce room# uniqueness


Comment: We've discussed this as a feature and decided not to implement as it complicates our training workshop tied to the app.
