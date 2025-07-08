# bssid_mapping
---

## 📘 Navigation

| **Section**            | **Anchor Link**                                                                                                                                      |
|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| BSSID Mapping        | [#bssid_mapping](#bssid_mapping)                                                                                                                    |
| Process Overview     | [#process](#process)                                                                                                                                |
| Own vs Other BSSID   | [#using-my-own-bssid-i-am-able-to-return-0-80-bssids-on-average-using-others-bssid-i-am-able-to-return-a-couple-million](#using-my-own-bssid-i-am-able-to-return-0-80-bssids-on-average-using-others-bssid-i-am-able-to-return-a-couple-million) |
| Ongoing Work         | [#still-in-progress-07082025](#still-in-progress-07082025)                                                                                          |
| Image Progress       | [#image-progress](#image-progress)                                                                                                                  |
| 200 BSSID Image      | [#200-bssid-visual](#200-bssid-visual)                                                                                                           |
| 2000 BSSID Image     | [#2000-bssid-visual](#2000-bssid-visual)                                                                                                         |
| 3000 BSSID Image     | [#3000-bssid-visual](#3000-bssid-visual)                                                                                                         |
| 3850 BSSID Image     | [#3850-bssid-visual](#3850-bssid-visual)                                                                                                         |

---

1. Current Step: Collecting BSSID's, Latitude, Longitude via API - Then mapping long/lat with BSSID.
2. Next Step: Reverse engineer the types of BSSID's - ##:##:##:##:##:## - How does each # and or char relate or what does it relate to? 
3. Future Step: Can I accurately estimate/guess others BSSID's based on latitude/longitude & Discovered charactistics.
4. Images included in `images` folder will eventually be used to help show with visuals.

# Process
---
## Using my own BSSID I am able to return 0-80 BSSID's on average. Using others BSSID... I am able to return a couple million?
---
Throughout this I learned pretty quickly that I could only get a couple 100 BSSID's before I realized I was building up quite the stockpile and I would almost consistently return the same exact BSSID's. Doing my best to get new ones, I got my first 200 to 400 by simply scanning through a list and trying at random. This was becoming tedious, almost no return per query, and feeling pointless. I automated the API calls and the cleaning the extracted data. I would constantly query the same data so I was constantly removing duplicates so I automated the entire process.

I then started calculating the delta between the largest and the smallest longitudes and latitudes and reusing the BSSID's with the greatest deltas as they would most likely be on the edge of where I had already scanned/mapped out as they were basically broken up into a coordinate grid (longitude and latitude) this would essentially allow me to understand if I'm going left right up or down. I quickly realized that I needed to rotate the Min/max long/lat in order to not query the same call over and over and over again. a quick implementation of rotating calls based on log results fixed that.

Once I got to about 2000 I was realizing that simply using the deltas and rotating still limited me as there was no further direction outside of just oh this is the farthest point from this point and as I'm using a coordinate grid I'm essentially only going in 90° angles all four ways. I decided to then try to calculate in a 45° angle and then rotate in 8 directions in order to potentially gain more data points. till tomorrow 07/08/2025



potential issue I am thinking of is that I doubt it would be a true outward spiral of api calls. I think it would be randomized clusters with a outward spiral.


## Still in progress 07/08/2025
---
## Image Progress
---
### 200 BSSID Visual
![200 BSSIDs](images/200_BSSIDs.png)

---

### 2000 BSSID Visual
![2000 BSSIDs](images/2000_BSSIDs.png)

---

### 3000 BSSID Visual
![3000 BSSIDs](images/3000_BSSIDs.png)

---

### 3850 BSSID Visual
![3850 BSSIDs](images/3850_BSSIDs.png)

