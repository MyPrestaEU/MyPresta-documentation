---
title: "Arukereso.hu - e-mails d'enquête du programme d'achat de confiance - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Arukereso.hu - e-mails d'enquête du programme d'achat de confiance par MyPresta.eu."
sidebar:
  label: "Arukereso.hu - e-mails d'enquête du programme d'achat de confiance - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Arukereso.hu - trusted purchase program survey emails sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/arukeresohu-trusted-purchase-program-survey-emails.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/arukeresohu-trusted-purchase-program-survey-emails/)
>
> ---


# Arukereso.hu - e-mails d'enquête du programme d'achat de confiance

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration spéciale du serveur n'est généralement nécessaire.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal et unique du module Arukereso.hu. Vous pouvez y accéder en naviguant vers **Modules > Gestionnaire de modules**, en recherchant « Arukereso.hu » et en cliquant sur « Configurer ».

#### 2.1.1 Arukereso.hu WebApiKey

-   **Ce que fait ce paramètre :** Il s'agit de votre identifiant unique fourni par Arukereso.hu. Il est essentiel pour qu'Arukereso.hu puisse lier les demandes d'enquête provenant de votre boutique PrestaShop à votre compte marchand spécifique sur leur plateforme.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est correctement saisi :* Le module peut communiquer avec succès avec les systèmes d'Arukereso.hu, permettant le processus automatisé d'envoi d'e-mails d'enquête.
    -   *Lorsqu'il est incorrect ou vide :* Arukereso.hu ne pourra pas identifier votre boutique, et les e-mails d'enquête ne seront pas envoyés à vos clients. L'intégration échouera.
-   **Valeur recommandée :** Saisissez la clé API exacte qui vous a été fournie par Arukereso.hu. Celle-ci se trouve généralement dans les paramètres de votre compte marchand sur le site web d'Arukereso.hu.
-   **Scénario / exemple de marchand :** Vous vous inscrivez au « Programme d'achat de confiance » sur Arukereso.hu. Ils vous fournissent une chaîne de caractères comme `abcdef1234567890`. Vous la copiez et la collez dans ce champ.

#### 2.1.2 Identifiant du produit (feed ITEM\_ID)

-   **Ce que fait ce paramètre :** Ce paramètre détermine quel identifiant de produit de votre boutique PrestaShop sera envoyé à Arukereso.hu. Arukereso.hu utilise cet ID pour faire correspondre le produit acheté avec sa liste sur leur plateforme, garantissant que l'enquête est pertinente.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est défini sur « ID produit » :* L'ID interne du produit PrestaShop (par exemple, `123`) sera utilisé. C'est l'option la plus courante et généralement la plus sûre.
    -   *Lorsqu'il est défini sur « Référence produit » :* Le code de référence de votre produit (par exemple, `SKU-001`) sera utilisé. Cela nécessite que vos références de produit soient uniques et cohérentes avec ce qu'Arukereso.hu attend.
    -   *Lorsqu'il est défini sur « EAN13 produit » :* Le code-barres EAN-13 du produit sera utilisé. Cela convient si vos EAN sont utilisés de manière cohérente et correspondent au catalogue de produits d'Arukereso.hu.
    -   *Lorsqu'il est défini sur « UPC produit » :* Le code UPC du produit sera utilisé. Similaire à l'EAN13, nécessite des données cohérentes.
-   **Valeur recommandée :** « ID produit » est généralement l'option la plus sûre et la plus fiable, sauf si vous avez une raison spécifique (et vérifiée avec Arukereso.hu) d'utiliser un autre identifiant.
-   **Scénario / exemple de marchand :** Si vous avez un produit « T-shirt rouge » avec un ID interne de `15`, une référence `TSHIRT-RED` et un EAN `1234567890123`, choisir « ID produit » enverra `15` à Arukereso.hu. Si vous choisissez « Référence produit », `TSHIRT-RED` sera envoyé. Assurez-vous que l'identifiant choisi est celui qu'Arukereso.hu attend pour lier correctement les produits.

#### 2.1.3 Demander le consentement du client

-   **Ce que fait ce paramètre :** Ce paramètre crucial contrôle si vos clients doivent explicitement accepter de participer au programme d'enquête Arukereso.hu lors du paiement. Ceci est vital pour se conformer aux réglementations sur la confidentialité des données comme le RGPD.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (« Oui ») :* Une case à cocher ou un mécanisme de consentement similaire apparaîtra pendant le processus de paiement. Seuls les clients qui cochent cette case verront leurs données de commande envoyées à Arukereso.hu à des fins d'enquête. Cela garantit la conformité au RGPD.
    -   *Lorsqu'il est désactivé (« Non ») :* Aucune option de consentement ne sera affichée. Tous les clients qui finalisent une commande seront automatiquement inscrits au programme d'enquête Arukereso.hu. **À utiliser avec prudence et uniquement si vous êtes certain que vos réglementations locales n'exigent pas de consentement explicite pour ce type de partage de données.**
-   **Valeur recommandée :** « Oui ». Il est fortement recommandé d'activer cette option pour assurer la conformité au RGPD et aux autres lois sur la confidentialité, donnant aux clients le contrôle sur leurs données.
-   **Scénario / exemple de marchand :** Vous opérez dans l'UE. Pour vous conformer au RGPD, vous activez ce paramètre. Lors du paiement, les clients voient une case à cocher : « Oui, j'accepte de recevoir une enquête de satisfaction client d'Arukereso.hu concernant mon achat. » Ce n'est que s'ils cochent cette case que leurs données seront partagées.

#### 2.1.4 Écrire les erreurs dans log.txt

-   **Ce que fait ce paramètre :** Ce paramètre contrôle si le module enregistre les erreurs ou les problèmes qu'il rencontre lors de son fonctionnement dans un fichier `log.txt` au sein du répertoire du module.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (« Oui ») :* Tout problème (par exemple, échec de connexion à Arukereso.hu, problèmes de clé API invalide) sera écrit dans `arukereso/log.txt`. C'est extrêmement utile pour le dépannage.
    -   *Lorsqu'il est désactivé (« Non ») :* Les erreurs ne seront pas enregistrées dans un fichier. Bien que cela réduise légèrement l'activité du disque, cela rend le diagnostic des problèmes beaucoup plus difficile.
-   **Valeur recommandée :** « Oui » lors de la configuration initiale et si vous rencontrez des problèmes. Une fois que le module fonctionne correctement, vous pouvez le désactiver si vous préférez, mais il est souvent préférable de le laisser activé pour une surveillance continue.
-   **Scénario / exemple de marchand :** Vous avez configuré le module, mais les clients ne reçoivent pas d'enquêtes. Vous activez ce paramètre, et après quelques commandes test, vous vérifiez `arukereso/log.txt` et trouvez un message d'erreur indiquant « Clé API invalide ». Cela vous indique immédiatement où chercher le problème.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Arukereso.hu WebApiKey | Votre clé Arukereso.hu | Identifiant unique de votre boutique sur Arukereso.hu. **Requis pour l'intégration.** |
| Configuration du module | Identifiant du produit (feed ITEM\_ID) | ID produit | Définit quel ID produit (ID PrestaShop, Référence, EAN, UPC) est envoyé à Arukereso.hu. |
| Configuration du module | Demander le consentement du client | Oui | Affiche une case à cocher de consentement lors du paiement. **Fortement recommandé pour la conformité au RGPD.** |
| Configuration du module | Écrire les erreurs dans log.txt | Oui | Enregistre les erreurs du module dans `arukereso/log.txt` pour le dépannage. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : Mes clients ne reçoivent pas d'e-mails d'enquête d'Arukereso.hu. Que dois-je vérifier ?**
R :

1.  **Arukereso.hu WebApiKey :** Vérifiez que votre clé API est correctement saisie dans la configuration du module. Même une seule faute de frappe empêchera l'intégration de fonctionner.
2.  **Paramètre de consentement :** Si « Demander le consentement du client » est activé, assurez-vous que les clients cochent bien la case de consentement lors du paiement. S'ils ne le font pas, aucune donnée n'est envoyée.
3.  **Fichier journal :** Activez « Écrire les erreurs dans log.txt » dans la configuration du module et vérifiez le fichier `arukereso/log.txt` pour tout message d'erreur après une commande test. C'est le moyen le plus direct de diagnostiquer les problèmes.
4.  **Compte Arukereso.hu :** Connectez-vous à votre compte marchand Arukereso.hu et vérifiez le statut de l'intégration de votre « Programme d'achat de confiance ». Ils peuvent avoir des journaux ou des indicateurs de statut spécifiques.
5.  **Statut de la commande :** Assurez-vous que le statut de la commande qui déclenche l'enquête (généralement « Paiement accepté » ou « Livré ») est correctement configuré du côté d'Arukereso.hu, et que vos commandes PrestaShop atteignent ce statut.

**Q : J'ai activé « Demander le consentement du client », mais je ne vois pas la case à cocher lors du paiement.**
R :

1.  **Compatibilité du thème :** Le module utilise les hooks PrestaShop standard (`displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop`). Si votre thème est fortement personnalisé, il pourrait ne pas rendre ces hooks correctement.
2.  **Cache :** Videz votre cache PrestaShop (Paramètres avancés > Performances > Vider le cache).
3.  **Position du module :** Allez dans Design > Positions et recherchez les hooks mentionnés ci-dessus. Assurez-vous que le module Arukereso.hu est listé et actif dans ces hooks. Si ce n'est pas le cas, essayez de le transplanter.
4.  **Conflits de modules :** Désactivez temporairement les autres modules qui modifient le processus de paiement pour exclure les conflits.

**Q : Que se passe-t-il si un client demande la suppression de ses données (droit à l'oubli RGPD) ?**
R : Le module est conçu pour s'intégrer aux outils RGPD de PrestaShop. Lorsqu'un client demande la suppression de données via le module RGPD de PrestaShop, ce module Arukereso.hu répondra au hook `actionDeleteGDPRCustomer`, garantissant que toutes les données relatives au client détenues par le module (par exemple, les enregistrements de consentement) sont supprimées. Cependant, il est important de noter que ce module *envoie* des données à Arukereso.hu. Vous devrez également contacter Arukereso.hu directement pour demander la suppression des données de ce client de leurs systèmes.

**Q : Puis-je personnaliser l'apparence de la case à cocher de consentement ?**
R : L'apparence de la case à cocher de consentement est principalement contrôlée par le CSS de votre thème PrestaShop. Le module fournit la structure HTML via son template `consent.tpl`. Vous pouvez surcharger ce template dans votre thème ou ajouter du CSS personnalisé pour styliser l'élément si vous devez modifier son apparence.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module Arukereso.hu est un module PrestaShop léger principalement axé sur l'intégration avec le « Programme d'achat de confiance » d'Arukereso.hu. Il utilise le système de hooks de PrestaShop pour injecter une option de consentement lors du paiement et pour envoyer les données de commande à Arukereso.hu lors de la confirmation de commande. Il suit une structure de module PrestaShop standard, avec sa logique principale résidant dans le fichier de module principal (`arukereso.php`) et utilisant des templates Smarty pour l'affichage en front-office. Il n'introduit pas de contrôleurs ou d'ObjectModels personnalisés, s'appuyant sur la classe `Configuration` de PrestaShop pour le stockage des paramètres.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient **pas** de contrôleurs Front-Office ou Back-Office personnalisés. Toute la logique est gérée dans le fichier de module principal `arukereso.php`, principalement via des méthodes de hook.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit **pas** de classes ou d'ObjectModels personnalisés dans le répertoire `classes/`. Il fonctionne directement dans le fichier `arukereso.php`, en utilisant les classes et fonctions PrestaShop standard.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut **pas** de fichiers JavaScript personnalisés. Toute interaction en front-office (par exemple, la case à cocher de consentement) est gérée via des formulaires HTML standard et un traitement côté serveur.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut **pas** de fichiers CSS personnalisés. Tout style pour la case à cocher de consentement ou d'autres éléments serait hérité du thème PrestaShop actif.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

-   `arukereso/views/templates/hook/consent.tpl`
    -   **Hook :** `displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop` (selon le thème et la version de PrestaShop, l'un de ceux-ci affichera le consentement).
    -   **Objectif :** Ce template rend le HTML pour la case à cocher de consentement client pendant le processus de paiement. Il comprend généralement une étiquette, l'entrée de la case à cocher et potentiellement un lien vers la politique de confidentialité ou plus d'informations sur Arukereso.hu.
    -   **Sortie :** Un petit élément de formulaire permettant au client de s'inscrire au programme d'enquête.
-   `arukereso/views/templates/hook/displayOrderConfirmation.tpl`
    -   **Hook :** `displayOrderConfirmation`
    -   **Objectif :** Ce template est rendu sur la page de confirmation de commande après un achat réussi. Il peut afficher un message au client confirmant sa participation au programme d'enquête (si le consentement a été donné) ou fournir des informations sur l'enquête à venir.
    -   **Sortie :** Un petit bloc d'informations sur la page de confirmation de commande.

#### Templates d'administration (`views/templates/admin/`)

Ce module ne contient **pas** de templates d'administration personnalisés au-delà de ce qui est rendu par `getContent()` dans le fichier de module principal.

#### Templates front-office (`views/templates/front/`)

Ce module ne contient **pas** de templates de page front-office autonomes dédiés.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

Ce module ne crée **pas** de tables de base de données personnalisées. Tous ses paramètres de configuration sont stockés dans la table `ps_configuration` de PrestaShop en utilisant les clés suivantes :

-   `ARUKERESO_FILE_LOG` : Stocke la valeur booléenne pour l'enregistrement des erreurs.
-   `ARUKERESO_ID` : Stocke la clé API Web Arukereso.hu.
-   `ARUKERESO_PRODUCT_ID` : Stocke le type d'identifiant de produit choisi (par exemple, 'id\_product', 'reference').
-   `ARUKERESO_CONSENT` : Stocke la valeur booléenne pour exiger le consentement du client.
-   `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` : Une clé de configuration PrestaShop standard, non directement gérée par ce module mais potentiellement utilisée pour la gestion des langues dans le back office.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayGDPRConsent` | Pendant le paiement, généralement près du consentement à la politique de confidentialité. | Rend la case à cocher de consentement client pour la participation à l'enquête Arukereso.hu. |
| `actionDeleteGDPRCustomer` | Déclenché lorsqu'un client demande la suppression de données via le module RGPD de PrestaShop. | Gère la suppression de toutes les données spécifiques au client stockées par le module (par exemple, le statut de consentement). |
| `actionExportGDPRData` | Déclenché lorsqu'un client demande l'exportation de données via le module RGPD de PrestaShop. | Fournit toutes les données spécifiques au client stockées par le module pour l'exportation. |
| `displayOrderConfirmation` | Sur la page de confirmation de commande après un achat réussi. | Affiche un message d'information au client et, surtout, envoie les données de commande à l'API d'Arukereso.hu si le consentement est donné. |
| `displayPaymentTop` | En haut de la section de paiement lors du paiement. | Hook alternatif pour rendre la case à cocher de consentement client, selon le thème. |
| `displayCheckoutSummaryTop` | En haut de la section du récapitulatif de paiement. | Hook alternatif pour rendre la case à cocher de consentement client, selon le thème. |
| `DisplayGDPRConsent` | (Alias/Ancienne version de `displayGDPRConsent`) | Rend la case à cocher de consentement client. |
| `DisplayPaymentTop` | (Alias/Ancienne version de `displayPaymentTop`) | Rend la case à cocher de consentement client. |
| `DisplayOrderConfirmation` | (Alias/Ancienne version de `displayOrderConfirmation`) | Rend les informations et envoie les données de commande. |
| `ActionDeleteGDPRCustomer` | (Alias/Ancienne version de `actionDeleteGDPRCustomer`) | Gère la suppression des données client. |
| `ActionExportGDPRData` | (Alias/Ancienne version de `actionExportGDPRData`) | Gère l'exportation des données client. |
| `DisplayCheckoutSummaryTop` | (Alias/Ancienne version de `displayCheckoutSummaryTop`) | Rend la case à cocher de consentement client. |

La logique principale du module pour l'envoi des données de commande à Arukereso.hu réside dans la méthode `hookDisplayOrderConfirmation` dans `arukereso.php`. Cette méthode vérifie le consentement du client (si requis), puis construit et envoie une requête HTTP à l'API Arukereso.hu avec les détails de la commande.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question que vous pourriez avoir concernant le module Arukereso.hu - e-mails d'enquête du programme d'achat de confiance.
