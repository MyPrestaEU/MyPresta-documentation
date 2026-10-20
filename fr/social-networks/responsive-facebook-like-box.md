---
title: "Boîte J'aime Facebook Responsive - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Boîte J'aime Facebook Responsive par MyPresta.eu."
sidebar:
  label: "Boîte J'aime Facebook Responsive - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Responsive Facebook Like Box sur MyPresta.eu](https://mypresta.eu/modules/social-networks/responsive-facebook-like-box.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/responsive-facebook-like-box/)
>
> ---


# Boîte J'aime Facebook Responsive

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont habituellement disponibles sur tout environnement d'hébergement moderne. Aucune exigence d'hébergement spéciale au-delà d'une configuration PrestaShop standard.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal de votre module "Boîte J'aime Facebook Responsive". Ici, vous définirez l'apparence et le comportement de votre Boîte J'aime Facebook sur votre boutique.

- **Emplacement du menu :** Back Office > Modules > Gestionnaire de modules > Recherchez "Boîte J'aime Facebook Responsive" > Cliquez sur "Configurer".

#### Paramètres et options :

1.  **URL de la page Facebook :**

    -   **Ce que fait ce paramètre :** C'est le paramètre le plus critique. Il indique au module quelle page Facebook spécifique afficher dans la Boîte J'aime.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque défini sur l'URL de votre page Facebook (par exemple, `https://www.facebook.com/MyPresta.eu`) :* Le module affichera la Boîte J'aime pour cette page spécifique.
        -   *Lorsque laissé vide ou défini sur une URL invalide :* La Boîte J'aime ne s'affichera pas correctement ou pas du tout.
    -   **Valeur recommandée :** L'URL de votre page Facebook officielle.
    -   **Scénario / exemple pour le marchand :** Si la page Facebook de votre boutique est `https://www.facebook.com/MyAwesomeStore`, vous entreriez cette URL ici.
2.  **Largeur de la Boîte J'aime (en pixels) :**

    -   **Ce que fait ce paramètre :** Contrôle la taille horizontale de la Boîte J'aime Facebook.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque défini sur une valeur en pixels spécifique (par exemple, `340`) :* La Boîte J'aime tentera de s'afficher à cette largeur exacte.
        -   *Lorsque défini sur une valeur plus petite :* La boîte sera plus étroite, masquant potentiellement une partie du contenu ou rendant le texte plus petit.
        -   *Lorsque défini sur une valeur plus grande :* La boîte sera plus large, occupant plus d'espace horizontal.
    -   **Valeur recommandée :** `340` (C'est une valeur par défaut courante pour le Page Plugin de Facebook et fonctionne souvent bien dans les colonnes latérales). Pour les sections pleine largeur, vous pourriez utiliser une valeur plus grande ou la laisser s'ajuster automatiquement si le thème le permet.
    -   **Scénario / exemple pour le marchand :** Si votre colonne de droite fait 300px de large, la définir à 280-300px garantirait qu'elle s'adapte parfaitement sans déborder.
3.  **Hauteur de la Boîte J'aime (en pixels) :**

    -   **Ce que fait ce paramètre :** Contrôle la taille verticale de la Boîte J'aime Facebook.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque défini sur une valeur en pixels spécifique (par exemple, `500`) :* La Boîte J'aime s'affichera à cette hauteur exacte.
        -   *Lorsque défini sur une valeur plus petite :* La boîte sera plus courte, nécessitant potentiellement un défilement pour voir tout le contenu (comme les publications récentes ou les visages d'amis).
        -   *Lorsque défini sur une valeur plus grande :* La boîte sera plus haute, occupant plus d'espace vertical.
    -   **Valeur recommandée :** `500` (Un bon équilibre pour afficher du contenu sans être excessivement longue). Ajustez en fonction de la quantité de contenu que vous souhaitez afficher (par exemple, plus de publications = plus de hauteur).
    -   **Scénario / exemple pour le marchand :** Si vous souhaitez afficher 3-4 publications récentes de votre page Facebook, vous pourriez avoir besoin d'une hauteur de 500px ou plus. Si vous souhaitez uniquement afficher le bouton "J'aime" et la photo de couverture, une hauteur plus petite comme 200px pourrait suffire.
4.  **Afficher les visages des amis :**

    -   **Ce que fait ce paramètre :** Détermine si la Boîte J'aime affiche les photos de profil des personnes qui ont aimé votre page et qui sont également amies avec l'utilisateur actuel.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé (OUI) :* La Boîte J'aime affichera les visages, ajoutant un élément de preuve sociale, car les visiteurs voient leurs amis connectés à votre marque.
        -   *Lorsque désactivé (NON) :* Les visages ne seront pas affichés, ce qui donnera un aspect plus propre et plus compact.
    -   **Valeur recommandée :** OUI (Utilise la preuve sociale pour encourager plus de "J'aime").
    -   **Scénario / exemple pour le marchand :** L'activation de cette option peut augmenter la confiance et l'engagement, car les acheteurs sont plus susceptibles de suivre une marque que leurs amis aiment déjà.
5.  **Afficher le flux (Publications de votre page) :**

    -   **Ce que fait ce paramètre :** Contrôle si les publications récentes de votre page Facebook sont affichées dans la Boîte J'aime.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé (OUI) :* Vos dernières publications Facebook apparaîtront dans la boîte, fournissant du contenu frais et encourageant l'interaction.
        -   *Lorsque désactivé (NON) :* Seuls la photo de couverture, le nom de la page et le bouton "J'aime" seront visibles, rendant la boîte plus compacte.
    -   **Valeur recommandée :** OUI (Maintient le contenu frais et montre aux visiteurs le type de contenu qu'ils peuvent attendre s'ils vous suivent).
    -   **Scénario / exemple pour le marchand :** Si vous publiez régulièrement des mises à jour, des promotions ou du contenu intéressant sur Facebook, l'affichage du flux maintient vos visiteurs engagés avec votre activité sur les médias sociaux.
6.  **Afficher l'en-tête :**

    -   **Ce que fait ce paramètre :** Détermine si un petit en-tête "Facebook" est affiché en haut de la Boîte J'aime.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé (OUI) :* Un petit en-tête avec le logo et le texte Facebook apparaîtra.
        -   *Lorsque désactivé (NON) :* L'en-tête sera supprimé, donnant un aspect légèrement plus intégré, mais potentiellement moins clair qu'il s'agit d'un widget Facebook.
    -   **Valeur recommandée :** OUI (Fournit une marque et un contexte clairs).
    -   **Scénario / exemple pour le marchand :** Garder l'en-tête aide les utilisateurs à le reconnaître immédiatement comme un widget Facebook.
7.  **Utiliser un petit en-tête :**

    -   **Ce que fait ce paramètre :** Si "Afficher l'en-tête" est activé, cette option contrôle si une version plus petite de l'en-tête est utilisée.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé (OUI) :* L'en-tête sera plus compact.
        -   *Lorsque désactivé (NON) :* L'en-tête de taille standard sera utilisé.
    -   **Valeur recommandée :** OUI (Souvent plus esthétique dans les colonnes latérales ou les petits espaces).
    -   **Scénario / exemple pour le marchand :** Utile si vous placez la Boîte J'aime dans une colonne étroite où l'espace est limité.
8.  **S'adapter à la largeur du conteneur :**

    -   **Ce que fait ce paramètre :** C'est un paramètre de réactivité crucial. Il indique à la Boîte J'aime Facebook d'ajuster automatiquement sa largeur pour s'adapter à la largeur du conteneur dans lequel elle est placée (par exemple, la colonne de votre thème).
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé (OUI) :* La Boîte J'aime se redimensionnera dynamiquement, la rendant vraiment responsive et évitant les problèmes de débordement sur différentes tailles d'écran. Le paramètre "Largeur de la Boîte J'aime" pourrait être ignoré ou utilisé comme maximum.
        -   *Lorsque désactivé (NON) :* La Boîte J'aime essaiera de maintenir le paramètre "Largeur de la Boîte J'aime", ce qui pourrait entraîner des problèmes de mise en page sur les petits écrans si la largeur définie est trop grande.
    -   **Valeur recommandée :** OUI (Essentiel pour une conception responsive et une bonne expérience utilisateur sur mobile).
    -   **Scénario / exemple pour le marchand :** Si vous placez la Boîte J'aime dans une barre latérale responsive, l'activation de cette option garantit qu'elle s'adapte toujours parfaitement, quel que soit l'appareil utilisé par votre client.
9.  **Couleur de fond (Code Hexadécimal) :**

    -   **Ce que fait ce paramètre :** Vous permet de définir une couleur de fond personnalisée pour la Boîte J'aime en utilisant un code couleur hexadécimal (par exemple, `#FFFFFF` pour le blanc).
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque défini sur un code hexadécimal spécifique :* Le fond de la Boîte J'aime changera pour cette couleur.
        -   *Lorsque laissé vide ou défini sur un code invalide :* La couleur de fond par défaut de Facebook (généralement gris clair ou blanc) sera utilisée.
    -   **Valeur recommandée :** Faites correspondre la couleur de fond de votre thème ou laissez vide pour la valeur par défaut.
    -   **Scénario / exemple pour le marchand :** Si votre boutique a un thème sombre, vous pourriez le définir sur un gris foncé pour mieux l'intégrer.
10. **Hook de placement :**

    -   **Ce que fait ce paramètre :** Détermine où la Boîte J'aime Facebook sera affichée sur votre boutique PrestaShop.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque défini sur `displayHeader` :* La Boîte J'aime apparaîtra dans la section d'en-tête de votre boutique.
        -   *Lorsque défini sur `displayLeftColumn` ou `displayRightColumn` :* La Boîte J'aime apparaîtra dans la barre latérale respective.
        -   *Lorsque défini sur `displayFooter` :* La Boîte J'aime apparaîtra dans la section de pied de page.
        -   *Lorsque défini sur `displayProductButtons` ou un hook de page produit similaire :* La Boîte J'aime apparaîtra sur les pages produits.
    -   **Valeur recommandée :** `displayRightColumn` ou `displayLeftColumn` (Courant et efficace pour la visibilité sans être intrusif).
    -   **Scénario / exemple pour le marchand :** Si vous souhaitez que la Boîte J'aime soit visible sur la plupart des pages sans occuper l'espace principal de l'en-tête, la placer dans une colonne est un bon choix. Si vous voulez qu'elle soit très proéminente, l'en-tête pourrait être préféré.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | URL de la page Facebook | URL de votre page Facebook | Lie le module à votre page Facebook spécifique. |
| Configuration du module | Largeur de la Boîte J'aime (px) | 340 | Définit la taille horizontale. |
| Configuration du module | Hauteur de la Boîte J'aime (px) | 500 | Définit la taille verticale. |
| Configuration du module | Afficher les visages des amis | OUI | Affiche les photos de profil des amis pour la preuve sociale. |
| Configuration du module | Afficher le flux (Publications) | OUI | Affiche les publications récentes de votre page Facebook. |
| Configuration du module | Afficher l'en-tête | OUI | Affiche l'en-tête "Facebook". |
| Configuration du module | Utiliser un petit en-tête | OUI | Utilise un en-tête compact si "Afficher l'en-tête" est activé. |
| Configuration du module | S'adapter à la largeur du conteneur | OUI | Rend la Boîte J'aime responsive à son conteneur parent. |
| Configuration du module | Couleur de fond (Hex) | (Laisser vide pour la valeur par défaut) | Personnalise la couleur de fond de la boîte. |
| Configuration du module | Hook de placement | displayRightColumn / displayLeftColumn | Détermine où la boîte apparaît sur votre boutique. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : La Boîte J'aime Facebook ne s'affiche pas sur ma boutique. Que dois-je faire ?**

-   **R :** Tout d'abord, vérifiez que vous avez entré l'**"URL de la page Facebook"** correcte et complète dans la configuration du module. Assurez-vous qu'elle commence par `https://`.
-   **R :** Vérifiez que le **"Hook de placement"** que vous avez sélectionné est réellement actif et affiché par votre thème. Certains thèmes peuvent ne pas afficher certains hooks (par exemple, la colonne de gauche) sur toutes les pages. Essayez de passer à un hook différent comme `displayFooter` pour voir s'il apparaît là.
-   **R :** Videz le cache de votre PrestaShop. Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions antérieures). Videz également le cache de votre navigateur.
-   **R :** Assurez-vous que le module est activé. Dans **Modules > Gestionnaire de modules**, recherchez le module et confirmez qu'il n'est pas désactivé.

**Q2 : La Boîte J'aime semble trop large/étroite ou trop haute/courte.**

-   **R :** Ajustez les paramètres **"Largeur de la Boîte J'aime"** et **"Hauteur de la Boîte J'aime"** dans la configuration du module.
-   **R :** Si vous souhaitez qu'elle s'adapte automatiquement à la colonne de votre thème, assurez-vous que **"S'adapter à la largeur du conteneur"** est réglé sur OUI. C'est particulièrement important pour les thèmes responsives.

**Q3 : Pourquoi les publications récentes ou les visages d'amis ne s'affichent-ils pas dans la Boîte J'aime ?**

-   **R :** Vérifiez les paramètres de configuration du module :
    -   Assurez-vous que **"Afficher le flux (Publications de votre page)"** est réglé sur OUI pour afficher les publications.
    -   Assurez-vous que **"Afficher les visages des amis"** est réglé sur OUI pour afficher les visages des amis.
-   **R :** L'API de Facebook a parfois des limitations ou des retards. Assurez-vous que votre page Facebook a des publications publiques récentes.

**Q4 : La couleur de fond que j'ai définie n'apparaît pas.**

-   **R :** Assurez-vous d'avoir entré un code couleur hexadécimal valide (par exemple, `#RRGGBB`). Si vous utilisez un thème personnalisé, il peut y avoir des styles CSS conflictuels. Vous pourriez avoir besoin d'un développeur web pour inspecter l'élément et appliquer une règle CSS plus spécifique si le paramètre du module est ignoré.

**Q5 : Le module fonctionne sur ordinateur mais semble étrange sur mobile.**

-   **R :** Cela est presque toujours dû au paramètre **"S'adapter à la largeur du conteneur"**. Assurez-vous qu'il est réglé sur OUI. Cela indique au widget Facebook d'être responsive. Vérifiez également la réactivité de votre thème ; si le conteneur dans lequel se trouve le module n'est pas responsive, le module ne peut pas s'adapter parfaitement.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé du module "Boîte J'aime Facebook Responsive" pour les développeurs et les webmasters.

### 4.1 Vue d'ensemble de l'architecture

Le module `Boîte J'aime Facebook Responsive` (`likebox/ar.php`) est un module PrestaShop standard suivant le modèle MVC, le cas échéant, pour sa configuration. Il exploite principalement le système de hooks de PrestaShop pour injecter le Page Plugin Facebook (Boîte J'aime) à divers emplacements du front-office. La fonctionnalité principale repose sur le SDK JavaScript du Page Plugin Facebook, qui est chargé et configuré dynamiquement en fonction des paramètres du module. La configuration est gérée via `Configuration::get()` et `Configuration::updateValue()` au sein de la classe principale du module.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la configuration est gérée directement dans la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée et n'étend pas `ObjectModel`. Toute la logique est encapsulée dans le fichier principal du module `ar.php`.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`likebox/jscolor/jscolor.js`**

    -   **Portée :** Back-office (Page de configuration de l'administration).
    -   **Objectif :** Il s'agit d'une bibliothèque JavaScript tierce pour un sélecteur de couleurs. Elle est utilisée sur la page de configuration du module pour fournir une interface conviviale permettant de sélectionner le paramètre "Couleur de fond".
    -   **Fonctionnalité :** Elle transforme un champ de saisie de texte standard en un sélecteur de couleurs interactif, permettant à l'administrateur de sélectionner visuellement un code couleur hexadécimal.
-   **`likebox/script.js`**

    -   **Portée :** Front-office.
    -   **Objectif :** Ce script est responsable du chargement dynamique du SDK JavaScript de Facebook et de l'initialisation du Page Plugin Facebook (Boîte J'aime) sur le front-office.
    -   **Fonctionnalité :**
        -   Il vérifie généralement l'existence du SDK Facebook (`FB`) et le charge s'il n'est pas déjà présent.
        -   Il appelle ensuite `FB.XFBML.parse()` ou des méthodes similaires pour rendre l'élément `div` avec la classe `fb-page`, en appliquant les attributs (data-href, data-width, etc.) basés sur la configuration du module.
        -   Il garantit que la Boîte J'aime est rendue correctement une fois le DOM prêt.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`likebox/css/css.css`**

    -   **Portée :** Front-office.
    -   **Objectif :** Contient des règles de style générales pour le conteneur de la Boîte J'aime Facebook et potentiellement quelques ajustements responsives.
    -   **Sélecteurs clés :** Cible probablement le `div` conteneur principal qui enveloppe le Page Plugin Facebook, garantissant qu'il s'intègre dans la mise en page du thème et gère la réactivité de base. Les développeurs peuvent remplacer ces styles dans le `custom.css` ou `theme.css` de leur thème si nécessaire.
-   **`likebox/css.css`**

    -   **Portée :** Front-office.
    -   **Objectif :** Similaire à `likebox/css/css.css`, ce fichier contient probablement des règles de style supplémentaires ou alternatives pour l'affichage front-office de la Boîte J'aime. Il peut inclure des règles pour des placements spécifiques ou des ajustements visuels mineurs.
    -   **Sélecteurs clés :** Cible le conteneur de la Boîte J'aime Facebook et les éléments associés.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **`likebox/header.tpl`**

    -   **Portée :** Front-office.
    -   **Hook :** `displayHeader` (ou un hook similaire lié à l'en-tête).
    -   **Objectif :** Ce template est responsable de la sortie de la structure HTML de la Boîte J'aime Facebook lorsque le module est configuré pour s'afficher dans l'en-tête. Il contient l'élément `div` avec la classe `fb-page` et les attributs `data-*` que le SDK Facebook utilise pour rendre le plugin.
    -   **Variables :** Accède aux variables de configuration (par exemple, `{$facebook_page_url}`, `{$width}`, `{$height}`, `{$show_faces}`, etc.) passées depuis la logique PHP du module.
-   **`likebox/rightcolumn.tpl`**

    -   **Portée :** Front-office.
    -   **Hook :** `displayRightColumn` (ou `displayLeftColumn`, `displayFooter`, `displayProductButtons`, etc., selon le hook choisi).
    -   **Objectif :** Ce template est responsable de la sortie de la structure HTML de la Boîte J'aime Facebook lorsque le module est configuré pour s'afficher dans une colonne ou d'autres zones de contenu. Il contient l'élément `div` avec la classe `fb-page` et les attributs `data-*`.
    -   **Variables :** Similaire à `header.tpl`, il accède aux variables de configuration pour définir dynamiquement les attributs du plugin.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :

    -   Ce module ne crée aucune table SQL personnalisée.
    -   Tous les paramètres de configuration sont stockés dans la table `ps_configuration` (ou le préfixe `_configuration`) en utilisant des clés comme `RESPONSIVE_FB_LIKEBOX_URL`, `RESPONSIVE_FB_LIKEBOX_WIDTH`, etc.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rendu dans la section `<head>` de la page, ou en haut du `<body>`. | Injecte le HTML de la Boîte J'aime Facebook et potentiellement le script d'initialisation du SDK Facebook. |
| `displayLeftColumn` | Rend le contenu dans la barre latérale gauche de la boutique. | Injecte le HTML de la Boîte J'aime Facebook dans la colonne de gauche. |
| `displayRightColumn` | Rend le contenu dans la barre latérale droite de la boutique. | Injecte le HTML de la Boîte J'aime Facebook dans la colonne de droite. |
| `displayFooter` | Rend le contenu dans la section de pied de page de la boutique. | Injecte le HTML de la Boîte J'aime Facebook dans le pied de page. |
| `displayProductButtons` (ou hook de page produit similaire) | Rend le contenu sur la page produit, souvent près du bouton "Ajouter au panier" ou de la description. | Injecte le HTML de la Boîte J'aime Facebook sur les pages produits. |
| `actionFrontControllerSetMedia` | Exécuté lorsqu'un contrôleur frontal définit ses médias (JS/CSS). | Enregistre les fichiers CSS et JavaScript du module pour l'affichage front-office. |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses médias (JS/CSS). | Enregistre le script `jscolor.js` et potentiellement le CSS spécifique à l'administration pour la page de configuration du module. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, les nouvelles versions et le support officiel du module "Boîte J'aime Facebook Responsive", veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez rencontrer.
