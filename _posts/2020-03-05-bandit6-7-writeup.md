---
layout: post
title: Bandit Level 6 → Level 7
author: Marcelo Silva
img: "assets/img/bandit-image.jpg"
excerpt_separator: <!--more-->
tags: [Bandit, 3 Bit Squad, CTF]
---

![image]({{ page.img | relative_url }})



## Hello everyone!


In this post I'll present my solution to the Bandit Level 6. Soon I'll be publishing the solution for Bandit Level 7.

<!--more-->
If you want to try it yourself before seeing the solution, here you have the URL:


[https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)


**When we start we are presented with the following statement:**

The password for the next level is stored somewhere on the server and has all of the following properties:

owned by user bandit7
owned by group bandit6
33 bytes in size

## *My solution*


To enter the level, one must do the command: 
     

     $ ssh -p 2220 -l bandit6 bandit.labs.overthewire.org

     With the password, which is the flag from the previous level.
    

## *And we are in!*     



Once inside lets see the home (~) folder's content with the command:

     ~$ ls


     And nothing appeared


We know from the challenge statement that the file is owned by user bandit7, owned by group bandit6 and as 33 bytes in size. Knowing this I did some search on the manual of the find command, like so:

    ~$ man find

And then I read a little bit and I found out that we have a flag to specify the group owner of the file and the user that owns the file, knowing this and the -size flag, as we have seen in the previous challenge we have the command:

    ~$ find /  -size 33c -group bandit6 -user bandit7
  
Once we type enter we get a huge list of files, however we have "Permission denied" in most of them, and "No such file or directory" in others, which are error messages, I belive that the file we want is somewhere in that mess! So lets remove this error messages by using the command grep with a few tweaks, like so:

    ~$ find / -size 33c -group bandit6 -user bandit7 2>&1 | grep  -v "Permission denied" 2>&1 | grep -v "No such file or directory"


And now we just get  one line as output!!
   
     /var/lib/dpkg/info/bandit7.password


Lets now see in more detail the tweaks we added to the command, we did 2>&1 before grep because we want to redirect all of the output, both stdout and stderr, to the | pipe. Meaning that 2>&1 is the same as 2 outputs, stdout and stderr, to merge into 1. This is all because the pipe only reads from the stdout. And if we try to remove the errors with the grep commands like we did before but without the 2>&1 we won't be able to remove them because they won't go through the pipe.  

----

Just a note, we did the find on the / directory because as said in the statement the file is somewhere on the server, and with this command we search in all files and folders inside the server.

----

Afterwards we use the cat command:

     ~$ cat /var/lib/dpkg/info/bandit7.password


And after this command the flag appears:

<details>
  <summary>And the printed flag is: </summary>
     {% highlight text %} HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs {% endhighlight text %}
</details> 

----
See you soon, **thank you!**  
Cheers  
*Marcelo Silva*

