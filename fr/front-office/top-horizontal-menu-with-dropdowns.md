---
title: "Menu horizontal supérieur avec sous-menus déroulants - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Menu horizontal supérieur avec sous-menus déroulants' par MyPresta.eu."
sidebar:
  label: "Menu horizontal supérieur avec sous-menus déroulants - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Top horizontal menu with dropdowns sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/top-horizontal-menu-with-dropdowns.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/top-horizontal-menu-with-dropdowns/)
>
> ---


# Menu horizontal supérieur avec sous-menus déroulants

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises par PrestaShop lui-même et devraient être disponibles sur tout environnement d'hébergement compatible.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » pour accéder aux paramètres du module. Cet écran vous permet de gérer les éléments qui apparaissent dans votre menu horizontal supérieur et de configurer la barre de recherche.

La page de configuration est divisée en deux sections principales : **Éléments de menu** et **Barre de recherche**.

#### 2.1.1 Gestion des éléments de menu

Cette section vous permet de définir les éléments qui apparaissent dans votre menu de navigation principal. Vous pouvez ajouter des liens vers des catégories, des pages CMS, des fabricants, des fournisseurs ou des URL personnalisées.

-   **Ajouter un nouvel élément de menu :**

    -   **Libellé :** C'est le texte qui sera affiché dans votre menu (par exemple, « Nouveautés », « Collection d'été », « À propos de nous »). Vous pouvez saisir différents libellés pour chaque langue prise en charge par votre boutique.
        -   *Effet du changement :* Modifie directement le texte visible de l'élément de menu pour les clients.
        -   *Valeur recommandée :* Texte clair, concis et descriptif qui représente précisément la destination du lien.
        -   *Scénario marchand :* Vous souhaitez ajouter un lien vers votre page « Contactez-nous ». Vous saisiriez « Contactez-nous » ici.
    -   **Lien :** C'est l'URL vers laquelle l'élément de menu pointera. Vous pouvez sélectionner parmi une liste de catégories, de pages CMS, de fabricants ou de fournisseurs existants, ou saisir une URL personnalisée.
        -   *Effet du changement :* Détermine où le client est dirigé lorsqu'il clique sur cet élément de menu.
        -   *Valeur recommandée :* Assurez-vous toujours que le lien est valide et pointe vers la bonne page. Pour les pages internes, utilisez les outils de sélection fournis. Pour les liens externes, assurez-vous que l'URL complète (par exemple, `https://example.com/blog`) est saisie.
        -   *Scénario marchand :* Vous souhaitez créer un lien vers votre catégorie « T-Shirts ». Vous sélectionneriez « T-Shirts » dans la liste déroulante des catégories. Si vous souhaitez créer un lien vers un blog externe, vous saisiriez l'URL complète du blog.
    -   **Nouvelle fenêtre :** Un interrupteur (Oui/Non) qui détermine si le lien s'ouvre dans un nouvel onglet ou une nouvelle fenêtre du navigateur.
        -   *Lorsque activé (Oui) :* Le lien s'ouvrira dans un nouvel onglet, gardant la page actuelle de votre boutique ouverte dans l'onglet d'origine.
        -   *Lorsque désactivé (Non) :* Le lien s'ouvrira dans le même onglet, éloignant le client de la page actuelle.
        -   *Valeur recommandée :* « Oui » pour les liens externes (par exemple, un blog, un profil de réseau social) afin de garder les clients sur votre boutique. « Non » pour les liens internes (catégories, produits, pages CMS) afin de maintenir un flux de navigation naturel au sein de votre site.
        -   *Scénario marchand :* Vous créez un lien vers votre page Facebook. Réglez « Nouvelle fenêtre » sur « Oui » afin que les clients puissent facilement revenir à votre boutique.
-   **Gestion des éléments de menu existants :**

    -   Le module affiche une liste de vos éléments de menu actuels. Vous pouvez faire glisser et déposer des éléments pour les réorganiser, ce qui affecte directement leur ordre d'affichage dans le front office.
    -   Vous pouvez cliquer sur « Modifier » pour modifier le libellé, le lien ou le paramètre de nouvelle fenêtre d'un élément existant.
    -   Vous pouvez cliquer sur « Supprimer » pour supprimer un élément du menu.
        -   *Effet des changements :* La réorganisation, la modification ou la suppression d'éléments met à jour immédiatement la structure et l'apparence du menu sur votre boutique en ligne.
        -   *Flux de travail recommandé :* Révisez régulièrement la structure de votre menu pour vous assurer qu'elle est logique et à jour. Priorisez les catégories ou promotions importantes en les plaçant plus tôt dans le menu.

#### 2.1.2 Configuration de la barre de recherche

Cette section contrôle la visibilité de la barre de recherche dans votre menu supérieur.

-   **Barre de recherche :** Un interrupteur (Activé/Désactivé) pour afficher ou masquer la barre de recherche.
    -   *Lorsque activé (Activé) :* Un champ de saisie de recherche apparaîtra dans ou près de votre menu horizontal supérieur, permettant aux clients de rechercher rapidement des produits.
    -   *Lorsque désactivé (Désactivé) :* La barre de recherche sera masquée de la zone du menu supérieur.
    -   *Valeur recommandée :* « Activé ». Une barre de recherche est un outil de navigation crucial pour la plupart des boutiques e-commerce, en particulier celles avec un grand catalogue de produits. Elle améliore considérablement l'expérience utilisateur.
    -   *Scénario marchand :* Vous souhaitez que les clients trouvent facilement des produits en tapant des mots-clés. Activez ce paramètre. Si votre boutique est très petite avec seulement quelques produits, vous pourriez envisager de le désactiver pour gagner de l'espace, mais ce n'est généralement pas recommandé.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | **Éléments de menu** | | |
| | Libellé | N/A | Texte affiché pour l'élément de menu. |
| | Lien | N/A | URL vers laquelle l'élément de menu pointe. |
| | Nouvelle fenêtre | Non (pour les liens internes), Oui (pour les liens externes) | Détermine si le lien s'ouvre dans un nouvel onglet. |
| | Réorganisation | N/A | Modifie l'ordre d'affichage des éléments de menu. |
| | Modifier/Supprimer | N/A | Modifie ou supprime les éléments de menu existants. |
| Page de configuration du module | **Barre de recherche** | Activé | Affiche/masque le champ de saisie de recherche dans le menu supérieur. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes modifications de menu n'apparaissent pas sur le front office.**
R : Après avoir effectué des modifications dans la configuration du module, vous devrez peut-être vider le cache de votre PrestaShop.
-   Allez dans **Paramètres avancés > Performances**.
-   Cliquez sur le bouton « Vider le cache » dans le coin supérieur droit.
-   Videz également le cache de votre navigateur (Ctrl+F5 ou Cmd+R) pour vous assurer de voir la dernière version de votre site.

**Q2 : Les menus déroulants ont l'air étranges ou ne s'affichent pas correctement avec mon thème personnalisé.**
R : Ce module modifie le menu supérieur standard de PrestaShop. Les thèmes personnalisés ont souvent leur propre CSS (style) spécifique pour le menu.
-   **Solution :** Le module inclut son propre CSS pour activer les menus déroulants. Le CSS de votre thème pourrait le remplacer ou entrer en conflit. Vous devrez peut-être faire appel à un développeur web pour inspecter le CSS et ajuster les styles de votre thème ou les styles du module pour assurer la compatibilité.
-   **Vérification temporaire :** Essayez de passer temporairement au thème PrestaShop par défaut (par exemple, Classic) pour voir si les menus déroulants fonctionnent. Si c'est le cas, cela confirme un conflit CSS lié au thème.

**Q3 : Comment traduire les libellés de mes éléments de menu dans d'autres langues ?**
R : Lorsque vous ajoutez ou modifiez un élément de menu, vous verrez un sélecteur de langue à côté du champ « Libellé ».
-   Cliquez sur l'icône du drapeau pour passer à une autre langue.
-   Saisissez le libellé traduit pour cette langue spécifique.
-   Répétez l'opération pour toutes les langues prises en charge par votre boutique.

**Q4 : Puis-je avoir plusieurs niveaux de menus déroulants (par exemple, Catégorie > Sous-catégorie > Sous-sous-catégorie) ?**
R : Le module améliore le menu PrestaShop standard, qui prend généralement en charge un ou deux niveaux de menus déroulants de manière efficace. Bien qu'il soit techniquement possible d'imbriquer des éléments, trop de niveaux peuvent devenir fastidieux pour les utilisateurs.
-   **Meilleure pratique :** Visez un maximum de deux niveaux (élément principal > éléments déroulants). Pour des hiérarchies plus profondes, envisagez d'utiliser des pages de destination de catégories ou une navigation à facettes sur les pages de catégories plutôt que des menus déroulants trop complexes.

**Q5 : La barre de recherche est activée, mais elle n'apparaît pas.**
R :
-   Tout d'abord, assurez-vous que le paramètre « Barre de recherche » dans la configuration du module est bien « Activé ».
-   Deuxièmement, vérifiez si votre thème a un hook ou un style spécifique pour la barre de recherche dans l'en-tête. Certains thèmes peuvent placer la barre de recherche à un endroit différent ou nécessiter une configuration spécifique au sein du thème lui-même.
-   Si le problème persiste, videz votre cache (comme décrit dans la Q1).

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé du module « Menu horizontal supérieur avec sous-menus déroulants » pour les développeurs et les webmasters.

### 4.1 Vue d'ensemble de l'architecture

Le module `blocktopdropdownmenu` est conçu comme un module PrestaShop standard, étendant principalement la fonctionnalité du module `blocktopmenu` de base (ou son équivalent dans les versions PS plus récentes) en injectant du JavaScript et du CSS personnalisés pour activer le comportement de menu déroulant. Il suit un modèle MVC PrestaShop classique pour sa configuration, utilisant `getContent()` pour le formulaire du back-office et enregistrant des hooks pour l'affichage du front-office. Il n'introduit pas de nouvelles tables de base de données ou de structures `ObjectModel` complexes, s'appuyant plutôt sur les valeurs de `Configuration` pour stocker ses paramètres et tirant parti des entités PrestaShop existantes (Catégories, CMS, etc.) pour les liens des éléments de menu.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur d'administration Front-Office ou Back-Office personnalisé. Toute la configuration est gérée dans la méthode `getContent()` du fichier de module principal.

### 4.3 Classes et modèles de base (`classes/`)

Ce module n'introduit aucune classe PHP personnalisée ou définition `ObjectModel` dans le répertoire `classes/`. Toute la logique est contenue dans le fichier principal `blocktopdropdownmenu.php`.

### 4.4 Actifs JavaScript (`views/js/`)

Le module s'appuie fortement sur JavaScript pour créer la fonctionnalité de menu déroulant.

-   `blocktopdropdownmenu/js/blocktopdropdownmenu.js`
    -   **Portée :** Front-office.
    -   **Responsabilité :** Il s'agit du script d'initialisation principal pour le menu déroulant. Il contient probablement la logique pour appliquer le plugin Superfish (ou une bibliothèque de menu déroulant similaire) à l'élément de navigation principal. Il lie les écouteurs d'événements pour les intentions de survol, gère l'expansion/la réduction des éléments de menu et assure la réactivité mobile (par exemple, la conversion du survol en tapotement pour les appareils tactiles ou l'intégration avec un menu hamburger). Il peut également contenir la logique pour le comportement de la barre de recherche si elle est chargée ou basculée dynamiquement.
-   `blocktopdropdownmenu/js/hoverIntent.js`
    -   **Portée :** Front-office.
    -   **Responsabilité :** Un plugin jQuery qui tente de déterminer l'intention de l'utilisateur de survoler un élément. Il aide à prévenir le déclenchement accidentel des menus déroulants en introduisant un délai et en vérifiant le mouvement de la souris, rendant le menu plus fluide et moins « scintillant ». Il s'agit généralement d'une dépendance pour Superfish.
-   `blocktopdropdownmenu/js/superfish-modified.js`
    -   **Portée :** Front-office.
    -   **Responsabilité :** Il s'agit probablement d'une version modifiée du populaire plugin jQuery Superfish, conçu pour créer des menus déroulants à plusieurs niveaux. Il gère les mécanismes de base d'affichage et de masquage des sous-menus au survol, la gestion des animations et potentiellement l'ajout de fonctionnalités d'accessibilité. Le suffixe « modified » suggère qu'il pourrait inclure des adaptations personnalisées pour la structure DOM de PrestaShop ou une compatibilité de thème spécifique.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module fournit un style pour présenter visuellement les menus déroulants.

-   `blocktopdropdownmenu/css/blocktopdropdownmenu.css`
    -   **Portée :** Style client Front-office.
    -   **Responsabilité :** Contient des règles CSS personnalisées spécifiques à ce module, potentiellement en remplaçant les styles de thème par défaut ou en ajoutant de nouveaux styles pour des éléments comme la barre de recherche, des états spécifiques d'éléments de menu ou des ajustements de mise en page généraux pour les menus déroulants.
    -   **Sélecteurs de classe CSS clés :** Les développeurs doivent inspecter ce fichier pour des classes comme `.sf-menu`, `.sf-menu li`, `.sf-menu li ul`, `.sf-menu li li`, etc., qui sont des sélecteurs Superfish courants, ainsi que toutes les classes personnalisées introduites par le module.
-   `blocktopdropdownmenu/css/superfish-modified.css`
    -   **Portée :** Style client Front-office.
    -   **Responsabilité :** Fournit le style visuel de base pour la structure du menu déroulant Superfish. Cela inclut les styles pour l'espacement des éléments de menu, les couleurs d'arrière-plan, les couleurs de texte, les effets de survol, les indicateurs de flèche déroulante et le positionnement des panneaux déroulants. Il est crucial pour l'apparence visuelle du menu à plusieurs niveaux.
    -   **Sélecteurs de classe CSS clés :** Similaire à `blocktopdropdownmenu.css`, ce fichier contiendra les sélecteurs Superfish de base. Les développeurs peuvent les remplacer dans le `custom.css` ou `theme.css` de leur thème pour correspondre à l'esthétique de leur marque.

### 4.6 Structure du template Smarty (`views/templates/`)

-   `blocktopdropdownmenu/blocktopdropdownmenu.tpl`
    -   **Portée :** Template de hook.
    -   **Hook :** `displayTop` (et potentiellement `displayNav` si la structure du thème le permet).
    -   **Responsabilité :** Il s'agit du template principal du front-office responsable du rendu de la structure HTML du menu horizontal supérieur, y compris les éléments de menu principaux et leurs sous-menus déroulants imbriqués. Il itère sur les éléments de menu configurés dans le back-office et génère la structure `<ul><li>` requise par le JavaScript Superfish. Il inclut également la logique de rendu de la barre de recherche si elle est activée.
-   `blocktopdropdownmenu/views/templates/admin/advert.tpl`
    -   **Portée :** Template d'administration.
    -   **Responsabilité :** Affiche probablement une publicité ou un message promotionnel de MyPresta.eu dans la page de configuration du module dans le Back Office.
-   `blocktopdropdownmenu/views/templates/admin/_configure/helpers/form/form.tpl`
    -   **Portée :** Template d'administration.
    -   **Responsabilité :** Ce template est un template d'aide PrestaShop standard utilisé pour rendre le formulaire de configuration principal du module. Il définit la structure et les champs pour la gestion des éléments de menu et le paramètre de la barre de recherche, tel que configuré dans `getContent()`.
-   `blocktopdropdownmenu/views/templates/admin/_configure/helpers/list/list_content.tpl`
    -   **Portée :** Template d'administration.
    -   **Responsabilité :** Ce template est un template d'aide PrestaShop standard utilisé pour rendre la liste des éléments de menu dans le formulaire de configuration, permettant la réorganisation par glisser-déposer, la modification et la suppression.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Ce module ne crée aucune table de base de données personnalisée.
    -   Les paramètres de configuration (par exemple, `MOD_blocktopdropdownmenu_ITEMS`, `MOD_blocktopdropdownmenu_SEARCH`) sont stockés dans la table `ps_configuration`. `MOD_blocktopdropdownmenu_ITEMS` stockera un tableau sérialisé ou une chaîne JSON représentant la structure du menu.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Injecte les actifs CSS et JavaScript (`blocktopdropdownmenu.js`, `hoverIntent.js`, `superfish-modified.js`, `blocktopdropdownmenu.css`, `superfish-modified.css`) requis pour la fonctionnalité de menu déroulant. |
| `displayTop` | Généralement dans la zone d'en-tête principale du thème. | Rend la structure HTML principale du menu horizontal avec les menus déroulants et la barre de recherche. |
| `displayNav` | Souvent dans la barre de navigation tout en haut (au-dessus de `displayTop`). | Peut être utilisé par certains thèmes pour afficher le menu, ou pour des éléments de navigation supplémentaires. Le module peut s'enregistrer ici pour une compatibilité de thème plus large. |
| `actionObjectProductUpdateAfter` | Après la mise à jour d'un produit. | Potentiellement utilisé pour vider le cache du module lié aux liens de produits, garantissant que les éléments de menu liés aux produits sont à jour. |
| `actionObjectProductDeleteAfter` | Après la suppression d'un produit. | Potentiellement utilisé pour vider le cache du module ou supprimer les éléments de menu liés au produit supprimé. |
| `actionObjectManufacturerAddAfter` | Après l'ajout d'un fabricant. | Potentiellement utilisé pour vider le cache du module lié aux liens de fabricants. |
| `actionObjectManufacturerUpdateAfter` | Après la mise à jour d'un fabricant. | Potentiellement utilisé pour vider le cache du module lié aux liens de fabricants. |
| `actionObjectManufacturerDeleteAfter` | Après la suppression d'un fabricant. | Potentiellement utilisé pour vider le cache du module ou supprimer les éléments de menu liés au fabricant supprimé. |
| `actionObjectSupplierAddAfter` | Après l'ajout d'un fournisseur. | Potentiellement utilisé pour vider le cache du module lié aux liens de fournisseurs. |
| `actionObjectSupplierUpdateAfter` | Après la mise à jour d'un fournisseur. | Potentiellement utilisé pour vider le cache du module lié aux liens de fournisseurs. |
| `actionObjectSupplierDeleteAfter` | Après la suppression d'un fournisseur. | Potentiellement utilisé pour vider le cache du module ou supprimer les éléments de menu liés au fournisseur supprimé. |
| `actionObjectCmsAddAfter` | Après l'ajout d'une page CMS. | Potentiellement utilisé pour vider le cache du module lié aux liens de pages CMS. |
| `actionObjectCmsUpdateAfter` | Après la mise à jour d'une page CMS. | Potentiellement utilisé pour vider le cache du module lié aux liens de pages CMS. |
| `actionObjectCmsDeleteAfter` | Après la suppression d'une page CMS. | Potentiellement utilisé pour vider le cache du module ou supprimer les éléments de menu liés à la page CMS supprimée. |
| `actionShopDataDuplication` | Lors de la duplication d'une boutique (dans un contexte multi-boutiques). | Garantit que la configuration du module (éléments de menu, paramètre de barre de recherche) est correctement dupliquée pour la nouvelle boutique. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Menu horizontal supérieur avec sous-menus déroulants », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour aider les marchands et les développeurs avec tout problème ou question lié à la fonctionnalité et à la compatibilité du module.
