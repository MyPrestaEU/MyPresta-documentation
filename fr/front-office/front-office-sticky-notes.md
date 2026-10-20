---
title: "Notes autocollantes du Front Office - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Notes autocollantes du Front Office par MyPresta.eu."
sidebar:
  label: "Notes autocollantes du Front Office - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Front office Sticky Notes sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/front-office-sticky-notes.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/front-office-sticky-notes/)
>
> ---


# Notes autocollantes du Front Office

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont habituellement disponibles sur tout environnement d'hébergement moderne.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur "Configurer" vous mènera à l'écran de configuration principal du module Notes autocollantes du Front Office. C'est ici que vous gérez toutes vos notes autocollantes.

La page de configuration affichera une liste de toutes les notes autocollantes que vous avez créées. À partir de là, vous pouvez :

- **Ajouter une nouvelle note autocollante :** Cliquez sur un bouton (généralement "Ajouter" ou une icône plus) pour créer une nouvelle note.
- **Modifier une note autocollante existante :** Cliquez sur une icône "Modifier" à côté d'une note dans la liste pour modifier ses paramètres.
- **Supprimer une note autocollante :** Cliquez sur une icône "Supprimer" à côté d'une note pour la retirer de votre boutique.

Lors de l'ajout ou de la modification d'une note autocollante, vous verrez généralement un formulaire avec les paramètres suivants :

- **Contenu de la note (Texte) :**

  - **Ce que fait ce paramètre :** C'est le message ou le texte réel qui apparaîtra à l'intérieur de votre note autocollante. Vous pouvez utiliser des balises HTML de base (comme `<b>` pour le gras, `<i>` pour l'italique, `<br>` pour les sauts de ligne, ou `<a>` pour les liens) pour formater votre texte et inclure des liens cliquables.
  - **Effet de la modification de ce paramètre :** Le texte que vous saisissez ici sera affiché à vos clients.
  - **Valeur recommandée :** Restez concis et percutant. Par exemple, "Stock limité !", "Nouveautés !", "Livraison gratuite à partir de 75 € !".
  - **Scénario / exemple pour le marchand :** Vous souhaitez annoncer une vente flash. Vous saisiriez : `<b>Vente Flash !</b> 20% de réduction sur toutes les robes ! <a href="/20-off-dresses">Achetez maintenant !</a>`
- **Couleur de la note (Couleur de fond) :**

  - **Ce que fait ce paramètre :** Cela vous permet de choisir la couleur de fond de votre note autocollante. Un outil de sélection de couleurs est généralement fourni pour une sélection facile.
  - **Effet de la modification de ce paramètre :** La note autocollante apparaîtra avec la couleur de fond choisie. C'est crucial pour la faire ressortir ou l'adapter à votre marque.
  - **Valeur recommandée :** Choisissez une couleur qui contraste bien avec l'arrière-plan de votre boutique et la couleur du texte, rendant la note facilement lisible et visible. Les couleurs vives et chaudes (jaune, orange, vert clair) fonctionnent souvent bien pour attirer l'attention.
  - **Scénario / exemple pour le marchand :** Pour un message d'avertissement, vous pourriez choisir un rouge vif ou un orange. Pour une annonce générale, un jaune classique ou un bleu clair.
- **Couleur du texte :**

  - **Ce que fait ce paramètre :** Cela définit la couleur du texte à l'intérieur de votre note autocollante.
  - **Effet de la modification de ce paramètre :** Le texte sera affiché dans la couleur sélectionnée.
  - **Valeur recommandée :** Choisissez toujours une couleur qui offre un contraste élevé avec la couleur de fond choisie pour une lisibilité optimale. Le noir ou le gris foncé sur un fond clair, ou le blanc sur un fond foncé, sont généralement les meilleurs.
  - **Scénario / exemple pour le marchand :** Si le fond de votre note est jaune, vous choisiriez le noir ou le gris foncé pour le texte. Si le fond est bleu foncé, le texte blanc serait idéal.
- **Position (Coordonnée X / Décalage gauche) :**

  - **Ce que fait ce paramètre :** Cela détermine la position horizontale de la note autocollante sur la page, mesurée à partir du bord gauche de l'écran ou de son conteneur parent. Elle est généralement spécifiée en pixels (px).
  - **Effet de la modification de ce paramètre :** Une valeur plus élevée déplace la note plus à droite. Une valeur plus faible la déplace plus près de la gauche.
  - **Valeur recommandée :** Expérimentez pour trouver une position qui n'obstrue pas le contenu important mais reste visible. Commencez avec des valeurs comme `20px` ou `50px` et ajustez.
  - **Scénario / exemple pour le marchand :** Vous voulez qu'une note apparaisse légèrement à droite de votre logo principal dans l'en-tête. Vous pourriez définir cela à `200px`.
- **Position (Coordonnée Y / Décalage haut) :**

  - **Ce que fait ce paramètre :** Cela détermine la position verticale de la note autocollante sur la page, mesurée à partir du bord supérieur de l'écran ou de son conteneur parent. Elle est généralement spécifiée en pixels (px).
  - **Effet de la modification de ce paramètre :** Une valeur plus élevée déplace la note plus bas sur la page. Une valeur plus faible la déplace plus près du haut.
  - **Valeur recommandée :** Considérez où la note sera la plus efficace sans être intrusive. Pour les messages d'en-tête, une petite valeur comme `10px` ou `20px` pourrait fonctionner. Pour les notes de page produit, vous devrez peut-être faire défiler pour voir l'effet.
  - **Scénario / exemple pour le marchand :** Vous voulez qu'une note apparaisse juste en dessous de votre barre de navigation principale. Vous pourriez définir cela à `100px`.
- **Largeur :**

  - **Ce que fait ce paramètre :** Cela contrôle la largeur du conteneur de la note autocollante. Elle est généralement spécifiée en pixels (px).
  - **Effet de la modification de ce paramètre :** Une largeur plus grande permet plus de texte sur une seule ligne, tandis qu'une largeur plus petite entraînera un retour à la ligne plus fréquent.
  - **Valeur recommandée :** Choisissez une largeur qui s'adapte confortablement à votre message sans être excessivement grande ou trop étroite. `200px` à `300px` est une plage courante.
  - **Scénario / exemple pour le marchand :** Si votre message est court, `200px` pourrait suffire. Si c'est une phrase légèrement plus longue, `280px` pourrait être mieux.
- **Hauteur :**

  - **Ce que fait ce paramètre :** Cela contrôle la hauteur du conteneur de la note autocollante. Elle est généralement spécifiée en pixels (px).
  - **Effet de la modification de ce paramètre :** Une hauteur plus grande permet plus de lignes de texte. Si le texte dépasse la hauteur, il pourrait être coupé ou déborder, selon le CSS de votre thème.
  - **Valeur recommandée :** Souvent, vous pouvez laisser ce champ vide ou le définir sur `auto` si le module le prend en charge, permettant à la hauteur de s'adapter au contenu. Si vous avez besoin d'une taille fixe, `100px` à `150px` est une plage courante.
  - **Scénario / exemple pour le marchand :** Si vous avez un message sur plusieurs lignes, vous devrez peut-être augmenter la hauteur pour vous assurer que tout le texte est visible.
- **Rotation (Angle) :**

  - **Ce que fait ce paramètre :** Cela vous permet de faire pivoter la note autocollante d'un certain degré, lui donnant une apparence plus naturelle de "collée".
  - **Effet de la modification de ce paramètre :** La note apparaîtra inclinée selon l'angle spécifié. Les valeurs positives tournent dans le sens des aiguilles d'une montre, les valeurs négatives dans le sens inverse.
  - **Valeur recommandée :** De petites rotations comme `3deg`, `-5deg` ou `7deg` sont souvent les plus esthétiques, offrant un effet subtil et réaliste sans rendre le texte difficile à lire.
  - **Scénario / exemple pour le marchand :** Pour donner l'impression qu'une note est collée de manière décontractée sur la page, vous pourriez la définir à `5deg`.
- **Z-Index :**

  - **Ce que fait ce paramètre :** Cette propriété CSS détermine l'ordre d'empilement des éléments. Un élément avec une valeur z-index plus élevée est placé devant les éléments avec des valeurs plus faibles.
  - **Effet de la modification de ce paramètre :** Si votre note autocollante apparaît derrière d'autres éléments (comme des pop-ups, des menus ou des bannières), augmenter son z-index la fera passer au premier plan.
  - **Valeur recommandée :** Commencez avec une valeur relativement élevée comme `999` ou `9999`. Si elle est toujours cachée, augmentez-la davantage.
  - **Scénario / exemple pour le marchand :** Votre note autocollante est cachée derrière une bannière de consentement aux cookies. Vous augmenteriez son Z-Index à `9999` pour vous assurer qu'elle est toujours au-dessus.
- **Actif / Activé :**

  - **Ce que fait ce paramètre :** Il s'agit d'un simple interrupteur (Oui/Non) pour activer ou désactiver la note autocollante sans la supprimer.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* La note autocollante sera visible sur votre front office selon ses autres paramètres.
    - *Lorsqu'désactivé :* La note autocollante sera cachée de votre front office, mais sa configuration sera sauvegardée, vous permettant de la réactiver plus tard.
  - **Valeur recommandée :** "Oui" lorsque vous voulez que la note soit visible ; "Non" lorsque vous voulez la masquer temporairement.
  - **Scénario / exemple pour le marchand :** Vous avez une note de promotion saisonnière. Vous pouvez la désactiver après la fin de la saison et la réactiver l'année prochaine sans la recréer.

#### 2.1.1 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Contenu de la note (Texte) | Varie | Le message affiché sur la note autocollante. Prend en charge le HTML de base. |
| Configuration du module | Couleur de la note (Fond) | Varie (ex. Jaune) | Définit la couleur de fond de la note. Choisissez pour le contraste. |
| Configuration du module | Couleur du texte | Varie (ex. Noir) | Définit la couleur du texte. Assurez un contraste élevé avec le fond. |
| Configuration du module | Position (Coordonnée X) | Varie (ex. 50px) | Position horizontale depuis la gauche. Ajustez pour le placement. |
| Configuration du module | Position (Coordonnée Y) | Varie (ex. 50px) | Position verticale depuis le haut. Ajustez pour le placement. |
| Configuration du module | Largeur | Varie (ex. 250px) | Largeur de la note autocollante. Affecte le retour à la ligne du texte. |
| Configuration du module | Hauteur | Varie (ex. auto ou 120px) | Hauteur de la note autocollante. Affecte la visibilité du contenu. |
| Configuration du module | Rotation (Angle) | Varie (ex. 5deg) | Incline la note pour un effet "collé" réaliste. |
| Configuration du module | Z-Index | Varie (ex. 9999) | Ordre d'empilement. Les valeurs plus élevées apparaissent au-dessus des autres éléments. |
| Configuration du module | Actif / Activé | Oui | Active ou désactive la visibilité de la note autocollante sur le front office. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Ma note autocollante n'apparaît pas sur le front office.**
R :

1. **Vérifiez le statut "Actif" :** Allez dans la configuration du module et assurez-vous que l'interrupteur "Actif" pour cette note spécifique est réglé sur "Oui".
2. **Videz le cache :** PrestaShop met souvent en cache le contenu. Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache".
3. **Z-Index :** Si le Z-Index de la note est trop bas, elle pourrait être cachée derrière d'autres éléments. Essayez d'augmenter la valeur du Z-Index (par exemple, à `9999`).
4. **Positionnement :** Vérifiez à nouveau les coordonnées X et Y. Si elles sont très élevées, la note pourrait être hors écran. Essayez de définir de petites valeurs comme `10px` pour les deux pour voir si elle apparaît.
5. **Installation du module :** Assurez-vous que le module est correctement installé et activé dans **Modules > Gestionnaire de modules**.

**Q : Le texte de ma note autocollante est coupé ou déborde.**
R :

1. **Ajustez la largeur/hauteur :** Augmentez les paramètres "Largeur" et/ou "Hauteur" pour cette note autocollante spécifique dans la configuration du module.
2. **Vérifiez le HTML :** Si vous utilisez du HTML, assurez-vous que toutes les balises sont correctement fermées (par exemple, `<b>` a un `</b>` correspondant). Un HTML incorrect peut parfois perturber le rendu.

**Q : La note autocollante a un aspect différent sur mobile que sur ordinateur de bureau.**
R : Le module vise la réactivité, mais le placement exact peut varier en raison des différentes tailles d'écran et du CSS de votre thème.

1. **Testez sur l'appareil :** Testez toujours l'apparence de la note sur des appareils mobiles réels ou utilisez les outils de développement de votre navigateur (F12) pour simuler des vues mobiles.
2. **Ajustez le positionnement :** Vous devrez peut-être ajuster les coordonnées X et Y pour un placement spécifique au mobile, bien que le module puisse ne pas offrir de paramètres mobiles distincts. S'il s'agit d'un problème majeur, demandez-vous si la note est vraiment essentielle sur mobile ou si une approche différente est nécessaire.
3. **Conflits de thème :** Occasionnellement, le CSS de votre thème peut entrer en conflit. Si vous le suspectez, contactez le support MyPresta.eu avec les détails de votre thème.

**Q : Comment puis-je faire du texte un lien ?**
R : Vous pouvez utiliser des balises d'ancrage HTML standard dans le champ "Contenu de la note".
Exemple : `<a href="https://votreboutique.com/nouveaux-produits">Cliquez ici pour les Nouveautés !</a>`
N'oubliez pas d'inclure l'URL complète, y compris `https://`.

**Q : Puis-je avoir des notes autocollantes différentes pour différentes langues ?**
R : Oui, le module prend en charge les fonctionnalités multilingues de PrestaShop. Lors de la modification d'une note autocollante, vous devriez voir des onglets de langue à côté du champ "Contenu de la note" (et potentiellement d'autres champs basés sur du texte). Sélectionnez l'onglet de langue souhaité et saisissez le contenu traduit pour cette note.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique pour les développeurs et les webmasters souhaitant comprendre, personnaliser ou déboguer le module "Notes autocollantes du Front Office".

### 4.1 Aperçu de l'architecture

Le module "Notes autocollantes du Front Office" suit une architecture de module PrestaShop standard, exploitant principalement la classe `Module` pour sa fonctionnalité principale et `ModuleFrontController` pour les interactions AJAX. Il stocke les données de configuration directement dans `ps_configuration` et rend son contenu via un template Smarty accroché au front office. Le module utilise du JavaScript côté client pour un comportement dynamique et un fichier CSS dédié pour le style.

### 4.2 Contrôleurs (`controllers/`)

Le module utilise des contrôleurs frontaux pour gérer les requêtes AJAX liées à la gestion des notes autocollantes (ajouter, modifier, supprimer). Ce ne sont pas des contrôleurs de page complète mais des points d'accès pour des interactions dynamiques.

- **Contrôleurs Front-Office** :

  - `controllers/front/add.php`
    - **Nom de la classe et classe parente** : `StickynotesfoAddModuleFrontController` étendant `ModuleFrontController`
    - **Responsabilité** : Gère les requêtes AJAX pour ajouter une nouvelle note autocollante. Il reçoit probablement des données POST contenant le contenu de la note, la position, les couleurs, etc., les valide et les enregistre dans la base de données (via la classe `Configuration` ou un `ObjectModel` personnalisé s'il en existait un). Renvoie une réponse JSON indiquant le succès ou l'échec.
  - `controllers/front/delete.php`
    - **Nom de la classe et classe parente** : `StickynotesfoDeleteModuleFrontController` étendant `ModuleFrontController`
    - **Responsabilité** : Gère les requêtes AJAX pour supprimer une note autocollante existante. Il attend un identifiant (par exemple, `id_note`) dans la requête, supprime les données correspondantes de la base de données et renvoie une réponse JSON.
  - `controllers/front/edit.php`
    - **Nom de la classe et classe parente** : `StickynotesfoEditModuleFrontController` étendant `ModuleFrontController`
    - **Responsabilité** : Gère les requêtes AJAX pour mettre à jour une note autocollante existante. Il reçoit des données POST avec l'ID de la note et les propriétés mises à jour, modifie l'enregistrement de la base de données et renvoie une réponse JSON.
  - `controllers/front/index.php`
    - **Nom de la classe et classe parente** : `StickynotesfoIndexModuleFrontController` étendant `ModuleFrontController`
    - **Responsabilité** : Ce contrôleur pourrait servir de point d'entrée général pour les requêtes AJAX ou pourrait être un recours. Compte tenu des contrôleurs spécifiques `add`, `delete`, `edit`, `index.php` pourrait gérer la liste des notes ou d'autres interactions générales non couvertes par les opérations CRUD spécifiques.
- **Contrôleurs d'administration Back-Office** : Aucun détecté. Toute la configuration du back-office est gérée dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

Aucune définition de `classes/` ou `ObjectModel` personnalisée n'a été détectée. Le module stocke probablement sa configuration directement dans la table `ps_configuration` de PrestaShop, en utilisant des clés uniques pour les propriétés de chaque note autocollante. Cette approche est courante pour les modules plus simples gérant un nombre limité de paramètres.

### 4.4 Actifs JavaScript (`views/js/`)

- `js/advajax.js`
  - **Portée** : Probablement Front-office.
  - **Description** : Ce fichier suggère un script utilitaire AJAX personnalisé ou tiers. Il fournit probablement des fonctions d'aide pour effectuer des requêtes asynchrones aux contrôleurs frontaux du module (`add.php`, `delete.php`, `edit.php`). Il pourrait encapsuler des modèles AJAX courants, la gestion des erreurs ou la sérialisation des données. Les développeurs devraient examiner ce fichier pour comprendre comment les appels AJAX sont structurés et initiés au sein du module.
- `js/jscolor/jscolor.js`
  - **Portée** : Back-office (pour la configuration).
  - **Description** : Il s'agit d'une bibliothèque JavaScript tierce pour un sélecteur de couleurs. Elle est utilisée dans le formulaire de configuration du back-office du module pour fournir une interface conviviale pour la sélection des couleurs de note et de texte. Elle se lie aux champs de saisie d'une classe ou d'un ID spécifique, les transformant en outils de sélection de couleurs interactifs.

### 4.5 Feuilles de style CSS (`views/css/`)

- `css/stickynotes.css`
  - **Portée** : Style client Front-office.
  - **Description** : C'est la feuille de style principale pour les notes autocollantes affichées sur le front office. Elle définit l'apparence visuelle des notes, y compris :
    - Le style de base pour le conteneur de la note autocollante (par exemple, `position: absolute;`, `background-color`, `border-radius`).
    - Le style du texte dans la note (`font-size`, `color`, `line-height`).
    - L'effet "décollé" ou rotatif (probablement en utilisant `transform: rotate()`).
    - `z-index` pour assurer la visibilité.
    - Potentiellement des ajustements réactifs pour différentes tailles d'écran à l'aide de requêtes média.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger** : Les développeurs doivent inspecter le HTML rendu pour identifier la classe de conteneur principale (par exemple, `.sticky-note`, `.stickynotesfo-item`) et ses éléments enfants pour appliquer un style personnalisé dans le `custom.css` ou `theme.css` de leur thème.

### 4.6 Structure du template Smarty (`views/templates/`)

- **Templates de hook (`views/templates/front/`)** :
  - `views/templates/front/sticky-notes-front-office.tpl`
    - **Hook** : Ce template est probablement rendu dans un hook général du front-office tel que `displayHeader`, `displayFooter`, ou potentiellement `displayBeforeBodyClosingTag`. La méthode `hookDisplayHeader` ou `hookDisplayFooter` du module récupérerait généralement toutes les notes autocollantes actives de la base de données et les attribuerait à ce template.
    - **Sortie de bloc visuel** : Ce template est responsable de l'itération sur la liste des notes autocollantes actives et du rendu de la structure HTML pour chacune d'elles. Il insérera dynamiquement le contenu de la note, les couleurs, les positions, la largeur, la hauteur, la rotation et le z-index comme styles en ligne ou attributs de données, qui sont ensuite récupérés par `stickynotes.css` et potentiellement `advajax.js` pour les mises à jour dynamiques. Chaque note sera probablement un élément `div` avec des ID ou des classes uniques.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de la base de données** :

  - Le module ne crée pas de tables SQL personnalisées. Au lieu de cela, il stocke ses données de configuration dans la table `ps_configuration` de PrestaShop. Les propriétés de chaque note autocollante (contenu, couleur, position, etc.) sont stockées comme des clés de configuration individuelles, probablement préfixées par `STICKYNOTESFO_NOTE_` suivi d'un identifiant unique (par exemple, `STICKYNOTESFO_NOTE_1_CONTENT`, `STICKYNOTESFO_NOTE_1_COLOR`). Les champs multilingues utiliseraient des suffixes `_LANG_ID`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | But technique |
| --- | --- | --- |
| `displayHeader` | Exécuté à la fin de la section `<head>` de chaque page du front-office. | Idéal pour injecter du CSS, du JavaScript et potentiellement la structure HTML initiale des notes autocollantes, en s'assurant qu'elles sont disponibles tôt dans le DOM. |
| `displayFooter` | Exécuté à la fin de la section `<body>` de chaque page du front-office. | Peut être utilisé pour injecter le HTML des notes autocollantes, surtout si elles sont destinées à flotter ou à être positionnées absolument par rapport à la fenêtre d'affichage. |
| `displayLeftColumn` | Exécuté dans la colonne de gauche des pages qui en ont une. | Permet le placement de notes autocollantes spécifiquement dans la barre latérale gauche. |
| `displayRightColumn` | Exécuté dans la colonne de droite des pages qui en ont une. | Permet le placement de notes autocollantes spécifiquement dans la barre latérale droite. |
| `displayProductAdditionalInfo` (ou hook de page produit similaire) | Exécuté sur la page produit, généralement près de la description du produit ou du bouton "Ajouter au panier". | Permet le placement de notes autocollantes spécifiques aux pages de produits individuelles. |
| `actionFrontControllerSetMedia` | Exécuté lorsqu'un contrôleur frontal définit ses médias (CSS/JS). | Utilisé par le module pour enregistrer ses fichiers `stickynotes.css` et `advajax.js` pour l'affichage du front-office. |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses médias (CSS/JS). | Utilisé par le module pour enregistrer `jscolor.js` et tout autre CSS/JS spécifique à l'administration pour sa page de configuration. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et toute assistance supplémentaire concernant le module "Notes autocollantes du Front Office", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à fournir un support rapide et à assurer le fonctionnement optimal de votre module.
