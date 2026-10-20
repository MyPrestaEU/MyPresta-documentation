---
title: "Exporter les produits vers Delcampe Lister - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Exporter les produits vers Delcampe Lister' par MyPresta.eu."
sidebar:
  label: "Exporter les produits vers Delcampe Lister - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Export products to Delcampe Lister sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/export-products-to-delcampe-lister.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/export-products-to-delcampe-lister/)
>
> ---


# Exporter les produits vers Delcampe Lister

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour que PrestaShop fonctionne correctement et devraient être disponibles sur la plupart des environnements d'hébergement.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Vous pouvez accéder à cet écran en naviguant vers **Modules > Gestionnaire de modules** et en cliquant sur « Configurer » à côté de « Exporter les produits vers Delcampe Lister ».

Cet écran gère principalement les paramètres généraux du module, y compris les vérifications de mise à jour.

-   **Vérification des mises à jour en direct MyPresta.eu :**
    -   **Ce que fait ce paramètre :** Cette option contrôle si le module vérifie automatiquement les nouvelles versions et mises à jour disponibles sur MyPresta.eu.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Le module se connectera périodiquement à MyPresta.eu pour voir si une version plus récente est disponible. Cela vous aide à rester à jour avec les corrections de bugs et les nouvelles fonctionnalités.
        -   *Lorsqu'il est désactivé :* Le module ne vérifiera pas les mises à jour automatiquement. Vous devrez vérifier manuellement les mises à jour dans votre compte MyPresta.eu.
    -   **Valeur recommandée :** OUI
    -   **Scénario / exemple de marchand :** Garder cette option activée garantit que vous utilisez toujours la version la plus stable et la plus riche en fonctionnalités du module sans avoir à vous souvenir de vérifier manuellement.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 Gestion des produits Delcampe (Back Office > Catalogue > Produits Delcampe)

C'est l'écran de gestion principal pour vos exportations de produits Delcampe. Vous pouvez y accéder en naviguant vers **Catalogue > Produits Delcampe** dans le menu de votre Back Office PrestaShop.

Cet écran fournit une vue en grille de vos produits et vous permet de gérer leurs paramètres d'exportation pour Delcampe. Vous pouvez ajouter de nouveaux produits à la liste d'exportation, modifier ceux qui existent déjà et générer le fichier d'exportation.

**Actions et paramètres disponibles :**

-   **Tableau de liste des produits :** Ce tableau affiche tous les produits qui sont déjà configurés pour l'exportation Delcampe ou disponibles pour être configurés. Vous verrez des colonnes comme l'ID du produit, le nom et potentiellement leurs paramètres spécifiques à Delcampe.
-   **Ajouter un nouveau produit / Modifier un produit :**
    -   Cliquer sur « Ajouter un nouveau » ou modifier un produit existant ouvrira un formulaire où vous pourrez définir des paramètres de liste Delcampe spécifiques pour ce produit.
    -   **`category_id` (ID de catégorie Delcampe) :**
        -   **Ce que fait ce paramètre :** C'est l'ID de catégorie spécifique sur Delcampe où votre produit sera listé. Delcampe a sa propre structure de catégories, qui peut différer de celle de PrestaShop.
        -   **Effet de la modification de ce paramètre :** Des ID de catégorie incorrects entraîneront la liste de votre produit dans la mauvaise section sur Delcampe, ou potentiellement un échec de la liste.
        -   **Valeur recommandée :** L'ID numérique exact de la catégorie Delcampe cible.
        -   **Scénario / exemple de marchand :** Si vous vendez un timbre rare, vous trouverez l'ID de catégorie « Timbres » approprié sur Delcampe et le saisirez ici.
    -   **`title` (Titre de l'annonce Delcampe) :**
        -   **Ce que fait ce paramètre :** Le titre qui apparaîtra pour votre produit sur Delcampe. Cela peut être différent du nom de votre produit PrestaShop.
        -   **Effet de la modification de ce paramètre :** Un titre attrayant et riche en mots-clés peut améliorer considérablement la visibilité sur Delcampe.
        -   **Valeur recommandée :** Un titre descriptif, concis et optimisé pour les recherches Delcampe.
        -   **Scénario / exemple de marchand :** Au lieu de « Vieux Timbre », vous pourriez utiliser « Timbre Français Rare 1920 - Neuf - Excellent État ».
    -   **`description` (Description de l'annonce Delcampe) :**
        -   **Ce que fait ce paramètre :** La description détaillée du produit qui sera affichée sur votre annonce Delcampe.
        -   **Effet de la modification de ce paramètre :** Une description complète avec tous les détails pertinents aide les acheteurs à prendre des décisions éclairées et renforce la confiance.
        -   **Valeur recommandée :** Une description complète, pouvant inclure le contexte historique, l'état et les dimensions.
        -   **Scénario / exemple de marchand :** Copiez votre description PrestaShop, mais envisagez d'ajouter des détails ou un formatage spécifiques à Delcampe.
    -   **`personal_reference` (Votre référence interne) :**
        -   **Ce que fait ce paramètre :** Un champ facultatif pour votre propre numéro de suivi ou de référence interne pour le produit sur Delcampe.
        -   **Effet de la modification de ce paramètre :** Vous aide à faire correspondre les ventes Delcampe à votre système d'inventaire interne.
        -   **Valeur recommandée :** Votre référence produit ou SKU PrestaShop.
        -   **Scénario / exemple de marchand :** L'utilisation de votre SKU PrestaShop ici vous permet d'identifier rapidement le produit dans votre boutique lorsqu'une commande Delcampe arrive.
    -   **`currency` (Devise de l'annonce) :**
        -   **Ce que fait ce paramètre :** La devise dans laquelle le produit sera listé sur Delcampe.
        -   **Effet de la modification de ce paramètre :** Doit correspondre à une devise prise en charge par Delcampe.
        -   **Valeur recommandée :** Votre devise de vente principale (par exemple, EUR, USD).
        -   **Scénario / exemple de marchand :** Si vous vendez principalement en Euros, définissez ceci sur EUR.
    -   **`selling_type` (Type de vente Delcampe) :**
        -   **Ce que fait ce paramètre :** Définit comment le produit est vendu sur Delcampe (par exemple, enchère, prix fixe).
        -   **Effet de la modification de ce paramètre :** Détermine le processus d'achat pour les clients sur Delcampe.
        -   **Valeur recommandée :** Choisissez le type qui convient le mieux à votre produit et à votre stratégie de vente (par exemple, « Prix fixe » pour les articles standard, « Enchère » pour les articles rares).
        -   **Scénario / exemple de marchand :** Pour un objet de collection courant, le « Prix fixe » pourrait convenir. Pour un article vraiment unique, une « Enchère » pourrait générer des offres plus élevées.
    -   **`price` (Prix de départ / Prix fixe) :**
        -   **Ce que fait ce paramètre :** Le prix initial pour une enchère ou le prix fixe pour une vente directe.
        -   **Effet de la modification de ce paramètre :** Impacte directement le coût pour l'acheteur.
        -   **Valeur recommandée :** Votre prix de vente souhaité.
        -   **Scénario / exemple de marchand :** Pour un article à prix fixe, ce serait votre prix de détail. Pour une enchère, c'est l'enchère minimale.
    -   **`initial_quantity` (Quantité disponible) :**
        -   **Ce que fait ce paramètre :** Le nombre d'unités de ce produit que vous mettez à disposition sur Delcampe.
        -   **Effet de la modification de ce paramètre :** Détermine le nombre d'articles qu'un acheteur peut acheter.
        -   **Valeur recommandée :** Votre niveau de stock actuel pour le produit.
        -   **Scénario / exemple de marchand :** Si vous avez 5 exemplaires d'un timbre particulier, définissez ceci sur 5.
    -   **`minimum_bid_step` (Incrément d'enchère) :**
        -   **Ce que fait ce paramètre :** Pour les annonces de type enchère, cela définit le montant minimum par lequel une enchère doit augmenter.
        -   **Effet de la modification de ce paramètre :** Influence le comportement des enchères.
        -   **Valeur recommandée :** Un incrément raisonnable (par exemple, 0.50, 1.00).
        -   **Scénario / exemple de marchand :** Si défini sur 1.00, une enchère de 10.00 nécessiterait que l'enchère suivante soit d'au moins 11.00.
    -   **`renew_duration` (Durée de renouvellement automatique) :**
        -   **Ce que fait ce paramètre :** Si activé, cela spécifie la durée pendant laquelle une annonce invendue sera automatiquement renouvelée.
        -   **Effet de la modification de ce paramètre :** Maintient votre produit listé sur Delcampe sans intervention manuelle.
        -   **Valeur recommandée :** Une durée qui correspond à votre cycle de vente (par exemple, 7 jours, 14 jours).
        -   **Scénario / exemple de marchand :** Si un article ne se vend pas en 7 jours, il sera automatiquement remis en vente pour 7 jours supplémentaires.
    -   **`renew_total_count` (Limite de renouvellement automatique) :**
        -   **Ce que fait ce paramètre :** Le nombre maximum de fois qu'une annonce invendue sera automatiquement renouvelée.
        -   **Effet de la modification de ce paramètre :** Empêche la remise en vente indéfinie d'articles impopulaires.
        -   **Valeur recommandée :** Une limite raisonnable (par exemple, 3, 5).
        -   **Scénario / exemple de marchand :** Si un article ne se vend pas après 3 renouvellements, il sera retiré de Delcampe.
    -   **`shipping_model` (Modèle d'expédition Delcampe) :**
        -   **Ce que fait ce paramètre :** La méthode ou le modèle d'expédition que vous utilisez sur Delcampe. Cela doit correspondre à vos paramètres d'expédition préconfigurés sur Delcampe.
        -   **Effet de la modification de ce paramètre :** Détermine comment les frais d'expédition sont calculés et présentés à l'acheteur.
        -   **Valeur recommandée :** L'ID ou le nom de votre modèle d'expédition Delcampe préféré.
        -   **Scénario / exemple de marchand :** Si vous avez un modèle « Expédition internationale standard » configuré sur Delcampe, vous entreriez son identifiant ici.
    -   **`weight` (Poids du produit) :**
        -   **Ce que fait ce paramètre :** Le poids du produit, utilisé pour les calculs d'expédition sur Delcampe.
        -   **Effet de la modification de ce paramètre :** Crucial pour une estimation précise des frais d'expédition.
        -   **Valeur recommandée :** Le poids réel du produit.
        -   **Scénario / exemple de marchand :** Entrez « 0.1 » pour un timbre léger.
    -   **`lister_sale_end_time` (Heure de fin de vente) :**
        -   **Ce que fait ce paramètre :** L'heure spécifique de la journée à laquelle l'annonce se terminera.
        -   **Effet de la modification de ce paramètre :** Vous permet de planifier la fin de vos annonces.
        -   **Valeur recommandée :** Une heure où votre public cible est le plus susceptible d'être en ligne (par exemple, 20:00).
        -   **Scénario / exemple de marchand :** Terminer une enchère à 20h un dimanche pourrait attirer plus d'offres de dernière minute.
    -   **`lister_sale_end_day` (Jour de fin de vente) :**
        -   **Ce que fait ce paramètre :** Le jour spécifique de la semaine où l'annonce se terminera.
        -   **Effet de la modification de ce paramètre :** Vous permet de planifier la fin de vos annonces.
        -   **Valeur recommandée :** Un jour où votre public cible est le plus susceptible d'être en ligne (par exemple, dimanche).
        -   **Scénario / exemple de marchand :** Terminer une enchère un dimanche pourrait attirer plus d'offres de dernière minute.
    -   **`option_last_minute_extension` (Extension de dernière minute) :**
        -   **Ce que fait ce paramètre :** Si activé, prolonge la durée de l'enchère si une offre est placée dans les dernières minutes.
        -   **Effet de la modification de ce paramètre :** Empêche le « sniping » et encourage les offres plus élevées.
        -   **Valeur recommandée :** OUI (pour les enchères).
        -   **Scénario / exemple de marchand :** Une offre placée 30 secondes avant la fin d'une enchère prolongera l'enchère de quelques minutes, donnant aux autres une chance de surenchérir.
    -   **`option_anonymous_buyer` (Acheteur anonyme) :**
        -   **Ce que fait ce paramètre :** Cache l'identité de l'acheteur aux autres enchérisseurs lors d'une enchère.
        -   **Effet de la modification de ce paramètre :** Peut augmenter la confidentialité des enchérisseurs.
        -   **Valeur recommandée :** NON (sauf si des préoccupations spécifiques en matière de confidentialité sont primordiales).
        -   **Scénario / exemple de marchand :** Si vous souhaitez protéger la confidentialité de l'acheteur, activez cette option.
    -   **`option_strong_title` (Titre fort / Titre en gras) :**
        -   **Ce que fait ce paramètre :** Met votre titre d'annonce en gras sur Delcampe, augmentant sa visibilité.
        -   **Effet de la modification de ce paramètre :** Votre annonce se démarque davantage dans les résultats de recherche.
        -   **Valeur recommandée :** OUI.
        -   **Scénario / exemple de marchand :** L'utilisation d'un titre en gras aide votre annonce de timbre rare à attirer l'attention des collectionneurs qui parcourent de nombreux articles similaires.
    -   **`option_background_color` (Couleur de fond) :**
        -   **Ce que fait ce paramètre :** Définit une couleur de fond personnalisée pour votre annonce sur Delcampe.
        -   **Effet de la modification de ce paramètre :** Peut rendre votre annonce plus attrayante visuellement ou correspondre à votre marque.
        -   **Valeur recommandée :** Laisser vide ou utiliser une couleur subtile.
        -   **Scénario / exemple de marchand :** L'utilisation d'un fond bleu clair pourrait faire ressortir votre annonce sans être distrayante.
    -   **`option_border_color` (Couleur de bordure) :**
        -   **Ce que fait ce paramètre :** Définit une couleur de bordure personnalisée pour votre annonce sur Delcampe.
        -   **Effet de la modification de ce paramètre :** Peut rendre votre annonce plus attrayante visuellement ou correspondre à votre marque.
        -   **Valeur recommandée :** Laisser vide ou utiliser une couleur subtile.
        -   **Scénario / exemple de marchand :** Une bordure fine et sombre peut donner à votre annonce un aspect plus professionnel.

**Flux de travail recommandé pour la gestion quotidienne de la boutique :**

1.  **Identifier les produits pour Delcampe :** Décidez quels produits de votre boutique PrestaShop sont adaptés à la place de marché Delcampe.
2.  **Ajouter/Modifier des produits :** Allez dans **Catalogue > Produits Delcampe**. Utilisez le bouton « Ajouter un nouveau » ou modifiez les entrées existantes pour configurer les paramètres spécifiques à Delcampe pour chaque produit. Portez une attention particulière aux ID de catégorie Delcampe, aux prix et au type de vente.
3.  **Générer l'exportation :** Une fois vos produits configurés, le module vous permettra de générer le fichier d'exportation. Ce fichier contiendra toutes les données nécessaires dans un format que Delcampe Lister peut importer.
4.  **Importer dans Delcampe Lister :** Téléchargez le fichier généré et importez-le dans votre outil Delcampe Lister.
5.  **Surveiller et mettre à jour :** Gardez un œil sur vos annonces Delcampe et mettez à jour les configurations de produits dans PrestaShop si nécessaire (par exemple, pour les changements de prix, les mises à jour de stock).

#### 2.2.2 AdminDelcampeProductsController (delcampeproducts/controllers/admin/AdminDelcampeProducts.php)

Ce contrôleur est responsable de la gestion des listes de produits Delcampe dans le back office de PrestaShop. Il gère l'affichage de la liste des produits, ainsi que la création, la modification et la suppression des configurations de produits Delcampe individuelles.

#### 2.2.3 index.php (delcampeproducts/controllers/admin/index.php)

Ce fichier sert probablement de placeholder ou de simple redirection au sein de la structure du contrôleur d'administration, garantissant que la section d'administration du module est correctement initialisée ou routée. Il ne contient généralement pas d'options de configuration directes pour le marchand.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Vérification des mises à jour en direct MyPresta.eu | OUI | Contrôle les vérifications automatiques des mises à jour du module. |
| Gestion des produits Delcampe | ID de catégorie Delcampe (`category_id`) | (ID Delcampe spécifique) | Mappe le produit PrestaShop à une catégorie Delcampe. |
| Gestion des produits Delcampe | Titre de l'annonce Delcampe (`title`) | (Personnalisé) | Titre du produit affiché sur Delcampe. |
| Gestion des produits Delcampe | Description de l'annonce Delcampe (`description`) | (Personnalisé) | Description détaillée du produit pour Delcampe. |
| Gestion des produits Delcampe | Votre référence interne (`personal_reference`) | (SKU PrestaShop) | Suivi interne de vos produits. |
| Gestion des produits Delcampe | Devise de l'annonce (`currency`) | (Votre devise principale) | Devise pour l'annonce Delcampe. |
| Gestion des produits Delcampe | Type de vente Delcampe (`selling_type`) | (Prix fixe / Enchère) | Comment le produit est vendu sur Delcampe. |
| Gestion des produits Delcampe | Prix de départ / Prix fixe (`price`) | (Votre prix souhaité) | Prix pour la vente directe ou le début de l'enchère. |
| Gestion des produits Delcampe | Quantité disponible (`initial_quantity`) | (Votre niveau de stock) | Nombre d'unités disponibles sur Delcampe. |
| Gestion des produits Delcampe | Incrément d'enchère (`minimum_bid_step`) | (par exemple, 0.50, 1.00) | Montant minimum d'augmentation des enchères. |
| Gestion des produits Delcampe | Durée de renouvellement automatique (`renew_duration`) | (par exemple, 7 jours) | Durée de renouvellement d'une annonce invendue. |
| Gestion des produits Delcampe | Limite de renouvellement automatique (`renew_total_count`) | (par exemple, 3, 5) | Nombre maximal de renouvellements automatiques d'une annonce invendue. |
| Gestion des produits Delcampe | Modèle d'expédition Delcampe (`shipping_model`) | (ID/Nom du modèle Delcampe) | Méthode d'expédition utilisée sur Delcampe. |
| Gestion des produits Delcampe | Poids du produit (`weight`) | (Poids réel du produit) | Poids du produit pour les calculs d'expédition. |
| Gestion des produits Delcampe | Heure de fin de vente (`lister_sale_end_time`) | (par exemple, 20:00) | Heure spécifique de la journée pour la fin de l'annonce. |
| Gestion des produits Delcampe | Jour de fin de vente (`lister_sale_end_day`) | (par exemple, dimanche) | Jour spécifique de la semaine pour la fin de l'annonce. |
| Gestion des produits Delcampe | Extension de dernière minute (`option_last_minute_extension`) | OUI (pour les enchères) | Prolonge l'enchère si une offre est placée dans les dernières minutes. |
| Gestion des produits Delcampe | Acheteur anonyme (`option_anonymous_buyer`) | NON | Cache l'identité de l'acheteur dans les enchères. |
| Gestion des produits Delcampe | Titre fort / Titre en gras (`option_strong_title`) | OUI | Met le titre de l'annonce en gras sur Delcampe. |
| Gestion des produits Delcampe | Couleur de fond (`option_background_color`) | (Laisser vide ou subtil) | Couleur de fond personnalisée pour l'annonce. |
| Gestion des produits Delcampe | Couleur de bordure (`option_border_color`) | (Laisser vide ou subtil) | Couleur de bordure personnalisée pour l'annonce. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes produits n'apparaissent pas sur Delcampe après l'exportation. Que dois-je vérifier ?**
R :

1.  **Avez-vous terminé l'importation sur Delcampe Lister ?** Ce module ne fait qu'*exporter* les données. Vous devez toujours télécharger le fichier généré et l'*importer* dans votre outil Delcampe Lister.
2.  **Vérifiez les ID de catégorie Delcampe :** Assurez-vous que le `category_id` que vous avez saisi pour chaque produit est correct et existe sur Delcampe. Des ID incorrects peuvent entraîner des échecs d'importation.
3.  **Examinez les erreurs de Delcampe Lister :** Lorsque vous importez le fichier dans Delcampe Lister, il fournit généralement des commentaires ou des messages d'erreur si quelque chose s'est mal passé. Vérifiez ces messages pour des indices.
4.  **Statut du produit :** Assurez-vous que les produits sont actifs et en stock dans votre boutique PrestaShop si vous avez configuré le module pour n'exporter que les articles actifs/en stock.

**Q : Comment gérer les mises à jour de produits (changements de prix, changements de stock) sur Delcampe ?**
R : Vous devrez réexporter et réimporter les données de produit mises à jour dans Delcampe Lister. Le module génère un nouveau fichier d'exportation basé sur vos données de produit PrestaShop actuelles et les paramètres spécifiques à Delcampe que vous avez configurés. Delcampe Lister gère généralement les mises à jour des annonces existantes lorsque vous importez un fichier avec des identifiants de produit correspondants.

**Q : Le fichier d'exportation semble vide ou incomplet.**
R :

1.  **Configuration du produit :** Vérifiez que vous avez bien configuré des produits pour l'exportation Delcampe sous **Catalogue > Produits Delcampe**. Si aucun produit n'est configuré, l'exportation sera vide.
2.  **Paramètres du module :** Examinez tous les paramètres généraux du module (le cas échéant) qui pourraient filtrer les produits, tels que « exporter uniquement les produits actifs » ou « exporter uniquement les produits en stock ».
3.  **Cache PrestaShop :** Parfois, vider votre cache PrestaShop (**Paramètres avancés > Performances > Vider le cache**) peut résoudre un comportement inattendu avec la génération de données.

**Q : Mon thème personnalisé cause des problèmes d'affichage dans la configuration du back-office du module.**
R : L'interface du back-office de ce module utilise des composants PrestaShop standard, elle devrait donc généralement être compatible. Si vous rencontrez des problèmes de style, il s'agit probablement d'un conflit avec les surcharges du back-office de votre thème personnalisé.

1.  **Vérifiez les surcharges :** Si votre thème a un dossier `admin` avec des surcharges de modèle, renommez-le temporairement pour voir si le problème est résolu.
2.  **Contactez le développeur du thème :** Si le problème persiste, contactez le développeur de votre thème pour obtenir de l'aide, car il pourrait avoir besoin d'ajuster son CSS pour s'adapter aux interfaces de module standard.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Exporter les produits vers Delcampe Lister » suit une architecture de module PrestaShop standard, tirant principalement parti des contrôleurs d'administration pour son interface back-office et sa gestion des données. Il ne repose pas fortement sur les composants front-office pour l'interaction directe avec les clients, mais utilise des hooks pour s'intégrer dans le cycle de vie de PrestaShop. La fonctionnalité principale tourne autour de la gestion des paramètres d'exportation Delcampe spécifiques aux produits et de la génération d'un flux de données pour l'outil Delcampe Lister.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    -   `controllers/front/feed.php`
        -   **Nom de la classe et classe parente** : `DelcampeproductsFeedModuleFrontController` étendant `ModuleFrontController`.
        -   **Responsabilité** : Ce contrôleur est probablement responsable de la génération du flux de produits Delcampe réel (par exemple, XML, CSV) que le marchand téléchargerait. Il interrogerait les produits configurés et formaterait leurs données selon les spécifications de Delcampe. Il répond à une route front-office spécifique, bien qu'il ne soit pas directement visible par l'utilisateur final naviguant dans la boutique.
    -   `controllers/front/index.php`
        -   **Nom de la classe et classe parente** : `DelcampeproductsIndexModuleFrontController` étendant `ModuleFrontController`.
        -   **Responsabilité** : Cela pourrait servir de contrôleur frontal par défaut ou de secours, ou il pourrait être utilisé pour une simple redirection. Dans de nombreux modules, si `feed.php` gère l'interaction front-office principale (génération du flux), `index.php` pourrait être minimal ou inutilisé.
-   **Contrôleurs d'administration Back-Office** :

    -   `controllers/admin/AdminDelcampeProducts.php`
        -   **Nom de la classe et classe parente** : `AdminDelcampeProductsController` étendant `ModuleAdminController`.
        -   **Nom de l'onglet et entité gérée** : Ce contrôleur gère la section « Produits Delcampe » sous le menu « Catalogue » dans le Back Office de PrestaShop. Il est responsable de la liste, de l'ajout, de la modification et de la suppression de la configuration spécifique à Delcampe pour chaque produit. Il utilise `HelperList` et `HelperForm` de PrestaShop pour afficher la grille des produits et le formulaire de configuration détaillé.
    -   `controllers/admin/index.php`
        -   **Nom de la classe et classe parente** : Pas une classe de contrôleur complète, généralement un simple fichier `index.php` pour empêcher la liste des répertoires ou pour inclure le fichier de module principal pour le contexte. Il ne définit pas de classe de contrôleur d'administration distincte.

### 4.3 Classes et modèles principaux (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que le module pourrait stocker ses paramètres d'exportation de produits personnalisés directement dans la table `ps_configuration` ou étendre dynamiquement les classes `ObjectModel` PrestaShop existantes (comme `Product`), ou utiliser une interaction de base de données plus directe au sein du contrôleur. Compte tenu des champs de formulaire détaillés, il est très probable que les paramètres Delcampe spécifiques aux produits soient stockés dans `ps_configuration` avec des clés comme `dp_export_categories` ou directement dans la logique de `AdminDelcampeProductsController`.

### 4.4 Actifs JavaScript (`views/js/`)

-   `delcampeproducts/lib/js/admin/delcampeproducts.js`
    -   **Portée** : Back-office.
    -   **Détails** : Ce script est chargé dans le Back Office de PrestaShop, spécifiquement pour le contrôleur `AdminDelcampeProducts`. Il gère probablement :
        -   Le comportement dynamique des formulaires (par exemple, afficher/masquer des champs en fonction du `selling_type`).
        -   Les appels AJAX pour enregistrer les paramètres ou générer le fichier d'exportation.
        -   La validation ou le formatage des entrées pour des champs comme `category_id`, `price`, `weight`.
        -   Tout élément interactif dans les formulaires de configuration de produit ou la grille de liste.
        -   Utilise potentiellement jQuery pour la manipulation du DOM et la gestion des événements.

### 4.5 Feuilles de style CSS (`views/css/`)

Le dossier du module n'indique aucun fichier CSS personnalisé. Cela implique que le module s'appuie entièrement sur le style par défaut du Back Office de PrestaShop pour ses formulaires et listes de configuration, garantissant une apparence cohérente avec le reste du panneau d'administration. Les développeurs souhaitant styliser l'interface d'administration du module devraient cibler les classes CSS PrestaShop existantes ou injecter du CSS personnalisé via le hook `actionAdminControllerSetMedia`.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** : Aucun explicitement listé, mais les modules utilisent souvent `displayAdminProductsExtra` ou similaire pour les onglets de page produit.
-   **Modèles d'administration (`views/templates/admin/`)** :
    -   `delcampeproducts/script.tpl`
        -   **Portée** : Back-office.
        -   **Détails** : Ce modèle est probablement utilisé pour générer des variables JavaScript ou des scripts en ligne nécessaires à `delcampeproducts.js`. Il pourrait transmettre des valeurs de configuration de PHP à JavaScript, ou définir des objets JS globaux. Il est souvent rendu via le hook `actionAdminControllerSetMedia`.
-   **Modèles Front-office (`views/templates/front/`)** : Aucun explicitement listé, ce qui correspond à la nature d'exportation en arrière-plan du module.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module stocke probablement ses paramètres de configuration dans la table `ps_configuration` en utilisant des clés telles que `dp_export_categories`, `dp_remember_settings`, `dp_option_homepage_promotion`, `dp_lister_status`, `dp_lister_creation_date`, `dp_lister_sending_date`, `dp_llister_sending_date`, `dp_lister_edit_date`, `dp_export_format`, `dp_export_active`, `dp_export_instock`, `dp_export_identification`, `dp_export_category`, `dp_export_manufacturers_default`.
    -   Pour les paramètres Delcampe spécifiques aux produits (comme `category_id`, `title`, `price`, etc.), étant donné qu'aucun `ObjectModel` personnalisé n'est listé, ceux-ci sont probablement stockés soit comme données sérialisées dans `ps_configuration` (moins idéal pour les paramètres par produit) soit, plus probablement, le `AdminDelcampeProductsController` gère directement une table de base de données personnalisée (par exemple, `ps_delcampe_product_settings`) qui n'a pas été explicitement identifiée dans le dossier mais serait une approche standard pour des données aussi détaillées par produit. Si aucune table personnalisée n'existe, il pourrait utiliser `Product::addFeature` ou `Product::addCustomization` d'une manière non standard, ou stocker des données dans `ps_product_lang` ou `ps_product_shop` via des surcharges. **(Note du développeur : Rechercher dans la base de données une table `ps_delcampe_product_settings` ou similaire lors de l'installation.)**
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionProductUpdate` | Après la mise à jour d'un produit dans le Back Office. | Permet au module de réagir aux changements de produit (par exemple, mettre à jour ses données d'exportation Delcampe internes, marquer un produit pour une nouvelle exportation). |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration est chargé et que ses médias (JS/CSS) sont définis. | Utilisé pour injecter le JavaScript personnalisé du module (`delcampeproducts.js`) et potentiellement des scripts en ligne (`script.tpl`) dans les pages du Back Office, en particulier pour le contrôleur `AdminDelcampeProducts`. |
| `displayAdminProductsExtra` | (Implicite, souvent utilisé pour les onglets de produit) | Si le module ajoute un onglet à la page d'édition de produit pour les paramètres Delcampe, ce hook serait utilisé. (Non explicitement listé comme un hook, mais courant pour une telle fonctionnalité). |
| `displayBackOfficeHeader` | Dans l'en-tête de chaque page du Back Office. | Peut être utilisé pour le JS/CSS global côté administration ou pour afficher des notifications. |
| `moduleRoutes` | Pendant la génération des routes pour le module. | Utilisé pour définir des URL front-office personnalisées pour des contrôleurs comme `feed.php`. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et un support complet pour le module « Exporter les produits vers Delcampe Lister », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support dédiée est disponible pour vous aider avec tout problème technique ou question concernant la fonctionnalité du module.
"""
