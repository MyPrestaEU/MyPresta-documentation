---
title: "Mise à jour de quantité en masse pro - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop « Mise à jour de quantité en masse pro » par MyPresta.eu."
sidebar:
  label: "Mise à jour de quantité en masse pro - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Mass quantity update pro sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-quantity-update-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/mass-quantity-update-pro/)
>
> ---


# Mise à jour de quantité en masse pro

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

Le module « Mise à jour de quantité en masse pro » fournit un écran de configuration unique et intuitif dans le back office de votre PrestaShop où vous définissez les produits à mettre à jour et les changements de quantité à appliquer.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Pour accéder à la configuration du module, naviguez vers **Modules > Gestionnaire de modules**, recherchez « Mise à jour de quantité en masse pro », et cliquez sur le bouton « Configurer ».

La page de configuration est divisée en deux sections principales : **Produits cibles** et **Que faire ?**.

#### 2.1.1 Produits cibles

Cette section vous permet de définir *quels* produits ou combinaisons de produits seront affectés par la mise à jour de quantité. Vous pouvez sélectionner des produits en fonction de divers critères.

- **Ce que fait ce paramètre :** Cette section définit la portée de votre mise à jour de quantité. Vous choisissez le groupe spécifique de produits dont les quantités seront modifiées.
- **Effet de la modification de ce paramètre :** Seuls les produits correspondant aux critères sélectionnés seront pris en compte pour la mise à jour de quantité. Si aucun critère n'est sélectionné, aucun produit ne sera ciblé.
- **Valeur recommandée :** Sélectionnez un ou plusieurs critères qui définissent précisément les produits que vous avez l'intention de modifier.

**Critères disponibles :**

1. **Produits par catégories :**

   - **Ce que fait ce paramètre :** Vous permet de sélectionner une ou plusieurs catégories de produits spécifiques. Tous les produits (et leurs combinaisons) appartenant à ces catégories seront ciblés.
   - **Effet de la modification de ce paramètre :**
     - *Lorsque sélectionné :* Les produits des catégories choisies seront inclus.
     - *Lorsque non sélectionné :* Les produits ne sont pas filtrés par catégorie.
   - **Valeur recommandée :** Sélectionnez ceci si vous devez mettre à jour le stock pour une ligne de produits ou un département entier.
   - **Scénario / exemple de marchand :** Vous avez reçu une nouvelle expédition pour tous les produits de votre catégorie « Collection d'été ». Vous pouvez sélectionner cette catégorie pour mettre à jour leur stock.
2. **Produits par marque :**

   - **Ce que fait ce paramètre :** Vous permet de sélectionner une ou plusieurs marques de produits spécifiques (fabricants). Tous les produits (et leurs combinaisons) associés à ces marques seront ciblés.
   - **Effet de la modification de ce paramètre :**
     - *Lorsque sélectionné :* Les produits des marques choisies seront inclus.
     - *Lorsque non sélectionné :* Les produits ne sont pas filtrés par marque.
   - **Valeur recommandée :** Sélectionnez ceci si vous devez mettre à jour le stock pour les produits d'un fournisseur ou d'une marque particulière.
   - **Scénario / exemple de marchand :** Votre fournisseur « Fashionista Inc. » a livré un nouveau stock. Vous sélectionnez « Fashionista Inc. » pour mettre à jour tous leurs produits.
3. **Produits par caractéristiques :**

   - **Ce que fait ce paramètre :** Vous permet de sélectionner des produits en fonction de leurs caractéristiques attribuées (par exemple, « Couleur : Rouge », « Matière : Coton »). Vous pouvez choisir une caractéristique puis des valeurs spécifiques pour cette caractéristique.
   - **Effet de la modification de ce paramètre :**
     - *Lorsque sélectionné :* Seuls les produits possédant la caractéristique et la valeur spécifiées seront inclus.
     - *Lorsque non sélectionné :* Les produits ne sont pas filtrés par caractéristiques.
   - **Valeur recommandée :** Utile pour des mises à jour très spécifiques basées sur les caractéristiques du produit.
   - **Scénario / exemple de marchand :** Vous souhaitez mettre à jour le stock de tous les t-shirts en « Coton biologique ». Vous sélectionnez « Matière » comme caractéristique et « Coton biologique » comme valeur.
4. **Produits par attributs :**

   - **Ce que fait ce paramètre :** Vous permet de sélectionner des produits en fonction de leurs attributs (par exemple, « Taille : M », « Couleur : Bleu »). Ceci est particulièrement utile pour les combinaisons de produits.
   - **Effet de la modification de ce paramètre :**
     - *Lorsque sélectionné :* Seules les combinaisons de produits avec l'attribut et la valeur spécifiés seront incluses.
     - *Lorsque non sélectionné :* Les produits ne sont pas filtrés par attributs.
   - **Valeur recommandée :** Essentiel pour gérer le stock de variations de produits spécifiques.
   - **Scénario / exemple de marchand :** Vous avez reçu une nouvelle livraison de t-shirts de « Taille L ». Vous sélectionnez « Taille » comme attribut et « L » comme valeur pour ne mettre à jour que ces combinaisons.
5. **Produits par associations de règles de taxe :**

   - **Ce que fait ce paramètre :** Vous permet de sélectionner des produits en fonction du groupe de règles de taxe qui leur est appliqué.
   - **Effet de la modification de ce paramètre :**
     - *Lorsque sélectionné :* Seuls les produits associés au groupe de règles de taxe choisi seront inclus.
     - *Lorsque non sélectionné :* Les produits ne sont pas filtrés par règle de taxe.
   - **Valeur recommandée :** Utile pour les boutiques avec des structures fiscales complexes ou lorsque les mises à jour de stock sont liées à l'inventaire lié aux taxes.
   - **Scénario / exemple de marchand :** Vous devez ajuster le stock de tous les produits soumis à une règle de taxe spécifique « Droits d'importation ».
6. **Produits spécifiques :**

   - **Ce que fait ce paramètre :** Fournit une boîte de recherche à saisie semi-automatique pour sélectionner manuellement des produits individuels par nom.
   - **Effet de la modification de ce paramètre :**
     - *Lorsque des produits sont ajoutés :* Seuls les produits explicitement sélectionnés (et leurs combinaisons) seront ciblés.
     - *Lorsque vide :* Aucun produit spécifique n'est ciblé de cette manière.
   - **Valeur recommandée :** Utilisez ceci pour des mises à jour très précises sur un petit ensemble de produits sélectionnés manuellement.
   - **Scénario / exemple de marchand :** Vous devez mettre à jour le stock pour « Produit A », « Produit B » et « Produit C » qui ne sont pas liés par catégorie ou marque.

#### 2.1.2 Que faire ?

Cette section définit *comment* les quantités des produits ciblés seront modifiées.

- **Ce que fait ce paramètre :** Cette section spécifie le type de modification de quantité (augmentation, diminution ou définition d'une valeur fixe) et le montant du changement.
- **Effet de la modification de ce paramètre :** L'opération sélectionnée sera appliquée aux quantités de tous les produits définis dans la section « Produits cibles ».
- **Valeur recommandée :** Choisissez l'opération qui reflète précisément votre ajustement d'inventaire.

**Opérations disponibles :**

1. **Augmenter la quantité de :**

   - **Ce que fait ce paramètre :** Ajoute un nombre spécifié à la quantité actuelle de chaque produit/combinaison ciblé.
   - **Effet de la modification de ce paramètre :** Le niveau de stock de chaque article ciblé augmentera du montant saisi.
   - **Valeur recommandée :** Utilisez lorsque de nouveaux stocks arrivent. Saisissez un entier positif (par exemple, `10`).
   - **Scénario / exemple de marchand :** Vous avez reçu 50 unités d'un produit. Vous sélectionnez « Augmenter la quantité de » et saisissez `50`.
2. **Diminuer la quantité de :**

   - **Ce que fait ce paramètre :** Soustrait un nombre spécifié de la quantité actuelle de chaque produit/combinaison ciblé.
   - **Effet de la modification de ce paramètre :** Le niveau de stock de chaque article ciblé diminuera du montant saisi.
   - **Valeur recommandée :** Utilisez lorsque le stock doit être réduit en raison de dommages, de retours ou d'utilisation interne. Saisissez un entier positif (par exemple, `5`).
   - **Scénario / exemple de marchand :** 5 articles ont été endommagés dans l'entrepôt. Vous sélectionnez « Diminuer la quantité de » et saisissez `5`.
3. **Définir la quantité à :**

   - **Ce que fait ce paramètre :** Modifie la quantité actuelle de chaque produit/combinaison ciblé à un nombre fixe spécifique.
   - **Effet de la modification de ce paramètre :** Le niveau de stock de chaque article ciblé deviendra exactement le montant saisi, quelle que soit sa quantité précédente.
   - **Valeur recommandée :** Utilisez lorsque vous devez synchroniser le stock avec un système externe ou corriger un décompte de stock absolu. Saisissez un entier non négatif (par exemple, `100`).
   - **Scénario / exemple de marchand :** Après un inventaire complet, vous savez que vous avez exactement 100 unités d'un produit. Vous sélectionnez « Définir la quantité à » et saisissez `100`.

**Remarque importante :** Après avoir défini à la fois les « Produits cibles » et « Que faire ? », vous devez cliquer sur le bouton **« Mettre à jour les quantités »** pour appliquer les modifications. Il n'y a pas de bouton « annuler », alors vérifiez toujours vos sélections avant de confirmer.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | **Produits cibles** | | Définit quels produits/combinaisons seront affectés. |
| | Produits par catégories | Sélectionner selon les besoins | Cible tous les produits des catégories choisies. |
| | Produits par marque | Sélectionner selon les besoins | Cible tous les produits des marques choisies. |
| | Produits par caractéristiques | Sélectionner selon les besoins | Cible les produits avec des caractéristiques/valeurs spécifiques. |
| | Produits par attributs | Sélectionner selon les besoins | Cible les combinaisons de produits avec des attributs/valeurs spécifiques. |
| | Produits par associations de règles de taxe | Sélectionner selon les besoins | Cible les produits associés aux règles de taxe choisies. |
| | Produits spécifiques | Sélectionner selon les besoins | Cible les produits sélectionnés individuellement. |
| | **Que faire ?** | | Définit comment les quantités seront modifiées. |
| | Augmenter la quantité de | Saisir un entier positif | Ajoute le montant spécifié au stock actuel. |
| | Diminuer la quantité de | Saisir un entier positif | Soustrait le montant spécifié du stock actuel. |
| | Définir la quantité à | Saisir un entier non négatif | Définit le stock à un montant exact et spécifié. |
| | **Bouton Mettre à jour les quantités** | Cliquer pour appliquer | Exécute les changements de quantité définis. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q1 : J'ai mis à jour les quantités, mais ma boutique affiche toujours les anciens chiffres. Qu'est-ce qui ne va pas ?**
**R1 :** Il s'agit généralement d'un problème de cache. PrestaShop utilise le cache pour accélérer votre boutique.

- **Solution :** Allez dans **Paramètres avancés > Performances** dans votre back office PrestaShop. Cliquez sur « Vider le cache » (ou « Vider le cache Smarty » / « Vider le cache » selon votre version de PrestaShop). Cela devrait forcer votre boutique à afficher les quantités mises à jour.

**Q2 : J'ai fait une erreur et mis à jour les mauvais produits/quantités. Puis-je annuler ?**
**R2 :** Le module n'a pas de bouton « annuler ». C'est pourquoi il est crucial de vérifier vos sélections avant de cliquer sur « Mettre à jour les quantités ».

- **Solution :** Si vous avez une sauvegarde récente de votre base de données, vous pouvez la restaurer (bien que cela puisse annuler d'autres modifications récentes). Sinon, vous devrez corriger manuellement les quantités des produits affectés, ou utiliser à nouveau le module avec les bons paramètres pour les réajuster. Par exemple, si vous avez accidentellement augmenté de 10, vous pouvez diminuer de 10.

**Q3 : Le module ne trouve pas de produits lorsque je tape dans la boîte de recherche « Produits spécifiques ».**
**R3 :** Assurez-vous de taper le nom complet ou partiel d'un produit existant dans votre boutique. La fonction de saisie semi-automatique repose sur JavaScript.

- **Solution :**
  1. Vérifiez la console de votre navigateur pour toute erreur JavaScript (touche F12, puis onglet « Console »).
  2. Essayez de vider le cache de votre navigateur.
  3. Assurez-vous que votre boutique PrestaShop fonctionne sur une version PHP compatible (voir section 3).
  4. Si le problème persiste, contactez le support MyPresta.eu.

**Q4 : Puis-je mettre à jour les quantités pour les produits qui ont des combinaisons (attributs) ?**
**R4 :** Oui, absolument ! Le module est conçu pour gérer les combinaisons de produits. Lorsque vous sélectionnez des produits par catégorie, marque, caractéristique ou produit spécifique, il appliquera le changement de quantité à toutes les combinaisons associées de ces produits. Si vous utilisez « Produits par attributs », vous pouvez même cibler directement des combinaisons spécifiques.

**Q5 : Le module semble lent lors de la mise à jour d'un très grand nombre de produits.**
**R5 :** La mise à jour de milliers de produits peut être gourmande en ressources.

- **Solution :**
  1. Assurez-vous que votre serveur répond aux spécifications recommandées par PrestaShop.
  2. Augmentez les limites de temps d'exécution PHP (`max_execution_time`) et les limites de mémoire (`memory_limit`) dans votre fichier `php.ini` (consultez votre hébergeur ou webmaster).
  3. Si possible, divisez les très grandes mises à jour en lots plus petits (par exemple, mettez à jour une catégorie à la fois au lieu de toutes les catégories).

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module « Mise à jour de quantité en masse pro ».

### 4.1 Aperçu de l'architecture

Le module `MassQtyPro` suit une architecture de module PrestaShop standard, exploitant principalement la classe `Module` pour sa fonctionnalité principale et la méthode `getContent()` pour son interface de configuration unique en back-office. Il intègre un outil de recherche personnalisé pour la sélection de produits, utilisant AJAX pour la fonctionnalité de saisie semi-automatique. Le module interagit directement avec les classes `Product` et `StockAvailable` de PrestaShop pour effectuer les mises à jour de quantité.

### 4.2 Contrôleurs (`controllers/`)

Le module n'utilise pas de contrôleurs front-office ou back-office personnalisés. Toute la logique de configuration et de traitement pour le back-office est gérée dans la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne définit aucune classe `ObjectModel` personnalisée ni de classes dédiées dans un répertoire `classes/`. Toute la logique principale réside dans le fichier `massqtypro.php`.

### 4.4 Actifs JavaScript (`views/js/`)

- **`massqtypro/lib/searchTool/views/js/autocomplete.js`**
  - **Portée :** Back-office (utilisé sur la page de configuration du module).
  - **Description :** Ce script implémente ou intègre probablement une fonctionnalité de saisie semi-automatique générique. Il écoute la saisie de l'utilisateur dans les champs de texte (spécifiquement pour la recherche de produits) et envoie des requêtes AJAX pour récupérer les noms de produits correspondants. Il affiche ensuite ces suggestions dans une liste déroulante, permettant à l'utilisateur de sélectionner des produits. Il gère l'affichage et la sélection des résultats de saisie semi-automatique.
- **`massqtypro/views/js/jquery.autocomplete.js`**
  - **Portée :** Back-office (utilisé sur la page de configuration du module).
  - **Description :** Il s'agit apparemment d'un plugin jQuery pour la fonctionnalité de saisie semi-automatique. Il fournit le cadre principal pour la boîte de recherche de produits sur la page de configuration du module. Il gère les appels AJAX au serveur (probablement à la méthode `getContent()` ou à un hook spécifique qui fournit des données de produit), traite la réponse JSON et rend les suggestions. Il gère également la sélection d'un élément de la liste et le remplissage du champ de saisie ou d'un champ masqué avec l'ID du produit sélectionné.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`massqtypro/lib/searchTool/views/css/autocomplete.css`**
  - **Portée :** Back-office (style pour la page de configuration du module).
  - **Description :** Cette feuille de style fournit la présentation visuelle de la boîte de recherche à saisie semi-automatique et de sa liste de suggestions. Elle définit les styles pour le champ de saisie, le conteneur déroulant, les éléments de suggestion individuels et potentiellement les états de survol/actif pour une meilleure interaction utilisateur. Les développeurs peuvent remplacer ces styles dans leur thème d'administration personnalisé ou en ajoutant des règles CSS spécifiques pour cibler les éléments du module.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module utilise des modèles Smarty pour le rendu de son formulaire de configuration en back-office.

- **`massqtypro/lib/searchTool/views/scripts.tpl`**
  - **Portée :** Back-office (inclus dans la page de configuration du module).
  - **Description :** Ce modèle inclut probablement les fichiers JavaScript et CSS nécessaires pour l'outil de recherche à saisie semi-automatique. Il peut également contenir du JavaScript en ligne pour initialiser le plugin de saisie semi-automatique sur des champs de saisie spécifiques, transmettre des options de configuration et définir des fonctions de rappel lorsqu'un produit est sélectionné.
- **`massqtypro/views/templates/admin/target_products.tpl`**
  - **Portée :** Back-office (partie du formulaire de configuration du module).
  - **Description :** Ce modèle rend la section « Produits cibles » de la page de configuration du module. Il contient le HTML pour tous les critères de sélection de produits : listes déroulantes de catégories, listes déroulantes de marques, sélecteurs de caractéristiques/attributs, sélecteurs de règles de taxe et le champ de saisie semi-automatique de produits spécifiques. Il utilise les assistants de formulaire PrestaShop standard et potentiellement du HTML personnalisé pour les éléments de sélection dynamique.
- **`massqtypro/views/templates/admin/wtd.tpl`**
  - **Portée :** Back-office (partie du formulaire de configuration du module).
  - **Description :** Ce modèle rend la section « Que faire ? » de la page de configuration du module. Il contient le HTML pour les opérations de mise à jour de quantité : boutons radio pour « Augmenter », « Diminuer » ou « Définir à », et le champ de saisie correspondant pour la valeur de la quantité. Il inclut également le bouton de soumission « Mettre à jour les quantités ».
- **`massqtypro/views/templates/hook/form.tpl`**
  - **Portée :** Back-office (formulaire de configuration principal).
  - **Description :** C'est le modèle principal pour la page de configuration du module. Il enveloppe probablement les modèles `target_products.tpl` et `wtd.tpl`, les combinant dans le formulaire de configuration complet. Il gère également la soumission globale du formulaire et affiche les messages de succès ou d'erreur.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** : Le module ne crée aucune table de base de données personnalisée. Il interagit principalement avec les tables PrestaShop existantes, notamment `ps_product`, `ps_product_attribute`, `ps_stock_available`, `ps_category_product`, `ps_manufacturer`, `ps_feature_product`, `ps_product_attribute_combination` et `ps_tax_rule_group_product`. Les paramètres de configuration sont stockés dans `ps_configuration`.
- **Table des hooks enregistrés** :
  La fonctionnalité principale du module est exécutée via sa méthode `getContent()` dans le back-office. Il ne s'enregistre pas explicitement aux hooks front-office à des fins d'affichage. Cependant, le module peut utiliser des hooks en interne pour des actions administratives ou la récupération de données.

  | Nom du hook | Moment d'exécution | Objectif technique |
  | --- | --- | --- |
  | `displayBackOfficeHeader` | Rendu dans la section `<head>` du Back Office. | Potentiellement utilisé pour charger les CSS/JS spécifiques au module pour la page de configuration, bien que souvent géré directement dans `getContent()`. |
  | `actionProductUpdate` | Après la mise à jour d'un produit. | Pourrait être utilisé pour la journalisation interne ou pour déclencher des actions connexes, bien que non explicitement indiqué dans les fonctionnalités. |
  | `actionUpdateQuantity` | Après la mise à jour de la quantité d'un produit. | Pourrait être utilisé pour la journalisation interne ou pour déclencher des actions connexes, bien que non explicitement indiqué dans les fonctionnalités. |

  La logique principale du module pour les mises à jour de quantité manipule directement les entrées `StockAvailable`, ce qui déclenche en interne les mécanismes de mise à jour de stock de PrestaShop.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support technique officiel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour aider les marchands et les développeurs avec tout problème ou question lié au module « Mise à jour de quantité en masse pro ».
"""
