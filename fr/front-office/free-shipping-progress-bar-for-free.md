---
title: "Barre de progression de la livraison gratuite - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop « Barre de progression de la livraison gratuite » par MyPresta.eu."
sidebar:
  label: "Barre de progression de la livraison gratuite - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Free Shipping Progress Bar for free sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-shipping-progress-bar-for-free.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/free-shipping-progress-bar-for-free/)
>
> ---


# Barre de progression de la livraison gratuite

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration spéciale de serveur n'est nécessaire.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module « Barre de progression de la livraison gratuite ». Vous pouvez y accéder en naviguant vers **Modules > Gestionnaire de modules** et en cliquant sur « Configurer » à côté du nom du module.

#### Paramètres généraux

-   **Activer la barre de progression de la livraison gratuite :**

    *   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver l'ensemble de la fonctionnalité de la barre de progression pour votre boutique.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé (OUI) :* La barre de progression apparaîtra aux positions sélectionnées sur votre front office, et tous les autres paramètres du module prendront effet.
        *   *Lorsqu'il est désactivé (NON) :* La barre de progression sera complètement masquée de votre boutique, quels que soient les autres paramètres.
    *   **Valeur recommandée :** OUI (pour utiliser les fonctionnalités du module).
    *   **Scénario / exemple de marchand :** Si vous exécutez temporairement une promotion différente ou effectuez une maintenance, vous pouvez le désactiver. Sinon, gardez-le activé pour encourager les ventes.
-   **Seuil de livraison gratuite :**

    *   **Ce que fait ce paramètre :** Il définit le montant exact (dans la devise par défaut de votre boutique) qu'un client doit dépenser pour bénéficier de la livraison gratuite.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur un montant spécifique (par exemple, 50.00) :* La barre de progression calculera le montant restant en fonction de ce seuil.
        *   *Lorsqu'il est modifié :* L'objectif de livraison gratuite est mis à jour instantanément pour tous les clients.
    *   **Valeur recommandée :** Définissez-le sur le seuil de livraison gratuite réel de votre boutique. Si vous offrez la livraison gratuite au-dessus de 50 €, définissez-le sur 50.00.
    *   **Scénario / exemple de marchand :** Si votre transporteur offre la livraison gratuite pour les commandes de plus de 75 €, vous le définirez sur 75.00.
-   **Hook d'affichage :**

    *   **Ce que fait ce paramètre :** Il détermine où la barre de progression de la livraison gratuite sera affichée sur votre site web. Vous pouvez choisir parmi plusieurs emplacements courants.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur 'displayHeader' :* La barre apparaîtra dans la section supérieure de votre site web, généralement au-dessus ou en dessous de votre logo/menu.
        *   *Lorsqu'il est défini sur 'displayLeftColumn' ou 'displayRightColumn' :* La barre apparaîtra dans la colonne latérale respective de votre boutique.
        *   *Lorsqu'il est défini sur 'displayFooter' :* La barre apparaîtra en bas de votre site web.
        *   *Lorsqu'il est défini sur 'displayProductButtons' (ou un hook de page produit similaire) :* La barre apparaîtra sur les pages de produits, souvent près du bouton d'ajout au panier.
    *   **Valeur recommandée :** 'displayHeader' ou 'displayProductButtons' sont souvent les plus efficaces pour la visibilité et pour encourager une action immédiate.
    *   **Scénario / exemple de marchand :** Pour assurer une visibilité maximale, vous pouvez choisir `displayHeader`. Si vous souhaitez encourager l'ajout de plus d'articles directement depuis la page produit, `displayProductButtons` est un bon choix.
-   **Couleur de la barre de progression :**

    *   **Ce que fait ce paramètre :** Vous permet de personnaliser la couleur de la barre de progression elle-même. Cela vous aide à l'adapter à l'image de marque de votre boutique.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur une couleur spécifique (par exemple, #4CAF50 pour le vert) :* La barre s'affichera dans cette couleur.
    *   **Valeur recommandée :** Une couleur qui contraste bien avec votre arrière-plan mais qui complète la palette de couleurs de votre marque.
    *   **Scénario / exemple de marchand :** Si votre marque utilise beaucoup de bleu, vous pouvez choisir une nuance de bleu ou un orange complémentaire pour faire ressortir la barre.
-   **Couleur de fond :**

    *   **Ce que fait ce paramètre :** Vous permet de personnaliser la couleur de fond du conteneur de la barre de progression.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur une couleur spécifique (par exemple, #F0F0F0 pour le gris clair) :* L'arrière-plan derrière la progression s'affichera dans cette couleur.
    *   **Valeur recommandée :** Une couleur subtile qui offre un bon contraste avec la couleur de la barre de progression, souvent un gris clair ou blanc.
    *   **Scénario / exemple de marchand :** Pour faire ressortir la barre de progression elle-même, vous pouvez utiliser une couleur de fond claire comme le blanc ou un gris très clair.
-   **Couleur du texte :**

    *   **Ce que fait ce paramètre :** Vous permet de personnaliser la couleur du texte affiché dans ou autour de la barre de progression (par exemple, « Il vous manque X pour la livraison gratuite ! »).
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur une couleur spécifique (par exemple, #333333 pour le gris foncé) :* Le texte s'affichera dans cette couleur.
    *   **Valeur recommandée :** Une couleur facilement lisible sur la barre de progression et son arrière-plan.
    *   **Scénario / exemple de marchand :** Si votre barre de progression est verte et son arrière-plan gris clair, une couleur de texte gris foncé ou noir assurerait la lisibilité.

#### Aperçu de l'édition Pro

Cette section contient généralement des informations et des liens pour passer à la version « Pro » du module, qui offre des fonctionnalités plus avancées. Il ne s'agit pas de paramètres de configuration pour le module gratuit, mais plutôt de contenu promotionnel.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer la barre de progression de la livraison gratuite | OUI | Interrupteur principal pour la fonctionnalité du module. |
| Configuration du module | Seuil de livraison gratuite | Montant de livraison gratuite de votre boutique | Définit le montant cible pour la livraison gratuite. |
| Configuration du module | Hook d'affichage | displayHeader / displayProductButtons | Détermine où la barre apparaît dans votre boutique. |
| Configuration du module | Couleur de la barre de progression | Personnalisable (par exemple, #4CAF50) | Définit la couleur de la partie remplie de la barre de progression. |
| Configuration du module | Couleur de fond | Personnalisable (par exemple, #F0F0F0) | Définit la couleur de fond du conteneur de la barre de progression. |
| Configuration du module | Couleur du texte | Personnalisable (par exemple, #333333) | Définit la couleur du texte affiché avec la barre. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : La barre de progression n'apparaît pas sur ma boutique. Que dois-je faire ?**
R1 :

-   **Vérifier l'état du module :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que « Barre de progression de la livraison gratuite » est installé et activé.
-   **Vérifier la configuration :** Accédez à la page de configuration du module. Assurez-vous que « Activer la barre de progression de la livraison gratuite » est réglé sur OUI. Vérifiez également que le paramètre « Hook d'affichage » est correctement choisi et que votre thème rend réellement ce hook (certains thèmes personnalisés pourraient ne pas le faire).
-   **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty »). Parfois, un ancien cache empêche l'affichage du nouveau contenu du module.
-   **Compatibilité du thème :** Bien que le module soit conçu pour les thèmes PrestaShop standard (Classic, Hummingbird), les thèmes fortement personnalisés peuvent nécessiter des ajustements mineurs. Si les étapes ci-dessus ne fonctionnent pas, contactez le support MyPresta.eu.

**Q2 : La barre de progression s'affiche, mais elle ne se met pas à jour lorsque j'ajoute des articles au panier.**
R2 :

-   **Vérifier JavaScript :** Assurez-vous qu'il n'y a pas d'erreurs JavaScript sur votre site qui pourraient empêcher l'exécution du script du module. Vous pouvez vérifier la console de développement de votre navigateur (généralement F12) pour les erreurs.
-   **Panier AJAX :** Le module s'appuie sur la fonctionnalité de panier AJAX de PrestaShop. Assurez-vous que le mécanisme de mise à jour du panier de votre thème est standard et ne surcharge pas les appels AJAX de base de PrestaShop d'une manière qui empêcherait le module de détecter les changements.
-   **Conflits de modules :** Désactivez temporairement d'autres modules qui modifient le comportement du panier ou affichent des éléments dans les mêmes hooks pour vérifier les conflits.

**Q3 : Comment puis-je modifier le texte affiché dans la barre de progression (par exemple, « Il vous manque X pour la livraison gratuite ! ») ?**
R3 : La version gratuite du module utilise généralement un texte prédéfini. Pour personnaliser ce texte, vous devriez normalement modifier le fichier de template du module (`progress.tpl`). Cependant, cela nécessite des connaissances de base des templates Smarty. Pour une manière plus conviviale de personnaliser le texte, la version Pro du module inclut souvent des champs de texte dédiés dans le back office.

**Q4 : La barre de progression semble étrange ou ne correspond pas au style de mon thème.**
R4 :

-   **Couleurs de configuration du module :** Tout d'abord, utilisez les paramètres « Couleur de la barre de progression », « Couleur de fond » et « Couleur du texte » dans la configuration du module pour essayer de correspondre à votre thème.
-   **Conflits CSS :** Le CSS de votre thème pourrait remplacer les styles par défaut du module. Un webmaster peut inspecter l'élément à l'aide des outils de développement du navigateur pour identifier les règles CSS conflictuelles et ajouter du CSS personnalisé à votre thème pour les remplacer. Les fichiers CSS du module (`front.css`) peuvent être un bon point de départ pour identifier les sélecteurs à cibler.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Barre de progression de la livraison gratuite » suit une architecture de module PrestaShop standard, exploitant principalement la classe `Module` pour l'installation, la désinstallation et la configuration. Il utilise des contrôleurs frontaux pour les interactions AJAX afin de mettre à jour dynamiquement la barre de progression sans rechargement complet de la page. Le module s'intègre au système de hooks de PrestaShop pour afficher son contenu à divers emplacements du front-office et utilise des templates Smarty pour le rendu de son interface utilisateur. La configuration est stockée dans la table `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    *   `controllers/front/index.php`
        *   **Nom de la classe et classe parente :** `SmartFreeShippingFreeIndexModuleFrontController` étend `ModuleFrontController`.
        *   **Responsabilité :** Ce contrôleur sert probablement de base ou de point d'entrée pour les interactions front-office, bien que ses méthodes spécifiques puissent être minimales si `refresh.php` gère l'AJAX principal. Il pourrait être utilisé pour le chargement initial des données ou la configuration du contexte.
    *   `controllers/front/refresh.php`
        *   **Nom de la classe et classe parente :** `SmartFreeShippingFreeRefreshModuleFrontController` étend `ModuleFrontController`.
        *   **Responsabilité :** C'est le contrôleur AJAX principal. Il répond aux requêtes (probablement POST ou GET) du JavaScript du front-office pour récupérer le total actuel du panier, calculer le montant restant pour la livraison gratuite et renvoyer le HTML ou les données de la barre de progression mis à jour. Il gère la conversion de devises et garantit que la barre de progression reflète les changements du panier en temps réel.
-   **Contrôleurs d'administration Back-Office** :

    *   Aucun. Toute la configuration est gérée dans la méthode `getContent()` du fichier de module principal.

### 4.3 Classes et modèles principaux (`classes/`)

-   Aucun. Le module ne définit pas de classes `ObjectModel` personnalisées ni de classes de logique métier complexes au-delà de ce qui est contenu dans le fichier de module principal (`index.php`) et les contrôleurs frontaux.

### 4.4 Actifs JavaScript (`views/js/`)

-   `views/js/front.js`
    *   **Portée :** Front-office.
    *   **Détails :** Ce script est responsable du comportement dynamique de la barre de progression.
        *   Il lie probablement des écouteurs d'événements aux événements de mise à jour du panier (par exemple, `prestashop.on('updateCart', ...)` ou des événements personnalisés déclenchés par le panier AJAX du thème).
        *   Lorsqu'une mise à jour du panier est détectée, il effectue un appel AJAX au contrôleur frontal `refresh.php` pour obtenir l'état mis à jour de la barre de progression.
        *   Il met ensuite à jour le DOM pour refléter la nouvelle progression (par exemple, la largeur de la barre de progression, le texte du montant restant).
        *   Peut inclure une logique pour le rendu initial au chargement de la page et la gestion des différents hooks d'affichage.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `views/css/admin-config.css`

    *   **Portée :** Style du formulaire d'administration du Back-office.
    *   **Détails :** Contient des styles spécifiquement pour la page de configuration du module dans le Back-office de PrestaShop, garantissant une mise en page propre et conviviale pour les paramètres.
    *   **Sélecteurs de classe CSS clés :** Cible probablement des éléments dans le formulaire de configuration du module, tels que `.panel`, `.form-group`, `.control-label`, etc., spécifiques à la structure HTML du module.
-   `views/css/admin-pro-teaser.css`

    *   **Portée :** Style du formulaire d'administration du Back-office.
    *   **Détails :** Styles pour le contenu promotionnel lié à la version « Pro » du module, garantissant qu'il soit attrayant et distinct au sein de la page de configuration.
    *   **Sélecteurs de classe CSS clés :** Cible des éléments tels que `.pro-teaser-block`, `.pro-feature-list`, etc.
-   `views/css/front.css`

    *   **Portée :** Style client du Front-office.
    *   **Détails :** Contient le CSS principal de la barre de progression de la livraison gratuite elle-même, y compris sa mise en page, ses couleurs, ses animations et sa réactivité.
    *   **Sélecteurs de classe CSS clés :** Cible des éléments tels que `#smartfreeshippingfree-progress-bar-container`, `.progress-bar-fill`, `.progress-bar-text`, etc. Les développeurs peuvent remplacer ces classes dans le fichier `custom.css` ou `theme.css` de leur thème pour correspondre à leur conception spécifique.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates d'administration (`views/templates/admin/`)** :

    *   `views/templates/admin/configure.tpl`
        *   **Objectif :** C'est le template Smarty principal pour la page de configuration du module dans le Back Office. Il rend les champs de formulaire, les interrupteurs et les éléments d'entrée pour tous les paramètres du module. Il inclut probablement `get-pro-hero.tpl` et `get-pro.tpl` pour le contenu promotionnel.
    *   `views/templates/admin/get-pro-hero.tpl`
        *   **Objectif :** Rend une section « héros » proéminente faisant la promotion de la version Pro du module, souvent en haut de la page de configuration.
    *   `views/templates/admin/get-pro.tpl`
        *   **Objectif :** Rend une section détaillée décrivant les fonctionnalités et les avantages de la mise à niveau vers la version Pro, incluant généralement un appel à l'action.
-   **Templates de hook (`views/templates/hook/`)** :

    *   `views/templates/hook/progress.tpl`
        *   **Objectif :** C'est le template principal du front-office. Il rend la structure HTML de la barre de progression de la livraison gratuite, y compris le conteneur, la section de progression remplie et le texte dynamique (par exemple, « Il vous manque X pour la livraison gratuite ! »). Ce template est rendu par la méthode `displayHook` du fichier de module principal.
-   **Templates Front-office (`views/templates/front/`)** :

    *   Aucun. L'affichage du front-office est géré via le fichier `hook/progress.tpl`.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    *   Le module ne crée pas de tables SQL personnalisées. Tous les paramètres de configuration sont stockés dans la table standard `ps_configuration` de PrestaShop, en utilisant des clés préfixées par `SMARTFREESHIPPINGFREE_` (par exemple, `SMARTFREESHIPPINGFREE_ENABLED`, `SMARTFREESHIPPINGFREE_THRESHOLD`).
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page, ou tout en haut du `<body>`. | Utilisé pour injecter des ressources CSS/JS et potentiellement afficher la barre de progression dans l'en-tête. |
| `displayLeftColumn` | Dans la colonne de gauche du thème. | Position alternative pour afficher la barre de progression. |
| `displayRightColumn` | Dans la colonne de droite du thème. | Position alternative pour afficher la barre de progression. |
| `displayFooter` | Dans la section du pied de page du thème. | Position alternative, moins intrusive, pour afficher la barre de progression. |
| `displayProductButtons` (ou similaire) | Sur la page produit, souvent près du bouton d'ajout au panier. | Placement spécifique pour encourager l'ajout d'articles directement depuis les pages produit. |
| `actionCartSave` | Après l'enregistrement d'un panier (par exemple, article ajouté/supprimé). | Hook interne (non destiné à l'affichage) utilisé par le module pour déclencher des mises à jour AJAX pour la barre de progression. |
| `actionFrontControllerSetMedia` | Avant qu'un contrôleur frontal ne rende sa sortie, pour ajouter du CSS/JS. | Utilisé pour enregistrer `front.js` et `front.css` pour les pages du front-office. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Barre de progression de la livraison gratuite », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes techniques que vous pourriez rencontrer.
