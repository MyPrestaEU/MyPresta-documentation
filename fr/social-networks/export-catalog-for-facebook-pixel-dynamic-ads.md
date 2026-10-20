---
title: "Export catalog for facebook pixel dynamic ads - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Export catalog for facebook pixel dynamic ads' par MyPresta.eu."
sidebar:
  label: "Export catalog for facebook pixel dynamic ads - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Export catalog for facebook pixel dynamic ads sur MyPresta.eu](https://mypresta.eu/modules/social-networks/export-catalog-for-facebook-pixel-dynamic-ads.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/export-catalog-for-facebook-pixel-dynamic-ads/)
>
> ---


# Export catalog for facebook pixel dynamic ads

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Assurez-vous que votre serveur dispose de suffisamment de mémoire et de temps d'exécution pour générer de grands flux de produits si vous avez de nombreux produits.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

La configuration du module est principalement gérée via un écran d'administration dédié, qui vous permet de définir la manière dont votre catalogue de produits est exporté.

### 2.1 Écran de configuration principal du module (Back Office > Modules > Gestionnaire de modules > Configurer)

Cet écran fournit les paramètres principaux du module, vous permettant de générer et de gérer vos flux de produits.

**Emplacement du menu :** Back Office > Modules > Gestionnaire de modules > Rechercher « Export catalog for facebook pixel dynamic ads » > Cliquer sur « Configurer ».

#### Paramètres généraux et génération de flux

Cette section est l'endroit où vous définissez les paramètres essentiels de votre flux de produits.

-   **Sélectionner la langue pour l'exportation :**
    *   **Ce que fait ce paramètre :** Détermine les noms de produits, descriptions et autres champs de texte de quelle langue seront inclus dans le flux exporté.
    *   **Effet de la modification de ce paramètre :**
        *   *Si défini sur Anglais :* Votre flux contiendra les détails des produits en anglais.
        *   *Si défini sur Français :* Votre flux contiendra les détails des produits en français.
    *   **Valeur recommandée :** La langue principale de votre public cible pour les publicités Facebook. Si vous diffusez des publicités dans plusieurs langues, vous devrez générer des flux séparés pour chaque langue.
    *   **Scénario / exemple marchand :** Si vous ciblez principalement des clients aux États-Unis, vous sélectionneriez « Anglais ». Si vous ciblez également des clients en France, vous généreriez un flux séparé avec « Français » sélectionné.
-   **Sélectionner la devise pour l'exportation :**
    *   **Ce que fait ce paramètre :** Détermine les prix de quelle devise seront inclus dans le flux exporté.
    *   **Effet de la modification de ce paramètre :**
        *   *Si défini sur USD :* Tous les prix des produits dans le flux seront en dollars américains.
        *   *Si défini sur EUR :* Tous les prix des produits dans le flux seront en euros.
    *   **Valeur recommandée :** La devise principale de votre public cible pour les publicités Facebook. Comme pour la langue, si vous ciblez plusieurs devises, vous aurez besoin de flux séparés.
    *   **Scénario / exemple marchand :** Si votre boutique vend en USD et en CAD, et que vous souhaitez diffuser des publicités Facebook pour vos clients canadiens, vous sélectionneriez « Dollar canadien » pour ce flux spécifique.
-   **Exporter uniquement les produits actifs :**
    *   **Ce que fait ce paramètre :** Contrôle si seuls les produits actuellement activés et visibles dans votre boutique sont inclus dans le flux.
    *   **Effet de la modification de ce paramètre :**
        *   *Si activé (OUI) :* Seuls les produits actifs dans votre boutique PrestaShop seront exportés. Cela empêche d'afficher des publicités pour des articles en rupture de stock ou abandonnés.
        *   *Si désactivé (NON) :* Tous les produits, y compris les inactifs, pourraient être exportés. Ce n'est généralement pas recommandé pour les campagnes publicitaires en direct.
    *   **Valeur recommandée :** **OUI**. Cela garantit que vos publicités sont toujours pertinentes et renvoient à des produits disponibles.
    *   **Scénario / exemple marchand :** Vous avez des produits saisonniers qui sont actuellement inactifs. L'activation de cette option garantit qu'ils n'apparaissent pas dans vos publicités Facebook tant que vous ne les réactivez pas.
-   **Exporter uniquement les produits en stock :**
    *   **Ce que fait ce paramètre :** Détermine si seuls les produits avec un stock disponible sont inclus dans le flux.
    *   **Effet de la modification de ce paramètre :**
        *   *Si activé (OUI) :* Seuls les produits actuellement en stock seront exportés.
        *   *Si désactivé (NON) :* Les produits en rupture de stock pourraient être exportés, ce qui pourrait entraîner une mauvaise expérience client s'ils cliquent sur une publicité pour un article indisponible.
    *   **Valeur recommandée :** **OUI**. Cela empêche les clients de cliquer sur des publicités pour des produits qu'ils ne peuvent pas acheter, réduisant la frustration et le gaspillage de dépenses publicitaires.
    *   **Scénario / exemple marchand :** Un article populaire vient d'être en rupture de stock. Avec cette option activée, il sera automatiquement supprimé de votre flux Facebook jusqu'à ce qu'il soit réapprovisionné.
-   **Exporter les combinaisons de produits (variations) :**
    *   **Ce que fait ce paramètre :** Contrôle si les combinaisons de produits individuelles (par exemple, un T-shirt de différentes tailles et couleurs) sont exportées comme des articles distincts dans le flux.
    *   **Effet de la modification de ce paramètre :**
        *   *Si activé (OUI) :* Chaque combinaison (par exemple, « T-shirt Rouge - Petit », « T-shirt Rouge - Moyen ») apparaîtra comme un article unique dans le flux, avec sa propre image, son prix et son lien. C'est crucial pour que les publicités dynamiques affichent la variante exacte qu'un client a consultée.
        *   *Si désactivé (NON) :* Seul le produit principal sera exporté, sans les combinaisons individuelles. Cela limite la granularité de vos publicités dynamiques.
    *   **Valeur recommandée :** **OUI**. C'est fortement recommandé pour la plupart des boutiques, en particulier celles vendant des vêtements, des produits électroniques ou tout produit avec des variations, afin d'assurer l'expérience publicitaire la plus précise et personnalisée.
    *   **Scénario / exemple marchand :** Un client consulte une « Robe Bleue - Grande » sur votre site. Si les combinaisons sont exportées, Facebook peut lui montrer une publicité spécifiquement pour cette « Robe Bleue - Grande ».
-   **Identification du produit (champ ID) :**
    *   **Ce que fait ce paramètre :** Spécifie quel champ d'ID PrestaShop doit être utilisé comme identifiant unique pour les produits dans le flux Facebook (champ `id`).
    *   **Effet de la modification de ce paramètre :**
        *   *ID du produit :* Utilise l'`id_product` standard de PrestaShop.
        *   *EAN13 :* Utilise le code-barres EAN13.
        *   *UPC :* Utilise le code-barres UPC.
        *   *Référence :* Utilise le code de référence interne du produit.
    *   **Valeur recommandée :** **ID du produit** est généralement l'option la plus sûre et la plus fiable car elle est toujours unique et interne à PrestaShop. Si vous utilisez systématiquement EAN13/UPC pour tous les produits et combinaisons, ceux-ci peuvent également fonctionner.
    *   **Scénario / exemple marchand :** Vous avez une intégration personnalisée qui repose sur `id_product` pour le suivi. L'utilisation de « ID du produit » ici garantit la cohérence.
-   **Champ Catégorie de produit :**
    *   **Ce que fait ce paramètre :** Détermine quelles informations de catégorie sont envoyées à Facebook.
    *   **Effet de la modification de ce paramètre :**
        *   *Catégorie PrestaShop par défaut :* Utilise le nom de la catégorie principale du produit.
        *   *Catégorie de produit Google :* Utilise la Catégorie de produit Google (si attribuée). C'est souvent préféré par Facebook pour une meilleure correspondance.
    *   **Valeur recommandée :** **Catégorie de produit Google** si vous les avez attribuées. Sinon, « Catégorie PrestaShop par défaut ».
    *   **Scénario / exemple marchand :** Vous vendez des « T-Shirts » dans PrestaShop, mais la Catégorie de produit Google est « Vêtements et accessoires > Vêtements > Chemises et hauts > T-Shirts ». L'utilisation de la catégorie Google fournit des données plus spécifiques à Facebook.
-   **Champ Marque du produit :**
    *   **Ce que fait ce paramètre :** Sélectionne quel champ de vos données produit doit être utilisé pour l'attribut `brand` dans le flux Facebook.
    *   **Effet de la modification de ce paramètre :**
        *   *Nom du fabricant :* Utilise le fabricant attribué au produit dans PrestaShop.
        *   *Nom du fournisseur :* Utilise le fournisseur attribué au produit.
    *   **Valeur recommandée :** **Nom du fabricant**. C'est le champ le plus courant et le plus logique pour la « marque ».
    *   **Scénario / exemple marchand :** Vous vendez des chaussures Nike. La sélection de « Nom du fabricant » remplira correctement « Nike » comme marque dans votre flux.
-   **Champ Type de produit :**
    *   **Ce que fait ce paramètre :** Spécifie quelles informations doivent être utilisées pour le champ `product_type` dans le flux Facebook.
    *   **Effet de la modification de ce paramètre :**
        *   *Catégorie PrestaShop par défaut :* Utilise le nom de la catégorie principale du produit.
        *   *Catégorie de produit Google :* Utilise la Catégorie de produit Google (si attribuée).
    *   **Valeur recommandée :** **Catégorie de produit Google** si disponible, sinon « Catégorie PrestaShop par défaut ». Cela aide Facebook à comprendre le type de produit.
    *   **Scénario / exemple marchand :** Pour un produit dans « Électronique > Smartphones », la Catégorie de produit Google pourrait être « Électronique > Communications > Téléphonie > Téléphones mobiles ».
-   **Champ Image du produit :**
    *   **Ce que fait ce paramètre :** Détermine quelle URL d'image est utilisée pour le `image_link` dans le flux.
    *   **Effet de la modification de ce paramètre :**
        *   *Image de produit par défaut :* Utilise l'image principale associée au produit.
        *   *Image de combinaison (si disponible) :* Si vous exportez des combinaisons, cela utilisera l'image spécifique attribuée à cette combinaison, sinon l'image de produit par défaut.
    *   **Valeur recommandée :** **Image de combinaison (si disponible)**. Cela garantit que si un client voit une chemise rouge, la publicité affiche une chemise rouge, et non seulement l'image générique du produit.
    *   **Scénario / exemple marchand :** Vous avez un produit avec plusieurs combinaisons de couleurs, chacune avec sa propre image. Ce paramètre garantit que l'image de couleur correcte est affichée dans la publicité.
-   **Champ Description du produit :**
    *   **Ce que fait ce paramètre :** Sélectionne quel champ de description de PrestaShop (`description` ou `short_description`) est utilisé pour l'attribut `description` dans le flux Facebook.
    *   **Effet de la modification de ce paramètre :**
        *   *Description :* Exporte la description complète et détaillée du produit.
        *   *Description courte :* Exporte le bref résumé du produit.
    *   **Valeur recommandée :** **Description**. Facebook préfère généralement une description plus détaillée pour un meilleur contexte publicitaire.
    *   **Scénario / exemple marchand :** Vous souhaitez fournir autant d'informations que possible dans vos publicités. L'utilisation de la description complète garantit cela.
-   **Champ Description courte du produit :**
    *   **Ce que fait ce paramètre :** Sélectionne quel champ de description de PrestaShop (`description` ou `short_description`) est utilisé pour l'attribut `short_description` dans le flux Facebook.
    *   **Effet de la modification de ce paramètre :**
        *   *Description :* Exporte la description complète et détaillée du produit.
        *   *Description courte :* Exporte le bref résumé du produit.
    *   **Valeur recommandée :** **Description courte**. C'est utile si le flux de Facebook nécessite à la fois une description longue et courte, ou si vous préférez un résumé concis pour certains formats d'annonces.
    *   **Scénario / exemple marchand :** Vous souhaitez un résumé concis pour le champ `short_description` dans votre flux.
-   **Délimiteur CSV :**
    *   **Ce que fait ce paramètre :** Spécifie le caractère utilisé pour séparer les valeurs dans le fichier CSV généré (par exemple, virgule, point-virgule).
    *   **Effet de la modification de ce paramètre :**
        *   *Virgule (,) :* Format CSV standard.
        *   *Point-virgule (;) :* Courant dans certaines localisations européennes.
    *   **Valeur recommandée :** **Virgule (,)**. C'est le délimiteur le plus largement accepté pour les fichiers CSV, y compris par Facebook.
    *   **Scénario / exemple marchand :** Si l'outil d'importation de Facebook spécifie un délimiteur point-virgule, vous le changeriez ici. Sinon, tenez-vous-en à la virgule.
-   **Supprimer les images du flux :**
    *   **Ce que fait ce paramètre :** Si activé, le module supprimera les liens d'image du flux généré.
    *   **Effet de la modification de ce paramètre :**
        *   *Si activé (OUI) :* Les colonnes `image_link` et `additional_image_link` du flux seront vides. Ce n'est généralement PAS recommandé car les images sont cruciales pour les publicités dynamiques.
        *   *Si désactivé (NON) :* Les liens d'image seront inclus dans le flux.
    *   **Valeur recommandée :** **NON**. Les images sont fondamentales pour les publicités visuelles.
    *   **Scénario / exemple marchand :** Ce paramètre est rarement utile, sauf si vous avez une configuration très spécifique et avancée où les images sont gérées entièrement séparément.

#### Exclure des produits

Cette section vous permet d'empêcher l'inclusion de produits spécifiques dans votre flux Facebook.

-   **Exclure des produits par ID :**
    *   **Ce que fait ce paramètre :** Vous permet de saisir une liste d'ID de produits séparés par des virgules que vous ne souhaitez pas voir apparaître dans votre catalogue de produits Facebook.
    *   **Effet de la modification de ce paramètre :**
        *   *Produits listés ici :* Seront complètement omis du flux généré.
    *   **Valeur recommandée :** Laisser vide, sauf si vous avez des produits spécifiques que vous ne voulez jamais annoncer (par exemple, produits de test internes, services non adaptés aux publicités dynamiques).
    *   **Scénario / exemple marchand :** Vous vendez à la fois des produits physiques et des services numériques. Vous pourriez exclure les produits de services numériques du flux car ils ne correspondent pas au format de publicité dynamique.

#### Bouton Générer le flux

-   **Ce que fait ce bouton :** Lance le processus de génération du fichier CSV du catalogue de produits basé sur tous les paramètres que vous avez configurés ci-dessus.
-   **Effet de cliquer sur ce bouton :** Le module traitera vos produits et créera un fichier CSV téléchargeable. Selon le nombre de produits, cela peut prendre un certain temps.
-   **Action recommandée :** Cliquez sur ce bouton après avoir examiné et enregistré tous vos paramètres souhaités.
-   **Scénario / exemple marchand :** Après avoir apporté des modifications à vos descriptions de produits ou ajouté de nouveaux produits, vous cliqueriez sur ce bouton pour générer un flux mis à jour pour Facebook.

#### Bouton Télécharger le flux

-   **Ce que fait ce bouton :** Vous permet de télécharger le fichier CSV du catalogue de produits le plus récemment généré sur votre ordinateur.
-   **Effet de cliquer sur ce bouton :** Votre navigateur téléchargera le fichier `facebook_products.csv`.
-   **Action recommandée :** Téléchargez le fichier après la génération, puis téléchargez-le sur votre Gestionnaire de publicités Facebook.
-   **Scénario / exemple marchand :** Une fois le flux généré, vous le téléchargez, puis naviguez vers votre Gestionnaire de publicités Facebook > Catalogues > Sources de données pour télécharger le CSV.

### 2.2 Écran d'administration dédié : AdminExportProductsFeedController

C'est l'écran d'administration principal où vous gérez la génération réelle du flux de produits et examinez les données qui seront exportées.

**Emplacement du menu :** Back Office > Modules > Gestionnaire de modules > Configurer « Export catalog for facebook pixel dynamic ads » > (Cet écran est l'interface de configuration principale elle-même, souvent accessible directement après avoir cliqué sur « Configurer »).

Cet écran présente une interface de type grille ou un formulaire avec diverses options pour contrôler la sortie de votre flux de produits. Les champs listés ci-dessous représentent les points de données qui peuvent être inclus dans votre catalogue de produits Facebook.

-   **ID :** L'identifiant unique du produit (basé sur votre paramètre « Identification du produit »).
-   **item\_group\_id :** Utilisé pour les combinaisons de produits afin de les regrouper sous un seul produit parent.
-   **Titre :** Le nom du produit.
-   **Description courte :** Le bref résumé du produit.
-   **Description :** La description complète du produit.
-   **Override :** (Probablement un paramètre interne du module, non directement exporté vers Facebook).
-   **Disponibilité :** Indique si le produit est en stock (`in stock`, `out of stock`).
-   **Inventaire :** La quantité de stock actuelle.
-   **Condition :** La condition du produit (par exemple, `new`, `used`, `refurbished`).
-   **Lien image :** L'URL de l'image principale du produit.
-   **Additional\_image\_link :** URLs des images de produits supplémentaires.
-   **Prix :** Le prix actuel du produit.
-   **sale\_price :** Le prix de vente du produit (le cas échéant).
-   **Marque :** La marque du produit (fabricant).
-   **Lien :** L'URL directe vers la page du produit sur votre boutique.
-   **Catégorie de produit Google :** La Catégorie de produit Google attribuée au produit.
-   **product\_type :** Le type de produit (par exemple, nom de catégorie).
-   **gender :** Pour les vêtements, le sexe cible (par exemple, `male`, `female`, `unisex`).
-   **size :** Pour les vêtements, la taille du produit.
-   **age\_group :** Pour les vêtements, la tranche d'âge cible (par exemple, `newborn`, `infant`, `toddler`, `kids`, `adult`).

**Actions et paramètres disponibles :**
Sur cet écran, vous trouverez les différentes options de configuration détaillées dans la section 4.1. La « Table / Entité gérée » ici fait référence à la table virtuelle de données produit que le module construit avant l'exportation. Il n'y a pas de table de base de données directe gérée par ce contrôleur spécifique, mais il traite et prépare les données de vos tables de produits PrestaShop existantes.

**Effet des modifications :**
Toute modification apportée aux paramètres de cet écran (par exemple, sélection d'une langue différente, activation/désactivation de l'exportation de combinaisons) modifiera directement le contenu et le format du fichier CSV généré lorsque vous cliquez sur le bouton « Générer le flux ».

**Flux de travail recommandé pour la gestion quotidienne de la boutique :**

1.  Périodiquement (par exemple, quotidiennement ou hebdomadairement, selon la fréquence de modification de votre catalogue de produits), visitez cette page de configuration.
2.  Assurez-vous que vos paramètres de langue, de devise et de stock/produits actifs sont corrects.
3.  Cliquez sur « Générer le flux » pour créer un fichier CSV mis à jour.
4.  Téléchargez le fichier CSV généré.
5.  Téléchargez ce nouveau fichier CSV sur votre Gestionnaire de publicités Facebook pour actualiser votre catalogue de produits. Facebook propose également des options pour planifier des récupérations automatiques à partir d'une URL, qui peuvent être configurées une fois que vous avez une URL de flux stable (souvent fournie par le module ou la configuration de votre serveur).

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Sélectionner la langue pour l'exportation | Votre langue principale | Détermine la langue des noms/descriptions de produits dans le flux. |
| | Sélectionner la devise pour l'exportation | Votre devise principale | Détermine la devise des prix dans le flux. |
| | Exporter uniquement les produits actifs | OUI | Inclut uniquement les produits actifs, empêchant les publicités pour les articles indisponibles. |
| | Exporter uniquement les produits en stock | OUI | Inclut uniquement les produits en stock, empêchant les publicités pour les articles en rupture de stock. |
| | Exporter les combinaisons de produits | OUI | Exporte chaque variation de produit (taille, couleur) comme un article unique pour des publicités granulaires. |
| | Identification du produit (champ ID) | ID du produit | Définit l'identifiant unique des produits dans le flux. |
| | Champ Catégorie de produit | Catégorie de produit Google (si disponible) | Spécifie les données de catégorie pour Facebook. |
| | Champ Marque du produit | Nom du fabricant | Spécifie les données de marque pour Facebook. |
| | Champ Type de produit | Catégorie de produit Google (si disponible) | Spécifie les données de type de produit pour Facebook. |
| | Champ Image du produit | Image de combinaison (si disponible) | Assure l'image correcte pour les variations de produit. |
| | Champ Description du produit | Description | Utilise la description complète du produit pour le flux. |
| | Champ Description courte du produit | Description courte | Utilise la description courte du produit pour le flux. |
| | Délimiteur CSV | Virgule (,) | Caractère séparant les valeurs dans le fichier CSV. |
| | Supprimer les images du flux | NON | Inclut les liens d'image dans le flux (essentiel pour les publicités). |
| | Exclure des produits par ID | Vide | Liste d'ID de produits séparés par des virgules à exclure du flux. |
| | Bouton Générer le flux | Cliquer après la finalisation des paramètres | Crée le fichier CSV du catalogue de produits. |
| | Bouton Télécharger le flux | Cliquer après la génération | Télécharge le fichier CSV sur votre ordinateur. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : Mon fichier de flux généré est vide ou contient très peu de produits.**
R :

-   **Vérifiez « Exporter uniquement les produits actifs » et « Exporter uniquement les produits en stock » :** Assurez-vous que ces options ne sont pas trop restrictives si vous vous attendez à de nombreux produits.
-   **Vérifiez la langue et la devise sélectionnées :** Assurez-vous que les produits existent pour la langue sélectionnée et qu'ils ont des prix dans la devise sélectionnée.
-   **Vérifiez la visibilité des produits :** Vos produits sont-ils réellement visibles dans le contexte de boutique sélectionné (si vous avez activé le multi-boutique) ?
-   **Videz le cache Smarty :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ». Parfois, d'anciennes données peuvent interférer.

**Q : Facebook rejette mon flux ou affiche des erreurs.**
R :

-   **Vérifiez le délimiteur CSV :** Assurez-vous qu'il correspond à ce que Facebook attend (généralement une virgule).
-   **Examinez les messages d'erreur de Facebook :** Le Gestionnaire de publicités Facebook fournit des rapports d'erreur détaillés. Portez une attention particulière aux champs qui posent problème (par exemple, liens d'image manquants, prix invalides).
-   **Vérifiez les liens d'image :** Assurez-vous que vos images de produits sont accessibles au public et que les URL sont correctes. Si vous avez un SSL (HTTPS), assurez-vous que les liens d'image sont également HTTPS.
-   **Vérifiez les caractères spéciaux :** Parfois, des caractères inhabituels dans les noms ou descriptions de produits peuvent causer des problèmes d'analyse.
-   **Assurez des ID uniques :** Le paramètre « Identification du produit » est crucial. Chaque élément du flux (en particulier les combinaisons) a besoin d'un `id` unique.

**Q : Mes images de produits n'apparaissent pas dans le flux Facebook.**
R :

-   **Vérifiez le paramètre « Supprimer les images du flux » :** Assurez-vous qu'il est réglé sur **NON**.
-   **Vérifiez les URL des images :** Ouvrez quelques liens d'image du CSV généré dans votre navigateur. Se chargent-ils correctement ? Sont-ils accessibles depuis l'extérieur de votre réseau ?
-   **Images de combinaison :** Si vous utilisez des images de combinaison, assurez-vous qu'elles sont correctement attribuées à vos combinaisons de produits dans PrestaShop.

**Q : À quelle fréquence dois-je générer et télécharger un nouveau flux ?**
R :

-   Cela dépend de la fréquence à laquelle votre catalogue de produits change.
-   **Quotidiennement :** Recommandé pour la plupart des boutiques, surtout si vous avez des changements de stock fréquents, des mises à jour de prix ou de nouvelles additions de produits.
-   **Hebdomadairement :** Acceptable pour les boutiques avec un catalogue très stable.
-   **Récupération automatisée :** La meilleure pratique est de configurer Facebook pour récupérer automatiquement le flux à partir d'une URL. Ce module génère le flux à la demande, vous pourriez donc avoir besoin d'une tâche cron pour déclencher la génération et rendre le fichier disponible à une URL cohérente pour que Facebook le récupère.

**Q : Le module n'apparaît pas dans ma liste de modules ou je ne peux pas le configurer.**
R :

-   **Re-téléchargez :** Essayez de re-télécharger le fichier ZIP du module via le Gestionnaire de modules.
-   **Vérifiez les permissions :** Assurez-vous que le dossier du module (`/modules/pixelfeed/`) et son contenu ont les permissions de fichier correctes (généralement 755 pour les dossiers, 644 pour les fichiers).
-   **Journaux d'erreurs :** Vérifiez votre mode de débogage PrestaShop et les journaux d'erreurs du serveur pour toute erreur PHP lors de l'installation ou de la configuration.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé du module « Export catalog for facebook pixel dynamic ads » pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module suit un modèle MVC (Modèle-Vue-Contrôleur) PrestaShop standard, se concentrant principalement sur les fonctionnalités administratives pour générer un flux de produits. Il s'appuie sur les classes `Product` et `Combination` de PrestaShop pour extraire les données, puis formate ces données dans un fichier CSV compatible avec la spécification du catalogue des publicités dynamiques de Facebook. Le fichier principal du module (`index.php`) agit comme point d'entrée pour la configuration, tandis que les contrôleurs d'administration dédiés gèrent la logique complexe d'extraction de données et de génération de flux. Des contrôleurs frontaux sont présents, probablement pour servir le flux généré ou pour des requêtes AJAX spécifiques.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   `controllers/front/feed.php`
    *   **Nom de la classe :** `PixelfeedFeedModuleFrontController` (ou similaire, étendant `ModuleFrontController`)
    *   **Responsabilité :** Ce contrôleur est probablement responsable de la diffusion du fichier de flux CSV généré via une URL publique. Il gérerait les requêtes vers une route spécifique (par exemple, `votreboutique.com/module/pixelfeed/feed`) et produirait directement le contenu CSV. C'est crucial pour les récupérations planifiées de Facebook.
-   `controllers/front/index.php`
    *   **Nom de la classe :** `PixelfeedIndexModuleFrontController` (ou similaire, étendant `ModuleFrontController`)
    *   **Responsabilité :** Il peut s'agir d'un espace réservé ou d'un contrôleur pour une action front-office très spécifique, non liée au flux, bien que la fonction principale du module soit la génération de flux en back-office. Il pourrait potentiellement gérer les requêtes AJAX liées à l'état du flux ou d'autres interactions mineures.

#### Contrôleurs d'administration Back-Office

-   `controllers/admin/AdminExportProductsFeed.php`
    *   **Nom de la classe :** `AdminExportProductsFeedController` (étendant `ModuleAdminController`)
    *   **Nom de l'onglet :** Ce contrôleur est le cœur de l'interface administrative du module. C'est l'écran de configuration principal où les marchands interagissent avec les paramètres et déclenchent la génération du flux.
    *   **Entité gérée :** Il ne gère pas directement une seule entité `ObjectModel`, mais orchestre plutôt la récupération et le traitement des données `Product` et `Combination` du cœur de PrestaShop.
    *   **Fonctionnalité clé :**
        *   Gère l'affichage du formulaire de configuration (`renderForm`).
        *   Traite les soumissions de formulaire (`postProcess`) pour enregistrer les paramètres du module (par exemple, langue, devise, options d'exportation).
        *   Déclenche la logique d'extraction de données et de génération CSV.
        *   Gère l'exclusion des produits.
        *   Les champs de formulaire et les colonnes listés dans le dossier du module (`ID`, `item_group_id`, `Title`, etc.) représentent la *structure de sortie* du flux, pas nécessairement des champs de saisie directs sur le formulaire d'administration, bien que de nombreux paramètres influencent ces colonnes de sortie.
        *   Clés de configuration associées : `pf_tree`, `PS_LANG_DEFAULT`, `PS_CURRENCY_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `pf_pixelfeed_products`, `pf_remember_settings`, `pf_export_not_group_combinations`, `pf_export_active`, `pf_export_instock`, `pf_export_identification`, `pf_export_category`, `pf_export_manufacturers_default`, `pf_export_type`, `pf_export_img`, `pf_export_manufacturers`, `pf_export_description_what`, `pf_export_short_description_what`, `pf_export_suppliers`, `pf_export_delimiter`, `pf_delete_images`. Ce sont les clés `Configuration` utilisées pour stocker les paramètres du module.
-   `controllers/admin/index.php`
    *   **Nom de la classe :** `PixelfeedAdminIndexController` (ou similaire, étendant `ModuleAdminController`)
    *   **Nom de l'onglet :** Il peut s'agir d'un contrôleur d'administration secondaire, potentiellement pour un tableau de bord ou une vue de gestion plus simple, ou il pourrait s'agir d'un fichier hérité. Étant donné que `AdminExportProductsFeedController` gère la logique principale, ce `index.php` pourrait être une redirection ou une page d'atterrissage très basique dans la section d'administration.

### 4.3 Classes et modèles de base (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela implique que la logique principale d'extraction de données et de génération de flux est probablement contenue dans le fichier principal du module (`pixelfeed/index.php`) et le `AdminExportProductsFeedController`. Il utilise directement les classes `Product`, `Combination`, `Category`, `Manufacturer`, `Image` et `Tools` de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

-   `pixelfeed/lib/searchTool/views/js/autocomplete.js`
    *   **Portée :** Back-office.
    *   **Fonctionnalité :** Fournit probablement une fonctionnalité d'autocomplétion pour les champs de saisie dans la configuration d'administration, tels que le champ « Exclure des produits par ID ». Il se lierait aux éléments d'entrée, effectuerait des appels AJAX pour rechercher des produits et afficherait des suggestions.
-   `pixelfeed/views/js/admin-app.js`
    *   **Portée :** Back-office.
    *   **Fonctionnalité :** C'est le fichier JavaScript principal pour l'interface d'administration du module. Il gérerait :
        *   La validation et la soumission des formulaires.
        *   Les requêtes AJAX pour générer le flux (vers `AdminExportProductsFeedController`).
        *   L'affichage des indicateurs de chargement ou des messages de succès/erreur.
        *   Potentiellement des mises à jour dynamiques de l'interface utilisateur basées sur les options sélectionnées.
        *   Les interactions avec Fancybox (si utilisé pour la sélection de catégories ou similaire).

### 4.5 Feuilles de style CSS (`views/css/`)

-   `pixelfeed/lib/searchTool/views/css/autocomplete.css`
    *   **Portée :** Style d'administration Back-office.
    *   **Fonctionnalité :** Style le menu déroulant d'autocomplétion et les champs de saisie, assurant une apparence cohérente dans le back-office de PrestaShop.
-   `pixelfeed/views/admin-theme.css`
    *   **Portée :** Style d'administration Back-office.
    *   **Fonctionnalité :** Fournit un style général pour la page de configuration du module, garantissant qu'il s'intègre bien au thème du back-office de PrestaShop. Cela peut inclure la mise en page, les styles de boutons et le style des éléments de formulaire.
-   `pixelfeed/views/css/admin-app.css`
    *   **Portée :** Style d'administration Back-office.
    *   **Fonctionnalité :** Style spécifique pour les éléments d'interface utilisateur personnalisés du module, tels que la progression de la génération du flux, les alertes ou tout widget personnalisé sur la page de configuration.

### 4.6 Structure des templates Smarty (`views/templates/`)

Le module utilise principalement des templates Smarty pour son interface Back Office.

#### Templates d'administration (`views/templates/admin/`)

-   `pixelfeed/views/templates/admin/dashboard.tpl`
    *   **Objectif :** Pourrait être un aperçu de type tableau de bord pour le module, affichant potentiellement l'état du flux, la dernière date de génération ou des liens rapides.
-   `pixelfeed/views/templates/admin/feeds.tpl`
    *   **Objectif :** Probablement le template principal pour afficher les options de génération de flux et les résultats, éventuellement y compris une liste des flux générés ou un journal.
-   `pixelfeed/views/templates/admin/form-chrome.tpl`
    *   **Objectif :** Un wrapper générique ou un template structurel pour les formulaires dans l'interface d'administration, assurant une mise en page et un style cohérents.
-   `pixelfeed/views/templates/admin/layout.tpl`
    *   **Objectif :** Le template de mise en page global pour les pages d'administration du module, définissant la structure générale, l'en-tête et le pied de page.

#### Autres templates (`views/`)

-   `pixelfeed/lib/searchTool/views/scripts.tpl`
    *   **Objectif :** Inclut le JavaScript pour l'outil de recherche, probablement rendu à la fin du corps HTML ou dans une section spécifique.
-   `pixelfeed/views/categories-fancybox.tpl`
    *   **Objectif :** Template pour une modale Fancybox, éventuellement utilisée pour sélectionner les catégories à inclure/exclure du flux, ou pour afficher des arborescences de catégories.
-   `pixelfeed/views/exclude-products.tpl`
    *   **Objectif :** Template pour la section où les produits peuvent être exclus par ID, incluant potentiellement le champ de saisie d'autocomplétion.
-   `pixelfeed/views/google_lang_links.tpl`
    *   **Objectif :** Pourrait être lié à l'affichage de liens ou d'informations spécifiques à la langue, éventuellement pour les catégories de produits Google.
-   `pixelfeed/views/returnAlert.tpl`
    *   **Objectif :** Un template pour afficher des messages de succès, d'erreur ou d'avertissement à l'utilisateur dans l'interface d'administration.
-   `pixelfeed/views/script-fancybox.tpl`
    *   **Objectif :** Inclut le JavaScript pour l'intégration de Fancybox, souvent pour les pop-ups modales.
-   `pixelfeed/views/script.tpl`
    *   **Objectif :** Inclusions JavaScript générales pour les pages d'administration du module, potentiellement pour des variables globales ou des initialisations.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données

Le dossier du module n'indique aucun fichier SQL personnalisé, suggérant qu'il ne crée pas ses propres tables de base de données dédiées. Tous les paramètres de configuration sont stockés dans la table `ps_configuration` de PrestaShop en utilisant des clés préfixées par `pf_` (par exemple, `pf_export_active`, `pf_export_delimiter`).

#### Tableau des hooks enregistrés

La fonction principale du module est l'exportation de données, et non l'affichage en front-office. Les hooks front-office listés (Header, Columns, Product, Footer) ne sont probablement *pas* utilisés pour une sortie visuelle directe par ce module. Au lieu de cela, ils pourraient être enregistrés pour :

-   **`displayHeader`** : Pour inclure les actifs JavaScript ou CSS nécessaires au contrôleur de flux front-office du module (s'il sert le flux directement).
-   **Hooks `action*`** : Le module utilise probablement des hooks `action` (par exemple, `actionProductUpdate`, `actionProductAdd`) en interne pour vider les caches ou déclencher des invites de régénération dans le back-office lorsque les données produit changent, bien que ceux-ci ne soient pas explicitement listés dans le dossier. La logique principale du module pour générer le flux est généralement déclenchée manuellement ou via une tâche cron, et non directement par un hook front-office.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` des pages front-office. | Potentiellement pour charger JS/CSS pour la diffusion du flux en front-office, ou pour des intégrations très spécifiques et non visuelles. |
| `displayRightColumn` / `displayLeftColumn` | Dans les colonnes latérales des pages front-office. | Peu susceptible d'être utilisé pour la fonction principale de ce module ; éventuellement pour un bloc de débogage ou une fonctionnalité très spécifique non essentielle à la génération de flux. |
| `displayProductAdditionalInfo` / `displayProductButtons` (Page produit) | Sur les pages produit. | Peu susceptible d'être utilisé pour la fonction principale de ce module. |
| `displayFooter` | Dans le pied de page des pages front-office. | Peu susceptible d'être utilisé pour la fonction principale de ce module. |
| (Implicite) `actionProductUpdate` / `actionProductAdd` / `actionProductDelete` | Après les modifications des données produit dans le BO. | Pour invalider les données de flux mises en cache ou inviter l'administrateur à régénérer le flux. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Export catalog for facebook pixel dynamic ads », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
