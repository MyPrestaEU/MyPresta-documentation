---
title: "Points de fidélité – Règles d'ancienneté - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Points de fidélité – Règles d'ancienneté par MyPresta.eu."
sidebar:
  label: "Points de fidélité – Règles d'ancienneté - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Loyalty points – Tenure (seniority) rules sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points-tenure-seniority-rules.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/loyalty-points-tenure-seniority-rules/)
>
> ---


# Points de fidélité – Règles d'ancienneté

## 1. Exigences et Compatibilité

- **Versions PrestaShop Supportées** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'Hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont habituellement disponibles sur la plupart des environnements d'hébergement. Ce module n'a pas d'exigences spécifiques supplémentaires au-delà d'une installation PrestaShop standard.

## 2. Guide de Configuration Complet (Chaque Paramètre Groupé par Écran)

### 2.1 Page de Configuration du Module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal du module, accessible immédiatement après l'installation ou en cliquant sur « Configurer » depuis le Gestionnaire de modules.

**Paramètres Généraux**

-   **Activer le module :**

    *   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver l'ensemble des fonctionnalités du module.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Le module commencera à traiter les règles de fidélité basées sur l'ancienneté du client et à attribuer des points comme configuré.
        *   *Lorsqu'il est désactivé :* Le module cessera de fonctionner. Aucun nouveau point ne sera attribué en fonction des règles d'ancienneté, et les règles existantes seront ignorées jusqu'à leur réactivation.
    *   **Valeur recommandée :** OUI
    *   **Scénario / exemple pour le marchand :** Vous avez terminé de configurer vos règles et êtes prêt à lancer votre programme de fidélité. Activez-le pour commencer à récompenser les clients. Si vous devez suspendre temporairement le programme pour maintenance ou révision, vous pouvez le désactiver ici.
-   **URL de la tâche Cron :**

    *   **Ce que fait ce paramètre :** Il affiche une URL unique que vous devez configurer comme une « tâche cron » sur votre serveur web. Une tâche cron est une tâche planifiée qui indique à votre serveur d'exécuter cette URL automatiquement à intervalles réguliers (par exemple, une fois par jour). C'est ainsi que le module vérifie l'ancienneté des clients et attribue des points sans que vous ayez à le déclencher manuellement.
    *   **Effet de la modification de ce paramètre :** Vous ne pouvez pas modifier cette URL directement. Elle est générée par le module.
        *   *Lorsqu'elle est correctement configurée comme une tâche cron :* Le module exécutera automatiquement ses vérifications et attribuera des points selon vos règles.
        *   *Lorsqu'elle N'EST PAS configurée comme une tâche cron :* L'attribution automatique de points par le module ne se produira pas. Vous devriez visiter manuellement cette URL dans votre navigateur pour déclencher le processus, ce qui va à l'encontre de l'automatisation.
    *   **Valeur recommandée :** Copiez cette URL et configurez-la comme une tâche cron quotidienne sur votre serveur.
    *   **Scénario / exemple pour le marchand :** Après avoir installé le module, copiez cette URL. Allez dans votre panneau de contrôle d'hébergement (par exemple, cPanel, Plesk) et trouvez la section « Tâches Cron » ou « Tâches Planifiées ». Ajoutez une nouvelle tâche cron pour exécuter cette URL une fois toutes les 24 heures. Cela garantit que vos clients reçoivent leurs points d'ancienneté automatiquement et à temps.

### 2.2 Écran d'Administration Dédié : Règles d'Ancienneté de Fidélité (Back Office > MyPresta.eu > Règles d'Ancienneté de Fidélité)

Cet écran vous permet de définir et de gérer les règles spécifiques pour l'attribution de points de fidélité basés sur l'ancienneté du client.

-   **Nom de l'écran et Emplacement du Menu :** Vous pouvez trouver cet écran en naviguant vers **MyPresta.eu > Règles d'Ancienneté de Fidélité** dans le menu de votre Back Office PrestaShop.
-   **Actions et Paramètres Disponibles :**

    *   **Tableau de Liste des Règles :** Ce tableau affiche toutes vos règles d'ancienneté actives et inactives. Pour chaque règle, vous verrez :
        *   **ID :** Un identifiant unique pour la règle.
        *   **Ancienneté (Jours) :** Le nombre minimum de jours pendant lesquels un client doit être enregistré pour être éligible à cette règle.
        *   **Points à Attribuer :** Le nombre de points de fidélité qu'un client recevra.
        *   **Actif :** Un interrupteur pour activer ou désactiver la règle.
        *   **Actions :** Boutons pour « Modifier » ou « Supprimer » une règle.
    *   **Bouton « Ajouter une nouvelle règle » :** Cliquez sur ce bouton pour créer une nouvelle règle d'ancienneté.

    **Lors de l'Ajout/Modification d'une Règle :**
    Un formulaire vous sera présenté pour définir les paramètres de la règle :

    *   **Ancienneté (Jours) :**

        *   **Ce que fait ce paramètre :** C'est le nombre minimum de jours pendant lesquels un client doit être enregistré sur votre boutique pour être éligible à cette attribution spécifique de points de fidélité.
        *   **Effet de la modification de ce paramètre :**
            *   *Réglé à 365 :* Les clients enregistrés depuis au moins un an seront éligibles.
            *   *Réglé à 730 :* Les clients enregistrés depuis au moins deux ans seront éligibles.
        *   **Valeur recommandée :** Choisissez des valeurs qui représentent des jalons significatifs pour vos clients (par exemple, 365 jours pour 1 an, 730 jours pour 2 ans, 1095 jours pour 3 ans).
        *   **Scénario / exemple pour le marchand :** Vous souhaitez récompenser les clients qui sont avec votre boutique depuis au moins un an. Vous le réglerez à `365`.
    *   **Points à Attribuer :**

        *   **Ce que fait ce paramètre :** C'est le nombre exact de points de fidélité qui seront accordés à un client qui remplit l'exigence « Ancienneté (Jours) » pour cette règle.
        *   **Effet de la modification de ce paramètre :**
            *   *Réglé à 100 :* Les clients éligibles reçoivent 100 points de fidélité.
            *   *Réglé à 50 :* Les clients éligibles reçoivent 50 points de fidélité.
        *   **Valeur recommandée :** Alignez cela avec la valeur de votre programme de points de fidélité existant. Un bon point de départ pourrait être des points équivalents à une petite réduction (par exemple, 5-10 % de la valeur moyenne d'une commande).
        *   **Scénario / exemple pour le marchand :** Pour remercier significativement un an de fidélité, vous pourriez attribuer `250` points, ce qui pourrait se traduire par une réduction de 5 € sur leur prochain achat.
    *   **Actif :**

        *   **Ce que fait ce paramètre :** Cet interrupteur détermine si cette règle spécifique est actuellement active et sera prise en compte par le module lors de l'attribution des points.
        *   **Effet de la modification de ce paramètre :**
            *   *Lorsqu'il est activé :* La règle sera traitée par la tâche cron, et des points seront attribués aux clients éligibles.
            *   *Lorsqu'il est désactivé :* La règle sera ignorée, et aucun point ne sera attribué en fonction de ce seuil d'ancienneté spécifique.
        *   **Valeur recommandée :** OUI (pour les règles que vous souhaitez activer).
        *   **Scénario / exemple pour le marchand :** Vous avez créé une règle pour 5 ans d'ancienneté mais souhaitez la tester en interne avant de la rendre publique. Vous pouvez la laisser désactivée jusqu'à ce que vous soyez prêt à l'activer.
-   **Effet des modifications :**

    *   L'ajout d'une nouvelle règle crée une nouvelle entrée dans la base de données que la tâche cron du module vérifiera.
    *   La modification d'une règle modifie ses paramètres (ancienneté, points, statut actif), affectant les futures attributions de points.
    *   La suppression d'une règle la supprime définitivement, et aucun autre point ne sera attribué en fonction de cette ancienneté spécifique.
    *   La clé de configuration `PS_LIST_LIMIT` contrôle le nombre d'éléments affichés par page dans le tableau de liste des règles.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**

    1.  **Planifiez vos niveaux de fidélité :** Décidez quels jalons d'ancienneté vous souhaitez récompenser (par exemple, 1 an, 2 ans, 5 ans).
    2.  **Calculez les valeurs des points :** Déterminez combien de points vous souhaitez attribuer pour chaque niveau, en tenant compte de la valeur monétaire de vos points de fidélité.
    3.  **Créez des règles :** Allez dans **MyPresta.eu > Règles d'Ancienneté de Fidélité** et cliquez sur « Ajouter une nouvelle règle » pour chaque niveau.
    4.  **Surveillez :** Vérifiez périodiquement les soldes de points de fidélité de vos clients et assurez-vous que la tâche cron fonctionne correctement.

### 2.3 Tableau de Référence Rapide de la Configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et Impact
Le module « Points de fidélité – Règles d'ancienneté » est conçu pour récompenser vos clients avec des points de fidélité en fonction de la durée de leur inscription sur votre boutique PrestaShop. Cela vous aide à reconnaître et à fidéliser vos clients les plus fidèles en leur attribuant automatiquement des points bonus lorsqu'ils atteignent certains jalons d'« ancienneté » (par exemple, 1 an, 2 ans, 5 ans depuis l'inscription).

## 3. Exigences et Compatibilité

- **Versions PrestaShop Supportées** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'Hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont habituellement disponibles sur la plupart des environnements d'hébergement. Ce module n'a pas d'exigences spécifiques supplémentaires au-delà d'une installation PrestaShop standard.

## 4. Guide de Configuration Complet (Chaque Paramètre Groupé par Écran)

### 4.1 Page de Configuration du Module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal du module, accessible immédiatement après l'installation ou en cliquant sur « Configurer » depuis le Gestionnaire de modules.

**Paramètres Généraux**

-   **Activer le module :**

    *   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver l'ensemble des fonctionnalités du module.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Le module commencera à traiter les règles de fidélité basées sur l'ancienneté du client et à attribuer des points comme configuré.
        *   *Lorsqu'il est désactivé :* Le module cessera de fonctionner. Aucun nouveau point ne sera attribué en fonction des règles d'ancienneté, et les règles existantes seront ignorées jusqu'à leur réactivation.
    *   **Valeur recommandée :** OUI
    *   **Scénario / exemple pour le marchand :** Vous avez terminé de configurer vos règles et êtes prêt à lancer votre programme de fidélité. Activez-le pour commencer à récompenser les clients. Si vous devez suspendre temporairement le programme pour maintenance ou révision, vous pouvez le désactiver ici.
-   **URL de la tâche Cron :**

    *   **Ce que fait ce paramètre :** Il affiche une URL unique que vous devez configurer comme une « tâche cron » sur votre serveur web. Une tâche cron est une tâche planifiée qui indique à votre serveur d'exécuter cette URL automatiquement à intervalles réguliers (par exemple, une fois par jour). C'est ainsi que le module vérifie l'ancienneté des clients et attribue des points sans que vous ayez à le déclencher manuellement.
    *   **Effet de la modification de ce paramètre :** Vous ne pouvez pas modifier cette URL directement. Elle est générée par le module.
        *   *Lorsqu'elle est correctement configurée comme une tâche cron :* Le module exécutera automatiquement ses vérifications et attribuera des points selon vos règles.
        *   *Lorsqu'elle N'EST PAS configurée comme une tâche cron :* L'attribution automatique de points par le module ne se produira pas. Vous devriez visiter manuellement cette URL dans votre navigateur pour déclencher le processus, ce qui va à l'encontre de l'automatisation.
    *   **Valeur recommandée :** Copiez cette URL et configurez-la comme une tâche cron quotidienne sur votre serveur.
    *   **Scénario / exemple pour le marchand :** Après avoir installé le module, copiez cette URL. Allez dans votre panneau de contrôle d'hébergement (par exemple, cPanel, Plesk) et trouvez la section « Tâches Cron » ou « Tâches Planifiées ». Ajoutez une nouvelle tâche cron pour exécuter cette URL une fois toutes les 24 heures. Cela garantit que vos clients reçoivent leurs points d'ancienneté automatiquement et à temps.

### 4.2 Écran d'Administration Dédié : Règles d'Ancienneté de Fidélité (Back Office > MyPresta.eu > Règles d'Ancienneté de Fidélité)

Cet écran vous permet de définir et de gérer les règles spécifiques pour l'attribution de points de fidélité basés sur l'ancienneté du client.

-   **Nom de l'écran et Emplacement du Menu :** Vous pouvez trouver cet écran en naviguant vers **MyPresta.eu > Règles d'Ancienneté de Fidélité** dans le menu de votre Back Office PrestaShop.
-   **Actions et Paramètres Disponibles :**

    *   **Tableau de Liste des Règles :** Ce tableau affiche toutes vos règles d'ancienneté actives et inactives. Pour chaque règle, vous verrez :
        *   **ID :** Un identifiant unique pour la règle.
        *   **Ancienneté (Jours) :** Le nombre minimum de jours pendant lesquels un client doit être enregistré pour être éligible à cette règle.
        *   **Points à Attribuer :** Le nombre de points de fidélité qu'un client recevra.
        *   **Actif :** Un interrupteur pour activer ou désactiver la règle.
        *   **Actions :** Boutons pour « Modifier » ou « Supprimer » une règle.
    *   **Bouton « Ajouter une nouvelle règle » :** Cliquez sur ce bouton pour créer une nouvelle règle d'ancienneté.

    **Lors de l'Ajout/Modification d'une Règle :**
    Un formulaire vous sera présenté pour définir les paramètres de la règle :

    *   **Ancienneté (Jours) :**

        *   **Ce que fait ce paramètre :** C'est le nombre minimum de jours pendant lesquels un client doit être enregistré sur votre boutique pour être éligible à cette attribution spécifique de points de fidélité.
        *   **Effet de la modification de ce paramètre :**
            *   *Réglé à 365 :* Les clients enregistrés depuis au moins un an seront éligibles.
            *   *Réglé à 730 :* Les clients enregistrés depuis au moins deux ans seront éligibles.
        *   **Valeur recommandée :** Choisissez des valeurs qui représentent des jalons significatifs pour vos clients (par exemple, 365 jours pour 1 an, 730 jours pour 2 ans, 1095 jours pour 3 ans).
        *   **Scénario / exemple pour le marchand :** Vous souhaitez récompenser les clients qui sont avec votre boutique depuis au moins un an. Vous le réglerez à `365`.
    *   **Points à Attribuer :**

        *   **Ce que fait ce paramètre :** C'est le nombre exact de points de fidélité qui seront accordés à un client qui remplit l'exigence « Ancienneté (Jours) » pour cette règle.
        *   **Effet de la modification de ce paramètre :**
            *   *Réglé à 100 :* Les clients éligibles reçoivent 100 points de fidélité.
            *   *Réglé à 50 :* Les clients éligibles reçoivent 50 points de fidélité.
        *   **Valeur recommandée :** Alignez cela avec la valeur de votre programme de points de fidélité existant. Un bon point de départ pourrait être des points équivalents à une petite réduction (par exemple, 5-10 % de la valeur moyenne d'une commande).
        *   **Scénario / exemple pour le marchand :** Pour remercier significativement un an de fidélité, vous pourriez attribuer `250` points, ce qui pourrait se traduire par une réduction de 5 € sur leur prochain achat.
    *   **Actif :**

        *   **Ce que fait ce paramètre :** Cet interrupteur détermine si cette règle spécifique est actuellement active et sera prise en compte par le module lors de l'attribution des points.
        *   **Effet de la modification de ce paramètre :**
            *   *Lorsqu'il est activé :* La règle sera traitée par la tâche cron, et des points seront attribués aux clients éligibles.
            *   *Lorsqu'il est désactivé :* La règle sera ignorée, et aucun point ne sera attribué en fonction de ce seuil d'ancienneté spécifique.
        *   **Valeur recommandée :** OUI (pour les règles que vous souhaitez activer).
        *   **Scénario / exemple pour le marchand :** Vous avez créé une règle pour 5 ans d'ancienneté mais souhaitez la tester en interne avant de la rendre publique. Vous pouvez la laisser désactivée jusqu'à ce que vous soyez prêt à l'activer.
-   **Effet des modifications :**

    *   L'ajout d'une nouvelle règle crée une nouvelle entrée dans la base de données que la tâche cron du module vérifiera.
    *   La modification d'une règle modifie ses paramètres (ancienneté, points, statut actif), affectant les futures attributions de points.
    *   La suppression d'une règle la supprime définitivement, et aucun autre point ne sera attribué en fonction de cette ancienneté spécifique.
    *   La clé de configuration `PS_LIST_LIMIT` contrôle le nombre d'éléments affichés par page dans le tableau de liste des règles.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**

    1.  **Planifiez vos niveaux de fidélité :** Décidez quels jalons d'ancienneté vous souhaitez récompenser (par exemple, 1 an, 2 ans, 5 ans).
    2.  **Calculez les valeurs des points :** Déterminez combien de points vous souhaitez attribuer pour chaque niveau, en tenant compte de la valeur monétaire de vos points de fidélité.
    3.  **Créez des règles :** Allez dans **MyPresta.eu > Règles d'Ancienneté de Fidélité** et cliquez sur « Ajouter une nouvelle règle » pour chaque niveau.
    4.  **Surveillez :** Vérifiez périodiquement les soldes de points de fidélité de vos clients et assurez-vous que la tâche cron fonctionne correctement.

### 4.3 Tableau de Référence Rapide de la Configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et Impact

## 5. Dépannage Marchand et Questions Fréquemment Posées (FAQ)

**Q1 : Mes clients ne reçoivent pas de points de fidélité, même si j'ai configuré des règles.**
R1 :

-   **Vérifier l'activation du module :** Assurez-vous que le paramètre « Activer le module » sur la page de configuration principale est réglé sur OUI.
-   **Vérifier la tâche Cron :** La raison la plus courante est une tâche cron mal configurée ou qui ne s'exécute pas. Vérifiez à nouveau l'URL de la tâche Cron depuis la page de configuration du module et assurez-vous qu'elle est correctement configurée sur votre serveur d'hébergement pour s'exécuter quotidiennement.
-   **Statut de la règle :** Assurez-vous que les règles d'ancienneté de fidélité individuelles que vous avez créées sont marquées comme « Actives ».
-   **Éligibilité du client :** Le client a-t-il réellement rempli l'exigence « Ancienneté (Jours) » pour l'une de vos règles actives ? Le module n'attribue des points qu'une fois qu'un client franchit un seuil.
-   **Cache Smarty :** Parfois, le cache de PrestaShop peut provoquer des problèmes d'affichage. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes).

**Q2 : Comment savoir si la tâche cron s'exécute correctement ?**
R2 :

-   **Vérifier les journaux d'hébergement :** La plupart des fournisseurs d'hébergement offrent un moyen de consulter les journaux d'exécution des tâches cron dans votre panneau de contrôle (par exemple, cPanel). Recherchez les entrées liées à l'URL de la tâche cron fournie par le module.
-   **Test manuel :** Vous pouvez visiter manuellement l'URL de la tâche Cron dans votre navigateur web. Cela déclenchera le processus d'attribution de points pour ce moment. Si des points sont attribués aux clients éligibles après cette visite manuelle, cela confirme que la logique du module fonctionne, et le problème concerne la configuration automatisée de la tâche cron.

**Q3 : Puis-je attribuer des points rétroactivement aux clients qui ont déjà dépassé un jalon d'ancienneté avant que j'installe le module ?**
R3 : Oui, lorsque la tâche cron s'exécute pour la première fois après que vous ayez configuré des règles, elle évaluera tous les clients existants par rapport à vos règles actives. Si un client remplit une exigence d'ancienneté et n'a pas été récompensé par des points pour cette règle spécifique auparavant, il les recevra. Cela signifie que les clients fidèles plus anciens recevront les points qu'ils méritent.

**Q4 : Mon thème personnalisé n'affiche pas correctement les points de fidélité, ou les notifications semblent étranges.**
R4 : Ce module interagit principalement avec le système de fidélité de base de PrestaShop. Tout problème d'affichage avec les points de fidélité ou les notifications est généralement lié au style de votre thème ou aux surcharges pour le module de fidélité natif.

-   **Personnalisation du thème :** Si vous avez un thème personnalisé, il peut avoir ses propres modèles ou CSS pour afficher les informations de fidélité. Vous devrez peut-être consulter le développeur de votre thème ou un webmaster pour vous assurer qu'il s'intègre correctement aux fonctionnalités de fidélité de PrestaShop.
-   **Test avec le thème par défaut :** Basculez temporairement vers le thème PrestaShop par défaut (Classic) pour voir si le problème persiste. Si cela fonctionne correctement sur le thème par défaut, le problème vient certainement de votre thème personnalisé.

**Q5 : Que se passe-t-il si je modifie une règle (par exemple, j'augmente les points) après que les clients aient déjà reçu des points de celle-ci ?**
R5 : Le module est conçu pour attribuer des points *une seule fois* pour chaque règle lorsqu'un client atteint pour la première fois le seuil d'ancienneté. Si vous modifiez une règle (par exemple, vous augmentez les points pour 365 jours de 100 à 150), les clients qui ont déjà reçu 100 points pour 365 jours ne recevront *pas* automatiquement les 50 points supplémentaires. La règle a déjà été « satisfaite » pour eux. Si vous souhaitez leur donner les points supplémentaires, vous devrez ajuster manuellement leur solde de fidélité ou créer une nouvelle règle temporaire.

## 6. Guide du Développeur et du Webmaster (Architecture Technique et Carte du Code)

### 6.1 Aperçu de l'Architecture

Le module « Points de fidélité – Règles d'ancienneté » (`myprestaloyalty_tenure`) étend les fonctionnalités de PrestaShop en introduisant un nouveau concept d'attribution de points de fidélité basé sur l'ancienneté d'inscription du client. Il suit une architecture de module PrestaShop standard, tirant parti d'`ObjectModel` pour la gestion des règles d'ancienneté et d'un contrôleur frontal dédié pour l'exécution des tâches cron. Le module s'intègre au `LoyaltyModule` de base de PrestaShop pour attribuer des points, assurant la compatibilité avec le système de fidélité natif.

### 6.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    *   `controllers/front/cron.php`
        *   **Nom de la classe :** `MyprestaloyaltyTenureCronModuleFrontController` (étend `ModuleFrontController`)
        *   **Responsabilité :** Ce contrôleur est conçu pour être exécuté via une tâche cron. Lorsqu'il est accédé, il itère sur toutes les règles d'ancienneté actives et tous les clients enregistrés. Pour chaque client, il calcule son âge d'inscription et vérifie s'il est éligible à une règle active pour laquelle il n'a pas encore reçu de points. Si un client est éligible, il attribue les points de fidélité spécifiés en utilisant la fonctionnalité du `LoyaltyModule` de base. Il renvoie généralement un simple message de succès ou une sortie de journal.
    *   `controllers/front/index.php`
        *   **Nom de la classe :** `MyprestaloyaltyTenureIndexModuleFrontController` (étend `ModuleFrontController`)
        *   **Responsabilité :** Il s'agit d'un contrôleur frontal de remplacement ou par défaut. Dans de nombreux modules, si aucune action spécifique n'est définie, `index.php` peut gérer une vue par défaut ou une redirection. Pour ce module, son interaction principale en front-office se fait via le contrôleur `cron.php`.
-   **Contrôleurs d'Administration Back-Office** :

    *   `controllers/admin/AdminMyprestaloyaltyTenureController.php`
        *   **Nom de la classe :** `AdminMyprestaloyaltyTenureController` (étend `ModuleAdminController`)
        *   **Nom de l'onglet :** « Règles d'Ancienneté de Fidélité » (sous le menu MyPresta.eu)
        *   **Entité gérée :** `MyprestaloyaltyTenureRule` (mappe à la table de base de données `_myprestaloyalty_tenure_rule`)
        *   **Responsabilité :** Ce contrôleur fournit l'interface CRUD (Créer, Lire, Mettre à jour, Supprimer) pour gérer les règles d'ancienneté de fidélité dans le Back Office de PrestaShop. Il utilise `HelperList` pour afficher la liste des règles et `HelperForm` pour ajouter/modifier des règles individuelles. Il gère les soumissions de formulaires, la validation et l'interaction avec l'`ObjectModel` `MyprestaloyaltyTenureRule`.
    *   `controllers/admin/index.php`
        *   **Nom de la classe :** (Pas de classe spécifique, généralement utilisé pour la sécurité)
        *   **Responsabilité :** Ce fichier contient généralement un simple `header('Location: ../../index.php?controller=AdminHome'); exit;` ou similaire pour empêcher l'affichage direct du répertoire et garantir que les contrôleurs d'administration sont accédés via le répartiteur PrestaShop.

### 6.3 Classes et Modèles de Base (`classes/`)

-   `classes/index.php`

    *   **Responsabilité :** Fichier de sécurité PrestaShop standard, contenant généralement `header('Location: ../../index.php?controller=AdminHome'); exit;` pour empêcher l'accès direct au répertoire `classes`.
-   `classes/MyprestaloyaltyTenureRule.php`

    *   **Nom de la classe :** `MyprestaloyaltyTenureRule` (étend `ObjectModel`)
    *   **Table de base de données :** `_myprestaloyalty_tenure_rule`
    *   **Champs `$definition` :**
        *   `id_myprestaloyalty_tenure_rule` : Clé primaire.
        *   `tenure_days` : Entier, le nombre minimum de jours pendant lesquels un client doit être enregistré.
        *   `points_to_award` : Entier, le nombre de points de fidélité à accorder.
        *   `active` : Booléen, si la règle est active (0 ou 1).
    *   **Méthodes publiques clés :**
        *   `__construct()` : Constructeur `ObjectModel` standard.
        *   `add()` : Surcharge `ObjectModel::add()` pour une logique personnalisée si nécessaire (par exemple, gestion des dates, validation).
        *   `update()` : Surcharge `ObjectModel::update()`.
        *   `delete()` : Surcharge `ObjectModel::delete()`.
        *   `getAllActiveRules()` : Méthode statique pour récupérer toutes les règles actives de la base de données.
        *   `hasCustomerReceivedPointsForRule($id_customer, $id_rule)` : Méthode statique pour vérifier si un client spécifique a déjà reçu des points pour une règle donnée. Ceci est crucial pour éviter les attributions en double.
        *   `markCustomerAsAwarded($id_customer, $id_rule)` : Méthode statique pour enregistrer qu'un client a reçu des points pour une règle.

### 6.4 Actifs JavaScript (`views/js/`)

Le dossier du module n'indique aucune présence de fichiers JavaScript personnalisés dans `views/js/`. Toutes les interactions sont gérées côté serveur ou via les helpers de formulaire/liste standard de PrestaShop.

### 6.5 Feuilles de Style CSS (`views/css/`)

Le dossier du module n'indique aucune présence de fichiers CSS personnalisés dans `views/css/`. L'interface du Back Office repose sur les styles du thème d'administration par défaut de PrestaShop.

### 6.6 Structure des Modèles Smarty (`views/templates/`)

Le dossier du module n'indique aucune présence de fichiers de modèles Smarty personnalisés dans `views/templates/`. Les écrans de configuration et de gestion des règles du module sont rendus à l'aide des classes `HelperForm` et `HelperList` de PrestaShop, qui s'appuient sur les fichiers de modèles de base de PrestaShop.

### 6.7 Schéma de Base de Données et Carte des Hooks

-   **Tables de Base de Données** :

    *   `ps_myprestaloyalty_tenure_rule` : Stocke les définitions de chaque règle d'ancienneté.
        *   `id_myprestaloyalty_tenure_rule` INT(10) UNSIGNED NOT NULL AUTO\_INCREMENT
        *   `tenure_days` INT(10) UNSIGNED NOT NULL
        *   `points_to_award` INT(10) UNSIGNED NOT NULL
        *   `active` TINYINT(1) UNSIGNED NOT NULL DEFAULT ‘1’
        *   PRIMARY KEY (`id_myprestaloyalty_tenure_rule`)
    *   `ps_myprestaloyalty_tenure_awarded` : Enregistre quels clients ont reçu des points pour quelles règles, afin d'éviter les attributions en double.
        *   `id_myprestaloyalty_tenure_awarded` INT(10) UNSIGNED NOT NULL AUTO\_INCREMENT
        *   `id_customer` INT(10) UNSIGNED NOT NULL
        *   `id_myprestaloyalty_tenure_rule` INT(10) UNSIGNED NOT NULL
        *   `date_awarded` DATETIME NOT NULL
        *   PRIMARY KEY (`id_myprestaloyalty_tenure_awarded`)
        *   UNIQUE KEY `customer_rule` (`id_customer`, `id_myprestaloyalty_tenure_rule`)
-   **Table des Hooks Enregistrés** :
    Le module n'enregistre explicitement aucun hook d'affichage front-office (comme `displayHeader`, `displayRightColumn`, `displayProductExtraContent`, `displayFooter`) car sa fonction principale est le traitement en arrière-plan via cron.
    Il utilise implicitement :

    | Nom du Hook | Moment d'Exécution | Objectif Technique |
    | --- | --- | --- |
    | `actionModuleInstall` | Lors de l'installation du module | Crée les tables de base de données, enregistre l'onglet d'administration. |
    | `actionModuleUninstall` | Lors de la désinstallation du module | Supprime les tables de base de données et la configuration. |
    | `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration est chargé | Si le module avait des JS/CSS personnalisés pour l'administration, il les enregistrerait ici. (Non utilisé dans ce module selon l'inventaire) |
    | `displayBackOfficeTop` | Rend le contenu en haut du Back Office | Utilisé pour afficher l'URL de la tâche cron et les instructions sur la page de configuration du module. |

## 7. Support Officiel et Mises à Jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Points de fidélité – Règles d'ancienneté », veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe est dédiée à fournir une assistance rapide et à garantir le fonctionnement optimal de votre module.

-   **Accéder aux Téléchargements et Mises à Jour :** Connectez-vous à votre compte sur [Historique des commandes et téléchargements MyPresta.eu](https://mypresta.eu/my-account/orders/).
-   **Contacter le Support :** Utilisez les canaux de support fournis dans votre compte MyPresta.eu pour toute question ou problème technique.
