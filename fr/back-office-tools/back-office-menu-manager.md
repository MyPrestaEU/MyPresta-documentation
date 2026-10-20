---
title: "Gestionnaire de menu du Back office - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Gestionnaire de menu du Back office' par MyPresta.eu."
sidebar:
  label: "Gestionnaire de menu du Back office - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Back office menu manager sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/back-office-menu-manager.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/back-office-menu-manager/)
>
> ---


# Gestionnaire de menu du Back office

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à l'écran de configuration principal du module « Gestionnaire de menu du Back office ».

Cet écran contient généralement les paramètres standard du module, qui peuvent inclure :

-   **Activer/Désactiver le module :**

    -   **Ce que fait ce paramètre :** Il s'agit d'un interrupteur principal pour activer ou désactiver la fonctionnalité du module.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Les fonctionnalités du module, y compris les nouvelles options de gestion de menu, seront actives dans votre Back Office.
        -   *Lorsqu'il est désactivé :* Le module cessera d'affecter votre menu de Back Office, et le comportement par défaut du menu PrestaShop reprendra.
    -   **Valeur recommandée :** **OUI** (Activé) pour utiliser le module.
    -   **Scénario / exemple pour le marchand :** Si vous testez le module ou souhaitez temporairement revenir au menu PrestaShop par défaut, vous pouvez le désactiver ici.
-   **Réinitialiser les paramètres du module :**

    -   **Ce que fait ce paramètre :** Cette option vous permet de rétablir tous les paramètres spécifiques au module et potentiellement toutes les configurations de menu personnalisées à leur état par défaut.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque cliqué :* Tous vos arrangements de menu personnalisés et préférences de module seront effacés, et le module se comportera comme s'il venait d'être installé pour la première fois.
    -   **Valeur recommandée :** À utiliser avec prudence. Ne cliquez que si vous souhaitez redémarrer complètement votre configuration de menu.
    -   **Scénario / exemple pour le marchand :** Si vous avez effectué de nombreux changements et souhaitez repartir de zéro, ou si vous rencontrez un problème inattendu et souhaitez exclure des problèmes de configuration, cela peut être une étape de dépannage utile.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Ce module introduit une nouvelle section dédiée dans votre Back Office PrestaShop pour gérer les onglets de menu.

#### Nom de l'écran et emplacement du menu : AdminMenuTabsController

-   **Emplacement du menu :** Après l'installation du module, vous trouverez un nouvel élément de menu, généralement sous **Paramètres avancés** ou une section administrative similaire, nommé quelque chose comme **« Gestionnaire de menu »** ou **« Menu du Back Office »**. Cliquer dessus vous mènera à l'écran `AdminMenuTabsController`.
-   **Actions et paramètres disponibles :**
    Cet écran fournit une vue de grille (tableau) complète de tous les onglets de menu actuellement disponibles dans votre Back Office PrestaShop. Pour chaque onglet de menu, vous verrez généralement :

    -   **ID :** L'identifiant unique de l'onglet de menu.
    -   **Nom :** Le nom d'affichage de l'onglet de menu (par exemple, « Commandes », « Produits », « Clients »).
    -   **Onglet parent :** À quel élément de menu principal cet onglet appartient (par exemple, « Commandes » est un parent de « Commandes », « Factures », « Avoirs »).
    -   **Position :** L'ordre numérique de l'onglet au sein de son groupe parent.
    -   **Interrupteur Actif/Inactif :** Un bouton pour activer ou désactiver la visibilité de l'onglet de menu.
    -   **Actions Modifier/Supprimer :** Boutons pour modifier les détails d'un onglet spécifique ou le supprimer (utilisez la suppression avec une extrême prudence, car cela pourrait supprimer des fonctionnalités essentielles).

    **Principales fonctionnalités que vous pouvez effectuer ici :**

    -   **Réorganiser les éléments de menu :** Vous pouvez généralement faire glisser et déposer des lignes dans la grille ou modifier manuellement la valeur de la « Position » pour réorganiser l'affichage des éléments de menu.
    -   **Masquer/Afficher les éléments de menu :** Utilisez l'interrupteur actif/inactif pour masquer les éléments de menu que vous n'utilisez pas ou que vous souhaitez restreindre à certains rôles du personnel (si combiné avec les permissions natives de PrestaShop).
    -   **Modifier les détails des éléments de menu :** Vous pourriez être en mesure de modifier le nom d'affichage d'un élément de menu, son icône ou son association parent (bien que la modification des associations parentes pour les onglets principaux ne soit généralement pas recommandée sans connaissances avancées).
    -   **Ajouter de nouveaux éléments de menu :** Bien que moins courant pour ce module spécifique (qui se concentre sur la gestion des onglets *existants*), certaines versions avancées pourraient permettre d'ajouter des liens de menu personnalisés.
-   **Effet des changements :**

    -   **Masquer un onglet :** L'onglet disparaîtra immédiatement du menu de votre Back Office pour tous les utilisateurs (sauf si des remplacements de permissions spécifiques sont en place).
    -   **Réorganiser les onglets :** L'ordre des éléments de menu changera instantanément dans la navigation du Back Office.
    -   **Modifier le nom d'un onglet :** Le nom affiché dans le menu du Back Office sera mis à jour.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**

    1.  **Configuration initiale :** Parcourez tous vos éléments de menu principaux et leurs sous-éléments. Décidez lesquels votre équipe utilise régulièrement, rarement ou jamais.
    2.  **Désencombrer :** Pour les éléments rarement ou jamais utilisés, utilisez l'interrupteur « Actif/Inactif » pour les masquer. Cela simplifie considérablement le menu.
    3.  **Prioriser :** Réorganisez les éléments fréquemment consultés pour qu'ils soient en haut de leurs sections respectives. Par exemple, si vous passez la plupart de votre temps sur les « Commandes », assurez-vous que « Commandes » est le premier sous-élément sous le menu principal « Commandes ».
    4.  **Réviser régulièrement :** À mesure que les opérations de votre boutique évoluent ou que de nouveaux modules sont installés (qui ajoutent souvent leurs propres éléments de menu), revisitez cet écran pour maintenir votre menu optimisé.

#### Nom de l'écran et emplacement du menu : index.php (adminmenu/controllers/admin/index.php)

Ce fichier, `index.php` dans un répertoire de contrôleur d'administration, sert généralement de marqueur de position ou de point d'entrée pour la fonctionnalité du contrôleur, plutôt que d'un écran autonome avec des options configurables. Dans PrestaShop, la logique et l'affichage réels d'un contrôleur d'administration sont gérés par la classe principale (par exemple, `AdminMenuTabsController.php`).

Par conséquent, vous n'interagirez pas directement avec un écran « index.php ». Sa présence fait partie de la structure interne du module, garantissant que l'`AdminMenuTabsController` fonctionne correctement. Toutes vos interactions se feront via l'interface `AdminMenuTabsController` décrite ci-dessus.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer/Désactiver le module | Activé | Active/désactive les fonctionnalités de gestion de menu du module. |
| Configuration du module | Réinitialiser les paramètres du module | N/A (Action) | Réinitialise tous les paramètres du module et les configurations de menu par défaut. À utiliser avec prudence. |
| AdminMenuTabsController | Nom de l'onglet (par exemple, « Commandes ») | Nom PrestaShop original | Affiche le nom de l'élément de menu. Peut être modifié. |
| AdminMenuTabsController | Onglet parent | Parent PrestaShop original | Affiche la catégorie de menu principale pour cet élément. |
| AdminMenuTabsController | Position | Varie | Contrôle l'ordre d'affichage de l'élément de menu au sein de son parent. Peut être modifié par glisser-déposer ou saisie directe. |
| AdminMenuTabsController | Interrupteur Actif/Inactif | Actif | Active/désactive la visibilité de l'élément de menu dans le Back Office. |
| AdminMenuTabsController | Actions Modifier/Supprimer | N/A (Action) | Permet la modification des détails de l'onglet ou sa suppression (supprimer avec prudence). |

## 3. Dépannage pour le marchand et questions fréquemment posées (FAQ)

**Q : J'ai masqué un élément de menu, mais il apparaît toujours pour certains utilisateurs. Pourquoi ?**
R : Ce module gère la *visibilité* et l'*ordre* des éléments de menu. Les permissions utilisateur natives de PrestaShop (sous **Paramètres avancés > Équipe > Profils** et **Permissions**) déterminent *qui peut accéder à quoi*. Si un profil utilisateur a une permission explicite pour un onglet, il pourrait toujours le voir même si vous l'avez marqué comme inactif dans ce module. Vérifiez toujours les paramètres de ce module et les permissions de PrestaShop.

**Q : J'ai effectué des modifications, mais le menu n'a pas été mis à jour. Que dois-je faire ?**
R :

1.  **Vider le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances**. Cliquez sur « Vider le cache » dans le coin supérieur droit. C'est souvent nécessaire pour que les modifications du Back Office prennent effet.
2.  **Actualiser le navigateur :** Parfois, une actualisation forcée de votre navigateur (Ctrl+F5 ou Cmd+Maj+R) est nécessaire pour vider le cache local du navigateur.
3.  **Vérifier l'état du module :** Assurez-vous que le module « Gestionnaire de menu du Back office » est toujours activé dans **Modules > Gestionnaire de modules**.

**Q : Puis-je ajouter de nouveaux liens personnalisés au menu du Back Office avec ce module ?**
R : Ce module se concentre principalement sur la gestion des onglets de menu PrestaShop *existants*. Bien que certaines versions avancées puissent offrir la création de liens personnalisés, son objectif principal est de permettre la gestion de la structure de menu par défaut de PrestaShop. Si vous avez besoin d'ajouter des liens personnalisés complexes, vous pourriez avoir besoin d'un module plus avancé ou d'un développement personnalisé.

**Q : J'ai accidentellement supprimé un élément de menu PrestaShop essentiel. Comment le récupérer ?**
R : La suppression d'éléments de menu essentiels n'est généralement pas recommandée. Si vous l'avez fait, le moyen le plus sûr de le restaurer est de :

1.  **Désactiver et réactiver le module :** Allez dans **Modules > Gestionnaire de modules**, trouvez « Gestionnaire de menu du Back office », désactivez-le, puis réactivez-le. Cela déclenche souvent une réinitialisation des entrées de menu par défaut.
2.  **Réinitialiser les paramètres du module :** Si ce qui précède ne fonctionne pas, allez sur la page de configuration du module et utilisez l'option « Réinitialiser les paramètres du module ». Sachez que cela effacera TOUTES vos configurations de menu personnalisées.
3.  **Restaurer à partir d'une sauvegarde :** En dernier recours, si des éléments de menu critiques sont manquants, vous devrez peut-être restaurer votre base de données à partir d'une sauvegarde effectuée *avant* la suppression.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique pour les développeurs et les webmasters travaillant avec le module « Gestionnaire de menu du Back office ».

### 4.1 Vue d'ensemble de l'architecture

Le module « Gestionnaire de menu du Back office » étend principalement la fonctionnalité de base du Back Office de PrestaShop en surchargeant des classes d'aide spécifiques pour réintroduire les capacités de gestion de menu. Il tire parti du modèle MVC de PrestaShop, avec un contrôleur d'administration dédié (`AdminMenuTabsController`) pour fournir l'interface utilisateur de gestion des onglets de menu. Le module interagit avec la table de base de données `ps_tab`, qui stocke les informations sur les éléments de menu du Back Office. La décision architecturale clé est l'utilisation de surcharges pour modifier le comportement de base de PrestaShop sans altérer directement les fichiers de base, assurant une meilleure compatibilité et des chemins de mise à niveau.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :
    Ce module ne contient aucun contrôleur front-office car sa fonctionnalité est exclusivement destinée au Back Office de PrestaShop.
-   **Contrôleurs d'administration Back-Office** :

    -   `adminmenu/controllers/admin/AdminMenuTabs.php`

        -   **Nom de la classe et classe parente** : `AdminMenuTabsController` étend `ModuleAdminController`.
        -   **Nom de l'onglet et entité gérée** : Ce contrôleur gère l'entité `Tab` (représentant les éléments de menu du Back Office). Il crée une entrée de menu dédiée dans le Back Office pour le « Gestionnaire de menu ».
        -   **Responsabilité** : C'est le contrôleur principal de l'interface utilisateur du module. Il gère l'affichage de la liste de tous les onglets du Back Office, permettant aux administrateurs de les visualiser, de les modifier, de les activer/désactiver et de les réorganiser. Il utilise généralement `HelperList` pour l'affichage de la grille et `HelperForm` pour les formulaires de modification. Il traite les requêtes POST pour l'enregistrement des modifications (par exemple, les mises à jour de position, les bascules de statut).
    -   `adminmenu/controllers/admin/index.php`

        -   **Responsabilité** : Ce fichier est un marqueur de position standard dans la structure des contrôleurs de PrestaShop. Il contient généralement une simple instruction `die('No direct script access allowed');` pour empêcher l'accès direct au répertoire et garantir que les requêtes sont acheminées via le répartiteur de PrestaShop. Il ne contient aucune logique fonctionnelle pour le module lui-même.

### 4.3 Classes et modèles de base (`classes/`)

Le module utilise des surcharges pour modifier le comportement de base de PrestaShop.

-   `adminmenu/override/classes/helper/HelperList.php`

    -   **Nom de la classe et classe parente** : `HelperList` (surcharge la classe `HelperList` de base).
    -   **Ce qu'il fait** : Cette surcharge modifie probablement le comportement de `HelperList` spécifiquement lors du rendu de la liste des entités `Tab` dans le Back Office. C'est crucial pour réactiver des fonctionnalités comme le réordonnancement par glisser-déposer ou des affichages de colonnes spécifiques qui ont été supprimés de l'implémentation par défaut de `HelperList` pour `Tab` dans les nouvelles versions de PrestaShop. Il pourrait injecter des actions personnalisées ou modifier la façon dont les données sont récupérées ou affichées pour les onglets de menu.
-   `adminmenu/override/classes/helper/index.php`

    -   **Responsabilité** : Similaire à `controllers/admin/index.php`, il s'agit d'un fichier de marqueur de position pour empêcher la liste ou l'accès direct au répertoire.
-   `adminmenu/override/classes/index.php`

    -   **Responsabilité** : Un autre fichier de marqueur de position pour empêcher la liste ou l'accès direct au répertoire.

### 4.4 Actifs JavaScript (`views/js/`)

L'inventaire fourni n'indique aucun fichier JavaScript personnalisé au sein du module. Cela suggère que la fonctionnalité de gestion de menu, y compris des fonctionnalités comme le réordonnancement par glisser-déposer, est gérée soit par :

1.  Le JavaScript natif de `HelperList` de PrestaShop (que la surcharge du module pourrait réactiver ou configurer).
2.  Le traitement côté serveur pour les mises à jour de position.
3.  Un JS en ligne minimal généré par les classes `HelperList` ou `HelperForm`.

Les développeurs doivent inspecter le HTML généré et les requêtes réseau sur la page `AdminMenuTabsController` pour comprendre l'implémentation JS exacte des éléments interactifs.

### 4.5 Feuilles de style CSS (`views/css/`)

L'inventaire fourni n'indique aucun fichier CSS personnalisé au sein du module. Cela implique que le module s'appuie entièrement sur le style par défaut du Back Office de PrestaShop. Tout style personnalisé pour l'interface du gestionnaire de menu serait soit :

1.  Injecté en ligne via des templates Smarty ou PHP.
2.  Utilisant les classes CSS PrestaShop existantes.

### 4.6 Structure des templates Smarty (`views/templates/`)

L'inventaire fourni n'indique aucun fichier de template Smarty (`.tpl`) personnalisé au sein du module. C'est un indicateur fort que le module s'appuie principalement sur les templates par défaut de `HelperList` et `HelperForm` de PrestaShop pour le rendu de son interface Back Office.

L'`AdminMenuTabsController` instancierait des objets `HelperList` et `HelperForm`, leur passant des tableaux de configuration, et ces helpers rendraient ensuite l'interface utilisateur en utilisant les templates de base de PrestaShop (par exemple, `_partials/helpers/list_action_enable.tpl`, `helpers/list/list_content.tpl`, `helpers/form/form.tpl`).

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    Ce module interagit principalement avec la table de base de données PrestaShop existante :

    -   `ps_tab` : Cette table stocke toutes les entrées de menu du Back Office, y compris leurs noms, ID parents, positions et statut actif. L'`AdminMenuTabsController` du module et la surcharge de `HelperList` lisent et écrivent directement dans cette table pour gérer le menu.
    -   `ps_configuration` : Table de configuration standard de PrestaShop. Les principaux paramètres de configuration du module (par exemple, statut activé/désactivé) seraient stockés ici (par exemple, `PS_ADMINMENU_MANAGER_ENABLED`).
-   **Table des hooks enregistrés** :
    Basé sur la description et la fonctionnalité du module, il n'enregistre explicitement aucun hook d'affichage front-office ou back-office (`displayHeader`, `actionValidateOrder`, etc.) au sens traditionnel. Sa fonctionnalité est obtenue par :

    1.  **Enregistrement du contrôleur d'administration** : Le module enregistre `AdminMenuTabsController` comme un nouvel onglet du Back Office, le rendant accessible via le menu du Back Office.
    2.  **Surcharges de classe** : Le mécanisme principal repose sur la surcharge de `classes/helper/HelperList.php` pour modifier la façon dont les onglets de menu sont gérés et affichés dans le Back Office. Ce n'est pas un « hook » mais une modification directe du comportement de base.

    Par conséquent, un tableau des hooks enregistrés n'est pas applicable au sens typique pour ce module. Son impact se situe sur le fonctionnement interne du rendu du menu du Back Office.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Gestionnaire de menu du Back office », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
