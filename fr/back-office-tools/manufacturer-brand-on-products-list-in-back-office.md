---
title: "Fabricant (marque) sur la liste des produits dans le back office - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Fabricant (marque) sur la liste des produits dans le back office' par MyPresta.eu."
sidebar:
  label: "Fabricant (marque) sur la liste des produits dans le back office - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Manufacturer (brand) on products list in back office sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/manufacturer-brand-on-products-list-in-back-office.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/manufacturer-brand-on-products-list-in-back-office/)
>
> ---


# Fabricant (marque) sur la liste des produits dans le back office

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.0.0 - 1.7.7.x, 1.7.8.x, 8.x (liste standard), 8.x (liste de produits expérimentale), 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur "Configurer" vous mènera à la page principale des paramètres du module. Cette page gère principalement les notifications de mise à jour et la maintenance générale du module.

- **Ce que fait ce paramètre :** Cette section gère généralement la manière dont le module vérifie les mises à jour et affiche les notifications.
- **Effet de la modification de ce paramètre :**
  - *Lorsque activé :* Le module vérifiera périodiquement MyPresta.eu pour de nouvelles versions et vous informera si une mise à jour est disponible. Cela vous aide à maintenir votre module à jour avec les dernières fonctionnalités et corrections de bugs.
  - *Lorsque désactivé :* Le module ne vérifiera pas les mises à jour automatiquement, et vous ne recevrez pas de notifications concernant les nouvelles versions. Vous devrez vérifier manuellement votre compte MyPresta.eu pour les mises à jour.
- **Valeur recommandée :** **Activé (Oui)**. Garder cette option activée garantit que vous êtes toujours informé des mises à jour disponibles, ce qui est crucial pour la sécurité et la compatibilité avec les futures versions de PrestaShop.
- **Scénario/exemple pour le marchand :** Vous souhaitez être informé lorsqu'une nouvelle version du module est publiée et prend en charge les dernières fonctionnalités de PrestaShop 8.x. L'activation de ce paramètre garantit que vous recevez cette notification directement dans votre back office.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Ce module n'introduit pas de nouveaux éléments de menu séparés ou d'écrans d'administration dédiés pour gérer sa fonctionnalité principale. Au lieu de cela, ses modifications sont intégrées directement dans la page existante **Catalogue > Produits**.

**Nom de l'écran et emplacement du menu :**

- **Catalogue > Produits** (La page standard de liste de produits PrestaShop)

**Actions et paramètres disponibles :**
En naviguant vers **Catalogue > Produits**, vous remarquerez immédiatement les changements introduits par le module :

- **Nouvelle colonne : Fabricant/Marque :** Une nouvelle colonne apparaîtra dans votre liste de produits affichant le nom du fabricant associé à chaque produit.
- **Logo du fabricant (facultatif) :** Selon la logique interne du module, il peut également afficher le logo du fabricant à côté du nom, s'il est disponible et configuré.
- **Filtrer par fabricant :** Au-dessus de la liste des produits, vous trouverez une nouvelle option de filtre, généralement un menu déroulant, vous permettant de sélectionner un fabricant spécifique. Une fois sélectionnée, la liste des produits se mettra à jour instantanément pour n'afficher que les produits de cette marque.

**Effet des changements :**

- **Ajout de la colonne Fabricant :** Fournit un repère visuel immédiat pour la marque de chaque produit, éliminant le besoin d'ouvrir les pages de produits individuellement pour vérifier cette information.
- **Filtrage par Fabricant :** Accélère considérablement les tâches où vous devez travailler avec des produits d'une marque spécifique. Par exemple, si un fabricant annonce une augmentation de prix, vous pouvez rapidement filtrer tous ses produits et mettre à jour les prix. Ou si vous devez vérifier les niveaux de stock pour les articles d'une marque particulière.

**Flux de travail recommandé pour la gestion quotidienne de la boutique :**

1. **Identification rapide de la marque :** Lorsque vous parcourez votre liste de produits, utilisez la nouvelle colonne "Fabricant" pour identifier rapidement les marques.
2. **Gestion ciblée :** Si vous devez effectuer une action sur tous les produits d'une marque spécifique (par exemple, mettre à jour les descriptions, ajuster les prix, vérifier l'inventaire), utilisez le nouveau menu déroulant "Filtrer par Fabricant" en haut de la liste des produits. Sélectionnez la marque souhaitée, et votre liste sera instantanément affinée.
3. **Actions en masse :** Combinez le filtre par fabricant avec les actions en masse standard de PrestaShop (par exemple, sélectionner plusieurs produits et appliquer un changement) pour une gestion très efficace et spécifique à la marque.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Notifications de mise à jour | Activé | Vous informe des nouvelles versions du module pour la sécurité et les fonctionnalités. |
| Catalogue > Liste de produits | Colonne Fabricant | N/A (Toujours activé) | Affiche la marque du produit directement dans la liste des produits pour une identification rapide. |
| Catalogue > Liste de produits | Filtrer par Fabricant | N/A (Toujours activé) | Permet de filtrer la liste des produits par une marque spécifique, simplifiant les tâches de gestion spécifiques à la marque. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai installé le module, mais je ne vois pas la colonne ou le filtre du fabricant sur ma liste de produits.**
R :

1. **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions plus anciennes). Parfois, PrestaShop a besoin d'une actualisation du cache pour afficher de nouveaux éléments.
2. **Module activé :** Vérifiez que le module est bien activé dans **Modules > Gestionnaire de modules**.
3. **Compatibilité de la version de PrestaShop :** Assurez-vous d'avoir téléchargé la version correcte du module pour votre installation PrestaShop spécifique. Si vous êtes sur PrestaShop 8.x, assurez-vous de ne pas avoir accidentellement installé une version 1.7.x, par exemple.
4. **Surcharges de thème :** Bien que le module soit conçu sans surcharges, un thème fortement personnalisé ou un autre module pourrait entrer en conflit. Si le problème persiste, essayez de désactiver les autres modules un par un pour identifier un conflit.

**Q : Le nom du fabricant apparaît, mais pas le logo.**
R : Le module se concentre principalement sur l'affichage du nom du fabricant. S'il prend en charge les logos, assurez-vous que :

1. **Logo du fabricant téléchargé :** Vous avez bien téléchargé un logo pour ce fabricant dans **Catalogue > Fabricants** dans votre back office PrestaShop.
2. **Paramètre du module :** Il peut y avoir un paramètre interne (bien que non exposé dans la configuration de base de ce module) qui contrôle l'affichage du logo. Si ce n'est pas le cas, cela signifie que le module est conçu pour afficher uniquement le nom.

**Q : Puis-je modifier la position de la colonne du fabricant dans la liste des produits ?**
R : Ce module s'intègre directement dans le système de grille de produits de PrestaShop. La position exacte de la colonne est déterminée par la configuration de la liste de produits de base de PrestaShop. Bien que ce module ajoute la colonne, il n'offre généralement pas d'options pour glisser-déposer les positions des colonnes. Vous pourriez avoir besoin d'un module de personnalisation de grille plus avancé ou d'un développement personnalisé pour réorganiser les colonnes.

**Q : Ce module ralentit-il mon back office ?**
R : Non, le module est conçu pour être léger et efficace. Il utilise le système de hooks natif de PrestaShop pour ajouter les données du fabricant sans traitement lourd. Vous ne devriez pas ressentir de ralentissements notables.

**Q : Ce module fonctionnera-t-il avec la nouvelle page de produit expérimentale de PrestaShop 8.x ?**
R : Oui, la description du module indique explicitement la compatibilité avec la "liste de produits expérimentale 8.x", ce qui signifie qu'il est conçu pour fonctionner à la fois avec les interfaces de liste de produits standard et les nouvelles interfaces expérimentales de PrestaShop 8.x.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Vue d'ensemble de l'architecture

Le module `Fabricant (marque) sur la liste des produits dans le back office` (nom interne `dpmypresta`) est conçu pour améliorer la page de liste des produits du Back Office de PrestaShop en ajoutant des informations sur le fabricant. Il adhère à une approche sans surcharge, s'appuyant fortement sur le système de hooks de PrestaShop, en particulier les hooks `actionProductGrid*` introduits dans PrestaShop 1.7.x pour modifier la grille du catalogue de produits. Cela le rend robuste face aux mises à jour du cœur de PrestaShop. Le module injecte principalement de nouvelles colonnes et des capacités de filtrage dans les données de la grille de produits existante et le processus de rendu.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs front-office. Il inclut deux fichiers de contrôleur d'administration, mais `AdminDpMyPrestaController.php` semble être un espace réservé ou un vestige, et `index.php` est un fichier vide standard pour empêcher l'affichage du répertoire. La logique principale du module pour la configuration est gérée dans la méthode `getContent()` de `dpmypresta.php`, et les modifications de la grille de produits sont gérées via des hooks.

- **Contrôleurs Front-Office** : Aucun. Toutes les fonctionnalités sont spécifiques au back-office.
- **Contrôleurs d'administration Back-Office** :
  - `controllers/admin/AdminDpMyPrestaController.php`
    - Nom de la classe : `AdminDpMyPrestaController` (étend `ModuleAdminController`)
    - Responsabilité : Ce contrôleur est présent mais semble être un espace réservé. Sa méthode `__construct` configure le contexte de base du module. Il ne définit aucune action spécifique ni ne rend aucune vue unique au-delà de ce qui pourrait être hérité de `ModuleAdminController`. Il n'est pas directement lié à la fonctionnalité principale d'ajout de données de fabricant à la liste de produits, qui est pilotée par les hooks.
  - `controllers/admin/index.php`
    - Fichier `index.php` vide standard pour la sécurité afin d'empêcher l'affichage du répertoire.

### 4.3 Classes et modèles de base (`classes/`)

Le module ne définit aucune classe personnalisée ni aucun `ObjectModel` dans le répertoire `classes/`. Ses opérations sont directement intégrées dans les structures de données et les mécanismes de grille existants de PrestaShop via des hooks.

### 4.4 Actifs JavaScript (`views/js/`)

Le module n'inclut aucun fichier JavaScript personnalisé. Toutes les interactions et la logique d'affichage pour la colonne et le filtre du fabricant sont gérées par les composants de grille natifs de PrestaShop et la logique PHP du module.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module n'inclut aucun fichier CSS personnalisé. Le style de la colonne et du filtre du fabricant ajoutés est hérité du thème du back office de PrestaShop.

### 4.6 Structure des templates Smarty (`views/templates/`)

Le module utilise le nouveau système de templating Twig utilisé dans PrestaShop 1.7+ pour les grilles du back-office.

- **Templates d'administration (`views/templates/admin/`)** :
  - `views/PrestaShop/Admin/Product/CatalogPage/Lists/list.html.twig`
    - Ce template Twig étend ou modifie probablement le template de liste de produits principal de PrestaShop. Il est responsable du rendu de la page globale du catalogue de produits, y compris la grille. Le module injecte la colonne et le filtre du fabricant dans cette structure.
  - `views/PrestaShop/Admin/Product/CatalogPage/Lists/products_table.html.twig`
    - Ce template Twig rend spécifiquement le tableau des produits dans la page du catalogue. Le module modifie ce template pour ajouter les données du fabricant à chaque ligne de produit.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de la base de données** : Le module ne crée aucune table de base de données personnalisée. Il s'appuie sur les tables PrestaShop existantes, principalement `ps_product`, `ps_manufacturer` et `ps_configuration` pour ses paramètres.

  - Les valeurs de configuration (`mypresta_updates`, `update_`, `updatev_`) sont stockées dans la table `ps_configuration`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionProductGridDataModifier` | Après la récupération des données produit pour la grille. | Modifie le tableau de données brutes pour chaque produit, en injectant l'ID et le nom du fabricant. |
| `actionAdminProductsListingFieldsModifier` | Avant la définition des champs de la grille de produits. | Ajoute la définition de la colonne 'Fabricant' à la grille de produits. |
| `actionProductGridDefinitionModifier` | Modifie la définition de la grille de produits elle-même. | Ajoute potentiellement le filtre du fabricant à la collection de filtres de la grille. |
| `actionAdminProductsListingResultsModifier` | Après la préparation des résultats de la liste de produits. | Modifie davantage les résultats, en s'assurant que les données du fabricant sont correctement formatées pour l'affichage. |
| `actionProductGridQueryBuilderModifier` | Modifie le Query Builder de Doctrine pour la grille de produits. | Joint la table `ps_manufacturer` à la requête produit et ajoute des conditions pour le filtrage par fabricant. |
| `displayBackOfficeHeader` | Rend le contenu dans la section `<head>` du Back Office. | Utilisé pour charger les actifs spécifiques au module (bien qu'aucun ne soit présent dans ce module) ou pour les vérifications de mise à jour. |
| `displayAdminProductsExtra` | Rend du contenu supplémentaire sur la page produit (non directement utilisé pour la modification de liste). | Non directement lié à la fonctionnalité principale de ce module, mais un hook courant pour les extensions de page produit d'administration. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et une assistance supplémentaire concernant le module "Fabricant (marque) sur la liste des produits dans le back office", veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est prête à vous aider pour toutes questions ou problèmes que vous pourriez rencontrer.
