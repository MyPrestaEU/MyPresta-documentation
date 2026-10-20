---
title: "Accès à la boutique par groupes de clients - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Accès à la boutique par groupes de clients' par MyPresta.eu."
sidebar:
  label: "Accès à la boutique par groupes de clients - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Access to shop by customer groups sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/access-to-shop-by-customer-groups.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/access-to-shop-by-customer-groups/)
>
> ---


# Accès à la boutique par groupes de clients

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont habituellement disponibles sur tout environnement d'hébergement moderne.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du nom du module pour accéder à ses paramètres.

#### **Groupes de clients sans accès à la boutique**

C'est le paramètre le plus crucial. Il détermine quels groupes de clients seront bloqués de la visualisation de votre boutique.

-   **Ce que fait ce paramètre :** Cette section affiche une liste de tous les groupes de clients définis dans votre boutique PrestaShop. Vous pouvez sélectionner un ou plusieurs groupes dans cette liste.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'un ou plusieurs groupes sont sélectionnés :* Tout client appartenant à *l'un quelconque* des groupes sélectionnés sera bloqué de l'accès au front office de la boutique. Il verra à la place le contenu personnalisé que vous définissez ci-dessous.
    *   *Lorsqu'aucun groupe n'est sélectionné :* Le module ne bloquera aucun client en fonction de son affiliation à un groupe. Tous les clients auront accès à la boutique (sauf si vous activez l'option « Bloquer l'accès pour les clients non connectés »).
-   **Valeur recommandée :** Sélectionnez les groupes spécifiques que vous souhaitez restreindre. Par exemple, si vous avez un groupe « Grossiste en attente d'approbation », vous pouvez le sélectionner ici.
-   **Scénario / exemple de marchand :** Vous avez créé un nouveau groupe de clients appelé « Nouvelles inscriptions - En attente de révision ». Vous sélectionnez ce groupe ici. Désormais, tout nouveau client qui s'inscrit sera automatiquement placé dans ce groupe et ne pourra pas naviguer sur votre boutique tant que vous ne l'aurez pas déplacé manuellement vers un groupe « Clients approuvés ».

#### **Bloquer l'accès pour les clients non connectés**

Ce paramètre contrôle l'accès pour les visiteurs qui ne sont pas connectés à votre boutique.

-   **Ce que fait ce paramètre :** Il s'agit d'un simple interrupteur ON/OFF.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'il est activé (OUI) :* Tous les visiteurs qui ne sont pas connectés à un compte client seront bloqués de l'accès à la boutique. Ils verront la page de contenu personnalisé. Une fois qu'ils se sont connectés (et s'ils appartiennent à un groupe autorisé), ils auront accès.
    *   *Lorsqu'il est désactivé (NON) :* Les visiteurs non connectés auront accès à la boutique, sauf s'ils sont explicitement bloqués en appartenant à un « Groupe de clients sans accès à la boutique ».
-   **Valeur recommandée :**
    *   **OUI :** Si vous souhaitez que l'ensemble de votre boutique soit privé, exigeant que tous les visiteurs se connectent d'abord (par exemple, une boutique B2B, un club réservé aux membres).
    *   **NON :** Si vous souhaitez que votre boutique soit visible publiquement, mais ne restreindre que des groupes de clients spécifiques.
-   **Scénario / exemple de marchand :** Vous gérez une boutique réservée aux grossistes. Vous activez ce paramètre. Désormais, toute personne visitant votre site doit d'abord se connecter pour voir vos produits et vos prix.

#### **Afficher le formulaire de connexion sur la page bloquée**

Ce paramètre détermine si un formulaire de connexion apparaît sur la page affichée aux clients bloqués.

-   **Ce que fait ce paramètre :** Il s'agit d'un simple interrupteur ON/OFF.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'il est activé (OUI) :* Un formulaire de connexion PrestaShop standard sera affiché sur la page de contenu personnalisé, permettant aux clients bloqués de tenter de se connecter.
    *   *Lorsqu'il est désactivé (NON) :* Aucun formulaire de connexion ne sera affiché. Les clients ne verront que votre message personnalisé.
-   **Valeur recommandée :**
    *   **OUI :** Si vous vous attendez à ce que les clients bloqués soient des clients existants qui ont simplement besoin de se connecter pour obtenir l'accès. Cela améliore l'expérience utilisateur.
    *   **NON :** Si vous souhaitez forcer les clients à s'inscrire d'abord, ou si la restriction d'accès est permanente pour certains groupes.
-   **Scénario / exemple de marchand :** Vous avez bloqué l'accès aux utilisateurs non connectés. En activant cela, les clients peuvent facilement se connecter directement depuis la page restreinte sans avoir à naviguer vers une page de connexion distincte.

#### **Autoriser l'inscription sur la page bloquée**

Ce paramètre détermine si un lien d'inscription apparaît sur la page affichée aux clients bloqués.

-   **Ce que fait ce paramètre :** Il s'agit d'un simple interrupteur ON/OFF.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'il est activé (OUI) :* Un lien vers la page d'inscription client sera affiché sur la page de contenu personnalisé.
    *   *Lorsqu'il est désactivé (NON) :* Aucun lien d'inscription ne sera affiché.
-   **Valeur recommandée :**
    *   **OUI :** Si vous souhaitez permettre aux nouveaux clients de s'inscrire depuis la page restreinte.
    *   **NON :** Si vous souhaitez contrôler l'inscription séparément, ou si votre boutique est strictement réservée aux clients pré-approuvés.
-   **Scénario / exemple de marchand :** Vous gérez une boutique B2B qui nécessite une inscription. Vous activez ce paramètre afin que les nouveaux clients potentiels puissent facilement créer un compte directement depuis la page à accès restreint.

#### **Contenus personnalisés à afficher**

C'est ici que vous définissez le message et le contenu affichés aux clients bloqués.

-   **Ce que fait ce paramètre :** Il s'agit d'un éditeur de texte enrichi (WYSIWYG) où vous pouvez saisir du texte, des images, du HTML et même des vidéos. Il prend en charge le contenu multilingue, vous pouvez donc fournir différents messages pour les différentes langues installées dans votre boutique.
-   **Effet de la modification de ce paramètre :** Le contenu que vous saisissez ici sera affiché à tout client bloqué de l'accès à votre boutique.
-   **Valeur recommandée :** Fournissez un message clair, poli et informatif.
-   **Scénario / exemple de marchand :**
    *   *Pour une boutique B2B :* « Bienvenue sur notre portail de vente en gros ! Veuillez vous connecter avec vos identifiants ou vous inscrire pour un nouveau compte afin de consulter notre catalogue de produits. »
    *   *Pour une restriction temporaire :* « Notre boutique est actuellement en maintenance. Nous serons de retour en ligne bientôt ! Merci de votre patience. »
    *   *Pour un accès exclusif :* « Cette section de notre boutique est réservée aux membres VIP. Veuillez vous connecter ou contacter le support pour y accéder. »

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | **Groupes de clients sans accès à la boutique** | Aucun sélectionné | Sélectionnez les groupes à bloquer de la visualisation de la boutique. Les clients de ces groupes voient le contenu personnalisé. |
| Configuration du module | **Bloquer l'accès pour les clients non connectés** | NON | OUI : Tous les visiteurs non connectés sont bloqués. NON : Les visiteurs non connectés ont accès (sauf s'ils font partie d'un groupe bloqué). |
| Configuration du module | **Afficher le formulaire de connexion sur la page bloquée** | OUI | OUI : Affiche un formulaire de connexion sur la page restreinte. NON : Aucun formulaire de connexion n'est affiché. |
| Configuration du module | **Autoriser l'inscription sur la page bloquée** | OUI | OUI : Affiche un lien d'inscription sur la page restreinte. NON : Aucun lien d'inscription n'est affiché. |
| Configuration du module | **Contenus personnalisés à afficher** | Vide | Définit le message/contenu HTML affiché aux clients bloqués. Prend en charge le multilingue. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Ma boutique est complètement bloquée, même pour moi ! Que dois-je faire ?**
R1 : Cela se produit généralement si vous avez activé « Bloquer l'accès pour les clients non connectés » et que vous n'êtes pas connecté, ou si votre compte administrateur est d'une manière ou d'une autre associé à un groupe de clients bloqué.
\* **Solution 1 (Recommandée) :** Connectez-vous à votre Back Office PrestaShop. Le module ne bloque que le front office. Une fois connecté au BO, naviguez vers Modules > Gestionnaire de modules, trouvez « Accès à la boutique par groupes de clients » et cliquez sur « Configurer ». Ajustez les paramètres pour autoriser votre accès.
\* **Solution 2 (Si vous ne pouvez pas accéder au BO) :** Si vous êtes complètement bloqué, vous devrez peut-être désactiver temporairement le module via FTP. Allez dans `modules/asg/` et renommez le fichier `asg.php` (par exemple, `asg.php.bak`). Cela désactivera le module. Ensuite, vous pourrez vous connecter à votre BO et le réactiver/reconfigurer. N'oubliez pas de renommer le fichier en `asg.php` par la suite.

**Q2 : Le contenu personnalisé semble simple ou ne correspond pas à mon thème.**
R2 : La zone de contenu personnalisé utilise un modèle de base.
\* **Solution :** Vous pouvez utiliser l'éditeur de texte enrichi pour ajouter du HTML, du CSS en ligne ou des images pour styliser votre message. Pour un style plus avancé, un webmaster peut modifier le fichier `custom.css` ou le modèle `custom-contents.tpl` (voir la section développeur). Assurez-vous que votre contenu personnalisé est bien formaté et réactif.

**Q3 : Pourquoi le formulaire de connexion/d'inscription ne s'affiche-t-il pas ?**
R3 : Vérifiez la configuration du module :
\* Assurez-vous que « Afficher le formulaire de connexion sur la page bloquée » est défini sur OUI.
\* Assurez-vous que « Autoriser l'inscription sur la page bloquée » est défini sur OUI.
\* Assurez-vous également que l'inscription des clients est généralement activée dans les paramètres de votre PrestaShop (Clients > Paramètres > Activer la création de compte).

**Q4 : J'ai effectué des modifications, mais elles n'apparaissent pas sur le front office.**
R4 : PrestaShop utilise la mise en cache, ce qui peut parfois retarder l'affichage des modifications.
\* **Solution :** Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop. Cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). Cela devrait rafraîchir votre front office.

**Q5 : Comment gérer quels clients appartiennent à quels groupes ?**
R5 : Vous gérez les groupes de clients via l'interface standard de PrestaShop :
\* Allez dans **Clients > Clients** pour modifier les comptes clients individuels et les attribuer à des groupes.
\* Allez dans **Clients > Groupes** pour créer de nouveaux groupes ou modifier ceux existants.
\* N'oubliez pas qu'un client peut appartenir à plusieurs groupes. Si un client appartient à *n'importe quel* groupe que vous avez marqué comme « sans accès », il sera bloqué.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Accès à la boutique par groupes de clients » (`asg`) fonctionne principalement en se greffant sur l'événement `displayHeader`. Cela lui permet d'exécuter sa logique très tôt dans le processus de chargement de la page, avant que tout contenu ne soit rendu. Si un client est jugé restreint, le module prend le contrôle, empêche le rendu ultérieur de la page PrestaShop standard et affiche à la place sa page d'accès personnalisée. Il utilise le système de configuration de PrestaShop pour les paramètres et Smarty pour le templating.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs front-office ou back-office dédiés. Toute la logique est encapsulée dans le fichier principal du module (`asg.php`) et exécutée via des hooks ou la méthode `getContent()` pour la configuration.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée ni entité `ObjectModel`. Il interagit directement avec les classes `Customer`, `Group` et `Configuration` de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`asg/views/css/custom.css`**
    *   **Portée :** Style du front-office pour la page d'accès restreint.
    *   **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :** Ce fichier fournit un style de base pour le wrapper de contenu personnalisé, le formulaire de connexion et le lien d'inscription sur la page d'accès restreint. Il garantit que le contenu affiché est centré et lisible.
    *   **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger :**
        *   `.asg_wrapper` : Le conteneur principal pour l'ensemble du contenu restreint.
        *   `.asg_content` : La div contenant le message HTML personnalisé.
        *   `.asg_login_form` : Le conteneur du formulaire de connexion.
        *   `.asg_registration_link` : Le conteneur du lien d'inscription.
        *   Éléments de formulaire PrestaShop standard dans le formulaire de connexion.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** : Aucun explicitement défini comme templates de hook. Le module rend directement les templates en fonction de sa logique interne.
-   **Templates d'administration (`views/templates/admin/`)** :
    *   **`asg/views/admin.tpl`** : Ce template est rendu par la méthode `getContent()` dans `asg.php`. Il contient la structure HTML du formulaire de configuration du module dans le Back Office de PrestaShop. Il inclut la sélection des groupes de clients, les interrupteurs pour la connexion/l'inscription et l'éditeur de texte enrichi pour le contenu personnalisé.
-   **Templates du front-office (`views/templates/front/`)** :
    *   **`asg/views/custom-contents.tpl`** : C'est le template principal rendu lorsqu'un client est bloqué. Il affiche le contenu personnalisé défini dans la configuration du module. Il inclut conditionnellement `login-form.tpl` et `registration-link.tpl` en fonction des paramètres du module.
    *   **`asg/views/login-form.tpl`** : Ce template contient le HTML du formulaire de connexion client PrestaShop standard. Il est inclus dans `custom-contents.tpl` si l'option « Afficher le formulaire de connexion » est activée.
    *   **`asg/views/registration-link.tpl`** : Ce template contient le HTML du lien vers la page d'inscription client. Il est inclus dans `custom-contents.tpl` si l'option « Autoriser l'inscription » est activée.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    *   Ce module ne crée aucune table SQL personnalisée.
    *   Il stocke ses paramètres de configuration dans la table `ps_configuration` (ou `_configuration` selon le préfixe) en utilisant des clés telles que :
        *   `ASG_ALLOWREGAUTH` : Booléen pour autoriser l'inscription.
        *   `ASG_SHOWLOGINFORM` : Booléen pour afficher le formulaire de connexion.
        *   `ASG_CCONTENTS` : Champ multilingue pour le contenu personnalisé (HTML).
        *   `ASG_WHATTOSHOW` : Tableau sérialisé des ID de groupes de clients bloqués.
        *   `ASG_BLOCK_NOT_LOGGED` : Booléen pour bloquer les utilisateurs non connectés.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Exécuté très tôt lors du chargement de la page du front-office, dans la section `<head>`. | C'est le hook principal utilisé par le module. Il vérifie le statut de connexion du client et son affiliation à un groupe. Si un client est restreint, il met immédiatement fin au processus de rendu PrestaShop standard et affiche la page d'accès personnalisée (`custom-contents.tpl`). |
| `actionCustomerGroupsUpdate` | Exécuté lorsque les groupes de clients sont mis à jour. | Utilisé pour vider le cache interne du module lié aux groupes de clients, garantissant que les modifications apportées aux attributions de groupes sont immédiatement reflétées. |
| `actionObjectCustomerAddAfter` | Exécuté après l'ajout d'un nouveau client. | Utilisé pour vider le cache interne du module lié aux groupes de clients, garantissant que les nouveaux clients sont correctement évalués pour l'accès. |
| `actionObjectCustomerUpdateAfter` | Exécuté après la mise à jour d'un client existant. | Utilisé pour vider le cache interne du module lié aux groupes de clients, garantissant que les modifications apportées aux attributions de groupes de clients sont immédiatement reflétées. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, les corrections de bugs et le support développeur dédié pour le module « Accès à la boutique par groupes de clients », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe s'engage à fournir une assistance rapide et à assurer la compatibilité du module avec les dernières versions de PrestaShop.
