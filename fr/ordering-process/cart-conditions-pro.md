---
title: "Cart Conditions - documentation et manuel d'utilisation"
sidebar:
  label: "Cart Conditions - documentation et manuel d'utilisation"
description: "Manuel de configuration et de dépannage pour les boutiques qui utilisent déjà Cart Conditions."
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Cart conditions pro sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/cart-conditions-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/cart-conditions-pro/)
>
> ---


## 1. Prérequis

Cart Conditions tourne dans la boutique. Il n'a besoin d'aucun autre module ni d'un compte chez un service externe.

- PrestaShop 1.7, 8 et 9. Ce manuel a été vérifié sur PrestaShop 9.2.0.
- La version de PHP exigée par cette version de PrestaShop. Le module ne demande pas d'extension PHP supplémentaire.
- Aucun autre module n'est requis.
- Les règles lisent le panier en cours. La taille du catalogue ne change pas le contrôle.

## 2. Installation

1. Ouvrez **Modules**, puis **Module Manager**.
2. Envoyez le zip et installez le module. L'installation l'active.
3. Ouvrez **Catalogue**. Cinq entrées apparaissent, dans cet ordre. Les noms restent en anglais dans chaque langue du back-office :

- **Cart Conditions**
- **Cart Value Conditions**
- **Cart Quantity Conditions**
- **Cart Associations Conditions**
- **Cart value by country conditions**

L'installation ne vide pas le cache de la boutique.

La désinstallation retire ces cinq entrées et décroche le module. Elle laisse les règles enregistrées, la liste d'exclusion, le réglage de disponibilité et le réglage des alertes. Une nouvelle installation ramène le menu, et les anciennes règles sont toujours là.

## 3. Configuration et travail quotidien

Le client remplit le panier. Sur la page panier, la boutique liste chaque règle rompue dans une alerte rouge. S'il continue vers le paiement, la boutique le renvoie au panier tant que chaque règle active n'est pas respectée. Un client de **Exclude customers from conditions** saute toutes les règles et peut commander.

Préparez la boutique dans cet ordre :

1. Ouvrez **Configure** et décidez qui et quels produits les règles ignorent.
2. Décidez si des dates de disponibilité futures peuvent être mélangées.
3. Ouvrez chaque liste sous **Catalogue**, cliquez **Add new**, remplissez le formulaire, mettez **Active** sur **On** et cliquez **Save**.
4. Passez une commande test avec un client ordinaire et avec un client exclu.

Un nouveau formulaire s'ouvre avec **Active** sur **Off**. **Save** enregistre la ligne, et le panier l'ignore tant que vous ne mettez pas **On**. La page de configuration répond **Saved**. Les listes affichent la confirmation habituelle du back-office après **Save**.

La note bleue de **Configure** dit : "Management of this module is located under Price Rules menu." Les cinq liens de cette note, et les entrées sous **Catalogue**, ouvrent les listes. Ce module n'ajoute pas d'entrée dans Price Rules.

Les écrans de ce manuel sont le back-office anglais. Les boutons et les champs portent le nom affiché sur ces écrans.

![Liens de la configuration](https://mypresta.eu/docs/images/docs/cartcon-configure-links.webp)

### 3.1 Page de configuration

Ouvrez **Modules**, **Module Manager**, trouvez **Cart Conditions** et cliquez **Configure**.

#### Exclure des clients et des produits

![Formulaire d'exclusion](https://mypresta.eu/docs/images/docs/cartcon-configure-exclude.webp)

Cherchez un client, cliquez le résultat, et cette personne entre dans la liste d'exclusion. Retirez une personne de la même liste avant d'enregistrer. Les clients exclus sautent chaque règle de panier, y compris le contrôle de disponibilité.

| Champ | Valeur de départ | Effet |
|---|---|---|
| **Exclude customers from conditions** | vide | Les clients de cette liste commandent sans règle de panier. **Save** enregistre la liste. |
| **Exclude products from conditions** | **Do not exclude products** | **Exclude selected products** fait ignorer les produits et les catégories choisis. **Do not exclude products** compte chaque produit. |
| **Categories** | aucune cochée | Les catégories cochées sont ignorées quand l'interrupteur du dessus vaut **Exclude selected products**. |
| **Save** | - | Enregistre les clients, l'interrupteur, les produits et les catégories. La page affiche **Saved**. |

La recherche de produits et l'arbre des catégories sont sur le même formulaire. Choisissez un produit comme un client : cherchez, puis cliquez le résultat.

#### Conditions globales

![Comparaison des disponibilités](https://mypresta.eu/docs/images/docs/cartcon-configure-availability.webp)

Le contrôle ne regarde que les produits en rupture dont **Availability date** est encore dans le futur. Les produits en stock, ceux dont la date est vide ou passée, et les produits exclus sont laissés de côté. Une seule date future dans le panier ne bloque pas. Deux valeurs différentes ou plus bloquent.

| Champ | Valeur de départ | Effet |
|---|---|---|
| **Block order of products with Various availabiltiy date** | **Off** | **On** bloque le panier quand ces dates futures ne correspondent pas à la comparaison ci-dessous. **Off** saute ce contrôle. PrestaShop peut déjà autoriser une commande pour un produit disponible plus tard. Cet interrupteur décide si des dates différentes peuvent tenir dans un même panier. |
| **How to compare availability dates** | **Exact date** | **Exact date** bloque quand les dates futures ne sont pas le même jour. **Same calendar month** autorise des jours différents du même mois et de la même année, et bloque quand le mois ou l'année diffère. Le 5 novembre 2026 et le 20 novembre 2026 passent. Le 2 décembre 2026 non. Le 5 novembre 2027 non. |
| **Save** | - | Enregistre l'interrupteur et la comparaison. La page affiche **Saved**. Ce bouton ne crée pas de règle du Catalogue. |

Texte du panier pour **Exact date** : "Availability dates of products in your cart are different. You cant place an order." Pour **Same calendar month** : "Availability months of products in your cart are different. You cant place an order."

#### Mises à jour MyPresta

![Contrôle de mise à jour](https://mypresta.eu/docs/images/docs/cartcon-configure-updates.webp)

| Champ | Valeur de départ | Effet |
|---|---|---|
| **Check updates** / **Check now** | - | Demande à MyPresta si un fichier plus récent existe. **Module is up to date!** signifie que ce fichier est à jour. **New version available!** signifie qu'un fichier plus récent est publié. Le bouton ne l'installe pas. |
| **Updates notifications** | **Disable** | **Enable** affiche un avertissement dans le back-office quand une version plus récente est publiée. **Disable** reste silencieux. **Save** enregistre le choix. |
| **Module page** | lien | Ouvre la page du module, où se trouve la liste des changements. |
| **Save** | - | Enregistre le choix des alertes. |

### 3.2 Cart Conditions

Ouvrez **Catalogue**, puis **Cart Conditions**. Ces règles s'appliquent à chaque client qui n'est pas exclu. Cette liste n'a pas de champ de groupe client.

![Liste Cart Conditions](https://mypresta.eu/docs/images/docs/cartcon-conditions-list.webp)

Colonnes : **ID**, **Cart condition**, **Target type**, **Target item** et **Active**. Une boutique vide affiche **No records found**. Les filtres sont au-dessus des colonnes. Actions de ligne : modifier, supprimer, icône **Active**. Action groupée : supprimer. **Add new** ouvre le formulaire.

![Nouvelle règle Cart Conditions](https://mypresta.eu/docs/images/docs/cartcon-conditions-form.webp)

| Champ | Valeur de départ | Effet |
|---|---|---|
| **Condition** | **Must have** | **Must have** exige la cible. **Can't have** la bloque. |
| **Target type** | **Category** | **Category** utilise un id de catégorie. **Product** utilise un id de produit. **More than defined number of products** utilise un nombre de pièces de tout le panier. |
| **Target item** | vide | Id de catégorie, id de produit ou nombre de pièces. L'aide du champ demande un id ou un nombre de produits. |
| **Active** | **Off** | **On** fait contrôler cette ligne par le panier. **Off** garde la ligne et la saute. |
| **Save** | - | Enregistre la règle. |

Ce que voit le client :

- **Must have** et **Category** : "To place an order you must order product from category: ...".
- **Can't have** et **Category** : "Your cart contains product from forbidden category: .... To continue order please remove it from cart."
- **Must have** et **Product** : "To place an order you must order product: ...".
- **Can't have** et **Product** : "Your cart contains forbidden product: .... To continue order please remove it from cart."
- **Must have** et un nombre de pièces : "Your cart contains less products than required (...). To continue order please increase quantity of products in your cart".
- **Can't have** et un nombre de pièces : "Your cart contains more products than allowed (...). To continue order please decrease quantity of products in your cart".

Le nombre de pièces est la somme des quantités du panier, après retrait des produits exclus. **Must have** exige que le panier atteigne ce nombre. **Can't have** bloque un panier au-dessus de ce nombre.

### 3.3 Cart Value Conditions

Ouvrez **Catalogue**, puis **Cart Value Conditions**. Chaque ligne est un groupe de clients, une catégorie et un montant minimum.

![Liste des montants](https://mypresta.eu/docs/images/docs/cartcon-value-list.webp)

Colonnes : **ID**, **Customer group**, **Cart condition**, **Target**, **Value** et **Active**. Liste vide : **No records found**. Actions de ligne : modifier, supprimer, icône **Active**. Action groupée : supprimer. **Add new** ouvre le formulaire.

![Nouvelle règle de montant](https://mypresta.eu/docs/images/docs/cartcon-value-form.webp)

| Champ | Valeur de départ | Effet |
|---|---|---|
| **Customer Group** | premier groupe de la boutique (Visitor sur une boutique par défaut) | Seuls les acheteurs de ce groupe sont contrôlés. Un client connecté est contrôlé dans chacun de ses groupes. |
| **Condition** | **Must order from selected category** | C'est le seul choix. La règle agit quand le panier contient déjà cette catégorie. |
| **Target item** | vide | Id de catégorie. |
| **Value** | vide | Total minimum TTC des produits de cette catégorie. Saisissez-le dans la devise par défaut de la boutique. Le signe monétaire du formulaire est la devise de la boutique. |
| **Active** | **Off** | **On** applique la ligne. **Off** l'enregistre sans l'utiliser. |
| **Save** | - | Enregistre la règle. |

Si la catégorie est absente du panier, la règle se tait. Si elle est présente et que le total TTC est sous **Value**, le panier affiche : "To place an order you must order for: ... from category: ...".

### 3.4 Cart Quantity Conditions

Ouvrez **Catalogue**, puis **Cart Quantity Conditions**.

![Liste des quantités](https://mypresta.eu/docs/images/docs/cartcon-quantity-list.webp)

Colonnes : **ID**, **Customer group**, **Cart condition**, **Target**, **Quantity** et **Active**. Liste vide : **No records found**. Actions de ligne : modifier, supprimer, icône **Active**. Action groupée : supprimer.

![Nouvelle règle de quantité](https://mypresta.eu/docs/images/docs/cartcon-quantity-form.webp)

| Champ | Valeur de départ | Effet |
|---|---|---|
| **Customer Group** | premier groupe de la boutique | Seul ce groupe est contrôlé. |
| **Condition** | **Must order at least X products from selected category** | Choisissez la limite. La liste complète est plus bas. |
| **Target country** | premier pays de la boutique | Utilisé seulement pour les deux règles "from Y category". Pour toute autre condition, la page cache cette liste. |
| **Target item** | vide | Id de catégorie, de produit, de fabricant, ou valeur d'attribut, selon **Condition**. L'aide demande l'id de la cible. Pour les conditions de panier entier, la page met le mot Cart et verrouille le champ. |
| **Quantity** | vide | Le nombre X de la condition choisie. |
| **Accept only multiplied qty** | **Off** | **On** n'accepte que les multiples de **Quantity**, par exemple 6, 12, 18, 24 quand **Quantity** vaut 6. **Off** accepte tout nombre qui respecte la règle. |
| **Active** | **Off** | **On** applique la ligne. |
| **Save** | - | Enregistre la règle. |

Choix de **Condition**, dans l'ordre du formulaire :

- **Must order at least X products from selected category**
- **Can't more than X products from selected category**
- **Must order at least X products from selected manufacturer**
- **Can't more than X products from selected manufacturer**
- **Must order at least X quantity of selected product**
- **Can't order more than X quantity of selected product**
- **Must order at least X quantity of each product**
- **Can't order more than X quantity of each product**
- **Can't order more than X products with the same attribute value**
- **Cart must have at least X products**
- **Cart can't have more than X products**
- **Cart must have at least X different products**
- **Cart can't have more than X different products**
- **Cart of user from selected country must have more than X products**
- **Cart of user from selected country can't have more than X products**
- **Cart of user from selected country must have more than X products from Y category**
- **Cart of user from selected country can't have more than X products from Y category**

Pour les deux dernières, réglez **Target country** et mettez l'id de catégorie dans **Target item**. Pour les deux règles de pays sans catégorie, la page cache **Target country**, donc vous n'y choisissez pas de pays. Utilisez **Cart value by country conditions** pour une limite en argent. Utilisez les deux dernières règles de quantité pour un nombre de pièces d'une catégorie.

**Search for attribute value** n'apparaît que pour **Can't order more than X products with the same attribute value**. Cherchez, cliquez une valeur, et elle devient **Target item**.

Le texte du panier suit le choix. Les règles de catégorie et de fabricant disent "at least" ou "can't order more than" et nomment la catégorie ou le fabricant. Une règle produit cite la quantité actuelle. Une règle de panier entier dit "you must order more than" ou "you can't order more than" et cite la quantité actuelle. Avec **Accept only multiplied qty** sur **On**, le panier ajoute : "We accept only multiplied quantity...".

Sur la fiche produit, le thème peut afficher "You must order at least: ... quantity of this product" pour **Must order at least X quantity of selected product**, quand ce produit est la cible et que le visiteur correspond au groupe. C'est un avis. Le blocage a lieu dans le panier.

### 3.5 Cart Associations Conditions

Ouvrez **Catalogue**, puis **Cart Associations Conditions**. Une ligne relie un élément à un autre pour un groupe de clients. La règle ne démarre que lorsque le premier élément est déjà dans le panier.

![Liste des associations](https://mypresta.eu/docs/images/docs/cartcon-associations-list.webp)

Colonnes : **ID**, **Customer group**, **Cart condition**, **Target item (1)**, **Associated item (2)** et **Active**. Liste vide : **No records found**. Actions de ligne : modifier, supprimer, icône **Active**. Action groupée : supprimer.

![Nouvelle association](https://mypresta.eu/docs/images/docs/cartcon-associations-form.webp)

| Champ | Valeur de départ | Effet |
|---|---|---|
| **Active** | **Off** | **On** applique la ligne. |
| **Type of condition** | **Associations between product and product** | **Associations between product and category** ou **Associations between category and category** change le sens des deux ids. |
| **For what customer group** | premier groupe de la boutique | Seul ce groupe est contrôlé. |
| **Target item (1)** | vide | Id de produit ou de catégorie. La règle agit quand le client met cet objet dans le panier. |
| **Condition** | **If customer will add to cart Target item (1) then it must order Associated item (2)** | Les choix sont plus bas. |
| **Associated item (2)** | vide | L'id de produit ou de catégorie exigé ou interdit. |
| **Save** | - | Enregistre la paire. |

Choix de **Condition** :

- **If customer will add to cart Target item (1) then it must order Associated item (2)**. Texte : "If your cart has a product: ... you must order also product: ..." ou l'équivalent catégorie.
- **If customer will add to cart Target item (1) then cart must have at least one different product**. Affiché seulement pour produit et produit. Le contrôle du panier n'affiche pas de message pour ce choix. Utilisez un autre choix quand le panier doit bloquer.
- **If customer will add to cart Target item (1) then it will be forbidden to order Associated item (2)**. Texte : "If your cart has a product: ... you can't place an order for: ...".
- **If customer will add to cart Target item (1) then it will be forbidden to add any other product to cart**. La page cache **Associated item (2)**. Texte : "If your cart has a product: ... you can't place an order for any other product."
- **If customer will add to cart Target item (1) then it will be forbidden to add products from categories other than Target item (1)**. Affiché seulement pour catégorie et catégorie. La page cache **Associated item (2)**.

Le formulaire contient aussi **Include subcategories of Target item (1)** et **Include subcategories of Associated item (2)**. La page cache les deux interrupteurs pour chaque type. La règle utilise les ids que vous saisissez.

### 3.6 Cart value by country conditions

Ouvrez **Catalogue**, puis **Cart value by country conditions**. La règle utilise le pays de l'adresse de livraison.

![Liste des montants par pays](https://mypresta.eu/docs/images/docs/cartcon-country-list.webp)

Colonnes : **ID**, **Customer group**, **Condition**, **Country**, **Value** et **Active**. Liste vide : **No records found**. Actions de ligne : modifier, supprimer, icône **Active**. Action groupée : supprimer.

![Nouveau montant par pays](https://mypresta.eu/docs/images/docs/cartcon-country-form.webp)

| Champ | Valeur de départ | Effet |
|---|---|---|
| **Customer Group** | premier groupe de la boutique | Seul ce groupe est contrôlé. |
| **Target country** | premier pays de la boutique | La règle agit quand l'adresse de livraison est ce pays. La liste est celle des pays de la boutique. |
| **Condition** | **Cart must be worth at least ...** | **Cart can't be worth more than ...** est le maximum. |
| **Condition tax** | **Tax included** | **Tax excluded** compare le total hors taxe. Le message du panier répète le libellé de taxe choisi. |
| **Cart value type** | **Products + shipping** | **Products** laisse la livraison hors du total comparé. |
| **Value** | vide | Le montant, dans la devise par défaut de la boutique. |
| **Active** | **Off** | **On** applique la ligne. |
| **Save** | - | Enregistre la règle. |

Sous le minimum, le panier affiche : "To place an order from country: ... your cart must be worth at least ..., while you cart is worth ...". Au-dessus du maximum : "To place an order from country: ... your cart can't be worth more than ..., while you cart is worth ...".

## 4. Boutique

Le client n'ouvre pas de page séparée. Le module parle sur la fiche produit et dans le panier.

Sur la fiche, et seulement pour une règle active **Must order at least X quantity of selected product** visant ce produit, le thème peut afficher : "You must order at least: ... quantity of this product". Le thème doit imprimer la zone d'actions du produit. Ce manuel n'a pas de photo de boutique, parce que cette ligne n'a pas été confirmée sur le thème de test.

Dans le panier, chaque règle rompue est une ligne d'une seule alerte rouge. Les noms des produits et catégories exigés ou interdits sont des liens. Si le client ouvre le paiement alors qu'une règle est rompue, la boutique le renvoie au panier et affiche la même alerte.

Un client de la liste d'exclusion ne voit aucun de ces messages et n'est pas renvoyé.

Il n'y a pas d'adresse de boutique à copier. Il n'y a pas de formulaire pour que le client accepte ou refuse une règle.

## 5. Problèmes

**Les cinq entrées manquent sous Catalogue.** Le module n'est pas installé, ou il a été désinstallé. Réinstallez-le dans **Module Manager**. Les anciennes règles reviennent avec lui.

**La note bleue parle de Price Rules, et Price Rules n'a pas d'entrée Cart Conditions.** Utilisez les cinq liens de la note, ou **Catalogue**. Le parent du menu est Catalogue.

**Une règle enregistrée ne fait rien.** **Active** est sur **Off**, le client est dans la liste d'exclusion, ou il n'est pas dans le groupe choisi. Un visiteur non connecté est contrôlé comme le groupe Visitor. Ouvrez la ligne, mettez **Active** sur **On** et testez avec un client de ce groupe.

**Une règle de montant se tait.** La catégorie n'est pas dans le panier. Ajoutez un produit de cette catégorie. Le total comparé est TTC.

**Deux règles de quantité par pays ignorent le pays.** **Target country** est caché tant que **Condition** n'est pas une des deux lignes "from Y category". Choisissez-en une, ou utilisez **Cart value by country conditions** pour une limite en argent.

**Same calendar month bloque encore novembre et novembre.** Les années diffèrent. Le 5 novembre 2026 et le 5 novembre 2027 sont différents. Le produit doit aussi être en rupture avec une **Availability date** future. Les produits en stock ne sont pas comparés.

**Check now n'affiche rien, ou l'avertissement n'apparaît jamais.** Le serveur de la boutique ne peut pas ouvrir l'adresse distante MyPresta. **Check now** ne fait que signaler une version. Il ne télécharge pas et n'installe pas le fichier. Ouvrez **Module page** et prenez le nouveau fichier là.

**L'alerte du panier manque, et le paiement renvoie quand même au panier.** Le thème n'imprime pas le bloc panier. Le retour au panier fonctionne toujours. Surchargez le modèle de panier dans le thème, ou vérifiez que le thème appelle le hook du panier.

**La désinstallation a retiré le menu, et une installation suivante montre les anciennes règles.** C'est le comportement de la désinstallation. Supprimez les lignes des listes avant de désinstaller si vous voulez un module vide ensuite.

## 6. Pour le développeur

### 6.1 Vue d'ensemble

Classe principale `cartcon`, version 2.1.9, nom de liste **Cart Conditions**, auteur MyPresta.eu, onglet `advertising_marketing`. `cartconPrestashopNewCompatibility` étend `cartcon` pour le format des prix et n'est pas l'instance du module. `psversion()` mappe une version majeure 8 ou plus sur la branche 1.7 pour quelques choix de balisage du back-office. Il n'y a pas de surcharge de `enable()` ni de `disable()`.

`getRestrictions()` lit les lignes actives de la boutique courante, saute les clients de `CARTCON_CUSTOMERS` et remplit `errors_cartcon`. `hookDisplayShoppingCart` imprime cette liste. `hookDisplayPaymentTop` redirige vers le panier avec `cartcon=show` quand la liste n'est pas vide. `hookDisplayProductActions` imprime une quantité minimale seulement pour `cartcon_quantity.c_type = 2` de cet id produit.

### 6.2 Fichiers

- `cartcon.php` - installation, formulaires, contrôles, hooks.
- `lib/prestashop9compatibility.php` - `cartconPrestashopNewCompatibility`.
- `controllers/admin/AdminCartConditionController.php` - must-have et can't-have.
- `controllers/admin/AdminCartValueConditionController.php` - montant minimum de catégorie.
- `controllers/admin/AdminCartQuantityConditionController.php` - règles de quantité.
- `controllers/admin/AdminCartAssociationsConditionController.php` - paires.
- `controllers/admin/AdminCartCountryConditionController.php` - montants par pays.
- `models/CartCondition.php`, `CartValueCondition.php`, `CartQuantityCondition.php`, `CartAssociationsCondition.php`, `CartCountryCondition.php` - modèles.
- `views/templates/front/displayShoppingCart.tpl` - alerte rouge.
- `views/templates/front/productActions.tpl` - minimum sur la fiche.
- `views/templates/admin/script.tpl` - comportement du formulaire de quantité.
- `views/templates/admin/search-attribute-value.tpl` - recherche d'attribut, visible pour le type de quantité 7.
- `lib/searchTool/searchTool.php` - `initTool()` n'injecte que des scripts. Il ne rend pas de panneau.

### 6.3 Contrôleurs

Les cinq contrôleurs admin étendent `ModuleAdminController`. `createMenu()` insère un onglet par langue avec le nom anglais, parent `AdminCatalog` (`Sell > Catalog` sur PrestaShop 9). Classes : `AdminCartCondition`, `AdminCartValueCondition`, `AdminCartQuantityCondition`, `AdminCartAssociationsCondition`, `AdminCartCountryCondition`. Il n'y a pas de contrôleur front. Le seul drapeau front lu par le module est `cartcon=show`, ajouté par la redirection du paiement.

`script.tpl` désactive **Target item** et met la valeur `Cart` pour les types de quantité 4, 5, 8, 9, 15 et 16. La liste des pays est affichée pour les types 8 et 9, puis cachée par le bloc suivant sauf si le type est 10 ou 11. Résultat visible : un champ pays seulement pour les types 10 et 11. Le type 7 affiche `.searchAttributeValue`.

Le script des associations cache `.subcatt` et `.subcata` pour chaque type. L'id de condition 4 n'est actif que pour catégorie-catégorie (type 3). L'id 5 n'est affiché que pour produit-produit (type 1). Les ids 3, 4 et 5 cachent **Associated item (2)**. `getRestrictions()` compare `c_value` d'association 1, 2, 3 et 4. Il ne compare pas `c_value` 5.

### 6.4 Hooks

- `displayHeader` - CSS et JS front, et l'appel ajax `getCartConditions`.
- `displayShoppingCart` - liste d'alertes.
- `displayProductActions` - avis de quantité minimale.
- `displayPaymentTop` - retour au panier dès qu'une erreur existe.
- `actionAdminControllerSetMedia` - ressources admin.

Le module n'enregistre pas de hooks propres.

### 6.5 Surcharges

Aucune. Pas de surcharge de classe ni de contrôleur.

### 6.6 Base

Tables préfixées. `inconsistency()` / `maybeUpdateDatabase()` ajoutent les colonnes manquantes dans `installdb()` et depuis le bouton de mise à jour. Elles ne tournent pas à chaque chargement de la configuration. La désinstallation ne supprime pas les tables.

| Table | Contenu |
|---|---|
| `cartcon` | `id_cartcon`, `c_type`, `c_value`, `c_option`, `active` défaut 1, `id_shop` ajouté ensuite. Pas de groupe client. |
| `cartcon_value` | `id_cartcon_value`, `c_type`, `c_target`, `c_value`, `active`, `c_only_if_in_cart` défaut 0, `c_group`, `id_shop`. `c_only_if_in_cart` n'est pas sur le formulaire. |
| `cartcon_quantity` | `id_cartcon_quantity`, `c_type`, `c_target`, `c_value`, `active`, `c_only_if_in_cart` défaut 0, `c_group`, `id_shop`, `multiply` défaut 0, `c_country` défaut 0. |
| `cartcon_ass` | `id_cartcon_ass`, `c_type`, `c_target1`, `c_target2`, `c_value`, `active`, `c_group`, `id_shop`, `subcatt` défaut 0, `subcata` défaut 0. L'appariement de catégories lit `subcatt` et `subcata` quand ils valent 1. Le formulaire cache les deux interrupteurs. |
| `cartcon_country` | `id_cartcon_country`, `c_type`, `c_target`, `c_value`, `active`, `c_group`, `id_shop`, `c_tax` défaut 1, `c_cartValueType` défaut 1. |

Les écrans HelperForm neufs envoient **Active** à 0 parce que le bouton Off est coché. Le défaut 1 de la colonne ne s'applique que si la colonne est omise.

### 6.7 Clés et traductions

| Clé | Si elle manque |
|---|---|
| `CARTCON_CUSTOMERS` | vide. Ids client séparés par des virgules. Ces clients sortent tout de suite de `getRestrictions()`. |
| `ccon_visibility_rule` | `0` signifie ne pas exclure. `1` ignore les produits et catégories choisis. |
| `ccon_visibility_products` | liste vide d'ids produit. |
| `ccon_visibility_cat` | liste vide d'ids catégorie. |
| `CARTCON_FUTURE` | absent, traité comme éteint. `1` lance la comparaison des dates. |
| `CARTCON_FUTURE_MODE` | absent, converti en `0` (**Exact date**). `1` groupe par `date('Y-m')`. Les produits comparés ont `stock_quantity <= 0` et `available_date` strictement dans le futur. Plus d'une clé distincte bloque la commande. |
| `mypresta_updates` | `0` coupe l'avertissement automatique. `1` l'active. |
| `update_cartcon` | horodatage du dernier contrôle. |
| `updatev_cartcon` | chaîne de version du dernier contrôle. |

Le contrôle utilise `allow_url_fopen` et `file_get_contents` vers `dev.mypresta.eu`. Les traductions boutique sont dans `translations/{iso}.php`. Les libellés de menu sont écrits en anglais pour chaque langue dans `createMenu()` et ne passent pas par un fichier de traduction. Les descriptions de champs sont dans les appels `l()` des contrôleurs et dans les chaînes `desc` HelperForm de `cartcon.php`. `getCustomerGroups()` mappe un panier `id_customer` 0 vers l'id de groupe 1. La branche invité ne tourne que si `id_customer` n'est pas défini.

### 6.8 Extension

Surchargez depuis le thème `views/templates/front/displayShoppingCart.tpl` et `views/templates/front/productActions.tpl`. Si le thème n'appelle jamais `displayShoppingCart` ni `displayProductActions`, il n'y a rien à surcharger et le client ne verra pas l'alerte. La redirection du paiement continue.

## 7. Aide

Page du module : [Cart Conditions Pro](https://mypresta.eu/modules/ordering-process/cart-conditions-pro.html).

Pour écrire au sujet de ce module, connectez-vous au compte client sur mypresta.eu, ouvrez le contact et choisissez **Support for paid modules**. Le formulaire indique que la connexion est exigée pour les modules payants. Après connexion, choisissez ce module dans l'historique d'achats.
