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

```bash
ping www.iancthompson.dev
```

- `ping` is the program we are running
- `www.iancthompson.dev` is the parameter `ping` will use to send packet requests to.

Now, in your terminal, you should recive output that looks similar to the following:

```bash
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

```bash
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

```bash
open .
```

`open` will attempt to open the folder or file in the same way as if you were to double-click it in Finder. The `.` tells the command to open the current _working directory_.

You should now see Finder open to the current working directory. You should be able to see all of the folders and files in Finder that you did when you ran the `ls` command.

### Changing Directories

The command line is no good if we can only work within the default working directory. So, we must be able to _change_ the current working directory.

You may assume that we could use the `open` command that we just learned.

**You try:** Try using the `open` command to open the Documents folder that is in your current working directory. Remember, we used the `.` to "open" the current working directory. To afflict commands on specific files or folders, we typically will state the command and _then_ state the file.

So then, the command could be: `open Documents`

What happens?

You will notice that the Documents folder is opened via Finder and not the terminal. If you were to run `pwd` you would see that it has not changed.

To change the current working directory of the command line, we will need a different command

#### The `cd` command

`cd` is the command that is used to change directories. To change into your desired directory:

```bash
cd PATH
```

- `cd` is the change directory command
- `PATH` is the directory or folder you wish to enter into

Thus, to change into the "Documents" directory, your command would look like:

```bash
cd Documents
```

Now, if you were to run `pwd`, you would see that the path to the working directory has now changed. Additionally, if you were to run the `ls` command, you would now see a list of all of teh files and directories within the Documents directory.

How do we go back a directory? To do this, we will add two periods to the end of the `cd` command. It would look like this: `cd ..`.

**Application question:** What would happen if we ran `cd .` ?

Knowing the `.` applies the command on the current working directory, `cd`ing on the `.` directory would not change the current working directory.

### Creating new directories and files

#### Creating new directories

To create a directory, we will use the `mkdir` command. It looks like this:

```bash
mkdir Folder
```

- `mkdir` is the command to make a new directory
- `Folder` specifies what the new directory will be called.

This new directory will be created in the current working directory.

`mkdir` **does not** change the current working directory. You will need to `cd` into the new directory you have just created

#### Creating new files

Suppose you wish to create a new file within the current working directory, but do not wish to edit it. To do this, you will use the `touch` command. It looks like this:

```bash
touch MyNewFile.txt
```

The command above will create a new .txt file called MyNewFile. It will not open it, nor will any text be added to it.

<!-- ##### Deeper Connections
If you want to edit this new file via the command line, you could use a program that is preinstalled on your Mac called `nano`.

If you have already created the file via `touch`, you could run:

```bash
nano MyNewFile.txt
```

You will notice the terminal change and open the in-terminal `nano` text editor. You can use this as you would a normal text editor, but you can only interact using keyboard and mouse.

Once you have started typing some text, you can save the text by typing `CTRL+X` to exit. Then,  -->

# Conclusion

By the end of this module, you should be able to understand what the command line is and how to execute basic system commands to change directories, list content of directories, create empty files, and make new directories.

In your web development journey, you will rely heavily on the command line, though you will likely do your basic text editing in a different application such as VSCode.

When you get into deploying your websites, installing packages to help you build great websites, or even using source control programs like `git`, you will need _at least_ a basic understanding of how to use the command line.

If this was a lot, do not worry. As with anything, the more you use the command line, thee more you will learn and become comfortable using it.

## Additional resrouces

- [Basic Unix Commands](https://www.unixtutorial.org/basic-unix-commands)
