# bssid_mapping
---
Collecting BSSID's via API - Then mapping long/lat

# Process
---
## Using my own BSSID I am able to return 0-80 BSSID's on average.
---
Throughout this I learned pretty quickly that I could only get a couple 100 BSSID's before I realized I was building up quite the stockpile and I would almost consistently return the same exact BSSID's. Doing my best to get new ones, I got my first 200 to 400 by simply scanning through a list and trying at random.

I then started calculating the delta between the largest and the smallest longitudes and latitudes and reusing the BSSID's with the greatest deltas as they would most likely be on the edge of where I had already scanned/mapped out as they were basically broken up into a coordinate grid (longitude and latitude) this would essentially allow me to understand if I'm going left right up or down.

Once I got to about 2000 I was realizing that simply using the deltas still limited me as there was no further direction outside of just oh this is the farthest point from this point and as I'm using a coordinate grid I'm essentially only going in 90° angles all four ways. I decided to then try to calculate in a 45° angle in order to potentially gain more data points. till tomorrow 07/08/2025


## Still in progress 07/08/2025
