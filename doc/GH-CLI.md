<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GitHub CLI</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            background-color: #f4f4f4;
            color: #333;
            margin: 0;
            padding: 20px;
        }
        h1 {
            color: #2c3e50;
            text-align: center;
        }
        h2 {
            color: #2980b9;
            border-bottom: 2px solid #2980b9;
            padding-bottom: 10px;
        }
        h3 {
            color: #3498db;
        }
        pre {
            background-color: #ecf0f1;
            border-left: 4px solid #2980b9;
            padding: 10px;
            overflow-x: auto;
        }
        code {
            font-family: monospace; /* Assure que la police est monospace pour les commandes */
        }
        ul {
            list-style-type: none;
            padding: 0;
        }
        ul li {
            margin: 5px 0;
        }
        blockquote {
            border-left: 4px solid #2980b9;
            margin: 10px 0;
            padding-left: 10px;
            color: #555;
            font-style: italic;
        }
        .footer {
            text-align: center;
            margin-top: 20px;
            font-size: 0.9em;
            color: #888;
        }
    </style>
</head>
<body>

<h1>GitHub CLI</h1>

<p>
    <strong>GitHub CLI</strong> (command line interface) ou <strong>GH CLI</strong>, est un outil en ligne de commande permettant d'interagir avec GitHub depuis le terminal. 
    Il permet d'effectuer des tâches GitHub courantes comme la gestion des issues, des pull requests, et la gestion des dépôts, sans avoir à ouvrir l'interface web. 
    Voici un guide complet pour l'installer et utiliser ses différentes commandes.
</p>

<h2>Sommaire</h2>
<ul>
    <li><a href="#installation-de-github-cli">1. Installation de GitHub CLI</a></li>
    <ul>
        <li><a href="#sur-linuxmacos-via-homebrew">- Sur Linux/macOS (via Homebrew)</a></li>
        <li><a href="#sur-ubuntudebian-via-apt">- Sur Ubuntu/Debian (via apt)</a></li>
        <li><a href="#sur-windows">- Sur Windows</a></li>
    </ul>
    <li><a href="#authentification">2. Authentification</a></li>
    <li><a href="#commandes-github-cli-principales">3. Commandes GitHub CLI Principales</a></li>
    <ul>
        <li><a href="#gestion-des-dépôts">- Gestion des Dépôts</a></li>
        <li><a href="#gestion-des-issues">- Gestion des Issues</a></li>
        <li><a href="#gestion-des-pull-requests">- Gestion des Pull Requests</a></li>
    </ul>
    <li><a href="#gestion-des-workflows-cicd">4. Gestion des Workflows CI/CD</a></li>
    <li><a href="#autres-commandes-utiles">5. Autres Commandes Utiles</a></li>
    <li><a href="#alias">6. Alias</a></li>
    <li><a href="#commandes-personnalisées">7. Commandes Personnalisées</a></li>
</ul>

<h2 id="installation-de-github-cli">1. <strong>Installation de GitHub CLI</strong></h2>

<h3 id="sur-linuxmacos-via-homebrew">Sur Linux/macOS (via Homebrew)</h3>
<pre><code style="color:black">brew install gh</code></pre>

<h3 id="sur-ubuntudebian-via-apt">Sur Ubuntu/Debian (via apt)</h3>
<pre><code style="color:black">sudo apt install gh</code></pre>

<h3 id="sur-windows">Sur Windows</h3>
<p>
    L'installer de façon manuelle via : 
    <a href="https://github.com/cli/cli/releases/?ref=techielass.com" target="_blank">GitHub CLI Releases</a>
</p>
<pre><code style="color:black">winget install --id github.cli</code></pre>

<h2 id="authentification">2. <strong>Authentification</strong></h2>

<p>Avant de commencer à utiliser <code style="color:white" >gh CLI</code>, tu dois t'authentifier :</p>
<pre><code style="color:black">gh auth login</code></pre>
<p>Pour déconnecter l'utilisateur actuel de GitHub :</p>
<pre><code style="color:black">gh auth logout</code></pre>

<h2 id="commandes-github-cli-principales">3. <strong>Commandes GitHub CLI Principales</strong></h2>

<h3 id="gestion-des-dépôts">Gestion des Dépôts</h3>
<p><strong>Cloner un dépôt :</strong></p>
<pre><code style="color:black">gh repo clone owner/nom-du-repo</code></pre>
<blockquote>
    <p style="color:white">owner signifie le nom de mon compte GitHub.</p>
</blockquote>

<p><strong>Créer un dépôt :</strong></p>
<pre><code style="color:black">gh repo create nom-du-nouveau-repo --public</code></pre>
<blockquote>
    <p style="color:white">--public veut dire que le repo créé sera visible pour tous, sinon --private.</p>
</blockquote>

<p><strong>Visualiser les informations d'un dépôt :</strong></p>
<pre><code style="color:black">gh repo view &lt;nom-du-repo&gt;</code></pre>
<pre><code style="color:black">gh repo view owner/nom-du-repo</code></pre>
<p>Ex : <code style="color:white">gh repo view octocat/Hello-World</code></p>

<h3 id="gestion-des-issues">Gestion des Issues</h3>
<p><strong>Lister les issues :</strong></p>
<pre><code style="color:black">gh issue list</code></pre>
<blockquote>
    <p style="color:white">Cela liste toutes les issues ouvertes dans le dépôt actuel.</p>
</blockquote>

<p><strong>Créer une nouvelle issue :</strong></p>
<pre><code style="color:black">gh issue create</code></pre>

<p><strong>Voir les détails d'une issue :</strong></p>
<pre><code style="color:black">gh issue view numero-issue</code></pre>
<p>Ex : <code style="color:white">gh issue view 23</code></p>

<h3 id="gestion-des-pull-requests">Gestion des Pull Requests</h3>
<p><strong>Lister les PR :</strong></p>
<pre><code style="color:black">gh pr list</code></pre>
<blockquote>
    <p style="color:white">Affiche toutes les pull requests ouvertes dans le dépôt.</p>
</blockquote>

<p><strong>Créer une pull request :</strong></p>
<pre><code style="color:black">gh pr create --base main --head feature-branch</code></pre>
<blockquote>
    <p style="color:white">On peut ajouter des options comme <code style="color:white">--title</code> ou <code style="color:white">--body</code> pour donner un titre ou une description à la PR.</p>
</blockquote>

<p><strong>Vérifier les détails d'une PR :</strong></p>
<pre><code style="color:black">gh pr view numéro-pr</code></pre>
<p>Ex : <code style="color:white">gh pr view 45</code></p>

<p><strong>Fusionner une PR :</strong></p>
<pre><code style="color:black">gh pr merge numéro-pr</code></pre>
<blockquote>
    <p style="color:white">Tu peux utiliser des options comme <code style="color:white">--squash</code> ou <code style="color:white">--rebase</code> pour spécifier le type de merge.</p>
</blockquote>

<h2 id="gestion-des-workflows-cicd">4. <strong>Gestion des Workflows CI/CD</strong></h2>
<p>GitHub CLI permet aussi de gérer les workflows GitHub Actions.</p>

<p><strong>Lister les workflows actifs :</strong></p>
<pre><code style="color:black">gh workflow list</code></pre>

<p><strong>Déclencher un workflow :</strong></p>
<pre><code style="color:black">gh workflow run nom-du-workflow</code></pre>

<p><strong>Visualiser les logs d'un workflow :</strong></p>
<pre><code style="color:black">gh run view id-du-run</code></pre>
<p>Ex : <code style="color:white">gh run view 1234567890 --log</code> pour voir les logs en détail.</p>

<h2 id="autres-commandes-utiles">5. <strong>Autres Commandes Utiles</strong></h2>

<p><strong>Visualiser le statut de l'utilisateur connecté :</strong></p>
<pre><code style="color:black">gh auth status</code></pre>

<p><strong>Créer un Gist (outil pour partager des snippets de code) :</strong></p>
<pre><code style="color:black">gh gist create nom-du-fichier --public</code></pre>

<p><strong>Ouvrir GitHub dans le navigateur pour ton dépôt actuel :</strong></p>
<pre><code style="color:black">gh browse</code></pre>

<h2 id="alias">6. <strong>Alias</strong></h2>
<p>Une fonctionnalité puissante de GitHub CLI est la possibilité de créer des alias pour les commandes que tu utilises fréquemment :</p>
<pre><code style="color:black">gh alias set co "pr checkout"</code></pre>
<p>Cela te permet de taper <code style="color:white">gh co &lt;pr&gt;</code> au lieu de <code style="color:white">gh pr checkout</code>.</p>

<h2 id="commandes-personnalisées">7. <strong>Commandes Personnalisées</strong></h2>
<p>Tu peux même ajouter tes propres scripts personnalisés dans GitHub CLI :</p>
<p>Place un script dans le dossier <code style="color:white">gh</code> sous <code style="color:white">~/.config/</code> ou <code style="color:white">C:\Users&lt;user&gt;\AppData\Roaming\gh\</code></p>
<p>Tu pourras ensuite l'appeler comme une commande native <code style="color:white">gh</code>.</p>

<div class="footer">
    <p>&copy; 2024 GitHub CLI Documentation</p>
</div>

</body>
</html>
