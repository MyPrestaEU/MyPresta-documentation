---
title: "Remplacer ajouter au panier par un lien vers une page - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Remplacer ajouter au panier par un lien vers une page' par MyPresta.eu."
sidebar:
  label: "Remplacer ajouter au panier par un lien vers une page - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Replace add to cart with link to page sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/replace-add-to-cart-with-link-to-page.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/replace-add-to-cart-with-link-to-page/)
>
> ---


# Remplacer ajouter au panier par un lien vers une page

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran principal où vous contrôlez le comportement global du module.

- **Activé**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité du module dans toute votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module commencera à remplacer les boutons « Ajouter au panier » par des liens personnalisés basés sur vos paramètres spécifiques au produit et d'autres configurations globales.
    - *Lorsqu'il est désactivé :* Le module sera inactif, et tous les boutons « Ajouter au panier » retrouveront leur comportement PrestaShop par défaut.
  - **Valeur recommandée :** OUI (pour activer le module).
  - **Scénario / exemple de marchand :** Si vous testez le module ou souhaitez temporairement désactiver sa fonctionnalité sans le désinstaller, vous pouvez le régler sur NON. Pour une utilisation active, il doit être sur OUI.
- **Texte du bouton**

  - **Ce que fait ce paramètre :** Définit le texte qui apparaîtra sur le bouton personnalisé, remplaçant « Ajouter au panier ». Ce texte peut être traduit dans différentes langues.
  - **Effet de la modification de ce paramètre :** Le texte sur le bouton changera pour la valeur spécifiée.
  - **Valeur recommandée :** Quelque chose de descriptif comme « En savoir plus », « Demander un devis », « Voir les détails » ou « Visiter le site partenaire ».
  - **Scénario / exemple de marchand :** Si vous liez à un site externe pour plus d'informations, vous pouvez le régler sur « En savoir plus ». Si vous dirigez les clients vers un formulaire de devis, « Demander un devis » serait approprié.
- **Masquer le champ quantité**

  - **Ce que fait ce paramètre :** Contrôle si le champ de saisie de quantité (où les clients sélectionnent le nombre d'articles à ajouter) est visible sur les pages produit lorsque le module est actif.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le sélecteur de quantité sera masqué, car il n'est pas pertinent lorsque le bouton redirige au lieu d'ajouter au panier.
    - *Lorsqu'il est désactivé :* Le sélecteur de quantité restera visible, ce qui pourrait être déroutant si le bouton n'ajoute pas au panier.
  - **Valeur recommandée :** OUI.
  - **Scénario / exemple de marchand :** Puisque le bouton n'ajoute plus au panier, il n'y a généralement pas besoin d'un champ de quantité. Le masquer simplifie l'interface et évite la confusion.
- **Classe CSS du bouton ajouter au panier sur la page produit**

  - **Ce que fait ce paramètre :** Vous permet de spécifier une classe CSS personnalisée pour le bouton de remplacement sur la page produit. Ceci est utile pour styliser le bouton afin qu'il corresponde à votre thème ou pour le faire ressortir.
  - **Effet de la modification de ce paramètre :** Le bouton héritera des styles définis par cette classe CSS dans la feuille de style de votre thème.
  - **Valeur recommandée :** Laissez vide si le style de bouton par défaut de votre thème est acceptable, ou utilisez une classe comme `btn btn-primary` ou `my-custom-button` si vous avez des styles spécifiques.
  - **Scénario / exemple de marchand :** Si votre thème utilise `btn-success` pour les boutons d'action principaux, vous pouvez entrer `btn-success` ici pour rendre votre bouton personnalisé vert et proéminent.
- **Classe CSS de la quantité**

  - **Ce que fait ce paramètre :** Vous permet de spécifier une classe CSS pour le champ de saisie de quantité sur la page produit. Ceci est principalement destiné au stylisme avancé ou si vous devez cibler le champ de quantité avec du CSS personnalisé.
  - **Effet de la modification de ce paramètre :** Le champ de saisie de quantité recevra cette classe CSS.
  - **Valeur recommandée :** Laissez vide sauf si vous avez un besoin de stylisme spécifique.
  - **Scénario / exemple de marchand :** Un développeur pourrait l'utiliser pour appliquer une largeur ou un rembourrage spécifique au champ de quantité s'il n'est pas masqué.
- **Appliquer le module à la liste des produits**

  - **Ce que fait ce paramètre :** Détermine si la fonctionnalité du module (remplacer « Ajouter au panier » par un lien personnalisé) s'applique également aux boutons de produit affichés dans les listes (par exemple, pages de catégorie, résultats de recherche, produits phares sur la page d'accueil).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les boutons « Ajouter au panier » dans les listes de produits seront également remplacés par le lien personnalisé.
    - *Lorsqu'il est désactivé :* Seul le bouton « Ajouter au panier » de la page produit sera affecté ; les boutons de liste de produits conserveront leur comportement par défaut.
  - **Valeur recommandée :** OUI, pour une cohérence dans toute votre boutique, surtout si le lien personnalisé est une partie essentielle de votre entonnoir de vente.
  - **Scénario / exemple de marchand :** Si tous les produits nécessitant ce lien personnalisé sont des services qui nécessitent un devis, vous voudriez que cela soit activé afin que les clients n'essaient pas d'« ajouter au panier » depuis une page de catégorie.
- **Classe CSS de l'élément avec le produit**

  - **Ce que fait ce paramètre :** Il s'agit d'un paramètre technique pour aider le module à identifier le conteneur principal d'un produit dans une vue de liste. Il est crucial pour que le module trouve et modifie correctement le bouton « Ajouter au panier » dans chaque article de produit.
  - **Effet de la modification de ce paramètre :** S'il est incorrect, le module pourrait ne pas appliquer ses modifications aux articles de la liste de produits.
  - **Valeur recommandée :** Cela dépend fortement du thème. Les valeurs courantes incluent `product-miniature`, `product-container`, `product-item`. Vous devrez peut-être inspecter le code HTML de votre thème pour trouver la classe correcte.
  - **Scénario / exemple de marchand :** Si votre thème utilise `<div class="product-card">` pour chaque produit dans une liste, vous entreriez `product-card` ici.
- **Classe CSS de** (Ceci fait probablement référence au bouton « Ajouter au panier » lui-même dans un article de liste de produits)

  - **Ce que fait ce paramètre :** Spécifie la classe CSS du bouton « Ajouter au panier » dans les articles de la liste de produits. Cela aide le module à cibler le bon bouton pour le remplacement.
  - **Effet de la modification de ce paramètre :** S'il est incorrect, le module pourrait ne pas remplacer le bouton « Ajouter au panier » dans les listes de produits.
  - **Valeur recommandée :** Cela dépend fortement du thème. Les valeurs courantes incluent `add-to-cart`, `product-add-to-cart`, `btn-primary`. Inspectez le code HTML de votre thème.
  - **Scénario / exemple de marchand :** Si le bouton « Ajouter au panier » de votre thème dans les listes a la classe `btn-add-to-cart`, vous l'entreriez ici.
- **Classe CSS du champ de quantité sur la liste des produits**

  - **Ce que fait ce paramètre :** Similaire au paramètre de la page produit, cela vous permet de spécifier la classe CSS pour le champ de saisie de quantité lorsque les produits sont affichés dans une liste. Il est utilisé pour le masquer si « Masquer le champ quantité » est activé.
  - **Effet de la modification de ce paramètre :** S'il est incorrect, le champ de quantité pourrait rester visible dans les listes de produits même si vous avez choisi de le masquer.
  - **Valeur recommandée :** Laissez vide sauf si vous avez un besoin de stylisme spécifique ou si le champ de quantité n'est pas masqué correctement. Inspectez le code HTML de votre thème.
  - **Scénario / exemple de marchand :** Si votre thème utilise `product-quantity-input` pour le champ de quantité dans les listes, vous l'entreriez ici.
- **Masquer l'info-bulle sur le bouton**

  - **Ce que fait ce paramètre :** Contrôle si l'info-bulle PrestaShop par défaut (affichant souvent « Ajouter au panier » ou similaire) apparaît au survol du bouton personnalisé.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* L'info-bulle sera masquée, évitant les messages potentiellement déroutants.
    - *Lorsqu'il est désactivé :* L'info-bulle par défaut pourrait toujours apparaître, ce qui pourrait entrer en conflit avec le but du bouton personnalisé.
  - **Valeur recommandée :** OUI.
  - **Scénario / exemple de marchand :** Si votre bouton personnalisé indique « Demander un devis », vous ne voulez pas qu'une info-bulle apparaisse disant « Ajouter au panier ». Le masquer garantit un message clair.
- **Ajouter rel=“nofollow”**

  - **Ce que fait ce paramètre :** Ajoute l'attribut `rel="nofollow"` au lien personnalisé. Cela indique aux moteurs de recherche de ne pas suivre le lien et de ne pas transmettre de « jus de lien » à la destination.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le lien aura `rel="nofollow"`, ce qui est utile pour les liens externes que vous ne voulez pas approuver ou pour les liens internes qui ne sont pas critiques pour le référencement (par exemple, les pages de connexion).
    - *Lorsqu'il est désactivé :* Le lien sera un lien standard suivi.
  - **Valeur recommandée :** OUI pour les liens externes, en particulier les liens d'affiliation ou les liens vers des sites que vous ne contrôlez pas entièrement. NON pour les liens internes de votre propre site que vous souhaitez que les moteurs de recherche explorent.
  - **Scénario / exemple de marchand :** Si vous liez au site web d'un partenaire affilié, l'activation de `nofollow` est une bonne pratique pour éviter les pénalités SEO potentielles et pour indiquer clairement qu'il s'agit d'un lien sponsorisé ou externe.
- **Ouvrir les liens dans une nouvelle fenêtre (onglet)**

  - **Ce que fait ce paramètre :** Détermine si le lien personnalisé s'ouvre dans le même onglet du navigateur ou dans un nouvel onglet.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le lien s'ouvrira dans un nouvel onglet du navigateur, gardant la page de votre boutique ouverte dans l'onglet d'origine.
    - *Lorsqu'il est désactivé :* Le lien s'ouvrira dans le même onglet, éloignant le client de votre boutique.
  - **Valeur recommandée :** OUI pour les liens externes, pour garder les clients sur votre site. NON pour les liens internes où vous voulez que le client navigue dans votre boutique.
  - **Scénario / exemple de marchand :** Si vous dirigez les clients vers un site partenaire externe, l'ouverture dans un nouvel onglet est généralement préférable afin qu'ils puissent facilement revenir à votre page produit.
- **Visibilité du module pour les produits sélectionnés**

  - **Ce que fait ce paramètre :** C'est un paramètre crucial qui définit *quels* produits verront leur bouton « Ajouter au panier » remplacé. Il fonctionne en conjonction avec les paramètres spécifiques au produit que vous trouverez sur la page d'édition de chaque produit.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le module ne s'appliquera qu'aux produits pour lesquels vous avez explicitement défini une URL personnalisée dans leurs paramètres de produit.
    - *Désactivé :* Le module ne s'appliquera à aucun produit, quels que soient leurs paramètres individuels.
  - **Valeur recommandée :** Activé. Cela vous permet d'appliquer sélectivement la fonctionnalité de lien personnalisé à des produits spécifiques.
  - **Scénario / exemple de marchand :** Vous ne voulez remplacer le bouton « Ajouter au panier » que pour vos meubles sur mesure, pas pour les accessoires standard. Vous activeriez ce paramètre, puis iriez à chaque produit de meuble et définiriez son URL personnalisée.

#### Paramètres spécifiques au produit (Back Office > Catalogue > Produits > Modifier le produit > Onglet Modules)

Une fois le module installé et activé, vous trouverez de nouveaux paramètres lors de l'édition de produits individuels.

- **Champ URL du produit**
  - **Ce que fait ce paramètre :** C'est ici que vous entrez l'URL spécifique vers laquelle le bouton « Ajouter au panier » de *ce produit particulier* redirigera.
  - **Effet de la modification de ce paramètre :** Lorsqu'un client clique sur le bouton personnalisé sur la page de ce produit (ou dans une liste, si activé), il sera dirigé vers cette URL.
  - **Valeur recommandée :** Une URL complète et valide (par exemple, `https://example.com/demander-un-devis` ou `/contactez-nous`).
  - **Scénario / exemple de marchand :** Pour un produit « Service de conception personnalisée », vous pouvez entrer `https://votreboutique.com/contactez-nous?sujet=Demande%20de%20conception%20personnalisée` ici.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### AdminAtcurlSearchController (Back Office > Modules > Remplacer ajouter au panier par un lien vers une page > Configurer > Onglet « Produits sélectionnés »)

Cet écran offre un moyen centralisé de gérer et de visualiser les produits pour lesquels des URL personnalisées ont été configurées.

- **Nom de l'écran et emplacement du menu :** Vous accédez à cet écran en naviguant vers **Modules > Gestionnaire de modules**, en trouvant « Remplacer ajouter au panier par un lien vers une page », en cliquant sur « Configurer », puis en sélectionnant l'onglet « Produits sélectionnés » (ou similaire, selon la version du module).
- **Actions et paramètres disponibles :** Cet écran affiche généralement une grille ou une liste de produits qui ont actuellement une URL personnalisée définie.
  - **Colonnes :** Vous verrez généralement des colonnes comme ID du produit, Nom du produit et l'URL personnalisée.
  - **Recherche/Filtre :** Il peut y avoir des options de recherche ou de filtre pour trouver rapidement des produits spécifiques.
  - **Modifier/Supprimer :** Vous pourriez avoir des liens directs pour modifier le produit (ce qui vous amène à la page d'édition de produit standard) ou supprimer l'URL personnalisée pour un produit directement depuis cette liste.
- **Effet des modifications :**
  - La modification d'une URL ici (si l'édition directe est disponible) ou via la page d'édition du produit changera immédiatement la destination de la redirection du bouton pour ce produit.
  - La suppression d'un produit de cette liste (ou la suppression de son URL personnalisée sur la page d'édition du produit) rétablira le comportement par défaut du bouton « Ajouter au panier » de PrestaShop.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Utilisez cet écran pour vérifier rapidement quels produits utilisent la fonctionnalité de lien personnalisé. Si vous devez mettre à jour de nombreux liens de produits, cette vue vous aide à garder une trace. Pour ajouter de nouveaux liens, il est généralement plus efficace d'aller directement à la page d'édition du produit.

#### index.php (atcurl/controllers/admin/index.php)

Ce fichier est un espace réservé et ne représente généralement pas un écran d'administration visible par l'utilisateur. Dans PrestaShop, les fichiers `index.php` dans les répertoires de contrôleur sont souvent utilisés pour empêcher la liste directe des répertoires ou pour inclure d'autres fichiers. Ce n'est pas un écran de configuration pour les marchands.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Activé | OUI | Interrupteur principal pour activer/désactiver la fonctionnalité du module. |
|  | Texte du bouton | « En savoir plus » (exemple) | Texte affiché sur le bouton personnalisé. |
|  | Masquer le champ quantité | OUI | Masque le sélecteur de quantité sur les pages produit. |
|  | Classe CSS du bouton ajouter au panier sur la page produit | (Vide / Dépend du thème) | Classe CSS personnalisée pour le bouton sur les pages produit. |
|  | Classe CSS de la quantité | (Vide) | Classe CSS personnalisée pour le champ de quantité sur les pages produit. |
|  | Appliquer le module à la liste des produits | OUI | Étend la fonctionnalité du module aux pages de liste de produits. |
|  | Classe CSS de l'élément avec le produit | `product-miniature` (exemple) | Aide le module à identifier les conteneurs de produits dans les listes. |
|  | Classe CSS de (bouton Ajouter au panier dans la liste) | `add-to-cart` (exemple) | Aide le module à identifier les boutons « Ajouter au panier » dans les listes. |
|  | Classe CSS du champ de quantité sur la liste des produits | (Vide) | Classe CSS personnalisée pour le champ de quantité dans les listes de produits. |
|  | Masquer l'info-bulle sur le bouton | OUI | Empêche l'info-bulle « Ajouter au panier » par défaut sur le bouton personnalisé. |
|  | Ajouter rel=“nofollow” | OUI (pour externe) / NON (pour interne) | Ajoute l'attribut `nofollow` au lien personnalisé. |
|  | Ouvrir les liens dans une nouvelle fenêtre (onglet) | OUI (pour externe) / NON (pour interne) | Ouvre le lien personnalisé dans un nouvel onglet du navigateur. |
|  | Visibilité du module pour les produits sélectionnés | Activé | Active la configuration d'URL spécifique au produit. |
| **Page d'édition du produit (Onglet Modules)** | Champ URL du produit | (URL personnalisée) | Définit l'URL de redirection spécifique pour *ce* produit. |
| **AdminAtcurlSearchController** | Grille de produits avec URL personnalisées | N/A | Vue centralisée pour gérer les produits avec des liens personnalisés. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mon bouton « Ajouter au panier » ne change pas, même après avoir configuré une URL.**
R1 :

- **Vérifier l'état du module :** Tout d'abord, assurez-vous que l'interrupteur « Activé » sur la page de configuration principale du module est réglé sur OUI.
- **Vérifier la visibilité du produit :** Assurez-vous que « Visibilité du module pour les produits sélectionnés » est réglé sur « Activé » sur la page de configuration du module.
- **Vérifier l'URL du produit :** Vérifiez que vous avez entré une URL valide dans le « Champ URL du produit » pour le produit spécifique que vous testez (sur la page d'édition du produit sous l'onglet « Modules »).
- **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). Parfois, PrestaShop met en cache d'anciens contenus.
- **Compatibilité du thème :** Votre thème peut utiliser des classes CSS non standard pour son bouton « Ajouter au panier » ou ses conteneurs de produits. Vérifiez les paramètres « Classe CSS de l'élément avec le produit » et « Classe CSS de » sur la page de configuration du module. Vous devrez peut-être utiliser les outils de développement de votre navigateur (F12) pour inspecter le code HTML et trouver les classes correctes.

**Q2 : Le champ de quantité est toujours visible, même si j'ai choisi de le masquer.**
R2 :

- **Vérifier « Masquer le champ quantité » :** Assurez-vous que ce paramètre est activé sur la page de configuration du module.
- **Vérifier « Classe CSS du champ de quantité » :** Si votre thème utilise une classe non standard pour le champ de quantité, le module pourrait ne pas être en mesure de le trouver et de le masquer. Utilisez les outils de développement de votre navigateur pour inspecter le champ de saisie de quantité et entrez sa classe CSS dans le paramètre « Classe CSS de la quantité » (pour la page produit) et « Classe CSS du champ de quantité sur la liste des produits » (pour les listes de produits).
- **Vider le cache :** Videz toujours le cache de votre PrestaShop après avoir effectué des modifications de configuration.

**Q3 : Le module fonctionne sur les pages produit mais pas sur les pages de catégorie/liste.**
R3 :

- **Vérifier « Appliquer le module à la liste des produits » :** Assurez-vous que ce paramètre est activé sur la page de configuration du module.
- **Vérifier les classes CSS pour les listes :** Le module doit savoir comment votre thème structure les listes de produits. Vérifiez que les paramètres « Classe CSS de l'élément avec le produit » et « Classe CSS de » (pour le bouton) sont corrects pour votre thème. Ceux-ci sont souvent différents des classes de la page produit. Utilisez les outils de développement du navigateur pour inspecter les éléments sur une page de catégorie.
- **Vider le cache :** Videz le cache de votre PrestaShop.

**Q4 : Mon bouton personnalisé n'a pas l'air correct (mauvaise couleur, taille, etc.).**
R4 :

- **Classe CSS pour le style :** Utilisez le paramètre « Classe CSS du bouton ajouter au panier sur la page produit ». Entrez une classe CSS qui existe déjà dans votre thème et fournit le style souhaité (par exemple, `btn btn-primary`, `btn-success`).
- **CSS personnalisé :** Si vous avez besoin d'un style unique, vous devrez ajouter du CSS personnalisé à votre thème. Vous pouvez cibler le bouton en utilisant la classe que vous avez définie dans la configuration du module, ou en inspectant son code HTML. Par exemple :

  ```
  .my-custom-button-class { background-color: #ff6600; color: white; border-radius: 5px; padding: 10px 20px;}
  ```

  Ajoutez ce CSS au fichier CSS personnalisé de votre thème ou via un module CSS personnalisé.
- **Vider le cache :** Videz le cache de votre PrestaShop.

**Q5 : Comment traduire le texte du bouton dans d'autres langues ?**
R5 :

- Allez dans **International > Traductions** dans votre Back Office PrestaShop.
- Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez la langue que vous souhaitez traduire.
- Trouvez le module « Remplacer ajouter au panier par un lien vers une page ». Vous y verrez le champ « Texte du bouton », vous permettant d'entrer des traductions pour chaque langue.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Remplacer ajouter au panier par un lien vers une page » (`atcurl`) est un module PrestaShop standard suivant un modèle de type MVC. Il étend principalement les fonctionnalités existantes de PrestaShop via des hooks pour modifier l'affichage front-office des pages produit et des listes de produits. La configuration est gérée via la méthode `getContent()` du module principal et stockée dans `ps_configuration`. Les URL spécifiques aux produits sont stockées en tant que `Product::specific_fields` ou potentiellement dans une table personnalisée, avec un contrôleur d'administration (`AdminAtcurlSearchController`) fournissant une interface de gestion. JavaScript est fortement utilisé pour remplacer dynamiquement les boutons et masquer les éléments sur le front-office.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Ce module ne contient aucun contrôleur front-office dédié. Toutes les modifications front-office sont gérées via des hooks et JavaScript.
- **Contrôleurs d'administration Back-Office** :

  - `atcurl/controllers/admin/AdminAtcurlSearchController.php`
    - **Nom de la classe et classe parente :** `AdminAtcurlSearchController` étend `ModuleAdminController`.
    - **Nom de l'onglet et entité gérée :** Ce contrôleur est probablement responsable de l'affichage d'une grille ou d'une liste de produits pour lesquels une URL personnalisée a été configurée par le module. Il fournit une vue centralisée pour gérer ces associations de produits, permettant potentiellement des modifications ou des suppressions rapides de l'URL personnalisée. Il ne gère pas un `ObjectModel` dédié mais interagit avec les données du produit et la configuration du module.
  - `atcurl/controllers/admin/index.php`
    - Il s'agit d'un fichier de remplacement PrestaShop standard, contenant généralement `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../../../"); exit;` pour empêcher la liste directe des répertoires et rediriger vers le panneau d'administration principal. Il ne fournit aucune logique de contrôleur fonctionnelle.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne semble pas définir de classes personnalisées ou d'`ObjectModel` dans le répertoire `classes/`. Les URL spécifiques aux produits sont probablement stockées en tant que `Product::specific_fields` ou directement dans la table `ps_configuration`, indexées par ID de produit, ou potentiellement un champ personnalisé ajouté à l'entité produit.

### 4.4 Actifs JavaScript (`views/js/`)

- `atcurl/lib/js/admin/atcurl177.js`
  - **Portée :** Back-office (Admin).
  - **Responsabilité :** Gère probablement la logique spécifique à la page de configuration du module ou à l'`AdminAtcurlSearchController` pour les versions PrestaShop 1.7.7+. Cela pourrait inclure des appels AJAX pour la sauvegarde des paramètres, des mises à jour dynamiques de l'interface utilisateur ou des interactions avec l'outil de recherche/sélection de produits.
- `atcurl/lib/js/front/atcurl-list-177.js`
  - **Portée :** Front-office.
  - **Responsabilité :** Cible spécifiquement les pages de liste de produits (catégorie, recherche, blocs de page d'accueil). Il écoute les changements du DOM (par exemple, lorsque les produits sont chargés via AJAX) et remplace dynamiquement les boutons « Ajouter au panier » par le lien personnalisé, masque les champs de quantité et applique les classes CSS personnalisées telles que configurées. Il est adapté aux thèmes PrestaShop 1.7.7+.
- `atcurl/lib/js/front/atcurl177.js`
  - **Portée :** Front-office.
  - **Responsabilité :** Cible principalement la page produit unique. Il identifie le bouton « Ajouter au panier », le remplace par le lien personnalisé, masque le champ de quantité et applique les attributs `nofollow` ou `target="_blank"` en fonction des paramètres du module. Il gère également le masquage des info-bulles. Adapté aux thèmes PrestaShop 1.7.7+.
- `atcurl/lib/searchTool/views/js/autocomplete.js`
  - **Portée :** Back-office (Admin).
  - **Responsabilité :** Fournit une fonctionnalité d'autocomplétion, probablement pour la sélection de produits dans la configuration du module ou dans la grille `AdminAtcurlSearchController`. Cela aide les administrateurs à trouver et à associer rapidement des produits à des URL personnalisées.

### 4.5 Feuilles de style CSS (`views/css/`)

- `atcurl/lib/searchTool/views/css/autocomplete.css`
  - **Portée :** Back-office (Admin).
  - **Responsabilité :** Style la liste déroulante d'autocomplétion et les éléments d'interface utilisateur associés utilisés dans l'outil de recherche d'administration, garantissant son intégration visuelle avec le thème du Back Office de PrestaShop.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :

  - `atcurl/views/hook/displayProductAdditionalInfo.tpl`
    - **Hook :** `displayProductAdditionalInfo`
    - **Objectif :** Ce template est probablement rendu sur la page produit, fournissant le conteneur ou le code HTML du bouton personnalisé qui remplace le bouton standard « Ajouter au panier ». Il contiendrait la logique pour afficher le texte et le lien du bouton personnalisé.
  - `atcurl/views/hook/displayProductListReviews.tpl`
    - **Hook :** `displayProductListReviews` (Ce nom de hook est inhabituel pour le remplacement de bouton et pourrait être une faute de frappe ou une manière indirecte d'injecter du JS/CSS pour les listes de produits. Il est plus courant d'utiliser `displayProductListFunctionalButtons` ou `displayProductActions` pour les modifications de bouton dans les listes).
    - **Objectif :** S'il est utilisé, ce template injecterait du JavaScript ou un élément caché dans les articles de la liste de produits, que le script `atcurl-list-177.js` utiliserait ensuite pour effectuer le remplacement du bouton. Il est moins probable qu'il contienne directement le code HTML du bouton.
- **Templates d'administration (`views/templates/admin/`)** :

  - `atcurl/lib/searchTool/views/scripts.tpl`
    - **Objectif :** Ce template est probablement inclus dans le Back Office pour charger le JavaScript nécessaire (`autocomplete.js`) et potentiellement le CSS (`autocomplete.css`) pour l'outil de recherche/sélection de produits utilisé dans la configuration du module ou l'`AdminAtcurlSearchController`.
  - `atcurl/views/tpl/selectedProducts.tpl`
    - **Objectif :** Ce template est utilisé par l'`AdminAtcurlSearchController` pour rendre la grille ou la liste des produits pour lesquels des URL personnalisées ont été configurées. Il définit la structure du tableau et la manière dont les informations de chaque produit (ID, nom, URL) sont affichées.
- **Templates Front-office (`views/templates/front/`)** : Aucun explicitement listé, car les modifications Front-office sont principalement gérées par JS et les templates de hook.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne semble pas créer de tables SQL personnalisées.
  - **`ps_configuration`** : Stocke les paramètres globaux du module (par exemple, `ATC_URL_BUTTON_FRONT`, `ATC_URL_BUTTON_TEXT`, `ATC_URL_BLANK`, `ATC_URL_NOFOLLOW`, `ATC_HIDE_TOOLTIP`, `ATC_URL_PL`, `ATC_URL_visibility_rule`, `ATC_URL_BUTTON_QTY_HIDE`, `ATC_URL_visibility_products`, `ATC_URL_visibility_cat`).
  - **`ps_product_shop` / `ps_product_lang`** : Les URL spécifiques aux produits sont probablement stockées comme un champ supplémentaire associé au produit, potentiellement en utilisant le mécanisme `specific_fields` de PrestaShop ou en mettant à jour directement les propriétés du produit. La méthode `install()` du module ajouterait ce champ.
- **Table des hooks enregistrés** :

| Nom du hook | Portée | Moment d'exécution | Objectif technique |
| --- | --- | --- | --- |
| `displayProductAdditionalInfo` | Front-Office | Sur la page produit, généralement sous la description du produit ou le bloc de prix. | Injecte le code HTML du bouton personnalisé ou un espace réservé pour que JS le cible. |
| `ActionAdminControllerSetMedia` | Back-Office | Lorsqu'un contrôleur d'administration charge ses médias (JS/CSS). | Charge le JavaScript (`atcurl177.js`, `autocomplete.js`) et le CSS (`autocomplete.css`) spécifiques à l'administration pour la configuration du module et la gestion des produits. |
| `actionProductUpdate` | Back-Office | Après la mise à jour/sauvegarde d'un produit dans le Back Office. | Permet au module de sauvegarder l'URL personnalisée associée au produit. |
| `displayHeader` | Front-Office | Dans la section `<head>` de chaque page front-office. | Injecte le JavaScript front-office (`atcurl177.js`, `atcurl-list-177.js`) et potentiellement du CSS en ligne ou des variables de configuration pour les scripts JS. |
| `displayProductListReviews` | Front-Office | Dans les articles de la liste de produits, souvent près du nom du produit ou de l'évaluation. | (Comme indiqué ci-dessus, ce hook est inhabituel pour le remplacement de bouton. Il est probablement utilisé pour injecter du JS pour le traitement des articles de liste, ou il pourrait s'agir d'un hook hérité. Les développeurs devraient vérifier son utilisation réelle dans le code du module.) |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Remplacer ajouter au panier par un lien vers une page », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe s'engage à garantir le fonctionnement optimal du module avec votre boutique PrestaShop.
