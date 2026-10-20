---
title: "Compari.ro - e-mails d'enquête du programme d'achat de confiance - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Compari.ro - e-mails d'enquête du programme d'achat de confiance par MyPresta.eu."
sidebar:
  label: "Compari.ro - e-mails d'enquête du programme d'achat de confiance - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Compari.ro - trusted purchase program survey emails sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/compariro-trusted-purchase-program-survey-emails.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/compariro-trusted-purchase-program-survey-emails/)
>
> ---


# Compari.ro - e-mails d'enquête du programme d'achat de confiance

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont suffisantes pour ce module.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal et unique pour le module Compari.ro. Vous pouvez y accéder en naviguant vers **Modules > Gestionnaire de modules**, en recherchant « Compari.ro » et en cliquant sur le bouton « Configurer ».

#### **1. Compari.ro WebApiKey**

- **Ce que fait ce paramètre :** Il s'agit de votre identifiant unique fourni par Compari.ro qui relie votre boutique PrestaShop à votre compte marchand Compari.ro. Il est essentiel pour que le « Programme d'achat de confiance » attribue correctement les demandes d'enquête à votre boutique.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est correctement saisi :* Le module pourra envoyer les données de commande à Compari.ro, leur permettant d'envoyer des e-mails d'enquête à vos clients.
  - *Lorsqu'il est incorrect ou vide :* L'intégration échouera et Compari.ro ne recevra pas les informations de commande, ce qui signifie qu'aucun e-mail d'enquête ne sera envoyé.
- **Valeur recommandée :** Saisissez la WebApiKey exacte qui vous a été fournie par Compari.ro.
- **Scénario / exemple de marchand :** Vous vous êtes inscrit au « Programme d'achat de confiance » de Compari.ro et avez reçu un e-mail avec votre clé API. Vous devez copier et coller cette clé ici pour que l'intégration fonctionne.

#### **2. Identifiant du produit (flux ITEM\_ID)**

- **Ce que fait ce paramètre :** Ce paramètre définit quel identifiant de produit de votre boutique PrestaShop doit être utilisé comme `ITEM_ID` lors de l'envoi d'informations sur les produits à Compari.ro. Ceci est crucial pour faire correspondre les produits de votre flux Compari.ro avec les produits de vos commandes.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur `id_product` (par défaut) :* L'ID interne du produit PrestaShop sera utilisé. C'est généralement l'option la plus sûre si vous n'avez pas d'identifiant personnalisé spécifique.
  - *Lorsqu'il est défini sur `reference` :* Le code de référence du produit sera utilisé. Choisissez cette option si votre flux de produits Compari.ro utilise la référence du produit comme `ITEM_ID`.
  - *Lorsqu'il est défini sur `ean13` :* Le code-barres EAN-13 du produit sera utilisé. Choisissez cette option si votre flux de produits Compari.ro utilise l'EAN-13 comme `ITEM_ID`.
  - *Lorsqu'il est défini sur `upc` :* Le code UPC du produit sera utilisé. Choisissez cette option si votre flux de produits Compari.ro utilise l'UPC comme `ITEM_ID`.
- **Valeur recommandée :** `id_product` (sauf si votre flux de produits Compari.ro utilise explicitement `reference`, `ean13` ou `upc` comme `ITEM_ID`).
- **Scénario / exemple de marchand :** Votre flux de produits Compari.ro utilise le code-barres EAN-13 unique pour chaque produit. Vous sélectionneriez `ean13` ici pour vous assurer que Compari.ro peut identifier correctement les produits achetés par vos clients.

#### **3. Exiger le consentement du client**

- **Ce que fait ce paramètre :** Cette option détermine si vos clients doivent explicitement accepter de participer au programme d'enquête Compari.ro pendant le processus de commande. Ceci est important pour la conformité au RGPD et le respect des préférences de confidentialité des clients.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (défini sur « Oui ») :* Une case à cocher apparaîtra pendant le processus de commande (par exemple, sur la page de paiement ou le résumé de la commande). Les clients doivent cocher cette case pour autoriser l'envoi de leurs données de commande à Compari.ro à des fins d'enquête. S'ils ne consentent pas, aucun e-mail d'enquête ne sera envoyé pour leur commande.
  - *Lorsqu'il est désactivé (défini sur « Non ») :* Aucune case à cocher de consentement ne sera affichée. Les données de commande seront envoyées à Compari.ro pour toutes les commandes, en supposant que la `WebApiKey` est correcte.
- **Valeur recommandée :** « Oui » si vous opérez dans des régions avec des lois strictes sur la confidentialité des données (comme le RGPD) ou si vous souhaitez donner aux clients un contrôle total sur le partage de leurs données. « Non » si vous avez déterminé qu'un consentement explicite n'est pas requis pour votre contexte juridique spécifique ou si vous souhaitez maximiser la participation à l'enquête.
- **Scénario / exemple de marchand :** Pour se conformer aux réglementations RGPD, vous activez ce paramètre. Pendant le processus de commande, les clients voient une case à cocher « J'accepte de participer à l'enquête du programme d'achat de confiance Compari.ro ». Seuls les clients qui cochent cette case recevront un e-mail d'enquête.

#### **4. Écrire les erreurs dans log.txt**

- **Ce que fait ce paramètre :** Il s'agit d'une option de débogage qui contrôle si le module enregistre les erreurs rencontrées lors de son fonctionnement (par exemple, problèmes d'envoi de données à Compari.ro) dans un fichier `log.txt` dans le répertoire du module.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (défini sur « Oui ») :* Toutes les erreurs techniques seront écrites dans `compari/log.txt`. Ce fichier peut être très utile pour votre webmaster ou le support MyPresta.eu pour diagnostiquer les problèmes.
  - *Lorsqu'il est désactivé (défini sur « Non ») :* Les erreurs ne seront pas explicitement enregistrées dans un fichier. Ceci est généralement préféré pour les boutiques en production afin d'éviter de générer de gros fichiers journaux, sauf si vous êtes en train de dépanner activement.
- **Valeur recommandée :** « Non » pour une boutique en production. « Oui » si vous rencontrez des problèmes avec l'intégration et avez besoin de déboguer. N'oubliez pas de le désactiver une fois le problème résolu.
- **Scénario / exemple de marchand :** Vous avez configuré le module, mais les clients ne reçoivent pas d'e-mails d'enquête. Vous activez « Écrire les erreurs dans log.txt », puis passez une commande test. Vous vérifiez ensuite le fichier `log.txt` pour des indices sur les raisons pour lesquelles l'intégration pourrait échouer.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Compari.ro WebApiKey | Votre clé API unique | Lie votre boutique à Compari.ro pour l'automatisation des enquêtes. **Critique pour la fonctionnalité.** |
| Configuration du module | Identifiant du produit (flux ITEM\_ID) | `id_product` (ou correspond à votre flux) | Spécifie quel ID de produit (interne, référence, EAN, UPC) envoyer à Compari.ro. |
| Configuration du module | Exiger le consentement du client | Oui (pour le RGPD) | Affiche une case à cocher de consentement pendant le processus de commande. Si elle n'est pas cochée, aucun e-mail d'enquête n'est envoyé. |
| Configuration du module | Écrire les erreurs dans log.txt | Non (activer pour le débogage) | Enregistre les erreurs techniques dans `compari/log.txt` pour le dépannage. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q1 : Mes clients ne reçoivent pas d'e-mails d'enquête de Compari.ro, mais le module est configuré.**
R1 :

- **Vérifiez la WebApiKey :** Vérifiez attentivement que votre « Compari.ro WebApiKey » est saisie correctement et exactement telle que fournie par Compari.ro. Même une seule faute de frappe empêchera l'intégration de fonctionner.
- **Vérifiez le paramètre de consentement :** Si « Exiger le consentement du client » est défini sur « Oui », assurez-vous que vos clients test cochent réellement la case de consentement pendant le processus de commande.
- **Vérifiez le compte Compari.ro :** Connectez-vous à votre compte marchand Compari.ro pour voir s'il y a des messages d'erreur ou si les commandes sont reçues de votre boutique.
- **Activez la journalisation :** Définissez « Écrire les erreurs dans log.txt » sur « Oui » dans la configuration du module, passez une commande test, puis vérifiez le fichier `compari/log.txt` pour tout message d'erreur. Cela fournira des détails techniques spécifiques.
- **Videz le cache :** Parfois, le cache de PrestaShop peut interférer. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ».

**Q2 : J'ai activé « Exiger le consentement du client », mais je ne vois pas de case à cocher pendant le processus de commande.**
R2 :

- **Compatibilité du thème :** Le module utilise les hooks PrestaShop standard (`displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop`) pour afficher la case à cocher de consentement. Si votre thème personnalisé modifie fortement le processus de commande, ces hooks pourraient ne pas être rendus, ou le style pourrait rendre la case à cocher invisible.
- **Cache :** Videz votre cache PrestaShop (**Paramètres avancés > Performances**).
- **Position du module :** Assurez-vous que le module n'est pas désactivé pour les hooks spécifiques qu'il utilise. Bien que moins courant pour une case à cocher de consentement, cela vaut la peine de vérifier dans **Design > Positions**.

**Q3 : Que se passe-t-il si un client change d'avis concernant le consentement après avoir passé une commande ?**
R3 : Le module traite le consentement au moment de la passation de la commande. Si un client souhaite révoquer son consentement pour de futures enquêtes, il devra généralement gérer cela directement avec Compari.ro ou via les outils généraux de gestion des données RGPD de votre boutique (si vous en avez). Le module lui-même n'offre pas d'« annulation » directe pour les commandes passées, mais il s'intègre aux hooks RGPD de PrestaShop pour la suppression et l'exportation de données.

**Q4 : Je vois un fichier `log.txt` devenir très volumineux. Que dois-je faire ?**
R4 : Si vous n'êtes pas en train de dépanner activement, définissez l'option « Écrire les erreurs dans log.txt » sur « Non » dans la configuration du module. Cela empêchera le module d'écrire d'autres entrées dans le fichier journal. Vous pouvez ensuite supprimer en toute sécurité le fichier `log.txt` pour libérer de l'espace.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, webmasters de boutique et agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module `Compari` est un module PrestaShop simple, principalement axé sur l'intégration avec une API externe (Compari.ro) basée sur les événements de commande. Il suit une structure de module PrestaShop standard, tirant parti des hooks pour injecter du contenu (consentement RGPD) et déclencher des actions (envoi de données de commande). Il n'introduit pas de contrôleurs personnalisés ni d'ObjectModels complexes, s'appuyant sur les données `Order` et `Customer` du cœur de PrestaShop. La logique principale réside dans le fichier `compari.php`, gérant la configuration, l'installation et les rappels de hook.

### 4.2 Contrôleurs (`controllers/`)

- Ce module ne contient **pas** de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la logique est gérée dans le fichier `compari.php` principal via des hooks.

### 4.3 Classes et modèles de base (`classes/`)

- Ce module ne contient **pas** de classes ou d'ObjectModels personnalisés dans le répertoire `classes/`. Toute la gestion des données est effectuée directement dans le fichier `compari.php` en utilisant les entités `Order`, `Customer` et `Product` du cœur de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

- Ce module ne contient **pas** de fichiers JavaScript personnalisés.

### 4.5 Feuilles de style CSS (`views/css/`)

- Ce module ne contient **pas** de fichiers CSS personnalisés. Le style de la case à cocher de consentement est censé être hérité du thème ou géré par le style du module RGPD de base de PrestaShop.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **Modèles de hook (`views/templates/hook/`)** :
  - `compari/views/templates/hook/consent.tpl` :
    - **Hook :** `displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop`
    - **Objectif :** Rend la case à cocher de consentement RGPD et le texte associé, permettant aux clients de s'inscrire ou de se désinscrire du programme d'enquête Compari.ro. Ce modèle n'est rendu que si la configuration `COMPARI_CONSENT` est activée.
    - **Sortie :** Un champ de saisie de case à cocher avec une étiquette.
  - `compari/views/templates/hook/displayOrderConfirmation.tpl` :
    - **Hook :** `displayOrderConfirmation`
    - **Objectif :** Ce modèle est inclus dans le hook `displayOrderConfirmation`. Bien qu'il s'agisse d'un fichier de modèle, son rôle principal ici est de déclencher la logique backend dans `hookDisplayOrderConfirmation` dans `compari.php` pour envoyer les données de commande à Compari.ro. Il n'affiche pas de contenu visible à l'utilisateur.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne crée **pas** de tables SQL personnalisées.
  - Il stocke ses paramètres de configuration dans la table `ps_configuration` :
    - `COMPARI_FILE_LOG` : Stocke la valeur booléenne pour la journalisation des erreurs.
    - `COMPARI_ID` : Stocke la WebApiKey de Compari.ro.
    - `COMPARI_PRODUCT_ID` : Stocke le type d'identifiant de produit sélectionné (par exemple, `id_product`, `reference`).
    - `COMPARI_CONSENT` : Stocke la valeur booléenne pour l'exigence du consentement du client.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `install()` | Lors de l'installation du module | Définit les valeurs de configuration par défaut, enregistre les hooks. |
| `uninstall()` | Lors de la désinstallation du module | Supprime les valeurs de configuration, désenregistre les hooks. |
| `hookDisplayGDPRConsent` | S'affiche sur les pages où le consentement RGPD est collecté (par exemple, paiement) | Affiche la case à cocher de consentement pour la participation à l'enquête Compari.ro. |
| `hookActionDeleteGDPRCustomer` | Lorsqu'un client demande la suppression de données RGPD | Gère la suppression de toutes les données client liées à Compari.ro (bien qu'aucune ne soit stockée directement par le module, c'est un hook de conformité). |
| `hookActionExportGDPRData` | Lorsqu'un client demande l'exportation de données RGPD | Gère l'exportation de toutes les données client liées à Compari.ro (aucune n'est stockée directement). |
| `hookDisplayOrderConfirmation` | Sur la page de confirmation de commande après un achat réussi | Déclenche l'envoi des données de commande à Compari.ro si le consentement est donné (ou non requis). |
| `hookDisplayPaymentTop` | En haut de l'étape de paiement dans le processus de commande | Hook alternatif pour afficher la case à cocher de consentement. |
| `hookDisplayCheckoutSummaryTop` | En haut de l'étape de résumé du processus de commande | Hook alternatif pour afficher la case à cocher de consentement. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Compari.ro - e-mails d'enquête du programme d'achat de confiance », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question que vous pourriez avoir.
