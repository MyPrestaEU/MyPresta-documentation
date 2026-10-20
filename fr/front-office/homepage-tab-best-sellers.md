---
title: "Onglet Meilleures ventes de la page d'accueil - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Onglet Meilleures ventes de la page d'accueil' par MyPresta.eu."
sidebar:
  label: "Onglet Meilleures ventes de la page d'accueil - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Homepage tab best sellers sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tab-best-sellers.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/homepage-tab-best-sellers/)
>
> ---


# Onglet Meilleures ventes de la page d'accueil

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont habituellement disponibles sur tout environnement d'hébergement moderne.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Onglet Meilleures ventes de la page d'accueil » dans le Gestionnaire de modules. Vous serez redirigé vers sa page de configuration.

#### Nombre de produits à afficher

-   **Ce que fait ce paramètre :** Ce paramètre contrôle le nombre de produits les plus vendus qui seront affichés dans l'onglet « Meilleures ventes » sur votre page d'accueil.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'il est défini sur un nombre plus élevé (par exemple, 12) :* Plus de produits seront affichés dans l'onglet, offrant aux clients un plus grand choix de vos meilleures ventes à parcourir. Cela peut être bon pour les boutiques avec de nombreux articles populaires.
    *   *Lorsqu'il est défini sur un nombre inférieur (par exemple, 4) :* Moins de produits seront affichés, créant une présentation plus concise et ciblée. Cela peut être bénéfique pour les boutiques avec moins de meilleures ventes ou lorsque vous souhaitez mettre l'accent sur quelques-uns.
-   **Valeur recommandée :** Un bon point de départ est généralement entre **8 et 12** produits. Cela offre suffisamment de variété sans submerger le client ni rendre la page trop longue.
-   **Scénario / exemple de marchand :** Si vous avez un grand catalogue et de nombreux produits qui se vendent constamment bien, vous pourriez le définir à 10 ou 12 pour présenter plus de vos articles populaires. Si vous préférez une page d'accueil plus propre et plus minimaliste, vous pourriez le définir à 6.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact ## 5. Cas d'utilisation pratiques et meilleures pratiques (Conseils de pro)

1.  **Exploitez la preuve sociale pour les nouveaux visiteurs :**
    *   **Scénario :** Un nouveau client arrive sur votre page d'accueil. Il ne connaît ni votre marque ni vos produits.
    *   **Conseil de pro :** L'onglet « Meilleures ventes » fournit immédiatement une preuve sociale, leur montrant ce que d'autres clients achètent et apprécient. Assurez-vous que vos meilleures ventes ont de bonnes images de produits et des descriptions claires. Envisagez de lancer une promotion temporaire (par exemple, « Nos 5 meilleures ventes - 10 % de réduction cette semaine ! ») pour attirer encore plus l'attention sur cette section.
2.  **Optimisez pour les produits saisonniers et tendance :**
    *   **Scénario :** Votre boutique connaît des pics de ventes saisonniers (par exemple, cadeaux de fin d'année, vêtements d'été) ou propose des produits qui deviennent soudainement tendance.
    *   **Conseil de pro :** Bien que le module identifie automatiquement les meilleures ventes, vous pouvez indirectement influencer cela en promouvant stratégiquement certains produits. Par exemple, pendant l'été, si vous voulez que vos maillots de bain apparaissent dans les « Meilleures ventes », assurez-vous qu'ils sont bien stockés, à des prix compétitifs et peut-être présentés dans d'autres efforts marketing. Au fur et à mesure qu'ils se vendent davantage, ils monteront naturellement dans le classement des meilleures ventes et apparaîtront dans l'onglet.
3.  **Faites de la promotion croisée avec d'autres sections de la page d'accueil :**
    *   **Scénario :** Vous avez d'autres sections de produits sur votre page d'accueil (par exemple, « Nouveaux produits », « Produits en vedette »).
    *   **Conseil de pro :** Utilisez l'onglet « Meilleures ventes » comme section complémentaire. Si un produit est nouveau et se vend exceptionnellement bien, il pourrait apparaître à la fois dans « Nouveaux produits » et « Meilleures ventes », renforçant sa popularité. Évitez d'avoir trop de produits qui se chevauchent si possible, pour offrir plus de variété aux clients, mais ne cachez pas un nouveau produit véritablement best-seller juste pour le plaisir de la variété. La nature automatique du module gérera cela naturellement.

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mon onglet « Meilleures ventes » n'apparaît pas sur la page d'accueil.**

-   **R :** Tout d'abord, assurez-vous que le module est installé et activé dans **Modules > Gestionnaire de modules**. Ensuite, vérifiez sa configuration. Si l'onglet n'apparaît toujours pas, il pourrait s'agir d'un problème de cache. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les anciennes versions). Si votre thème est fortement personnalisé, il pourrait ne pas s'accrocher correctement à `displayHomeTab` et `displayHomeTabContent`. Dans ce cas, vous devrez peut-être consulter le développeur de votre thème ou un expert PrestaShop.

**Q2 : Les produits dans l'onglet « Meilleures ventes » ne semblent pas être mes véritables meilleures ventes.**

-   **R :** Le module s'appuie sur les données de ventes internes de PrestaShop pour déterminer les meilleures ventes.
    *   Assurez-vous d'avoir des données de ventes réelles pour les produits. Les nouvelles boutiques ou les boutiques avec très peu de ventes pourraient ne pas avoir suffisamment de données pour une liste de « meilleures ventes » significative.
    *   Le calcul des « meilleures ventes » est généralement basé sur le nombre d'unités vendues sur une période. Il peut falloir un certain temps pour que les ventes récentes se reflètent dans la liste.
    *   Videz votre cache PrestaShop (**Paramètres avancés > Performances > Vider le cache**) pour vous assurer que les dernières données sont extraites.

**Q3 : À quelle fréquence la liste des « Meilleures ventes » est-elle mise à jour ?**

-   **R :** La liste des meilleures ventes est générée dynamiquement par PrestaShop en fonction des données de ventes. Elle se met à jour automatiquement au fur et à mesure que les commandes sont passées et traitées. Cependant, pour que les changements soient visibles sur le front office, vous devrez peut-être vider votre cache PrestaShop, surtout si vous avez un cache agressif activé.

**Q4 : Puis-je changer le titre de l'onglet (par exemple, de « Meilleures ventes » à « Nos coups de cœur ») ?**

-   **R :** Oui, vous le pouvez. Le titre de l'onglet est généralement une chaîne de caractères traduisible au sein du module.
    1.  Allez dans **International > Traductions**.
    2.  Sélectionnez « Traductions des modules installés ».
    3.  Choisissez votre thème.
    4.  Sélectionnez votre langue.
    5.  Trouvez le module « Onglet Meilleures ventes de la page d'accueil » dans la liste.
    6.  Localisez la chaîne de texte pour le titre de l'onglet (par exemple, « Meilleures ventes ») et modifiez-la avec le texte souhaité. N'oubliez pas d'enregistrer vos modifications.

**Q5 : Les produits ont l'air étranges ou mal alignés dans l'onglet.**

-   **R :** Il s'agit généralement d'un conflit de style CSS avec votre thème PrestaShop. Le module fournit les données du produit, mais votre thème est responsable de la façon dont ces données sont affichées (mise en page, polices, couleurs, tailles d'image).
    *   Assurez-vous que votre thème est à jour.
    *   Essayez de vider votre cache PrestaShop (**Paramètres avancés > Performances**).
    *   Si le problème persiste, vous devrez peut-être ajouter du CSS personnalisé à votre thème pour remplacer le style par défaut du module ou du thème. Cela nécessite généralement un développeur web.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé du module « Onglet Meilleures ventes de la page d'accueil » pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module `Onglet Meilleures ventes de la page d'accueil` est un module PrestaShop simple conçu pour s'intégrer de manière transparente au système d'onglets de la page d'accueil. Il suit une structure de module PrestaShop classique, utilisant principalement la classe `Module` et les hooks du front-office. Il n'introduit pas de contrôleurs, de modèles ou de JavaScript/CSS complexes personnalisés, s'appuyant plutôt sur les fonctionnalités de base de PrestaShop pour la récupération des données de produits et sur le style de thème existant pour la présentation. Sa logique principale réside dans le fichier `homebestsellerstab.php`, gérant la configuration et l'enregistrement des hooks.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Aucun. Le contenu du front-office du module est rendu directement via des templates Smarty accrochés à `displayHomeTab` et `displayHomeTabContent`.
-   **Contrôleurs d'administration Back-Office** : Aucun. La configuration du module est gérée par la méthode `getContent()` au sein de la classe principale du module.

### 4.3 Classes et modèles de base (`classes/`)

-   Aucun. Le module ne définit aucune classe personnalisée ni n'étend `ObjectModel`. Il utilise les classes `Product` et `ProductSale` de base de PrestaShop (ou des mécanismes internes similaires) pour récupérer les données des produits les plus vendus.

### 4.4 Actifs JavaScript (`views/js/`)

-   Aucun. Le module n'inclut aucun fichier JavaScript personnalisé. Tout comportement interactif (comme le changement d'onglet) est censé être géré par le JavaScript existant du thème PrestaShop.

### 4.5 Feuilles de style CSS (`views/css/`)

-   Aucun. Le module n'inclut aucun fichier CSS personnalisé. Le style de l'onglet et des listes de produits qu'il contient dépend entièrement du thème PrestaShop actif. Les développeurs doivent inspecter le HTML généré et cibler les classes/ID pertinents dans le CSS de leur thème pour personnaliser l'apparence.

### 4.6 Structure des templates Smarty (`views/templates/`)

Le module utilise deux fichiers de template Smarty, tous deux situés dans le répertoire `views/templates/hook/`, pour rendre son contenu dans le front office.

-   **`views/templates/hook/tab.tpl`**

    -   **Hook** : `displayHomeTab`
    -   **Objectif** : Ce template est responsable du rendu de l'élément d'onglet cliquable sur la page d'accueil. Il contient généralement la balise `<li>` ou `<a>` qui représente l'onglet « Meilleures ventes », y compris son titre traduisible.
    -   **Sortie** : Un élément d'onglet qui, lorsqu'il est cliqué, révèle le contenu rendu par `homebestsellerstab.tpl`.
-   **`views/templates/hook/homebestsellerstab.tpl`**

    -   **Hook** : `displayHomeTabContent`
    -   **Objectif** : Ce template rend la liste ou la grille réelle des produits les plus vendus lorsque l'onglet « Meilleures ventes » est actif. Il reçoit un tableau de données de produits de la logique PHP du module.
    -   **Sortie** : Balisage HTML pour l'affichage des produits (par exemple, conteneurs `div`, images de produits, noms, prix, boutons d'ajout au panier). Il itère généralement sur la variable `$products` qui lui est transmise.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** : Le module ne crée aucune table de base de données personnalisée. Il stocke sa configuration (par exemple, `HOME_BEST_NBR`) dans la table `ps_configuration` de PrestaShop.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique La clé de configuration `HOME_BEST_NBR` est utilisée pour stocker le nombre de produits à afficher.
Les clés `PS_LANG_DEFAULT` et `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` sont des clés de configuration de base de PrestaShop utilisées pour gérer les paramètres de langue par défaut et de langue du formulaire employé. Celles-ci ne sont pas directement configurées par le module mais sont accessibles pour le contexte.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Onglet Meilleures ventes de la page d'accueil », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Vous pouvez télécharger la version la plus récente du module depuis l'historique de vos commandes. Pour une assistance technique ou des questions, veuillez utiliser les canaux de support fournis sur le site web de MyPresta.eu.
