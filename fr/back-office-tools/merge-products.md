---
title: "Fusionner des produits - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Fusionner des produits par MyPresta.eu."
sidebar:
  label: "Fusionner des produits - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Merge Products sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/merge-products.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/merge-products/)
>
> ---


# Fusionner des produits

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

Le module Fusionner des produits offre un écran d'administration dédié pour gérer le processus de fusion, accessible depuis votre back office PrestaShop.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Lorsque vous cliquez pour la première fois sur « Configurer » après l'installation, vous accédez à une page de type tableau de bord. Cette page sert principalement de point d'entrée à l'outil de fusion principal.

- **Ce que fait cet écran :** Cette page de configuration initiale fournit un bref aperçu et un lien direct vers l'outil principal « Fusionner des produits ». Elle ne contient pas de paramètres spécifiques en soi, mais vous guide vers l'endroit où la fusion réelle a lieu.
- **Effet de la modification de ce paramètre :** Il n'y a pas de paramètres directs à modifier sur cet écran initial.
- **Valeur recommandée :** N/A
- **Scénario / exemple de marchand :** C'est votre point de départ. À partir de là, vous cliquerez sur un bouton ou un lien pour accéder à la fonctionnalité principale du module.

### 2.2 Écran d'administration dédié : Outil de fusion des produits (Back Office > Catalogue > Fusionner des produits)

C'est l'interface principale où vous effectuerez toutes les opérations de fusion de produits. Vous pouvez la trouver en naviguant vers **Catalogue > Fusionner des produits** dans le menu de votre back office PrestaShop.

Cet écran est divisé en plusieurs sections pour vous guider tout au long du processus de fusion :

#### Étape 1 : Sélectionner le produit maître

- **Ce que fait cette section :** Ici, vous définissez le produit « maître ». C'est le produit dans lequel tous les autres produits « source » sélectionnés seront fusionnés, devenant ses combinaisons.
- **Champ de saisie : « Rechercher un produit »**
  - **Ce que fait ce paramètre :** Vous permet de rechercher un produit existant dans votre catalogue pour le désigner comme produit maître. Vous pouvez rechercher par nom de produit, ID, EAN ou référence.
  - **Effet de la modification de ce paramètre :** Au fur et à mesure que vous tapez, une liste de saisie semi-automatique apparaît. La sélection d'un produit remplit la zone « Produit maître » avec ses détails. Ce produit sera la base des nouvelles combinaisons.
  - **Valeur recommandée :** Choisissez le produit qui représente le mieux la liste consolidée. Par exemple, si vous fusionnez « T-shirt rouge S », « T-shirt rouge M », « T-shirt rouge L » en un seul, vous pourriez choisir « T-shirt rouge S » comme maître, et les autres deviendraient ses combinaisons.
  - **Scénario / exemple de marchand :** Vous avez « iPhone 13 (Neuf) » et « iPhone 13 (Reconditionné) » comme produits séparés. Vous recherchez et sélectionnez « iPhone 13 (Neuf) » comme produit maître.

#### Étape 2 : Sélectionner les produits source

- **Ce que fait cette section :** Ici, vous sélectionnez les produits qui seront convertis en combinaisons et ajoutés au produit maître.
- **Champ de saisie : « Rechercher des produits à fusionner »**
  - **Ce que fait ce paramètre :** Similaire à la recherche de produit maître, ce champ vous permet de trouver et de sélectionner plusieurs produits qui deviendront des combinaisons.
  - **Effet de la modification de ce paramètre :** Chaque produit sélectionné est ajouté à une liste ci-dessous. Ce sont les produits dont les données (prix, stock, attributs) seront transférées au produit maître en tant que nouvelles combinaisons.
  - **Valeur recommandée :** Sélectionnez tous les produits qui sont des variations de votre produit maître choisi et qui doivent être consolidés.
  - **Scénario / exemple de marchand :** En suivant l'exemple de l'iPhone, vous recherchez et sélectionnez « iPhone 13 (Reconditionné) » ici. Si vous aviez également « iPhone 13 (Occasion - Grade A) », vous le sélectionneriez également.

#### Étape 3 : Configurer les options de fusion

Cette section contient des paramètres critiques qui contrôlent la manière dont l'opération de fusion est effectuée.

- **Option : Mode de fusion**

  - **Ce que fait ce paramètre :** Détermine la manière dont les attributs des produits source sont gérés lors de la création de combinaisons.
  - **Effet de la modification de ce paramètre :**
    - *Ajouter un nouveau groupe d'attributs :* Le module créera un nouveau groupe d'attributs (par exemple, « Condition ») et un attribut pour chaque produit source (par exemple, « Neuf », « Reconditionné », « Occasion »). C'est idéal lorsque les produits source diffèrent par une caractéristique non déjà couverte par des attributs existants.
    - *Utiliser un groupe d'attributs existant :* Si vos produits source partagent déjà un groupe d'attributs commun (par exemple, « Taille » ou « Couleur ») et que vous souhaitez les fusionner en fonction de celui-ci, vous pouvez le sélectionner. C'est moins courant pour la fusion de produits entièrement séparés, mais utile pour consolider des variations au sein d'une structure d'attributs existante.
  - **Valeur recommandée :** **« Ajouter un nouveau groupe d'attributs »** est généralement recommandé pour la fusion de produits distincts, car il offre un moyen clair de différencier les nouvelles combinaisons.
  - **Scénario / exemple de marchand :** Vous fusionnez « Produit X - Neuf » et « Produit X - Occasion ». La sélection de « Ajouter un nouveau groupe d'attributs » créera un groupe d'attributs « Condition » avec les attributs « Neuf » et « Occasion » pour les combinaisons.
- **Champ de saisie : Nom du nouveau groupe d'attributs (visible uniquement si « Ajouter un nouveau groupe d'attributs » est sélectionné)**

  - **Ce que fait ce paramètre :** Spécifie le nom du nouveau groupe d'attributs qui sera créé pour différencier les combinaisons fusionnées.
  - **Effet de la modification de ce paramètre :** Ce nom apparaîtra sur votre page de produit (par exemple, « Condition », « Grade », « Version »).
  - **Valeur recommandée :** Un nom descriptif comme « Condition », « Statut », « Type » ou « Grade ».
  - **Scénario / exemple de marchand :** Si vous fusionnez des produits « Neuf » et « Occasion », vous pouvez saisir « Condition ».
- **Option : Règle du produit maître**

  - **Ce que fait ce paramètre :** Définit la manière dont le produit maître lui-même est traité pendant la fusion.
  - **Effet de la modification de ce paramètre :**
    - *Conserver comme produit maître :* Le produit maître reste le produit par défaut, et les produits source deviennent ses combinaisons. Ses combinaisons existantes (le cas échéant) sont préservées.
    - *Convertir en combinaison :* Le produit maître lui-même est également converti en combinaison sous sa propre fiche. C'est utile si vous souhaitez que toutes les variations, y compris le maître original, soient sélectionnables via le nouveau groupe d'attributs.
  - **Valeur recommandée :** **« Conserver comme produit maître »** est souvent suffisant. Choisissez « Convertir en combinaison » si vous souhaitez que l'état original du produit maître soit explicitement sélectionnable comme combinaison.
  - **Scénario / exemple de marchand :** Si « iPhone 13 (Neuf) » est votre maître, et que vous y fusionnez « iPhone 13 (Reconditionné) », « Conserver comme produit maître » signifie que « iPhone 13 (Neuf) » est le produit par défaut. Si vous choisissez « Convertir en combinaison », alors « Neuf » deviendrait une option sélectionnable aux côtés de « Reconditionné ».
- **Option : Action sur le produit source**

  - **Ce que fait ce paramètre :** Détermine ce qui arrive aux produits source originaux après qu'ils ont été fusionnés dans le produit maître en tant que combinaisons.
  - **Effet de la modification de ce paramètre :**
    - *Désactiver :* Les pages de produits source originales seront désactivées, les rendant inaccessibles aux clients. C'est généralement l'option la plus sûre.
    - *Supprimer :* Les pages de produits source originales seront définitivement supprimées de votre catalogue. À utiliser avec prudence, car cette action est irréversible.
    - *Ne rien faire :* Les pages de produits source originales restent actives. Ce n'est généralement pas recommandé car cela peut entraîner du contenu dupliqué et de la confusion.
  - **Valeur recommandée :** **« Désactiver »** est le choix le plus sûr et le plus courant. Si vous êtes confiant dans votre fusion et vos redirections, « Supprimer » peut nettoyer votre catalogue, mais assurez-vous d'avoir des sauvegardes.
  - **Scénario / exemple de marchand :** Après avoir fusionné « iPhone 13 (Reconditionné) » dans « iPhone 13 (Neuf) », vous choisiriez généralement « Désactiver » pour empêcher les clients de trouver l'ancienne page de produit « Reconditionné ».
- **Option : Créer des redirections 301**

  - **Ce que fait ce paramètre :** Si activé, le module créera des redirections permanentes (301) des anciennes URL des produits source vers la nouvelle URL du produit maître.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Tout client ou moteur de recherche essayant d'accéder à une ancienne URL de produit source sera automatiquement envoyé vers la page du produit maître. C'est crucial pour le SEO, la préservation de l'équité des liens et la prévention des liens brisés.
    - *Désactivé :* Les anciennes URL de produits source entraîneront une erreur « page non trouvée » si le produit source est désactivé ou supprimé.
  - **Valeur recommandée :** **OUI (Activé)**. Ceci est fortement recommandé pour le SEO et l'expérience utilisateur.
  - **Scénario / exemple de marchand :** Un client a mis en favori l'ancienne page « iPhone 13 (Reconditionné) ». Avec les redirections activées, il atterrira automatiquement sur la page maître « iPhone 13 ».
- **Option : Taille du lot**

  - **Ce que fait ce paramètre :** Contrôle le nombre de produits traités en un seul lot pendant l'opération de fusion. Il s'agit d'un paramètre technique pour éviter les délais d'attente du serveur pour les fusions importantes.
  - **Effet de la modification de ce paramètre :** Un nombre plus faible réduit la charge du serveur mais rend le processus plus long. Un nombre plus élevé l'accélère mais peut causer des problèmes sur un hébergement moins puissant.
  - **Valeur recommandée :** Laissez par défaut, sauf si vous rencontrez des délais d'attente. Si c'est le cas, essayez de le réduire.
  - **Scénario / exemple de marchand :** Si vous fusionnez des centaines de produits et que le processus échoue, la réduction de la taille du lot peut aider.
- **Option : Seulement les produits actifs**

  - **Ce que fait ce paramètre :** Si activé, seuls les produits source actifs seront pris en compte pour la fusion.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Empêche la fusion de produits inactifs, ce qui peut simplifier le processus et éviter de créer des combinaisons pour des produits que vous n'avez pas l'intention de vendre.
    - *Désactivé :* Tous les produits, actifs ou inactifs, peuvent être fusionnés.
  - **Valeur recommandée :** **OUI (Activé)**, sauf si vous avez spécifiquement besoin de fusionner des produits inactifs.
  - **Scénario / exemple de marchand :** Vous ne souhaitez fusionner que les produits actuellement visibles et achetables sur votre boutique.
- **Option : Exclure les packs**

  - **Ce que fait ce paramètre :** Si activé, les produits configurés comme des « packs » (lots d'autres produits) seront exclus de la sélection des produits source.
  - **Effet de la modification de ce paramètre :** Empêche la fusion accidentelle de packs de produits, qui ont des relations complexes et pourraient ne pas se comporter comme prévu lorsqu'ils sont convertis en combinaisons.
  - **Valeur recommandée :** **OUI (Activé)**. La fusion de packs peut entraîner un comportement inattendu.
  - **Scénario / exemple de marchand :** Vous avez un pack « Kit de démarrage ». Vous ne voulez pas qu'il soit fusionné comme une combinaison dans un autre produit.
- **Option : Exclure les produits virtuels**

  - **Ce que fait ce paramètre :** Si activé, les produits virtuels (par exemple, fichiers téléchargeables, services) seront exclus de la sélection des produits source.
  - **Effet de la modification de ce paramètre :** Empêche la fusion accidentelle de produits virtuels, qui n'ont généralement pas d'attributs physiques ou de stock et pourraient ne pas convenir à la conversion en combinaison.
  - **Valeur recommandée :** **OUI (Activé)**. Les produits virtuels ne sont généralement pas de bons candidats pour la fusion en combinaisons de produits physiques.
  - **Scénario / exemple de marchand :** Vous vendez un e-book téléchargeable. Vous ne voulez pas qu'il soit fusionné comme une combinaison dans un produit livre physique.
- **Option : Taille minimale du groupe**

  - **Ce que fait ce paramètre :** Définit un nombre minimum de produits source requis pour former un nouveau groupe d'attributs.
  - **Effet de la modification de ce paramètre :** C'est une mesure de sécurité. Si vous sélectionnez « Ajouter un nouveau groupe d'attributs » mais ne fusionnez qu'un seul produit source, ce paramètre peut empêcher la création d'un groupe d'attributs inutile avec une seule option.
  - **Valeur recommandée :** Laissez par défaut (généralement 2).
  - **Scénario / exemple de marchand :** Si vous sélectionnez accidentellement un seul produit source, cela peut empêcher le module de créer un groupe d'attributs avec une seule option, ce qui est redondant.
- **Option : Groupe d'attributs à utiliser (visible uniquement si « Utiliser un groupe d'attributs existant » est sélectionné)**

  - **Ce que fait ce paramètre :** Vous permet de sélectionner un groupe d'attributs existant dans votre boutique pour catégoriser les nouvelles combinaisons.
  - **Effet de la modification de ce paramètre :** Le module tentera de mapper les produits source aux attributs de ce groupe choisi. Cela nécessite une planification minutieuse pour s'assurer que vos produits source s'intègrent logiquement dans la structure d'attributs existante.
  - **Valeur recommandée :** N'utilisez que si vous avez un scénario très spécifique où les produits source sont déjà des variations d'un attribut existant. Sinon, « Ajouter un nouveau groupe d'attributs » est plus sûr.
  - **Scénario / exemple de marchand :** Vous avez les produits « Chemise - Bleue » et « Chemise - Rouge » comme produits séparés, et vous souhaitez les fusionner dans un produit maître « Chemise », en utilisant le groupe d'attributs « Couleur » existant.

#### Étape 4 : Vérifier et fusionner

- **Bouton : « Fusionner les produits »**
  - **Ce que fait ce bouton :** Lance le processus de fusion réel en fonction de vos sélections et configurations.
  - **Effet du clic :** Le module traitera les produits source sélectionnés, les convertira en combinaisons, les attribuera au produit maître, mettra à jour les stocks et les prix, et effectuera les redirections/désactivations comme configuré. Une barre de progression ou un message de succès sera affiché.
  - **Action recommandée :** Examinez attentivement toutes vos sélections avant de cliquer. Assurez-vous d'avoir une sauvegarde de votre boutique.
  - **Scénario / exemple de marchand :** Après avoir sélectionné « iPhone 13 (Neuf) » comme maître, « iPhone 13 (Reconditionné) » comme source, défini « Condition » comme nouveau groupe d'attributs et activé les redirections 301, vous cliquez sur « Fusionner les produits » pour exécuter la consolidation.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Outil de fusion des produits** | **Recherche de produit maître** | N/A | Sélectionne le produit principal auquel les autres seront fusionnés. |
|  | **Recherche de produits source** | N/A | Sélectionne les produits à convertir en combinaisons sous le maître. |
|  | **Mode de fusion** | Ajouter un nouveau groupe d'attributs | Détermine si un nouveau groupe d'attributs est créé ou si un groupe existant est utilisé pour les combinaisons. |
|  | **Nom du nouveau groupe d'attributs** | Nom descriptif (par exemple, « Condition ») | Nom du groupe d'attributs créé pour différencier les combinaisons fusionnées. |
|  | **Règle du produit maître** | Conserver comme produit maître | Définit si le produit maître lui-même devient une combinaison ou reste le produit par défaut. |
|  | **Action sur le produit source** | Désactiver | Ce qui arrive aux pages de produits source originales après la fusion (Désactiver, Supprimer, Ne rien faire). |
|  | **Créer des redirections 301** | OUI | Crée des redirections permanentes des anciennes URL source vers la nouvelle URL maître. Crucial pour le SEO. |
|  | **Taille du lot** | Par défaut (par exemple, 10) | Nombre de produits traités par lot. Ajuster pour les performances du serveur. |
|  | **Seulement les produits actifs** | OUI | Limite la sélection des produits source aux seuls produits actifs. |
|  | **Exclure les packs** | OUI | Empêche la sélection des packs de produits comme produits source. |
|  | **Exclure les produits virtuels** | OUI | Empêche la sélection des produits virtuels comme produits source. |
|  | **Taille minimale du groupe** | Par défaut (par exemple, 2) | Nombre minimum de produits source pour créer un nouveau groupe d'attributs. |
|  | **Groupe d'attributs à utiliser** | N/A (uniquement si mode « Utiliser existant… ») | Sélectionne un groupe d'attributs existant pour le mappage des combinaisons. |
|  | **Bouton Fusionner les produits** | Cliquer après vérification | Exécute l'opération de fusion. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q1 : Après la fusion, je ne vois pas les nouvelles combinaisons sur ma page de produit.**
R1 : Tout d'abord, videz votre cache PrestaShop. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » en haut à droite. Si le problème persiste, vérifiez le produit maître dans votre Back Office pour vous assurer que les combinaisons ont été créées correctement et sont actives. Vérifiez également que le groupe d'attributs créé par le module est activé et associé au produit maître.

**Q2 : Mes anciennes URL de produits affichent des erreurs « Page non trouvée ».**
R2 : Cela signifie généralement que les redirections 301 n'ont pas été créées ou ne fonctionnent pas.
1. Retournez à l'outil « Fusionner des produits » (**Catalogue > Fusionner des produits**).
2. Vérifiez si l'option « Créer des redirections 301 » était activée pendant la fusion. Si ce n'est pas le cas, vous devrez configurer manuellement les redirections ou refusionner (après avoir restauré une sauvegarde si vous avez supprimé les produits source).
3. Assurez-vous que le fichier `.htaccess` de votre serveur est correctement configuré pour gérer les URL conviviales et les redirections de PrestaShop. Parfois, les configurations de serveur peuvent interférer.

**Q3 : Le module semble se bloquer ou expirer pendant le processus de fusion.**
R3 : Cela peut arriver avec un grand nombre de produits ou sur des serveurs avec des ressources limitées.
1. Essayez de réduire le paramètre **« Taille du lot »** dans la section « Configurer les options de fusion » du module. Une taille de lot plus petite (par exemple, 5 ou 10) traitera moins de produits à la fois, réduisant la charge du serveur.
2. Vérifiez les paramètres `max_execution_time` et `memory_limit` de PHP de votre serveur. Vous devrez peut-être augmenter temporairement ces valeurs (contactez votre hébergeur si vous n'êtes pas sûr).

**Q4 : Puis-je annuler une opération de fusion ?**
R4 : Le module n'a pas de bouton « annuler ». C'est pourquoi les **sauvegardes sont absolument critiques**. Si vous devez revenir en arrière, vous devez restaurer votre boutique à partir d'une sauvegarde effectuée *avant* la fusion. Si vous n'avez fait que désactiver les produits source et ne les avez pas supprimés, vous pourriez les réactiver manuellement et supprimer les combinaisons nouvellement créées du produit maître, mais c'est un processus manuel complexe.

**Q5 : Que faire si mon thème personnalisé n'affiche pas correctement le nouveau groupe d'attributs ?**
R5 : Le module crée des groupes d'attributs et des combinaisons PrestaShop standard. Si votre thème ne les affiche pas correctement, il s'agit probablement d'un problème de CSS ou de modèle Smarty dans votre thème.
1. Vérifiez si les thèmes PrestaShop par défaut (par exemple, Classic) affichent correctement les combinaisons. Si c'est le cas, le problème vient de votre thème personnalisé.
2. Vous devrez peut-être consulter un développeur web pour ajuster le fichier `product.tpl` de votre thème ou le CSS associé afin de rendre correctement les nouveaux sélecteurs d'attributs.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Vue d'ensemble de l'architecture

Le module `Merge Products` suit un modèle MVC PrestaShop standard pour ses composants Back Office. Il s'appuie sur l'`ObjectModel` de PrestaShop pour la manipulation des données (bien qu'il interagisse principalement avec les objets `Product` et `Combination` directement plutôt qu'avec des modèles spécifiques au module). La logique principale pour trouver, construire et fusionner les produits et leurs combinaisons est encapsulée dans des classes de service dédiées. Le module utilise un contrôleur Admin personnalisé pour son interface principale, offrant une grille et un formulaire conviviaux pour le processus de fusion. Il implémente également un mécanisme de journalisation pour suivre les opérations de fusion.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. Le module est purement un outil d'administration Back-Office.
- **Contrôleurs Admin Back-Office** :

  - `controllers/admin/AdminMyMergeProductsController.php`

    - **Nom de la classe** : `AdminMyMergeProductsController`
    - **Classe parente** : `ModuleAdminController`
    - **Responsabilité** : C'est le contrôleur principal de l'interface administrative du module. Il gère l'affichage de l'outil de fusion, y compris la recherche de produits (saisie semi-automatique), les options de configuration et le lancement du processus de fusion. Il orchestre les appels aux classes de service principales (`MmpFinder`, `MmpMergeEngine`, `MmpLogger`, `MmpRedirector`) pour effectuer la fusion réelle. Il gère la soumission du formulaire et affiche les retours à l'utilisateur.
    - **Nom de l'onglet** : « Fusionner des produits » (sous le menu Catalogue)
    - **Entité gérée** : Produits et leurs combinaisons, attributs.
  - `controllers/admin/index.php`

    - **Nom de la classe** : N/A (fichier vide)
    - **Classe parente** : N/A
    - **Responsabilité** : Il s'agit d'un fichier `index.php` vide standard, souvent placé dans les répertoires pour empêcher la liste des répertoires sur les serveurs web. Il n'a aucun rôle fonctionnel dans la logique du module.

### 4.3 Classes et modèles principaux (`classes/`)

- `classes/index.php`

  - **Responsabilité** : Fichier `index.php` vide standard pour empêcher la liste des répertoires.
- `classes/MmpCombinationBuilder.php`

  - **Nom de la classe** : `MmpCombinationBuilder`
  - **Classe parente** : Aucune (classe de service autonome)
  - **Responsabilité** : Cette classe est responsable de la logique complexe de création de nouvelles combinaisons de produits basées sur les produits source. Elle gère :
    - Le mappage des données des produits source (prix, quantité, EAN, référence) aux nouvelles combinaisons.
    - La création de nouveaux attributs et groupes d'attributs si `MMP_MERGE_MODE` est défini sur « Ajouter un nouveau groupe d'attributs ».
    - L'attribution des attributs existants aux nouvelles combinaisons.
    - La gestion des images pour les combinaisons.
    - L'assurance que les règles de stock et de prix sont correctement appliquées aux nouvelles combinaisons.
- `classes/MmpFinder.php`

  - **Nom de la classe** : `MmpFinder`
  - **Classe parente** : Aucune (classe de service autonome)
  - **Responsabilité** : Fournit des méthodes pour rechercher et récupérer des produits en fonction de divers critères (ID, nom, EAN, référence). Cette classe est utilisée par `AdminMyMergeProductsController` pour la fonctionnalité de recherche par saisie semi-automatique des produits maîtres et source. Elle filtre également les produits en fonction de la configuration du module (par exemple, `MMP_ACTIVE_ONLY`, `MMP_EXCLUDE_PACKS`, `MMP_EXCLUDE_VIRTUAL`).
- `classes/MmpLogger.php`

  - **Nom de la classe** : `MmpLogger`
  - **Classe parente** : Aucune (classe de service autonome)
  - **Responsabilité** : Gère la journalisation des opérations de fusion. Il enregistre les détails de chaque fusion, y compris le produit maître, les produits source et les paramètres de configuration utilisés. Ceci est crucial pour le débogage et l'audit. Il stocke probablement les journaux dans une table de base de données personnalisée ou un fichier.
- `classes/MmpMergeEngine.php`

  - **Nom de la classe** : `MmpMergeEngine`
  - **Classe parente** : Aucune (classe de service autonome)
  - **Responsabilité** : C'est l'orchestrateur central du processus de fusion. Il prend le produit maître et les produits source, ainsi que les paramètres de configuration, et coordonne les actions :
    - Appelle `MmpCombinationBuilder` pour créer des combinaisons.
    - Met à jour le produit maître.
    - Gère l'`MMP_SOURCE_ACTION` (désactiver ou supprimer les produits source).
    - Gère le traitement par lots (`MMP_BATCH_SIZE`).
    - Interagit avec `MmpRedirector` pour les redirections 301.
    - Utilise `MmpLogger` pour enregistrer l'opération.
- `classes/MmpRedirector.php`

  - **Nom de la classe** : `MmpRedirector`
  - **Classe parente** : Aucune (classe de service autonome)
  - **Responsabilité** : Gère la création des redirections 301. Lorsque `MMP_REDIRECT` est activé, cette classe crée des entrées dans la table `ps_product_redirect` de PrestaShop (ou un mécanisme similaire) pour rediriger les anciennes URL de produits source vers la nouvelle URL de produit maître.

### 4.4 Actifs JavaScript (`views/js/`)

- `lib/searchTool/views/js/autocomplete.js`

  - **Portée** : Back-office.
  - **Responsabilité** : Fournit la logique JavaScript pour les champs de recherche de produit à saisie semi-automatique utilisés dans `AdminMyMergeProductsController`. Il utilise probablement AJAX pour interroger `MmpFinder` afin d'obtenir des suggestions de produits au fur et à mesure que l'utilisateur tape, affichant les résultats dans une liste déroulante. Il gère la sélection et le remplissage des champs de produit respectifs.
- `views/js/admin.js`

  - **Portée** : Back-office.
  - **Responsabilité** : Contient les fonctionnalités JavaScript générales pour l'interface d'administration du module. Cela peut inclure :
    - L'affichage conditionnel des champs de configuration (par exemple, `Nom du nouveau groupe d'attributs` visible uniquement si « Ajouter un nouveau groupe d'attributs » est sélectionné).
    - La validation du formulaire.
    - Les appels AJAX pour lancer le processus de fusion et afficher la progression.
    - Les écouteurs d'événements pour les boutons et les changements de formulaire.

### 4.5 Feuilles de style CSS (`views/css/`)

- `lib/searchTool/views/css/autocomplete.css`

  - **Portée** : Style de l'administration Back-office.
  - **Responsabilité** : Style la liste déroulante de saisie semi-automatique et les champs de saisie de recherche, en veillant à ce qu'ils soient visuellement cohérents et conviviaux dans le Back Office de PrestaShop.
- `views/css/admin.css`

  - **Portée** : Style de l'administration Back-office.
  - **Responsabilité** : Fournit un style spécifique pour l'interface `AdminMyMergeProductsController`, y compris la mise en page des sections, le style des listes de produits et les améliorations visuelles générales pour la page de configuration du module.

### 4.6 Structure du modèle Smarty (`views/templates/`)

- `lib/searchTool/views/scripts.tpl`

  - **Portée** : Back-office.
  - **Responsabilité** : Ce modèle inclut probablement le JavaScript et le CSS nécessaires pour l'outil de recherche par saisie semi-automatique, garantissant qu'il est chargé sur les pages d'administration pertinentes. Il peut contenir des balises `script` et `link`.
- `views/templates/admin/configure_shell.tpl`

  - **Portée** : Administration Back-office.
  - **Responsabilité** : Ce modèle sert d'enveloppe ou de shell pour le contenu de configuration principal du module. Il peut inclure des éléments d'en-tête/pied de page communs, une navigation ou une structure de mise en page générale pour les pages d'administration du module. Il inclut probablement `dashboard.tpl`.
- `views/templates/admin/dashboard.tpl`

  - **Portée** : Administration Back-office.
  - **Responsabilité** : C'est le modèle principal pour la vue `AdminMyMergeProductsController`. Il rend l'interface complète de l'outil de fusion, y compris :
    - La zone de sélection du produit maître.
    - La zone de sélection des produits source.
    - Le formulaire des options de configuration de fusion (avec tous les paramètres comme `MMP_MERGE_MODE`, `MMP_REDIRECT`, etc.).
    - Le bouton « Fusionner les produits ».
    - Tous les messages d'état ou indicateurs de progression pendant la fusion.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de la base de données** :

  - Le module interagit principalement avec les tables principales existantes de PrestaShop :
    - `ps_product` : Pour récupérer les informations sur les produits et mettre à jour le statut des produits (actif/inactif).
    - `ps_product_attribute` : Pour créer et gérer les combinaisons de produits.
    - `ps_product_attribute_shop` : Pour les données de combinaison spécifiques à la boutique.
    - `ps_product_attribute_combination` : Lie les combinaisons aux attributs.
    - `ps_attribute_group`, `ps_attribute_group_lang`, `ps_attribute_group_shop` : Pour créer de nouveaux groupes d'attributs.
    - `ps_attribute`, `ps_attribute_lang`, `ps_attribute_shop` : Pour créer de nouveaux attributs.
    - `ps_stock_available` : Pour mettre à jour les quantités de stock pour les combinaisons.
    - `ps_product_lang` : Pour les noms et descriptions des produits.
    - `ps_product_shop` : Pour les données de produits spécifiques à la boutique.
    - `ps_url_rewrite` : Pour gérer les URL conviviales.
    - `ps_configuration` : Stocke les paramètres de configuration du module (par exemple, `MMP_MERGE_MODE`, `MMP_MASTER_RULE`, `MMP_SOURCE_ACTION`, `MMP_REDIRECT`, `MMP_BATCH_SIZE`, `MMP_ACTIVE_ONLY`, `MMP_EXCLUDE_PACKS`, `MMP_EXCLUDE_VIRTUAL`, `MMP_MIN_GROUP`, `MMP_ATTRIBUTE_GROUP`, `MMP_ATTRIBUTE_GROUP_NAME`).
  - Le module pourrait créer une table personnalisée pour journaliser les opérations de fusion (par exemple, `ps_mmp_log` ou similaire), bien que cela ne soit pas explicitement détaillé dans l'inventaire fourni. Si elle existe, elle stockerait les enregistrements de chaque événement de fusion.
  - Pour les redirections 301, il utilise probablement la table `ps_product_redirect` de PrestaShop (ou un mécanisme similaire si le module implémente son propre gestionnaire de redirection).
- **Table des hooks enregistrés** :
  Le module n'enregistre explicitement aucun hook front-office (comme `displayHeader`, `displayProductButtons`, etc.) car il s'agit d'un outil back-office. Son interaction principale avec le système de hooks de PrestaShop serait pour :

  - `actionAdminControllerSetMedia` : Pour charger ses fichiers CSS et JS spécifiques dans le Back Office.
  - `actionProductUpdate` / `actionProductAdd` / `actionProductDelete` : Bien que non explicitement listée, la logique interne du module pour modifier les produits pourrait déclencher ces hooks PrestaShop de base, que d'autres modules pourraient écouter.
  - `actionObjectProductAddAfter`, `actionObjectProductUpdateAfter`, `actionObjectProductDeleteAfter` : Hooks ObjectModel qui seraient déclenchés lorsque le module crée, met à jour ou supprime des objets `Product` ou `ProductAttribute`.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Fusionner des produits », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question que vous pourriez avoir concernant la fonctionnalité du module.
