---
title: "Amazon Ads Tag Conversions API - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Amazon Ads Tag Conversions API par MyPresta.eu."
sidebar:
  label: "Amazon Ads Tag Conversions API - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Amazon Ads Tag Conversions API sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/amazon-ads-tag-conversions-api.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/amazon-ads-tag-conversions-api/)
>
> ---


# Amazon Ads Tag Conversions API

## 1. Exigences et Compatibilité

- **Versions PrestaShop Supportées** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'Hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises pour que le module fonctionne correctement, en particulier pour l'API de Conversions (CAPI) qui repose sur une communication sécurisée de serveur à serveur. Votre environnement d'hébergement doit également autoriser les connexions sortantes vers les points d'accès de l'API d'Amazon.

## 2. Guide de Configuration Complet (Chaque Paramètre Groupé par Écran)

Cette section vous guide à travers chaque paramètre du module « Amazon Ads Tag Conversions API ».

### 2.1 Page de Configuration du Module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal où vous configurerez votre suivi Amazon Ads.

**Accès :** Naviguez vers **Modules > Gestionnaire de modules**, puis trouvez « Amazon Ads Tag Conversions API » et cliquez sur **Configurer**.

#### **Sélection du Mode de Suivi**

Cette section détermine comment votre boutique envoie des données à Amazon.

- **Ce que fait ce paramètre :** Vous permet de choisir entre trois méthodes principales pour envoyer des données de conversion à Amazon : Amazon Ads Tag (côté client), Conversions API (côté serveur), ou une combinaison des deux.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur « Amazon Ads Tag (Côté Client) » :* Le module s'appuiera principalement sur le tag JavaScript placé dans le navigateur du client pour envoyer des données. Ceci est susceptible d'être bloqué par les bloqueurs de publicité.
  - *Lorsqu'il est défini sur « Conversions API (Côté Serveur) » :* Le module enverra des données directement de votre serveur PrestaShop aux serveurs d'Amazon. C'est plus fiable et contourne les bloqueurs de publicité.
  - *Lorsqu'il est défini sur « Mode Dual (Hybride) » :* Le module enverra des données en utilisant à la fois l'Amazon Ads Tag et l'API de Conversions. Cela offre une résilience et une précision maximales des données.
- **Valeur recommandée :** **« Mode Dual (Hybride) »** pour le suivi le plus robuste et le plus précis. Si vous êtes très préoccupé par la confidentialité et souhaitez minimiser les scripts côté client, « Conversions API (Côté Serveur) » est une alternative solide.
- **Scénario / exemple de marchand :** Si vous avez remarqué une divergence entre les conversions rapportées par vos Amazon Ads et vos ventes réelles sur PrestaShop, passer en « Mode Dual » ou « Conversions API » peut améliorer considérablement la précision en récupérant les conversions perdues à cause des bloqueurs de publicité.

#### **ID du Tag Amazon Ads**

- **Ce que fait ce paramètre :** C'est votre identifiant unique fourni par Amazon Ads pour votre tag de suivi. Il indique à Amazon à quel compte attribuer les données de conversion.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'un ID valide est saisi :* L'Amazon Ads Tag (s'il est activé dans votre mode de suivi) enverra correctement les données à votre compte Amazon Ads.
  - *Lorsqu'il est laissé vide ou qu'un ID invalide est saisi :* Le suivi côté client ne fonctionnera pas, et les données ne seront pas envoyées à votre compte Amazon Ads via le tag.
- **Valeur recommandée :** Votre ID de Tag Amazon Ads spécifique. Vous pouvez le trouver dans votre compte Amazon Ads sous « Gestionnaire d'événements » ou « Audiences ».
- **Scénario / exemple de marchand :** Vous venez de configurer une nouvelle campagne Amazon Ads. Saisir l'ID de Tag correct ici est la première étape pour garantir le suivi des performances de votre campagne.

#### **Jeton d'Accès à l'API de Conversions Amazon**

- **Ce que fait ce paramètre :** C'est un jeton sécurisé fourni par Amazon Ads qui authentifie votre serveur lors de l'envoi de données via l'API de Conversions. Il garantit que seules les sources autorisées peuvent envoyer des données à votre compte Amazon Ads.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'un jeton valide est saisi :* Votre serveur PrestaShop peut envoyer en toute sécurité des données de conversion directement à Amazon via l'API de Conversions (si activé dans votre mode de suivi).
  - *Lorsqu'il est laissé vide ou qu'un jeton invalide est saisi :* Le suivi côté serveur via l'API de Conversions ne fonctionnera pas, et les données ne seront pas envoyées à votre compte Amazon Ads via CAPI.
- **Valeur recommandée :** Votre Jeton d'Accès à l'API de Conversions Amazon spécifique. Celui-ci est généré dans votre compte Amazon Ads, généralement sous « Gestionnaire d'événements » ou « Sources de données ». Traitez ce jeton comme un mot de passe ; gardez-le sécurisé.
- **Scénario / exemple de marchand :** Vous souhaitez améliorer la fiabilité de votre suivi des conversions en utilisant l'API de Conversions. Après avoir généré le jeton dans Amazon Ads, collez-le ici pour activer la transmission de données côté serveur.

#### **Activer le Mode Débogage**

- **Ce que fait ce paramètre :** Active un mode spécial qui affiche des informations détaillées sur les données envoyées à Amazon, visibles uniquement par vous (ou toute personne ayant les outils de développement ouverts) dans la console du navigateur. C'est inestimable pour le dépannage.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Vous verrez des journaux de console et potentiellement des superpositions à l'écran (selon l'implémentation spécifique du débogage) montrant quels événements sont déclenchés et quelles données sont envoyées à Amazon. Ce n'est pas visible pour les clients réguliers.
  - *Lorsqu'il est désactivé :* Aucune information de débogage ne sera affichée.
- **Valeur recommandée :** **« NON »** pour les boutiques de production en direct. N'activez temporairement que lors de la configuration ou du dépannage.
- **Scénario / exemple de marchand :** Vous avez configuré le module, mais les conversions n'apparaissent pas dans votre compte Amazon Ads. L'activation du mode débogage peut vous aider à voir si les événements se déclenchent correctement sur votre site web et si la charge utile des données semble précise.

#### **Intégration de la Gestion du Consentement**

- **Ce que fait ce paramètre :** Permet au module de s'intégrer à la solution de consentement aux cookies de votre boutique. Cela garantit que le suivi Amazon Ads ne s'active qu'après qu'un client a donné son consentement explicite, se conformant aux réglementations de confidentialité comme le GDPR ou le CCPA.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé et intégré à un module de consentement :* L'Amazon Ads Tag (côté client) ne se chargera et ne déclenchera des événements que si le client a accepté les cookies de suivi. Le CAPI côté serveur peut toujours envoyer des données anonymisées ou attendre le consentement en fonction de votre configuration spécifique et de vos politiques de confidentialité.
  - *Lorsqu'il est désactivé :* Le module tentera de suivre les événements sans vérification explicite du consentement, ce qui pourrait ne pas être conforme aux lois sur la confidentialité dans certaines régions.
- **Valeur recommandée :** **« OUI »** si votre boutique opère dans des régions avec des lois de confidentialité strictes (par exemple, UE, Californie) et que vous utilisez un module de consentement aux cookies.
- **Scénario / exemple de marchand :** Votre boutique sert des clients en Europe et vous utilisez une bannière de cookies conforme au GDPR. L'activation de ce paramètre garantit que votre suivi Amazon Ads respecte les choix de confidentialité des clients.

#### **Paramètres Avancés (par exemple, Couche de Données, Mappage d'Événements, Résolution d'ID Produit)**

Le module peut inclure des paramètres avancés qui permettent un réglage fin de la collecte et de la transmission des données. Ceux-ci sont généralement destinés aux utilisateurs plus techniques ou à des scénarios spécifiques.

- **Suivi de la Couche de Données :**
  - **Ce que fait ce paramètre :** Détermine si le module doit utiliser une « couche de données » standardisée pour collecter des informations de votre boutique. Ceci est souvent utilisé pour la compatibilité avec d'autres outils de suivi ou des implémentations personnalisées.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module recherchera et poussera des données vers un objet JavaScript `dataLayer`, ce qui peut être utile pour le débogage ou l'intégration avec Google Tag Manager.
    - *Lorsqu'il est désactivé :* Le module collectera les données directement à partir des variables internes de PrestaShop.
  - **Valeur recommandée :** **« OUI »** si vous utilisez Google Tag Manager ou d'autres outils qui dépendent d'une couche de données. Sinon, « NON » est généralement suffisant.
- **Mappage d'Événements :**
  - **Ce que fait ce paramètre :** Vous permet de personnaliser la façon dont des actions PrestaShop spécifiques (par exemple, « ajouter au panier ») sont mappées aux noms d'événements Amazon Ads.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est personnalisé :* Vous pouvez envoyer des noms d'événements différents à Amazon que ceux par défaut du module, ce qui peut être utile pour des configurations de campagne Amazon Ads spécifiques.
    - *Lorsqu'il est par défaut :* Le module utilise son mappage prédéfini.
  - **Valeur recommandée :** Laissez par défaut, sauf si vous avez une raison spécifique de le modifier en fonction de la documentation Amazon Ads.
- **Résolution d'ID Produit :**
  - **Ce que fait ce paramètre :** Définit quel identifiant de produit (par exemple, ID Produit, EAN, UPC, SKU) le module doit envoyer à Amazon pour les événements liés aux produits.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur ID Produit :* Amazon recevra l'ID de produit interne de PrestaShop.
    - *Lorsqu'il est défini sur EAN/UPC/SKU :* Amazon recevra l'identifiant de produit correspondant. Ceci est crucial pour faire correspondre les produits dans votre catalogue de produits Amazon.
  - **Valeur recommandée :** Choisissez l'identifiant qui correspond le plus systématiquement aux ID de produit que vous utilisez dans vos flux de produits ou votre catalogue Amazon. **EAN/UPC** est souvent préféré pour les produits de détail.
- **Domaines de Liaison :**
  - **Ce que fait ce paramètre :** Spécifie les domaines supplémentaires qui doivent être inclus dans le suivi inter-domaines. Ceci est important si votre processus de paiement ou d'autres parties de votre parcours client impliquent plusieurs domaines (par exemple, un sous-domaine séparé pour un blog ou une passerelle de paiement qui redirige).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est configuré :* L'Amazon Ads Tag peut maintenir la continuité du suivi sur différents domaines, évitant la perte d'attribution.
    - *Lorsqu'il n'est pas configuré pour plusieurs domaines :* Les conversions pourraient être mal attribuées ou perdues si le client navigue entre les domaines pendant son parcours.
  - **Valeur recommandée :** Ajoutez tous les domaines ou sous-domaines qui font partie du parcours de votre client.
- **Assistant de Devise :**
  - **Ce que fait ce paramètre :** Garantit que les valeurs de devise envoyées à Amazon sont correctement formatées et correspondent à la devise utilisée dans votre compte Amazon Ads.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est correctement configuré :* Amazon reçoit des valeurs de devise précises.
    - *Lorsqu'il est mal configuré :* Les valeurs de devise pourraient être mal interprétées par Amazon, entraînant des rapports incorrects.
  - **Valeur recommandée :** Assurez-vous que cela correspond à la devise principale de votre boutique et à la devise de votre compte Amazon Ads.

### 2.2 Écrans d'Administration Dédiés et Vues de Contrôleur

Le module fournit plusieurs écrans dédiés pour vous aider à surveiller et à optimiser votre suivi Amazon Ads. Ceux-ci sont généralement accessibles via des onglets ou des sous-sections dans la configuration principale du module.

#### **4.2.1 Statistiques en Direct**

- **Nom de l'écran et Emplacement du Menu :** Généralement un onglet dans la configuration principale du module (par exemple, « Statistiques en Direct »).
- **Actions et Paramètres Disponibles :** Cet écran affiche des données en temps réel ou quasi-réel sur les événements envoyés à Amazon. Il peut afficher :
  - Les événements récents (par exemple, PageView, AddToCart, Purchase) avec des horodatages.
  - Les types d'événements et leur fréquence.
  - Les scores de qualité des données.
  - Des visualisations de l'activité de suivi.
- **Effet des modifications :** Il s'agit d'un écran de rapport ; il n'y a pas de paramètres directs à modifier ici. Il reflète les données envoyées en fonction de votre configuration principale.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vérifiez régulièrement cet écran pour vous assurer que les événements se déclenchent comme prévu, surtout après avoir apporté des modifications à votre boutique ou lancé de nouvelles campagnes. C'est votre première ligne de défense pour identifier les problèmes de suivi.

#### **4.2.2 Score de Santé et Radar de Récupération**

- **Nom de l'écran et Emplacement du Menu :** Souvent un onglet dans la configuration principale du module (par exemple, « Score de Santé » ou « Diagnostics »).
- **Actions et Paramètres Disponibles :** Cette section fournit un score de santé global pour votre suivi Amazon Ads et identifie les problèmes potentiels ou les conversions « perdues ». Elle peut inclure :
  - Un score en pourcentage indiquant la santé du suivi.
  - Des recommandations pour améliorer la qualité des données.
  - Un « Radar de Récupération » montrant les conversions estimées qui auraient pu être manquées en raison de bloqueurs de publicité ou d'autres problèmes, et comment CAPI aide à les récupérer.
  - Des avertissements concernant les ID de Tag manquants, les Jetons d'Accès ou les problèmes de consentement.
- **Effet des modifications :** Comme les Statistiques en Direct, il s'agit principalement d'un écran de rapport et de diagnostic. Les actions que vous entreprenez en fonction de ses recommandations (par exemple, la mise à jour d'un ID de Tag manquant) amélioreront votre suivi.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Examinez périodiquement votre Score de Santé. Un score faible ou un « Radar de Récupération » actif indique des domaines où votre suivi pourrait être amélioré, ce qui pourrait conduire à de meilleures performances publicitaires.

#### **4.2.3 Coach de Qualité des Données / Docteur de Catalogue**

- **Nom de l'écran et Emplacement du Menu :** Potentiellement un onglet dans la configuration principale du module (par exemple, « Qualité des Données » ou « Docteur de Catalogue »).
- **Actions et Paramètres Disponibles :** Ces outils vous aident à vous assurer que les données que vous envoyez à Amazon sont de haute qualité et correctement formatées. Ils peuvent :
  - Vérifier les problèmes de données courants (par exemple, ID de produit manquants, formats de devise incorrects).
  - Fournir des suggestions pour améliorer les données de votre catalogue de produits afin de mieux correspondre aux exigences d'Amazon.
  - Mettre en évidence les divergences entre les données côté client et côté serveur.
- **Effet des modifications :** Cet écran fournit des informations exploitables. La résolution des problèmes mis en évidence ici (par exemple, la mise à jour des EAN de produits dans votre catalogue PrestaShop) améliorera directement la qualité et les capacités de correspondance de vos données de conversion dans Amazon Ads.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Si vous rencontrez des problèmes de correspondance de produits dans Amazon Ads ou si vous voyez des avertissements dans votre Score de Santé, consultez ces outils pour affiner vos données.

### 2.3 Tableau de Référence Rapide de la Configuration

| Écran / Vue | Paramètre / Option | Valeur par Défaut / Recommandée | Objectif et Impact |
| --- | --- | --- | --- |
| Config Principale | **Mode de Suivi** | Mode Dual (Hybride) | Détermine si le suivi est côté client, côté serveur, ou les deux. Le Mode Dual offre une résilience maximale. |
| Config Principale | **ID du Tag Amazon Ads** | Votre ID de Tag Amazon | Essentiel pour le suivi côté client. Lie les données à votre compte Amazon Ads. |
| Config Principale | **Jeton d'Accès à l'API de Conversions Amazon** | Votre Jeton d'Accès CAPI | Essentiel pour le suivi côté serveur. Authentifie votre serveur auprès d'Amazon. |
| Config Principale | **Activer le Mode Débogage** | NON | Affiche les données de suivi dans la console du navigateur pour le dépannage. Désactiver sur les boutiques en direct. |
| Config Principale | **Intégration de la Gestion du Consentement** | OUI (si applicable) | Garantit que le suivi respecte la confidentialité des clients et le consentement aux cookies. |
| Config Principale | **Suivi de la Couche de Données** | OUI (si utilisation de GTM) | Utilise une couche de données pour la collecte d'événements, utile pour GTM ou les intégrations personnalisées. |
| Config Principale | **Résolution d'ID Produit** | EAN/UPC | Définit quel identifiant de produit est envoyé à Amazon pour la correspondance. Crucial pour la correspondance du catalogue. |
| Config Principale | **Domaines de Liaison** | Vide (ajouter si nécessaire) | Maintient le suivi sur plusieurs domaines dans le parcours client. |
| Statistiques en Direct | (Rapport Uniquement) | N/A | Affiche les données d'événements en temps réel, vous aidant à vérifier que le suivi est actif. |
| Score de Santé | (Rapport Uniquement) | N/A | Fournit une évaluation globale de la santé de votre suivi et identifie les problèmes. |
| Qualité des Données | (Rapport Uniquement) | N/A | Aide à identifier et à corriger les problèmes de qualité des données dans votre catalogue de produits pour une meilleure correspondance Amazon. |

## 3. Dépannage du Marchand et Questions Fréquemment Posées (FAQ)

**Q1 : Mes conversions Amazon Ads ne correspondent pas à mes ventes PrestaShop. Que dois-je faire ?**
R1 : C'est un problème courant, souvent dû aux bloqueurs de publicité.
\* **Vérifiez le Mode de Suivi :** Assurez-vous que vous utilisez le « Mode Dual (Hybride) » ou « Conversions API (Côté Serveur) » dans les paramètres du module. C'est le moyen le plus efficace de récupérer les conversions perdues.
\* **Vérifiez les ID/Jetons :** Vérifiez à nouveau que votre ID de Tag Amazon Ads et votre Jeton d'Accès à l'API de Conversions sont correctement saisis dans la configuration du module.
\* **Utilisez le Mode Débogage :** Activez temporairement le « Mode Débogage » et effectuez un achat test. Vérifiez la console de votre navigateur et les « Statistiques en Direct » du module pour voir si les événements se déclenchent.
\* **Videz le Cache :** Allez dans **Paramètres Avancés > Performances** dans votre back office PrestaShop et videz le cache Smarty et les autres caches. Parfois, l'ancien code du module peut persister.

**Q2 : Je vois des avertissements concernant la « Qualité des Données » ou les « ID de Produit Manquants » dans le Score de Santé du module. Comment puis-je résoudre ce problème ?**
R2 : Amazon s'appuie sur des données de produit de haute qualité pour une correspondance précise.
\* **Résolution d'ID Produit :** Dans la configuration du module, assurez-vous que votre paramètre « Résolution d'ID Produit » (par exemple, EAN, UPC, SKU) correspond à l'identifiant principal utilisé dans votre flux de produits Amazon.
\* **Mettez à Jour les Données Produit :** Allez dans **Catalogue > Produits** dans votre back office PrestaShop. Modifiez les produits signalés par le « Coach de Qualité des Données » et assurez-vous qu'ils ont des EAN, UPC ou SKU complets et précis, comme requis.
\* **Cohérence :** Assurez-vous que les identifiants de produit dans votre boutique PrestaShop sont cohérents avec ce que vous fournissez à Amazon dans vos flux de produits.

**Q3 : Mon site web utilise une bannière de consentement aux cookies. Ce module respectera-t-il les choix des clients ?**
R3 : Oui, si configuré correctement.
\* **Activez l'Intégration du Consentement :** Dans la configuration du module, assurez-vous que l'« Intégration de la Gestion du Consentement » est activée.
\* **Compatibilité du Module de Cookies :** Ce module est conçu pour s'intégrer aux modules de consentement aux cookies PrestaShop standard. Si vous utilisez une solution personnalisée, vous devrez peut-être vous assurer qu'elle déclenche correctement les événements `prestashop.on('updateProduct', ...)` ou similaires que les modules écoutent pour les changements de consentement.
\* **CAPI vs. Tag :** N'oubliez pas que l'API de Conversions (côté serveur) est moins affectée par les bannières de consentement côté client que l'Amazon Ads Tag (côté client), car elle envoie les données directement depuis votre serveur. Cependant, il est toujours préférable de n'envoyer des informations personnellement identifiables (PII) via CAPI qu'après consentement.

**Q4 : Le module semble ralentir mon site. Que puis-je faire ?**
R4 : Ce module est optimisé pour la performance, mais voici quelques vérifications :
\* **Désactivez le Mode Débogage :** Assurez-vous que le « Mode Débogage » est désactivé sur votre boutique en direct, car il ajoute des journaux de console supplémentaires.
\* **Performances du Serveur :** L'API de Conversions (CAPI) effectue des appels de serveur à serveur. Bien que généralement rapides, assurez-vous que votre serveur d'hébergement dispose de ressources adéquates et d'une connexion Internet stable.
\* **Autres Modules :** Vérifiez si d'autres modules de suivi ou de publicité lourds fonctionnent également simultanément. Trop de scripts côté client peuvent avoir un impact sur les performances.
\* **Videz le Cache :** Videz toujours le cache de PrestaShop après avoir apporté des modifications de configuration.

**Q5 : Je reçois un message d'erreur lorsque j'essaie d'enregistrer la configuration du module.**
R5 :
\* **Vérifiez les Permissions :** Assurez-vous que le dossier du module (`/modules/myamazon/`) et ses sous-dossiers ont les bonnes permissions d'écriture (généralement 755 pour les dossiers, 644 pour les fichiers).
\* **Journaux du Serveur :** Vérifiez les journaux d'erreurs PHP de votre serveur pour des informations plus détaillées sur l'erreur. Cela peut souvent être trouvé dans votre panneau de contrôle d'hébergement ou en contactant votre hébergeur.
\* **Mode Débogage PrestaShop :** Activez temporairement le mode débogage de PrestaShop (dans `config/defines.inc.php`, changez `define('_PS_MODE_DEV_', false);` en `define('_PS_MODE_DEV_', true);`) pour voir des messages d'erreur plus détaillés à l'écran.

## 4. Guide du Développeur et du Webmaster (Architecture Technique et Carte du Code)

Cette section fournit une analyse approfondie de la structure technique du module « Amazon Ads Tag Conversions API », destinée aux développeurs et aux webmasters.

### 4.1 Vue d'Ensemble de l'Architecture

Le module `myamazon` est construit en suivant le modèle MVC (Model-View-Controller) de PrestaShop, avec un fort accent sur la modularité et le suivi basé sur les événements. Il exploite à la fois les mécanismes côté client (Amazon Ads Tag) et côté serveur (Conversions API), souvent dans une approche hybride.

Composants architecturaux clés :

- **Classe de Module Principale (`myamazon/index.php`) :** Gère l'installation, la désinstallation, l'enregistrement des hooks et la méthode `getContent()` principale pour la configuration du back-office.
- **Contrôleurs :** Contrôleurs frontaux dédiés aux interactions AJAX et contrôleurs d'administration pour la gestion des paramètres du module et des vues de diagnostic.
- **Classes Principales (`classes/`) :** Un ensemble robuste de classes gère divers aspects :
  - **Logique de Suivi :** `MyamazonAatTracker.php` (côté client), `MyamazonCapiTracker.php` (côté serveur), `MyamazonHybridTracker.php` (mode dual), `MyamazonTrackerFactory.php` (instancie les traqueurs).
  - **Gestion des Données :** `MyamazonUserData.php` (données client), `MyamazonEventMap.php` (traduction d'événements), `MyamazonProductIdResolver.php` (logique d'ID produit), `MyamazonCurrencyHelper.php`.
  - **Client API :** `MyamazonCapiClient.php` (gère la communication avec l'API CAPI d'Amazon).
  - **Diagnostics et Santé :** `MyamazonHealthScore.php`, `MyamazonCatalogDoctor.php`, `MyamazonDataQualityCoach.php`, `MyamazonLiveStats.php`.
  - **Consentement :** `MyamazonConsent.php` (s'intègre aux mécanismes de consentement).
- **Hooks :** Utilisation extensive des hooks PrestaShop pour injecter du JavaScript, capturer des événements et envoyer des données à des points critiques du parcours client.
- **Templates Smarty :** Utilisés pour le rendu des vues de configuration du back-office et des scripts de suivi du front-office.
- **JavaScript :** Gère l'injection de tags côté client, l'écoute d'événements et les interactions de la couche de données.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `controllers/front/ajax.php`
  - **Nom de la Classe :** `MyamazonAjaxModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** Gère les requêtes asynchrones (AJAX) depuis le front-office. Ceci est généralement utilisé pour l'envoi d'événements côté serveur via CAPI qui ne peut pas être effectué directement dans le navigateur (par exemple, les événements post-achat où le navigateur pourrait être fermé, ou les événements nécessitant un traitement de données côté serveur). Il reçoit les données du JavaScript côté client et les transmet au `MyamazonCapiTracker`.
- `controllers/front/index.php`
  - **Nom de la Classe :** `MyamazonIndexModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** Ce contrôleur pourrait servir de solution de repli ou de point d'entrée simple, bien que son cas d'utilisation principal puisse être minimal si `ajax.php` gère la plupart des interactions frontales. Il pourrait être utilisé pour des redirections spécifiques ou des affichages de données simples si nécessaire, mais sert souvent de placeholder.

#### Contrôleurs d'Administration Back-Office

- `controllers/admin/AdminMyamazonAjaxController.php`
  - **Nom de la Classe :** `AdminMyamazonAjaxController` (étend `ModuleAdminController`)
  - **Nom de l'Onglet :** Pas directement un onglet de menu, mais un point d'accès AJAX pour l'interface d'administration.
  - **Responsabilité :** Gère les requêtes AJAX provenant des pages de configuration du back-office du module. Cela inclut la récupération de données pour les statistiques en direct, les scores de santé ou l'exécution de vérifications en arrière-plan (par exemple, la validation du jeton API) sans recharger la page entière. Il interagit avec des classes comme `MyamazonLiveStats`, `MyamazonHealthScore` et `MyamazonCapiClient`.
- `controllers/admin/index.php`
  - **Nom de la Classe :** `AdminMyamazonIndexController` (étend `ModuleAdminController`)
  - **Nom de l'Onglet :** Pas un onglet de menu direct.
  - **Responsabilité :** Similaire au `index.php` du front-office, cela pourrait être un placeholder ou gérer des interactions d'administration très spécifiques et non-AJAX. La logique de configuration principale réside dans la méthode `getContent()` du module principal.

### 4.3 Classes et Modèles Principaux (`classes/`)

- `classes/autoload.php` : Fichier d'autoload standard de PrestaShop.
- `classes/index.php` : Fichier placeholder, courant dans les répertoires vides.
- `classes/MyamazonAatTracker.php` :
  - **Responsabilité :** Implémente la logique de suivi côté client de l'Amazon Ads Tag. Génère le JavaScript nécessaire pour `aa.js` et pousse les événements vers la couche de données du navigateur ou directement vers l'Amazon Ads Tag.
- `classes/MyamazonCapiClient.php` :
  - **Responsabilité :** Gère les requêtes HTTP réelles vers les points d'accès de l'API de Conversions d'Amazon. Encapsule la logique cURL ou Guzzle (si utilisé), l'authentification avec le jeton d'accès et la gestion des erreurs pour la communication de serveur à serveur.
- `classes/MyamazonCapiTracker.php` :
  - **Responsabilité :** Implémente la logique de suivi côté serveur de l'API de Conversions. Formate les données d'événement selon les spécifications CAPI d'Amazon et utilise `MyamazonCapiClient` pour les envoyer.
- `classes/MyamazonCatalogDoctor.php` :
  - **Responsabilité :** Analyse les données du catalogue de produits de la boutique pour les problèmes potentiels qui pourraient affecter la correspondance des produits Amazon (par exemple, EAN manquants, SKU incorrects). Fournit des commentaires de diagnostic pour l'interface d'administration.
- `classes/MyamazonConsent.php` :
  - **Responsabilité :** Gère l'intégration du consentement aux cookies. Vérifie l'état du consentement du client et active/désactive conditionnellement les scripts de suivi côté client. S'intègre à l'événement `prestashop.on('updateProduct', ...)` de PrestaShop pour les changements de consentement.
- `classes/MyamazonCurrencyHelper.php` :
  - **Responsabilité :** Fournit des méthodes utilitaires pour formater correctement les valeurs de devise pour Amazon Ads, en gérant les décimales et les codes de devise.
- `classes/MyamazonDataLayerTracker.php` :
  - **Responsabilité :** Gère la poussée des données d'événement vers un objet JavaScript `dataLayer`, souvent utilisé pour la compatibilité avec Google Tag Manager ou d'autres consommateurs de couche de données.
- `classes/MyamazonDataQualityCoach.php` :
  - **Responsabilité :** Fournit des informations et des recommandations pour améliorer la qualité globale des données envoyées à Amazon, couvrant des aspects au-delà des simples ID de produit.
- `classes/MyamazonEventId.php` :
  - **Responsabilité :** Génère des ID d'événement uniques pour chaque événement, cruciaux pour la déduplication lors de l'utilisation du suivi en mode dual (garantissant qu'Amazon ne compte pas le même événement deux fois à partir du côté client et du côté serveur).
- `classes/MyamazonEventMap.php` :
  - **Responsabilité :** Définit le mappage entre les événements internes de PrestaShop (par exemple, `actionCartSave`) et les noms d'événements standard d'Amazon Ads (par exemple, `AddToCart`). Permet la personnalisation de ces mappages.
- `classes/MyamazonEvents.php` :
  - **Responsabilité :** Une classe centrale ou une collection de méthodes pour déclencher et gérer divers événements Amazon Ads (par exemple, `PageView`, `ViewContent`, `AddToCart`, `Purchase`).
- `classes/MyamazonHealthScore.php` :
  - **Responsabilité :** Calcule et présente un « score de santé » global pour le suivi du module, identifiant les problèmes de configuration, les données manquantes ou les lacunes potentielles de suivi.
- `classes/MyamazonHybridTracker.php` :
  - **Responsabilité :** Orchestre le suivi en mode dual, combinant `MyamazonAatTracker` et `MyamazonCapiTracker` pour envoyer des événements via les méthodes côté client et côté serveur, gérant la déduplication.
- `classes/MyamazonLiveStats.php` :
  - **Responsabilité :** Collecte et traite les données d'événements en temps réel ou quasi-réel pour l'affichage dans la vue back-office « Statistiques en Direct ».
- `classes/MyamazonProductIdResolver.php` :
  - **Responsabilité :** Détermine quel identifiant de produit (ID, EAN, UPC, SKU) doit être utilisé lors de l'envoi de données produit à Amazon, en fonction de la configuration du module.
- `classes/MyamazonPropertyRules.php` :
  - **Responsabilité :** Définit les règles et les validations pour les propriétés d'événement, garantissant que les données envoyées à Amazon respectent leurs spécifications API.
- `classes/MyamazonTrackerFactory.php` :
  - **Responsabilité :** Une classe de type fabrique responsable de l'instanciation du traqueur correct (`AatTracker`, `CapiTracker` ou `HybridTracker`) en fonction de la configuration du module.
- `classes/MyamazonTrackerInterface.php` :
  - **Responsabilité :** Définit une interface commune pour toutes les classes de traqueurs (`AatTracker`, `CapiTracker`, `HybridTracker`), garantissant qu'elles implémentent un ensemble cohérent de méthodes pour le suivi des événements.
- `classes/MyamazonUserData.php` :
  - **Responsabilité :** Collecte et formate les données relatives aux clients (par exemple, e-mail, téléphone, adresse) pour les inclure dans les événements Amazon Ads, en particulier pour l'API de Conversions où les PII peuvent être hachées et envoyées.

### 4.4 Actifs JavaScript (`views/js/`)

- `views/js/myamazon-admin.js` :
  - **Portée :** Back-office.
  - **Détails :** Gère les éléments interactifs sur les pages de configuration du module, tels que le changement d'onglet, les appels AJAX pour les statistiques en direct, la validation de formulaire et les mises à jour dynamiques des outils de diagnostic.
- `views/js/myamazon-debug.js` :
  - **Portée :** Front-office (chargé conditionnellement lorsque le mode débogage est actif).
  - **Détails :** Fournit une journalisation verbeuse à la console du navigateur, affichant les événements déclenchés, les charges utiles des données et l'état des appels Amazon Ads Tag et CAPI. Peut inclure des superpositions visuelles pour un débogage rapide.
- `views/js/myamazon-ghost.js` :
  - **Portée :** Front-office.
  - **Détails :** Probablement lié aux mécanismes de suivi « fantôme » ou en arrière-plan, potentiellement pour la capture d'événements qui pourraient autrement être manqués ou pour des reports spécifiques liés au consentement.
- `views/js/myamazon-live.js` :
  - **Portée :** Back-office.
  - **Détails :** Alimente le tableau de bord « Statistiques en Direct », effectuant des requêtes AJAX vers `AdminMyamazonAjaxController` pour récupérer et afficher les données d'événements en temps réel.
- `views/js/myamazon-tcf.js` :
  - **Portée :** Front-office.
  - **Détails :** S'intègre aux solutions de consentement aux cookies conformes au Transparency and Consent Framework (TCF), garantissant que le suivi côté client respecte les préférences de consentement de l'utilisateur.
- `views/js/myamazon-wizard.js` :
  - **Portée :** Back-office.
  - **Détails :** Fournit des étapes interactives pour l'assistant de configuration initial, guidant le marchand à travers la configuration essentielle.
- `views/js/myamazon.js` :
  - **Portée :** Front-office.
  - **Détails :** Le JavaScript principal côté client pour le module. Il injecte l'Amazon Ads Tag (script `aa.js`), écoute divers événements DOM (par exemple, `click` sur les boutons d'ajout au panier), capture les données de la page, pousse les événements vers la couche de données et peut effectuer des appels AJAX vers `MyamazonAjaxModuleFrontController` pour le traitement côté serveur. Il gère également la logique de déduplication des événements.

### 4.5 Feuilles de Style CSS (`views/css/`)

- `myamazon/opis/sugestie/style1.css`, `myamazon/opis/sugestie/style2.css`, `myamazon/opis/sugestie/sugestie/style1.css`, `myamazon/opis/sugestie/sugestie/style2.css`, `myamazon/opis/sugestie/sugestie/tailwind-new-7.css`, `myamazon/opis/sugestie/tailwind-new-7.css` :
  - **Portée :** Back-office.
  - **Détails :** Ces fichiers semblent être liés à un framework d'interface utilisateur personnalisé ou à un style pour les suggestions/indices dans la configuration du back-office, éventuellement pour une configuration guidée ou un retour de diagnostic. `tailwind-new-7.css` suggère l'utilisation de Tailwind CSS pour un style axé sur les utilitaires.
- `views/css/myamazon-admin.css` :
  - **Portée :** Style du formulaire d'administration du back-office.
  - **Détails :** Fournit un style spécifique pour les formulaires de configuration du module, les onglets, les panneaux de diagnostic et d'autres éléments d'interface utilisateur personnalisés dans le back office de PrestaShop.
- `views/css/myamazon-debug.css` :
  - **Portée :** Front-office (chargé conditionnellement).
  - **Détails :** Styles pour la superposition de débogage ou les messages de console, garantissant qu'ils sont lisibles et distincts lorsque le mode débogage est actif.

### 4.6 Structure des Templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

- `views/templates/hook/capi-pageview.tpl` :
  - **Hook :** `displayHeader` (ou similaire).
  - **Sortie :** Injecte les données d'événement PageView côté serveur (CAPI), potentiellement sous forme d'entrée cachée ou de variable JavaScript, à récupérer par le contrôleur `ajax.php` pour l'envoi côté serveur.
- `views/templates/hook/debug.tpl` :
  - **Hook :** `displayHeader` (conditionnellement).
  - **Sortie :** Injecte le script `myamazon-debug.js` et toutes les variables de débogage initiales nécessaires lorsque le mode débogage est activé.
- `views/templates/hook/displayOrderConfirmation.tpl` :
  - **Hook :** `displayOrderConfirmation`.
  - **Sortie :** Rend les données d'événement « Purchase » critiques, y compris les détails de la commande, les produits et les informations client, pour la transmission côté client et côté serveur CAPI. C'est là que la valeur de conversion est capturée.
- `views/templates/hook/ghost.tpl` :
  - **Hook :** `displayHeader` (ou similaire).
  - **Sortie :** Lié au mécanisme de suivi « fantôme », potentiellement pour un chargement différé ou une logique spécifique liée au consentement.
- `views/templates/hook/header.tpl` :
  - **Hook :** `displayHeader`.
  - **Sortie :** Le template principal pour injecter l'Amazon Ads Tag (script `aa.js`), `myamazon.js` et les variables de configuration initiales dans la section `<head>` de chaque page.
- `views/templates/hook/payment.tpl` :
  - **Hook :** `displayPaymentTop` (ou similaire).
  - **Sortie :** Peut être utilisé pour suivre les événements « InitiateCheckout » ou d'autres événements liés au paiement avant la confirmation finale de la commande.
- `views/templates/hook/product-details.tpl` :
  - **Hook :** `displayProductButtons` ou `displayProductExtraContent`.
  - **Sortie :** Injecte du JavaScript pour suivre les événements « ViewContent » lorsqu'une page produit est chargée, capturant des données spécifiques au produit.

#### Templates d'administration (`views/templates/admin/`)

- `views/templates/admin/consent-guide.tpl` : Affiche des conseils sur la façon de s'intégrer aux modules de consentement aux cookies.
- `views/templates/admin/doctor.tpl` : Rend la vue de diagnostic « Docteur de Catalogue », affichant les problèmes de données produit.
- `views/templates/admin/dq.tpl` : Rend la vue « Coach de Qualité des Données », fournissant des informations sur la qualité des données.
- `views/templates/admin/health.tpl` : Affiche le « Score de Santé » global et les diagnostics associés.
- `views/templates/admin/linker-domains.tpl` : Rend le champ de saisie pour la configuration des domaines de liaison.
- `views/templates/admin/live-maintain.tpl` : Probablement une vue de maintenance pour les statistiques en direct.
- `views/templates/admin/live.tpl` : Rend le tableau de bord « Statistiques en Direct ».
- `views/templates/admin/mode-context.tpl`, `views/templates/admin/mode-note-aat.tpl`, `views/templates/admin/mode-note-both.tpl`, `views/templates/admin/mode-note-capi.tpl`, `views/templates/admin/mode-note-datalayer.tpl`, `views/templates/admin/mode-picker.tpl` : Ces templates sont utilisés pour la section « Sélection du Mode de Suivi », fournissant des explications et le bouton radio/menu déroulant pour choisir la méthode de suivi.
- `views/templates/admin/properties-list.tpl` : Affiche une liste des propriétés d'événement et de leurs valeurs, éventuellement pour le débogage ou la configuration.
- `views/templates/admin/recent-events.tpl` : Rend un tableau ou une liste des événements récemment suivis, faisant partie des « Statistiques en Direct ».
- `views/templates/admin/tabs.tpl` : Rend la structure de navigation par onglets pour la configuration du back-office du module.
- `views/templates/admin/tag-chips.tpl` : Affiche des « puces » ou des étiquettes visuelles pour les tags/jetons configurés.
- `views/templates/admin/tag-ids.tpl` : Rend les champs de saisie pour l'ID du Tag Amazon Ads et le Jeton d'Accès CAPI.
- `views/templates/admin/wizard.tpl` : Rend l'interface de l'assistant de configuration initial.

### 4.7 Schéma de Base de Données et Carte des Hooks

#### Tables de Base de Données

Le module stocke principalement sa configuration dans la table `ps_configuration` de PrestaShop.

- `ps_configuration` : Stocke les paires clé-valeur pour les paramètres du module (par exemple, `MYAMAZON_TAG_ID`, `MYAMAZON_CAPI_TOKEN`, `MYAMAZON_TRACKING_MODE`).
  Aucune table SQL personnalisée n'est explicitement créée par ce module sur la base de l'inventaire fourni.

#### Tableau des Hooks Enregistrés

| Nom du Hook | Moment d'Exécution | Objectif Technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Injecte le script Amazon Ads Tag (`aa.js`), `myamazon.js` et les variables de configuration initiales. Également utilisé pour `capi-pageview.tpl` et `debug.tpl`. |
| `displayOrderConfirmation` | Sur la page de confirmation de commande après un achat réussi. | Capture et envoie les données d'événement « Purchase », y compris les détails de la commande et les produits, à Amazon via les méthodes côté client et côté serveur. |
| `actionCartSave` | Lorsqu'un produit est ajouté ou retiré du panier, ou que la quantité du panier change. | Déclenche les événements « AddToCart » ou « RemoveFromCart ». |
| `actionProductAdd` | Lorsqu'un nouveau produit est ajouté au catalogue. | Potentiellement utilisé par `MyamazonCatalogDoctor` pour les vérifications de qualité des données. |
| `actionProductUpdate` | Lorsqu'un produit existant est mis à jour dans le catalogue. | Potentiellement utilisé par `MyamazonCatalogDoctor` pour les vérifications de qualité des données. |
| `actionFrontControllerSetMedia` | Avant qu'un contrôleur frontal ne rende son template, permettant l'ajout de JS/CSS. | Injecte les fichiers JS/CSS spécifiques au module (`myamazon.js`, `myamazon-debug.js`, etc.) dans le front office. |
| `actionAdminControllerSetMedia` | Avant qu'un contrôleur d'administration ne rende son template. | Injecte les fichiers JS/CSS spécifiques au module (`myamazon-admin.js`, `myamazon-admin.css`, etc.) dans le back office. |
| `actionValidateOrder` | Après qu'une commande a été validée et enregistrée avec succès dans la base de données. | Crucial pour l'envoi d'événements « Purchase » côté serveur via CAPI, garantissant que les données sont envoyées même si le client ferme le navigateur avant d'atteindre la page de confirmation. |
| `displayProductButtons` / `displayProductExtraContent` | Sur la page produit, près du bouton d'ajout au panier ou de la description du produit. | Injecte du JavaScript pour suivre les événements « ViewContent ». |
| `displayPaymentTop` | En haut de la page de sélection de paiement pendant le processus de commande. | Potentiellement utilisé pour suivre les événements « InitiateCheckout ». |
| `displayFooter` | Dans la section du pied de page de chaque page. | Moins courant pour le suivi de base, mais pourrait être utilisé pour le chargement différé de scripts ou des pop-ups de consentement spécifiques. |
| `actionObjectCustomerAddAfter` | Après la création d'un nouveau compte client. | Potentiellement utilisé pour envoyer des événements « SignUp » ou « Lead » à Amazon. |
| `actionObjectCustomerUpdateAfter` | Après la mise à jour des détails d'un client. | Pourrait être utilisé pour mettre à jour les données client pour CAPI. |

## 5. Support Officiel et Mises à Jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur MyPresta.eu.

- **Mises à Jour du Module :** Connectez-vous à votre compte sur [Historique des Commandes et Téléchargements MyPresta.eu](https://mypresta.eu/my-account/orders/) pour télécharger les nouvelles versions du module « Amazon Ads Tag Conversions API ».
- **Support Technique :** Si vous rencontrez des problèmes ou avez des questions concernant la fonctionnalité, la configuration ou l'intégration du module, veuillez ouvrir un ticket de support via votre compte client MyPresta.eu. Notre équipe d'experts est prête à vous aider.
