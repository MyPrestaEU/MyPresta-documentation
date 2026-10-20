---
title: "Partage de produit Facebook + code de réduction - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Partage de produit Facebook + code de réduction' par MyPresta.eu."
sidebar:
  label: "Partage de produit Facebook + code de réduction"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Facebook product share + discount code sur MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-product-share-discount-code.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/facebook-product-share-discount-code/)
>
> ---


# Partage de produit Facebook + code de réduction

## 1. Exigences et compatibilité
-   **Versions PrestaShop prises en charge :** PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x
-   **Compatibilité PHP :** PHP 5.6 - 8.5
-   **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop et sont habituellement disponibles sur la plupart des environnements d'hébergement.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Après l'installation, naviguez vers **Modules > Gestionnaire de modules** et cliquez sur "Configurer" à côté de "Partage de produit Facebook + code de réduction". Cet écran vous permet de contrôler la fonctionnalité et l'apparence principales du module.

#### **Paramètres généraux**

-   **Activer / Désactiver le module :**
    -   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour l'ensemble du module.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Le bouton de partage Facebook apparaîtra sur les pages produit, et la fonctionnalité de code de réduction sera active.
        -   *Lorsqu'il est désactivé :* Le module sera complètement inactif. Le bouton de partage n'apparaîtra pas, et aucun code de réduction ne sera généré.
    -   **Valeur recommandée :** OUI (pour activer les fonctionnalités du module).
    -   **Scénario / exemple de marchand :** Si vous configurez le module pour la première fois ou effectuez une maintenance, vous pouvez le désactiver temporairement. Une fois prêt, activez-le pour commencer à générer des partages et des réductions.

-   **ID d'application Facebook :**
    -   **Ce que fait ce paramètre :** Ce champ nécessite votre ID d'application Facebook unique. Cet ID est crucial pour que Facebook identifie correctement votre site web et suive les partages. Vous devez créer une application Facebook sur la plateforme Facebook Developers (developers.facebook.com) pour obtenir cet ID.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est correctement saisi :* Le module communiquera correctement avec Facebook, permettant le suivi des partages et le fonctionnement du mécanisme de réduction.
        -   *Lorsqu'il est incorrect ou vide :* La fonctionnalité de partage Facebook peut ne pas fonctionner, ou les partages peuvent ne pas être suivis, empêchant l'émission de codes de réduction.
    -   **Valeur recommandée :** Votre ID d'application Facebook valide (par exemple, `123456789012345`).
    -   **Scénario / exemple de marchand :** Vous avez créé une application Facebook pour votre boutique. Copiez l'ID d'application depuis votre tableau de bord Facebook Developer et collez-le ici. C'est une configuration unique.

-   **Type de réduction :**
    -   **Ce que fait ce paramètre :** Détermine le type de réduction que les clients reçoivent après le partage.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur "Pourcentage" :* Le code de réduction offrira un pourcentage de réduction sur le total de la commande (par exemple, 10 % de réduction).
        -   *Lorsqu'il est défini sur "Montant" :* Le code de réduction offrira une valeur monétaire fixe de réduction sur le total de la commande (par exemple, 5 € de réduction).
    -   **Valeur recommandée :** "Pourcentage" ou "Montant" en fonction de votre stratégie marketing.
    -   **Scénario / exemple de marchand :** Si vous souhaitez encourager des commandes plus importantes, une réduction en pourcentage pourrait être plus attrayante. Pour des achats plus petits et fréquents, un montant fixe pourrait être plus efficace.

-   **Valeur de la réduction :**
    -   **Ce que fait ce paramètre :** Spécifie la valeur réelle de la réduction.
    -   **Effet de la modification de ce paramètre :**
        -   *Si le "Type de réduction" est Pourcentage :* Saisissez la valeur en pourcentage (par exemple, `10` pour 10 %).
        -   *Si le "Type de réduction" est Montant :* Saisissez la valeur monétaire (par exemple, `5.00` pour 5 €).
    -   **Valeur recommandée :** Une valeur attrayante pour les clients mais également rentable pour votre entreprise (par exemple, `10` pour 10 % de réduction, ou `5.00` pour 5 € de réduction).
    -   **Scénario / exemple de marchand :** Vous décidez d'offrir une réduction de 15 % pour le partage. Vous définirez "Type de réduction" sur "Pourcentage" et "Valeur de la réduction" sur `15`.

-   **Montant minimum pour la réduction :**
    -   **Ce que fait ce paramètre :** Définit un total de commande minimum (avant expédition) que le client doit atteindre pour utiliser le code de réduction généré.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'une valeur est saisie (par exemple, `50.00`) :* Le code de réduction ne sera valide que si le total du panier du client est égal ou supérieur à ce montant.
        -   *Lorsqu'il est laissé vide ou défini sur `0` :* Le code de réduction peut être utilisé sur n'importe quelle commande, quelle que soit sa valeur totale.
    -   **Valeur recommandée :** Une valeur qui encourage les clients à ajouter plus d'articles à leur panier, ou `0` si vous ne voulez pas de minimum.
    -   **Scénario / exemple de marchand :** Pour éviter que les clients n'utilisent une réduction de 10 % sur un article à 1 €, vous pouvez définir un montant minimum de `25.00 €`.

-   **Validité du code de réduction (en jours) :**
    -   **Ce que fait ce paramètre :** Définit le nombre de jours pendant lesquels le code de réduction généré sera valide à partir du moment de son émission.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'une valeur est saisie (par exemple, `7`) :* Le code de réduction expirera après 7 jours, créant un sentiment d'urgence.
        -   *Lorsqu'il est laissé vide ou défini sur `0` :* Le code de réduction n'aura pas de date d'expiration (non recommandé, car cela réduit l'urgence).
    -   **Valeur recommandée :** `7` à `30` jours pour encourager une utilisation rapide.
    -   **Scénario / exemple de marchand :** Vous souhaitez que les clients utilisent leur réduction rapidement. Définir cette valeur sur `7` jours les incitera à effectuer un achat dans la semaine.

-   **Préfixe du code de réduction :**
    -   **Ce que fait ce paramètre :** Vous permet d'ajouter un préfixe personnalisé à tous les codes de réduction générés. Cela vous aide à identifier les codes générés par ce module dans votre gestion des réductions PrestaShop.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'un préfixe est saisi (par exemple, `FBSHARE-`) :* Tous les codes générés commenceront par ce préfixe (par exemple, `FBSHARE-XYZ123`).
        -   *Lorsqu'il est laissé vide :* Les codes seront générés sans préfixe spécifique.
    -   **Valeur recommandée :** Un préfixe court et descriptif (par exemple, `FB-`, `SHARE-`, `SOCIAL-`).
    -   **Scénario / exemple de marchand :** Pour suivre facilement le succès de votre campagne de partage Facebook, vous pouvez utiliser `FB2023-` comme préfixe.

-   **Afficher le bouton de partage sur :**
    -   **Ce que fait ce paramètre :** Détermine où le bouton de partage Facebook apparaîtra sur vos pages produit. Il s'agit généralement d'une liste déroulante ou d'une sélection par bouton radio.
    -   **Effet de la modification de ce paramètre :**
        -   *En-tête :* Le bouton apparaît dans l'en-tête de la boutique (moins courant pour les partages spécifiques aux produits).
        -   *Colonnes (Gauche/Droite) :* Le bouton apparaît dans l'une des colonnes latérales.
        -   *Page produit (Contenu principal) :* Le bouton apparaît dans la zone d'informations principales du produit (le plus courant et recommandé).
        -   *Pied de page :* Le bouton apparaît dans le pied de page de la boutique.
    -   **Valeur recommandée :** "Page produit (Contenu principal)" pour une visibilité et une pertinence maximales.
    -   **Scénario / exemple de marchand :** Vous souhaitez que le bouton de partage soit facilement visible juste à côté de l'image et de la description du produit. La sélection de "Page produit (Contenu principal)" garantit cela.

-   **Texte du bouton de partage :**
    -   **Ce que fait ce paramètre :** Vous permet de personnaliser le texte affiché sur le bouton de partage Facebook.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'un texte est saisi (par exemple, "Partager et obtenir une réduction !") :* Le bouton affichera votre texte personnalisé.
        -   *Lorsqu'il est laissé vide :* Un texte par défaut (par exemple, "Partager sur Facebook") sera utilisé.
    -   **Valeur recommandée :** Un texte clair et orienté vers l'action qui met en évidence l'avantage (par exemple, "Partager pour une réduction !", "Obtenez X% de réduction - Partagez maintenant !").
    -   **Scénario / exemple de marchand :** Pour inciter les clients, vous pouvez modifier le texte du bouton en "Partager et débloquez votre réduction !".

-   **Titre du message contextuel :**
    -   **Ce que fait ce paramètre :** Définit le titre de la fenêtre contextuelle qui apparaît après un partage réussi, affichant le code de réduction.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'un titre est saisi (par exemple, "Félicitations !") :* La fenêtre contextuelle affichera votre titre personnalisé.
        -   *Lorsqu'il est laissé vide :* Un titre par défaut sera utilisé.
    -   **Valeur recommandée :** Un titre accueillant et de félicitations (par exemple, "Votre code de réduction !", "Merci d'avoir partagé !").
    -   **Scénario / exemple de marchand :** Vous voulez que le client se sente récompensé, vous définissez donc le titre sur "Voici votre réduction exclusive !".

-   **Contenu du message contextuel :**
    -   **Ce que fait ce paramètre :** Vous permet de personnaliser le contenu textuel principal de la fenêtre contextuelle du code de réduction. Vous pouvez inclure des instructions ou des messages supplémentaires.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'un contenu est saisi :* La fenêtre contextuelle affichera votre message personnalisé.
        -   *Lorsqu'il est laissé vide :* Un message par défaut sera utilisé.
    -   **Valeur recommandée :** Un message clair indiquant au client de copier le code et comment l'utiliser (par exemple, "Copiez ce code et appliquez-le au moment du paiement pour recevoir votre réduction.").
    -   **Scénario / exemple de marchand :** Vous souhaitez rappeler aux clients où utiliser le code : "Merci d'avoir partagé ! Utilisez le code ci-dessous au moment du paiement pour vos économies."

#### **Paramètres avancés (si disponibles)**

-   **Feuille de style CSS pour le bouton/popup :**
    -   **Ce que fait ce paramètre :** Vous permet de sélectionner ou de saisir du CSS personnalisé pour styliser le bouton de partage et/ou la fenêtre contextuelle de réduction afin de mieux correspondre à votre thème.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque du CSS personnalisé est appliqué :* L'apparence visuelle (couleurs, polices, tailles) du bouton et de la fenêtre contextuelle changera selon vos styles.
        -   *Lorsque la valeur par défaut est utilisée :* Le module utilisera son style intégré.
    -   **Valeur recommandée :** Laissez vide initialement, puis personnalisez si le style par défaut ne correspond pas à votre marque.
    -   **Scénario / exemple de marchand :** Votre boutique utilise une nuance spécifique de bleu pour les boutons. Vous pouvez ajouter une règle CSS ici pour changer la couleur d'arrière-plan du bouton de partage à cette nuance.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Configuration du module | Activer / Désactiver le module | OUI | Active/désactive toutes les fonctionnalités du module. |
| | ID d'application Facebook | Votre ID d'application | Lie votre boutique à votre application Facebook pour le suivi des partages. |
| | Type de réduction | Pourcentage | Définit si la réduction est un pourcentage ou un montant fixe. |
| | Valeur de la réduction | ex., 10 (pour 10%) | La valeur réelle de la réduction offerte. |
| | Montant minimum pour la réduction | 0 (pas de minimum) | Définit une valeur de commande minimale pour l'utilisation du code de réduction. |
| | Validité du code de réduction (en jours) | 7-30 jours | Définit une période d'expiration pour les codes de réduction générés. |
| | Préfixe du code de réduction | FB- | Ajoute un préfixe personnalisé aux codes générés pour une identification facile. |
| | Afficher le bouton de partage sur | Page produit (Contenu principal) | Contrôle le placement du bouton de partage sur les pages produit. |
| | Texte du bouton de partage | Partager pour une réduction ! | Personnalise le texte affiché sur le bouton de partage. |
| | Titre du message contextuel | Votre code de réduction ! | Définit le titre de la fenêtre contextuelle du code de réduction. |
| | Contenu du message contextuel | Copiez ce code... | Personnalise le message principal dans la fenêtre contextuelle du code de réduction. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Le bouton de partage Facebook n'apparaît pas sur mes pages produit.**
**R1 :**
*   **Vérifier l'état du module :** Assurez-vous que le module est activé dans les paramètres de configuration.
*   **Vérifier l'ID d'application Facebook :** Vérifiez à nouveau que votre ID d'application Facebook est correctement saisi dans la configuration du module. Un ID incorrect ou manquant empêchera le chargement du bouton.
*   **Vérifier le placement du bouton :** Confirmez que le paramètre "Afficher le bouton de partage sur" est correctement choisi (par exemple, "Page produit (Contenu principal)"). Si votre thème a des hooks fortement personnalisés, vous devrez peut-être essayer différents emplacements ou consulter un développeur.
*   **Vider le cache :** Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop et videz le cache Smarty et tous les caches. Parfois, d'anciens fichiers mis en cache empêchent l'apparition de nouveaux éléments de module.

**Q2 : Les clients partagent, mais ils ne reçoivent pas de code de réduction.**
**R2 :**
*   **ID d'application Facebook :** C'est la cause la plus fréquente. Le module s'appuie sur l'ID d'application Facebook pour suivre les partages réussis. Assurez-vous qu'il est correct et que votre application Facebook est correctement configurée (par exemple, l'URL du site web est ajoutée).
*   **Permissions/Confidentialité Facebook :** Parfois, les paramètres de confidentialité Facebook d'un client ou les bloqueurs de publicité du navigateur peuvent interférer avec le suivi des partages. C'est moins courant mais cela peut arriver.
*   **Configuration du module :** Examinez tous les paramètres liés aux réductions (Type de réduction, Valeur, Validité). Assurez-vous qu'ils sont définis sur des valeurs valides.
*   **Paramètres des bons de réduction PrestaShop :** Assurez-vous que les paramètres généraux des bons de réduction/règles de panier de votre boutique PrestaShop n'empêchent pas la création de nouveaux codes (par exemple, nombre maximum de bons atteint, bien que cela soit rare).

**Q3 : La fenêtre contextuelle du code de réduction semble étrange ou ne correspond pas au design de ma boutique.**
**R3 :**
*   **Conflits de thème :** Votre thème PrestaShop personnalisé peut avoir des styles CSS conflictuels.
*   **CSS du module :** Le module inclut son propre CSS. Vous pouvez essayer de le remplacer.
*   **Solution :** Dans la configuration du module, recherchez les options "CSS personnalisé" ou "Feuille de style". Vous devrez peut-être ajouter des règles CSS personnalisées pour ajuster l'apparence de la fenêtre contextuelle. Si vous n'êtes pas à l'aise avec le CSS, un webmaster ou un développeur peut vous aider. Vider le cache de votre navigateur peut également parfois résoudre des problèmes d'affichage mineurs.

**Q4 : Puis-je traduire le texte du bouton et les messages contextuels dans d'autres langues ?**
**R4 :** Oui, le système de traduction de PrestaShop prend en charge les traductions de modules.
*   Allez dans **International > Traductions** dans votre Back Office.
*   Sélectionnez "Traductions des modules installés", choisissez votre thème, puis sélectionnez votre langue.
*   Recherchez le module "Partage de produit Facebook + code de réduction" et vous pourrez traduire tous les textes visibles par l'utilisateur, y compris le texte du bouton et les messages contextuels.

**Q5 : Que se passe-t-il si un client partage un produit plusieurs fois ? Obtient-il plusieurs réductions ?**
**R5 :** Le module est conçu pour émettre un code de réduction unique par *événement de partage réussi* pour un utilisateur donné. Cependant, selon l'implémentation exacte, un utilisateur pourrait être en mesure de partager différents produits et de recevoir plusieurs codes. Il est généralement préférable d'encourager les partages uniques pour des récompenses uniques. Si vous souhaitez le limiter à un code par client, quel que soit le nombre de partages, vous pourriez avoir besoin d'un développement personnalisé ou de gérer manuellement les bons générés.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)
Cette section fournit une analyse approfondie de la structure technique du module "Partage de produit Facebook + code de réduction" pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture
Le module suit une architecture de module PrestaShop standard, exploitant principalement la classe `Module` pour l'installation, la désinstallation et la configuration. Il s'intègre au front-office via des hooks pour afficher le bouton de partage et utilise AJAX pour gérer la génération du code de réduction après le partage. La logique principale de création de bons est probablement encapsulée dans la classe principale du module ou une classe d'aide.

### 4.2 Contrôleurs (`controllers/`)
Ce module ne semble pas utiliser de fichiers `ModuleFrontController` ou `AdminController` dédiés dans le répertoire `controllers/` d'après l'inventaire fourni. Les interactions AJAX du front-office sont probablement gérées directement dans le fichier principal du module (`ajax_productlike.php`) ou via un répartiteur AJAX générique de PrestaShop.

### 4.3 Classes et modèles principaux (`classes/`)
D'après l'inventaire fourni, il n'y a pas de classes `ObjectModel` personnalisées définies dans un répertoire `classes/`. Le module gère probablement sa configuration directement via `Configuration::get()` et `Configuration::updateValue()` et crée des objets `CartRule` de PrestaShop pour les réductions.

### 4.4 Actifs JavaScript (`views/js/`)
Le module inclut plusieurs fichiers JavaScript, indiquant une logique côté client pour l'interaction Facebook et l'affichage des fenêtres contextuelles.

-   `productlike/js/productlike.js` :
    *   **Portée :** Front-office.
    *   **Responsabilité :** Gère probablement la logique principale pour initier la boîte de dialogue de partage Facebook, écouter l'événement de fin de partage du SDK de Facebook, puis effectuer un appel AJAX vers le back-end de la boutique PrestaShop pour demander le code de réduction. Il gérerait également l'affichage de la fenêtre contextuelle du code de réduction.
    *   **Fonctionnalités clés :** Initialisation du SDK Facebook, appels de méthode `FB.ui` pour le partage, requêtes AJAX vers le back-end du module, manipulation du DOM pour l'affichage de la fenêtre contextuelle.

-   `productlike/js/script.js` :
    *   **Portée :** Front-office.
    *   **Responsabilité :** Il pourrait s'agir d'un script utilitaire général ou d'une alternative/solution de repli à `productlike.js`. Il pourrait contenir des écouteurs d'événements pour le clic sur le bouton de partage, ou gérer la logique d'affichage/masquage de la fenêtre contextuelle de réduction.
    *   **Fonctionnalités clés :** Liaison d'événements, potentiellement des animations simples ou une manipulation du DOM.

-   `productlike/lib/voucherengine/script.js` :
    *   **Portée :** Front-office.
    *   **Responsabilité :** Suggère un script dédié à l'affichage et à l'interaction avec les bons. Il pourrait gérer la copie du code du bon dans le presse-papiers, la fermeture de la fenêtre contextuelle ou d'autres éléments d'interface utilisateur liés à la réduction.
    *   **Fonctionnalités clés :** Interaction avec l'API du presse-papiers, événements de fermeture de la fenêtre contextuelle, retour d'interface utilisateur.

### 4.5 Feuilles de style CSS (`views/css/`)
Le module utilise plusieurs fichiers CSS pour styliser ses composants front-office.

-   `productlike/css/css.css` :
    *   **Portée :** Style client du front-office.
    *   **Responsabilité :** Contient les styles généraux pour le bouton de partage Facebook et potentiellement la fenêtre contextuelle du code de réduction.
    *   **Sélecteurs clés :** `.productlike-button`, `.productlike-popup`, `.productlike-voucher-code`. Les développeurs peuvent les remplacer dans le `custom.css` de leur thème ou en utilisant l'entrée CSS personnalisée du module si disponible.

-   `productlike/css.css` :
    *   **Portée :** Style client du front-office.
    *   **Responsabilité :** Potentiellement une feuille de style plus ancienne ou alternative, ou des styles spécifiques pour certains éléments non couverts par `css.css`.
    *   **Sélecteurs clés :** Similaires à `css.css`, selon son contenu.

-   `productlike/lib/voucherengine/ps16.css` :
    *   **Portée :** Style client du front-office, spécifiquement pour la compatibilité PrestaShop 1.6.
    *   **Responsabilité :** Fournit des ajustements de style pour garantir que la fenêtre contextuelle du bon et le bouton s'affichent correctement sur les thèmes PrestaShop 1.6, qui peuvent avoir des styles d'éléments par défaut différents.
    *   **Sélecteurs clés :** Cible probablement les éléments d'interface utilisateur courants de PrestaShop 1.6 pour assurer une cohérence visuelle.

### 4.6 Structure des templates Smarty (`views/templates/`)
Le module utilise des templates Smarty pour rendre ses composants front-office.

-   **Templates de hook (`views/templates/hook/`)** :
    *   `productlike/header.tpl` :
        *   **Hook :** `displayHeader`
        *   **Objectif :** Ce template est probablement responsable de l'initialisation du SDK JavaScript de Facebook, du chargement des fichiers JavaScript nécessaires et potentiellement du passage de variables de configuration (comme l'ID d'application Facebook) du back-end du module au JavaScript du front-end. Il garantit que l'API Facebook est prête avant que le bouton de partage ne soit rendu.
    *   `productlike/share.tpl` :
        *   **Hook :** `displayProductButtons`, `displayRightColumnProduct`, `displayLeftColumnProduct`, `displayFooterProduct` (ou des hooks de page produit similaires, selon la configuration).
        *   **Objectif :** Rend le bouton "Partager sur Facebook" réel sur la page produit. Il contiendra la structure HTML du bouton et potentiellement un espace réservé pour la fenêtre contextuelle du code de réduction, qui est ensuite dynamiquement remplie par JavaScript.

-   **Templates d'administration (`views/templates/admin/`)** : Aucun explicitement listé, ce qui implique que la configuration est gérée directement par `getContent()` dans le fichier principal du module.

-   **Templates front-office (`views/templates/front/`)** : Aucun explicitement listé, car l'interaction principale se fait via des hooks et des fenêtres contextuelles.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    *   Le module ne crée probablement pas de tables de base de données personnalisées.
    *   Les paramètres de configuration (ID d'application Facebook, valeurs de réduction, etc.) sont stockés dans la table `ps_configuration` à l'aide de clés telles que `PRODUCTLIKE_FACEBOOK_APP_ID`, `PRODUCTLIKE_DISCOUNT_TYPE`, `PRODUCTLIKE_DISCOUNT_VALUE`, etc.
    *   Les codes de réduction générés sont des entrées `CartRule` PrestaShop standard, stockées dans `ps_cart_rule` et les tables associées.

-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Initialise le SDK Facebook, charge les JS/CSS du module, transmet les variables de configuration. |
| `displayProductButtons` | Sur la page produit, généralement près du bouton Ajouter au panier. | Rend le bouton de partage Facebook. (Courant pour PS 1.7+) |
| `displayRightColumnProduct` | Dans la colonne de droite de la page produit. | Rend le bouton de partage Facebook (si configuré). |
| `displayLeftColumnProduct` | Dans la colonne de gauche de la page produit. | Rend le bouton de partage Facebook (si configuré). |
| `displayFooterProduct` | Dans la zone du pied de page de la page produit. | Rend le bouton de partage Facebook (si configuré). |
| `displayProductExtraContent` | Sur la page produit, pour les onglets/blocs de contenu supplémentaires. | Hook alternatif pour le placement du bouton (PS 1.7+). |
| `actionFrontControllerSetMedia` | Avant que le contrôleur frontal ne rende la page. | Enregistre les fichiers JS et CSS du module. |
| `actionObjectCartRuleAddAfter` | Après l'ajout d'une nouvelle règle de panier (bon de réduction). | Potentiellement utilisé pour la journalisation ou le traitement ultérieur des bons générés. |

## 5. Support officiel et mises à jour
Pour les dernières mises à jour, corrections de bugs et support professionnel pour votre module "Partage de produit Facebook + code de réduction", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe est dédiée à fournir une assistance et à garantir le fonctionnement optimal de votre module.
