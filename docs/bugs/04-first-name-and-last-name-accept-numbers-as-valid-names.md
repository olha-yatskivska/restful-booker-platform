Link: https://github.com/mwinteringham/restful-booker-platform/issues/49   
Summary: First name and Last name accept numbers as valid names

Status: Closed

Currently if I provide a single number char for either of first name and last name, the system accepts as valid name   .

It should validate at least that the name should not start with numbers and should be at least more than 1 character.


Implemented: Validation rules have been updated to now set a minimum of three characters and only accept alphas
