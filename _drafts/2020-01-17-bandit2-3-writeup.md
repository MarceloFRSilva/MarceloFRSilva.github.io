Hello everyone!

In this post I'll present my solution to the Bandit Level 2. Soon I'll be publishing the solution for Bandit Level 3.



If you want to try it yourself before seeing the solution, here you have the URL:


https://overthewire.org/wargames/bandit/



When we start we are presented with the following statement: 



The password for the next level is stored in a file called spaces in this filename located in the home directory.


*My solution*


To enter the level, one must do the command: 
     

     $ ssh -p 2220 -l bandit2 bandit.labs.overthewire.org

     With the password, which is the flag from the previous level.
    
And we are in!     



Once inside I did the command:
    
     $ ls
    
     And the file spaces in this filename appeared.
    
     In order to open it I did the command:
    
     $ cat spaces\ in\ this\ filename     



In order to escape the spaces one as to use the symbol \ its just that really.


Careful, I am about to reveal the flag! skip this part if you don't want to know it.



And after this command the flag appears:
