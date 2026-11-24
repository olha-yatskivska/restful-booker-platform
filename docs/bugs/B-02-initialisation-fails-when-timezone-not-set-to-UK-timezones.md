Id: B-02   
Summary: Initialisation fails when Timezone not set to UK timezones  #33   
Status: Closed

Running the shell script will fail if the system's timezone is set to be outside the UK (eg, if you're from Ecuador)

The script will finish after erroring out, informing that the server's been successfully raised, but the app will be unavailable

Rootcause: Looks like the API was translating dates incorrectly if in a timezone outside of ETC. Fixed the issue by setting a default timezone for the API.
