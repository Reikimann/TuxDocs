# Getting Comfortable with the command line

Great! You got your freshly installed setup, now what?

Linux is a whole lot diffrent from more mainstream operating systems such as windows, first big thing that you need to get used to is installing apps.

Lets look at some terminal basics, when ever you see a symbol like `$` that symbolises a temrinal command, you dont want to include the `$`

The first things you should know is navigation within the terminal, here is a few examples

```bash
# Moving into a folder
$ cd Desktop
# cd meanning change directory

# List all avaliable files and folders in the current directory
$ ls

# Create a folder
$ mkdir <folder>

# Remove a file / folder, you need to use the second one if there are files in the folder
$ rm <file>
$ rm -r <folder>
```

The first time i was on a linux machine I went to the internet and downloaded the spotify installer as an exe. This is far from how it works, first thing i want to talk about is installing apps.

The methods we are talking about in this article are on `debian` and `arch`

## Debian (apt)

## Arch (pacman and yay)

On the arch system we mainly use the package manager `pacman` and `yay` for [AURs](https://wiki.archlinux.org/title/Arch_User_Repository), what is an AUR you say? Its what we call an Arch User Reposetory simply a method for downloading an app.

A few important commands to remember about pacman is:

```bash
$ pacman -Ss <package name>
```
This will search for a package, if youre looking for something like firefox etc

```bash
$ sudo pacman -S <package name>
```
Install the application youre looking for

```bash
$ sudo pacman -Rns <package name>
```
Removes a package

Obviusly this is a very breef description of the pacman package manager and so if you want to read more click [here](https://wiki.archlinux.org/title/Pacman)

The other way we can install a package is using something we call `yay`

Yay can install what we call [Arch User Reposetories](https://wiki.archlinux.org/title/Arch_User_Repository) these can be usefull when installing an app like spotify

Firstly with yay we will look at the installation process, unfortunately yay cannot be found using pacman and we need to install and build it ourselves

```bash
# We need these two packages to get started, git to download the project files and base-devel to compile
$ sudo pacman -S git
$ sudo pacman -S base-devel

# Now we can make a new folder, enter it and clone the files
$ git clone https://aur.archlinux.org/yay.git
$ cd yay

# Compiile the files
$ makepkg -si

# And now that we finished the install we can agein remove the installation files 
$ cd ..
$ rm -r yay
```

And thats how we succesfully can install yay

**WARNING: It is very important when we use yay to avoid using sudo, it will ask you for permission when it needs it**

```bash
$ yay -S <package name>
```
As you can see, yay acuallt uses the same [flags](technical_termonologies.md) as with pacman, so installing, searching and removing packages is the same

### A little task

Up for your first challange?

Try installing spotify using your command line

<details closed="closed">
  <summary>Solution [Spoilers]</summary>

  <p>We want to make sure that we have yay installed before starting</p>

  ```bash
  $ yay -S spotify
  ```

</details>

dev Note : https://dev.to/mattdark/installing-yay-on-arch-linux-1kgm

