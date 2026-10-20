---
title: "Pinterest Tag & Conversions API - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Pinterest Tag & Conversions API par MyPresta.eu."
sidebar:
  label: "Pinterest Tag & Conversions API - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Pinterest Tag & Conversions API sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/pinterest-tag-conversions-api.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/pinterest-tag-conversions-api/)
>
> ---


# Pinterest Tag & Conversions API

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL). Votre serveur doit être capable d'effectuer des requêtes HTTP sortantes vers les points de terminaison de l'API de Pinterest.

## 2. Présentation complète de la configuration (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est le centre principal pour configurer votre suivi Pinterest. Vous trouverez diverses sections et onglets pour gérer votre Tag Pinterest, l'API de Conversions et la qualité des données.

#### Paramètres généraux et mode de suivi

- **ID du Tag Pinterest (Requis)**

  - **Ce que fait ce paramètre :** C'est votre identifiant unique fourni par Pinterest. Il indique à Pinterest à quel compte publicitaire appartiennent les données de votre site web.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est saisi :* Permet au module d'envoyer des données à votre compte publicitaire Pinterest. Sans cela, aucun suivi ne peut avoir lieu.
    - *Lorsqu'il est vide :* Le module ne peut envoyer aucune donnée à Pinterest.
  - **Valeur recommandée :** Votre ID de Tag Pinterest. Vous pouvez le trouver dans votre Gestionnaire d'annonces Pinterest sous "Annonces" > "Conversions" > "Tag Pinterest".
  - **Scénario / exemple de marchand :** Vous venez de créer un compte Pinterest Ads et devez y lier votre boutique. Copiez l'ID du Tag de Pinterest et collez-le ici.
- **Mode de suivi**

  - **Ce que fait ce paramètre :** Détermine comment votre boutique envoie des données à Pinterest. Vous pouvez choisir entre le Tag Pinterest traditionnel (côté navigateur), l'API de Conversions plus robuste (côté serveur), ou une combinaison des deux.
  - **Effet de la modification de ce paramètre :**
    - *Tag Pinterest (côté navigateur) :* Les données sont envoyées directement depuis le navigateur du client. C'est plus simple mais peut être affecté par les bloqueurs de publicités ou les paramètres de confidentialité du navigateur.
    - *API de Conversions (côté serveur) :* Les données sont envoyées directement depuis votre serveur PrestaShop à Pinterest. C'est plus fiable et moins sujet au blocage, offrant une meilleure précision des données.
    - *Les deux (Hybride avec déduplication) :* Les données sont envoyées via les deux méthodes. Le module ajoute automatiquement un `event_id` unique à chaque événement, permettant à Pinterest d'identifier et d'ignorer les événements en double, assurant une couverture maximale des données sans surcompter.
  - **Valeur recommandée :** **Les deux (Hybride avec déduplication)** pour le suivi le plus fiable et le plus complet.
  - **Scénario / exemple de marchand :** Vous voulez vous assurer que vos campagnes Pinterest sont aussi précises que possible, même avec l'augmentation des mesures de confidentialité. Choisir "Les deux" offre le meilleur des deux mondes.

#### Paramètres de l'API de Conversions (CAPI) (Visibles si le mode CAPI ou Les deux est sélectionné)

- **Jeton d'accès à l'API de Conversions (Requis pour CAPI)**

  - **Ce que fait ce paramètre :** C'est un jeton sécurisé qui authentifie votre serveur lors de l'envoi de données directement à l'API de Conversions de Pinterest. C'est comme un mot de passe pour que votre serveur puisse communiquer avec Pinterest.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est saisi :* Permet à votre serveur d'envoyer des données via l'API de Conversions.
    - *Lorsqu'il est vide :* Le suivi de l'API de Conversions ne fonctionnera pas, même s'il est sélectionné comme mode de suivi.
  - **Valeur recommandée :** Votre Jeton d'accès à l'API de Conversions Pinterest. Générez-le dans votre Gestionnaire d'annonces Pinterest sous "Annonces" > "Conversions" > "API de Conversions".
  - **Scénario / exemple de marchand :** Vous avez décidé d'utiliser l'API de Conversions pour un suivi plus fiable. Vous générerez ce jeton dans Pinterest et le collerez ici.
- **Activer la correspondance améliorée pour CAPI**

  - **Ce que fait ce paramètre :** Lorsqu'il est activé, le module envoie des informations client supplémentaires (comme l'e-mail, le numéro de téléphone, le nom, l'adresse – toutes hachées pour la confidentialité) avec les événements de l'API de Conversions. Cela aide Pinterest à faire correspondre les événements à des utilisateurs spécifiques plus précisément, même s'ils ne sont pas connectés à Pinterest.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Améliore la précision de la correspondance des événements sur Pinterest, ce qui conduit à un meilleur ciblage d'audience et à une meilleure optimisation des campagnes.
    - *Lorsqu'il est désactivé :* Seules les données d'événement de base sont envoyées, ce qui peut réduire la précision de la correspondance.
  - **Valeur recommandée :** **OUI**. Cela améliore considérablement la qualité des données et les performances des annonces.
  - **Scénario / exemple de marchand :** Vous voulez vous assurer que Pinterest peut attribuer avec précision les ventes à vos annonces, même si les clients utilisent différents appareils ou navigateurs. La correspondance améliorée aide à combler ces lacunes.

#### Confidentialité des données et consentement

- **Intégrer avec le module de consentement aux cookies**
  - **Ce que fait ce paramètre :** Si vous utilisez un module de consentement aux cookies distinct (par exemple, un module de conformité GDPR), l'activation de cette option garantit que le suivi Pinterest ne se déclenche qu'après que le client a donné son consentement.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le suivi Pinterest respectera les choix de consentement du client de votre module de cookies. Si le consentement est refusé, aucune donnée Pinterest n'est envoyée.
    - *Lorsqu'il est désactivé :* Le suivi Pinterest se déclenchera quelles que soient les autres configurations de consentement aux cookies, ce qui pourrait entraîner des problèmes de conformité.
  - **Valeur recommandée :** **OUI** si vous utilisez un module de consentement aux cookies. **NON** si vous n'en utilisez pas ou si vous gérez le consentement manuellement.
  - **Scénario / exemple de marchand :** Votre boutique doit être conforme au GDPR. En activant cela, vous vous assurez que le suivi Pinterest respecte les préférences de confidentialité de vos clients.

#### Paramètres avancés et débogage

- **Activer le mode débogage**

  - **Ce que fait ce paramètre :** Active un mode spécial qui affiche des informations détaillées sur les événements Pinterest envoyés, directement dans la console de développement de votre navigateur. C'est utile pour vérifier que votre suivi fonctionne correctement.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les développeurs et les webmasters peuvent voir les données d'événements Pinterest en temps réel dans la console du navigateur. Cela ne devrait **jamais** être activé sur une boutique de production en direct pour une visualisation publique générale.
    - *Lorsqu'il est désactivé :* Aucune information de débogage n'est affichée.
  - **Valeur recommandée :** **NON** pour une boutique de production en direct. **OUI** uniquement pendant la configuration et les tests.
  - **Scénario / exemple de marchand :** Vous venez d'installer le module et souhaitez confirmer que les événements "Ajouter au panier" se déclenchent correctement. Vous activez le mode débogage, ajoutez un produit à votre panier et vérifiez la console du navigateur pour les données d'événement.
- **Domaines de liaison (pour le suivi inter-domaines)**

  - **Ce que fait ce paramètre :** Si votre boutique utilise plusieurs sous-domaines ou redirige vers un autre domaine pendant le processus de paiement (par exemple, un domaine de passerelle de paiement distinct), vous pouvez lister ces domaines ici. Cela aide Pinterest à attribuer correctement les actions sur différents domaines.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque des domaines sont listés :* Pinterest peut maintenir la continuité du suivi sur ces domaines, évitant ainsi la perte de données.
    - *Lorsqu'il est vide :* Le suivi pourrait être interrompu si les clients naviguent entre différents domaines pendant leur parcours, ce qui entraînerait des données incomplètes.
  - **Valeur recommandée :** Laissez vide, sauf si vous avez des besoins spécifiques de suivi inter-domaines. Si c'est le cas, entrez chaque domaine sur une nouvelle ligne.
  - **Scénario / exemple de marchand :** Votre boutique principale est `shop.example.com`, mais votre blog est `blog.example.com` et vous souhaitez suivre les utilisateurs qui visitent les deux. Vous ajouteriez `blog.example.com` ici.

#### Qualité des données et score de santé (Sections d'information)

Ces sections fournissent des informations sur votre configuration de suivi et ne sont pas des paramètres de configuration directs, mais plutôt des rapports générés par le module.

- **Score de santé** : Affiche un score global indiquant la qualité et l'exhaustivité de votre configuration de suivi Pinterest. Un score plus élevé signifie des données plus fiables.
- **Docteur de catalogue** : Aide à identifier les problèmes potentiels avec les données de votre catalogue de produits qui pourraient affecter la capacité de Pinterest à faire correspondre les produits pour les annonces dynamiques.
- **Coach de qualité des données** : Fournit des recommandations et des avertissements sur vos données d'événements, tels que des paramètres manquants ou un formatage incorrect, pour vous aider à améliorer la précision.
- **Statistiques en direct** : Affiche les événements récents envoyés à Pinterest, vous permettant de surveiller l'activité en temps réel.
- **Événements récents** : Un journal des événements les plus récents traités par le module.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 AdminMypinterestAjaxController (Back Office > Modules > Pinterest Tag & Conversions API > Statistiques en direct / Score de santé / Coach de qualité des données)

Ce contrôleur alimente les sections dynamiques et interactives de la page de configuration principale du module, spécifiquement pour des fonctionnalités comme les Statistiques en direct, le Score de santé et le Coach de qualité des données.

- **Nom de l'écran et emplacement du menu :** Ce ne sont pas des éléments de menu autonomes mais plutôt des panneaux interactifs au sein de la page de configuration principale du module (Back Office > Modules > Gestionnaire de modules > Configurer "Pinterest Tag & Conversions API").
- **Actions et paramètres disponibles :** Ce contrôleur gère les requêtes AJAX pour récupérer et afficher les données et rapports en temps réel.
  - **Statistiques en direct** : Affiche un flux en temps réel d'événements (par exemple, PageView, AddToCart, Purchase) tels qu'ils sont envoyés à Pinterest, y compris s'ils ont été envoyés via le Tag, CAPI ou les deux. Cela vous permet de vérifier rapidement que les événements se déclenchent.
  - **Score de santé** : Affiche un résumé de la santé de votre configuration de suivi, mettant en évidence les domaines à améliorer (par exemple, jeton CAPI manquant, faible qualité de correspondance des événements).
  - **Coach de qualité des données** : Offre des recommandations spécifiques pour améliorer la qualité des données envoyées à Pinterest, telles que s'assurer que tous les paramètres requis sont inclus pour chaque type d'événement.
  - **Docteur de catalogue** : Analyse votre flux de catalogue de produits (si vous en utilisez un pour Pinterest) et signale les problèmes potentiels qui pourraient entraver les annonces de produits dynamiques.
- **Effet des modifications :** L'interaction avec ces panneaux (par exemple, l'actualisation des Statistiques en direct) déclenche des appels AJAX qui récupèrent les dernières données de votre serveur ou de l'API de Pinterest, fournissant des informations à jour sans recharger toute la page.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vérifiez régulièrement le Score de santé et le Coach de qualité des données pour vous assurer que votre suivi reste optimal. Utilisez les Statistiques en direct pendant les tests ou après avoir apporté des modifications pour vérifier que les événements se déclenchent correctement.

#### 2.2.2 index.php (mypinterest/controllers/admin/index.php)

Ce fichier est un espace réservé et sert généralement de mesure de sécurité pour empêcher la liste directe des répertoires dans les dossiers d'administration de PrestaShop. Il ne représente pas un écran configurable ou une entité gérée en soi.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | ID du Tag Pinterest | Votre ID de Tag | Lie votre boutique à votre compte publicitaire Pinterest pour le suivi. |
| Configuration du module | Mode de suivi | Les deux (Hybride) | Envoie les données via le navigateur (Tag) et le serveur (CAPI) pour une fiabilité maximale. |
| Configuration du module | Jeton d'accès à l'API de Conversions | Votre Jeton CAPI | Authentifie l'envoi de données côté serveur à Pinterest. |
| Configuration du module | Activer la correspondance améliorée pour CAPI | OUI | Améliore la précision de la correspondance des événements sur Pinterest pour un meilleur ciblage. |
| Configuration du module | Intégrer avec le module de consentement aux cookies | OUI (si applicable) | Garantit que le suivi Pinterest respecte les choix de confidentialité des clients. |
| Configuration du module | Activer le mode débogage | NON (sur une boutique en direct) | Affiche des informations de suivi détaillées dans la console du navigateur pour les tests. |
| Configuration du module | Domaines de liaison | Vide (sauf si nécessaire) | Maintient la continuité du suivi sur plusieurs domaines liés. |
| Panneau Statistiques en direct | N/A | N/A | Affiche les événements Pinterest en temps réel pour vérification. |
| Panneau Score de santé | N/A | N/A | Fournit une évaluation globale de la qualité de votre configuration de suivi. |
| Panneau Coach de qualité des données | N/A | N/A | Offre des recommandations pour améliorer la précision des données d'événements. |
| Panneau Docteur de catalogue | N/A | N/A | Identifie les problèmes dans votre catalogue de produits pour les annonces Pinterest. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q1 : J'ai installé le module, mais je ne vois aucune donnée dans mon Gestionnaire d'annonces Pinterest. Que dois-je faire ?**
R1 : Tout d'abord, vérifiez que votre **ID de Tag Pinterest** et votre **Jeton d'accès à l'API de Conversions** (si vous utilisez CAPI) sont correctement saisis dans la configuration du module. Assurez-vous qu'il n'y a pas de fautes de frappe. Ensuite, videz le cache de votre PrestaShop (**Paramètres avancés > Performances > Vider le cache**). Ensuite, visitez le front office de votre boutique et effectuez quelques actions (consulter un produit, ajouter au panier, effectuer un achat test). Si le "Mode débogage" est activé dans le module, vérifiez la console de développement de votre navigateur pour les événements Pinterest. Si aucune donnée n'apparaît toujours, vérifiez la configuration de votre Gestionnaire d'annonces Pinterest et assurez-vous que votre compte est actif.

**Q2 : Mon Tag Pinterest semble être bloqué par les bloqueurs de publicités. Comment puis-je m'assurer que mes données sont toujours collectées ?**
R2 : C'est précisément pourquoi l'API de Conversions (CAPI) est si importante ! Assurez-vous que votre "Mode de suivi" est défini sur **"Les deux (Hybride avec déduplication)"**. De cette façon, même si le Tag Pinterest côté navigateur est bloqué, votre serveur PrestaShop enverra toujours les données d'événement directement à Pinterest via l'API de Conversions, garantissant que votre suivi reste robuste.

**Q3 : Comment ce module gère-t-il la confidentialité des clients et le GDPR/CCPA ?**
R3 : Le module inclut une option pour **"Intégrer avec le module de consentement aux cookies"**. Si vous avez un module de consentement aux cookies distinct installé (ce qui est fortement recommandé pour la conformité à la confidentialité), activez ce paramètre. Le suivi Pinterest ne s'activera alors qu'une fois que le client aura donné son consentement via votre solution de consentement existante. Le module hache également les données client sensibles avant de les envoyer via la correspondance améliorée pour CAPI, ajoutant une autre couche de confidentialité.

**Q4 : Je vois un "Score de santé" faible ou des avertissements dans le "Coach de qualité des données". Que signifient-ils ?**
R4 : Ces sections sont conçues pour vous aider à optimiser votre suivi. Un Score de santé faible ou des avertissements indiquent généralement que certains paramètres de données peuvent être manquants ou mal formatés, ou que votre configuration n'est pas entièrement optimisée (par exemple, CAPI non activé). Examinez les recommandations spécifiques fournies dans les panneaux "Coach de qualité des données" et "Docteur de catalogue". Ils vous guideront sur la façon d'améliorer la qualité de vos données, ce qui a un impact direct sur l'efficacité de vos annonces Pinterest.

**Q5 : Ce module va-t-il ralentir mon site web ?**
R5 : Le module est conçu pour être hautement optimisé. Le Tag Pinterest côté navigateur est chargé de manière asynchrone, ce qui signifie qu'il ne bloque pas le chargement de votre page. Les appels de l'API de Conversions côté serveur se produisent en arrière-plan et n'ont pas d'impact sur les temps de chargement des pages du front office. Vous ne devriez pas ressentir de ralentissements notables dus à ce module.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module `Pinterest Tag & Conversions API` (`mypinterest`) implémente une stratégie de suivi hybride pour Pinterest, combinant le Tag Pinterest traditionnel côté navigateur avec l'API de Conversions (CAPI) côté serveur. Il suit le modèle MVC de PrestaShop lorsque cela est applicable, en tirant parti des hooks pour l'injection d'événements côté front-office et des contrôleurs d'administration dédiés pour la configuration et le reporting des données. Les composants architecturaux clés incluent :

- **Fabrique de traqueurs** : Instancie dynamiquement le mécanisme de suivi approprié (Tag, CAPI ou Hybride) en fonction de la configuration du module.
- **Mappage d'événements** : Traduit les événements internes de PrestaShop (par exemple, `actionCartSave`, `actionValidateOrder`) en noms d'événements et paramètres standard de Pinterest.
- **Outils de qualité des données** : Classes dédiées pour le score de santé, les diagnostics de catalogue et le coaching de qualité des données, fournissant des informations exploitables dans le back office.
- **Gestion du consentement** : Intégration avec des modules de consentement aux cookies tiers pour assurer la conformité GDPR/CCPA.
- **Statistiques en direct** : Surveillance des événements en temps réel via AJAX pour le débogage et la vérification.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `controllers/front/ajax.php`
  - **Nom de la classe et classe parente** : `MypinterestAjaxModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité** : Gère les requêtes AJAX du front office, principalement pour l'envoi d'événements côté serveur (CAPI) qui sont déclenchés par des actions côté client mais doivent être traités en toute sécurité sur le serveur. Cela peut inclure des événements difficiles à suivre uniquement côté client ou à des fins de déduplication. Il reçoit probablement les données d'événement de `mypinterest.js` et les transmet au client CAPI.
- `controllers/front/cron.php`
  - **Nom de la classe et classe parente** : `MypinterestCronModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité** : Fournit un point de terminaison pour une tâche cron. Cela pourrait être utilisé pour des tâches telles que l'envoi d'événements CAPI différés, la synchronisation des catalogues de produits ou l'exécution de vérifications périodiques de la qualité des données sans interaction directe de l'utilisateur.
- `controllers/front/index.php`
  - **Nom de la classe et classe parente** : `MypinterestIndexModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité** : Un contrôleur frontal de substitution, généralement utilisé pour empêcher la liste directe des répertoires ou comme solution de repli pour les routes spécifiques au module qui ne correspondent pas à d'autres contrôleurs. Dans ce module, il sert probablement un objectif minimal ou redirige.

#### Contrôleurs d'administration Back-Office

- `controllers/admin/AdminMypinterestAjaxController.php`
  - **Nom de la classe et classe parente** : `AdminMypinterestAjaxController` étend `ModuleAdminController`.
  - **Nom de l'onglet et entité gérée** : Ce contrôleur n'est pas directement exposé comme un onglet de menu mais sert de point de terminaison AJAX pour la page de configuration du module. Il gère les requêtes de données dynamiques affichées dans les panneaux "Statistiques en direct", "Score de santé", "Coach de qualité des données" et "Docteur de catalogue" au sein de la configuration principale du module. Il récupère les journaux d'événements en temps réel, les métriques de santé et les rapports de diagnostic.
- `controllers/admin/index.php`
  - **Nom de la classe et classe parente** : Pas un contrôleur fonctionnel.
  - **Nom de l'onglet et entité gérée** : C'est un espace réservé de sécurité, empêchant la liste des répertoires.

### 4.3 Classes et modèles principaux (`classes/`)

- `classes/autoload.php` : Fichier d'autoload PrestaShop standard, garantissant que les classes du module sont chargées correctement.
- `classes/MypinterestCapiClient.php` :
  - **Table de base de données** : Aucune directement.
  - **Étend** : Pas de `ObjectModel`.
  - **Méthodes publiques clés** : Gère les requêtes HTTP réelles vers le point de terminaison de l'API de Conversions de Pinterest. Encapsule la logique de construction des charges utiles CAPI, y compris les données d'événement, les données utilisateur et les jetons d'accès.
- `classes/MypinterestCapiTracker.php` :
  - **Table de base de données** : Aucune.
  - **Étend** : Implémente `MypinterestTrackerInterface`.
  - **Méthodes publiques clés** : Gère la logique de suivi des événements spécifiquement via l'API de Conversions. Formate les données pour CAPI, gère la déduplication des événements (`event_id`) et délègue l'envoi à `MypinterestCapiClient`.
- `classes/MypinterestCatalogDoctor.php` :
  - **Table de base de données** : Aucune.
  - **Étend** : Pas de `ObjectModel`.
  - **Méthodes publiques clés** : Contient la logique pour analyser les données de produit (par exemple, à partir de flux de produits ou d'objets `Product`) et identifier les problèmes potentiels qui pourraient affecter la capacité de Pinterest à faire correspondre les produits pour les annonces dynamiques. Fournit des rapports de diagnostic.
- `classes/MypinterestConsent.php` :
  - **Table de base de données** : Aucune.
  - **Étend** : Pas de `ObjectModel`.
  - **Méthodes publiques clés** : Gère l'intégration avec des modules de consentement aux cookies tiers. Vérifie l'état du consentement de l'utilisateur et détermine si le suivi Pinterest doit être activé ou désactivé en fonction du consentement.
- `classes/MypinterestCurrencyHelper.php` :
  - **Table de base de données** : Aucune.
  - **Étend** : Pas de `ObjectModel`.
  - **Méthodes publiques clés** : Classe utilitaire pour la gestion du formatage et de la conversion des devises, garantissant que les événements Pinterest envoient les valeurs de devise dans le format correct.
- `classes/MypinterestDataQualityCoach.php` :
  - **Table de base de données** : Aucune.
  - **Étend** : Pas de `ObjectModel`.
  - **Méthodes publiques clés** : Analyse la qualité des données d'événement envoyées (par exemple, présence des paramètres requis, types de données corrects) et fournit des recommandations d'amélioration.
- `classes/MypinterestEventId.php` :
  - **Table de base de données** : Aucune.
  - **Étend** : Pas de `ObjectModel`.
  - **Méthodes publiques clés** : Génère et gère des valeurs `event_id` uniques pour la déduplication des événements, crucial pour le suivi hybride.
- `classes/MypinterestEventMap.php` :
  - **Table de base de données** : Aucune.
  - **Étend** : Pas de `ObjectModel`.
  - **Méthodes publiques clés** : Définit le mappage entre les actions/données de PrestaShop et les noms d'événements standard de Pinterest ainsi que leurs paramètres requis/recommandés.
- `classes/MypinterestEvents.php` :
  - **Table de base de données** : Aucune.
  - **Étend** : Pas de `ObjectModel`.
  - **Méthodes publiques clés** : Centralise la logique de déclenchement et de gestion de divers événements Pinterest (PageView, AddToCart, Purchase, etc.) à travers le module.
- `classes/MypinterestHealthScore.php` :
  - **Table de base de données** : Aucune.
  - **Étend** : Pas de `ObjectModel`.
  - **Méthodes publiques clés** : Calcule un "score de santé" global pour la configuration de suivi Pinterest basé sur divers facteurs comme la présence du jeton CAPI, le mode de suivi et la qualité des données.
- `classes/MypinterestHybridTracker.php` :
  - **Table de base de données** : Aucune.
  - **Étend** : Implémente `MypinterestTrackerInterface`.
  - **Méthodes publiques clés** : Orchestre le suivi lorsque le mode "Les deux" est sélectionné. Appelle à la fois `MypinterestTagTracker` et `MypinterestCapiTracker`, garantissant que `event_id` est cohérent pour la déduplication.
- `classes/MypinterestLiveStats.php` :
  - **Table de base de données** : Stocke les journaux d'événements récents (par exemple, dans `ps_configuration` ou une table personnalisée).
  - **Étend** : Pas de `ObjectModel`.
  - **Méthodes publiques clés** : Enregistre et récupère les événements Pinterest récents pour affichage dans le panneau "Statistiques en direct" du back office.
- `classes/MypinterestProductIdResolver.php` :
  - **Table de base de données** : Aucune.
  - **Étend** : Pas de `ObjectModel`.
  - **Méthodes publiques clés** : Aide à résoudre et à formater les ID de produit pour correspondre aux exigences du catalogue de Pinterest, garantissant une correspondance précise des produits pour les annonces dynamiques.
- `classes/MypinterestPropertyRules.php` :
  - **Table de base de données** : Aucune.
  - **Étend** : Pas de `ObjectModel`.
  - **Méthodes publiques clés** : Définit les règles et les validations pour les propriétés d'événement Pinterest, garantissant que les données envoyées à Pinterest respectent leurs spécifications.
- `classes/MypinterestTagTracker.php` :
  - **Table de base de données** : Aucune.
  - **Étend** : Implémente `MypinterestTrackerInterface`.
  - **Méthodes publiques clés** : Gère la logique d'injection du script du Tag Pinterest côté navigateur et de déclenchement des événements via les appels `pintrk()`.
- `classes/MypinterestTrackerFactory.php` :
  - **Table de base de données** : Aucune.
  - **Étend** : Pas de `ObjectModel`.
  - **Méthodes publiques clés** : Une classe de type fabrique responsable de la création et du retour de l'instance de traqueur correcte (`MypinterestTagTracker`, `MypinterestCapiTracker` ou `MypinterestHybridTracker`) basée sur la configuration du module.
- `classes/MypinterestTrackerInterface.php` :
  - **Table de base de données** : Aucune.
  - **Étend** : Pas de `ObjectModel`.
  - **Méthodes publiques clés** : Définit l'interface commune pour tous les traqueurs Pinterest, garantissant la cohérence dans la façon dont les événements sont gérés, quelle que soit la méthode de suivi sous-jacente.
- `classes/MypinterestUserData.php` :
  - **Table de base de données** : Aucune.
  - **Étend** : Pas de `ObjectModel`.
  - **Méthodes publiques clés** : Collecte et formate les données client (e-mail, téléphone, adresse, etc.) pour la "Correspondance améliorée", en s'assurant qu'elles sont hachées et conformes aux exigences de Pinterest.

### 4.4 Actifs JavaScript (`views/js/`)

- `mypinterest/views/js/mypinterest-admin.js` :
  - **Portée** : Back-office.
  - **Description** : Contient le JavaScript pour l'interface d'administration du module. Gère les appels AJAX à `AdminMypinterestAjaxController` pour récupérer les statistiques en direct, les scores de santé et d'autres contenus dynamiques. Gère les interactions de l'interface utilisateur sur la page de configuration.
- `mypinterest/views/js/mypinterest-debug.js` :
  - **Portée** : Front-office.
  - **Description** : Chargé lorsque le "Mode débogage" est activé. Fournit une journalisation de la console et des superpositions visuelles pour afficher les données d'événement Pinterest au fur et à mesure de leur envoi, aidant au dépannage et à la vérification.
- `mypinterest/views/js/mypinterest-ghost.js` :
  - **Portée** : Front-office.
  - **Description** : Potentiellement lié au suivi "fantôme" ou différé, ou à un mécanisme de secours pour les événements qui pourraient ne pas se déclencher immédiatement. Pourrait être utilisé pour des types d'événements spécifiques ou des retards liés au consentement.
- `mypinterest/views/js/mypinterest-live.js` :
  - **Portée** : Back-office.
  - **Description** : Spécifiquement pour le panneau "Statistiques en direct". Gère la mise à jour en temps réel des journaux d'événements, interrogeant le serveur via AJAX pour afficher les événements Pinterest récents.
- `mypinterest/views/js/mypinterest-tcf.js` :
  - **Portée** : Front-office.
  - **Description** : Gère l'intégration avec les modules de consentement aux cookies compatibles avec le Transparency and Consent Framework (TCF). Écoute les événements de consentement et active/désactive le suivi Pinterest en conséquence.
- `mypinterest/views/js/mypinterest-wizard.js` :
  - **Portée** : Back-office.
  - **Description** : Alimente la fonctionnalité de l'assistant de configuration au sein de la configuration du module. Guide le marchand à travers les étapes de configuration initiales, validant les entrées et fournissant des commentaires.
- `mypinterest/views/js/mypinterest.js` :
  - **Portée** : Front-office.
  - **Description** : Le JavaScript principal du front-office pour le Tag Pinterest. Injecte la bibliothèque `pintrk()`, initialise le Tag Pinterest avec l'ID du Tag et déclenche les événements standard (PageView, AddToCart, Checkout, Purchase) basés sur les événements DOM ou les hooks JavaScript de PrestaShop. Également responsable de la génération de l'`event_id` pour la déduplication et potentiellement de l'envoi d'appels AJAX à `controllers/front/ajax.php` pour les événements CAPI.

### 4.5 Feuilles de style CSS (`views/css/`)

- `mypinterest/views/css/mypinterest-admin.css` :
  - **Portée** : Style du formulaire d'administration du back-office.
  - **Description** : Styles pour la page de configuration du module, y compris la disposition des onglets, des champs de saisie, des boutons et des panneaux dynamiques pour les Statistiques en direct, le Score de santé, etc.
  - **Sélecteurs de classe CSS clés** : `.mypinterest-config`, `.mypinterest-tab-content`, `.mypinterest-health-score`, `.mypinterest-live-stats`.
- `mypinterest/views/css/mypinterest-debug.css` :
  - **Portée** : Style client du front-office (uniquement lorsque le mode débogage est actif).
  - **Description** : Fournit un style pour la superposition de débogage ou la sortie de la console, rendant les informations de débogage plus lisibles pour les développeurs.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)

- `mypinterest/views/templates/hook/capi-pageview.tpl` :
  - **Hook** : Probablement `displayHeader` ou `displayFooter`.
  - **Sortie** : Rend un élément caché ou un petit script pour déclencher un événement PageView côté serveur via CAPI, souvent utilisé pour le suivi du chargement initial de la page ou comme solution de secours.
- `mypinterest/views/templates/hook/debug.tpl` :
  - **Hook** : `displayHeader` ou `displayFooter` (rendu conditionnellement).
  - **Sortie** : Injecte le script `mypinterest-debug.js` et potentiellement une structure HTML de superposition de débogage lorsque le mode débogage est actif.
- `mypinterest/views/templates/hook/displayOrderConfirmation.tpl` :
  - **Hook** : `displayOrderConfirmation`.
  - **Sortie** : Rend le script d'événement "Achat" de Pinterest, y compris les détails de la commande (valeur, devise, ID de commande, produits) pour le Tag Pinterest et CAPI (via appel AJAX).
- `mypinterest/views/templates/hook/ghost.tpl` :
  - **Hook** : `displayHeader` ou `displayFooter`.
  - **Sortie** : Potentiellement lié au script `mypinterest-ghost.js`, utilisé pour des mécanismes de suivi spécifiques, éventuellement différés ou en arrière-plan.
- `mypinterest/views/templates/hook/header.tpl` :
  - **Hook** : `displayHeader`.
  - **Sortie** : Injecte le code de base principal du Tag Pinterest (`pintrk()`) et le script `mypinterest.js`. Initialise le Tag Pinterest avec l'ID du Tag et déclenche potentiellement l'événement "PageView" initial.
- `mypinterest/views/templates/hook/payment.tpl` :
  - **Hook** : `displayPayment` ou `displayPaymentTop`.
  - **Sortie** : Pourrait être utilisé pour suivre l'initiation du processus de paiement ou la sélection d'un mode de paiement, déclenchant potentiellement un événement "Checkout" ou "InitiateCheckout".
- `mypinterest/views/templates/hook/product-details.tpl` :
  - **Hook** : `displayProductButtons` ou `displayFooterProduct`.
  - **Sortie** : Rend le JavaScript pour suivre les événements "ViewContent" lorsqu'une page de produit est chargée, y compris l'ID du produit, le nom, le prix et la catégorie. Inclut également probablement la logique pour les événements "Ajouter au panier".

#### Modèles d'administration (`views/templates/admin/`)

- `mypinterest/views/templates/admin/consent-guide.tpl` : Affiche des informations et des conseils sur l'intégration avec les modules de consentement aux cookies.
- `mypinterest/views/templates/admin/doctor.tpl` : Rend le panneau "Docteur de catalogue", affichant les diagnostics pour les données du catalogue de produits.
- `mypinterest/views/templates/admin/dq.tpl` : Rend le panneau "Coach de qualité des données", fournissant des recommandations pour améliorer les données d'événements.
- `mypinterest/views/templates/admin/health.tpl` : Rend le panneau "Score de santé", affichant la santé globale du suivi.
- `mypinterest/views/templates/admin/linker-domains.tpl` : Modèle pour le champ de saisie "Domaines de liaison".
- `mypinterest/views/templates/admin/live-maintain.tpl` : Peut-être un message de maintenance ou d'état pour la fonctionnalité de statistiques en direct.
- `mypinterest/views/templates/admin/live.tpl` : Rend le panneau "Statistiques en direct", affichant les journaux d'événements en temps réel.
- `mypinterest/views/templates/admin/mode-context.tpl` : Fournit des informations contextuelles sur le mode de suivi sélectionné.
- `mypinterest/views/templates/admin/mode-note-both.tpl` : Note/explication spécifique pour le mode de suivi "Les deux (Hybride)".
- `mypinterest/views/templates/admin/mode-note-capi.tpl` : Note/explication spécifique pour le mode de suivi "API de Conversions".
- `mypinterest/views/templates/admin/mode-note-tag.tpl` : Note/explication spécifique pour le mode de suivi "Tag Pinterest".
- `mypinterest/views/templates/admin/mode-picker.tpl` : Rend les boutons radio ou la liste déroulante pour la sélection du "Mode de suivi".
- `mypinterest/views/templates/admin/properties-list.tpl` : Affiche une liste des propriétés d'événement et leur statut (par exemple, requis, recommandé).
- `mypinterest/views/templates/admin/recent-events.tpl` : Rend un tableau ou une liste des événements récents pour le panneau "Statistiques en direct".
- `mypinterest/views/templates/admin/tabs.tpl` : Rend la structure de navigation par onglets pour la page de configuration du module.
- `mypinterest/views/templates/admin/tag-chips.tpl` : Probablement pour afficher les ID de Tag Pinterest dans un format "puce" visuellement attrayant.
- `mypinterest/views/templates/admin/tag-ids.tpl` : Rend les champs de saisie pour l'ID du Tag Pinterest et le Jeton d'accès CAPI.
- `mypinterest/views/templates/admin/wizard.tpl` : Rend l'interface de l'assistant de configuration étape par étape.

#### Modèles Front-office (`views/templates/front/`)

- `mypinterest/views/templates/front/index.tpl` : Un modèle de substitution, probablement non utilisé pour le rendu direct mais comme valeur par défaut pour le `MypinterestIndexModuleFrontController`.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module utilise principalement `ps_configuration` pour stocker ses paramètres (par exemple, `MYPINTEREST_TAG_ID`, `MYPINTEREST_TRACKING_MODE`, `MYPINTEREST_CAPI_TOKEN`).
  - Il peut également utiliser une table personnalisée (par exemple, `ps_mypinterest_events_log`) pour stocker les données d'événements récents pour la fonctionnalité "Statistiques en direct", bien que cela puisse également être stocké dans `ps_configuration` sous forme de données sérialisées. (Aucun fichier SQL explicite trouvé, donc probablement `ps_configuration` ou création dynamique de table).
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Injecte le JavaScript de base du Tag Pinterest, `mypinterest.js`, et potentiellement les événements PageView initiaux. |
| `displayOrderConfirmation` | Sur la page de confirmation de commande après un achat réussi. | Déclenche l'événement "Achat", envoyant des données détaillées de commande et de produit à Pinterest. |
| `displayProductButtons` | Sur la page produit, près du bouton "Ajouter au panier". | Injecte du JavaScript pour suivre les événements "ViewContent" et "Ajouter au panier". |
| `displayFooter` | À la fin de la section `<body>` de chaque page. | Peut être utilisé comme emplacement alternatif ou supplémentaire pour l'injection de scripts, en particulier pour les événements qui n'ont pas besoin de bloquer le rendu de la page. |
| `actionCartSave` | Lorsqu'un panier est mis à jour (par exemple, produit ajouté/supprimé). | Déclenche les événements "AddToCart" ou "RemoveFromCart", souvent gérés côté serveur via CAPI ou côté client via AJAX. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | Déclenche l'événement "Achat" côté serveur via CAPI pour une fiabilité maximale, complétant l'événement `displayOrderConfirmation` côté client. |
| `actionFrontControllerSetMedia` | Lorsqu'un contrôleur frontal définit ses médias (JS/CSS). | Permet au module d'enregistrer ses fichiers JavaScript et CSS du front-office. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration définit ses médias (JS/CSS). | Permet au module d'enregistrer ses fichiers JavaScript et CSS du back-office. |
| `actionObjectProductUpdateAfter` / `actionObjectProductAddAfter` | Après la mise à jour ou l'ajout d'un produit. | Potentiellement utilisé pour la mise à jour des données du catalogue de produits ou le déclenchement de diagnostics de catalogue. |
| `actionObjectProductDeleteAfter` | Après la suppression d'un produit. | Potentiellement utilisé pour la mise à jour des données du catalogue de produits. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module Pinterest Tag & Conversions API, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question concernant la fonctionnalité du module.
