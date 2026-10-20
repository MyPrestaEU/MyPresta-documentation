---
title: "CBR Currency Exchange & Rates (Banque de Russie) - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop CBR Currency Exchange & Rates (Banque de Russie) par MyPresta.eu."
sidebar:
  label: "CBR Currency Exchange & Rates (Banque de Russie) - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module CBR Currency Exchange & Rates (Bank of Russia) sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/cbr-currency-exchange-rates-bank-of-russia.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/cbr-currency-exchange-rates-bank-of-russia/)
>
> ---


# CBR Currency Exchange & Rates (Banque de Russie)

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour la communication API externe, qui sont courantes sur la plupart des environnements d'hébergement web.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après avoir installé le module, cliquez sur « Configurer » pour accéder à ses paramètres. C'est l'écran principal où vous gérerez tous les aspects du module CBR Currency Exchange & Rates.

#### **Paramètres généraux**

-   **Activer les mises à jour automatiques :**

    -   **Ce que fait ce paramètre :** Ce commutateur contrôle si le module vérifiera et appliquera automatiquement les nouveaux taux de change de la Banque Centrale de Russie.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (OUI) :* Le module récupérera périodiquement les derniers taux de change du site web de la CBR. Ceci est crucial pour maintenir la précision de vos prix en RUB sans intervention manuelle. Vous devrez configurer une tâche CRON (expliquée ci-dessous) pour que cela fonctionne.
        -   *Lorsqu'désactivé (NON) :* Le module ne mettra pas à jour les taux automatiquement. Vous devriez mettre à jour les taux manuellement si cette option est désactivée, ce qui va à l'encontre du but du module.
    -   **Valeur recommandée :** OUI
    -   **Scénario / exemple de marchand :** Vous voulez que vos prix en RUB reflètent toujours le taux de change officiel actuel sans avoir à vous connecter quotidiennement et à les mettre à jour. L'activation de cette option garantit que votre boutique est toujours à jour.
-   **Fréquence de mise à jour (en heures) :**

    -   **Ce que fait ce paramètre :** Définit la fréquence à laquelle le module doit tenter de récupérer de nouveaux taux de change de la CBR.
    -   **Effet de la modification de ce paramètre :**
        -   *Définir un nombre plus bas (par exemple, 1 heure) :* Les taux seront vérifiés et mis à jour plus fréquemment. C'est idéal si votre entreprise nécessite des conversions très précises, quasi en temps réel.
        -   *Définir un nombre plus élevé (par exemple, 24 heures) :* Les taux seront vérifiés moins fréquemment. Cela pourrait convenir si vos prix ne fluctuent pas de manière spectaculaire ou si vous préférez réduire la charge du serveur due à des appels externes fréquents.
    -   **Valeur recommandée :** 24 (Les mises à jour quotidiennes sont généralement suffisantes, car les taux CBR changent une fois par jour).
    -   **Scénario / exemple de marchand :** Vous voulez vous assurer que vos prix en RUB sont mis à jour quotidiennement, vous définissez donc cela à 24 heures. Si vous vendez des articles de grande valeur avec des marges serrées, vous pourriez le définir à 12 heures pour capturer les changements de milieu de journée si la CBR les publie (bien que ce soit généralement une fois par jour).
-   **Marge sur le taux de change (%) :**

    -   **Ce que fait ce paramètre :** Vous permet d'ajouter une marge en pourcentage en plus du taux de change officiel de la CBR. Cela peut être utilisé pour couvrir les frais de transaction, les coûts de conversion de devises ou pour ajuster légèrement votre stratégie de prix.
    -   **Effet de la modification de ce paramètre :**
        -   *Définir une valeur positive (par exemple, 2) :* Le module augmentera le taux de change calculé de 2 %. Cela signifie que pour chaque unité de votre devise de base, vous obtiendrez légèrement plus de RUB, augmentant ainsi vos prix en RUB.
        -   *Définir 0 ou laisser vide :* Le module utilisera le taux de change officiel exact de la CBR sans aucun ajustement.
        -   *Définir une valeur négative (par exemple, -1) :* Le module diminuera le taux de change calculé de 1 %. Cela signifie que vous obtiendrez légèrement moins de RUB pour chaque unité de votre devise de base, diminuant ainsi vos prix en RUB.
    -   **Valeur recommandée :** 0 (Sauf si vous avez des raisons commerciales spécifiques d'ajouter une marge).
    -   **Scénario / exemple de marchand :** Votre passerelle de paiement facture des frais de 1,5 % pour la conversion du RUB vers votre devise de base. Vous pouvez définir une marge de 1,5 % ici pour compenser ce coût et maintenir vos marges bénéficiaires.
-   **URL de la tâche CRON :**

    -   **Ce que fait ce paramètre :** Affiche l'URL unique que vous devez configurer comme tâche CRON sur votre serveur d'hébergement. Lorsque cette URL est accédée, elle déclenche le module pour récupérer et mettre à jour les taux de change.
    -   **Effet de la modification de ce paramètre :** Ce n'est pas un paramètre que vous modifiez, mais plutôt une URL que vous *utilisez*.
        -   *Lorsqu'elle est correctement configurée comme tâche CRON :* Le module s'exécutera automatiquement en arrière-plan à la fréquence spécifiée (basée sur le paramètre « Fréquence de mise à jour ») pour mettre à jour les taux.
        -   *Si elle n'est pas configurée comme tâche CRON :* Les mises à jour automatiques ne se produiront pas, même si « Activer les mises à jour automatiques » est défini sur OUI.
    -   **Valeur recommandée :** Copiez cette URL et configurez-la comme tâche CRON sur votre serveur.
    -   **Scénario / exemple de marchand :** Après avoir configuré le module, vous copiez cette URL et l'ajoutez au planificateur de tâches CRON de votre panneau de contrôle d'hébergement pour qu'elle s'exécute quotidiennement à 3h du matin, garantissant que les taux sont mis à jour avant le début de votre journée de travail.

#### **Paramètres de devise**

-   **Devise à mettre à jour :**
    -   **Ce que fait ce paramètre :** Ce menu déroulant vous permet de sélectionner la devise spécifique de votre boutique PrestaShop qui doit être mise à jour avec les taux CBR. Il listera toutes les devises que vous avez activées dans votre Back Office PrestaShop.
    -   **Effet de la modification de ce paramètre :**
        -   *Sélectionner « Rouble Russe (RUB) » :* Le module ciblera et mettra à jour spécifiquement le taux de change du Rouble Russe par rapport à la devise de base de votre boutique en utilisant les données CBR.
        -   *Sélectionner toute autre devise :* Ce module est spécifiquement conçu pour les taux CBR, qui sont pour le Rouble Russe. Sélectionner une autre devise pourrait entraîner un comportement inattendu ou aucune mise à jour pour cette devise.
    -   **Valeur recommandée :** Rouble Russe (RUB)
    -   **Scénario / exemple de marchand :** La devise de base de votre boutique est l'EUR, et vous voulez vous assurer que lorsque les clients sélectionnent le RUB, la conversion de l'EUR au RUB est précise selon la CBR. Vous sélectionnez « Rouble Russe (RUB) » ici.

#### **Bouton Enregistrer**

-   **Enregistrer :**
    -   **Ce que cela fait :** Applique toutes les modifications que vous avez apportées sur la page de configuration.
    -   **Effet du clic :** Vos paramètres seront stockés dans la base de données, et le module fonctionnera selon les nouveaux paramètres.
    -   **Action recommandée :** Cliquez toujours sur « Enregistrer » après avoir effectué des modifications.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer les mises à jour automatiques | OUI | Contrôle la récupération automatique des taux CBR. OUI pour des mises à jour sans intervention. |
| Configuration du module | Fréquence de mise à jour (en heures) | 24 | Fréquence à laquelle la tâche CRON doit déclencher les mises à jour des taux. 24 pour quotidien. |
| Configuration du module | Marge sur le taux de change (%) | 0 | Ajoute un pourcentage au taux officiel. À utiliser pour les frais ou la stratégie de prix. |
| Configuration du module | URL de la tâche CRON | (URL unique) | URL à configurer sur votre serveur pour les mises à jour automatisées. |
| Configuration du module | Devise à mettre à jour | Rouble Russe (RUB) | Spécifie la devise PrestaShop à mettre à jour avec les taux CBR. Doit être RUB. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes prix en RUB ne se mettent pas à jour automatiquement. Que dois-je vérifier ?**
R1 :

-   **Le paramètre « Activer les mises à jour automatiques » est-il défini sur OUI ?** Vérifiez la configuration du module.
-   **Avez-vous configuré la tâche CRON sur votre serveur d'hébergement ?** C'est la raison la plus courante. Copiez l'« URL de la tâche CRON » de la configuration du module et ajoutez-la au planificateur CRON de votre panneau d'hébergement. Assurez-vous qu'elle est configurée pour s'exécuter au moins aussi fréquemment que votre paramètre « Fréquence de mise à jour ».
-   **La « Devise à mettre à jour » est-elle définie sur « Rouble Russe (RUB) » ?** Le module est conçu pour le RUB.
-   **Vérifiez les journaux de tâches CRON de votre serveur (si disponibles) :** Votre hébergeur peut proposer des journaux qui indiquent si la tâche CRON s'exécute et si elle a rencontré des erreurs.
-   **Videz le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » pour vous assurer que votre boutique affiche les dernières données.

**Q2 : Le taux de change semble incorrect ou n'a pas changé depuis un certain temps.**
R2 :

-   **Vérifiez le taux officiel de la CBR :** Consultez le site web officiel de la Banque Centrale de Russie pour le taux de change du jour afin de confirmer ce qu'il devrait être.
-   **Vérifiez votre « Fréquence de mise à jour » :** Si elle est définie sur 24 heures, elle ne se mettra à jour qu'une fois par jour.
-   **Jours fériés bancaires :** La CBR ne met pas à jour les taux les jours fériés bancaires. Le module utilise intelligemment le dernier taux disponible. S'il y a une longue période de vacances, le taux peut rester statique pendant plusieurs jours.
-   **Problèmes de tâche CRON :** Reportez-vous à la Q1 pour le dépannage des tâches CRON.

**Q3 : Puis-je utiliser ce module pour d'autres devises que le RUB ?**
R3 : Non, ce module est spécifiquement conçu pour s'intégrer aux données de taux de change de la Banque Centrale de Russie, qui concernent principalement le Rouble Russe. Il ne mettra à jour avec précision que la devise RUB dans votre boutique.

**Q4 : J'ai changé de thème, et maintenant les prix semblent étranges en RUB.**
R4 : Ce module ne gère que la *valeur* de la conversion de devise. L'*affichage* des prix (polices, couleurs, mise en page) est géré par votre thème PrestaShop. Si les prix semblent étranges après un changement de thème, il s'agit probablement d'un problème de CSS ou de modèle avec votre nouveau thème, et non du module lui-même. Vous devrez peut-être ajuster le style de votre thème.

**Q5 : Comment puis-je mettre à jour manuellement les taux si nécessaire ?**
R5 : Bien que le module soit conçu pour les mises à jour automatiques, vous pouvez forcer une mise à jour en visitant manuellement l'URL de la tâche CRON dans votre navigateur web. Cela déclenchera le processus de mise à jour une fois. N'oubliez pas de vider votre cache PrestaShop par la suite.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module CBR Currency Exchange & Rates.

### 4.1 Aperçu de l'architecture

Le module `cbrrates` suit une architecture de module PrestaShop standard, utilisant principalement la classe `Module` pour sa fonctionnalité principale et sa configuration. Il utilise des contrôleurs frontaux pour l'exécution des tâches CRON et une simple méthode `getContent()` pour la configuration du back-office. Le module récupère les données XML de l'API CBR, les analyse et met à jour les taux de change de la `Currency` de PrestaShop.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    -   `controllers/front/cronjob.php`
        -   **Nom de la classe et classe parente** : `CbrratesCronjobModuleFrontController` étendant `ModuleFrontController`.
        -   **Responsabilité** : Ce contrôleur est conçu pour être appelé par une tâche CRON externe. Lorsqu'il est accédé, il initie le processus de mise à jour des taux de change. Il vérifie les valeurs de configuration `update_` et `updatev_` pour déterminer si une mise à jour est due en fonction de la fréquence configurée. Il appelle ensuite la logique principale du module pour récupérer et appliquer les derniers taux CBR. Il affiche un simple message de succès ou d'erreur.
    -   `controllers/front/index.php`
        -   **Nom de la classe et classe parente** : `CbrratesIndexModuleFrontController` étendant `ModuleFrontController`.
        -   **Responsabilité** : Il s'agit d'un contrôleur frontal de remplacement ou par défaut. Dans de nombreux modules, si aucune action spécifique n'est définie, `index.php` peut servir de solution de repli ou simplement rediriger. Pour `cbrrates`, sa fonction principale est probablement minimale, car l'interaction principale du front-office se fait via `cronjob.php`. Il peut être présent pour s'assurer qu'une route front-office valide existe pour le module, même s'il n'est pas activement utilisé pour l'affichage.
-   **Contrôleurs d'administration Back-Office** :

    -   Aucun contrôleur d'administration dédié n'est présent dans ce module. Toute la configuration du back-office est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

Aucune classe personnalisée ou définition d'`ObjectModel` n'est présente dans le répertoire `classes/` pour ce module. Toute la logique principale réside dans le fichier `cbrrates.php`.

### 4.4 Actifs JavaScript (`views/js/`)

Aucun fichier JavaScript personnalisé n'est présent dans le module.

### 4.5 Feuilles de style CSS (`views/css/`)

Aucun fichier CSS personnalisé n'est présent dans le module.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles d'administration (`views/templates/admin/`)** :
    -   `cbrrates/views/admin.tpl`
        -   **Objectif** : Ce modèle est rendu par la méthode `getContent()` dans `cbrrates.php` pour afficher le formulaire de configuration du module dans le Back Office de PrestaShop.
        -   **Contenu** : Il contient généralement la structure HTML pour les champs de saisie, les commutateurs et les boutons pour des paramètres tels que `mypresta_updates`, `update_`, `updatev_`, `currency_`, et l'affichage de l'URL de la tâche CRON. Il utilise les assistants de formulaire et le style standard de PrestaShop.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module ne crée aucune table SQL personnalisée.
    -   Il stocke ses paramètres de configuration dans la table `ps_configuration` (ou `_configuration` selon le préfixe).
        -   `PS_CBRRATES_UPDATE_ENABLED` : Booléen (0/1) pour « Activer les mises à jour automatiques ».
        -   `PS_CBRRATES_UPDATE_FREQUENCY` : Entier pour « Fréquence de mise à jour (en heures) ».
        -   `PS_CBRRATES_MARGIN` : Flottant pour « Marge sur le taux de change (%) ».
        -   `PS_CBRRATES_CURRENCY_ID` : Entier, ID de la devise PrestaShop à mettre à jour (par exemple, ID pour RUB).
        -   `PS_CBRRATES_LAST_UPDATE` : Horodatage de la dernière mise à jour réussie.
        -   `PS_CBRRATES_CRON_TOKEN` : Une chaîne unique utilisée dans l'URL de la tâche CRON pour la sécurité.
-   **Table des hooks enregistrés** :
    Le module n'enregistre pas explicitement de hooks pour l'affichage en front-office (par exemple, `displayHeader`, `displayFooter`). Son interaction principale avec le cœur de PrestaShop se fait via le hook `actionUpdateCurrency` (implicitement, en mettant à jour les taux de devise) et son propre mécanisme CRON interne.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionUpdateCurrency` | Déclenché lorsqu'une devise est mise à jour (implicitement par ce module) | Non explicitement enregistré par le module, mais la fonction principale du module est de mettre à jour les taux de devise, ce qui peut déclencher ce hook PrestaShop principal. |
| (CRON interne) | Via `controllers/front/cronjob.php` | Déclenche la récupération et la mise à jour des taux de change CBR en fonction de la fréquence configurée. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « CBR Currency Exchange & Rates (Banque de Russie) », veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
