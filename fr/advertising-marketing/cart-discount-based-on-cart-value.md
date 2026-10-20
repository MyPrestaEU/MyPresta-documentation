---
title: "Remise panier basée sur la valeur du panier - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop « Remise panier basée sur la valeur du panier » par MyPresta.eu."
sidebar:
  label: "Remise panier basée sur la valeur du panier - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Cart discount based on cart value sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/cart-discount-based-on-cart-value.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/cart-discount-based-on-cart-value/)
>
> ---


# Remise panier basée sur la valeur du panier

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises, qui sont généralement disponibles sur la plupart des environnements d'hébergement compatibles PrestaShop.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran principal où vous contrôlez le comportement général et les paramètres de votre programme de remise sur le panier.

-   **Activer le programme**

    -   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver l'ensemble du programme de remise sur le panier.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (OUI) :* Le module vérifiera activement les valeurs du panier et appliquera les remises selon vos règles définies.
        -   *Lorsqu'désactivé (NON) :* Aucune remise sur le panier ne sera appliquée, et aucun message connexe n'apparaîtra sur la page du panier, quelles que soient les autres configurations.
    -   **Valeur recommandée :** OUI (une fois que vous avez configuré vos règles de remise).
    -   **Scénario / exemple marchand :** Vous pourriez le désactiver temporairement lors d'une vente spéciale où d'autres règles de remise s'appliquent, ou si vous devez effectuer une maintenance.
-   **Désactiver le programme de remises sur le panier pour les groupes de clients sélectionnés**

    -   **Ce que fait ce paramètre :** Vous permet d'empêcher des groupes de clients spécifiques (par exemple, grossistes, VIP ou invités) de recevoir ces remises basées sur la valeur du panier.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque sélectionné :* Les clients appartenant aux groupes choisis ne recevront aucune remise de ce module, même si la valeur de leur panier répond aux critères.
        -   *Lorsque non sélectionné :* Tous les groupes de clients sont éligibles aux remises.
    -   **Valeur recommandée :** Dépend de votre stratégie commerciale. Si vous avez des prix spéciaux pour certains groupes, vous pourriez les exclure.
    -   **Scénario / exemple marchand :** Vous avez un groupe de clients « Grossistes » qui bénéficie déjà de prix spéciaux. Vous sélectionneriez ce groupe ici pour éviter l'empilement des remises.
-   **Type de prix**

    -   **Ce que fait ce paramètre :** Détermine si la valeur du panier pour le calcul de la remise doit inclure ou exclure les taxes.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque défini sur « Prix TTC » :* La remise est calculée sur la valeur totale du panier *incluant* la TVA/les taxes.
        -   *Lorsque défini sur « Prix HT » :* La remise est calculée sur la valeur totale du panier *excluant* la TVA/les taxes.
    -   **Valeur recommandée :** « Prix TTC » pour la plupart des boutiques B2C, « Prix HT » pour les boutiques B2B ou si votre tarification principale est hors taxes.
    -   **Scénario / exemple marchand :** Si vos clients sont habitués à voir les prix TTC, le calcul de la remise basé sur le « Prix TTC » leur semblera plus naturel et transparent.
-   **Exclure les produits avec remise**

    -   **Ce que fait ce paramètre :** Contrôle si les produits déjà en promotion ou ayant un prix spécifique (par exemple, d'une règle de catalogue) doivent être pris en compte dans la valeur du panier pour le calcul de la remise.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (OUI) :* Les produits déjà remisés seront ignorés lors du calcul de la valeur totale du panier pour la remise échelonnée.
        -   *Lorsqu'désactivé (NON) :* Tous les produits du panier, qu'ils soient déjà remisés ou non, contribueront à la valeur du panier pour la remise échelonnée.
    -   **Valeur recommandée :** OUI, pour éviter le « double-remise » et protéger vos marges.
    -   **Scénario / exemple marchand :** Vous proposez une remise de 20 % sur des T-shirts spécifiques. Si un client achète un T-shirt et d'autres articles, et que ce paramètre est OUI, la valeur du T-shirt ne l'aidera pas à atteindre le niveau de remise suivant sur le panier.
-   **Exclure les produits du fabricant**

    -   **Ce que fait ce paramètre :** Vous permet de spécifier certains fabricants dont les produits ne doivent pas contribuer à la valeur du panier lors du calcul de la remise échelonnée.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque sélectionné :* Les produits des fabricants choisis seront ignorés lors du calcul de la valeur totale du panier pour la remise échelonnée.
        -   *Lorsque non sélectionné :* Tous les produits, quel que soit le fabricant, contribuent à la valeur du panier.
    -   **Valeur recommandée :** Laisser vide, sauf si vous avez des accords spécifiques ou des produits à faible marge de certains fabricants.
    -   **Scénario / exemple marchand :** Vous vendez des produits d'une marque premium qui a des règles de prix strictes et ne peut pas être incluse dans les remises générales. Vous sélectionneriez ce fabricant ici.
-   **Exclure les produits remisés de la valeur de la remise**

    -   **Ce que fait ce paramètre :** Détermine si la *valeur* des produits déjà remisés doit être exclue du *montant* de la remise sur le panier appliquée. C'est une distinction subtile mais importante par rapport à « Exclure les produits avec remise ».
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (OUI) :* Si une remise de 5 % sur le panier est appliquée, et que certains produits du panier sont déjà remisés, les 5 % ne s'appliqueront qu'aux articles non remisés.
        -   *Lorsqu'désactivé (NON) :* La remise de 5 % sur le panier s'appliquera à la *valeur totale* du panier, même si certains articles sont déjà remisés.
    -   **Valeur recommandée :** OUI, pour protéger les marges et éviter les remises excessives sur les articles déjà réduits.
    -   **Scénario / exemple marchand :** Un client a un panier de 100 €, avec un article de 20 € déjà remisé de 10 %. Si une remise de 5 % sur le panier s'applique et que ce paramètre est OUI, les 5 % ne s'appliqueront qu'aux articles non remisés d'une valeur de 80 €.
-   **Exclure le panier avec code de bon de réduction**

    -   **Ce que fait ce paramètre :** Empêche les remises basées sur la valeur du panier du module de s'appliquer si un client a déjà saisi un code de bon de réduction (coupon) distinct dans son panier.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (OUI) :* Si un client utilise un code de bon de réduction, la remise automatique sur le panier du module ne sera pas appliquée, évitant ainsi l'empilement des remises.
        -   *Lorsqu'désactivé (NON) :* La remise du module s'appliquera même si un code de bon de réduction est présent, ce qui pourrait empiler les remises.
    -   **Valeur recommandée :** OUI, pour éviter les remises excessives et garder le contrôle de vos promotions.
    -   **Scénario / exemple marchand :** Vous menez une campagne d'e-mailing spéciale avec un bon de réduction unique de 10 %. Vous voulez que les clients choisissent entre ce bon de réduction ou la remise échelonnée sur le panier, pas les deux.
-   **Afficher les informations du programme de remise sur la page du panier**

    -   **Ce que fait ce paramètre :** Contrôle si les messages concernant le programme de remise sur le panier (par exemple, « Dépensez X de plus pour Y % de remise ! ») sont affichés sur la page du panier d'achat.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (OUI) :* Des messages informatifs apparaîtront sur la page du panier, guidant les clients vers des dépenses plus élevées.
        -   *Lorsqu'désactivé (NON) :* Aucun message lié aux remises de ce module ne sera affiché sur la page du panier. La remise s'appliquera toujours si elle est active, mais sans le message promotionnel.
    -   **Valeur recommandée :** OUI, car c'est une fonctionnalité clé pour encourager une VMC plus élevée.
    -   **Scénario / exemple marchand :** Vous voulez encourager activement les clients à atteindre le niveau de remise suivant. L'activation de cette option leur montrera exactement combien ils doivent dépenser de plus.
-   **Contenus personnalisés supplémentaires**

    -   **Ce que fait ce paramètre :** Vous permet d'ajouter du texte personnalisé, du HTML ou même des images qui seront affichés avec les informations du programme de remise sur la page du panier. Ce contenu peut être traduit dans différentes langues.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque du contenu est saisi :* Votre message personnalisé apparaîtra sur la page du panier, améliorant le message promotionnel.
        -   *Lorsque laissé vide :* Aucun contenu personnalisé supplémentaire ne sera affiché.
    -   **Valeur recommandée :** Utilisez ceci pour ajouter un appel à l'action convaincant ou expliquer les avantages du programme de remise.
    -   **Scénario / exemple marchand :** Vous pourriez ajouter « Ne manquez pas les économies ! Plus vous achetez, plus vous économisez ! » ou un lien vers vos conditions générales de remise.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 AdminCdisListController (Back Office > Modules > Remise panier basée sur la valeur du panier > Bouton « Configurer », puis naviguez vers l'onglet « Remises » ou similaire)

Cet écran est l'endroit où vous définissez et gérez vos règles de remise réelles. Il est généralement accessible après avoir cliqué sur « Configurer » sur le module, puis en naviguant vers un onglet ou un lien spécifique pour « Remises » ou « Règles ».

-   **Nom de l'écran et emplacement du menu :** Cet écran est généralement accessible via un onglet ou un lien dédié dans la page de configuration principale du module, souvent intitulé « Remises », « Règles » ou « Gérer les remises ».
-   **Actions et paramètres disponibles :**
    -   **Vue Grille / Gestion :** Vous verrez un tableau listant toutes vos règles de remise définies. Chaque ligne représente une règle avec des colonnes comme :
        -   **Valeur minimale du panier :** Le seuil que le panier doit atteindre.
        -   **Type de remise :** S'il s'agit d'un pourcentage ou d'un montant fixe.
        -   **Valeur de la remise :** Le pourcentage (par exemple, 5) ou le montant fixe (par exemple, 10,00).
        -   **Actif :** Si la règle est actuellement activée.
        -   **Actions :** Boutons pour « Modifier » ou « Supprimer » des règles individuelles.
    -   **Bouton Ajouter une nouvelle règle :** Un bouton (par exemple, « Ajouter une nouvelle règle de remise ») pour créer une nouvelle condition de remise. Lorsque vous cliquez dessus, un formulaire s'ouvrira pour définir une nouvelle règle.
    -   **Formulaire de modification de règle :** Lors de l'ajout ou de la modification d'une règle, vous trouverez généralement des champs pour :
        -   **Valeur minimale du panier :** (par exemple, 500) - La valeur totale minimale du panier pour que cette remise s'applique.
        -   **Type de remise :** (par exemple, Pourcentage, Montant fixe) - Choisissez comment la remise est calculée.
        -   **Valeur de la remise :** (par exemple, 5 pour 5 %, ou 10,00 pour 10 €) - La remise réelle à appliquer.
        -   **Actif :** (Interrupteur Oui/Non) - Pour activer ou désactiver cette règle spécifique sans la supprimer.
        -   **Priorité :** (par exemple, 1, 2, 3) - Si plusieurs règles peuvent s'appliquer (par exemple, la valeur du panier est de 1000 €, et vous avez des règles pour 500 € et 1000 €), la priorité détermine laquelle prend le pas. Les nombres inférieurs signifient généralement une priorité plus élevée.
-   **Effet des changements :**
    -   **Ajout d'une règle :** Une nouvelle condition de remise devient active dans votre boutique, s'appliquant automatiquement aux paniers des clients qui répondent aux critères.
    -   **Modification d'une règle :** Modifie une condition de remise existante, changeant son seuil, sa valeur ou son statut actif.
    -   **Suppression d'une règle :** Supprime définitivement une condition de remise, et elle ne sera plus appliquée aux paniers.
    -   **Activation/Désactivation :** Bascule la disponibilité d'une règle de remise spécifique sans supprimer sa configuration.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Commencez par planifier vos niveaux de remise (par exemple, 250 € pour 2 %, 500 € pour 5 %, 1000 € pour 10 %).
    2.  Cliquez sur « Ajouter une nouvelle règle de remise » pour chaque niveau.
    3.  Saisissez la « Valeur minimale du panier », sélectionnez le « Type de remise » (généralement Pourcentage) et saisissez la « Valeur de la remise ».
    4.  Assurez-vous que « Actif » est défini sur OUI.
    5.  Définissez les priorités si vous avez des plages qui se chevauchent (par exemple, une règle pour >500 € et une autre pour >1000 €, assurez-vous que la règle de 1000 € a une priorité plus élevée si vous voulez qu'elle s'applique au lieu de la règle de 500 € lorsque le panier dépasse 1000 €). Le module gère généralement cela en appliquant la remise de la valeur la plus élevée pour le niveau le plus élevé atteint.
    6.  Examinez régulièrement vos règles de remise, surtout avant les grandes ventes ou les périodes promotionnelles, pour vous assurer qu'elles correspondent à votre stratégie marketing actuelle.

#### 2.2.2 index.php (cartdiscount/controllers/admin/index.php)

Ce fichier est un espace réservé et contient généralement uniquement une instruction de sécurité `die()` pour empêcher l'accès direct au répertoire. Il ne représente pas un écran configurable ou une vue de gestion d'entité pour le marchand.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Activer le programme | OUI | Interrupteur principal pour l'ensemble du programme de remise. |
|  | Désactiver le programme de remises sur le panier pour les groupes de clients sélectionnés | (Aucun sélectionné) | Exclut les groupes de clients choisis de recevoir des remises. |
|  | Type de prix | Prix TTC | Détermine si la valeur du panier inclut ou exclut la taxe pour le calcul. |
|  | Exclure les produits avec remise | OUI | Empêche les produits déjà remisés de contribuer au seuil de valeur du panier. |
|  | Exclure les produits du fabricant | (Aucun sélectionné) | Ignore les produits des fabricants sélectionnés pour le calcul de la valeur du panier. |
|  | Exclure les produits remisés de la valeur de la remise | OUI | Garantit que la remise sur le panier ne s'applique qu'aux articles non remisés du panier. |
|  | Exclure le panier avec code de bon de réduction | OUI | Empêche les remises du module si un code de bon de réduction séparé est utilisé. |
|  | Afficher les informations du programme de remise sur la page du panier | OUI | Affiche des messages promotionnels sur la page du panier. |
|  | Contenus personnalisés supplémentaires | (Vide) | Ajoute du texte/HTML personnalisé aux informations de remise de la page du panier. |
| **AdminCdisListController (Liste des remises)** | Valeur minimale du panier | (Définie par le marchand) | Le seuil total du panier pour déclencher une remise. |
|  | Type de remise | Pourcentage | Comment la remise est calculée (pourcentage ou montant fixe). |
|  | Valeur de la remise | (Définie par le marchand) | Le montant réel de la remise (par exemple, 5 pour 5 %, 10,00 pour 10 €). |
|  | Actif | OUI | Active ou désactive une règle de remise spécifique. |
|  | Priorité | (Auto/Définie par le marchand) | Détermine quelle règle s'applique si plusieurs seuils sont atteints. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : Mes remises ne s'appliquent pas, même si j'ai configuré des règles. Qu'est-ce qui ne va pas ?**
R :

1.  **Vérifiez « Activer le programme » :** Assurez-vous que l'interrupteur principal sur la page de configuration du module est réglé sur OUI.
2.  **Vérifiez le statut « Actif » de chaque règle individuelle :** Assurez-vous que chaque règle de remise que vous avez créée dans l'AdminCdisListController est également réglée sur OUI.
3.  **Videz le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). PrestaShop met souvent en cache les paramètres des modules.
4.  **Vérifiez les groupes de clients :** Vérifiez que le groupe de clients avec lequel vous testez n'est pas exclu sous « Désactiver le programme de remises sur le panier pour les groupes de clients sélectionnés ».
5.  **Seuil de valeur du panier :** Vérifiez à nouveau que la valeur de votre panier atteint bien la « Valeur minimale du panier » pour que la remise se déclenche.

**Q : La remise s'applique, mais le message sur la page du panier n'apparaît pas.**
R :

1.  **Vérifiez « Afficher les informations du programme de remise sur la page du panier » :** Assurez-vous que ce paramètre est activé (OUI) sur la page de configuration principale du module.
2.  **Compatibilité du thème :** Votre thème personnalisé pourrait remplacer l'affichage standard du panier. Vérifiez si le hook `displayShoppingCartFooter` est correctement implémenté dans le fichier `shopping-cart.tpl` de votre thème ou un fichier équivalent. Si ce n'est pas le cas, un développeur pourrait avoir besoin d'ajouter manuellement le hook.
3.  **Videz le cache :** Videz toujours votre cache PrestaShop après avoir effectué des modifications de configuration.

**Q : La valeur de la remise semble incorrecte, ou elle ne s'applique pas à tous les articles.**
R :

1.  **« Type de prix » :** Vérifiez si vous avez sélectionné « Prix TTC » ou « Prix HT » pour le calcul.
2.  **« Exclure les produits avec remise » :** Si activé, les produits déjà en promotion ne contribueront pas au seuil.
3.  **« Exclure les produits remisés de la valeur de la remise » :** Si activé, la remise en pourcentage ne s'appliquera qu'aux articles non remisés du panier. Passez en revue ces paramètres pour vous assurer qu'ils correspondent au comportement souhaité.
4.  **« Exclure le panier avec code de bon de réduction » :** Si un client a appliqué un bon de réduction séparé, et que ce paramètre est OUI, la remise du module ne s'appliquera pas.

**Q : Comment traduire le contenu personnalisé que j'ai ajouté ?**
R :

1.  Allez dans **International > Traductions** dans votre Back Office PrestaShop.
2.  Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez la langue que vous souhaitez traduire.
3.  Recherchez le module « Remise panier basée sur la valeur du panier ». Vous devriez voir des champs pour traduire les « Contenus personnalisés supplémentaires » pour chaque langue.

**Q : Je vois une erreur après la mise à jour de PrestaShop ou d'un autre module.**
R :

1.  **Vérifiez la version du module :** Assurez-vous d'utiliser la dernière version du module « Remise panier basée sur la valeur du panier » compatible avec votre version de PrestaShop. Téléchargez le bon ZIP depuis MyPresta.eu.
2.  **Compatibilité PHP :** Vérifiez que la version PHP de votre serveur se situe dans la plage prise en charge par le module (PHP 5.6 - 8.5).
3.  **Désactiver les overrides (pour les développeurs) :** Si vous suspectez un conflit, désactivez temporairement les overrides dans **Paramètres avancés > Performances** (définissez « Désactiver les modules non PrestaShop » sur OUI, puis videz le cache). Si le problème est résolu, il s'agit probablement d'un conflit d'override. Réactivez et consultez un développeur.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Remise panier basée sur la valeur du panier » étend les fonctionnalités de base de PrestaShop `Cart` et `CartRule` via des overrides pour appliquer dynamiquement des remises. Il utilise un contrôleur d'administration dédié (`AdminCdisListController`) pour gérer les règles de remise stockées dans une table de base de données personnalisée. L'intégration front-office est principalement réalisée via des hooks pour afficher des messages d'information et assurer l'application des remises pendant les processus de panier et de commande.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Aucun explicitement défini dans le répertoire `controllers/front/` du module. La logique front-office pour l'application des remises est gérée via des overrides et des hooks.
-   **Contrôleurs d'administration Back-Office** :

    -   `cartdiscount/controllers/admin/AdminCdisList.php`
        -   **Nom de la classe et classe parente :** `AdminCdisListController` étend `ModuleAdminController`.
        -   **Nom de l'onglet et entité gérée :** Gère la liste et les formulaires des entités `Cdis` (Remise Panier). Ce contrôleur fournit l'interface pour créer, modifier et supprimer les règles de remise échelonnées. Il définit la vue de liste (`renderList()`) et la vue de formulaire (`renderForm()`) pour les règles de remise.
    -   `cartdiscount/controllers/admin/index.php`
        -   **Nom de la classe et classe parente :** N/A (fichier de sécurité).
        -   **Responsabilité :** Contient une instruction `die('No direct script access allowed');` pour empêcher l'accès direct au répertoire, une pratique de sécurité standard de PrestaShop.

### 4.3 Classes et modèles de base (`classes/`)

Le module s'appuie fortement sur des overrides pour injecter sa logique dans les classes PrestaShop de base.

-   `cartdiscount/override/classes/Cart.php`
    -   **Classe originale :** `Cart`
    -   **Responsabilité :** Cet override est crucial. Il étend la classe `Cart` pour modifier la façon dont les totaux du panier sont calculés, spécifiquement pour appliquer les remises dynamiques basées sur les règles du module. Il intercepte probablement des méthodes comme `getProducts()`, `getProductsTotal()`, ou `getPackageShippingCost()` pour ajuster les prix avant qu'ils ne soient finalisés. Il contient également une logique pour déterminer si une remise doit être appliquée en fonction de la valeur actuelle du panier et des règles configurées.
-   `cartdiscount/override/classes/CartRule.php`
    -   **Classe originale :** `CartRule`
    -   **Responsabilité :** Cet override étend probablement la classe `CartRule` pour permettre au module de créer et de gérer ses propres objets `CartRule` internes dynamiquement. Lorsque le module applique une remise, cela se fait souvent en créant une `CartRule` temporaire ou spécifique qui reflète la remise calculée, qui est ensuite appliquée au panier. Cet override assure la compatibilité et la gestion appropriée de ces règles générées dynamiquement.
-   `cartdiscount/override/classes/index.php`
    -   **Responsabilité :** Fichier de sécurité, `die('No direct script access allowed');`.
-   `cartdiscount/override/classes/order/index.php`
    -   **Responsabilité :** Fichier de sécurité, `die('No direct script access allowed');`.
-   `cartdiscount/override/classes/order/Order.php`
    -   **Classe originale :** `Order`
    -   **Responsabilité :** Cet override garantit que les remises appliquées par le module sont correctement reportées et stockées lors de la passation d'une commande. Il peut modifier les méthodes liées à la création de commande ou au calcul du total pour refléter les règles de panier appliquées.

### 4.4 Actifs JavaScript (`views/js/`)

-   `cartdiscount/views/admin/js/cdis.js`
    -   **Portée :** Back-office.
    -   **Responsabilité :** Ce script gère probablement les interactions côté client pour l'`AdminCdisListController`. Cela pourrait inclure :
        -   Appels AJAX pour l'enregistrement/la mise à jour des règles de remise.
        -   Validation de formulaire pour le formulaire « Ajouter/Modifier une règle de remise ».
        -   Mises à jour dynamiques de l'interface utilisateur ou interactions au sein de la grille de gestion des règles de remise.
        -   Potentiellement, la gestion des champs « Exclure les produits du fabricant » ou d'autres champs de sélection dynamique.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `cartdiscount/views/admin/css/cdis.css`
    -   **Portée :** Style du formulaire d'administration du Back-office.
    -   **Responsabilité :** Fournit un style spécifique pour l'interface `AdminCdisListController`, garantissant que les formulaires et les listes de gestion des règles de remise sont bien présentés et cohérents avec l'interface utilisateur du Back-office de PrestaShop.
    -   **Sélecteurs de classe CSS clés :** Les développeurs peuvent inspecter le HTML généré par `AdminCdisListController` pour trouver des classes spécifiques (par exemple, `.cdis-form`, `.cdis-list-table`) à override si un style d'administration personnalisé est nécessaire.
-   `cartdiscount/views/css/cartdiscount.css`
    -   **Portée :** Style client Front-office.
    -   **Responsabilité :** Style les messages d'information affichés sur la page du panier (par exemple, « Dépensez X de plus pour Y % de remise ! »).
    -   **Sélecteurs de classe CSS clés :** Cible probablement des éléments dans le template `myDiscount.tpl` (par exemple, `.cartdiscount-info`, `.cartdiscount-message`, `.cartdiscount-progress`). Les développeurs peuvent override ces classes dans le fichier `custom.css` de leur thème ou équivalent pour correspondre à l'image de marque de la boutique.

### 4.6 Structure du template Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :
    -   `cartdiscount/views/templates/hook/myDiscount.tpl`
        -   **Hook :** `displayShoppingCartFooter` (et potentiellement d'autres comme `displayHeader` pour l'inclusion de JS/CSS).
        -   **Bloc visuel :** Ce template est responsable du rendu des messages dynamiques sur la page du panier d'achat. Il affiche des informations sur la valeur actuelle du panier, la remise appliquée et le montant que le client doit dépenser pour atteindre le niveau de remise suivant. Il rend également les « Contenus personnalisés supplémentaires » si configurés.
-   **Templates d'administration (`views/templates/admin/`)** :
    -   L'`AdminCdisListController` utilisera les templates d'administration standard de PrestaShop pour le rendu de ses vues de liste et de formulaire, généralement trouvés dans `_partials` ou `helpers/list/list_header.tpl`, `helpers/form/form.tpl`, etc., qui font partie du cœur de PrestaShop. Le module lui-même pourrait ne pas avoir de fichiers `.tpl` personnalisés dans `views/templates/admin/` mais s'appuie plutôt sur le contrôleur pour transmettre les données aux helpers de base.
-   **Templates Front-office (`views/templates/front/`)** : Aucun explicitement défini.
-   `cartdiscount/lib/searchTool/views/scripts.tpl`
    -   **Portée :** Probablement utilisé pour inclure des actifs JavaScript ou CSS pour un composant d'outil de recherche dans la configuration du module ou une fonctionnalité spécifique. Son utilisation exacte dépendrait de l'implémentation de l'outil de recherche (par exemple, pour sélectionner les fabricants à exclure).

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :

    -   `ps_cdis` : Cette table personnalisée stocke les règles de remise réelles définies par le marchand (valeur minimale du panier, type de remise, valeur de la remise, statut actif, priorité).
    -   `ps_configuration` : Les paramètres du module comme `CDIS_ACTIVE`, `CDIS_PRICETYPE`, `CDIS_GROUPSNOT`, `CDIS_EXMANUFACTURER`, `CDIS_SHOWINFO_CART`, `CDIS_EXSPECIFIC`, `CDIS_ORDERCOUPON`, `cdis_contents` (pour le contenu personnalisé) et `mypresta_updates` y sont stockés.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page front-office. | Utilisé pour inclure le CSS front-office du module (`cartdiscount.css`) et potentiellement du JavaScript, garantissant que les styles et les scripts sont chargés pour la page du panier. |
| `ActionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration est initialisé et que ses médias (JS/CSS) sont définis. | Utilisé pour inclure le CSS back-office du module (`cdis.css`) et le JavaScript (`cdis.js`) pour l'`AdminCdisListController`, assurant un style et une fonctionnalité appropriés de l'interface d'administration. |
| `displayShoppingCartFooter` | En bas de la page de récapitulatif du panier d'achat. | Rend le template `myDiscount.tpl`, affichant des messages d'information sur le programme de remise, les économies actuelles et les prochains niveaux de remise au client. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Remise panier basée sur la valeur du panier », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
