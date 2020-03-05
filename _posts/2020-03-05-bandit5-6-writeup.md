---
layout: post
title: Bandit Level 5 → Level 6
author: Marcelo Silva
img: "assets/img/bandit-image.jpg"
excerpt_separator: <!--more-->
tags: [Bandit, 3 Bit Squad, CTF]
---

![image]({{ page.img | relative_url }})



## Hello everyone!


In this post I'll present my solution to the Bandit Level 5. Soon I'll be publishing the solution for Bandit Level 6.

<!--more-->
If you want to try it yourself before seeing the solution, here you have the URL:


[https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)


**When we start we are presented with the following statement:**

The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

human-readable
1033 bytes in size
not executable

## *My solution*


To enter the level, one must do the command: 
     

     $ ssh -p 2220 -l bandit5 bandit.labs.overthewire.org

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



     maybehere00  maybehere03  maybehere06  maybehere09  maybehere12  maybehere15

     maybehere18  maybehere01  maybehere04  maybehere07  maybehere10  maybehere13

     maybehere16  maybehere19  maybehere02  maybehere05  maybehere08  maybehere11

     maybehere14  maybehere17



     Which consist in a bunch of folders, now how can we find anything here, fast, without having to go to every fodler and see its content?

   

As we have on the challenge statement the flag is "stored in the only human-readable it has 1033 bytes in size and it is not executable". Knowing this we will use some part of the previous exercise, for instances we will use this command, for starts:

   

    First lets try this command then:


    ~/inhere$ find . -exec file {} +| grep ASCII


    This command, as we know, will display all of the files with ASCII text, however we still have alot of files as output, in order to narrow it down we need to insert a new restriction, lets say that we now will say that only want to see the files from the type ASCII text and with size 1033, for that I did some research and manage to find the flag -size of the find command, therefore the command with both of the restritions is:


    ~/inhere$ find -size 1033c -exec file {} +| grep ASCII


    And now we get only one output:


   ./maybehere07/.file2: ASCII text, with very long lines


    In order to make choore that we have to right file lets add the third restriciton from the challenge statement, which states that it is not an executable file, for that we will use the flag -executable as negative, like so:

   

   ~/inhere$ find . -size 1033c ! -executable -exec file {} +| grep ASCII



   Here I leave an image:

![GitHub Logo](/images/bandi5image.png)




    As we can see, this is the only file that meets all 3 restrictions, now lets see if it as the flag inside it by typing the following command:



    ~/inhere$ cat ./maybehere07/.file2


And after this command the flag appears:

<details>
  <summary>And the printed flag is: </summary>
     {% highlight text %} DXjZPULLxYr17uwoI01bNLQbtFemEgo7 {% endhighlight text %}
</details> 

----
See you soon, **thank you!**  
Cheers  
*Marcelo Silva*

