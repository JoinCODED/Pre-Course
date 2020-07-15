### Topics to discuss:

- Navigating the file system in the Terminal.
- Creating a new directory.
- Command structure.

The Terminal is a tool you'll be using constantly throughout your life as a developer. You can't do without it. So here you'll learn about the basic usage of the Terminal, and get some practice in.

# Step 1: Git Bash for Windows

_Windows_ has a separate command line language from _Mac/Linux_. So to be able to use the same commands as the instructor will, download **Git Bash**.

Download the [64-bit version of Git Bash for Windows here](https://github.com/git-for-windows/git/releases/download/v2.26.2.windows.1/Git-2.26.2-64-bit.exe)

**_When it Prompts you to adjust your PATH environment you should pick the 3rd option\
`Use Git and optional Unix tools from the Windows Command Prompt`_**

# Step 2: Navigating the file system

We usually use the Finder app or another file explorer application to open our files and folders. But you can do the same thing (and more) using the Terminal.

## Finder Folders

Let's go through an example scenario using the Finder app:

1. Open Finder
2. See there's an example folder with name "MyProjects"
3. "Go into" the folder
4. Now we are _inside_ the folder.

## Folders are directories

Let's do the same thing using the Terminal:

1. Open the Terminal
2. See the files and folders we have

   ```bash
   $ ls
   ```

   This `$` is not part of the command, it's only tot indicate that this line is a Terminal command.

3. Go into the `MyProjects/` directory

   ```bash
   $ cd MyProjects
   ```

4. New we are _inside_ the directory.
5. See what files and folders there are inside

   ```bash
   $ ls
   ```

## Going back one step: `..`

How do we go _out_ of a directory we're in? Wherever you are, you can always run the following command to **exit** the current directory you're in:

```bash
$ cd ..
```

The `..` means _one directory out_.

## Why would we use the Terminal?

It's a powerful and convenient tool for developers. With experience, you'll learn to fully appreciate it.

For now, just try to get used to using it.

Here's a list of the Terminal commands we just used:

- `ls`: Lists files and directories.
- `cd`: Changes directory. Example: `cd MyProjects` to go into the `MyProjects` directory.
- `cd ..`: Exiting current directory.

---

### **Task**: Take 5 minutes to explore these commands and navigate the directories in your computer.

---

# Step 3: New Directory

Using the Finder app, you can create a new directory by right-clicking and picking "New Folder". Let's see how we can do that in the Terminal. Inside "MyProjects":

1. Create a new directory with the name "NewWebsite"

   ```bash
   $ mkdir NewWebsite
   ```

2. Navigate into the new directory

   ```bash
   $ cd NewWebsite
   ```

3. Verify that you're now inside the new directory

   ```bash
   $ pwd
   ```

   `pwd` is short for _`p`rint `w`orking `d`irectory_. It displays your current location in the computer file system. We can use it to make sure we are where we expect to be.

## Directory within a directory **(+ Command History)**

We can also create a directory within a directory, and can keep nesting folders like this indefinitely.

1. Move into `NewWebsite/`

   ```bash
   $ cd NewWebsite
   ```

2. Create a new folder named `ExampleSite`

   ```bash
   $ mkdir ExampleSite
   ```

3. Hit up-arrow three times to run `pwd`. This'll show us the previous commands we ran, so we don't have to type them everytime.

---

## Task (10 min)

1. Use this [Terminal Cheat Sheet](https://github.com/0nn0/terminal-mac-cheatsheet#english-version) and explore the Terminal.
2. Create a directory called "Development" either in your home directory (mac/linux) or in your Desktop (windows). You'll put all your work in the bootcamp in this Development directory.

---

# Step 4: Command Structure

Terminal command follow a certain structure. Let's take a moment to dissect and understand it.

## Command: `ls`

This command will allow us to see the files and folders in the current working directory.

The first "word" in the terminal command is the name of the command to be executed. So with this command, you just type the name of the command, `ls`, and hit enter. There's nothing more to it.

## Another Command: `ls Development`

This command will allow us to see the files and folders inside the `Development/` directory.

The second "word" is the first _argument_ in the command. Every word after is another argument given to the command being executed. So here, `Development` is a **command argument**.

## One Last Command: `mkdir example1 example2`

This command will create a folder called `example1` and another folder called `example2`.

`mkdir` is the name of the command, `example1` is the _first_ argument, `example2` is the _second_ argument.

# List of Commands

Here's a list of the commands we used today, that you'll likely use often:

- `ls`: Lists files and folders in the current working directory.
- `cd`: Changes the current working directory.
- `pwd`: Shows the location of the current working directory.
- `mkdir`: Create a new directory.
