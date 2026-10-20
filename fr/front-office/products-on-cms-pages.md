---
title: "Produits sur les pages CMS - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Produits sur les pages CMS par MyPresta.eu."
sidebar:
  label: "Produits sur les pages CMS - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Products on CMS pages sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/products-on-cms-pages.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/products-on-cms-pages/)
>
> ---


# Produits sur les pages CMS

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises par PrestaShop lui-même et sont suffisantes pour ce module.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Produits sur les pages CMS » dans le Gestionnaire de modules. Vous verrez l'écran de configuration principal.

#### **Masquer les produits et les shortcodes**

- **Ce que fait ce paramètre :** Ce paramètre contrôle si le module traite et affiche les produits à partir des shortcodes que vous avez placés dans vos pages CMS. Il affecte également si les shortcodes eux-mêmes sont visibles pour les clients si le module ne les traite pas.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Le module ne traitera *pas* les shortcodes. Au lieu d'afficher les listes de produits, les shortcodes (par exemple, `[products ids="1,2,3"]`) seront masqués de la vue du client sur le front office. Ceci est utile si vous souhaitez désactiver temporairement l'affichage des produits sans supprimer les shortcodes de votre contenu CMS.
  - *Lorsqu'il est désactivé (NON) :* Le module recherchera et traitera activement les shortcodes dans vos pages CMS. Il les remplacera par les listes de produits correspondantes, rendant vos produits visibles pour les clients.
- **Valeur recommandée :** **NON** (sauf si vous souhaitez spécifiquement masquer les listes de produits et les shortcodes).
- **Scénario / exemple pour le marchand :**
  - Vous avez configuré plusieurs pages CMS avec des shortcodes de produits pour une promotion saisonnière. Lorsque la promotion se termine, au lieu de modifier manuellement chaque page CMS pour supprimer les shortcodes, vous pouvez simplement activer « Masquer les produits et les shortcodes » pour masquer instantanément toutes les listes de produits de ces pages. Lorsque la prochaine promotion commence, vous le désactivez à nouveau.

### 2.2 Comment utiliser les shortcodes dans vos pages CMS

Ce module n'a pas d'écrans d'administration dédiés au-delà de la configuration principale. Sa fonctionnalité principale est contrôlée par des « shortcodes » que vous insérez directement dans le contenu de votre page CMS.

**Pour ajouter des produits à une page CMS :**

1. Naviguez vers **Paramètres de la boutique > Pages CMS** dans votre Back Office PrestaShop.
2. Modifiez une page CMS existante ou créez-en une nouvelle.
3. Dans l'éditeur de contenu principal (généralement un éditeur de texte enrichi comme TinyMCE), vous pouvez taper ou coller les shortcodes.

**Shortcodes disponibles :**

- **Afficher des produits spécifiques par ID :**

  - `[products ids="1,2,3,4"]`
  - **Objectif :** Ce shortcode vous permet d'afficher une liste de produits spécifiques par leurs numéros d'identification uniques. Vous pouvez trouver les ID de produits dans votre Back Office sous **Catalogue > Produits**.
  - **Exemple :** Si vous souhaitez afficher le Produit A (ID 1), le Produit B (ID 2) et le Produit C (ID 3), vous utiliseriez `[products ids="1,2,3"]`.
- **Afficher les produits d'une catégorie spécifique :**

  - `[products category="5"]`
  - **Objectif :** Ce shortcode affiche tous les produits appartenant à une catégorie spécifique. Vous pouvez trouver les ID de catégorie dans votre Back Office sous **Catalogue > Catégories** en modifiant une catégorie et en regardant l'URL ou la colonne « ID » dans la liste des catégories.
  - **Exemple :** Pour afficher tous les produits de votre catégorie « Électronique » (en supposant que son ID est 5), vous utiliseriez `[products category="5"]`.
- **Afficher les produits d'un fabricant/marque spécifique :**

  - `[products manufacturer="1"]`
  - **Objectif :** Ce shortcode affiche tous les produits associés à un fabricant ou une marque particulière. Les ID de fabricant peuvent être trouvés sous **Catalogue > Marques & Fournisseurs > Marques**.
  - **Exemple :** Pour afficher tous les produits de « Apple » (en supposant que son ID est 1), vous utiliseriez `[products manufacturer="1"]`.
- **Afficher les nouveaux produits :**

  - `[products new="5"]`
  - **Objectif :** Ce shortcode affiche les produits les plus récemment ajoutés à votre boutique. Le nombre « 5 » indique combien de nouveaux produits vous souhaitez afficher.
  - **Exemple :** Pour afficher les 5 produits les plus récents, utilisez `[products new="5"]`.
- **Afficher les produits les plus vendus :**

  - `[products bestseller="5"]`
  - **Objectif :** Ce shortcode affiche vos produits les plus vendus. Le nombre « 5 » indique combien de produits les plus vendus vous souhaitez afficher.
  - **Exemple :** Pour afficher vos 5 produits les plus vendus, utilisez `[products bestseller="5"]`.
- **Afficher les produits en promotion :**

  - `[products sale="5"]`
  - **Objectif :** Ce shortcode affiche les produits actuellement en promotion. Le nombre « 5 » indique combien de produits en promotion vous souhaitez afficher.
  - **Exemple :** Pour afficher 5 produits actuellement en promotion, utilisez `[products sale="5"]`.
- **Afficher les produits phares (de la page d'accueil) :**

  - `[products featured="5"]`
  - **Objectif :** Ce shortcode affiche les produits marqués comme « phares » sur votre page d'accueil (généralement contrôlés par le module « Produits phares »). Le nombre « 5 » indique combien de produits phares vous souhaitez afficher.
  - **Exemple :** Pour afficher 5 de vos produits phares, utilisez `[products featured="5"]`.

**Notes importantes :**

- Vous pouvez combiner des shortcodes sur la même page, mais chaque shortcode générera sa propre liste de produits.
- Assurez-vous qu'il n'y a pas d'espaces supplémentaires ou de fautes de frappe dans les crochets des shortcodes `[]`.
- Après avoir ajouté les shortcodes, enregistrez votre page CMS. Les produits apparaîtront automatiquement sur le front office (sauf si vous avez activé « Masquer les produits et les shortcodes » dans la configuration du module).

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Masquer les produits et les shortcodes | NON | Contrôle si les listes de produits des shortcodes sont affichées (NON) ou masquées (OUI) sur les pages CMS. |
| Éditeur de page CMS | `[products ids="1,2,3"]` | N/A | Affiche des produits spécifiques par leurs ID. |
| Éditeur de page CMS | `[products category="5"]` | N/A | Affiche tous les produits d'une catégorie spécifique. |
| Éditeur de page CMS | `[products manufacturer="1"]` | N/A | Affiche tous les produits d'un fabricant spécifique. |
| Éditeur de page CMS | `[products new="5"]` | N/A | Affiche les 5 produits les plus récents. |
| Éditeur de page CMS | `[products bestseller="5"]` | N/A | Affiche les 5 produits les plus vendus. |
| Éditeur de page CMS | `[products sale="5"]` | N/A | Affiche les 5 produits actuellement en promotion. |
| Éditeur de page CMS | `[products featured="5"]` | N/A | Affiche les 5 produits phares de la page d'accueil. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes produits n'apparaissent pas sur la page CMS, mais les shortcodes sont visibles.**
R : Vérifiez la page de configuration du module (**Modules > Gestionnaire de modules > Configurer** pour « Produits sur les pages CMS »). Assurez-vous que « Masquer les produits et les shortcodes » est défini sur **NON**. S'il est défini sur OUI, le module masquera les produits et les shortcodes eux-mêmes. Vérifiez également la syntaxe de votre shortcode pour toute faute de frappe ou guillemets manquants.

**Q : Mes produits n'apparaissent pas, et les shortcodes non plus (juste un espace vide).**
R : Cela signifie généralement que le module est actif et essaie de traiter les shortcodes, mais qu'il rencontre un problème.
1. **Vider le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » en haut à droite.
2. **Vérifier les ID de produit/catégorie :** Assurez-vous que les ID que vous utilisez dans `[products ids="..."]`, `[products category="..."]` ou `[products manufacturer="..."]` sont corrects et correspondent à des produits/catégories/fabricants existants et actifs dans votre boutique.
3. **Visibilité du produit :** Assurez-vous que les produits que vous essayez d'afficher sont actifs et visibles dans votre boutique (non désactivés, en rupture de stock si la gestion des stocks est stricte, ou définis comme « cachés »).

**Q : Les produits apparaissent, mais leur style ne correspond pas à celui de mon thème.**
R : Le module utilise un style de base, mais le CSS de votre thème peut le remplacer ou entrer en conflit avec lui.
1. **Personnalisation du thème :** La plupart des thèmes ont des options pour le CSS personnalisé. Vous ou votre webmaster pouvez ajouter des règles CSS personnalisées pour cibler les listes de produits générées par ce module.
2. **Contacter le développeur du thème :** Si vous n'êtes pas sûr, contactez le développeur de votre thème pour obtenir des conseils sur la meilleure façon de styliser les grilles de produits.
3. **Contacter le support MyPresta.eu :** Si vous suspectez un problème de style spécifique au module, contactez le support MyPresta.eu.

**Q : Puis-je utiliser plusieurs shortcodes sur la même page CMS ?**
R : Oui, vous pouvez utiliser autant de shortcodes différents que vous le souhaitez sur une seule page CMS. Chaque shortcode générera sa propre liste de produits distincte.

**Q : Ce module prend-il en charge les boutiques multilingues ?**
R : Oui, le module fonctionne avec les capacités multilingues de PrestaShop. Les noms et descriptions de produits affichés seront dans la langue sélectionnée par le client, tout comme sur les pages de produits ou de catégories normales. Les shortcodes eux-mêmes (`[products ids="..."]`) restent les mêmes dans toutes les langues.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Vue d'ensemble de l'architecture

Le module « Produits sur les pages CMS » fonctionne principalement en surchargeant le `CmsController` principal pour intercepter et traiter le contenu avant qu'il ne soit rendu à l'utilisateur. Il utilise des expressions régulières pour trouver des shortcodes spécifiques dans le contenu de la page CMS et les remplace par des listes de produits générées dynamiquement. Les données de produit sont récupérées à l'aide des méthodes `Product::getProducts` et `Product::getProductsProperties` de PrestaShop, puis rendues via des templates Smarty.

### 4.2 Contrôleurs (`controllers/`)

Ce module utilise une surcharge pour étendre les fonctionnalités de base de PrestaShop.

- **Contrôleurs Front-Office** :

  - `cmsproducts/override/controllers/front/CmsController.php`
    - **Nom de la classe et classe parente** : `CmsController` (surcharge `CmsControllerCore`)
    - **Responsabilité** : C'est le cœur de la fonctionnalité du module. Il surcharge la méthode `initContent()` du `CmsController` standard. Dans `initContent()`, il récupère le contenu de la page CMS, le scanne pour les shortcodes définis (par exemple, `[products ids="..."]`), traite ces shortcodes en récupérant les données de produit pertinentes, puis remplace les shortcodes par le HTML de produit rendu avant que le contenu de la page ne soit affiché. Il s'assure également que le CSS du module est chargé.
  - `cmsproducts/override/controllers/front/index.php`
    - **Nom de la classe et classe parente** : N/A (fichier vide)
    - **Responsabilité** : Il s'agit d'un fichier `index.php` vide standard placé dans les sous-répertoires pour empêcher la liste des répertoires, une pratique de sécurité courante. Il n'a aucun impact fonctionnel sur la logique du module.
- **Contrôleurs d'administration Back-Office** : Aucun. La configuration du module est gérée directement dans la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles de base (`classes/`)

Aucune classe personnalisée ou définition d'`ObjectModel` n'est présente dans ce module. Il utilise les classes de base existantes de PrestaShop comme `Product`, `Category`, `Manufacturer`, `Context`, `Tools` et `Configuration`.

### 4.4 Actifs JavaScript (`views/js/`)

Aucun fichier JavaScript personnalisé n'est inclus dans ce module. Toutes les fonctionnalités sont gérées côté serveur via PHP.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module inclut deux fichiers CSS pour styliser les listes de produits. Ceux-ci sont chargés via le hook `actionAdminControllerSetMedia` (pour le contexte du back-office, bien que la surcharge gère le chargement du front-office).

- `cmsproducts/cmsproducts.css`
  - **Portée** : Style client du front-office.
  - **Principaux composants et conteneurs d'interface utilisateur qu'il stylise** : Contient le style général pour la grille/liste de produits générée par les shortcodes. Cela inclurait les styles pour les conteneurs de produits, les images, les noms, les prix et potentiellement les boutons « Ajouter au panier » pour assurer une apparence cohérente.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger** : Cible probablement des classes comme `.cmsproducts-product-list`, `.cmsproducts-product-item`, `.cmsproducts-product-image`, `.cmsproducts-product-name`, `.cmsproducts-product-price`.
- `cmsproducts/css.css`
  - **Portée** : Style client du front-office.
  - **Principaux composants et conteneurs d'interface utilisateur qu'il stylise** : Similaire à `cmsproducts.css`, ce fichier fournit probablement des règles de style supplémentaires ou spécifiques pour l'affichage des produits, potentiellement pour la réactivité ou des ajustements de mise en page spécifiques.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger** : Similaire à `cmsproducts.css`.

### 4.6 Structure des templates Smarty (`views/templates/`)

Le module utilise des templates Smarty pour rendre les listes de produits.

- **Templates de hook (`views/templates/hook/`)** : Aucun explicitement défini comme templates de hook. Les templates sont rendus directement par la surcharge du `CmsController`.
- **Templates d'administration (`views/templates/admin/`)** : Aucun.
- **Templates Front-office (`views/templates/front/`)** :
  - `cmsproducts/html.tpl`
    - **Objectif** : Ce template sert probablement de wrapper ou de conteneur général pour les listes de produits. Il peut inclure une structure HTML de base entourant les articles de produit.
  - `cmsproducts/products-carousel.tpl`
    - **Objectif** : Ce template est conçu pour afficher les produits sous forme de carrousel ou de slider. Il contiendrait la structure HTML nécessaire et potentiellement l'initialisation JavaScript pour un carrousel de produits. Ce template est probablement utilisé lorsqu'un paramètre de shortcode spécifique ou un paramètre de module (non exposé dans la configuration actuelle) implique un affichage en carrousel.
  - `cmsproducts/products.tpl`
    - **Objectif** : C'est le template principal pour afficher une grille ou une liste standard de produits. Il itère sur les données de produit passées par le contrôleur PHP et affiche les détails individuels du produit (image, nom, prix, bouton d'ajout au panier, etc.). C'est le template le plus couramment utilisé pour les shortcodes `[products ...]` .

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** : Ce module ne crée aucune table de base de données personnalisée. Il stocke ses paramètres de configuration dans la table `ps_configuration` standard.
  - Entrées `ps_configuration` :
    - `mypresta_updates` : Stocke les informations relatives aux mises à jour du module depuis MyPresta.eu.
    - `cmsproducts_hide` : Stocke la valeur du paramètre « Masquer les produits et les shortcodes » (1 pour activé/OUI, 0 pour désactivé/NON).
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses actifs multimédias. | Bien que listé, le chargement CSS principal pour le front office est géré par la surcharge du `CmsController`. Ce hook pourrait être utilisé pour un éventuel style côté administration futur ou si le module avait un contrôleur d'administration. |

La fonctionnalité principale de traitement des shortcodes et de rendu des produits est réalisée via la surcharge du `CmsController`, qui manipule directement le contenu avant l'affichage, plutôt que de s'appuyer sur un hook front-office spécifique pour l'injection de contenu.

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour accéder aux dernières versions du module « Produits sur les pages CMS », veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour aider les marchands et les développeurs avec toutes questions ou problèmes liés au module.
