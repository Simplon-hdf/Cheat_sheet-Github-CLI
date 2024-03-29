## Table des matières

- [Intoduction](./Intro_CLI_fr)
- [CheatSheet](./Cheat_sheet_fr.md)
- [Installation](./installCLI_fr.md)
- BaseUse
    - [Authentication](#auth)
    - [Managing repositories](#repo)
    - [Managing issues](#issues)
    - [Managing pull requests](#pr)
    - [Managing workflows](#workflows)





  # **Utilisation basique de GitHub CLI**

GitHub CLI (**gh**) et un outil de ligne de commande qui apporte les fonctionnalité de GitHub dans le terminal.<br>Ce fonctionnement de GitHub fonctionne sans interagir avec l'interface graphique et permet de rester concentré sur le terminal.

## command de base de GitHub CLI

### <a id=auth></a> **Authentification :**

Entré <code>gh auth login</code> et suivre le prompts pour se connecter en utilisant notre identifiant GitHub.

```
gh auth login <flag>
```


  Options  |  Description 
  ---| ---
```gh auth login --hostname github.example.com --web```| S'authentifier sans commande supplémentaire 

<img src="assets/Use_img/Auth_exemple.png" alt="Auth_exemple" width="" >

<br>
Vous pouvez entrer cette commande <code>gh auth logout</code> pour vous déconnecter.

### <a id=repo></a> **Managing Repository :**

Entrer <code> gh repo create </code> pour créer un dépot distant.<br>
``` gh repo create ``` : créer un dépot 

<img src="assets/Use_img/Gh_repo_create.png" alt="Gh_repo_create">  

  Options | Description
  --- | ---
  ```-p```,```--template <repository>```|Faire que le nouveau dépôt sois basé sur ce template.
  ```-t```,```team <name>```| Le nom de l'organisation pour lui permettre d'avoir les accès.
  ```-c```,```--clone```| Clone le nouveau dépôt dans le chemin actuel. 
<br>

+ ```gh repo fork [<repository>] [flag]``` : pour Fork un dépôt
+ ```gh repo clone [<repository>] [<directory>]``` : Clone un dépôt
+ ```gh repo view [<repository>] [flag]``` : regarder un dépôt

**Exemple pour** : ```gh repo fork```

![Repo Fork](assets/Use_img/Gh_fork.png) 

**Exemple pour** : ```gh repo fork cli/cli``` : un drapeau pour fork et cloner directement
![Repo Fork & Clone](assets/Use_img/Repo_Fork_&_Clone.png)

**Exemple pour** : ```gh repo clone``` 
![Repo Clone](assets/Use_img/Repo_Clone.png)


  Options | Description
  --- | ---
  ``` -b ```,``` --branch <string>``` | regarder une branche spécifique du dépôt
  ``` -w ```,``` --web``` | Ouvrir le dépôt dans le navigateur
<br>

### <a id=issues></a> **Gestion des problèmes**

  - ```gh issue create [flag]``` : créer un problème

  Options | Description
  --- | ---
  ```-t```, ```title <string>```| Fournie un titre
  ```-l```, ```label <name>``` | ajoute des étiquettes par nom
  ```-a```, ```assignee <login>``` | Attribue une personne a partir de son identifiant? utiliser "@me" pour m'assigner moi même

  **Exemple pour** : ``` gh issue create ``` : 

  ![gh_Issue_Create_ex](assets/Use_img/Issue_Create.png)

  **Exemple pour** : ``` gh issue create [flags] ``` : 

  ![gh_issue_Create_with_flags_ex](assets/Use_img/gh_issue_create_flag.png)

  - ```gh issue list [flag]```: Listes les problèmes

  Options | Description
  --- | ---
  ```-a```, ``` --assignee <string>``` | Filter by assignee
  ```-A```, ``` --author <string>``` | Filter by author
  ```-s```, ``` --state <string> (default "open")``` | Filter by state: {open\|closed\|all}
  ```-l```, ``` --label <strings>``` | Filter by label

  **Example for** : ``` gh issue list ``` :

  ![gh_issue_list](assets/Use_img/gh_issue_list_ex.png)

  **Example for** : ``` gh issue list [flags] ``` :

  ![gh_issue_list_with flag](assets/Use_img/gh_issue_list.png)

  - ```gh issue status``` : Show status of relevant issues
  ```gh issue view {<number> | ur>} [flags]``` : view a specific issue

  Options | Description
  --- | ---
  ```-c```,```--comments``` | View issue comments

  **Example for** : ```gh issue status``` :

  ![gh_issue_status](assets/Use_img/gh_Issue_status.png)

  ```issue close {<number> | <url>} [flags]``` : Close issue

  Options | Description
  ---| ---
  ```-c```, ``` --comment <string> ``` | Leave a closing comment
  ```-r```, ``` --reason <string>``` | Reason for closing

  <br>

### <a id=pr></a>**Managing pull requests**

  - ```gh pr create [flags] ```: create a pull request

  Options | Description
  --- | ---
  ```-B```, ``` --base <branch>``` | The branch into which you want your code merged.
  ```-f```, ``` --fill ``` | Use commit info for title and body 
  ```-l```, ``` --label <name> ``` | add labels by name

  **Example for** : ``` gh pr create```: 

  ![Pr_create](assets/Use_img/Pr_Create.png)

  **Example for** : ``` gh pr create [flag] ```:

  ![Pr_create_flag](assets/Use_img/Pr_create_flag.png)

  - ```gh pr list [flags]``` : List pull request

  Options | Description 
  --- | ---
  ```-a ```,```--assignee <string>``` | Filter by assigne
  ```-A```, ``` -- author <string> ``` | Filter by author
  ```-s```, ```--state <string> (default "open")``` | Filter by state : {open\|closed\|merged\|all}
  ```-l```,```--label <strings>``` | Filter by label

  **Example for** : ```gh pr list ```: 

  ![gh_pr_list](assets/Use_img/gh_pr_list.png)

  **Example for** : ```gh pr list [flag]``` :

  ![gh_pr_list_flag](assets/Use_img/gh_pr_list_flag.png)

  - ```gh pr status``` : Show status of relevant pull request
  - ```gh pr view {<number> | <url> | <branch>} [flags]``` : View a specific pull request

  Options | Description
  --- | ---
  ```-c```,```--comment <string>``` | Leave a reopening comment

  **Example for** : ```gh pr status``` :

  ![gh_pr_status](assets/Use_img/gh_pr_status.png)

  **Example for** : ```gh pr view ``` : 

  ![gh_pr_view](assets/Use_img/gh_pr_view.png)

  **Example for** : ```gh pr view <number> ```:<br> but we can add other arguments like "Url" and "branch".

  ![gh_or_view_number](assets/Use_img/gh_pr_view_number.png)

### <a id=workflows></a>**Managing workflows**

  - ```gh workflow list [flag]``` : List workflow files, hiding disabled workflows by default

  Options | Descripstion
  --- | ---
  ```-a```, ```--all``` | Include disabled workflows

  - ```gh workflow view [<workflow-id> | <workflow-name | <filename>] [flags]```: View the summary of a workflow
  - ```gh workflow run [<workflow-id> | <workflow-name>]``` : execute a workflow
  - ```gh workflow enable [<workflow-id> | <workflow-name>]``` : Enable a workflow, allowing it to be run
  - ```gh workflow disable [<workflow-id> | <workflow-name>]``` : Disable a workflow, preventing it from running

  **Example for** : ```gh workflow run [flag]``` :

  ![gh_workflow_run_flag](assets/Use_img/gh_workflow_run_flag.png)