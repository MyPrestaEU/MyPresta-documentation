---
title: "Changement de type de produit en masse - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Changement de type de produit en masse' par MyPresta.eu."
sidebar:
  label: "Changement de type de produit en masse - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Mass change product type sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-change-product-type.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/mass-change-product-type/)
>
> ---


# Changement de type de produit en masse

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes et sont habituellement activées par défaut sur la plupart des environnements d'hébergement.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

Le module « Changement de type de produit en masse » offre un écran de configuration unique et intuitif dans votre Back Office PrestaShop. Cet écran vous guide à travers la sélection des produits, puis l'application du changement de type de produit souhaité.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Pour accéder à la configuration du module, naviguez vers **Modules > Gestionnaire de modules**, recherchez « Changement de type de produit en masse », et cliquez sur **« Configurer »**.

La page de configuration est divisée en deux sections principales : **1. Sélectionner les produits** et **2. Que faire avec les produits sélectionnés**.

#### Section 1 : Sélectionner les produits

Cette section vous permet de définir quels produits seront affectés par le changement en masse. Vous pouvez sélectionner des produits en fonction de divers critères.

##### 1.1 Sélectionner les produits par catégorie

- **Ce que fait ce paramètre :** Vous permet de sélectionner tous les produits appartenant à une ou plusieurs catégories spécifiques.
- **Effet de la modification de ce paramètre :**
  - *Lorsque des catégories sont sélectionnées :* Seuls les produits des catégories choisies seront pris en compte pour le changement de type.
  - *Lorsque aucune catégorie n'est sélectionnée :* Ce critère ne sera pas utilisé pour filtrer les produits.
- **Valeur recommandée :** Sélectionnez les catégories pertinentes pour votre opération de changement en masse.
- **Scénario / exemple pour le marchand :** Vous souhaitez convertir tous les produits de votre catégorie « Téléchargements numériques » de produits standard en produits virtuels. Vous sélectionneriez la catégorie « Téléchargements numériques » ici.

##### 1.2 Sélectionner les produits par marque

- **Ce que fait ce paramètre :** Vous permet de sélectionner tous les produits associés à une ou plusieurs marques (fabricants) spécifiques.
- **Effet de la modification de ce paramètre :**
  - *Lorsque des marques sont sélectionnées :* Seuls les produits des marques choisies seront pris en compte pour le changement de type.
  - *Lorsque aucune marque n'est sélectionnée :* Ce critère ne sera pas utilisé pour filtrer les produits.
- **Valeur recommandée :** Sélectionnez les marques pertinentes pour votre opération de changement en masse.
- **Scénario / exemple pour le marchand :** Vous avez décidé de vendre tous les produits de « Marque X » sous forme de packs. Vous sélectionneriez « Marque X » ici.

##### 1.3 Sélectionner les produits par caractéristique

- **Ce que fait ce paramètre :** Vous permet de sélectionner les produits qui ont une caractéristique spécifique et, éventuellement, une valeur spécifique pour cette caractéristique.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une caractéristique (et éventuellement une valeur) est sélectionnée :* Seuls les produits correspondant à ce critère de caractéristique seront pris en compte.
  - *Lorsqu'aucune caractéristique n'est sélectionnée :* Ce critère ne sera pas utilisé pour filtrer les produits.
- **Valeur recommandée :** Choisissez la caractéristique et la valeur qui identifient précisément les produits que vous souhaitez modifier.
- **Scénario / exemple pour le marchand :** Vous souhaitez changer tous les produits dont la caractéristique « Matériau » est définie sur « Numérique » en produits virtuels. Vous sélectionneriez « Matériau » puis « Numérique » ici.

##### 1.4 Sélectionner les produits par attribut

- **Ce que fait ce paramètre :** Vous permet de sélectionner les produits qui ont un attribut spécifique et, éventuellement, une valeur spécifique pour cet attribut. Ceci est utile pour les produits avec combinaisons.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'un attribut (et éventuellement une valeur) est sélectionné :* Seuls les produits correspondant à ce critère d'attribut seront pris en compte.
  - *Lorsqu'aucun attribut n'est sélectionné :* Ce critère ne sera pas utilisé pour filtrer les produits.
- **Valeur recommandée :** Choisissez l'attribut et la valeur qui identifient précisément les produits que vous souhaitez modifier.
- **Scénario / exemple pour le marchand :** Vous souhaitez convertir tous les produits ayant l'attribut « Taille » défini sur « Téléchargeable » en produits virtuels. Vous sélectionneriez « Taille » puis « Téléchargeable » ici.

##### 1.5 Sélectionner les produits par phrase de recherche

- **Ce que fait ce paramètre :** Vous permet de sélectionner les produits dont les noms contiennent une phrase spécifique. Cela utilise un outil de recherche pour trouver des produits.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une phrase de recherche est saisie :* Les produits dont les noms correspondent à la phrase seront ajoutés à la sélection.
  - *Lorsqu'aucune phrase de recherche n'est saisie :* Ce critère ne sera pas utilisé pour filtrer les produits.
- **Valeur recommandée :** Saisissez une phrase claire et concise pour identifier vos produits cibles.
- **Scénario / exemple pour le marchand :** Vous souhaitez changer tous les produits dont le nom contient « eBook » en produits virtuels. Vous taperiez « eBook » dans la boîte de recherche.

##### 1.6 Liste des produits sélectionnés

- **Ce que fait ce paramètre :** Après avoir appliqué l'un des filtres ci-dessus, cette zone affichera une liste de produits qui correspondent à vos critères. Vous pouvez supprimer manuellement des produits de cette liste si vous ne souhaitez pas qu'ils soient affectés.
- **Effet de la modification de ce paramètre :**
  - *Suppression d'un produit :* Ce produit spécifique sera exclu du changement de type en masse.
  - *Laisser les produits dans la liste :* Ils seront inclus dans le changement de type en masse.
- **Valeur recommandée :** Examinez toujours attentivement cette liste pour vous assurer que seuls les produits souhaités sont sélectionnés.
- **Scénario / exemple pour le marchand :** Vous avez recherché « eBook » mais un livre physique intitulé « Manuel du lecteur eBook » est apparu. Vous supprimeriez ce produit spécifique de la liste.

#### Section 2 : Que faire avec les produits sélectionnés

Une fois que vous avez sélectionné vos produits cibles, cette section vous permet de choisir le nouveau type de produit que vous souhaitez appliquer.

##### 2.1 Changer le type de produit en :

- **Ce que fait ce paramètre :** Ce menu déroulant vous permet de sélectionner le nouveau type de produit pour tous les produits identifiés dans la Section 1.
- **Options :**
  - **Produit standard :** Un produit physique régulier.
  - **Pack de produits :** Un ensemble d'autres produits.
  - **Produit avec combinaisons :** Un produit avec des variations (par exemple, taille, couleur).
  - **Produit virtuel :** Un produit non physique (par exemple, service, téléchargement).
- **Effet de la modification de ce paramètre :**
  - *Sélection d'une option :* Tous les produits sélectionnés seront convertis à ce nouveau type.
- **Valeur recommandée :** Choisissez le type de produit qui reflète précisément la nouvelle nature de vos produits sélectionnés.
- **Scénario / exemple pour le marchand :** Vous avez sélectionné tous les produits « eBook ». Vous choisiriez « Produit virtuel » ici.

##### 2.2 Bouton Appliquer les modifications

- **Ce que fait ce paramètre :** Ce bouton exécute l'opération de changement en masse.
- **Effet de la modification de ce paramètre :**
  - *Cliquer sur le bouton :* Le module traitera tous les produits de la « Liste des produits sélectionnés » et changera leur type de produit vers celui choisi dans « Changer le type de produit en : ». Un message de confirmation apparaîtra généralement.
- **Valeur recommandée :** Cliquez sur ce bouton uniquement après être absolument certain de votre sélection de produits et du nouveau type souhaité.
- **Scénario / exemple pour le marchand :** Après avoir examiné vos eBooks sélectionnés et confirmé « Produit virtuel » comme nouveau type, vous cliquez sur « Appliquer les modifications » pour les convertir tous.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | **Sélectionner les produits par catégorie** | Sélectionner les catégories pertinentes | Filtre les produits par leurs catégories assignées. |
| Configuration du module | **Sélectionner les produits par marque** | Sélectionner les marques pertinentes | Filtre les produits par leur fabricant/marque. |
| Configuration du module | **Sélectionner les produits par caractéristique** | Sélectionner la caractéristique et la valeur | Filtre les produits par des caractéristiques spécifiques et leurs valeurs. |
| Configuration du module | **Sélectionner les produits par attribut** | Sélectionner l'attribut et la valeur | Filtre les produits par des attributs spécifiques et leurs valeurs (pour les combinaisons). |
| Configuration du module | **Sélectionner les produits par phrase de recherche** | Saisir le terme de recherche | Filtre les produits par mots-clés dans leur nom. |
| Configuration du module | **Liste des produits sélectionnés** | Examiner attentivement | Affiche les produits sélectionnés ; permet la suppression manuelle avant le traitement. |
| Configuration du module | **Changer le type de produit en :** | Choisir le type souhaité | Définit le nouveau type de produit (Standard, Pack, Combinaisons, Virtuel) pour tous les produits sélectionnés. |
| Configuration du module | **Bouton Appliquer les modifications** | Cliquer pour exécuter | Lance le changement de type de produit en masse pour tous les produits sélectionnés. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai changé les types de produits, mais je ne vois pas les modifications sur le front office de ma boutique.**
R : Après avoir effectué des modifications dans le Back Office, videz toujours le cache de votre PrestaShop. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » dans le coin supérieur droit. Le cache de votre navigateur pourrait également avoir besoin d'être vidé (Ctrl+F5 ou Cmd+R).

**Q : Certains produits n'ont pas été modifiés, même s'ils figuraient dans ma sélection.**
R :

1.  **Vérifiez à nouveau la « Liste des produits sélectionnés » :** Les avez-vous accidentellement supprimés de la liste avant d'appliquer les modifications ?
2.  **Vérifiez les critères :** Revérifiez vos critères de sélection (catégorie, marque, caractéristique, attribut, phrase de recherche). Les produits correspondent-ils vraiment à tous les filtres sélectionnés ?
3.  **Statut du produit :** Assurez-vous que les produits sont actifs et non désactivés.
4.  **Erreurs :** Vérifiez si des messages d'erreur sont apparus pendant le processus « Appliquer les modifications ».

**Q : Puis-je annuler les modifications apportées par ce module ?**
R : Ce module effectue des mises à jour directes de la base de données. Il n'y a pas de bouton « annuler » dans le module lui-même. C'est pourquoi une **sauvegarde de la base de données avant utilisation est cruciale**. Si vous devez annuler, vous restaureriez généralement votre base de données à partir d'une sauvegarde effectuée *avant* d'utiliser le module. Alternativement, vous devrez utiliser le module à nouveau pour ramener les types de produits à leur état d'origine, ou les modifier manuellement.

**Q : Ce module affectera-t-il le référencement ou les URL de mes produits ?**
R : Changer le type d'un produit n'altère pas directement son URL conviviale pour le référencement. Cependant, si le changement de type entraîne d'autres modifications (par exemple, suppression de combinaisons, modification de la structure du produit), il est toujours bon de vérifier vos pages de produits et potentiellement de régénérer les URL (section SEO & URL dans PrestaShop) si vous remarquez des problèmes, bien que cela soit rare pour un simple changement de type.

**Q : Le module n'affiche aucun produit lorsque j'utilise la phrase de recherche.**
R :

1.  **Vérifiez les fautes de frappe :** Assurez-vous que votre phrase de recherche est correctement orthographiée.
2.  **Sensibilité à la casse :** Les noms de produits peuvent être sensibles à la casse selon la configuration de votre base de données, essayez différentes casses.
3.  **Langue :** Assurez-vous que vous recherchez dans la bonne langue si votre boutique est multilingue.
4.  **Conflit de module :** Désactivez temporairement les autres modules liés à la recherche pour vérifier les conflits.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique pour les développeurs et les webmasters qui maintiennent ou étendent une boutique PrestaShop à l'aide du module « Changement de type de produit en masse ».

### 4.1 Aperçu de l'architecture

Le module « Changement de type de produit en masse » (`massptype`) est un module PrestaShop standard fonctionnant principalement dans le Back Office. Il s'appuie sur la classe `Module` de PrestaShop et utilise AJAX pour le filtrage des produits et le processus de mise à jour en masse. La logique principale réside dans le fichier principal du module, gérant la configuration, la sélection des produits et la mise à jour en masse des types de produits. Il intègre un outil de recherche personnalisé pour la sélection des produits.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs front-office ou back-office dédiés dans les répertoires `controllers/admin` ou `controllers/front`. Toute la logique est gérée dans le fichier principal du module `massptype.php` et sa méthode `getContent()`, qui agit comme le point d'entrée principal de la configuration. Les requêtes AJAX sont envoyées via le fichier `ajax_products_list.php` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne définit pas de classes `ObjectModel` personnalisées. Il interagit directement avec les méthodes `Product` et `Product::updateProductFlags()` de PrestaShop pour modifier les types de produits.

### 4.4 Actifs JavaScript (`views/js/`)

- `massptype/lib/searchTool/views/js/autocomplete.js`
  - **Portée :** Back-office (utilisé dans la page de configuration du module).
  - **Objectif :** Fournit la logique principale pour la fonctionnalité d'autocomplétion de la recherche de produits. Il gère probablement l'envoi de requêtes AJAX au point de terminaison `ajax_products_list.php` du module pour récupérer des suggestions de produits basées sur l'entrée de l'utilisateur.
- `massptype/views/js/jquery.autocomplete.js`
  - **Portée :** Back-office (utilisé dans la page de configuration du module).
  - **Objectif :** Il s'agit apparemment d'un plugin jQuery pour la fonctionnalité d'autocomplétion, probablement une dépendance ou une implémentation personnalisée utilisée par l'outil de recherche. Il gère l'aspect UI de l'affichage des suggestions et de l'interaction utilisateur.

### 4.5 Feuilles de style CSS (`views/css/`)

- `massptype/lib/searchTool/views/css/autocomplete.css`
  - **Portée :** Back-office (style les éléments de la page de configuration du module).
  - **Objectif :** Style la liste déroulante d'autocomplétion, les champs de saisie et potentiellement la liste des produits sélectionnés dans l'interface de l'outil de recherche du module. Les développeurs peuvent remplacer ces styles dans leur thème Back Office personnalisé ou en ajoutant des règles CSS plus spécifiques.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :
  - `massptype/views/templates/hook/form.tpl`
    - **Hook :** Non directement hooké au sens traditionnel, mais rendu par `getContent()` du fichier principal du module.
    - **Objectif :** C'est le template principal du formulaire de configuration du module dans le Back Office. Il contient la structure HTML pour la sélection des produits par divers critères et le choix du nouveau type de produit.
- **Templates d'administration (`views/templates/admin/`)** :
  - `massptype/views/templates/admin/target_products.tpl`
    - **Objectif :** Ce template est probablement utilisé pour afficher la liste des produits sélectionnés après l'application des critères de filtrage. Il se met à jour dynamiquement via AJAX pour montrer quels produits seront affectés.
  - `massptype/views/templates/admin/wtd.tpl` (What To Do - Que faire)
    - **Objectif :** Ce template rend probablement la section où l'utilisateur sélectionne le nouveau type de produit (Standard, Pack, Combinaisons, Virtuel) et le bouton « Appliquer les modifications ».
- **Autres templates** :
  - `massptype/lib/searchTool/views/scripts.tpl`
    - **Objectif :** Ce template inclut probablement du code JavaScript ou initialise la fonctionnalité d'autocomplétion JavaScript pour l'outil de recherche de produits. Il pourrait être inclus dans `form.tpl`.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de la base de données** : Le module ne crée pas de tables de base de données personnalisées. Il modifie les tables principales existantes de PrestaShop, spécifiquement `ps_product` (et potentiellement `ps_product_shop`) en mettant à jour les champs `cache_is_pack`, `cache_has_attachments`, `is_virtual` et `cache_default_attribute`, qui déterminent le type de produit. Les paramètres de configuration sont stockés dans `ps_configuration` à l'aide de clés standard (par exemple, `_PS_MASS_PTYPE_...`).
- **Table des hooks enregistrés** :
  Le module n'enregistre aucun hook d'affichage traditionnel front-office ou back-office. Sa fonctionnalité est entièrement contenue dans sa méthode `getContent()` et ses appels AJAX.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionModuleInstall` | Lors de l'installation du module | Configure la configuration initiale. |
| `actionModuleUninstall` | Lors de la désinstallation du module | Nettoie la configuration. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et le support officiel du module « Changement de type de produit en masse », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité du module.
