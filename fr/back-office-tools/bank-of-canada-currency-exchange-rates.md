---
title: "Banque du Canada - taux de change - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Banque du Canada - taux de change par MyPresta.eu."
sidebar:
  label: "Banque du Canada - taux de change - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Bank of Canada - currency exchange rates sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-canada-currency-exchange-rates.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/bank-of-canada-currency-exchange-rates/)
>
> ---


# Banque du Canada - taux de change

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour la récupération de données externes, et sont presque universellement disponibles sur les environnements d'hébergement modernes.

## 2. Présentation complète de la configuration (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » pour accéder aux paramètres du module. C'est l'écran principal où vous gérerez la mise à jour des taux de change.

#### **1. Mettre à jour les taux de change manuellement**

-   **Ce que fait ce paramètre :** C'est un bouton qui, lorsqu'il est cliqué, déclenche immédiatement le module pour récupérer les derniers taux de change de la Banque du Canada et les mettre à jour dans votre boutique.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est cliqué :* Le module se connecte à la Banque du Canada, récupère les taux les plus récents, calcule les taux croisés et les applique aux devises de votre boutique. Un message de confirmation apparaît généralement.
-   **Valeur recommandée :** Utilisez ce bouton pour des mises à jour immédiates ou pour tester le module après la configuration initiale. Pour les mises à jour continues, la tâche CRON (expliquée ci-dessous) est recommandée.
-   **Scénario / exemple de marchand :** Vous venez de lancer un nouveau produit et souhaitez vous assurer que tous les prix internationaux sont absolument à jour avant une campagne marketing majeure. Cliquez sur ce bouton pour forcer une mise à jour immédiate.

#### **2. URL de la tâche CRON**

-   **Ce que fait ce paramètre :** Ce champ affiche une URL unique qui, lorsqu'elle est accédée, déclenche le module pour mettre à jour automatiquement les taux de change. Cette URL est conçue pour être utilisée avec une « tâche CRON » sur votre serveur web.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsque l'URL est accédée (par une tâche CRON) :* Le module effectue le même processus de mise à jour des taux que le clic sur le bouton de mise à jour manuelle, mais il le fait automatiquement à intervalles réguliers.
-   **Valeur recommandée :** Copiez cette URL et configurez-la comme une tâche CRON sur votre serveur d'hébergement.
-   **Scénario / exemple de marchand :** Vous souhaitez que vos taux de change soient mis à jour tous les jours à 3h du matin. Vous copiez cette URL et configurez votre panneau d'hébergement (cPanel, Plesk, etc.) pour visiter cette URL quotidiennement à 3h du matin. Cela garantit que vos taux sont toujours à jour sans que vous ayez à lever le petit doigt.

#### **3. Marge de taux de change (%)**

-   **Ce que fait ce paramètre :** Cela vous permet d'ajouter une marge en pourcentage aux taux de change récupérés de la Banque du Canada. Par exemple, si le taux de la BDC est de 1,20 et que vous définissez une marge de 2 %, votre boutique utilisera un taux de 1,224 (1,20 \* 1,02).
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est défini sur une valeur positive (par exemple, 2) :* Tous les prix convertis dans votre boutique seront légèrement plus élevés, reflétant la marge ajoutée. Cela peut aider à couvrir les frais de transaction, les coûts de conversion de devises ou simplement à augmenter votre marge bénéficiaire sur les ventes internationales.
    -   *Lorsqu'il est défini sur 0 (ou laissé vide) :* Le module utilisera les taux de change exacts fournis par la Banque du Canada sans aucune majoration supplémentaire.
-   **Valeur recommandée :** Commencez par 0 % et ajustez en fonction de vos besoins commerciaux, des frais de passerelle de paiement et des marges bénéficiaires souhaitées. Une pratique courante est de 1 à 3 % pour couvrir les coûts potentiels.
-   **Scénario / exemple de marchand :** Votre passerelle de paiement facture des frais de 1,5 % pour les conversions de devises internationales. Vous définissez la « Marge de taux de change » à 1,5 % pour vous assurer que ce coût est couvert dans la tarification de vos produits, plutôt que d'éroder votre profit.

#### **4. Dernière mise à jour**

-   **Ce que fait ce paramètre :** Ce champ affiche la date et l'heure de la dernière mise à jour réussie des taux de change effectuée par le module.
-   **Effet de la modification de ce paramètre :** Il s'agit d'un champ en lecture seule et ne peut pas être modifié. Il sert d'indicateur informatif.
-   **Valeur recommandée :** Surveillez ce champ pour vous assurer que votre tâche CRON fonctionne correctement et que les taux sont mis à jour régulièrement.
-   **Scénario / exemple de marchand :** Vous remarquez que vos prix internationaux semblent obsolètes. Vous vérifiez « Dernière mise à jour » et constatez qu'il n'a pas été mis à jour depuis une semaine, ce qui indique un problème potentiel avec la configuration de votre tâche CRON.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Mettre à jour les taux de change manuellement (Bouton) | Cliquer pour mettre à jour | Force une mise à jour immédiate de tous les taux de change des devises de la BDC. |
| Configuration du module | URL de la tâche CRON | Copier et configurer sur le serveur | Fournit une URL pour les mises à jour automatisées et planifiées via le service CRON de votre hébergement. |
| Configuration du module | Marge de taux de change (%) | 0% | Ajoute une majoration en pourcentage aux taux de change récupérés, affectant tous les prix convertis. |
| Configuration du module | Dernière mise à jour | Lecture seule | Affiche l'horodatage de la dernière mise à jour réussie des taux de change. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes taux de change ne se mettent pas à jour automatiquement. Que dois-je faire ?**
R1 : C'est presque toujours un problème de tâche CRON.
-   **Vérifiez votre panneau d'hébergement :** Connectez-vous à votre compte d'hébergement (cPanel, Plesk, etc.) et vérifiez que la tâche CRON est correctement configurée avec l'URL exacte fournie par le module. Assurez-vous que la fréquence est correcte (par exemple, quotidienne).
-   **Vérifiez la commande CRON :** La commande ressemble généralement à `wget -O /dev/null "VOTRE_URL_CRON_ICI"` ou `curl "VOTRE_URL_CRON_ICI"`. Assurez-vous qu'il n'y a pas de fautes de frappe.
-   **Vérifiez « Dernière mise à jour » dans le module :** Si cette date est ancienne, cela confirme que le CRON ne s'exécute pas.
-   **Exécutez manuellement l'URL CRON :** Copiez l'URL CRON de la configuration du module et collez-la dans votre navigateur. Si elle se met à jour, alors l'URL elle-même est correcte, et le problème vient uniquement de la configuration CRON de votre hébergement.

**Q2 : Les prix dans d'autres devises semblent trop élevés/bas par rapport à la devise par défaut.**
R2 :
-   **Vérifiez votre « Marge de taux de change (%) » :** Si elle est trop élevée, les prix seront gonflés. Si elle est négative (bien que non recommandée), les prix seraient plus bas.
-   **Vérifiez votre devise par défaut :** Assurez-vous que la devise par défaut de votre boutique PrestaShop (Localisation > Devises) est correctement définie sur votre devise d'exploitation principale (par exemple, CAD si vous récupérez de la Banque du Canada). Le module calcule les taux par rapport à votre devise par défaut.
-   **Videz le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). Parfois, d'anciens prix peuvent être mis en cache.

**Q3 : Le module indique que la « Dernière mise à jour » a réussi, mais je ne vois pas les changements sur le front office.**
R3 :
-   **Videz le cache de PrestaShop :** C'est la raison la plus courante. Videz toujours votre cache après toute mise à jour de données significative dans PrestaShop.
-   **Vérifiez le cache du navigateur :** Essayez de vider le cache de votre navigateur ou de consulter votre boutique dans une fenêtre de navigation privée pour exclure les problèmes de cache local.
-   **Vérifiez la sélection de la devise :** Assurez-vous que vous consultez réellement la boutique dans la devise non par défaut où vous vous attendez à voir les prix convertis.

**Q4 : Ce module fonctionne-t-il avec des thèmes personnalisés ?**
R4 : Oui, ce module fonctionne en arrière-plan en mettant à jour les taux de change des devises de base de PrestaShop. Il n'interagit pas directement avec les éléments visuels de votre thème, il devrait donc être compatible avec n'importe quel thème personnalisé. Le sélecteur de devise du thème affichera simplement les prix basés sur les taux fournis par le module.

**Q5 : Puis-je utiliser ce module si ma devise par défaut n'est pas le CAD ?**
R5 : Oui, vous le pouvez. Le module récupère les taux de base de la Banque du Canada (par exemple, USD vers CAD, EUR vers CAD). Il calcule ensuite intelligemment les taux croisés par rapport à *la devise par défaut de votre boutique*. Ainsi, si votre devise par défaut est l'EUR, et que la BDC fournit USD/CAD, le module calculera EUR/USD, EUR/CAD, etc., en fonction des données disponibles.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Banque du Canada - taux de change » (`bocrates`) est conçu comme une solution légère et automatisée pour la synchronisation des taux de change. Il s'appuie principalement sur l'`ObjectModel` `Currency` de PrestaShop pour mettre à jour les taux de change. Le module utilise un contrôleur frontal pour l'exécution des tâches CRON, garantissant que les mises à jour des taux se produisent en dehors du contexte standard du Back Office, ce qui est idéal pour les tâches planifiées. Il adhère à l'architecture des modules PrestaShop, utilisant les méthodes `install()` et `uninstall()` pour la configuration et le nettoyage, et `getContent()` pour la configuration du Back Office.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    -   `controllers/front/cronjob.php`
        -   **Nom de la classe et classe parente** : `BocratesCronjobModuleFrontController` étendant `ModuleFrontController`.
        -   **Responsabilité** : Ce contrôleur est le point d'entrée pour la tâche CRON automatisée. Lorsqu'il est accédé via son URL unique (fournie dans la configuration du module), il déclenche la méthode `processUpdateExchangeRates()` au sein de la classe principale du module. Il est conçu pour être appelé en externe par un planificateur CRON côté serveur, et non directement par un utilisateur. Il affiche généralement un simple message de succès ou d'erreur.
    -   `controllers/front/index.php`
        -   **Nom de la classe et classe parente** : `BocratesIndexModuleFrontController` étendant `ModuleFrontController`.
        -   **Responsabilité** : Il s'agit d'un contrôleur frontal de remplacement ou par défaut. Dans de nombreux modules, si une action spécifique n'est pas définie, `index.php` peut être utilisé. Pour ce module, sa fonction principale est probablement de servir de solution de repli ou de s'assurer que le routage frontal du module est correctement établi, même s'il n'effectue pas d'action spécifique visible par l'utilisateur. Le `cronjob.php` est le contrôleur frontal actif pour la fonctionnalité.
-   **Contrôleurs d'administration Back-Office** :

    -   Aucun. Toute la configuration du Back Office est gérée directement dans la méthode `getContent()` du fichier principal du module `bocrates.php`.

### 4.3 Classes et modèles principaux (`classes/`)

-   Aucun. Le module interagit directement avec l'`ObjectModel` `Currency` et la classe `Configuration` de PrestaShop pour le stockage et la manipulation des données.

### 4.4 Actifs JavaScript (`views/js/`)

-   Aucun. Le module n'utilise pas de JavaScript personnalisé pour sa fonctionnalité.

### 4.5 Feuilles de style CSS (`views/css/`)

-   Aucun. Le module n'utilise pas de CSS personnalisé pour sa fonctionnalité.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles d'administration (`views/templates/admin/`)** :
    -   `bocrates/views/admin.tpl`
        -   **Objectif** : Ce modèle est rendu par la méthode `getContent()` du fichier principal du module `bocrates.php`. Il affiche le formulaire de configuration du module dans le Back Office de PrestaShop. Cela inclut le bouton de mise à jour manuelle, l'URL de la tâche CRON, le champ de saisie de la marge de taux de change et l'horodatage de la dernière mise à jour.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module ne crée pas de tables SQL personnalisées.
    -   Il stocke ses paramètres de configuration dans la table `ps_configuration` en utilisant des clés telles que :
        -   `BOCRATES_MARGIN` : Stocke la marge en pourcentage pour les taux de change.
        -   `BOCRATES_LAST_UPDATE` : Stocke l'horodatage de la dernière mise à jour réussie.
        -   `MYPRESTA_UPDATES`, `UPDATE_`, `UPDATEV_` : Liés au mécanisme de mise à jour de MyPresta.eu.
-   **Table des hooks enregistrés** :
    Le module fonctionne principalement en arrière-plan et n'enregistre pas de hooks pour l'affichage frontal. Sa fonctionnalité principale est déclenchée par le contrôleur frontal `cronjob`.

    | Nom du hook | Moment d'exécution | Objectif technique |
    | --- | --- | --- |
    | `actionModuleInstall` | Lors de l'installation du module | Définit les valeurs de configuration par défaut et enregistre les hooks nécessaires (le cas échéant). |
    | `actionModuleUninstall` | Lors de la désinstallation du module | Nettoie les valeurs de configuration. |
    | `displayBackOfficeHeader` | Rendu dans l'en-tête du Back Office | Potentiellement utilisé pour inclure des actifs ou afficher des notifications dans le panneau d'administration (bien qu'aucun actif spécifique ne soit listé). |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support technique dédié pour le module « Banque du Canada - taux de change », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour aider les marchands et les développeurs avec tout problème ou question concernant la fonctionnalité et l'intégration du module.
