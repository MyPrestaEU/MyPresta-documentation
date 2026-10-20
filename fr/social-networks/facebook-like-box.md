---
title: "Facebook Like Box - Manuel du Marchand & Guide de Configuration"
description: ""
sidebar:
  label: "Facebook Like Box - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Facebook Like Box sur MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-like-box.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/facebook-like-box/)
>
> ---


# Facebook Like Box

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et tout module interagissant avec des API externes comme Facebook.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal de votre module Facebook Like Box. Ici, vous définirez l'apparence et le comportement de votre Like Box sur votre boutique.

**Nom de l'écran et emplacement du menu :** Back Office > Modules > Gestionnaire de modules > Facebook Like Box > Configurer

| Paramètre / Option | Ce que fait ce paramètre | Effet de la modification de ce paramètre | Valeur recommandée | Scénario / exemple pour le marchand |
| --- | --- | --- | --- | --- |
| **URL de la page Facebook** | C'est le lien direct vers votre page Facebook officielle. | *Si défini :* La Like Box affichera le contenu de cette page Facebook spécifique. *Si vide :* Le module ne fonctionnera pas correctement car il ne saura pas quelle page afficher. | L'URL de votre page Facebook (par exemple, `https://www.facebook.com/myprestaeu`) | Vous souhaitez promouvoir la page Facebook principale de votre entreprise. |
| **ID d'application (Facebook)** | Votre ID d'application Facebook, requis pour certaines fonctionnalités avancées et intégrations API. | *Si défini :* Permet au module d'interagir avec l'API Graph de Facebook en utilisant votre application. *Si vide :* Peut entraîner des erreurs "App non configurée" si le module nécessite un accès API. | Votre ID d'application Facebook (par exemple, `123456789012345`) | Vous devez résoudre une erreur "App non configurée" ou activer des fonctionnalités avancées de l'API Facebook. |
| **Largeur** | Contrôle la largeur de la Facebook Like Box en pixels. | *Si défini à une valeur spécifique (par exemple, 280) :* La Like Box conservera cette largeur exacte. *Si laissé vide ou défini à 0 :* La Like Box tentera d'être réactive et d'ajuster sa largeur automatiquement pour s'adapter à son conteneur. | Laisser vide pour la détection automatique (comportement réactif) ou définir une valeur spécifique comme `280` si vous avez besoin d'une largeur fixe. | Vous voulez que la Like Box s'intègre parfaitement dans une colonne étroite, vous la définissez donc à `280`. |
| **Hauteur** | Contrôle la hauteur de la Facebook Like Box en pixels. | *Si défini à une valeur spécifique (par exemple, 500) :* La Like Box conservera cette hauteur exacte. *Si laissé vide ou défini à 0 :* La Like Box tentera d'être réactive et d'ajuster sa hauteur automatiquement. | Laisser vide pour la détection automatique (comportement réactif) ou définir une valeur spécifique comme `500` si vous souhaitez afficher plus de flux de publications. | Vous souhaitez afficher plus de publications récentes de votre page Facebook, vous augmentez donc la hauteur à `500`. |
| **Afficher les visages** | Détermine si les photos de profil des personnes qui ont aimé votre page sont affichées. | *Si activé (OUI) :* De petites photos de profil de certains de vos fans Facebook apparaîtront sous le bouton "J'aime", ajoutant une preuve sociale. *Si désactivé (NON) :* Seuls le bouton "J'aime" et les informations de la page seront affichés, sans les visages individuels. | OUI | Vous voulez montrer que de vraies personnes aiment votre page, encourageant les autres à la rejoindre. |
| **Afficher le flux** | Contrôle si les publications récentes de votre page Facebook sont affichées dans la Like Box. | *Si activé (OUI) :* Vos dernières publications Facebook défileront dans la Like Box, fournissant du contenu frais. *Si désactivé (NON) :* Seuls la couverture de la page, le profil et le bouton "J'aime" seront visibles, rendant la boîte plus compacte. | OUI | Vous publiez fréquemment des mises à jour sur Facebook et souhaitez les partager directement sur votre boutique. |
| **Afficher l'en-tête** | Contrôle si l'en-tête "Facebook" est affiché en haut de la Like Box. | *Si activé (OUI) :* Un petit titre "Facebook" apparaîtra en haut du widget. *Si désactivé (NON) :* L'en-tête sera masqué, rendant le widget plus propre et mieux intégré. | NON | Vous préférez un look minimaliste pour la Like Box et n'avez pas besoin de l'en-tête "Facebook" explicite. |
| **Petit en-tête** | Utilise une version plus petite de l'en-tête. | *Si activé (OUI) :* L'en-tête sera plus compact. *Si désactivé (NON) :* La taille standard de l'en-tête sera utilisée. | NON | Vous voulez économiser de l'espace vertical dans votre mise en page. |
| **Masquer la couverture** | Masque la photo de couverture de votre page Facebook. | *Si activé (OUI) :* Seuls la photo de profil et le nom de votre page seront visibles, rendant le widget plus compact. *Si désactivé (NON) :* La photo de couverture de votre page Facebook sera affichée en haut du widget. | NON | Vous avez un espace très étroit et souhaitez privilégier le bouton "J'aime" et les publications plutôt que la photo de couverture. |
| **Adapter à la largeur du conteneur** | Permet à la Like Box d'ajuster automatiquement sa largeur pour s'adapter au conteneur parent dans lequel elle est placée. | *Si activé (OUI) :* Le widget se redimensionnera pour remplir la largeur disponible, le rendant réactif. *Si désactivé (NON) :* Le widget conservera le paramètre `Largeur` spécifié, pouvant entraîner un débordement ou un espace vide. | OUI | Vous voulez que la Like Box s'affiche correctement sur tous les appareils et toutes les tailles d'écran sans ajustements manuels. |
| **CSS personnalisé** | Vous permet d'ajouter des règles CSS personnalisées pour styliser davantage la Like Box. | *Si rempli de code CSS :* Vos styles personnalisés seront appliqués, remplaçant les styles par défaut. *Si vide :* Le module utilisera son style par défaut ou le style par défaut de Facebook. | Laisser vide sauf si vous avez des besoins de style spécifiques. | Vous voulez changer la taille ou la couleur de la police du texte dans la Like Box pour correspondre au thème de votre marque. |
| **Hook pour afficher le module** | Sélectionne l'endroit où la Like Box apparaîtra dans votre boutique. | *Si un hook est sélectionné :* Le module affichera son contenu à cet emplacement spécifique (par exemple, `displayRightColumn`, `displayFooter`). *Si aucun hook n'est sélectionné :* Le module ne sera pas visible sur votre front office. | `displayRightColumn` ou `displayLeftColumn` sont courants, mais choisissez en fonction de la mise en page de votre thème. | Vous voulez que la Like Box soit visible sur le côté de vos listes de produits, vous choisissez donc `displayRightColumn`. |
| **Couleur de fond** | Définit la couleur de fond de la Like Box. | *Si une couleur est sélectionnée :* La Like Box aura cette couleur de fond. *Si laissé vide :* La Like Box héritera généralement de la couleur de fond de son conteneur parent ou utilisera celle par défaut de Facebook. | Laisser vide ou faire correspondre la couleur de fond de votre thème. | Votre thème a un fond sombre, et vous voulez que la Like Box s'y intègre, vous définissez donc une couleur de fond sombre. |
| **Couleur de la bordure** | Définit la couleur de la bordure autour de la Like Box. | *Si une couleur est sélectionnée :* La Like Box aura une bordure de cette couleur. *Si laissé vide :* La Like Box n'aura généralement pas de bordure ou une bordure Facebook par défaut. | Laisser vide ou faire correspondre les couleurs de bordure de votre thème. | Vous voulez une bordure grise subtile autour de la Like Box pour la séparer des autres contenus. |

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | URL de la page Facebook | L'URL de votre page Facebook | Lie le widget à votre page Facebook spécifique. |
| Configuration du module | ID d'application (Facebook) | Vide (si non requis) | Votre ID d'application Facebook pour l'intégration API. |
| Configuration du module | Largeur | Vide (Réactif) | Contrôle la largeur du widget ; vide pour l'ajustement automatique. |
| Configuration du module | Hauteur | Vide (Réactif) | Contrôle la hauteur du widget ; vide pour l'ajustement automatique. |
| Configuration du module | Afficher les visages | OUI | Affiche les photos de profil des "likers" pour la preuve sociale. |
| Configuration du module | Afficher le flux | OUI | Affiche les publications récentes de votre page Facebook. |
| Configuration du module | Afficher l'en-tête | NON | Masque le titre "Facebook" pour un look plus épuré. |
| Configuration du module | Petit en-tête | NON | Utilise un en-tête plus petit si `Afficher l'en-tête` est OUI. |
| Configuration du module | Masquer la couverture | NON | Affiche la photo de couverture de votre page Facebook. |
| Configuration du module | Adapter à la largeur du conteneur | OUI | Assure que le widget est réactif à son conteneur parent. |
| Configuration du module | CSS personnalisé | Vide | Permet un style avancé avec des règles CSS personnalisées. |
| Configuration du module | Hook pour afficher le module | `displayRightColumn` (ou colonne pertinente) | Détermine où le module apparaît sur votre boutique. |
| Configuration du module | Couleur de fond | Vide | Définit la couleur de fond du widget. |
| Configuration du module | Couleur de la bordure | Vide | Définit la couleur de la bordure du widget. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : La Facebook Like Box n'apparaît pas sur ma boutique. Que dois-je faire ?**
R1 :

-   **Vérifier le statut du module :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que le module "Facebook Like Box" est installé et activé.
-   **Vérifier la sélection du hook :** Dans la configuration du module, assurez-vous d'avoir sélectionné un "Hook pour afficher le module" (par exemple, `displayRightColumn`, `displayFooter`). Si votre thème ne rend pas le hook sélectionné, il n'apparaîtra pas. Essayez un autre hook courant.
-   **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions plus anciennes). Parfois, le cache de PrestaShop empêche les nouveaux modules d'apparaître immédiatement.
-   **URL de la page Facebook :** Vérifiez que l'"URL de la page Facebook" dans la configuration du module est correcte et accessible.

**Q2 : La Like Box semble trop large/étroite ou ne s'adapte pas correctement à mon thème.**
R2 :

-   **Paramètres réactifs :** Dans la configuration du module, assurez-vous que "Adapter à la largeur du conteneur" est défini sur OUI, et laissez les champs "Largeur" et "Hauteur" vides. Cela permet à Facebook de gérer la réactivité.
-   **Conflits de thème :** Le CSS de votre thème pourrait remplacer les styles du module. Si vous êtes à l'aise avec le CSS, utilisez les outils de développement de votre navigateur (F12) pour inspecter l'élément et voir quelles règles CSS sont appliquées.
-   **CSS personnalisé :** Utilisez le champ "CSS personnalisé" dans la configuration du module pour ajouter des règles spécifiques afin d'ajuster sa taille ou son apparence si nécessaire. Par exemple : `.fb_iframe_widget { max-width: 100% !important; }`.

**Q3 : La Like Box affiche une erreur ou ne charge pas le contenu de ma page Facebook.**
R3 :

-   **URL correcte :** Vérifiez que l'"URL de la page Facebook" est absolument correcte et pointe vers une page Facebook publique (pas un profil personnel ou un groupe).
-   **Problèmes d'API Facebook :** Occasionnellement, l'API de Facebook peut rencontrer des problèmes temporaires. Attendez un peu et vérifiez à nouveau.
-   **Restrictions de page :** Assurez-vous que votre page Facebook n'a pas de restrictions de pays ou d'âge qui pourraient empêcher le widget de se charger pour tous les visiteurs.

:::caution
\*\*Erreur "App non configurée" (Module Version 1.8 et supérieure)\*\*
Si vous rencontrez une erreur "App non configurée", en particulier avec la version 1.8 ou supérieure du module, qui prend en charge l'API Facebook Graph v18.0 :
1. \*\*Saisissez votre ID d'application Facebook :\*\* Assurez-vous d'avoir correctement saisi votre ID d'application Facebook dans le champ de configuration du module.
2. \*\*Vérifiez les paramètres de domaine sur Facebook :\*\* Connectez-vous à votre compte développeur Facebook ([developers.facebook.com](https://developers.facebook.com/)). Accédez aux paramètres de votre application et confirmez que le domaine de votre boutique (par exemple, `votreboutique.com`) est correctement ajouté et vérifié dans les paramètres de l'application.
:::

**Q4 : Puis-je avoir plusieurs Facebook Like Boxes sur différentes pages ?**
R4 : Ce module est conçu pour afficher une seule Facebook Like Box configurée globalement. Si vous avez besoin de plusieurs Like Boxes distinctes (par exemple, pour différentes pages Facebook ou avec des paramètres différents), vous devriez généralement installer le module plusieurs fois (si pris en charge par le système de modules de PrestaShop, ce qui est rare pour les modules à instance unique) ou utiliser du code personnalisé. Pour ce module spécifique, il s'agit généralement d'une seule instance, une seule configuration.

**Q5 : Comment traduire le texte dans la Like Box (par exemple, "J'aime la Page") ?**
R5 : Le texte dans la Facebook Like Box elle-même (comme "J'aime la Page", "Suivre", "Partager") est contrôlé par Facebook en fonction des paramètres de langue du navigateur de l'utilisateur et de la propre localisation de Facebook. Ce module ne traduit pas directement ces éléments. Tout texte *autour* de la Like Box que vous ajoutez dans votre thème ou d'autres modules serait traduisible via le système de traduction de PrestaShop.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module Facebook Like Box (`likebox`) est un module PrestaShop standard suivant un modèle MVC de base. Il utilise principalement la classe `Module` pour l'installation, la désinstallation et la gestion de la configuration. La fonctionnalité principale implique le rendu d'un template Smarty qui intègre le plugin de page Facebook (anciennement Like Box) à l'aide du SDK JavaScript officiel de Facebook. Les paramètres de configuration sont stockés dans `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la configuration est gérée dans la méthode `getContent()` du fichier de module principal.

### 4.3 Classes et modèles de base (`classes/`)

Ce module ne définit aucune classe personnalisée et n'étend pas `ObjectModel`. Toute la logique est contenue dans le fichier de module principal (`likebox/ar.php`).

### 4.4 Actifs JavaScript (`views/js/`)

-   **`likebox/jscolor/jscolor.js`**

    *   **Portée :** Back-office (Page de configuration de l'administration)
    *   **Objectif :** Il s'agit d'une bibliothèque JavaScript tierce qui fournit une fonctionnalité de sélecteur de couleurs. Elle est utilisée sur la page de configuration du module pour permettre au marchand de sélectionner visuellement les paramètres "Couleur de fond" et "Couleur de la bordure".
    *   **Interaction :** Elle se lie à des champs de saisie spécifiques (probablement avec une classe comme `jscolor`) pour ouvrir une palette de sélection de couleurs.
-   **`likebox/script.js`**

    *   **Portée :** Back-office (Page de configuration de l'administration)
    *   **Objectif :** Ce script gère les mises à jour dynamiques et la fonctionnalité de prévisualisation en direct sur la page de configuration du module. Il prend les paramètres de saisie du marchand (URL de la page Facebook, largeur, hauteur, affichage des visages, etc.) et met à jour dynamiquement un `<iframe>` ou une zone de prévisualisation pour montrer à quoi ressemblera la Facebook Like Box.
    *   **Interaction :**
        *   Écoute les événements `change` et `keyup` sur divers champs de saisie (par exemple, `#facebook_page_url`, `#width`, `#height`, cases à cocher).
        *   Construit les paramètres d'URL du plugin de page Facebook en fonction des paramètres actuels.
        *   Met à jour l'attribut `src` d'un `<iframe>` de prévisualisation ou génère dynamiquement le code d'intégration du SDK Facebook pour refléter les changements en temps réel.
        *   Utilise probablement `jscolor.js` pour obtenir les valeurs de couleur pour le fond et la bordure.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`likebox/css.css`**

    *   **Portée :** Back-office (Page de configuration de l'administration)
    *   **Objectif :** Fournit le style pour le formulaire de configuration du module dans le Back Office de PrestaShop. Cela peut inclure des ajustements de mise en page, le style des champs de saisie ou le style de la zone de prévisualisation en direct.
    *   **Sélecteurs clés :** Cible probablement les éléments dans la sortie de `getContent()`, tels que les groupes de formulaires, les étiquettes et le conteneur de prévisualisation.
-   **`likebox/css/css.css`**

    *   **Portée :** Front-office (Boutique côté client)
    *   **Objectif :** Fournit un style minimal pour le widget Facebook Like Box lui-même, principalement pour s'assurer qu'il s'intègre bien à la mise en page de la boutique. Cela peut inclure un rembourrage par défaut, des marges ou des ajustements réactifs de base.
    *   **Sélecteurs clés :** Cible l'élément conteneur où le widget Facebook est intégré (par exemple, `.facebook_like_box_container`) et applique potentiellement `max-width: 100%` pour la réactivité. Les développeurs peuvent remplacer ces styles dans le `custom.css` ou `theme.css` de leur thème.

### 4.6 Structure du template Smarty (`views/templates/`)

Les templates du module sont situés directement dans le répertoire racine du module.

-   **`likebox/header.tpl`**

    *   **Portée :** Front-office
    *   **Hook :** `displayHeader`
    *   **Objectif :** Ce template est conçu pour être accroché à `displayHeader`. Son rôle principal est d'inclure le SDK JavaScript de Facebook, qui est nécessaire pour que le plugin de page Facebook s'affiche correctement. Il contient également l'élément `div` où la Like Box sera rendue par le SDK.
    *   **Sortie :**

        ```
        <div id="fb-root"></div><script> (function(d, s, id) { var js, fjs = d.getElementsByTagName(s)[0]; if (d.getElementById(id)) return; js = d.createElement(s); js.id = id; js.src = "//connect.facebook.net/en\_US/sdk.js#xfbml=1&version=v2.8&appId={$app\_id}"; // Version might vary, appId added fjs.parentNode.insertBefore(js, fjs); }(document, 'script', 'facebook-jssdk'));</script><div class="fb-page" data-href="{$facebook\_page\_url}" data-width="{$width}" data-height="{$height}" data-small-header="{$small\_header}" data-adapt-container-width="{$adapt\_container\_width}" data-hide-cover="{$hide\_cover}" data-show-facepile="{$show\_faces}" data-show-posts="{$show\_stream}" data-colorscheme="{$colorscheme}" data-header="{$show\_header}"> <div class="fb-xfbml-parse-ignore"> <blockquote cite="{$facebook\_page\_url}"> <a href="{$facebook\_page\_url}">{$facebook\_page\_url}</a> </blockquote> </div></div>
        ```

        (Note : La version réelle du SDK et les attributs de données peuvent varier légèrement en fonction de l'implémentation exacte du module et des changements d'API de Facebook.)
-   **`likebox/rightcolumn.tpl`**

    *   **Portée :** Front-office
    *   **Hook :** `displayRightColumn`, `displayLeftColumn`, `displayFooter`, `displayProductButtons`, etc. (selon la configuration du module)
    *   **Objectif :** Ce template sert d'enveloppe pour la Facebook Like Box. Il est conçu pour être flexible et peut être accroché à diverses positions. Il inclut généralement l'élément `div` avec la classe `fb-page` que le SDK de Facebook transformera en Like Box visuelle.
    *   **Sortie :**

        ```
        <div class="block facebook\_like\_box\_container"> <h4>{l s='Follow us on Facebook' mod='likebox'}</h4> <div class="block\_content"> <div class="fb-page" data-href="{$facebook\_page\_url}" data-width="{$width}" data-height="{$height}" data-small-header="{$small\_header}" data-adapt-container-width="{$adapt\_container\_width}" data-hide-cover="{$hide\_cover}" data-show-facepile="{$show\_faces}" data-show-posts="{$show\_stream}" data-colorscheme="{$colorscheme}" data-header="{$show\_header}"> <div class="fb-xfbml-parse-ignore"> <blockquote cite="{$facebook\_page\_url}"> <a href="{$facebook\_page\_url}">{$facebook\_page\_url}</a> </blockquote> </div> </div> </div></div>
        ```

        Ce template inclut également le titre `<h4>` et la structure `block_content` courants pour les blocs de colonne de PrestaShop.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    *   Ce module ne crée pas de tables SQL personnalisées.
    *   Les paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide de clés généralement préfixées par `LIKEBOX_` (par exemple, `LIKEBOX_FACEBOOK_PAGE_URL`, `LIKEBOX_WIDTH`, `LIKEBOX_HEIGHT`, `LIKEBOX_APP_ID`, etc.).
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rendu dans la section `<head>` de chaque page. | Utilisé pour inclure le SDK JavaScript de Facebook et le div `fb-root` initial, essentiels au fonctionnement de la Like Box. |
| `displayLeftColumn` | Rend le contenu dans la colonne latérale gauche. | Affiche le widget Facebook Like Box dans la colonne gauche. |
| `displayRightColumn` | Rend le contenu dans la colonne latérale droite. | Affiche le widget Facebook Like Box dans la colonne droite. |
| `displayFooter` | Rend le contenu dans la section du pied de page de la boutique. | Affiche le widget Facebook Like Box dans le pied de page. |
| `displayHome` | Rend le contenu sur la page d'accueil. | Affiche le widget Facebook Like Box sur la page d'accueil. |
| `displayProductButtons` | Rend le contenu près des boutons d'action du produit sur la page produit. | Affiche le widget Facebook Like Box sur les pages produit. |
| `displayProductExtraContent` | Rend du contenu supplémentaire sur la page produit, souvent dans un onglet ou sous le contenu principal. | Affiche le widget Facebook Like Box sur les pages produit. |
| `displayMyAccountBlock` | Rend le contenu dans le bloc "Mon compte" du client. | Affiche le widget Facebook Like Box dans la zone du compte client (moins courant pour ce module). |
| `displayMyAccountBlockfooter` | Rend le contenu dans le pied de page du bloc "Mon compte". | Affiche le widget Facebook Like Box dans la zone du compte client. |

(Note : La méthode `install()` du module enregistre ces hooks, et les méthodes `hook<NomDuHook>()` dans `ar.php` sont responsables du rendu de `rightcolumn.tpl` ou `header.tpl` en fonction du hook.)

## 5. Support officiel et mises à jour

Pour les dernières versions, mises à jour et un support dédié pour le module Facebook Like Box, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question que vous pourriez avoir.
