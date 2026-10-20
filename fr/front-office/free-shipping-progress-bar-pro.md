---
title: "Barre de progression de la livraison gratuite Pro - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Barre de progression de la livraison gratuite Pro par MyPresta.eu."
sidebar:
  label: "Barre de progression de la livraison gratuite Pro - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Free Shipping Progress Bar Pro sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-shipping-progress-bar-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/free-shipping-progress-bar-pro/)
>
> ---


# Barre de progression de la livraison gratuite Pro

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises et sont habituellement activées par défaut sur la plupart des environnements d'hébergement modernes.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est la zone de configuration principale où vous définirez toutes les règles, l'apparence et le comportement de votre barre de progression de la livraison gratuite. La page est conçue pour être intuitive, vous guidant à travers les différentes sections.

#### Paramètres généraux

-   **Ce que fait ce paramètre :** Contrôle l'activation globale et le comportement de base de la barre de progression.
-   **Effet de la modification de ce paramètre :**
    *   *Activer/Désactiver le module :* Active ou désactive l'ensemble de la fonctionnalité de la barre de progression pour votre boutique.
    *   *Position d'affichage :* Détermine où la barre de progression apparaît sur votre front office (par exemple, En-tête, Pied de page, Page produit, Page panier).
    *   *Barre fixe :* Rend la barre « fixe » en haut ou en bas de l'écran lorsque l'utilisateur fait défiler, la gardant visible.
-   **Valeur recommandée :**
    *   *Activer le module :* OUI (pour activer la fonctionnalité).
    *   *Position d'affichage :* En-tête (souvent la plus efficace pour la visibilité).
    *   *Barre fixe :* OUI (pour un impact maximal).
-   **Scénario/exemple de marchand :** Vous souhaitez que la barre de progression soit toujours visible en haut de votre boutique pour rappeler constamment aux clients la livraison gratuite. Vous activeriez le module, définiriez la position d'affichage sur « En-tête » et activeriez la « Barre fixe ».

#### Seuils de livraison gratuite

-   **Ce que fait ce paramètre :** Définit le montant que les clients doivent dépenser pour bénéficier de la livraison gratuite. C'est le cœur de la fonctionnalité du module. Vous pouvez définir un seuil par défaut, puis le remplacer par des règles spécifiques pour les pays ou les groupes de clients.
-   **Effet de la modification de ce paramètre :**
    *   *Seuil par défaut :* Définit le montant de base pour tous les clients non couverts par des règles spécifiques.
    *   *Seuils spécifiques par pays :* Vous permet de définir différents montants de livraison gratuite pour les clients de pays particuliers (par exemple, plus élevé pour l'expédition internationale).
    *   *Seuils spécifiques par groupe de clients :* Adaptez les seuils pour différents groupes de clients (par exemple, plus bas pour les clients VIP, plus élevés pour les grossistes).
-   **Valeur recommandée :** Commencez par un seuil par défaut qui a du sens pour votre valeur moyenne de commande et vos frais de port. Ensuite, ajoutez des règles spécifiques si nécessaire.
-   **Scénario/exemple de marchand :** Votre livraison gratuite par défaut est de 100 €. Cependant, pour les clients au Canada, vous souhaitez qu'elle soit de 150 € en raison des frais de port plus élevés. Vous définiriez le seuil par défaut à 100 €, puis ajouteriez une règle de pays pour le Canada à 150 €. Pour votre groupe de clients « Grossistes », vous pourriez le fixer à 500 €.

#### Concepteur visuel

-   **Ce que fait ce paramètre :** Fournit une interface conviviale pour personnaliser l'apparence de votre barre de progression sans aucun codage. Vous pouvez modifier les couleurs, les polices, les styles de barre, et bien plus encore.
-   **Effet de la modification de ce paramètre :** Impacte directement l'apparence visuelle de la barre de progression sur votre front office.
    *   *Couleurs :* Ajustez les couleurs d'arrière-plan, de texte et de remplissage de la barre de progression pour correspondre à votre marque.
    *   *Polices et tailles :* Personnalisez les styles de texte pour les messages.
    *   *Style de barre :* Choisissez entre différents styles visuels pour la barre de progression elle-même (par exemple, arrondie, plate).
    *   *Animations :* Ajoutez des animations subtiles pour une expérience plus engageante.
-   **Valeur recommandée :** Expérimentez pour trouver un design visuellement attrayant, clairement visible et cohérent avec l'image de marque de votre boutique.
-   **Scénario/exemple de marchand :** Votre boutique utilise une nuance spécifique de bleu et une police propre et moderne. Vous utiliseriez le concepteur visuel pour définir l'arrière-plan de la barre de progression sur ce bleu, le texte en blanc, et choisir une police sans empattement pour correspondre à votre thème.

#### Messages dynamiques

-   **Ce que fait ce paramètre :** Vous permet de créer des messages personnalisés qui apparaissent dans la barre de progression, changeant en fonction de la progression du client vers la livraison gratuite. Vous pouvez utiliser des espaces réservés pour insérer des valeurs dynamiques comme le montant restant.
-   **Effet de la modification de ce paramètre :**
    *   *Messages pour « Pas encore qualifié » :* S'affiche lorsque le client n'a pas atteint le seuil.
    *   *Messages pour « Qualifié » :* S'affiche une fois que le client a atteint ou dépassé le seuil.
    *   *Espaces réservés :* L'utilisation de `[amount_left]`, `[total_cart]`, `[free_shipping_threshold]`, `[currency_symbol]` insérera dynamiquement ces valeurs dans vos messages.
-   **Valeur recommandée :** Gardez les messages clairs, concis et encourageants. Utilisez des espaces réservés pour les rendre dynamiques et personnels.
-   **Scénario/exemple de marchand :**
    *   *Non qualifié :* « Dépensez [amount\_left] de plus pour la livraison GRATUITE ! »
    *   *Qualifié :* « Félicitations ! Votre commande est éligible à la livraison GRATUITE ! »
    Cela communique clairement l'objectif et célèbre la réussite.

#### Tests A/B et analyses

-   **Ce que fait ce paramètre :** Vous permet d'effectuer des tests A/B sur différentes configurations de barre de progression (par exemple, différents messages, couleurs ou seuils) et de suivre leurs performances.
-   **Effet de la modification de ce paramètre :**
    *   *Active le mode de test A/B :* Vous permet de créer des variations de votre barre de progression.
    *   *Suit les conversions :* Enregistre l'impact des différentes variations sur vos taux de conversion et la valeur moyenne de commande.
-   **Valeur recommandée :** Activez cette fonctionnalité une fois que votre configuration de base est stable. Utilisez-la pour optimiser continuellement l'efficacité de votre barre de progression.
-   **Scénario/exemple de marchand :** Vous voulez tester si « Dépensez X € de plus pour la livraison GRATUITE ! » est plus performant que « Débloquez la livraison GRATUITE avec seulement X € de plus ! ». Vous configurerez deux variations et laisserez le module suivre celle qui génère le plus de ventes.

#### Paramètres avancés

-   **Ce que fait ce paramètre :** Contient des options pour des aspects plus techniques, tels que la mise en cache, la compatibilité avec des thèmes spécifiques ou du CSS/JS personnalisé.
-   **Effet de la modification de ce paramètre :** Peut avoir un impact sur les performances, l'intégration du thème ou permettre des personnalisations très spécifiques.
    *   *Paramètres de cache :* Améliore la vitesse de chargement en mettant en cache le contenu de la barre.
    *   *CSS/JS personnalisé :* Permet aux développeurs d'ajouter leurs propres styles ou scripts.
-   **Valeur recommandée :** En général, laissez ces paramètres par défaut, sauf si vous avez un besoin spécifique ou si un développeur vous le conseille.
-   **Scénario/exemple de marchand :** Votre thème personnalisé a une structure d'en-tête unique et la barre de progression ne s'aligne pas parfaitement. Un développeur pourrait utiliser le champ « CSS personnalisé » pour ajouter des règles de style spécifiques afin de corriger l'alignement.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Paramètres généraux** | Activer le module | OUI | Active/désactive l'ensemble de la fonctionnalité de la barre de progression. |
| | Position d'affichage | En-tête | Où la barre apparaît (En-tête, Pied de page, Produit, Panier, Colonnes). |
| | Barre fixe | OUI | Rend la barre fixe en haut/bas de l'écran. |
| **Seuils de livraison gratuite** | Seuil par défaut | Montant de livraison gratuite de votre boutique | Montant de base pour la livraison gratuite. |
| | Règles par pays | Selon les besoins | Remplace le défaut pour des pays spécifiques. |
| | Règles par groupe de clients | Selon les besoins | Remplace le défaut pour des groupes de clients spécifiques. |
| **Concepteur visuel** | Couleur d'arrière-plan de la barre | Dépend du thème | Modifie la couleur d'arrière-plan de la barre. |
| | Couleur de remplissage de la progression | Dépend du thème | Modifie la couleur de la section de progression remplie. |
| | Couleur du texte | Dépend du thème | Modifie la couleur des messages. |
| | Famille / Taille de police | Dépend du thème | Personnalise l'apparence du texte. |
| | Style de barre | Par défaut | Conception visuelle de la barre de progression elle-même. |
| **Messages dynamiques** | Message - Non qualifié | « Dépensez [amount\_left] de plus pour la livraison GRATUITE ! » | Message affiché lorsque l'objectif n'est pas atteint. |
| | Message - Qualifié | « Félicitations ! Votre commande est éligible à la livraison GRATUITE ! » | Message affiché lorsque l'objectif est atteint. |
| **Tests A/B et analyses** | Activer les tests A/B | NON (initialement) | Permet d'exécuter des tests sur différentes configurations de barre. |
| | Suivre les conversions | OUI (lors des tests A/B) | Enregistre les performances des différentes versions de la barre. |
| **Paramètres avancés** | Activer le cache | OUI | Améliore la vitesse de chargement de la barre. |
| | CSS personnalisé | Laisser vide | Pour les surcharges de style avancées par les développeurs. |
| | JS personnalisé | Laisser vide | Pour les ajouts de scripts avancés par les développeurs. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : La barre de progression ne s'affiche pas sur ma boutique, ou elle ne se met pas à jour.**
**R1 :**

-   **Vérifier l'état du module :** Tout d'abord, assurez-vous que le module est activé dans votre Back Office PrestaShop sous **Modules > Gestionnaire de modules**.
-   **Vérifier la position d'affichage :** Allez dans la configuration du module et vérifiez le paramètre « Position d'affichage ». Assurez-vous qu'il est défini sur un hook visible (par exemple, En-tête, Pied de page). Si vous avez choisi un hook de colonne, assurez-vous que votre thème affiche réellement cette colonne.
-   **Vider le cache :** PrestaShop met souvent en cache le contenu. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures). Videz également le cache de votre navigateur.
-   **Compatibilité du thème :** Certains thèmes très personnalisés peuvent nécessiter des ajustements mineurs. Si le problème persiste après avoir vidé le cache, contactez le support MyPresta.eu avec les détails de votre thème.

**Q2 : La barre de progression a une apparence étrange ou ne correspond pas au design de mon thème.**
**R2 :**

-   **Utiliser le concepteur visuel :** Le module comprend une section « Concepteur visuel » dans sa configuration. Utilisez-la pour ajuster les couleurs, les polices et les styles afin de mieux correspondre à votre thème.
-   **CSS personnalisé :** Si le concepteur visuel ne suffit pas, votre webmaster ou un développeur peut utiliser le champ « CSS personnalisé » dans les paramètres avancés du module pour ajouter des règles de style spécifiques qui remplacent les valeurs par défaut.
-   **Cache du thème :** Après avoir effectué des modifications de conception, videz toujours le cache de votre PrestaShop (**Paramètres avancés > Performances**) et le cache de votre navigateur.

**Q3 : Le montant de la livraison gratuite est incorrect ou ne change pas pour certains clients.**
**R3 :**

-   **Vérifier les règles de seuil :** Allez dans la section « Seuils de livraison gratuite » dans la configuration du module.
    *   Vérifiez que le « Seuil par défaut » est correct.
    *   Vérifiez si des « Seuils spécifiques par pays » ou des « Seuils spécifiques par groupe de clients » remplacent le seuil par défaut pour les clients concernés. Assurez-vous que les règles sont correctement configurées pour les pays/groupes pertinents.
-   **Devise :** Assurez-vous que votre devise par défaut et la devise utilisée pour le seuil correspondent.
-   **Calcul du panier :** Le module s'appuie sur le total du panier de PrestaShop. Assurez-vous que vos produits ont des prix corrects et que les règles fiscales sont appliquées comme prévu.

**Q4 : Comment traduire les messages dans différentes langues pour mes clients internationaux ?**
**R4 :**

-   Le module prend en charge le système de traduction natif de PrestaShop.
-   Allez dans **International > Traductions** dans votre Back Office PrestaShop.
-   Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez le module « Barre de progression de la livraison gratuite Pro ».
-   Vous pouvez ensuite traduire tous les messages dynamiques et autres textes affichés par le module dans les langues souhaitées. N'oubliez pas d'enregistrer vos modifications.

**Q5 : La barre de progression ne s'affiche pas sur les appareils mobiles, ou elle n'est pas réactive.**
**R5 :**

-   Le module est conçu pour être entièrement réactif.
-   **Vider le cache :** Comme toujours, videz le cache de PrestaShop (**Paramètres avancés > Performances**) et le cache de votre navigateur mobile.
-   **Vérifier la position d'affichage :** Assurez-vous que la position d'affichage choisie (par exemple, En-tête) est une position que votre thème affiche de manière proéminente sur mobile. Certains thèmes peuvent masquer certains éléments sur les écrans plus petits.
-   **Conflits de thème :** Très rarement, un thème mobile très personnalisé peut avoir des CSS conflictuels. Si le problème persiste, consultez le support MyPresta.eu ou votre webmaster.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de la structure technique du module Barre de progression de la livraison gratuite Pro, destinée aux développeurs, webmasters et agences techniques.

### 4.1 Aperçu de l'architecture

Le module `Barre de progression de la livraison gratuite Pro` (`smartfreeshippingpro`) suit l'architecture standard des modules PrestaShop, exploitant principalement les hooks pour l'affichage en front-office et un `ModuleFrontController` dédié pour les interactions AJAX. La configuration est gérée via la méthode `getContent()` de la classe principale du module, rendant un template Smarty pour l'interface du back-office. Il utilise la classe `Configuration` de PrestaShop pour stocker les paramètres et s'appuie sur les services PrestaShop de base pour les informations sur le panier et la devise. Le module met l'accent sur une approche de configuration visuelle avec un JS dédié pour l'interface d'administration.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    -   `smartfreeshippingpro/controllers/front/index.php`
        -   **Nom de la classe :** `SmartFreeShippingProIndexModuleFrontController` (probablement, basé sur la convention de nommage des fichiers)
        -   **Classe parente :** `ModuleFrontController`
        -   **Responsabilité :** Ce contrôleur sert probablement de base ou de point d'entrée pour les interactions front-office, bien que ses méthodes spécifiques puissent être minimales si `refresh.php` gère l'AJAX principal. Il pourrait être responsable de la configuration initiale des données ou de la logique front-office non-AJAX.
    -   `smartfreeshippingpro/controllers/front/refresh.php`
        -   **Nom de la classe :** `SmartFreeShippingProRefreshModuleFrontController`
        -   **Classe parente :** `ModuleFrontController`
        -   **Responsabilité :** C'est le point d'extrémité AJAX critique. Il répond aux requêtes (par exemple, de `front.js`) pour mettre à jour la barre de progression de la livraison gratuite. Il récupère le total actuel du panier, calcule le montant restant pour la livraison gratuite en fonction des seuils configurés (règles par défaut, par pays, par groupe), et renvoie les données de progression et les messages mis à jour, généralement au format JSON. Ce contrôleur est responsable des mises à jour en temps réel de la barre.
-   **Contrôleurs d'administration Back-Office** :

    -   Aucun fichier `AdminController` dédié n'est présent. Toute la configuration du back-office est gérée dans la méthode `getContent()` du fichier principal du module (`index.php`).

### 4.3 Classes et modèles principaux (`classes/`)

Aucune classe personnalisée étendant `ObjectModel` ou d'autres classes PrestaShop de base n'est explicitement listée dans l'inventaire fourni. Le module s'appuie probablement sur les classes `Cart`, `Context`, `Configuration`, `Currency` et `Country` intégrées à PrestaShop pour sa logique.

### 4.4 Assets JavaScript (`views/js/`)

-   `smartfreeshippingpro/views/js/admin-config.js`
    -   **Portée :** Back-office.
    -   **Description :** Gère probablement les interactions générales du formulaire de configuration, la sauvegarde des paramètres et potentiellement la validation du formulaire pour la page de configuration principale du module.
-   `smartfreeshippingpro/views/js/admin-placeholders.js`
    -   **Portée :** Back-office.
    -   **Description :** Gère l'insertion dynamique des espaces réservés (par exemple, `[amount_left]`, `[total_cart]`) dans les champs de saisie de message de la configuration d'administration, facilitant ainsi la création de messages dynamiques par les marchands.
-   `smartfreeshippingpro/views/js/admin-threshold-picker.js`
    -   **Portée :** Back-office.
    -   **Description :** Gère la logique d'ajout, de modification et de suppression des seuils de livraison gratuite spécifiques aux pays et aux groupes de clients. Cela impliquerait des éléments de formulaire dynamiques pour la sélection des pays/groupes et la saisie des montants.
-   `smartfreeshippingpro/views/js/admin-visual-designer.js`
    -   **Portée :** Back-office.
    -   **Description :** Alimente l'interface de personnalisation visuelle. Il utilise probablement JavaScript pour mettre à jour dynamiquement un aperçu de la barre de progression lorsque l'administrateur modifie les couleurs, les polices et les styles, offrant un retour visuel immédiat.
-   `smartfreeshippingpro/views/js/admin.js`
    -   **Portée :** Back-office.
    -   **Description :** Un script d'administration à usage général qui pourrait initialiser d'autres fichiers JS spécifiques à l'administration, gérer les événements d'administration globaux ou fournir des fonctions utilitaires pour l'interface du back-office.
-   `smartfreeshippingpro/views/js/front.js`
    -   **Portée :** Front-office.
    -   **Description :** C'est le script frontal principal.
        -   **Écouteurs d'événements :** Se lie à `prestashop.on('updateCart', ...)` ou à des événements similaires pour détecter les changements dans le panier (ajout, suppression, mise à jour de la quantité).
        -   **Appels AJAX :** Déclenche des requêtes AJAX vers le contrôleur frontal `refresh.php` pour obtenir des données de barre de progression mises à jour.
        -   **Manipulation du DOM :** Met à jour la largeur de la barre de progression, les messages texte et potentiellement sa visibilité en fonction de la réponse AJAX.
        -   **Animations :** Peut inclure une logique pour des transitions ou des animations fluides de la barre de progression.
        -   **Logique de la barre fixe :** Si la fonction de barre fixe est activée, ce script gérerait le positionnement CSS (`position: fixed`) et potentiellement les écouteurs d'événements de défilement pour gérer sa visibilité.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `smartfreeshippingpro/views/css/admin-config.css`
    -   **Portée :** Style du formulaire d'administration du back-office.
    -   **Description :** Styles pour la mise en page générale et les éléments de la page de configuration principale du module.
-   `smartfreeshippingpro/views/css/admin-threshold-picker.css`
    -   **Portée :** Style du formulaire d'administration du back-office.
    -   **Description :** Styles spécifiques pour les interfaces de sélection de seuil par pays et par groupe de clients.
-   `smartfreeshippingpro/views/css/admin-visual-designer.css`
    -   **Portée :** Style du formulaire d'administration du back-office.
    -   **Description :** Styles pour l'interface du concepteur visuel, y compris les sélecteurs de couleurs, les éléments d'aperçu et la mise en page.
-   `smartfreeshippingpro/views/css/admin.css`
    -   **Portée :** Style du formulaire d'administration du back-office.
    -   **Description :** Styles d'administration généraux, incluant potentiellement des éléments communs utilisés dans différentes sections d'administration du module.
-   `smartfreeshippingpro/views/css/front.css`
    -   **Portée :** Style client du front-office.
    -   **Description :**
        -   Composants d'interface utilisateur principaux : Style le conteneur de la barre de progression, le remplissage de la progression et les messages texte.
        -   Sélecteurs de classes CSS clés : Inclut probablement des classes comme `.smartfreeshippingpro-bar`, `.smartfreeshippingpro-progress`, `.smartfreeshippingpro-message`, `.smartfreeshippingpro-sticky`. Les développeurs peuvent les remplacer dans le `custom.css` de leur thème ou en ajoutant du CSS personnalisé dans les paramètres avancés du module.
        -   Règles de conception réactive pour différentes tailles d'écran.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates d'administration (`views/templates/admin/`)** :

    -   `smartfreeshippingpro/views/templates/admin/configure.tpl`
        -   **Description :** Le template principal pour la page de configuration du module dans le Back Office. Il rend l'ensemble du formulaire, y compris les paramètres généraux, les liens vers d'autres sous-templates pour des sections spécifiques (comme le concepteur visuel, le sélecteur de seuil).
    -   `smartfreeshippingpro/views/templates/admin/country-priority.tpl`
        -   **Description :** Probablement un sous-template utilisé dans `configure.tpl` pour gérer la priorité des règles spécifiques aux pays si plusieurs règles pouvaient s'appliquer (par exemple, un client est dans un pays avec une règle spécifique, mais fait également partie d'un groupe avec une autre règle).
    -   `smartfreeshippingpro/views/templates/admin/country-rules-picker.tpl`
        -   **Description :** Un sous-template pour l'interface où les administrateurs définissent et gèrent les seuils de livraison gratuite basés sur les pays des clients.
    -   `smartfreeshippingpro/views/templates/admin/group-rules-picker.tpl`
        -   **Description :** Un sous-template pour l'interface où les administrateurs définissent et gèrent les seuils de livraison gratuite basés sur les groupes de clients.
    -   `smartfreeshippingpro/views/templates/admin/visual-designer.tpl`
        -   **Description :** Un sous-template pour l'interface du concepteur visuel, contenant la structure HTML pour la barre de prévisualisation et les champs de saisie (sélecteurs de couleurs, curseurs, champs de texte) pour la personnalisation.
-   **Templates de hook (`views/templates/hook/`)** :

    -   `smartfreeshippingpro/views/templates/hook/progress.tpl`
        -   **Description :** C'est le template principal du front-office. Il contient la structure HTML de la barre de progression de la livraison gratuite elle-même (par exemple, une `div` pour la barre, une `div` pour le remplissage de la progression et un `span` pour le message dynamique).
        -   **Rendu dans les hooks :** Ce template est rendu dans divers hooks du front-office tels que `displayHeader`, `displayFooter`, `displayProductButtons`, `displayShoppingCart`, `displayLeftColumn`, `displayRightColumn`, selon la configuration du marchand.
        -   **Sortie du bloc visuel :** Affiche la barre de progression complète et stylisée avec son message dynamique.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module ne semble pas créer de tables SQL personnalisées d'après l'inventaire.
    -   Les enregistrements de configuration sont stockés dans la table `ps_configuration` de PrestaShop. Les clés suivraient généralement un modèle comme `SMARTFREESHIPPINGPRO_ENABLED`, `SMARTFREESHIPPINGPRO_THRESHOLD_DEFAULT`, `SMARTFREESHIPPINGPRO_COLOR_BAR`, `SMARTFREESHIPPINGPRO_MESSAGE_NOT_QUALIFIED`, etc.
    -   Les règles spécifiques aux pays et aux groupes pourraient être stockées sous forme de tableaux sérialisés dans une seule entrée `ps_configuration` ou potentiellement dans une simple table personnalisée si la structure est complexe, bien que l'inventaire suggère que `ObjectModel` n'est pas utilisé.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rendu dans la section `<head>` ou tout en haut du `<body>`. | Injecte les assets CSS/JS et/ou le HTML de la barre de progression (surtout pour les barres fixes). |
| `displayFooter` | Rendu en bas du `<body>` avant la balise de fermeture. | Injecte les assets CSS/JS et/ou le HTML de la barre de progression. |
| `displayLeftColumn` | Rend le contenu dans la barre latérale gauche de la boutique. | Affiche la barre de progression dans la colonne de gauche. |
| `displayRightColumn` | Rend le contenu dans la barre latérale droite de la boutique. | Affiche la barre de progression dans la colonne de droite. |
| `displayProductButtons` | Rendu près du bouton « Ajouter au panier » sur les pages produits. | Affiche la barre de progression directement sur les pages produits. |
| `displayShoppingCart` | Rendu sur la page de résumé du panier. | Affiche la barre de progression sur la page du panier pour encourager plus d'achats. |
| `actionFrontControllerSetMedia` | Exécuté lorsqu'un contrôleur frontal définit ses médias (CSS/JS). | Injecte les fichiers CSS et JavaScript spécifiques au front-office. |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses médias (CSS/JS). | Injecte les fichiers CSS et JavaScript spécifiques au back-office pour la page de configuration. |
| `actionCartSave` | Exécuté après la sauvegarde d'un panier (par exemple, article ajouté/supprimé). | Déclenche le JS du front-office pour rafraîchir la barre de progression via AJAX. |
| `actionObjectCartUpdateAfter` | Exécuté après la mise à jour d'un objet panier. | Similaire à `actionCartSave`, utilisé pour déclencher des mises à jour. |
| `actionObjectOrderAddAfter` | Exécuté après l'ajout d'une nouvelle commande. | Potentiellement utilisé pour l'analyse des tests A/B afin de suivre les conversions. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour votre module Barre de progression de la livraison gratuite Pro, veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe est dédiée à assurer le bon fonctionnement et l'efficacité de votre module.

-   **Accéder aux mises à jour :** Connectez-vous à votre compte MyPresta.eu et naviguez vers votre historique de commandes et la section des téléchargements pour obtenir la version la plus récente du module.
-   **Support technique :** Si vous rencontrez des problèmes, avez des questions ou avez besoin d'aide pour la configuration, veuillez ouvrir un ticket de support via votre compte client MyPresta.eu. Notre équipe d'experts se fera un plaisir de vous aider.
