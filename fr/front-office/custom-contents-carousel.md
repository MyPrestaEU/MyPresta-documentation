---
title: "Carrousel de contenus personnalisés - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Carrousel de contenus personnalisés par MyPresta.eu."
sidebar:
  label: "Carrousel de contenus personnalisés - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Custom contents carousel sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/custom-contents-carousel.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/custom-contents-carousel/)
>
> ---


# Carrousel de contenus personnalisés

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement nécessaire au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

Le module « Carrousel de contenus personnalisés » organise ses paramètres sur plusieurs écrans de votre Back Office PrestaShop. Vous configurerez d'abord les paramètres globaux, puis créerez des « Groupes » (qui sont vos carrousels), et enfin ajouterez des « Éléments » (les diapositives individuelles) à chaque groupe.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Carrousel de contenus personnalisés)

C'est l'écran de configuration principal du module, accessible immédiatement après l'installation ou en cliquant sur « Configurer » depuis le Gestionnaire de modules.

- **Ce que fait ce paramètre :** Cet écran gère principalement les paramètres généraux du module et les vérifications de mise à jour.
- **Effet de la modification de ce paramètre :**
  - `mypresta_updates`, `update_`, `updatev_` : Ce sont des paramètres internes utilisés par les modules MyPresta.eu pour gérer les mises à jour et les vérifications de version. Ils n'affectent pas directement l'affichage du front-office mais garantissent que votre module reste à jour.
  - `CCAROUSEL_LIGHTSLIDER` : Ce paramètre contrôle probablement l'activation de la bibliothèque JavaScript LightSlider, qui alimente la fonctionnalité du carrousel.
    - *Lorsqu'il est activé (OUI)* : La bibliothèque LightSlider sera chargée sur votre front office, permettant aux carrousels de fonctionner correctement.
    - *Lorsqu'il est désactivé (NON)* : La bibliothèque LightSlider pourrait ne pas se charger, ce qui pourrait rompre l'affichage et la fonctionnalité du carrousel.
- **Valeur recommandée :**
  - `CCAROUSEL_LIGHTSLIDER` : **OUI** (Activé). C'est crucial pour le fonctionnement du carrousel.
  - Autres paramètres : Laissez par défaut.
- **Scénario/exemple marchand :** Vous venez d'installer le module et souhaitez vous assurer que tous les scripts nécessaires sont chargés. Vous vérifieriez que `CCAROUSEL_LIGHTSLIDER` est activé. Si vous rencontrez des problèmes avec le carrousel qui ne glisse pas, ce serait l'un des premiers endroits à vérifier.

### 2.2 Écran d'administration dédié : Groupes de contenus personnalisés (Back Office > Modules > Carrousel de contenus personnalisés > Groupes de contenus personnalisés)

Cet écran vous permet de créer et de gérer vos carrousels individuels. Chaque « groupe » représente un carrousel distinct que vous pouvez ensuite remplir de diapositives.

- **Nom de l'écran et emplacement du menu :** Vous le trouverez sous **Modules > Carrousel de contenus personnalisés > Groupes de contenus personnalisés** dans le menu de votre Back Office PrestaShop.
- **Actions et paramètres disponibles :**
  - **Vue en grille** : Affiche une liste de tous vos groupes de carrousels existants. Vous pouvez voir leurs noms, leur statut (actif/inactif) et les actions.
  - **Ajouter un nouveau groupe** : Cliquez sur le bouton « Ajouter » pour créer un tout nouveau carrousel.
  - **Modifier/Supprimer un groupe** : Pour chaque groupe, vous aurez des options pour modifier ses paramètres (par exemple, nom, options d'affichage) ou le supprimer entièrement.
  - **Basculer le statut** : Activez ou désactivez rapidement un groupe de carrousels sans le supprimer. Un groupe inactif n'apparaîtra pas sur votre front office.
- **Effet des modifications :**
  - **Ajout d'un nouveau groupe** : Crée un nouveau conteneur de carrousel vide. Vous devrez ensuite y ajouter des éléments (diapositives).
  - **Modification d'un groupe** : Vous permet de changer le nom du carrousel, ses paramètres d'affichage (par exemple, lecture automatique, vitesse, nombre de diapositives visibles) et sa position.
  - **Activation/Désactivation** : Contrôle si le carrousel est visible pour vos clients sur le front office.
  - **Suppression d'un groupe** : Supprime définitivement le carrousel et tous ses éléments (diapositives) associés.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Commencez par créer un nouveau groupe pour chaque carrousel que vous souhaitez afficher (par exemple, « Carrousel de bannières de la page d'accueil », « Slider Nouveautés »).
  2. Donnez à chaque groupe un nom clair et descriptif.
  3. Configurez les paramètres d'affichage du groupe (par exemple, lecture automatique, boucle, pause au survol) pour correspondre à l'expérience utilisateur souhaitée.
  4. Une fois le groupe créé, passez à l'écran « Éléments de contenus personnalisés » pour y ajouter des diapositives.

### 2.3 Écran d'administration dédié : Éléments de contenus personnalisés (Back Office > Modules > Carrousel de contenus personnalisés > Éléments de contenus personnalisés)

Cet écran est l'endroit où vous gérez les diapositives individuelles (éléments) au sein de vos carrousels. Chaque élément peut être une image, une vidéo, du texte ou du contenu intégré.

- **Nom de l'écran et emplacement du menu :** Vous le trouverez sous **Modules > Carrousel de contenus personnalisés > Éléments de contenus personnalisés** dans le menu de votre Back Office PrestaShop.
- **Actions et paramètres disponibles :**
  - **Vue en grille** : Liste toutes les diapositives individuelles, indiquant à quel groupe elles appartiennent, leur type de contenu et leur statut.
  - **Ajouter un nouvel élément** : Cliquez sur « Ajouter » pour créer une nouvelle diapositive. Vous choisirez ensuite le groupe auquel elle appartient et définirez son contenu.
  - **Modifier/Supprimer un élément** : Modifiez le contenu, le lien ou l'ordre d'affichage d'une diapositive existante, ou supprimez-la.
  - **Basculer le statut** : Activez ou désactivez les diapositives individuelles. Une diapositive inactive n'apparaîtra pas dans son carrousel.
  - **Réorganisation par glisser-déposer** : Modifiez facilement l'ordre d'affichage des diapositives au sein d'un groupe.
- **Effet des modifications :**
  - **Ajout d'un nouvel élément** : Crée une nouvelle diapositive. Vous spécifierez son contenu (téléchargement d'image, URL vidéo, texte, HTML), un lien, et l'assignerez à l'un de vos groupes de carrousels existants.
  - **Modification d'un élément** : Vous permet de mettre à jour le contenu, de changer le lien, de modifier l'image ou d'ajuster sa position dans le carrousel.
  - **Activation/Désactivation** : Contrôle si une diapositive spécifique est visible dans son carrousel.
  - **Suppression d'un élément** : Supprime définitivement la diapositive de son carrousel.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Sélectionnez le groupe de carrousels auquel vous souhaitez ajouter des diapositives (si vous en avez plusieurs).
  2. Cliquez sur « Ajouter un nouvel élément » et choisissez le type de contenu (image, vidéo, texte, HTML).
  3. Téléchargez votre image, collez votre URL vidéo ou saisissez votre texte/HTML.
  4. Ajoutez un lien pertinent si la diapositive doit diriger les clients vers un produit, une catégorie ou une page externe.
  5. Définissez l'ordre d'affichage.
  6. Répétez l'opération pour toutes les diapositives de votre carrousel.
  7. Utilisez la fonction glisser-déposer pour affiner l'ordre de vos diapositives.

### 2.4 Écran d'administration dédié : index.php (ccarousel/controllers/admin/index.php)

Ce fichier est une pratique standard de PrestaShop pour sécuriser les répertoires d'administration. Il contient généralement une simple instruction `die('No direct script access allowed');` et ne présente pas d'écran configurable ou d'entité gérée en soi. C'est une mesure de sécurité, pas une interface de configuration.

### 2.5 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | `CCAROUSEL_LIGHTSLIDER` | OUI | Active/désactive la bibliothèque JavaScript principale pour la fonctionnalité du carrousel. **Doit être OUI pour que les carrousels fonctionnent.** |
| Groupes de contenus personnalisés | Nom du groupe | Défini par l'utilisateur | Identifie votre carrousel (par exemple, « Bannières de la page d'accueil »). |
| Groupes de contenus personnalisés | Statut | Activé | Contrôle la visibilité de l'ensemble du carrousel sur le front office. |
| Groupes de contenus personnalisés | Paramètres du carrousel | Défini par l'utilisateur | Contrôle la lecture automatique, la vitesse, la boucle, la navigation, etc., pour chaque carrousel. |
| Éléments de contenus personnalisés | Contenu de l'élément | Défini par l'utilisateur | Le contenu réel de la diapositive (image, vidéo, texte, HTML). |
| Éléments de contenus personnalisés | Lien de l'élément | URL facultative | Où la diapositive dirige les clients lorsqu'elle est cliquée. |
| Éléments de contenus personnalisés | Statut | Activé | Contrôle la visibilité des diapositives individuelles dans un carrousel. |
| Éléments de contenus personnalisés | Position | Défini par l'utilisateur | Détermine l'ordre des diapositives dans un carrousel. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Mon carrousel n'apparaît pas sur la page d'accueil.**

- **R :** Tout d'abord, vérifiez si le module « Carrousel de contenus personnalisés » est activé dans **Modules > Gestionnaire de modules**. Ensuite, naviguez vers **Modules > Carrousel de contenus personnalisés > Groupes de contenus personnalisés** et assurez-vous que votre groupe de carrousels est actif (coche verte). Enfin, assurez-vous d'avoir au moins un « Élément de contenu personnalisé » actif assigné à ce groupe. Vérifiez également que le paramètre `CCAROUSEL_LIGHTSLIDER` sur la page de configuration principale du module est activé.

**Q2 : Les images de mon carrousel sont floues ou déformées.**

- **R :** Assurez-vous que les images que vous téléchargez sont de haute qualité et ont des dimensions appropriées pour l'espace où le carrousel est affiché. Si votre thème a des recommandations spécifiques de taille d'image pour les bannières ou les sliders, essayez de les respecter. Le module redimensionnera les images, mais il est essentiel de partir d'une bonne image source.

**Q3 : Le carrousel ne glisse pas ou ne se lance pas automatiquement.**

- **R :** Il s'agit souvent d'un problème JavaScript.
  1. Allez dans **Modules > Configurer > Carrousel de contenus personnalisés** et assurez-vous que `CCAROUSEL_LIGHTSLIDER` est réglé sur « OUI ».
  2. Videz votre cache PrestaShop (**Paramètres avancés > Performances > Vider le cache**).
  3. Videz le cache de votre navigateur.
  4. Si le problème persiste, il pourrait y avoir un conflit JavaScript avec un autre module ou votre thème. Vérifiez la console de développement de votre navigateur (F12) pour toute erreur JavaScript.

**Q4 : Comment puis-je changer l'ordre des diapositives dans mon carrousel ?**

- **R :** Allez dans **Modules > Carrousel de contenus personnalisés > Éléments de contenus personnalisés**. Vous devriez voir une liste de vos diapositives. Cherchez une colonne avec des flèches ou une icône de glisser-déposer. Vous pouvez généralement faire glisser et déposer les lignes pour les réorganiser, ou il peut y avoir un champ « Position » que vous pouvez modifier. N'oubliez pas d'enregistrer vos modifications.

**Q5 : Puis-je avoir plusieurs carrousels sur différentes pages ?**

- **R :** Le module utilise principalement le hook `displayHome`, ce qui signifie qu'il est conçu pour la page d'accueil. Bien que vous puissiez créer plusieurs *groupes* (carrousels), ils s'afficheront tous généralement dans la même position hookée. Pour afficher des carrousels sur différentes pages ou à différentes positions, une intégration de thème personnalisée ou une enregistrement de hook supplémentaire serait nécessaire (voir le Guide du développeur).

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters qui maintiennent ou étendent le module « Carrousel de contenus personnalisés ».

### 4.1 Aperçu de l'architecture

Le module « Carrousel de contenus personnalisés » suit un modèle MVC (Modèle-Vue-Contrôleur) PrestaShop standard pour ses composants Back Office. Il s'appuie sur la classe `Module` de PrestaShop pour les fonctionnalités de base et sur `AdminController` pour la gestion des groupes et des éléments de contenu. L'affichage du front-office est principalement géré via un template Smarty hooké dans `displayHome`, avec des ressources JavaScript (LightSlider) et CSS chargées via `displayHeader`. La persistance des données est gérée par des classes `ObjectModel` personnalisées.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :
  Le module ne contient aucun contrôleur front-office dédié. Tout le rendu front-office est géré directement via la classe de module principale (`ccarousel.php`) en enregistrant des hooks et en rendant des templates.
- **Contrôleurs d'administration Back-Office** :

  - `controllers/admin/AdminCustomContentsGroupsController.php`
    - Nom de la classe : `AdminCustomContentsGroupsController`
    - Classe parente : `ModuleAdminController`
    - Responsabilité : Gère l'entité `gcarousel` (groupes de carrousels). Ce contrôleur gère la liste, l'ajout, la modification et la suppression des groupes de carrousels. Il définit les champs de formulaire pour la configuration des groupes (par exemple, nom, statut, paramètres du carrousel comme la lecture automatique, la vitesse).
  - `controllers/admin/AdminCustomContentsItemsController.php`
    - Nom de la classe : `AdminCustomContentsItemsController`
    - Classe parente : `ModuleAdminController`
    - Responsabilité : Gère l'entité `gcitem` (diapositives/éléments de carrousel individuels). Ce contrôleur gère la liste, l'ajout, la modification et la suppression des diapositives. Il définit les champs de formulaire pour le contenu des diapositives (téléchargement d'image, URL vidéo, texte/HTML, lien, position, groupe associé). Il gère également la fonctionnalité de réorganisation par glisser-déposer pour les diapositives.
  - `controllers/admin/index.php`
    - Nom de la classe : N/A (simple fichier PHP)
    - Classe parente : N/A
    - Responsabilité : Une mesure de sécurité pour empêcher l'affichage direct du répertoire ou l'accès direct. Contient `die('No direct script access allowed');`.

### 4.3 Classes et modèles principaux (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que les définitions `ObjectModel` pour `gcarousel` et `gcitem` sont probablement intégrées directement dans le fichier de module principal (`ccarousel.php`) ou dans les fichiers `AdminController` respectifs.

- **`gcarousel` (Modèle de groupe de carrousels)** :

  - Étend probablement `ObjectModel`.
  - Interagit avec une table de base de données personnalisée (par exemple, `ps_gcarousel`).
  - Les champs `$definition` incluraient : `id_gcarousel`, `name`, `active`, `settings` (éventuellement un tableau sérialisé ou une chaîne JSON pour les options d'affichage du carrousel).
  - Méthodes clés : `add()`, `update()`, `delete()`, `getGroups()`.
- **`gcitem` (Modèle d'élément/diapositive de carrousel)** :

  - Étend probablement `ObjectModel`.
  - Interagit avec une table de base de données personnalisée (par exemple, `ps_gcitem`).
  - Les champs `$definition` incluraient : `id_gcitem`, `id_gcarousel` (clé étrangère), `position`, `active`, `type` (image, vidéo, texte, html), `content` (chemin vers l'image, URL vidéo, texte), `link`, `title`, `description` (pour le support multilingue).
  - Méthodes clés : `add()`, `update()`, `delete()`, `getItemsByGroup()`, `updatePosition()`.

### 4.4 Ressources JavaScript (`views/js/`)

- `ccarousel/lib/src/js/lightslider.js`
  - Portée : Front-office.
  - Responsabilité : Il s'agit de la bibliothèque LightSlider principale. Elle initialise et gère la fonctionnalité du carrousel. Elle lie les écouteurs d'événements pour la navigation (flèches, points), gère les gestes tactiles/de balayage, la lecture automatique, la boucle et les ajustements réactifs. La méthode `hookDisplayHeader` ou `hookDisplayHome` du module mettrait généralement ce script en file d'attente, puis un script en ligne ou un fichier JS de module séparé appellerait `$('#your-carousel-selector').lightSlider({...});` pour initialiser des carrousels spécifiques.

### 4.5 Feuilles de style CSS (`views/css/`)

- `ccarousel/css.css`
  - Portée : Front-office.
  - Responsabilité : Contient probablement un style personnalisé spécifique au module « Carrousel de contenus personnalisés », remplaçant ou étendant les styles de base de LightSlider pour correspondre au thème par défaut de PrestaShop ou fournir des ajustements visuels spécifiques au module.
- `ccarousel/lib/src/css/ccarousel.css`
  - Portée : Front-office.
  - Responsabilité : Pourrait être une feuille de style de base pour la structure du module ou un espace réservé. Compte tenu du nom, il s'agit probablement d'un style spécifique au module.
- `ccarousel/lib/src/css/lightslider.css`
  - Portée : Front-office.
  - Responsabilité : La feuille de style par défaut de la bibliothèque LightSlider. Elle fournit le style essentiel pour le conteneur du carrousel, les diapositives, les flèches de navigation et les points de pagination. Les développeurs peuvent remplacer ces styles dans le `custom.css` de leur thème ou en modifiant `ccarousel/css.css`.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :
  - `ccarousel/views/templates/hook/ccarousel.tpl`
    - Rendu dans : `displayHome` (et potentiellement d'autres hooks si configuré dans le module).
    - Sorties : La structure HTML pour un ou plusieurs carrousels. Ce template itère à travers les groupes de carrousels et leurs éléments associés, générant les éléments `<ul>` et `<li>` nécessaires que LightSlider attend. Il inclut des balises d'image, des intégrations vidéo ou du contenu HTML brut en fonction du type d'élément, ainsi que des liens. Il contient également probablement l'appel d'initialisation JavaScript pour LightSlider, transmettant les options de configuration récupérées des paramètres `gcarousel`.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - `ps_gcarousel` : Stocke les informations sur chaque groupe de carrousels.
    - `id_gcarousel` (PK, INT)
    - `name` (VARCHAR)
    - `active` (TINYINT)
    - `settings` (TEXT ou JSON, pour les options LightSlider sérialisées)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - `ps_gcitem` : Stocke les informations sur chaque diapositive/élément individuel.
    - `id_gcitem` (PK, INT)
    - `id_gcarousel` (FK vers `ps_gcarousel`, INT)
    - `position` (INT)
    - `active` (TINYINT)
    - `type` (VARCHAR, par exemple, 'image', 'video', 'text', 'html')
    - `content` (TEXT, stocke le chemin de l'image, l'URL de la vidéo ou le texte/HTML brut)
    - `link` (VARCHAR)
    - `title` (VARCHAR, pour le multilingue)
    - `description` (TEXT, pour le multilingue)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - `ps_configuration` : Stocke les valeurs de configuration spécifiques au module, telles que `CCAROUSEL_LIGHTSLIDER`, `MYPRESTA_UPDATES`, etc.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Met en file d'attente les fichiers CSS (`lightslider.css`, `ccarousel.css`) et JavaScript (`lightslider.js`) nécessaires pour que le carrousel fonctionne et soit stylisé correctement. |
| `displayHome` | Dans la zone de contenu principale de la page d'accueil. | Rend le template `ccarousel.tpl`, qui génère la structure HTML pour les groupes de carrousels actifs et leurs éléments, ainsi que le script d'initialisation LightSlider. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour vous assurer que vous utilisez la version la plus récente et la plus sécurisée du module « Carrousel de contenus personnalisés », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité et la compatibilité du module.
