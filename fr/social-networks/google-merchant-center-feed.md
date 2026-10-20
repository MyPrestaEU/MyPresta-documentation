---
title: "Flux Google Merchant Center - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Flux Google Merchant Center' par MyPresta.eu."
sidebar:
  label: "Flux Google Merchant Center - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Google merchant center feed sur MyPresta.eu](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/google-merchant-center-feed/)
>
> ---


# Flux Google Merchant Center

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL). Des ressources serveur suffisantes (CPU, RAM) peuvent être nécessaires pour générer de très grands flux de produits, en particulier pour les boutiques avec des dizaines de milliers de produits.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal du module, accessible immédiatement après l'installation ou en cliquant sur « Configurer » depuis le Gestionnaire de modules.

-   **Ce que fait ce paramètre :** Cette option contrôle si un sélecteur d'arborescence de catégories est affiché sur l'écran d'exportation des produits, vous permettant d'inclure ou d'exclure des produits en fonction de leur catégorie.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'activé (coché) :* Sur l'écran d'exportation des produits (`AdminExportProductsFeedGoogle`), vous verrez une arborescence visuelle des catégories de votre boutique. Cela vous permet de sélectionner facilement les catégories de produits qui doivent être incluses ou exclues de votre flux Google Merchant Center. C'est crucial pour filtrer votre flux afin d'inclure uniquement les produits pertinents ou d'exclure des catégories spécifiques que vous ne souhaitez pas annoncer sur Google.
    *   *Lorsqu'désactivé (décoché) :* Le sélecteur d'arborescence de catégories n'apparaîtra pas sur l'écran d'exportation. Cela signifie que vous ne pourrez pas filtrer les produits par catégorie directement dans l'interface du module. Vous exporteriez alors tous les produits, ou vous vous baseriez sur d'autres options de filtrage si disponibles (par exemple, des exclusions spécifiques aux produits).
-   **Valeur recommandée :** **OUI (coché)**.
-   **Scénario / exemple de marchand :** Vous vendez à la fois des vêtements et des téléchargements numériques. Vous ne souhaitez annoncer que vos produits vestimentaires sur Google Shopping. En activant « Afficher l'arborescence des catégories », vous pouvez facilement sélectionner uniquement vos catégories « Vêtements » pour les inclure dans le flux, en excluant votre catégorie « Téléchargements numériques ».

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### AdminExportProductsFeedGoogleController (Back Office > Modules > Flux Google Merchant Center > Exporter le flux de produits)

C'est l'écran principal où vous générerez et gérerez vos flux de produits Google Merchant Center. Vous y accédez en naviguant vers **Modules > Gestionnaire de modules**, en trouvant « Flux Google Merchant Center », puis en cliquant sur le lien « Exporter le flux de produits » (ou similaire, selon la version de PrestaShop, il peut s'agir d'un sous-élément de menu sous l'entrée principale du module).

Cet écran vous permet de définir le contenu et le format de votre flux de produits.

**Actions et paramètres disponibles :**

L'écran présente un formulaire avec divers champs correspondant aux attributs requis par Google Merchant Center. Vous les remplirez pour personnaliser votre flux.

-   **ID :**
    *   **Objectif :** C'est l'identifiant unique de chaque produit dans votre flux. Google l'utilise pour faire correspondre votre produit à ses données.
    *   **Effet des modifications :** Garantit que chaque produit a un ID distinct, ce qui est essentiel pour que Google traite correctement votre flux.
    *   **Valeur recommandée :** Généralement, il correspond à l'ID interne ou à la référence de votre produit.
-   **GTIN (Global Trade Item Number) :**
    *   **Objectif :** Les numéros d'article commercial mondial (comme EAN, UPC, ISBN) sont des identifiants de produit uniques utilisés dans le monde entier. Google les exige pour la plupart des produits.
    *   **Effet des modifications :** L'inclusion de GTIN corrects aide Google à identifier vos produits avec précision, améliorant la visibilité et la confiance. Des GTIN manquants ou incorrects peuvent entraîner des refus de produits.
    *   **Valeur recommandée :** Mappez au champ EAN/UPC de votre produit.
-   **Identifier\_exists :**
    *   **Objectif :** Indique si un identifiant de produit unique (comme GTIN, Marque, MPN) existe pour le produit.
    *   **Effet des modifications :** Si vous vendez des produits personnalisés ou des produits sans identifiants standard, le fait de définir cette option sur 'non' (ou 'false') peut éviter les refus. Pour la plupart des produits standard, elle devrait être 'oui'.
    *   **Valeur recommandée :** Généralement 'oui' si des GTIN sont fournis.
-   **Titre :**
    *   **Objectif :** Le nom de votre produit tel qu'il apparaîtra sur Google Shopping. C'est un champ crucial pour attirer les clics.
    *   **Effet des modifications :** Un titre clair et descriptif avec des mots-clés pertinents améliore la visibilité dans les recherches et les taux de clics.
    *   **Valeur recommandée :** Le nom de votre produit, potentiellement enrichi d'attributs clés (par exemple, « T-shirt rouge - Taille M - Coton »).
-   **Disponibilité :**
    *   **Objectif :** Indique si le produit est en stock, en rupture de stock ou disponible en précommande.
    *   **Effet des modifications :** Une disponibilité précise empêche les clients de cliquer sur des articles en rupture de stock, améliorant l'expérience utilisateur et réduisant les dépenses publicitaires inutiles.
    *   **Valeur recommandée :** Tirée automatiquement du statut de stock de votre produit.
-   **Availability\_date :**
    *   **Objectif :** La date à laquelle un produit en précommande sera disponible.
    *   **Effet des modifications :** Offre de la transparence aux clients intéressés par les articles en précommande.
    *   **Valeur recommandée :** À définir si vous proposez des précommandes.
-   **Inventaire :**
    *   **Objectif :** La quantité de produit actuellement en stock.
    *   **Effet des modifications :** Maintient vos annonces Google synchronisées avec vos niveaux de stock réels, évitant les surventes.
    *   **Valeur recommandée :** Tirée automatiquement de la quantité de stock de votre produit.
-   **Marque :**
    *   **Objectif :** Le nom de la marque de votre produit.
    *   **Effet des modifications :** Aide les clients à identifier les marques familières et améliore la catégorisation des produits sur Google.
    *   **Valeur recommandée :** La marque/fabricant de votre produit.
-   **Lien :**
    *   **Objectif :** L'URL directe vers la page de votre produit sur votre boutique.
    *   **Effet des modifications :** Essentiel pour diriger les clients de Google vers votre site web.
    *   **Valeur recommandée :** L'URL canonique de votre produit.
-   **Lien image :**
    *   **Objectif :** L'URL de l'image principale de votre produit.
    *   **Effet des modifications :** Des images de haute qualité et claires sont essentielles pour attirer les clics sur Google Shopping.
    *   **Valeur recommandée :** L'URL de l'image principale de votre produit.
-   **Additional\_image\_link :**
    *   **Objectif :** URL des images supplémentaires de votre produit.
    *   **Effet des modifications :** Fournit plus d'informations visuelles aux clients potentiels, les aidant à prendre des décisions d'achat.
    *   **Valeur recommandée :** URL des images secondaires du produit.
-   **Sous-titre de l'article :**
    *   **Objectif :** Une description optionnelle, plus courte ou un détail supplémentaire pour le produit.
    *   **Effet des modifications :** Peut être utilisé pour mettre en évidence des fonctionnalités clés ou des promotions.
    *   **Valeur recommandée :** Optionnel, utilisez-le pour des détails courts et percutants.
-   **Description :**
    *   **Objectif :** Une description détaillée de votre produit.
    *   **Effet des modifications :** Fournit des informations complètes aux clients et aide Google à comprendre la pertinence de votre produit.
    *   **Valeur recommandée :** La description complète de votre produit.
-   **Type de produit :**
    *   **Objectif :** Votre propre catégorisation du produit au sein de votre boutique.
    *   **Effet des modifications :** Aide Google à comprendre votre hiérarchie de produits et peut être utilisé pour le ciblage de campagnes.
    *   **Valeur recommandée :** Votre chemin de catégorie interne (par exemple, « Vêtements > T-shirts > T-shirts pour hommes »).
-   **Condition :**
    *   **Objectif :** L'état du produit (par exemple, neuf, d'occasion, reconditionné).
    *   **Effet des modifications :** Des informations précises sur l'état sont vitales pour la confiance des clients et les politiques de Google.
    *   **Valeur recommandée :** Généralement 'neuf' pour la plupart des boutiques e-commerce.
-   **Prix :**
    *   **Objectif :** Le prix de vente actuel de votre produit.
    *   **Effet des modifications :** Une tarification précise est primordiale. Des incohérences entre votre flux et votre site web peuvent entraîner des refus.
    *   **Valeur recommandée :** Le prix actuel de votre produit.
-   **Prix de vente :**
    *   **Objectif :** Le prix réduit de votre produit s'il est en promotion.
    *   **Effet des modifications :** Met en évidence les promotions et attire les clients à la recherche de bonnes affaires.
    *   **Valeur recommandée :** Le prix spécifique de votre produit.
-   **Taux de taxe :**
    *   **Objectif :** Le taux de taxe applicable au produit.
    *   **Effet des modifications :** Garantit des informations de prix précises, en particulier pour les régions où la taxe est calculée à la caisse.
    *   **Valeur recommandée :** Le taux de taxe applicable à votre boutique.
-   **Mots-clés contextuels :**
    *   **Objectif :** Mots-clés supplémentaires pour aider Google à comprendre votre produit.
    *   **Effet des modifications :** Peut améliorer la pertinence de votre produit dans les résultats de recherche.
    *   **Valeur recommandée :** Termes de recherche pertinents non déjà présents dans le titre ou la description.
-   **Catégorie de produit Google :**
    *   **Objectif :** La catégorisation standardisée des produits par Google. C'est un champ essentiel pour que Google comprenne ce que vous vendez.
    *   **Effet des modifications :** La catégorisation correcte de vos produits selon la taxonomie de Google améliore la visibilité et garantit que vos produits apparaissent dans les recherches pertinentes. Des catégories incorrectes peuvent entraîner des refus.
    *   **Valeur recommandée :** Sélectionnez la catégorie de produit Google la plus spécifique qui s'applique à votre produit.

**Autres paramètres et options :**

-   **Exporter l'attribut de taille :**
    *   **Objectif :** Détermine si les attributs de taille du produit doivent être inclus dans le flux, ce qui est important pour les vêtements et autres produits dépendants de la taille.
    *   **Effet des modifications :**
        *   *Lorsqu'activé :* Les tailles de produit (par exemple, S, M, L) seront exportées, permettant à Google d'afficher les informations de taille et les options de filtrage.
        *   *Lorsqu'désactivé :* Les informations de taille ne seront pas incluses.
    *   **Valeur recommandée :** **OUI** pour les magasins de vêtements/habillement, **NON** pour les autres types de produits.
-   **Exporter les catégories à exclure :**
    *   **Objectif :** Vous permet de sélectionner des catégories spécifiques dont les produits doivent être *exclus* du flux. Cela fonctionne en conjonction avec le paramètre « Afficher l'arborescence des catégories » de la configuration principale.
    *   **Effet des modifications :** Les produits appartenant aux catégories sélectionnées n'apparaîtront pas dans le flux généré.
    *   **Valeur recommandée :** Utilisez ceci pour filtrer les produits que vous ne souhaitez pas annoncer sur Google (par exemple, les catégories en rupture de stock, les services ou les produits à faible marge).
-   **Exporter la date de disponibilité :**
    *   **Objectif :** Contrôle si l'attribut `availability_date` est inclus dans le flux.
    *   **Effet des modifications :**
        *   *Lorsqu'activé :* La date à laquelle un produit devient disponible (pour les précommandes) sera incluse.
        *   *Lorsqu'désactivé :* Cette information sera omise.
    *   **Valeur recommandée :** **OUI** si vous utilisez la fonctionnalité de précommande de PrestaShop et que vous souhaitez communiquer les dates de disponibilité à Google.
-   **Bouton Générer le flux :**
    *   **Objectif :** Lance le processus de génération du flux de produits XML/CSV basé sur toutes vos options sélectionnées.
    *   **Effet des modifications :** Crée le fichier de flux, que vous pouvez ensuite télécharger ou fournir l'URL à Google Merchant Center pour des récupérations planifiées.

**Flux de travail recommandé pour la gestion quotidienne de la boutique :**

1.  **Configuration initiale :** Mappez soigneusement tous les attributs de Google Merchant Center aux champs de produits de votre PrestaShop. Portez une attention particulière au GTIN, à la marque et à la catégorie de produit Google.
2.  **Filtrage des catégories :** Utilisez l'option « Exporter les catégories à exclure » pour affiner les produits envoyés à Google.
3.  **Générer et tester :** Générez un flux et téléchargez-le sur Google Merchant Center. Surveillez les erreurs ou avertissements dans votre compte Google Merchant Center.
4.  **Récupérations planifiées :** Une fois votre flux approuvé, configurez une récupération planifiée dans Google Merchant Center en utilisant l'URL fournie par le module. Cela garantit que Google dispose toujours des dernières données produit.
5.  **Examen régulier :** Examinez périodiquement les diagnostics de votre Google Merchant Center pour détecter tout refus ou avertissement, et ajustez les paramètres de votre module ou les données produit dans PrestaShop en conséquence.

#### index.php (gmfeed/controllers/admin/index.php)

Ce fichier sert probablement de marqueur de position ou de redirection au sein de la structure du contrôleur d'administration du module et ne représente pas un écran distinct et configurable pour le marchand. La configuration et la gestion principales se font via `AdminExportProductsFeedGoogleController`.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Afficher l'arborescence des catégories | OUI | Active le filtrage des catégories sur l'écran d'exportation pour une sélection précise des produits. |
| **AdminExportProductsFeedGoogle** | ID | ID du produit | Identifiant unique pour chaque produit dans le flux. |
| | GTIN | EAN/UPC du produit | Numéro d'article commercial mondial pour l'identification du produit. |
| | Identifier\_exists | Oui | Indique si des identifiants uniques sont présents. |
| | Titre | Nom du produit | Titre du produit pour Google Shopping. |
| | Disponibilité | Détection automatique | Statut de stock du produit (en stock, en rupture de stock). |
| | Availability\_date | Détection automatique | Date de disponibilité pour la précommande. |
| | Inventaire | Détection automatique | Quantité de stock actuelle. |
| | Marque | Fabricant du produit | Nom de la marque du produit. |
| | Lien | URL du produit | Lien direct vers la page du produit. |
| | Lien image | URL de l'image principale du produit | URL de l'image principale du produit. |
| | Additional\_image\_link | URL des images secondaires du produit | URL des images supplémentaires du produit. |
| | Sous-titre de l'article | Optionnel | Détail court et supplémentaire du produit. |
| | Description | Description du produit | Description détaillée du produit. |
| | Product\_type | Votre chemin de catégorie | Votre catégorisation interne des produits. |
| | Condition | Neuf | État du produit (neuf, d'occasion, reconditionné). |
| | Prix | Prix du produit | Prix de vente actuel. |
| | Prix de vente | Prix spécifique du produit | Prix réduit si en promotion. |
| | Taux de taxe | Taux de taxe de la boutique | Taux de taxe applicable. |
| | Mots-clés contextuels | Optionnel | Mots-clés supplémentaires pour la pertinence du produit. |
| | Catégorie de produit Google | Sélectionner dans la taxonomie Google | Catégorie de produit standardisée par Google. |
| | Exporter l'attribut de taille | OUI (pour les vêtements) | Inclut les attributs de taille du produit dans le flux. |
| | Exporter les catégories à exclure | Sélectionner selon les besoins | Exclut les produits des catégories sélectionnées. |
| | Exporter la date de disponibilité | OUI (pour les précommandes) | Inclut l'attribut `availability_date`. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes produits n'apparaissent pas sur Google Shopping, ou je reçois des refus. Que dois-je vérifier en premier ?**
R1 :

-   **Compte Google Merchant Center (GMC) :** Connectez-vous à votre compte GMC et consultez la section « Diagnostics ». C'est là que Google signale les erreurs ou avertissements spécifiques pour vos produits et votre flux.
-   **Traitement du flux :** Assurez-vous que votre flux a été traité avec succès par Google. Vérifiez la section « Flux » dans GMC.
-   **Attributs requis :** Vérifiez que tous les attributs Google obligatoires (ID, Titre, Lien, Lien image, Prix, Description, GTIN/Marque/MPN, Disponibilité, Catégorie de produit Google) sont correctement mappés et renseignés dans les paramètres d'exportation du module.
-   **Incohérences de données :** Google est très strict quant à la concordance des prix et de la disponibilité entre votre flux et votre site web. Assurez-vous que les données de vos produits PrestaShop sont exactes et que Google récupère le dernier flux.
-   **Catégorie de produit Google :** Assurez-vous d'avoir sélectionné la catégorie de produit Google la plus précise pour vos produits.

**Q2 : J'ai apporté des modifications à mes produits dans PrestaShop, mais elles ne sont pas mises à jour sur Google Shopping.**
R2 :

-   **Générer un nouveau flux :** Après avoir apporté des modifications dans PrestaShop, vous devez générer un nouveau flux à l'aide du bouton « Générer le flux » du module.
-   **Récupération planifiée par Google :** Google Merchant Center doit récupérer ce flux mis à jour. Si vous avez configuré une récupération planifiée, elle sera mise à jour automatiquement à la prochaine heure prévue. Vous pouvez également déclencher manuellement une récupération dans votre compte Google Merchant Center sous « Flux » > « Récupérer maintenant ».
-   **Mise en cache :** Videz le cache Smarty de votre PrestaShop (Paramètres avancés > Performances) et le cache de votre navigateur pour vous assurer que vous voyez la dernière version de la configuration du module et du flux généré.

**Q3 : Comment exclure certains produits ou catégories du flux Google ?**
R3 :

-   Sur l'écran de configuration principal du module, assurez-vous que « Afficher l'arborescence des catégories » est activé.
-   Ensuite, sur l'écran `AdminExportProductsFeedGoogle`, utilisez l'option « Exporter les catégories à exclure ». Vous verrez une arborescence de vos catégories. Sélectionnez les catégories dont vous souhaitez exclure les produits du flux.
-   Générez un nouveau flux après avoir effectué ces sélections.

**Q4 : Le processus de génération du flux prend beaucoup de temps ou expire pour ma grande boutique.**
R4 :

-   **Ressources serveur :** La génération de grands flux peut être gourmande en ressources. Contactez votre hébergeur pour vous assurer que votre serveur dispose d'une limite de mémoire PHP, d'un temps d'exécution et de ressources CPU suffisants.
-   **Paramètres PHP :** Augmentez `max_execution_time` et `memory_limit` dans votre fichier `php.ini` (ou via votre panneau de contrôle d'hébergement).
-   **Filtrer les produits :** Si possible, essayez de segmenter votre flux en excluant les catégories ou produits moins importants pour réduire la taille du flux.
-   **Mises à jour du module :** Assurez-vous d'utiliser la dernière version du module, car les améliorations de performances sont souvent incluses dans les mises à jour.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module `Flux Google Merchant Center` suit une architecture de module PrestaShop standard, exploitant principalement les contrôleurs du Back-Office pour la configuration et la génération de flux. Il utilise un contrôleur frontal pour exposer l'URL du flux généré pour les récupérations planifiées de Google. Le module n'étend pas `ObjectModel` pour les tables de base de données personnalisées, mais s'appuie sur la classe `Configuration` de PrestaShop pour les paramètres. Il intègre une bibliothèque d'outils de recherche tierce pour la fonctionnalité d'autocomplétion.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   `controllers/front/feed.php`
    *   **Nom de la classe :** `GmfeedFeedModuleFrontController`
    *   **Classe parente :** `ModuleFrontController`
    *   **Responsabilité :** Ce contrôleur est responsable de la diffusion du flux de produits XML/CSV généré vers Google Merchant Center. Lorsque Google effectue une récupération planifiée, il accède à une URL gérée par ce contrôleur. Le contrôleur récupère les dernières données de flux générées et les affiche, généralement avec des en-têtes appropriés pour le téléchargement de fichiers ou l'affichage direct.
-   `controllers/front/index.php`
    *   **Nom de la classe :** `GmfeedIndexModuleFrontController`
    *   **Classe parente :** `ModuleFrontController`
    *   **Responsabilité :** Il s'agit probablement d'un espace réservé ou d'un contrôleur frontal par défaut qui pourrait rediriger ou simplement afficher une page blanche. Il ne semble pas avoir un rôle fonctionnel direct dans la génération ou l'affichage du flux, d'après les informations fournies.

#### Contrôleurs d'administration Back-Office

-   `controllers/admin/AdminExportProductsFeedGoogle.php`
    *   **Nom de la classe :** `AdminExportProductsFeedGoogleController`
    *   **Classe parente :** `ModuleAdminController`
    *   **Nom de l'onglet :** « Exporter le flux de produits » (ou similaire, lié à la configuration principale du module)
    *   **Entité gérée :** Génération du flux de produits.
    *   **Responsabilité :** Il s'agit du contrôleur d'administration principal pour la gestion et la génération du flux Google Merchant Center. Il gère l'affichage du formulaire de configuration pour les attributs du flux (GTIN, Titre, Prix, etc.), traite les soumissions de formulaire et déclenche la logique de génération du flux. Il interagit avec les données de produits, de catégories et d'attributs de PrestaShop pour compiler le flux. Il gère également l'exclusion des catégories (`gm_export_exclude_categories`) et d'autres paramètres spécifiques au flux.
-   `controllers/admin/index.php`
    *   **Nom de la classe :** `GmfeedIndexModuleAdminController`
    *   **Classe parente :** `ModuleAdminController`
    *   **Nom de l'onglet :** (Probablement pas un onglet direct, mais fait partie du routage interne du module)
    *   **Responsabilité :** Similaire à son homologue frontal, il s'agit probablement d'un espace réservé ou d'un contrôleur d'administration par défaut. Il ne semble pas gérer une entité spécifique ni fournir une interface utilisateur distincte.

### 4.3 Classes et modèles principaux (`classes/`)

Les informations fournies n'indiquent aucune classe ou modèle personnalisé dans le répertoire `classes/`. Le module effectue probablement ses opérations directement dans le fichier de module principal (`gmfeed.php`) et ses contrôleurs, en tirant parti des classes `ObjectModel` existantes de PrestaShop (comme `Product`, `Category`, `Manufacturer`, `AttributeGroup`, `Attribute`) et de la classe `Configuration` pour les paramètres.

### 4.4 Actifs JavaScript (`views/js/`)

-   `gmfeed/lib/searchTool/views/js/autocomplete.js`
    *   **Portée :** Probablement Back-office.
    *   **Détails :** Ce script fait partie d'une bibliothèque d'outils de recherche, probablement utilisée pour la fonctionnalité d'autocomplétion dans les formulaires de configuration d'administration, tels que la sélection des catégories de produits Google ou l'exclusion de produits/catégories spécifiques. Il se lierait aux champs de saisie, effectuerait des requêtes AJAX vers un point de terminaison backend (éventuellement géré par l'un des contrôleurs d'administration) pour récupérer des suggestions et les afficher à l'utilisateur.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `gmfeed/lib/searchTool/views/css/autocomplete.css`
    *   **Portée :** Style du formulaire d'administration du Back-office.
    *   **Détails :** Fournit le style pour les suggestions d'autocomplétion et les champs de saisie, garantissant une apparence cohérente et conviviale pour l'outil de recherche dans l'interface d'administration du module.
    *   **Sélecteurs CSS clés :** Inclut probablement des classes pour le conteneur d'autocomplétion, la liste de suggestions, la suggestion active et le champ de saisie.
-   `gmfeed/views/admin-theme.css`
    *   **Portée :** Style du formulaire d'administration du Back-office.
    *   **Détails :** Contient des règles de style générales spécifiques aux pages de configuration du module dans le Back Office de PrestaShop. Cela peut inclure des ajustements de mise en page, le style des boutons, le style des éléments de formulaire ou des repères visuels spécifiques pour l'interface du module.
    *   **Sélecteurs CSS clés :** ID ou classes de conteneurs spécifiques au module, classes d'éléments de formulaire.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)

Le dossier du module indique `actionAdminControllerSetMedia` comme un hook de front-office, ce qui est inhabituel car il s'agit d'un hook d'administration. Il est plus probable que le module utilise `actionAdminControllerSetMedia` pour charger ses actifs JS/CSS dans le back-office, et les modèles listés ci-dessous sont rendus dans le contexte d'administration.

#### Modèles d'administration (`views/templates/admin/`)

-   `gmfeed/lib/searchTool/views/scripts.tpl`
    *   **Objectif :** Inclut probablement du code JavaScript ou initialise la fonctionnalité d'autocomplétion. Ce modèle serait rendu dans le Back Office pour configurer l'outil de recherche.
-   `gmfeed/views/categories-fancybox.tpl`
    *   **Objectif :** Ce modèle est utilisé pour afficher l'arborescence des catégories pour la sélection/exclusion, probablement dans une fenêtre contextuelle Fancybox (ou similaire). Il rendrait la liste hiérarchique des catégories.
-   `gmfeed/views/exclude-products.tpl`
    *   **Objectif :** Ce modèle afficherait l'interface pour sélectionner les produits à exclure du flux, potentiellement en utilisant l'outil de recherche et l'arborescence des catégories.
-   `gmfeed/views/google_lang_links.tpl`
    *   **Objectif :** Ce modèle pourrait être utilisé pour afficher des liens ou des informations liés à Google Merchant Center pour différentes langues, guidant éventuellement le marchand à configurer des flux pour différentes langues de boutique.
-   `gmfeed/views/returnAlert.tpl`
    *   **Objectif :** Un modèle générique pour afficher des alertes ou des messages à l'utilisateur dans le Back Office, tels que des messages de succès après la génération du flux ou des notifications d'erreur.
-   `gmfeed/views/script-fancybox.tpl`
    *   **Objectif :** Ce modèle contient probablement du code JavaScript pour initialiser et configurer la bibliothèque Fancybox (ou similaire), utilisée pour afficher des popups comme l'arborescence des catégories.
-   `gmfeed/views/script.tpl`
    *   **Objectif :** Un modèle de script général pour le Back Office du module, contenant potentiellement diverses fonctionnalités JavaScript, des écouteurs d'événements ou des appels AJAX liés au processus de configuration et de génération du flux.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    *   Le module ne semble pas créer de tables SQL personnalisées d'après les informations fournies (pas de `classes/` avec `ObjectModel` ou de fichiers SQL `install/uninstall`).
    *   Les paramètres de configuration (par exemple, `pf_tree`, `gm_export_size_attribute`, `gm_export_exclude_categories`, `gm_export_availability_date`) sont stockés dans la table `ps_configuration`. La valeur de `gm_export_exclude_categories` serait probablement un tableau sérialisé d'ID de catégories.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration est initialisé et que ses médias (JS/CSS) sont définis. | Utilisé par le module pour charger ses fichiers JavaScript et CSS spécifiques (par exemple, `autocomplete.js`, `admin-theme.css`) dans le Back Office pour ses écrans de configuration. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et les dernières versions du module « Flux Google Merchant Center », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez rencontrer concernant la fonctionnalité du module et son intégration avec votre boutique PrestaShop.
