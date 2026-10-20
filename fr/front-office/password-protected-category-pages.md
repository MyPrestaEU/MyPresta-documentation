---
title: "Pages de catégorie protégées par mot de passe - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Pages de catégorie protégées par mot de passe' par MyPresta.eu."
sidebar:
  label: "Pages de catégorie protégées par mot de passe - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Password protected category pages sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/password-protected-category-pages.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/password-protected-category-pages/)
>
> ---


# Pages de catégorie protégées par mot de passe

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation du module, cliquez sur « Configurer » pour accéder à ses paramètres principaux. Cet écran fournit des options générales de gestion du module.

-   **Ce que fait ce paramètre :** Cette section inclut généralement les paramètres standard des modules MyPresta.eu liés aux mises à jour et à la licence. Elle garantit que votre module est à jour et correctement sous licence.
-   **Effet de la modification de ce paramètre :**
    -   *`mypresta_updates`* : Ce paramètre contrôle si le module vérifie automatiquement les mises à jour. Le maintenir activé vous assure d'être informé des nouvelles versions.
    -   *`update_`* et *`updatev_`* : Ce sont des paramètres internes utilisés par le module pour gérer les vérifications de mise à jour et les informations de version. Vous n'avez généralement pas besoin d'interagir directement avec ceux-ci.
-   **Valeur recommandée :** Gardez `mypresta_updates` activé pour recevoir les mises à jour importantes et les corrections de bugs.
-   **Scénario / exemple de marchand :** Si vous souhaitez vous assurer que votre module dispose toujours des dernières fonctionnalités et correctifs de sécurité, maintenez la vérification des mises à jour activée. Si vous avez une boutique fortement personnalisée et préférez contrôler manuellement les mises à jour après des tests approfondis, vous pourriez la désactiver, mais ce n'est généralement pas recommandé pour la plupart des marchands.

### 2.2 Écran d'administration dédié : Mots de passe de catégorie (Back Office > Catalogue > Mots de passe de catégorie)

C'est l'écran de gestion principal pour configurer et gérer les mots de passe de vos catégories.

-   **Nom de l'écran et emplacement du menu :** Vous pouvez trouver cet écran en naviguant vers **Catalogue > Mots de passe de catégorie** dans le menu de votre Back Office PrestaShop.
-   **Actions et paramètres disponibles :**
    -   **Liste des catégories :** Cet écran affiche une liste de toutes vos catégories. Pour chaque catégorie, vous verrez si elle est actuellement protégée par mot de passe et combien de mots de passe lui sont attribués.
    -   **Ajouter/Modifier des mots de passe :** Pour chaque catégorie, vous pouvez cliquer sur un bouton « Modifier » ou « Gérer les mots de passe » (ou une icône similaire) pour ouvrir une interface dédiée. Ici, vous pouvez :
        -   **Sélectionner une catégorie :** Choisissez la catégorie spécifique que vous souhaitez protéger.
        -   **Ajouter un nouveau mot de passe :** Saisissez un nouveau mot de passe pour la catégorie sélectionnée. Vous pouvez ajouter plusieurs mots de passe pour une seule catégorie. Ceci est utile si vous souhaitez donner différents codes d'accès à différents groupes de clients (par exemple, « VIP123 » pour les clients premium, « WHOLESALE456 » pour les partenaires B2B).
        -   **Supprimer un mot de passe :** Supprimez les mots de passe existants.
        -   **Activer/Désactiver la protection :** Un interrupteur ou une case à cocher pourrait être disponible pour activer ou désactiver rapidement la protection par mot de passe pour une catégorie sans supprimer tous ses mots de passe.
-   **Effet des modifications :**
    -   **Ajout d'un mot de passe :** La catégorie sélectionnée deviendra immédiatement protégée par mot de passe dans le front office. Les clients devront saisir l'un des mots de passe attribués pour afficher ses produits.
    -   **Suppression d'un mot de passe :** Ce mot de passe spécifique ne donnera plus accès. S'il s'agissait du seul mot de passe pour une catégorie, la catégorie pourrait devenir non protégée (selon la logique exacte du module, il est plus sûr de désactiver explicitement la protection si vous voulez qu'elle soit ouverte).
    -   **Désactivation de la protection :** La catégorie redeviendra publiquement accessible, et les clients verront ses produits sans avoir besoin d'un mot de passe.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Allez dans **Catalogue > Mots de passe de catégorie**.
    2.  Identifiez la catégorie que vous souhaitez protéger.
    3.  Cliquez sur l'icône « Gérer les mots de passe » ou « Modifier » à côté.
    4.  Dans le nouvel écran, ajoutez un ou plusieurs mots de passe. N'oubliez pas que chaque mot de passe que vous ajoutez donnera accès.
    5.  Enregistrez vos modifications.
    6.  Pour supprimer la protection, supprimez tous les mots de passe de cette catégorie ou utilisez un interrupteur « Activer/Désactiver » si disponible.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | `mypresta_updates` | Activé | Contrôle les vérifications automatiques de mise à jour pour le module. Gardez activé pour les dernières fonctionnalités et la sécurité. |
| Page de configuration du module | `update_`, `updatev_` | (Interne) | Paramètres internes pour la gestion des mises à jour. Aucune interaction du marchand n'est nécessaire. |
| Mots de passe de catégorie (Catalogue > Mots de passe de catégorie) | Liste des catégories | N/A | Aperçu de toutes les catégories et de leur statut de protection par mot de passe. |
| Mots de passe de catégorie (Catalogue > Mots de passe de catégorie) | Ajouter/Modifier des mots de passe | N/A | Permet d'ajouter, de modifier ou de supprimer des mots de passe pour des catégories spécifiques. Plusieurs mots de passe par catégorie sont pris en charge. |
| Mots de passe de catégorie (Catalogue > Mots de passe de catégorie) | Activer/Désactiver la protection | N/A | Active ou désactive la protection par mot de passe pour une catégorie. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : J'ai défini un mot de passe, mais la catégorie est toujours visible sans. Qu'est-ce qui ne va pas ?**
R1 :

-   **Vider le cache :** La raison la plus courante est la mise en cache. Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » et « Vider le cache » pour tous les caches).
-   **Vérifier le statut de la catégorie :** Assurez-vous que la catégorie elle-même est active et visible dans votre boutique.
-   **Vérifier la saisie du mot de passe :** Vérifiez que vous avez correctement saisi et enregistré le(s) mot(s) de passe dans la section **Catalogue > Mots de passe de catégorie**.
-   **Position du module :** Assurez-vous que le module est correctement accroché. Bien que le module gère cela automatiquement, si vous avez des thèmes fortement personnalisés, les hooks peuvent parfois être écrasés.

**Q2 : Puis-je avoir plusieurs mots de passe pour une seule catégorie ?**
R2 : Oui ! Ce module prend explicitement en charge un nombre illimité de mots de passe pour une seule catégorie. C'est utile pour donner différents codes d'accès à différents groupes (par exemple, mot de passe « VIP », mot de passe « Grossiste »).

**Q3 : Que se passe-t-il si un client tente d'accéder à un produit directement depuis une catégorie protégée via son URL ?**
R3 : Si un produit appartient à une catégorie protégée par mot de passe, l'accès direct à la page du produit nécessitera toujours la saisie préalable du mot de passe de la catégorie. Le module garantit que le contexte de la catégorie est respecté, empêchant l'accès direct aux produits d'une catégorie sécurisée sans authentification.

**Q4 : Comment puis-je supprimer la protection par mot de passe d'une catégorie ?**
R4 : Allez dans **Catalogue > Mots de passe de catégorie**. Trouvez la catégorie que vous souhaitez déprotéger. Vous pouvez soit supprimer tous les mots de passe associés à cette catégorie, soit, s'il existe un interrupteur explicite « Activer/Désactiver » pour la protection de la catégorie, l'utiliser. Une fois tous les mots de passe supprimés ou la protection désactivée, la catégorie redeviendra publiquement accessible.

**Q5 : Le formulaire de mot de passe n'a pas l'air bien sur mon thème personnalisé. Comment puis-je le réparer ?**
R5 : Le module utilise le templating et le CSS standard de PrestaShop. S'il ne s'affiche pas correctement, il s'agit probablement d'un conflit CSS avec votre thème personnalisé.

-   **Inspecter l'élément :** Utilisez les outils de développement de votre navigateur (F12) pour inspecter les éléments du formulaire de mot de passe. Recherchez les règles CSS conflictuelles de votre thème.
-   **CSS personnalisé :** Vous pouvez ajouter du CSS personnalisé au fichier `custom.css` de votre thème (ou similaire) pour remplacer le style par défaut du module et le faire correspondre à votre thème.
-   **Contacter le support :** Si vous n'êtes pas à l'aise avec le CSS, contactez le développeur de votre thème ou le support MyPresta.eu pour obtenir de l'aide.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Pages de catégorie protégées par mot de passe » s'intègre à l'architecture MVC de PrestaShop principalement en surchargeant le `CategoryController` de base pour intercepter les requêtes vers les pages de catégorie. Il utilise un contrôleur d'administration dédié (`AdminCatPasswordController`) pour gérer les associations catégorie-mot de passe, les stockant dans une table de base de données personnalisée. L'affichage en front-office est géré via un template Smarty personnalisé pour le formulaire de saisie du mot de passe.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    -   `catpswd/override/controllers/front/listing/CategoryController.php`
        -   **Nom de la classe :** `CategoryController` (surcharge le `CategoryController` de base de PrestaShop)
        -   **Classe parente :** `CategoryControllerCore`
        -   **Responsabilité :** Cette surcharge est le cœur de la fonctionnalité front-office du module. Elle intercepte les requêtes vers les pages de catégorie. Avant d'afficher le contenu réel de la catégorie, elle vérifie si la catégorie est protégée par mot de passe. Si c'est le cas, et que l'utilisateur n'a pas encore saisi le mot de passe correct (ou que la session a expiré), elle rend le formulaire de saisie du mot de passe (`category.tpl`) au lieu de la page de catégorie standard. Elle gère la soumission du formulaire de mot de passe, valide le mot de passe saisi et définit une variable de session en cas d'authentification réussie.
    -   `catpswd/override/controllers/front/listing/index.php`
        -   **Responsabilité :** Il s'agit d'un fichier `index.php` PrestaShop standard dans un répertoire de surcharge, généralement utilisé pour empêcher la liste directe des répertoires et assurer le bon chargement du module. Il ne contient pas de logique de contrôleur active en soi.
-   **Contrôleurs d'administration Back-Office** :

    -   `catpswd/controllers/admin/AdminCatPasswordController.php`
        -   **Nom de l'onglet :** « Mots de passe de catégorie » (sous le menu Catalogue)
        -   **Entité gérée :** `CatPassword` (bien qu'aucun `ObjectModel` ne soit explicitement listé, ce contrôleur gère les relations catégorie-mot de passe, interagissant probablement directement avec la base de données ou une classe d'aide).
        -   **Responsabilité :** Ce contrôleur fournit l'interface dans le Back Office PrestaShop permettant aux administrateurs de gérer la protection par mot de passe des catégories. Il liste les catégories, permet d'ajouter plusieurs mots de passe à une catégorie et de les supprimer. Il gère les opérations CRUD pour les données catégorie-mot de passe.
    -   `catpswd/controllers/admin/index.php`
        -   **Responsabilité :** Similaire au `index.php` du front-office, ce fichier empêche la liste directe des répertoires pour le répertoire des contrôleurs d'administration.

### 4.3 Classes et modèles de base (`classes/`)

Le dossier du module n'indique aucune classe explicite dans le répertoire `classes/`. Cela suggère que l'`AdminCatPasswordController` gère probablement les interactions avec la base de données directement ou utilise une simple fonction d'aide dans le fichier principal du module (`catpswd.php`) pour la gestion des données, plutôt qu'un `ObjectModel` dédié.

### 4.4 Actifs JavaScript (`views/js/`)

Le dossier du module n'indique aucun fichier JavaScript spécifique. La soumission et la validation du mot de passe sont probablement gérées via la soumission de formulaire HTML standard et le traitement côté serveur dans la surcharge du `CategoryController`.

### 4.5 Feuilles de style CSS (`views/css/`)

Le dossier du module n'indique aucun fichier CSS spécifique. Le style du formulaire de saisie du mot de passe est probablement minimal et repose sur le style de base du thème PrestaShop par défaut. Les développeurs souhaitant personnaliser l'apparence doivent cibler les éléments du formulaire dans le template `category.tpl` en utilisant le CSS personnalisé de leur thème.

### 4.6 Structure du template Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :
    -   `catpswd/lib/searchTool/views/scripts.tpl`
        -   **Hook :** Probablement utilisé dans `displayHeader` ou `actionAdminControllerSetMedia` (s'il contient des inclusions JS/CSS pour un outil de recherche).
        -   **Sortie :** Ce template contient probablement des inclusions JavaScript ou CSS, éventuellement pour un utilitaire de recherche utilisé dans l'interface d'administration du module ou pour des fonctionnalités front-office.
-   **Templates Front-office (`views/templates/front/`)** :
    -   `catpswd/views/templates/front/category.tpl`
        -   **Objectif :** C'est le template rendu par le `CategoryController` surchargé lorsqu'une catégorie protégée par mot de passe est accédée sans authentification. Il affiche le formulaire de saisie du mot de passe au client. Il inclut généralement des champs pour le mot de passe, un bouton de soumission et des messages pour les tentatives réussies ou échouées.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :
    -   `ps_catpassword` : Cette table personnalisée est créée par le module lors de l'installation. Elle stocke les associations entre les ID de catégorie et leurs mots de passe respectifs.
        -   **Colonnes (attendues) :** `id_catpassword` (clé primaire), `id_category` (clé étrangère vers `ps_category`), `password` (la chaîne de mot de passe hachée ou en texte clair).
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Potentiellement utilisé pour inclure des actifs CSS ou JS globaux, ou pour définir des balises meta liées à la fonctionnalité du module. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration est chargé et que ses médias (JS/CSS) sont définis. | Utilisé par le module pour injecter ses fichiers JavaScript et CSS spécifiques dans le Back Office pour l'`AdminCatPasswordController` ou d'autres pages d'administration où les actifs du module sont nécessaires. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support professionnel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à fournir une assistance rapide et à assurer le bon fonctionnement de votre module.
