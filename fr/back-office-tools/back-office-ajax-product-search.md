---
title: "Recherche de produits Ajax dans le Back Office - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Recherche de produits Ajax dans le Back Office' par MyPresta.eu."
sidebar:
  label: "Recherche de produits Ajax dans le Back Office - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Back office ajax product search sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/back-office-ajax-product-search.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/back-office-ajax-product-search/)
>
> ---


# Recherche de produits Ajax dans le Back Office

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont habituellement disponibles sur tout environnement d'hébergement moderne.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ce module est conçu pour être très efficace et largement « configuré une fois pour toutes ». Il s'intègre parfaitement à votre back office sans nécessiter de configurations complexes.

Lorsque vous cliquez sur « Configurer » après l'installation, vous trouverez généralement une interface simple, souvent sans paramètres spécifiques à ajuster. La fonctionnalité principale du module (recherche de produits AJAX avec autocomplétion) est activée par défaut lors de l'installation.

-   **Ce que fait cet écran :** C'est la zone de configuration principale du module. Cependant, pour la « Recherche de produits Ajax dans le Back Office », sa fonction première est de confirmer que le module est installé et actif.
-   **Effet de la modification des paramètres :** Puisqu'il n'y a pas de paramètres configurables par l'utilisateur exposés sur cet écran, le module fonctionnera avec son comportement par défaut et optimisé.
-   **Valeur recommandée :** Aucune action spécifique n'est généralement requise ici. Le module est conçu pour fonctionner dès l'installation.
-   **Scénario/exemple pour le marchand :** Après l'installation, naviguez simplement vers n'importe quelle page du back office. Vous devriez remarquer que lorsque vous commencez à taper dans un champ de recherche de produits, des suggestions apparaissent instantanément, et cliquer dessus vous mène directement à la page d'édition du produit.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | (Aucun paramètre spécifique) | N/A | Le module améliore automatiquement la recherche de produits du back office avec la fonctionnalité d'autocomplétion AJAX dès l'installation. |

## 3. Dépannage pour le marchand et Foire aux questions (FAQ)

**Q : J'ai installé le module, mais la barre de recherche ne semble pas fonctionner différemment.**
R :

1.  **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » en haut à droite. Parfois, le cache de PrestaShop doit être vidé pour que les nouveaux actifs du module (comme JavaScript et CSS) se chargent correctement.
2.  **Cache du navigateur :** Essayez de vider le cache de votre navigateur ou de tester dans une fenêtre de navigation privée/incognito.
3.  **Statut du module :** Assurez-vous que le module est activé dans **Modules > Gestionnaire de modules**.
4.  **Compatibilité du thème :** Bien que rare pour les modules de back office, un thème d'administration fortement personnalisé pourrait interférer. Si le problème persiste, contactez le support MyPresta.eu.

**Q : Ce module va-t-il ralentir mon back office ?**
R : Non, bien au contraire. En utilisant AJAX, le module effectue des recherches en arrière-plan sans rechargement complet des pages, ce qui est intrinsèquement plus rapide et plus efficace que les méthodes de recherche traditionnelles. Il est conçu pour améliorer les performances, pas pour les entraver.

**Q : Ce module affecte-t-il la recherche front-office pour les clients ?**
R : Non, ce module est strictement destiné au back office de PrestaShop. Il n'a aucun impact sur la boutique visible par les clients ou sur sa fonctionnalité de recherche.

**Q : Puis-je configurer le nombre de résultats de recherche affichés ?**
R : Ce module est conçu pour la simplicité et la fonctionnalité prête à l'emploi. Il n'offre généralement pas d'options configurables pour le nombre de résultats. Le comportement par défaut est généralement optimisé pour une bonne expérience utilisateur.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module `Recherche de produits Ajax dans le Back Office` (boproductfinder) est un module PrestaShop léger principalement axé sur l'amélioration de l'expérience utilisateur au sein du back office. Il réalise sa fonctionnalité en injectant des actifs JavaScript et CSS personnalisés dans l'en-tête du back office, en tirant parti du système de hooks de PrestaShop. La logique principale réside dans le JavaScript côté client, qui intercepte la saisie de l'utilisateur dans des champs de recherche spécifiques et effectue des requêtes AJAX vers les points d d'accès de recherche de produits intégrés de PrestaShop, puis affiche les résultats à l'aide d'une interface utilisateur d'autocomplétion. Il n'introduit pas de nouvelles tables de base de données ni de logique complexe côté serveur au-delà de ce que PrestaShop fournit déjà pour la recherche de produits.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur front-office ou back-office personnalisé. Il s'appuie sur les contrôleurs PrestaShop existants pour gérer les requêtes de recherche de produits (par exemple, les méthodes AJAX de `AdminProductsController`).

### 4.3 Classes et modèles principaux (`classes/`)

Ce module n'introduit aucune classe PHP personnalisée ni définition d'`ObjectModel`. Sa fonctionnalité est principalement côté client.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`boproductfinder/views/autocomplete.js`**
    *   **Portée** : Back-office.
    *   **Description** : Ce script implémente ou intègre probablement une bibliothèque d'autocomplétion générique. Il fournit la fonctionnalité principale pour afficher des suggestions au fur et à mesure que l'utilisateur tape dans un champ de saisie de texte. Il gère le rendu de l'interface utilisateur de la liste de suggestions, la navigation au clavier dans la liste et la sélection des éléments. C'est un composant fondamental pour la recherche interactive du module.
-   **`boproductfinder/views/boproductfinder.js`**
    *   **Portée** : Back-office.
    *   **Description** : C'est le script principal du module.
    *   **Écouteurs d'événements** : Il se lie probablement aux événements `keyup` ou `input` sur des champs de saisie de recherche de produits spécifiques dans le back office de PrestaShop (par exemple, `input[name="product_search"]` ou des sélecteurs similaires).
    *   **Appels AJAX** : Lorsqu'un utilisateur tape, ce script déclenche des requêtes AJAX vers l'API de recherche de produits interne de PrestaShop (par exemple, `admin-ajax.php` ou une action AJAX spécifique d'un contrôleur d'administration pour la recherche de produits). Il envoie la requête de recherche et potentiellement d'autres paramètres (par exemple, `id_lang`).
    *   **Manipulation du DOM** : Il reçoit la réponse JSON du serveur (contenant les ID de produits, les noms et potentiellement les liens) et utilise `autocomplete.js` (ou une logique similaire) pour afficher ces résultats dans une liste déroulante sous le champ de recherche.
    *   **Navigation** : Lorsqu'une suggestion de produit est cliquée ou sélectionnée, ce script construit l'URL de la page d'édition du produit (par exemple, `admin/index.php?controller=AdminProducts&id_product=X&updateproduct&token=Y`) et redirige le navigateur vers cette page.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`boproductfinder/views/autocomplete.css`**
    *   **Portée** : Style des formulaires d'administration du back-office.
    *   **Description** : Cette feuille de style fournit le style visuel pour la liste de suggestions d'autocomplétion.
    *   **Principaux composants et conteneurs d'interface utilisateur qu'elle stylise** :
        *   Le conteneur déroulant pour les résultats de recherche.
        *   Les éléments de liste individuels dans les suggestions.
        *   La mise en surbrillance pour la suggestion actuellement survolée ou sélectionnée.
        *   Potentiellement des indicateurs de chargement ou des messages « aucun résultat ».
    *   **Sélecteurs de classes CSS clés que les développeurs peuvent surcharger** : Les développeurs peuvent inspecter le HTML généré pour des classes comme `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected` afin de personnaliser l'apparence dans leur thème d'administration.

### 4.6 Structure des templates Smarty (`views/templates/`)

Ce module ne contient aucun fichier de template Smarty (`.tpl`) personnalisé. Sa fonctionnalité est injectée directement via des actifs JavaScript et CSS chargés via des hooks.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** : Ce module ne crée aucune table de base de données personnalisée. Il s'appuie sur les tables PrestaShop existantes `ps_product`, `ps_product_lang` et les tables associées pour les données de produits. La configuration est stockée dans `ps_configuration` si des paramètres étaient présents, mais pour ce module, elle est généralement minimale ou inexistante.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayBackOfficeHeader` | Exécuté dans la section `<head>` de chaque page du back office. | Utilisé pour inclure les fichiers CSS et JavaScript du module (`autocomplete.css`, `autocomplete.js`, `boproductfinder.js`) afin de s'assurer qu'ils sont chargés sur toutes les pages d'administration où la fonctionnalité de recherche pourrait être nécessaire. |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses actifs média. | Un hook alternatif ou complémentaire à `displayBackOfficeHeader` pour ajouter des fichiers CSS et JS, assurant la compatibilité entre les différentes versions de PrestaShop et les thèmes du back office. Il garantit que les actifs du module sont correctement enregistrés et chargés. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Recherche de produits Ajax dans le Back Office », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir concernant la fonctionnalité ou la compatibilité du module.
