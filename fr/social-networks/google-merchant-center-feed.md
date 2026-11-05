---
title: "Google Merchant Center Feed - mode d'emploi du vendeur"
sidebar:
  label: "Google Merchant Center Feed - mode d'emploi du vendeur"
description: "Comment régler le fichier produits pour Google Merchant Center, et que faire quand ce fichier échoue."
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Google merchant center feed sur MyPresta.eu](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/google-merchant-center-feed/)
>
> ---


## 1. Prérequis

Le module tourne sur PrestaShop 1.6, 1.7, 8 et 9, et sur PHP 5.6 à 8.5.

Le serveur doit avoir cURL et JSON. Il n'a pas besoin d'un autre module.

Avec plusieurs dizaines de milliers de produits, l'ouverture de l'adresse du fichier dure plus longtemps et demande plus de mémoire.

Vous créez vous-même le compte Google Merchant Center.

## 2. Installation

1. Envoyez le module dans **Modules**, **Gestionnaire de modules**, et activez-le.
2. Après l'installation, **Catalogue** a l'entrée **Flux Google Merchant**.
3. Le module ne vide pas le cache à l'installation.

La désinstallation retire seulement l'entrée du Catalogue. La liste des fichiers, les associations de catégories, les fichiers enregistrés sur le serveur et le réglage de l'arborescence restent. Ils reviennent quand vous réinstallez le module.

## 3. Configuration

Les captures viennent d'un back-office en anglais. Plus bas, les noms sont en français quand le panneau français les affiche.

### 3.1 Page des paramètres du module

Ouvrez **Modules**, **Gestionnaire de modules**, **Google Merchant Center Feed**, **Configurer**. Le titre est **Paramètres du module**. Il y a un champ.

![Paramètres du module](https://mypresta.eu/docs/images/docs/gmfeed-settings.webp)

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Afficher l'arborescence des catégories** | **Non** | **Oui** montre les catégories parentes pendant que vous associez les catégories Google. Cela ne choisit pas les produits du fichier. |

Cliquez sur **Save**. Vous voyez **Paramètres correctement enregistrés**.

### 3.2 Tableau de bord

Ouvrez **Catalogue**, **Flux Google Merchant**. Le titre est **Flux Google Merchant Center**. L'onglet est **Tableau de bord**.

![Tableau de bord](https://mypresta.eu/docs/images/docs/gmfeed-dashboard.webp)

Le tableau de bord montre combien de fichiers sont enregistrés, combien de fois quelqu'un a ouvert une adresse aujourd'hui, combien de fois sur les 7 derniers jours, et combien de fichiers sont sur le serveur. Le graphique et la liste des derniers passages restent vides tant que personne n'ouvre une adresse. En bas se trouve la liste des fichiers réglés pour un enregistrement sur le serveur.

### 3.3 Liste des fichiers

L'onglet est **Flux**.

![Flux](https://mypresta.eu/docs/images/docs/gmfeed-feeds.webp)

Quand la liste est vide, vous voyez qu'il n'y a pas encore de flux, et **Créer un nouveau flux**.

Quand des fichiers existent, une ligne montre l'état, le nom, la boutique, le dernier passage et l'adresse. **Créer un nouveau flux** est au-dessus de la liste.

- L'interrupteur allume ou éteint un fichier. L'adresse reste.
- Un fichier en direct a une adresse. Google la lit, et la liste est produite à chaque ouverture.
- L'enregistrement sur le serveur a deux adresses. L'adresse de génération construit la liste et écrit le fichier. Dans Google, collez l'adresse du fichier, pas l'adresse de génération. Si le fichier n'est pas encore là, ouvrez d'abord l'adresse de génération.
- **Edit** ouvre le formulaire. Une copie ajoute une marque de copie au nom. **Delete** demande une confirmation et retire la ligne. Le fichier sur le disque reste.

### 3.4 Mises à jour

L'onglet est **Mises à jour**.

![Mises à jour](https://mypresta.eu/docs/images/docs/gmfeed-updates.webp)

- **Mises à jour MyPresta**
- **Check Now** demande une fois s'il existe une version plus récente.
- Notifications automatiques : **Enabled** ou **Disabled**. **Enabled** vérifie environ tous les trois jours et peut afficher un avis dans le back-office.
- **Product Page** ouvre la page du module.
- **Save** enregistre ces réglages.

### 3.5 Formulaire du fichier

Cliquez sur **Créer un nouveau flux** ou **Edit**. En bas se trouvent **Save feed** et **Save & download**.

L'image montre le haut du formulaire.

![Formulaire du fichier](https://mypresta.eu/docs/images/docs/gmfeed-form.webp)

Un nom vide devient **Flux sans titre** à l'enregistrement.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Feed name** | vide, obligatoire | Le nom dans la liste. |
| **Active** | **Yes** | **No** garde l'adresse. L'ouverture dit que le fichier est coupé. |
| **Shop** | la boutique en cours | Le champ n'apparaît qu'avec plusieurs boutiques. L'adresse vaut dans la boutique choisie. |

### 3.6 Options du catalogue

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Remember settings** | **Yes** | Le prochain nouveau fichier démarre avec les mêmes choix. Celui que vous venez d'enregistrer garde les siens. |

### 3.7 Quoi exporter

Ici vous choisissez le fichier que Google lira, et si la liste se construit à l'ouverture ou s'écrit sur le serveur.

![Quoi exporter](https://mypresta.eu/docs/images/docs/gmfeed-form-export.webp)

Laissez **CSV**, sauf si Google doit recevoir du XML. **Products** est une ligne par produit. L'autre choix est une ligne par déclinaison. **Combination title** n'apparaît que dans ce cas. **Save to file** sur **No** affiche la liste tout de suite. **Yes** l'écrit aussi sur le serveur. L'adresse copiée depuis la liste contient déjà la clé. Sans elle, vous voyez **Access denied**.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| Type de fichier | **CSV** | **CSV** ou **XML**. |
| Quoi exporter | **Products** | **Products** : une ligne par produit. L'autre choix : une ligne par déclinaison. |
| **Save to file** | **No** | **No** : l'adresse affiche la liste tout de suite. **Yes** : la liste est aussi écrite sur le serveur. Pour écrire, l'adresse doit contenir la clé de cette page. Sans la clé, vous voyez **Access denied**. Connecté au back-office, vous écrivez le fichier sans coller la clé. |
| **File name** | vide | Lettres, chiffres, trait d'union et tiret bas restent. Un nom vide est rempli à partir du type d'export. |
| Comment reconnaître le produit | id produit | Id produit, id déclinaison, ou les deux. C'est la colonne ID du fichier. |

### 3.8 Taille, genre, couleur et âge

Google demande ces colonnes pour l'habillement et les produits proches. Elles sont coupées au départ. N'allumez un groupe que si la boutique a vraiment cette valeur. Les autres champs apparaissent quand le groupe est sur **Yes**.

![Taille, genre, couleur et âge](https://mypresta.eu/docs/images/docs/gmfeed-form-attributes.webp)

| Groupe | Champs |
|---|---|
| Taille | exporter ou non, attribut de taille, valeur par défaut |
| Genre | exporter ou non, source, caractéristique, attribut, défaut : male, female, unisex |
| Couleur | exporter ou non, source, attribut, caractéristique, valeur par défaut |
| Âge | exporter ou non, source, caractéristique, attribut, défaut : newborn, infant, toddler, kids, adult |

### 3.9 Réglages du fichier

Ici se trouve le contenu d'une ligne : identifiants, livraison, descriptions, noms, stock, images et prix. Laissez les valeurs de départ si Google doit recevoir un catalogue ordinaire.

![Identifiants et livraison](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-a.webp)

![Livraison, descriptions et nom](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-b.webp)

![Format, langue et stock](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-c.webp)

![Images et prix](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-d.webp)

La devise et le pays démarrent sur ceux de la boutique. L'image montre ceux de la boutique de test.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| Id de groupe | **No** | Colonne qui relie les déclinaisons d'un produit. |
| Identifiant unique | UPC | UPC, EAN-13, référence, MPN, ISBN, ou vide. Vide dit que l'identifiant n'existe pas. |
| Champ identifier_exists | **No** | Colonne indiquant si un identifiant existe. |
| Champ adult | ne pas inclure | Le laisser de côté, l'inclure comme true, ou l'inclure comme false. |
| Prix de livraison | ne pas inclure | Calculé par article, ou saisi à la main. |
| Frais de livraison supplémentaires du produit | **No** | Ajoute le supplément de livraison de la fiche produit. |
| Montant de livraison manuel | 0 | Le montant quand la livraison est manuelle. |
| Zone pour calculer la livraison | la première zone | La zone d'où vient le prix de livraison. |
| Poids | **No** | Colonne de poids. |
| Type de produit | **No** | Votre propre chemin de catégories dans le fichier. |
| Ajouter l'id de catégorie au type | **No** | Le numéro de catégorie à côté du nom. |
| Description courte | description courte | Description courte ou description longue. |
| Retirer le HTML des descriptions | **No** | **Yes** enlève les balises. |
| Nom du produit | nom du produit | Ou le méta-titre. |
| Titre de la déclinaison | le nom seul | Le nom, le nom plus la valeur de déclinaison, ou le nom plus « étiquette : valeur ». |
| Format du nom | inchangé | Première lettre, chaque mot, ou tout en minuscules. |
| Caractères à retirer du nom | vide | Les caractères saisis disparaissent du nom. |
| Langue | langue de la boutique | Noms et descriptions dans le fichier. |
| Séparateur | barre verticale | Le caractère entre les colonnes CSV. |
| Guillemets autour du texte | **No** | **Yes** entoure les champs de guillemets. |
| Information de stock | le stock réel | Tous en stock, tous en rupture, tous en réassort, ou le réassort traité comme en stock. |
| Date de disponibilité | vide | La date pour les produits en réassort qui n'ont pas la leur. |
| Quantité | **No** | **Yes** ajoute la quantité. |
| Marque s'il n'y en a pas | Default | Le texte de marque quand le produit n'a pas de fabricant. |
| Taille de l'image | tailles de la boutique | Quelle taille d'image mettre dans l'adresse. |
| Image produit quand la déclinaison n'en a pas | **No** | Pour les déclinaisons sans image propre. |
| Combien d'images | couverture seule | Ou toutes les images. |
| Devise | devise de la boutique | Prix dans le fichier. |
| Taxe dans le prix | taxe comprise | Taxe comprise ou taxe exclue. |
| Prix spécifiques | **Yes** | Quand la devise du fichier n'est pas la devise dans laquelle vous regardez la boutique. |
| Groupe de prix | groupe visiteur | Prix pour ce groupe de clients. |
| Prix unitaire | **No** | Une colonne supplémentaire de prix unitaire. |
| Pays des prix | pays de la boutique | Le pays pour la taxe et les remises. |

### 3.10 Produits choisis

Laissez **All** si tous les fabricants, fournisseurs et catégories doivent entrer. Un seul choix réduit le catalogue. Il ne remplace pas les exclusions plus bas.

![Fabricant, fournisseur et catégorie](https://mypresta.eu/docs/images/docs/gmfeed-form-products.webp)

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| Fabricant | **All** | Un fabricant, ou tous. |
| Fournisseur | **All** | Un fournisseur, ou tous. |
| Catégorie | **All** | Une catégorie, ou toutes. |

### 3.11 Exclusions

Ici sortent les produits qui ont passé le filtre du point 3.10. Au départ, presque rien n'est exclu.

![Exclusions](https://mypresta.eu/docs/images/docs/gmfeed-form-exclude.webp)

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| Catégories à laisser de côté | vide | Saisissez un nom. Les produits de cette catégorie sortent. |
| Produits sans image | **No** | **Yes** laisse de côté les produits sans image. |
| Disponibilité | tous les produits | Ou seulement ceux activés dans la boutique. |
| Stock | tous les produits | Ou seulement ceux en stock. |
| Laisser de côté selon la référence | coupé | Active un filtre sur le début de la référence. Cela vaut aussi pour les déclinaisons. |
| Début de la référence | vide | Texte à partir duquel une référence sort. |
| Laisser de côté moins cher que | coupé | Un seuil de prix dans la devise de la boutique. |
| Montant du seuil | vide | Les produits sous ce montant sortent. |
| Produits nommés | vide | Une recherche des produits à laisser de côté. |

### 3.12 Limite

Laissez 0 si tout le catalogue doit tenir dans un fichier. À côté du champ, vous voyez le nombre de produits de la boutique. Sur un hébergement juste, réglez une limite et un numéro de partie. L'exemple du formulaire : 3000 produits et une limite de 1000 donnent les parties 1, 2 et 3.

![Limite et code magasin](https://mypresta.eu/docs/images/docs/gmfeed-form-limit.webp)

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| Limite de produits | 0 | 0 ou vide veut dire pas de limite. Le nombre de produits de la boutique est affiché à côté du champ. |
| Partie du fichier | 0 | Le numéro de partie quand vous coupez un catalogue en plusieurs fichiers. Avec 3000 produits et une limite de 1000, vous faites les parties 1, 2 et 3. |

### 3.13 Code de magasin

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| Inclure le code magasin | **No** | Une colonne pour le code du magasin. |
| Code magasin | vide | Le même code que dans Google Business. La casse compte. |

### 3.14 Catégories Google

En bas, il y a une ligne par langue de la boutique. **Pair categories** ouvre l'association. **Synchronize** récupère la liste Google de cette langue. Si la liste manque, le bouton est rouge. Sur l'image, en-us a déjà le fichier et fr ne l'a pas.

![Catégories Google](https://mypresta.eu/docs/images/docs/gmfeed-form-categories.webp)

**Afficher l'arborescence des catégories** du point 3.1 ne change que le dessin de cette liste. En bas se trouvent encore **Save & download** et **Save feed**.

**Afficher l'arborescence des catégories** du point 3.1 ne change que le dessin de cette liste. Cela ne change pas les produits qui entrent dans le fichier.

## 4. Boutique

Le client ne voit rien sur la boutique. Il n'y a pas de bloc sur la fiche, dans le panier ni dans le pied de page. Il n'y a pas de capture de la boutique.

Il y a une adresse que Google ou un navigateur ouvre. Copiez-la dans la liste. Ne la construisez pas vous-même.

Une ouverture en direct renvoie du CSV ou du XML. Quand vous enregistrez sur le serveur, l'adresse de génération écrit le fichier, et l'adresse pour Google est celle du fichier.

Ajouter vos propres paramètres ne change rien. Le module utilise les réglages enregistrés sur ce fichier.

Enregistrer le formulaire n'envoie pas les produits à Google. La liste est produite à l'ouverture de l'adresse.

| Ce que vous voyez à l'ouverture | Que faire |
|---|---|
| feed does not exists | Le numéro est faux, ou le fichier a été retiré. Copiez l'adresse depuis la liste. |
| Feed is disabled | Allumez **Active**. |
| Feed is not available in this store | Le fichier appartient à une autre boutique. |
| Access denied | L'enregistrement sur le serveur est allumé, et l'adresse n'a pas la clé. Copiez l'adresse depuis la liste. |
| Invalid export path | Raccourcissez le nom du fichier. |
| Unable to save export file | Vérifiez l'espace disque et le droit d'écriture dans le dossier du module. |

## 5. Problèmes

**Google affiche encore les produits d'hier.** Le module n'envoie rien à Google. Ouvrez l'adresse et vérifiez la liste. Lancez ensuite un téléchargement à la main dans Merchant Center.

**Le fichier ne contient presque pas de produits.** Vérifiez s'il ne reste que les produits activés, que ceux en stock, un fabricant, un fournisseur, une catégorie, des exclusions, une limite ou un numéro de partie.

**L'arborescence est allumée, et le fichier a les mêmes produits.** L'arborescence montre seulement les catégories parentes pendant l'association.

**J'ai désinstallé le module et la liste a disparu.** Réinstallez-le. Les données restent. Seule l'entrée du Catalogue a disparu.

**Un gros catalogue s'arrête au milieu.** Réglez une limite et un numéro de partie. Faites plusieurs fichiers.

## 6. Pour le développeur

### 6.1 Vue d'ensemble

`gmfeed` 2.4.3. La classe `gmfeed` étend `Module`. Le nom dans la liste des modules est la chaîne fixe `Google Merchant Center Feed`. Auteur MyPresta.eu. Onglet `administration`.

Le formulaire enregistre une ligne `gms`. Le champ `conf` est une chaîne de requête. L'adresse publique lit cette ligne, construit le CSV ou le XML et termine la réponse. L'enregistrement dans un fichier l'écrit sous `/modules/gmfeed/`.

### 6.2 Fichiers

- `gmfeed.php` : install, uninstall, la page de paramètres, la clé d'écriture, et le nettoyage du nom, de l'extension et du type.
- `controllers/admin/AdminExportProductsFeedGoogle.php` : tableau de bord, liste, formulaire, enregistrement.
- `controllers/front/feed.php` : génération. `initContent()` appelle `generateFeed()` et `die()`.
- `model/gms.php` : la ligne du fichier et l'adresse. Classe `gms`.
- `model/google.php` : les paires de catégories. Classe `pixelgoogle`.
- `lib/updateChecker.php` : classe `gmfeedUpdate`.
- `lib/searchTool/searchTool.php` : suggestions de catégories et de produits.
- `views/templates/admin/` : `layout.tpl`, `dashboard.tpl`, `feeds.tpl`, `form-chrome.tpl`.
- `google/en-us.txt` : la taxonomie. Première ligne `# Google_Product_Taxonomy_Version: 2015-02-19`.
- `.htaccess` dans le dossier du module bloque l'exécution de PHP.

### 6.3 Contrôleurs

Admin : `AdminExportProductsFeedGoogle`, parent `AdminCatalog`. Vues dans `gmfeed_view` : `dashboard`, `feeds`, `form`, `updates`.

Front : `gmfeedfeedModuleFrontController`. Adresse `module/gmfeed/feed?feed=` plus le numéro.

La clé d'écriture est un HMAC-SHA256 de `gmfeed.write.` plus l'id boutique, secret `_COOKIE_KEY_`. Un employé connecté écrit sans la clé. Les paramètres `export_` et `gmfeed_` reçus sont écartés et remplacés par ceux qui sont enregistrés. La clé et `debug_feed` restent.

Un fichier coupé renvoie HTTP 503 et `Feed is disabled`. Un `conf` vide ou trop court se termine par `feed does not exists`. Un autre `id_shop` se termine par `Feed is not available in this store`.

### 6.4 Hooks

Il y a un hook : `actionAdminControllerSetMedia`. Il charge fancybox et l'autocomplétion seulement sur `AdminExportProductsFeedGoogle`. Le module ne publie pas ses propres hooks. Il n'y a pas de `enable()` ni de `disable()`.

### 6.5 Surcharges

Ce module ne surcharge ni les classes ni les contrôleurs de PrestaShop.

### 6.6 Base de données

| Table | Contenu |
|---|---|
| `pixelgoogle` | Une paire de catégories : `id_google`, `id_category`, `id_lang`, `value`. |
| `gms` | Un fichier : `name`, `id_shop`, `conf`, `active`. `CREATE` ne pose pas de clé primaire. |
| `gms_log` | Une ouverture de l'adresse : heure, nombre, statut, écriture du fichier, nom, format, source. |

`ensureSchema` sur la page catalogue ajoute `active` et `id_shop`, crée `gms_log` s'il manque, et remplit `id_shop` 0 avec la boutique par défaut. La désinstallation ne supprime pas les tables.

### 6.7 Clés et traductions

`pf_tree` : une clé absente signifie coupée. Le reste du formulaire vit dans `gms.conf`. **Remember settings** envoyé à 1 copie aussi les champs vers `gm_{champ}`, sans la clé d'écriture, le lien court, actif, la boutique et l'id du fichier. Sur un fichier ouvert, un champ absent prend la valeur de départ du formulaire, pas la copie `gm_`. Une ancienne clé `notepad_products` est copiée vers `gmfeed_products` quand la nouvelle manque.

Mises à jour : `mypresta_updates`, `update_gmfeed` (172800 secondes entre les vérifications), `updatev_gmfeed`. Un `mkey` absent est envoyé comme `nokey`.

Une nouvelle langue est un fichier `translations/{iso}.php`. Les textes de `$this->l()` partent de la source anglaise. Le nom dans la liste des modules ne passe pas par `$this->l()`. Dans `translations/de.php`, les textes de la page de paramètres sont en tchèque.

Le type d'export enregistré `product` est traité comme `products` à la génération. Les extensions permises sont `csv`, `xml` et `txt`. Le formulaire affiche CSV et XML.

### 6.8 Étendre

Le thème n'a rien à surcharger sur la page boutique, parce que le front ne rend pas de modèle. Un autre ordre de colonnes demande de modifier le code du module. Vous ajoutez une taxonomie dans une autre langue sous la forme `google/{code}.txt`.

## 7. Support

Page du module : [Google Merchant Center Feed](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html).

Pour écrire au sujet de ce module, connectez-vous à votre compte client sur [mypresta.eu](https://mypresta.eu/), ouvrez le [contact](https://mypresta.eu/contact.html) et choisissez le sujet **Support for paid modules**. Le formulaire indique que la connexion est requise. Une fois connecté, choisissez ce module dans l'historique des achats.
