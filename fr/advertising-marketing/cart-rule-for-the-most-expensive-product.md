---
title: "Règle de panier pour le produit le plus cher - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Règle de panier pour le produit le plus cher' par MyPresta.eu."
sidebar:
  label: "Règle de panier pour le produit le plus cher"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Cart rule for the most expensive product sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/cart-rule-for-the-most-expensive-product.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/cart-rule-for-the-most-expensive-product/)
>
> ---


# Règle de panier pour le produit le plus cher

## 1. Exigences et compatibilité

-   **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x
-   **Compatibilité PHP** : PHP 7.1 - 8.5
-   **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Après l'installation, cliquez sur "Configurer" à côté du module dans le Gestionnaire de modules. Cela vous mènera à l'écran de configuration principal pour "Règle de panier pour le produit le plus cher".

#### Paramètres et options :

-   **Mises à jour en direct MyPresta.eu (mypresta_updates)**
    -   **Ce que fait ce paramètre :** Ce paramètre contrôle si le module peut vérifier les mises à jour directement depuis MyPresta.eu. Il vous aide à vous assurer que vous utilisez toujours la dernière version avec les corrections de bugs et les nouvelles fonctionnalités.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé (OUI) :* Le module se connectera périodiquement à MyPresta.eu pour vérifier les nouvelles versions. Si une mise à jour est disponible, vous pourriez voir une notification dans votre Back Office PrestaShop.
        -   *Lorsqu'il est désactivé (NON) :* Le module ne vérifiera pas les mises à jour automatiquement. Vous devrez vérifier et télécharger manuellement les mises à jour depuis votre compte MyPresta.eu.
    -   **Valeur recommandée :** OUI
    -   **Scénario / exemple de marchand :** Garder cette option activée garantit que vous recevez des notifications en temps opportun pour les mises à jour critiques, améliorant la sécurité et la compatibilité sans effort manuel.

-   **Produits exclus (csc_excluded_products)**
    -   **Ce que fait ce paramètre :** Ce champ vous permet de spécifier les produits qui ne doivent *jamais* être considérés pour la réduction "produit le plus cher", même s'ils sont effectivement l'article le plus cher du panier. Ceci est utile pour les produits à très faible marge, les promotions spéciales ou les articles que vous ne souhaitez pas réduire.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque des ID de produit sont saisis :* Le module ignorera ces produits spécifiques lors de la détermination de l'article le "plus cher" pour la règle de panier. Si l'un de ces produits exclus est le plus cher, le module recherchera alors le prochain produit le plus cher *non exclu* pour appliquer la réduction.
        -   *Lorsqu'il est laissé vide :* Tous les produits du panier sont éligibles pour être identifiés comme le "plus cher" pour la réduction.
    -   **Valeur recommandée :** Laisser vide sauf si vous avez des produits spécifiques à exclure.
    -   **Scénario / exemple de marchand :** Vous vendez un produit très populaire à forte marge (ID 123) et quelques articles d'appel (ID 456, ID 789). Vous souhaitez que la réduction "produit le plus cher" s'applique à vos articles à forte marge, mais pas aux articles d'appel. Vous saisiriez `456,789` (ID de produit séparés par des virgules) dans ce champ.

#### 2.1.1 Page d'édition de la règle de panier (Back Office > Catalogue > Réductions > Règles panier > Ajouter / Modifier)
Ce module ajoute une nouvelle option directement à la page standard de création/édition des règles de panier de PrestaShop. Vous trouverez cette option lorsque vous créez ou modifiez une règle de panier qui utilise une **réduction en pourcentage**.

-   **Emplacement du menu :** Back Office > Catalogue > Réductions > Règles panier. Cliquez sur "Ajouter une nouvelle règle panier" ou modifiez une règle existante.
-   **Action disponible :** Sur l'onglet "Actions" de la configuration de la règle de panier, après avoir sélectionné "Pourcentage" pour l'option "Appliquer une réduction", une nouvelle case à cocher apparaîtra.

    -   **Appliquer la réduction uniquement au produit le plus cher**
        -   **Ce que fait ce paramètre :** C'est la fonctionnalité principale du module. Lorsqu'elle est activée pour une règle de panier spécifique, la réduction en pourcentage définie pour cette règle ne sera appliquée qu'au produit unique le plus cher du panier du client.
        -   **Effet de la modification de ce paramètre :**
            -   *Lorsqu'elle est activée (cochée) :* La réduction en pourcentage de la règle de panier sera calculée uniquement sur le prix du produit le plus cher du panier (à l'exclusion de tout produit que vous avez globalement exclu dans la configuration principale du module).
            -   *Lorsqu'elle est désactivée (décochée) :* La règle de panier se comportera comme une réduction en pourcentage standard de PrestaShop, appliquant la réduction au total du panier ou aux produits éligibles selon les autres configurations de la règle de panier (par exemple, sélection de produits, montant minimum).
        -   **Valeur recommandée :** Activez ceci uniquement pour les règles de panier où vous souhaitez spécifiquement cibler l'article le plus cher.
        -   **Scénario / exemple de marchand :** Vous souhaitez lancer une promotion "20 % de réduction sur votre article le plus cher". Vous créez une nouvelle règle de panier, définissez la réduction à 20 % (pourcentage), puis cochez cette case. Lorsque les clients utilisent ce bon d'achat, ils bénéficieront de 20 % de réduction sur leur article le plus cher, et non de 20 % sur l'ensemble de leur commande.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Config du module | Mises à jour en direct MyPresta.eu | OUI | Active les vérifications automatiques des mises à jour pour le module. |
| Config du module | Produits exclus | Vide | ID de produits séparés par des virgules à exclure du calcul du "plus cher". |
| Édition Règle panier (onglet Actions) | Appliquer la réduction uniquement au produit le plus cher | Décoché | Lorsqu'elle est cochée, applique la réduction en pourcentage uniquement à l'article le plus cher du panier. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : La réduction ne s'applique pas au produit le plus cher, ou elle ne fonctionne pas du tout.**
R :
1.  **Vérifiez la configuration de la règle de panier :** Allez dans **Catalogue > Réductions > Règles panier**, modifiez votre règle et assurez-vous que sur l'onglet "Actions", "Appliquer une réduction" est défini sur "Pourcentage" et que la case à cocher "Appliquer la réduction uniquement au produit le plus cher" est **cochée**.
2.  **Vérifiez l'éligibilité du produit :** Vérifiez la configuration principale du module (**Modules > Gestionnaire de modules > Configurer** pour "Règle de panier pour le produit le plus cher"). Assurez-vous que le produit auquel vous vous attendez que la réduction s'applique n'est pas répertorié dans le champ "Produits exclus".
3.  **Videz le cache :** Parfois, le cache de PrestaShop peut empêcher les modifications de prendre effet immédiatement. Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" en haut à droite.
4.  **Conflits de modules :** Si vous avez d'autres modules qui modifient fortement les calculs de panier ou de réduction, il pourrait y avoir un conflit. Essayez de désactiver temporairement d'autres modules liés aux réductions pour voir si le problème se résout.

**Q : Puis-je appliquer cette réduction à une catégorie de produits spécifique uniquement ?**
R : Oui, vous pouvez combiner la fonctionnalité de ce module avec les restrictions standard des règles de panier de PrestaShop. Sur l'onglet "Conditions" de votre règle de panier, vous pouvez ajouter des conditions comme "Sélection de produits" pour spécifier que la réduction ne s'applique que si un produit d'une certaine catégorie est dans le panier. Cependant, rappelez-vous que *si* un tel produit est présent, le module choisira toujours le produit le plus cher *global* du panier (sauf si ce produit est exclu) et lui appliquera la réduction, pas nécessairement le produit le plus cher *de cette catégorie spécifique*.

**Q : Ce module fonctionne-t-il avec des réductions de montant fixe ?**
R : Non, ce module est spécifiquement conçu pour fonctionner uniquement avec des **réductions en pourcentage**. L'option "Appliquer la réduction uniquement au produit le plus cher" n'apparaîtra et ne fonctionnera que lorsque vous sélectionnerez "Pourcentage" comme type de réduction sur l'onglet "Actions" de la règle de panier.

**Q : Mon thème personnalisé n'affiche pas correctement la réduction.**
R : Le module modifie principalement la logique de calcul de la réduction, et non l'affichage en front-office. Les modèles par défaut de PrestaShop devraient afficher la réduction correctement. Si votre thème personnalisé a fortement personnalisé le résumé du panier ou du paiement, il pourrait nécessiter des ajustements mineurs pour refléter correctement la façon dont les réductions sont appliquées. Dans la plupart des cas, vider le cache Smarty (**Paramètres avancés > Performances > Vider le cache**) devrait résoudre les problèmes d'affichage. Sinon, consultez le développeur de votre thème.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture
Le module "Règle de panier pour le produit le plus cher" (`crexpensive`) étend principalement la classe `CartRule` de PrestaShop via un override. Cela lui permet d'injecter une logique personnalisée dans le processus de calcul des réductions sans modifier directement les fichiers du cœur. Le module fournit également une interface de configuration minimale dans le Back Office et enregistre un hook pour injecter le JavaScript nécessaire aux formulaires d'administration.

### 4.2 Contrôleurs (`controllers/`)
Ce module n'introduit aucun contrôleur front-office ou back-office personnalisé. Sa fonctionnalité est intégrée directement dans les processus PrestaShop existants via des overrides et des hooks.

### 4.3 Classes et modèles du cœur (`classes/`)

-   **`crexpensive/override/classes/CartRule.php`**
    *   **Nom de la classe :** `CartRule` (remplace la classe `CartRule` du cœur)
    *   **Classe parente :** `CartRuleCore`
    *   **Responsabilité :** Cet override est le cœur de la fonctionnalité du module. Il modifie le comportement de l'application des règles de panier, ciblant spécifiquement le calcul de `reduction_percent`.
    *   **Méthodes et logique clés :**
        *   L'override intercepte ou modifie probablement les méthodes liées au calcul de `reduction_percent` au sein de la classe `CartRule`. Il contiendra une logique pour :
            1.  Vérifier si la règle de panier actuelle a l'indicateur `apply_to_most_expensive_product` activé (un champ personnalisé ajouté par le module).
            2.  Si activé, itérer sur les produits du panier pour identifier le plus cher, en tenant compte de tous les produits globalement exclus configurés dans le module.
            3.  Ajuster l'application de `reduction_percent` pour n'affecter que le produit le plus cher identifié, en s'assurant que la réduction est calculée par rapport à son prix plutôt qu'à l'ensemble du panier ou à d'autres produits.
        *   Il ajoute également un nouveau champ à la définition de `CartRule` (`$definition`) pour stocker l'indicateur `apply_to_most_expensive_product` dans la table de base de données `ps_cart_rule`.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`crexpensive/views/js/crexpensive.js`**
    *   **Portée :** Back-office (spécifiquement la page d'édition de la règle de panier).
    *   **Responsabilité :** Ce script est responsable de l'affichage/masquage dynamique de la case à cocher "Appliquer la réduction uniquement au produit le plus cher" sur la page d'édition de la règle de panier.
    *   **Logique clé :**
        *   Il écoute probablement les changements sur les listes déroulantes/boutons radio "Appliquer une réduction" (spécifiquement lorsque "Pourcentage" est sélectionné).
        *   Lorsque "Pourcentage" est choisi, il rend la case à cocher personnalisée visible.
        *   Lorsque d'autres types de réduction (par exemple, "Montant", "Livraison gratuite") sont choisis, il masque la case à cocher, car le module ne s'applique qu'aux réductions en pourcentage.
        *   Assure que l'état de la case à cocher est correctement chargé lors de l'édition d'une règle de panier existante.

### 4.5 Feuilles de style CSS (`views/css/`)
Ce module n'inclut aucun fichier CSS personnalisé. Il s'appuie sur le style par défaut de PrestaShop pour ses éléments de configuration et la case à cocher injectée sur la page de la règle de panier.

### 4.6 Structure des modèles Smarty (`views/templates/`)
Ce module n'inclut aucun fichier de modèle Smarty personnalisé. Le formulaire de configuration est rendu via `getContent()` dans le fichier principal du module, et la case à cocher personnalisée est injectée dans la page d'édition de la règle de panier existante via JavaScript.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    *   Le module modifie la table `ps_cart_rule` en ajoutant une nouvelle colonne, probablement nommée `apply_to_most_expensive_product` (ou similaire), qui est un champ tinyint (booléen) pour stocker l'état de la case à cocher personnalisée pour chaque règle de panier.
    *   Les valeurs de configuration (`mypresta_updates`, `csc_excluded_products`) sont stockées dans la table `ps_configuration`.

-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| :-------- | :--------------- | :---------------- |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses ressources média (JS/CSS). | Ce hook est utilisé pour charger `crexpensive.js` sur la page d'édition de la règle de panier dans le Back Office, permettant l'affichage dynamique de la case à cocher "Appliquer la réduction uniquement au produit le plus cher". |

## 5. Support officiel et mises à jour
Pour les mises à jour officielles, le support technique et pour accéder aux dernières versions du module "Règle de panier pour le produit le plus cher", veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir.
