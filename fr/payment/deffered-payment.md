---
title: "Paiement Différé - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Paiement Différé par MyPresta.eu."
sidebar:
  label: "Paiement Différé - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Deffered Payment sur MyPresta.eu](https://mypresta.eu/modules/payment-process/deffered-payment.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/payment/deffered-payment/)
>
> ---


# Paiement Différé

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et généralement suffisantes pour ce module. Aucune extension inhabituelle n'est nécessaire.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Paiement Différé)

C'est l'écran de configuration principal où vous définissez le comportement essentiel du module Paiement Différé.

- **Emplacement du menu :** Back Office > Modules > Gestionnaire de modules > Rechercher « Paiement Différé » > Cliquer sur « Configurer »

#### Paramètres généraux

| Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- |
| **Activer le Paiement Différé** | OUI | **Ce que fait ce paramètre :** C'est l'interrupteur principal du module.   **Effet de la modification de ce paramètre :**   *Lorsqu'il est activé :* L'option Paiement Différé sera disponible à la caisse pour les clients éligibles.   *Lorsqu'il est désactivé :* L'option Paiement Différé sera masquée pour tous les clients, quelles que soient les autres configurations.   **Valeur recommandée :** OUI (pour utiliser le module).   **Scénario marchand :** Activez-le lorsque vous êtes prêt à offrir cette méthode de paiement. |
| **Groupes de clients autorisés** | (Sélectionner les groupes pertinents) | **Ce que fait ce paramètre :** Détermine quels groupes de clients peuvent voir et utiliser l'option Paiement Différé.   **Effet de la modification de ce paramètre :**   *Lorsqu'ils sont sélectionnés :* Seuls les clients appartenant aux groupes choisis verront le Paiement Différé à la caisse.   *Lorsqu'ils ne sont pas sélectionnés :* Les clients des groupes non sélectionnés ne verront pas cette option.   **Valeur recommandée :** Sélectionnez des groupes spécifiques (par exemple, « Grossistes », « Clients VIP »). Évitez « Tous les clients » sauf si vous avez l'intention d'offrir le paiement différé à tout le monde.   **Scénario marchand :** Vous avez un groupe « Clients B2B ». Sélectionnez uniquement ce groupe afin que seuls vos clients professionnels puissent utiliser le paiement différé. |
| **Jours d'échéance du paiement** | 30 | **Ce que fait ce paramètre :** Définit le nombre de jours après la passation d'une commande pendant lesquels le paiement est dû.   **Effet de la modification de ce paramètre :** Cette valeur sera utilisée pour calculer la date d'échéance du paiement affichée au client et pour le suivi interne.   **Valeur recommandée :** 30 (courant pour les conditions net-30), 7, 14, 60, etc., selon votre politique commerciale.   **Scénario marchand :** Réglez sur 30 pour des conditions de paiement « Net 30 ». |
| **Total minimum de commande pour le Paiement Différé** | 0.00 | **Ce que fait ce paramètre :** Définit une valeur de commande minimale (dans votre devise par défaut) qu'une commande doit atteindre pour être éligible au paiement différé.   **Effet de la modification de ce paramètre :**   *Si le total de la commande est inférieur à cette valeur :* Le Paiement Différé ne sera pas disponible, même pour les groupes de clients éligibles.   *Si le total de la commande est supérieur ou égal à cette valeur :* Le Paiement Différé sera disponible (si les autres conditions sont remplies).   **Valeur recommandée :** 0.00 (pas de minimum) ou une valeur spécifique (par exemple, 100.00 pour le B2B).   **Scénario marchand :** Vous ne souhaitez offrir le paiement différé que pour les commandes importantes, vous le réglez donc sur 500.00. |
| **Statut de commande pour le Paiement Différé** | En attente de paiement différé | **Ce que fait ce paramètre :** Spécifie le statut initial de la commande qui sera attribué aux commandes passées en utilisant la méthode de Paiement Différé.   **Effet de la modification de ce paramètre :** Ce statut sera visible dans votre liste de commandes du Back Office et pour le client dans son historique de commandes. Il vous aide à identifier rapidement les commandes en attente de paiement.   **Valeur recommandée :** Créez un statut spécifique comme « En attente de paiement différé » ou « Paiement dû » dans **Statuts de commande** (Back Office > Paramètres de la boutique > Paramètres de commande > Statuts) et sélectionnez-le ici.   **Scénario marchand :** Vous souhaitez un statut clair pour différencier ces commandes de « En attente de virement bancaire » ou « Paiement accepté ». |
| **URL de la tâche Cron** | (URL affichée) | **Ce que fait ce paramètre :** Cette URL est utilisée pour déclencher des tâches automatisées liées aux paiements différés (par exemple, vérifier les dates d'échéance, envoyer des rappels, si de telles fonctionnalités sont implémentées ou étendues).   **Effet de la modification de ce paramètre :** Il s'agit d'un champ en lecture seule. Vous devez configurer une tâche cron sur votre serveur pour visiter cette URL régulièrement (par exemple, une fois par jour).   **Valeur recommandée :** Copiez cette URL et ajoutez-la au planificateur de tâches cron de votre serveur.   **Scénario marchand :** Vous souhaitez automatiser tous les processus d'arrière-plan que le module pourrait avoir, tels que la mise à jour des statuts de commande ou l'envoi de notifications. |

#### Produits cibles (Éligibilité de produits spécifiques)

Cette section vous permet de restreindre le paiement différé à des produits ou catégories spécifiques.

| Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- |
| **Appliquer uniquement à des produits spécifiques** | NON | **Ce que fait ce paramètre :** Détermine si l'option de paiement différé est limitée aux commandes ne contenant que des produits spécifiques.   **Effet de la modification de ce paramètre :**   *Lorsqu'il est activé :* L'option « Paiement Différé » n'apparaîtra à la caisse que si *tous* les produits du panier figurent sur votre liste approuvée.   *Lorsqu'il est désactivé :* Le module s'appliquera en fonction des groupes de clients et du total minimum de commande, quels que soient les produits spécifiques.   **Valeur recommandée :** NON (pour une utilisation générale) ou OUI (pour des scénarios très spécifiques).   **Scénario marchand :** Vous n'offrez le paiement différé que pour vos produits « Services Premium » de grande valeur. Vous activez ceci et ajoutez ces produits ci-dessous. |
| **Produits autorisés pour le paiement différé** | (Vide) | **Ce que fait ce paramètre :** Si « Appliquer uniquement à des produits spécifiques » est activé, ce champ vous permet de rechercher et d'ajouter des produits spécifiques.   **Effet de la modification de ce paramètre :** Seules les commandes contenant ces produits (et aucun autre) seront éligibles au paiement différé.   **Valeur recommandée :** Ajoutez les produits pertinents si « Appliquer uniquement à des produits spécifiques » est OUI.   **Scénario marchand :** Vous ajoutez « Produit A » et « Produit B ». Si le panier d'un client contient « Produit A » et « Produit C », le paiement différé ne sera pas disponible. S'il ne contient que « Produit A », il le sera. |

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module ajoute plusieurs nouvelles sections à votre menu Back Office de PrestaShop pour gérer les paiements différés.

#### 2.2.1 Utilisateurs du paiement différé (Back Office > Paiement Différé > Utilisateurs du paiement différé)

Cet écran vous permet de gérer les autorisations individuelles des clients pour le paiement différé, en annulant ou en complétant les paramètres des groupes de clients.

- **Nom de l'écran et emplacement du menu :** Back Office > Paiement Différé > Utilisateurs du paiement différé
- **Actions et paramètres disponibles :**
  - **Tableau de liste :** Affiche une liste des clients qui ont été spécifiquement autorisés ou refusés l'accès au paiement différé.
  - **Ajouter un nouveau / Modifier un utilisateur :**
    - **Recherche client :** Trouvez un client spécifique par nom ou e-mail.
    - **Activer le paiement différé :** Interrupteur OUI/NON pour accorder ou révoquer l'accès au paiement différé pour ce client individuel.
    - **Jours d'échéance du paiement (Priorité) :** Définissez éventuellement un nombre personnalisé de jours d'échéance du paiement pour ce client spécifique, annulant le paramètre global.
    - **Limite de crédit :** Définissez un montant maximal impayé (dans votre devise par défaut, basé sur `PS_CURRENCY_DEFAULT`) que ce client peut avoir sur les commandes à paiement différé.
  - **Effet des modifications :**
    - L'ajout d'un client et l'activation du paiement différé lui accordent l'accès, même si son groupe n'est pas sélectionné dans la configuration principale du module.
    - La désactivation pour un client révoque son accès, même si son groupe est sélectionné.
    - Les jours d'échéance personnalisés et les limites de crédit s'appliquent uniquement à ce client spécifique.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Utilisez cette section pour accorder des conditions de paiement différé spéciales à des clients VIP individuels ou pour bloquer des clients problématiques.
  2. Révisez régulièrement les limites de crédit pour les utilisateurs de paiement différé à volume élevé.

#### 2.2.2 Journal d'activité du paiement différé (Back Office > Paiement Différé > Journal d'activité)

Cet écran fournit un historique des actions et des événements liés aux paiements différés.

- **Nom de l'écran et emplacement du menu :** Back Office > Paiement Différé > Journal d'activité
- **Actions et paramètres disponibles :**
  - **Tableau de liste :** Affiche un journal des événements, qui peut inclure :
    - Quand une commande à paiement différé a été passée.
    - Quand un paiement a été marqué comme reçu.
    - Modifications des paramètres utilisateur du paiement différé.
    - Exécutions de tâches cron.
  - **Colonnes :** Inclut généralement Date/Heure, Type d'événement, Commande/Client associé, Description.
- **Effet des modifications :** Il s'agit d'un journal en lecture seule. Vous ne pouvez pas modifier directement les entrées ici, mais il fournit des informations précieuses pour l'audit et le dépannage.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Vérifiez périodiquement le journal pour surveiller l'activité des paiements différés et vous assurer que tout fonctionne correctement.
  2. Utilisez-le pour enquêter sur tout problème signalé par les clients concernant leurs commandes à paiement différé.

#### 2.2.3 Tableau de bord (Back Office > Paiement Différé > Tableau de bord)

Cet écran (probablement représenté par `defpay/controllers/admin/index.php`) fournirait généralement un aperçu ou un résumé des activités de paiement différé.

- **Nom de l'écran et emplacement du menu :** Back Office > Paiement Différé > Tableau de bord (ou élément de menu principal « Paiement Différé »)
- **Actions et paramètres disponibles :**
  - **Vue grille / Gestion :** Cet écran présente probablement des statistiques clés, des paiements en attente, des paiements en retard ou un résumé rapide des commandes à paiement différé. Il pourrait offrir des filtres ou des capacités de recherche.
- **Effet des modifications :** Il s'agit principalement d'un tableau de bord informatif. Toute action entreprise (par exemple, marquer une commande comme payée) redirigerait généralement vers la page de commande spécifique ou un autre écran de gestion.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Utilisez-le comme votre aperçu principal pour identifier rapidement les commandes nécessitant une attention (par exemple, dates d'échéance approchantes, paiements en retard).
  2. Surveillez la santé globale de votre système de paiement différé.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
|---|---|---|
| **Configuration du module** | Activer le Paiement Différé | OUI | Interrupteur principal pour la méthode de paiement. |
| | Groupes de clients autorisés | (Sélectionner les groupes pertinents) | Restreint l'accès à des segments de clients spécifiques. |
| | Jours d'échéance du paiement | 30 | Définit le délai de paiement par défaut en jours. |
| | Total minimum de commande pour le Paiement Différé | 0.00 | Valeur minimale du panier pour l'éligibilité au paiement différé. |
| | Statut de commande pour le Paiement Différé | En attente de paiement différé | Statut initial des commandes passées avec cette méthode. |
| | URL de la tâche Cron | (URL affichée) | URL pour les tâches d'automatisation côté serveur. |
| | Appliquer uniquement à des produits spécifiques | NON | Limite le paiement différé à des produits spécifiques. |
| | Produits autorisés pour le paiement différé | (Vide) | Liste des produits éligibles si « Appliquer uniquement à des produits spécifiques » est OUI. |
| **Utilisateurs du paiement différé** | Recherche client | N/A | Trouver et gérer l'accès individuel des clients. |
| | Activer le paiement différé (par utilisateur) | OUI/NON | Annulation individuelle pour l'accès au paiement différé. |
| | Jours d'échéance du paiement (Priorité) | (Vide pour global) | Conditions de paiement personnalisées pour un client spécifique. |
| | Limite de crédit | (Vide pour aucune limite) | Montant maximal impayé pour un client spécifique. |
| **Journal d'activité** | N/A | N/A | Journal en lecture seule des événements de paiement différé. |
| **Tableau de bord** | N/A | N/A | Aperçu des commandes à paiement différé et des statistiques. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : Pourquoi le Paiement Différé n'apparaît-il pas pour mes clients à la caisse ?**
R :

1.  **Le module est-il activé ?** Vérifiez « Activer le Paiement Différé » dans la configuration du module.
2.  **Les groupes de clients sont-ils corrects ?** Assurez-vous que le client est connecté et appartient à l'un des « Groupes de clients autorisés » sélectionnés dans les paramètres du module.
3.  **Total minimum de commande :** Le total du panier est-il supérieur au « Total minimum de commande pour le Paiement Différé » ?
4.  **Produits spécifiques :** Si « Appliquer uniquement à des produits spécifiques » est activé, le panier contient-il *uniquement* des produits de votre liste approuvée ?
5.  **Paramètres utilisateur individuels :** Vérifiez « Utilisateurs du paiement différé » pour voir si le client a été désactivé individuellement ou a des annulations spécifiques.
6.  **Cache :** Videz le cache de votre PrestaShop (Paramètres avancés > Performances) et le cache de votre navigateur.

**Q : Comment modifier le statut de la commande une fois qu'un paiement différé est reçu ?**
R : Vous devrez mettre à jour manuellement le statut de la commande dans le Back Office de PrestaShop. Allez dans **Commandes > Commandes**, trouvez la commande pertinente et modifiez son statut de « En attente de paiement différé » (ou ce que vous avez configuré) à « Paiement accepté » ou « Livré » selon le cas.

**Q : Puis-je définir des jours d'échéance de paiement différents pour différents clients ?**
R : Oui ! Utilisez l'écran « Utilisateurs du paiement différé ». Vous pouvez rechercher un client spécifique et définir un « Jours d'échéance du paiement (Priorité) » personnalisé pour lui, qui aura la priorité sur le paramètre global.

**Q : À quoi sert l'URL de la tâche Cron et dois-je la configurer ?**
R : L'URL de la tâche Cron est destinée aux tâches automatisées que le module pourrait effectuer en arrière-plan (par exemple, vérifier les paiements en retard, envoyer des notifications, si implémenté). Bien que le module puisse fonctionner sans elle pour le traitement de base des paiements, il est fortement recommandé de la configurer sur votre serveur pour garantir que toutes les fonctionnalités automatisées fonctionnent correctement. Votre hébergeur web ou un développeur peut vous aider à configurer une tâche cron pour visiter cette URL quotidiennement.

**Q : Le module est installé, mais je ne vois pas l'élément de menu « Paiement Différé » dans le Back Office.**
R :

1.  **Permissions :** Vérifiez les permissions de votre employé (Paramètres avancés > Équipe > Employés > Modifier votre profil > onglet Permissions). Assurez-vous d'avoir accès au module « Paiement Différé » et à ses contrôleurs d'administration associés.
2.  **Cache :** Videz le cache de votre PrestaShop (Paramètres avancés > Performances).

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de la structure technique du module Paiement Différé pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module Paiement Différé suit le modèle MVC (Modèle-Vue-Contrôleur) standard de PrestaShop. Il s'intègre en tant que module de paiement, étendant `PaymentModule` et fournissant des contrôleurs d'administration personnalisés pour la gestion des utilisateurs et des journaux de paiement différé. Il utilise le système de configuration de PrestaShop pour les paramètres et les hooks pour l'affichage en front-office et l'intégration des commandes en back-office. Le module introduit des tables de base de données personnalisées (`defpay_log`, `defpayuser`) pour stocker des données spécifiques au paiement différé.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `defpay/controllers/front/cron.php`
  - **Nom de la classe :** `DefPayCronModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** Gère l'exécution des tâches cron. Ce contrôleur est accessible via l'`URL de la tâche Cron` fournie dans la configuration du module. Il est conçu pour être appelé périodiquement par un planificateur cron côté serveur pour effectuer des opérations en arrière-plan comme la vérification des dates d'échéance de paiement, la mise à jour des statuts de commande ou le déclenchement de notifications.
- `defpay/controllers/front/index.php`
  - **Nom de la classe :** `DefPayIndexModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** Un contrôleur frontal de substitution ou par défaut. Souvent utilisé pour le routage de module de base ou si le module a besoin d'un point d'entrée frontal par défaut qui ne correspond pas directement à une action spécifique. Dans ce module, il pourrait ne pas avoir de fonction directe visible par l'utilisateur.
- `defpay/controllers/front/statement.php`
  - **Nom de la classe :** `DefPayStatementModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** Gère probablement l'affichage ou la génération des relevés de paiement différé pour les clients. Il pourrait s'agir d'une page dans la zone du compte client affichant les paiements en attente ou un lien pour télécharger une facture.
- `defpay/controllers/front/validation.php`
  - **Nom de la classe :** `DefPayValidationModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** Le contrôleur principal de validation de paiement. Lorsqu'un client sélectionne « Paiement Différé » à la caisse et confirme la commande, ce contrôleur traite la commande, définit le statut de commande approprié et redirige le client vers la page de confirmation de commande.

#### Contrôleurs d'administration Back-Office

- `defpay/controllers/admin/AdminDefPayActivityLog.php`
  - **Nom de la classe :** `AdminDefPayActivityLogController` (étend `ModuleAdminController`)
  - **Nom de l'onglet :** `Journal d'activité du paiement différé`
  - **Entité gérée :** `defpay_log` (table de base de données personnalisée)
  - **Responsabilité :** Fournit une interface de gestion de liste pour la table `defpay_log`. Affiche un historique des événements liés aux paiements différés, tels que les passations de commande, les changements de statut ou les actions cron.
- `defpay/controllers/admin/AdminDefPayUsers.php`
  - **Nom de la classe :** `AdminDefPayUsersController` (étend `ModuleAdminController`)
  - **Nom de l'onglet :** `Utilisateurs du paiement différé`
  - **Entité gérée :** `defpayuser` (table de base de données personnalisée)
  - **Responsabilité :** Gère les paramètres individuels des clients pour le paiement différé. Permet aux administrateurs d'activer/désactiver le paiement différé pour des clients spécifiques, de définir des jours d'échéance personnalisés et de définir des limites de crédit. Interagit avec la table `ps_currency` (via `PS_CURRENCY_DEFAULT`) pour la devise de la limite de crédit.
- `defpay/controllers/admin/index.php`
  - **Nom de la classe :** `AdminDefPayDashboardController` (probablement, étend `ModuleAdminController`)
  - **Nom de l'onglet :** `Tableau de bord du paiement différé` (ou élément de menu principal)
  - **Entité gérée :** Aucune entité unique directe ; agrège les données.
  - **Responsabilité :** Sert de tableau de bord principal ou d'aperçu pour le module Paiement Différé dans le Back Office. Il affiche probablement des statistiques clés, des résumés des paiements en attente/en retard et des liens rapides vers d'autres sections de gestion.

### 4.3 Classes et modèles principaux (`classes/`)

Les informations de module fournies n'indiquent aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que la logique principale du module, y compris les définitions `ObjectModel` pour `defpay_log` et `defpayuser`, pourrait être directement intégrée dans le fichier principal `defpay/cronjob.php` ou dans les contrôleurs d'administration eux-mêmes. C'est une approche moins courante mais parfois utilisée pour des modules plus simples.

Si `defpay_log` et `defpayuser` sont bien des tables personnalisées, leurs définitions `ObjectModel` (par exemple, les classes `DefPayLog` et `DefPayUser`) se trouveraient généralement dans `classes/`. Sinon, elles sont probablement définies en ligne ou gérées directement via des appels de classe `Db`.

### 4.4 Actifs JavaScript (`views/js/`)

- `defpay/lib/emailTemplatesManager/js/emailTemplatesManager.js`
  - **Portée :** Back-office.
  - **Description :** Fournit probablement des fonctionnalités pour la gestion des modèles d'e-mail dans la configuration du module ou des écrans d'administration spécifiques. Cela pourrait inclure des champs de formulaire dynamiques, la prévisualisation de modèles ou l'enregistrement du contenu des modèles.
- `defpay/lib/searchTool/views/js/autocomplete.js`
  - **Portée :** Back-office (par exemple, `AdminDefPayUsers` pour la recherche de clients, ou la configuration du module pour la recherche de produits).
  - **Description :** Implémente une fonction d'autocomplétion pour les champs de recherche, tels que la recherche de clients ou de produits. Il écoute la saisie de l'utilisateur, effectue des appels AJAX pour récupérer des suggestions et les affiche dans une liste déroulante.
- `defpay/tools/browser-demo-simulator.js`
  - **Portée :** Potentiellement les deux, mais plus probablement pour le développement/test.
  - **Description :** Un script utilitaire, éventuellement pour simuler le comportement du navigateur ou les interactions du module à des fins de test. Non typiquement utilisé dans un environnement de production.
- `defpay/views/js/adminDefPayActivityPreview.js`
  - **Portée :** Back-office (`AdminDefPayActivityLog`).
  - **Description :** Fournit des fonctionnalités interactives pour le journal d'activité, telles que l'expansion des entrées de journal, le filtrage ou la prévisualisation des détails d'une activité.
- `defpay/views/js/adminDefPayCollections.js`
  - **Portée :** Back-office (probablement lié à la gestion des recouvrements de paiement différé).
  - **Description :** Implémente la logique JavaScript pour une interface de gestion des « recouvrements », qui pourrait impliquer de marquer les paiements comme reçus, d'envoyer des rappels ou de gérer les comptes en retard.
- `defpay/views/js/adminDefPayDashboard.js`
  - **Portée :** Back-office (Tableau de bord).
  - **Description :** Alimente les éléments interactifs du tableau de bord du paiement différé, tels que les graphiques dynamiques, le filtrage des données ou les mises à jour AJAX pour les statistiques.
- `defpay/views/js/adminDefPayPortfolio.js`
  - **Portée :** Back-office.
  - **Description :** Probablement lié à la gestion d'un « portefeuille » de comptes ou de commandes à paiement différé, offrant éventuellement un filtrage avancé, des rapports ou des actions en masse.
- `defpay/views/js/defpay_target_products.js`
  - **Portée :** Back-office (Configuration du module).
  - **Description :** Fournit la fonctionnalité JavaScript pour la section « Produits cibles » dans la configuration du module, permettant la recherche, la sélection et la suppression de produits pour l'éligibilité au paiement différé.

### 4.5 Feuilles de style CSS (`views/css/`)

- `defpay/lib/emailTemplatesManager/css/emailTemplatesManager.css`
  - **Portée :** Back-office.
  - **Description :** Styles pour l'interface de gestion des modèles d'e-mail, assurant une apparence cohérente dans le panneau d'administration de PrestaShop.
- `defpay/lib/searchTool/views/css/autocomplete.css`
  - **Portée :** Back-office.
  - **Description :** Styles pour les suggestions de recherche d'autocomplétion, garantissant qu'elles sont visuellement distinctes et conviviales.
- `defpay/views/css/admin_defpay.css`
  - **Portée :** Back-office.
  - **Description :** Style général pour les écrans d'administration personnalisés du module (Tableau de bord, Utilisateurs, Journal d'activité), assurant une conception cohérente dans le Back Office de PrestaShop.
- `defpay/views/css/defpay.css`
  - **Portée :** Front-office.
  - **Description :** Style général pour les composants front-office du module, tels que l'affichage de l'option de paiement sur la page de commande ou les sections du compte client.
- `defpay/views/css/statement-document.css`
  - **Portée :** Front-office (pour l'impression/PDF).
  - **Description :** Styles spécifiques pour la version imprimable ou PDF d'un relevé de paiement différé, optimisés pour la mise en page des documents.
- `defpay/views/css/statement.css`
  - **Portée :** Front-office.
  - **Description :** Styles pour l'affichage à l'écran des relevés de paiement différé dans la zone du compte client.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

- `defpay/views/templates/hook/confirmation.tpl`
  - **Hook :** `displayOrderConfirmation` (ou similaire).
  - **Sortie :** Contenu affiché sur la page de confirmation de commande après qu'une commande à paiement différé est passée, informant le client des conditions de paiement.
- `defpay/views/templates/hook/displayAdminOrder16.tpl`
  - **Hook :** `displayAdminOrder` (PrestaShop 1.6).
  - **Sortie :** Ajoute un bloc d'informations ou d'actions liées au paiement différé sur la page de détails de la commande dans le Back Office de PrestaShop 1.6.
- `defpay/views/templates/hook/displayAdminOrder17.tpl`
  - **Hook :** `displayAdminOrder` (PrestaShop 1.7+).
  - **Sortie :** Similaire à `displayAdminOrder16.tpl`, mais adapté à la page de détails de la commande du Back Office de PrestaShop 1.7+, affichant le statut du paiement différé, la date d'échéance et éventuellement les actions de recouvrement de paiement.
- `defpay/views/templates/hook/displayCustomerAccount.tpl`
  - **Hook :** `displayCustomerAccount` ou `displayMyAccountBlock`.
  - **Sortie :** Ajoute un lien ou un bloc à la page « Mon compte » du client, potentiellement lié à son relevé ou historique de paiement différé.
- `defpay/views/templates/hook/displayOrderDetail.tpl`
  - **Hook :** `displayOrderDetail` (front-office).
  - **Sortie :** Affiche des informations spécifiques au paiement différé (par exemple, date d'échéance, statut de paiement) dans la page de détails de la commande front-office du client.
- `defpay/views/templates/hook/payment.tpl`
  - **Hook :** `displayPayment` (ou `paymentOptions` pour PS 1.7+).
  - **Sortie :** Rend l'option « Paiement Différé » sur la page de sélection du paiement à la caisse.

#### Templates d'administration (`views/templates/admin/`)

- `defpay/views/templates/admin/cron_setup.tpl`
  - **Objectif :** Probablement utilisé dans la page de configuration principale du module (`getContent()`) pour afficher l'URL de la tâche Cron et les instructions.
- `defpay/views/templates/admin/defpay_target_products.tpl`
  - **Objectif :** Rend l'interface pour la sélection de produits spécifiques éligibles au paiement différé dans la configuration du module.

#### Templates Front-office (`views/templates/front/`)

- `defpay/views/templates/front/statement_preview.tpl`
  - **Objectif :** Affiche un aperçu d'un relevé de paiement différé au client dans le front office.
- `defpay/views/templates/front/validation.tpl`
  - **Objectif :** Le template rendu par le contrôleur frontal `validation.php`, généralement un message de confirmation ou un résumé après qu'une commande à paiement différé a été passée avec succès.

#### Templates PDF (`views/templates/pdf/`)

- `defpay/views/templates/pdf/statement.tpl`
  - **Objectif :** Template utilisé pour générer une version PDF d'un relevé ou d'une facture de paiement différé.

#### Templates de bibliothèque (`defpay/lib/emailTemplatesManager/views/` & `defpay/lib/searchTool/views/`)

Ces templates font partie de bibliothèques intégrées au module :

- `defpay/lib/emailTemplatesManager/views/buttonManager.tpl`
- `defpay/lib/emailTemplatesManager/views/createTemplateForm.tpl`
- `defpay/lib/emailTemplatesManager/views/editTemplateForm.tpl`
- `defpay/lib/emailTemplatesManager/views/mainForm.tpl`
- `defpay/lib/emailTemplatesManager/views/selectInput.tpl`
  - **Objectif :** Ces templates sont utilisés pour rendre les différents composants de l'interface de gestion des modèles d'e-mail dans le Back Office.
- `defpay/lib/searchTool/views/scripts.tpl`
  - **Objectif :** Inclut probablement l'initialisation ou la configuration JavaScript pour l'outil de recherche d'autocomplétion.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

- `ps_defpay_log` (ou `defpay_log`) :
  - Stocke les entrées du journal d'activité liées aux paiements différés.
  - Les champs incluent probablement : `id_defpay_log`, `id_order`, `id_customer`, `event_type`, `description`, `date_add`.
- `ps_defpayuser` (ou `defpayuser`) :
  - Stocke les paramètres individuels de paiement différé pour les clients.
  - Les champs incluent probablement : `id_defpayuser`, `id_customer`, `deferred_payment_enabled` (booléen), `payment_due_days_override` (entier), `credit_limit` (décimal), `date_add`, `date_upd`.
- `ps_configuration` :
  - Les paramètres du module y sont stockés avec des clés comme `DEFPAY_ENABLED`, `DEFPAY_GROUPS`, `DEFPAY_DUE_DAYS`, `DEFPAY_MIN_TOTAL`, `DEFPAY_ORDER_STATUS`, `DEFPAY_CRON_URL`, `DEFPAY_TARGET_PRODUCTS_ENABLED`, `DEFPAY_TARGET_PRODUCTS_LIST`.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayPayment` (PS 1.6) | À l'étape de sélection du paiement de la caisse. | Rend l'option « Paiement Différé ». |
| `paymentOptions` (PS 1.7+) | À l'étape de sélection du paiement de la caisse. | Rend l'option « Paiement Différé » (hook moderne). |
| `displayOrderConfirmation` | Après qu'une commande est passée avec succès. | Affiche les détails du paiement différé sur la page de confirmation. |
| `displayCustomerAccount` / `displayMyAccountBlock` | Sur la page « Mon compte » du client. | Ajoute un lien vers les relevés ou l'historique de paiement différé. |
| `displayOrderDetail` | Sur la page de détails de la commande front-office du client. | Affiche des informations spécifiques au paiement différé pour une commande. |
| `displayAdminOrder` (PS 1.6) | Sur la page de détails de la commande dans le Back Office (PS 1.6). | Injecte le statut du paiement différé et les outils de gestion. |
| `displayAdminOrder` (PS 1.7+) | Sur la page de détails de la commande dans le Back Office (PS 1.7+). | Injecte le statut du paiement différé et les outils de gestion. |
| `actionValidateOrder` | Après qu'une commande est validée avec succès. | Utilisé pour effectuer des actions comme la définition du statut initial de la commande à paiement différé, l'enregistrement de l'événement ou la création d'une entrée `defpayuser` si nécessaire. |
| `actionOrderStatusUpdate` | Lorsque le statut d'une commande est modifié. | Peut être utilisé pour déclencher des actions basées sur les changements de statut (par exemple, paiement reçu, en retard). |
| `actionFrontControllerSetMedia` | Avant qu'un contrôleur frontal ne rende sa sortie. | Utilisé pour mettre en file d'attente les actifs CSS et JS du front-office. |
| `actionAdminControllerSetMedia` | Avant qu'un contrôleur d'administration ne rende sa sortie. | Utilisé pour mettre en file d'attente les actifs CSS et JS du back-office. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Vous y trouverez vos modules achetés et l'accès à nos canaux de support.
