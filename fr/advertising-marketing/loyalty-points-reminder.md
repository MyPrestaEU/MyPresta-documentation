---
title: "Rappel de points de fidélité - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Rappel de points de fidélité par MyPresta.eu."
sidebar:
  label: "Rappel de points de fidélité - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Loyalty points reminder sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points-reminder.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/loyalty-points-reminder/)
>
> ---


# Rappel de points de fidélité

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Le module s'appuie sur les fonctions de messagerie natives et les capacités de tâche cron de PrestaShop.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Rappel de points de fidélité)

Ceci est l'écran de configuration principal et unique du module « Rappel de points de fidélité ». Ici, vous définirez comment et quand les e-mails de rappel sont envoyés.

#### **Activer / Désactiver le module**

- **Ce que fait ce paramètre :** C'est l'interrupteur principal du module.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Le module vérifiera activement les points de fidélité expirant et enverra des e-mails de rappel selon vos autres paramètres.
  - *Lorsqu'il est désactivé :* Le module n'enverra aucun e-mail de rappel, quels que soient les autres paramètres.
- **Valeur recommandée :** OUI (une fois que vous avez configuré les autres paramètres).
- **Scénario / exemple de marchand :** Vous venez d'installer le module et souhaitez commencer à rappeler les clients. Vous l'activeriez après avoir configuré les jours avant l'expiration.

#### **Jours avant l'expiration pour envoyer le rappel**

- **Ce que fait ce paramètre :** Il détermine combien de jours *avant* l'expiration des points de fidélité d'un client l'e-mail de rappel sera envoyé.
- **Effet de la modification de ce paramètre :**
  - *Si défini à 7 :* Les clients recevront un e-mail 7 jours avant l'expiration de leurs points.
  - *Si défini à 30 :* Les clients recevront un e-mail 30 jours avant l'expiration de leurs points.
- **Valeur recommandée :** 7-14 jours. Cela donne aux clients suffisamment de temps pour réagir sans être trop en avance pour qu'ils oublient.
- **Scénario / exemple de marchand :** Vous voulez donner aux clients une semaine pour utiliser leurs points. Vous le définiriez à « 7 ». Si vous voulez leur donner plus de marge de manœuvre, peut-être « 14 ».

#### **URL de la tâche Cron**

- **Ce que fait ce paramètre :** Il affiche une URL unique que vous devez configurer comme tâche cron sur votre serveur. Une tâche cron est une tâche planifiée qui indique à votre serveur d'exécuter un script spécifique à intervalles réguliers (par exemple, une fois par jour). C'est ainsi que le module vérifie automatiquement les points expirant et envoie des e-mails sans que vous ayez à faire quoi que ce soit manuellement.
- **Effet de la modification de ce paramètre :** Vous ne pouvez pas modifier ce paramètre directement. C'est une URL générée.
  - *Si la tâche cron est configurée correctement :* Le module s'exécutera automatiquement, envoyant des e-mails comme configuré.
  - *Si la tâche cron N'EST PAS configurée :* Le module n'enverra jamais d'e-mails de rappel, même s'il est activé.
- **Valeur recommandée :** Copiez cette URL et configurez-la comme tâche cron quotidienne sur votre serveur d'hébergement.
- **Scénario / exemple de marchand :** Après avoir configuré le paramètre « Jours avant l'expiration », vous copieriez cette URL et la colleriez dans le planificateur de tâches cron de votre panneau de contrôle d'hébergement (par exemple, cPanel, Plesk, ou accès direct au serveur). Vous la configureriez généralement pour qu'elle s'exécute une fois toutes les 24 heures.

#### **Adresse e-mail de test**

- **Ce que fait ce paramètre :** Vous permet d'envoyer un e-mail de rappel de test à une adresse spécifique pour vous assurer que le module fonctionne correctement et que le contenu de l'e-mail est satisfaisant.
- **Effet de la modification de ce paramètre :**
  - *Saisir une adresse e-mail et cliquer sur « Envoyer un e-mail de test » :* Un e-mail sera envoyé à l'adresse spécifiée, simulant un rappel de points de fidélité. Cet e-mail contiendra des données de substitution car il s'agit d'un test.
- **Valeur recommandée :** Utilisez votre propre adresse e-mail ou celle d'un collègue pour les tests.
- **Scénario / exemple de marchand :** Avant de passer en production, vous voulez voir à quoi ressemble l'e-mail de rappel. Vous saisiriez votre adresse e-mail ici et cliqueriez sur le bouton de test.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | **Activer / Désactiver le module** | OUI | Interrupteur principal pour activer ou désactiver les e-mails de rappel. |
| Configuration du module | **Jours avant l'expiration pour envoyer le rappel** | 7-14 jours | Définit combien de jours avant l'expiration des points l'e-mail est envoyé. |
| Configuration du module | **URL de la tâche Cron** | Copier et configurer quotidiennement | Essentiel pour l'envoi automatisé d'e-mails ; doit être configuré sur votre serveur. |
| Configuration du module | **Adresse e-mail de test** | Votre e-mail pour les tests | Envoie un e-mail de rappel échantillon pour vérifier le contenu et la livraison. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes clients ne reçoivent pas les e-mails de rappel. Que dois-je vérifier ?**
R :

1. **Le module est-il activé ?** Allez dans la configuration du module et assurez-vous que « Activer / Désactiver le module » est réglé sur OUI.
2. **La tâche cron est-elle correctement configurée ?** C'est le problème le plus courant. Le module s'appuie sur une tâche cron pour s'exécuter automatiquement. Copiez l'« URL de la tâche Cron » depuis la configuration du module et assurez-vous qu'elle est correctement configurée sur votre serveur d'hébergement pour s'exécuter quotidiennement.
3. **Vérifiez les paramètres e-mail de votre PrestaShop :** Allez dans **Paramètres avancés > E-mail** dans votre Back Office. Envoyez un e-mail de test à partir de là pour vous assurer que le système d'e-mail de votre boutique fonctionne.
4. **Vérifiez les dossiers de spam :** Demandez aux clients de vérifier leurs dossiers de spam ou de courrier indésirable.
5. **Videz le cache Smarty :** Parfois, les modifications de modèle ou les mises à jour de module nécessitent de vider le cache. Allez dans **Paramètres avancés > Performances**, faites défiler jusqu'à « Vider le cache » et cliquez sur « Vider le cache ».

**Q : L'e-mail de test fonctionne, mais les clients ne reçoivent toujours pas de rappels.**
R : Cela suggère fortement que la tâche cron est le problème. L'e-mail de test utilise l'envoi immédiat de courrier de PrestaShop, tandis que les rappels réels dépendent de l'exécution du processus en arrière-plan du module par la tâche cron. Vérifiez à nouveau la configuration de votre tâche cron auprès de votre hébergeur.

**Q : Puis-je personnaliser le contenu de l'e-mail de rappel ?**
R : Le module utilise les modèles d'e-mail standard de PrestaShop. Vous trouverez généralement les fichiers de modèle d'e-mail dans le répertoire `mails/` de votre thème (par exemple, `themes/votretheme/mails/fr/loyalty_points_reminder.html` et `loyalty_points_reminder.txt`). Si ceux-ci n'existent pas, le module utilisera les modèles d'e-mail par défaut de PrestaShop. Vous pouvez les surcharger dans votre thème pour personnaliser le texte et l'apparence.

**Q : Que se passe-t-il si un client n'a pas de points de fidélité ?**
R : Le module est conçu pour n'envoyer des e-mails qu'aux clients qui ont réellement des points de fidélité dont la date d'expiration approche. Si un client n'a pas de points, ou si ses points n'expirent pas bientôt, il ne recevra pas d'e-mail.

**Q : Ce module fonctionne-t-il avec des modules de points de fidélité personnalisés ?**
R : Ce module est conçu pour fonctionner avec le système de points de fidélité natif de PrestaShop. Si vous utilisez un module de fidélité tiers, il pourrait ne pas s'intégrer directement à moins que ce module n'étende ou n'utilise spécifiquement les fonctionnalités de fidélité de base de PrestaShop de manière compatible.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module « Rappel de points de fidélité ».

### 4.1 Aperçu de l'architecture

Le module « Rappel de points de fidélité » (`lpreminder`) est un module PrestaShop standard suivant un modèle de type MVC. Sa fonctionnalité principale repose sur une tâche planifiée (tâche cron) qui déclenche un contrôleur frontal pour traiter les points de fidélité expirant et envoyer des e-mails. Il s'appuie sur les classes natives `LoyaltyModule` et `Mail` de PrestaShop.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs sont conçus pour être accessibles via une URL spécifique, principalement pour l'exécution des tâches cron.

- **`controllers/front/cronjob.php`**
  - **Nom de la classe et classe parente :** `LpreminderCronjobModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** C'est le point d'accès critique pour la tâche cron. Lorsqu'il est accédé, il exécute la logique du module pour identifier les clients avec des points de fidélité expirant et envoie des e-mails de rappel. Il devrait idéalement être protégé (par exemple, par un jeton ou une restriction IP) s'il n'est pas déjà implémenté par le module pour empêcher tout accès non autorisé. Il ne rend aucune sortie visuelle mais effectue un traitement en arrière-plan.
- **`controllers/front/index.php`**
  - **Nom de la classe et classe parente :** `LpreminderIndexModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur pourrait servir de point d'entrée par défaut ou de placeholder. Dans de nombreux modules, si une action spécifique n'est pas définie, `index.php` pourrait la gérer. Compte tenu de la fonction principale du module, `cronjob.php` est le contrôleur frontal opérationnel principal. Ce `index.php` pourrait être un fallback ou utilisé pour de futures extensions.

#### Contrôleurs d'administration Back-Office

Le module n'utilise aucun contrôleur d'administration personnalisé. Toute la configuration est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne définit aucune classe personnalisée ou `ObjectModel` dans le répertoire `classes/`. Il interagit directement avec les classes principales de PrestaShop, notamment :

- `LoyaltyModule` : Pour récupérer les points de fidélité des clients et leurs dates d'expiration.
- `Customer` : Pour récupérer les détails du client pour l'envoi d'e-mails.
- `Mail` : Pour envoyer les e-mails de rappel.
- `Configuration` : Pour stocker et récupérer les paramètres du module.

### 4.4 Actifs JavaScript (`views/js/`)

Le module n'inclut aucun fichier JavaScript personnalisé. Toutes les fonctionnalités sont gérées côté serveur.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module n'inclut aucun fichier CSS personnalisé. La page de configuration utilise le style par défaut du Back Office de PrestaShop.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module n'inclut aucun fichier de modèle Smarty personnalisé dans son répertoire `views/templates/`.

- **Modèles d'e-mail :** Le module s'appuie sur le système de modèles d'e-mail par défaut de PrestaShop. Le contenu de l'e-mail de rappel est généré à l'aide d'un modèle nommé `loyalty_points_reminder`. Les développeurs peuvent personnaliser cet e-mail en créant ou en surchargeant les fichiers suivants dans le répertoire `mails/` de leur thème actif :
  - `themes/votretheme/mails/fr/loyalty_points_reminder.html` (pour le contenu de l'e-mail HTML)
  - `themes/votretheme/mails/fr/loyalty_points_reminder.txt` (pour le contenu de l'e-mail en texte brut)
  - Remplacez `fr` par le code de langue approprié.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** : Le module ne crée aucune table de base de données personnalisée. Il stocke ses paramètres de configuration (par exemple, `PS_LPREMINDER_DAYS_BEFORE_EXPIRY`, `PS_LPREMINDER_ENABLED`) dans la table `ps_configuration`. Il interroge les tables PrestaShop existantes comme `ps_loyalty_history` et `ps_customer`.
- **Table des hooks enregistrés** :
Le module utilise principalement le hook `actionFrontControllerSetMedia` pour une éventuelle inclusion future de JS/CSS (bien qu'aucun ne soit présent actuellement) et s'appuie implicitement sur le mécanisme de tâche cron pour sa fonctionnalité principale, qui n'est pas un hook PrestaShop traditionnel mais un déclencheur externe vers un contrôleur frontal.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rend le contenu dans la section `<head>` des pages du front-office. | Non directement utilisé pour la logique principale du module, mais pourrait être utilisé pour JS/CSS si nécessaire. |
| `displayRightColumn` | Rend le contenu dans la colonne de droite des pages du front-office. | Non directement utilisé pour la logique principale du module. |
| `displayLeftColumn` | Rend le contenu dans la colonne de gauche des pages du front-office. | Non directement utilisé pour la logique principale du module. |
| `displayFooter` | Rend le contenu dans le pied de page des pages du front-office. | Non directement utilisé pour la logique principale du module. |
| `displayProductExtraContent` | Rend le contenu sur la page produit. | Non directement utilisé pour la logique principale du module. |
| `actionFrontControllerSetMedia` | Exécuté lorsqu'un contrôleur frontal configure ses médias (JS/CSS). | Permet au module d'enregistrer ses propres actifs JS/CSS si nécessaire. |
| *(Déclencheur de tâche Cron)* | Tâche planifiée côté serveur externe (par exemple, quotidienne). | Déclenche le contrôleur frontal `cronjob.php` pour traiter les points de fidélité expirant et envoyer des e-mails. C'est le déclencheur opérationnel principal du module. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Rappel de points de fidélité », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question concernant la fonctionnalité du module.
