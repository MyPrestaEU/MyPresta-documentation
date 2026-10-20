---
title: "Panier latéral coulissant - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Panier latéral coulissant par MyPresta.eu."
sidebar:
  label: "Panier latéral coulissant - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Sliding sidebar cart sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/sliding-sidebar-cart.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/sliding-sidebar-cart/)
>
> ---


# Panier latéral coulissant

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après avoir installé le module, cliquez sur « Configurer » pour accéder à ses paramètres. Cette page vous permet de contrôler exactement quelles informations sont affichées dans le panier latéral coulissant.

-   **Afficher l'image du produit**

    -   **Ce que fait ce paramètre :** Contrôle si l'image miniature de chaque produit dans le panier est affichée dans la barre latérale.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (« Oui ») :* Une petite image de chaque produit apparaîtra à côté de son nom dans la barre latérale, ce qui facilitera l'identification visuelle des articles par les clients.
        -   *Lorsqu'désactivé (« Non ») :* Seuls le nom du produit et d'autres détails textuels seront affichés, ce qui économise de l'espace mais peut rendre le panier moins attrayant visuellement.
    -   **Valeur recommandée :** « Oui »
    -   **Scénario / exemple pour le marchand :** L'activation de cette option aide les clients à confirmer rapidement qu'ils ont ajouté le bon article, particulièrement utile pour les boutiques avec de nombreux produits ou variations aux noms similaires.
-   **Afficher le nom du produit**

    -   **Ce que fait ce paramètre :** Détermine si le nom de chaque produit est visible dans le panier coulissant.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (« Oui ») :* Le nom complet de chaque produit sera affiché.
        -   *Lorsqu'désactivé (« Non ») :* Les noms des produits seront masqués. Ce n'est généralement pas recommandé car cela rend le panier difficile à comprendre.
    -   **Valeur recommandée :** « Oui »
    -   **Scénario / exemple pour le marchand :** C'est une information fondamentale. Gardez-la toujours sur « Oui » pour que les clients sachent exactement ce qu'il y a dans leur panier.
-   **Afficher les valeurs d'attribut de produit**

    -   **Ce que fait ce paramètre :** Si vos produits ont des attributs (comme la taille, la couleur, le matériau), ce paramètre contrôle si ces attributs sélectionnés sont affichés pour chaque produit dans le panier.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (« Oui ») :* Pour un produit comme « T-Shirt (Taille : M, Couleur : Bleu) », « Taille : M, Couleur : Bleu » sera affiché.
        -   *Lorsqu'désactivé (« Non ») :* Seul « T-Shirt » sera affiché, ce qui pourrait dérouter les clients quant à la variante exacte qu'ils ont ajoutée.
    -   **Valeur recommandée :** « Oui » (surtout pour les boutiques vendant des produits configurables)
    -   **Scénario / exemple pour le marchand :** Crucial pour les boutiques vendant des vêtements, des appareils électroniques avec des spécifications différentes, ou tout produit avec plusieurs options. Cela aide les clients à vérifier qu'ils ont sélectionné la bonne variante.
-   **Afficher le prix du produit**

    -   **Ce que fait ce paramètre :** Contrôle si le prix individuel de chaque produit dans le panier est affiché.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (« Oui ») :* Le prix unitaire de chaque article sera visible.
        -   *Lorsqu'désactivé (« Non ») :* Les prix individuels des produits seront masqués, bien que la valeur totale du panier sera toujours affichée.
    -   **Valeur recommandée :** « Oui »
    -   **Scénario / exemple pour le marchand :** La transparence est essentielle. L'affichage des prix individuels aide les clients à comprendre la répartition des coûts et confirme leurs sélections.
-   **Afficher le champ de saisie de la quantité**

    -   **Ce que fait ce paramètre :** Permet aux clients de modifier la quantité d'un article directement dans le panier latéral à l'aide d'un champ de saisie.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (« Oui ») :* Un champ de saisie numérique (par exemple, « 1 », « 2 », « 3 ») apparaîtra à côté de chaque produit, permettant aux clients de taper une nouvelle quantité ou d'utiliser les boutons d'incrémentation/décrémentation.
        -   *Lorsqu'désactivé (« Non ») :* Les clients ne peuvent pas modifier les quantités dans la barre latérale ; ils devraient se rendre sur la page complète du panier pour le faire.
    -   **Valeur recommandée :** « Oui »
    -   **Scénario / exemple pour le marchand :** Cela améliore considérablement la convivialité. Un client qui a accidentellement ajouté 2 articles au lieu de 1 peut le corriger instantanément sans quitter sa page actuelle, réduisant la frustration et l'abandon potentiel du panier.
-   **Afficher le bouton de suppression**

    -   **Ce que fait ce paramètre :** Ajoute un bouton (généralement un « X » ou une icône de poubelle) à côté de chaque produit, permettant aux clients de le supprimer du panier.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (« Oui ») :* Les clients peuvent facilement supprimer les articles indésirables de leur panier directement depuis la barre latérale.
        -   *Lorsqu'désactivé (« Non ») :* Les clients ne peuvent pas supprimer d'articles de la barre latérale ; ils devraient se rendre sur la page complète du panier.
    -   **Valeur recommandée :** « Oui »
    -   **Scénario / exemple pour le marchand :** Essentiel pour une expérience d'achat flexible. Si un client change d'avis sur un article, il peut le supprimer instantanément, l'empêchant d'abandonner l'ensemble du panier à cause d'un produit indésirable.
-   **Afficher les frais de port**

    -   **Ce que fait ce paramètre :** Affiche une estimation ou le coût réel des frais de port dans le résumé du panier latéral.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (« Oui ») :* Le coût estimé ou calculé des frais de port sera affiché dans le résumé du panier.
        -   *Lorsqu'désactivé (« Non ») :* Les frais de port ne seront pas affichés dans la barre latérale, seulement sur la page complète du panier ou de paiement.
    -   **Valeur recommandée :** « Oui » (si votre calcul de frais de port est précis dès le début)
    -   **Scénario / exemple pour le marchand :** La transparence sur les frais de port dès le départ peut éviter le « choc de l'autocollant » à la caisse, qui est une cause majeure d'abandon de panier. Si vos frais de port sont complexes ou dépendent fortement de l'adresse du client, vous pourriez envisager de le laisser sur « Non » pour éviter des estimations trompeuses.
-   **Afficher le sous-total (valeur totale des produits)**

    -   **Ce que fait ce paramètre :** Affiche la valeur totale de tous les produits dans le panier, *avant* l'application des frais de port, taxes ou réductions.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (« Oui ») :* La somme de tous les prix des produits sera affichée.
        -   *Lorsqu'désactivé (« Non ») :* Cette ligne de sous-total spécifique sera masquée.
    -   **Valeur recommandée :** « Oui »
    -   **Scénario / exemple pour le marchand :** Fournit une ventilation claire au client, l'aidant à comprendre le coût des articles eux-mêmes, séparément des autres frais.
-   **Afficher les taxes du sous-total**

    -   **Ce que fait ce paramètre :** Affiche le montant total des taxes appliquées aux produits dans le panier.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (« Oui ») :* Le montant total des taxes sera affiché dans le résumé du panier.
        -   *Lorsqu'désactivé (« Non ») :* Les détails des taxes ne seront pas affichés dans la barre latérale.
    -   **Valeur recommandée :** « Oui » (surtout dans les régions où la transparence fiscale est légalement requise ou attendue par les clients)
    -   **Scénario / exemple pour le marchand :** Important pour la transparence, en particulier dans les pays où la TVA ou la taxe de vente est une composante significative du prix final. Cela aide les clients à comprendre la ventilation complète des coûts avant de passer à la caisse.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Afficher l'image du produit | Oui | Affiche les miniatures des produits pour une identification visuelle. |
| Configuration du module | Afficher le nom du produit | Oui | Affiche le nom de chaque produit dans le panier. |
| Configuration du module | Afficher les valeurs d'attribut de produit | Oui | Affiche les attributs sélectionnés (taille, couleur) pour les produits configurables. |
| Configuration du module | Afficher le prix du produit | Oui | Affiche le prix individuel de chaque produit. |
| Configuration du module | Afficher le champ de saisie de la quantité | Oui | Permet aux clients de modifier les quantités de produits directement dans la barre latérale. |
| Configuration du module | Afficher le bouton de suppression | Oui | Permet aux clients de supprimer des produits du panier directement dans la barre latérale. |
| Configuration du module | Afficher les frais de port | Oui | Affiche le coût estimé/réel des frais de port dans le résumé. |
| Configuration du module | Afficher le sous-total (valeur totale des produits) | Oui | Affiche la valeur totale des produits avant les frais de port/taxes. |
| Configuration du module | Afficher les taxes du sous-total | Oui | Affiche le montant total des taxes appliquées aux produits. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : La barre latérale ne glisse pas lorsque j'ajoute un produit au panier.**
R1 :

-   **Vérifier l'état du module :** Assurez-vous que le module « Panier latéral coulissant » est installé et activé dans **Modules > Gestionnaire de modules**.
-   **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures). Parfois, d'anciens fichiers mis en cache empêchent le chargement de nouvelles fonctionnalités du module.
-   **Conflits de thème :** Votre thème peut avoir sa propre confirmation « ajouter au panier » ou un JavaScript qui entre en conflit avec ce module. Passez temporairement au thème PrestaShop par défaut (Classic) pour voir si la barre latérale fonctionne. Si c'est le cas, le problème vient du JavaScript ou du CSS de votre thème personnalisé. Vous devrez peut-être demander à un développeur d'enquêter.
-   **Erreurs JavaScript :** Ouvrez la console de développement de votre navigateur (généralement F12) et vérifiez s'il y a des erreurs JavaScript lorsque vous ajoutez un produit. Ces erreurs peuvent empêcher l'apparition de la barre latérale.

**Q2 : La barre latérale apparaît, mais le style est incorrect (mauvaises couleurs, polices ou mise en page).**
R2 :

-   **Conflits CSS de thème :** Il s'agit presque toujours d'un conflit CSS avec votre thème PrestaShop actif. Les feuilles de style de votre thème peuvent remplacer les styles du module.
-   **Solution :** Vous aurez probablement besoin d'un webmaster ou d'un développeur pour inspecter le CSS à l'aide des outils de développement du navigateur. Ils pourront identifier les styles conflictuels et ajouter du CSS personnalisé à votre thème (ou au fichier CSS personnalisé du module si disponible) pour garantir que la barre latérale s'affiche correctement.

**Q3 : Les quantités ou les prix ne se mettent pas à jour correctement lorsque je les modifie dans la barre latérale.**
R3 :

-   **Vider le cache :** Encore une fois, essayez de vider le cache de votre PrestaShop (**Paramètres avancés > Performances**).
-   **Problèmes AJAX :** Le module utilise AJAX pour mettre à jour le panier. S'il y a des erreurs côté serveur ou des conflits JavaScript empêchant les appels AJAX de se terminer, les mises à jour ne seront pas enregistrées. Vérifiez la console de développement de votre navigateur pour les erreurs réseau ou les erreurs JavaScript lorsque vous essayez de modifier les quantités.
-   **Configuration du module :** Vérifiez que « Afficher le champ de saisie de la quantité » est activé dans la configuration du module.

**Q4 : Comment traduire le texte de la barre latérale dans d'autres langues ?**
R4 :

-   **Système de traduction PrestaShop :** Allez dans **International > Traductions** dans votre Back Office.
-   **Type de traduction :** Sélectionnez « Traductions des modules installés ».
-   **Sélectionner le module :** Choisissez « Panier latéral coulissant » dans la liste déroulante des modules.
-   **Sélectionner la langue :** Choisissez la langue que vous souhaitez traduire.
-   **Traduire :** Vous verrez une liste de chaînes traduisibles du module. Saisissez vos traductions et enregistrez.

**Q5 : Puis-je changer le côté d'où la barre latérale glisse (gauche ou droite) ?**
R5 :

-   Le comportement par défaut du module est généralement de glisser depuis la droite. Modifier cela nécessiterait des modifications CSS personnalisées, car cela est contrôlé par les fichiers `sidcart.css` et `sidcart-right.css`. Un développeur pourrait ajuster les propriétés CSS (par exemple, `right: 0` à `left: 0`) et potentiellement la logique d'animation pour y parvenir.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Panier latéral coulissant » (`sidcart`) suit une architecture de module PrestaShop standard, se concentrant principalement sur les améliorations du front-office. Il exploite le système de hooks de PrestaShop pour injecter ses fonctionnalités et ses modèles dans la vitrine. La logique principale d'interaction avec le panier (ajout, mise à jour, suppression de produits) est gérée via un contrôleur frontal AJAX, garantissant une expérience utilisateur dynamique et non perturbatrice. La configuration est gérée via la méthode `getContent()` de la classe principale du module, stockant les paramètres dans `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    -   `controllers/front/ajax.php`
        -   **Nom de la classe et classe parente** : `SidcartAjaxModuleFrontController` étend `ModuleFrontController`.
        -   **Responsabilité** : Ce contrôleur est responsable de la gestion de toutes les requêtes AJAX liées au panier coulissant. Lorsqu'un utilisateur ajoute un produit, met à jour une quantité ou supprime un article de la barre latérale, le JavaScript envoie une requête à ce contrôleur. Il traite la modification du panier à l'aide de la classe `Cart` de PrestaShop et renvoie ensuite un résumé de panier mis à jour (généralement des fragments HTML ou des données JSON) au JavaScript du front-end, qui rafraîchit ensuite le contenu de la barre latérale. Cela garantit des mises à jour en temps réel sans rechargement complet de la page.
-   **Contrôleurs d'administration Back-Office** : Aucun. Toute la configuration est gérée dans la méthode `getContent()` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne définit aucune classe `ObjectModel` personnalisée ni de classes dédiées dans le répertoire `classes/`. Sa logique principale réside dans le fichier `sidcart.php` et le contrôleur frontal `ajax.php`, interagissant directement avec les classes natives `Cart` et `Product` de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

-   `sidcart/views/js/sidcart.js`
    -   **Portée** : Front-office.
    -   **Détails** : Il s'agit du fichier JavaScript principal du module.
        -   Il écoute les événements « ajouter au panier » (par exemple, les clics sur des boutons avec des classes spécifiques comme `.add-to-cart`).
        -   Il intercepte le comportement par défaut d'« ajouter au panier » et déclenche à la place la barre latérale coulissante.
        -   Il gère la communication AJAX avec `controllers/front/ajax.php` pour mettre à jour le contenu du panier.
        -   Il gère l'affichage et l'animation de la barre latérale (glissement entrant/sortant).
        -   Il lie les écouteurs d'événements pour les changements de quantité et les boutons de suppression dans la barre latérale elle-même, envoyant d'autres requêtes AJAX pour mettre à jour le panier.
        -   Il utilise probablement `jQuery` pour la manipulation du DOM et les appels AJAX, ce qui est courant dans PrestaShop 1.7.x et 8.x.
        -   Il peut également écouter `prestashop.on('updateCart', ...)` ou des événements similaires pour s'assurer que la barre latérale reflète les modifications apportées par d'autres modules ou par la fonctionnalité principale de PrestaShop.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `sidcart/views/css/sidcart-right.css`

    -   **Portée** : Style client du Front-office.
    -   **Détails** : Cette feuille de style définit l'apparence visuelle et le positionnement de la barre latérale coulissante lorsqu'elle apparaît depuis le côté droit de l'écran.
        -   Elle inclut des règles pour la largeur, l'arrière-plan, l'index z et la position `right` initiale de la barre latérale (par exemple, `right: -300px;` pour la masquer).
        -   Elle définit les propriétés de transition pour des animations de glissement fluides (par exemple, `transition: right 0.3s ease-in-out;`).
        -   Elle stylise la superposition qui apparaît derrière la barre latérale lorsqu'elle est ouverte.
        -   Elle contient des règles spécifiques pour la réactivité mobile, ajustant la largeur ou la position de la barre latérale sur les écrans plus petits.
        -   **Sélecteurs de classe CSS clés** : `.sidcart-wrapper`, `.sidcart-content`, `.sidcart-overlay`, `.sidcart-open`.
-   `sidcart/views/css/sidcart.css`

    -   **Portée** : Style client du Front-office.
    -   **Détails** : Cette feuille de style contient des règles de style générales pour les éléments *à l'intérieur* du panier coulissant, qu'il glisse de gauche ou de droite.
        -   Elle stylise les éléments de la liste de produits (`.sidcart-product-line`).
        -   Elle stylise les images de produits, les noms, les prix, les attributs, les champs de saisie de quantité et les boutons de suppression.
        -   Elle stylise les sections de résumé du panier (sous-total, frais de port, total).
        -   Elle stylise les boutons « Continuer mes achats » et « Passer à la caisse ».
        -   **Sélecteurs de classe CSS clés** : `.sidcart-product-image`, `.sidcart-product-name`, `.sidcart-product-price`, `.sidcart-qty-input`, `.sidcart-remove-button`, `.sidcart-summary`, `.sidcart-buttons`.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** :

    -   `sidcart/views/templates/hook/product-line.tpl`
        -   **Hook** : Ce modèle n'est pas directement hooké mais est rendu dynamiquement par le contrôleur AJAX (`ajax.php`) pour représenter une seule entrée de produit dans le panier coulissant.
        -   **Sortie** : Rend le HTML pour un produit, y compris son image, son nom, ses attributs, son prix, son champ de saisie de quantité et son bouton de suppression, en fonction des paramètres de configuration du module.
    -   `sidcart/views/templates/hook/sidcart.tpl`
        -   **Hook** : Ce modèle est probablement rendu par le hook `displayHeader` ou `displayNav2` (ou similaire) pour injecter la structure principale de la barre latérale coulissante dans la page. Il peut être initialement masqué puis révélé par JavaScript.
        -   **Sortie** : Contient la structure HTML principale de l'ensemble de la barre latérale coulissante, y compris le conteneur, la zone de liste de produits, le résumé du panier et les boutons d'action. Il sert d'enveloppe pour le contenu `product-line.tpl` chargé dynamiquement.
-   **Modèles d'administration (`views/templates/admin/`)** : Aucun.
-   **Modèles Front-office (`views/templates/front/`)** :

    -   `sidcart/views/templates/modal.tpl`
        -   **Hook** : Ce modèle est probablement une solution de repli ou une structure alternative pour un affichage de type modal, ou il pourrait être utilisé pour une partie spécifique de la barre latérale (par exemple, un message de confirmation). Compte tenu de la description du module, il est moins probable qu'il s'agisse du panneau coulissant principal lui-même, mais il pourrait être un composant à l'intérieur de celui-ci ou un modèle hérité.
        -   **Sortie** : Rend une structure modale ou contextuelle générique. Les développeurs doivent vérifier son utilisation réelle dans la logique `sidcart.js` ou `ajax.php`.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    Le module ne crée aucune table SQL personnalisée. Tous les paramètres de configuration sont stockés dans la table `ps_configuration` de PrestaShop à l'aide de clés comme `sc_ajaxInfo`, `sc_continueshopping`, `sc_pimage`, `sc_total`, `sc_subtotals_tax`, `sc_subtotals`, `sc_shipping`, `sc_remove`, `sc_qty_change`, `sc_price`, `sc_pname`, `sc_attributes`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Utilisé pour inclure les fichiers CSS et JavaScript du module (`sidcart.css`, `sidcart-right.css`, `sidcart.js`) et potentiellement pour injecter la structure HTML initiale et masquée de la barre latérale. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration est initialisé et que ses actifs multimédias sont définis. | Utilisé pour inclure tout CSS/JS nécessaire pour la page de configuration du module dans le Back Office. |
| `displayNav2` | Dans la barre de navigation, généralement près de l'icône du panier. | Utilisé pour injecter un petit résumé du panier (par exemple, nombre d'articles, prix total) ou pour attacher l'écouteur d'événements à l'icône de panier existante qui déclenche la barre latérale. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Panier latéral coulissant », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
