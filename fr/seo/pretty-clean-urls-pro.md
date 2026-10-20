---
title: "Pretty / Clean URLs PRO - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Pretty / Clean URLs PRO par MyPresta.eu."
sidebar:
  label: "Pretty / Clean URLs PRO - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Pretty / Clean URLs PRO sur MyPresta.eu](https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/seo/pretty-clean-urls-pro/)
>
> ---


# Pretty / Clean URLs PRO

## 1. Exigences et Compatibilité

-   **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.0.0 - 1.7.4.x, 1.7.5.0 - 1.7.7.x, 1.7.8.x, 8.x, 9.x
-   **Compatibilité PHP** : PHP 5.6 - 8.5
-   **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL). Votre serveur doit également avoir `mod_rewrite` activé pour Apache ou une fonctionnalité de réécriture d'URL équivalente pour Nginx, ce qui est standard pour la plupart des installations PrestaShop.
-   **URL simplifiées PrestaShop** : L'option native "URL simplifiée" de PrestaShop (disponible sous **Paramètres de la boutique > SEO & URLs**) *doit être activée* pour que ce module fonctionne correctement. Ce module améliore la fonctionnalité native de PrestaShop, il ne la remplace pas.

## 2. Guide de configuration complet

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à la page de configuration principale de « Pretty / Clean URLs PRO ». C'est ici que vous contrôlez le comportement principal du module.

**Paramètres généraux**

-   **Activer les URL simplifiées :**
    -   **Ce que fait ce paramètre :** C'est l'interrupteur principal du module. Il contrôle si le module génère et utilise activement des URL propres dans toute votre boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Le module commencera à générer et à rediriger vers des URL propres pour tous les types de pages pris en charge (produits, catégories, CMS, etc.).
        -   *Lorsqu'il est désactivé :* Le module sera inactif et PrestaShop reviendra à sa structure d'URL par défaut (qui peut inclure des ID).
    -   **Valeur recommandée :** **OUI** (C'est la fonction principale du module).
    -   **Scénario/exemple pour le marchand :** Vous venez d'installer le module et souhaitez activer ses avantages SEO. Vous activeriez ce paramètre. Si vous avez besoin de dépanner temporairement ou de revenir au comportement par défaut de PrestaShop, vous pourriez le désactiver.
-   **Supprimer les ID des URL :**
    -   **Ce que fait ce paramètre :** Cette option contrôle spécifiquement si l'ID numérique (par exemple, `123` dans `votreboutique.com/123-mon-produit`) est supprimé des URL.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Les URL seront plus courtes et plus propres, comme `votreboutique.com/mon-produit`. C'est généralement mieux pour le SEO et l'esthétique.
        -   *Lorsqu'il est désactivé :* Les URL resteront « jolies » mais conserveront l'ID, par exemple, `votreboutique.com/123-mon-produit`. Cela pourrait être utile si vous avez des systèmes externes qui dépendent de la présence de l'ID dans l'URL, bien que ce soit moins courant.
    -   **Valeur recommandée :** **OUI** (Pour un maximum d'avantages SEO et une esthétique propre).
    -   **Scénario/exemple pour le marchand :** Vous voulez les URL les plus propres possibles pour un meilleur indexage par les moteurs de recherche et une meilleure lisibilité pour l'utilisateur. Vous activeriez ceci.
-   **Redirection automatique 301 :**
    -   **Ce que fait ce paramètre :** Ce paramètre critique indique au module de créer automatiquement des redirections permanentes 301 des anciennes URL basées sur des ID vers les nouvelles URL propres.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Tout visiteur ou robot de moteur de recherche essayant d'accéder à une ancienne URL (par exemple, une qui a été indexée avant que le module ne soit actif) sera redirigé de manière transparente vers la nouvelle URL propre. Cela évite les erreurs 404 et préserve votre capital de liens SEO.
        -   *Lorsqu'il est désactivé :* Les anciennes URL mèneront à des erreurs 404 « Page non trouvée », ce qui est mauvais pour l'expérience utilisateur et peut gravement nuire à votre SEO.
    -   **Valeur recommandée :** **OUI** (Absolument essentiel pour maintenir le SEO et l'expérience utilisateur pendant et après la transition vers des URL propres).
    -   **Scénario/exemple pour le marchand :** Vous venez d'activer le module sur une boutique existante avec de nombreuses pages indexées. L'activation de ceci garantit que tous vos anciens liens continuent de fonctionner et transmettent leur valeur SEO aux nouveaux liens.
-   **Forcer le slash final :**
    -   **Ce que fait ce paramètre :** Détermine si un slash final (`/`) est toujours ajouté à la fin de vos URL (par exemple, `votreboutique.com/categorie/` vs `votreboutique.com/categorie`).
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Toutes les URL générées se termineront par un slash. Cela peut aider à la cohérence des URL et certains outils SEO le préfèrent.
        -   *Lorsqu'il est désactivé :* Les URL ne se termineront pas nécessairement par un slash, selon le comportement par défaut de PrestaShop pour ce type de page.
    -   **Valeur recommandée :** **OUI** (Pour la cohérence et pour éviter les problèmes potentiels de contenu dupliqué si les moteurs de recherche traitent `url` et `url/` comme des pages différentes).
    -   **Scénario/exemple pour le marchand :** Vous voulez vous assurer que toutes vos URL de catégorie et de page CMS se terminent systématiquement par un slash pour une meilleure gestion SEO et pour éviter les problèmes potentiels de contenu dupliqué.
-   **Supprimer l'extension .html :**
    -   **Ce que fait ce paramètre :** Cette option contrôle si l'extension `.html` est supprimée des URL des pages produit et CMS.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Les URL seront encore plus courtes, par exemple, `votreboutique.com/mon-produit` au lieu de `votreboutique.com/mon-produit.html`. C'est généralement préféré pour la conception web moderne et le SEO.
        -   *Lorsqu'il est désactivé :* Les URL des pages produit et CMS conserveront l'extension `.html`.
    -   **Valeur recommandée :** **OUI** (Pour la structure d'URL la plus propre et la plus moderne).
    -   **Scénario/exemple pour le marchand :** Vous voulez que vos pages produit ressemblent à `votreboutique.com/mon-produit` au lieu de `votreboutique.com/mon-produit.html` pour une apparence plus élégante et un meilleur SEO.

**Bouton Enregistrer :**

-   Cliquez toujours sur le bouton « Enregistrer » après avoir effectué des modifications pour les appliquer à votre boutique.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Ce module fonctionne principalement en surchargeant les classes et contrôleurs PrestaShop pour modifier la génération et le routage des URL. Bien qu'il n'introduise pas un nouvel élément de menu dédié dans le Back Office pour gérer une liste d'« URL simplifiées », il s'intègre directement aux fonctionnalités existantes de PrestaShop.

**Intégration `AdminProductsController` (Back Office > Catalogue > Produits)**

-   **Nom de l'écran et emplacement du menu :** **Catalogue > Produits**
-   **Actions et paramètres disponibles :**
    -   Lorsque vous modifiez ou créez un produit, le module influence le comportement du champ « URL simplifiée ». Au lieu de vous obliger à supprimer manuellement les ID ou à assurer une structure propre, la logique du module générera et suggérera automatiquement une URL propre et sans ID basée sur le nom de votre produit et les paramètres du module.
    -   Le module garantit que lorsque vous enregistrez un produit, son URL est générée conformément aux paramètres de votre module « Pretty / Clean URLs PRO » (par exemple, pas d'ID, pas d'extension `.html` si configuré).
-   **Effet des modifications :**
    -   Lorsque vous enregistrez un produit, l'URL générée et utilisée par PrestaShop reflétera la structure d'URL propre définie dans la configuration du module.
    -   Si vous modifiez le nom d'un produit, le module vous aidera à garantir que l'URL simplifiée est mise à jour proprement.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    -   Continuez à gérer vos produits comme d'habitude sous **Catalogue > Produits**. Le module fonctionne en arrière-plan pour garantir que les URL sont optimisées.
    -   Lors de la création ou de la modification de produits, assurez-vous que les noms de vos produits sont descriptifs, car ils sont utilisés pour générer les URL simplifiées.
    -   Vous pouvez toujours ajuster manuellement le champ « URL simplifiée » pour un produit si vous avez besoin d'une URL spécifique, mais la logique du module guidera la génération initiale.

**Autres contrôleurs d'administration (intégration implicite)**

Le module affecte également implicitement d'autres zones où les URL sont générées, telles que :

-   **Catalogue > Catégories** : Lors de la création ou de la modification de catégories.
-   **Catalogue > Marques** : Lors de la création ou de la modification de marques.
-   **Catalogue > Fournisseurs** : Lors de la création ou de la modification de fournisseurs.
-   **Design > Pages (CMS)** : Lors de la création ou de la modification de pages CMS.

Dans tous ces cas, le module garantit que les URL simplifiées générées par PrestaShop adhèrent aux paramètres de « Pretty / Clean URLs PRO », en supprimant les ID et les extensions comme configuré.

### 2.3 Intégration des paramètres SEO et URL de PrestaShop

Le module "Pretty / Clean URLs PRO" à partir de la version 2.8.3 et supérieure possède sa propre section dédiée à la définition des schémas d'URL, ce qui rend inutile la configuration manuelle de ces paramètres dans la section native de PrestaShop **Paramètres de la boutique > SEO & URLs**. Cependant, il est crucial de comprendre l'interaction.

:::caution Note importante
Bien que le module gère le schéma d'URL, l'option native **URL simplifiée** de PrestaShop sous **Paramètres de la boutique > SEO & URLs** *doit être activée* pour que le module fonctionne. Le module améliore cette fonctionnalité de base de PrestaShop.
:::

**Schéma des URL (géré par le module)**

Historiquement, les utilisateurs de PrestaShop définissaient les modèles d'URL (routes) pour les produits, les catégories, les pages CMS, etc., dans la section **Paramètres de la boutique > SEO & URLs**. Le module "Pretty / Clean URLs PRO" prend désormais cette responsabilité en charge, vous permettant de les configurer directement depuis sa propre page de configuration.

Le module garantit que les routes sont définies pour supprimer `{id}` des URL, ce qui est essentiel pour des URL vraiment propres. Si, pour une raison quelconque, vous constatez que les routes dans **Paramètres de la boutique > SEO & URLs** contiennent toujours `{id}` après l'installation et la configuration du module, cela pourrait indiquer un problème avec les surcharges du module (voir la section 6 pour le dépannage).

Pour référence, voici les structures de route recommandées que le module vise à implémenter :

| Type de route          | Valeur PrestaShop par défaut (Exemple) | Valeur souhaitée du module (Propre) |
| :--------------------- | :------------------------------------- | :---------------------------------- |
| Route vers le produit  | `{category:/}{id}-{rewrite}{-:ean13}.html` | `{category:/}{rewrite}.html` (ou `{rewrite}.html`) |
| Route vers la catégorie | `{id}-{rewrite}`                       | `{parent_categories:/}{rewrite}/` (ou `{rewrite}/`) |
| Route vers le fournisseur | `{id}__{rewrite}`                      | `supplier/{rewrite}/`               |
| Route vers le fabricant | `{id}_{rewrite}`                       | `manufacturer/{rewrite}/`           |
| Route vers la page CMS | `content/{id}-{rewrite}`               | `info/{rewrite}.html`               |
| Route vers la page de catégorie CMS | `content/category/{id}-{rewrite}` | `info/{rewrite}`                    |

:::tip Environnement multistore
Si vous utilisez un PrestaShop Multistore, n'oubliez pas de vérifier et, si nécessaire, d'ajuster les paramètres du schéma d'URL pour chaque boutique individuelle. Vous pouvez sélectionner la boutique que vous souhaitez configurer à partir du menu contextuel de la boutique dans votre Back Office.
:::

### 2.4 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Config du module | Activer les URL simplifiées | OUI | Active/désactive la fonctionnalité principale du module. |
| Config du module | Supprimer les ID des URL | OUI | Supprime les ID numériques des URL (par exemple, `123-produit` devient `produit`). |
| Config du module | Redirection automatique 301 | OUI | Redirige les anciennes URL basées sur des ID vers de nouvelles URL propres, préservant le SEO. |
| Config du module | Forcer le slash final | OUI | Garantit que toutes les URL se terminent par un `/` pour la cohérence et le SEO. |
| Config du module | Supprimer l'extension .html | OUI | Supprime `.html` des URL des pages produit/CMS pour des liens plus propres. |
| Catalogue > Produits (Modifier) | Champ URL simplifiée | Auto-généré | Le module influence la génération automatique d'URL propres pour les produits. |
| Catalogue > Catégories (Modifier) | Champ URL simplifiée | Auto-généré | Le module influence la génération automatique d'URL propres pour les catégories. |
| Design > Pages (Modifier) | Champ URL simplifiée | Auto-généré | Le module influence la génération automatique d'URL propres pour les pages CMS. |
| Paramètres de la boutique > SEO & URLs | URL simplifiée | OUI | **CRITIQUE :** Doit être activé pour que le module fonctionne. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Après l'installation, mes URL sont toujours les mêmes, ou j'obtiens des erreurs 404.**

-   **R :** Tout d'abord, assurez-vous que « Activer les URL simplifiées » est réglé sur OUI dans la configuration du module.
-   Deuxièmement, allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures).
-   Troisièmement, assurez-vous que l'option native « URL simplifiée » de PrestaShop est activée sous **Paramètres de la boutique > SEO & URLs**. Ce module améliore la fonctionnalité native d'URL simplifiée de PrestaShop, il ne la remplace pas entièrement.
-   Enfin, vérifiez le fichier `.htaccess` de votre serveur (si vous utilisez Apache) ou la configuration Nginx. Le module s'appuie sur la réécriture d'URL côté serveur (mod_rewrite pour Apache) pour fonctionner correctement. Si vous n'êtes pas sûr, contactez votre hébergeur.

**Q2 : Mon thème personnalisé présente des problèmes d'affichage étranges après l'activation du module.**

-   **R :** Ce module affecte principalement la génération et la redirection des URL, et non l'affichage visuel. Il est peu probable qu'il cause directement des problèmes d'affichage du thème. Cependant, si vous avez vidé le cache, le CSS ou le JS de votre thème pourrait avoir besoin d'être rechargé. Essayez de vider le cache de votre navigateur. Si le problème persiste, il pourrait s'agir d'un conflit avec un autre module ou une modification de thème personnalisée. Désactivez temporairement « Pretty / Clean URLs PRO » pour voir si le problème se résout. Si c'est le cas, contactez le support MyPresta.eu.

**Q3 : Ce module fonctionnera-t-il avec mes URL personnalisées ou mes redirections existantes ?**

-   **R :** Le module se concentre sur la génération d'URL propres pour les entités PrestaShop principales (produits, catégories, CMS, etc.). Si vous avez créé manuellement des redirections personnalisées ou des URL simplifiées spécifiques en dehors du système standard de PrestaShop, la redirection automatique 301 du module privilégiera ses propres URL propres générées. Il est généralement préférable de laisser le module gérer toutes les URL des entités principales pour la cohérence. Si vous avez des redirections personnalisées très spécifiques, vous devrez peut-être tester leur interaction.

**Q4 : J'ai changé le nom d'un produit, mais l'URL ne s'est pas mise à jour automatiquement.**

-   **R :** Lorsque vous modifiez le nom d'un produit, PrestaShop suggère généralement une nouvelle URL simplifiée. Vous devez enregistrer explicitement le produit pour que les modifications prennent effet et pour que le module traite la nouvelle URL. Si le champ d'URL simplifiée ne se met pas à jour automatiquement, vous devrez peut-être cliquer manuellement sur « Générer l'URL » à côté du champ d'URL simplifiée sur la page de modification du produit, puis enregistrer le produit. Le module s'assurera alors que cette nouvelle URL est propre et gérera la redirection depuis l'ancienne.

**Q5 : Ce module affecte-t-il mes URL multilingues ?**

-   **R :** Non, il les améliore ! Le module fonctionne avec les capacités multilingues de PrestaShop. Il générera des URL propres pour chaque langue, en respectant le code de langue dans l'URL (par exemple, `/en/my-product` et `/fr/mon-produit`). Assurez-vous que les noms de vos produits, catégories et pages CMS sont traduits pour chaque langue afin d'obtenir les meilleures URL simplifiées.

**Q6 : Je vois un message d'erreur "le mot-clé {id} est requis pour la route (...)" lorsque j'essaie d'enregistrer les schémas d'URL.**

-   **R :** Cette erreur se produit généralement si les surcharges du module (une partie essentielle de sa fonctionnalité) ne sont pas correctement installées ou sont désactivées dans votre boutique PrestaShop. Le module s'appuie sur ces surcharges pour modifier le comportement de routage d'URL par défaut de PrestaShop, lui permettant de supprimer le `{id}` des routes.
    -   **Solution :**
        1.  **Vérifier les surcharges :** Assurez-vous que le système de surcharge de PrestaShop est activé. Vous pouvez généralement trouver ce paramètre sous **Paramètres avancés > Performances**. Recherchez une option liée à "Désactiver les modules non PrestaShop" ou "Désactiver les surcharges" et assurez-vous qu'elle est définie sur "Non".
        2.  **Réinstaller le module :** Parfois, la réinstallation du module peut résoudre les problèmes de surcharge. Désinstallez le module, videz le cache de votre PrestaShop, puis réinstallez-le.
        3.  **Vérification manuelle des surcharges :** Vérifiez que les fichiers de surcharge du module sont présents dans vos répertoires `override/classes/` et `override/controllers/` (par exemple, `override/classes/Dispatcher.php`, `override/controllers/front/ProductController.php`). S'ils sont manquants, cela indique un problème d'installation.
    -   Si le problème persiste, veuillez contacter le support MyPresta.eu.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Pretty / Clean URLs PRO » fonctionne en surchargeant les classes PrestaShop principales, notamment `Dispatcher` et `Link`, pour modifier la façon dont les URL sont générées et analysées. Il intercepte la logique de routage et de génération d'URL par défaut pour supprimer les ID et les extensions en fonction de ses paramètres de configuration. Le module utilise le système de surcharge de PrestaShop (`/override/`) pour injecter sa logique personnalisée sans modifier directement les fichiers principaux, garantissant ainsi la compatibilité des mises à niveau. Il inclut également une surcharge de contrôleur d'administration pour `AdminProductsController` afin de garantir que la génération d'URL simplifiées dans le back office s'aligne sur les paramètres du module.

### 4.2 Contrôleurs (`controllers/`)

Le module utilise principalement des surcharges de contrôleurs front-office pour modifier la génération et le routage des URL.

-   **Contrôleurs Front-Office** :

    -   `purls/override/controllers/front/CartController.php`
        -   **Nom de la classe et classe parente** : `CartController` (surcharge `CartControllerCore`)
        -   **Responsabilité** : Modifie la génération d'URL pour les liens liés au panier afin de s'assurer qu'ils sont propres et sans ID, le cas échéant.
    -   `purls/override/controllers/front/CmsController.php`
        -   **Nom de la classe et classe parente** : `CmsController` (surcharge `CmsControllerCore`)
        -   **Responsabilité** : Modifie la génération d'URL pour les pages CMS, en supprimant les ID et les extensions `.html` comme configuré.
    -   `purls/override/controllers/front/listing/CategoryController.php`
        -   **Nom de la classe et classe parente** : `CategoryController` (surcharge `CategoryControllerCore`)
        -   **Responsabilité** : Modifie la génération d'URL pour les pages de catégorie, en supprimant les ID et en garantissant des URL propres.
    -   `purls/override/controllers/front/listing/index.php`
        -   **Nom de la classe et classe parente** : Pas un contrôleur direct, probablement un fichier vide ou un espace réservé. L'autoloader de PrestaShop pourrait récupérer d'autres fichiers dans ce répertoire.
        -   **Responsabilité** : Aucune responsabilité directe ; sert de marqueur de répertoire.
    -   `purls/override/controllers/front/listing/ManufacturerController.php`
        -   **Nom de la classe et classe parente** : `ManufacturerController` (surcharge `ManufacturerControllerCore`)
        -   **Responsabilité** : Modifie la génération d'URL pour les pages de fabricant, en supprimant les ID et en garantissant des URL propres.
    -   `purls/override/controllers/front/listing/SupplierController.php`
        -   **Nom de la classe et classe parente** : `SupplierController` (surcharge `SupplierControllerCore`)
        -   **Responsabilité** : Modifie la génération d'URL pour les pages de fournisseur, en supprimant les ID et en garantissant des URL propres.
    -   `purls/override/controllers/front/ProductController.php`
        -   **Nom de la classe et classe parente** : `ProductController` (surcharge `ProductControllerCore`)
        -   **Responsabilité** : Modifie la génération d'URL pour les pages de produit, en supprimant les ID et les extensions `.html` comme configuré.
-   **Contrôleurs d'administration Back-Office** :

    -   `purls/override/controllers/admin/AdminProductsController.php`
        -   **Nom de la classe et classe parente** : `AdminProductsController` (surcharge `AdminProductsControllerCore`)
        -   **Responsabilité** : S'intègre à l'interface de gestion des produits pour garantir que lorsque les URL simplifiées sont générées ou mises à jour dans le back office, elles adhèrent aux paramètres du module (par exemple, suppression des ID). Il modifie probablement la méthode `generateFriendlyUrl` ou une logique similaire.

### 4.3 Classes et modèles principaux (`classes/`)

La logique principale du module réside dans ses surcharges de classe, qui sont fondamentales pour la façon dont PrestaShop gère les URL.

-   `purls/override/classes/Dispatcher.php`
    -   **Nom de la classe et classe parente** : `Dispatcher` (surcharge `DispatcherCore`)
    -   **Interaction avec la base de données** : Aucune directement, mais interagit avec `ps_configuration` pour les paramètres du module.
    -   **Méthodes publiques clés et logique métier** : Cette classe est responsable du routage des requêtes entrantes vers le bon contrôleur et de la génération des URL. La surcharge modifie probablement des méthodes comme `getFriendlyUrl` ou `createUrl` pour supprimer les ID et les extensions, et pour gérer la logique de redirection 301 pour les anciennes URL. C'est le point central de l'analyse et de la génération des URL.
-   `purls/override/classes/Link.php`
    -   **Nom de la classe et classe parente** : `Link` (surcharge `LinkCore`)
    -   **Interaction avec la base de données** : Aucune directement, mais interagit avec `ps_configuration` pour les paramètres du module.
    -   **Méthodes publiques clés et logique métier** : La classe `Link` est utilisée dans tout PrestaShop pour construire des URL pour diverses entités (produits, catégories, CMS, etc.). La surcharge dans ce module modifie des méthodes comme `getProductLink`, `getCategoryLink`, `getCMSLink`, etc., pour générer des URL propres, sans ID et sans extensions `.html` selon la configuration du module. Elle fonctionne en conjonction avec la surcharge `Dispatcher` pour assurer une génération d'URL cohérente.

### 4.4 Actifs JavaScript (`views/js/`)

-   `purls/views/js/purls.js`
    -   **Portée** : Back-office (probablement sur les pages de modification de produit/catégorie/CMS).
    -   **Détails** : Ce script contient probablement une logique côté client pour améliorer le processus de génération d'URL simplifiées dans le Back Office de PrestaShop. Il pourrait :
        -   Écouter les changements dans les noms de produit/catégorie/CMS et mettre à jour automatiquement le champ « URL simplifiée » en fonction des paramètres du module.
        -   Fournir un retour d'information ou une validation en temps réel pour les URL générées.
        -   Potentiellement interagir avec des appels AJAX au serveur pour obtenir des URL simplifiées suggérées.
        -   S'assurer que le bouton « Générer l'URL » (s'il est présent) déclenche la logique du module.

### 4.5 Feuilles de style CSS (`views/css/`)

Aucun fichier CSS personnalisé n'a été trouvé dans l'archive du module, ce qui indique que le module n'introduit pas de nouveaux éléments visuels nécessitant un style spécifique. Il s'appuie sur le style par défaut du Back Office de PrestaShop pour sa page de configuration.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates d'administration (`views/templates/admin/`)** :
    -   `purls/views/purls.tpl`
        -   **Portée** : Back-office, page de configuration du module.
        -   **Détails** : Ce template rend le formulaire de configuration principal du module « Pretty / Clean URLs PRO ». Il contient la structure HTML de tous les paramètres décrits dans la section 4.1, y compris les interrupteurs pour activer/désactiver les fonctionnalités, et le bouton « Enregistrer ». Il utilise les helpers de formulaire et le style standard de PrestaShop.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module ne crée aucune table SQL personnalisée.
    -   Il stocke ses paramètres de configuration dans la table standard `ps_configuration` de PrestaShop. Les clés de configuration suivraient généralement un modèle comme `PURLS_ENABLE`, `PURLS_REMOVE_IDS`, `PURLS_301_REDIRECT`, etc.
-   **Table des hooks enregistrés** :
    Le module fonctionne principalement via des surcharges de classe plutôt que par un enregistrement direct de hooks pour sa fonctionnalité principale. Cependant, il peut interagir implicitement avec des hooks qui déclenchent la génération ou la redirection d'URL.

| Nom du hook | Moment d'exécution | Objectif technique |
| :---------- | :----------------- | :----------------- |
| `displayHeader` | À chaque chargement de page dans le front office, dans la section `<head>`. | Bien qu'il n'enregistre pas directement un élément visuel, les surcharges `Dispatcher` et `Link` du module sont actives pendant le rendu de la page, influençant toutes les URL générées dans l'en-tête (par exemple, les URL canoniques, les sélecteurs de langue). |
| `actionDispatcherBefore` | Avant que le dispatcher ne traite la requête. | La surcharge `Dispatcher` est active à ce stade, permettant au module d'intercepter et de modifier la logique d'analyse et de routage des URL avant que PrestaShop ne détermine quel contrôleur charger. Ceci est crucial pour gérer les redirections 301 depuis les anciennes URL. |
| `actionDispatcherAfter` | Après que le dispatcher a traité la requête. | La surcharge `Dispatcher` peut également être active ici, potentiellement pour le post-traitement ou la journalisation liés à la gestion des URL. |
| `actionProductUpdate` / `actionProductAdd` | Après la mise à jour ou l'ajout d'un produit dans le Back Office. | La surcharge `AdminProductsController` garantit que lorsqu'un produit est enregistré, son URL simplifiée est générée conformément aux paramètres du module. Il s'agit d'une interaction implicite plutôt que d'un enregistrement direct de hook par le module lui-même. |
| `actionCategoryUpdate` / `actionCategoryAdd` | Après la mise à jour ou l'ajout d'une catégorie dans le Back Office. | Similaire aux produits, le module garantit des URL propres pour les catégories. |
| `actionCmsUpdate` / `actionCmsAdd` | Après la mise à jour ou l'ajout d'une page CMS dans le Back Office. | Similaire aux produits, le module garantit des URL propres pour les pages CMS. |

## 5. Support officiel et ressources

Pour les mises à jour officielles, le support technique et toute question concernant le module « Pretty / Clean URLs PRO », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tous les problèmes ou questions que vous pourriez avoir.
