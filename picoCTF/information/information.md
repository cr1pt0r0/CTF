# Overview
10 Points
Category: Forensics

# Description
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/a614a27d4cb251d04c7d2f3f3f76a965/cat.jpg)

# Hints 
1. Look at the details of the file
2. Make sure to submit the flag as picoCTF{XXXXX}

# Approach
I use strings command to see if the flag shows up.

`strings cat.jpg`

The image echoed a lot of strings so I started to filter 20 lines of strings from the top by adding head -20 command towards the end.

`strings cat.jpg | head -20`

The result shows as below

![](https://user-images.githubusercontent.com/49737524/120900174-58ae0a80-c601-11eb-8633-e70bde55e200.png)

Since I saw PicoCTF in the header, I started to decode the id and the resource in base64.

![](https://user-images.githubusercontent.com/49737524/120900304-20f39280-c602-11eb-9b30-f10c1532bfb7.png)

# Flag
picoCTF{the_m3tadata_1s_modified}
