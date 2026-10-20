---
title: "Mise à jour des taux de change NBP - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop de mise à jour des taux de change NBP par MyPresta.eu."
sidebar:
  label: "Mise à jour des taux de change NBP - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module NBP currency rates update sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/nbp-currency-rates-update.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/nbp-currency-rates-update/)
>
> ---


# Mise à jour des taux de change NBP

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard comme cURL, JSON et OpenSSL sont généralement requises et sont standard sur la plupart des environnements d'hébergement web modernes. Votre hébergement doit également prendre en charge la configuration des tâches cron.

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Mise à jour des taux de change NBP ». L'écran de configuration principal s'affichera.

#### **URL de la tâche Cron**

-   **Ce que fait ce paramètre :** Il affiche une URL unique que vous utiliserez pour configurer une tâche automatisée (une « tâche cron ») sur votre serveur web. Lorsque cette URL est accédée, le module se connectera aux serveurs de la NBP, récupérera les derniers taux de change et les mettra à jour dans votre boutique PrestaShop.
-   **Effet de la modification de ce paramètre :** Vous ne pouvez pas modifier cette URL directement. Elle est générée par le module.
-   **Valeur recommandée :** Copiez cette URL exactement telle qu'elle apparaît.
-   **Scénario / exemple pour le marchand :** Vous prendrez cette URL et la collerez dans la section « Tâches Cron » de votre panneau de contrôle d'hébergement (par exemple, cPanel, Plesk, ou une configuration cron de serveur personnalisée). Cela indique à votre serveur de visiter cette URL à des intervalles spécifiés (par exemple, tous les jours à 3h du matin), déclenchant automatiquement le processus de mise à jour des devises.

#### **Fréquence de la tâche Cron**

-   **Ce que fait ce paramètre :** Ce n'est pas un paramètre que vous modifiez *dans* PrestaShop, mais plutôt une recommandation sur la fréquence à laquelle vous devriez configurer la tâche cron de votre serveur pour appeler l'URL.
-   **Effet de la modification de ce paramètre :** Ce texte vous conseille simplement. La fréquence réelle est contrôlée par la configuration de la tâche cron de votre serveur.
-   **Valeur recommandée :** « Une fois par jour » est généralement suffisant pour la plupart des boutiques, car les taux NBP sont généralement mis à jour quotidiennement.
-   **Scénario / exemple pour le marchand :** Si vous configurez la tâche cron de votre serveur pour qu'elle s'exécute quotidiennement, les taux de change de votre boutique seront actualisés une fois toutes les 24 heures, garantissant qu'ils sont toujours à jour avec les données NBP. L'exécuter plus fréquemment (par exemple, toutes les heures) est généralement inutile et pourrait surcharger votre serveur ou l'API NBP.

#### **Note importante sur les tâches Cron**

-   **Ce que fait ce paramètre :** Cette section fournit des instructions cruciales sur la façon de configurer la tâche cron sur votre serveur. Elle explique que vous devez accéder à votre panneau de contrôle d'hébergement (comme cPanel ou Plesk) et ajouter une nouvelle tâche cron.
-   **Effet de la modification de ce paramètre :** Il s'agit d'un texte informatif. Vous devez suivre ces instructions en dehors de PrestaShop.
-   **Valeur recommandée :** Lisez attentivement ceci et suivez les étapes fournies par votre hébergeur pour la configuration des tâches cron.
-   **Scénario / exemple pour le marchand :** Votre hébergeur aura une section, généralement appelée « Tâches Cron » ou « Tâches planifiées », où vous pourrez ajouter une nouvelle commande. Vous choisirez généralement une fréquence (par exemple, « Une fois par jour »), puis collerez l'« URL de la tâche Cron » dans le champ de commande, souvent précédée de `wget -q -O /dev/null`. Si vous n'êtes pas sûr, contactez le support de votre hébergeur.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et Impact |
| --- | --- | --- | --- |
| Configuration du module | URL de la tâche Cron | (URL unique) | L'URL pour déclencher les mises à jour automatiques des devises via une tâche cron du serveur. Copiez ceci pour la configuration de votre serveur. |
| Configuration du module | Fréquence de la tâche Cron | Une fois par jour | Recommandation sur la fréquence d'exécution de la tâche cron sur votre serveur pour maintenir les taux à jour. |
| Configuration du module | Instructions pour la configuration de la tâche Cron | N/A | Guide sur la façon de configurer la tâche cron sur votre serveur d'hébergement web. |

## 3. Dépannage pour le marchand et questions fréquemment posées (FAQ)

**Q : Mes taux de change ne se mettent pas à jour, même après avoir configuré la tâche cron. Que dois-je faire ?**
R :

1.  **Vérifiez l'URL de la tâche Cron :** Assurez-vous d'avoir copié l'URL exactement depuis la page de configuration du module et de l'avoir collée correctement dans les paramètres de la tâche cron de votre panneau de contrôle d'hébergement.
2.  **Vérifiez l'exécution de la tâche Cron :** Vérifiez les journaux des tâches cron de votre hébergeur (si disponibles) pour voir si la tâche cron s'exécute réellement à l'heure prévue. Parfois, la commande peut être incorrecte, ou le chemin vers `wget` peut nécessiter un ajustement.
3.  **Testez manuellement :** Essayez de visiter l'« URL de la tâche Cron » directement dans votre navigateur web. Cela devrait déclencher une mise à jour immédiate. Si les taux se mettent à jour après une visite manuelle, le problème vient de la configuration de la tâche cron de votre serveur, et non du module lui-même.
4.  **Vérifiez les devises de PrestaShop :** Assurez-vous que les devises que vous souhaitez mettre à jour sont activées dans PrestaShop (**International > Devises**) et qu'elles ont un code ISO valide que la NBP peut reconnaître (par exemple, USD, EUR, GBP).
5.  **Videz le cache :** Parfois, le cache de PrestaShop peut vous empêcher de voir les changements immédiats. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ».

**Q : Ce module met-il à jour toutes les devises de ma boutique ?**
R : Il met à jour les devises pour lesquelles la NBP fournit des taux de change, par rapport au PLN. Le module est suffisamment intelligent pour convertir ces taux dans la devise par défaut de votre boutique. Par exemple, si votre devise par défaut est l'EUR, et que la NBP fournit USD/PLN et EUR/PLN, le module peut calculer USD/EUR. Si la NBP ne fournit pas de taux pour une devise spécifique, le taux de cette devise ne sera pas mis à jour par ce module.

**Q : Puis-je définir la fréquence de mise à jour à plus d'une fois par jour ?**
R : Bien que vous puissiez configurer la tâche cron de votre serveur pour qu'elle s'exécute plus fréquemment (par exemple, toutes les heures), les taux de change de la NBP sont généralement mis à jour une fois par jour. Exécuter la tâche cron plus souvent que quotidiennement est généralement inutile et ne fournira pas de données plus récentes, mais cela ne nuira à rien non plus.

**Q : Je reçois un message d'erreur lorsque j'essaie de configurer le module ou lorsque la tâche cron s'exécute.**
R :

1.  **Vérifiez la version de PHP :** Assurez-vous que votre version de PHP se situe dans la plage prise en charge (PHP 5.6 - 8.5).
2.  **Connectivité du serveur :** Le module doit se connecter au site web de la NBP pour récupérer les taux. Assurez-vous que votre serveur dispose d'un accès Internet sortant et n'est pas bloqué par un pare-feu pour accéder aux URL externes.
3.  **Mode débogage de PrestaShop :** Activez le mode débogage de PrestaShop (**Paramètres avancés > Performances > Mode débogage**) pour voir des messages d'erreur plus détaillés, ce qui peut aider à identifier le problème. N'oubliez pas de le désactiver après le dépannage.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Vue d'ensemble de l'architecture

Le module `Mise à jour des taux de change NBP` est un module PrestaShop léger principalement conçu pour effectuer une tâche unique et critique : récupérer et mettre à jour les taux de change de la Banque Nationale de Pologne (NBP) via une tâche cron planifiée. Il suit une structure de module PrestaShop standard, utilisant `ModuleFrontController` pour son point d'accès cron et la classe de module principale pour la configuration et l'installation. La logique principale réside dans le fichier `cronjob.php`, qui agit à la fois comme la classe de module principale et le point d'entrée pour l'exécution du cron.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    -   `nbprates/controllers/front/cronjob.php`
        -   **Nom de la classe et classe parente** : `NbpratesCronjobModuleFrontController` étend `ModuleFrontController`
        -   **Responsabilité** : Ce contrôleur sert de point d'accès public pour la tâche cron. Lorsqu'il est accédé via l'URL unique générée par le module, il déclenche la logique de mise à jour des devises. Il ne rend aucune sortie visuelle mais exécute le processus de récupération et de mise à jour des taux. Il est conçu pour être appelé par `wget` ou `curl` à partir du planificateur cron d'un serveur.
    -   `nbprates/controllers/front/index.php`
        -   **Nom de la classe et classe parente** : `NbpratesIndexModuleFrontController` étend `ModuleFrontController`
        -   **Responsabilité** : Il s'agit d'un contrôleur de remplacement, souvent inclus dans les modules pour empêcher l'affichage du contenu du répertoire si `index.php` n'est pas présent dans le répertoire `controllers/front`. Il ne fait généralement rien de plus que rediriger vers la page d'accueil ou afficher une erreur « 404 Not Found ». Il ne contient aucune logique métier spécifique à ce module.
-   **Contrôleurs d'administration Back-Office** :

    -   Aucun. Toute la configuration est gérée directement dans la méthode `getContent()` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)

-   Aucun. La logique du module est principalement contenue dans le fichier du module principal (`nbprates/cronjob.php`).

### 4.4 Actifs JavaScript (`views/js/`)

-   Aucun. Le module n'utilise pas de JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

-   Aucun. Le module n'utilise pas de CSS personnalisé.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles d'administration (`views/templates/admin/`)** :
    -   `nbprates/views/admin.tpl`
        -   **Objectif** : Ce modèle est rendu par la méthode `getContent()` de la classe de module principale (`NbpratesCronjob`) pour afficher le formulaire de configuration du module dans le Back Office de PrestaShop.
        -   **Contenu** : Il affiche généralement l'« URL de la tâche Cron » et les instructions pour configurer la tâche cron. Il s'agit d'un affichage statique d'informations plutôt que d'un formulaire interactif avec des champs de saisie.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module ne crée aucune table SQL personnalisée.
    -   Il stocke sa configuration (spécifiquement le jeton cron généré) dans la table `ps_configuration`. La clé du jeton cron serait généralement `NBP_CRON_TOKEN`.
    -   Il met à jour les taux de change existants dans la table `ps_currency` (spécifiquement la colonne `conversion_rate`).
-   **Table des hooks enregistrés** :
    Le module ne s'enregistre explicitement à aucun hook d'affichage PrestaShop standard (comme `displayHeader`, `displayFooter`, etc.) pour le rendu front-office. Son « hook » principal est le point d'accès `ModuleFrontController` qui est appelé en externe par la tâche cron du serveur.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `install()` | Lors de l'installation du module | Crée le jeton cron unique et le stocke dans `ps_configuration`. |
| `uninstall()` | Lors de la désinstallation du module | Supprime le jeton cron de `ps_configuration`. |
| `actionFrontControllerSetMedia` | Non explicitement enregistré, mais `ModuleFrontController` gère implicitement le chargement des actifs s'il y en avait. | N/A (aucun actif n'est chargé par ce module). |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Mise à jour des taux de change NBP », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité du module et son intégration avec votre boutique PrestaShop.
