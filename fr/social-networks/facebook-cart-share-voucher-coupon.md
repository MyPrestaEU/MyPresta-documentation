---
title: "Partage de panier Facebook + bon de réduction - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Partage de panier Facebook + bon de réduction' par MyPresta.eu."
sidebar:
  label: "Partage de panier Facebook + bon de réduction"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Facebook cart share + voucher coupon sur MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-cart-share-voucher-coupon.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/facebook-cart-share-voucher-coupon/)
>
> ---


# Partage de panier Facebook + bon de réduction

## 1. Exigences et compatibilité
- **Versions de PrestaShop prises en charge :** PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop et les interactions avec l'API Facebook.

## 2. Présentation complète de la configuration (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
C'est l'écran de configuration principal du module "Partage de panier Facebook + bon de réduction". Vous le trouverez en naviguant vers **Modules > Gestionnaire de modules**, en recherchant "Partage de panier Facebook + bon de réduction", et en cliquant sur "Configurer".

#### **Paramètres généraux**

-   **ID d'application Facebook (cshare_appid / cshare_app_id)**
    -   **Ce que fait ce paramètre :** C'est un identifiant unique pour votre application Facebook, qui est requis pour que le module interagisse avec l'API de Facebook. Vous devez créer une application Facebook sur la plateforme Facebook Developers (developers.facebook.com) pour obtenir cet ID.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est correctement défini :* Le module peut se connecter avec succès à Facebook, permettant aux clients de partager leurs paniers et à votre boutique de suivre ces partages.
        -   *Lorsqu'il est laissé vide ou mal défini :* La fonctionnalité de partage Facebook ne fonctionnera pas, et les clients ne pourront pas partager leurs paniers.
    -   **Valeur recommandée :** Votre ID d'application Facebook unique.
    -   **Scénario / exemple de marchand :** Vous avez enregistré votre boutique PrestaShop en tant qu'application sur Facebook Developers et avez reçu un ID d'application comme `123456789012345`. Entrez cet ID ici.

-   **Afficher le bouton de partage sur (cshare_lasttab)**
    -   **Ce que fait ce paramètre :** Détermine où le bouton "Partager le panier sur Facebook" apparaîtra dans le front office de votre boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur "Page du panier d'achat" :* Le bouton apparaît sur la page où les clients examinent le contenu de leur panier avant de passer à la caisse.
        -   *Lorsqu'il est défini sur "Page de confirmation de commande" :* Le bouton apparaît après que le client a passé une commande avec succès.
        -   *Lorsqu'il est défini sur "Les deux" :* Le bouton apparaît sur les deux pages.
    -   **Valeur recommandée :** "Les deux" pour maximiser la visibilité et les opportunités de partage.
    -   **Scénario / exemple de marchand :** Vous souhaitez encourager le partage avant et après un achat, vous sélectionnez donc "Les deux".

-   **Style du bouton de partage Facebook (cshare_button_style)**
    -   **Ce que fait ce paramètre :** Vous permet de choisir le style visuel du bouton de partage Facebook.
    -   **Effet de la modification de ce paramètre :** Modifie l'apparence du bouton de partage pour mieux correspondre au design de votre boutique ou à votre préférence pour un bouton plus grand/plus petit.
    -   **Valeur recommandée :** Expérimentez pour trouver ce qui convient le mieux à votre thème.
    -   **Scénario / exemple de marchand :** Votre thème a un design minimaliste, vous pourriez donc choisir un bouton de partage simple, basé sur du texte, plutôt qu'un bouton graphique plus grand.

#### **Paramètres des bons de réduction**

-   **Activer la génération de bons de réduction (cshare_voucher)**
    -   **Ce que fait ce paramètre :** Active ou désactive la génération et l'offre d'un bon de réduction au client après qu'il ait partagé son panier avec succès sur Facebook.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Un code de bon de réduction unique est créé et affiché au client après le partage.
        -   *Lorsqu'il est désactivé :* Aucun bon de réduction n'est généré ou offert, supprimant l'incitation directe au partage.
    -   **Valeur recommandée :** "OUI" pour tirer parti de l'incitation au partage et stimuler les conversions.
    -   **Scénario / exemple de marchand :** Vous souhaitez récompenser les clients pour le partage et encourager les achats répétés, vous activez donc cette option.

-   **Type de bon de réduction (cshare_gift)**
    -   **Ce que fait ce paramètre :** Définit le type et la valeur du bon de réduction que les clients reçoivent. Cela correspond aux paramètres "Type de réduction" et "Valeur" lors de la création d'une nouvelle règle de panier dans PrestaShop.
    -   **Effet de la modification de ce paramètre :**
        -   *Montant fixe :* Le client reçoit une réduction monétaire spécifique (par exemple, 5 € de réduction).
        -   *Pourcentage :* Le client reçoit une réduction en pourcentage (par exemple, 10 % de réduction).
        -   *Livraison gratuite :* Le client reçoit la livraison gratuite sur sa prochaine commande.
    -   **Valeur recommandée :** Une valeur suffisamment attrayante pour inciter au partage mais également durable pour votre entreprise.
    -   **Scénario / exemple de marchand :** Vous décidez d'offrir une "réduction de 10 %" pour encourager de nouveaux achats, vous sélectionnez donc "Pourcentage" et définissez la valeur dans le champ suivant.

-   **Valeur du bon de réduction (cshare_image)**
    -   **Ce que fait ce paramètre :** Définit la valeur spécifique du bon de réduction, en fonction du type de "Type de bon de réduction" choisi.
    -   **Effet de la modification de ce paramètre :**
        -   *Si "Montant fixe" est choisi :* Ce sera la valeur monétaire exacte de la réduction.
        -   *Si "Pourcentage" est choisi :* Ce sera le pourcentage de la réduction.
    -   **Valeur recommandée :** Une réduction attrayante (par exemple, 5, 10, 15 pour le pourcentage ; 5, 10, 20 pour le montant fixe).
    -   **Scénario / exemple de marchand :** Vous avez choisi "Pourcentage" pour "Type de bon de réduction", vous entrez donc ici "10" pour une réduction de 10 %.

#### **Paramètres du contenu partagé**

Ces paramètres contrôlent les informations sur le panier du client qui sont incluses dans la publication Facebook lorsqu'il la partage.

-   **Afficher les prix (cshare_show_prices)**
    -   **Ce que fait ce paramètre :** Détermine si les prix individuels des produits dans le panier sont affichés dans la publication de partage Facebook.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Chaque produit listé dans le panier partagé affichera son prix.
        -   *Lorsqu'il est désactivé :* Les prix des produits seront omis de la publication partagée.
    -   **Valeur recommandée :** "OUI" pour assurer la transparence et encourager les clics, sauf si votre stratégie de prix l'exige autrement.
    -   **Scénario / exemple de marchand :** Vous souhaitez que les clients potentiels voient la valeur des articles, vous activez donc "Afficher les prix".

-   **Afficher le total (cshare_show_total)**
    -   **Ce que fait ce paramètre :** Détermine si la valeur totale du panier d'achat est affichée dans la publication de partage Facebook.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Le prix total de tous les articles du panier sera affiché.
        -   *Lorsqu'il est désactivé :* Le total du panier ne sera pas inclus dans la publication.
    -   **Valeur recommandée :** "OUI" pour donner un aperçu clair de la valeur du panier.
    -   **Scénario / exemple de marchand :** Un client a un panier d'une valeur de 250 €, et vous voulez que ses amis voient cet achat important, vous activez donc "Afficher le total".

-   **Afficher les produits (cshare_show_products)**
    -   **Ce que fait ce paramètre :** Détermine si les noms et les quantités des produits individuels dans le panier sont listés dans la publication de partage Facebook.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Une liste de produits (par exemple, "T-Shirt x1, Jean x1") apparaîtra dans la publication.
        -   *Lorsqu'il est désactivé :* Seul un message général concernant le partage du panier apparaîtra, sans détails spécifiques sur les produits.
    -   **Valeur recommandée :** "OUI" pour présenter les articles spécifiques et générer de l'intérêt.
    -   **Scénario / exemple de marchand :** Vous souhaitez mettre en évidence les produits spécifiques qu'un client achète, vous activez donc "Afficher les produits".

-   **Afficher l'URL du produit (cshare_show_product_url)**
    -   **Ce que fait ce paramètre :** Détermine si des liens directs vers les pages de produits individuelles sont inclus dans la publication de partage Facebook.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Chaque produit listé aura un lien cliquable vers sa page sur votre boutique.
        -   *Lorsqu'il est désactivé :* Les noms des produits seront affichés mais sans liens directs.
    -   **Valeur recommandée :** "OUI" pour diriger le trafic directement vers les pages de produits.
    -   **Scénario / exemple de marchand :** Vous souhaitez que les amis du partageur puissent facilement cliquer et voir les produits, vous activez donc "Afficher l'URL du produit".

#### **Paramètres avancés**

-   **Forcer HTTPS (cshare_http)**
    -   **Ce que fait ce paramètre :** Garantit que toutes les URL générées pour le partage Facebook utilisent HTTPS, même si votre configuration PrestaShop pourrait parfois par défaut utiliser HTTP. C'est crucial pour la sécurité et les exigences de Facebook.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Tous les liens partagés seront sécurisés (HTTPS).
        -   *Lorsqu'il est désactivé :* Les liens pourraient parfois être HTTP, ce qui peut causer des problèmes avec l'API de Facebook et des avertissements de sécurité.
    -   **Valeur recommandée :** "OUI" si votre boutique utilise HTTPS (ce qui devrait être le cas !).
    -   **Scénario / exemple de marchand :** Toute votre boutique fonctionne en HTTPS, vous activez donc cette option pour assurer la cohérence et éviter les avertissements du navigateur.

-   **Nom de la boutique PrestaShop (PS_SHOP_NAME)**
    -   **Ce que fait ce paramètre :** Ce champ extrait généralement le nom de votre boutique des paramètres généraux de PrestaShop. Il est utilisé dans la publication Facebook partagée.
    -   **Effet de la modification de ce paramètre :** Garantit que le nom correct de la boutique est affiché dans la publication Facebook.
    -   **Valeur recommandée :** Laisser par défaut (il devrait se remplir automatiquement à partir de votre configuration PrestaShop).
    -   **Scénario / exemple de marchand :** Votre boutique s'appelle "Ma Super Boutique", et ce champ affiche correctement "Ma Super Boutique".

-   **E-mail de la boutique PrestaShop (PS_SHOP_EMAIL)**
    -   **Ce que fait ce paramètre :** Ce champ extrait généralement l'e-mail de contact de votre boutique des paramètres généraux de PrestaShop. Il peut être utilisé pour les opérations internes du module ou dans le contenu généré.
    -   **Effet de la modification de ce paramètre :** Garantit que l'e-mail correct est utilisé si le module doit y faire référence.
    -   **Valeur recommandée :** Laisser par défaut (il devrait se remplir automatiquement à partir de votre configuration PrestaShop).
    -   **Scénario / exemple de marchand :** L'e-mail de contact de votre boutique est `info@masuperboutique.com`, et ce champ l'affiche correctement.

-   **Taxe PrestaShop (PS_TAX)**
    -   **Ce que fait ce paramètre :** Ce champ extrait généralement le paramètre de taxe par défaut de votre boutique. Il peut être utilisé pour calculer correctement les prix dans le contenu partagé.
    -   **Effet de la modification de ce paramètre :** Garantit que les considérations fiscales sont gérées correctement si les prix sont affichés.
    -   **Valeur recommandée :** Laisser par défaut (il devrait se remplir automatiquement à partir de votre configuration PrestaShop).
    -   **Scénario / exemple de marchand :** Votre boutique fonctionne avec une TVA de 20 %, et ce champ le reflète.

#### **Paramètres internes du module (Généralement à laisser par défaut)**

-   **Mises à jour MyPresta.eu (mypresta_updates, update_, updatev_)**
    -   **Ce que fait ce paramètre :** Ce sont des paramètres internes utilisés par les modules MyPresta.eu pour vérifier les mises à jour et assurer la compatibilité.
    -   **Effet de la modification de ce paramètre :** La modification de ces paramètres pourrait interférer avec la capacité du module à recevoir des mises à jour ou à fonctionner correctement.
    -   **Valeur recommandée :** Laisser par défaut.
    -   **Scénario / exemple de marchand :** Vous n'avez généralement pas besoin d'interagir avec ces paramètres.

-   **Initialisation Facebook (cshare_fbinit)**
    -   **Ce que fait ce paramètre :** Un indicateur interne qui indique si le SDK Facebook a été initialisé.
    -   **Effet de la modification de ce paramètre :** La modification de ce paramètre pourrait empêcher le chargement correct de la fonctionnalité de partage Facebook.
    -   **Valeur recommandée :** Laisser par défaut.
    -   **Scénario / exemple de marchand :** C'est un paramètre technique non destiné à l'interaction du marchand.

### 2.2 Écrans d'administration dédiés et vues de contrôleur
Ce module n'introduit aucun écran d'administration ou contrôleur personnalisé dédié au-delà de sa page de configuration principale. Tous les paramètres sont gérés directement via l'interface de configuration standard du module.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
|---|---|---|---|
| Configuration du module | ID d'application Facebook | Votre ID d'application unique | Essentiel pour la connexion à l'API Facebook ; le partage ne fonctionnera pas sans elle. |
| Configuration du module | Afficher le bouton de partage sur | Les deux | Contrôle où le bouton de partage apparaît (Panier, Confirmation de commande, ou les deux). |
| Configuration du module | Style du bouton de partage Facebook | (Varie) | Modifie l'apparence visuelle du bouton de partage. |
| Configuration du module | Activer la génération de bons de réduction | OUI | Active ou désactive la création et l'affichage d'un bon de réduction après le partage. |
| Configuration du module | Type de bon de réduction | Pourcentage / Montant fixe | Définit le type de réduction (par exemple, 10 % de réduction, 5 € de réduction, Livraison gratuite). |
| Configuration du module | Valeur du bon de réduction | (Votre valeur souhaitée) | Définit la valeur spécifique pour le type de bon de réduction choisi. |
| Configuration du module | Afficher les prix | OUI | Inclut les prix individuels des produits dans la publication de partage Facebook. |
| Configuration du module | Afficher le total | OUI | Inclut la valeur totale du panier dans la publication de partage Facebook. |
| Configuration du module | Afficher les produits | OUI | Liste les noms et quantités des produits individuels dans la publication de partage Facebook. |
| Configuration du module | Afficher l'URL du produit | OUI | Ajoute des liens directs vers les pages de produits dans la publication de partage Facebook. |
| Configuration du module | Forcer HTTPS | OUI | Garantit que tous les liens partagés sont sécurisés (HTTPS). |
| Configuration du module | Nom de la boutique PrestaShop | (Rempli automatiquement) | Affiche le nom de votre boutique dans la publication Facebook. |
| Configuration du module | E-mail de la boutique PrestaShop | (Rempli automatiquement) | E-mail de contact de la boutique. |
| Configuration du module | Taxe PrestaShop | (Rempli automatiquement) | Paramètre de taxe par défaut de la boutique. |
| Configuration du module | Mises à jour MyPresta.eu | (Interne) | Paramètres internes pour les mises à jour du module. |
| Configuration du module | Initialisation Facebook | (Interne) | Indicateur interne pour l'initialisation du SDK Facebook. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Le bouton de partage Facebook n'apparaît pas sur ma page de panier/confirmation de commande.**
*   **R :** Tout d'abord, vérifiez la configuration du module dans votre Back Office (**Modules > Gestionnaire de modules > Configurer Partage de panier Facebook + bon de réduction**). Assurez-vous que "Afficher le bouton de partage sur" est correctement défini (par exemple, "Page du panier d'achat", "Page de confirmation de commande" ou "Les deux"). Vérifiez également que votre ID d'application Facebook est correctement saisi. Si cela ne s'affiche toujours pas, videz le cache de votre PrestaShop (**Paramètres avancés > Performances > Vider le cache**).

**Q2 : Lorsque les clients cliquent sur le bouton de partage, rien ne se passe ou ils obtiennent une erreur.**
*   **R :** Cela indique presque toujours un problème avec votre ID d'application Facebook ou la configuration de l'application Facebook elle-même.
    1.  **Vérifiez à nouveau votre ID d'application Facebook :** Assurez-vous qu'il est correctement saisi dans la configuration du module.
    2.  **Vérifiez les paramètres de l'application Facebook :** Connectez-vous à [developers.facebook.com](https://developers.facebook.com/). Assurez-vous que votre application est "En ligne" (pas en mode développement). Vérifiez la section "Paramètres > Basique" de votre application : les champs "Domaines d'application" et "Site web" doivent lister précisément le domaine de votre boutique (par exemple, `votreboutique.com` et `https://www.votreboutique.com`).
    3.  **Forcer HTTPS :** Assurez-vous que l'option "Forcer HTTPS" dans la configuration du module est définie sur "OUI" si votre boutique utilise HTTPS.

**Q3 : Les bons de réduction ne sont pas générés après un partage réussi.**
*   **R :**
    1.  **Vérifiez "Activer la génération de bons de réduction" :** Dans la configuration du module, assurez-vous que ce paramètre est défini sur "OUI".
    2.  **Type et valeur du bon de réduction :** Assurez-vous d'avoir sélectionné un type de "Type de bon de réduction" (par exemple, Pourcentage, Montant fixe) et saisi une "Valeur du bon de réduction" valide.
    3.  **Limites des règles de panier PrestaShop :** PrestaShop a des limites sur le nombre de règles de panier. Bien que peu probable pour ce module, si vous avez un volume extrêmement élevé de partages, assurez-vous que votre serveur peut gérer la création de nouvelles règles de panier.
    4.  **Journaux d'erreurs :** Vérifiez les journaux d'erreurs de votre PrestaShop (généralement dans `var/logs/` ou `app/logs/` pour PS 1.7+) pour toute erreur liée pendant le processus de génération de bons de réduction.

**Q4 : Le contenu partagé sur Facebook ne s'affiche pas correctement (par exemple, prix manquants, mauvaise image).**
*   **R :**
    1.  **Paramètres du module :** Passez en revue les "Paramètres du contenu partagé" dans la configuration du module (Afficher les prix, Afficher le total, Afficher les produits, Afficher l'URL du produit). Assurez-vous qu'ils sont tous définis sur "OUI" si vous souhaitez un maximum de détails.
    2.  **Facebook Open Graph :** Facebook utilise les balises Open Graph (OG) de vos pages de produits pour générer des aperçus. Assurez-vous que votre thème PrestaShop et les autres modules génèrent correctement ces balises OG (en particulier `og:image`, `og:title`, `og:description`). Vous pouvez utiliser le [Débogueur de partage](https://developers.facebook.com/tools/debug/) de Facebook pour voir comment Facebook extrait vos URL.
    3.  **Cache :** Videz le cache de votre PrestaShop et le cache de votre navigateur. Facebook met également en cache le contenu partagé, alors utilisez le Débogueur de partage pour "Scraper à nouveau" si vous avez apporté des modifications.

**Q5 : Le module ne s'affiche pas correctement avec mon thème personnalisé.**
*   **R :** Le module utilise ses propres CSS (`css.css`, `ps16.css`). Votre thème personnalisé pourrait remplacer ou entrer en conflit avec ces styles.
    1.  **Inspecter l'élément :** Utilisez les outils de développement de votre navigateur (F12) pour inspecter le bouton de partage et l'affichage du bon de réduction. Identifiez les classes CSS appliquées par le module et votre thème.
    2.  **CSS personnalisé :** Vous pouvez ajouter du CSS personnalisé au fichier `custom.css` de votre thème (ou équivalent) pour remplacer les styles du module et le faire mieux correspondre à votre thème. Ciblez les classes spécifiques du module pour éviter d'affecter d'autres parties de votre boutique.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture
Le module "Partage de panier Facebook + bon de réduction" suit une architecture de module PrestaShop standard, exploitant principalement la classe `Module` et `ModuleFrontController` pour les interactions front-office. Il s'intègre au SDK JavaScript de Facebook pour la fonctionnalité de partage et utilise l'objet `CartRule` de PrestaShop pour la génération de bons de réduction. La configuration est gérée via la méthode `getContent()` dans le fichier principal du module, stockant les paramètres dans `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office :**
    *   `cartshare/controllers/front/cartshare.php`
        *   **Nom de classe et classe parente :** `CartshareCartshareModuleFrontController` étend `ModuleFrontController`.
        *   **Responsabilité :** Ce contrôleur est probablement responsable de la gestion du rappel AJAX de Facebook après un partage, ou du rendu de la page dédiée au partage de panier si le module en possède une. Il traiterait l'événement de partage et déclencherait la logique de génération de bons de réduction. Il pourrait également être responsable du rendu du template `cartsharepage.tpl`.
    *   `cartshare/controllers/front/index.php`
        *   **Nom de classe et classe parente :** Il s'agit généralement d'un fichier vide ou d'une simple redirection pour empêcher l'affichage du répertoire, courant dans les modules PrestaShop. Il ne contient pas de classe de contrôleur spécifique.
        *   **Responsabilité :** Mesure de sécurité pour empêcher l'accès direct au répertoire `front`.

-   **Contrôleurs d'administration Back-Office :**
    *   Aucun. Toute l'administration est gérée via la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)
Ce module ne semble pas définir de classes personnalisées ou d'`ObjectModel` dans le répertoire `classes/`. Sa logique principale pour la génération de bons de réduction interagit probablement directement avec la classe `CartRule` de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

-   `cartshare/lib/voucherengine/script.js`
    *   **Portée :** Front-office.
    *   **Détails :** Ce script est crucial pour l'interaction côté client. Il initialise probablement le SDK JavaScript de Facebook en utilisant le `cshare_appid` de la configuration du module. Il lie les écouteurs d'événements au bouton "Partager sur Facebook", gère la boîte de dialogue de partage Facebook et, après un partage réussi, effectue un appel AJAX au contrôleur frontal `cartshare.php` pour déclencher la génération de bons de réduction et afficher le code du bon de réduction à l'utilisateur. Il pourrait également gérer l'affichage dynamique du code du bon de réduction sur la page.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `cartshare/css.css`
    *   **Portée :** Front-office.
    *   **Détails :** Contient le style général des éléments du module, tels que le bouton de partage, la zone d'affichage du bon de réduction et tout autre composant d'interface utilisateur introduit par le module.
-   `cartshare/lib/voucherengine/ps16.css`
    *   **Portée :** Front-office.
    *   **Détails :** Contient probablement des ajustements de style spécifiques ou des remplacements adaptés aux thèmes PrestaShop 1.6, garantissant la compatibilité et un rendu correct sur les versions plus anciennes.
-   `cartshare/views/css/css/css.css`
    *   **Portée :** Front-office.
    *   **Détails :** Ce chemin semble redondant (`css/css/`). Il est possible qu'il s'agisse d'un doublon ou d'une version plus ancienne de `cartshare/css.css`, ou qu'il contienne un style très spécifique pour certains éléments. Les développeurs doivent vérifier son contenu pour comprendre son objectif.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`) :**
    *   `cartshare/views/templates/hook/header.tpl`
        *   **Hook :** `displayHeader`
        *   **Sortie :** Ce template est responsable de l'inclusion du code d'initialisation du SDK JavaScript de Facebook et potentiellement des fichiers JavaScript (`script.js`) et CSS principaux du module. Il garantit que l'API Facebook est prête avant que le bouton de partage ne soit rendu.
    *   `cartshare/views/templates/hook/share.tpl`
        *   **Hook :** `displayShoppingcart`, `displayOrderConfirmation` (selon la configuration du module)
        *   **Sortie :** Rend le bouton "Partager le panier sur Facebook" et le conteneur pour afficher le code du bon de réduction après un partage réussi. C'est le principal composant visuel avec lequel les clients interagissent.

-   **Templates Front-office (`views/templates/front/`) :**
    *   `cartshare/views/templates/front/cartsharepage.tpl`
        *   **Objectif :** Ce template est probablement rendu par le `CartshareCartshareModuleFrontController` et pourrait être une page dédiée ou une vue partielle pour afficher le contenu du panier à partager, ou le code du bon de réduction.
    *   `cartshare/views/templates/front/facebook-share-contents.tpl`
        *   **Objectif :** Ce template génère dynamiquement le contenu qui sera transmis à la boîte de dialogue de partage Facebook. Il construit le titre, la description, l'image et les URL en fonction du panier du client et des paramètres de configuration du module (par exemple, `cshare_show_prices`, `cshare_show_products`).
    *   `cartshare/views/templates/front/shopping-cart.tpl`
        *   **Objectif :** Ce template pourrait être un remplacement ou un bloc supplémentaire spécifiquement conçu pour être inclus dans la page standard du panier d'achat de PrestaShop, potentiellement pour rendre le bouton de partage ou d'autres contenus spécifiques au module directement dans le résumé du panier.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données :**
    *   Ce module ne crée pas de tables SQL personnalisées.
    *   Les paramètres de configuration sont stockés dans la table `ps_configuration`, en utilisant des clés telles que `CSHARE_APPID`, `CSHARE_VOUCHER`, `CSHARE_SHOW_PRICES`, etc.
    *   Les bons de réduction sont générés en tant qu'entrées `CartRule` PrestaShop standard, stockées dans `ps_cart_rule` et les tables associées.

-   **Table des hooks enregistrés :**

| Nom du hook | Moment d'exécution | Objectif technique |
|---|---|---|
| `displayHeader` | Dans la section `<head>` de chaque page. | Initialise le SDK Facebook, charge les actifs JS/CSS du module. |
| `displayShoppingcart` | Sur la page de résumé du panier d'achat. | Rend le bouton "Partager le panier sur Facebook" et la zone d'affichage du bon de réduction. |
| `displayOrderConfirmation` | Sur la page de confirmation de commande après un achat réussi. | Rend le bouton "Partager le panier sur Facebook" et la zone d'affichage du bon de réduction. |
| `displayShoppingCart` | (Duplicata de `displayShoppingcart` dans les informations du module, fait probablement référence au même hook) | Rend le bouton "Partager le panier sur Facebook" et la zone d'affichage du bon de réduction. |

## 5. Support officiel et mises à jour
Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module "Partage de panier Facebook + bon de réduction", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe s'engage à garantir le fonctionnement optimal du module avec votre boutique PrestaShop.
