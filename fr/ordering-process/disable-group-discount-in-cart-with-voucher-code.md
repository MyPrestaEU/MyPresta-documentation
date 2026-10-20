---
title: "Désactiver la réduction de groupe dans le panier avec un code de bon d'achat - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Désactiver la réduction de groupe dans le panier avec un code de bon d'achat' par MyPresta.eu."
sidebar:
  label: "Désactiver la réduction de groupe dans le panier avec un code de bon d'achat - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Disable group discount in cart with voucher code sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-group-discount-in-cart-with-voucher-code.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/disable-group-discount-in-cart-with-voucher-code/)
>
> ---


# Désactiver la réduction de groupe dans le panier avec un code de bon d'achat

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur "Configurer" à côté du nom du module pour accéder à ses paramètres.

#### Paramètre : Désactiver la réduction de groupe dans le panier avec une règle de panier

C'est l'interrupteur de contrôle principal pour la fonctionnalité du module.

-   **Ce que fait ce paramètre :** Ce paramètre détermine si le module intervient activement pour désactiver les réductions de groupe lorsqu'un code de bon d'achat est présent dans le panier.
-   **Effet de la modification de ce paramètre :**
    *   ***Lorsque activé :*** Si un client appartient à un groupe avec une réduction spéciale (par exemple, 10 % de réduction pour les "Clients grossistes") ET qu'il applique un code de bon d'achat (règle de panier) à son panier, la réduction de groupe sera ignorée. Seule la réduction du bon d'achat sera appliquée au total de la commande. Cela empêche le client de recevoir les deux réductions simultanément.
    *   ***Lorsque désactivé :*** Le module n'interviendra pas. Le comportement par défaut de PrestaShop s'appliquera, ce qui signifie que si un client est éligible à la fois à une réduction de groupe et à une réduction par bon d'achat, les deux pourraient être appliquées, potentiellement en cumulant les réductions.
-   **Valeur recommandée :** **Activé**. C'est la fonctionnalité principale du module et elle est généralement recommandée pour éviter le cumul involontaire de réductions et protéger vos marges bénéficiaires pendant les campagnes de bons d'achat.
-   **Scénario / exemple de marchand :**
    *   *Scénario 1 (Activé) :* Vous avez un groupe "Clients VIP" qui bénéficie de 5 % de réduction sur tous les produits. Vous lancez également un code de bon d'achat "ÉTÉ20" pour 20 % de réduction. Un client VIP ajoute des articles à son panier et applique "ÉTÉ20". Avec le module **Activé**, il ne bénéficiera que des 20 % de réduction du bon d'achat, et non de 5 % + 20 %.
    *   *Scénario 2 (Désactivé) :* En utilisant le même exemple, si le module est **Désactivé**, le client VIP pourrait recevoir à la fois la réduction de groupe de 5 % et la réduction par bon d'achat de 20 %, ce qui entraînerait une réduction totale de 25 % (ou un calcul plus complexe selon l'ordre d'application interne des réductions de PrestaShop).

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Désactiver la réduction de groupe dans le panier avec une règle de panier | Activé | Lorsque activé, les réductions de groupe sont ignorées si un code de bon d'achat est présent dans le panier, garantissant que seule la réduction du bon d'achat est appliquée. Prévient le cumul des réductions. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai activé le module, mais les clients obtiennent toujours les deux réductions. Qu'est-ce qui ne va pas ?**
R1 : Tout d'abord, assurez-vous que le module est bien "Activé" dans sa configuration. Deuxièmement, videz votre cache PrestaShop (Allez dans **Paramètres avancés > Performances**, puis cliquez sur "Vider le cache" en haut à droite). Parfois, d'anciennes données de cache peuvent empêcher les modifications de prendre effet immédiatement. Testez également avec un nouveau panier et une nouvelle session client (par exemple, dans une fenêtre de navigation privée).

**Q2 : Ce module affectera-t-il mes prix spécifiques ou mes règles de prix catalogue ?**
R2 : Non, ce module cible spécifiquement les *réductions de groupe* et les *règles de panier (codes de bon d'achat)*. Il n'interfère pas avec les prix spécifiques définis pour des produits individuels, des combinaisons de produits ou les règles de prix catalogue qui s'appliquent en fonction de la quantité ou d'autres conditions. Il modifie uniquement l'interaction entre les réductions de groupe client et les codes de bon d'achat.

**Q3 : Ce module fonctionne-t-il avec tous les types de codes de bon d'achat (pourcentage, montant fixe, livraison gratuite) ?**
R3 : Oui, la logique du module est conçue pour détecter la présence de *toute* règle de panier (code de bon d'achat) active dans le panier. Une fois qu'une règle de panier est détectée, elle désactivera alors la réduction de groupe, quel que soit le type de réduction fourni par le bon d'achat (pourcentage, montant fixe, livraison gratuite, etc.).

**Q4 : Que faire si je veux autoriser les réductions de groupe ET un code de bon d'achat pour une promotion spécifique ?**
R4 : Si vous avez une promotion spécifique où vous *souhaitez* autoriser le cumul des deux réductions, vous devrez temporairement **Désactiver** ce module dans sa configuration. N'oubliez pas de le réactiver une fois cette promotion spécifique terminée si vous souhaitez revenir au comportement de réduction "bon d'achat uniquement".

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Ce module fonctionne principalement via une surcharge d'une classe PrestaShop de base. Au lieu d'utiliser des hooks, il modifie directement le comportement de la classe `Product` pour ajuster la façon dont les prix sont calculés lorsqu'une réduction de groupe client est impliquée et qu'une règle de panier est active. Cette approche garantit que la logique de réduction est appliquée à un niveau fondamental lors de la récupération du prix du produit.

### 4.2 Contrôleurs (`controllers/`)

- Ce module n'inclut aucun contrôleur front-office ou back-office personnalisé. Sa fonctionnalité est implémentée via des surcharges de classe.

### 4.3 Classes et modèles de base (`classes/`)

-   **Chemin du fichier** : `exgcr/override/classes/Product.php`

    -   **Nom de la classe** : `Product` (surcharge la classe `Product` de base)
    -   **Classe parente** : `ProductCore`
    -   **Responsabilité** : Cette surcharge modifie la méthode `getPriceStatic` de la classe `Product`. La méthode `getPriceStatic` est cruciale car elle est responsable du calcul du prix final d'un produit, en tenant compte de divers facteurs tels que les taxes, les prix spécifiques, les groupes de clients et les règles de panier.
    -   **Logique clé** :
        -   La surcharge vérifie si le module `exgcr` est activé.
        -   Elle vérifie ensuite s'il y a une `CartRule` (code de bon d'achat) active appliquée au panier actuel.
        -   Si les deux conditions sont remplies (module activé ET bon d'achat présent), elle modifie les paramètres passés à la méthode `getPriceStatic` parente pour ignorer efficacement la réduction de groupe client. Plus précisément, elle définit le paramètre `$use_group_reduction` sur `false` lors de l'appel de la méthode parente, empêchant ainsi l'application de la réduction de groupe.
        -   Cela garantit que lorsqu'un bon d'achat est utilisé, le calcul du prix se déroule comme si le client n'appartenait pas à un groupe bénéficiant d'une réduction, empêchant ainsi le cumul des réductions de groupe avec les réductions par bon d'achat.
-   **Chemin du fichier** : `exgcr/override/classes/index.php`

    -   **Objectif** : Il s'agit d'un fichier `index.php` vide standard placé dans les répertoires pour empêcher l'affichage du contenu des répertoires (mesure de sécurité). Il ne contient aucun code fonctionnel.

### 4.4 Actifs JavaScript (`views/js/`)

- Ce module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

- Ce module n'inclut aucun fichier CSS personnalisé.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- Ce module n'inclut aucun fichier de modèle Smarty personnalisé. Sa configuration est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Ce module ne crée aucune table de base de données personnalisée.
    -   Il stocke son paramètre de configuration (`exgcr`) dans la table standard `ps_configuration`.
        -   Entrée `PS_CONFIGURATION` : `EXGCR_ENABLED` (stocke `1` pour activé, `0` pour désactivé).
-   **Table des hooks enregistrés** :

    -   Ce module n'enregistre aucun hook spécifique dans la table `ps_hook_module`. Sa fonctionnalité est implémentée via une surcharge de classe, ce qui est un moyen plus direct de modifier le comportement de base sans dépendre de l'exécution des hooks.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module "Désactiver la réduction de groupe dans le panier avec un code de bon d'achat", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité du module et son intégration avec votre boutique PrestaShop.
