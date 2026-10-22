---
title: "URLs bonitas y limpias - mode d'emploi du vendeur"
description: "Instructions de configuration et de dépannage pour les personnes qui ont déjà ce module."
sidebar:
  label: "URLs bonitas y limpias - mode d'emploi du vendeur"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Pretty / Clean URLs PRO sur MyPresta.eu](https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/seo/pretty-clean-urls-pro/)
>
> ---


Nom technique `purls`, version 3.0.0, nom dans le panneau : URLs bonitas y limpias.

Le fichier `translations/fr.php` enregistre les libellés en espagnol. Un back-office en français affiche ces chaînes. Elles sont citées telles quelles ci-dessous.

## Où sont les écrans

Ouvrez **Modules > Gestionnaire de modules** et configurez **URLs bonitas y limpias**. La page est le formulaire **Configuración**, puis le panneau **Posibles colisiones**, puis le panneau **Actualizaciones de MyPresta**. Le module n'ajoute pas d'entrée de menu, pas d'écran d'import et pas de bloc sur la fiche produit.

La phrase « on documentation page of this module » n'est pas dans les fichiers de traduction. L'écran affiche donc la source anglaise.

## Ce que l'ouverture de la configuration écrit

`install()` n'écrit pas ces valeurs. À l'ouverture, `getContent()` écrit une route quand la valeur courante manque ou est vide :

| Clé | Valeur écrite |
| --- | --- |
| `PURLS_ROUTE_cms_rule` | `info/{rewrite}.html` |
| `PURLS_ROUTE_cms_category_rule` | `info/{rewrite}` |
| `PURLS_ROUTE_supplier_rule` | `supplier/{rewrite}/` |
| `PURLS_ROUTE_manufacturer_rule` | `manufacturer/{rewrite}/` |
| `PS_ROUTE_category_rule` | `{parent_categories:/}{rewrite}/` |
| `PS_ROUTE_product_rule` | `{category:/}{rewrite}.html` |

`PS_ROUTE_product_rule` et `PS_ROUTE_category_rule` sont des clés PrestaShop. Si elles sont vides, ouvrir cette page les remplace par les valeurs du tableau. Avec plusieurs langues, les quatre clés `PURLS_ROUTE_*` sont enregistrées par langue. Avec une langue, en une seule chaîne.

## Configuration

![L'écran est en anglais. Dans ce mode d'emploi : Configuración.](https://mypresta.eu/docs/images/docs/purls-configure-settings.webp)

![Écran en anglais, après enregistrement. ID produit : ID of product + ID of attribute. Hash désactivé. Catégories, marques, fournisseurs et CMS activés. 301 activé. Dans ce mode d'emploi : Configuración.](https://mypresta.eu/docs/images/docs/purls-configure-enabled.webp)

La légende est **Configuración**. La description est **Selecciona de qué tipo de URLs quieres eliminar el ID**. Le bouton est **Guardar** (`submitCategoryFeatured`).

`install()` ne crée pas ces clés. Jusqu'au premier enregistrement, `Configuration::get` renvoie false. Le retrait de l'ID ne tourne que pour les valeurs ci-dessous, donc une clé absente laisse l'ID dans l'adresse. Sur le formulaire, false correspond à l'option `0` (**No eliminar los números de ID** / **Desactivado**).

| Libellé dans fr.php | Clé | Valeurs |
| --- | --- | --- |
| ID de producto | `purls_products` | `0` No eliminar los números de ID. `1` ID de producto + ID de atributo. `2` Solo ID de atributo. `3` Solo ID de producto. |
| Código hash con atributos | `purls_product_hash` | `1` Activado, `0` Desactivado. |
| Categorías | `purls_categories` | `1` Activado retire l'ID des liens de catégorie. `0` Desactivado. |
| Fabricantes | `purls_manufacturers` | `1` Activado retire l'ID des liens fabricant. `0` Desactivado. |
| Proveedores | `purls_suppliers` | `1` Activado retire l'ID des liens fournisseur. `0` Desactivado. |
| CMS | `purls_cms` | `1` Activado retire l'ID des liens CMS. `0` Desactivado. |
| Redirección 301 desde las URLs antiguas | `purls_301` | Radio. `1` Activado, `0` Desactivado. Texte : Activar la redirección automática desde las URLs antiguas (con ID) a las nuevas URLs (sin ID). |

L'aide de **ID de producto** demande de modifier le schéma produit :

- **ID de producto + ID de atributo** : retirer `{id}` et `{id_product_attribute}`.
- **Solo ID de atributo** : retirer `{id_product_attribute}`.
- **Solo ID de producto** : retirer `{id}` et utiliser `{id_product_attribute:-}` pour l'id d'attribut.

La même aide ouvre `https://mypresta.eu/documentation/pretty-clean-urls/configuration-and-module-usage/schema-of-urls-settings.html`. Le texte du lien est la source anglaise « on documentation page of this module ».

**Código hash con atributos** : Activado coupe l'URL produit au caractère `#`. Desactivado, et seulement si ID de producto vaut `1` ou `2`, conserve un hash du type `#/size-s/color-white`. Le texte d'aide dit que l'option agit quand l'id d'attribut produit est retiré de l'URL. Dans le code, `Link::getProductLink()` garde le hash seulement si `purls_product_hash` vaut `0` et `purls_products` vaut `1` ou `2`. Avec la valeur `3`, la même méthode coupe toujours l'URL à `#`. La valeur `0` d'ID de producto appelle la méthode parente de PrestaShop.

| Libellé dans fr.php | Clé | Champ langue | Mots du formulaire |
| --- | --- | --- | --- |
| Regla de producto | `PS_ROUTE_product_rule` | Non | `{rewrite}`, `{category}`, `{categories}`, `{id}`, `{-:id_product_attribute}` |
| Regla de categoría | `PS_ROUTE_category_rule` | Non | `{id}`, `{rewrite}`, `{parent_categories}` |
| Regla de proveedor | `PURLS_ROUTE_supplier_rule` | Oui | `{id}`, `{rewrite}` |
| Regla de marca | `PURLS_ROUTE_manufacturer_rule` | Oui | `{id}`, `{rewrite}` |
| Regla de página de Cms | `PURLS_ROUTE_cms_rule` | Oui | `{categories:/}`, `{id}`, `{rewrite}` |
| Regla de página de categoría de Cms | `PURLS_ROUTE_cms_category_rule` | Oui | `{id}`, `{rewrite}` |

Sur les règles produit et catégorie, le champ indique qu'il se règle aussi dans le schéma d'URL, sous paramètres de la boutique > trafic et SEO.

Sur fournisseur, marque, page CMS et catégorie CMS, avec l'interrupteur à `0`, le texte est **Para editar este campo necesitas activar la opción para eliminar el ID de este tipo de URL**. Le champ reste saisissable. Le dispatcher et `Link` utilisent la route du module seulement si l'interrupteur vaut `1`.

### Schémas des champs de route

Ce sont les modèles de la page des schémas. Dans **Regla de producto**, mettre une ligne du groupe qui correspond à l'ID produit. `{category}` est le rewrite de la catégorie par défaut. `{categories}` sont les rewrite des catégories parentes joints par `/` (`Link::getProductLink()`). `{rewrite}` est `link_rewrite`. `{id}` est l'id du produit. `{id_product_attribute:-}` est l'id de la déclinaison, avec `-` devant quand cet id est présent. Un champ produit vide reçoit `{category:/}{rewrite}.html` même si l'ID produit vaut `2` ou `3`. Pour ces deux options, saisir dans le champ une ligne de leur groupe.

| Champ | ID produit | Schéma |
| --- | --- | --- |
| Regla de producto | `1` | `{rewrite}.html` |
| Regla de producto | `1` | `{category:/}{rewrite}.html` |
| Regla de producto | `1` | `{categories}{rewrite}.html` |
| Regla de producto | `1` | `{categories}{rewrite}` |
| Regla de producto | `2` | `{id}-{rewrite}.html` |
| Regla de producto | `2` | `{category:/}{id}-{rewrite}.html` |
| Regla de producto | `2` | `{categories}{id}-{rewrite}.html` |
| Regla de producto | `2` | `{categories}{id}-{rewrite}` |
| Regla de producto | `3` | `{id_product_attribute:-}{rewrite}.html` |
| Regla de producto | `3` | `{category:/}{id_product_attribute:-}{rewrite}.html` |
| Regla de producto | `3` | `{categories}{id_product_attribute:-}{rewrite}.html` |
| Regla de producto | `3` | `{categories}{id_product_attribute:-}{rewrite}` |

| Champ | Schéma |
| --- | --- |
| Regla de categoría | `{parent_categories:/}{rewrite}/` |
| Regla de categoría | `{rewrite}/` |
| Regla de proveedor | `supplier/{rewrite}/` |
| Regla de proveedor | `any-text/{rewrite}/` |
| Regla de marca | `manufacturer/{rewrite}/` |
| Regla de marca | `any-text/{rewrite}/` |
| Regla de página de Cms | `info/{rewrite}.html` |
| Regla de página de categoría de Cms | `info/{rewrite}` |

Un champ catégorie vide reçoit `{parent_categories:/}{rewrite}/`. L'autre ligne catégorie est l'alternative. `{parent_categories}` sont les rewrite des catégories parentes joints par `/`, sans les id 1, 2 et la catégorie elle-même. Un champ fournisseur vide reçoit `supplier/{rewrite}/`, un champ marque vide `manufacturer/{rewrite}/`. `any-text` n'est pas un mot de route. C'est un préfixe fixe à saisir à la place de ces mots, par exemple `marque/{rewrite}/`. La page des schémas ne donne pas d'alternative pour les deux règles CMS. Les champs CMS vides reçoivent `info/{rewrite}.html` et `info/{rewrite}`.

`parent::loadRoutes()` lit `PS_ROUTE_` plus l'id de route. Si cette valeur n'est pas vide, cette chaîne est la règle compilée : un schéma produit ou catégorie enregistré remplace la règle assignée par `loadRoutes()`. Ce module n'écrit pas `PS_ROUTE_supplier_rule_{id_lang}`, `PS_ROUTE_manufacturer_rule_{id_lang}`, `PS_ROUTE_cms_rule_{id_lang}` ni `PS_ROUTE_cms_category_rule_{id_lang}`. Ces routes de langue restent les valeurs `PURLS_ROUTE_*`. Les routes de base `supplier_rule` et `manufacturer_rule` restent `supplier/{rewrite}/` et `manufacturer/{rewrite}/`.

## Ce que fait Guardar

**Guardar** fait, dans cet ordre :

1. Supprime les noms de configuration `PURLS_ROUTE_cms_category_rule`, `PURLS_ROUTE_cms_rule`, `PURLS_ROUTE_supplier_rule` et `PURLS_ROUTE_manufacturer_rule`. Les valeurs de ces quatre clés, pour toutes les langues, disparaissent avant l'écriture des nouvelles.
2. Réécrit ces quatre clés depuis les champs envoyés. Avec plusieurs langues, les champs s'appellent `PURLS_ROUTE_..._{id_lang}`. Avec une langue, le champ utilise l'id de la langue de contexte. Un champ vide est enregistré comme chaîne vide.
3. Écrit `purls_product_hash`, `PS_ROUTE_category_rule`, `PS_ROUTE_product_rule`, `purls_products`, `purls_categories`, `purls_manufacturers`, `purls_suppliers`, `purls_cms` et `purls_301`.

L'enregistrement remplace le schéma produit et catégorie de PrestaShop. Le formulaire n'écrit pas `PS_ROUTE_supplier_rule`, `PS_ROUTE_manufacturer_rule`, `PS_ROUTE_cms_rule` ni `PS_ROUTE_cms_category_rule`. Le message est **Tu configuración ha sido actualizada.**

## Alertes du formulaire

L'alerte apparaît quand l'interrupteur est éteint (`0` ou absent) et que `strpos` du mot dans la route PrestaShop vaut `== false`. En PHP cette comparaison est aussi vraie quand le mot est en position 0, donc un schéma qui commence par `{id}` affiche quand même l'alerte.

Le contrôle lit les clés PrestaShop, pas les champs `PURLS_ROUTE_*` :

- ID de producto vaut `0` et `PS_ROUTE_product_rule` n'a pas `{id}` : « La URL de reescritura de tu producto no contiene la variable {id}. Es necesaria cuando no quieres eliminar el ID de la URL de las páginas de producto ».
- ID de producto vaut `0` et `{-:id_product_attribute}` manque : « La URL de reescritura de tu producto no contiene la variable {-:id_product_attribute}. Es necesaria cuando no quieres eliminar el ID del atributo del producto de la URL de las páginas de producto ».
- Categorías vaut `0` et `PS_ROUTE_category_rule` n'a pas `{id}` : « La URL de reescritura de tu categoría no contiene la variable {id}. Es necesaria cuando no quieres eliminar el ID de la URL de las páginas de categoría ».
- Fabricantes vaut `0` et `PS_ROUTE_manufacturer_rule` n'a pas `{id}` : « La URL de reescritura de tu fabricante no contiene la variable {id}. Es necesaria cuando no quieres eliminar el ID de la URL de las páginas de fabricante ».
- Proveedores vaut `0` et `PS_ROUTE_supplier_rule` n'a pas `{id}` : « La URL de reescritura de tu proveedor no contiene la variable {id}. Es necesaria cuando no quieres eliminar el ID de la URL de las páginas de proveedor ».
- CMS vaut `0` et `PS_ROUTE_cms_category_rule` n'a pas `{id}` : « La URL de reescritura de tu categoría de CMS no contiene la variable {id}. Es necesaria cuando no quieres eliminar el ID de la URL de las páginas de proveedor ».
- CMS vaut `0` et `PS_ROUTE_cms_rule` n'a pas `{id}` : « La URL de reescritura de tu CMS no contiene la variable {id}. Es necesaria cuando no quieres eliminar el ID de la URL de las páginas de proveedor ».

Les deux dernières phrases parlent de pages fournisseur. C'est le texte de `translations/fr.php`.

## Posibles colisiones

![L'écran est en anglais. Dans ce mode d'emploi : Posibles colisiones.](https://mypresta.eu/docs/images/docs/purls-collisions.webp)

Le panneau **Posibles colisiones** est `views/purls.tpl`, sous le formulaire. Il liste les `link_rewrite` en double, par langue active de la boutique courante.

Le texte **Añade esta URL a tu tabla de trabajos cron para corregir colisiones automáticamente** affiche un lien front vers le contrôleur `cron` du module, avec `key` égal à `Tools::hash('purls')`. Ce paquet ne contient pas `controllers/front/cron.php`. La méthode `cronJob()` appelle la même routine pour les produits et les catégories dans chaque langue active, et aucun fichier de ce paquet n'appelle `cronJob()`.

**URLs de producto**. Colonnes : **ID**, **Nombre**, **Reescritura de enlace**, **Ocurrencia**, **Acción**. Par langue, le menu **Corregir todas las colisiones** contient **Corregir todo de una vez** et **Corregir parcialmente**. **Mostrar productos** recharge la page avec `product_rewrite` et `id_lang`. Liste vide : **No se encontraron colisiones**.

**URLs de categoría** a les mêmes colonnes. Le bouton est **Hacer únicos los campos de reescritura**. **Mostrar categorías** ajoute `category_rewrite`. `getAllCategoryCollisionsRewrite()` reçoit un argument `id_lang` et exécute le SQL avec l'id de langue du contexte, pas avec cet argument.

**Corregir todo de una vez**, **Hacer únicos los campos de reescritura** et **Corregir parcialmente** appellent `makeUnique()`. Pour chaque rewrite en double, la première ligne garde `link_rewrite`. Chaque ligne suivante est enregistrée avec ce rewrite plus `-1`, `-2`, et ainsi de suite, dans la langue du bouton. `save()` s'exécute pour chaque ligne du groupe, y compris la première. Cela modifie `product_lang.link_rewrite` ou `category_lang.link_rewrite`. La désinstallation ne remet pas l'ancien rewrite.

**Corregir parcialmente** envoie une requête AJAX par ligne produit (`AjaxCollisions`, `id_lang`, `id_product`) et masque la ligne après la réponse.

La requête produits groupe `link_rewrite` dans `product_lang` pour la boutique et la langue courantes et garde les groupes dont le nombre est au moins 2. Elle ne filtre pas par catégorie. Les catégories font de même sur `category_lang`.

## Routes, redirections et hash produit

L'appariement de `Dispatcher::getController()` tourne quand PrestaShop utilise les URL simplifiées (`use_routes`), que le contrôleur n'est pas déjà choisi et que la requête n'est pas dans le back-office. L'override copie les routes d'origine et les enregistre à nouveau avec le suffixe `_original`.

Ces écrans de boutique sont après l'enregistrement de Configuration. La langue de la boutique est l'anglais. Les chemins n'ont pas d'id numérique.

![Boutique en anglais. Chemin : men/hummingbird-printed-t-shirt.html#/color-white/size-s. Size S et Color White sont sélectionnés.](https://mypresta.eu/docs/images/docs/purls-front-product.webp)

![Boutique en anglais. Chemin : clothes/men/. Titre : Men.](https://mypresta.eu/docs/images/docs/purls-front-category.webp)

![Boutique en anglais. Chemin : manufacturer/studio-design/. Titre : List of products by brand Studio Design.](https://mypresta.eu/docs/images/docs/purls-front-manufacturer.webp)

![Boutique en anglais. Chemin : info/delivery.html. Titre : Delivery.](https://mypresta.eu/docs/images/docs/purls-front-cms.webp)

Avec l'interrupteur à `1`, `Dispatcher::loadRoutes()` assigne ces `default_routes` puis appelle `parent::loadRoutes()` :

| Interrupteur | Id de route | Règle assignée |
| --- | --- | --- |
| `purls_products` = `1` | `product_rule` | `{category:/}{rewrite}.html` |
| `purls_products` = `2` | `product_rule` | `{category:/}{id}-{rewrite}.html` |
| `purls_products` = `3` | `product_rule` | `{category:/}{id_product_attribute:-}{rewrite}.html` |
| `purls_categories` = `1` | `category_rule` | `{parent_categories:/}{rewrite}/` |
| `purls_suppliers` = `1` | `supplier_rule` et `supplier_rule_{id_lang}` | base `supplier/{rewrite}/`, règle de langue depuis `PURLS_ROUTE_supplier_rule` |
| `purls_manufacturers` = `1` | `manufacturer_rule` et `manufacturer_rule_{id_lang}` | base `manufacturer/{rewrite}/`, règle de langue depuis `PURLS_ROUTE_manufacturer_rule` |
| `purls_cms` = `1` | `cms_rule`, `cms_category_rule` et les mêmes avec `_{id_lang}` | base `info/{rewrite}.html` et `info/{rewrite}` |

Les autres schémas de ces champs sont dans Configuration, sous **Schémas des champs de route**. Un schéma produit ou catégorie enregistré remplace la règle de ce tableau.

`Link` construit l'adresse seulement si l'interrupteur est allumé. Sinon il appelle la méthode parente de PrestaShop.

- Produits (`purls_products` `1`, `2` ou `3`) : `getProductLink()` utilise `product_rule`. Les paramètres qui ne sont pas des mots de cette route sont omis. Les `extraParams` qui ne sont pas des mots de la route restent.
- Catégories (`purls_categories` = `1`) : `getCategoryLink()` utilise `category_rule`. Si la route a le mot `parent_categories`, le chemin est construit à partir des catégories parentes, sans les id 1, 2 et la catégorie elle-même.
- Fournisseurs, fabricants, pages CMS et catégories CMS utilisent `supplier_rule_{id_lang}`, `manufacturer_rule_{id_lang}`, `cms_rule_{id_lang}` et `cms_category_rule_{id_lang}`.

Recherche quand l'id n'est pas dans l'URL :

- Produits en modes `1` et `3` : le dernier segment, sans `.html`, est comparé à `product_lang.link_rewrite`. S'il y a un segment de catégorie, le `link_rewrite` de la catégorie par défaut est aussi comparé. Si rien n'est trouvé, une seconde requête n'utilise que `link_rewrite`. Le résultat va dans `$_GET['id_product']`.
- Catégories : le chemin est comparé à `category_lang.link_rewrite`, avec les segments parents s'il y a plus d'une partie.
- Pages CMS : `cms_lang.link_rewrite`, sans `.html`.
- Catégories CMS : `cms_category_lang.link_rewrite`.
- Fabricants et fournisseurs : `Tools::str2url()` du **nom**, pas de la colonne `link_rewrite`. Le premier segment `supplier` est rejeté par le contrôle fabricant. Si plusieurs noms donnent le même slug, la dernière ligne de la boucle reste.

`purls_301` = `1` envoie `HTTP/1.1 301 Moved Permanently` seulement dans ces cas :

- La route fournisseur contient `id_supplier` et le retrait fournisseurs est actif : redirection vers `getSupplierLink()`.
- La route fabricant contient `id_manufacturer` et le retrait fabricants est actif : redirection vers `getManufacturerLink()`.
- La route CMS contient `id_cms` : redirection vers `getCmsLink()`. Elle contient `id_cms_category` : redirection vers `getCmsCategoryLink()`. Le retrait CMS doit être actif.
- Mode produit `1` : la route contient `id_product` et `isProductLink()` a renvoyé false : redirection vers `getProductLink()`. Les modes `2` et `3` n'appellent pas cette redirection.
- Le retrait catégories est actif, la route contient `id_category` et `isCategoryLink()` a renvoyé false : redirection vers `getCategoryLink()`.

Le mode produit `3`, si l'appariement contient un `id_product_attribute` non vide, appelle `isProductLinkAttribute()`. Cette méthode écrit `$_GET['id_product']` et `$_GET['id_product_attriubte']` (la clé est orthographiée ainsi dans le fichier). Elle n'écrit pas `id_product_attribute`.

Sur la page produit, `displayHeader` ajoute `views/js/purls.js` seulement si le contrôleur est `product`, la requête n'est pas AJAX, un id produit est présent, `purls_product_hash` vaut `0`, `purls_products` vaut `1` ou `2` et le produit a des déclinaisons. Le séparateur est `PS_ATTRIBUTE_ANCHOR_SEPARATOR`, ou `-` si cette valeur manque ou est vide. Le script lit le hash, règle le `select` ou le `radio` `group[groupId]` et émet `prestashop.updateProduct` si un contrôle a changé.

`CartController::displayAjaxProductRefresh()` reconstruit l'URL produit et ajoute `idpa` avec l'id de déclinaison. `ProductController::init()` copie `idpa` dans `id_product_attribute` quand `id_product_attribute` est absent. `getIdProductAttributeByRequest()` lit d'abord `idpa`.

Si `pm_advancedsearch4` est installé, `hookModuleRoutes()` ajoute trois routes avec `/filter-{id}/s-{id_search}/{as4_sq}` aux règles catégorie, fournisseur et fabricant. S'il n'est pas installé, le hook ne renvoie rien.

## Hooks

`install()` n'enregistre que ces hooks :

| Hook | Méthode | Effet |
| --- | --- | --- |
| `displayHeader` | `hookdisplayHeader` | Sur la page produit, aux conditions ci-dessus, ajoute `views/js/purls.js` et la carte `purls_attributes`. |
| `ModuleRoutes` | `hookModuleRoutes` | Renvoie les routes Advanced Search 4 si ce module est installé. |
| `actionAdminControllerSetMedia` | `hookactionAdminControllerSetMedia` | Méthode vide. |

## Classes et fichiers remplacés

PrestaShop copie ces fichiers dans `override/` de la boutique à l'installation :

| Fichier | Classe | Modification |
| --- | --- | --- |
| `override/classes/Dispatcher.php` | `Dispatcher` étend `DispatcherCore` | `loadRoutes()`, `getController()` et `isProductLink`, `isProductLinkAttribute`, `isCategoryLink`, `isCmsLink`, `isCmsCategoryLink`, `isManufacturerLink`, `isSupplierLink`. |
| `override/classes/Link.php` | `Link` étend `LinkCore` | `getProductLink`, `getCategoryLink`, `getSupplierLink`, `getManufacturerLink`, `getCMSLink`, `getCMSCategoryLink`, `getPaginationLink`, `getAnchor`. Omet les paramètres qui ne sont pas des mots de la route compilée. |
| `override/controllers/front/ProductController.php` | `ProductController` | Lit `idpa` dans `init()`, `getIdProductAttributeByRequest()` et `getIdProductAttribute()`. |
| `override/controllers/front/CartController.php` | `CartController` | `displayAjaxProductRefresh()` ajoute `idpa`. |
| `override/controllers/front/CmsController.php` | `CmsController` | Si `purls_cms` vaut `1`, retrouve `id_cms` / `id_cms_category` depuis `link_rewrite`. Lit aussi les anciens chemins `content/{id}-{rewrite}` et `content/category/{id}-{rewrite}`. |
| `override/controllers/front/listing/CategoryController.php` | `CategoryController` | Si `purls_categories` vaut `1`, retrouve `id_category` depuis `category_rewrite` et le chemin. |
| `override/controllers/front/listing/ManufacturerController.php` | `ManufacturerController` | Si `purls_manufacturers` vaut `1`, retrouve `id_manufacturer` avec `Tools::str2url(name)`. |
| `override/controllers/front/listing/SupplierController.php` | `SupplierController` | Si `purls_suppliers` vaut `1`, retrouve `id_supplier` avec `Tools::str2url(name)`. |
| `override/controllers/admin/AdminProductsController.php` | `AdminProductsController` | Seulement `getPreviewUrl()`. Construit le lien produit dans la langue par défaut de la boutique, id de déclinaison `0`, `force_routes` égal à `PS_REWRITING_SETTINGS`. Un produit inactif reçoit `adtoken`, `ad` et `id_employee`. |

Il n'y a pas de panneau sur la fiche produit. Il n'y a pas de fichier CSS. La configuration est `views/purls.tpl` plus l'assistant de formulaire PrestaShop. Le script boutique est `views/js/purls.js`. `purls.tpl` contient aussi la fonction `FixProductsCollisions`.

`Link::psversion()` et `ProductController::psversion()` découpent `_PS_VERSION_`. `getCategoryLink()` utilise une branche de meta title quand la version mineure est 6 ou 7, ou la majeure est 8 ou plus, et une autre branche sinon. Les commentaires de `Dispatcher.php` et `ProductController.php` nomment PrestaShop 9 et, pour une méthode privée, PrestaShop 1.7.

Le module ne crée pas de table SQL. Il lit et écrit `configuration`, et lit `product_lang`, `category_lang`, `cms_lang`, `cms_category_lang`, `manufacturer`, `supplier` et les tables d'attributs pour construire le hash. La réparation des collisions écrit `link_rewrite` via `Product::save()` et `Category::save()`.

Dans le back-office, le constructeur crée `override/controllers/front/listing` en mode `0777` si `override/controllers/front/` existe et que `listing` n'existe pas.

## Actualizaciones de MyPresta

![L'écran est en anglais. Dans ce mode d'emploi : Actualizaciones de MyPresta.](https://mypresta.eu/docs/images/docs/purls-updates.webp)

Le panneau **Actualizaciones de MyPresta** est entre le formulaire et le panneau des collisions.

| Libellé dans fr.php | Contrôle |
| --- | --- |
| Comprobar actualizaciones | Bouton **Comprobar ahora** (`submit_settings_updates_now`). Affiche **¡Nueva versión disponible!** ou **¡El módulo está actualizado!** |
| Notificaciones de actualizaciones | Liste `mypresta_updates` : **-- seleccionar --** (`-`), **Activar** (`1`), **Desactivar** (`0`). |
| Página del módulo | Lien vers la page produit. L'adresse est dans la section support. |
| Guardar | `submit_settings_updates` n'écrit que `mypresta_updates`. |

À chaque requête du back-office, le constructeur appelle `checkforupdates()`. Si `update_purls` manque ou a plus de 259200 secondes, `purlsUpdate::verify()` appelle `http://dev.mypresta.eu/update/get.php` si `allow_url_fopen` et `file_get_contents` sont disponibles. Il enregistre l'heure Unix dans `update_purls` et le corps de la réponse dans `updatev_purls`. La valeur de licence de ce paquet est `nlc` (`$this->mkey`), sauf si un fichier `key.php` à côté du module la remplace. Ce paquet ne contient pas `key.php`.

Si `mypresta_updates` n'est pas `0` et n'est pas false, que la version distante enregistrée est supérieure à 3.0.0 et que la requête n'est pas AJAX, le back-office affiche **Nueva versión disponible, visita http://MyPresta.eu para más información** et **Más detalles en el changelog**. La valeur `0` exécute quand même la requête temporisée et n'ajoute pas cet avertissement. Une clé absente vaut false, et false équivaut à `0`, donc sans avertissement.

## Installation, désactivation, activation, désinstallation

`install()` appelle `parent::install()` et enregistre `displayHeader`, `ModuleRoutes` et `actionAdminControllerSetMedia`. Si l'un d'eux échoue, l'installation renvoie false. Elle n'insère pas de configuration et ne crée pas de table.

Le fichier ne définit ni `enable()` ni `disable()`. Désactiver le module dans le panneau n'exécute aucune méthode de ce fichier. Les classes d'override restent dans `override/` de la boutique, parce que ce module n'a pas de `disable()` qui les retire. Les trois hooks ne s'exécutent pas tant que le module est désactivé.

`uninstall()` ne renvoie que `parent::uninstall()`. Cela retire le module, désenregistre les hooks et supprime les copies d'override installées par PrestaShop. Cela ne supprime pas la configuration. Cela ne restaure pas `PS_ROUTE_product_rule` ni `PS_ROUTE_category_rule`. Cela ne restaure pas les `link_rewrite` modifiés par les boutons de collisions. Restent : `purls_products`, `purls_product_hash`, `purls_categories`, `purls_manufacturers`, `purls_suppliers`, `purls_cms`, `purls_301`, les quatre clés `PURLS_ROUTE_*`, `mypresta_updates`, `update_purls`, `updatev_purls` et les deux clés `PS_ROUTE_*` écrites par le formulaire.

## Quand une page ne se résout pas

- L'ID est encore dans l'URL : ID de producto vaut `0` ou la clé n'a pas été enregistrée, ou le schéma produit/catégorie contient encore `{id}`. L'appariement propre de `getController()` ne tourne que si les URL simplifiées (`use_routes`) sont actives.
- Une URL nettoyée tombe sur le contrôleur introuvable : deux produits ou catégories partagent `link_rewrite`. Le panneau des collisions liste ces lignes. Les boutons de correction changent `link_rewrite` en base.
- Une ancienne URL avec id ne redirige pas : `purls_301` n'est pas `1`, ou le type de page est le mode produit `2` ou `3` (ces branches n'appellent pas `Tools::redirect`).
- L'URL fabricant ou fournisseur ouvre le mauvais enregistrement, ou aucun : l'appariement utilise `Tools::str2url()` du nom.
- Le module est désactivé et les URL passent encore par ce code : les overrides restent dans `override/` jusqu'à la désinstallation.
- Après désinstallation, les schémas produit et catégorie sont les dernières valeurs enregistrées par ce formulaire.

## Support

Page produit : [https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html](https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html). Le champ **Página del módulo** du panneau de mises à jour ouvre cette adresse. L'aide de la configuration ouvre aussi `https://mypresta.eu/documentation/pretty-clean-urls/configuration-and-module-usage/schema-of-urls-settings.html`.
