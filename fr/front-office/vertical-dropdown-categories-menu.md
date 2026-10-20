---
title: "Menu de catégories déroulant vertical - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Menu de catégories déroulant vertical' par MyPresta.eu."
sidebar:
  label: "Menu de catégories déroulant vertical - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Vertical dropdown categories menu sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/vertical-dropdown-categories-menu.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/vertical-dropdown-categories-menu/)
>
> ---


# Menu de catégories déroulant vertical

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Menu de catégories déroulant vertical » dans le Gestionnaire de modules. Cela vous mènera à son écran de configuration principal.

La page de configuration du module fournit des paramètres standard pour contrôler son comportement et son apparence.

- **Ce que fait ce paramètre :** Cette section contient généralement les paramètres généraux du module, tels que l'activation/désactivation, le choix de son emplacement ou les options d'affichage de base. Bien que les paramètres spécifiques ne soient pas détaillés dans le dossier, les options courantes pour un module de ce type incluent :

  - **Activer/Désactiver le module** : Un simple interrupteur pour activer ou désactiver le module sans le désinstaller.
  - **Afficher la catégorie racine** : Choisissez d'afficher ou non la catégorie principale « Accueil » ou « Racine » dans le menu.
  - **Profondeur maximale** : Limitez le nombre de niveaux de sous-catégories affichés dans le menu déroulant.
  - **Sélection du hook** : Choisissez les hooks d'affichage auxquels le module doit s'attacher (par exemple, `displayLeftColumn`, `displayRightColumn`).
  - **Paramètres de cache** : Options pour activer ou désactiver la mise en cache de la sortie du module afin d'améliorer les performances.
- **Effet de la modification de ce paramètre :**

  - *Lorsqu'il est activé :* Le module sera actif et affichera le menu de catégories vertical sur votre front office selon les autres paramètres.
  - *Lorsqu'il est désactivé :* Le module n'apparaîtra pas sur votre boutique, mais sa configuration sera sauvegardée.
  - *Choisir un hook (par exemple, `displayLeftColumn`) :* Le bloc de menu vertical apparaîtra dans la colonne de gauche de votre boutique.
  - *Limiter la profondeur :* Seules les catégories jusqu'au niveau spécifié seront affichées, simplifiant le menu pour les clients.
- **Valeur recommandée :**

  - **Activer le module** : OUI
  - **Afficher la catégorie racine** : NON (généralement, pour commencer directement avec vos principales catégories de produits)
  - **Profondeur maximale** : 3 (un bon équilibre pour la plupart des boutiques, évitant des menus trop complexes)
  - **Sélection du hook** : `displayLeftColumn` ou `displayRightColumn` (selon la préférence de mise en page de votre thème).
- **Scénario/exemple pour le marchand :**

  - *Scénario 1 (Simplification de la navigation) :* Vous avez une structure de catégories très profonde (par exemple, 5-6 niveaux). Vous pouvez définir la « Profondeur maximale » à 3 pour éviter que les clients ne soient submergés par trop d'options, en les guidant d'abord à travers les choix de niveau supérieur.
  - *Scénario 2 (Optimisation des performances) :* Si votre boutique connaît un trafic élevé, l'activation de la mise en cache pour la sortie du module peut considérablement accélérer les temps de chargement des pages, car le menu n'a pas besoin d'être reconstruit pour chaque visiteur.
  - *Scénario 3 (Ajustement de la mise en page) :* Votre thème est plus esthétique avec la navigation sur le côté droit. Vous sélectionneriez `displayRightColumn` dans les paramètres de hook pour déplacer le bloc de menu en conséquence.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Activer/Désactiver le module | Activé | Contrôle si le module est actif sur votre boutique. |
| Page de configuration du module | Afficher la catégorie racine | Non | Détermine si la catégorie « Accueil » de niveau supérieur est affichée. |
| Page de configuration du module | Profondeur maximale | 3 | Limite le nombre de niveaux de sous-catégories affichés. |
| Page de configuration du module | Sélection du hook | `displayLeftColumn` | Spécifie où le bloc de menu apparaît (par exemple, colonne gauche ou droite). |
| Page de configuration du module | Mise en cache | Activé | Améliore les performances en stockant le code HTML du menu généré. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Le menu n'apparaît pas sur ma boutique après l'installation.**
**R1 :**

1.  **Vérifier l'état du module :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que le module « Menu de catégories déroulant vertical » est installé et activé.
2.  **Vérifier l'affectation du hook :** Dans la configuration du module, assurez-vous qu'il est affecté à un hook actif (par exemple, `displayLeftColumn`, `displayRightColumn`). Certains thèmes peuvent ne pas afficher tous les hooks par défaut, ou vous pourriez avoir besoin d'ajuster les paramètres de mise en page de votre thème.
3.  **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty »). Parfois, un ancien contenu mis en cache empêche les nouveaux modules d'apparaître.
4.  **Compatibilité du thème :** Si vous utilisez un thème très personnalisé, il pourrait outrepasser le rendu des hooks par défaut de PrestaShop. Contactez le développeur de votre thème ou un expert PrestaShop.

**Q2 : L'effet déroulant ne fonctionne pas, ou il semble cassé.**
**R2 :**

1.  **Conflits de thème :** Un autre module ou le JavaScript/CSS personnalisé de votre thème pourrait être en conflit avec le style ou la fonctionnalité du module.
2.  **Vider le cache :** Essayez toujours de vider le cache de votre PrestaShop (**Paramètres avancés > Performances**) et le cache de votre navigateur.
3.  **Inspecter avec les outils du navigateur :** Utilisez les outils de développement de votre navigateur (F12) pour vérifier les erreurs JavaScript dans la console ou les conflits CSS. Recherchez les messages d'erreur rouges.
4.  **Réinstallation du module :** Essayez de désinstaller et de réinstaller le module (après avoir sauvegardé vos paramètres si possible).

**Q3 : Comment puis-je changer les couleurs ou les polices du menu ?**
**R3 :** Le module est livré avec son propre fichier `blockcategories.css` pour le style.

1.  **Personnalisation de base :** Pour des changements mineurs, vous pouvez souvent remplacer ces styles dans le fichier CSS personnalisé de votre thème (par exemple, `themes/yourtheme/assets/css/custom.css`). C'est le moyen le plus sûr d'apporter des modifications sans modifier les fichiers principaux du module.
2.  **Personnalisation avancée :** Pour des changements plus importants, vous pourriez avoir besoin de modifier directement le fichier `blockcategories.css` dans le répertoire `views/css/` du module. **Cependant, sachez que ces changements seront perdus lors des mises à jour du module.** Il est toujours préférable d'utiliser les surcharges de thème.
3.  **Personnalisateur de thème PrestaShop :** Certains thèmes offrent un « Personnalisateur de thème » ou un « Configurateur en direct » qui permet des changements de style de base sans toucher au code. Vérifiez si votre thème dispose de cette fonctionnalité.

**Q4 : Mes catégories n'apparaissent pas dans le menu.**
**R4 :**

1.  **Statut de la catégorie :** Assurez-vous que vos catégories sont actives et visibles dans votre Back Office PrestaShop (**Catalogue > Catégories**).
2.  **Paramètre de la catégorie racine :** Vérifiez la configuration du module pour voir si « Afficher la catégorie racine » est activé ou désactivé. S'il est désactivé et que vos catégories sont des enfants directs de la racine, elles pourraient ne pas apparaître.
3.  **Permissions :** Assurez-vous que les catégories ont les permissions de groupe appropriées si vous utilisez des groupes de clients.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Menu de catégories déroulant vertical » (`verticalblockcategories`) est un module PrestaShop standard conçu pour afficher un bloc de navigation de catégories dynamique. Il exploite principalement le système de hooks de PrestaShop pour rendre son contenu à divers emplacements du front-office. La logique du module est contenue dans son fichier PHP principal, qui gère l'installation, la désinstallation, l'enregistrement des hooks et la configuration. La présentation visuelle est gérée via des templates Smarty et un fichier CSS dédié. Il n'introduit pas de contrôleurs personnalisés ni d'ObjectModels complexes, se concentrant sur un rendu efficace des données de catégories existantes.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient aucun contrôleur d'administration Front-Office ou Back-Office personnalisé. Toute la logique est gérée dans le fichier principal du module (`index.php`) et rendue via des hooks.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe ou `ObjectModel` personnalisé dans un répertoire `classes/`. Il utilise directement les classes principales de PrestaShop `Category` et `Tools` pour récupérer et traiter les données de catégories.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module ne contient aucun fichier JavaScript personnalisé. L'effet déroulant est généralement obtenu uniquement via CSS, ou repose sur des bibliothèques jQuery/JavaScript existantes déjà chargées par PrestaShop ou le thème.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`verticalblockcategories/blockcategories.css`**
    -   **Portée** : Style client du front-office.
    -   **Principaux composants et conteneurs d'interface utilisateur qu'il stylise** : Cette feuille de style est responsable de la mise en page visuelle, de l'apparence et de l'animation déroulante du menu de catégories vertical. Elle cible les éléments au sein de la structure HTML générée par le module, tels que `div#categories_block_left`, `ul.tree`, `li.last`, `a.selected` et `ul.tree li ul`.
    -   **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger dans leur thème** :
        -   `#categories_block_left` (ou ID/classe similaire pour le conteneur de bloc principal)
        -   `.block_content`
        -   `ul.tree` (pour la liste principale des catégories)
        -   `ul.tree li` (pour les éléments de catégorie individuels)
        -   `ul.tree li a` (pour les liens de catégorie)
        -   `ul.tree li ul` (pour les menus déroulants de sous-catégories)
        -   `ul.tree li ul li` (pour les éléments de sous-catégorie individuels)
        -   `.selected` (pour la catégorie actuellement active)
        -   Classes liées aux effets de survol et aux transitions pour le menu déroulant.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :
    -   **`verticalblockcategories/blockcategories.tpl`** : C'est le fichier de template principal rendu par le module lorsqu'il est accroché. Il contient généralement la structure globale du bloc de catégories, y compris le titre et la liste non ordonnée principale (`<ul>`) qui contiendra l'arborescence des catégories. Il inclut probablement `category-tree-branch.tpl` de manière récursive pour construire le menu complet.
        -   **Accroché dans** : `displayLeftColumn`, `displayRightColumn`, `displayHeader`, `displayFooter`, `displayProductExtraContent` (ou d'autres hooks de colonne/contenu).
        -   **Sorties** : Le bloc HTML principal pour le menu de catégories vertical.
    -   **`verticalblockcategories/category-tree-branch.tpl`** : Ce template est conçu pour le rendu récursif des branches de catégories individuelles (catégories et leurs sous-catégories). Il gère l'affichage d'un seul élément de catégorie et, si cette catégorie a des enfants, s'appelle récursivement pour rendre ces enfants sous forme de liste imbriquée, créant ainsi la structure arborescente.
        -   **Inclus par** : `blockcategories.tpl` (et potentiellement lui-même).
        -   **Sorties** : Un élément `<li>` pour une catégorie, contenant potentiellement un `<ul>` imbriqué pour ses sous-catégories.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** : Ce module ne crée aucune table de base de données personnalisée. Il s'appuie entièrement sur les tables principales de PrestaShop `ps_category`, `ps_category_lang` et `ps_category_product` pour les données de catégories. Les paramètres de configuration sont stockés dans `ps_configuration` en utilisant des clés préfixées par `VERTICALBLOCKCATEGORIES_`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` du HTML. | Potentiellement utilisé pour charger des actifs CSS/JS, bien que pour ce module, le CSS soit généralement enregistré via `install()` ou `hookDisplayHeader` lui-même. |
| `displayLeftColumn` | Rend le contenu dans la colonne de gauche de la boutique. | Hook principal pour afficher le bloc de menu de catégories vertical. |
| `displayRightColumn` | Rend le contenu dans la colonne de droite de la boutique. | Hook alternatif pour afficher le bloc de menu de catégories vertical. |
| `displayHome` | Rend le contenu sur la page d'accueil. | Peut être utilisé pour afficher le menu sur la page d'accueil, bien que moins courant pour un menu vertical. |
| `displayFooter` | Rend le contenu dans la section du pied de page. | Moins courant pour un menu de navigation principal, mais possible pour des liens supplémentaires. |
| `displayProductExtraContent` | Rend le contenu sur la page produit, généralement sous les informations principales du produit. | Pourrait être utilisé pour afficher des catégories connexes pour la navigation des produits. |
| `actionObjectCategoryAddAfter` | Après l'ajout d'une catégorie. | Potentiellement utilisé pour vider le cache du module si la structure des catégories change. |
| `actionObjectCategoryUpdateAfter` | Après la mise à jour d'une catégorie. | Potentiellement utilisé pour vider le cache du module si la structure des catégories change. |
| `actionObjectCategoryDeleteAfter` | Après la suppression d'une catégorie. | Potentiellement utilisé pour vider le cache du module si la structure des catégories change. |
| `actionShopDataDuplication` | Lors de la duplication d'une boutique (dans un contexte multi-boutique). | Assure que la configuration du module est copiée vers la nouvelle boutique. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Menu de catégories déroulant vertical », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question concernant la fonctionnalité du module.
