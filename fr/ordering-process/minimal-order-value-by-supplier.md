---
title: "Valeur de commande minimale par fournisseur - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Valeur de commande minimale par fournisseur' par MyPresta.eu."
sidebar:
  label: "Valeur de commande minimale par fournisseur - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Minimal order value by supplier sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimal-order-value-by-supplier.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/minimal-order-value-by-supplier/)
>
> ---


# Valeur de commande minimale par fournisseur

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à la page de configuration principale du module. C'est ici que vous pouvez activer ou désactiver le module et accéder à l'écran de gestion principal pour vos minimums par fournisseur.

- **Ce que fait ce paramètre :** Cet écran sert de hub central pour le module. Il vous permet d'activer ou de désactiver l'ensemble des fonctionnalités du module et fournit un lien direct pour gérer vos valeurs de commande minimales par fournisseur.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Le module vérifiera activement les paniers des clients par rapport à vos valeurs de commande minimales par fournisseur définies et bloquera le passage à la caisse si les exigences ne sont pas remplies.
  - *Lorsqu'il est désactivé :* Le module cessera de fonctionner. Aucune vérification de la valeur de commande minimale ne sera effectuée, et les clients pourront passer à la caisse quelle que soit la valeur totale des commandes par fournisseur.
- **Valeur recommandée :** « OUI » (Activé) si vous avez l'intention d'utiliser les fonctionnalités du module.
- **Scénario/exemple pour le marchand :** Si vous configurez le module pour la première fois, vous l'activerez ici. Si vous devez suspendre temporairement les règles (par exemple, lors d'une promotion à l'échelle de la boutique où vous souhaitez autoriser toutes les commandes), vous pouvez le désactiver ici.

Sur cet écran, vous trouverez également un bouton ou un lien vers **« Gérer les valeurs de commande minimales par fournisseur »**. Cliquer dessus vous mènera à l'écran d'administration dédié où vous définissez les règles réelles.

### 2.2 Écrans d'administration dédiés et vues du contrôleur

#### AdminMobsController (Back Office > Modules > Valeur de commande minimale par fournisseur > Gérer les valeurs de commande minimales)

C'est l'écran principal où vous définissez et gérez les valeurs de commande minimales pour chacun de vos fournisseurs.

- **Nom de l'écran et emplacement du menu :** Vous accédez à cet écran en naviguant vers **Modules > Gestionnaire de modules**, en trouvant « Valeur de commande minimale par fournisseur », en cliquant sur « Configurer », puis en cliquant sur le bouton/lien « Gérer les valeurs de commande minimales par fournisseur ».
- **Actions et paramètres disponibles :**
  - **Tableau de liste :** Cet écran affiche un tableau de toutes les valeurs de commande minimales actuellement configurées. Chaque ligne affiche généralement :
    - **Nom du fournisseur :** Le nom du fournisseur pour lequel la règle s'applique.
    - **Valeur de commande minimale :** Le montant monétaire que les produits de ce fournisseur doivent atteindre dans le panier.
    - **Actions :** Généralement des boutons « Modifier » et « Supprimer » pour modifier ou supprimer une règle existante.
  - **Bouton Ajouter une nouvelle règle :** Un bouton (par exemple, « Ajouter une nouvelle valeur de commande minimale ») pour créer une nouvelle règle.
  - **Formulaire Ajouter/Modifier :** Lors de l'ajout d'une nouvelle règle ou de la modification d'une règle existante, vous verrez généralement un formulaire avec les champs suivants :
    - **Sélection du fournisseur :** Une liste déroulante ou un champ de recherche pour sélectionner l'un de vos fournisseurs existants.
    - **Valeur minimale :** Un champ de saisie où vous entrez le montant numérique de la commande minimale requise pour les produits du fournisseur sélectionné. Cette valeur sera dans la devise par défaut de votre boutique (par exemple, EUR, USD).
    - **Bouton Enregistrer :** Pour appliquer vos modifications.
- **Effet des modifications :**
  - *Ajout d'une règle :* Une fois enregistrée, la nouvelle valeur de commande minimale pour le fournisseur sélectionné devient immédiatement active. Les clients devront respecter cette valeur pour les produits de ce fournisseur.
  - *Modification d'une règle :* La modification de la valeur minimale ou le changement de fournisseur pour une règle existante met à jour l'exigence active.
  - *Suppression d'une règle :* Supprime l'exigence de valeur de commande minimale pour ce fournisseur spécifique. Les clients ne seront plus limités par un achat minimum de ce fournisseur.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. **Identifier les fournisseurs :** Déterminez quels fournisseurs nécessitent des valeurs de commande minimales en fonction de vos besoins commerciaux (par exemple, frais d'expédition élevés, accords de dropshipping).
  2. **Ajouter des règles :** Pour chaque fournisseur identifié, cliquez sur « Ajouter une nouvelle valeur de commande minimale », sélectionnez le fournisseur, entrez le montant minimum et enregistrez.
  3. **Surveiller et ajuster :** Révisez régulièrement vos accords avec les fournisseurs et vos données de vente. Si un fournisseur modifie ses conditions, ou si vous remarquez une tendance de petites commandes non rentables, revenez à cet écran pour ajuster ou ajouter de nouvelles règles.
  4. **Tester :** Après avoir ajouté ou modifié des règles, testez toujours la fonctionnalité en ajoutant des produits des fournisseurs concernés à votre panier dans le front office et en tentant de passer à la caisse.

#### index.php (mobs/controllers/admin/index.php)

Ce fichier sert généralement de marqueur de position ou de redirigeur dans le répertoire des contrôleurs d'administration et ne présente pas d'écran de configuration direct au marchand. Sa fonction principale est généralement de s'assurer que l'accès direct au répertoire est géré avec élégance, redirigeant souvent vers la configuration principale du module ou une page d'erreur. Les marchands n'interagiront pas directement avec ce fichier.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Activer/Désactiver le module | Activé | Contrôle si la fonctionnalité du module (vérifications de la valeur de commande minimale) est active ou inactive. |
| **AdminMobsController** | Ajouter une nouvelle règle (Fournisseur) | N/A | Sélectionne un fournisseur auquel appliquer une règle de valeur de commande minimale. |
| **AdminMobsController** | Ajouter une nouvelle règle (Valeur minimale) | N/A | Définit le seuil monétaire pour les produits du fournisseur sélectionné. |
| **AdminMobsController** | Modifier la règle (Fournisseur) | N/A | Modifie le fournisseur associé à une règle existante. |
| **AdminMobsController** | Modifier la règle (Valeur minimale) | N/A | Modifie le seuil monétaire pour une règle de fournisseur existante. |
| **AdminMobsController** | Supprimer la règle | N/A | Supprime une exigence de valeur de commande minimale pour un fournisseur spécifique. |

## 3. Dépannage pour le marchand et questions fréquemment posées (FAQ)

**Q1 : J'ai défini une valeur minimale, mais cela ne fonctionne pas dans le panier. Que dois-je vérifier ?**
R1 :

1. **Le module est-il activé ?** Allez dans **Modules > Gestionnaire de modules**, trouvez « Valeur de commande minimale par fournisseur » et assurez-vous qu'il est activé.
2. **La règle est-elle correctement configurée ?** Allez sur l'écran « Gérer les valeurs de commande minimales par fournisseur » et vérifiez que le fournisseur est correctement sélectionné et que la valeur minimale est saisie sous forme de nombre (sans symboles monétaires).
3. **Les produits sont-ils correctement attribués au fournisseur ?** Vérifiez à nouveau les produits dans le panier du client pour vous assurer qu'ils sont bien associés au fournisseur pour lequel vous avez défini la règle.
4. **Vider le cache :** Parfois, le cache de PrestaShop peut empêcher les modifications d'apparaître immédiatement. Allez dans **Paramètres avancés > Performance** et cliquez sur « Vider le cache ».

**Q2 : Le message de notification s'affiche, mais il n'est pas dans la langue de ma boutique.**
R2 : Les messages du module en front-office sont traduisibles.

1. Allez dans **International > Traductions**.
2. Sélectionnez « Traductions des modules installés », choisissez votre thème, sélectionnez votre langue et cliquez sur « Modifier ».
3. Trouvez le module « mobs » (Valeur de commande minimale par fournisseur) et traduisez les chaînes pertinentes. Enregistrez vos modifications.

**Q3 : Le module bloque le passage à la caisse, mais je souhaite autoriser une exception pour un client ou une commande spécifique.**
R3 : Le module applique les règles globalement. Pour faire une exception, vous devrez désactiver temporairement la règle du fournisseur spécifique dans la configuration du module (**Modules > Valeur de commande minimale par fournisseur > Gérer les valeurs de commande minimales**) ou désactiver l'ensemble du module si plusieurs règles sont actives. N'oubliez pas de le réactiver par la suite. Il n'y a pas de fonction de « dérogation » intégrée par client ou par commande.

**Q4 : Le module est actif, mais le style du message de notification ne correspond pas à mon thème.**
R4 : Le module est livré avec un style de base. S'il entre en conflit avec votre thème personnalisé, votre webmaster ou développeur peut remplacer le CSS du module. Le fichier CSS du module est `mobs/views/css/mobs.css`. Ils peuvent ajouter des styles personnalisés au fichier `custom.css` ou `theme.css` de votre thème, en ciblant les éléments de notification du module pour qu'ils correspondent à l'image de votre marque.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Valeur de commande minimale par fournisseur » (`mobs`) suit une architecture de module PrestaShop standard, tirant parti des principes MVC. Il se compose principalement d'une classe de module principale, d'un contrôleur d'administration dédié à la gestion des règles et d'un contrôleur frontal pour les interactions AJAX et l'affichage des notifications. Il n'utilise pas de classes `ObjectModel` personnalisées mais stocke la configuration directement dans `ps_configuration` et gère les minimums spécifiques aux fournisseurs via l'`AdminMobsController` qui interagit probablement avec une table personnalisée ou étend un `AdminController` générique pour gérer les données. L'interaction en front-office est gérée via un template dédié pour le panier et un contrôleur AJAX pour les vérifications dynamiques.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :

  - `controllers/front/ajax.php`
    - **Nom de la classe et classe parente** : `MobsAjaxModuleFrontController` étend `ModuleFrontController`.
    - **Responsabilité** : Ce contrôleur est responsable de la gestion des requêtes AJAX depuis le front-office, généralement initiées depuis la page du panier. Il effectue probablement des vérifications en temps réel du contenu du panier par rapport aux valeurs de commande minimales par fournisseur configurées. Il renvoie des réponses JSON indiquant si les minimums sont respectés et fournissant des messages pertinents si ce n'est pas le cas. Cela permet des mises à jour dynamiques de l'affichage du panier sans rechargement complet de la page.
  - `controllers/front/index.php`
    - **Nom de la classe et classe parente** : `MobsIndexModuleFrontController` étend `ModuleFrontController`.
    - **Responsabilité** : Ce contrôleur pourrait servir de point d'entrée par défaut pour la partie front-office du module, bien que sa fonction principale soit souvent de rediriger ou de servir une page de base si le module n'a pas de page front-office dédiée. Compte tenu de la fonctionnalité du module, il est plus probable que le contrôleur `ajax.php` gère la logique principale du front-office, et `index.php` est une solution de repli ou une page minimale.
- **Contrôleurs d'administration Back-Office** :

  - `controllers/admin/AdminMobs.php`
    - **Nom de la classe et classe parente** : `AdminMobsController` étend `ModuleAdminController`.
    - **Nom de l'onglet et entité gérée** : Ce contrôleur gère les règles de « Valeurs de commande minimales par fournisseur ». Il fournit l'interface pour lister, ajouter, modifier et supprimer ces règles. Il interagit probablement avec une table de base de données personnalisée (par exemple, `ps_mobs_rules`) pour stocker l'ID du fournisseur et la valeur minimale associée. La vue en grille et les champs de formulaire sont rendus à l'aide des classes `HelperList` et `HelperForm` de PrestaShop.
  - `controllers/admin/index.php`
    - **Nom de la classe et classe parente** : Pas de classe spécifique, généralement un simple fichier PHP.
    - **Responsabilité** : Ce fichier est généralement un marqueur de position ou une mesure de sécurité pour empêcher la liste directe des répertoires. Il contient souvent un simple `header('Location: ../../../index.php?controller=AdminHome');` ou une redirection similaire vers le tableau de bord du back office de PrestaShop, garantissant que l'accès direct à `votreboutique.com/modules/mobs/controllers/admin/` n'expose pas d'informations sensibles ou ne provoque pas d'erreurs. Il ne présente pas d'écran visible par l'utilisateur.

### 4.3 Classes et modèles principaux (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que le module :

1. Stocke sa configuration directement dans `ps_configuration` pour les paramètres simples.
2. Gère ses données (minimums par fournisseur) directement dans l'`AdminMobsController` en utilisant les méthodes de requête de base de données standard de PrestaShop, interagissant potentiellement avec une table personnalisée créée lors de l'installation, sans `ObjectModel` dédié.

Si une table personnalisée est utilisée, sa structure serait définie dans la méthode `install()` du fichier principal du module (`mobs/index.php`).

### 4.4 Actifs JavaScript (`views/js/`)

- `views/js/mobs.js`
  - **Portée** : Front-office.
  - **Description** : Ce fichier JavaScript est responsable des interactions côté client liées aux vérifications de la valeur de commande minimale. Il est probable qu'il :
    - Lie des écouteurs d'événements aux changements de quantité du panier, aux suppressions de produits ou au bouton « Passer à la caisse ».
    - Envoie des requêtes AJAX à `controllers/front/ajax.php` pour valider le panier par rapport aux minimums des fournisseurs.
    - Reçoit des réponses JSON du contrôleur AJAX.
    - Met à jour dynamiquement l'affichage du panier, affichant des messages de notification si les minimums ne sont pas atteints.
    - Désactive ou active le bouton « Passer à la caisse » en fonction des résultats de la validation.
    - Peut inclure une logique pour afficher des pop-ups modaux ou des messages d'erreur en ligne.

### 4.5 Feuilles de style CSS (`views/css/`)

- `views/css/mobs.css`
  - **Portée** : Style client du front-office.
  - **Description** : Cette feuille de style fournit la présentation visuelle des éléments du front-office du module, principalement les messages de notification affichés dans le panier.
  - **Principaux composants et conteneurs d'interface utilisateur qu'il stylise** : Il ciblera probablement des classes CSS spécifiques ajoutées par le module au template du panier, telles que `div.mobs-notification`, `p.mobs-error-message`, ou des éléments similaires qui affichent les avertissements concernant les valeurs de commande minimales non atteintes.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer** : Les développeurs peuvent inspecter la sortie HTML des notifications du module pour identifier les noms de classe exacts (par exemple, `.mobs-alert`, `.mobs-supplier-name`, `.mobs-required-value`) et les remplacer dans le `custom.css` de leur thème pour correspondre à l'image de marque de la boutique.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :

  - Aucun template de hook spécifique n'est listé dans l'inventaire, ce qui suggère que la sortie du front-office du module est principalement injectée dans un template existant comme `displayShoppingCart.tpl` ou via un rendu de template direct dans un contrôleur.
- **Templates d'administration (`views/templates/admin/`)** :

  - Le dossier du module ne liste pas de templates d'administration spécifiques. L'`AdminMobsController` utilise probablement les templates `HelperList` et `HelperForm` par défaut de PrestaShop pour ses vues en grille et de formulaire, qui font partie du framework PrestaShop de base.
- **Templates Front-office (`views/templates/front/`)** :

  - `views/templates/front/displayShoppingCart.tpl`
    - **Description** : Ce template est spécifiquement conçu pour être inclus ou rendu dans la page du panier. Il contient la structure HTML pour afficher les notifications de valeur de commande minimale au client. Il itérera probablement sur toutes les valeurs minimales de fournisseur non atteintes et affichera un message pour chacune, incluant éventuellement le nom du fournisseur et le montant restant nécessaire. Ce template est mis à jour dynamiquement par le script `mobs.js` en fonction des réponses AJAX.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** :

  - Le dossier du module ne liste pas explicitement de classes personnalisées ou de fichiers SQL, mais pour que l'`AdminMobsController` gère les « Valeurs de commande minimales par fournisseur », il doit stocker ces données. Il est très probable que le module crée une table personnalisée lors de sa méthode `install()` dans `mobs/index.php`.
  - **Nom de table probable** : `ps_mobs_rules` (ou similaire, par exemple, `ps_minimal_order_by_supplier`).
  - **Structure de table probable** :
    - `id_mobs_rule` (CLÉ PRIMAIRE, INT)
    - `id_supplier` (INT, CLÉ ÉTRANGÈRE vers `ps_supplier.id_supplier`)
    - `min_value` (DECIMAL(20,6))
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - **Enregistrements de configuration** : Le statut d'activation/désactivation principal du module est probablement stocké dans `ps_configuration` avec une clé comme `MOBS_ENABLED`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Pour inclure les fichiers CSS (`mobs.css`) et JavaScript (`mobs.js`) pour la fonctionnalité front-office. |
| `displayShoppingCartFooter` | En bas de la page du panier. | Pour afficher le template `displayShoppingCart.tpl`, qui contient les messages de notification pour les valeurs de commande minimales non atteintes. |
| `actionCartSave` | Après l'enregistrement d'un panier (par exemple, changement de quantité, ajout/suppression de produit). | Pour déclencher la logique qui vérifie les valeurs de commande minimales et potentiellement met à jour le statut du panier ou les variables de session. |
| `actionValidateOrder` | Avant qu'une commande ne soit officiellement validée. | Pour effectuer une vérification finale des valeurs de commande minimales et empêcher la validation de la commande si les exigences ne sont pas remplies. |
| `displayBeforeCarrier` | Avant l'étape de sélection du transporteur lors du paiement. | Pour afficher des avertissements ou bloquer la progression si les minimums ne sont pas atteints à un stade antérieur du paiement. |
| `displayPaymentTop` | En haut de la page de sélection du paiement. | Pour afficher des avertissements ou bloquer la progression si les minimums ne sont pas atteints avant le paiement. |

*Note : Le dossier du module mentionne « Header, Columns, Product, or Footer » comme hooks front-office. Bien que `displayHeader` soit certain, le module utilise probablement `displayShoppingCartFooter` ou un hook similaire spécifique au panier pour sa sortie principale, et `actionCartSave`/`actionValidateOrder` pour sa logique principale. `displayRightColumn` ou `displayLeftColumn` pourraient être utilisés pour des blocs statiques optionnels, mais sont moins probables pour la fonctionnalité principale.*

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour accéder aux dernières versions du module « Valeur de commande minimale par fournisseur », veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la configuration du module.
