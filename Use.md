# **Base use of GitHub CLI**

GitHub CLI (**gh**) is a command-line tool that brings GitHub functionality to your terminal.This GitHub operations <br> without interacting with the graphical interface and remaining focused on the terminal.

## Basic command CLI

### **Authentification**

Enter <code>gh auth login</code> and follow the prompts to log in using your GitHub ID

```
gh auth login <flag>
```


  Options  |  effect 
  ---| ---
```gh auth login --hostname github.example.com --web```| Authentificate without additional command

<img src="assets/Use_img/Auth_exemple.png" alt="Auth_exemple" width="" >

<br>
You can enter <code>gh auth logout</code> to log out.

### **Managing Repository**

Enter <code> gh repo create <code> to create a repository


