---
title: "Free My AI Act - Conformité à la loi sur l'intelligence artificielle - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Free My AI Act - Conformité à la loi sur l'intelligence artificielle par MyPresta.eu."
sidebar:
  label: "Free My AI Act - Conformité à la loi sur l'intelligence artificielle"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Free My AI Act - Artificial Intelligence Act compliance sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-my-ai-act-artificial-intelligence-act-compliance.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/free-my-ai-act-artificial-intelligence-act-compliance/)
>
> ---


# Free My AI Act - Conformité à la loi sur l'intelligence artificielle

## 1. Exigences et compatibilité
-   **Versions PrestaShop prises en charge** : PrestaShop 9.x
-   **Compatibilité PHP** : PHP 7.4 - 8.5
-   **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour une installation PrestaShop et sont suffisantes pour ce module.

## 2. Présentation complète de la configuration (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Pour accéder à la configuration du module, naviguez vers **Modules > Gestionnaire de modules**, recherchez "Free My AI Act" et cliquez sur le bouton "Configurer".

Cet écran fournit tous les paramètres essentiels pour contrôler la manière dont le contenu IA est divulgué sur votre boutique.

#### **Paramètres généraux**

-   **Activer la conformité à l'AI Act :**
    -   **Ce que fait ce paramètre :** Il s'agit de l'interrupteur principal pour activer ou désactiver les fonctionnalités du module dans votre boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Toutes les fonctionnalités de divulgation IA configurées (badges, bannières, avis) deviendront actives sur votre front office.
        -   *Lorsqu'il est désactivé :* Toutes les fonctionnalités de divulgation IA seront masquées et le module n'affichera aucune information liée à l'IA aux clients.
    -   **Valeur recommandée :** OUI
    -   **Scénario/exemple de marchand :** Vous avez terminé votre configuration et êtes prêt à mettre en ligne la conformité à l'AI Act. Activez ce paramètre. Si vous devez désactiver temporairement toutes les divulgations pour la maintenance, passez-le à NON.

#### **Options de divulgation de contenu IA**

-   **Afficher le badge IA sur les images de produits :**
    -   **Ce que fait ce paramètre :** Contrôle si un petit badge (par exemple, "Généré par l'IA" ou une icône) apparaît directement sur les images de produits dans les listes de catégories et sur la page du produit.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Un indicateur visuel sera superposé sur les images de produits que vous avez marquées comme générées par l'IA.
        -   *Lorsqu'il est désactivé :* Aucun badge n'apparaîtra sur les images de produits, même si elles sont marquées comme générées par l'IA.
    -   **Valeur recommandée :** OUI
    -   **Scénario/exemple de marchand :** Vous utilisez l'IA pour générer ou améliorer bon nombre de vos photos de produits. L'activation de cette option fournit une divulgation visuelle immédiate aux clients lorsqu'ils naviguent.

-   **Afficher l'avis d'informations supplémentaires sur la page produit :**
    -   **Ce que fait ce paramètre :** Détermine si un avis textuel dédié est affiché sur les pages de produits individuelles pour informer les clients du contenu généré par l'IA (texte ou images) pour ce produit spécifique.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Un bloc de texte personnalisable apparaîtra sur les pages de produits, généralement sous la description ou dans un nouvel onglet, détaillant l'utilisation de l'IA pour le contenu de ce produit.
        -   *Lorsqu'il est désactivé :* Aucun avis de divulgation IA spécifique ne sera affiché sur les pages de produits.
    -   **Valeur recommandée :** OUI
    -   **Scénario/exemple de marchand :** Vous souhaitez fournir une explication plus détaillée sur le contenu IA pour chaque produit. Cet avis vous permet d'élaborer au-delà d'un simple badge.

-   **Afficher la bannière de politique IA à l'échelle de la boutique :**
    -   **Ce que fait ce paramètre :** Active une bannière qui apparaît de manière cohérente sur l'ensemble de votre boutique (par exemple, en haut ou en bas de chaque page) pour informer les visiteurs de votre politique générale de contenu IA.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Une bannière personnalisable sera visible sur toutes les pages, souvent avec un lien vers une page de politique IA plus complète.
        -   *Lorsqu'il est désactivé :* Aucune bannière à l'échelle de la boutique ne sera affichée.
    -   **Valeur recommandée :** OUI
    -   **Scénario/exemple de marchand :** Vous souhaitez faire une déclaration générale sur l'utilisation de l'IA par votre boutique et diriger les clients vers une page de politique dédiée pour une transparence totale.

-   **Lien vers la page de politique IA (URL) :**
    -   **Ce que fait ce paramètre :** Vous permet de spécifier l'URL d'une page CMS ou d'un lien externe où les clients peuvent trouver votre politique détaillée en matière de contenu IA. Ce lien sera généralement inclus dans la bannière à l'échelle de la boutique ou dans les avis d'informations supplémentaires.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'une URL est saisie :* La bannière et les avis incluront un lien cliquable vers cette page.
        -   *Lorsqu'il est laissé vide :* Aucun lien ne sera fourni, ou la bannière/l'avis pourrait ne pas apparaître s'il dépend de ce lien.
    -   **Valeur recommandée :** `[L'URL de votre page CMS, par exemple, /content/10-ai-policy]`
    -   **Scénario/exemple de marchand :** Vous avez créé une page CMS dédiée expliquant votre utilisation de l'IA, vos pratiques en matière de données et votre engagement en faveur de la transparence. Saisissez son URL ici afin que les clients puissent y accéder facilement.

#### **Personnalisation du contenu**

-   **Texte du badge IA (par exemple, "IA") :**
    -   **Ce que fait ce paramètre :** Définit le texte court qui apparaît sur le badge IA superposé sur les images de produits.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est modifié :* Le texte sur le badge sera mis à jour en conséquence.
    -   **Valeur recommandée :** IA
    -   **Scénario/exemple de marchand :** Vous préférez une étiquette plus courte comme "IA" au lieu de "Généré par l'IA" pour garder le badge concis.

-   **Couleur du badge IA :**
    -   **Ce que fait ce paramètre :** Définit la couleur de fond du badge IA.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est modifié :* La couleur de fond du badge sera mise à jour, vous permettant de l'adapter à l'image de marque de votre boutique.
    -   **Valeur recommandée :** #FF0000 (Rouge) ou une couleur qui contraste bien avec les images de vos produits.
    -   **Scénario/exemple de marchand :** Votre marque utilise une palette de couleurs spécifique. Vous pouvez définir la couleur du badge sur une teinte contrastante qui reste visuellement attrayante.

-   **Couleur du texte du badge IA :**
    -   **Ce que fait ce paramètre :** Définit la couleur du texte à l'intérieur du badge IA.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est modifié :* La couleur du texte sur le badge sera mise à jour.
    -   **Valeur recommandée :** #FFFFFF (Blanc) ou une couleur qui contraste bien avec la couleur de fond du badge choisie.
    -   **Scénario/exemple de marchand :** Si le fond de votre badge est sombre, vous voudrez un texte blanc ou de couleur claire pour une meilleure lisibilité.

-   **Texte de l'avis d'informations supplémentaires :**
    -   **Ce que fait ce paramètre :** Vous permet de personnaliser le texte complet affiché dans l'"Avis d'informations supplémentaires" sur les pages de produits.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est modifié :* Le contenu de l'avis sur les pages de produits reflétera votre texte personnalisé.
    -   **Valeur recommandée :** "Veuillez noter : Certaines parties de cette description de produit et/ou des images peuvent avoir été générées ou améliorées à l'aide de l'Intelligence Artificielle pour vous fournir des informations complètes."
    -   **Scénario/exemple de marchand :** Vous souhaitez indiquer clairement que le texte et les images peuvent être générés par l'IA et expliquer pourquoi (par exemple, pour des informations complètes).

-   **Texte de la bannière à l'échelle de la boutique :**
    -   **Ce que fait ce paramètre :** Personnalise le message affiché dans la bannière de politique IA à l'échelle de la boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est modifié :* Le texte de la bannière sur toutes les pages sera mis à jour.
    -   **Valeur recommandée :** "Notre boutique utilise l'IA pour améliorer le contenu. En savoir plus sur notre politique IA."
    -   **Scénario/exemple de marchand :** Vous souhaitez un message concis dans la bannière qui encourage les clients à cliquer sur le lien pour plus de détails.

#### **Signalement IA spécifique au produit**

Ce module s'intègre également directement à votre page d'édition de produit. Lorsque vous modifiez un produit dans le Back Office (**Catalogue > Produits > Modifier le produit**), vous trouverez un nouvel onglet ou une nouvelle section liée à la "Conformité à l'AI Act".

-   **Marquer le contenu du produit comme généré par l'IA :**
    -   **Ce que fait ce paramètre :** Une case à cocher ou un interrupteur sur la page d'édition du produit qui vous permet de marquer individuellement le contenu textuel d'un produit spécifique (description, courte description, caractéristiques) comme généré par l'IA.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé pour un produit :* L'"Avis d'informations supplémentaires" (si activé dans la configuration du module) apparaîtra sur la page de ce produit, et toute autre divulgation IA basée sur le texte s'activera.
        -   *Lorsqu'il est désactivé pour un produit :* Aucune divulgation IA basée sur le texte n'apparaîtra pour ce produit spécifique.
    -   **Valeur recommandée :** Activer pour tout produit où l'IA a été utilisée pour le texte.
    -   **Scénario/exemple de marchand :** Vous avez utilisé un assistant d'écriture IA pour créer la description longue d'un nouveau produit. Vous activeriez ce paramètre pour ce produit spécifique.

-   **Marquer les images de produits comme générées par l'IA :**
    -   **Ce que fait ce paramètre :** Une case à cocher ou un interrupteur sur la page d'édition du produit qui vous permet de marquer individuellement les images d'un produit spécifique comme générées ou améliorées par l'IA.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé pour un produit :* Le "Badge IA" (si activé dans la configuration du module) apparaîtra sur les images de ce produit, et l'"Avis d'informations supplémentaires" s'activera également.
        -   *Lorsqu'il est désactivé pour un produit :* Aucun badge IA n'apparaîtra sur les images de ce produit spécifique.
    -   **Valeur recommandée :** Activer pour tout produit où l'IA a été utilisée pour les images.
    -   **Scénario/exemple de marchand :** Vous avez utilisé un générateur ou un améliorateur d'images IA pour l'image principale du produit. Vous activeriez ce paramètre pour ce produit spécifique.

#### 2.1.1 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
|---|---|---|---|
| Configuration du module | Activer la conformité à l'AI Act | OUI | Interrupteur principal pour toutes les fonctionnalités du module. |
| Configuration du module | Afficher le badge IA sur les images de produits | OUI | Affiche le badge "IA" sur les images de produits signalées par l'IA. |
| Configuration du module | Afficher l'avis d'informations supplémentaires sur la page produit | OUI | Affiche un avis textuel sur les pages de produits signalées par l'IA. |
| Configuration du module | Afficher la bannière de politique IA à l'échelle de la boutique | OUI | Affiche une bannière sur toutes les pages pour la politique générale. |
| Configuration du module | Lien vers la page de politique IA (URL) | `/content/10-ai-policy` | URL de votre page de politique IA détaillée. |
| Configuration du module | Texte du badge IA | IA | Texte affiché sur le badge de l'image du produit. |
| Configuration du module | Couleur du badge IA | `#FF0000` (Rouge) | Couleur de fond du badge IA. |
| Configuration du module | Couleur du texte du badge IA | `#FFFFFF` (Blanc) | Couleur du texte du badge IA. |
| Configuration du module | Texte de l'avis d'informations supplémentaires | Personnalisable | Texte complet pour l'avis de la page produit. |
| Configuration du module | Texte de la bannière à l'échelle de la boutique | Personnalisable | Texte complet pour la bannière à l'échelle de la boutique. |
| Page d'édition du produit | Marquer le contenu du produit comme généré par l'IA | N/A (par produit) | Signale le contenu textuel du produit comme généré par l'IA. |
| Page d'édition du produit | Marquer les images de produits comme générées par l'IA | N/A (par produit) | Signale les images de produits comme générées par l'IA. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q1 : J'ai activé le module et configuré les paramètres, mais je ne vois aucun badge ou bannière IA sur ma boutique.**
**R1 :**
1.  **Vérifiez "Activer la conformité à l'AI Act" :** Assurez-vous que l'interrupteur principal dans la configuration du module est réglé sur OUI.
2.  **Videz le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les anciennes versions). Le cache de votre navigateur pourrait également avoir besoin d'être vidé (Ctrl+F5 ou Cmd+R).
3.  **Vérifiez les paramètres de produits individuels :** Pour les badges et les avis de page produit, assurez-vous d'avoir marqué individuellement les produits spécifiques comme ayant du contenu/des images générés par l'IA sur leurs pages d'édition de produit respectives.
4.  **Compatibilité du thème :** Bien que le module soit conçu pour PrestaShop 9.x, les thèmes personnalisés peuvent parfois interférer. Si les problèmes persistent, passez temporairement au thème PrestaShop par défaut pour exclure un conflit de thème.

**Q2 : Le badge ou la bannière IA semble étrange ou est mal placé sur mon thème personnalisé.**
**R2 :** Il s'agit souvent d'un conflit CSS avec votre thème.
1.  **Inspecter l'élément :** Utilisez les outils de développement de votre navigateur (F12) pour inspecter le badge/la bannière IA. Recherchez les règles CSS conflictuelles.
2.  **CSS personnalisé :** Vous devrez peut-être ajouter du CSS personnalisé à la feuille de style de votre thème (ou via un module CSS personnalisé) pour ajuster le positionnement ou le style. Les classes CSS du module sont généralement bien définies (par exemple, `.myaiactfree-badge`, `.myaiactfree-banner`).
3.  **Contacter le support :** Si vous n'êtes pas à l'aise avec le CSS, contactez le support MyPresta.eu ou votre développeur web pour obtenir de l'aide.

**Q3 : Comment traduire le texte du badge IA, le texte de la bannière ou l'avis d'informations supplémentaires dans d'autres langues ?**
**R3 :**
1.  Allez dans **International > Traductions** dans votre Back Office PrestaShop.
2.  Sélectionnez "Traductions des modules installés" pour le "Type de traduction".
3.  Choisissez votre thème et la langue que vous souhaitez traduire.
4.  Recherchez le module "Free My AI Act" dans la liste. Vous pourrez y traduire directement les champs de texte que vous avez configurés (Texte du badge IA, Texte de l'avis d'informations supplémentaires, Texte de la bannière à l'échelle de la boutique).
5.  Enregistrez vos modifications.

**Q4 : Quelle est la différence entre ce module "Free" et "My AI Act Pro" ?**
**R4 :** Le module "Free My AI Act" offre des fonctionnalités de divulgation essentielles pour une conformité de base. "My AI Act Pro" (un module payant distinct) offre des fonctionnalités avancées telles que l'intégration AI Studio, l'accès API pour le signalement automatisé, les pistes d'audit et des capacités avancées de filigrane pour les images. La version gratuite est un excellent point de départ, et vous pouvez passer à la version Pro si vos besoins deviennent plus complexes.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique pour les développeurs et les webmasters souhaitant comprendre, étendre ou dépanner le module "Free My AI Act".

### 4.1 Aperçu de l'architecture
Le module `myaiactfree` suit une architecture de module PrestaShop standard, exploitant principalement les hooks pour l'affichage en front-office et `getContent()` pour la configuration en back-office. Il s'intègre directement dans l'interface d'édition de produit en se connectant à `displayAdminProductsExtra` pour fournir des options de signalement IA spécifiques au produit. La configuration est stockée dans `ps_configuration`, et le rendu en front-office est réalisé via des templates Smarty et un fichier JavaScript dédié pour les interactions dynamiques.

### 4.2 Contrôleurs (`controllers/`)
Ce module ne contient aucun contrôleur front-office ou back-office dédié. Toute la logique front-office est gérée via des hooks dans le fichier principal du module, et la configuration back-office est gérée par la méthode `getContent()`.

### 4.3 Classes et modèles principaux (`classes/`)
Ce module ne définit aucune classe personnalisée ni aucune instance `ObjectModel`. Toutes les données sont gérées directement via `Configuration` pour les paramètres globaux et les propriétés `Product` pour les drapeaux spécifiques aux produits.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`myaiactfree/views/js/front.js`**
    *   **Portée :** Front-office.
    *   **Responsabilité :** Ce script est probablement responsable de tout comportement dynamique en front-office lié aux éléments de divulgation IA. Cela pourrait inclure :
        *   L'initialisation de l'affichage du badge IA sur les images de produits une fois le DOM prêt.
        *   La gestion des événements de clic sur la bannière de politique IA (si elle est masquable ou a des éléments interactifs).
        *   L'assurance d'un positionnement et d'une réactivité corrects du badge ou de la bannière IA, en particulier si les images sont chargées dynamiquement ou redimensionnées.
        *   L'ajout potentiel d'info-bulles ou de popovers lors du survol des badges IA.
        *   La liaison aux événements `prestashop.on` pour les mises à jour de contenu dynamique (par exemple, `updateProduct` sur la page produit).

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`myaiactfree/views/css/admin.css`**
    *   **Portée :** Style du formulaire d'administration du back-office.
    *   **Responsabilité :** Fournit le style pour la page de configuration du module (`configure.tpl`) et potentiellement l'onglet/la section personnalisée ajoutée à la page d'édition du produit (`product_tab.tpl`). Cela garantit une apparence cohérente et conviviale au sein du Back Office de PrestaShop.
    *   **Sélecteurs de classe CSS clés :** Cible probablement les éléments du formulaire de configuration du module, tels que des champs de saisie spécifiques, des étiquettes ou des blocs d'information.

-   **`myaiactfree/views/css/front.css`**
    *   **Portée :** Style client du front-office.
    *   **Responsabilité :** Définit l'apparence visuelle de tous les éléments de divulgation IA visibles par les clients. Cela inclut :
        *   Le style du badge IA (par exemple, `.myaiactfree-badge`, `.myaiactfree-badge-text`, `.myaiactfree-badge-icon`), y compris sa position, sa couleur de fond, la couleur du texte, le rembourrage et le rayon de la bordure.
        *   Le style de l'avis d'informations supplémentaires sur les pages de produits (par exemple, `.myaiactfree-additional-info`).
        *   Le style de la bannière de politique IA à l'échelle de la boutique (par exemple, `.myaiactfree-banner`, `.myaiactfree-banner-text`, `.myaiactfree-banner-link`).
    *   **Sélecteurs de classe CSS clés :** Les développeurs peuvent remplacer ces classes dans le CSS personnalisé de leur thème pour correspondre au design de leur marque.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :
    *   **`myaiactfree/views/templates/hook/additional_info.tpl`** :
        *   **Hook :** Probablement rendu dans `displayProductExtraContent` ou des hooks similaires de page produit.
        *   **Sortie :** Affiche le texte personnalisable de l'"Avis d'informations supplémentaires" sur la page produit lorsqu'un produit est signalé comme généré par l'IA.
    *   **`myaiactfree/views/templates/hook/ai_badge.tpl`** :
        *   **Hook :** Probablement rendu dans `displayProductListReviews` (pour les listes de produits) ou `displayProductAdditionalInfo` (pour l'image de la page produit).
        *   **Sortie :** Génère la structure HTML du badge IA qui se superpose aux images de produits, y compris le texte et le style personnalisables.
    *   **`myaiactfree/views/templates/hook/banner.tpl`** :
        *   **Hook :** Probablement rendu dans `displayHeader`, `displayTop`, `displayWrapperTop` ou `displayFooter`.
        *   **Sortie :** Rend la bannière de politique IA à l'échelle de la boutique, y compris le texte personnalisable et un lien vers la page de politique IA.

-   **Templates d'administration (`views/templates/admin/`)** :
    *   **`myaiactfree/views/templates/admin/configure.tpl`** :
        *   **Objectif :** Il s'agit du template principal pour la page de configuration du module accessible via `getContent()`. Il rend tous les paramètres globaux (activer/désactiver, texte du badge, texte de la bannière, etc.) comme décrit dans la section 4.1.
    *   **`myaiactfree/views/templates/admin/configure_intro.tpl`** :
        *   **Objectif :** Affiche probablement un message d'introduction ou une explication en haut de la page de configuration du module, expliquant peut-être l'AI Act ou l'objectif du module.
    *   **`myaiactfree/views/templates/admin/product_tab.tpl`** :
        *   **Hook :** Rendu via `displayAdminProductsExtra`.
        *   **Objectif :** Ce template fournit l'interface dans la page d'édition du produit (Back Office > Catalogue > Produits > Modifier le produit) où les marchands peuvent marquer individuellement le contenu et les images d'un produit comme générés par l'IA. Il contient les cases à cocher ou les interrupteurs pour les drapeaux IA spécifiques au produit.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** :
    *   Ce module ne crée pas de tables SQL personnalisées.
    *   Les paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide de clés généralement préfixées par `MYAIACTFREE_`. Exemples :
        *   `MYAIACTFREE_ENABLED`
        *   `MYAIACTFREE_SHOW_BADGE`
        *   `MYAIACTFREE_BADGE_TEXT`
        *   `MYAIACTFREE_BADGE_COLOR`
        *   `MYAIACTFREE_BADGE_TEXT_COLOR`
        *   `MYAIACTFREE_SHOW_ADDITIONAL_INFO`
        *   `MYAIACTFREE_ADDITIONAL_INFO_TEXT`
        *   `MYAIACTFREE_SHOW_BANNER`
        *   `MYAIACTFREE_BANNER_TEXT`
        *   `MYAIACTFREE_POLICY_URL`
    *   Les drapeaux IA spécifiques aux produits (pour le contenu et les images) sont probablement stockés en tant que propriétés d'objet `Product` ou dans un champ personnalisé associé à l'entité `Product`, éventuellement via `Configuration::updateValue` avec un suffixe d'ID de produit ou en modifiant directement les données de l'objet `Product`.

-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
|---|---|---|
| `displayHeader` | Dans la section `<head>` de chaque page. | Injecter les actifs CSS/JS (`front.css`, `front.js`) et potentiellement la bannière à l'échelle de la boutique (`banner.tpl`). |
| `displayTop` / `displayWrapperTop` | Souvent tout en haut du contenu de la page. | Hook alternatif pour la bannière à l'échelle de la boutique (`banner.tpl`). |
| `displayFooter` | En bas de chaque page. | Hook alternatif pour la bannière à l'échelle de la boutique (`banner.tpl`). |
| `displayProductListReviews` | Sur les pages de liste de produits, près des images de produits. | Rendre le badge IA (`ai_badge.tpl`) sur les miniatures de produits. |
| `displayProductAdditionalInfo` | Sur la page produit, près du bloc image/prix du produit. | Rendre le badge IA (`ai_badge.tpl`) sur l'image principale du produit. |
| `displayProductExtraContent` | Sur la page produit, généralement sous la description ou dans un nouvel onglet. | Rendre l'avis d'informations supplémentaires (`additional_info.tpl`). |
| `displayAdminProductsExtra` | Sur la page d'édition du produit dans le Back Office. | Injecter l'onglet/la section personnalisée pour le signalement IA spécifique au produit (`product_tab.tpl`). |
| `actionProductUpdate` | Après la mise à jour d'un produit dans le Back Office. | Enregistrer les drapeaux IA spécifiques au produit (contenu/image) dans la base de données. |
| `actionProductAdd` | Après l'ajout d'un nouveau produit dans le Back Office. | Initialiser les drapeaux IA spécifiques aux nouveaux produits. |

## 5. Support officiel et mises à jour
Pour les mises à jour officielles, le support technique et pour accéder aux dernières versions du module "Free My AI Act - Conformité à la loi sur l'intelligence artificielle", veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité ou la compatibilité du module.
