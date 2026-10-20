---
title: "Supprimer les déclinaisons par attribut - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Supprimer les déclinaisons par attribut' par MyPresta.eu."
sidebar:
  label: "Supprimer les déclinaisons par attribut - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Delete combinations by attribute sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/delete-combinations-by-attribute.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/delete-combinations-by-attribute/)
>
> ---


# Supprimer les déclinaisons par attribut

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune exigence d'hébergement particulière au-delà d'une installation PrestaShop standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal et unique du module « Supprimer les déclinaisons par attribut ». Vous y trouverez tous les outils pour sélectionner et supprimer les déclinaisons.

#### **Section supérieure : Mises à jour et informations du module**

Cette section affiche généralement des informations sur les mises à jour et les versions du module de MyPresta.eu.

- **Ce que fait ce paramètre :** Fournit des informations sur les mises à jour disponibles pour le module, garantissant que vous utilisez la dernière version pour les corrections de bugs et les nouvelles fonctionnalités.
- **Effet de la modification de ce paramètre :** Ce sont des champs d'information et n'ont pas de paramètres directs que vous pouvez modifier. Ils affichent simplement des données.
- **Valeur recommandée :** Maintenez votre module à jour avec la dernière version.
- **Scénario/exemple pour le marchand :** Vous voyez une notification qu'une nouvelle version `1.3.1` est disponible. Vous la téléchargeriez alors depuis MyPresta.eu et mettriez à jour le module.

#### **Options de configuration principales**

1. **Valeur d'attribut**

   - **Ce que fait ce paramètre :** C'est le filtre principal. Il vous permet de sélectionner une valeur d'attribut spécifique (par exemple, « Rouge », « Petit », « Coton ») que vous souhaitez cibler pour la suppression. Le module recherchera toutes les déclinaisons de produits qui incluent cette valeur d'attribut sélectionnée.
   - **Effet de la modification de ce paramètre :**
     - *Lorsqu'une valeur est sélectionnée :* Le module identifiera toutes les déclinaisons de votre boutique qui utilisent cette valeur d'attribut spécifique.
     - *Lorsqu'aucune valeur n'est sélectionnée :* Vous ne pouvez pas procéder au processus de suppression car le module ne sait pas quelles déclinaisons cibler.
   - **Valeur recommandée :** Sélectionnez la valeur d'attribut exacte pour laquelle vous souhaitez supprimer les déclinaisons.
   - **Scénario/exemple pour le marchand :** Vous avez abandonné tous les produits de couleur « Orange ». Vous sélectionneriez « Orange » dans ce menu déroulant pour cibler toutes les déclinaisons avec « Orange » comme l'un de leurs attributs.
2. **Quantité**

   - **Ce que fait ce paramètre :** Cela vous permet de filtrer les déclinaisons en fonction de leur quantité de stock actuelle. Vous pouvez choisir de supprimer les déclinaisons uniquement si leur quantité est inférieure, égale ou supérieure à un nombre spécifié.
   - **Effet de la modification de ce paramètre :**
     - *Lorsque « Que faire » est défini sur « inférieur à » et « Quantité » est 5 :* Seules les déclinaisons avec une quantité de stock de 4 ou moins seront considérées pour la suppression.
     - *Lorsque « Que faire » est défini sur « égal à » et « Quantité » est 0 :* Seules les déclinaisons avec exactement 0 stock seront considérées.
   - **Valeur recommandée :** Souvent utilisé avec « égal à » et « 0 » pour nettoyer les déclinaisons en rupture de stock.
   - **Scénario/exemple pour le marchand :** Vous souhaitez supprimer toutes les déclinaisons de produits « Orange » qui sont actuellement en rupture de stock. Vous sélectionneriez « Orange » dans « Valeur d'attribut », puis définiriez « Que faire » sur « égal à » et « Quantité » sur « 0 ».
3. **Que faire (avec Quantité)**

   - **Ce que fait ce paramètre :** Ce menu déroulant fonctionne conjointement avec le champ « Quantité » pour définir la condition de filtrage des stocks. Les options incluent généralement « inférieur à », « égal à », « supérieur à ».
   - **Effet de la modification de ce paramètre :** Il modifie la logique de comparaison pour le filtre « Quantité ».
   - **Valeur recommandée :** « égal à » est courant pour cibler les articles en rupture de stock.
   - **Scénario/exemple pour le marchand :** Pour supprimer les déclinaisons qui ont un stock très faible, vous pourriez choisir « inférieur à » et définir « Quantité » sur « 3 ».
4. **Liste des codes de référence**

   - **Ce que fait ce paramètre :** Ce champ vous permet de spécifier une liste de codes de référence de produit (SKU) à inclure ou à exclure du processus de suppression. Ceci est utile si vous ne souhaitez affecter qu'un sous-ensemble de produits.
   - **Effet de la modification de ce paramètre :**
     - *Lorsque « Champ de code » est « Référence » et « Que faire » est « inclure » :* Seules les déclinaisons appartenant à des produits avec ces codes de référence spécifiques seront affectées.
     - *Lorsque « Champ de code » est « Référence » et « Que faire » est « exclure » :* Les déclinaisons appartenant à des produits avec ces codes de référence spécifiques seront ignorées.
   - **Valeur recommandée :** Utilisez ceci pour réduire la portée de la suppression à des produits spécifiques. Entrez un code par ligne.
   - **Scénario/exemple pour le marchand :** Vous souhaitez uniquement supprimer les déclinaisons « Orange » des produits avec les codes de référence `PROD-A`, `PROD-B` et `PROD-C`. Vous entreriez ces codes, sélectionneriez « Référence » pour « Champ de code » et « inclure » pour « Que faire ».
5. **Champ de code**

   - **Ce que fait ce paramètre :** Définit à quel champ d'identifiant de produit la « Liste des codes » fait référence. Les options sont généralement « Référence » (SKU) ou « EAN13 » (Code-barres).
   - **Effet de la modification de ce paramètre :** Modifie la façon dont le module interprète les codes saisis dans la « Liste des codes ».
   - **Valeur recommandée :** « Référence » pour les SKU internes, « EAN13 » pour les codes-barres.
   - **Scénario/exemple pour le marchand :** Si votre liste contient des codes-barres EAN13, sélectionnez « EAN13 » ici.
6. **Liste des codes (Que faire)**

   - **Ce que fait ce paramètre :** Détermine si la « Liste des codes de référence » (ou codes EAN) doit être *incluse* dans le processus de suppression (supprimer uniquement de ces produits) ou *exclue* (supprimer de tous les produits SAUF ceux-ci).
   - **Effet de la modification de ce paramètre :** Contrôle la portée des produits affectés par la suppression.
   - **Valeur recommandée :** « inclure » pour les suppressions ciblées, « exclure » pour les suppressions larges avec des exceptions.
   - **Scénario/exemple pour le marchand :** Vous souhaitez supprimer les déclinaisons « Orange » de tous les produits *sauf* votre `BESTSELLER-01` le plus vendu. Vous entreriez `BESTSELLER-01` dans la « Liste des codes » et sélectionneriez « exclure » ici.
7. **Produit**

   - **Ce que fait ce paramètre :** Cela vous permet de sélectionner un produit spécifique par son nom. Si sélectionné, la suppression ne s'appliquera *qu'aux* déclinaisons de ce seul produit, annulant tout autre filtre au niveau du produit.
   - **Effet de la modification de ce paramètre :**
     - *Lorsqu'un produit est sélectionné :* Le module ne traitera que les déclinaisons appartenant à ce produit spécifique.
     - *Lorsqu'il est laissé vide :* Le module appliquera les critères de suppression à tous les produits de votre boutique (sous réserve d'autres filtres comme la « Liste des codes de référence »).
   - **Valeur recommandée :** Utilisez ceci pour des suppressions très ciblées sur un seul produit.
   - **Scénario/exemple pour le marchand :** Vous souhaitez uniquement supprimer les déclinaisons « Orange » de votre produit « Robe d'été ». Vous sélectionneriez « Robe d'été » ici.

#### **Bouton d'action**

- **Bouton « Supprimer les déclinaisons sélectionnées »**
  - **Ce que fait ce bouton :** C'est le bouton d'action qui, lorsqu'il est cliqué, exécute le processus de suppression basé sur tous les critères que vous avez définis ci-dessus.
  - **Effet de cliquer sur ce bouton :** **Cette action est irréversible !** Toutes les déclinaisons de produits correspondant à votre « Valeur d'attribut » sélectionnée, aux filtres de « Quantité » et aux filtres « Produit » ou « Référence/EAN » seront définitivement supprimées de votre base de données. Cela inclut leur stock associé, leurs images et leurs prix spécifiques.
  - **Valeur recommandée :** **TOUJOURS effectuer une sauvegarde complète de la base de données avant de cliquer sur ce bouton.** Vérifiez attentivement tous vos paramètres.
  - **Scénario/exemple pour le marchand :** Après avoir soigneusement sélectionné « Couleur : Orange », défini « Quantité : égal à 0 » et confirmé votre sauvegarde, vous cliquez sur ce bouton pour supprimer toutes les déclinaisons orange en rupture de stock.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | **Valeur d'attribut** | *Sélectionner une valeur spécifique* | Filtre principal : Supprime les déclinaisons contenant cette valeur d'attribut. |
| Configuration du module | **Quantité** | *0 ou nombre désiré* | Filtre les déclinaisons en fonction de leur quantité de stock. |
| Configuration du module | **Que faire (avec Quantité)** | *égal à* | Définit la logique de comparaison pour le filtre « Quantité » (inférieur à, égal à, supérieur à). |
| Configuration du module | **Liste des codes de référence** | *Vide ou codes spécifiques* | Liste des codes de référence produit (SKU) ou EAN à inclure/exclure. Un par ligne. |
| Configuration du module | **Champ de code** | *Référence* | Spécifie si la « Liste des codes » fait référence à « Référence » ou « EAN13 ». |
| Configuration du module | **Liste des codes (Que faire)** | *inclure* | Détermine si les codes listés sont inclus ou exclus de la suppression. |
| Configuration du module | **Produit** | *Vide ou nom de produit spécifique* | Cible la suppression sur un seul produit, annulant les autres filtres de produit. |
| Configuration du module | **Supprimer les déclinaisons sélectionnées** | **Cliquer avec prudence !** | Exécute la suppression irréversible des déclinaisons en fonction de tous les critères. **Sauvegardez d'abord !** |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai cliqué sur « Supprimer » mais rien ne s'est passé, ou toutes les déclinaisons n'ont pas été supprimées.**
R :

- **Vérifiez vos filtres :** Revérifiez tous vos paramètres : « Valeur d'attribut », conditions de « Quantité », « Liste des codes » (inclure/exclure) et sélection de « Produit ». Même une petite incohérence peut empêcher les déclinaisons d'être ciblées.
- **Videz le cache :** Parfois, le cache de PrestaShop peut causer des problèmes d'affichage. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ».
- **Conflits de modules :** Un autre module pourrait interférer. Essayez de désactiver d'autres modules un par un (en particulier ceux liés à la gestion des produits ou des déclinaisons) pour voir si le problème se résout.

**Q : J'ai accidentellement supprimé des déclinaisons que je ne voulais pas. Puis-je les récupérer ?**
R : **Non, pas directement via le module.** C'est pourquoi une sauvegarde est essentielle. Si vous avez une sauvegarde récente de la base de données, vous pouvez restaurer votre boutique à l'état où elle se trouvait avant la suppression. Si vous n'avez pas de sauvegarde, vous devrez recréer manuellement les déclinaisons.

**Q : La valeur d'attribut que je souhaite supprimer n'apparaît pas dans le menu déroulant.**
R :

- **Vérifiez si elle existe :** Assurez-vous que la valeur d'attribut existe réellement dans votre catalogue PrestaShop et qu'elle est attribuée à au moins un produit. Allez dans **Catalogue > Attributs & Caractéristiques** pour vérifier.
- **Langue :** Assurez-vous que vous visualisez le Back Office dans la bonne langue si le nom de la valeur d'attribut dépend de la langue.

**Q : Puis-je supprimer des déclinaisons en fonction des caractéristiques plutôt que des attributs ?**
R : Non, ce module est spécifiquement conçu pour fonctionner avec les **attributs et les valeurs d'attribut**. Les caractéristiques sont un concept différent dans PrestaShop et ne sont pas prises en charge par ce module pour la suppression.

**Q : La suppression des déclinaisons supprimera-t-elle également les images associées ou les prix spécifiques ?**
R : Oui, lorsqu'une déclinaison est supprimée, toutes les données directement liées à cette déclinaison spécifique (comme son image unique, les règles de prix spécifiques pour cette déclinaison et sa quantité de stock) seront également supprimées. L'image principale du produit et les prix spécifiques généraux du produit resteront.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module `delcombs` est un module PrestaShop simple, principalement axé sur les fonctionnalités du Back Office. Il adhère à la structure des modules PrestaShop, utilisant la classe `Module` pour l'installation, la désinstallation et la configuration. Sa logique principale réside dans la méthode `getContent()` du fichier principal du module, où il gère la soumission de formulaire, la validation des données et l'exécution des opérations de base de données pour supprimer les déclinaisons de produits. Il n'introduit pas de contrôleurs front-office personnalisés ni d'ObjectModels complexes, s'appuyant plutôt sur des requêtes de base de données directes et les classes `Product` et `Combination` de PrestaShop pour la manipulation des données.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. Toutes les fonctionnalités sont confinées au Back Office.
- **Contrôleurs Admin Back-Office** : Aucun. La logique de configuration et de traitement du module est gérée dans la méthode `getContent()` de la classe principale du module, qui est rendue dans le cadre de la page de configuration standard du module.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne définit aucune classe personnalisée dans le répertoire `classes/`. Il interagit directement avec les classes `Product` et `Combination` de PrestaShop et effectue des requêtes de base de données directes pour l'efficacité des opérations de suppression en masse.

### 4.4 Actifs JavaScript (`views/js/`)

- `delcombs/views/js/delcombs-admin.js`
  - **Portée :** Back-office (page de configuration du module).
  - **Objectif :** Ce script gère probablement le comportement dynamique sur le formulaire de configuration du module. Cela pourrait inclure :
    - Les appels AJAX pour la recherche de produits ou d'attributs (par exemple, pour le champ de sélection « Produit »).
    - L'affichage conditionnel des champs de formulaire en fonction des sélections de l'utilisateur (par exemple, afficher/masquer les filtres de quantité).
    - La validation des entrées avant la soumission du formulaire.
    - Les boîtes de dialogue de confirmation avant d'exécuter l'action de suppression.
    - Les interactions avec le `searchTool` (probablement un composant de recherche personnalisé pour les produits/attributs).

### 4.5 Feuilles de style CSS (`views/css/`)

- `delcombs/views/css/delcombs-admin.css`
  - **Portée :** Back-office (page de configuration du module).
  - **Objectif :** Fournit le style pour les éléments du formulaire de configuration du module, assurant une interface cohérente et conviviale au sein du Back Office de PrestaShop.
  - **Sélecteurs de classe CSS clés :** Cible probablement des ID ou des classes spécifiques dans la sortie `getContent()` du module, tels que les groupes de formulaires, les champs de saisie et potentiellement le composant `searchTool`. Les développeurs peuvent remplacer ces styles dans leurs thèmes d'administration personnalisés ou en ajoutant du CSS avec une spécificité plus élevée.

### 4.6 Structure des templates Smarty (`views/templates/`)

- `delcombs/lib/searchTool/views/scripts.tpl`
  - **Portée :** Back-office.
  - **Objectif :** Ce template contient probablement du code JavaScript ou des variables Smarty nécessaires à un composant d'outil de recherche générique utilisé dans le module. Il pourrait initialiser des champs de recherche, définir des points de terminaison AJAX pour les requêtes de recherche ou configurer la gestion des données côté client pour les résultats de recherche. Il est probablement inclus par le template de configuration principal.
- `delcombs/views/templates/admin/tabs.tpl`
  - **Portée :** Back-office (page de configuration du module).
  - **Objectif :** C'est le template Smarty principal rendu par la méthode `getContent()` du module `delcombs`. Il structure l'ensemble du formulaire de configuration, y compris :
    - Les différents champs de saisie (menus déroulants pour les attributs, zones de texte pour les codes, saisies de quantité).
    - Le bouton « Supprimer les déclinaisons sélectionnées ».
    - Tous les messages ou avertissements d'information.
    - Il inclut probablement `scripts.tpl` pour la fonctionnalité de recherche.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de la base de données** :

  - Le module ne crée aucune table de base de données personnalisée.
  - Il opère directement sur les tables principales de PrestaShop, principalement :
    - `ps_product_attribute` (table principale des déclinaisons)
    - `ps_product_attribute_combination` (lie les déclinaisons aux valeurs d'attribut)
    - `ps_product_attribute_shop` (données de déclinaison spécifiques à la boutique)
    - `ps_stock_available` (stock pour les déclinaisons)
    - `ps_specific_price` (prix spécifiques pour les déclinaisons)
    - `ps_image` (images liées aux déclinaisons)
    - `ps_product` (pour le filtrage par ID de produit, référence, EAN)
    - `ps_attribute_lang`, `ps_attribute_group_lang` (pour l'affichage des noms d'attributs dans les menus déroulants)
  - Les paramètres de configuration sont stockés dans `ps_configuration` avec des clés comme `delcombs_attribute`, `delcombs_product`, `delcombs_qty_wtd`, `delcombs_qty`, `delcombs_ref_codes`, `delcombs_ref_type`, `delcombs_ean_codes`, `delcombs_ean_type`, `delcombs_ean_field`, `delcombs_product_mode`.
- **Table des hooks enregistrés** :
  Le module n'enregistre aucun hook d'affichage front-office ou back-office. Sa fonctionnalité est entièrement autonome au sein de sa page de configuration.
  Il peut utiliser des hooks d'action en interne (par exemple, `actionProductUpdate` ou `actionAttributeCombinationSave`) pour vider le cache ou réagir aux changements, mais ceux-ci ne sont pas explicitement listés comme des hooks enregistrés pour l'interaction avec des modules externes.
  La logique principale du module est déclenchée par la soumission du formulaire dans sa méthode `getContent()`, et non par un hook PrestaShop standard.

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour télécharger les dernières versions du module « Supprimer les déclinaisons par attribut », veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
