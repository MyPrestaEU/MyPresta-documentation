---
title: "Related Products Pro - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Related Products Pro par MyPresta.eu."
sidebar:
  label: "Related Products Pro - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Related Products Pro sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/related-products-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/related-products-pro/)
>
> ---


# Related Products Pro

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises et sont habituellement activées par défaut sur la plupart des environnements d'hébergement.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Gestionnaire de modules > Related Products Pro > Configurer)

Ceci est l'écran de configuration principal où vous gérerez tous les aspects de vos listes de produits associés. L'interface est conçue pour être intuitive, vous permettant de créer, modifier et attribuer des produits associés avec facilité.

La page de configuration présentera généralement une liste de vos listes de produits associés existantes (le cas échéant) et des options pour en créer de nouvelles ou gérer les paramètres globaux.

#### **Éléments principaux de l'interface :**

-   **Liste des blocs de produits associés existants :** Ce tableau affichera toutes les listes de produits associés que vous avez créées. Pour chaque liste, vous verrez des détails comme son nom, les produits auxquels elle est attribuée, et des options pour la modifier ou la supprimer.
-   **Bouton « Ajouter un nouveau bloc de produits associés » :** Cliquez ici pour créer un tout nouvel ensemble de produits associés.
-   **Paramètres globaux / Préférences :** (Si disponibles) Ces paramètres peuvent contrôler les options d'affichage générales ou les comportements par défaut pour tous les blocs de produits associés.

#### **Lors de l'ajout/modification d'un bloc de produits associés :**

Lorsque vous cliquez pour ajouter un nouveau bloc ou modifier un bloc existant, vous verrez généralement un formulaire avec les paramètres suivants :

1.  **Nom du bloc :**

    -   **Ce que fait ce paramètre :** C'est le nom interne de votre liste de produits associés, visible uniquement dans le Back Office. Il vous aide à identifier les différentes listes.
    -   **Effet de la modification de ce paramètre :** Modifie l'étiquette de ce bloc de produits associés spécifique dans votre panneau d'administration.
    -   **Valeur recommandée :** Utilisez un nom descriptif, par exemple, « Produit X - Articles complémentaires », « Catégorie Y - Meilleures ventes ».
    -   **Scénario / exemple marchand :** Vous pourriez nommer une liste « Robes d'été - Sandales assorties » pour la retrouver facilement plus tard.
2.  **Emplacement d'affichage (Hook) :**

    -   **Ce que fait ce paramètre :** Détermine où ce bloc de produits associés spécifique apparaîtra sur la page produit. Vous sélectionnez un « hook » PrestaShop qui est une zone d'affichage désignée.
    -   **Effet de la modification de ce paramètre :** Les produits associés se déplaceront vers l'emplacement choisi sur la page produit du front office.
    -   **Valeur recommandée :** Expérimentez avec différents hooks en fonction de votre thème. Les choix courants incluent `displayProductExtraContent` (souvent près de la description du produit), `displayProductFooter` (en bas de la page produit), ou `displayRightColumnProduct` (si votre thème a une colonne de droite sur les pages produits).
    -   **Scénario / exemple marchand :** Si vous souhaitez que les produits associés apparaissent juste en dessous de l'image et de la description principales du produit, vous pourriez choisir `displayProductExtraContent`. Si vous les préférez tout en bas de la page, `displayProductFooter` serait mieux.
3.  **Produits à afficher :**

    -   **Ce que fait ce paramètre :** C'est ici que vous définissez *quels* produits seront affichés dans ce bloc de produits associés. Vous aurez généralement plusieurs options :
        -   **Produits spécifiques (Sélection manuelle) :**
            -   **Ce que cela fait :** Vous permet de rechercher et de sélectionner manuellement des produits individuels à inclure dans la liste.
            -   **Effet :** Seuls les produits que vous choisissez explicitement apparaîtront.
            -   **Recommandé :** À utiliser pour des recommandations très ciblées.
            -   **Scénario :** Pour un appareil photo spécifique, vous pourriez sélectionner manuellement un trépied, un sac photo et un objectif supplémentaire.
        -   **Produits des catégories sélectionnées :**
            -   **Ce que cela fait :** Affiche les produits d'une ou plusieurs catégories que vous sélectionnez.
            -   **Effet :** La liste affichera dynamiquement les produits de ces catégories.
            -   **Recommandé :** Bon pour afficher des articles connexes au sein d'une gamme de produits ou d'un département.
            -   **Scénario :** Pour une « Chemise homme », vous pourriez sélectionner les catégories « Pantalons homme » et « Accessoires homme ».
        -   **Nouveaux produits :**
            -   **Ce que cela fait :** Affiche automatiquement les produits les plus récents ajoutés à votre boutique.
            -   **Effet :** La liste affichera toujours vos dernières additions.
            -   **Recommandé :** Idéal pour promouvoir les nouveautés.
            -   **Scénario :** Utilisez ce bloc pour mettre en avant votre dernière collection de bijoux.
        -   **Meilleures ventes :**
            -   **Ce que cela fait :** Affiche automatiquement les produits les plus vendus de votre boutique.
            -   **Effet :** La liste se mettra à jour dynamiquement pour afficher vos articles les plus populaires.
            -   **Recommandé :** Excellent pour la preuve sociale et la promotion des articles populaires.
            -   **Scénario :** Afficher les articles « Les clients ont également acheté » en fonction de la popularité globale de la boutique.
    -   **Nombre de produits à afficher :**
        -   **Ce que cela fait :** Contrôle le nombre de produits associés affichés dans le bloc.
        -   **Effet :** Limite les produits visibles.
        -   **Recommandé :** 4 à 8 produits pour un aspect épuré, selon votre mise en page.
        -   **Scénario :** Afficher 5 articles associés pour garder la section concise.
4.  **Attribuer aux produits :**

    -   **Ce que fait ce paramètre :** C'est crucial – il détermine *sur quelles pages produit* ce bloc de produits associés spécifique apparaîtra.
    -   **Effet de la modification de ce paramètre :** Le bloc de produits associés ne sera visible que sur les pages produit que vous sélectionnez ici.
    -   **Valeur recommandée :** Vous pouvez l'attribuer à :
        -   **Tous les produits :** Si c'est un bloc général « Meilleures ventes » ou « Nouveautés ».
        -   **Produits spécifiques (Sélection manuelle) :** Pour des recommandations très ciblées.
        -   **Produits des catégories sélectionnées :** Pour appliquer le bloc à une gamme de catégories entière.
    -   **Scénario / exemple marchand :** Vous créez une liste d'« Accessoires iPhone ». Vous attribueriez alors ce bloc uniquement à vos pages produits iPhone. Ou, vous créez un bloc « Articles en solde d'été » et l'attribuez à tous les produits de votre catégorie « Collection d'été ».
5.  **Type d'affichage / Modèle :**

    -   **Ce que fait ce paramètre :** Vous permet de choisir la mise en page visuelle ou le modèle pour l'affichage des produits associés (par exemple, grille, carrousel, liste, tableau). Le module inclut souvent divers modèles, dont certains peuvent être optimisés pour des thèmes spécifiques (comme les thèmes Panda, Warehouse, Zone).
    -   **Effet de la modification de ce paramètre :** Modifie la présentation visuelle des produits associés sur le front office.
    -   **Valeur recommandée :** Expérimentez pour trouver la meilleure adéquation avec votre thème et le hook choisi. Un carrousel est souvent bon pour économiser de l'espace, tandis qu'une grille pourrait être meilleure pour une section dédiée.
    -   **Scénario / exemple marchand :** Si vous souhaitez un affichage élégant et peu encombrant, vous pourriez choisir un modèle « carrousel ». Si vous avez beaucoup d'espace et souhaitez afficher plus de détails, une « grille » ou un « tableau » pourrait être mieux. Certains modèles peuvent être spécifiquement nommés pour des thèmes populaires (par exemple, `panda-blocksProductsCart.tpl`) pour assurer une meilleure intégration.
6.  **Paramètres du carrousel (le cas échéant) :**

    -   **Ce que fait ce paramètre :** Si vous choisissez un type d'affichage carrousel, vous pourriez avoir des options supplémentaires comme :
        -   **Lecture automatique :** Si le carrousel défile automatiquement.
        -   **Boucle :** Si le carrousel se répète depuis le début après le dernier article.
        -   **Articles par vue :** Combien de produits sont visibles à la fois dans le carrousel.
        -   **Flèches/points de navigation :** Si les contrôles pour le défilement manuel doivent être affichés.
    -   **Effet de la modification de ce paramètre :** Contrôle le comportement et l'apparence du carrousel de produits.
    -   **Valeur recommandée :** La lecture automatique peut être engageante mais peut aussi être distrayante. Considérez votre public. 3 à 5 articles par vue est un bon équilibre courant.
    -   **Scénario / exemple marchand :** Vous voulez un carrousel subtil qui défile automatiquement toutes les 5 secondes, affichant 4 produits à la fois, avec des flèches de navigation pour les utilisateurs qui veulent naviguer manuellement.

#### **Enregistrement de vos modifications :**

N'oubliez jamais de cliquer sur le bouton « Enregistrer » ou « Mettre à jour » après avoir apporté des modifications à un bloc de produits associés pour vous assurer que vos paramètres sont appliqués.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | **Nom du bloc** | Descriptif (par exemple, « Produit X - Vente croisée ») | Étiquette interne pour identifier le bloc de produits associés dans le Back Office. |
| | **Emplacement d'affichage (Hook)** | `displayProductExtraContent` ou `displayProductFooter` | Détermine où le bloc apparaît sur la page produit du front office. |
| | **Produits à afficher : Produits spécifiques** | Sélection manuelle | Affiche uniquement les produits choisis manuellement. Idéal pour des recommandations très ciblées. |
| | **Produits à afficher : Des catégories sélectionnées** | Sélectionner les catégories pertinentes | Affiche dynamiquement les produits des catégories choisies. Bon pour les gammes de produits associées. |
| | **Produits à afficher : Nouveaux produits** | Rempli automatiquement | Affiche automatiquement les derniers produits de votre boutique. Idéal pour les nouveautés. |
| | **Produits à afficher : Meilleures ventes** | Rempli automatiquement | Affiche automatiquement les produits les plus vendus de votre boutique. Excellent pour la preuve sociale. |
| | **Nombre de produits à afficher** | 4-8 | Limite le nombre de produits affichés dans le bloc pour une mise en page épurée. |
| | **Attribuer aux produits : Tous les produits** | N/A | Affiche le bloc sur chaque page produit. À utiliser pour des recommandations générales. |
| | **Attribuer aux produits : Produits spécifiques** | Sélection manuelle | Affiche le bloc uniquement sur les pages produits sélectionnées. Pour des ventes croisées ciblées. |
| | **Attribuer aux produits : Des catégories sélectionnées** | Sélectionner les catégories pertinentes | Affiche le bloc sur les pages produits des catégories choisies. |
| | **Type d'affichage / Modèle** | `accessories.tpl` ou spécifique au thème | Contrôle la mise en page visuelle (grille, carrousel, liste). Choisir en fonction du thème et du hook. |
| | **Paramètres du carrousel (Lecture automatique, Boucle, Articles par vue, Navigation)** | Varie, souvent activé | Contrôle le comportement des affichages carrousel. Ajuster pour l'expérience utilisateur. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Mes produits associés n'apparaissent pas sur le front office.**

-   **R :** Tout d'abord, assurez-vous que le module est activé et configuré. Vérifiez que vous avez bien *attribué* le bloc de produits associés aux produits ou catégories spécifiques que vous consultez. Vérifiez également que l'« Emplacement d'affichage (Hook) » que vous avez sélectionné est réellement rendu par votre thème sur la page produit. Enfin, videz votre cache PrestaShop (Paramètres avancés > Performances > Vider le cache).

**Q2 : Les produits associés ont une apparence étrange ou ne correspondent pas au design de mon thème.**

-   **R :** Il s'agit souvent d'un conflit de style avec votre thème personnalisé.
    -   **Solution 1 :** Essayez différentes options de « Type d'affichage / Modèle » dans la configuration du module. Certains modèles sont conçus pour des thèmes populaires spécifiques (par exemple, `panda-blocksProductsCart.tpl`).
    -   **Solution 2 :** Videz le cache de votre navigateur et le cache Smarty de PrestaShop (Paramètres avancés > Performances).
    -   **Solution 3 :** Si le problème persiste, des ajustements CSS personnalisés pourraient être nécessaires. C'est une tâche pour un webmaster ou un développeur (voir Section 7.5).

**Q3 : Puis-je avoir plusieurs blocs de produits associés sur la même page produit ?**

-   **R :** Oui ! Le module est conçu pour cela. Vous pouvez créer plusieurs blocs de produits associés distincts, chacun avec ses propres produits, son type d'affichage et son emplacement (hook) attribué. Assurez-vous simplement de les placer dans des hooks différents pour éviter les chevauchements.

**Q4 : Comment traduire le texte du module (par exemple, « Produits associés ») dans d'autres langues ?**

-   **R :** Allez dans **International > Traductions** dans votre Back Office PrestaShop. Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez « Related Products Pro » dans la liste déroulante des modules. Vous pourrez alors modifier les chaînes de texte pour chaque langue.

**Q5 : Le carrousel ne fonctionne pas ou les produits sont empilés verticalement.**

-   **R :** Cela indique généralement un conflit JavaScript ou une bibliothèque JS manquante.
    -   **Solution 1 :** Assurez-vous que votre thème est à jour.
    -   **Solution 2 :** Videz votre cache PrestaShop et le cache de votre navigateur.
    -   **Solution 3 :** Vérifiez les erreurs de console dans les outils de développement de votre navigateur (F12). Si vous voyez des erreurs JavaScript, cela peut indiquer un conflit avec un autre module ou votre thème. Cela nécessiterait l'intervention d'un développeur.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse technique approfondie du module « Related Products Pro » pour les développeurs, les webmasters et les agences techniques.

### 4.1 Aperçu de l'architecture

Le module « Related Products Pro » (`ppb`) suit une architecture de module PrestaShop standard, exploitant principalement la classe `Module` pour sa fonctionnalité principale. Il se concentre sur l'extension de l'expérience de la page produit du front-office en injectant des listes de produits personnalisées dans divers hooks d'affichage. Le module gère sa configuration et les données des produits associés directement dans la méthode `getContent()` du fichier `index.php`, qui gère à la fois le rendu du formulaire et la persistance des données. Il utilise un système de templating personnalisé pour un affichage front-office flexible, y compris des modèles spécifiques pour les thèmes populaires. Les ressources JavaScript et CSS sont chargées de manière conditionnelle pour améliorer l'interface utilisateur et fournir la fonctionnalité de carrousel.

### 4.2 Contrôleurs (`controllers/`)

Le module ne semble pas utiliser de classes `ModuleFrontController` ou `AdminController` dédiées. Tout le rendu du front-office est géré via des hooks, et la configuration du back-office est gérée dans la méthode `getContent()` du fichier `index.php` principal.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne définit pas de classes personnalisées étendant `ObjectModel` dans un répertoire `classes/` dédié. La persistance des données pour les configurations de produits associés est probablement gérée directement via `Configuration::updateValue()` ou des tables de base de données personnalisées gérées dans le fichier `index.php` principal.

### 4.4 Ressources JavaScript (`views/js/`)

-   **`ppb/lib/searchTool/views/js/autocomplete.js`** :
    -   **Portée :** Back-office.
    -   **Responsabilité :** Fournit la fonctionnalité d'autocomplétion pour les champs de sélection de produits dans les formulaires de configuration du module, probablement pour la sélection manuelle de produits spécifiques à inclure ou à attribuer. Il écoute la saisie de l'utilisateur dans les champs de texte et suggère des produits basés sur des correspondances partielles.
-   **`ppb/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`** :
    -   **Portée :** Back-office.
    -   **Responsabilité :** Fait probablement partie d'un utilitaire générique pour la gestion des modèles Smarty au sein de l'interface d'administration. Il pourrait gérer le chargement dynamique, la sauvegarde ou la prévisualisation du code de modèle, éventuellement utilisé pour des fonctionnalités de création ou de modification de modèles personnalisés au sein du module.
-   **`ppb/lib/src/js/lightslider.js`** :
    -   **Portée :** Front-office.
    -   **Responsabilité :** Il s'agit d'une bibliothèque tierce pour la création de carrousels de contenu réactifs. Elle se lie à des éléments HTML spécifiques (probablement `<ul>` ou `<div>` avec une classe désignée) pour les transformer en un curseur. Elle gère les événements tactiles/de balayage, la navigation, la lecture automatique et les ajustements réactifs.
-   **`ppb/views/admin/ppb.js`** :
    -   **Portée :** Back-office.
    -   **Responsabilité :** Contient la logique JavaScript principale pour la page de configuration du Back Office du module. Cela inclurait les écouteurs d'événements pour les soumissions de formulaires, les mises à jour dynamiques des paramètres basées sur les choix de l'utilisateur (par exemple, afficher/masquer les options du carrousel), les appels AJAX pour la sauvegarde des données et potentiellement la gestion de la liste des blocs de produits associés.
-   **`ppb/views/admin/ppb8.js`** :
    -   **Portée :** Back-office.
    -   **Responsabilité :** Similaire à `ppb.js`, mais contient probablement des adaptations spécifiques ou des fonctionnalités supplémentaires pour les environnements PrestaShop 8.x, traitant des changements d'API ou des différences d'interface utilisateur dans les versions plus récentes de PrestaShop.
-   **`ppb/views/js/accessories.js`** :
    -   **Portée :** Front-office.
    -   **Responsabilité :** Contient le JavaScript spécifique au front-office pour les blocs de produits associés. Cela pourrait inclure la logique d'initialisation du carrousel `lightslider.js`, la gestion des clics sur les produits ou toute interaction dynamique au sein des listes de produits associés affichées.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`ppb/css.css`** :
    -   **Portée :** Front-office et Back-office.
    -   **Responsabilité :** Style général à l'échelle du module. Pourrait contenir des styles de base pour les blocs de produits associés ou des éléments communs utilisés dans tout le module.
-   **`ppb/lib/searchTool/views/css/autocomplete.css`** :
    -   **Portée :** Back-office.
    -   **Responsabilité :** Styles pour les listes déroulantes d'autocomplétion et les champs de saisie utilisés dans l'outil de sélection de produits de l'administration.
-   **`ppb/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`** :
    -   **Portée :** Back-office.
    -   **Responsabilité :** Style pour l'interface de gestion des modèles Smarty dans la configuration du module.
-   **`ppb/lib/src/css/lightslider.css`** :
    -   **Portée :** Front-office.
    -   **Responsabilité :** Style principal pour le carrousel `lightslider.js`, définissant sa structure, ses flèches de navigation, ses points et son comportement réactif. Les développeurs peuvent remplacer ces styles pour correspondre à leur thème.
-   **`ppb/views/admin/ppb.css`** :
    -   **Portée :** Back-office.
    -   **Responsabilité :** Style spécifique pour la page de configuration du module dans le panneau d'administration de PrestaShop, garantissant une bonne intégration avec l'interface utilisateur du back-office de PrestaShop.
-   **`ppb/views/css/ppb-table.css`** :
    -   **Portée :** Front-office.
    -   **Responsabilité :** Style pour les listes de produits associés affichées sous forme de tableau, probablement utilisé pour des modèles spécifiques de « liste-tableau ».
-   **`ppb/views/css/ppb.css`** :
    -   **Portée :** Front-office.
    -   **Responsabilité :** Style principal du front-office pour les blocs de produits associés, y compris les mises en page des fiches produits, l'espacement et l'apparence générale.
-   **`ppb/views/css/ppbcarousell.css`** :
    -   **Portée :** Front-office.
    -   **Responsabilité :** Style supplémentaire ou spécifique pour l'affichage carrousel des produits associés, potentiellement en surchargeant ou en étendant `lightslider.css` pour une esthétique de module personnalisée.
-   **`ppb/views/css/ppb_custom.css`** :
    -   **Portée :** Front-office.
    -   **Responsabilité :** Probablement destiné au CSS personnalisé défini par l'utilisateur ou aux surcharges spécifiques au thème pour ajuster l'apparence des blocs de produits associés sans modifier les fichiers principaux du module.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module fournit un riche ensemble de modèles, dont beaucoup sont adaptés à des hooks spécifiques et à des thèmes PrestaShop populaires.

-   **`ppb/lib/searchTool/views/scripts.tpl`** :
    -   **Portée :** Back-office.
    -   **Objectif :** Contient l'initialisation ou la configuration JavaScript pour l'outil de recherche d'autocomplétion utilisé dans l'administration.
-   **`ppb/lib/smartyTemplatesManager/tpl/example.tpl`** :
    -   **Portée :** Back-office.
    -   **Objectif :** Un exemple de modèle, probablement utilisé comme référence ou pour démontrer les capacités du gestionnaire de modèles Smarty.
-   **`ppb/lib/smartyTemplatesManager/views/buttonManager.tpl`** :
    -   **Portée :** Back-office.
    -   **Objectif :** Rend les boutons ou les contrôles pour la gestion des modèles dans l'interface d'administration.
-   **`ppb/lib/smartyTemplatesManager/views/createTemplateForm.tpl`** :
    -   **Portée :** Back-office.
    -   **Objectif :** Rend le formulaire pour la création de nouveaux modèles d'affichage personnalisés pour les produits associés.
-   **`ppb/lib/smartyTemplatesManager/views/editTemplateForm.tpl`** :
    -   **Portée :** Back-office.
    -   **Objectif :** Rend le formulaire pour la modification des modèles d'affichage personnalisés existants.
-   **`ppb/lib/smartyTemplatesManager/views/mainForm.tpl`** :
    -   **Portée :** Back-office.
    -   **Objectif :** Le formulaire principal du gestionnaire de modèles Smarty, listant probablement les modèles et fournissant des options.
-   **`ppb/lib/smartyTemplatesManager/views/selectInput.tpl`** :
    -   **Portée :** Back-office.
    -   **Objectif :** Rend un champ de sélection déroulant, éventuellement utilisé pour choisir des modèles ou d'autres options.
-   **`ppb/views/templates/admin/tabs.tpl`** :
    -   **Portée :** Back-office.
    -   **Objectif :** Rend la structure de navigation par onglets pour la page de configuration du module, si elle utilise plusieurs onglets pour différents paramètres.
-   **Modèles de hook (`views/templates/hook/`)** : Ces modèles sont rendus sur la page produit du front-office via divers hooks PrestaShop. Beaucoup sont spécifiques au thème pour assurer une intégration optimale.

    -   **`accessories.tpl`** :
        -   **Hook :** Configurable, souvent `displayProductExtraContent` ou `displayProductFooter`.
        -   **Sortie :** Un modèle générique pour l'affichage des produits associés, généralement dans une grille ou un carrousel.
    -   **`blocksProductsCart.tpl`** :
        -   **Hook :** Configurable, souvent `displayProductExtraContent` ou `displayProductFooter`.
        -   **Sortie :** Un bloc de produits, potentiellement stylisé pour une apparence de panier ou pour des recommandations générales de produits.
    -   **`blocksProductsOrder.tpl`** :
        -   **Hook :** Configurable.
        -   **Sortie :** Similaire à `blocksProductsCart.tpl`, mais pourrait être stylisé pour un contexte ou une mise en page différente.
    -   **`custom-pictures-only.tpl`** :
        -   **Hook :** Configurable.
        -   **Sortie :** Un affichage minimaliste montrant uniquement les images des produits, idéal pour les espaces compacts ou la navigation visuelle.
    -   **`panda-blocksProductsCart.tpl`**, **`panda-blocksProductsOrder.tpl`**, **`panda-ProductExtraContent.tpl`**, **`panda-productFooter.tpl`**, **`panda-productTab.tpl`**, **`panda-productTabContent.tpl`** :
        -   **Hook :** Configurable, conçu pour le thème Panda.
        -   **Sortie :** Modèles spécifiques au thème assurant une intégration et un style transparents avec le langage de conception du thème Panda. Ils rendront les produits associés dans les zones spécifiées du thème Panda (par exemple, contenu supplémentaire du produit, pied de page ou onglets dédiés).
    -   **`ProductExtraContent.tpl`** :
        -   **Hook :** `displayProductExtraContent`.
        -   **Sortie :** Rend les produits associés dans le hook `displayProductExtraContent`, généralement une zone proéminente près des détails principaux du produit.
    -   **`productFooter.tpl`** :
        -   **Hook :** `displayProductFooter`.
        -   **Sortie :** Rend les produits associés en bas de la page produit.
    -   **`productTab.tpl`** :
        -   **Hook :** Configurable, souvent `displayProductButtons` ou `displayProductExtraContent` (pour ajouter un nouvel onglet).
        -   **Sortie :** Rend l' *en-tête de l'onglet* pour un onglet dédié « Produits associés » sur la page produit.
    -   **`productTabContent.tpl`** :
        -   **Hook :** Configurable, souvent `displayProductContent` ou `displayProductExtraContent` (pour ajouter du contenu pour un nouvel onglet).
        -   **Sortie :** Rend le *contenu* pour un onglet dédié « Produits associés », apparaissant lorsque l'en-tête `productTab.tpl` est cliqué.
    -   **`table-list.tpl`** :
        -   **Hook :** Configurable.
        -   **Sortie :** Affiche les produits associés dans un format tabulaire, potentiellement utile pour comparer des fonctionnalités ou pour une liste plus structurée.
    -   **`warehouse-blocksProductsCart.tpl`**, **`warehouse-blocksProductsOrder.tpl`**, etc. (tous les modèles préfixés par `warehouse-`) :
        -   **Hook :** Configurable, conçu pour le thème Warehouse.
        -   **Sortie :** Modèles spécifiques au thème Warehouse, assurant une intégration correcte du style et de la mise en page.
    -   **`zone-blocksProductsCart.tpl`**, **`zone-blocksProductsOrder.tpl`**, etc. (tous les modèles préfixés par `zone-`) :
        -   **Hook :** Configurable, conçu pour le thème Zone.
        -   **Sortie :** Modèles spécifiques au thème Zone, assurant une intégration correcte du style et de la mise en page.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** : Le module stocke probablement ses données de configuration (définitions des blocs de produits associés, produits attribués, paramètres d'affichage) dans des tables de base de données personnalisées créées lors de l'installation, ou il pourrait fortement s'appuyer sur `ps_configuration` pour des paramètres plus simples. Compte tenu de la complexité des multiples listes de produits associés, des tables personnalisées sont plus probables. Les développeurs devraient inspecter la méthode `install()` dans `ppb/index.php` pour les appels `Db::getInstance()->execute()` afin d'identifier la création de tables.

    -   **Tables probables (hypothétiques basées sur la fonctionnalité) :**
        -   `ps_ppb_blocks` : Stocke la définition principale de chaque bloc de produits associés (ID, nom, hook, type d'affichage, etc.).
        -   `ps_ppb_block_products` : Une table de relation plusieurs-à-plusieurs liant les blocs de produits associés aux produits qu'ils doivent afficher.
        -   `ps_ppb_block_assignments` : Une table de relation plusieurs-à-plusieurs liant les blocs de produits associés aux pages produits sur lesquelles ils doivent apparaître.
        -   `ps_ppb_block_categories` : Une table pour stocker les attributions de catégories pour la sélection ou l'attribution dynamique de produits.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Utilisé pour charger les ressources CSS et JavaScript (par exemple, `lightslider.js`, `ppb.css`) de manière conditionnelle uniquement sur les pages produits ou globalement. |
| `displayRightColumnProduct` | Dans la colonne de droite de la page produit. | Rend les blocs de produits associés dans la barre latérale droite. |
| `displayLeftColumnProduct` | Dans la colonne de gauche de la page produit. | Rend les blocs de produits associés dans la barre latérale gauche. |
| `displayProductExtraContent` | Un hook flexible souvent trouvé près de la description/image du produit. | Un hook courant et fortement recommandé pour injecter des blocs de produits associés directement dans la zone de contenu principal. |
| `displayProductFooter` | En bas de la page produit, avant le pied de page général. | Rend les blocs de produits associés dans une section dédiée à la fin du contenu de la page produit. |
| `displayProductButtons` | Près du bouton Ajouter au panier ou des actions du produit. | Pourrait être utilisé pour ajouter un en-tête d'onglet « Produits associés ». |
| `displayProductContent` | Dans la zone de contenu principal du produit. | Pourrait être utilisé pour rendre le contenu d'un onglet « Produits associés ». |
| `displayFooter` | Dans le pied de page global de la boutique. | Moins courant pour les produits associés, mais possible pour des recommandations très larges. |
| `actionProductUpdate` | Après la mise à jour d'un produit dans le Back Office. | Potentiellement utilisé pour vider le cache ou réindexer les données des produits associés si des listes dynamiques sont utilisées. |
| `actionProductDelete` | Après la suppression d'un produit. | Pour nettoyer toutes les attributions de produits associés impliquant le produit supprimé. |
| `actionCategoryUpdate` | Après la mise à jour d'une catégorie. | Pour réévaluer les listes de produits associés qui dépendent des sélections de catégories. |
| `actionCategoryDelete` | Après la suppression d'une catégorie. | Pour nettoyer les attributions de produits associés impliquant la catégorie supprimée. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant le module « Related Products Pro ».
