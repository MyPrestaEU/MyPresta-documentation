---
title: "Zoom sur les attributs de couleur / texture - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Zoom sur les attributs de couleur / texture par MyPresta.eu."
sidebar:
  label: "Zoom sur les attributs de couleur / texture - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Color / texture attribute zoom sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/color-texture-attribute-zoom.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/color-texture-attribute-zoom/)
>
> ---


# Zoom sur les attributs de couleur / texture

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises par PrestaShop lui-même et sont suffisantes pour ce module.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module « Zoom sur les attributs de couleur / texture », accessible après l'installation en cliquant sur le bouton « Configurer ».

#### **Activer / Désactiver le module**

-   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité du module dans toute votre boutique.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé :* La fonction de zoom couleur/texture sera active sur vos pages produits et vos pop-ups de vue rapide, selon les autres paramètres que vous avez choisis.
    -   *Lorsqu'il est désactivé :* La fonction de zoom sera complètement désactivée, et aucun aperçu agrandi n'apparaîtra.
-   **Valeur recommandée :** **Activé** (pour utiliser les fonctionnalités du module).
-   **Scénario / exemple de marchand :** Si vous souhaitez désactiver temporairement la fonction de zoom pour la maintenance ou les tests, vous pouvez la désactiver sans désinstaller le module.

#### **Afficher le nom (valeur) de la couleur / texture**

-   **Ce que fait ce paramètre :** Détermine si le nom textuel de la couleur ou de la texture (par exemple, « Rouge », « Cuir ») apparaît à côté de la fenêtre d'aperçu zoomée.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé :* Le nom de l'attribut sera affiché à côté de l'image zoomée, fournissant un contexte supplémentaire au client.
    -   *Lorsqu'il est désactivé :* Seule l'image zoomée apparaîtra, sans l'étiquette de texte.
-   **Valeur recommandée :** **Activé**. Cela fournit des informations plus claires au client, surtout si les couleurs sont similaires ou si les textures sont subtiles.
-   **Scénario / exemple de marchand :** Si vous avez de nombreuses nuances de bleu (par exemple, « Bleu Ciel », « Bleu Marine »), afficher le nom aide les clients à les différencier clairement.

#### **Désactiver le changement d'attribut au toucher**

-   **Ce que fait ce paramètre :** Contrôle le comportement du module sur les appareils tactiles (comme les smartphones et les tablettes) lorsqu'un client touche un échantillon de couleur/texture.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé :* Taper sur un échantillon de couleur/texture affichera uniquement l'aperçu du zoom. L'image principale du produit sur la page NE changera PAS pour refléter l'attribut touché.
    -   *Lorsqu'il est désactivé :* Taper sur un échantillon de couleur/texture affichera l'aperçu du zoom ET mettra également à jour l'image principale du produit pour afficher le produit dans la couleur/texture sélectionnée.
-   **Valeur recommandée :** **Désactivé**. La plupart des clients s'attendent à ce que l'image principale du produit se mette à jour lorsqu'ils sélectionnent une couleur/texture, même sur mobile. Activez ceci uniquement si vous avez une raison spécifique de ne pas changer l'image principale au toucher.
-   **Scénario / exemple de marchand :** Si vos images de produits sont génériques et ne changent pas en fonction des attributs de couleur, ou si vous souhaitez éviter les changements accidentels d'image principale sur mobile, vous pouvez activer ceci. Sinon, gardez-le désactivé pour un comportement standard.

#### **Largeur de la fenêtre d'aperçu des couleurs**

-   **Ce que fait ce paramètre :** Définit la largeur (en pixels) de la fenêtre contextuelle qui affiche l'aperçu de la couleur zoomée.
-   **Effet de la modification de ce paramètre :**
    -   *Augmenter la valeur :* Rend la fenêtre d'aperçu plus large, affichant plus de détails.
    -   *Diminuer la valeur :* Rend la fenêtre d'aperçu plus étroite.
-   **Valeur recommandée :** Une valeur entre **200px et 300px** est généralement un bon équilibre. Commencez par `280` et ajustez en fonction de vos images de produits et de la conception de votre thème.
-   **Scénario / exemple de marchand :** Si vos échantillons de couleur sont très petits et que vous souhaitez afficher un agrandissement significatif, augmentez cette valeur. Si la mise en page de votre page produit est très étroite, vous devrez peut-être la réduire.

#### **Hauteur de la fenêtre d'aperçu des couleurs**

-   **Ce que fait ce paramètre :** Définit la hauteur (en pixels) de la fenêtre contextuelle qui affiche l'aperçu de la couleur zoomée.
-   **Effet de la modification de ce paramètre :**
    -   *Augmenter la valeur :* Rend la fenêtre d'aperçu plus haute, affichant plus de détails.
    -   *Diminuer la valeur :* Rend la fenêtre d'aperçu plus courte.
-   **Valeur recommandée :** Une valeur entre **200px et 300px** est généralement un bon équilibre. Commencez par `280` et ajustez en fonction de vos images de produits et de la conception de votre thème.
-   **Scénario / exemple de marchand :** Similaire à la largeur, ajustez ceci pour vous assurer que la couleur zoomée est clairement visible sans être excessivement grande ou petite pour votre page produit.

#### **Activer le zoom dans le tableau des combinaisons**

-   **Ce que fait ce paramètre :** Détermine si la fonction de zoom doit également s'appliquer aux attributs de couleur/texture affichés dans un tableau de combinaisons de produits (si votre thème en utilise un).
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé :* Les clients peuvent survoler/taper sur les échantillons de couleur/texture dans un tableau de combinaisons pour voir l'aperçu zoomé.
    -   *Lorsqu'il est désactivé :* La fonction de zoom ne fonctionnera que pour les attributs de couleur/texture en dehors de tout tableau de combinaisons.
-   **Valeur recommandée :** **Activé**. Cela offre une expérience cohérente et utile dans toutes les zones où les attributs de couleur/texture sont affichés.
-   **Scénario / exemple de marchand :** Si vous vendez des t-shirts avec un tableau affichant les tailles et les couleurs disponibles, l'activation de cette option permet aux clients de zoomer sur les couleurs directement à partir de ce tableau.

#### **Largeur de la fenêtre d'aperçu des textures**

-   **Ce que fait ce paramètre :** Définit la largeur (en pixels) de la fenêtre contextuelle qui affiche l'aperçu de la texture zoomée. Ceci est distinct de la largeur de l'aperçu des couleurs, vous permettant d'optimiser pour différents types d'images d'attributs.
-   **Effet de la modification de ce paramètre :**
    -   *Augmenter la valeur :* Rend l'aperçu de la texture plus large.
    -   *Diminuer la valeur :* Rend l'aperçu de la texture plus étroit.
-   **Valeur recommandée :** Similaire à la couleur, une valeur entre **200px et 300px** est souvent appropriée. Commencez par `280`.
-   **Scénario / exemple de marchand :** Si vos images de texture sont très détaillées et nécessitent une vue plus grande pour être appréciées, vous pouvez définir une largeur plus élevée ici que pour de simples échantillons de couleur.

#### **Exclure certains groupes d'attributs de couleur du ZOOM**

-   **Ce que fait ce paramètre :** Vous permet de spécifier certains groupes d'attributs (par exemple, « Taille », « Matériau ») pour lesquels la fonction de zoom NE doit PAS être appliquée, même s'ils utilisent des images de couleur ou de texture.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsque les ID de groupe d'attributs sont saisis :* La fonction de zoom sera désactivée pour tous les attributs appartenant aux groupes spécifiés.
    -   *Lorsqu'il est laissé vide :* La fonction de zoom s'appliquera à tous les groupes d'attributs de couleur/texture.
-   **Valeur recommandée :** Laissez **vide** sauf si vous avez une raison spécifique d'exclure des groupes. Si vous devez exclure, entrez les ID numériques des groupes d'attributs, séparés par des virgules (par exemple, `1, 5, 12`). Vous pouvez trouver les ID de groupe d'attributs dans votre Back Office PrestaShop sous **Catalogue > Attributs & Caractéristiques > Groupes d'attributs**.
-   **Scénario / exemple de marchand :** Vous pourriez avoir un groupe d'attributs « Disponibilité » qui utilise des échantillons de couleur (par exemple, vert pour en stock, rouge pour en rupture de stock), mais vous ne voulez pas que ceux-ci déclenchent un zoom. Dans ce cas, vous trouveriez l'ID du groupe d'attributs « Disponibilité » et le saisiriez ici.

#### **Type d'animation**

-   **Ce que fait ce paramètre :** Sélectionne l'effet visuel utilisé lorsque la fenêtre d'aperçu du zoom apparaît.
-   **Effet de la modification de ce paramètre :** Change la façon dont la fenêtre d'aperçu s'anime (par exemple, fondu, glissement).
-   **Valeur recommandée :** **Fondu**. C'est généralement l'animation la plus subtile et la plus professionnelle. Expérimentez avec d'autres si vous préférez un effet différent.
-   **Scénario / exemple de marchand :** Vous pouvez choisir une animation qui correspond le mieux à l'esthétique générale de votre boutique.

#### **Mettre à jour le type d'animation**

-   **Ce que fait ce paramètre :** Sélectionne l'effet visuel utilisé lorsque le contenu de la fenêtre d'aperçu du zoom change (par exemple, lors du passage entre différentes couleurs/textures alors que l'aperçu est déjà ouvert).
-   **Effet de la modification de ce paramètre :** Change l'animation pour les mises à jour de contenu dans l'aperçu.
-   **Valeur recommandée :** **Fondu**. Similaire à l'animation initiale, un fondu est généralement fluide et non distrayant.
-   **Scénario / exemple de marchand :** Si un client survole rapidement plusieurs échantillons de couleur, cette animation dicte la fluidité de la transition du contenu de l'aperçu.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer / Désactiver le module | Activé | Interrupteur principal pour la fonctionnalité du module. |
| Configuration du module | Afficher le nom (valeur) de la couleur / texture | Activé | Affiche le nom de l'attribut avec l'aperçu du zoom. |
| Configuration du module | Désactiver le changement d'attribut au toucher | Désactivé | Empêche le changement d'image principale au toucher sur mobile (si activé). |
| Configuration du module | Largeur de la fenêtre d'aperçu des couleurs | 280 | Largeur de la fenêtre contextuelle de zoom des couleurs en pixels. |
| Configuration du module | Hauteur de la fenêtre d'aperçu des couleurs | 280 | Hauteur de la fenêtre contextuelle de zoom des couleurs en pixels. |
| Configuration du module | Activer le zoom dans le tableau des combinaisons | Activé | Étend le zoom aux attributs dans les tableaux de combinaisons. |
| Configuration du module | Largeur de la fenêtre d'aperçu des textures | 280 | Largeur de la fenêtre contextuelle de zoom des textures en pixels. |
| Configuration du module | Exclure certains groupes d'attributs de couleur du ZOOM | Vide | ID séparés par des virgules des groupes d'attributs à ignorer pour le zoom. |
| Configuration du module | Type d'animation | Fondu | Animation pour l'apparition de l'aperçu du zoom. |
| Configuration du module | Mettre à jour le type d'animation | Fondu | Animation pour les changements de contenu dans l'aperçu du zoom. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : Le zoom n'apparaît pas sur ma page produit. Que dois-je vérifier ?**
R :

1.  **Module activé :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que « Zoom sur les attributs de couleur / texture » est activé.
2.  **Configuration des attributs :** Vérifiez que vos attributs de produit sont correctement configurés comme type « Couleur » ou « Texture » dans **Catalogue > Attributs & Caractéristiques > Attributs**. Assurez-vous d'avoir téléchargé des images réelles pour ces attributs, pas seulement des codes de couleur.
3.  **Cache :** Videz votre cache PrestaShop. Allez dans **Paramètres avancés > Performances**, faites défiler jusqu'à « Vider le cache » et cliquez sur « Vider le cache ». Videz également le cache de votre navigateur.
4.  **Compatibilité du thème :** Bien que le module soit conçu pour une large compatibilité, des thèmes très fortement personnalisés peuvent parfois interférer. Si les étapes ci-dessus ne fonctionnent pas, passez temporairement au thème PrestaShop par défaut pour voir si le zoom apparaît. Si c'est le cas, votre thème pourrait nécessiter un petit ajustement.

**Q : La fenêtre d'aperçu du zoom est trop petite/grande.**
R : Ajustez les paramètres « Largeur de la fenêtre d'aperçu des couleurs », « Hauteur de la fenêtre d'aperçu des couleurs » et « Largeur de la fenêtre d'aperçu des textures » dans la page de configuration du module. Augmentez les valeurs pour agrandir la fenêtre, diminuez-les pour la réduire. N'oubliez pas d'enregistrer les modifications et de vider le cache.

**Q : Le nom de la couleur/texture n'apparaît pas avec le zoom.**
R : Vérifiez le paramètre « Afficher le nom (valeur) de la couleur / texture » dans la configuration du module. Assurez-vous qu'il est défini sur « Activé ».

**Q : Sur mobile, lorsque je touche une couleur, l'image principale du produit ne change pas, mais je veux qu'elle change.**
R : Allez dans la configuration du module et assurez-vous que « Désactiver le changement d'attribut au toucher » est défini sur « Désactivé ». Cela permettra à l'image principale du produit de se mettre à jour lorsqu'une couleur/texture est touchée.

**Q : Je souhaite exclure un groupe d'attributs spécifique de la fonction de zoom.**
R : Naviguez vers **Catalogue > Attributs & Caractéristiques > Groupes d'attributs** dans votre Back Office PrestaShop. Trouvez le groupe d'attributs que vous souhaitez exclure et notez son ID (généralement visible dans l'URL lorsque vous le modifiez, ou dans le tableau lui-même). Ensuite, allez dans la configuration du module, trouvez « Exclure certains groupes d'attributs de couleur du ZOOM », et entrez le(s) ID(s) séparé(s) par des virgules (par exemple, `1,5,12`).

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Zoom sur les attributs de couleur / texture » (`colorzoom`) est un module de fonctionnalité front-office conçu pour améliorer la visualisation des attributs de produit. Il exploite principalement le système de hooks de PrestaShop pour injecter ses ressources JavaScript et CSS dans l'en-tête du front-office et pour rendre son modèle de zoom spécifique sur les pages produits. Il utilise la bibliothèque `tooltipster` pour la fonctionnalité de zoom/tooltip réelle, l'attachant dynamiquement aux éléments d'attributs de couleur et de texture. La configuration est gérée via la méthode standard `getContent()` dans le fichier principal du module, stockant les paramètres dans `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

Le module comprend deux contrôleurs front-office, bien que leur fonction principale dans ce module soit souvent minimale ou pour des besoins AJAX spécifiques, une grande partie de la logique étant gérée côté client via JavaScript.

-   **Contrôleurs Front-Office** :

    -   `controllers/front/index.php`
        -   Nom de la classe : `ColorzoomIndexModuleFrontController` (étend `ModuleFrontController`)
        -   Responsabilité : Ce contrôleur sert probablement de solution de repli ou de point d'entrée générique. Étant donné que la fonction principale du module est l'amélioration de l'interface utilisateur via JS/CSS, ce contrôleur pourrait ne pas avoir une logique étendue ou pourrait être utilisé pour une simple récupération de données si nécessaire par le front-end.
    -   `controllers/front/loader.php`
        -   Nom de la classe : `ColorzoomLoaderModuleFrontController` (étend `ModuleFrontController`)
        -   Responsabilité : Ce contrôleur pourrait être utilisé pour charger des ressources ou des données spécifiques dynamiquement, potentiellement pour des requêtes AJAX liées à la fonctionnalité de zoom, bien que la logique de zoom principale soit côté client.
-   **Contrôleurs d'administration Back-Office** : Aucun. Toute la configuration est gérée via la méthode `getContent()` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne définit aucune classe `ObjectModel` personnalisée ni de classes de logique métier dédiées dans le répertoire `classes/`. Sa fonctionnalité principale est implémentée dans le fichier `colorzoom.php` et via ses ressources JavaScript.

### 4.4 Ressources JavaScript (`views/js/`)

Le module repose fortement sur JavaScript pour sa fonctionnalité de zoom interactive, en particulier la bibliothèque `tooltipster`.

-   `colorzoom/lib/tooltipster/dist/js/plugins/tooltipster/SVG/tooltipster-SVG.js`
    -   Portée : Front-office.
    -   Détails : Un plugin pour la bibliothèque `tooltipster`, spécifiquement pour la gestion des éléments SVG dans les infobulles. Cela pourrait être utilisé si les images d'attributs sont basées sur SVG ou si le module doit interagir avec des éléments SVG sur la page.
-   `colorzoom/lib/tooltipster/dist/js/tooltipster.bundle.js`
    -   Portée : Front-office.
    -   Détails : La version complète groupée de la bibliothèque `tooltipster`, fournissant la fonctionnalité principale pour créer des infobulles flexibles et personnalisables. C'est la bibliothèque principale responsable des pop-ups de zoom.
-   `colorzoom/lib/tooltipster/dist/js/tooltipster.core.js`
    -   Portée : Front-office.
    -   Détails : Le fichier JavaScript principal de la bibliothèque `tooltipster`. Il est possible que `tooltipster.bundle.js` l'inclue déjà, mais il est listé séparément, indiquant une inclusion modulaire.
-   `colorzoom/views/js/colorzoom-combinationstable.js`
    -   Portée : Front-office.
    -   Détails : Ce script cible spécifiquement les tableaux de combinaisons de produits. Il contient probablement la logique pour identifier les attributs de couleur/texture dans ces tableaux et initialiser la fonctionnalité de zoom `tooltipster` sur ceux-ci, en respectant le paramètre de configuration `cz_ctab`. Il lie les écouteurs d'événements aux éléments de ces tableaux.
-   `colorzoom/views/js/colorzoom.js`
    -   Portée : Front-office.
    -   Détails : C'est le principal JavaScript personnalisé pour le module. Il est responsable de :
        -   L'identification des éléments d'attributs de couleur/texture sur la page produit (en dehors des tableaux de combinaisons).
        -   L'initialisation de `tooltipster` sur ces éléments avec des configurations spécifiques au module (largeur, hauteur, type d'animation, affichage du nom).
        -   La gestion de la logique « Désactiver le changement d'attribut au toucher » pour les appareils mobiles.
        -   Potentiellement l'écoute des événements `prestashop.on` comme `updateProduct` pour réinitialiser les infobulles si le contenu du produit change via AJAX.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module inclut du CSS pour styliser les aperçus du zoom et la bibliothèque `tooltipster`.

-   `colorzoom/lib/tooltipster/dist/css/tooltipster.bundle.css`
    -   Portée : Style client Front-office.
    -   Détails : Le CSS groupé pour la bibliothèque `tooltipster`, fournissant un style par défaut pour les infobulles (les fenêtres d'aperçu du zoom).
-   `colorzoom/lib/tooltipster/dist/css/tooltipster.core.css`
    -   Portée : Style client Front-office.
    -   Détails : Le CSS principal de `tooltipster`, définissant les styles fondamentaux.
-   `colorzoom/views/css/colorszoom.css`
    -   Portée : Style client Front-office.
    -   Détails : CSS personnalisé spécifique au module « Zoom sur les attributs de couleur / texture ». Ce fichier contient probablement des remplacements ou des styles supplémentaires pour intégrer les infobulles `tooltipster` de manière transparente dans la page produit de PrestaShop, garantissant un positionnement correct, des tailles de police pour les noms d'attributs et la réactivité. Les développeurs peuvent inspecter ce fichier pour les sélecteurs clés à remplacer dans le CSS personnalisé de leur thème.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module utilise des modèles Smarty pour injecter son JavaScript et son CSS, et pour rendre le contenu de l'aperçu du zoom.

-   **Modèles de hook (`views/templates/hook/`)** :
    -   `colorzoom/views/header.tpl`
        -   Hook : `displayHeader`
        -   Objectif : Ce modèle est responsable de l'inclusion des fichiers CSS et JavaScript du module dans la section `<head>` des pages du front-office. Il transmet également les variables de configuration du back-office (comme `cz_width`, `cz_height`, `cz_animation`, `cz_name`, `cz_disableclick`, `cz_ctab`, `cz_exclusions`) au JavaScript du front-end, les rendant accessibles pour une initialisation dynamique.
-   **Modèles Front-office (`views/templates/front/`)** :
    -   `colorzoom/views/quickview.tpl`
        -   Objectif : Ce modèle est probablement conçu pour être rendu dans une fenêtre contextuelle de vue rapide de produit. Il contient le balisage ou la logique nécessaire pour garantir que la fonctionnalité de zoom est correctement initialisée pour les attributs affichés dans les modales de vue rapide.
    -   `colorzoom/views/zoom.tpl`
        -   Objectif : C'est le modèle principal pour le contenu affiché dans l'aperçu du zoom (infobulle). Il reçoit dynamiquement l'URL de l'image de l'attribut et le nom de l'attribut, les rendant dans la structure de l'infobulle. C'est le composant visuel que la bibliothèque `tooltipster` affichera.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    Le module ne crée aucune table SQL personnalisée. Tous ses paramètres de configuration sont stockés dans la table `ps_configuration` en utilisant des clés préfixées par `cz_` (par exemple, `cz_width`, `cz_height`, `cz_animation`, `cz_name`, `cz_disableclick`, `cz_exclusions`, `cz_ctab`) et `mypresta_updates`, `update_`, `updatev_` pour la gestion des mises à jour.
-   **Table des hooks enregistrés** :

    | Nom du hook | Moment d'exécution | Objectif technique |
    | --- | --- | --- |
    | `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Injecte les fichiers CSS et JavaScript du module, et transmet les variables de configuration au front-end. |
    | `displayProductAdditionalInfo` | Dans le bloc d'informations produit sur la page produit. | Ce hook est utilisé pour rendre l'initialisation JavaScript nécessaire ou le balisage spécifique pour la fonction de zoom sur la page produit, garantissant qu'il est actif pour les attributs de couleur/texture. |

## 5. Support officiel et mises à jour

Pour le support officiel, les mises à jour du module et toute assistance supplémentaire, veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe est dédiée à fournir un support rapide et à garantir le fonctionnement optimal de votre module.
