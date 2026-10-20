---
title: "Méthodes de livraison (transporteurs) du produit le plus cher - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Méthodes de livraison (transporteurs) du produit le plus cher' par MyPresta.eu."
sidebar:
  label: "Méthodes de livraison (transporteurs) du produit le plus cher - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Shipping methods (carriers) from the most expensive product sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/shipping-methods-carriers-from-the-most-expensive-product.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/shipping-methods-carriers-from-the-most-expensive-product/)
>
> ---


# Méthodes de livraison (transporteurs) du produit le plus cher

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur "Configurer" à côté du nom du module pour accéder à ses paramètres.

#### **Activer / Désactiver le module**

- **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité principale du module.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Le module modifiera la logique de sélection des transporteurs par défaut de PrestaShop, garantissant que seuls les transporteurs associés au produit le plus cher du panier sont affichés lors du paiement.
  - *Lorsqu'il est désactivé :* PrestaShop reviendra à son comportement par défaut, où les transporteurs ne sont affichés que s'ils peuvent expédier *tous* les produits du panier.
- **Valeur recommandée :** "Activé" si vous souhaitez utiliser la fonctionnalité du module.
- **Scénario / exemple de marchand :** Si vous testez le module ou souhaitez temporairement revenir au comportement par défaut de PrestaShop sans désinstaller, vous pouvez le désactiver ici.

#### **Comment obtenir les transporteurs ?**

- **Ce que fait ce paramètre :** Ce paramètre crucial définit *comment* le module identifie le "produit le plus cher" et détermine ensuite les transporteurs disponibles. Il offre deux méthodes distinctes.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est réglé sur "Du produit le plus cher (par prix)" :* Le module calculera le prix total de chaque produit unique dans le panier (quantité \* prix unitaire) et identifiera le produit avec le prix total le plus élevé. Les transporteurs associés à *ce produit spécifique* seront ensuite utilisés pour filtrer les options de livraison disponibles.
  - *Lorsqu'il est réglé sur "Du produit le plus cher (par prix) - LIVRAISON GRATUITE" :* Cette option fonctionne de manière similaire à la première, mais elle prend également en compte si le produit le plus cher est éligible à la livraison gratuite. Si le produit le plus cher a la livraison gratuite activée, alors les options de livraison gratuite seront prioritaires ou rendues disponibles selon vos paramètres de transporteur.
  - *Lorsqu'il est réglé sur "Du produit le plus cher (par prix) - COÛT" :* Cette option identifie également le produit le plus cher par prix, mais elle se concentre spécifiquement sur le *coût* associé à l'expédition de ce produit. Elle garantit que les coûts et options de livraison présentés sont directement liés à la configuration d'expédition de l'article le plus cher.
- **Valeur recommandée :**
  - "Du produit le plus cher (par prix)" est le choix le plus courant et recommandé pour une utilisation générale, car il met directement en œuvre la promesse principale du module.
  - Choisissez "Du produit le plus cher (par prix) - LIVRAISON GRATUITE" si vous proposez fréquemment la livraison gratuite sur des articles de grande valeur et que vous souhaitez que cela soit une considération principale dans la sélection des transporteurs.
  - Choisissez "Du produit le plus cher (par prix) - COÛT" si vous avez des règles de coût d'expédition complexes liées à des produits spécifiques de grande valeur et que vous souhaitez que ces règles dictent les transporteurs disponibles.
- **Scénario / exemple de marchand :**
  - Vous vendez une télévision à 1000 $ et une télécommande à 10 $. Si la télévision est configurée avec des transporteurs spécifiques (par exemple, fret assuré) et la télécommande avec un service postal standard, choisir "Du produit le plus cher (par prix)" garantira que les transporteurs de la télévision sont affichés.
  - Si votre télévision à 1000 $ est livrée avec la livraison gratuite, sélectionner "Du produit le plus cher (par prix) - LIVRAISON GRATUITE" garantirait que les options de livraison gratuite sont présentées si disponibles pour la télévision.

#### **Tableau de référence rapide de la configuration**

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Activer / Désactiver le module | Activé | Active/désactive la logique du module pour la sélection des transporteurs en fonction du produit le plus cher. |
| Page de configuration du module | Comment obtenir les transporteurs ? | Du produit le plus cher (par prix) | Définit la méthode d'identification du "produit le plus cher" et de ses transporteurs associés. Options : "par prix", "par prix - LIVRAISON GRATUITE", "par prix - COÛT". |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai activé le module, mais je vois toujours les anciennes options de transporteur ou aucun transporteur du tout.**
R :

1.  **Vider le cache :** Videz toujours le cache de votre PrestaShop après avoir modifié la configuration du module. Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" en haut à droite.
2.  **Vérifier les associations de transporteurs de produits :** Assurez-vous que vos produits, en particulier les plus chers, sont correctement associés aux transporteurs souhaités dans leurs paramètres de produit (**Catalogue > Produits > Modifier le produit > onglet Livraison**).
3.  **Vérifier que le module est activé :** Vérifiez à nouveau que le paramètre "Activer / Désactiver le module" est réglé sur "Activé" dans la configuration du module.
4.  **Compatibilité du thème :** Bien que rare pour ce type de module, un thème fortement personnalisé pourrait interférer. Passez temporairement au thème PrestaShop par défaut pour écarter cette possibilité.

**Q : Comment le module gère-t-il deux produits ayant exactement le même prix le plus élevé ?**
R : Dans les cas où deux produits ou plus partagent exactement le prix le plus élevé, le module en sélectionnera généralement un en fonction de l'ordre interne des ID de produit PrestaShop ou de l'ordre dans lequel ils ont été ajoutés au panier. Il utilisera ensuite les transporteurs associés à ce produit sélectionné. Pour la cohérence, il est préférable de s'assurer que vos configurations de transporteurs sont suffisamment robustes pour couvrir des articles de grande valeur similaires.

**Q : Ce module affecte-t-il les frais de livraison ou seulement la disponibilité des transporteurs ?**
R : Ce module affecte principalement la *disponibilité des transporteurs*. Il détermine *quels* transporteurs sont affichés. Les frais de livraison réels pour le transporteur choisi seront toujours calculés par les mécanismes standard de PrestaShop (basés sur le poids, le prix, la zone, etc.) pour le *panier entier*, mais uniquement pour les transporteurs rendus disponibles par la logique de ce module.

**Q : Que se passe-t-il si le produit le plus cher n'a aucun transporteur associé ?**
R : Si le produit le plus cher du panier n'a aucun transporteur explicitement associé dans ses paramètres de produit, alors aucun transporteur ne sera affiché lors du paiement, ce qui pourrait entraîner un message "aucune méthode de livraison disponible". Assurez-vous toujours que vos produits de grande valeur ont des transporteurs appropriés attribués.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module "Méthodes de livraison (transporteurs) du produit le plus cher" réalise sa fonctionnalité en surchargeant une classe PrestaShop de base, `Cart`. C'est une méthode courante et puissante dans PrestaShop pour modifier les comportements fondamentaux sans modifier directement les fichiers du cœur. En surchargeant `Cart::getAvailableCarriers()`, le module injecte sa logique personnalisée pour filtrer les transporteurs en fonction du produit le plus cher, plutôt que la règle par défaut "tous les produits doivent être compatibles".

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. Le module fonctionne en surchargeant une classe de base, et non en introduisant de nouvelles routes ou pages front-office.
- **Contrôleurs d'administration Back-Office** : Aucun. La configuration du module est gérée directement dans la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles de base (`classes/`)

La logique principale du module réside dans une surcharge de la classe `Cart`.

- **`cfep/override/classes/Cart.php`**

  - **Nom de la classe** : `Cart` (surcharge `PrestaShop\Classes\Cart\Cart` ou `CartCore` selon la version et le contexte de PrestaShop).
  - **Classe parente** : `CartCore`
  - **Responsabilité** : Ce fichier contient la méthode `getAvailableCarriers()` surchargée. Cette méthode est cruciale pour déterminer quels transporteurs sont présentés au client lors du paiement. La surcharge introduit la logique pour :
    1. Identifier le produit le plus cher dans le panier actuel en fonction de la configuration du module (`CFEP`, `CFEP_FREE`, `CFEP_COST`).
    2. Récupérer les transporteurs spécifiquement associés à ce produit le plus cher.
    3. Filtrer la liste de tous les transporteurs disponibles pour n'inclure que ceux compatibles avec le produit le plus cher.
    4. Retourner cette liste filtrée de transporteurs.
  - **Méthodes publiques clés** :
    - `getAvailableCarriers(bool $return_full_list = false, int $id_zone = null, bool $use_cache = true)` : C'est la méthode surchargée. Elle étend la méthode originale `CartCore::getAvailableCarriers` pour implémenter la logique de filtrage des transporteurs personnalisée. Elle appelle d'abord la méthode parente pour obtenir tous les transporteurs potentiellement disponibles, puis applique son propre filtrage basé sur le produit le plus cher.
- **`cfep/override/classes/index.php`**

  - **Responsabilité** : Il s'agit d'un fichier `index.php` vide standard, généralement placé dans les répertoires pour empêcher la liste des répertoires lorsqu'ils sont directement accessibles via un navigateur web. Il n'a aucun impact fonctionnel sur la logique du module.

### 4.4 Actifs JavaScript (`views/js/`)

- Aucun. Le module n'ajoute aucun JavaScript personnalisé au front ou au back office.

### 4.5 Feuilles de style CSS (`views/css/`)

- Aucun. Le module n'ajoute aucun CSS personnalisé au front ou au back office.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- Aucun. Le module n'utilise aucun modèle Smarty personnalisé. Son interface de configuration est générée dynamiquement par `getContent()` dans le fichier principal du module.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :
  Le module ne crée aucune table de base de données personnalisée. Il stocke ses paramètres de configuration dans la table standard `ps_configuration`.

  - Entrées `ps_configuration` :
    - `CFEP` : Stocke la méthode sélectionnée pour obtenir les transporteurs (par exemple, 'price', 'free', 'cost').
    - `mypresta_updates` : Utilisé pour les vérifications internes des mises à jour MyPresta.eu.
    - `update_` : Utilisé pour les vérifications internes des mises à jour MyPresta.eu.
    - `updatev_` : Utilisé pour les vérifications internes des mises à jour MyPresta.eu.
- **Table des hooks enregistrés** :
  Le module n'enregistre explicitement aucun hook dans la table `ps_hook_module`. Sa fonctionnalité est implémentée via une surcharge de classe, ce qui est un moyen plus direct de modifier le comportement de base de PrestaShop sans dépendre de points d'exécution de hooks spécifiques.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module "Méthodes de livraison (transporteurs) du produit le plus cher", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
