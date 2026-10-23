---
title: "Google Merchant Center Feed - mode d'emploi du vendeur"
sidebar:
  label: "Google Merchant Center Feed - mode d'emploi du vendeur"
description: "Configuration du fichier catalogue, des fichiers enregistrés et de l'adresse du catalogue dans une boutique qui a déjà le module."
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Google merchant center feed sur MyPresta.eu](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/google-merchant-center-feed/)
>
> ---


Le nom technique du module est `gmfeed`, version 2.4.3. Dans la liste des modules s'affiche **Google Merchant Center Feed**. Ce nom est écrit dans le fichier du module et ne vient pas de `translations/fr.php`.

## 1. Où sont les écrans

Il y a deux écrans.

Modules, puis Gestionnaire de modules, puis **Google Merchant Center Feed**, puis Configurer. Cette page a un champ, **Afficher l'arborescence des catégories**.

Catalogue, puis **Flux Google Merchant**. C'est le contrôleur `AdminExportProductsFeedGoogle`. Le titre est **Flux Google Merchant Center**. Les onglets sont **Tableau de bord**, **Flux**, **Mises à jour** et **Create / Edit feed**. Le dernier reste désactivé tant que **Créer un nouveau flux** ou un flux existant n'est pas ouvert. **Create / Edit feed** n'a pas d'entrée dans `translations/fr.php`, l'écran affiche la source anglaise.

Il n'y a pas d'écran d'import ni de bloc sur la fiche produit. La vitrine ne dessine pas de cadre. L'effet public est l'adresse catalogue d'un flux enregistré.

## 2. Ce que l'installation écrit

L'installation lance l'installation parente, enregistre `actionAdminControllerSetMedia`, crée un onglet sous Catalogue et crée les tables du point 8.

La classe de l'onglet est `AdminExportProductsFeedGoogle`. Le libellé passé à l'installation est **Flux Google Merchant**. Le même libellé est écrit pour chaque langue de la boutique qui existe à ce moment.

`actionAdminControllerSetMedia` charge les plugins fancybox et autocomplete seulement lorsque le contrôleur est `AdminExportProductsFeedGoogle`.

La classe n'a pas de méthode `enable()` ni `disable()`.

## 3. Paramètres du module

![Paramètres du module](https://mypresta.eu/docs/images/docs/gmfeed-settings.webp)

L'écran est en anglais. Dans ce mode d'emploi cette page s'appelle **Paramètres du module**.

La légende est **Paramètres du module**. Le bouton est **Save**. Le seul champ est **Afficher l'arborescence des catégories** (`pf_tree`). **Non** vaut 0. **Oui** vaut 1. Si la clé manque, `(int)Configuration::get('pf_tree')` vaut 0 et la liste affiche **Non**. **Save** n'a pas d'entrée pour ce modèle dans `translations/fr.php`, le bouton affiche la source anglaise.

**Save** envoie `submitgmfeedSettings` et écrit `pf_tree`. Le texte ensuite est **Paramètres correctement enregistrés**.

**Oui** fait afficher les catégories parentes dans la liste d'association du formulaire. La description pointe vers `https://i.imgur.com/enzXRaJ.png`. La même description pointe vers **Catalogue > Flux Google Merchant**.

Cette page ne construit pas le fichier catalogue.

## 4. Page du catalogue

![Tableau de bord](https://mypresta.eu/docs/images/docs/gmfeed-dashboard.webp)

L'écran est en anglais. Dans ce mode d'emploi cet onglet s'appelle **Tableau de bord**.

![Flux](https://mypresta.eu/docs/images/docs/gmfeed-feeds.webp)

L'écran est en anglais. Dans ce mode d'emploi cet onglet s'appelle **Flux**.

Ouvrez **Catalogue > Flux Google Merchant**.

**Tableau de bord** affiche les chiffres de `gms` et `gms_log`. Si aucune adresse n'a été appelée, la page affiche la source anglaise **No cron or URL generations yet. Save a feed, then call its catalog URL from a scheduler.**

**Flux** liste les lignes de `gms`, le plus grand `id_gms` en premier. **Créer un nouveau flux** ouvre le formulaire. Dupliquer copie la chaîne de requête enregistrée, retire `export_id_gms`, `id_gms` et `gmfeed_write_key` et ajoute ` (copy)` au nom. Un nom vide part de **Untitled feed**. Le texte ensuite est la source anglaise **Feed duplicated. Review the copy and save if you need a different filename or URL.** Retirer supprime cette ligne `gms`. Le texte est **Feed removed.** Le fichier enregistré sur le disque n'est pas supprimé par cette action.

![Mises à jour](https://mypresta.eu/docs/images/docs/gmfeed-updates.webp)

L'écran est en anglais. Dans ce mode d'emploi cet onglet s'appelle **Mises à jour**.

**Mises à jour** est le formulaire de `lib/updateChecker.php`. **Check now** envoie `submit_settings_updates_now`. **Save** envoie `submit_settings_updates` et écrit `mypresta_updates`. Le constructeur interroge le serveur distant lorsque `mypresta_updates` n'est pas 0 et que `update_gmfeed` a plus de 172800 secondes. La valeur de licence envoyée si `mkey` manque est `nokey`. Un avertissement apparaît lorsque `updatev_gmfeed` est supérieur à 2.4.3 et que la requête n'est pas ajax.

## 5. Formulaire du flux

![Créer un nouveau flux](https://mypresta.eu/docs/images/docs/gmfeed-form.webp)

L'écran est en anglais. Dans ce mode d'emploi cette vue s'appelle **Créer un nouveau flux**. Le cadrage montre le haut du formulaire. Les autres champs suivent plus bas.

**Create feed** et **Edit feed** utilisent le même formulaire. Le nom du flux est obligatoire. **Active** **Yes** / **No** est stocké dans `gms.active`. Un nouveau flux est actif. **Shop** enregistre `gms.id_shop`. Les autres champs sont stockés dans `gms.conf` sous forme de chaîne de requête.

Une clé absente sur un nouveau formulaire prend la valeur du tableau. Pendant l'édition, une clé absente prend cette même valeur et ne lit pas la configuration partagée `gm_`.

| Clé | Valeur par défaut d'un nouveau formulaire | Ce que le code en fait |
|---|---|---|
| `export_file_format` | `csv` | `csv` ou `xml`. Toute autre extension est ramenée à `csv` par `sanitizeExportExtension`. |
| `export_type` | `product` | `sanitizeExportType` ne garde que `products` et `combinations`. Le `product` enregistré est donc traité comme `products`. |
| `export_save_file` | `0` | `0` envoie le catalogue dans la réponse. `1` écrit un fichier sous `/modules/gmfeed/`. |
| `export_filename` | vide | Utilisé seulement pour l'enregistrement dans un fichier. Vide devient le type d'export. Les caractères autres que lettres, chiffres, `_` et `-` sont retirés. |
| `export_identification` | `id_product` | Identifiant produit écrit comme identifiant du catalogue. |
| `export_delimiter` | barre verticale | Séparateur des colonnes CSV. |
| `export_enclosure` | `0` | Valeur d'encadrement passée à l'écriture CSV. |
| `export_language` | `PS_LANG_DEFAULT` | Langue des noms et des descriptions. |
| `export_currency` | `PS_CURRENCY_DEFAULT` | Devise des prix. |
| `export_tax` | `price_tin` | Quelle colonne de prix est remplie. |
| `export_specific` | `1` | Quand la devise par défaut de la boutique diffère de la devise du contexte, une valeur non nulle fait utiliser les prix spécifiques à l'étape du prix. |
| `export_category` | `all` | Catégories incluses dans le catalogue. |
| `export_manufacturers` | `all` | Fabricants inclus. |
| `export_manufacturers_default` | `Default` | Texte de marque quand le produit n'a pas de fabricant. |
| `export_suppliers` | `all` | Fournisseurs inclus. |
| `export_gtin` | `upc` | Quel code produit est écrit comme GTIN. |
| `export_img` | `1` | Type d'image passé à `getImageLink`. La liste affiche les noms des types d'image. |
| `export_what_pictures` | `0` | `0` est la source anglaise **Export cover only** et retire la colonne des images supplémentaires. `1` est **Export all pictures**. |
| `export_active` | false | Passé à `Product::getProducts` comme indicateur actifs seulement. `0` est **Export all products.** `1` est **Export only active products**. |
| `export_instock` | false | `1` saute une ligne quand la quantité est 0 ou moins. `0` est **Export all products.** `1` est **Export only in-stock products**. |
| `export_igid` | `0` | `0` retire `item_group_id`. |
| `export_gender` | `0` | `0` retire la colonne genre. |
| `export_age_group` | `0` | `0` retire la colonne tranche d'âge. |
| `export_size` | `0` | `0` retire la colonne taille. |
| `export_color` | `0` | `0` retire la colonne couleur. |
| `export_shipping_info` | `0` | `0` est **Do not include**. `1` est **Include (shipping price calculated for each item separately)**. `2` est **Set shipping price manually**. |
| `export_product_weight` | `0` | Le poids reste désactivé tant que cette valeur n'est pas changée. |
| `export_product_type` | `0` | Le type de produit reste désactivé tant que cette valeur n'est pas changée. |
| `export_removehtml` | `0` | Une valeur autre que `0` retire le HTML de la description. |
| `export_nophoto_exclude` | `0` | `1` écarte un produit sans photo. |
| `export_adult` | `0` | Adult reste désactivé tant que cette valeur n'est pas changée. |
| `export_storecode` | `0` | `0` retire la colonne code magasin. |
| `export_country_prices` | `PS_COUNTRY_DEFAULT` | Pays utilisé pour le prix. |
| `export_group_prices` | `PS_UNIDENTIFIED_GROUP` | Groupe de clients utilisé pour le prix. |
| `remember_settings` | true | Quand la valeur envoyée est `1`, le même enregistrement écrit aussi `gm_{clé}` dans Configuration. La clé d'écriture, la boutique, l'id du flux et le drapeau actif sont ignorés. |
| `feed_active` | activé pour un nouveau flux | `gms.active`. `0` fait renvoyer par l'adresse HTTP 503 et le texte `Feed is disabled`. |

**Save to file** décrit le répertoire `modules/gmfeed/` et indique que l'écriture du fichier depuis l'adresse exige la clé affichée sur ce formulaire. La clé est `gmfeed_write_key`, un HMAC de `gmfeed.write.` plus l'id boutique, avec `_COOKIE_KEY_`. Un employé connecté écrit le fichier sans cette clé. Toute autre personne reçoit `Access denied`.

Le texte après enregistrement est la source anglaise **Feed saved. Its catalog URL is ready to use.**

## 6. Adresse du catalogue et fichier

L'adresse du catalogue est le contrôleur frontal `feed` plus `?feed=` et l'id `gms`. `gms::getFeedUrl` ajoute `gmfeed_write_key` lorsqu'il construit le lien pour le back-office.

L'ouverture charge la chaîne enregistrée et remplace les valeurs `export_` et `gmfeed_` de la requête, sauf la clé d'écriture et `debug_feed`. Un flux absent, ou un `conf` de 20 caractères ou moins, s'arrête sur `feed does not exists`. Un flux dont `id_shop` est défini et n'est pas la boutique courante s'arrête sur `Feed is not available in this store`.

`debug_feed` affiche les paramètres enregistrés et n'écrit pas le fichier.

Le nom de fichier est le `export_filename` nettoyé plus `.csv`, `.xml` ou `.txt`. Le chemin doit rester dans `/modules/gmfeed/`. `.htaccess` de ce répertoire interdit l'exécution directe des fichiers PHP. `index.php` reste autorisé. Le catalogue est servi par le contrôleur frontal, pas par l'ouverture des fichiers PHP.

Chaque exécution insère `gms_log` : heure, durée, nombre d'articles, statut, fichier enregistré ou non, nom de fichier, format et source `url`.

## 7. Catégories Google

Le formulaire liste les fichiers de taxonomie de `/modules/gmfeed/google/`. Une langue de la boutique est marquée présente lorsque `google/{language_code}.txt` existe. Ce paquet contient `google/en-us.txt`. La première ligne de ce fichier est `# Google_Product_Taxonomy_Version: 2015-02-19`.

Associer une catégorie de la boutique écrit `pixelgoogle` : `id_google`, `id_category`, `id_lang`, `value`. **Afficher l'arborescence des catégories** change seulement le dessin de cette liste.

## 8. Tables

L'installation crée trois tables lorsqu'elles manquent. Le préfixe de la boutique précède chaque nom.

| Table | Ce que l'instruction CREATE écrit |
|---|---|
| `pixelgoogle` | `id_pixelgoogle` auto increment, clé primaire, `id_google`, `id_category`, `id_lang`, `value` varchar 254. Jeu de caractères `utf8`. |
| `gms` | `id_gms` auto increment, `name`, `id_shop` par défaut 0, `conf` text, `active` par défaut 1. Clés `idtoskey` et `id_shop`. L'instruction CREATE n'a pas de clé primaire. |
| `gms_log` | `id_gms_log` auto increment, clé primaire, `id_gms`, `date_add`, `duration_ms`, `items`, `status` par défaut `ok`, `save_file`, `file_name`, `format`, `source` par défaut `url`. |

L'ouverture de la page catalogue exécute `gms::ensureSchema()`. Cela ajoute `gms.active` et `gms.id_shop` s'ils manquent, crée `gms_log` si la table manque, et remplit `id_shop` 0 avec `PS_SHOP_DEFAULT`.

Configuration partagée qui n'est pas une colonne : `pf_tree`, `gm_{champ}` lorsque le formulaire l'écrit hors d'un flux, `mypresta_updates`, `update_gmfeed`, `updatev_gmfeed`.

Fichiers de la page catalogue : `views/css/admin-app.css`, `views/js/admin-app.js`, fancybox, autocomplete. La configuration du module charge fancybox. Le script de recherche d'id vient de `lib/searchTool/`.

## 9. Désinstallation

`uninstall()` supprime l'onglet Catalogue `AdminExportProductsFeedGoogle`, puis lance la désinstallation parente. La méthode parente retire le module et l'enregistrement du hook.

La méthode ne supprime pas `pixelgoogle`, `gms` ni `gms_log`. Elle ne supprime pas `pf_tree`, `mypresta_updates`, `update_gmfeed`, `updatev_gmfeed` ni les clés `gm_`. Elle ne supprime pas les fichiers écrits sous `/modules/gmfeed/`. Une installation ultérieure utilise `CREATE TABLE IF NOT EXISTS`, les lignes laissées dans les tables restent.

## 10. Support

Page du module : [Google Merchant Center Feed](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html).
