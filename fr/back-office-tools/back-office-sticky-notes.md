---
title: "Notes autocollantes du Back office - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Notes autocollantes du Back office' par MyPresta.eu."
sidebar:
  label: "Notes autocollantes du Back office - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Back office Sticky Notes sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/back-office-sticky-notes.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/back-office-sticky-notes/)
>
> ---


# Notes autocollantes du Back office

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes et préinstallées sur la plupart des environnements d'hébergement.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à l'écran de configuration principal du module « Notes autocollantes du Back office ». C'est ici que vous gérez vos notes autocollantes.

La page de configuration elle-même n'a pas beaucoup de « paramètres » au sens traditionnel (comme des interrupteurs marche/arrêt). Au lieu de cela, c'est votre centre pour créer, modifier et gérer toutes vos notes autocollantes.

#### **Ajouter une nouvelle note autocollante**

En haut de la page de configuration, vous trouverez généralement un formulaire ou une section pour ajouter une nouvelle note.

-   **Contenu de la note (Zone de texte) :**

    -   **Ce que fait ce paramètre :** C'est ici que vous tapez le message ou le rappel réel pour votre note autocollante.
    -   **Effet de la modification de ce paramètre :** Tout ce que vous tapez ici sera affiché sur la note autocollante dans votre back office.
    -   **Valeur recommandée :** Soyez concis et clair. Utilisez des puces ou des phrases courtes pour la lisibilité.
    -   **Scénario / exemple pour le marchand :** « N'oubliez pas de faire un suivi avec le client #1234 concernant le statut de sa commande. » ou « Nouvelles images de produits pour la 'Collection d'été' à livrer avant vendredi. »
-   **Couleur de la note (Sélecteur de couleurs) :**

    -   **Ce que fait ce paramètre :** Vous permet de choisir la couleur de fond de votre note autocollante.
    -   **Effet de la modification de ce paramètre :** La note autocollante apparaîtra avec la couleur choisie dans le back office. Différentes couleurs peuvent aider à catégoriser les notes ou à souligner l'urgence.
    -   **Valeur recommandée :** Choisissez des couleurs qui ressortent mais ne sont pas trop distrayantes. Vous pourriez utiliser le rouge pour les notes urgentes, le jaune pour les rappels généraux et le vert pour les tâches terminées.
    -   **Scénario / exemple pour le marchand :** Définissez une note concernant un bug critique en rouge, et une note concernant une nouvelle idée marketing en jaune.
-   **Bouton Enregistrer / Ajouter une note :**

    -   **Ce que fait ce paramètre :** Soumet le contenu et la couleur que vous avez choisis pour créer une nouvelle note autocollante.
    -   **Effet de la modification de ce paramètre :** Une nouvelle note autocollante sera créée et apparaîtra sur vos pages de back office. Elle sera également listée dans la section « Notes existantes » ci-dessous.
    -   **Valeur recommandée :** Cliquez sur ce bouton après avoir finalisé le contenu et la couleur de votre note.
    -   **Scénario / exemple pour le marchand :** Après avoir tapé votre rappel et sélectionné une couleur, cliquez sur « Enregistrer » pour activer la note.

#### **Gestion des notes autocollantes existantes**

Sous la section « Ajouter une nouvelle note », vous verrez une liste ou un tableau de toutes les notes autocollantes que vous avez déjà créées.

-   **Liste des notes (Tableau/Affichage) :**

    -   **Ce que fait ce paramètre :** Affiche toutes les notes autocollantes actives, leur contenu et leur couleur attribuée.
    -   **Effet de la modification de ce paramètre :** C'est un affichage de vos notes actuelles. Vous pouvez les revoir visuellement ici.
    -   **Valeur recommandée :** Revoyez régulièrement cette liste pour vous assurer que les notes sont toujours pertinentes.
    -   **Scénario / exemple pour le marchand :** Scannez rapidement la liste pour voir toutes les tâches ou rappels en attente.
-   **Bouton Modifier (pour chaque note) :**

    -   **Ce que fait ce paramètre :** Vous permet de modifier le contenu ou la couleur d'une note autocollante existante.
    -   **Effet de la modification de ce paramètre :** Cliquer sur ce bouton chargera généralement le contenu de la note dans le formulaire « Ajouter une nouvelle note » (qui pourrait passer en mode « Modifier la note »), vous permettant d'apporter des modifications. Une fois enregistrée, la note sera mise à jour dans tout votre back office.
    -   **Valeur recommandée :** Utilisez ceci pour mettre à jour les statuts des tâches, ajouter plus de détails ou modifier l'urgence.
    -   **Scénario / exemple pour le marchand :** Une note dit « Vérifier les nouvelles images de produits. » Une fois vérifiée, vous pouvez la modifier en « Nouvelles images de produits approuvées. »
-   **Bouton Supprimer (pour chaque note) :**

    -   **Ce que fait ce paramètre :** Supprime définitivement une note autocollante.
    -   **Effet de la modification de ce paramètre :** La note disparaîtra de votre back office et ne sera plus listée dans la configuration. Cette action est généralement irréversible.
    -   **Valeur recommandée :** Supprimez les notes uniquement lorsque la tâche est terminée ou que l'information n'est plus pertinente.
    -   **Scénario / exemple pour le marchand :** Une fois qu'un problème de commande est résolu, supprimez la note autocollante qui y est liée.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | **Contenu de la note (Zone de texte)** | Texte clair et concis | Le message réel affiché sur la note autocollante. |
| Page de configuration du module | **Couleur de la note (Sélecteur de couleurs)** | Sélectionné par l'utilisateur | Définit la couleur de fond de la note pour la catégorisation/l'urgence. |
| Page de configuration du module | **Bouton Enregistrer / Ajouter une note** | Cliquer après avoir défini le contenu/la couleur | Crée une nouvelle note autocollante visible dans le back office. |
| Page de configuration du module | **Bouton Modifier (par note)** | Cliquer pour modifier | Permet de mettre à jour le contenu ou la couleur d'une note existante. |
| Page de configuration du module | **Bouton Supprimer (par note)** | Cliquer pour supprimer | Supprime définitivement une note autocollante du back office. |

## 3. Dépannage pour le marchand et questions fréquemment posées (FAQ)

**Q1 : Mes notes autocollantes n'apparaissent pas dans le back office après que je les ai enregistrées.**
R1 :

-   **Vider le cache :** La raison la plus courante des problèmes d'affichage est la mise en cache. Allez dans **Paramètres avancés > Performances** dans votre back office PrestaShop. Cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes).
-   **Vérifier le statut du module :** Assurez-vous que le module est toujours installé et activé dans **Modules > Gestionnaire de modules**.
-   **Cache du navigateur :** Essayez de vider le cache de votre navigateur ou d'ouvrir votre back office dans une fenêtre de navigation privée/incognito pour exclure les problèmes spécifiques au navigateur.

**Q2 : Puis-je déplacer les notes autocollantes sur l'écran ?**
R2 : Oui, une fois qu'une note autocollante est affichée dans votre back office, vous devriez pouvoir cliquer et la faire glisser vers n'importe quelle position sur la page. Le module est conçu pour mémoriser sa position pour vous.

**Q3 : Les différents administrateurs peuvent-ils voir les notes autocollantes des autres ?**
R3 : Oui, par défaut, toutes les notes autocollantes créées via ce module sont visibles par tous les administrateurs ayant accès au back office. C'est une fonctionnalité clé pour la collaboration d'équipe.

**Q4 : Les couleurs de mes notes autocollantes semblent étranges ou ne s'appliquent pas correctement.**
R4 :

-   **Vérifier le sélecteur de couleurs :** Assurez-vous d'utiliser correctement l'outil de sélecteur de couleurs sur la page de configuration du module.
-   **Conflits de thème personnalisé :** Si vous utilisez un thème de back office fortement personnalisé, il pourrait y avoir des conflits CSS. Essayez de passer temporairement au thème de back office PrestaShop par défaut pour voir si le problème persiste. Si cela résout le problème, le CSS de votre thème est probablement en train de remplacer les styles du module.
-   **Compatibilité du navigateur :** Assurez-vous que votre navigateur est à jour.

**Q5 : Comment traduire l'interface du module dans une autre langue ?**
R5 :

-   Allez dans **International > Traductions** dans votre back office PrestaShop.
-   Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez la langue que vous souhaitez traduire.
-   Recherchez « Notes autocollantes du Back office » dans la liste et traduisez les chaînes de texte disponibles.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Notes autocollantes du Back office » est un module PrestaShop classique principalement conçu pour le Back Office. Il tire parti de l'architecture des modules de PrestaShop, utilisant la classe `Module` pour l'installation, la désinstallation et la configuration. La fonctionnalité principale tourne autour de l'affichage et de la gestion des « notes autocollantes » créées par l'utilisateur au sein du panneau d'administration. Il repose fortement sur JavaScript pour l'interaction front-end (glisser, positionner) et AJAX pour la sauvegarde des données des notes. La persistance des données est gérée via `ps_configuration` pour les paramètres du module et probablement des tables de base de données personnalisées ou `ps_configuration` pour les notes elles-mêmes.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne semble pas utiliser de contrôleurs d'administration Front-Office ou Back-Office dédiés au sens traditionnel du MVC de PrestaShop (c'est-à-dire des fichiers dans `controllers/front/` ou `controllers/admin/`). Toute la configuration et la gestion AJAX semblent être gérées directement dans le fichier principal du module (`addstickynote.php`) en utilisant la méthode `getContent()` pour la configuration et potentiellement les méthodes `ajaxProcess` ou des appels AJAX directs pour la gestion dynamique des notes.

### 4.3 Classes et modèles de base (`classes/`)

D'après l'inventaire fourni, il n'y a pas de classes personnalisées ou de définitions `ObjectModel` dans un répertoire `classes/`. Cela suggère que les données des notes autocollantes sont probablement stockées directement dans la table `ps_configuration`, où le contenu, la couleur et la position de chaque note pourraient être sérialisés ou stockés comme des clés de configuration individuelles.

### 4.4 Actifs JavaScript (`views/js/`)

Le module repose fortement sur JavaScript pour ses fonctionnalités interactives dans le back office.

-   `stickynotes/js/advajax.js` :
    -   **Portée :** Back-office.
    -   **Responsabilité :** Probablement un script utilitaire AJAX personnalisé, éventuellement un wrapper pour les fonctions AJAX de jQuery ou une implémentation autonome pour gérer la communication asynchrone avec le backend PHP du module pour la sauvegarde/le chargement des notes.
-   `stickynotes/js/joverlay.js` :
    -   **Portée :** Back-office.
    -   **Responsabilité :** Suggère une fonctionnalité liée aux superpositions ou aux popups modales, potentiellement utilisée pour éditer le contenu des notes dans une interface plus conviviale, ou pour afficher des messages de confirmation.
-   `stickynotes/js/jscolor/jscolor.js` :
    -   **Portée :** Back-office (spécifiquement sur la page de configuration du module).
    -   **Responsabilité :** Une bibliothèque JavaScript tierce pour fournir une interface de sélecteur de couleurs. Elle est utilisée pour permettre aux administrateurs de sélectionner la couleur de fond de leurs notes autocollantes.
-   `stickynotes/js/script.js` :
    -   **Portée :** Back-office.
    -   **Responsabilité :** Il s'agit probablement du script principal pour la logique front-end du module. Il gérerait :
        -   L'initialisation des notes autocollantes au chargement de la page.
        -   La fonctionnalité de glisser-déposer pour le repositionnement des notes.
        -   La sauvegarde des positions des notes via AJAX.
        -   Les écouteurs d'événements pour l'édition/la suppression des notes.
        -   L'interaction avec `advajax.js` pour la persistance des données.
        -   Potentiellement le rendu dynamique de nouvelles notes.
-   `stickynotes/js/script17.js` :
    -   **Portée :** Back-office (spécifique à PrestaShop 1.7.x et 8.x).
    -   **Responsabilité :** Ce script contient probablement des adaptations ou du code spécifique pour les environnements PrestaShop 1.7+, abordant les différences dans la structure DOM, les versions de jQuery ou les changements de thème du back office par rapport aux versions plus anciennes de PrestaShop (1.5/1.6). Il assurerait la compatibilité et le bon fonctionnement sur les nouvelles plateformes.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module inclut des fichiers CSS pour styliser l'apparence des notes autocollantes.

-   `stickynotes/css/stickynotes-twig-shit.css` :
    -   **Portée :** Style d'administration du back-office.
    -   **Responsabilité :** Le nom suggère que ce fichier contient des ajustements de style spécifiques ou des remplacements pour les back offices de PrestaShop 1.7+, qui utilisent le templating Twig. Il cible probablement des éléments au sein du nouveau thème du back office pour garantir que les notes sont affichées correctement et de manière cohérente.
    -   **Sélecteurs CSS clés :** `.sticky-note`, `.sticky-note-content`, `.sticky-note-header` (hypothétique, basé sur les conventions de nommage courantes).
-   `stickynotes/css/stickynotes.css` :
    -   **Portée :** Style d'administration du back-office.
    -   **Responsabilité :** Il s'agit de la feuille de style principale pour les notes autocollantes, définissant leur apparence par défaut, leur positionnement et leurs états interactifs (par exemple, lorsqu'elles sont glissées). Elle contiendrait des styles généraux applicables à différentes versions de PrestaShop.
    -   **Sélecteurs CSS clés :** `.sticky-note`, `.draggable`, `.resizable`, `.note-text`, `.note-controls` (hypothétique). Les développeurs peuvent remplacer ces classes dans leurs thèmes de back office personnalisés si nécessaire.

### 4.6 Structure des templates Smarty (`views/templates/`)

Le module utilise un seul template Smarty pour le rendu des notes autocollantes dans le back office.

-   **Templates de hook (`views/templates/hook/`)** :
    -   `stickynotes/sticky-notes-back-office.tpl` :
        -   **Rendu dans le hook :** Ce template est probablement accroché à un hook global du back office, tel que `displayBackOfficeHeader` ou `displayAdminAfterHeader`, pour injecter la structure HTML et l'initialisation JavaScript nécessaires aux notes autocollantes sur toutes les pages d'administration.
        -   **Sortie du bloc visuel :** Il génère les conteneurs HTML pour les notes autocollantes, incluant potentiellement un template caché pour les nouvelles notes, et les appels JavaScript pour initialiser l'affichage et la fonctionnalité de glisser-déposer des notes. Il contiendrait également la logique pour itérer sur les notes existantes et les rendre.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Ce module ne semble pas créer de tables SQL personnalisées. Il est très probable que toutes les données des notes autocollantes (contenu, couleur, position, ID) soient stockées dans la table `ps_configuration`. Chaque note pourrait correspondre à une clé de configuration `PS_STICKY_NOTE_X` unique, où `X` est un identifiant, et la valeur est un tableau sérialisé ou une chaîne JSON contenant les propriétés de la note.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayBackOfficeHeader` | Exécuté dans la section `<head>` de chaque page du back office. | Injecte les fichiers CSS et JavaScript requis pour la fonctionnalité et le style des notes autocollantes. |
| `displayAdminAfterHeader` (ou similaire) | Exécuté après l'en-tête principal de chaque page du back office. | Rend la structure HTML des notes autocollantes et initialise leur affichage et leur comportement interactif. |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses médias (JS/CSS). | Potentiellement utilisé pour charger conditionnellement les actifs JS/CSS en fonction de la page d'administration actuelle, bien que `displayBackOfficeHeader` soit plus courant pour les actifs globaux. |
| `actionModuleInstall` | Exécuté lors de l'installation du module. | Crée les entrées de configuration initiales dans `ps_configuration` (le cas échéant) et enregistre les hooks nécessaires. |
| `actionModuleUninstall` | Exécuté lors de la désinstallation du module. | Nettoie les entrées de configuration et désenregistre les hooks. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour télécharger les dernières versions du module « Notes autocollantes du Back office », veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
"""
