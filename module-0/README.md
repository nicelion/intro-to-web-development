# Introduction to the Command Line

**Learning objective:** By the end of this module, you will

- Understand what the command line is
- What purpose thee command line serves
- Basic computer interaction using the command line
- Know how to execute basic system commands

## What is the command line?

The command line, specifically in the context of Unix-like operating systems, refers to a text-based interface that allows users to interact with their computer's operating system by entering commands directly into a terminal emulator. Unlike graphical user interfaces (GUIs) that rely on visual elements like windows and icons, the command line operates entirely through text commands.

In the Unix command line, users type commands using a specific syntax, consisting of a command followed by options and arguments. Commands can perform a wide range of tasks, including file management, system configuration, software installation, and more. Unix-like systems, such as Linux, macOS, and various Unix distributions, provide a powerful and efficient environment for both novice and advanced users to control their computers.

## Accessing the command line

To access the command line on a Mac, you will use the "Terminal" application. You can open this application by searching in your applications directory or by typing `CMD+SPACE` to open Spotlight and then typing in "Terminal".

Personally, I use a third party terminal interface called "iTerm2." It functions the _exact_ same way as the default terminal application, but offers a few more advanced features.

It is not necessary to download this application, but you are certainly welcome to.

Any images of the terminal throughout this demo will be using iTerm, so it may look slightly different

### Let's open up the command line!

As I previously described, go ahead and open up your terminal environment

You will be greeted with a blank terminal and are now ready to start entering commands.

![terminal](/img/terminal-default.png)
^ It should look something like this

### Running our first command

Again, to control or execute commands in the terminal, you simply type the command you wish to execute. There are a bunch of preinstalled programs that you can run.

The first program we will run is `ping`. `ping` will send packet requests to a server in which you specify.

To begin this program, type the following into your command line:

```
ping www.iancthompson.dev
```

- `ping` is the program we are running
- `www.iancthompson.dev` is the parameter `ping` will use to send packet requests to.

Now, in your terminal, you should recive output that looks similar to the following:

```
ping www.iancthompson.dev

PING cname.vercel-dns.com (76.76.21.98): 56 data bytes
64 bytes from 76.76.21.98: icmp_seq=0 ttl=245 time=25.358 ms
64 bytes from 76.76.21.98: icmp_seq=1 ttl=245 time=29.213 ms
64 bytes from 76.76.21.98: icmp_seq=2 ttl=245 time=30.086 ms
64 bytes from 76.76.21.98: icmp_seq=3 ttl=245 time=29.590 ms
64 bytes from 76.76.21.98: icmp_seq=4 ttl=245 time=26.307 ms
64 bytes from 76.76.21.98: icmp_seq=5 ttl=245 time=31.444 ms
64 bytes from 76.76.21.98: icmp_seq=6 ttl=245 time=33.076 ms
64 bytes from 76.76.21.98: icmp_seq=7 ttl=245 time=25.525 ms
64 bytes from 76.76.21.98: icmp_seq=8 ttl=245 time=103.213 ms
64 bytes from 76.76.21.98: icmp_seq=9 ttl=245 time=32.429 ms
64 bytes from 76.76.21.98: icmp_seq=10 ttl=245 time=27.516 ms
64 bytes from 76.76.21.98: icmp_seq=11 ttl=245 time=31.043 ms
^C
--- cname.vercel-dns.com ping statistics ---
12 packets transmitted, 12 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 25.358/35.400/103.213/20.597 ms
```

To kill the program, you will need to type `CTRL+C`. Any program that does not self-exit will need to be terminated this way.

Congratulations, you have just run your first program via command line!

## Exploring the file system via command line

Your entire file system is accessible through the command line. Again, there are no point-and-click interfaces as we are using the command line, so we will need to learn all the commands used to navigate the file system.

### Current Working Directory

First, we need to determine our current _working directory_, or where in the filesystem the command line is currently operating.

To find our current working directory, simply type the command `pwd`. You will recieve output that looks something like:

```
pwd

/Users/[USERNAME]
```

- [USERNAME] will be the username of the current account in which you are logged into your computer with. Typically this is your name. If you are on a Mac, this user name was created when you first set up your Mac.

Again, this shows us the path to the current _folder_ in which the terminal is working in.

### Seeing What's Inside the Current Working Directory

Now that we know what the current working directory is, we now need to see what exactly is inside of it. The command for this is `ls`. Now, type `ls` into the command line and hit enter.

`ls` will list all of the contents inside the current working directory. It will look something like this:

![ls](/img/ls.png)

Now, you can see all of the files and folders that exist within your current working directory.

#### Deeper Connection

So that you may form a deeper connection of where exactly you are in the filesystem, run the following command in the command line:

```
open .
```

`open` will attempt to open the folder or file in the same way as if you were to double-click it in Finder. The `.` tells the command to open the current _working directory_.

You should now see Finder open to the current working directory. You should be able to see all of the folders and files in Finder that you did when you ran the `ls` command.
