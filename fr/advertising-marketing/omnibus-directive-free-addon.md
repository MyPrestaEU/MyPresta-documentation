---
title: "Directive Omnibus - Addon Gratuit - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Directive Omnibus - Addon Gratuit par MyPresta.eu."
sidebar:
  label: "Directive Omnibus - Addon Gratuit - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Omnibus Directive - Free Addon sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/omnibus-directive-free-addon.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/omnibus-directive-free-addon/)
>
> ---


# Directive Omnibus - Addon Gratuit

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5 (Le module est conçu pour être compatible avec une large gamme de versions PHP, jusqu'aux dernières versions stables prises en charge par PrestaShop 9.x)
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises par PrestaShop lui-même et sont suffisantes pour ce module. Aucune configuration spéciale de serveur n'est nécessaire.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Pour accéder à la configuration du module, naviguez vers **Modules > Gestionnaire de modules**, recherchez « Directive Omnibus - Addon Gratuit », et cliquez sur le bouton « Configurer ».

#### Paramètres généraux

-   **Activer la conformité à la Directive Omnibus :**

    -   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité principale du module.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé (OUI) :* Le module commencera à suivre les prix des produits et affichera le prix le plus bas des 30 derniers jours sur les pages produits lorsqu'une réduction est active.
        -   *Lorsqu'il est désactivé (NON) :* Le module cessera de suivre les prix et n'affichera aucune information liée à la Directive Omnibus sur votre boutique.
    -   **Valeur recommandée :** OUI (sauf si vous ne vendez pas à des clients de l'UE ou si vous le désactivez temporairement pour maintenance).
    -   **Scénario / exemple de marchand :** Vous venez d'installer le module et souhaitez vous assurer que votre boutique est conforme. Vous le réglerez sur OUI. Si vous testez un nouveau thème et souhaitez masquer temporairement l'affichage, vous pouvez le régler sur NON.
-   **Afficher le texte du prix le plus bas :**

    -   **Ce que fait ce paramètre :** Cela vous permet de personnaliser le texte qui apparaît avant le prix le plus bas des 30 derniers jours.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est modifié :* Le texte affiché aux clients reflétera votre message personnalisé.
        -   *Lorsqu'il est laissé par défaut :* Le texte par défaut (par exemple, « Prix le plus bas des 30 derniers jours : ») sera utilisé.
    -   **Valeur recommandée :** « Prix le plus bas des 30 derniers jours : » ou similaire, assurant la clarté pour vos clients.
    -   **Scénario / exemple de marchand :** Vous pourriez vouloir utiliser une formulation légèrement différente comme « Notre prix le plus bas récemment était : » pour correspondre au ton de votre marque.
-   **Afficher sur la page produit (Sélection du hook) :**

    -   **Ce que fait ce paramètre :** Ce paramètre crucial détermine *où* sur votre page produit les informations sur le prix le plus bas des 30 derniers jours seront affichées. Le module propose des options prédéfinies pour les structures de thème courantes (Classic, Hummingbird) et une option de hook personnalisé.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque le « Profil de thème Classic » est sélectionné :* Le module tentera d'injecter l'historique des prix dans un emplacement approprié au sein de la structure standard du thème Classic (par exemple, `displayProductPriceBlock` ou `displayProductButtons`).
        -   *Lorsque le « Profil de thème Hummingbird » est sélectionné :* Le module tentera d'injecter l'historique des prix dans un emplacement approprié au sein de la structure standard du thème Hummingbird.
        -   *Lorsque le « Hook personnalisé » est sélectionné :* Vous devrez spécifier manuellement un hook PrestaShop où le module doit afficher son contenu. Cela nécessite des connaissances techniques ou une modification du thème.
    -   **Valeur recommandée :** Commencez par le « Profil de thème Classic » ou le « Profil de thème Hummingbird » selon votre thème actif. Si l'affichage n'est pas satisfaisant, consultez un webmaster pour l'intégration du « Hook personnalisé ».
    -   **Scénario / exemple de marchand :** Si votre boutique utilise le thème PrestaShop Classic par défaut, choisissez « Profil de thème Classic ». Si vous avez mis à niveau vers PrestaShop 8.x et utilisez le thème Hummingbird, sélectionnez « Profil de thème Hummingbird ». Si vous avez un thème fortement personnalisé, vous devrez peut-être utiliser le « Hook personnalisé » et demander à votre développeur d'ajouter `{hook h='displayMyCustomOmnibusHook'}` à votre modèle de page produit.
-   **Nom du hook personnalisé (si « Hook personnalisé » est sélectionné ci-dessus) :**

    -   **Ce que fait ce paramètre :** Si vous avez choisi « Hook personnalisé » dans le paramètre précédent, ce champ vous permet de spécifier le nom exact du hook où le module doit rendre son contenu.
    -   **Effet de la modification de ce paramètre :** Le module n'affichera son contenu que si un hook avec ce nom exact est présent dans le modèle de page produit de votre thème.
    -   **Valeur recommandée :** Laissez vide sauf si vous avez sélectionné « Hook personnalisé » ci-dessus et connaissez le nom exact du hook. Exemple : `displayProductExtraContent`.
    -   **Scénario / exemple de marchand :** Votre webmaster a modifié votre modèle de page produit (`product.tpl`) pour inclure `{hook h='displayMyCustomOmnibusHook'}`. Vous devrez alors saisir `displayMyCustomOmnibusHook` dans ce champ.

#### Gestion des données

-   **Effacer les données Omnibus :**
    -   **Ce que fait ce paramètre :** Ce bouton vous permet de supprimer toutes les données d'historique des prix précédemment enregistrées par le module.
    -   **Effet de la modification de ce paramètre :** Cliquer sur ce bouton supprimera définitivement tous les enregistrements de prix historiques. Le module commencera alors à collecter de nouvelles données à partir du moment où les produits sont consultés ou mis à jour.
    -   **Valeur recommandée :** À utiliser avec prudence. Ne supprimez les données que si vous avez besoin de réinitialiser l'historique des prix, par exemple, après une refonte majeure du catalogue de produits ou si vous suspectez une corruption des données.
    -   **Scénario / exemple de marchand :** Vous avez importé un ensemble de produits entièrement nouveau avec des stratégies de prix différentes, et vous voulez vous assurer que les données Omnibus commencent à zéro sans aucun prix hérité. Vous cliquerez sur ce bouton.

#### 2.1.1 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer la conformité à la Directive Omnibus | OUI | Active/désactive le suivi et l'affichage des prix pour la conformité UE. |
| Configuration du module | Afficher le texte du prix le plus bas | « Prix le plus bas des 30 derniers jours : » | Personnalise le texte affiché avant le prix historique. |
| Configuration du module | Afficher sur la page produit (Sélection du hook) | Profil Classic/Hummingbird (selon le thème) | Détermine où l'historique des prix apparaît sur la page produit. |
| Configuration du module | Nom du hook personnalisé | (Vide) | Spécifie un hook personnalisé pour l'affichage si « Hook personnalisé » est sélectionné. |
| Configuration du module | Effacer les données Omnibus | (Bouton) | Supprime tout l'historique des prix stocké, forçant un nouveau départ. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : L'information sur le prix le plus bas n'apparaît pas sur mes pages produits.**
R :

1.  **Vérifiez « Activer la conformité à la Directive Omnibus » :** Assurez-vous qu'il est réglé sur OUI dans la configuration du module.
2.  **Vérifiez « Afficher sur la page produit (Sélection du hook) » :** Essayez de basculer entre « Profil de thème Classic » et « Profil de thème Hummingbird » si vous n'êtes pas sûr de celui qui correspond le mieux à votre thème.
3.  **Videz le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). Parfois, les modifications de thème ou les mises à jour de modules nécessitent un rafraîchissement du cache.
4.  **Vérifiez les réductions :** L'information n'apparaît que lorsqu'un produit est réellement en promotion. Assurez-vous que le produit que vous testez a un prix spécifique actif ou une règle de prix catalogue appliquée.
5.  **Thème personnalisé :** Si vous utilisez un thème fortement personnalisé, le module pourrait ne pas être en mesure d'injecter automatiquement le contenu. Vous devrez probablement utiliser l'option « Hook personnalisé » et demander à votre webmaster de l'intégrer dans le fichier `product.tpl` de votre thème.

**Q : Le prix le plus bas affiché semble incorrect ou trop élevé/bas.**
R :

1.  **Temps de collecte des données :** Le module a besoin de temps pour collecter des données. Si vous venez de l'installer, il ne commencera à suivre les prix qu'à partir de ce moment. Il faudra 30 jours pour avoir un historique complet de 30 jours.
2.  **Effacer les données Omnibus :** Si vous suspectez que d'anciennes données incorrectes sont utilisées, vous pouvez cliquer sur le bouton « Effacer les données Omnibus » dans la configuration du module. Sachez que cela supprimera tout l'historique, et le module commencera à collecter des données à partir de zéro.
3.  **Combinaisons de produits/Devises :** Assurez-vous que vous regardez la bonne combinaison et la bonne devise. Le module suit les prix par combinaison et par devise.

**Q : Ce module va-t-il ralentir ma boutique ?**
R : Le module est conçu pour être léger. Le suivi des prix se fait en arrière-plan ou lors des consultations de produits, et l'affichage sur le front office est une simple sortie de texte. Tout impact sur les performances devrait être négligeable.

**Q : Comment ce module gère-t-il les boutiques multilingues ?**
R : Le paramètre « Afficher le texte du prix le plus bas » est traduisible. Vous pouvez aller dans **International > Traductions**, sélectionner « Traductions des modules installés », choisir votre thème, puis sélectionner le module « Directive Omnibus - Addon Gratuit » pour traduire le texte dans toutes vos langues actives.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Directive Omnibus - Addon Gratuit » suit une architecture de module PrestaShop standard. Sa fonctionnalité principale réside dans le fichier `index.php` principal, qui agit comme point d'entrée du module et gère l'installation, la désinstallation, la configuration et l'enregistrement des hooks. L'historique des prix est géré en observant les changements de prix des produits et en les stockant, probablement dans une table personnalisée ou `ps_configuration` (bien que le dossier indique aucune SQL personnalisée, ce qui implique `ps_configuration` ou une génération dynamique de données). L'affichage en front-office est réalisé en se connectant aux points d'affichage PrestaShop standard, avec une logique spécifique pour les thèmes Classic et Hummingbird.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Aucun explicitement défini dans le dossier. La logique front-office est probablement gérée directement dans les méthodes de hook du fichier de module principal.
-   **Contrôleurs Admin Back-Office** : Aucun explicitement défini dans le dossier. Toute la configuration back-office est gérée via la méthode `getContent()` de la classe de module principale.

### 4.3 Classes et modèles de base (`classes/`)

-   Aucun explicitement défini dans le dossier. La logique du module, y compris le suivi et le stockage des prix, est probablement encapsulée dans la classe `Omnifree` dans `index.php`.
    -   **Classe `Omnifree` (dans `omnifree/index.php`)** :
        -   Étend `Module`.
        -   Gère l'installation (`install()`) et la désinstallation (`uninstall()`) du module.
        -   Enregistre les hooks nécessaires (par exemple, `displayHeader`, `displayProductPriceBlock`, `displayProductButtons`, `displayFooter`, `actionProductUpdate`, `actionProductSave`).
        -   Gère les paramètres de configuration via `getContent()`.
        -   Contient des méthodes pour le suivi et la récupération des prix, interagissant probablement avec `ps_configuration` pour stocker les prix historiques ou les calculer dynamiquement en fonction de l'historique des commandes.
        -   Implémente des méthodes de hook (`hookDisplayHeader`, `hookDisplayProductPriceBlock`, `hookDisplayProductButtons`, `hookDisplayFooter`, etc.) pour injecter du contenu dans le front office.
        -   Implémente des hooks d'action (`hookActionProductUpdate`, `hookActionProductSave`) pour enregistrer les changements de prix.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`omnifree/views/js/admin-config.js`** :
    -   **Portée :** Back-office.
    -   **Objectif :** Ce script gère probablement le comportement dynamique de la page de configuration du module. Cela pourrait inclure :
        -   Afficher/masquer le champ de saisie « Nom du hook personnalisé » en fonction de la valeur de la liste déroulante « Afficher sur la page produit (Sélection du hook) ».
        -   Appels AJAX pour le bouton « Effacer les données Omnibus » afin d'effectuer le nettoyage des données sans rechargement complet de la page.
        -   Validation des entrées ou autres éléments interactifs sur le formulaire de configuration.
    -   **Écouteurs d'événements :** Écoute probablement les événements `change` sur les listes déroulantes et les événements `click` sur les boutons du formulaire de configuration du module.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`omnifree/views/css/admin-config.css`** :
    -   **Portée :** Style du formulaire d'administration du back-office.
    -   **Objectif :** Fournit un style spécifique pour les éléments de la page de configuration du module dans le back office de PrestaShop, garantissant une interface d'administration cohérente et conviviale.
    -   **Sélecteurs de classe CSS clés :** Cible probablement des ID ou des classes spécifiques dans le modèle `configure.tpl`.
-   **`omnifree/views/css/omnibus-classic.css`** :
    -   **Portée :** Style client Front-office (spécifiquement pour le thème Classic).
    -   **Objectif :** Contient des règles CSS pour garantir que les informations de prix les plus bas affichées sont correctement stylisées et positionnées dans le thème PrestaShop Classic, évitant les conflits et maintenant l'harmonie visuelle.
    -   **Sélecteurs de classe CSS clés :** Cible des éléments comme `.product-prices`, `.product-information`, ou des classes personnalisées ajoutées par le module pour l'affichage de l'historique des prix.
-   **`omnifree/views/css/omnibus-hummingbird.css`** :
    -   **Portée :** Style client Front-office (spécifiquement pour le thème Hummingbird).
    -   **Objectif :** Fournit des ajustements de style et de positionnement spécifiques pour les informations de prix les plus bas lorsque le thème Hummingbird (par défaut de PrestaShop 8.x) est actif.
    -   **Sélecteurs de classe CSS clés :** Cible des éléments spécifiques à la structure de la page produit du thème Hummingbird.
-   **`omnifree/views/css/omnibus.css`** :
    -   **Portée :** Style client Front-office (général).
    -   **Objectif :** Contient des règles CSS générales, indépendantes du thème, pour l'affichage du prix le plus bas. Cela peut inclure un style de police de base, une couleur ou une marge qui s'applique quel que soit le profil de thème spécifique choisi.
    -   **Sélecteurs de classe CSS clés :** Classes génériques utilisées dans `omnibus.tpl`.

### 4.6 Structure du modèle Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** :
    -   **`omnifree/views/templates/hook/omnibus.tpl`** :
        -   **Objectif :** C'est le modèle front-office principal responsable du rendu des informations sur le prix le plus bas des 30 derniers jours. Il sera rendu par les méthodes de hook du module (par exemple, `hookDisplayProductPriceBlock`, `hookDisplayProductButtons`, ou un hook personnalisé).
        -   **Variables :** S'attend probablement à des variables telles que `$lowest_price_30_days`, `$currency_symbol`, `$display_text`, et potentiellement `$product_id` ou `$id_product_attribute`.
        -   **Sortie :** Un petit extrait HTML contenant le texte configuré et le prix le plus bas formaté.
-   **Modèles d'administration (`views/templates/admin/`)** :
    -   **`omnifree/views/templates/admin/configure.tpl`** :
        -   **Objectif :** Ce modèle rend le formulaire de configuration principal du module dans le back office de PrestaShop. Il inclut tous les paramètres décrits dans la Section 4.1.
        -   **Variables :** Reçoit les valeurs de configuration de `getContent()` pour pré-remplir les champs du formulaire.
        -   **Structure :** Utilise la structure de formulaire d'aide de PrestaShop (par exemple, `AdminForm`) pour créer les champs de saisie, les interrupteurs et les boutons.
    -   **`omnifree/views/templates/admin/pro-teaser.tpl`** :
        -   **Objectif :** Ce modèle affiche probablement du contenu promotionnel ou un « teaser » pour une version « Pro » ou payante du module Directive Omnibus par MyPresta.eu. Il pourrait mettre en évidence des fonctionnalités supplémentaires disponibles dans la version premium.
        -   **Placement :** Probablement inclus dans `configure.tpl` ou affiché comme un bloc séparé sur la page de configuration.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** :
    -   Le dossier n'indique aucun fichier SQL personnalisé. Cela suggère que les données d'historique des prix sont soit :
        1.  Stockées directement dans `ps_configuration` sous forme de tableaux sérialisés (moins efficace pour les grands ensembles de données).
        2.  Calculées dynamiquement à partir des tables `ps_order_detail` et `ps_product_attribute_combination` (plus complexe, mais évite les tables personnalisées).
        3.  Une table personnalisée est créée par programme dans `install()` sans fichier SQL séparé. Compte tenu de la nature « Addon Gratuit », l'option 1 ou 2 est plus probable pour la simplicité.
-   **Table des hooks enregistrés** :

| Nom du hook | Portée | Moment d'exécution | Objectif technique |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | À chaque chargement de page dans la section `<head>`. | Pour charger les actifs CSS/JS du module (par exemple, `omnibus.css`, `omnibus-classic.css`, `omnibus-hummingbird.css`). |
| `displayProductPriceBlock` | Front-Office | Sur les pages produits, généralement près du prix. | L'un des hooks principaux pour afficher les informations de prix les plus bas dans le thème Classic. |
| `displayProductButtons` | Front-Office | Sur les pages produits, généralement près du bouton d'ajout au panier. | Un autre hook potentiel pour afficher les informations de prix les plus bas dans le thème Classic. |
| `displayFooter` | Front-Office | En bas de chaque page. | Moins probable pour l'affichage des prix, mais pourrait être utilisé pour des messages de conformité généraux ou si un hook personnalisé est placé ici. |
| `actionProductUpdate` | Back-Office | Lorsqu'un produit est mis à jour/enregistré dans le back office. | Pour déclencher le mécanisme de suivi des prix et enregistrer le prix actuel du produit pour l'historique. |
| `actionProductSave` | Back-Office | Lorsqu'un produit est enregistré (nouveau ou existant) dans le back office. | Similaire à `actionProductUpdate`, garantit que les changements de prix sont capturés. |
| `actionFrontControllerSetMedia` | Front-Office | Avant qu'un contrôleur frontal ne rende sa sortie. | Pour charger conditionnellement des CSS/JS spécifiques en fonction de la page ou du thème actuel. |
| (Nom du hook personnalisé) | Front-Office | Où le marchand place `{hook h='NomDuHookPersonnalisé'}` dans son modèle. | Permet un placement flexible de l'affichage du prix le plus bas pour les thèmes fortement personnalisés. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Directive Omnibus - Addon Gratuit », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe de support est disponible pour aider les marchands et les développeurs avec tout problème ou question lié à la fonctionnalité et à l'intégration du module.
