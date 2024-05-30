
# Command line basics!


* [What the hell is "the shell"?](#what-the-hell-is-\"the-shell\"?)
* [Why should I use one?](#why-should-i-use-one?)
* [Getting started!](#getting-started!)
* [References](#references)



Hi everyone! 

This will be a very soft introduction to the command-line.

~~~I am assuming you are using either a Mac or a Linux machine.~~~

Please head over to our jupyter notebook in this link

*Note*: If you already use a command line you are welcome to use that instead on your personal computer.


# 1. What the hell is "the shell"?

Read this [5 min tutorial](https://swcarpentry.github.io/shell-novice/01-intro/index.html) and then come back here!


Now you know what it is! It is a computer program that allows you to "talk" to your computer and give it tasks. But you need to speak its language!

In a Unix or Linux based machines, which includes Macs (they use Unix in the background with a fluffy interface for the user), the command line or shell is easy to access. On a Mac, you can do so by going to the app "Terminal". 

# 2. Why should I use one?

It may not seem worth your while to run a program ONCE using the command-line, but when you find yourself contemplating manually repeating a computational task 100 times, the appeal becomes clear!

* high action-to-keystroke ratio
* support for automating repetitive tasks
* capacity to access networked machines.

# 3. Opening a terminal window

![](images/collab.png)


![](images/collab2.png)

* Alternative: you may try to use this webspace here, which is super cool but it's a bit flimsy (doesn't always work).

* Use your own computer

1. Mac: In your personal or lab computer (if Linux or Mac), go to the "Terminal" application. Tip: if you don't know where to find it, open Finder and search for it. 

2. Windows: if you have found a way to use a command line on Windows, you're welcome to do so, but I have zero knowledge about this. 

### 4. Let's get familiar with the terminal!

Once you open a terminal, run the "path to working directory" command:

```{bash}
pwd
```
Q1. What does this show you? (I.e., what is the output of this command)



Now check what's in that directory:

```{bash, eval=F}
ls 

```

Q2. What do you think the above command does?

Check your guess by using the pwd command again to check where you are:

```{bash, eval=F}
pwd
```


notice that “cd ~/Desktop” is equivalent to “cd /Users/your_username/Desktop” if on a Mac (or “home/your_username”/Desktop if on Linux). 

If you are using the web terminal, this won't be your desktop, of course, but something like



Try it!


```{bash}
#type your command in your terminal 
```

And then check what directory you're currently in with the path to working directory command:
```{bash, eval=F}
pwd
```


Knowing that your downloads folder (on a Mac) has the following path: /Users/your username/Downloads

Type a command that will take you there without having to type the entire path above


```{bash}
#type your command in your terminal 
```

Now check where you are by using the “pwd” command:
```{bash}
#type your command in your terminal 
```


Great! Now let’s go back to the Desktop folder:
```{bash}
#type your command in your terminal 
```


Now, we are going to create a subdirectory(a subfolder) within your desktop. Let’s call it “B216”. The command to create that is “make directory”, which is executed by typing:

```{bash, eval=F}
mkdir B216
```


Next, we are going to move into that directory. Remember, you are already in the Desktop directory, and the B216 directory lives inside it, so all you have to do is use the “cd” command followed by the name of the subdirectory. Try it!
```{bash}
#type your command in your terminal 
```

Great! Now, let’s list the files inside this directory. Use the “list” commands, which ix executed by typing “ls”:

```{bash}
#type your command in your terminal 
```

You shouldn’t see anything in there, because you just created this - it’s brand new! But to check that this works, list the files that are currently in your “Downloads” folder. (if you’re anything like your professor, there will be about 2,000 files in there). You will do this by typing “ls” followed by the path to your Downloads folder:

```{bash}
#type your command in your terminal 
```


Finally, let’s go back to your Desktop folder. There are three ways to do this. Two you already know (type the path or the shortcut path we saw above). The third one involves using “..”.

Your directories have an internal structure. “Desktop” is a subdirectory of “Users/” and “B216” is a subdirectory of “Desktop”. Whenever you are in a subdirectory, you can go back to the one “above” it by simply typing “../”.

Try the three different commands, followed by “pwd” to check that they will all get you to where you want to go:

```{bash}
#type your command in your terminal and write it down here
cd ../ # this command means "go back to the directory above this one in the hierarchy
#check where you are by typing pwd:
```


### References

https://swcarpentry.github.io/shell-novice/01-intro/index.html

The end!


