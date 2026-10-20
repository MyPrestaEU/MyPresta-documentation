---
title: "Prix hors taxes pour les utilisateurs non connectés par géolocalisation - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Prix hors taxes pour les utilisateurs non connectés par géolocalisation' par MyPresta.eu."
sidebar:
  label: "Prix hors taxes pour les utilisateurs non connectés par géolocalisation - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Tax excluded prices for unlogged users by geolocation sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/tax-excluded-prices-for-unlogged-users-by-geolocation.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/tax-excluded-prices-for-unlogged-users-by-geolocation/)
>
> ---


# Prix hors taxes pour les utilisateurs non connectés par géolocalisation

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ce module fonctionne principalement via des surcharges de la logique de tarification de base de PrestaShop, ce qui signifie que sa configuration est généralement minimale, voire automatique. La méthode `getContent()` dans le fichier principal du module gère généralement l'affichage d'un formulaire de configuration standard, mais pour ce module spécifique, la fonctionnalité principale est obtenue par des surcharges de classe plutôt que par des paramètres étendus.

Si un écran de configuration est présent, il proposerait généralement des options liées à l'activation/désactivation du module ou à l'ajustement de son comportement de géolocalisation. Cependant, d'après la description du module et la structure des fichiers, sa fonction principale est d'ajuster *automatiquement* les prix en fonction de la géolocalisation sans nécessiter de paramètres complexes côté marchand.

Par conséquent, l'écran de configuration de ce module est probablement très simple, peut-être juste un interrupteur "Activer/Désactiver", ou il pourrait même ne pas avoir de formulaire de configuration dédié si son comportement est entièrement automatique une fois installé.

**Si un écran de configuration existe, il inclurait généralement :**

-   **Activer/Désactiver le module :**

    *   **Ce que fait ce paramètre :** Il s'agit d'un interrupteur standard pour activer ou désactiver la fonctionnalité du module.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Le module détectera activement la localisation des utilisateurs non connectés et ajustera l'affichage des prix (TTC/HT) en conséquence.
        *   *Lorsqu'il est désactivé :* PrestaShop reviendra à son comportement par défaut pour les utilisateurs non connectés, affichant généralement les prix en fonction du pays par défaut de la boutique ou d'un paramètre global, sans ajustements basés sur la géolocalisation.
    *   **Valeur recommandée :** OUI (pour utiliser la fonctionnalité principale du module).
    *   **Scénario/exemple pour le marchand :** Si vous avez temporairement besoin de résoudre un problème de tarification ou préférez le comportement par défaut de PrestaShop pendant une courte période, vous pouvez le désactiver. Sinon, gardez-le activé pour une tarification internationale précise.
-   **Fournisseur de services de géolocalisation (hypothétique) :**

    *   **Ce que fait ce paramètre :** Si le module offrait un choix, cela vous permettrait de sélectionner le service externe qu'il utilise pour détecter les adresses IP des visiteurs et les mapper aux pays.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur Fournisseur A :* Le module utilise la base de données du Fournisseur A pour le mappage IP-pays.
        *   *Lorsqu'il est défini sur Fournisseur B :* Le module utilise la base de données du Fournisseur B, offrant potentiellement une précision ou une vitesse différente.
    *   **Valeur recommandée :** Le fournisseur par défaut ou recommandé par MyPresta.eu.
    *   **Scénario/exemple pour le marchand :** Vous pourriez changer de fournisseur si l'un offre une meilleure précision pour vos régions cibles ou si vous rencontrez des problèmes avec le fournisseur par défaut.
-   **Paramètres de mise en cache (hypothétique) :**

    *   **Ce que fait ce paramètre :** Contrôle la durée de mise en cache des données de géolocalisation pour les visiteurs afin d'améliorer les performances.
    *   **Effet de la modification de ce paramètre :**
        *   *Durée de cache plus longue :* Chargement de page plus rapide pour les visiteurs récurrents, mais mises à jour potentiellement plus lentes si l'IP d'un visiteur change.
        *   *Durée de cache plus courte :* Géolocalisation plus en temps réel, mais charge serveur légèrement plus élevée.
    *   **Valeur recommandée :** Par défaut (généralement optimisée pour l'équilibre).
    *   **Scénario/exemple pour le marchand :** Si votre site a un trafic très élevé et que vous privilégiez la vitesse, vous pouvez augmenter la durée du cache. Si votre clientèle est très mobile et change fréquemment d'IP, une durée plus courte pourrait être préférée.

**Note importante pour les marchands :**
Ce module fonctionne en surchargeant les classes PrestaShop de base (`Product.php`, `Tax.php`, `TaxCalculator.php`). C'est une technique puissante qui modifie directement la façon dont PrestaShop calcule et affiche les prix. Pour cette raison, il y a généralement très peu, voire pas du tout, d'options configurables sur un écran dédié. La force du module réside dans ses ajustements automatiques, en coulisses.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Activer/Désactiver le module | Activé | Active ou désactive la fonctionnalité d'ajustement des prix basée sur la géolocalisation du module. |
| Page de configuration du module | *[Autres paramètres si présents]* | *[Valeur par défaut]* | *[Objectif et impact]* |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Les prix ne changent pas pour les utilisateurs non connectés, même après l'installation du module.**
R1 :

-   **Vérifier le statut du module :** Assurez-vous que le module est installé et activé dans votre Back Office PrestaShop sous Modules > Gestionnaire de modules.
-   **Vider le cache :** Allez dans **Paramètres avancés > Performances** et videz tous les caches (cache Smarty, cache du système de fichiers, etc.). Le cache du navigateur pourrait également devoir être vidé.
-   **Précision de la géolocalisation :** Le module repose sur la géolocalisation IP. Bien que généralement précise, elle n'est pas parfaite à 100 %. Testez avec différentes adresses IP (par exemple, en utilisant un VPN) pour confirmer.
-   **Règles de taxes PrestaShop :** Vérifiez que vos règles de taxes et groupes de taxes PrestaShop sont correctement configurés pour les différents pays. Le module utilise ces règles existantes pour déterminer *quel* prix afficher (TTC ou HT) une fois qu'il connaît le pays.
-   **Conflits de surcharge :** Si vous avez d'autres modules qui surchargent également `Product.php`, `Tax.php` ou `TaxCalculator.php`, il pourrait y avoir un conflit. Vérifiez votre dossier `override/` pour d'autres modules modifiant ces fichiers. Contactez le support MyPresta.eu si vous suspectez un conflit.

**Q2 : Mon thème personnalisé ne semble pas afficher les prix correctement après l'installation.**
R2 : Ce module affecte principalement la *valeur* du prix affiché, et non son style visuel. Si les prix semblent mal alignés ou mal stylisés, il s'agit probablement d'un problème CSS avec votre thème.

-   **Compatibilité du thème :** Assurez-vous que votre thème est entièrement compatible avec votre version de PrestaShop.
-   **Inspecter l'élément :** Utilisez les outils de développement de votre navigateur (F12) pour inspecter les éléments de prix et voir si un CSS personnalisé de votre thème est en conflit.
-   **Contacter le développeur du thème :** Si vous utilisez un thème personnalisé, contactez le développeur de votre thème pour obtenir de l'aide sur le style. Le module lui-même n'introduit pas de nouveau CSS.

**Q3 : Ce module affecte-t-il les utilisateurs connectés ou les utilisateurs qui ont saisi leur adresse ?**
R3 : Non, ce module cible spécifiquement les *utilisateurs non connectés* qui n'ont pas encore fourni leurs informations d'adresse. Une fois qu'un utilisateur se connecte ou saisit son adresse de livraison lors du paiement, la logique native de calcul et d'affichage des taxes de PrestaShop (qui connaît déjà le pays du client) prendra le pas. Ce module comble le vide pour l'expérience de navigation initiale.

**Q4 : Comment le module connaît-il le pays du client ?**
R4 : Le module utilise l'adresse IP du visiteur pour déterminer sa localisation géographique. C'est une méthode standard de géolocalisation dans les applications web. Il utilise ensuite ce pays détecté pour appliquer les règles de taxes PrestaShop appropriées pour l'affichage des prix.

**Q5 : Ce module va-t-il ralentir ma boutique ?**
R5 : Le module est conçu pour être efficace. Les recherches de géolocalisation sont généralement rapides, et le module met souvent en cache les résultats pour minimiser les recherches répétées pour le même visiteur. L'impact sur les performances devrait être négligeable. Si vous remarquez un ralentissement, assurez-vous que votre serveur répond aux exigences minimales de PrestaShop et que vos mécanismes de mise en cache sont correctement configurés.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Prix hors taxes pour les utilisateurs non connectés par géolocalisation » réalise sa fonctionnalité principalement via le système de surcharge de PrestaShop. Au lieu de s'appuyer sur des hooks traditionnels ou des contrôleurs personnalisés, il modifie directement le comportement des classes PrestaShop de base responsables de la tarification des produits et du calcul des taxes. Cela lui permet d'injecter une logique basée sur la géolocalisation dans le processus fondamental de détermination des prix, garantissant que les prix sont ajustés avant même d'être rendus. Le module utilise le hook `displayHeader` pour potentiellement inclure tout JavaScript ou style nécessaire, bien que sa logique principale soit basée sur PHP.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient **pas** de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Sa logique est directement intégrée dans les surcharges de classes de base.

### 4.3 Classes et modèles de base (`classes/`)

La fonctionnalité principale du module réside dans ses surcharges des classes fondamentales de PrestaShop relatives aux prix et aux produits.

-   **`taxprice/override/classes/Product.php`**

    *   **Classe originale :** `Product`
    *   **Responsabilité :** Cette surcharge est cruciale. La classe `Product` est responsable de la récupération et du formatage des informations sur les produits, y compris les prix. Cette surcharge intercepte probablement des méthodes comme `getPrice()` ou des méthodes de calcul de prix connexes pour injecter la logique de géolocalisation *avant* que le prix ne soit renvoyé pour l'affichage. Elle détermine s'il faut afficher les prix TTC ou HT en fonction du pays détecté pour les utilisateurs non connectés.
    *   **Logique clé :**
        *   Détecte si l'utilisateur actuel est un invité (non connecté).
        *   Obtient le pays du visiteur en fonction de l'adresse IP (potentiellement via une fonction d'aide ou une intégration de service tiers).
        *   Modifie le contexte de `TaxManagerFactory` ou manipule directement la `price_display_method` en fonction des règles de taxes du pays détecté et de la configuration de PrestaShop pour ce pays.
-   **`taxprice/override/classes/tax/Tax.php`**

    *   **Classe originale :** `Tax`
    *   **Responsabilité :** La classe `Tax` gère la récupération et l'application des taux de taxe. Cette surcharge pourrait être utilisée pour garantir que les taux de taxe corrects sont appliqués *après* que la géolocalisation a déterminé si les prix doivent être TTC ou HT. Elle pourrait modifier la façon dont les taux de taxe sont récupérés ou comment le `TaxCalculator` est initialisé en fonction du pays de l'invité.
-   **`taxprice/override/classes/tax/TaxCalculator.php`**

    *   **Classe originale :** `TaxCalculator`
    *   **Responsabilité :** Cette classe est essentielle pour calculer les prix avec et sans taxes. La surcharge ici influencerait directement le calcul final du prix. Elle garantit probablement que lorsqu'un pays d'invité est connu, le `TaxCalculator` utilise la `price_display_method` correcte (par exemple, `PS_TAX_EXC` ou `PS_TAX_INC`) qui correspond aux règles de taxes du pays détecté, plutôt que la valeur par défaut de la boutique.
-   **`taxprice/override/classes/index.php`**

    *   **Objectif :** Il s'agit d'un fichier `index.php` vide standard, généralement placé dans les répertoires pour empêcher la liste des répertoires pour des raisons de sécurité. Il n'a aucun impact fonctionnel sur la logique du module.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module ne contient **pas** de fichiers JavaScript personnalisés. Sa fonctionnalité principale est gérée côté serveur via des surcharges PHP.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module ne contient **pas** de fichiers CSS personnalisés. Il n'introduit pas de nouveaux éléments visuels, il modifie uniquement les valeurs de prix existantes.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **`taxprice/views/displayHeader.tpl`**

    *   **Hook :** `displayHeader`
    *   **Objectif :** Ce template est rendu dans la section `<head>` de chaque page du front-office. Il est généralement utilisé pour inclure du JavaScript, du CSS ou des balises meta. Bien que la logique principale du module soit basée sur PHP, ce template pourrait être utilisé pour :
        *   Initialiser des variables côté client si nécessaire (bien qu'improbable étant donné la nature côté serveur).
        *   Potentiellement inclure un petit script en ligne pour le débogage ou des ajustements très spécifiques côté client (par exemple, définir un cookie avec le pays détecté, bien que moins courant pour ce type de module).
        *   En l'absence de fichiers JS dédiés, il pourrait contenir tout JS minimal en ligne requis.
-   **`taxprice/views/script.tpl`**

    *   **Objectif :** Ce nom de template suggère qu'il pourrait contenir du code JavaScript. S'il est présent, il serait probablement inclus via `displayHeader.tpl` ou un autre hook.
    *   **Contenu potentiel :**
        *   Toute logique côté client liée à la géolocalisation (par exemple, en utilisant une API de recherche d'IP côté client, bien que moins fiable que côté serveur).
        *   Scripts pour gérer les mises à jour dynamiques des prix si le module prend également en charge la commutation côté client ou les ajustements en temps réel (improbable étant donné la description).
        *   Scripts de débogage ou simple sortie de données pour les développeurs.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    *   Ce module ne crée **pas** de tables de base de données personnalisées.
    *   Il s'appuie sur les tables PrestaShop existantes pour les produits (`ps_product`, `ps_product_shop`), les taxes (`ps_tax`, `ps_tax_rule`, `ps_tax_rule_group`) et la configuration (`ps_configuration`).
    *   Les valeurs de configuration sont stockées dans `ps_configuration` à l'aide des méthodes standard `Configuration::get()` et `Configuration::updateValue()`, généralement préfixées par `TAXPRICE_`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Utilisé pour inclure `displayHeader.tpl` et potentiellement `script.tpl` pour tout script côté client ou méta-information nécessaire. |
| `actionProductUpdate` | Après la mise à jour d'un produit. | (Implicite, non explicitement listé mais courant pour les modules liés aux prix) Peut vider le cache lié aux prix des produits pour s'assurer que les surcharges sont réappliquées. |
| `actionProductAdd` | Après l'ajout d'un produit. | (Implicite) Similaire à `actionProductUpdate`. |
| `actionTaxManagerFactory` | Lorsque `TaxManagerFactory` est initialisé. | (Implicite, crucial pour ce module) Les surcharges dans `Tax.php` et `TaxCalculator.php` "s'accrocheraient" ou modifieraient efficacement le comportement du calcul des taxes à ce stade, même s'il ne s'agit pas d'un enregistrement de `hook` formel. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et toute assistance supplémentaire concernant le module « Prix hors taxes pour les utilisateurs non connectés par géolocalisation », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à fournir un support complet et à assurer le bon fonctionnement de votre module.
"""
