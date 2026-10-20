---
title: "Ajouter des images aux commentaires de produits (avis) - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Ajouter des images aux commentaires de produits (avis)' par MyPresta.eu."
sidebar:
  label: "Ajouter des images aux commentaires de produits (avis) - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Add pictures to product comments (reviews) sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/add-pictures-to-product-comments-reviews.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/add-pictures-to-product-comments-reviews/)
>
> ---


# Ajouter des images aux commentaires de produits (avis)

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).
- **Dépendance** : Ce module nécessite que le module « Commentaires de produits » (développé par MyPresta.eu) soit installé et actif, car il étend ses fonctionnalités.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Ajouter des images aux commentaires de produits (avis) » dans le Gestionnaire de modules. Cela vous mènera à son écran de configuration principal.

La configuration du module est simple, se concentrant principalement sur l'activation ou la désactivation de sa fonctionnalité principale.

**Paramètres et options :**

-   **Activer le téléchargement d'images pour les commentaires de produits :**
    *   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité principale du module. Lorsqu'il est activé, vos clients verront l'option de télécharger des images lorsqu'ils écrivent un avis sur un produit.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé (OUI) :* Le champ de téléchargement d'images apparaîtra dans le formulaire de soumission d'avis sur les pages de vos produits. Les clients pourront alors joindre des images à leurs avis. Les avis existants avec des images afficheront également ces images.
        *   *Lorsqu'il est désactivé (NON) :* Le champ de téléchargement d'images sera masqué du formulaire de soumission d'avis. Les clients ne pourront soumettre que des avis textuels. Les avis existants avec des images pourraient toujours les afficher, mais aucune nouvelle image ne pourra être ajoutée.
    *   **Valeur recommandée :** **OUI**. Pour tirer parti des avantages des avis visuels, vous devriez activer cette fonctionnalité.
    *   **Scénario/exemple pour le marchand :** Si vous souhaitez permettre aux clients de montrer leur nouvelle robe ou comment un gadget fonctionne dans la vie réelle, activez cette option. Si vous souhaitez temporairement restreindre les téléchargements d'images pour la maintenance ou une campagne spécifique, vous pouvez la désactiver.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Activer le téléchargement d'images pour les commentaires de produits | OUI | Contrôle si les clients peuvent télécharger des images avec leurs avis sur les produits. |

## 3. Dépannage pour le marchand et questions fréquemment posées (FAQ)

**Q : J'ai activé le module, mais je ne vois pas le champ de téléchargement d'images sur ma page produit.**
R :

1.  **Vérifiez le module « Commentaires de produits » :** Ce module étend le module « Commentaires de produits ». Assurez-vous que le module « Commentaires de produits » (par MyPresta.eu) est installé, activé et configuré correctement sur votre boutique.
2.  **Videz le cache :** Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop et cliquez sur « Vider le cache » en haut à droite. Parfois, d'anciens fichiers mis en cache empêchent l'apparition de nouvelles fonctionnalités de module.
3.  **Compatibilité du thème :** Bien que le module soit conçu pour une large compatibilité, les thèmes personnalisés peuvent parfois remplacer les structures de modèles par défaut. Si vider le cache ne résout pas le problème, contactez le support MyPresta.eu avec les détails de votre thème.

**Q : Mes clients téléchargent des images, mais elles n'apparaissent pas à côté de l'avis.**
R :

1.  **Modération des avis :** Vérifiez si votre module « Commentaires de produits » a la modération des avis activée. Si c'est le cas, les nouveaux avis (et leurs images associées) n'apparaîtront qu'après que vous les ayez approuvés dans le Back Office.
2.  **Vérifiez la configuration du module :** Vérifiez à nouveau que « Activer le téléchargement d'images pour les commentaires de produits » est réglé sur OUI dans la configuration de ce module.
3.  **Permissions de fichiers :** Assurez-vous que le répertoire `img/p/` (ou l'endroit où PrestaShop stocke les images de produits) a les bonnes permissions d'écriture (généralement 755 ou 775). Si le serveur ne peut pas écrire de fichiers, les images ne seront pas enregistrées.

**Q : Puis-je limiter le nombre d'images qu'un client peut télécharger par avis ?**
R : Ce module spécifique fournit une fonctionnalité de téléchargement de base. Des contrôles avancés comme la limitation du nombre d'images ou de la taille des fichiers peuvent nécessiter des modifications personnalisées ou une mise à jour du module principal « Commentaires de produits ». Veuillez vérifier les paramètres du module « Commentaires de produits » ou contacter le support MyPresta.eu pour de telles fonctionnalités.

**Q : Les images téléchargées semblent déformées ou ne sont pas affichées correctement.**
R :

1.  **Conflits CSS :** Le CSS de votre thème pourrait être en conflit avec le style du module. Utilisez les outils de développement de votre navigateur (F12) pour inspecter les éléments d'image et identifier les styles conflictuels.
2.  **Régénération des images :** Parfois, les miniatures d'images peuvent ne pas être générées correctement. Dans PrestaShop, allez dans **Design > Paramètres des images** et essayez de régénérer les miniatures pour les « produits » ou les « avis » si une telle option existe, ou pour toutes les images.
3.  **Qualité de l'image originale :** Conseillez aux clients de télécharger des images de taille raisonnable et claires. Les images de très basse résolution auront naturellement un aspect médiocre lorsqu'elles seront affichées en plus grand.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Ajouter des images aux commentaires de produits (avis) » (`reviewspics`) est conçu comme une extension du module principal « Commentaires de produits » (vraisemblablement `productcomments` ou un module similaire de MyPresta.eu). Il injecte principalement une interface de téléchargement d'images dans le formulaire d'avis existant et modifie l'affichage des avis pour inclure des images. Il utilise le système de hooks de PrestaShop pour l'intégration et utilise les ressources standard du front-office et du back-office. Le module crée une table de base de données personnalisée pour lier les images à des commentaires de produits spécifiques.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur Front-Office ou Back-Office personnalisé. Sa fonctionnalité est intégrée via des hooks et des modifications directes de modèles dans le contexte du module parent « Commentaires de produits ».

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit pas de classes personnalisées dans le répertoire `classes/`. Sa logique principale réside dans le fichier principal du module `index.php` et le fichier `install.sql` pour le schéma de la base de données.

### 4.4 Ressources JavaScript (`views/js/`)

-   **`reviewspics/views/js/reviewspics-bo.js`**

    -   **Portée :** Back-office.
    -   **Objectif :** Ce script gère probablement toute fonctionnalité basée sur JavaScript dans la configuration du back-office du module ou pour la gestion des images téléchargées associées aux avis dans le panneau d'administration. Cela pourrait inclure des appels AJAX pour la suppression d'images, les mises à jour de statut ou les éléments de formulaire dynamiques.
    -   **Détails :** Il se lierait généralement aux éléments du modèle `backOffice.tpl` ou à l'interface de gestion des commentaires de produits de l'administration.
-   **`reviewspics/views/js/reviewspics.js`**

    -   **Portée :** Front-office.
    -   **Objectif :** Il s'agit du JavaScript principal du front-office pour la fonctionnalité de téléchargement d'images. Il gère :
        -   L'affichage du champ de téléchargement d'images (par exemple, champ de fichier, zone de glisser-déposer).
        -   La prévisualisation des images sélectionnées avant le téléchargement.
        -   Le téléchargement d'images basé sur AJAX lors de la soumission de l'avis.
        -   La validation des types/tailles d'images (côté client).
        -   Potentiellement, la suppression des images sélectionnées avant la soumission.
    -   **Détails :** Il se lie aux éléments du formulaire de soumission d'avis, probablement dans le modèle `displayMyPrestaCommentsField.tpl`, et interagit avec la logique côté serveur pour traiter les fichiers image.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`reviewspics/views/css/reviewspics.css`**
    -   **Portée :** Front-office (principalement) et potentiellement Back-office.
    -   **Objectif :** Cette feuille de style fournit le style visuel pour le formulaire de téléchargement d'images et l'affichage des images téléchargées dans les avis sur les produits.
    -   **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :**
        -   La zone de téléchargement d'images (par exemple, bordure, arrière-plan, icône).
        -   Les aperçus d'images (taille, rapport d'aspect, bordures).
        -   La disposition des images dans un avis.
        -   Potentiellement, le style pour la gestion des images dans le Back Office.
    -   **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer :** Recherchez des classes comme `.reviewspics-upload-area`, `.reviewspics-image-preview`, `.reviewspics-review-images`, etc. Celles-ci peuvent être ciblées dans le `custom.css` ou `theme.css` d'un thème personnalisé pour correspondre à l'image de marque de la boutique.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** :

    -   **`reviewspics/views/templates/hook/backOffice.tpl`**

        -   **Hook :** Probablement rendu dans `displayAdminProductsExtra` ou un hook personnalisé dans l'interface d'administration du module « Commentaires de produits ».
        -   **Sorties :** Ce modèle est destiné au Back Office. Il rend probablement le formulaire de configuration du module (tel que décrit dans la section 4.1) ou fournit une interface permettant aux administrateurs de gérer les images associées aux commentaires de produits (par exemple, visualiser, supprimer, approuver des images).
    -   **`reviewspics/views/templates/hook/displayMyPrestaComment.tpl`**

        -   **Hook :** Ce modèle est conçu pour être accroché à l'affichage d'un *commentaire de produit individuel*, probablement dans `displayProductListReviews` ou un hook similaire fourni par le module « Commentaires de produits ».
        -   **Sorties :** Il rend les images réelles associées à un avis de produit spécifique. Il itérerait sur les images liées au commentaire et les afficherait, potentiellement sous forme de miniatures ou d'une petite galerie.
    -   **`reviewspics/views/templates/hook/displayMyPrestaCommentsField.tpl`**

        -   **Hook :** Ce modèle est destiné à être injecté dans le *formulaire de soumission d'avis* sur les produits, probablement via un hook comme `displayProductForm` ou un hook personnalisé dans le formulaire d'avis du module « Commentaires de produits ».
        -   **Sorties :** Il rend la structure HTML pour le champ de saisie de téléchargement d'images avec lequel les clients interagissent lorsqu'ils écrivent un nouvel avis. Cela inclut le champ de fichier, toutes les zones de glisser-déposer et potentiellement des espaces réservés pour les aperçus d'images.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** :

    -   Le fichier `reviewspics/install.sql` indique la création d'au moins une table personnalisée pour stocker les données d'image et les lier aux commentaires de produits.
    -   **`ps_reviewspics_image`** : (Nom de table probable, basé sur le nom du module et les conventions courantes de PrestaShop).
        -   **Objectif :** Stocke les métadonnées de chaque image téléchargée.
        -   **Champs (attendus) :**
            -   `id_reviewspics_image` (Clé primaire, INT)
            -   `id_product_comment` (Clé étrangère, INT, liant à la table d'avis du module parent « Commentaires de produits »)
            -   `image_name` (VARCHAR, nom de fichier de l'image)
            -   `date_add` (DATETIME, horodatage du téléchargement)
            -   `active` (TINYINT, pour la modération/visibilité)
            -   `position` (INT, pour l'ordre si plusieurs images par avis)
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rendu dans la section `<head>` de toutes les pages du front-office. | Pour inclure les fichiers CSS (`reviewspics.css`) et JavaScript (`reviewspics.js`) du front-office. |
| `displayBackOfficeHeader` | Rendu dans la section `<head>` de toutes les pages du back-office. | Pour inclure les fichiers CSS et JavaScript (`reviewspics-bo.js`) du back-office pour la configuration de l'administration ou la gestion des avis. |
| `displayProductListReviews` (ou similaire du module Commentaires de produits) | Rendu dans la liste des avis sur les produits sur les pages produits. | Pour injecter `displayMyPrestaComment.tpl` afin d'afficher les images dans les avis existants. |
| `displayProductForm` (ou similaire du module Commentaires de produits) | Rendu dans le formulaire de soumission d'avis sur les produits. | Pour injecter `displayMyPrestaCommentsField.tpl` pour le champ de téléchargement d'images. |
| `actionProductCommentAdd` (ou similaire du module Commentaires de produits) | Exécuté après l'ajout d'un nouveau commentaire de produit. | Pour traiter les images téléchargées, les enregistrer dans le système de fichiers et enregistrer leurs détails dans la table `ps_reviewspics_image`, en les liant au nouveau commentaire. |
| `actionProductCommentDelete` (ou similaire du module Commentaires de produits) | Exécuté après la suppression d'un commentaire de produit. | Pour nettoyer les images associées du système de fichiers et de la table `ps_reviewspics_image`. |
| `actionProductCommentUpdate` (ou similaire du module Commentaires de produits) | Exécuté après la mise à jour d'un commentaire de produit. | Pour gérer toute modification des associations d'images ou du statut de modération. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support professionnel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe est dédiée à assurer le bon fonctionnement et l'amélioration continue de vos modules PrestaShop.
