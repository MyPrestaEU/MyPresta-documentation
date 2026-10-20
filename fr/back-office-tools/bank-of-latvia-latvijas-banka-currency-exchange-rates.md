---
title: "Banque de Lettonie (Latvijas Banka) - taux de change - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Banque de Lettonie (Latvijas Banka) - taux de change par MyPresta.eu."
sidebar:
  label: "Banque de Lettonie (Latvijas Banka) - taux de change - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Bank of Latvia (Latvijas Banka) - currency exchange rates sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-latvia-latvijas-banka-currency-exchange-rates.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/bank-of-latvia-latvijas-banka-currency-exchange-rates/)
>
> ---


# Banque de Lettonie (Latvijas Banka) - taux de change

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour la récupération de données externes, et sont presque universellement disponibles sur les environnements d'hébergement modernes.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » pour accéder à la page des paramètres principaux du module. C'est ici que vous définirez comment le module récupère et applique les taux de change.

La page de configuration du module « Banque de Lettonie (Latvijas Banka) - taux de change » est simple et conçue pour vous permettre de démarrer rapidement.

**Capture d'écran de la page de configuration (exemple) :**
*(Imaginez une capture d'écran ici montrant la page de configuration du module avec des champs pour « URL CRON », « Marge », « Fréquence de mise à jour » et un interrupteur « Activé/Désactivé »)*

#### 2.1.1 URL CRON

-   **Ce que fait ce paramètre :** Il s'agit d'une adresse web unique (URL) qui, lorsqu'elle est visitée, déclenche le module pour récupérer les derniers taux de change auprès de la Banque de Lettonie et les mettre à jour dans votre boutique PrestaShop. Il est conçu pour être appelé automatiquement par une « tâche cron » sur votre serveur.
-   **Effet de la modification de ce paramètre :** Vous ne pouvez pas modifier cette URL directement. Elle est générée par le module. Copier cette URL est essentiel pour configurer les mises à jour automatisées. Si vous ne configurez pas de tâche cron en utilisant cette URL, les taux de change ne seront pas mis à jour automatiquement.
-   **Valeur recommandée :** Copiez cette URL exactement telle qu'elle apparaît.
-   **Scénario / exemple de marchand :** Vous copierez cette URL et la collerez dans la section « Tâches Cron » de votre panneau de contrôle d'hébergement (par exemple, cPanel, Plesk ou une interface similaire) pour planifier des mises à jour quotidiennes.

#### 2.1.2 Marge (%)

-   **Ce que fait ce paramètre :** Cela vous permet d'ajouter un « tampon » ou une marge en pourcentage aux taux de change officiels. Lorsque le module récupère un taux, il l'augmentera de ce pourcentage avant de l'enregistrer dans votre boutique. Cela aide à protéger vos marges bénéficiaires contre les fluctuations monétaires et les frais de transaction.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsque défini sur 0 :* Le module utilisera les taux de change exacts fournis par la Banque de Lettonie. Vos prix refléteront directement les taux officiels.
    -   *Lorsque défini sur une valeur positive (par exemple, 2 %) :* Les taux de change dans votre boutique seront 2 % plus élevés que les taux officiels. Cela signifie que si un produit coûte 100 EUR et que le taux officiel vers l'USD est de 1,10, avec une marge de 2 %, le module utilisera un taux de 1,122 (1,10 \* 1,02), ce qui portera le prix en USD à 112,20.
-   **Valeur recommandée :** Cela dépend de votre modèle commercial, des frais de passerelle de paiement et des marges bénéficiaires souhaitées. Un point de départ courant pourrait être de 0,5 % à 2 % pour couvrir les coûts de transaction et les fluctuations mineures.
-   **Scénario / exemple de marchand :** Si votre processeur de paiement facture des frais de 1 % pour les transactions internationales, la définition d'une marge de 1,5 % pourrait vous aider à absorber ce coût et à maintenir votre marge bénéficiaire souhaitée.

#### 2.1.3 Fréquence de mise à jour

-   **Ce que fait ce paramètre :** Ce paramètre détermine la fréquence à laquelle le module *devrait* tenter de mettre à jour les taux de change. Bien que la tâche cron (voir URL CRON) soit ce qui déclenche réellement la mise à jour, ce paramètre agit comme une protection pour éviter des mises à jour trop fréquentes, ce qui pourrait être inutile voire problématique pour certains environnements d'hébergement.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsque défini sur « Quotidien » :* Le module ne traitera une mise à jour qu'une fois toutes les 24 heures, même si la tâche cron s'exécute plus fréquemment.
    -   *Lorsque défini sur « Horaire » :* Le module traitera une mise à jour une fois par heure.
    -   *Lorsque défini sur « Toutes les 15 minutes » :* Le module traitera une mise à jour toutes les 15 minutes.
-   **Valeur recommandée :** « Quotidien » est généralement suffisant pour la plupart des boutiques e-commerce, car les taux de change officiels ne fluctuent généralement pas de manière drastique en quelques minutes. Si vous avez des articles de très grande valeur ou opérez sur des marchés extrêmement volatils, « Horaire » pourrait être envisagé.
-   **Scénario / exemple de marchand :** Vous configurez votre tâche cron pour qu'elle s'exécute toutes les 6 heures, mais vous définissez la « Fréquence de mise à jour » ici sur « Quotidien ». Le module n'effectuera une mise à jour réelle des taux qu'une fois par période de 24 heures, même si la tâche cron tente de la déclencher plus souvent. Cela évite les appels API et l'utilisation de ressources inutiles.

#### 2.1.4 Activer le module

-   **Ce que fait ce paramètre :** Il s'agit d'un simple interrupteur marche/arrêt pour la fonctionnalité principale du module.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsque activé (OUI) :* Le module récupérera et mettra à jour activement les taux de change selon vos paramètres et le calendrier de la tâche cron.
    -   *Lorsque désactivé (NON) :* Le module cessera de récupérer et de mettre à jour les taux de change. Votre boutique continuera d'utiliser les derniers taux connus, ou le comportement par défaut de PrestaShop pour les mises à jour de taux si vous avez d'autres mécanismes en place.
-   **Valeur recommandée :** « OUI » pour garantir les mises à jour automatiques des devises.
-   **Scénario / exemple de marchand :** Vous pourriez désactiver temporairement le module si vous devez effectuer une maintenance sur votre boutique ou si vous décidez de gérer les taux de change manuellement pendant une courte période. N'oubliez pas de le réactiver par la suite.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue         | Paramètre / Option      | Par défaut / Recommandé       | Objectif et impact                                                                                             |
| :------------------ | :---------------------- | :---------------------------- | :------------------------------------------------------------------------------------------------------------- |
| Configuration module | URL CRON                | Copier exactement             | URL pour déclencher les mises à jour des taux via une tâche cron du serveur. Essentiel pour l'automatisation. |
| Configuration module | Marge (%)               | 0 % - 2 % (dépend du commerce) | Ajoute une marge en pourcentage aux taux de change récupérés pour protéger les bénéfices.                       |
| Configuration module | Fréquence de mise à jour | Quotidien                     | Contrôle la fréquence à laquelle le module *traite réellement* une mise à jour, même si la tâche cron s'exécute plus souvent. |
| Configuration module | Activer le module       | OUI                           | Active ou désactive la fonctionnalité de mise à jour des taux du module.                                       |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes taux de change ne se mettent pas à jour. Que dois-je faire ?**
R :

1.  **Vérifiez votre tâche Cron :** La raison la plus courante est une tâche cron mal configurée ou manquante sur votre serveur d'hébergement. Vérifiez que vous avez copié l'URL CRON exacte depuis la page de configuration du module et que votre tâche cron est planifiée pour s'exécuter.
2.  **Module activé ?** Assurez-vous que l'interrupteur « Activer le module » sur la page de configuration est réglé sur « OUI ».
3.  **Fréquence de mise à jour :** Vérifiez le paramètre « Fréquence de mise à jour ». Si votre tâche cron s'exécute toutes les heures mais que la fréquence est réglée sur « Quotidien », elle ne se mettra à jour qu'une fois par jour.
4.  **Cache PrestaShop :** Parfois, vider votre cache PrestaShop (sous **Paramètres avancés > Performances**) peut aider à rafraîchir les données affichées, bien que cela soit moins susceptible d'affecter les mises à jour des taux en arrière-plan.

**Q : Puis-je remplacer manuellement un taux de change après que le module l'ait mis à jour ?**
R : Oui, vous le pouvez. Le module met à jour les taux dans le système de gestion des devises standard de PrestaShop. Si vous allez dans **International > Devises** dans votre Back Office, vous pouvez modifier manuellement le taux de change pour n'importe quelle devise. Cependant, sachez que le module écrasera vos modifications manuelles la prochaine fois que la tâche cron s'exécutera et déclenchera une mise à jour.

**Q : Que se passe-t-il si le service de la Banque de Lettonie est temporairement indisponible ?**
R : Le module est conçu pour récupérer les taux d'une source externe. Si le service de la Banque de Lettonie est en panne ou inaccessible, le module ne parviendra probablement pas à récupérer de nouveaux taux. Dans de tels cas, votre boutique continuera d'utiliser les *derniers taux de change mis à jour avec succès*. Elle ne reviendra pas à des taux par défaut ou incorrects. Une fois le service restauré, la prochaine exécution de la tâche cron mettra à jour les taux à nouveau.

**Q : Ce module crée-t-il de nouvelles devises dans ma boutique ?**
R : Non, ce module ne met à jour que les taux de change des devises que vous avez *déjà activées* dans votre boutique PrestaShop (sous **International > Devises**). Vous devez d'abord ajouter et activer les devises souhaitées dans les paramètres standard de PrestaShop pour que ce module puisse gérer leurs taux.

**Q : Mon thème personnalisé n'affiche pas correctement les prix après les mises à jour.**
R : Ce module ne modifie que les taux de change sous-jacents. Si les prix sont affichés incorrectement, il est très peu probable qu'il s'agisse d'un problème direct du module.

1.  **Videz le cache Smarty :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ».
2.  **Compatibilité du thème :** Assurez-vous que votre thème personnalisé est entièrement compatible avec votre version de PrestaShop.
3.  **Code personnalisé :** Si votre thème a un code personnalisé pour l'affichage des prix, il se peut qu'il n'interprète pas correctement les taux de devise mis à jour de PrestaShop. Consultez le développeur de votre thème ou un expert PrestaShop.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Banque de Lettonie (Latvijas Banka) - taux de change » (`lbrates`) est un module PrestaShop léger principalement conçu pour automatiser les mises à jour des taux de change. Il suit un modèle MVC simple où le fichier principal du module (`cronjob.php`) agit comme le contrôleur principal pour la configuration et le contrôleur frontal (`cronjob.php`) gère la logique de récupération des taux. Il utilise les classes `Currency` et `Configuration` de PrestaShop pour gérer les taux et les paramètres. Le module est piloté par des appels de tâches cron externes, ce qui en fait un processus d'arrière-plan asynchrone.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    -   `lbrates/controllers/front/cronjob.php`
        -   Nom de la classe : `LbratesCronjobModuleFrontController`
        -   Classe parente : `ModuleFrontController`
        -   Responsabilité : Ce contrôleur est le cœur de la fonctionnalité du module. Il est conçu pour être appelé par une tâche cron externe. Lorsqu'il est accédé, il récupère les derniers taux de référence de l'Euro auprès de l'API officielle de la Banque de Lettonie, applique la marge configurée et met à jour les taux de change pour toutes les devises actives dans la base de données PrestaShop. Il gère également la journalisation et empêche les mises à jour trop fréquentes basées sur la clé de configuration `PS_LBRATES_LAST_UPDATE`.
    -   `lbrates/controllers/front/index.php`
        -   Nom de la classe : `LbratesIndexModuleFrontController`
        -   Classe parente : `ModuleFrontController`
        -   Responsabilité : Il s'agit d'un fichier `index.php` vide standard souvent inclus dans les répertoires des contrôleurs frontaux de module PrestaShop pour empêcher l'affichage du contenu du répertoire. Il ne contient aucune logique fonctionnelle.
-   **Contrôleurs d'administration Back-Office** :

    -   Aucun. Toute l'administration est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

-   Aucun. Le module interagit directement avec les classes `Currency` et `Configuration` de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

-   Aucun. Le module n'utilise aucun JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

-   Aucun. Le module n'utilise aucun CSS personnalisé.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates d'administration (`views/templates/admin/`)** :
    -   `lbrates/views/admin.tpl`
        -   Ce template est rendu par la méthode `getContent()` dans le fichier principal du module `cronjob.php`. Il affiche le formulaire de configuration du module dans le Back Office de PrestaShop. Cela inclut les champs pour l'URL CRON, la marge, la fréquence de mise à jour et l'interrupteur Activer/Désactiver. Il utilise les assistants de formulaire et le style standard de PrestaShop.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module ne crée aucune table SQL personnalisée.
    -   Il stocke ses paramètres de configuration dans la table `ps_configuration` :
        -   `PS_LBRATES_SPREAD` : Stocke la marge en pourcentage configurée.
        -   `PS_LBRATES_UPDATE_FREQUENCY` : Stocke la fréquence de mise à jour configurée (par exemple, quotidienne, horaire).
        -   `PS_LBRATES_LAST_UPDATE` : Stocke l'horodatage de la dernière mise à jour réussie pour éviter les appels trop fréquents.
        -   `PS_LBRATES_ENABLED` : Stocke l'état activé/désactivé du module.
    -   Il met à jour la colonne `exchange_rate` dans la table `ps_currency` pour les devises actives.
-   **Table des hooks enregistrés** :

    -   Le module n'enregistre aucun hook d'affichage traditionnel (`displayHeader`, `displayFooter`, etc.) dans le front office. Sa fonction principale est le traitement en arrière-plan.
    -   Il utilise implicitement le hook `actionUpdateCurrency` (ou des mécanismes internes similaires) en modifiant directement les taux de change des devises, mais il ne s'y enregistre pas explicitement.
    -   La méthode `install()` du module enregistrerait le module lui-même dans le système de modules de PrestaShop, rendant sa configuration accessible.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Banque de Lettonie (Latvijas Banka) - taux de change », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour aider les marchands et les développeurs avec tout problème ou question lié à la fonctionnalité et à l'intégration du module.
