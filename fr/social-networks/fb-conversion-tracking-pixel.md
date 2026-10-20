---
title: "Pixel de suivi des conversions Fb - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Pixel de suivi des conversions Fb' par MyPresta.eu."
sidebar:
  label: "Pixel de suivi des conversions Fb - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Fb conversion tracking pixel sur MyPresta.eu](https://mypresta.eu/modules/social-networks/fb-conversion-tracking-pixel.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/fb-conversion-tracking-pixel/)
>
> ---


# Pixel de suivi des conversions Fb

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard comme cURL, JSON et OpenSSL sont nécessaires au bon fonctionnement du module, en particulier pour les fonctionnalités de l'API de conversions (CAPI). Celles-ci sont généralement disponibles sur tous les environnements d'hébergement modernes.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, vous arriverez sur la page de configuration principale. C'est ici que vous connecterez votre boutique à Facebook et personnaliserez la manière dont les événements sont suivis.

#### Onglet Paramètres généraux

- **ID(s) de pixel :**

  - **Ce que fait ce paramètre :** Il s'agit de l'identifiant unique de votre Pixel Facebook. Vous pouvez le trouver dans votre Gestionnaire de publicités Facebook ou votre Gestionnaire d'événements. Vous pouvez saisir plusieurs ID de pixel séparés par des virgules si vous gérez plusieurs pixels.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est rempli :* Le module intégrera le code du Pixel Facebook sur le front office de votre boutique, envoyant des données aux ID de pixel spécifiés.
    - *Lorsqu'il est vide :* Aucun suivi du Pixel Facebook ne sera effectué.
  - **Valeur recommandée :** Votre ID de Pixel Facebook principal.
  - **Scénario / exemple pour le marchand :** Vous avez un pixel principal pour votre marque et un pixel secondaire pour une ligne de produits spécifique. Saisissez les deux ici : `1234567890,9876543210`.
- **Jeton d'accès CAPI :**

  - **Ce que fait ce paramètre :** Ce jeton active l'API de conversions Facebook (CAPI), qui envoie les données de conversion directement de votre serveur à Facebook, contournant les limitations du navigateur (comme les bloqueurs de publicités ou les restrictions de cookies). Cela améliore la précision des données.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est rempli :* Le module tentera d'envoyer des événements côté serveur à Facebook en utilisant CAPI, en plus ou à la place des événements de pixel côté navigateur, selon vos autres paramètres.
    - *Lorsqu'il est vide :* Seul le suivi du pixel côté navigateur aura lieu (si l'ID de pixel est défini).
  - **Valeur recommandée :** Fortement recommandé d'utiliser CAPI pour une meilleure précision des données. Générez ce jeton dans votre Gestionnaire d'événements Facebook.
  - **Scénario / exemple pour le marchand :** Vous souhaitez garantir une précision maximale des données pour vos événements d'achat, même si les clients utilisent des bloqueurs de publicités. Vous générez un jeton d'accès dans le Gestionnaire d'événements Facebook et le collez ici.
- **Code d'événement de test :**

  - **Ce que fait ce paramètre :** Ce code est utilisé pour tester votre configuration CAPI dans le Gestionnaire d'événements Facebook. Lorsqu'il est saisi, le module enverra des événements de test, vous permettant de vérifier que votre suivi côté serveur fonctionne correctement.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est rempli :* Les événements CAPI incluront ce code de test, les rendant visibles dans l'onglet « Tester les événements » du Gestionnaire d'événements Facebook.
    - *Lorsqu'il est vide :* Les événements CAPI seront envoyés comme des événements en direct.
  - **Valeur recommandée :** À utiliser uniquement lorsque vous testez activement votre configuration CAPI. Supprimez-le une fois le test terminé.
  - **Scénario / exemple pour le marchand :** Vous venez de configurer CAPI et souhaitez confirmer qu'il envoie des données. Vous copiez le code de test du Gestionnaire d'événements Facebook, le collez ici, effectuez un achat test sur votre site, puis vérifiez l'onglet « Tester les événements » sur Facebook.
- **Mode de consentement :**

  - **Ce que fait ce paramètre :** Cette option s'intègre à la solution de consentement aux cookies de votre boutique (par exemple, les modules GDPR). Elle détermine si les événements du Pixel Facebook sont déclenchés uniquement après que le client a donné son consentement.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les événements du pixel ne se déclencheront que si le client a accepté les cookies.
    - *Lorsqu'il est désactivé :* Les événements du pixel se déclencheront quel que soit le consentement aux cookies (à utiliser avec prudence, selon les lois locales sur la confidentialité).
  - **Valeur recommandée :** « Oui » si vous opérez dans des régions avec des lois strictes sur la confidentialité (comme le GDPR en Europe).
  - **Scénario / exemple pour le marchand :** Votre boutique cible des clients dans l'UE. Vous activez ce paramètre pour vous conformer au GDPR, garantissant que les données du pixel ne sont collectées qu'auprès des utilisateurs qui acceptent explicitement l'utilisation des cookies.
- **Statuts payés :**

  - **Ce que fait ce paramètre :** Sélectionne les statuts de commande dans PrestaShop qui doivent déclencher un événement « Purchase » vers Facebook. Généralement, cela inclut des statuts comme « Paiement accepté » ou « Livré ».
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est sélectionné :* Les commandes atteignant ces statuts enverront un événement « Purchase » à Facebook.
    - *Lorsqu'il n'est pas sélectionné :* Les commandes n'enverront pas d'événement « Purchase » lorsqu'elles atteindront ces statuts.
  - **Valeur recommandée :** Sélectionnez tous les statuts qui représentent réellement une commande complétée et payée.
  - **Scénario / exemple pour le marchand :** Vous considérez une commande comme « payée » lorsqu'elle est « Paiement accepté » et « Expédiée ». Vous sélectionnez ces deux statuts.
- **Statuts de remboursement / annulation :**

  - **Ce que fait ce paramètre :** Sélectionne les statuts de commande qui indiquent un remboursement ou une annulation. Cela permet au module d'envoyer potentiellement un événement « Refund » ou « Cancel » (si pris en charge par l'API de Facebook et la version du module) ou d'éviter un suivi d'achat faussement positif.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est sélectionné :* Le module reconnaîtra ces commandes comme des non-achats ou des remboursements.
    - *Lorsqu'il n'est pas sélectionné :* Ces commandes pourraient toujours être comptées comme des achats si elles ont précédemment atteint un « statut payé ».
  - **Valeur recommandée :** Sélectionnez des statuts comme « Annulé », « Remboursé », « Erreur de paiement ».
  - **Scénario / exemple pour le marchand :** Un client annule une commande. Vous voulez vous assurer que cela n'est pas compté comme un achat réussi. Vous sélectionnez « Annulé » et « Remboursé » ici.

#### Onglet Paramètres avancés

- **Sélecteur CSS d'ajout au panier :**

  - **Ce que fait ce paramètre :** Il s'agit d'un paramètre technique qui aide le module à identifier le bouton « Ajouter au panier » sur vos pages produit. Si votre thème utilise un bouton non standard, vous devrez peut-être spécifier son sélecteur CSS.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est correct :* L'événement « AddToCart » se déclenchera de manière fiable lorsqu'un client cliquera sur le bouton.
    - *Lorsqu'il est incorrect ou vide (et que la détection automatique échoue) :* L'événement « AddToCart » pourrait ne pas se déclencher, entraînant des données manquantes.
  - **Valeur recommandée :** Laissez vide d'abord ; le module détecte souvent automatiquement. Si des événements « AddToCart » sont manquants, consultez le développeur de votre thème ou utilisez l'inspecteur de votre navigateur pour trouver le sélecteur CSS correct (par exemple, `.add-to-cart-button`).
  - **Scénario / exemple pour le marchand :** Votre thème personnalisé a un bouton « Ajouter au panier » unique. Vous inspectez le bouton dans votre navigateur et trouvez que sa classe est `my-custom-add-button`. Vous saisissez `.my-custom-add-button` ici.
- **Sélecteur CSS de prix du produit :**

  - **Ce que fait ce paramètre :** Similaire au sélecteur d'ajout au panier, cela aide le module à trouver avec précision le prix du produit sur la page, en particulier pour les prix dynamiques ou les mises en page de thème spécifiques.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est correct :* Le paramètre « value » pour des événements comme « ViewContent » et « AddToCart » reflétera avec précision le prix du produit.
    - *Lorsqu'il est incorrect ou vide (et que la détection automatique échoue) :* Le paramètre « value » pourrait être manquant ou incorrect, ce qui aurait un impact sur l'optimisation des publicités.
  - **Valeur recommandée :** Laissez vide d'abord. Si les valeurs de prix sont incorrectes dans le Gestionnaire d'événements Facebook, trouvez le sélecteur CSS correct (par exemple, `.current-price span[itemprop="price"]`).
  - **Scénario / exemple pour le marchand :** Votre page produit affiche les prix d'une manière non standard. Vous identifiez le sélecteur CSS pour l'élément de prix afin de vous assurer que Facebook reçoit la valeur correcte.
- **Identification du produit :**

  - **Ce que fait ce paramètre :** Détermine quel identifiant de produit (ID) votre boutique envoie à Facebook. Les options incluent généralement `ID` (ID interne du produit de PrestaShop), `Reference` (SKU de votre produit) ou `EAN13` / `UPC` (numéros de code-barres). C'est crucial pour faire correspondre les produits dans votre catalogue Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini :* Facebook recevra le type d'ID choisi, qui doit correspondre aux ID de votre catalogue de produits Facebook pour que les publicités dynamiques fonctionnent.
    - *Lorsqu'il ne correspond pas à votre catalogue :* Les publicités dynamiques pourraient ne pas afficher les produits corrects ou pourraient ne pas s'afficher du tout.
  - **Valeur recommandée :** Choisissez l'ID que vous utilisez de manière cohérente dans votre catalogue de produits Facebook. `Reference` (SKU) est souvent un bon choix s'il est unique.
  - **Scénario / exemple pour le marchand :** Votre catalogue de produits Facebook utilise le SKU de votre produit comme identifiant unique. Vous sélectionnez « Référence » ici pour assurer une correspondance parfaite.
- **Séparateur :**

  - **Ce que fait ce paramètre :** Si vous utilisez une combinaison d'ID de produit et d'ID d'attribut (par exemple, pour différentes tailles/couleurs), cela définit le caractère utilisé pour les séparer dans l'ID Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini :* L'ID de produit envoyé à Facebook sera `ID_Produit` + `Séparateur` + `ID_Attribut`.
    - *Lorsqu'il est vide :* Seul l'ID de produit de base pourrait être envoyé, ce qui pourrait causer des problèmes avec le suivi de variations de produits spécifiques.
  - **Valeur recommandée :** Un séparateur courant comme `-` ou `_`.
  - **Scénario / exemple pour le marchand :** Vous vendez un T-shirt (ID 123) en différentes tailles (ID d'attribut 10 pour S, 11 pour M). Si vous définissez le séparateur sur `-`, Facebook recevra `123-10` pour un T-shirt de petite taille.
- **Préfixe d'ID de produit / Suffixe d'ID de produit :**

  - **Ce que fait ce paramètre :** Vous permet d'ajouter du texte avant ou après l'ID de produit envoyé à Facebook. C'est utile si les ID de votre catalogue de produits Facebook ont un format spécifique qui diffère de vos ID PrestaShop.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini :* L'ID de produit final envoyé à Facebook sera `Préfixe` + `ID_Produit` + `Suffixe`.
    - *Lorsqu'il est vide :* Seul l'ID de produit brut (et l'ID de séparateur/attribut si applicable) est envoyé.
  - **Valeur recommandée :** Laissez vide, sauf si votre catalogue de produits Facebook l'exige.
  - **Scénario / exemple pour le marchand :** Votre catalogue de produits Facebook exige que tous les ID de produit commencent par « PS_ ». Vous saisissez `PS_` dans le champ « Préfixe d'ID de produit ».
- **Devise cible :**

  - **Ce que fait ce paramètre :** Spécifie la devise dans laquelle les valeurs d'événement (comme le montant de l'achat) sont envoyées à Facebook. C'est crucial pour un reporting précis et l'optimisation des publicités, en particulier pour les boutiques multi-devises.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini :* Toutes les valeurs d'événement seront converties et envoyées dans cette devise cible.
    - *Lorsqu'il est vide :* Le module tentera d'utiliser la devise du contexte de la boutique actuelle ou la devise sélectionnée par le client.
  - **Valeur recommandée :** Votre devise publicitaire principale (par exemple, USD, EUR).
  - **Scénario / exemple pour le marchand :** Votre boutique vend en EUR, USD et GBP, mais toutes vos publicités Facebook sont gérées en USD. Vous définissez « Devise cible » sur « USD » pour vous assurer que toutes les valeurs de conversion sont rapportées de manière cohérente en USD.

#### Onglet Paramètres de suivi des événements

Cette section vous permet d'activer ou de désactiver des événements spécifiques du Pixel Facebook. N'activez que les événements que vous souhaitez suivre activement.

- **Événement Pageview :**

  - **Ce que fait ce paramètre :** Suit lorsqu'un client consulte n'importe quelle page de votre site web.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un événement `PageView` est envoyé à chaque chargement de page.
    - *Lorsqu'il est désactivé :* Aucun événement `PageView` n'est envoyé.
  - **Valeur recommandée :** Oui. C'est un événement fondamental pour tout suivi.
- **Événement Purchase :**

  - **Ce que fait ce paramètre :** Suit lorsqu'un client effectue un achat. C'est l'événement de conversion le plus critique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un événement `Purchase` est envoyé sur la page de confirmation de commande et/ou via CAPI lorsqu'une commande atteint un « statut payé ».
    - *Lorsqu'il est désactivé :* Aucun événement `Purchase` n'est envoyé.
  - **Valeur recommandée :** Oui. Absolument essentiel pour la publicité e-commerce.
- **Événement ViewContent :**

  - **Ce que fait ce paramètre :** Suit lorsqu'un client consulte une page produit.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un événement `ViewContent` est envoyé lorsqu'une page produit est chargée.
    - *Lorsqu'il est désactivé :* Aucun événement `ViewContent` n'est envoyé.
  - **Valeur recommandée :** Oui. Important pour les publicités dynamiques de produits et le remarketing.
- **Événement AddToCart :**

  - **Ce que fait ce paramètre :** Suit lorsqu'un client ajoute un article à son panier.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un événement `AddToCart` est envoyé lorsqu'un article est ajouté au panier.
    - *Lorsqu'il est désactivé :* Aucun événement `AddToCart` n'est envoyé.
  - **Valeur recommandée :** Oui. Crucial pour les campagnes de récupération de paniers abandonnés.
- **Événement RemoveFromCart :**

  - **Ce que fait ce paramètre :** Suit lorsqu'un client retire un article de son panier.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un événement `RemoveFromCart` est envoyé lorsqu'un article est retiré.
    - *Lorsqu'il est désactivé :* Aucun événement `RemoveFromCart` n'est envoyé.
  - **Valeur recommandée :** Oui. Peut fournir des informations sur le comportement des clients et l'intérêt pour les produits.
- **Événement InitiateCheckout :**

  - **Ce que fait ce paramètre :** Suit lorsqu'un client commence le processus de commande.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un événement `InitiateCheckout` est envoyé lorsque le client entre dans la première étape de la commande.
    - *Lorsqu'il est désactivé :* Aucun événement `InitiateCheckout` n'est envoyé.
  - **Valeur recommandée :** Oui. Utile pour comprendre les performances de l'entonnoir de commande.
- **Événement Search :**

  - **Ce que fait ce paramètre :** Suit lorsqu'un client utilise la fonction de recherche interne de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un événement `Search` est envoyé avec la requête de recherche.
    - *Lorsqu'il est désactivé :* Aucun événement `Search` n'est envoyé.
  - **Valeur recommandée :** Oui. Fournit des données précieuses sur ce que les clients recherchent.
- **Événement AddToWishlist :**

  - **Ce que fait ce paramètre :** Suit lorsqu'un client ajoute un produit à sa liste de souhaits.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un événement `AddToWishlist` est envoyé.
    - *Lorsqu'il est désactivé :* Aucun événement `AddToWishlist` n'est envoyé.
  - **Valeur recommandée :** Oui, si votre boutique utilise une fonction de liste de souhaits.
- **Événement AddPaymentInfo :**

  - **Ce que fait ce paramètre :** Suit lorsqu'un client sélectionne un mode de paiement pendant la commande.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un événement `AddPaymentInfo` est envoyé.
    - *Lorsqu'il est désactivé :* Aucun événement `AddPaymentInfo` n'est envoyé.
  - **Valeur recommandée :** Oui. Aide à analyser les préférences de mode de paiement et les abandons potentiels.
- **Événement Contact :**

  - **Ce que fait ce paramètre :** Suit lorsqu'un client visite votre page de contact.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un événement `Contact` est envoyé.
    - *Lorsqu'il est désactivé :* Aucun événement `Contact` n'est envoyé.
  - **Valeur recommandée :** Oui. Utile pour suivre les demandes de service client.
- **Événement Lead :**

  - **Ce que fait ce paramètre :** Suit lorsqu'un client effectue une action qui indique un intérêt pour vos produits ou services, mais qui n'est pas un achat direct (par exemple, inscription à la newsletter, création de compte).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un événement `Lead` est envoyé lors de l'inscription à la newsletter et/ou de la création de compte.
    - *Lorsqu'il est désactivé :* Aucun événement `Lead` n'est envoyé.
  - **Valeur recommandée :** Oui. Important pour les campagnes de génération de leads.
- **Événement CompleteRegistration :**

  - **Ce que fait ce paramètre :** Suit lorsqu'un client crée un compte avec succès sur votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un événement `CompleteRegistration` est envoyé.
    - *Lorsqu'il est désactivé :* Aucun événement `CompleteRegistration` n'est envoyé.
  - **Valeur recommandée :** Oui. Utile pour suivre l'acquisition de nouveaux clients.

#### Onglet Statistiques en direct

Cet onglet fournit des informations en temps réel sur les événements envoyés de votre boutique à Facebook, vous aidant à surveiller la santé de votre pixel.

- **Conserver les événements pendant (jours) :**

  - **Ce que fait ce paramètre :** Détermine la durée pendant laquelle le module stocke les données d'événement localement pour l'affichage dans l'onglet Statistiques en direct.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini :* Les données d'événement plus anciennes que ce nombre de jours seront automatiquement purgées.
    - *Lorsqu'il est défini sur 0 :* Les événements ne sont pas stockés localement (et les Statistiques en direct n'afficheront pas de données).
  - **Valeur recommandée :** 7 à 30 jours, selon la quantité de données historiques que vous souhaitez consulter.
  - **Scénario / exemple pour le marchand :** Vous souhaitez consulter les événements de la dernière semaine. Vous définissez ceci sur `7`.
- **Intervalle d'interrogation en direct (secondes) :**

  - **Ce que fait ce paramètre :** Contrôle la fréquence à laquelle l'onglet Statistiques en direct se rafraîchit pour afficher de nouveaux événements.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini :* Le tableau des Statistiques en direct se mettra à jour toutes les X secondes.
    - *Lorsqu'il est défini sur 0 :* Les Statistiques en direct ne se rafraîchiront pas automatiquement.
  - **Valeur recommandée :** 5 à 10 secondes pour une surveillance active.
  - **Scénario / exemple pour le marchand :** Vous testez activement votre pixel et souhaitez voir les événements apparaître presque instantanément. Vous définissez ceci sur `5`.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Paramètres généraux | ID(s) de pixel | Votre ID de Pixel Facebook | Connecte votre boutique au Pixel Facebook pour le suivi. |
| Paramètres généraux | Jeton d'accès CAPI | Votre jeton d'accès CAPI | Active le suivi côté serveur pour une meilleure précision des données. |
| Paramètres généraux | Code d'événement de test | Vide (à utiliser uniquement pour les tests) | Envoie des événements de test au Gestionnaire d'événements Facebook. |
| Paramètres généraux | Mode de consentement | Oui (pour la conformité GDPR) | Déclenche les événements du pixel uniquement après le consentement du client. |
| Paramètres généraux | Statuts payés | Paiement accepté, Livré | Définit les statuts de commande qui déclenchent un événement « Purchase ». |
| Paramètres généraux | Statuts de remboursement / annulation | Annulé, Remboursé | Définit les statuts de commande considérés comme non-achat. |
| Paramètres avancés | Sélecteur CSS d'ajout au panier | Vide (détection automatique) | Aide à identifier le bouton « Ajouter au panier » pour le suivi. |
| Paramètres avancés | Sélecteur CSS de prix du produit | Vide (détection automatique) | Aide à identifier le prix du produit pour les valeurs d'événement. |
| Paramètres avancés | Identification du produit | Référence (SKU) | Détermine quel ID de produit est envoyé à Facebook. |
| Paramètres avancés | Séparateur | - (tiret) | Séparateur pour l'ID de produit et l'ID d'attribut. |
| Paramètres avancés | Préfixe d'ID de produit | Vide | Ajoute un préfixe à l'ID de produit envoyé à Facebook. |
| Paramètres avancés | Suffixe d'ID de produit | Vide | Ajoute un suffixe à l'ID de produit envoyé à Facebook. |
| Paramètres avancés | Devise cible | Votre devise publicitaire principale | Convertit les valeurs d'événement dans une devise spécifique. |
| Suivi des événements | Événement Pageview | Oui | Suit toutes les vues de page. |
| Suivi des événements | Événement Purchase | Oui | Suit les achats terminés. |
| Suivi des événements | Événement ViewContent | Oui | Suit les vues de page produit. |
| Suivi des événements | Événement AddToCart | Oui | Suit les articles ajoutés au panier. |
| Suivi des événements | Événement RemoveFromCart | Oui | Suit les articles retirés du panier. |
| Suivi des événements | Événement InitiateCheckout | Oui | Suit le début de la commande. |
| Suivi des événements | Événement Search | Oui | Suit les recherches internes du site. |
| Suivi des événements | Événement AddToWishlist | Oui (si la liste de souhaits est utilisée) | Suit les articles ajoutés à la liste de souhaits. |
| Suivi des événements | Événement AddPaymentInfo | Oui | Suit les informations de paiement ajoutées lors de la commande. |
| Suivi des événements | Événement Contact | Oui | Suit les visites sur la page de contact. |
| Suivi des événements | Événement Lead | Oui | Suit les inscriptions à la newsletter/créations de compte. |
| Suivi des événements | Événement CompleteRegistration | Oui | Suit les enregistrements de compte réussis. |
| Statistiques en direct | Conserver les événements pendant (jours) | 7-30 | Période de rétention pour les données d'événements locales. |
| Statistiques en direct | Intervalle d'interrogation en direct (secondes) | 5-10 | Taux de rafraîchissement pour l'affichage des Statistiques en direct. |

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### AdminFbpixelAjaxController (Back Office > Modules > Pixel de suivi des conversions Fb > Onglet Statistiques en direct)

Ce contrôleur alimente l'onglet « Statistiques en direct » dans la configuration du module. Il n'a pas d'élément de menu séparé mais fait partie intégrante de l'interface de configuration du module.

- **Nom de l'écran et emplacement du menu :** Accessible via **Modules > Gestionnaire de modules > Pixel de suivi des conversions Fb > Configurer**, puis cliquez sur l'onglet **« Statistiques en direct »**.
- **Actions et paramètres disponibles :** Cet écran affiche une grille ou un tableau des événements récents du Pixel Facebook qui ont été déclenchés depuis votre boutique. Il affiche des détails tels que le nom de l'événement (par exemple, `PageView`, `AddToCart`, `Purchase`), l'horodatage, l'ID de pixel associé, et souvent les paramètres envoyés avec l'événement (par exemple, ID de produit, valeur, devise).
- **Effet des modifications :** Il n'y a pas de « paramètres » directs à modifier sur cet écran. C'est un outil de surveillance. Les données affichées sont influencées par les paramètres « Conserver les événements pendant (jours) » et « Intervalle d'interrogation en direct (secondes) » sur la même page de configuration.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vérifiez régulièrement cet onglet, surtout après avoir apporté des modifications à votre boutique ou lancé de nouveaux produits, pour vous assurer que votre Pixel Facebook se déclenche correctement et envoie des données précises. C'est votre première ligne de défense pour le dépannage des problèmes de pixel avant de vérifier le Gestionnaire d'événements Facebook.

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mon extension Chrome Facebook Pixel Helper n'affiche aucun pixel ou des erreurs. Que dois-je faire ?**

- **R :** Tout d'abord, assurez-vous d'avoir saisi correctement votre ou vos « ID de pixel » dans la configuration du module.
- **R :** Vérifiez si le « Mode de consentement » est activé. Si c'est le cas, vous devrez peut-être accepter les cookies sur votre boutique pour que le pixel se déclenche.
- **R :** Videz le cache de votre PrestaShop (Paramètres avancés > Performances > Vider le cache).
- **R :** Si vous utilisez un thème personnalisé, il peut y avoir des conflits. Passez temporairement au thème PrestaShop par défaut pour exclure cette possibilité.
- **R :** Utilisez l'outil « Tester les événements » de Facebook dans le Gestionnaire d'événements pour voir si les événements sont reçus.

**Q2 : Mes événements d'achat ne s'affichent pas correctement dans le Gestionnaire d'événements Facebook.**

- **R :** Vérifiez que vos « Statuts payés » sont correctement sélectionnés dans la configuration du module. Seules les commandes atteignant ces statuts déclencheront un événement d'achat.
- **R :** Si vous utilisez CAPI, assurez-vous que votre « Jeton d'accès CAPI » est correct et testez-le à l'aide de la fonction « Code d'événement de test ».
- **R :** Vérifiez si votre « Devise cible » est correctement définie, en particulier pour les boutiques multi-devises.
- **R :** Consultez l'onglet « Statistiques en direct » dans la configuration du module pour voir si le module enregistre en interne les événements d'achat.

**Q3 : Les publicités dynamiques de produits n'affichent pas les produits corrects ou aucun produit du tout.**

- **R :** La raison la plus courante est une non-concordance entre votre paramètre « Identification du produit » dans le module et les ID de votre catalogue de produits Facebook. Assurez-vous qu'ils sont identiques (par exemple, si votre catalogue utilise le SKU, définissez le module sur « Référence »).
- **R :** Assurez-vous que votre catalogue de produits Facebook est à jour et exempt d'erreurs.
- **R :** Vérifiez que les événements « ViewContent » et « AddToCart » se déclenchent correctement avec le paramètre `content_ids` correspondant à vos ID de catalogue.

**Q4 : Comment puis-je assurer la conformité au GDPR ou à d'autres lois sur la confidentialité avec ce module ?**

- **R :** Activez le paramètre « Mode de consentement » dans le module. Cela s'intégrera à votre module de consentement aux cookies existant (s'il est correctement configuré) pour ne déclencher le pixel qu'après le consentement explicite de l'utilisateur.
- **R :** Assurez-vous que la politique de confidentialité de votre boutique indique clairement que vous utilisez le Pixel Facebook à des fins de publicité et d'analyse, et comment les utilisateurs peuvent se désinscrire ou gérer leurs préférences en matière de cookies.

**Q5 : L'événement « Ajouter au panier » ne se déclenche pas sur ma page produit.**

- **R :** Votre thème peut avoir un bouton « Ajouter au panier » personnalisé que le module ne peut pas détecter automatiquement. Essayez d'inspecter le bouton « Ajouter au panier » sur votre page produit à l'aide des outils de développement de votre navigateur (clic droit > Inspecter) pour trouver sa classe ou son ID CSS. Ensuite, saisissez-le dans le champ « Sélecteur CSS d'ajout au panier » de la configuration du module (par exemple, `.my-custom-atc-button` ou `#add_to_cart_button`).

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, webmasters de boutique et agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module `Fb conversion tracking pixel` suit une architecture de module PrestaShop standard, exploitant les hooks pour l'injection d'événements côté front-office et un AdminController pour les interactions AJAX côté back-office (Statistiques en direct). Il s'appuie fortement sur un modèle de fabrique (`FbpixelTrackerFactory`) pour gérer différents mécanismes de suivi (pixel côté navigateur, CAPI côté serveur). Les données d'événement sont collectées et traitées par des classes dédiées (`FbpixelEvents`, `FbpixelPixelTracker`, `FbpixelCapiTracker`) puis dispatchées. La configuration est stockée dans `ps_configuration`. Le module comprend également des outils robustes pour le débogage et les vérifications de santé.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :

  - `controllers/front/ajax.php`
    - **Nom de la classe :** `FbpixelAjaxModuleFrontController` (étend `ModuleFrontController`)
    - **Responsabilité :** Gère les requêtes AJAX du front-office, principalement pour la collecte et l'enregistrement des données d'événements en temps réel pour la fonction Statistiques en direct. Il peut également être utilisé pour des déclencheurs d'événements spécifiques qui ne peuvent pas être gérés uniquement côté client (par exemple, `RemoveFromCart` après une mise à jour du panier).
  - `controllers/front/cron.php`
    - **Nom de la classe :** `FbpixelCronModuleFrontController` (étend `ModuleFrontController`)
    - **Responsabilité :** Conçu pour être appelé par une tâche cron. Ce contrôleur est probablement responsable du traitement des événements CAPI en file d'attente, de l'exécution du nettoyage des données (par exemple, la purge des anciennes entrées des Statistiques en direct) ou d'autres tâches planifiées.
  - `controllers/front/index.php`
    - **Nom de la classe :** `FbpixelIndexModuleFrontController` (étend `ModuleFrontController`)
    - **Responsabilité :** Un contrôleur de remplacement ou par défaut, souvent utilisé pour empêcher l'affichage du contenu du répertoire ou fournir une réponse par défaut pour les routes spécifiques au module.
  - `controllers/front/sync.php`
    - **Nom de la classe :** `FbpixelSyncModuleFrontController` (étend `ModuleFrontController`)
    - **Responsabilité :** Gère potentiellement les tâches de synchronisation, telles que l'envoi de mises à jour de catalogue de produits ou d'autres données à Facebook, ou la réception de données de Facebook.
- **Contrôleurs d'administration Back-Office** :

  - `controllers/admin/AdminFbpixelAjaxController.php`
    - **Nom de la classe :** `AdminFbpixelAjaxController` (étend `ModuleAdminController`)
    - **Nom de l'onglet :** Pas un onglet autonome, mais intégré à la configuration du module.
    - **Entité gérée :** Gère les requêtes AJAX de la page de configuration back-office du module, spécifiquement pour la récupération et l'affichage des données d'événements des « Statistiques en direct ». Il fournit les données pour le template `recent-events.tpl`.

### 4.3 Classes et modèles principaux (`classes/`)

- `fbpixel/classes/autoload.php` : Gère le chargement des classes personnalisées pour le module.
- `fbpixel/classes/FbpixelCapiClient.php` :
  - **Responsabilité :** Encapsule la logique pour effectuer des requêtes HTTP vers l'API de conversions de Facebook. Gère l'authentification, le formatage des requêtes et la gestion des erreurs.
- `fbpixel/classes/FbpixelCapiTracker.php` :
  - **Responsabilité :** Implémente l'`FbpixelTrackerInterface` pour le suivi des événements côté serveur. Formate les données d'événement selon les spécifications CAPI et les envoie via `FbpixelCapiClient`.
- `fbpixel/classes/FbpixelCatalogDoctor.php` :
  - **Responsabilité :** Fournit des outils et une logique pour diagnostiquer les problèmes liés à la correspondance du catalogue de produits et à la cohérence des données entre PrestaShop et Facebook.
- `fbpixel/classes/FbpixelConsent.php` :
  - **Responsabilité :** Gère et vérifie l'état du consentement de l'utilisateur, s'intégrant aux mécanismes de consentement aux cookies de PrestaShop (si disponibles) pour assurer la conformité GDPR.
- `fbpixel/classes/FbpixelCurrencyHelper.php` :
  - **Responsabilité :** Classe utilitaire pour la conversion et le formatage des devises, garantissant que les valeurs d'événement sont envoyées dans la devise cible correcte.
- `fbpixel/classes/FbpixelEmqCoach.php` :
  - **Responsabilité :** Fournit probablement des conseils ou des recommandations pour améliorer la qualité de correspondance des événements (EMQ) pour les événements Facebook.
- `fbpixel/classes/FbpixelEventId.php` :
  - **Responsabilité :** Génère et gère des ID d'événement uniques, cruciaux pour la déduplication entre les événements côté navigateur et côté serveur.
- `fbpixel/classes/FbpixelEvents.php` :
  - **Responsabilité :** Une classe centrale pour définir et gérer les différents types d'événements du Pixel Facebook (PageView, Purchase, AddToCart, etc.) et leurs paramètres standard.
- `fbpixel/classes/FbpixelHealthScore.php` :
  - **Responsabilité :** Calcule et affiche un « score de santé » pour la configuration du pixel, identifiant les problèmes potentiels ou les domaines à améliorer.
- `fbpixel/classes/FbpixelLiveStats.php` :
  - **Table de base de données :** `ps_fbpixel_events` (probablement, basé sur la fonctionnalité)
  - **Étend :** Probablement `ObjectModel`
  - **Responsabilité :** Stocke et récupère les données d'événement localement pour la fonction « Statistiques en direct » dans le back office. Gère la rétention et la purge des données.
- `fbpixel/classes/FbpixelPixelRules.php` :
  - **Responsabilité :** Définit les règles et les conditions pour le déclenchement d'événements de pixel spécifiques, potentiellement basées sur le type de page, les actions de l'utilisateur ou la configuration.
- `fbpixel/classes/FbpixelPixelTracker.php` :
  - **Responsabilité :** Implémente l'`FbpixelTrackerInterface` pour le suivi des événements côté navigateur. Génère le code JavaScript pour les appels `fbq()` et l'injecte dans le front office.
- `fbpixel/classes/FbpixelProductIdResolver.php` :
  - **Responsabilité :** Résout l'ID de produit et l'ID d'attribut corrects en fonction de la configuration du module (préfixe, suffixe, séparateur, type d'ID choisi) pour l'envoi à Facebook.
- `fbpixel/classes/FbpixelTrackerFactory.php` :
  - **Responsabilité :** Une classe de fabrique qui instancie le traqueur approprié (par exemple, `FbpixelPixelTracker` pour le navigateur, `FbpixelCapiTracker` pour le serveur) en fonction de la configuration et du contexte du module.
- `fbpixel/classes/FbpixelTrackerInterface.php` :
  - **Responsabilité :** Définit une interface commune pour toutes les classes de suivi, garantissant des signatures de méthode cohérentes pour la distribution des événements.
- `fbpixel/classes/FbpixelUserData.php` :
  - **Responsabilité :** Collecte et formate les données utilisateur (par exemple, e-mail, téléphone, adresse IP) pour l'envoi avec les événements CAPI, crucial pour la qualité de correspondance des événements.
- `fbpixel/classes/index.php` : Fichier vide, généralement utilisé pour empêcher l'affichage du contenu du répertoire.

### 4.4 Actifs JavaScript (`views/js/`)

- `fbpixel/lib/searchTool/views/js/autocomplete.js` :
  - **Portée :** Back-office.
  - **Détails :** Fournit une fonctionnalité d'autocomplétion pour les champs de saisie, probablement utilisée dans la configuration du module pour sélectionner des produits, des catégories ou d'autres entités.
- `fbpixel/views/js/fbpixel-admin.js` :
  - **Portée :** Back-office.
  - **Détails :** Gère la logique administrative générale pour la page de configuration du module, y compris les soumissions de formulaires, le changement d'onglet et potentiellement les appels AJAX à `AdminFbpixelAjaxController`.
- `fbpixel/views/js/fbpixel-debug.js` :
  - **Portée :** Front-office (conditionnel).
  - **Détails :** Fournit des informations de débogage dans la console du navigateur ou une superposition visuelle, montrant quels événements de pixel se déclenchent et leurs paramètres. Activé par un paramètre de mode de débogage.
- `fbpixel/views/js/fbpixel-ghost.js` :
  - **Portée :** Front-office.
  - **Détails :** Probablement un script côté client qui aide à détecter et à suivre les événements qui pourraient autrement être manqués par l'observation DOM standard, tels que le chargement de contenu dynamique ou des interactions AJAX spécifiques.
- `fbpixel/views/js/fbpixel-live.js` :
  - **Portée :** Back-office.
  - **Détails :** Alimente l'onglet « Statistiques en direct », effectuant des requêtes AJAX à `AdminFbpixelAjaxController` pour récupérer et afficher les données d'événements en temps réel, et gérant l'intervalle d'interrogation.
- `fbpixel/views/js/fbpixel-wizard.js` :
  - **Portée :** Back-office.
  - **Détails :** Gère l'assistant de configuration étape par étape, guidant le marchand à travers la configuration initiale.
- `fbpixel/views/js/fbpixel.js` :
  - **Portée :** Front-office.
  - **Détails :** Le JavaScript côté client principal pour le Pixel Facebook. Il initialise la fonction `fbq()`, gère les écouteurs d'événements pour `AddToCart`, `RemoveFromCart`, `Search`, `InitiateCheckout`, etc., et envoie les événements à Facebook. Il gère également les sélecteurs CSS pour les éléments dynamiques.
- `fbpixel/views/js/mp-collect.js` :
  - **Portée :** Front-office.
  - **Détails :** Probablement un script utilitaire pour collecter des points de données spécifiques du front-office, éventuellement liés au comportement de l'utilisateur ou à des facteurs environnementaux, afin d'améliorer les paramètres d'événement.
- `fbpixel/views/js/mp-front.js` :
  - **Portée :** Front-office.
  - **Détails :** Utilitaires JavaScript généraux ou fonctions d'aide côté front-office utilisés par le module.
- `fbpixel/views/js/mp-inspect.js` :
  - **Portée :** Front-office (conditionnel).
  - **Détails :** Fournit un outil d'inspection, éventuellement une superposition visuelle, pour aider à déboguer et à vérifier les événements de pixel directement sur la boutique.

### 4.5 Feuilles de style CSS (`views/css/`)

- `fbpixel/lib/searchTool/views/css/autocomplete.css` :
  - **Portée :** Back-office.
  - **Détails :** Styles pour les listes déroulantes d'autocomplétion et les champs de saisie utilisés dans l'interface d'administration.
- `fbpixel/views/css/fbpixel-admin.css` :
  - **Portée :** Style du formulaire d'administration du back-office.
  - **Détails :** Style de la page de configuration du module, des onglets, des champs de saisie et du tableau des Statistiques en direct.
- `fbpixel/views/css/fbpixel-debug.css` :
  - **Portée :** Front-office (conditionnel).
  - **Détails :** Styles pour la superposition de débogage ou la sortie console, rendant les informations de débogage plus lisibles.
- `fbpixel/views/css/mp-inspect.css` :
  - **Portée :** Front-office (conditionnel).
  - **Détails :** Styles pour l'outil d'inspection du front-office, s'il est activé.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :

  - `fbpixel/views/templates/hook/capi-pageview.tpl` : Rendu dans un hook (probablement `displayHeader` ou `actionFrontControllerSetMedia`) pour déclencher un événement `PageView` côté serveur via CAPI.
  - `fbpixel/views/templates/hook/debug.tpl` : Rend la superposition de débogage ou la sortie console pour le débogage du front-office.
  - `fbpixel/views/templates/hook/displayOrderConfirmation.tpl` : Rend l'événement `Purchase` côté navigateur sur la page de confirmation de commande.
  - `fbpixel/views/templates/hook/ghost.tpl` : Rend un élément ou un script caché pour la fonctionnalité `fbpixel-ghost.js`.
  - `fbpixel/views/templates/hook/header.tpl` : Rend le code d'initialisation de base du Pixel Facebook (`fbq('init', ...)` et `fbq('track', 'PageView')`) dans la section `<head>`, généralement via `displayHeader` ou `actionFrontControllerSetMedia`.
  - `fbpixel/views/templates/hook/payment.tpl` : Potentiellement utilisé pour suivre les événements `AddPaymentInfo` ou d'autres interactions liées au paiement.
  - `fbpixel/views/templates/hook/product-details.tpl` : Rend des scripts ou des données spécifiques aux pages produit, principalement pour les événements `ViewContent` et `AddToCart`, probablement injectés via `displayProductFooter` ou `displayProductAdditionalInfo`.
- **Templates d'administration (`views/templates/admin/`)** :

  - `fbpixel/lib/searchTool/views/scripts.tpl` : Inclut le JavaScript pour l'outil de recherche/autocomplétion dans l'administration.
  - `fbpixel/views/templates/admin/configure.tpl` : Le template principal pour la page de configuration du module, orchestrant tous les autres templates d'administration.
  - `fbpixel/views/templates/admin/doctor.tpl` : Affiche les résultats du `FbpixelCatalogDoctor` pour diagnostiquer les problèmes de catalogue.
  - `fbpixel/views/templates/admin/emq.tpl` : Affiche des informations ou des recommandations de `FbpixelEmqCoach` concernant la qualité de correspondance des événements.
  - `fbpixel/views/templates/admin/health.tpl` : Affiche le score de santé du pixel de `FbpixelHealthScore`.
  - `fbpixel/views/templates/admin/live-maintain.tpl` : Template pour la gestion des paramètres des statistiques en direct (rétention, intervalle d'interrogation).
  - `fbpixel/views/templates/admin/live.tpl` : Le template conteneur pour l'onglet « Statistiques en direct ».
  - `fbpixel/views/templates/admin/mode-context.tpl` : Affiche des informations spécifiques au contexte basées sur le mode de fonctionnement du pixel.
  - `fbpixel/views/templates/admin/mode-note-capi.tpl` : Affiche des notes ou des avertissements spécifiques à la configuration CAPI.
  - `fbpixel/views/templates/admin/mode-note-pixel.tpl` : Affiche des notes ou des avertissements spécifiques à la configuration du pixel côté navigateur.
  - `fbpixel/views/templates/admin/mode-picker.tpl` : Permet au marchand de sélectionner le mode de fonctionnement du pixel (par exemple, standard, débogage).
  - `fbpixel/views/templates/admin/pixels-list.tpl` : Affiche une liste des ID de pixel configurés.
  - `fbpixel/views/templates/admin/recent-events.tpl` : Rend le tableau des événements récents pour l'onglet « Statistiques en direct », rempli par `AdminFbpixelAjaxController`.
  - `fbpixel/views/templates/admin/tabs.tpl` : Rend la navigation par onglets pour la page de configuration du module.
  - `fbpixel/views/templates/admin/wizard.tpl` : Rend l'interface de l'assistant de configuration étape par étape.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** :

  - `ps_configuration` : Stocke tous les paramètres du module (par exemple, `FBPIXEL_ID`, `FBPIXEL_CAPI_TOKEN`, `FBPIXEL_PAID_STATUSES`).
  - `ps_fbpixel_events` (probablement) : Une table personnalisée créée par le module pour stocker les journaux d'événements locaux pour la fonction « Statistiques en direct ». Les colonnes comprendraient généralement `id_fbpixel_event`, `pixel_id`, `event_name`, `event_data` (JSON), `timestamp`, `ip_address`, `user_agent`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionFrontControllerSetMedia` | Avant le rendu du contrôleur frontal, pour ajouter JS/CSS. | Injecte le JS du Pixel Facebook principal, les scripts de suivi d'événements et le PageView CAPI. |
| `displayContactContent` | Sur la page de contact. | Déclenche l'événement `Contact`. |
| `displayOrderConfirmation` | Sur la page de confirmation de commande. | Déclenche l'événement `Purchase` côté navigateur. |
| `actionNewsletterRegistrationAfter` | Après une inscription à la newsletter. | Déclenche l'événement `Lead` (et potentiellement `CompleteRegistration` si combiné). |
| `displayProductFooter` | En bas des pages produit. | Injecte les données spécifiques au produit et l'événement `ViewContent`. |
| `displayHeader` | Dans la section `<head>` de toutes les pages du front-office. | Injecte le code de base du Pixel Facebook et l'événement `PageView`. |
| `DisplayProductButtons` | Près des boutons d'action du produit (par exemple, Ajouter au panier). | Peut injecter du JS pour l'écouteur d'événement `AddToCart`. |
| `ActionObjectProductInCartDeleteBefore` | Avant qu'un produit ne soit retiré du panier. | Déclenche potentiellement l'événement `RemoveFromCart`. |
| `DisplayProductAdditionalInfo` | Dans le bloc d'informations produit. | Injection de données produit supplémentaires ou déclencheurs d'événements. |
| `ActionCronJob` | Lors de l'exécution d'une tâche cron planifiée. | Déclenche le traitement des événements CAPI, le nettoyage des données. |
| `ActionObjectProductInCartDeleteAfter` | Après qu'un produit a été retiré du panier. | Déclenche l'événement `RemoveFromCart`. |
| `ActionValidateOrder` | Après qu'une commande a été validée avec succès. | Déclenche l'événement `Purchase` côté serveur via CAPI. |
| `DisplayLeftColumnProduct` | Dans la colonne de gauche des pages produit. | Moins courant pour le pixel, éventuellement pour des événements spécifiques liés au produit. |
| `displayExtraLeft` | Dans la colonne gauche supplémentaire. | Moins courant pour le pixel, éventuellement pour des événements spécifiques liés au produit. |
| `ActionCartUpdateQuantityBefore` | Avant la mise à jour de la quantité du panier. | Potentiellement utilisé pour suivre les changements qui pourraient entraîner un `RemoveFromCart`. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant le module « Pixel de suivi des conversions Fb ».
