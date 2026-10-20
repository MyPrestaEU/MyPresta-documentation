---
title: "Pixel Snapchat & API Conversions - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Pixel Snapchat & API Conversions par MyPresta.eu."
sidebar:
  label: "Pixel Snapchat & API Conversions - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Snapchat Pixel & Conversions API sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/snapchat-pixel-conversions-api.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/snapchat-pixel-conversions-api/)
>
> ---


# Pixel Snapchat & API Conversions

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises. Celles-ci sont généralement activées par défaut sur la plupart des environnements d'hébergement modernes.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal où vous configurerez votre Pixel Snapchat et l'API Conversions. Le module fournit une interface conviviale avec diverses sections pour vous guider tout au long de la configuration.

#### **1. Paramètres généraux et mode de suivi**

- **Mode de suivi :**

  - **Ce que fait ce paramètre :** Détermine comment votre boutique envoie des données à Snapchat. Vous pouvez choisir entre le côté client (Pixel), le côté serveur (API Conversions) ou une approche hybride.
  - **Effet de la modification de ce paramètre :**
    - *Pixel uniquement :* Seul le Pixel Snap (code JavaScript dans le navigateur) suivra les événements. C'est plus simple mais plus susceptible aux bloqueurs de publicité et aux restrictions de navigateur.
    - *API Conversions uniquement :* Seul le suivi côté serveur sera utilisé. C'est plus fiable pour la confidentialité et la précision des données mais nécessite une configuration serveur robuste.
    - *Hybride (Recommandé) :* Le Pixel et la CAPI suivront les événements. Le module déduplique automatiquement les événements à l'aide d'un `event_id` partagé, garantissant un rapport précis tout en maximisant la capture de données. C'est généralement l'option la plus robuste et recommandée.
  - **Valeur recommandée :** `Hybride`
  - **Scénario/exemple de marchand :** Si vous débutez, "Pixel uniquement" est rapide. Pour une publicité sérieuse, "Hybride" vous offre le meilleur des deux mondes, garantissant que vous capturez autant de données précises que possible pour l'optimisation de la campagne.
- **ID du Pixel Snap :**

  - **Ce que fait ce paramètre :** C'est votre identifiant unique pour votre Pixel Snapchat. Il indique à Snapchat à quel compte publicitaire associer les événements suivis.
  - **Effet de la modification de ce paramètre :** S'il est incorrect ou vide, aucun suivi côté client ne se produira et vos publicités Snapchat ne pourront pas suivre les visiteurs du site Web ou les conversions.
  - **Valeur recommandée :** Votre ID de Pixel Snap (par exemple, `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`). Vous pouvez le trouver dans votre Gestionnaire de publicités Snapchat.
  - **Scénario/exemple de marchand :** Vous avez créé un compte publicitaire sur Snapchat et devez y lier votre boutique. Entrez l'ID du Pixel fourni par Snapchat ici.
- **Jeton de l'API Conversions :**

  - **Ce que fait ce paramètre :** C'est un jeton sécurisé qui permet à votre serveur d'envoyer des données directement à l'API Conversions de Snapchat. Il authentifie vos requêtes côté serveur.
  - **Effet de la modification de ce paramètre :** S'il est incorrect ou vide, aucun suivi côté serveur ne se produira. Cela signifie que vous perdez les avantages de fiabilité et de confidentialité améliorés de la CAPI.
  - **Valeur recommandée :** Votre Jeton de l'API Conversions. Vous le générez dans votre Gestionnaire de publicités Snapchat.
  - **Scénario/exemple de marchand :** Pour vous assurer que vos données d'achat sont envoyées de manière fiable à Snapchat même si un client utilise un bloqueur de publicité, vous devrez configurer et saisir votre jeton CAPI ici.

#### **2. Suivi des événements et qualité des données**

- **Activer la correspondance avancée :**

  - **Ce que fait ce paramètre :** Permet au module d'envoyer des données client supplémentaires (comme l'e-mail, le numéro de téléphone, le nom) à Snapchat, hachées de manière sécurisée, pour améliorer la correspondance des événements et la création d'audiences.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Snapchat peut faire correspondre plus précisément les visiteurs du site Web à leurs profils Snapchat, améliorant le ciblage d'audience et l'attribution des publicités.
    - *Désactivé :* Moins de données sont envoyées, ce qui peut réduire la précision de la correspondance d'audience et de l'optimisation des campagnes.
  - **Valeur recommandée :** `OUI` (sauf si vous avez des préoccupations strictes en matière de confidentialité qui l'emportent sur les avantages).
  - **Scénario/exemple de marchand :** Vous voulez que Snapchat soit aussi efficace que possible pour trouver des clients similaires à vos clients existants. L'activation de cette option aide Snapchat à identifier les utilisateurs plus précisément.
- **Intégration de la gestion du consentement :**

  - **Ce que fait ce paramètre :** S'intègre aux modules de consentement aux cookies populaires (par exemple, les modules GDPR) pour garantir que le suivi Snapchat ne se produit qu'après que le client a donné son consentement explicite.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le module attendra le consentement avant d'initialiser le Pixel Snap ou d'envoyer des événements CAPI qui nécessitent des données utilisateur.
    - *Désactivé :* Le suivi se produira quel que soit le consentement de l'utilisateur, ce qui pourrait entraîner des problèmes de conformité en matière de confidentialité dans certaines régions.
  - **Valeur recommandée :** `OUI` (fortement recommandé pour le GDPR, le CCPA et d'autres réglementations en matière de confidentialité).
  - **Scénario/exemple de marchand :** Votre boutique opère dans l'UE et doit se conformer au GDPR. L'activation de cette option garantit que vous ne suivez que les utilisateurs qui ont accepté votre politique en matière de cookies.
- **Type d'ID produit pour la correspondance de catalogue :**

  - **Ce que fait ce paramètre :** Spécifie quel identifiant de produit (par exemple, ID produit, Référence produit, EAN/UPC) le module doit envoyer à Snapchat pour la correspondance de catalogue de produits. C'est crucial pour les publicités dynamiques de produits.
  - **Effet de la modification de ce paramètre :** Si le type d'ID envoyé par le module ne correspond pas aux ID de votre catalogue de produits Snapchat, vos publicités dynamiques n'afficheront pas les produits corrects.
  - **Valeur recommandée :** Choisissez le type d'ID que vous utilisez de manière cohérente dans votre catalogue de produits Snapchat. Souvent, `ID produit` ou `Référence produit` sont de bons choix.
  - **Scénario/exemple de marchand :** Vous diffusez des publicités de reciblage dynamique sur Snapchat. Si votre catalogue de produits utilise la "Référence produit" comme identifiant unique, vous devez sélectionner "Référence produit" ici pour que les publicités affichent les bons produits aux clients.
- **Activer le mode débogage :**

  - **Ce que fait ce paramètre :** Active un mode spécial qui affiche des informations détaillées sur les événements envoyés à Snapchat directement dans la console de développement de votre navigateur.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Vous verrez des retours en temps réel sur les données envoyées, ce qui vous aidera à dépanner et à vérifier votre configuration. Ceci n'est visible que pour vous (ou toute personne ayant les outils de développement ouverts).
    - *Désactivé :* Aucune information de débogage n'est affichée.
  - **Valeur recommandée :** `NON` pour les boutiques en ligne. `OUI` pendant la configuration initiale et le dépannage.
  - **Scénario/exemple de marchand :** Après avoir installé le module, vous voulez confirmer que les événements "Ajout au panier" se déclenchent correctement. Vous activez le mode débogage, ajoutez un produit à votre panier et vérifiez la console pour les détails de l'événement.

#### **3. Fonctionnalités avancées**

- **Ghost Collector (Correspondance ScCid) :**

  - **Ce que fait ce paramètre :** Améliore la précision de la correspondance des utilisateurs sur différentes sessions et appareils en créant un identifiant unique et anonyme (ScCid) et en le stockant dans un cookie de première partie.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Meilleure attribution et création d'audience, en particulier dans les scénarios où les cookies tiers sont restreints.
    - *Désactivé :* La capacité de Snapchat à suivre les utilisateurs sur les sessions pourrait être moins précise.
  - **Valeur recommandée :** `OUI`
  - **Scénario/exemple de marchand :** Un client visite votre boutique, part et revient plus tard depuis un appareil différent. Ghost Collector aide Snapchat à les reconnaître comme le même utilisateur, améliorant vos efforts de reciblage.
- **Domaines de liaison (Suivi inter-domaines) :**

  - **Ce que fait ce paramètre :** Vous permet de spécifier des domaines supplémentaires (par exemple, un blog séparé, un sous-domaine pour des produits spécifiques) où vous souhaitez également suivre les événements Snapchat et lier les sessions utilisateur.
  - **Effet de la modification de ce paramètre :**
    - *Configuré :* Snapchat peut suivre le parcours d'un utilisateur de manière transparente entre votre boutique principale et les domaines liés spécifiés.
    - *Vide :* Le suivi est limité au domaine de votre boutique principale uniquement.
  - **Valeur recommandée :** Laissez vide sauf si vous avez plusieurs domaines/sous-domaines qui nécessitent un suivi croisé.
  - **Scénario/exemple de marchand :** Vous avez votre boutique principale sur `mystore.com` et un blog séparé sur `blog.mystore.com`. Vous voulez suivre les utilisateurs qui visitent les deux. Vous ajouteriez `blog.mystore.com` à ce paramètre.
- **URL de tâche Cron pour la synchronisation CAPI :**

  - **Ce que fait ce paramètre :** Fournit une URL unique que vous pouvez configurer comme tâche cron sur votre serveur. Cette tâche cron envoie périodiquement tous les événements côté serveur en file d'attente à Snapchat, garantissant que les données sont livrées même en cas de problèmes de réseau temporaires.
  - **Effet de la modification de ce paramètre :** Il s'agit d'un champ en lecture seule. La configuration de la tâche cron assure une livraison fiable et asynchrone des événements CAPI. Si elle n'est pas configurée, les événements CAPI peuvent n'être envoyés qu'en temps réel ou lors d'actions utilisateur spécifiques, ce qui peut entraîner la perte de certaines données si l'envoi en temps réel échoue.
  - **Valeur recommandée :** Configurez une tâche cron sur votre serveur pour exécuter cette URL toutes les 5 à 15 minutes.
  - **Scénario/exemple de marchand :** Pour vous assurer que toutes vos données d'achat sont envoyées à Snapchat, même si un client ferme son navigateur immédiatement après l'achat, vous configurez une tâche cron pour traiter régulièrement tous les événements CAPI en attente.

#### **4. Qualité des données et score de santé**

Cette section fournit généralement des informations et des recommandations en lecture seule basées sur votre configuration actuelle et les événements suivis.

- **Score de santé :**

  - **Ce que fait ce paramètre :** Affiche un score global indiquant la qualité et l'exhaustivité de votre configuration de suivi Snapchat. Un score plus élevé signifie de meilleures données.
  - **Effet de la modification de ce paramètre :** C'est un outil de diagnostic. L'amélioration de votre configuration (par exemple, l'activation de la CAPI, la correspondance avancée) augmentera ce score.
  - **Valeur recommandée :** Visez le score le plus élevé possible.
  - **Scénario/exemple de marchand :** Votre score de santé est de 60 %. Le module pourrait suggérer d'activer la correspondance avancée pour l'améliorer, indiquant un domaine potentiel pour une meilleure qualité des données.
- **Coach de qualité des données :**

  - **Ce que fait ce paramètre :** Offre des recommandations et des avertissements spécifiques concernant votre configuration de suivi, tels que des jetons CAPI manquants, des types d'ID produit non configurés ou des problèmes de consentement potentiels.
  - **Effet de la modification de ce paramètre :** C'est un outil de diagnostic. La prise en compte des recommandations améliorera la précision de votre suivi.
  - **Valeur recommandée :** Examinez et agissez sur toutes les recommandations.
  - **Scénario/exemple de marchand :** Le coach vous indique que votre "Type d'ID produit" ne correspond pas à votre catalogue. Vous revenez ensuite aux paramètres et l'ajustez.
- **Docteur de catalogue :**

  - **Ce que fait ce paramètre :** Vous aide à diagnostiquer les problèmes liés à votre catalogue de produits et à la façon dont il est mis en correspondance avec les événements Snapchat. Il vérifie la cohérence des identifiants de produit.
  - **Effet de la modification de ce paramètre :** C'est un outil de diagnostic. La résolution des problèmes ici garantit que vos publicités dynamiques de produits fonctionnent correctement.
  - **Valeur recommandée :** Utilisez cet outil si vous rencontrez des problèmes avec des publicités dynamiques de produits affichant des articles incorrects.
  - **Scénario/exemple de marchand :** Vos publicités dynamiques affichent des produits génériques au lieu de ceux que les clients ont consultés. Le Docteur de catalogue pourrait révéler que vos ID de produit sont incohérents.

#### **5. Statistiques en direct et événements récents**

- **Statistiques en direct :**

  - **Ce que fait ce paramètre :** Fournit un aperçu en temps réel des événements envoyés à Snapchat (par exemple, Vues de page, Ajouts au panier, Achats).
  - **Effet de la modification de ce paramètre :** C'est un outil de surveillance. Il vous aide à vérifier rapidement si les événements se déclenchent comme prévu.
  - **Valeur recommandée :** Vérifiez régulièrement cette section pour vous assurer que votre suivi est actif.
  - **Scénario/exemple de marchand :** Vous lancez un nouveau produit et souhaitez voir si les événements "Vue de contenu" sont suivis immédiatement. Vous vérifiez les statistiques en direct.
- **Journal des événements récents :**

  - **Ce que fait ce paramètre :** Affiche un journal des événements les plus récents envoyés à Snapchat, y compris des détails tels que le type d'événement, l'horodatage et si l'événement a été envoyé via Pixel ou CAPI.
  - **Effet de la modification de ce paramètre :** C'est un outil de journalisation détaillé pour la vérification et le dépannage.
  - **Valeur recommandée :** Utilisez-le pour approfondir des événements spécifiques si vous suspectez un problème.
  - **Scénario/exemple de marchand :** Un client signale un problème avec un achat, et vous voulez confirmer si l'événement "Achat" a été envoyé avec succès à Snapchat pour cette commande.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### **AdminMysnapapiAjaxController (Back Office > Modules > Pixel Snapchat & API Conversions > [Appels AJAX internes])**

Ce contrôleur n'est pas directement accessible via un élément de menu mais gère les requêtes AJAX en arrière-plan depuis la page de configuration du module. Il est responsable de :

- **Nom de l'écran et emplacement du menu :** Non directement visible dans le menu. Il traite les requêtes initiées depuis la page de configuration principale du module.
- **Actions et paramètres disponibles :** Il gère le chargement dynamique des données pour les sections "Statistiques en direct", "Événements récents", "Score de santé", "Coach de qualité des données" et "Docteur de catalogue". Il gère également la sauvegarde de paramètres de configuration spécifiques sans rechargement complet de la page.
- **Effet des modifications :** Lorsque vous interagissez avec des éléments dynamiques sur la page de configuration principale (par exemple, actualiser les statistiques en direct, enregistrer un sous-paramètre spécifique), ce contrôleur traite la requête et met à jour les informations affichées ou enregistre les données.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Les marchands n'interagissent pas directement avec ce contrôleur. Sa fonctionnalité est intégrée à la page de configuration principale du module.

#### **index.php (mysnapapi/controllers/admin/index.php)**

Ce fichier est un espace réservé et ne contient généralement pas de fonctionnalité directe ni d'interface utilisateur. Dans PrestaShop, les fichiers `index.php` dans les répertoires de contrôleurs servent souvent à empêcher la liste des répertoires plutôt qu'à fournir une logique de contrôleur spécifique.

- **Nom de l'écran et emplacement du menu :** Pas un écran direct.
- **Actions et paramètres disponibles :** Aucun.
- **Effet des modifications :** Aucune interaction ou effet direct pour le marchand.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Aucune interaction requise.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Mode de suivi | Hybride | Définit comment les données sont envoyées (Pixel, CAPI, ou les deux). Hybride est le plus robuste. |
| | ID du Pixel Snap | Votre ID de Pixel | ID unique pour le suivi côté client. Essentiel pour le Pixel. |
| | Jeton de l'API Conversions | Votre Jeton CAPI | Jeton sécurisé pour le suivi côté serveur. Essentiel pour la CAPI. |
| | Activer la correspondance avancée | OUI | Améliore la correspondance des utilisateurs pour un meilleur ciblage publicitaire. |
| | Intégration de la gestion du consentement | OUI | Assure la conformité à la confidentialité en respectant le consentement de l'utilisateur. |
| | Type d'ID produit pour la correspondance de catalogue | ID produit / Référence | Fait correspondre les identifiants de produit pour les publicités dynamiques. |
| | Activer le mode débogage | NON (OUI pour la configuration) | Affiche les informations de suivi dans la console du navigateur pour le dépannage. |
| | Ghost Collector (Correspondance ScCid) | OUI | Améliore la correspondance des utilisateurs sur les sessions/appareils. |
| | Domaines de liaison | Vide (ou vos domaines) | Permet le suivi inter-domaines pour plusieurs sites liés. |
| | URL de tâche Cron pour la synchronisation CAPI | (Lecture seule) | URL pour la livraison des événements côté serveur, configurée comme tâche cron. |
| | Score de santé | (Diagnostic) | Qualité globale de votre configuration de suivi. Visez un score élevé. |
| | Coach de qualité des données | (Diagnostic) | Recommandations spécifiques pour améliorer la qualité des données. |
| | Docteur de catalogue | (Diagnostic) | Diagnostique les problèmes de correspondance de catalogue de produits. |
| | Statistiques en direct | (Surveillance) | Aperçu en temps réel des événements suivis. |
| | Journal des événements récents | (Surveillance) | Journal détaillé des événements récents pour vérification. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q1 : Mes publicités Snapchat n'affichent aucune conversion, mais je sais que je fais des ventes. Qu'est-ce qui ne va pas ?**
R1 :

-   **Vérifiez l'ID du Pixel et le Jeton CAPI :** Vérifiez à nouveau que votre ID du Pixel Snap et votre Jeton de l'API Conversions sont correctement saisis dans la configuration du module. Même une seule faute de frappe empêchera le suivi.
-   **Mode de suivi :** Assurez-vous que vous utilisez "Hybride" ou au moins "Pixel uniquement" si vous vous attendez à un suivi côté client.
-   **Mode débogage :** Activez le "Mode débogage" dans les paramètres du module et ouvrez la console de développement de votre navigateur (F12). Naviguez dans votre boutique et effectuez des actions (afficher un produit, ajouter au panier, effectuer un achat test). Recherchez les événements Snapchat enregistrés dans la console. Si vous ne les voyez pas, il y a un problème de configuration fondamental.
-   **Videz le cache :** Videz toujours le cache de votre PrestaShop (Paramètres avancés > Performances) après avoir effectué des modifications de configuration du module.
-   **Bloqueurs de publicité :** Testez avec une fenêtre de navigation privée/incognito sans aucun bloqueur de publicité activé, car ils peuvent interférer avec le suivi des pixels.

**Q2 : J'ai activé le module, mais je m'inquiète de la conformité au GDPR/CCPA. Comment ce module aide-t-il ?**
R2 :

-   Le module comprend un paramètre **"Intégration de la gestion du consentement"**. Lorsqu'il est activé, il s'intégrera à votre solution de consentement aux cookies existante (par exemple, un module GDPR). Cela signifie que le suivi Snapchat ne s'activera *qu'après* qu'un utilisateur a donné son consentement explicite via la bannière de consentement de votre boutique.
-   **Action :** Assurez-vous que ce paramètre est activé et que vous avez un module de consentement aux cookies fonctionnel sur votre boutique PrestaShop.

**Q3 : Mes publicités dynamiques de produits sur Snapchat affichent les mauvais produits ou ne fonctionnent pas du tout.**
R3 :

-   **Type d'ID produit :** Allez dans la configuration du module et vérifiez le paramètre **"Type d'ID produit pour la correspondance de catalogue"**. Cela doit correspondre exactement à l'identifiant unique que vous utilisez dans votre catalogue de produits Snapchat (par exemple, si votre catalogue utilise `reference`, sélectionnez `Référence produit` ici).
-   **Synchronisation du catalogue :** Assurez-vous que votre catalogue de produits est correctement synchronisé et à jour dans votre Gestionnaire de publicités Snapchat. Le module envoie les ID corrects, mais Snapchat doit avoir ces ID dans son catalogue.
-   **Docteur de catalogue :** Utilisez l'outil "Docteur de catalogue" dans la configuration du module pour diagnostiquer les incohérences potentielles entre les données de produits de votre boutique et ce que Snapchat attend.

**Q4 : Je vois des événements en double dans mon Gestionnaire de publicités Snapchat (par exemple, deux événements "Achat" pour une seule commande).**
R4 :

-   Cela se produit généralement si vous utilisez à la fois le Pixel et la CAPI sans déduplication appropriée.
-   **Action :** Assurez-vous que votre "Mode de suivi" est défini sur **"Hybride"**. Ce module est conçu pour gérer automatiquement la déduplication des événements lorsqu'il fonctionne en mode hybride en générant un `event_id` partagé pour les événements côté client et côté serveur. Si vous voyez des doublons, vérifiez que le module est correctement configuré pour le mode hybride et qu'aucun autre code de suivi Snapchat n'est présent sur votre site.

**Q5 : Les sections "Statistiques en direct" ou "Score de santé" sur la page de configuration du module ne se mettent pas à jour ou n'affichent pas de données.**
R5 :

-   **Problèmes AJAX :** Cela indique généralement un problème avec la capacité de votre serveur à traiter les requêtes AJAX ou une erreur JavaScript dans votre back office.
-   **Console du navigateur :** Ouvrez la console de développement de votre navigateur (F12) sur la page de configuration du module et vérifiez s'il y a des messages d'erreur rouges dans l'onglet "Console".
-   **Journaux du serveur :** Vérifiez les journaux d'erreurs PHP de votre serveur pour toute erreur connexe.
-   **Mode débogage de PrestaShop :** Activez temporairement le mode débogage de PrestaShop (Paramètres avancés > Performances > Mode débogage : OUI) pour voir si des erreurs plus détaillées apparaissent.
-   **Contactez le support :** Si vous ne parvenez pas à le résoudre, rassemblez tous les messages d'erreur et contactez le support MyPresta.eu.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module `Pixel Snapchat & API Conversions` (`mysnapapi`) implémente une solution de suivi robuste tirant parti du suivi des événements côté client (Pixel Snap) et côté serveur (API Conversions - CAPI). Il suit une approche modulaire et orientée objet, adhérant au modèle MVC de PrestaShop lorsque cela est applicable.

Composants architecturaux clés :

-   **Suivi hybride :** Le module prend en charge le mode Pixel uniquement, CAPI uniquement et un mode hybride recommandé. En mode hybride, il génère un `event_id` unique pour chaque événement, partagé entre les charges utiles du Pixel et de la CAPI pour assurer la déduplication côté Snapchat.
-   **Mappage d'événements :** Un mappage complet des actions PrestaShop (par exemple, `actionCartSave`, `actionValidateOrder`) aux événements Snapchat standard (`ADD_CART`, `PURCHASE`, `VIEW_CONTENT`, `PAGE_VIEW`).
-   **Gestion du consentement :** Points d'intégration pour les modules de consentement populaires afin d'assurer la conformité GDPR/CCPA.
-   **Outils de qualité des données :** Diagnostics intégrés tels que le Score de santé, le Coach de qualité des données et le Docteur de catalogue pour faciliter la configuration et le dépannage.
-   **CAPI asynchrone :** Les événements CAPI sont souvent mis en file d'attente et envoyés de manière asynchrone, soit en temps réel, soit via une tâche cron, pour améliorer les performances et la fiabilité.
-   **Données de première partie :** Utilise un "Ghost Collector" pour créer des cookies de première partie pour la correspondance `ScCid`, améliorant l'identification de l'utilisateur dans un environnement axé sur la confidentialité.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   `mysnapapi/controllers/front/ajax.php`
    -   **Nom de la classe et classe parente :** `MysnapapiAjaxModuleFrontController` étend `ModuleFrontController`.
    -   **Responsabilité :** Gère diverses requêtes AJAX depuis le front-office, principalement pour la fonctionnalité "Ghost Collector" (ScCid). Il peut collecter des données utilisateur anonymes ou mettre à jour des cookies de première partie sans rechargement complet de la page.
-   `mysnapapi/controllers/front/cron.php`
    -   **Nom de la classe et classe parente :** `MysnapapiCronModuleFrontController` étend `ModuleFrontController`.
    -   **Responsabilité :** Ce contrôleur est conçu pour être appelé par une tâche cron externe. Son rôle principal est de traiter tous les événements côté serveur (CAPI) en file d'attente qui n'ont pas été envoyés en temps réel. Il garantit que toutes les données CAPI sont finalement livrées à Snapchat, améliorant la fiabilité.
-   `mysnapapi/controllers/front/index.php`
    -   **Nom de la classe et classe parente :** `MysnapapiIndexModuleFrontController` étend `ModuleFrontController`.
    -   **Responsabilité :** Généralement un espace réservé ou un point d'entrée par défaut. Il peut gérer l'initialisation de base du module ou rediriger s'il est accédé directement. Souvent, `index.php` dans un répertoire de contrôleur empêche la liste des répertoires.
-   `mysnapapi/controllers/front/sync.php`
    -   **Nom de la classe et classe parente :** `MysnapapiSyncModuleFrontController` étend `ModuleFrontController`.
    -   **Responsabilité :** Gère probablement des tâches de synchronisation de données spécifiques, potentiellement liées aux mises à jour de catalogue de produits ou à d'autres échanges de données avec l'API de Snapchat, séparément du suivi des événements principal.

#### Contrôleurs d'administration Back-Office

-   `mysnapapi/controllers/admin/AdminMysnapapiAjaxController.php`
    -   **Nom de la classe et classe parente :** `AdminMysnapapiAjaxController` étend `AdminController`.
    -   **Nom de l'onglet et entité gérée :** Pas un onglet de menu direct. Ce contrôleur gère les requêtes AJAX provenant de la page de configuration principale du module (méthode `getContent()` de `mysnapapi.php`). Il est responsable du chargement dynamique des données pour les divers outils de diagnostic (Statistiques en direct, Score de santé, etc.) et de la sauvegarde de paramètres de configuration spécifiques sans rechargement complet de la page.
-   `mysnapapi/controllers/admin/index.php`
    -   **Nom de la classe et classe parente :** Pas un contrôleur fonctionnel.
    -   **Nom de l'onglet et entité gérée :** Espace réservé. Empêche la liste des répertoires.

### 4.3 Classes et modèles de base (`classes/`)

-   `mysnapapi/classes/autoload.php` : Fichier d'autoload standard de PrestaShop.
-   `mysnapapi/classes/index.php` : Espace réservé pour empêcher la liste des répertoires.
-   `mysnapapi/classes/MysnapapiCapiClient.php` :
    -   **Interagit avec :** Point de terminaison de l'API Conversions de Snapchat.
    -   **Étend ObjectModel :** Non.
    -   **Méthodes clés :** Gère l'envoi d'événements côté serveur à Snapchat. Encapsule la logique de requête API, l'authentification (à l'aide du jeton CAPI) et la gestion des erreurs.
-   `mysnapapi/classes/MysnapapiCapiTracker.php` :
    -   **Interagit avec :** `ps_configuration` (pour le jeton CAPI), `MysnapapiCapiClient`.
    -   **Étend ObjectModel :** Non.
    -   **Méthodes clés :** Responsable de la préparation et de l'envoi des données d'événement spécifiquement pour l'API Conversions. Il formate les charges utiles d'événement selon les spécifications CAPI de Snapchat.
-   `mysnapapi/classes/MysnapapiCatalogDoctor.php` :
    -   **Interagit avec :** Données produit (des ObjectModels `Product` et `ProductSupplier`).
    -   **Étend ObjectModel :** Non.
    -   **Méthodes clés :** Fournit une logique de diagnostic pour vérifier la cohérence et les problèmes liés aux identifiants de produit utilisés pour la correspondance de catalogue (par exemple, `id_product`, `reference`, `ean13`).
-   `mysnapapi/classes/MysnapapiConsent.php` :
    -   **Interagit avec :** `ps_configuration` (pour les paramètres de consentement), potentiellement d'autres modules de consentement.
    -   **Étend ObjectModel :** Non.
    -   **Méthodes clés :** Gère l'état du consentement. Vérifie si le consentement de l'utilisateur est requis et s'il a été accordé avant d'autoriser le déclenchement des scripts de suivi ou des événements CAPI.
-   `mysnapapi/classes/MysnapapiCurrencyHelper.php` :
    -   **Interagit avec :** La classe `Currency` de PrestaShop.
    -   **Étend ObjectModel :** Non.
    -   **Méthodes clés :** Fournit des fonctions utilitaires pour la gestion du formatage et de la conversion des devises, garantissant que les valeurs d'événement sont envoyées dans le format et le code de devise corrects à Snapchat.
-   `mysnapapi/classes/MysnapapiDataQualityCoach.php` :
    -   **Interagit avec :** Paramètres de configuration du module.
    -   **Étend ObjectModel :** Non.
    -   **Méthodes clés :** Analyse la configuration du module et fournit des recommandations ou des avertissements pour améliorer la qualité des données et l'efficacité du suivi.
-   `mysnapapi/classes/MysnapapiEventId.php` :
    -   **Interagit avec :** Session, cookies.
    -   **Étend ObjectModel :** Non.
    -   **Méthodes clés :** Génère et gère des valeurs `event_id` uniques pour chaque événement suivi. Crucial pour la déduplication lors de l'utilisation du mode de suivi hybride.
-   `mysnapapi/classes/MysnapapiEventMap.php` :
    -   **Interagit avec :** N/A.
    -   **Étend ObjectModel :** Non.
    -   **Méthodes clés :** Définit le mappage entre les événements/données internes de PrestaShop et les noms et paramètres d'événements standard de Snapchat.
-   `mysnapapi/classes/MysnapapiEvents.php` :
    -   **Interagit avec :** Diverses classes de base de PrestaShop (par exemple, `Cart`, `Product`, `Order`).
    -   **Étend ObjectModel :** Non.
    -   **Méthodes clés :** Classe centralisée pour la collecte et le formatage des données d'événement (par exemple, `PageView`, `ViewContent`, `AddToCart`, `Purchase`) du contexte de PrestaShop dans une structure compatible avec Snapchat.
-   `mysnapapi/classes/MysnapapiHealthScore.php` :
    -   **Interagit avec :** Configuration du module, potentiellement données d'événements en direct.
    -   **Étend ObjectModel :** Non.
    -   **Méthodes clés :** Calcule un "score de santé" global pour la configuration de suivi basé sur les options configurées et les problèmes détectés.
-   `mysnapapi/classes/MysnapapiHybridTracker.php` :
    -   **Interagit avec :** `MysnapapiPixelTracker`, `MysnapapiCapiTracker`, `MysnapapiEventId`.
    -   **Étend ObjectModel :** Non.
    -   **Méthodes clés :** Orchestre le suivi en mode "Hybride", garantissant que les événements Pixel et CAPI sont envoyés avec le même `event_id` pour la déduplication.
-   `mysnapapi/classes/MysnapapiLiveStats.php` :
    -   **Interagit avec :** Potentiellement un journal temporaire des événements récents ou des données en temps réel.
    -   **Étend ObjectModel :** Non.
    -   **Méthodes clés :** Collecte et présente des statistiques en temps réel sur les événements suivis pour le panneau d'administration.
-   `mysnapapi/classes/MysnapapiPixelTracker.php` :
    -   **Interagit avec :** `ps_configuration` (pour l'ID du Pixel).
    -   **Étend ObjectModel :** Non.
    -   **Méthodes clés :** Responsable de la génération du code JavaScript pour le Pixel Snap et de son intégration dans le front-office, y compris les données d'événement.
-   `mysnapapi/classes/MysnapapiProductIdResolver.php` :
    -   **Interagit avec :** Données produit.
    -   **Étend ObjectModel :** Non.
    -   **Méthodes clés :** Détermine l'identifiant de produit correct (par exemple, `id_product`, `reference`, `ean13`) à utiliser en fonction de la configuration du module pour la correspondance de catalogue.
-   `mysnapapi/classes/MysnapapiPropertyRules.php` :
    -   **Interagit avec :** N/A.
    -   **Étend ObjectModel :** Non.
    -   **Méthodes clés :** Définit les règles et les validations pour les propriétés d'événement, garantissant que les données envoyées à Snapchat adhèrent à leurs spécifications API.
-   `mysnapapi/classes/MysnapapiTrackerFactory.php` :
    -   **Interagit avec :** Configuration du module (mode de suivi).
    -   **Étend ObjectModel :** Non.
    -   **Méthodes clés :** Modèle de fabrique pour instancier la classe de suivi correcte (`MysnapapiPixelTracker`, `MysnapapiCapiTracker` ou `MysnapapiHybridTracker`) en fonction du mode de suivi configuré du module.
-   `mysnapapi/classes/MysnapapiTrackerInterface.php` :
    -   **Interagit avec :** N/A.
    -   **Étend ObjectModel :** Non.
    -   **Méthodes clés :** Définit une interface commune pour toutes les classes de suivi, garantissant des signatures de méthode cohérentes pour le suivi des événements.
-   `mysnapapi/classes/MysnapapiUserData.php` :
    -   **Interagit avec :** Données client (de l'ObjectModel `Customer`), session, cookies.
    -   **Étend ObjectModel :** Non.
    -   **Méthodes clés :** Collecte et formate les données spécifiques à l'utilisateur (par exemple, e-mail, téléphone, adresse IP, agent utilisateur) pour une correspondance avancée, garantissant que les données sont hachées et conformes.

### 4.4 Actifs JavaScript (`views/js/`)

-   `mysnapapi/tools/console-simulate-bo-ui.js` :
    -   **Portée :** Back-office (outil de développement).
    -   **Description :** Un script utilitaire, probablement pour le développement/débogage, pour simuler ou interagir avec l'interface utilisateur du Back Office depuis la console du navigateur.
-   `mysnapapi/views/js/mp-collect.js` :
    -   **Portée :** Front-office.
    -   **Description :** Script de collecte de données côté client. Il peut écouter des événements DOM spécifiques ou des interactions utilisateur pour déclencher des événements Pixel Snapchat.
-   `mysnapapi/views/js/mp-consent.js` :
    -   **Portée :** Front-office.
    -   **Description :** Gère l'intégration avec les mécanismes de consentement aux cookies. Il vérifie l'état du consentement et charge/initialise conditionnellement le Pixel Snapchat ou le suivi associé. Peut interagir avec `prestashop.on('updateConsent')`.
-   `mysnapapi/views/js/mp-front.js` :
    -   **Portée :** Front-office.
    -   **Description :** JavaScript général du front-office pour le module. Il contient probablement la logique principale pour initialiser le Pixel Snap, pousser les événements vers l'objet `snap` et gérer les déclencheurs d'événements côté client.
-   `mysnapapi/views/js/mp-inspect.js` :
    -   **Portée :** Front-office (mode débogage).
    -   **Description :** Utilisé lorsque le mode débogage est activé. Il intercepte et affiche les événements Snapchat dans la console du navigateur, fournissant des informations détaillées sur les données envoyées.
-   `mysnapapi/views/js/mysnapapi-admin.js` :
    -   **Portée :** Back-office.
    -   **Description :** JavaScript pour l'interface d'administration du module. Gère les interactions de formulaire, les appels AJAX à `AdminMysnapapiAjaxController`, les mises à jour dynamiques des sections de diagnostic (Statistiques en direct, Score de santé) et les étapes de l'assistant.
-   `mysnapapi/views/js/mysnapapi-debug.js` :
    -   **Portée :** Front-office (mode débogage).
    -   **Description :** Similaire à `mp-inspect.js`, fournit des utilitaires de débogage supplémentaires ou des superpositions visuelles pour les développeurs afin de vérifier le suivi.
-   `mysnapapi/views/js/mysnapapi-ghost.js` :
    -   **Portée :** Front-office.
    -   **Description :** Implémente la fonctionnalité "Ghost Collector". Il gère la création et la lecture de cookies de première partie pour la correspondance `ScCid` (Snapchat Click ID), améliorant l'identification de l'utilisateur.
-   `mysnapapi/views/js/mysnapapi-live.js` :
    -   **Portée :** Back-office.
    -   **Description :** Alimente la section "Statistiques en direct" dans le panneau d'administration, effectuant des appels AJAX pour récupérer et afficher les données d'événements en temps réel.
-   `mysnapapi/views/js/mysnapapi-tcf.js` :
    -   **Portée :** Front-office.
    -   **Description :** Spécifiquement pour l'intégration avec les solutions de consentement conformes au Transparency and Consent Framework (TCF), garantissant que le suivi Snapchat adhère aux signaux TCF.
-   `mysnapapi/views/js/mysnapapi-wizard.js` :
    -   **Portée :** Back-office.
    -   **Description :** Fournit une logique interactive pour l'assistant de configuration du module, guidant le marchand à travers les étapes de configuration initiale.
-   `mysnapapi/views/js/mysnapapi.js` :
    -   **Portée :** Front-office.
    -   **Description :** Point d'entrée principal ou JavaScript utilitaire général pour le front-office, chargeant potentiellement d'autres scripts ou contenant des fonctions globales spécifiques au module.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `mysnapapi/views/css/mp-inspect.css` :
    -   **Portée :** Front-office (mode débogage).
    -   **Description :** Styles pour la superposition de débogage ou la sortie de la console lorsque `mp-inspect.js` est actif.
-   `mysnapapi/views/css/mysnapapi-admin.css` :
    -   **Portée :** Style du formulaire d'administration du Back-office.
    -   **Description :** Styles pour la page de configuration du module, y compris la mise en page, les boutons, les sections de diagnostic (Score de santé, Coach de qualité des données) et les étapes de l'assistant.
-   `mysnapapi/views/css/mysnapapi-debug.css` :
    -   **Portée :** Front-office (mode débogage).
    -   **Description :** Style supplémentaire pour les éléments de débogage, potentiellement des indicateurs visuels ou des bordures pour les éléments suivis.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)

-   `mysnapapi/views/templates/hook/capi-pageview.tpl` :
    -   **Hook :** Potentiellement `displayHeader` ou `displayFooter` (contexte côté serveur).
    -   **Sortie :** Rend un élément caché ou un appel côté serveur pour déclencher un événement CAPI `PAGE_VIEW`, souvent utilisé comme solution de secours ou pour le chargement initial de la page.
-   `mysnapapi/views/templates/hook/debug.tpl` :
    -   **Hook :** `displayHeader` ou `displayFooter` (conditionnel au mode débogage).
    -   **Sortie :** Rend les informations de débogage ou initialise les scripts de débogage dans le front-office.
-   `mysnapapi/views/templates/hook/displayOrderConfirmation.tpl` :
    -   **Hook :** `displayOrderConfirmation`.
    -   **Sortie :** Rend l'événement `PURCHASE` du Pixel Snap et/ou déclenche l'événement `PURCHASE` de la CAPI sur la page de confirmation de commande, en transmettant les détails de la commande.
-   `mysnapapi/views/templates/hook/ghost.tpl` :
    -   **Hook :** `displayHeader` ou `displayFooter`.
    -   **Sortie :** Rend le JavaScript pour le "Ghost Collector" afin de gérer les cookies `ScCid`.
-   `mysnapapi/views/templates/hook/header.tpl` :
    -   **Hook :** `displayHeader`.
    -   **Sortie :** Le modèle principal pour initialiser le code de base du Pixel Snap, l'objet `snap` et potentiellement les événements `PAGE_VIEW`. Il charge les fichiers JavaScript nécessaires.
-   `mysnapapi/views/templates/hook/payment.tpl` :
    -   **Hook :** `displayPayment` ou `displayPaymentTop`.
    -   **Sortie :** Rend les événements `INITIATE_CHECKOUT` ou d'autres événements pertinents pendant la phase de sélection du paiement de la commande.
-   `mysnapapi/views/templates/hook/product-details.tpl` :
    -   **Hook :** `displayProductButtons` ou `displayFooterProduct`.
    -   **Sortie :** Rend l'événement `VIEW_CONTENT` du Pixel Snap et l'événement `ADD_CART` (ou le JS associé) sur la page produit, en transmettant les données spécifiques au produit.

#### Modèles d'administration (`views/templates/admin/`)

-   `mysnapapi/views/templates/admin/consent-guide.tpl` : Affiche des conseils sur l'intégration de la gestion du consentement.
-   `mysnapapi/views/templates/admin/doctor.tpl` : Rend l'interface de l'outil de diagnostic "Docteur de catalogue".
-   `mysnapapi/views/templates/admin/dq.tpl` : Rend les recommandations du "Coach de qualité des données".
-   `mysnapapi/views/templates/admin/health.tpl` : Affiche le "Score de santé" et les informations connexes.
-   `mysnapapi/views/templates/admin/linker-domains.tpl` : Champ de saisie et explication pour le suivi inter-domaines.
-   `mysnapapi/views/templates/admin/live-maintain.tpl` : Interface pour maintenir ou effacer les statistiques en direct.
-   `mysnapapi/views/templates/admin/live.tpl` : Affiche le tableau de bord des "Statistiques en direct".
-   `mysnapapi/views/templates/admin/mode-context.tpl` : Fournit le contexte ou l'explication du mode de suivi choisi.
-   `mysnapapi/views/templates/admin/mode-note-both.tpl` : Note spécifique pour le mode de suivi "Hybride".
-   `mysnapapi/views/templates/admin/mode-note-capi.tpl` : Note spécifique pour le mode de suivi "API Conversions uniquement".
-   `mysnapapi/views/templates/admin/mode-note-pixel.tpl` : Note spécifique pour le mode de suivi "Pixel uniquement".
-   `mysnapapi/views/templates/admin/mode-picker.tpl` : L'interface de sélection pour choisir le mode de suivi.
-   `mysnapapi/views/templates/admin/properties-list.tpl` : Affiche une liste des propriétés d'événement et de leurs règles.
-   `mysnapapi/views/templates/admin/recent-events.tpl` : Tableau ou liste affichant les événements suivis les plus récents.
-   `mysnapapi/views/templates/admin/tabs.tpl` : Rend la structure de navigation par onglets pour la page de configuration du module.
-   `mysnapapi/views/templates/admin/tag-chips.tpl` : Composants visuels pour l'affichage des balises ou des identifiants.
-   `mysnapapi/views/templates/admin/tag-ids.tpl` : Champs de saisie pour l'ID du Pixel et le Jeton CAPI.
-   `mysnapapi/views/templates/admin/wizard.tpl` : Le modèle pour l'assistant de configuration étape par étape.

#### Modèles Front-office (`views/templates/front/`)

(Pas de modèles de page autonomes dédiés, tous les modèles front-office sont basés sur des hooks.)

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

Le module utilise principalement la table `ps_configuration` de PrestaShop pour stocker ses paramètres.

-   `ps_configuration` : Stocke les paires clé-valeur pour les paramètres du module (par exemple, `MYSNAPAPI_PIXEL_ID`, `MYSNAPAPI_CAPI_TOKEN`, `MYSNAPAPI_TRACKING_MODE`).
-   Aucune table SQL personnalisée n'est explicitement créée par le module sur la base de l'inventaire fourni. Les événements CAPI peuvent être temporairement mis en file d'attente en mémoire ou dans un système basé sur des fichiers avant d'être envoyés, plutôt que dans une table de base de données dédiée.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rendu dans la section `<head>` de chaque page du front-office. | Initialise le code de base du Pixel Snap, charge les actifs JS, déclenche les événements `PAGE_VIEW` et configure le `ScCid` (Ghost Collector). |
| `displayFooter` | Rendu à la fin de la section `<body>` de chaque page du front-office. | Peut inclure le chargement différé de scripts, des déclencheurs d'événements supplémentaires ou la gestion du `ScCid`. |
| `displayProductButtons` | Sur la page produit, près du bouton "Ajouter au panier". | Déclenche les événements `VIEW_CONTENT` et potentiellement `ADD_CART` avec les détails du produit. |
| `displayFooterProduct` | Sur la page produit, dans la zone du pied de page. | Emplacement alternatif ou supplémentaire pour les événements `VIEW_CONTENT` et `ADD_CART`. |
| `actionCartSave` | Exécuté chaque fois qu'un panier est modifié (ajout, mise à jour, suppression de produit). | Déclenche les événements `ADD_CART` ou `REMOVE_FROM_CART`. |
| `actionValidateOrder` | Exécuté après qu'une commande a été passée avec succès. | Déclenche l'événement crucial `PURCHASE`, envoyant les détails complets de la commande (valeur, devise, produits). |
| `displayOrderConfirmation` | Sur la page de confirmation de commande après un achat réussi. | Rend l'événement `PURCHASE` côté client pour le Pixel Snap. |
| `displayPayment` | Avant la sélection du mode de paiement. | Déclenche l'événement `INITIATE_CHECKOUT`. |
| `displayPaymentTop` | En haut de la page de sélection du paiement. | Emplacement alternatif ou supplémentaire pour l'événement `INITIATE_CHECKOUT`. |
| `actionFrontControllerSetMedia` | Exécuté lorsqu'un contrôleur frontal définit ses actifs multimédias. | Injecte les fichiers CSS et JavaScript spécifiques au module dans le front-office. |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses actifs multimédias. | Injecte les fichiers CSS et JavaScript spécifiques au module dans la page de configuration du back-office. |
| `actionModuleInstall` | Exécuté lors de l'installation du module. | Définit les valeurs de configuration par défaut dans `ps_configuration`. |
| `actionModuleUninstall` | Exécuté lors de la désinstallation du module. | Nettoie les valeurs de configuration de `ps_configuration`. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et les dernières versions du module Pixel Snapchat & API Conversions, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
