---
title: "Pages produit protégées par mot de passe - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Pages produit protégées par mot de passe' par MyPresta.eu."
sidebar:
  label: "Pages produit protégées par mot de passe"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Password protected product pages sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/password-protected-product-pages.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/password-protected-product-pages/)
>
> ---


# Pages produit protégées par mot de passe

## 1. Exigences et compatibilité
- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Ceci est l'écran de configuration principal du module, accessible en cliquant sur "Configurer" après l'installation ou depuis le Gestionnaire de modules.

- **Ce que fait ce paramètre :** Cet écran contient généralement les paramètres généraux du module, bien que pour "Pages produit protégées par mot de passe", la gestion principale des mots de passe pour des produits spécifiques soit gérée dans un écran d'administration dédié (voir 4.2). Cet écran pourrait offrir des options pour l'apparence de la page de saisie du mot de passe ou le comportement général du module.
- **Effet de la modification de ce paramètre :** Toute modification ici affecterait la façon dont le mécanisme de protection par mot de passe se comporte globalement, ou l'apparence par défaut du formulaire de saisie du mot de passe.
- **Valeur recommandée :** Les valeurs par défaut sont généralement un bon point de départ.
- **Scénario / exemple pour le marchand :** S'il existe une option pour personnaliser le message affiché sur la page du mot de passe, vous pourriez le changer de "Entrez le mot de passe" à "Veuillez entrer votre code d'accès VIP".

### 2.2 Écran d'administration dédié : Mots de passe produit (Back Office > Catalogue > Mots de passe produit)
C'est l'écran le plus important pour gérer quels produits sont protégés par mot de passe et quels sont ces mots de passe. Vous trouverez ce nouvel élément de menu sous **Catalogue** dans votre Back Office PrestaShop.

- **Nom de l'écran et emplacement du menu :** **Catalogue > Mots de passe produit**
- **Actions et paramètres disponibles :**
    -   **Tableau de liste :** Cet écran affiche une liste de tous les produits qui ont actuellement un mot de passe attribué. Vous verrez généralement des colonnes telles que :
        -   **Nom du produit :** Le nom du produit protégé.
        -   **ID du produit :** L'identifiant unique du produit.
        -   **Mot de passe :** Le mot de passe requis pour accéder à la page du produit.
        -   **Actions :** Boutons pour "Modifier" ou "Supprimer" le mot de passe d'un produit spécifique.
    -   **Ajouter un nouveau mot de passe :** Il y aura un bouton (par exemple, "Ajouter un nouveau mot de passe produit" ou une icône plus) pour ajouter une nouvelle entrée de protection par mot de passe. Lorsque vous cliquez dessus, un formulaire vous sera généralement présenté :
        -   **Sélecteur de produit :** Un champ pour rechercher et sélectionner le produit que vous souhaitez protéger. Il peut s'agir d'un champ de saisie semi-automatique où vous tapez le nom du produit.
        -   **Champ de mot de passe :** Un champ de saisie où vous définissez le mot de passe pour ce produit spécifique.
    -   **Modifier le mot de passe :** Cliquer sur "Modifier" à côté d'une entrée existante vous permet de changer le mot de passe de ce produit ou potentiellement de changer le produit associé.
    -   **Supprimer le mot de passe :** Cliquer sur "Supprimer" supprime la protection par mot de passe de ce produit, le rendant à nouveau publiquement accessible.
- **Effet des modifications :**
    -   **Ajout d'un mot de passe :** La page du produit sélectionné deviendra immédiatement protégée par mot de passe dans le front office.
    -   **Modification d'un mot de passe :** Les clients devront utiliser le nouveau mot de passe pour accéder à la page du produit.
    -   **Suppression d'un mot de passe :** La page du produit redeviendra publiquement accessible sans aucune exigence de mot de passe.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Pour protéger un nouveau produit : Naviguez vers **Catalogue > Mots de passe produit**, cliquez sur "Ajouter un nouveau mot de passe produit", sélectionnez votre produit et définissez un mot de passe fort et unique.
    2.  Pour mettre à jour un mot de passe : Trouvez le produit dans la liste, cliquez sur "Modifier" et entrez le nouveau mot de passe.
    3.  Pour supprimer la protection : Trouvez le produit dans la liste et cliquez sur "Supprimer".
    4.  Examinez régulièrement vos produits protégés pour vous assurer que les mots de passe sont toujours pertinents et sécurisés.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
|---|---|---|---|
| Page de configuration du module | (Paramètres généraux, le cas échéant) | (Par défaut du module) | Comportement global ou apparence de la page de saisie du mot de passe. |
| Catalogue > Mots de passe produit | Ajouter un nouveau mot de passe produit | N/A | Sélectionnez un produit et attribuez un mot de passe pour restreindre l'accès à sa page. |
| Catalogue > Mots de passe produit | Modifier le mot de passe produit | N/A | Modifiez le mot de passe d'un produit déjà protégé. |
| Catalogue > Mots de passe produit | Supprimer le mot de passe produit | N/A | Supprimez la protection par mot de passe, rendant la page du produit à nouveau publique. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai défini un mot de passe, mais la page du produit est toujours publique. Qu'est-ce qui ne va pas ?**
R1 :
*   **Vérifiez la saisie du mot de passe :** Vérifiez à nouveau dans **Catalogue > Mots de passe produit** que le produit est listé et que le mot de passe est correctement défini.
*   **Videz le cache :** PrestaShop utilise la mise en cache. Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" si disponible). Cela garantit que votre boutique charge la dernière configuration.
*   **Statut du module :** Assurez-vous que le module "Pages produit protégées par mot de passe" est activé dans **Modules > Gestionnaire de modules**.
*   **Statut du produit :** Assurez-vous que le produit lui-même est activé et visible dans votre catalogue.

**Q2 : Puis-je avoir des mots de passe différents pour différents produits ?**
R2 : Oui, absolument ! Le module est conçu pour cela. Vous pouvez attribuer un mot de passe unique à chaque produit individuel que vous souhaitez protéger via l'écran **Catalogue > Mots de passe produit**.

**Q3 : Que se passe-t-il si un client tente d'accéder directement à une page produit protégée via son URL sans le mot de passe ?**
R3 : Il sera redirigé vers la page de saisie du mot de passe. Il ne pourra pas voir le contenu du produit tant qu'il n'aura pas entré le mot de passe correct.

**Q4 : Comment traduire le texte de la page de saisie du mot de passe (par exemple, "Entrez le mot de passe") ?**
R4 : Vous pouvez généralement traduire les textes du module via l'interface de traduction de PrestaShop. Allez dans **International > Traductions**, sélectionnez "Traductions des modules installés", choisissez votre thème, puis sélectionnez le module "Pages produit protégées par mot de passe". Vous devriez y trouver les chaînes de texte modifiables.

**Q5 : Ce module fonctionnera-t-il avec mon thème personnalisé ?**
R5 : Le module est conçu pour s'intégrer de manière transparente aux thèmes PrestaShop standard. Cependant, les thèmes hautement personnalisés peuvent nécessiter des ajustements CSS mineurs pour garantir que le formulaire de saisie du mot de passe s'affiche parfaitement. Si vous rencontrez des problèmes de style, consultez votre webmaster ou le développeur de votre thème.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture
Le module "Pages produit protégées par mot de passe" fonctionne principalement en surchargeant le `ProductController` par défaut pour intercepter les requêtes de produits protégés. Il utilise un contrôleur d'administration dédié pour gérer les associations produit-mot de passe, qui sont stockées dans la base de données. La logique du front-office vérifie la présence d'un cookie de session valide contenant le mot de passe pour un produit donné avant de rendre la page produit réelle.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :
    *   `prodpswd/controllers/front/ProductPasswd.php`
        *   **Nom de la classe et classe parente :** `ProductPasswdModuleFrontController` étendant `ModuleFrontController`.
        *   **Responsabilité :** Ce contrôleur est probablement responsable du rendu du formulaire de saisie du mot de passe lorsqu'un produit protégé est accédé. Il gère la requête POST lorsqu'un utilisateur soumet un mot de passe, le valide par rapport au mot de passe stocké pour le produit, et définit une session ou un cookie après une authentification réussie pour accorder l'accès. Il peut également gérer la redirection vers la page produit réelle.
    *   `prodpswd/override/controllers/front/ProductController.php`
        *   **Nom de la classe et classe parente :** `ProductController` (surchargé).
        *   **Responsabilité :** Il s'agit d'une surcharge cruciale. Elle intercepte la méthode `init()` ou `postProcess()` du `ProductController` principal. Avant que le contenu standard de la page produit ne soit chargé, cette surcharge vérifie si le produit actuel est protégé par mot de passe et si l'utilisateur a déjà fourni le mot de passe correct (par exemple, via un cookie de session). Si le produit est protégé et qu'aucun mot de passe valide n'est trouvé, il redirige l'utilisateur vers le `ProductPasswdModuleFrontController` (ou rend directement son template) pour demander le mot de passe.

-   **Contrôleurs d'administration Back-Office** :
    *   `prodpswd/controllers/admin/AdminProdPasswordController.php`
        *   **Nom de l'onglet et entité gérée :** Accessible via **Catalogue > Mots de passe produit**. Gère les entités `prodpassword` (ID du produit et mot de passe associé).
        *   **Responsabilité :** Il s'agit d'un `AdminController` standard responsable des opérations CRUD (Créer, Lire, Mettre à jour, Supprimer) pour les associations produit-mot de passe. Il affiche la liste des produits protégés, permet aux administrateurs d'ajouter de nouvelles entrées produit-mot de passe, de modifier les mots de passe existants et de les supprimer. Il utilise probablement `HelperList` pour la vue en grille et `HelperForm` pour les formulaires d'ajout/modification.
    *   `prodpswd/controllers/admin/index.php`
        *   **Responsabilité :** Ce fichier est généralement un fichier `index.php` vide placé dans les sous-répertoires des modules PrestaShop pour empêcher la liste des répertoires, améliorant ainsi la sécurité. Il ne contient aucune logique de contrôleur fonctionnelle.

### 4.3 Classes et modèles principaux (`classes/`)
Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. L'entité `prodpassword` est probablement gérée directement par l'`AdminProdPasswordController` à l'aide d'une simple définition `ObjectModel` dans le fichier principal du module ou le contrôleur lui-même, ou elle pourrait interagir directement avec `Configuration` ou une table personnalisée sans `ObjectModel` dédié. Étant donné que l'`AdminProdPasswordController` gère une table `prodpassword`, il est fort probable qu'un `ObjectModel` soit défini pour celle-ci, même s'il ne se trouve pas dans un dossier `classes/` séparé.

### 4.4 Actifs JavaScript (`views/js/`)
Le dossier du module n'indique aucun fichier JavaScript personnalisé. Le formulaire de mot de passe du front-office et la grille/formulaire du back-office devraient s'appuyer sur le JS PrestaShop standard ou de simples soumissions de formulaires HTML.

### 4.5 Feuilles de style CSS (`views/css/`)
Le dossier du module n'indique aucun fichier CSS personnalisé. Le style de la page de saisie du mot de passe dans le front office et des formulaires d'administration héritera probablement du thème PrestaShop actif et des styles du back-office.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :
    *   Aucun template de hook spécifique n'est listé, ce qui suggère que le module fonctionne principalement via des surcharges de contrôleur et des templates front-office dédiés plutôt que d'injecter du contenu dans des hooks standard.
-   **Templates d'administration (`views/templates/admin/`)** :
    *   Aucun template d'administration spécifique n'est listé. L'`AdminProdPasswordController` utilise probablement les templates `HelperList` et `HelperForm` standard de PrestaShop pour son interface.
-   **Templates Front-office (`views/templates/front/`)** :
    *   `prodpswd/views/templates/front/product.tpl`
        *   **Objectif :** Ce template est probablement le formulaire de saisie de mot de passe personnalisé affiché aux clients lorsqu'ils tentent d'accéder à une page produit protégée. Il contient la structure HTML pour le champ de saisie du mot de passe, le bouton de soumission et tout message d'accompagnement (par exemple, "Entrez le mot de passe pour voir ce produit").
    *   `prodpswd/lib/searchTool/views/scripts.tpl`
        *   **Objectif :** Ce template contient probablement du JavaScript ou de la logique Smarty liée à un outil de recherche, éventuellement utilisé dans la configuration d'administration pour sélectionner les produits à protéger. Il pourrait inclure des appels AJAX ou des capacités de filtrage dynamique pour la sélection de produits.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :
    *   `ps_prodpassword` (ou similaire) : Cette table personnalisée est censée stocker l'ID du produit (`id_product`) et le mot de passe associé (`password`) pour chaque produit protégé. Elle est créée lors de la méthode `install()` du module.
    *   Enregistrements de configuration dans `ps_configuration` : Les paramètres généraux du module (le cas échéant) y seraient stockés.

-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
|---|---|---|
| `actionFrontControllerSetMedia` | Avant le chargement des médias (JS/CSS) d'un contrôleur frontal. | Potentiellement pour charger du JS/CSS personnalisé pour le formulaire de mot de passe, bien qu'aucun ne soit listé dans le dossier. |
| `displayHeader` | Dans la section `<head>` du front office. | Pourrait être utilisé pour des balises méta ou du JS/CSS conditionnel, mais pas explicitement pour le contenu. |
| `displayRightColumn` | Dans la colonne de droite du front office. | Non directement utilisé pour la fonctionnalité principale du module. |
| `displayLeftColumn` | Dans la colonne de gauche du front office. | Non directement utilisé pour la fonctionnalité principale du module. |
| `displayFooter` | Dans le pied de page du front office. | Non directement utilisé pour la fonctionnalité principale du module. |
| `actionProductControllerSetMedia` | Après que le `ProductController` a défini ses médias. | Pourrait être utilisé pour injecter du JS/CSS spécifique pour la page produit, mais peu probable étant donné la surcharge. |
| `actionDispatcherBefore` | Avant qu'un contrôleur frontal ne soit dispatché. | L'`override/controllers/front/ProductController.php` agit effectivement à ce stade pour les pages produit. |
| `actionDispatcherAfter` | Après qu'un contrôleur frontal a été dispatché. | Moins probable pour la fonctionnalité principale de ce module. |

Le mécanisme principal de ce module est la surcharge du `ProductController`, qui agit comme un hook implicite, interceptant les requêtes avant même que les hooks standard ne soient traités pour le contenu de la page produit.

## 5. Support officiel et mises à jour
Pour les dernières mises à jour, corrections de bugs et support officiel du module "Pages produit protégées par mot de passe", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez rencontrer.
