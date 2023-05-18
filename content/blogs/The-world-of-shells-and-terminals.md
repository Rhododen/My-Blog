---
title: "The World of Shells and Terminals"
date: 2023-05-18T20:33:44+01:00
draft: false
author: "Rhoda"
tags: 
    - Linux
    - Bash
    - Terminals
    - Operating systems
image: /images/terminal-background.jpg
description:
---

Hey there!

Do you know you don't speak the same language as your computer? While you may be multilingual, your computer only speaks and understands one language. **Binary**.

Right. You may be able to speak Spanish and English but your computer can only speak ones and zeros.

How do I then make my computer do what I want it to do?

 **The Kernel**: The kernel is the core of the operating system (Think of the engine in a car). It is responsible for the execution of processes, handling of system operations, and management of system resources amongst other things.  But there is a small problem there - The  kernel 'understands' only binary language, which is basically ones and zeros. So if I want a particular process to be executed, how do I communicate to my kernel to get that done?

 **The Shell**: It is the shell that acts as the middleman between the user and the kernel. The shell accepts the commands entered in the language recognizable by the user and translates them to binary language for the kernel. Without shells, it is practically impossible for a person to utilise the features and functionality offered by the kernel installed on their system.

 *The Terminal*: The user interacts with the shell through the terminal. This is  where the user enters a written command. The shell then takes those commands and interprets them into binary language which it passes to the kernel. The kernel finally takes the binary language commands and executes the task. 

There are different types of shells each with its own set of unique features and functionalities. We have sh, bash, zsh, ksh, fish, and others. 

<div align="center">
    <img src=/images/Linux.webp>
</div>

On Linux-based operating systems, the default shell is the Bash shell which is an acronym for Bourne-Again shell. This may be a major reason why it’s the most popular. Another reason is that Bash is open-source software, meaning that anyone can contribute to its development and improvement and this has brought about a large community of Bash users so you are more likely to get help online whenever you run into a Bash-related problem.

Finally, I also want to mention the versatility of Bash. Bash offers a wide range of features and it has amazing shell scripting capabilities. So it’s pretty easy to customize your shell environment and automate your tasks.

**Shell prompt vs Shell script**

There are 2 ways you can pass commands to the shell. You can decide to do it manually, one at a time  and get immediate feedback by using the shell prompt. The shell prompt typically displays information such as the user’s username, hostname and the current working directory. 

<div align="center">
    <img src=/images/terminal2.webp>
</div>

You can also pass commands to the shell by writing scripts. A script is a text file that contains a set of commands that can be executed automatically by the shell. Scripting(passing commands via scripts which can be written in different programming languages) allows you automate repetitive tasks and perform operations that require multiple commands 

I will like to hear your thoughts and your feedbacks. Please feel free to share your thoughts using the contact me section of this website.

See ya!!