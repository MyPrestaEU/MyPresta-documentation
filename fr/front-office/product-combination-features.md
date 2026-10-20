---
title: "Fonctionnalités des combinaisons de produits - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Fonctionnalités des combinaisons de produits' par MyPresta.eu."
sidebar:
  label: "Fonctionnalités des combinaisons de produits - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Product combination features sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-combination-features.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/product-combination-features/)
>
> ---


# Fonctionnalités des combinaisons de produits

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module « Fonctionnalités des combinaisons de produits ». Vous pouvez y accéder en naviguant vers **Modules > Gestionnaire de modules**, en recherchant « Fonctionnalités des combinaisons de produits » et en cliquant sur « Configurer ».

#### **Activer les caractéristiques pour les combinaisons**

-   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité principale d'attribution de caractéristiques uniques aux combinaisons de produits.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé :* Vous verrez une nouvelle section sur vos pages d'édition de produit (sous l'onglet « Modules ») où vous pourrez attribuer des caractéristiques spécifiques et leurs valeurs à chaque combinaison. Lorsque les clients sélectionnent une combinaison sur le front office, la fiche technique du produit se mettra à jour dynamiquement pour afficher ces caractéristiques spécifiques à la combinaison.
    -   *Lorsqu'il est désactivé :* La section de gestion des caractéristiques de combinaison n'apparaîtra pas sur les pages d'édition de produit, et le front office reviendra à n'afficher que les caractéristiques du produit principal, quelle que soit la combinaison sélectionnée.
-   **Valeur recommandée :** **Activé** (si vous souhaitez utiliser la fonction principale du module).
-   **Scénario / exemple marchand :** Si vous vendez des t-shirts et que vous voulez « Matière : 100% Coton » pour le t-shirt blanc et « Matière : 50% Coton, 50% Polyester » pour le t-shirt gris, vous *devez* activer cette option.

#### **Classe CSS de la fiche technique**

-   **Ce que fait ce paramètre :** Cela vous permet de spécifier une classe CSS ou un ID d'élément HTML que le module doit cibler lors de la mise à jour de la section des caractéristiques sur la page du produit. C'est crucial pour que le module identifie correctement où afficher les caractéristiques spécifiques à la combinaison dans votre thème.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est correctement défini :* Le module trouvera l'élément spécifié et insérera ou mettra à jour dynamiquement les caractéristiques de la combinaison à l'intérieur de celui-ci.
    -   *Lorsqu'il est mal défini ou laissé vide :* Les caractéristiques de la combinaison pourraient ne pas apparaître sur le front office, ou elles pourraient apparaître à un endroit inattendu, car le module ne saura pas où les placer.
-   **Valeur recommandée :** Cela dépend entièrement de votre thème PrestaShop. Une classe courante est `.product-features` ou `.data-sheet`. Vous devrez peut-être inspecter le code HTML de votre page produit pour trouver le sélecteur correct. En cas de doute, consultez le développeur de votre thème ou un webmaster.
-   **Scénario / exemple marchand :** Votre thème affiche les caractéristiques du produit dans une `div` avec la classe `product-specifications`. Vous entreriez `.product-specifications` ici.

#### **Flux de travail**

-   **Ce que fait ce paramètre :** Cela contrôle la façon dont le module gère les caractéristiques lorsqu'une combinaison est sélectionnée.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est défini sur « Ajouter » :* Les caractéristiques spécifiques à la combinaison seront *ajoutées* aux caractéristiques du produit principal. Ainsi, vous verrez à la fois les caractéristiques générales du produit et les caractéristiques uniques de la combinaison.
    -   *Lorsqu'il est défini sur « Remplacer » :* Les caractéristiques spécifiques à la combinaison *remplaceront* les caractéristiques du produit principal. Seules les caractéristiques pertinentes pour la combinaison sélectionnée seront affichées.
-   **Valeur recommandée :** **Remplacer** dans la plupart des cas, car cela fournit les informations les plus précises. Choisissez « Ajouter » si vous avez des caractéristiques générales qui s'appliquent à toutes les combinaisons, plus des caractéristiques spécifiques.
-   **Scénario / exemple marchand :**
    -   *Remplacer :* Pour un ordinateur portable, vous pourriez vouloir que « Processeur : i7 », « RAM : 16 Go » remplace complètement « Processeur : i5 », « RAM : 8 Go » lorsqu'un client sélectionne la combinaison i7/16 Go.
    -   *Ajouter :* Pour un t-shirt, vous pourriez toujours vouloir afficher « Marque : MaMarque » (caractéristique générale), mais ensuite *ajouter* « Matière : Coton Biologique » lorsqu'une combinaison spécifique est choisie.

#### **Activer les descriptions pour les combinaisons**

-   **Ce que fait ce paramètre :** Cela active ou désactive la possibilité d'attribuer des descriptions uniques à chaque combinaison de produit.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé :* Un nouveau champ apparaîtra sur vos pages d'édition de produit (sous l'onglet « Modules ») vous permettant de saisir une description spécifique pour chaque combinaison. Lorsque les clients sélectionnent une combinaison, cette description remplacera dynamiquement la description du produit principal.
    -   *Lorsqu'il est désactivé :* Le champ de description de la combinaison n'apparaîtra pas, et le front office affichera toujours la description du produit principal.
-   **Valeur recommandée :** **Activé** (si vous avez besoin de descriptions spécifiques aux combinaisons).
-   **Scénario / exemple marchand :** Vous vendez des bijoux personnalisés. Un produit « Bague en argent » peut avoir une combinaison « Gravé : Oui ». Vous pourriez utiliser une description de combinaison pour expliquer le processus de gravure et les limites de caractères, ce qui n'est pas pertinent pour la combinaison « Gravé : Non ».

#### **Classe CSS / ID d'objet de la description**

-   **Ce que fait ce paramètre :** Similaire à la « Classe CSS de la fiche technique », cela indique au module quel élément HTML de votre page produit contient la description du produit principal qui doit être remplacée par la description spécifique à la combinaison.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est correctement défini :* Le module trouvera l'élément spécifié et mettra à jour dynamiquement son contenu avec la description de la combinaison.
    -   *Lorsqu'il est mal défini ou laissé vide :* La description de la combinaison pourrait ne pas apparaître, ou elle pourrait apparaître à un endroit inattendu.
-   **Valeur recommandée :** Cela dépend de votre thème. Les sélecteurs courants sont `.product-description`, `#description_short` ou `#product-description-short`. Vous devrez inspecter le code HTML de votre page produit.
-   **Scénario / exemple marchand :** Votre thème utilise une `div` avec l'ID `product-description-full` pour la description principale. Vous entreriez `#product-description-full` ici.

#### **Activer le méta-titre pour les combinaisons**

-   **Ce que fait ce paramètre :** Cela active ou désactive la possibilité de définir un méta-titre unique pour chaque combinaison de produit. Ce méta-titre est ce qui apparaît dans l'onglet du navigateur et est utilisé par les moteurs de recherche.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé :* Un nouveau champ apparaîtra sur vos pages d'édition de produit (sous l'onglet « Modules ») vous permettant de saisir un méta-titre spécifique pour chaque combinaison. Lorsqu'un client sélectionne une combinaison, le titre de l'onglet du navigateur se mettra à jour dynamiquement.
    -   *Lorsqu'il est désactivé :* Le champ de méta-titre de la combinaison n'apparaîtra pas, et l'onglet du navigateur affichera toujours le méta-titre du produit principal.
-   **Valeur recommandée :** **Activé** (si vous souhaitez améliorer le SEO pour des combinaisons spécifiques ou fournir des titres d'onglet de navigateur plus clairs).
-   **Scénario / exemple marchand :** Pour un produit « Smartphone », vous pourriez avoir une combinaison « Couleur : Bleu, Stockage : 128 Go ». Vous pourriez définir son méta-titre sur « Smartphone Bleu 128 Go - [Nom de votre boutique] » pour une meilleure visibilité dans les moteurs de recherche.

#### **Mode de titre par défaut**

-   **Ce que fait ce paramètre :** Cela définit la façon dont le méta-titre de la combinaison est construit si vous n'en définissez pas explicitement un pour une combinaison, ou si vous souhaitez combiner le titre du produit avec les attributs de la combinaison.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est défini sur « Nom du produit + nom de la combinaison » :* Le méta-titre sera le nom du produit principal suivi des noms d'attributs de la combinaison sélectionnée (par exemple, « T-Shirt - Rouge, Grand »).
    -   *Lorsqu'il est défini sur « Nom de la combinaison + nom du produit » :* Le méta-titre sera les noms d'attributs de la combinaison sélectionnée suivis du nom du produit principal (par exemple, « Rouge, Grand - T-Shirt »).
    -   *Lorsqu'il est défini sur « Nom de la combinaison » :* Seuls les noms d'attributs de la combinaison seront utilisés (par exemple, « Rouge, Grand »).
    -   *Lorsqu'il est défini sur « Nom du produit » :* Le méta-titre sera toujours le nom du produit principal, ignorant les combinaisons.
-   **Valeur recommandée :** **« Nom du produit + nom de la combinaison »** ou **« Nom de la combinaison + nom du produit »** pour un bon équilibre entre l'identité du produit et la spécificité de la combinaison.
-   **Scénario / exemple marchand :** Vous vendez des chaussures. Si un client sélectionne « Taille 44, Couleur Noir », et que « Nom du produit + nom de la combinaison » est choisi, le titre devient « Chaussures de course - Taille 44, Noir ».

#### **Séparateur de titre**

-   **Ce que fait ce paramètre :** Cela vous permet de définir le caractère ou la chaîne de caractères utilisée pour séparer les différentes parties du méta-titre généré dynamiquement (par exemple, entre le nom du produit et le nom de la combinaison).
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est défini sur « - » :* Le titre pourrait ressembler à « Nom du produit - Combinaison ».
    -   *Lorsqu'il est défini sur « | » :* Le titre pourrait ressembler à « Nom du produit | Combinaison ».
    -   *Lorsqu'il est laissé vide :* Les parties du titre pourraient s'afficher sans séparateur clair.
-   **Valeur recommandée :** **-** (tiret) ou **|** (barre verticale) sont des séparateurs courants et clairs.
-   **Scénario / exemple marchand :** Si votre mode de titre par défaut est « Nom du produit + nom de la combinaison » et que le séparateur est défini sur « | », un titre pourrait devenir « Mon super T-Shirt | Rouge, Grand ».

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Ce module ne crée pas d'écrans d'administration de haut niveau dédiés. Au lieu de cela, il s'intègre directement à la **Page d'édition de produit** existante dans votre Back Office PrestaShop.

-   **Nom de l'écran et emplacement du menu :**

    -   Naviguez vers **Catalogue > Produits**.
    -   Modifiez un produit existant ou créez-en un nouveau.
    -   Sur la page d'édition du produit, cliquez sur l'onglet **« Modules »**.
    -   Vous trouverez une nouvelle section intitulée **« Fonctionnalités des combinaisons de produits »** (ou similaire, selon la version/traduction du module).
-   **Actions et paramètres disponibles :**

    -   Dans cette section, vous verrez une liste de toutes les combinaisons configurées pour le produit actuel.
    -   Pour chaque combinaison, vous aurez des champs pour :
        -   **Attribuer des caractéristiques :** Vous pouvez sélectionner des caractéristiques existantes et leurs valeurs, ou même créer de nouvelles valeurs de caractéristiques, spécifiquement pour cette combinaison. Le module prend en charge les multi-caractéristiques, ce qui signifie qu'une combinaison peut avoir plusieurs valeurs pour la même caractéristique (par exemple, « Matière : Coton, Matière : Spandex »).
        -   **Saisir la description de la combinaison :** Un éditeur de texte riche (comme l'éditeur de description standard de PrestaShop) sera disponible pour saisir une description unique pour cette combinaison.
        -   **Saisir le méta-titre de la combinaison :** Un champ de texte pour saisir un méta-titre unique pour cette combinaison.
    -   **Enregistrement des modifications :** N'oubliez pas de cliquer sur le bouton principal « Enregistrer » pour le produit afin d'appliquer toutes les modifications spécifiques à la combinaison.
-   **Effet des modifications :**

    -   Toutes les caractéristiques, descriptions ou méta-titres que vous définissez ici seront stockés dans la base de données et affichés dynamiquement sur la page produit du front office lorsque la combinaison correspondante est sélectionnée par un client.
    -   Si vous supprimez une combinaison, ses caractéristiques, descriptions et méta-titres associés seront également supprimés.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**

    1.  Tout d'abord, créez votre produit et ses combinaisons comme d'habitude dans PrestaShop (sous l'onglet « Combinaisons »).
    2.  Une fois les combinaisons créées, accédez à l'onglet **« Modules »** sur la page d'édition du produit.
    3.  Pour chaque combinaison, attribuez soigneusement les caractéristiques pertinentes, rédigez une description spécifique et définissez un méta-titre optimisé.
    4.  Enregistrez le produit.
    5.  Testez toujours sur le front office pour vous assurer que les caractéristiques, descriptions et titres se mettent à jour correctement lorsque les combinaisons sont sélectionnées.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer les caractéristiques pour les combinaisons | Activé | Interrupteur principal pour les caractéristiques de combinaison. |
| Configuration du module | Classe CSS de la fiche technique | `.product-features` (dépend du thème) | Sélecteur CSS pour l'affichage des caractéristiques de combinaison. |
| Configuration du module | Flux de travail | Remplacer | Comment les caractéristiques de combinaison interagissent avec les caractéristiques du produit principal (ajouter ou remplacer). |
| Configuration du module | Activer les descriptions pour les combinaisons | Activé | Interrupteur principal pour les descriptions de combinaison. |
| Configuration du module | Classe CSS / ID d'objet de la description | `#product-description-short` (dépend du thème) | Sélecteur CSS pour l'affichage des descriptions de combinaison. |
| Configuration du module | Activer le méta-titre pour les combinaisons | Activé | Interrupteur principal pour les méta-titres de combinaison. |
| Configuration du module | Mode de titre par défaut | Nom du produit + nom de la combinaison | Comment les méta-titres sont générés s'ils ne sont pas explicitement définis. |
| Configuration du module | Séparateur de titre | `-` | Caractère utilisé pour séparer les parties du méta-titre. |
| Page d'édition du produit > Onglet Modules | Attribuer des caractéristiques par combinaison | N/A | Attribuer des caractéristiques et des valeurs uniques à chaque combinaison. |
| Page d'édition du produit > Onglet Modules | Description de la combinaison | N/A | Saisir une description unique en texte riche pour chaque combinaison. |
| Page d'édition du produit > Onglet Modules | Méta-titre de la combinaison | N/A | Saisir un méta-titre unique pour chaque combinaison. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : Mes caractéristiques/descriptions de combinaison n'apparaissent pas sur la page produit.**
R :

1.  **Vérifiez la configuration du module :** Assurez-vous que « Activer les caractéristiques pour les combinaisons » et/ou « Activer les descriptions pour les combinaisons » sont activés dans la configuration du module.
2.  **Vérifiez les sélecteurs CSS :** Les paramètres « Classe CSS de la fiche technique » et « Classe CSS / ID d'objet de la description » sont cruciaux. Ceux-ci doivent correspondre exactement à la classe CSS ou à l'ID des éléments de votre thème où les caractéristiques/description sont affichées. Utilisez les outils de développement de votre navigateur (F12) pour inspecter votre page produit et trouver les sélecteurs corrects. En cas de doute, consultez le développeur de votre thème.
3.  **Videz le cache PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ». Parfois, un ancien contenu mis en cache empêche l'affichage de la nouvelle sortie du module.
4.  **Vérifiez les paramètres du produit :** Assurez-vous d'avoir réellement attribué des caractéristiques/descriptions aux combinaisons spécifiques sur la page d'édition du produit sous l'onglet « Modules ».

**Q : Les caractéristiques/descriptions de combinaison apparaissent, mais elles semblent sans style ou mal placées.**
R : Il s'agit généralement d'un conflit CSS avec votre thème.

1.  **Inspectez avec les outils du navigateur :** Utilisez F12 pour voir quelles règles CSS sont appliquées à la sortie du module.
2.  **Ajustez la classe CSS :** Si la sortie du module est enveloppée dans une `div` générique, vous devrez peut-être ajuster la « Classe CSS de la fiche technique » ou la « Classe CSS / ID d'objet de la description » à un conteneur plus spécifique que votre thème stylise déjà.
3.  **CSS personnalisé :** Vous devrez peut-être ajouter du CSS personnalisé à la feuille de style de votre thème (ou via un module CSS personnalisé) pour styliser les caractéristiques/descriptions de combinaison afin qu'elles correspondent à l'apparence de votre thème.

**Q : Mes méta-titres de combinaison ne changent pas dans l'onglet du navigateur.**
R :

1.  **Activez le paramètre :** Assurez-vous que « Activer le méta-titre pour les combinaisons » est activé dans la configuration du module.
2.  **Définissez les titres :** Assurez-vous d'avoir saisi des méta-titres spécifiques pour vos combinaisons sur la page d'édition du produit.
3.  **Comportement du navigateur :** Certains navigateurs peuvent ne pas mettre à jour immédiatement le titre de l'onglet pour les onglets déjà ouverts. Essayez d'ouvrir la page produit dans un nouvel onglet ou de vider le cache de votre navigateur.
4.  **Implications SEO :** Bien que le module mette à jour le titre côté client, pour que les moteurs de recherche reprennent ces titres spécifiques aux combinaisons, ils doivent pouvoir explorer et indexer le contenu généré dynamiquement. Assurez-vous que votre site est explorable et déterminez si ces titres dynamiques sont vraiment bénéfiques pour votre stratégie SEO par rapport aux titres de produits statiques.

**Q : Puis-je utiliser ce module avec des boutiques multilingues ?**
R : Oui, le module prend entièrement en charge le multilingue. Lorsque vous modifiez les caractéristiques, descriptions ou méta-titres de combinaison sur la page produit, vous verrez le sélecteur de langue standard de PrestaShop, vous permettant de saisir du contenu pour chaque langue.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Fonctionnalités des combinaisons de produits » (`combfeat`) étend la gestion des produits de base de PrestaShop en injectant des champs et une logique personnalisés dans la page d'édition de produit du Back Office et en mettant à jour dynamiquement le contenu du Front Office en fonction des combinaisons de produits sélectionnées. Il utilise le système de hooks de PrestaShop pour s'intégrer de manière transparente sans modifier les fichiers du cœur. Le module fonctionne principalement via JavaScript sur le front-end pour les mises à jour dynamiques et PHP sur le back-end pour la configuration et la gestion des données. Il n'introduit pas de nouvelles tables de base de données mais stocke ses données dans les structures PrestaShop existantes (probablement `ps_product_attribute_feature` pour les caractéristiques et `ps_product_attribute_lang` pour les descriptions/titres, ou `ps_configuration` pour les paramètres du module).

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs d'administration Front-Office ou Back-Office dédiés. Sa logique d'affichage et d'enregistrement des données de combinaison est intégrée directement dans le fichier principal du module `combfeat.php` et via JavaScript.

### 4.3 Classes et modèles de base (`classes/`)

Ce module ne définit pas de classes personnalisées dans le répertoire `classes/`. Sa logique de base est contenue dans le fichier principal `combfeat.php`, interagissant directement avec les `ObjectModel`s `Product` et `Combination` (ProductAttribute) de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`combfeat/views/js/acplt.js`**

    -   **Portée :** Probablement Back-office (page produit admin).
    -   **Responsabilité :** Ce script semble être une bibliothèque d'autocomplétion personnalisée ou un composant utilisé pour sélectionner les caractéristiques et leurs valeurs pour les combinaisons. Il gérerait les requêtes AJAX pour récupérer les caractéristiques et les valeurs disponibles, et gérerait l'interface utilisateur pour les ajouter/supprimer d'une combinaison.
    -   **Interactions clés :** Écouteurs d'événements pour les champs de saisie, appels AJAX à un hook de module ou à un contrôleur admin pour les données, manipulation du DOM pour afficher les suggestions et les éléments sélectionnés.
-   **`combfeat/views/js/admin-combfeat.js`**

    -   **Portée :** Back-office (page produit admin, onglet « Modules »).
    -   **Responsabilité :** C'est le script principal de la fonctionnalité du module dans la page d'édition de produit du Back Office de PrestaShop. Il initialise les champs de caractéristiques, de description et de méta-titre de la combinaison. Il écoute probablement les changements dans la sélection de combinaison (le cas échéant) et gère l'affichage et l'enregistrement des données pour chaque combinaison.
    -   **Interactions clés :** Manipulation du DOM pour injecter des champs personnalisés, écouteurs d'événements pour les changements de saisie, potentiellement des appels AJAX pour enregistrer des données spécifiques à la combinaison.
-   **`combfeat/views/js/combfeat-append.js`**

    -   **Portée :** Front-office (page produit).
    -   **Responsabilité :** Ce script est spécifiquement destiné à l'option de flux de travail « Ajouter ». Lorsqu'une combinaison est sélectionnée, il récupère et *ajoute* dynamiquement les caractéristiques spécifiques à la combinaison aux caractéristiques existantes du produit sur le front-end.
    -   **Interactions clés :** Écoute les événements `updateProduct` ou similaires (déclenchés par la sélection de combinaison), appels AJAX pour récupérer les données de combinaison, manipulation du DOM pour ajouter des caractéristiques à l'élément spécifié par `combfeat_ds`.
-   **`combfeat/views/js/combfeat-title.js`**

    -   **Portée :** Front-office (page produit).
    -   **Responsabilité :** Ce script gère la mise à jour dynamique du méta-titre du navigateur en fonction de la combinaison de produit sélectionnée.
    -   **Interactions clés :** Écoute les événements `updateProduct` ou similaires, récupère le méta-titre de la combinaison (personnalisé ou généré en fonction des paramètres du module) et met à jour `document.title`.
-   **`combfeat/views/js/combfeat.js`**

    -   **Portée :** Front-office (page produit).
    -   **Responsabilité :** C'est le script principal du front-office pour le module. Il orchestre l'affichage dynamique des caractéristiques et descriptions spécifiques à la combinaison. Il écoute probablement les changements dans les combinaisons de produits (par exemple, la sélection d'attributs) et déclenche des mises à jour des éléments DOM pertinents. Ce script gérerait le flux de travail « Remplacer » pour les caractéristiques et la mise à jour de la description.
    -   **Interactions clés :** Écoute les événements `updateProduct` ou similaires (par exemple, `prestashop.on('updatedProduct', ...) `), appels AJAX pour récupérer les données de combinaison, manipulation du DOM pour mettre à jour les éléments spécifiés par `combfeat_ds` et `combfeat_description`.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`combfeat/views/css/combfeat.css`**
    -   **Portée :** Front-office et Back-office.
    -   **Responsabilité :** Fournit un style de base pour les éléments injectés du module. Cela pourrait inclure le style des champs de saisie des caractéristiques/descriptions de combinaison dans le Back Office, ou pour les blocs de caractéristiques/descriptions mis à jour dynamiquement sur le Front Office.
    -   **Sélecteurs de classe CSS clés :** Cible probablement les classes utilisées par les modèles et le JavaScript du module, telles que `.combfeat-feature-list`, `.combfeat-description-wrapper`, ou des styles spécifiques pour le composant d'autocomplétion. Les développeurs pourraient avoir besoin de les remplacer dans le `custom.css` ou `theme.css` de leur thème pour une intégration parfaite.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **`combfeat/views/templates/admin/combfeat.tpl`**

    -   **Portée :** Modèle d'administration.
    -   **Responsabilité :** Ce modèle rend la section personnalisée dans l'onglet « Modules » sur la page d'édition de produit dans le Back Office. Il affiche l'interface pour gérer les caractéristiques, descriptions et méta-titres spécifiques à la combinaison. Il itère probablement sur toutes les combinaisons de produits et fournit des champs de saisie pour chacune.
    -   **Éléments clés :** Boucles pour les combinaisons, champs de saisie pour la sélection des caractéristiques (éventuellement en utilisant le composant `acplt.js`), éditeur de texte riche pour les descriptions, champ de saisie de texte pour les méta-titres.
-   **`combfeat/views/templates/hook/product-details.tpl`**

    -   **Portée :** Modèle de hook Front-office.
    -   **Responsabilité :** Ce modèle est probablement accroché à `displayProductAdditionalInfo` ou à des hooks similaires pour rendre les caractéristiques et/ou la description spécifiques à la combinaison sur la page produit du front office. Il fournit la structure HTML que `combfeat.js` et `combfeat-append.js` rempliront et mettront à jour dynamiquement.
    -   **Éléments clés :** Espaces réservés (par exemple, des `div` vides avec des ID ou des classes spécifiques) où les caractéristiques et descriptions de combinaison seront injectées par JavaScript.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module ne crée pas de nouvelles tables personnalisées. Il stocke probablement les caractéristiques spécifiques aux combinaisons en étendant la relation `ps_product_attribute_feature` ou similaire, et les descriptions/méta-titres de combinaison dans `ps_product_attribute_lang` ou une structure similaire, en les associant à `id_product_attribute` et `id_lang`.
    -   Les paramètres de configuration du module (`combfeat_ds`, `combfeat_description`, etc.) sont stockés dans la table `ps_configuration`.
-   **Table des hooks enregistrés** :

| Nom du hook | Portée | Moment d'exécution | Objectif technique |
| --- | --- | --- | --- |
| `displayHeader` | Front-office | Dans la section `<head>` de toutes les pages du front-office. | Enregistre les actifs CSS et JS du front-office (`combfeat.css`, `combfeat.js`, `combfeat-append.js`, `combfeat-title.js`). |
| `DisplayHeader` | Front-office | Alias pour `displayHeader`. | Identique à `displayHeader`. |
| `displayProductAdditionalInfo` | Front-office | Sur la page produit, généralement sous les informations principales du produit. | Rend le modèle `product-details.tpl`, fournissant un espace réservé pour les caractéristiques/descriptions de combinaison. |
| `ActionAdminControllerSetMedia` | Back-office | Lorsqu'un contrôleur d'administration est chargé et que ses actifs multimédias sont définis. | Enregistre les actifs CSS et JS du back-office (`combfeat.css`, `acplt.js`, `admin-combfeat.js`) pour la page d'édition de produit. |
| `ActionProductUpdate` | Back-office | Après la mise à jour d'un produit (y compris les combinaisons). | Potentiellement utilisé pour enregistrer ou synchroniser les données spécifiques à la combinaison lorsque le formulaire produit est soumis. |
| `actionProductUpdate` | Back-office | Alias pour `ActionProductUpdate`. | Identique à `ActionProductUpdate`. |
| `displayAdminProductsExtra` | Back-office | Sur la page d'édition de produit, généralement sous forme de nouvel onglet ou de nouvelle section. | Rend le modèle `admin/combfeat.tpl`, créant la section « Fonctionnalités des combinaisons de produits » sous l'onglet « Modules ». |
| `DisplayAdminProductsExtra` | Back-office | Alias pour `displayAdminProductsExtra`. | Identique à `displayAdminProductsExtra`. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Fonctionnalités des combinaisons de produits », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
