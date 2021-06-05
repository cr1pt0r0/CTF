# Overview
5 Points
Category: General Skills

# Description
This file has a flag in plain sight (aka "in-the-clear").  [Download flag](https://mercury.picoctf.net/static/33996e32dce022205a6a36f69aba56f0/flag).

# Hints 
1. Any hints about entering a command into the Terminal (such as the next one), will start with a '$'... everything after the dollar sign will be typed (or copy and pasted) into your Terminal.
2. To get the file accessible in your shell, enter the following in the Terminal prompt: $ wget https://mercury.picoctf.net/static/33996e32dce022205a6a36f69aba56f0/flag
3. $ man cat

# Approach
I use strings command to see if the flag shows up.

`strings flag`

The result shows as below

![](https://user-images.githubusercontent.com/49737524/120900741-7d57b180-c604-11eb-8e1e-73fae083f335.png)

# Flag
picoCTF{s4n1ty_v3r1f13d_2aa22101}
