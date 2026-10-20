---
title: "Google Customer Reviews pour PrestaShop - opt-in & enquête (GCR) - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Google Customer Reviews pour PrestaShop - opt-in & enquête (GCR) par MyPresta.eu."
sidebar:
  label: "Google Customer Reviews pour PrestaShop - opt-in & enquête (GCR) - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Google Customer Reviews for PrestaShop - opt-in & survey (GCR) sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/google-customer-reviews-for-prestashop-opt-in-survey-gcr.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/google-customer-reviews-for-prestashop-opt-in-survey-gcr/)
>
> ---


# Google Customer Reviews pour PrestaShop - opt-in & enquête (GCR)

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Pour accéder aux paramètres du module, allez dans **Modules > Gestionnaire de modules**, recherchez « Google Customer Reviews » et cliquez sur le bouton « Configurer ».

#### **ID Marchand Google**

- **Ce que fait ce paramètre :** Il s'agit de l'identifiant unique de votre compte Google Merchant Center. Google utilise cet ID pour associer les avis collectés à votre entreprise spécifique.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est correctement saisi :* Le script d'opt-in de Google Customer Reviews fonctionnera correctement, envoyant les données d'avis à votre compte Google Merchant Center.
  - *Lorsqu'il est incorrect ou vide :* Le script d'opt-in ne fonctionnera pas et Google ne collectera pas d'avis pour votre boutique.
- **Valeur recommandée :** Votre ID Google Merchant Center exact. Vous pouvez trouver cet ID en vous connectant à votre compte Google Merchant Center (merchant.google.com) – il est généralement affiché en haut à droite.
- **Scénario / exemple de marchand :** Si votre ID Google Merchant Center est `123456789`, vous entreriez `123456789` dans ce champ. Sans cela, Google ne sait pas à quel marchand attribuer les avis.

#### **Inclure la liste GTIN des produits dans la charge utile GCR**

- **Ce que fait ce paramètre :** Cette option contrôle si les numéros d'article commercial mondial (GTIN) des produits de la commande du client sont inclus lorsque les données d'opt-in sont envoyées à Google. Les GTIN (comme EAN, UPC, ISBN) aident Google à identifier des produits spécifiques pour les avis au niveau du produit.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (Oui) :* Le module tentera de récupérer et d'inclure les GTIN pour chaque produit de la commande. Cela permet à Google de potentiellement collecter des avis spécifiques aux produits, qui peuvent apparaître sur les pages produits et dans Google Shopping.
  - *Lorsqu'il est désactivé (Non) :* Seuls les avis sur le vendeur seront collectés. Les GTIN spécifiques aux produits ne seront pas envoyés, ce qui signifie que Google ne demandera pas aux clients d'avis sur les produits individuels de cette commande.
- **Valeur recommandée :** **Oui**. L'inclusion des GTIN est fortement recommandée si vous souhaitez collecter des avis au niveau du produit, qui sont très précieux pour la visibilité et la confiance des produits. Assurez-vous que les champs EAN/UPC de vos produits dans PrestaShop sont correctement remplis.
- **Scénario / exemple de marchand :** Si vous vendez un « T-shirt bleu » avec l'EAN `1234567890123`, l'activation de cette option garantit que Google sait *quel* produit le client a acheté, lui permettant d'évaluer cet article spécifique. Si elle est désactivée, Google ne demanderait qu'un avis général sur votre boutique.

#### **Décalage de livraison de secours (jours)**

- **Ce que fait ce paramètre :** Ce paramètre détermine le nombre estimé de jours après la passation d'une commande pendant lesquels le client est censé recevoir sa livraison. Google utilise cette date pour planifier l'envoi de l'e-mail d'enquête d'avis.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur un nombre spécifique (par exemple, 7) :* Le module calcule la date de livraison estimée en ajoutant ce nombre de jours à la date de la commande. Google enverra ensuite l'e-mail d'enquête autour de cette date de livraison calculée.
  - *Lorsqu'il est défini sur 0 ou un nombre très faible :* Google pourrait envoyer l'enquête trop tôt, avant que le client n'ait reçu son produit, ce qui entraînerait des avis non pertinents ou négatifs.
  - *Lorsqu'il est défini sur un nombre très élevé :* Google pourrait envoyer l'enquête trop tard, et le client pourrait avoir oublié les détails de son expérience d'achat.
- **Valeur recommandée :** Cela dépend de vos délais de livraison moyens. Un point de départ courant est de **7 jours**. Ajustez cela en fonction de vos performances de livraison réelles.
- **Scénario / exemple de marchand :** Si votre délai de livraison moyen est de 5 à 7 jours ouvrables, le réglage sur `7` jours est approprié. Si vous expédiez à l'international et que les livraisons prennent 2 à 3 semaines, vous pouvez le régler sur `14` ou `21` jours. Cela garantit que l'enquête arrive lorsque le client a eu le temps de recevoir et d'expérimenter le produit.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | ID Marchand Google | Votre ID Marchand | Lie les avis collectés à votre compte Google Merchant Center. **CRITIQUE pour le fonctionnement.** |
| Configuration du module | Inclure la liste GTIN des produits dans la charge utile GCR | Oui | Permet la collecte d'avis spécifiques aux produits en envoyant des identifiants de produit. |
| Configuration du module | Décalage de livraison de secours (jours) | 7 | Définit la date de livraison estimée pour la planification de l'enquête. Ajustez en fonction du délai de livraison moyen. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai configuré le module, mais je ne vois pas l'opt-in Google Customer Reviews sur ma page de confirmation de commande.**
R :

1.  **Vérifiez votre ID Marchand Google :** Vérifiez à nouveau que vous avez saisi le bon ID Marchand Google dans la configuration du module. Un ID incorrect empêchera le script de se charger.
2.  **Videz le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). Parfois, le contenu mis en cache peut empêcher l'apparition de nouveaux scripts de module.
3.  **Vérifiez les erreurs JavaScript :** Ouvrez la console de développement de votre navigateur (généralement F12) sur la page de confirmation de commande. Recherchez toute erreur JavaScript, qui pourrait indiquer un conflit avec un autre module ou votre thème.
4.  **Vérifiez l'exécution du hook :** Assurez-vous que votre thème appelle correctement le hook `displayOrderConfirmation`. Bien que standard, certains thèmes fortement personnalisés peuvent omettre ou renommer des hooks.

**Q : L'opt-in apparaît, mais je ne vois aucun avis dans mon Google Merchant Center.**
R :

1.  **Statut du Google Merchant Center :** Connectez-vous à votre compte Google Merchant Center et accédez à la section « Google Customer Reviews ». Assurez-vous que le programme est actif et qu'aucun problème n'est signalé. Il peut falloir un certain temps pour que les avis commencent à apparaître après la configuration initiale.
2.  **Taux d'opt-in des clients :** Tous les clients ne s'inscriront pas à l'enquête. Un certain pourcentage de clients doit accepter de recevoir l'e-mail d'enquête de Google.
3.  **Achèvement de l'enquête :** Même si un client s'inscrit, il doit toujours remplir l'enquête envoyée par Google.

**Q : Puis-je personnaliser l'apparence de l'opt-in ou du badge Google Customer Reviews ?**
R : L'apparence de l'invite d'opt-in et du badge Google Customer Reviews est contrôlée par Google et ne peut pas être directement personnalisée via le module PrestaShop. Google maintient une expérience de marque cohérente pour ces éléments. Vous pouvez cependant choisir où afficher le badge sur votre site via les paramètres de votre Google Merchant Center (par exemple, pied de page, barre latérale).

**Q : Mes produits ont des GTIN, mais je ne reçois pas d'avis au niveau du produit.**
R :

1.  **Activez les GTIN dans le module :** Assurez-vous que l'option « Inclure la liste GTIN des produits dans la charge utile GCR » est définie sur « Oui » dans la configuration du module.
2.  **Format GTIN correct :** Vérifiez que les GTIN de vos produits (EAN, UPC, ISBN) sont correctement saisis dans les pages de vos produits PrestaShop et qu'ils respectent les formats standard. Les GTIN mal formatés peuvent être ignorés par Google.
3.  **Discrétion de Google :** Même avec les GTIN fournis, Google décide en fin de compte s'il faut demander des avis au niveau du produit. Des facteurs tels que la popularité du produit et le volume d'avis peuvent influencer cela.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module `gcroptin` est un module PrestaShop léger conçu pour injecter le script officiel d'opt-in de Google Customer Reviews dans le hook `displayOrderConfirmation`. Il utilise la classe `Module` de PrestaShop et le moteur de templating `Smarty`. La logique principale réside dans le fichier principal du module, gérant le stockage de la configuration et l'injection dynamique de données dans le template Smarty. Il n'introduit pas de contrôleurs personnalisés, de modèles ou d'actifs JavaScript/CSS complexes, se concentrant uniquement sur l'injection de script requise avec des données de commande dynamiques.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. Le module fonctionne en se rattachant à `displayOrderConfirmation` et en rendant un template directement.
- **Contrôleurs d'administration Back-Office** : Aucun. Toute la configuration est gérée dans la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

- Aucune classe personnalisée ou instance d'`ObjectModel` n'est définie. Toute la logique est autonome dans `gcroptin.php`.

### 4.4 Actifs JavaScript (`views/js/`)

- Aucun. Le module génère directement le fragment de code JavaScript de Google Customer Reviews dans un template Smarty.

### 4.5 Feuilles de style CSS (`views/css/`)

- Aucune. L'interface utilisateur d'opt-in de Google Customer Reviews est rendue par le script de Google et ne nécessite pas de style personnalisé de la part du module.

### 4.6 Structure du template Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :
  - `gcroptin/views/templates/hook/gcroptin-order-confirmation.tpl`
    - **Objectif :** Ce template est rendu lorsque le hook `displayOrderConfirmation` est exécuté. Il contient le fragment de code JavaScript d'opt-in principal de Google Customer Reviews.
    - **Données disponibles :** Ce template reçoit diverses variables spécifiques à la commande du module, notamment :
      - `{$gcr_merchant_id}` : L'ID Google Merchant Center configuré dans le back office.
      - `{$gcr_order_id}` : L'ID de commande PrestaShop.
      - `{$gcr_currency_iso_code}` : Code ISO de la devise de la commande.
      - `{$gcr_total_paid}` : Montant total payé pour la commande.
      - `{$gcr_customer_email}` : Adresse e-mail du client.
      - `{$gcr_delivery_country}` : Code ISO du pays de livraison.
      - `{$gcr_delivery_date}` : Date de livraison estimée calculée.
      - `{$gcr_product_gtins_json}` : Tableau encodé en JSON des GTIN des produits (si activé).
    - **Sortie :** Il génère une balise `<script>` contenant le code d'opt-in de Google Customer Reviews, rempli dynamiquement avec les détails de la commande.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** : Le module ne crée aucune table de base de données personnalisée. Il stocke ses paramètres de configuration dans la table `ps_configuration` de PrestaShop en utilisant des clés comme `GCROPTIN_MERCHANT_ID`, `GCROPTIN_INCLUDE_GTIN` et `GCROPTIN_DELIVERY_OFFSET`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayOrderConfirmation` | Exécuté sur la page de confirmation de commande après un paiement réussi. | Injecte le fragment de code JavaScript d'opt-in de Google Customer Reviews avec les données de commande dynamiques. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant le module « Google Customer Reviews pour PrestaShop - opt-in & enquête (GCR) ».
