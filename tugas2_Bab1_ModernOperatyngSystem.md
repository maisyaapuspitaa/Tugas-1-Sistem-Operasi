<h1 align = "center"> 1</h1>
<h1 align = "center">Introduction </h1>

<p align="justify">A modern computer consists of one or more processors, some main memory, disks, printers, a keyboard, a mouse, a display, network interfaces, and various other input/output devices. All in all, a complex system.oo If every application programmer had to understand how all these things work in detail, no code would ever get written. Furthermore, managing all these components and using them optimally is an exceedingly challenging job. For this reason, computers are equipped with a layer of software called the <b>operating system</b>, whose job is to provide user programs with a better, simpler, cleaner, model of the computer and to handle managing all the resources just mentioned. Operating systems are the subject of this book.
</p>

<p align = "justify"> Most readers will have had some experience with an operating system such as Windows, Linux, FreeBSD, or OS X, but appearances can be deceiving. The program that users interact with, usually called the <b>shell</b> when it is text based and the <b>GUI (Graphical User Interface)</b> which is pronounced ‘‘gooey’’—when it uses icons, is actually not part of the operating system, although it uses the operating system to get its work done.</p>

<p align = "justify"> A simple overview of the main components under discussion here is given in Fig. 1-1. Here we see the hardware at the bottom. The hardware consists of chips, boards, disks, a keyboard, a monitor, and similar physical objects. On top of the hardware is the software. Most computers have two modes of operation: kernel mode and user mode. The operating system, the most fundamental piece of software, runs in <b>kernel mode</b> (also called <b>supervisor mode</b>). In this mode it has</p>
<center>1</center>

__________


<p align = "justify"> complete access to all the hardware and can execute any instruction the machine is capable of executing. The rest of the software runs in <b>user mode</b>, in which only a subset of the machine instructions is available. In particular, those instructions that affect control of the machine or do <b>I/O )Input</b>/Output" are forbidden to user-mode programs. We will come back to the difference between kernel mode and usermode repeatedly throughout this book. It plays a crucial role in how operating systems work.</p>


<p align = "center"><img src = "figure 1.1.png"><br><b>Figure 1-1.</b> Where the operating system fits in</p></br>

<p align = "justify">The user interface program, shell or GUI, is the lowest level of user-mode software, and allows the user to start other programs, such as a Web browser, email reader, or music player. These programs, too, make heavy use of the operating system.</p>

<p align = "justify"> The placement of the operating system is shown in Fig. 1-1. It runs on the bare hardware and provides the base for all the other software. </p>

<p align = "justify"> An important distinction between the operating system and normal (usermode) software is that if a user does not like a particular email reader, he† is free to get a different one or write his own if he so chooses; he is not free to write his own clock interrupt handler, which is part of the operating system and is protected by hardware against attempts by users to modify it. </p>

<p align = "justify">This distinction, however, is sometimes blurred in embedded systems (which may not have kernel mode) or interpreted systems (such as Java-based systems that use interpretation, not hardware, to separate the components).</p>

<p align = "justify">Also, in many systems there are programs that run in user mode but help the operating system or perform privileged functions. For example, there is often a program that allows users to change their passwords. It is not part of the operating system and does not run in kernel mode, but it clearly carries out a sensitive function and has to be protected in a special way. In some systems, this idea is carried to an extreme, and pieces of what is traditionally considered to be the operating </p>

___

<p align = "justify">system (such as the file system) run in user space. In such systems, it is difficult to draw a clear boundary. Everything running in kernel mode is clearly part of the operating system, but some programs running outside it are arguably also part of it, or at least closely associated with it.</p>

<p align = "justify">Operating systems differ from user (i.e., application) programs in ways other than where they reside. In particular, they are huge, complex, and long-lived. The source code of the heart of an operating system like Linux or Windows is on the order of fiv e million lines of code or more. To conceive of what this means, think of printing out fiv e million lines in book form, with 50 lines per page and 1000 pages per volume (larger than this book). It would take 100 volumes to list an operating system of this size—essentially an entire bookcase. Can you imagine getting a job maintaining an operating system and on the first day having your boss bring you to a bookcase with the code and say: ‘‘Go learn that.’’ And this is only for the part that runs in the kernel. When essential shared libraries are included, Windows is well over 70 million lines of code or 10 to 20 bookcases. And this excludes basic application software (things like Windows Explorer, Windows Media Player, and so on).</p>

<p align = "justify">It should be clear now why operating systems live a long time—they are very hard to write, and having written one, the owner is loath to throw it out and start again. Instead, such systems evolve over long periods of time. Windows 95/98/Me was basically one operating system and Windows NT/2000/XP/Vista/Windows 7 is a different one. They look similar to the users because Microsoft made very sure that the user interface of Windows 2000/XP/Vista/Windows 7 was quite similar to that of the system it was replacing, mostly Windows 98. Nevertheless, there were very good reasons why Microsoft got rid of Windows 98. We will come to these when we study Windows in detail in Chap. 11</p>

<p align = "justify">Besides Windows, the other main example we will use throughout this book is UNIX and its variants and clones. It, too, has evolved over the years, with versions like System V, Solaris, and FreeBSD being derived from the original system, whereas Linux is a fresh code base, although very closely modeled on UNIX and highly compatible with it. We will use examples from UNIX throughout this book and look at Linux in detail in Chap. 10</p>

<p align = "justify">In this chapter we will briefly touch on a number of key aspects of operating systems, including what they are, their history, what kinds are around, some of the basic concepts, and their structure. We will come back to many of these important topics in later chapters in more detail.</p>