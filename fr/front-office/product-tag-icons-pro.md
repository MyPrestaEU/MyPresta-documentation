---
title: "Product Tag Icons Pro - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Product Tag Icons Pro par MyPresta.eu."
sidebar:
  label: "Product Tag Icons Pro - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Product Tag Icons Pro sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-tag-icons-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/product-tag-icons-pro/)
>
> ---


# Product Tag Icons Pro

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises et sont présentes sur la plupart des environnements d'hébergement modernes. Aucune configuration de serveur spéciale n'est nécessaire.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

Le module « Product Tag Icons Pro » offre un ensemble complet d'options de configuration réparties sur plusieurs écrans dédiés dans votre back office PrestaShop.

### 2.1 Page de configuration du module (Back Office > Modules > Gestionnaire de modules > Configurer Product Tag Icons Pro)

Ceci est l'écran de configuration principal pour les paramètres généraux du module.

- **Ce que fait ce paramètre :** Contrôle le comportement général et les options d'affichage par défaut de vos icônes de produit.
- **Effet de la modification de ce paramètre :** Ces paramètres ont un impact sur la façon dont les icônes sont affichées dans toute votre boutique, ou sur la façon dont le module interagit avec d'autres parties de PrestaShop.
- **Valeur recommandée :** Varie en fonction du design de votre boutique et de la fonctionnalité souhaitée.

**Tableau de référence rapide de la configuration (Configuration principale du module)**

| Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- |
| **Activer le module** | OUI | **Objectif :** Active ou désactive la fonctionnalité du module. **Impact :** Si désactivé, aucune icône n'apparaîtra sur votre front office, et les fonctionnalités du module seront inactives. Gardez-le activé pour utiliser le module. |
| **Taille de l'icône (px)** | 32 | **Objectif :** Définit la taille par défaut (largeur et hauteur) pour toutes les icônes affichées sur le front office. **Impact :** Toutes les icônes seront rendues à cette taille en pixels spécifiée. Choisissez une taille qui s'intègre bien avec vos images de produits et le design général sans être trop petite pour être vue ou trop grande pour être intrusive. |
| **Position de l'icône (Hook)** | `displayProductAdditionalInfo` (ou un hook de page produit similaire) | **Objectif :** Détermine où sur la page produit les icônes seront affichées par défaut. Vous pouvez choisir parmi une liste de hooks PrestaShop disponibles. **Impact :** Les icônes apparaîtront dans la section sélectionnée de la page produit. Expérimentez avec différents hooks pour trouver le meilleur placement visuel pour votre thème. Les choix courants incluent `displayProductAdditionalInfo`, `displayProductPriceBlock` ou `displayAfterProductThumbs`. |
| **Afficher les icônes sur la liste de produits** | OUI | **Objectif :** Contrôle si les icônes sont visibles sur les pages de liste de produits (catégories, résultats de recherche, produits phares de la page d'accueil). **Impact :** Si activé, les icônes attribuées aux produits apparaîtront sur leurs fiches/vignettes de produits respectives dans les listes. Si désactivé, les icônes n'apparaîtront que sur les pages de produits individuelles. Recommandé de l'activer pour un impact maximal. |
| **Type d'info-bulle** | Light | **Objectif :** Sélectionne le thème visuel de l'info-bulle qui apparaît lorsqu'un client survole une icône. Les options incluent généralement Light, Noir, Punk, Shadow. **Impact :** Modifie l'apparence de la boîte d'info-bulle (arrière-plan, couleur du texte, bordure) qui affiche la description de l'icône. Choisissez-en une qui correspond à l'esthétique de votre boutique. |
| **Position de l'info-bulle** | Top | **Objectif :** Détermine où l'info-bulle apparaît par rapport à l'icône lorsqu'elle est survolée (par exemple, Top, Bottom, Left, Right). **Impact :** Affecte l'expérience utilisateur lors de l'interaction avec les icônes. Choisissez une position qui n'obstrue pas d'autres informations importantes sur la page. |
| **Activer les animations d'info-bulle** | OUI | **Objectif :** Ajoute des animations subtiles (fondu, glissement) lorsque les info-bulles apparaissent et disparaissent. **Impact :** Rend l'interaction avec l'info-bulle plus moderne et engageante. Si vous préférez une apparence statique et instantanée, désactivez cette option. |
| **CSS personnalisé** | (Vide) | **Objectif :** Vous permet d'ajouter des règles CSS personnalisées pour styliser davantage vos icônes ou info-bulles sans modifier les fichiers du module. **Impact :** Toutes les règles CSS saisies ici seront appliquées aux éléments du module, remplaçant les styles par défaut. Utilisez ceci pour affiner les couleurs, les marges ou les comportements spécifiques des icônes. |

### 2.2 Écran d'administration dédié : Gérer toutes les icônes (Back Office > Product Tag Icons Pro > Gérer toutes les icônes)

Cet écran vous permet de créer, modifier et supprimer les définitions d'icônes que vous associerez ensuite à vos produits.

- **Nom de l'écran et emplacement du menu :** Vous le trouverez sous **Product Tag Icons Pro > Gérer toutes les icônes** dans le menu de votre back office PrestaShop.
- **Actions et paramètres disponibles :**
  - **Ajouter une nouvelle icône :** Cliquez sur le bouton « Ajouter une nouvelle icône » pour créer une nouvelle icône.
    - **Nom de l'icône :** Un nom descriptif pour votre icône (par exemple, « Livraison Gratuite », « Nouvelle Arrivée »). Ceci est pour votre référence interne.
    - **Image de l'icône :** Téléchargez le fichier image de votre icône. Il doit s'agir d'une petite image claire (par exemple, PNG, JPG, SVG).
    - **Description de l'icône :** Un court texte qui apparaîtra comme une info-bulle lorsque les clients survoleront l'icône sur le front office. Expliquez ce que l'icône signifie.
    - **Actif :** Active ou désactive la disponibilité et l'affichage de cette icône.
    - **Champs spécifiques à la langue :** Si votre boutique est multilingue, vous pouvez fournir différents noms et descriptions pour chaque langue.
  - **Modifier l'icône :** Cliquez sur le bouton « Modifier » à côté d'une icône existante dans la liste pour modifier ses détails.
  - **Supprimer l'icône :** Cliquez sur le bouton « Supprimer » pour supprimer une icône. Soyez prudent, car cela supprimera également ses associations avec tous les produits.
  - **Vue grille / gestion :** Un tableau listant toutes vos icônes créées, affichant leur nom, image, description et statut actif. Vous pouvez trier et filtrer cette liste.
- **Effet des modifications :**
  - **Ajouter une icône :** Rend une nouvelle icône disponible pour association avec des produits.
  - **Modifier une icône :** Met à jour l'image, le nom ou la description pour toutes les instances de cette icône dans votre boutique.
  - **Supprimer une icône :** Supprime entièrement l'icône et elle n'apparaîtra plus sur les produits auxquels elle était précédemment attribuée.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Planifiez vos icônes : Décidez des caractéristiques clés ou des promotions que vous souhaitez mettre en évidence.
  2. Créez des images d'icônes petites et de haute qualité (par exemple, 32x32px ou 64x64px) qui correspondent à votre marque.
  3. Allez dans « Gérer toutes les icônes » et ajoutez chaque icône, en fournissant un nom clair et une description d'info-bulle utile.
  4. Assurez-vous que toutes les icônes sont « Actives » si vous avez l'intention de les utiliser.

### 2.3 Écran d'administration dédié : Gérer les associations d'icônes (Back Office > Product Tag Icons Pro > Gérer les associations d'icônes)

Cet écran est l'endroit où vous liez vos icônes créées à des produits spécifiques de votre catalogue.

- **Nom de l'écran et emplacement du menu :** Vous le trouverez sous **Product Tag Icons Pro > Gérer les associations d'icônes** dans le menu de votre back office PrestaShop.
- **Actions et paramètres disponibles :**
  - **Recherche de produits :** Utilisez la barre de recherche pour trouver des produits par nom, ID ou référence.
  - **Liste de produits :** Une fois que vous avez recherché des produits, ils apparaîtront dans une liste.
  - **Attribuer des icônes :** Pour chaque produit, vous verrez une section où vous pouvez sélectionner les icônes que vous avez créées qui doivent être affichées pour ce produit spécifique. Il s'agit généralement d'une liste déroulante à sélection multiple ou d'une liste de cases à cocher.
  - **Enregistrer les modifications :** Après avoir attribué ou désattribué des icônes pour un produit, n'oubliez pas d'enregistrer vos modifications.
  - **Vue grille / gestion :** Un tableau affichant les produits et leurs icônes actuellement associées.
- **Effet des modifications :**
  - **Attribuer une icône à un produit :** L'icône sélectionnée apparaîtra désormais sur le front office pour ce produit spécifique (sur sa page produit et dans les listes de produits, selon les paramètres principaux de votre module).
  - **Désattribuer une icône d'un produit :** L'icône ne sera plus affichée pour ce produit.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Après avoir créé vos icônes (dans « Gérer toutes les icônes »), accédez à cet écran.
  2. Recherchez le produit que vous souhaitez étiqueter.
  3. Sélectionnez les icônes pertinentes dans la liste pour ce produit.
  4. Répétez l'opération pour tous les produits que vous souhaitez étiqueter.
  5. Révisez périodiquement vos étiquettes de produits, surtout lors du lancement de nouveaux produits ou de promotions.

### 2.4 Tableau de référence rapide de la configuration (Tous les écrans)

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
|---|---|---|
| **Configuration du module** | Activer le module | OUI | Active/désactive le module. |
| | Taille de l'icône (px) | 32 | Définit la taille d'affichage par défaut de l'icône. |
| | Position de l'icône (Hook) | `displayProductAdditionalInfo` | Placement par défaut sur la page produit. |
| | Afficher les icônes sur la liste de produits | OUI | Affiche les icônes sur les pages de catégorie/recherche. |
| | Type d'info-bulle | Light | Thème visuel pour les descriptions d'icônes. |
| | Position de l'info-bulle | Top | Où l'info-bulle apparaît par rapport à l'icône. |
| | Activer les animations d'info-bulle | OUI | Animations fluides pour les info-bulles. |
| | CSS personnalisé | (Vide) | Ajoute un style personnalisé pour les icônes/info-bulles. |
| **Gérer toutes les icônes** | Ajouter une nouvelle icône | N/A | Crée une nouvelle définition d'icône. |
| | Nom de l'icône | (Descriptif) | Nom interne de l'icône. |
| | Image de l'icône | (Télécharger le fichier) | Représentation visuelle de l'icône. |
| | Description de l'icône | (Texte de l'info-bulle) | Texte affiché au survol. |
| | Actif | OUI | Active/désactive l'icône pour utilisation. |
| | Modifier l'icône | N/A | Modifie les détails d'une icône existante. |
| | Supprimer l'icône | N/A | Supprime une définition d'icône. |
| **Gérer les associations d'icônes** | Recherche de produits | N/A | Trouve les produits à étiqueter. |
| | Attribuer des icônes | N/A | Lie les icônes créées à des produits spécifiques. |
| | Enregistrer les modifications | N/A | Applique les attributions d'icônes aux produits. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q1 : Mes icônes n'apparaissent pas sur le front office, que dois-je faire ?**
R :

1. **Vérifier l'état du module :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que « Product Tag Icons Pro » est activé.
2. **Vérifier l'état de l'icône :** Allez dans **Product Tag Icons Pro > Gérer toutes les icônes** et vérifiez que les icônes spécifiques que vous essayez d'afficher sont marquées comme « Actives ».
3. **Vérifier les associations de produits :** Allez dans **Product Tag Icons Pro > Gérer les associations d'icônes** et confirmez que les icônes sont correctement attribuées aux produits sur lesquels vous vous attendez à les voir apparaître.
4. **Vider le cache :** Allez dans **Paramètres avancés > Performance** et cliquez sur « Vider le cache Smarty » et « Vider le cache » (si disponible). Parfois, d'anciennes données mises en cache empêchent l'apparition des nouvelles modifications du module.
5. **Vérifier la position du hook :** Dans la configuration principale du module, assurez-vous d'avoir sélectionné un hook valide et approprié pour l'affichage des icônes (par exemple, `displayProductAdditionalInfo`). Certains thèmes peuvent avoir des hooks personnalisés ou ne pas rendre certains hooks standard.

**Q2 : Les icônes semblent trop grandes/petites ou ne correspondent pas au design de mon thème.**
R :

1. **Ajuster la taille de l'icône :** Dans la configuration principale du module, modifiez le paramètre « Taille de l'icône (px) » à vos dimensions souhaitées.
2. **CSS personnalisé :** Si un simple ajustement de taille ne suffit pas, utilisez le champ « CSS personnalisé » dans la configuration principale du module pour affiner le style. Vous pouvez cibler des classes d'icônes spécifiques (par exemple, `.ticon-image`) pour ajuster les marges, le rembourrage ou même appliquer des filtres.
3. **Compatibilité du thème :** Bien que le module soit conçu pour être compatible, certains thèmes très personnalisés peuvent nécessiter des ajustements CSS mineurs. Si vous êtes à l'aise avec le CSS, inspectez les éléments à l'aide des outils de développement de votre navigateur pour identifier les sélecteurs pertinents.

**Q3 : Les info-bulles n'apparaissent pas ou ont l'air étranges.**
R :

1. **Activer les info-bulles :** Assurez-vous que la fonction d'info-bulle est activée dans la configuration principale du module.
2. **Vérifier le contenu de l'info-bulle :** Vérifiez que vous avez saisi une « Description » pour chaque icône dans **Product Tag Icons Pro > Gérer toutes les icônes**. Cette description est ce qui apparaît dans l'info-bulle.
3. **Thème/Position de l'info-bulle :** Expérimentez avec différents paramètres de « Type d'info-bulle » et de « Position de l'info-bulle » dans la configuration principale du module pour voir si une option différente résout le problème ou s'intègre mieux à votre thème.
4. **Conflits JavaScript :** Dans de rares cas, le JavaScript d'un autre module peut entrer en conflit. Vérifiez la console de développement de votre navigateur pour toute erreur JavaScript. Si vous trouvez des erreurs, essayez de désactiver temporairement d'autres modules un par un pour isoler le conflit.

**Q4 : Puis-je traduire les noms et descriptions des icônes pour différentes langues ?**
R : Oui ! Lorsque vous créez ou modifiez une icône dans **Product Tag Icons Pro > Gérer toutes les icônes**, vous verrez des onglets de langue (par exemple, « Français », « Anglais », « Espagnol ») à côté des champs « Nom de l'icône » et « Description de l'icône ». Il suffit de passer à l'onglet de la langue souhaitée et de saisir la traduction pour cette langue spécifique. Le module affichera automatiquement la traduction correcte en fonction de la langue sélectionnée par le client.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de la structure technique du module « Product Tag Icons Pro », destinée aux développeurs, webmasters et agences techniques.

### 4.1 Vue d'ensemble de l'architecture

Le module « Product Tag Icons Pro » (`ticons`) suit une architecture de module PrestaShop standard, exploitant principalement le modèle MVC. Il étend `Module` pour sa fonctionnalité principale et utilise des instances `AdminController` dédiées pour gérer les icônes et leurs associations. Les données sont stockées dans des tables de base de données personnalisées, et l'affichage en front-office est réalisé via divers hooks PrestaShop et des templates Smarty. Le module intègre également des bibliothèques tierces pour une interface utilisateur améliorée (par exemple, Tooltipster pour les info-bulles, un autocomplétion personnalisé pour la recherche de produits).

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ce module ne définit pas explicitement de contrôleurs front-office personnalisés. Tout le rendu front-office est géré via des méthodes `hook` au sein de la classe principale du module (`ajax_ticons.php`) et des templates Smarty associés.

#### Contrôleurs d'administration Back-Office

- **`ticons/controllers/admin/AdminTiconsAllController.php`**

  - **Nom de la classe :** `AdminTiconsAllController` (étend `ModuleAdminController`)
  - **Nom de l'onglet :** « Gérer toutes les icônes »
  - **Responsabilité :** Gère la création, la modification et la suppression des définitions d'icônes individuelles. Il gère les opérations CRUD pour l'entité `ticon`. Ce contrôleur utilise `HelperList` pour afficher la liste des icônes et `HelperForm` pour le formulaire d'ajout/modification. Il gère les téléchargements d'images d'icônes.
- **`ticons/controllers/admin/AdminTiconsAssociationsController.php`**

  - **Nom de la classe :** `AdminTiconsAssociationsController` (étend `ModuleAdminController`)
  - **Nom de l'onglet :** « Gérer les associations d'icônes »
  - **Responsabilité :** Gère l'association des icônes créées avec des produits spécifiques. Il fournit une interface pour rechercher des produits, puis leur attribuer/désattribuer plusieurs icônes. Ce contrôleur utilise également `HelperList` pour l'affichage des produits et un formulaire personnalisé pour la sélection des icônes. Il gère les requêtes AJAX pour l'autocomplétion de la recherche de produits.
- **`ticons/controllers/admin/index.php`**

  - **Responsabilité :** Il s'agit d'un fichier `index.php` vide standard, généralement présent dans les répertoires PrestaShop pour empêcher la liste des répertoires. Il ne contient aucune logique de contrôleur fonctionnelle.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne définit pas explicitement de fichiers PHP séparés dans un répertoire `classes/`. Au lieu de cela, le fichier principal du module `ajax_ticons.php` contient probablement les définitions `ObjectModel` pour `Ticon` et `TiconProduct` (ou des entités similaires) directement dans sa portée, ou elles sont implicitement gérées via des interactions avec la base de données.

- **`Ticon` (ObjectModel implicite) :**

  - **Table de base de données :** `ps_ticons` (ou similaire, basé sur la méthode `install()` du module).
  - **Champs :** Inclut probablement `id_ticon`, `name` (multilingue), `description` (multilingue), `image`, `active`.
  - **Objectif :** Représente une définition d'icône individuelle, y compris son image, son nom et sa description d'info-bulle.
- **`TiconProduct` (ObjectModel implicite) :**

  - **Table de base de données :** `ps_ticon_products` (ou similaire, basé sur la méthode `install()` du module).
  - **Champs :** Inclut probablement `id_ticon_product`, `id_ticon`, `id_product`.
  - **Objectif :** Représente la relation plusieurs-à-plusieurs entre les icônes et les produits.

### 4.4 Actifs JavaScript (`views/js/`)

- **`ticons/lib/searchTool/views/js/autocomplete.js`**

  - **Portée :** Back-office (AdminTiconsAssociationsController).
  - **Fonctionnalité :** Fournit une fonctionnalité de recherche par autocomplétion pour les produits dans l'écran « Gérer les associations d'icônes ». Il envoie probablement des requêtes AJAX au contrôleur d'administration pour récupérer des suggestions de produits au fur et à mesure que l'utilisateur tape.
- **`ticons/lib/tooltipster/js/jquery.tooltipster.js`**

  - **Portée :** Front-office.
  - **Fonctionnalité :** Il s'agit de la bibliothèque principale du plugin Tooltipster. Elle gère la création, le positionnement et le style des info-bulles interactives qui apparaissent lorsque les utilisateurs survolent les icônes de produits. Elle lie les événements de survol aux éléments avec des classes spécifiques (par exemple, `.tooltipster`).
- **`ticons/views/js/ticons-front.js`**

  - **Portée :** Front-office.
  - **Fonctionnalité :** Contient du JavaScript personnalisé spécifique à l'affichage des icônes en front-office. Ce script initialise probablement le plugin Tooltipster sur les éléments d'icônes pertinents, en passant les options de configuration (thème, position, animation) basées sur les paramètres du back-office du module. Il garantit que les icônes sont correctement rendues et interactives.
- **`ticons/views/js/ticons.js`**

  - **Portée :** Back-office.
  - **Fonctionnalité :** Contient du JavaScript général pour les écrans de configuration et de gestion du back-office du module. Cela peut inclure la validation de formulaire, la manipulation dynamique d'éléments ou d'autres améliorations de l'interface utilisateur pour l'interface d'administration.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`ticons/lib/searchTool/views/css/autocomplete.css`**

  - **Portée :** Back-office.
  - **Fonctionnalité :** Style la liste déroulante d'autocomplétion et le champ de saisie utilisés dans l'écran « Gérer les associations d'icônes ».
- **`ticons/lib/tooltipster/css/themes/tooltipster-light.css`**

  - **Portée :** Front-office.
  - **Fonctionnalité :** Définit les styles pour le thème « Light » du plugin Tooltipster.
- **`ticons/lib/tooltipster/css/themes/tooltipster-noir.css`**

  - **Portée :** Front-office.
  - **Fonctionnalité :** Définit les styles pour le thème « Noir » du plugin Tooltipster.
- **`ticons/lib/tooltipster/css/themes/tooltipster-punk.css`**

  - **Portée :** Front-office.
  - **Fonctionnalité :** Définit les styles pour le thème « Punk » du plugin Tooltipster.
- **`ticons/lib/tooltipster/css/themes/tooltipster-shadow.css`**

  - **Portée :** Front-office.
  - **Fonctionnalité :** Définit les styles pour le thème « Shadow » du plugin Tooltipster.
- **`ticons/lib/tooltipster/css/tooltipster.css`**

  - **Portée :** Front-office.
  - **Fonctionnalité :** Le CSS principal du plugin Tooltipster, fournissant les styles de base pour toutes les info-bulles.
- **`ticons/views/css/ticons-admin.css`**

  - **Portée :** Back-office.
  - **Fonctionnalité :** Contient du CSS personnalisé spécifiquement pour les interfaces back-office du module (par exemple, le style des listes d'icônes, des formulaires et des éléments personnalisés dans les contrôleurs d'administration).
- **`ticons/views/css/ticons-fontawesome.css`**

  - **Portée :** Front-office.
  - **Fonctionnalité :** Inclut ou importe probablement les icônes Font Awesome, qui pourraient être utilisées comme icônes de secours ou pour des éléments d'interface utilisateur spécifiques au sein de l'affichage du module.
- **`ticons/views/css/ticons-front-24.css`**, **`ticons/views/css/ticons-front-32.css`**, **`ticons/views/css/ticons-front-48.css`**, **`ticons/views/css/ticons-front-64.css`**, **`ticons/views/css/ticons-front-74.css`**

  - **Portée :** Front-office.
  - **Fonctionnalité :** Ces feuilles de style contiennent probablement des règles spécifiques pour différentes tailles d'icônes. Lorsque le marchand sélectionne une « Taille d'icône » dans la configuration, le module charge dynamiquement le fichier CSS correspondant pour s'assurer que les icônes sont rendues aux bonnes dimensions et potentiellement avec un espacement optimisé. Elles définissent des classes comme `.ticon-24`, `.ticon-32`, etc.
- **`ticons/views/css/ticons.css`**

  - **Portée :** Front-office.
  - **Fonctionnalité :** CSS général du front-office pour le module, y compris les styles de base pour les conteneurs d'icônes, les images et la mise en page globale. Ce fichier peut contenir des règles communes appliquées quelle que soit la taille d'icône sélectionnée.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/front/`)

Ces templates sont rendus lorsque le module est accroché à diverses positions du front-office. Ils reçoivent généralement un tableau de données d'icônes des méthodes `hook` du module.

- **`ticons/views/templates/front/deliveryTime.tpl`**

  - **Hook :** Potentiellement `displayProductDeliveryTime` ou similaire.
  - **Sortie :** Rend les icônes liées aux informations de livraison.
- **`ticons/views/templates/front/displayActions.tpl`**

  - **Hook :** `displayProductActions` ou similaire.
  - **Sortie :** Rend les icônes près des boutons d'action du produit (par exemple, « Ajouter au panier »).
- **`ticons/views/templates/front/displayAfterProductThumbs.tpl`**

  - **Hook :** `displayAfterProductThumbs` (PrestaShop 1.7+).
  - **Sortie :** Rend les icônes directement sous les images miniatures du produit sur la page du produit.
- **`ticons/views/templates/front/displayColumns.tpl`**

  - **Hook :** `displayLeftColumn`, `displayRightColumn`.
  - **Sortie :** Rend les icônes dans les modules de colonne gauche ou droite.
- **`ticons/views/templates/front/displayLeftColumn.tpl`**

  - **Hook :** `displayLeftColumn`.
  - **Sortie :** Rend les icônes spécifiquement dans la colonne de gauche.
- **`ticons/views/templates/front/displayProductAdditionalInfo.tpl`**

  - **Hook :** `displayProductAdditionalInfo` (PrestaShop 1.7+).
  - **Sortie :** Rend les icônes dans la section « Informations supplémentaires » de la page du produit, un emplacement courant et recommandé.
- **`ticons/views/templates/front/displayProductPriceBlock.tpl`**

  - **Hook :** `displayProductPriceBlock`.
  - **Sortie :** Rend les icônes près du bloc de prix du produit.
- **`ticons/views/templates/front/displayTop.tpl`**

  - **Hook :** `displayTop` (en-tête).
  - **Sortie :** Rend les icônes dans la section d'en-tête de la boutique.
- **`ticons/views/templates/front/listReviews.tpl`**

  - **Hook :** Potentiellement `displayProductListReviews` ou similaire.
  - **Sortie :** Rend les icônes liées aux avis ou évaluations de produits.
- **`ticons/views/templates/front/productFooter.tpl`**

  - **Hook :** `displayFooterProduct` ou similaire.
  - **Sortie :** Rend les icônes dans la section de pied de page de la page du produit.
- **`ticons/views/templates/front/showIcons.tpl`**

  - **Hook :** Il s'agit probablement d'un template générique inclus par d'autres templates de hook pour rendre la structure HTML réelle de l'icône (par exemple, des balises `<img>` avec des classes `tooltipster`). Il itère sur la variable `$icons` qui lui est passée.

#### Templates d'administration (`views/templates/admin/`)

Ces templates sont utilisés pour la configuration et les écrans de gestion du back-office du module.

- **`ticons/lib/searchTool/views/scripts.tpl`**

  - **Portée :** Back-office.
  - **Sortie :** Contient du JavaScript pour l'outil de recherche, incluant probablement l'initialisation de l'autocomplétion jQuery UI ou similaire.
- **`ticons/views/templates/admin/customHook.tpl`**

  - **Portée :** Back-office.
  - **Sortie :** Un template générique qui pourrait être utilisé pour rendre le contenu de hooks personnalisés définis dans l'interface d'administration du module, ou pour afficher des messages spécifiques.
- **`ticons/views/templates/admin/tabs.tpl`**

  - **Portée :** Back-office.
  - **Sortie :** Rend les onglets de navigation (par exemple, « Gérer toutes les icônes », « Gérer les associations d'icônes ») pour les pages de configuration du module.
- **`ticons/views/templates/admin/ticonsSelection.tpl`**

  - **Portée :** Back-office (AdminTiconsAssociationsController).
  - **Sortie :** Rend l'interface pour sélectionner et attribuer des icônes à un produit, généralement une liste déroulante à sélection multiple ou une liste de cases à cocher dans le formulaire d'association de produits.
- **`ticons/views/templates/admin/ticons_all/helpers/list/list_content.tpl`**

  - **Portée :** Back-office (AdminTiconsAllController).
  - **Sortie :** Personnalise le contenu du tableau `HelperList` pour afficher la liste de toutes les icônes créées. Il peut inclure des colonnes personnalisées pour les images d'icônes ou le statut actif.
- **`ticons/views/templates/admin/ticons_associations/helpers/form/form.tpl`**

  - **Portée :** Back-office (AdminTiconsAssociationsController).
  - **Sortie :** Personnalise le `HelperForm` pour l'écran d'association de produits. Ce template inclut probablement le champ de recherche de produits et le `ticonsSelection.tpl` pour l'attribution d'icônes.
- **`ticons/views/templates/admin/ticons_associations/helpers/list/list_content.tpl`**

  - **Portée :** Back-office (AdminTiconsAssociationsController).
  - **Sortie :** Personnalise le contenu du tableau `HelperList` pour afficher la liste des produits et de leurs icônes associées.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données

Le module crée des tables personnalisées lors de sa méthode `install()` pour stocker les définitions d'icônes et leurs associations :

- **`ps_ticons`** : Stocke les définitions principales des icônes.
  - `id_ticon` (PK, INT)
  - `image` (VARCHAR) : Nom de fichier de l'image de l'icône.
  - `active` (TINYINT) : 1 si actif, 0 si inactif.
- **`ps_ticons_lang`** : Stocke les champs multilingues pour les icônes.
  - `id_ticon` (PK, INT)
  - `id_lang` (PK, INT)
  - `name` (VARCHAR) : Nom de l'icône pour usage interne.
  - `description` (TEXT) : Texte de l'info-bulle pour l'icône.
- **`ps_ticon_products`** : Stocke la relation plusieurs-à-plusieurs entre les icônes et les produits.
  - `id_ticon_product` (PK, INT)
  - `id_ticon` (FK, INT)
  - `id_product` (FK, INT)

Les paramètres de configuration sont stockés dans `ps_configuration` avec des clés comme `TICONS_ICON_SIZE`, `TICONS_HOOK_POSITION`, `TICONS_SHOW_IN_LIST`, etc.

#### Tableau des hooks enregistrés

Le module enregistre plusieurs hooks pour afficher les icônes en front office. Les hooks exacts utilisés dépendent de la version de PrestaShop et de la configuration du marchand.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Met en file d'attente les ressources CSS et JS (Tooltipster, JS/CSS personnalisé). |
| `displayProductAdditionalInfo` | Sur la page produit, dans le bloc « Informations supplémentaires » (PS 1.7+). | Rend les icônes associées au produit actuel. |
| `displayProductPriceBlock` | Sur la page produit, près du prix. | Rend les icônes associées au produit actuel. |
| `displayAfterProductThumbs` | Sur la page produit, sous les images du produit (PS 1.7+). | Rend les icônes associées au produit actuel. |
| `displayProductListFunctionalButtons` | Sur les éléments de la liste de produits (par exemple, pages de catégorie). | Rend les icônes sur les fiches/miniatures de produits. |
| `displayProductListReviews` | Sur les éléments de la liste de produits, près des avis. | Rend les icônes sur les fiches/miniatures de produits. |
| `displayProductDeliveryTime` | Sur la page produit, près des informations de livraison. | Rend les icônes associées au produit actuel. |
| `displayLeftColumn` | Dans la colonne de gauche des pages. | Rend les icônes si configurées pour un affichage général. |
| `displayRightColumn` | Dans la colonne de droite des pages. | Rend les icônes si configurées pour un affichage général. |
| `displayFooterProduct` | En bas de la page produit. | Rend les icônes associées au produit actuel. |
| `actionProductUpdate` | Après la mise à jour d'un produit dans le back office. | Potentiellement vide le cache ou met à jour les associations d'icônes. |
| `actionProductDelete` | Après la suppression d'un produit. | Nettoie les entrées d'icônes associées de `ps_ticon_products`. |
| `actionObjectLanguageAddAfter` | Après l'ajout d'une nouvelle langue. | Garantit que les champs spécifiques à la langue pour les icônes sont gérés. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant le module « Product Tag Icons Pro ».
