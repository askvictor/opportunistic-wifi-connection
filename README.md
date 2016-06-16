# opportunistic-wifi-connection
Code for ESP8266 (and possibly others) to connect to any open wifi network, and attempt to get through the captive portal.

The basic workflow will be as follows:
* Look for open wifi network
* attempt to connect
* if not connected, try another network
* if connected, try to connect to http://clients3.google.com/generate_204 - this should return no content and a 204 status
* if data returned, look for form elements the following in the returned data:
   * Checkboxes
   * submit buttons
   * email, name and D.O.B. fields
* submit form data
* try connection again, rinse, repeat 

Particularly for failed attempts, it would be useful to save the portal page for further analysis down the track.
