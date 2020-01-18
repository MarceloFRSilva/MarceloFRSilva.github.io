---
layout: post
title: Bandit Level 2 → Level 3
author: Marcelo Silva
img: "assets/img/bandit-image.jpg"
excerpt_separator: <!--more-->
tags: [Bandit, 3 Bit Squad, CTF]
---

![image]({{ page.img | relative_url }})



## Hello everyone!

In this post, I'll present my solution to the Bandit Level 2. Soon I'll be publishing the solution for Bandit Level 3.

<!--more-->
If you want to try it yourself before seeing the solution, here you have the URL:


[https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)


**When we start we are presented with the following statement:**

The password for the next level is stored in a file called spaces in this filename located in the home directory.



## *My solution*


To enter the level, one must do the command: 
     

     $ ssh -p 2220 -l bandit2 bandit.labs.overthewire.org

     With the password, which is the flag from the previous level.
    

## *And we are in!*     



Once inside I did the command:
    
     $ ls
    
     And the file spaces in this filename appeared.
    
     To open it I did the command:
    
     $ cat spaces\ in\ this\ filename     



To escape the spaces one as to use the symbol \ its just that.


**Careful, I am about to reveal the flag! skip this part if you don't want to know it.**



And after this command the flag appears:

<details>
  <summary>And the printed flag is: </summary>
     {% highlight text %} UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK {% endhighlight text %}
</details> 

----
See you soon, **thank you!**  
Cheers  
*Marcelo Silva*
