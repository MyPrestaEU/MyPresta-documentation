---
title: "Pièces jointes pour utilisateurs connectés uniquement - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop « Pièces jointes pour utilisateurs connectés uniquement » par MyPresta.eu."
sidebar:
  label: "Pièces jointes pour utilisateurs connectés uniquement - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Attachments for logged users only sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/attachments-for-logged-users-only.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/attachments-for-logged-users-only/)
>
> ---


# Pièces jointes pour utilisateurs connectés uniquement

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement nécessaire.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après avoir installé le module, cliquez sur « Configurer » pour accéder à ses paramètres. C'est l'écran principal où vous contrôlez le comportement du module.

#### **Activer la fonctionnalité**

- **Ce que fait ce paramètre :** C'est l'interrupteur principal du module. Il détermine si la fonctionnalité de restriction des pièces jointes est active ou inactive sur votre boutique.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (« Activé ») :* Le module restreindra activement les téléchargements de pièces jointes de produits aux seuls clients connectés. Les utilisateurs non connectés ne pourront pas télécharger les pièces jointes.
  - *Lorsqu'il est désactivé (« Désactivé ») :* Le module sera inactif. Les pièces jointes de produits se comporteront comme elles le font par défaut dans PrestaShop, ce qui signifie que n'importe qui (connecté ou invité) peut les télécharger.
- **Valeur recommandée :** « Activé » si vous souhaitez restreindre les téléchargements de pièces jointes.
- **Scénario / exemple de marchand :** Si vous souhaitez commencer à exiger des clients qu'ils se connectent pour télécharger des manuels, définissez ce paramètre sur « Activé ». Si vous testez ou souhaitez revenir temporairement au comportement par défaut de PrestaShop, définissez-le sur « Désactivé ».

#### **Télécharger pour les clients uniquement**

- **Ce que fait ce paramètre :** Ce paramètre affine la « fonctionnalité d'activation » en vous permettant de spécifier *quels* clients peuvent télécharger des pièces jointes en fonction de leur historique de commandes.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Seuls les clients qui sont connectés ET qui ont au moins une commande avec un statut sélectionné (voir « Sélectionner les statuts de commande » ci-dessous) pourront télécharger les pièces jointes. Cela ajoute une couche supplémentaire d'exclusivité.
  - *Lorsqu'il est désactivé :* Tout client connecté (quel que soit son historique de commandes) pourra télécharger les pièces jointes, à condition que la « fonctionnalité d'activation » soit activée.
- **Valeur recommandée :** « Désactivé » dans la plupart des cas, permettant à tout client connecté de télécharger. « Activé » si vous souhaitez offrir des pièces jointes comme avantage pour les clients *payants*.
- **Scénario / exemple de marchand :** Vous vendez des logiciels et souhaitez fournir des mises à jour ou des guides premium uniquement aux clients qui ont effectivement acheté le logiciel. Vous activeriez ce paramètre et sélectionneriez « Paiement accepté » dans l'option « Sélectionner les statuts de commande ».

#### **Sélectionner les statuts de commande**

- **Ce que fait ce paramètre :** Cette option n'apparaît que si « Télécharger pour les clients uniquement » est activé. Elle vous permet de choisir quels statuts de commande qualifient un client pour télécharger des pièces jointes. Un client doit avoir au moins une commande avec l'un des statuts sélectionnés pour obtenir l'accès.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'un ou plusieurs statuts sont sélectionnés :* Seuls les clients connectés ayant une commande correspondant à l'un de ces statuts peuvent télécharger les pièces jointes.
  - *Lorsqu'aucun statut n'est sélectionné (et que « Télécharger pour les clients uniquement » est activé) :* Cette configuration pourrait empêcher tout client de télécharger, car aucun statut de commande qualifiant n'est défini. Il est crucial de sélectionner au moins un statut si vous activez « Télécharger pour les clients uniquement ».
- **Valeur recommandée :** Si « Télécharger pour les clients uniquement » est activé, sélectionnez les statuts pertinents comme « Paiement accepté », « Livré » ou « Expédié » pour accorder l'accès aux clients qui ont terminé une commande avec succès.
- **Scénario / exemple de marchand :** Si vous souhaitez donner accès aux pièces jointes uniquement aux clients dont les commandes ont été payées et traitées avec succès, vous sélectionneriez « Paiement accepté » et « Livré ». Cela empêche les clients ayant des commandes en attente ou annulées d'accéder aux fichiers.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer la fonctionnalité | Activé | Interrupteur principal pour activer/désactiver la restriction des pièces jointes. |
| Configuration du module | Télécharger pour les clients uniquement | Désactivé | Si activé, seuls les clients connectés avec des statuts de commande spécifiques peuvent télécharger. |
| Configuration du module | Sélectionner les statuts de commande | (Aucun sélectionné) | Si « Télécharger pour les clients uniquement » est actif, sélectionnez les statuts de commande qui accordent l'accès au téléchargement. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : Mes pièces jointes sont toujours téléchargeables par tout le monde, même après avoir activé le module. Qu'est-ce qui ne va pas ?**
R :

1. **Vérifiez « Activer la fonctionnalité » :** Assurez-vous que le paramètre « Activer la fonctionnalité » sur la page de configuration du module est défini sur « Activé ».
2. **Videz le cache :** PrestaShop utilise la mise en cache. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). Cela résout souvent les problèmes d'affichage après des modifications de configuration du module.
3. **Position du module :** Assurez-vous que le module est correctement accroché. Bien que le module gère cela automatiquement, des conflits de thème peuvent parfois survenir.

**Q : J'ai activé « Télécharger pour les clients uniquement » et sélectionné les statuts de commande, mais mes clients connectés ne peuvent toujours pas télécharger.**
R :

1. **Vérifiez le statut de la commande :** Vérifiez que le client qui tente de télécharger a bien une commande avec l'un des statuts *exacts* que vous avez sélectionnés dans « Sélectionner les statuts de commande ».
2. **Connexion client :** Confirmez que le client est bien connecté à son compte.
3. **Cache :** Videz le cache de votre PrestaShop (Paramètres avancés > Performances).

**Q : Comment traduire les messages affichés aux utilisateurs non connectés ?**
R : Le module devrait s'intégrer au système de traduction de PrestaShop.

1. Allez dans **International > Traductions**.
2. Sélectionnez « Traductions des modules installés ».
3. Choisissez votre thème, votre langue, puis le module « Pièces jointes pour utilisateurs connectés uniquement ».
4. Vous devriez y trouver les chaînes de texte pertinentes à traduire.

**Q : Ce module fonctionnera-t-il avec mon thème personnalisé ?**
R : Oui, le module est conçu pour fonctionner avec les mécanismes de pièces jointes standard de PrestaShop. Il intercepte principalement la demande de téléchargement plutôt que de modifier fortement l'affichage visuel des pièces jointes. Cependant, si votre thème personnalisé remplace complètement la façon dont les pièces jointes sont affichées ou liées, des ajustements mineurs pourraient être nécessaires. Testez toujours minutieusement après l'installation.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Pièces jointes pour utilisateurs connectés uniquement » fonctionne principalement en surchargeant le `AttachmentController` par défaut pour intercepter les requêtes de téléchargement. Il utilise le système de hooks de PrestaShop (`displayHeader`, `header`) pour injecter le JavaScript et le CSS nécessaires, et sa logique principale réside dans le fichier `atlogged.php`, gérant la configuration et la surcharge principale. Le module utilise une structure de configuration simple stockée dans `ps_configuration` et inclut des contrôleurs front-office pour les interactions AJAX et la logique de secours potentielle.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `atlogged/controllers/front/index.php`

  - **Nom de la classe :** `AtloggedIndexModuleFrontController` (probablement, basé sur la convention de nommage des fichiers)
  - **Classe parente :** `ModuleFrontController`
  - **Responsabilité :** Ce contrôleur pourrait servir de point d'entrée général pour les actions front-office spécifiques au module, gérant potentiellement les redirections ou l'affichage de messages lorsqu'un téléchargement de pièce jointe est restreint. Il pourrait également être un espace réservé ou utilisé pour un routage spécifique.
- `atlogged/controllers/front/popuploader.php`

  - **Nom de la classe :** `AtloggedPopuploaderModuleFrontController`
  - **Classe parente :** `ModuleFrontController`
  - **Responsabilité :** Ce contrôleur gère probablement les requêtes AJAX liées à l'affichage d'une invite de connexion/inscription ou d'un message spécifique lorsqu'un utilisateur tente de télécharger une pièce jointe restreinte. Il pourrait rendre un petit template (par exemple, `atlogged-ajax.tpl`) avec le contenu approprié.
- `atlogged/override/controllers/front/AttachmentController.php`

  - **Nom de la classe :** `AttachmentController` (surcharge la classe principale)
  - **Classe parente :** `AttachmentControllerCore`
  - **Responsabilité :** C'est la partie la plus critique de la logique front-office du module. Elle surcharge directement le `AttachmentController` principal de PrestaShop. Sa fonction principale est de :
    1. Vérifier si le module est activé (`ATLOGGED_ON`).
    2. Vérifier si l'utilisateur actuel est connecté.
    3. Si `ATLOGGED_C_ON` (Télécharger pour les clients uniquement) est activé, il vérifie en outre l'historique des commandes de l'utilisateur par rapport aux `atlogged_ostates` configurés.
    4. Si l'utilisateur ne répond pas aux critères, il empêche le processus de téléchargement de pièce jointe par défaut et redirige l'utilisateur ou déclenche une action spécifique au module (par exemple, affichage d'une invite de connexion via AJAX).
- `atlogged/override/controllers/front/index.php`

  - **Nom de la classe :** `IndexController` (surcharge la classe principale)
  - **Classe parente :** `IndexControllerCore`
  - **Responsabilité :** La surcharge de l'`IndexController` est moins courante pour la logique spécifique aux pièces jointes. Cela pourrait être utilisé pour :
    1. Des vérifications globales ou des redirections liées au module sur la page d'accueil.
    2. S'assurer que certains actifs spécifiques au module (JS/CSS) sont chargés globalement.
    3. Potentiellement gérer une redirection vers la page de connexion si un lien de pièce jointe est accédé directement sans être connecté depuis le contexte de la page d'accueil.

#### Contrôleurs d'administration Back-Office

- Aucun identifié. La configuration du module est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

- Aucun identifié. Le module ne semble pas définir de classes `ObjectModel` personnalisées. Il fonctionne probablement directement avec les objets principaux existants de PrestaShop (par exemple, `Customer`, `Order`, `Attachment`) et les valeurs de configuration.

### 4.4 Actifs JavaScript (`views/js/`)

- `atlogged/views/js/atlogged.js`
  - **Portée :** Front-office.
  - **Détails :** Ce script est probablement responsable de :
    1. L'interception des clics sur les liens de téléchargement de pièces jointes (balises `<a>` avec des classes ou des attributs de données spécifiques).
    2. L'exécution d'appels AJAX vers les contrôleurs frontaux `popuploader.php` ou `index.php` lorsqu'un téléchargement restreint est tenté par un utilisateur non qualifié.
    3. L'affichage de popups modales ou de messages (par exemple, « Veuillez vous connecter pour télécharger ») basés sur la réponse AJAX.
    4. Potentiellement la redirection des utilisateurs vers la page de connexion si la réponse AJAX l'exige.
    5. L'assurance d'une expérience utilisateur fluide lorsque l'accès est refusé.

### 4.5 Feuilles de style CSS (`views/css/`)

- `atlogged/views/css/atlogged.css`
  - **Portée :** Style client Front-office.
  - **Détails :** Cette feuille de style fournit le style nécessaire pour tout élément personnalisé introduit par le module, tel que :
    1. Le style de la modale ou de la boîte de message d'invite de connexion/inscription.
    2. Des ajustements à l'apparence des liens de pièces jointes s'ils sont désactivés ou visuellement modifiés lorsqu'ils sont restreints.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger :** Les développeurs doivent inspecter la sortie HTML générée par les templates du module (par exemple, `atlogged-ajax.tpl`) pour identifier des classes spécifiques (par exemple, `.atlogged-modal`, `.atlogged-message`, `.atlogged-login-button`) pour l'intégration et la personnalisation du thème.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates d'administration (`views/templates/admin/`)** :

  - `atlogged/views/templates/admin/orderstates.tpl`
    - **Objectif :** Ce template est utilisé dans la méthode `getContent()` du module dans le Back Office. Il rend la liste des statuts de commande (`atlogged_ostates`) pour l'option de configuration « Sélectionner les statuts de commande », généralement sous forme de liste déroulante à sélection multiple ou de liste de cases à cocher.
- **Templates Front-office (`views/templates/front/`)** :

  - `atlogged/views/templates/front/atlogged-ajax.tpl`
    - **Objectif :** Ce template est probablement rendu par le contrôleur frontal `popuploader.php` en réponse à une requête AJAX. Il contient le contenu HTML du message affiché aux utilisateurs qui ne peuvent pas télécharger une pièce jointe (par exemple, « Veuillez vous connecter pour continuer », avec des liens vers la connexion/l'inscription).
  - `atlogged/views/templates/front/atlogged.tpl`
    - **Objectif :** Ce template pourrait être inclus via un hook (par exemple, `displayHeader`) ou directement par un contrôleur frontal. Il pourrait contenir :
      1. Des éléments cachés ou des attributs de données utilisés par `atlogged.js`.
      2. Des variables de configuration ou de configuration initiales pour le JavaScript.
      3. Des messages de secours ou des éléments toujours présents mais affichés conditionnellement par JS.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne crée pas de tables SQL personnalisées.
  - Les enregistrements de configuration sont stockés dans la table `ps_configuration` :
    - `ATLOGGED_ON` : Stocke la valeur booléenne du paramètre « Activer la fonctionnalité ».
    - `ATLOGGED_C_ON` : Stocke la valeur booléenne du paramètre « Télécharger pour les clients uniquement ».
    - `atlogged_ostates` : Stocke un tableau sérialisé ou une chaîne de caractères séparée par des virgules des ID de statut de commande sélectionnés pour le paramètre « Sélectionner les statuts de commande ».
    - `mypresta_updates`, `update_`, `updatev_` : Utilisés pour les vérifications de mise à jour du module par MyPresta.eu.
    - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` : Une clé de configuration PrestaShop principale, probablement accédée pour le contexte linguistique dans le Back Office.
- **Table des hooks enregistrés** :

  | Nom du hook | Moment d'exécution | Objectif technique |
  | --- | --- | --- |
  | `displayHeader` | Dans la section `<head>` de chaque page front-office. | Utilisé pour injecter `atlogged.js` et `atlogged.css` dans la page, garantissant que la logique côté client et le style du module sont chargés. |
  | `header` | Alias de `displayHeader` dans certaines versions/contextes de PrestaShop. | Même objectif que `displayHeader`. |
  | `actionFrontControllerSetMedia` | Lorsqu'un contrôleur frontal définit ses actifs multimédias. | Pourrait être utilisé pour charger conditionnellement JS/CSS uniquement sur des pages spécifiques (par exemple, les pages produit) pour l'optimisation des performances. |
  | `actionDispatcherBefore` | Avant qu'un contrôleur frontal ne soit dispatché. | Potentiellement utilisé par la surcharge de l'`AttachmentController` pour intercepter la requête de téléchargement très tôt. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support technique dédié pour le module « Pièces jointes pour utilisateurs connectés uniquement », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est prête à vous aider pour toute question ou problème que vous pourriez rencontrer.
