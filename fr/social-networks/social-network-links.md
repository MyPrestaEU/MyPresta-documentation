---
title: "Liens vers les réseaux sociaux - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Liens vers les réseaux sociaux par MyPresta.eu."
sidebar:
  label: "Liens vers les réseaux sociaux - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Social Network Links sur MyPresta.eu](https://mypresta.eu/modules/social-networks/social-network-links.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/social-network-links/)
>
> ---


# Liens vers les réseaux sociaux

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes et habituellement préinstallées sur la plupart des environnements d'hébergement web.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Liens vers les réseaux sociaux)

Ceci est l'écran de configuration principal et unique du module « Liens vers les réseaux sociaux ». Ici, vous définirez quels réseaux sociaux afficher et où ils apparaissent sur votre boutique.

**Accès :** Naviguez vers **Modules > Gestionnaire de modules**, recherchez « Liens vers les réseaux sociaux », et cliquez sur « Configurer ».

#### **Paramètres généraux**

- **URL Facebook :**

  - **Ce que fait ce paramètre :** C'est ici que vous entrez l'adresse web complète (URL) de votre page Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est rempli :* Une icône Facebook apparaîtra dans le bloc du module, renvoyant directement à l'URL que vous avez fournie.
    - *Lorsqu'il est vide :* Aucune icône Facebook ne sera affichée.
  - **Valeur recommandée :** L'URL de votre page Facebook officielle (par exemple, `https://www.facebook.com/nomdevotreboutique`).
  - **Scénario / exemple pour le marchand :** Si votre page Facebook est `https://www.facebook.com/MaSuperBoutique`, entrez cette URL ici. Les clients qui cliquent sur l'icône Facebook seront dirigés vers votre page.
- **URL Twitter :**

  - **Ce que fait ce paramètre :** Entrez l'adresse web complète (URL) de votre profil Twitter.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est rempli :* Une icône Twitter apparaîtra, renvoyant à votre profil Twitter.
    - *Lorsqu'il est vide :* Aucune icône Twitter ne sera affichée.
  - **Valeur recommandée :** L'URL de votre profil Twitter officiel (par exemple, `https://twitter.com/nomdevotreboutique`).
  - **Scénario / exemple pour le marchand :** Si votre nom d'utilisateur Twitter est `@MaSuperBoutique`, votre URL pourrait être `https://twitter.com/MaSuperBoutique`.
- **URL YouTube :**

  - **Ce que fait ce paramètre :** Entrez l'adresse web complète (URL) de votre chaîne YouTube.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est rempli :* Une icône YouTube apparaîtra, renvoyant à votre chaîne.
    - *Lorsqu'il est vide :* Aucune icône YouTube ne sera affichée.
  - **Valeur recommandée :** L'URL de votre chaîne YouTube officielle (par exemple, `https://www.youtube.com/channel/votredidentifiantdechaîne`).
  - **Scénario / exemple pour le marchand :** Si vous avez des vidéos de présentation de produits ou des tutoriels sur YouTube, liez votre chaîne ici.
- **URL Google+ :**

  - **Ce que fait ce paramètre :** Entrez l'adresse web complète (URL) de votre profil ou page Google+.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est rempli :* Une icône Google+ apparaîtra, renvoyant à votre profil.
    - *Lorsqu'il est vide :* Aucune icône Google+ ne sera affichée.
  - **Valeur recommandée :** L'URL de votre profil/page Google+ officiel (par exemple, `https://plus.google.com/+NomDeVotreBoutique`).
  - **Scénario / exemple pour le marchand :** Bien que Google+ soit largement obsolète, si vous maintenez toujours une présence ou avez du contenu hérité, vous pouvez le lier ici. Sinon, laissez-le vide.
- **URL RSS :**

  - **Ce que fait ce paramètre :** Entrez l'adresse web complète (URL) de votre flux RSS. Ceci est généralement utilisé pour les blogs ou les sections d'actualités afin de permettre aux utilisateurs de s'abonner aux mises à jour.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est rempli :* Une icône RSS apparaîtra, renvoyant à votre flux.
    - *Lorsqu'il est vide :* Aucune icône RSS ne sera affichée.
  - **Valeur recommandée :** Si votre boutique a un blog ou une section d'actualités avec un flux RSS, entrez son URL (par exemple, `https://votreboutique.com/blog/feed`). Sinon, laissez vide.
  - **Scénario / exemple pour le marchand :** Si vous publiez régulièrement des articles de blog sur vos produits ou votre secteur, fournir un flux RSS permet aux clients avertis de recevoir directement les mises à jour.

#### **Paramètres d'affichage**

- **Afficher dans l'en-tête :**

  - **Ce que fait ce paramètre :** Contrôle si le bloc de liens vers les réseaux sociaux apparaît dans la section d'en-tête de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (Oui) :* Le bloc de liens sociaux sera visible en haut de votre site web.
    - *Lorsqu'il est désactivé (Non) :* Le bloc n'apparaîtra pas dans l'en-tête.
  - **Valeur recommandée :** **Oui**, si vous souhaitez une grande visibilité pour vos liens sociaux.
  - **Scénario / exemple pour le marchand :** Activez ceci si vous souhaitez que les clients voient immédiatement votre présence sociale dès qu'ils arrivent sur votre site.
- **Afficher dans la colonne de gauche :**

  - **Ce que fait ce paramètre :** Contrôle si le bloc de liens vers les réseaux sociaux apparaît dans la barre latérale gauche de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (Oui) :* Le bloc de liens sociaux sera visible dans la colonne de gauche (si votre thème en a une).
    - *Lorsqu'il est désactivé (Non) :* Le bloc n'apparaîtra pas dans la colonne de gauche.
  - **Valeur recommandée :** **Non**, sauf si vous avez une raison spécifique de le placer là et que votre thème prend en charge une colonne de gauche. Souvent, la colonne de droite ou le pied de page est préféré.
  - **Scénario / exemple pour le marchand :** Si votre thème a une colonne de gauche proéminente et que vous souhaitez que les liens restent visibles pendant que les clients parcourent les catégories, activez ceci.
- **Afficher dans la colonne de droite :**

  - **Ce que fait ce paramètre :** Contrôle si le bloc de liens vers les réseaux sociaux apparaît dans la barre latérale droite de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (Oui) :* Le bloc de liens sociaux sera visible dans la colonne de droite (si votre thème en a une).
    - *Lorsqu'il est désactivé (Non) :* Le bloc n'apparaîtra pas dans la colonne de droite.
  - **Valeur recommandée :** **Oui**, si vous souhaitez afficher les liens dans une barre latérale.
  - **Scénario / exemple pour le marchand :** Une bonne option pour maintenir les liens sociaux visibles sans trop encombrer l'en-tête ou le pied de page.
- **Afficher dans le pied de page :**

  - **Ce que fait ce paramètre :** Contrôle si le bloc de liens vers les réseaux sociaux apparaît dans la section de pied de page de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (Oui) :* Le bloc de liens sociaux sera visible en bas de votre site web.
    - *Lorsqu'il est désactivé (Non) :* Le bloc n'apparaîtra pas dans le pied de page.
  - **Valeur recommandée :** **Oui**, car le pied de page est un endroit standard et attendu pour les liens de médias sociaux.
  - **Scénario / exemple pour le marchand :** Activez ceci pour fournir un emplacement cohérent pour les liens sociaux que les clients recherchent souvent en bas d'une page.
- **Afficher sur la page produit :**

  - **Ce que fait ce paramètre :** Contrôle si le bloc de liens vers les réseaux sociaux apparaît sur les pages de produits individuelles.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (Oui) :* Le bloc de liens sociaux sera visible sur chaque page de détail de produit.
    - *Lorsqu'il est désactivé (Non) :* Le bloc n'apparaîtra pas sur les pages de produits.
  - **Valeur recommandée :** **Oui**, si vous souhaitez encourager le partage social ou le suivi directement depuis les pages de produits.
  - **Scénario / exemple pour le marchand :** Si vous souhaitez que les clients trouvent facilement vos médias sociaux pendant qu'ils envisagent un achat, activez ceci.

#### 2.1.1 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | URL Facebook | Vide / URL de votre page Facebook | Lien vers votre profil Facebook. Vide = pas d'icône. |
| Configuration du module | URL Twitter | Vide / URL de votre profil Twitter | Lien vers votre profil Twitter. Vide = pas d'icône. |
| Configuration du module | URL YouTube | Vide / URL de votre chaîne YouTube | Lien vers votre chaîne YouTube. Vide = pas d'icône. |
| Configuration du module | URL Google+ | Vide / URL de votre profil Google+ | Lien vers votre profil Google+. Vide = pas d'icône. |
| Configuration du module | URL RSS | Vide / URL de votre flux RSS | Lien vers votre flux RSS. Vide = pas d'icône. |
| Configuration du module | Afficher dans l'en-tête | Non / Oui | Afficher les liens sociaux dans l'en-tête de la boutique. |
| Configuration du module | Afficher dans la colonne de gauche | Non / Non | Afficher les liens sociaux dans la barre latérale gauche. |
| Configuration du module | Afficher dans la colonne de droite | Non / Oui | Afficher les liens sociaux dans la barre latérale droite. |
| Configuration du module | Afficher dans le pied de page | Non / Oui | Afficher les liens sociaux dans le pied de page de la boutique. |
| Configuration du module | Afficher sur la page produit | Non / Oui | Afficher les liens sociaux sur les pages de produits individuelles. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

- **Q : Mes icônes sociales n'apparaissent pas après la configuration.**

  - **R :** Tout d'abord, vérifiez que vous avez bien saisi les URL complètes de vos réseaux sociaux dans la configuration du module. Assurez-vous également d'avoir sélectionné au moins une option « Afficher dans... » (par exemple, « Afficher dans le pied de page » sur Oui). Enfin, videz le cache de votre PrestaShop sous **Paramètres avancés > Performances** (cliquez sur le bouton « Vider le cache »). Parfois, la mise en cache du thème peut également empêcher les modifications d'apparaître immédiatement.
- **Q : Les icônes s'affichent, mais elles semblent mal alignées ou ne correspondent pas à mon thème.**

  - **R :** Le module fournit un style de base. Si votre thème a des règles CSS très spécifiques, elles pourraient remplacer ou entrer en conflit avec les styles du module.
    - **Solution 1 (Basique) :** Essayez de vider le cache de votre navigateur (Ctrl+F5 ou Cmd+R).
    - **Solution 2 (Avancée) :** Cela nécessite généralement qu'un webmaster ou un développeur inspecte le CSS de votre thème et ajoute potentiellement des règles CSS personnalisées au fichier `custom.css` de votre thème pour ajuster l'apparence. Le fichier CSS du module (`socialnetworklinks.css`) peut servir de référence.
- **Q : Puis-je ajouter d'autres réseaux sociaux non listés (par exemple, Instagram, Pinterest) ?**

  - **R :** La version actuelle du module prend en charge Facebook, Twitter, YouTube, Google+ et RSS. Pour ajouter d'autres réseaux, cela nécessiterait un développement personnalisé pour modifier le code du module et ajouter de nouvelles icônes et champs de saisie. Alternativement, recherchez un module de médias sociaux plus complet si vous avez besoin d'une gamme plus large de plateformes.
- **Q : Les liens s'ouvrent dans le même onglet, mais je veux qu'ils s'ouvrent dans un nouvel onglet.**

  - **R :** Par défaut, le module est conçu pour ouvrir les liens dans un nouvel onglet (`target="_blank"`). Si cela ne se produit pas, cela peut être dû à un conflit avec le JavaScript de votre thème ou à un navigateur plus ancien. Assurez-vous que votre PrestaShop et votre navigateur sont à jour. Si le problème persiste, un développeur devra inspecter le code HTML généré.
- **Q : J'ai activé « Afficher dans la colonne de gauche/droite », mais rien n'apparaît.**

  - **R :** De nombreux thèmes PrestaShop modernes sont conçus sans colonnes gauche ou droite traditionnelles sur toutes les pages, en particulier sur les pages de produits ou la page d'accueil. Si votre thème ne rend pas ces colonnes, le module n'aura pas d'endroit pour afficher son bloc. Vérifiez la documentation de votre thème ou personnalisez sa mise en page pour activer les colonnes où vous souhaitez que le module apparaisse. Le pied de page et l'en-tête sont généralement des emplacements d'affichage plus fiables sur tous les thèmes.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Liens vers les réseaux sociaux » est un module PrestaShop simple suivant un modèle de type MVC de base dans le cadre du module. Il utilise principalement la classe `Module` pour ses fonctionnalités principales, sa configuration et l'enregistrement des hooks. Il stocke ses paramètres directement dans la table `ps_configuration` de PrestaShop. L'affichage front-office du module est géré via un seul template Smarty rendu via divers hooks d'affichage.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient **pas** de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la configuration est gérée directement dans la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne contient **pas** de classes personnalisées ou de définitions `ObjectModel`. Toute la logique est encapsulée dans la classe principale `SocialNetworkLinks`.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module ne contient **pas** de fichiers JavaScript personnalisés. La fonctionnalité d'ouverture des liens dans de nouveaux onglets est gérée directement dans le HTML du template à l'aide de `target="_blank"`.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`socialnetworklinks/css/socialnetworklinks.css`**
  - **Portée :** Style client Front-office.
  - **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :** Cette feuille de style fournit l'apparence visuelle de base pour les icônes de médias sociaux, y compris leur taille, leur espacement et potentiellement les effets de survol. Elle cible le bloc de conteneur principal et les éléments de lien social individuels.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger dans leur thème :**
    - `.socialnetworklinks_block` : Le conteneur principal du bloc de liens sociaux.
    - `.socialnetworklinks_block ul` : La liste non ordonnée contenant les icônes sociales.
    - `.socialnetworklinks_block li` : Éléments de liste individuels pour chaque icône sociale.
    - `.socialnetworklinks_block li a` : La balise d'ancrage pour chaque lien social.
    - `.socialnetworklinks_block li a i` : L'élément d'icône (par exemple, Font Awesome ou similaire, selon le thème).
    - Des classes spécifiques pour chaque réseau social (par exemple, `.facebook`, `.twitter`, etc.) peuvent être présentes ou peuvent être ajoutées pour un style personnalisé par réseau.

### 4.6 Structure du template Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :
  - **`socialnetworklinks/views/front/column.tpl`** :
    - **Hook(s) rendu(s) dans :** `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (ou un hook de page produit similaire selon la version de PrestaShop et le thème).
    - **Sortie du bloc visuel :** Ce template rend la structure HTML pour le bloc de liens vers les réseaux sociaux. Il itère sur les URL des réseaux sociaux configurées et affiche une icône (généralement à l'aide d'une bibliothèque d'icônes de police comme Font Awesome, qui est généralement fournie par le thème ou le cœur de PrestaShop) pour chaque lien actif. Chaque icône est enveloppée dans une balise `<a>` avec `target="_blank"` pour ouvrir le lien dans un nouvel onglet.
    - **Variables disponibles :**
      - `$facebook_url` : L'URL Facebook configurée.
      - `$twitter_url` : L'URL Twitter configurée.
      - `$youtube_url` : L'URL YouTube configurée.
      - `$google_url` : L'URL Google+ configurée.
      - `$rss_url` : L'URL RSS configurée.
      - `$module_dir` : Le répertoire de base du module, utile pour lier les actifs du module (bien que peu utilisé dans ce template spécifique).

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :
  Le module ne crée aucune table de base de données personnalisée. Tous les paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide de clés préfixées par `SOCIALNETWORKLINKS_`.

  - `PS_SOCIALNETWORKLINKS_FACEBOOK_URL`
  - `PS_SOCIALNETWORKLINKS_TWITTER_URL`
  - `PS_SOCIALNETWORKLINKS_YOUTUBE_URL`
  - `PS_SOCIALNETWORKLINKS_GOOGLE_URL`
  - `PS_SOCIALNETWORKLINKS_RSS_URL`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_HEADER`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_LEFT_COLUMN`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_RIGHT_COLUMN`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_FOOTER`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_PRODUCT_PAGE`
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rend le contenu dans la section `<head>` ou tout en haut du `<body>`. | Utilisé pour afficher le bloc de liens sociaux dans l'en-tête de la boutique. |
| `displayLeftColumn` | Rend le contenu dans la barre latérale gauche. | Utilisé pour afficher le bloc de liens sociaux dans la colonne de gauche. |
| `displayRightColumn` | Rend le contenu dans la barre latérale droite. | Utilisé pour afficher le bloc de liens sociaux dans la colonne de droite. |
| `displayFooter` | Rend le contenu dans le pied de page de la boutique. | Utilisé pour afficher le bloc de liens sociaux dans le pied de page. |
| `displayProductButtons` (ou hook de page produit similaire) | Rend le contenu sur la page produit, souvent près du bouton « Ajouter au panier » ou de la description du produit. | Utilisé pour afficher le bloc de liens sociaux sur les pages de produits individuelles. |
| `moduleRoutes` | (Géré implicitement par PrestaShop pour la configuration du module) | Non directement utilisé pour l'affichage front-office, mais fait partie du cycle de vie du module. |
| `actionAdminControllerSetMedia` | (Géré implicitement par PrestaShop pour la configuration du module) | Utilisé pour charger le CSS/JS dans le back office pour la page de configuration du module. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Liens vers les réseaux sociaux », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
