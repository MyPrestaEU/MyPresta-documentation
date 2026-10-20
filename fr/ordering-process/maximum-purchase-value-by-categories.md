---
title: "Valeur d'achat maximale par catégories - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Valeur d'achat maximale par catégories par MyPresta.eu."
sidebar:
  label: "Valeur d'achat maximale par catégories - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Maximum purchase value by categories sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-purchase-value-by-categories.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/maximum-purchase-value-by-categories/)
>
> ---


# Valeur d'achat maximale par catégories

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune exigence d'hébergement spéciale au-delà d'une configuration PrestaShop standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module, où vous gérez les paramètres généraux et accédez aux règles pour les valeurs d'achat maximales.

- **Ce que fait ce paramètre :** Cette page fournit des informations générales sur le module et inclut souvent un lien ou un bouton pour gérer les règles réelles.
- **Effet de la modification de ce paramètre :** Bien que cet écran spécifique puisse ne pas avoir de « paramètres » directs à modifier, il sert de point d'entrée à la fonctionnalité du module.
- **Valeur recommandée :** N/A (Ceci est un écran d'information).
- **Scénario / exemple de marchand :** Après l'installation, vous atterrirez ici. Vous cliquerez ensuite sur un bouton ou un lien (par exemple, « Gérer les règles » ou « Configurer les valeurs maximales ») pour passer à l'écran dédié où vous définissez vos limites de catégorie.

### 2.2 Écran d'administration dédié : Règles de valeur d'achat maximale (Back Office > Modules > Valeur d'achat maximale par catégories > Configurer)

C'est le cœur du module où vous définissez et gérez vos règles de valeur d'achat maximale pour différentes catégories. Vous trouverez généralement cet écran en cliquant sur « Configurer » après l'installation du module, ou en naviguant vers **Modules > Gestionnaire de modules**, en trouvant le module et en cliquant sur « Configurer ».

**Nom de l'écran et emplacement du menu :**
Vous accéderez à cet écran en naviguant vers **Modules > Gestionnaire de modules**, en recherchant « Valeur d'achat maximale par catégories » et en cliquant sur le bouton « Configurer ». Cela vous mènera à une interface d'administration dédiée pour gérer vos règles.

**Actions et paramètres disponibles :**
Sur cet écran, vous verrez une liste (grille) de toutes vos règles de valeur d'achat maximale actuellement définies. Pour chaque règle, vous verrez généralement :

- **Nom de la catégorie :** Le nom de la catégorie de produits à laquelle la règle s'applique.
- **Valeur maximale :** La valeur totale la plus élevée (dans votre devise par défaut) autorisée pour les produits de cette catégorie dans une seule commande.
- **Actions :** Boutons pour « Modifier » une règle existante ou la « Supprimer ».

Vous trouverez également :

- **Bouton « Ajouter une nouvelle règle » :** Un bouton proéminent pour créer une nouvelle règle de valeur d'achat maximale.

**Lors de l'ajout ou de la modification d'une règle, vous rencontrerez généralement les champs suivants :**

1. **Sélectionner une catégorie :**

   - **Ce que fait ce paramètre :** Vous permet de choisir la catégorie de produits spécifique à laquelle cette règle de valeur d'achat maximale s'appliquera. Vous verrez généralement une liste déroulante ou un sélecteur d'arborescence de catégories.
   - **Effet de la modification de ce paramètre :**
     - *Lorsqu'une catégorie est sélectionnée :* La règle s'appliquera à tous les produits de cette catégorie (et souvent à ses sous-catégories, selon la logique du module).
     - *Lorsqu'aucune catégorie n'est sélectionnée (ou si vous la modifiez) :* La règle sera soit invalide, soit s'appliquera à une autre catégorie.
   - **Valeur recommandée :** Sélectionnez la catégorie spécifique que vous souhaitez limiter.
   - **Scénario / exemple de marchand :** Vous souhaitez limiter les achats de produits « Électronique ». Vous sélectionneriez « Électronique » dans la liste.
2. **Valeur d'achat maximale :**

   - **Ce que fait ce paramètre :** C'est la valeur numérique (dans la devise par défaut de votre boutique) qui représente le total le plus élevé autorisé pour les produits de la catégorie sélectionnée dans le panier d'un client.
   - **Effet de la modification de ce paramètre :**
     - *Lorsqu'une valeur spécifique est définie (par exemple, 500) :* Les clients ne pourront pas avoir plus de 500 unités de la devise par défaut de votre boutique en produits de la catégorie sélectionnée dans leur panier.
     - *Lorsqu'elle est définie à 0 ou laissée vide (si autorisé) :* Cela pourrait désactiver la règle pour la catégorie ou être considéré comme une entrée invalide.
   - **Valeur recommandée :** Une valeur numérique positive représentant votre limite souhaitée (par exemple, `250.00`).
   - **Scénario / exemple de marchand :** Vous souhaitez limiter les « Impressions d'art en édition limitée » à un maximum de 250 $ par commande. Vous saisiriez `250` ici. Le module calculera automatiquement les valeurs équivalentes pour les autres devises si votre boutique les prend en charge.

**Effet des modifications :**

- **Ajout d'une nouvelle règle :** Applique immédiatement la valeur d'achat maximale pour la catégorie sélectionnée dans votre boutique. Les clients seront empêchés de dépasser cette limite.
- **Modification d'une règle :** Met à jour la valeur maximale pour une catégorie existante. La nouvelle limite prend effet immédiatement.
- **Suppression d'une règle :** Supprime la restriction pour cette catégorie. Les clients ne seront plus limités dans leurs achats de cette catégorie.

**Flux de travail recommandé pour la gestion quotidienne de la boutique :**

1. Examinez périodiquement vos catégories de produits et identifiez celles qui pourraient bénéficier d'une limite de valeur d'achat (par exemple, nouveaux produits très demandés, articles en stock limité ou produits avec des accords de distribution spécifiques).
2. Naviguez vers l'écran de configuration « Valeur d'achat maximale par catégories ».
3. Utilisez le bouton « Ajouter une nouvelle règle » pour créer de nouvelles limites.
4. Surveillez les commentaires des clients ou les modèles de commande pour ajuster les limites existantes si nécessaire à l'aide de l'action « Modifier ».
5. Si une ligne de produits ou une catégorie ne nécessite plus de limite, utilisez l'action « Supprimer » pour supprimer la règle.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| AdminMaobcController (Gestion des règles) | **Sélectionner une catégorie** | Nom de catégorie spécifique | Définit la catégorie de produits à laquelle la valeur maximale s'applique. |
| AdminMaobcController (Gestion des règles) | **Valeur d'achat maximale** | Valeur numérique (par exemple, `250.00`) | Définit la valeur totale la plus élevée autorisée pour les produits de la catégorie sélectionnée dans une seule commande (dans la devise par défaut). Convertit automatiquement pour les autres devises. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai défini une limite, mais les clients peuvent toujours la dépasser. Qu'est-ce qui ne va pas ?**
R1 :

- **Vérifier l'affectation des catégories :** Assurez-vous que les produits en question sont correctement affectés à la catégorie pour laquelle vous avez défini la limite.
- **Module activé :** Vérifiez que le module « Valeur d'achat maximale par catégories » est activé dans **Modules > Gestionnaire de modules**.
- **Règle active :** Accédez à la configuration du module et confirmez que la règle pour la catégorie spécifique est présente et a une valeur maximale valide.
- **Vider le cache :** Parfois, le cache de PrestaShop peut empêcher les modifications de prendre effet immédiatement. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ».

**Q2 : Le module affiche la mauvaise devise ou ne convertit pas correctement.**
R2 : Le module utilise automatiquement la devise par défaut de votre boutique pour la valeur que vous saisissez, puis la convertit pour les autres devises.

- **Devise par défaut :** Assurez-vous que votre devise par défaut est correctement définie dans **International > Devises**. La valeur que vous saisissez dans la configuration du module doit toujours être dans cette devise par défaut.
- **Taux de change :** Vérifiez vos taux de change dans **International > Devises** pour vous assurer qu'ils sont à jour et précis pour les devises que vous prenez en charge.

**Q3 : Puis-je définir des limites différentes pour différents groupes de clients ?**
R3 : Ce module spécifique définit une limite globale par catégorie, s'appliquant à tous les clients. Si vous avez besoin de limites différentes pour des groupes de clients spécifiques (par exemple, grossistes vs détaillants), vous auriez besoin d'un module plus avancé ou d'un développement personnalisé.

**Q4 : Comment traduire les messages d'erreur affichés aux clients ?**
R4 : Les messages du front-office du module sont généralement traduisibles via le système de traduction de PrestaShop :

1. Allez dans **International > Traductions**.
2. Sélectionnez « Traductions des modules installés ».
3. Choisissez votre thème, la langue, puis sélectionnez « Valeur d'achat maximale par catégories » dans la liste des modules.
4. Vous pouvez ensuite trouver et modifier les chaînes de texte affichées par le module à vos clients.

**Q5 : Le module semble entrer en conflit avec un autre module dans mon panier/paiement.**
R5 : Des conflits de modules peuvent parfois survenir.

- **Isoler le problème :** Désactivez temporairement les autres modules qui interagissent avec le panier ou la page produit un par un pour voir si le conflit se résout.
- **Compatibilité du thème :** Si vous utilisez un thème personnalisé, il pourrait avoir des surcharges spécifiques qui interfèrent. Vérifiez si le problème persiste avec le thème PrestaShop par défaut.
- **Contacter le support :** Si vous ne parvenez pas à identifier le conflit, rassemblez les détails (quels modules, quelle erreur exacte) et contactez le support MyPresta.eu pour obtenir de l'aide.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Valeur d'achat maximale par catégories » (`maobc`) suit un modèle MVC (Modèle-Vue-Contrôleur) PrestaShop standard. Il utilise principalement un contrôleur d'administration pour gérer la configuration et les règles, et un contrôleur frontal pour intercepter les requêtes AJAX liées aux mises à jour du panier. La logique principale réside dans la classe principale du module, qui s'accroche à divers événements PrestaShop pour appliquer les limites de valeur basées sur les catégories. Il stocke sa configuration dans la table `ps_configuration` et gère ses règles via une table personnalisée et un contrôleur d'administration.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :

  - `controllers/front/ajax.php`
    - **Nom de la classe** : `MaobcAjaxModuleFrontController` (étend `ModuleFrontController`)
    - **Responsabilité** : Ce contrôleur est responsable de la gestion des requêtes AJAX du front-office, principalement celles liées à l'ajout de produits au panier ou à la mise à jour des quantités du panier. Il intercepte ces requêtes pour effectuer une validation en temps réel par rapport aux règles de valeur d'achat maximale définies avant que PrestaShop ne traite la mise à jour du panier. Il renvoie des réponses JSON indiquant le succès ou l'échec avec des messages appropriés.
  - `controllers/front/index.php`
    - **Nom de la classe** : `MaobcIndexModuleFrontController` (étend `ModuleFrontController`)
    - **Responsabilité** : Ce contrôleur pourrait servir de solution de repli ou de simple point d'entrée, mais compte tenu de la fonctionnalité du module, `ajax.php` est le principal point d'interaction du front-office. Il pourrait rendre une page simple ou rediriger s'il est accédé directement.
- **Contrôleurs d'administration Back-Office** :

  - `controllers/admin/AdminMaobc.php`
    - **Nom de la classe** : `AdminMaobcController` (étend `ModuleAdminController`)
    - **Nom de l'onglet** : « Valeur d'achat maximale par catégories » (ou similaire, accessible via le bouton « Configurer » du module).
    - **Entité gérée** : Ce contrôleur gère l'entité `maobc` personnalisée, qui représente les règles individuelles pour les valeurs d'achat maximales par catégorie. Il gère les opérations CRUD (Créer, Lire, Mettre à jour, Supprimer) pour ces règles.
    - **Responsabilité** : Affiche une liste (grille) de toutes les règles configurées, permet aux administrateurs d'ajouter de nouvelles règles, de modifier celles existantes (en sélectionnant une catégorie et en définissant une valeur maximale) et de supprimer des règles. Il interagit avec le stockage interne des données du module (probablement une table de base de données personnalisée ou des entrées `ps_configuration`).
  - `controllers/admin/index.php`
    - **Nom de la classe** : `AdminMaobcIndexController` (étend `ModuleAdminController`)
    - **Responsabilité** : Similaire au `index.php` du front-office, cela pourrait être un simple point d'entrée ou une solution de repli. L'`AdminMaobcController` est le contrôleur principal pour la gestion des règles du module.

### 4.3 Classes et modèles principaux (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que la logique principale du module et la gestion des données sont probablement intégrées directement dans le fichier principal du module (`maobc/index.php`) ou gérées via la classe `Configuration` standard de PrestaShop pour les paramètres et potentiellement une table de base de données personnalisée gérée directement par l'`AdminMaobcController` sans `ObjectModel` dédié.

### 4.4 Actifs JavaScript (`views/js/`)

- `views/js/maobc.js`
  - **Portée** : Front-office.
  - **Détails** : Ce script est probablement responsable des interactions côté client liées aux mises à jour du panier. Il pourrait :
    - Surcharger ou étendre les fonctions de panier AJAX par défaut de PrestaShop (par exemple, les clics sur le bouton `ajouter au panier`).
    - Intercepter les réponses AJAX de `controllers/front/ajax.php` pour afficher des messages d'erreur personnalisés à l'utilisateur si une valeur maximale est dépassée.
    - Potentiellement mettre à jour l'interface utilisateur (par exemple, désactiver les boutons, afficher des alertes) en fonction des résultats de la validation.
    - Il utilisera probablement `jQuery` ou les événements `prestashop.on` pour lier sa logique.

### 4.5 Feuilles de style CSS (`views/css/`)

- `views/css/maobc.css`
  - **Portée** : Front-office.
  - **Détails** : Cette feuille de style fournit un style personnalisé pour les éléments du front-office du module, principalement les messages de notification affichés aux clients lorsqu'une valeur d'achat maximale est dépassée.
  - **Sélecteurs de classe CSS clés** : Les développeurs doivent inspecter ce fichier pour des classes comme `.maobc-error-message`, `.maobc-alert`, ou similaires, qui peuvent être surchargées dans le `custom.css` ou `theme.css` de leur thème pour correspondre à l'image de marque de la boutique.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **Modèles de hook (`views/templates/hook/`)** :

  - Le dossier du module ne liste pas explicitement les modèles dans `views/templates/hook/`. Cela suggère que tous les messages ou contenus dynamiques pourraient être injectés directement via JavaScript ou rendus par le fichier principal du module à l'aide de méthodes `display()`.
- **Modèles d'administration (`views/templates/admin/`)** :

  - Le dossier du module ne liste pas explicitement les modèles dans `views/templates/admin/`. L'`AdminMaobcController` utilise probablement des formulaires d'aide PrestaShop standard (`HelperList`, `HelperForm`) pour sa grille et ses formulaires de configuration, qui génèrent leur HTML dynamiquement.
- **Modèles Front-Office (`views/templates/front/`)** :

  - `views/templates/front/displayShoppingCart.tpl`
    - **Objectif** : Ce modèle est probablement utilisé pour afficher le message d'erreur personnalisé sur la page du panier si la valeur d'achat maximale pour une catégorie est dépassée. Il contiendrait la structure HTML de l'alerte ou de la notification qui informe le client de la limite. Il est probablement accroché à un `displayShoppingCartFooter` ou un hook similaire.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module crée probablement une table de base de données personnalisée (par exemple, `ps_maobc_rules`) pour stocker l'ID de catégorie et la valeur d'achat maximale associée pour chaque règle.
  - Les valeurs de configuration (par exemple, l'état activé du module, les paramètres généraux) sont stockées dans la table `ps_configuration`, généralement avec des clés préfixées `MAOBC_`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rendu dans la section `<head>` de toutes les pages du front-office. | Potentiellement utilisé pour charger les actifs `maobc.js` et `maobc.css`, ou pour injecter des variables JavaScript. |
| `displayRightColumn` / `displayLeftColumn` | Rend le contenu dans les colonnes latérales. | Moins probable pour ce module, mais pourrait être utilisé pour afficher un message statique sur les limites d'achat. |
| `displayProductAdditionalInfo` / `displayProductButtons` | Rendu sur la page du produit. | Pourrait être utilisé pour afficher un message d'avertissement sur la page du produit si l'article appartient à une catégorie restreinte. |
| `displayShoppingCartFooter` / `displayShoppingCart` | Rendu sur la page du panier. | Utilisé pour afficher le modèle `displayShoppingCart.tpl` avec des messages d'erreur si les limites sont dépassées. |
| `actionCartSave` | Exécuté après l'enregistrement d'un panier (par exemple, produit ajouté/supprimé, quantité modifiée). | Crucial pour la validation côté serveur du contenu du panier par rapport aux limites de catégorie. C'est là que la logique principale empêche les états de panier invalides. |
| `actionAjaxDieCartController` | Exécuté avant une réponse AJAX du CartController. | Permet au module d'intercepter et de modifier les réponses AJAX, en injectant des messages d'erreur personnalisés si les limites sont dépassées lors des mises à jour du panier AJAX. |
| `actionFrontControllerSetMedia` | Exécuté avant qu'un contrôleur frontal ne rende sa sortie. | Utilisé pour enregistrer les fichiers CSS et JavaScript du front-office. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour télécharger les dernières versions du module « Valeur d'achat maximale par catégories », veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité ou l'intégration du module.
