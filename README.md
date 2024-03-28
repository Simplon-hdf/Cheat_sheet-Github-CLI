# GitHub CLI

<p align="center"><img src ="assets/ghcli.png"/></p>

# Cheat-sheet of ```gh``` commands

### **authentication**

- ```gh auth login``` : Connect to a github account <br>
- ```gh auth logout``` : Remove authentication for a github account

### **Managing repositories**

- ```gh repo create [<name>] [flags]``` : Create a repository

    Options | effect 
    --- | --- 
    ```-p, --template <repository>``` | Make the new repository based on a template repository
    ```-t, --team <name>``` | The name of the organization team to be granted access
    ```-c, --clone``` | Clone the new repository to the current directory
<br>

- ```gh repo fork [<repository>] [flags]``` : Fork a repository
- ```gh repo clone <repository> [<directory>]``` : Clone a repository
- ```gh repo view [<repository>] [flags]``` : View a repository

    Options | effect 
    --- | --- 
    ```-b, --branch <string>``` | View a specific branch of the repository
    ```-w, --web``` | Open a repository in the browser
<br>