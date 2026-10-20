---
title: "Flux de produits Pinterest - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop « Flux de produits Pinterest » par MyPresta.eu."
sidebar:
  label: "Flux de produits Pinterest - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Pinterest products feed sur MyPresta.eu](https://mypresta.eu/modules/social-networks/pinterest-products-feed.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/pinterest-products-feed/)
>
> ---


# Flux de produits Pinterest

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et assurent le bon fonctionnement des modules. Votre environnement d'hébergement doit également permettre une mémoire et un temps d'exécution suffisants pour générer de grands flux de produits, surtout si vous avez de nombreux produits.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

Le module « Flux de produits Pinterest » dispose d'un écran de configuration principal et d'un écran d'administration dédié à la gestion de vos flux de produits.

### 2.1 Page de configuration du module (Back Office > Modules > Gestionnaire de modules > Configurer Flux de produits Pinterest)

C'est l'écran de configuration principal où vous définissez les paramètres essentiels de votre flux de produits Pinterest.

#### Onglet Paramètres généraux

Cet onglet contient les paramètres fondamentaux pour la génération de votre flux de produits.

-   **Activer le flux Pinterest :**
    *   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité du module.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'activé (OUI) :* Le module générera le flux de produits et le rendra accessible via une URL.
        *   *Lorsqu'désactivé (NON) :* Le module ne générera ni ne mettra à jour le flux, et l'URL du flux deviendra inactive.
    *   **Valeur recommandée :** OUI (une fois que vous avez configuré les autres paramètres).
    *   **Scénario/exemple pour le marchand :** Vous êtes prêt à commencer à vendre sur Pinterest, vous l'activez donc après avoir configuré vos filtres de produits.
-   **Type de fichier de flux :**
    *   **Ce que fait ce paramètre :** Détermine le format du fichier de flux de produits. Pinterest prend en charge les formats CSV (Comma Separated Values) et XML (Extensible Markup Language).
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur CSV :* Le flux sera un fichier texte brut avec les données produit séparées par des virgules.
        *   *Lorsqu'il est défini sur XML :* Le flux sera un fichier structuré utilisant des balises XML.
    *   **Valeur recommandée :** XML (généralement plus robuste pour les données complexes, mais les deux fonctionnent avec Pinterest).
    *   **Scénario/exemple pour le marchand :** Pinterest recommande souvent le XML pour des données plus riches, vous pourriez donc choisir le XML pour une meilleure compatibilité et une meilleure pérennité.
-   **Langue par défaut pour le flux :**
    *   **Ce que fait ce paramètre :** Sélectionne la langue dans laquelle les noms de produits, les descriptions et autres données textuelles seront exportés dans le flux.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur Anglais :* Tout le texte du produit sera en anglais.
        *   *Lorsqu'il est défini sur Français :* Tout le texte du produit sera en français.
    *   **Valeur recommandée :** La langue principale de votre public cible sur Pinterest.
    *   **Scénario/exemple pour le marchand :** Si vous ciblez des clients en France, vous sélectionneriez le français. Si vous ciblez un public anglophone mondial, vous sélectionneriez l'anglais.
-   **Devise par défaut pour le flux :**
    *   **Ce que fait ce paramètre :** Sélectionne la devise dans laquelle les prix des produits seront exportés dans le flux.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur USD :* Tous les prix seront en dollars américains.
        *   *Lorsqu'il est défini sur EUR :* Tous les prix seront en euros.
    *   **Valeur recommandée :** La devise principale de votre marché cible sur Pinterest.
    *   **Scénario/exemple pour le marchand :** Si votre marché principal utilise l'euro, définissez-le sur EUR pour assurer un affichage correct des prix sur Pinterest.
-   **Pays par défaut pour le flux :**
    *   **Ce que fait ce paramètre :** Sélectionne le pays associé à vos produits dans le flux. Cela peut influencer les calculs d'expédition et de taxes du côté de Pinterest.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur États-Unis :* Les produits sont associés au marché américain.
        *   *Lorsqu'il est défini sur France :* Les produits sont associés au marché français.
    *   **Valeur recommandée :** Votre pays d'opération principal ou votre marché cible.
    *   **Scénario/exemple pour le marchand :** Si votre entreprise est basée en Allemagne et vend principalement à des clients allemands, vous sélectionneriez l'Allemagne.
-   **Transporteur par défaut pour le flux :**
    *   **Ce que fait ce paramètre :** Spécifie le transporteur par défaut à associer aux produits dans le flux. Cela peut être utilisé par Pinterest pour estimer les frais d'expédition.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur « Mon transporteur » :* Pinterest pourrait utiliser les règles d'expédition générales de ce transporteur (si disponibles) pour l'affichage.
    *   **Valeur recommandée :** Votre transporteur le plus couramment utilisé ou par défaut.
    *   **Scénario/exemple pour le marchand :** Si vous expédiez principalement avec FedEx, vous sélectionneriez FedEx ici.
-   **Inclure les déclinaisons de produits (variations) :**
    *   **Ce que fait ce paramètre :** Détermine si les déclinaisons de produits individuelles (comme différentes tailles ou couleurs d'une chemise) sont incluses comme des articles distincts dans le flux.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'activé (OUI) :* Chaque déclinaison (par exemple, « T-shirt rouge - Petit », « T-shirt rouge - Moyen ») sera une entrée distincte dans le flux.
        *   *Lorsqu'désactivé (NON) :* Seul le produit principal sera inclus, sans les déclinaisons individuelles.
    *   **Valeur recommandée :** OUI (si vous voulez que les clients voient et cliquent sur des déclinaisons spécifiques sur Pinterest).
    *   **Scénario/exemple pour le marchand :** Vous vendez des t-shirts de différentes tailles et couleurs. L'activation de cette option garantit que chaque combinaison unique de taille/couleur obtient sa propre épingle sur Pinterest, permettant aux clients de trouver exactement ce qu'ils recherchent.
-   **Exporter les produits avec un attribut spécifique (par exemple, Taille) :**
    *   **Ce que fait ce paramètre :** Vous permet de spécifier un attribut particulier (comme « Taille » ou « Couleur ») qui doit être inclus dans le flux de produits, souvent utilisé pour des données produit riches.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est sélectionné (par exemple, « Taille ») :* L'attribut de taille de vos produits sera explicitement inclus dans les données du flux.
        *   *Lorsqu'il n'est pas sélectionné :* Cet attribut spécifique ne sera pas explicitement exporté.
    *   **Valeur recommandée :** Sélectionnez un attribut crucial pour la différenciation des produits, comme « Taille » ou « Couleur ».
    *   **Scénario/exemple pour le marchand :** Si vous vendez des vêtements, la sélection de « Taille » garantit que Pinterest peut afficher les informations de taille directement sur l'épingle, améliorant l'expérience d'achat.
-   **Exporter les produits avec une caractéristique spécifique (par exemple, Matériau) :**
    *   **Ce que fait ce paramètre :** Similaire aux attributs, cela vous permet d'inclure une caractéristique de produit spécifique (comme « Matériau » ou « Marque ») dans le flux.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est sélectionné (par exemple, « Matériau ») :* La caractéristique de matériau de vos produits sera explicitement incluse dans les données du flux.
        *   *Lorsqu'il n'est pas sélectionné :* Cette caractéristique spécifique ne sera pas explicitement exportée.
    *   **Valeur recommandée :** Sélectionnez une caractéristique qui ajoute des informations précieuses pour les acheteurs, comme « Matériau », « Marque » ou « Style ».
    *   **Scénario/exemple pour le marchand :** Si vous vendez des meubles, la sélection de « Matériau » (par exemple, « Chêne », « Pin ») aide les clients à filtrer et à trouver des produits en fonction de leurs préférences.
-   **Exporter les produits avec une étiquette personnalisée spécifique (par exemple, Meilleure vente) :**
    *   **Ce que fait ce paramètre :** Vous permet d'inclure une étiquette personnalisée (si vous les avez définies dans PrestaShop) dans le flux. Celles-ci peuvent être utilisées pour des campagnes marketing spécifiques sur Pinterest.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'elle est sélectionnée (par exemple, « Meilleure vente ») :* Les produits avec cette étiquette personnalisée l'auront incluse dans leurs données de flux.
        *   *Lorsqu'elle n'est pas sélectionnée :* Les étiquettes personnalisées ne seront pas exportées.
    *   **Valeur recommandée :** Utilisez si vous avez des étiquettes spécifiques pour le marketing ou la catégorisation sur Pinterest.
    *   **Scénario/exemple pour le marchand :** Vous avez marqué certains produits comme « Meilleures ventes » dans PrestaShop. L'exportation de cette étiquette vous permet de créer des campagnes publicitaires Pinterest ciblant spécifiquement ces produits très performants.
-   **Exclure les produits par catégorie :**
    *   **Ce que fait ce paramètre :** Fournit un sélecteur arborescent pour choisir des catégories entières de produits que vous NE voulez PAS inclure dans votre flux Pinterest.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsque des catégories sont sélectionnées :* Tous les produits de ces catégories (et de leurs sous-catégories) seront exclus du flux généré.
        *   *Lorsque aucune catégorie n'est sélectionnée :* Tous les produits de toutes les catégories seront considérés pour l'exportation (sauf s'ils sont exclus par d'autres paramètres).
    *   **Valeur recommandée :** Excluez les catégories qui ne conviennent pas à Pinterest (par exemple, services, téléchargements numériques ou produits que vous ne souhaitez pas annoncer).
    *   **Scénario/exemple pour le marchand :** Vous vendez à la fois des produits physiques et des cartes-cadeaux numériques. Vous excluriez la catégorie « Cartes-cadeaux numériques » du flux, car Pinterest est principalement destiné aux produits physiques.
-   **Exclure des produits spécifiques :**
    *   **Ce que fait ce paramètre :** Vous permet de rechercher et de sélectionner des produits individuels que vous souhaitez explicitement exclure du flux Pinterest.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsque des produits sont sélectionnés :* Ces produits spécifiques n'apparaîtront pas dans le flux généré.
        *   *Lorsque aucun produit n'est sélectionné :* Tous les produits (non exclus par catégorie) seront considérés pour l'exportation.
    *   **Valeur recommandée :** Excluez les produits spécifiques qui sont en rupture de stock indéfiniment, abandonnés, ou pour toute autre raison pour laquelle vous ne les voulez pas sur Pinterest.
    *   **Scénario/exemple pour le marchand :** Un produit particulier est temporairement indisponible en raison d'un problème de fournisseur, vous l'excluez donc jusqu'à ce qu'il soit de nouveau en stock.
-   **Générer l'URL du flux :**
    *   **Ce que fait ce paramètre :** Affiche l'URL unique où votre flux de produits Pinterest peut être consulté. C'est l'URL que vous fournirez à Pinterest.
    *   **Effet de la modification de ce paramètre :** Il s'agit d'un champ d'affichage uniquement. L'URL change si vous modifiez le domaine de votre boutique ou les paramètres SSL.
    *   **Valeur recommandée :** Copiez cette URL et collez-la dans les paramètres de votre compte professionnel Pinterest lors de la configuration de votre catalogue de produits.
    *   **Scénario/exemple pour le marchand :** Après avoir configuré tous les paramètres, vous copiez cette URL et accédez à votre compte professionnel Pinterest pour configurer votre catalogue de produits, en collant cette URL dans le champ « Source de données ».
-   **Générer le flux (Bouton) :**
    *   **Ce que fait ce paramètre :** Déclenche manuellement le processus de génération du fichier de flux de produits.
    *   **Effet de la modification de ce paramètre :** Cliquer sur ce bouton créera ou mettra à jour immédiatement le fichier de flux en fonction de vos paramètres actuels. Cela peut prendre un certain temps pour les grands catalogues.
    *   **Valeur recommandée :** Cliquez sur ce bouton après avoir apporté des modifications à vos paramètres de flux ou lorsque vous souhaitez forcer une mise à jour immédiate.
    *   **Scénario/exemple pour le marchand :** Vous venez d'ajouter 50 nouveaux produits et souhaitez qu'ils apparaissent sur Pinterest dès que possible, vous cliquez donc sur « Générer le flux ».

#### Onglet Paramètres de la tâche Cron

Cet onglet fournit des informations pour automatiser le processus de génération du flux.

-   **URL de la tâche Cron :**
    *   **Ce que fait ce paramètre :** Affiche une URL spéciale qui, lorsqu'elle est visitée, déclenche automatiquement le processus de génération du flux sans que vous ayez à cliquer sur le bouton « Générer le flux » dans le back office.
    *   **Effet de la modification de ce paramètre :** Il s'agit d'un champ d'affichage uniquement.
    *   **Valeur recommandée :** Copiez cette URL et configurez-la comme une « tâche cron » sur le serveur de votre hébergement web.
    *   **Scénario/exemple pour le marchand :** Vous souhaitez que votre flux Pinterest soit mis à jour chaque nuit à 3h du matin. Vous copiez cette URL et configurez une tâche cron sur votre serveur pour visiter cette URL quotidiennement à 3h du matin.
-   **Comment configurer une tâche Cron :**
    *   **Ce que fait ce paramètre :** Fournit des instructions sur la façon de configurer une tâche automatisée (tâche cron) sur votre serveur web pour mettre à jour régulièrement votre flux de produits.
    *   **Effet de la modification de ce paramètre :** Il s'agit d'une section informative.
    *   **Valeur recommandée :** Suivez ces instructions ou fournissez-les à votre webmaster/support d'hébergement pour vous assurer que votre flux est toujours à jour.
    *   **Scénario/exemple pour le marchand :** Vous ne savez pas comment configurer une tâche cron. Cette section vous donne les étapes exactes ou les informations à transmettre à votre fournisseur d'hébergement.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### Tableau de bord des flux Pinterest (Back Office > Vendre > Flux Pinterest)

Cette section dédiée de votre back office PrestaShop offre une vue d'ensemble et une interface de gestion pour vos flux de produits Pinterest. Vous pouvez la trouver sous le menu « Vendre » dans PrestaShop 1.7/8/9.

-   **Nom de l'écran et emplacement du menu :** Flux Pinterest (sous « Vendre » dans le menu principal).
-   **Actions et paramètres disponibles :**
    *   **Tableau de liste des flux :** Ce tableau affiche tous les flux générés (si le module prend en charge plusieurs flux, sinon il affichera le principal). Il comprend généralement :
        *   **Nom/ID du flux :** Un identifiant unique pour le flux.
        *   **Langue :** La langue des produits dans le flux.
        *   **Devise :** La devise des prix dans le flux.
        *   **Dernière génération :** La date et l'heure de la dernière mise à jour du flux.
        *   **URL du flux :** Le lien direct vers le fichier de flux généré.
        *   **Actions :** Boutons pour afficher, télécharger ou régénérer le flux.
    *   **Ajouter un nouveau flux / Modifier un flux :** Bien que le module se concentre principalement sur un seul flux principal, cette interface pourrait permettre une expansion future ou des configurations de flux spécifiques. Pour l'instant, elle reflète largement les paramètres de la page de configuration principale.
    *   **Vue grille / gestion :** Cet écran offre un aperçu clair de l'état de votre flux et un accès rapide à son URL et à ses options de régénération.
-   **Effet des modifications :**
    *   *Régénérer un flux :* Met à jour le fichier de flux avec les dernières données produit de votre boutique, reflétant toute modification des informations produit, des prix ou des niveaux de stock.
    *   *Afficher l'URL du flux :* Vous permet de copier rapidement l'URL nécessaire pour Pinterest.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Vérifiez périodiquement ce tableau de bord pour vous assurer que votre flux est généré régulièrement (si vous avez configuré une tâche cron) et que l'horodatage « Dernière génération » est récent.
    2.  Si vous apportez des modifications importantes aux produits (par exemple, mises à jour de prix en masse, lancements de nouveaux produits), vous pouvez régénérer manuellement le flux à partir de cet écran ou de la configuration du module pour vous assurer que Pinterest reçoit les dernières données rapidement.
    3.  Copiez l'URL du flux à partir d'ici lors de la configuration initiale de votre compte professionnel Pinterest.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Activer le flux Pinterest | OUI | Active/désactive la génération du flux. |
| | Type de fichier de flux | XML | Définit le format de sortie du flux (CSV ou XML). |
| | Langue par défaut pour le flux | Votre langue principale | Langue des noms/descriptions de produits. |
| | Devise par défaut pour le flux | Votre devise principale | Devise des prix des produits. |
| | Pays par défaut pour le flux | Votre pays principal | Association de pays pour les produits. |
| | Transporteur par défaut pour le flux | Votre transporteur par défaut | Transporteur pour les estimations Pinterest. |
| | Inclure les déclinaisons de produits | OUI | Exporte les variations de produits individuelles. |
| | Exporter les produits avec un attribut spécifique | Sélectionnez l'attribut pertinent (par exemple, Taille) | Inclut des attributs de produit spécifiques dans le flux. |
| | Exporter les produits avec une caractéristique spécifique | Sélectionnez la caractéristique pertinente (par exemple, Matériau) | Inclut des caractéristiques de produit spécifiques dans le flux. |
| | Exporter les produits avec une étiquette personnalisée spécifique | Sélectionnez l'étiquette pertinente (par exemple, Meilleure vente) | Inclut des étiquettes personnalisées pour le marketing. |
| | Exclure les produits par catégorie | Sélectionnez les catégories à exclure | Empêche les produits des catégories choisies d'apparaître dans le flux. |
| | Exclure des produits spécifiques | Sélectionnez les produits individuels à exclure | Empêche des produits spécifiques d'apparaître dans le flux. |
| | Générer l'URL du flux | (Affichage uniquement) | L'URL à fournir à Pinterest pour récupérer votre flux. |
| | Générer le flux (Bouton) | Cliquez après les modifications | Déclenche manuellement la génération immédiate du flux. |
| **Onglet Paramètres de la tâche Cron** | URL de la tâche Cron | (Affichage uniquement) | URL pour la génération automatisée du flux via cron du serveur. |
| | Comment configurer une tâche Cron | Suivez les instructions | Guide pour la configuration des mises à jour automatisées du flux. |
| **Tableau de bord des flux Pinterest** | Tableau de liste des flux | (Vue) | Aperçu des flux générés, de leur statut et de leurs URL. |
| | Régénérer le flux (Action) | Cliquez au besoin | Met à jour le flux avec les dernières données de la boutique. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes produits n'apparaissent pas sur Pinterest après avoir configuré le flux. Que dois-je faire ?**
R1 : Tout d'abord, assurez-vous que le paramètre « Activer le flux Pinterest » dans la configuration du module est défini sur OUI. Ensuite, cliquez manuellement sur le bouton « Générer le flux » pour créer le fichier de flux initial. Ensuite, vérifiez que vous avez correctement copié et collé l'« URL de génération du flux » dans les paramètres du catalogue de produits de votre compte professionnel Pinterest. Pinterest peut prendre un certain temps (jusqu'à 24-48 heures) pour traiter un nouveau flux. Vérifiez également votre compte professionnel Pinterest pour tout message d'erreur lié au flux.

**Q2 : Les prix ou les niveaux de stock sur Pinterest sont obsolètes. Comment puis-je résoudre ce problème ?**
R2 : Cela signifie généralement que votre flux n'est pas mis à jour régulièrement. Assurez-vous d'avoir configuré la tâche cron sur votre serveur d'hébergement en utilisant l'« URL de la tâche Cron » fournie dans le module. Si la tâche cron est configurée, vérifiez qu'elle s'exécute correctement (votre hébergeur peut vous aider). Vous pouvez également régénérer manuellement le flux en cliquant sur le bouton « Générer le flux » dans la configuration du module pour forcer une mise à jour immédiate.

**Q3 : Certains de mes produits sont manquants dans le flux Pinterest.**
R3 : Accédez à la page de configuration du module et vérifiez les paramètres « Exclure les produits par catégorie » et « Exclure des produits spécifiques ». Vous avez peut-être involontairement exclu des catégories ou des produits individuels. Assurez-vous également que les produits ont des images valides, des prix et qu'ils sont définis comme « actifs » et « disponibles à la commande » dans votre boutique PrestaShop, car le module n'exporte généralement que les produits actifs et achetables.

**Q4 : Le processus de génération du flux prend beaucoup de temps ou expire.**
R4 : Si vous avez un très grand catalogue (des milliers de produits), la génération du flux peut être gourmande en ressources.
\* **Solution 1 :** Augmentez les paramètres `memory_limit` et `max_execution_time` de PHP dans le fichier `php.ini` de votre serveur. Votre hébergeur peut vous aider.
\* **Solution 2 :** Assurez-vous que votre tâche cron est configurée pour s'exécuter pendant les heures creuses afin de minimiser l'impact sur les performances de la boutique.
\* **Solution 3 :** Envisagez d'exclure les catégories ou les produits moins importants si la taille du flux est constamment un problème.

**Q5 : Les styles de mon thème personnalisé ne sont pas appliqués à l'interface d'administration du module.**
R5 : L'interface d'administration du module utilise ses propres CSS (`admin-app.css`, `admin-theme.css`). Ceux-ci sont distincts de votre thème front-office. Si vous souhaitez personnaliser l'apparence des pages du back-office du module, vous devrez remplacer ces fichiers CSS spécifiques ou ajouter du CSS personnalisé à votre back office PrestaShop. C'est généralement une tâche pour un développeur web.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une plongée approfondie dans la structure technique du module « Flux de produits Pinterest » pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module `pinterestfeed` suit un modèle MVC (Model-View-Controller) PrestaShop standard, avec des contrôleurs frontaux dédiés à la génération de flux et à l'exécution de tâches cron, et des contrôleurs d'administration pour la configuration et la gestion. Il s'appuie sur `ObjectModel` pour une persistance potentielle des données (bien qu'il se concentre principalement sur la génération dynamique de flux) et utilise des templates Smarty pour le rendu de la configuration du back-office et des vues d'information. La logique principale pour générer le flux selon les spécifications de Pinterest est encapsulée dans des classes d'aide dédiées.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs gèrent les requêtes publiques, principalement pour le flux lui-même et l'exécution des tâches cron.

-   `controllers/front/cron.php`
    *   **Nom de la classe et classe parente :** `PinterestFeedCronModuleFrontController` étendant `ModuleFrontController`.
    *   **Responsabilité :** Ce contrôleur est conçu pour être appelé par une tâche cron côté serveur. Lorsqu'il est accédé, il déclenche la classe `PinterestFeedGenerator` pour régénérer le flux de produits en fonction de la configuration actuelle du module. Il renvoie généralement un simple message de succès/échec ou enregistre le processus. Il ne rend pas de page visuelle.
-   `controllers/front/feed.php`
    *   **Nom de la classe et classe parente :** `PinterestFeedFeedModuleFrontController` étendant `ModuleFrontController`.
    *   **Responsabilité :** Ce contrôleur sert le fichier de flux de produits réel. Lorsqu'il est accédé via l'« URL de génération du flux », il lit le fichier de flux pré-généré (ou le génère s'il n'existe pas/est obsolète, selon l'implémentation) et affiche son contenu (CSV ou XML) avec les en-têtes HTTP appropriés (`Content-Type`).

#### Contrôleurs d'administration Back-Office

Ces contrôleurs gèrent la configuration du module et fournissent des interfaces administratives.

-   `controllers/admin/AdminExportProductsFeedPinterest.php`
    *   **Nom de la classe et classe parente :** `AdminExportProductsFeedPinterestController` étendant `ModuleAdminController`.
    *   **Nom de l'onglet et entité gérée :** Ce contrôleur est responsable du tableau de bord « Flux Pinterest » que l'on trouve sous le menu « Vendre ». Il gère l'affichage et les actions liées aux flux de produits générés. Il ne gère pas directement une entité `ObjectModel` spécifique, mais orchestre plutôt la génération et l'affichage des données liées au flux.
    *   **Clés de configuration principales utilisées :** `PS_LANG_DEFAULT`, `PS_CARRIER_DEFAULT`, `PS_COUNTRY_DEFAULT`, `PS_CURRENCY_DEFAULT` (pour les valeurs par défaut dans les formulaires), `pm_pinterestfeed_products`, `pm_export_size_attribute` (pour les paramètres spécifiques au module). Il utilise également `pf_tree` pour la sélection de catégorie et `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` pour la sélection de langue dans les formulaires.
-   `controllers/admin/index.php`
    *   **Nom de la classe et classe parente :** Ce fichier sert probablement de placeholder ou de simple redirection/point d'entrée pour la section d'administration, plutôt que d'un contrôleur à part entière. Dans PrestaShop, les fichiers `index.php` dans les sous-répertoires empêchent souvent l'affichage direct du répertoire. Son rôle principal est d'assurer la sécurité en empêchant l'accès direct au contenu du répertoire.

### 4.3 Classes et modèles principaux (`classes/`)

-   `classes/index.php`
    *   **Objectif :** Fichier de sécurité PrestaShop standard pour empêcher l'affichage direct du répertoire.
-   `classes/PinterestFeedGenerator.php`
    *   **Responsabilité :** C'est la classe logique principale pour la construction du flux de produits.
    *   **Interaction avec la base de données :** Interagit avec diverses tables principales de PrestaShop (par exemple, `ps_product`, `ps_product_lang`, `ps_image`, `ps_category`, `ps_attribute`, `ps_feature`, `ps_stock_available`) pour récupérer les données produit.
    *   **Extension `ObjectModel` :** N'étend pas `ObjectModel` directement, car son objectif est l'agrégation et le formatage des données plutôt que la persistance d'une seule entité.
    *   **Méthodes publiques clés :** Contient des méthodes pour récupérer les produits, gérer les déclinaisons, appliquer des filtres (catégories, produits spécifiques), formater les données selon les spécifications de Pinterest et écrire la sortie dans le type de fichier choisi (CSV/XML).
-   `classes/PinterestFeedSpec.php`
    *   **Responsabilité :** Cette classe définit probablement les champs requis et optionnels pour la spécification du flux de produits Pinterest. Elle agit comme une couche de mappage ou de validation pour garantir que le flux généré respecte les directives de Pinterest.
    *   **Interaction avec la base de données :** Aucune directement.
    *   **Extension `ObjectModel` :** N'étend pas `ObjectModel`.
    *   **Méthodes publiques clés :** Peut contenir des méthodes pour récupérer la liste des champs requis/optionnels, leurs types de données et toutes les règles de formatage spécifiques.

### 4.4 Assets JavaScript (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`
    *   **Portée :** Back-office.
    *   **Objectif :** Fournit une fonctionnalité d'autocomplétion, probablement pour la recherche et la sélection de produits ou de catégories dans les formulaires de configuration d'administration (par exemple, pour « Exclure des produits spécifiques »).
    *   **Écouteurs d'événements :** Se lie aux événements `keyup` ou `input` des champs de saisie pour déclencher des recherches AJAX.
    *   **Manipulation du DOM :** Affiche les résultats de recherche dans une liste déroulante, permet la sélection et met à jour les champs de saisie masqués.
-   `views/js/admin-app.js`
    *   **Portée :** Back-office.
    *   **Objectif :** JavaScript principal pour la configuration et le tableau de bord du back-office du module. Gère les soumissions de formulaires, les mises à jour dynamiques et potentiellement les appels AJAX pour l'état de la génération du flux.
    *   **Écouteurs d'événements :** Se lie aux événements `submit` des formulaires, aux événements `click` des boutons (par exemple, « Générer le flux ») et potentiellement aux événements `change` des listes déroulantes.
    *   **Manipulation du DOM :** Gère l'affichage des onglets de configuration, met à jour les messages d'état et interagit avec le composant d'autocomplétion.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `lib/searchTool/views/css/autocomplete.css`
    *   **Portée :** Style des formulaires d'administration du back-office.
    *   **Objectif :** Style l'entrée de recherche d'autocomplétion et ses résultats déroulants, assurant une apparence cohérente dans le back office de PrestaShop.
    *   **Sélecteurs de classes CSS clés :** `.autocomplete-container`, `.autocomplete-results`, `.autocomplete-item`.
-   `views/admin-theme.css`
    *   **Portée :** Style des formulaires d'administration du back-office.
    *   **Objectif :** Fournit un style général pour les pages de configuration du back-office du module, garantissant qu'il s'intègre bien au thème d'administration de PrestaShop.
    *   **Sélecteurs de classes CSS clés :** `.panel`, `.form-group`, `.control-label`, `.help-block`.
-   `views/css/admin-app.css`
    *   **Portée :** Style des formulaires d'administration du back-office.
    *   **Objectif :** Style spécifique pour les éléments et la mise en page personnalisés du module dans l'interface d'administration, tels que la navigation par onglets, les boutons personnalisés ou les blocs d'informations uniques.
    *   **Sélecteurs de classes CSS clés :** `.pinterestfeed-tabs`, `.pinterestfeed-panel`, `.pinterestfeed-alert`.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** : La description du module ne liste pas explicitement les templates de hook, ce qui suggère que sa présence en front-office se fait principalement via l'URL du flux, et non par affichage direct. S'il y en a, ils seraient pour des blocs d'information.
-   **Templates d'administration (`views/templates/admin/`)** :
    *   `views/templates/admin/dashboard.tpl` : Probablement le template principal pour le tableau de bord « Flux Pinterest », affichant la liste des flux, leur statut et les actions.
    *   `views/templates/admin/feeds.tpl` : Pourrait être un template partiel utilisé dans `dashboard.tpl` pour rendre le tableau des flux.
    *   `views/templates/admin/form-chrome.tpl` : Un template d'habillage générique pour les formulaires d'administration, fournissant le panneau et la structure de formulaire standard de PrestaShop.
    *   `views/templates/admin/layout.tpl` : Le template de mise en page principal pour la section d'administration du module, définissant la structure globale incluant l'en-tête, les onglets et la zone de contenu.
-   **Templates de configuration et d'utilitaires (`views/`)** :
    *   `views/categories-fancybox.tpl` : Template pour une modale Fancybox utilisée pour la sélection de catégorie (par exemple, pour l'exclusion).
    *   `views/custom-labels.tpl` : Template pour l'affichage ou la gestion des étiquettes personnalisées.
    *   `views/exclude-products.tpl` : Template pour l'interface de recherche et de sélection d'exclusion de produits.
    *   `views/google_lang_links.tpl` : Potentiellement pour afficher des liens ou des informations spécifiques à une langue, bien que son utilisation directe dans un module de flux Pinterest puisse être à des fins d'information.
    *   `views/returnAlert.tpl` : Un template générique pour afficher des alertes de succès ou d'erreur dans le back office.
    *   `views/script-fancybox.tpl` : Contient du JavaScript pour l'initialisation et la gestion des modales Fancybox.
    *   `views/script.tpl` : Extraits JavaScript généraux ou scripts d'initialisation pour les pages d'administration du module.
    *   `lib/searchTool/views/scripts.tpl` : Contient du JavaScript pour l'outil de recherche d'autocomplétion.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** :
    *   Le module ne semble pas créer ses propres tables SQL personnalisées d'après l'inventaire fourni.
    *   Il s'appuie fortement sur les tables principales existantes de PrestaShop : `ps_product`, `ps_product_lang`, `ps_image`, `ps_category`, `ps_category_product`, `ps_attribute_group`, `ps_attribute`, `ps_feature`, `ps_feature_product`, `ps_stock_available`, `ps_configuration` (pour les paramètres du module comme `PINTERESTFEED_ENABLED`, `PINTERESTFEED_FILE_TYPE`, etc.).
-   **Table des hooks enregistrés** :
    La fonction principale du module est la génération de flux, qui est généralement déclenchée par un accès direct au contrôleur (URL du flux, URL cron) ou des actions d'administration. Bien que la description du module mentionne « Hooks Front-Office : En-tête, Colonnes, Produit ou Pied de page », l'inventaire des fichiers et la description des fonctionnalités fournis suggèrent que ceux-ci ne sont pas activement utilisés pour l'affichage visuel par *ce module spécifique*. Au lieu de cela, le module enregistre probablement des hooks pour des processus internes ou des extensions futures potentielles.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | À chaque chargement de page en front-office. | Potentiellement pour ajouter du JS/CSS personnalisé si le module avait un composant front-office, ou pour un suivi interne. (Peu probable pour une sortie visuelle par ce module). |
| `displayRightColumn` | Dans la colonne de droite du front-office. | (Peu probable pour une sortie visuelle par ce module). |
| `displayLeftColumn` | Dans la colonne de gauche du front-office. | (Peu probable pour une sortie visuelle par ce module). |
| `displayFooter` | Dans le pied de page de chaque page en front-office. | (Peu probable pour une sortie visuelle par ce module). |
| `displayProductExtraContent` | Sur la page produit, sous le contenu principal. | (Peu probable pour une sortie visuelle par ce module). |
| `actionProductUpdate` | Après la mise à jour d'un produit en back-office. | Potentiellement pour marquer le flux comme nécessitant une régénération ou pour déclencher une mise à jour partielle. |
| `actionProductAdd` | Après l'ajout d'un nouveau produit. | Similaire à `actionProductUpdate`. |
| `actionProductDelete` | Après la suppression d'un produit. | Similaire à `actionProductUpdate`. |
| `actionUpdateQuantity` | Après la modification de la quantité de stock d'un produit. | Potentiellement pour déclencher la régénération du flux si les changements de stock sont critiques pour le flux. |
| `actionModuleInstall` | Lors de l'installation du module. | Pour créer des entrées de configuration et potentiellement le fichier de flux initial. |
| `actionModuleUninstall` | Lors de la désinstallation du module. | Pour nettoyer les entrées de configuration et les fichiers générés. |
| `displayAdminProductsExtra` | Sur la page d'édition de produit en back-office. | Pourrait être utilisé pour ajouter un onglet ou un champ spécifique lié aux paramètres du flux Pinterest pour les produits individuels. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour votre module « Flux de produits Pinterest », veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe est dédiée à assurer le fonctionnement parfait de votre module et à vous aider à atteindre vos objectifs e-commerce.

-   **Historique des commandes et téléchargements MyPresta.eu :** <https://mypresta.eu/my-account/orders/>
-   **Contact support MyPresta.eu :** <https://mypresta.eu/contact>
