# Introduction à GitHub CLI

GitHub CLI est un outil de ligne de commande conçu pour utiliser github depuis le terminal. Avec CLI vous avez accès à toutes les fonctionnalités de Github, plus rapidement et de manière plus fluide. CLI vous aide à rester productifs et à éviter le contexte switching (perte de concentration).

### *Quelles différences entre Github CLI et Git par ligne de commande ?*

L'interface de ligne de commande Github (Github CLI) vous permets de travailler avec un dépôt local ou distant. Le dépôt distant peut être hébérgé par Github ou un autre service.

GitHub CLI (gh) est conçu pour fonctionner avec Github et permet d'utiliser la ligne de commande pour interagir de plusieurs manières. CLI comprends des fonctionnalités telles que:

 - Voir, créer, cloner et fork des dépôts

 - créer, fermer, éditer et voir les pull requests (demandes de tirage)

 - Review et merge les pull requests

 - Créer, lister, voir et supprimer les releases
    
### *Pourquoi utiliser Github CLI?*

   **Productivité**: Effectuez des tâches communes en utilisant le moins de commandes possible sans quitter le terminal.

   **Conçu pour github**: Interagissez avec toutes les fonctionnalités de Github.

**Personalisation et extensions**: Définissez des alias pour les commandes que vous utilisez fréquemment.

## Comment installer github CLI ?

**Windows**

Avec Scoop ```scoop  install gh```

Avec Chocolatey ```choco  install gh```

Installation manuelle

```Téléchargez le fichier .msi depuis la page releases de GitHub CLI. Exécutez-le et suivez les intructions.```

---
**MacOS**

Avec Homebrew ```brew install gh```

Avec MacPorts

- ```Téléchargez le fichier .pkg  depuis la page releases de GitHub CLI. Exécutez-le et suivez les intructions```

- ```sudo port install gh```


---
```Linux```

Pour Debian/Ubuntu (et dérivés) 

avec apt 
    
- ```sudo apt update```
- ```sudo apt install gh```

---
Pour Fedora 

avec dnf 
    
```sudo dnf install gh```

Pour CentOS 

avec yum 

```sudo yum install gh```

---
Pour Arch Linux 

avec pacman

- ```Téléchargez le fichier.tar.gz depuis la page releases de GitHub CLI exécutez-le et suivez les intructions.```

- ```sudo pacman -S github-cli```

Vérifier l'installation

```gh --version```    


### CONFIGURATION
Authentification GitHub

Pour vous connecter à Github par la ligne de commande, utilisez la commande suivante:

```gh auth login```

suivez les instructions pour vous authentifier.

**Configuration de l'éditeur de code**

 Pour définir votre éditeur pour les opérations en ligne de commande, utilisez:

```gh config set editor```

suivi du nom de votre éditeur

```gh config set editor code```

Alias

Pour définir des alias pour des commandes que vous utilisez fréquemment:

```gh alias set```

Par exemple si vous voulez créer un alias pour la commande: ```gh repo create```

vous pouvez le faire avec la commande :


```gh alias set create-repo `____` ```