---
title: "Homefeatured multi slider - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Homefeatured multi slider par MyPresta.eu."
sidebar:
  label: "Homefeatured multi slider - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Homefeatured multi slider sur MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/homefeatured-multi-slider.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/sliders-slideshows/homefeatured-multi-slider/)
>
> ---


# Homefeatured multi slider

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour qu'une boutique PrestaShop fonctionne correctement. Ce module n'a pas d'exigences d'hébergement inhabituelles ou spécifiques au-delà d'un environnement PrestaShop standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

Le module « Homefeatured multi slider » propose deux zones principales de configuration : la page de configuration principale du module pour les paramètres généraux et un écran d'administration dédié pour gérer vos sliders de produits et catégories.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran principal où vous configurerez le comportement général et l'apparence de votre slider de produits multi-vedettes. Pour y accéder, allez dans **Modules > Gestionnaire de modules**, trouvez « Homefeatured multi slider » et cliquez sur « Configurer ».

#### Onglet Paramètres généraux

| Paramètre / Option | Ce que fait ce paramètre | Effet de la modification de ce paramètre | Valeur recommandée | Scénario / exemple marchand |
| --- | --- | --- | --- | --- |
| **Afficher dans le Hook** | Détermine où le slider apparaîtra sur votre site web. | *Lorsqu'il est défini sur `displayHome` (ou un hook de contenu principal similaire) :* Le slider sera une caractéristique proéminente sur votre page d'accueil. *Lorsqu'il est défini sur `displayLeftColumn` ou `displayRightColumn` :* Le slider apparaîtra dans les barres latérales, généralement plus petit. *Lorsqu'il est défini sur `displayFooter` :* Le slider sera en bas de vos pages. | `displayHome` pour un slider de page d'accueil proéminent. | Vous voulez que vos principaux produits phares soient la première chose que les clients voient sur votre page d'accueil. |
| **Nombre de produits à afficher** | Contrôle le nombre de produits visibles dans le slider à un moment donné. | *Lorsqu'il est défini sur `4` :* Quatre produits seront affichés côte à côte (si l'espace le permet). *Lorsqu'il est défini sur `1` :* Un seul produit sera visible, souvent avec des images plus grandes. | `4` ou `5` pour la plupart des thèmes, selon la taille de vos images de produits et le design. | Vous avez de grandes images de produits et souhaitez afficher moins d'articles à la fois pour un meilleur détail, ou vous avez de petites images et souhaitez en afficher plus. |
| **Vitesse du slider (ms)** | Définit la vitesse à laquelle le slider effectue les transitions entre les produits ou les diapositives. Mesuré en millisecondes (1000ms = 1 seconde). | *Lorsqu'il est défini sur `500` :* Les transitions sont très rapides. *Lorsqu'il est défini sur `5000` :* Les transitions sont lentes, donnant aux clients plus de temps pour visualiser chaque produit. | `3000` (3 secondes) à `5000` (5 secondes) pour une expérience de visualisation confortable. | Vous voulez un affichage dynamique et rapide des produits, ou une expérience de navigation plus détendue et contemplative. |
| **Lecture automatique du slider** | Détermine si le slider fait automatiquement défiler les produits sans interaction de l'utilisateur. | *Lorsqu'il est activé (OUI) :* Le slider passera automatiquement au produit suivant après la « Vitesse du slider » définie. *Lorsqu'il est désactivé (NON) :* Le slider ne changera de diapositives que lorsque le client cliquera sur les flèches de navigation. | `OUI` pour maintenir le contenu dynamique et engageant. | Vous voulez vous assurer que tous les produits phares sont visibles même si les clients ne cliquent pas activement. |
| **Afficher les flèches de navigation** | Contrôle la visibilité des flèches « suivant » et « précédent » sur le slider. | *Lorsqu'il est activé (OUI) :* Les flèches apparaissent sur les côtés du slider, permettant une navigation manuelle. *Lorsqu'il est désactivé (NON) :* Les clients doivent compter sur la lecture automatique ou d'autres méthodes de navigation (si disponibles). | `OUI` pour un meilleur contrôle utilisateur et une meilleure accessibilité. | Vous voulez que les clients puissent facilement parcourir les produits à leur propre rythme. |
| **Afficher les points de pagination** | Contrôle la visibilité des petits points ou indicateurs, généralement en bas du slider, représentant chaque diapositive. | *Lorsqu'il est activé (OUI) :* Des points apparaissent, montrant la position de la diapositive actuelle et permettant de sauter directement à des diapositives spécifiques. *Lorsqu'il est désactivé (NON) :* Les points sont masqués. | `OUI` pour une meilleure orientation de l'utilisateur et un accès direct aux diapositives. | Vous voulez que les clients sachent combien de diapositives il y a et puissent sauter directement à une diapositive spécifique. |
| **Largeur de l'image du produit (px)** | Définit la largeur des images de produits dans le slider. | *Lorsqu'il est défini sur `200` :* Les images auront une largeur de 200 pixels. *Lorsqu'il est défini sur `300` :* Les images auront une largeur de 300 pixels. Cela affecte la taille globale et la mise en page du slider. | `250` à `350` pixels, selon le design de votre thème et le « Nombre de produits à afficher ». | Vos images de produits sont en haute résolution et vous voulez qu'elles apparaissent plus grandes, ou vous en avez besoin de plus petites pour afficher plus de produits. |
| **Hauteur de l'image du produit (px)** | Définit la hauteur des images de produits dans le slider. | *Lorsqu'il est défini sur `200` :* Les images auront une hauteur de 200 pixels. *Lorsqu'il est défini sur `300` :* Les images auront une hauteur de 300 pixels. Cela fonctionne conjointement avec la largeur pour maintenir le rapport d'aspect ou recadrer. | `250` à `350` pixels, correspondant à la largeur choisie pour les images carrées, ou ajusté pour le portrait/paysage. | Vous avez des images de produits avec des rapports d'aspect variés et souhaitez standardiser leur hauteur d'affichage. |
| **Couleur de fond** | Vous permet de définir une couleur de fond personnalisée pour l'ensemble du bloc du slider. | *Lorsqu'il est défini sur `#FFFFFF` (blanc) :* Le fond du slider sera blanc. *Lorsqu'il est défini sur `#F0F0F0` (gris clair) :* Le fond sera gris clair. | Laissez vide pour transparent ou utilisez une couleur qui correspond à votre thème. | Vous voulez que le slider se démarque avec une couleur de fond distincte, ou qu'il se fonde parfaitement avec le fond de votre page. |
| **Couleur du texte** | Définit la couleur des noms de produits et d'autres textes dans le slider. | *Lorsqu'il est défini sur `#000000` (noir) :* Le texte sera noir. *Lorsqu'il est défini sur `#333333` (gris foncé) :* Le texte sera gris foncé. | Une couleur qui offre un bon contraste avec la couleur de fond choisie. | Vous devez vous assurer que les noms de produits sont facilement lisibles sur le fond du slider. |
| **Couleur du prix** | Définit la couleur des prix des produits affichés dans le slider. | *Lorsqu'il est défini sur `#FF0000` (rouge) :* Les prix seront rouges, souvent utilisés pour les soldes. *Lorsqu'il est défini sur `#008000` (vert) :* Les prix seront verts. | Une couleur qui fait ressortir les prix, souvent la couleur d'accent de votre marque ou une couleur de prix standard. | Vous voulez que les prix soient très visibles et attirent l'attention. |

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Ce module comprend une section dédiée dans votre Back Office PrestaShop pour gérer les catégories de vos produits phares et leur attribuer des produits.

#### Nom de l'écran et emplacement du menu : « Multi Featured Slider »

Vous pouvez trouver cette section en naviguant vers :
**Modules > Gestionnaire de modules > Homefeatured multi slider > Configurer**
Sur la page de configuration, vous verrez un onglet ou un lien qui mène à l'interface de gestion « Multi Featured Slider ». Dans PrestaShop 1.7+, cela pourrait apparaître comme un nouvel élément de menu sous « Catalogue » ou « Modules » si le module enregistre son propre onglet.

Cet écran est géré par le `AdminprosliderController` (situé à `multihomefeatured/controllers/admin/adminproslider.php`).

**Actions et paramètres disponibles :**

Cet écran présente généralement une liste de vos « catégories de produits phares » créées (appelées « opinion » dans le code sous-jacent, mais fonctionnant comme des catégories pour votre slider).

-   **Tableau de liste :** Vous verrez un tableau listant toutes les catégories personnalisées que vous avez créées pour vos produits phares. Chaque ligne affichera probablement :
    -   **# (ID) :** Un identifiant unique pour la catégorie.
    -   **Nom de la catégorie :** Le nom que vous avez donné à ce groupe de produits phares (par exemple, « Meilleures ventes », « Nouveautés »).
    -   **Statut :** Si la catégorie est active (visible dans le slider) ou inactive.
    -   **Actions :** Boutons pour « Modifier » (modifier le nom de la catégorie, le statut et attribuer des produits) ou « Supprimer » la catégorie.
-   **Ajouter une nouvelle catégorie :** Il y aura un bouton (par exemple, « Ajouter une nouvelle catégorie » ou « Ajouter ») pour créer un nouveau groupe de produits phares. Lors de l'ajout ou de la modification d'une catégorie, vous trouverez généralement :
    -   **Nom de la catégorie :** Un champ de saisie pour définir le nom de votre catégorie de produits phares (par exemple, « Offres saisonnières », « Favoris des clients »).
    -   **Commutateur Actif/Inactif :** Un interrupteur pour activer ou désactiver l'affichage de cette catégorie spécifique dans le slider du front-office.
    -   **Attribution de produits :** C'est la fonctionnalité principale. Vous verrez probablement une barre de recherche ou une liste de produits disponibles. Vous pouvez rechercher des produits et les ajouter à cette catégorie spécifique. Les produits peuvent généralement être réorganisés au sein de la catégorie.

**Effet des changements :**

-   **Ajout d'une nouvelle catégorie :** Crée un nouvel onglet ou une nouvelle section dans votre slider du front-office. Vous pouvez ensuite le remplir avec des produits spécifiques.
-   **Modification d'une catégorie :**
    -   La modification du **Nom de la catégorie** met à jour l'étiquette affichée aux clients dans le slider.
    -   L'activation/désactivation du **Statut Actif/Inactif** affiche ou masque immédiatement cette catégorie entière et ses produits du slider du front-office.
    -   **Ajout/Suppression de produits :** Met à jour directement les produits qui apparaissent dans cette catégorie de slider spécifique.
    -   **Réorganisation des produits :** Modifie la séquence dans laquelle les produits apparaissent dans le slider de cette catégorie.
-   **Suppression d'une catégorie :** Supprime définitivement la catégorie et tous ses produits attribués du slider. Les produits eux-mêmes ne sont pas supprimés de votre boutique.

**Flux de travail recommandé pour la gestion quotidienne de la boutique :**

1.  **Planifiez vos catégories :** Avant de créer, décidez des groupes logiques pour vos produits phares (par exemple, « Nouveautés », « En solde », « Meilleures ventes », « Sélections saisonnières »).
2.  **Créez des catégories :** Utilisez le bouton « Ajouter » pour créer chaque catégorie, en lui donnant un nom clair et descriptif.
3.  **Attribuez des produits :** Pour chaque catégorie, utilisez l'interface d'attribution de produits pour rechercher et ajouter les produits pertinents. Assurez-vous d'enregistrer vos modifications.
4.  **Commandez les produits :** Organisez les produits dans chaque catégorie dans l'ordre dans lequel vous souhaitez qu'ils apparaissent.
5.  **Vérifiez et activez :** Une fois satisfait, assurez-vous que la catégorie est définie sur « Active ».
6.  **Vérifiez le Front-Office :** Vérifiez toujours les modifications sur votre boutique en ligne pour vous assurer que le slider s'affiche et fonctionne comme prévu.
7.  **Mises à jour régulières :** Mettez à jour périodiquement vos catégories de produits phares avec de nouveaux produits, des articles saisonniers ou des articles que vous souhaitez promouvoir. Supprimez les articles plus anciens ou en rupture de stock pour garder le slider frais et pertinent.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Afficher dans le Hook | `displayHome` | Contrôle où le slider apparaît (page d'accueil, colonnes, pied de page). |
| | Nombre de produits à afficher | `4` | Combien de produits sont visibles à la fois dans le slider. |
| | Vitesse du slider (ms) | `3000` - `5000` | Vitesse des transitions automatiques des diapositives. |
| | Lecture automatique du slider | `OUI` | Le slider fait automatiquement défiler les produits. |
| | Afficher les flèches de navigation | `OUI` | Affiche les flèches pour la navigation manuelle. |
| | Afficher les points de pagination | `OUI` | Affiche les points pour l'indication des diapositives et l'accès direct. |
| | Largeur de l'image du produit (px) | `250` - `350` | Définit la largeur des images de produits dans le slider. |
| | Hauteur de l'image du produit (px) | `250` - `350` | Définit la hauteur des images de produits dans le slider. |
| | Couleur de fond | Laisser vide / Correspondant au thème | Définit la couleur de fond du bloc du slider. |
| | Couleur du texte | Correspondant au thème / `#333333` | Définit la couleur des noms de produits et des descriptions. |
| | Couleur du prix | Correspondant au thème / Couleur d'accent | Définit la couleur des prix des produits. |
| **Écran d'administration « Multi Featured Slider »** | Ajouter/Modifier le nom de la catégorie | Nom descriptif (par exemple, « Meilleures ventes ») | Crée/modifie un onglet/une section dans le slider. |
| | Statut de la catégorie (Actif/Inactif) | `Actif` | Affiche ou masque une catégorie entière de produits phares. |
| | Attribuer des produits à la catégorie | N/A | Sélectionne les produits qui apparaissent dans une catégorie de slider spécifique. |
| | Réorganiser les produits | N/A | Modifie l'ordre d'affichage des produits dans une catégorie. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Mon slider n'apparaît pas sur la page d'accueil après la configuration.**

-   **R :** Tout d'abord, vérifiez si le module est activé et configuré pour s'afficher dans le bon hook (par exemple, `displayHome`) sur la page de configuration principale du module. Deuxièmement, assurez-vous d'avoir créé au moins une catégorie « Multi Featured Slider » et de lui avoir attribué des produits, et que la catégorie est définie sur « Active » dans l'écran d'administration dédié. Enfin, videz votre cache PrestaShop (**Paramètres avancés > Performances > Vider le cache**).

**Q2 : Le slider semble cassé ou mal aligné sur ma boutique.**

-   **R :** Il s'agit souvent d'un conflit CSS avec votre thème.
    1.  **Vérifiez les dimensions de l'image :** Allez sur la page de configuration du module et vérifiez les paramètres « Largeur de l'image du produit » et « Hauteur de l'image du produit ». Assurez-vous qu'ils sont appropriés pour votre thème et le nombre de produits que vous souhaitez afficher.
    2.  **Surcharges de thème :** Votre thème peut avoir des styles conflictuels. Essayez de passer temporairement au thème PrestaShop par défaut pour voir si le problème persiste. Si cela résout le problème, le CSS de votre thème est probablement en train de surcharger les styles du module. Vous devrez peut-être faire appel à un développeur web pour créer une surcharge CSS personnalisée dans le fichier `custom.css` de votre thème.
    3.  **Videz le cache :** Videz toujours le cache de votre navigateur et le cache Smarty de PrestaShop après avoir effectué des modifications liées au design.

**Q3 : Comment puis-je modifier l'ordre des produits dans une catégorie de slider ?**

-   **R :** Allez sur l'écran d'administration dédié « Multi Featured Slider ». Modifiez la catégorie spécifique que vous souhaitez réorganiser. Dans l'interface d'attribution de produits, vous devriez pouvoir faire glisser et déposer les produits pour modifier leur ordre, ou il pourrait y avoir des flèches haut/bas à côté de chaque produit. N'oubliez pas d'enregistrer vos modifications.

**Q4 : Puis-je traduire les noms de catégories pour différentes langues ?**

-   **R :** Oui, les modules PrestaShop prennent généralement en charge la saisie multilingue pour des champs comme les noms de catégories. Lorsque vous modifiez un nom de catégorie dans l'écran d'administration « Multi Featured Slider », recherchez un sélecteur de langue (généralement une icône de drapeau) à côté du champ de saisie. Cliquez dessus pour saisir le nom pour chaque langue installée.

**Q5 : Le slider est trop rapide/lent, ou la lecture automatique ne fonctionne pas.**

-   **R :** Ajustez le paramètre « Vitesse du slider (ms) » sur la page de configuration principale du module. Un nombre plus élevé signifie une transition plus lente. Assurez-vous que « Lecture automatique du slider » est défini sur `OUI` si vous souhaitez qu'il tourne automatiquement. N'oubliez pas d'enregistrer et de vider votre cache.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé du module « Homefeatured multi slider » pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module `Homefeatured multi slider` (nom interne `multihomefeatured`) suit une architecture de module PrestaShop standard, tirant parti du modèle MVC. Il se compose principalement de :

-   Un fichier de module principal (`ajax_multihomefeatured.php`) gérant l'installation, la désinstallation et le formulaire de configuration principal (`getContent()`).
-   Un contrôleur frontal (`default.php`) pour d'éventuelles interactions AJAX ou une logique de rendu spécifique au front-office.
-   Un contrôleur d'administration (`AdminprosliderController.php`) pour gérer les « catégories de produits phares » personnalisées (appelées `opinion` dans le contexte de la base de données, mais fonctionnant comme des catégories).
-   Des templates Smarty pour le rendu de la configuration du back-office et des éléments du slider du front-office.
-   Du JavaScript pour la fonctionnalité du slider et du CSS pour le style.

Le module ne semble pas utiliser de classes `ObjectModel` personnalisées basées sur l'inventaire fourni, ce qui suggère qu'il pourrait stocker ses attributions de catégories et de produits personnalisées directement dans `ps_configuration` ou une table personnalisée gérée par le `AdminprosliderController`.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   `multihomefeatured/controllers/front/default.php`
    -   **Nom de la classe et classe parente** : `MultihomefeaturedDefaultModuleFrontController` étendant `ModuleFrontController`.
    -   **Responsabilité** : Ce contrôleur est probablement utilisé pour gérer des requêtes spécifiques du front-office, potentiellement pour des appels AJAX liés au contenu du slider, ou pour rendre une page autonome si le module en proposait une. Compte tenu de la fonction principale du module en tant que slider, il pourrait gérer le chargement de contenu dynamique ou la récupération de données de produits spécifiques pour le slider.

#### Contrôleurs d'administration Back-Office

-   `multihomefeatured/controllers/admin/adminproslider.php`
    -   **Nom de l'onglet et entité gérée** : Ce contrôleur gère les catégories « Multi Featured Slider » personnalisées et leurs produits associés. Il apparaît probablement comme un sous-onglet ou une entrée dédiée dans le menu du Back Office de PrestaShop, souvent sous « Catalogue » ou « Modules ». L'entité gérée est conceptuellement une « catégorie de produits phares », que le module appelle en interne `opinion` dans ses interactions avec la base de données.
    -   **Responsabilité** : Ce contrôleur fournit l'interface CRUD (Créer, Lire, Mettre à jour, Supprimer) pour ces catégories personnalisées. Il gère :
        -   La liste des catégories existantes.
        -   L'affichage des formulaires pour ajouter de nouvelles catégories.
        -   L'affichage des formulaires pour modifier des catégories existantes (y compris l'attribution et la réorganisation des produits).
        -   Le traitement des soumissions de formulaires pour la création/mise à jour de catégories.
        -   La gestion de la suppression des catégories.
        -   La gestion de l'association entre les catégories et les produits PrestaShop spécifiques.

### 4.3 Classes et modèles de base (`classes/`)

Basé sur l'inventaire fourni, aucune classe PHP personnalisée n'est explicitement listée dans le répertoire `classes/`. Cela suggère que :

1.  Le module pourrait être plus ancien et manipuler directement les tables de la base de données sans `ObjectModel` dédié.
2.  Le `AdminprosliderController` pourrait gérer directement les interactions avec la base de données pour son entité `opinion`.
3.  Le fichier de module principal (`ajax_multihomefeatured.php`) pourrait contenir toute la logique nécessaire pour la configuration et la gestion des données de base.

Si des données personnalisées (comme les « catégories de produits phares » et leurs attributions de produits) sont stockées, c'est soit dans `ps_configuration` (pour de simples paires clé-valeur) soit dans une table de base de données personnalisée gérée directement par le `AdminprosliderController` sans définition formelle d'`ObjectModel` dans `classes/`.

### 4.4 Actifs JavaScript (`views/js/`)

-   `multihomefeatured/js/jquery.catslider.16.js`
    -   **Portée** : Front-office.
    -   **Description** : Probablement une version d'un plugin jQuery de « category slider » ou « content slider », spécifiquement adapté ou destiné à PrestaShop 1.6.x. Il gérerait l'animation principale du slider, la navigation et la réactivité.
-   `multihomefeatured/js/jquery.catslider.js`
    -   **Portée** : Front-office.
    -   **Description** : Similaire à ce qui précède, potentiellement une version plus générique ou pour d'autres versions de PrestaShop. Ce script initialiserait le slider, gérerait les transitions, la lecture automatique et l'interaction utilisateur (clics, balayages).
-   `multihomefeatured/js/jscolor/jscolor.js`
    -   **Portée** : Back-office.
    -   **Description** : Il s'agit d'une bibliothèque JavaScript pour un sélecteur de couleurs. Elle est utilisée dans le formulaire de configuration du back-office du module pour fournir une interface conviviale de sélection des couleurs (par exemple, pour l'arrière-plan, le texte, les couleurs des prix). Elle se lie à des champs de saisie spécifiques pour afficher le sélecteur de couleurs.
-   `multihomefeatured/js/modernizr.custom.63321.js`
    -   **Portée** : Front-office.
    -   **Description** : Modernizr est une bibliothèque JavaScript qui détecte les fonctionnalités HTML5 et CSS3 dans le navigateur de l'utilisateur. Elle est souvent utilisée pour fournir des mécanismes de détection de fonctionnalités et de secours, garantissant que le slider fonctionne correctement sur différents navigateurs, en particulier les plus anciens qui pourraient manquer de certaines capacités de transition ou d'animation CSS3.
-   `multihomefeatured/js/script.js`
    -   **Portée** : Front-office et/ou Back-office.
    -   **Description** : Il s'agit probablement du fichier JavaScript personnalisé principal du module. Il contiendrait :
        -   La logique d'initialisation du plugin `jquery.catslider`, en passant les options de configuration des paramètres du module.
        -   Les écouteurs d'événements pour les flèches de navigation, les points de pagination ou les interactions personnalisées.
        -   Potentiellement des appels AJAX au contrôleur frontal `default.php` pour le chargement de contenu dynamique.
        -   Toute manipulation DOM spécifique ou amélioration de l'interface utilisateur liée au slider.
        -   Dans le back-office, il pourrait contenir des scripts pour la recherche et l'attribution de produits dans les formulaires du `AdminprosliderController`.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `multihomefeatured/css/style.css`
    -   **Portée** : Front-office.
    -   **Description** : Il s'agit de la feuille de style principale pour le slider du front-office. Elle définit l'apparence visuelle du conteneur du slider, des éléments de produit, des flèches de navigation, des points de pagination, des titres de produits, des prix et de tout autre élément affiché dans le slider.
    -   **Sélecteurs de classe CSS clés** : Les développeurs peuvent s'attendre à des classes comme `.multihomefeatured-slider`, `.slider-item`, `.product-image`, `.product-title`, `.product-price`, `.slider-nav-arrow`, `.slider-pagination`, etc., qui peuvent être surchargées dans le fichier `custom.css` d'un thème personnalisé ou via le mécanisme de surcharge de thème de PrestaShop.
-   `multihomefeatured/js/css/ui-lightness/jquery-ui-1.10.2.custom.css`
    -   **Portée** : Back-office.
    -   **Description** : Cette feuille de style fait partie de la bibliothèque jQuery UI, spécifiquement le thème « UI-lightness ». Elle est probablement utilisée dans le back-office pour styliser des éléments comme les sélecteurs de date, les boîtes de dialogue ou d'autres composants interactifs qui pourraient faire partie des formulaires du `AdminprosliderController` (par exemple, pour l'autocomplétion de la recherche de produits, si implémentée à l'aide de jQuery UI).

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :
    -   `multihomefeatured/header.tpl`
        -   **Hook** : Probablement `displayHeader` ou `actionFrontControllerSetMedia`.
        -   **Sortie** : Inclut les fichiers CSS et JavaScript spécifiques au module (`jquery.catslider.js`, `modernizr.custom.63321.js`, `style.css`, `script.js`) dans la section `<head>` du front-office, en s'assurant qu'ils sont chargés avant le rendu du slider.
    -   `multihomefeatured/home.tpl`
        -   **Hook** : Configurable (par exemple, `displayHome`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`).
        -   **Sortie** : C'est le template principal pour l'affichage du slider dans le front-office. Il contient la structure HTML de l'ensemble du slider multi-catégories, y compris les onglets pour les différentes catégories et le conteneur pour les diapositives de produits. Il itère sur les catégories et les produits configurés pour construire le slider.
    -   `multihomefeatured/homeTab.tpl`
        -   **Hook** : Rendu en interne par `home.tpl`.
        -   **Sortie** : Ce template rend probablement un seul onglet ou élément de navigation pour l'une des catégories de produits phares (par exemple, « Meilleures ventes », « Nouveautés »). Il fait partie de la navigation pour basculer entre les différents sliders de produits.
    -   `multihomefeatured/homeTabContents.tpl`
        -   **Hook** : Rendu en interne par `home.tpl`.
        -   **Sortie** : Ce template rend la liste de produits réelle pour une seule catégorie de produits phares. Il contient la boucle qui affiche les images de produits individuelles, les noms, les prix et potentiellement les boutons « Ajouter au panier », le tout enveloppé dans la structure requise par le plugin `jquery.catslider`.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module ne définit pas explicitement de classes `ObjectModel` personnalisées, mais le `AdminprosliderController` gère une entité appelée `opinion`. Cela suggère fortement que le module crée au moins une table personnalisée, probablement nommée `ps_multihomefeatured_opinion` (ou similaire, suivant la convention de préfixe `ps_` de PrestaShop) pour stocker :
        -   `id_multihomefeatured_opinion` (Clé primaire)
        -   `name` (pour le nom de la catégorie, potentiellement multilingue)
        -   `active` (booléen pour le statut de la catégorie)
        -   Autres champs liés à la configuration de la catégorie.
    -   De plus, il y aurait une table de liaison, par exemple `ps_multihomefeatured_opinion_product`, pour stocker la relation plusieurs-à-plusieurs entre ces catégories et les entrées `ps_product`, y compris un champ `position` pour l'ordonnancement.
    -   Les paramètres de configuration du module (comme la vitesse du slider, les dimensions de l'image, les couleurs) sont généralement stockés dans la table `ps_configuration` avec des clés préfixées par le nom du module (par exemple, `MULTIHOMEFEATURED_SLIDER_SPEED`).
-   **Table des hooks enregistrés** :

| Nom du Hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Injecte les fichiers CSS et JavaScript du module pour la fonctionnalité du front-office. |
| `displayHome` | Zone de contenu principale de la page d'accueil. | Rend le slider de produits multi-catégories principal sur la page d'accueil. |
| `displayLeftColumn` | Barre latérale gauche des pages du front-office. | Rend une version plus petite du slider dans la colonne de gauche. |
| `displayRightColumn` | Barre latérale droite des pages du front-office. | Rend une version plus petite du slider dans la colonne de droite. |
| `displayFooter` | Section inférieure de chaque page du front-office. | Rend le slider dans la zone du pied de page. |
| `displayProductExtraContent` (ou hook de page produit similaire) | Sur la page produit, sous les détails du produit. | Potentiellement utilisé pour afficher des produits connexes dans un slider sur les pages produits. |
| `actionFrontControllerSetMedia` | Avant qu'un contrôleur frontal ne rende sa sortie. | Un moyen plus robuste d'enregistrer des actifs (CSS/JS) pour des pages spécifiques ou globalement. |
| `actionModuleInstall` | Lors de l'installation du module. | Crée les tables de la base de données, définit les valeurs de configuration par défaut, enregistre les hooks. |
| `actionModuleUninstall` | Lors de la désinstallation du module. | Nettoie les tables de la base de données, supprime les valeurs de configuration, désenregistre les hooks. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Homefeatured multi slider », veuillez vous référer à votre compte client sur MyPresta.eu. Vous pouvez télécharger les versions les plus récentes du module depuis votre historique de commandes. Pour une assistance technique ou des questions spécifiques, veuillez contacter directement le support MyPresta.eu via votre compte client.
