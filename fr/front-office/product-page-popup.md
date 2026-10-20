---
title: "Popup de page produit - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Popup de page produit par MyPresta.eu."
sidebar:
  label: "Popup de page produit - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Product page popup sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-popup.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/product-page-popup/)
>
> ---


# Popup de page produit

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration spéciale du serveur n'est généralement nécessaire.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, vous serez redirigé vers la page de configuration principale du module. Ici, vous pouvez gérer tous vos pop-ups de page produit.

La page de configuration est divisée en deux sections principales :

1.  Onglet **« Ajouter un nouveau pop-up »** : Pour créer de nouvelles fenêtres pop-up.
2.  Onglet **« Liste des pop-ups »** : Pour afficher, modifier ou supprimer les pop-ups existants.

#### 2.1.1 Onglet « Ajouter un nouveau pop-up »

Cet onglet vous permet de définir une nouvelle fenêtre pop-up et ses paramètres associés.

-   **Nom du pop-up :**
    *   **Ce que fait ce paramètre :** Il s'agit d'un nom interne pour votre pop-up, visible uniquement dans votre back-office PrestaShop. Il vous aide à identifier et à gérer différents pop-ups.
    *   **Effet de la modification de ce paramètre :** La modification de ce nom n'affecte que la façon dont vous le voyez dans le back-office ; elle n'a aucun impact sur le front-office ou l'expérience client.
    *   **Valeur recommandée :** Utilisez un nom descriptif, par exemple, « Soldes d'été sur les T-shirts », « Guide des tailles pour les Jeans », « Tutoriel vidéo pour le Produit X ».
    *   **Scénario / exemple pour le marchand :** Si vous avez un pop-up pour un produit spécifique, nommez-le d'après ce produit pour le retrouver facilement plus tard.
-   **Contenu du pop-up :**
    *   **Ce que fait ce paramètre :** C'est le contenu principal qui sera affiché à l'intérieur de la fenêtre pop-up. C'est un éditeur de texte riche (TinyMCE) où vous pouvez ajouter du texte, des images, des vidéos, des liens et même du HTML personnalisé.
    *   **Effet de la modification de ce paramètre :** Cela modifie directement ce que vos clients voient lorsque le pop-up apparaît. Vous pouvez le rendre informatif, promotionnel ou interactif.
    *   **Valeur recommandée :** Restez concis et visuellement attrayant. Utilisez des titres, des puces et des images pertinentes.
    *   **Scénario / exemple pour le marchand :** Vous pourriez ajouter un code de réduction, une vidéo YouTube intégrée démontrant le produit, ou un tableau des tailles détaillé.
-   **Largeur du pop-up (px) :**
    *   **Ce que fait ce paramètre :** Définit la largeur de la fenêtre pop-up en pixels.
    *   **Effet de la modification de ce paramètre :** Une largeur plus grande rendra le pop-up plus large, pouvant potentiellement accueillir plus de contenu horizontalement. Une largeur plus petite le rendra plus étroit.
    *   **Valeur recommandée :** Commencez par `600px` et ajustez en fonction de votre contenu. Assurez-vous qu'il s'affiche correctement sur différentes tailles d'écran.
    *   **Scénario / exemple pour le marchand :** Si votre pop-up contient une image large ou un tableau, vous pourriez avoir besoin d'une largeur plus grande. Pour du texte simple, une largeur plus étroite pourrait être suffisante.
-   **Hauteur du pop-up (px) :**
    *   **Ce que fait ce paramètre :** Définit la hauteur de la fenêtre pop-up en pixels.
    *   **Effet de la modification de ce paramètre :** Une hauteur plus grande rendra le pop-up plus haut, permettant plus de contenu vertical sans défilement. Une hauteur plus petite le rendra plus court, nécessitant potentiellement un défilement si le contenu dépasse la hauteur.
    *   **Valeur recommandée :** Commencez par `400px` et ajustez en fonction de votre contenu.
    *   **Scénario / exemple pour le marchand :** Si vous avez une longue description textuelle ou une image haute, augmentez la hauteur. Si le contenu est court, une hauteur plus petite est plus propre.
-   **Couleur de fond du pop-up :**
    *   **Ce que fait ce paramètre :** Vous permet de choisir la couleur de fond de la fenêtre pop-up elle-même. Cela utilise un outil de sélection de couleurs.
    *   **Effet de la modification de ce paramètre :** Modifie l'apparence visuelle du pop-up, l'aidant à correspondre à l'image de marque de votre boutique ou à se démarquer.
    *   **Valeur recommandée :** Choisissez une couleur qui complète le design de votre boutique et assure une bonne lisibilité de votre contenu.
    *   **Scénario / exemple pour le marchand :** Utilisez la couleur principale de votre marque pour le fond, ou un blanc/gris clair neutre pour une lisibilité maximale.
-   **Couleur de la bordure du pop-up :**
    *   **Ce que fait ce paramètre :** Vous permet de choisir la couleur de la bordure autour de la fenêtre pop-up.
    *   **Effet de la modification de ce paramètre :** Ajoute un cadre visuel au pop-up, définissant ses bords.
    *   **Valeur recommandée :** Souvent, une couleur de bordure subtile qui correspond à l'esthétique de votre boutique ou une couleur contrastante pour faire ressortir le pop-up.
    *   **Scénario / exemple pour le marchand :** Une bordure gris clair pour un look épuré, ou une couleur vive si le pop-up est destiné à attirer beaucoup l'attention.
-   **Largeur de la bordure du pop-up (px) :**
    *   **Ce que fait ce paramètre :** Définit l'épaisseur de la bordure du pop-up en pixels.
    *   **Effet de la modification de ce paramètre :** Une valeur plus élevée rend la bordure plus épaisse et plus proéminente.
    *   **Valeur recommandée :** `1px` ou `2px` pour une bordure subtile.
    *   **Scénario / exemple pour le marchand :** Une bordure de `5px` pourrait être utilisée pour un message très audacieux et urgent, tandis que `1px` est plus courant pour des informations générales.
-   **Rayon de la bordure du pop-up (px) :**
    *   **Ce que fait ce paramètre :** Contrôle l'arrondi des coins du pop-up. Une valeur de `0` signifie des coins nets et carrés. Des valeurs plus élevées créent des coins plus arrondis.
    *   **Effet de la modification de ce paramètre :** Affecte l'esthétique globale du pop-up, le rendant plus doux ou plus moderne.
    *   **Valeur recommandée :** `0px` pour des coins nets, `5px` à `10px` pour des coins légèrement arrondis.
    *   **Scénario / exemple pour le marchand :** Si le design de votre boutique utilise des éléments arrondis, un rayon de bordure de `10px` permettrait au pop-up de mieux s'intégrer.
-   **Couleur de l'arrière-plan du pop-up :**
    *   **Ce que fait ce paramètre :** C'est la couleur de la couche semi-transparente qui apparaît derrière le pop-up, assombrissant le reste de la page du produit.
    *   **Effet de la modification de ce paramètre :** Modifie le contraste visuel entre le pop-up et l'arrière-plan. Un arrière-plan plus sombre fait ressortir davantage le pop-up.
    *   **Valeur recommandée :** Un noir semi-transparent (`#000000` avec une certaine transparence) est standard.
    *   **Scénario / exemple pour le marchand :** Un arrière-plan légèrement plus clair pourrait être utilisé si vous souhaitez que les informations sur le produit en arrière-plan restent quelque peu visibles.
-   **Opacité de l'arrière-plan du pop-up (0-100) :**
    *   **Ce que fait ce paramètre :** Contrôle la transparence de la couleur de l'arrière-plan. `0` est entièrement transparent (invisible), `100` est entièrement opaque (couleur unie, masque complètement l'arrière-plan).
    *   **Effet de la modification de ce paramètre :** Détermine la quantité de la page produit sous-jacente qui est visible à travers l'arrière-plan.
    *   **Valeur recommandée :** `70` à `80` est un bon équilibre, rendant le pop-up proéminent sans masquer complètement la page.
    *   **Scénario / exemple pour le marchand :** Si vous souhaitez que le client puisse encore voir légèrement l'image du produit derrière le pop-up, utilisez une opacité plus faible comme `50`.
-   **Produits pour ce pop-up :**
    *   **Ce que fait ce paramètre :** C'est la partie cruciale où vous sélectionnez les produits spécifiques qui déclencheront ce pop-up. Vous pouvez rechercher des produits par nom.
    *   **Effet de la modification de ce paramètre :** Le pop-up n'apparaîtra *que* sur les pages de produits que vous sélectionnez ici. Si aucun produit n'est sélectionné, le pop-up n'apparaîtra nulle part.
    *   **Valeur recommandée :** Sélectionnez tous les produits pertinents pour ce message spécifique.
    *   **Scénario / exemple pour le marchand :** Si vous avez créé un pop-up avec un guide des tailles pour les « T-shirts pour hommes », vous sélectionneriez tous vos produits de t-shirts pour hommes ici.

Après avoir configuré tous les paramètres, cliquez sur le bouton **« Enregistrer »** pour créer votre nouveau pop-up.

#### 2.1.2 Onglet « Liste des pop-ups »

Cet onglet affiche un tableau de tous les pop-ups que vous avez créés.

-   **Colonnes du tableau :**
    *   **ID :** Identifiant unique du pop-up.
    *   **Nom :** Le nom interne que vous avez donné au pop-up.
    *   **Produits :** Liste le nombre de produits associés à ce pop-up.
    *   **Actions :**
        *   **Modifier :** Cliquez sur l'icône en forme de crayon pour revenir à l'onglet « Ajouter un nouveau pop-up » avec tous les paramètres actuels du pop-up pré-remplis, vous permettant de les modifier.
        *   **Supprimer :** Cliquez sur l'icône de la corbeille pour supprimer définitivement le pop-up. Une invite de confirmation apparaîtra.
-   **Effet des modifications :**
    *   **Modification :** Vous permet de mettre à jour le contenu, le style ou les associations de produits pour un pop-up existant sans en créer un nouveau.
    *   **Suppression :** Supprime définitivement le pop-up de votre boutique. Il n'apparaîtra plus sur aucune page de produit.
-   **Flux de travail recommandé :** Examinez régulièrement cette liste pour vous assurer que tous vos pop-ups sont à jour et pertinents. Supprimez toute promotion ou information obsolète.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Ajouter un nouveau pop-up** | Nom du pop-up | Nom descriptif | Identification interne pour le back-office. |
| | Contenu du pop-up | HTML/Texte personnalisé | Message principal affiché au client. |
| | Largeur du pop-up (px) | 600px | Taille horizontale du pop-up. |
| | Hauteur du pop-up (px) | 400px | Taille verticale du pop-up. |
| | Couleur de fond du pop-up | Blanc / Couleur de la marque | Couleur de fond de la zone de contenu du pop-up. |
| | Couleur de la bordure du pop-up | Subtile / Couleur de la marque | Couleur du cadre autour du pop-up. |
| | Largeur de la bordure du pop-up (px) | 1px - 2px | Épaisseur de la bordure du pop-up. |
| | Rayon de la bordure du pop-up (px) | 0px - 10px | Arrondi des coins du pop-up. |
| | Couleur de l'arrière-plan du pop-up | Noir semi-transparent | Couleur de l'arrière-plan assombri. |
| | Opacité de l'arrière-plan du pop-up (0-100) | 70 - 80 | Transparence de l'arrière-plan. |
| | Produits pour ce pop-up | Sélectionner les produits pertinents | Détermine sur quelles pages de produits le pop-up apparaît. |
| **Liste des pop-ups** | Action Modifier | N/A | Modifier les paramètres d'un pop-up existant. |
| | Action Supprimer | N/A | Supprimer un pop-up définitivement. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mon pop-up n'apparaît pas sur la page du produit. Que dois-je vérifier ?**
R :

1.  **Le pop-up est-il associé au bon produit ?** Allez dans la configuration du module, modifiez votre pop-up et assurez-vous que le produit spécifique sur lequel vous testez est sélectionné dans le champ « Produits pour ce pop-up ».
2.  **Le module est-il activé ?** Dans **Modules > Gestionnaire de modules**, assurez-vous que « Popup de page produit » est installé et activé.
3.  **Videz votre cache PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). Le cache de votre navigateur pourrait également avoir besoin d'être vidé (Ctrl+F5 ou Cmd+R).
4.  **Vérifiez les erreurs JavaScript :** Ouvrez la console de développement de votre navigateur (F12) et recherchez les erreurs dans l'onglet « Console ». Si vous voyez des erreurs, cela pourrait indiquer un conflit avec un autre module ou votre thème.

**Q : Le pop-up a une apparence étrange ou ne correspond pas au style de mon thème.**
R :

1.  **Vérifiez les paramètres de style du pop-up :** Vérifiez à nouveau les paramètres « Couleur de fond du pop-up », « Couleur de la bordure du pop-up », « Largeur de la bordure du pop-up » et « Rayon de la bordure du pop-up » dans la configuration du module.
2.  **Conflits de thème :** Le CSS de votre thème pourrait annuler les styles du module. Si vous êtes à l'aise avec le CSS, vous pouvez inspecter les éléments du pop-up à l'aide des outils de développement de votre navigateur pour identifier les styles conflictuels. Pour les problèmes de style complexes, vous pourriez avoir besoin de l'aide d'un développeur web.

**Q : Puis-je avoir plusieurs pop-ups sur la même page de produit ?**
R : Non, le module est conçu pour afficher un pop-up spécifique par page de produit. Si un produit est associé à plusieurs pop-ups, un seul sera affiché (généralement le premier trouvé ou celui avec l'ID le plus bas, bien que ce comportement ne soit pas explicitement garanti et doive être évité). Il est préférable de créer un pop-up complet par produit ou groupe de produits.

**Q : Comment traduire le contenu du pop-up dans différentes langues ?**
R : Le champ « Contenu du pop-up » dans la configuration du module devrait proposer des onglets de langue si votre boutique PrestaShop a plusieurs langues activées. Il suffit de passer à l'onglet de la langue souhaitée et de saisir le contenu traduit pour cette langue.

**Q : Le contenu du pop-up est trop long et nécessite un défilement. Comment puis-je résoudre ce problème ?**
R :

1.  **Augmenter la hauteur du pop-up :** Dans la configuration du module, augmentez la valeur de « Hauteur du pop-up (px) ».
2.  **Condenser le contenu :** Essayez de rendre le contenu de votre pop-up plus concis. Utilisez des puces, des paragraphes plus courts et, si possible, des liens vers des pages externes pour des informations très détaillées.
3.  **Optimiser les images/vidéos :** Assurez-vous que tous les médias de votre pop-up sont optimisés pour le web afin d'éviter des temps de chargement excessifs et d'améliorer l'affichage.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module `Product page popup` pour PrestaShop 1.5.x et 1.6.x suit un modèle de conception monolithique simple, typique des modules PrestaShop plus anciens. Il utilise principalement la classe `Module` pour sa fonctionnalité principale, gérant l'installation, la désinstallation et la configuration. L'affichage en front-office est géré en s'accrochant à des points d'affichage standard, tandis que la configuration est gérée via la méthode `getContent()` dans le fichier principal du module. Les données sont stockées directement dans `ps_configuration` et gérées via les interactions standard de la base de données PrestaShop. Il n'y a pas de classes `ObjectModel` personnalisées ni de contrôleurs front/admin dédiés au-delà du fichier principal du module.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs front-office ou back-office dédiés dans le répertoire `controllers/`. Toute la logique front-office est gérée directement dans le fichier principal du module via des hooks, et toute la configuration back-office est gérée par la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne contient aucune classe ou modèle PHP personnalisé dans le répertoire `classes/`. Toute la gestion des données et la logique métier sont encapsulées dans le fichier principal du module `ajax_productpopup.php`.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`productpopup/js/jscolor/jscolor.js`**
    *   **Portée :** Back-office.
    *   **Description :** Il s'agit d'une bibliothèque JavaScript tierce pour fournir une fonctionnalité de sélecteur de couleurs. Elle est utilisée dans le formulaire de configuration du module pour permettre aux marchands de sélectionner facilement les couleurs pour l'arrière-plan, la bordure et l'incrustation du pop-up. Elle fonctionne généralement en s'attachant à des champs de saisie avec une classe spécifique (par exemple, `jscolor`).
-   **`productpopup/js/script.js`**
    *   **Portée :** Front-office.
    *   **Description :** Ce script contient la logique principale pour afficher le pop-up en front-office.
        *   **Écouteurs d'événements :** Il écoute probablement l'événement `DOMContentLoaded` ou similaire pour s'assurer que la page est entièrement chargée.
        *   **Manipulation du DOM :** Il est responsable de :
            *   Vérifier si l'ID du produit actuel a un pop-up associé.
            *   Créer dynamiquement la structure HTML du pop-up (incrustation, conteneur du pop-up, zone de contenu, bouton de fermeture).
            *   Injecter le contenu du pop-up (récupéré de la configuration du module).
            *   Appliquer les styles configurés (largeur, hauteur, couleurs, bordure, opacité).
            *   Afficher le pop-up avec une animation (par exemple, fondu enchaîné).
            *   Lier des événements pour fermer le pop-up (clic sur le bouton de fermeture, clic sur l'incrustation, touche Échap).
-   **`productpopup/js/tinymce16.inc.js`**
    *   **Portée :** Back-office.
    *   **Description :** Ce fichier est un script d'intégration pour l'éditeur de texte riche TinyMCE, spécifiquement adapté aux environnements PrestaShop 1.6.x. Il initialise l'éditeur TinyMCE pour la zone de texte « Contenu du pop-up » dans le formulaire de configuration du module, offrant au marchand une interface WYSIWYG pour créer un contenu HTML riche pour les pop-ups. Il configure les options de TinyMCE telles que les boutons disponibles, les plugins et les paramètres de langue.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`productpopup/css/productpopup.css`**
    *   **Portée :** Front-office.
    *   **Description :** Cette feuille de style définit l'apparence visuelle par défaut et la mise en page du pop-up de la page produit et de son incrustation.
        *   **Composants principaux de l'interface utilisateur :** Styles pour le `.productpopup-overlay` (l'arrière-plan assombri) et le `.productpopup-container` (la boîte de pop-up réelle).
        *   **Sélecteurs de classes CSS clés :**
            *   `.productpopup-overlay` : Contrôle `position`, `top`, `left`, `width`, `height`, `background-color`, `opacity`, `z-index`.
            *   `.productpopup-container` : Contrôle `position`, `top`, `left`, `transform` (pour le centrage), `background-color`, `border`, `border-radius`, `box-shadow`, `z-index`, `overflow`.
            *   `.productpopup-content` : Styles pour la zone de contenu interne, y compris `padding`, `font-size`, `line-height`.
            *   `.productpopup-close` : Styles pour le bouton de fermeture (par exemple, `position`, `top`, `right`, `font-size`, `color`, `cursor`).
        *   **Surcharge par le développeur :** Les développeurs peuvent surcharger ces styles dans le `global.css` de leur thème ou en créant une feuille de style personnalisée chargée après celle-ci, ciblant ces classes spécifiques.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** : Ce module ne définit pas explicitement de templates pour des hooks spécifiques dans ce répertoire. Le HTML du pop-up en front-office est probablement généré dynamiquement par `script.js` en fonction de la configuration.
-   **Templates d'administration (`views/templates/admin/`)** :
    *   **`productpopup/views/templates/admin/tabs-no-product.tpl`**
        *   **Description :** Ce template est probablement utilisé dans la méthode `getContent()` du module pour rendre le formulaire « Ajouter un nouveau pop-up » lorsqu'aucun pop-up spécifique n'est en cours de modification, ou peut-être une version simplifiée du formulaire. Il contient les champs de saisie pour le nom du pop-up, le contenu, les dimensions, les couleurs et l'interface de sélection des produits.
    *   **`productpopup/views/templates/admin/tabs.tpl`**
        *   **Description :** C'est le template principal de la page de configuration du back-office du module. Il rend généralement la structure des onglets (par exemple, « Ajouter un nouveau pop-up » et « Liste des pop-ups ») et inclut le contenu d'autres templates d'administration (comme `tabs-no-product.tpl`) dans ses panneaux d'onglets. Il rend également le tableau pour lister les pop-ups existants.
-   **Templates front-office (`views/templates/front/`)** :
    *   **`productpopup/views/templates/front/footer.tpl`**
        *   **Description :** Ce template est probablement utilisé pour afficher un petit conteneur HTML caché ou une variable JavaScript qui contient les données du pop-up (contenu, styles, ID de produit) pour que le `script.js` du front-office les récupère et rende le pop-up dynamiquement. Il est généralement accroché à `displayFooter` ou `displayHeader` pour s'assurer que les données sont disponibles à chaque chargement de page.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** :

    *   Ce module ne crée pas de tables SQL personnalisées. Tous les paramètres de configuration et les données des pop-ups sont stockés dans la table de configuration standard de PrestaShop : `ps_configuration`.
    *   **Clés de configuration** :
        *   `PRODUCTPOPUP_DATA` : Stocke les données sérialisées de tous les pop-ups créés, y compris leur contenu, leur style et les ID de produits associés. Cette clé contient une structure de tableau complexe.
        *   D'autres clés peuvent exister pour les paramètres globaux du module, le cas échéant, mais les données primaires se trouvent dans `PRODUCTPOPUP_DATA`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Exécuté dans la section `<head>` de chaque page. | Probablement utilisé pour inclure les fichiers CSS et JavaScript (`productpopup.css`, `script.js`) pour la fonctionnalité de pop-up en front-office. |
| `displayFooter` | Exécuté à la fin de la section `<body>` de chaque page. | Pourrait être utilisé pour afficher les données cachées pour `script.js` ou pour s'assurer que la structure HTML du pop-up est ajoutée au DOM après tout autre contenu. |
| `displayProductTab` (PrestaShop 1.6.x) / `displayProductExtraContent` (PrestaShop 1.7+) | Exécuté sur la page du produit, généralement dans les onglets du produit ou la zone de contenu supplémentaire. | Bien que la description du module implique une modale, il pourrait utiliser ce hook pour injecter un déclencheur pour le pop-up, ou pour s'assurer que son JS est chargé spécifiquement sur les pages de produits. |
| `displayRightColumn` / `displayLeftColumn` | Exécuté dans les colonnes latérales de la boutique. | Moins probable pour un pop-up de page produit, mais pourrait être utilisé pour injecter un déclencheur global ou un petit script si nécessaire. |
| `actionProductUpdate` / `actionProductAdd` / `actionProductDelete` | Exécuté lorsqu'un produit est ajouté, mis à jour ou supprimé. | Pourrait être utilisé pour mettre à jour ou nettoyer les `PRODUCTPOPUP_DATA` dans `ps_configuration` si un produit associé à un pop-up est supprimé. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, les corrections de bugs et le support développeur dédié, veuillez vous référer à votre compte client sur MyPresta.eu. Assurez-vous de télécharger la dernière version du module « Popup de page produit » compatible avec votre installation PrestaShop. Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité et l'intégration du module.
