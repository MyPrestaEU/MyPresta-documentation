---
title: "Partage de produit Twitter + code de réduction - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Partage de produit Twitter + code de réduction' par MyPresta.eu."
sidebar:
  label: "Partage de produit Twitter + code de réduction - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Twitter product share + voucher code sur MyPresta.eu](https://mypresta.eu/modules/social-networks/twitter-product-share-voucher-code.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/twitter-product-share-voucher-code/)
>
> ---


# Partage de produit Twitter + code de réduction

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop et sont habituellement activées par défaut sur la plupart des environnements d'hébergement.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module « Partage de produit Twitter + code de réduction », accessible après l'installation en cliquant sur le bouton « Configurer ». Ici, vous définirez le comportement du bouton de partage et la manière dont les codes de réduction sont générés.

#### **Paramètres généraux**

-   **Activer le module :**

    *   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver l'ensemble du module.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé (OUI) :* Le bouton de partage Twitter apparaîtra sur vos pages produit (selon votre sélection de hook), et le système de génération de codes de réduction sera actif.
        *   *Lorsqu'il est désactivé (NON) :* Le bouton de partage Twitter n'apparaîtra pas, et aucun code de réduction ne sera généré pour les partages.
    *   **Valeur recommandée :** OUI (pour activer la fonctionnalité du module).
    *   **Scénario / exemple marchand :** Si vous configurez le module pour la première fois ou effectuez une maintenance, vous pourriez le désactiver temporairement. Sinon, gardez-le activé pour bénéficier du partage social.
-   **Hook pour afficher le bouton :**

    *   **Ce que fait ce paramètre :** Détermine l'emplacement visuel du bouton de partage Twitter sur vos pages produit.
    *   **Effet de la modification de ce paramètre :**
        *   *Options (exemples) :* `displayProductButtons`, `displayRightColumnProduct`, `displayFooterProduct`, `displayProductExtraContent`.
        *   *Lorsqu'il est défini sur `displayProductButtons` (courant) :* Le bouton apparaîtra probablement près du bouton « Ajouter au panier » ou du sélecteur de quantité de produit.
        *   *Lorsqu'il est défini sur `displayRightColumnProduct` :* Le bouton apparaîtra dans la colonne de droite de votre page produit (si votre thème en a une).
        *   *Lorsqu'il est défini sur `displayFooterProduct` :* Le bouton apparaîtra dans la section du pied de page du produit.
    *   **Valeur recommandée :** `displayProductButtons` ou `displayProductExtraContent` pour une visibilité et un engagement maximum, car ceux-ci sont généralement proches des informations principales du produit.
    *   **Scénario / exemple marchand :** Vous pourriez tester différents hooks pour voir quel emplacement génère le plus de partages sur votre thème spécifique. Un emplacement proéminent est généralement le meilleur.
-   **Nombre de partages requis pour un bon de réduction :**

    *   **Ce que fait ce paramètre :** Définit le nombre de partages de produits uniques qu'un client doit effectuer avant de recevoir un bon de réduction.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur 1 :* Un client reçoit un bon de réduction immédiatement après son premier partage.
        *   *Lorsqu'il est défini sur 3 :* Un client doit partager trois produits différents (ou le même produit trois fois, selon la logique interne) avant qu'un bon de réduction ne soit émis.
    *   **Valeur recommandée :** 1 (pour encourager l'action immédiate et la récompense) ou 2 (pour encourager un peu plus d'engagement sans être trop exigeant).
    *   **Scénario / exemple marchand :** Si vous voulez faciliter l'obtention d'une réduction pour les clients, définissez-le sur 1. Si vous voulez encourager un partage plus étendu, définissez-le plus haut, mais sachez qu'un nombre plus élevé pourrait réduire la participation.

#### **Paramètres du code de réduction**

-   **Préfixe du code de réduction :**

    *   **Ce que fait ce paramètre :** Une chaîne de caractères personnalisée qui apparaîtra au début de chaque code de réduction généré.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur `TWITTER-` :* Un code de réduction pourrait ressembler à `TWITTER-ABCDE123`.
        *   *Lorsqu'il est laissé vide :* Le code de réduction sera composé de caractères purement aléatoires.
    *   **Valeur recommandée :** `TWITTER-` ou `SHARE-` pour identifier facilement la source du bon de réduction.
    *   **Scénario / exemple marchand :** L'utilisation d'un préfixe vous aide à suivre quelles campagnes marketing génèrent des bons de réduction spécifiques dans vos rapports de vente PrestaShop.
-   **Valeur du code de réduction (pourcentage) :**

    *   **Ce que fait ce paramètre :** Le pourcentage de réduction appliqué par le code de réduction généré.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur 10 :* Le bon de réduction donnera une remise de 10 % sur la commande du client.
        *   *Lorsqu'il est défini sur 5 :* Le bon de réduction donnera une remise de 5 %.
    *   **Valeur recommandée :** 5-15 % (selon vos marges bénéficiaires et le niveau d'incitation souhaité).
    *   **Scénario / exemple marchand :** Une réduction de 10 % est souvent un bon équilibre entre l'attrait pour les clients et le maintien de la rentabilité.
-   **Validité du code de réduction (jours) :**

    *   **Ce que fait ce paramètre :** Le nombre de jours pendant lesquels le code de réduction généré sera valide à partir du moment où il est émis.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur 7 :* Le bon de réduction expirera 7 jours après que le client l'ait reçu.
        *   *Lorsqu'il est défini sur 30 :* Le bon de réduction sera valide pendant un mois.
    *   **Valeur recommandée :** 7-14 jours (pour créer un sentiment d'urgence sans être trop restrictif).
    *   **Scénario / exemple marchand :** Une période de validité plus courte encourage les clients à effectuer un achat plus tôt que tard, les empêchant d'oublier le bon de réduction.
-   **Montant minimum pour que le bon de réduction soit valide :**

    *   **Ce que fait ce paramètre :** Le montant total minimum de la commande (avant expédition) requis pour que le client puisse utiliser le bon de réduction.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur 50 :* Le bon de réduction ne peut être utilisé que si le total du panier du client est de 50 € ou plus.
        *   *Lorsqu'il est défini sur 0 (ou vide) :* Le bon de réduction peut être utilisé sur n'importe quel montant de commande.
    *   **Valeur recommandée :** Un montant raisonnable qui encourage un achat légèrement plus important, ou 0 si vous souhaitez l'autoriser sur n'importe quelle commande.
    *   **Scénario / exemple marchand :** Si votre valeur moyenne de commande est de 40 €, définir un minimum de 50 € pourrait encourager les clients à ajouter un autre article à leur panier pour atteindre le seuil et utiliser la réduction.
-   **Description du code de réduction :**

    *   **Ce que fait ce paramètre :** Une courte description textuelle qui sera associée au code de réduction dans votre back office PrestaShop (et potentiellement visible par le client dans son compte s'il consulte ses bons de réduction).
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur « Réduction Partage Twitter » :* Ce texte apparaîtra dans les détails du bon de réduction.
    *   **Valeur recommandée :** « Réduction pour Partage Twitter » ou « Merci d'avoir partagé sur Twitter ! »
    *   **Scénario / exemple marchand :** Cela vous aide, vous et vos clients, à comprendre l'origine du bon de réduction.
-   **Nom du code de réduction :**

    *   **Ce que fait ce paramètre :** Le nom interne de la règle de bon de réduction dans PrestaShop. Ceci est principalement pour votre organisation interne.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur « Coupon Partage Twitter » :* Ce nom apparaîtra dans votre section « Règles panier » de PrestaShop.
    *   **Valeur recommandée :** « Coupon Partage Twitter » ou « Réduction Partage Social ».
    *   **Scénario / exemple marchand :** Un nom clair facilite la recherche et la gestion de ces bons de réduction générés automatiquement dans votre administration PrestaShop.

#### **Paramètres du texte de partage Twitter**

-   **Texte de partage par défaut :**
    *   **Ce que fait ce paramètre :** Le texte par défaut qui sera pré-rempli dans la fenêtre contextuelle de partage Twitter lorsqu'un client clique sur le bouton de partage. Ce texte sera combiné avec le nom du produit et le lien.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur « Découvrez ce produit génial ! » :* Le tweet pourrait ressembler à « Découvrez ce produit génial ! [Nom du produit] [Lien du produit] ».
    *   **Valeur recommandée :** Quelque chose d'engageant comme « Découvrez ce produit incroyable de [Nom de votre boutique] ! » ou « Je viens de trouver ce super produit ! »
    *   **Scénario / exemple marchand :** Un texte par défaut attrayant encourage plus de clics et d'engagement de la part des abonnés du client.

#### **Bouton Enregistrer**

-   **Enregistrer :**
    *   **Ce que fait ce bouton :** Applique toutes les modifications que vous avez apportées sur cette page de configuration.
    *   **Effet de cliquer sur ce bouton :** Vos paramètres sont enregistrés dans la base de données, et le comportement du module se mettra à jour immédiatement sur votre front office.
    *   **Action recommandée :** Cliquez toujours sur « Enregistrer » après avoir effectué des modifications.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer le module | OUI | Active/désactive le module. |
| | Hook pour afficher le bouton | `displayProductButtons` | Contrôle l'emplacement du bouton de partage sur les pages produit. |
| | Nombre de partages requis pour un bon de réduction | 1 | Nombre de partages avant qu'un client n'obtienne un bon de réduction. |
| | Préfixe du code de réduction | `TWITTER-` | Ajoute un préfixe personnalisé aux codes de réduction générés. |
| | Valeur du code de réduction (pourcentage) | 10 | Le pourcentage de réduction du bon de réduction. |
| | Validité du code de réduction (jours) | 7-14 | Durée de validité du bon de réduction après génération. |
| | Montant minimum pour que le bon de réduction soit valide | 0 (ou montant raisonnable) | Total minimum du panier requis pour utiliser le bon de réduction. |
| | Description du code de réduction | « Réduction pour Partage Twitter » | Description interne du bon de réduction. |
| | Nom du code de réduction | « Coupon Partage Twitter » | Nom interne de la règle de bon de réduction. |
| | Texte de partage par défaut | « Découvrez ce produit incroyable ! » | Texte pré-rempli pour la fenêtre contextuelle de partage Twitter. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Le bouton de partage Twitter n'apparaît pas sur mes pages produit.**

-   **R :** Tout d'abord, assurez-vous que le module est **activé** dans sa configuration. Deuxièmement, vérifiez le paramètre **« Hook pour afficher le bouton »**. Votre thème pourrait ne pas afficher le hook choisi à un emplacement visible, ou le hook pourrait ne pas exister. Essayez de passer à un autre hook courant comme `displayProductButtons` ou `displayProductExtraContent`. S'il n'apparaît toujours pas, votre thème pourrait nécessiter une intégration personnalisée pour certains hooks, ou il pourrait y avoir un conflit.
-   **Conseil de pro :** Videz votre cache PrestaShop (Paramètres avancés > Performances) après avoir effectué des modifications aux paramètres du module ou aux fichiers de thème.

**Q2 : Les clients partagent, mais ils ne reçoivent pas de codes de réduction.**

-   **R :**
    1.  **Vérifiez « Nombre de partages requis pour un bon de réduction » :** Est-il défini sur 1 ? S'il est plus élevé, les clients doivent partager plus de fois avant d'obtenir un bon de réduction.
    2.  **Vérifiez les paramètres du bon de réduction :** Assurez-vous que « Valeur du code de réduction (pourcentage) » est défini sur un nombre supérieur à 0, et que « Validité du code de réduction (jours) » est également défini.
    3.  **Règles panier PrestaShop :** Vérifiez votre Back Office PrestaShop sous **Catalogue > Réductions > Règles panier**. Vous devriez voir des bons de réduction générés automatiquement avec le nom que vous avez spécifié (par exemple, « Coupon Partage Twitter »). Si aucune nouvelle règle n'apparaît, il pourrait y avoir un problème avec la logique de génération du bon de réduction.
-   **Conseil de pro :** Testez le processus vous-même. Partagez un produit de votre boutique en étant connecté en tant que client et voyez si un bon de réduction est généré.

**Q3 : La fenêtre contextuelle de partage Twitter semble étrange ou ne fonctionne pas correctement.**

-   **R :** Cela est souvent dû à des conflits JavaScript avec d'autres modules ou votre thème.
    1.  **Vérifiez la console du navigateur :** Ouvrez les outils de développement de votre navigateur (généralement F12) et recherchez les erreurs dans l'onglet « Console » lorsque vous cliquez sur le bouton de partage.
    2.  **Conflits de modules :** Désactivez temporairement les autres modules qui ajoutent du JavaScript aux pages produit (en particulier les modules de partage social ou de fenêtre contextuelle) pour voir si le problème est résolu.
-   **Conseil de pro :** Assurez-vous que votre installation PrestaShop et votre thème sont à jour. Des composants obsolètes peuvent parfois provoquer des conflits inattendus.

**Q4 : Puis-je personnaliser l'apparence du bouton de partage ?**

-   **R :** Le module utilise son propre CSS (`twittercoupon/css.css` et `twittercoupon/css/css.css`). Vous pouvez remplacer ces styles dans le fichier CSS personnalisé de votre thème. Inspectez le bouton à l'aide des outils de développement de votre navigateur pour identifier ses classes CSS, puis ajoutez vos styles personnalisés au fichier `custom.css` de votre thème ou à un fichier équivalent.
-   **Conseil de pro :** Évitez de modifier directement les fichiers CSS du module, car vos modifications seront perdues lors des mises à jour du module. Utilisez toujours les capacités CSS personnalisées de votre thème.

**Q5 : Comment le module prévient-il les abus (par exemple, quelqu'un qui partage à plusieurs reprises pour obtenir plusieurs bons de réduction) ?**

-   **R :** Le module suit généralement les partages par client (souvent par adresse IP ou ID client si connecté) pour empêcher un seul utilisateur de générer un nombre illimité de bons de réduction. Le paramètre « Nombre de partages requis pour un bon de réduction » aide également à gérer cela. Pour une prévention de la fraude plus avancée, vous pourriez avoir besoin de modules de sécurité PrestaShop supplémentaires.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Partage de produit Twitter + code de réduction » (`twittercoupon`) est un module PrestaShop standard principalement implémenté dans son fichier PHP principal, `ajax_twittercoupon.php`. Il utilise le système de hooks de PrestaShop pour l'affichage en front-office et la classe `Configuration` pour le stockage des paramètres. Le module génère dynamiquement des objets `CartRule` (bons de réduction) basés sur les actions de l'utilisateur. Sa fonctionnalité front-office repose sur JavaScript pour interagir avec l'API Twitter et un point d'accès AJAX au sein du module pour traiter les partages et émettre des bons de réduction.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs front-office ou back-office dédiés dans le répertoire `controllers/`. Toutes les requêtes AJAX du front-office et la gestion de la configuration du back-office sont gérées directement dans le fichier principal du module, `ajax_twittercoupon.php`, spécifiquement via sa méthode `getContent()` pour la configuration et une distribution AJAX personnalisée pour le traitement des partages.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit pas de classes personnalisées ni n'étend `ObjectModel` dans un répertoire `classes/` dédié. La logique principale de génération des bons de réduction interagit directement avec les classes `CartRule` et `Configuration` de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

Le module inclut des fichiers JavaScript pour gérer les interactions du front-office.

-   `twittercoupon/lib/voucherengine/script.js`
    *   **Portée :** Front-office.
    *   **Responsabilité :** Il semble s'agir du script principal responsable de la logique côté client du module. Il gère probablement :
        *   La liaison des événements de clic au bouton de partage Twitter.
        *   L'ouverture de la fenêtre contextuelle de partage Twitter (en utilisant l'API Web Intent de Twitter).
        *   La détection des partages réussis (éventuellement via des rappels ou un sondage).
        *   L'envoi d'appels AJAX au backend du module pour enregistrer le partage et demander un bon de réduction.
        *   L'affichage du code de réduction à l'utilisateur après une génération réussie.
        *   Peut inclure une logique pour empêcher plusieurs partages du même utilisateur dans un court laps de temps ou pour suivre le nombre de partages.
-   `twittercoupon/trusted.js`
    *   **Portée :** Front-office.
    *   **Responsabilité :** Le nom « trusted.js » suggère qu'il pourrait être lié à la sécurité, au suivi ou à l'intégrité du processus de partage. Il pourrait potentiellement gérer :
        *   La validation côté client avant d'initier un partage.
        *   Le suivi des interactions de l'utilisateur pour des mesures anti-fraude.
        *   L'intégration avec d'autres scripts de suivi ou d'analyse.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module fournit des fichiers CSS pour styliser les éléments du front-office.

-   `twittercoupon/css.css`
    *   **Portée :** Style client du front-office.
    *   **Responsabilité :** Contient les styles principaux pour le bouton de partage Twitter, toutes les fenêtres contextuelles associées ou les messages affichés au client.
    *   **Sélecteurs de classe CSS clés :** Les développeurs doivent inspecter le HTML rendu pour identifier les classes spécifiques (par exemple, `.twitter-share-button`, `.twitter-coupon-message`) à remplacer dans le `custom.css` de leur thème.
-   `twittercoupon/css/css.css`
    *   **Portée :** Style client du front-office.
    *   **Responsabilité :** Ce fichier semble être un doublon ou un chemin alternatif pour le CSS principal. Il est courant que les modules aient des chemins redondants ou que l'un soit un fallback. Les développeurs doivent vérifier lequel est réellement chargé dans le navigateur.
    *   **Sélecteurs de classe CSS clés :** Identiques à ci-dessus.

### 4.6 Structure des templates Smarty (`views/templates/`)

Le module utilise des templates Smarty pour rendre son contenu front-office.

-   **Templates de hook (`views/templates/hook/`)** :
    *   `twittercoupon/share.tpl`
        *   **Hook :** Ce template est rendu dans le hook choisi dans la configuration du module (par exemple, `displayProductButtons`, `displayRightColumnProduct`, `displayFooterProduct`).
        *   **Objectif :** Il affiche le HTML du bouton « Partager sur Twitter » et potentiellement un espace réservé pour le message du code de réduction ou un déclencheur modal. Il inclura probablement des variables pour le nom du produit, l'URL du produit et le texte de partage par défaut.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :

    *   Le module stocke principalement ses paramètres de configuration dans la table `ps_configuration` de PrestaShop.
        *   `PS_TWITTERCOUPON_ENABLED` (booléen)
        *   `PS_TWITTERCOUPON_HOOK` (chaîne)
        *   `PS_TWITTERCOUPON_SHARES_REQUIRED` (entier)
        *   `PS_TWITTERCOUPON_PREFIX` (chaîne)
        *   `PS_TWITTERCOUPON_VALUE` (flottant)
        *   `PS_TWITTERCOUPON_VALIDITY` (entier)
        *   `PS_TWITTERCOUPON_MIN_AMOUNT` (flottant)
        *   `PS_TWITTERCOUPON_DESCRIPTION` (chaîne)
        *   `PS_TWITTERCOUPON_NAME` (chaîne)
        *   `PS_TWITTERCOUPON_DEFAULT_TEXT` (chaîne)
    *   Il utilise également probablement une table personnalisée (par exemple, `ps_twittercoupon_shares` ou similaire) pour suivre les partages individuels des clients (par `id_customer` ou `ip_address`, `id_product`) et prévenir les abus, bien qu'aucun fichier SQL explicite n'ait été listé, cette logique serait gérée dans la méthode `install()` du module principal. Cette table suivrait :
        *   `id_customer` (si connecté)
        *   `ip_address`
        *   `id_product`
        *   `share_date`
        *   `voucher_issued` (booléen)
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Pour charger les actifs CSS et JavaScript du module (`twittercoupon/css.css`, `twittercoupon/lib/voucherengine/script.js`, `twittercoupon/trusted.js`). |
| `displayProductButtons` | Sur la page produit, généralement près du bouton d'ajout au panier. | Pour afficher le bouton de partage Twitter (`share.tpl`). |
| `displayRightColumnProduct` | Sur la page produit, dans la colonne de droite. | Hook alternatif pour afficher le bouton de partage Twitter (`share.tpl`). |
| `displayFooterProduct` | Sur la page produit, dans la zone du pied de page. | Hook alternatif pour afficher le bouton de partage Twitter (`share.tpl`). |
| `displayProductExtraContent` | Sur la page produit, souvent sous la description principale du produit. | Hook alternatif pour afficher le bouton de partage Twitter (`share.tpl`). |
| `actionFrontControllerSetMedia` | Avant qu'un contrôleur frontal ne rende son contenu, permettant aux modules d'ajouter des actifs. | Pour charger les actifs CSS et JavaScript du module de manière conditionnelle en fonction de la page. |
| (Appel AJAX interne) | Déclenché par JavaScript lors d'un événement de partage. | Pour traiter le partage, mettre à jour le nombre de partages et générer une `CartRule` (bon de réduction) si les conditions sont remplies. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support technique dédié pour le module « Partage de produit Twitter + code de réduction », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe s'engage à fournir une assistance rapide et à assurer la performance optimale de votre module.
