---
title: "Rappel de Bon d'Achat - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Rappel de Bon d'Achat par MyPresta.eu."
sidebar:
  label: "Rappel de Bon d'Achat - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Voucher Reminder sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-reminder.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/voucher-reminder/)
>
> ---


# Rappel de Bon d'Achat

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. L'accès pour configurer une tâche cron sur votre serveur est essentiel pour le fonctionnement automatique du module.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, le premier écran que vous verrez est la page de configuration principale du module Rappel de Bon d'Achat. Cette page est cruciale pour configurer la fonctionnalité principale.

**URL de la tâche Cron :**

- **Ce que fait ce paramètre :** Il affiche une URL unique que la tâche cron de votre serveur doit appeler périodiquement. Cette URL déclenche le module pour vérifier les bons d'achat expirant et envoyer des rappels.
- **Effet de la modification de ce paramètre :** Vous ne pouvez pas modifier cette URL directement. Elle est générée par le module. Si la tâche cron n'est pas configurée correctement sur votre serveur pour appeler cette URL, le module n'enverra aucun rappel automatiquement.
- **Valeur recommandée :** Copiez cette URL exactement et utilisez-la pour configurer une tâche cron sur votre serveur d'hébergement.
- **Scénario / exemple marchand :** Vous avez créé plusieurs règles de rappel, mais aucun e-mail n'est envoyé. La première chose à vérifier est si vous avez correctement configuré la tâche cron sur votre serveur en utilisant cette URL.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 Gestion des rappels de bons d'achat (Back Office > Modules > Rappel de Bon d'Achat > Rappels de Bons d'Achat)

C'est ici que vous définissez et gérez les règles de rappel. Chaque règle spécifie quand un rappel doit être envoyé et quel modèle d'e-mail il doit utiliser.

- **Nom de l'écran et emplacement du menu :** **Rappels de Bons d'Achat** (sous **Modules > Rappel de Bon d'Achat** dans le menu principal de PrestaShop).
- **Actions et paramètres disponibles :**
  - **Liste des rappels :** Vous verrez un tableau listant toutes vos règles de rappel définies.
  - **Ajouter un nouveau rappel :** Cliquez sur le bouton « Ajouter » pour créer une nouvelle règle de rappel.
    - **Rappeler (heures avant expiration) :**
      - **Ce que fait ce paramètre :** C'est le paramètre le plus critique pour une règle de rappel. Il détermine combien d'heures *avant* la date d'expiration d'un bon d'achat l'e-mail de rappel doit être envoyé.
      - **Effet de la modification de ce paramètre :**
        - *Défini à 24 :* Un e-mail de rappel sera envoyé exactement 24 heures avant l'expiration du bon d'achat.
        - *Défini à 72 :* Un e-mail de rappel sera envoyé 3 jours (72 heures) avant l'expiration.
      - **Valeur recommandée :** Cela dépend de votre stratégie. Les valeurs courantes sont 24, 48, 72 heures, ou même 168 heures (1 semaine).
      - **Scénario / exemple marchand :** Vous souhaitez donner aux clients un dernier coup de pouce un jour avant l'expiration de leur bon d'achat. Vous définiriez cela à `24`. Si vous voulez leur donner un préavis d'une semaine, vous le définiriez à `168`.
    - **Titre :**
      - **Ce que fait ce paramètre :** Un nom descriptif pour votre règle de rappel, visible uniquement dans le Back Office. Cela vous aide à identifier les différentes règles de rappel.
      - **Effet de la modification de ce paramètre :** Modifie l'étiquette de cette règle dans votre panneau d'administration. Aucun impact sur le front-office.
      - **Valeur recommandée :** Quelque chose de clair et descriptif, par exemple, « 24 heures avant expiration », « Une semaine avant expiration du bon d'achat ».
      - **Scénario / exemple marchand :** Vous avez plusieurs rappels. Les nommer « Rappel 1 jour » et « Rappel 3 jours » facilite la gestion.
    - **Titre de l'e-mail :**
      - **Ce que fait ce paramètre :** C'est l'objet de l'e-mail que vos clients recevront.
      - **Effet de la modification de ce paramètre :** Modifie directement l'objet des e-mails de rappel.
      - **Valeur recommandée :** Quelque chose d'engageant et de clair, par exemple, « Votre [Code de bon d'achat] est sur le point d'expirer ! », « Ne manquez pas votre réduction ! ».
      - **Scénario / exemple marchand :** Vous voulez que l'e-mail se démarque dans la boîte de réception du client. Un objet comme « Dernière chance : Votre réduction expire bientôt ! » est plus efficace qu'un objet générique.
    - **Fichier de modèle d'e-mail :**
      - **Ce que fait ce paramètre :** Spécifie quel fichier de modèle d'e-mail (par exemple, `voucher_reminder.html` et `voucher_reminder.txt`) le module doit utiliser pour ce rappel spécifique. Cela vous permet d'avoir différentes conceptions d'e-mail pour différents moments de rappel.
      - **Effet de la modification de ce paramètre :** Détermine le contenu et la mise en page de l'e-mail envoyé. Si vous créez un modèle personnalisé, vous sélectionneriez son nom ici.
      - **Valeur recommandée :** Utilisez le modèle par défaut, sauf si vous avez des besoins de conception spécifiques. Si vous créez des modèles personnalisés, assurez-vous qu'ils sont correctement placés dans le répertoire `mails` de votre thème.
      - **Scénario / exemple marchand :** Vous souhaitez un e-mail de rappel doux une semaine avant, et un e-mail plus urgent de « dernière chance » 24 heures avant. Vous créeriez deux modèles d'e-mail différents et les assigneriez à leurs règles de rappel respectives.
    - **Envoyer le rappel :**
      - **Ce que fait ce paramètre :** Un simple interrupteur ON/OFF pour activer ou désactiver cette règle de rappel spécifique.
      - **Effet de la modification de ce paramètre :**
        - *Activé (Oui) :* Le module enverra des e-mails selon cette règle.
        - *Désactivé (Non) :* Cette règle sera ignorée, et aucun e-mail ne sera envoyé pour celle-ci.
      - **Valeur recommandée :** « Oui » une fois que vous avez configuré la règle et que vous êtes prêt à l'utiliser.
      - **Scénario / exemple marchand :** Vous testez une nouvelle règle de rappel et voulez vous assurer qu'elle est parfaite avant de l'activer pour tous les clients. Vous la maintiendriez désactivée pendant les tests.
  - **Bouton Enregistrer :** Applique toutes les modifications apportées à la règle de rappel.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Commencez par créer une ou deux règles de rappel (par exemple, 72 heures et 24 heures avant l'expiration).
  2. Utilisez des titres clairs et des objets d'e-mail convaincants.
  3. Surveillez l'« Historique des rappels de bons d'achat » pour voir si les e-mails sont envoyés comme prévu.
  4. Envisagez de créer des modèles d'e-mail personnalisés pour différents moments de rappel afin d'adapter votre message.

#### 2.2.2 Historique des rappels de bons d'achat (Back Office > Modules > Rappel de Bon d'Achat > Historique)

Cet écran fournit un journal de tous les e-mails de rappel qui ont été envoyés avec succès par le module.

- **Nom de l'écran et emplacement du menu :** **Historique** (sous **Modules > Rappel de Bon d'Achat** dans le menu principal de PrestaShop).
- **Actions et paramètres disponibles :**
  - **Liste des rappels envoyés :** Un tableau affichant :
    - **ID :** Identifiant unique pour l'entrée de l'historique.
    - **Date d'envoi de l'e-mail :** Quand l'e-mail a été envoyé.
    - **Rappel :** Quelle règle de rappel (par titre) a déclenché cet e-mail.
    - **Client :** Le client qui a reçu le rappel.
    - **Bon d'achat :** Le code de bon d'achat spécifique qui a fait l'objet du rappel.
- **Effet des modifications :** Il s'agit d'un journal en lecture seule. Vous ne pouvez pas y apporter de modifications, mais il est inestimable pour vérifier le fonctionnement du module.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vérifiez régulièrement cet historique pour vous assurer que les rappels sont envoyés comme prévu. Si vous remarquez des lacunes ou un comportement inattendu, ce journal est votre premier point de référence pour le dépannage.

#### 2.2.3 Désabonnements (Back Office > Modules > Rappel de Bon d'Achat > Désabonnements)

Cet écran liste les clients qui se sont désabonnés des rappels de bons d'achat.

- **Nom de l'écran et emplacement du menu :** **Désabonnements** (sous **Modules > Rappel de Bon d'Achat** dans le menu principal de PrestaShop).
- **Actions et paramètres disponibles :**
  - **Liste des clients désabonnés :** Un tableau affichant :
    - **ID :** Identifiant unique pour l'entrée de désabonnement.
    - **E-mail :** L'adresse e-mail du client qui s'est désabonné.
    - **IP :** L'adresse IP à partir de laquelle la désinscription a eu lieu.
    - **Date de désabonnement :** Quand le client s'est désabonné.
  - **Ajouter un nouveau désabonnement :** Vous pouvez ajouter manuellement une adresse e-mail à la liste de désabonnement.
    - **E-mail du client :** Saisissez l'adresse e-mail que vous souhaitez désabonner.
    - **IP :** (Facultatif) L'adresse IP associée à la désinscription.
    - **Date :** (Facultatif) La date de désinscription.
    - **Bouton Enregistrer :** Ajoute le client à la liste de désabonnement.
- **Effet des modifications :** Les clients listés ici ne recevront plus d'e-mails de rappel de bons d'achat de votre boutique, même s'ils ont des bons d'achat expirant. L'ajout manuel d'un e-mail garantit qu'ils sont désabonnés.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Bien que les clients puissent se désabonner eux-mêmes, cet écran vous permet d'ajouter manuellement des clients s'ils vous contactent directement pour demander à être retirés des listes de rappel. C'est également un bon endroit pour surveiller les tendances de désabonnement.

#### 2.2.4 index.php (vreminders/controllers/admin/index.php)

Ce fichier est généralement un espace réservé ou une redirection au sein de la structure d'administration de PrestaShop et ne représente pas un écran direct et configurable pour le marchand. Son but est généralement de s'assurer que l'accès direct au répertoire est restreint ou de rediriger vers la configuration principale du module.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | URL de la tâche Cron | (URL générée) | Essentiel pour configurer l'automatisation côté serveur pour envoyer des rappels. |
| **Rappels de Bons d'Achat** | Rappeler (heures avant expiration) | Varie (par exemple, 24, 72) | Définit le moment de l'e-mail de rappel par rapport à l'expiration du bon d'achat. |
| | Titre | Descriptif (par exemple, « Rappel 1 jour ») | Libellé interne pour identifier les règles de rappel dans le Back Office. |
| | Titre de l'e-mail | Objet engageant | L'objet de l'e-mail que les clients reçoivent. |
| | Fichier de modèle d'e-mail | `voucher_reminder` | Spécifie le modèle d'e-mail utilisé pour ce rappel. |
| | Envoyer le rappel | Oui | Active ou désactive une règle de rappel spécifique. |
| **Historique des rappels de bons d'achat** | (Tous les champs) | N/A (Lecture seule) | Journal de tous les e-mails de rappel envoyés pour vérification et dépannage. |
| **Désabonnements** | E-mail du client | N/A | Ajouter manuellement les e-mails des clients pour les empêcher de recevoir des rappels. |
| | IP | N/A | (Facultatif) Adresse IP associée à la désinscription. |
| | Date | N/A | (Facultatif) Date de désinscription. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : Mes rappels ne sont pas envoyés. Que dois-je vérifier en premier ?**
R : La raison la plus courante est une tâche cron mal configurée.

1. Allez dans **Modules > Rappel de Bon d'Achat > Configurer**.
2. Copiez exactement l'« URL de la tâche Cron ».
3. Connectez-vous à votre panneau de contrôle d'hébergement (cPanel, Plesk, etc.) et naviguez vers la section « Tâches Cron ».
4. Créez une nouvelle tâche cron qui appelle cette URL toutes les 5 à 15 minutes. La commande ressemble généralement à `wget -q -O /dev/null "VOTRE_URL_DE_TACHE_CRON_ICI"` ou `curl -s "VOTRE_URL_DE_TACHE_CRON_ICI" > /dev/null`.
5. Assurez-vous également que les règles de rappel individuelles sont activées (« Envoyer le rappel » est défini sur « Oui ») sous **Modules > Rappel de Bon d'Achat > Rappels de Bons d'Achat**.

**Q : Des clients se plaignent de ne pas recevoir de rappels, mais l'historique indique qu'ils ont été envoyés.**
R : Cela indique généralement des problèmes de livraison d'e-mails.

1. **Vérifiez les dossiers de spam :** Conseillez aux clients de vérifier leurs dossiers de spam ou de courrier indésirable.
2. **Configuration du serveur de messagerie :** Assurez-vous que les paramètres d'e-mail de votre boutique PrestaShop (sous **Paramètres avancés > E-mail**) sont correctement configurés et que votre serveur n'est pas sur liste noire. L'utilisation d'un serveur SMTP (comme SendGrid, Mailgun, etc.) est souvent plus fiable que la fonction `mail()` de PHP.
3. **Problèmes de modèle d'e-mail :** Assurez-vous que vos modèles d'e-mail sont des fichiers HTML/texte valides et ne contiennent pas de liens brisés ou d'images qui pourraient déclencher les filtres anti-spam.

**Q : Puis-je personnaliser les modèles d'e-mail ?**
R : Oui !

1. Le module utilise des modèles d'e-mail PrestaShop standard. Vous pouvez trouver les fichiers de modèle par défaut dans `modules/vreminders/mails/fr/` (ou votre dossier de langue).
2. **Meilleure pratique :** Copiez ces fichiers dans le répertoire `mails/fr/` de votre thème actif (par exemple, `themes/votreetheme/mails/fr/`). De cette façon, vos personnalisations ne seront pas écrasées lors de la mise à jour du module.
3. Modifiez les fichiers `.html` et `.txt` pour correspondre à votre marque et à votre message. Vous pouvez utiliser les variables Smarty disponibles dans les modèles d'e-mail PrestaShop.
4. Si vous créez des fichiers de modèle entièrement nouveaux (par exemple, `mon_rappel_personnalise.html`), vous devrez sélectionner `mon_rappel_personnalise` dans le paramètre « Fichier de modèle d'e-mail » pour votre règle de rappel.

**Q : Comment puis-je tester les rappels sans les envoyer à de vrais clients ?**
R :

1. Créez un compte client test dans votre boutique.
2. Créez manuellement un code de bon d'achat pour ce client test avec une date d'expiration dans quelques heures ou jours.
3. Configurez une règle de rappel avec un « Rappeler (heures avant expiration) » court (par exemple, 1 heure).
4. Au lieu d'attendre la tâche cron, vous pouvez déclencher manuellement l'URL cron dans votre navigateur (bien que cela ne soit pas recommandé pour la production).
5. Vérifiez l'« Historique des rappels de bons d'achat » et la boîte de réception du client test.
6. Une fois satisfait, supprimez le bon d'achat et la règle de rappel de test, et configurez vos règles de production.

**Q : Que se passe-t-il si un client utilise son bon d'achat après l'envoi d'un rappel mais avant son expiration ?**
R : Le module est conçu pour n'envoyer des rappels que pour les bons d'achat *non utilisés*. Si un client utilise son bon d'achat, il ne sera plus considéré comme « actif » et « non utilisé », donc aucun autre rappel pour ce bon d'achat spécifique ne sera envoyé.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Rappel de Bon d'Achat » suit une architecture de module PrestaShop standard, tirant parti des principes MVC. Sa fonctionnalité principale repose sur une tâche cron qui vérifie périodiquement les bons d'achat expirant et envoie des e-mails basés sur les règles configurées. Il utilise l'`ObjectModel` de PrestaShop pour gérer ses entités personnalisées (rappels, historique, désabonnements) et les mécanismes d'e-mail standard pour la communication. La logique principale du module réside dans `cronjob.php` (qui agit comme la classe de module principale) et les contrôleurs d'administration dédiés pour les opérations CRUD sur ses données personnalisées.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :

  - `controllers/front/CronJob.php`
    - **Nom de la classe et classe parente** : `VremindersCronJobModuleFrontController` étend `ModuleFrontController`.
    - **Responsabilité** : Ce contrôleur est le point d'entrée de la tâche cron du module. Lorsque l'URL cron (générée dans la configuration du module) est accédée, ce contrôleur est exécuté. Il contient la logique pour récupérer les bons d'achat expirant, vérifier les règles de rappel configurées et envoyer les e-mails. Il ne rend généralement aucune sortie visuelle mais effectue un traitement en arrière-plan.
  - `controllers/front/index.php`
    - **Nom de la classe et classe parente** : Pas une classe, généralement un fichier vide ou un simple `die('No direct script access allowed')` pour empêcher la liste ou l'accès direct au répertoire.
- **Contrôleurs d'administration Back-Office** :

  - `controllers/admin/AdminVoucherReminders.php`
    - **Nom de l'onglet et entité gérée** : Gère la liste et les formulaires des « Rappels de Bons d'Achat » dans le Back Office. Il gère les opérations CRUD pour l'entité `VoucherReminder` (qui correspond à la table `ps_vr`).
  - `controllers/admin/AdminVoucherRemindersHistory.php`
    - **Nom de l'onglet et entité gérée** : Gère la liste de l'« Historique des Rappels de Bons d'Achat » dans le Back Office. Il affiche un journal en lecture seule des rappels envoyés, correspondant à l'entité `VoucherReminderHistory` (qui correspond à la table `ps_vr_history`).
  - `controllers/admin/AdminVRemindersUnsub.php`
    - **Nom de l'onglet et entité gérée** : Gère la liste et les formulaires des « Désabonnements » dans le Back Office. Il gère les opérations CRUD pour l'entité `VoucherReminderUnsub` (qui correspond à la table `ps_vr_vunsub`).
  - `controllers/admin/index.php`
    - **Nom de la classe et classe parente** : Pas une classe, généralement un fichier vide ou un simple `die('No direct script access allowed')` pour empêcher la liste ou l'accès direct au répertoire.

### 4.3 Classes et modèles principaux (`classes/`)

Le dossier du module n'indique pas de répertoire `classes/` explicite. Cela implique que les classes `ObjectModel` principales sont probablement définies directement dans le fichier de module principal (`cronjob.php`) ou dans les fichiers de contrôleur d'administration respectifs. Basé sur la structure typique des modules PrestaShop et les entités identifiées, les classes `ObjectModel` suivantes devraient être présentes, probablement définies dans `cronjob.php` ou `AdminVoucherReminders.php`, `AdminVoucherRemindersHistory.php`, `AdminVRemindersUnsub.php` :

- **`VoucherReminder` (ou similaire)**

  - **Table de base de données** : `ps_vr` (ou `_vreminders_vr`)
  - **Étend `ObjectModel`** : Oui.
  - **Champs `$definition`** : Les champs attendus incluent `id_vr`, `remind_hours`, `title`, `email_title`, `email_template`, `active`.
  - **Méthodes publiques clés** : Méthodes pour ajouter, mettre à jour, supprimer des règles de rappel, et potentiellement des méthodes pour récupérer les règles actives.
- **`VoucherReminderHistory` (ou similaire)**

  - **Table de base de données** : `ps_vr_history` (ou `_vreminders_vr_history`)
  - **Étend `ObjectModel`** : Oui.
  - **Champs `$definition`** : Les champs attendus incluent `id_vr_history`, `id_vr`, `id_customer`, `id_cart_rule`, `date_add`.
  - **Méthodes publiques clés** : Méthodes pour enregistrer les rappels envoyés.
- **`VoucherReminderUnsub` (ou similaire)**

  - **Table de base de données** : `ps_vr_vunsub` (ou `_vreminders_vr_vunsub`)
  - **Étend `ObjectModel`** : Oui.
  - **Champs `$definition`** : Les champs attendus incluent `id_vunsub`, `email`, `ip`, `date_add`.
  - **Méthodes publiques clés** : Méthodes pour gérer les désabonnements, y compris l'ajout et la vérification des e-mails désabonnés.

### 4.4 Actifs JavaScript (`views/js/`)

Le dossier du module n'indique aucun fichier JavaScript. Cela suggère que le module s'appuie entièrement sur les fonctionnalités JavaScript de base de PrestaShop pour ses formulaires et listes du Back Office, ou que tout JS minimal est intégré directement dans les modèles.

### 4.5 Feuilles de style CSS (`views/css/`)

Le dossier du module n'indique aucun fichier CSS. Cela suggère que le module s'appuie entièrement sur le CSS de base du Back Office de PrestaShop pour ses interfaces d'administration, et que tout style front-office (pour les e-mails) est géré dans les modèles d'e-mail eux-mêmes.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **Modèles d'administration (`views/templates/admin/`)** :

  - `vreminders/views/templates/admin/order_reminders/helpers/form/form.tpl`
    - **Objectif** : Ce modèle est probablement utilisé par `AdminVoucherRemindersController` pour rendre le formulaire d'ajout/édition des règles de rappel de bons d'achat individuelles. Il contiendrait les champs de saisie pour « Rappeler (heures avant expiration) », « Titre », « Titre de l'e-mail », « Fichier de modèle d'e-mail » et « Envoyer le rappel ».
- **Modèles de hook (`views/templates/hook/`)** :

  - `vreminders/views/templates/hook/form.tpl`
    - **Objectif** : Ce modèle pourrait être un modèle de formulaire générique ou un modèle spécifique pour un hook qui affiche un formulaire. Compte tenu de la nature du module, il est moins probable qu'il s'agisse d'un formulaire front-office visible et plus probable d'un composant interne ou d'un hook hérité. Sans plus de contexte, son emplacement exact en front-office n'est pas clair, mais il pourrait s'agir d'un formulaire de désabonnement ou similaire.
  - `vreminders/views/templates/hook/header.tpl`
    - **Objectif** : Ce modèle est rendu dans le hook `displayHeader`. Il est généralement utilisé pour inclure des fichiers CSS ou JavaScript, des balises meta ou d'autres éléments qui doivent être chargés dans la section `<head>` du document HTML. Pour ce module, il pourrait être utilisé pour inclure tout JS nécessaire pour la tâche cron ou pour configurer des balises meta spécifiques, bien que le dossier n'indique aucun fichier JS/CSS. Il pourrait également s'agir d'un espace réservé.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de la base de données** :

  - `ps_vr` (ou `_vreminders_vr`) : Stocke la configuration de chaque règle de rappel de bon d'achat.
    - `id_vr` (PK, INT)
    - `remind_hours` (INT)
    - `title` (VARCHAR)
    - `email_title` (VARCHAR)
    - `email_template` (VARCHAR)
    - `active` (TINYINT)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - `ps_vr_history` (ou `_vreminders_vr_history`) : Enregistre chaque e-mail de rappel envoyé.
    - `id_vr_history` (PK, INT)
    - `id_vr` (FK vers `ps_vr.id_vr`, INT)
    - `id_customer` (FK vers `ps_customer.id_customer`, INT)
    - `id_cart_rule` (FK vers `ps_cart_rule.id_cart_rule`, INT)
    - `date_add` (DATETIME)
  - `ps_vr_vunsub` (ou `_vreminders_vr_vunsub`) : Stocke les adresses e-mail des clients qui se sont désabonnés des rappels.
    - `id_vunsub` (PK, INT)
    - `email` (VARCHAR)
    - `ip` (VARCHAR)
    - `date_add` (DATETIME)
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page front-office. | Pour inclure les actifs nécessaires (JS/CSS) ou les balises meta pour le module. |
| `actionModuleInstall` | Lors de l'installation du module. | Pour créer les tables de la base de données et la configuration par défaut. |
| `actionModuleUninstall` | Lors de la désinstallation du module. | Pour supprimer les tables de la base de données et la configuration. |
| `displayAdminProductsExtra` (ou similaire) | Potentiellement sur les pages produits dans le BO. | Si le module avait des paramètres de rappel spécifiques aux produits, mais non indiqué par le dossier. |
| `displayBackOfficeHeader` | Dans la section `<head>` de chaque page back-office. | Pour inclure des JS/CSS spécifiques à l'administration ou le contexte pour la configuration du module. |
| `moduleRoutes` | Lors de l'initialisation de la réécriture d'URL. | Pour définir des URL conviviales personnalisées pour les contrôleurs frontaux (par exemple, URL de la tâche cron, URL de désabonnement). |

La logique principale du module pour l'envoi des rappels est déclenchée par le contrôleur frontal `CronJob.php`, qui est appelé via une tâche cron côté serveur, et non directement par un hook PrestaShop.

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et une assistance supplémentaire concernant votre module « Rappel de Bon d'Achat », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à fournir un support complet et à assurer le bon fonctionnement de votre module.
