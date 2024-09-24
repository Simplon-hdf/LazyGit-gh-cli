### <span style="color:#003366;">Lazygit : Un Guide Complet</span> 🚀

*Lazygit est une interface utilisateur (UI) en mode texte pour Git, qui permet de gérer des dépôts Git via une interface conviviale dans le terminal. Grâce à des raccourcis clavier bien pensés, il permet de rendre plus efficace la gestion des branches, des commits, des merges, des rebases, etc.*

---

### Table des matières 📚
1. [Introduction à Lazygit](#1-introduction-à-lazygit)
2. [Installation de Lazygit](#2-installation-de-lazygit)
   - 2.1. [Sur Linux](#21-sur-linux)
   - 2.2. [Sur macOS](#22-sur-macos)
   - 2.3. [Sur Windows](#23-sur-windows)
3. [Prise en main de l'interface](#3-prise-en-main-de-linterface)
   - 3.1. [Vue générale de l'interface](#31-vue-générale-de-linterface)
   - 3.2. [Panneaux et leur usage](#32-panneaux-et-leur-usage)
4. [Les raccourcis clavier essentiels](#4-les-raccourcis-clavier-essentiels)
5. [Fonctionnalités clés](#5-fonctionnalités-clés)
   - 5.1. [Gestion des commits](#51-gestion-des-commits)
   - 5.2. [Gestion des branches](#52-gestion-des-branches)
   - 5.3. [Gestion des conflits](#53-gestion-des-conflits)
   - 5.4. [Merging et Rebase](#54-merging-et-rebase)
6. [Trucs et astuces](#6-trucs-et-astuces)
7. [Comparaison avec Git CLI](#7-comparaison-avec-git-cli)
8. [Conclusion](#8-conclusion)

---

### <span id="1-introduction-à-lazygit" style="color:#003366;">1. Introduction à Lazygit</span> 💻

Lazygit est un outil qui simplifie grandement l'utilisation de Git en offrant une interface utilisateur en mode terminal. Pour ceux qui trouvent Git complexe à utiliser, surtout en ligne de commande pure, Lazygit est une solution qui permet de visualiser rapidement les statuts des fichiers, gérer les branches et effectuer des opérations comme les commits, les merges, ou encore la résolution des conflits avec un minimum de friction.

**Pourquoi Lazygit ?**
- **Gain de temps** : Les raccourcis clavier permettent de faire des actions complexes en un rien de temps.
- **Moins d'erreurs** : L'interface visuelle permet de visualiser clairement les changements avant d'agir.
- **Apprentissage plus facile** : Pour les débutants, il est plus intuitif que d’apprendre les commandes Git à la main.
  
---

### <span id="2-installation-de-lazygit" style="color:#003366;">2. Installation de Lazygit</span> 🛠️

L'installation de Lazygit varie en fonction du système d'exploitation utilisé. Voici un guide détaillé pour chaque plateforme.

#### <span id="21-sur-linux" style="color:#003366;">2.1. Sur Linux</span>

Sur Linux, vous pouvez installer Lazygit via votre gestionnaire de paquets ou via Go (le langage dans lequel Lazygit est écrit).

```bash
# Installation via un package manager comme apt (Debian/Ubuntu)
sudo add-apt-repository ppa:lazygit-team/release
sudo apt update
sudo apt install lazygit
```

Ou, si Go est déjà installé sur votre machine :

```bash
go install github.com/jesseduffield/lazygit@latest
```

#### <span id="22-sur-macos" style="color:#003366;">2.2. Sur macOS</span>

Pour macOS, Homebrew est le moyen le plus simple d'installer Lazygit.

```bash
brew install jesseduffield/lazygit/lazygit
```

#### <span id="23-sur-windows" style="color:#003366;">2.3. Sur Windows</span>

Sur Windows, vous pouvez utiliser `scoop` ou `chocolatey` pour installer Lazygit.

Avec Scoop :

```bash
scoop bucket add extras
scoop install lazygit
```

Avec Chocolatey :

```bash
choco install lazygit
```

---

### <span id="3-prise-en-main-de-linterface" style="color:#003366;">3. Prise en main de l'interface</span> 🖥️

L'interface de Lazygit se décompose en plusieurs panneaux, chacun ayant une fonction spécifique pour vous aider à gérer vos dépôts Git.

#### <span id="31-vue-générale-de-linterface" style="color:#003366;">3.1. Vue générale de l'interface</span>

Lorsque vous démarrez Lazygit en tapant `lazygit` dans le terminal, voici une vue générale de l’interface :

- **Panneau des fichiers** : Montre les fichiers modifiés et non suivis.
- **Panneau des branches** : Permet de gérer et de naviguer entre les branches.
- **Panneau des logs de commits** : Affiche les derniers commits.
- **Panneau des détails** : Donne des détails sur l’élément actuellement sélectionné (commit, fichier, branche, etc.).

#### <span id="32-panneaux-et-leur-usage" style="color:#003366;">3.2. Panneaux et leur usage</span>

Voici une répartition des différents panneaux de Lazygit et leur utilité :

| **Panneau**              | **Fonction**                                                                  |
|--------------------------|-------------------------------------------------------------------------------|
| Panneau des fichiers      | Liste les fichiers modifiés et non suivis. Vous pouvez y faire des commits ou les ajouter à l'index. |
| Panneau des branches      | Gérer les branches actuelles, les créer, supprimer, ou naviguer entre elles.  |
| Panneau des logs de commit| Voir les commits récents et explorer l'historique de commits.                 |
| Panneau des détails       | Affiche des informations détaillées sur le fichier ou le commit sélectionné.  |

---

### <span id="4-les-raccourcis-clavier-essentiels" style="color:#003366;">4. Les raccourcis clavier essentiels</span> ⌨️

Lazygit est conçu pour rendre les actions Git rapides grâce à une série de raccourcis clavier. Voici quelques-uns des plus importants :

| **Action**                 | **Raccourci** |
|----------------------------|---------------|
| Ouvrir Lazygit             | `lazygit`     |
| Ajouter un fichier à l'index| `a`           |
| Committer des changements  | `c`           |
| Pousser sur la branche distante | `p`       |
| Tirer les changements distants | `f`        |
| Changer de branche         | `b`           |
| Gérer un conflit           | `m`           |
| Afficher les logs          | `l`           |

---

### <span id="5-fonctionnalités-clés" style="color:#003366;">5. Fonctionnalités clés</span> 🔑

Lazygit propose un ensemble de fonctionnalités qui couvrent les opérations les plus fréquentes sur Git, mais aussi certaines plus avancées.

#### <span id="51-gestion-des-commits" style="color:#003366;">5.1. Gestion des commits</span>

La gestion des commits dans Lazygit est simplifiée grâce à des raccourcis pour ajouter des fichiers à l'index, les committer, et visualiser les différences avant de confirmer les changements.

**Actions fréquentes :**
- Ajouter des fichiers avec `a`.
- Visualiser les modifications avant commit avec `Enter` sur le fichier.
- Committer avec `c`.

#### <span id="52-gestion-des-branches" style="color:#003366;">5.2. Gestion des branches</span>

La gestion des branches est intuitive, permettant de passer rapidement d'une branche à une autre ou d'en créer de nouvelles.

**Actions fréquentes :**
- Créer une nouvelle branche : `n`.
- Changer de branche : `b`.
- Supprimer une branche : `d`.

#### <span id="53-gestion-des-conflits" style="color:#003366;">5.3. Gestion des conflits</span>

Lors d’un conflit de merge, Lazygit affiche une interface pour visualiser les fichiers en conflit et résoudre ces derniers.

**Actions fréquentes :**
- Voir les fichiers en conflit : `m`.
- Résoudre un conflit : `r` après avoir édité le fichier.

#### <span id="54-merging-et-rebase" style="color:#003366;">5.4. Merging et Rebase</span>

Lazygit supporte à la fois les merges et les rebase. Le rebase est souvent préféré pour maintenir un historique plus propre, tandis que le merge est plus simple à comprendre pour un débutant.

**Actions fréquentes :**
- Merge une branche : `M`.
- Rebase une branche : `R`.

---

### <span id="6-trucs-et-astuces" style="color:#003366

;">6. Trucs et astuces</span> ⚡

Voici quelques astuces pour utiliser Lazygit plus efficacement :

- **Utilisez les alias Git pour lancer Lazygit plus rapidement** : On peut créer un alias dans `.bashrc` ou `.zshrc` :
  ```bash
  alias lg='lazygit'
  ```
- **Intégration avec des IDE** : Lazygit peut être utilisé en parallèle avec des éditeurs comme VS Code pour combiner une interface graphique et une interface terminal.
  
---

### <span id="7-comparaison-avec-git-cli" style="color:#003366;">7. Comparaison avec Git CLI</span> ⚔️

| **Fonctionnalité**     | **Lazygit**                                       | **Git CLI**                             |
|------------------------|--------------------------------------------------|-----------------------------------------|
| Interface              | Graphique en mode terminal                       | Pure ligne de commande                  |
| Facilité d'utilisation | Très facile avec les raccourcis et l’interface    | Peut être plus difficile pour les débutants |
| Gestion des branches   | Simplifiée avec des raccourcis                   | Nécessite de taper des commandes plus longues |
| Résolution des conflits| Interface dédiée avec visualisation des conflits | Doit être géré manuellement avec des outils externes (comme Vim ou VSCode) |

---

### <span id="8-conclusion" style="color:#003366;">8. Conclusion</span> 🎯

Lazygit est un outil puissant pour ceux qui souhaitent gérer leurs dépôts Git de manière plus fluide et visuelle. Il permet de gagner du temps, réduit les erreurs et simplifie les workflows Git. Bien qu’il soit toujours bon de connaître les bases de Git en ligne de commande, Lazygit offre un compromis idéal entre productivité et simplicité. Il est donc particulièrement recommandé pour les développeurs qui travaillent régulièrement avec Git et souhaitent rationaliser leur processus.

---

Avec Lazygit, on dispose d’un outil robuste et rapide qui améliore significativement l'expérience Git, surtout lorsqu'il s'agit de gérer de grands projets ou de nombreux commits et branches.
