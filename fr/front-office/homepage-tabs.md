---
title: "Onglets de page d'accueil - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Onglets de page d'accueil par MyPresta.eu."
sidebar:
  label: "Onglets de page d'accueil - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Homepage tabs sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tabs.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/homepage-tabs/)
>
> ---


# Onglets de page d'accueil

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur inhabituelle n'est requise.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Onglets de page d'accueil » dans le Gestionnaire de modules. Cela vous mènera à l'écran de configuration principal.

La page de configuration du module est simple, se concentrant principalement sur la garantie que le module peut recevoir des mises à jour.

- **Ce que fait ce paramètre :** Cette section gère la capacité du module à vérifier et à recevoir les mises à jour de MyPresta.eu. Maintenir vos modules à jour est crucial pour la sécurité, les performances et la compatibilité avec les nouvelles versions de PrestaShop.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'activé (par défaut) :* Le module vérifiera périodiquement MyPresta.eu pour de nouvelles versions. Si une mise à jour est disponible, vous serez averti dans votre back office PrestaShop, vous permettant de télécharger et d'installer facilement la dernière version. Cela garantit que votre module reste compatible et bénéficie des dernières fonctionnalités et corrections de bugs.
  - *Lorsqu'désactivé :* Le module ne vérifiera pas les mises à jour. Vous ne serez pas informé des nouvelles versions, risquant de manquer des améliorations importantes, des correctifs de sécurité ou des correctifs de compatibilité. Vous devrez vérifier manuellement les mises à jour sur MyPresta.eu.
- **Valeur recommandée :** **OUI (Activé)**. Il est fortement recommandé de laisser ce paramètre activé pour garantir que votre module est toujours à jour et sécurisé.
- **Scénario / exemple de marchand :** Imaginez que PrestaShop publie une nouvelle version mineure (par exemple, 8.1.5). Une mise à jour du module « Onglets de page d'accueil » pourrait être publiée pour assurer une compatibilité totale. Avec les mises à jour activées, vous seriez averti et pourriez facilement mettre à jour, évitant ainsi tout problème potentiel. Si désactivé, vos onglets pourraient cesser de fonctionner correctement après la mise à jour de PrestaShop, et vous ne sauriez pas pourquoi avant de vérifier manuellement les mises à jour du module.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Vérifications des mises à jour (`mypresta_updates`, `update_`, `updatev_`) | OUI (Activé) | Active les vérifications automatiques des mises à jour du module depuis MyPresta.eu, garantissant la compatibilité, la sécurité et l'accès aux nouvelles fonctionnalités. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes onglets de page d'accueil n'apparaissent pas après l'installation.**
R :

1.  **Vérifier la position du module :** Allez dans **Design > Positions** dans votre back office PrestaShop. Recherchez `displayHome`. Assurez-vous que le module « Onglets de page d'accueil » est accroché à `displayHome`. S'il n'y est pas, utilisez le bouton « Greffer un module » pour l'ajouter.
2.  **Vider le cache :** Videz toujours votre cache PrestaShop après avoir installé ou configuré des modules. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » dans le coin supérieur droit.
3.  **Vérifier les conflits de thème :** Certains thèmes personnalisés peuvent remplacer le hook `displayHome` ou avoir un style spécifique qui masque le module. Basculez temporairement vers le thème PrestaShop par défaut (Classic) pour voir si les onglets apparaissent. Si c'est le cas, votre thème nécessite des ajustements CSS ou de modèle personnalisés.

**Q : Les produits dans les onglets ne s'affichent pas correctement (par exemple, mauvaise taille, mal alignés).**
R : Il s'agit généralement d'un problème de style lié au thème de votre boutique. Le module lui-même fournit les données du produit, mais votre thème dicte la façon dont les listes de produits sont affichées.

1.  **Vider le cache :** Encore une fois, videz votre cache PrestaShop.
2.  **CSS du thème :** Le CSS de votre thème peut être en conflit avec le style par défaut du module. Un développeur web peut inspecter les éléments à l'aide des outils de développement du navigateur et appliquer des remplacements CSS personnalisés dans le fichier `custom.css` de votre thème pour corriger l'apparence.

**Q : Puis-je modifier l'ordre des onglets ou les produits qui y apparaissent ?**
R : Ce module restaure la *fonctionnalité* des onglets de page d'accueil (Populaire, Nouveau, Meilleures ventes, En promotion). Les types de produits spécifiques affichés (par exemple, « Produits populaires ») sont déterminés par la logique de base de PrestaShop pour ces catégories. Ce module n'offre pas d'options pour sélectionner manuellement les produits pour chaque onglet ou réorganiser les onglets eux-mêmes via sa configuration. Pour une personnalisation avancée comme des sélections de produits personnalisées ou l'ordre des onglets, vous auriez généralement besoin d'un module plus avancé ou d'un développement personnalisé.

**Q : Le module est installé, mais je ne vois aucune option de configuration au-delà des paramètres de mise à jour.**
R : Ce module est conçu pour réactiver la fonctionnalité principale des onglets de page d'accueil de PrestaShop qui a été supprimée. Sa fonction principale est de faire réapparaître les onglets, en utilisant la logique par défaut de PrestaShop pour les produits « Populaires », « Nouveaux », « Meilleures ventes » et « En promotion ». Par conséquent, il ne dispose pas d'options de configuration étendues pour la gestion du contenu au sein des onglets eux-mêmes, car cette logique est gérée par le cœur de PrestaShop.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Onglets de page d'accueil » (`homepagetabs`) est un module PrestaShop léger conçu pour réactiver une fonctionnalité front-office essentielle qui a été supprimée dans les versions plus récentes de PrestaShop. Il fonctionne principalement en s'accrochant à `displayHome` pour rendre les onglets de produits et à `displayHeader` pour inclure les ressources nécessaires. Il exploite les mécanismes existants de récupération de produits de PrestaShop pour les produits « Populaires », « Nouveaux », « Meilleures ventes » et « En promotion », agissant efficacement comme un pont pour restaurer le composant visuel. Le module suit un modèle MVC PrestaShop standard, bien que sa logique principale réside dans la classe de module principale (`homepagetabs.php`) pour le rendu.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Aucun. La logique d'affichage front-office du module est entièrement gérée par le fichier de module `homepagetabs.php` via des hooks.
-   **Contrôleurs d'administration Back-Office** : Aucun. Toute la configuration est gérée directement dans la méthode `getContent()` de la classe de module principale.

### 4.3 Classes et modèles principaux (`classes/`)

-   Aucun. Le module ne définit aucune classe personnalisée ni aucune instance d'`ObjectModel`. Il s'appuie sur les classes principales de PrestaShop pour la récupération des données de produits.

### 4.4 Ressources JavaScript (`views/js/`)

-   `homepagetabs/views/js/homepagetabs.js`
    -   **Portée** : Front-office.
    -   **Responsabilité** : Ce script est responsable du comportement interactif des onglets de la page d'accueil. Il gère probablement :
        -   La liaison des écouteurs d'événements de clic aux en-têtes d'onglet.
        -   Le basculement de la visibilité des blocs de contenu de produit en fonction de l'onglet actif.
        -   L'ajout/suppression de classes CSS actives aux en-têtes d'onglet et au contenu.
        -   Potentiellement la gestion des requêtes AJAX si le contenu du produit est chargé dynamiquement (bien que pour ce module, il s'agisse plus probablement d'un simple mécanisme d'affichage/masquage pour le contenu pré-rendu).
        -   S'assurer que les onglets fonctionnent correctement sur différentes tailles d'écran et appareils.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `homepagetabs/views/css/homepagetabs.css`
    -   **Portée** : Style client Front-office.
    -   **Responsabilité** : Cette feuille de style fournit la présentation visuelle par défaut des onglets de la page d'accueil et de leur contenu. Elle définit les styles pour :
        -   Le conteneur d'onglets lui-même.
        -   Les en-têtes d'onglets individuels (par exemple, `ul.home-tabs li a`).
        -   L'état de l'onglet actif (par exemple, `ul.home-tabs li.active a`).
        -   Le conteneur de la grille de produits pour chaque onglet (par exemple, `.tab-content`).
        -   Des ajustements réactifs de base pour différentes tailles d'écran.
    -   **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer** : Les développeurs peuvent cibler des classes comme `.home-tabs`, `.home-tabs li`, `.home-tabs li.active`, `.tab-content` et les éléments de la grille de produits dans `.tab-content` pour intégrer l'apparence du module de manière transparente avec leur thème personnalisé.

### 4.6 Structure du modèle Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** :
    -   `homepagetabs/views/templates/hook/homepagetabs.tpl`
        -   **Hook** : `displayHome`
        -   **Objectif** : Il s'agit du modèle front-office principal responsable du rendu de l'intégralité du bloc d'onglets de la page d'accueil. Il contiendra la structure HTML pour les en-têtes d'onglet (par exemple, `<ul>` pour les titres d'onglet) et les zones de contenu correspondantes (par exemple, `<div>` pour les listes de produits). Il itère sur les données de produit qui lui sont transmises par la méthode `hookDisplayHome()` du module, affichant les produits « Populaires », « Nouveaux », « Meilleures ventes » et « En promotion » dans leurs zones de contenu d'onglet respectives. Ce modèle est l'endroit où les fiches produits (images, noms, prix, boutons d'ajout au panier) sont rendues pour chaque type de produit.
-   **Modèles d'administration (`views/templates/admin/`)** :
    -   `homepagetabs/views/templates/admin/homepagetabs.tpl`
        -   **Objectif** : Ce modèle rend le formulaire de configuration du module dans le back office de PrestaShop. Il affiche les paramètres liés aux vérifications de mise à jour (`mypresta_updates`, `update_`, `updatev_`) et tout autre élément de configuration de module standard.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** : Le module ne crée aucune table de base de données personnalisée. Il stocke ses paramètres de configuration (par exemple, `mypresta_updates`) dans la table standard `ps_configuration`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHome` | Rend le contenu sur la page d'accueil de la boutique. | Ce hook est utilisé pour afficher l'intégralité de la structure HTML des onglets de la page d'accueil, y compris les en-têtes d'onglet et les listes de produits. |
| `displayHeader` | Exécuté dans la section `<head>` de chaque page front-office. | Ce hook est utilisé pour inclure les fichiers CSS (`homepagetabs.css`) et JavaScript (`homepagetabs.js`) du module, garantissant un style et une fonctionnalité interactive corrects des onglets. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et une assistance supplémentaire concernant le module « Onglets de page d'accueil », veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez rencontrer.
