---
title: "Banque d'Israël - taux de change - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Banque d'Israël - taux de change par MyPresta.eu."
sidebar:
  label: "Banque d'Israël - taux de change - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Bank of Israel - currency exchange rates sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-israel-currency-exchange-rates.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/bank-of-israel-currency-exchange-rates/)
>
> ---


# Banque d'Israël - taux de change

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour récupérer des données externes. Votre environnement d'hébergement doit également prendre en charge les tâches CRON pour les mises à jour automatisées.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » pour accéder aux paramètres du module. C'est l'écran principal où vous configurerez la manière dont le module récupère et applique les taux de change.

#### **Mises à jour MyPresta.eu**

-   **Ce que fait ce paramètre :** Cette section fournit des informations sur les mises à jour de MyPresta.eu, y compris la version actuelle du module et les mises à jour disponibles. Elle vous aide à maintenir votre module à jour.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'une mise à jour est disponible :* Vous verrez une notification et un lien pour télécharger la dernière version depuis votre compte MyPresta.eu.
    *   *Lorsqu'aucune mise à jour n'est disponible :* La section affichera simplement votre version actuelle.
-   **Valeur recommandée :** Gardez toujours vos modules à jour pour bénéficier des nouvelles fonctionnalités, des corrections de bugs et des améliorations de sécurité.
-   **Scénario / exemple de marchand :** Vérifiez régulièrement cette section pour vous assurer que votre module est à jour, surtout après des mises à niveau majeures de la version de PrestaShop.

#### **Intervalle de mise à jour**

-   **Ce que fait ce paramètre :** Cela détermine la fréquence à laquelle le module tente de récupérer et de mettre à jour les taux de change auprès de la Banque d'Israël.
-   **Effet de la modification de ce paramètre :**
    *   *Définir un intervalle plus court (par exemple, 1 heure) :* Les taux de change seront mis à jour plus fréquemment, garantissant que vos prix sont toujours très proches du temps réel. C'est bon pour les devises très volatiles ou les ventes internationales à volume élevé.
    *   *Définir un intervalle plus long (par exemple, 24 heures) :* Les taux de change seront mis à jour moins fréquemment. Cela pourrait convenir si les fluctuations monétaires ne sont pas une préoccupation majeure pour votre entreprise ou si vous préférez des appels externes moins fréquents.
-   **Valeur recommandée :** « 24 heures » pour la plupart des boutiques. Si vous avez un volume de ventes élevé avec des clients internationaux et des taux de change fréquemment modifiés, envisagez « 12 heures » ou « 6 heures ».
-   **Scénario / exemple de marchand :** Si vous vendez des produits électroniques de grande valeur à des clients internationaux, vous pourriez choisir « 6 heures » pour vous assurer que vos prix reflètent les dernières conditions du marché. Pour une boutique locale avec des ventes internationales occasionnelles, « 24 heures » est suffisant.

#### **Marge de mise à jour (%)**

-   **Ce que fait ce paramètre :** Cela vous permet d'ajouter une marge en pourcentage aux taux de change récupérés auprès de la Banque d'Israël. Cette marge est appliquée en plus du taux officiel.
-   **Effet de la modification de ce paramètre :**
    *   *Définir une marge positive (par exemple, 2 %) :* Vos prix convertis dans d'autres devises seront légèrement supérieurs au taux de change officiel direct, vous aidant à couvrir les frais de transaction potentiels, les coûts de conversion de devises, ou simplement à augmenter votre marge bénéficiaire.
    *   *Définir une marge nulle (0 %) :* Vos prix refléteront le taux de change officiel exact sans aucune majoration supplémentaire.
-   **Valeur recommandée :** « 0 » si vous souhaitez des taux officiels exacts. Une petite valeur positive (par exemple, « 1 » ou « 2 ») est souvent recommandée pour couvrir les frais bancaires potentiels ou fournir un tampon contre les fluctuations mineures.
-   **Scénario / exemple de marchand :** Si votre passerelle de paiement facture des frais de 1,5 % pour les transactions internationales, définir une marge de « 1,5 » ou « 2 » pour cent peut vous aider à absorber ce coût sans impacter le prix de base de votre produit dans votre devise par défaut.

#### **Devises à mettre à jour**

-   **Ce que fait ce paramètre :** Il s'agit d'une liste de toutes les devises actuellement actives dans votre boutique PrestaShop. Vous pouvez sélectionner lesquelles de ces devises doivent voir leurs taux de change automatiquement mis à jour par ce module.
-   **Effet de la modification de ce paramètre :**
    *   *Sélectionner une devise (case cochée) :* Le module récupérera le taux de change de cette devise (par rapport à l'ILS) auprès de la Banque d'Israël et le mettra à jour dans votre boutique.
    *   *Désélectionner une devise (case décochée) :* Le module ignorera cette devise, et son taux de change ne sera *pas* automatiquement mis à jour. Vous devrez le mettre à jour manuellement si nécessaire.
-   **Valeur recommandée :** Sélectionnez toutes les devises que vous utilisez activement pour les ventes internationales et que vous souhaitez maintenir à jour. Assurez-vous que votre devise par défaut (par exemple, ILS) est correctement configurée dans PrestaShop.
-   **Scénario / exemple de marchand :** Si vous vendez à des clients aux États-Unis, en Europe et au Royaume-Uni, vous cocherez les cases pour USD, EUR et GBP. Si vous ne vendez que localement en ILS et occasionnellement aux États-Unis, vous ne cocherez peut-être que USD.

#### **URL de la tâche CRON**

-   **Ce que fait ce paramètre :** Il affiche l'URL unique qui doit être configurée comme une tâche CRON sur votre serveur web. Une tâche CRON est une tâche planifiée qui indique à votre serveur de visiter cette URL à intervalles réguliers, déclenchant le module pour récupérer et mettre à jour automatiquement les taux de change.
-   **Effet de la modification de ce paramètre :** Ce n'est pas un paramètre que vous modifiez, mais plutôt une URL que vous *utilisez*.
    *   *Lorsque la tâche CRON est correctement configurée :* Le module s'exécutera automatiquement à votre « Intervalle de mise à jour » spécifié, gardant vos taux de change à jour sans aucune intervention manuelle.
    *   *Lorsque la tâche CRON n'est PAS configurée :* Les taux de change ne seront *pas* mis à jour automatiquement. Vous devrez visiter manuellement cette URL dans votre navigateur (ce qui n'est pas recommandé pour une utilisation régulière) ou mettre à jour manuellement les taux dans PrestaShop.
-   **Valeur recommandée :** Copiez cette URL et configurez-la comme une tâche CRON sur votre panneau d'hébergement (par exemple, cPanel, Plesk, ou via SSH). La fréquence de la tâche CRON doit correspondre ou être légèrement plus fréquente que votre paramètre « Intervalle de mise à jour ». Par exemple, si votre intervalle de mise à jour est de 24 heures, configurez la tâche CRON pour qu'elle s'exécute une fois toutes les 24 heures.
-   **Scénario / exemple de marchand :** Après avoir configuré tous les autres paramètres, copiez cette URL et collez-la dans le planificateur de tâches CRON de votre hébergeur. Configurez-la pour qu'elle s'exécute quotidiennement à une heure de faible trafic (par exemple, 3h du matin).

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Mises à jour MyPresta.eu | N/A | Affiche la version du module et la disponibilité des mises à jour. |
| Configuration du module | Intervalle de mise à jour | 24 heures | Fréquence de récupération des taux de change (par exemple, 6, 12, 24 heures). |
| Configuration du module | Marge de mise à jour (%) | 0-2% | Ajoute une majoration en pourcentage aux taux de change récupérés. |
| Configuration du module | Devises à mettre à jour | Toutes les devises actives | Sélectionne les devises à mettre à jour automatiquement. |
| Configuration du module | URL de la tâche CRON | N/A | URL à configurer sur votre serveur pour les mises à jour automatisées. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes taux de change ne se mettent pas à jour automatiquement. Que dois-je faire ?**
R :

1.  **Vérifiez la tâche CRON :** La raison la plus courante est une tâche CRON mal configurée ou manquante. Vérifiez l'URL de la tâche CRON fournie dans la configuration du module et assurez-vous qu'elle est correctement configurée sur votre serveur d'hébergement pour s'exécuter à la fréquence souhaitée.
2.  **Paramètres du module :** Vérifiez que l'« Intervalle de mise à jour » est défini et que les « Devises à mettre à jour » souhaitées sont cochées dans la configuration du module.
3.  **Accès au serveur :** Assurez-vous que votre serveur peut effectuer des requêtes externes vers l'API de la Banque d'Israël. Parfois, les pare-feu ou les paramètres de sécurité peuvent bloquer cela. Contactez votre hébergeur si vous suspectez cela.
4.  **Cache PrestaShop :** Videz le cache de votre PrestaShop (Paramètres avancés > Performances > Vider le cache) après avoir apporté des modifications aux paramètres du module.

**Q : Puis-je annuler manuellement un taux de change après que le module l'ait mis à jour ?**
R : Oui, vous le pouvez. Une fois le module exécuté, les taux sont stockés dans les paramètres de devise standard de PrestaShop (International > Devises). Vous pouvez modifier manuellement le taux de change d'une devise spécifique à cet endroit. Cependant, sachez que la prochaine fois que la tâche CRON s'exécutera, elle écrasera votre modification manuelle avec le dernier taux de la Banque d'Israël (plus votre marge).

**Q : Que se passe-t-il si l'API de la Banque d'Israël est temporairement indisponible ?**
R : Si le module ne peut pas récupérer les données, il conservera généralement les derniers taux de change mis à jour avec succès. Il ne supprimera ni ne réinitialisera vos taux à zéro. Il essaiera simplement à nouveau lors de la prochaine exécution planifiée de la tâche CRON.

**Q : Mes prix semblent légèrement erronés après la mise à jour. Pourquoi ?**
R :

1.  **Marge de mise à jour :** Vérifiez le paramètre « Marge de mise à jour (%) » dans la configuration du module. Si vous avez défini une marge positive, vos prix seront légèrement supérieurs au taux officiel direct.
2.  **Arrondi :** Les paramètres de devise de PrestaShop ont également une option « Nombre de décimales ». Assurez-vous que cela est défini de manière appropriée pour vos devises afin d'éviter des problèmes d'arrondi inattendus.
3.  **Devise de base :** Assurez-vous que votre devise par défaut dans PrestaShop (International > Devises) est correctement définie comme le Shekel israélien (ILS) si c'est votre devise de base pour ces mises à jour.

**Q : Comment configurer une tâche CRON ?**
R : Ce processus varie selon l'hébergeur. Généralement, vous vous connecterez à votre panneau de contrôle d'hébergement (par exemple, cPanel, Plesk). Recherchez une section nommée « Tâches Cron », « Tâches planifiées » ou « Tâches automatisées ». Vous devrez ajouter une nouvelle tâche CRON, spécifier la fréquence (par exemple, une fois par jour) et coller l'« URL de la tâche CRON » fournie par le module. Si vous n'êtes pas sûr, contactez le support de votre hébergeur, en leur fournissant l'URL et la fréquence souhaitée.

## 4. Guide du développeur et du webmaster (architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Banque d'Israël - taux de change » (`boirates`) suit une architecture de module PrestaShop standard. Il utilise une classe de module principale (`boirates.php`) pour l'installation, la désinstallation et la gestion de la configuration. Les mises à jour des taux de change sont principalement déclenchées via un contrôleur frontal (`cronjob.php`) conçu pour être appelé par une tâche CRON côté serveur. Le module récupère les données XML de l'API officielle de la Banque d'Israël, les analyse et met à jour la table `ps_currency` de PrestaShop.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    -   `controllers/front/cronjob.php`
        -   **Nom de la classe** : `BoiratesCronjobModuleFrontController` (étend `ModuleFrontController`)
        -   **Responsabilité** : Ce contrôleur est conçu pour être invoqué par une tâche CRON externe. Il contient la logique principale pour récupérer les taux de change de l'API de la Banque d'Israël, analyser la réponse XML, appliquer la marge configurée et mettre à jour la table `ps_currency` dans PrestaShop. Il ne rend aucun contenu front-office mais effectue un traitement de données en arrière-plan. Il est crucial pour la fonctionnalité automatisée du module.
    -   `controllers/front/index.php`
        -   **Nom de la classe** : `BoiratesIndexModuleFrontController` (étend `ModuleFrontController`)
        -   **Responsabilité** : Il s'agit d'un contrôleur frontal de substitution ou par défaut. Dans de nombreux modules, si une action spécifique n'est pas routée, `index.php` peut être appelé. Pour ce module, sa fonction principale est probablement d'empêcher l'affichage du répertoire ou de fournir une réponse par défaut minimale s'il est accédé directement sans paramètres spécifiques. La logique principale réside dans `cronjob.php`.
-   **Contrôleurs d'administration Back-Office** :

    -   Aucun. Toute la configuration est gérée directement dans la méthode `getContent()` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)

-   Aucun. La logique du module est principalement encapsulée dans le fichier `boirates.php` principal et le `BoiratesCronjobModuleFrontController`. L'interaction avec les données est directe avec la classe `Currency` de PrestaShop et la table `ps_configuration`.

### 4.4 Actifs JavaScript (`views/js/`)

-   Aucun. Le module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

-   Aucun. Le module n'inclut aucun fichier CSS personnalisé.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles d'administration (`views/templates/admin/`)** :
    -   `views/templates/admin/admin.tpl`
        -   **Objectif** : Ce modèle est rendu par la méthode `getContent()` du fichier de module `boirates.php`. Il définit la structure et la mise en page de la page de configuration du module dans le Back Office de PrestaShop. Il inclut les éléments de formulaire pour les paramètres `mypresta_updates`, `update_`, `updatev_` et `currency_`, ainsi que l'affichage de l'URL de la tâche CRON.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module ne crée aucune table SQL personnalisée.
    -   Il interagit avec la table `ps_configuration` standard de PrestaShop pour stocker ses paramètres (par exemple, `BOIRATES_UPDATE_INTERVAL`, `BOIRATES_UPDATE_MARGIN`, `BOIRATES_CURRENCIES_TO_UPDATE`).
    -   Il met à jour la colonne `exchange_rate` dans la table `ps_currency` pour les devises sélectionnées.
-   **Table des hooks enregistrés** :
    Le module n'enregistre explicitement aucun hook d'affichage front-office (comme `displayHeader`, `displayRightColumn`, `displayProductButtons`, `displayFooter`) dans sa méthode `install()` pour le rendu de contenu. Sa fonction principale est le traitement des données en arrière-plan.
    Il utilise probablement des hooks PrestaShop internes pour sa fonctionnalité principale, tels que :

    | Nom du hook | Moment d'exécution | Objectif technique |
    | --- | --- | --- |
    | `actionModuleInstall` | Pendant l'installation du module | Configure les valeurs de configuration par défaut et enregistre les éléments nécessaires. |
    | `actionModuleUninstall` | Pendant la désinstallation du module | Nettoie les valeurs de configuration. |
    | `displayBackOfficeHeader` | Rend le contenu dans l'en-tête du Back Office | Potentiellement utilisé pour ajouter du CSS/JS ou des notifications, bien que non explicitement détecté dans l'inventaire. |

## 5. Support officiel et mises à jour

Pour le support officiel, les mises à jour et pour télécharger les dernières versions du module « Banque d'Israël - taux de change », veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité et la compatibilité du module.
