---
title: "Blocs de Catégories Multiples - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Blocs de Catégories Multiples par MyPresta.eu."
sidebar:
  label: "Blocs de Catégories Multiples - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Multiple Categories Blocks sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/multiple-categories-blocks.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/multiple-categories-blocks/)
>
> ---


# Blocs de Catégories Multiples

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration serveur spéciale n'est habituellement nécessaire.

## 2. Présentation complète de la configuration (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Blocs de Catégories Multiples)

C'est l'écran de configuration principal où vous créerez et gérerez tous vos blocs de catégories personnalisés.

En entrant dans la page de configuration, vous verrez une liste des blocs de catégories existants (le cas échéant) et des options pour en ajouter de nouveaux.

#### **Ajouter / Modifier un bloc de catégories**

Lorsque vous cliquez sur "Ajouter un nouveau bloc" ou modifiez un bloc existant, les paramètres suivants vous seront présentés :

- **Nom du bloc :**

  - **Ce que fait ce paramètre :** C'est un nom interne pour votre référence dans le Back Office. Il vous aide à identifier les différents blocs.
  - **Effet de la modification de ce paramètre :** Affecte uniquement la façon dont vous voyez le bloc dans le panneau d'administration. Il n'est pas visible pour les clients.
  - **Valeur recommandée :** Un nom descriptif (par exemple, "Catégories Électronique Page d'accueil", "Vêtements Colonne Gauche").
  - **Scénario / exemple marchand :** Si vous avez un bloc pour "Mode Homme" dans la colonne de gauche, nommez-le "Colonne Gauche - Mode Homme".
- **Afficher le titre du bloc :**

  - **Ce que fait ce paramètre :** Détermine si un titre (par exemple, "Catégories") est affiché au-dessus de la liste des catégories dans le front office.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque activé (Oui) :* Un titre apparaîtra au-dessus du bloc de catégories. Vous pouvez définir ce titre dans le champ "Titre du bloc".
    - *Lorsque désactivé (Non) :* Aucun titre ne sera affiché, seulement la liste des catégories.
  - **Valeur recommandée :** "Oui" pour la plupart des blocs, car cela fournit un contexte au client.
  - **Scénario / exemple marchand :** Si vous voulez que votre bloc se fonde simplement dans le design sans titre explicite, réglez-le sur "Non".
- **Titre du bloc :** (Apparaît uniquement si "Afficher le titre du bloc" est Oui)

  - **Ce que fait ce paramètre :** Le texte réel qui sera affiché comme titre du bloc dans le front office. Ceci est multilingue.
  - **Effet de la modification de ce paramètre :** Modifie le titre visible pour les clients.
  - **Valeur recommandée :** Un titre clair et concis (par exemple, "Acheter par catégorie", "Nos produits", "Départements").
  - **Scénario / exemple marchand :** Pour un bloc affichant uniquement les catégories "Électronique", vous pourriez définir le titre sur "Électronique".
- **Hook pour afficher le bloc :**

  - **Ce que fait ce paramètre :** Sélectionne l'endroit où ce bloc de catégories apparaîtra dans votre boutique. Les hooks sont des points d'affichage spécifiques dans votre thème PrestaShop.
  - **Effet de la modification de ce paramètre :** Détermine l'emplacement physique du bloc sur votre site web.
  - **Valeur recommandée :** Dépend de votre design. Les choix courants sont `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayHome`.
  - **Scénario / exemple marchand :** Pour afficher un bloc dans la barre latérale gauche, sélectionnez `displayLeftColumn`. Pour l'afficher dans le pied de page, sélectionnez `displayFooter`.
- **Catégorie racine :**

  - **Ce que fait ce paramètre :** C'est le point de départ (le "parent") pour les catégories affichées dans ce bloc spécifique. Seule cette catégorie et ses sous-catégories seront affichées.
  - **Effet de la modification de ce paramètre :**
    - *Sélectionner "Accueil" :* Le bloc affichera toutes les catégories à partir du tout début de votre arborescence de catégories.
    - *Sélectionner une catégorie spécifique (par exemple, "Électronique") :* Le bloc n'affichera que "Électronique" et toutes ses sous-catégories.
  - **Valeur recommandée :** Choisissez la catégorie de plus haut niveau qui définit la portée de ce bloc.
  - **Scénario / exemple marchand :** Si vous voulez un bloc spécifiquement pour les "Vêtements", sélectionnez votre catégorie "Vêtements" ici.
- **Profondeur maximale :**

  - **Ce que fait ce paramètre :** Contrôle le nombre de niveaux de sous-catégories affichés dans ce bloc, à partir de la Catégorie racine.
  - **Effet de la modification de ce paramètre :**
    - *Réglé sur 1 :* Seule la Catégorie racine elle-même sera affichée (si "Afficher la Catégorie racine" est Oui).
    - *Réglé sur 2 :* La Catégorie racine et ses sous-catégories immédiates seront affichées.
    - *Réglé sur 0 (ou vide) :* Toutes les sous-catégories, quelle que soit leur profondeur, seront affichées.
  - **Valeur recommandée :** 2 ou 3 pour la plupart des blocs de colonnes afin de les garder gérables. 0 pour les blocs de pied de page si vous voulez un plan de site complet.
  - **Scénario / exemple marchand :** Si votre catégorie "Électronique" a des sous-catégories comme "Appareils photo" et "Ordinateurs portables", et que "Appareils photo" a "Appareils photo reflex" et "Hybrides", régler la profondeur sur 2 afficherait "Électronique > Appareils photo, Ordinateurs portables". Régler sur 3 afficherait "Électronique > Appareils photo > Appareils photo reflex, Hybrides, Ordinateurs portables".
- **Dynamique (ouvrir l'arborescence de la catégorie actuelle) :**

  - **Ce que fait ce paramètre :** Lorsqu'un client navigue vers une page de catégorie, cette option détermine si le bloc de catégories s'étend automatiquement pour afficher la catégorie actuelle et ses sous-catégories.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque activé (Oui) :* Si un client est sur la page "Appareils photo reflex", le bloc de catégories étendra automatiquement "Électronique > Appareils photo > Appareils photo reflex" pour afficher le chemin.
    - *Lorsque désactivé (Non) :* Le bloc de catégories restera dans son état replié par défaut, quelle que soit la page actuelle.
  - **Valeur recommandée :** "Oui" pour une meilleure expérience utilisateur, car cela aide les clients à comprendre leur emplacement actuel dans l'arborescence des catégories.
  - **Scénario / exemple marchand :** Ceci est particulièrement utile dans les colonnes latérales pour maintenir la navigation pertinente au contexte de navigation actuel de l'utilisateur.
- **Afficher la catégorie racine :**

  - **Ce que fait ce paramètre :** Contrôle si la "Catégorie racine" elle-même (celle que vous avez sélectionnée ci-dessus) est affichée comme premier élément du bloc.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque activé (Oui) :* La Catégorie racine sera le premier élément cliquable du bloc.
    - *Lorsque désactivé (Non) :* Le bloc commencera à s'afficher à partir des sous-catégories immédiates de la Catégorie racine.
  - **Valeur recommandée :** "Oui" si la Catégorie racine est une catégorie large comme "Acheter par département". "Non" si la Catégorie racine n'est qu'un regroupement logique et que vous voulez commencer directement par ses sous-catégories (par exemple, un bloc "Marques" où "Marques" elle-même n'est pas une catégorie de produits).
  - **Scénario / exemple marchand :** Si votre Catégorie racine est "Vêtements Homme" et que vous voulez que ce soit le lien principal, réglez sur "Oui". Si vous voulez que le bloc commence directement par "Chemises", "Pantalons", etc., réglez sur "Non".
- **Afficher le nombre de produits :**

  - **Ce que fait ce paramètre :** Affiche le nombre de produits disponibles dans chaque catégorie à côté de son nom dans le bloc.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque activé (Oui) :* Les catégories apparaîtront sous la forme "Nom de la catégorie (X)".
    - *Lorsque désactivé (Non) :* Seul le nom de la catégorie sera affiché.
  - **Valeur recommandée :** "Oui" peut être utile pour les clients afin d'évaluer la taille d'une catégorie, mais "Non" peut conduire à un aspect plus épuré. Testez les deux pour voir ce qui convient à votre design.
  - **Scénario / exemple marchand :** Si vous voulez afficher "T-shirts (125)" à côté du nom de la catégorie, activez cette option.
- **Afficher les catégories sans produits :**

  - **Ce que fait ce paramètre :** Détermine si les catégories qui n'ont actuellement aucun produit qui leur est attribué sont toujours affichées dans le bloc.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque activé (Oui) :* Les catégories vides apparaîtront toujours.
    - *Lorsque désactivé (Non) :* Les catégories vides seront masquées du bloc.
  - **Valeur recommandée :** "Non" pour éviter les impasses pour les clients et garder votre navigation propre. N'activez "Oui" que si vous avez une raison spécifique d'afficher les catégories à venir.
  - **Scénario / exemple marchand :** Si vous développez une nouvelle gamme de produits et avez créé des catégories mais n'avez pas encore ajouté de produits, vous pourriez temporairement activer "Oui" pour des tests internes, mais généralement "Non" pour les boutiques en ligne.
- **Trier par :**

  - **Ce que fait ce paramètre :** Définit l'ordre de tri des catégories dans le bloc.
  - **Effet de la modification de ce paramètre :** Modifie la séquence dans laquelle les catégories sont listées.
  - **Valeur recommandée :** "Position" (ordre PrestaShop par défaut) ou "Nom" (alphabétique).
  - **Scénario / exemple marchand :** Si vous voulez que vos catégories apparaissent par ordre alphabétique, sélectionnez "Nom". Si vous préférez les trier manuellement dans la section Catégories de PrestaShop, sélectionnez "Position".
- **Ordre de tri :**

  - **Ce que fait ce paramètre :** Spécifie l'ordre croissant ou décroissant pour le paramètre "Trier par".
  - **Effet de la modification de ce paramètre :**
    - *ASC :* Croissant (A-Z, 1-9).
    - *DESC :* Décroissant (Z-A, 9-1).
  - **Valeur recommandée :** "ASC" dans la plupart des cas.
  - **Scénario / exemple marchand :** Si vous avez trié par "Nom" et que vous voulez A-Z, sélectionnez "ASC".

#### **Gestion des blocs existants**

Après avoir créé des blocs, vous verrez une liste avec des options pour :

- **Modifier :** Modifier les paramètres d'un bloc existant.
- **Supprimer :** Supprimer un bloc de votre boutique.
- **Activer/Désactiver :** Activer ou désactiver rapidement un bloc sans supprimer sa configuration.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | **Nom du bloc** | Descriptif | Identifiant interne du bloc. |
| | **Afficher le titre du bloc** | Oui | Affiche/masque le titre du bloc pour les clients. |
| | **Titre du bloc** | "Catégories" (exemple) | Le titre visible du bloc (multilingue). |
| | **Hook pour afficher le bloc** | `displayLeftColumn` | Détermine où le bloc apparaît dans votre thème. |
| | **Catégorie racine** | Accueil | Définit le point de départ des catégories dans ce bloc. |
| | **Profondeur maximale** | 0 (Tous) | Limite le nombre de niveaux de sous-catégories affichés. |
| | **Dynamique (ouvrir l'arborescence de la catégorie actuelle)** | Oui | Développe automatiquement l'arborescence vers la catégorie actuelle. |
| | **Afficher la catégorie racine** | Oui | Affiche/masque la catégorie racine sélectionnée elle-même. |
| | **Afficher le nombre de produits** | Non | Affiche/masque le nombre de produits à côté des noms de catégorie. |
| | **Afficher les catégories sans produits** | Non | Affiche/masque les catégories qui n'ont pas de produits. |
| | **Trier par** | Position | Trie les catégories par position ou par nom. |
| | **Ordre de tri** | ASC | Trie les catégories par ordre croissant ou décroissant. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Mon nouveau bloc de catégories n'apparaît pas sur le front office.**
R1 :

-   **Vérifier le Hook :** Assurez-vous d'avoir sélectionné le bon "Hook pour afficher le bloc" dans la configuration du module.
-   **Position du module :** Allez dans **Design > Positions** (ou **Modules > Positions** dans les versions plus anciennes). Recherchez `Blocs de Catégories Multiples` et assurez-vous qu'il est accroché à la position que vous avez sélectionnée et qu'il n'est pas désactivé. Vous devrez peut-être déplacer sa position vers le haut ou vers le bas si d'autres modules se chevauchent.
-   **Statut du module :** Dans la configuration du module, assurez-vous que le bloc est "Activé" (coche verte).
-   **Cache :** Videz le cache de votre PrestaShop (**Paramètres avancés > Performances > Vider le cache**).

**Q2 : Les catégories de mon bloc ne s'étendent pas ou ne s'affichent pas correctement.**
R2 :

-   **Catégorie racine et profondeur maximale :** Vérifiez vos paramètres "Catégorie racine" et "Profondeur maximale". Si la profondeur maximale est trop faible, les sous-catégories n'apparaîtront pas. Si la catégorie racine est incorrecte, vous verrez la mauvaise arborescence.
-   **Option dynamique :** Si vous vous attendez à ce que l'arborescence s'étende automatiquement lors de la navigation, assurez-vous que "Dynamique (ouvrir l'arborescence de la catégorie actuelle)" est réglé sur "Oui".
-   **Catégories sans produits :** Si des catégories sont manquantes, vérifiez "Afficher les catégories sans produits". Si c'est "Non", les catégories sans produits seront masquées.

**Q3 : Le style du bloc de catégories ne correspond pas à mon thème.**
R3 :

-   Le module essaie d'hériter les styles de votre thème PrestaShop actif. Cependant, les thèmes personnalisés peuvent nécessiter des ajustements CSS mineurs.
-   Vous pouvez souvent remplacer le CSS par défaut du module en ajoutant des règles au fichier `custom.css` ou `theme.css` de votre thème. (Voir la section 7.5 pour les détails développeur sur le CSS du module).
-   Pour PrestaShop 1.7/8/9, assurez-vous d'utiliser le fichier `multicatblock-prestashop17.css` si votre thème l'exige (ceci est géré automatiquement par le module).

**Q4 : Comment traduire le titre du bloc dans d'autres langues ?**
R4 :

-   Lors de la modification d'un bloc, le champ "Titre du bloc" aura des drapeaux de langue à côté. Cliquez sur chaque drapeau pour saisir le titre pour cette langue spécifique.
-   Enregistrez vos modifications après avoir saisi toutes les traductions.

**Q5 : Pourquoi certaines catégories sont-elles manquantes dans le bloc, même si elles ont des produits ?**
R5 :

-   **Portée de la catégorie racine :** Assurez-vous que les catégories manquantes sont bien des descendants (sous-catégories) de la "Catégorie racine" que vous avez sélectionnée pour ce bloc spécifique. Si elles sont en dehors de cette branche, elles n'apparaîtront pas.
-   **Statut de la catégorie :** Vérifiez dans **Catalogue > Catégories** que les catégories manquantes sont "Activées" et "Affichées" (visibles).
-   **Association de produits :** Vérifiez à nouveau que les produits sont correctement associés aux catégories en question.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module Blocs de Catégories Multiples (`multicatblocks`) suit une architecture de module PrestaShop standard, exploitant principalement la classe `Module` pour ses fonctionnalités et sa configuration principales. Il s'intègre au front-office via divers hooks d'affichage et utilise des templates Smarty pour le rendu. Le module stocke ses paramètres de configuration dans la table `ps_configuration`, permettant de définir plusieurs blocs de catégories distincts. Il utilise une logique de rendu d'arbre personnalisée pour construire la navigation par catégorie.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs front-office ou back-office dédiés. Toute la logique de configuration et de rendu front-office est gérée dans le fichier principal du module `index.php` et ses templates et hooks associés.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit pas de classes `ObjectModel` personnalisées. Toute la manipulation des données pour les catégories repose sur la classe `Category` native de PrestaShop.

La logique principale réside dans `multicatblocks/index.php` :

-   **Classe `Multicatblocks` :** Étend `Module`.
    *   **`__construct()` :** Initialise les détails du module, configure les onglets et enregistre les hooks.
    *   **`install()` :** Enregistre les hooks nécessaires (`displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayHome`, `displayProductButtons` - bien que ce dernier puisse être pour un usage hérité/interne car il n'est pas exposé dans la configuration), crée les entrées de configuration par défaut.
    *   **`uninstall()` :** Nettoie les entrées de configuration.
    *   **`getContent()` :** Gère la soumission et l'affichage du formulaire de configuration du Back Office. Il gère la création, la modification et la suppression des blocs de catégories, stockant leurs paramètres dans `Configuration::updateValue()`.
    *   **`hookDisplayHeader()` :** Injecte les ressources CSS et JavaScript dans la section `<head>` du front office.
    *   **`hookDisplayLeftColumn()`, `hookDisplayRightColumn()`, `hookDisplayFooter()`, `hookDisplayHome()`, `hookDisplayProductButtons()` :** Ces méthodes sont responsables de la récupération des blocs configurés pour leurs hooks respectifs, de la récupération des données de catégorie, de la préparation des variables Smarty et du rendu du template `multicatblock.tpl` ou `multicatblock-footer.tpl`.
    *   **`getCategoryTree()` :** Une méthode interne cruciale qui récupère et structure récursivement les données de catégorie en fonction de la configuration du bloc (catégorie racine, profondeur maximale, nombre de produits, etc.).

### 4.4 Ressources JavaScript (`views/js/`)

-   **`multicatblocks/js/script.js`** :
    *   **Portée :** Front-office.
    *   **Objectif :** Gère le comportement interactif principal de l'arborescence des catégories, tel que l'expansion/la réduction des sous-catégories. Il lie probablement les événements de clic aux liens de catégorie ou aux icônes d'expansion/réduction.
    *   **Détails :** Ce script est responsable du comportement "dynamique", garantissant que lorsqu'une catégorie est cliquée, ses sous-catégories sont révélées ou masquées, et potentiellement en surbrillance le chemin de la catégorie active.
-   **`multicatblocks/js/tree.js`** :
    *   **Portée :** Front-office.
    *   **Objectif :** Probablement une dépendance ou une version plus ancienne de la fonctionnalité d'arbre, ou gère spécifiquement l'état initial et le rendu de la structure de l'arbre.
    *   **Détails :** Pourrait contenir la logique d'initialisation de l'arbre, la gestion des appels AJAX pour les données de catégorie (le cas échéant, bien que le module semble rendre l'arbre complet au chargement de la page), ou la gestion de l'état de l'arbre.
-   **`multicatblocks/lib/searchTool/views/js/autocomplete.js`** :
    *   **Portée :** Back-office (configuration admin).
    *   **Objectif :** Fournit une fonctionnalité d'autocomplétion pour la sélection de catégories dans le formulaire de configuration du module, spécifiquement pour le paramètre "Catégorie racine".
    *   **Détails :** Se lie à un champ de saisie, effectue des requêtes AJAX à un contrôleur d'administration PrestaShop (probablement `AdminCategories` ou un contrôleur personnalisé s'il est présent, bien qu'aucun ne soit listé) pour rechercher des catégories, et affiche des suggestions.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`multicatblocks/css.css`** :
    *   **Portée :** Front-office.
    *   **Objectif :** Style général des blocs de catégories.
    *   **Détails :** Contient des règles de base pour les éléments de liste, les liens et potentiellement les icônes d'expansion/réduction. Les sélecteurs clés peuvent inclure `.multicatblock`, `.multicatblock_list`, `.multicatblock_item`.
-   **`multicatblocks/lib/searchTool/views/css/autocomplete.css`** :
    *   **Portée :** Back-office (configuration admin).
    *   **Objectif :** Styles pour le champ de recherche d'autocomplétion et sa liste déroulante de suggestions.
    *   **Détails :** Garantit que l'outil de recherche de catégories dans le panneau d'administration est visuellement cohérent et convivial.
-   **`multicatblocks/multicatblock-prestashop17.css`** :
    *   **Portée :** Front-office.
    *   **Objectif :** Surcharges spécifiques ou styles supplémentaires adaptés aux thèmes PrestaShop 1.7.x, 8.x et 9.x (par exemple, le thème Classic).
    *   **Détails :** Résout les incohérences potentielles de mise en page ou de style qui pourraient survenir entre les anciennes versions de PrestaShop et les nouvelles structures de thème. Ceci est chargé conditionnellement en fonction de la version de PS.
-   **`multicatblocks/multicatblock.css`** :
    *   **Portée :** Front-office.
    *   **Objectif :** Style principal des blocs de catégories, probablement pour les anciennes versions de PrestaShop (1.5.x, 1.6.x) ou comme solution de repli.
    *   **Détails :** Similaire à `css.css`, mais peut contenir des règles plus spécifiques pour les anciennes structures de thème.
-   **`multicatblocks/views/css/mcb-admin.css`** :
    *   **Portée :** Back-office (configuration admin).
    *   **Objectif :** Style de la page de configuration du module dans le Back Office de PrestaShop.
    *   **Détails :** Garantit que le formulaire de paramètres du module, la liste des blocs et les autres éléments de l'interface utilisateur d'administration sont bien présentés et cohérents avec le thème d'administration de PrestaShop.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/` - bien que les fichiers soient directement dans `multicatblocks/`) :**
    *   **`multicatblocks/multicatblock.tpl`** :
        *   **Accroché dans :** `displayLeftColumn`, `displayRightColumn`, `displayHome`, `displayProductButtons`.
        *   **Sorties :** La structure principale du bloc de catégories, y compris le titre (si activé) et l'arborescence de catégories récursive générée par `category-tree-branch.tpl`.
    *   **`multicatblocks/multicatblock-footer.tpl`** :
        *   **Accroché dans :** `displayFooter`.
        *   **Sorties :** Une variation du bloc de catégories spécifiquement pour le pied de page, potentiellement avec des styles ou des éléments structurels différents. Il utilise également `category-tree-branch-footer.tpl`.
    *   **`multicatblocks/category-tree-branch.tpl`** :
        *   **Accroché dans :** Inclus par `multicatblock.tpl`.
        *   **Sorties :** Rend récursivement une seule branche de l'arborescence des catégories. Il itère à travers les sous-catégories, gère les limites de profondeur et affiche le nombre de produits.
    *   **`multicatblocks/category-tree-branch-footer.tpl`** :
        *   **Accroché dans :** Inclus par `multicatblock-footer.tpl`.
        *   **Sorties :** Similaire à `category-tree-branch.tpl` mais adapté à la structure du bloc de pied de page.
-   **Templates d'administration (`views/templates/admin/` - bien que `shell.tpl` soit dans `multicatblocks/views/templates/admin/`) :**
    *   **`multicatblocks/views/templates/admin/shell.tpl`** :
        *   **Objectif :** Le template principal de la page de configuration du module dans le Back Office.
        *   **Sorties :** Le formulaire pour ajouter/modifier des blocs, la liste des blocs existants et potentiellement d'autres éléments spécifiques à l'administration.
-   **Templates de bibliothèque :**
    *   **`multicatblocks/lib/searchTool/views/scripts.tpl`** :
        *   **Objectif :** Inclut probablement le JavaScript nécessaire à l'outil de recherche d'autocomplétion utilisé dans la configuration d'administration.
        *   **Sorties :** Balises `<script>` ou JavaScript en ligne pour la fonctionnalité d'autocomplétion.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** :
    *   Le module ne crée pas de tables SQL personnalisées.
    *   Toute la configuration de chaque bloc de catégories est stockée dans la table `ps_configuration`. Les paramètres de chaque bloc sont sérialisés et stockés sous une clé de configuration unique (par exemple, `MULTICATBLOCKS_BLOCKS`).
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Injecte les fichiers CSS et JavaScript du module. |
| `displayLeftColumn` | Dans la barre latérale gauche du front-office. | Rend un bloc de catégories configuré dans la colonne de gauche. |
| `displayRightColumn` | Dans la barre latérale droite du front-office. | Rend un bloc de catégories configuré dans la colonne de droite. |
| `displayFooter` | Dans la section du pied de page du front-office. | Rend un bloc de catégories configuré dans le pied de page. |
| `displayHome` | Sur la page d'accueil (si le thème prend en charge le hook `displayHome`). | Rend un bloc de catégories configuré sur la page d'accueil. |
| `displayProductButtons` | Sur la page produit, près du bouton "Ajouter au panier". | Rend un bloc de catégories configuré sur les pages produit (moins courant pour ce module, mais disponible). |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module "Blocs de Catégories Multiples", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question que vous pourriez avoir.
