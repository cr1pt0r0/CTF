# Overview
20 Points
Category: Reverse Engineering

# Description
I wonder what this really is... [enc](https://mercury.picoctf.net/static/dd6004f51362ff76f98cb8c699510f23/enc) ''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])

# Hints 
1. You may find some decoders online

# Approach
I use cat command to identify the content

`cat enc`

![Screenshot_2021-06-10_01-23-58](https://user-images.githubusercontent.com/49737524/121469490-93f66380-c98a-11eb-8c37-ea9787ceff1e.png)

After seeing this, I tried to decode these characters by getting the integers. This can be done using python. I started to create a new file called enc.py. In this method, I used mousepad as my editor.

`mousepad enc.py`

And the I entered the code as below. I used ord() function to return the integer representing the Unicode character.

![Screenshot_2021-06-10_01-30-03](https://user-images.githubusercontent.com/49737524/121469965-6d84f800-c98b-11eb-8532-6dc1d3126ada.png)


I ran the python script `python3 enc.py` and the result is shown as below

![Screenshot_2021-06-10_01-33-32](https://user-images.githubusercontent.com/49737524/121470214-e2f0c880-c98b-11eb-9d2b-05b5912feeca.png)

Then I converted this to hex code by adding hex() function after the ord() function.

![Screenshot_2021-06-10_01-40-57](https://user-images.githubusercontent.com/49737524/121470958-eb95ce80-c98c-11eb-9153-8cdb71ee1681.png)

Then I ran the script, result shown as below.

![Screenshot_2021-06-10_01-39-50](https://user-images.githubusercontent.com/49737524/121470868-ca34e280-c98c-11eb-99ce-c8216b70df0a.png)

After getting the hex code, I stripped the "0x" from the result and print the result in one line by adding `end=''` after print() function.

![Screenshot_2021-06-10_01-44-34](https://user-images.githubusercontent.com/49737524/121471314-74ad0580-c98d-11eb-9348-ebefd5068f12.png)

Result shown as below

![Screenshot_2021-06-10_01-44-14](https://user-images.githubusercontent.com/49737524/121471387-95755b00-c98d-11eb-9745-1d0907b16498.png)

Finally, I decoded the hex to ascii by using bytearray.fromhex().decode command and got the flag. (Note: You can also use online decoder for this)

![transformation_finalcode](https://user-images.githubusercontent.com/49737524/121471645-09affe80-c98e-11eb-8594-6bc147f350a5.png)

![transformation_flag](https://user-images.githubusercontent.com/49737524/121471685-192f4780-c98e-11eb-96ed-8f36c4e85ae2.png)

# Flag
picoCTF{16_bits_inst34d_of_8_0ddcd97a}
