---
title: "Remise ou Frais de Paiement - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Remise ou Frais de Paiement par MyPresta.eu."
sidebar:
  label: "Remise ou Frais de Paiement - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Payment Discount or Fee sur MyPresta.eu](https://mypresta.eu/modules/payment-process/payment-discount-or-fee.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/payment/payment-discount-or-fee/)
>
> ---


# Remise ou Frais de Paiement

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises, qui sont généralement disponibles sur la plupart des environnements d'hébergement web modernes.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

Le module « Remise ou Frais de Paiement » offre un ensemble complet d'options pour contrôler précisément la manière dont les remises ou les frais sont appliqués.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Remise ou Frais de Paiement)

C'est l'écran de configuration principal où vous activez et configurez le comportement essentiel du module.

- **Activer le module :**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité du module dans votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module commencera à appliquer les remises ou les frais en fonction de vos règles définies lors du passage en caisse.
    - *Lorsqu'il est désactivé :* Le module cessera toutes ses opérations, et aucune remise ou frais ne sera appliqué.
  - **Valeur recommandée :** OUI (une fois que vous avez configuré vos règles).
  - **Scénario / exemple marchand :** Vous avez terminé de configurer toutes vos règles et êtes prêt à passer en production. Activez ceci pour activer le module. Si vous devez le désactiver temporairement pour la maintenance, réglez-le sur NON.
- **Afficher les frais/remises dans le récapitulatif du panier :**

  - **Ce que fait ce paramètre :** Contrôle si l'ajustement du mode de paiement est affiché comme une ligne distincte dans le récapitulatif du panier *avant* que le client n'atteigne l'étape de paiement.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clients verront une ligne comme « Ajustement du mode de paiement » dans leur récapitulatif du panier, même avant de sélectionner un mode de paiement, indiquant que le prix final pourrait changer.
    - *Lorsqu'il est désactivé :* L'ajustement n'apparaîtra qu'une fois que le client aura sélectionné un mode de paiement sur la page de commande.
  - **Valeur recommandée :** OUI (pour la transparence).
  - **Scénario / exemple marchand :** Vous souhaitez que les clients soient pleinement conscients des ajustements de paiement potentiels le plus tôt possible. L'activation de cette option offre une transparence maximale.
- **Appliquer les frais/remises aux frais de port :**

  - **Ce que fait ce paramètre :** Détermine si la remise ou les frais calculés doivent également être appliqués aux frais de port de la commande, ou uniquement au total des produits.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Si vous avez des frais de 2 %, et que le total des produits est de 100 € et les frais de port de 10 €, les frais seront de 2 % de 110 € (2,20 €).
    - *Lorsqu'il est désactivé :* Les frais de 2 % ne s'appliqueraient qu'au total des produits de 100 € (2,00 €), et les frais de port resteraient séparés.
  - **Valeur recommandée :** OUI (si les frais de votre passerelle de paiement s'appliquent également à la valeur totale de la commande, y compris les frais de port).
  - **Scénario / exemple marchand :** La plupart des passerelles de paiement facturent un pourcentage sur le montant *total* de la transaction, y compris les frais de port. L'activation de cette option garantit que vos frais reflètent précisément vos coûts.
- **Appliquer les frais/remises à la taxe :**

  - **Ce que fait ce paramètre :** Détermine si la remise ou les frais calculés doivent également être appliqués au montant de la taxe de la commande, ou uniquement au total des produits (et potentiellement aux frais de port).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Si vous avez des frais de 2 %, et que le total des produits est de 100 €, les frais de port de 10 € et la taxe de 20 €, les frais seront de 2 % de 130 € (2,60 €).
    - *Lorsqu'il est désactivé :* Les frais de 2 % ne s'appliqueraient qu'au total des produits (et aux frais de port si activé), et la taxe resterait séparée.
  - **Valeur recommandée :** OUI (si les frais de votre passerelle de paiement s'appliquent également à la valeur totale de la commande, y compris la taxe).
  - **Scénario / exemple marchand :** Similaire aux frais de port, les passerelles de paiement facturent généralement sur le grand total. L'activation de cette option garantit que votre calcul des frais est complet.
- **Libellé des frais/remises dans le panier/la commande :**

  - **Ce que fait ce paramètre :** Vous permet de personnaliser le libellé textuel qui apparaît à côté du montant de la remise ou des frais dans le récapitulatif du panier et les détails de la commande.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur « Surcharge du mode de paiement » :* Ce texte sera affiché.
    - *Lorsqu'il est défini sur « Remise de paiement » :* Ce texte sera affiché.
  - **Valeur recommandée :** « Ajustement du mode de paiement » ou « Surcharge de paiement » / « Remise de paiement » selon votre utilisation principale.
  - **Scénario / exemple marchand :** Vous utilisez principalement le module pour ajouter des frais. Définir le libellé sur « Surcharge de paiement » le rend clair pour les clients. Si vous offrez des remises, « Remise de paiement » est plus approprié.
- **URL de la tâche Cron pour le nettoyage du journal d'audit :**

  - **Ce que fait ce paramètre :** Fournit une URL que vous pouvez configurer comme tâche cron sur votre serveur pour nettoyer automatiquement les anciennes entrées du journal d'audit du module, empêchant la base de données de devenir trop volumineuse.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est configuré comme tâche cron :* Le journal d'audit sera régulièrement purgé des anciennes entrées, améliorant les performances de la base de données.
    - *Lorsqu'il n'est pas configuré :* Le journal d'audit augmentera indéfiniment, ralentissant potentiellement votre Back Office au fil du temps.
  - **Valeur recommandée :** Configurez une tâche cron pour exécuter cette URL quotidiennement ou hebdomadairement.
  - **Scénario / exemple marchand :** Vous souhaitez garder votre base de données légère et rapide. Copiez cette URL et ajoutez-la au planificateur de tâches cron de votre panneau de contrôle d'hébergement.

### 2.2 Écran d'administration dédié : Règles de remise ou de frais de paiement (Back Office > Paiement > Règles de remise ou de frais de paiement)

Cet écran est l'endroit où vous définissez et gérez toutes les règles d'application des remises ou des frais.

- **Nom de l'écran et emplacement du menu :** **Règles de remise ou de frais de paiement** (situé sous **Paiement** dans le menu principal du Back Office de PrestaShop).
- **Actions et paramètres disponibles :**

  - **Tableau de liste des règles :** Affiche toutes vos règles actuellement actives et inactives, indiquant leur nom, mode de paiement, type (remise/frais), valeur et statut.
  - **Bouton « Ajouter une nouvelle règle » :** Cliquez ici pour créer une nouvelle règle de remise ou de frais.
  - **Actions Modifier/Supprimer :** Pour chaque règle de la liste, vous pouvez cliquer pour modifier ses détails ou la supprimer.
  - **Champs du formulaire pour ajouter/modifier une règle :**
    - **Nom de la règle :**
      - **Ce que fait ce paramètre :** Un nom descriptif pour votre règle, visible uniquement dans le Back Office.
      - **Effet de la modification de ce paramètre :** Vous aide à identifier et à gérer facilement vos règles.
      - **Valeur recommandée :** Claire et descriptive (par exemple, « Frais PayPal 2 % », « Remise Virement bancaire 5 % »).
    - **Mode de paiement :**
      - **Ce que fait ce paramètre :** Sélectionne la passerelle de paiement ou le mode spécifique auquel cette règle s'applique.
      - **Effet de la modification de ce paramètre :** La règle ne s'activera que lorsqu'un client choisira ce mode de paiement.
      - **Valeur recommandée :** Choisissez le mode de paiement exact que vous souhaitez cibler.
      - **Scénario / exemple marchand :** Vous souhaitez ajouter des frais pour « PayPal », vous sélectionnez donc « PayPal » dans la liste déroulante.
    - **Type :**
      - **Ce que fait ce paramètre :** Détermine si la règle applique une « Remise » ou des « Frais ».
      - **Effet de la modification de ce paramètre :**
        - *Remise :* Réduit le total de la commande.
        - *Frais :* Augmente le total de la commande.
      - **Valeur recommandée :** Sélectionnez en fonction de votre objectif (par exemple, « Frais » pour les coûts de traitement des cartes de crédit).
    - **Valeur :**
      - **Ce que fait ce paramètre :** Le montant ou le pourcentage de la remise/des frais.
      - **Effet de la modification de ce paramètre :**
        - *Si « Type » est « Pourcentage » :* Entrez « 2 » pour 2 %.
        - *Si « Type » est « Montant fixe » :* Entrez « 5.00 » pour 5,00 €.
      - **Valeur recommandée :** Le pourcentage ou le montant fixe exact que vous souhaitez appliquer.
    - **Type de valeur :**
      - **Ce que fait ce paramètre :** Choisissez si la « Valeur » est un « Pourcentage » du total de la commande ou un « Montant fixe ».
      - **Effet de la modification de ce paramètre :** Dicte la manière dont le champ « Valeur » est interprété.
      - **Valeur recommandée :** Le pourcentage est courant pour les frais ; le montant fixe pour des remises spécifiques.
    - **Montant minimum du panier (facultatif) :**
      - **Ce que fait ce paramètre :** Le total minimum de la commande (avant la remise/les frais) requis pour que cette règle s'applique.
      - **Effet de la modification de ce paramètre :** Si le total du panier est inférieur à ce montant, la règle ne sera pas appliquée.
      - **Valeur recommandée :** Laissez vide si aucun minimum n'est requis.
      - **Scénario / exemple marchand :** Vous ne souhaitez appliquer des frais que sur les commandes importantes pour éviter les micro-frais sur les petits achats.
    - **Montant maximum du panier (facultatif) :**
      - **Ce que fait ce paramètre :** Le total maximum de la commande (avant la remise/les frais) pour que cette règle s'applique.
      - **Effet de la modification de ce paramètre :** Si le total du panier est supérieur à ce montant, la règle ne sera pas appliquée.
      - **Valeur recommandée :** Laissez vide si aucun maximum n'est requis.
    - **Groupes de clients (facultatif) :**
      - **Ce que fait ce paramètre :** Restreint la règle à des groupes de clients spécifiques (par exemple, « Grossistes », « Invités »).
      - **Effet de la modification de ce paramètre :** Seuls les clients appartenant aux groupes sélectionnés seront affectés par cette règle.
      - **Valeur recommandée :** Sélectionnez « Tous les groupes de clients » sauf si vous avez des stratégies de prix spécifiques basées sur les groupes.
      - **Scénario / exemple marchand :** Vous souhaitez offrir une remise spéciale à vos « Clients VIP » lorsqu'ils paient par virement bancaire.
    - **Pays (facultatif) :**
      - **Ce que fait ce paramètre :** Restreint la règle aux clients de pays spécifiques.
      - **Effet de la modification de ce paramètre :** La règle ne s'appliquera que si l'adresse de livraison du client se trouve dans l'un des pays sélectionnés.
      - **Valeur recommandée :** Sélectionnez « Tous les pays » sauf si vous avez des stratégies de paiement spécifiques à un pays.
      - **Scénario / exemple marchand :** Vous avez des frais de traitement plus élevés pour les paiements par carte de crédit internationaux provenant de certaines régions.
    - **Produits à exclure (facultatif) :**
      - **Ce que fait ce paramètre :** Vous permet de spécifier des produits individuels qui ne doivent *pas* être inclus dans le calcul de la remise ou des frais.
      - **Effet de la modification de ce paramètre :** La valeur de ces produits sera soustraite du total du panier *avant* que le pourcentage ou le montant fixe ne soit calculé.
      - **Valeur recommandée :** Laissez vide sauf si des produits spécifiques doivent être exemptés.
      - **Scénario / exemple marchand :** Vous vendez des produits à faible marge où l'application de frais les rendrait non rentables, vous les excluez donc.
    - **Statut (Activer/Désactiver) :**
      - **Ce que fait ce paramètre :** Active ou désactive une règle individuelle sans la supprimer.
      - **Effet de la modification de ce paramètre :**
        - *Activé :* La règle est active et sera appliquée.
        - *Désactivé :* La règle est inactive et ne sera pas appliquée.
      - **Valeur recommandée :** Activé pour les règles actives.
      - **Scénario / exemple marchand :** Vous souhaitez suspendre temporairement une règle pour une promotion sans perdre sa configuration.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**

  1. Commencez par identifier les modes de paiement qui entraînent des coûts ou offrent des avantages que vous souhaitez répercuter.
  2. Cliquez sur « Ajouter une nouvelle règle ».
  3. Donnez un nom clair à la règle.
  4. Sélectionnez le mode de paiement cible.
  5. Choisissez « Frais » ou « Remise » et entrez la valeur (pourcentage ou fixe).
  6. Affinez la règle avec les montants minimum/maximum du panier, les groupes de clients, les pays ou les exclusions de produits si nécessaire.
  7. Activez la règle et enregistrez.
  8. Testez la règle sur votre front office en passant une commande test.

### 2.3 Écran d'administration dédié : Journal d'audit des remises ou frais de paiement (Back Office > Paiement > Journal d'audit des remises ou frais de paiement)

Cet écran fournit un historique de toutes les instances où le module a appliqué une remise ou des frais.

- **Nom de l'écran et emplacement du menu :** **Journal d'audit des remises ou frais de paiement** (situé sous **Paiement** dans le menu principal du Back Office de PrestaShop).
- **Actions et paramètres disponibles :**
  - **Tableau de liste des journaux :** Affiche les entrées avec des détails tels que :
    - **ID de commande :** L'ID de la commande où l'ajustement a été appliqué.
    - **Nom du client :** Le client qui a passé la commande.
    - **Mode de paiement :** Le mode de paiement choisi.
    - **Règle appliquée :** Le nom de la règle qui a déclenché l'ajustement.
    - **Type d'ajustement :** S'il s'agissait d'une remise ou de frais.
    - **Valeur d'ajustement :** Le montant de la remise ou des frais.
    - **Date :** Quand l'ajustement a été appliqué.
  - **Filtrage et recherche :** Vous pouvez filtrer le journal par ID de commande, client, mode de paiement ou date pour trouver rapidement des entrées spécifiques.
  - **Effet des modifications :** Cet écran est uniquement destiné à la visualisation ; vous ne pouvez pas modifier directement les entrées du journal ici. Il sert de registre précieux pour le dépannage et l'analyse.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  - Examinez régulièrement le journal d'audit pour vous assurer que les règles sont appliquées correctement.
  - Utilisez-le pour résoudre les demandes des clients concernant les écarts de prix.
  - Surveillez le volume des ajustements pour comprendre l'impact de vos règles.

### 2.4 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activer le module | OUI | Interrupteur principal pour la fonctionnalité du module. |
|  | Afficher les frais/remises dans le récapitulatif du panier | OUI | Affiche l'ajustement tôt dans le panier pour la transparence. |
|  | Appliquer les frais/remises aux frais de port | OUI | Inclut les frais de port dans le calcul des frais/remises. |
|  | Appliquer les frais/remises à la taxe | OUI | Inclut la taxe dans le calcul des frais/remises. |
|  | Libellé des frais/remises dans le panier/la commande | « Ajustement du mode de paiement » | Personnalise le libellé affiché aux clients. |
|  | URL de la tâche Cron pour le nettoyage du journal d'audit | (URL fournie) | Automatise le nettoyage des anciennes entrées du journal d'audit. |
| **Règles de remise ou de frais de paiement** | Nom de la règle | (Nom descriptif) | Nom interne de la règle. |
|  | Mode de paiement | (Méthode spécifique) | Sélectionne le mode de paiement pour la règle. |
|  | Type | Frais / Remise | Détermine s'il s'agit d'une augmentation ou d'une diminution. |
|  | Valeur | (Valeur numérique) | Le montant ou le pourcentage de l'ajustement. |
|  | Type de valeur | Pourcentage / Montant fixe | Comment la « Valeur » est interprétée. |
|  | Montant minimum du panier | (Vide) | Total minimum de la commande pour que la règle s'applique. |
|  | Montant maximum du panier | (Vide) | Total maximum de la commande pour que la règle s'applique. |
|  | Groupes de clients | Tous les groupes de clients | Restreint la règle à des groupes de clients spécifiques. |
|  | Pays | Tous les pays | Restreint la règle à des pays spécifiques. |
|  | Produits à exclure | (Vide) | Produits dont la valeur est exclue du calcul. |
|  | Statut | Activé | Active ou désactive la règle. |
| **Journal d'audit des remises ou frais de paiement** | (Tous les champs) | (Lecture seule) | Fournit un historique des ajustements appliqués. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Mes remises/frais n'apparaissent pas sur la page de commande. Que dois-je vérifier ?**
R1 :

- **Module activé ?** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que « Remise ou Frais de Paiement » est activé.
- **Règles actives ?** Naviguez vers **Paiement > Règles de remise ou de frais de paiement** et vérifiez que vos règles spécifiques sont activées (colonne Statut).
- **Conditions de la règle remplies ?** Vérifiez si les conditions de total du panier, de groupe de clients, de pays ou de produits exclus de vos règles sont remplies par votre commande test.
- **Mode de paiement sélectionné ?** L'ajustement n'apparaît *qu'après* la sélection d'un mode de paiement sur la page de commande (sauf si « Afficher les frais/remises dans le récapitulatif du panier » est activé).
- **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (en haut à droite). Parfois, d'anciennes données mises en cache empêchent les modifications d'apparaître immédiatement.

**Q2 : Le montant de la remise/des frais semble incorrect.**
R2 :

- **Type de valeur (Pourcentage vs. Fixe) :** Assurez-vous d'avoir sélectionné le bon « Type de valeur » (Pourcentage ou Montant fixe) pour votre règle.
- **Appliquer aux frais de port/taxes :** Vérifiez dans la configuration principale du module si « Appliquer les frais/remises aux frais de port » et « Appliquer les frais/remises à la taxe » sont activés ou désactivés, car cela affecte le montant de base pour les calculs de pourcentage.
- **Produits exclus :** Si vous avez des produits exclus du calcul, assurez-vous que leur valeur est correctement soustraite avant que le pourcentage/montant fixe ne soit appliqué.
- **Devise :** Assurez-vous que la devise par défaut de votre boutique est correctement définie dans PrestaShop, car le module s'appuie sur cela pour les montants fixes.

**Q3 : Le module est en conflit avec un autre module ou mon thème.**
R3 :

- **Identifier le conflit :** Essayez de désactiver d'autres modules un par un pour identifier celui qui cause le conflit.
- **Surcharges de thème :** Si vous avez un thème fortement personnalisé, il pourrait surcharger les modèles de paiement de base de PrestaShop sur lesquels le module s'appuie. Vérifiez le dossier `templates/checkout/` de votre thème pour des fichiers comme `payment.tpl` ou `cart-summary.tpl`.
- **Contacter le support :** Si vous suspectez un conflit, rassemblez les détails (messages d'erreur, étapes pour reproduire) et contactez le support MyPresta.eu.

**Q4 : Comment traduire le « Libellé des frais/remises » dans d'autres langues ?**
R4 :

- Allez dans **International > Traductions**.
- Sélectionnez « Traductions des modules installés », votre thème et la langue que vous souhaitez traduire.
- Trouvez le module « Remise ou Frais de Paiement ». Vous devriez voir le champ pour traduire le paramètre « Libellé des frais/remises dans le panier/la commande ».

**Q5 : Mon journal d'audit devient trop volumineux. Comment le gérer ?**
R5 :

- Dans la configuration principale du module, vous trouverez une « URL de la tâche Cron pour le nettoyage du journal d'audit ».
- Copiez cette URL et configurez-la comme tâche cron sur votre serveur d'hébergement. La plupart des panneaux de contrôle d'hébergement (cPanel, Plesk) ont une section « Tâches Cron » où vous pouvez ajouter une nouvelle tâche.
- Configurez-la pour qu'elle s'exécute quotidiennement ou hebdomadairement (par exemple, `wget -q -O /dev/null "VOTRE_URL_CRON_ICI"`). Cela supprimera automatiquement les anciennes entrées de journal et maintiendra votre base de données optimisée.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé du module « Remise ou Frais de Paiement » pour les développeurs, les webmasters et les agences techniques.

### 4.1 Vue d'ensemble de l'architecture

Le module « Remise ou Frais de Paiement » suit un modèle MVC (Modèle-Vue-Contrôleur) PrestaShop standard, avec un fort accent sur les hooks pour s'intégrer au flux de commande. Il utilise `ObjectModel` pour gérer les règles et les journaux d'audit, et des contrôleurs personnalisés pour les interactions AJAX du front-office et la gestion du back-office. La logique principale de calcul et d'application des frais/remises est encapsulée dans des classes de moteur dédiées, garantissant la séparation des préoccupations. Des classes de compatibilité sont utilisées pour combler les différences entre PrestaShop 1.7, 8 et 9.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `controllers/front/ajax.php`
  - **Nom de la classe :** `PaydisorfeeAjaxModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** Gère les requêtes AJAX depuis la page de commande. Lorsqu'un client sélectionne un mode de paiement, ce contrôleur reçoit la requête, calcule la remise/les frais applicables en fonction des règles actives et renvoie les données récapitulatives du panier mises à jour (par exemple, nouveau total, ligne de frais/remise) à afficher dynamiquement.
- `controllers/front/cron.php`
  - **Nom de la classe :** `PaydisorfeeCronModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** Fournit le point d'accès pour la tâche cron de nettoyage du journal d'audit. Lorsqu'il est accédé, il déclenche la logique de nettoyage au sein du module, supprimant les anciennes entrées de journal en fonction des politiques de rétention configurées.
- `controllers/front/index.php`
  - **Nom de la classe :** `PaydisorfeeIndexModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** Un contrôleur frontal de substitution, généralement utilisé pour les pages de module par défaut ou pour empêcher la liste des répertoires. Dans ce module, sa fonction principale pourrait être de gérer le routage par défaut si aucune action spécifique n'est demandée, ou il pourrait rediriger vers la page principale de la boutique.

#### Contrôleurs d'administration Back-Office

- `controllers/admin/AdminPaydisorfeeAuditLog.php`
  - **Nom de la classe :** `AdminPaydisorfeeAuditLogController` (étend `ModuleAdminController`)
  - **Nom de l'onglet :** Journal d'audit des remises ou frais de paiement
  - **Entité gérée :** `PaydisorfeeAuditLog` (correspond à la table de base de données `paydisorfee_log`)
  - **Responsabilité :** Gère l'affichage et le filtrage des entrées du journal d'audit dans le Back Office de PrestaShop. Il utilise `HelperList` pour afficher la vue en grille des enregistrements de journal.
- `controllers/admin/AdminPaydisorfeeRules.php`
  - **Nom de la classe :** `AdminPaydisorfeeRulesController` (étend `ModuleAdminController`)
  - **Nom de l'onglet :** Règles de remise ou de frais de paiement
  - **Entité gérée :** `PaydisorfeeRule` (correspond à la table de base de données `paydisorfee_rule`)
  - **Responsabilité :** Fournit l'interface pour créer, modifier, supprimer et lister les règles de remise/frais de paiement. Il utilise `HelperList` pour l'aperçu des règles et `HelperForm` pour les formulaires d'ajout/modification de règles, y compris les sélecteurs dynamiques pour les produits, les groupes de clients et les pays.
- `controllers/admin/index.php`
  - **Nom de la classe :** `PaydisorfeeAdminIndexModuleFrontController` (étend `ModuleAdminController`)
  - **Responsabilité :** Similaire au `index.php` frontal, cela pourrait servir de contrôleur d'administration par défaut ou de redirigeur si aucune action spécifique n'est demandée pour le contexte d'administration.

### 4.3 Classes et modèles principaux (`classes/`)

- `classes/index.php` : Fichier vide standard pour empêcher la liste des répertoires.
- `classes/PaydisorfeeAdmin.php`
  - **Responsabilité :** Contient probablement des méthodes d'aide ou des fonctions utilitaires spécifiques à l'administration du Back Office, potentiellement pour gérer les soumissions de formulaires, la validation des données ou le rendu de composants d'administration spécifiques.
- `classes/PaydisorfeeAuditLog.php`
  - **Étend :** `ObjectModel`
  - **Table de base de données :** `paydisorfee_log`
  - **Champs `$definition` :** Définit la structure des entrées du journal d'audit (par exemple, `id_order`, `id_customer`, `payment_method`, `rule_name`, `type`, `value`, `date_add`).
  - **Méthodes publiques clés :** Méthodes pour ajouter de nouvelles entrées de journal, récupérer les données du journal et potentiellement pour les opérations de nettoyage.
- `classes/PaydisorfeeCartState.php`
  - **Responsabilité :** Gère l'état du panier pendant le processus de commande, spécifiquement lié à la remise/aux frais appliqués par le module. Il stocke et récupère probablement l'ajustement calculé pour s'assurer qu'il persiste à travers les différentes étapes de la commande et est correctement appliqué à la commande.
- `classes/PaydisorfeeCompatibility.php`
  - **Responsabilité :** Contient des méthodes pour gérer les problèmes de compatibilité entre les différentes versions de PrestaShop (1.7.x, 8.x, 9.x). Cette classe abstrait le code spécifique à la version, tel que les différences dans les noms de hook, les structures de classe ou les appels d'API, garantissant que le module fonctionne correctement sur toutes les versions prises en charge.
- `classes/PaydisorfeeDashboard.php`
  - **Responsabilité :** Fournit probablement des données ou une logique pour un tableau de bord ou une vue analytique potentielle au sein de l'interface d'administration du module, résumant l'impact des remises/frais.
- `classes/PaydisorfeeEngine.php`
  - **Responsabilité :** C'est la classe de logique principale pour calculer et appliquer la remise ou les frais. Elle prend le panier actuel, le mode de paiement sélectionné et les règles actives en entrée, puis détermine le montant de l'ajustement final. Elle gère les calculs de pourcentage vs. fixe, les montants minimum/maximum du panier et les exclusions de produits.
- `classes/PaydisorfeeFeeProduct.php`
  - **Responsabilité :** Potentiellement une classe d'aide pour créer un « produit virtuel » afin de représenter les frais/remises dans le panier, lui permettant d'être affiché comme une ligne. C'est une technique courante dans PrestaShop pour intégrer des ajustements de prix dynamiques dans le récapitulatif du panier.
- `classes/PaydisorfeeLog.php`
  - **Responsabilité :** Il pourrait s'agir d'un alias ou d'une ancienne version de `PaydisorfeeAuditLog.php`, ou d'un mécanisme de journalisation plus simple à des fins de débogage.
- `classes/PaydisorfeeRule.php`
  - **Étend :** `ObjectModel`
  - **Table de base de données :** `paydisorfee_rule`
  - **Champs `$definition` :** Définit la structure d'une règle de paiement (par exemple, `name`, `id_payment_module`, `type`, `value`, `value_type`, `min_cart_amount`, `max_cart_amount`, `customer_groups`, `countries`, `excluded_products`, `active`).
  - **Méthodes publiques clés :** Méthodes pour les opérations CRUD sur les règles, la récupération des règles actives et la validation des conditions de règle.

### 4.4 Actifs JavaScript (`views/js/`)

- `paydisorfee/lib/searchTool/views/js/autocomplete.js`
  - **Portée :** Back-office (utilisé dans `AdminPaydisorfeeRules` pour le sélecteur d'exclusion de produits).
  - **Description :** Fournit une fonctionnalité d'autocomplétion pour la recherche de produits lors de la configuration du champ « Produits à exclure » dans une règle. Il envoie probablement des requêtes AJAX à un contrôleur de back-office pour récupérer des suggestions de produits.
- `paydisorfee/views/js/adminPaydisorfeeDashboard.js`
  - **Portée :** Back-office (si une vue de tableau de bord existe).
  - **Description :** JavaScript pour toutes les fonctionnalités de tableau de bord ou d'analyse au sein de l'interface d'administration du module. Cela pourrait inclure le rendu de graphiques, le filtrage de données ou le chargement de contenu dynamique.
- `paydisorfee/views/js/adminPaydisorfeeSelector.js`
  - **Portée :** Back-office (utilisé dans `AdminPaydisorfeeRules`).
  - **Description :** Gère la sélection dynamique des groupes de clients, des pays et potentiellement des modes de paiement dans le formulaire de configuration des règles. Il pourrait gérer des boîtes de sélection multiples ou fournir des éléments interactifs pour ces champs.
- `paydisorfee/views/js/checkout.js`
  - **Portée :** Front-office (page de commande).
  - **Description :** C'est un script essentiel pour la fonctionnalité front-office. Il écoute les changements dans le mode de paiement sélectionné sur la page de commande. Lorsqu'un mode de paiement est choisi, il déclenche un appel AJAX à `controllers/front/ajax.php` pour recalculer le total du panier et mettre à jour dynamiquement le récapitulatif de la commande avec la nouvelle ligne de remise/frais. Il gère également la logique d'affichage de ces mises à jour.

### 4.5 Feuilles de style CSS (`views/css/`)

- `paydisorfee/lib/searchTool/views/css/autocomplete.css`
  - **Portée :** Back-office.
  - **Description :** Styles pour le champ de recherche d'autocomplétion et sa liste déroulante de suggestions, utilisés dans le sélecteur d'exclusion de produits dans la configuration des règles.
- `paydisorfee/views/css/admin_paydisorfee.css`
  - **Portée :** Back-office.
  - **Description :** Style général pour les pages du Back Office du module, y compris la liste des règles, le journal d'audit et les formulaires de configuration. Il assure une apparence cohérente avec le thème d'administration de PrestaShop.
- `paydisorfee/views/css/front.css`
  - **Portée :** Front-office.
  - **Description :** Styles pour l'affichage de la ligne de remise/frais et de tout message connexe sur la page de commande ou le récapitulatif du panier. Il garantit que l'ajustement est clairement visible et bien intégré à la conception de la boutique.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- `paydisorfee/lib/searchTool/views/scripts.tpl`
  - **Portée :** Back-office.
  - **Description :** Contient le code Smarty pour inclure JavaScript et potentiellement CSS pour l'outil de recherche (par exemple, `autocomplete.js`). Il est probablement inclus dans le formulaire `AdminPaydisorfeeRules`.
- `paydisorfee/views/templates/admin/auditPreview.tpl`
  - **Portée :** Back-office (AdminPaydisorfeeAuditLogController).
  - **Description :** Modèle pour le rendu des entrées du journal d'audit, généralement utilisé par `HelperList` pour afficher la grille de données.
- `paydisorfee/views/templates/admin/cron_setup.tpl`
  - **Portée :** Back-office (Configuration principale du module).
  - **Description :** Affiche l'URL de la tâche cron et les instructions pour la configurer, comme on le voit sur la page de configuration principale du module.
- `paydisorfee/views/templates/admin/rulesPreview.tpl`
  - **Portée :** Back-office (AdminPaydisorfeeRulesController).
  - **Description :** Modèle pour le rendu de la liste des règles de paiement, utilisé par `HelperList` pour afficher la grille de données.
- `paydisorfee/views/templates/admin/scopeSelector.tpl`
  - **Portée :** Back-office (AdminPaydisorfeeRulesController).
  - **Description :** Modèle pour les sélecteurs dynamiques (groupes de clients, pays, produits à exclure) dans le formulaire de configuration des règles, souvent utilisé en conjonction avec `adminPaydisorfeeSelector.js`.
- `paydisorfee/views/templates/hook/admin_order.tpl`
  - **Portée :** Back-office (Hook `displayAdminOrderTabContent` ou similaire).
  - **Description :** Affiche des informations sur la remise ou les frais de paiement appliqués dans la page de détail de la commande de PrestaShop dans le Back Office. Cela permet aux administrateurs de voir l'ajustement directement sur la commande.
- `paydisorfee/views/templates/hook/payment_top.tpl`
  - **Portée :** Front-office (Hook `displayPaymentTop` ou similaire).
  - **Description :** Ce modèle est probablement utilisé pour afficher les informations dynamiques de remise/frais sur la page de commande, généralement au-dessus de la sélection du mode de paiement, ou dans le cadre du récapitulatif de la commande. Il est mis à jour par `checkout.js` via AJAX.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

- `ps_paydisorfee_log` : Stocke les entrées du journal d'audit pour chaque remise ou frais appliqué.
  - `id_paydisorfee_log` (CLÉ PRIMAIRE)
  - `id_order` (INT)
  - `id_customer` (INT)
  - `payment_method` (VARCHAR)
  - `rule_name` (VARCHAR)
  - `type` (VARCHAR, ‘discount’ ou ‘fee’)
  - `value` (DECIMAL)
  - `date_add` (DATETIME)
- `ps_paydisorfee_rule` : Stocke la configuration de chaque règle de remise/frais de paiement.
  - `id_paydisorfee_rule` (CLÉ PRIMAIRE)
  - `name` (VARCHAR)
  - `id_payment_module` (INT)
  - `type` (VARCHAR, ‘discount’ ou ‘fee’)
  - `value` (DECIMAL)
  - `value_type` (VARCHAR, ‘percentage’ ou ‘fixed’)
  - `min_cart_amount` (DECIMAL)
  - `max_cart_amount` (DECIMAL)
  - `customer_groups` (TEXT, tableau sérialisé d'ID)
  - `countries` (TEXT, tableau sérialisé d'ID)
  - `excluded_products` (TEXT, tableau sérialisé d'ID)
  - `active` (TINYINT)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_configuration` : Les paramètres du module sont stockés ici avec des clés comme `PAYDISORFEE_ENABLED`, `PAYDISORFEE_DISPLAY_CART`, `PAYDISORFEE_APPLY_SHIPPING`, `PAYDISORFEE_APPLY_TAX`, `PAYDISORFEE_LABEL`.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionFrontControllerSetMedia` | Avant le rendu du contrôleur frontal | Enregistre le CSS (`front.css`) et le JS (`checkout.js`) du front-office. |
| `actionAdminControllerSetMedia` | Avant le rendu du contrôleur d'administration | Enregistre le CSS (`admin_paydisorfee.css`, `autocomplete.css`) et le JS (`adminPaydisorfeeDashboard.js`, `adminPaydisorfeeSelector.js`, `autocomplete.js`) du back-office. |
| `displayHeader` | Dans la section `<head>` de chaque page | Potentiellement pour charger des JS/CSS globaux ou des balises meta. |
| `displayPaymentTop` | En haut du bloc de sélection de paiement sur la page de commande | Affiche les informations dynamiques de frais/remises au client. |
| `actionCartSummary` | Après la génération du récapitulatif du panier | Utilisé pour injecter la ligne de frais/remises dans le récapitulatif du panier. |
| `actionPaymentConfirmation` | Après qu'une commande a été passée avec succès | Enregistre la remise/les frais appliqués dans le journal d'audit. |
| `actionValidateOrder` | Lors de la validation d'une commande | S'assure que le total final de la commande reflète l'ajustement du mode de paiement. |
| `displayAdminOrderTabContent` | Dans la page de détail de la commande dans le Back Office | Affiche les détails de l'ajustement de paiement pour la commande. |
| `displayAdminOrder` | Sur la page de détail de la commande dans le Back Office | Similaire à `displayAdminOrderTabContent`, pour afficher les données du module spécifiques à la commande. |
| `actionGetExtraMailTemplateVars` | Avant l'envoi d'un e-mail de confirmation de commande | Injecte les détails des frais/remises dans les modèles d'e-mail. |
| `actionObjectOrderAddAfter` | Après l'ajout d'un nouvel objet commande | Potentiellement pour le traitement final ou la journalisation liée à la commande. |
| `actionObjectOrderUpdateAfter` | Après la mise à jour d'un objet commande | Potentiellement pour réévaluer les frais si une commande est modifiée. |
| `actionObjectCartUpdateAfter` | Après la mise à jour d'un objet panier | Déclenche le recalcul des frais/remises potentiels. |
| `actionObjectCartAddAfter` | Après l'ajout d'un nouvel objet panier | Déclenche le recalcul des frais/remises potentiels. |
| `actionAjaxDie` | Avant `die()` dans le contexte AJAX | Permet au module d'effectuer des actions avant l'envoi de la réponse AJAX. |
| `displayBackOfficeHeader` | Dans la section `<head>` de chaque page du Back Office | Enregistre les JS/CSS d'administration globaux. |
| `displayModuleConfigureExtraButtons` | Sur la page de configuration du module | Ajoute des boutons supplémentaires (par exemple, « Gérer les règles », « Afficher le journal d'audit »). |
| `displayPaymentOptions` | Affiche les options de paiement à la commande | Potentiellement modifie les options de paiement en fonction des règles. |
| `actionPaymentOptionsModifier` | Modifie les options de paiement avant l'affichage | Permet au module d'ajouter/supprimer/modifier les options de paiement. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Remise ou Frais de Paiement », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité et l'intégration du module.
"""
