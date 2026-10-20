---
title: "Téléchargement de Fichiers Clients - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Téléchargement de Fichiers Clients par MyPresta.eu."
sidebar:
  label: "Téléchargement de Fichiers Clients - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Customer Files Upload sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/customer-files-upload.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/customer-files-upload/)
>
> ---


# Téléchargement de Fichiers Clients

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises par PrestaShop lui-même et sont suffisantes pour ce module. Assurez-vous que votre serveur dispose de suffisamment d'espace disque pour stocker les fichiers téléchargés.

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module, accessible après l'installation ou en cliquant sur « Configurer » depuis le Gestionnaire de modules.

- **Activer le module :**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité du module dans votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Toutes les fonctionnalités de téléchargement de fichiers, la gestion des fichiers clients et les outils du back-office deviennent actifs.
    - *Lorsqu'il est désactivé :* Les fonctionnalités du module sont complètement désactivées, et aucun formulaire de téléchargement ou section « Mes fichiers » n'apparaîtra.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** Si vous configurez le module pour la première fois ou effectuez une maintenance, vous pouvez le désactiver temporairement. Sinon, gardez-le activé pour offrir le service de téléchargement de fichiers.
- **Autoriser les téléchargements sur la page produit :**

  - **Ce que fait ce paramètre :** Contrôle si les clients peuvent télécharger des fichiers directement depuis la page d'un produit.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un formulaire de téléchargement apparaîtra sur les pages produit, permettant aux clients de joindre des fichiers avant d'ajouter le produit à leur panier.
    - *Lorsqu'il est désactivé :* Aucun formulaire de téléchargement ne sera visible sur les pages produit.
  - **Valeur recommandée :** OUI (si vos produits nécessitent des fichiers de personnalisation avant l'achat)
  - **Scénario / exemple de marchand :** Si vous vendez des tasses personnalisées, l'activation de cette option permet aux clients de télécharger leur photo directement sur la page produit de la tasse.
- **Autoriser les téléchargements sur la page du panier :**

  - **Ce que fait ce paramètre :** Détermine si une zone de téléchargement est affichée sur la page de résumé du panier.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clients peuvent télécharger des fichiers généraux liés à l'ensemble de leur panier ou à des articles spécifiques avant de passer à la caisse.
    - *Lorsqu'il est désactivé :* Aucun formulaire de téléchargement ne sera visible sur la page du panier.
  - **Valeur recommandée :** OUI (si les clients peuvent avoir besoin de fournir des instructions générales de commande ou des fichiers pour plusieurs articles)
  - **Scénario / exemple de marchand :** Un client commandant plusieurs articles personnalisés pourrait télécharger un seul document avec des instructions générales ou un guide de marque pour l'ensemble de la commande.
- **Autoriser les téléchargements sur la page de confirmation de commande :**

  - **Ce que fait ce paramètre :** Contrôle si les clients peuvent télécharger des fichiers immédiatement après avoir passé une commande, sur l'écran de confirmation de commande.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un formulaire de téléchargement apparaît sur la page « Confirmation de commande », permettant aux clients de joindre des fichiers à leur commande nouvellement passée.
    - *Lorsqu'il est désactivé :* Aucun formulaire de téléchargement ne sera visible sur la page de confirmation de commande.
  - **Valeur recommandée :** OUI (fortement recommandé pour la plupart des cas d'utilisation)
  - **Scénario / exemple de marchand :** Un client vient d'acheter une bannière personnalisée. Il peut immédiatement télécharger son fichier de conception haute résolution sur la page de confirmation sans naviguer ailleurs.
- **Autoriser les téléchargements dans le compte client (Mes fichiers et Historique des commandes) :**

  - **Ce que fait ce paramètre :** Active la section « Mes fichiers » dans le compte client et autorise les téléchargements sur les pages de détails de commande individuelles dans leur historique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clients disposent d'une zone dédiée « Mes fichiers » pour gérer tous leurs téléchargements et peuvent ajouter des fichiers à des commandes passées spécifiques.
    - *Lorsqu'il est désactivé :* Les clients ne peuvent pas gérer les fichiers depuis leur compte, et aucune option de téléchargement n'apparaîtra sur les pages d'historique des commandes.
  - **Valeur recommandée :** OUI (offre une flexibilité maximale et un contrôle client)
  - **Scénario / exemple de marchand :** Un client réalise qu'il a oublié de télécharger un fichier de police spécifique pour sa commande de t-shirt personnalisé un jour plus tard. Il peut se connecter à son compte, accéder à la commande et le télécharger.
- **Taille maximale des fichiers (Mo) :**

  - **Ce que fait ce paramètre :** Définit la limite supérieure pour la taille de chaque fichier individuel qu'un client peut télécharger.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'une valeur est définie (par exemple, 10) :* Les clients ne pourront pas télécharger de fichiers de plus de 10 Mo.
    - *Lorsqu'il est défini sur 0 ou vide :* Le module se référera généralement aux limites de téléchargement PHP de votre serveur, qui peuvent être très élevées ou très faibles.
  - **Valeur recommandée :** 5-20 Mo (ajuster en fonction des types de fichiers typiques ; par exemple, les images haute résolution peuvent nécessiter plus).
  - **Scénario / exemple de marchand :** Si vous vous attendez à ce que les clients téléchargent des photos haute résolution, vous pouvez définir cette valeur à 20 Mo. Si seuls de petits documents sont nécessaires, 5 Mo peuvent suffire pour économiser de l'espace serveur.
- **Types de fichiers autorisés (séparés par des virgules) :**

  - **Ce que fait ce paramètre :** Spécifie les extensions de fichiers autorisées pour le téléchargement.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur « jpg,png,pdf » :* Seuls les fichiers avec ces extensions peuvent être téléchargés. Tout autre type de fichier sera rejeté.
    - *Lorsqu'il est laissé vide :* Tous les types de fichiers peuvent être autorisés (non recommandé pour la sécurité).
  - **Valeur recommandée :** Incluez uniquement les types que vous attendez (par exemple, `jpg,jpeg,png,gif,pdf,doc,docx,xls,xlsx,txt,zip`). Évitez les fichiers exécutables.
  - **Scénario / exemple de marchand :** Si vous n'avez besoin que de fichiers de conception, vous pouvez lister `ai,eps,svg,psd,pdf,jpg,png`. Si vous avez besoin de documents, `doc,docx,pdf` serait approprié.
- **Forcer le téléchargement de fichiers pour des produits spécifiques (ID de produits) :**

  - **Ce que fait ce paramètre :** Vous permet de rendre le téléchargement de fichiers obligatoire pour certains produits. Saisissez les ID de produits séparés par des virgules.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque des ID de produits sont saisis :* Si un client tente d'ajouter l'un de ces produits au panier ou de passer à la caisse sans télécharger de fichier, il sera invité à le faire.
    - *Lorsqu'il est laissé vide :* Aucun produit n'aura de téléchargement de fichier obligatoire.
  - **Valeur recommandée :** Utilisez uniquement pour les produits pour lesquels un fichier est absolument essentiel au traitement de la commande.
  - **Scénario / exemple de marchand :** Pour un produit « Conception de cartes de visite personnalisées » (ID 123), vous pouvez saisir `123`. Le client ne peut pas finaliser l'achat sans télécharger son logo ou son brief de conception.
- **Notification par e-mail au client lors du téléchargement de fichiers :**

  - **Ce que fait ce paramètre :** Contrôle si un e-mail est envoyé au client lorsqu'il télécharge un fichier avec succès.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le client reçoit un e-mail de confirmation que son fichier a été reçu.
    - *Lorsqu'il est désactivé :* Aucune notification par e-mail n'est envoyée au client.
  - **Valeur recommandée :** OUI (améliore la confiance du client et fournit une confirmation)
  - **Scénario / exemple de marchand :** Un client télécharge une photo pour un cadeau personnalisé. Un e-mail confirme le téléchargement, le rassurant que son fichier a été reçu correctement.
- **Notification par e-mail à l'administrateur lors du téléchargement de fichiers :**

  - **Ce que fait ce paramètre :** Contrôle si un e-mail est envoyé au(x) administrateur(s) de la boutique lorsqu'un client télécharge un fichier.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* L'administrateur de la boutique reçoit une alerte par e-mail, l'informant des nouveaux fichiers qui nécessitent une attention.
    - *Lorsqu'il est désactivé :* Aucune notification par e-mail n'est envoyée à l'administrateur.
  - **Valeur recommandée :** OUI (essentiel pour un traitement rapide des commandes)
  - **Scénario / exemple de marchand :** Un client télécharge un fichier de conception. L'administrateur reçoit un e-mail, l'invitant à vérifier la commande et à commencer le traitement de l'article personnalisé.
- **Afficher le bouton de téléchargement dans l'en-tête/le pied de page/les colonnes :**

  - **Ce que fait ce paramètre :** Vous permet de choisir où un bouton ou un lien général « Télécharger des fichiers » apparaît sur votre boutique (par exemple, dans l'en-tête, le pied de page ou les colonnes latérales).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'un hook est sélectionné :* Un lien ou un bouton apparaîtra à cet emplacement, dirigeant les clients vers leur section « Mes fichiers » ou une page de téléchargement générale.
    - *Lorsque « Aucun » est sélectionné :* Aucun bouton de téléchargement général ne sera affiché en dehors des pages produit/panier/commande.
  - **Valeur recommandée :** Envisagez `displayHeader` ou `displayFooter` pour un accès facile à « Mes fichiers » si vous vous attendez à des téléchargements fréquents.
  - **Scénario / exemple de marchand :** Placer un lien « Mes fichiers » dans le pied de page permet aux clients récurrents d'accéder et de gérer rapidement leurs documents téléchargés.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 Gestionnaire de fichiers clients (Back Office > Modules > Téléchargement de Fichiers Clients > Fichiers Clients)

Cet écran fournit un endroit centralisé pour vous, le propriétaire de la boutique, pour afficher et gérer tous les fichiers téléchargés par vos clients.

- **Nom de l'écran et emplacement du menu :** Vous pouvez le trouver en naviguant vers **Modules > Gestionnaire de modules**, en trouvant « Téléchargement de Fichiers Clients » et en cliquant sur « Configurer ». Dans la configuration du module, il devrait y avoir un onglet ou un lien intitulé « Fichiers Clients » ou « Gérer les fichiers ». Alternativement, il peut apparaître directement sous le menu « Modules » sous le nom « Fichiers Clients ».
- **Actions et paramètres disponibles :**
  - **Tableau de liste des fichiers :** Affiche une liste de tous les fichiers téléchargés, y compris des détails tels que :
    - **Nom du fichier :** Le nom du fichier téléchargé.
    - **Client :** Le nom du client qui a téléchargé le fichier.
    - **ID de commande :** Si le fichier est lié à une commande spécifique.
    - **Produit :** Si le fichier est lié à un produit spécifique.
    - **Date de téléchargement :** Quand le fichier a été téléchargé.
    - **Taille :** La taille du fichier.
    - **Actions :** Comprend généralement des options pour **Télécharger** le fichier, **Afficher les détails** ou **Supprimer** le fichier.
  - **Filtrage et recherche :** Vous pouvez généralement filtrer les fichiers par client, ID de commande, produit ou plage de dates pour trouver rapidement des téléchargements spécifiques.
  - **Actions en masse :** Options pour sélectionner plusieurs fichiers et effectuer des actions telles que la suppression en masse.
- **Effet des modifications :**
  - **Téléchargement d'un fichier :** Récupère le fichier téléchargé par le client sur votre ordinateur pour traitement.
  - **Suppression d'un fichier :** Supprime définitivement le fichier de votre serveur et de la section « Mes fichiers » du client. À utiliser avec prudence !
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vérifiez régulièrement cette section pour les nouveaux téléchargements, surtout après avoir reçu des notifications par e-mail de l'administrateur. Téléchargez les fichiers nécessaires à l'exécution des commandes, et examinez et supprimez périodiquement les fichiers anciens ou inutiles pour libérer de l'espace serveur.

#### 2.2.2 Intégration de la page de détails de commande (Back Office > Commandes > Commandes > Afficher la commande)

Le module s'intègre directement dans vos pages de détails de commande PrestaShop existantes.

- **Nom de l'écran et emplacement du menu :** Lorsque vous affichez une commande spécifique dans votre Back Office (par exemple, **Commandes > Commandes**, puis cliquez sur « Afficher » à côté d'une commande).
- **Actions et paramètres disponibles :**
  - Dans la page de détails de la commande, une nouvelle section ou un nouvel onglet apparaîtra, spécifiquement pour « Fichiers clients » ou « Fichiers téléchargés ».
  - Cette section listera tous les fichiers que le client a téléchargés pour *cette commande spécifique*.
  - Vous verrez les noms de fichiers, les dates de téléchargement et les options pour **Télécharger** chaque fichier.
  - Il peut également y avoir une option pour l'administrateur de **Télécharger un fichier** au nom du client ou pour un usage interne lié à la commande.
- **Effet des modifications :**
  - **Téléchargement de fichiers à partir d'ici :** Vous permet d'accéder rapidement aux fichiers pertinents pour la commande que vous consultez actuellement, rationalisant le traitement des commandes.
  - **Téléchargement par l'administrateur :** Si disponible, vous permet d'ajouter des notes internes ou des fichiers liés à la commande directement à la liste des fichiers de la commande.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Lors du traitement d'une commande qui nécessite des fichiers clients, naviguez vers la page de détails de la commande, localisez la section « Fichiers clients » et téléchargez tous les documents nécessaires avant de commencer la production ou l'exécution.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activer le module | OUI | Interrupteur principal pour la fonctionnalité du module. |
|  | Autoriser les téléchargements sur la page produit | OUI (si nécessaire) | Affiche le formulaire de téléchargement sur les pages produit. |
|  | Autoriser les téléchargements sur la page du panier | OUI (si nécessaire) | Affiche le formulaire de téléchargement sur la page du panier. |
|  | Autoriser les téléchargements sur la page de confirmation de commande | OUI | Affiche le formulaire de téléchargement après la commande. |
|  | Autoriser les téléchargements dans le compte client | OUI | Active « Mes fichiers » et les téléchargements de l'historique des commandes. |
|  | Taille maximale des fichiers (Mo) | 5-20 Mo | Limite la taille de téléchargement des fichiers individuels. |
|  | Types de fichiers autorisés | `jpg,png,pdf,...` | Restreint les extensions de fichiers pour la sécurité/pertinence. |
|  | Forcer le téléchargement de fichiers pour des produits spécifiques (ID) | Vide (utiliser au besoin) | Rend le téléchargement obligatoire pour les produits spécifiés. |
|  | Notification par e-mail au client | OUI | Envoie une confirmation par e-mail au client lors du téléchargement. |
|  | Notification par e-mail à l'administrateur | OUI | Envoie une alerte par e-mail à l'administrateur lors d'un nouveau téléchargement. |
|  | Afficher le bouton de téléchargement dans l'en-tête/le pied de page/les colonnes | `displayFooter` (ou au besoin) | Place un lien général « Télécharger des fichiers » dans le hook sélectionné. |
| **Gestionnaire de fichiers clients** | Liste des fichiers | N/A | Afficher, filtrer, télécharger et supprimer tous les fichiers clients. |
|  | Actions en masse | N/A | Effectuer des actions sur plusieurs fichiers sélectionnés. |
| **Page de détails de commande** | Section Fichiers clients | N/A | Afficher et télécharger les fichiers spécifiques à la commande actuelle. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Mes clients ne voient pas les formulaires de téléchargement ou la section « Mes fichiers ».**
R :

- **Vérifier l'état du module :** Assurez-vous que le module est activé dans **Modules > Gestionnaire de modules**.
- **Vérifier la configuration :** Accédez à la page de configuration du module et vérifiez que « Activer le module » est défini sur OUI et que les emplacements de téléchargement spécifiques (Page produit, Panier, Compte client) sont également activés.
- **Vider le cache :** Parfois, le cache de PrestaShop peut empêcher les modifications d'apparaître immédiatement. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ».
- **Compatibilité du thème :** Si vous utilisez un thème fortement personnalisé, il se peut qu'il ne se connecte pas correctement aux points d'affichage du module. Contactez le support MyPresta.eu ou votre développeur Web.

**Q2 : Les clients reçoivent une erreur lorsqu'ils essaient de télécharger des fichiers.**
R :

- **Vérifier la limite de taille de fichier :** Vérifiez la « Taille maximale des fichiers (Mo) » dans la configuration du module. Le fichier du client pourrait être trop volumineux.
- **Vérifier les types de fichiers autorisés :** Assurez-vous que le type de fichier que le client essaie de télécharger est répertorié dans le paramètre « Types de fichiers autorisés » (par exemple, s'il télécharge un fichier `.zip`, `zip` doit être dans la liste).
- **Limites du serveur :** Votre hébergeur Web peut avoir des limites de téléchargement PHP côté serveur (`upload_max_filesize`, `post_max_size`) qui sont inférieures au paramètre de votre module. Vous devrez peut-être contacter votre hébergeur ou ajuster votre fichier `php.ini`.

**Q3 : Je ne reçois pas de notifications par e-mail lorsque les clients téléchargent des fichiers.**
R :

- **Vérifier les paramètres de notification par e-mail :** Dans la configuration du module, assurez-vous que « Notification par e-mail à l'administrateur lors du téléchargement de fichiers » est défini sur OUI.
- **Paramètres d'e-mail de PrestaShop :** Vérifiez que les paramètres d'e-mail de votre boutique PrestaShop sont correctement configurés et que les e-mails sont envoyés avec succès (**Paramètres avancés > E-mail**). Envoyez un e-mail de test à partir de là.
- **Dossier de spam :** Vérifiez votre dossier de spam ou de courrier indésirable pour les notifications.
- **Serveur de messagerie :** Assurez-vous que la fonction de messagerie de votre serveur fonctionne correctement.

**Q4 : Comment traduire le texte du module dans d'autres langues ?**
R :

- Naviguez vers **International > Traductions** dans votre Back Office PrestaShop.
- Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez « Téléchargement de Fichiers Clients » dans la liste déroulante des modules.
- Vous pouvez ensuite traduire toutes les chaînes visibles utilisées par le module.

**Q5 : Où les fichiers téléchargés sont-ils stockés sur mon serveur ?**
R : Le module stocke généralement les fichiers dans un dossier dédié au sein de votre installation PrestaShop, souvent nommé `upload` ou `orderfiles_uploads` à l'intérieur du répertoire du module ou d'un répertoire `upload` général. Vous pouvez y accéder via FTP/SFTP, mais il est toujours préférable de les gérer via l'interface du Back Office pour maintenir l'intégrité de la base de données.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Téléchargement de Fichiers Clients » suit une architecture de module PrestaShop standard, tirant parti des principes MVC. Il étend `Module` pour sa fonctionnalité et sa configuration de base, utilise `ModuleFrontController` pour les interactions front-office (téléchargement, gestion des fichiers) et `AdminController` pour la gestion back-office. Les données sont stockées dans le système de fichiers et potentiellement liées via `ps_configuration` pour les paramètres. Le module s'appuie fortement sur le système de hooks de PrestaShop pour injecter sa fonctionnalité dans diverses parties de la boutique.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `controllers/front/customerfiles.php`
  - **Nom de la classe et classe parente :** `CustomerfilesCustomerfilesModuleFrontController` étend `ModuleFrontController`
  - **Responsabilité :** Gère probablement la page principale « Mes fichiers » côté client, affichant une liste de fichiers téléchargés et offrant des options de gestion. Il récupère les fichiers associés au client connecté.
- `controllers/front/download.php`
  - **Nom de la classe et classe parente :** `DownloadCustomerfilesModuleFrontController` étend `ModuleFrontController`
  - **Responsabilité :** Gère les téléchargements de fichiers sécurisés. Il prend un ID de fichier ou un chemin, vérifie les autorisations du client (le cas échéant) et sert le fichier au navigateur, forçant souvent un téléchargement.
- `controllers/front/filesmanager.php`
  - **Nom de la classe et classe parente :** `FilesmanagerCustomerfilesModuleFrontController` étend `ModuleFrontController`
  - **Responsabilité :** Pourrait être une interface générique de gestion de fichiers, potentiellement utilisée pour les appels AJAX liés aux opérations de fichiers (par exemple, la suppression d'un fichier de la vue du client).
- `controllers/front/index.php`
  - **Nom de la classe et classe parente :** `IndexCustomerfilesModuleFrontController` étend `ModuleFrontController`
  - **Responsabilité :** Souvent un espace réservé ou un contrôleur de redirection. Dans certains modules, il peut servir de point d'entrée par défaut ou gérer le routage de base.
- `controllers/front/myfiles.php`
  - **Nom de la classe et classe parente :** `MyfilesCustomerfilesModuleFrontController` étend `ModuleFrontController`
  - **Responsabilité :** Similaire à `customerfiles.php`, cela gère probablement la section spécifique « Mes fichiers » dans le compte client, affichant leurs fichiers téléchargés et potentiellement un formulaire de téléchargement.
- `controllers/front/thumb.php`
  - **Nom de la classe et classe parente :** `ThumbCustomerfilesModuleFrontController` étend `ModuleFrontController`
  - **Responsabilité :** Génère et sert des miniatures pour les fichiers image téléchargés, améliorant les performances et l'affichage sur les pages de liste de fichiers.
- `controllers/front/upload.php`
  - **Nom de la classe et classe parente :** `UploadCustomerfilesModuleFrontController` étend `ModuleFrontController`
  - **Responsabilité :** Le gestionnaire de téléchargement principal. Il reçoit les téléchargements de fichiers (via AJAX ou soumission de formulaire standard), valide le type et la taille du fichier, déplace le fichier vers le répertoire désigné et enregistre les informations du fichier dans la base de données.

#### Contrôleurs d'administration Back-Office

- `controllers/admin/customerFiles.php`
  - **Nom de l'onglet et entité gérée :** « Fichiers clients » (ou similaire). Ce contrôleur gère la vue principale de la grille de tous les fichiers téléchargés par les clients dans le Back Office. Il fournit des fonctionnalités pour lister, filtrer, afficher les détails, télécharger et supprimer des fichiers.
  - **Clés de configuration associées :** `PS_SHOP_EMAIL`, `PS_SHOP_NAME` (pour les notifications par e-mail), `OF_CEMAIL_CUSTOMER`, `OF_CEMAIL_ATTACH` (probablement lié aux paramètres de modèle d'e-mail pour les notifications client).
- `controllers/admin/index.php`
  - **Nom de la classe et classe parente :** `IndexCustomerfilesModuleAdminController` étend `ModuleAdminController`
  - **Nom de l'onglet et entité gérée :** Similaire à `index.php` du front-office, cela pourrait être un espace réservé ou un contrôleur de redirection pour la section d'administration du module.

### 4.3 Classes et modèles de base (`classes/`)

L'inventaire fourni n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que le module pourrait utiliser `ObjectModel` directement dans le fichier de module principal ou les contrôleurs d'administration, ou qu'il s'agit d'une structure de module héritée où la gestion des données est intégrée. Si les données sont stockées dans une table personnalisée, la méthode `install()` du module principal définirait son schéma.

### 4.4 Actifs JavaScript (`views/js/`)

- `js/jquery.form.js`
  - **Portée :** Probablement Front-office et Back-office.
  - **Explication :** Un plugin jQuery pour soumettre facilement des formulaires via AJAX, y compris les téléchargements de fichiers. Il gère les complexités de `multipart/form-data` et fournit des rappels de progression.
- `js/orders.js`
  - **Portée :** Back-office (spécifiquement les pages de détails de commande).
  - **Explication :** Ce script ajoute probablement des fonctionnalités à la page de détails de commande de PrestaShop, telles que l'affichage de la section des fichiers téléchargés, la gestion des téléchargements de fichiers côté administrateur, ou potentiellement la possibilité pour les administrateurs de télécharger des fichiers vers une commande.
- `js/script-customers.js`
  - **Portée :** Front-office (pages de compte client).
  - **Explication :** Gère la logique côté client pour la section « Mes fichiers » dans le compte client, y compris l'affichage des listes de fichiers, la gestion des actions de suppression et l'initiation de nouveaux téléchargements.
- `js/script.js`
  - **Portée :** Front-office (général, pages produit, panier) et potentiellement configuration Back-office.
  - **Explication :** Un script polyvalent pour le module. Il initialise probablement les formulaires de téléchargement, gère la validation des fichiers (taille, type) avant la soumission, affiche la progression du téléchargement et gère les interactions de l'interface utilisateur liées aux téléchargements de fichiers à divers emplacements du front-office.

### 4.5 Feuilles de style CSS (`views/css/`)

- `css/ajaxuploader.css`
  - **Portée :** Front-office.
  - **Explication :** Styles pour l'interface de téléchargement de fichiers basée sur AJAX, y compris les barres de progression, les zones de glisser-déposer et les éléments d'entrée de fichier.
- `css/backoffice.css`
  - **Portée :** Back-office.
  - **Explication :** Styles spécifiques pour les pages d'administration du module, telles que la grille du « Gestionnaire de fichiers clients », les formulaires de configuration et l'intégration dans la page de détails de commande.
- `css/orderfiles.css`
  - **Portée :** Front-office.
  - **Explication :** Style général pour les composants front-office du module, y compris les listes de fichiers, les boutons et les messages affichés aux clients.
- `css.css`
  - **Portée :** Front-office.
  - **Explication :** Pourrait être une feuille de style héritée ou générale, contenant potentiellement les styles de base pour les éléments visuels du module.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

- `displayProductPageUploadFormSmall.tpl` : Rend un formulaire de téléchargement compact sur la page produit.
- `filesmanager-orderhistory.tpl` : Affiche la section de gestion/téléchargement de fichiers dans la page de détails de l'historique des commandes du client.
- `force-redirect.tpl` : Un template utilitaire, éventuellement pour gérer les redirections après certaines actions ou pour afficher des messages avant la redirection.
- `header.tpl` : Injecté dans `displayHeader`, généralement pour charger les actifs CSS/JS ou les balises meta requis par le module.
- `my-account-17.tpl` : Rend le lien ou le bloc « Mes fichiers » dans le tableau de bord du compte client pour PrestaShop 1.7.x et versions ultérieures.
- `my-account.tpl` : Rend le lien ou le bloc « Mes fichiers » dans le tableau de bord du compte client pour les anciennes versions de PrestaShop (1.5.x, 1.6.x).
- `orderConfirmation.tpl` : Affiche le formulaire de téléchargement ou la liste des fichiers sur la page de confirmation de commande.
- `product-files-button.tpl` : Rend un bouton ou un lien sur la page produit qui pourrait ouvrir un modal de téléchargement ou rediriger vers une section de téléchargement.
- `product-files.tpl` : Affiche une liste de fichiers associés à un produit ou un formulaire de téléchargement sur la page produit.
- `shopping-cart-force-files-alert.tpl` : Affiche une alerte dans le panier si des fichiers obligatoires sont manquants pour certains produits.
- `shopping-cart-qty-infos-alert.tpl` : Potentiellement lié aux alertes pour les exigences de fichiers basées sur la quantité dans le panier.
- `shopping-cart.tpl` : Affiche le formulaire de téléchargement ou la liste des fichiers sur la page de résumé du panier.
- `tab.tpl` : Un template d'onglet générique, éventuellement utilisé pour afficher un onglet « Fichiers » sur les pages produit ou dans le compte client.

#### Templates d'administration (`views/templates/admin/`)

- `admin.tpl` : Template d'administration général, éventuellement pour la page de configuration principale du module ou un tableau de bord.
- `adminOrderDetailUpload.tpl` : Intègre la section de téléchargement/gestion de fichiers dans la page de détails de commande de PrestaShop dans le Back Office.
- `boscript.tpl` : Contient du JavaScript spécifique au Back Office, potentiellement pour initialiser des formulaires ou gérer AJAX sur les pages d'administration.
- `bulk-delete-files.tpl` : Template pour une confirmation ou une interface de suppression en masse dans le gestionnaire de fichiers d'administration.
- `comments_cartfiles.tpl` : Affiche les commentaires ou les notes liés aux fichiers téléchargés pour un panier spécifique.
- `comments_orderfiles.tpl` : Affiche les commentaires ou les notes liés aux fichiers téléchargés pour une commande spécifique.
- `comments_productfiles.tpl` : Affiche les commentaires ou les notes liés aux fichiers téléchargés pour un produit spécifique.
- `customerfilesmanager.tpl` : Le template principal pour la vue de la grille du « Gestionnaire de fichiers clients » dans le Back Office.
- `_configure/helpers/list/list_action_details.tpl` : Template pour un bouton d'action « détails » dans un helper de liste.
- `_configure/helpers/list/list_content.tpl` : Template pour le contenu principal d'un helper de liste (par exemple, les lignes de la liste de fichiers).
- `_configure/prestashopbug/helpers/list/*.tpl` : Ces templates (`list.tpl`, `list_action_delete.tpl`, `list_action_details.tpl`, `list_content.tpl`, `list_footer.tpl`, `list_header.tpl`) suggèrent une implémentation de helper de liste personnalisée ou surchargée, éventuellement pour répondre à des besoins d'affichage spécifiques ou à des bugs dans les anciennes versions de PrestaShop.

#### Templates Front-office (`views/templates/front/`)

- `access-denied.tpl` : Affiche un message lorsqu'un client tente d'accéder à un fichier ou à une page sans les autorisations appropriées.
- `customerfilesmanager.tpl` : Le template principal pour la page « Mes fichiers » du client, affichant ses fichiers téléchargés et ses options de gestion.
- `filesmanager.tpl` : Un template de gestionnaire de fichiers générique, potentiellement utilisé pour divers scénarios de liste et de téléchargement de fichiers front-office.
- `my-files.tpl` : Un autre template pour la section « Mes fichiers » du client, probablement similaire à `customerfilesmanager.tpl` ou utilisé en conjonction.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module crée probablement au moins une table personnalisée pour stocker les métadonnées sur les fichiers téléchargés. Une structure de table typique serait `ps_orderfiles` (ou similaire), contenant des champs comme :
    - `id_order_file` (Clé primaire)
    - `id_customer` (Clé étrangère vers `ps_customer`)
    - `id_order` (Clé étrangère vers `ps_order`, nullable)
    - `id_product` (Clé étrangère vers `ps_product`, nullable)
    - `filename` (Nom original du fichier)
    - `filepath` (Chemin d'accès au fichier stocké sur le serveur)
    - `filesize` (Taille en octets)
    - `file_extension`
    - `date_add` (Horodatage du téléchargement)
    - `comment` (Commentaire facultatif du client ou de l'administrateur)
  - Les paramètres de configuration sont stockés dans `ps_configuration` avec des clés comme `OF_CEMAIL_CUSTOMER`, `OF_CEMAIL_ATTACH` et d'autres paramètres spécifiques au module.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Injecter du CSS, du JavaScript et potentiellement des balises meta pour le module. |
| `displayProductAdditionalInfo` (ou hook de page produit similaire) | Sur la page produit, généralement sous la description du produit ou le bouton d'ajout au panier. | Afficher le formulaire de téléchargement ou le bouton spécifique au produit. |
| `displayShoppingCartFooter` (ou hook de page panier similaire) | Sur la page de résumé du panier. | Afficher le formulaire de téléchargement ou la liste des fichiers à l'échelle du panier. |
| `displayOrderConfirmation` | Sur la page de confirmation de commande après un achat réussi. | Afficher le formulaire de téléchargement post-achat. |
| `displayCustomerAccount` | Dans le tableau de bord « Mon compte » du client. | Ajouter un lien ou un bloc vers la section « Mes fichiers ». |
| `displayMyAccountBlock` (PrestaShop 1.6.x) | Dans le tableau de bord « Mon compte » du client. | Ajouter un lien ou un bloc vers la section « Mes fichiers ». |
| `displayRightColumn` / `displayLeftColumn` | Dans les colonnes latérales de la boutique. | Afficher un bouton/lien général « Télécharger des fichiers » si configuré. |
| `displayFooter` | Dans le pied de page de chaque page. | Afficher un bouton/lien général « Télécharger des fichiers » si configuré. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | Potentiellement utilisé pour lier les fichiers téléchargés au nouvel ID de commande créé ou déclencher des notifications d'administrateur. |
| `actionProductUpdate` / `actionProductAdd` | Lorsqu'un produit est mis à jour ou ajouté. | Pourrait être utilisé pour gérer les exigences de fichiers spécifiques au produit ou nettoyer les fichiers associés. |
| `actionCustomerAccountAdd` | Lorsqu'un nouveau compte client est créé. | (Moins probable pour ce module, mais possible pour la configuration initiale). |
| `actionAdminOrdersView` | Lorsqu'un administrateur consulte une commande dans le Back Office. | Injecter la section de gestion de fichiers du module dans la page de détails de commande. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Téléchargement de Fichiers Clients », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à garantir que votre module fonctionne parfaitement et vous aide à maximiser le potentiel de votre boutique.
