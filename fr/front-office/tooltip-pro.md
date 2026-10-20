---
title: "Tooltip Pro - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Tooltip Pro par MyPresta.eu."
sidebar:
  label: "Tooltip Pro - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Tooltip Pro sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/tooltip-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/tooltip-pro/)
>
> ---


# Tooltip Pro

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration spéciale du serveur n'est généralement nécessaire.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Tooltip Pro)

Ceci est l'écran de configuration principal du module Tooltip Pro, où vous contrôlez son comportement général et son apparence.

- **Emplacement du menu :** Back Office > Modules > Gestionnaire de modules > Rechercher "Tooltip Pro" > Cliquer sur "Configurer"

#### Paramètres et options :

1.  **Activer les info-bulles :**

    -   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver l'ensemble de la fonctionnalité d'info-bulle sur votre front office.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (OUI) :* Les info-bulles seront actives sur votre boutique selon vos autres paramètres.
        -   *Lorsqu'désactivé (NON) :* Aucune info-bulle n'apparaîtra sur votre boutique, quelles que soient les entrées d'info-bulles individuelles que vous avez créées.
    -   **Valeur recommandée :** OUI (une fois que vous avez configuré vos info-bulles).
    -   **Scénario / exemple pour le marchand :** Si vous effectuez une maintenance ou souhaitez désactiver temporairement toutes les info-bulles sans les supprimer, définissez ce paramètre sur NON.
2.  **Mettre en évidence les mots-clés des info-bulles :**

    -   **Ce que fait ce paramètre :** Détermine si le texte qui déclenche une info-bulle doit être visuellement mis en évidence sur votre site web.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (OUI) :* Les mots-clés que vous avez définis pour les info-bulles auront un style visuel appliqué (par exemple, un soulignement en pointillés, un gras ou une couleur spécifique, selon le CSS de votre thème ou le style par défaut du module). Cela aide les clients à identifier les éléments interactifs.
        -   *Lorsqu'désactivé (NON) :* Les mots-clés apparaîtront comme du texte normal, mais le survol les déclenchera toujours. Cela peut rendre les info-bulles moins faciles à découvrir.
    -   **Valeur recommandée :** OUI.
    -   **Scénario / exemple pour le marchand :** L'activation de ce paramètre indique clairement à vos clients quels mots sont interactifs, les encourageant à découvrir les informations utiles. Si vous préférez un design très minimaliste et attendez des utilisateurs qu'ils découvrent les info-bulles naturellement, vous pouvez le désactiver.
3.  **Placement de l'info-bulle :**

    -   **Ce que fait ce paramètre :** Contrôle où la fenêtre contextuelle de l'info-bulle apparaît par rapport au texte du mot-clé.
    -   **Effet de la modification de ce paramètre :**
        -   *Options (par exemple, Haut, Bas, Gauche, Droite, Auto) :* Choisir "Haut" fera apparaître l'info-bulle au-dessus du texte, "Bas" en dessous, etc. "Auto" tente de placer intelligemment l'info-bulle pour éviter qu'elle ne sorte de l'écran.
    -   **Valeur recommandée :** Auto.
    -   **Scénario / exemple pour le marchand :** "Auto" est généralement le meilleur choix car il s'adapte aux différentes tailles d'écran et mises en page de contenu. Si vous constatez que les info-bulles masquent constamment du contenu important dans une zone spécifique, vous pouvez expérimenter un placement fixe comme "Bas".
4.  **Animation de l'info-bulle :**

    -   **Ce que fait ce paramètre :** Sélectionne l'effet d'animation lorsqu'une info-bulle apparaît et disparaît.
    -   **Effet de la modification de ce paramètre :**
        -   *Options (par exemple, Fade, Grow, Swing, Slide, Fall) :* Chaque option offre une transition visuelle différente. "Fade" est une simple dissolution, "Grow" s'agrandit, etc.
    -   **Valeur recommandée :** Fade ou Grow.
    -   **Scénario / exemple pour le marchand :** Une animation subtile comme "Fade" ou "Grow" ajoute une touche soignée sans être distrayante. Évitez les animations trop complexes qui pourraient ralentir l'expérience utilisateur ou sembler déplacées par rapport à votre marque.
5.  **Thème de l'info-bulle :**

    -   **Ce que fait ce paramètre :** Vous permet de choisir un thème visuel prédéfini pour vos info-bulles. Cela affecte les couleurs, les bordures et le style général.
    -   **Effet de la modification de ce paramètre :**
        -   *Options (par exemple, Default, Light, Dark, Bordered, Punk) :* Chaque thème applique un ensemble différent de styles CSS.
    -   **Valeur recommandée :** Default ou Light.
    -   **Scénario / exemple pour le marchand :** Choisissez un thème qui correspond le mieux au design général et à l'image de marque de votre boutique. "Light" ou "Default" sont souvent de bons points de départ. Si vous avez un site web à thème sombre, "Dark" pourrait être plus approprié.
6.  **Largeur maximale de l'info-bulle (pixels) :**

    -   **Ce que fait ce paramètre :** Définit la largeur maximale de la boîte contextuelle de l'info-bulle en pixels.
    -   **Effet de la modification de ce paramètre :**
        -   *Saisie d'une valeur (par exemple, 300) :* L'info-bulle ne dépassera pas cette largeur, en renvoyant le texte à la ligne si nécessaire.
        -   *Laisser vide ou 0 :* L'info-bulle s'adaptera automatiquement à son contenu, ce qui peut parfois entraîner des info-bulles très larges.
    -   **Valeur recommandée :** 250-350 pixels.
    -   **Scénario / exemple pour le marchand :** Définir une largeur maximale raisonnable garantit que les info-bulles ne deviennent pas trop larges et ne s'étirent pas sur l'écran, en particulier sur les petits appareils ou dans les mises en page à colonnes étroites.
7.  **Délai avant affichage (millisecondes) :**

    -   **Ce que fait ce paramètre :** Le temps (en millisecondes) pendant lequel un utilisateur doit survoler un mot-clé avant que l'info-bulle n'apparaisse.
    -   **Effet de la modification de ce paramètre :**
        -   *Valeur plus élevée (par exemple, 500 ms) :* Les info-bulles apparaissent après un délai plus long, les empêchant de s'afficher trop rapidement si un utilisateur ne fait que déplacer sa souris sur la page.
        -   *Valeur plus faible (par exemple, 0 ms) :* Les info-bulles apparaissent instantanément.
    -   **Valeur recommandée :** 200-300.
    -   **Scénario / exemple pour le marchand :** Un léger délai (par exemple, 200 ms) offre une expérience utilisateur plus fluide, car il empêche les info-bulles accidentelles d'apparaître et de disparaître rapidement.
8.  **Délai avant masquage (millisecondes) :**

    -   **Ce que fait ce paramètre :** Le temps (en millisecondes) pendant lequel l'info-bulle reste visible après que l'utilisateur a éloigné sa souris du mot-clé.
    -   **Effet de la modification de ce paramètre :**
        -   *Valeur plus élevée (par exemple, 200 ms) :* L'info-bulle reste visible pendant une courte période, permettant aux utilisateurs de déplacer légèrement leur souris sans que l'info-bulle ne disparaisse immédiatement.
        -   *Valeur plus faible (par exemple, 0 ms) :* L'info-bulle disparaît instantanément lorsque la souris quitte le mot-clé.
    -   **Valeur recommandée :** 100-200.
    -   **Scénario / exemple pour le marchand :** Un petit délai ici peut être utile si un utilisateur déplace accidentellement sa souris du mot-clé mais souhaite continuer à lire l'info-bulle.
9.  **Types de pages autorisés pour les info-bulles :**

    -   **Ce que fait ce paramètre :** Spécifie sur quels types de pages les info-bulles doivent être actives.
    -   **Effet de la modification de ce paramètre :**
        -   *Cases à cocher (par exemple, Pages produits, Pages de catégories, Pages CMS, Toutes les pages) :* Sélectionnez les types de pages spécifiques où vous souhaitez que vos info-bulles fonctionnent.
        -   *Sélectionner "Toutes les pages" :* Les info-bulles seront actives partout sur votre boutique.
    -   **Valeur recommandée :** Sélectionnez uniquement les types de pages où vous avez réellement besoin d'info-bulles pour éviter un traitement inutile sur d'autres pages.
    -   **Scénario / exemple pour le marchand :** Si vous utilisez principalement des info-bulles pour les spécifications de produits, vous ne pouvez cocher que "Pages produits". Si vous avez beaucoup de termes techniques sur l'ensemble de votre site, "Toutes les pages" pourrait être approprié.

### 2.2 Écran d'administration dédié : Liste des info-bulles (Back Office > Tooltip Pro > Info-bulles)

Cet écran est l'endroit où vous gérez toutes les info-bulles individuelles que vous souhaitez créer et afficher sur votre boutique. Il sert de centre pour ajouter, modifier et supprimer des entrées d'info-bulles.

- **Nom de l'écran et emplacement du menu :** Back Office > Tooltip Pro > Info-bulles
- **Actions et paramètres disponibles :**
  - **Tableau de la liste des info-bulles :** Affiche une liste de toutes vos info-bulles créées, affichant généralement le mot-clé, le contenu et son statut (activé/désactivé).
  - **Bouton Ajouter une nouvelle info-bulle :** Cliquez ici pour créer une nouvelle entrée d'info-bulle.
  - **Actions Modifier/Supprimer :** Chaque info-bulle de la liste aura des boutons d'action (par exemple, une icône de crayon pour "Modifier", une icône de corbeille pour "Supprimer") pour gérer les entrées individuelles.
  - **Actions en masse :** Souvent, il existe des options pour activer, désactiver ou supprimer plusieurs info-bulles sélectionnées à la fois.

#### Lors de l'ajout/modification d'une info-bulle :

1.  **Mot-clé :**

    -   **Ce que fait ce paramètre :** C'est le mot ou la phrase exacte qui, lorsqu'il est trouvé sur votre site web, déclenchera l'info-bulle.
    -   **Effet de la modification de ce paramètre :** Le module recherchera ce texte spécifique sur vos pages activées. La sensibilité à la casse peut s'appliquer en fonction de la logique interne du module (supposez qu'elle est sensible à la casse pour de meilleurs résultats).
    -   **Valeur recommandée :** Soyez précis. Utilisez l'orthographe et la capitalisation exactes telles qu'elles apparaissent sur votre site.
    -   **Scénario / exemple pour le marchand :** Si vous souhaitez expliquer "Coton Biologique", entrez "Coton Biologique". Si vous entrez "coton biologique", cela pourrait ne pas se déclencher sur "Coton Biologique".
2.  **Contenu de l'info-bulle :**

    -   **Ce que fait ce paramètre :** C'est l'information qui sera affichée dans la fenêtre contextuelle de l'info-bulle. Il s'agit généralement d'un éditeur de texte riche (WYSIWYG) permettant différents types de contenu.
    -   **Effet de la modification de ce paramètre :** Tout ce que vous saisissez ici sera affiché au client lorsqu'il survolera le mot-clé.
    -   **Valeur recommandée :** Restez concis et informatif. Utilisez des images, des vidéos ou des liens avec parcimonie pour éviter de submerger l'utilisateur.
    -   **Scénario / exemple pour le marchand :** Pour "Coton Biologique", vous pourriez ajouter : "Le coton biologique est cultivé sans produits chimiques nocifs, pesticides ou OGM, ce qui est meilleur pour l'environnement et votre peau. [Lien vers un article de blog sur la durabilité]."
3.  **Actif :**

    -   **Ce que fait ce paramètre :** Contrôle si cette entrée d'info-bulle spécifique est active ou inactive.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (OUI) :* Cette info-bulle individuelle apparaîtra sur votre boutique.
        -   *Lorsqu'désactivé (NON) :* Cette info-bulle n'apparaîtra pas, même si le module principal est activé.
    -   **Valeur recommandée :** OUI (pour les info-bulles que vous souhaitez afficher).
    -   **Scénario / exemple pour le marchand :** Vous pouvez désactiver temporairement une info-bulle si l'information est obsolète ou si une fonctionnalité de produit qu'elle décrit n'est plus disponible, sans supprimer l'entrée entière.

-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Commencez par identifier les questions courantes ou les termes déroutants sur vos pages produits, pages de catégories ou pages CMS importantes.
    2.  Allez dans **Back Office > Tooltip Pro > Info-bulles**.
    3.  Cliquez sur "Ajouter une nouvelle info-bulle".
    4.  Entrez le **Mot-clé** exact que vous souhaitez expliquer.
    5.  Rédigez un **Contenu d'info-bulle** clair, concis et utile.
    6.  Assurez-vous que **Actif** est défini sur OUI.
    7.  Enregistrez vos modifications.
    8.  Testez l'info-bulle sur votre front office pour vous assurer qu'elle apparaît correctement et fournit les informations souhaitées.
    9.  Examinez régulièrement vos info-bulles pour vous assurer que les informations restent exactes et pertinentes.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activer les info-bulles | OUI | Interrupteur principal pour toutes les fonctionnalités d'info-bulles. |
| | Mettre en évidence les mots-clés des info-bulles | OUI | Marque visuellement les mots-clés sur le front-office. |
| | Placement de l'info-bulle | Auto | Position de la fenêtre contextuelle de l'info-bulle par rapport au mot-clé. |
| | Animation de l'info-bulle | Fade / Grow | Effet visuel lorsque l'info-bulle apparaît/disparaît. |
| | Thème de l'info-bulle | Default / Light | Style (couleurs, bordures) de la boîte d'info-bulle. |
| | Largeur maximale de l'info-bulle (pixels) | 250-350 | Empêche les info-bulles de devenir trop larges. |
| | Délai avant affichage (ms) | 200-300 | Temps avant que l'info-bulle n'apparaisse au survol. |
| | Délai avant masquage (ms) | 100-200 | Temps avant que l'info-bulle ne disparaisse après le survol. |
| | Types de pages autorisés | Sélectionner selon les besoins | Restreint les info-bulles à des types de pages spécifiques (par exemple, Produit, Catégorie). |
| **Liste des info-bulles (Ajouter/Modifier)** | Mot-clé | Texte exact | Le mot/la phrase spécifique qui déclenche l'info-bulle. |
| | Contenu de l'info-bulle | Concis, informatif | L'information affichée dans l'info-bulle. |
| | Actif | OUI | Active/désactive une entrée d'info-bulle individuelle. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes info-bulles n'apparaissent pas sur le front office, même si je les ai créées.**
R :

1.  **Vérifier l'interrupteur principal :** Allez dans **Modules > Gestionnaire de modules > Configurer Tooltip Pro**. Assurez-vous que "Activer les info-bulles" est défini sur OUI.
2.  **Vérifier le statut de l'info-bulle individuelle :** Allez dans **Tooltip Pro > Info-bulles**. Assurez-vous que l'info-bulle spécifique que vous attendez de voir a "Actif" défini sur OUI.
3.  **Vérifier le type de page :** Vérifiez que le paramètre "Types de pages autorisés pour les info-bulles" inclut le type de page que vous consultez actuellement (par exemple, si vous êtes sur une page produit, "Pages produits" doit être coché).
4.  **Correspondance du mot-clé :** Assurez-vous que le "Mot-clé" que vous avez saisi pour l'info-bulle correspond exactement au texte de votre front office, y compris la capitalisation et les espaces.
5.  **Vider le cache :** Parfois, le cache de PrestaShop peut empêcher l'affichage de nouveau contenu. Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache".

**Q : Le contenu de l'info-bulle semble étrange ou ne s'affiche pas correctement (par exemple, images cassées, formatage bizarre).**
R :

1.  **Erreurs HTML :** Si vous avez utilisé l'éditeur de texte riche, assurez-vous de n'avoir introduit aucune balise HTML cassée. Passez à la vue du code source dans l'éditeur pour vérifier les balises non fermées ou les attributs invalides.
2.  **Chemins d'image :** Si les images ne s'affichent pas, vérifiez que l'URL de l'image dans le contenu de votre info-bulle est correcte et accessible. Utilisez des URL absolues (commençant par `http://` ou `https://`) pour les images hébergées sur votre serveur.
3.  **Conflits CSS :** Le CSS de votre thème pourrait remplacer le style du module. Il s'agit plutôt d'un problème de développeur, mais vous pouvez essayer de changer le "Thème de l'info-bulle" dans la configuration du module pour voir si un thème différent le résout.

**Q : Les info-bulles apparaissent sur des pages où je ne les veux pas.**
R :

1.  **Examiner les "Types de pages autorisés" :** Allez dans **Modules > Gestionnaire de modules > Configurer Tooltip Pro**. Examinez attentivement les "Types de pages autorisés pour les info-bulles" et décochez tous les types de pages où vous ne souhaitez pas que les info-bulles apparaissent.
2.  **Spécificité du mot-clé :** Si un mot-clé est très générique (par exemple, "produit"), il peut apparaître sur de nombreuses pages. Envisagez de rendre vos mots-clés plus spécifiques ou de les restreindre à certains types de pages.

**Q : Comment traduire mes info-bulles dans d'autres langues ?**
R :

1.  **Modifier l'info-bulle :** Allez dans **Tooltip Pro > Info-bulles** et cliquez sur "Modifier" sur l'info-bulle que vous souhaitez traduire.
2.  **Sélecteur de langue :** Dans l'éditeur de texte riche "Contenu de l'info-bulle", vous devriez voir un sélecteur de langue (généralement une icône de drapeau ou une liste déroulante). Sélectionnez la langue souhaitée et saisissez le contenu traduit pour cette langue. Répétez l'opération pour toutes les langues.
3.  **Traduction du mot-clé :** Le "Mot-clé" lui-même n'est généralement pas traduit par le module, car il recherche le texte exact sur la page. Si vos mots-clés changent selon la langue (par exemple, "Size Guide" vs. "Guide des Tailles"), vous devrez créer des entrées d'info-bulles distinctes pour le mot-clé de chaque langue.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Vue d'ensemble de l'architecture

Le module Tooltip Pro suit une architecture de module PrestaShop standard, tirant parti des principes MVC. Il se compose principalement de :

-   Une classe de module principale (`index.php`) pour l'installation, la désinstallation et la configuration.
-   Des contrôleurs d'administration dédiés (`AdminTooltipsListController`) pour gérer les entités d'info-bulles dans le Back Office.
-   Des contrôleurs frontaux (`ajax.php`) pour gérer les requêtes de contenu dynamique si nécessaire (bien que le rendu principal des info-bulles soit côté client).
-   Du JavaScript côté client (utilisant la bibliothèque Tooltipster) pour détecter les mots-clés et afficher les info-bulles dynamiquement.
-   Une table de base de données personnalisée (`ps_tooltips`) pour stocker les définitions des info-bulles.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   `controllers/front/ajax.php`
    -   **Nom de la classe et classe parente :** `TooltipsAjaxModuleFrontController` étend `ModuleFrontController`.
    -   **Responsabilité :** Ce contrôleur est conçu pour gérer les requêtes AJAX depuis le front-office. Bien que le contenu principal de l'info-bulle soit souvent rendu directement dans le HTML, ce contrôleur pourrait être utilisé pour le chargement de contenu dynamique, la récupération de données d'info-bulle à la demande ou d'autres fonctionnalités interactives. Il répond à des routes spécifiques définies par le module.
-   `controllers/front/index.php`
    -   **Nom de la classe et classe parente :** `TooltipsIndexModuleFrontController` étend `ModuleFrontController`.
    -   **Responsabilité :** Ce contrôleur pourrait servir de solution de repli ou de placeholder. Dans de nombreux modules simples, `index.php` dans le répertoire du contrôleur frontal n'est pas directement utilisé pour le rendu d'une page, mais pourrait être présent pour l'exhaustivité architecturale ou pour gérer le routage par défaut du module si aucun autre contrôleur frontal spécifique ne correspond. Pour Tooltip Pro, l'interaction principale du front-office se fait via JavaScript et les hooks.

#### Contrôleurs d'administration du Back-Office

-   `controllers/admin/AdminTooltipsList.php`
    -   **Nom de la classe et classe parente :** `AdminTooltipsListController` étend `ModuleAdminController`.
    -   **Nom de l'onglet et entité gérée :** Ce contrôleur gère la liste des "Info-bulles" dans le Back Office de PrestaShop. Il est responsable de l'affichage de la grille des info-bulles existantes, de la gestion des opérations d'ajout/modification/suppression pour les objets `Tooltip` et du rendu des formulaires associés. Il interagit directement avec l'`ObjectModel` `Tooltip`.
-   `controllers/admin/index.php`
    -   **Nom de la classe et classe parente :** `TooltipsAdminIndexModuleFrontController` étend `ModuleAdminController`.
    -   **Nom de l'onglet et entité gérée :** Similaire à `index.php` du front-office, cela pourrait être un placeholder ou un point d'entrée par défaut pour la section d'administration du module. La gestion principale est assurée par `AdminTooltipsList.php`.

### 4.3 Classes et modèles principaux (`classes/`)

Le dossier du module n'indique pas de répertoire `classes/` spécifique, ce qui implique que l'`ObjectModel` `Tooltip` principal et la logique associée pourraient être définis directement dans le fichier `tooltips/index.php` ou générés dynamiquement.
En supposant une structure de module PrestaShop standard, il y aurait généralement une classe `Tooltip.php`.

-   **`Tooltip` (hypothétique, probablement dans `index.php` ou un `classes/Tooltip.php` dédié si présent) :**
    -   **Table de base de données :** `ps_tooltips` (ou `_PREFIX_tooltips`)
    -   **Étend `ObjectModel` :** Oui.
    -   **Champs `$definition` :**
        -   `id_tooltip` : Clé primaire (INT)
        -   `keyword` : La chaîne de texte à mettre en évidence (VARCHAR)
        -   `content` : Le contenu HTML de l'info-bulle (HTML, TEXT)
        -   `active` : Booléen pour le statut actif/inactif (TINYINT)
        -   `date_add` : Date de création (DATETIME)
        -   `date_upd` : Date de dernière mise à jour (DATETIME)
        -   `id_shop` : ID de la boutique pour le multi-boutique (INT)
        -   `id_lang` : ID de la langue pour le contenu multilingue (INT)
    -   **Méthodes publiques clés :** Méthodes `ObjectModel` standard (`add()`, `update()`, `delete()`, `getFields()`). Les méthodes personnalisées pourraient inclure `getTooltipsByShopAndLang()` ou `getKeywordsForPageType()`.

### 4.4 Actifs JavaScript (`views/js/`)

Le module utilise la bibliothèque `Tooltipster` pour sa fonctionnalité d'info-bulle.

-   `tooltips/lib/tooltipster/js/plugins/tooltipster/SVG/tooltipster-SVG.js`
    -   **Portée :** Front-office.
    -   **Description :** Un plugin pour la bibliothèque Tooltipster spécifiquement pour la gestion des éléments SVG. Si vos info-bulles doivent interagir avec ou être placées sur des graphiques SVG, ce plugin fournit la fonctionnalité nécessaire.
-   `tooltips/lib/tooltipster/js/tooltipster.bundle.js`
    -   **Portée :** Front-office.
    -   **Description :** La version complète et groupée de la bibliothèque Tooltipster, y compris son cœur et potentiellement d'autres plugins courants. Cela fournit la fonctionnalité principale pour créer et gérer des info-bulles.
-   `tooltips/lib/tooltipster/js/tooltipster.core.js`
    -   **Portée :** Front-office.
    -   **Description :** La fonctionnalité principale de la bibliothèque Tooltipster. Ce fichier contient la logique essentielle pour la création, le positionnement, les événements et le style des info-bulles.
-   `tooltips/views/js/tooltips.js`
    -   **Portée :** Front-office.
    -   **Description :** Il s'agit du JavaScript personnalisé du module.
        -   **Écouteurs d'événements :** Se lie probablement à l'événement `ready` du document (`$(document).ready()` ou similaire) pour initialiser les info-bulles.
        -   **Manipulation du DOM :** Analyse le contenu de la page pour les mots-clés définis, les enveloppe dans un élément HTML spécifique (par exemple, `<span class="tooltip-keyword">`), puis initialise la bibliothèque Tooltipster sur ces éléments.
        -   **Initialisation de Tooltipster :** Configure Tooltipster avec les paramètres du Back Office du module (placement, animation, thème, délais, largeur maximale).
        -   **Appels AJAX :** Effectue potentiellement des appels AJAX à `controllers/front/ajax.php` pour récupérer le contenu de l'info-bulle dynamiquement, bien que la description du module suggère que le contenu est souvent pré-rendu.
        -   **Interaction mobile :** Gère les événements de toucher pour les appareils mobiles afin de déclencher les info-bulles.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `tooltips/lib/tooltipster/css/tooltipster.bundle.css`
    -   **Portée :** Style client du front-office.
    -   **Description :** La feuille de style principale de la bibliothèque Tooltipster, contenant les styles par défaut pour la boîte d'info-bulle, les flèches et les différents thèmes.
-   `tooltips/lib/tooltipster/css/tooltipster.core.css`
    -   **Portée :** Style client du front-office.
    -   **Description :** CSS de base pour la bibliothèque Tooltipster, définissant les propriétés visuelles essentielles pour les info-bulles.
-   `tooltips/views/css/tooltips-admin.css`
    -   **Portée :** Style des formulaires d'administration du Back-office.
    -   **Description :** Contient des styles spécifiques pour les pages de configuration du module et le contrôleur `AdminTooltipsList` dans le Back Office de PrestaShop, garantissant une interface d'administration cohérente et conviviale.
-   `tooltips/views/css/tooltips.css`
    -   **Portée :** Style client du front-office.
    -   **Description :** Il s'agit du CSS personnalisé du front-office du module.
        -   **Composants d'interface utilisateur principaux :** Style les mots-clés mis en évidence (par exemple, `span.tooltip-keyword`).
        -   **Sélecteurs de classe CSS clés :** Les développeurs peuvent remplacer les styles pour `.tooltip-keyword` ou les classes de thème Tooltipster spécifiques (par exemple, `.tooltipster-base`, `.tooltipster-light`) dans le `custom.css` de leur thème ou en créant un fichier d'override.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   `tooltips/views/tooltips.tpl`
    -   **Portée :** Template de hook du front-office.
    -   **Description :** Ce template est probablement accroché à `displayHeader` ou `displayFooter` pour générer les variables JavaScript nécessaires et potentiellement le script d'initialisation pour le fichier `tooltips.js`. Il pourrait transmettre les paramètres de configuration du Back Office (par exemple, `tooltip_placement`, `tooltip_animation`, `tooltip_theme`) en tant que variables Smarty au JavaScript. Il ne rend pas directement le contenu de l'info-bulle lui-même, car cela est géré dynamiquement par JavaScript.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   `ps_tooltips` : Stocke les définitions de chaque info-bulle.
        -   `id_tooltip` (PK, INT)
        -   `keyword` (VARCHAR)
        -   `content` (TEXT, HTML autorisé)
        -   `active` (TINYINT(1))
        -   `date_add` (DATETIME)
        -   `date_upd` (DATETIME)
        -   `id_shop` (INT)
        -   `id_lang` (INT)
    -   `ps_configuration` : Stocke les paramètres à l'échelle du module (par exemple, `TOOLTIPS_PRO_ENABLED`, `TOOLTIPS_PRO_HIGHLIGHT`, `TOOLTIPS_PRO_PLACEMENT`, etc.).
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Injecte les fichiers CSS et JavaScript (bibliothèque Tooltipster, `tooltips.js` et styles spécifiques au module) dans la page. Génère également les variables de configuration pour JS. |
| `displayBackOfficeHeader` | Dans la section `<head>` de chaque page du Back Office. | Injecte le CSS spécifique à l'administration (`tooltips-admin.css`) et potentiellement du JS pour les pages de configuration et de liste du module. |
| `actionFrontControllerSetMedia` | Après que les médias ont été définis pour un contrôleur frontal. | Permet au module d'ajouter conditionnellement son CSS/JS en fonction du contexte de la page actuelle (par exemple, uniquement sur les pages produits si configuré). |
| `moduleRoutes` | Lors de l'initialisation du routeur. | Enregistre des routes front-office personnalisées pour `ajax.php` si le chargement de contenu dynamique est utilisé. |
| `actionObjectTooltipAddAfter` | Après l'ajout d'un objet `Tooltip`. | Peut être utilisé pour vider le cache ou pour la journalisation. |
| `actionObjectTooltipUpdateAfter` | Après la mise à jour d'un objet `Tooltip`. | Peut être utilisé pour vider le cache ou pour la journalisation. |
| `actionObjectTooltipDeleteAfter` | Après la suppression d'un objet `Tooltip`. | Peut être utilisé pour vider le cache ou pour la journalisation. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour votre module Tooltip Pro, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à assurer le fonctionnement parfait de votre module et à vous aider à améliorer votre boutique PrestaShop.
