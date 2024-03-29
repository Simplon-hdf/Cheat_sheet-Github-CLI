## Table des matières

- [Intoduction](./Intro_CLI_fr.md)
- [CheatSheet](./Cheat_sheet_fr.md)
- [Installation](./installCLI_fr.md)
- BaseUse
    - [Authentification](#auth)
    - [Gestion des dépôt](#repo)
    - [Gestion des issues](#issues)
    - [Gestion des pull requests](#pr)
    - [Gestion des workflows](#workflows)





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

<img src="../assets/Use_img/Auth_exemple.png" alt="Auth_exemple" width="" >

<br>
Vous pouvez entrer cette commande <code>gh auth logout</code> pour vous déconnecter.

### <a id=repo></a> **Gestion des dépôts** :

Entrer <code> gh repo create </code> pour créer un dépot distant.<br>
``` gh repo create ``` : créer un dépot 

<img src="../assets/Use_img/Gh_repo_create.png" alt="Gh_repo_create">  

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

![Repo Fork](../assets/Use_img/Gh_fork.png) 

**Exemple pour** : ```gh repo fork cli/cli``` : un drapeau pour fork et cloner directement
![Repo Fork & Clone](../assets/Use_img/Repo_Fork_&_Clone.png)

**Exemple pour** : ```gh repo clone``` 
![Repo Clone](../assets/Use_img/Repo_Clone.png)


  Options | Description
  --- | ---
  ``` -b ```,``` --branch <string>``` | regarder une branche spécifique du dépôt
  ``` -w ```,``` --web``` | Ouvrir le dépôt dans le navigateur
<br>

### <a id=issues></a> **Gestion des issues**

  - ```gh issue create [flag]``` : créer une issue

  Options | Description
  --- | ---
  ```-t```, ```title <string>```| Fournie un titre
  ```-l```, ```label <name>``` | ajoute des étiquettes par nom
  ```-a```, ```assignee <login>``` | Attribue une personne a partir de son identifiant? utiliser "@me" pour m'assigner moi même

  **Exemple pour** : ``` gh issue create ``` : 

  ![gh_Issue_Create_ex](../assets/Use_img/Issue_Create.png)

  **Exemple pour** : ``` gh issue create [flags] ``` : 

  ![gh_issue_Create_with_flags_ex](../assets/Use_img/gh_issue_create_flag.png)

  - ```gh issue list [flag]```: Listes les issues

  Options | Description
  --- | ---
  ```-a```, ``` --assignee <string>``` | Filtre par assignation
  ```-A```, ``` --author <string>``` | Filtre par auteur
  ```-s```, ``` --state <string> (default "open")``` | Filtre par état: {ouvert\|fermer\|tout}
  ```-l```, ``` --label <strings>``` | Filtre par étiquettes

  **Exemple pour** : ``` gh issue list ``` :

  ![gh_issue_list](../assets/Use_img/gh_issue_list_ex.png)

  **Exemple pour** : ``` gh issue list [flags] ``` :

  ![gh_issue_list_with flag](../assets/Use_img/gh_issue_list.png)

  - ```gh issue status``` : Affiche l'état des issues pertinents
  ```gh issue view {<number> | ur>} [flags]``` : Montre les issues spécifiques

  Options | Description
  --- | ---
  ```-c```,```--comments``` | Montre les commentaires du problèmes

  **Exemple pour** : ```gh issue status``` :

  ![gh_issue_status](../assets/Use_img/gh_Issue_status.png)

  ```issue close {<number> | <url>} [flags]``` : Ferme l'issue

  Options | Description
  ---| ---
  ```-c```, ``` --comment <string> ``` | Laisser un commentaire de clôture
  ```-r```, ``` --reason <string>``` | la raison de la fermeture

  <br>

### <a id=pr></a>**Gestion des pulls requests**

  - ```gh pr create [flags] ```: Créer une pull request

  Options | Description
  --- | ---
  ```-B```, ``` --base <branch>``` | La branche dans la qu'elle vous-voulez fusionner
  ```-f```, ``` --fill ``` | Utilise les infos du commit pour le titre et le corps
  ```-l```, ``` --label <name> ``` | Ajoute des étiquettes par nom

  **Exemple pour** : ``` gh pr create```: 

  ![Pr_create](../assets/Use_img/Pr_Create.png)

  **Exemple pour** : ``` gh pr create [flag] ```:

  ![Pr_create_flag](../assets/Use_img/Pr_create_flag.png)

  - ```gh pr list [flags]``` : Liste les pulls requests

  Options | Description 
  --- | ---
  ```-a ```,```--assignee <string>``` | Filtre par assignation
  ```-A```, ``` -- author <string> ``` | Filtre par auteur
  ```-s```, ```--state <string> (default "open")``` | Filtre par état : {ouvert\|fermé\|fusionné\|tout}
  ```-l```,```--label <strings>``` | Filtre par étiquettes

  **Exemple pour** : ```gh pr list ```: 

  ![gh_pr_list](../assets/Use_img/gh_pr_list.png)

  **Exemple pour** : ```gh pr list [flag]``` :

  ![gh_pr_list_flag](../assets/Use_img/gh_pr_list_flag.png)

  - ```gh pr status``` : Affiche l'état des pulls requests relevé
  - ```gh pr view {<number> | <url> | <branch>} [flags]``` : Montre les pulls request spécifique

  Options | Description
  --- | ---
  ```-c```,```--comment <string>``` | Laisse un commentaire de réouverture

  **Exemple pour** : ```gh pr status``` :

  ![gh_pr_status](../assets/Use_img/gh_pr_status.png)

  **Exemple pour** : ```gh pr view ``` : 

  ![gh_pr_view](../assets/Use_img/gh_pr_view.png)

  **Exemple pour** : ```gh pr view <number> ```:<br> mais on peut utiliser d'autre arguments comme "Url" et "branch".

  ![gh_or_view_number](../assets/Use_img/gh_pr_view_number.png)

### <a id=workflows></a>**Gestion du workflow**

  - ```gh workflow list [flag]``` : Listé les fichiers du workflow, les workflow ne sont pas caché par défaut

  Options | Descripstion
  --- | ---
  ```-a```, ```--all``` | Inclure la désactivation des workflow

  - ```gh workflow view [<workflow-id> | <workflow-name | <filename>] [flags]```: Voir le résumé des Workflow
  - ```gh workflow run [<workflow-id> | <workflow-name>]``` : execute le workflow
  - ```gh workflow enable [<workflow-id> | <workflow-name>]``` : Active le workflow, lui permettant de fonctionner
  - ```gh workflow disable [<workflow-id> | <workflow-name>]``` : Désactiver le workflow, l'empêchant de fonctionner

  **Exemple pour** : ```gh workflow run [flag]``` :

  ![gh_workflow_run_flag](../assets/Use_img/gh_workflow_run_flag.png)