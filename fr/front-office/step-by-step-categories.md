---
title: Step by Step - documentation et manuel utilisateur
sidebar:
  label: Step by Step - documentation et manuel utilisateur
description: Guide de réglage et de dépannage pour les boutiques qui ont déjà le filtre de catégories Step by Step.
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Step by step - categories sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/step-by-step-categories.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/step-by-step-categories/)
>
> ---


## 1. Prérequis

Le module tourne dans PrestaShop. Il n'a besoin d'aucun autre module ni d'un compte externe.

- PrestaShop à partir de 1.6.0.0, y compris PrestaShop 8 et 9.
- PHP dans la version demandée par cette version de PrestaShop. La vérification des mises à jour utilise cURL si PHP l'a. Sinon, elle ouvre l'adresse par une requête ordinaire. N'installez pas d'extension PHP supplémentaire pour les listes.
- Aucun autre module n'est nécessaire.
- En multiboutique, un bloc peut appartenir à une boutique ou à toutes.

## 2. Installation

1. Dans le back-office, ouvrez **Modules**, puis **Gestionnaire de modules**.
2. Envoyez le fichier zip et cliquez sur **Installer**.
3. Ouvrez **Configurer** sur **Step By Step - categories tree**. La page a **Blocks**, **Settings** et **Updates**. **Blocks** est la liste des jeux de listes. La première visite crée la page cachée de cette liste. Elle n'apparaît pas comme entrée propre dans le menu de gauche.
4. L'installation ne vide pas le cache dans une étape séparée. Si la boutique montre encore l'ancienne mise en page après une mise à jour, videz le cache dans **Paramètres avancés**, **Performances**.

La désinstallation retire cette page cachée. Les blocs, les titres, les libellés et les deux interrupteurs globaux restent dans la base. Après une réinstallation, les mêmes blocs sont là. Ouvrez **Configurer** une fois pour réenregistrer la page de liste.

En dehors de l'interrupteur habituel du **Gestionnaire de modules**, il n'y a pas d'action d'activation séparée. Si vous désactivez le module, les listes disparaissent de la boutique et les blocs enregistrés restent.

## 3. Configuration et utilisation dans le back-office

Vous créez un bloc, vous fixez la profondeur de l'arbre de catégories et vous choisissez l'emplacement dans la boutique. Le client choisit une catégorie. La liste suivante charge ses enfants. **ok** ouvre la catégorie choisie, ou un produit si la liste de produits est active.

Les captures de ce chapitre viennent du back-office en anglais. Les libellés à l'écran restent en anglais.

### 3.1 Page de configuration du module

Ouvrez **Modules**, **Gestionnaire de modules**, **Step By Step - categories tree**, **Configurer**.

![Réglages](https://mypresta.eu/docs/images/docs/stepbystep-configure-settings.webp)

En haut se trouvent **Blocks**, **Settings** et **Updates**. **Blocks** quitte cette page et ouvre la liste des blocs. **Settings** est l'onglet de départ. Sous la barre, le texte dit que ces options valent pour chaque bloc et que les blocs se modifient dans **Blocks**.

| Champ | Au départ | Effet |
|---|---|---|
| **Reset search fields** | No | Yes vide les listes après une recherche. No garde les catégories choisies par le visiteur. Le navigateur garde ce choix 30 minutes. |
| **Include Select2 library** | No | Yes charge le script et la feuille de style supplémentaires pour **Search inside dropdown** d'un bloc. No laisse des listes ordinaires. |

Cliquez sur **Save**. La page affiche **Settings saved.**

![Mises à jour](https://mypresta.eu/docs/images/docs/stepbystep-configure-updates.webp)

**Updates** est le formulaire **MyPresta updates**.

| Champ | Au départ | Effet |
|---|---|---|
| **Manual check** | bouton **Check now** | Demande à MyPresta si une version plus récente existe. **New version available!** mène au journal des modifications. **Module is up to date!** signifie que cette installation correspond à la version publiée. Le bouton n'envoie pas de zip. |
| **Automatic notifications** | Enabled | Enabled répète cette vérification environ tous les 3 jours pendant que vous travaillez dans le back-office. Disabled la saute. |
| **Product page** | lien vers la page du module | Ouvre la page Step by Step sur mypresta.eu. |

**Save** affiche **Update settings saved.** Envoyez un nouveau zip depuis le **Gestionnaire de modules** lorsqu'une version plus récente est indiquée.

### 3.2 Liste des blocs

Ouvrez **Blocks**. Sous la barre, le texte dit que chaque bloc est un jeu de listes.

![Liste des blocs](https://mypresta.eu/docs/images/docs/stepbystep-blocks-list.webp)

| Champ | Au départ | Effet |
|---|---|---|
| **ID** | attribué à l'enregistrement | Numéro du bloc. Il sert à distinguer les lignes. |
| **Title** | Block et le numéro, jusqu'à ce que vous saisissiez un titre | Titre dans la langue du back-office. |
| **Depth** | 3 pour un bloc nouveau | Combien de listes le bloc dessine. |
| **Root category** | catégorie Home de la boutique pour un bloc nouveau | Parent de la première liste, en numéro et en nom. |
| **Hook** | Top pour un bloc nouveau | Emplacement du bloc dans la boutique. |
| **Active** | Yes | L'icône active ou désactive le bloc. Off masque les listes et laisse la ligne. |
| **Position** | prochaine position libre | Glissez la ligne pour changer l'ordre des blocs du même hook. |

Les actions de ligne sont **Edit** et **Delete**. **Bulk actions** a **Enable selection**, **Disable selection** et **Delete selected**. La confirmation demande **Delete selected blocks?**

**Add new** ouvre un formulaire vide. Un bloc nouveau est actif, profondeur 3, racine la catégorie Home, tri par ID croissant, compteur de produits éteint, bouton après la dernière liste, produits éteints, envoi automatique éteint, recherche dans la liste éteinte, libellé dans la liste, hook Top et la boutique en cours. Enregistrez-le. Le formulaire se rouvre pour que vous remplissiez les libellés. Les libellés n'apparaissent dans le formulaire que lorsque le bloc existe.

La liste montre les blocs de la boutique où vous êtes et les blocs avec **All shops**.

### 3.3 Formulaire du bloc

Ouvrez une ligne avec **Edit**, ou utilisez **Add new** puis l'écran d'édition qui suit le premier enregistrement.

![Formulaire du bloc, haut](https://mypresta.eu/docs/images/docs/stepbystep-block-form.webp)

![Formulaire du bloc, libellés et position](https://mypresta.eu/docs/images/docs/stepbystep-block-form-bottom.webp)

| Champ | Au départ | Effet |
|---|---|---|
| **Block title** | vide | Titre au-dessus des listes. Un champ par langue de la boutique. |
| **Depth** | 3 | Combien de listes le bloc dessine. Enregistrez le bloc et rouvrez-le pour remplir un libellé par niveau. Le formulaire montre au plus 30 champs de libellé. |
| **Root category** | catégorie Home | La première liste montre les enfants de cette catégorie. |
| **Sort method** | By ID | By ID, By name ou By position. Position est l'ordre de la catégorie dans le catalogue. |
| **Sort direction** | Ascending | Ascending ou Descending. |
| **Products counter** | No | Yes écrit le nombre de produits entre parenthèses après le nom de la catégorie. |
| **Submit button** | After last select box | After each select box montre **ok** au niveau où se trouve le client. After last select box montre un **ok** pour tout le jeu. |
| **Include products** | No | Yes montre une liste de produits de la dernière catégorie choisie. |
| **Auto submit** | No | Yes envoie le formulaire dès que la dernière catégorie disponible est choisie. La boutique ouvre cette catégorie. Cela vaut quand **Include products** est éteint. Si la catégorie choisie n'a pas d'enfants, la boutique l'ouvre aussi. |
| **Search inside dropdown** | No | Yes active la recherche dans les listes. Dans **Settings**, **Include Select2 library** doit aussi être allumé. |
| **Exclude categories** | vide | Identifiants de catégorie qui ne doivent pas apparaître dans les listes. Séparez-les par des virgules, par exemple 1,2,3,4,5,6. La recherche à côté du champ trouve une catégorie et ajoute son identifiant. |
| **Show on category pages** | vide | Vide montre le bloc sur chaque page où se trouve son hook. Des identifiants de catégorie, séparés par des virgules, le montrent seulement sur ces pages de catégorie. |
| **Label position** | Inside select box | Inside select box met le libellé comme première option. Outside select box l'imprime au-dessus du champ. |
| **Label 1**, **Label 2** et la suite | vide | Un champ par niveau et par langue. Ils apparaissent après l'enregistrement du bloc. Changez **Depth** et enregistrez si vous en voulez plus ou moins. |
| **Module position** | Top | Top, displaySearch, TopColumn, Left column, Right column, Home ou displaySbs. |
| **Position top settings** | Blocks | Blocks empile les listes. Wide horizontal bar les met sur une ligne. La barre large vaut sur Top et displaySearch. Les autres emplacements restent empilés. Sur la barre large, **ok** se place après la dernière liste et passe à la ligne suivante s'il n'y a pas de place. |
| **Shop** | la boutique que vous modifiez | Une boutique ou **All shops**. **All shops** laisse le bloc dans chaque boutique. |
| **Active** | Yes | No masque le bloc dans la boutique. |

Cliquez sur **Save**. PrestaShop affiche sa confirmation habituelle. Supprimer un bloc supprime aussi le titre, le choix de la barre large et les libellés de niveau.

Pour montrer un bloc dans un fichier de thème qui n'a pas de hook déjà placé, utilisez le hook displaySbs et mettez **Module position** sur displaySbs. Les autres emplacements se branchent dans **Apparence**, **Positions**, si le thème ne les imprime pas lui-même.

## 4. Boutique

Le client voit le titre du bloc et les listes.

1. La première liste montre les enfants de la catégorie racine. Les listes suivantes restent inactives tant que le niveau précédent n'a pas de catégorie.
2. Le client choisit une catégorie. Un indicateur couvre le bloc. La liste suivante se remplit avec les enfants. L'indicateur disparaît quand la liste est prête, et aussi si la requête échoue.
3. Les identifiants exclus sont absents de ces listes.
4. Avec **Submit button** sur after each select box, **ok** est au niveau en cours. Avec after last select box, il y a un **ok** pour le jeu.
5. **ok** ouvre la catégorie choisie.
6. Avec **Include products**, le dernier niveau ajoute une liste de produits. La première option est **- Select Product -**. **ok** utilise alors le produit choisi.
7. Avec **Auto submit** allumé et **Include products** éteint, la dernière catégorie s'ouvre sans **ok**. La même redirection vaut si la catégorie choisie n'a pas d'enfants.
8. Avec **Reset search fields** éteint, une visite suivante peut montrer les mêmes catégories. Le navigateur les garde 30 minutes. Avec l'option allumée, les listes partent vides.
9. Si **Search inside dropdown** et **Include Select2 library** sont allumés, le client peut taper dans la liste.

Dans la colonne gauche et la colonne droite, les niveaux se suivent, avec le titre en capitales comme sur Classic. Sur la barre large, les niveaux sont sur une ligne. Sur un écran étroit, la barre large s'empile. Les couleurs, le cadre et le bouton **ok** viennent du thème, y compris Hummingbird et Classic sous PrestaShop 9.

Un bloc dont **Show on category pages** est rempli est absent des autres pages. Un bloc inactif est absent. Un bloc d'une autre boutique est absent aussi.

## 5. Problèmes

**Le bloc est absent de la boutique.** Ouvrez le bloc et vérifiez **Active**, **Module position** et **Shop**. **Show on category pages** vide le montre sur chaque page de ce hook. Une liste remplie le montre seulement sur ces pages de catégorie. Dans **Apparence**, **Positions**, vérifiez que le hook est sur les pages prévues. Pour un emplacement propre, le template doit appeler displaySbs et le bloc doit utiliser cette position.

**La liste suivante ne se remplit pas, ou l'indicateur reste.** Videz le cache de la boutique pour qu'elle prenne la feuille de style et le script actuels. L'indicateur doit disparaître quand la requête se termine, même si la réponse ne peut pas être appliquée. Si la boutique montre encore l'ancien chargeur gif, l'ancien CSS est en cache.

**La recherche dans la liste ne fait rien.** Allumez **Include Select2 library** dans **Settings** et **Search inside dropdown** sur le bloc. Enregistrez les deux. Videz le cache.

**Un bloc nouveau n'a pas de libellés.** Enregistrez le bloc une fois. Rouvrez-le. **Label 1** et la suite apparaissent quand le bloc existe, et seulement jusqu'au **Depth** enregistré.

**Une catégorie attendue manque dans la liste.** Retirez son identifiant de **Exclude categories**. Vérifiez qu'elle est enfant du parent choisi et qu'elle est active dans le catalogue.

**La barre large empile encore les champs.** **Wide horizontal bar** vaut sur Top et displaySearch. Gauche, droite, accueil, TopColumn et displaySbs restent empilés. Sur téléphone, la barre large s'empile exprès.

**Après une mise à jour, la page Blocks manque.** Ouvrez **Configurer** une fois. Cette visite enregistre la page. Ne désinstallez pas le module si vous voulez garder les lignes déjà là. La désinstallation retire la page et laisse les lignes.

**L'ancien écran de configuration n'a pas d'icône de corbeille.** C'est une version antérieure. Envoyez le zip actuel depuis le compte client. Dans la version actuelle, vous supprimez un bloc dans la liste **Blocks**, avec **Delete** sur la ligne ou avec **Delete selected**.

## 6. Pour les développeurs

### 6.1 Vue d'ensemble

Nom technique `stepbystep`, classe `Stepbystep`, version 1.9.0, auteur MyPresta.eu, onglet `front_office_features`. Le nom dans le back-office est **Step By Step - categories tree**.

`AdminStepbystepBlocksController` écrit les lignes dans `sbs_block` et le titre, les libellés et l'indicateur de barre large dans `Configuration`. Les hooks de la boutique lisent les lignes actives de la boutique en cours ou avec `id_shop = 0`. `controllers/front/tree.php` fournit le script qui remplit la liste suivante.

### 6.2 Fichiers

| Fichier | Rôle |
|---|---|
| `stepbystep.php` | Installation, hooks, formulaire de réglages, HTML des listes, script de la boutique. |
| `controllers/admin/AdminStepbystepBlocksController.php` | Liste des blocs et formulaire du bloc. |
| `models/SbsBlock.php` | Modèle d'objet de `sbs_block`. |
| `controllers/front/tree.php` | Contrôleur de boutique qui fournit le script du niveau suivant. |
| `views/templates/hook/front.tpl` | Balisage de la boutique pour chaque hook. |
| `views/templates/hook/header.tpl` | Imprime le script en ligne. |
| `views/templates/admin/configure.tpl` | Barre Blocks, Settings, Updates. |
| `css/sbs-front.css` | Mise en page de la boutique, variables du thème, indicateur. |
| `js/advajax.js` | Requête des listes. |
| `lib/updatesChecker.php` | Vérification des mises à jour. Classe `stepbystepUpdate`. |
| `lib/searchTool/searchTool.php` | Recherche de l'identifiant de catégorie dans le formulaire du bloc. Classe `searchToolstepbystep`. |
| `lib/prestashop9compatibility.php` | Classe `stepbystepPrestashopNewCompatibility`. |
| `views/css/admin.css` | Barre du back-office. |

`tree.php` à la racine du module est l'ancienne copie du contrôleur de boutique. Le lien de la boutique utilise `controllers/front/tree.php`. `views/templates/hook/block.tpl`, `blockSbs.tpl`, `top.tpl` et `displaySearch.tpl` ne sont pas rendus. `css/sbs-block.css` et `css/sbs-top.css` ne sont pas chargés.

### 6.3 Contrôleurs

`AdminStepbystepBlocksController` étend `ModuleAdminController`. `class_name` est `AdminStepbystepBlocks`. `id_parent` est `-1`, la page est cachée dans le menu. L'identifiant de liste est `id`. Le glisser de position appelle `ajaxProcessUpdatePositions`. Le filtre de liste est `id_shop` de la boutique du contexte ou `0`.

`stepbysteptreeModuleFrontController` est le contrôleur de boutique `tree`. `initContent` met `ajax` et n'appelle pas `parent::initContent`. Il lit `sbs_block`, `sbs_pid`, `sbs_lvl`, et à la confirmation `sbs_blockid` et `sbs_cidlink`. Le corps de la réponse est du JavaScript. Un bloc absent ferme la réponse.

### 6.4 Hooks

Hooks enregistrés : `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayTop`, `displaySearch`, `displayHome`, `displaySbs`, `displayBackOfficeHeader`. À partir de PrestaShop 1.6, aussi `displaytopColumn`.

| Hook | Valeur de position du bloc | Mise en page |
|---|---|---|
| `displayTop` | 1 | haut, barre large si `sbs_top_type{id}` vaut 1 |
| `displayLeftColumn` | 2 | empilé |
| `displayRightColumn` | 3 | empilé |
| `displayHome` | 4 | empilé |
| `displaytopColumn` | 5 | empilé |
| `displaySearch` | 6 | haut, barre large si `sbs_top_type{id}` vaut 1 |
| `displaySbs` | 7 | empilé |

`displayHeader` charge `js/advajax.js` et `css/sbs-front.css`. Si `SBS_SELECT2` vaut 1, il charge aussi Select2. Il n'y a pas de surcharge de `enable()` ni de `disable()`.

### 6.5 Surcharges

Le module ne remplace aucune classe ni aucun contrôleur de PrestaShop.

### 6.6 Base de données

| Table | Contenu |
|---|---|
| `ps_sbs_block` | `id`, `depth`, `root`, `orderby`, `orderway`, `counter`, `each_submit`, `lbl_position`, `block_position`, `position`, `active`, `products`, `last_submit`, `search_inside`, `exclude`, `id_shop`, `on_cat_only`, `id_categories`. |

Le préfixe est celui de la boutique. La désinstallation ne supprime pas la table. `inconsistency()` ajoute une colonne manquante de cette liste quand la configuration du module ou la liste des blocs s'ouvre. `on_cat_only` reste et n'est pas dans le formulaire. La boutique utilise `id_categories`.

### 6.7 Clés de configuration et traductions

| Clé | Si elle manque |
|---|---|
| `SBS_RESET` | Compte pour 0. Le choix reste 30 minutes dans les cookies `sbs_selectbox_{block}_{level}`. |
| `SBS_SELECT2` | Compte pour 0. Select2 n'est pas chargé. |
| `sbs_title{id}` | Titre du bloc, multilingue. |
| `{id}sbs_lbl_{n}` | Libellé du niveau `n`, multilingue, de 1 à la profondeur, au plus 30. |
| `sbs_top_type{id}` | 0 empilé, 1 barre large. |

L'installation écrit aussi `sbs_depth`, `sbs_counter`, `sbs_each_submit`, `sbs_position`, `sbs_lbl_position` et `sbs_root`. Le formulaire du bloc ne lit pas ces clés. Les blocs nouveaux utilisent les valeurs de `prepareObjectDefaults()`.

Les traductions sont dans `translations/{iso}.php`. Les textes du contrôleur de blocs ont la source `AdminStepbystepBlocksController`. Le texte du bouton est le texte du module `ok`. Le libellé produit est `- Select Product -`.

### 6.8 Extension

Remplacez `views/templates/hook/front.tpl` dans le thème sous `themes/{theme}/modules/stepbystep/views/templates/hook/front.tpl`. Remplacez `css/sbs-front.css` par le même chemin si le thème doit changer la mise en page. La place du bouton sur la barre large est l'ordre flex de cette feuille : le `.sbs__actions` visible se place après les listes et passe à la ligne avec elles.

## 7. Aide

Page du module : [Step by Step categories](https://mypresta.eu/modules/front-office-features/step-by-step-categories.html).

Pour écrire au sujet de ce module, connectez-vous au compte client sur [mypresta.eu](https://mypresta.eu), ouvrez le formulaire de contact et choisissez **Support for paid modules**. Ce sujet indique qu'une connexion est nécessaire. Après la connexion, choisissez ce module dans l'historique d'achats.
