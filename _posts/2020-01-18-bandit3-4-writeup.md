---
layout: post
title: Bandit Level 3 → Level 4
author: Marcelo Silva
img: "assets/img/bandit-image.jpg"
excerpt_separator: <!--more-->
tags: [Bandit, 3 Bit Squad, CTF]
---

![image]({{ page.img | relative_url }})



## Hello everyone!


In this post I'll present my solution to the Bandit Level 3. Soon I'll be publishing the solution for Bandit Level 4.

<!--more-->
If you want to try it yourself before seeing the solution, here you have the URL:


[https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)



**When we start we are presented with the following statement: **



The password for the next level is stored in a hidden file in the inhere directory.



## *My solution*


To enter the level, one must do the command: 
     

     $ ssh -p 2220 -l bandit3 bandit.labs.overthewire.org

     With the password, which is the flag from the previous level.
    

## *And we are in!*     



Once inside I did the command:
    
     ~$ ls


     And the folder inhere appeared



Let's see the folders content and move inside it with the command cd



    ~$ cd inhere



Once in the folder, lets type the command ls again:



    ~/inhere$ ls

    
     And nothing appeared.
    
     Once I saw that the ls command didn't printed anything I thought the file was hidden. 

     In order to find a hidden folder or file one as to use the ls command with a certain flag:



-a,   --all do not ignore entries starting with. (from the ls --help command)
     ~/inhere$ ls -a



     And now we could see a file .hidden


     $ cat .hidden     


Careful, I am about to reveal the flag! skip this part if you don't want to know it.



And after this command the flag appears:

<details>
  <summary>And the printed flag is: </summary>
     {% highlight text %} pIwrPrtPN36QITSp3EQaw936yaFoFgAB {% endhighlight text %}
</details> 

----
See you soon, **thank you!**  
Cheers  
*Marcelo Silva*

