---
title: "Afficher le prix dans différentes devises simultanément - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Afficher le prix dans différentes devises simultanément' par MyPresta.eu."
sidebar:
  label: "Afficher le prix dans différentes devises simultanément - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Show price in different currencies at the same time sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/show-price-in-different-currencies-at-the-same-time.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/show-price-in-different-currencies-at-the-same-time/)
>
> ---


# Afficher le prix dans différentes devises simultanément

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour une installation PrestaShop et sont suffisantes pour ce module.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module « Afficher le prix dans différentes devises simultanément ». Vous pouvez y accéder en naviguant vers **Modules > Gestionnaire de modules** et en cliquant sur « Configurer » à côté du nom du module.

La page de configuration présentera une série d'options pour contrôler comment et où les prix multi-devises sont affichés.

#### Paramètres généraux

- **Activer l'affichage des prix multi-devises :**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité principale du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module commencera à afficher les prix dans plusieurs devises selon vos autres paramètres.
    - *Lorsqu'il est désactivé :* Le module cessera de fonctionner, et seul le prix dans la devise principale sera affiché.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** Si vous configurez le module pour la première fois ou effectuez une maintenance, vous pouvez le désactiver temporairement. Pour un fonctionnement normal, il doit toujours être activé.
- **Sélectionner les devises à afficher :**

  - **Ce que fait ce paramètre :** Cela vous permet de choisir les devises supplémentaires, au-delà de la devise principale, pour lesquelles vous souhaitez afficher les prix. Vous verrez généralement une liste de toutes les devises actives dans votre boutique PrestaShop.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque sélectionné :* Les prix seront affichés dans les devises choisies.
    - *Lorsque non sélectionné :* Les prix ne seront pas affichés dans cette devise spécifique.
  - **Valeur recommandée :** Sélectionnez toutes les devises pertinentes pour vos marchés internationaux cibles.
  - **Scénario / exemple de marchand :** Si vous vendez à des clients de la zone euro, des États-Unis et du Royaume-Uni, vous sélectionneriez EUR, USD et GBP.
- **Afficher sur les pages de liste de produits (Catégories, Résultats de recherche, etc.) :**

  - **Ce que fait ce paramètre :** Contrôle si les prix multi-devises apparaissent sur les pages qui listent plusieurs produits (par exemple, pages de catégories, résultats de recherche, pages de fabricants).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les prix multi-devises seront visibles sous le prix principal sur les fiches produits.
    - *Lorsqu'il est désactivé :* Les prix multi-devises n'apparaîtront que sur la page de détails du produit individuelle.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** L'activation de cette option offre une clarté immédiate des prix lorsque les clients naviguent, les aidant à comparer rapidement les produits dans leur devise préférée.
- **Afficher sur la page de détails du produit :**

  - **Ce que fait ce paramètre :** Contrôle si les prix multi-devises apparaissent sur la page de produit individuelle.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les prix multi-devises seront visibles près du prix principal sur la page du produit.
    - *Lorsqu'il est désactivé :* Les prix multi-devises ne seront pas affichés sur la page du produit.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** Ceci est crucial pour les clients qui prennent une décision finale, en particulier lorsqu'ils considèrent des combinaisons de produits ou des remises sur quantité, car le module garantit que ces prix dynamiques sont également convertis.
- **Format d'affichage des prix :**

  - **Ce que fait ce paramètre :** Définit la manière dont les prix des devises supplémentaires sont formatés (par exemple, avec ou sans symbole monétaire, nombre de décimales). Cela utilise généralement le formatage natif des devises de PrestaShop.
  - **Effet de la modification de ce paramètre :** Modifie la présentation visuelle des prix convertis.
  - **Valeur recommandée :** Utilisez un format clair et cohérent avec les normes internationales pour chaque devise (par exemple, « 100,00 $ USD » ou « 100,00 € »).
  - **Scénario / exemple de marchand :** Vous pourriez choisir d'afficher « USD 100.00 » au lieu de « $100.00 » pour éviter toute confusion avec d'autres devises libellées en dollars.
- **Position des prix supplémentaires :**

  - **Ce que fait ce paramètre :** Détermine où les prix des devises supplémentaires sont placés par rapport au prix principal du produit. Les options peuvent inclure « Sous le prix principal », « À côté du prix principal » ou « Dans un bloc séparé ».
  - **Effet de la modification de ce paramètre :** Modifie la disposition visuelle des prix sur vos pages de produits.
  - **Valeur recommandée :** « Sous le prix principal » est souvent le plus clair et le moins intrusif.
  - **Scénario / exemple de marchand :** Si la mise en page de votre page de produit est très compacte, placer les prix en dessous pourrait être préférable à côté, pour éviter l'encombrement.
- **Mettre à jour les prix avec les combinaisons/remises sur quantité :**

  - **Ce que fait ce paramètre :** Garantit que lorsqu'un client sélectionne une combinaison de produit différente (par exemple, une taille plus grande avec un prix différent) ou modifie la quantité (déclenchant une remise sur quantité), les prix multi-devises affichés sont mis à jour dynamiquement pour refléter le nouveau total.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module utilisera JavaScript pour recalculer et afficher les prix convertis corrects en temps réel.
    - *Lorsqu'il est désactivé :* Les prix supplémentaires pourraient ne pas être mis à jour, ce qui entraînerait des informations incorrectes pour le client.
  - **Valeur recommandée :** OUI (Crucial pour la précision et la confiance du client).
  - **Scénario / exemple de marchand :** Un client sélectionne un t-shirt « Grande taille » (qui coûte plus cher) ou ajoute 10 articles (déclenchant une remise en gros). Ce paramètre garantit qu'il voit le prix converti correct pour le t-shirt grande taille ou le prix en gros réduit dans les devises choisies.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer l'affichage des prix multi-devises | OUI | Active/désactive la fonctionnalité principale du module. |
| Configuration du module | Sélectionner les devises à afficher | Sélectionner les devises pertinentes | Détermine les devises supplémentaires affichées. |
| Configuration du module | Afficher sur les pages de liste de produits | OUI | Affiche les prix multi-devises sur les pages de catégories, de recherche, etc. |
| Configuration du module | Afficher sur la page de détails du produit | OUI | Affiche les prix multi-devises sur les pages de produits individuelles. |
| Configuration du module | Format d'affichage des prix | Varie (utiliser les valeurs par défaut de PrestaShop) | Contrôle le formatage visuel des prix convertis. |
| Configuration du module | Position des prix supplémentaires | Sous le prix principal | Définit la disposition des prix supplémentaires par rapport au prix principal. |
| Configuration du module | Mettre à jour les prix avec les combinaisons/remises sur quantité | OUI | Assure les mises à jour dynamiques des prix pour les combinaisons et les remises. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Les prix multi-devises n'apparaissent pas sur ma boutique.**
**R1 :**

- **Vérifier l'état du module :** Tout d'abord, assurez-vous que l'option « Activer l'affichage des prix multi-devises » est définie sur OUI dans la configuration du module.
- **Devises sélectionnées :** Vérifiez que vous avez sélectionné les devises spécifiques que vous souhaitez afficher dans les paramètres du module.
- **Cache :** Videz le cache de votre PrestaShop (Paramètres avancés > Performances > Vider le cache) et le cache de votre navigateur. Parfois, un ancien contenu mis en cache empêche l'affichage de nouveaux modules.
- **Compatibilité du thème :** Si vous utilisez un thème fortement personnalisé, il peut y avoir un conflit. Contactez le support MyPresta.eu avec les détails de votre thème.

**Q2 : Les prix dans d'autres devises sont incorrects ou ne sont pas mis à jour.**
**R2 :**

- **Taux de change :** Assurez-vous que les taux de change de votre PrestaShop sont à jour. Allez dans **International > Devises** dans votre Back Office et vérifiez les taux de change pour chaque devise. Vous pouvez généralement les mettre à jour automatiquement ou manuellement.
- **Paramètre de mise à jour dynamique :** Assurez-vous que « Mettre à jour les prix avec les combinaisons/remises sur quantité » est activé dans la configuration du module si vous vous attendez à ce que les prix changent avec les options de produit.
- **Cache :** Videz tous les caches (PrestaShop et navigateur) après avoir mis à jour les taux de change.

**Q3 : Les prix multi-devises semblent étranges ou ne sont pas correctement stylisés sur mon thème.**
**R3 :**

- **Configuration du module :** Vérifiez les paramètres « Format d'affichage des prix » et « Position des prix supplémentaires » dans le module.
- **CSS du thème :** Le CSS de votre thème personnalisé peut remplacer le style par défaut du module. Cela nécessite généralement qu'un webmaster ou un développeur inspecte le CSS. Vous pouvez souvent ajouter du CSS personnalisé à votre thème pour ajuster l'apparence.
- **Contacter le support :** Si vous ne parvenez pas à résoudre les problèmes de style, fournissez des captures d'écran et l'URL de votre boutique au support MyPresta.eu pour obtenir de l'aide.

**Q4 : Ce module va-t-il ralentir ma boutique ?**
**R4 :** Le module est conçu pour être léger. Il récupère principalement les taux de change existants et effectue des calculs simples. Les mises à jour dynamiques pour les combinaisons utilisent JavaScript, qui s'exécute côté client. Dans la plupart des cas, tout impact sur les performances devrait être négligeable. Assurez-vous que votre serveur répond aux exigences minimales de PrestaShop pour des performances optimales.

**Q5 : Comment traduire le texte du module (par exemple, « Prix en USD ») ?**
**R5 :** Vous pouvez traduire toutes les chaînes de texte ajoutées par le module via l'interface de traduction de PrestaShop :

- Naviguez vers **International > Traductions**.
- Sélectionnez « Traductions des modules installés ».
- Choisissez votre thème, votre langue, puis sélectionnez le module « Afficher le prix dans différentes devises simultanément ».
- Vous pouvez ensuite modifier les traductions pour toutes les phrases introduites par le module.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de l'architecture technique du module « Afficher le prix dans différentes devises simultanément », destinée aux développeurs, webmasters et agences techniques.

### 4.1 Aperçu de l'architecture

Le module `multiprice` (nom interne `ajax_multiprice`) est un module PrestaShop standard principalement axé sur l'affichage en front-office. Il utilise le système de hooks de PrestaShop pour injecter des informations de prix multi-devises dans les listes de produits et les pages de détails des produits. La logique principale réside dans le fichier principal du module, gérant la configuration et l'enregistrement des hooks. Le JavaScript côté client est utilisé pour les mises à jour dynamiques des prix lorsque les combinaisons ou les quantités de produits changent, garantissant une précision en temps réel sans rechargement complet de la page. Il n'introduit pas de tables de base de données personnalisées ni d'ObjectModels complexes, s'appuyant plutôt sur les mécanismes existants de PrestaShop pour les devises et les prix des produits.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la configuration est gérée via la méthode `getContent()` dans le fichier principal du module, et les interactions en front-office sont gérées via des hooks et du JavaScript côté client.

### 4.3 Classes et modèles de base (`classes/`)

Le module ne définit aucune classe ou `ObjectModel` personnalisé dans le répertoire `classes/`. Sa logique est encapsulée dans le fichier principal du module `ajax_multiprice.php`.

### 4.4 Actifs JavaScript (`views/js/`)

- **`multiprice/lib/searchTool/views/js/autocomplete.js`**

  - **Portée :** Potentiellement Front-office (s'il est utilisé pour une fonction de recherche au sein du module, bien que non directement lié à l'affichage principal des prix multiples).
  - **Responsabilité :** Ce fichier semble faire partie d'une bibliothèque générique d'outils de recherche d'autocomplétion fournie avec le module. Il gérerait généralement les requêtes AJAX pour les suggestions de recherche, se lierait aux champs de saisie et afficherait les résultats. Sa pertinence directe pour l'affichage des prix multi-devises est probablement minime, à moins que le module n'intègre une fonction de recherche qui affiche également les prix.
  - **Détails :** Se lie aux champs de saisie, écoute les événements `keyup`, effectue des appels AJAX à un point de terminaison backend (non défini dans les contrôleurs de ce module, probablement un contrôleur de recherche générique de PrestaShop ou un contrôleur d'outil de recherche fourni) et manipule le DOM pour afficher une liste déroulante de suggestions.
- **`multiprice/views/js/multiprice.js`**

  - **Portée :** Front-office.
  - **Responsabilité :** Il s'agit du fichier JavaScript principal pour l'affichage des prix multi-devises. Il est responsable de la mise à jour dynamique des prix affichés lorsque les attributs du produit (combinaisons) ou les quantités changent sur la page du produit.
  - **Détails :**
    - Écoute les événements `change` sur les sélecteurs de combinaisons de produits (par exemple, les éléments `select` pour les attributs, les boutons radio).
    - Écoute les événements `change` ou `blur` sur le champ de saisie de la quantité.
    - S'accroche à l'événement natif de PrestaShop `prestashop.on('updatedProduct', ...)` (pour PS 1.7+), qui est déclenché lorsque les données du produit (y compris le prix) sont mises à jour après la sélection d'une combinaison.
    - Récupère le nouveau prix de base à partir des données du produit mises à jour.
    - Effectue des calculs côté client pour convertir le nouveau prix de base dans les devises supplémentaires configurées, en utilisant des taux de change potentiellement transmis depuis le backend ou stockés dans une variable JS globale.
    - Met à jour les éléments du DOM (`<span>`, `<div>`) où les prix des devises supplémentaires sont affichés.
    - Assure un formatage correct des prix convertis (symbole monétaire, décimales).

### 4.5 Feuilles de style CSS (`views/css/`)

- **`multiprice/lib/searchTool/views/css/autocomplete.css`**

  - **Portée :** Front-office.
  - **Responsabilité :** Style la liste déroulante des résultats de recherche d'autocomplétion, y compris les suggestions, la mise en surbrillance et la mise en page générale.
  - **Sélecteurs de classes CSS clés :** Cible probablement des classes comme `.autocomplete-results`, `.autocomplete-item`, `.highlighted`. Les développeurs peuvent les remplacer dans le `custom.css` ou `theme.css` de leur thème.
- **`multiprice/views/css/multiprice.css`**

  - **Portée :** Style client Front-office.
  - **Responsabilité :** Fournit le style par défaut pour les blocs d'affichage des prix multi-devises. Cela inclut les tailles de police, les couleurs, les marges et potentiellement la mise en page (par exemple, l'empilement vertical des prix).
  - **Sélecteurs de classes CSS clés :** Ciblera des classes spécifiques ajoutées par les modèles du module (par exemple, `.multiprice-container`, `.multiprice-currency-item`, `.multiprice-price`). Les développeurs peuvent remplacer ces sélecteurs dans le CSS de leur thème pour correspondre au design de leur boutique.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **`multiprice/lib/searchTool/views/scripts.tpl`**

  - **Portée :** Front-office.
  - **Objectif :** Ce modèle inclut probablement le JavaScript et le CSS pour la fonctionnalité `autocomplete.js`. Il serait accroché à `displayHeader` ou `displayFooter` pour s'assurer que les actifs nécessaires sont chargés.
- **`multiprice/views/templates/multiprice-custom.tpl`**

  - **Portée :** Front-office (modèle de hook).
  - **Objectif :** Ce modèle est probablement un modèle de secours ou un modèle alternatif pour afficher les prix multi-devises, éventuellement pour des hooks spécifiques ou des placements personnalisés. Il contiendrait la structure HTML pour rendre le prix principal, puis itérerait sur les devises supplémentaires pour afficher leurs prix convertis.
- **`multiprice/views/templates/multiprice.tpl`**

  - **Portée :** Front-office (modèle de hook).
  - **Objectif :** Il s'agit du modèle principal responsable du rendu du bloc de prix multi-devises. Il est injecté dans les éléments de la liste de produits et la page de détails du produit via les hooks PrestaShop. Il reçoit un tableau de devises et leurs prix convertis et les formate selon la configuration du module.
  - **Variables :** Attend des variables comme `$product_price`, `$additional_currencies` (un tableau d'objets de devises avec des prix convertis), `$currency_format`, etc.
- **`multiprice/views/templates/selectedProducts.tpl`**

  - **Portée :** Front-office.
  - **Objectif :** Le nom de ce modèle suggère qu'il pourrait être utilisé dans un contexte où une liste de produits sélectionnés est affichée, potentiellement dans un résumé de panier, une page de comparaison ou un widget de sélection de produits personnalisé. Il itérerait sur une collection de produits et afficherait leurs prix, potentiellement avec la fonction multi-devises.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne crée aucune table SQL personnalisée.
  - Il stocke ses paramètres de configuration (par exemple, état activé, devises sélectionnées, options d'affichage) dans la table `ps_configuration`, en utilisant des clés préfixées par `MULTIPRICE_` ou similaire.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Pour inclure `multiprice.js` et `multiprice.css` (et potentiellement les actifs `autocomplete`) sur les pages du front-office. |
| `displayProductPriceBlock` (type `after_price`) | Après le bloc de prix principal sur les pages de produits. | Pour injecter le contenu de `multiprice.tpl` ou `multiprice-custom.tpl` affichant les prix des devises supplémentaires sur la page de détails du produit. |
| `displayProductListReviews` (ou similaire pour la liste de produits) | Dans les éléments de la liste de produits (par exemple, pages de catégories). | Pour injecter le contenu de `multiprice.tpl` ou `multiprice-custom.tpl` affichant les prix des devises supplémentaires sous le prix principal sur les pages de liste de produits. Le hook exact peut varier en fonction de la version de PrestaShop et de la structure du thème (par exemple, `displayProductPriceBlock` peut également être utilisé ici, ou un hook personnalisé fourni par le thème). |
| `actionProductUpdate` (ou similaire) | Après la mise à jour d'un produit dans le back office. | (Moins probable pour ce module) Pourrait être utilisé pour vider le cache lié aux prix des produits, bien que ce ne soit pas strictement nécessaire pour sa fonction principale. |
| `actionFrontControllerSetMedia` | Avant qu'un contrôleur frontal ne rende son contenu. | Pour enregistrer les fichiers JavaScript et CSS pour le front office, en s'assurant qu'ils sont chargés correctement. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et toute question concernant le module « Afficher le prix dans différentes devises simultanément », veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec l'installation, la configuration et tout problème que vous pourriez rencontrer.
