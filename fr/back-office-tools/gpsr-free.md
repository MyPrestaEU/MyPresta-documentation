---
title: "GPSR Free - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop GPSR Free par MyPresta.eu."
sidebar:
  label: "GPSR Free"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module GPSR Free sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/gpsr-free.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/gpsr-free/)
>
> ---


# GPSR Free

## 1. Exigences et compatibilité
-   **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilité PHP** : PHP 7.1 - 8.5
-   **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises, qui sont généralement disponibles sur la plupart des environnements d'hébergement compatibles PrestaShop.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > GPSR Free)

C'est l'écran de configuration principal du module GPSR Free, accessible immédiatement après l'installation ou en cliquant sur "Configurer" depuis le Gestionnaire de modules.

-   **Ce que fait ce paramètre :** Cet interrupteur contrôle si le bloc d'informations GPSR est affiché sur vos pages produits dans le front office.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (Oui) :* Le bloc d'informations GPSR, contenant les détails du fabricant, de la personne responsable et des avertissements, apparaîtra sur les pages produits où vous avez mappé les informations pertinentes.
    -   *Lorsqu'il est désactivé (Non) :* Le bloc d'informations GPSR sera masqué de toutes les pages produits, quelle que soit la configuration de mappage que vous avez définie.
-   **Valeur recommandée :** **Oui**. Pour se conformer au RGSP et afficher les informations, cela devrait être activé.
-   **Scénario / exemple de marchand :** Si vous configurez activement vos données GPSR et souhaitez qu'elles soient visibles pour les clients, activez ceci. Si vous êtes toujours en train de configurer les données ou souhaitez temporairement masquer le bloc (par exemple, lors d'une refonte du site), vous pouvez le désactiver.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module GPSR Free ajoute plusieurs nouveaux éléments de menu sous une section principale "GPSR Free" dans votre Back Office PrestaShop. Ces écrans vous permettent de gérer les différentes informations requises pour la conformité au RGSP.

#### 2.2.1 Tableau de bord GPSR Free (Back Office > GPSR Free > Tableau de bord)
Cet écran sert de point d'entrée principal pour l'administration dédiée du module. Il fournit généralement un aperçu ou des liens rapides vers les autres sections de gestion.

-   **Actions et paramètres disponibles :** Cette vue présente généralement une interface de type tableau de bord, affichant potentiellement des statistiques ou des liens rapides pour gérer les Fabricants, les Entités, les Avertissements et les Mappages de produits.
-   **Effet des modifications :** Cet écran lui-même n'a pas de paramètres directs qui modifient le comportement du front-office, mais c'est votre centre de navigation pour toute la gestion des données GPSR.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Commencez ici pour obtenir un aperçu, puis naviguez vers les sections spécifiques (Fabricants, Entités, Avertissements, Mappage de produits) pour ajouter ou modifier des données.

#### 2.2.2 Fabricants (Back Office > GPSR Free > Fabricants)
Cet écran vous permet de définir et de gérer les fabricants de vos produits.

-   **Actions et paramètres disponibles :**
    -   **Tableau de liste :** Affiche tous les fabricants que vous avez ajoutés, avec des colonnes pour le nom, l'adresse et des actions comme "Modifier" ou "Supprimer".
    -   **Bouton "Ajouter un nouveau fabricant" :** Cliquer sur ce bouton ouvre un formulaire pour créer une nouvelle entrée de fabricant.
    -   **Champs du formulaire (pour ajouter/modifier un fabricant) :**
        -   **Nom :** Le nom officiel du fabricant.
        -   **Adresse :** L'adresse postale complète du fabricant.
        -   **Est un fabricant de l'UE ?** : Un interrupteur pour indiquer si ce fabricant est basé au sein de l'Union européenne. Ceci est crucial pour déterminer si une "Personne responsable dans l'UE" doit être assignée.
-   **Effet des modifications :** L'ajout ou la modification de fabricants ici crée ou met à jour la liste centrale des fabricants que vous pouvez ensuite associer à vos produits. Ces informations seront affichées sur les pages produits si elles sont mappées.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Avant de mapper les produits, assurez-vous que tous les fabricants de vos produits sont listés ici avec des détails précis. Si une nouvelle gamme de produits provient d'un nouveau fabricant, ajoutez-le ici en premier.

#### 2.2.3 Personnes responsables dans l'UE (Back Office > GPSR Free > Personnes responsables dans l'UE)
Cet écran est destiné à la gestion des "Personnes responsables dans l'UE" (également appelées "Entités" dans la nomenclature interne du module) qui sont désignées pour les produits fabriqués en dehors de l'UE.

-   **Actions et paramètres disponibles :**
    -   **Tableau de liste :** Affiche toutes les personnes responsables dans l'UE définies, avec leur nom, adresse et actions.
    -   **Bouton "Ajouter une nouvelle personne responsable dans l'UE" :** Ouvre un formulaire pour ajouter une nouvelle personne responsable.
    -   **Champs du formulaire (pour ajouter/modifier une personne responsable dans l'UE) :**
        -   **Nom :** Le nom de la personne ou entité responsable dans l'UE (par exemple, importateur, représentant autorisé).
        -   **Adresse :** L'adresse postale complète de la personne responsable dans l'UE au sein de l'UE.
-   **Effet des modifications :** Cela crée ou met à jour la liste des personnes responsables dans l'UE qui peuvent être liées à des fabricants non-UE ou directement à des produits. Ces informations sont affichées sur les pages produits lorsque cela est applicable.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Si vous importez des produits de l'extérieur de l'UE, assurez-vous d'avoir les détails corrects de la personne responsable dans l'UE saisis ici.

#### 2.2.4 Avertissements (Back Office > GPSR Free > Avertissements)
Cet écran vous permet de créer et de gérer des avertissements ou des clauses de non-responsabilité personnalisés.

-   **Actions et paramètres disponibles :**
    -   **Tableau de liste :** Affiche tous les avertissements créés, avec leur texte et leurs actions.
    -   **Bouton "Ajouter un nouvel avertissement" :** Ouvre un formulaire pour créer un nouvel avertissement.
    -   **Champs du formulaire (pour ajouter/modifier un avertissement) :**
        -   **Texte de l'avertissement :** Le texte réel de l'avertissement ou de l'instruction de sécurité. Ce champ est généralement multilingue, vous permettant de fournir des traductions pour chaque langue activée dans votre boutique (contrôlé par `PS_LANG_DEFAULT`).
-   **Effet des modifications :** L'ajout ou la modification d'avertissements ici crée ou met à jour le pool d'avertissements que vous pouvez associer aux produits. Les avertissements sélectionnés apparaîtront sur la page produit.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Créez des avertissements génériques qui s'appliquent à plusieurs produits (par exemple, "Tenir hors de portée des enfants", "Lire les instructions avant utilisation"). Vous pourrez ensuite facilement les sélectionner pour des produits individuels.

#### 2.2.5 Mappage de produits (Back Office > GPSR Free > Mappage de produits)
C'est l'écran le plus critique où vous liez vos produits aux fabricants, aux personnes responsables dans l'UE et aux avertissements que vous avez définis.

-   **Actions et paramètres disponibles :**
    -   **Tableau de liste :** Affiche les mappages de produits existants, affichant généralement le nom du produit, le fabricant associé, la personne responsable dans l'UE et les avertissements.
    -   **Bouton "Ajouter un nouveau mappage de produit" :** Ouvre un formulaire pour créer un nouveau mappage.
    -   **Champs du formulaire (pour ajouter/modifier un mappage de produit) :**
        -   **Recherche de produit :** Un champ pour rechercher et sélectionner le produit spécifique que vous souhaitez mapper.
        -   **Fabricant :** Une liste déroulante pour sélectionner l'un des fabricants que vous avez définis dans la section "Fabricants".
        -   **Personne responsable dans l'UE :** Une liste déroulante pour sélectionner l'une des personnes responsables dans l'UE que vous avez définies. Ce champ peut n'être obligatoire ou apparaître que si le fabricant sélectionné n'est *pas* un fabricant de l'UE.
        -   **Avertissements :** Une boîte de sélection multiple ou une liste de contrôle pour choisir un ou plusieurs avertissements de la section "Avertissements" à associer à ce produit.
-   **Effet des modifications :** Lorsque vous enregistrez un mappage de produit, le fabricant sélectionné, la personne responsable dans l'UE (le cas échéant) et les avertissements seront affichés sur la page produit du front-office pour ce produit spécifique, à condition que le paramètre "Activer le bloc GPSR" soit actif.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Après avoir configuré vos fabricants, personnes responsables dans l'UE et avertissements, parcourez votre catalogue de produits et mappez chaque produit pertinent ici. C'est là que les informations GPSR sont rassemblées pour l'affichage.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
|---|---|---|---|
| Configuration du module | Activer le bloc GPSR | Oui | Contrôle la visibilité du bloc d'informations GPSR sur les pages produits. |
| Fabricants | Nom | N/A | Nom officiel du fabricant du produit. |
| Fabricants | Adresse | N/A | Adresse postale complète du fabricant. |
| Fabricants | Est un fabricant de l'UE ? | Oui | Indique si le fabricant est basé dans l'UE, ce qui affecte la nécessité d'une personne responsable dans l'UE. |
| Personnes responsables dans l'UE | Nom | N/A | Nom de la personne/entité responsable dans l'UE désignée. |
| Personnes responsables dans l'UE | Adresse | N/A | Adresse postale complète de la personne responsable dans l'UE au sein de l'UE. |
| Avertissements | Texte de l'avertissement | N/A | Le texte réel de l'avertissement ou de l'instruction de sécurité (multilingue). |
| Mappage de produits | Produit | N/A | Sélectionne le produit auquel les informations GPSR seront mappées. |
| Mappage de produits | Fabricant | N/A | Associe un fabricant défini au produit sélectionné. |
| Mappage de produits | Personne responsable dans l'UE | N/A | Associe une personne responsable dans l'UE définie au produit sélectionné (si le fabricant n'est pas de l'UE). |
| Mappage de produits | Avertissements | N/A | Sélectionne un ou plusieurs avertissements définis à afficher pour le produit. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai tout configuré, mais le bloc GPSR n'apparaît pas sur mes pages produits.**
R :
1.  **Vérifiez "Activer le bloc GPSR" :** Allez dans **Modules > Gestionnaire de modules > GPSR Free > Configurer** et assurez-vous que le paramètre "Activer le bloc GPSR" est défini sur "Oui".
2.  **Videz le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions plus anciennes). Parfois, le cache de PrestaShop empêche l'apparition immédiate de nouveau contenu.
3.  **Mappage de produits :** Vérifiez que le produit spécifique que vous consultez a été mappé dans **GPSR Free > Mappage de produits** avec un fabricant et au moins un avertissement/entité.
4.  **Compatibilité du thème :** Bien que le module essaie d'être compatible avec la plupart des thèmes, les thèmes très fortement personnalisés peuvent nécessiter des ajustements mineurs. Si le bloc est complètement manquant après avoir vérifié ce qui précède, contactez le support MyPresta.eu.

**Q : Le texte d'avertissement ou les détails du fabricant ne s'affichent pas dans la bonne langue.**
R :
1.  **Vérifiez les traductions :** Lors de la modification d'un avertissement ou d'un fabricant, assurez-vous d'avoir fourni des traductions pour toutes les langues actives de votre boutique. Recherchez les onglets de langue à côté des champs de saisie.
2.  **Langue par défaut :** Le module utilise la langue par défaut de PrestaShop (`PS_LANG_DEFAULT`) si une traduction spécifique est manquante. Assurez-vous que votre langue par défaut est correctement définie dans **International > Localisation**.

**Q : Comment puis-je supprimer les données d'exemple installées avec le module ?**
R : Vous pouvez accéder à chaque écran de gestion respectif (**GPSR Free > Fabricants**, **GPSR Free > Personnes responsables dans l'UE**, **GPSR Free > Avertissements**, **GPSR Free > Mappage de produits**) et utiliser l'action "Supprimer" pour chaque entrée d'exemple.

**Q : Puis-je personnaliser l'apparence du bloc GPSR ?**
R : Oui, le module inclut un fichier `front.css`. Pour des modifications de style de base (couleurs, polices, espacement), vous pouvez souvent remplacer ces styles dans le fichier CSS personnalisé de votre thème sans modifier directement le module. Pour des modifications de mise en page plus avancées, vous devrez peut-être ajuster le modèle `product-footer.tpl`. (Voir la section 7 pour les détails du développeur).

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture
Le module GPSR Free suit le modèle MVC (Modèle-Vue-Contrôleur) de PrestaShop. Il utilise des contrôleurs d'administration personnalisés pour gérer les données liées au RGSP (Fabricants, Entités, Avertissements, Mappages de produits) et exploite l'`ObjectModel` de PrestaShop pour la persistance des données. L'affichage en front-office est géré via un modèle de hook. Le module utilise un modèle de dépôt (`GpsrFreeRepository`) pour les interactions avec la base de données, favorisant un code plus propre et une séparation des préoccupations.

### 4.2 Contrôleurs (`controllers/`)

Le module utilise principalement des contrôleurs d'administration Back-Office pour la gestion des données. Il n'y a pas de contrôleurs front-office dédiés car l'affichage en front-office est géré directement via des hooks.

-   **Contrôleurs d'administration Back-Office** :
    -   `controllers/admin/AdminGpsrFreeController.php`
        -   **Nom de la classe :** `AdminGpsrFreeController` (étend `ModuleAdminController`)
        -   **Nom de l'onglet :** GPSR Free (entrée principale du tableau de bord)
        -   **Responsabilité :** Sert de point d'entrée principal pour l'administration du module, affichant probablement un tableau de bord ou des liens vers d'autres écrans de gestion spécifiques. Il ne gère pas une entité spécifique mais orchestre l'accès aux autres contrôleurs.
    -   `controllers/admin/AdminGpsrFreeEntitiesController.php`
        -   **Nom de la classe :** `AdminGpsrFreeEntitiesController` (étend `ModuleAdminController`)
        -   **Nom de l'onglet :** Personnes responsables dans l'UE
        -   **Entité gérée :** `GpsrFreeEntity` (mappe à la table `ps_gpsrfree_entity`)
        -   **Responsabilité :** Gère la création, l'édition, la liste et la suppression des personnes responsables dans l'UE (entités). Fournit une vue de liste et de formulaire PrestaShop standard pour ces données.
    -   `controllers/admin/AdminGpsrFreeManufacturersController.php`
        -   **Nom de la classe :** `AdminGpsrFreeManufacturersController` (étend `ModuleAdminController`)
        -   **Nom de l'onglet :** Fabricants
        -   **Entité gérée :** `GpsrFreeManufacturer` (mappe à la table `ps_gpsrfree_manufacturer`)
        -   **Responsabilité :** Gère la création, l'édition, la liste et la suppression des fabricants de produits. Inclut la logique pour `is_eu_manufacturer`.
    -   `controllers/admin/AdminGpsrFreeMapController.php`
        -   **Nom de la classe :** `AdminGpsrFreeMapController` (étend `ModuleAdminController`)
        -   **Nom de l'onglet :** Mappage de produits
        -   **Entité gérée :** `GpsrFreeProductMap` (mappe à la table `ps_gpsrfree_product_map`)
        -   **Responsabilité :** Gère le mappage entre les produits, les fabricants, les personnes responsables dans l'UE et les avertissements. Ce contrôleur gère les relations complexes entre les différents types de données GPSR.
    -   `controllers/admin/AdminGpsrFreeWarningsController.php`
        -   **Nom de la classe :** `AdminGpsrFreeWarningsController` (étend `ModuleAdminController`)
        -   **Nom de l'onglet :** Avertissements
        -   **Entité gérée :** `GpsrFreeWarning` (mappe à la table `ps_gpsrfree_warning`)
        -   **Responsabilité :** Gère la création, l'édition, la liste et la suppression des avertissements de sécurité. Prend en charge les champs multilingues.
    -   `controllers/admin/GpsrFreeAdminController.php`
        -   **Nom de la classe :** `GpsrFreeAdminController` (étend `ModuleAdminController`)
        -   **Nom de l'onglet :** (Probablement un contrôleur de base ou abstrait pour d'autres contrôleurs d'administration, ou un point d'entrée plus ancien/redondant)
        -   **Responsabilité :** Compte tenu de son nom générique, il pourrait servir de classe de base pour d'autres contrôleurs d'administration dans le module, fournissant des méthodes ou des propriétés communes, ou il pourrait s'agir d'un point d'entrée hérité.
    -   `controllers/admin/index.php`
        -   **Nom de la classe :** N/A
        -   **Responsabilité :** Fichier de sécurité PrestaShop standard pour empêcher la liste directe des répertoires.

### 4.3 Classes et modèles principaux (`classes/`)

-   `classes/GpsrFreeAdminUi.php`
    -   **Nom de la classe :** `GpsrFreeAdminUi`
    -   **Responsabilité :** Probablement une classe d'aide pour générer ou gérer des éléments d'interface utilisateur dans le Back Office, tels que des champs de formulaire, des configurations de liste ou des composants d'interface d'administration courants. Elle aide à standardiser l'apparence des écrans d'administration du module.
-   `classes/GpsrFreeEntity.php`
    -   **Nom de la classe :** `GpsrFreeEntity` (étend `ObjectModel`)
    -   **Table de base de données :** `ps_gpsrfree_entity`
    -   **Champs `$definition` :** Définit des champs comme `name`, `address`.
    -   **Méthodes publiques clés :** Méthodes `ObjectModel` standard pour les opérations CRUD. Représente une personne responsable dans l'UE.
-   `classes/GpsrFreeManufacturer.php`
    -   **Nom de la classe :** `GpsrFreeManufacturer` (étend `ObjectModel`)
    -   **Table de base de données :** `ps_gpsrfree_manufacturer`
    -   **Champs `$definition` :** Définit des champs comme `name`, `address`, `is_eu_manufacturer`.
    -   **Méthodes publiques clés :** Méthodes `ObjectModel` standard pour les opérations CRUD. Représente un fabricant de produit.
-   `classes/GpsrFreeProductMap.php`
    -   **Nom de la classe :** `GpsrFreeProductMap` (étend `ObjectModel`)
    -   **Table de base de données :** `ps_gpsrfree_product_map`
    -   **Champs `$definition` :** Définit des champs comme `id_product`, `id_manufacturer`, `id_entity`, `id_warning`. Cette table stocke probablement les relations plusieurs-à-plusieurs ou les mappages directs.
    -   **Méthodes publiques clés :** Méthodes `ObjectModel` standard pour les opérations CRUD. Gère les liens entre les produits et les données GPSR.
-   `classes/GpsrFreeRepository.php`
    -   **Nom de la classe :** `GpsrFreeRepository`
    -   **Responsabilité :** Implémente le modèle de dépôt. Cette classe est responsable de toutes les interactions directes avec la base de données, les abstraisant des contrôleurs et des modèles. Elle contient des méthodes pour récupérer, insérer, mettre à jour et supprimer des données liées au RGSP, souvent en utilisant la classe `Db` de PrestaShop. Elle contiendrait des méthodes comme `getMappedProductData($id_product)`.
-   `classes/GpsrFreeWarning.php`
    -   **Nom de la classe :** `GpsrFreeWarning` (étend `ObjectModel`)
    -   **Table de base de données :** `ps_gpsrfree_warning`
    -   **Champs `$definition` :** Définit des champs comme `text` (multilingue).
    -   **Méthodes publiques clés :** Méthodes `ObjectModel` standard pour les opérations CRUD. Représente un avertissement de sécurité.
-   `classes/index.php`
    -   **Nom de la classe :** N/A
    -   **Responsabilité :** Fichier de sécurité PrestaShop standard pour empêcher la liste directe des répertoires.

### 4.4 Actifs JavaScript (`views/js/`)
L'inventaire fourni indique qu'aucun fichier JavaScript personnalisé n'est inclus dans le module. Cela suggère que le module s'appuie principalement sur les fonctionnalités JavaScript intégrées de PrestaShop pour ses formulaires d'administration et potentiellement des interactions minimales en front-office, ou que tout comportement dynamique est géré côté serveur.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `views/css/admin.css`
    -   **Portée :** Style des formulaires d'administration du Back-Office.
    -   **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :** Fournit probablement un style spécifique pour les pages d'administration personnalisées du module, telles que les tableaux de liste, les éléments de formulaire ou les widgets de tableau de bord, afin d'assurer une apparence cohérente au sein du Back Office de PrestaShop.
    -   **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer :** Toutes les classes personnalisées utilisées dans les modèles d'administration du module (par exemple, `.gpsrfree-admin-panel`, `.gpsrfree-table`).
-   `views/css/front.css`
    -   **Portée :** Style client du Front-Office.
    -   **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :** Style le bloc d'informations GPSR affiché sur les pages produits. Cela inclurait le style du conteneur du bloc, des titres, des détails du fabricant, des détails de la personne responsable dans l'UE et des listes d'avertissements.
    -   **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer :** Classes comme `.gpsrfree-block`, `.gpsrfree-manufacturer`, `.gpsrfree-entity`, `.gpsrfree-warnings`, etc. Les développeurs peuvent cibler ces classes dans le fichier `custom.css` ou `theme.css` de leur thème pour correspondre à l'image de marque de la boutique.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** :
    -   `views/templates/hook/product-footer.tpl`
        -   **Hook :** `displayFooterProduct` (et potentiellement `displayProductButtons` ou similaire, bien que `displayFooterProduct` soit explicitement listé).
        -   **Sortie du bloc visuel :** Ce modèle est responsable du rendu de l'intégralité du bloc d'informations GPSR sur la page produit. Il contiendra la logique pour afficher les détails du fabricant, les détails de la personne responsable dans l'UE (le cas échéant) et une liste d'avertissements associés, basés sur les données récupérées du `GpsrFreeRepository` pour le produit actuel.
-   **Modèles d'administration (`views/templates/admin/`)** :
    -   `views/templates/admin/configure.tpl`
        -   **Hook :** Rendu par la méthode `getContent()` du fichier de module principal `gpsrfree.php`.
        -   **Sortie du bloc visuel :** Ce modèle rend le formulaire de configuration principal du module dans le Back Office, en particulier l'interrupteur "Activer le bloc GPSR". Il peut également contenir des liens ou un texte d'introduction pour naviguer vers les contrôleurs d'administration dédiés.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    -   `ps_gpsrfree_entity` : Stocke les informations sur les personnes responsables dans l'UE (id, nom, adresse).
    -   `ps_gpsrfree_manufacturer` : Stocke les informations sur les fabricants de produits (id, nom, adresse, is_eu_manufacturer).
    -   `ps_gpsrfree_product_map` : Stocke les relations de mappage entre les produits, les fabricants, les personnes responsables dans l'UE et les avertissements (id_product, id_manufacturer, id_entity, id_warning). Cette table gère probablement les relations plusieurs-à-plusieurs en stockant plusieurs entrées pour un seul produit s'il a plusieurs avertissements.
    -   `ps_gpsrfree_warning` : Stocke le texte des avertissements de sécurité (id, texte - multilingue).
    -   `ps_configuration` : Les paramètres du module comme `GPSRFREE_ENABLED` sont stockés ici.

-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
|---|---|---|
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Potentiellement utilisé pour charger le CSS du front-office (`front.css`) ou le JavaScript (s'il y en avait) globalement. |
| `displayFooterProduct` | En bas de la page produit, généralement sous le contenu principal du produit. | Hook principal pour le rendu du bloc d'informations GPSR (`product-footer.tpl`) sur la page produit. |
| `displayBackOfficeHeader` | Dans la section `<head>` de chaque page du Back Office. | Utilisé pour charger le CSS du Back Office (`admin.css`) ou le JavaScript pour les écrans d'administration du module. |
| `displayAdminProductsExtra` | (Implicite, souvent utilisé pour ajouter des onglets/sections à la page d'édition de produit) | Bien que non explicitement listé comme enregistré, les modules utilisent souvent ce hook ou des hooks similaires pour s'intégrer à la page d'édition de produit si le mappage y était effectué directement. Compte tenu de `AdminGpsrFreeMapController`, il s'agit probablement d'un écran séparé. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | (Non explicitement listé comme enregistré, mais courant pour les modules interagissant avec les commandes. S'il est présent, il serait destiné au traitement des données GPSR liées aux commandes, ce qui n'est pas indiqué par la description du module.) |

*Note : Le dossier du module listait `DisplayHeader`, `DisplayFooterProduct`, `displayHeader`, `DisplayBackOfficeHeader`, `displayFooterProduct`, `displayBackOfficeHeader`. Ce sont des doublons dus à la sensibilité à la casse, mais ils se réfèrent fonctionnellement aux mêmes hooks.*

## 5. Support officiel et mises à jour
Pour les dernières mises à jour, corrections de bugs et support officiel du module GPSR Free, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
