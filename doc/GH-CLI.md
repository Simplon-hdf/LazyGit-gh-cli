# 🚀 GitHub CLI

**GitHub CLI** (command line interface) ou **GH CLI**, est un outil en ligne de commande permettant d'interagir avec GitHub depuis le terminal. 
Il permet d'effectuer des tâches GitHub courantes comme la gestion des dépôts, des issues et des pull requests sans avoir à ouvrir l'interface web. 

Voici un guide complet pour l'installer et utiliser ses différentes commandes.

## 📚 Sommaire

1. [Installation de GitHub CLI](#installation-de-github-cli)  
   - [Sur Linux/macOS (via Homebrew)](#sur-linuxmacos-via-homebrew)  
   - [Sur Ubuntu/Debian (via apt)](#sur-ubuntudebian-via-apt)  
   - [Sur Windows](#sur-windows)  

2. [Authentification](#authentification)  

3. [Commandes GitHub CLI Principales](#commandes-github-cli-principales)  
   - [Gestion des Dépôts](#gestion-des-dépôts)  
   - [Gestion des Issues](#gestion-des-issues)  
   - [Gestion des Pull Requests](#gestion-des-pull-requests)

4. [Gestion des Workflows CI/CD](#gestion-des-workflows-cicd)  

5. [Autres Commandes Utiles](#autres-commandes-utiles)  

6. [Alias](#alias)  

7. [Commandes Personnalisées](#commandes-personnalisées)


## 1. **Installation de GitHub CLI**

#### Sur Linux/macOS (via Homebrew)

```
	brew install gh
```
#### Sur Ubuntu/Debian (via apt)

```
	sudo apt install gh
```

#### Sur Windows

Pour l'**installer** de façon **manuelle** via : 

> https://github.com/cli/cli/releases/?ref=techielass.com

Ou **installation** via **winget**:

```
	winget install --id github.cli
```	

## 2. **Authentification**

Avant de pouvoir utiliser `GH CLI`, il faut s'**identifier** :

```
	gh auth login
```	

Pour **déconnecter** l'**utilisateur actuel** de **GitHub** :

```
	gh auth logout
```

## 3.  **Commandes GitHub CLI Principales**

### Gestion des Dépôts

Pour **Cloner** un **dépôt** :

```
	gh repo clone owner/nom-du-repo
```

> *owner signifit le nom de mon compte GitHub*

Pour **Créer** un **dépôt** :

```
	gh repo create nom-du-nouveau-repo --public
```

> *--public signifit que le repo crée sera visible pour tous, sinon --private*

Pour **Visualiser** les **informations** d'un **dépôt** :

```
	gh repo view nom-du-repo
	
	gh repo view owner/nom-du-repo
```

### Gestion des Issues

Pour **Lister** les **issues** :

```
	gh issue list
```
	
> *Liste toutes les issues ouvertes dans le dépôt actuel*

Pour **Créer** une nouvelle **issue** :

```
	gh issue create
```

Pour **Visualiser** les **détails** d'une **issue** :

```
	gh issue view numero-issue
```

### Gestion des Pull Requests (PR)

Pour **Lister** les **PR** :

```
	gh pr list
```

> *Affiche toutes les pull requests ouvertes dans le dépôt*

Pour **Créer** une **PR** :

```
	gh pr create --base main --head feature-branch
```

> *Possible d'ajouter des options comme `--title` ou `--body` pour donner un titre ou une description à la PR*

Pour **Vérifier** les **détails** d'une **PR** :

```
	gh pr view numéro-pr
```

Pour **Fusionner** une **PR** :

```
	gh pr merge numéro-pr
```

> *Possible d'utiliser des options comme `--squash` ou `--rebase` pour spécifier le type de merge*

## 4. **Gestion des Workflows CI/CD**

**GitHub CLI** permet aussi de **gérer** les **workflows GitHub Actions**

Pour **Lister** les **workflows actifs** :

```
	gh workflow list
```

Pour **Déclencher** un **workflow** :

```
	gh workflow run nom-du-workflow
```

Pour **Visualiser** les **logs** d'un **workflow** :

```
	gh run view id-du-run
```

> *`gh run view 1234567890 suivi de --log` pour voir les logs en détail*

## 5. **Autres Commandes Utiles**

Pour **Visualiser** le **statut** de l'**utilisateur connecté** :

```
	gh auth status
```

Pour **Créer** un **Gist** (outil pour partager des snippets de code) :

```
	gh gist create nom-du-fichier --public
```

Pour **Ouvrir GitHub** dans le **navigateur** pour ton **dépôt actuel** :

```
	gh browse
```

## 6. **Alias**

Une fonctionnalité puissante de **GitHub CLI** est la possibilité de **créer** des **alias** pour les commandes que tu utilises fréquemment :

```
	gh alias set co "pr checkout"
```

*Ex : Permet de raccourcir la commande `gh pr checkout` en `gh co <pr>`*

## 7. **Commandes Personnalisées**

Il est même possible d'ajouter ses propres scripts personnalisés dans `GitHub CLI` :

Placer un script dans le dossier `gh` sous `~/.config/` 
ou `C:\Users\<user>\AppData\Roaming\gh\`  
Tu pourras ensuite l'appeler comme une commande native `gh`.