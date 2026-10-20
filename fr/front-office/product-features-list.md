---
title: "Liste des caractéristiques du produit - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Liste des caractéristiques du produit' par MyPresta.eu."
sidebar:
  label: "Liste des caractéristiques du produit - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Product features list sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-features-list.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/product-features-list/)
>
> ---


# Liste des caractéristiques du produit

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Liste des caractéristiques du produit)

C'est l'écran de configuration principal du module, accessible immédiatement après l'installation ou en cliquant sur « Configurer » depuis le Gestionnaire de modules.

- **Ce que fait ce paramètre :** Ce paramètre contrôle où la liste des caractéristiques du produit apparaîtra visuellement sur vos pages de liste de produits (pages de catégorie, résultats de recherche, etc.).
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur « displayProductListReviews » :* Les caractéristiques apparaîtront près de la section des avis sur les produits dans la liste des produits. C'est souvent un bon endroit pour regrouper la preuve sociale avec les attributs clés du produit.
  - *Lorsqu'il est défini sur « displayProductDeliveryTime » :* Les caractéristiques apparaîtront près de toute information de délai de livraison affichée. Cela peut être utile pour les produits dont les caractéristiques sont étroitement liées à la logistique ou à la disponibilité.
  - *Lorsqu'il est défini sur « displayHeader » :* Cette option est moins courante pour l'affichage visuel sur les listes de produits et pourrait placer les caractéristiques dans l'en-tête de la page, ce qui n'est généralement pas l'endroit où vous voudriez que les caractéristiques spécifiques au produit apparaissent. C'est principalement un hook technique.
- **Valeur recommandée :** « displayProductListReviews » ou « displayProductDeliveryTime ». Choisissez celui qui s'intègre le mieux à la mise en page de votre thème et où vous estimez que les caractéristiques seront les plus visibles sans encombrement.
- **Scénario / exemple de marchand :** Si votre thème affiche les évaluations par étoiles et le nombre d'avis de manière proéminente, « displayProductListReviews » placerait les caractéristiques juste à côté, créant un bloc d'informations riche. Si vos produits ont souvent des détails de livraison spécifiques (par exemple, « Expédié en 24h »), placer les caractéristiques avec « displayProductDeliveryTime » pourrait avoir du sens.

### 2.2 Écran d'administration dédié : Association des caractéristiques (Back Office > Modules > Liste des caractéristiques du produit > Configurer > « Gérer les associations de caractéristiques » ou lien similaire)

Cet écran est crucial pour définir *quelles* caractéristiques apparaissent pour *quels* produits et catégories. C'est là que vous associez des caractéristiques de produit spécifiques à des catégories.

- **Nom de l'écran et emplacement du menu :** Après avoir configuré le module principal, vous trouverez généralement un lien ou un bouton sur la page de configuration du module (ou un nouvel élément de menu sous « Catalogue ») qui mène à « Gérer les associations de caractéristiques » ou « Liste des caractéristiques du produit ». Le chemin exact peut varier légèrement selon votre version de PrestaShop, mais il sera lié à la configuration principale du module.
- **Actions et paramètres disponibles :**
  - **Vue grille/gestion :** Vous verrez un tableau listant vos caractéristiques de produit existantes (ce sont les caractéristiques standard que vous définissez sous **Catalogue > Attributs & Caractéristiques > Caractéristiques**).
  - **Bouton Modifier/Associer :** Pour chaque caractéristique, il y aura un bouton « Modifier » ou « Associer ». Cliquer dessus ouvrira un formulaire où vous pourrez :
    - **Sélectionner des catégories :** Choisissez une ou plusieurs catégories pour lesquelles cette caractéristique spécifique doit être affichée sur les listes de produits. Par exemple, si vous avez une caractéristique « Matériau », vous pourriez l'associer aux catégories « T-shirts », « Robes » et « Vestes ».
    - **Activer/Désactiver :** Vous pourriez avoir une option pour activer ou désactiver l'affichage de cette caractéristique sur les listes de produits globalement ou par catégorie.
- **Effet des modifications :**
  - *Lorsque vous associez une caractéristique à une catégorie :* Les produits de cette catégorie qui possèdent cette caractéristique l'afficheront dans leur entrée de liste de produits.
  - *Lorsque vous supprimez une association :* La caractéristique n'apparaîtra plus pour les produits de cette catégorie sur les listes de produits.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Tout d'abord, assurez-vous que toutes vos caractéristiques de produit sont correctement configurées sous **Catalogue > Attributs & Caractéristiques > Caractéristiques**.
  2. Naviguez vers l'écran « Gérer les associations de caractéristiques » du module « Liste des caractéristiques du produit ».
  3. Parcourez chaque caractéristique pertinente.
  4. Pour chaque caractéristique, sélectionnez les catégories où vous souhaitez que cette caractéristique soit visible sur les pages de liste de produits.
  5. Enregistrez vos modifications.
  6. Révisez périodiquement ces associations, en particulier lors de l'ajout de nouveaux produits, catégories ou caractéristiques, pour vous assurer que vos listes de produits restent informatives.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Position des tags (fplist\_position) | displayProductListReviews | Détermine où les caractéristiques apparaissent sur les pages de liste de produits (par exemple, près des avis, près du délai de livraison). |
| Association des caractéristiques | Nom de la caractéristique (par exemple, « Matériau ») | N/A | Caractéristique PrestaShop standard à gérer. |
| Association des caractéristiques | Catégories associées | N/A | Sélectionnez les catégories où cette caractéristique doit être visible sur les listes de produits. |
| Association des caractéristiques | Activer/Désactiver la caractéristique | Activé | Contrôle si une caractéristique est activement affichée pour ses catégories associées. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai configuré le module, mais les caractéristiques n'apparaissent pas sur mes pages de catégorie.**
R :

1. **Vérifiez les associations de caractéristiques :** Allez à l'écran « Gérer les associations de caractéristiques » et assurez-vous que les caractéristiques que vous vous attendez à voir sont réellement associées aux catégories que vous consultez.
2. **Videz le cache :** PrestaShop utilise la mise en cache. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » si disponible).
3. **Position du module :** Vérifiez à nouveau le paramètre « Position des tags » dans la configuration principale du module. Assurez-vous qu'il est défini sur un hook que votre thème rend réellement dans le contexte de la liste de produits (par exemple, `displayProductListReviews` ou `displayProductDeliveryTime`). Certains thèmes personnalisés peuvent ne pas appeler explicitement tous les hooks standard.
4. **Données produit :** Vérifiez que les produits en question ont bien des valeurs pour les caractéristiques que vous essayez d'afficher (par exemple, si vous voulez afficher « Matériau », assurez-vous que le produit a un matériau assigné).

**Q : Les caractéristiques s'affichent, mais elles sont désordonnées ou ne correspondent pas au design de mon thème.**
R :

1. **Conflit CSS :** Il s'agit probablement d'un conflit de style avec votre thème. Le module inclut son propre CSS (`fplist/views/css/fplist.css`), mais les styles de votre thème pourraient le remplacer ou causer des problèmes de mise en page.
2. **Thème personnalisé :** Si vous utilisez un thème hautement personnalisé, vous pourriez avoir besoin d'un webmaster ou d'un développeur pour ajuster le CSS du module ou le CSS de votre thème afin d'assurer une intégration correcte.
3. **Positionnement :** Essayez de modifier le paramètre « Position des tags » pour voir si un hook différent s'intègre mieux visuellement à votre thème.

**Q : Puis-je afficher des caractéristiques différentes pour des catégories différentes ?**
R : Oui, absolument ! C'est l'une des principales forces du module. Utilisez l'écran « Gérer les associations de caractéristiques » pour sélectionner des catégories spécifiques pour chaque caractéristique. Cela vous permet d'adapter les informations affichées précisément au contexte de la liste de produits.

**Q : Ce module affecte-t-il mes pages produit ?**
R : Non, ce module cible spécifiquement les pages de *liste* de produits (catégorie, résultats de recherche, etc.). Il ne modifie pas la façon dont les caractéristiques sont affichées sur les pages de détails de produits individuels.

**Q : Ma boutique est multilingue. Les noms des caractéristiques sont-ils traduits ?**
R : Oui, les caractéristiques standard de PrestaShop (que ce module utilise) sont entièrement traduisibles. Assurez-vous d'avoir fourni des traductions pour les noms et les valeurs de vos caractéristiques sous **Catalogue > Attributs & Caractéristiques > Caractéristiques** pour toutes les langues actives de votre boutique. Le module affichera alors la traduction correcte sur le front office.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Liste des caractéristiques du produit » (`fplist`) suit une architecture de module PrestaShop standard, étendant principalement `Module` pour sa fonctionnalité principale et `AdminController` pour son interface de gestion Back Office. Il utilise le système de hooks de PrestaShop pour injecter du contenu dans les pages de liste de produits et utilise un `ObjectModel` (implicitement via `AdminFplistAssociationController`) pour gérer l'association entre les caractéristiques et les catégories. L'affichage front-office du module est géré par un template Smarty rendu via un hook.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Ce module ne contient pas de contrôleurs front-office dédiés. Toute la logique d'affichage front-office est gérée directement dans le fichier principal du module (`fplist.php`) via des hooks enregistrés.
- **Contrôleurs d'administration Back-Office** :

  - `fplist/controllers/admin/AdminFplistAssociation.php`
    - **Nom de la classe :** `AdminFplistAssociationController` (étend `ModuleAdminController`)
    - **Responsabilité :** Ce contrôleur gère l'association entre les caractéristiques PrestaShop et les catégories. Il fournit l'interface Back Office (une liste et potentiellement un formulaire d'édition) permettant aux administrateurs de sélectionner les caractéristiques à afficher sur les listes de produits pour des catégories spécifiques. Il interagit avec le stockage interne des données du module (probablement la table `ps_fplist_association`, bien qu'aucun `ObjectModel` explicite ne soit fourni dans le dossier, le contrôleur implique son existence et sa gestion).
  - `fplist/controllers/admin/index.php`
    - **Nom de la classe :** N/A (il s'agit généralement d'un fichier vide ou d'une redirection pour empêcher l'accès direct au répertoire, pas d'un contrôleur fonctionnel).
    - **Responsabilité :** Mesure de sécurité PrestaShop standard pour empêcher la liste des répertoires.

### 4.3 Classes et modèles principaux (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Le `AdminFplistAssociationController` implique l'existence d'un modèle de données pour les associations caractéristique-catégorie, qui est probablement géré directement dans le contrôleur ou le fichier principal du module à l'aide de requêtes `Db::getInstance()`, plutôt qu'un `ObjectModel` dédié. Si un `ObjectModel` était présent, il serait généralement nommé `FplistAssociation` ou similaire.

### 4.4 Actifs JavaScript (`views/js/`)

Le dossier du module n'indique aucun fichier JavaScript personnalisé. Tout comportement dynamique ou interaction AJAX devrait être implémenté directement dans les fichiers PHP ou de template du module, ou s'appuyer sur le JS principal de PrestaShop.

### 4.5 Feuilles de style CSS (`views/css/`)

- `fplist/views/css/fplist.css`
  - **Portée :** Style client Front-Office.
  - **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :** Cette feuille de style est responsable de la présentation visuelle de la liste des caractéristiques du produit sur les pages de catégorie et de liste. Elle définit les styles pour le conteneur des caractéristiques, les éléments de caractéristiques individuels, et potentiellement les icônes ou les étiquettes qui leur sont associées.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger :** Les développeurs doivent inspecter le HTML rendu pour identifier les classes spécifiques (par exemple, `.fplist-container`, `.fplist-item`, `.fplist-feature-name`, `.fplist-feature-value`) à surcharger dans le `custom.css` ou `theme.css` de leur thème pour une intégration transparente.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :
  - `fplist/views/templates/fplist-front.tpl`
    - **Hook :** Ce template est rendu dans les hooks `displayProductListReviews` et `displayProductDeliveryTime` (tel que configuré par `fplist_position`).
    - **Sortie :** Il génère la structure HTML pour la liste des caractéristiques d'un seul produit sur une page de liste de produits. Il itère sur les caractéristiques récupérées par le module pour le produit et la catégorie actuels, affichant leurs noms et leurs valeurs.
  - `fplist/views/templates/fplist.tpl`
    - **Hook :** Ce template est probablement utilisé pour la page de configuration principale du module dans le Back Office (via `getContent()`).
    - **Sortie :** Il rend le formulaire pour le paramètre « Position des tags » et potentiellement des liens vers le `AdminFplistAssociationController` pour la gestion des associations de caractéristiques.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - `ps_fplist_association` (implicite) : Cette table n'est pas explicitement définie dans le dossier mais est nécessaire pour que le `AdminFplistAssociationController` stocke la relation plusieurs-à-plusieurs entre les caractéristiques et les catégories de PrestaShop. Elle contiendrait généralement des colonnes comme `id_feature`, `id_category`, et potentiellement `id_shop`.
  - Enregistrements de configuration dans `ps_configuration` :
    - `mypresta_updates` : Stocke les informations de mise à jour pour les modules MyPresta.eu.
    - `update_` : Lié aux vérifications de mise à jour du module.
    - `updatev_` : Lié aux vérifications de mise à jour du module.
    - `fplist_position` : Stocke le nom du hook sélectionné pour l'affichage des caractéristiques (par exemple, `displayProductListReviews`).
    - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` : Configuration PrestaShop standard pour la langue du formulaire d'employé.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | But technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page front-office. | Principalement utilisé pour charger des actifs CSS/JS ou des balises meta. Le module l'utilise comme position configurable pour les caractéristiques, bien que moins courant pour l'affichage visuel. |
| `displayProductListReviews` | Dans l'élément de la liste de produits, généralement près des avis sur les produits. | Injecte le HTML de la liste des caractéristiques dans chaque entrée de produit sur les pages de catégorie/recherche. |
| `displayProductDeliveryTime` | Dans l'élément de la liste de produits, généralement près des informations sur le délai de livraison. | Injecte le HTML de la liste des caractéristiques dans chaque entrée de produit sur les pages de catégorie/recherche. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | (Non explicitement utilisé par ce module, mais un hook courant pour les actions liées aux commandes). |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support professionnel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant le module « Liste des caractéristiques du produit ».
