---
title: "Avant & après - outil de comparaison d'images - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Avant & après - outil de comparaison d'images par MyPresta.eu."
sidebar:
  label: "Avant & après - outil de comparaison d'images - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Before & after - pictures diff tool sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/before-after-pictures-diff-tool.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/before-after-pictures-diff-tool/)
>
> ---


# Avant & après - outil de comparaison d'images

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est habituellement nécessaire.

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Avant & après - outil de comparaison d'images » pour accéder à ses paramètres principaux.

#### Paramètres généraux

-   **Ce que fait ce paramètre :** Cette section contrôle l'activation globale et le mode de fonctionnement du module.
-   **Effet de la modification de ce paramètre :**
    -   *Activé :* Le module sera actif dans toute votre boutique. L'outil de comparaison d'images « Avant & Après » sera disponible sur les pages produits où vous avez configuré des images.
    -   *Désactivé :* Le module sera inactif. L'outil de comparaison d'images « Avant & Après » n'apparaîtra sur aucune page produit, même si vous avez configuré des images pour celles-ci.
    -   *Mode test :* Cette option est généralement utilisée pour les environnements de développement ou de staging. Lorsqu'elle est activée, le module peut afficher des informations de débogage supplémentaires ou fonctionner dans des conditions spécifiques qui ne conviennent pas à une boutique de production en direct. Il n'est généralement pas recommandé pour les boutiques en direct, sauf instruction explicite du support.
-   **Valeur recommandée :** « Activé » pour une boutique en direct. « Désactivé » si vous souhaitez masquer temporairement la fonctionnalité sans désinstaller le module.
-   **Scénario/exemple marchand :** Si vous lancez une nouvelle ligne de produits qui repose fortement sur des transformations visuelles (par exemple, des chaussures peintes sur mesure), vous le réglerez sur « Activé » pour présenter le travail. Si vous effectuez une maintenance ou ne souhaitez pas que la fonctionnalité soit active pendant une période, vous le réglerez sur « Désactivé ».

#### Paramètres de langue (Implicite)

Bien que non explicitement listé comme un paramètre, le module respectera les paramètres de langue par défaut de votre PrestaShop pour le Back Office.

-   **`PS_LANG_DEFAULT` :** Ce paramètre central de PrestaShop détermine la langue par défaut de votre boutique.
-   **`PS_BO_ALLOW_EMPLOYEE_FORM_LANG` :** Ce paramètre central de PrestaShop permet aux employés de choisir leur langue préférée pour les formulaires.
-   **Effet de la modification de ce paramètre :** Ces paramètres centraux de PrestaShop garantissent que tout texte ou étiquette fourni par le module dans le Back Office (par exemple, sur la page d'édition de produit pour ajouter des images avant/après) est affiché dans la langue correcte pour l'administrateur.
-   **Valeur recommandée :** Assurez-vous que votre `PS_LANG_DEFAULT` est défini sur la langue principale de votre boutique. Si vous avez une équipe multilingue, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` doit être activé.

#### Paramètres de mise à jour (Implicite)

Le module inclut également des paramètres internes liés aux mises à jour de MyPresta.eu. Ceux-ci sont généralement gérés automatiquement.

-   **`mypresta_updates`, `update_`, `updatev_` :** Ce sont des clés de configuration internes utilisées par les modules MyPresta.eu pour vérifier et gérer les mises à jour. Vous n'avez généralement pas besoin d'interagir avec celles-ci.
-   **Effet de la modification de ce paramètre :** La modification directe de ces paramètres pourrait interférer avec la capacité du module à recevoir des mises à jour importantes et des corrections de bugs.
-   **Valeur recommandée :** Laissez-les inchangés.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### Page d'édition de produit (Back Office > Catalogue > Produits > Modifier le produit)

Ce module s'intègre directement dans l'interface d'édition de produit standard de PrestaShop.

-   **Nom de l'écran et emplacement du menu :** Pour y accéder, naviguez vers **Catalogue > Produits**, puis cliquez sur « Modifier » sur n'importe quel produit.
-   **Actions et paramètres disponibles :** Dans la page d'édition de produit, vous trouverez une nouvelle section ou un nouvel onglet spécifiquement pour « Avant & après - outil de comparaison d'images ». Ici, vous pourrez :
    -   **Télécharger l'image « Avant » :** Sélectionnez et téléchargez l'image de l'état initial de votre produit.
    -   **Télécharger l'image « Après » :** Sélectionnez et téléchargez l'image de l'état final de votre produit.
    -   **Enregistrer :** Après le téléchargement, n'oubliez pas d'enregistrer le produit pour appliquer les modifications.
-   **Effet des modifications :**
    -   *Ajout d'images :* Une fois que vous avez téléchargé à la fois une image « Avant » et une image « Après » pour un produit spécifique et enregistré, le curseur de comparaison interactif apparaîtra automatiquement sur la page front-office de ce produit.
    -   *Suppression d'images :* Si vous supprimez une ou les deux images, le curseur de comparaison ne sera plus affiché pour ce produit.
    -   *Mise à jour des images :* Le remplacement des images mettra à jour le curseur sur le front office.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Lorsque vous ajoutez un nouveau produit qui bénéficie d'une comparaison avant/après, créez d'abord le produit comme d'habitude.
    2.  Naviguez vers sa page d'édition.
    3.  Localisez la section « Avant & après ».
    4.  Téléchargez vos images « avant » et « après ». Assurez-vous qu'elles ont des dimensions similaires pour le meilleur effet visuel.
    5.  Enregistrez le produit.
    6.  Vérifiez la page produit sur le front office pour confirmer que le curseur fonctionne comme prévu.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Statut du module | Activé | Active/désactive l'ensemble des fonctionnalités du module. |
| Page d'édition de produit | Télécharger l'image « Avant » | N/A | Définit l'image de l'état initial pour la comparaison. |
| Page d'édition de produit | Télécharger l'image « Après » | N/A | Définit l'image de l'état final pour la comparaison. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Le curseur « Avant & Après » n'apparaît pas sur ma page produit.**
R1 :

-   **Vérifier le statut du module :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que « Avant & après - outil de comparaison d'images » est « Activé ».
-   **Vérifier les images du produit :** Modifiez le produit spécifique (**Catalogue > Produits > Modifier**) et vérifiez qu'une image « Avant » et une image « Après » ont été téléchargées et enregistrées dans la section du module.
-   **Vider le cache :** Parfois, le cache de PrestaShop peut empêcher l'affichage de nouveau contenu. Allez dans **Paramètres avancés > Performance** et cliquez sur « Vider le cache ».
-   **Compatibilité du thème :** Bien que le module soit conçu pour être compatible, certains thèmes très personnalisés peuvent nécessiter des ajustements CSS mineurs. Si les étapes ci-dessus ne fonctionnent pas, contactez le support MyPresta.eu.

**Q2 : Les images semblent déformées ou mal alignées dans le curseur.**
R2 :

-   **Dimensions des images :** Pour de meilleurs résultats, assurez-vous que vos images « Avant » et « Après » ont exactement les mêmes dimensions (largeur et hauteur). Si elles diffèrent significativement, le curseur pourrait avoir du mal à les aligner parfaitement.
-   **Qualité des images :** Utilisez des images de haute qualité. Les images basse résolution peuvent apparaître pixélisées lorsqu'elles sont mises à l'échelle.

**Q3 : Puis-je utiliser ce module pour des produits avec plusieurs variations (combinaisons) ?**
R3 : Le module vous permet actuellement de définir une image « Avant » et une image « Après » par produit, et non par combinaison. Si vos variations ont des états avant/après différents, vous devrez peut-être créer des produits distincts ou utiliser les images principales du produit pour la comparaison.

**Q4 : Comment traduire le texte du module (le cas échéant) dans d'autres langues ?**
R4 : Toutes les étiquettes de texte introduites par le module dans le Back Office (par exemple, « Télécharger l'image Avant ») peuvent généralement être traduites via le système de traduction intégré de PrestaShop. Allez dans **International > Traductions**, sélectionnez « Traductions des modules installés », choisissez votre thème, puis recherchez le module « Avant & après - outil de comparaison d'images » pour modifier ses traductions.

**Q5 : Le curseur fonctionne, mais il ne s'intègre pas parfaitement au design de mon thème.**
R5 : Cela est souvent dû au style CSS. Votre thème peut avoir des styles conflictuels. Vous pouvez essayer d'inspecter l'élément à l'aide des outils de développement de votre navigateur pour identifier le CSS conflictuel. Pour une personnalisation plus avancée, vous pourriez avoir besoin d'un développeur web ou contacter le support MyPresta.eu pour obtenir des conseils sur la surcharge des styles par défaut du module.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Avant & après - outil de comparaison d'images » est un module PrestaShop standard suivant un modèle de type MVC. Il étend principalement la classe `Module`, s'intègre à la page d'administration des produits via des hooks, et injecte ses ressources et modèles front-office dans le pied de page du produit. Il utilise des plugins jQuery externes (`jquery.event.move.js`, `jquery.twentytwenty.js`) pour la fonctionnalité de curseur interactif.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs front-office ou back-office dédiés. Toute la logique est gérée au sein de la classe principale du module et via des hooks.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée ni `ObjectModel`. Il stocke sa configuration directement dans `ps_configuration` et les chemins d'images spécifiques aux produits en tant qu'attributs de produit ou valeurs de configuration, gérés via le hook `displayAdminProductsExtra`.

### 4.4 Ressources JavaScript (`views/js/`)

Le module inclut plusieurs fichiers JavaScript, principalement pour le curseur de comparaison d'images « TwentyTwenty ». Ceux-ci sont chargés dans le front-office.

-   **`beforeafter/js/jquery.event.move.js`**
    -   **Portée :** Front-office.
    -   **Objectif :** Un plugin jQuery léger qui fournit la gestion des événements tactiles et de souris pour le glissement d'éléments. C'est une dépendance pour `jquery.twentytwenty.js`.
    -   **Détails :** Lie des événements comme `move`, `movestart`, `moveend` pour activer la fonctionnalité de glissement.
-   **`beforeafter/js/jquery.twentytwenty.js`**
    -   **Portée :** Front-office.
    -   **Objectif :** Le plugin jQuery principal qui implémente le curseur de comparaison d'images « TwentyTwenty ».
    -   **Détails :** Initialise le curseur sur les éléments spécifiés, gère le rendu visuel des images avant/après et gère le diviseur interactif basé sur `jquery.event.move.js`. Il cible généralement un conteneur avec deux balises `img` à l'intérieur.
-   **`beforeafter/js/twentytwenty.js`**
    -   **Portée :** Front-office.
    -   **Objectif :** Ce fichier contient probablement la logique d'initialisation spécifique du module pour le plugin `jquery.twentytwenty.js`, l'appliquant aux éléments corrects sur la page produit.
    -   **Détails :** Il contiendra des sélecteurs jQuery pour identifier l'élément `div` enveloppant les images avant/après et appellera la méthode `.twentytwenty()` dessus, potentiellement avec des options de configuration.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module inclut des fichiers CSS pour styliser le curseur de comparaison d'images et ses composants.

-   **`beforeafter/css/foundation.css`**
    -   **Portée :** Front-office.
    -   **Objectif :** Ce fichier contient probablement des styles de réinitialisation ou fondamentaux de base, éventuellement un sous-ensemble du framework Zurb Foundation, pour assurer un rendu cohérent des éléments du curseur. Il peut définir des styles de grille, de typographie ou de formulaire de base que le module utilise.
    -   **Sélecteurs clés :** Peut inclure des styles généraux `div`, `img`, `button`, ou des classes spécifiques comme `.row`, `.column`.
-   **`beforeafter/css/twentytwenty.css`**
    -   **Portée :** Front-office.
    -   **Objectif :** Contient le style spécifique requis pour le curseur de comparaison d'images « TwentyTwenty » lui-même.
    -   **Sélecteurs clés :** Définira l'apparence du conteneur du curseur, de la poignée du diviseur, de la superposition et du positionnement des images « avant » et « après ». Exemples : `.twentytwenty-container`, `.twentytwenty-overlay`, `.twentytwenty-handle`, `.twentytwenty-before`, `.twentytwenty-after`. Les développeurs peuvent surcharger ces classes dans le `custom.css` ou `theme.css` de leur thème pour correspondre au design de leur boutique.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :
    -   `beforeafter/views/templates/front/hook/displayFooter.tpl`
        -   **Hook :** `displayFooter` (ou potentiellement `displayFooterProduct` selon la logique interne).
        -   **Objectif :** Ce template est responsable du rendu de la structure HTML réelle du curseur de comparaison d'images « Avant & Après » sur le front-office. Il contiendra les éléments `div` que le JavaScript ciblera pour initialiser le plugin `twentytwenty`, y compris les balises `img` pour les images « avant » et « après ». Il inclut également probablement le chargement des ressources JavaScript et CSS nécessaires.
    -   `beforeafter/views/templates/front/hook/displayFooterCms.tpl`
        -   **Hook :** Probablement `displayFooter` ou `displayFooterProduct` mais potentiellement avec une logique conditionnelle pour les pages CMS.
        -   **Objectif :** Ce template pourrait être un fallback ou une alternative pour le rendu du curseur sur les pages CMS, bien que la description du module se concentre sur les pages produits. Son contenu serait similaire à `displayFooter.tpl`.
-   **Templates d'administration (`views/templates/admin/`)** :
    -   `beforeafter/views/templates/admin/displayAdminProductsExtra.tpl`
        -   **Hook :** `displayAdminProductsExtra`
        -   **Objectif :** Ce template rend les champs de saisie personnalisés et les formulaires de téléchargement dans la page d'édition de produit de PrestaShop dans le Back Office. Il fournit l'interface permettant aux administrateurs de télécharger et de gérer les images « Avant » et « Après » pour chaque produit. Il contiendra des éléments de formulaire (par exemple, `input type="file"`) et affichera potentiellement des miniatures des images déjà téléchargées.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module ne crée pas de tables SQL personnalisées.
    -   Il stocke ses paramètres de configuration (comme `BA_TEST`) dans la table `ps_configuration`.
    -   Les chemins d'images « avant » et « après » spécifiques aux produits sont probablement stockés en tant que valeurs de configuration ou attributs spécifiques aux produits, gérés via le hook `displayAdminProductsExtra` et les méthodes `install()` et `uninstall()` du module.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionProductUpdate` | Après la mise à jour d'un produit dans le Back Office. | Utilisé pour enregistrer les chemins des images « avant » et « après » téléchargées via la page d'édition de produit. |
| `displayFooterProduct` | Rend le contenu dans la section du pied de page de la page produit. | Utilisé pour afficher le curseur de comparaison d'images « Avant & Après » sur la page produit du front-office. |
| `displayAdminProductsExtra` | Rend du contenu supplémentaire sur la page d'édition de produit dans le Back Office. | Utilisé pour injecter les champs de formulaire personnalisés pour le téléchargement des images « avant » et « après » dans l'interface d'administration des produits. |
| `actionAdminControllerSetMedia` | Avant qu'un contrôleur d'administration ne rende sa vue, permettant aux modules d'ajouter du JS/CSS. | Utilisé pour charger les fichiers JavaScript nécessaires (`jquery.event.move.js`, `jquery.twentytwenty.js`, `twentytwenty.js`) et CSS (`foundation.css`, `twentytwenty.css`) pour le module dans le Back Office (si nécessaire pour la page produit d'administration) et potentiellement le front office. |
| `displayHeader` | Rend le contenu dans la section `<head>` des pages du front-office. | Utilisé pour charger les fichiers JavaScript et CSS nécessaires au curseur « Avant & Après » sur le front-office, en s'assurant qu'ils sont disponibles avant que le hook `displayFooterProduct` ne rende le HTML du curseur. |

## 5. Support officiel et mises à jour

Pour le support officiel, les mises à jour et toute assistance supplémentaire concernant le module « Avant & après - outil de comparaison d'images », veuillez vous référer à votre compte client MyPresta.eu. Vous y trouverez les dernières versions du module, la documentation et pourrez contacter notre équipe de support directement via le site web de MyPresta.eu.
"""
