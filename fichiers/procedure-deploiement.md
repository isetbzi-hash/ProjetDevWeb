# Procédure de déploiement — Bizerte Voyages

## 1. Prérequis
- Un compte GitHub.
- Git installé et configuré (`git --version`).
- Le projet `Atelier4-bizerte-voyages/` avec `index.html`, `style.css` et `images/`.
- VS Code et l'extension Live Server.
- Une connexion Internet pour charger Bootstrap depuis son CDN.

## 2. Vérification locale
1. Ouvrir le dossier du projet dans VS Code.
2. Vérifier que les dix images attendues sont présentes dans `images/`.
3. Ouvrir `index.html` avec **Open with Live Server**.
4. Tester le menu, les liens internes, les cartes et le formulaire.
5. Ouvrir les outils de développement (F12) et vérifier l'onglet Console et l'onglet Network.

## 3. Initialiser Git et publier le dépôt
Dans le terminal, à la racine du dossier :

```bash
git init
git add .
git commit -m "Site Bootstrap responsive"
git branch -M main
```

Sur GitHub, créer un dépôt **public** nommé `bizerte-voyages`, sans README, licence ni `.gitignore` initialisés automatiquement.

Relier le dépôt local au dépôt GitHub (remplacer `VOTRE-NOM` par votre identifiant GitHub) :

```bash
git remote add origin https://github.com/VOTRE-NOM/bizerte-voyages.git
git push -u origin main
```

Pour les modifications ultérieures :

```bash
git add .
git commit -m "Description claire des modifications"
git push
```

## 4. Activer GitHub Pages
1. Ouvrir le dépôt GitHub `bizerte-voyages`.
2. Aller dans **Settings**, puis **Pages**.
3. Dans **Build and deployment**, choisir **Deploy from a branch**.
4. Sélectionner la branche `main` et le dossier `/ (root)`.
5. Cliquer sur **Save**.
6. Attendre la fin du déploiement dans l'onglet **Actions**.
7. Ouvrir l'adresse publique affichée dans **Settings > Pages**. Elle est généralement de la forme `https://VOTRE-NOM.github.io/bizerte-voyages/`.

## 5. Vérification finale
Effectuer les tests de la checklist sur l'adresse publique, et non uniquement sur Live Server. Si un problème est corrigé, faire un nouveau commit et un `git push`, puis retester.

## 6. Retour arrière en cas de problème
1. Identifier le dernier commit stable avec `git log --oneline`.
2. Pour annuler un commit déjà publié sans réécrire l'historique, utiliser :

```bash
git revert IDENTIFIANT_DU_COMMIT
git push
```

3. Attendre le nouveau déploiement GitHub Pages et vérifier de nouveau le site.

## 7. Limite du formulaire
Le formulaire fourni est mis en forme avec Bootstrap, mais `action="#"` ne transmet pas les demandes à une adresse e-mail ou à une base de données. Un service de traitement côté serveur ou un service de formulaires devra être configuré pour recevoir réellement les demandes.
