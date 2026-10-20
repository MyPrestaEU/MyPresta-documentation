---
title: "Onglet de Vente Facebook - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Onglet de Vente Facebook par MyPresta.eu."
sidebar:
  label: "Onglet de Vente Facebook - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Facebook Sales Tab sur MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-sales-tab.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/facebook-sales-tab/)
>
> ---


# Onglet de Vente Facebook

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).
- **Exigences externes** : Une Page Fan Facebook (Page Professionnelle) active dont vous êtes l'administrateur. Vous devrez également créer une Application Facebook pour lier votre boutique à votre Page Fan, ce qui implique l'obtention d'un ID d'application et d'un Secret d'application depuis le portail Développeur de Facebook.

## 2. Présentation complète de la configuration (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Onglet de Vente Facebook)

Ceci est l'écran de configuration principal et unique pour le module Onglet de Vente Facebook. Ici, vous lierez votre boutique PrestaShop à votre Page Fan Facebook et définirez le contenu affiché.

Pour accéder à cette page, allez dans **Back Office > Modules > Gestionnaire de modules**, recherchez « Onglet de Vente Facebook » et cliquez sur « Configurer ».

#### **Paramètres de l'application Facebook**

Ces paramètres sont cruciaux pour établir la connexion entre votre boutique PrestaShop et votre Page Fan Facebook. Vous devrez créer une Application Facebook via le portail Développeur Facebook pour obtenir ces identifiants.

- **ID d'application Facebook :**

  - **Ce que fait ce paramètre :** C'est un identifiant unique pour votre Application Facebook. Il indique à Facebook quelle application tente de se connecter à votre Page Fan.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est correctement saisi :* Permet à votre module de communiquer avec Facebook et d'afficher l'onglet de vente.
    - *Lorsqu'il est incorrect ou vide :* Le module ne pourra pas se connecter à Facebook, et l'onglet de vente ne fonctionnera pas ou n'apparaîtra pas sur votre Page Fan.
  - **Valeur recommandée :** L'ID d'application exact fourni par Facebook lorsque vous créez votre application.
  - **Scénario / exemple de marchand :** Vous avez créé une application Facebook nommée « Onglet de Vente MaBoutique » sur developers.facebook.com, et Facebook lui a attribué un ID d'application comme `123456789012345`. Vous saisiriez ce numéro ici.
- **Secret d'application Facebook :**

  - **Ce que fait ce paramètre :** C'est une clé secrète associée à votre Application Facebook, utilisée pour authentifier les requêtes de votre application auprès de Facebook. Elle doit être gardée confidentielle.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est correctement saisi :* Assure une communication sécurisée entre votre boutique et Facebook.
    - *Lorsqu'il est incorrect ou vide :* Facebook rejettera les tentatives de connexion, et l'onglet de vente ne fonctionnera pas.
  - **Valeur recommandée :** Le Secret d'application exact fourni par Facebook lorsque vous créez votre application.
  - **Scénario / exemple de marchand :** Avec votre ID d'application, Facebook fournit un Secret d'application (par exemple, `abcdef1234567890abcdef1234567890`). Vous saisissez cette chaîne ici.
- **ID de page Facebook :**

  - **Ce que fait ce paramètre :** C'est l'identifiant unique de votre Page Fan Facebook spécifique où vous souhaitez que l'onglet de vente apparaisse.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est correctement saisi :* Le module sait quelle Page Fan cibler pour ajouter l'onglet de vente.
    - *Lorsqu'il est incorrect ou vide :* L'onglet de vente ne sera pas ajouté à votre Page Fan souhaitée, ou il pourrait être ajouté à la mauvaise si un ID incorrect est saisi.
  - **Valeur recommandée :** L'ID de page exact de votre Page Fan Facebook. Vous pouvez généralement le trouver dans la section « À propos » de votre Page Fan ou en utilisant un outil de recherche d'ID de page Facebook.
  - **Scénario / exemple de marchand :** La Page Fan Facebook de votre boutique est « Ma Super Boutique ». Vous trouvez son ID de page (par exemple, `987654321098765`) et le saisissez ici.

#### **Paramètres de contenu de l'onglet de vente**

Ces paramètres contrôlent les produits ou promotions affichés sur votre onglet de vente Facebook.

- **Nombre de produits à afficher :**

  - **Ce que fait ce paramètre :** Détermine combien de produits de votre sélection de ventes spéciales seront affichés sur l'onglet Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur un nombre plus élevé (par exemple, 20) :* Plus de produits seront visibles, offrant aux clients un choix plus large.
    - *Lorsqu'il est défini sur un nombre plus bas (par exemple, 5) :* Moins de produits seront affichés, ce qui pourrait concentrer l'attention sur vos meilleures offres.
  - **Valeur recommandée :** 10-20, selon le nombre de ventes actives que vous avez généralement et la quantité de contenu que vous souhaitez présenter.
  - **Scénario / exemple de marchand :** Vous avez 15 produits en solde. Définir ce paramètre sur « 15 » garantit que tous sont affichés sur votre onglet Facebook. Si vous ne voulez mettre en avant que les 5 meilleurs, vous le définiriez sur « 5 ».
- **Afficher les produits de catégories spécifiques :**

  - **Ce que fait ce paramètre :** Vous permet de filtrer les produits affichés sur l'onglet Facebook pour n'inclure que ceux des catégories sélectionnées dans votre boutique PrestaShop.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque des catégories spécifiques sont sélectionnées :* Seuls les produits appartenant à ces catégories apparaîtront sur l'onglet Facebook, même si d'autres produits sont en solde.
    - *Lorsqu'aucune catégorie n'est sélectionnée (ou toutes sont sélectionnées) :* Tous les produits qui répondent aux critères de « ventes » seront affichés.
  - **Valeur recommandée :** Sélectionnez les catégories pertinentes pour vos promotions actuelles ou les articles les plus vendus que vous souhaitez mettre en avant sur Facebook.
  - **Scénario / exemple de marchand :** Vous organisez une promotion spéciale sur les « Robes d'été » et les « Accessoires de plage ». Vous sélectionneriez ces deux catégories pour vous assurer que seuls ces produits apparaissent sur votre onglet de vente Facebook.
- **Afficher les produits avec des réductions/ventes spécifiques :**

  - **Ce que fait ce paramètre :** C'est le filtre principal pour ce qui constitue un produit « en solde ». Vous pouvez choisir d'afficher les produits qui ont une réduction de prix spécifique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé et configuré :* Seuls les produits avec des prix spéciaux actifs ou des réductions en pourcentage seront affichés.
    - *Lorsqu'il est désactivé :* Le module pourrait afficher des produits réguliers ou des produits basés sur d'autres critères (bien que l'objectif principal du module soit les « ventes »).
  - **Valeur recommandée :** OUI, et assurez-vous que vos produits ont des prix spéciaux actifs configurés dans PrestaShop.
  - **Scénario / exemple de marchand :** Vous avez configuré une réduction de 10 % sur tous les « Manteaux d'hiver » dans les paramètres de vos produits PrestaShop. Ce paramètre garantit que ces manteaux à prix réduit sont ceux qui apparaissent sur votre onglet Facebook.

#### **Paramètres d'affichage généraux**

- **Titre de l'onglet sur Facebook :**

  - **Ce que fait ce paramètre :** C'est le texte qui apparaîtra comme nom de l'onglet sur votre Page Fan Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur « Offres spéciales » :* Votre onglet sera étiqueté « Offres spéciales » sur Facebook.
    - *Lorsqu'il est défini sur « Acheter maintenant » :* Votre onglet sera étiqueté « Acheter maintenant ».
  - **Valeur recommandée :** Quelque chose de clair et invitant comme « Ventes spéciales », « Acheter maintenant » ou « Nos offres ».
  - **Scénario / exemple de marchand :** Vous voulez indiquer clairement que cet onglet est destiné aux promotions, vous définissez donc le titre sur « Ventes Flash ! »
- **Icône de l'onglet :**

  - **Ce que fait ce paramètre :** Vous permet de télécharger une icône personnalisée qui apparaîtra à côté du titre de votre onglet sur Facebook. Cela aide votre onglet à se démarquer.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'une icône est téléchargée :* Votre onglet aura un identifiant visuel personnalisé.
    - *Lorsqu'aucune icône n'est téléchargée :* Facebook utilisera une icône par défaut, ou l'onglet pourrait apparaître sans icône spécifique.
  - **Valeur recommandée :** Une icône petite, claire et pertinente (par exemple, un panier d'achat, une étoile, un signe de pourcentage) qui correspond à votre marque.
  - **Scénario / exemple de marchand :** Vous téléchargez une petite image d'un panier d'achat pour rendre votre onglet « Acheter maintenant » visuellement attrayant et facile à repérer.

#### **Tableau de référence rapide de la configuration**

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | ID d'application Facebook | Votre ID d'application Facebook | Lie votre boutique à votre application Facebook pour l'authentification. |
| Configuration du module | Secret d'application Facebook | Votre Secret d'application Facebook | Authentifie de manière sécurisée votre application auprès de Facebook. |
| Configuration du module | ID de page Facebook | Votre ID de Page Fan Facebook | Spécifie à quelle Page Fan l'onglet de vente sera ajouté. |
| Configuration du module | Nombre de produits à afficher | 10-20 | Contrôle le nombre de produits en solde affichés sur l'onglet. |
| Configuration du module | Afficher les produits de catégories spécifiques | Sélectionnez les catégories pertinentes | Filtre les produits par catégorie pour l'affichage sur l'onglet. |
| Configuration du module | Afficher les produits avec des réductions/ventes spécifiques | OUI | Garantit que seuls les produits à prix réduit sont affichés sur l'onglet. |
| Configuration du module | Titre de l'onglet sur Facebook | « Ventes spéciales » / « Acheter maintenant » | Définit le nom visible de l'onglet sur votre Page Fan Facebook. |
| Configuration du module | Icône de l'onglet | Téléchargez une icône pertinente | Fournit une icône visuelle personnalisée pour votre onglet Facebook. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Mon onglet de vente Facebook n'apparaît pas sur ma Page Fan. Que dois-je faire ?**
R1 :

- **Vérifiez l'ID d'application, le Secret d'application et l'ID de page :** Vérifiez que les trois valeurs sont correctement saisies dans la configuration du module. Même une seule faute de frappe empêchera la connexion.
- **Statut de l'application Facebook :** Assurez-vous que votre application Facebook est en ligne et publiquement disponible (pas en mode développement). Vous pouvez vérifier cela dans votre tableau de bord Développeur Facebook.
- **Autorisations :** Assurez-vous que votre application Facebook dispose des autorisations nécessaires pour gérer les pages.
- **Cache :** Videz le cache Smarty de votre PrestaShop (Paramètres avancés > Performances) et le cache de votre navigateur. Parfois, les changements prennent un moment pour se propager.
- **Administrateur de page Facebook :** Assurez-vous que le compte Facebook que vous utilisez pour gérer la Page Fan dispose des droits d'administrateur pour la Page Fan et l'application Facebook.

**Q2 : Les produits affichés sur l'onglet Facebook ne sont pas ceux que j'attends.**
R2 :

- **Paramètre « Afficher les produits avec des réductions/ventes spécifiques » :** Assurez-vous que ce paramètre est activé si vous ne souhaitez afficher que les articles à prix réduit.
- **Réductions de produits :** Vérifiez que les produits que vous *attendez* de voir ont bien des prix spéciaux actifs ou des réductions en pourcentage configurés dans les paramètres de vos produits PrestaShop.
- **Paramètre « Afficher les produits de catégories spécifiques » :** Si vous avez sélectionné des catégories spécifiques, assurez-vous que les produits que vous souhaitez afficher appartiennent à ces catégories.
- **« Nombre de produits à afficher » :** Si vous avez de nombreuses ventes, mais que ce nombre est faible, seuls les premiers seront affichés.

**Q3 : Comment obtenir un ID d'application Facebook, un Secret d'application et un ID de page ?**
R3 :

- **ID d'application Facebook et Secret d'application :** Allez sur [developers.facebook.com](https://developers.facebook.com/), connectez-vous et créez une nouvelle application. Suivez les instructions de Facebook pour configurer une nouvelle application, en choisissant généralement un type « Entreprise » ou « Site web ». Une fois créée, vous trouverez l'ID d'application et le Secret d'application dans les paramètres du tableau de bord de votre application.
- **ID de page Facebook :** Naviguez vers votre Page Fan Facebook. Vous pouvez souvent trouver l'ID de page dans la section « À propos » de votre page. Alternativement, il existe des outils en ligne (recherchez « Facebook Page ID Finder ») où vous pouvez coller l'URL de votre Page Fan pour récupérer son ID.

**Q4 : L'icône ou le titre de l'onglet ne se met pas à jour sur Facebook.**
R4 :

- **Mise en cache de Facebook :** Facebook lui-même peut mettre en cache les informations de page. Il peut falloir un certain temps (jusqu'à quelques heures) pour que les modifications du titre ou de l'icône de l'onglet se reflètent globalement.
- **Enregistrement de la configuration du module :** Assurez-vous d'avoir enregistré la configuration du module après avoir effectué des modifications.
- **Vider le cache :** Videz le cache de votre PrestaShop (Paramètres avancés > Performances) et le cache de votre navigateur.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Vue d'ensemble de l'architecture

Le module `Onglet de Vente Facebook` (`prestasales`) est un module PrestaShop standard conçu pour s'intégrer à la plateforme Facebook. Sa fonction principale est de servir du contenu (spécifiquement, une liste de produits en solde) qui peut être intégré dans un onglet de Page Fan Facebook. Le module utilise le système de configuration de PrestaShop pour stocker les identifiants de l'API Facebook et les préférences d'affichage. Il n'introduit pas de modèles MVC complexes ni de tables de base de données personnalisées, mais s'appuie plutôt sur les fonctionnalités de base de PrestaShop pour la récupération des produits et la gestion de la configuration. La logique principale du module réside dans son fichier `de.php`, gérant l'installation, la désinstallation et l'affichage de la configuration.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient aucun contrôleur d'administration Front-Office ou Back-Office personnalisé. Toute la configuration est gérée directement dans la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module n'introduit aucune classe personnalisée ni définition d'`ObjectModel`. Il interagit directement avec les classes `Product` et `Category` de base de PrestaShop et la classe `Configuration` pour les paramètres.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`prestasales/css/css.css`** :
  - **Portée :** Cette feuille de style est destinée à styliser le contenu affiché dans l'onglet Facebook.
  - **Principaux composants et conteneurs d'interface utilisateur qu'elle stylise :** Elle contiendrait généralement des styles pour les listes de produits, les images, les prix, les badges de réduction et les boutons « ajouter au panier » ou « voir le produit » dans l'onglet Facebook intégré.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger dans leur thème :** Les développeurs doivent inspecter la sortie HTML dans l'onglet Facebook pour identifier les noms de classe spécifiques. Les sélecteurs courants pourraient inclure `.prestasales-product-list`, `.prestasales-product-item`, `.prestasales-product-image`, `.prestasales-product-name`, `.prestasales-price`, `.prestasales-discount`, `.prestasales-button`.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Ce module ne liste pas explicitement les fichiers `.tpl` dans l'inventaire fourni. Cependant, en fonction de sa fonctionnalité, il contiendrait généralement :

- **Modèles de hook (`views/templates/hook/`)** :

  - Il est très probable qu'un modèle comme `views/templates/hook/displayFacebookSalesTab.tpl` (ou similaire) existe en interne dans le fichier `de.php` du module ou soit généré à la volée. Ce modèle serait responsable du rendu de la structure HTML de la liste de produits qui est ensuite servie à Facebook.
  - **Objectif :** Ce modèle itérerait sur les produits en solde sélectionnés et afficherait leurs images, noms, prix et liens, formatés pour être intégrés dans une iframe Facebook.
- **Modèles d'administration (`views/templates/admin/`)** :

  - Étant donné que la configuration est gérée par `getContent()`, un modèle comme `views/templates/admin/configure.tpl` ou `views/templates/admin/configuration_form.tpl` serait utilisé pour rendre le formulaire de configuration du back-office du module. Ce modèle contiendrait les champs de saisie pour l'ID d'application, le Secret d'application, l'ID de page, les options d'affichage des produits, etc.
- **Modèles de front-office (`views/templates/front/`)** :

  - Aucun modèle de front-office dédié n'est attendu car la sortie du module est principalement destinée à la plateforme Facebook.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Ce module ne crée aucune table SQL personnalisée.
  - Tous les paramètres de configuration sont stockés dans la table `ps_configuration` de PrestaShop en utilisant des clés comme `PRESTASALES_APP_ID`, `PRESTASALES_APP_SECRET`, `PRESTASALES_PAGE_ID`, `PRESTASALES_NUM_PRODUCTS`, `PRESTASALES_CATEGORIES`, `PRESTASALES_DISCOUNTS_ONLY`, `PRESTASALES_TAB_TITLE`, `PRESTASALES_TAB_ICON`.
- **Table des hooks enregistrés** :
  L'interaction principale du module avec le système de hooks de PrestaShop serait pour sa configuration et potentiellement pour le rendu du contenu que Facebook récupère.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Bien que le module n'affiche pas de contenu directement sur la boutique, il pourrait utiliser ce hook pour charger les scripts SDK Facebook nécessaires ou les balises meta s'il devait implémenter des fonctionnalités d'intégration Facebook avancées (par exemple, les balises Open Graph), bien que cela ne soit pas explicitement indiqué pour la fonction principale de ce module. |
| `displayBackOfficeHeader` | Dans la section `<head>` de chaque page du back-office. | Utilisé pour charger les CSS ou JS spécifiques au module pour la page de configuration, le cas échéant. |
| `moduleRoutes` | Lors de l'initialisation de la réécriture d'URL. | Non explicitement utilisé par ce module, car il ne définit pas de routes front-office personnalisées. |
| `actionProductUpdate` / `actionProductAdd` | Après la mise à jour ou l'ajout d'un produit. | Non explicitement utilisé, mais pourrait être utilisé pour vider le cache lié aux listes de produits pour l'onglet Facebook. |
| `actionModuleInstall` | Lors de l'installation du module. | Pour enregistrer les valeurs par défaut de la configuration et potentiellement configurer les étapes initiales d'intégration de l'application Facebook. |
| `actionModuleUninstall` | Lors de la désinstallation du module. | Pour nettoyer les données de configuration de `ps_configuration`. |

La fonctionnalité principale de service du contenu à Facebook est probablement gérée par une requête directe au fichier PHP principal du module (`de.php`) ou à une méthode interne spécifique qui rend la liste de produits, plutôt que par un hook `display` PrestaShop standard. Ce contenu est ensuite intégré dans une iframe sur la Page Fan Facebook.

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et toute assistance supplémentaire concernant le module « Onglet de Vente Facebook », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez rencontrer.
