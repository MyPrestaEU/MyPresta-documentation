---
title: "Accès aux produits - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Accès aux produits' par MyPresta.eu."
sidebar:
  label: "Accès aux produits - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Access to Products sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/access-to-products.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/access-to-products/)
>
> ---


# Accès aux produits

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises par PrestaShop lui-même et sont suffisantes pour ce module.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Accès aux produits)

C'est l'écran de configuration principal où vous définissez les règles d'accès aux produits.

#### Paramètres généraux

| Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- |
| **Activer le module** | OUI | **Objectif :** Active ou désactive la fonctionnalité du module.   **Effet :**   *Lorsqu'il est activé :* Toutes vos restrictions configurées seront actives sur le front office.   *Lorsqu'il est désactivé :* Le module n'aura aucun effet, et tous les produits seront visibles et achetables par tous les clients, quel que soit le groupe.   **Recommandé :** OUI, une fois que vous avez configuré vos règles. |
| **Bloquer la possibilité de voir la page produit** | NON | **Objectif :** Contrôle si les clients ne faisant pas partie des groupes autorisés peuvent même voir la page dédiée du produit.   **Effet :**   *Lorsqu'il est activé :* Si un client ne faisant pas partie d'un groupe autorisé tente d'accéder directement à la page produit (par exemple, via un lien ou un moteur de recherche), il sera redirigé ou verra un message d'accès refusé.   *Lorsqu'il est désactivé :* Les clients non autorisés peuvent toujours consulter la page produit, mais ils seront empêchés de l'ajouter à leur panier.   **Recommandé :** OUI pour les produits véritablement exclusifs, NON si vous voulez qu'ils voient le produit mais ne l'achètent pas (par exemple, « contactez-nous pour le prix de gros »). |
| **Masquer le produit sur les listes de produits** | NON | **Objectif :** Détermine si les produits restreints sont masqués des pages de catégorie, des résultats de recherche et d'autres listes de produits pour les clients non autorisés.   **Effet :**   *Lorsqu'il est activé :* Les produits n'apparaîtront tout simplement pas dans les listes de produits pour les clients ne faisant pas partie des groupes autorisés.   *Lorsqu'il est désactivé :* Les produits apparaîtront dans les listes, mais lorsque le client cliquera dessus, il sera soit bloqué de la visualisation de la page (si « Bloquer la possibilité de voir la page produit » est OUI), soit bloqué de l'ajout au panier.   **Recommandé :** OUI pour une expérience de navigation plus propre et plus ciblée pour chaque groupe de clients. |
| **Message pour les clients non autorisés** | « Vous n'êtes pas autorisé à commander ce produit. » | **Objectif :** Le texte affiché aux clients qui tentent d'ajouter un produit restreint à leur panier ou de consulter une page produit restreinte (si « Bloquer la possibilité de voir la page produit » est NON).   **Effet :** Ce message apparaît dans le panier à côté du produit restreint ou sur la page produit.   **Recommandé :** Un message clair et poli. Vous pouvez le personnaliser pour expliquer pourquoi (par exemple, « Ce produit est réservé aux clients grossistes. Veuillez vous connecter à votre compte grossiste. »). |

#### Tableau des restrictions de produits

Cette section affiche une liste de tous les produits pour lesquels vous avez défini des restrictions d'accès. Vous pouvez ajouter de nouvelles restrictions ou modifier celles existantes ici.

- **Nom du produit :** Le nom du produit faisant l'objet de la restriction.
- **Groupes de clients autorisés :** Une liste des groupes de clients qui *sont* autorisés à voir et/ou acheter ce produit.
- **Actions :** Modifier (icône crayon) ou Supprimer (icône poubelle) la restriction.

#### Ajout/Modification de restrictions de produits

Lorsque vous cliquez sur « Ajouter une nouvelle restriction » ou sur l'icône « Modifier » pour une restriction existante, vous verrez un formulaire :

- **Sélectionner le produit :**

  - **Ce que fait ce paramètre :** Vous permet de rechercher et de sélectionner le produit spécifique que vous souhaitez restreindre.
  - **Effet de la modification de ce paramètre :** Cela lie la règle de restriction à un produit particulier de votre catalogue.
  - **Valeur recommandée :** Sélectionnez le produit exact.
  - **Scénario marchand :** Vous souhaitez restreindre le « Mélange de café en gros » à vos clients grossistes. Vous recherchez et sélectionnez « Mélange de café en gros ».
- **Sélectionner les groupes de clients :**

  - **Ce que fait ce paramètre :** Une liste de tous les groupes de clients définis dans votre boutique PrestaShop (par exemple, Visiteur, Invité, Client, Grossiste, VIP). Vous sélectionnez lesquels de ces groupes *sont autorisés* à accéder au produit.
  - **Effet de la modification de ce paramètre :** Seuls les clients appartenant aux groupes sélectionnés pourront interagir avec le produit selon vos paramètres généraux (voir, ajouter au panier). Tous les autres groupes seront restreints.
  - **Valeur recommandée :** Sélectionnez uniquement les groupes qui devraient avoir accès.
  - **Scénario marchand :** Pour le « Mélange de café en gros », vous sélectionneriez « Grossiste ». Si vous vouliez également que les VIP aient accès, vous sélectionneriez « Grossiste » et « VIP ».

Après avoir fait vos sélections, cliquez sur **« Enregistrer »** pour appliquer la restriction.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
|---|---|---|
| Configuration du module | Activer le module | OUI | Active/désactive toutes les fonctionnalités du module. |
| Configuration du module | Bloquer la possibilité de voir la page produit | NON (considérer OUI pour l'exclusivité) | Empêche les clients non autorisés de voir la page produit. |
| Configuration du module | Masquer le produit sur les listes de produits | NON (considérer OUI pour un affichage ciblé) | Masque les produits restreints des résultats de catégorie/recherche pour les clients non autorisés. |
| Configuration du module | Message pour les clients non autorisés | « Vous n'êtes pas autorisé à commander ce produit. » | Message personnalisable affiché aux clients non autorisés. |
| Tableau des restrictions de produits | Sélectionner le produit | N/A | Choisissez le produit auquel appliquer les restrictions. |
| Tableau des restrictions de produits | Sélectionner les groupes de clients | N/A | Définissez quels groupes de clients sont *autorisés* à accéder au produit sélectionné. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai configuré des restrictions, mais elles ne semblent pas fonctionner. Que dois-je faire ?**
R :

1.  **Vérifier l'état du module :** Assurez-vous que « Activer le module » est défini sur OUI dans la configuration du module.
2.  **Vider le cache :** Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop. Cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures). C'est crucial pour que les modifications prennent effet.
3.  **Affectation du groupe de clients :** Vérifiez que le client avec lequel vous testez est correctement affecté au groupe de clients prévu (Clients > Clients, puis modifiez le client).
4.  **Sélection du produit :** Vérifiez que vous avez sélectionné le bon produit dans les paramètres de restriction du module.
5.  **Cache du navigateur :** Essayez de vider le cache de votre navigateur ou de tester dans une fenêtre de navigation privée/incognito pour exclure les problèmes de cache côté client.

**Q : Comment traduire le « Message pour les clients non autorisés » dans d'autres langues ?**
R :

1.  Allez dans **International > Traductions** dans votre Back Office PrestaShop.
2.  Sélectionnez « Traductions des modules installés » comme Type de traduction.
3.  Choisissez votre thème.
4.  Sélectionnez la langue que vous souhaitez traduire.
5.  Recherchez le module « Accès aux produits ». Vous devriez y voir le champ du message, prêt à être traduit.

**Q : Ce module va-t-il ralentir ma boutique ?**
R : Le module est conçu pour être léger et efficace. Il s'intègre directement à la logique de base des produits et du panier de PrestaShop. Tout impact sur les performances devrait être négligeable, surtout après la mise en cache. Si vous remarquez des ralentissements importants, assurez-vous que votre serveur répond aux exigences minimales de PrestaShop et que vous utilisez une version PHP récente.

**Q : Que se passe-t-il si un client fait partie de plusieurs groupes, et qu'un groupe est autorisé tandis qu'un autre ne l'est pas ?**
R : Si un client appartient à *n'importe quel* groupe explicitement autorisé à accéder à un produit, il aura accès. Le module accorde l'accès si *l'un quelconque* des groupes du client correspond à un groupe autorisé pour ce produit. C'est une logique « OU » : si le Groupe A est autorisé OU le Groupe B est autorisé, et que le client est dans le Groupe A, il obtient l'accès.

**Q : Puis-je restreindre l'accès à des catégories entières au lieu de produits individuels ?**
R : Ce module se concentre sur les restrictions de produits individuels. Pour restreindre des catégories entières, vous devrez appliquer la restriction à chaque produit de cette catégorie. Pour les restrictions au niveau de la catégorie, vous pourriez avoir besoin d'un module différent ou d'un développement personnalisé.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module « Accès aux produits » (`pga`) fonctionne principalement en surchargeant les classes PrestaShop de base pour injecter sa logique de contrôle d'accès. Il utilise l'`ObjectModel` de PrestaShop pour le stockage de la configuration et modifie la visibilité des produits et le comportement du panier à des points clés du cycle de vie des requêtes du front-office. La logique principale du module réside dans `index.php` (le fichier principal du module) et ses surcharges.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur front-office ou back-office personnalisé. Toute la configuration est gérée via la méthode `getContent()` dans le fichier principal du module (`pga/index.php`).

### 4.3 Classes et modèles de base (`classes/`)

Le module utilise le mécanisme de surcharge de PrestaShop pour modifier le comportement de base.

- `pga/override/classes/Pack.php`

  - **Nom de la classe :** `Pack` (surcharge la classe `Pack` de PrestaShop)
  - **Responsabilité :** Cette surcharge modifie probablement la façon dont les packs de produits sont gérés, spécifiquement en relation avec la visibilité et l'accès aux produits. Elle garantit que si un produit au sein d'un pack est restreint, le pack lui-même respecte ces restrictions. C'est crucial pour maintenir un contrôle d'accès cohérent pour les produits groupés.
  - **Méthodes clés (probablement modifiées/ajoutées) :** Les méthodes liées à `getPackProducts()` ou `isPack()` pourraient être étendues pour filtrer les produits en fonction des restrictions `pga`.
- `pga/override/classes/shop/Shop.php`

  - **Nom de la classe :** `Shop` (surcharge la classe `Shop` de PrestaShop)
  - **Responsabilité :** Cette surcharge est moins courante pour les modules d'accès aux produits et suggère une intégration plus profonde. Elle pourrait être utilisée pour garantir que les restrictions de produits sont correctement appliquées dans différentes boutiques dans un environnement multi-boutiques, ou pour modifier la façon dont les données de produits sont récupérées à un niveau très fondamental, affectant potentiellement les requêtes de produits.
  - **Méthodes clés (probablement modifiées/ajoutées) :** Des méthodes comme `getProducts()` ou `getProductById()` pourraient être étendues pour filtrer les résultats en fonction des règles `pga` avant même qu'elles ne soient renvoyées par le contexte `Shop`.

### 4.4 Actifs JavaScript (`views/js/`)

- `pga/views/js/pga.js`
  - **Portée :** Back-office.
  - **Objectif :** Ce script est probablement responsable de l'amélioration de l'expérience utilisateur sur la page de configuration du module. Il pourrait gérer les appels AJAX pour la recherche de produits, les mises à jour dynamiques du tableau de restriction de produits ou la validation côté client pour le formulaire de configuration.
  - **Fonctionnalités clés :**
    - Écouteurs d'événements pour les champs de saisie de recherche de produits (par exemple, événements `keyup` pour déclencher des suggestions AJAX).
    - Requêtes AJAX vers un point de terminaison du module (via `AdminController` ou `index.php?fc=module&module=pga&controller=ajax`) pour récupérer des données de produits ou enregistrer des restrictions.
    - Manipulation du DOM pour afficher les résultats de recherche, ajouter les produits sélectionnés à la liste de restrictions ou mettre à jour les messages.

### 4.5 Feuilles de style CSS (`views/css/`)

- `pga/views/css/pga.css`
  - **Portée :** Back-office.
  - **Objectif :** Fournit le style de l'interface de configuration du module dans le Back Office de PrestaShop.
  - **Principaux composants de l'interface utilisateur :** Styles pour le champ de recherche de produits, le tableau de restriction de produits, les boutons et tout élément personnalisé introduit par la méthode `getContent()` du module.
  - **Sélecteurs de classe CSS clés :** Les développeurs peuvent inspecter la sortie HTML du module dans le Back Office pour identifier des classes spécifiques (par exemple, `.pga-product-search`, `.pga-restriction-table`) pour d'éventuelles surcharges si un style de thème d'administration personnalisé est requis.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Tous les modèles sont destinés à la configuration du Back Office.

- `pga/views/templates/admin/AdminTab.tpl`

  - **Objectif :** Ce modèle est probablement un wrapper générique ou un modèle partiel utilisé dans la vue de configuration principale. Il pourrait définir la structure d'une interface à onglets ou d'un en-tête/pied de page commun pour les pages d'administration.
- `pga/views/templates/admin/csv.tpl`

  - **Objectif :** Suggère une fonctionnalité liée à l'importation/exportation CSV des restrictions de produits. Ce modèle rendrait l'interface pour télécharger un fichier CSV ou en générer un.
- `pga/views/templates/admin/csv_file.tpl`

  - **Objectif :** Un sous-modèle ou partiel utilisé par `csv.tpl`, éventuellement pour afficher un formulaire de téléchargement de fichier ou une liste de fichiers CSV.
- `pga/views/templates/admin/customerGroups.tpl`

  - **Objectif :** Ce modèle est crucial pour la fonctionnalité « Sélectionner les groupes de clients ». Il affiche la liste des groupes de clients avec des cases à cocher ou une liste déroulante à sélection multiple, permettant à l'administrateur de choisir quels groupes sont autorisés pour un produit spécifique.
- `pga/views/templates/admin/main.tpl`

  - **Objectif :** C'est le modèle principal de la page de configuration du module (rendu par `getContent()`). Il orchestre tous les autres partiels et affiche les paramètres généraux, le tableau de restriction de produits et les formulaires d'ajout/modification de restriction.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module stocke sa configuration dans la table `ps_configuration` de PrestaShop pour les paramètres généraux (par exemple, `PGA_ENABLED`, `PGA_BLOCK_VIEW`, `PGA_HIDE_LISTS`, `PGA_MESSAGE`).
  - Pour les restrictions spécifiques aux produits, le module crée probablement une table de base de données personnalisée (par exemple, `ps_pga_product_group`) pour stocker le mappage entre `id_product` et `id_group`. La méthode `install()` dans `pga/index.php` définirait cette table.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Potentiellement utilisé pour charger des CSS/JS spécifiques au module pour l'affichage du front-office (par exemple, si un message personnalisé nécessite un style) ou pour effectuer des vérifications précoces pour la redirection de la page produit. |
| `displayRightColumn` / `displayLeftColumn` | Dans la barre latérale droite/gauche des pages du front-office. | Moins probable pour ce module, mais pourrait être utilisé pour afficher un bloc personnalisé (par exemple, « Connectez-vous pour un accès exclusif ») si configuré. |
| `displayProductButtons` / `displayProductActions` (ou hooks de page produit similaires) | Sur la page produit, près du bouton Ajouter au panier. | Utilisé pour masquer ou désactiver le bouton « Ajouter au panier » pour les utilisateurs non autorisés, ou pour afficher le message de restriction personnalisé. |
| `displayFooter` | Dans le pied de page de chaque page du front-office. | Moins courant pour les fonctionnalités de base, mais pourrait être utilisé pour des scripts à chargement tardif ou des analyses liées à l'accès aux produits. |
| `actionCartSave` / `actionObjectCartAddAfter` (ou hooks de panier similaires) | Lorsqu'un produit est ajouté ou enregistré dans le panier. | **CRITIQUE :** C'est là que le module intercepte le processus du panier pour vérifier si le produit ajouté est restreint pour le groupe du client actuel. Si restreint, il empêche l'ajout ou marque l'article comme invalide, affichant le message personnalisé. |
| `actionProductListOverride` (ou hooks de liste de produits similaires) | Lorsque PrestaShop génère une liste de produits (par exemple, page de catégorie, résultats de recherche). | **CRITIQUE :** Utilisé pour filtrer les produits restreints des listes de produits si « Masquer le produit sur les listes de produits » est activé. |
| `actionDispatcherBefore` / `actionFrontControllerSetMedia` | Avant qu'un contrôleur frontal ne soit dispatché ou avant que les ressources multimédias ne soient définies. | Pourrait être utilisé pour implémenter la logique de redirection pour « Bloquer la possibilité de voir la page produit » en vérifiant l'ID du produit demandé par rapport aux restrictions. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Accès aux produits », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir.
