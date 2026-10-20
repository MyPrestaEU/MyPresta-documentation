---
title: "Pixel TikTok / API Événements - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Pixel TikTok / API Événements par MyPresta.eu."
sidebar:
  label: "Pixel TikTok / API Événements - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module TikTok Pixel / Events API sur MyPresta.eu](https://mypresta.eu/modules/social-networks/tiktok-pixel-events-api.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/tiktok-pixel-events-api/)
>
> ---


# Pixel TikTok / API Événements

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises pour que le module fonctionne correctement, en particulier pour l'API Événements (suivi côté serveur). Celles-ci sont généralement disponibles sur la plupart des environnements d'hébergement modernes.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est la zone de configuration principale où vous configurerez votre Pixel TikTok et l'API Événements. Les paramètres sont conçus pour être intuitifs, vous guidant à travers le processus de connexion de votre boutique à TikTok Ads.

#### **Paramètres généraux**

- **ID du Pixel TikTok :**

  - **Ce que fait ce paramètre :** C'est votre identifiant unique fourni par le Gestionnaire de publicités TikTok. Il indique à TikTok à quel compte publicitaire appartiennent les données de votre site web.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est saisi :* Le module commencera à envoyer des données à votre Pixel TikTok spécifié.
    - *Lorsqu'il est laissé vide :* Aucune donnée ne sera envoyée à TikTok via le Pixel, et le module ne fonctionnera pas pour le suivi côté navigateur.
  - **Valeur recommandée :** Votre ID de Pixel TikTok valide.
  - **Scénario / exemple de marchand :** Vous créez un compte publicitaire TikTok et configurez un Pixel. TikTok vous fournit un ID numérique (par exemple, `1234567890`). Vous entrez cet ID ici pour lier votre boutique à votre compte TikTok.
- **Jeton d'accès TikTok (pour l'API Événements) :**

  - **Ce que fait ce paramètre :** C'est un jeton sécurisé généré dans votre Gestionnaire de publicités TikTok qui autorise votre boutique PrestaShop à envoyer des données directement aux serveurs de TikTok via l'API Événements. Il est crucial pour le suivi côté serveur.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est saisi :* Active le suivi côté serveur (API Événements), qui est plus fiable et moins affecté par les bloqueurs de publicités.
    - *Lorsqu'il est laissé vide :* Le suivi côté serveur sera désactivé.
  - **Valeur recommandée :** Votre jeton d'accès valide pour l'API Événements TikTok.
  - **Scénario / exemple de marchand :** Pour améliorer la précision des données et contourner les limitations du navigateur, vous décidez d'utiliser l'API Événements. Vous générez un jeton d'accès dans le Gestionnaire de publicités TikTok et le collez ici.
- **Mode de suivi :**

  - **Ce que fait ce paramètre :** Détermine comment les données sont envoyées à TikTok. Vous pouvez choisir entre Pixel (côté navigateur), API Événements (côté serveur) ou Mode Dual (les deux).
  - **Effet de la modification de ce paramètre :**
    - *Pixel uniquement :* Seul le suivi côté navigateur est actif.
    - *API Événements uniquement :* Seul le suivi côté serveur est actif.
    - *Mode Dual (Recommandé) :* Le Pixel et l'API Événements sont tous deux actifs. Le module utilise intelligemment un `event_id` partagé pour dédupliquer les événements dans TikTok, garantissant la précision.
  - **Valeur recommandée :** `Mode Dual` pour une précision maximale des données et une résilience contre les bloqueurs de publicités.
  - **Scénario / exemple de marchand :** Vous souhaitez le suivi le plus fiable possible. Vous sélectionnez « Mode Dual » afin que si un client utilise un bloqueur de publicités, l'API Événements côté serveur puisse toujours capturer la conversion, et TikTok ne la comptera pas deux fois si les deux méthodes réussissent.
- **Activer le mode débogage :**

  - **Ce que fait ce paramètre :** Active un mode spécial qui affiche des informations détaillées sur les événements TikTok envoyés, directement dans la console de développement de votre navigateur. C'est inestimable pour le dépannage.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les développeurs et les utilisateurs avancés peuvent voir exactement quelles données sont envoyées à TikTok en temps réel, aidant à vérifier la configuration correcte.
    - *Lorsqu'il est désactivé :* Aucune information de débogage n'est affichée.
  - **Valeur recommandée :** `Non` pour les boutiques de production en direct. N'activez temporairement que pour les tests et le débogage.
  - **Scénario / exemple de marchand :** Vous venez d'installer le module et souhaitez vous assurer que les événements `AddToCart` se déclenchent correctement. Vous activez le mode débogage, ajoutez un article à votre panier et vérifiez votre console de navigateur pour les données d'événement TikTok.

#### **Paramètres avancés**

- **Gestion du consentement (RGPD/CCPA) :**

  - **Ce que fait ce paramètre :** S'intègre à la solution de consentement aux cookies de votre boutique (si disponible) pour garantir que le suivi TikTok ne s'active qu'après que le client a donné son consentement.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le Pixel TikTok/API Événements ne se chargera et n'enverra des données que si le client a accepté les cookies.
    - *Lorsqu'il est désactivé :* Le suivi aura lieu quel que soit le consentement aux cookies, ce qui pourrait ne pas être conforme aux réglementations de confidentialité comme le RGPD ou le CCPA.
  - **Valeur recommandée :** `Oui` si votre boutique opère dans des régions avec des lois de confidentialité strictes (par exemple, UE, Californie).
  - **Scénario / exemple de marchand :** Votre boutique dessert des clients dans l'Union européenne. Pour vous conformer au RGPD, vous activez ce paramètre, garantissant que le suivi TikTok respecte les choix de confidentialité des utilisateurs.
- **Type d'ID produit :**

  - **Ce que fait ce paramètre :** Détermine quel identifiant de produit (ID) est envoyé à TikTok. Les options incluent généralement l'ID interne du produit de PrestaShop, EAN13, UPC ou une référence personnalisée. C'est crucial pour faire correspondre les produits dans votre catalogue de produits TikTok.
  - **Effet de la modification de ce paramètre :**
    - *Modification du type :* Garantit que les ID de produit envoyés à TikTok correspondent aux ID utilisés dans votre catalogue de produits TikTok, permettant des publicités de produits dynamiques.
  - **Valeur recommandée :** Choisissez le type d'ID que vous utilisez dans votre catalogue de produits TikTok. Souvent, l'`ID produit` de PrestaShop ou l'`EAN13` sont des choix courants.
  - **Scénario / exemple de marchand :** Vous avez téléchargé un catalogue de produits sur TikTok en utilisant les codes EAN13 de vos produits. Vous sélectionnez `EAN13` ici pour vous assurer que TikTok peut identifier correctement les produits que les clients consultent ou achètent.
- **Domaines de liaison (pour le suivi inter-domaines) :**

  - **Ce que fait ce paramètre :** Vous permet de spécifier des noms de domaine supplémentaires si le parcours de votre client implique plusieurs domaines (par exemple, une boutique principale et un blog séparé sur un domaine différent). Cela aide TikTok à suivre les utilisateurs de manière transparente sur ces domaines.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque des domaines sont ajoutés :* TikTok peut maintenir la cohérence du suivi des utilisateurs sur les domaines listés.
    - *Lorsqu'il est laissé vide :* Le suivi pourrait être interrompu si les clients naviguent entre différents domaines qui font partie de votre entreprise.
  - **Valeur recommandée :** Ajoutez tous les sous-domaines ou domaines liés pertinents que vos clients pourraient visiter.
  - **Scénario / exemple de marchand :** Votre boutique principale est `mystore.com`, mais vous avez un blog sur `blog.mystore.com` où vous créez des liens vers des produits. L'ajout de `blog.mystore.com` ici garantit que TikTok peut suivre les utilisateurs du blog vers votre boutique.

#### **Qualité des données et Score de santé**

Cette section fournit des informations sur les performances et la précision de votre suivi TikTok.

- **Score de santé :**

  - **Ce que cela fait :** Affiche un score indiquant la santé globale et la précision de votre transmission de données à TikTok. Un score plus élevé signifie une meilleure qualité des données.
  - **Effet :** Vous aide à identifier rapidement s'il y a des problèmes avec votre configuration de suivi qui pourraient avoir un impact sur les performances des publicités.
  - **Recommandé :** Visez un score élevé. Le module fournira des recommandations si le score est faible.
- **Radar de récupération :**

  - **Ce que cela fait :** Surveille les paniers abandonnés et fournit des informations sur les ventes potentielles perdues, vous aidant à identifier les opportunités de campagnes de reciblage.
  - **Effet :** Vous donne un aperçu rapide du nombre de paniers initiés par rapport aux paniers terminés, mettant en évidence les domaines à améliorer dans votre processus de commande ou votre stratégie de reciblage.
- **Statistiques en direct :**

  - **Ce que cela fait :** Affiche des données en temps réel sur les événements envoyés à TikTok, vous permettant de voir si les événements se déclenchent comme prévu.
  - **Effet :** Fournit un retour immédiat pendant les tests et la surveillance continue, confirmant que votre suivi est actif et précis.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module étend le Back Office de PrestaShop avec plusieurs écrans dédiés pour vous aider à gérer et à surveiller votre intégration TikTok. Ceux-ci sont généralement accessibles depuis la page de configuration du module via des onglets ou des éléments de menu dédiés.

#### **AdminMytiktokAjaxController (Opérations Ajax)**

- **Nom de l'écran et emplacement du menu :** Ce contrôleur gère principalement les requêtes AJAX en arrière-plan depuis la page de configuration du module. Vous ne naviguerez pas directement vers un « écran » pour cela, mais il alimente les mises à jour dynamiques et la récupération de données dans les onglets de configuration du module principal (par exemple, Statistiques en direct, Score de santé, Journaux d'événements).
- **Actions et paramètres disponibles :** Il traite les requêtes pour :
  - Récupération des données d'événements en direct.
  - Mise à jour des scores de santé.
  - Récupération des informations de diagnostic.
  - Enregistrement de parties spécifiques de la configuration sans rechargement complet de la page.
- **Effet des modifications :** Les interactions sur la page de configuration du module principal (comme l'actualisation des statistiques en direct ou l'exécution de diagnostics) déclenchent ce contrôleur pour récupérer et afficher les données pertinentes.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vous interagissez indirectement avec cela en utilisant les divers outils de diagnostic et de surveillance fournis sur la page de configuration du module principal.

#### **index.php (Point d'entrée principal du module)**

- **Nom de l'écran et emplacement du menu :** C'est le point d'entrée principal pour la configuration du module, accessible via **Back Office > Modules > Gestionnaire de modules > Configurer (pour Pixel TikTok / API Événements)**.
- **Actions et paramètres disponibles :** Cet écran présente tous les paramètres généraux et avancés décrits dans la section 4.1, organisés en onglets ou sections logiques. Il héberge également les divers outils de diagnostic comme le Score de santé, les Statistiques en direct et le Radar de récupération.
- **Effet des modifications :** Toute modification enregistrée sur cet écran a un impact direct sur le fonctionnement de votre Pixel TikTok et de l'API Événements sur votre boutique.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. **Configuration initiale :** Configurez votre ID de Pixel, votre jeton d'accès et votre mode de suivi.
  2. **Surveillance régulière :** Vérifiez périodiquement les onglets « Score de santé » et « Statistiques en direct » pour garantir la qualité des données et le déclenchement des événements.
  3. **Dépannage :** Utilisez le « Mode débogage » (temporairement) et les « Statistiques en direct » pour diagnostiquer tout problème de suivi.
  4. **Optimisation :** Examinez les informations du « Radar de récupération » pour éclairer vos stratégies de reciblage.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | ID du Pixel TikTok | Votre ID de Pixel | Lie votre boutique à votre compte publicitaire TikTok pour le suivi par navigateur. |
| Configuration du module | Jeton d'accès TikTok | Votre Jeton d'accès | Autorise le suivi côté serveur via l'API Événements. |
| Configuration du module | Mode de suivi | Mode Dual | Détermine si le Pixel, l'API Événements, ou les deux sont utilisés pour le suivi. Le mode Dual est recommandé pour la précision. |
| Configuration du module | Activer le mode débogage | Non (pour la production) | Affiche des données d'événements détaillées dans la console du navigateur pour le dépannage. |
| Configuration du module | Gestion du consentement | Oui (pour RGPD/CCPA) | Garantit que le suivi respecte le consentement aux cookies de l'utilisateur. |
| Configuration du module | Type d'ID produit | Correspondant à votre catalogue | Sélectionne l'identifiant de produit envoyé à TikTok pour la correspondance du catalogue. |
| Configuration du module | Domaines de liaison | Vide (ajouter si nécessaire) | Permet le suivi inter-domaines pour les structures de site complexes. |
| Configuration du module | Score de santé | Score élevé | Indique la qualité globale des données et la précision du suivi. |
| Configuration du module | Radar de récupération | Surveiller | Informations sur les paniers abandonnés pour le reciblage. |
| Configuration du module | Statistiques en direct | Surveiller | Vue en temps réel des événements envoyés à TikTok. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai installé le module, mais je ne vois aucune donnée dans mon Gestionnaire de publicités TikTok. Que dois-je faire ?**

- **R :** Tout d'abord, vérifiez que votre **ID de Pixel TikTok** et votre **Jeton d'accès** sont correctement saisis dans la configuration du module. Assurez-vous qu'il n'y a pas de fautes de frappe.
- Ensuite, vérifiez que votre **Mode de suivi** est défini sur « Mode Dual » ou « Pixel » (si vous n'utilisez que le Pixel).
- Activez le **Mode débogage** dans les paramètres du module, puis visitez le front office de votre boutique, effectuez quelques actions (comme consulter un produit, ajouter au panier) et vérifiez la console de développement de votre navigateur (généralement F12 > onglet Console) pour les messages d'événements TikTok.
- Enfin, videz votre cache PrestaShop (**Paramètres avancés > Performances > Vider le cache**).

**Q2 : Mon Score de santé TikTok est faible. Comment puis-je l'améliorer ?**

- **R :** Un Score de santé faible indique souvent des problèmes de qualité des données ou de livraison des événements.
- **Vérifiez les données manquantes :** Assurez-vous que toutes les informations produit requises (prix, devise, nom) sont complètes pour vos produits.
- **Vérifiez le consentement :** Si vous avez activé la « Gestion du consentement », assurez-vous que votre bannière de consentement aux cookies fonctionne correctement et que les utilisateurs acceptent les cookies.
- **Examinez les Statistiques en direct :** Recherchez les erreurs ou les événements manquants dans la section « Statistiques en direct » du module.
- Le module lui-même fournit souvent des recommandations spécifiques dans la section Score de santé pour vous guider.

**Q3 : Ce module va-t-il ralentir mon site web ?**

- **R :** Le module est conçu pour être léger et efficace. Le suivi Pixel côté navigateur peut ajouter une petite charge négligeable, similaire à tout autre script d'analyse. L'API Événements côté serveur n'a pratiquement aucun impact sur les temps de chargement du front office car les données sont envoyées directement depuis votre serveur. Nous recommandons d'utiliser le « Mode Dual » pour des performances optimales et une précision des données.

**Q4 : J'ai un thème personnalisé. Le module fonctionnera-t-il correctement ?**

- **R :** Oui, le module est conçu pour s'intégrer de manière transparente aux thèmes PrestaShop standard et à la plupart des thèmes personnalisés. Il utilise le système de hooks officiel de PrestaShop pour injecter ses scripts et son code de suivi.
- Si vous rencontrez des problèmes avec un thème très personnalisé, surtout s'il modifie considérablement les modèles PrestaShop de base pour les pages de produits ou la commande, vous devrez peut-être consulter un développeur pour vous assurer que les hooks sont toujours présents et correctement rendus.

**Q5 : Comment le module gère-t-il les boutiques multilingues et multidevises ?**

- **R :** Le module est conçu pour être entièrement compatible avec les fonctionnalités multilingues et multidevises de PrestaShop. Il détecte automatiquement la langue et la devise actives sur le front office et envoie ces informations à TikTok, garantissant que vos données d'événements sont précises et localisées. Les noms et valeurs des produits seront envoyés dans le contexte de la langue et de la devise sélectionnées par le client.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de la structure technique du module Pixel TikTok / API Événements, destinée aux développeurs, webmasters et agences techniques.

### 4.1 Vue d'ensemble de l'architecture

Le module `mytiktok` suit une architecture de module PrestaShop standard, tirant parti du modèle MVC le cas échéant. Il fonctionne principalement comme un traqueur d'événements, injectant du JavaScript pour le suivi côté client (Pixel) et utilisant une logique côté serveur pour l'API Événements. Les composants clés comprennent :

- **Classe de module principale (`index.php`) :** Gère l'installation, la désinstallation, la configuration et l'enregistrement des hooks.
- **Contrôleurs :** Contrôleurs frontaux pour les requêtes AJAX et contrôleurs d'administration pour la gestion du back-office.
- **Classes principales :** Un ensemble robuste de classes (`classes/`) pour gérer la communication API, le mappage d'événements, la qualité des données, le consentement et diverses stratégies de suivi (Pixel, CAPI, Hybride).
- **Templates :** Templates Smarty pour l'injection de hooks côté front-office et les vues de configuration côté back-office.
- **Assets :** JS et CSS dédiés pour les interfaces d'administration et le débogage/suivi côté front-office.

Le module implémente une `MytiktokTrackerInterface` et utilise une `MytiktokTrackerFactory` pour abstraire les différents modes de suivi (Pixel, CAPI, Hybride), favorisant une conception propre et extensible. Il comprend également des outils sophistiqués de qualité des données et de surveillance de la santé.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `mytiktok/controllers/front/ajax.php`
  - **Nom de la classe et classe parente :** `MytiktokAjaxModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Gère les requêtes asynchrones du front-office, principalement pour le suivi d'événements côté serveur (API Événements) ou la collecte de données qui ne nécessite pas un rechargement complet de la page. Il peut traiter les données soumises par JavaScript et les transmettre à l'API Événements TikTok.
- `mytiktok/controllers/front/index.php`
  - **Nom de la classe et classe parente :** `MytiktokIndexModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur peut servir de solution de repli ou de point d'extrémité spécifique pour certaines interactions du front-office, bien que `ajax.php` soit généralement plus actif pour la gestion des événements. Il pourrait être utilisé pour des redirections ou des initialisations spécifiques si nécessaire.

#### Contrôleurs d'administration Back-Office

- `mytiktok/controllers/admin/AdminMytiktokAjaxController.php`
  - **Nom de la classe et classe parente :** `AdminMytiktokAjaxController` étend `ModuleAdminController`.
  - **Nom de l'onglet et entité gérée :** Ce contrôleur n'est pas directement accessible en tant qu'onglet de menu. Il gère les requêtes AJAX provenant de la page de configuration principale du module (`index.php`) dans le back office. Il est responsable des mises à jour dynamiques, de la récupération des statistiques en direct, des scores de santé, des journaux d'événements et d'autres données de diagnostic sans nécessiter un rafraîchissement complet de la page.
- `mytiktok/controllers/admin/index.php`
  - **Nom de la classe et classe parente :** `AdminMytiktokController` étend `ModuleAdminController`.
  - **Nom de l'onglet et entité gérée :** C'est le contrôleur d'administration principal pour la configuration du module. C'est le contrôleur vers lequel `index.php` (le fichier de module principal) se dirige lorsque le bouton « Configurer » est cliqué. Il gère l'affichage de tous les formulaires de configuration, des onglets (par exemple, Paramètres généraux, Qualité des données, Statistiques en direct) et gère l'enregistrement des paramètres du module.

### 4.3 Classes et modèles principaux (`classes/`)

- `mytiktok/classes/autoload.php` : Fichier d'autoload PrestaShop standard, garantissant que les classes du module sont chargées correctement.
- `mytiktok/classes/index.php` : Fichier vide, souvent utilisé pour empêcher la liste des répertoires.
- `mytiktok/classes/MytiktokCapiClient.php` :
  - **Table de base de données :** Aucune directement.
  - **Étend ObjectModel :** Non.
  - **Méthodes publiques clés :** Gère la communication avec l'API Événements TikTok (CAPI). Contient des méthodes pour envoyer des données d'événements, gérer l'authentification avec le jeton d'accès et gérer les réponses de l'API.
- `mytiktok/classes/MytiktokCapiTracker.php` :
  - **Table de base de données :** Aucune directement.
  - **Étend ObjectModel :** Non.
  - **Méthodes publiques clés :** Implémente `MytiktokTrackerInterface`. Responsable de la préparation et de l'envoi des événements côté serveur à TikTok via `MytiktokCapiClient`.
- `mytiktok/classes/MytiktokCatalogDoctor.php` :
  - **Table de base de données :** Aucune directement.
  - **Étend ObjectModel :** Non.
  - **Méthodes publiques clés :** Fournit des outils de diagnostic et des recommandations liés aux données du catalogue de produits, garantissant que les ID de produits et les attributs sont correctement formatés pour TikTok.
- `mytiktok/classes/MytiktokConsent.php` :
  - **Table de base de données :** Aucune directement.
  - **Étend ObjectModel :** Non.
  - **Méthodes publiques clés :** Gère la logique de consentement aux cookies, s'intégrant aux mécanismes de consentement de PrestaShop ou aux modules de consentement personnalisés pour garantir la conformité RGPD/CCPA.
- `mytiktok/classes/MytiktokCurrencyHelper.php` :
  - **Table de base de données :** Aucune directement.
  - **Étend ObjectModel :** Non.
  - **Méthodes publiques clés :** Classe utilitaire pour gérer le formatage et les conversions de devises, garantissant que les valeurs d'événements sont envoyées à TikTok dans le format et la devise corrects.
- `mytiktok/classes/MytiktokDataQualityCoach.php` :
  - **Table de base de données :** Aucune directement.
  - **Étend ObjectModel :** Non.
  - **Méthodes publiques clés :** Analyse la qualité et l'exhaustivité des données envoyées à TikTok, fournissant des informations et des suggestions d'amélioration.
- `mytiktok/classes/MytiktokEventId.php` :
  - **Table de base de données :** Aucune directement.
  - **Étend ObjectModel :** Non.
  - **Méthodes publiques clés :** Génère et gère des valeurs `event_id` uniques pour les événements, cruciales pour la déduplication dans le suivi en mode dual.
- `mytiktok/classes/MytiktokEventMap.php` :
  - **Table de base de données :** Aucune directement.
  - **Étend ObjectModel :** Non.
  - **Méthodes publiques clés :** Mappe les actions et les données de PrestaShop aux noms et propriétés d'événements TikTok standard (par exemple, `ViewContent`, `AddToCart`, `CompletePayment`).
- `mytiktok/classes/MytiktokEvents.php` :
  - **Table de base de données :** Aucune directement.
  - **Étend ObjectModel :** Non.
  - **Méthodes publiques clés :** Classe centrale pour déclencher et gérer divers événements TikTok basés sur les actions de l'utilisateur dans PrestaShop.
- `mytiktok/classes/MytiktokHealthScore.php` :
  - **Table de base de données :** Aucune directement.
  - **Étend ObjectModel :** Non.
  - **Méthodes publiques clés :** Calcule et affiche le score de santé global de l'intégration TikTok basé sur la qualité des données, la livraison des événements et la configuration.
- `mytiktok/classes/MytiktokHybridTracker.php` :
  - **Table de base de données :** Aucune directement.
  - **Étend ObjectModel :** Non.
  - **Méthodes publiques clés :** Implémente `MytiktokTrackerInterface`. Orchestre le suivi en mode dual, envoyant des événements via le Pixel et la CAPI avec déduplication de l'`event_id`.
- `mytiktok/classes/MytiktokLiveStats.php` :
  - **Table de base de données :** Aucune directement.
  - **Étend ObjectModel :** Non.
  - **Méthodes publiques clés :** Collecte et affiche des statistiques en temps réel des événements envoyés à TikTok à des fins de surveillance.
- `mytiktok/classes/MytiktokPixelTracker.php` :
  - **Table de base de données :** Aucune directement.
  - **Étend ObjectModel :** Non.
  - **Méthodes publiques clés :** Implémente `MytiktokTrackerInterface`. Responsable de l'injection et de la gestion des événements du Pixel TikTok côté navigateur.
- `mytiktok/classes/MytiktokProductIdResolver.php` :
  - **Table de base de données :** Aucune directement.
  - **Étend ObjectModel :** Non.
  - **Méthodes publiques clés :** Résout l'ID de produit correct en fonction de la configuration du module (par exemple, ID PrestaShop, EAN13, UPC) pour l'envoi à TikTok.
- `mytiktok/classes/MytiktokPropertyRules.php` :
  - **Table de base de données :** Aucune directement.
  - **Étend ObjectModel :** Non.
  - **Méthodes publiques clés :** Définit et applique les règles pour les propriétés d'événements, garantissant que les données envoyées à TikTok respectent ses spécifications.
- `mytiktok/classes/MytiktokTrackerFactory.php` :
  - **Table de base de données :** Aucune directement.
  - **Étend ObjectModel :** Non.
  - **Méthodes publiques clés :** Modèle de fabrique pour instancier la classe de traqueur correcte (`MytiktokPixelTracker`, `MytiktokCapiTracker` ou `MytiktokHybridTracker`) en fonction de la configuration du « Mode de suivi » du module.
- `mytiktok/classes/MytiktokTrackerInterface.php` :
  - **Table de base de données :** Aucune directement.
  - **Étend ObjectModel :** Non.
  - **Méthodes publiques clés :** Définit le contrat pour toutes les classes de traqueurs, garantissant une interface cohérente pour l'envoi d'événements.
- `mytiktok/classes/MytiktokTrans.php` :
  - **Table de base de données :** Aucune directement.
  - **Étend ObjectModel :** Non.
  - **Méthodes publiques clés :** Classe utilitaire pour gérer les traductions du module.
- `mytiktok/classes/MytiktokUserData.php` :
  - **Table de base de données :** Aucune directement.
  - **Étend ObjectModel :** Non.
  - **Méthodes publiques clés :** Collecte et formate les données utilisateur (par exemple, e-mail, téléphone, adresse IP) pour une correspondance améliorée dans l'API Événements TikTok.

### 4.4 Assets JavaScript (`views/js/`)

- `mytiktok/views/js/mytiktok-admin.js` :
  - **Portée :** Back-office.
  - **Description :** Gère les éléments interactifs et les appels AJAX dans les pages d'administration du module. Cela inclut la gestion des onglets, la mise à jour des statistiques en direct, la gestion des soumissions de formulaires et des étapes de l'assistant.
- `mytiktok/views/js/mytiktok-debug.js` :
  - **Portée :** Front-office (lorsque le mode débogage est activé).
  - **Description :** Injecte des informations de débogage dans la console du navigateur, enregistrant les événements TikTok, leurs propriétés et les problèmes potentiels. Essentiel pour vérifier le déclenchement correct des événements.
- `mytiktok/views/js/mytiktok-ghost.js` :
  - **Portée :** Front-office.
  - **Description :** Gère potentiellement des mécanismes de suivi « fantômes » ou cachés, éventuellement liés à l'initiation d'événements côté serveur ou à des interactions utilisateur spécifiques qui doivent être capturées sans interaction directe avec le pixel.
- `mytiktok/views/js/mytiktok-live.js` :
  - **Portée :** Back-office.
  - **Description :** Alimente la fonctionnalité « Statistiques en direct » dans le panneau d'administration, récupérant et affichant périodiquement les données d'événements en temps réel.
- `mytiktok/views/js/mytiktok-tcf.js` :
  - **Portée :** Front-office.
  - **Description :** S'intègre au Cadre de Transparence et de Consentement (TCF) ou à d'autres solutions de consentement aux cookies pour gérer le consentement de l'utilisateur avant d'initialiser le Pixel TikTok.
- `mytiktok/views/js/mytiktok-wizard.js` :
  - **Portée :** Back-office.
  - **Description :** Gère l'assistant de configuration étape par étape pour la configuration initiale du module, guidant le marchand à travers les paramètres essentiels.
- `mytiktok/views/js/mytiktok.js` :
  - **Portée :** Front-office.
  - **Description :** Le fichier JavaScript principal du front-office. Il initialise le Pixel TikTok, déclenche les événements standard (PageView, ViewContent, AddToCart, InitiateCheckout) et collecte les données nécessaires du DOM pour les envoyer à TikTok. Il gère également la génération de l'`event_id` pour la déduplication.

### 4.5 Feuilles de style CSS (`views/css/`)

- `mytiktok/views/css/mytiktok-admin.css` :
  - **Portée :** Style du formulaire d'administration du back-office.
  - **Description :** Style la page de configuration du module, y compris les onglets, les champs de saisie, les boutons et les affichages de diagnostic (Score de santé, Statistiques en direct, etc.) pour garantir une interface cohérente et conviviale dans le back office de PrestaShop.
- `mytiktok/views/css/mytiktok-debug.css` :
  - **Portée :** Style client du front-office (uniquement lorsque le mode débogage est actif).
  - **Description :** Fournit un style minimal pour tout élément de débogage visuel qui pourrait apparaître sur le front office lorsque le mode débogage est activé (par exemple, une petite superposition ou une bannière indiquant l'état du débogage).

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

- `mytiktok/views/templates/hook/capi-pageview.tpl` :
  - **Hook :** Potentiellement `displayHeader` ou `displayBeforeBodyClosingTag`.
  - **Sortie :** Rend l'événement `PageView` côté serveur pour l'API Événements. Ce template peut contenir des champs cachés ou des structures de données utilisées par la logique côté serveur pour initier l'événement CAPI PageView.
- `mytiktok/views/templates/hook/debug.tpl` :
  - **Hook :** `displayHeader` ou `displayBeforeBodyClosingTag`.
  - **Sortie :** Rend un petit bloc HTML ou une balise de script à des fins de débogage, incluant souvent `mytiktok-debug.js` et les données de débogage initiales.
- `mytiktok/views/templates/hook/displayOrderConfirmation.tpl` :
  - **Hook :** `displayOrderConfirmation`.
  - **Sortie :** Rend les données de l'événement `CompletePayment`, y compris la valeur de la commande, la devise et les détails du produit, à envoyer au Pixel TikTok et/ou à l'API Événements après un achat réussi.
- `mytiktok/views/templates/hook/ghost.tpl` :
  - **Hook :** Divers hooks du front-office.
  - **Sortie :** Rend des éléments ou des scripts cachés pour le suivi « fantôme », potentiellement liés aux déclencheurs d'événements côté serveur ou à la collecte de données avancées.
- `mytiktok/views/templates/hook/header.tpl` :
  - **Hook :** `displayHeader`.
  - **Sortie :** Injecte le code de base principal du Pixel TikTok, `mytiktok.js`, et les variables de configuration initiales dans la section `<head>` de toutes les pages du front-office. C'est là que le Pixel est initialisé.
- `mytiktok/views/templates/hook/payment.tpl` :
  - **Hook :** Potentiellement `displayPaymentTop` ou `displayPaymentOptions`.
  - **Sortie :** Peut rendre les données de l'événement `InitiateCheckout` ou des scripts connexes lorsqu'un client atteint l'étape de sélection du paiement pendant la commande.
- `mytiktok/views/templates/hook/product-details.tpl` :
  - **Hook :** `displayProductAdditionalInfo` ou un hook de page produit similaire.
  - **Sortie :** Rend les données de l'événement `ViewContent`, y compris l'ID du produit, le nom, le prix et la catégorie, pour le produit actuellement consulté.

#### Templates d'administration (`views/templates/admin/`)

- `mytiktok/views/templates/admin/consent-guide.tpl` : Affiche des conseils sur la configuration du consentement aux cookies.
- `mytiktok/views/templates/admin/doctor.tpl` : Rend l'interface de diagnostic « Docteur du catalogue ».
- `mytiktok/views/templates/admin/dq.tpl` : Affiche des informations et des recommandations sur la qualité des données.
- `mytiktok/views/templates/admin/health.tpl` : Rend le tableau de bord « Score de santé ».
- `mytiktok/views/templates/admin/linker-domains.tpl` : Champ de formulaire pour la configuration des domaines de liaison.
- `mytiktok/views/templates/admin/live-maintain.tpl` : Espace réservé ou vue de maintenance pour les statistiques en direct.
- `mytiktok/views/templates/admin/live.tpl` : Affiche le tableau de bord « Statistiques en direct ».
- `mytiktok/views/templates/admin/mode-context.tpl` : Informations contextuelles sur le mode de suivi sélectionné.
- `mytiktok/views/templates/admin/mode-note-both.tpl` : Note/explication pour le suivi en « Mode Dual ».
- `mytiktok/views/templates/admin/mode-note-capi.tpl` : Note/explication pour le suivi « API Événements uniquement ».
- `mytiktok/views/templates/admin/mode-note-pixel.tpl` : Note/explication pour le suivi « Pixel uniquement ».
- `mytiktok/views/templates/admin/mode-picker.tpl` : L'interface pour sélectionner le mode de suivi (Pixel, CAPI, Dual).
- `mytiktok/views/templates/admin/properties-list.tpl` : Affiche une liste des propriétés d'événements.
- `mytiktok/views/templates/admin/recent-events.tpl` : Affiche un journal des événements récents envoyés.
- `mytiktok/views/templates/admin/tabs.tpl` : Structure pour l'interface à onglets sur la page de configuration du module.
- `mytiktok/views/templates/admin/tag-chips.tpl` : Composants visuels pour l'affichage des balises ou des ID.
- `mytiktok/views/templates/admin/tag-ids.tpl` : Champs de saisie pour l'ID du Pixel TikTok et le Jeton d'accès.
- `mytiktok/views/templates/admin/wizard.tpl` : L'interface de l'assistant de configuration étape par étape.

#### Templates Front-office (`views/templates/front/`)

- Aucun template de page autonome dédié n'est listé, car le module injecte principalement des scripts et des données via des hooks.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de base de données

Le module stocke principalement ses paramètres de configuration dans la table `ps_configuration` de PrestaShop.

- `ps_configuration` : Stocke les paires clé-valeur pour les paramètres du module, tels que `MYTIKTOK_PIXEL_ID`, `MYTIKTOK_ACCESS_TOKEN`, `MYTIKTOK_TRACKING_MODE`, etc.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Initialise le code de base du Pixel TikTok, charge `mytiktok.js` et configure les variables de configuration globales. |
| `displayBeforeBodyClosingTag` | Juste avant la balise `</body>`. | Peut injecter des scripts ou des données supplémentaires qui doivent être exécutés après le chargement du DOM, ou pour les événements CAPI PageView. |
| `displayProductAdditionalInfo` | Sur la page produit, généralement près des détails du produit. | Déclenche l'événement `ViewContent`, transmettant les données spécifiques au produit à TikTok. |
| `displayShoppingCartFooter` | Sur la page du panier, généralement sous le résumé du panier. | Déclenche l'événement `AddToCart` (s'il n'est pas déjà géré par AJAX) et potentiellement `InitiateCheckout`. |
| `displayPaymentTop` | En haut de la page de sélection du paiement pendant la commande. | Déclenche l'événement `InitiateCheckout`. |
| `displayOrderConfirmation` | Sur la page de confirmation de commande après un achat réussi. | Déclenche l'événement crucial `CompletePayment`, envoyant les détails complets de la commande (valeur, produits, devise) à TikTok. |
| `actionFrontControllerSetMedia` | Lorsqu'un contrôleur frontal définit ses assets média. | Injecte les fichiers JS/CSS spécifiques au module dans le front office. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration définit ses assets média. | Injecte les fichiers JS/CSS spécifiques au module dans le back office. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | Déclencheur côté serveur pour l'événement `CompletePayment` via l'API Événements, garantissant un suivi fiable des conversions. |
| `actionCartSave` | Lorsque le panier est mis à jour (par exemple, ajout/suppression de produit). | Déclencheur côté serveur pour les événements `AddToCart` ou `RemoveFromCart` via l'API Événements. |
| `actionProductUpdate` | Lorsqu'un produit est mis à jour dans le back office. | Potentiellement utilisé pour la synchronisation du catalogue ou les vérifications de la qualité des données. |
| `actionObjectProductAddAfter` | Après l'ajout d'un nouveau produit. | Potentiellement utilisé pour la synchronisation du catalogue ou les vérifications de la qualité des données. |
| `actionObjectProductUpdateAfter` | Après la mise à jour d'un produit. | Potentiellement utilisé pour la synchronisation du catalogue ou les vérifications de la qualité des données. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Pixel TikTok / API Événements », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support dédiée est disponible pour vous aider avec tout problème technique ou question concernant la fonctionnalité du module.
