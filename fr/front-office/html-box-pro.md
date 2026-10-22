---
title: "HTML Box Pro - mode d'emploi du vendeur"
sidebar:
  label: "HTML Box Pro - mode d'emploi du vendeur"
description: "Configuration des boîtes HTML, des positions de hook et des règles de visibilité pour une boutique qui a déjà le module."
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module HTML Box Pro sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/html-box-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/html-box-pro/)
>
> ---


Le nom technique du module est `htmlboxpro`, version 4.0.5. Dans cette langue la liste des modules affiche **HTML Box Pro**.

## Où sont les écrans

Modules, puis Gestionnaire de modules, puis le module **HTML Box Pro**, puis Configurer. La page est la configuration du module (`configure=htmlboxpro`).

La barre sous le titre a deux boutons : **Paramètres** et **Boîtes**. **Paramètres** écrit `hbp_lasttab` = 1. **Boîtes** écrit `hbp_lasttab` = 2. Si la clé manque, l'ouverture de la page écrit 1, le premier écran est donc **Paramètres**.

Dans la même barre, **Support** ouvre `https://mypresta.eu/contact.html` dans un nouvel onglet. **Mises à jour** ouvre la page du module chez MyPresta dans un nouvel onglet. Le contrôle de version est le panneau en bas de **Paramètres**, pas ce bouton.

Il n'y a pas d'import et pas de bloc sur la fiche produit. Une boîte apparaît en boutique seulement quand son hook est activé, que le bloc est actif et qu'il passe les filtres plus bas.

Si `firsttime_hbp` n'est pas 1, la page affiche une alerte avec `https://www.youtube.com/watch?v=uxzhSr5TrF4`. La fermeture envoie `firsttime_hbp` = 1 et l'alerte ne revient pas.

## Ce que l'installation écrit

L'installation lance l'installation parente, crée les tables, écrit `hbp_notinyjs` = 1 et enregistre `actionAdminControllerSetMedia` plus chaque hook de la liste plus bas.

Elle n'active pas ces hooks. Un hook affiche des boîtes seulement quand la clé `hbp_` plus le nom du hook vaut 1. Tant que la case de **Boîtes** n'est pas enregistrée, la clé est absente et le hook ne renvoie rien.

Ouvrir la configuration vérifie toujours les colonnes et ajoute celles qui manquent dans `hbp_block`. Les lignes déjà là restent.

## Paramètres

![Écran en anglais. Settings est Paramètres. Global module settings est Paramètres globaux du module. Updates notifications est Notifications de mises à jour.](https://mypresta.eu/docs/images/docs/htmlboxpro-settings.webp)

Le titre est **Paramètres globaux du module**. Le bouton est **Enregistrer**. Chaque interrupteur est **Activé** (1) ou **Désactivé** (0).

| Libellé | Clé | Après l'installation |
| --- | --- | --- |
| Utiliser l'éditeur de texte riche interne du module | `hbp_tiny` | clé absente ; le formulaire affiche **Désactivé** |
| Empêcher la suppression des URL des images | `hbp_forceurls` | clé absente ; le formulaire affiche **Désactivé** |
| Ne pas charger (dupliquer) les boîtes avec les requêtes ajax de la page produit | `hbp_noajax` | clé absente ; le formulaire affiche **Désactivé** |
| Ne pas charger les bibliothèques tinyMCE | `hbp_notinyjs` | 1, donc **Activé** |

**Enregistrer** envoie les noms des quatre interrupteurs. Le module écrit chaque valeur envoyée. `hbp_tiny` = 1 charge sur cette page `views/js/tinymce16.inc.js`. Le même interrupteur avec `hbp_forceurls` = 1 charge à la place `views/js/tinymce16-force-urls.inc.js`. `hbp_tiny` = 0 charge le fichier boutique `js/admin/tinymce.inc.js` et appelle `tinySetup()`. `hbp_notinyjs` = 1 saute `js/tiny_mce/tinymce.min.js`. La page inclut quand même `js/tiny_mce/tiny_mce.js`, `views/js/script.js` et `views/css/styles.css`.

`hbp_noajax` = 1 fait renvoyer vide à `generateHookContents` quand la requête a `ajax` = 1 et `action` = refresh. Les autres requêtes affichent toujours les boîtes.

Sous les interrupteurs, la page ajoute le panneau de mise à jour de `checkforupdates`. La liste **Notifications de mises à jour** a `-- select --`, **Activer** (1) et **Désactiver** (0). **Vérifier maintenant** est le bouton `submit_settings_updates_now`. **Enregistrer** de ce panneau est `submit_settings_updates` et n'écrit que `mypresta_updates`.

Le constructeur interroge le serveur distant quand `mypresta_updates` n'est pas 0, ou quand la clé manque (`Configuration::get` vaut false), et que `update_htmlboxpro` a plus de 259200 secondes. La requête part si `allow_url_fopen` est actif. La valeur de licence de ce paquet est `nlc`. Un avertissement s'affiche quand la version renvoyée est supérieure à 4.0.5 et que la requête n'est pas ajax. **Désactiver** (0) entre quand même dans la branche avec délai ; la condition de l'avertissement est celle de cette branche.

## Boîtes

![Écran en anglais. Boxes est Boîtes. Default positions est Positions par défaut. Search hooks n'est pas dans translations/fr.php, l'écran affiche cette source anglaise.](https://mypresta.eu/docs/images/docs/htmlboxpro-boxes.webp)

**Boîtes** a deux colonnes. À gauche, **Positions par défaut**. Au-dessus des lignes, un champ de recherche. L'espace réservé **Search hooks** n'est pas dans `translations/fr.php`, l'écran affiche cette source anglaise. **Positions personnalisées** est le panneau sous cette liste, dans la même colonne de gauche. La colonne de droite montre les blocs du hook choisi ou l'état vide. La colonne principale commence par le titre **No box selected** et la phrase **Veuillez sélectionner des blocs dans la liste disponible à gauche. Ou créez un nouveau bloc.** **No box selected** et **No boxes in this position yet** (hook déplié sans bloc) ne sont pas dans `translations/fr.php`, l'écran affiche cette source anglaise.

Chaque hook par défaut est une ligne : case, nom du hook et le bouton de nouvelle boîte. Le nom mène à `https://mypresta.eu/prestashop/hook/` plus le nom en minuscules. La case envoie `togglehook`. Cochée, elle écrit `hbp_{hook}` = 1 et rappelle `registerHook`. Décochée, elle n'envoie pas `status`, la clé devient 0. Couper le hook ne le désenregistre pas. Le texte de succès est **Visibilité du hook modifiée correctement**.

La ligne du bloc montre le nom interne, ou **pas de nom de bloc interne** si le nom est vide. Les boutons sont **Modifier ce bloc**, **Dupliquer ce bloc** et **Supprimer ce bloc**. Le succès de l'interrupteur d'activité est **Visibilité du bloc modifiée correctement**. Glisser une ligne envoie `action=updateSlidesPosition` et `elements{hook}[]` et écrit `hbp_block.position`. L'onglet charge jQuery UI sortable. Un hook vide affiche **aucun bloc défini**. En multiboutique la ligne peut afficher **pour cette boutique**.

**Dupliquer ce bloc** copie le bloc et préfixe le nom avec `[dupliquer] `. Le texte de succès est **Bloc dupliqué correctement**. **Supprimer ce bloc** supprime la ligne par le modèle objet. Le texte de succès est **Bloc supprimé correctement**. L'interrupteur de la liste lance `smart_clean` sur le corps de chaque langue, enregistre le bloc et pose `active` en SQL.

## Ajouter et modifier un bloc

![Écran en anglais. Create new block est Créer un nouveau bloc. Contents est Contenus. Smarty templates manager est Gestionnaire de modèles Smarty. Placement n'a pas de traduction.](https://mypresta.eu/docs/images/docs/htmlboxpro-block-form.webp)

Ajouter une boîte ouvre **Créer un nouveau bloc**. Modifier ouvre **Modifier le bloc existant**. Le bouton est **Enregistrer**. L'ajout envoie `submitAddNewHbox`. La modification envoie `submitEditHbox`. Le texte d'ajout est **Bloc ajouté correctement**. Le texte d'enregistrement est **Bloc enregistré correctement**.

Le corps de chaque langue de la boutique va dans `hbp_block_lang.body`. Avant l'enregistrement le module exécute `addslashes(smart_clean(...))`. `smart_clean` ramène un caractère d'espace répété à un seul et coupe les extrémités. Le dernier remplacement de `prepare()` réécrit `\'`, `\\` et `\"`. Les lignes précédentes de `prepare()` partent de la chaîne d'origine et ne changent pas la valeur renvoyée. La fonction ne retire pas les balises HTML. Le même nettoyage repart quand l'interrupteur de la liste change l'activité.

Les libellés des champs sont dans `translations/fr.php`. Le titre produits est **Produits**. **Placement**, **Pages**, **Cart**, **Customers** et **Schedule** n'y ont pas d'entrée, l'écran affiche cette source anglaise.

| Section | Ce que font les champs |
| --- | --- |
| Contenu | **Contenus** (`hbp_body`, une valeur par langue) et **Nom** (`hbp_name`, 150 caractères). L'interrupteur d'éditeur dans `views/js/script.js` appelle `tinyMCE.execCommand('mceToggleEditor')` pour le champ de cette langue. Sous l'éditeur se trouve **Gestionnaire de modèles Smarty**. Le bouton ouvre le gestionnaire de `lib/smartyTemplatesManager/`. |
| Placement | Boutique, position (`hbp_hook`), **Active** (`hbp_active`, 0 dans la table jusqu'à ce que l'enregistrement mette 1), pages SSL seulement (`hbp_bssl`), **Active on mobile devices**, **Active on tablet devices**, **Active on PC devices**. Une valeur d'appareil absente est enregistrée à 1. Les libellés français sont dans `translations/fr.php`. |
| Pages | Accueil, promotions, confirmation de commande, catégorie, catégorie et sous-catégories, catégories exclues, catégorie CMS, page CMS, page fabricant, URL exacte et mots de recherche. Les id sont séparés par des virgules. Le champ de recherche à côté d'un id est l'outil de recherche du module (`ajax=1` et `searchType`). |
| Products | Inclure ou exclure des id produit, toutes les fiches, prix spécifique, rupture, disponible à l'achat, non disponible, en stock, valeur min et max, catégorie du produit, fabricant, fournisseur et valeur de caractéristique. |
| Cart | La boîte seulement si le panier contient, ou ne contient pas, les id de catégorie ou de produit indiqués. |
| Customers | **All users** (0), **Logged only** (1), **Unlogged only** (2) dans `hbp_logged`. Les textes français de ces trois options sont dans `translations/fr.php`. **Show for all groups** et les cases de groupe vont dans `hbp_cgroup` en liste séparée par des virgules. **Hide for (users' groups)** est `hbp_hcgroup`. La géolocalisation et le pays de l'adresse de livraison sont dans cette section. |
| Schedule | Devise, date du / au, jours de la semaine et heure du / au. |

Les jours appellent la traduction avec le domaine `forms` (`Sunday` à `Saturday`). Les fichiers `translations/*.php` rangent ces mots dans le domaine `htmlboxpro`, pas `forms`. L'écran affiche la source anglaise : Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday.

Le texte de géolocalisation pointe vers `https://mypresta.eu/prestashop-17/geolite2-city-geolocation-download.html` et le dossier `/app/Resources/geoip/`. Le même texte dit que la géolocalisation ne fonctionne pas sur localhost. Les pays choisis vont dans `selected_geoip`, séparés par des points-virgules. Les pays de livraison vont dans `delivery_address_selected`, séparés par des points-virgules. C'est un interrupteur distinct de la géolocalisation.

## Quand la boutique masque un bloc

`generateHookContents` charge les blocs avec `active` = 1 pour la langue et le hook en cours, triés par `position`. Si le multiboutique est actif, `shop` doit être l'id de la boutique en cours ou 0. Le modèle `html.tpl` masque le corps dès qu'une règle ci-dessous ne passe pas. Un interrupteur laissé sur **Désactivé** n'applique pas cette règle.

| Interrupteur actif | Le corps est masqué quand |
| --- | --- |
| Accueil seulement | le contrôleur n'est pas `index` |
| Plage de dates | aujourd'hui est avant la date de début ou après la date de fin (`Y-m-d`) |
| Mots de recherche | la recherche n'est pas un des mots séparés par des virgules |
| Pages SSL seulement | `$_SERVER['HTTPS']` n'est pas `on` |
| Connectés seulement | le client n'est pas connecté |
| Non connectés seulement | le client est connecté |
| Fiches produit choisies | l'id produit n'est pas dans la liste. Un premier élément vide garde le bloc si un id produit est présent |
| Rupture | le stock utilisé par le modèle est supérieur à 0 |
| En stock | ce stock n'est pas supérieur à 0 |
| Non disponible / disponible à l'achat | la valeur `oos` ne correspond pas à la règle deny ou allow de `html.tpl` |
| Prix spécifique / pas de prix spécifique | `hook_params.product` n'a pas de prix spécifique correspondant |
| Catégories choisies | le contrôleur n'est pas celui de catégorie ou l'id n'est pas choisi |
| Catégories et sous-catégories | la catégorie n'est pas choisie et n'est pas un enfant selon `htmlboxpro::checkIfChildren` |
| Catégorie CMS, page CMS, page fabricant | l'id en cours n'est pas dans la liste ou le contrôleur est une autre page |
| URL choisie | `htmlboxpro::currentPageURL()` n'est pas dans la liste enregistrée. La comparaison retire `rand=` |
| Produit dans une catégorie | les catégories du produit ne croisent pas la liste |
| Caractéristique | le produit n'a pas la valeur de caractéristique choisie |
| Confirmation de commande | le contrôleur n'est pas `orderconfirmation` |
| Fabricant ou fournisseur du produit | le fabricant ou le fournisseur n'est pas choisi |
| Panier, catégorie ou produit, contient ou ne contient pas | le panier ne correspond pas à la liste. Le PHP de `get_blocks` retire le bloc avant le modèle pour ces quatre filtres |
| Masquer pour le groupe | le groupe du client correspond à `hbp_hcgroup`. Les groupes 1 et 2 sont comparés au groupe par défaut. Un autre groupe masque le bloc s'il est parmi les groupes du client |
| Appareil | `Context::getDevice()` vaut 1 et PC est coupé ; 2 et la tablette est coupée ; 4 et le mobile est coupé |
| Valeur min / max | le prix converti est hors du montant ou le hook n'a pas de produit |
| Jours | `hbp_daytype_on` vaut 1 et le `%w` du jour n'est pas dans la liste |
| Devise | `hbp_currency_on` vaut 1 et l'id de devise n'est pas `hbp_currency` |
| Adresse de livraison | le pays de livraison n'est pas dans `delivery_address_selected` |
| Géolocalisation | `hbp_geoip` vaut 1 et le pays résolu n'est pas dans `selected_geoip` |
| Produits exclus, toutes les fiches, catégories exclues | le produit ou la catégorie en cours est exclu |

Le filtre d'heure tourne en PHP, avant le modèle. Si `hbp_tim` vaut 1, `timfrom` et `timto` sont comparés à `date("H:i:s")` après retrait des deux-points. `timto` passe par `ltrim` avec le masque de caractères `0`, les zéros de gauche de cette borne sautent. Un bloc hors de la fenêtre sort de la liste.

## Jetons dans le corps de la boîte

Le remplacement tourne quand la requête a un `controller` et que ce n'est pas `AdminModules`. Un jeton non rempli devient une chaîne vide à la fin. L'exception est `{current_url}`.

| Jeton | Rempli quand |
| --- | --- |
| `{currency_iso}` | une devise est chargée ; la valeur est le code ISO |
| `{id_lang}` | toujours dans cette branche ; la valeur est le code ISO de la langue, pas l'id numérique |
| `{id_customer}`, `{email_customer}`, `{customer_firstname}`, `{customer_lastname}` | le client est connecté |
| `{id_product}`, `{id_product_attribute}`, `{product_name}`, `{product_ean13}`, `{product_isbn}`, `{manufacturer_name}` | le contrôleur est `product` ou le hook reçoit `product` |
| `{product_price_tax_incl}`, `{product_price_tax_excl}` | fiche produit ; montant via l'aide au prix du module |
| `{product_price_tax_incl_no_currency}`, `{product_price_tax_excl_no_currency}` | les mêmes montants sans le signe de devise |
| `{id_category}`, `{name_category}`, `{path_array_category}` | un id de catégorie est dans la requête |
| `{cart_products_id}`, `{cart_total}`, `{cart_total_with_currency}` | un panier existe |
| `{order_id}`, `{order_customer_email}`, `{order_currency_iso_code}`, `{order_total_paid}`, `{order_total_paid_tax_excl}`, `{order_total_paid_tax_incl}`, `{order_total_products_tax_included}`, `{order_total_products_tax_excluded}`, `{order_products_id}`, `{order_products_id_google}`, `{order_delivery_date}`, `{order_delivery_country}` | la branche de confirmation de commande a un id de commande |
| `{current_url}` | chaque requête, après la branche ci-dessus. Schéma, hôte et URI |
| `{HOOK:HookName}` | `Hook::exec` de ce nom, sauf si le nom est le hook qui affiche cette boîte ; le jeton est alors vide |
| `{HOOK:HookName:moduleName}` | `Hook::exec` limité à l'id de ce module |
| `{smartyTemplate:name}` | le modèle chargé par `loadSmartyTemplateFromManager` |

`{shop_name}` reçoit le nom de la boutique, puis la passe de nettoyage remplace `{shop_name}` par une chaîne vide. Le jeton ne reste pas comme nom de boutique. `{id_product_attribute}` est vide quand l'id d'attribut vaut 0.

## Positions personnalisées

![Écran en anglais. Custom positions est Positions personnalisées. Add support of new hook est Ajouter le support d'un nouveau hook. Hook name est Nom du hook. Add new hook est Ajouter un nouveau hook. regenerate now! est régénérer maintenant !](https://mypresta.eu/docs/images/docs/htmlboxpro-custom-hooks.webp)

**Positions personnalisées** liste les lignes de `hbp_customhook`. Le titre au-dessus du champ est **Ajouter le support d'un nouveau hook**. **Ajouter un nouveau hook** lit **Nom du hook**. Le nom enregistré ne garde que les lettres et les chiffres (`preg_replace("/[^\da-z]/i", '')`). Si la boutique n'a pas de hook de ce nom, le module crée une ligne `Hook` avec `live_edit` 1, `position` 1, le titre égal au nom et la description `Custom hook created with usage of HTML BOX PRO module`. Il insère `hbp_customhook` si la ligne manque, réécrit `htmlboxpro.php` et enregistre le hook.

Si le hook existe déjà et que la méthode `hook{Name}` est déjà dans `htmlboxpro.php`, la page affiche **Le hook existe déjà dans la base de données de la boutique** et n'ajoute pas une autre ligne. Si le hook existe et que la méthode manque, le module réécrit quand même le fichier et enregistre le hook.

**régénérer maintenant !** envoie `hbp_rh_submit`. L'avertissement du bouton est **utilisez cette option pour reconstruire le fichier du module si les hooks personnalisés ne fonctionnent pas**. Le titre à côté est **Régénérer les hooks**. La réécriture remplace la partie de `htmlboxpro.php` entre `//~~explode~~//` par une méthode par hook : `hook{Name}` renvoie `generateHookContents("{Name}", $params)`. Le fichier doit être accessible en écriture. Texte d'échec : **Le fichier principal du module n'est pas accessible en écriture. Veuillez vérifier les permissions (CHMOD) du fichier /modules/htmlboxpro/htmlboxpro.php**. Texte de succès : **Fichier principal du module reconstruit correctement. Le module devrait maintenant prendre en charge les hooks personnalisés.**

**Remove hook** demande **Remove this custom hook?** Ces deux chaînes ne sont pas dans `translations/fr.php`, l'écran affiche cette source anglaise. L'action supprime la ligne `hbp_customhook` et, si l'id du hook existe dans la boutique, supprime ce `Hook`, puis réécrit le fichier.

Le lien **Comment utiliser les hooks personnalisés ?** ouvre `https://mypresta.eu/en/art/news/html-content-box-custom-hooks.html`. Dans le formulaire, un bloc sur un hook propre affiche **Ce bloc utilise un hook personnalisé** et deux extraits :

`{hook::exec('HookName') nofilter}`

`{hook h='HookName' product=$product}`

Le second extrait est celui décrit pour une liste de produits.

## Hooks enregistrés à l'installation

`actionAdminControllerSetMedia` ajoute le plugin jQuery autocomplete seulement quand `configure` vaut `htmlboxpro`. Il n'affiche pas de boîte.

Ces hooks appellent `generateHookContents` avec le nom du hook. L'affichage dépend encore de `hbp_{hook}` = 1 et d'un bloc actif :

`displayHeader`, `displayBanner`, `displayNav1`, `displayNav2`, `displayNavFullWidth`, `displayTop`, `displayHome`, `displayFooterBefore`, `displayFooter`, `displayFooterAfter`, `displayMyAccountBlock`, `displayBeforeBodyClosingTag`, `displayLeftColumn`, `displayLeftColumnProduct`, `displayRightColumn`, `displayRightColumnProduct`, `displayOrderConfirmation`, `displayCustomerAccount`, `displayCustomerAccountForm`, `displayProductAdditionalInfo`, `displayReassurance`, `displayFooterProduct`, `displayAfterProductThumbs`, `displayProductListReviews`, `actionProductOutOfStock`, `displayShoppingCart`, `displayCartExtraProductActions`, `displayShoppingCartFooter`, `displayExpressCheckout`, `displayCustomerLoginFormAfter`, `displayBeforeCarrier`, `displayAfterCarrier`, `displayPaymentTop`, `displayPaymentByBinaries`.

`displayHeader` n'attache pas de fichier CSS ou JS en boutique. Il affiche les boîtes de ce hook. La boutique n'a pas de feuille de style propre au module. Le HTML, le CSS et le JavaScript sont le corps enregistré par le vendeur.

`registerHook` utilise la méthode parente quand `hook{Name}` existe déjà. Sinon il insère la ligne `Hook` si besoin et insère `hook_module`.

## Tables et fichiers

L'installation crée trois tables si elles manquent, moteur InnoDB, jeu de caractères `utf8_general_ci`. Le préfixe boutique précède chaque nom.

| Table | Colonnes de l'instruction CREATE |
| --- | --- |
| `hbp_block` | `id` (auto increment, clé primaire), `position` défaut 1, `hook` varchar(50), `active` défaut 0, `logged` défaut 0, `name` varchar(150), index `indek1` |
| `hbp_customhook` | `id`, `hook` varchar(70) |
| `hbp_block_lang` | `id`, `id_lang`, `body` text. L'instruction CREATE n'a pas de clé primaire |

Le modèle `models/hbox.php` mappe `hbp_block`, `body` est multilingue. L'ouverture suivante de la configuration ajoute les colonnes des filtres : `bssl`, `shop` (défaut 1), les drapeaux de page et de produit, les colonnes texte des id choisis, `datefrom`, `dateto`, `timfrom`, `timto`, `cgroup` (passé en varchar 250), `hcgroup`, `onmobile`, `ontablet`, `onpc` (défaut 1), les champs de prix, `daytype`, `currency`, `geoip` et les colonnes panier et livraison. `inconsistency()` élargit `hook` en varchar(255).

Autres fichiers : `views/templates/hook/html.tpl` est le corps en boutique, `views/templates/admin/_configure/helpers/form/form.tpl` remplace le formulaire helper de ce module, `lib/searchTool/` est la recherche d'id, `lib/smartyTemplatesManager/` sert `{smartyTemplate:name}`, `lib/prestashop9compatibility.php` est l'aide à l'affichage du prix. `key.php` est facultatif et absent de ce paquet. La licence de mise à jour dans `checkforupdates` est le littéral `nlc`.

Clés de configuration qui ne sont pas des colonnes : `hbp_notinyjs`, `hbp_tiny`, `hbp_forceurls`, `hbp_noajax`, `hbp_lasttab`, `firsttime_hbp`, `hbp_{hookname}`, `mypresta_updates`, `update_htmlboxpro`, `updatev_htmlboxpro`.

## Désactiver, activer, désinstaller

La classe n'a pas de `disable()` ni de `enable()`. Désactiver utilise le parent PrestaShop : le module reste installé, les tables et la configuration restent, les hooks ne s'exécutent pas. Activer utilise l'activation parente.

La classe n'a pas de `uninstall()`. La désinstallation utilise la méthode parente : le module est désenregistré et les enregistrements de hook que PrestaShop a stockés pour lui sont retirés. La méthode parente ne supprime pas `hbp_block`, `hbp_block_lang` ni `hbp_customhook`. Elle ne supprime pas les clés de configuration listées. Elle ne supprime pas les lignes `Hook` créées avec **Ajouter un nouveau hook** et ne restaure pas `htmlboxpro.php` après **régénérer maintenant !** ni après l'ajout d'un hook propre. Une installation suivante utilise `CREATE TABLE IF NOT EXISTS`, les lignes laissées dans ces tables restent.

## Zone vide sous les onglets

Le code accepte `selecttab` = 3 et peut stocker `hbp_lasttab` = 3. La barre n'a pas de troisième bouton et le rendu du formulaire n'a pas de page pour 3. Avec cette valeur la zone sous la barre est vide. **Paramètres** ou **Boîtes** réécrit 1 ou 2.

## Support

Page du module : [HTML Box Pro](https://mypresta.eu/modules/front-office-features/html-box-pro.html).
