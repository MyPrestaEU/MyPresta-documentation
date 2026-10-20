---
title: "Bloc-notes de produits - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Bloc-notes de produits par MyPresta.eu."
sidebar:
  label: "Bloc-notes de produits - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Products Notepad sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/products-notepad.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/products-notepad/)
>
> ---


# Bloc-notes de produits

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour le fonctionnement général de PrestaShop. Aucune extension supplémentaire spécifique n'est nécessaire pour ce module.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Bloc-notes de produits » dans le Gestionnaire de modules. Cela vous mènera à l'écran de configuration principal.

#### Paramètres généraux

- **Ce que fait ce paramètre :** Cette section contrôle le comportement et l'affichage principaux du module Bloc-notes de produits sur votre boutique.

  - **Mémoriser les produits dans le bloc-notes :**

    - **Ce que fait ce paramètre :** Détermine si les produits qu'un client ajoute à son bloc-notes sont mémorisés d'une session de navigation à l'autre ou si le bloc-notes est vidé lorsqu'il ferme son navigateur.
    - **Effet de la modification de ce paramètre :**
      - *Lorsque activé (OUI) :* Les produits ajoutés au bloc-notes persisteront même si le client quitte votre site et y revient plus tard (par exemple, le lendemain). Cela utilise des cookies de navigateur pour stocker le contenu du bloc-notes.
      - *Lorsque désactivé (NON) :* Le bloc-notes sera vidé lorsque le client ferme son navigateur ou efface ses cookies. Chaque nouvelle session commencera avec un bloc-notes vide.
    - **Valeur recommandée :** **OUI**. Cela offre une bien meilleure expérience client, car cela permet aux clients de construire une liste au fil du temps sans perdre leur progression.
    - **Scénario/exemple pour le marchand :** Un client ajoute plusieurs articles à son bloc-notes le lundi. Si « Mémoriser les produits » est OUI, il peut revenir le mercredi et retrouver sa liste intacte. Si NON, la liste serait vide.
  - **Limiter le nombre de produits dans le bloc-notes :**

    - **Ce que fait ce paramètre :** Vous permet de définir un nombre maximum de produits qu'un client peut enregistrer dans son bloc-notes.
    - **Effet de la modification de ce paramètre :**
      - *Lorsque activé (OUI) :* Le bloc-notes n'autorisera qu'un nombre spécifié de produits. Une fois la limite atteinte, les clients ne pourront plus ajouter de produits tant qu'ils n'en auront pas supprimé d'existants.
      - *Lorsque désactivé (NON) :* Les clients peuvent ajouter un nombre illimité de produits à leur bloc-notes.
    - **Valeur recommandée :** **NON** (sauf si vous avez une raison spécifique de le limiter, comme des problèmes de performance avec des listes extrêmement longues). Autoriser un nombre illimité d'articles offre aux clients une flexibilité maximale.
    - **Scénario/exemple pour le marchand :** Si vous activez cette option et définissez la limite à 10, un client qui tente d'ajouter un 11ème produit recevra un message indiquant que le bloc-notes est plein.
  - **Valeur limite :** (N'apparaît que si « Limiter le nombre de produits dans le bloc-notes » est défini sur OUI)

    - **Ce que fait ce paramètre :** Spécifie le nombre maximum exact de produits autorisés dans le bloc-notes.
    - **Effet de la modification de ce paramètre :** Définit le plafond numérique pour le bloc-notes.
    - **Valeur recommandée :** Si vous choisissez de limiter, un nombre raisonnable comme **20-50** est souvent suffisant, équilibrant la flexibilité du client avec les performances potentielles.
    - **Scénario/exemple pour le marchand :** Si « Limiter le nombre de produits » est OUI et « Valeur limite » est 25, les clients peuvent enregistrer jusqu'à 25 produits.

#### Paramètres d'affichage

- **Ce que fait ce paramètre :** Cette section contrôle l'emplacement du bloc Bloc-notes de produits sur le front-office de votre boutique.

  - **Afficher dans la colonne de gauche :**

    - **Ce que fait ce paramètre :** Contrôle si le bloc de résumé du bloc-notes est affiché dans la colonne de gauche de votre boutique.
    - **Effet de la modification de ce paramètre :**
      - *Lorsque activé (OUI) :* Le bloc du bloc-notes apparaîtra dans la colonne de gauche sur les pages qui ont une colonne de gauche (par exemple, pages de catégorie, pages de produit, pages CMS).
      - *Lorsque désactivé (NON) :* Le bloc du bloc-notes ne sera pas affiché dans la colonne de gauche.
    - **Valeur recommandée :** **OUI** (ou colonne de droite), car les colonnes sont un endroit courant pour de tels blocs utilitaires.
    - **Scénario/exemple pour le marchand :** Un client naviguant sur une page de catégorie verra le résumé de son bloc-notes dans la barre latérale gauche, le rendant facilement accessible.
  - **Afficher dans la colonne de droite :**

    - **Ce que fait ce paramètre :** Contrôle si le bloc de résumé du bloc-notes est affiché dans la colonne de droite de votre boutique.
    - **Effet de la modification de ce paramètre :**
      - *Lorsque activé (OUI) :* Le bloc du bloc-notes apparaîtra dans la colonne de droite sur les pages qui ont une colonne de droite.
      - *Lorsque désactivé (NON) :* Le bloc du bloc-notes ne sera pas affiché dans la colonne de droite.
    - **Valeur recommandée :** **OUI** (ou colonne de gauche). Choisissez l'un ou les deux en fonction de la mise en page de votre thème et des autres modules que vous avez.
    - **Scénario/exemple pour le marchand :** Si votre thème utilise la colonne de droite pour les promotions, vous pourriez y placer le bloc-notes pour garder la colonne de gauche libre pour la navigation.
  - **Afficher dans le pied de page :**

    - **Ce que fait ce paramètre :** Contrôle si le bloc de résumé du bloc-notes est affiché dans la section du pied de page de votre boutique.
    - **Effet de la modification de ce paramètre :**
      - *Lorsque activé (OUI) :* Le bloc du bloc-notes apparaîtra en bas de chaque page, généralement dans le contenu général du pied de page.
      - *Lorsque désactivé (NON) :* Le bloc du bloc-notes ne sera pas affiché dans le pied de page.
    - **Valeur recommandée :** **NON** (sauf si votre thème a une section de pied de page très proéminente pour les blocs utilitaires). Les colonnes sont généralement plus visibles pour ce type de fonctionnalité.
    - **Scénario/exemple pour le marchand :** Si votre pied de page est déjà encombré de liens et d'informations légales, y ajouter le bloc-notes pourrait le rendre moins visible.
  - **Afficher dans l'en-tête :**

    - **Ce que fait ce paramètre :** Contrôle si le bloc de résumé du bloc-notes est affiché dans la section de l'en-tête de votre boutique.
    - **Effet de la modification de ce paramètre :**
      - *Lorsque activé (OUI) :* Le bloc du bloc-notes apparaîtra en haut de chaque page, souvent près des liens du panier ou du compte.
      - *Lorsque désactivé (NON) :* Le bloc du bloc-notes ne sera pas affiché dans l'en-tête.
    - **Valeur recommandée :** **NON** (sauf si votre thème dispose d'un espace suffisant et d'un design spécifique pour cela). Les en-têtes sont souvent réservés à la navigation critique et au panier.
    - **Scénario/exemple pour le marchand :** Une icône compacte dans l'en-tête pourrait fonctionner, mais un bloc complet pourrait encombrer l'en-tête.
  - **Afficher sur la page produit :**

    - **Ce que fait ce paramètre :** Contrôle si le bouton « Ajouter au bloc-notes » et potentiellement un petit résumé du bloc-notes sont affichés directement sur les pages de produits individuelles.
    - **Effet de la modification de ce paramètre :**
      - *Lorsque activé (OUI) :* Les clients verront le bouton « Ajouter au bloc-notes » sur chaque page produit, ce qui facilite l'enregistrement des articles pendant la navigation.
      - *Lorsque désactivé (NON) :* Le bouton « Ajouter au bloc-notes » n'apparaîtra pas sur les pages produit, rendant la fonctionnalité moins accessible.
    - **Valeur recommandée :** **OUI**. C'est un emplacement crucial pour que la fonctionnalité soit efficace.
    - **Scénario/exemple pour le marchand :** Un client consultant un produit peut l'ajouter immédiatement à son bloc-notes pour une comparaison ultérieure avec d'autres produits.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Mémoriser les produits dans le bloc-notes | OUI | Conserve les articles du bloc-notes enregistrés entre les sessions pour une meilleure UX. |
| Configuration du module | Limiter le nombre de produits dans le bloc-notes | NON | Permet un nombre illimité de produits dans le bloc-notes, maximisant le choix du client. |
| Configuration du module | Valeur limite | (N/A si la limite est NON) | Définit le nombre maximum de produits si la limitation est activée. |
| Configuration du module | Afficher dans la colonne de gauche | OUI | Affiche le résumé du bloc-notes dans la barre latérale gauche. |
| Configuration du module | Afficher dans la colonne de droite | OUI | Affiche le résumé du bloc-notes dans la barre latérale droite. |
| Configuration du module | Afficher dans le pied de page | NON | Évite d'encombrer le pied de page, moins visible. |
| Configuration du module | Afficher dans l'en-tête | NON | Évite d'encombrer l'en-tête, moins visible. |
| Configuration du module | Afficher sur la page produit | OUI | Essentiel pour que les clients puissent facilement ajouter des produits au bloc-notes. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Le bloc-notes n'apparaît pas sur ma boutique. Que dois-je faire ?**
R1 : Tout d'abord, vérifiez la configuration du module dans votre Back Office (**Modules > Gestionnaire de modules > Bloc-notes de produits > Configurer**). Assurez-vous qu'au moins une option d'affichage (par exemple, « Afficher dans la colonne de gauche » ou « Afficher sur la page produit ») est définie sur OUI. Si cela ne s'affiche toujours pas, essayez de vider votre cache PrestaShop (**Paramètres avancés > Performances > Vider le cache**). Parfois, des conflits de thème peuvent également empêcher l'affichage des modules ; basculez temporairement vers le thème PrestaShop par défaut pour exclure cette possibilité.

**Q2 : Les produits ne sont pas mémorisés dans le bloc-notes après que le client a fermé son navigateur.**
R2 : Accédez à la page de configuration du module (**Modules > Gestionnaire de modules > Bloc-notes de produits > Configurer**) et assurez-vous que le paramètre « Mémoriser les produits dans le bloc-notes » est défini sur **OUI**. Cette option utilise les cookies du navigateur pour stocker le contenu du bloc-notes, alors assurez-vous que les clients n'ont pas désactivé les cookies dans leur navigateur.

**Q3 : Le bouton « Ajouter au bloc-notes » a une apparence étrange ou n'est pas correctement stylisé sur mes pages produits.**
R3 : Il s'agit souvent d'un conflit CSS avec votre thème personnalisé. Le module fournit son propre style de base, mais les styles de votre thème peuvent le remplacer. Vous pouvez soit :
1. Contacter le développeur de votre thème pour obtenir de l'aide.
2. Utiliser l'éditeur de thème en direct de PrestaShop (si disponible dans votre version) ou les outils de développement du navigateur (F12) pour inspecter le bouton et appliquer des remplacements CSS personnalisés dans le fichier `custom.css` de votre thème.
3. Contacter le support MyPresta.eu pour obtenir des conseils.

**Q4 : Les clients peuvent-ils partager leur bloc-notes avec d'autres ?**
R4 : Non, ce module est conçu pour une utilisation individuelle par le client et n'inclut pas de fonctionnalité de partage. C'est une aide à la navigation personnelle, pas une liste de souhaits collaborative.

**Q5 : Le bloc-notes fonctionnera-t-il avec les boutiques multilingues ?**
R5 : Oui, le module est conçu pour être compatible avec les fonctionnalités multilingues de PrestaShop. Tout texte affiché par le module (comme les étiquettes de bouton ou les titres de bloc) peut être traduit via l'interface de traduction de PrestaShop (**International > Traductions > Traductions des modules installés**).

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module Bloc-notes de produits est un module PrestaShop standard suivant un modèle de type MVC. Il utilise principalement des contrôleurs frontaux pour les interactions AJAX et le rendu, et des templates Smarty pour son affichage en front-office. Il s'appuie sur les cookies du navigateur pour la persistance s'il est configuré pour mémoriser les produits. La logique principale du module réside dans `notepad.php` et ses contrôleurs frontaux associés.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :

  - `controllers/front/ajaxload.php`
    - **Nom de la classe et classe parente** : `NotepadAjaxloadModuleFrontController` étendant `ModuleFrontController`.
    - **Responsabilité** : Ce contrôleur gère toutes les requêtes AJAX liées à la fonctionnalité du bloc-notes. Il est responsable de l'ajout de produits au bloc-notes, de leur suppression et potentiellement de la mise à jour de l'affichage du bloc-notes. Il traite les données envoyées via POST ou GET et renvoie des réponses JSON au JavaScript du front-end.
  - `controllers/front/index.php`
    - **Nom de la classe et classe parente** : `NotepadIndexModuleFrontController` étendant `ModuleFrontController`.
    - **Responsabilité** : Ce contrôleur sert probablement de solution de repli ou de page dédiée au bloc-notes si une vue pleine page est implémentée. Compte tenu de la nature AJAX primaire du module, il pourrait s'agir d'un point d'entrée moins fréquemment utilisé, redirigeant ou rendant éventuellement une vue complète du bloc-notes.
- **Contrôleurs d'administration Back-Office** : Aucun. Toute la configuration est gérée via la méthode `getContent()` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)

Aucune classe `ObjectModel` personnalisée n'est définie dans ce module. Les données de produit sont probablement stockées directement dans les cookies du navigateur ou les variables de session, récupérées et traitées par la classe principale du module et les contrôleurs frontaux.

### 4.4 Actifs JavaScript (`views/js/`)

- `admin.js`
  - **Portée** : Back-office.
  - **Description** : Ce script gère probablement les interactions sur la page de configuration du module dans le Back Office de PrestaShop. Il peut gérer la visibilité des paramètres (par exemple, `notepad_limit_value` en fonction de `notepad_limit`), les soumissions de formulaires ou la validation.
- `jscolor.js`
  - **Portée** : Back-office (probablement).
  - **Description** : Une bibliothèque JavaScript tierce pour les sélecteurs de couleurs. Si le module avait des options de personnalisation des couleurs pour l'affichage du bloc-notes, ce script fournirait l'interface utilisateur pour sélectionner les couleurs dans le panneau d'administration. (Basé sur l'inventaire, il est présent mais pourrait être un vestige ou pour une utilisation future si aucun paramètre de couleur n'est actuellement exposé).
- `lib/searchTool/views/js/autocomplete.js`
  - **Portée** : Front-office (potentiellement Back-office si utilisé pour la sélection de produits).
  - **Description** : Ce script fournit une fonctionnalité d'autocomplétion, probablement pour la recherche de produits. Si le bloc-notes avait une fonctionnalité pour ajouter des produits par recherche, ou s'il fait partie d'une bibliothèque d'« outils de recherche » plus large incluse avec le module, cela gérerait les appels AJAX et l'affichage des suggestions de recherche.
- `notepad.js`
  - **Portée** : Front-office.
  - **Description** : C'est le JavaScript principal du front-office pour la fonctionnalité du bloc-notes.
    - **Écouteurs d'événements** : Lie les événements de clic aux boutons « Ajouter au bloc-notes » (par exemple, sur les pages produits, les listes de produits), aux liens/boutons « Supprimer du bloc-notes » dans le bloc du bloc-notes, et potentiellement à l'en-tête du bloc du bloc-notes lui-même pour basculer sa visibilité ou naviguer vers une vue complète.
    - **Appels AJAX** : Effectue des requêtes asynchrones vers `controllers/front/ajaxload.php` pour ajouter, supprimer ou récupérer le contenu du bloc-notes.
    - **Manipulation du DOM** : Met à jour le bloc d'affichage du bloc-notes (par exemple, le nombre de produits, la liste des produits), affiche les messages de succès/erreur et rend dynamiquement les entrées de produit dans le bloc-notes.
    - **Gestion des cookies** : Interagit avec les cookies du navigateur pour stocker et récupérer les ID de produit du bloc-notes si l'option « Mémoriser les produits » est activée.

### 4.5 Feuilles de style CSS (`views/css/`)

- `css/admincss.css`
  - **Portée** : Style du formulaire d'administration du Back-office.
  - **Description** : Styles pour la page de configuration du module dans le Back Office de PrestaShop, assurant une apparence cohérente avec le thème d'administration de PrestaShop.
- `css/css.css`
  - **Portée** : Style client du Front-office.
  - **Description** : Contient les styles principaux pour le bloc d'affichage du bloc-notes, le bouton « Ajouter au bloc-notes » et tous les éléments associés sur la boutique.
  - **Sélecteurs de classe CSS clés** : Les développeurs peuvent inspecter le HTML généré pour des classes comme `.notepad-block`, `.add-to-notepad`, `.notepad-product-item` pour remplacer les styles dans le fichier `custom.css` ou `theme.css` de leur thème.
- `lib/searchTool/views/css/autocomplete.css`
  - **Portée** : Front-office (ou Back-office si l'outil de recherche y est utilisé).
  - **Description** : Styles pour la liste déroulante des résultats de recherche d'autocomplétion, si le script `autocomplete.js` est activement utilisé pour une fonctionnalité de recherche de produits dans le module.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :
  - `extraleft.tpl`
    - **Hook** : Probablement `displayLeftColumn` ou similaire.
    - **Objectif** : Rend le bloc principal de résumé du bloc-notes qui apparaît dans la colonne de gauche. Cela affiche généralement un titre, le nombre d'articles et une brève liste ou un lien vers le bloc-notes complet.
  - `notepad.tpl`
    - **Hook** : Ceci pourrait être un template général inclus par d'autres templates ou directement accroché à `displayRightColumn`, `displayFooter` ou `displayHeader` selon la configuration. Il contient probablement la structure de base du bloc-notes.
- **Templates d'administration (`views/templates/admin/`)** : Aucun explicitement listé, la configuration est probablement gérée directement par `notepad.php` qui rend les éléments de formulaire.
- **Templates Front-office (`views/templates/front/`)** :
  - `views/addToCart.tpl`
    - **Objectif** : Ce template est rendu sur les pages produits (et potentiellement les listes de produits) pour afficher le bouton « Ajouter au bloc-notes ». Il est probablement accroché à `displayProductButtons` ou `displayProductActions`.
  - `views/selectedProducts.tpl`
    - **Objectif** : Ce template est utilisé pour afficher la liste détaillée des produits dans le bloc-notes, soit dans une popup, une page dédiée, soit dans le bloc de colonne étendu. Il itère sur les produits enregistrés dans le bloc-notes et affiche leur image, nom, prix et une option « supprimer ».
  - `lib/searchTool/views/scripts.tpl`
    - **Objectif** : Ce template inclut probablement le JavaScript et le CSS nécessaires pour la bibliothèque `searchTool`, tels que `autocomplete.js` et `autocomplete.css`, si le module utilise une fonctionnalité de recherche. Il serait accroché à `displayHeader` ou `displayFooter` pour charger ces actifs.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** : Le module ne semble pas créer de tables SQL personnalisées. Les ID de produit et les données associées pour le bloc-notes sont gérés côté client, principalement via les cookies du navigateur ou les variables de session. Les paramètres de configuration sont stockés dans `ps_configuration` (par exemple, `NOTEPAD_REMEMBER`, `NOTEPAD_LIMIT`, `NOTEPAD_LIMIT_VALUE`).
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Pour charger les actifs CSS et JS du module (par exemple, `notepad.js`, `css.css`) et potentiellement rendre un résumé compact du bloc-notes si configuré. |
| `displayLeftColumn` | Dans la barre latérale gauche des pages qui en ont une. | Pour afficher le bloc principal de résumé du bloc-notes (`extraleft.tpl`). |
| `displayRightColumn` | Dans la barre latérale droite des pages qui en ont une. | Pour afficher le bloc principal de résumé du bloc-notes (`notepad.tpl` ou similaire). |
| `displayFooter` | Dans la section du pied de page de chaque page. | Pour afficher le bloc de résumé du bloc-notes si configuré, ou pour charger le JS différé. |
| `displayProductButtons` / `displayProductActions` (ou hook de page produit similaire) | Sur la page produit, près du bouton « Ajouter au panier ». | Pour rendre le bouton « Ajouter au bloc-notes » (`views/addToCart.tpl`). |
| `actionFrontControllerSetMedia` | Avant que le contrôleur frontal ne rende sa sortie. | Pour enregistrer les fichiers CSS et JS du module pour un chargement optimal. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module Bloc-notes de produits, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
