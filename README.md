# GitHub CLI

<p align="center"><img src ="assets/ghcli.png"/></p>

## Table of contents

- [Intoduction](./Intro_CLI_eng)
- CheatSheet
    - [Authentication](#auth)
    - [Managing repositories](#repo)
    - [Managing issues](#issues)
    - [Managing pull requests](#pr)
    - [Managing workflows](#workflows)
- [Installation](./installCLI.md)
- [Uses](./Use.md)

# Cheat-sheet of ```gh``` commands

### <a id=auth></a>**authentication**

- ```gh auth login``` : Connect to a github account <br>
- ```gh auth logout``` : Remove authentication for a github account

### <a id=repo></a>**Managing repositories**

- ```gh repo create [<name>] [flags]``` : Create a repository

    Options | Description 
    --- | --- 
    ```-p```, ``` --template <repository>``` | Make the new repository based on a template repository
    ```-t```, ``` --team <name>``` | The name of the organization team to be granted access
    ```-c```, ``` --clone``` | Clone the new repository to the current directory
<br>

- ```gh repo fork [<repository>] [flags]``` : Fork a repository
- ```gh repo clone <repository> [<directory>]``` : Clone a repository
- ```gh repo view [<repository>] [flags]``` : View a repository

    Options | Description 
    --- | --- 
    ```-b```, ``` --branch <string>``` | View a specific branch of the repository
    ```-w```, ``` --web``` | Open a repository in the browser
<br>

### <a id=issues></a>**Managing issues**

- ```gh issue create [flags]``` : Create an issue

    Options | Description 
    --- | --- 
    ```-t```, ``` --title <string>``` | Supply a title
    ```-l```, ``` --label <name>``` | Add labels by name
    ```-a```, ``` --assignee <login>``` | Assign people by their login. Use "@me" to self-assign
<br>

- ```gh issue list [flags]``` : List issues

    Options | Description 
    --- | --- 
    ```-a```, ``` --assignee <string>``` | Filter by assignee
    ```-A```, ``` --author <string>``` | Filter by author
    ```-s```, ``` --state <string> (default "open")``` | Filter by state: {open\|closed\|all}
    ```-l```, ``` --label <strings>``` | Filter by label
<br>

- ```gh issue status``` : Show status of relevant issues
- ```gh issue view {<number> | <url>} [flags]``` : View a specific issue
    Options | Description 
    --- | --- 
    ```-c```, ``` --comments``` | View issue comments
<br>

- ```gh issue close {<number> | <url>} [flags]``` : Close issue
    Options | Description 
    --- | --- 
    ```-c```, ``` --comment <string>``` | Leave a closing comment
    ```-r```, ``` --reason <string>``` | Reason for closing
<br>

- ```gh issue reopen {<number> | <url>} [flags]``` : Reopen an issue
    Options | Description 
    --- | --- 
    ```-c```, ``` --comment <string>``` | Leave a reopening comment
<br>

### <a id=pr></a>**Managing pull requests**

- ```gh pr create [flags]``` : Create an pull request

    Options | Description 
    --- | --- 
    ```-B```, ``` --base <branch>``` | The branch into which you want your code merged
    ```-f```, ``` --fill``` | Use commit info for title and body
    ```-l```, ``` --label <name>``` | Add labels by name
<br>

- ```gh pr list [flags]``` : List pull request

    Options | Description 
    --- | --- 
    ```-a```, ``` --assignee <string>``` | Filter by assignee
    ```-A```, ``` --author <string>``` | Filter by author
    ```-s```, ``` --state <string> (default "open")``` | Filter by state: {open\|closed\|merged\|all}
    ```-l```, ``` --label <strings>``` | Filter by label
<br>

- ```gh pr status``` : Show status of relevant pull request
- ```gh pr view {<number> | <url> | <branch>} [flags]``` : View a specific pull request
    Options | Description 
    --- | --- 
    ```-c```, ``` --comments``` | View pull request comments
<br>

- ```gh pr checkout {<number> | <url> | <branch>}``` : Check out a pull request
- ```gh pr merge {<number> | <url> | <branch>}``` : Merge a pull request
- ```gh pr diff {<number> | <url> | <branch>} [flags]``` : View changes in a pull request

- ```gh pr close {<number> | <url> | <branch>} [flags]``` : Close pull request
    Options | Description 
    --- | --- 
    ```-c```, ``` --comment <string>``` | Leave a closing comment
    ```-d```, ``` --delete-branch``` | Delete the local and remote branch after close
<br>

- ```gh pr reopen {<number> | <url> | <branch>} [flags]``` : Reopen a pull request
    Options | Description 
    --- | --- 
    ```-c```, ``` --comment <string>``` | Leave a reopening comment
<br>

### <a id=workflows></a>**Managing workflows**

- ```gh workflow list [flags]``` : List workflow files, hiding disabled workflows by default

    Options | Description 
    --- | --- 
    ```-a```, ``` --all``` | Include disabled workflows

-```gh workflow view [<workflow-id> | <workflow-name> | <filename>] [flags]``` : View the summary of a workflow
- ```gh workflow run [<workflow-id> | <workflow-name>]``` : execute a workflow
- ```gh workflow enable [<workflow-id> | <workflow-name>]``` : Enable a workflow, allowing it to be run
- ```gh workflow disable [<workflow-id> | <workflow-name>]``` : Disable a workflow, preventing it from running 
<br>