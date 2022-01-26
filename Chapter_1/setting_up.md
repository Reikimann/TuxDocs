# Getting setup

Great! You got your freshly installed setup, now what?

Linux is a whole lot diffrent from more mainstream operating systems such as windows, first big thing is installing apps.

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


