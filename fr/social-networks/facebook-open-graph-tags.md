---
title: "Balises Open Graph de Facebook - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Balises Open Graph de Facebook par MyPresta.eu."
sidebar:
  label: "Balises Open Graph de Facebook - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Facebook Open Graph Tags sur MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-open-graph-tags.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/facebook-open-graph-tags/)
>
> ---


# Balises Open Graph de Facebook

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.3.x, 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes et sont habituellement activées par défaut sur la plupart des environnements d'hébergement.

## 2. Présentation complète de la configuration (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Balises Open Graph de Facebook)

C'est l'écran de configuration principal où vous contrôlez le comportement essentiel du module.

| Paramètre / Option | Ce que fait ce paramètre | Effet de la modification de ce paramètre | Valeur recommandée | Scénario / exemple pour le marchand |
| --- | --- | --- | --- | --- |
| **Activer les balises Open Graph** | Cet interrupteur principal contrôle si le module génère des balises Open Graph. | *Lorsque activé :* Le module injectera les balises Open Graph nécessaires dans la section `<head>` HTML de votre boutique, permettant à Facebook d'afficher des aperçus enrichis. *Lorsque désactivé :* Aucune balise Open Graph ne sera générée par ce module, et Facebook essaiera de deviner le contenu, ce qui entraînera souvent des aperçus médiocres ou manquants. | **OUI** | Vous voulez que les partages de vos produits aient un aspect professionnel sur Facebook. |
| **ID d'application Facebook** | Votre identifiant unique pour votre application Facebook. Cela lie les partages de votre site web à votre application Facebook, permettant des analyses et des statistiques. | *Lorsque fourni :* Facebook peut attribuer les partages à votre application, vous fournissant des analyses sur la performance de votre contenu sur leur plateforme. *Lorsque laissé vide :* Les partages fonctionneront toujours, mais vous n'obtiendrez pas d'informations détaillées via les outils de développement de Facebook. | **Votre ID d'application Facebook** (si vous en avez un) | Vous souhaitez suivre les performances de votre contenu partagé sur Facebook à l'aide de Facebook Insights. Si vous n'en avez pas, vous pouvez le laisser vide. |
| **ID d'administrateur Facebook** | L'ID utilisateur Facebook de l'administrateur (ou des administrateurs) de votre page ou application Facebook. Cela aide Facebook à comprendre qui gère le contenu. | *Lorsque fourni :* Facebook sait qui est l'auteur/administrateur du contenu, ce qui peut être utile pour la modération ou des fonctionnalités Facebook spécifiques. *Lorsque laissé vide :* Aucun administrateur spécifique ne sera lié. | **Votre ID utilisateur Facebook** (si applicable) | Vous souhaitez lier votre profil Facebook personnel en tant qu'administrateur du contenu partagé. |
| **Image par défaut pour la page d'accueil** | Ce paramètre vous permet de spécifier une image de secours que Facebook utilisera lorsque votre page d'accueil est partagée, surtout si votre page d'accueil n'a pas d'image proéminente elle-même. | *Lorsqu'une image est téléchargée :* Cette image sera utilisée comme `og:image` lorsque la page d'accueil de votre boutique est partagée sur Facebook. *Lorsque laissé vide :* Facebook essaiera de trouver une image sur votre page d'accueil, ce qui pourrait ne pas toujours être idéal (par exemple, un petit logo ou une bannière). | **Téléchargez le logo principal de votre boutique ou une image de bannière attrayante.** | Votre page d'accueil est principalement textuelle, et vous voulez qu'une image spécifique et attrayante apparaisse lorsque quelqu'un partage l'URL principale de votre boutique. |
| **Titre par défaut pour la page d'accueil** | Le titre que Facebook affichera lorsque la page d'accueil de votre boutique est partagée. | *Lorsque fourni :* Ce titre sera utilisé comme `og:title` pour les partages de votre page d'accueil. *Lorsque laissé vide :* Facebook utilisera probablement la méta-titre par défaut de votre boutique, qui pourrait ne pas être optimisé pour le partage social. | **Nom de votre boutique - Slogan** (par exemple, « Ma Super Boutique - Découvrez des Produits Uniques ! ») | Vous voulez qu'un titre accrocheur et de marque apparaisse lorsque l'URL principale de votre boutique est partagée. |
| **Description par défaut pour la page d'accueil** | La description que Facebook affichera lorsque la page d'accueil de votre boutique est partagée. | *Lorsque fournie :* Cette description sera utilisée comme `og:description` pour les partages de votre page d'accueil. *Lorsque laissée vide :* Facebook utilisera probablement la méta-description par défaut de votre boutique, qui pourrait ne pas être optimisée pour le partage social. | **Un résumé concis et engageant de votre boutique.** (par exemple, « Découvrez les dernières tendances en mode et électronique. Livraison rapide dans le monde entier ! ») | Vous voulez contrôler le message qui apparaît lorsque la page d'accueil de votre boutique est partagée, incitant les utilisateurs à cliquer. |

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 AdminOpenGraphController (Back Office > Paramètres avancés > Balises Open Graph)

Cet écran vous permet de gérer des balises Open Graph spécifiques pour des pages individuelles ou de remplacer le comportement par défaut. Bien que le module génère automatiquement des balises pour les produits et les catégories, cette section est utile pour les pages personnalisées ou l'ajustement fin.

- **Nom de l'écran et emplacement du menu :** Vous pouvez accéder à cet écran en naviguant vers **Paramètres avancés > Balises Open Graph** dans votre Back Office PrestaShop.
- **Actions et paramètres disponibles :** Cet écran présente généralement une grille (liste) des configurations de balises Open Graph personnalisées que vous avez ajoutées. Vous y trouverez des options pour :
  - **Ajouter nouveau :** Créer un nouvel ensemble de balises Open Graph personnalisées pour une URL spécifique.
  - **Modifier :** Modifier un ensemble de balises personnalisées existant.
  - **Supprimer :** Supprimer un ensemble de balises personnalisées.
  - **Colonnes de la grille :** Affiche généralement l'URL, le titre, la description et l'image associés à la balise personnalisée.
- **Effet des modifications :**
  - **Ajout d'une nouvelle entrée :** Lorsque vous ajoutez une nouvelle entrée pour une URL spécifique (par exemple, une page CMS personnalisée ou l'URL d'un article de blog), le module utilisera le titre, la description et l'image que vous fournissez ici au lieu d'essayer de les générer automatiquement lorsque cette URL spécifique est partagée sur Facebook.
  - **Modification d'une entrée :** Met à jour l'aperçu social pour cette URL spécifique.
  - **Suppression d'une entrée :** Rétablit le comportement pour cette URL à la génération automatique du module ou aux paramètres par défaut de la page d'accueil.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. **Identifier les pages nécessitant des aperçus personnalisés :** Pour la plupart des produits et catégories, le module fonctionne automatiquement. Cependant, pour les pages CMS personnalisées (par exemple, « À propos de nous », « Contactez-nous », articles de blog si vous avez un blog intégré), vous pourriez vouloir des aperçus spécifiques et engageants.
  2. **Cliquez sur « Ajouter nouveau »** pour créer une nouvelle entrée.
  3. **Entrez l'URL exacte** de la page que vous souhaitez personnaliser.
  4. **Fournissez un titre, une description et téléchargez une image pertinente** pour cette page spécifique.
  5. **Enregistrez** vos modifications.
  6. **Testez :** Utilisez le [Débogueur de partage](https://developers.facebook.com/tools/debug/) de Facebook pour vérifier l'apparence de votre page après avoir effectué des modifications.

#### 2.2.2 index.php (opengraph/controllers/admin/index.php)

Ce fichier est un point d'entrée de contrôleur PrestaShop standard et ne représente pas un écran distinct et configurable pour les marchands. Il est généralement utilisé pour le routage ou l'administration de base du module, et non pour la gestion de contenu ou de paramètres spécifiques. Toutes les configurations destinées aux marchands sont gérées via la page de configuration principale du module ou le `AdminOpenGraphController`.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activer les balises Open Graph | OUI | Interrupteur principal pour la fonctionnalité du module. |
|  | ID d'application Facebook | (Votre ID d'application) / Vide | Lie les partages à votre application Facebook pour l'analyse. |
|  | ID d'administrateur Facebook | (Votre ID utilisateur) / Vide | Identifie l'administrateur du contenu sur Facebook. |
|  | Image par défaut pour la page d'accueil | Téléchargez votre logo | Image de secours pour les partages de la page d'accueil. |
|  | Titre par défaut pour la page d'accueil | Nom de votre boutique | Titre pour les partages de la page d'accueil. |
|  | Description par défaut pour la page d'accueil | Slogan de la boutique | Description pour les partages de la page d'accueil. |
| **Paramètres avancés > Balises Open Graph** | Ajouter/Modifier/Supprimer des balises personnalisées | N/A | Remplace les balises générées automatiquement pour des URL spécifiques par des titres, descriptions et images personnalisés. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes partages sur Facebook sont toujours de mauvaise qualité, même après l'installation du module. Qu'est-ce qui ne va pas ?**
R :

1. **Vérifiez l'activation du module :** Assurez-vous que « Activer les balises Open Graph » est réglé sur OUI dans la configuration du module.
2. **Videz le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). C'est crucial pour que les modifications prennent effet.
3. **Utilisez le débogueur de partage Facebook :** C'est votre meilleur ami ! Allez sur [developers.facebook.com/tools/debug/](https://developers.facebook.com/tools/debug/), collez l'URL que vous essayez de partager, et cliquez sur « Déboguer ». Il vous montrera exactement quelles balises Facebook voit et s'il y a des erreurs. Vous devrez peut-être cliquer sur « Scraper à nouveau » pour forcer Facebook à relire votre page après avoir effectué des modifications.
4. **Vérifiez les conflits :** Un autre module ou votre thème pourrait ajouter des balises Open Graph conflictuelles. Le débogueur mettra souvent en évidence les balises en double.

**Q : L'image de mes partages de produits est incorrecte ou manquante.**
R :

1. **Image du produit :** Assurez-vous que votre produit a une image principale assignée dans ses paramètres de produit.
2. **Taille de l'image :** Bien que Facebook puisse redimensionner, des images très petites ou avec un rapport d'aspect inhabituel pourraient être ignorées. Visez au moins 600x315 pixels, idéalement 1200x628 pour un affichage optimal.
3. **Cache :** Videz le cache de PrestaShop et utilisez le débogueur de partage Facebook pour « Scraper à nouveau ».

**Q : Comment obtenir un ID d'application Facebook ou un ID d'administrateur ?**
R :

1. **ID d'application Facebook :** Allez sur [developers.facebook.com](https://developers.facebook.com/), connectez-vous et créez une nouvelle application. Suivez les étapes pour obtenir votre ID d'application. C'est une chaîne numérique.
2. **ID d'administrateur Facebook :** C'est votre ID utilisateur Facebook personnel. Vous pouvez le trouver en allant sur votre profil Facebook, en cliquant sur votre photo de profil et en regardant l'URL dans votre navigateur (par exemple, `facebook.com/profile.php?id=VOTRE_ID_UTILISATEUR`).

**Q : Ce module fonctionne-t-il avec des thèmes personnalisés ?**
R : Oui, le module injecte des balises directement dans la section `<head>` de votre HTML, ce qui est une pratique standard et devrait fonctionner avec tout thème PrestaShop bien codé. Si vous rencontrez des problèmes, il s'agit généralement d'un problème de cache ou d'un conflit avec un autre module.

**Q : Ma page personnalisée (par exemple, un article de blog) n'affiche pas le bon aperçu.**
R : Utilisez la section **Paramètres avancés > Balises Open Graph** dans le Back Office. Ajoutez une nouvelle entrée pour l'URL exacte de votre page personnalisée et spécifiez manuellement le titre, la description et l'image souhaités. N'oubliez pas de vider le cache et d'utiliser le débogueur de partage Facebook par la suite.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Balises Open Graph de Facebook » est conçu pour s'intégrer de manière transparente aux fonctionnalités principales de PrestaShop, principalement en tirant parti des hooks pour injecter des balises meta Open Graph dans la section `<head>` HTML de diverses pages du front-office. Il suit une structure de module PrestaShop standard, utilisant une classe de module principale, un contrôleur d'administration pour la gestion des balises personnalisées et des templates Smarty pour le rendu. Le module n'introduit pas de schémas de base de données complexes ni de modèles d'objets personnalisés pour sa fonction principale, mais utilise `Configuration` pour ses paramètres principaux et potentiellement une table personnalisée pour les `og_tags` gérée par `AdminOpenGraphController`.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Ce module ne contient aucun contrôleur front-office dédié. Toute la logique front-office pour la génération de balises est gérée directement dans la classe principale du module (`index.php`) via des écouteurs de hook.
- **Contrôleurs d'administration Back-Office** :

  - `opengraph/controllers/admin/AdminOpenGraphController.php`
    - **Nom de la classe et classe parente** : `AdminOpenGraphController` étend `ModuleAdminController`.
    - **Nom de l'onglet et entité gérée** : Ce contrôleur gère une entité personnalisée, probablement `og_tags`, qui stocke les configurations Open Graph personnalisées pour des URL spécifiques. Il crée une nouvelle entrée de menu sous « Paramètres avancés » (ou similaire) dans le Back Office.
    - **Responsabilité** : Fournit une interface CRUD (Créer, Lire, Mettre à jour, Supprimer) PrestaShop standard pour la gestion des ensembles de balises Open Graph personnalisées. Il gère l'affichage d'une liste de balises personnalisées (en utilisant `renderList()`) et le formulaire pour les ajouter/modifier (en utilisant `renderForm()`). Il traite les soumissions de formulaires et interagit avec la base de données pour stocker et récupérer les données `og_tags`.
  - `opengraph/controllers/admin/index.php`
    - **Nom de la classe et classe parente** : Il s'agit généralement d'un fichier `index.php` vide dans un répertoire de contrôleur, servant de mesure de sécurité pour empêcher la liste directe des répertoires. Il ne contient aucune classe ou logique fonctionnelle.

### 4.3 Classes et modèles principaux (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. La logique principale pour la génération des balises Open Graph est probablement contenue dans le fichier principal du module (`opengraph/index.php`), et le `AdminOpenGraphController` gérerait les interactions avec une table de base de données personnalisée directement ou via un simple `ObjectModel` si l'un était défini en interne.

Si une table personnalisée `og_tags` est gérée par `AdminOpenGraphController`, il est fort probable que le `AdminOpenGraphController` lui-même définisse les propriétés `$this->table` et `$this->className`, et qu'une simple définition `ObjectModel` pour `og_tags` soit déclarée dans le fichier principal du module ou le contrôleur lui-même, même si ce n'est pas dans un fichier `classes/` séparé.

### 4.4 Actifs JavaScript (`views/js/`)

Le dossier du module n'indique aucun fichier JavaScript personnalisé. Tout comportement dynamique ou interaction AJAX serait géré par le JS principal de PrestaShop ou n'est pas présent dans ce module.

### 4.5 Feuilles de style CSS (`views/css/`)

Le dossier du module n'indique aucun fichier CSS personnalisé. Le module s'appuie sur le style par défaut du Back Office de PrestaShop pour ses formulaires de configuration et toute sortie front-office est purement des balises meta, et non des éléments visuels.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :

  - `opengraph/views/templates/front/hook/header.tpl` :
    - **Hook** : Probablement `displayHeader` ou `actionFrontControllerSetMedia`.
    - **Objectif** : C'est le template principal responsable du rendu des balises `<meta>` Open Graph réelles dans la section `<head>` des pages du front-office. Il reçoit des variables (par exemple, `og_title`, `og_description`, `og_image`, `og_url`, `og_type`, `og_app_id`, `og_admin_id`) de la méthode `hookDisplayHeader` (ou similaire) du module et génère les balises meta HTML correspondantes.
  - `opengraph/views/templates/hook/form.tpl` :
    - **Hook** : Ce template est probablement utilisé en interne par l'`AdminOpenGraphController` pour le rendu des champs de formulaire lors de l'ajout ou de la modification d'une entrée de balise Open Graph personnalisée. Ce n'est pas un template de hook front-office.
    - **Objectif** : Définit la structure et les champs de saisie pour le formulaire de configuration des balises Open Graph personnalisées dans le Back Office.
  - `opengraph/views/templates/hook/script.tpl` :
    - **Hook** : Pourrait être `displayHeader` ou `actionFrontControllerSetMedia`.
    - **Objectif** : Ce template pourrait être utilisé pour générer du JavaScript en ligne lié à Open Graph, tel que l'initialisation du SDK Facebook ou le suivi d'événements spécifiques, bien que le dossier n'indique aucun fichier JS, il pourrait donc s'agir d'un script très minimal ou d'un espace réservé.
- **Templates d'administration (`views/templates/admin/`)** : Non explicitement listés, mais `form.tpl` et potentiellement un `list.tpl` seraient utilisés par `AdminOpenGraphController` pour ses vues.
- **Templates Front-Office (`views/templates/front/`)** :

  - `opengraph/views/templates/front/hook/header.tpl` est le seul template front-office identifié, spécifiquement pour l'injection de hook.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - `ps_configuration` : Stocke les paramètres principaux du module (par exemple, `PS_OG_ENABLED`, `PS_OG_APP_ID`, `PS_OG_ADMIN_ID`, `PS_OG_HOME_IMAGE`, `PS_OG_HOME_TITLE`, `PS_OG_HOME_DESCRIPTION`).
  - `ps_og_tags` (ou similaire, gérée par `AdminOpenGraphController`) : Une table personnalisée pour stocker les remplacements de balises Open Graph définis par l'utilisateur pour des URL spécifiques.
    - Champs probables : `id_og_tag`, `url`, `title`, `description`, `image`, `date_add`, `date_upd`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rend le contenu dans la section `<head>` de toutes les pages du front-office. | Hook principal pour injecter les balises meta Open Graph (`og:title`, `og:description`, `og:image`, `og:url`, `og:type`, etc.) dans le HTML. |
| `actionFrontControllerSetMedia` | Exécuté après que le contrôleur frontal a défini ses médias (CSS/JS). | Pourrait être utilisé comme hook alternatif ou additionnel pour injecter des balises meta ou des scripts associés, en particulier dans PrestaShop 1.7+. |
| `displayBackOfficeHeader` | Rend le contenu dans la section `<head>` des pages du Back Office. | Utilisé pour inclure tout CSS ou JS nécessaire pour les pages de configuration du module dans le Back Office. |
| `actionAdminControllerSetMedia` | Exécuté après qu'un contrôleur d'administration a défini ses médias. | Similaire à `displayBackOfficeHeader` mais plus spécifique aux contrôleurs d'administration, pour charger les ressources pour `AdminOpenGraphController`. |
| `moduleRoutes` (PrestaShop 1.7+) | Permet aux modules de définir des routes personnalisées. | Non explicitement utilisé pour la fonction principale de ce module, mais pourrait être présent pour de futures extensions ou une gestion d'URL spécifique. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour accéder aux dernières versions du module « Balises Open Graph de Facebook », veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
