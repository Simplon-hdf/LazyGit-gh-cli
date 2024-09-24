Le **GitHub CLI** (`gh`) est un outil en ligne de commande conçu pour interagir avec GitHub directement depuis ton terminal. Il permet d'effectuer des tâches GitHub courantes comme la gestion des issues, des pull requests, et la gestion des dépôts, sans avoir à ouvrir l'interface web. Voici un guide complet pour l'installer et utiliser ses différentes commandes.

### 1. **Installation de GitHub CLI**

#### Sur Linux/macOS (via Homebrew)

	brew install gh
#### Sur Ubuntu/Debian (via apt)

	sudo apt install gh

#### Sur Windows

L'installer de façon manuelle via : 
https://github.com/cli/cli/releases/?ref=techielass.com

Ou installation via winget:

	winget install --id github.cli

### 2. **Authentification**

Avant de commencer à utiliser `gh`, tu dois t'authentifier :

	gh auth login
	

### 3. **Commandes GitHub CLI Principales**

#### Gestion des Dépôts

 **Cloner un dépôt** :

	gh repo clone <owner>/<repo>

Ex : `gh repo clone octocat/Hello-World`

**Créer un dépôt** :

	gh repo create <nom-du-repo> --public

Ex : `gh repo create mon-nouveau-repo --public`

**Visualiser les informations d'un dépôt** :

	gh repo view <nom-du-repo>
	
Ex : `gh repo view octocat/Hello-World 

#### Gestion des Issues

- **Lister les issues** :

	gh issue list
	
Cela liste toutes les issues ouvertes dans le dépôt actuel.

**Créer une nouvelle issue** :

	gh issue create


**Voir les détails d'une issue** :

	gh issue view <numéro-issue>

Ex : `gh issue view 23`

**Gestion des Pull Requests (PR)**

**Lister les PR** :

	gh pr list

Affiche toutes les pull requests ouvertes dans le dépôt.

**Créer une pull request** :

	gh pr create --base main --head feature-branch

On peut ajouter des options comme `--title` ou `--body` pour donner un titre ou une description à la PR.

**Vérifier les détails d'une PR** :

	gh pr view <numéro-pr>
	
Ex : `gh pr view 45`

**Fusionner une PR** :

	gh pr merge <numéro-pr>

Tu peux utiliser des options comme `--squash` ou `--rebase` pour spécifier le type de merge.

**Workflow de CI/CD**
GitHub CLI permet aussi de gérer les workflows GitHub Actions.

**Lister les workflows actifs** :

	gh workflow list

**Déclencher un workflow** :

	gh workflow run <nom-du-workflow>

**Visualiser les logs d'un workflow :**

	gh run view <id-du-run>

Ex : gh run view 1234567890 --log pour voir les logs en détail.

**Autres Commandes Utiles**

    Visualiser le statut de l'utilisateur connecté :

		gh auth status

Créer un Gist (outil pour partager des snippets de code) :

	gh gist create <nom-du-fichier> --public
