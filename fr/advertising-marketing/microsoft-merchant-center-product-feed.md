---
title: "Flux de produits Microsoft Merchant Center - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Flux de produits Microsoft Merchant Center' par MyPresta.eu."
sidebar:
  label: "Flux de produits Microsoft Merchant Center - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Microsoft Merchant Center Product Feed sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/microsoft-merchant-center-product-feed.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/microsoft-merchant-center-product-feed/)
>
> ---


# Flux de produits Microsoft Merchant Center

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Extensions PHP standard (cURL, JSON, OpenSSL). Votre serveur doit être capable d'exécuter des tâches cron pour la génération automatisée du flux.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à la page de configuration principale du module. C'est ici que vous définirez le comportement général et accéderez aux outils de gestion des flux.

#### Paramètres généraux

Cette section couvre généralement les paramètres globaux qui affectent le fonctionnement du module et la génération des flux.

- **Ce que fait ce paramètre :** Ce sont les paramètres essentiels qui définissent la manière dont vos données produit sont préparées pour Microsoft Merchant Center. Vous trouverez généralement des options pour sélectionner la langue, la devise et le pays de votre flux, ainsi que des préférences générales d'exportation.
- **Effet de la modification de ce paramètre :**
  - *Langue :* Détermine quelle version linguistique de vos noms de produits, descriptions et catégories sera incluse dans le flux. Crucial pour cibler des marchés internationaux spécifiques.
  - *Devise :* Définit la devise pour tous les prix du flux. Doit correspondre à la devise configurée dans votre compte Microsoft Merchant Center pour le pays cible.
  - *Pays :* Spécifie le pays cible pour le flux. Cela influence les règles fiscales, les paramètres d'expédition et d'autres exigences spécifiques au pays dans Microsoft Merchant Center.
  - *Autres options d'exportation :* Peut inclure des paramètres pour gérer les variantes de produits, exclure certaines catégories ou définir la manière dont des attributs spécifiques (comme la taille ou la couleur) sont exportés.
- **Valeur recommandée :**
  - *Langue, Devise, Pays :* Sélectionnez la langue, la devise et le pays principaux que vous ciblez avec vos annonces Microsoft Shopping. Si vous faites de la publicité dans plusieurs pays/langues, vous créerez probablement des flux distincts pour chacun.
  - *Autres options :* Suivez les recommandations du module ou ajustez en fonction de votre catalogue de produits spécifique et de votre stratégie publicitaire.
- **Scénario / exemple de marchand :** Si vous vendez en France et que la langue par défaut de votre boutique est le français, vous sélectionneriez le français pour la langue, l'EUR pour la devise et la France pour le pays. Si vous vendez également en Allemagne, vous créeriez un flux distinct configuré pour la langue allemande, la devise EUR et l'Allemagne comme pays.

#### Gestion et génération des flux

Cette section donne accès à la création, la gestion et la génération de vos flux de produits.

- **Ce que fait ce paramètre :** C'est le cœur du module, vous permettant de définir et de générer les fichiers de flux de produits réels. Vous trouverez généralement des options pour créer de nouveaux flux, afficher les flux existants et déclencher le processus de génération.
- **Effet de la modification de ce paramètre :**
  - *Création d'un nouveau flux :* Lance le processus de configuration d'un nouveau flux de produits avec ses propres paramètres spécifiques (langue, devise, catégories, etc.).
  - *Génération d'un flux :* Traite les données de vos produits PrestaShop et crée le fichier CSV, XML ou TSV que vous téléchargerez sur Microsoft Merchant Center. Ce fichier contient tous les attributs du produit au format requis par Microsoft.
  - *URL Cron :* Fournit une adresse web spéciale qui, lorsqu'elle est visitée, déclenche automatiquement la génération du flux. Ceci est essentiel pour configurer des mises à jour quotidiennes ou horaires automatisées de votre flux de produits sans intervention manuelle.
- **Valeur recommandée :**
  - Créez au moins un flux pour votre marché cible principal.
  - Configurez une tâche cron à l'aide de l'URL fournie pour vous assurer que votre flux de produits est régulièrement mis à jour (par exemple, quotidiennement) avec les dernières informations sur les produits (niveaux de stock, prix, nouveaux produits).
- **Scénario / exemple de marchand :** Vous venez de lancer une nouvelle gamme de produits. Grâce à une tâche cron quotidienne, vos annonces Microsoft Shopping refléteront automatiquement ces nouveaux produits et leurs niveaux de stock actuels le lendemain, sans que vous ayez à télécharger manuellement le flux.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### AdminExportProductsFeedMicrosoftController (Back Office > Microsoft Merchant Center > Exportation du flux de produits)

C'est l'écran dédié principal pour gérer les détails de vos flux de produits. Vous y accéderez via un nouvel élément de menu ajouté par le module, probablement sous « Catalogue » ou une nouvelle section « Microsoft Merchant Center ».

- **Nom de l'écran et emplacement du menu :** **Back Office > Microsoft Merchant Center > Exportation du flux de produits** (ou similaire, selon la version du module et la structure du menu PrestaShop).
- **Actions et paramètres disponibles :** Cet écran est l'endroit où vous définissez le contenu spécifique et le mappage pour chacun de vos flux de produits. Vous verrez généralement une liste des flux existants, avec des options pour « Ajouter un nouveau flux » ou « Modifier » un flux existant. Lors de l'ajout/modification, vous configurerez :
  - **Nom du flux :** Un nom descriptif pour votre flux (par exemple, « France - Flux français », « USA - Flux anglais »).
  - **Pays cible :** Le pays pour lequel ce flux est destiné (par exemple, France, États-Unis). Cela a un impact sur la devise, la langue et les règles fiscales.
  - **Langue du contenu :** La langue des données produit dans ce flux (par exemple, français, anglais).
  - **Devise :** La devise utilisée pour les prix dans ce flux (par exemple, EUR, USD).
  - **Format de fichier :** Choisissez entre CSV, XML ou TSV, selon les exigences de Microsoft Merchant Center.
  - **Mappage des catégories :** Il s'agit d'une section cruciale où vous mappez vos catégories PrestaShop à la taxonomie des produits de Microsoft. Cela aide Microsoft à comprendre ce que sont vos produits et à les afficher dans les recherches pertinentes.
  - **Filtrage des produits :** Options pour inclure/exclure des produits spécifiques ou des catégories entières du flux.
  - **Mappage des attributs :** Mappez les attributs des produits PrestaShop (comme la taille, la couleur, le matériau) aux attributs requis par Microsoft (par exemple, `size`, `color`, `material`).
  - **Libellés personnalisés :** Définissez jusqu'à 5 libellés personnalisés (`custom_label_0` à `custom_label_4`) pour segmenter vos produits pour les stratégies d'enchères dans Microsoft Ads.
  - **Disponibilité et condition :** Paramètres pour définir la manière dont la disponibilité des produits (en stock, en rupture de stock, en précommande) et la condition (neuf, occasion, reconditionné) sont exportées.
  - **GTIN (Global Trade Item Number) :** Paramètres pour l'exportation des codes EAN/UPC en tant que GTIN.
  - **Marque :** Comment les marques de produits sont exportées.
  - **Description :** Options pour l'exportation des descriptions de produits, souvent avec conversion en texte brut.
  - **Liens d'image :** Comment les images de produits sont liées.
  - **Prix et prix de vente :** Comment les prix réguliers et les prix de vente sont exportés, y compris les considérations fiscales.
  - **URL Cron :** L'URL unique pour ce flux spécifique que vous utiliserez pour les mises à jour automatisées.
- **Effet des modifications :**
  - Les modifications ici ont un impact direct sur le contenu et la structure du fichier de flux de produits généré. Des paramètres incorrects peuvent entraîner des refus de produits dans Microsoft Merchant Center.
  - Un mappage correct des catégories garantit que vos produits apparaissent dans les catégories d'achat pertinentes sur Bing.
  - Des données précises sur les prix et la disponibilité évitent la frustration des clients et les refus d'annonces.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. **Configuration initiale :** Créez un flux pour chaque combinaison pays/langue cible pour laquelle vous faites de la publicité. Mappez soigneusement vos catégories à la taxonomie de Microsoft.
  2. **Vérification des attributs :** Assurez-vous que tous les attributs critiques (GTIN, marque, prix, disponibilité, liens d'image) sont correctement mappés et exportés.
  3. **Configuration des tâches Cron :** Implémentez les URL Cron fournies sur votre serveur d'hébergement pour automatiser la génération quotidienne (ou plus fréquente) du flux. Ceci est essentiel pour maintenir vos données produit à jour.
  4. **Surveillance de Microsoft Merchant Center :** Vérifiez régulièrement votre compte Microsoft Merchant Center pour tout refus ou avertissement de produit, et ajustez les paramètres du module si nécessaire.
  5. **Mises à jour des produits :** Lors de l'ajout de nouveaux produits ou de modifications importantes à des produits existants, assurez-vous que votre tâche cron est en cours d'exécution, ou régénérez manuellement le flux si une mise à jour immédiate est requise.

#### index.php (mmcfeed/controllers/admin/index.php)

Ce contrôleur sert probablement de tableau de bord ou de vue de gestion générale pour le module au sein du Back Office de PrestaShop.

- **Nom de l'écran et emplacement du menu :** Probablement une partie de la section principale du menu « Microsoft Merchant Center », éventuellement la page d'atterrissage par défaut.
- **Actions et paramètres disponibles :** Cet écran affiche probablement un aperçu de vos flux configurés, leur dernière date de génération, leur statut et des liens rapides pour les modifier ou les générer. Il peut également afficher l'état général du module ou des alertes importantes.
- **Effet des modifications :** Cette vue offre un aperçu rapide de la configuration de votre flux. Les actions ici (comme cliquer sur « Générer le flux ») déclencheront le processus de génération du flux.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Utilisez cet écran comme un tableau de bord rapide pour surveiller la santé de vos flux de produits. Si vous avez besoin de déclencher manuellement une mise à jour de flux, c'est ici que vous le feriez.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Langue cible | Langue principale de votre boutique | Détermine la langue des noms de produits, descriptions, etc. |
|  | Devise cible | Devise principale de votre boutique | Définit la devise pour tous les prix du flux. |
|  | Pays cible | Votre marché cible principal | Influence les règles fiscales, d'expédition et spécifiques au pays. |
|  | URL Cron | Fournie par le module | Automatise la génération du flux à intervalles réguliers. |
| **AdminExportProductsFeedMicrosoftController** | Nom du flux | Descriptif (par exemple, « France - FR ») | Identifie le flux spécifique. |
|  | Format de fichier | CSV, XML ou TSV | Choisissez en fonction des exigences de Microsoft Merchant Center. |
|  | Mappage des catégories | Mappez PrestaShop à la taxonomie Microsoft | Garantit que les produits apparaissent dans les catégories d'achat correctes. |
|  | Filtrage des produits | Basé sur votre stratégie | Inclure/exclure des produits ou des catégories spécifiques. |
|  | Mappage des attributs | Mappez PrestaShop aux attributs Microsoft | Fournit des informations détaillées sur les produits pour les annonces. |
|  | Libellés personnalisés (0-4) | Selon les besoins des campagnes publicitaires | Segmente les produits pour les stratégies d'enchères. |
|  | Exportation GTIN | Activé si disponible | Exporte les codes EAN/UPC pour l'identification des produits. |
|  | Date de disponibilité | Activé si applicable | Exporte la date de disponibilité du produit pour les précommandes. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : Mes produits n'apparaissent pas dans les annonces Microsoft Shopping. Que dois-je vérifier ?**
R :

1. **Statut de téléchargement du flux :** Tout d'abord, vérifiez votre compte Microsoft Merchant Center pour vous assurer que votre flux a été téléchargé et traité avec succès sans erreurs majeures.
2. **Refus de produits :** Recherchez tout refus de produits dans la section « Diagnostics » de Microsoft Merchant Center. Ceux-ci vous indiqueront exactement pourquoi les produits ne s'affichent pas. Les raisons courantes incluent des GTIN manquants, des liens d'image incorrects ou des violations de politique.
3. **Configuration du module :** Vérifiez que les paramètres de votre module (langue, devise, pays, mappage des catégories) sont corrects et correspondent aux paramètres de votre compte Microsoft Merchant Center.
4. **Génération du flux :** Assurez-vous que le flux est généré correctement par le module. Essayez de le générer manuellement et de vérifier le fichier de sortie.
5. **Campagnes publicitaires :** Confirmez que vos campagnes Microsoft Ads sont actives, correctement ciblées et liées au bon flux de produits.

**Q : Les prix ou les niveaux de stock de mes produits sont obsolètes dans les annonces Microsoft Shopping.**
R : Cela signifie généralement que votre flux de produits n'est pas mis à jour assez fréquemment.

1. **Tâche Cron :** Assurez-vous que votre tâche cron est correctement configurée sur votre serveur d'hébergement et qu'elle s'exécute à la fréquence souhaitée (par exemple, quotidiennement). Le module fournit une URL unique pour cela.
2. **Génération manuelle :** Si vous avez effectué des modifications urgentes, vous pouvez régénérer manuellement le flux depuis la page de configuration du module et le télécharger à nouveau sur Microsoft Merchant Center (si vous n'utilisez pas de récupérations planifiées).

**Q : Certains de mes produits sont manquants dans le flux.**
R :

1. **Exclusion de catégorie :** Vérifiez si les catégories contenant ces produits ont été accidentellement exclues dans les paramètres du module.
2. **Statut du produit :** Assurez-vous que les produits sont actifs, visibles et en stock dans votre boutique PrestaShop. Les produits marqués comme « désactivés » ou « en rupture de stock » (selon vos paramètres) peuvent être exclus.
3. **Filtres spécifiques :** Examinez tous les filtres de produits spécifiques que vous avez pu appliquer dans la configuration du module.

**Q : Comment mapper mes catégories PrestaShop à la taxonomie des produits de Microsoft ?**
R : Dans l'écran de configuration du flux du module, il y aura une section pour le « Mappage des catégories ». Vous verrez généralement une liste de vos catégories PrestaShop. Pour chacune, vous devrez sélectionner la catégorie la plus appropriée dans la liste de taxonomie prédéfinie de Microsoft. C'est une étape cruciale pour la pertinence des annonces. Prenez votre temps pour bien faire les choses.

**Q : Mon thème personnalisé cause des problèmes d'affichage avec l'interface d'administration du module.**
R : Bien que l'impact du module sur le front-office soit nul, son interface de back-office peut parfois entrer en conflit avec des thèmes d'administration fortement personnalisés.

1. **Vider le cache :** Tout d'abord, essayez de vider le cache Smarty de votre PrestaShop (Paramètres avancés > Performances > Vider le cache).
2. **Thème par défaut :** Basculez temporairement votre thème de back-office vers le thème PrestaShop par défaut pour voir si le problème persiste. Si cela résout le problème, le conflit est avec votre thème d'administration personnalisé.
3. **Contacter le support :** Si le problème persiste, rassemblez des captures d'écran et des détails et contactez le support de MyPresta.eu pour obtenir de l'aide.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module `Flux de produits Microsoft Merchant Center` (`mmcfeed`) suit une architecture de module PrestaShop standard, utilisant principalement les contrôleurs d'administration pour la gestion du back-office et les contrôleurs frontaux pour générer le flux de produits via des tâches cron. Il n'introduit pas de nouvelles classes `ObjectModel` mais interroge plutôt les données produit PrestaShop existantes et les formate selon les spécifications de Microsoft Merchant Center. Le module s'appuie fortement sur les valeurs de configuration stockées dans `ps_configuration` et utilise des templates Smarty pour le rendu des interfaces d'administration et potentiellement des parties de la logique de génération de flux (bien que les flux soient généralement générés par programme).

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `mmcfeed/controllers/front/feed.php`
  - **Nom de la classe et classe parente :** `MmcfeedFeedModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur est le point d'entrée principal pour la génération du flux de produits. Il est conçu pour être appelé via une URL unique (l'« URL cron ») pour la génération automatisée du flux. Il gère la logique d'interrogation des données produit, l'application des règles de filtrage et de mappage définies dans le back-office, et la sortie du flux de produits dans le format spécifié (CSV, XML, TSV). Il ne rend généralement pas de page visuelle mais produit des données brutes.
- `mmcfeed/controllers/front/index.php`
  - **Nom de la classe et classe parente :** `MmcfeedIndexModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Il s'agit d'un contrôleur frontal de substitution ou de secours. Dans de nombreux modules, `index.php` dans un répertoire de contrôleur sert de point d'entrée par défaut ou simple. Il peut rediriger ou simplement renvoyer une réponse vide si aucune action spécifique n'est définie. Son rôle fonctionnel direct dans la génération de flux est probablement minimal par rapport à `feed.php`.

#### Contrôleurs d'administration Back-Office

- `mmcfeed/controllers/admin/AdminExportProductsFeedMicrosoft.php`
  - **Nom de l'onglet et entité gérée :** Gère la configuration et la génération des flux de produits individuels de Microsoft Merchant Center. Il crée un nouvel élément de menu dans le back-office de PrestaShop.
  - **Responsabilité :** Ce contrôleur gère les opérations CRUD pour les configurations de flux de produits. Il affiche la liste des flux configurés, permet d'ajouter de nouveaux flux, de modifier ceux existants et de déclencher leur génération. Il traite les soumissions de formulaires pour définir des paramètres spécifiques au flux tels que le pays cible, la langue, la devise, le format de fichier, le mappage des catégories, le filtrage des produits et le mappage des attributs (par exemple, `gtin`, `identifier_exists`, `title`, `availability`, `brand`, `link`, `image_link`, `description`, `product_type`, `condition`, `price`, `sale_price`, `tax rate`, `custom_label_0`, `google_product_category`). Il interagit avec `ps_configuration` pour stocker ces paramètres et orchestre la récupération et le formatage des données pour le processus de génération du flux.
- `mmcfeed/controllers/admin/index.php`
  - **Nom de l'onglet et entité gérée :** Probablement un tableau de bord ou une page d'aperçu pour le module dans le back-office de PrestaShop.
  - **Responsabilité :** Ce contrôleur sert probablement de point d'entrée principal pour l'interface d'administration du module, fournissant un résumé des flux configurés, de leur statut et des actions rapides. Il peut rendre un template de type tableau de bord (`dashboard.tpl`) pour donner un aperçu de l'activité du module.

### 4.3 Classes et modèles principaux (`classes/`)

Les informations fournies n'indiquent aucune classe ou modèle personnalisé dans le répertoire `classes/`. Cela suggère que le module fonctionne principalement en interrogeant directement les classes `ObjectModel` principales de PrestaShop (`Product`, `Category`, `Language`, `Currency`, etc.) et `ps_configuration` pour ses paramètres. La logique de traitement des données et de génération de flux est probablement encapsulée dans le fichier de module principal `mmcfeed.php` et les contrôleurs admin/front.

### 4.4 Actifs JavaScript (`views/js/`)

- `mmcfeed/lib/searchTool/views/js/autocomplete.js`
  - **Portée :** Back-office.
  - **Responsabilité :** Fournit une fonctionnalité d'autocomplétion, probablement pour la recherche de produits, de catégories ou d'attributs dans les formulaires de configuration du module. Cela améliore l'expérience utilisateur lors du mappage de catégories ou du filtrage de produits. Il se lie aux champs de saisie et effectue des requêtes AJAX pour récupérer des suggestions.
- `mmcfeed/views/js/admin-app.js`
  - **Portée :** Back-office.
  - **Responsabilité :** Il s'agit du fichier JavaScript principal pour l'interface back-office du module. Il gère divers éléments interactifs, les validations de formulaires, le chargement de contenu dynamique (par exemple, les modales Fancybox pour la sélection de catégories) et les appels AJAX liés à la sauvegarde des configurations ou au déclenchement de la génération de flux. Il lie probablement des écouteurs d'événements aux boutons, sélecteurs et champs de saisie dans les formulaires du contrôleur `AdminExportProductsFeedMicrosoft`.

### 4.5 Feuilles de style CSS (`views/css/`)

- `mmcfeed/lib/searchTool/views/css/autocomplete.css`
  - **Portée :** Style des formulaires d'administration du back-office.
  - **Responsabilité :** Style les listes déroulantes d'autocomplétion et les champs de saisie utilisés par le script `autocomplete.js`, garantissant une apparence cohérente et conviviale dans le back-office de PrestaShop.
- `mmcfeed/views/admin-theme.css`
  - **Portée :** Style des formulaires d'administration du back-office.
  - **Responsabilité :** Fournit des ajustements de style généraux et des remplacements pour les pages du back-office du module afin de s'intégrer de manière transparente au thème d'administration de PrestaShop. Il peut définir des styles pour la mise en page, les boutons, les tableaux et les éléments de formulaire spécifiques au module.
- `mmcfeed/views/css/admin-app.css`
  - **Portée :** Style des formulaires d'administration du back-office.
  - **Responsabilité :** Contient des styles spécifiques pour les composants d'interface utilisateur personnalisés et les mises en page du module dans le panneau d'administration, tels que les interfaces de mappage de catégories, les listes d'exclusion de produits ou les éléments de tableau de bord. Il fonctionne en conjonction avec `admin-theme.css` pour fournir l'identité visuelle du module dans le back-office.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** : Aucun explicitement listé, ce qui indique que le module ne rend pas de contenu directement dans les hooks front-office standard.
- **Templates d'administration (`views/templates/admin/`)** :
  - `mmcfeed/views/templates/admin/dashboard.tpl` : Probablement le template de tableau de bord principal rendu par `controllers/admin/index.php`, fournissant un aperçu du module et de ses flux configurés.
  - `mmcfeed/views/templates/admin/feeds.tpl` : Rend probablement la liste des flux de produits gérés par `AdminExportProductsFeedMicrosoftController`, affichant leur statut, la dernière date de génération et les actions.
  - `mmcfeed/views/templates/admin/form-chrome.tpl` : Un template générique pour envelopper les formulaires dans l'interface d'administration de PrestaShop, offrant un style et une structure cohérents (par exemple, en-tête, pied de page, boutons de sauvegarde).
  - `mmcfeed/views/templates/admin/layout.tpl` : Un template de mise en page de base pour les pages d'administration du module, définissant la structure globale, y compris les en-têtes, les menus et les zones de contenu.
- **Autres templates (`views/`)** :
  - `mmcfeed/lib/searchTool/views/scripts.tpl` : Contient du code JavaScript ou des inclusions de scripts liés à la fonctionnalité de l'outil de recherche/autocomplétion.
  - `mmcfeed/views/categories-fancybox.tpl` : Rend le contenu d'une modale Fancybox utilisée pour la sélection ou le mappage de catégories, fournissant probablement une structure arborescente pour une navigation facile.
  - `mmcfeed/views/category_taxonomy.tpl` : Un template partiel utilisé dans `categories-fancybox.tpl` ou le formulaire de configuration du flux principal pour afficher et gérer le mappage des catégories PrestaShop à la taxonomie de Microsoft.
  - `mmcfeed/views/exclude-products.tpl` : Rend l'interface pour sélectionner et gérer les produits à exclure du flux.
  - `mmcfeed/views/google_lang_links.tpl` : Ce nom de template est curieux pour un module Microsoft. Il pourrait s'agir d'un vestige d'un module Google Merchant Center ou d'un composant générique pour gérer les liens spécifiques à la langue, potentiellement pour les URL de flux elles-mêmes.
  - `mmcfeed/views/returnAlert.tpl` : Un template générique pour afficher des messages de succès ou d'erreur à l'utilisateur dans le back-office.
  - `mmcfeed/views/script-fancybox.tpl` : Contient du code JavaScript ou des inclusions de scripts spécifiquement pour la bibliothèque Fancybox, utilisée pour les popups modales.
  - `mmcfeed/views/script.tpl` : Un template d'inclusion de script général, potentiellement pour des variables JavaScript ou des initialisations à l'échelle du module.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne crée pas de tables SQL personnalisées sur la base des informations fournies.
  - Toutes les configurations du module sont stockées dans la table `ps_configuration`, en utilisant des clés préfixées par `mmc_` (par exemple, `mmc_pf_tree`, `mmc_mmcfeed_products`, `mmc_export_size_attribute`, `mmc_export_exclude_categories`, `mmc_export_availability_date`).
  - Il interagit avec les tables PrestaShop standard telles que `ps_product`, `ps_product_lang`, `ps_category`, `ps_category_lang`, `ps_image`, `ps_stock_available`, `ps_attribute_group`, `ps_attribute`, `ps_feature`, `ps_feature_value`, `ps_manufacturer`, `ps_tax_rule`, etc., pour récupérer les données produit.
- **Table des hooks enregistrés** :
  Le module utilise principalement des hooks de back-office pour son interface d'administration et potentiellement des hooks `action` pour la logique interne. Les hooks de front-office ne sont pas utilisés pour le rendu de contenu, mais le contrôleur frontal du module `feed.php` agit comme un point d'entrée direct pour les services externes (comme les tâches cron).

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` des pages front-office. | *Non utilisé pour le rendu de contenu.* S'il est enregistré, probablement pour le chargement interne de JS/CSS, mais la fonction principale du module est la génération de flux, pas l'affichage front-office. |
| `displayRightColumn` | Dans la colonne de droite des pages front-office. | *Non utilisé pour le rendu de contenu.* |
| `displayLeftColumn` | Dans la colonne de gauche des pages front-office. | *Non utilisé pour le rendu de contenu.* |
| `displayFooter` | Dans le pied de page des pages front-office. | *Non utilisé pour le rendu de contenu.* |
| `displayAdminProductsExtra` | Sur la page d'édition de produit dans le back-office. | *Potentiellement utilisé* pour ajouter un onglet ou une section pour les exclusions ou les remplacements de flux spécifiques aux produits. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration est initialisé et avant le chargement de ses médias (JS/CSS). | Utilisé pour enregistrer les fichiers JavaScript (`admin-app.js`, `autocomplete.js`) et CSS (`admin-app.css`, `admin-theme.css`, `autocomplete.css`) spécifiques au module pour l'interface back-office. |
| `actionModuleInstall` | Lors de l'installation du module. | Pour créer des entrées de configuration dans `ps_configuration` et potentiellement enregistrer des onglets d'administration. |
| `actionModuleUninstall` | Lors de la désinstallation du module. | Pour nettoyer les entrées de configuration et supprimer les onglets d'administration. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | *Improbable pour ce module.* S'il est présent, ce serait pour le suivi des conversions ou la mise à jour des données de flux en fonction des ventes, mais ce n'est pas une fonction essentielle pour un générateur de flux. |
| `actionProductUpdate` | Après la mise à jour d'un produit. | *Potentiellement utilisé* pour déclencher un indicateur de régénération de flux ou pour mettre à jour les caches internes si le module en maintient. |
| `actionProductAdd` | Après l'ajout d'un nouveau produit. | *Potentiellement utilisé* pour déclencher un indicateur de régénération de flux ou pour mettre à jour les caches internes. |
| `displayAdminNavBarBefore` | Avant la barre de navigation principale dans le back-office. | *Potentiellement utilisé* pour ajouter un lien rapide ou une notification liée au module. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). MyPresta.eu fournit un support dédié pour tous les modules achetés, garantissant que votre boutique reste à jour et fonctionnelle.
