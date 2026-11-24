   
id: B-01    
Summary: Update of booking data leads to deletion of name and price entry #29    
Status: Closed 

Steps to reproduce:

* enter a booking (name, price etc.), press create button
* update this booking, e.g. extend the booking by one day


Actual result:   
With the update, first name and family name are deleted. Price is set to 0.

Expected result:    
The values should not be updated since the user did not change them.
