---
title: "Product Extra Tabs Pro - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Product Extra Tabs Pro par MyPresta.eu."
sidebar:
  label: "Product Extra Tabs Pro - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Product Extra Tabs Pro sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-extra-tabs-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/product-extra-tabs-pro/)
>
> ---


# Product Extra Tabs Pro

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont habituellement disponibles sur tout environnement d'hébergement moderne.

## 2. Parcours complet de la configuration (Chaque paramètre regroupé par écran)

Le module « Product Extra Tabs Pro » est principalement configuré directement depuis la page d'édition du produit, vous permettant de gérer les onglets par produit. L'écran de configuration principal du module gère les paramètres globaux.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Pour accéder à la configuration principale, allez dans **Modules > Gestionnaire de modules**, recherchez « Product Extra Tabs Pro », et cliquez sur « Configurer ».

Sur cet écran, vous trouverez des paramètres qui s'appliquent globalement ou définissent le comportement du module dans votre boutique.

-   **Paramètre : Activer l'éditeur TinyMCE pour le contenu des onglets**

    -   **Ce que fait ce paramètre :** Ce commutateur détermine si un éditeur de texte enrichi (TinyMCE, le même éditeur que PrestaShop utilise pour les descriptions de produits) est disponible lorsque vous créez ou modifiez le contenu des onglets.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Vous verrez un éditeur convivial avec des options de formatage (gras, italique, listes, images, liens, etc.) lorsque vous ajoutez du contenu à vos onglets supplémentaires. Cela facilite la création de contenu visuellement attrayant et bien structuré sans connaître le HTML.
        -   *Lorsqu'il est désactivé :* Vous n'aurez qu'une zone de texte brut pour le contenu des onglets. Vous devrez écrire manuellement des balises HTML pour formater votre texte, ce qui est plus complexe pour les utilisateurs non techniques.
    -   **Valeur recommandée :** **OUI**
    -   **Scénario / exemple marchand :** Si vous souhaitez ajouter des images, des vidéos ou du texte stylisé à vos onglets (par exemple, un onglet « Guide des tailles » avec une image, ou un onglet « Garantie » avec des termes clés en gras), activez ceci. Si vous n'avez besoin que de texte brut, vous pouvez le désactiver pour une interface plus simple.
-   **Paramètre : Afficher les onglets globalement (pour tous les produits)**

    -   **Ce que fait ce paramètre :** Cette option vous permet de créer des onglets « globaux » qui apparaissent automatiquement sur *chaque* page produit de votre boutique. C'est utile pour les informations qui s'appliquent universellement, comme les politiques d'expédition générales ou les histoires de marque.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Tous les onglets que vous créez dans l'interface de configuration du module (pas sur les pages produits individuelles) seront affichés sur toutes les pages produits. Vous pouvez ensuite gérer ces onglets globaux depuis la configuration principale du module.
        -   *Lorsqu'il est désactivé :* Les onglets doivent être créés et gérés individuellement pour chaque produit depuis sa page d'édition respective. Les onglets globaux ne seront pas affichés.
    -   **Valeur recommandée :** **OUI** (si vous avez des informations qui s'appliquent à tous les produits, sinon NON).
    -   **Scénario / exemple marchand :** Vous souhaitez ajouter un onglet « Politique de retour » identique pour tous les produits. Activez ceci, créez l'onglet ici, et il apparaîtra sur chaque page produit. Si vous n'avez besoin que d'onglets uniques pour des produits spécifiques, gardez ceci désactivé.
-   **Paramètre : Position d'affichage des onglets**

    -   **Ce que fait ce paramètre :** Ce menu déroulant contrôle l'emplacement d'affichage des onglets supplémentaires sur la page produit.
    -   **Effet de la modification de ce paramètre :**
        -   *Option : `displayProductExtraContent` (Par défaut) :* Les onglets apparaîtront dans la zone de contenu standard du produit, généralement sous les détails principaux du produit, à côté des onglets de description/fiche technique par défaut. C'est la position la plus courante et recommandée.
        -   *Option : `displayFooterProduct` (PrestaShop 1.6 uniquement) :* Les onglets apparaîtront dans la section du pied de page de la page produit. Cela pourrait convenir à des informations moins critiques, supplémentaires.
        -   *Option : `displayRightColumnProduct` (PrestaShop 1.6 uniquement) :* Les onglets apparaîtront dans la colonne de droite de la page produit. C'est moins courant pour les onglets et pourrait dépendre fortement de la mise en page de votre thème.
        -   *Option : `displayLeftColumnProduct` (PrestaShop 1.6 uniquement) :* Les onglets apparaîtront dans la colonne de gauche de la page produit. Similaire à la colonne de droite, c'est moins courant pour les onglets.
    -   **Valeur recommandée :** `displayProductExtraContent`
    -   **Scénario / exemple marchand :** Pour la plupart des boutiques, `displayProductExtraContent` offre la meilleure expérience utilisateur car il regroupe toutes les informations relatives au produit. Si votre thème a une mise en page très spécifique ou si vous souhaitez minimiser l'importance des onglets, vous pouvez expérimenter avec les positions de pied de page ou de colonne (bien que celles-ci soient moins courantes pour les onglets).

#### 2.1.1 Gestion des onglets globaux (si « Afficher les onglets globalement » est activé)

Si vous avez activé « Afficher les onglets globalement », cette section apparaîtra sur la page de configuration du module. Ici, vous pouvez ajouter, modifier ou supprimer des onglets qui s'afficheront sur *toutes* les pages produits.

-   **Bouton Ajouter un nouvel onglet :** Cliquez dessus pour ouvrir un formulaire où vous pouvez définir un nouvel onglet global.
    -   **Titre de l'onglet :** Le texte qui apparaît sur l'onglet lui-même (par exemple, « Infos d'expédition », « Garantie »). Ceci est généralement multilingue.
    -   **Contenu de l'onglet :** Le contenu réel qui apparaît lorsque l'onglet est cliqué. Utilisez l'éditeur TinyMCE si activé. Ceci est également multilingue.
    -   **Actif :** Un commutateur pour activer ou désactiver l'onglet sans le supprimer.
    -   **Position :** Un nombre pour contrôler l'ordre de l'onglet par rapport aux autres onglets globaux. Les nombres inférieurs apparaissent en premier.
-   **Liste des onglets existants :** Un tableau affichant tous vos onglets globaux actuellement configurés.
    -   **Icône Modifier :** Cliquez pour modifier le titre, le contenu ou les paramètres d'un onglet existant.
    -   **Icône Supprimer :** Cliquez pour supprimer définitivement un onglet global.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

La principale façon de gérer les onglets supplémentaires spécifiques aux produits est directement depuis la **page d'édition du produit** dans votre Back Office PrestaShop.

-   **Nom de l'écran et emplacement du menu :**

    1.  Naviguez vers **Catalogue > Produits**.
    2.  Modifiez un produit existant ou créez-en un nouveau.
    3.  Dans l'interface d'édition du produit, recherchez un nouvel onglet ou une nouvelle section intitulée **« Extra Tabs Pro »** (ou similaire, selon votre version de PrestaShop et votre thème).
-   **Actions et paramètres disponibles dans la section « Extra Tabs Pro » sur une page produit :**

    -   **Bouton Ajouter un nouvel onglet :** Cliquez dessus pour créer un nouvel onglet *spécifiquement pour ce produit*.
        -   **Titre de l'onglet :** Saisissez le titre de cet onglet spécifique au produit (par exemple, « Spécifications techniques pour le modèle X »). Ceci est multilingue.
        -   **Contenu de l'onglet :** Saisissez le contenu de cet onglet. L'éditeur TinyMCE sera disponible si activé dans la configuration principale du module. Ceci est multilingue.
        -   **Actif :** Activez/désactivez cet onglet spécifique pour ce produit.
        -   **Position :** Définissez l'ordre d'affichage de cet onglet par rapport aux autres onglets de cette page produit.
    -   **Liste des onglets existants :** Un tableau affichant tous les onglets supplémentaires que vous avez créés pour *ce produit particulier*.
        -   **Icône Modifier :** Modifiez le titre, le contenu ou le statut d'un onglet existant spécifique au produit.
        -   **Icône Supprimer :** Supprimez un onglet de ce produit.
-   **Effet des modifications :**

    -   Lorsque vous ajoutez, modifiez ou supprimez un onglet de la section « Extra Tabs Pro » d'un produit, ces modifications *n'affectent que cette page produit spécifique*.
    -   Le contenu et la visibilité de ces onglets sont immédiatement mis à jour sur la page produit du front office après avoir enregistré vos modifications.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**

    1.  **Identifiez les informations universelles :** Si vous avez des informations qui s'appliquent à TOUS les produits (par exemple, expédition générale, retours, histoire de la marque), utilisez la fonction **onglets globaux** dans la configuration principale du module.
    2.  **Identifiez les informations spécifiques au produit :** Pour les détails uniques à un produit (par exemple, dimensions spécifiques, composition des matériaux, instructions d'utilisation, critiques vidéo), accédez à la **page d'édition du produit individuel** et utilisez la section « Extra Tabs Pro » à cet endroit.
    3.  **Utilisez l'éditeur TinyMCE :** Activez toujours l'éditeur TinyMCE dans la configuration principale du module pour faciliter la création et le formatage du contenu.
    4.  **Vérifiez régulièrement :** Vérifiez périodiquement vos pages produits pour vous assurer que les onglets s'affichent correctement et que le contenu est à jour.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activer l'éditeur TinyMCE | OUI | Fournit un éditeur de texte enrichi pour le contenu des onglets ; formatage plus facile. |
| | Afficher les onglets globalement | NON (ou OUI si nécessaire) | OUI : Les onglets globaux apparaissent sur tous les produits. NON : Les onglets sont spécifiques au produit. |
| | Position d'affichage des onglets | `displayProductExtraContent` | Contrôle l'emplacement des onglets sur la page produit. |
| | **Liste des onglets globaux** | (N/A) | Ajouter/Modifier/Supprimer des onglets qui apparaissent sur TOUTES les pages produits. |
| **Page d'édition du produit** | **Section Extra Tabs Pro** | (N/A) | Ajouter/Modifier/Supprimer des onglets spécifiques au produit actuel. |
| | Titre de l'onglet | (Défini par l'utilisateur) | Le nom visible de l'onglet sur la page produit. |
| | Contenu de l'onglet | (Défini par l'utilisateur) | Les informations affichées lorsque l'onglet est cliqué. |
| | Actif | OUI | Contrôle si l'onglet est visible ou masqué. |
| | Position | (Défini par l'utilisateur) | Détermine l'ordre des onglets sur la page produit. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

-   **Q : Mes nouveaux onglets n'apparaissent pas sur la page produit.**
    -   **R :** Tout d'abord, assurez-vous que l'onglet est marqué comme « Actif » à la fois dans la configuration globale du module (s'il s'agit d'un onglet global) et sur la page produit individuelle (s'il est spécifique au produit). Deuxièmement, videz votre cache PrestaShop : Allez dans **Paramètres avancés > Performances**, et cliquez sur « Vider le cache » en haut à droite. Videz également le cache de votre navigateur.
-   **Q : L'éditeur TinyMCE n'apparaît pas lorsque j'essaie d'ajouter du contenu à un onglet.**
    -   **R :** Allez sur la page de configuration principale du module (**Modules > Gestionnaire de modules > Product Extra Tabs Pro > Configurer**) et assurez-vous que le paramètre « Activer l'éditeur TinyMCE pour le contenu des onglets » est défini sur **OUI**. Enregistrez les modifications et videz le cache.
-   **Q : Mes onglets ont l'air étranges ou ne correspondent pas au style de mon thème.**
    -   **R :** Le module essaie de s'intégrer de manière transparente, mais les thèmes personnalisés peuvent parfois remplacer le style par défaut. Si l'apparence est incorrecte, cela nécessite généralement des ajustements CSS mineurs dans votre thème. Contactez votre webmaster ou le support MyPresta.eu avec des captures d'écran pour obtenir de l'aide.
-   **Q : Puis-je avoir des onglets différents pour différentes langues ?**
    -   **R :** Oui ! Les champs « Titre de l'onglet » et « Contenu de l'onglet » sont multilingues. Lors de l'édition d'un onglet, vous verrez des drapeaux de langue à côté de ces champs. Cliquez sur le drapeau pour passer à une autre langue et saisir le contenu traduit.
-   **Q : Je souhaite afficher un onglet uniquement pour certains produits, pas pour tous.**
    -   **R :** Assurez-vous que le paramètre « Afficher les onglets globalement » dans la configuration principale du module est défini sur **NON**. Ensuite, naviguez vers chaque produit spécifique auquel vous souhaitez ajouter un onglet (**Catalogue > Produits > Modifier le produit > section Extra Tabs Pro**) et créez les onglets à cet endroit.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module `Product Extra Tabs Pro` est conçu comme un module PrestaShop standard, étendant principalement la classe `Module`. Il utilise le système de hooks de PrestaShop pour injecter son contenu dans les pages produits et utilise une table de base de données personnalisée pour stocker les données des onglets. La configuration est gérée via `getContent()` dans le fichier principal du module, et la gestion des onglets spécifiques aux produits est intégrée directement dans la page d'administration des produits via un onglet personnalisé. Il utilise AJAX pour le chargement et l'enregistrement dynamique du contenu.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs front-office ou back-office dédiés dans le répertoire `controllers/`. Tout le rendu front-office est géré via des hooks et des fichiers de template, et la configuration back-office est gérée dans la méthode `getContent()` du fichier principal du module et les appels AJAX.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne définit pas de classes personnalisées dans le répertoire `classes/`. Sa logique principale de gestion des données est intégrée dans le fichier principal du module `extratabspro/ajax_extratabspro.php`.

### 4.4 Actifs JavaScript (`views/js/`)

-   `extratabspro/js/tinymce16.inc.js` :
    -   **Portée :** Back-office.
    -   **Objectif :** Ce fichier contient probablement l'initialisation et la configuration de l'éditeur de texte enrichi TinyMCE, spécifiquement adapté aux environnements PrestaShop 1.6. Il garantit que l'éditeur est chargé et configuré correctement pour les champs de saisie de contenu des onglets.
-   `extratabspro/lib/searchTool/views/js/autocomplete.js` :
    -   **Portée :** Back-office.
    -   **Objectif :** Ce script fait partie d'une bibliothèque d'outils de recherche, probablement utilisée pour la fonctionnalité d'autocomplétion dans un champ de saisie de recherche au sein de l'interface d'administration du module (par exemple, la recherche de produits pour attribuer des onglets, bien que cette fonctionnalité spécifique ne soit pas explicitement mentionnée dans le guide du marchand, c'est un modèle courant pour une telle bibliothèque). Il lie les écouteurs d'événements aux champs de saisie et gère les requêtes AJAX pour les suggestions de recherche.
-   `extratabspro/views/admin/extratabspro.js` :
    -   **Portée :** Back-office (PrestaShop 1.7.x, 8.x, 9.x).
    -   **Objectif :** Il s'agit du fichier JavaScript principal pour l'interface d'administration du module. Il gère :
        -   Les appels AJAX pour l'ajout, la modification, la suppression des onglets globaux.
        -   Les appels AJAX pour l'ajout, la modification, la suppression des onglets spécifiques aux produits sur la page d'édition du produit.
        -   Les mises à jour dynamiques des tableaux de listes d'onglets.
        -   Les écouteurs d'événements pour les soumissions de formulaires, les clics sur les boutons (ajouter/modifier/supprimer), et potentiellement le réordonnancement des onglets par glisser-déposer.
        -   L'intégration avec TinyMCE pour les champs de contenu.
-   `extratabspro/views/admin/extratabspro8.js` :
    -   **Portée :** Back-office (PrestaShop 8.x, 9.x).
    -   **Objectif :** Similaire à `extratabspro.js`, mais contient probablement des adaptations ou des correctifs spécifiques pour les environnements PrestaShop 8.x et 9.x, traitant des changements dans la structure DOM du Back Office ou des API JavaScript. Il exécute les mêmes fonctions principales que `extratabspro.js` mais assure la compatibilité avec les versions plus récentes de PrestaShop.
-   `extratabspro/views/js/extratabspro.js` :
    -   **Portée :** Front-office.
    -   **Objectif :** Ce script gère l'affichage et l'interaction front-end des onglets supplémentaires sur la page produit. Il est probable qu'il :
        -   Initialise le mécanisme de commutation d'onglets (par exemple, onglets jQuery UI, onglets Bootstrap ou logique personnalisée).
        -   Lie les événements de clic aux en-têtes d'onglets pour afficher/masquer le contenu correspondant.
        -   Assure des transitions fluides ou le chargement du contenu.
        -   Peut gérer le comportement réactif des onglets sur différentes tailles d'écran.
-   `extratabspro/views/js/tinymce16.inc.js` : (Duplicata, probablement pour différents contextes ou une omission dans l'empaquetage)
    -   **Portée :** Back-office.
    -   **Objectif :** Identique à celui de `extratabspro/js/`, probablement pour l'initialisation de TinyMCE.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `extratabspro/lib/searchTool/views/css/autocomplete.css` :
    -   **Portée :** Back-office.
    -   **Objectif :** Fournit le style pour la liste déroulante des suggestions d'autocomplétion et les éléments d'interface utilisateur associés de la bibliothèque d'outils de recherche.
-   `extratabspro/views/admin/extratabspro.css` :
    -   **Portée :** Back-office.
    -   **Objectif :** Style les formulaires de configuration du module, les tableaux de listes d'onglets et tous les éléments d'interface utilisateur personnalisés dans le Back Office de PrestaShop, assurant une apparence cohérente.
-   `extratabspro/views/css/extratabspro.css` :
    -   **Portée :** Front-office.
    -   **Objectif :** Fournit le style principal pour les onglets supplémentaires sur la page produit. Cela inclut l'apparence des en-têtes d'onglets, les états des onglets actifs et les zones de contenu. Les développeurs peuvent remplacer ces styles dans le fichier `custom.css` ou `theme.css` de leur thème en ciblant des classes comme `.extratabs-pro-tabs`, `.extratabs-pro-tab-header`, `.extratabs-pro-tab-content`, etc.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :

    -   `extratabspro/views/front/footer.tpl` : Ce template est probablement destiné aux hooks `displayFooter` ou `displayFooterProduct` (bien que le module utilise principalement `displayProductExtraContent`). Il afficherait du contenu dans la zone du pied de page.
    -   `extratabspro/views/front/tab.tpl` : Ce template rend un seul en-tête d'onglet (la partie cliquable). Il est utilisé dans une boucle pour générer tous les en-têtes d'onglets.
    -   `extratabspro/views/front/tab16.tpl` : Une version de `tab.tpl` spécifiquement pour PrestaShop 1.6, s'adaptant à sa structure HTML ou à ses classes CSS différentes.
    -   `extratabspro/views/front/tabcontents.tpl` : Ce template rend la zone de contenu pour tous les onglets supplémentaires. Il contient généralement une boucle qui itère sur le contenu de chaque onglet, l'enveloppant dans un conteneur qui peut être affiché/masqué par JavaScript.
    -   `extratabspro/views/front/tabcontents16.tpl` : Une version de `tabcontents.tpl` spécifiquement pour PrestaShop 1.6.
-   **Templates d'administration (`views/templates/admin/`)** :

    -   `extratabspro/lib/searchTool/views/scripts.tpl` : Ce template inclut probablement les actifs JavaScript et CSS pour la bibliothèque d'outils de recherche dans le contexte d'administration.
    -   `extratabspro/views/admin/tabs-list.tpl` : Ce template rend le tableau qui liste tous les onglets configurés (soit les onglets globaux sur la page de configuration du module, soit les onglets spécifiques au produit sur la page d'édition du produit). Il inclut des contrôles pour l'édition et la suppression des onglets.
    -   `extratabspro/views/admin/tabs17.tpl` : Ce template est le formulaire de configuration principal ou l'affichage du module dans le Back Office de PrestaShop 1.7.x / 8.x / 9.x. Il contient probablement les champs de formulaire pour les paramètres globaux et l'inclusion de `tabs-list.tpl` pour la gestion des onglets.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   `ps_extratabspro_tab` : Stocke les informations principales de chaque onglet supplémentaire (ID, ID produit, position, statut actif).
    -   `ps_extratabspro_tab_lang` : Stocke le contenu multilingue de chaque onglet (titre, contenu), lié à `ps_extratabspro_tab` par `id_extratabspro_tab` et `id_lang`.
    -   `ps_configuration` : Stocke les paramètres globaux du module (par exemple, `EXTRATABSPRO_TINYMCE_ENABLED`, `EXTRATABSPRO_GLOBAL_TABS_ENABLED`, `EXTRATABSPRO_HOOK_POSITION`).
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Injecte les fichiers CSS et JS du module pour l'affichage front-office. |
| `displayBackOfficeHeader` | Dans la section `<head>` des pages du Back Office. | Injecte les fichiers CSS et JS du module pour la configuration du Back Office et l'intégration de la page produit. |
| `displayAdminProductsExtra` | Sur la page d'édition du produit dans le Back Office. | Injecte la section « Extra Tabs Pro » dans l'interface d'administration du produit, permettant la gestion des onglets par produit. |
| `displayProductExtraContent` | Dans la zone de contenu principale de la page produit, généralement sous la description du produit. | Rend les onglets supplémentaires et leur contenu sur la page produit du front-office. C'est le hook principal pour l'affichage front-end. |
| `displayFooterProduct` | Dans la section du pied de page de la page produit. | Hook alternatif pour l'affichage des onglets, si configuré par le marchand. |
| `displayRightColumnProduct` | Dans la colonne de droite de la page produit. | Hook alternatif pour l'affichage des onglets, si configuré par le marchand. |
| `displayLeftColumnProduct` | Dans la colonne de gauche de la page produit. | Hook alternatif pour l'affichage des onglets, si configuré par le marchand. |
| `actionProductUpdate` | Après la mise à jour d'un produit dans le Back Office. | Potentiellement utilisé pour vider le cache ou effectuer d'autres actions liées aux modifications des données du produit. |
| `actionProductDelete` | Après la suppression d'un produit. | Nettoie les onglets spécifiques au produit de la base de données. |
| `actionObjectProductAddAfter` | Après l'ajout d'un nouveau produit. | Potentiellement utilisé pour la configuration initiale ou la création d'onglets par défaut pour les nouveaux produits. |
| `actionObjectProductUpdateAfter` | Après la mise à jour d'un objet produit. | Similaire à `actionProductUpdate`, pour les mises à jour du modèle d'objet. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et toute autre question concernant le module « Product Extra Tabs Pro », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support et nos développeurs sont disponibles pour vous aider.
