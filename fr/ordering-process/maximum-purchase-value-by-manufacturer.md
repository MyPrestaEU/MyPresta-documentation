---
title: "Valeur d'achat maximale par fabricant - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Valeur d'achat maximale par fabricant' par MyPresta.eu."
sidebar:
  label: "Valeur d'achat maximale par fabricant - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Maximum purchase value by manufacturer sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-purchase-value-by-manufacturer.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/maximum-purchase-value-by-manufacturer/)
>
> ---


# Valeur d'achat maximale par fabricant

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration spéciale du serveur n'est généralement nécessaire.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal où vous pouvez activer ou désactiver le module et accéder à la zone de gestion dédiée pour configurer les limites par fabricant.

- **Ce que fait ce paramètre :** Cette section contient généralement un simple interrupteur pour activer ou désactiver la fonctionnalité principale du module. Elle fournit également un lien direct vers l'écran dédié où vous définissez les valeurs d'achat maximales réelles pour les fabricants.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Le module vérifiera activement les paniers des clients par rapport aux limites définies par le fabricant et empêchera les commandes si les limites sont dépassées.
  - *Lorsqu'il est désactivé :* Le module cessera de fonctionner et aucune limite d'achat par fabricant ne sera appliquée.
- **Valeur recommandée :** "OUI" (Activé) si vous avez l'intention d'utiliser les fonctionnalités du module.
- **Scénario / exemple de marchand :** Vous venez d'installer le module et souhaitez commencer à définir des limites. Vous l'activeriez ici, puis passeriez à la section "Gérer les limites par fabricant".

### 2.2 Écran d'administration dédié : Limites par fabricant (Back Office > Modules > Valeur d'achat maximale par fabricant > Configurer > Bouton "Gérer les limites par fabricant" ou une entrée de menu dédiée)

Cet écran est l'endroit où vous définissez et gérez les valeurs d'achat maximales réelles pour chaque fabricant. Il présentera généralement une liste de vos fabricants et vous permettra d'ajouter, de modifier ou de supprimer des règles.

**Nom de l'écran et emplacement du menu :**
Vous accéderez à cet écran en cliquant sur le bouton "Configurer" à côté du module dans le Gestionnaire de modules, puis probablement en cliquant sur un bouton proéminent comme "Gérer les limites par fabricant" ou "Ajouter une nouvelle règle". Alternativement, le module pourrait créer un nouvel élément de menu sous "Catalogue" ou "Paramètres de la boutique" pour un accès direct à `AdminMaobm`.

**Actions et paramètres disponibles :**

1. **Tableau de liste des règles existantes :**

   - Vous verrez un tableau listant toutes les limites par fabricant que vous avez déjà configurées.
   - Les colonnes incluent généralement : Nom du fabricant, Valeur maximale, et des actions comme "Modifier" ou "Supprimer".
   - **Effet des modifications :** Ce tableau fournit un aperçu de vos règles actives. La suppression d'une règle supprimera la limite d'achat pour ce fabricant spécifique.
   - **Flux de travail recommandé :** Examinez régulièrement ce tableau pour vous assurer que vos limites sont à jour avec vos besoins commerciaux.
2. **Formulaire Ajouter / Modifier une règle :**

   - Lorsque vous cliquez sur "Ajouter" ou "Modifier" une règle existante, vous verrez généralement un formulaire avec les champs suivants :
     - **Fabricant :** Une liste déroulante ou une boîte de recherche pour sélectionner le fabricant auquel vous souhaitez appliquer la limite.
       - **Ce que fait ce paramètre :** Spécifie le fabricant auquel cette règle s'applique.
       - **Effet de la modification de ce paramètre :** La règle ne s'appliquera qu'aux produits associés au fabricant sélectionné.
       - **Valeur recommandée :** Sélectionnez le fabricant spécifique que vous souhaitez limiter.
       - **Scénario / exemple de marchand :** Vous souhaitez définir une limite pour les produits "Acme Corp.", vous sélectionnez donc "Acme Corp." dans la liste.
     - **Valeur d'achat maximale :** Un champ de saisie où vous entrez la valeur totale maximale (dans la devise par défaut de votre boutique) qu'un client peut acheter auprès du fabricant sélectionné en une seule commande.
       - **Ce que fait ce paramètre :** Définit le plafond monétaire pour les produits du fabricant choisi.
       - **Effet de la modification de ce paramètre :** Si la valeur totale des produits de ce fabricant dans le panier d'un client dépasse ce nombre, il sera empêché de commander.
       - **Valeur recommandée :** Une valeur numérique représentant le total maximal autorisé, par exemple, "500.00" pour 500 unités de votre devise par défaut.
       - **Scénario / exemple de marchand :** Vous souhaitez limiter les produits "Acme Corp." à un maximum de 500 € par commande. Vous entreriez "500" ici.
     - **Bouton Enregistrer :** Pour appliquer vos modifications.
       - **Effet des modifications :** Enregistre la nouvelle règle ou met à jour une règle existante dans la base de données, la rendant active immédiatement.

**Flux de travail recommandé pour la gestion quotidienne de la boutique :**

- **Configuration initiale :** Parcourez votre liste de fabricants et identifiez ceux pour lesquels vous devez définir des limites d'achat. Ajoutez une nouvelle règle pour chacun.
- **Surveillance :** Gardez un œil sur vos ventes et vos stocks. Si vous remarquez que les produits d'un fabricant sont achetés en quantités excessives, ou si les accords avec les fournisseurs changent, revenez à cet écran pour ajuster ou ajouter de nouvelles limites.
- **Mises à jour :** Lorsque de nouveaux fabricants sont ajoutés à votre boutique, déterminez s'ils nécessitent une règle de limite d'achat.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Statut du module (Activer/Désactiver) | Activé | Active ou désactive la fonctionnalité du module. |
| `AdminMaobmController` (Limites par fabricant) | Fabricant | Sélectionner dans la liste | Spécifie le fabricant auquel la limite s'applique. |
| `AdminMaobmController` (Limites par fabricant) | Valeur d'achat maximale | Votre limite monétaire souhaitée (par exemple, 500.00) | Définit la valeur totale maximale pour les produits du fabricant sélectionné en une seule commande. Le dépassement de cette limite bloque le processus de commande. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Un client essaie de passer commande, mais il voit un message concernant le dépassement d'une limite de fabricant. Que dois-je faire ?**
R : Cela signifie que le module fonctionne comme prévu. Le client a trop d'articles d'un fabricant spécifique dans son panier, et la valeur totale de ces articles dépasse la limite que vous avez définie. Vous pouvez soit :
1. Conseiller au client de réduire la quantité d'articles de ce fabricant.
2. Désactiver temporairement ou ajuster la limite pour ce fabricant dans la configuration du module si vous estimez la commande acceptable (mais soyez prudent avec cela).

**Q : J'ai défini une limite, mais elle ne semble pas fonctionner. Les clients peuvent toujours commander plus que le maximum.**
R :
1. **Vérifier le statut du module :** Assurez-vous que le module est activé dans **Modules > Gestionnaire de modules** et sur sa page de configuration principale.
2. **Vérifier la règle :** Revérifiez la règle que vous avez créée dans l'écran "Gérer les limites par fabricant". Le bon fabricant est-il sélectionné ? La "Valeur d'achat maximale" est-elle correctement définie ?
3. **Vider le cache :** Parfois, le cache de PrestaShop peut empêcher les modifications de prendre effet immédiatement. Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache".
4. **Fabricant du produit :** Assurez-vous que les produits en question sont correctement attribués au fabricant pour lequel vous avez défini la limite. Vérifiez les paramètres du produit dans votre catalogue.

**Q : Puis-je définir des limites différentes pour différents groupes de clients ?**
R : Ce module, dans sa forme standard, applique une seule limite par fabricant à tous les clients. Si vous avez besoin de limites spécifiques à des groupes de clients, cela nécessiterait un développement personnalisé.

**Q : Le message d'avertissement n'est pas clair ou ne correspond pas à la langue/au thème de ma boutique.**
R :
1. **Traductions :** Allez dans **International > Traductions**, sélectionnez "Traductions des modules installés", votre thème, et le module "Valeur d'achat maximale par fabricant". Vous pouvez personnaliser le texte du message d'avertissement ici.
2. **Style du thème :** Le module utilise le style standard de PrestaShop pour ses messages. S'il semble déplacé, votre thème pourrait avoir un CSS personnalisé qui nécessite un ajustement. Un webmaster peut inspecter le fichier `maobm.css` et le CSS de votre thème pour le rendre visuellement cohérent.

**Q : Que se passe-t-il si un produit n'a pas de fabricant attribué ?**
R : Les produits sans fabricant attribué ne seront soumis à aucune limite définie par ce module, car les règles sont spécifiques aux fabricants.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module "Valeur d'achat maximale par fabricant" (`maobm`) suit une architecture de module PrestaShop standard. Il utilise principalement une classe `Module` pour l'installation et la configuration de base, un `AdminController` pour gérer les limites par fabricant, et des `FrontController`s pour gérer les requêtes AJAX et s'intégrer au processus de panier du front-office. Le module exploite le système de hooks de PrestaShop pour injecter sa logique dans le flux du panier et de la commande, empêchant les commandes si les limites sont dépassées. Il stocke sa configuration dans `ps_configuration` et gère les limites spécifiques des fabricants via une table de base de données dédiée (bien qu'aucun `ObjectModel` ne soit explicitement listé, cela implique une interaction directe avec la base de données ou un simple `AdminController` gérant la configuration).

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office :**

  - `controllers/front/ajax.php`
    - **Nom de la classe :** `MaobmAjaxModuleFrontController` (implicite, étend `ModuleFrontController`)
    - **Responsabilité :** Ce contrôleur gère probablement les requêtes AJAX du front-office, par exemple lorsqu'un client met à jour son panier. Il réévaluerait les limites par fabricant et renverrait une réponse (par exemple, un message d'avertissement ou un statut indiquant si la commande peut être passée). Il pourrait être hooké sur `actionCartSave` ou des événements similaires pour fournir un retour d'information en temps réel.
  - `controllers/front/index.php`
    - **Nom de la classe :** `MaobmIndexModuleFrontController` (implicite, étend `ModuleFrontController`)
    - **Responsabilité :** Ce contrôleur pourrait servir de solution de repli ou de simple point d'entrée, bien que sa fonction principale puisse être minimale si `ajax.php` gère la plupart des interactions front-end. Il pourrait potentiellement afficher un message générique ou rediriger s'il est accédé directement.
- **Contrôleurs d'administration Back-Office :**

  - `controllers/admin/AdminMaobm.php`
    - **Nom de la classe :** `AdminMaobmController` (étend `ModuleAdminController`)
    - **Nom de l'onglet :** Probablement un onglet personnalisé créé par le module, ou accessible via la page de configuration du module.
    - **Entité gérée :** Gère les règles spécifiques de limite par fabricant. Il fournit l'interface pour lister, ajouter, modifier et supprimer ces règles. Ce contrôleur interagirait directement avec la base de données pour stocker et récupérer les ID des fabricants et leurs valeurs maximales associées. Il utiliserait généralement `HelperList` pour le tableau d'aperçu et `HelperForm` pour le formulaire d'ajout/modification.
  - `controllers/admin/index.php`
    - **Nom de la classe :** `AdminMaobmIndexController` (implicite, étend `ModuleAdminController`)
    - **Responsabilité :** Similaire au `index.php` du front-office, cela pourrait être un espace réservé ou une simple redirection. Dans PrestaShop, les fichiers `index.php` dans les répertoires de contrôleurs servent souvent de mesures de sécurité pour empêcher la liste directe des répertoires.

### 4.3 Classes et modèles principaux (`classes/`)

L'inventaire fourni n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que le module :

1. Manipule directement les tables de base de données (par exemple, `ps_maobm_limits`) en utilisant `Db::getInstance()` dans ses contrôleurs ou le fichier de module principal.
2. Stocke toute la configuration dans `ps_configuration` en utilisant `Configuration::updateValue()`, avec l'`AdminMaobmController` gérant ces entrées de configuration.
   Compte tenu de la fonctionnalité "nombre illimité de règles", l'interaction directe avec la base de données pour une table personnalisée est plus probable que `ps_configuration` pour stocker plusieurs limites par fabricant.

### 4.4 Actifs JavaScript (`views/js/`)

- `views/js/maobm.js`
  - **Portée :** Probablement Front-office.
  - **Détails :** Ce script serait responsable des interactions côté client liées à la fonctionnalité du module. Il pourrait :
    - Lier des écouteurs d'événements aux actions de mise à jour du panier (par exemple, changements de quantité, suppression de produit).
    - Effectuer des appels AJAX à `controllers/front/ajax.php` pour réévaluer les limites par fabricant en temps réel sans rechargement complet de la page.
    - Afficher des messages d'avertissement ou désactiver le bouton de paiement si les limites sont dépassées, en fonction de la réponse AJAX.
    - Potentiellement s'intégrer aux événements `prestashop.on` de PrestaShop pour une meilleure compatibilité.

### 4.5 Feuilles de style CSS (`views/css/`)

- `views/css/maobm.css`
  - **Portée :** Principalement Front-office, éventuellement un peu de style Back-office pour les éléments personnalisés.
  - **Détails :** Cette feuille de style contiendrait les règles CSS nécessaires pour styliser les messages d'avertissement affichés au client dans le panier ou le processus de commande. Elle pourrait définir des classes pour :
    - `#maobm-warning-message` ou des conteneurs similaires pour le texte d'erreur.
    - Le style des boutons de paiement désactivés.
    - Assurer la réactivité sur différentes tailles d'écran.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger :** Recherchez des classes comme `.maobm-alert`, `.maobm-error-message`, ou des ID spécifiques utilisés pour le conteneur d'avertissement.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`) :**

  - `views/templates/front/displayShoppingCart.tpl`
    - **Hook :** Ce template est probablement rendu dans un hook qui apparaît sur la page du panier, tel que `displayShoppingCartFooter` ou `displayShoppingCart`.
    - **Sortie :** Il serait responsable d'afficher le message d'avertissement au client s'il dépasse la limite d'achat d'un fabricant. Il recevrait des variables du module indiquant si une limite est dépassée et le message pertinent à afficher.
- **Templates d'administration (`views/templates/admin/`) :** (Non explicitement listé, mais implicite par `AdminMaobmController`)

  - L'`AdminMaobmController` utiliserait généralement les templates `HelperList` et `HelperForm` de PrestaShop pour son interface, mais il pourrait avoir des fichiers `.tpl` personnalisés pour des parties spécifiques de sa configuration ou pour afficher une liste de règles. Ceux-ci se trouveraient généralement dans `views/templates/admin/maobm/` ou similaire.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données :**

  - `ps_maobm_limits` (Implicite) : Une table personnalisée pour stocker les limites par fabricant.
    - `id_maobm_limit` (Clé primaire, AUTO_INCREMENT)
    - `id_manufacturer` (Clé étrangère vers `ps_manufacturer.id_manufacturer`)
    - `max_value` (Décimal ou Flottant, stockant la valeur d'achat maximale autorisée)
    - `date_add`, `date_upd` (Horodatages PrestaShop standard)
  - `ps_configuration` : Le module pourrait stocker des paramètres généraux (comme le statut activé/désactivé du module) ici.
- **Table des hooks enregistrés :**

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rendu dans la section `<head>` de toutes les pages du front-office. | Pour inclure les actifs `maobm.css` et `maobm.js`. |
| `displayShoppingCart` ou `displayShoppingCartFooter` | Rend le contenu sur la page du panier. | Pour afficher le message d'avertissement (`displayShoppingCart.tpl`) si les limites sont dépassées. |
| `actionCartSave` | Exécuté après l'enregistrement ou la mise à jour d'un panier. | Pour réévaluer les limites par fabricant et potentiellement mettre à jour le statut du panier ou afficher des messages. |
| `actionValidateOrder` | Exécuté avant qu'une commande ne soit officiellement validée. | **CRITIQUE** : Pour effectuer une vérification finale des limites par fabricant et empêcher la validation de la commande si les limites sont dépassées. C'est là que résiderait la logique de blocage de la commande. |
| `displayAdminProductsExtra` (ou similaire) | Pourrait être utilisé pour afficher les informations de limite par fabricant directement sur la page d'édition du produit dans le BO. | (Facultatif) Pour fournir un accès rapide aux informations de limite pour le fabricant du produit. |
| `displayBackOfficeHeader` | Rendu dans la section `<head>` de toutes les pages du back-office. | Pour inclure les CSS/JS spécifiques au back-office pour `AdminMaobmController`. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et le support officiel du module "Valeur d'achat maximale par fabricant", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la configuration du module.
