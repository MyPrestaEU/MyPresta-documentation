---
title: "Export Products Pro - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Export Products Pro par MyPresta.eu."
sidebar:
  label: "Export Products Pro - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Export Products Pro sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/export-products-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/export-products-pro/)
>
> ---


# Export Products Pro

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour le fonctionnement général de PrestaShop, mais ce module n'a pas d'exigences exotiques spécifiques au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Export Products Pro)

C'est l'écran de configuration principal où vous définissez le comportement général et les paramètres de vos exportations de produits.

#### Paramètres généraux

- **Format d'exportation** :

  - **Ce que fait ce paramètre :** Détermine le format de fichier de vos données exportées.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque défini sur CSV :* Le module générera un fichier de valeurs séparées par des virgules, largement compatible avec les logiciels de feuille de calcul comme Excel, Google Sheets ou LibreOffice Calc. C'est le format le plus courant et le plus polyvalent.
    - *Lorsque défini sur XML :* Le module générera un fichier Extensible Markup Language, souvent utilisé pour un échange de données plus structuré entre systèmes ou pour des flux de produits spécifiques (par exemple, Google Shopping).
  - **Valeur recommandée :** CSV pour une utilisation générale et une analyse en feuille de calcul. XML si vous avez un système spécifique qui l'exige.
  - **Scénario / exemple pour le marchand :** Si vous souhaitez ouvrir les données dans Excel pour analyser les prix, choisissez CSV. Si vous créez un flux pour une application tierce qui spécifie XML, choisissez XML.
- **Délimiteur** :

  - **Ce que fait ce paramètre :** Ce caractère sépare les différentes colonnes (champs) de votre fichier CSV.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque défini sur virgule (,) :* Chaque élément de données d'une ligne sera séparé par une virgule. C'est la norme pour de nombreux systèmes.
    - *Lorsque défini sur point-virgule (;) :* Chaque élément de données sera séparé par un point-virgule. C'est courant dans certaines régions européennes ou lorsque des virgules peuvent apparaître dans vos données de produit (par exemple, dans les descriptions), ce qui peut entraîner des problèmes d'analyse.
  - **Valeur recommandée :** Virgule (`,`) dans la plupart des cas. Si votre logiciel de feuille de calcul a du mal à ouvrir correctement le CSV, essayez le point-virgule (`;`).
  - **Scénario / exemple pour le marchand :** Si vous ouvrez votre CSV dans Excel et que toutes les données apparaissent dans une seule colonne, essayez de changer le délimiteur en point-virgule et de réexporter.
- **Exporter uniquement les produits actifs** :

  - **Ce que fait ce paramètre :** Contrôle si seuls les produits actuellement visibles et achetables sur votre boutique sont inclus dans l'exportation.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque activé (Oui) :* Seuls les produits dont le « Statut » est défini sur « En ligne » ou « Actif » dans votre back office PrestaShop seront exportés. C'est utile pour l'inventaire actuel.
    - *Lorsque désactivé (Non) :* Tous les produits, y compris ceux marqués comme inactifs ou désactivés, seront exportés. C'est utile pour une sauvegarde complète du catalogue ou un audit.
  - **Valeur recommandée :** Oui, pour la plupart des exportations opérationnelles.
  - **Scénario / exemple pour le marchand :** Si vous générez un flux de produits pour Google Shopping, vous ne voulez que les produits actifs, alors activez ceci. Si vous effectuez une sauvegarde complète des données, désactivez-le.
- **Exporter uniquement les produits en stock** :

  - **Ce que fait ce paramètre :** Filtre l'exportation pour n'inclure que les produits dont la quantité est actuellement supérieure à zéro.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque activé (Oui) :* Seuls les produits actuellement en stock seront exportés.
    - *Lorsque désactivé (Non) :* Les produits seront exportés quelle que soit leur quantité de stock (en stock ou en rupture de stock).
  - **Valeur recommandée :** Oui, si vous créez un flux pour les ventes ou la disponibilité actuelle.
  - **Scénario / exemple pour le marchand :** Si vous envoyez une liste de produits disponibles à un dropshipper, activez ceci. Si vous avez besoin de voir tous les produits, y compris ceux que vous devez réapprovisionner, désactivez-le.
- **Exporter les images de produits** :

  - **Ce que fait ce paramètre :** Détermine si les URL de vos images de produits sont incluses dans l'exportation.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque activé (Oui) :* Le fichier CSV/XML contiendra des colonnes avec les URL de vos images de produits.
    - *Lorsque désactivé (Non) :* Les URL des images seront omises, ce qui réduira la taille du fichier si les images ne sont pas nécessaires.
  - **Valeur recommandée :** Oui, si vous avez besoin d'images pour les places de marché ou les catalogues externes.
  - **Scénario / exemple pour le marchand :** Si vous mettez à jour un catalogue de produits sur une autre plateforme qui nécessite des URL d'images, activez ceci.
- **Exporter la description courte du produit** :

  - **Ce que fait ce paramètre :** Inclut la description courte (résumé) de vos produits dans l'exportation.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque activé (Oui) :* La description courte de chaque produit sera incluse en tant que colonne.
    - *Lorsque désactivé (Non) :* La description courte sera omise.
  - **Valeur recommandée :** Oui, car les descriptions courtes sont souvent utilisées pour les listes de produits et les résultats de recherche.
  - **Scénario / exemple pour le marchand :** Si vous créez un flux de produits pour un site de comparaison qui affiche des descriptions courtes, activez ceci.
- **Exporter la description du produit** :

  - **Ce que fait ce paramètre :** Inclut la description complète et détaillée de vos produits dans l'exportation.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque activé (Oui) :* La description complète du produit sera incluse en tant que colonne.
    - *Lorsque désactivé (Non) :* La description complète sera omise.
  - **Valeur recommandée :** Oui, pour une exportation complète des données.
  - **Scénario / exemple pour le marchand :** Si vous migrez votre boutique vers une nouvelle plateforme et avez besoin de tout le contenu des produits, activez ceci.
- **Mémoriser les paramètres** :

  - **Ce que fait ce paramètre :** Si activé, le module enregistrera vos derniers paramètres d'exportation utilisés (filtres, champs sélectionnés) pour votre prochaine exportation.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque activé (Oui) :* Le module pré-remplira le formulaire d'exportation avec vos choix précédents, ce qui vous fera gagner du temps pour les exportations répétitives.
    - *Lorsque désactivé (Non) :* Le formulaire d'exportation se réinitialisera toujours aux paramètres par défaut chaque fois que vous le visiterez.
  - **Valeur recommandée :** Oui, si vous effectuez fréquemment des exportations similaires.
  - **Scénario / exemple pour le marchand :** Si vous exportez régulièrement une liste de produits actifs et en stock avec des champs spécifiques, l'activation de cette option accélérera votre flux de travail.

#### Options de filtrage

- **Exporter les produits de la catégorie** :

  - **Ce que fait ce paramètre :** Vous permet de sélectionner des catégories de produits spécifiques à inclure dans votre exportation.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque des catégories spécifiques sont sélectionnées :* Seuls les produits appartenant à ces catégories seront exportés.
    - *Lorsque aucune catégorie n'est sélectionnée (ou toutes sont sélectionnées) :* Tous les produits, quelle que soit leur catégorie, seront pris en compte pour l'exportation (sous réserve d'autres filtres).
  - **Valeur recommandée :** Sélectionnez des catégories spécifiques si vous avez besoin d'une exportation ciblée ; sinon, laissez non sélectionné pour un catalogue complet.
  - **Scénario / exemple pour le marchand :** Si vous ne souhaitez exporter que les produits de votre catégorie « Électronique », sélectionnez-la ici.
- **Exporter uniquement les catégories parentes** :

  - **Ce que fait ce paramètre :** Si vous avez sélectionné des catégories, cette option affine davantage si les produits des sous-catégories sont également inclus.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque activé (Oui) :* Seuls les produits directement attribués aux catégories parentes sélectionnées seront exportés. Les produits de leurs sous-catégories seront exclus.
    - *Lorsque désactivé (Non) :* Les produits des catégories parentes sélectionnées ET de toutes leurs sous-catégories seront exportés.
  - **Valeur recommandée :** Non, dans la plupart des cas, car vous souhaitez généralement aussi les produits des sous-catégories. Activez uniquement si vous avez une raison spécifique d'exclure les produits des sous-catégories.
  - **Scénario / exemple pour le marchand :** Si vous avez « Vêtements » comme catégorie parente et « T-shirts » comme sous-catégorie, l'activation de cette option exporterait les produits directement dans « Vêtements » mais pas ceux dans « T-shirts ».
- **Exporter les produits du fabricant** :

  - **Ce que fait ce paramètre :** Vous permet de filtrer les produits par leur fabricant attribué.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque des fabricants spécifiques sont sélectionnés :* Seuls les produits de ces fabricants seront exportés.
    - *Lorsque aucun fabricant n'est sélectionné (ou tous sont sélectionnés) :* Les produits de tous les fabricants seront pris en compte.
  - **Valeur recommandée :** Sélectionnez des fabricants spécifiques pour des exportations ciblées.
  - **Scénario / exemple pour le marchand :** Si vous devez envoyer une liste de produits à une marque spécifique pour examen, sélectionnez son fabricant ici.
- **Exporter les produits du fournisseur** :

  - **Ce que fait ce paramètre :** Vous permet de filtrer les produits par leur fournisseur attribué.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque des fournisseurs spécifiques sont sélectionnés :* Seuls les produits de ces fournisseurs seront exportés.
    - *Lorsque aucun fournisseur n'est sélectionné (ou tous sont sélectionnés) :* Les produits de tous les fournisseurs seront pris en compte.
  - **Valeur recommandée :** Sélectionnez des fournisseurs spécifiques pour des exportations ciblées.
  - **Scénario / exemple pour le marchand :** Si vous devez fournir une liste de produits que vous stockez auprès d'un fournisseur particulier, sélectionnez-le ici.

### 2.2 Écran d'administration dédié : Tableau de bord Export Products Pro (Back Office > Catalogue > Export Products Pro)

C'est l'interface principale pour initier et gérer vos exportations de produits.

- **Nom de l'écran et emplacement du menu :** **Catalogue > Export Products Pro**
- **Actions et paramètres disponibles :**
  - **Bouton Exporter :** C'est le bouton d'action principal. Cliquer dessus lancera le processus d'exportation en fonction des paramètres que vous avez configurés sur cette page.
  - **Sélection des champs :** Sous les paramètres généraux, vous trouverez une liste complète de tous les champs de produit et de déclinaison disponibles. Vous pouvez cocher ou décocher individuellement les champs que vous souhaitez inclure dans votre exportation.
    - **Champs de produit :** Inclut les détails standard du produit comme l'ID, le nom, la référence, l'EAN13, l'UPC, le prix, la quantité, le poids, les descriptions, etc.
    - **Champs de déclinaison :** Si vos produits ont des déclinaisons (par exemple, taille, couleur), vous verrez des champs spécifiques aux déclinaisons comme « ID de déclinaison », « Attribut (Nom:Type:Position) », « Valeur (Valeur:Position) », « Impact sur le prix », « Impact sur le poids », « Par défaut (0 = Non, 1 = Oui) », « Date de disponibilité de la déclinaison ».
  - **Effet des modifications :**
    - **Sélectionner/Désélectionner des champs :** Seuls les champs cochés apparaîtront comme colonnes dans votre fichier CSV/XML exporté. Cela vous permet de créer des exportations hautement personnalisées, n'incluant que les données dont vous avez besoin et omettant les informations inutiles.
  - **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1. Naviguez vers **Catalogue > Export Products Pro**.
    2. Passez en revue les « Paramètres généraux » et les « Options de filtrage » en haut de la page. Ajustez-les en fonction de si vous avez besoin de produits actifs, de produits en stock, de catégories spécifiques, de fabricants ou de fournisseurs.
    3. Sélectionnez soigneusement les « Champs de produit » et les « Champs de déclinaison » que vous souhaitez inclure dans votre exportation. Si vous n'êtes pas sûr, il est souvent plus sûr de sélectionner plus de champs initialement, puis de supprimer les colonnes indésirables dans votre logiciel de feuille de calcul.
    4. Cliquez sur le bouton « Exporter ». Le module générera et vous invitera à télécharger le fichier CSV ou XML.
    5. Ouvrez le fichier téléchargé dans votre logiciel de feuille de calcul préféré (par exemple, Excel, Google Sheets) pour vérifier les données et le format.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Format d'exportation | CSV | Détermine le type de fichier de sortie (CSV ou XML). |
| | Délimiteur | Virgule (`,`) | Caractère séparant les champs dans le CSV. À modifier si des problèmes d'analyse surviennent. |
| | Exporter uniquement les produits actifs | Oui | Inclut uniquement les produits actifs. |
| | Exporter uniquement les produits en stock | Oui | Inclut uniquement les produits avec une quantité > 0. |
| | Exporter les images de produits | Oui | Inclut les URL des images dans l'exportation. |
| | Exporter la description courte du produit | Oui | Inclut la description courte du produit. |
| | Exporter la description du produit | Oui | Inclut la description complète du produit. |
| | Mémoriser les paramètres | Oui | Enregistre vos derniers choix d'exportation pour plus de commodité. |
| | Exporter les produits de la catégorie | (Aucun sélectionné) | Filtre l'exportation par catégories sélectionnées. |
| | Exporter uniquement les catégories parentes | Non | Si des catégories sont sélectionnées, inclut/exclut les produits des sous-catégories. |
| | Exporter les produits du fabricant | (Aucun sélectionné) | Filtre l'exportation par fabricants sélectionnés. |
| | Exporter les produits du fournisseur | (Aucun sélectionné) | Filtre l'exportation par fournisseurs sélectionnés. |
| **Tableau de bord Export Products Pro** | **Sélection des champs** | Varie selon les besoins | Choisissez des attributs de produit/déclinaison spécifiques à inclure comme colonnes dans le fichier d'exportation. |
| | Bouton Exporter | N/A | Lance l'exportation des produits en fonction de tous les paramètres configurés. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mon fichier CSV exporté semble illisible ou toutes les données sont dans une seule colonne lorsque je l'ouvre dans Excel.**
**R1 :** Il s'agit généralement d'un problème de délimiteur ou d'encodage de caractères.

- **Solution 1 (Délimiteur) :** Retournez à la configuration du module, changez le paramètre « Délimiteur » de virgule (`,`) à point-virgule (`;`), et réexportez. Essayez d'ouvrir le nouveau fichier.
- **Solution 2 (Encodage) :** Lorsque vous ouvrez le CSV dans Excel, utilisez l'option « Données > À partir de texte/CSV ». Dans l'assistant d'importation, assurez-vous de sélectionner la bonne « Origine du fichier » ou « Encodage » (généralement `UTF-8`) et de spécifier le bon délimiteur.

**Q2 : Certains produits sont manquants dans mon exportation, mais je sais qu'ils existent dans ma boutique.**
**R2 :** Vérifiez vos paramètres de filtre dans la configuration du module :

- **Solution :** Assurez-vous que « Exporter uniquement les produits actifs » et « Exporter uniquement les produits en stock » sont correctement définis pour vos besoins. Si vous avez sélectionné des catégories, des fabricants ou des fournisseurs spécifiques, vérifiez que les produits manquants correspondent à ces filtres. Si vous voulez tout, assurez-vous qu'aucun filtre n'est sélectionné.

**Q3 : Le processus d'exportation prend beaucoup de temps ou expire pour les grands catalogues.**
**R3 :** L'exportation de milliers de produits peut être gourmande en ressources.

- **Solution 1 :** Essayez d'exporter par petits lots en utilisant les filtres « Exporter les produits de la catégorie », « du fabricant » ou « du fournisseur ».
- **Solution 2 :** Si vous avez accès aux paramètres de votre serveur, vous devrez peut-être augmenter temporairement `memory_limit` et `max_execution_time` de PHP dans votre fichier `php.ini`. Contactez votre hébergeur pour obtenir de l'aide à ce sujet.
- **Solution 3 :** Désélectionnez les champs inutiles pour réduire la quantité de données traitées.

**Q4 : Comment traduire les en-têtes de colonne dans le fichier exporté ?**
**R4 :** Les en-têtes de colonne dans le fichier exporté sont généralement basés sur les noms de champs internes ou les étiquettes PrestaShop par défaut, et ne sont pas directement traduisibles via l'interface du module.

- **Solution :** Le moyen le plus simple est d'ouvrir le fichier CSV exporté dans un programme de feuille de calcul (comme Excel ou Google Sheets) et de renommer manuellement les en-têtes de colonne dans la langue ou la terminologie souhaitée. Enregistrez le fichier avec les nouveaux en-têtes.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de la structure technique du module Export Products Pro, destinée aux développeurs, webmasters et agences techniques.

### 4.1 Aperçu de l'architecture

Le module `Export Products Pro` suit le modèle MVC standard de PrestaShop, se concentrant principalement sur les fonctionnalités du back-office. Il utilise les contrôleurs d'administration pour son interface utilisateur et des classes personnalisées pour la gestion des données et la génération de flux. La logique principale du module réside dans son fichier `exportproducts.php` et le contrôleur `AdminExportProductsController` qui gère le processus d'exportation et la configuration. Il utilise `ObjectModel` pour ses données personnalisées, le cas échéant, bien que dans ce cas, il interagisse principalement avec les données de produits PrestaShop de base.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `controllers/front/feed.php`
  - **Nom de la classe et classe parente :** `ExportProductsFeedModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur est probablement responsable de la génération d'un flux de produits (par exemple, XML ou CSV) qui peut être accédé directement via une URL. Il gérerait la logique de requête des produits en fonction de paramètres spécifiques et de leur sortie dans le format choisi. Cela pourrait être utilisé pour la génération automatisée de flux pour des services externes.
- `controllers/front/index.php`
  - **Nom de la classe et classe parente :** `ExportProductsIndexModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur pourrait servir de point d'entrée par défaut ou de solution de repli pour les requêtes front-office liées au module. Compte tenu de la fonction principale du module, il pourrait rediriger ou afficher un simple message, ou il pourrait être un espace réservé pour de futures fonctionnalités front-office.

#### Contrôleurs d'administration Back-Office

- `controllers/admin/AdminExportProducts.php`
  - **Nom de l'onglet et entité gérée :** Ce contrôleur gère le tableau de bord principal « Export Products Pro » dans le Back Office de PrestaShop, accessible via **Catalogue > Export Products Pro**. Il ne gère pas une seule entité `ObjectModel` au sens traditionnel, mais orchestre plutôt le processus d'exportation des produits.
  - **Responsabilité :**
    - Affiche le formulaire de configuration pour les paramètres d'exportation (filtres, format, délimiteur, etc.).
    - Gère la requête POST lorsque le bouton « Exporter » est cliqué.
    - Traite les champs de produit et de déclinaison sélectionnés.
    - Interroge la base de données PrestaShop pour les données de produit et de déclinaison en fonction des filtres appliqués.
    - Génère le contenu du fichier CSV ou XML.
    - Lance le téléchargement du fichier vers le navigateur de l'utilisateur.
    - Gère la fonctionnalité `ep_remember_settings` pour conserver les choix de l'utilisateur.
- `controllers/admin/index.php`
  - **Responsabilité :** Il s'agit généralement d'un fichier vide ou d'un fichier contenant une simple instruction `die('No direct script access');`, servant de mesure de sécurité pour empêcher l'accès direct au répertoire `controllers/admin`. Il ne contient pas de logique de contrôleur active.

### 4.3 Classes et modèles de base (`classes/`)

- `classes/ExportProductsFeed.php`
  - **Avec quelle table de base de données il interagit :** Cette classe interagit probablement avec diverses tables PrestaShop de base telles que `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_manufacturer`, `ps_supplier`, `ps_image`, `ps_product_attribute`, `ps_product_attribute_combination`, `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang`, etc.
  - **Si elle étend `ObjectModel` et la définition des champs `$definition` :** Il est peu probable qu'elle étende `ObjectModel` directement, car son rôle principal est d'*interroger* et de *traiter* les données de produits existantes plutôt que de gérer une nouvelle entité de base de données. Elle contiendrait des méthodes pour récupérer les données de produits avec diverses jointures (catégories, fabricants, fournisseurs, images, descriptions).
  - **Méthodes publiques clés et logique métier encapsulée :**
    - Méthodes pour récupérer les données de produits avec diverses jointures (catégories, fabricants, fournisseurs, images, descriptions).
    - Méthodes pour gérer les déclinaisons de produits et leurs attributs spécifiques.
    - Logique pour appliquer les filtres (actif, en stock, catégorie, fabricant, fournisseur).
    - Méthodes pour formater les données en structures CSV ou XML.
    - Potentiellement des méthodes pour gérer de grands ensembles de données afin d'éviter l'épuisement de la mémoire.
- `classes/index.php`
  - **Responsabilité :** Similaire à `controllers/admin/index.php`, il s'agit d'un fichier de sécurité pour empêcher la liste directe des répertoires ou l'exécution de fichiers dans le répertoire `classes/`.

### 4.4 Actifs JavaScript (`views/js/`)

L'inventaire des modules fourni n'indique aucun fichier JavaScript personnalisé (`[]`). Cela suggère que le front-end du module (configuration du Back Office) repose entièrement sur les bibliothèques JavaScript natives de PrestaShop (par exemple, jQuery, le JS de base de PrestaShop) pour la gestion des formulaires, ou que son interface est suffisamment simple pour ne pas nécessiter d'interactions complexes côté client au-delà des soumissions de formulaires standard.

### 4.5 Feuilles de style CSS (`views/css/`)

L'inventaire des modules fourni n'indique aucun fichier CSS personnalisé (`[]`). Cela implique que l'interface du Back Office du module utilise le style par défaut du back-office de PrestaShop, garantissant une apparence cohérente sans introduire de styles personnalisés.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **`exportproducts/script.tpl`**
  - **Portée :** Probablement un modèle générique utilisé pour intégrer de petits extraits JavaScript ou des variables de configuration directement dans le HTML, éventuellement accroché à `displayHeader` ou `displayBackOfficeHeader` s'il doit s'exécuter sur des pages spécifiques. Étant donné qu'il n'y a pas de fichiers JS, cela pourrait contenir du JS en ligne pour la validation de formulaire ou un comportement dynamique.
- **`exportproducts/views/templates/admin/dashboard.tpl`**
  - **Portée :** Modèle d'administration.
  - **Objectif :** C'est le modèle principal pour le `AdminExportProductsController`. Il rend l'intégralité du formulaire de configuration d'exportation, y compris les paramètres généraux, les options de filtre et la liste étendue des champs de produit et de déclinaison que le marchand peut sélectionner pour l'exportation. Il contient également le bouton « Exporter ».
- **`exportproducts/views/templates/admin/form_header.tpl`**
  - **Portée :** Modèle d'administration.
  - **Objectif :** Ce modèle rend probablement une section d'en-tête commune pour les formulaires de configuration d'administration, y compris potentiellement le titre du module, la description, et peut-être un texte d'introduction ou des liens. Il est conçu pour être inclus en haut d'autres modèles d'administration (comme `dashboard.tpl`) pour la cohérence.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne semble pas créer ses propres tables de base de données personnalisées.
  - Il stocke ses paramètres de configuration (par exemple, `ep_export_format`, `ep_export_active`, `ep_remember_settings`, `ep_export_categories_onlycats`, etc.) dans la table standard `ps_configuration` de PrestaShop. Ces clés sont préfixées par `ep_` pour « Export Products ».
  - Il lit principalement les données des tables PrestaShop de base : `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_manufacturer`, `ps_supplier`, `ps_image`, `ps_product_attribute`, `ps_product_attribute_combination`, `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang`, etc.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayModuleRoutes` | Pendant la génération des routes pour les modules. | Permet au module d'enregistrer des URL conviviales personnalisées pour ses contrôleurs front-office (par exemple, `/feed` pour `feed.php`). |
| `moduleRoutes` | Pendant la génération des routes pour les modules. | Similaire à `displayModuleRoutes`, utilisé pour définir des modèles d'URL personnalisés et les associer aux contrôleurs de module. |
| `displayBackOfficeHeader` | Rend le contenu dans la section `<head>` du Back Office. | Potentiellement utilisé pour inclure `script.tpl` pour du JS ou CSS en ligne, ou pour ajouter des balises meta ou des variables JS spécifiques nécessaires à l'interface d'administration. |
| `actionAdminControllerSetMedia` | Avant qu'un contrôleur d'administration ne rende sa page. | Utilisé pour enregistrer les fichiers CSS et JavaScript pour le Back Office, en s'assurant qu'ils ne sont chargés que lorsque cela est nécessaire. (Bien qu'aucun fichier JS/CSS ne soit listé, ce hook serait l'endroit standard s'ils étaient présents). |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module **Export Products Pro**, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à assurer le bon fonctionnement et l'amélioration continue de nos modules.
