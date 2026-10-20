---
title: "Sauvegarde de base de données localement et dans le cloud - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Sauvegarde de base de données localement et dans le cloud' par MyPresta.eu."
sidebar:
  label: "Sauvegarde de base de données localement et dans le cloud - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Database backup locally and in cloud sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/database-backup-locally-and-in-cloud.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/database-backup-locally-and-in-cloud/)
>
> ---


# Sauvegarde de base de données localement et dans le cloud

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Extensions PHP standard (cURL, JSON, OpenSSL). Ressources serveur suffisantes (CPU, mémoire) pour l'exportation de la base de données, en particulier pour les très grandes bases de données, bien que le module soit conçu pour atténuer ces problèmes avec le découpage en morceaux. Droits d'écriture pour le répertoire de sauvegarde sur votre serveur.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

Le module « Sauvegarde de base de données localement et dans le cloud » offre une interface complète pour gérer vos sauvegardes. Vous interagirez principalement avec deux zones principales : la page de configuration principale du module et son écran d'administration dédié « Mes Sauvegardes ».

### 2.1 Page de configuration principale du module (Back Office > Modules > Gestionnaire de modules > Configurer « Sauvegarde de base de données localement et dans le cloud »)

Cette page de configuration initiale (`mybackups/index.php` via `getContent()`) gère la configuration de base et l'intégration du module.

#### Paramètres généraux

-   **Ce que fait ce paramètre :** Ces paramètres contrôlent les aspects fondamentaux du fonctionnement du module et de son intégration avec votre environnement PrestaShop.
-   **Effet de la modification de ce paramètre :** L'ajustement de ces paramètres peut avoir un impact sur les performances, la sécurité et la fiabilité globale de vos sauvegardes.
-   **Valeur recommandée :** En général, conservez les valeurs par défaut, sauf si vous avez une raison spécifique ou si le support vous le conseille.

#### Intégrations de stockage cloud

-   **Ce que fait ce paramètre :** Cette section vous permet de connecter votre boutique PrestaShop à divers fournisseurs de stockage cloud où vos sauvegardes seront stockées. Chaque fournisseur (Google Drive, Dropbox, FTP/FTPS, Amazon S3) aura son propre ensemble de détails de connexion.
-   **Effet de la modification de ce paramètre :** Une connexion réussie à un service cloud active ce service comme destination de sauvegarde. Des identifiants incorrects empêcheront le téléchargement des sauvegardes vers ce cloud spécifique.
-   **Valeur recommandée :** Connectez-vous à au moins un fournisseur de stockage cloud pour les sauvegardes hors site. Google Drive et Dropbox sont souvent les plus faciles à configurer pour la plupart des marchands.
-   **Scénario/exemple de marchand :** Vous souhaitez stocker vos sauvegardes sur Google Drive. Vous cliqueriez sur le bouton « Connecter à Google Drive », suivriez les étapes d'authentification et accorderiez au module la permission d'accéder à un dossier spécifique dans votre Google Drive. Cela garantit que même si votre serveur tombe en panne, vos sauvegardes sont en sécurité dans le cloud.

### 2.2 Écran d'administration dédié : Mes Sauvegardes (Back Office > Mes Sauvegardes)

C'est le centre de gestion de toutes vos sauvegardes de base de données. Vous trouverez cet écran sous un nouvel élément de menu, généralement nommé « Mes Sauvegardes » ou similaire, ajouté à la navigation de votre Back Office PrestaShop. Cet écran est alimenté par `mybackups/controllers/admin/AdminMyBackupsController.php`.

#### Tableau de bord et liste des sauvegardes

-   **Nom de l'écran et emplacement du menu :** Vous trouverez « Mes Sauvegardes » sous le menu principal de PrestaShop, généralement regroupé avec « Administration » ou « Paramètres avancés ».
-   **Actions et paramètres disponibles :**
    -   **Liste des sauvegardes :** Ce tableau affiche toutes vos sauvegardes de base de données existantes, qu'elles soient stockées localement ou dans le cloud. Chaque entrée affiche généralement :
        -   **Date/Heure :** Quand la sauvegarde a été créée.
        -   **Taille :** La taille du fichier de sauvegarde compressé.
        -   **Emplacement :** Où la sauvegarde est stockée (Local, Google Drive, Dropbox, FTP, S3).
        -   **Actions :**
            -   **Télécharger :** Téléchargez le fichier de sauvegarde sur votre ordinateur.
            -   **Restaurer :** Lancez un processus de restauration de base de données en utilisant cette sauvegarde. (Soyez extrêmement prudent avec cette action, car elle écrasera votre base de données actuelle !)
            -   **Supprimer :** Supprimez le fichier de sauvegarde de son emplacement de stockage.
    -   **Bouton Créer une nouvelle sauvegarde :** Un bouton proéminent pour lancer manuellement une nouvelle sauvegarde de base de données.
    -   **Statut du stockage cloud :** Indicateurs visuels montrant quels services cloud sont actuellement connectés et disponibles.
    -   **Sauvegardes planifiées :** Une section pour afficher et gérer vos tâches de sauvegarde automatisées (tâches cron).
-   **Effet des modifications :**
    -   **Création d'une nouvelle sauvegarde :** Génère un nouveau dump SQL compressé de votre base de données et le stocke aux emplacements configurés (local et/ou cloud).
    -   **Restauration d'une sauvegarde :** Remplace votre base de données en direct actuelle par les données du fichier de sauvegarde sélectionné. Il s'agit d'une action puissante et potentiellement destructive ; assurez-vous toujours d'avoir une nouvelle sauvegarde avant de tenter une restauration.
    -   **Suppression d'une sauvegarde :** Supprime définitivement le fichier de sauvegarde de son stockage.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  **Configuration initiale :** Connectez-vous à vos fournisseurs de stockage cloud préférés sur la page de configuration du module.
    2.  **Planifier les sauvegardes :** Configurez une tâche cron (voir « Cas d'utilisation pratiques » ci-dessous) pour créer automatiquement des sauvegardes quotidiennement ou hebdomadairement, en fonction de l'activité de votre boutique. Assurez-vous que ces sauvegardes planifiées sont envoyées à au moins un emplacement cloud.
    3.  **Surveillance régulière :** Vérifiez périodiquement le tableau de bord « Mes Sauvegardes » pour vous assurer que les sauvegardes sont créées avec succès et que vos connexions cloud sont actives.
    4.  **Sauvegarde manuelle (facultatif) :** Créez une sauvegarde manuelle avant toute modification majeure de la boutique (par exemple, installations de modules, mises à jour de thème, importations de produits).
    5.  **Test de restauration (CRITIQUE) :** Effectuez occasionnellement un test de restauration sur un *environnement de développement ou de staging* (JAMAIS sur votre boutique en direct sans une extrême prudence) pour vous assurer que vos sauvegardes sont valides et que le processus de restauration fonctionne comme prévu.

#### Formulaire de création de sauvegarde

Lorsque vous cliquez sur « Créer une nouvelle sauvegarde », vous aurez généralement des options :

-   **Nom de la sauvegarde :**
    -   **Ce que fait ce paramètre :** Vous permet de donner un nom personnalisé à votre fichier de sauvegarde pour une identification facile.
    -   **Effet de la modification de ce paramètre :** Le fichier de sauvegarde sera enregistré avec ce nom (par exemple, `ma-boutique-sauvegarde-2023-10-27.sql.zip`).
    -   **Valeur recommandée :** Utilisez un nom descriptif, incluant peut-être la date ou une brève note sur la raison de la sauvegarde (par exemple, « Sauvegarde avant mise à jour »).
-   **Emplacements de stockage :**
    -   **Ce que fait ce paramètre :** Sélectionnez où le fichier de sauvegarde doit être enregistré. Les options incluent généralement « Serveur local » et tous les services cloud connectés (Google Drive, Dropbox, FTP, S3).
    -   **Effet de la modification de ce paramètre :** La sauvegarde ne sera stockée qu'aux emplacements sélectionnés.
    -   **Valeur recommandée :** Sélectionnez toujours « Serveur local » et au moins une option de stockage cloud pour la redondance.
-   **Exclure les tables :**
    -   **Ce que fait ce paramètre :** Vous permet de sélectionner des tables de base de données spécifiques qui ne doivent *pas* être incluses dans la sauvegarde. Cela peut être utile pour les très grandes tables qui contiennent des données non critiques ou facilement régénérables (par exemple, tables de cache, tables de logs).
    -   **Effet de la modification de ce paramètre :** Les tables sélectionnées seront ignorées, ce qui réduira la taille du fichier de sauvegarde.
    -   **Valeur recommandée :** Pour la plupart des marchands, laissez ce champ vide pour sauvegarder l'intégralité de la base de données. N'excluez les tables que si vous comprenez les implications et que vous essayez de réduire la taille de la sauvegarde en raison de contraintes d'hébergement sévères.
-   **Bouton Démarrer la sauvegarde :** Lance le processus de sauvegarde. Vous verrez généralement une barre de progression ou des mises à jour de statut au fur et à mesure que la sauvegarde est créée et téléchargée.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Paramètres généraux | Par défaut | Contrôle les opérations fondamentales du module, les performances et la sécurité. |
| | Intégration Google Drive | Connecter | Active Google Drive comme destination de sauvegarde. |
| | Intégration Dropbox | Connecter | Active Dropbox comme destination de sauvegarde. |
| | Intégration FTP/FTPS | Configurer | Active FTP/FTPS comme destination de sauvegarde. |
| | Intégration Amazon S3 | Configurer | Active Amazon S3 comme destination de sauvegarde. |
| **Tableau de bord Mes Sauvegardes** | Créer une nouvelle sauvegarde | N/A | Lance manuellement une nouvelle sauvegarde de base de données. |
| | Liste des sauvegardes (Télécharger) | N/A | Télécharge un fichier de sauvegarde sur votre ordinateur local. |
| | Liste des sauvegardes (Restaurer) | N/A | **CRITIQUE :** Écrase la base de données actuelle avec la sauvegarde sélectionnée. À utiliser avec une extrême prudence, de préférence sur un environnement de staging. |
| | Liste des sauvegardes (Supprimer) | N/A | Supprime définitivement un fichier de sauvegarde de son emplacement de stockage. |
| **Formulaire de création de sauvegarde** | Nom de la sauvegarde | Généré automatiquement | Nom personnalisé pour le fichier de sauvegarde. |
| | Emplacements de stockage | Local + Cloud | Sélectionne où la sauvegarde sera enregistrée (serveur local, services cloud). |
| | Exclure les tables | Aucune | Ignore les tables spécifiées de la sauvegarde pour réduire la taille du fichier. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes sauvegardes échouent ou prennent trop de temps. Que dois-je faire ?**
R :

-   **Vérifiez les ressources du serveur :** Les grandes bases de données nécessitent une mémoire serveur et un temps d d'exécution importants. Bien que le module découpe les exportations, les environnements d'hébergement très contraints peuvent toujours rencontrer des difficultés. Contactez votre hébergeur pour vérifier les limites de mémoire PHP (`memory_limit`) et le temps d'exécution maximal (`max_execution_time`).
-   **Videz le cache :** Parfois, le cache de PrestaShop peut interférer. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ».
-   **Excluez les tables :** Envisagez d'exclure les tables non critiques (comme les tables de cache ou de statistiques) de la sauvegarde si elles sont très volumineuses. Cela peut réduire considérablement la taille et le temps de sauvegarde.
-   **Vérifiez les journaux d'erreurs :** Recherchez dans les journaux d'erreurs de votre PrestaShop (généralement `var/logs/` ou `app/logs/` selon la version de PS) ou les journaux d'erreurs PHP de votre serveur des messages d'erreur spécifiques.

**Q : Je me suis connecté à Google Drive/Dropbox, mais je ne vois pas mes sauvegardes là-bas.**
R :

-   **Vérifiez l'état de la connexion :** Allez sur la page de configuration du module et vérifiez que votre service cloud est affiché comme « Connecté ». Si ce n'est pas le cas, essayez de vous reconnecter.
-   **Permissions des dossiers :** Assurez-vous que le module dispose des permissions nécessaires pour écrire dans le dossier spécifié de votre stockage cloud. Pour Google Drive/Dropbox, le module crée généralement son propre dossier.
-   **Test de téléchargement manuel :** Essayez de créer une petite sauvegarde manuelle et de sélectionner explicitement le service cloud comme destination pour voir si elle est téléchargée avec succès.
-   **Vérifiez directement le stockage cloud :** Connectez-vous à votre compte Google Drive ou Dropbox via leur site web et parcourez manuellement les dossiers pour voir si les sauvegardes s'y trouvent, peut-être à un emplacement inattendu.

**Q : Comment restaurer ma base de données à partir d'une sauvegarde ?**
R :

-   **AVERTISSEMENT :** La restauration d'une base de données écrasera votre base de données en direct actuelle. Il s'agit d'une action très destructive. **Ayez toujours une nouvelle sauvegarde de votre base de données actuelle avant de tenter une restauration.**
-   Allez dans **Back Office > Mes Sauvegardes**.
-   Localisez le fichier de sauvegarde que vous souhaitez restaurer dans la liste.
-   Cliquez sur le bouton « Restaurer » à côté de cette sauvegarde.
-   Suivez les instructions à l'écran. Le module vous guidera tout au long du processus.
-   Si votre boutique est complètement hors service, vous devrez peut-être télécharger manuellement le fichier de sauvegarde via FTP, puis utiliser l'interface du module ou un outil comme phpMyAdmin pour l'importer. Dans de telles situations critiques, il est préférable de consulter un développeur ou votre hébergeur.

**Q : Que se passe-t-il si mon serveur manque d'espace disque lors d'une sauvegarde locale ?**
R : Le processus de sauvegarde échouera probablement et vous verrez un message d'erreur lié à l'espace disque. Assurez-vous d'avoir suffisamment d'espace disque libre sur votre serveur, surtout si vous stockez plusieurs sauvegardes locales ou si vous avez une très grande base de données. Supprimez régulièrement les anciennes sauvegardes locales qui ont déjà été téléchargées en toute sécurité dans le cloud.

**Q : Mon thème personnalisé ne s'affiche pas correctement après une restauration.**
R : Les sauvegardes de base de données restaurent principalement vos données. Les fichiers de thème, les fichiers de module et les images sont généralement stockés sur le système de fichiers de votre serveur, pas directement dans la base de données.

-   **Videz le cache :** Allez dans **Paramètres avancés > Performances** et videz tous les caches (Smarty, système de fichiers, etc.).
-   **Vérifiez le système de fichiers :** Assurez-vous que tous vos fichiers de thème, fichiers de module et dossiers d'images sont présents et ont les bonnes permissions sur le serveur. Une restauration de base de données n'affectera pas ces fichiers. Si vous avez restauré à partir d'une très ancienne sauvegarde, certaines configurations de module pourraient devoir être réenregistrées dans le Back Office.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de l'architecture technique et de la base de code du module « Sauvegarde de base de données localement et dans le cloud » pour les développeurs et les webmasters.

### 4.1 Vue d'ensemble de l'architecture

Le module MyBackups est conçu en mettant l'accent sur la robustesse, l'évolutivité et la tolérance aux pannes, en particulier pour la gestion des opérations de base de données volumineuses et des intégrations cloud externes. Il suit une approche modulaire et orientée objet, tirant parti du modèle MVC de PrestaShop le cas échéant, mais implémentant également sa propre architecture interne orientée services pour la logique de sauvegarde/restauration.

Les principaux modèles architecturaux incluent :

-   **Traitement par morceaux :** L'exportation et l'importation de la base de données sont divisées en morceaux plus petits et gérables pour contourner les limites de temps d'exécution et de mémoire de PHP.
-   **Gestion de l'état :** Un système de gestion de l'état robuste (`MyBackupsStateManager`) suit la progression des tâches de sauvegarde/restauration de longue durée, permettant l'exécution par web-cron et la récupération après des interruptions.
-   **Abstraction du stockage :** Une conception basée sur des interfaces (`MyBackupsStorageInterface`) permet une intégration facile de nouveaux fournisseurs de stockage cloud sans modifier la logique de sauvegarde principale.
-   **Intégration OAuth :** Flux OAuth 2.0 sécurisés pour Google Drive et Dropbox, gérant le stockage et le rafraîchissement des jetons.
-   **Exécuteur de Cron/Tâches :** Contrôleurs frontaux et classes dédiés pour déclencher et gérer les tâches en arrière-plan via cron ou web-cron.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs sont principalement utilisés pour les tâches en arrière-plan et les rappels OAuth, et non pour le rendu de contenu destiné aux clients.

-   `mybackups/controllers/front/cron.php`
    -   **Nom de la classe et classe parente :** `MyBackupsCronModuleFrontController` étendant `ModuleFrontController`.
    -   **Responsabilité :** Ce contrôleur sert de point d'entrée pour les tâches cron planifiées. Lorsqu'il est accédé avec le jeton correct, il déclenche le `MyBackupsCronRunner` pour traiter les tâches de sauvegarde en attente. Il est conçu pour être appelé en externe par un démon cron de serveur ou un service web-cron.
-   `mybackups/controllers/front/index.php`
    -   **Nom de la classe et classe parente :** `MyBackupsIndexModuleFrontController` étendant `ModuleFrontController`.
    -   **Responsabilité :** Un contrôleur frontal de substitution ou par défaut, souvent utilisé pour le routage de module ou de simples redirections si aucune action spécifique n'est demandée. Dans ce module, il pourrait servir de base ou de repli.
-   `mybackups/controllers/front/job.php`
    -   **Nom de la classe et classe parente :** `MyBackupsJobModuleFrontController` étendant `ModuleFrontController`.
    -   **Responsabilité :** Gère les requêtes AJAX liées à la progression et au statut des tâches de sauvegarde/restauration en cours. Il interagit avec `MyBackupsJobRunner` et `MyBackupsStateManager` pour fournir des mises à jour en temps réel à l'interface utilisateur du Back Office.
-   `mybackups/controllers/front/oauthdropbox.php`
    -   **Nom de la classe et classe parente :** `MyBackupsOauthdropboxModuleFrontController` étendant `ModuleFrontController`.
    -   **Responsabilité :** C'est l'URI de rappel pour le flux OAuth 2.0 de Dropbox. Après qu'un marchand autorise le module sur Dropbox, Dropbox redirige vers ce contrôleur, qui gère ensuite l'échange du code d'autorisation contre un jeton d'accès et le stocke en toute sécurité.
-   `mybackups/controllers/front/oauthgdrive.php`
    -   **Nom de la classe et classe parente :** `MyBackupsOauthgdriveModuleFrontController` étendant `ModuleFrontController`.
    -   **Responsabilité :** Similaire à `oauthdropbox.php`, c'est l'URI de rappel pour le flux OAuth 2.0 de Google Drive. Il traite le code d'autorisation de Google et obtient/stocke les jetons d'accès et de rafraîchissement nécessaires.

#### Contrôleurs d'administration Back-Office

Ces contrôleurs gèrent l'interface du module dans le Back Office de PrestaShop.

-   `mybackups/controllers/admin/AdminMyBackupsController.php`
    -   **Nom de la classe et classe parente :** `AdminMyBackupsController` étendant `ModuleAdminController`.
    -   **Nom de l'onglet et entité gérée :** C'est le contrôleur d'administration principal pour le tableau de bord « Mes Sauvegardes ». Il gère la liste, la création, le téléchargement, la restauration et la suppression des fichiers de sauvegarde. Il orchestre les interactions avec `MyBackupsCatalog`, `MyBackupsExporter`, `MyBackupsImporter` et les différentes classes de stockage.
-   `mybackups/controllers/admin/index.php`
    -   **Nom de la classe et classe parente :** Fichier `index.php` PrestaShop standard pour les répertoires de contrôleurs d'administration.
    -   **Responsabilité :** Empêche la liste directe des répertoires et assure un accès sécurisé aux contrôleurs d'administration.

### 4.3 Classes et modèles principaux (`classes/`)

-   `mybackups/classes/index.php` : Fichier `index.php` vide standard pour empêcher la liste des répertoires.
-   `mybackups/classes/MyBackupsAdminAjax.php` : Gère diverses requêtes AJAX depuis l'interface d'administration, telles que la récupération des listes de sauvegardes, l'initiation d'actions spécifiques ou la mise à jour des éléments de l'interface utilisateur.
-   `mybackups/classes/MyBackupsAdminForms.php` : Probablement responsable du rendu et du traitement des formulaires de configuration du module dans le Back Office, y compris les paramètres d'intégration cloud.
-   `mybackups/classes/MyBackupsCatalog.php` : Gère le catalogue des fichiers de sauvegarde, qu'ils soient locaux ou dans le cloud. Il fournit des méthodes pour lister, filtrer et récupérer des informations sur les sauvegardes existantes.
-   `mybackups/classes/MyBackupsCloudUi.php` : Aide à générer les éléments d'interface utilisateur et la logique pour l'intégration du stockage cloud dans le Back Office (par exemple, boutons de connexion, indicateurs d'état).
-   `mybackups/classes/MyBackupsCronRunner.php` : La logique principale pour l'exécution des tâches de sauvegarde planifiées. Il vérifie les tâches en attente et lance `MyBackupsJobRunner` pour chacune.
-   `mybackups/classes/MyBackupsDumpVerifier.php` : Responsable de la vérification de l'intégrité et de la validité des fichiers de dump SQL, potentiellement en recherchant les erreurs courantes ou les dumps incomplets.
-   `mybackups/classes/MyBackupsExporter.php` : Gère le processus d'exportation de la base de données, y compris le découpage du dump SQL, le filtrage des tables et la compression.
-   `mybackups/classes/MyBackupsImporter.php` : Gère le processus d'importation (restauration) de la base de données, analysant le dump SQL et exécutant les requêtes par morceaux.
-   `mybackups/classes/MyBackupsJobLock.php` : Implémente un mécanisme de verrouillage pour empêcher l'exécution simultanée de plusieurs tâches de sauvegarde/restauration, garantissant la cohérence des données et évitant la contention des ressources.
-   `mybackups/classes/MyBackupsJobRunner.php` : Orchestre l'ensemble de la tâche de sauvegarde ou de restauration, gérant la séquence des étapes (exportation, compression, téléchargement/téléchargement, importation) et interagissant avec `MyBackupsStateManager`.
-   `mybackups/classes/MyBackupsMemoryGuard.php` : Une classe utilitaire pour surveiller et gérer l'utilisation de la mémoire PHP pendant les opérations intensives, aidant à prévenir les erreurs de manque de mémoire.
-   `mybackups/classes/MyBackupsOAuthReturn.php` : Gère les dernières étapes du processus de rappel OAuth, traitant le code d'autorisation renvoyé et gérant le stockage des jetons.
-   `mybackups/classes/MyBackupsOAuthState.php` : Gère le paramètre d'état pendant les flux OAuth pour prévenir les attaques CSRF.
-   `mybackups/classes/MyBackupsPaths.php` : Fournit une gestion centralisée des chemins de fichiers et des répertoires utilisés par le module (par exemple, répertoire de stockage des sauvegardes).
-   `mybackups/classes/MyBackupsStateManager.php` : Crucial pour les tâches de longue durée. Il stocke et récupère l'état actuel d'une opération de sauvegarde/restauration, permettant aux tâches d'être mises en pause et reprises sur plusieurs requêtes HTTP (par exemple, pendant l'exécution cron ou les mises à jour de progression basées sur le web).
-   `mybackups/classes/MyBackupsTableFilter.php` : Implémente la logique de filtrage des tables de base de données pendant l'exportation, en fonction des sélections de l'utilisateur.
-   `mybackups/classes/MyBackupsTimeBudget.php` : Aide à gérer les limites de temps d'exécution pour les processus de longue durée, permettant au module de s'arrêter gracieusement et de sauvegarder l'état avant d'atteindre `max_execution_time`.
-   `mybackups/classes/MyBackupsTokenCrypto.php` : Gère le chiffrement et le déchiffrement des jetons OAuth sensibles et des clés API pour un stockage sécurisé.
-   `mybackups/classes/MyBackupsZip.php` : Gère la compression et la décompression des fichiers de sauvegarde dans des archives ZIP.

#### Sous-classes de stockage (`classes/storage/`)

Ce répertoire contient des classes implémentant l'`MyBackupsStorageInterface` pour divers backends de stockage.

-   `mybackups/classes/storage/index.php` : Fichier `index.php` vide standard.
-   `mybackups/classes/storage/MyBackupsCloudUploader.php` : Une classe générique pour gérer le processus de téléchargement vers le stockage cloud, potentiellement gérant les téléchargements par morceaux et le suivi de la progression.
-   `mybackups/classes/storage/MyBackupsDropboxStorage.php` : Implémente `MyBackupsStorageInterface` pour interagir avec l'API Dropbox.
-   `mybackups/classes/storage/MyBackupsFtpStorage.php` : Implémente `MyBackupsStorageInterface` pour interagir avec les serveurs FTP/FTPS.
-   `mybackups/classes/storage/MyBackupsGoogleDriveStorage.php` : Implémente `MyBackupsStorageInterface` pour interagir avec l'API Google Drive.
-   `mybackups/classes/storage/MyBackupsHttp.php` : Une classe utilitaire pour effectuer des requêtes HTTP, probablement utilisée par les classes de stockage cloud pour les appels API.
-   `mybackups/classes/storage/MyBackupsLocalStorage.php` : Implémente `MyBackupsStorageInterface` pour stocker et récupérer les sauvegardes sur le système de fichiers du serveur local.
-   `mybackups/classes/storage/MyBackupsS3Storage.php` : Implémente `MyBackupsStorageInterface` pour interagir avec Amazon S3.
-   `mybackups/classes/storage/MyBackupsStorageFactory.php` : Une classe de modèle de fabrique responsable de l'instanciation de la classe de stockage correcte en fonction de la configuration.
-   `mybackups/classes/storage/MyBackupsStorageInterface.php` : Définit le contrat (méthodes) que toutes les classes de stockage doivent implémenter (par exemple, `upload`, `download`, `delete`, `list_files`).

### 4.4 Actifs JavaScript (`views/js/`)

-   `mybackups/lib/searchTool/views/js/autocomplete.js` :
    -   **Portée :** Probablement Back-office.
    -   **Détails :** Fournit une fonctionnalité d'autocomplétion, éventuellement pour la recherche dans les tables de base de données lors de la configuration des exclusions ou pour le filtrage des listes de sauvegardes.
-   `mybackups/views/js/mybackups-cloud.js` :
    -   **Portée :** Back-office.
    -   **Détails :** Gère les interactions côté client pour la configuration du stockage cloud. Cela inclut les appels AJAX pour se connecter/déconnecter des services, mettre à jour l'interface utilisateur en fonction de l'état de la connexion et potentiellement gérer la navigation dans les dossiers au sein des services cloud.
-   `mybackups/views/js/mybackups-job.js` :
    -   **Portée :** Back-office.
    -   **Détails :** Gère l'affichage de la progression en temps réel pour les tâches de sauvegarde et de restauration. Il utilise AJAX pour interroger le contrôleur frontal `job.php` pour les mises à jour de l'état de la tâche, mettant à jour les barres de progression, les messages d'état et gérant les notifications d'achèvement ou d'échec de la tâche.
-   `mybackups/views/js/mybackups-table-picker.js` :
    -   **Portée :** Back-office.
    -   **Détails :** Fournit l'interface interactive pour sélectionner ou exclure des tables de base de données lors de la création de sauvegardes, potentiellement avec des fonctions de recherche et de sélection multiple.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `mybackups/lib/searchTool/views/css/autocomplete.css` :
    -   **Portée :** Style d'administration Back-office.
    -   **Détails :** Styles pour les champs de saisie d'autocomplétion et les listes de suggestions utilisés dans le Back Office.
-   `mybackups/views/css/admin.css` :
    -   **Portée :** Style d'administration Back-office.
    -   **Détails :** Contient le style principal de l'interface Back Office du module, y compris le tableau de bord, la liste des sauvegardes, les formulaires, les barres de progression et les sections d'intégration cloud. Les développeurs peuvent remplacer ces styles dans leur thème d'administration personnalisé ou en ajoutant du CSS personnalisé via un hook si nécessaire.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   `mybackups/lib/searchTool/views/scripts.tpl` :
    -   **Portée :** Back-office.
    -   **Détails :** Inclut probablement les actifs JavaScript et CSS pour l'outil de recherche/autocomplétion, potentiellement accroché à `displayBackOfficeHeader` ou similaire.
-   `mybackups/views/templates/admin/backups.tpl` :
    -   **Portée :** Modèle d'administration.
    -   **Détails :** Le modèle principal pour afficher la liste des sauvegardes existantes, y compris les colonnes pour la date, la taille, l'emplacement et les boutons d'action (télécharger, restaurer, supprimer). C'est le cœur de l'affichage de l'`AdminMyBackupsController`.
-   `mybackups/views/templates/admin/configure.tpl` :
    -   **Portée :** Modèle d'administration.
    -   **Détails :** Rend le formulaire de configuration principal du module, généralement accessible via `getContent()` dans le fichier de module principal. Cela inclut les paramètres généraux et la configuration initiale des intégrations de services cloud.
-   `mybackups/views/templates/admin/dashboard.tpl` :
    -   **Portée :** Modèle d'administration.
    -   **Détails :** Le modèle de tableau de bord général pour la section « Mes Sauvegardes », combinant des éléments tels que la liste des sauvegardes, le bouton « Créer une nouvelle sauvegarde », les indicateurs d'état du cloud et potentiellement les informations de sauvegarde planifiée.
-   `mybackups/views/templates/admin/job-progress.tpl` :
    -   **Portée :** Modèle d'administration.
    -   **Détails :** Affiche la barre de progression et les messages d'état pour les tâches de sauvegarde ou de restauration en cours, mis à jour dynamiquement par `mybackups-job.js`.
-   `mybackups/views/templates/admin/table-picker.tpl` :
    -   **Portée :** Modèle d'administration.
    -   **Détails :** Rend l'interface pour sélectionner ou exclure des tables de base de données lors de la création de sauvegardes.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module ne crée pas de tables SQL personnalisées pour stocker les données de sauvegarde elles-mêmes, car les sauvegardes sont des fichiers.
    -   Il stockera les valeurs de configuration dans la table `ps_configuration` de PrestaShop, telles que :
        -   Clés/secrets d'API cloud (chiffrés).
        -   Jetons OAuth (chiffrés).
        -   Paramètres spécifiques au module (par exemple, emplacements de sauvegarde par défaut, jeton cron).
        -   Informations d'état des tâches pour `MyBackupsStateManager`.
-   **Table des hooks enregistrés** :
    Le module utilise principalement les hooks du Back Office et les contrôleurs frontaux pour sa fonctionnalité. Les hooks front-office listés (Header, Columns, Product, Footer) ne sont probablement *pas* utilisés par ce module, car sa fonctionnalité est purement administrative et axée sur le backend. S'ils étaient utilisés, ce serait à des fins très spécifiques et non visibles, telles que le chargement d'actifs ou l'exécution de vérifications en arrière-plan.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayBackOfficeHeader` | Rendu dans la section `<head>` des pages du Back Office. | Utilisé pour injecter le CSS (`admin.css`) et le JavaScript (`mybackups-cloud.js`, `mybackups-job.js`, `mybackups-table-picker.js`, `autocomplete.js`) spécifiques au module dans le panneau d'administration. |
| `displayAdminProductsExtra` (ou similaire) | Potentiellement pour ajouter une option de sauvegarde sur la page d'édition de produit, bien qu'improbable pour ce module. | (Si utilisé) Pour ajouter une action de sauvegarde spécifique ou des informations liées aux données produit. |
| `actionModuleInstall` | Exécuté lors de l'installation du module. | Crée les répertoires nécessaires, définit les valeurs de configuration par défaut, enregistre les onglets du menu d'administration et configure potentiellement les instructions initiales de la tâche cron. |
| `actionModuleUninstall` | Exécuté lors de la désinstallation du module. | Nettoie les valeurs de configuration, supprime les onglets du menu d'administration et supprime les répertoires spécifiques au module (bien qu'il laisse souvent les fichiers de sauvegarde pour des raisons de sécurité). |
| `actionAdminControllerSetMedia` | Exécuté avant qu'un contrôleur d'administration ne rende sa page. | Utilisé pour ajouter des actifs CSS/JS spécifiques uniquement aux pages d'administration propres au module (`AdminMyBackupsController`). |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Sauvegarde de base de données localement et dans le cloud », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question que vous pourriez avoir concernant la fonctionnalité et la configuration du module.
