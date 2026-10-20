---
title: "Accès aux produits par pays - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Accès aux produits par pays' par MyPresta.eu."
sidebar:
  label: "Accès aux produits par pays - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Access to products by country sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/access-to-products-by-country.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/access-to-products-by-country/)
>
> ---


# Accès aux produits par pays

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module « Accès aux produits par pays ». Vous y trouverez tous les paramètres pour définir comment l'accès aux produits est restreint.

#### Paramètres généraux

-   **Activé / Désactivé (Statut du module)**

    -   **Ce que fait ce paramètre :** C'est l'interrupteur principal du module.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Le module filtrera activement les produits en fonction des restrictions par pays.
        -   *Lorsqu'il est désactivé :* Le module sera inactif, et tous les produits seront visibles pour tous les clients, quel que soit leur pays.
    -   **Valeur recommandée :** **Activé** une fois que vous avez configuré vos règles.
    -   **Scénario / exemple marchand :** Vous configurez le module pour la première fois ; gardez-le désactivé jusqu'à ce que vous ayez défini toutes vos règles, puis activez-le pour le mettre en ligne.
-   **Que voulez-vous faire ? (Type de restriction)**

    -   **Ce que fait ce paramètre :** Définit la logique principale de vos restrictions par pays : voulez-vous *bloquer* les produits dans les pays sélectionnés, ou *autoriser* les produits *UNIQUEMENT* dans les pays sélectionnés ?
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur « Bloquer l'accès aux produits dans les pays sélectionnés » :* Les produits que vous configurez seront masqués aux clients des pays que vous spécifiez. Ils seront visibles partout ailleurs.
        -   *Lorsqu'il est défini sur « Autoriser l'accès aux produits UNIQUEMENT dans les pays sélectionnés » :* Les produits que vous configurez ne seront visibles *que* pour les clients des pays que vous spécifiez. Ils seront masqués partout ailleurs.
    -   **Valeur recommandée :** Choisissez en fonction de votre cas d'utilisation principal. Si vous avez quelques pays où un produit est restreint, choisissez « Bloquer ». Si un produit est exclusif à quelques pays, choisissez « Autoriser UNIQUEMENT ».
    -   **Scénario / exemple marchand :**
        -   *Bloquer :* Vous vendez une marque spécifique qui ne peut pas être expédiée au Canada. Vous sélectionneriez « Bloquer l'accès » puis choisiriez le Canada pour ce produit.
        -   *Autoriser UNIQUEMENT :* Vous avez un produit en édition spéciale uniquement disponible à la vente aux États-Unis et au Mexique. Vous sélectionneriez « Autoriser l'accès UNIQUEMENT » puis choisiriez les États-Unis et le Mexique pour ce produit.
-   **Sélectionner les pays**

    -   **Ce que fait ce paramètre :** C'est ici que vous sélectionnez les pays spécifiques qui seront affectés par la règle « Que voulez-vous faire ? ».
    -   **Effet de la modification de ce paramètre :** Les pays sélectionnés seront soit bloqués de voir le produit, soit seront les seuls autorisés à le voir, selon le paramètre « Que voulez-vous faire ? ».
    -   **Valeur recommandée :** Sélectionnez tous les pays pertinents en fonction de vos restrictions de produits.
    -   **Scénario / exemple marchand :** Si vous bloquez les ventes au Canada et en Australie, vous sélectionneriez le Canada et l'Australie dans la liste.
-   **Sélectionner les catégories**

    -   **Ce que fait ce paramètre :** Vous permet d'appliquer les règles de restriction par pays à des catégories de produits entières au lieu de produits individuels.
    -   **Effet de la modification de ce paramètre :** Tous les produits des catégories sélectionnées hériteront des règles de restriction par pays définies ci-dessus.
    -   **Valeur recommandée :** Utilisez ceci pour des restrictions larges. Laissez vide si vous souhaitez gérer les restrictions produit par produit.
    -   **Scénario / exemple marchand :** Tous les produits de votre catégorie « Électronique » ne peuvent pas être vendus au Brésil. Vous sélectionneriez la catégorie « Électronique » ici.
-   **Sélectionner le fabricant**

    -   **Ce que fait ce paramètre :** Vous permet d'appliquer les règles de restriction par pays à tous les produits de fabricants spécifiques.
    -   **Effet de la modification de ce paramètre :** Tous les produits des fabricants sélectionnés hériteront des règles de restriction par pays.
    -   **Valeur recommandée :** Utilisez ceci pour des restrictions au niveau de la marque. Laissez vide si vous souhaitez gérer les restrictions produit par produit ou catégorie par catégorie.
    -   **Scénario / exemple marchand :** Vous avez un accord de distribution qui vous empêche de vendre les produits « Marque X » en Europe. Vous sélectionneriez « Marque X » ici.

#### Exclusions de clients et de groupes

-   **Exclure des groupes de clients**

    -   **Ce que fait ce paramètre :** Vous permet d'exempter certains groupes de clients des restrictions par pays. Par exemple, vous pourriez avoir un groupe B2B spécial autorisé à acheter des produits restreints.
    -   **Effet de la modification de ce paramètre :** Les clients appartenant aux groupes sélectionnés ne seront *pas* soumis aux restrictions par pays définies par ce module. Ils verront tous les produits.
    -   **Valeur recommandée :** Sélectionnez les groupes qui ont besoin d'un accès spécial, tels que « Clients professionnels » ou « Employés ». Laissez vide si tous les clients doivent être soumis aux restrictions.
    -   **Scénario / exemple marchand :** Vous avez un groupe « Clients VIP » qui est autorisé à acheter des produits autrement restreints dans leur pays. Vous sélectionneriez le groupe « Clients VIP » ici.
-   **Exclure des clients**

    -   **Ce que fait ce paramètre :** Vous permet d'exempter des clients individuels spécifiques des restrictions par pays.
    -   **Effet de la modification de ce paramètre :** Les clients individuels sélectionnés ne seront *pas* soumis aux restrictions par pays. Ils verront tous les produits.
    -   **Valeur recommandée :** Utilisez ceci pour des exceptions spécifiques. Laissez vide si non nécessaire.
    -   **Scénario / exemple marchand :** Un client spécifique est un partenaire de longue date et a besoin d'accéder à tous les produits, quel que soit son emplacement. Vous sélectionneriez son compte client ici.

#### Paramètres de géolocalisation et de simulation

-   **Définir la priorité des méthodes d'identification d'origine**

    -   **Ce que fait ce paramètre :** Détermine l'ordre dans lequel le module tente d'identifier le pays du client. C'est crucial pour la précision.
    -   **Effet de la modification de ce paramètre :** Le module essaiera d'abord la méthode en haut de la liste. Si cela échoue ou n'est pas disponible, il passe à la suivante.
    -   **Valeur recommandée :**
        1.  **Adresse de livraison (si disponible) :** C'est la plus précise pour l'intention d'achat réelle.
        2.  **Géolocalisation :** Bon pour la navigation initiale.
        3.  **Pays du compte client :** Si connecté.
    -   **Scénario / exemple marchand :** Un client navigue depuis les États-Unis (géolocalisation), mais a l'intention d'expédier au Canada. Si « Adresse de livraison » est priorisée, le module utilisera le Canada pour les restrictions une fois qu'il l'aura saisie dans le panier.
-   **Utiliser l'adresse de livraison**

    -   **Ce que fait ce paramètre :** Lorsqu'il est activé, le module considérera le pays de l'adresse de livraison sélectionnée par le client dans le panier comme son « origine » pour appliquer les restrictions.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Si un client ajoute un produit restreint à son panier et sélectionne ensuite une adresse de livraison dans un pays bloqué, le module empêchera le paiement ou supprimera le produit.
        -   *Lorsqu'il est désactivé :* Le module se basera uniquement sur la géolocalisation IP ou le pays enregistré du client, ce qui pourrait ne pas correspondre à sa destination d'expédition prévue.
    -   **Valeur recommandée :** **OUI**. Cela fournit l'application de restriction la plus précise et la plus pratique pendant le processus de paiement.
    -   **Scénario / exemple marchand :** Un client d'Allemagne (où un produit est autorisé) l'ajoute à son panier, mais sélectionne ensuite une adresse de livraison en Autriche (où le produit est bloqué). Avec ce paramètre activé, le module empêchera la commande.
-   **Simuler la visite**

    -   **Ce que fait ce paramètre :** Vous permet de tester vos restrictions par pays en simulant une visite depuis un pays spécifique sans réellement changer votre adresse IP.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Le module traitera votre session actuelle comme si vous naviguiez depuis le pays spécifié dans « Simuler l'IP ».
        -   *Lorsqu'il est désactivé :* Le module utilise votre adresse IP réelle pour la géolocalisation.
    -   **Valeur recommandée :** **Désactivé** pour les boutiques en ligne. **Activé** uniquement pour les tests.
    -   **Scénario / exemple marchand :** Vous voulez vérifier si un produit est correctement masqué pour les clients en France. Vous activez « Simuler la visite », entrez une adresse IP française (ou sélectionnez la France si disponible), puis naviguez sur votre boutique.
-   **Simuler l'IP**

    -   **Ce que fait ce paramètre :** Lorsque « Simuler la visite » est activé, ce champ vous permet de saisir une adresse IP du pays que vous souhaitez simuler, ou de sélectionner un pays dans une liste déroulante.
    -   **Effet de la modification de ce paramètre :** Le module utilisera cette IP/ce pays pour toutes les vérifications de restriction pendant votre session simulée.
    -   **Valeur recommandée :** Saisissez une adresse IP valide ou sélectionnez un pays à des fins de test.
    -   **Scénario / exemple marchand :** Pour simuler une visite depuis l'Allemagne, vous pourriez entrer `88.130.179.0` (une IP allemande) ou simplement sélectionner « Allemagne » dans la liste.

#### Paramètres de liste blanche

-   **Activer la liste blanche**

    -   **Ce que fait ce paramètre :** Ce paramètre utilise la fonctionnalité de liste blanche de géolocalisation intégrée de PrestaShop. Si la géolocalisation de PrestaShop est active, cette liste blanche vous permet de définir des adresses IP ou des plages d'IP spécifiques qui devraient *toujours* être autorisées à accéder à votre boutique, quel que soit leur pays détecté. C'est utile pour les IP de votre propre bureau ou des partenaires de confiance.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Le module respectera la liste blanche de géolocalisation de PrestaShop. Les IP de cette liste contourneront toutes les restrictions par pays.
        -   *Lorsqu'il est désactivé :* La liste blanche ne sera pas prise en compte.
    -   **Valeur recommandée :** **OUI** si vous utilisez la géolocalisation de PrestaShop et que vous avez des IP que vous souhaitez mettre en liste blanche.
    -   **Scénario / exemple marchand :** Votre bureau est dans un pays où certains produits sont restreints, mais vous devez y accéder à des fins administratives. Vous ajouteriez l'adresse IP de votre bureau à la liste blanche de géolocalisation de PrestaShop et activeriez ce paramètre.
-   **Liste blanche**

    -   **Ce que fait ce paramètre :** C'est ici que vous gérez les adresses IP ou les plages d'IP spécifiques qui sont mises en liste blanche. Cela correspond directement au paramètre `PS_GEOLOCATION_WHITELIST` de PrestaShop.
    -   **Effet de la modification de ce paramètre :** Toute adresse IP ou plage saisie ici contournera toutes les restrictions basées sur la géolocalisation.
    -   **Valeur recommandée :** Ajoutez les adresses IP de votre propre bureau, les IP de serveurs de développement ou toute autre IP de confiance qui devrait toujours avoir un accès complet.
    -   **Scénario / exemple marchand :** Vous ajoutez `192.168.1.1/24` (votre réseau de bureau) pour vous assurer que tous les employés peuvent accéder à tous les produits.

#### Paramètres de mise à jour (Internes)

-   **mypresta\_updates, update\_, updatev\_**
    -   **Ce que font ces paramètres :** Ce sont des paramètres internes utilisés par les modules MyPresta.eu pour gérer les mises à jour et les vérifications de version. Ils ne sont pas destinés à une interaction directe avec le marchand.
    -   **Effet de la modification de ce paramètre :** La modification de ces paramètres pourrait interférer avec les notifications de mise à jour du module.
    -   **Valeur recommandée :** Laissez ces paramètres tels quels.
    -   **Scénario / exemple marchand :** Pas de scénario marchand ; ceux-ci sont pour la gestion interne du module.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | **Activé / Désactivé** | Activé | Interrupteur principal pour la fonctionnalité du module. |
| Configuration du module | **Que voulez-vous faire ?** | Bloquer l'accès | Définit si les règles bloquent l'accès ou autorisent l'accès UNIQUEMENT. |
| Configuration du module | **Sélectionner les pays** | (Aucun) | Pays affectés par la règle de restriction. |
| Configuration du module | **Sélectionner les catégories** | (Aucun) | Catégories dont les produits sont affectés par la règle. |
| Configuration du module | **Sélectionner le fabricant** | (Aucun) | Fabricants dont les produits sont affectés par la règle. |
| Configuration du module | **Exclure des groupes de clients** | (Aucun) | Groupes de clients exemptés des restrictions. |
| Configuration du module | **Exclure des clients** | (Aucun) | Clients individuels exemptés des restrictions. |
| Configuration du module | **Définir la priorité des méthodes d'identification d'origine** | Adresse de livraison, Géolocalisation, Pays du compte client | Ordre des méthodes pour déterminer le pays du client. |
| Configuration du module | **Utiliser l'adresse de livraison** | OUI | Prend en compte l'adresse de livraison pour l'application des restrictions. |
| Configuration du module | **Simuler la visite** | Désactivé | Active/désactive la simulation d'IP pour les tests. |
| Configuration du module | **Simuler l'IP** | (Vide) | Adresse IP/pays à simuler pour les tests. |
| Configuration du module | **Activer la liste blanche** | OUI | Active/désactive la liste blanche de géolocalisation de PrestaShop. |
| Configuration du module | **Liste blanche** | (Vide) | Liste d'adresses IP/plages pour contourner les restrictions. |

## 3. Dépannage marchand et Foire Aux Questions (FAQ)

**Q1 : Les produits sont toujours visibles dans un pays bloqué, que dois-je faire ?**
R1 : Tout d'abord, vérifiez la configuration de votre module :
\* Le module est-il « Activé » ?
\* Le paramètre « Que voulez-vous faire ? » est-il correctement défini (par exemple, « Bloquer l'accès » si vous voulez les masquer) ?
\* Les « Pays sélectionnés » sont-ils correctement choisis ?
\* Les « Catégories sélectionnées » ou « Fabricant sélectionné » sont-ils correctement appliqués aux produits en question ?
\* Si vous testez, assurez-vous que « Simuler la visite » est activé et que « Simuler l'IP » est défini sur le bon pays.
\* Enfin, videz le cache de votre PrestaShop (**Paramètres avancés > Performances > Vider le cache**) et le cache de votre navigateur.

**Q2 : Mon adresse IP semble être bloquée, même si je suis dans un pays autorisé.**
R2 : Cela peut arriver si votre IP est mal identifiée ou si vous avez fait une erreur dans votre configuration.
\* Vérifiez le paramètre « Liste blanche » et assurez-vous que l'adresse IP de votre bureau ou personnelle y est ajoutée si vous souhaitez contourner toutes les restrictions.
\* Vérifiez votre adresse IP publique réelle (vous pouvez utiliser des sites Web comme « quelle est mon IP »).
\* Assurez-vous que « Activer la liste blanche » est activé si vous utilisez la liste blanche de géolocalisation intégrée de PrestaShop.

**Q3 : Comment le module détermine-t-il le pays d'un client ?**
R3 : Le module utilise un système de priorité :
1.  **Adresse de livraison :** Si « Utiliser l'adresse de livraison » est activé et que le client a saisi une adresse de livraison dans le panier, celle-ci est priorisée.
2.  **Géolocalisation :** Il utilise l'adresse IP du client pour déterminer sa localisation géographique.
3.  **Pays du compte client :** Si le client est connecté, il utilise le pays enregistré dans son compte.
Vous pouvez ajuster la priorité de ces méthodes dans la configuration du module.

**Q4 : J'ai un thème personnalisé, ce module fonctionnera-t-il ?**
R4 : Oui, le module est conçu pour fonctionner avec les thèmes PrestaShop standard. Il filtre principalement les produits au niveau des données avant qu'ils ne soient rendus par le thème. Cependant, si votre thème personnalisé a une logique de liste de produits très inhabituelle ou surcharge les hooks d'affichage de produits PrestaShop, des ajustements mineurs pourraient être nécessaires. Si vous rencontrez des problèmes, contactez le support MyPresta.eu.

**Q5 : Puis-je restreindre l'accès à des produits spécifiques, pas seulement à des catégories ou des fabricants ?**
R5 : Oui, le module fonctionne en filtrant les produits. Bien que l'écran de configuration principal vous permette de sélectionner des catégories et des fabricants, la logique principale du module s'applique aux produits individuels. Vous pouvez laisser « Sélectionner les catégories » et « Sélectionner le fabricant » vides et gérer les restrictions directement sur les pages de produits individuels (si le module y ajoute un onglet, ce qui est courant pour de tels modules). *D'après les informations fournies, le module fonctionne en configurant des règles qui s'appliquent aux produits en fonction des catégories/fabricants sélectionnés dans la configuration principale. Il n'indique pas explicitement un onglet de configuration au niveau du produit, mais la description implique « chaque produit individuellement ». S'il n'y a pas d'onglet produit, la sélection de catégorie/fabricant est le moyen principal de cibler les produits.*

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Accès aux produits par pays » (`atpbc`) est construit comme un module PrestaShop standard, tirant parti du modèle MVC le cas échéant. Sa fonction principale est d'intercepter les requêtes de produits et de filtrer les résultats en fonction des restrictions par pays configurées et de la localisation identifiée du client. Il s'intègre au cœur de PrestaShop en se connectant à divers points d'affichage et d'action, en particulier ceux liés à la récupération et à l'affichage des produits. La géolocalisation est un composant clé, déterminant l'origine du client, qui est ensuite recoupée avec les règles du module.

### 4.2 Contrôleurs (`controllers/`)

Le module ne semble pas avoir de contrôleurs front-office ou back-office personnalisés dans son répertoire `controllers/` d'après l'inventaire fourni. Toute la configuration est gérée dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne semble pas avoir de classes personnalisées ou de définitions `ObjectModel` dans un répertoire `classes/`. La logique principale et la gestion des données sont probablement encapsulées dans le fichier `atpbc.php` principal, utilisant `Configuration` pour les paramètres et des requêtes directes à la base de données ou les classes `Product` et `Category` de PrestaShop pour la manipulation des données.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`atpbc/lib/searchTool/views/js/autocomplete.js`**
    -   **Portée :** Back-office.
    -   **Objectif :** Ce script fournit probablement une fonctionnalité d'autocomplétion pour les champs de saisie dans la configuration du module, tels que la sélection de clients, de catégories ou de fabricants. Il améliore l'expérience utilisateur en suggérant des options au fur et à mesure que l'administrateur tape, réduisant les erreurs et accélérant la configuration.
    -   **Fonctionnalité :** Lie des écouteurs d'événements à des champs de saisie spécifiques (`keyup`, `focus` par exemple), envoie des requêtes AJAX à un point de terminaison du back-office (probablement géré par le fichier principal du module ou un contrôleur d'administration PrestaShop) pour récupérer des suggestions, et affiche ces suggestions dans une liste déroulante. Il gère la sélection et le remplissage du champ de saisie.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`atpbc/lib/searchTool/views/css/autocomplete.css`**
    -   **Portée :** Style du formulaire d'administration du back-office.
    -   **Objectif :** Fournit le style pour la liste déroulante des suggestions d'autocomplétion et potentiellement les champs de saisie eux-mêmes, assurant une apparence cohérente et conviviale dans le back-office de PrestaShop.
    -   **Sélecteurs clés :** Cible probablement des classes comme `.autocomplete-suggestions`, `.autocomplete-suggestion-item`, `.autocomplete-input` pour contrôler la mise en page, les couleurs, les polices et les états de survol. Les développeurs peuvent les remplacer dans leur thème d'administration personnalisé ou en ajoutant du CSS avec une spécificité plus élevée.

### 4.6 Structure du template Smarty (`views/templates/`)

-   **`atpbc/lib/searchTool/views/scripts.tpl`**
    -   **Portée :** Back-office.
    -   **Objectif :** Ce template est probablement utilisé pour inclure le script `autocomplete.js` et potentiellement d'autres configurations JavaScript ou scripts en ligne pour la fonctionnalité `searchTool`. Il pourrait également définir des variables passées au JavaScript.
    -   **Rendu dans :** Probablement accroché à `actionAdminControllerSetMedia` ou directement inclus dans le template de configuration principal.
-   **`atpbc/views/templates/admin/AdminTab.tpl`**
    -   **Portée :** Back-office.
    -   **Objectif :** Ce template est probablement un template générique pour un onglet d'administration personnalisé ou une section dans la configuration du module. Il pourrait contenir la structure pour afficher des listes, des formulaires ou d'autres contenus administratifs.
    -   **Rendu dans :** Pourrait être inclus par `configuration.tpl` ou utilisé si le module avait un contrôleur d'administration dédié.
-   **`atpbc/views/templates/admin/button-subcategories.tpl`**
    -   **Portée :** Back-office.
    -   **Objectif :** Ce template rend probablement un bouton ou un élément d'interface utilisateur spécifiquement pour la gestion des sous-catégories dans la configuration du module, éventuellement pour le paramètre « Sélectionner les catégories » afin d'étendre/réduire les arborescences de catégories.
    -   **Rendu dans :** Dans `configuration.tpl` lors de l'affichage des options de sélection de catégorie.
-   **`atpbc/views/templates/admin/configuration.tpl`**
    -   **Portée :** Back-office.
    -   **Objectif :** C'est le template Smarty principal pour la page de configuration du module, rendu par la méthode `getContent()` dans `atpbc.php`. Il contient tous les formulaires HTML, les champs de saisie, les interrupteurs et les listes de sélection pour les paramètres du module.
    -   **Rendu dans :** Lors de l'accès à la page de configuration du module dans le Back Office de PrestaShop.
-   **`atpbc/views/templates/hook/displayHeader.tpl`**
    -   **Portée :** Front-office.
    -   **Objectif :** Ce template est accroché à `displayHeader`. Il est généralement utilisé pour inclure du CSS, du JavaScript ou des balises meta du front-office qui doivent être chargés tôt dans la page. Pour ce module, il pourrait inclure une logique pour détecter le pays du client ou configurer des variables côté client pour une utilisation ultérieure.
    -   **Rendu dans :** La section `<head>` de chaque page du front-office.
-   **`atpbc/views/templates/hook/displayHeaderNoAccess.tpl`**
    -   **Portée :** Front-office.
    -   **Objectif :** Ce template est probablement un fallback ou un affichage spécifique pour le cas où un client est détecté comme n'ayant « pas accès » à un produit ou une page particulière. Il pourrait contenir un script de redirection, un message ou un style spécifique pour masquer le contenu.
    -   **Rendu dans :** Potentiellement dans `displayHeader` ou un autre hook, conditionnellement aux restrictions d'accès.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :
    -   Le module utilise principalement la table `ps_configuration` de PrestaShop pour stocker ses paramètres (par exemple, `atpbc_EXCLUDE_GROUP`, `atpbc_EXCLUDE_CUSTOMER`, `atpbc_COUNTRY`, `atpbc_WTD`, `atpbc_MANUFACT`, `atpbc_CATEGORIES`, `atpbc_PRIORITY`, `atpbc_SIMULATE_ON`, `atpbc_SIMULATE_IP`, `atpbc_DELIVERY`, `atpbc_WHITELIST_ON`).
    -   Il ne semble pas créer de tables SQL personnalisées d'après l'inventaire fourni.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Avant le rendu du contenu d'un contrôleur d'administration, après la définition des médias. | Pour inclure du JS/CSS du back-office (par exemple, `autocomplete.js`, `autocomplete.css`) pour la page de configuration du module. |
| `actionDispatcherAfter` | Après que le dispatcher a traité une requête. | Potentiellement utilisé pour effectuer des redirections ou modifier la réponse en fonction des règles d'accès après qu'une page a été identifiée. |
| `displayFilterProductSearch` | Pendant le filtrage de la recherche de produits. | Pour modifier les résultats de la recherche de produits, en supprimant les produits restreints en fonction du pays. |
| `actionProductUpdate` | Après la mise à jour d'un produit dans le Back Office. | Pour potentiellement vider le cache lié à la disponibilité des produits ou réévaluer les règles pour le produit mis à jour. |
| `displayAdminProductsExtra` | Sur la page d'édition du produit dans le Back Office. | Pour ajouter des champs supplémentaires ou un onglet pour les règles d'accès spécifiques au produit (bien que non explicitement indiqué, c'est une utilisation courante de ce hook). |
| `actionCartSave` | Après l'enregistrement ou la mise à jour d'un panier. | Pour vérifier si les produits du panier sont autorisés pour le pays identifié du client (surtout si « Utiliser l'adresse de livraison » est activé). |
| `FilterProductSearch` | Pendant le filtrage de la recherche de produits (similaire à `displayFilterProductSearch`, souvent pour manipuler directement la requête). | Pour modifier la requête de base de données pour les recherches de produits, garantissant que les produits restreints ne sont pas récupérés. |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Pour inclure du JavaScript/CSS du front-office (par exemple, `displayHeader.tpl`, `displayHeaderNoAccess.tpl`) ou effectuer une détection précoce du pays. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support professionnel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe s'engage à garantir le fonctionnement optimal de votre module et à offrir la meilleure expérience possible pour votre boutique.
