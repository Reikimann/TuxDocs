# Getting Comfortable with the command line

Great! You got your freshly installed setup, now what?

Linux is a whole lot different from more mainstream operating systems such as windows, first big thing that you need to get used to is installing apps.

Lets look at some terminal basics, when ever you see a symbol like `$` that symbolizes a terminal command, you don't want to include the `$`

The first things you should know is navigation within the terminal, here is a few examples

```bash
# Moving into a folder
$ cd Desktop # cd means change directory

# List files and folders in the current directory
$ ls

# Create a folder
$ mkdir <folder> # mkdir means make directory

# Remove a file/folder. You need to use the second one if there are files in the folder
$ rm <file>
$ rm -r <folder> # -r means recursively 
```

## Installing packages

Now, in Windows when you want to install something, you typically open your browser, locates what you want to download and download it.
This is far from how it works on linux. Packages on linux are installed like the apps on our phones. From one place. Through a package manager in the terminal.

Depending on how your system is set up, the method may vary. We will be covering package installation for the Debian- and Arch-based systems.

### Debian (apt)

### Arch (pacman and yay)

On the Arch system we mainly use the package manager "pacman" for official packages and "yay" for [AURs](https://wiki.archlinux.org/title/Arch_User_Repository), what is an AUR you say? Its what we call the Arch User Repository, which is a community-driven repository for Arch users.

Now, a few important terminal commands to remember for managing packages on your system:

```bash
$ pacman -Ss <package name> # Searches for a packages in the database, searches both in packages' names and descriptions
```

```bash
$ sudo pacman -S <package name(s)> # Installs the package(s) 
```

```bash
$ sudo pacman -Rns <package name(s)> # Removes package(s), prevents backups and dependencies which are no longer needed
```

Obviously this is a very brief description of the pacman package manager, so if you want to read more click [here](https://wiki.archlinux.org/title/Pacman).

If we want to install a package which is not in the official repositories, we can look for them in the AUR.
To do this we need an AUR helper and the most used is [Yay](https://github.com/Jguer/yay).

Firstly we will look at the installation process for yay. Unfortunately yay is not in the official repositories and we need to install and build it from [source](technical_terminologies.md) ourselves.

```bash
# We need two packages to get started, git to download the project files and base-devel to compile.
# Base-devel contains tools required to build many packages.
$ sudo pacman -S git base-devel

# Now we can make a new folder, enter it and clone the files
$ git clone https://aur.archlinux.org/yay.git
$ cd yay

$ makepkg -si # [Compiles](technical_terminologies.md) the files.

# And now that we finished the install, we can remove the installation files again.
$ cd ..
$ rm -r yay
```

And thats how we successfully can install yay.

**WARNING: It is very important to not give yay [sudo privileges](technical_terminologies.md), when installing packages, it will ask you for permission when it needs it.**

Now, when installing packages with yay, the [flags](technical_termonologies.md) used a pretty much the same as pacman's.

```bash
$ yay -S <package name>
```

<details closed="closed">
  <summary>A little task to see if you installed yay correctly.</summary>

  <p>We want to make sure that we have yay correctly installed before starting.</p>

  ```bash
  $ yay -S asciiquarium-git # A small fun ascii art aquarium.
  $ asciiquarium # Runs the program and press q to quit.
  ```

</details>

Dev-note: https://dev.to/mattdark/installing-yay-on-arch-linux-1kgm
