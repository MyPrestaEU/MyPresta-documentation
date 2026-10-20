---
title: "Flux de tags de produits Instagram - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Flux de tags de produits Instagram' par MyPresta.eu."
sidebar:
  label: "Flux de tags de produits Instagram - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Instagram product tag feed sur MyPresta.eu](https://mypresta.eu/modules/social-networks/instagram-product-tag-feed.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/instagram-product-tag-feed/)
>
> ---


# Flux de tags de produits Instagram

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour la communication API, et sont presque universellement disponibles sur les environnements d'hébergement modernes.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Pour accéder aux paramètres du module, allez dans **Modules > Gestionnaire de modules** dans votre Back Office PrestaShop, recherchez « Flux de tags de produits Instagram », et cliquez sur le bouton « Configurer ».

Vous y trouverez les principales options de configuration pour contrôler l'affichage de vos flux Instagram.

#### Paramètres généraux

- **Jeton d'accès Instagram :**

  - **Ce que fait ce paramètre :** Il s'agit d'un code unique qui accorde à votre boutique PrestaShop l'autorisation d'accéder aux données publiques de votre compte Instagram (comme les photos associées à des tags spécifiques). Vous devez générer ce jeton à partir des outils de développement d'Instagram ou d'un outil tiers qui simplifie le processus.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est correctement saisi :* Votre module pourra récupérer et afficher les photos Instagram.
    - *Lorsqu'il est incorrect ou vide :* Le module ne pourra pas se connecter à Instagram, et aucune photo ne sera affichée, ce qui entraînera un flux vide ou un message d'erreur.
  - **Valeur recommandée :** Votre jeton d'accès Instagram valide.
  - **Scénario/exemple pour le marchand :** Vous venez de configurer votre compte professionnel Instagram. Vous devrez suivre les instructions d'Instagram (ou utiliser un outil d'aide) pour obtenir ce jeton et le coller ici. Sans lui, le module ne peut pas « voir » vos photos Instagram.
- **ID utilisateur Instagram :**

  - **Ce que fait ce paramètre :** Il s'agit de l'identifiant numérique unique de votre compte Instagram. Il est souvent requis avec le jeton d'accès pour récupérer correctement les données.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est correctement saisi :* Garantit que le module récupère les données de votre compte Instagram spécifique.
    - *Lorsqu'il est incorrect ou vide :* Peut entraîner des erreurs lors de la récupération des données ou la récupération de données d'un mauvais compte, ce qui entraîne un flux vide ou incorrect.
  - **Valeur recommandée :** Votre ID utilisateur Instagram valide.
  - **Scénario/exemple pour le marchand :** Similaire au jeton d'accès, vous obtiendrez cet ID lors de la configuration de votre accès à l'API Instagram. Il indique au module *quel* flux Instagram regarder.
- **Nombre de photos à afficher :**

  - **Ce que fait ce paramètre :** Contrôle le nombre de photos Instagram récupérées et affichées dans une seule instance de flux.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur un nombre plus élevé (par exemple, 10) :* Plus de photos seront chargées et potentiellement affichées dans le flux, le rendant plus riche mais potentiellement plus lent à charger.
    - *Lorsqu'il est défini sur un nombre plus faible (par exemple, 3) :* Moins de photos seront affichées, ce qui entraînera un flux plus concis et des temps de chargement plus rapides.
  - **Valeur recommandée :** Commencez avec 6 à 9 photos pour un bon équilibre entre contenu et performances. Ajustez en fonction de votre mise en page et des tests de vitesse de page.
  - **Scénario/exemple pour le marchand :** Pour un onglet de page produit, vous pourriez vouloir 6 photos. Pour un carrousel de page d'accueil, vous pourriez en vouloir 12 pour offrir plus de variété aux utilisateurs qui défilent.
- **Afficher sur la page d'accueil :**

  - **Ce que fait ce paramètre :** Un simple interrupteur pour activer ou désactiver le flux Instagram sur la page d'accueil de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module tentera d'afficher un flux Instagram sur votre page d'accueil (généralement via le hook `displayHome`).
    - *Lorsqu'il est désactivé :* Aucun flux Instagram n'apparaîtra sur votre page d'accueil.
  - **Valeur recommandée :** OUI, si vous souhaitez présenter votre contenu Instagram de manière proéminente. NON, si vous préférez une page d'accueil plus épurée ou si vous ne souhaitez des flux que sur les pages produits.
  - **Scénario/exemple pour le marchand :** Vous souhaitez montrer vos dernières photos de style de vie sur la page d'accueil pour engager immédiatement les visiteurs. Vous activeriez ceci.
- **Afficher sur la page produit :**

  - **Ce que fait ce paramètre :** Un simple interrupteur pour activer ou désactiver le flux Instagram sur les pages produits individuelles.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module tentera d'afficher un flux Instagram spécifique au produit sur vos pages produits (généralement via les hooks `displayProductTab` ou `displayProductExtraContent`).
    - *Lorsqu'il est désactivé :* Aucun flux Instagram n'apparaîtra sur les pages produits.
  - **Valeur recommandée :** OUI, car c'est l'une des fonctionnalités principales du module et un puissant outil de conversion.
  - **Scénario/exemple pour le marchand :** Vous vendez des chaussures et vous souhaitez afficher des photos Instagram de personnes portant *ce modèle de chaussure spécifique* sur sa page produit. Vous activeriez ceci.
- **Afficher dans la colonne de gauche :**

  - **Ce que fait ce paramètre :** Contrôle si le flux Instagram apparaît dans la colonne latérale gauche de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un flux sera rendu dans la colonne de gauche sur les pages où il est accroché.
    - *Lorsqu'il est désactivé :* Aucun flux dans la colonne de gauche.
  - **Valeur recommandée :** NON, sauf si vous avez un besoin de conception très spécifique. Les colonnes peuvent devenir encombrées.
  - **Scénario/exemple pour le marchand :** Vous souhaitez un petit flux persistant visible lorsque les clients parcourent les catégories.
- **Afficher dans la colonne de droite :**

  - **Ce que fait ce paramètre :** Contrôle si le flux Instagram apparaît dans la colonne latérale droite de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un flux sera rendu dans la colonne de droite sur les pages où il est accroché.
    - *Lorsqu'il est désactivé :* Aucun flux dans la colonne de droite.
  - **Valeur recommandée :** NON, sauf si vous avez un besoin de conception très spécifique. Les colonnes peuvent devenir encombrées.
  - **Scénario/exemple pour le marchand :** Similaire à la colonne de gauche, pour un flux persistant et plus petit.
- **Afficher dans le pied de page :**

  - **Ce que fait ce paramètre :** Contrôle si le flux Instagram apparaît dans la zone du pied de page de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un flux sera rendu dans le pied de page.
    - *Lorsqu'il est désactivé :* Aucun flux dans le pied de page.
  - **Valeur recommandée :** OUI, pour une manière subtile mais efficace de présenter votre Instagram. C'est moins intrusif que les colonnes.
  - **Scénario/exemple pour le marchand :** Vous souhaitez ajouter une section visuellement attrayante en bas de chaque page, encourageant les visiteurs à explorer votre Instagram.
- **Afficher dans l'en-tête (gauche) :**

  - **Ce que fait ce paramètre :** Contrôle si le flux Instagram apparaît dans la partie gauche de l'en-tête de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un flux sera rendu dans la section gauche de l'en-tête.
    - *Lorsqu'il est désactivé :* Aucun flux dans l'en-tête.
  - **Valeur recommandée :** NON, les en-têtes sont généralement réservés à la navigation et à l'image de marque.
  - **Scénario/exemple pour le marchand :** Conception très spécifique où vous souhaitez une petite icône Instagram rotative ou une seule image dans l'en-tête.
- **Afficher dans l'en-tête (droite) :**

  - **Ce que fait ce paramètre :** Contrôle si le flux Instagram apparaît dans la partie droite de l'en-tête de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un flux sera rendu dans la section droite de l'en-tête.
    - *Lorsqu'il est désactivé :* Aucun flux dans l'en-tête.
  - **Valeur recommandée :** NON, les en-têtes sont généralement réservés à la navigation et à l'image de marque.
  - **Scénario/exemple pour le marchand :** Similaire à l'en-tête (gauche).
- **Fonctionnalité Carrousel :**

  - **Ce que fait ce paramètre :** Active ou désactive la fonctionnalité de carrousel (galerie coulissante) pour les flux Instagram.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les photos s'afficheront dans un carrousel horizontal et défilable, économisant de l'espace et permettant aux utilisateurs de parcourir facilement de nombreuses images.
    - *Lorsqu'il est désactivé :* Les photos s'afficheront probablement dans une grille statique ou une liste, selon le modèle.
  - **Valeur recommandée :** OUI, pour la plupart des emplacements (page d'accueil, page produit) car il est économe en espace et attrayant.
  - **Scénario/exemple pour le marchand :** Vous avez 9 photos pour un produit, mais seulement de la place pour 3 à la fois. L'activation du carrousel permet aux clients de faire défiler les 9 photos.
- **Fonctionnalité Fancybox :**

  - **Ce que fait ce paramètre :** Active ou désactive l'effet « Fancybox », qui est une bibliothèque JavaScript populaire qui affiche les images dans une fenêtre contextuelle élégante et superposée lorsqu'elles sont cliquées.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Cliquer sur une photo Instagram dans le flux l'ouvrira dans une grande fenêtre contextuelle élégante, permettant aux clients de voir les détails sans quitter la page.
    - *Lorsqu'il est désactivé :* Cliquer sur une image peut l'ouvrir directement dans un nouvel onglet de navigateur ou simplement ne rien faire, selon le thème.
  - **Valeur recommandée :** OUI, car cela offre une bien meilleure expérience utilisateur pour la visualisation des images.
  - **Scénario/exemple pour le marchand :** Un client voit une superbe tenue sur Instagram dans votre flux. Cliquer dessus ouvre une vue grande et claire de la photo, ce qui facilite l'appréciation des détails.

#### Paramètres spécifiques à la page produit (onglet Back Office produit)

Après l'installation du module, vous trouverez un nouveau champ ou onglet lors de l'édition d'un produit dans votre Back Office PrestaShop :

- **Hashtag Instagram (par produit) :**
  - **Ce que fait ce paramètre :** Ce champ vous permet de spécifier un hashtag Instagram unique pour chaque produit individuel. Le module utilisera ensuite ce hashtag pour récupérer les photos pertinentes de votre compte Instagram.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'un hashtag est saisi (par exemple, #monnomdeproduit) :* Le flux Instagram sur cette page produit spécifique affichera les photos de votre compte Instagram qui sont taguées avec `#monnomdeproduit`.
    - *Lorsqu'il est laissé vide :* Aucun flux Instagram spécifique au produit ne sera affiché pour ce produit, même si « Afficher sur la page produit » est activé.
  - **Valeur recommandée :** Un hashtag unique et descriptif pour chaque produit. Assurez-vous d'utiliser ce hashtag de manière cohérente dans vos publications Instagram.
  - **Scénario/exemple pour le marchand :** Pour un produit appelé « Robe Brise d'Été », vous pourriez saisir `#RobeBriseDEte` ou `#MaMarqueRobeDEte`. Ensuite, lorsque vous publiez des photos de cette robe sur Instagram, vous incluez ce hashtag. Le module affichera alors ces photos sur la page produit de la robe.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Config du module | Jeton d'accès Instagram | Votre jeton valide | Se connecte à l'API Instagram pour récupérer les photos. **CRITIQUE.** |
| Config du module | ID utilisateur Instagram | Votre ID utilisateur valide | Identifie votre compte Instagram pour la récupération des données. |
| Config du module | Nombre de photos à afficher | 6-9 | Contrôle le nombre de photos affichées dans une instance de flux. |
| Config du module | Afficher sur la page d'accueil | OUI | Affiche un flux général sur la page d'accueil de votre boutique. |
| Config du module | Afficher sur la page produit | OUI | Affiche un flux spécifique au produit sur les pages produits. |
| Config du module | Afficher dans la colonne de gauche | NON | Affiche un flux dans la barre latérale gauche. Peut encombrer la mise en page. |
| Config du module | Afficher dans la colonne de droite | NON | Affiche un flux dans la barre latérale droite. Peut encombrer la mise en page. |
| Config du module | Afficher dans le pied de page | OUI | Affiche un flux dans le pied de page de la boutique. Bon pour une promotion subtile. |
| Config du module | Afficher dans l'en-tête (gauche) | NON | Affiche un flux dans l'en-tête gauche. Généralement non recommandé. |
| Config du module | Afficher dans l'en-tête (droite) | NON | Affiche un flux dans l'en-tête droit. Généralement non recommandé. |
| Config du module | Fonctionnalité Carrousel | OUI | Affiche les photos dans une galerie coulissante, économisant de l'espace. |
| Config du module | Fonctionnalité Fancybox | OUI | Ouvre les photos dans une fenêtre contextuelle élégante pour une meilleure visualisation. |
| Page d'édition produit | Hashtag Instagram | Unique par produit | Définit le hashtag pour récupérer les photos de *ce produit spécifique*. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : Mon flux Instagram n'affiche aucune photo. Que dois-je faire ?**
R :

1. **Vérifiez votre jeton d'accès Instagram et votre ID utilisateur :** Ce sont les coupables les plus courants. Assurez-vous qu'ils sont correctement saisis dans la configuration du module et qu'ils sont toujours valides. Les jetons Instagram peuvent expirer, vous devrez peut-être les régénérer.
2. **Vérifiez les hashtags :** Pour les pages produits, assurez-vous que le champ « Hashtag Instagram » est rempli pour le produit spécifique et que vous avez réellement des publications sur Instagram utilisant ce hashtag exact.
3. **Compte public :** Assurez-vous que votre compte Instagram est public. Le module ne peut pas récupérer les photos des comptes privés.
4. **Videz le cache :** Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop et videz le cache Smarty (et éventuellement, tous les caches). Parfois, d'anciennes données mises en cache empêchent l'affichage de nouveau contenu.
5. **Vérifiez les limites de l'API :** Instagram a des limites de taux d'API. Si vous récupérez trop fréquemment ou si vous avez un très grand nombre de produits, vous pourriez atteindre ces limites temporairement.

**Q : Les images s'affichent, mais elles ont l'air étranges ou cassent la mise en page de mon thème.**
R :

1. **Conflits de thème :** Votre thème PrestaShop personnalisé peut avoir des styles CSS conflictuels. C'est un problème courant avec les modules tiers.
2. **CSS du module :** Le module inclut son propre CSS (`instagramfeed/css/css.css`, `instagramfeed/lib/src/css/lightslider.css`). Votre webmaster ou développeur peut inspecter la page pour identifier les styles conflictuels et écrire des remplacements CSS personnalisés dans la feuille de style de votre thème.
3. **Dimensions des images :** Assurez-vous que les images que vous publiez sur Instagram sont de qualité et de rapport d'aspect raisonnables. Bien que le module essaie de s'adapter, des images extrêmement larges ou hautes peuvent causer des problèmes d'affichage.

**Q : Comment obtenir un jeton d'accès Instagram et un ID utilisateur ?**
R : L'accès à l'API d'Instagram a changé au fil du temps. Vous avez généralement besoin d'un compte professionnel Instagram et d'un compte développeur Facebook. Le processus implique la création d'une application Facebook, sa connexion à votre compte professionnel Instagram, puis la génération d'un jeton. Il existe également des outils tiers (recherchez « Générateur de jeton d'accès Instagram ») qui peuvent simplifier ce processus, mais utilisez toujours des outils réputés.

**Q : Puis-je afficher différents flux sur différentes pages (par exemple, un flux général sur la page d'accueil et des flux spécifiques aux produits) ?**
R : Oui, absolument ! C'est la fonctionnalité principale. Utilisez le paramètre « Afficher sur la page d'accueil » pour un flux général (qui tirera généralement d'un hashtag par défaut ou de votre flux utilisateur principal), puis utilisez le champ « Hashtag Instagram » sur les pages produits individuelles pour les flux spécifiques aux produits.

**Q : Le carrousel ou Fancybox ne fonctionne pas.**
R :

1. **Activez les fonctionnalités :** Vérifiez que les fonctionnalités « Carrousel » et « Fancybox » sont activées dans la configuration du module.
2. **Conflits JavaScript :** Un autre module ou votre thème pourrait charger des bibliothèques JavaScript conflictuelles (par exemple, un autre script de carrousel ou de lightbox). Votre webmaster devrait déboguer cela à l'aide de la console de développement du navigateur (recherchez les erreurs JavaScript).
3. **jQuery :** Assurez-vous que jQuery est correctement chargé sur votre boutique, car de nombreuses fonctionnalités JavaScript en dépendent.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module `Flux de tags de produits Instagram` suit une architecture de module PrestaShop standard, tirant principalement parti de la classe `Module` pour la configuration et du système de `Hook` pour l'affichage en front-office. Il intègre une classe personnalisée pour l'interaction avec l'API Instagram et utilise des bibliothèques JavaScript externes (lightslider, fancybox) pour une UI/UX améliorée. La logique principale du module réside dans son fichier `index.php` principal, gérant la configuration, l'installation et l'enregistrement des hooks. Le rendu en front-office est réalisé en transmettant des données aux templates Smarty enregistrés sur divers hooks d'affichage.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient **pas** de contrôleurs front-office ou back-office dédiés. Toute la configuration est gérée via la méthode `getContent()` dans le fichier principal du module, et l'affichage en front-office est géré directement via les hooks enregistrés.

### 4.3 Classes et modèles principaux (`classes/`)

- `instagramfeed/classes/index.php` :

  - Il s'agit généralement d'un fichier vide ou d'un fichier contenant `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../"); exit;` pour empêcher la liste directe des répertoires. Il ne contient aucune logique de classe fonctionnelle.
- `instagramfeed/classes/instagram_class.php` :

  - **Nom de la classe** : `Instagram`
  - **Classe parente** : Aucune (classe utilitaire autonome)
  - **Responsabilité** : Cette classe encapsule la logique d'interaction avec l'API Instagram. Elle est responsable d'effectuer des requêtes HTTP pour récupérer des médias basés sur l'ID utilisateur et les hashtags, de gérer les jetons d'accès et d'analyser les réponses JSON d'Instagram.
  - **Méthodes publiques clés** :
    - `__construct($access_token, $user_id)` : Constructeur, s'initialise avec le jeton d'accès Instagram et l'ID utilisateur.
    - `getMediaByHashtag($hashtag, $count)` : Récupère un nombre spécifié d'éléments multimédias de l'API Instagram qui sont tagués avec le hashtag donné et associés à l'ID utilisateur configuré. Renvoie un tableau d'objets multimédias.
    - `getMediaByUser($count)` : Récupère un nombre spécifié d'éléments multimédias directement du flux de l'utilisateur (si pris en charge par la version de l'API et la portée du jeton).
    - (Potentiellement d'autres méthodes d'aide pour les appels API, la gestion des erreurs, etc.)

### 4.4 Actifs JavaScript (`views/js/`)

- `instagramfeed/js/if_carousell.js` :
  - **Portée** : Front-office.
  - **Description** : Ce script initialise et configure probablement la fonctionnalité de carrousel `lightslider` pour les flux Instagram. Il se lie à des éléments DOM spécifiques (par exemple, `ul` avec une certaine classe) et applique le comportement du carrousel, y compris les paramètres de réactivité, de lecture automatique, de navigation, etc.
  - **Dépendances** : Repose sur `lightslider.js` et jQuery.
- `instagramfeed/js/if_fancybox.js` :
  - **Portée** : Front-office.
  - **Description** : Ce script initialise et configure la fonctionnalité de lightbox Fancybox. Il cible les liens d'image dans le flux Instagram (par exemple, les balises `a` enveloppant les balises `img`) et leur permet de s'ouvrir dans une fenêtre contextuelle Fancybox lorsqu'elles sont cliquées, offrant une vue plus grande et plus immersive de l'image.
  - **Dépendances** : Repose sur la bibliothèque Fancybox (non incluse dans ce module, mais censée être chargée par le thème ou un autre module) et jQuery.
- `instagramfeed/js/if_sliding.js` :
  - **Portée** : Front-office.
  - **Description** : Ce fichier pourrait être un script alternatif ou supplémentaire pour la fonctionnalité de glissement, éventuellement pour les anciennes versions de PrestaShop ou des mises en page spécifiques. Compte tenu de `if_carousell.js` et `lightslider.js`, il pourrait s'agir d'un script hérité ou d'un wrapper pour des comportements de glissement spécifiques non couverts par le carrousel principal.
  - **Dépendances** : Probablement jQuery.
- `instagramfeed/js/ps14.js` :
  - **Portée** : Front-office (spécifiquement pour la compatibilité PrestaShop 1.4).
  - **Description** : Ce script contient probablement des correctifs de compatibilité ou des polyfills pour les anciens environnements PrestaShop 1.4, traitant des différences JavaScript potentielles ou des versions/fonctionnalités jQuery manquantes par rapport aux nouvelles versions de PrestaShop.
  - **Dépendances** : jQuery.
- `instagramfeed/lib/src/js/lightslider.js` :
  - **Portée** : Front-office.
  - **Description** : Il s'agit de la bibliothèque de plugins jQuery `lightslider` principale. Elle fournit la fonctionnalité de création de carrousels et de curseurs de contenu réactifs et tactiles. `if_carousell.js` appellerait généralement des méthodes de cette bibliothèque.
  - **Dépendances** : jQuery.

### 4.5 Feuilles de style CSS (`views/css/`)

- `instagramfeed/css/css.css` :
  - **Portée** : Style client en front-office.
  - **Description** : Contient des règles CSS personnalisées spécifiques à la mise en page du flux Instagram, au dimensionnement des images, à l'espacement et à l'apparence générale dans les différents hooks. Il définit des classes pour le conteneur du flux, les éléments d'image individuels et potentiellement les légendes ou les liens.
  - **Sélecteurs de classe CSS clés** : Les développeurs peuvent inspecter le code HTML généré pour trouver des classes comme `.instagram-feed-container`, `.instagram-item`, `.instagram-image`, etc., qui peuvent être remplacées dans le `custom.css` ou `theme.css` du thème.
- `instagramfeed/lib/src/css/lightslider.css` :
  - **Portée** : Style client en front-office.
  - **Description** : Il s'agit de la feuille de style par défaut du plugin jQuery `lightslider`. Elle fournit le style essentiel pour les flèches de navigation du carrousel, les points de pagination, les transitions de diapositives et le comportement réactif.
  - **Sélecteurs de classe CSS clés** : Des classes comme `.lightSlider`, `.lSAction`, `.lSPager`, etc., qui peuvent être personnalisées pour correspondre à l'image de marque de la boutique.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates d'administration (`views/templates/admin/`)** :

  - `instagramfeed/views/templates/admin/instagram_feed.tpl` : Ce template est rendu par la méthode `getContent()` dans le fichier principal du module. Il affiche le formulaire de configuration du back-office du module, y compris les champs de saisie pour le jeton d'accès Instagram, l'ID utilisateur, le nombre de photos et divers interrupteurs d'affichage (page d'accueil, page produit, colonnes, pied de page, en-tête, carrousel, fancybox). Il utilise généralement les composants de formulaire d'aide de PrestaShop.
- **Templates de hook (`views/templates/hook/`)** :

  - `instagramfeed/views/templates/hook/column-feed.tpl` : Rend le flux Instagram lorsqu'il est accroché à `displayLeftColumn` ou `displayRightColumn`. Il affiche généralement une version plus compacte du flux.
  - `instagramfeed/views/templates/hook/feed.tpl` : Un template de flux à usage général, probablement utilisé pour l'affichage principal de la page d'accueil ou du pied de page. Il contient la structure de base pour l'affichage des images Instagram, potentiellement enveloppées dans un conteneur de carrousel.
  - `instagramfeed/views/templates/hook/header-left.tpl` : Rend le flux lorsqu'il est accroché à `displayHeaderLeft`.
  - `instagramfeed/views/templates/hook/header-right.tpl` : Rend le flux lorsqu'il est accroché à `displayHeaderRight`.
  - `instagramfeed/views/templates/hook/homepage-feed.tpl` : Spécifiquement conçu pour le hook `displayHome`, présentant souvent une mise en page plus proéminente ou plus large pour la page d'accueil.
  - `instagramfeed/views/templates/hook/tab.tpl` : Rend le titre de l'onglet pour le flux Instagram sur la page produit (par exemple, « Photos Instagram »). Ceci est généralement accroché à `displayProductTab` (PrestaShop 1.6) ou `displayProductExtraContent` (PrestaShop 1.7+).
  - `instagramfeed/views/templates/hook/tabcontents.tpl` : Rend le contenu réel du flux Instagram dans l'onglet de la page produit. Ce template contiendra la logique pour afficher les images récupérées à l'aide du hashtag spécifique au produit, en utilisant souvent les fonctionnalités de carrousel et de fancybox.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne crée pas de tables SQL personnalisées.
  - Les paramètres de configuration (Jeton d'accès, ID utilisateur, options d'affichage, etc.) sont stockés dans la table `ps_configuration` à l'aide de clés telles que `INSTAGRAMFEED_ACCESS_TOKEN`, `INSTAGRAMFEED_USER_ID`, `INSTAGRAMFEED_NUM_PHOTOS`, etc.
  - Le hashtag Instagram spécifique au produit est stocké dans la table `ps_product_lang` (ou une table similaire liée au produit) en tant que nouveau champ ajouté par le module lors de l'installation. Ce champ serait généralement nommé `instagram_hashtag` ou similaire.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Utilisé pour charger les actifs CSS et JavaScript (lightslider, fancybox, scripts personnalisés) requis pour les flux Instagram. |
| `displayHome` | Sur la page d'accueil de la boutique. | Rend le flux Instagram général sur la page d'accueil. |
| `displayLeftColumn` | Dans la barre latérale gauche des pages où il est activé. | Rend un flux Instagram compact dans la colonne de gauche. |
| `displayRightColumn` | Dans la barre latérale droite des pages où il est activé. | Rend un flux Instagram compact dans la colonne de droite. |
| `displayFooter` | Dans la section du pied de page de la boutique. | Rend un flux Instagram général dans le pied de page. |
| `displayHeaderLeft` | Dans la partie gauche de l'en-tête de la boutique. | Rend un petit flux Instagram dans l'en-tête. |
| `displayHeaderRight` | Dans la partie droite de l'en-tête de la boutique. | Rend un petit flux Instagram dans l'en-tête. |
| `displayProductTab` (PS 1.6) | Sur la page produit, pour ajouter de nouveaux onglets. | Rend le titre de l'onglet du flux Instagram sur la page produit. |
| `displayProductTabContent` (PS 1.6) | Sur la page produit, pour ajouter du contenu aux onglets. | Rend le contenu (le flux Instagram réel) dans l'onglet de la page produit. |
| `displayProductExtraContent` (PS 1.7+) | Sur la page produit, pour ajouter des blocs de contenu supplémentaires. | Hook alternatif pour PrestaShop 1.7+ pour afficher le flux Instagram sur les pages produit, souvent comme un nouveau bloc sous les informations principales du produit. |
| `actionProductUpdate` | Après la mise à jour d'un produit dans le Back Office. | Utilisé pour enregistrer la valeur du champ `instagram_hashtag` pour le produit. |
| `actionProductAdd` | Après l'ajout d'un nouveau produit dans le Back Office. | Utilisé pour enregistrer la valeur du champ `instagram_hashtag` pour le nouveau produit. |
| `displayAdminProductsExtra` | Dans la page d'édition de produit dans le Back Office. | Rend le champ de saisie pour le « Hashtag Instagram » sur la page de configuration du produit. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à fournir une assistance et à garantir le fonctionnement optimal de votre module.
