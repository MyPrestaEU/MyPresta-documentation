---
title: "Bloc Nouveaux produits sur la page d'accueil - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Bloc Nouveaux produits sur la page d'accueil par MyPresta.eu."
sidebar:
  label: "Bloc Nouveaux produits sur la page d'accueil - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Home new products block sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/home-new-products-block.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/home-new-products-block/)
>
> ---


# Bloc Nouveaux produits sur la page d'accueil

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est nécessaire au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Bloc Nouveaux produits sur la page d'accueil » pour accéder à ses paramètres.

#### Paramètre : Nombre de produits à afficher

-   **Ce que fait ce paramètre :** Ce champ vous permet de contrôler combien de vos nouveaux produits seront affichés dans le bloc sur votre page d'accueil.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est défini sur un nombre plus élevé (par exemple, 10) :* Plus de nouveaux produits seront visibles dans le bloc, offrant aux clients une sélection plus large de vos derniers articles. Cela pourrait rendre le bloc plus long ou nécessiter plus de défilement.
    -   *Lorsqu'il est défini sur un nombre plus faible (par exemple, 4) :* Moins de nouveaux produits seront affichés, rendant le bloc plus compact. Cela peut être utile si vous avez un espace limité ou si vous souhaitez mettre en évidence uniquement les articles les plus récents.
-   **Valeur recommandée :** Un bon point de départ est `8` ou `12` produits. Cela offre une sélection décente sans surcharger la page.
-   **Scénario / exemple de marchand :** Si vous gérez un magasin de mode et ajoutez 20 nouveaux articles chaque semaine, le fait de le définir sur `12` garantit qu'une bonne variété est toujours visible. Si vous n'ajoutez que quelques nouveaux produits artisanaux chaque mois, `4` ou `6` pourraient être plus appropriés pour garder le bloc concis.

#### Paramètre : Afficher sur la page d'accueil

-   **Ce que fait ce paramètre :** Il s'agit d'un simple interrupteur ON/OFF qui contrôle si le « Bloc Nouveaux produits sur la page d'accueil » est visible sur la page d'accueil de votre boutique.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (OUI) :* Le bloc avec vos nouveaux produits apparaîtra sur votre page d'accueil, comme décrit dans la Section 2.
    -   *Lorsqu'il est désactivé (NON) :* Le bloc sera masqué de votre page d'accueil. Cela peut être utile si vous souhaitez le supprimer temporairement sans désinstaller le module, ou si vous préférez utiliser d'autres méthodes pour présenter de nouveaux produits.
-   **Valeur recommandée :** `OUI` (Activé). Le but principal de ce module est d'afficher de nouveaux produits sur la page d'accueil.
-   **Scénario / exemple de marchand :** Vous pourriez le désactiver temporairement si vous menez une campagne saisonnière spéciale qui nécessite tout l'espace de la page d'accueil pour des bannières promotionnelles, puis le réactiver une fois la campagne terminée.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Nombre de produits à afficher | 8-12 | Contrôle le nombre de nouveaux produits affichés dans le bloc. Un nombre plus élevé en montre plus, un nombre plus faible le rend plus compact. |
| Page de configuration du module | Afficher sur la page d'accueil | OUI | Active ou désactive la visibilité du bloc de nouveaux produits sur votre page d'accueil. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mon bloc de nouveaux produits n'apparaît pas sur la page d'accueil après l'installation.**
R :

1.  **Vérifiez la configuration du module :** Allez dans **Modules > Gestionnaire de modules**, trouvez « Bloc Nouveaux produits sur la page d'accueil » et cliquez sur « Configurer ». Assurez-vous que « Afficher sur la page d'accueil » est défini sur `OUI`.
2.  **Videz le cache :** Parfois, le cache de PrestaShop empêche les modifications d'apparaître immédiatement. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » dans le coin supérieur droit.
3.  **Vérifiez la position du hook :** Bien que le module soit conçu pour s'accrocher automatiquement, des conflits de thème ou d'autres modules peuvent parfois interférer. Allez dans **Design > Positions**. Recherchez `displayHome` (ou `displayHomeTabContent` si votre thème utilise des onglets). Assurez-vous que `home-new-products-block` est listé et activé dans l'un de ces hooks. Si ce n'est pas le cas, vous devrez peut-être « Greffer un module » à `displayHome`.

**Q : Le bloc affiche d'anciens produits, pas de nouveaux.**
R : Le module affiche les produits en fonction de leur « date d'ajout » dans PrestaShop. Assurez-vous que lorsque vous ajoutez de nouveaux produits, leur date de création est correctement définie à la date actuelle. Si vous avez importé des produits avec d'anciennes dates, ils pourraient ne pas apparaître comme « nouveaux ». Vous devrez peut-être mettre à jour manuellement le champ `date_add` pour ces produits dans votre base de données (tâche avancée, consultez un développeur) ou les ajouter à nouveau.

**Q : Je souhaite modifier l'emplacement du bloc sur ma page d'accueil (par exemple, plus haut, ou dans une colonne).**
R : Vous pouvez ajuster la position du module à l'aide de la fonction « Live Edit » intégrée de PrestaShop.

1.  Allez dans **Design > Positions**.
2.  Cliquez sur le bouton « Lancer le Live Edit » (généralement en haut à droite).
3.  Naviguez vers votre page d'accueil.
4.  Vous devriez voir des contours autour de divers blocs de modules. Trouvez le « Bloc Nouveaux produits sur la page d'accueil » et faites-le glisser vers la position souhaitée. Vous pouvez également utiliser le bouton « Greffer un module » pour le déplacer vers un autre hook (par exemple, `displayLeftColumn`, `displayRightColumn`, `displayFooter`).

**Q : Le bloc a l'air étrange ou ne correspond pas au style de mon thème.**
R : Ce module utilise des modèles d'affichage de produits PrestaShop standard, qui devraient hériter de la plupart du style de votre thème. Si l'apparence est incorrecte :

1.  **Videz le cache :** Comme ci-dessus, videz le cache de votre PrestaShop.
2.  **Surcharges de thème :** Votre thème peut avoir un CSS spécifique qui entre en conflit. Cela nécessite généralement qu'un développeur web inspecte le CSS de votre site et ajoute potentiellement des styles personnalisés au fichier `custom.css` de votre thème ou équivalent pour remplacer les valeurs par défaut.
3.  **Mise à jour du module :** Assurez-vous d'avoir la dernière version du module de MyPresta.eu.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Bloc Nouveaux produits sur la page d'accueil » est un module PrestaShop simple qui suit la structure de module standard. Il utilise principalement la classe `Module` pour gérer son cycle de vie (installation, désinstallation) et les méthodes `hook` pour rendre le contenu dans le front-office. Il récupère les données des produits directement à partir des tables de la base de données principale de PrestaShop, en tirant parti des fonctionnalités `Product` et `Category` existantes. Il n'y a pas de contrôleurs personnalisés ou d'ObjectModels complexes, ce qui le rend léger et facile à intégrer.

### 4.2 Contrôleurs (`controllers/`)

-   Ce module ne contient **pas** de contrôleurs Front-Office ou Back-Office personnalisés. Toute la logique est encapsulée dans le fichier principal du module et exécutée via des hooks.

### 4.3 Classes et modèles principaux (`classes/`)

-   Ce module ne contient **pas** de classes ou d'ObjectModels personnalisés dans un répertoire `classes/`. Il s'appuie sur les classes `Product` et `Category` de PrestaShop pour la récupération des données.

### 4.4 Actifs JavaScript (`views/js/`)

-   Ce module n'inclut **pas** de fichiers JavaScript personnalisés. Tout comportement dynamique (par exemple, les carrousels) serait généralement géré par le JS existant du thème ou un module distinct.

### 4.5 Feuilles de style CSS (`views/css/`)

-   Ce module n'inclut **pas** de fichiers CSS personnalisés. Il s'appuie sur le style par défaut du thème pour les listes et les grilles de produits. Les développeurs souhaitant styliser spécifiquement ce bloc doivent cibler sa structure HTML (par exemple, `div#home_new_products`) dans le fichier `custom.css` de leur thème ou équivalent.

### 4.6 Structure du modèle Smarty (`views/templates/`)

-   Ce module utilise principalement un seul fichier de modèle pour rendre son contenu.

    -   **Modèles de hook (`views/templates/hook/`)** :
        -   `views/templates/hook/home-new-products-block.tpl` : Il s'agit du fichier de modèle principal responsable du rendu du bloc de nouveaux produits sur la page d'accueil.
            -   **Hook :** Principalement destiné à `displayHome` (ou `displayHomeTabContent` dans certains thèmes).
            -   **Objectif :** Il itère sur la variable `$products` (un tableau d'objets `Product`) passée par la méthode `hookDisplayHome` et affiche l'image, le nom, le prix et le bouton « Ajouter au panier » de chaque produit, généralement en utilisant une boucle et en incluant un modèle d'élément de liste de produits standard (par exemple, `product-miniature.tpl` ou similaire, selon la version de PrestaShop et le thème).

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :

    -   Ce module ne crée **pas** de tables de base de données personnalisées.
    -   Il stocke ses paramètres de configuration (par exemple, `HOME_NEW_PRODUCTS_NBR`, `HOME_NEW_PRODUCTS_DISPLAY`) dans la table standard `ps_configuration`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHome` | Rend le contenu dans la zone principale de la page d'accueil. | Affiche le bloc de nouveaux produits sur la page d'accueil de la boutique. |
| `displayHeader` | Exécuté dans la section `<head>` de chaque page. | Utilisé pour enregistrer des actifs (CSS/JS) s'il y en avait, bien que ce module ne l'utilise pas à cette fin. Pourrait être utilisé pour des balises meta ou d'autres éléments globaux. |
| `displayLeftColumn` | Rend le contenu dans la barre latérale gauche. | Permet de déplacer le bloc de nouveaux produits vers la colonne de gauche via « Design > Positions ». |
| `displayRightColumn` | Rend le contenu dans la barre latérale droite. | Permet de déplacer le bloc de nouveaux produits vers la colonne de droite via « Design > Positions ». |
| `displayFooter` | Rend le contenu dans le pied de page de la boutique. | Permet de déplacer le bloc de nouveaux produits vers le pied de page via « Design > Positions ». |
| `actionProductAdd` | Exécuté après l'ajout d'un nouveau produit. | Pourrait être utilisé pour vider le cache ou réindexer, bien que non explicitement utilisé par ce module. |
| `actionProductUpdate` | Exécuté après la mise à jour d'un produit. | Pourrait être utilisé pour vider le cache ou réindexer, bien que non explicitement utilisé par ce module. |
| `actionProductDelete` | Exécuté après la suppression d'un produit. | Pourrait être utilisé pour vider le cache ou réindexer, bien que non explicitement utilisé par ce module. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Bloc Nouveaux produits sur la page d'accueil », veuillez vous référer à votre compte client MyPresta.eu. Vous pouvez télécharger les dernières versions et accéder aux ressources de support directement depuis [MyPresta.eu](https://mypresta.eu).
