---
title: "Ship to pay + virtual products support - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Ship to pay + virtual products support par MyPresta.eu."
sidebar:
  label: "Ship to pay + virtual products support - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Ship to pay + virtual products support sur MyPresta.eu](https://mypresta.eu/modules/payment-process/ship-to-pay-virtual-products-support.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/payment/ship-to-pay-virtual-products-support/)
>
> ---


# Ship to pay + virtual products support

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises par PrestaShop lui-même et sont habituellement présentes sur tout environnement d'hébergement compatible.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Ship to pay + virtual products support ». Vous serez présenté avec un écran de configuration unique et complet.

Cet écran affiche une matrice (une grille) où vous pouvez lier vos transporteurs disponibles à vos modules de paiement installés.

**Comprendre la grille de configuration :**

- **Lignes (Transporteurs) :** Chaque ligne représente un transporteur que vous avez configuré dans votre boutique PrestaShop (par exemple, « Mon transporteur », « Transporteur par défaut PrestaShop », « DHL », « UPS », etc.).
- **Colonnes (Modules de paiement) :** Chaque colonne représente un module de paiement que vous avez installé et activé dans votre boutique PrestaShop (par exemple, « Virement bancaire », « Paiement à la livraison », « PayPal », « Stripe », etc.).
- **Cases à cocher :** À l'intersection de chaque ligne de transporteur et de chaque colonne de module de paiement, il y a une case à cocher.

**Comment configurer :**

1. **Identifiez vos transporteurs :** Regardez la colonne de gauche pour voir tous vos transporteurs actifs.
2. **Identifiez vos méthodes de paiement :** Regardez la ligne du haut pour voir tous vos modules de paiement actifs.
3. **Reliez-les :** Pour chaque transporteur, parcourez sa ligne et **cochez la case** pour chaque méthode de paiement que vous souhaitez autoriser pour ce transporteur spécifique.
   - *Ce que fait ce paramètre :* Cette case à cocher détermine si une méthode de paiement particulière sera proposée au client lorsqu'il sélectionnera le transporteur correspondant lors du paiement.
   - *Effet de la modification de ce paramètre :*
     - **Lorsque coché :** La méthode de paiement sera visible et sélectionnable par le client s'il choisit ce transporteur.
     - **Lorsque décoché :** La méthode de paiement sera masquée et indisponible pour le client s'il choisit ce transporteur.
   - *Valeur recommandée :* Cochez uniquement les combinaisons qui ont du sens pour votre logique commerciale.
   - *Scénario/exemple pour le marchand :* Si « DHL Express » est un service rapide et premium, vous ne pourriez cocher que « PayPal » et « Carte de crédit (Stripe) » pour celui-ci, et décocher « Virement bancaire » pour assurer un paiement rapide pour une livraison rapide.

**Ligne spéciale : « Produits virtuels »**

Ce module inclut une fonctionnalité unique pour les produits virtuels. Vous verrez une ligne dédiée intitulée **« Produits virtuels »** (ou similaire, selon votre version de PrestaShop et votre langue).

- **Ce que fait ce paramètre :** Cette ligne vous permet de spécifier quelles méthodes de paiement sont disponibles lorsque le panier d'un client ne contient *que* des produits virtuels. Étant donné que les produits virtuels n'ont pas de méthode de livraison traditionnelle, cette ligne agit comme leur « transporteur » pour l'association des méthodes de paiement.
- *Effet de la modification de ce paramètre :*
  - **Lorsque coché (pour une méthode de paiement dans la ligne « Produits virtuels ») :** Cette méthode de paiement sera disponible si le panier du client ne contient que des produits virtuels.
  - **Lorsque décoché :** Cette méthode de paiement ne sera pas disponible pour les paniers contenant uniquement des produits virtuels.
- *Valeur recommandée :* Cochez les méthodes de paiement adaptées à la livraison numérique immédiate, généralement les passerelles de paiement en ligne comme PayPal, Stripe ou les modules de carte de crédit.
- *Scénario/exemple pour le marchand :* Si vous vendez des e-books, vous cocherez probablement « PayPal » et « Carte de crédit (Stripe) » dans la ligne « Produits virtuels », mais décocherez « Paiement à la livraison » ou « Virement bancaire » car ceux-ci ne conviennent pas à la livraison numérique instantanée.

**Enregistrement de votre configuration :**

- Après avoir effectué toutes vos sélections, n'oubliez pas de cliquer sur le bouton **« Enregistrer »** (généralement en bas de la page) pour appliquer vos modifications.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Case à cocher pour Transporteur X / Paiement Y | Décoché par défaut | **Objectif :** Lie une méthode de paiement spécifique à un transporteur spécifique. **Impact :** Si coché, la méthode de paiement est disponible lorsque le Transporteur X est choisi. Si décoché, elle est masquée. |
| Page de configuration du module | Case à cocher pour « Produits virtuels » / Paiement Y | Décoché par défaut | **Objectif :** Lie une méthode de paiement spécifique aux paniers contenant uniquement des produits virtuels. **Impact :** Si coché, la méthode de paiement est disponible pour les paniers de produits virtuels uniquement. Si décoché, elle est masquée. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai configuré le module, mais les méthodes de paiement ne changent pas lors du paiement. Qu'est-ce qui ne va pas ?**
R1 :

- **Vider le cache :** Le problème le plus courant. Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes).
- **Module activé :** Assurez-vous que le module « Ship to pay + virtual products support » est bien activé dans **Modules > Gestionnaire de modules**.
- **Modules de paiement activés :** Assurez-vous que les modules de paiement que vous essayez de lier sont également activés et configurés correctement dans votre boutique.
- **Compatibilité du thème :** Bien que rare, certains thèmes fortement personnalisés peuvent interférer. Si vider le cache ne fonctionne pas, essayez de passer temporairement au thème PrestaShop par défaut pour voir si le problème persiste. Si cela résout le problème, votre thème pourrait nécessiter un ajustement.

**Q2 : Pourquoi certaines méthodes de paiement s'affichent-elles toujours même si je les ai décochées pour un transporteur ?**
R2 :

- **Plusieurs transporteurs dans le panier :** Si un client a des produits dans son panier qui utiliseraient différents transporteurs (par exemple, un produit expédié par le transporteur A, un autre par le transporteur B), la logique de paiement de PrestaShop peut devenir complexe. Ce module fonctionne principalement lorsqu'une seule méthode de livraison est sélectionnée pour l'ensemble du panier.
- **Produits virtuels dans le panier :** Si le panier contient un mélange de produits physiques et virtuels, la logique du module pour les produits virtuels pourrait interagir avec la logique spécifique au transporteur. Assurez-vous que votre ligne « Produits virtuels » est configurée comme prévu.
- **Autres modules :** Un autre module pourrait remplacer les options de paiement. Désactivez temporairement les autres modules liés au paiement pour vérifier les conflits.

**Q3 : Comment traduire le texte du module dans d'autres langues ?**
R3 :

- Allez dans **International > Traductions** dans votre Back Office PrestaShop.
- Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez la langue que vous souhaitez traduire.
- Trouvez le module « Ship to pay + virtual products support » dans la liste et cliquez sur « Modifier ». Vous pouvez alors modifier toutes les chaînes traduisibles.

**Q4 : J'ai ajouté un nouveau transporteur ou module de paiement, mais il n'apparaît pas dans la grille de configuration.**
R4 :

- **Actualiser la configuration du module :** Parfois, PrestaShop a besoin d'une actualisation pour prendre en compte de nouvelles entités. Allez dans **Modules > Gestionnaire de modules**, trouvez « Ship to pay + virtual products support », et cliquez à nouveau sur « Configurer ». Cela devrait recharger la page de configuration et afficher le nouveau transporteur/module de paiement.
- **Assurez-vous qu'il est activé :** Assurez-vous que le nouveau transporteur ou module de paiement est entièrement activé et configuré dans sa section respective du Back Office de PrestaShop.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Vue d'ensemble de l'architecture

Le module « Ship to pay + virtual products support » fonctionne en surchargeant une classe PrestaShop principale responsable de la recherche des options de paiement disponibles lors du paiement. Cela lui permet d'injecter sa logique personnalisée basée sur les transporteurs sélectionnés et la présence de produits virtuels dans le panier, filtrant les méthodes de paiement présentées au client. Il utilise le système de surcharge de PrestaShop et le stockage de configuration standard.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur front-office ou back-office personnalisé. Sa logique est principalement gérée via le fichier principal du module et une surcharge.

### 4.3 Classes et modèles principaux (`classes/`)

- **`shiptopay/override/classes/checkout/PaymentOptionsFinder.php`**
  - **Objectif :** C'est le cœur de la fonctionnalité du module. Il surcharge la classe `PaymentOptionsFinder` par défaut de PrestaShop, qui est responsable de la détermination des options de paiement disponibles pour le client lors du paiement.
  - **Classe parente :** `PaymentOptionsFinderCore`
  - **Méthodes et logique clés :**
    - La méthode `find()` surchargée (ou similaire, selon la version de PrestaShop) est interceptée.
    - Dans cette méthode, le module récupère l'ID du transporteur actuellement sélectionné (à partir du panier ou de la session) et vérifie si le panier ne contient que des produits virtuels.
    - Il interroge ensuite la configuration du module (stockée dans `ps_configuration`) pour déterminer quels modules de paiement sont autorisés pour le transporteur sélectionné ou pour les produits virtuels.
    - La liste originale des options de paiement renvoyée par `PaymentOptionsFinderCore` est ensuite filtrée, supprimant toutes les méthodes de paiement qui ne sont pas autorisées selon la configuration du module.
    - Cela garantit que seules les méthodes de paiement autorisées sont affichées au client.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé. La mise à jour dynamique des options de paiement est gérée par le JavaScript de paiement principal de PrestaShop, qui réagit aux changements de sélection de méthode de livraison et re-rend la section de paiement en fonction des options filtrées fournies par le `PaymentOptionsFinder` surchargé.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé. Il s'intègre parfaitement au style de thème PrestaShop existant pour les options de paiement.

### 4.6 Structure de modèle Smarty (`views/templates/`)

- **`shiptopay/views/shiptopay.tpl`**
  - **Objectif :** Ce modèle est probablement utilisé pour rendre le formulaire de configuration du module dans le Back Office de PrestaShop. Il construit la matrice HTML (grille) des transporteurs et des méthodes de paiement avec des cases à cocher, permettant au marchand de les lier.
  - **Portée :** Modèle d'administration.
  - **Variables :** Il itérerait généralement sur les tableaux `$carriers` et `$payment_modules`, en utilisant `Configuration::get()` pour récupérer les paramètres enregistrés pour chaque case à cocher.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données :**

  - Le module ne crée aucune table SQL personnalisée.
  - Les paramètres de configuration (les liens entre les transporteurs/produits virtuels et les méthodes de paiement) sont stockés dans la table `ps_configuration`. Chaque paramètre serait généralement stocké sous forme de paire clé-valeur, où la clé pourrait être `SHIP_TO_PAY_CARRIER_X_PAYMENT_Y` et la valeur `1` (activé) ou `0` (désactivé). Les paramètres des « Produits virtuels » suivraient une convention de nommage similaire.
- **Table des hooks enregistrés :**

  | Nom du hook | Moment d'exécution | Objectif technique |
  | --- | --- | --- |
  | `displayHeader` | Dans la section `<head>` de chaque page. | Bien que listé comme un hook front-office potentiel, ce module utilise principalement une surcharge et ne rend généralement pas de contenu visible via `displayHeader`. Il pourrait être utilisé pour l'initialisation interne du module ou le chargement d'actifs s'il y en avait. |
  | `displayRightColumn` | Dans la colonne de droite des pages (si activé par le thème). | Non directement utilisé pour la fonctionnalité principale du module, car son impact est sur les options de paiement lors du paiement. |
  | `displayLeftColumn` | Dans la colonne de gauche des pages (si activé par le thème). | Non directement utilisé pour la fonctionnalité principale du module, car son impact est sur les options de paiement lors du paiement. |
  | `displayFooter` | Dans la section du pied de page de chaque page. | Non directement utilisé pour la fonctionnalité principale du module, car son impact est sur les options de paiement lors du paiement. |
  | `displayModuleConfigureExtraButtons` | Dans le gestionnaire de modules, à côté du bouton de configuration. | Non explicitement utilisé pour la fonctionnalité principale, mais pourrait être utilisé pour des actions d'administration supplémentaires. |
  | `actionPaymentOptionsModifier` | (Implicite/Interne) | Ce module fonctionne principalement en surchargeant `PaymentOptionsFinder`, qui est appelé en interne pendant le processus de paiement pour générer la liste des options de paiement. Bien qu'il ne s'agisse pas d'un hook `hookDisplay` ou `action` traditionnel, la surcharge agit comme un point d'interception. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Ship to pay + virtual products support », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question concernant la fonctionnalité du module.
