---
title: "Frais de Commande Conditionnels - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Frais de Commande Conditionnels par MyPresta.eu."
sidebar:
  label: "Frais de Commande Conditionnels - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Conditional Order Fees sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-order-fees.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/conditional-order-fees/)
>
> ---


# Frais de Commande Conditionnels

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL) généralement disponibles sur la plupart des environnements d'hébergement compatibles PrestaShop.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Frais de Commande Conditionnels)

C'est l'écran de configuration principal où vous activez ou désactivez le module et configurez le « produit » fondamental qui représente vos frais.

- **Emplacement du menu :** Back Office > Modules > Gestionnaire de modules > Frais de Commande Conditionnels > Configurer

#### Paramètres généraux

- **Activer le module :**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour l'ensemble du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module évaluera activement vos politiques de frais définies et appliquera des frais aux paniers qui remplissent les conditions.
    - *Lorsqu'il est désactivé :* Aucun frais ne sera appliqué par ce module, quelles que soient vos politiques.
  - **Valeur recommandée :** OUI (une fois que vous avez configuré vos politiques).
  - **Scénario / exemple marchand :** Vous avez terminé de configurer toutes vos politiques de frais et êtes prêt à les mettre en ligne. Activez ceci pour commencer à facturer des frais. Si vous devez temporairement arrêter tous les frais pour la maintenance ou une promotion, désactivez-le.
- **ID du produit de frais :**

  - **Ce que fait ce paramètre :** Ce paramètre crucial lie vos frais à un produit spécifique et caché de votre catalogue. PrestaShop a besoin d'un « produit » pour représenter tout article ajouté au panier, même s'il s'agit d'un service ou d'un frais. Ce module crée un produit spécial, non visible, à cette fin lors de l'installation.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur un ID de produit valide :* Le module utilisera ce produit pour représenter le frais dans le panier, la commande et les détails de la commande. Le nom du produit sera remplacé par l'étiquette personnalisée du frais, et son prix sera remplacé par le frais calculé.
    - *Lorsqu'il est défini sur un ID de produit invalide ou inexistant :* Le module ne pourra pas ajouter de frais au panier, car il n'aura pas de produit « placeholder » valide à utiliser.
  - **Valeur recommandée :** Utilisez l'ID du produit spécial « Frais de Commande Conditionnels » créé par le module lors de l'installation. Vous pouvez trouver cet ID en recherchant « Frais de Commande Conditionnels » dans votre liste de produits (bien qu'il soit généralement caché du front office). Le module le pré-remplira souvent pour vous.
  - **Scénario / exemple marchand :** Le module crée automatiquement un produit nommé « Frais de Commande Conditionnels » (ou similaire) et définit son ID ici. Vous ne devriez généralement pas le modifier, sauf si vous souhaitez intentionnellement utiliser un produit différent comme placeholder de frais (ce qui n'est pas recommandé pour la plupart des utilisateurs).

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module fournit des sections dédiées dans votre Back Office PrestaShop pour gérer vos politiques de frais et revoir leur application.

#### 2.2.1 Tableau de bord des frais de commande conditionnels (Back Office > Frais de Commande Conditionnels > Tableau de bord)

Cet écran fournit un aperçu de l'activité de votre module, y compris un résumé des frais appliqués et un accès rapide à la gestion des politiques.

- **Nom de l'écran et emplacement du menu :** **Frais de Commande Conditionnels > Tableau de bord** (situé sous l'élément de menu principal « Frais de Commande Conditionnels » dans la barre latérale gauche).
- **Actions et paramètres disponibles :**
  - **Statistiques récapitulatives :** Affichez les métriques clés telles que le total des frais collectés, le nombre de commandes avec frais et le frais moyen par commande. Cela vous aide à comprendre l'impact de vos politiques de frais.
  - **Frais récents appliqués :** Une liste rapide des commandes les plus récentes où un frais conditionnel a été appliqué, y compris l'ID de commande, le client et le montant du frais.
  - **Liens rapides :** Liens directs vers « Gérer les politiques » et « Voir le journal d'audit ».
- **Effet des modifications :** Cet écran est principalement destiné à la surveillance et à la navigation. Aucune modification directe n'est effectuée ici, mais il reflète l'impact de vos politiques de frais.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vérifiez ce tableau de bord périodiquement pour surveiller les performances de vos politiques de frais et vous assurer qu'elles fonctionnent comme prévu.

#### 2.2.2 Gérer les politiques de frais (Back Office > Frais de Commande Conditionnels > Politiques)

C'est ici que vous définissez, modifiez et gérez toutes vos règles de frais conditionnels. Chaque « politique » est un ensemble de conditions qui, lorsqu'elles sont remplies, appliqueront un frais spécifique.

- **Nom de l'écran et emplacement du menu :** **Frais de Commande Conditionnels > Politiques** (situé sous l'élément de menu principal « Frais de Commande Conditionnels » dans la barre latérale gauche).
- **Actions et paramètres disponibles :**
  - **Liste des politiques :** Un tableau affichant toutes vos politiques de frais existantes, y compris leur nom, leur statut (activé/désactivé), leur priorité et le montant/type de frais.
  - **Ajouter une nouvelle politique :** Cliquez sur le bouton « Ajouter une nouvelle politique » pour créer une nouvelle règle de frais.
    - **Nom de la politique :** Un nom descriptif pour votre référence interne (par exemple, « Frais de traitement petite commande », « Surtaxe emballage fragile »).
    - **Statut :** Activez ou désactivez la politique.
    - **Priorité :** Si plusieurs politiques peuvent s'appliquer au même panier, celle ayant la priorité la plus élevée (le nombre le plus bas) sera évaluée en premier. Si « Arrêter le traitement des règles suivantes » est activé, seule la règle correspondante de la plus haute priorité s'appliquera.
    - **Type de frais :**
      - **Montant fixe :** Une valeur monétaire spécifique (par exemple, 5,00 €).
      - **Pourcentage du total du panier :** Un pourcentage du sous-total du panier (par exemple, 2 %).
      - **Pourcentage des produits dans le panier :** Un pourcentage du prix total des produits dans le panier (hors frais de port/taxes).
    - **Valeur du frais :** Le montant ou le pourcentage réel basé sur le type de frais sélectionné.
    - **Libellé du frais (Multi-langue) :** Le texte que les clients verront dans leur panier et leur récapitulatif de commande (par exemple, « Frais de traitement », « Frais de service »). Cela peut être traduit pour différentes langues.
    - **Constructeur de conditions :** C'est le cœur de la politique. Vous pouvez construire des règles complexes en utilisant des groupes « ET » / « OU », combinant des conditions telles que :
      - Valeur du panier (total, sous-total, quantité)
      - Groupe de clients
      - Pays, état ou zone
      - Transporteur
      - Produits spécifiques dans le panier (par ID, catégorie, fabricant, fournisseur)
      - Méthode de paiement
      - Et plus encore…
    - **Arrêter le traitement des règles suivantes :** Si activé, une fois que cette politique s'applique, aucune autre politique de priorité inférieure ne sera évaluée pour le même panier.
  - **Modifier/Supprimer des politiques :** Modifiez les politiques existantes ou supprimez-les.
  - **Dupliquer la politique :** Créez rapidement une nouvelle politique basée sur une existante, ce qui vous fait gagner du temps lors de la création de règles similaires.
- **Effet des modifications :** L'ajout, la modification ou la suppression de politiques a un impact direct sur les frais appliqués aux paniers des clients et dans quelles circonstances. Des politiques mal configurées peuvent entraîner des frais inattendus ou des pertes de revenus.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1.  Commencez par définir vos scénarios de frais les plus courants.
  2.  Utilisez le bouton « Ajouter une nouvelle politique » pour créer chaque règle.
  3.  Construisez soigneusement vos conditions à l'aide du constructeur. Testez minutieusement à l'aide du simulateur (si disponible, voir le journal d'audit) pour vous assurer qu'elles fonctionnent comme prévu.
  4.  Définissez des priorités appropriées, surtout si vous avez des conditions qui se chevauchent.
  5.  Examinez et mettez à jour régulièrement les politiques à mesure que vos besoins commerciaux ou vos promotions changent.

#### 2.2.3 Journal d'audit (Back Office > Frais de Commande Conditionnels > Journal d'audit)

Le journal d'audit fournit un historique détaillé de chaque instance où le module a évalué un panier et appliqué (ou non appliqué) un frais. C'est inestimable pour le dépannage et pour comprendre pourquoi certains frais ont été ou n'ont pas été facturés.

- **Nom de l'écran et emplacement du menu :** **Frais de Commande Conditionnels > Journal d'audit** (situé sous l'élément de menu principal « Frais de Commande Conditionnels » dans la barre latérale gauche).
- **Actions et paramètres disponibles :**
  - **Entrées de journal :** Un tableau affichant chaque événement d'évaluation, y compris :
    - Date et heure
    - Client (si connecté)
    - ID du panier
    - Politique appliquée (le cas échéant)
    - Montant du frais (si appliqué)
    - Statut (par exemple, « Frais appliqués », « Aucun frais appliqué », « Politique non remplie »)
  - **Vue détaillée :** Cliquez sur une entrée de journal pour voir une ventilation complète de la façon dont les conditions ont été évaluées pour ce panier spécifique, montrant quelles conditions ont été remplies et lesquelles ont échoué. C'est comme un « simulateur » pour les événements passés.
  - **Filtrage et recherche :** Filtrez les entrées de journal par date, client, ID de panier ou politique pour trouver rapidement des événements spécifiques.
- **Effet des modifications :** Cet écran est destiné à l'examen et au débogage. Aucune modification directe n'est effectuée ici, mais il fournit des informations essentielles sur le comportement du module.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1.  Si un client signale un frais inattendu ou l'absence d'un frais attendu, utilisez le journal d'audit pour enquêter.
  2.  Filtrez par le nom du client ou l'ID du panier pour voir exactement quelles politiques ont été évaluées et pourquoi.
  3.  Utilisez la vue détaillée pour identifier la condition spécifique qui a fait qu'une politique a été remplie ou non.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activer le module | OUI | Interrupteur principal pour activer/désactiver toutes les fonctionnalités du module. |
| | ID du produit de frais | ID auto-généré | Lie les frais à un produit caché pour le système de panier de PrestaShop. Ne pas modifier sauf instruction contraire. |
| **Politiques** | Nom de la politique | N/A | Libellé interne pour votre règle de frais. |
| | Statut | Activé | Active/désactive une politique de frais individuelle. |
| | Priorité | 1 (nombre le plus bas = priorité la plus élevée) | Détermine l'ordre d'évaluation si plusieurs politiques peuvent s'appliquer. |
| | Type de frais | Montant fixe | Choisissez comment le frais est calculé (fixe, % du panier, % des produits). |
| | Valeur du frais | 0.00 | Le montant ou le pourcentage du frais. |
| | Libellé du frais | « Frais de traitement » (exemple) | Texte visible par le client pour le frais dans le panier/la commande. |
| | Constructeur de conditions | N/A | Définissez les critères spécifiques (panier, client, produit, etc.) pour que le frais s'applique. |
| | Arrêter le traitement des règles suivantes | Non | Si activé, empêche les politiques de priorité inférieure de s'appliquer une fois que celle-ci correspond. |
| **Journal d'audit** | (Toutes les entrées) | N/A | Fournit un historique détaillé des évaluations de frais pour le dépannage et la surveillance. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : J'ai configuré une politique, mais le frais n'apparaît pas dans le panier.**
R1 :

-   **Vérifier l'état du module :** Assurez-vous que le paramètre « Activer le module » sur la page de configuration principale est défini sur OUI.
-   **Vérifier l'état de la politique :** Assurez-vous que la politique spécifique que vous attendez d'appliquer est « Activée » dans la liste des politiques.
-   **Examiner les conditions :** Vérifiez à nouveau les conditions de votre politique. Sont-elles toutes réellement remplies par le panier actuel ? Utilisez le journal d'audit (Frais de Commande Conditionnels > Journal d'audit) pour voir comment vos conditions ont été évaluées pour un panier test.
-   **ID du produit de frais :** Vérifiez que l'« ID du produit de frais » sur la page de configuration principale est correct et pointe vers le produit spécial créé par le module.
-   **Cache :** Videz le cache de votre PrestaShop (Paramètres avancés > Performances) et le cache de votre navigateur.

**Q2 : Le frais apparaît, mais le libellé ou le montant est incorrect.**
R2 :

-   **Paramètres de la politique :** Accédez à la politique spécifique dans « Frais de Commande Conditionnels > Politiques » et vérifiez les paramètres « Valeur du frais » et « Libellé du frais ». Assurez-vous que le libellé est correctement traduit pour la langue que vous testez.
-   **Politiques multiples :** Si plusieurs politiques peuvent potentiellement s'appliquer, vérifiez leur « Priorité » et le paramètre « Arrêter le traitement des règles suivantes ». Une politique de priorité plus élevée pourrait s'appliquer à la place de celle que vous attendez.

**Q3 : Puis-je traduire le libellé du frais pour différentes langues ?**
R3 : Oui ! Lors de la modification d'une politique, le champ « Libellé du frais » aura généralement un sélecteur de langue (une icône de drapeau). Cliquez dessus pour saisir les traductions pour chaque langue installée dans votre boutique.

**Q4 : Que se passe-t-il si je supprime le « Produit de frais » que le module utilise ?**
R4 : Si vous supprimez le produit spécifié dans le paramètre « ID du produit de frais », le module ne pourra plus ajouter de frais au panier. Il est crucial de ne pas supprimer ce produit. S'il est accidentellement supprimé, vous devrez peut-être réinstaller le module (ce qui le recréera) ou créer manuellement un nouveau produit caché et mettre à jour le paramètre « ID du produit de frais ».

**Q5 : Le module semble ralentir mon processus de commande.**
R5 : Bien que le module soit optimisé pour la performance, des politiques complexes avec de nombreuses conditions, en particulier celles impliquant des vérifications de produits étendues, peuvent ajouter une légère surcharge.

-   **Simplifier les conditions :** Examinez vos politiques. Des conditions peuvent-elles être simplifiées ou combinées ?
-   **Prioriser :** Utilisez efficacement les paramètres « Priorité » et « Arrêter le traitement des règles suivantes » pour minimiser le nombre de politiques qui nécessitent une évaluation complète pour un panier donné.
-   **Ressources du serveur :** Assurez-vous que votre environnement d'hébergement répond aux spécifications recommandées par PrestaShop.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module Frais de Commande Conditionnels est construit en suivant le modèle MVC de PrestaShop, tirant fortement parti d'`ObjectModel` pour la persistance des données et une architecture robuste basée sur les événements via les hooks PrestaShop. Il introduit un moteur sophistiqué d'évaluation des conditions, permettant une logique `ET`/`OU` complexe et imbriquée pour déterminer l'applicabilité des frais. Le module s'intègre de manière transparente dans le flux de traitement du panier et de la commande en ajoutant dynamiquement un « produit virtuel » au panier lorsque les conditions sont remplies. Les interfaces d'administration sont construites à l'aide des composants `AdminController` et `HelperList`/`HelperForm` de PrestaShop, avec du JavaScript personnalisé pour le constructeur de conditions et le simulateur.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   `conorderfee/controllers/front/index.php`
    -   **Nom de la classe :** `ConorderfeeIndexModuleFrontController` (étend `ModuleFrontController`)
    -   **Responsabilité :** Ce contrôleur sert probablement de solution de repli ou de simple point d'entrée, mais la logique principale d'application des frais est principalement gérée via des hooks, et non via des routes de contrôleur frontal directes. Il pourrait être utilisé pour des informations de module de base ou une redirection s'il est accédé directement.

#### Contrôleurs d'administration Back-Office

-   `conorderfee/controllers/admin/AdminconorderfeeAuditLog.php`
    -   **Nom de la classe :** `AdminconorderfeeAuditLogController` (étend `ModuleAdminController`)
    -   **Nom de l'onglet :** Frais de Commande Conditionnels > Journal d'audit
    -   **Entité gérée :** `ConorderfeeLog` (ORM pour la table `ps_conorderfee_log`).
    -   **Responsabilité :** Gère l'affichage et le filtrage du journal d'audit des frais. Il utilise `HelperList` pour rendre le tableau des entrées de journal et fournit des vues détaillées pour les entrées de journal individuelles, montrant le processus d'évaluation des conditions.
-   `conorderfee/controllers/admin/AdminconorderfeePolicies.php`
    -   **Nom de la classe :** `AdminconorderfeePoliciesController` (étend `ModuleAdminController`)
    -   **Nom de l'onglet :** Frais de Commande Conditionnels > Politiques
    -   **Entité gérée :** `ConorderfeePolicy` (ORM pour la table `ps_conorderfee_policy`).
    -   **Responsabilité :** Gère la création, la modification, la duplication et la suppression des politiques de frais. Il utilise `HelperList` pour l'aperçu des politiques et `HelperForm` pour le formulaire de création/modification de politique, qui comprend l'interface complexe du constructeur de conditions.
-   `conorderfee/controllers/admin/index.php`
    -   **Nom de la classe :** `ConorderfeeIndexModuleAdminController` (étend `ModuleAdminController`)
    -   **Nom de l'onglet :** Frais de Commande Conditionnels > Tableau de bord
    -   **Entité gérée :** N/A (vue du tableau de bord)
    -   **Responsabilité :** Sert de tableau de bord principal pour le module dans le back office, affichant des statistiques et des liens rapides. C'est le contrôleur par défaut chargé lorsque l'on clique sur l'élément de menu principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

-   `conorderfee/classes/ConorderfeeAdmin.php`
    -   **Responsabilité :** Classe utilitaire pour les fonctionnalités spécifiques à l'administration, gérant potentiellement l'enregistrement des menus, la gestion des onglets et les aides générales liées à l'administration.
-   `conorderfee/classes/ConorderfeeAuditLog.php`
    -   **Table de base de données :** `ps_conorderfee_log`
    -   **Étend ObjectModel :** Oui.
    -   **Champs `$definition` :** `id_conorderfee_log`, `id_cart`, `id_order`, `id_customer`, `id_conorderfee_policy`, `fee_amount`, `fee_label`, `conditions_snapshot`, `evaluation_result`, `date_add`.
    -   **Méthodes publiques clés :** Méthodes pour enregistrer les entrées de journal, récupérer les données de journal et potentiellement formater les détails de journal pour l'affichage.
-   `conorderfee/classes/ConorderfeeCartState.php`
    -   **Responsabilité :** Une classe d'aide pour encapsuler l'état actuel du panier et le contexte associé (client, adresse, transporteur, etc.) pour l'évaluation des conditions. Elle fournit des méthodes pour récupérer diverses propriétés du panier nécessaires aux conditions.
-   `conorderfee/classes/ConorderfeeCompatibility.php`
    -   **Responsabilité :** Gère les couches de compatibilité pour différentes versions de PrestaShop (par exemple, 1.7 vs 8.x vs 9.x) pour garantir que le module fonctionne correctement sur les versions prises en charge.
-   `conorderfee/classes/ConorderfeeCondition.php`
    -   **Table de base de données :** `ps_conorderfee_condition`
    -   **Étend ObjectModel :** Oui.
    -   **Champs `$definition` :** `id_conorderfee_condition`, `id_conorderfee_condition_group`, `type`, `operator`, `value`, `is_inverted`.
    -   **Méthodes publiques clés :** Représente une seule condition au sein d'une politique (par exemple, « Total du panier > 100 »). Méthodes pour enregistrer, charger et potentiellement valider les données de condition.
-   `conorderfee/classes/ConorderfeeConditionEvaluator.php`
    -   **Responsabilité :** Le moteur logique principal pour évaluer un `ConorderfeeConditionTree` par rapport à un `ConorderfeeCartState`. Il traite récursivement les groupes de conditions et les conditions individuelles pour déterminer si une politique s'applique.
-   `conorderfee/classes/ConorderfeeConditionGroup.php`
    -   **Table de base de données :** `ps_conorderfee_condition_group`
    -   **Étend ObjectModel :** Oui.
    -   **Champs `$definition` :** `id_conorderfee_condition_group`, `id_conorderfee_policy`, `id_parent_group`, `operator` (`AND`/`OR`).
    -   **Méthodes publiques clés :** Représente un groupe de conditions (par exemple, « Condition A ET (Condition B OU Condition C) »). Gère ses conditions enfants et ses sous-groupes.
-   `conorderfee/classes/ConorderfeeConditionTree.php`
    -   **Responsabilité :** Représente la structure hiérarchique des conditions pour une politique (groupe racine, sous-groupes, conditions individuelles). Utilisé par le `ConorderfeeConditionEvaluator`.
-   `conorderfee/classes/ConorderfeeContext.php`
    -   **Responsabilité :** Un wrapper autour de l'objet `Context` de PrestaShop, ajoutant potentiellement des données de contexte spécifiques au module ou simplifiant l'accès aux éléments de contexte courants.
-   `conorderfee/classes/ConorderfeeDashboard.php`
    -   **Responsabilité :** Fournit des données et une logique pour la vue du tableau de bord du module, récupérant des statistiques et des entrées de journal récentes.
-   `conorderfee/classes/ConorderfeeEngine.php`
    -   **Responsabilité :** L'orchestrateur central de la logique front-office du module. Il se connecte à divers événements PrestaShop, récupère les politiques actives, utilise le `ConorderfeeConditionEvaluator` pour vérifier les conditions et ajoute le produit de frais au panier si applicable.
-   `conorderfee/classes/ConorderfeeFeeProduct.php`
    -   **Responsabilité :** Gère le « produit de frais » spécial qui représente le frais conditionnel dans le panier. Il gère sa création lors de l'installation et s'assure qu'il est correctement configuré comme un produit virtuel et non visible.
-   `conorderfee/classes/ConorderfeeListRenderer.php`
    -   **Responsabilité :** Une classe d'aide pour le rendu des listes dans le back office, étendant potentiellement `HelperList` ou fournissant une logique de rendu de colonne personnalisée.
-   `conorderfee/classes/ConorderfeeLog.php`
    -   **Table de base de données :** `ps_conorderfee_log` (identique à `ConorderfeeAuditLog`, probablement un alias ou une classe de base)
    -   **Étend ObjectModel :** Oui.
    -   **Champs `$definition` :** Identiques à `ConorderfeeAuditLog`.
    -   **Méthodes publiques clés :** Méthodes pour enregistrer les événements, stocker les résultats d'évaluation et récupérer les données de journal.
-   `conorderfee/classes/ConorderfeePolicy.php`
    -   **Table de base de données :** `ps_conorderfee_policy`
    -   **Étend ObjectModel :** Oui.
    -   **Champs `$definition` :** `id_conorderfee_policy`, `name`, `active`, `priority`, `fee_type`, `fee_value`, `fee_label`, `stop_further_rules`, `date_add`, `date_upd`.
    -   **Méthodes publiques clés :** Représente une politique de frais complète. Méthodes pour enregistrer, charger et gérer ses `ConorderfeeConditionGroup`s associés.
-   `conorderfee/classes/ConorderfeePolicyDuplicator.php`
    -   **Responsabilité :** Gère la logique de duplication d'une politique de frais existante, y compris toutes ses conditions et groupes associés, pour rationaliser la création de politiques.
-   `conorderfee/classes/ConorderfeePreset.php`
    -   **Responsabilité :** Gère les types de conditions et les opérateurs prédéfinis pour le constructeur de conditions (par exemple, « Total du panier », « Groupe de clients », « est supérieur à », « est l'un de »).
-   `conorderfee/classes/ConorderfeeRule.php`
    -   **Responsabilité :** Probablement une classe abstraite ou de base pour définir des règles, ou un type de règle spécifique au sein du constructeur de conditions.
-   `conorderfee/classes/ConorderfeeTreeRepository.php`
    -   **Responsabilité :** Gère la persistance et la récupération de la structure de l'arbre de conditions (politiques, groupes, conditions) à partir de la base de données.
-   `conorderfee/classes/index.php`
    -   **Responsabilité :** Fichier vide, généralement utilisé pour empêcher l'affichage du contenu du répertoire.

### 4.4 Actifs JavaScript (`views/js/`)

-   `conorderfee/lib/searchTool/views/js/autocomplete.js`
    -   **Portée :** Back-office.
    -   **Description :** Fournit une fonctionnalité d'autocomplétion pour les champs de recherche, probablement utilisée pour sélectionner des produits, des catégories, des clients, etc., dans le constructeur de conditions.
-   `conorderfee/lib/searchTool/views/views/js/autocomplete.js`
    -   **Portée :** Back-office.
    -   **Description :** Duplicata du précédent, probablement une erreur de chemin ou un fichier hérité.
-   `conorderfee/views/js/adminConditionBuilder.js`
    -   **Portée :** Back-office (`AdminconorderfeePoliciesController`).
    -   **Description :** Le JavaScript principal pour l'interface interactive du constructeur de conditions. Il gère l'ajout/la suppression de conditions et de groupes, la gestion de la logique `ET`/`OU`, le chargement dynamique des types de conditions et des opérateurs, et la mise à jour de l'interface utilisateur en fonction de l'entrée de l'utilisateur.
-   `conorderfee/views/js/adminConorderfeeDashboard.js`
    -   **Portée :** Back-office (`AdminconorderfeeDashboardController`).
    -   **Description :** JavaScript pour le tableau de bord, gérant potentiellement les mises à jour AJAX pour les statistiques, le rendu des graphiques ou les éléments interactifs du tableau de bord.
-   `conorderfee/views/js/adminConorderfeeSearchTool.js`
    -   **Portée :** Back-office.
    -   **Description :** Intègre l'outil de recherche d'autocomplétion (de `lib/searchTool`) dans divers formulaires d'administration, en particulier pour la sélection d'entités dans les conditions.
-   `conorderfee/views/js/adminConorderfeeSimulator.js`
    -   **Portée :** Back-office (probablement sur la page d'édition de la politique ou le journal d'audit).
    -   **Description :** Fournit un outil d'évaluation de conditions en temps réel ou simulé dans le back office, permettant aux administrateurs de tester les politiques par rapport à des scénarios de panier hypothétiques sans passer une commande réelle.
-   `conorderfee/views/js/adminPolicyRules.js`
    -   **Portée :** Back-office (`AdminconorderfeePoliciesController`).
    -   **Description :** Gère les interactions JavaScript générales sur la liste des politiques et les pages d'édition, telles que l'activation/la désactivation des politiques, la gestion de la duplication et la gestion du formulaire de politique global.
-   `conorderfee/views/js/checkout.js`
    -   **Portée :** Front-office.
    -   **Description :** Ce script surveille probablement les changements dans le panier pendant le processus de commande (par exemple, les mises à jour de quantité, la sélection du transporteur) et déclenche des appels AJAX pour réévaluer les frais, garantissant que le total du panier est toujours précis. Il pourrait également mettre à jour l'affichage de la ligne de frais.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `conorderfee/lib/searchTool/views/css/autocomplete.css`
    -   **Portée :** Back-office (Admin).
    -   **Description :** Styles pour les champs de saisie de recherche d'autocomplétion et leurs suggestions déroulantes.
-   `conorderfee/lib/searchTool/views/views/css/autocomplete.css`
    -   **Portée :** Back-office (Admin).
    -   **Description :** Duplicata du précédent, probablement une erreur de chemin ou un fichier hérité.
-   `conorderfee/views/css/admin_conorderfee.css`
    -   **Portée :** Back-office (Admin).
    -   **Description :** Style général pour les interfaces back-office du module, y compris le tableau de bord, la liste des politiques, le journal d'audit, et surtout le constructeur de conditions complexe, garantissant une mise en page cohérente et conviviale.
-   `conorderfee/views/css/front.css`
    -   **Portée :** Front-office (Client).
    -   **Description :** Style minimal pour l'apparence de la ligne de frais dans le récapitulatif du panier et les pages de commande, garantissant son intégration visuelle avec le thème de la boutique.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

-   `conorderfee/views/templates/hook/admin_order.tpl`
    -   **Hook :** `displayAdminOrder`
    -   **Sortie :** Affiche des informations sur les frais conditionnels appliqués dans la vue de commande du Back Office de PrestaShop, permettant aux administrateurs de voir quelles politiques ont été appliquées à une commande spécifique.

#### Templates d'administration (`views/templates/admin/`)

-   `conorderfee/lib/searchTool/views/scripts.tpl`
    -   **Sortie :** Inclut le JavaScript et le CSS nécessaires pour l'outil de recherche dans le back office.
-   `conorderfee/lib/searchTool/views/views/scripts.tpl`
    -   **Sortie :** Duplicata du précédent, probablement une erreur de chemin ou un fichier hérité.
-   `conorderfee/views/templates/admin/auditPreview.tpl`
    -   **Sortie :** Rend la vue détaillée d'une entrée de journal d'audit individuelle, montrant le processus complet d'évaluation des conditions.
-   `conorderfee/views/templates/admin/dashboard.tpl`
    -   **Sortie :** La vue principale du tableau de bord pour le module, affichant des statistiques et des liens rapides.
-   `conorderfee/views/templates/admin/helpers/list/list_action_duplicate.tpl`
    -   **Sortie :** Template personnalisé pour le bouton d'action « dupliquer » dans les vues `HelperList`, spécifiquement pour les politiques.
-   `conorderfee/views/templates/admin/policiesPreview.tpl`
    -   **Sortie :** Rend un aperçu ou un résumé d'une politique, potentiellement utilisé dans le journal d'audit ou un simulateur.
-   `conorderfee/views/templates/admin/policyConditionBuilder.tpl`
    -   **Sortie :** La structure HTML complexe pour l'interface interactive du constructeur de conditions utilisée lors de la création ou de la modification d'une politique.
-   `conorderfee/views/templates/admin/policyRuleCard.tpl`
    -   **Sortie :** Rend une seule règle ou condition dans le constructeur de conditions, généralement une carte ou un bloc visuel.
-   `conorderfee/views/templates/admin/policyRulesTable.tpl`
    -   **Sortie :** Rend le tableau des politiques dans la vue de liste `AdminconorderfeePolicies`.
-   `conorderfee/views/templates/admin/scopeSelector.tpl`
    -   **Sortie :** Un template pour sélectionner la portée d'une condition (par exemple, « Panier », « Produit », « Client »), utilisé dans le constructeur de conditions.

#### Templates Front-office (`views/templates/front/`)

-   `conorderfee/controllers/front/index.php` (Aucun fichier .tpl spécifique listé, gère probablement la sortie directement ou redirige)

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

-   `ps_conorderfee_policy` : Stocke les définitions principales des politiques de frais (nom, statut actif, type de frais, valeur, libellé, priorité).
-   `ps_conorderfee_condition_group` : Stocke la structure hiérarchique des groupes de conditions (logique ET/OU) au sein de chaque politique.
-   `ps_conorderfee_condition` : Stocke les conditions individuelles (type, opérateur, valeur) liées aux groupes de conditions.
-   `ps_conorderfee_log` : Stocke un journal d'audit de chaque fois qu'un frais a été évalué, y compris les détails du panier, la politique appliquée, le montant du frais et un instantané du résultat de l'évaluation.
-   `ps_configuration` : Stocke les valeurs de configuration spécifiques au module comme `CONORDERFEE_ENABLED` et `CONORDERFEE_FEE_PRODUCT_ID`.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page front-office. | Non explicitement listé dans les informations du module, mais souvent utilisé pour charger le CSS/JS du front-office. |
| `displayBeforeCarrier` | Avant la sélection du transporteur sur la page de commande. | Potentiellement utilisé pour réévaluer les frais si la sélection du transporteur a un impact sur les conditions. |
| `actionObjectProductInCartDeleteBefore` | Avant qu'un produit ne soit retiré du panier. | Réévaluer les frais pour ajuster si le produit retiré faisait partie d'une condition. |
| `actionPresentCart` | Lorsque les données du panier sont présentées au front office. | **CRITIQUE :** Hook principal pour injecter la ligne de frais dans le récapitulatif du panier. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration est chargé, avant son contenu. | Charge le CSS et le JavaScript du back-office pour les interfaces d'administration du module. |
| `actionPresentProductListing` | Lorsque les listes de produits sont présentées. | Non directement lié aux frais, mais pourrait être utilisé pour des indicateurs de frais spécifiques aux produits. |
| `actionValidateOrderBefore` | Juste avant qu'une commande ne soit validée. | Vérification finale et application des frais pour s'assurer que le total de la commande est correct. |
| `actionGetProductPropertiesAfter` | Après la récupération des propriétés du produit. | Potentiellement utilisé pour identifier des produits spécifiques qui déclenchent des frais. |
| `displayAdminOrder` | Dans la page de détail de commande du Back Office. | Affiche des informations sur les frais appliqués pour une commande spécifique. |
| `actionFrontControllerInitAfter` | Après l'initialisation d'un contrôleur frontal. | Initialisation générale du front-office, configurant potentiellement le contexte pour l'évaluation des frais. |
| `actionPresentProduct` | Lorsqu'un seul produit est présenté. | Similaire à `actionPresentProductListing`. |
| `actionPresentCartProduct` | Lorsqu'un produit dans le panier est présenté. | Permet la modification des données du produit du panier, potentiellement pour l'affichage lié aux frais. |
| `actionProductPriceCalculation` | Pendant le calcul du prix du produit. | Garantit que le prix du produit de frais est correctement remplacé par le frais calculé. |
| `actionFrontControllerSetVariables` | Avant que les variables Smarty ne soient attribuées dans un contrôleur frontal. | Transmet les données liées aux frais aux templates du front-office. |
| `actionCartSave` | Après l'enregistrement d'un panier (par exemple, changement de quantité, ajout/suppression de produit). | **CRITIQUE :** Déclenche la logique principale d'évaluation des frais chaque fois que le contenu du panier change. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | Enregistre l'application finale des frais et l'associe au nouvel ID de commande. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, les corrections de bugs et le support développeur dédié, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Assurez-vous de toujours télécharger la dernière version compatible avec votre installation PrestaShop.
