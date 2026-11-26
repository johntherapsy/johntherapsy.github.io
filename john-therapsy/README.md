# john.therapsy : guide du blog

Ce dossier contient tout le blog. Il est conçu pour être hébergé **gratuitement** sur GitHub Pages, et pour que tu puisses publier des articles **sans coder**, directement depuis le site de GitHub.

---

## 1. Mettre le blog en ligne (une seule fois)

### a) Créer un compte GitHub
Va sur <https://github.com/signup> et crée un compte gratuit. Choisis bien ton pseudo : il apparaîtra dans l'adresse provisoire du blog (`ton-pseudo.github.io`).

### b) Créer le dépôt
1. En haut à droite, clique sur **+** puis **New repository**.
2. Dans **Repository name**, écris exactement : `ton-pseudo.github.io` (remplace `ton-pseudo` par ton vrai pseudo).
3. Laisse le dépôt en **Public** (obligatoire pour l'hébergement gratuit).
4. Clique sur **Create repository**.

### c) Envoyer les fichiers
1. Sur la page du dépôt, clique sur le lien **uploading an existing file**.
2. Ouvre le dossier `john-therapsy` sur ton Mac, sélectionne **tout son contenu** (Cmd + A) et glisse-le dans la fenêtre GitHub. Glisse bien le *contenu* du dossier, pas le dossier lui-même.
3. Attends que tous les fichiers soient chargés, puis clique sur **Commit changes**.

### d) Activer la publication
1. Dans le dépôt, va dans **Settings** puis **Pages** (menu de gauche).
2. Dans **Source**, choisis **Deploy from a branch**, puis la branche **main** et le dossier **/ (root)**. Clique sur **Save**.
3. Après 2 à 5 minutes, le blog est en ligne sur `https://ton-pseudo.github.io`.

---

## 2. Écrire un article

1. Ouvre le fichier `_modele-article.md` et copie tout son contenu.
2. Va dans le dossier `_posts`, clique sur **Add file** puis **Create new file**.
3. Nomme le fichier avec la date et un titre court, sans accents ni espaces :
   `2026-12-03-apprivoiser-ses-emotions.md`
4. Colle le modèle, remplis le titre, la description et la rubrique, puis écris ton texte.
5. Clique sur **Commit changes**. L'article apparaît sur le blog quelques minutes plus tard.

**Rubriques possibles :** `psychologie`, `spiritualite`, `bien-etre`

**Modifier un article :** ouvre-le dans `_posts` et clique sur l'icône crayon ✏️.
**Supprimer un article :** ouvre-le, clique sur les trois points **…** puis **Delete file**.

> ⚠️ Un article daté dans le futur n'apparaît pas sur le blog. Utilise la date du jour.

### Mise en forme rapide

| Tu écris | Résultat |
|---|---|
| `**mot**` | **gras** |
| `*mot*` | *italique* |
| `## Titre` | un intertitre |
| `- élément` | une liste à puces |
| `> phrase` | une citation |
| `[texte](https://lien.fr)` | un lien |
| `---` seul sur une ligne | un séparateur ✦ ✦ ✦ |

### Ajouter une image
1. Va dans le dossier `assets/img`, clique sur **Add file** puis **Upload files**, et dépose ton image (de préférence en `.jpg`, moins de 500 Ko, avec un nom sans accents ni espaces).
2. Dans ton article, écris : `![Description de l'image](/assets/img/nom-de-l-image.jpg)`

---

## 3. Brancher ton nom de domaine

1. Achète le domaine chez un registraire (OVH, Gandi, etc.).
2. Sur GitHub : **Settings** puis **Pages**, puis **Custom domain**. Écris ton domaine (par exemple `johntherapsy.fr`) et clique sur **Save**.
3. Chez ton registraire, dans la zone DNS du domaine, ajoute :

   | Type | Nom / Sous-domaine | Valeur |
   |---|---|---|
   | A | @ (vide) | `185.199.108.153` |
   | A | @ (vide) | `185.199.109.153` |
   | A | @ (vide) | `185.199.110.153` |
   | A | @ (vide) | `185.199.111.153` |
   | CNAME | www | `ton-pseudo.github.io.` |

   Supprime les éventuels enregistrements A ou CNAME déjà présents pour `@` et `www` (souvent une page « parking » du registraire).
4. Attends que tout se propage (de quelques minutes à 24 h), puis retourne dans **Settings** puis **Pages** et coche **Enforce HTTPS**.

---

## 4. Changer les réglages

- **Nom, description, e-mail de contact :** fichier `_config.yml`
- **Page « À propos » :** fichier `a-propos.md`
- **Rubriques (noms et descriptions) :** fichier `_data/rubriques.yml`

Pour le design (couleurs, mise en page, nouvelles fonctionnalités), demande à Claude : les fichiers `_layouts`, `_includes` et `assets/css` sont plus délicats à modifier à la main.

---

## En cas de souci

Si une modification n'apparaît pas, ouvre l'onglet **Actions** du dépôt : une croix rouge ❌ indique une erreur de publication. Le plus souvent, c'est une erreur dans l'en-tête d'un article (les lignes entre les deux `---`) : un guillemet oublié, ou deux-points dans le titre sans guillemets autour.
