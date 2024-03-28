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

### **Managing issues**

- ```gh issue create [flags]``` : Create an issue

    Options | effect 
    --- | --- 
    ```-t, --title <string>``` | Supply a title
    ```-l, --label <name>``` | Add labels by name
    ```-a, --assignee <login>``` | Assign people by their login. Use "@me" to self-assign
<br>

- ```gh issue list [flags]``` : List issues

    Options | effect 
    --- | --- 
    ```-a, --assignee <string>``` | Filter by assignee
    ```-A, --author <string>``` | Filter by author
    ```-s, --state <string> (default "open")``` | Filter by state: {open\|closed\|all}
    ```-l, --label <strings>``` | Filter by label
<br>

- ```gh issue status``` : Show status of relevant issues
- ```gh issue view {<number> | <url>} [flags]``` : View a specific issue
    Options | effect 
    --- | --- 
    ```-c, --comments``` | View issue comments
<br>

- ```gh issue close {<number> | <url>} [flags]``` : Close issue
    Options | effect 
    --- | --- 
    ```-c, --comment <string>``` | Leave a closing comment
    ```-r, --reason <string>``` | Reason for closing
<br>

- ```gh issue reopen {<number> | <url>} [flags]``` : Reopen an issue
    Options | effect 
    --- | --- 
    ```-c, --comment <string>``` | Leave a reopening comment
<br>