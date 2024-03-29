- Introduction
   - [Difference between Github CLI and Git on the command line](#diff)
   - [Why use Github CLI ?](#why)
   - [How to install Github CLI ?](#how)
   - [Configuration](#conf)
- [CheatSheet](./README.md)
- [Installation](./installCLI.md)
- [Uses](./Use.md)

# Introduction to GitHub CLI

GitHub CLI is a command-line tool meant to help you use github directly from your terminal. With CLI you can use every feature available on github, but faster and more efficiently. CLI helps you stay on track and avoiding context switching (loss of focus).


### <a id=diff></a>*What's the difference between GitHub CLI and Git on the command line ?*

The Github command line interface (github CLI) allows you to work with a local or remote repository. The remote repository may be hosted on GitHub or it may be hosted by another service.

GitHub CLI (gh) is specifically designed to work with GitHub. It allows the use of the command line to interact with GitHub in many ways. CLI includes features such as:

- View, create, clone, and fork repositories

- Create, close, edit, and view issues and pull requests

- Review, diff, and merge pull requests

- Run, view, and list workflows
    
### <a id=why></a>*Why use Github CLI ?*

   **Increased productivity**: complete common tasks using less commands and without quitting your terminal.

   **Made specifically for GitHub**: Interact with nearly every features in github

**Customisation and extensions**: Extend CLI functionnality with aliases for custom commands.

## <a id=how></a>How to install Github CLI ?

**Windows**

With Scoop ```scoop  install gh```

With Chocolatey ```choco  install gh```

Manual installation

```Download the .msi file from the releases page of GitHub CLI, launch it and follow the instructions.```

**MacOS**

with Homebrew ```brew install gh```

with MacPorts

- ```Download the.pkg file file from the releases page of GitHub CLI, launch it and follow the instructions```

- ```sudo port install gh```

---
**Linux**

In Debian/Ubuntu (et dérivés)

with apt 
- ```sudo apt update```

- ```sudo apt install gh```

---
In Fedora avec dnf 
    
```sudo dnf install gh```

---
In CentOS 

with yum 

```sudo yum install gh```

---
In Arch Linux 

with pacman

- ```Download the .tar.gz file from the releases page of GitHub CLI, launch it and follow the instructions.```

- ```sudo pacman -S github-cli```

### Checking for installation

```gh --version```    


## <a id=conf></a>Configuration
GitHub Authentication

To connect to your Github account through the commande line, use the following command :

```gh auth login```

Follow the instructions on screen to authenticate.

**Code Editor Configuration**

 To set your editor for command line-operations, use the command:

```gh config set editor``` 

followed by your editor's name

```gh config set editor code```

Alias

To declare aliases for commands you use frequently, use the command:

```gh alias set```

For example if you want to create an alias for the command **gh repo create**
You can do so using :

```gh alias set create-repo `____```