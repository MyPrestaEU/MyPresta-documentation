---
title: "Banque d'Italie (Banca d'Italia) - taux de change - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Banque d'Italie (Banca d'Italia) - taux de change par MyPresta.eu."
sidebar:
  label: "Banque d'Italie (Banca d'Italia) - taux de change - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Bank of Italy (Banca dItalia) - currency exchange rates sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-italy-banca-ditalia-currency-exchange-rates.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/bank-of-italy-banca-ditalia-currency-exchange-rates/)
>
> ---


# Banque d'Italie (Banca d'Italia) - taux de change

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour la communication API externe, et sont presque universellement disponibles sur les environnements d'hébergement modernes.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur le bouton « Configurer » à côté du nom du module dans le Gestionnaire de modules. Cela vous mènera à l'écran de configuration principal du module « Banque d'Italie (Banca d'Italia) - taux de change ».

#### Paramètres généraux

-   **Ce que fait ce paramètre :** Cette section vous permet de contrôler la manière dont le module met à jour vos taux de change et de gérer ses fonctionnalités principales.
-   **Effet de la modification de ce paramètre :** Ces paramètres ont un impact direct sur la précision et la fréquence des taux de change de votre boutique.

#### Paramètres et options spécifiques :

1.  **Bouton « Mettre à jour les taux »**

    *   **Ce que fait ce paramètre :** Il s'agit d'un déclencheur manuel pour récupérer immédiatement les derniers taux de change auprès de la Banque d'Italie et les appliquer aux devises de votre boutique.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est cliqué :* Le module se connectera à la source de données de la Banque d'Italie, récupérera les taux de référence Euro les plus récents et mettra à jour toutes les devises actives dans votre boutique PrestaShop (à l'exception de votre devise par défaut, qui est généralement l'EUR). Ceci est utile pour les tests ou pour une mise à jour immédiate en dehors de vos tâches cron planifiées.
    *   **Valeur recommandée :** Cliquez sur ce bouton après la configuration initiale pour vous assurer que vos taux sont à jour. Utilisez-le manuellement chaque fois que vous avez besoin d'une mise à jour immédiate.
    *   **Scénario / exemple pour le marchand :** Vous venez d'ajouter une nouvelle devise à votre boutique, ou il y a eu une fluctuation importante du marché, et vous voulez vous assurer que vos prix sont instantanément mis à jour avant une vente majeure.
2.  **Champ « URL CRON pour les mises à jour automatiques »**

    *   **Ce que fait ce paramètre :** Ce champ affiche une URL unique que vous pouvez utiliser avec le service de « tâche cron » de votre hébergeur. Une tâche cron est une tâche planifiée qui s'exécute automatiquement à des intervalles spécifiés (par exemple, une fois par jour, toutes les heures).
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est configuré avec votre hébergeur :* Les taux de change de votre boutique seront automatiquement mis à jour à la fréquence que vous définissez dans les paramètres de votre tâche cron, sans que vous ayez besoin de cliquer manuellement sur des boutons. Cela garantit que vos taux sont toujours à jour.
        *   *Lorsqu'il n'est pas configuré :* Vous devrez cliquer manuellement sur le bouton « Mettre à jour les taux » pour actualiser vos taux de change.
    *   **Valeur recommandée :** Copiez cette URL et configurez une tâche cron sur votre serveur pour qu'elle s'exécute au moins une fois toutes les 24 heures. Une mise à jour quotidienne est généralement suffisante pour la plupart des boutiques e-commerce.
    *   **Scénario / exemple pour le marchand :** Vous souhaitez que les taux de change de votre boutique soient mis à jour tous les matins à 3h du matin, garantissant que tous les prix sont à jour pour le début de la journée de travail, sans que vous ayez à vous en souvenir.
3.  **Champ « Ajouter une marge aux taux de change (%) »**

    *   **Ce que fait ce paramètre :** Cela vous permet d'ajouter une marge en pourcentage aux taux de change récupérés. Par exemple, si le taux officiel est de 1 EUR = 1,10 USD, et que vous définissez une marge de 2 %, le module utilisera 1 EUR = 1,078 USD (1,10 \* 0,98) ou 1 EUR = 1,122 USD (1,10 \* 1,02) selon le sens de la conversion. Cela aide à couvrir les frais de transaction potentiels, les coûts de conversion de devises, ou simplement à vous donner une légère marge de manœuvre.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur une valeur positive (par exemple, 2) :* Le module ajustera les taux de change récupérés de ce pourcentage. Cela signifie généralement que vous obtiendrez un peu plus de devise locale pour vos produits basés en Euro, ou un peu moins d'Euros pour les produits en devise locale, ce qui contribue à protéger vos marges bénéficiaires.
        *   *Lorsqu'il est défini sur 0 (ou vide) :* Le module utilisera les taux de change exacts fournis par la Banque d'Italie sans aucun ajustement.
    *   **Valeur recommandée :** Commencez par 0. Si vous rencontrez des problèmes de rentabilité en raison des fluctuations de devises ou des frais de transaction, envisagez d'ajouter une petite marge (par exemple, 1 à 3 %).
    *   **Scénario / exemple pour le marchand :** Votre passerelle de paiement facture des frais de 1,5 % pour les transactions internationales. En définissant une marge de 2 %, vous pouvez absorber ce coût et vous assurer que votre rentabilité n'est pas érodée par les conversions de devises.
4.  **Commutateur « Vérifier les mises à jour du module »**

    *   **Ce que fait ce paramètre :** Ce bouton contrôle si le module vérifie périodiquement MyPresta.eu pour les nouvelles versions du module.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé (OUI) :* Le module se connectera occasionnellement à MyPresta.eu pour voir si une nouvelle version est disponible. Si une mise à jour est trouvée, vous verrez une notification dans votre back office PrestaShop, vous invitant à télécharger et installer la dernière version. Cela vous aide à rester à jour avec les corrections de bugs, les nouvelles fonctionnalités et les mises à jour de compatibilité.
        *   *Lorsqu'il est désactivé (NON) :* Le module ne vérifiera pas les mises à jour, et vous ne serez pas informé des nouvelles versions. Vous devrez vérifier manuellement votre compte MyPresta.eu pour les mises à jour.
    *   **Valeur recommandée :** **OUI**. Maintenir vos modules à jour est crucial pour la sécurité, les performances et la compatibilité avec les futures versions de PrestaShop.
    *   **Scénario / exemple pour le marchand :** Vous souhaitez être informé automatiquement lorsqu'une nouvelle version du module est publiée, afin de pouvoir bénéficier des dernières améliorations et vous assurer que votre boutique reste sécurisée et fonctionnelle.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Bouton « Mettre à jour les taux » | Cliquer après la configuration / manuellement si nécessaire | Récupère et applique immédiatement les derniers taux de change de la Banque d'Italie. |
| Page de configuration du module | « URL CRON pour les mises à jour automatiques » | Copier et configurer sur l'hébergement | Automatise les mises à jour quotidiennes/horaires des taux de change, assurant une précision constante. |
| Page de configuration du module | « Ajouter une marge aux taux de change (%) » | 0 (ou 1-3% si nécessaire) | Ajoute une marge en pourcentage aux taux de change pour couvrir les frais ou protéger les marges bénéficiaires. |
| Page de configuration du module | « Vérifier les mises à jour du module » | OUI | Vous informe des nouvelles versions du module pour les corrections de bugs, les fonctionnalités et la compatibilité. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes taux de change ne se mettent pas à jour automatiquement. Que dois-je faire ?**
R1 : Cela est presque toujours lié à la configuration de la tâche cron.
- **Vérifiez votre hébergement :** Connectez-vous à votre panneau de contrôle d'hébergement (cPanel, Plesk, etc.) et vérifiez que la tâche cron pour l'URL du module est correctement configurée et s'exécute aux intervalles spécifiés. Assurez-vous que l'URL copiée depuis la configuration du module est exacte.
- **Testez l'URL manuellement :** Copiez l'« URL CRON pour les mises à jour automatiques » depuis la configuration du module et collez-la directement dans votre navigateur web. Si elle s'exécute avec succès, vous devriez voir un simple message « OK » ou similaire. Si vous voyez une erreur, il peut y avoir un problème côté serveur ou un problème avec l'URL elle-même.
- **Vérifiez l'état du module :** Assurez-vous que le module est activé dans votre back office PrestaShop.

**Q2 : J'ai cliqué sur « Mettre à jour les taux » mais mes prix dans d'autres devises n'ont pas changé.**
R2 :
- **Videz le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** dans votre back office PrestaShop et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures). PrestaShop met souvent en cache les conversions de devises.
- **Vérifiez les devises actives :** Assurez-vous que les devises que vous vous attendez à voir mises à jour sont bien activées dans **International > Devises**. Le module ne met à jour que les devises actives.
- **Vérifiez la devise par défaut :** Le module met à jour les *autres* devises par rapport à votre devise par défaut (généralement l'EUR). Si votre devise par défaut n'est pas l'EUR, le module récupérera toujours les taux EUR et effectuera la conversion à partir de là. Assurez-vous que votre devise par défaut est correctement définie.

**Q3 : Puis-je définir des marges différentes pour différentes devises ?**
R3 : Non, le paramètre « Ajouter une marge aux taux de change (%) » applique une marge en pourcentage unique et uniforme à *tous* les taux de change récupérés par le module. Si vous avez besoin de marges très spécifiques par devise, vous auriez besoin d'une solution de développement personnalisée ou d'un module de gestion de devises plus avancé.

**Q4 : Le module indique qu'il récupère les taux de la Banca d'Italia. Est-ce fiable ?**
R4 : Oui, la Banca d'Italia (Banque d'Italie) est une banque centrale au sein du Système européen de banques centrales (SEBC) et fournit les taux de référence officiels de l'Euro. Ces taux sont très fiables et largement utilisés pour les transactions financières à travers l'Europe.

**Q5 : Après la mise à jour du module, ma boutique semble un peu étrange ou je vois des erreurs.**
R5 :
- **Videz le cache :** Videz toujours le cache de votre PrestaShop (**Paramètres avancés > Performances**) après toute mise à jour de module.
- **Cache du navigateur :** Videz le cache et les cookies de votre navigateur web, ou essayez d'accéder à votre boutique en mode incognito/privé.
- **Revenir en arrière (si nécessaire) :** Si le problème persiste, vous devrez peut-être désactiver ou désinstaller temporairement le module et revenir à une sauvegarde précédente de votre boutique. Ensuite, contactez le support MyPresta.eu avec les détails du problème.

## 4. Guide pour les développeurs et webmasters (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, webmasters de boutiques et agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Banque d'Italie (Banca d'Italia) - taux de change » (`birates`) est un module PrestaShop léger conçu pour automatiser les mises à jour des taux de change. Il suit un modèle MVC PrestaShop standard lorsque cela est applicable, se concentrant principalement sur une interface de configuration unique et un contrôleur frontal pour l'exécution des tâches cron. Il utilise l'`ObjectModel` `Currency` de PrestaShop pour mettre à jour les taux de change. La logique principale réside dans le fichier principal du module, gérant l'installation, la désinstallation, la configuration et le processus de récupération des taux.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    *   `controllers/front/cronjob.php`
        *   **Nom de classe et classe parente** : `BiratesCronjobModuleFrontController` étend `ModuleFrontController`.
        *   **Responsabilité** : Ce contrôleur est conçu pour être appelé par une tâche cron externe. Sa méthode `initContent()` (ou une logique similaire dans `postProcess()`) déclenche la méthode `updateRates()` du module principal `birates`. Il ne rend aucun contenu visuel à l'utilisateur ; son but est purement d'exécuter la logique de mise à jour des taux en arrière-plan. Il affiche généralement un simple message de succès ou un statut.
    *   `controllers/front/index.php`
        *   **Nom de classe et classe parente** : `BiratesIndexModuleFrontController` étend `ModuleFrontController`.
        *   **Responsabilité** : Il s'agit d'un contrôleur frontal de substitution ou de secours. Dans de nombreux modules, les contrôleurs `index.php` sont utilisés pour définir une route par défaut ou gérer les cas où une action spécifique n'est pas fournie. Pour ce module, il sert probablement de point d'entrée de base, mais la fonctionnalité principale de mise à jour des taux est gérée par `cronjob.php`. Il peut rediriger ou simplement afficher une page minimale.
-   **Contrôleurs d'administration Back-Office** :

    *   Aucun contrôleur d'administration dédié n'est présent dans ce module. Toute la configuration du back-office est gérée directement dans la méthode `getContent()` du fichier principal du module `birates.php`.

### 4.3 Classes et modèles principaux (`classes/`)

Aucune classe personnalisée ou définition d'`ObjectModel` n'est présente dans le répertoire `classes/`. Le module interagit directement avec l'`ObjectModel` `Currency` de PrestaShop pour mettre à jour les taux de change des devises existantes.

### 4.4 Actifs JavaScript (`views/js/`)

Aucun fichier JavaScript personnalisé n'est présent dans le module.

### 4.5 Feuilles de style CSS (`views/css/`)

Aucun fichier CSS personnalisé n'est présent dans le module.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates d'administration (`views/templates/admin/`)** :

    *   `birates/views/admin.tpl`
        *   **Objectif** : Ce template est rendu par la méthode `getContent()` du fichier principal du module `birates.php`. Il affiche l'intégralité du formulaire de configuration du module dans le back office de PrestaShop.
        *   **Contenu** : Il inclut le bouton « Mettre à jour les taux », le champ URL CRON, le champ de saisie « Ajouter une marge aux taux de change (%) » et le commutateur « Vérifier les mises à jour du module ». Il utilise les assistants de formulaire et le style standard de PrestaShop.
-   **Templates de hook (`views/templates/hook/`)** : Aucun.
-   **Templates front-office (`views/templates/front/`)** : Aucun.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    *   Le module ne crée aucune table SQL personnalisée.
    *   Il stocke ses paramètres de configuration (par exemple, `mypresta_updates`, `update_`, `updatev_`, `currency_`) dans la table `ps_configuration` (ou `_configuration` selon votre préfixe de table). Ces clés sont généralement préfixées par le nom du module ou un identifiant unique.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Non utilisé directement pour la sortie visuelle, mais pourrait être utilisé pour charger des ressources (bien qu'il n'y en ait aucune). |
| `displayRightColumn` | Dans la colonne de droite des pages du front-office. | Non utilisé pour la sortie visuelle. |
| `displayLeftColumn` | Dans la colonne de gauche des pages du front-office. | Non utilisé pour la sortie visuelle. |
| `displayFooter` | En bas de chaque page du front-office. | Non utilisé pour la sortie visuelle. |
| `displayProductExtraContent` | Sur la page produit, généralement sous les informations principales du produit. | Non utilisé pour la sortie visuelle. |
| `actionUpdateCurrency` | Après la mise à jour d'une devise. | Le module *déclenche* lui-même les mises à jour de devises, mais ne s'y connecte pas explicitement pour sa propre logique. |
| `actionModuleInstall` | Lors de l'installation du module. | Utilisé pour définir les valeurs de configuration par défaut et enregistrer les hooks. |
| `actionModuleUninstall` | Lors de la désinstallation du module. | Utilisé pour nettoyer les valeurs de configuration et désenregistrer les hooks. |

*Note : La fonction principale du module (mise à jour des taux) est initiée par son contrôleur frontal `cronjob.php`, qui est appelé en externe, plutôt que par un hook PrestaShop standard.*

## 5. Support officiel et mises à jour

Pour un support officiel, des mises à jour et pour télécharger la dernière version du module « Banque d'Italie (Banca d'Italia) - taux de change », veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la configuration du module.
