---
layout: post
title: Bandit Level 1 → Level 2
tags: [Bandit, 3 Bit Squad, CTF]
author: Marcelo Silva
img: "assets/img/bandit-image.jpg"
excerpt_separator: <!--more-->
---

![image]({{ page.img | relative_url }})

## Hello everyone!


In this post, I'll present my solution to the Bandit Level 1. Soon I'll be publishing the solution for Bandit Level 2.

<!--more-->
If you want to try it yourself before seeing the solution, here you have the URL:


[https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)


**When we start we are presented with the following statement:**

The password for the next level is stored in a file called - located in the home directory.


## *My solution*

To enter the level, one must do the command: 
     

     $ ssh -p 2220 -l bandit1 bandit.labs.overthewire.org

     With the password which is the flag from the previous level.
     

## *And we are in!*



Once inside I did the command:
    
     $ ls
    
     And the file - appeared.
    
     To open it I did the command:
    
     $ cat ./-       



The command cat - doesn't work because the cat will be waiting for a flag, 
so to escape it we must add ./ before the file name.
    
**Careful, I am about to reveal the flag! skip this part if you don't want to know it.**


<details>
  <summary>And the printed flag is: </summary>
     {% highlight text %} CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9 {% endhighlight text %}
</details>  


----
See you soon, **thank you!**  
Cheers  
*Marcelo Silva*
