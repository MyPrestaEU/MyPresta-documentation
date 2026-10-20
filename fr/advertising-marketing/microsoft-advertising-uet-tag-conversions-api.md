---
title: "Balise UET et API de Conversions Microsoft Advertising - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Balise UET et API de Conversions Microsoft Advertising par MyPresta.eu."
sidebar:
  label: "Balise UET et API de Conversions Microsoft Advertising - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Microsoft Advertising UET Tag & Conversions API sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/microsoft-advertising-uet-tag-conversions-api.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/microsoft-advertising-uet-tag-conversions-api/)
>
> ---


# Balise UET et API de Conversions Microsoft Advertising

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard telles que cURL, JSON et OpenSSL sont requises pour que le module fonctionne correctement, en particulier pour les fonctionnalités de l'API de Conversions. Celles-ci sont généralement activées par défaut sur la plupart des environnements d'hébergement modernes.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est le centre principal pour configurer votre suivi Microsoft Advertising. Vous trouverez une série d'onglets et de paramètres conçus pour vous guider tout au long du processus.

#### Onglet Configuration principale (Vue initiale)

-   **Ce que fait ce paramètre :** Cet onglet fournit généralement un aperçu et des options de configuration initiales, incluant souvent un assistant pour simplifier la première configuration.
-   **Effet de la modification de ce paramètre :** La complétion de l'assistant ou le remplissage des détails initiaux activera la fonctionnalité de suivi de base et préparera le module pour des paramètres plus avancés.
-   **Valeur recommandée :** Suivez attentivement les étapes de l'assistant.
-   **Scénario / exemple de marchand :** Lors de la première installation du module, l'assistant vous demandera votre ID de balise UET et vous guidera dans le choix de votre méthode de suivi (balise UET, API de Conversions, ou les deux).

#### ID de balise UET

-   **Ce que fait ce paramètre :** C'est votre identifiant unique fourni par Microsoft Advertising. Il indique à Microsoft à quel compte associer les données de suivi.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est saisi correctement :* Le module intégrera la balise UET sur votre boutique, permettant à Microsoft Advertising de suivre le comportement des utilisateurs.
    -   *Lorsqu'il est laissé vide ou incorrect :* Aucun suivi de balise UET ne se produira, et vos campagnes Microsoft Advertising ne recevront pas de données de conversion du front-office.
-   **Valeur recommandée :** Votre ID de balise UET exact de votre compte Microsoft Advertising.
-   **Scénario / exemple de marchand :** Vous avez créé un compte Microsoft Advertising et configuré une balise UET. Vous copiez l'ID (par exemple, `12345678`) et le collez ici.

#### Mode de suivi (Balise UET, API de Conversions, ou les deux)

-   **Ce que fait ce paramètre :** Détermine comment les données de conversion sont envoyées à Microsoft Advertising.
    -   **Balise UET uniquement :** Suivi traditionnel côté client via JavaScript dans le navigateur du client.
    -   **API de Conversions uniquement :** Suivi côté serveur, envoyant les données directement de votre serveur PrestaShop à Microsoft. Plus résilient aux paramètres de confidentialité des navigateurs.
    -   **Les deux (Hybride) :** Utilise à la fois la balise UET et l'API de Conversions, avec un mécanisme de déduplication des événements, garantissant un comptage précis même si les deux méthodes signalent la même conversion.
-   **Effet de la modification de ce paramètre :**
    -   *Balise UET uniquement :* Repose uniquement sur le suivi basé sur le navigateur, qui peut être affecté par les bloqueurs de publicité ou les paramètres de confidentialité.
    -   *API de Conversions uniquement :* Fournit un suivi plus robuste, mais nécessite une configuration côté serveur et peut ne pas capturer tous les événements côté client (comme les vues de page) aussi facilement.
    -   *Les deux (Hybride) :* Offre le suivi le plus complet et le plus fiable, combinant les forces des deux méthodes tout en empêchant les conversions en double.
-   **Valeur recommandée :** **Les deux (Hybride)** est généralement recommandé pour une précision et une résilience maximales.
-   **Scénario / exemple de marchand :** Vous souhaitez les données les plus précises possibles, vous sélectionnez donc "Les deux (Hybride)" pour vous assurer que les conversions sont suivies même si un client utilise un bloqueur de publicité.

#### Jeton d'accès à l'API de Conversions

-   **Ce que fait ce paramètre :** Il s'agit d'un jeton sécurisé généré dans votre compte Microsoft Advertising, autorisant votre boutique PrestaShop à envoyer des données directement aux serveurs de Microsoft via l'API de Conversions.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est saisi correctement :* Active le suivi côté serveur pour l'API de Conversions.
    -   *Lorsqu'il est laissé vide ou incorrect :* L'API de Conversions ne fonctionnera pas, et les données de conversion côté serveur ne seront pas envoyées.
-   **Valeur recommandée :** Votre Jeton d'accès à l'API de Conversions exact de votre compte Microsoft Advertising.
-   **Scénario / exemple de marchand :** Vous avez généré un Jeton d'accès dans votre compte Microsoft Advertising (par exemple, sous "Outils" > "Suivi des conversions" > "API de Conversions"). Vous collez cette longue chaîne de caractères ici.

#### Activer les conversions améliorées

-   **Ce que fait ce paramètre :** Lorsqu'il est activé, cette fonctionnalité envoie des données client hachées (comme les adresses e-mail) avec les événements de conversion. Cela aide Microsoft à faire correspondre les conversions plus précisément, surtout lorsque les cookies sont limités, améliorant ainsi les performances de vos campagnes.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé :* Correspondance des conversions plus précise, ce qui peut potentiellement conduire à une meilleure optimisation de vos campagnes publicitaires.
    -   *Lorsqu'il est désactivé :* Les conversions reposent uniquement sur les méthodes de suivi standard, ce qui pourrait être moins précis dans certains environnements de navigateur axés sur la confidentialité.
-   **Valeur recommandée :** **OUI** (Activé), car cela améliore considérablement la correspondance des données.
-   **Scénario / exemple de marchand :** Vous souhaitez donner à Microsoft Advertising les meilleures données possibles pour optimiser vos campagnes, vous activez donc les conversions améliorées.

#### Intégration de la gestion du consentement

-   **Ce que fait ce paramètre :** Ce module peut s'intégrer aux modules de consentement aux cookies existants (comme les modules RGPD) pour garantir que la balise UET ne se déclenche qu'après que le client a donné son consentement.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé et intégré :* La balise UET respectera les choix de consentement du client. Si un client refuse les cookies de suivi, la balise UET ne se chargera pas.
    -   *Lorsqu'il est désactivé ou non intégré :* La balise UET pourrait se charger indépendamment du consentement, ce qui pourrait entraîner des problèmes de conformité.
-   **Valeur recommandée :** **OUI** (Activé) si vous utilisez un module de consentement aux cookies et que vous devez vous conformer aux réglementations en matière de confidentialité (par exemple, RGPD, CCPA).
-   **Scénario / exemple de marchand :** Votre boutique utilise un module RGPD. Vous activez ce paramètre pour vous assurer que votre suivi Microsoft Advertising est conforme aux lois sur la confidentialité.

#### Mode Débogage

-   **Ce que fait ce paramètre :** Active un mode spécial qui affiche des informations détaillées sur la balise UET et les événements de l'API de Conversions directement sur vos pages du front-office (visible uniquement par vous, l'administrateur, ou des adresses IP spécifiques). C'est inestimable pour vérifier que le suivi est correctement configuré.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé :* Vous verrez une superposition de débogage ou des messages de console sur le front-office de votre boutique, montrant quels événements sont suivis et quelles données sont envoyées.
    -   *Lorsqu'il est désactivé :* Le module fonctionne silencieusement, sans information de débogage visible.
-   **Valeur recommandée :** **NON** (Désactivé) pour les boutiques en production. **OUI** (Activé) temporairement pendant la configuration et le dépannage.
-   **Scénario / exemple de marchand :** Vous venez d'installer le module et souhaitez confirmer que les événements "Ajouter au panier" sont envoyés correctement. Vous activez le mode débogage, ajoutez un produit à votre panier et vérifiez la sortie de débogage.

#### Mappage d'événements (Avancé)

-   **Ce que fait ce paramètre :** Vous permet de personnaliser la façon dont des actions spécifiques de PrestaShop (par exemple, "Produit ajouté au panier") sont mappées aux noms d'événements Microsoft Advertising (par exemple, "add\_to\_cart"). Vous pouvez également définir des paramètres personnalisés à envoyer avec chaque événement.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est configuré :* Garantit que vos événements sont correctement catégorisés et enrichis avec des données pertinentes dans Microsoft Advertising.
    -   *Lorsqu'il est mal configuré :* Les événements pourraient ne pas être suivis, ou les données envoyées pourraient être inexactes, entraînant une mauvaise optimisation des campagnes.
-   **Valeur recommandée :** Utilisez les mappages par défaut, sauf si vous avez une raison spécifique de les modifier en fonction de votre configuration Microsoft Advertising.
-   **Scénario / exemple de marchand :** Vous souhaitez envoyer la marque du produit comme paramètre personnalisé avec chaque événement "view\_item". Vous configurerez ce mappage ici.

#### Domaines de liaison (Avancé)

-   **Ce que fait ce paramètre :** Si vous avez plusieurs sous-domaines ou sites web liés qui partagent la même balise UET, ce paramètre aide à garantir que les sessions utilisateur sont correctement liées entre ces domaines.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est configuré :* Permet un suivi transparent des parcours utilisateur sur plusieurs domaines sous votre contrôle.
    -   *Lorsqu'il n'est pas configuré (et nécessaire) :* Les sessions utilisateur pourraient être interrompues, entraînant une attribution de conversion inexacte.
-   **Valeur recommandée :** Laissez vide, sauf si vous exploitez plusieurs sous-domaines ou sites liés qui nécessitent un suivi inter-domaine.
-   **Scénario / exemple de marchand :** Vous avez votre boutique principale sur `shop.example.com` et un blog sur `blog.example.com`, tous deux utilisant la même balise UET. Vous ajouteriez `blog.example.com` à la liste des domaines de liaison.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Config principale | ID de balise UET | Votre ID de balise | Active le suivi de la balise UET. Essentiel pour les données côté client. |
| Config principale | Mode de suivi | Les deux (Hybride) | Sélectionne la balise UET, l'API de Conversions, ou les deux pour la transmission des données. L'hybride est le plus robuste. |
| Config principale | Jeton d'accès à l'API de Conversions | Votre Jeton d'accès | Autorise l'envoi de données côté serveur à Microsoft. |
| Config principale | Activer les conversions améliorées | OUI | Améliore la précision de la correspondance des conversions en envoyant des données client hachées. |
| Config principale | Intégration de la gestion du consentement | OUI (si applicable) | Garantit que la balise UET respecte les choix de confidentialité des clients (RGPD, CCPA). |
| Config principale | Mode Débogage | NON (OUI pour les tests) | Affiche les données de suivi sur le front-office pour vérification. |
| Config principale | Mappage d'événements | Par défaut | Personnalise la façon dont les actions PrestaShop sont mappées aux événements Microsoft. |
| Config principale | Domaines de liaison | Vide (si non nécessaire) | Active le suivi inter-domaine pour les sites web liés. |

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 AdminMybingAjaxController (Back Office > Modules > Balise UET et API de Conversions Microsoft Advertising > Statistiques en direct / Score de santé / Docteur / Qualité des données)

Ce contrôleur alimente les sections dynamiques et interactives de la configuration du module, fournissant des informations en temps réel et des outils de diagnostic. Vous n'accéderez pas à un élément de menu séparé pour cela, mais interagirez plutôt avec des onglets spécifiques au sein de la configuration principale du module.

-   **Nom de l'écran et emplacement du menu :** Ce sont généralement des sous-onglets au sein de la page de configuration principale du module (par exemple, "Statistiques en direct", "Score de santé", "Coach de qualité des données", "Docteur du catalogue").
-   **Actions et paramètres disponibles :**
    -   **Statistiques en direct :** Affiche les événements récents envoyés à Microsoft Advertising, montrant les vues de page, les ajouts au panier, les achats, etc., en temps quasi réel. Cela vous aide à confirmer que les événements se déclenchent correctement.
    -   **Score de santé :** Analyse votre configuration de suivi et fournit un score basé sur les meilleures pratiques, mettant en évidence les problèmes potentiels ou les domaines à améliorer.
    -   **Coach de qualité des données :** Offre des recommandations spécifiques pour améliorer la qualité et l'exhaustivité des données que vous envoyez à Microsoft, en particulier pour les conversions améliorées.
    -   **Docteur du catalogue :** Aide à diagnostiquer les problèmes liés à vos données produit qui pourraient affecter la publicité de flux de produits ou le remarketing dynamique.
-   **Effet des modifications :** L'interaction avec ces écrans fournit principalement des informations et des retours de diagnostic. Il n'y a pas de "paramètres" directs à modifier ici, mais les informations obtenues éclaireront les ajustements que vous pourriez apporter dans la configuration principale ou votre catalogue de produits.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    -   Vérifiez régulièrement les **Statistiques en direct** après avoir effectué des modifications ou lancé de nouvelles campagnes pour vous assurer que les événements sont suivis.
    -   Examinez périodiquement le **Score de santé** et le **Coach de qualité des données** pour des recommandations afin d'optimiser votre configuration de suivi.
    -   Si vous rencontrez des problèmes avec les annonces liées aux produits, consultez le **Docteur du catalogue**.

#### 2.2.2 index.php (Back Office > Modules > Balise UET et API de Conversions Microsoft Advertising)

Ceci fait référence au point d'entrée principal de l'interface back-office du module, qui est la page de configuration elle-même. Tous les paramètres décrits dans la section 4.1 sont gérés via cette vue principale. Il n'y a pas d'écran "index.php" séparé à naviguer au-delà de la configuration initiale du module.

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : Mes conversions n'apparaissent pas dans Microsoft Advertising. Que dois-je faire ?**
R :

1.  **Vérifiez l'ID de balise UET et le jeton d'accès :** Vérifiez à nouveau que votre ID de balise UET et votre jeton d'accès à l'API de Conversions sont correctement saisis dans la configuration du module. Même une seule faute de frappe peut empêcher le suivi.
2.  **Vérifiez le mode de suivi :** Assurez-vous que votre "Mode de suivi" est défini sur "Les deux (Hybride)" pour une fiabilité maximale.
3.  **Activez le mode débogage :** Activez le "Mode débogage" dans les paramètres du module et effectuez un achat test sur votre boutique. Recherchez la superposition de débogage ou les messages de la console pour voir si les événements se déclenchent.
4.  **Videz le cache :** Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop et videz le cache Smarty et tout autre cache. Parfois, d'anciens paramètres peuvent persister.
5.  **Vérifiez le compte Microsoft Advertising :** Connectez-vous à votre compte Microsoft Advertising et vérifiez l'état de la balise UET et la configuration des objectifs de conversion. Assurez-vous que vos objectifs de conversion sont correctement configurés pour correspondre aux événements envoyés par le module (par exemple, "Achat").

**Q : Le module indique que "l'intégration de la gestion du consentement" est activée, mais je n'ai pas de module RGPD. Est-ce un problème ?**
R : Si vous n'avez pas de module de consentement aux cookies dédié installé et configuré, ce paramètre n'aura aucun effet pratique. Le module supposera le consentement par défaut. Cependant, pour la conformité légale (par exemple, RGPD, CCPA), il est fortement recommandé d'utiliser un module de consentement aux cookies approprié. Si vous en installez un plus tard, ce module s'intégrera automatiquement à celui-ci.

**Q : Mon thème personnalisé semble un peu décalé après l'installation du module, ou je vois une page blanche.**
R : Ce module fonctionne principalement en arrière-plan et ne devrait pas affecter l'apparence visuelle de votre thème.

1.  **Videz le cache :** La solution la plus courante pour les problèmes d'affichage après l'installation du module est de vider votre cache PrestaShop (**Paramètres avancés > Performances**).
2.  **Vérifiez les conflits :** Si le problème persiste, désactivez temporairement les autres modules récemment installés pour vérifier les conflits.
3.  **Erreurs PHP :** Si vous voyez une page blanche, activez le rapport d'erreurs PHP sur votre serveur (ou vérifiez les journaux d'erreurs de votre serveur) pour identifier toute erreur critique.
    Si le problème persiste, contactez le support MyPresta.eu avec les détails de votre thème et tout message d'erreur.

**Q : Comment traduire les textes du module dans d'autres langues ?**
R :

1.  Allez dans **International > Traductions** dans votre Back Office PrestaShop.
2.  Sélectionnez "Traductions des modules installés" comme type de traduction.
3.  Choisissez votre thème, la langue que vous souhaitez traduire, puis sélectionnez "Balise UET et API de Conversions Microsoft Advertising" dans la liste des modules.
4.  Vous pouvez ensuite traduire toutes les chaînes visibles utilisées par le module.

**Q : Pourquoi le "Coach de qualité des données" ou le "Score de santé" affiche-t-il des avertissements ?**
R : Ces outils sont conçus pour vous aider à optimiser votre suivi. Les avertissements indiquent souvent :

-   **Données de conversion améliorées manquantes :** Assurez-vous que les données client (comme l'e-mail) sont disponibles et envoyées.
-   **Problèmes de données produit :** Votre catalogue de produits pourrait manquer de GTIN, MPN ou d'autres identifiants cruciaux pour la publicité de flux de produits.
-   **Faible volume d'événements :** Si votre boutique a très peu de trafic, les outils pourraient ne pas avoir suffisamment de données pour fournir une analyse complète.
    Suivez les recommandations spécifiques fournies par les outils pour améliorer la qualité de vos données et la santé de votre suivi.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module `Balise UET et API de Conversions Microsoft Advertising` (`mybing`) est construit selon le modèle MVC (Model-View-Controller) de PrestaShop, avec un fort accent sur la modularité et l'extensibilité. Il utilise un modèle de fabrique pour l'instanciation du traqueur (`MybingTrackerFactory`) afin de prendre en charge différents modes de suivi (UET, CAPI, Hybride) et exploite un système d'événements robuste (`MybingEvents`) pour capturer diverses actions de commerce électronique. La qualité des données et les diagnostics sont gérés par des classes dédiées (`MybingHealthScore`, `MybingDataQualityCoach`, `MybingCatalogDoctor`). Le module s'intègre au système de hooks de PrestaShop pour l'injection d'événements côté front-office et utilise des contrôleurs d'administration dédiés pour sa configuration avancée et ses outils de diagnostic.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   `mybing/controllers/front/ajax.php`
    -   **Nom de la classe :** `MybingAjaxModuleFrontController` (étend `ModuleFrontController`)
    -   **Responsabilité :** Gère les requêtes AJAX du front-office, principalement pour l'envoi d'événements côté client ou de données qui ne peuvent pas être directement gérées par la balise UET (par exemple, pour l'intégration de la gestion du consentement, ou la collecte de données spécifiques avant une redirection de page). Il peut également être utilisé pour envoyer des événements CAPI qui sont déclenchés côté client mais nécessitent un traitement côté serveur.
-   `mybing/controllers/front/cron.php`
    -   **Nom de la classe :** `MybingCronModuleFrontController` (étend `ModuleFrontController`)
    -   **Responsabilité :** Fournit un point d'accès pour une tâche cron. Ceci est généralement utilisé pour les tâches côté serveur qui doivent s'exécuter périodiquement, telles que l'envoi d'événements d'API de Conversions différés, la synchronisation de données ou l'exécution de tâches de maintenance liées à la fonctionnalité du module.
-   `mybing/controllers/front/index.php`
    -   **Nom de la classe :** `MybingIndexModuleFrontController` (étend `ModuleFrontController`)
    -   **Responsabilité :** Un contrôleur frontal générique, souvent utilisé comme solution de repli ou pour des interactions simples et non-AJAX du front-office. Dans ce module, il pourrait être utilisé pour des redirections spécifiques ou pour gérer les requêtes initiales liées à la configuration du suivi.

#### Contrôleurs d'administration Back-Office

-   `mybing/controllers/admin/AdminMybingAjaxController.php`
    -   **Nom de la classe :** `AdminMybingAjaxController` (étend `AdminController`)
    -   **Nom de l'onglet :** Pas un onglet autonome, mais un point d'accès AJAX pour la configuration principale du module.
    -   **Entité gérée :** Gère le chargement et le traitement dynamique des données pour les onglets de diagnostic et de statistiques du module (Statistiques en direct, Score de santé, Coach de qualité des données, Docteur du catalogue). Il traite les requêtes pour les journaux d'événements, les vérifications de santé et les rapports de qualité des données, renvoyant des réponses JSON au JavaScript de l'administration.
-   `mybing/controllers/admin/index.php`
    -   **Nom de la classe :** `AdminMybingIndexController` (étend `AdminController`)
    -   **Nom de l'onglet :** Pas un onglet autonome. Il s'agit d'un espace réservé ou d'un contrôleur d'administration générique qui pourrait être utilisé pour des redirections ou des actions internes spécifiques au sein de l'interface d'administration du module, mais la configuration principale est gérée par la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

-   `mybing/classes/autoload.php` : Fichier d'autoload standard de PrestaShop, garantissant que les classes du module sont chargées correctement.
-   `mybing/classes/index.php` : Fichier de remplacement, souvent pour empêcher la liste des répertoires.
-   `mybing/classes/MybingCapiClient.php` : Gère la communication avec le point de terminaison de l'API de Conversions Microsoft Advertising. Encapsule les requêtes HTTP, l'authentification (Jeton d'accès) et le formatage des données pour la soumission d'événements côté serveur.
-   `mybing/classes/MybingCapiTracker.php` : Implémente `MybingTrackerInterface` pour le suivi côté serveur (API de Conversions). Responsable de la collecte des données d'événements, de leur préparation pour le client CAPI et de leur envoi.
-   `mybing/classes/MybingCatalogDoctor.php` : Fournit une logique de diagnostic pour analyser la qualité des données produit, identifiant les problèmes qui pourraient affecter les flux de produits ou le remarketing dynamique dans Microsoft Advertising.
-   `mybing/classes/MybingConsent.php` : Gère l'intégration avec les modules de consentement aux cookies. Détermine si le consentement de l'utilisateur a été donné pour le suivi et contrôle le déclenchement de la balise UET en conséquence.
-   `mybing/classes/MybingCurrencyHelper.php` : Classe utilitaire pour gérer les conversions et le formatage des devises, garantissant que les valeurs d'événements sont envoyées correctement à Microsoft Advertising.
-   `mybing/classes/MybingDataQualityCoach.php` : Analyse la qualité et l'exhaustivité des données envoyées pour les événements, en particulier pour les conversions améliorées, et fournit des recommandations d'amélioration.
-   `mybing/classes/MybingEventId.php` : Génère et gère des ID d'événements uniques pour la déduplication, crucial pour le suivi hybride (UET + CAPI).
-   `mybing/classes/MybingEventMap.php` : Définit le mappage entre les actions PrestaShop (par exemple, `actionCartSave`) et les noms d'événements Microsoft Advertising (par exemple, `add_to_cart`), y compris les paramètres personnalisés.
-   `mybing/classes/MybingEvents.php` : Classe centrale pour définir et déclencher tous les événements de commerce électronique suivis (par exemple, `PageView`, `AddToCart`, `Purchase`). Elle agit comme un répartiteur d'événements au sein du module.
-   `mybing/classes/MybingHealthScore.php` : Calcule un "score de santé" pour la configuration globale du suivi, évaluant la configuration, la qualité des données et le déclenchement des événements.
-   `mybing/classes/MybingHybridTracker.php` : Implémente `MybingTrackerInterface` pour le suivi hybride. Orchestre le suivi de la balise UET et de l'API de Conversions, assurant la déduplication des événements à l'aide de `event_id`.
-   `mybing/classes/MybingLiveStats.php` : Collecte et fournit des statistiques en temps réel sur les événements suivis, affichées dans l'interface d'administration.
-   `mybing/classes/MybingProductIdResolver.php` : Aide à résoudre et à formater les ID de produit selon les exigences de Microsoft Advertising (par exemple, GTIN, MPN, custom\_label).
-   `mybing/classes/MybingPropertyRules.php` : Définit les règles et la logique pour extraire et formater diverses propriétés d'événements (par exemple, prix du produit, quantité, catégorie) pour Microsoft Advertising.
-   `mybing/classes/MybingTrackerFactory.php` : Classe de fabrique responsable de la création de l'instance de traqueur appropriée (`MybingUetTracker`, `MybingCapiTracker` ou `MybingHybridTracker`) en fonction de la configuration du module.
-   `mybing/classes/MybingTrackerInterface.php` : Définit le contrat pour toutes les classes de traqueurs, garantissant une interface cohérente pour les méthodes de suivi d'événements.
-   `mybing/classes/MybingUetTracker.php` : Implémente `MybingTrackerInterface` pour le suivi côté client (balise UET). Responsable de la génération du code JavaScript à injecter dans le front-office.
-   `mybing/classes/MybingUserData.php` : Collecte et formate les données spécifiques à l'utilisateur (par exemple, e-mail, téléphone, adresse) pour les conversions améliorées, y compris le hachage.

### 4.4 Actifs JavaScript (`views/js/`)

-   `mybing/views/js/mybing-admin.js` : JavaScript du back-office pour les fonctionnalités d'administration générales, les interactions de formulaire et les mises à jour dynamiques au sein de la page de configuration du module.
-   `mybing/views/js/mybing-debug.js` : JavaScript du front-office spécifiquement pour le mode débogage, affichant les informations de suivi et les charges utiles d'événements à l'administrateur.
-   `mybing/views/js/mybing-ghost.js` : JavaScript du front-office, potentiellement pour gérer les événements "fantômes" ou les interactions spécifiques côté client qui doivent être suivies sans action directe de l'utilisateur.
-   `mybing/views/js/mybing-live.js` : JavaScript du back-office pour l'onglet "Statistiques en direct", gérant les requêtes AJAX vers `AdminMybingAjaxController` et mettant à jour le flux d'événements en direct.
-   `mybing/views/js/mybing-tcf.js` : JavaScript du front-office pour l'intégration avec le Transparency and Consent Framework (TCF) ou d'autres plateformes de gestion du consentement, garantissant que la balise UET ne se déclenche qu'avec le consentement.
-   `mybing/views/js/mybing-wizard.js` : JavaScript du back-office pour l'assistant de configuration initial, guidant le marchand à travers les étapes de configuration.
-   `mybing/views/js/mybing.js` : Fichier JavaScript principal du front-office. Contient la logique de base pour initialiser la balise UET, capturer les événements côté client (par exemple, `add_to_cart`) et envoyer des données à la balise UET ou au contrôleur AJAX du module pour le traitement CAPI. Il se lie à divers événements DOM et aux événements `prestashop.on` de PrestaShop.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `mybing/views/css/mybing-admin.css` : CSS du back-office pour styliser la page de configuration du module, les outils de diagnostic et l'assistant, garantissant une interface d'administration cohérente et conviviale.
-   `mybing/views/css/mybing-debug.css` : CSS du front-office pour styliser la superposition de débogage, rendant les informations de suivi clairement visibles pour l'administrateur sans perturber la conception de la boutique.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)

-   `mybing/views/templates/hook/capi-pageview.tpl` : Rend un élément ou un script caché pour déclencher un événement PageView côté serveur via CAPI, souvent utilisé lorsque la balise UET pourrait être bloquée.
-   `mybing/views/templates/hook/debug.tpl` : Rend la structure HTML pour la superposition de débogage du front-office, affichant les données d'événements.
-   `mybing/views/templates/hook/displayOrderConfirmation.tpl` : Injecté dans le hook `displayOrderConfirmation`. Rend le script d'événement d'achat de la balise UET et/ou déclenche l'événement d'achat CAPI après une commande réussie.
-   `mybing/views/templates/hook/ghost.tpl` : Rend un script ou un élément caché pour le suivi "fantôme", potentiellement pour des événements d'arrière-plan spécifiques ou la collecte de données.
-   `mybing/views/templates/hook/header.tpl` : Injecté dans le hook `displayHeader`. Rend le script de base principal de la balise UET, l'intégration de la gestion du consentement et les événements PageView initiaux.
-   `mybing/views/templates/hook/payment.tpl` : Potentiellement utilisé pour suivre les événements liés à la sélection ou à l'initiation d'un mode de paiement, bien que `displayOrderConfirmation` soit plus courant pour l'achat final.
-   `mybing/views/templates/hook/product-details.tpl` : Injecté dans un hook de page produit (par exemple, `displayProductButtons` ou `displayProductExtraContent`). Rend les scripts pour les événements `view_item` et les écouteurs d'événements `add_to_cart`.

#### Modèles d'administration (`views/templates/admin/`)

-   `mybing/views/templates/admin/consent-guide.tpl` : Affiche des conseils et des informations concernant l'intégration de la gestion du consentement.
-   `mybing/views/templates/admin/doctor.tpl` : Rend l'interface de l'outil de diagnostic "Docteur du catalogue".
-   `mybing/views/templates/admin/dq.tpl` : Rend l'interface des recommandations du "Coach de qualité des données".
-   `mybing/views/templates/admin/health.tpl` : Rend l'interface de l'aperçu du "Score de santé".
-   `mybing/views/templates/admin/linker-domains.tpl` : Rend le champ de saisie et l'explication pour la configuration des domaines de liaison.
-   `mybing/views/templates/admin/live-maintain.tpl` : Rend un message de maintenance ou un statut pour la fonctionnalité de statistiques en direct.
-   `mybing/views/templates/admin/live.tpl` : Rend l'interface des "Statistiques en direct", affichant les événements récents.
-   `mybing/views/templates/admin/mode-context.tpl` : Fournit des informations contextuelles sur le mode de suivi choisi.
-   `mybing/views/templates/admin/mode-note-both.tpl` : Affiche une note ou une explication spécifique lorsque le mode "Les deux (Hybride)" est sélectionné.
-   `mybing/views/templates/admin/mode-note-capi.tpl` : Affiche une note ou une explication spécifique lorsque le mode "API de Conversions uniquement" est sélectionné.
-   `mybing/views/templates/admin/mode-note-uet.tpl` : Affiche une note ou une explication spécifique lorsque le mode "Balise UET uniquement" est sélectionné.
-   `mybing/views/templates/admin/mode-picker.tpl` : Rend les boutons radio ou la liste déroulante pour la sélection du mode de suivi.
-   `mybing/views/templates/admin/properties-list.tpl` : Rend une liste ou un tableau des propriétés d'événements et de leurs valeurs pour la configuration ou l'affichage.
-   `mybing/views/templates/admin/recent-events.tpl` : Rend un tableau ou une liste des événements récemment suivis, souvent dans le cadre des "Statistiques en direct".
-   `mybing/views/templates/admin/tabs.tpl` : Rend la structure de navigation par onglets pour la page de configuration du module (par exemple, Général, Statistiques en direct, Score de santé).
-   `mybing/views/templates/admin/tag-chips.tpl` : Rend des "jetons" visuels ou des indicateurs pour les ID de balise UET configurés.
-   `mybing/views/templates/admin/tag-ids.tpl` : Rend le champ de saisie pour les ID de balise UET.
-   `mybing/views/templates/admin/wizard.tpl` : Rend l'interface étape par étape pour l'assistant de configuration initial.

#### Modèles Front-office (`views/templates/front/`)

-   Aucun modèle de page autonome dédié identifié. Le rendu du front-office est principalement géré via des modèles de hook.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

Le module ne crée pas explicitement de tables SQL personnalisées basées sur l'inventaire fourni. Les enregistrements de configuration sont stockés dans la table `ps_configuration` de PrestaShop, en utilisant des clés préfixées par `MYBING_` (par exemple, `MYBING_UET_ID`, `MYBING_CAPI_TOKEN`, `MYBING_TRACKING_MODE`).

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Injecte le JavaScript de base de la balise UET, initialise la gestion du consentement et déclenche les événements `PageView`. |
| `displayOrderConfirmation` | Sur la page de confirmation de commande après un achat réussi. | Déclenche les événements `Purchase` pour la balise UET et l'API de Conversions, y compris les détails de la commande. |
| `actionFrontControllerSetMedia` | Lorsqu'un contrôleur frontal définit ses actifs multimédias. | Injecte le JavaScript et le CSS spécifiques au module dans le front-office. |
| `actionCartSave` | Lorsqu'un produit est ajouté ou retiré du panier. | Déclenche les événements `AddToCart` ou `RemoveFromCart`. |
| `actionProductAdd` | Lorsqu'un produit est ajouté au panier (spécifique à certains thèmes/modules). | Hook alternatif ou supplémentaire pour les événements `AddToCart`. |
| `actionProductUpdate` | Lorsqu'un produit est mis à jour dans le Back Office. | Potentiellement utilisé par le `Catalog Doctor` pour réévaluer la qualité des données produit. |
| `actionObjectProductUpdateAfter` | Après la mise à jour d'un `ObjectModel` de produit. | Similaire à `actionProductUpdate`, pour les vérifications de qualité des données ou l'invalidation du cache. |
| `actionObjectOrderAddAfter` | Après l'ajout d'un `ObjectModel` de commande. | Déclenche les événements `Purchase` côté serveur via l'API de Conversions, assurant un suivi robuste. |
| `actionObjectOrderUpdateAfter` | Après la mise à jour d'un `ObjectModel` de commande. | Potentiellement pour suivre les changements de statut de commande (par exemple, remboursement, annulation) si configuré dans Microsoft Ads. |
| `displayProductExtraContent` | Sur la page produit, souvent sous le contenu principal. | Peut être utilisé pour injecter des scripts de suivi spécifiques au produit ou des données pour les événements `ViewItem`. |
| `displayFooter` | À la fin de la section `<body>` de chaque page du front-office. | Peut être utilisé pour le chargement différé de scripts ou des éléments de suivi supplémentaires. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration définit ses actifs multimédias. | Injecte le JavaScript et le CSS spécifiques au module dans le Back Office pour la page de configuration. |
| `actionAdminMybingAjaxController` | Hook personnalisé pour `AdminMybingAjaxController` afin de gérer des actions AJAX spécifiques. | Utilisé en interne pour les mises à jour dynamiques et la récupération de données dans les onglets de diagnostic du module. |
| `actionModuleInstall` | Lors de l'installation du module. | Effectue la configuration initiale, crée les entrées de configuration et enregistre les hooks. |
| `actionModuleUninstall` | Lors de la désinstallation du module. | Nettoie les entrées de configuration et désenregistre les hooks. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel des développeurs, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question concernant la fonctionnalité du module.
