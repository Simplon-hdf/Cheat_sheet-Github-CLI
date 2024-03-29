# Comment installer Github CLI sur différents systèmes d'exploitation

## Systèmes d'exploitation
- [Linux](#installation-de-gh-sur-linux-et-bsd)
- [Windows](#installation-de-gh-sur-windows)
- [macOS](#macos)
### Installation de gh sur Linux et BSD

---
| **Linux**                                    | gestionnaire de paquets | Ligne de commande     |
|------------------------------------------|-------------------|-----------------------|
| _Debian, Ubuntu Linux, Raspberry Pi OS_  | ```apt```         | ```sudo apt install gh ```  |
| _Fedora, CentOS, Red Hat Enterprise Linux_| ```dnf```        | ```sudo dnf install gh ```  |
| _Amazon Linux 2_                           | ```yum```       | ```sudo yum install gh ```   |
| _openSUSE/SUSE Linux_                      | ```zypper```    | ```sudo zypper install gh ```|


**Kiss Linux**

Les utilisateurs de Kiss Linux peuvent installer à partir de la prise de possession de la communauté : ```kiss b github-cli && kiss i github-cli```

**Linux alpin**

Les utilisateurs d'Alpine Linux peuvent installer à partir du référentiel de paquets de la communauté des versions stables. ```apk add github-cli```

**Linux Vid**

Les utilisateurs de Void Linux peuvent installer à partir du repo de distribution officiel :```sudo xbps-install github-cli```


Pour vérifier la version installée de gh, utilisez cette ligne de commande:

``` gh --version```

Pour mettre à niveau la version de gh, il faut utiliser la commande  :  ```update```

Exemple : ![commande update](/assets/Commandupdate.png)



### **BSD** 

**FreeBSD**

Les utilisateurs de FreeBSD peuvent installer à partir de la collection des ports :
```cd /usr/ports/devel/gh/ && make install clean```

Ou via pkg(8):
```pkg install gh```

**NetBSD/pkgsrc**

Les utilisateurs de NetBSD et ceux sur les plateformes supportés par pkgsrc peuvent installer le paquet gh : ```pkgin install gh```

Pour installer à partir de la source: ```cd /usr/pkgsrc/net/gh && make package-install```

**OpenBSD**
En cours ou dans des versions commençant à partir de 7.0, les utilisateurs d'OpenBSD peuvent s'installer à partir des paquets: ```pkg_add github-cli```

### **Installation de gh sur Windows**

---

```gh``` est disponible via WinGet, scoop, Chocolatey, Conda, Webi, et en tant que MSI téléchargeable.

|            | installer                             | Mise à niveau                        |
|------------|---------------------------------------|--------------------------------------|
| WinGet     |  ```winget install --id GitHub.cli``` | ```winget upgrade --id GitHub.cli``` |
| scoop      |   ```scoop install gh```              |   ```scoop update gh```              |
| Chocolatey |   ```choco install gh```              |   ```choco upgrade gh```             |

macOS
---
```gh``` est disponible via Homebrew, MacPorts, Conda, Spack, Webi, et en tant que binaire téléchargeable à partir de la page des versions.

|          | installer                                      | mise à niveau                                           |
|----------|------------------------------------------------|---------------------------------------------------------|
| Homebrew |      ```brew install gh```                     |   ```brew upgrade gh```                                 |
| MacPorts |   ```sudo port install gh```                   |      ```sudo port selfupdate && sudo port upgrade gh``` |
| Conda    |   ```conda install gh --channel conda-forge``` |      ```conda update gh --channel conda-forge```        |
| Spack    |      ```spack install gh```                    |      ```spack uninstall gh && spack install gh```       |
| Webi     |      ```curl -sS https://webi.sh/gh \| sh```   |      ```webi gh@stable```                               |

#### REMARQUE: 
---

Pour vérifier la version installée de gh, utilisez cette ligne de commande:

``` gh --version```

Pour mettre à niveau la version de gh, il faut utiliser la commande  :  ```update```

Exemple : ![commande update](/assets/Commandupdate.png)