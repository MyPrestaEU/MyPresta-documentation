---
title: "Assigner un transporteur aux produits en masse - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Assigner un transporteur aux produits en masse' par MyPresta.eu."
sidebar:
  label: "Assigner un transporteur aux produits en masse - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Assign carrier to products in bulk sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/assign-carrier-to-products-in-bulk.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/assign-carrier-to-products-in-bulk/)
>
> ---


# Assigner un transporteur aux produits en masse

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur inhabituelle n'est requise.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Assigner un transporteur aux produits en masse)

C'est l'interface principale où vous définirez vos tâches d'assignation de transporteur en masse. La page est conçue pour être intuitive, vous guidant à travers le processus de sélection des transporteurs, puis de spécification des produits à affecter.

**Options de configuration principales :**

1.  **Sélectionner les transporteurs :**

    -   **Ce que fait ce paramètre :** Cette section affiche une liste de tous les transporteurs actifs configurés dans votre boutique PrestaShop (trouvés sous **Livraison > Transporteurs**). Vous pouvez sélectionner un ou plusieurs transporteurs que vous souhaitez assigner à vos produits.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'un ou plusieurs transporteurs sont sélectionnés :* Les transporteurs choisis seront assignés aux produits que vous spécifiez dans les étapes suivantes. Cela signifie que ces transporteurs deviendront des options d'expédition disponibles pour ces produits lors du paiement.
        -   *Lorsqu'aucun transporteur n'est sélectionné :* Le module n'effectuera aucune assignation. Vous devez sélectionner au moins un transporteur pour continuer.
    -   **Valeur recommandée :** Sélectionnez tous les transporteurs qui devraient être disponibles pour les produits cibles.
    -   **Scénario / exemple de marchand :** Si vous souhaitez rendre « UPS Ground » et « FedEx Express » disponibles pour une nouvelle gamme d'électronique, vous les sélectionneriez tous les deux dans cette liste.
2.  **Sélectionner les produits auxquels assigner les transporteurs :**

    -   **Ce que fait ce paramètre :** Cette section cruciale vous permet de définir la portée des produits qui recevront les assignations de transporteurs sélectionnées. Vous disposez de trois options puissantes :
        -   **Par catégories :** Assigner des transporteurs à tous les produits d'une catégorie spécifique.
        -   **Par fabricants :** Assigner des transporteurs à tous les produits de fabricants spécifiques.
        -   **Par produits spécifiques :** Assigner des transporteurs à des produits individuels que vous sélectionnez.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque « Par catégories » est sélectionné :* Une liste des catégories de votre boutique apparaîtra. La sélection de catégories ici signifie que tous les produits appartenant à ces catégories auront les transporteurs choisis assignés.
        -   *Lorsque « Par fabricants » est sélectionné :* Une liste des fabricants de votre boutique apparaîtra. La sélection de fabricants ici signifie que tous les produits associés à ces fabricants auront les transporteurs choisis assignés.
        -   *Lorsque « Par produits spécifiques » est sélectionné :* Un champ de saisie avec une fonction d'autocomplétion apparaîtra. Vous pouvez taper des noms de produits, et le système suggérera des produits. Vous pouvez ajouter plusieurs produits spécifiques à la liste.
    -   **Valeur recommandée :** Choisissez la méthode qui regroupe le mieux vos produits cibles. Pour des changements généraux, les catégories ou les fabricants sont efficaces. Pour des ajustements précis, les produits spécifiques sont les meilleurs.
    -   **Scénario / exemple de marchand :**
        -   *Catégories :* Vous lancez une nouvelle catégorie « Articles fragiles ». Vous sélectionneriez cette catégorie et assigneriez un « Transporteur de marchandises fragiles » spécialisé à tous les produits qu'elle contient.
        -   *Fabricants :* Une nouvelle marque de vêtements arrive. Vous sélectionnez le fabricant et assignez votre « Transporteur de vêtements » standard à tous ses produits.
        -   *Produits spécifiques :* Vous avez trois produits uniques et surdimensionnés qui nécessitent un « Transporteur de fret ». Vous rechercheriez et ajouteriez ces trois produits individuellement.
3.  **Boutons d'action :**

    -   **Bouton « Assigner les transporteurs » :**
        -   **Ce que fait ce bouton :** Lance le processus d'assignation en masse. Après avoir cliqué, le module traitera vos sélections et mettra à jour les associations de transporteurs pour tous les produits spécifiés.
        -   **Effet de cliquer sur ce bouton :** Les transporteurs sélectionnés seront liés aux produits choisis. Un message de succès ou d'erreur sera généralement affiché.
        -   **Action recommandée :** Cliquez uniquement après avoir soigneusement examiné vos sélections de transporteurs et de produits.
        -   **Scénario / exemple de marchand :** Après avoir configuré vos transporteurs et groupes de produits, cliquer sur ce bouton exécute les changements dans votre boutique.
    -   **Bouton « Effacer toutes les assignations » (ou similaire) :**
        -   **Ce que fait ce bouton :** Cette option (si présente) supprimerait généralement *toutes* les assignations de transporteurs pour les produits sélectionnés, ou potentiellement pour tous les produits de la boutique, selon l'implémentation exacte du module.
        -   **Effet de cliquer sur ce bouton :** Les produits reviendraient à n'avoir aucun transporteur spécifique assigné, ou seulement des transporteurs par défaut, ce qui pourrait affecter la disponibilité de l'expédition.
        -   **Action recommandée :** Utilisez avec une extrême prudence et seulement si vous comprenez parfaitement les implications. C'est une action puissante qui peut perturber vos options d'expédition.
        -   **Scénario / exemple de marchand :** Vous réorganisez complètement votre stratégie d'expédition et devez réinitialiser tous les liens produit-transporteur avant de les réassigner.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 AdminMassCarrierCronController (Back Office > Paramètres avancés > Cron de transporteur en masse)

Cet écran permet de gérer les tâches cron liées au module, vous permettant de planifier et d'automatiser les tâches d'assignation de transporteur.

-   **Nom de l'écran et emplacement du menu :** Vous trouverez généralement un nouvel élément de menu sous **Paramètres avancés** (ou une section similaire, selon la version de PrestaShop) nommé quelque chose comme « Cron de transporteur en masse » ou « Planificateur d'assignation de transporteur ».
-   **Actions et paramètres disponibles :** Cet écran affichera probablement une grille (liste) de tâches planifiées. Pour chaque tâche, vous pourriez voir :
    -   **ID de tâche :** Identifiant unique.
    -   **Description :** Une brève explication de ce que fait la tâche (par exemple, « Assigner UPS à la catégorie X »).
    -   **Fréquence :** À quelle fréquence la tâche s'exécute (par exemple, quotidiennement, hebdomadairement, une fois).
    -   **Dernière exécution :** Horodatage de la dernière exécution.
    -   **Statut :** Si la tâche est active, en attente ou terminée.
    -   **Actions :** Boutons pour « Ajouter une nouvelle tâche », « Modifier », « Supprimer » ou « Exécuter maintenant ».
-   **Effet des changements :**
    -   *Ajouter une nouvelle tâche :* Vous permet de définir une nouvelle opération d'assignation de transporteur en masse à exécuter automatiquement à un intervalle spécifié. Ceci est utile pour les mises à jour récurrentes (par exemple, de nouvelles importations de produits).
    -   *Modifier une tâche :* Modifie les paramètres (transporteurs, produits, fréquence) d'une assignation planifiée existante.
    -   *Supprimer une tâche :* Supprime une assignation planifiée, l'empêchant de s'exécuter à l'avenir.
    -   *Exécuter une tâche maintenant :* Exécute une tâche planifiée immédiatement, en dehors de son calendrier régulier.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    -   Utilisez cet écran pour automatiser les assignations de transporteurs de routine, surtout si vous importez régulièrement de nouveaux produits dans des catégories spécifiques ou de certains fabricants qui utilisent toujours les mêmes transporteurs.
    -   Pour les assignations ponctuelles et immédiates, utilisez la page de configuration principale du module (4.1).
    -   Vérifiez régulièrement les champs « Dernière exécution » et « Statut » pour vous assurer que vos tâches automatisées s'exécutent correctement.

#### 2.2.2 index.php (masscarrier/controllers/admin/index.php)

Ce fichier sert généralement de placeholder ou de redirection dans le répertoire des contrôleurs d'administration du module et ne représente généralement pas un écran distinct et configurable pour le marchand. Dans le développement de modules PrestaShop, les fichiers `index.php` dans les sous-répertoires empêchent souvent l'affichage du contenu du répertoire ou gèrent le routage de base, plutôt que de fournir une interface utilisateur. Par conséquent, il n'y a pas de paramètres ou d'actions spécifiques destinés au marchand associés à ce fichier.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Sélectionner les transporteurs | Sélectionner tous les pertinents | Choisir les transporteurs qui seront assignés aux produits. |
| | Sélectionner les produits : Par catégories | Sélectionner les catégories pertinentes | Assigner les transporteurs à tous les produits des catégories choisies. |
| | Sélectionner les produits : Par fabricants | Sélectionner les fabricants pertinents | Assigner les transporteurs à tous les produits des fabricants choisis. |
| | Sélectionner les produits : Par produits spécifiques | Rechercher et ajouter des produits | Assigner les transporteurs aux produits sélectionnés individuellement. |
| | Bouton Assigner les transporteurs | Cliquer après la sélection | Exécute l'assignation de transporteurs en masse. |
| | Bouton Effacer toutes les assignations | Utiliser avec prudence | Supprime les assignations de transporteurs pour les produits sélectionnés (si présent). |
| **AdminMassCarrierCronController** | Ajouter/Modifier/Supprimer une tâche | Selon les besoins d'automatisation | Planifier et gérer les assignations de transporteurs en masse automatisées. |
| | Action Exécuter maintenant | Au besoin pour une exécution immédiate | Déclencher manuellement une tâche planifiée. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai assigné des transporteurs, mais ils n'apparaissent pas pour les clients lors du paiement.**
R :

1.  **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). PrestaShop met souvent en cache la disponibilité des transporteurs.
2.  **Configuration du transporteur :** Vérifiez que les transporteurs eux-mêmes sont actifs, ont des zones de livraison valides et sont configurés pour gérer la plage de poids/prix du produit. Allez dans **Livraison > Transporteurs** et modifiez le transporteur pour revoir ses paramètres.
3.  **Dimensions/Poids du produit :** Assurez-vous que les dimensions et le poids du produit sont correctement saisis et qu'ils se situent dans les plages définies par le transporteur.
4.  **Exécution du module :** Réexécutez le processus d'assignation dans le module, en vous assurant d'avoir sélectionné les transporteurs et les groupes de produits corrects.

**Q : Le module semble bloqué ou prend beaucoup de temps à traiter.**
R :

1.  **Ressources du serveur :** Si vous avez un très grand catalogue (des dizaines de milliers de produits) et que vous assignez à « tous les produits », le processus peut être gourmand en ressources. Assurez-vous que votre hébergement dispose de suffisamment de mémoire PHP et de limites de temps d'exécution.
2.  **Tâche Cron :** Pour les opérations extrêmement importantes, envisagez d'utiliser le « AdminMassCarrierCronController » pour planifier la tâche comme une tâche cron en arrière-plan, ce qui est plus robuste pour les processus de longue durée.
3.  **Décomposer les tâches :** Au lieu d'assigner à *tous* les produits en une seule fois, essayez de le décomposer par catégories ou fabricants principaux.

**Q : Puis-je supprimer un transporteur de produits en masse à l'aide de ce module ?**
R : La fonction principale de ce module est d'*assigner* des transporteurs. Bien qu'il n'ait pas de fonction directe « supprimer le transporteur des produits sélectionnés », vous pouvez y parvenir efficacement en :

1.  **Réassignant :** Si vous souhaitez remplacer le Transporteur A par le Transporteur B pour un groupe de produits, sélectionnez simplement le Transporteur B et le groupe de produits, puis exécutez l'assignation. Cela ajoutera le Transporteur B. Vous devrez ensuite supprimer manuellement le Transporteur A de ces produits si vous souhaitez qu'il disparaisse complètement, ou utiliser un outil séparé si disponible.
2.  **Suppression manuelle :** Pour des produits spécifiques, vous pouvez toujours aller à la page d'édition du produit (**Catalogue > Produits > Modifier le produit > onglet Livraison**) et décocher manuellement le transporteur.

**Q : Mon thème personnalisé n'affiche pas correctement les éléments du module (si certains étaient visibles).**
R : Ce module n'a pas d'éléments visuels en front-office, donc les problèmes de compatibilité de thème sont peu probables du point de vue de l'affichage. Si vous rencontrez des problèmes avec les écrans de configuration du *back-office* :

1.  **Version de PrestaShop :** Assurez-vous d'avoir téléchargé la version correcte du module pour votre installation PrestaShop.
2.  **Cache du navigateur :** Videz le cache de votre navigateur.
3.  **Surcharges de thème :** Si votre thème de back-office est fortement personnalisé, il pourrait interférer. Essayez de passer temporairement au thème de back-office par défaut de PrestaShop pour voir si le problème persiste.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Assigner un transporteur aux produits en masse » (`masscarrier`) suit un modèle MVC (Modèle-Vue-Contrôleur) PrestaShop standard, se concentrant principalement sur les tâches administratives. Il exploite la classe `Module` de PrestaShop pour sa fonctionnalité principale et étend `AdminController` pour ses écrans de gestion dédiés au back-office. Le module interagit directement avec les données de produit et de transporteur de base de PrestaShop, modifiant la table `ps_product_carrier` pour établir des associations. Il inclut également un contrôleur frontal pour l'exécution des tâches cron, permettant des opérations de masse planifiées.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    -   `controllers/front/cronjob.php`
        -   **Nom de la classe et classe parente** : `MassCarrierCronjobModuleFrontController` étend `ModuleFrontController`.
        -   **Responsabilité** : Ce contrôleur est conçu pour être appelé en externe, généralement par une tâche cron côté serveur. Il exécute les tâches d'assignation de transporteur planifiées définies dans le back-office. Il ne rend aucune sortie visuelle au navigateur mais effectue un traitement en arrière-plan. Il gère la logique de récupération des tâches en attente de la table `masscarriercron` et d'application des changements de transporteur aux produits.
-   **Contrôleurs Admin Back-Office** :

    -   `controllers/admin/AdminMassCarrierCron.php`
        -   **Nom de l'onglet et entité gérée** : Ce contrôleur gère l'entité `masscarriercron`, qui représente les tâches d'assignation de transporteur en masse planifiées. Il crée un nouvel onglet dans le back-office de PrestaShop (probablement sous « Paramètres avancés » ou un menu personnalisé « Transporteur en masse »).
        -   **Responsabilité** : Fournit une interface `AdminController` PrestaShop standard pour lister, ajouter, modifier et supprimer des tâches cron planifiées. Il gère la soumission de formulaires pour créer/mettre à jour des tâches, valider les entrées et interagir avec la table de base de données `masscarriercron`.
    -   `controllers/admin/index.php`
        -   **Responsabilité** : Il s'agit d'un fichier `index.php` vide standard souvent placé dans les répertoires de modules PrestaShop pour empêcher l'affichage du contenu du répertoire lorsqu'il est accédé directement via un navigateur web. Il ne contient aucune logique fonctionnelle ni ne gère aucune entité.

### 4.3 Classes et modèles de base (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela implique que la logique principale pour l'assignation des transporteurs et la gestion des tâches cron est probablement gérée directement dans le fichier principal `masscarrier.php` et les contrôleurs respectifs, en utilisant éventuellement directement les `ObjectModel` `Product` et `Carrier` de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

-   `masscarrier/lib/searchTool/views/js/autocomplete.js`
    -   **Portée** : Back-office.
    -   **Responsabilité** : Ce script fournit probablement la fonctionnalité d'autocomplétion pour la sélection de produits spécifiques sur la page de configuration principale du module. Il écoute la saisie de l'utilisateur dans un champ de recherche de produit désigné, envoie des requêtes AJAX à un contrôleur de back-office (ou à la méthode `getContent()` du module principal) pour récupérer des suggestions de produits, et les affiche dans une liste déroulante. Il gère les événements de sélection pour ajouter les produits choisis à une liste pour l'assignation en masse.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `masscarrier/lib/searchTool/views/css/autocomplete.css`
    -   **Portée** : Style du formulaire d'administration du back-office.
    -   **Responsabilité** : Fournit le style pour le champ de recherche d'autocomplétion et sa liste de suggestions, garantissant qu'il s'intègre visuellement au thème du back-office de PrestaShop. Il définit les styles pour le champ de saisie, le conteneur déroulant et les éléments de suggestion individuels. Les développeurs peuvent surcharger ces classes dans leurs thèmes de back-office personnalisés si nécessaire.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :

    -   Aucun template de hook spécifique n'est listé, ce qui suggère que la configuration principale du module est gérée via `getContent()` et des contrôleurs d'administration dédiés.
-   **Templates d'administration (`views/templates/admin/`)** :

    -   `masscarrier/lib/searchTool/views/scripts.tpl`
        -   **Objectif** : Ce template inclut probablement le JavaScript nécessaire pour l'outil de recherche d'autocomplétion (par exemple, `autocomplete.js`) et potentiellement des configurations JavaScript en ligne ou des liens CSS. Il est probablement inclus dans le formulaire de configuration principal du module ou un formulaire de contrôleur d'administration.
    -   `masscarrier/masscarrier.tpl`
        -   **Objectif** : C'est le template de configuration principal du module, rendu par la méthode `getContent()` de `masscarrier.php`. Il contient la structure HTML pour la sélection des transporteurs, le choix des groupes de produits (catégories, fabricants, produits spécifiques) et le bouton « Assigner les transporteurs ». Il inclut probablement le `scripts.tpl` pour la fonctionnalité d'autocomplétion.
    -   `masscarrier/views/button-subcategories.tpl`
        -   **Objectif** : Ce template rend probablement un bouton ou une section liée à la gestion des sous-catégories, éventuellement pour développer/réduire les arborescences de catégories dans l'interface de sélection de produits, ou pour des actions spécifiques liées à la sélection de sous-catégories.
-   **Templates Front-office (`views/templates/front/`)** :

    -   Aucun template front-office n'est listé, ce qui est cohérent avec la nature administrative du module en back-office.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   `ps_masscarriercron` : Cette table personnalisée stocke les détails des tâches d'assignation de transporteur en masse planifiées. Elle contiendrait généralement des champs tels que :
        -   `id_masscarriercron` : Clé primaire.
        -   `carriers` : Un tableau sérialisé ou une chaîne d'ID de transporteurs séparés par des virgules.
        -   `product_selection_type` : (par exemple, 'category', 'manufacturer', 'product').
        -   `product_selection_ids` : Un tableau sérialisé ou une chaîne d'ID de catégorie/fabricant/produit séparés par des virgules.
        -   `frequency` : (par exemple, 'daily', 'weekly', 'once').
        -   `last_run` : DATETIME de la dernière exécution.
        -   `active` : BOOLEAN indiquant si la tâche est activée.
    -   Le module interagit principalement avec les tables de base de PrestaShop :
        -   `ps_product_carrier` : C'est la table cruciale qui stocke la relation plusieurs-à-plusieurs entre les produits et les transporteurs. Le module insère/met à jour des enregistrements dans cette table.
        -   `ps_product` : Pour récupérer les informations sur les produits.
        -   `ps_category_product` : Pour lier les produits aux catégories.
        -   `ps_product_supplier` / `ps_manufacturer` : Pour lier les produits aux fabricants.
        -   `ps_carrier` : Pour récupérer les informations sur les transporteurs.
-   **Table des hooks enregistrés** :
    La description du module mentionne « Hooks Front-Office : Header, Columns, Product, ou Footer » mais, d'après l'inventaire du code et l'objectif du module, il est très peu probable qu'il enregistre des hooks front-office pour une sortie visuelle. Il pourrait s'agir de placeholders génériques ou faire référence à des hooks internes utilisés pour l'initialisation du module ou le traitement des données.

    Le module utiliserait principalement des hooks PrestaShop internes pour sa fonctionnalité :

    | Nom du hook | Moment d'exécution | Objectif technique |
    | --- | --- | --- |
    | `actionModuleInstall` | Lors de l'installation du module | Crée la table `ps_masscarriercron`, enregistre les onglets d'administration. |
    | `actionModuleUninstall` | Lors de la désinstallation du module | Supprime la table `ps_masscarriercron`, désenregistre les onglets d'administration. |
    | `actionAdminControllerSetMedia` | Lors du chargement d'un contrôleur d'administration | Injecte les ressources JS/CSS pour les formulaires du back-office (par exemple, autocomplete.js, autocomplete.css). |
    | `displayBackOfficeHeader` | Rendu dans l'en-tête du back-office | Peut inclure du JS/CSS global du back-office ou de la configuration. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Assigner un transporteur aux produits en masse », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). MyPresta.eu fournit un support direct et vous assure d'avoir accès aux versions les plus compatibles et riches en fonctionnalités du module pour votre boutique PrestaShop.
