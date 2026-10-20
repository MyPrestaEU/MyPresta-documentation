---
title: "Quantité maximale de produit disponible à l'achat par date - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Quantité maximale de produit disponible à l'achat par date' par MyPresta.eu."
sidebar:
  label: "Quantité maximale de produit disponible à l'achat par date"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Maximum available product quantity to purchase by date sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-available-product-quantity-to-purchase-by-date.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/maximum-available-product-quantity-to-purchase-by-date/)
>
> ---


# Quantité maximale de produit disponible à l'achat par date

## 1. Exigences et compatibilité
- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises, lesquelles sont généralement disponibles sur la plupart des environnements d'hébergement compatibles PrestaShop.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
C'est l'écran de configuration initial que vous rencontrez après l'installation du module ou en cliquant sur "Configurer" depuis le Gestionnaire de modules.

-   **Ce que fait ce paramètre :** Cette page contient généralement un simple interrupteur pour activer ou désactiver la fonctionnalité globale du module.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé :* Le module vérifiera et appliquera activement les limites de quantité de produit que vous définissez.
    -   *Lorsqu'il est désactivé :* Le module sera inactif et aucune limite de quantité ne sera appliquée, quelles que soient les règles que vous avez configurées.
-   **Valeur recommandée :** "OUI" (Activé) pour s'assurer que le module est actif et applique vos règles de quantité.
-   **Scénario / exemple de marchand :** Après l'installation, vous devez vous assurer que ce paramètre est activé pour commencer à utiliser les fonctionnalités du module. Si vous avez besoin de suspendre temporairement toutes les limites de quantité (par exemple, pendant une fenêtre de maintenance du site), vous pouvez le désactiver ici.

### 2.2 Écran d'administration dédié : Limite de quantité d'achat de produit par date (Back Office > Catalogue > Limite de quantité d'achat de produit par date)
C'est le centre névralgique pour créer, gérer et réviser toutes vos limites de quantité de produit basées sur des dates.

**Nom de l'écran et emplacement du menu :**
Vous pouvez accéder à cet écran en naviguant vers **Catalogue > Limite de quantité d'achat de produit par date** dans le menu de votre Back Office PrestaShop.

**Actions et paramètres disponibles :**
Cet écran affiche une liste de toutes les règles de limite de quantité existantes. À partir de là, vous pouvez ajouter de nouvelles règles, modifier celles qui existent ou les supprimer.

#### **Colonnes du tableau de liste :**
-   **ID :** Un identifiant interne unique pour chaque règle de limite de quantité spécifique. Utile pour la référence technique.
-   **Produit :** Le nom du produit auquel cette règle spécifique s'applique. Cela vous aide à identifier rapidement quel produit est limité.
-   **Date de début :** La date et l'heure exactes (par exemple, "2024-08-01 09:00:00") à partir desquelles cette limite de quantité commence à être appliquée.
-   **Date de fin :** La date et l'heure exactes (par exemple, "2024-08-07 17:00:00") auxquelles cette limite de quantité cesse d'être appliquée.
-   **Quantité :** Le nombre maximal d'unités du produit spécifié qu'un client peut acheter pendant la période "Date de début" et "Date de fin".
-   **Actif :** Un simple indicateur "Oui" ou "Non" (souvent un interrupteur à bascule) indiquant si la règle est actuellement activée.

#### **Ajouter / Modifier une règle de limite de quantité :**
Lorsque vous cliquez sur le bouton "Ajouter nouveau" ou cliquez pour modifier une règle existante, un formulaire apparaîtra avec les champs suivants :

-   **Limite de quantité d'achat de produit par date :** C'est le titre du formulaire, indiquant que vous définissez une nouvelle limite ou modifiez une limite existante.
-   **ID Produit :**
    -   **Ce que fait ce paramètre :** C'est un champ de recherche où vous tapez le nom ou l'ID du produit auquel vous souhaitez appliquer la limite. Au fur et à mesure que vous tapez, des suggestions apparaîtront, vous permettant de sélectionner le bon produit.
    -   **Effet de la modification de ce paramètre :** Lie directement cette règle de limite de quantité à un produit spécifique de votre catalogue.
    -   **Valeur recommandée :** Sélectionnez toujours le produit exact que vous avez l'intention de limiter.
    -   **Scénario / exemple de marchand :** Vous organisez une promotion spéciale sur les "Grains de café bio". Vous taperiez "Grains de café bio" et le sélectionneriez dans la liste déroulante.
-   **Date de début :**
    -   **Ce que fait ce paramètre :** Vous permet de choisir la date et l'heure exactes du calendrier à partir desquelles cette restriction de quantité doit commencer. Il comprend généralement un sélecteur de date et un sélecteur d'heure.
    -   **Effet de la modification de ce paramètre :** Le module ne commencera à appliquer la limite de quantité que pour les achats effectués à partir de cette date et heure spécifiques.
    -   **Valeur recommandée :** Définissez-la au début exact de votre période promotionnelle ou lorsque la restriction doit prendre effet.
    -   **Scénario / exemple de marchand :** Vous souhaitez qu'une limite commence au début d'une journée ouvrable, vous la définissez donc sur "2024-09-01 00:00:00".
-   **Date de fin :**
    -   **Ce que fait ce paramètre :** Vous permet de choisir la date et l'heure exactes du calendrier auxquelles cette restriction de quantité doit se terminer. Similaire à "Date de début", il comprend un sélecteur de date et un sélecteur d'heure.
    -   **Effet de la modification de ce paramètre :** Après cette date et heure spécifiques, la limite de quantité définie dans cette règle ne sera plus active, et les clients pourront acheter n'importe quel stock disponible.
    -   **Valeur recommandée :** Définissez-la à la fin exacte de votre période promotionnelle ou lorsque la restriction doit être levée.
    -   **Scénario / exemple de marchand :** Vous souhaitez que la limite se termine à la fin d'une journée ouvrable, vous la définissez donc sur "2024-09-07 23:59:59".
-   **Quantité :**
    -   **Ce que fait ce paramètre :** C'est un champ de saisie numérique où vous spécifiez le nombre maximal d'unités du produit sélectionné qu'un seul client peut acheter dans la plage "Date de début" et "Date de fin" définie.
    -   **Effet de la modification de ce paramètre :** Cette valeur est le cœur de la restriction. Si un client tente d'ajouter plus que cette quantité à son panier (ou en a déjà plus dans son panier) pendant la période active, le module interviendra.
    -   **Valeur recommandée :** La quantité maximale spécifique que vous souhaitez autoriser. Par exemple, "1" pour une limite d'un par client, ou "10" pour une limite d'achat en gros.
    -   **Scénario / exemple de marchand :** Pour assurer une distribution équitable d'un article en édition limitée, vous définissez la quantité à "2" par client.
-   **Actif (interrupteur On/Off) :**
    -   **Ce que fait ce paramètre :** C'est un interrupteur à bascule (souvent étiqueté "On" et "Off") qui contrôle si cette règle de limite de quantité spécifique est actuellement active et appliquée par le module.
    -   **Effet de la modification de ce paramètre :**
        -   *On :* La règle est active et appliquera sa limite de quantité pendant sa plage de dates spécifiée.
        -   *Off :* La règle est inactive et n'appliquera aucune limite de quantité, même si sa plage de dates est actuelle. Ceci est utile pour préparer des règles à l'avance ou les suspendre temporairement sans les supprimer.
    -   **Valeur recommandée :** "On" pour les règles que vous souhaitez activer, "Off" pour les règles que vous préparez ou avez temporairement suspendues.
    -   **Scénario / exemple de marchand :** Vous avez créé une règle pour une vente de vacances, mais les vacances sont encore dans un mois. Vous pouvez la définir sur "Off" jusqu'à ce que la date approche, puis la basculer sur "On" lorsque vous êtes prêt.
-   **Bouton Enregistrer :**
    -   **Ce que fait ce paramètre :** Valide toutes les modifications que vous avez apportées au formulaire dans la base de données.
    -   **Effet de la modification de ce paramètre :** La nouvelle règle de limite de quantité ou la règle mise à jour sera immédiatement appliquée à l'application des quantités de produits de votre boutique.

**Effet des modifications :**
-   **Ajout d'une nouvelle règle :** Une nouvelle restriction sera créée. Si elle est marquée "Active" et dans sa plage de dates, elle commencera immédiatement à limiter les achats pour le produit spécifié.
-   **Modification d'une règle existante :** Toute modification du produit, des dates, de la quantité ou du statut actif sera instantanément reflétée dans la manière dont le module applique les limites.
-   **Suppression d'une règle :** La limite de quantité sera définitivement supprimée, et le produit ne sera plus soumis à cette restriction spécifique pour cette plage de dates.

**Flux de travail recommandé pour la gestion quotidienne du magasin :**
1.  **Identifier les produits à limiter :** Déterminez quels produits nécessitent des restrictions de quantité (par exemple, les nouveautés, les articles en solde, les produits très demandés).
2.  **Définir les paramètres :** Pour chaque produit, décidez de la quantité maximale, ainsi que des dates et heures de début et de fin précises de la restriction.
3.  **Créer des règles :** Naviguez vers **Catalogue > Limite de quantité d'achat de produit par date** et cliquez sur "Ajouter nouveau". Remplissez soigneusement tous les champs, en vous assurant que les dates et heures sont exactes. Définissez "Actif" sur "On".
4.  **Vérifier et tester :** Après avoir créé les règles, testez-les sur votre front office (par exemple, essayez d'ajouter plus que la quantité autorisée à votre panier) pour vous assurer qu'elles fonctionnent comme prévu.
5.  **Surveiller et ajuster :** Gardez un œil sur vos ventes et votre inventaire. Si une promotion est prolongée ou si le stock change, mettez à jour les champs "Date de fin" ou "Quantité" de vos règles si nécessaire. Utilisez le bouton "Actif" pour désactiver temporairement les règles sans les supprimer si les circonstances changent.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue                                       | Paramètre / Option                     | Valeur par défaut / Recommandée | Objectif et impact
