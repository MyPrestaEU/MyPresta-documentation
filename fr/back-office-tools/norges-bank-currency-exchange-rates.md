---
title: "Norges Bank - taux de change - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Norges Bank - taux de change par MyPresta.eu."
sidebar:
  label: "Norges Bank - taux de change - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Norges Bank - currency exchange rates sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/norges-bank-currency-exchange-rates.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/norges-bank-currency-exchange-rates/)
>
> ---


# Norges Bank - taux de change

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour récupérer des données externes. Votre environnement d'hébergement doit également prendre en charge les tâches CRON pour les mises à jour automatisées.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à la page principale des paramètres du module « Norges Bank - taux de change ». C'est ici que vous contrôlez comment et quand vos taux de change sont mis à jour.

#### **Paramètres et Options**

1.  **URL CRON pour les mises à jour automatiques :**

    *   **Ce que fait ce paramètre :** Il s'agit d'une adresse web unique (URL) qui, lorsqu'elle est visitée, déclenche le module pour récupérer les derniers taux de change auprès de la Norges Bank et les mettre à jour dans votre boutique PrestaShop.
    *   **Effet de la modification de ce paramètre :** Vous ne pouvez pas modifier cette URL directement. Elle est générée par le module. Vous avez besoin de cette URL pour configurer une tâche automatisée (une « tâche CRON ») sur votre serveur d'hébergement web.
    *   **Valeur recommandée :** Copiez cette URL exactement telle qu'elle apparaît.
    *   **Scénario / exemple pour le marchand :** Vous fournirez cette URL à votre hébergeur ou l'utiliserez dans votre panneau de contrôle d'hébergement (comme cPanel ou Plesk) pour planifier une tâche qui visite cette URL régulièrement (par exemple, une fois par jour). Cela garantit que vos taux sont toujours à jour sans aucune intervention manuelle de votre part.
2.  **Marge de taux de change (%) :**

    *   **Ce que fait ce paramètre :** Cela vous permet d'ajouter une marge en pourcentage aux taux de change récupérés auprès de la Norges Bank. Par exemple, si le taux officiel est de 1 EUR = 10 NOK, et que vous définissez une marge de 2 %, votre boutique pourrait utiliser 1 EUR = 9,8 NOK (ou 10,2 NOK, selon la direction du calcul, rendant généralement la devise étrangère légèrement plus chère pour le client afin de couvrir les coûts de conversion).
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsque défini à 0 :* Votre boutique utilise les taux de change officiels exacts fournis par la Norges Bank.
        *   *Lorsque défini à une valeur positive (par exemple, 2) :* Le module ajuste les taux de change pour inclure ce pourcentage, vous donnant ainsi une petite marge ou un profit sur les conversions de devises. Cela peut aider à couvrir les frais de transaction ou simplement à augmenter votre rentabilité.
    *   **Valeur recommandée :** Commencez par `0` si vous souhaitez des taux exacts. Si vous avez besoin de couvrir des coûts ou d'ajouter un petit profit, une valeur entre `0,5` et `2` pour cent est courante.
    *   **Scénario / exemple pour le marchand :** Si votre passerelle de paiement facture des frais de 1 % pour les transactions internationales, définir une marge de 1 % ici peut vous aider à absorber ce coût sans impacter le prix de vos produits dans votre devise de base.
3.  **Dernière mise à jour :**

    *   **Ce que fait ce paramètre :** Affiche la date et l'heure de la dernière mise à jour réussie des taux de change dans votre boutique par le module.
    *   **Effet de la modification de ce paramètre :** Il s'agit d'un champ informatif qui ne peut pas être modifié. Il vous aide à vérifier que votre tâche CRON fonctionne correctement et que vos taux sont mis à jour régulièrement.
    *   **Valeur recommandée :** Vérifiez ce champ périodiquement pour vous assurer que les mises à jour se déroulent comme prévu.
    *   **Scénario / exemple pour le marchand :** Après avoir configuré votre tâche CRON, vous pouvez vérifier ce champ le lendemain pour confirmer que le module s'est exécuté avec succès et a mis à jour les taux.

#### **Bouton de mise à jour manuelle**

-   **Ce que fait ce bouton :** Ce bouton vous permet de déclencher manuellement une mise à jour immédiate de tous les taux de change de la Norges Bank.
-   **Effet de cliquer sur ce bouton :** Le module récupérera instantanément les derniers taux et les appliquera à votre boutique. C'est utile pour les tests ou si vous avez besoin d'une mise à jour immédiate en dehors de votre tâche CRON planifiée.
-   **Utilisation recommandée :** Utilisez-le pour les tests initiaux après la configuration, ou s'il y a une fluctuation monétaire significative et soudaine que vous souhaitez refléter immédiatement.

#### **Instructions de configuration de la tâche CRON**

Sous les paramètres, vous trouverez des instructions claires sur la façon de configurer la tâche CRON sur votre serveur. Ceci est crucial pour le fonctionnement « sans maintenance » du module.

-   **Ce que fait cette section :** Fournit la commande exacte ou la méthode que vous devez utiliser avec le planificateur de tâches CRON de votre hébergeur.
-   **Effet de suivre ces instructions :** Une fois configuré, votre serveur visitera automatiquement l'URL CRON à des intervalles spécifiés (par exemple, une fois par jour), garantissant que vos taux de change sont toujours à jour sans intervention manuelle.
-   **Fréquence recommandée :** Les mises à jour quotidiennes sont généralement suffisantes. Pour les devises très volatiles ou les ventes internationales à volume élevé, vous pourriez envisager deux fois par jour.
-   **Scénario / exemple pour le marchand :** Dans cPanel, vous iriez à « Tâches Cron », sélectionneriez un paramètre courant comme « Une fois par jour », et colleriez la commande fournie dans le champ « Commande ».

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et Impact |
| --- | --- | --- | --- |
| Configuration du module | URL CRON pour les mises à jour automatiques | (URL générée) | URL pour déclencher les mises à jour automatiques des taux via une tâche CRON. **Crucial pour l'automatisation.** |
| Configuration du module | Marge de taux de change (%) | 0 | Ajoute une marge en pourcentage aux taux de change pour la rentabilité/récupération des coûts. |
| Configuration du module | Dernière mise à jour | (Date/Heure) | Champ informatif affichant la dernière mise à jour réussie des taux. |
| Configuration du module | Bouton de mise à jour manuelle | N/A | Récupère et applique immédiatement les derniers taux. Utile pour les tests/mises à jour urgentes. |
| Configuration du module | Instructions de configuration de la tâche CRON | N/A | Guide pour configurer les mises à jour automatisées sur votre serveur d'hébergement. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes taux de change ne se mettent pas à jour automatiquement. Que dois-je faire ?**
R : Cela est presque toujours lié à la configuration de la tâche CRON sur votre serveur.
1.  **Vérifier la tâche CRON :** Vérifiez attentivement votre panneau de contrôle d'hébergement (cPanel, Plesk, etc.) pour vous assurer que la tâche CRON est correctement configurée avec l'URL exacte fournie par le module et qu'elle est planifiée pour s'exécuter.
2.  **Chemin CRON :** Parfois, le chemin PHP dans la commande CRON doit être absolu (par exemple, `/usr/bin/php` au lieu de simplement `php`). Votre hébergeur peut le confirmer.
3.  **Vérifier « Dernière mise à jour » :** Si le champ « Dernière mise à jour » dans la configuration du module ne change jamais, cela confirme que la tâche CRON n'exécute pas le script de mise à jour du module.
4.  **Mise à jour manuelle :** Essayez de cliquer sur le bouton « Mise à jour manuelle » dans la configuration du module. Si cela fonctionne, cela confirme que le module lui-même peut récupérer les taux, ce qui indique définitivement un problème de tâche CRON.

**Q : Les taux de change semblent incorrects ou n'ont pas beaucoup changé.**
R :
1.  **Vérifier la Norges Bank :** Comparez les taux de votre boutique avec les taux officiels publiés par la Norges Bank (leur site web est généralement accessible via une recherche rapide).
2.  **Paramètre de marge :** N'oubliez pas que votre paramètre « Marge de taux de change (%) » ajustera légèrement les taux. Assurez-vous qu'il est défini comme prévu.
3.  **Dernière mise à jour :** Vérifiez le champ « Dernière mise à jour ». S'il est ancien, votre tâche CRON ne s'exécute pas.

**Q : Ce module affecte-t-il ma devise par défaut ?**
R : Non, le module ne met à jour les taux de change que pour les devises non par défaut par rapport à votre devise par défaut. La valeur de votre devise par défaut reste inchangée.

**Q : J'ai mis à jour mon thème, et maintenant le sélecteur de devise ne fonctionne plus correctement.**
R : Ce module ne met à jour que les *valeurs* des taux de change. L'affichage visuel et la fonctionnalité du sélecteur de devise lui-même sont gérés par le cœur de PrestaShop ou votre thème. Si le sélecteur ne fonctionne pas, il s'agit probablement d'un problème de thème ou de PrestaShop, non directement lié à ce module. Videz votre cache Smarty (**Paramètres avancés > Performances**) et vérifiez la configuration de votre thème.

**Q : Puis-je utiliser ce module avec d'autres modules de devise ?**
R : Il n'est généralement pas recommandé d'exécuter plusieurs modules qui tentent de mettre à jour les taux de change, car ils pourraient entrer en conflit ou écraser les données les uns des autres. Ce module est conçu pour être une solution autonome pour les taux de la Norges Bank. Si vous avez besoin de taux provenant d'une source différente, vous devez désactiver ce module et utiliser l'autre.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module « Norges Bank - taux de change » (`nbrates`) est un module PrestaShop léger principalement axé sur une tâche unique et critique : la récupération et la mise à jour des taux de change. Il utilise la classe `Module` de PrestaShop pour l'installation et la configuration et utilise un contrôleur frontal pour exposer un point d'accès CRON pour les mises à jour automatisées. La logique principale implique l'envoi d'une requête HTTP à l'API de la Norges Bank, l'analyse de la réponse XML, le calcul des taux croisés et la mise à jour de la table `ps_currency` de PrestaShop.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    -   `controllers/front/cronjob.php`
        -   **Nom de la classe** : `NbratesCronjobModuleFrontController`
        -   **Classe parente** : `ModuleFrontController`
        -   **Responsabilité** : Ce contrôleur gère l'exécution de la tâche CRON. Lorsqu'il est accédé via son URL (fournie dans la configuration du module), il déclenche la méthode `cronjob()` au sein de la classe principale du module `nbrates`. Il est conçu pour être appelé par un planificateur externe (CRON) et affiche un simple message de succès/échec. Il ne rend aucun contenu visuel pour l'utilisateur.
    -   `controllers/front/index.php`
        -   **Nom de la classe** : `NbratesIndexModuleFrontController`
        -   **Classe parente** : `ModuleFrontController`
        -   **Responsabilité** : Il s'agit d'un contrôleur de substitution, souvent inclus dans les modules mais non activement utilisé dans la fonctionnalité principale de ce module spécifique. Il sert généralement de point d'entrée par défaut si un module a une page front-office dédiée. Dans ce module, son objectif principal est probablement d'empêcher l'affichage du contenu du répertoire si `cronjob.php` est accédé directement sans action spécifique.
-   **Contrôleurs d'administration Back-Office** :

    -   Aucun. Toute la configuration est gérée directement dans la méthode `getContent()` du module principal.

### 4.3 Classes et modèles de base (`classes/`)

-   Aucun. La logique principale du module est autonome dans le fichier principal `nbrates/cronjob.php`. Ceci est courant pour les modules plus simples qui ne nécessitent pas de structures de données complexes ou d'interactions étendues avec la base de données au-delà de la configuration standard.

### 4.4 Actifs JavaScript (`views/js/`)

-   Aucun. Le module n'inclut aucun JavaScript personnalisé pour les fonctionnalités du front-office ou du back-office.

### 4.5 Feuilles de style CSS (`views/css/`)

-   Aucun. Le module n'inclut aucune feuille de style CSS personnalisée. La configuration du back-office repose sur le style par défaut du panneau d'administration de PrestaShop.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles d'administration (`views/templates/admin/`)** :
    -   `views/templates/admin/admin.tpl`
        -   **Objectif** : Ce modèle est rendu par la méthode `getContent()` de la classe principale du module (`nbrates/cronjob.php`) pour afficher le formulaire de configuration du module dans le Back Office de PrestaShop.
        -   **Contenu** : Il contient généralement la structure HTML pour l'affichage de l'URL CRON, le champ de saisie de la marge de taux de change, les informations de « Dernière mise à jour », le bouton de mise à jour manuelle et les instructions de configuration de la tâche CRON. Il utilise les assistants de formulaire et le style standard de PrestaShop.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :

    -   Le module ne crée aucune table de base de données personnalisée.
    -   Il interagit avec la table standard `ps_configuration` de PrestaShop pour stocker ses paramètres (par exemple, `NBS_LAST_UPDATE`, `NBS_MARGIN`).
    -   Il met à jour la table `ps_currency`, spécifiquement la colonne `conversion_rate` pour les devises non par défaut.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayBackOfficeHeader` | Rendu dans la section `<head>` du Back Office. | Utilisé pour inclure tout CSS/JS nécessaire pour la page de configuration du module (bien qu'aucun ne soit utilisé dans ce module). |
| `actionAdminControllerSetMedia` | Appelé avant le rendu d'un contrôleur d'administration. | Utilisé pour enregistrer des ressources (JS/CSS) pour les pages d'administration. |
| `actionCronJob` | Hook personnalisé, déclenché par le contrôleur frontal `cronjob`. | Le hook principal où la logique de mise à jour des devises du module est exécutée. |
| `displayHeader` | Rend le contenu dans la section `<head>` du front office. | (Non explicitement utilisé par ce module pour la sortie, mais souvent enregistré par les modules). |
| `displayLeftColumn` | Rend le contenu dans la colonne de gauche du front office. | (Non explicitement utilisé par ce module pour la sortie). |
| `displayRightColumn` | Rend le contenu dans la colonne de droite du front office. | (Non explicitement utilisé par ce module pour la sortie). |
| `displayFooter` | Rend le contenu dans le pied de page du front office. | (Non explicitement utilisé par ce module pour la sortie). |
| `displayProductExtraContent` | Rend le contenu sur la page produit. | (Non explicitement utilisé par ce module pour la sortie). |

*Note : Bien que la description du module mentionne des hooks Front-Office comme Header, Columns, Product ou Footer, l'inventaire du code fourni ne montre aucun modèle ou logique spécifique pour le rendu de contenu dans ces hooks. Il est possible que ce soient des hooks génériques enregistrés lors de l'installation mais non activement utilisés pour la sortie visuelle par ce module spécifique, car sa fonction est purement la synchronisation des données backend.*

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Norges Bank - taux de change », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Vous pouvez télécharger les versions les plus récentes depuis l'historique de vos commandes et accéder aux ressources de support directement depuis la plateforme MyPresta.eu.
