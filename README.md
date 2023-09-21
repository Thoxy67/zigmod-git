# zigmod-git

This PKGBUILD allows you to easily install the latest development version of zigmod (Zig package manager).

## About Zigmod

Zigmod is a package manager for the Zig programming language. 

The following links provide information and resources related to zigmod :

- [Source](https://github.com/nektro/zigmod) :  The source code for the zigmod package manager, hosted on GitHub.

## Installation

1. Clone the `zls-git` repository from Github using the following command:

```
git clone https://github.com/Thoxy67/zigmod-git.git
```

2. Change your current working directory to the `zigmod-git` folder:

```
cd zigmod-git
```

3. You can now build and install the package via makepkg:

```
makepkg -si
```

After installation, you can start using Zig Language Server by running the `zigmod` command in your
terminal.

## Update

To update zls, run the `makepkg -si` script again. It will check for updates and
build the new PKGBUILD to proceed with the installation.

## License

This repository is licensed under the MIT License. For more information, see the
[LICENSE](LICENSE) file.
