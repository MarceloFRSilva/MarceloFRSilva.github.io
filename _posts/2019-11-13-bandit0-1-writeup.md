---
layout: post
title: Bandit Level 0 → Level 1
tags: [Bandit, 3 Bit Squad, CTF]
author: Marcelo Silva
img: "assets/img/bandit-image.jpg"
excerpt_separator: <!--more-->
---

![image]({{ page.img | relative_url }})

## Hello everyone!


In this post I'll present my solution to the Bandit Level 0. Soon I'll be publishing the solution for Bandit Level 1.



If you want to try it yourself before seeing the solution, here you have the URL:


[https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)



When we start we are presented with the following statement: 


The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.


## *My solution*


First we need to know which are the flags that enable us to specify the username and the port.
After some search I manage to find out that the flags are:

Username flag -l <username>
Port flag -p <port_number>

Therefore, the final command is:

    $ ssh -p 2220 -l bandit0 bandit.labs.overthewire.org

    And then insert the password bandit0
