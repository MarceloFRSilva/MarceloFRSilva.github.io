---
layout: post
title: Bandit Level 4 → Level 5
author: Marcelo Silva
img: "assets/img/bandit-image.jpg"
excerpt_separator: <!--more-->
tags: [Bandit, 3 Bit Squad, CTF]
---

![image]({{ page.img | relative_url }})



## Hello everyone!


In this post I'll present my solution to the Bandit Level 4. Soon I'll be publishing the solution for Bandit Level 5.

<!--more-->
If you want to try it yourself before seeing the solution, here you have the URL:


[https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)


**When we start we are presented with the following statement:**

The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.



## *My solution*


To enter the level, one must do the command: 
     

     $ ssh -p 2220 -l bandit4 bandit.labs.overthewire.org

     With the password, which is the flag from the previous level.
    
    
## *And we are in!*     



Once inside lets see the home (~) folder's content with the command:

     ~$ ls


     And the folder inhere appeared



Now, let's see the inhere folder's content and move inside it with the command cd



    ~$ cd inhere/



Once in the folder, lets type the command ls again:



    ~/inhere$ ls



     And the output we get:



     -file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09



   

As we have on the challenge statement the flag is "stored in the only human-readable file in the inhere directory". 


    After some search I manage to find a few possible ways to find human-readable files.

   

    First I tried to use the ls command with the -h flag:


    ~/inhere$ ls -h


    But the output was the same as it was before.


    ## So I tried another thing, the file command on all of the files on the inhere directory, I used the file command as it "Determine type of FILEs" according to the file command manual, like so:

![GitHub Logo](/images/images.jpeg)
Format: ![Alt Text](url)
