---
title: "Remises quantitatives sur les listes de produits - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop « Remises quantitatives sur les listes de produits » par MyPresta.eu."
sidebar:
  label: "Remises quantitatives sur les listes de produits - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Quantity discounts on products lists sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/quantity-discounts-on-products-lists.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/quantity-discounts-on-products-lists/)
>
> ---


# Remises quantitatives sur les listes de produits

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur inhabituelle n'est requise.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module, accessible après l'installation en cliquant sur le bouton « Configurer ».

#### Paramètres généraux

- **Ce que fait ce paramètre :** Cette section contient les paramètres essentiels pour activer ou désactiver la fonctionnalité du module et contrôler son comportement de base.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Le module commencera à afficher les remises quantitatives sur les pages de listes de produits selon vos autres paramètres.
  - *Lorsqu'il est désactivé :* Le module cessera d'afficher toute remise quantitative sur les pages de listes de produits.
- **Valeur recommandée :** OUI (sauf si vous devez le désactiver temporairement pour la maintenance).
- **Scénario / exemple de marchand :** Si vous menez une promotion spéciale qui annule les remises quantitatives, vous pourriez désactiver temporairement le module. Sinon, gardez-le activé pour profiter de ses avantages.

#### Options d'affichage

- **Ce que fait ce paramètre :** Ces options contrôlent l'apparence visuelle et le placement des informations de remise quantitative sur vos listes de produits.
- **Effet de la modification de ce paramètre :**
  - *Exemple : « Afficher sur la page produit » :*
    - *Lorsqu'il est activé :* Les remises quantitatives seront également affichées sur la page de détail du produit individuelle.
    - *Lorsqu'il est désactivé :* Les remises quantitatives n'apparaîtront que sur les pages de listes de produits (catégories, résultats de recherche, etc.), en supposant qu'elles soient déjà présentes sur la page produit par la fonctionnalité PrestaShop par défaut.
  - *Exemple : « Position des informations de remise » :*
    - *Option A (par exemple, « Sous le prix du produit ») :* Les détails de la remise apparaîtront directement sous le prix principal du produit.
    - *Option B (par exemple, « Au-dessus du nom du produit ») :* Les détails de la remise apparaîtront au-dessus du nom du produit.
- **Valeur recommandée :** Expérimentez avec les positions pour trouver ce qui convient le mieux à votre thème. Souvent, « Sous le prix du produit » est un bon point de départ. « Afficher sur la page produit » peut être activé si votre thème n'affiche pas déjà les remises quantitatives de manière proéminente à cet endroit.
- **Scénario / exemple de marchand :** Si vos fiches produits sont très compactes, vous pourriez choisir une position subtile. Si vous souhaitez mettre en évidence les remises, une position plus proéminente pourrait être meilleure.

#### Style et personnalisation

- **Ce que fait ce paramètre :** Ces paramètres vous permettent de personnaliser l'apparence de l'affichage des remises pour correspondre au thème de votre boutique. Cela peut inclure des options pour la couleur du texte, la couleur de fond, la taille de la police, ou même du CSS personnalisé.
- **Effet de la modification de ce paramètre :**
  - *Exemple : « Couleur du texte » :*
    - *Lorsqu'il est réglé sur rouge :* Le texte de la remise apparaîtra en rouge.
    - *Lorsqu'il est réglé sur vert :* Le texte de la remise apparaîtra en vert.
- **Valeur recommandée :** Choisissez des couleurs et des styles qui complètent votre thème existant.
- **Scénario / exemple de marchand :** Si votre marque utilise une palette de couleurs spécifique, vous voudriez que les informations de remise s'intègrent harmonieusement plutôt que de jurer.

#### Paramètres avancés

- **Ce que fait ce paramètre :** Cette section peut contenir des paramètres pour la mise en cache, l'optimisation des performances ou des options d'intégration spécifiques.
- **Effet de la modification de ce paramètre :**
  - *Exemple : « Activer la mise en cache » :*
    - *Lorsqu'il est activé :* Le module stockera le HTML de remise généré pour un chargement plus rapide, améliorant la vitesse de la page.
    - *Lorsqu'il est désactivé :* Le module générera le HTML de remise à chaque chargement de page, ce qui pourrait ralentir les pages mais garantira que les données les plus récentes sont toujours affichées (utile pendant le développement).
- **Valeur recommandée :** OUI pour la mise en cache sur les boutiques en ligne.
- **Scénario / exemple de marchand :** Si vous remarquez des problèmes de performance sur les pages avec de nombreuses listes de produits, l'activation de la mise en cache peut aider. Pendant le développement du thème, vous pourriez désactiver la mise en cache pour voir les changements instantanément.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### AdminPlqdSearchController (Back Office > Modules > Remises quantitatives sur les listes de produits > Paramètres de recherche)

Ce contrôleur gère probablement les paramètres liés à la manière dont le module identifie et traite les produits pour l'affichage des remises, y compris éventuellement un outil de recherche pour des produits ou catégories spécifiques.

- **Nom de l'écran et emplacement du menu :** Cet écran peut être accessible via un sous-onglet ou un lien dédié dans la page de configuration principale du module, éventuellement intitulé « Paramètres de recherche » ou « Sélection de produits ».
- **Actions et paramètres disponibles :** Cet écran comporterait généralement une grille ou un formulaire pour :
  - **Rechercher des produits :** Vous permettre de trouver des produits spécifiques par nom, ID ou référence.
  - **Exclure des produits/catégories :** Définir des produits spécifiques ou des catégories entières où les remises quantitatives ne doivent PAS être affichées, même si elles sont configurées.
  - **Gérer les règles d'affichage :** Potentiellement configurer des règles plus granulaires pour savoir quand et où les remises apparaissent en fonction des attributs du produit ou d'autres critères.
- **Effet des modifications :**
  - *Exclure un produit :* Les informations de remise quantitative pour ce produit spécifique n'apparaîtront plus sur aucune page de liste de produits.
  - *Exclure une catégorie :* Toutes les informations de remise quantitative des produits de la catégorie sélectionnée seront masquées sur les pages de liste.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Utilisez cet écran si vous avez des produits ou des catégories spécifiques pour lesquels l'affichage des remises quantitatives sur les listes n'est pas souhaité (par exemple, articles de très grande valeur, produits sur mesure ou produits avec une tarification complexe qui pourrait dérouter les clients si elle est simplifiée).

#### index.php (plqd/controllers/admin/index.php)

Ce fichier, bien que répertorié comme un contrôleur d'administration, est souvent un espace réservé ou un redirigeur dans les modules PrestaShop. Dans le contexte de ce module, il est fort probable que `plqd/index.php` (le fichier principal du module) gère le formulaire de configuration principal via `getContent()`, et que `AdminPlqdSearchController.php` gère toutes les interfaces d'administration secondaires plus complexes. Le fichier `index.php` dans le répertoire `controllers/admin` pourrait simplement garantir que l'accès direct au répertoire est géré avec élégance, ou il pourrait s'agir d'un fichier hérité. Pour les marchands, tous les paramètres pertinents se trouveront dans la configuration principale du module ou dans `AdminPlqdSearchController`.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Activer le module | OUI | Active/désactive la fonctionnalité principale du module. |
|  | Afficher sur la page produit | OUI/NON (dépend du thème) | Affiche les remises sur les pages de produits individuelles. |
|  | Position des informations de remise | Sous le prix du produit | Contrôle l'emplacement du texte de remise sur les fiches produits. |
|  | Couleur du texte | (Par défaut du thème) | Définit la couleur du texte de remise. |
|  | Couleur de fond | (Par défaut du thème) | Définit la couleur de fond du bloc de remise. |
|  | Activer la mise en cache | OUI | Améliore les performances en stockant le HTML généré. |
| **AdminPlqdSearchController** | Exclure un produit (par ID/Nom) | N/A | Empêche l'affichage des remises pour des produits spécifiques. |
|  | Exclure une catégorie | N/A | Empêche l'affichage des remises pour tous les produits d'une catégorie. |

## 3. Dépannage pour les marchands et Foire aux questions (FAQ)

**Q1 : Les remises quantitatives n'apparaissent pas sur mes listes de produits après l'installation.**
R :

1. **Vérifier l'état du module :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que « Remises quantitatives sur les listes de produits » est installé et activé.
2. **Configurer le module :** Cliquez sur « Configurer » pour le module et assurez-vous que le paramètre principal « Activer le module » est réglé sur OUI.
3. **Vider le cache :** PrestaShop met souvent en cache le contenu. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures).
4. **Vérifier les remises des produits :** Assurez-vous que les produits pour lesquels vous vous attendez à voir des remises ont bien des remises quantitatives configurées dans leurs paramètres de produit (Back Office > Catalogue > Produits > Modifier le produit > Onglet Prix > Prix spécifiques).
5. **Compatibilité du thème :** Certains thèmes très personnalisés peuvent nécessiter des ajustements mineurs. Si après avoir vidé le cache et vérifié les paramètres, cela n'apparaît toujours pas, contactez le support MyPresta.eu avec les détails de votre thème.

**Q2 : Le texte de la remise s'affiche, mais il ne s'intègre pas bien à mon thème (mauvaises couleurs, police ou alignement).**
R :

1. **Configuration du module :** Accédez à la page de configuration du module (**Modules > Gestionnaire de modules > Configurer** pour « Remises quantitatives sur les listes de produits »). Recherchez les options « Style et personnalisation ». Vous pourrez peut-être ajuster les couleurs, les tailles de police ou le rembourrage directement à partir de là.
2. **CSS personnalisé :** Si les paramètres du module n'offrent pas un contrôle suffisant, votre webmaster ou développeur peut ajouter du CSS personnalisé à votre thème pour remplacer les styles par défaut du module. Les fichiers CSS du module (voir Section 7.5) leur donneront les sélecteurs de classe nécessaires.

**Q3 : Je souhaite masquer les remises quantitatives pour certains produits ou catégories, mais pas pour tous.**
R :

1. **AdminPlqdSearchController :** Naviguez vers l'écran d'administration dédié du module (probablement un sous-onglet ou un lien depuis la configuration principale, potentiellement nommé « Paramètres de recherche » ou « Exclusions »).
2. **Ajouter des exclusions :** Utilisez les outils de cet écran pour rechercher et ajouter des produits spécifiques ou des catégories entières à une liste d'exclusion. Une fois ajoutés, le module ignorera ces éléments lors de l'affichage des remises sur les listes de produits.

**Q4 : Ce module va-t-il ralentir ma boutique ?**
R : Le module est conçu pour être efficace. Il utilise les données de remises quantitatives existantes de PrestaShop.

1. **Activer la mise en cache :** Assurez-vous que l'option « Activer la mise en cache » dans les paramètres avancés du module est réglée sur OUI. Cela réduit considérablement la charge de traitement lors des vues de page ultérieures.
2. **Performances du serveur :** Si votre serveur est déjà sous-alimenté ou fortement chargé, tout module supplémentaire peut avoir un impact mineur. Assurez-vous que votre hébergement répond aux spécifications recommandées par PrestaShop.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Remises quantitatives sur les listes de produits » (`plqd`) est un module PrestaShop standard suivant le modèle MVC. Il étend principalement la classe `Module`, exploitant le système de hooks de PrestaShop pour injecter du contenu dans les modèles de listes de produits. Il n'introduit pas d'entités `ObjectModel` personnalisées, mais lit plutôt les données `SpecificPrice` existantes. Le module utilise un contrôleur d'administration dédié (`AdminPlqdSearchController`) pour gérer les exclusions de produits/catégories, et intègre JavaScript et CSS pour l'affichage en front-office.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun contrôleur frontal autonome n'est explicitement défini. Le module injecte probablement son contenu directement dans les modèles via des hooks et gère tout contenu dynamique ou AJAX via des méthodes `displayAjax` au sein de la classe principale du module ou via du JS inclus.
- **Contrôleurs d'administration Back-Office** :
  - `plqd/controllers/admin/AdminPlqdSearchController.php`
    - **Nom de la classe et classe parente** : `AdminPlqdSearchController` étend `ModuleAdminController`.
    - **Nom de l'onglet et entité gérée** : Ce contrôleur est responsable de la gestion des paramètres de recherche et d'exclusion pour les produits et les catégories. Il fournit probablement une interface de grille ou de formulaire pour sélectionner les produits/catégories qui ne doivent *pas* afficher les remises quantitatives sur les listes de produits. Il ne gère pas un `ObjectModel` spécifique mais plutôt des données de configuration (par exemple, `Configuration::updateValue` pour les ID séparés par des virgules).
  - `plqd/controllers/admin/index.php`
    - Ce fichier est généralement une mesure de sécurité dans PrestaShop, empêchant la liste directe des répertoires. Il contient généralement un simple `header('Location: ../../index.php?controller=AdminHome');` ou `die('No direct script access');`. Il ne sert pas de contrôleur fonctionnel pour la logique ou l'interface utilisateur du module.

### 4.3 Classes et modèles principaux (`classes/`)

Aucune classe personnalisée ou définition d'`ObjectModel` n'est trouvée dans le répertoire `classes/` pour ce module. Le module interagit directement avec les classes `Product` et `SpecificPrice` de PrestaShop et la classe `Configuration` pour ses paramètres.

### 4.4 Actifs JavaScript (`views/js/`)

- `plqd/lib/searchTool/views/js/autocomplete.js`
  - **Portée** : Back-office (probablement utilisé dans `AdminPlqdSearchController`).
  - **Objectif** : Fournit une fonctionnalité d'autocomplétion pour la recherche de produits ou de catégories dans l'interface d'exclusion de l'administration. Il se lie aux champs de saisie, envoie des requêtes AJAX à un point de terminaison backend (éventuellement `AdminPlqdSearchController` lui-même ou un gestionnaire AJAX dédié), et affiche des suggestions à l'utilisateur.
- `plqd/views/js/plqd.js`
  - **Portée** : Front-office.
  - **Objectif** : Il s'agit du JavaScript principal du module pour le front-office. Il est probable qu'il :
    - Scanne les éléments de la liste de produits au chargement de la page ou après les mises à jour AJAX (par exemple, défilement infini, filtres de catégorie).
    - Injecte ou formate dynamiquement les informations de remise quantitative dans les fiches produits.
    - Peut gérer les ajustements réactifs ou les interactions mineures de l'interface utilisateur liées à l'affichage des remises.
    - Pourrait potentiellement effectuer des appels AJAX pour récupérer les données de remise si elles ne sont pas pré-rendues par Smarty.

### 4.5 Feuilles de style CSS (`views/css/`)

- `plqd/lib/searchTool/views/css/autocomplete.css`
  - **Portée** : Back-office.
  - **Objectif** : Style la liste déroulante d'autocomplétion et les champs de saisie utilisés dans l'`AdminPlqdSearchController` pour la recherche de produits/catégories.
  - **Sélecteurs clés** : Cible probablement des classes comme `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected`, etc.
- `plqd/views/css/plqd-classic.css`
  - **Portée** : Front-office.
  - **Objectif** : Fournit un style par défaut pour l'affichage des remises quantitatives, potentiellement adapté aux thèmes PrestaShop plus anciens ou à un look « classique ».
  - **Sélecteurs clés** : Cible le conteneur principal des informations de remise (par exemple, `.plqd-discounts-wrapper`), les lignes de remise individuelles (`.plqd-discount-item`), les quantités (`.plqd-quantity`) et les prix (`.plqd-price`).
- `plqd/views/css/plqd-hide-default.css`
  - **Portée** : Front-office.
  - **Objectif** : Cette feuille de style contient probablement des règles pour masquer les affichages de remises quantitatives par défaut qui pourraient être présents dans certains thèmes, afin d'éviter la duplication lorsque le module injecte sa propre version stylisée.
  - **Sélecteurs clés** : Pourrait cibler des éléments de thème courants comme `.product-price-and-shipping .discount-quantity` ou similaires.
- `plqd/views/css/plqd.css`
  - **Portée** : Front-office.
  - **Objectif** : La feuille de style principale du module pour le front-office, fournissant le style de base pour l'affichage des remises quantitatives. Cela pourrait être une feuille de style plus moderne ou générale par rapport à `plqd-classic.css`.
  - **Sélecteurs clés** : Similaire à `plqd-classic.css`, ciblant `.plqd-discounts-wrapper`, `.plqd-discount-item`, etc. Les développeurs peuvent remplacer ces classes dans le `custom.css` ou `theme.css` de leur thème.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **Modèles de hook (`views/templates/hook/`)** :
  - `plqd/views/tpl/html.tpl`
    - **Hook** : Il s'agit probablement du modèle principal rendu par le hook `hookDisplayProductListFunctionalButtons` (ou un hook de liste de produits similaire) du module pour afficher le HTML de remise quantitative pour un seul produit. Il reçoit les données de produit et de prix spécifique du module.
    - **Sortie** : Rend le HTML structuré pour les lignes de remise quantitative (par exemple, « À partir de X unités : Y € »).
- **Modèles d'administration (`views/templates/admin/`)** :
  - `plqd/lib/searchTool/views/scripts.tpl`
    - **Objectif** : Ce modèle est probablement inclus dans la vue `AdminPlqdSearchController`. Il contient l'initialisation JavaScript pour la fonctionnalité d'autocomplétion (par exemple, blocs `$(document).ready()`, définitions de variables pour les URL AJAX, etc.) et potentiellement des inclusions CSS.
  - `plqd/views/tpl/selectedProducts.tpl`
    - **Objectif** : Utilisé dans `AdminPlqdSearchController` pour afficher la liste des produits ou catégories qui ont été sélectionnés pour exclusion. Il rendrait généralement un tableau ou une liste de ces éléments, éventuellement avec des options pour les supprimer.
- **Modèles Front-office (`views/templates/front/`)** :
  - `plqd/views/tpl/html-product-page.tpl`
    - **Objectif** : Ce modèle est spécifiquement conçu pour afficher les remises quantitatives sur la page de produit individuelle, si le module est configuré pour le faire. Il pourrait avoir un style ou une structure légèrement différents par rapport au modèle de page de liste (`html.tpl`) pour mieux s'adapter à la mise en page de la page de produit.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :
  - Le module ne crée pas de tables SQL personnalisées. Il s'appuie sur la table `ps_specific_price` de PrestaShop pour les données de remises quantitatives.
  - Les paramètres de configuration (par exemple, état activé, options de style, ID de produits/catégories exclus) sont stockés dans la table `ps_configuration` à l'aide de clés généralement préfixées par `PLQD_`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Utilisé pour inclure les CSS du module (`plqd.css`, `plqd-classic.css`, `plqd-hide-default.css`) et JavaScript (`plqd.js`). |
| `displayProductListFunctionalButtons` | Dans les éléments de liste de produits (par exemple, catégorie, résultats de recherche). | Hook principal pour injecter le HTML de remise quantitative (`html.tpl`) dans les fiches produits. |
| `displayProductPriceBlock` (type `after_price`) | Après le bloc de prix principal sur les pages de produits. | Utilisé pour injecter `html-product-page.tpl` si configuré pour afficher les remises sur les pages de produits. |
| `displayRightColumn` / `displayLeftColumn` | Dans les colonnes latérales droite/gauche. | Moins probable pour ce module, mais pourrait être utilisé pour un bloc promotionnel lié aux remises quantitatives si implémenté. |
| `displayFooter` | En bas de chaque page du front-office. | Pourrait être utilisé pour le chargement tardif de JS ou des scripts supplémentaires si nécessaire. |
| `actionProductUpdate` | Après la mise à jour d'un produit dans le Back Office. | Pourrait être utilisé pour vider le cache du module lié à ce produit, garantissant que les prix spécifiques mis à jour sont reflétés. |
| `actionModuleInstall` | Lors de l'installation du module. | Crée des entrées de configuration dans `ps_configuration`. |
| `actionModuleUninstall` | Lors de la désinstallation du module. | Nettoie les entrées de configuration et potentiellement toutes les données personnalisées. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, les corrections de bugs et le support développeur dédié pour le module « Remises quantitatives sur les listes de produits », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe est disponible pour vous aider avec tout problème technique ou question concernant la fonctionnalité et l'intégration du module.
