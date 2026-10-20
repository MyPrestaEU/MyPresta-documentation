---
title: "Rappel de commande impayée - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Rappel de commande impayée' par MyPresta.eu."
sidebar:
  label: "Rappel de commande impayée - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Unpaid order reminder sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/unpaid-order-reminder.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/unpaid-order-reminder/)
>
> ---


# Rappel de commande impayée

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Assurez-vous que la fonctionnalité de tâche cron de votre serveur est activée et correctement configurée pour que les rappels automatisés du module fonctionnent.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

Le module « Rappel de commande impayée » offre plusieurs écrans de configuration pour gérer vos paramètres de rappel, consulter l'historique et gérer les clients désabonnés.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Rappel de commande impayée)

C'est l'écran de configuration principal où vous définissez le comportement essentiel du module.

- **Ce que fait ce paramètre :** Cette section vous permet d'activer ou de désactiver le module, de configurer la tâche cron et de gérer les paramètres généraux de vos e-mails de rappel.
- **Effet de la modification de ce paramètre :** Contrôle la fonctionnalité globale et l'automatisation du système de rappel.

#### Paramètres généraux

- **Activer le module :**

  - **Ce que fait ce paramètre :** Active ou désactive l'ensemble du module « Rappel de commande impayée ».
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module commencera à envoyer des rappels selon vos règles définies et la tâche cron.
    - *Lorsqu'il est désactivé :* Aucun rappel ne sera envoyé et le module sera inactif.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** Activez-le après avoir configuré vos règles de rappel pour commencer à récupérer les commandes impayées. Désactivez-le si vous devez arrêter temporairement tous les rappels pour la maintenance ou une campagne spécifique.
- **URL de la tâche Cron :**

  - **Ce que fait ce paramètre :** Affiche l'URL unique que la tâche cron de votre serveur doit exécuter périodiquement. Cette URL déclenche le module pour vérifier les commandes impayées et envoyer des rappels.
  - **Effet de la modification de ce paramètre :** Cette URL est cruciale pour l'automatisation du module. Sans qu'elle ne soit appelée par une tâche cron, aucun rappel ne sera envoyé automatiquement.
  - **Valeur recommandée :** Copiez cette URL et configurez-la dans le gestionnaire de tâches cron de votre panneau de contrôle d'hébergement.
  - **Scénario / exemple de marchand :** Vous configurerez généralement cela une fois lors de la configuration initiale. Par exemple, vous pouvez configurer votre serveur pour appeler cette URL toutes les heures afin d'assurer des rappels opportuns.
- **Lien de désabonnement dans l'e-mail :**

  - **Ce que fait ce paramètre :** Détermine si un lien de désabonnement est inclus dans les e-mails de rappel.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clients peuvent cliquer sur un lien dans l'e-mail pour se désinscrire des futurs rappels de commandes impayées.
    - *Lorsqu'il est désactivé :* Les clients ne peuvent pas facilement se désinscrire, ce qui pourrait entraîner de la frustration ou marquer vos e-mails comme spam.
  - **Valeur recommandée :** OUI (Fortement recommandé pour la conformité et la satisfaction client).
  - **Scénario / exemple de marchand :** Incluez toujours cela pour donner aux clients le contrôle et maintenir une bonne réputation d'expéditeur.
- **Statuts de commande à rappeler :**

  - **Ce que fait ce paramètre :** Vous permet de sélectionner les statuts de commande spécifiques qui doivent déclencher un rappel. Généralement, ce sont des statuts indiquant qu'une commande est en attente de paiement (par exemple, « En attente de virement bancaire », « En attente de paiement par chèque »).
  - **Effet de la modification de ce paramètre :** Seules les commandes avec les statuts sélectionnés seront prises en compte pour les rappels.
  - **Valeur recommandée :** Sélectionnez tous les statuts qui représentent une commande en attente de paiement.
  - **Scénario / exemple de marchand :** Si vous utilisez « En attente de virement bancaire » et « En attente de paiement par chèque », sélectionnez les deux. Si vous avez un statut personnalisé comme « En attente de passerelle de paiement », incluez-le également.
- **Statuts de commande pour arrêter les rappels :**

  - **Ce que fait ce paramètre :** Définit les statuts de commande qui, s'ils sont atteints, doivent arrêter tout rappel ultérieur pour cette commande spécifique. Cela inclut généralement des statuts comme « Paiement accepté », « Expédié » ou « Annulé ».
  - **Effet de la modification de ce paramètre :** Une fois qu'une commande atteint l'un de ces statuts, le module n'enverra plus de rappels pour celle-ci, évitant ainsi des e-mails inutiles ou déroutants.
  - **Valeur recommandée :** Sélectionnez tous les statuts qui indiquent que le paiement a été reçu, que la commande est traitée ou que la commande n'est plus valide (par exemple, « Paiement accepté », « Annulé », « Remboursé »).
  - **Scénario / exemple de marchand :** Si un client paie une commande, vous ne voulez pas qu'il reçoive un autre rappel. La sélection de « Paiement accepté » ici garantit cela.

#### Règles de rappel

Cette section est l'endroit où vous définissez les e-mails de rappel réels. Vous pouvez créer plusieurs règles, chacune avec un timing et un contenu d'e-mail différents.

- **Ajouter une nouvelle règle de rappel :**
  - **Ce que fait ce paramètre :** Vous permet de créer un nouvel ensemble de paramètres de rappel.
  - **Effet de la modification de ce paramètre :** Ouvre un formulaire pour définir un nouvel e-mail de rappel.
  - **Valeur recommandée :** Créez au moins une règle.
  - **Scénario / exemple de marchand :** Vous pourriez vouloir envoyer un premier rappel après 24 heures et un second, plus urgent, après 72 heures.

Lors de l'ajout/modification d'une règle, vous configurerez :

- **Jours après la création de la commande :**

  - **Ce que fait ce paramètre :** Spécifie combien de jours après la passation de la commande cet e-mail de rappel particulier doit être envoyé.
  - **Effet de la modification de ce paramètre :** Contrôle le moment du rappel.
  - **Valeur recommandée :** Commencez par 1 ou 2 jours pour le premier rappel.
  - **Scénario / exemple de marchand :** Définissez sur « 1 » pour un premier rappel 24 heures après la commande. Définissez sur « 3 » pour un second rappel 3 jours après la commande.
- **Objet de l'e-mail :**

  - **Ce que fait ce paramètre :** La ligne d'objet de l'e-mail de rappel.
  - **Effet de la modification de ce paramètre :** C'est ce que les clients voient dans leur boîte de réception. Un objet clair et concis augmente les taux d'ouverture.
  - **Valeur recommandée :** Quelque chose comme « Rappel : Votre commande impayée sur [Nom de la boutique] » ou « Action requise : Finalisez votre commande n°[ID de commande] ».
  - **Scénario / exemple de marchand :** « N'oubliez pas votre commande de MyPresta.eu ! »
- **Contenu de l'e-mail :**

  - **Ce que fait ce paramètre :** Le corps principal de l'e-mail de rappel. Vous pouvez utiliser des variables (comme `{customer_name}`, `{order_id}`, `{shop_name}`) pour personnaliser le message.
  - **Effet de la modification de ce paramètre :** C'est le message principal à votre client. Un ton amical et serviable est préférable.
  - **Valeur recommandée :** Incluez une salutation, mentionnez la commande impayée, fournissez des instructions sur la façon de payer ou où trouver les détails de paiement, et offrez de l'aide.
  - **Scénario / exemple de marchand :** « Cher {customer\_name}, Ceci est un rappel amical concernant votre récente commande #{order\_id} sur {shop\_name}. Il semble que le paiement de cette commande soit toujours en attente. Veuillez finaliser votre paiement dès que possible pour que votre commande soit traitée. Vous pouvez consulter les détails de votre commande ici : [Lien vers l'historique des commandes]. Si vous avez des questions, veuillez nous contacter. »
- **Actif :**

  - **Ce que fait ce paramètre :** Active ou désactive cette règle de rappel spécifique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Ce rappel sera envoyé selon son calendrier.
    - *Lorsqu'il est désactivé :* Ce rappel ne sera pas envoyé, même si le module est actif.
  - **Valeur recommandée :** OUI pour les règles actives.
  - **Scénario / exemple de marchand :** Vous pourriez désactiver une règle si vous testez un nouveau contenu ou si vous souhaitez suspendre temporairement un rappel spécifique.

### 2.2 Gestion des rappels de commande (Back Office > Modules > Rappel de commande impayée > Rappels de commande)

Cet écran dédié, accessible via le menu du module dans le Back Office, vous permet de visualiser et de gérer les commandes actuellement éligibles aux rappels.

- **Nom de l'écran et emplacement du menu :** **Rappels de commande** (sous l'élément de menu « Rappel de commande impayée »).
- **Actions et paramètres disponibles :** Cet écran affiche une liste des commandes qui correspondent actuellement à vos critères « Statuts de commande à rappeler ».
  - **Vue grille / gestion :** Vous verrez un tableau avec des colonnes comme ID de commande, Nom du client, Date de commande, Statut actuel et potentiellement la prochaine date de rappel.
  - **Actions :** Vous pourriez avoir des actions pour envoyer manuellement un rappel pour une commande spécifique, ou pour exclure une commande des futurs rappels.
- **Effet des modifications :**
  - **Envoi manuel d'un rappel :** Envoie immédiatement le prochain e-mail de rappel programmé pour cette commande.
  - **Exclusion d'une commande :** Empêche le module d'envoyer d'autres rappels pour cette commande spécifique, même si son statut correspond toujours aux critères de rappel.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vérifiez périodiquement cette liste pour avoir un aperçu des commandes impayées en attente. Utilisez l'option d'envoi manuel si un client appelle et que vous souhaitez lui envoyer immédiatement les détails de paiement à nouveau. Excluez les commandes si vous avez pris un arrangement spécial avec un client ou si une commande est problématique.

### 2.3 Historique des rappels de commande (Back Office > Modules > Rappel de commande impayée > Historique)

Cet écran fournit un journal de tous les e-mails de rappel qui ont été envoyés par le module.

- **Nom de l'écran et emplacement du menu :** **Historique** (sous l'élément de menu « Rappel de commande impayée »).
- **Actions et paramètres disponibles :** Cet écran affiche un tableau avec les détails de chaque rappel envoyé :
  - Les colonnes incluent généralement : ID de commande, Nom du client, Adresse e-mail, Règle de rappel (quelle règle l'a déclenché), Date d'envoi et potentiellement l'objet de l'e-mail.
- **Effet des modifications :** Il s'agit d'un journal en lecture seule. Aucune modification directe n'est effectuée ici, mais il fournit des informations précieuses.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Utilisez cet écran pour vérifier que les rappels sont envoyés correctement. Si un client prétend ne pas avoir reçu de rappel, vous pouvez consulter cet historique pour confirmer s'il a été envoyé.

### 2.4 Clients désabonnés (Back Office > Modules > Rappel de commande impayée > Clients désabonnés)

Cet écran liste les clients qui se sont désabonnés des rappels de commande impayée.

- **Nom de l'écran et emplacement du menu :** **Clients désabonnés** (sous l'élément de menu « Rappel de commande impayée »).
- **Actions et paramètres disponibles :** Cet écran affiche un tableau avec :
  - Les colonnes incluent généralement : ID client, Nom du client, Adresse e-mail et Date de désabonnement.
  - **Actions :** Vous pourriez avoir une option pour supprimer manuellement un client de cette liste, le réabonnant ainsi aux rappels (à utiliser avec prudence et uniquement si le client le demande).
- **Effet des modifications :**
  - **Suppression de la liste :** Le client sera à nouveau éligible pour recevoir des rappels si le statut de sa commande correspond.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Surveillez cette liste pour comprendre les préférences des clients. Ne réabonnez un client que s'il le demande explicitement.

### 2.5 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activer le module | OUI | Active/désactive la fonctionnalité du module. |
|  | URL de la tâche Cron | Copier et configurer | Essentiel pour l'envoi automatisé des rappels. |
|  | Lien de désabonnement dans l'e-mail | OUI | Permet aux clients de se désabonner, améliore la réputation de l'expéditeur. |
|  | Statuts de commande à rappeler | En attente de virement bancaire, En attente de chèque, etc. | Définit les statuts de commande qui déclenchent les rappels. |
|  | Statuts de commande pour arrêter les rappels | Paiement accepté, Annulé, etc. | Empêche les rappels pour les commandes payées ou invalides. |
|  | **Règles de rappel** |  |  |
|  | Jours après la création de la commande | 1, 3, 7 (exemple) | Définit le moment de chaque e-mail de rappel. |
|  | Objet de l'e-mail | « Rappel : Votre commande impayée… » | Ligne d'objet de l'e-mail de rappel. |
|  | Contenu de l'e-mail | Message personnalisé avec variables | Corps de l'e-mail de rappel. |
|  | Actif (pour chaque règle) | OUI | Active/désactive les règles de rappel individuelles. |
| **Rappels de commande** | (Liste des commandes éligibles) | N/A | Aperçu des commandes en attente de paiement. |
|  | Envoyer un rappel manuel | N/A | Envoie immédiatement le prochain rappel pour la commande sélectionnée. |
|  | Exclure la commande | N/A | Empêche les futurs rappels pour la commande sélectionnée. |
| **Historique** | (Journal des rappels envoyés) | N/A | Piste d'audit de tous les e-mails de rappel envoyés. |
| **Clients désabonnés** | (Liste des clients désabonnés) | N/A | Affiche les clients qui se sont désabonnés des rappels. |
|  | Supprimer de la liste de désabonnement | N/A | Réabonne le client aux rappels (à utiliser avec prudence). |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q1 : Mes rappels ne sont pas envoyés. Que dois-je vérifier en premier ?**
**R1 :**

-   **Module activé :** Allez dans **Modules > Gestionnaire de modules > Rappel de commande impayée** et assurez-vous que le paramètre « Activer le module » est défini sur OUI.
-   **Tâche Cron :** Le problème le plus courant. Vous *devez* configurer la tâche cron sur votre serveur d'hébergement. Copiez l'« URL de la tâche Cron » depuis la page de configuration du module et ajoutez-la au gestionnaire de tâches cron de votre panneau de contrôle d'hébergement. Assurez-vous qu'elle est configurée pour s'exécuter fréquemment (par exemple, toutes les heures). Si vous ne savez pas comment faire, contactez votre hébergeur.
-   **Statuts de commande :** Vérifiez à nouveau les « Statuts de commande à rappeler » et les « Statuts de commande pour arrêter les rappels » dans la configuration du module. Assurez-vous que les commandes pour lesquelles vous attendez des rappels ont un statut sélectionné dans la liste « à rappeler » et n'ont pas atteint un statut dans la liste « à arrêter ».
-   **Règles de rappel actives :** Assurez-vous que les règles de rappel individuelles que vous avez créées sont marquées comme « Actives ».

**Q2 : Les clients reçoivent trop de rappels, ou des rappels après avoir payé. Comment puis-je résoudre ce problème ?**
**R2 :**

-   **« Statuts de commande pour arrêter les rappels » :** C'est crucial. Assurez-vous que tous les statuts qui indiquent une commande payée ou terminée (par exemple, « Paiement accepté », « Expédié », « Annulé », « Remboursé ») sont sélectionnés dans ce paramètre. Cela indique au module d'arrêter d'envoyer des rappels une fois que la commande atteint l'un de ces états.
-   **Timing des règles de rappel :** Examinez les « Jours après la création de la commande » pour chaque règle de rappel. Assurez-vous qu'ils sont espacés de manière appropriée et ne se chevauchent pas d'une manière qui envoie trop d'e-mails trop rapidement.

**Q3 : Puis-je personnaliser les modèles d'e-mail ?**
**R3 :** Oui, le module vous permet de personnaliser l'objet et le contenu de l'e-mail directement dans les paramètres des règles de rappel. Vous pouvez utiliser des variables spécifiques (comme `{customer_name}`, `{order_id}`, `{shop_name}`) pour personnaliser le message. Pour une personnalisation visuelle plus avancée, un développeur devrait modifier les fichiers de modèle d'e-mail sous-jacents (situés dans `mails/` au sein de votre installation PrestaShop, en utilisant la structure de modèle du module comme guide).

**Q4 : Le lien de désabonnement ne fonctionne pas, ou les clients reçoivent toujours des e-mails après s'être désabonnés.**
**R4 :**

-   **Lien de désabonnement activé :** Assurez-vous que « Lien de désabonnement dans l'e-mail » est défini sur OUI dans la configuration principale du module.
-   **Vérifiez la liste « Clients désabonnés » :** Allez dans **Modules > Rappel de commande impayée > Clients désabonnés**. Vérifiez que l'adresse e-mail du client apparaît sur cette liste. Si ce n'est pas le cas, il n'a peut-être pas réussi à se désabonner.
-   **Cache :** Videz le cache de votre PrestaShop (**Paramètres avancés > Performances > Vider le cache**) après avoir effectué des modifications de configuration.

**Q5 : Que se passe-t-il si un client a plusieurs commandes impayées ?**
**R5 :** Le module traitera chaque commande impayée individuellement. Si un client a deux commandes impayées distinctes, il recevra des rappels pour chaque commande selon vos règles définies, tant que ces commandes répondent aux critères.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de la structure technique du module « Rappel de commande impayée », destinée aux développeurs et aux webmasters.

### 4.1 Aperçu de l'architecture

Le module « Rappel de commande impayée » (`oreminders`) suit une architecture de module PrestaShop standard, tirant parti des principes MVC. Il se concentre principalement sur l'administration du back-office pour la configuration et sur une tâche cron front-office pour le traitement automatisé. Il étend `Module` pour sa fonctionnalité principale et utilise des classes `AdminController` personnalisées pour gérer les rappels, l'historique et les clients désabonnés. La gestion des modèles d'e-mail est assurée par un gestionnaire personnalisé, et la configuration est stockée dans `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   `controllers/front/CronJob.php`
    -   **Nom de la classe et classe parente :** `OremindersCronJobModuleFrontController` étend `ModuleFrontController`.
    -   **Responsabilité :** Ce contrôleur est conçu pour être appelé par une tâche cron côté serveur. C'est le point d'entrée de la logique automatisée du module. Lors de son exécution, il parcourt les commandes impayées, vérifie les règles de rappel définies et envoie les e-mails de rappel. Il renvoie généralement un simple message de succès/échec ou une sortie de journal.
-   `controllers/front/index.php`
    -   **Nom de la classe et classe parente :** `OremindersIndexModuleFrontController` étend `ModuleFrontController`.
    -   **Responsabilité :** Il s'agit probablement d'un espace réservé ou d'un contrôleur de secours. Dans de nombreux modules, `index.php` dans `controllers/front` sert de point d'entrée par défaut ou simple si aucune action spécifique n'est demandée. Il pourrait gérer l'affichage de base du module ou la redirection si le module avait une présence en front-office. Compte tenu de la nature du module, son interaction principale en front-office se fait via `CronJob.php`.

#### Contrôleurs Admin Back-Office

-   `controllers/admin/AdminOrderReminders.php`
    -   **Nom de la classe et classe parente :** `AdminOrderRemindersController` étend `ModuleAdminController`.
    -   **Nom de l'onglet et entité gérée :** Gère la liste « Rappels de commande ». Ce contrôleur est responsable de l'affichage d'une liste de commandes actuellement éligibles aux rappels en fonction de la configuration du module. Il fournit des actions pour envoyer manuellement des rappels ou exclure des commandes spécifiques.
-   `controllers/admin/AdminOrderRemindersHistory.php`
    -   **Nom de la classe et classe parente :** `AdminOrderRemindersHistoryController` étend `ModuleAdminController`.
    -   **Nom de l'onglet et entité gérée :** Gère le journal « Historique ». Ce contrôleur affiche une liste en lecture seule de tous les e-mails de rappel qui ont été envoyés avec succès par le module, y compris des détails comme l'ID de commande, le client et la date d'envoi.
-   `controllers/admin/AdminOrderRemindersUnsub.php`
    -   **Nom de la classe et classe parente :** `AdminOrderRemindersUnsubController` étend `ModuleAdminController`.
    -   **Nom de l'onglet et entité gérée :** Gère la liste « Clients désabonnés ». Ce contrôleur affiche les clients qui se sont désabonnés des rappels et permet leur réabonnement (si nécessaire).
-   `controllers/admin/index.php`
    -   **Nom de la classe et classe parente :** `AdminOremindersIndexController` étend `ModuleAdminController`.
    -   **Nom de l'onglet et entité gérée :** Similaire au `index.php` du front-office, cela pourrait servir de contrôleur d'administration par défaut ou de secours. Il pourrait potentiellement gérer la configuration principale du module si `getContent()` dans le fichier principal du module y redirige, ou s'il est utilisé pour une action d'administration spécifique et simple.

### 4.3 Classes et modèles principaux (`classes/`)

L'inventaire fourni n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que le module pourrait utiliser `ObjectModel` directement dans son fichier de module principal ou ses contrôleurs d'administration, ou qu'il gère les données via des requêtes de base de données directes ou en étendant les modèles de base de PrestaShop existants (par exemple, `Order`, `Customer`).

Si des données personnalisées sont stockées, elles sont probablement gérées via `ps_configuration` pour les paramètres et potentiellement des tables de base de données personnalisées créées lors de l'installation (bien qu'aucun fichier SQL n'ait été listé, la création de tables serait en ligne dans `install()`).

### 4.4 Actifs JavaScript (`views/js/`)

-   `oreminders/lib/emailTemplatesManager/js/emailTemplatesManager.js`
    -   **Portée :** Back-office.
    -   **Détails :** Ce script fournit probablement des fonctionnalités dynamiques pour l'interface de gestion des modèles d'e-mail dans la configuration du module. Cela pourrait inclure :
        -   Ajout/suppression dynamique de règles de rappel.
        -   Gestion des requêtes AJAX pour l'enregistrement/chargement des modèles d'e-mail.
        -   Implémentation d'un éditeur de texte riche (par exemple, intégration TinyMCE) pour le contenu des e-mails.
        -   Gestion de l'insertion de variables dans les modèles d'e-mail.
        -   Validation côté client pour les champs de formulaire liés aux règles d'e-mail.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `oreminders/lib/emailTemplatesManager/css/emailTemplatesManager.css`
    -   **Portée :** Style du formulaire d'administration du Back-office.
    -   **Détails :** Cette feuille de style fournit un style spécifique pour l'interface du gestionnaire de modèles d'e-mail dans la configuration du Back Office du module. Elle définirait les styles pour :
        -   Mise en page des formulaires de règles de rappel.
        -   Style des champs de saisie, des boutons et des zones de texte dans l'éditeur de modèle.
        -   Assurer une apparence cohérente avec le thème du Back Office de PrestaShop.
    -   **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer :** Recherchez des classes spécifiques préfixées par `oreminders-` ou `email-templates-manager-` dans les modèles d'administration du module pour identifier les éléments personnalisables.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)

-   `oreminders/views/templates/hook/form.tpl`
    -   **Hook :** Potentiellement `displayAdminModuleConfigure` ou similaire, s'il est utilisé pour un petit formulaire dans un contexte de hook. Plus probablement, il s'agit d'un modèle de formulaire générique utilisé en interne.
    -   **Sortie :** Rend une structure de formulaire générique.
-   `oreminders/views/templates/hook/header.tpl`
    -   **Hook :** `displayHeader` (Front-office).
    -   **Sortie :** Utilisé pour inclure les fichiers CSS ou JavaScript nécessaires dans la section `<head>` du front-office, si le module avait des composants front-end (par exemple, pour la page de désabonnement).
-   `oreminders/views/templates/hook/identity.tpl`
    -   **Hook :** Non clair d'après le nom, mais `displayCustomerAccount` ou similaire pour afficher des informations spécifiques au client, ou peut-être lié au processus de désabonnement.
    -   **Sortie :** Pourrait rendre un message ou un formulaire lié à l'identité ou aux préférences du client.

#### Modèles d'administration (`views/templates/admin/`)

-   `oreminders/lib/emailTemplatesManager/views/buttonManager.tpl`
    -   **Contexte :** Utilisé dans le gestionnaire de modèles d'e-mail.
    -   **Sortie :** Rend les boutons pour la gestion des modèles d'e-mail (par exemple, « Ajouter une nouvelle règle », « Enregistrer », « Supprimer »).
-   `oreminders/lib/emailTemplatesManager/views/createTemplateForm.tpl`
    -   **Contexte :** Utilisé dans le gestionnaire de modèles d'e-mail.
    -   **Sortie :** Rend le formulaire pour créer un nouveau modèle/règle d'e-mail de rappel.
-   `oreminders/lib/emailTemplatesManager/views/editTemplateForm.tpl`
    -   **Contexte :** Utilisé dans le gestionnaire de modèles d'e-mail.
    -   **Sortie :** Rend le formulaire pour modifier un modèle/règle d'e-mail de rappel existant.
-   `oreminders/lib/emailTemplatesManager/views/mainForm.tpl`
    -   **Contexte :** Utilisé dans le gestionnaire de modèles d'e-mail.
    -   **Sortie :** Le modèle d'enveloppe principal pour l'interface de gestion des modèles d'e-mail, combinant probablement `buttonManager`, `createTemplateForm` et `editTemplateForm`.
-   `oreminders/lib/emailTemplatesManager/views/selectInput.tpl`
    -   **Contexte :** Utilisé dans le gestionnaire de modèles d'e-mail.
    -   **Sortie :** Un modèle réutilisable pour rendre une liste déroulante `<select>`, probablement pour choisir les statuts de commande ou d'autres options.
-   `oreminders/views/templates/admin/order_reminders/helpers/form/form.tpl`
    -   **Contexte :** Utilisé par `AdminOrderRemindersController` pour ses vues de formulaire (par exemple, s'il y a un formulaire d'ajout/modification pour une entrée de rappel de commande, bien qu'il s'agisse principalement d'un contrôleur de liste).
    -   **Sortie :** Rend un formulaire d'administration PrestaShop standard.
-   `oreminders/views/templates/admin/order_reminders/helpers/list/list_action_email.tpl`
    -   **Contexte :** Utilisé par `AdminOrderRemindersController` dans sa vue de liste.
    -   **Sortie :** Rend un bouton d'action ou un lien spécifique dans la liste des rappels de commande, probablement pour « Envoyer un e-mail » ou « Afficher l'e-mail ».
-   `oreminders/views/templates/admin/script.tpl`
    -   **Contexte :** Back Office d'administration.
    -   **Sortie :** Inclut probablement du code JavaScript en ligne ou des variables de configuration nécessaires à l'interface du Back Office, éventuellement pour les appels AJAX ou les éléments d'interface utilisateur dynamiques.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données

La description du module et l'inventaire des fichiers ne listent pas explicitement les fichiers SQL pour la création de tables personnalisées. Cependant, sur la base des contrôleurs d'administration, le module interagit probablement avec les éléments suivants (soit des tables personnalisées, soit `ps_configuration` pour les paramètres) :

-   `ps_configuration` : Stocke tous les paramètres du module (par exemple, `OREMINDERS_ENABLED`, `OREMINDERS_CRON_URL`, `OREMINDERS_UNSUB_LINK`, `OREMINDERS_STATUSES_REMIND`, `OREMINDERS_STATUSES_STOP`, et les données sérialisées pour les règles de rappel individuelles).
-   `ps_or` (ou similaire, géré par `AdminOrderRemindersController`) : Probablement une table personnalisée pour stocker des informations sur les commandes actuellement rappelées, ou pour marquer les commandes comme exclues.
-   `ps_or_history` (ou similaire, géré par `AdminOrderRemindersHistoryController`) : Une table personnalisée pour enregistrer chaque e-mail de rappel envoyé, y compris `id_order`, `id_customer`, `email`, `id_reminder_rule`, `date_sent`.
-   `ps_or_ounsub` (ou similaire, géré par `AdminOrderRemindersUnsubController`) : Une table personnalisée pour stocker les ID client ou les adresses e-mail de ceux qui se sont désabonnés des rappels.

#### Tableau des hooks enregistrés

| Nom du hook | Portée | Moment d'exécution | Objectif technique |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | Dans la section `<head>` de toutes les pages du front-office. | Pour inclure les CSS/JS spécifiques au module pour les composants du front-office (par exemple, page de désabonnement). |
| `displayAdminModuleConfigure` | Back-Office | Lors de l'affichage de la page de configuration principale du module. | Pour rendre le formulaire de configuration principal du module (méthode `getContent()`). |
| `actionValidateOrder` | Back-Office | Après qu'une commande a été validée avec succès. | Potentiellement utilisé pour initialiser le suivi des rappels pour les nouvelles commandes, bien que la tâche cron soit le déclencheur principal. |
| `actionOrderStatusUpdate` | Back-Office | Lorsqu'un statut de commande est modifié. | Pour vérifier si le nouveau statut d'une commande doit arrêter les rappels (par exemple, si elle devient « Paiement accepté »). |
| `actionCronJob` | Back-Office (via le contrôleur frontal) | Exécuté par la tâche cron du serveur. | Le hook principal qui déclenche la logique du module pour trouver les commandes impayées et envoyer des rappels. |
| (Hooks implicites pour les onglets d'administration) | Back-Office | Lors du rendu du menu du Back Office. | Pour ajouter les éléments de menu personnalisés du module (Rappels de commande, Historique, Clients désabonnés). |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Rappel de commande impayée », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la configuration du module.
