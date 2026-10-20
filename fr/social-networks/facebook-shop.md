---
title: "Boutique Facebook - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Boutique Facebook par MyPresta.eu."
sidebar:
  label: "Boutique Facebook - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Facebook Shop sur MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-shop.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/facebook-shop/)
>
> ---


# Boutique Facebook

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).
- **Page Fan Facebook** : Vous devez avoir une Page Fan Facebook active (pas un profil personnel) dont vous êtes administrateur.
- **Certificat SSL** : Votre boutique PrestaShop doit avoir un certificat SSL actif (HTTPS) pour que la Boutique Facebook fonctionne correctement, car Facebook exige des connexions sécurisées pour les applications intégrées.

## 2. Présentation complète de la configuration (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal de votre module Boutique Facebook. Vous trouverez une série d'onglets ou de sections pour personnaliser l'apparence et le fonctionnement de votre boutique sur Facebook.

#### Onglet Paramètres généraux (ou vue initiale similaire)

- **Afficher les mises à jour MyPresta.eu :**

  - **Ce que fait ce paramètre :** Contrôle si vous voyez les notifications de mises à jour de MyPresta.eu directement dans la configuration de votre module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Vous recevrez des alertes pour les nouvelles versions ou les nouvelles importantes de MyPresta.eu, vous aidant à maintenir votre module à jour.
    - *Lorsqu'désactivé :* Vous ne verrez pas ces notifications, ce qui pourrait signifier que vous manquerez des mises à jour importantes ou des corrections de bugs.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple marchand :** Gardez ceci activé pour vous assurer d'être toujours informé des dernières améliorations et correctifs de sécurité pour votre module Boutique Facebook.
- **Affichage de la langue de la Boutique Facebook :** (`faceshop_lang_disp`)

  - **Ce que fait ce paramètre :** Détermine si le sélecteur de langue est visible dans votre Boutique Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients peuvent changer la langue de votre Boutique Facebook, utile pour les boutiques internationales.
    - *Lorsqu'désactivé :* La boutique s'affichera dans la langue par défaut, ou la langue détectée par Facebook, sans sélecteur explicite.
  - **Valeur recommandée :** OUI (si vous avez plusieurs langues activées dans PrestaShop)
  - **Scénario / exemple marchand :** Si vous vendez à des clients dans différents pays et avez traduit votre boutique PrestaShop, activez ceci pour leur permettre de naviguer dans leur langue préférée.
- **Affichage de la devise de la Boutique Facebook :** (`faceshop_curr_disp`)

  - **Ce que fait ce paramètre :** Détermine si le sélecteur de devise est visible dans votre Boutique Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients peuvent changer la devise affichée dans votre Boutique Facebook, utile pour les boutiques internationales.
    - *Lorsqu'désactivé :* La boutique affichera les prix dans votre devise par défaut.
  - **Valeur recommandée :** OUI (si vous avez plusieurs devises activées dans PrestaShop)
  - **Scénario / exemple marchand :** Si vous acceptez les paiements en USD, EUR et GBP, activez ceci pour que les clients puissent voir les prix dans leur devise locale.
- **Activer la réécriture de module (URL conviviales pour le SEO) :** (`faceshop_modrew`)

  - **Ce que fait ce paramètre :** Contrôle si le module utilise des URL conviviales pour le SEO au sein de la Boutique Facebook, similaires à celles de votre boutique PrestaShop principale.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les URL des produits et des catégories au sein de la Boutique Facebook seront propres et descriptives (par exemple, `votreboutique.com/produit/mon-super-produit`). Ceci est généralement meilleur pour le SEO et l'expérience utilisateur.
    - *Lorsqu'désactivé :* Les URL pourraient être moins lisibles (par exemple, `votreboutique.com/index.php?id_product=123`).
  - **Valeur recommandée :** OUI
  - **Scénario / exemple marchand :** Activez toujours ceci pour une meilleure visibilité dans les moteurs de recherche et un aspect plus professionnel pour vos liens de produits partagés depuis Facebook.

#### Onglet Paramètres de la page d'accueil

- **Afficher le nombre d'articles sur la page d'accueil :** (`faceshop_homepage_itemcount`)

  - **Ce que fait ce paramètre :** Définit le nombre de produits à afficher sur la page d'accueil de votre Boutique Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini à 10 :* La page d'accueil de votre Boutique Facebook affichera 10 produits.
    - *Lorsqu'il est défini à 20 :* La page d'accueil de votre Boutique Facebook affichera 20 produits.
  - **Valeur recommandée :** 12-24 (suffisant pour montrer de la variété sans surcharger la page).
  - **Scénario / exemple marchand :** Si vous souhaitez présenter un large éventail de produits immédiatement, définissez un nombre plus élevé. Si vous préférez un look plus épuré avec moins d'articles plus proéminents, définissez un nombre plus bas.
- **Afficher les produits en promotion sur la page d'accueil :** (`faceshop_homepage_disphot`)

  - **Ce que fait ce paramètre :** Contrôle si les produits en promotion (en solde) sont mis en avant sur la page d'accueil de votre Boutique Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les produits actuellement en solde seront affichés de manière proéminente, encourageant les achats impulsifs.
    - *Lorsqu'désactivé :* Seuls les produits à prix régulier apparaîtront sur la page d'accueil (sauf si d'autres options d'affichage sont activées).
  - **Valeur recommandée :** OUI
  - **Scénario / exemple marchand :** Utilisez ceci pour attirer l'attention sur vos promotions et écouler votre stock.
- **Afficher les nouveaux produits sur la page d'accueil :** (`faceshop_homepage_dispnew`)

  - **Ce que fait ce paramètre :** Contrôle si vos nouveaux produits sont mis en avant sur la page d'accueil de votre Boutique Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les produits récemment ajoutés seront présentés, gardant votre boutique fraîche et excitante pour les visiteurs réguliers.
    - *Lorsqu'désactivé :* Les nouveaux produits n'auront pas de section dédiée sur la page d'accueil.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple marchand :** Si vous ajoutez fréquemment de nouveaux articles, c'est un excellent moyen de les mettre en évidence et d'encourager les visites répétées.
- **Afficher la catégorie racine de la page d'accueil :** (`faceshop_homepage_root`)

  - **Ce que fait ce paramètre :** Vous permet de sélectionner une catégorie racine spécifique pour afficher les produits sur la page d'accueil de votre Boutique Facebook. S'il est laissé vide, il affichera les produits de votre catégorie racine PrestaShop par défaut.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'une catégorie spécifique est sélectionnée :* Seuls les produits de cette catégorie et de ses sous-catégories apparaîtront sur la page d'accueil.
    - *Lorsqu'il est laissé vide :* Les produits de la catégorie racine par défaut de l'ensemble de votre boutique seront pris en compte pour l'affichage sur la page d'accueil.
  - **Valeur recommandée :** Laisser vide, sauf si vous avez une stratégie marketing spécifique.
  - **Scénario / exemple marchand :** Si vous menez une campagne spéciale pour la "Collection d'été" et que vous ne voulez que ces produits sur la page d'accueil de votre Boutique Facebook, vous sélectionneriez la catégorie "Collection d'été" ici.

#### Onglet Paramètres de l'en-tête

- **Afficher l'en-tête dans la Boutique Facebook :** (`faceshop_header_disp`)
  - **Ce que fait ce paramètre :** Contrôle si la section d'en-tête de votre boutique PrestaShop (logo, barre de recherche, résumé du panier) est visible dans la Boutique Facebook intégrée.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Votre Boutique Facebook aura un en-tête familier, la faisant ressembler davantage à votre boutique principale.
    - *Lorsqu'désactivé :* L'en-tête sera masqué, offrant un look plus minimaliste.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple marchand :** Garder l'en-tête visible aide à maintenir la cohérence de la marque et fournit des éléments de navigation essentiels comme la barre de recherche.

#### Onglet Paramètres de la page de catégorie

- **Catégorie racine pour la Boutique Facebook :** (`faceshop_cat_root`)

  - **Ce que fait ce paramètre :** Définit la catégorie principale à partir de laquelle votre Boutique Facebook commencera à afficher les produits et les catégories. Cela agit comme la "racine" pour la navigation de votre Boutique Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque "Accueil" (racine PrestaShop par défaut) est sélectionné :* Toutes les catégories et tous les produits de l'ensemble de votre boutique seront accessibles.
    - *Lorsqu'une catégorie spécifique (par exemple, "Vêtements") est sélectionnée :* Seuls "Vêtements" et ses sous-catégories/produits seront visibles dans la Boutique Facebook.
  - **Valeur recommandée :** "Accueil" (ou la catégorie racine de votre boutique principale) sauf si vous souhaitez limiter la portée de votre Boutique Facebook.
  - **Scénario / exemple marchand :** Si vous ne souhaitez vendre qu'une ligne de produits spécifique (par exemple, "Électronique") sur Facebook, vous définiriez ceci sur votre catégorie "Électronique".
- **Afficher les nouveaux produits sur les pages de catégorie :** (`faceshop_cat_dispnew`)

  - **Ce que fait ce paramètre :** Contrôle si les nouveaux produits sont mis en évidence ou ont une section dédiée sur les pages de liste de catégories au sein de votre Boutique Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients parcourant les catégories repéreront facilement les articles récemment ajoutés.
    - *Lorsqu'désactivé :* Les nouveaux produits apparaîtront simplement dans la liste régulière sans emphase particulière.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple marchand :** Aide les clients à découvrir vos dernières nouveautés même lorsqu'ils parcourent des types de produits spécifiques.
- **Afficher les produits en promotion sur les pages de catégorie :** (`faceshop_cat_disphot`)

  - **Ce que fait ce paramètre :** Contrôle si les produits en promotion sont mis en évidence ou ont une section dédiée sur les pages de liste de catégories au sein de votre Boutique Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients parcourant les catégories repéreront facilement les articles en solde.
    - *Lorsqu'désactivé :* Les produits en promotion apparaîtront simplement dans la liste régulière sans emphase particulière.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple marchand :** Encourage les achats en rendant les articles en solde plus visibles dans les catégories pertinentes.
- **Nombre d'articles par page de catégorie :** (`faceshop_cat_itemcount`)

  - **Ce que fait ce paramètre :** Définit le nombre de produits à afficher par page lorsque les clients parcourent les catégories dans votre Boutique Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini à 12 :* Chaque page de catégorie affichera 12 produits avant la pagination.
    - *Lorsqu'il est défini à 30 :* Chaque page de catégorie affichera 30 produits.
  - **Valeur recommandée :** 12-24 (standard pour la plupart des sites e-commerce).
  - **Scénario / exemple marchand :** Un nombre plus élevé réduit les clics mais peut rendre les pages plus lentes à charger. Un nombre plus bas nécessite plus de clics mais peut sembler moins accablant.
- **Style d'affichage des catégories :** (`faceshop_cat_dispstyle`)

  - **Ce que fait ce paramètre :** Détermine comment les catégories sont présentées dans la Boutique Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Option A (par exemple, "Vue en grille") :* Les catégories sont affichées sous forme de grille d'images/noms.
    - *Option B (par exemple, "Vue en liste") :* Les catégories sont affichées sous forme de liste verticale.
  - **Valeur recommandée :** Vue en grille (souvent plus attrayante visuellement).
  - **Scénario / exemple marchand :** Choisissez le style qui correspond le mieux à l'esthétique de votre marque et à la façon dont vous souhaitez que les clients naviguent dans votre gamme de produits.

#### Onglet Paramètres du slider

- **Afficher le slider dans la Boutique Facebook :** (`faceshop_slider_disp`)

  - **Ce que fait ce paramètre :** Contrôle si un slider d'images (carrousel) est affiché dans votre Boutique Facebook. Ce slider présente généralement des produits vedettes, des promotions ou des bannières.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Une bannière rotative ou un slider de produits apparaîtra, attirant l'attention.
    - *Lorsqu'désactivé :* Aucun slider ne sera affiché, ce qui entraînera une mise en page statique.
  - **Valeur recommandée :** OUI (si vous avez des images attrayantes pour un slider).
  - **Scénario / exemple marchand :** Utilisez le slider pour mettre en évidence votre dernière collection, vos soldes saisonniers ou vos articles les plus vendus directement en haut de votre Boutique Facebook.
- **Temps de transition du slider (en millisecondes) :** (`faceshop_slider_time`)

  - **Ce que fait ce paramètre :** Définit la durée pendant laquelle chaque diapositive reste visible avant de passer à la suivante.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini à 3000 (3 secondes) :* Les diapositives changeront toutes les 3 secondes.
    - *Lorsqu'il est défini à 5000 (5 secondes) :* Les diapositives changeront toutes les 5 secondes.
  - **Valeur recommandée :** 4000-6000 (4-6 secondes) pour laisser aux utilisateurs suffisamment de temps pour lire.
  - **Scénario / exemple marchand :** Ajustez ceci en fonction de la quantité d'informations sur vos diapositives. Des temps plus courts pour les diapositives uniquement avec des images, plus longs pour les diapositives avec du texte.
- **Emplacement du slider :** (`faceshop_slider_place`)

  - **Ce que fait ce paramètre :** Détermine où le slider apparaît dans votre Boutique Facebook (par exemple, en haut de la page, sous les catégories).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur "Haut" :* Le slider sera la première chose que les clients verront.
    - *Lorsqu'il est défini sur "Sous les produits" :* Le slider apparaîtra plus bas sur la page.
  - **Valeur recommandée :** Haut (pour une visibilité maximale).
  - **Scénario / exemple marchand :** Placez le slider en haut pour capter immédiatement l'attention avec vos promotions les plus importantes.

#### Onglet Paramètres du menu

- **Afficher le lien Nouveaux produits dans le menu :** (`faceshop_menu_newproducts`)

  - **Ce que fait ce paramètre :** Ajoute un lien vers "Nouveaux produits" dans le menu de navigation de votre Boutique Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients peuvent facilement cliquer pour voir toutes vos dernières additions.
    - *Lorsqu'désactivé :* Ce lien spécifique n'apparaîtra pas dans le menu.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple marchand :** Essentiel pour les boutiques qui mettent fréquemment à jour leur inventaire afin d'aider les clients à découvrir de nouveaux articles.
- **Afficher le lien Produits en solde dans le menu :** (`faceshop_menu_saleproducts`)

  - **Ce que fait ce paramètre :** Ajoute un lien vers "Produits en solde" ou "Promotions" dans le menu de navigation de votre Boutique Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients peuvent rapidement trouver tous vos articles en promotion.
    - *Lorsqu'désactivé :* Ce lien spécifique n'apparaîtra pas dans le menu.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple marchand :** Idéal pour générer du trafic vers vos promotions et augmenter les ventes.
- **Afficher le lien Pages d'information dans le menu :** (`faceshop_menu_informations`)

  - **Ce que fait ce paramètre :** Ajoute un lien vers vos pages CMS (Information) de PrestaShop (par exemple, À propos de nous, Livraison, Conditions générales) dans le menu de navigation.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients peuvent accéder directement à des informations non liées aux produits.
    - *Lorsqu'désactivé :* Ces liens n'apparaîtront pas dans le menu.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple marchand :** Crucial pour établir la confiance et fournir les informations de service client nécessaires.
- **Afficher le lien Page de contact dans le menu :** (`faceshop_menu_contact`)

  - **Ce que fait ce paramètre :** Ajoute un lien vers votre page Contactez-nous de PrestaShop dans le menu de navigation.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients peuvent facilement trouver comment vous contacter.
    - *Lorsqu'désactivé :* Ce lien spécifique n'apparaîtra pas dans le menu.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple marchand :** Fournit un canal direct pour les demandes des clients, améliorant le support.
- **Style d'affichage des catégories du menu :** (`faceshop_menu_catstyle`)

  - **Ce que fait ce paramètre :** Détermine comment les catégories sont affichées dans le menu de navigation principal de votre Boutique Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Option A (par exemple, "Menu déroulant") :* Les catégories apparaissent dans un menu déroulant.
    - *Option B (par exemple, "Liste horizontale") :* Les catégories apparaissent sous forme de liste horizontale.
  - **Valeur recommandée :** Menu déroulant (pour de nombreuses catégories) ou Liste horizontale (pour peu de catégories).
  - **Scénario / exemple marchand :** Si vous avez de nombreuses catégories de produits, un menu déroulant maintient la navigation propre. Si vous n'avez que quelques catégories principales, une liste horizontale pourrait être plus directe.
- **Afficher le lien Fabricants dans le menu :** (`faceshop_menu_manuf`)

  - **Ce que fait ce paramètre :** Ajoute un lien vers votre page Fabricants de PrestaShop dans le menu de navigation.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients peuvent parcourir les produits par marque ou fabricant.
    - *Lorsqu'désactivé :* Ce lien spécifique n'apparaîtra pas dans le menu.
  - **Valeur recommandée :** OUI (si vous vendez des produits de plusieurs marques distinctes).
  - **Scénario / exemple marchand :** Si vous êtes un revendeur de diverses marques, cela aide les clients à trouver les produits de leurs fabricants préférés.

#### Onglet Paramètres de la page produit

- **Afficher le fil d'Ariane :** (`faceshop_display_breadcrumb`)

  - **Ce que fait ce paramètre :** Contrôle si le fil d'Ariane (par exemple, Accueil > Catégorie > Sous-catégorie > Produit) est affiché sur les pages de produits.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Aide les clients à comprendre leur emplacement dans la hiérarchie de la boutique et à naviguer facilement vers les catégories parentes.
    - *Lorsqu'désactivé :* Le fil d'Ariane sera masqué.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple marchand :** Améliore l'expérience utilisateur en fournissant des chemins de navigation clairs, en particulier pour les boutiques avec des structures de catégories profondes.
- **Tronquer la description du produit :** (`faceshop_pdisp_trim`)

  - **Ce que fait ce paramètre :** Si activé, il raccourcira les longues descriptions de produits sur la page produit, affichant souvent un lien "Lire la suite".
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les pages produit apparaissent plus propres, et les utilisateurs peuvent choisir d'étendre la description s'ils sont intéressés.
    - *Lorsqu'désactivé :* Les descriptions complètes des produits sont toujours affichées, ce qui peut rendre les pages très longues.
  - **Valeur recommandée :** OUI (pour les produits avec de très longues descriptions).
  - **Scénario / exemple marchand :** Empêche les pages produit d'être trop longues, en particulier sur mobile, en affichant d'abord un résumé concis.
- **Afficher le prix du produit :** (`faceshop_pdisp_price`)

  - **Ce que fait ce paramètre :** Contrôle si le prix du produit est visible sur les pages de produits.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Le prix sera clairement affiché.
    - *Lorsqu'désactivé :* Le prix sera masqué.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple marchand :** Masquer les prix n'est généralement pas recommandé pour une boutique e-commerce, sauf si vous avez une stratégie B2B spécifique nécessitant des devis. Pour la plupart des commerces de détail, les prix sont essentiels.
- **Afficher le nom du produit :** (`faceshop_pdisp_name`)

  - **Ce que fait ce paramètre :** Contrôle si le nom du produit est visible sur les pages de produits.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Le nom du produit sera affiché.
    - *Lorsqu'désactivé :* Le nom du produit sera masqué.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple marchand :** Le nom du produit est fondamental pour l'identification ; gardez toujours ceci activé.
- **Afficher l'image du produit :** (`faceshop_pdisp_image`)

  - **Ce que fait ce paramètre :** Contrôle si l'image du produit est visible sur les pages de produits.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* L'image principale du produit et les images supplémentaires seront affichées.
    - *Lorsqu'désactivé :* Les images du produit seront masquées.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple marchand :** Les images de produits sont cruciales pour les ventes en ligne ; gardez toujours ceci activé.

#### Onglet Paramètres de partage social

- **Afficher le bouton de partage Facebook :** (`faceshop_social_facebook`)

  - **Ce que fait ce paramètre :** Ajoute un bouton "Partager" Facebook aux pages de produits de votre Boutique Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients peuvent facilement partager des produits avec leurs amis Facebook, augmentant le marketing viral.
    - *Lorsqu'désactivé :* Le bouton de partage Facebook n'apparaîtra pas.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple marchand :** Encouragez les clients à faire connaître vos produits sur leurs propres fils d'actualité.
- **Afficher le bouton de partage Pinterest :** (`faceshop_social_pinterest`)

  - **Ce que fait ce paramètre :** Ajoute un bouton "Épingler" Pinterest aux pages de produits de votre Boutique Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients peuvent facilement épingler des images de produits sur leurs tableaux Pinterest, générant du trafic depuis Pinterest.
    - *Lorsqu'désactivé :* Le bouton de partage Pinterest n'apparaîtra pas.
  - **Valeur recommandée :** OUI (surtout si vos produits sont visuellement attrayants).
  - **Scénario / exemple marchand :** Idéal pour la mode, la décoration intérieure, l'artisanat et d'autres produits visuellement attrayants pour tirer parti de l'audience de Pinterest.
- **Afficher le bouton de partage Google+ :** (`faceshop_social_google`)

  - **Ce que fait ce paramètre :** Ajoute un bouton de partage Google+ aux pages de produits de votre Boutique Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients peuvent partager des produits sur Google+.
    - *Lorsqu'désactivé :* Le bouton de partage Google+ n'apparaîtra pas.
  - **Valeur recommandée :** NON (Google+ a été abandonné).
  - **Scénario / exemple marchand :** Cette plateforme n'est plus active, il est donc inutile de la maintenir activée.

#### Onglet Paramètres du pied de page

- **Afficher le pied de page dans la Boutique Facebook :** (`faceshop_footer_disp`)
  - **Ce que fait ce paramètre :** Contrôle si la section de pied de page de votre boutique PrestaShop (copyright, liens, icônes de paiement) est visible dans la Boutique Facebook intégrée.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Votre Boutique Facebook aura un pied de page familier, maintenant la cohérence de la marque et fournissant des liens supplémentaires.
    - *Lorsqu'désactivé :* Le pied de page sera masqué.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple marchand :** Le pied de page contient souvent des liens légaux importants (politique de confidentialité, conditions de service) et des informations de contact, qu'il est bon de garder visibles pour la confiance et la conformité.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Paramètres généraux** | Afficher les mises à jour MyPresta.eu | OUI | Recevoir les notifications de mise à jour du module. |
|  | Affichage de la langue de la Boutique Facebook (`faceshop_lang_disp`) | OUI | Permettre aux clients de changer la langue de la boutique. |
|  | Affichage de la devise de la Boutique Facebook (`faceshop_curr_disp`) | OUI | Permettre aux clients de changer la devise de la boutique. |
|  | Activer la réécriture de module (URL conviviales pour le SEO) (`faceshop_modrew`) | OUI | Utiliser des URL propres et descriptives pour un meilleur SEO et UX. |
| **Paramètres de la page d'accueil** | Afficher le nombre d'articles sur la page d'accueil (`faceshop_homepage_itemcount`) | 12-24 | Nombre de produits affichés sur la page d'accueil. |
|  | Afficher les produits en promotion sur la page d'accueil (`faceshop_homepage_disphot`) | OUI | Mettre en avant les produits en solde sur la page d'accueil. |
|  | Afficher les nouveaux produits sur la page d'accueil (`faceshop_homepage_dispnew`) | OUI | Mettre en avant les nouveautés sur la page d'accueil. |
|  | Afficher la catégorie racine de la page d'accueil (`faceshop_homepage_root`) | Vide (racine par défaut) | Sélectionner une catégorie spécifique pour les produits de la page d'accueil. |
| **Paramètres de l'en-tête** | Afficher l'en-tête dans la Boutique Facebook (`faceshop_header_disp`) | OUI | Afficher l'en-tête de votre boutique (logo, recherche, panier). |
| **Paramètres de la page de catégorie** | Catégorie racine pour la Boutique Facebook (`faceshop_cat_root`) | Accueil (racine par défaut) | Définit la catégorie de départ pour la Boutique Facebook. |
|  | Afficher les nouveaux produits sur les pages de catégorie (`faceshop_cat_dispnew`) | OUI | Mettre en évidence les nouveaux produits dans les catégories. |
|  | Afficher les produits en promotion sur les pages de catégorie (`faceshop_cat_disphot`) | OUI | Mettre en évidence les produits en solde dans les catégories. |
|  | Nombre d'articles par page de catégorie (`faceshop_cat_itemcount`) | 12-24 | Nombre de produits affichés par page de catégorie. |
|  | Style d'affichage des catégories (`faceshop_cat_dispstyle`) | Vue en grille | Comment les catégories sont présentées (grille/liste). |
| **Paramètres du slider** | Afficher le slider dans la Boutique Facebook (`faceshop_slider_disp`) | OUI | Afficher un slider d'images/produits. |
|  | Temps de transition du slider (en millisecondes) (`faceshop_slider_time`) | 4000-6000 | Vitesse des transitions de diapositives. |
|  | Emplacement du slider (`faceshop_slider_place`) | Haut | Position du slider (par exemple, en haut de page). |
| **Paramètres du menu** | Afficher le lien Nouveaux produits dans le menu (`faceshop_menu_newproducts`) | OUI | Ajouter "Nouveaux produits" au menu de navigation. |
|  | Afficher le lien Produits en solde dans le menu (`faceshop_menu_saleproducts`) | OUI | Ajouter "Produits en solde" au menu de navigation. |
|  | Afficher le lien Pages d'information dans le menu (`faceshop_menu_informations`) | OUI | Ajouter des liens vers les pages CMS (À propos de nous, etc.). |
|  | Afficher le lien Page de contact dans le menu (`faceshop_menu_contact`) | OUI | Ajouter un lien "Contactez-nous". |
|  | Style d'affichage des catégories du menu (`faceshop_menu_catstyle`) | Menu déroulant | Comment les catégories apparaissent dans le menu (déroulant/liste). |
|  | Afficher le lien Fabricants dans le menu (`faceshop_menu_manuf`) | OUI | Ajouter un lien vers les fabricants/marques. |
| **Paramètres de la page produit** | Afficher le fil d'Ariane (`faceshop_display_breadcrumb`) | OUI | Afficher le chemin de navigation (Accueil > Catégorie > Produit). |
|  | Tronquer la description du produit (`faceshop_pdisp_trim`) | OUI | Raccourcir les longues descriptions de produits. |
|  | Afficher le prix du produit (`faceshop_pdisp_price`) | OUI | Afficher le prix du produit. |
|  | Afficher le nom du produit (`faceshop_pdisp_name`) | OUI | Afficher le nom du produit. |
|  | Afficher l'image du produit (`faceshop_pdisp_image`) | OUI | Afficher les images du produit. |
| **Paramètres de partage social** | Afficher le bouton de partage Facebook (`faceshop_social_facebook`) | OUI | Permettre le partage sur Facebook. |
|  | Afficher le bouton de partage Pinterest (`faceshop_social_pinterest`) | OUI | Permettre le partage sur Pinterest. |
|  | Afficher le bouton de partage Google+ (`faceshop_social_google`) | NON | Google+ est abandonné. |
| **Paramètres du pied de page** | Afficher le pied de page dans la Boutique Facebook (`faceshop_footer_disp`) | OUI | Afficher le pied de page de votre boutique. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Ma Boutique Facebook ne s'affiche pas ou je vois un message d'erreur.**
R1 :

- **Vérifiez le SSL :** Assurez-vous que votre boutique PrestaShop dispose d'un certificat SSL valide (HTTPS). Facebook exige des connexions sécurisées pour les applications intégrées. Si votre boutique n'est pas en HTTPS, la Boutique Facebook ne se chargera pas.
- **Paramètres de la page Facebook :** Vérifiez à nouveau que vous êtes administrateur de la Page Fan Facebook et que l'onglet "Boutique" est correctement ajouté et configuré sur Facebook lui-même.
- **Configuration du module :** Retournez à la configuration du module dans PrestaShop et assurez-vous que tous les paramètres sont enregistrés correctement.
- **Videz le cache :** Dans PrestaShop, allez dans **Paramètres avancés > Performances** et videz le cache Smarty, le cache du navigateur et tout autre cache.

**Q2 : Les produits ne s'affichent pas correctement ou des images sont manquantes.**
R2 :

- **Paramètres du produit :** Vérifiez que les produits que vous vous attendez à voir sont actifs et visibles dans votre boutique PrestaShop principale.
- **Chemins d'image :** Assurez-vous que les chemins de vos images de produits sont corrects et qu'elles sont accessibles publiquement.
- **Paramètres du module :** Vérifiez les paramètres `faceshop_pdisp_image`, `faceshop_pdisp_name`, `faceshop_pdisp_price` pour vous assurer qu'ils sont activés.
- **Catégorie racine :** Confirmez que vos paramètres `faceshop_cat_root` et `faceshop_homepage_root` pointent correctement vers des catégories qui contiennent des produits.

**Q3 : Le module a un aspect différent sur les appareils mobiles au sein de Facebook.**
R3 :

- **Application Facebook vs. Navigateur :** L'expérience peut varier légèrement entre l'application mobile Facebook et l'accès à Facebook via un navigateur mobile. Le module est conçu pour être réactif, mais l'habillage propre à Facebook peut influencer l'apparence finale.
- **Vérifiez la réactivité :** Testez votre boutique PrestaShop principale sur mobile pour vous assurer qu'elle est entièrement réactive. La Boutique Facebook hérite d'une grande partie de son style de votre boutique principale.
- **CSS personnalisé :** Si vous avez du CSS personnalisé dans votre thème PrestaShop, il pourrait interférer. Consultez un développeur web pour inspecter le CSS dans l'iframe Facebook.

**Q4 : Comment traduire la Boutique Facebook dans d'autres langues ?**
R4 :

- **Traductions PrestaShop :** Le module Boutique Facebook extrait le contenu (noms de produits, descriptions, noms de catégories) directement de votre boutique PrestaShop. Assurez-vous que tout le contenu de vos produits et catégories est traduit dans PrestaShop lui-même.
- **Texte du module :** Pour le texte de l'interface propre au module (par exemple, lien "Nouveaux produits"), allez dans **International > Traductions** dans votre Back Office PrestaShop. Sélectionnez "Traductions des modules installés", choisissez votre thème, votre langue, puis trouvez le module "Boutique Facebook" pour traduire ses chaînes spécifiques.
- **Sélecteur de langue :** Assurez-vous que `faceshop_lang_disp` est activé dans la configuration du module pour permettre aux clients de changer de langue.

**Q5 : Ma Boutique Facebook est lente à charger.**
R5 :

- **Optimisation des images :** Assurez-vous que vos images de produits sont optimisées pour le web (compressées, dimensions appropriées). Les images volumineuses sont une cause fréquente de chargement lent.
- **Performances de l'hébergement :** Vérifiez les performances de votre hébergement web. Un serveur lent affectera à la fois votre boutique principale et votre Boutique Facebook.
- **Nombre de produits :** Si vous affichez un très grand nombre de produits sur la page d'accueil ou les pages de catégories (`faceshop_homepage_itemcount`, `faceshop_cat_itemcount`), envisagez de réduire ces nombres.
- **Mise en cache :** Assurez-vous que les mécanismes de mise en cache de PrestaShop sont correctement configurés (**Paramètres avancés > Performances**).

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module Boutique Facebook (`faceshop`) est conçu comme un module PrestaShop standard, étendant principalement la classe `Module`. Il utilise le système de configuration de PrestaShop (`Configuration::get()`, `Configuration::updateValue()`) pour stocker ses paramètres. La fonctionnalité principale du module consiste à afficher une version simplifiée du front-office de PrestaShop dans une iframe sur une Page Fan Facebook. Il y parvient en ajustant dynamiquement l'affichage en fonction d'un paramètre d'URL spécifique (`?fc=module&module=faceshop&controller=shop`). Le module n'introduit pas de tables de base de données personnalisées ni d'ObjectModels complexes, mais manipule plutôt l'affichage existant du front-office de PrestaShop via des hooks et des surcharges de templates.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient **pas** de contrôleurs front-office ou back-office dédiés dans le répertoire `controllers/`.
Sa fonctionnalité front-office est principalement gérée par le fichier principal `faceshop.php`, qui intercepte les requêtes via un paramètre de contrôleur `shop` personnalisé (par exemple, `index.php?fc=module&module=faceshop&controller=shop`). Cette approche permet au module de rendre une version modifiée du front-office PrestaShop standard dans l'iframe Facebook, plutôt que de créer des structures de page entièrement nouvelles.

### 4.3 Classes et modèles principaux (`classes/`)

Le module n'introduit **pas** de classes ou d'ObjectModels personnalisés dans un répertoire `classes/`. Toute la logique principale est encapsulée dans le fichier principal `faceshop/faceshop.php`.

### 4.4 Actifs JavaScript (`views/js/`)

Le module inclut plusieurs fichiers JavaScript, principalement pour améliorer l'affichage du front-office dans l'iframe Facebook.

- `faceshop/jscolor/jscolor.js`
  - **Portée :** Back-office (probablement utilisé dans le formulaire de configuration du module).
  - **Description :** Une bibliothèque JavaScript pour un sélecteur de couleurs. Elle permet aux administrateurs de sélectionner facilement des couleurs pour les paramètres du module, bien qu'aucun paramètre de couleur explicite n'ait été identifié dans les clés de configuration, c'est un utilitaire courant pour la personnalisation de l'interface utilisateur.
- `faceshop/js/advajax.js`
  - **Portée :** Front-office (dans l'iframe Facebook).
  - **Description :** Probablement un script utilitaire AJAX personnalisé. Il gérerait les requêtes asynchrones pour le chargement des données de produits, la pagination ou d'autres contenus dynamiques dans la Boutique Facebook sans rechargement complet de la page. Cela améliore l'expérience utilisateur en rendant la boutique plus réactive.
- `faceshop/js/jquery.nivo.slider.pack.js`
  - **Portée :** Front-office (dans l'iframe Facebook).
  - **Description :** Une version compressée du plugin jQuery Nivo Slider. Ce script est responsable de la fonctionnalité du slider d'images (`faceshop_slider_disp`) sur la page d'accueil de la Boutique Facebook, gérant les transitions, la navigation et la lecture automatique.
- `faceshop/js/shop2.js`
  - **Portée :** Front-office (dans l'iframe Facebook).
  - **Description :** Il s'agit probablement du fichier JavaScript personnalisé principal pour la logique front-end de la Boutique Facebook. Il contiendrait du code pour :
    - L'initialisation du Nivo Slider.
    - La gestion du chargement de contenu dynamique (par exemple, boutons "Charger plus" pour les produits).
    - L'ajustement de la mise en page ou du comportement spécifiquement pour l'environnement de l'iframe Facebook.
    - Potentiellement la gestion des interactions avec le SDK Facebook (bien que non explicitement mentionné, courant pour les applications Facebook).
    - Toute amélioration d'interface utilisateur personnalisée ou tout écouteur d'événements spécifique à la boutique intégrée.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module inclut plusieurs fichiers CSS pour styliser la Boutique Facebook intégrée, garantissant une apparence cohérente et un fonctionnement correct dans l'iframe.

- `faceshop/css.css`
  - **Portée :** Front-office (dans l'iframe Facebook).
  - **Description :** Une feuille de style générale pour la Boutique Facebook. Elle contient probablement les règles de mise en page de base, la typographie et le style de base pour les éléments courants (boutons, liens, formulaires) afin d'assurer une apparence cohérente.
- `faceshop/css/style.css`
  - **Portée :** Front-office (dans l'iframe Facebook).
  - **Description :** Il pourrait s'agir d'une feuille de style plus spécifique, potentiellement surchargeant ou étendant `css.css`. Elle pourrait contenir des styles pour des fonctionnalités spécifiques du module ou des ajustements de mise en page pour mieux s'adapter à l'environnement Facebook.
- `faceshop/default/default.css`
  - **Portée :** Front-office (dans l'iframe Facebook).
  - **Description :** Cette feuille de style fait probablement partie du plugin Nivo Slider, fournissant un style par défaut pour la navigation, les légendes et l'apparence générale du slider. Les développeurs peuvent surcharger ces styles pour correspondre au thème de la boutique.
- `faceshop/style.css`
  - **Portée :** Front-office (dans l'iframe Facebook).
  - **Description :** Similaire à `faceshop/css/style.css`, il pourrait s'agir d'une autre feuille de style principale ou d'un fichier de secours/hérité. Il définirait la présentation visuelle des éléments de la boutique, garantissant qu'ils sont rendus correctement dans l'iframe Facebook.

### 4.6 Structure des templates Smarty (`views/templates/`)

Le dossier du module indique qu'aucun fichier `.tpl` spécifique n'a été trouvé dans `views/templates/`. Cela suggère que le module fonctionne principalement en :

1. **Interceptant les requêtes standard du front-office de PrestaShop :** Lorsqu'il est accédé via l'URL de la Boutique Facebook, le module modifie probablement les variables Smarty globales ou les chemins de template pour rendre les templates de thème PrestaShop existants.
2. **Utilisant les méthodes `display` dans `faceshop.php` :** Les méthodes `display()` du module peuvent rendre directement du HTML ou inclure des extraits du thème PrestaShop principal, ajoutant ou supprimant dynamiquement des éléments en fonction de sa configuration.
3. **Rendu piloté par JavaScript :** Certains éléments peuvent être injectés ou modifiés dynamiquement par les fichiers JavaScript après le chargement initial de la page.

Si des templates personnalisés étaient présents, ils se trouveraient généralement dans :

- `views/templates/hook/` : Pour le contenu rendu dans des hooks PrestaShop spécifiques.
- `views/templates/admin/` : Pour les formulaires ou affichages back-office personnalisés.
- `views/templates/front/` : Pour les pages front-office autonomes ou le contenu spécifique du module.

L'absence de fichiers `.tpl` explicites implique une manipulation plus directe du processus de rendu existant du front-office de PrestaShop.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** :
  Le module ne crée aucune table de base de données personnalisée. Tous ses paramètres de configuration sont stockés dans la table `ps_configuration` (ou `_configuration` selon le préfixe de table) en utilisant les clés de configuration listées dans la section 4.1.
- **Table des hooks enregistrés** :
  Le module interagit principalement avec l'affichage du front-office de PrestaShop. Bien que le dossier liste "Header, Columns, Product, or Footer" comme hooks front-office, la fonctionnalité principale du module est d'intégrer l'*ensemble* du front-office. Il utilise probablement une combinaison de :

  - **`hookDisplayHeader`** : Pour injecter ses actifs CSS et JavaScript, et potentiellement pour modifier la section `<head>` pour la compatibilité avec l'iframe Facebook.
  - **`hookDisplayFooter`** : Pour injecter des scripts ou du contenu supplémentaires en bas de page.
  - **`actionFrontControllerSetMedia`** : (PrestaShop 1.7+) Pour enregistrer ses fichiers CSS et JS.
  - **Logique interne pour le rendu de la boutique** : Le module a probablement une logique interne qui, lorsqu'il est détecté comme étant chargé dans l'iframe Facebook, modifie la sortie standard du front-office de PrestaShop pour masquer/afficher des éléments en fonction de ses paramètres de configuration (par exemple, `faceshop_header_disp`, `faceshop_footer_disp`). Ceci est souvent réalisé en surchargeant ou en manipulant les variables Smarty et les affectations de templates dans les méthodes `display()` ou `hook` du module.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Avant le contenu principal de la page, dans la section `<head>`. | Injecter les fichiers CSS et JavaScript du module, potentiellement modifier les balises meta pour l'iframe Facebook. |
| `displayFooter` | À la fin du contenu de la page, avant la balise `</body>` fermante. | Injecter des scripts ou des codes de suivi supplémentaires, ou modifier le contenu du pied de page si `faceshop_footer_disp` est activé. |
| `actionFrontControllerSetMedia` (PS 1.7+) | Pendant la phase de définition des médias d'un contrôleur frontal. | Enregistrer les fichiers CSS et JS pour un chargement optimal. |
| (Implicite) Hooks de page produit | Sur les pages de détails de produits. | Modifier l'affichage de la page produit en fonction de `faceshop_pdisp_trim`, `faceshop_pdisp_price`, etc., et injecter des boutons de partage social. |
| (Implicite) Hooks de page de catégorie | Sur les pages de liste de catégories. | Modifier l'affichage de la page de catégorie en fonction de `faceshop_cat_dispnew`, `faceshop_cat_disphot`, etc. |
| (Implicite) Hooks de page d'accueil | Sur la page d'accueil de la boutique. | Rendre le slider, les produits vedettes, les nouveaux produits et les produits en promotion en fonction des paramètres du module. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour votre module Boutique Facebook, veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe est dédiée à assurer le fonctionnement optimal de votre module et à vous aider à maximiser vos ventes en ligne.

- **Historique des commandes et téléchargements MyPresta.eu :** <https://mypresta.eu/my-account/orders/>
- **Contact support MyPresta.eu :** <https://mypresta.eu/contact>
