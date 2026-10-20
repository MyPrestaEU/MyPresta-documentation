---
title: "Éditeur de combinaisons de produits en masse - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Éditeur de combinaisons de produits en masse' par MyPresta.eu."
sidebar:
  label: "Éditeur de combinaisons de produits en masse - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Mass product combinations editor sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-product-combinations-editor.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/mass-product-combinations-editor/)
>
> ---


# Éditeur de combinaisons de produits en masse

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune exigence de serveur particulière au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Éditeur de combinaisons de produits en masse)

En cliquant sur « Configurer » pour le module « Éditeur de combinaisons de produits en masse », vous serez dirigé vers une interface d'administration dédiée. C'est là que vous effectuerez toutes vos modifications de combinaisons en masse.

La page de configuration principale de ce module agit comme son interface principale. Elle n'a pas de « formulaire de paramètres » traditionnel avec des interrupteurs et des champs de saisie pour le module lui-même, mais elle EST l'outil d'édition des combinaisons.

Voici un aperçu de ce que vous verrez et comment l'utiliser :

**Nom de l'écran et emplacement du menu :**

-   **Chemin du menu :** Après l'installation, vous trouverez généralement un nouvel élément de menu sous **Catalogue** ou **Modules** (selon votre version et thème PrestaShop) ou vous pouvez toujours y accéder via **Modules > Gestionnaire de modules** et en cliquant sur « Configurer » à côté de « Éditeur de combinaisons de produits en masse ».
-   **Titre de l'écran :** « Éditeur de combinaisons de produits en masse » ou similaire.

**Actions et paramètres disponibles :**

L'interface principale vous présentera une grille ou un tableau puissant qui liste les combinaisons de produits. L'apparence exacte peut varier légèrement entre les versions de PrestaShop, mais la fonctionnalité principale reste cohérente.

1.  **Sélection / Filtrage des produits :**

    -   **Ce que cela fait :** Cette zone vous permet de sélectionner les combinaisons de produits que vous souhaitez modifier. Vous pouvez voir une barre de recherche, une liste déroulante de produits ou des filtres par catégorie, fabricant, etc.
    -   **Effet de la modification de ce paramètre :** En sélectionnant un produit ou en appliquant des filtres, le tableau ci-dessous sera rempli uniquement avec les combinaisons appartenant aux produits choisis. Ceci est crucial pour affiner votre focus.
    -   **Valeur recommandée :** Commencez par rechercher un produit spécifique ou filtrez par catégorie pour vous familiariser avec l'interface.
    -   **Scénario / exemple de marchand :** Vous souhaitez mettre à jour le stock de toutes les combinaisons de votre produit « T-shirt d'été ». Vous recherchez « T-shirt d'été » et le sélectionnez.
2.  **Tableau de liste des combinaisons :**

    -   **Ce que cela fait :** C'est le cœur du module. Il affiche un tableau où chaque ligne représente une combinaison de produit unique (par exemple, « T-shirt - Rouge - Petit »). Les colonnes représentent des champs modifiables comme :
        -   **Référence :** Code produit interne pour cette combinaison spécifique.
        -   **EAN13 / UPC :** Numéros de code-barres.
        -   **Quantité :** Niveau de stock pour cette combinaison.
        -   **Impact sur le prix :** Comment cette combinaison affecte le prix de base du produit (par exemple, +5 € pour la taille XL).
        -   **Prix d'achat :** Le prix de revient de cette combinaison.
        -   **Poids :** Comment cette combinaison affecte le poids de base du produit.
        -   **Quantité minimale :** Le nombre minimum de cette combinaison qu'un client doit acheter.
        -   **Combinaison par défaut :** Une case à cocher pour marquer une combinaison comme par défaut pour le produit.
        -   **Image :** L'image associée à cette combinaison.
    -   **Effet de la modification de ce paramètre :** Vous pouvez cliquer directement dans les cellules de ce tableau et taper de nouvelles valeurs. Par exemple, changer la « Quantité » de 5 à 10 mettra à jour le niveau de stock pour cette combinaison spécifique.
    -   **Valeur recommandée :** Examinez attentivement chaque combinaison et ses valeurs actuelles avant d'apporter des modifications.
    -   **Scénario / exemple de marchand :** Vous venez de recevoir une nouvelle expédition. Vous pouvez parcourir la colonne « Quantité » et mettre à jour les niveaux de stock pour toutes les combinaisons pertinentes en quelques secondes.
3.  **Bouton Enregistrer :**

    -   **Ce que cela fait :** Après avoir effectué toutes les modifications souhaitées dans le tableau, vous **devez** cliquer sur un bouton « Enregistrer » ou « Appliquer les modifications » (généralement situé en haut ou en bas du tableau) pour valider vos modifications dans la base de données.
    -   **Effet de la modification de ce paramètre :** Tant que vous ne cliquez pas sur enregistrer, vos modifications ne sont visibles que sur l'écran et ne sont pas actives sur votre boutique. Cliquer sur enregistrer applique toutes les modifications en attente.
    -   **Valeur recommandée :** Enregistrez toujours votre travail fréquemment, surtout après avoir effectué un lot de modifications.
    -   **Scénario / exemple de marchand :** Vous avez mis à jour les prix de 20 combinaisons. Cliquez sur « Enregistrer » pour que ces nouveaux prix soient actifs sur vos pages de produits.

**Flux de travail recommandé pour la gestion quotidienne de la boutique :**

1.  **Identifiez votre tâche :** Devez-vous mettre à jour le stock, modifier les prix ou modifier les références ?
2.  **Naviguez vers le module :** Allez dans **Modules > Gestionnaire de modules** et cliquez sur « Configurer » pour « Éditeur de combinaisons de produits en masse ».
3.  **Sélectionnez les produits :** Utilisez les options de recherche ou de filtre pour charger les combinaisons avec lesquelles vous devez travailler.
4.  **Effectuez les modifications :** Modifiez directement les valeurs dans les cellules du tableau. Vous pouvez souvent utiliser des raccourcis clavier (comme Tab) pour vous déplacer rapidement entre les champs.
5.  **Vérifiez :** Revérifiez vos modifications avant d'enregistrer.
6.  **Enregistrez :** Cliquez sur le bouton « Enregistrer » pour appliquer toutes les modifications.
7.  **Videz le cache (si nécessaire) :** Dans certains cas, surtout après des changements majeurs de prix ou de stock, il est bon de vider votre cache PrestaShop (**Paramètres avancés > Performances**) pour s'assurer que les changements sont immédiatement visibles sur le front office.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Sélection/Filtre de produits | (Varie selon le produit) | Réduit les combinaisons affichées pour l'édition. |
| Page de configuration du module | Tableau de liste des combinaisons (par exemple, Quantité, Impact sur le prix, Référence, EAN13) | (Varie selon le produit) | Édition directe des attributs de combinaison. Les modifications sont appliquées à la combinaison sélectionnée. |
| Page de configuration du module | Bouton Enregistrer | Cliquer après les modifications | Valide toutes les modifications à l'écran dans la base de données, les rendant actives sur votre boutique. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : Mes modifications n'apparaissent pas sur le front office après avoir enregistré !**
R : Il s'agit généralement d'un problème de cache. Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » / « Vider le cache » selon votre version). Vos modifications devraient alors apparaître.

**Q : Le module est lent à charger les combinaisons pour les produits avec de nombreuses variations.**
R : Pour les produits avec des centaines ou des milliers de combinaisons, le chargement de toutes les données peut prendre du temps. C'est normal en raison de la quantité de données traitées. Assurez-vous que votre serveur répond aux spécifications recommandées par PrestaShop. Si la lenteur est constante, vérifiez les paramètres de limite de mémoire PHP et de temps d'exécution de votre serveur (votre hébergeur peut vous aider à ce sujet).

**Q : Puis-je annuler les modifications effectuées avec ce module ?**
R : Le module met à jour directement votre base de données. Il n'y a pas de bouton « annuler » intégré. C'est pourquoi il est crucial de **toujours avoir une sauvegarde récente de votre boutique** avant d'effectuer des modifications en masse. Si vous faites une erreur, vous devrez corriger manuellement les valeurs ou restaurer à partir d'une sauvegarde.

**Q : Je ne trouve pas le module dans le menu après l'installation.**
R : Après l'installation, naviguez vers **Modules > Gestionnaire de modules**. Recherchez « Éditeur de combinaisons de produits en masse » et cliquez sur le bouton « Configurer » à côté. Cela vous mènera toujours à l'interface du module. Selon votre version et thème PrestaShop, un lien de menu direct peut apparaître sous « Catalogue » ou « Modules » pour un accès plus rapide.

**Q : Ce module fonctionne-t-il avec des thèmes personnalisés ?**
R : Oui, ce module fonctionne entièrement dans le Back Office de PrestaShop. Il n'affiche aucun élément du front office, il devrait donc être entièrement compatible avec n'importe quel thème personnalisé sans conflits.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Éditeur de combinaisons de produits en masse » (`qce`) est principalement un outil d'administration Back-Office. Il utilise la classe `Module` de PrestaShop pour sa fonctionnalité principale et un point d'accès AJAX personnalisé pour gérer le chargement et l'enregistrement dynamiques des données de combinaison de produits. L'interface du module est rendue via un template Smarty, avec JavaScript gérant les interactions utilisateur et la soumission des données. Il interagit directement avec les structures de données de produits et de combinaisons de base de PrestaShop sans introduire de nouvelles classes `ObjectModel` ou de tables de base de données.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de classes `ModuleFrontController` ou `AdminController` dédiées dans le répertoire `controllers/`. Toute la logique du Back-Office, y compris le point d'accès AJAX, est gérée directement dans le fichier principal du module `qce/ajax_qce.php` via la méthode `getContent()`.

### 4.3 Classes et modèles de base (`classes/`)

Le module n'introduit aucune classe personnalisée dans un répertoire `classes/`. Il utilise directement les classes de base de PrestaShop, telles que `Product`, `Combination`, `Tools`, `Configuration`, etc., pour récupérer et mettre à jour les données.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`qce/views/admin/js/qce.js`**
    -   **Portée :** Back-office (panneau d'administration).
    -   **Objectif :** Il s'agit du fichier JavaScript principal pour l'interface du module. Il gère :
        -   **Sélection de produits :** Gère probablement la liste déroulante ou le champ de recherche pour sélectionner un produit.
        -   **Chargement des données AJAX :** Envoie des requêtes AJAX à la méthode `getContent()` du module (ou à un gestionnaire AJAX spécifique en son sein) pour récupérer les données de combinaison pour le produit sélectionné.
        -   **Rendu du tableau :** Remplit dynamiquement le tableau HTML avec les données de combinaison reçues du serveur.
        -   **Édition en place :** Implémente la fonctionnalité permettant aux utilisateurs de cliquer sur les cellules du tableau et de modifier directement les valeurs (par exemple, des champs de saisie apparaissant au clic).
        -   **Validation des données :** Peut inclure une validation côté client pour les champs de saisie (par exemple, s'assurer que la quantité est un nombre).
        -   **Enregistrement des données AJAX :** Rassemble toutes les données de combinaison modifiées du tableau et les envoie via AJAX à la méthode `getContent()` du module pour traitement et enregistrement dans la base de données.
        -   **Retour utilisateur :** Affiche des indicateurs de chargement, des messages de succès ou des alertes d'erreur.
        -   **Écouteurs d'événements :** Lie des écouteurs à des éléments tels que les listes déroulantes de sélection de produits, les champs de saisie dans le tableau et le bouton « Enregistrer ».

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`qce/lib/blue/style.css`**
    -   **Portée :** Back-office (panneau d'administration).
    -   **Objectif :** Il semble s'agir d'une feuille de style tierce ou générique, éventuellement pour un composant d'interface utilisateur ou un thème de style spécifique utilisé dans l'interface du module. Elle définit probablement des styles de tableau généraux, des styles de champs de saisie ou l'esthétique des boutons. Les développeurs doivent inspecter ce fichier pour comprendre son impact sur la présentation visuelle du module.
-   **`qce/views/admin/css/qce.css`**
    -   **Portée :** Back-office (panneau d'administration).
    -   **Objectif :** Il s'agit de la feuille de style spécifique du module. Elle contient des règles CSS personnalisées pour styliser le tableau d'édition des combinaisons, les éléments de sélection de produits et tout autre composant d'interface utilisateur unique dans la page de configuration du module.
    -   **Sélecteurs de classes CSS clés :** Les développeurs souhaitant remplacer ou personnaliser l'apparence du module doivent inspecter ce fichier pour les noms de classes comme `.qce-table`, `.qce-product-selector`, `.qce-input-field`, etc., et les cibler dans leur thème d'administration personnalisé ou en remplaçant le CSS du module.

### 4.6 Structure du template Smarty (`views/templates/`)

-   **`qce/views/admin/qce.tpl`**
    -   **Portée :** Template d'administration.
    -   **Objectif :** Il s'agit du fichier de template Smarty principal responsable du rendu de l'interface complète de l'« Éditeur de combinaisons de produits en masse » dans le Back Office de PrestaShop.
    -   **Contenu :** Il inclut généralement :
        -   La structure HTML pour la zone de sélection/filtrage des produits.
        -   L'espace réservé (par exemple, un `<table>` ou `<div>` vide) où les données de combinaison seront chargées et rendues dynamiquement par `qce.js`.
        -   Le bouton « Enregistrer » et tout autre bouton d'action.
        -   Les inclusions pour les fichiers JavaScript (`qce.js`) et CSS (`qce.css`, `style.css`) nécessaires.
        -   Tout message initial ou instruction pour le marchand.
    -   **Rendu :** Ce template est rendu par la méthode `getContent()` du fichier de module `ajax_qce.php`.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :
    -   Le module ne crée **pas** de tables de base de données personnalisées.
    -   Il lit et écrit directement dans les tables de base de PrestaShop liées aux produits et aux combinaisons, principalement :
        -   `ps_product_attribute` (données principales des combinaisons)
        -   `ps_product_attribute_shop` (données des combinaisons spécifiques à la boutique)
        -   `ps_product_attribute_combination` (lie les attributs aux combinaisons)
        -   `ps_product` (pour les informations sur le produit)
        -   `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang` (pour les définitions d'attributs)
        -   `ps_image`, `ps_image_shop`, `ps_image_lang` (pour les images de combinaison)
    -   Les paramètres de configuration (s'il y en avait au-delà de l'interface principale) seraient stockés dans `ps_configuration`.
-   **Table des hooks enregistrés** :
    Le module n'enregistre pas explicitement de hooks d'affichage front-office ou back-office (`displayHeader`, `actionValidateOrder`, etc.) au sens traditionnel. Sa fonctionnalité est accessible directement via sa page de configuration dans le Back Office. La méthode `install()` du module s'enregistrerait en tant que module d'administration, le rendant accessible via le Gestionnaire de modules.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Éditeur de combinaisons de produits en masse », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité du module.
