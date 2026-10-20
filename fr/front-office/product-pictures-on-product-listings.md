---
title: "Images de produits sur les listes de produits - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Images de produits sur les listes de produits' par MyPresta.eu."
sidebar:
  label: "Images de produits sur les listes de produits - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Product pictures on product listings sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-pictures-on-product-listings.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/product-pictures-on-product-listings/)
>
> ---


# Images de produits sur les listes de produits

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises pour PrestaShop lui-même et généralement disponibles sur tous les environnements d'hébergement modernes.

## 2. Présentation complète de la configuration (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module « Images de produits sur les listes de produits ». Vous pouvez y accéder en naviguant vers **Modules > Gestionnaire de modules** et en cliquant sur « Configurer » à côté du nom du module.

#### **Position du module**

- **Ce que fait ce paramètre :** Il détermine où les images de produits supplémentaires apparaîtront par rapport à l'image principale du produit sur les pages de liste.
- **Effet de la modification de ce paramètre :**
  - *displayProductAdditionalInfo :* Les images apparaîtront dans un hook commun souvent utilisé pour des détails de produit supplémentaires.
  - *displayAfterProductThumbs :* Les images apparaîtront immédiatement après les vignettes de l'image principale du produit (si votre thème les affiche).
  - *displayFooterProduct :* Les images apparaîtront dans la section du pied de page du bloc produit sur la page de liste.
  - *displayProductDeliveryTime :* Les images apparaîtront près des informations de délai de livraison (si votre thème les affiche).
  - *displayHeader :* C'est une position moins courante pour les images de produits sur les pages de liste et pourrait nécessiter un style personnalisé pour un rendu optimal.
  - *displayProductListReviews :* Les images apparaîtront près des étoiles ou du nombre d'avis sur le produit (si votre thème les affiche).
- **Valeur recommandée :** Expérimentez d'abord avec `displayProductAdditionalInfo` ou `displayAfterProductThumbs`, car ce sont généralement de bons emplacements visuels.
- **Scénario/exemple pour le marchand :** Si votre thème a une mise en page épurée et que vous souhaitez que les images soient subtilement intégrées sous l'image principale, `displayProductAdditionalInfo` pourrait être le meilleur choix. Si vous voulez qu'elles ressortent davantage, `displayFooterProduct` pourrait fonctionner.

#### **Design du module**

- **Ce que fait ce paramètre :** Il vous permet de choisir entre différents styles visuels pour la sortie du module, affectant principalement la manière dont les vignettes sont présentées.
- **Effet de la modification de ce paramètre :**
  - *Thème classique :* Applique un style souvent compatible avec les thèmes PrestaShop plus anciens ou les thèmes qui imitent l'apparence classique.
  - *Universel :* Applique un design plus moderne et réactif qui vise à bien fonctionner avec un plus large éventail de thèmes contemporains.
- **Valeur recommandée :** `Universel` pour la plupart des boutiques PrestaShop modernes (1.7.x, 8.x, 9.x). Utilisez `Thème classique` si vous avez un thème plus ancien ou fortement personnalisé qui ne rend pas `Universel` correctement.
- **Scénario/exemple pour le marchand :** Si votre boutique utilise un thème PrestaShop 8 par défaut, `Universel` s'intégrera probablement de manière transparente. Si vous êtes sur PrestaShop 1.6 avec un thème personnalisé, `Thème classique` pourrait être un pari plus sûr.

#### **Méthode d'affichage**

- **Ce que fait ce paramètre :** Il contrôle quelles images supplémentaires sont affichées pour chaque produit sur la page de liste.
- **Effet de la modification de ce paramètre :**
  - *Images pour les combinaisons de couleurs :* N'affiche que les images spécifiquement liées aux attributs de couleur d'un produit. Utile pour la mode ou les produits avec des variantes de couleur distinctes.
  - *Images pour chaque combinaison :* Affiche les images pour toutes les combinaisons de produits (par exemple, taille, couleur, matériau). Cela peut entraîner de nombreuses images si vous avez beaucoup de combinaisons.
  - *Toutes les images du produit :* Affiche toutes les images associées au produit, quelle que soit la combinaison. C'est l'option la plus complète.
- **Valeur recommandée :** `Toutes les images du produit` pour la plupart des produits généraux. `Images pour les combinaisons de couleurs` si vos produits dépendent fortement des variations de couleur et que vous souhaitez maintenir le nombre d'images gérable.
- **Scénario/exemple pour le marchand :** Pour un magasin de vêtements, la sélection de `Images pour les combinaisons de couleurs` afficherait toutes les couleurs disponibles pour un t-shirt spécifique. Pour un magasin de meubles, `Toutes les images du produit` afficherait différents angles et gros plans d'un canapé.

#### **En stock seulement**

- **Ce que fait ce paramètre :** Cette option filtre les images affichées en fonction de la disponibilité du stock du produit.
- **Effet de la modification de ce paramètre :**
  - *Activé :* N'affiche que les images pour les combinaisons de produits actuellement en stock. Si une couleur spécifique est en rupture de stock, ses images associées n'apparaîtront pas.
  - *Désactivé :* Affiche toutes les images sélectionnées, quel que soit l'état du stock.
- **Valeur recommandée :** `Activé` pour éviter de montrer aux clients des images de produits qu'ils ne peuvent pas acheter immédiatement, ce qui peut entraîner de la frustration.
- **Scénario/exemple pour le marchand :** Si vous vendez des chaussures et qu'une combinaison taille/couleur particulière est en rupture de stock, l'activation de cette option empêche les clients de voir les images de cette variante spécifique, les guidant vers les options disponibles.

#### **Afficher des boîtes de couleurs au lieu d'images**

- **Ce que fait ce paramètre :** Au lieu d'afficher de petites vignettes d'images, cette option affiche des échantillons de couleurs (boîtes) pour les combinaisons de produits.
- **Effet de la modification de ce paramètre :**
  - *Activé :* Remplace les vignettes d'images par de petites boîtes de couleurs, utilisant généralement la couleur définie pour l'attribut du produit.
  - *Désactivé :* Affiche les vignettes d'images réelles.
- **Valeur recommandée :** `Désactivé` si vous souhaitez afficher des images de produits réelles. `Activé` si vos produits ont des attributs de couleur clairs et que vous préférez un aspect plus propre et plus compact pour la sélection des couleurs.
- **Scénario/exemple pour le marchand :** Pour un magasin de peinture, l'activation de cette option afficherait de petits carrés colorés représentant différentes couleurs de peinture, ce qui est plus efficace que d'afficher une petite image de chaque couleur.

#### **Conteneur principal du produit sur la liste des produits**

- **Ce que fait ce paramètre :** C'est un paramètre technique pour aider le module à identifier le conteneur principal de chaque produit sur vos pages de liste. Il nécessite un sélecteur CSS.
- **Effet de la modification de ce paramètre :** S'il est mal configuré, le module pourrait ne pas être en mesure de trouver où injecter les images supplémentaires, ou il pourrait les injecter au mauvais endroit.
- **Valeur recommandée :** Cela dépend entièrement de votre thème. Les valeurs courantes sont `.product-miniature`, `.product-container` ou `.ajax_block_product`. Vous devrez peut-être inspecter le code HTML de votre thème pour trouver le sélecteur correct.
- **Scénario/exemple pour le marchand :** Si votre thème utilise `<div class="product-item">` pour chaque produit, vous entreriez `.product-item` ici.

#### **CSS de l'image de couverture du produit**

- **Ce que fait ce paramètre :** C'est un paramètre technique pour aider le module à identifier l'élément d'image principal du produit dans chaque conteneur de produit. Il nécessite un sélecteur CSS.
- **Effet de la modification de ce paramètre :** S'il est mal configuré, le module ne pourra pas changer l'image principale du produit lorsqu'une vignette est cliquée/survolée.
- **Valeur recommandée :** Cela dépend de votre thème. Les valeurs courantes sont `.product-thumbnail`, `.img-fluid` ou `img.replace-me`. Vous devrez peut-être inspecter le code HTML de votre thème.
- **Scénario/exemple pour le marchand :** Si l'image principale de votre thème a la classe `product-image-thumb`, vous entreriez `.product-image-thumb` ici.

#### **CSS de l'ancre de l'image de couverture du produit**

- **Ce que fait ce paramètre :** C'est un paramètre technique pour aider le module à identifier le lien (balise d'ancrage) qui enveloppe l'image principale du produit. C'est important pour s'assurer que le lien fonctionne toujours correctement après le changement d'image.
- **Effet de la modification de ce paramètre :** S'il est mal configuré, cliquer sur l'image principale du produit pourrait ne pas mener à la page du produit, ou le changement d'image pourrait échouer.
- **Valeur recommandée :** Cela dépend de votre thème. Les valeurs courantes sont `.product-thumbnail a`, `.product-image a` ou `a.product-cover`. Vous devrez peut-être inspecter le code HTML de votre thème.
- **Scénario/exemple pour le marchand :** Si votre thème enveloppe l'image principale du produit dans `<a class="product-link">`, vous entreriez `a.product-link` ici.

#### **Ancre du titre du produit**

- **Ce que fait ce paramètre :** C'est un paramètre technique pour identifier le lien (balise d'ancrage) autour du titre du produit.
- **Effet de la modification de ce paramètre :** Ce paramètre aide le module à garantir que le lien du titre du produit reste fonctionnel et pointe correctement vers la page du produit.
- **Valeur recommandée :** Cela dépend de votre thème. Les valeurs courantes sont `.product-title a`, `.product-name a` ou `h3 a`. Vous devrez peut-être inspecter le code HTML de votre thème.
- **Scénario/exemple pour le marchand :** Si vos titres de produits sont enveloppés dans `<h3 class="product-name"><a href="...">`, vous entreriez `h3.product-name a` ici.

#### **Classe additionnelle pour l'ancre miniature**

- **Ce que fait ce paramètre :** Il vous permet d'ajouter une classe CSS supplémentaire aux balises d'ancrage des images miniatures affichées par le module. C'est utile pour un style personnalisé.
- **Effet de la modification de ce paramètre :** La classe spécifiée sera ajoutée au code HTML des liens d'images miniatures, vous permettant de les cibler avec des règles CSS personnalisées dans votre thème.
- **Valeur recommandée :** Laissez vide, sauf si vous avez des exigences de style personnalisées spécifiques.
- **Scénario/exemple pour le marchand :** Si vous souhaitez ajouter une bordure spéciale à vos images miniatures, vous pourriez entrer `ma-classe-miniature-personnalisee` ici, puis ajouter du CSS comme `.ma-classe-miniature-personnalisee img { border: 1px solid blue; }` à votre thème.

#### **Méthode de changement d'image**

- **Ce que fait ce paramètre :** Il contrôle la façon dont l'image principale du produit change lorsqu'un client interagit avec les vignettes supplémentaires.
- **Effet de la modification de ce paramètre :**
  - *Au clic :* L'image principale ne change que lorsqu'un client clique sur une vignette.
  - *Au survol :* L'image principale change lorsqu'un client déplace son curseur de souris sur une vignette (sans cliquer).
  - *Slider :* Le module affiche un petit slider avec des flèches de navigation, permettant aux clients de faire défiler les images. Cela implique souvent un comportement « au clic » pour les contrôles du slider.
- **Valeur recommandée :** `Au survol` pour une expérience rapide et interactive. `Au clic` si vous préférez une action utilisateur explicite. `Slider` si vous avez de nombreuses images et souhaitez une présentation plus compacte.
- **Scénario/exemple pour le marchand :** Pour un magasin de mode, `Au survol` permet aux clients de prévisualiser rapidement différents looks. Pour un produit avec de nombreuses images détaillées, `Slider` peut garder la page de liste propre tout en offrant un accès complet à tous les visuels.

#### **Images pour les combinaisons de couleurs (paramètre en double, probablement un bug ou un héritage)**

- **Ce que fait ce paramètre :** Il semble s'agir d'un doublon du paramètre « Méthode d'affichage », spécifiquement lié à l'affichage des images pour les combinaisons de couleurs.
- **Effet de la modification de ce paramètre :** Il est préférable de se fier au paramètre « Méthode d'affichage » pour cette fonctionnalité. S'il s'agit d'un contrôle distinct, il pourrait annuler ou entrer en conflit avec le paramètre « Méthode d'affichage ».
- **Valeur recommandée :** Assurer la cohérence avec le paramètre « Méthode d'affichage ».
- **Scénario/exemple pour le marchand :** Si la « Méthode d'affichage » est définie sur « Images pour les combinaisons de couleurs », ce paramètre doit également être activé ou cohérent.

#### **Images pour chaque combinaison (paramètre en double, probablement un bug ou un héritage)**

- **Ce que fait ce paramètre :** Similaire à ce qui précède, il semble s'agir d'un doublon du paramètre « Méthode d'affichage », spécifiquement lié à l'affichage des images pour toutes les combinaisons.
- **Effet de la modification de ce paramètre :** Il est préférable de se fier au paramètre « Méthode d'affichage ».
- **Valeur recommandée :** Assurer la cohérence avec le paramètre « Méthode d'affichage ».
- **Scénario/exemple pour le marchand :** Si la « Méthode d'affichage » est définie sur « Images pour chaque combinaison », ce paramètre doit également être activé ou cohérent.

#### **Toutes les images du produit (paramètre en double, probablement un bug ou un héritage)**

- **Ce que fait ce paramètre :** Similaire à ce qui précède, il semble s'agir d'un doublon du paramètre « Méthode d'affichage », spécifiquement lié à l'affichage de toutes les images du produit.
- **Effet de la modification de ce paramètre :** Il est préférable de se fier au paramètre « Méthode d'affichage ».
- **Valeur recommandée :** Assurer la cohérence avec le paramètre « Méthode d'affichage ».
- **Scénario/exemple pour le marchand :** Si la « Méthode d'affichage » est définie sur « Toutes les images du produit », ce paramètre doit également être activé ou cohérent.

#### **Tableau de référence rapide de la configuration**

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Position du module | `displayProductAdditionalInfo` | Détermine où les images supplémentaires apparaissent sur les listes de produits. |
| Configuration du module | Design du module | `Universel` | Définit le style visuel des vignettes d'images (Classique vs Moderne). |
| Configuration du module | Méthode d'affichage | `Toutes les images du produit` | Contrôle quelles images sont affichées (combinaisons de couleurs, toutes les combinaisons, ou toutes les images du produit). |
| Configuration du module | En stock seulement | `Activé` | Filtre les images pour n'afficher que celles des combinaisons de produits en stock. |
| Configuration du module | Afficher des boîtes de couleurs au lieu d'images | `Désactivé` | Remplace les vignettes d'images par des échantillons de couleurs si activé. |
| Configuration du module | Conteneur principal du produit sur la liste des produits | `.product-miniature` (ou spécifique au thème) | Sélecteur CSS pour le bloc produit principal sur les pages de liste. |
| Configuration du module | CSS de l'image de couverture du produit | `.product-thumbnail` (ou spécifique au thème) | Sélecteur CSS pour l'élément d'image principal du produit. |
| Configuration du module | CSS de l'ancre de l'image de couverture du produit | `.product-thumbnail a` (ou spécifique au thème) | Sélecteur CSS pour le lien enveloppant l'image principale du produit. |
| Configuration du module | Ancre du titre du produit | `h3 a` (ou spécifique au thème) | Sélecteur CSS pour le lien enveloppant le titre du produit. |
| Configuration du module | Classe additionnelle pour l'ancre miniature | Laisser vide | Ajoute une classe CSS personnalisée aux liens d'images miniatures pour le style. |
| Configuration du module | Méthode de changement d'image | `Au survol` | Définit comment l'image principale change (clic, survol ou slider). |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Les images supplémentaires n'apparaissent pas sur mes listes de produits.**

- **R :** Tout d'abord, vérifiez la configuration de votre module :
  - Assurez-vous que la « Position du module » est définie sur un hook que votre thème rend réellement (par exemple, `displayProductAdditionalInfo`). Si votre thème est fortement personnalisé, vous devrez peut-être essayer différentes positions ou consulter un développeur.
  - Vérifiez les paramètres « Conteneur principal du produit sur la liste des produits », « CSS de l'image de couverture du produit », « CSS de l'ancre de l'image de couverture du produit » et « Ancre du titre du produit ». Ce sont des sélecteurs CSS cruciaux qui doivent correspondre à la structure HTML de votre thème. Utilisez les outils de développement de votre navigateur (F12) pour inspecter les éléments de votre page de catégorie et trouver les classes/ID corrects.
  - Assurez-vous que les produits ont bien plusieurs images téléchargées dans leurs paramètres de produit dans le Back Office.
- **R :** Videz le cache de votre PrestaShop : Allez dans **Paramètres avancés > Performances**, et cliquez sur « Vider le cache » en haut à droite. Videz également le cache de votre navigateur.

**Q2 : Les images apparaissent, mais elles ne changent pas lorsque je survole/clique.**

- **R :** Cela indique généralement un problème avec les sélecteurs CSS pour l'image principale du produit ou son conteneur.
  - Vérifiez à nouveau « CSS de l'image de couverture du produit » et « CSS de l'ancre de l'image de couverture du produit ». Ceux-ci doivent cibler précisément l'image principale et son lien d'enveloppement.
  - Assurez-vous qu'il n'y a pas d'erreurs JavaScript sur votre page qui pourraient empêcher l'exécution du script du module. Vérifiez la console de développement de votre navigateur (F12 > onglet Console).
  - Si vous avez d'autres modules qui modifient les listes de produits, il pourrait y avoir un conflit. Essayez de désactiver temporairement d'autres modules front-office pour isoler le problème.

**Q3 : Les images semblent déformées ou le style est incorrect.**

- **R :**
  - Essayez de changer le paramètre « Design du module » entre `Thème classique` et `Universel` pour voir si l'un s'intègre mieux à votre thème.
  - Votre thème pourrait avoir des règles CSS conflictuelles. Vous pouvez utiliser le paramètre « Classe additionnelle pour l'ancre miniature » pour ajouter une classe personnalisée, puis utiliser du CSS personnalisé dans votre thème pour annuler les styles conflictuels.
  - Assurez-vous que vos images de produits téléchargées sont de qualité et de rapport d'aspect cohérents.

**Q4 : J'utilise un thème personnalisé et le module ne semble pas fonctionner du tout.**

- **R :** Les thèmes personnalisés utilisent souvent des structures HTML et des classes CSS différentes des thèmes PrestaShop par défaut.
  - Vous devrez presque certainement ajuster les sélecteurs CSS pour « Conteneur principal du produit sur la liste des produits », « CSS de l'image de couverture du produit », « CSS de l'ancre de l'image de couverture du produit » et « Ancre du titre du produit » pour qu'ils correspondent au balisage spécifique de votre thème. Cela nécessite généralement une connaissance de base de l'inspection HTML/CSS à l'aide des outils de développement du navigateur.
  - Votre thème personnalisé pourrait ne pas appeler les hooks PrestaShop standard que le module utilise. Vous devrez peut-être ajouter manuellement les appels de hook du module aux fichiers `.tpl` de votre thème (consultez le développeur de votre thème ou un développeur PrestaShop pour cela).

**Q5 : Le module ralentit la vitesse de chargement de ma page.**

- **R :** Bien que le module soit optimisé, l'affichage de nombreuses images supplémentaires peut naturellement augmenter le temps de chargement de la page.
  - Assurez-vous que vos images de produits sont optimisées pour le web (compressées, dimensions appropriées).
  - Envisagez d'utiliser l'option « En stock seulement » pour réduire le nombre d'images chargées pour les articles en rupture de stock.
  - Si vous avez de nombreuses images par produit, envisagez d'utiliser la méthode `Slider`, qui charge souvent les images plus efficacement ou de manière paresseuse.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de la structure technique du module « Images de produits sur les listes de produits », destinée aux développeurs, webmasters et agences techniques.

### 4.1 Aperçu de l'architecture

Le module `productlistpics` est principalement un module de fonctionnalités front-office conçu pour injecter des fonctionnalités d'images de produits supplémentaires dans les modèles de listes de produits existants. Il exploite le système de hooks de PrestaShop pour rendre son contenu et utilise JavaScript pour gérer le changement dynamique d'images (survol/clic) ou la fonctionnalité de slider. La configuration est gérée via la méthode standard `getContent()` dans la classe principale du module, stockant les paramètres dans `ps_configuration`. Le module n'introduit pas de tables de base de données personnalisées ni d'entités `ObjectModel` complexes.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient **pas** de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la logique est encapsulée dans la classe principale du module et ses modèles et actifs associés.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne contient **pas** de classes personnalisées ou d'entités `ObjectModel` dans le répertoire `classes/`. Toute la logique principale réside dans `productlistpics.php`.

### 4.4 Actifs JavaScript (`views/js/`)

Le module inclut plusieurs fichiers JavaScript, principalement pour gérer le changement d'images et la fonctionnalité de slider.

- `productlistpics/js/owl-carousel/owl.carousel.js` :
  - **Portée :** Front-office.
  - **Description :** Il s'agit de la bibliothèque principale Owl Carousel, un plugin jQuery populaire et tactile pour les carrousels réactifs. Il fournit la fonctionnalité fondamentale pour créer des sliders d'images.
- `productlistpics/js/owl-carousel/owl.run.js` :
  - **Portée :** Front-office.
  - **Description :** Ce script contient probablement le code d'initialisation et de configuration des instances d'Owl Carousel utilisées par le module. Il configure le comportement du slider, la réactivité et les options de navigation en fonction des paramètres du module.
- `productlistpics/js/plp-replacement.js` :
  - **Portée :** Front-office.
  - **Description :** Ce script est probablement responsable de la logique principale de remplacement de l'image principale du produit lorsqu'une vignette est interagie. Il écoute les événements (clic/survol) sur les vignettes générées et met à jour les attributs `src` et `srcset` de l'image principale du produit, potentiellement aussi en mettant à jour le `href` de la balise d'ancrage de l'image principale.
- `productlistpics/js/productlistpics-mouseover.js` :
  - **Portée :** Front-office.
  - **Description :** Ce script implémente spécifiquement la méthode de changement d'image « Au survol ». Il attache des écouteurs d'événements `mouseover` et `mouseout` aux ancres d'images miniatures pour déclencher le remplacement de l'image principale.
- `productlistpics/js/productlistpics.js` :
  - **Portée :** Front-office.
  - **Description :** Il s'agit probablement du point d'entrée JavaScript principal du module pour le front-office. Il pourrait gérer la méthode de changement d'image « Au clic », la manipulation générale du DOM liée à l'injection des vignettes, et potentiellement l'orchestration du chargement d'autres scripts en fonction de la configuration.
- `productlistpics/js/slider-productlistpics-mouseover.js` :
  - **Portée :** Front-office.
  - **Description :** Ce script combine la fonctionnalité de slider avec le changement d'image basé sur le survol. Il initialiserait probablement Owl Carousel, puis ajouterait des écouteurs de survol aux éléments du slider pour mettre à jour l'image principale du produit.
- `productlistpics/js/slider-productlistpics.js` :
  - **Portée :** Front-office.
  - **Description :** Ce script intègre le slider Owl Carousel avec le changement d'image basé sur le clic. Il initialise le slider et gère les clics sur les éléments du slider pour mettre à jour l'image principale du produit.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module inclut plusieurs fichiers CSS pour styliser les éléments injectés et le carrousel Owl.

- `productlistpics/css.css` :
  - **Portée :** Front-office.
  - **Description :** Style général pour les éléments du module, tels que le conteneur pour les images supplémentaires, le dimensionnement des vignettes et la mise en page de base.
- `productlistpics/js/owl-carousel/owl.carousel.css` :
  - **Portée :** Front-office.
  - **Description :** Styles de base pour le plugin Owl Carousel, définissant la structure et l'apparence par défaut du slider.
- `productlistpics/js/owl-carousel/owl.theme.css` :
  - **Portée :** Front-office.
  - **Description :** Thème par défaut pour Owl Carousel, fournissant un style visuel pour les boutons de navigation, les points et l'esthétique globale du slider.
- `productlistpics/js/owl-carousel/owl.transitions.css` :
  - **Portée :** Front-office.
  - **Description :** CSS pour divers effets de transition utilisés par Owl Carousel (par exemple, fondu, glissement).
- `productlistpics/productlistpics-classic.css` :
  - **Portée :** Front-office.
  - **Description :** Règles de style spécifiques appliquées lorsque l'option de conception « Thème classique » est sélectionnée dans la configuration du module. Cela cible les thèmes PrestaShop plus anciens ou les thèmes imitant l'apparence classique.
- `productlistpics/productlistpics.css` :
  - **Portée :** Front-office.
  - **Description :** Style principal du module, contenant probablement des règles pour l'option de conception « Universel » et des annulations ou améliorations générales.

**Sélecteurs de classe CSS clés que les développeurs peuvent surcharger :**

- `.productlistpics-container` : Le conteneur principal pour les images supplémentaires.
- `.productlistpics-thumb` : Conteneurs de vignettes individuels.
- `.productlistpics-thumb img` : L'image réelle dans la vignette.
- `.owl-carousel`, `.owl-item`, `.owl-nav`, `.owl-dots` : Sélecteurs Owl Carousel standard pour la personnalisation du slider.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module utilise des modèles Smarty pour rendre son contenu dans divers hooks PrestaShop.

- **Modèles de hook (`views/templates/hook/`)** :
  - `productlistpics/header.tpl` :
    - **Hook :** `displayHeader` (ou similaire, généralement enregistré dans `install()`).
    - **Sortie :** Ce modèle est responsable de l'inclusion des actifs CSS et JavaScript nécessaires au fonctionnement du module sur le front-office. Il charge conditionnellement les scripts en fonction de la « Méthode de changement d'image » choisie (par exemple, `owl.carousel.js`, `productlistpics-mouseover.js`, `slider-productlistpics.js`).
  - `productlistpics/html.tpl` :
    - **Hook :** C'est un modèle générique qui peut être inclus par d'autres modèles ou utilisé pour des blocs de contenu spécifiques. Son utilisation exacte dépend de la façon dont le fichier PHP principal du module rend le contenu.
    - **Sortie :** Contient la structure HTML pour l'affichage des images de produits supplémentaires, y compris des boucles pour itérer sur les images et une logique conditionnelle pour afficher des boîtes de couleurs ou des vignettes d'images.
  - `productlistpics/productFooter.tpl` :
    - **Hook :** `displayFooterProduct` (tel que configuré dans « Position du module »).
    - **Sortie :** Rend les images de produits supplémentaires dans la section du pied de page d'un bloc produit sur les pages de liste. Il inclut probablement `html.tpl` ou une logique similaire.
  - `productlistpics/productPage.tpl` :
    - **Hook :** Ce modèle est probablement utilisé pour des hooks comme `displayProductAdditionalInfo`, `displayAfterProductThumbs`, `displayProductDeliveryTime`, `displayProductListReviews` (tel que configuré dans « Position du module »).
    - **Sortie :** Rend les images de produits supplémentaires dans le hook de liste de produits spécifié. Il contient la logique principale pour générer les vignettes d'images ou les boîtes de couleurs et configurer les attributs de données nécessaires à l'interaction JavaScript.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** :
  Le module ne crée **pas** de tables de base de données personnalisées. Tous ses paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide de clés telles que `PLP_TYPE`, `PLP_INSTOCK`, `PLP_METHOD`, `PLP_SWITCH`, `PLP_DESIGN`, `PLP_POSITION`, et diverses clés de sélecteur CSS (`pls_product_miniature`, `pls_product_miniature_img`, etc.).
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Injecte les actifs CSS et JavaScript requis par le module. |
| `displayProductAdditionalInfo` | Dans le bloc miniature du produit, souvent sous l'image principale ou le titre. | Rend les vignettes/slider d'images de produits supplémentaires. |
| `displayAfterProductThumbs` | Après les vignettes de l'image principale du produit (si présentes). | Rend les vignettes/slider d'images de produits supplémentaires. |
| `displayFooterProduct` | Dans la zone du pied de page de chaque bloc miniature du produit. | Rend les vignettes/slider d'images de produits supplémentaires. |
| `displayProductDeliveryTime` | Près des informations de délai de livraison du produit dans la miniature du produit. | Rend les vignettes/slider d'images de produits supplémentaires. |
| `displayProductListReviews` | Près des étoiles/du nombre d'avis sur le produit dans la miniature du produit. | Rend les vignettes/slider d'images de produits supplémentaires. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et le support officiel du module « Images de produits sur les listes de produits », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
