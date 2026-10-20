---
title: "Désactiver les prix spécifiques des produits lorsque le panier contient une règle de panier - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Désactiver les prix spécifiques des produits lorsque le panier contient une règle de panier' par MyPresta.eu."
sidebar:
  label: "Désactiver les prix spécifiques des produits lorsque le panier contient une règle de panier - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Disable product specific prices when cart has cart rule sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-product-specific-prices-when-cart-has-cart-rule.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/disable-product-specific-prices-when-cart-has-cart-rule/)
>
> ---


# Désactiver les prix spécifiques des produits lorsque le panier contient une règle de panier

## 1. Exigences et compatibilité

Ce module est conçu pour fonctionner de manière transparente avec les installations PrestaShop modernes.

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises pour PrestaShop lui-même et sont généralement disponibles sur tout environnement d'hébergement web moderne. Aucune exigence d'hébergement spéciale au-delà d'une configuration PrestaShop standard.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

Ce module dispose d'un écran de configuration unique et simple.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Pour accéder à la configuration, naviguez vers **Modules > Gestionnaire de modules**, recherchez « Désactiver les prix spécifiques des produits lorsque le panier contient une règle de panier », et cliquez sur le bouton « Configurer ».

![Capture d'écran de la configuration du module (Placeholder)]
*(Imaginez une capture d'écran ici montrant un formulaire simple avec un seul interrupteur à bascule intitulé « Désactiver l'utilisation des prix spécifiques dans le panier avec une règle de panier » et les options « Activé » / « Désactivé ».)*

**Paramètre : Désactiver l'utilisation des prix spécifiques dans le panier avec une règle de panier**

- **Ce que fait ce paramètre :** Il s'agit de l'interrupteur de contrôle principal de la fonctionnalité essentielle du module. Il détermine si le module intervient activement pour désactiver les prix spécifiques lorsqu'une règle de panier (code de bon) est présente dans le panier du client.
- **Effet de la modification de ce paramètre :**
  - **Lorsqu'il est activé (OUI) :** Si un client applique une règle de panier (code de bon) à son panier, le module empêchera l'application de tout prix spécifique aux produits de ce panier. Les prix des produits reviendront à leur prix de base avant l'application de la réduction de la règle de panier, garantissant que seule la réduction de la règle de panier affecte le prix final. Cela empêche le double-escompte.
  - **Lorsqu'il est désactivé (NON) :** Le module sera inactif. Les prix spécifiques et les règles de panier fonctionneront indépendamment, ce qui signifie qu'ils peuvent potentiellement s'empiler sur le même produit, entraînant l'application simultanée de plusieurs réductions. C'est le comportement par défaut de PrestaShop.
- **Valeur recommandée :** **Activé (OUI)**. C'est l'objectif principal du module et il vous permet de protéger vos marges bénéficiaires et de contrôler votre stratégie de réduction.
- **Scénario / exemple de marchand :**
  - **Choisissez « Activé »** si vous voulez vous assurer que lorsqu'un client utilise un code de bon (par exemple, « ÉCONOMISEZ10 » pour 10 % de réduction), tous les prix spécifiques existants sur les produits de son panier sont ignorés. Cela signifie que la réduction de 10 % sera appliquée au prix régulier du produit, et non à un prix spécifique déjà réduit. Cela empêche un produit d'être réduit deux fois.
  - **Choisissez « Désactivé »** si vous préférez le comportement par défaut de PrestaShop où les prix spécifiques et les règles de panier peuvent s'empiler, ce qui peut entraîner des réductions plus importantes que prévu. Cela peut être souhaité dans des campagnes promotionnelles très spécifiques et agressives, mais généralement, « Activé » est recommandé pour la protection des bénéfices.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Désactiver l'utilisation des prix spécifiques dans le panier avec une règle de panier | Activé | Lorsqu'il est activé, les prix spécifiques sont ignorés si une règle de panier est active dans le panier, empêchant les doubles réductions. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai activé le module, mais les prix spécifiques s'affichent toujours même avec un code de bon. Qu'est-ce qui ne va pas ?**

- **R :** Tout d'abord, assurez-vous d'avoir enregistré la configuration après avoir activé le module.
- **R :** Videz votre cache PrestaShop. Allez dans **Paramètres avancés > Performances**, et cliquez sur « Vider le cache » en haut à droite.
- **R :** Testez avec un nouveau panier. Parfois, le cache du navigateur ou les données de session peuvent interférer. Essayez dans une fenêtre de navigation privée.
- **R :** Vérifiez que la règle de panier que vous testez est réellement active et correctement appliquée aux produits du panier.

**Q2 : Mes clients se plaignent que leurs prix spécifiques ont disparu lorsqu'ils ont utilisé un bon. Est-ce normal ?**

- **R :** Oui, c'est le comportement attendu du module. Lorsque le module est activé et qu'un client applique une règle de panier (bon), les prix spécifiques des produits du panier sont temporairement désactivés pour éviter le double-escompte. Le prix du produit sera alors calculé sur la base de son prix d'origine, avec la réduction de la règle de panier appliquée. Vous pourriez vouloir mettre à jour vos conditions générales ou vos messages promotionnels pour clarifier la façon dont les réductions interagissent.

**Q3 : Ce module affecte-t-il d'autres types de réductions, comme les réductions par catégorie ou les réductions par groupe de clients ?**

- **R :** Ce module cible spécifiquement les « prix spécifiques » (réductions définies directement sur des produits individuels ou des combinaisons) et leur interaction avec les « règles de panier » (codes de bon). Il n'interfère pas directement avec d'autres mécanismes de réduction comme les réductions par catégorie, les réductions par groupe de clients ou les réductions de quantité, à moins que ceux-ci ne soient implémentés comme des prix spécifiques.

**Q4 : Ce module va-t-il ralentir ma boutique ?**

- **R :** Le module effectue des surcharges mineures sur les classes PrestaShop de base pour ajuster la logique de calcul des prix. Ces modifications sont hautement optimisées et devraient avoir un impact négligeable sur les performances de votre boutique. Le module n'active sa logique que lorsqu'une règle de panier est présente, il ne fonctionne donc pas en permanence.

**Q5 : Je souhaite autoriser temporairement l'empilement des prix spécifiques et des règles de panier pour une promotion spéciale. Comment faire ?**

- **R :** Il suffit d'aller sur la page de configuration du module (**Modules > Gestionnaire de modules > Configurer** pour « Désactiver les prix spécifiques des produits lorsque le panier contient une règle de panier ») et de définir l'option « Désactiver l'utilisation des prix spécifiques dans le panier avec une règle de panier » sur **« Désactivé »**. N'oubliez pas de le réactiver après la fin de votre promotion spéciale pour restaurer le comportement de protection par défaut.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module « Désactiver les prix spécifiques des produits lorsque le panier contient une règle de panier ».

### 4.1 Aperçu de l'architecture

Ce module fonctionne principalement en surchargeant les classes PrestaShop de base liées au calcul des prix et à la gestion des prix spécifiques. Il utilise le mécanisme de surcharge de PrestaShop pour injecter sa logique dans les classes `Cart`, `Product` et `SpecificPrice`. L'idée principale est de détecter la présence d'une règle de panier dans le panier actuel et, si elle est trouvée, de modifier le comportement de récupération des prix spécifiques pour les ignorer efficacement lors des calculs de prix.

La configuration principale du module est gérée via la méthode `getContent()` dans le fichier principal du module, stockant un simple indicateur booléen dans `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur front-office ou back-office personnalisé. Sa logique est entièrement intégrée dans les surcharges de classes.

- **Contrôleurs Front-Office** : Aucun
- **Contrôleurs Admin Back-Office** : Aucun

### 4.3 Classes et modèles de base (`classes/`)

La fonctionnalité principale du module réside dans ses surcharges de classes. Ces fichiers sont situés dans `cartspecdis/override/classes/`. PrestaShop charge automatiquement ces surcharges, remplaçant les classes de base originales par les versions modifiées du module.

- **`cartspecdis/override/classes/Cart.php`**

  - **Nom de la classe et classe parente** : `Cart` (surcharge `\Cart`)
  - **Responsabilité** : Cette surcharge est cruciale. Elle introduit probablement une méthode ou modifie une méthode existante (par exemple, `getProducts()`, `getPackageList()`, ou une aide au calcul de prix) pour vérifier la présence de règles de panier. Si des règles de panier sont trouvées, elle définit un indicateur ou modifie des paramètres qui influencent la façon dont les prix spécifiques sont ensuite récupérés ou appliqués. La méthode `hasCartRules()` est un candidat probable pour vérifier les règles de panier.
  - **Logique clé** : La surcharge ajoutera probablement une vérification dans les méthodes de calcul de prix pour voir si `Cart::getCartRules()` renvoie des règles actives. Si c'est le cas, elle influencera alors les appels `Product::getPriceStatic()` ou `SpecificPrice::getSpecificPrice()` pour ignorer les prix spécifiques.
- **`cartspecdis/override/classes/Product.php`**

  - **Nom de la classe et classe parente** : `Product` (surcharge `\Product`)
  - **Responsabilité** : Cette surcharge devrait modifier la méthode `getPriceStatic()`, qui est centrale à la façon dont les prix des produits sont récupérés dans PrestaShop.
  - **Logique clé** : À l'intérieur de `getPriceStatic()`, le module ajoutera probablement une condition. Si l'objet `Cart` actuel (passé en paramètre ou accessible globalement) contient des règles de panier actives, et que la configuration du module est activée, alors les paramètres passés à `SpecificPrice::getSpecificPrice()` seront modifiés (par exemple, les indicateurs `id_specific_price` ou `use_specific_price`) pour s'assurer qu'aucun prix spécifique n'est renvoyé, ou que le calcul du prix spécifique est contourné.
- **`cartspecdis/override/classes/SpecificPrice.php`**

  - **Nom de la classe et classe parente** : `SpecificPrice` (surcharge `\SpecificPrice`)
  - **Responsabilité** : Cette surcharge est susceptible de modifier la méthode `getSpecificPrice()`, qui est responsable de la récupération des détails des prix spécifiques pour un produit donné.
  - **Logique clé** : Cette surcharge contiendra la logique directe pour empêcher le retour des prix spécifiques. Elle vérifiera si le `Cart` actuel a des règles de panier et si le module est activé. Si les deux conditions sont vraies, `getSpecificPrice()` sera configuré pour renvoyer `false` ou un tableau vide, indiquant effectivement qu'aucun prix spécifique ne s'applique, même s'il en existe un dans la base de données. C'est le dernier gardien des prix spécifiques.
- **`cartspecdis/override/classes/index.php`**

  - **Nom de la classe et classe parente** : Aucun
  - **Responsabilité** : Il s'agit d'un fichier `index.php` vide standard, généralement placé dans les répertoires pour empêcher la liste des répertoires lorsqu'ils sont directement accessibles via un navigateur web. Il n'a aucun impact fonctionnel sur la logique du module.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé. Toute sa logique est gérée côté serveur.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé. Il n'a pas de composants visuels front-office et sa configuration back-office utilise des éléments de formulaire PrestaShop standard.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Ce module n'utilise aucun modèle Smarty personnalisé. Son formulaire de configuration est généré dynamiquement par la méthode `getContent()` dans le fichier principal du module à l'aide des formulaires d'aide de PrestaShop.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne crée aucune table SQL personnalisée.
  - Il stocke son paramètre de configuration dans la table `ps_configuration` :
    - Clé `PS_CONFIGURATION` : `cartspecdis` (stocke la valeur booléenne pour l'activation/désactivation de la fonctionnalité principale du module).
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur Admin configure ses ressources multimédias (CSS/JS). | Ce hook est généralement utilisé par les modules pour ajouter leurs propres fichiers CSS ou JavaScript au Back Office. Pour ce module, il est probablement utilisé pour s'assurer que tout style ou script nécessaire côté administration (bien qu'aucun ne soit explicitement listé dans l'inventaire) est chargé, ou il pourrait s'agir d'un vestige d'une structure de module de modèle. Étant donné qu'aucun fichier JS/CSS n'est listé, son objectif principal ici est probablement minimal ou pour une expansion future. |

### 4.8 Fichier principal du module (`cartspecdis/cartspecdis.php`)

- **Nom de la classe** : `Cartspecdis` (étend `Module`)
- **`__construct()`** : Initialise les métadonnées du module (nom, onglet, version, auteur, `need_instance`, `ps_versions_compliancy`).
- **`install()`** :
  - Appelle `parent::install()`.
  - Enregistre le hook `actionAdminControllerSetMedia`.
  - Définit la valeur de configuration par défaut pour `cartspecdis` à `1` (activé) dans `ps_configuration`.
  - Enregistre les surcharges de classes (`Cart`, `Product`, `SpecificPrice`).
- **`uninstall()`** :
  - Appelle `parent::uninstall()`.
  - Désenregistre le hook `actionAdminControllerSetMedia`.
  - Supprime la valeur de configuration `cartspecdis` de `ps_configuration`.
  - Désenregistre les surcharges de classes.
- **`getContent()`** :
  - Gère la soumission du formulaire pour la configuration du module.
  - Met à jour la valeur de configuration `cartspecdis` dans `ps_configuration` en fonction de l'entrée de l'utilisateur.
  - Affiche un message de confirmation.
  - Rend le formulaire de configuration à l'aide de la classe `HelperForm` de PrestaShop, y compris le seul interrupteur à bascule pour « Désactiver l'utilisation des prix spécifiques dans le panier avec une règle de panier ».
- **`hookActionAdminControllerSetMedia()`** :
  - Cette méthode est appelée lorsque le hook `actionAdminControllerSetMedia` est exécuté.
  - Elle est généralement utilisée pour ajouter des fichiers CSS ou JavaScript au Back Office. Dans l'état actuel de ce module (basé sur l'inventaire), elle contient probablement peu ou pas de code actif pour l'ajout d'actifs, ou c'est un espace réservé.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Désactiver les prix spécifiques des produits lorsque le panier contient une règle de panier », veuillez vous référer à votre compte client sur MyPresta.eu.

- **Mises à jour du module** : Connectez-vous à votre compte MyPresta.eu et naviguez vers votre historique de commandes et la section des téléchargements pour obtenir la version la plus récente du module.
- **Support technique** : Si vous rencontrez des problèmes ou avez des questions qui ne sont pas couvertes dans cette documentation, veuillez ouvrir un ticket de support via votre compte client MyPresta.eu. Notre équipe se fera un plaisir de vous aider.
"""
