---
title: "Séparer les combinaisons en produits distincts - Manuel du Marchand & Guide de Configuration"
description: ""
sidebar:
  label: "Séparer les combinaisons en produits distincts - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Split combinations into separate products sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/split-combinations-into-separate-products.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/split-combinations-into-separate-products/)
>
> ---


# Séparer les combinaisons en produits distincts

## 1. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 1.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal du module, accessible en cliquant sur « Configurer » après l'installation.

#### Paramètres généraux

- **Activer le module :**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les fonctionnalités du module, y compris la capacité de séparer les produits et sa logique d'affichage, deviennent actives.
    - *Lorsqu'il est désactivé :* La fonctionnalité du module est complètement désactivée. Aucune combinaison ne sera séparée, et tous les produits séparés existants reviendront à leur état d'origine ou seront gérés comme des produits réguliers en fonction de la logique interne du module.
  - **Valeur recommandée :** OUI (une fois que vous êtes prêt à utiliser le module).
  - **Scénario / exemple de marchand :** Vous configurez le module pour la première fois et souhaitez le tester. Vous l'activez pour voir ses effets. Si vous devez le désactiver temporairement pour la maintenance, vous pouvez le désactiver.
- **Mode de séparation :**

  - **Ce que fait ce paramètre :** Détermine comment le module gère les combinaisons de produits. Vous pouvez choisir entre créer de nouveaux produits réels pour chaque combinaison ou simplement modifier la façon dont ils sont affichés sur les pages de liste.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur « Créer des produits séparés pour chaque combinaison » :* Le module créera physiquement de nouvelles entrées de produit dans votre base de données pour chaque combinaison. Chaque nouveau produit aura son propre ID, URL, stock, prix, etc. C'est l'option la plus puissante pour le référencement et le contrôle granulaire.
    - *Lorsqu'il est défini sur « Afficher une tuile par combinaison sur les listes de catégories, de marques, de fournisseurs, de recherche et de meilleures ventes (séparation virtuelle) » :* Le module ne créera *pas* de nouveaux produits. Au lieu de cela, il modifiera la façon dont les produits existants avec des combinaisons sont affichés sur les pages de liste, donnant l'impression que chaque combinaison est un produit distinct. Le catalogue de produits réel reste inchangé. C'est moins impactant pour le référencement mais peut améliorer l'expérience de navigation.
  - **Valeur recommandée :** « Créer des produits séparés pour chaque combinaison » pour un maximum de référencement et de contrôle, ou « Afficher une tuile par combinaison… » pour une amélioration d'affichage plus simple.
  - **Scénario / exemple de marchand :** Vous voulez que chaque couleur et taille de votre T-shirt ait sa propre page produit et se classe dans Google. Vous choisissez « Créer des produits séparés ». Si vous voulez juste rendre vos pages de catégories plus propres en affichant chaque variation sans créer de nouveaux produits, vous choisissez « Afficher une tuile par combinaison ».
- **Ne séparer que les produits actifs :**

  - **Ce que fait ce paramètre :** Contrôle si le module doit traiter uniquement les produits actuellement activés dans votre boutique, ou tous les produits quel que soit leur statut actif.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Seuls les produits actuellement définis comme « actifs » dans votre catalogue PrestaShop verront leurs combinaisons séparées. Les produits inactifs seront ignorés.
    - *Lorsqu'il est désactivé :* Le module tentera de séparer les combinaisons pour tous les produits, y compris ceux qui sont actuellement inactifs.
  - **Valeur recommandée :** OUI (pour éviter de créer des produits inutiles pour des articles que vous ne vendez pas).
  - **Scénario / exemple de marchand :** Vous avez de nombreux produits anciens et inactifs dans votre catalogue. Vous ne voulez séparer les combinaisons que pour votre inventaire actuel et actif afin de garder votre boutique organisée. Vous activez ce paramètre.
- **Action sur le produit source après la séparation :**

  - **Ce que fait ce paramètre :** Définit ce qui arrive au produit original (celui avec les combinaisons) après que ses combinaisons ont été séparées en nouveaux produits individuels.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur « Désactiver le produit source » :* Le produit original sera marqué comme inactif dans votre catalogue. Il ne sera plus visible dans le front office.
    - *Lorsqu'il est défini sur « Garder le produit source actif » :* Le produit original restera actif et visible dans votre boutique. Vous devrez peut-être ajuster manuellement son affichage ou son contenu pour éviter toute confusion avec les nouveaux produits séparés.
    - *Lorsqu'il est défini sur « Supprimer le produit source » :* Le produit original sera définitivement supprimé de votre catalogue. À utiliser avec une extrême prudence !
  - **Valeur recommandée :** « Désactiver le produit source » ou « Garder le produit source actif » (selon votre stratégie). « Supprimer le produit source » n'est généralement pas recommandé, sauf si vous en êtes absolument sûr.
  - **Scénario / exemple de marchand :** Vous avez séparé un produit « T-shirt » en « T-shirt - Rouge - S », « T-shirt - Bleu - M », etc. Vous voulez que les clients ne voient que les variations individuelles, vous choisissez donc « Désactiver le produit source » pour le « T-shirt » original.
- **Copier les images du produit :**

  - **Ce que fait ce paramètre :** Détermine si les images associées au produit original et à ses combinaisons doivent être copiées vers les nouveaux produits séparés créés.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les images du produit original et de sa combinaison spécifique seront dupliquées et attribuées au nouveau produit séparé. Cela garantit que chaque nouveau produit a des visuels pertinents.
    - *Lorsqu'il est désactivé :* Les nouveaux produits séparés seront créés sans aucune image. Vous devrez alors télécharger manuellement des images pour chaque nouveau produit, ce qui est très chronophage.
  - **Valeur recommandée :** OUI.
  - **Scénario / exemple de marchand :** Vous avez une combinaison « T-shirt Rouge » avec une image spécifique. Lorsque vous la séparez en « T-shirt - Rouge - Petit », vous voulez que cette image de t-shirt rouge soit automatiquement attribuée au nouveau produit.
- **Nombre minimum de combinaisons à séparer :**

  - **Ce que fait ce paramètre :** Définit un seuil pour le nombre de combinaisons qu'un produit doit avoir avant que le module ne considère de le séparer. Les produits avec moins de combinaisons que cette valeur seront ignorés.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur une valeur (par exemple, 2) :* Seuls les produits qui ont 2 combinaisons ou plus seront traités. Les produits avec seulement 1 combinaison (ou aucune combinaison) seront ignorés.
    - *Lorsqu'il est défini sur 0 ou 1 :* Tous les produits avec au moins une combinaison seront considérés pour la séparation.
  - **Valeur recommandée :** 2 (pour éviter de séparer des produits simples qui pourraient ne pas en bénéficier).
  - **Scénario / exemple de marchand :** Vous avez des produits avec une seule combinaison (par exemple, un T-shirt « Taille Unique »). Vous ne voulez pas les séparer, mais vous voulez séparer les produits avec plusieurs couleurs et tailles. Vous définissez ce paramètre sur 2.

#### Paramètres du générateur de noms

Ces paramètres contrôlent la façon dont les noms des nouveaux produits séparés sont générés.

- **Modèle de générateur de noms :**

  - **Ce que fait ce paramètre :** Vous permet de définir un modèle personnalisé pour générer les noms des nouveaux produits séparés. Vous pouvez utiliser des espaces réservés pour le nom du produit, les noms des groupes d'attributs et les noms des attributs.
  - **Effet de la modification de ce paramètre :** Le module utilisera ce modèle pour construire le champ `name` de chaque nouveau produit.
  - **Valeur recommandée :** `[product_name] - [attribute_group_name]: [attribute_name]` (ou similaire, selon le style de votre marque).
  - **Scénario / exemple de marchand :** Votre produit original est « Robe Fantaisie ». Il a des combinaisons comme « Couleur : Rouge » et « Taille : Petite ». Si votre modèle est `[product_name] - [attribute_name]`, le nouveau nom du produit serait « Robe Fantaisie - Rouge ».
- **Modèle de générateur d'URL :**

  - **Ce que fait ce paramètre :** Similaire au générateur de noms, cela vous permet de définir un modèle personnalisé pour générer les URL conviviales (slugs) des nouveaux produits séparés.
  - **Effet de la modification de ce paramètre :** Le module utilisera ce modèle pour construire le champ `link_rewrite` de chaque nouveau produit.
  - **Valeur recommandée :** `[product_name]-[attribute_name]` (ou similaire, en s'assurant qu'il est optimisé pour le référencement et unique).
  - **Scénario / exemple de marchand :** En utilisant l'exemple de la « Robe Fantaisie », si votre modèle d'URL est `[product_name]-[attribute_name]`, la nouvelle URL pourrait être `/robe-fantaisie-rouge`.
- **Séparateur pour les attributs multiples :**

  - **Ce que fait ce paramètre :** Spécifie le caractère ou la chaîne de caractères utilisée pour séparer plusieurs noms d'attributs lorsqu'ils sont combinés dans le nom du produit ou l'URL.
  - **Effet de la modification de ce paramètre :** Ce caractère sera inséré entre les noms d'attributs si un produit a des combinaisons de plusieurs groupes d'attributs (par exemple, Couleur et Taille).
  - **Valeur recommandée :** `-` (tiret) pour les URL, `,` (virgule espace) pour les noms.
  - **Scénario / exemple de marchand :** Si un produit est « T-shirt - Rouge - Petit », le tiret est le séparateur. Vous pouvez le changer en barre oblique `/` si vous préférez.

#### Paramètres avancés

- **Rediriger les anciennes URL :**

  - **Ce que fait ce paramètre :** Si activé, le module créera des redirections 301 de l'URL du produit original (et potentiellement des URL spécifiques aux combinaisons) vers l'URL du nouveau produit séparé. C'est crucial pour le référencement.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les moteurs de recherche et les utilisateurs accédant aux anciennes URL seront automatiquement redirigés vers la nouvelle page produit correcte, préservant la valeur SEO et évitant les liens brisés.
    - *Lorsqu'il est désactivé :* Les anciennes URL mèneront à des erreurs 404 « Page non trouvée », nuisant à votre référencement et à l'expérience utilisateur.
  - **Valeur recommandée :** OUI.
  - **Scénario / exemple de marchand :** Vous avez séparé « T-shirt » en « T-shirt - Rouge - Petit ». Si un client ou un moteur de recherche tente d'accéder à l'ancienne page « T-shirt », il sera automatiquement envoyé vers la nouvelle page produit séparée la plus pertinente.
- **Vider le cache après la séparation :**

  - **Ce que fait ce paramètre :** Vide automatiquement le cache de PrestaShop après qu'une opération de séparation est effectuée.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Garantit que les modifications apportées par le module (nouveaux produits, redirections) sont immédiatement visibles sur le front office sans vidage manuel du cache.
    - *Lorsqu'il est désactivé :* Vous devrez peut-être vider manuellement le cache (Paramètres avancés > Performances) pour que les modifications apparaissent.
  - **Valeur recommandée :** OUI.
  - **Scénario / exemple de marchand :** Vous venez de séparer un grand nombre de produits. L'activation de cette option garantit que vos clients voient les nouvelles listes de produits immédiatement sans que vous ayez à vider manuellement le cache.

### 1.2 Écrans d'administration dédiés et vues de contrôleur

#### AdminMySplitProductsController (Back Office > Modules > Séparer les combinaisons en produits distincts > Gérer les séparations)

Cet écran fournit l'interface pour initier, gérer et annuler les opérations de séparation de produits.

- **Nom de l'écran et emplacement du menu :** « Gérer les séparations » (accessible depuis la page de configuration principale du module ou potentiellement un nouvel élément de menu sous « Catalogue » ou « Modules »).
- **Actions et paramètres disponibles :**
  - **Recherche et sélection de produits :** Une barre de recherche et une fonction de saisie semi-automatique pour trouver des produits spécifiques que vous souhaitez séparer.
  - **Bouton « Séparer le produit » :** Lance le processus de séparation pour le produit sélectionné.
  - **Bouton « Annuler » :** Vous permet d'annuler une opération de séparation précédente pour un produit spécifique, en restaurant le produit original et en supprimant les produits séparés.
  - **Tableau d'historique :** Une liste de tous les produits qui ont été séparés, affichant :
    - Nom du produit original
    - Date de séparation
    - Nombre de combinaisons séparées
    - Statut (par exemple, « Terminé », « Annulé »)
    - Boutons d'action (par exemple, « Annuler », « Voir les produits séparés »)
- **Effet des modifications :**
  - **Séparer un produit :** Crée de nouvelles entrées de produit dans votre catalogue en fonction des combinaisons du produit sélectionné et des paramètres de configuration du module (noms, URL, images, etc.). Le statut du produit original peut changer (par exemple, désactivé).
  - **Annuler une séparation :** Supprime les produits créés lors de la séparation et restaure le produit original à son état avant la séparation (par exemple, le réactive, restaure ses combinaisons). C'est une puissante fonction d'annulation.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Utilisez la barre de recherche pour trouver le produit que vous souhaitez séparer.
  2. Examinez les noms et URL proposés (si un aperçu est disponible).
  3. Cliquez sur « Séparer le produit ».
  4. Surveillez le tableau d'historique pour le statut.
  5. Si vous faites une erreur ou changez d'avis, utilisez la fonction « Annuler » du tableau d'historique.

#### index.php (mysplitproducts/controllers/admin/index.php)

Ce fichier sert probablement de placeholder ou de base pour les contrôleurs d'administration du module, garantissant les meilleures pratiques de sécurité de PrestaShop en empêchant la liste directe des répertoires. Il ne représente pas un écran distinct visible par l'utilisateur mais fait partie de la structure interne du module.

### 1.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Activer le module | OUI | Interrupteur principal pour la fonctionnalité du module. |
|  | Mode de séparation | « Créer des produits séparés » | Comment les combinaisons sont gérées (nouveaux produits vs. affichage virtuel). |
|  | Ne séparer que les produits actifs | OUI | Traiter uniquement les produits actifs. |
|  | Action sur le produit source après la séparation | « Désactiver le produit source » | Ce qui arrive au produit original. |
|  | Copier les images du produit | OUI | Dupliquer les images vers les nouveaux produits séparés. |
|  | Nombre minimum de combinaisons à séparer | 2 | Seuil pour la séparation des produits. |
|  | Modèle de générateur de noms | `[product_name] - [attribute_group_name]: [attribute_name]` | Définit les noms des nouveaux produits. |
|  | Modèle de générateur d'URL | `[product_name]-[attribute_name]` | Définit les URL conviviales des nouveaux produits. |
|  | Séparateur pour les attributs multiples | `-` (pour URL), `,` (pour nom) | Caractère pour séparer plusieurs attributs. |
|  | Rediriger les anciennes URL | OUI | Crée des redirections 301 pour le référencement. |
|  | Vider le cache après la séparation | OUI | Vide automatiquement le cache de PrestaShop. |
| **Gérer les séparations (AdminMySplitProductsController)** | Recherche et séparation de produits | N/A | Trouver et initier la séparation des produits. |
|  | Annuler la séparation | N/A | Annuler une opération de séparation précédente. |
|  | Tableau d'historique | N/A | Afficher et gérer les opérations de séparation passées. |

## 2. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Après avoir séparé les produits, je ne vois pas les nouveaux produits dans mes catégories ou les résultats de recherche.**

- **R :** La raison la plus courante est la mise en cache.
  - **Solution :** Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop. Cliquez sur « Vider le cache » (ou « Vider le cache Smarty » et « Vider le cache » pour tous les caches). Si le paramètre du module « Vider le cache après la séparation » est activé, cela devrait se produire automatiquement, mais un vidage manuel est parfois nécessaire. Assurez-vous également que les nouveaux produits sont définis comme « actifs » et associés à des catégories.

**Q2 : Mes anciennes URL de produits affichent maintenant « Page non trouvée » (erreurs 404).**

- **R :** Cela signifie généralement que la fonction de redirection n'est pas active ou ne fonctionne pas correctement.
  - **Solution :** Allez sur la page de configuration du module et assurez-vous que « Rediriger les anciennes URL » est défini sur OUI. Si c'est déjà activé, videz votre cache PrestaShop (Paramètres avancés > Performances). Si le problème persiste, vérifiez le fichier `.htaccess` de votre serveur pour d'éventuelles règles de réécriture conflictuelles, ou contactez le support.

**Q3 : Les noms ou les URL de mes nouveaux produits séparés semblent étranges ou ne sont pas ce à quoi je m'attendais.**

- **R :** Ceci est contrôlé par les paramètres « Modèle de générateur de noms » et « Modèle de générateur d'URL ».
  - **Solution :** Allez sur la page de configuration du module et examinez ces modèles. Assurez-vous que vous utilisez les bons espaces réservés (`[product_name]`, `[attribute_name]`, `[attribute_group_name]`) et que les séparateurs sont appropriés. Vous pouvez d'abord tester différents modèles sur un seul produit. N'oubliez pas de vider le cache après avoir apporté des modifications aux modèles.

**Q4 : Certains produits avec des combinaisons n'ont pas été séparés, même si j'ai initié le processus.**

- **R :** Vérifiez le paramètre « Nombre minimum de combinaisons à séparer » dans la configuration du module.
  - **Solution :** Si un produit a moins de combinaisons que ce seuil, il sera ignoré. Ajustez ce paramètre si vous souhaitez séparer des produits avec moins de variations. Assurez-vous également que « Ne séparer que les produits actifs » n'empêche pas le traitement des produits inactifs si telle est votre intention.

**Q5 : Que se passe-t-il avec les paniers des clients si je sépare un produit qu'ils ont déjà ajouté ?**

- **R :** Le module est conçu pour gérer cela avec élégance. Les paniers ouverts existants qui contiennent une combinaison d'un produit qui a été séparé seront généralement mis à jour pour refléter le nouvel ID de produit distinct. Cela signifie que le panier du client contiendra toujours le bon article, maintenant lié à sa nouvelle entrée de produit individuelle. Cependant, il est toujours préférable d'effectuer les séparations pendant les périodes de faible trafic ou de tester minutieusement.

## 3. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 3.1 Vue d'ensemble de l'architecture

Le module « Séparer les combinaisons en produits distincts » (`mysplitproducts`) est construit en suivant le modèle MVC (Modèle-Vue-Contrôleur) de PrestaShop. Il utilise fortement `ObjectModel` pour la persistance des données, un `AdminController` personnalisé pour son interface Back Office, et un ensemble de classes de service dédiées pour encapsuler la logique complexe de la séparation des produits, de la dénomination et de la redirection. Le module étend les fonctionnalités de base de PrestaShop en créant et en gérant dynamiquement des entités de produit, en gérant les réécritures d'URL et en s'intégrant au gestionnaire de modules. Il s'appuie sur un système de journalisation interne robuste et un modèle de recherche pour une récupération efficace des données.

### 3.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun explicitement défini dans l'inventaire fourni. La logique d'affichage Front-Office pour les séparations virtuelles ou les redirections est probablement gérée via des hooks dans le fichier `mysplitproducts.php` principal ou via des overrides.
- **Contrôleurs d'administration Back-Office** :

  - `controllers/admin/AdminMySplitProductsController.php`
    - **Nom de la classe et classe parente :** `AdminMySplitProductsController` étend `ModuleAdminController`.
    - **Nom de l'onglet et entité gérée :** Ce contrôleur gère la fonctionnalité principale de séparation et d'annulation des produits. Il présente une vue en grille/gestion pour les produits qui ont été traités et permet aux administrateurs d'initier de nouvelles séparations ou de revenir sur des séparations existantes. Il interagit avec les classes `MspSplitEngine`, `MspLogger` et `MspRedirector`.
    - **Responsabilité :** Gère l'affichage de l'interface « Gérer les séparations », traite les requêtes AJAX pour la recherche de produits, initie le processus de séparation des produits et gère les opérations d'annulation. C'est le centre névralgique des tâches administratives du module.
  - `controllers/admin/index.php`
    - **Nom de la classe et classe parente :** N/A (pas un fichier de classe).
    - **Responsabilité :** Il s'agit d'un fichier `index.php` vide standard placé dans les sous-répertoires pour empêcher la liste des répertoires, améliorant ainsi la sécurité. Il ne contient aucune logique fonctionnelle pour le module.

### 3.3 Classes et modèles de base (`classes/`)

- `classes/index.php`
  - **Responsabilité :** Fichier `index.php` vide standard pour la sécurité, empêchant la liste des répertoires.
- `classes/MspAliasStore.php`
  - **Avec quelle table de base de données interagit-il :** Probablement `ps_mysplitproducts_alias` (table personnalisée) ou `ps_configuration` pour stocker les alias/redirections.
  - **S'il étend ObjectModel :** Peu probable d'étendre directement `ObjectModel` mais gère les données liées aux alias.
  - **Méthodes publiques clés et logique métier encapsulée :** Gère le mappage entre les ID de produit/combinaison originaux et leurs ID de produit séparés nouvellement créés. Crucial pour la fonctionnalité de redirection et d'annulation.
- `classes/MspCatalog.php`
  - **Avec quelle table de base de données interagit-il :** `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_image`, `ps_image_shop`, `ps_stock_available`, etc. (tables de produits PrestaShop de base).
  - **S'il étend ObjectModel :** Non, probablement une classe de service.
  - **Méthodes publiques clés et logique métier encapsulée :** Fournit des méthodes pour interroger et manipuler les données de produits PrestaShop de base. Utilisé par `MspSplitEngine` pour récupérer les détails des produits, les combinaisons et mettre à jour les statuts des produits.
- `classes/MspCombinationSearchProvider.php`
  - **Avec quelle table de base de données interagit-il :** `ps_product`, `ps_product_lang`, `ps_product_attribute`, `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang`.
  - **S'il étend ObjectModel :** Non, probablement une classe de service.
  - **Méthodes publiques clés et logique métier encapsulée :** Fournit des fonctionnalités pour rechercher des produits et leurs combinaisons, souvent utilisées pour la fonction de saisie semi-automatique dans le contrôleur d'administration.
- `classes/MspFinder.php`
  - **Avec quelle table de base de données interagit-il :** Diverses tables PrestaShop, selon le contexte de recherche.
  - **S'il étend ObjectModel :** Non, probablement une classe utilitaire/de service.
  - **Méthodes publiques clés et logique métier encapsulée :** Une classe de récupération de données à usage général, abstraite les requêtes de base de données courantes pour les produits, les attributs et d'autres entités nécessaires au module.
- `classes/MspLogger.php`
  - **Avec quelle table de base de données interagit-il :** Probablement `ps_mysplitproducts_log` (table personnalisée).
  - **S'il étend ObjectModel :** Oui, ou gère directement une table personnalisée.
  - **Méthodes publiques clés et logique métier encapsulée :** Enregistre toutes les opérations de séparation et d'annulation, y compris les horodatages, les produits affectés et le statut. Essentiel pour le tableau d'historique dans `AdminMySplitProductsController` et pour le débogage.
- `classes/MspNameBuilder.php`
  - **Avec quelle table de base de données interagit-il :** N/A (logique pure).
  - **S'il étend ObjectModel :** Non, une classe utilitaire.
  - **Méthodes publiques clés et logique métier encapsulée :** Implémente la logique de génération de nouveaux noms de produits et d'URL conviviales basés sur les modèles configurés (`MSP_NAME_BUILDER_TEMPLATE`, `MSP_URL_BUILDER_TEMPLATE`) et les données d'attributs.
- `classes/MspProductCloner.php`
  - **Avec quelle table de base de données interagit-il :** `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_image`, `ps_image_shop`, `ps_stock_available`, etc.
  - **S'il étend ObjectModel :** Non, une classe de service.
  - **Méthodes publiques clés et logique métier encapsulée :** La classe principale responsable de la duplication d'un produit et de ses données associées (images, stock, catégories, caractéristiques, etc.) pour créer un nouveau produit distinct pour une combinaison spécifique. Elle gère le processus complexe de copie de données entre plusieurs tables PrestaShop.
- `classes/MspRedirector.php`
  - **Avec quelle table de base de données interagit-il :** `ps_mysplitproducts_redirect` (table personnalisée) ou `ps_url_rewrite` (PrestaShop de base).
  - **S'il étend ObjectModel :** Non, une classe de service.
  - **Méthodes publiques clés et logique métier encapsulée :** Gère la création et la suppression des redirections 301 des URL de produit/combinaison originales vers les nouvelles URL de produit séparées. S'intègre au système de réécriture d'URL de PrestaShop ou implémente sa propre logique de redirection.
- `classes/MspSplitEngine.php`
  - **Avec quelle table de base de données interagit-il :** Orchestre les interactions avec `MspCatalog`, `MspProductCloner`, `MspNameBuilder`, `MspRedirector`, `MspLogger`.
  - **S'il étend ObjectModel :** Non, la classe de service orchestratrice principale.
  - **Méthodes publiques clés et logique métier encapsulée :** La classe centrale qui coordonne l'ensemble du processus de séparation. Elle prend un ID de produit, récupère ses combinaisons, utilise `MspNameBuilder` pour générer de nouveaux détails, `MspProductCloner` pour créer de nouveaux produits, `MspRedirector` pour les URL et `MspLogger` pour enregistrer l'opération. Gère également la logique d'annulation.

### 3.4 Actifs JavaScript (`views/js/`)

- `lib/searchTool/views/js/autocomplete.js`
  - **Portée :** Back-office.
  - **Quels écouteurs d'événements il lie :** Événements d'entrée sur les champs de recherche.
  - **Quelles manipulations DOM, popups modales, animations ou appels de SDK tiers externes il exécute :** Fournit une fonctionnalité de saisie semi-automatique pour les champs de recherche de produits dans l'interface d'administration, utilisant probablement des appels AJAX à `AdminMySplitProductsController` pour récupérer des suggestions de produits.
- `views/js/admin.js`
  - **Portée :** Back-office.
  - **Quels écouteurs d'événements il lie :** Événements de clic sur les boutons (par exemple, « Séparer le produit », « Annuler »), soumissions de formulaires.
  - **Quelles manipulations DOM, popups modales, animations ou appels de SDK tiers externes il exécute :** Gère les éléments interactifs du tableau de bord `AdminMySplitProductsController`, y compris l'initiation des actions de séparation/annulation, la mise à jour du tableau d'historique et l'affichage des indicateurs de chargement ou des messages de succès/erreur.
- `views/js/configure.js`
  - **Portée :** Back-office.
  - **Quels écouteurs d'événements il lie :** Événements de changement sur les champs de configuration, soumissions de formulaires.
  - **Quelles manipulations DOM, popups modales, animations ou appels de SDK tiers externes il exécute :** Gère le formulaire de configuration principal du module. Peut inclure une logique pour afficher/masquer des champs en fonction d'autres sélections (par exemple, mode de séparation), la validation du formulaire et la sauvegarde AJAX des paramètres de configuration.
- `views/js/listing.js`
  - **Portée :** Front-office (pour le mode de séparation virtuelle).
  - **Quels écouteurs d'événements il lie :** Potentiellement des événements `prestashop.on` pour les mises à jour de la liste de produits, DOM ready.
  - **Quelles manipulations DOM, popups modales, animations ou appels de SDK tiers externes il exécute :** Si le mode de « séparation virtuelle » est actif, ce script modifierait dynamiquement les listes de produits sur les pages de catégories, de recherche et autres pour afficher des tuiles de combinaison individuelles. Cela pourrait impliquer le clonage d'éléments de produit existants, la mise à jour de leur contenu (nom, image, prix) et le re-rendu de parties de la grille de produits.

### 3.5 Feuilles de style CSS (`views/css/`)

- `lib/searchTool/views/css/autocomplete.css`
  - **Portée :** Style du formulaire d'administration Back-office.
  - **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :** Styles pour la liste déroulante de saisie semi-automatique, les champs de saisie de recherche et les listes de suggestions dans le panneau d'administration.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer dans leur thème :** `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected`.
- `views/css/admin.css`
  - **Portée :** Style du formulaire d'administration Back-office.
  - **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :** Style général pour les pages de configuration du module et le tableau de bord « Gérer les séparations », y compris les tableaux, les boutons, les éléments de formulaire et les indicateurs de statut.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer dans leur thème :** `.mysplitproducts-config`, `.mysplitproducts-dashboard`, `.mysplitproducts-table`, `.mysplitproducts-status-success`, `.mysplitproducts-status-error`.

### 3.6 Structure des modèles Smarty (`views/templates/`)

- **Modèles de hook (`views/templates/hook/`)** : Aucun explicitement listé, mais le module pourrait utiliser des hooks pour l'affichage front-office en mode de séparation virtuelle (par exemple, `displayProductList`, `displayProductExtraContent`) qui seraient gérés par le fichier `mysplitproducts.php` principal.
- **Modèles d'administration (`views/templates/admin/`)** :
  - `views/templates/admin/configure_shell.tpl`
    - **Objectif :** Ce modèle sert probablement d'enveloppe principale ou de shell pour la page de configuration du module, y compris les paramètres généraux et éventuellement des onglets ou des sections pour d'autres paramètres. Il fournit la mise en page globale pour `getContent()`.
  - `views/templates/admin/dashboard.tpl`
    - **Objectif :** Ce modèle rend le tableau de bord « Gérer les séparations », y compris le champ de recherche de produits, le bouton « Séparer le produit » et le tableau d'historique des opérations de séparation. C'est la vue pour `AdminMySplitProductsController`.
- **Modèles Front-office (`views/templates/front/`)** : Aucun explicitement listé. Le rendu Front-office pour les séparations virtuelles impliquerait probablement la modification des modèles de thème existants via des hooks ou des overrides, ou l'injection dynamique de contenu via JavaScript (`listing.js`).

### 3.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - `ps_mysplitproducts_log` : Stocke un historique de toutes les opérations de séparation et d'annulation, y compris `id_product_original`, `id_product_split`, `action` (séparation/annulation), `date_add`, `status`.
  - `ps_mysplitproducts_redirect` : Stocke les mappages de redirection 301 des anciennes URL vers les nouvelles URL de produits séparés, y compris `old_url`, `new_url`, `id_product_original`, `id_product_split`.
  - `ps_mysplitproducts_alias` : Stocke les mappages entre les ID de produit/combinaison originaux et les nouveaux ID de produit séparés, cruciaux pour les recherches internes et les annulations.
  - Enregistrements de configuration stockés dans `ps_configuration` :
    - `MSP_MODE` : (int) 0 pour virtuel, 1 pour séparation réelle.
    - `MSP_ACTIVE_ONLY` : (bool) Ne séparer que les produits actifs.
    - `MSP_SOURCE_ACTION` : (int) Action pour le produit source (désactiver, garder actif, supprimer).
    - `MSP_IMAGE_COPY` : (bool) Copier les images vers les nouveaux produits.
    - `MSP_MIN_COMBINATIONS` : (int) Nombre minimum de combinaisons pour la séparation.
    - `MSP_NAME_BUILDER_TEMPLATE` : (string) Modèle pour les noms des nouveaux produits.
    - `MSP_URL_BUILDER_TEMPLATE` : (string) Modèle pour les URL des nouveaux produits.
    - `MSP_SEPARATOR_MULTIPLE_ATTRIBUTES` : (string) Séparateur pour les attributs multiples.
    - `MSP_REDIRECT_OLD_URLS` : (bool) Activer les redirections 301.
    - `MSP_CLEAR_CACHE_AFTER_SPLIT` : (bool) Vider le cache automatiquement.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Potentiellement injecte du CSS/JS pour la séparation virtuelle front-office, ou des balises meta pour le référencement. |
| `displayBackOfficeHeader` | Dans la section `<head>` de chaque page du Back Office. | Injecte du CSS/JS pour les pages d'administration du module (`admin.css`, `admin.js`, `autocomplete.css`, `autocomplete.js`). |
| `actionProductUpdate` | Après la mise à jour d'un produit. | Potentiellement déclenche une réévaluation pour la séparation ou des mises à jour liées aux produits séparés. |
| `actionProductDelete` | Après la suppression d'un produit. | Gère le nettoyage des produits séparés ou des redirections si le produit original est supprimé. |
| `actionProductSave` | Avant ou après la sauvegarde d'un produit. | Intercepte les sauvegardes de produits pour gérer les produits séparés ou les données associées. |
| `actionObjectProductAddAfter` | Après l'ajout d'un nouveau produit. | Potentiellement déclenche la séparation pour les produits nouvellement ajoutés si configuré. |
| `actionObjectProductUpdateAfter` | Après la mise à jour d'un produit. | Met à jour les produits séparés ou les redirections associées. |
| `actionObjectProductDeleteAfter` | Après la suppression d'un produit. | Nettoie les produits séparés et les redirections associées. |
| `displayProductList` | Lorsqu'une liste de produits est rendue (catégorie, recherche, etc.). | **Crucial pour le mode de séparation virtuelle.** Modifie la liste de produits pour afficher des tuiles de combinaison individuelles. |
| `displayProductExtraContent` | Sur la page produit, sous le contenu principal. | Pourrait être utilisé pour afficher des liens vers d'autres combinaisons ou un message sur les produits séparés. |
| `displayAdminProductsExtra` | Sur la page d'édition de produit dans le Back Office. | Ajoute un onglet ou une section personnalisée à la page d'édition de produit pour gérer les séparations liées à ce produit spécifique. |
| `actionAdminProductsListingResultsModifier` | Modifie les résultats de la liste de produits dans le Back Office. | Ajuste la liste de produits pour afficher/masquer les produits originaux ou mettre en évidence les produits séparés. |
| `actionFrontControllerSetMedia` | Avant qu'un contrôleur frontal ne rende son modèle. | Enregistre le JavaScript (`listing.js`) et le CSS front-office pour le mode de séparation virtuelle. |
| `moduleRoutes` | Lors de l'initialisation du routage d'URL. | Enregistre des routes personnalisées pour les produits séparés ou les redirections. |

## 4. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et un support complet, veuillez vous référer à votre compte client sur MyPresta.eu.

- **Mises à jour du module :** Connectez-vous à votre compte sur [MyPresta.eu Order History & Downloads](https://mypresta.eu/my-account/orders/) pour télécharger la version la plus récente de « Séparer les combinaisons en produits distincts ».
- **Support technique :** Si vous rencontrez des problèmes ou avez des questions qui ne sont pas couvertes dans ce guide, veuillez ouvrir un ticket de support via votre compte client MyPresta.eu. Notre équipe d'experts est prête à vous aider.
