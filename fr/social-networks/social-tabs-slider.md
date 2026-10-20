---
title: "Curseur d'onglets sociaux - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Curseur d'onglets sociaux par MyPresta.eu."
sidebar:
  label: "Curseur d'onglets sociaux - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Social tabs slider sur MyPresta.eu](https://mypresta.eu/modules/social-networks/social-tabs-slider.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/social-tabs-slider/)
>
> ---


# Curseur d'onglets sociaux

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et assurent une communication correcte avec les API des médias sociaux.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran principal où vous configurerez toutes les options de votre Curseur d'onglets sociaux.

#### Paramètres généraux

-   **Modèle :**

    -   **Ce que fait ce paramètre :** Cela vous permet de choisir le style visuel et le design de vos onglets sociaux. Le module est livré avec plusieurs modèles prédéfinis.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur Modèle 1, 2, 3, etc. :* L'apparence des icônes sociales, le design de l'onglet et potentiellement le style d'animation changeront sur votre front office.
    -   **Valeur recommandée :** Expérimentez pour trouver celui qui correspond le mieux au thème de votre boutique.
    -   **Scénario / exemple de marchand :** Si votre boutique a un design minimaliste, vous pourriez choisir un modèle avec des icônes épurées et plates. Si vous préférez un look plus vibrant, un autre modèle pourrait offrir des icônes colorées et brillantes.
-   **Position :**

    -   **Ce que fait ce paramètre :** Détermine où le curseur d'onglets sociaux apparaîtra sur votre site web.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur « Gauche » :* Le curseur sera fixé sur le côté gauche de la fenêtre du navigateur.
        -   *Lorsqu'il est défini sur « Droite » :* Le curseur sera fixé sur le côté droit de la fenêtre du navigateur.
    -   **Valeur recommandée :** « Gauche » ou « Droite » selon la disposition de votre thème et l'endroit où il interfère le moins avec d'autres éléments.
    -   **Scénario / exemple de marchand :** Si votre thème a une barre latérale gauche, vous pourriez choisir « Droite » pour éviter l'encombrement. Si votre thème est large et centré, « Gauche » ou « Droite » pourrait bien fonctionner.
-   **Dernier onglet ouvert par défaut :**

    -   **Ce que fait ce paramètre :** Contrôle si l'un des onglets sociaux doit s'ouvrir automatiquement lorsqu'un visiteur arrive pour la première fois sur votre page.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur « OUI » :* Le dernier onglet social qui a été ouvert par un visiteur précédent (ou un onglet par défaut s'il n'y a pas d'historique) s'ouvrira automatiquement lorsqu'un nouveau visiteur arrive.
        -   *Lorsqu'il est défini sur « NON » :* Tous les onglets sociaux resteront fermés jusqu'à ce que le visiteur clique ou survole activement l'un d'eux.
    -   **Valeur recommandée :** « NON » pour éviter de potentiellement ennuyer les visiteurs avec un onglet qui s'ouvre automatiquement.
    -   **Scénario / exemple de marchand :** Vous pourriez le définir sur « OUI » temporairement si vous menez une campagne spéciale sur un réseau social et que vous souhaitez attirer immédiatement l'attention sur celle-ci, mais généralement, « NON » offre une meilleure expérience utilisateur.

#### Paramètres de la boîte "J'aime" Facebook

-   **Afficher la boîte "J'aime" Facebook :**

    -   **Ce que fait ce paramètre :** Active ou désactive la visibilité de l'onglet Facebook et de sa boîte "J'aime" intégrée.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé (OUI) :* L'onglet Facebook apparaîtra dans le curseur, et lorsqu'il sera ouvert, il affichera la boîte "J'aime" de votre page de fans Facebook.
        -   *Lorsqu'il est désactivé (NON) :* L'onglet Facebook ne sera pas affiché dans le curseur.
    -   **Valeur recommandée :** « OUI » si vous avez une page Facebook active que vous souhaitez promouvoir.
    -   **Scénario / exemple de marchand :** Si Facebook est un canal principal pour l'interaction client et le marketing, vous voudrez certainement l'activer.
-   **Hauteur de la boîte "J'aime" Facebook :**

    -   **Ce que fait ce paramètre :** Définit la taille verticale de la zone de contenu de la boîte "J'aime" Facebook lorsque l'onglet est ouvert.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur une valeur plus élevée (par exemple, 500px) :* Plus de contenu (publications, visages) de votre page Facebook sera visible dans l'onglet.
        -   *Lorsqu'il est défini sur une valeur plus basse (par exemple, 200px) :* Moins de contenu sera visible, nécessitant un défilement si le flux est long.
    -   **Valeur recommandée :** Commencez par `280px` et ajustez en fonction de la quantité de contenu que vous souhaitez afficher et de son apparence sur votre site.
    -   **Scénario / exemple de marchand :** Si vous publiez fréquemment et que vous souhaitez que les visiteurs voient plus de votre activité récente, augmentez la hauteur.
-   **Schéma de couleurs de la boîte "J'aime" Facebook :**

    -   **Ce que fait ce paramètre :** Modifie le thème de couleur de la boîte "J'aime" Facebook elle-même (pas l'icône de l'onglet).
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur « Clair » :* L'arrière-plan et le texte de la boîte "J'aime" utiliseront des couleurs plus claires.
        -   *Lorsqu'il est défini sur « Sombre » :* L'arrière-plan et le texte de la boîte "J'aime" utiliseront des couleurs plus foncées.
    -   **Valeur recommandée :** Choisissez « Clair » ou « Sombre » pour correspondre au mieux au design général de votre boutique.
    -   **Scénario / exemple de marchand :** Si votre site web a un arrière-plan sombre, un schéma de couleurs « Sombre » pour la boîte "J'aime" pourrait mieux s'intégrer visuellement.
-   **Afficher les visages de la boîte "J'aime" Facebook :**

    -   **Ce que fait ce paramètre :** Détermine si les photos de profil des personnes qui aiment votre page sont affichées dans la boîte "J'aime".
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé (OUI) :* Une rangée de photos de profil des fans de votre page sera affichée.
        -   *Lorsqu'il est désactivé (NON) :* Les photos de profil ne seront pas affichées.
    -   **Valeur recommandée :** « OUI » car cela ajoute un élément de preuve sociale, montrant que de vraies personnes aiment votre page.
    -   **Scénario / exemple de marchand :** L'affichage des visages peut encourager d'autres personnes à aimer votre page, car cela démontre sa popularité.
-   **Couleur de la bordure de la boîte "J'aime" Facebook :**

    -   **Ce que fait ce paramètre :** Définit la couleur de la bordure autour de la boîte "J'aime" Facebook.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur une couleur spécifique (par exemple, #CCCCCC) :* La bordure apparaîtra dans cette couleur.
    -   **Valeur recommandée :** Une couleur qui complète le design de votre site web ou qui est transparente/invisible si vous préférez.
    -   **Scénario / exemple de marchand :** Vous pourriez utiliser la couleur principale de votre marque pour la bordure afin de renforcer l'image de marque.
-   **Afficher le flux de la boîte "J'aime" Facebook :**

    -   **Ce que fait ce paramètre :** Contrôle si vos publications Facebook récentes (le « flux ») sont affichées dans la boîte "J'aime".
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé (OUI) :* Vos dernières publications Facebook seront visibles dans l'onglet.
        -   *Lorsqu'il est désactivé (NON) :* Seul le bouton « J'aime » et potentiellement les visages seront affichés, sans le flux de publications.
    -   **Valeur recommandée :** « OUI » pour fournir du contenu frais et encourager l'engagement.
    -   **Scénario / exemple de marchand :** Si vous partagez régulièrement des nouvelles, des promotions ou des mises à jour de produits sur Facebook, l'affichage du flux tient les visiteurs informés.
-   **Afficher l'en-tête de la boîte "J'aime" Facebook :**

    -   **Ce que fait ce paramètre :** Active ou désactive la visibilité de l'en-tête « Retrouvez-nous sur Facebook » en haut de la boîte "J'aime".
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé (OUI) :* L'en-tête sera affiché.
        -   *Lorsqu'il est désactivé (NON) :* L'en-tête sera masqué, rendant la boîte "J'aime" plus compacte.
    -   **Valeur recommandée :** « OUI » pour plus de clarté, ou « NON » si vous souhaitez un look plus épuré et supposez que les utilisateurs comprennent qu'il s'agit de Facebook.
    -   **Scénario / exemple de marchand :** Si l'espace est limité, masquer l'en-tête peut économiser de l'espace vertical.
-   **URL de la page de fans Facebook :**

    -   **Ce que fait ce paramètre :** C'est le paramètre le plus crucial pour Facebook. Vous devez saisir l'URL complète de votre page de fans Facebook.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est correctement saisi :* L'onglet Facebook affichera la boîte "J'aime" pour votre page spécifiée.
        -   *Lorsqu'il est incorrect ou vide :* L'onglet Facebook peut ne pas s'afficher correctement ou affichera une erreur.
    -   **Valeur recommandée :** L'URL exacte de votre page de fans Facebook (par exemple, `https://www.facebook.com/MyPresta`).
    -   **Scénario / exemple de marchand :** Copiez et collez l'URL directement depuis votre navigateur lorsque vous consultez votre page Facebook pour garantir l'exactitude.

#### Paramètres Google+

-   **Afficher le suivi Google+ :**

    -   **Ce que fait ce paramètre :** Active ou désactive la visibilité de l'onglet Google+ et de son bouton de suivi/profil intégré.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé (OUI) :* L'onglet Google+ apparaîtra dans le curseur.
        -   *Lorsqu'il est désactivé (NON) :* L'onglet Google+ ne sera pas affiché.
    -   **Valeur recommandée :** « OUI » si vous utilisez activement Google+ (bien que son utilisation ait diminué, il pourrait toujours être pertinent pour certains niches).
    -   **Scénario / exemple de marchand :** Si votre entreprise a une forte présence sur Google My Business ou des stratégies de référencement local spécifiques impliquant Google+, cela peut être bénéfique.
-   **ID de profil Google+ :**

    -   **Ce que fait ce paramètre :** Vous devez fournir votre ID de profil Google+ (une chaîne numérique) pour que le module affiche le profil correct.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est correctement saisi :* L'onglet Google+ affichera le bouton de suivi/profil pour l'ID spécifié.
        -   *Lorsqu'il est incorrect ou vide :* L'onglet Google+ peut ne pas s'afficher correctement.
    -   **Valeur recommandée :** Votre ID de profil Google+.
    -   **Scénario / exemple de marchand :** Trouvez votre ID Google+ en naviguant vers votre page de profil Google+ et en regardant l'URL (il s'agit généralement d'une longue chaîne de chiffres).

#### Paramètres Twitter

-   **Afficher la chronologie de l'utilisateur Twitter :**

    -   **Ce que fait ce paramètre :** Active ou désactive la visibilité de l'onglet Twitter et de son widget de chronologie utilisateur intégré.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé (OUI) :* L'onglet Twitter apparaîtra dans le curseur, affichant vos tweets récents.
        -   *Lorsqu'il est désactivé (NON) :* L'onglet Twitter ne sera pas affiché.
    -   **Valeur recommandée :** « OUI » si vous avez un compte Twitter actif pour votre entreprise.
    -   **Scénario / exemple de marchand :** Si vous utilisez Twitter pour le service client, les annonces ou les ventes flash, c'est un excellent moyen de tenir les visiteurs informés.
-   **Nom d'utilisateur Twitter :**

    -   **Ce que fait ce paramètre :** Spécifie le compte Twitter dont la chronologie sera affichée.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est correctement saisi (par exemple, MyPresta) :* L'onglet Twitter affichera les tweets de ce nom d'utilisateur.
        -   *Lorsqu'il est incorrect ou vide :* L'onglet Twitter peut ne pas s'afficher correctement.
    -   **Valeur recommandée :** Votre nom d'utilisateur Twitter (sans le symbole « @ »).
    -   **Scénario / exemple de marchand :** Saisissez `MyPresta` si votre identifiant Twitter est `@MyPresta`.
-   **ID du widget Twitter :**

    -   **Ce que fait ce paramètre :** Il s'agit d'un ID unique généré par Twitter lorsque vous créez un widget de chronologie intégré. Il est crucial pour le fonctionnement du widget.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est correctement saisi :* La chronologie Twitter se chargera et s'affichera correctement.
        -   *Lorsqu'il est incorrect ou vide :* L'onglet Twitter affichera probablement une erreur ou restera vide.
    -   **Valeur recommandée :** Votre ID de widget Twitter.
    -   **Scénario / exemple de marchand :** Pour l'obtenir, allez sur [Twitter Publish](https://publish.twitter.com/), sélectionnez « Chronologie intégrée », entrez l'URL de votre profil et copiez le `data-widget-id` du code généré.

#### Paramètres YouTube

-   **Afficher le compte YouTube :**

    -   **Ce que fait ce paramètre :** Active ou désactive la visibilité de l'onglet YouTube et de son flux de chaîne/utilisateur intégré.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé (OUI) :* L'onglet YouTube apparaîtra dans le curseur.
        -   *Lorsqu'il est désactivé (NON) :* L'onglet YouTube ne sera pas affiché.
    -   **Valeur recommandée :** « OUI » si vous avez une chaîne YouTube avec des vidéos de produits, des tutoriels ou du contenu de marque.
    -   **Scénario / exemple de marchand :** Si vous vendez des produits qui bénéficient de démonstrations vidéo, c'est un excellent moyen de les présenter.
-   **Nom d'utilisateur YouTube :**

    -   **Ce que fait ce paramètre :** Spécifie la chaîne ou l'utilisateur YouTube dont les vidéos seront affichées.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est correctement saisi :* L'onglet YouTube affichera le contenu de cette chaîne/utilisateur.
        -   *Lorsqu'il est incorrect ou vide :* L'onglet YouTube peut ne pas s'afficher correctement.
    -   **Valeur recommandée :** Le nom de l'URL personnalisée de votre chaîne YouTube ou votre ancien nom d'utilisateur.
    -   **Scénario / exemple de marchand :** Si l'URL de votre chaîne YouTube est `youtube.com/user/MyPrestaVideos`, votre nom d'utilisateur serait `MyPrestaVideos`. Si c'est `youtube.com/c/MyPresta`, vous devrez peut-être trouver l'ancien nom d'utilisateur ou l'ID de la chaîne.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | **Modèle** | (Choisissez le meilleur ajustement) | Modifie le style visuel des onglets sociaux. |
| | **Position** | Droite | Détermine si les onglets apparaissent sur le côté gauche ou droit du navigateur. |
| | **Dernier onglet ouvert par défaut** | NON | Contrôle si un onglet s'ouvre automatiquement au chargement de la page. |
| | **Afficher la boîte "J'aime" Facebook** | OUI | Affiche/masque l'onglet Facebook. |
| | **Hauteur de la boîte "J'aime" Facebook** | 280px | Définit la hauteur de la zone de contenu Facebook. |
| | **Schéma de couleurs de la boîte "J'aime" Facebook** | Clair | Modifie le thème de couleur de la boîte "J'aime" Facebook. |
| | **Afficher les visages de la boîte "J'aime" Facebook** | OUI | Affiche les photos de profil des fans. |
| | **Couleur de la bordure de la boîte "J'aime" Facebook** | (vide/transparent) | Définit la couleur de la bordure de la boîte "J'aime". |
| | **Afficher le flux de la boîte "J'aime" Facebook** | OUI | Affiche les publications Facebook récentes. |
| | **Afficher l'en-tête de la boîte "J'aime" Facebook** | OUI | Affiche/masque l'en-tête « Retrouvez-nous sur Facebook ». |
| | **URL de la page de fans Facebook** | (Votre URL Facebook) | **CRITIQUE :** URL de votre page de fans Facebook. |
| | **Afficher le suivi Google+** | NON | Affiche/masque l'onglet Google+. |
| | **ID de profil Google+** | (Votre ID Google+) | **CRITIQUE :** Votre ID de profil numérique Google+. |
| | **Afficher la chronologie de l'utilisateur Twitter** | OUI | Affiche/masque l'onglet Twitter. |
| | **Nom d'utilisateur Twitter** | (Votre identifiant Twitter) | **CRITIQUE :** Votre nom d'utilisateur Twitter (par exemple, `MyPresta`). |
| | **ID du widget Twitter** | (Votre ID de widget Twitter) | **CRITIQUE :** ID unique de votre widget de chronologie Twitter. |
| | **Afficher le compte YouTube** | OUI | Affiche/masque l'onglet YouTube. |
| | **Nom d'utilisateur YouTube** | (Votre nom d'utilisateur YouTube) | **CRITIQUE :** Le nom d'utilisateur ou l'ID hérité de votre chaîne YouTube. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Les onglets sociaux n'apparaissent pas sur ma boutique, ou seulement certains d'entre eux sont affichés.**
**R1 :**

-   **Vérifier le statut du module :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que « Curseur d'onglets sociaux » est installé et activé.
-   **Vérifier la configuration :** Allez sur la page de configuration du module. Assurez-vous que « Afficher la boîte "J'aime" Facebook », « Afficher le suivi Google+ », etc., sont définis sur « OUI » pour les onglets que vous souhaitez afficher.
-   **ID/URL corrects :** Vérifiez à nouveau que votre URL de page de fans Facebook, votre ID de profil Google+, votre nom d'utilisateur/ID de widget Twitter et votre nom d'utilisateur YouTube sont saisis *exactement* comme requis. Une seule faute de frappe empêchera l'onglet de se charger.
-   **Compatibilité du thème :** Certains thèmes très personnalisés peuvent avoir des problèmes avec les hooks de module. Essayez de passer temporairement au thème PrestaShop par défaut pour voir si les onglets apparaissent. Si c'est le cas, votre thème pourrait nécessiter des ajustements mineurs.
-   **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). Parfois, d'anciens fichiers mis en cache empêchent l'affichage du nouveau contenu du module.

**Q2 : Mon onglet Facebook/Twitter/YouTube affiche une erreur ou est vide lorsqu'il est ouvert.**
**R2 :**

-   **ID/URL incorrects :** C'est la raison la plus courante. Revérifiez chaque caractère de votre URL de page de fans Facebook, de votre ID de profil Google+, de votre nom d'utilisateur Twitter, de votre ID de widget Twitter et de votre nom d'utilisateur YouTube. Même une barre oblique manquante ou un espace supplémentaire peut causer des problèmes.
-   **Modifications d'API :** Les plateformes de médias sociaux mettent occasionnellement à jour leurs API ou leurs codes d'intégration. Assurez-vous que la version de votre module est à jour depuis MyPresta.eu.
-   **Paramètres de confidentialité :** Assurez-vous que vos pages/profils de médias sociaux sont publics et accessibles. S'ils sont définis sur privé, le module ne pourra pas afficher leur contenu.
-   **Problèmes de réseau :** Désactivez temporairement tout bloqueur de publicités ou extension de navigateur qui pourrait interférer avec les widgets de médias sociaux.

**Q3 : Les onglets sociaux semblent étranges ou mal alignés sur mon appareil mobile.**
**R3 :**

-   **Réactivité du thème :** Bien que le module soit conçu pour être réactif, son apparence peut être affectée par la réactivité globale du thème de votre PrestaShop.
-   **Conflits CSS :** Le CSS de votre thème pourrait remplacer le style du module. Si vous avez un webmaster, il peut inspecter les éléments à l'aide des outils de développement du navigateur pour identifier les conflits.
-   **Modèle de module :** Essayez de passer à un « Modèle » différent dans la configuration du module pour voir si l'un s'adapte mieux au mobile.
-   **Vider le cache :** Videz toujours le cache de votre PrestaShop après avoir effectué des modifications de configuration.

**Q4 : Comment obtenir mon ID de widget Twitter ?**
**R4 :**

1.  Allez sur [Twitter Publish](https://publish.twitter.com/).
2.  Sélectionnez « Chronologie intégrée ».
3.  Entrez l'URL complète de votre profil Twitter (par exemple, `https://twitter.com/MyPresta`).
4.  Cliquez sur la flèche, puis sélectionnez « Chronologie intégrée ».
5.  Twitter générera un code. Recherchez `data-widget-id="VOTRE_ID_WIDGET_ICI"` dans ce code. Copiez uniquement l'ID numérique.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Curseur d'onglets sociaux » est un module PrestaShop classique implémenté comme un seul fichier PHP (`socialslider.php`) suivant la structure des modules PrestaShop. Il utilise le système de hooks de PrestaShop pour injecter son CSS, son JavaScript et son contenu HTML dans le front office. La configuration est gérée via la méthode `getContent()` dans la classe principale du module, stockant les paramètres dans `ps_configuration`. Le module utilise des bibliothèques JavaScript externes (jscolor) et des scripts personnalisés pour gérer l'animation de glissement et le chargement des widgets de médias sociaux.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise **pas** de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la logique est encapsulée dans le fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit **pas** de classes personnalisées et n'étend pas `ObjectModel`. Toute la logique principale réside dans la classe `Socialslider` dans `socialslider.php`. Les valeurs de configuration sont stockées directement dans la table `ps_configuration` à l'aide de `Configuration::get()` et `Configuration::updateValue()`.

### 4.4 Actifs JavaScript (`views/js/`)

Le module inclut plusieurs fichiers JavaScript pour gérer ses fonctionnalités :

-   `socialslider/jscolor/jscolor.js`
    -   **Portée :** Back-office (utilisé dans `getContent()` pour l'entrée du sélecteur de couleurs).
    -   **Responsabilité :** Fournit une fonctionnalité de sélecteur de couleurs JavaScript pour les champs de saisie, spécifiquement pour le paramètre de couleur de bordure Facebook.
-   `socialslider/left.js`
    -   **Portée :** Front-office.
    -   **Responsabilité :** Contient la logique JavaScript pour l'animation de glissement et l'interaction des onglets lorsque le curseur est positionné sur le côté **gauche** de l'écran. Il gère l'ouverture/fermeture des onglets, le chargement dynamique du contenu des médias sociaux et potentiellement la gestion des cookies pour la fonction « dernier onglet ouvert ».
-   `socialslider/right.js`
    -   **Portée :** Front-office.
    -   **Responsabilité :** Contient la logique JavaScript pour l'animation de glissement et l'interaction des onglets lorsque le curseur est positionné sur le côté **droit** de l'écran. Similaire à `left.js` mais adapté pour un positionnement à droite.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module utilise une approche basée sur des modèles pour son style, avec des fichiers CSS séparés pour chaque modèle et position.

-   `socialslider/templates/1/css/left.css`
    -   **Portée :** Front-office (pour le modèle 1, position gauche).
    -   **Responsabilité :** Définit les styles visuels pour les onglets sociaux, les icônes et le conteneur du curseur lorsque le modèle 1 est sélectionné et que le curseur est à gauche.
    -   **Sélecteurs clés :** `.socialslider_left`, `.socialslider_tab`, `.socialslider_tab_icon`, `.socialslider_content`.
-   `socialslider/templates/1/css/right.css`
    -   **Portée :** Front-office (pour le modèle 1, position droite).
    -   **Responsabilité :** Définit les styles visuels pour les onglets sociaux, les icônes et le conteneur du curseur lorsque le modèle 1 est sélectionné et que le curseur est à droite.
    -   **Sélecteurs clés :** `.socialslider_right`, `.socialslider_tab`, `.socialslider_tab_icon`, `.socialslider_content`.
-   `socialslider/templates/2/css/left.css`
    -   **Portée :** Front-office (pour le modèle 2, position gauche).
    -   **Responsabilité :** Style pour le modèle 2, position gauche.
-   `socialslider/templates/2/css/right.css`
    -   **Portée :** Front-office (pour le modèle 2, position droite).
    -   **Responsabilité :** Style pour le modèle 2, position droite.
-   `socialslider/templates/3/css/left.css`
    -   **Portée :** Front-office (pour le modèle 3, position gauche).
    -   **Responsabilité :** Style pour le modèle 3, position gauche.
-   `socialslider/templates/3/css/right.css`
    -   **Portée :** Front-office (pour le modèle 3, position droite).
    -   **Responsabilité :** Style pour le modèle 3, position droite.
-   `socialslider/templates/4/css/left.css`
    -   **Portée :** Front-office (pour le modèle 4, position gauche).
    -   **Responsabilité :** Style pour le modèle 4, position gauche.
-   `socialslider/templates/4/css/right.css`
    -   **Portée :** Front-office (pour le modèle 4, position droite).
    -   **Responsabilité :** Style pour le modèle 4, position droite.
-   `socialslider/templates/5/css/left.css`
    -   **Portée :** Front-office (pour le modèle 5, position gauche).
    -   **Responsabilité :** Style pour le modèle 5, position gauche.
-   `socialslider/templates/5/css/right.css`
    -   **Portée :** Front-office (pour le modèle 5, position droite).
    -   **Responsabilité :** Style pour le modèle 5, position droite.
-   `socialslider/templates/6/css/left.css`
    -   **Portée :** Front-office (pour le modèle 6, position gauche).
    -   **Responsabilité :** Style pour le modèle 6, position gauche.
-   `socialslider/templates/6/css/right.css`
    -   **Portée :** Front-office (pour le modèle 6, position droite).
    -   **Responsabilité :** Style pour le modèle 6, position droite.

Les développeurs peuvent remplacer ces styles dans le `custom.css` de leur thème ou en créant un thème enfant.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module utilise des modèles Smarty pour rendre son contenu front-office et pour le formulaire de configuration back-office.

-   **Modèles de hook (`views/templates/hook/`)** :
    -   `socialslider/header.tpl`
        -   **Hook :** `displayHeader`
        -   **Sortie :** Ce modèle est responsable de l'inclusion des fichiers CSS et JavaScript nécessaires dynamiquement en fonction de la configuration du module (par exemple, chargement de `left.js` ou `right.js`, et du CSS spécifique au modèle correct). Il inclut également les SDK/widgets Facebook, Twitter et Google+ s'ils sont activés.
    -   `socialslider/top.tpl`
        -   **Hook :** `displayTop`
        -   **Sortie :** C'est le modèle principal qui rend la structure HTML du curseur d'onglets sociaux lui-même. Il génère les éléments `div` pour le conteneur du curseur, les onglets individuels (Facebook, Google+, Twitter, YouTube) et leurs zones de contenu respectives, en les remplissant avec les valeurs de configuration.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    Le module ne crée aucune table SQL personnalisée. Tous les paramètres de configuration sont stockés dans la table standard `ps_configuration` de PrestaShop.

    -   `ps_configuration` (ou `_configuration` avec votre préfixe) : Stocke les paires clé-valeur pour les paramètres du module, par exemple, `SS_TEMPLATE`, `SS_POSITION`, `SS_FCB_FANPAGEURL`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Injecte les fichiers CSS et JavaScript du module, ainsi que les SDK/scripts de widgets des plateformes de médias sociaux (SDK Facebook, script de widget Twitter, script Google+). |
| `displayTop` | Généralement tout en haut de la zone de contenu, sous l'en-tête principal. | Rend la structure HTML principale du curseur d'onglets sociaux (le conteneur fixe, les onglets individuels et leurs zones de contenu). |
| `header` | (Alias de `displayHeader` dans certaines versions de PrestaShop, ou utilisé pour les thèmes plus anciens) | Identique à `displayHeader`, assure la compatibilité pour l'injection d'actifs. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, les corrections de bugs et le support développeur pour le module « Curseur d'onglets sociaux », veuillez vous référer à votre compte client MyPresta.eu. Vous pouvez télécharger les dernières versions et accéder aux ressources de support directement depuis l'historique de vos commandes.
