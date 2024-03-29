# GitHub CLI

<p align="center"><img src ="../assets/ghcli.png"/></p>

## Table des matières

- [Intoduction](./Intro_CLI_fr)
- CheatSheet
    - [Authentfication](#auth)
    - [Gestion des dépôt](#depo)
    - [Gestion des issues](#issues)
    - [Gestion des pull requests](#pr)
    - [Gestion des workflows](#workflows)
- [Installation](./installCLI.md)
- [Uses](./Use.md)

# Cheat-sheet des commandes ```gh```

### <a id=auth></a>**authentification**

- ```gh auth login``` : Se connecter à un compte GitHub 
- ```gh auth logout``` : Retirer l'authentification à un compte GitHub

### <a id=depo></a>**Gestion des dépôt**

- ```gh repo create [<name>] [flags]``` : Créer un dépôt

    Options | Description 
    --- | --- 
    ```-p```, ``` --template <repository>``` | Baser le dépôt sur une template
    ```-t```, ``` --team <name>``` | Autoriser l'accès à un groupe ou une organisation
    ```-c```, ``` --clone``` | Cloner le dépôt dans le dossier courant
<br>

- ```gh repo fork [<repository>] [flags]``` : Fork un dépôt
- ```gh repo clone <repository> [<directory>]``` : Cloner un dépôt
- ```gh repo view [<repository>] [flags]``` : Voir un dépôt

    Options | Description 
    --- | --- 
    ```-b```, ``` --branch <string>``` | Voir une branche du dépôt
    ```-w```, ``` --web``` | Ouvrir un dépôt dans l'explorateur web
<br>

### <a id=issues></a>**Gestion des issues**

- ```gh issue create [flags]``` : Créer une issue

    Options | Description 
    --- | --- 
    ```-t```, ``` --title <string>``` | Donner un titre
    ```-l```, ``` --label <name>``` | Ajouter un label par nom
    ```-a```, ``` --assignee <login>``` | Assigner quelqun par leur login. Utiliser "@me" pour l'assigner à soit même
<br>

- ```gh issue list [flags]``` : Lister les issues

    Options | Description 
    --- | --- 
    ```-a```, ``` --assignee <string>``` | Filtrer par personne assignée
    ```-A```, ``` --author <string>``` | Filtrer par auteur
    ```-s```, ``` --state <string> (default "open")``` | Filtrer par statut: {open\|closed\|all}
    ```-l```, ``` --label <strings>``` | Filtrer par label
<br>

- ```gh issue status``` : Afficher le status des issues qui te concerne
- ```gh issue view {<number> | <url>} [flags]``` : Voir une issue spécifique
    Options | Description 
    --- | --- 
    ```-c```, ``` --comments``` | Voir les commentaires d'une issue
<br>

- ```gh issue close {<number> | <url>} [flags]``` : Fermer une issue
    Options | Description 
    --- | --- 
    ```-c```, ``` --comment <string>``` | laisser un commentaire de clôture
    ```-r```, ``` --reason <string>``` | Raison de la clôture
<br>

- ```gh issue reopen {<number> | <url>} [flags]``` : Reouvir une issue
    Options | Description 
    --- | --- 
    ```-c```, ``` --comment <string>``` | Laisser un commentaire de réouverture
<br>

### <a id=pr></a>**Gestion des pull requests**

- ```gh pr create [flags]``` : Créer une pull request

    Options | Description 
    --- | --- 
    ```-B```, ``` --base <branch>``` | La branche dans laquelle vous voulez merge votre code
    ```-f```, ``` --fill``` | Utiliser les infos du commit pour le titre et corps
    ```-l```, ``` --label <name>``` | Ajouter un label par nom
<br>

- ```gh pr list [flags]``` : Lister les pull request

    Options | Description 
    --- | --- 
    ```-a```, ``` --assignee <string>``` | Filtrer par personne assignée
    ```-A```, ``` --author <string>``` | Filtrer par auteur
    ```-s```, ``` --state <string> (default "open")``` | Filtrer par Statut: {open\|closed\|merged\|all}
    ```-l```, ``` --label <strings>``` | Filter par label
<br>

- ```gh pr status``` : Afficher le status des pull request qui te concerne 
- ```gh pr view {<number> | <url> | <branch>} [flags]``` : Voir une pull request spécifique
    Options | Description 
    --- | --- 
    ```-c```, ``` --comments``` | Voir les commentaire d'une pull request
<br>

- ```gh pr checkout {<number> | <url> | <branch>}``` : Voir les détails d'une pull request
- ```gh pr merge {<number> | <url> | <branch>}``` : Merge une pull request
- ```gh pr diff {<number> | <url> | <branch>} [flags]``` : Voir les changements dans une pull request

- ```gh pr close {<number> | <url> | <branch>} [flags]``` : Fermer une pull request
    Options | Description 
    --- | --- 
    ```-c```, ``` --comment <string>``` | Leave a closing comment
    ```-d```, ``` --delete-branch``` | Supprimer la branche locale et distante aprés la fermeture
<br>

- ```gh pr reopen {<number> | <url> | <branch>} [flags]``` : Réouvrir une pull request
    Options | Description 
    --- | --- 
    ```-c```, ``` --comment <string>``` | Laisser un commentaire de réouverture
<br>

### <a id=workflows>**Gestion des workflows**

- ```gh workflow list [flags]``` : Lister les fichier workflow , cachant les désactiver par défaut

    Options | Description 
    --- | --- 
    ```-a```, ``` --all``` | Inclure les workflows désactivés

-```gh workflow view [<workflow-id> | <workflow-name> | <filename>] [flags]``` : Voir une résumé d'un workflow
- ```gh workflow run [<workflow-id> | <workflow-name>]``` : éxecute un workflow
- ```gh workflow enable [<workflow-id> | <workflow-name>]``` : Active un workflow, lui permetant d'être exécuté
- ```gh workflow disable [<workflow-id> | <workflow-name>]``` : Désactive un workflow, l'empéchant d'être exéctué
<br>