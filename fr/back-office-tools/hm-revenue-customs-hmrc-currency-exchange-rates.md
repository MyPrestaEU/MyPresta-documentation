---
title: "HM Revenue & Customs (HMRC) - taux de change - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop HM Revenue & Customs (HMRC) - taux de change par MyPresta.eu."
sidebar:
  label: "HM Revenue & Customs (HMRC) - taux de change - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module HM Revenue & Customs (HMRC) - currency exchange rates sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/hm-revenue-customs-hmrc-currency-exchange-rates.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/hm-revenue-customs-hmrc-currency-exchange-rates/)
>
> ---


# HM Revenue & Customs (HMRC) - taux de change

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour récupérer des données externes, ce qui est standard sur la plupart des environnements d'hébergement.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à l'écran de configuration principal du module Taux de change HMRC. C'est ici que vous configurerez la manière dont le module récupère et applique les taux de change officiels.

La page de configuration vous présentera les informations et paramètres clés suivants :

#### **URL de la tâche Cron**

- **Ce que fait ce paramètre :** Il s'agit d'une adresse web spéciale (URL) qui, lorsqu'elle est visitée, déclenche le module pour récupérer les derniers taux de change HMRC et les mettre à jour dans votre boutique PrestaShop. Il est conçu pour être exécuté automatiquement par une « tâche cron » sur votre serveur.
- **Effet de la modification de ce paramètre :** Vous ne pouvez pas modifier cette URL directement. Elle est générée par le module.
- **Valeur recommandée :** Copiez cette URL exactement telle qu'elle apparaît.
- **Scénario/exemple pour le marchand :** Vous aurez besoin de cette URL pour configurer une tâche automatisée (tâche cron) sur le serveur de votre hébergement web. Cette tâche visitera l'URL à un moment planifié (par exemple, une fois par jour ou une fois par mois) pour garantir que vos taux sont toujours à jour sans que vous ayez à cliquer manuellement sur quoi que ce soit.

#### **Commande de la tâche Cron (pour les serveurs Linux/Unix)**

- **Ce que fait ce paramètre :** Il s'agit d'une instruction de ligne de commande qui produit le même résultat que la visite de l'URL de la tâche Cron, mais elle est spécifiquement formatée pour une utilisation directe dans le planificateur de tâches cron d'un serveur (souvent trouvé dans votre panneau de contrôle d'hébergement comme cPanel ou Plesk). Elle utilise `wget` ou `curl` pour demander silencieusement l'URL.
- **Effet de la modification de ce paramètre :** Vous ne pouvez pas modifier cette commande directement. Elle est générée par le module.
- **Valeur recommandée :** Copiez cette commande exactement telle qu'elle apparaît.
- **Scénario/exemple pour le marchand :** Si votre hébergeur utilise des serveurs Linux/Unix (ce qui est le cas de la plupart), vous utiliserez cette commande pour configurer votre tâche cron automatisée. C'est généralement plus fiable que de dépendre de services cron basés sur le web.

#### **Statut de la dernière mise à jour**

- **Ce que fait ce paramètre :** Cette section affiche des informations sur la dernière fois que le module a réussi à récupérer et à mettre à jour les taux HMRC. Elle affichera la date et l'heure de la dernière mise à jour.
- **Effet de la modification de ce paramètre :** Il s'agit uniquement d'un affichage informatif ; vous ne pouvez pas le modifier.
- **Valeur recommandée :** Surveillez cela pour vous assurer que votre tâche cron s'exécute correctement et que les taux sont mis à jour régulièrement.
- **Scénario/exemple pour le marchand :** Si vous configurez votre tâche cron pour qu'elle s'exécute quotidiennement, vous devriez voir le « Statut de la dernière mise à jour » changer quotidiennement, confirmant que le module fonctionne comme prévu. S'il ne se met pas à jour, cela indique un problème avec la configuration de votre tâche cron.

#### **Bouton « Mettre à jour maintenant »**

- **Ce que fait ce paramètre :** Ce bouton vous permet de déclencher manuellement le processus de mise à jour des taux immédiatement, directement depuis la page de configuration du module.
- **Effet de la modification de ce paramètre :** Cliquer sur ce bouton récupérera instantanément les derniers taux HMRC et les appliquera aux devises de votre boutique.
- **Valeur recommandée :** Utilisez ce bouton pour les tests initiaux après l'installation, ou si vous avez besoin de forcer une mise à jour immédiate en dehors de votre tâche cron planifiée.
- **Scénario/exemple pour le marchand :** Après avoir installé le module, cliquez sur « Mettre à jour maintenant » pour voir s'il récupère correctement les taux et pour remplir votre boutique avec les derniers taux HMRC avant l'exécution de votre première tâche cron planifiée.

#### **Note importante sur les tâches Cron :**

La fonctionnalité principale de ce module repose sur la mise en place d'une **tâche cron** sur votre serveur web. Une tâche cron est un planificateur de tâches basé sur le temps dans les systèmes d'exploitation de type Unix. Elle permet aux utilisateurs de planifier l'exécution de tâches (commandes ou scripts) périodiquement à des heures, des dates ou des intervalles fixes.

**Comment configurer une tâche cron (étapes générales) :**

1.  **Accédez à votre panneau de contrôle d'hébergement :** Connectez-vous à votre cPanel, Plesk ou autre panneau de contrôle d'hébergement.
2.  **Recherchez « Tâches Cron » ou « Tâches planifiées » :** Recherchez une section généralement nommée « Tâches Cron », « Tâches planifiées » ou « Automatisation ».
3.  **Ajoutez une nouvelle tâche Cron :**
    *   **Fréquence :** Définissez la fréquence. Pour les taux HMRC, mensuel est généralement suffisant (par exemple, « Une fois par mois » le 1er jour du mois). Certains marchands préfèrent quotidiennement pour plus de sécurité, mais les taux HMRC sont mensuels.
    *   **Commande :** Collez la « Commande de la tâche Cron » fournie par le module dans le champ de commande.
    *   **Email :** Vous pouvez généralement spécifier une adresse e-mail pour recevoir la sortie de la tâche cron. C'est utile pour le dépannage si la tâche échoue.
4.  **Enregistrer :** Enregistrez la tâche cron.

Si vous ne savez pas comment configurer une tâche cron, veuillez contacter l'équipe de support de votre hébergeur et leur fournir la « Commande de la tâche Cron » de la page de configuration du module, en leur demandant de la configurer pour qu'elle s'exécute mensuellement (ou quotidiennement, selon votre préférence).

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Config du module | URL de la tâche Cron | N/A (Copier et utiliser) | URL pour déclencher la mise à jour des taux ; pour les services cron basés sur le web. |
| Config du module | Commande de la tâche Cron | N/A (Copier et utiliser) | Instruction de ligne de commande pour les tâches cron basées sur le serveur (par exemple, cPanel). |
| Config du module | Statut de la dernière mise à jour | N/A (Informationnel) | Affiche la date/heure de la dernière mise à jour réussie des taux. |
| Config du module | Bouton « Mettre à jour maintenant » | Cliquer pour une mise à jour manuelle | Récupère et applique immédiatement les derniers taux HMRC. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes taux de change ne se mettent pas à jour. Que dois-je faire ?**
R : La raison la plus courante est une tâche cron mal configurée.
1.  **Vérifiez la configuration de votre tâche cron :** Connectez-vous à votre panneau de contrôle d'hébergement (cPanel, Plesk, etc.) et vérifiez que la tâche cron est correctement configurée à l'aide de la « Commande de la tâche Cron » fournie par le module. Assurez-vous que la fréquence est définie comme souhaité (par exemple, mensuelle ou quotidienne).
2.  **Testez manuellement :** Allez sur la page de configuration du module dans votre back office PrestaShop et cliquez sur le bouton « Mettre à jour maintenant ». Si cela fonctionne, le problème vient certainement de la configuration de votre tâche cron. Si cela ne fonctionne pas, il pourrait y avoir un problème côté serveur empêchant le module de récupérer les données (par exemple, pare-feu, problèmes cURL).
3.  **Contactez votre hébergeur :** Si vous n'êtes pas sûr de la configuration des tâches cron, fournissez à votre support d'hébergement la « Commande de la tâche Cron » et demandez-leur de la configurer pour vous.

**Q : Ce module affecte-t-il les prix que les clients voient sur mon site web ?**
R : Oui, indirectement. Le module met à jour les taux de change sous-jacents dans PrestaShop. Si votre boutique permet aux clients de basculer entre les devises, les prix affichés dans ces devises étrangères refléteront les taux mis à jour. Cependant, l'objectif principal du module est la comptabilité *interne* et la conformité fiscale, pas nécessairement les stratégies de prix dynamiques en front-end.

**Q : Que se passe-t-il si l'HMRC modifie sa méthode de publication des taux de change ?**
R : MyPresta.eu surveille régulièrement les changements apportés aux services externes comme l'HMRC. Si l'HMRC modifie sa source de données ou son format, nous publierons une mise à jour du module pour assurer une compatibilité continue. Gardez toujours vos modules à jour vers leurs dernières versions.

**Q : Puis-je utiliser ce module si ma devise de base n'est pas la GBP ?**
R : Bien que le module récupère les taux HMRC, son principal avantage est la conformité à la TVA britannique, qui suppose généralement la GBP comme devise de déclaration. Si votre devise de base n'est pas la GBP, le module mettra toujours à jour les taux de change pour les autres devises par rapport à votre devise de base, mais vous devrez comprendre comment cela interagit avec vos obligations de déclaration fiscale spécifiques. Pour la TVA britannique, il est généralement recommandé d'avoir la GBP comme devise par défaut.

**Q : Je vois un message d'erreur lorsque j'essaie de mettre à jour les taux manuellement.**
R : Cela pourrait indiquer plusieurs choses :
1.  **Connectivité du serveur :** Votre serveur pourrait être incapable de se connecter au site web de l'HMRC pour récupérer les données. Cela pourrait être dû à un pare-feu, un problème réseau ou une indisponibilité temporaire du serveur HMRC.
2.  **Extensions PHP :** Assurez-vous que les extensions PHP standard comme `cURL` et `JSON` sont activées sur votre serveur.
3.  **Permissions du module :** Vérifiez que les fichiers du module ont les bonnes permissions de lecture/écriture.
Si le problème persiste, contactez le support MyPresta.eu avec le message d'erreur exact.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique pour les développeurs et les webmasters responsables de la maintenance ou de l'extension de la boutique PrestaShop.

### 4.1 Vue d'ensemble de l'architecture

Le module `hmrcrates` est un module PrestaShop simple conçu pour récupérer et mettre à jour les taux de change depuis le site web de l'HMRC. Il exploite l'architecture des modules de PrestaShop, utilisant principalement la classe `Module` pour l'installation/désinstallation et `ModuleFrontController` pour gérer les requêtes de tâches cron. La logique principale réside dans le fichier principal du module, `cronjob.php`, qui agit également comme point d'entrée principal pour la configuration et l'exécution cron. Il n'utilise pas `ObjectModel` car il manipule directement les objets `Currency` existants.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :

  - `controllers/front/cronjob.php`
    - **Nom de la classe et classe parente** : `HmrcratesCronjobModuleFrontController` étendant `ModuleFrontController`.
    - **Responsabilité** : Ce contrôleur est le point d'accès public pour la tâche cron. Lorsqu'il est accédé via son URL (par exemple, `votreboutique.com/module/hmrcrates/cronjob`), il déclenche la méthode `processUpdateRates()` dans le module `hmrcrates` principal. Il est conçu pour être appelé par des services cron externes ou des tâches cron côté serveur. Il affiche un simple message de succès ou d'erreur.
  - `controllers/front/index.php`
    - **Nom de la classe et classe parente** : `HmrcratesIndexModuleFrontController` étendant `ModuleFrontController`.
    - **Responsabilité** : Il s'agit d'un contrôleur de remplacement, généralement utilisé pour fournir un point d'entrée par défaut pour un module si aucune action spécifique n'est demandée. Dans le contexte de ce module, il n'a probablement aucune fonction directe autre que de fournir une route par défaut si `cronjob.php` n'est pas explicitement appelé. Il peut rediriger ou simplement afficher une page blanche.
- **Contrôleurs d'administration Back-Office** :

  - Ce module n'utilise pas de fichiers `AdminController` dédiés. Toute la configuration du back-office est gérée directement dans la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée dans le répertoire `classes/`. La logique principale pour la récupération et la mise à jour des taux est encapsulée dans le fichier principal du module, `hmrcrates/cronjob.php`. Il interagit directement avec la classe `Currency` intégrée de PrestaShop pour mettre à jour les taux de change.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé. La configuration du back-office repose sur le style par défaut du back-office de PrestaShop.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **Modèles d'administration (`views/templates/admin/`)** :
  - `views/templates/admin/admin.tpl`
    - **Objectif** : Ce modèle est rendu par la méthode `getContent()` de la classe principale du module (`hmrcrates/cronjob.php`) pour afficher le formulaire de configuration du module dans le back office de PrestaShop.
    - **Contenu** : Il inclut généralement la structure HTML pour afficher l'URL de la tâche Cron, la commande de la tâche Cron, le statut de la dernière mise à jour et le bouton « Mettre à jour maintenant ». Il utilise les assistants de formulaire et le style standard de PrestaShop.

### 4.7 Schéma de la base de données et carte des Hooks

- **Tables de la base de données** :

  - Ce module ne crée aucune table SQL personnalisée.
  - Il stocke ses paramètres de configuration (par exemple, `HMRCRATES_LAST_UPDATE`) dans la table `ps_configuration` standard de PrestaShop.
  - Il met à jour la colonne `exchange_rate` dans la table `ps_currency` pour les devises pertinentes.
- **Table des Hooks enregistrés** :
Ce module n'enregistre explicitement aucun hook d'affichage front-office (comme `displayHeader`, `displayRightColumn`, `displayFooter`) car sa fonctionnalité est purement orientée backend. Son « hook » principal est le hook `action` déclenché par le `ModuleFrontController` pour la tâche cron.

| Nom du Hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionModuleInstall` | Lors de l'installation du module | Crée les entrées de configuration, configure les données initiales. |
| `actionModuleUninstall` | Lors de la désinstallation du module | Nettoie les entrées de configuration. |
| (Implicite) `actionFrontControllerSetMedia` | Lorsqu'un contrôleur frontal est chargé | Non explicitement utilisé par ce module, mais standard pour les modules afin de charger des actifs. |
| (Implicite) `actionDispatcher` | Lorsqu'un contrôleur frontal est dispatché | Le `ModuleFrontController` `HmrcratesCronjobModuleFrontController` est dispatché lorsque l'URL cron est accédée, déclenchant la logique de mise à jour des taux. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour télécharger les dernières versions du module « HM Revenue & Customs (HMRC) - taux de change », veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité ou la configuration du module.
