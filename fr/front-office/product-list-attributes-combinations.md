---
title: "Attributs de liste de produits (combinaisons) - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Attributs de liste de produits (combinaisons)' par MyPresta.eu."
sidebar:
  label: "Attributs de liste de produits (combinaisons)"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Product list attributes (combinations) sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-list-attributes-combinations.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/product-list-attributes-combinations/)
>
> ---


# Attributs de liste de produits (combinaisons)

## 1. Exigences et compatibilité

-   **Versions PrestaShop prises en charge :** PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilité PHP :** PHP 5.6 - 8.5
-   **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises, qui sont généralement disponibles sur la plupart des environnements d'hébergement web modernes.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Après l'installation, cliquer sur "Configurer" vous mènera à la page principale des paramètres du module "Attributs de liste de produits (combinaisons)". C'est ici que vous contrôlez la manière dont les combinaisons sont affichées sur vos listes de produits.

#### Paramètres généraux

-   **Afficher les combinaisons sur la liste de produits :**
    -   **Ce que fait ce paramètre :** C'est l'interrupteur principal du module. Il contrôle si les combinaisons de produits sont affichées sur les pages de liste de produits.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé (OUI) :* Le module injectera l'interface de sélection de combinaison dans vos modèles de liste de produits, permettant aux clients de choisir les variantes directement.
        -   *Lorsque désactivé (NON) :* Le module sera inactif sur le front office, et les listes de produits se comporteront comme PrestaShop standard, obligeant les clients à visiter la page du produit pour sélectionner les combinaisons.
    -   **Valeur recommandée :** OUI (pour utiliser la fonctionnalité principale du module).
    -   **Scénario / exemple de marchand :** Si vous souhaitez offrir une expérience d'achat plus rapide, activez ceci. Si vous préférez que les clients atterrissent toujours sur la page du produit pour plus de détails, désactivez-le.

-   **Afficher le bouton "Ajouter au panier" :**
    -   **Ce que fait ce paramètre :** Détermine si un bouton "Ajouter au panier" est affiché à côté des sélecteurs de combinaison sur la liste de produits.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé (OUI) :* Un bouton "Ajouter au panier" apparaîtra à côté des options de combinaison. Une fois qu'un client sélectionne une combinaison, il peut cliquer sur ce bouton pour l'ajouter à son panier.
        -   *Lorsque désactivé (NON) :* Les sélecteurs de combinaison seront toujours visibles, mais les clients devront cliquer sur l'image ou le nom du produit pour accéder à la page du produit afin de l'ajouter au panier. Cela peut être utile si vous souhaitez afficher les options mais encourager quand même les visites de la page du produit.
    -   **Valeur recommandée :** OUI (pour un maximum de commodité et de conversion).
    -   **Scénario / exemple de marchand :** Pour une expérience d'achat rapide, activez ceci. Si vos produits nécessitent une lecture ou une personnalisation approfondie avant l'achat, vous pouvez le désactiver pour guider les clients vers la page du produit.

-   **Afficher le champ de quantité :**
    -   **Ce que fait ce paramètre :** Contrôle si un champ de saisie de quantité est affiché à côté du bouton "Ajouter au panier" sur la liste de produits.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé (OUI) :* Les clients peuvent spécifier la quantité d'une combinaison choisie qu'ils souhaitent ajouter à leur panier directement depuis la liste de produits.
        -   *Lorsque désactivé (NON) :* Le bouton "Ajouter au panier" ajoutera une seule unité de la combinaison sélectionnée. Les clients devront alors ajuster les quantités dans le panier ou sur la page du produit.
    -   **Valeur recommandée :** OUI (pour la plupart des boutiques, car cela offre plus de flexibilité).
    -   **Scénario / exemple de marchand :** Si les clients achètent souvent plusieurs unités du même article (par exemple, chaussettes, papeterie), activez ceci. Si vos produits sont généralement achetés un par un, vous pouvez le désactiver pour un aspect plus épuré.

-   **Afficher la référence du produit :**
    -   **Ce que fait ce paramètre :** Affiche ou masque le numéro de référence du produit (SKU) à côté des options de combinaison.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé (OUI) :* La référence du produit sera visible, ce qui peut être utile pour les clients qui suivent des articles spécifiques ou pour les clients B2B.
        -   *Lorsque désactivé (NON) :* La référence ne sera pas affichée, ce qui conduit à une interface plus propre et moins encombrée.
    -   **Valeur recommandée :** NON (sauf si votre public cible bénéficie spécifiquement de la visualisation des références).
    -   **Scénario / exemple de marchand :** Pour les boutiques B2B ou les produits techniques où les clients commandent souvent par SKU, activez ceci. Pour la vente au détail générale, ce n'est généralement pas nécessaire.

-   **Afficher l'EAN13/JAN du produit :**
    -   **Ce que fait ce paramètre :** Affiche ou masque le numéro de code-barres EAN13 ou JAN du produit.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé (OUI) :* L'EAN13/JAN sera visible, ce qui peut être utile pour les clients qui ont besoin de recouper des produits à l'aide de ces identifiants.
        -   *Lorsque désactivé (NON) :* L'EAN13/JAN ne sera pas affiché.
    -   **Valeur recommandée :** NON (similaire à la référence, n'activez que s'il y a un besoin client spécifique).
    -   **Scénario / exemple de marchand :** Rarement nécessaire pour l'affichage en front-office, mais pourrait être utile pour des niches spécifiques ou le B2B.

-   **Afficher l'UPC du produit :**
    -   **Ce que fait ce paramètre :** Affiche ou masque le numéro de code-barres UPC du produit.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé (OUI) :* L'UPC sera visible.
        -   *Lorsque désactivé (NON) :* L'UPC ne sera pas affiché.
    -   **Valeur recommandée :** NON (similaire à l'EAN13/JAN).
    -   **Scénario / exemple de marchand :** Similaire à l'EAN13/JAN, généralement pas une exigence du front-office pour la plupart des détaillants.

-   **Afficher le poids du produit :**
    -   **Ce que fait ce paramètre :** Affiche ou masque le poids du produit à côté des options de combinaison.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé (OUI) :* Le poids du produit sera visible, ce qui peut être important pour les clients soucieux des frais d'expédition ou de la manutention.
        -   *Lorsque désactivé (NON) :* Le poids ne sera pas affiché.
    -   **Valeur recommandée :** NON (sauf si le poids est un facteur critique pour vos produits).
    -   **Scénario / exemple de marchand :** Pour les produits où le poids est un facteur d'achat important (par exemple, produits en vrac, pièces de machines lourdes), activez ceci.

-   **Afficher le prix du produit :**
    -   **Ce que fait ce paramètre :** Contrôle si le prix de la combinaison sélectionnée est dynamiquement mis à jour et affiché sur la liste de produits.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé (OUI) :* Lorsqu'un client sélectionne différentes combinaisons, le prix affiché se mettra à jour pour refléter le prix de la combinaison spécifique (y compris les impacts de prix des attributs).
        -   *Lorsque désactivé (NON) :* Le prix affiché sur la liste de produits restera le prix de base du produit, et les clients pourraient avoir besoin de déduire le prix de la combinaison ou d'aller sur la page du produit.
    -   **Valeur recommandée :** OUI (crucial pour la transparence et l'achat éclairé).
    -   **Scénario / exemple de marchand :** Activez toujours ceci pour une tarification claire. Si désactivé, les clients pourraient être confus par les changements de prix à la caisse.

-   **Afficher la disponibilité du produit :**
    -   **Ce que fait ce paramètre :** Affiche ou masque l'état de disponibilité du stock pour la combinaison sélectionnée (par exemple, "En stock", "Hors stock", "Derniers articles !").
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé (OUI) :* Les clients verront l'état du stock, ce qui les aidera à prendre des décisions d'achat et à éviter la frustration d'essayer de commander des articles en rupture de stock.
        -   *Lorsque désactivé (NON) :* L'état du stock ne sera pas affiché, ce qui pourrait amener les clients à tenter d'ajouter des articles en rupture de stock à leur panier.
    -   **Valeur recommandée :** OUI (fortement recommandé pour gérer les attentes des clients).
    -   **Scénario / exemple de marchand :** Essentiel pour toute boutique afin d'éviter les commandes d'articles indisponibles. Toujours activer.

-   **Afficher la description du produit :**
    -   **Ce que fait ce paramètre :** Affiche ou masque une courte description du produit sous les combinaisons.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé (OUI) :* Une brève description du produit apparaîtra, offrant plus de contexte sans nécessiter un clic sur la page du produit.
        -   *Lorsque désactivé (NON) :* La description ne sera pas affichée, ce qui maintient la liste de produits concise.
    -   **Valeur recommandée :** NON (les listes de produits sont généralement destinées à une navigation rapide ; les descriptions détaillées appartiennent à la page du produit).
    -   **Scénario / exemple de marchand :** Si vous avez des descriptions très courtes et percutantes qui facilitent les décisions rapides, vous pouvez activer ceci. Sinon, laissez-le désactivé pour éviter l'encombrement.

-   **Afficher la description courte du produit :**
    -   **Ce que fait ce paramètre :** Similaire à "Afficher la description du produit", mais spécifiquement pour le champ de description courte.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé (OUI) :* La description courte du produit sera visible.
        -   *Lorsque désactivé (NON) :* La description courte ne sera pas affichée.
    -   **Valeur recommandée :** NON (pour les mêmes raisons que la description complète).
    -   **Scénario / exemple de marchand :** À utiliser avec parcimonie, uniquement si vos descriptions courtes sont extrêmement concises et cruciales pour l'achat en vue liste.

-   **Afficher les images du produit :**
    -   **Ce que fait ce paramètre :** Détermine si l'image du produit se met à jour dynamiquement lorsqu'un client sélectionne une combinaison différente (par exemple, la sélection d'une chemise "bleue" affiche l'image de la chemise bleue).
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé (OUI) :* L'image principale du produit sur la liste changera pour refléter l'image associée à la combinaison sélectionnée. Cela fournit un riche retour visuel.
        -   *Lorsque désactivé (NON) :* L'image du produit restera statique, affichant l'image par défaut du produit quelle que soit la combinaison sélectionnée.
    -   **Valeur recommandée :** OUI (fortement recommandé pour une confirmation visuelle et une meilleure expérience utilisateur).
    -   **Scénario / exemple de marchand :** Crucial pour les vêtements, l'électronique ou tout produit où la représentation visuelle de la variante est importante.

-   **Afficher les attributs du produit comme :**
    -   **Ce que fait ce paramètre :** C'est un paramètre crucial qui définit la manière dont les options de combinaison (par exemple, taille, couleur) sont présentées au client.
    -   **Effet de la modification de ce paramètre :**
        -   *Liste déroulante :* Les attributs apparaîtront sous forme d'éléments `<select>` HTML standard. C'est compact et adapté à de nombreuses options.
        -   *Boutons radio :* Les attributs apparaîtront sous forme de boutons radio. Bon pour un petit nombre d'options distinctes.
        -   *Sélecteur de couleurs :* Si vos attributs sont définis comme de type "couleur" dans PrestaShop, cela les affichera sous forme d'échantillons de couleur cliquables.
    -   **Valeur recommandée :**
        -   *Sélecteur de couleurs* pour les attributs de couleur.
        -   *Liste déroulante* pour les attributs avec de nombreuses options (par exemple, tailles S-XXL).
        -   *Boutons radio* pour les attributs avec peu d'options distinctes (par exemple, "Oui/Non", "Avec/Sans").
    -   **Scénario / exemple de marchand :** Pour un magasin de vêtements, vous utiliseriez probablement le "Sélecteur de couleurs" pour les couleurs et la "Liste déroulante" pour les tailles. Pour un produit simple avec deux options comme "Emballé cadeau : Oui/Non", les boutons radio pourraient être les meilleurs.

-   **Afficher les attributs du produit pour :**
    -   **Ce que fait ce paramètre :** Vous permet de spécifier quels attributs de produit doivent avoir leurs combinaisons affichées sur la liste de produits. Vous pouvez sélectionner des groupes d'attributs spécifiques (par exemple, "Taille", "Couleur", "Matériau").
    -   **Effet de la modification de ce paramètre :**
        -   *Groupes d'attributs sélectionnés :* Seules les combinaisons impliquant les groupes d'attributs choisis seront affichées. Par exemple, si vous sélectionnez "Couleur" et "Taille", les clients verront les options pour les couleurs et les tailles.
        -   *Aucune sélection :* Si rien n'est sélectionné, le module peut par défaut afficher tous les attributs ou aucun, selon la logique interne du module. Il est préférable de sélectionner explicitement.
    -   **Valeur recommandée :** Sélectionnez tous les groupes d'attributs pertinents qui définissent vos combinaisons de produits.
    -   **Scénario / exemple de marchand :** Si vous vendez des T-shirts de différentes couleurs et tailles, sélectionnez "Couleur" et "Taille". Si vous avez également un attribut "Matériau" mais que vous ne voulez pas l'afficher sur la liste, laissez-le non sélectionné.

-   **Hook pour afficher le module :**
    -   **Ce que fait ce paramètre :** Détermine où les sélecteurs de combinaison seront injectés sur vos pages de liste de produits.
    -   **Effet de la modification de ce paramètre :**
        -   `displayProductListFunctionalButtons` : Ce hook est généralement situé près du bouton "Ajouter au panier" ou d'autres éléments fonctionnels sur les articles de la liste de produits.
        -   `displayProductListReviews` : Souvent près des étoiles d'évaluation ou des nombres d'évaluations.
        -   `displayProductListPrice` : Généralement près du prix du produit.
        -   `displayProductListExtraContent` : Un hook général pour du contenu supplémentaire, souvent en bas de la fiche produit.
        -   `displayProductListFooter` : Tout en bas de la fiche produit.
    -   **Valeur recommandée :** `displayProductListFunctionalButtons` ou `displayProductListExtraContent` sont des choix courants, mais cela dépend fortement de la mise en page de votre thème. Vous devrez peut-être expérimenter pour trouver le meilleur emplacement visuel.
    -   **Scénario / exemple de marchand :** Si votre thème a une zone propre sous le nom et le prix du produit, `displayProductListFunctionalButtons` pourrait bien s'adapter. Si vous voulez que les options apparaissent plus en évidence, `displayProductListExtraContent` pourrait être meilleur.

-   **Exclure des produits du module :**
    -   **Ce que fait ce paramètre :** Vous permet de spécifier des produits individuels par leur ID qui ne doivent *pas* afficher de combinaisons sur la liste de produits, même si le module est généralement activé.
    -   **Effet de la modification de ce paramètre :**
        -   *Saisie des ID de produit (séparés par des virgules) :* Les produits spécifiés reviendront au comportement PrestaShop standard sur les listes de produits, nécessitant un clic sur la page du produit pour la sélection des combinaisons.
        -   *Laisser vide :* Tous les produits avec des combinaisons les afficheront sur la liste.
    -   **Valeur recommandée :** Laisser vide, sauf si vous avez des produits spécifiques qui nécessitent une visite complète de la page du produit.
    -   **Scénario / exemple de marchand :** Vous pourriez avoir quelques produits complexes avec de nombreux attributs, ou des produits qui nécessitent un configurateur détaillé, où vous préférez que les clients atterrissent d'abord sur la page du produit.

-   **Exclure des catégories du module :**
    -   **Ce que fait ce paramètre :** Vous permet de spécifier des catégories par leur ID qui ne doivent *pas* afficher de combinaisons sur leurs listes de produits.
    -   **Effet de la modification de ce paramètre :**
        -   *Saisie des ID de catégorie (séparés par des virgules) :* Les produits de ces catégories n'afficheront pas de combinaisons sur leurs pages de liste respectives.
        -   *Laisser vide :* Toutes les catégories afficheront les combinaisons de produits.
    -   **Valeur recommandée :** Laisser vide, sauf si vous avez des catégories spécifiques où cette fonctionnalité n'est pas souhaitée.
    -   **Scénario / exemple de marchand :** Si vous avez une catégorie "Liquidation" où tous les produits sont à variante unique et que vous souhaitez garder l'affichage très minimal, vous pouvez l'exclure.

#### 2.1.1 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
|---|---|---|---|
| Configuration du module | Afficher les combinaisons sur la liste de produits | OUI | Interrupteur principal pour activer/désactiver l'affichage des combinaisons sur les listes de produits. |
| Configuration du module | Afficher le bouton "Ajouter au panier" | OUI | Affiche un bouton "Ajouter au panier" à côté des combinaisons pour un achat direct. |
| Configuration du module | Afficher le champ de quantité | OUI | Permet aux clients de sélectionner la quantité directement sur la liste de produits. |
| Configuration du module | Afficher la référence du produit | NON | Affiche/masque le SKU du produit. |
| Configuration du module | Afficher l'EAN13/JAN du produit | NON | Affiche/masque l'EAN13/JAN du produit. |
| Configuration du module | Afficher l'UPC du produit | NON | Affiche/masque l'UPC du produit. |
| Configuration du module | Afficher le poids du produit | NON | Affiche/masque le poids du produit. |
| Configuration du module | Afficher le prix du produit | OUI | Met à jour dynamiquement le prix en fonction de la combinaison sélectionnée. |
| Configuration du module | Afficher la disponibilité du produit | OUI | Affiche l'état du stock pour la combinaison sélectionnée. |
| Configuration du module | Afficher la description du produit | NON | Affiche/masque la description complète du produit. |
| Configuration du module | Afficher la description courte du produit | NON | Affiche/masque la description courte du produit. |
| Configuration du module | Afficher les images du produit | OUI | Met à jour dynamiquement l'image du produit en fonction de la combinaison sélectionnée. |
| Configuration du module | Afficher les attributs du produit comme | Liste déroulante, Radio, Sélecteur de couleurs | Définit la présentation visuelle des options d'attribut. |
| Configuration du module | Afficher les attributs du produit pour | Sélectionner les groupes pertinents | Spécifie les groupes d'attributs à afficher. |
| Configuration du module | Hook pour afficher le module | `displayProductListFunctionalButtons` | Détermine l'emplacement visuel du module sur les fiches produit. |
| Configuration du module | Exclure des produits du module | Laisser vide | ID de produits séparés par des virgules à exclure de la fonctionnalité. |
| Configuration du module | Exclure des catégories du module | Laisser vide | ID de catégories séparés par des virgules à exclure de la fonctionnalité. |

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Ce module utilise des contrôleurs d'administration personnalisés pour la gestion interne, mais ceux-ci ne sont généralement pas directement accessibles par le marchand pour la configuration quotidienne. Ils sont principalement destinés aux opérations internes du module ou au débogage avancé.

#### 2.2.1 AdminPlaSearchController (Back Office > Modules > Attributs de liste de produits (combinaisons) > Configuration de la recherche)
-   **Nom de l'écran et emplacement du menu :** Ce contrôleur est probablement utilisé pour la configuration de la recherche interne ou la gestion des données liées à la manière dont les combinaisons sont indexées ou récupérées. Il peut ne pas avoir d'élément de menu direct et visible pour le marchand, ou il pourrait s'agir d'un onglet interne dans la configuration principale du module.
-   **Actions et paramètres disponibles :** Cet écran présenterait généralement une vue en grille ou en liste de données (par exemple, produits indexés, mappages d'attributs) et pourrait offrir des actions comme "Reconstruire l'index", "Vider le cache" ou "Modifier les paramètres de recherche".
-   **Effet des modifications :** Les modifications ici auraient un impact sur les performances ou la précision de l'affichage des combinaisons, en particulier dans les grands catalogues. Des paramètres incorrects pourraient entraîner l'absence d'affichage des combinaisons ou un chargement lent.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Les marchands n'ont généralement pas besoin d'interagir avec cet écran, sauf avis du support ou pour un dépannage avancé. La page de configuration principale du module gère tous les paramètres destinés à l'utilisateur.

#### 2.2.2 index.php (pla/controllers/admin/index.php)
-   **Nom de l'écran et emplacement du menu :** Ce fichier `index.php` dans le répertoire du contrôleur `admin` est une pratique courante de PrestaShop pour empêcher la liste des répertoires. Il ne représente généralement pas un écran visible par l'utilisateur, mais assure plutôt la sécurité et le routage approprié pour les autres contrôleurs d'administration du module.
-   **Actions et paramètres disponibles :** Aucune action ou paramètre directement accessible par le marchand.
-   **Effet des modifications :** Aucun effet direct sur l'affichage de la boutique ou les données, car il s'agit d'un fichier structurel.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Aucune interaction requise.

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : Les combinaisons n'apparaissent pas sur ma liste de produits. Que dois-je faire ?**
R :
1.  **Vérifier l'état du module :** Allez dans **Modules > Gestionnaire de modules**, trouvez "Attributs de liste de produits (combinaisons)", et assurez-vous qu'il est installé et activé.
2.  **Vérifier la configuration du module :** Allez sur la page de configuration du module. Assurez-vous que "Afficher les combinaisons sur la liste de produits" est défini sur OUI.
3.  **Vérifier les groupes d'attributs :** Assurez-vous d'avoir sélectionné les bons groupes "Afficher les attributs du produit pour" (par exemple, "Taille", "Couleur").
4.  **Vérifier les exclusions :** Vérifiez que le produit ou la catégorie que vous testez n'est pas listé dans "Exclure des produits du module" ou "Exclure des catégories du module".
5.  **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions antérieures). Parfois, d'anciens fichiers mis en cache empêchent l'affichage du nouveau contenu du module.
6.  **Compatibilité du thème :** Votre thème pourrait être fortement personnalisé et ne pas utiliser les hooks PrestaShop standard. Essayez de changer le paramètre "Hook pour afficher le module" pour un autre hook (par exemple, `displayProductListExtraContent`) et videz le cache. Si les problèmes persistent, contactez votre webmaster ou le support MyPresta.eu.

**Q : Le bouton "Ajouter au panier" ou le champ de quantité ne s'affiche pas.**
R :
1.  **Vérifier la configuration du module :** Assurez-vous que "Afficher le bouton 'Ajouter au panier'" et "Afficher le champ de quantité" sont tous deux définis sur OUI dans la configuration du module.
2.  **Vider le cache :** Videz toujours votre cache PrestaShop après avoir effectué des modifications de configuration.

**Q : L'image du produit ne change pas lorsque je sélectionne une combinaison différente.**
R :
1.  **Vérifier la configuration du module :** Assurez-vous que "Afficher les images du produit" est défini sur OUI.
2.  **Images du produit :** Vérifiez que vos combinaisons de produits ont bien des images associées. Dans la page de back office de votre produit, allez dans l'onglet "Combinaisons" et assurez-vous que chaque combinaison a des images liées.
3.  **Vider le cache :** Videz votre cache PrestaShop.

**Q : Le style (couleurs, alignement) des combinaisons semble incorrect sur ma boutique.**
R :
Il s'agit généralement d'un conflit CSS avec votre thème.
1.  **Vider le cache :** Parfois, vider le cache aide.
2.  **Personnalisation du thème :** Votre thème peut avoir des règles de style spécifiques qui remplacent ou entrent en conflit avec le CSS par défaut du module. Cela nécessite qu'un webmaster ou un développeur inspecte le CSS et apporte des ajustements dans la feuille de style de votre thème. Le module fournit ses propres fichiers CSS, mais les thèmes peuvent toujours les remplacer.

**Q : Ce module fonctionne-t-il avec les boutiques multilingues ?**
R : Oui, le module est conçu pour être compatible avec les fonctionnalités multilingues de PrestaShop. Les noms et valeurs des attributs s'afficheront dans la langue du front-office sélectionnée, à condition qu'ils soient correctement traduits dans votre back office PrestaShop (Catalogue > Attributs & Caractéristiques).

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé du module "Attributs de liste de produits (combinaisons)" pour les développeurs et les webmasters.

### 4.1 Vue d'ensemble de l'architecture
Le module suit un modèle MVC (Modèle-Vue-Contrôleur) PrestaShop standard, étendant principalement `Module` pour sa fonctionnalité principale et `ModuleFrontController` pour les interactions AJAX. Il utilise le système de hooks de PrestaShop pour injecter son contenu dans les modèles de liste de produits. La logique principale du module réside dans `index.php` (le fichier principal du module), qui gère l'installation, la désinstallation et la méthode `getContent()` pour la configuration du back-office. L'affichage en front-office est géré via des modèles Smarty rendus via des hooks, avec des interactions dynamiques alimentées par JavaScript et AJAX.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office
-   `controllers/front/ajax.php`
    *   **Nom de la classe et classe parente :** `PlaAjaxModuleFrontController` étend `ModuleFrontController`.
    *   **Responsabilité :** Ce contrôleur gère toutes les requêtes AJAX du front office. Lorsqu'un client interagit avec les sélecteurs de combinaison (par exemple, change une taille ou une couleur), ce contrôleur est responsable de la réception de la requête, de son traitement (par exemple, récupération des prix mis à jour, du stock, des images pour la combinaison sélectionnée) et du renvoi d'une réponse JSON pour mettre à jour le front-end dynamiquement sans rechargement complet de la page. Il est crucial pour l'expérience interactive du module.
-   `controllers/front/index.php`
    *   **Nom de la classe et classe parente :** `PlaIndexModuleFrontController` étend `ModuleFrontController`.
    *   **Responsabilité :** Il s'agit d'un contrôleur frontal de substitution, souvent utilisé pour empêcher la liste des répertoires ou comme solution de repli pour les routes spécifiques au module. Dans le contexte de ce module, il peut ne pas avoir de routage direct et actif, mais sert de pratique PrestaShop standard. L'interaction principale en front-office se fait via `ajax.php`.

#### Contrôleurs d'administration Back-Office
-   `controllers/admin/AdminPlaSearchController.php`
    *   **Nom de la classe et classe parente :** `AdminPlaSearchController` étend `ModuleAdminController`.
    *   **Nom de l'onglet et entité gérée :** Ce contrôleur gère probablement les mécanismes de recherche ou d'indexation internes pour les combinaisons de produits. Il peut ne pas avoir d'entrée de menu directe mais pourrait être accédé en interne par le module pour des tâches comme la reconstruction d'un index de recherche pour les combinaisons. Il gérerait généralement une entité virtuelle liée aux données de recherche plutôt qu'un `ObjectModel` direct.
-   `controllers/admin/index.php`
    *   **Nom de la classe et classe parente :** Pas une classe de contrôleur directe, mais un fichier `index.php` standard.
    *   **Nom de l'onglet et entité gérée :** Ce fichier est une mesure de sécurité pour empêcher la liste des répertoires du dossier `admin`. Il ne représente pas un écran d'administration fonctionnel en soi.

### 4.3 Classes et modèles principaux (`classes/`)
Le dossier du module n'indique aucune classe ou modèle personnalisé dans le répertoire `classes/`. Cela suggère que le module fonctionne principalement en étendant les fonctionnalités de base existantes de PrestaShop (comme `Product`, `Combination`) et utilise des requêtes de base de données directes ou la classe `Db` de PrestaShop pour l'interaction avec les données, plutôt que de définir ses propres entités `ObjectModel`. Toute la logique principale est probablement encapsulée dans le fichier principal du module (`pla/index.php`) et ses contrôleurs.

### 4.4 Actifs JavaScript (`views/js/`)
-   `pla/lib/searchTool/views/js/autocomplete.js`
    *   **Portée :** Potentiellement à la fois Front-office (pour la fonctionnalité de recherche en direct si intégrée) et Back-office (pour les champs de recherche d'administration). Compte tenu de l'objectif du module, il est plus probable qu'il s'agisse d'une configuration de recherche en back-office liée à `AdminPlaSearchController`.
    *   **Détails :** Gère la fonctionnalité d'autocomplétion, probablement pour la recherche de produits ou d'attributs dans la configuration d'administration du module ou une fonction de recherche personnalisée. Il se lierait aux champs de saisie, écouterait les événements `keyup` et effectuerait des appels AJAX pour récupérer des suggestions.
-   `pla/views/templates/js/pla.js`
    *   **Portée :** Front-office.
    *   **Détails :** Il s'agit du fichier JavaScript principal pour la fonctionnalité front-office.
        *   **Écouteurs d'événements :** Lie les événements `change` aux sélecteurs de combinaison (listes déroulantes, boutons radio, sélecteurs de couleurs) sur les articles de la liste de produits.
        *   **Manipulation du DOM :** Met à jour les prix des produits, l'état du stock, les images des produits et les états des boutons "Ajouter au panier" en fonction des combinaisons sélectionnées.
        *   **Appels AJAX :** Effectue des requêtes AJAX vers `controllers/front/ajax.php` pour récupérer les données de combinaison mises à jour (prix, stock, URL de l'image, etc.) lorsqu'une sélection change.
        *   **Initialisation du module :** Contient probablement du code pour initialiser les sélecteurs de combinaison au chargement de la page et les réinitialiser après les mises à jour AJAX (par exemple, défilement infini, filtrage par catégorie).

### 4.5 Feuilles de style CSS (`views/css/`)
-   `pla/css.css`
    *   **Portée :** Probablement Front-office.
    *   **Détails :** Style général pour les éléments d'affichage des combinaisons sur les listes de produits. Contient les styles de base pour les listes déroulantes, les boutons radio, les champs de quantité et les boutons "Ajouter au panier" tels que rendus par le module.
-   `pla/lib/searchTool/views/css/autocomplete.css`
    *   **Portée :** Potentiellement à la fois Front-office et Back-office.
    *   **Détails :** Styles pour la liste de suggestions d'autocomplétion et les champs de saisie, probablement utilisés conjointement avec `autocomplete.js`.
-   `pla/views/templates/css/pla-classic.css`
    *   **Portée :** Front-office.
    *   **Détails :** Style spécifique adapté aux anciens thèmes PrestaShop (par exemple, thème Classic ou structures similaires). Peut contenir des remplacements plus explicites ou des styles de secours.
-   `pla/views/templates/css/pla.css`
    *   **Portée :** Front-office.
    *   **Détails :** Style principal pour les éléments front-office du module, potentiellement pour les versions plus récentes de PrestaShop ou une approche plus générique. Contient des styles pour les wrappers de combinaison, les options d'attribut et les éléments dynamiques.
    *   **Sélecteurs de classes CSS clés :** Les développeurs peuvent s'attendre à ce que des classes comme `.pla-combinations-wrapper`, `.pla-attribute-group`, `.pla-attribute-option`, `.pla-add-to-cart-btn`, `.pla-quantity-input`, `.pla-price-display`, `.pla-availability-status` soient présentes et peuvent les remplacer dans le `custom.css` ou `theme.css` de leur thème.

### 4.6 Structure du modèle Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)
-   `pla/views/templates/hook/pla.tpl`
    *   **Hook :** Principalement destiné aux hooks comme `displayProductListFunctionalButtons`, `displayProductListExtraContent`, etc.
    *   **Sortie :** C'est le modèle principal responsable du rendu des sélecteurs de combinaison, du bouton "Ajouter au panier", du champ de quantité, du prix et de la disponibilité sur chaque article de produit dans la liste de produits. Il itère sur les groupes d'attributs et les valeurs disponibles, générant le HTML approprié (listes déroulantes, boutons radio, échantillons de couleur) en fonction de la configuration du module.

#### Modèles d'administration (`views/templates/admin/`)
-   `pla/views/templates/admin/admin.tpl`
    *   **Objectif :** Ce modèle est utilisé pour la page de configuration principale du module dans le back office de PrestaShop (accessible via `getContent()` dans `pla/index.php`). Il contient les formulaires pour tous les paramètres décrits dans la section 4.1.
-   `pla/views/templates/admin/selectedCa.tpl`
    *   **Objectif :** Probablement un modèle partiel utilisé dans un formulaire ou une grille d'administration pour afficher les catégories sélectionnées (par exemple, pour le paramètre "Exclure des catégories du module"). Il rendrait une liste de catégories sélectionnées, éventuellement avec des options pour les supprimer.
-   `pla/views/templates/admin/selectedProducts.tpl`
    *   **Objectif :** Similaire à `selectedCa.tpl`, mais pour les produits sélectionnés (par exemple, pour le paramètre "Exclure des produits du module"). Il afficherait une liste de produits sélectionnés.

#### Modèles JavaScript (`views/templates/js/`)
-   `pla/views/templates/js/pla_admin.tpl`
    *   **Portée :** Back-office.
    *   **Sortie :** Ce modèle contient probablement du code JavaScript spécifiquement pour le panneau d'administration. Il peut inclure des scripts pour gérer les éléments de formulaire dynamiques, les appels AJAX dans l'administration ou l'initialisation des composants sur la page de configuration du module.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données
Le dossier du module n'indique aucun fichier SQL personnalisé. Cela implique que le module stocke principalement ses paramètres de configuration dans la table `ps_configuration` de PrestaShop.
-   **`ps_configuration`** : Stocke les paramètres du module (par exemple, `PLA_DISPLAY_COMBINATIONS`, `PLA_DISPLAY_ADD_TO_CART`, `PLA_EXCLUDE_PRODUCTS`, `PLA_HOOK_NAME`, etc.). Ces clés sont généralement préfixées par `PLA_` ou `MYPRESTA_PLA_`.

#### Tableau des hooks enregistrés
Le module enregistre et utilise plusieurs hooks PrestaShop pour intégrer ses fonctionnalités.

| Nom du hook | Moment d'exécution | Objectif technique |
|---|---|---|
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Pour inclure les fichiers CSS et JavaScript nécessaires à la fonctionnalité front-office du module. |
| `displayProductListFunctionalButtons` | Dans chaque article de produit sur les pages de liste de produits, généralement près des boutons d'action. | Un hook courant pour injecter les sélecteurs de combinaison et le bouton "Ajouter au panier". |
| `displayProductListReviews` | Dans chaque article de produit sur les pages de liste de produits, souvent près des éléments d'évaluation. | Hook alternatif pour afficher les options de combinaison. |
| `displayProductListPrice` | Dans chaque article de produit sur les pages de liste de produits, près du prix du produit. | Hook alternatif pour afficher les options de combinaison. |
| `displayProductListExtraContent` | Un hook à usage général dans chaque article de produit pour du contenu supplémentaire. | Hook flexible pour injecter les sélecteurs de combinaison, souvent en bas de la fiche produit. |
| `displayProductListFooter` | Tout en bas de chaque article de produit sur les pages de liste de produits. | Un autre hook alternatif pour afficher les options de combinaison. |
| `actionFrontControllerSetMedia` | Avant qu'un contrôleur frontal ne rende son contenu, permettant aux modules d'ajouter des actifs. | Pour charger conditionnellement des actifs JS/CSS spécifiques uniquement lorsque le module en a besoin sur les pages pertinentes. |
| `actionProductUpdate` | Après la mise à jour d'un produit dans le back office. | Potentiellement utilisé pour vider les caches spécifiques au module ou réindexer les données de combinaison de produits si le module dispose d'un mécanisme d'indexation interne. |
| `actionAttributeGroupUpdate` / `actionAttributeUpdate` | Après la mise à jour des groupes d'attributs ou des attributs. | Similaire à `actionProductUpdate`, pour la suppression du cache ou la réindexation. |

## 5. Support officiel et mises à jour
Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe est dédiée à fournir une assistance et à assurer le bon fonctionnement de votre module.
"""
