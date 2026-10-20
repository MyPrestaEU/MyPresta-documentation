---
title: "Zoom d'image des produits Fancybox - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Zoom d'image des produits Fancybox' par MyPresta.eu."
sidebar:
  label: "Zoom d'image des produits Fancybox - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Fancybox products image zoom sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/fancybox-products-image-zoom.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/fancybox-products-image-zoom/)
>
> ---


# Zoom d'image des produits Fancybox

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement nécessaire.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal pour le module "Zoom d'image des produits Fancybox". Vous le trouverez en naviguant vers **Modules > Gestionnaire de modules**, en recherchant "Zoom d'image des produits Fancybox", et en cliquant sur "Configurer".

#### Paramètres de support de thème et de sélecteur

Ces paramètres aident le module à identifier les éléments corrects sur votre page produit pour appliquer le zoom Fancybox, particulièrement important pour les thèmes personnalisés.

- **Support de thème**

  - **Ce que fait ce paramètre :** C'est un paramètre crucial qui indique au module quelle structure de thème il doit s'attendre. Il aide le module à identifier correctement l'image principale du produit et ses miniatures sur vos pages produits.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur "Classic" :* Le module utilisera des sélecteurs prédéfinis qui fonctionnent parfaitement avec le thème "Classic" par défaut de PrestaShop. C'est le paramètre le plus courant et recommandé si vous utilisez le thème Classic ou un thème très étroitement basé sur celui-ci.
    - *Lorsqu'il est défini sur "Hummingbird" :* Le module utilisera des sélecteurs prédéfinis pour le thème "Hummingbird", qui est le thème par défaut pour PrestaShop 8.1 et les versions plus récentes.
    - *Lorsqu'il est défini sur "Custom" :* Cette option vous permet de spécifier manuellement les sélecteurs CSS pour votre image principale du produit et vos miniatures. C'est essentiel si vous utilisez un thème fortement personnalisé ou un thème tiers qui ne suit pas la structure "Classic" ou "Hummingbird".
  - **Valeur recommandée :** "Classic" si vous êtes sur PrestaShop 1.7.x à 8.0.x avec le thème Classic. "Hummingbird" si vous êtes sur PrestaShop 8.1+ avec le thème Hummingbird. "Custom" si vous avez un thème unique.
  - **Scénario/exemple pour le marchand :** Si vos images de produits ne zooment pas correctement après l'installation, et que vous utilisez un thème personnalisé, passer ce paramètre à "Custom" puis ajuster les sélecteurs ci-dessous est la prochaine étape.
- **Profil de thème détecté**

  - **Ce que fait ce paramètre :** Ce champ affiche le profil de thème que le module a automatiquement détecté en fonction de votre sélection "Support de thème". C'est un champ informatif, non directement configurable.
  - **Effet de la modification de ce paramètre :** Aucun effet direct, car c'est un champ d'affichage uniquement. Il confirme simplement quel ensemble de sélecteurs le module utilise actuellement.
  - **Valeur recommandée :** N/A (informatif).
  - **Scénario/exemple pour le marchand :** Vous avez défini "Support de thème" sur "Classic", et ce champ confirme que "Classic" est détecté.
- **Sélecteur de couverture Hummingbird** (Visible uniquement si "Support de thème" est "Hummingbird")

  - **Ce que fait ce paramètre :** Spécifie le sélecteur CSS pour le conteneur de l'image de couverture principale du produit lors de l'utilisation du thème Hummingbird. Cela aide le module à cibler la zone correcte pour le zoom.
  - **Effet de la modification de ce paramètre :** S'il est incorrect, le zoom Fancybox pourrait ne pas s'activer sur l'image principale du produit, ou il pourrait cibler le mauvais élément.
  - **Valeur recommandée :** Laisser par défaut, sauf si votre thème basé sur Hummingbird a considérablement modifié sa structure.
  - **Scénario/exemple pour le marchand :** Votre thème Hummingbird a une structure unique pour l'image principale. Vous pourriez avoir besoin d'inspecter le code de votre thème pour trouver la classe ou l'ID CSS correct pour le conteneur de l'image principale et le saisir ici.
- **Sélecteur d'image Hummingbird** (Visible uniquement si "Support de thème" est "Hummingbird")

  - **Ce que fait ce paramètre :** Spécifie le sélecteur CSS pour la balise `<img>` réelle de l'image de couverture principale du produit dans le thème Hummingbird.
  - **Effet de la modification de ce paramètre :** Similaire au sélecteur de couverture, une valeur incorrecte empêchera le zoom de fonctionner sur l'image principale.
  - **Valeur recommandée :** Laisser par défaut.
  - **Scénario/exemple pour le marchand :** Si le zoom ne fonctionne pas sur l'image principale, et que vous êtes sur Hummingbird, vérifiez ce sélecteur.
- **Sélecteur de miniatures Hummingbird** (Visible uniquement si "Support de thème" est "Hummingbird")

  - **Ce que fait ce paramètre :** Spécifie le sélecteur CSS pour le conteneur des images miniatures du produit lors de l'utilisation du thème Hummingbird. C'est important pour créer une galerie à partir de vos miniatures.
  - **Effet de la modification de ce paramètre :** S'il est incorrect, le module pourrait ne pas être en mesure de créer une galerie Fancybox à partir de vos miniatures, ou cliquer sur les miniatures pourrait ne pas ouvrir la Fancybox.
  - **Valeur recommandée :** Laisser par défaut.
  - **Scénario/exemple pour le marchand :** Si cliquer sur les miniatures n'ouvre pas la galerie Fancybox, vérifiez ce sélecteur.
- **Sélecteur d'image de couverture principale** (Visible uniquement si "Support de thème" est "Custom")

  - **Ce que fait ce paramètre :** Lorsque le support de thème "Custom" est sélectionné, ce champ vous permet de saisir manuellement le sélecteur CSS pour l'élément conteneur qui contient votre image principale du produit sur la page produit.
  - **Effet de la modification de ce paramètre :** Si ce sélecteur est incorrect, le zoom Fancybox ne s'activera pas sur votre image principale du produit.
  - **Valeur recommandée :** Vous devrez utiliser les outils de développement de votre navigateur (F12) pour inspecter votre page produit et trouver la classe ou l'ID CSS unique de l'élément `<div>` ou autre conteneur qui enveloppe votre image principale du produit.
  - **Scénario/exemple pour le marchand :** Votre thème personnalisé utilise `<div id="my-custom-main-image-wrapper">` pour l'image principale. Vous saisiriez `#my-custom-main-image-wrapper` ici.
- **Image de couverture principale** (Visible uniquement si "Support de thème" est "Custom")

  - **Ce que fait ce paramètre :** Lorsque le support de thème "Custom" est sélectionné, ce champ vous permet de saisir manuellement le sélecteur CSS pour la balise `<img>` réelle de votre image principale du produit.
  - **Effet de la modification de ce paramètre :** Si ce sélecteur est incorrect, le zoom Fancybox ne s'activera pas sur votre image principale du produit.
  - **Valeur recommandée :** Utilisez les outils de développement de votre navigateur pour trouver la classe ou l'ID CSS unique de la balise `<img>` elle-même.
  - **Scénario/exemple pour le marchand :** Votre thème personnalisé utilise `<img class="product-main-image-src">` pour l'image principale. Vous saisiriez `.product-main-image-src` ici.
- **Sélecteur d'images miniatures** (Visible uniquement si "Support de thème" est "Custom")

  - **Ce que fait ce paramètre :** Lorsque le support de thème "Custom" est sélectionné, ce champ vous permet de saisir manuellement le sélecteur CSS pour l'élément conteneur qui contient vos images miniatures du produit.
  - **Effet de la modification de ce paramètre :** Si ce sélecteur est incorrect, le module ne pourra pas créer une galerie Fancybox à partir de vos miniatures, ou cliquer sur les miniatures pourrait ne pas ouvrir la Fancybox.
  - **Valeur recommandée :** Utilisez les outils de développement de votre navigateur pour trouver la classe ou l'ID CSS unique de l'élément `<div>` ou autre conteneur qui enveloppe vos miniatures de produit.
  - **Scénario/exemple pour le marchand :** Votre thème personnalisé utilise `<ul id="product-thumbnails-list">` pour les miniatures. Vous saisiriez `#product-thumbnails-list` ici.

#### Paramètres de comportement Fancybox

Ces paramètres contrôlent le comportement du zoom Fancybox et son interaction avec vos clients.

- **Créer une galerie**

  - **Ce que fait ce paramètre :** Détermine si toutes les images du produit (image principale et miniatures) sont regroupées dans une seule galerie Fancybox. Lorsqu'il est activé, cliquer sur n'importe quelle image ouvrira Fancybox, et les clients pourront ensuite naviguer à travers toutes les images du produit à l'aide de flèches.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé ("Oui") :* Les clients peuvent parcourir toutes les images du produit dans une superposition Fancybox en plein écran, à l'aide de flèches de navigation. Cela offre une vue complète du produit.
    - *Lorsqu'il est désactivé ("Non") :* Cliquer sur une image n'ouvrira que cette image spécifique dans Fancybox. Les clients ne peuvent pas naviguer vers d'autres images du produit depuis la vue Fancybox.
  - **Valeur recommandée :** "Oui" pour une meilleure expérience utilisateur et pour encourager les clients à voir tous les angles du produit.
  - **Scénario/exemple pour le marchand :** Vous souhaitez que les clients puissent facilement feuilleter toutes les images du produit sans fermer et rouvrir le zoom pour chacune. Activez ceci.
- **Balayage**

  - **Ce que fait ce paramètre :** Active ou désactive les gestes de balayage pour naviguer dans la galerie Fancybox sur les appareils tactiles (smartphones, tablettes).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé ("Oui") :* Les clients peuvent balayer vers la gauche ou la droite sur leurs appareils tactiles pour passer d'une image à l'autre dans la galerie Fancybox.
    - *Lorsqu'il est désactivé ("Non") :* Les gestes de balayage ne fonctionneront pas. Les clients devront utiliser les flèches de navigation (si "Créer une galerie" est activé).
  - **Valeur recommandée :** "Oui" pour une expérience mobile moderne et intuitive.
  - **Scénario/exemple pour le marchand :** Vous souhaitez que vos utilisateurs mobiles aient un moyen fluide et naturel de parcourir les images de produits. Gardez ceci activé.
- **Éviter l'image de couverture doublée dans la galerie**

  - **Ce que fait ce paramètre :** Lorsque "Créer une galerie" est activé, l'image principale du produit peut parfois apparaître deux fois dans la galerie (une fois comme image principale, et une autre fois si elle est également répertoriée comme miniature). Ce paramètre empêche cette duplication.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé ("Oui") :* Le module essaiera de détecter et de supprimer toute image principale du produit en double de la galerie Fancybox, garantissant que chaque image n'apparaît qu'une seule fois.
    - *Lorsqu'il est désactivé ("Non") :* Si l'image principale du produit fait également partie de la liste des miniatures, elle pourrait apparaître deux fois dans la galerie Fancybox.
  - **Valeur recommandée :** "Oui" pour une expérience de galerie plus propre et plus professionnelle.
  - **Scénario/exemple pour le marchand :** Vous remarquez que lorsque les clients ouvrent la galerie Fancybox, la première image est identique à la seconde. L'activation de ceci corrigera cela.
- **Afficher les légendes (titres d'image)**

  - **Ce que fait ce paramètre :** Contrôle si le titre/légende associé à chaque image du produit est affiché dans la superposition Fancybox. Ces titres sont généralement définis dans la gestion des images de vos produits PrestaShop.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé ("Oui") :* Le titre de l'image apparaîtra comme une légende sous ou au-dessus de l'image dans la superposition Fancybox.
    - *Lorsqu'il est désactivé ("Non") :* Aucune légende ne sera affichée, offrant une vue plus propre, uniquement avec l'image.
  - **Valeur recommandée :** "Oui" si vos titres d'image fournissent des informations utiles (par exemple, "Vue de face", "Gros plan du tissu", "Modèle portant le produit"). "Non" si vos titres d'image sont génériques ou si vous préférez un look minimaliste.
  - **Scénario/exemple pour le marchand :** Vous utilisez des titres descriptifs pour vos images de produits et souhaitez que les clients les voient lors du zoom. Activez ceci.
- **Changer l'image principale au survol de la miniature**

  - **Ce que fait ce paramètre :** Détermine si le survol de la souris sur une miniature de produit modifie automatiquement l'image principale du produit affichée sur la page produit, *avant* de cliquer pour ouvrir Fancybox.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé ("Oui") :* Le déplacement du curseur de la souris sur une miniature changera instantanément l'image principale du produit pour afficher la miniature survolée. C'est une fonctionnalité courante et pratique pour les acheteurs.
    - *Lorsqu'il est désactivé ("Non") :* L'image principale du produit ne changera que lorsqu'une miniature est cliquée, pas seulement survolée.
  - **Valeur recommandée :** "Oui" pour une expérience de navigation plus interactive et conviviale.
  - **Scénario/exemple pour le marchand :** Vous souhaitez que les clients prévisualisent rapidement différentes images de produits en déplaçant simplement leur souris, sans avoir besoin de cliquer. Activez ceci.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | **Support de thème** | Classic / Hummingbird | Sélectionne des sélecteurs CSS prédéfinis pour votre thème (Classic, Hummingbird ou Custom). Crucial pour la fonctionnalité du module. |
| Configuration du module | **Profil de thème détecté** | N/A (Informations) | Affiche le profil de thème actuellement actif. |
| Configuration du module | **Sélecteur de couverture Hummingbird** | Par défaut | Sélecteur CSS pour le conteneur de l'image principale (thème Hummingbird). |
| Configuration du module | **Sélecteur d'image Hummingbird** | Par défaut | Sélecteur CSS pour la balise `<img>` principale (thème Hummingbird). |
| Configuration du module | **Sélecteur de miniatures Hummingbird** | Par défaut | Sélecteur CSS pour le conteneur des miniatures (thème Hummingbird). |
| Configuration du module | **Sélecteur d'image de couverture principale** | Personnalisé (Inspecter le thème) | Sélecteur CSS pour le conteneur de l'image principale (thème Custom). |
| Configuration du module | **Image de couverture principale** | Personnalisé (Inspecter le thème) | Sélecteur CSS pour la balise `<img>` principale (thème Custom). |
| Configuration du module | **Sélecteur d'images miniatures** | Personnalisé (Inspecter le thème) | Sélecteur CSS pour le conteneur des miniatures (thème Custom). |
| Configuration du module | **Créer une galerie** | Oui | Regroupe toutes les images du produit dans une galerie Fancybox navigable. |
| Configuration du module | **Balayage** | Oui | Active les gestes de balayage pour la navigation dans la galerie sur les appareils tactiles. |
| Configuration du module | **Éviter l'image de couverture doublée dans la galerie** | Oui | Empêche l'image principale d'apparaître deux fois dans la galerie. |
| Configuration du module | **Afficher les légendes (titres d'image)** | Oui / Non (Préférence du marchand) | Affiche les titres d'image comme légendes dans la superposition Fancybox. |
| Configuration du module | **Changer l'image principale au survol de la miniature** | Oui | Change l'image principale du produit au survol de la miniature. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Le zoom Fancybox n'apparaît pas du tout sur mes pages produits.**
R :

1. **Vérifier l'état du module :** Assurez-vous que le module est installé et activé dans **Modules > Gestionnaire de modules**.
2. **Paramètre de support de thème :** Accédez à la page de configuration du module. Si vous utilisez le thème "Classic", assurez-vous que "Support de thème" est défini sur "Classic". Si vous êtes sur PrestaShop 8.1+ avec le thème Hummingbird, définissez-le sur "Hummingbird". Si vous avez un thème personnalisé, définissez-le sur "Custom" et examinez attentivement les sélecteurs CSS que vous avez saisis (voir point suivant).
3. **Sélecteurs de thème personnalisés :** Si "Support de thème" est "Custom", le problème le plus courant est des sélecteurs CSS incorrects. Utilisez les outils de développement de votre navigateur (F12) pour inspecter votre page produit. Trouvez les classes ou ID CSS exacts pour le conteneur de votre image principale du produit, la balise `<img>` et le conteneur de vos miniatures. Mettez-les à jour dans les paramètres du module.

**Q : La Fancybox s'ouvre, mais elle affiche la mauvaise image ou une seule image.**
R :

1. **Paramètre "Créer une galerie" :** Assurez-vous que "Créer une galerie" est défini sur "Oui" dans la configuration du module si vous souhaitez parcourir plusieurs images.
2. **Sélecteurs de miniatures :** Si "Créer une galerie" est activé mais qu'une seule image apparaît, vérifiez votre "Sélecteur d'images miniatures" (surtout si "Support de thème" est "Custom"). Le module doit identifier correctement toutes vos miniatures pour construire la galerie.
3. **Titres/légendes d'image :** Si les légendes ne s'affichent pas, assurez-vous que "Afficher les légendes (titres d'image)" est "Oui" et que vos images de produits ont bien des titres définis dans le back office de PrestaShop.

**Q : Les gestes de balayage ne fonctionnent pas sur mon appareil mobile.**
R :

1. **Paramètre "Balayage" :** Assurez-vous que l'option "Balayage" est définie sur "Oui" dans la configuration du module.
2. **Galerie activée :** Le balayage ne fonctionne que si "Créer une galerie" est également "Oui", car il sert à naviguer entre plusieurs images.
3. **Compatibilité navigateur/appareil :** Bien que largement pris en charge, de très anciens navigateurs ou des configurations d'appareils spécifiques peuvent rencontrer des problèmes. Testez sur un navigateur mobile moderne.

**Q : La mise en page de ma page produit semble un peu décalée après l'installation du module.**
R :

1. **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache". Parfois, d'anciens fichiers mis en cache peuvent interférer avec le nouveau style du module.
2. **Conflits de thème :** Bien que le module essaie d'être compatible, un CSS de thème personnalisé très spécifique peut entrer en conflit. Si vider le cache ne résout pas le problème, désactivez temporairement le module pour voir si le problème disparaît. Si c'est le cas, vous pourriez avoir besoin d'un développeur web pour ajuster le CSS de votre thème ou les sélecteurs personnalisés du module.

**Q : Comment trouver les sélecteurs CSS corrects pour mon thème personnalisé ?**
R :

1. Ouvrez votre page produit dans un navigateur web (Chrome, Firefox, Edge).
2. Faites un clic droit sur l'image principale de votre produit et sélectionnez "Inspecter" ou "Inspecter l'élément".
3. Cela ouvrira les outils de développement du navigateur. Recherchez la balise `<img>` de votre image principale et son `<div>` parent ou autre conteneur. Notez tous les attributs `id` uniques (par exemple, `id="my-image"`) ou les attributs `class` (par exemple, `class="product-image-wrapper"`).
4. Répétez cette opération pour vos miniatures de produit.
5. Utilisez ces ID (préfixés par `#`, par exemple, `#my-image`) ou classes (préfixées par `.`, par exemple, `.product-image-wrapper`) dans les paramètres de thème "Custom" du module. Vous devrez peut-être expérimenter un peu pour trouver les sélecteurs les plus spécifiques et fiables.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module `fancyzoom` est un module PrestaShop léger principalement conçu pour remplacer la fonctionnalité de zoom d'image de produit par défaut par Fancybox. Il y parvient en se raccordant à `displayHeader` pour injecter son JavaScript et son CSS personnalisés, et en utilisant JavaScript pour identifier et réinitialiser les éléments d'image avec Fancybox. La configuration du module est gérée via la méthode standard `getContent()` dans le fichier principal du module, stockant les paramètres dans `ps_configuration`. Il n'introduit pas de tables de base de données personnalisées, de classes `ObjectModel` ou de contrôleurs front/admin dédiés au-delà de la configuration principale du module.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. Toutes les fonctionnalités du front-office sont injectées via des hooks et gérées par JavaScript.
- **Contrôleurs Admin Back-Office** : Aucun. Toute la configuration du back-office est gérée par la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

- Aucune classe personnalisée ou définition `ObjectModel` n'est présente dans le répertoire `classes/`. Toute la logique principale réside dans le fichier principal du module `fancyzoom.php`.

### 4.4 Actifs JavaScript (`views/js/`)

Le module inclut deux fichiers JavaScript, principalement pour la fonctionnalité front-office. Ils sont enregistrés via le hook `displayHeader`.

- `fancyzoom/views/templates/js/fancyzoom.js`

  - **Portée :** Front-office.
  - **Responsabilité :** C'est le script principal qui initialise Fancybox. Il identifie dynamiquement l'image principale du produit et les miniatures en fonction des sélecteurs CSS configurés (ou des sélecteurs Classic/Hummingbird par défaut). Il lie ensuite les événements de clic à ces images pour les ouvrir dans une galerie Fancybox. Il gère également la fonctionnalité "changer l'image principale au survol de la miniature". Il est responsable de la désactivation du zoom PrestaShop par défaut.
  - **Fonctionnalités clés :**
    - Désactive le zoom d'image PrestaShop par défaut.
    - Détecte le profil de thème (Classic, Hummingbird, Custom) et applique les sélecteurs appropriés.
    - Initialise Fancybox sur les images de produits.
    - Gère la création de la galerie Fancybox et ses options (balayage, légendes, images doublées).
    - Gère l'effet de survol des miniatures pour changer l'image principale.
    - Écoute l'événement `updateProduct` (mises à jour de la page produit PrestaShop 1.7+) pour réinitialiser Fancybox.
- `fancyzoom/views/templates/js/touchswipe.js`

  - **Portée :** Front-office.
  - **Responsabilité :** Il s'agit d'une bibliothèque tierce qui fournit une détection robuste des événements de balayage tactile. Elle est utilisée par `fancyzoom.js` pour activer la navigation par balayage dans la galerie Fancybox sur les appareils tactiles.
  - **Fonctionnalités clés :** Fournit un plugin jQuery pour détecter les gestes de balayage (gauche, droite, haut, bas) et d'autres événements tactiles.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module inclut un fichier CSS pour le style du front-office.

- `fancyzoom/views/templates/css/fancyzoom.css`
  - **Portée :** Style client du front-office.
  - **Responsabilité :** Contient le CSS nécessaire pour la superposition Fancybox elle-même, y compris le style des flèches de navigation, du bouton de fermeture, des légendes et de l'apparence générale. Il garantit que le modal Fancybox est correctement positionné et stylisé.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger :**
    - `.fancybox-container` : Conteneur principal de la superposition Fancybox.
    - `.fancybox-bg` : Superposition d'arrière-plan.
    - `.fancybox-toolbar` : Barre d'outils avec bouton de fermeture, etc.
    - `.fancybox-caption` : Zone de légende.
    - `.fancybox-button` : Boutons (fermer, navigation).
    - `.fancybox-image` : L'image elle-même dans Fancybox.
      Les développeurs peuvent surcharger ces classes dans le fichier `custom.css` de leur thème ou un fichier similaire pour correspondre à l'image de marque de leur boutique.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **Modèles de hook (`views/templates/hook/`)** :

  - `fancyzoom/views/templates/hook/fancyzoom.tpl`
    - **Hook :** `displayHeader`
    - **Objectif :** Ce modèle est responsable de l'injection des variables JavaScript nécessaires et des fichiers JS et CSS du module dans la section `<head>` du front-office. Il transmet les variables de configuration du back-office (comme les sélecteurs, les options de galerie) au script `fancyzoom.js`.
- **Modèles d'administration (`views/templates/admin/`)** :

  - `fancyzoom/views/templates/admin/admin.tpl`
    - **Objectif :** Ce modèle rend le formulaire de configuration du module dans le back office de PrestaShop. Il affiche tous les paramètres décrits dans la section 4.1, y compris les champs de saisie pour les sélecteurs, les cases à cocher pour les options de galerie et la détection du profil de thème.
- **Modèles Front-office (`views/templates/front/`)** : Aucun.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :
  Le module ne crée aucune table de base de données personnalisée. Tous ses paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide de clés préfixées par `FZ_` (par exemple, `FZ_THEME`, `FZ_COVER_DIV`, `FZ_GALLERY`).
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Injecte les fichiers CSS et JavaScript du module, et transmet les variables de configuration aux scripts front-end. C'est là que la bibliothèque Fancybox et sa logique d'initialisation sont chargées. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour télécharger les dernières versions du module "Zoom d'image des produits Fancybox", veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
