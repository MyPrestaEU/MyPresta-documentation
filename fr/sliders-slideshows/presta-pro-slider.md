---
title: "Presta Pro Slider - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module Presta Pro Slider de MyPresta.eu pour PrestaShop."
sidebar:
  label: "Presta Pro Slider - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Presta Pro Slider sur MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/presta-pro-slider.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/sliders-slideshows/presta-pro-slider/)
>
> ---


# Presta Pro Slider

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur inhabituelle n'est requise.

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Presta Pro Slider)

Ceci est l'écran de configuration principal où vous gérez les paramètres généraux de votre slider et ajoutez/modifiez des diapositives individuelles.

#### Paramètres généraux du slider

-   **Ce que fait ce paramètre :** Ces paramètres contrôlent l'apparence générale et le comportement de votre slider, tels que ses dimensions, sa vitesse d'animation et son emplacement sur votre site.
-   **Effet de la modification de ce paramètre :** L'ajustement de ces valeurs aura un impact direct sur l'apparence et le fonctionnement du slider pour vos clients.

| Paramètre / Option | Ce qu'il fait | Effet de la modification | Valeur recommandée | Scénario / Exemple pour le marchand |
| --- | --- | --- | --- | --- |
| **Largeur du slider (px)** | Définit la largeur totale du slider en pixels. | *Si défini à 1000 :* Le slider aura 1000 pixels de large. *Si défini à 500 :* Le slider aura 500 pixels de large. | `100%` (pour pleine largeur) ou une valeur en pixels spécifique comme `1170` (courant pour les zones de contenu). | Vous voulez que votre slider s'étende sur toute la zone de contenu de votre page d'accueil, qui fait 1170px de large. Vous entreriez `1170`. Si vous voulez qu'il soit réactif et prenne toute la largeur disponible, utilisez `100%`. |
| **Hauteur du slider (px)** | Définit la hauteur totale du slider en pixels. | *Si défini à 400 :* Le slider aura 400 pixels de haut. *Si défini à 250 :* Le slider aura 250 pixels de haut. | `350` - `500` (selon le contenu de l'image). | Vous avez des images de bannière de haute qualité qui sont mieux affichées à une certaine hauteur. Vous définiriez cela à `450` pour vous assurer que vos images sont affichées sans être trop étirées ou écrasées. |
| **Vitesse d'animation (ms)** | Contrôle la vitesse de transition entre les diapositives, en millisecondes. | *Si défini à 500 :* Les diapositives passent rapidement (0,5 seconde). *Si défini à 2000 :* Les diapositives passent lentement (2 secondes). | `1000` (1 seconde) | Vous voulez une transition fluide et perceptible entre vos diapositives promotionnelles, mais pas si lente que les clients s'ennuient. Le régler à `1000` offre un bon équilibre. |
| **Lecture automatique** | Détermine si le slider avance automatiquement à la diapositive suivante. | *Si activé (OUI) :* Les diapositives changeront automatiquement après un délai défini. *Si désactivé (NON) :* Les diapositives ne changeront que lorsqu'un client clique sur les flèches de navigation ou les points. | `OUI` | Vous voulez que vos promotions principales défilent automatiquement sur la page d'accueil sans interaction client. |
| **Vitesse de lecture automatique (ms)** | Si la lecture automatique est activée, cela définit le délai avant l'apparition de la diapositive suivante, en millisecondes. | *Si défini à 5000 :* Chaque diapositive s'affiche pendant 5 secondes. *Si défini à 3000 :* Chaque diapositive s'affiche pendant 3 secondes. | `5000` (5 secondes) | Vous avez beaucoup de texte sur vos diapositives et vous voulez donner aux clients suffisamment de temps pour le lire avant que la diapositive suivante n'apparaisse. Le régler à `7000` (7 secondes) serait approprié. |
| **Afficher sur le hook** | Sélectionne le hook PrestaShop où le slider sera affiché. | *Si défini à `displayHeader` :* Le slider apparaît en haut de chaque page. *Si défini à `displayLeftColumn` :* Le slider apparaît dans la barre latérale gauche. | `displayHome` (si disponible, sinon `displayHeader` ou `displayTop`) | Vous voulez que le slider soit une caractéristique proéminente sur votre page d'accueil. Vous sélectionneriez `displayHome` ou `displayTop`. Si vous le voulez sur les pages produits, vous pourriez sélectionner `displayProductFooter`. |
| **Couleur de fond** | Définit la couleur de fond du conteneur du slider. | *Si défini à #FFFFFF :* Le fond sera blanc. *Si défini à #000000 :* Le fond sera noir. | `Laisser vide` (pour transparent) ou une couleur correspondant à votre thème. | Votre thème a un fond clair, et vous voulez que le slider s'intègre parfaitement. Vous définiriez cela à `#FFFFFF`. |
| **Couleur du texte** | Définit la couleur par défaut du texte dans le slider (légendes, descriptions). | *Si défini à #000000 :* Le texte sera noir. *Si défini à #FF0000 :* Le texte sera rouge. | `#333333` (gris foncé) | Vos images de slider sont lumineuses, et vous avez besoin d'un texte sombre pour assurer la lisibilité. Vous définiriez cela à `#333333`. |

#### Section de gestion des diapositives

Cette section vous permet d'ajouter, de modifier et de supprimer des diapositives individuelles qui composent votre diaporama.

-   **Bouton Ajouter une nouvelle diapositive :** Cliquez ici pour ouvrir un formulaire de création d'une toute nouvelle diapositive.
-   **Liste des diapositives existantes :** Affiche un tableau de toutes vos diapositives actuellement actives, généralement avec des options pour les modifier ou les supprimer.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### AdminprosliderController (Back Office > Modules > Presta Pro Slider > Configurer > "Ajouter une nouvelle diapositive" ou "Modifier" une diapositive existante)

Cet écran apparaît lorsque vous cliquez sur "Ajouter une nouvelle diapositive" ou sur le bouton "Modifier" à côté d'une diapositive existante dans la configuration principale. Il vous permet de définir le contenu et le comportement de chaque diapositive individuelle.

-   **Nom de l'écran et emplacement du menu :** Accessible depuis la page de configuration principale du module en cliquant sur "Ajouter une nouvelle diapositive" ou sur l'icône de modification d'une diapositive existante.
-   **Actions et paramètres disponibles :** Ce formulaire vous permet de saisir tous les détails d'une seule diapositive.

| Paramètre / Option | Ce qu'il fait | Effet de la modification | Valeur recommandée | Scénario / Exemple pour le marchand |
| --- | --- | --- | --- | --- |
| **Titre de la diapositive (Légende)** | Le titre principal ou le texte court affiché sur la diapositive. | Ce texte apparaîtra en évidence sur votre diapositive, généralement dans une police plus grande. | Gardez-le concis et percutant. | "Soldes d'été !" ou "Nouveautés" |
| **Description de la diapositive** | Texte plus long fournissant plus de détails sur le contenu de la diapositive. | Ce texte apparaîtra sous le titre, offrant plus d'informations au client. | Fournissez suffisamment de détails sans être accablant. | "Jusqu'à 50% de réduction sur tous les maillots de bain pour une durée limitée !" |
| **Image de la diapositive** | L'image de fond principale pour cette diapositive spécifique. | Cette image sera la pièce maîtresse visuelle de votre diapositive. | Image de haute qualité, pertinente et de bonne résolution. | Une jolie photo d'un mannequin portant une nouvelle robe pour une promotion de mode. |
| **URL du lien** | L'adresse web (URL) vers laquelle les clients seront dirigés lorsqu'ils cliqueront sur cette diapositive. | *Si défini :* Cliquer sur la diapositive mène le client à cette URL. *Si vide :* La diapositive ne sera pas cliquable. | Une URL valide vers un produit, une catégorie ou une page d'information. | Lien vers votre page de catégorie "Nouveautés" : `https://votreboutique.com/nouveautes` |
| **Ouvrir dans une nouvelle fenêtre** | Détermine si l'URL du lien s'ouvre dans un nouvel onglet/fenêtre du navigateur. | *Si activé (OUI) :* Le lien s'ouvre dans un nouvel onglet, gardant votre boutique ouverte dans l'onglet d'origine. *Si désactivé (NON) :* Le lien s'ouvre dans le même onglet, naviguant loin de votre page actuelle. | `OUI` (généralement recommandé pour les liens externes ou les promotions) | Vous liez à un article de blog externe ou à un profil de réseau social. Vous activeriez ceci pour garder vos clients sur votre boutique PrestaShop. |
| **Actif** | Contrôle si cette diapositive est actuellement visible dans le slider. | *Si activé (OUI) :* La diapositive fera partie du diaporama. *Si désactivé (NON) :* La diapositive sera masquée mais non supprimée, vous permettant de la réactiver plus tard. | `OUI` pour les promotions actives. | Vous avez une promotion saisonnière qui est terminée, mais vous pourriez la relancer l'année prochaine. Vous la définiriez à `NON` au lieu de la supprimer. |
| **Ordre / Position** | Définit l'ordre d'affichage de cette diapositive par rapport aux autres. | Les diapositives avec des numéros inférieurs apparaissent plus tôt dans la séquence. | `1`, `2`, `3`, etc., dans l'ordre souhaité. | Vous voulez que votre diapositive "Soldes d'été" apparaisse en premier, suivie de "Nouveautés". Vous définiriez "Soldes d'été" à `1` et "Nouveautés" à `2`. |

-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  **Planifiez vos promotions :** Décidez quels produits, catégories ou messages vous souhaitez mettre en avant.
    2.  **Préparez vos images :** Assurez-vous d'avoir des images de haute qualité qui correspondent aux dimensions du slider.
    3.  **Ajoutez de nouvelles diapositives :** Utilisez le bouton "Ajouter une nouvelle diapositive" pour créer du nouveau contenu. Remplissez tous les détails, y compris le titre, la description, l'image et le lien.
    4.  **Classez vos diapositives :** Ajustez l'"Ordre / Position" pour contrôler la séquence.
    5.  **Activez/Désactivez :** Utilisez le bouton "Actif" pour gérer la visibilité sans supprimer le contenu.
    6.  **Vérifiez sur le front-office :** Vérifiez toujours votre slider sur la boutique en ligne pour vous assurer qu'il a l'apparence et le fonctionnement attendus.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Largeur du slider (px) | `100%` ou `1170` | Définit la taille horizontale du slider. |
| | Hauteur du slider (px) | `350` - `500` | Définit la taille verticale du slider. |
| | Vitesse d'animation (ms) | `1000` | Contrôle la vitesse de transition des diapositives. |
| | Lecture automatique | `OUI` | Fait avancer automatiquement les diapositives. |
| | Vitesse de lecture automatique (ms) | `5000` | Délai entre les changements automatiques de diapositives. |
| | Afficher sur le hook | `displayHome` / `displayHeader` | Où le slider apparaît dans votre boutique. |
| | Couleur de fond | `Laisser vide` / `#FFFFFF` | Couleur de fond de la zone du slider. |
| | Couleur du texte | `#333333` | Couleur de texte par défaut pour les légendes/descriptions. |
| **Ajouter/Modifier une diapositive** | Titre de la diapositive (Légende) | Concis et percutant | Titre principal de la diapositive. |
| | Description de la diapositive | Informative | Texte détaillé pour la diapositive. |
| | Image de la diapositive | Image de haute qualité | Fond visuel de la diapositive. |
| | URL du lien | URL valide | Destination lorsque la diapositive est cliquée. |
| | Ouvrir dans une nouvelle fenêtre | `OUI` | Ouvre le lien dans un nouvel onglet du navigateur. |
| | Actif | `OUI` | Active/désactive la visibilité de la diapositive. |
| | Ordre / Position | `1, 2, 3...` | Détermine la séquence des diapositives. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mon slider n'apparaît pas sur le front office, ou il apparaît au mauvais endroit.**

-   **R :** Tout d'abord, vérifiez le paramètre "Afficher sur le hook" dans la configuration du module. Assurez-vous d'avoir sélectionné le bon hook (par exemple, `displayHeader`, `displayTop`, `displayHome`). Si votre thème a des noms de hook personnalisés ou ne prend pas explicitement en charge un hook standard à cet emplacement, le slider pourrait ne pas apparaître.
-   **R :** Vérifiez également que les diapositives individuelles sont marquées comme "Actives" dans leurs paramètres. Si aucune diapositive n'est active, rien ne s'affichera.
-   **R :** Enfin, videz votre cache PrestaShop. Allez dans **Paramètres avancés > Performances**, et cliquez sur "Vider le cache" en haut à droite. Parfois, les modifications n'apparaissent pas tant que le cache n'est pas actualisé.

**Q2 : Mes images de slider semblent floues ou étirées.**

-   **R :** Cela se produit généralement si vos images téléchargées ne correspondent pas aux paramètres "Largeur du slider" et "Hauteur du slider", ou si elles sont de faible résolution.
-   **R : Solution :** Assurez-vous que vos images sont en haute résolution et ont idéalement le même rapport d'aspect que les dimensions de votre slider configuré. Par exemple, si votre slider mesure 1200px de large et 400px de haut, essayez de télécharger des images d'au moins 1200px par 400px. Vous devrez peut-être redimensionner ou recadrer vos images avant de les télécharger.

**Q3 : Le texte de mes diapositives est difficile à lire.**

-   **R :** Il s'agit souvent d'un problème de contraste entre votre "Image de la diapositive" et la "Couleur du texte" que vous avez choisie.
-   **R : Solution :**
    1.  Ajustez la "Couleur du texte" dans la configuration principale du module à une couleur qui contraste bien avec vos images (par exemple, texte blanc sur images sombres, texte noir sur images claires).
    2.  Envisagez d'ajouter une superposition subtile à vos images (vous pourriez avoir besoin d'un éditeur graphique pour cela) pour les assombrir ou les éclaircir légèrement, afin de faire ressortir davantage le texte.
    3.  Gardez votre "Titre de la diapositive" et votre "Description de la diapositive" concis. Moins de texte est souvent plus facile à lire rapidement.

**Q4 : Comment traduire les titres et descriptions des diapositives dans différentes langues ?**

-   **R :** Lorsque vous modifiez une diapositive, vous devriez voir des onglets de sélection de langue à côté des champs "Titre de la diapositive" et "Description de la diapositive" (si votre boutique PrestaShop a plusieurs langues activées).
-   **R : Solution :** Cliquez sur l'icône du drapeau ou l'onglet de langue pour chaque langue que vous souhaitez traduire, puis saisissez le texte correspondant pour cette langue. N'oubliez pas d'enregistrer vos modifications.

**Q5 : Les animations du slider sont trop rapides/lentes, ou la lecture automatique ne fonctionne pas.**

-   **R :** Vérifiez les paramètres "Vitesse d'animation (ms)", "Lecture automatique" et "Vitesse de lecture automatique (ms)" dans la configuration principale du module.
-   **R : Solution :**
    -   Augmentez la "Vitesse d'animation" pour des transitions plus lentes, diminuez-la pour des transitions plus rapides.
    -   Assurez-vous que la "Lecture automatique" est réglée sur `OUI` si vous souhaitez que les diapositives avancent automatiquement.
    -   Ajustez la "Vitesse de lecture automatique" pour contrôler la durée d'affichage de chaque diapositive avant de passer à la suivante. N'oubliez pas que ces valeurs sont en millisecondes (1000ms = 1 seconde).

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module Presta Pro Slider suit une architecture de module PrestaShop standard, tirant parti du modèle MVC le cas échéant. Il utilise principalement un seul fichier de module principal (`ajax_proslider.php`) pour sa logique et sa configuration de base, un contrôleur administratif pour la gestion des diapositives et des modèles front-office pour le rendu du slider. Il s'appuie sur jQuery et Modernizr pour ses animations et son style front-end. Les données des diapositives sont stockées directement dans la table `ps_configuration` de PrestaShop, plutôt que dans un `ObjectModel` dédié et une table de base de données personnalisée.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    -   `controllers/front/default.php`
        -   **Nom de la classe et classe parente** : `ProsliderDefaultModuleFrontController` étendant `ModuleFrontController`.
        -   **Responsabilité** : Ce contrôleur est probablement destiné à une route par défaut ou à une action front-office spécifique, bien que son objectif exact puisse être minimal étant donné que le module s'accroche principalement aux zones de modèle existantes. Il gérerait les requêtes vers `votreboutique.com/module/proslider/default` et pourrait être utilisé pour les appels AJAX ou le rendu d'une page autonome si le module en avait une. Dans le contexte de ce module, il pourrait s'agir d'un espace réservé ou être utilisé pour une récupération de données spécifique si le contenu du slider était chargé dynamiquement.
-   **Contrôleurs d'administration Back-Office** :

    -   `controllers/admin/adminproslider.php`
        -   **Nom de la classe et classe parente** : `AdminprosliderController` étendant `ModuleAdminController`.
        -   **Nom de l'onglet et entité gérée** : Ce contrôleur gère les "diapositives" ou "opinions" (selon le dossier, bien que "opinion" semble être une faute de frappe et devrait probablement être "diapositive" ou "proslider_item" s'il s'agissait d'un ObjectModel). Il fournit l'interface pour ajouter, modifier et supprimer des diapositives individuelles. Il gère la soumission du formulaire pour les détails des diapositives (titre, description, image, lien, etc.) et met à jour la table `ps_configuration` ou une table personnalisée si elle était présente.

### 4.3 Classes et modèles de base (`classes/`)

Le dossier du module n'indique aucune classe ou modèle personnalisé dans le répertoire `classes/`. Cela suggère que le module stocke ses données directement dans la table `ps_configuration` en utilisant des tableaux sérialisés ou des clés de configuration individuelles pour chaque diapositive, ou qu'il pourrait utiliser une approche plus simple, non-ORM, au sein de l'`AdminprosliderController` pour gérer les données. S'il utilisait `ObjectModel`, il y aurait une classe définie ici (par exemple, `ProsliderSlide.php`).

### 4.4 Actifs JavaScript (`views/js/`)

-   `proslider/js/jquery.cslider.js`
    -   **Portée** : Front-office.
    -   **Description** : Il s'agit probablement du plugin jQuery principal responsable de la fonctionnalité de slider animé. Il gère les transitions de diapositives, la logique de lecture automatique, les contrôles de navigation et la réactivité. Les développeurs devraient consulter ce fichier pour comprendre les types d'animation du slider et les options disponibles.
-   `proslider/js/jscolor/jscolor.js`
    -   **Portée** : Back-office.
    -   **Description** : Une bibliothèque JavaScript pour un widget de sélecteur de couleurs. Elle est utilisée dans les formulaires de configuration du back-office du module pour permettre aux marchands de sélectionner facilement les couleurs de fond et de texte du slider.
-   `proslider/js/modernizr.custom.28468.js`
    -   **Portée** : Front-office.
    -   **Description** : Modernizr est une bibliothèque JavaScript qui détecte les fonctionnalités HTML5 et CSS3 dans le navigateur de l'utilisateur. Cette version personnalisée spécifique est probablement utilisée par `jquery.cslider.js` pour fournir une détection de fonctionnalités et potentiellement des mécanismes de secours pour les navigateurs plus anciens, garantissant des animations fluides et une compatibilité.
-   `proslider/js/script.js`
    -   **Portée** : Front-office.
    -   **Description** : Il s'agit du fichier JavaScript personnalisé principal du module. Il initialise le plugin `jquery.cslider.js` avec les paramètres spécifiques configurés dans le back office (largeur, hauteur, vitesse, lecture automatique, etc.). Il lie les écouteurs d'événements pour la navigation du slider (si des personnalisations sont implémentées) et garantit que le slider fonctionne correctement dans l'environnement PrestaShop.
-   `proslider/tinymce16.inc.js`
    -   **Portée** : Back-office.
    -   **Description** : Ce fichier est un include pour l'éditeur de texte riche TinyMCE, spécifiquement configuré pour PrestaShop 1.6.x. Il est utilisé dans les formulaires du back-office pour les champs "Description de la diapositive", permettant aux marchands de formater le texte avec du HTML. Pour PrestaShop 1.7.x et 8.x, l'intégration native de TinyMCE de PrestaShop pourrait être utilisée, ou ce fichier pourrait toujours être chargé pour la compatibilité.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `proslider/css/style2.css`
    -   **Portée** : Style client Front-office.
    -   **Description** : Il s'agit de la feuille de style principale pour le slider front-end. Elle définit l'apparence visuelle du conteneur du slider, des diapositives individuelles, des légendes, des descriptions, des flèches de navigation et des points de pagination.
    -   **Sélecteurs de classe CSS clés** : Les développeurs peuvent inspecter ce fichier pour des classes comme `.cs-slider`, `.cs-wrapper`, `.cs-bg`, `.cs-caption`, `.cs-description`, `.cs-nav`, `.cs-dots` pour remplacer ou étendre le style dans le CSS personnalisé de leur thème.
-   `proslider/js/css/ui-lightness/jquery-ui-1.10.2.custom.css`
    -   **Portée** : Style du formulaire d'administration Back-office.
    -   **Description** : Il s'agit d'une version personnalisée du framework CSS jQuery UI, spécifiquement pour le thème "UI-lightness". Il est probablement utilisé pour styliser les éléments des formulaires de configuration du back-office du module, tels que les sélecteurs de date (le cas échéant), les boutons ou d'autres widgets d'interface utilisateur qui pourraient faire partie de l'interface de gestion des diapositives.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** :

    -   `proslider/header.tpl`
        -   **Hook** : Probablement destiné à `displayHeader` ou `displayTop`.
        -   **Sortie** : Ce modèle contiendrait la structure HTML principale du slider, y compris les éléments `div` que `jquery.cslider.js` cible, et potentiellement la boucle pour rendre les diapositives individuelles en fonction des données passées par le module. Il pourrait également inclure les inclusions JS et CSS nécessaires.
    -   `proslider/top.tpl`
        -   **Hook** : Probablement destiné à `displayTop` ou `displayNav`.
        -   **Sortie** : Similaire à `header.tpl`, cela rendrait le slider dans la section supérieure de la boutique, souvent sous la navigation principale.
    -   `proslider/views/templates/hook/left-column.tpl`
        -   **Hook** : `displayLeftColumn` ou `displayRightColumn`.
        -   **Sortie** : Ce modèle rend une version potentiellement plus petite ou différemment stylisée du slider spécifiquement pour les colonnes latérales de la boutique.
-   **Modèles d'administration (`views/templates/admin/`)** :

    -   `proslider/views/templates/front/form.tpl`
        -   **Hook** : Ce chemin suggère qu'il s'agit d'un modèle front-office, mais le contexte de `AdminprosliderController` implique qu'il pourrait être utilisé pour le *formulaire* d'ajout/modification de diapositives dans l'administration. C'est un modèle courant où un module peut réutiliser un modèle de "formulaire" pour la saisie de données à la fois front-end (si applicable) et back-end.
        -   **Sortie** : Ce modèle définirait la structure du formulaire HTML pour ajouter ou modifier une seule diapositive, y compris les champs de saisie pour le titre, la description, le téléchargement d'image, l'URL, l'état actif et la position.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Le dossier du module n'indique aucun fichier SQL personnalisé. Cela suggère fortement que le module stocke sa configuration et ses données de diapositives directement dans la table `ps_configuration` de PrestaShop. Les données de chaque diapositive (titre, description, image, lien, etc.) seraient probablement sérialisées dans une seule clé de configuration, ou plusieurs clés par diapositive, par exemple, `PROSLIDER_SLIDE_1_TITLE`, `PROSLIDER_SLIDE_1_IMAGE`, etc. Cette approche est plus simple mais moins évolutive que l'utilisation d'un `ObjectModel` dédié.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Injection des actifs CSS/JS et potentiellement de la structure HTML principale du slider. |
| `displayTop` | Généralement sous la navigation principale, au-dessus du contenu. | Affichage du slider principal dans une position supérieure proéminente. |
| `displayHome` | Dans la zone de contenu de la page d'accueil. | Affichage du slider comme élément central de la page d'accueil. |
| `displayLeftColumn` | Dans la barre latérale gauche des pages qui en ont une. | Affichage d'un slider plus petit et contextuel dans la colonne de gauche. |
| `displayRightColumn` | Dans la barre latérale droite des pages qui en ont une. | Affichage d'un slider plus petit et contextuel dans la colonne de droite. |
| `displayProductFooter` | En bas des pages produits. | Affichage d'un slider lié au produit (par exemple, accessoires, articles connexes). |
| `displayFooter` | Dans la section du pied de page de chaque page. | Affichage d'un slider pour les promotions secondaires ou le contenu de la marque. |
| `actionFrontControllerSetMedia` | Avant qu'un contrôleur front-office ne rende sa sortie, après que les médias soient définis. | Enregistrement des fichiers CSS et JavaScript spécifiques au module pour les pages front-office. |
| `actionAdminControllerSetMedia` | Avant qu'un contrôleur d'administration ne rende sa sortie, après que les médias soient définis. | Enregistrement des fichiers CSS et JavaScript spécifiques au module pour les pages back-office (par exemple, pour le sélecteur de couleurs ou TinyMCE). |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à fournir une assistance et à assurer le bon fonctionnement de votre module Presta Pro Slider.
