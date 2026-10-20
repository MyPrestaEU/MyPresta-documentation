---
title: "Google Analytics 4 - Suivi gtag, MP & dataLayer - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Google Analytics 4 - Suivi gtag, MP & dataLayer par MyPresta.eu."
sidebar:
  label: "Google Analytics 4 - Suivi gtag, MP & dataLayer - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Google Analytics 4 - gtag, MP & dataLayer tracking sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/google-analytics-4-gtag-mp-datalayer-tracking.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/google-analytics-4-gtag-mp-datalayer-tracking/)
>
> ---


# Google Analytics 4 - Suivi gtag, MP & dataLayer

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard telles que cURL, JSON et OpenSSL sont requises pour que le module fonctionne correctement, en particulier pour le suivi Measurement Protocol côté serveur.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

Le module "Google Analytics 4 - Suivi gtag, MP & dataLayer" offre un ensemble complet d'options de configuration, accessibles via sa page de configuration principale et ses écrans d'administration dédiés.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran principal où vous configurerez votre suivi GA4. Le module utilise une interface de type assistant pour vous guider à travers la configuration initiale, mais vous pouvez toujours revenir en arrière et ajuster les paramètres.

#### **Assistant de configuration initiale**

Lors de la première configuration, vous serez probablement accueilli par un assistant. Suivez ses étapes pour configurer rapidement votre propriété GA4 principale.

-   **Étape 1 : Choisir le mode de suivi**

    *   **Ce que fait ce paramètre :** Détermine comment votre boutique envoie des données à Google Analytics 4. C'est une décision cruciale basée sur votre configuration technique et vos exigences en matière de confidentialité.
    *   **Effet de la modification de ce paramètre :**
        *   *`gtag.js` (Recommandé pour la plupart) :* C'est la balise web standard de Google Analytics 4. Elle charge une bibliothèque JavaScript (`gtag.js`) directement sur les pages de votre boutique, qui envoie ensuite des données à GA4. Elle est facile à implémenter mais repose sur l'exécution côté client du navigateur et le consentement aux cookies.
        *   *`dataLayer` (Pour les utilisateurs de Google Tag Manager) :* Ce mode pousse toutes les données d'événement GA4 dans l'objet `dataLayer`, que votre conteneur Google Tag Manager (GTM) lit ensuite et envoie à GA4. Choisissez cette option si vous utilisez déjà GTM pour d'autres balises et souhaitez une gestion centralisée des balises.
        *   *`Measurement Protocol` (Avancé, pour une récupération maximale des données) :* Ce mode envoie des données directement de votre serveur PrestaShop à Google Analytics 4, en contournant entièrement le navigateur. C'est idéal pour récupérer des données lorsque le suivi `gtag.js` ou `dataLayer` est bloqué par des bloqueurs de publicité, les paramètres du navigateur ou un consentement aux cookies refusé. C'est plus complexe mais offre la collecte de données la plus robuste.
    *   **Valeur recommandée :** `gtag.js` pour la simplicité, `dataLayer` si vous utilisez GTM, `Measurement Protocol` si l'exactitude des données est primordiale et que vous êtes à l'aise avec une configuration avancée.
    *   **Scénario / exemple de marchand :** Si vous voulez commencer rapidement et que vous n'utilisez pas GTM, `gtag.js` est parfait. Si vous avez une équipe marketing dédiée gérant GTM, `dataLayer` s'intègre parfaitement. Si vous constatez des écarts importants entre vos ventes et les données GA4, `Measurement Protocol` peut aider à combler cet écart.
-   **Étape 2 : Saisir votre ou vos ID de mesure GA4**

    *   **Ce que fait ce paramètre :** C'est votre identifiant unique pour votre propriété Google Analytics 4 (par exemple, `G-XXXXXXXXXX`). Le module en a besoin pour savoir où envoyer vos données. Vous pouvez ajouter plusieurs ID si vous suivez différentes parties de votre boutique dans des propriétés GA4 distinctes.
    *   **Effet de la modification de ce paramètre :** Les données seront envoyées à la propriété GA4 spécifiée. Des ID incorrects signifient aucune donnée ou des données envoyées au mauvais endroit.
    *   **Valeur recommandée :** Votre ID de mesure GA4 principal.
    *   **Scénario / exemple de marchand :** Vous avez une propriété GA4 principale `G-ABCDEF1234`. Saisissez cet ID. Si vous souhaitez également envoyer des données de produits spécifiques à une propriété distincte `G-XYZW5678`, vous pouvez l'ajouter également.
-   **Étape 3 : Configurer la gestion du consentement (le cas échéant)**

    *   **Ce que fait ce paramètre :** S'intègre à la solution de consentement aux cookies de votre boutique pour garantir que le suivi GA4 respecte les choix de confidentialité de l'utilisateur.
    *   **Effet de la modification de ce paramètre :**
        *   *Activé :* Les balises GA4 ne se déclencheront que si l'utilisateur a donné son consentement pour les cookies d'analyse.
        *   *Désactivé :* Les balises GA4 se déclencheront quel que soit le consentement (non recommandé pour la conformité GDPR/CCPA).
    *   **Valeur recommandée :** Activé, et assurez-vous d'avoir un module de consentement aux cookies robuste installé et configuré.
    *   **Scénario / exemple de marchand :** Un client visite votre boutique et refuse les cookies d'analyse. Avec la gestion du consentement activée, les scripts `gtag.js` ou `dataLayer` ne se chargeront pas, empêchant le suivi côté client. Si vous utilisez le Measurement Protocol, vous pourriez toujours envoyer des données d'achat anonymisées côté serveur.

#### **Paramètres généraux (après l'assistant)**

Une fois l'assistant terminé, vous verrez une interface de configuration plus détaillée, souvent organisée en onglets.

-   **Gestion des ID de mesure**

    *   **Ce que fait ce paramètre :** Vous permet d'ajouter, de modifier ou de supprimer plusieurs ID de mesure GA4 (`G-XXXXXXXXXX`) et de les associer à des modes de suivi spécifiques.
    *   **Effet de la modification de ce paramètre :** Détermine quelles propriétés GA4 reçoivent des données de votre boutique.
    *   **Valeur recommandée :** Ne conservez que les propriétés GA4 nécessaires.
    *   **Scénario / exemple de marchand :** Vous avez créé une nouvelle propriété GA4 pour une campagne marketing spécifique. Vous pouvez ajouter son ID ici pour suivre les performances spécifiques à la campagne.
-   **Domaines de liaison (pour le suivi inter-domaines)**

    *   **Ce que fait ce paramètre :** Si votre boutique fonctionne sur plusieurs domaines (par exemple, `shop.example.com` et `blog.example.com`), ce paramètre aide Google Analytics à comprendre que ceux-ci font partie du même parcours utilisateur, empêchant de nouvelles sessions de démarrer lorsqu'un utilisateur navigue entre eux.
    *   **Effet de la modification de ce paramètre :** Assure un suivi précis du parcours utilisateur sur les domaines liés. Sans cela, les utilisateurs se déplaçant entre vos domaines pourraient être comptés comme de nouveaux utilisateurs ou de nouvelles sessions.
    *   **Valeur recommandée :** Ajoutez tous les domaines liés qu'un utilisateur pourrait visiter dans le cadre de son parcours sur votre site.
    *   **Scénario / exemple de marchand :** Votre boutique principale est `mystore.com` et votre blog est `blog.mystore.com`. Ajoutez `blog.mystore.com` à la liste des domaines de liaison.
-   **Mode débogage**

    *   **Ce que fait ce paramètre :** Active une vue de débogage spéciale dans le front office et envoie des événements de débogage à GA4, vous permettant de vérifier que votre suivi fonctionne correctement.
    *   **Effet de la modification de ce paramètre :**
        *   *Activé :* Un petit panneau de débogage apparaît sur le front office de votre boutique, montrant quels événements GA4 sont envoyés. Les événements apparaissent également dans la vue DebugView de GA4.
        *   *Désactivé :* Pas de panneau de débogage, suivi normal.
    *   **Valeur recommandée :** Activer uniquement pendant les tests et le dépannage. Désactiver pour les boutiques en production.
    *   **Scénario / exemple de marchand :** Vous venez d'installer le module et souhaitez confirmer que les événements `add_to_cart` se déclenchent correctement. Activez le mode débogage, ajoutez un produit à votre panier et vérifiez le panneau de débogage et la vue DebugView de GA4.
-   **Coach de qualité des données**

    *   **Ce que fait ce paramètre :** Fournit des informations et des recommandations pour améliorer la qualité et l'exhaustivité de vos données GA4. Il vérifie les problèmes courants tels que les ID de produit manquants, les formats de devise incorrects, etc.
    *   **Effet de la modification de ce paramètre :** C'est un outil de diagnostic ; il ne modifie pas directement le comportement du front office mais vous aide à identifier et à corriger les problèmes qui pourraient entraîner des analyses inexactes.
    *   **Valeur recommandée :** Examinez régulièrement les recommandations.
    *   **Scénario / exemple de marchand :** Le coach pourrait vous dire que certains produits manquent de codes EAN/UPC, qui sont précieux pour les données de produit GA4. Vous pouvez ensuite mettre à jour votre catalogue de produits.
-   **Docteur du catalogue**

    *   **Ce que fait ce paramètre :** Analyse votre catalogue de produits pour détecter les problèmes potentiels qui pourraient affecter le suivi GA4, tels que les produits sans prix, images ou catégories valides.
    *   **Effet de la modification de ce paramètre :** Similaire au Coach de qualité des données, c'est un outil de diagnostic pour garantir que vos données de produit sont robustes pour GA4.
    *   **Valeur recommandée :** Exécutez cette vérification périodiquement.
    *   **Scénario / exemple de marchand :** Le docteur pourrait signaler des produits en rupture de stock mais toujours visibles, ce qui pourrait perturber le suivi GA4 des vues de produits.
-   **Statistiques en direct**

    *   **Ce que fait ce paramètre :** Affiche les données d'événement en temps réel envoyées de votre boutique à GA4, directement dans votre back office PrestaShop.
    *   **Effet de la modification de ce paramètre :** Fournit un aperçu immédiat des interactions et événements récents des utilisateurs.
    *   **Valeur recommandée :** Utile pour la surveillance, surtout après des modifications ou pendant les périodes de pointe.
    *   **Scénario / exemple de marchand :** Vous venez de lancer un nouveau produit. Vous pouvez consulter les statistiques en direct pour voir les événements `view_item` et `add_to_cart` en temps réel.
-   **Mappage et personnalisation des événements**

    *   **Ce que fait ce paramètre :** Vous permet de personnaliser la façon dont les actions PrestaShop sont mappées aux événements GA4 et à leurs paramètres. Par exemple, vous pourriez vouloir envoyer un paramètre personnalisé avec l'événement `purchase`.
    *   **Effet de la modification de ce paramètre :** Affine les données envoyées à GA4, permettant des rapports plus spécifiques et la création d'audiences.
    *   **Valeur recommandée :** Ne modifiez que si vous avez des besoins spécifiques en matière de rapports GA4.
    *   **Scénario / exemple de marchand :** Vous souhaitez inclure un paramètre personnalisé `loyalty_program_status` avec chaque événement `purchase`. Vous pouvez configurer ce mappage ici.
-   **Règles multi-propriétés**

    *   **Ce que fait ce paramètre :** Définit des règles pour envoyer des événements ou des données spécifiques à différentes propriétés GA4. Par exemple, vous pourriez envoyer tous les événements à votre propriété principale mais uniquement les événements "achat" pour une catégorie spécifique à une propriété distincte.
    *   **Effet de la modification de ce paramètre :** Permet une segmentation avancée de vos données d'analyse sur plusieurs propriétés GA4.
    *   **Valeur recommandée :** À utiliser si vous avez des exigences de suivi complexes impliquant plusieurs propriétés GA4.
    *   **Scénario / exemple de marchand :** Vous avez une propriété GA4 principale pour l'ensemble de votre boutique, mais vous avez également une propriété distincte pour votre ligne de "Produits Premium". Vous pouvez définir une règle pour envoyer les événements `purchase` pour les produits de la catégorie "Produits Premium" aux deux propriétés.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module fournit également des écrans dédiés pour une gestion et un diagnostic plus avancés.

#### **AdminMyanalyticsAjaxController (Back Office > Modules > Google Analytics 4 > [Divers onglets])**

Ce contrôleur gère de nombreux éléments interactifs et affichages de données au sein de la configuration du module, en particulier pour les outils de diagnostic et les statistiques en direct. Vous ne naviguerez pas directement vers ce contrôleur ; il alimente le contenu dynamique de la page de configuration principale.

-   **Nom de l'écran et emplacement du menu :** Ce contrôleur n'est pas un élément de menu autonome. Il sert les requêtes AJAX pour les différents onglets et sections de la page de configuration principale du module (par exemple, "Coach de qualité des données", "Docteur du catalogue", "Statistiques en direct").
-   **Actions et paramètres disponibles :**
    *   **Grille du Coach de qualité des données :** Affiche un tableau des problèmes de qualité des données détectés, souvent avec des suggestions de résolution.
    *   **Rapport du Docteur du catalogue :** Affiche un rapport sur l'intégrité des données des produits.
    *   **Flux d'événements en direct :** Un flux en temps réel des événements envoyés à GA4.
    *   **Étapes de l'assistant :** Gère la progression et la soumission des données pour l'assistant de configuration initiale.
-   **Effet des modifications :** L'interaction avec ces éléments (par exemple, cliquer sur "Exécuter la vérification" pour le Coach de qualité des données) déclenche des processus en arrière-plan qui analysent les données de votre boutique et mettent à jour les informations affichées. Cela vous aide à diagnostiquer et à résoudre les problèmes, mais ne modifie pas directement le comportement du front office.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vérifiez régulièrement les onglets "Coach de qualité des données" et "Docteur du catalogue" pour vous assurer que vos données GA4 restent précises. Surveillez les "Statistiques en direct" pendant les périodes critiques ou après des modifications majeures de la boutique.

#### **index.php (Back Office > Modules > Google Analytics 4)**

C'est le point d'entrée principal pour la configuration du module dans le back office. Bien qu'il soit nommé `index.php`, c'est le cœur de la méthode `getContent()` qui rend l'interface de configuration entière, y compris tous les onglets et paramètres décrits dans la section 4.1.

-   **Nom de l'écran et emplacement du menu :** **Modules > Gestionnaire de modules > Google Analytics 4 - Suivi gtag, MP & dataLayer > Configurer**.
-   **Actions et paramètres disponibles :** Tous les paramètres, onglets et étapes de l'assistant mentionnés dans la section 4.1 sont rendus et gérés via cette vue de configuration principale.
-   **Effet des modifications :** Toute modification enregistrée sur cet écran a un impact direct sur la façon dont votre suivi GA4 est implémenté et sur les données envoyées à Google Analytics.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** C'est ici que vous configurerez initialement le module et reviendrez pour toute modification majeure de vos propriétés GA4, modes de suivi ou règles avancées.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Config principale | **Mode de suivi** | `gtag.js` | Définit la manière dont les données sont envoyées (côté client, GTM ou côté serveur). Crucial pour l'exactitude des données et la confidentialité. |
| Config principale | **ID de mesure** | Votre ID GA4 (`G-XXXXXXXXXX`) | Spécifie quelle propriété GA4 reçoit les données. Des ID incorrects signifient aucune donnée. |
| Config principale | **Gestion du consentement** | Activé (si utilisation d'un module de consentement) | Garantit que le suivi GA4 respecte les choix de confidentialité de l'utilisateur. |
| Config principale | **Domaines de liaison** | Vide (ajouter si inter-domaines) | Permet un suivi précis des utilisateurs sur plusieurs domaines liés. |
| Config principale | **Mode débogage** | Désactivé (activer pour les tests) | Affiche un panneau de débogage en front-office et envoie des événements de débogage à GA4. |
| Config principale | **Coach de qualité des données** | N/A (outil de diagnostic) | Identifie et suggère des corrections pour les problèmes de qualité des données GA4. |
| Config principale | **Docteur du catalogue** | N/A (outil de diagnostic) | Analyse le catalogue de produits pour la préparation au suivi GA4. |
| Config principale | **Statistiques en direct** | N/A (outil de surveillance) | Affiche les événements GA4 en temps réel dans le back office. |
| Config principale | **Mappage des événements** | Par défaut (modifier pour des besoins personnalisés) | Personnalise la façon dont les actions PrestaShop sont mappées aux événements et paramètres GA4. |
| Config principale | **Règles multi-propriétés** | Aucune (ajouter pour un suivi avancé) | Définit des règles pour envoyer des données spécifiques à différentes propriétés GA4. |
| AdminMyanalyticsAjaxController | (Diverses vues AJAX) | N/A | Alimente le contenu dynamique des outils de diagnostic et des statistiques en direct. |
| index.php | (Page de configuration principale) | N/A | Rend l'interface de configuration complète du module. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai installé le module, mais je ne vois aucune donnée dans ma propriété Google Analytics 4.**

-   **R :** Tout d'abord, assurez-vous d'avoir saisi le bon ID de mesure GA4 (commençant par `G-`) dans la configuration du module.
-   **R :** Vérifiez la "DebugView" de votre propriété GA4 (dans Google Analytics, allez dans Admin > DebugView) pendant que vous naviguez sur votre boutique. Si vous y voyez des événements, des données sont envoyées.
-   **R :** Videz le cache Smarty de votre PrestaShop (Paramètres avancés > Performances > Vider le cache).
-   **R :** Si vous utilisez `gtag.js` ou `dataLayer`, vérifiez la console de développement de votre navigateur (F12) pour toute erreur JavaScript. Assurez-vous également d'avoir accepté les cookies d'analyse si vous avez un module de consentement.
-   **R :** Si vous utilisez le Measurement Protocol, assurez-vous que `cURL` est activé sur votre serveur et qu'il n'y a pas de règles de pare-feu bloquant les connexions sortantes vers les serveurs de Google.

**Q2 : Mes données d'achat GA4 ne correspondent pas à mes données de commande PrestaShop.**

-   **R :** C'est un problème courant, souvent dû aux bloqueurs de publicité, aux paramètres de confidentialité du navigateur ou au refus de consentement aux cookies par les utilisateurs.
-   **R :** **Envisagez fortement d'activer le Measurement Protocol pour les événements d'achat.** Cela envoie les données d'achat directement depuis votre serveur, contournant les problèmes de navigateur côté client.
-   **R :** Utilisez le "Coach de qualité des données" et le "Docteur du catalogue" du module pour identifier toute incohérence de données qui pourrait causer des problèmes.
-   **R :** Assurez-vous que votre page de confirmation de commande est toujours atteinte par les clients après un achat réussi. Si les clients sont redirigés ailleurs ou ferment le navigateur trop tôt, les événements d'achat côté client pourraient ne pas se déclencher.

**Q3 : Le panneau de débogage du module n'apparaît pas, ou je ne vois pas d'événements dans la DebugView de GA4.**

-   **R :** Assurez-vous que le "Mode débogage" est explicitement activé dans la configuration du module.
-   **R :** Videz le cache de votre navigateur et le cache Smarty de PrestaShop.
-   **R :** Assurez-vous d'être connecté en tant qu'administrateur dans votre back office PrestaShop et de naviguer sur le front office dans la même session de navigateur.
-   **R :** Vérifiez la console de développement de votre navigateur pour toute erreur JavaScript qui pourrait empêcher le chargement du panneau de débogage.

**Q4 : Comment m'assurer que le module respecte mon module de consentement aux cookies ?**

-   **R :** Le module est conçu pour s'intégrer aux mécanismes standard de consentement aux cookies. Dans la configuration du module, il devrait y avoir un paramètre pour la "Gestion du consentement". Assurez-vous qu'il est activé.
-   **R :** Vérifiez que votre module de consentement aux cookies catégorise correctement les cookies d'analyse et que les choix des utilisateurs sont stockés et respectés. Le module GA4 ne chargera alors les balises côté client (`gtag.js`, `dataLayer`) que si le consentement est donné.
-   **R :** Pour une récupération maximale des données, envisagez d'utiliser le Measurement Protocol pour les événements critiques comme `purchase`, car il peut souvent contourner les problèmes de consentement côté client (bien que vous deviez toujours informer les utilisateurs du traitement des données).

**Q5 : Je souhaite suivre des événements ou des paramètres personnalisés non couverts par la configuration par défaut.**

-   **R :** Le module comprend une section "Mappage et personnalisation des événements". Ici, vous pouvez définir comment les actions PrestaShop sont mappées aux événements GA4 et ajouter des paramètres personnalisés.
-   **R :** Pour un suivi personnalisé très complexe, en particulier avec `dataLayer`, vous devrez peut-être combiner les capacités de ce module avec des scripts personnalisés dans votre conteneur Google Tag Manager.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module `myanalytics` pour PrestaShop est conçu pour fournir une intégration Google Analytics 4 robuste et flexible. Il suit une approche modulaire et orientée objet, tirant parti du modèle MVC et du système de hooks de PrestaShop.

Composants architecturaux clés :

-   **Classe de module principale (`Myanalytics`) :** Gère l'installation, la désinstallation, l'enregistrement des hooks et la méthode `getContent()` principale pour la configuration du back-office.
-   **Fabrique de traqueurs (`MyanalyticsTrackerFactory`) :** Instancie dynamiquement le mécanisme de suivi approprié (`gtag.js`, `dataLayer` ou `Measurement Protocol`) en fonction de la configuration du module.
-   **Classes de traqueurs dédiées :** Chaque méthode de suivi (`MyanalyticsGtagTracker`, `MyanalyticsDataLayerTracker`, `MyanalyticsMpTracker`) implémente `MyanalyticsTrackerInterface` et encapsule la logique d'envoi des événements GA4 via sa méthode spécifique.
-   **Mappage des événements et gestion de la couche de données :** Des classes comme `MyanalyticsEvents` et `MyanalyticsDataLayerTracker` sont responsables de la traduction des actions PrestaShop (par exemple, vue de produit, ajout au panier) en noms d'événements et paramètres conformes à GA4.
-   **Outils de diagnostic :** Des classes comme `MyanalyticsDataQualityCoach`, `MyanalyticsCatalogDoctor` et `MyanalyticsHealthScore` fournissent des informations en back-office sur l'intégrité des données et l'état du suivi.
-   **Contrôleurs d'administration :** Gèrent les requêtes AJAX pour le contenu dynamique dans le back-office (par exemple, statistiques en direct, rapports de diagnostic).
-   **Contrôleurs frontaux :** Principalement utilisés pour les points d'extrémité AJAX, en particulier pour le Measurement Protocol de secours ou les actions liées au consentement.
-   **Templates Smarty :** Utilisés pour le rendu des vues de configuration du back-office et des scripts de suivi du front-office injectés via des hooks.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   `controllers/front/ajax.php`
    *   **Nom de la classe et classe parente :** `MyanalyticsAjaxModuleFrontController` étend `ModuleFrontController`.
    *   **Responsabilité :** Gère les requêtes AJAX du front office. Cela peut inclure l'envoi d'événements Measurement Protocol dans des scénarios spécifiques (par exemple, lorsque le suivi côté client est bloqué), la mise à jour de l'état du consentement ou d'autres interactions dynamiques qui ne nécessitent pas un rechargement complet de la page. Il renvoie généralement des réponses JSON.
-   `controllers/front/index.php`
    *   **Nom de la classe et classe parente :** `MyanalyticsIndexModuleFrontController` étend `ModuleFrontController`.
    *   **Responsabilité :** Ce contrôleur peut servir de solution de repli ou de point d'extrémité spécifique pour certaines fonctionnalités du module, bien que souvent la classe de module principale gère la plupart des injections de scripts du front-office via des hooks. Il pourrait être utilisé pour des redirections spécifiques ou le traitement de données si nécessaire.

#### Contrôleurs d'administration Back-Office

-   `controllers/admin/AdminMyanalyticsAjaxController.php`
    *   **Nom de la classe et classe parente :** `AdminMyanalyticsAjaxController` étend `AdminController`.
    *   **Nom de l'onglet et entité gérée :** Ce contrôleur n'est pas directement accessible en tant qu'élément de menu. Il sert les requêtes AJAX de la page de configuration principale du module (`getContent()`). Il gère les mises à jour dynamiques pour des sections comme le Coach de qualité des données, le Docteur du catalogue, les Statistiques en direct et les étapes de l'assistant de configuration.
    *   **Responsabilité :** Traite les requêtes pour les rapports de diagnostic, les données d'événements en direct et les soumissions d'étapes de l'assistant, renvoyant des données JSON pour mettre à jour l'interface utilisateur du back-office.
-   `controllers/admin/index.php`
    *   **Nom de la classe et classe parente :** `AdminMyanalyticsIndexController` étend `AdminController`.
    *   **Nom de l'onglet et entité gérée :** Similaire à `AdminMyanalyticsAjaxController`, il s'agit probablement d'un contrôleur interne ou d'un espace réservé. La configuration principale du back-office est gérée par la méthode `getContent()` de la classe de module `Myanalytics` principale.

### 4.3 Classes et modèles principaux (`classes/`)

-   `classes/autoload.php` : Fichier d'autoload standard de PrestaShop pour les classes de module.
-   `classes/index.php` : Fichier vide, pratique courante pour empêcher l'affichage du contenu du répertoire.
-   `classes/MyanalyticsCatalogDoctor.php`
    *   **Ce qu'il fait :** Analyse le catalogue de produits PrestaShop pour les problèmes de qualité des données pertinents pour le suivi GA4 (par exemple, prix manquants, images, catégories invalides).
    *   **Méthodes publiques clés :** Méthodes pour exécuter des vérifications et récupérer des rapports sur la santé du catalogue.
-   `classes/MyanalyticsConsent.php`
    *   **Ce qu'il fait :** Gère et interagit avec les mécanismes de consentement aux cookies, déterminant si le suivi analytique est autorisé en fonction des choix de l'utilisateur.
    *   **Méthodes publiques clés :** Méthodes pour vérifier l'état du consentement, définir le consentement et potentiellement s'intégrer à des modules de consentement tiers.
-   `classes/MyanalyticsCurrencyHelper.php`
    *   **Ce qu'il fait :** Fournit des fonctions utilitaires pour la gestion du formatage et de la conversion des devises, garantissant que GA4 reçoit les données de devise dans le bon format.
-   `classes/MyanalyticsDataLayerTracker.php`
    *   **Ce qu'il fait :** Implémente `MyanalyticsTrackerInterface` pour le suivi `dataLayer`. Il pousse les données d'événement GA4 dans le tableau JavaScript `dataLayer`, les rendant disponibles pour Google Tag Manager.
    *   **Méthodes publiques clés :** Méthodes pour ajouter des événements à la couche de données, gérer des événements e-commerce spécifiques (par exemple, `add_to_cart`, `purchase`).
-   `classes/MyanalyticsDataQualityCoach.php`
    *   **Ce qu'il fait :** Fournit un outil de diagnostic pour identifier et signaler les problèmes potentiels de qualité des données dans le flux d'événements GA4 ou la configuration.
    *   **Méthodes publiques clés :** Méthodes pour exécuter des vérifications de qualité des données et générer des rapports.
-   `classes/MyanalyticsEventId.php`
    *   **Ce qu'il fait :** Probablement une classe utilitaire pour générer des ID d'événement uniques, ce qui peut être utile pour la déduplication dans GA4, en particulier avec le Measurement Protocol.
-   `classes/MyanalyticsEventMap.php`
    *   **Ce qu'il fait :** Définit le mappage entre les actions/données de PrestaShop et les noms et paramètres d'événements GA4 standard.
    *   **Méthodes publiques clés :** Méthodes pour récupérer les définitions d'événements et les mappages de paramètres.
-   `classes/MyanalyticsEvents.php`
    *   **Ce qu'il fait :** Une classe centrale pour déclencher et gérer les événements GA4 au sein du module. Elle orchestre quel traqueur (gtag, datalayer, MP) doit gérer quel événement.
    *   **Méthodes publiques clés :** Méthodes comme `trackPageView()`, `trackAddToCart()`, `trackPurchase()`, etc.
-   `classes/MyanalyticsGtagTracker.php`
    *   **Ce qu'il fait :** Implémente `MyanalyticsTrackerInterface` pour le suivi `gtag.js`. Il génère et injecte le code JavaScript nécessaire pour envoyer des événements directement à GA4 via `gtag()`.
    *   **Méthodes publiques clés :** Méthodes pour générer des appels `gtag()` pour divers événements GA4.
-   `classes/MyanalyticsHealthScore.php`
    *   **Ce qu'il fait :** Calcule et affiche un "score de santé" pour l'intégration GA4, basé sur diverses vérifications et bonnes pratiques.
-   `classes/MyanalyticsLiveStats.php`
    *   **Ce qu'il fait :** Collecte et fournit des statistiques en temps réel sur les événements envoyés à GA4, affichées dans le back office.
-   `classes/MyanalyticsMpClient.php`
    *   **Ce qu'il fait :** Gère les requêtes HTTP réelles pour l'envoi de données à Google Analytics 4 via le Measurement Protocol.
    *   **Méthodes publiques clés :** Méthodes pour construire et envoyer des charges utiles Measurement Protocol.
-   `classes/MyanalyticsMpTracker.php`
    *   **Ce qu'il fait :** Implémente `MyanalyticsTrackerInterface` pour le suivi `Measurement Protocol`. Il prépare les données d'événement et utilise `MyanalyticsMpClient` pour les envoyer côté serveur.
    *   **Méthodes publiques clés :** Méthodes pour formater et envoyer des événements côté serveur.
-   `classes/MyanalyticsProductIdResolver.php`
    *   **Ce qu'il fait :** Résout divers identifiants de produit (ID, référence, EAN, UPC) pour garantir que des données de produit cohérentes sont envoyées à GA4.
-   `classes/MyanalyticsPropertyRules.php`
    *   **Ce qu'il fait :** Gère la logique de suivi multi-propriétés, définissant des règles pour savoir quels événements vont à quelles propriétés GA4.
-   `classes/MyanalyticsTrackerFactory.php`
    *   **Ce qu'il fait :** Une classe de fabrique responsable de la création et du retour de l'implémentation correcte de `MyanalyticsTrackerInterface` basée sur la configuration du module (gtag, datalayer ou MP).
-   `classes/MyanalyticsTrackerInterface.php`
    *   **Ce qu'il fait :** Définit l'interface commune que toutes les classes de traqueurs GA4 doivent implémenter, garantissant la cohérence dans la gestion des événements.
-   `classes/MyanalyticsUserData.php`
    *   **Ce qu'il fait :** Collecte et formate les données spécifiques à l'utilisateur (par exemple, ID utilisateur, données démographiques) pour le suivi GA4, en respectant les paramètres de confidentialité.

### 4.4 Assets JavaScript (`views/js/`)

-   `myanalytics/views/js/myanalytics-admin.js`
    *   **Portée :** Back-office.
    *   **Ce qu'il fait :** Fournit des fonctionnalités interactives pour les pages de configuration du back-office du module. Cela inclut la gestion des soumissions de formulaires, les appels AJAX pour les outils de diagnostic (Coach de qualité des données, Docteur du catalogue), la mise à jour des statistiques en direct et la gestion des règles multi-propriétés.
-   `myanalytics/views/js/myanalytics-debug.js`
    *   **Portée :** Front-office (lorsque le mode débogage est activé).
    *   **Ce qu'il fait :** Injecte un panneau de débogage dans le front office, affichant les événements GA4 au fur et à mesure qu'ils sont déclenchés. Il écoute les appels `gtag()` ou les événements `dataLayer.push()` et les rend pour une vérification facile.
-   `myanalytics/views/js/myanalytics-ghost.js`
    *   **Portée :** Front-office.
    *   **Ce qu'il fait :** Ce script pourrait être lié au suivi "fantôme" ou "ombre", potentiellement pour le Measurement Protocol de secours ou pour capturer des événements qui pourraient autrement être manqués. Il pourrait impliquer l'écoute d'événements DOM spécifiques et le déclenchement d'appels côté serveur.
-   `myanalytics/views/js/myanalytics-live.js`
    *   **Portée :** Back-office.
    *   **Ce qu'il fait :** Alimente la fonction "Statistiques en direct" dans le back office. Il utilise probablement AJAX pour récupérer périodiquement les événements GA4 récents du serveur et met à jour l'affichage en temps réel.
-   `myanalytics/views/js/myanalytics-wizard.js`
    *   **Portée :** Back-office.
    *   **Ce qu'il fait :** Fournit la logique interactive pour l'assistant de configuration du module, guidant l'utilisateur à travers les étapes de configuration initiale, validant les entrées et soumettant les données via AJAX.
-   `myanalytics/views/js/myanalytics.js`
    *   **Portée :** Front-office.
    *   **Ce qu'il fait :** Le fichier JavaScript principal du front-office. Il gère la logique de suivi GA4 côté client, y compris :
        *   L'initialisation de `gtag.js` ou `dataLayer`.
        *   L'écoute des événements DOM (par exemple, clics sur les boutons "Ajouter au panier", vues d'images de produits).
        *   La collecte des données pertinentes sur les produits et les utilisateurs.
        *   Le push d'événements vers `dataLayer` ou l'appel de commandes `gtag()`.
        *   Potentiellement la gestion de l'intégration du consentement aux cookies.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `myanalytics/views/css/myanalytics-admin.css`
    *   **Portée :** Style du formulaire d'administration du back-office.
    *   **Ce qu'il fait :** Style la page de configuration du module, y compris les onglets, les champs de saisie, les boutons, les rapports de diagnostic et les affichages de statistiques en direct, garantissant une interface cohérente et conviviale au sein du back office de PrestaShop.
-   `myanalytics/views/css/myanalytics-debug.css`
    *   **Portée :** Style client du front-office (lorsque le mode débogage est activé).
    *   **Ce qu'il fait :** Style le panneau de débogage du front-office, le rendant visuellement distinct et lisible pour les développeurs et les administrateurs.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

-   `myanalytics/views/templates/hook/debug.tpl`
    *   **Hook :** Probablement injecté via `displayHeader` ou `displayFooter` de manière conditionnelle lorsque le mode débogage est actif.
    *   **Sorties :** La structure HTML du panneau de débogage du front-office.
-   `myanalytics/views/templates/hook/displayOrderConfirmation.tpl`
    *   **Hook :** `displayOrderConfirmation`.
    *   **Sorties :** Le code JavaScript nécessaire ou les push `dataLayer` pour l'événement `purchase`, incluant généralement les détails de la transaction, les informations sur le produit et potentiellement les paramètres du Measurement Protocol.
-   `myanalytics/views/templates/hook/ghost.tpl`
    *   **Hook :** Pourrait être `displayHeader` ou `displayFooter`.
    *   **Sorties :** Code JavaScript lié au suivi "fantôme", potentiellement pour le Measurement Protocol de secours ou la capture d'événements avancés.
-   `myanalytics/views/templates/hook/header.tpl`
    *   **Hook :** `displayHeader`.
    *   **Sorties :** Le script d'initialisation principal `gtag.js` ou `dataLayer`, incluant le ou les ID de mesure GA4 et toutes les configurations globales. Ceci est crucial pour le suivi initial des vues de page.
-   `myanalytics/views/templates/hook/mp-pageview.tpl`
    *   **Hook :** Probablement `displayHeader` ou `displayFooter` (conditionnellement pour le Measurement Protocol).
    *   **Sorties :** Code rendu côté serveur pour envoyer un événement `page_view` via le Measurement Protocol, particulièrement utile lorsque le suivi côté client est bloqué ou que le consentement est refusé.
-   `myanalytics/views/templates/hook/payment.tpl`
    *   **Hook :** `displayPaymentTop` ou des hooks similaires liés au paiement.
    *   **Sorties :** JavaScript ou push `dataLayer` pour les événements `add_payment_info` ou `begin_checkout`, capturant la sélection du mode de paiement.
-   `myanalytics/views/templates/hook/product-details.tpl`
    *   **Hook :** `displayProductButtons`, `displayProductExtraContent` ou des hooks similaires de page produit.
    *   **Sorties :** JavaScript ou push `dataLayer` pour les événements `view_item` et `add_to_cart`, incluant des informations détaillées sur le produit.

#### Templates d'administration (`views/templates/admin/`)

-   `myanalytics/views/templates/admin/doctor.tpl` : Rend l'interface du Docteur du catalogue, affichant les rapports et les recommandations.
-   `myanalytics/views/templates/admin/dq.tpl` : Rend l'interface du Coach de qualité des données, affichant les problèmes de qualité des données.
-   `myanalytics/views/templates/admin/health.tpl` : Affiche le score de santé global et les métriques associées pour l'intégration GA4.
-   `myanalytics/views/templates/admin/linker-domains.tpl` : Rend le champ de saisie et la liste pour la gestion des domaines de liaison inter-domaines.
-   `myanalytics/views/templates/admin/live-maintain.tpl` : Probablement un sous-template pour les statistiques en direct, éventuellement pour les messages de maintenance ou les contrôles.
-   `myanalytics/views/templates/admin/live.tpl` : Rend l'interface principale de la fonction Statistiques en direct, affichant les données d'événements en temps réel.
-   `myanalytics/views/templates/admin/measurement-ids.tpl` : Rend la section pour la gestion de plusieurs ID de mesure GA4.
-   `myanalytics/views/templates/admin/mode-context.tpl` : Fournit des informations contextuelles ou des explications pour le mode de suivi choisi.
-   `myanalytics/views/templates/admin/mode-note-datalayer.tpl` : Notes ou instructions spécifiques pour le mode de suivi `dataLayer`.
-   `myanalytics/views/templates/admin/mode-note-gtag.tpl` : Notes ou instructions spécifiques pour le mode de suivi `gtag.js`.
-   `myanalytics/views/templates/admin/mode-note-mp.tpl` : Notes ou instructions spécifiques pour le mode de suivi `Measurement Protocol`.
-   `myanalytics/views/templates/admin/mode-picker.tpl` : Rend les boutons radio ou la liste déroulante pour la sélection du mode de suivi GA4.
-   `myanalytics/views/templates/admin/properties-list.tpl` : Affiche une liste des propriétés GA4 configurées.
-   `myanalytics/views/templates/admin/recent-events.tpl` : Un sous-template pour afficher une liste d'événements récents, souvent utilisé dans les statistiques en direct ou les vues de débogage.
-   `myanalytics/views/templates/admin/tabs.tpl` : Rend la structure de navigation par onglets pour la page de configuration du module.
-   `myanalytics/views/templates/admin/tag-chips.tpl` : Affiche des "chips" ou des étiquettes visuelles pour les balises/propriétés GA4 configurées.
-   `myanalytics/views/templates/admin/wizard.tpl` : Rend la structure globale et les étapes de l'assistant de configuration du module.

#### Templates Front-office (`views/templates/front/`)

Le module ne semble pas avoir de templates de page front-office autonomes dédiés, s'appuyant plutôt sur l'injection de scripts et de données via des hooks.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** :

    *   Le module stocke principalement sa configuration dans la table `ps_configuration` de PrestaShop.
    *   Il pourrait également créer des tables personnalisées pour :
        *   `ps_myanalytics_events` : Pour enregistrer les événements Measurement Protocol ou d'autres données d'événements internes pour le débogage/les statistiques en direct.
        *   `ps_myanalytics_properties` : Pour stocker les détails sur plusieurs propriétés GA4 et leurs règles associées.
        *   `ps_myanalytics_consent` : Pour stocker l'état du consentement ou s'intégrer aux modules de consentement.
        *   `ps_myanalytics_health_log` : Pour stocker les résultats des vérifications de santé et des rapports de qualité des données.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Injecter les scripts d'initialisation `gtag.js` ou `dataLayer`, la configuration globale de GA4 et potentiellement les événements `page_view`. |
| `displayFooter` | Avant la balise de fermeture `</body>` de chaque page. | Injecter des scripts de suivi supplémentaires, des panneaux de débogage ou des appels Measurement Protocol de secours. |
| `displayOrderConfirmation` | Sur la page de confirmation de commande après un achat réussi. | Envoyer l'événement crucial `purchase` à GA4, y compris les détails de la transaction et les données du produit. C'est souvent là que le Measurement Protocol est utilisé. |
| `displayProductButtons` | Près des boutons d'action du produit (par exemple, "Ajouter au panier") sur la page du produit. | Injecter du JavaScript pour capturer les événements `add_to_cart`. |
| `displayProductExtraContent` | Dans la section de contenu supplémentaire de la page du produit. | Injecter du JavaScript pour les événements `view_item` ou d'autres interactions de détails de produit. |
| `displayPaymentTop` | Avant les options de paiement sur la page de commande. | Capturer les événements `begin_checkout` et `add_payment_info`. |
| `actionFrontControllerSetMedia` | Lorsqu'un contrôleur frontal définit ses assets multimédias. | Mettre en file d'attente les fichiers JS/CSS spécifiques au module pour le front office. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration définit ses assets multimédias. | Mettre en file d'attente les fichiers JS/CSS spécifiques au module pour le back office. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | Déclencher les événements `purchase` du Measurement Protocol côté serveur, garantissant la capture des données même si le côté client échoue. |
| `actionObjectProductAddAfter` | Après l'ajout d'un nouveau produit. | Potentiellement déclencher des vérifications du docteur du catalogue ou mettre à jour les caches de données de produits internes. |
| `actionObjectProductUpdateAfter` | Après la mise à jour d'un produit existant. | Similaire à `actionObjectProductAddAfter`. |
| `actionObjectProductDeleteAfter` | Après la suppression d'un produit. | Nettoyer toutes les données de suivi ou les caches associés. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour vous assurer que vous utilisez la version la plus récente et la plus compatible du module "Google Analytics 4 - Suivi gtag, MP & dataLayer", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/).

MyPresta.eu fournit un support dédié pour tous ses modules, garantissant que l'intégration analytique de votre boutique reste robuste et à jour avec les dernières normes GA4 et versions de PrestaShop.
