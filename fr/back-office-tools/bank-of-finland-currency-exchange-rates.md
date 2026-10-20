---
title: "Banque de Finlande - taux de change - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Banque de Finlande - taux de change par MyPresta.eu."
sidebar:
  label: "Banque de Finlande - taux de change - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Bank of Finland - currency exchange rates sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-finland-currency-exchange-rates.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/bank-of-finland-currency-exchange-rates/)
>
> ---


# Banque de Finlande - taux de change

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour récupérer des données externes. Votre environnement d'hébergement doit également prendre en charge les tâches CRON pour les mises à jour automatisées.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » pour accéder aux paramètres du module. C'est ici que vous définirez comment les taux de change sont mis à jour et appliqués.

#### **1. URL CRON**

- **Ce que fait ce paramètre :** Il s'agit d'une adresse web unique (URL) qui, lorsqu'elle est visitée, déclenche le module pour récupérer les derniers taux de change auprès de la Banque de Finlande et les mettre à jour dans votre boutique PrestaShop.
- **Effet de la modification de ce paramètre :** Vous ne pouvez pas modifier cette URL directement. Elle est générée par le module. Cette URL est cruciale pour la mise en place d'une tâche automatisée (tâche CRON) sur votre serveur web.
- **Valeur recommandée :** Copiez cette URL exactement telle qu'elle apparaît.
- **Scénario / exemple de marchand :** Vous fournirez cette URL à votre hébergeur ou l'utiliserez dans votre panneau de contrôle d'hébergement (par exemple, cPanel, Plesk) pour configurer une tâche CRON. Cela garantit que vos taux de change sont mis à jour automatiquement, par exemple, une fois par jour, sans que vous ayez à cliquer manuellement sur quoi que ce soit.

#### **2. Instructions de configuration de la tâche CRON**

- **Ce que fait ce paramètre :** Cette section fournit des instructions sur la façon de configurer la tâche CRON en utilisant l'URL fournie ci-dessus. Une tâche CRON est un planificateur de tâches basé sur le temps dans les systèmes d'exploitation de type Unix. Il vous permet de planifier l'exécution automatique de commandes ou de scripts à des intervalles spécifiés.
- **Effet de la modification de ce paramètre :** Il s'agit d'une section informative ; vous ne modifiez rien ici. Suivre correctement ces instructions garantit que vos taux de change sont mis à jour automatiquement.
- **Valeur recommandée :** Lisez et suivez attentivement ces instructions.
- **Scénario / exemple de marchand :** Le panneau de contrôle de votre hébergeur (comme cPanel) aura une section « Tâches Cron » ou « Tâches planifiées ». Vous ajouterez généralement une nouvelle tâche cron, spécifierez la fréquence (par exemple, une fois par jour à 3h du matin) et collerez l'URL CRON dans le champ de commande, souvent précédée de `wget -q -O /dev/null`.

#### **3. Marge (%)**

- **Ce que fait ce paramètre :** Cela vous permet d'ajouter une marge en pourcentage aux taux de change récupérés. Par exemple, si le taux officiel est de 1 EUR = 1,10 USD, et que vous définissez une marge de 2 %, le module utilisera 1 EUR = 1,078 USD (1,10 \* 0,98) ou 1 EUR = 1,122 USD (1,10 \* 1,02) selon la façon dont le module applique la marge (généralement pour se protéger contre les fluctuations, il pourrait donc légèrement augmenter le prix en devise étrangère).
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est réglé sur 0 :* Les taux de change seront mis à jour exactement tels que fournis par la Banque de Finlande.
  - *Lorsqu'il est réglé sur une valeur positive (par exemple, 2) :* Le module ajustera le taux de change de ce pourcentage. Cela peut aider à couvrir les frais de transaction, les coûts de conversion de devises, ou simplement à fournir une petite marge contre les mouvements de taux défavorables, garantissant ainsi le maintien de vos marges bénéficiaires.
- **Valeur recommandée :** Commencez par 0. Si vous rencontrez des problèmes de rentabilité en raison des fluctuations monétaires ou des frais de conversion, envisagez une petite marge comme 1 à 3 %.
- **Scénario / exemple de marchand :** Si vous vendez un produit pour 100 EUR et que le taux de change est de 1 EUR = 1,10 USD, le produit coûterait 110 USD. Si vous définissez une marge de 2 %, le module pourrait calculer le taux comme 1 EUR = 1,078 USD, ce qui rend le produit à 107,80 USD. Cela vous donne une petite marge.

#### **4. Dernière mise à jour**

- **Ce que fait ce paramètre :** Il affiche la date et l'heure de la dernière mise à jour réussie des taux de change par le module.
- **Effet de la modification de ce paramètre :** Il s'agit d'un champ informatif qui ne peut pas être modifié directement. Il sert de vérification que votre tâche CRON fonctionne correctement et que le module met activement à jour les taux.
- **Valeur recommandée :** Cela devrait afficher une date et une heure récentes, idéalement dans les dernières 24 heures si votre tâche CRON s'exécute quotidiennement.
- **Scénario / exemple de marchand :** Si vous configurez votre tâche CRON pour qu'elle s'exécute quotidiennement à 3h du matin, vous devriez voir l'horodatage « Dernière mise à jour » changer pour refléter 3h du matin (ou peu après) du jour actuel chaque matin. Si elle ne se met pas à jour, cela indique un problème avec la configuration de votre tâche CRON.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | URL CRON | Copier exactement | URL unique pour déclencher les mises à jour des taux via une tâche CRON. |
| Configuration du module | Instructions de configuration de la tâche CRON | Lire attentivement | Guide pour la configuration des mises à jour automatisées sur votre serveur. |
| Configuration du module | Marge (%) | 0 (ou 1-3% si nécessaire) | Ajoute une marge en pourcentage aux taux de change pour protéger les marges bénéficiaires. |
| Configuration du module | Dernière mise à jour | N/A (informatif) | Affiche l'horodatage de la dernière mise à jour réussie des taux. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes taux de change ne se mettent pas à jour. Que dois-je faire ?**
R1 : Cela est presque toujours lié à la configuration de la tâche CRON.
1. **Vérifiez l'horodatage « Dernière mise à jour » :** Allez sur la page de configuration du module. Si cette date est ancienne, votre tâche CRON ne s'exécute pas.
2. **Vérifiez la configuration de la tâche CRON :** Connectez-vous à votre panneau de contrôle d'hébergement (par exemple, cPanel, Plesk). Naviguez vers la section « Tâches Cron » ou « Tâches planifiées ».
\* Assurez-vous que l'URL CRON que vous avez copiée du module est exactement celle qui se trouve dans la commande de votre tâche CRON.
\* Assurez-vous que la commande est correctement formatée (par exemple, `wget -q -O /dev/null "VOTRE_URL_CRON_ICI"`).
\* Confirmez que la fréquence est définie comme souhaité (par exemple, quotidiennement).
\* Vérifiez l'adresse e-mail associée à la tâche CRON (le cas échéant) pour les messages d'erreur.
3. **Exécutez manuellement l'URL CRON :** Copiez l'URL CRON de la configuration du module et collez-la directement dans la barre d'adresse de votre navigateur web. Cela devrait déclencher une mise à jour. Si cela fonctionne, le problème est certainement lié à la configuration de la tâche CRON de votre serveur. Si cela ne fonctionne pas, il peut y avoir un problème côté serveur empêchant le module de récupérer les données (par exemple, pare-feu, cURL non activé).

**Q2 : Mes prix en devises étrangères semblent légèrement erronés, même après les mises à jour.**
R2 : Vérifiez le paramètre « Marge (%) » dans la configuration du module. Si vous avez défini une marge (par exemple, 2 %), le module ajustera intentionnellement le taux de change de ce pourcentage. Si vous souhaitez des taux officiels exacts, définissez la marge sur 0. Assurez-vous également que votre devise de base dans PrestaShop (Localisation > Devises) est correctement définie sur EUR si vous traitez principalement avec les taux de la Banque de Finlande.

**Q3 : Ce module fonctionne-t-il avec toutes les devises ?**
R3 : Le module récupère les données de référence officielles de la Banque de Finlande, qui fournit principalement des taux par rapport à l'Euro. Cependant, il calcule intelligemment les taux croisés pour les devises non-euro. Cela signifie que si la Banque de Finlande fournit des taux EUR vers USD et EUR vers GBP, le module peut en déduire le taux USD vers GBP. Tant que la Banque de Finlande fournit un taux pour une devise par rapport à l'Euro, le module devrait être en mesure de le mettre à jour.

**Q4 : Dois-je vider mon cache Smarty après les mises à jour ?**
R4 : Non, généralement pas. Ce module met à jour les valeurs de la base de données (taux de change). Le cache Smarty de PrestaShop affecte principalement la compilation des modèles et le contenu statique. Les changements de taux de change sont dynamiques et devraient se refléter immédiatement dans la tarification de votre boutique sans avoir besoin de vider le cache.

**Q5 : Mon thème personnalisé n'affiche pas correctement les prix mis à jour.**
R5 : Le module met à jour les taux de change sous-jacents dans la base de données de PrestaShop. Le sélecteur de devise et la logique d'affichage des prix de votre thème devraient automatiquement prendre en compte ces taux mis à jour. Si ce n'est pas le cas, il s'agit probablement d'un problème spécifique au thème plutôt que d'un problème de module.
1. **Vérifiez les taux internes de PrestaShop :** Allez dans **Localisation > Devises** dans votre Back Office. Vérifiez la colonne « Taux de change » pour vos devises non-EUR. Si ces taux sont mis à jour correctement, le module fonctionne.
2. **Contactez le développeur de votre thème :** Si les taux sont corrects dans le Back Office mais pas sur le front-office, votre thème pourrait avoir une mise en cache personnalisée ou une manière spécifique de gérer l'affichage des devises qui nécessite l'attention du développeur du thème.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Banque de Finlande - taux de change » (`sprates`) est un module PrestaShop léger conçu pour une tâche unique et critique : l'automatisation des mises à jour des taux de change. Il utilise un contrôleur de front-office pour exposer un point d'accès appelable par CRON, qui, lorsqu'il est accédé, récupère les données XML de la Banque de Finlande, les analyse et met à jour la table `ps_currency`. Le module suit un modèle MVC PrestaShop standard pour sa configuration et son déclencheur front-end.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs de Front-Office

- `sprates/controllers/front/cronjob.php`
  - **Nom de la classe et classe parente :** `SpratesCronjobModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** C'est le contrôleur principal du processus de mise à jour automatisée. Il répond aux requêtes faites à l'URL CRON. Lors de l'exécution, il :
    1. Récupère les données XML du flux officiel des taux de change de la Banque de Finlande.
    2. Analyse le XML pour extraire les taux de change basés sur l'EUR.
    3. Calcule les taux croisés pour les devises non-EUR si nécessaire.
    4. Applique la marge configurée.
    5. Met à jour la colonne `exchange_rate` dans la table `ps_currency` pour toutes les devises actives dans PrestaShop.
    6. Met à jour l'horodatage `last_update` dans la configuration du module.
    7. Affiche un simple message de succès ou d'erreur (souvent supprimé par `wget -q -O /dev/null`).
- `sprates/controllers/front/index.php`
  - **Nom de la classe et classe parente :** `SpratesIndexModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** C'est un contrôleur de substitution, généralement utilisé pour empêcher l'affichage des répertoires ou fournir une action par défaut si la distribution principale du module n'est pas utilisée. Dans le contexte de ce module, il sert probablement de solution de repli ou de pratique PrestaShop standard pour les modules avec des contrôleurs frontaux, mais la logique principale réside dans `cronjob.php`.

#### Contrôleurs d'administration du Back-Office

Ce module n'utilise aucun contrôleur d'administration personnalisé dédié. Toute la configuration est gérée via la méthode `getContent()` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe ou modèle personnalisé dans le répertoire `classes/`. Il interagit directement avec les classes `Currency` et `Configuration` de PrestaShop pour gérer les taux de change et les paramètres du module.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **Modèles d'administration (`views/templates/admin/`)** :
  - `sprates/views/admin.tpl`
    - **Objectif :** Ce modèle rend le formulaire de configuration du module dans le Back Office de PrestaShop. Il affiche l'URL CRON, les instructions de configuration, le champ de saisie de la marge et l'horodatage de la dernière mise à jour. Il utilise des éléments de formulaire d'aide PrestaShop standard.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données

Le module ne crée aucune table de base de données personnalisée. Il interagit avec les tables PrestaShop existantes :

- `ps_currency` : Met à jour la colonne `exchange_rate` pour les devises actives.
- `ps_configuration` : Stocke les paramètres spécifiques au module tels que `SP_RATES_MARGIN` (pour le pourcentage de marge) et `SP_RATES_LAST_UPDATE` (pour l'horodatage de la dernière mise à jour).

#### Tableau des hooks enregistrés

Ce module n'enregistre aucun hook d'affichage traditionnel (par exemple, `displayHeader`, `displayFooter`) car il n'a pas de composants visuels côté front-office. Son mécanisme de « hook » principal est la tâche CRON, qui déclenche son contrôleur frontal.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionModuleInstall` | Lors de l'installation du module | Définit les valeurs de configuration par défaut. |
| `actionModuleUninstall` | Lors de la désinstallation du module | Nettoie les valeurs de configuration. |
| (Tâche CRON via le contrôleur frontal) | Planifié par le serveur (par exemple, quotidiennement) | Récupère, calcule et met à jour les taux de change. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Banque de Finlande - taux de change », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question que vous pourriez avoir.
"""
