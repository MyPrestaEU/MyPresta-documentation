---
title: "Microsoft Merchant Center Product Feed - documentation et manuel utilisateur"
description: "Manuel destiné aux utilisateurs qui possèdent déjà le module et doivent configurer des flux Microsoft Merchant Center ou résoudre des problèmes de génération et de catalogue."
sidebar:
  label: "Microsoft Merchant Center Product Feed - documentation et manuel utilisateur"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Microsoft Merchant Center Product Feed sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/microsoft-merchant-center-product-feed.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/microsoft-merchant-center-product-feed/)
>
> ---


## 1. Prérequis

Avant d'installer le module, vérifiez que la boutique et l'hébergement répondent aux exigences suivantes :

- PrestaShop 1.7, 8 ou 9.
- PHP 7.1 à 8.5.
- Extensions PHP : cURL, JSON, hash et SimpleXML pour générer des flux XML.
- Un compte Microsoft Merchant Center actif permettant de créer un catalogue et d'indiquer l'adresse de son flux.
- Aucun autre module PrestaShop n'est requis.

Un catalogue volumineux exige assez de temps d'exécution et de mémoire PHP pour collecter les produits, calculer les prix et la livraison, puis construire la sortie. Si un flux complet dépasse les limites de l'hébergement, utilisez **Limit number of products in feed** avec **Part of feed** pour le diviser.

## 2. Installation

1. Ouvrez **Modules → Module Manager**.
2. Cliquez sur **Upload a module** et envoyez le fichier ZIP du module.
3. Installez **Microsoft Merchant Center Feed**.
4. Ouvrez **Catalog → Microsoft Merchant Feed**. Cet espace sert à créer les flux, copier les adresses, surveiller les exécutions et associer les catégories.
5. Si des noms de catégories se répètent dans différentes branches, ouvrez **Modules → Module Manager**, recherchez le module, cliquez sur **Configure** et activez **Show categories tree**.

L'installation ne vide pas le cache PrestaShop.

Pour supprimer le module, désinstallez-le dans **Module Manager**. La désinstallation retire **Microsoft Merchant Feed** du menu **Catalog**, mais conserve les flux, l'historique, les associations de catégories, les réglages mémorisés, les fichiers générés et les taxonomies téléchargées. Une réinstallation peut donc réutiliser ces données.

## 3. Configuration et utilisation du back-office

Pour publier un catalogue :

1. Ouvrez **Catalog → Microsoft Merchant Feed** et sélectionnez **Create new feed**.
2. Saisissez un **Feed name**, laissez **Active** sur **Yes**, choisissez les options, associez les **Microsoft Categories**, puis cliquez sur **Save feed**.
3. Choisissez une méthode :
   - Pour un flux dynamique, laissez **Save to file** sur **No**. Copiez la **Live catalog URL**. Microsoft appelle cette adresse et le module régénère le flux à chaque requête.
   - Pour un fichier statique, mettez **Save to file** sur **Yes**. Appelez la **Generate / cron URL** secrète manuellement ou avec un planificateur. Après une première génération réussie, copiez la **Catalog file URL**. Fournissez à Microsoft l'adresse du fichier, jamais l'adresse de génération.
4. Créez ou ouvrez le catalogue correspondant dans Microsoft Merchant Center et collez l'adresse dynamique ou celle du fichier comme source.
5. Revenez au **Dashboard** pour vérifier les exécutions et la disponibilité du fichier.
6. Dans **Microsoft Categories**, synchronisez la taxonomie de la langue, puis utilisez **Pair categories** pour relier les catégories de la boutique à celles de Microsoft.
7. Pour suspendre la publication sans changer l'adresse, désactivez le flux dans **Feeds**. **Active** sur **No** arrête la génération ; sa réactivation reprend le même flux à la même adresse.

Les captures d'écran de ce manuel proviennent d'un back-office en anglais.

### 3.1 Réglages du module

Ouvrez **Modules → Module Manager**, recherchez **Microsoft Merchant Center Feed**, puis cliquez sur **Configure**.

![Réglages du module avec Show categories tree](https://mypresta.eu/docs/images/docs/mmcfeed-module-settings.webp)

| Champ | Valeur initiale | Fonction |
|---|---|---|
| **Show categories tree** | No | L'espace du flux se trouve sous **Catalog → Microsoft Merchant Feed**. Mettez ce champ sur **Yes** pour afficher le chemin parent de chaque catégorie dans la fenêtre d'association et distinguer les noms identiques. Cliquez sur **Save** ; la page confirme **Settings saved properly**. |

### 3.2 Liste des flux

Ouvrez **Catalog → Microsoft Merchant Feed**, puis sélectionnez **Feeds**.

![Liste des flux](https://mypresta.eu/docs/images/docs/mmcfeed-feeds.webp)

En l'absence de flux, la page affiche **You have no feeds yet** et **Create your first feed**. Sinon, utilisez les colonnes suivantes :

| Colonne | Contenu |
|---|---|
| **Status** | **On** ou **Off**. Suspendez ou reprenez le flux sans le supprimer ni changer son adresse. |
| **Feed** | Nom et badges de format, export de produits ou variantes, langue et mode **Live** ou **File**. |
| **Shop** | Boutique propriétaire. En multiboutique, un flux extérieur à la boutique actuelle porte la mention **Not available in this store**. |
| **Last run** | Nombre d'éléments et heure de la dernière exécution. Avant le premier appel : **Never** et **No cron call yet**. |
| **Catalog URL** | En direct, adresse **Live catalog**. En fichier, adresses **Generate / cron** secrète et **Catalog file** publique. Utilisez le bouton de copie adjacent. |
| **Actions** | Commandes disponibles. |

- **Edit** ouvre les options enregistrées.
- **Duplicate** crée une copie à vérifier. Modifiez son nom, fichier, boutique, filtres ou autres réglages si elle doit être indépendante.
- **Generate** lance le générateur en mode fichier.
- **Open file** ouvre le fichier enregistré.
- **Open** génère et ouvre un flux dynamique.
- **Delete** supprime définitivement le flux après confirmation.

La page peut afficher :

- **Feed saved. Its catalog URL is ready to use.**
- **Feed removed.**
- **Feed duplicated. Review the copy and save if you need a different filename or URL.**

### 3.3 Dashboard

Sélectionnez **Dashboard** pour surveiller l'activité.

![Dashboard](https://mypresta.eu/docs/images/docs/mmcfeed-dashboard.webp)

Le résumé présente **Saved feeds**, **Cron runs today**, les produits générés aujourd'hui, **Runs last 7 days**, la durée moyenne et les **Saved files** prêts. **Catalog generation activity** couvre 14 jours. **Recent runs** indique le flux, l'heure, le nombre d'éléments, la durée, le format et l'écriture éventuelle d'un fichier.

La table **Generated files** indique boutique, nom, taille, état et dernière mise à jour. **Waiting for first cron** signifie que l'adresse de génération n'a pas encore créé le fichier. **On disk** signifie qu'il est disponible à son adresse publique.

### 3.4 Onglet Updates

Sélectionnez **Updates** pour rechercher les mises à jour MyPresta.

![Onglet Updates](https://mypresta.eu/docs/images/docs/mmcfeed-updates.webp)

| Champ | Valeur initiale | Fonction |
|---|---|---|
| **Manual Check** | Aucun résultat avant vérification | Cliquez sur **Check Now** après l'installation ou lorsqu'une version est attendue. Le module compare les versions et affiche **Module is up to date!** ou **New version available!**. |
| **Automatic Notifications** | Préférence MyPresta partagée actuelle | **Enabled** effectue une vérification environ tous les trois jours et avertit les employés. **Disabled** convient à une gestion manuelle. Cliquez sur **Save**. |
| **Product Page** | Lien disponible | Ouvre la page officielle et ses ressources d'assistance. Aucun réglage n'est requis. |

### 3.5 Créer/modifier un flux

Sélectionnez **Create new feed** ou cliquez sur **Edit**. Les champs suivent l'ordre de l'écran. Les options dépendantes de la boutique proviennent des langues, devises, pays, groupes, types d'image, caractéristiques, attributs, catégories, fabricants, fournisseurs, zones et boutiques configurés dans PrestaShop.

**Save feed** enregistre et revient à la liste. **Save & download** enregistre puis télécharge immédiatement un CSV ou XML. En modification, la page affiche aussi la **Live catalog URL** ou les **Generate / cron URL** et **Catalog file URL**.

![Créer ou modifier : nom, état, format, type et mode fichier](https://mypresta.eu/docs/images/docs/mmcfeed-form-top.webp)

**Identité et sortie du flux**

| Champ | Valeur initiale | Fonction |
|---|---|---|
| **Feed name** | Vide | Saisissez un nom obligatoire et reconnaissable. Une valeur vide arrivée à l'enregistrement devient **Untitled feed**. |
| **Active** | Yes | Laissez activé pour autoriser la génération. **No** suspend le flux tout en conservant son adresse et ses réglages. |
| **Shop** | Boutique actuelle ; multiboutique seulement | Affecte le flux à une boutique. Son adresse ne fonctionne que pour elle. |
| **Remember settings** | Yes | Mémorise les choix pour le prochain flux. Choisissez **No** si ces choix ne doivent pas devenir les valeurs initiales. |
| **Type of file module will generate** | CSV | **CSV** produit un flux texte ; **XML** un flux Atom. Pour TSV, choisissez **CSV** et `Tab` dans **Delimiter**. |
| **What you want to export?** | Products | **Products** crée une ligne par produit ; **All products variants** exporte séparément les déclinaisons. |
| **Save to file** | No | **No** génère le flux à chaque appel. **Yes** écrit un fichier statique via l'adresse secrète ; transmettez à Microsoft l'adresse publique distincte. |
| **File name** | Vide | Avec **Save to file**, indiquez le nom de base. Vide, il reprend le type d'export. Utilisez lettres, chiffres, tirets ou traits de soulignement. |
| **How to identify product?** | `id_product` | Choisissez `id_product`, `id_combination` ou `id_product-id_attribute`. Utilisez une option tenant compte des déclinaisons lorsqu'elles sont exportées séparément. |

**Taille, genre, couleur et tranche d'âge**

![Champs de taille, genre, couleur et âge](https://mypresta.eu/docs/images/docs/mmcfeed-form-attributes.webp)

| Champ | Valeur initiale | Fonction |
|---|---|---|
| **Export size** | No | **Yes** inclut `size`. |
| **Size attribute** | None | Sélectionnez le groupe contenant la taille. Maintenez Ctrl pour plusieurs groupes. En l'absence de valeur, **Default size value** est utilisé. |
| **Default size value** | Vide | Taille de remplacement. |
| **Export gender** | No | **Yes** inclut `gender`. |
| **Export gender value from** | Aucune source | Choisissez **Attribute** ou **Feature**, puis le champ source associé. |
| **Gender feature** | Aucune caractéristique | Avec **Feature**, sélectionnez la caractéristique du genre. |
| **Gender attribute** | Aucun attribut | Avec **Attribute**, sélectionnez le groupe du genre. |
| **Default gender value** | Vide | Choisissez **Male**, **Female** ou **Unisex** comme valeur de remplacement. |
| **Export color** | No | **Yes** inclut `color`. |
| **Export color value from** | Aucune source | Choisissez **Attribute** ou **Feature**. |
| **Color attribute** | Aucun attribut | Groupe d'attributs contenant la couleur. |
| **Color feature** | Aucune caractéristique | Caractéristique contenant la couleur. |
| **Default color value** | Vide | Valeur de remplacement. Employez des noms de couleurs anglais, acceptés par Microsoft. |
| **Export age_group** | No | **Yes** inclut `age_group`. |
| **Export age group value from** | Aucune source | Choisissez **Attribute** ou **Feature**. |
| **age group feature** | Aucune caractéristique | Caractéristique contenant la tranche d'âge. |
| **age group attribute** | Aucun attribut | Groupe contenant la tranche d'âge. |
| **Default age group value** | Aucune valeur | Choisissez **adult**, **kids**, **toddler**, **infant** ou la valeur affichée **newbord**. En production, respectez les valeurs Microsoft. |

**Champs, livraison, texte, stock, images et prix**

![Réglages du flux, identifiants, livraison, descriptions, langue et séparateur](https://mypresta.eu/docs/images/docs/mmcfeed-form-feed-settings.webp)

| Champ | Valeur initiale | Fonction |
|---|---|---|
| **Include item_group_id** | No | **Yes** regroupe les variantes différant par taille, couleur, motif, âge ou genre. |
| **Unique product identifier** | Product UPC barcode | Choisissez **Product UPC barcode**, **Product ean13 / JAN barcode**, **Product reference number**, **Product MPN code**, **Product ISBN code** ou **Make this field empty, identifier_exists field will have value false then**. Fournissez les identifiants fabricant disponibles. |
| **Include identifier_exists field** | No | **Yes** ajoute `identifier_exists`. |
| **Include adult field** | Do not include | Choisissez **Include as true**, **Include as false** ou **- do not include -**. N'utilisez pas l'étiquette sans rapport **Lowercase all letters, example: product name**. |
| **Include shipping price** | Do not include | Choisissez **Do not include**, **Include (shipping price calculated for each item separately)** ou **Set shipping price manually**. Le calcul automatique est propre à chaque article. |
| **Include product's additional shipping cost** | No | **Yes** ajoute le supplément de livraison du produit. |
| **Manual shipping value** | 0 | Montant appliqué à chaque article en mode manuel. |
| **Automatic shipping price zone select** | Zone initiale | Zone de destination du calcul automatique, plus gourmand qu'un forfait manuel. |
| **Include weight** | No | **Yes** inclut le poids avec l'unité de la boutique. |
| **Product type** | No | **Yes** inclut la structure interne comme `product_type`. |
| **Product type - include category ID** | No | Ajoute l'ID pour distinguer les catégories homonymes. |
| **Short description** | Short description | Choisissez **Short description** ou **Long description** comme source. |
| **Remove html from descriptions** | Yes | Microsoft exige du texte brut. Les balises et retours gênants sont retirés même avec **No** ; conservez **Yes**. |
| **Product name** | Product name | Choisissez **Product name** ou **Meta title**. |
| **Format name** | Do not format name | Aucun changement, première lettre ou chaque mot en capitale, ou tout en minuscules. |
| **Remove selected characters from product name** | Vide | `x=,` retire `x`, `=` et `,`. Laissez vraiment vide pour ne rien retirer. |
| **Language** | Langue par défaut | Langue des titres, descriptions et données traduites. |
| **Delimiter** | `|` | Séparateur CSV. Saisissez `Tab` pour TSV, recommandé par Microsoft. Sans effet sur XML. |
| **Wrap strings in double quotes** | Yes | Évite que les séparateurs ou caractères spéciaux cassent les lignes CSV. |
| **Information about stock** | Include real stock information | Utilisez le stock réel ou forcez **in-stock**, **out-of-stock** ou **backorder**. La dernière option traite les commandes en attente autorisées comme en stock. |
| **Availability date** | Vide | Date de remplacement exigée pour les articles en attente sans date individuelle. |
| **Include quantity info** | No | **Yes** ajoute la quantité du produit ou de la déclinaison. |
| **Default manufacturer value** | `Default` | Marque de remplacement sans fabricant. |
| **Image size for product pictures** | Type initial de la boutique | Type d'image PrestaShop utilisé dans les URL. |
| **Use default product picture if combination will not have associated photo** | No | **Yes** utilise l'image principale si une déclinaison n'en a pas. |
| **How many pictures you want to export?** | Export cover only | **Export cover only** ou **Export all pictures**, qui ajoute des liens. |
| **Currency** | Devise par défaut | Devise des prix, à faire correspondre au marché Microsoft. |
| **Price tax included or excluded** | Price Tax Included | Inclut ou exclut les taxes des prix ordinaires et promotionnels. |
| **Include specific prices** | Yes | Conservez si les prix spécifiques PrestaShop doivent être reflétés. |
| **Export prices for selected group** | Groupe client non identifié | Contexte de prix utilisé. |
| **Export also unit price** | No | **Yes** ajoute les mesures de prix unitaire disponibles. |
| **Export prices for selected country** | Pays par défaut | Contexte fiscal et de remises par pays. |

**Sélection, exclusions, limites, stock local et catégories**

![Filtres, limites, code magasin et Microsoft Categories](https://mypresta.eu/docs/images/docs/mmcfeed-form-filters.webp)

| Champ | Valeur initiale | Fonction |
|---|---|---|
| **Product Manufacturer** | All | Tous les fabricants ou celui sélectionné. |
| **Product Supplier** | All | Tous les fournisseurs ou celui sélectionné. |
| **Product Category** | All | Toutes les catégories ou celle sélectionnée. |
| **Exclude categories** | Vide | Recherchez et ajoutez les catégories à exclure. Leurs produits sont omis. |
| **Exclude products without pictures** | No | **Yes** exclut les produits sans image exploitable. |
| **Products's availability** | Export all products | **Export only active products** exclut les produits désactivés. |
| **Products's stock** | Export all products | **Export only in-stock products** exclut les produits sans stock. |
| **Exclude products with specific reference** | No | **Yes** active le filtre par préfixe de référence. |
| **Exclude product where reference starts with:** | Vide | Préfixe à exclure pour produits et déclinaisons. |
| **Exclude products worth less than defined value** | No | **Yes** exclut sous une valeur minimale dans la devise par défaut. |
| **Value of products (worth less) to exclude** | Vide | Valeur minimale du filtre précédent. |
| **Exclude products** | Liste vide | Recherchez et sélectionnez un produit. **Add all search results** ajoute tous les résultats ; le bouton de suppression retire un élément. |
| **Limit number of products in feed** | 0 | Maximum d'articles. Vide ou `0` signifie sans limite. Utile lorsque temps ou mémoire sont insuffisants. |
| **Part of feed** | 0 | `0` sans découpage. Pour 3 000 produits et une limite de 1 000, créez les parties 1, 2 et 3. |
| **Include store code to feed** | No | **Yes** identifie un magasin physique dans un flux de stock local. Utilisez l'identifiant du compte Microsoft. |
| **Store code** | Vide | Identifiant alphanumérique exact, sensible à la casse. |
| **Microsoft Categories** | Taxonomie pas forcément synchronisée | Vérifiez chaque langue. Cliquez sur **Synchronize** ou choisissez **Synchronize specific**, puis **Pair categories**. L'icône de répétition applique une valeur partout ; l'icône de suppression retire l'association. |

## 4. Boutique et adresses du flux

Le module n'ajoute aucun bloc, bouton, contenu produit, formulaire, page de compte ni autre interface à la boutique. Les clients n'interagissent pas avec lui.

- **Live catalog URL** régénère le catalogue à chaque requête, sans fichier statique.
- **Generate / cron URL** contient le secret d'écriture. Appelez-la via un planificateur ou **Generate** et ne la fournissez pas à Microsoft.
- **Catalog file URL** pointe vers le fichier statique. Utilisez-la comme source lorsque **Save to file** est actif.

| Message | Action |
|---|---|
| **Feed is disabled** | Dans **Feeds**, passez sur **On**, ou mettez **Active** sur **Yes**. |
| **feed does not exists** | Recopiez l'adresse depuis **Feeds**. Le flux est supprimé, l'adresse incomplète ou la configuration invalide. |
| **Feed is not available in this store** | Passez à la boutique affectée, modifiez **Shop** et recopiez l'adresse. |
| **Access denied** | Utilisez la **Generate / cron URL** complète sans modifier sa partie secrète. |

## 5. Problèmes et solutions

### 5.1 Le flux est indiqué comme désactivé

**Symptôme :** **Feed is disabled**.  
**Cause :** Le statut est coupé ou **Active** vaut **No**.  
**Action :** Ouvrez **Catalog → Microsoft Merchant Feed → Feeds** et passez sur **On**. L'adresse reste valide.

### 5.2 Le flux n'existe pas

**Symptôme :** **feed does not exists**.  
**Cause :** Flux supprimé, adresse incomplète ou configuration inutilisable.  
**Action :** Recopiez l'adresse dans **Feeds** ou recréez le flux.

### 5.3 Le flux appartient à une autre boutique

**Symptôme :** **Not available in this store** ou **Feed is not available in this store**.  
**Cause :** Affectation à une autre boutique.  
**Action :** Changez de boutique ou modifiez **Shop**, enregistrez et recopiez l'adresse.

### 5.4 La génération de fichier refuse l'accès

**Symptôme :** **Access denied**, fichier non actualisé.  
**Cause :** L'autorisation secrète manque dans l'adresse.  
**Action :** Recopiez **Generate / cron URL**, utilisez-la sans modification et gardez-la privée.

### 5.5 Microsoft reçoit la réponse du générateur

**Symptôme :** La récupération échoue ou relance une génération malgré **Save to file**.  
**Cause :** La **Generate / cron URL** a été fournie à Microsoft.  
**Action :** Réservez-la au planificateur, vérifiez **On disk** dans **Dashboard**, puis fournissez **Catalog file URL**.

### 5.6 Le flux est vide ou incomplet

**Symptôme :** La génération réussit avec trop peu d'articles.  
**Cause :** Les filtres de fabricant, fournisseur, catégorie, exclusions, image, activité, stock, référence, valeur, limite ou partie retirent des produits.  
**Action :** Choisissez temporairement **All**, désactivez les exclusions, videz les listes et mettez limite et partie à `0`. Réintroduisez ensuite chaque filtre.

### 5.7 Les catégories Microsoft manquent

**Symptôme :** Valeurs absentes ou recherche impossible dans **Pair categories**.  
**Cause :** Taxonomie non synchronisée ou catégories non associées.  
**Action :** Dans **Microsoft Categories**, utilisez **Synchronize** ou **Synchronize specific**, puis **Pair categories**.

### 5.8 Un grand catalogue dépasse le temps ou la mémoire

**Symptôme :** Arrêt, lenteur ou fichier non actualisé.  
**Cause :** L'hébergement ne peut pas traiter catalogue, prix, images et livraison automatique en une fois.  
**Action :** Définissez **Limit number of products in feed**, créez des **Part of feed** successives, utilisez si possible un forfait de livraison et planifiez les parties séparément.

### 5.9 Microsoft signale des problèmes de qualité

**Symptôme :** Avertissements sur identifiants, descriptions, prix, disponibilité, images, variantes, âge, genre, couleurs ou livraison.  
**Cause :** Sources vides, valeurs non admises ou marché incohérent.  
**Action :** Alignez **Language**, **Currency**, pays et taxes. Fournissez GTIN, marque, texte brut, disponibilité, images et catégories. Pour l'habillement, vérifiez **size**, **gender**, **color**, **age_group** et **item_group_id**, puis régénérez.

## 6. Référence développeur

### 6.1 Vue d'ensemble du module

| Élément | Valeur |
|---|---|
| Nom technique | `mmcfeed` |
| Version | `1.1.0` |
| Nom affiché | `Microsoft Merchant Center Feed` |
| Auteur | `MyPresta.eu` |
| Onglet module | `administration` |
| Onglet back-office | `AdminExportProductsFeedMicrosoft`, sous `AdminCatalog` |
| Endpoint frontal | `controllers/front/feed.php` |

`mmcfeed` étend `Module`. L'ObjectModel `mmc` stocke nom, boutique, état actif et configuration sérialisée. Les téléchargements du back-office et le contrôleur frontal construisent un CSV ou XML depuis les données PrestaShop. Le mode fichier écrit un nom assaini dans le répertoire du module ; le mode direct diffuse la réponse.

### 6.2 Fichiers et classes importants

| Fichier | Responsabilité |
|---|---|
| `mmcfeed.php` | Métadonnées, installation, formulaire global, assainissement, chemins sûrs et validation HMAC. |
| `controllers/admin/AdminExportProductsFeedMicrosoft.php` | Dashboard, liste, formulaire, duplication, suppression, taxonomie, export et valeurs mémorisées. |
| `controllers/front/feed.php` | Charge et valide le flux, applique les options, diffuse ou écrit le fichier. |
| `model/mmc.php` | ObjectModel `mmc`, schéma, URL, liste, journal, statistiques et fichiers. |
| `model/categorymap.php` | ObjectModel `pixelgoogle` des associations. |
| `model/google.php` | Duplique `pixelgoogle` de `model/categorymap.php` ; charger les deux redéclare la classe. |
| `lib/updateChecker.php` | `mmcfeedUpdate`, vérifications et formulaire Updates. |
| `lib/searchTool/searchTool.php` | Autocomplétion de produits et catégories. |
| `views/templates/admin/layout.tpl` | En-tête, navigation, messages et ressources. |
| `views/templates/admin/feeds.tpl` | Cartes, URL, états et actions. |
| `views/templates/admin/dashboard.tpl` | Indicateurs, graphique, exécutions et fichiers. |
| `views/templates/admin/form-chrome.tpl` | En-tête du formulaire et URL. |
| `views/category_taxonomy.tpl` | État, synchronisation et association. |
| `views/categories-fancybox.tpl` | Dialogue d'association et chemins parents. |
| `views/exclude-products.tpl` | Autocomplétion et liste d'exclusion. |
| `views/js/admin-app.js` et `views/css/admin-app.css` | Interactions et styles. |

### 6.3 Contrôleurs et requêtes

`AdminExportProductsFeedMicrosoftController` étend `ModuleAdminController`. `mmcfeed_view` sélectionne `dashboard`, `feeds`, `updates` ou `form`. Il traite :

- `saveonly`, enregistrement puis retour à la liste ;
- `submitExport`, enregistrement et téléchargement ;
- `updatemmc` avec `id_mmc` ;
- `duplicatemmc` et `deletemmc` ;
- AJAX `toggleFeedActive` ;
- la synchronisation, les associations, l'autocomplétion et leur enregistrement/suppression via AJAX.

`mmcfeedfeedModuleFrontController` étend `ModuleFrontController`. Il accepte l'ID enregistré, ne charge que les paramètres stockés, refuse un flux absent, désactivé ou d'une autre boutique, puis lance la génération. Le mode fichier exige `mmcfeed_write_key`. Les paramètres entrants de débogage et d'export sont ignorés pour empêcher le remplacement des réglages.

Les fichiers `index.php` sont des marqueurs ; aucun second contrôleur frontal fonctionnel n'existe.

### 6.4 Hooks et cycle de vie

Le seul hook est `actionAdminControllerSetMedia`. Pour `AdminExportProductsFeedMicrosoft`, il active Fancybox et l'autocomplétion jQuery, sans sortie frontale.

Le module ne définit pas de méthodes `enable()` ou `disable()` personnalisées ni de hooks propres.

`install()` appelle le parent, enregistre le hook, crée l'onglet et les tables et complète le schéma, sans vider le cache. `uninstall()` retire l'onglet et appelle `parent::uninstall()` sans supprimer tables, configuration, flux, fichiers ou taxonomies.

### 6.5 Overrides

Le module n'installe aucun override de classe ou contrôleur PrestaShop.

### 6.6 Base de données

Le préfixe réel est celui configuré dans la boutique.

| Table | Contenu |
|---|---|
| `pixelgoogle` | Associations : `id_pixelgoogle`, ancien `id_google`, `id_category`, `id_lang` et `value`. |
| `mmc` | Flux : `id_mmc`, `name`, `id_shop`, `conf` sérialisée et `active`. Le schéma complète les anciennes installations. |
| `mmc_log` | Historique : ID, date, durée, nombre, état, mode fichier, nom, format et source. Les entrées de plus de 90 jours sont supprimées lors d'une nouvelle journalisation. |

La désinstallation conserve les trois tables, leurs flux, associations et historiques.

### 6.7 Clés de configuration et valeurs initiales

| Clé | Valeur ou comportement |
|---|---|
| `mmc_pf_tree` | Absente, vaut `0` ; contrôle les chemins parents. |
| `mypresta_updates` | Préférence partagée ; absente, vérification périodique désactivée. |
| `update_mmcfeed` | Horodatage de la dernière vérification. |
| `updatev_mmcfeed` | Dernière version renvoyée. |

Avec **Remember settings**, les valeurs utilisent le préfixe `mmc_` :

| Clés | Valeurs de repli |
|---|---|
| `mmc_export_igid`, `mmc_export_active`, `mmc_export_instock`, `mmc_export_product_type`, `mmc_export_product_type_id`, `mmc_export_product_weight`, `mmc_export_shipping_info`, `mmc_export_unit_price`, `mmc_export_save_file`, `mmc_export_nophoto_exclude`, `mmc_export_adult`, `mmc_export_color`, `mmc_export_gender`, `mmc_export_age_group`, `mmc_export_size`, `mmc_export_storecode`, `mmc_export_mainpicture`, `mmc_export_inventory`, `mmc_export_ie` | `0` ou false. |
| `mmc_export_additional_sc`, `mmc_export_exworthless` | False. |
| `mmc_remember_settings`, `mmc_export_specific`, `mmc_export_enclosure`, `mmc_export_removehtml` | `1` ou true. |
| `mmc_export_file_format` | `csv`. |
| `mmc_export_type` | Ancien `product`, normalisé en `products`. |
| `mmc_export_identification` | `id_product`. |
| `mmc_export_gtin` | `upc`. |
| `mmc_export_product_name` | `name`. |
| `mmc_export_product_name_format`, `mmc_export_instock_info`, `mmc_export_what_pictures` | `0`. |
| `mmc_export_short_description_what` | `short`. |
| `mmc_export_delimiter` | `|`. |
| `mmc_export_tax` | `price_tin`. |
| `mmc_export_manufacturers_default` | `Default`. |
| `mmc_export_language`, `mmc_export_currency`, `mmc_export_country_prices`, `mmc_export_group_prices` | Valeurs par défaut de la boutique. |
| `mmc_export_category`, `mmc_export_manufacturers`, `mmc_export_suppliers` | Ancien `all` ; option visible **All**. |
| `mmc_export_shipping_info_price`, `mmc_limit_limit`, `mmc_limit_page` | `0`. |
| `mmc_export_shipping_id_zone` | `1`. |
| `mmc_export_filename`, `mmc_export_remove_char_product_name`, `mmc_export_exclude`, `mmc_export_exclude_categories`, `mmc_export_color_type`, `mmc_export_color_default`, `mmc_export_gender_default`, `mmc_export_size_default`, `mmc_export_availability_date`, `mmc_export_exreference`, `mmc_export_exreference_value`, `mmc_export_sc`, `mmc_export_exworthless_value` | Chaîne vide. |
| `mmc_export_color_attribute`, `mmc_export_color_feature`, `mmc_export_gender_type`, `mmc_export_gender_feature`, `mmc_export_gender_attribute`, `mmc_export_age_group_type`, `mmc_export_age_group_feature`, `mmc_export_age_group_attribute`, `mmc_export_age_group_default` | `0`. |
| `mmc_export_size_attribute` | ID séparés par virgules ; vide. |
| `mmc_mmcfeed_products` | ID exclus séparés par virgules ; vide. |

Le formulaire lit aussi `delete_images` sous `mmc_delete_images`, sans champ visible. La désinstallation ne supprime aucune de ces clés.

### 6.8 Fichiers, taxonomie, sécurité et extensions

Les fichiers sont écrits sous `modules/mmcfeed/{sanitized-name}.{csv|xml|txt}`. Les noms sont limités aux lettres, chiffres, tirets et traits de soulignement, avec contrôle du chemin. Les taxonomies sont dans `modules/mmcfeed/google/{language-code}.txt`. Rien n'est supprimé à la désinstallation.

Le jeton est `hash_hmac('sha256', 'mmcfeed.write.' . $idShop, _COOKIE_KEY_)`. Un employé peut écrire directement ; un appel externe doit présenter le jeton, comparé avec `hash_equals`. Le contrôleur retire les paramètres non fiables `export_*`, `mmcfeed_*`, `mmc_*`, `pf_*`, de limite, débogage et exclusion avant d'appliquer la configuration.

CSV emploie `fputcsv`, un séparateur normalisé et les guillemets doubles. Le texte décode les entités, normalise les espaces et retire retours, tabulations et HTML. XML utilise `SimpleXMLElement`. Les mises à jour utilisent cURL ou l'accès aux URL.

Les traductions utilisent `translations/{iso}.php`. La plupart des chaînes passent par la traduction du module ; certaines étiquettes comme **All**, **Price Tax Included** et **Price Tax Excluded** restent littéralement en anglais. Les descriptions des champs sont dans les tableaux HelperForm du contrôleur et celles des mises à jour dans `lib/updateChecker.php`.

Aucun modèle de vitrine ne peut être surchargé par un thème. Les modèles Smarty du back-office exigent de modifier ou étendre le module. Préférez un fork maintenu ou une intégration séparée ; aucun hook d'extension formel n'est exposé.

## 7. Aide

Page du produit : [Microsoft Merchant Center Product Feed](https://mypresta.eu/modules/advertising-and-marketing/microsoft-merchant-center-feed.html)

Pour obtenir de l'aide, connectez-vous à votre compte mypresta.eu, ouvrez la page de contact et sélectionnez **Support for paid modules**. Après connexion, choisissez le module dans l'historique des achats et décrivez le flux, la boutique et le message exact.
