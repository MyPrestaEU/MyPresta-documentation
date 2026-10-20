---
title: "Changement de date de produit - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Changement de date de produit' par MyPresta.eu."
sidebar:
  label: "Changement de date de produit - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Product date change sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/product-date-change.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/product-date-change/)
>
> ---


# Changement de date de produit

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement nécessaire.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à la page de configuration principale du module « Changement de date de produit ». C'est ici que vous sélectionnerez les produits et modifierez leurs dates.

#### **Sélection de produit**

- **Ce que fait ce paramètre :** Cette section vous permet de rechercher et de sélectionner les produits spécifiques dont vous souhaitez modifier les dates.
- **Effet de la modification de ce paramètre :**
  - *Recherche d'un produit :* Taper dans la boîte de recherche filtrera votre liste de produits, facilitant la recherche du produit exact dont vous avez besoin.
  - *Sélection d'un produit :* Une fois un produit sélectionné, ses dates de création et de mise à jour actuelles seront affichées, et vous pourrez saisir de nouvelles dates.
- **Valeur recommandée :** Utilisez la barre de recherche pour localiser rapidement les produits par nom ou par ID.
- **Scénario / exemple pour le marchand :** Vous souhaitez modifier la date de la « Robe d'été 2023 ». Vous tapez « Robe d'été » dans la boîte de recherche, et le module affiche les produits correspondants. Vous cliquez ensuite sur « Robe d'été 2023 » pour la sélectionner.

#### **Modifier la date de création du produit**

- **Ce que fait ce paramètre :** Ce champ vous permet de définir une nouvelle `date_add` (date de création) pour le produit sélectionné. Cette date est souvent utilisée par PrestaShop pour déterminer si un produit est « nouveau ».
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une nouvelle date est saisie et enregistrée :* La date de création du produit dans votre base de données sera mise à jour. Cela peut faire réapparaître le produit dans les blocs « Nouveaux produits » ou modifier sa position lors du tri par « Date d'ajout ».
  - *Lorsqu'il est laissé inchangé :* La date de création originale du produit sera conservée.
- **Valeur recommandée :** Définissez une date qui reflète le moment où vous souhaitez que le produit soit considéré comme « nouveau » ou le moment où il a été réellement ajouté à votre catalogue. Pour une nouvelle mise en avant, une date récente (aujourd'hui ou hier) est idéale.
- **Scénario / exemple pour le marchand :** Votre produit « Manteau d'hiver » a été ajouté l'année dernière. Vous souhaitez le promouvoir comme une « nouvelle arrivée » pour la saison hivernale à venir. Vous sélectionnez le produit, puis définissez la « Date de création du produit » à la date d'aujourd'hui. Maintenant, il apparaîtra dans votre section « Nouveaux produits ».

#### **Modifier la date de mise à jour du produit**

- **Ce que fait ce paramètre :** Ce champ vous permet de définir une nouvelle `date_upd` (date de dernière mise à jour) pour le produit sélectionné. Cette date est utilisée pour le suivi interne et peut également influencer le tri des produits.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une nouvelle date est saisie et enregistrée :* La date de dernière mise à jour du produit dans votre base de données sera modifiée. Cela peut affecter les options de tri où les clients trient par « Date de mise à jour ».
  - *Lorsqu'il est laissé inchangé :* La date de mise à jour originale du produit sera conservée.
- **Valeur recommandée :** Définissez une date qui reflète la dernière fois que vous avez apporté des modifications importantes au produit (par exemple, mise à jour de la description, du prix, des images) ou si vous souhaitez le placer en haut des listes de produits « récemment mis à jour ».
- **Scénario / exemple pour le marchand :** Vous venez de mettre à jour la description et d'ajouter de nouvelles images pour votre produit « Grains de café bio ». Vous souhaitez que ce produit apparaisse plus haut lorsque les clients trient par « récemment mis à jour ». Vous sélectionnez le produit et définissez la « Date de mise à jour du produit » à la date d'aujourd'hui.

#### **Bouton Enregistrer**

- **Ce que fait ce paramètre :** Ce bouton applique toutes les modifications de date que vous avez apportées pour le produit sélectionné.
- **Effet de la modification de ce paramètre :** Cliquer sur « Enregistrer » validera les nouvelles dates de création et/ou de mise à jour dans votre base de données PrestaShop. Vous verrez généralement un message de succès.
- **Valeur recommandée :** Cliquez toujours sur « Enregistrer » après avoir effectué des modifications de date.
- **Scénario / exemple pour le marchand :** Après avoir défini les dates de création et de mise à jour pour vos « Baskets en édition limitée », vous cliquez sur « Enregistrer » pour appliquer ces modifications à votre boutique.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Champ de recherche de produit | N/A | Recherchez des produits par nom ou ID pour modifier leurs dates. |
| Page de configuration du module | Modifier la date de création du produit | `date_add` actuelle du produit | Définit une nouvelle date de création. Affecte la visibilité des « Nouveaux produits » et le tri par « Date d'ajout ». Recommandé : Une date récente pour une nouvelle mise en avant. |
| Page de configuration du module | Modifier la date de mise à jour du produit | `date_upd` actuelle du produit | Définit une nouvelle date de dernière mise à jour. Affecte le tri par « Date de mise à jour ». Recommandé : Une date récente après des modifications importantes du produit. |
| Page de configuration du module | Bouton Enregistrer | N/A | Applique toutes les modifications de date sélectionnées au produit dans la base de données. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai changé la date, mais le produit n'apparaît pas comme « nouveau » sur ma page d'accueil. Quel est le problème ?**
R1 :

- **Vider le cache :** PrestaShop s'appuie fortement sur la mise en cache. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures). C'est la solution la plus courante.
- **Configuration du module :** Vérifiez les paramètres de votre module « Nouveaux produits » (par exemple, « Bloc Nouveaux produits » ou « Page Nouveaux produits »). Assurez-vous qu'il est configuré pour afficher les produits en fonction de leur date de création et que le nombre de jours pour les produits « nouveaux » est défini de manière appropriée (par exemple, 30 jours). Si vous définissez la date de création d'un produit comme étant antérieure à ce seuil, il n'apparaîtra pas comme nouveau.
- **Spécificités du thème :** Certains thèmes peuvent avoir leur propre mise en cache ou une logique personnalisée pour les « nouveaux produits ». Si vider le cache ne fonctionne pas, consultez la documentation ou le support de votre thème.

**Q2 : Le changement de date du produit affectera-t-il mon SEO ?**
R2 : Directement, non. Les moteurs de recherche comme Google se concentrent principalement sur le contenu de votre page produit (description, images, avis) et les liens externes, et non sur les dates de produit internes de PrestaShop. Cependant, indirectement, si le changement de date fait apparaître le produit comme « nouveau » et génère plus de trafic interne ou de ventes, cet engagement accru *peut* influencer positivement le SEO au fil du temps. Il s'agit plus de l'expérience utilisateur et du merchandising que de la manipulation directe du SEO.

**Q3 : Puis-je modifier les dates de plusieurs produits à la fois (édition en masse) ?**
R3 : Ce module est conçu pour les modifications de date de produits individuels. Si vous avez besoin de modifier en masse les dates d'un grand nombre de produits, vous auriez généralement besoin d'un outil d'importation/exportation plus avancé ou d'un script personnalisé. Pour quelques produits, les faire un par un avec ce module est efficace.

**Q4 : Que se passe-t-il si je définis une date future ?**
R4 : PrestaShop acceptera une date future. Cependant, l'effet pratique pourrait être limité. Un produit défini avec une date de création future pourrait ne pas apparaître dans les listes de « nouveaux produits » avant cette date. Il est généralement recommandé d'utiliser des dates actuelles ou passées.

**Q5 : J'ai changé la date, mais lorsque je modifie le produit dans le Back Office, l'ancienne date est toujours là.**
R5 : Ce module modifie directement les champs `date_add` et `date_upd` dans la base de données. Lorsque vous visualisez un produit dans la page d'édition de produit standard de PrestaShop, il devrait refléter ces modifications. Si ce n'est pas le cas, assurez-vous d'avoir cliqué sur « Enregistrer » dans la configuration du module, vidé votre cache PrestaShop et rechargé la page d'édition du produit. Si le problème persiste, il pourrait y avoir un conflit avec un autre module ou un problème de mise en cache plus profond.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Vue d'ensemble de l'architecture

Le module `Product date change` (`pdc`) est un module PrestaShop simple conçu pour interagir directement avec l'ObjectModel `Product`. Il utilise la méthode standard `getContent()` pour sa configuration Back Office, fournissant un formulaire simple pour sélectionner un produit et modifier ses champs `date_add` et `date_upd`. Il n'introduit pas de nouvelles tables de base de données, de contrôleurs complexes ou de logique front-office étendue, ce qui le rend léger et axé sur sa tâche administrative principale.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient aucun contrôleur front-office ou back-office personnalisé. Toute la logique est encapsulée dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles de base (`classes/`)

Ce module n'introduit aucune classe ou ObjectModel personnalisé dans le répertoire `classes/`. Il interagit directement avec l'ObjectModel `Product` de base de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé. Le style est censé être géré par les styles par défaut du Back Office de PrestaShop.

### 4.6 Structure du template Smarty (`views/templates/`)

- **`pdc/views/pdc.tpl`** :
  - **Portée** : Configuration d'administration du Back Office.
  - **Objectif** : Ce template rend le formulaire de configuration principal du module. Il comprend :
    - Un champ de saisie de recherche pour trouver des produits.
    - Des zones d'affichage pour les `date_add` et `date_upd` actuelles du produit sélectionné.
    - Des champs de saisie (probablement des sélecteurs de date) pour définir de nouvelles valeurs `date_add` et `date_upd`.
    - Un bouton de soumission pour enregistrer les modifications.
  - **Utilisation** : Ce template est rendu par la méthode `getContent()` du module `pdc`.
  - **Sélecteurs clés** : Les développeurs peuvent inspecter le HTML généré pour des ID ou des classes spécifiques afin de remplacer le style si nécessaire, bien que cela ne soit généralement pas requis pour un simple formulaire d'administration.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Ce module ne crée aucune table de base de données personnalisée.
  - Il modifie directement les colonnes `date_add` et `date_upd` dans la table `ps_product` existante (et potentiellement `ps_product_shop` si des dates spécifiques au contexte sont gérées, bien que la description du module implique une modification directe de l'objet produit).
  - Les valeurs de configuration (le cas échéant, bien qu'aucune ne soit explicitement répertoriée au-delà de la manipulation directe du produit) seraient stockées dans `ps_configuration`.
- **Table des hooks enregistrés** :
  Ce module n'enregistre aucun hook spécifique pour l'affichage front-office ou les actions back-office au-delà du standard `displayBackOfficeHeader` (pour les actifs, le cas échéant) et `moduleRoutes` (si des URL personnalisées étaient nécessaires, ce qui n'est pas le cas pour ce module). Son interaction principale se fait via la méthode `getContent()`.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayBackOfficeHeader` | Rendu dans la section `<head>` des pages du Back Office. | (Potentiellement) Pour inclure les JS/CSS nécessaires à la page de configuration du module, bien qu'aucun ne soit présent dans ce module. |
| `actionProductUpdate` | Exécuté après la mise à jour d'un produit. | La logique interne du module pour la mise à jour des dates de produit pourrait déclencher ce hook, mais le module lui-même ne s'enregistre pas explicitement pour l'écouter ou effectuer des actions basées sur celui-ci. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Changement de date de produit », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité et la compatibilité du module.
