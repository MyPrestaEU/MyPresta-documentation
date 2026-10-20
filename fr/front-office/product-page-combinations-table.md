---
title: "Tableau des déclinaisons sur la page produit - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Tableau des déclinaisons sur la page produit' par MyPresta.eu."
sidebar:
  label: "Tableau des déclinaisons sur la page produit - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Product page combinations table sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-combinations-table.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/product-page-combinations-table/)
>
> ---


# Tableau des déclinaisons sur la page produit

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal où vous contrôlez l'apparence et le comportement du tableau des déclinaisons sur vos pages produit.

#### Paramètres généraux

-   **Activer la fonction de filtres**

    -   **Ce que fait ce paramètre :** Active ou désactive un système de filtrage au-dessus du tableau des déclinaisons, permettant aux clients d'affiner rapidement les options en fonction de valeurs d'attributs spécifiques (par exemple, "Afficher uniquement les chemises rouges").
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Une barre de filtres apparaîtra au-dessus du tableau, facilitant la recherche de déclinaisons spécifiques dans de grandes listes pour les clients.
        -   *Lorsqu'désactivé :* Aucune barre de filtres ne sera affichée, et toutes les déclinaisons seront affichées sans options de filtrage.
    -   **Valeur recommandée :** OUI (si vous avez de nombreuses déclinaisons par produit, ou si les clients recherchent souvent des attributs spécifiques).
    -   **Scénario / exemple de marchand :** Un magasin de vêtements avec des dizaines de tailles et de couleurs pour un seul t-shirt. Les filtres aident les clients à trouver rapidement les t-shirts "Bleu Large".
-   **Mettre en évidence le meilleur prix**

    -   **Ce que fait ce paramètre :** Met visuellement en évidence la déclinaison avec le prix le plus bas dans le tableau, attirant l'attention du client sur l'option la plus abordable.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* La ligne correspondant à la déclinaison la moins chère sera mise en évidence (par exemple, avec une couleur de fond différente).
        -   *Lorsqu'désactivé :* Aucune mise en évidence spéciale pour le prix le plus bas.
    -   **Valeur recommandée :** OUI (peut encourager les achats en mettant en évidence la valeur).
    -   **Scénario / exemple de marchand :** Un produit avec diverses offres groupées ou configurations où une déclinaison offre une bien meilleure affaire.
-   **Afficher la colonne des économies**

    -   **Ce que fait ce paramètre :** Ajoute une colonne supplémentaire au tableau qui affiche le montant ou le pourcentage qu'un client économise lors de l'achat d'une déclinaison spécifique, particulièrement utile avec les réductions de quantité ou les prix spéciaux.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Une colonne "Économies" apparaîtra, affichant la réduction pour chaque déclinaison si applicable.
        -   *Lorsqu'désactivé :* Cette colonne ne sera pas affichée.
    -   **Valeur recommandée :** OUI (si vous offrez fréquemment des réductions ou avez une tarification basée sur la quantité).
    -   **Scénario / exemple de marchand :** Vendre un produit avec un prix de base, mais certaines déclinaisons (par exemple, une déclinaison "bundle") ont un prix réduit, et vous voulez montrer l'économie.
-   **Astuce de seuil de réduction de quantité**

    -   **Ce que fait ce paramètre :** Affiche une petite info-bulle ou un message indiquant la quantité requise pour débloquer une réduction spécifique, encourageant les clients à acheter plus.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Lorsqu'un client survole ou interagit avec une saisie de quantité, une astuce peut apparaître indiquant "Achetez 5 pour 10% de réduction !".
        -   *Lorsqu'désactivé :* Aucune astuce de ce type ne sera affichée.
    -   **Valeur recommandée :** OUI (si vous utilisez la fonction de réductions de quantité de PrestaShop).
    -   **Scénario / exemple de marchand :** Un magasin vendant des fournitures de bureau où l'achat de 10 stylos donne droit à une réduction de 5%, et cette astuce le rappelle au client.
-   **Mise en page mobile en carte**

    -   **Ce que fait ce paramètre :** Détermine la manière dont le tableau des déclinaisons est affiché sur les appareils mobiles. Au lieu d'un tableau large, il peut passer à une mise en page "carte" plus conviviale.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Sur les smartphones, chaque déclinaison sera présentée comme une carte séparée, empilée verticalement, ce qui facilite la lecture et l'interaction.
        -   *Lorsqu'désactivé :* Le module tentera d'afficher le tableau complet, ce qui pourrait nécessiter un défilement horizontal sur mobile, entravant potentiellement l'utilisabilité.
    -   **Valeur recommandée :** OUI (crucial pour la réactivité mobile et une bonne expérience utilisateur).
    -   **Scénario / exemple de marchand :** Un client naviguant sur votre boutique depuis son téléphone. La mise en page en carte garantit qu'il peut facilement voir et sélectionner les déclinaisons sans zoomer ou faire défiler excessivement.
-   **Ordre des colonnes**

    -   **Ce que fait ce paramètre :** Vous permet de personnaliser la séquence des colonnes (par exemple, Image, Référence, Prix, Quantité) dans le tableau des déclinaisons.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'modifié :* Les colonnes se réorganiseront dans le tableau du front-office selon l'ordre que vous avez spécifié.
    -   **Valeur recommandée :** Organisez les colonnes dans un ordre intuitif qui a du sens pour vos produits (par exemple, Image, Attributs, Prix, Quantité, Ajouter au panier).
    -   **Scénario / exemple de marchand :** Pour un magasin de mode, vous pourriez vouloir "Image" en premier, puis "Couleur", puis "Taille", puis "Prix". Pour l'électronique, "Référence" pourrait être plus important.
-   **Cliquer et changer de déclinaison**

    -   **Ce que fait ce paramètre :** Contrôle si le fait de cliquer sur une ligne de déclinaison dans le tableau met automatiquement à jour l'image principale du produit, le prix et d'autres détails sur la page produit pour refléter cette déclinaison spécifique.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Cliquer sur une ligne mettra à jour dynamiquement l'affichage principal du produit, donnant au client une confirmation visuelle de sa sélection.
        -   *Lorsqu'désactivé :* L'affichage principal du produit ne changera pas lorsqu'une ligne est cliquée ; seule la saisie de la quantité et le bouton "Ajouter au panier" pour cette ligne sont actifs.
    -   **Valeur recommandée :** OUI (améliore l'expérience utilisateur en fournissant un retour visuel).
    -   **Scénario / exemple de marchand :** Un client clique sur une déclinaison "Rouge, Grande", et l'image principale du produit passe immédiatement à la version rouge du produit.

#### Paramètres d'image

-   **Afficher l'image**

    -   **Ce que fait ce paramètre :** Détermine si une image miniature pour chaque déclinaison doit être affichée dans le tableau.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Une colonne d'image apparaîtra, affichant l'image spécifique associée à chaque déclinaison (si disponible).
        -   *Lorsqu'désactivé :* Aucune colonne d'image ne sera affichée.
    -   **Valeur recommandée :** OUI (les visuels sont puissants pour la sélection de produits).
    -   **Scénario / exemple de marchand :** Un magasin de vêtements où chaque variation de couleur a une image distincte.
-   **Afficher la colonne d'image s'il y a au moins une déclinaison avec image**

    -   **Ce que fait ce paramètre :** Contrôle la visibilité de la colonne d'image en fonction de la présence d'une image spécifique attribuée à une déclinaison.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Si au moins une déclinaison a une image, la colonne d'image apparaîtra pour toutes les déclinaisons (affichant l'image par défaut du produit pour celles sans images de déclinaison spécifiques).
        -   *Lorsqu'désactivé :* La colonne d'image n'apparaîtra que si *toutes* les déclinaisons ont des images spécifiques, ou elle pourrait ne pas apparaître du tout si vous utilisez également "Utiliser l'image par défaut du produit" avec prudence.
    -   **Valeur recommandée :** OUI (évite une colonne d'image vide si seules quelques déclinaisons ont des images).
    -   **Scénario / exemple de marchand :** Vous avez 20 déclinaisons, mais seulement 5 ont des images uniques. Cela garantit que la colonne d'image apparaît toujours, en utilisant l'image principale du produit pour les 15 autres.
-   **Utiliser l'image par défaut du produit**

    -   **Ce que fait ce paramètre :** Si une déclinaison spécifique n'a pas sa propre image, ce paramètre détermine si l'image principale du produit doit être utilisée comme solution de repli.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Les déclinaisons sans images spécifiques afficheront l'image principale du produit.
        -   *Lorsqu'désactivé :* Les déclinaisons sans images spécifiques afficheront un espace réservé ou aucune image.
    -   **Valeur recommandée :** OUI (garantit que toutes les déclinaisons ont une représentation visuelle).
    -   **Scénario / exemple de marchand :** Un produit avec de nombreuses variations de taille mais une seule image par couleur. Cela garantit que toutes les tailles d'une couleur spécifique affichent l'image de couleur correcte.
-   **Activer le zoom Fancybox**

    -   **Ce que fait ce paramètre :** Permet aux clients de cliquer sur les images de déclinaison dans le tableau pour afficher une version plus grande et zoomée dans une fenêtre contextuelle (Fancybox).
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Cliquer sur une image de déclinaison l'ouvrira dans une fenêtre contextuelle Fancybox.
        -   *Lorsqu'désactivé :* Les images ne seront pas cliquables pour le zoom.
    -   **Valeur recommandée :** OUI (améliore l'expérience de visualisation des images).
    -   **Scénario / exemple de marchand :** Un client souhaite voir plus en détail la texture ou le détail d'une variation de couleur spécifique.
-   **Type d'image à afficher**

    -   **Ce que fait ce paramètre :** Sélectionne la taille/le type d'image (par exemple, `small_default`, `medium_default`) à afficher en tant que miniatures dans le tableau des déclinaisons.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'modifié :* La taille des images dans le tableau sera mise à jour au type d'image sélectionné.
    -   **Valeur recommandée :** `small_default` ou `medium_default` (choisissez-en un qui s'intègre bien dans la mise en page de votre tableau sans être trop grand ou trop petit).
    -   **Scénario / exemple de marchand :** Vous voulez que les images du tableau soient légèrement plus grandes que le minuscule `small_default` mais pas aussi grandes que `large_default`.
-   **Type d'image utilisé pour agrandir la miniature**

    -   **Ce que fait ce paramètre :** Sélectionne la taille/le type d'image à utiliser lorsque la fonction de zoom Fancybox est activée.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'modifié :* L'image affichée dans la fenêtre contextuelle Fancybox sera de la taille sélectionnée.
    -   **Valeur recommandée :** `large_default` ou `thickbox_default` (choisissez le type d'image le plus grand et de la plus haute qualité pour le zoom).
    -   **Scénario / exemple de marchand :** Un client zoome sur une image et s'attend à voir une version haute résolution.

#### Paramètres d'affichage des attributs

-   **Méthode d'affichage des attributs**

    -   **Ce que fait ce paramètre :** Contrôle la manière dont les noms d'attributs (par exemple, "Taille", "Couleur") sont affichés dans l'en-tête du tableau.
    -   **Effet de la modification de ce paramètre :**
        -   *Options (par exemple, "Nom complet", "Nom court", "ID") :* Modifie l'apparence des en-têtes d'attributs.
    -   **Valeur recommandée :** "Nom complet" (le plus descriptif pour les clients).
    -   **Scénario / exemple de marchand :** Vous voulez que "Taille" apparaisse comme "Taille" et non "T" ou "ID: 1".
-   **Associations d'attributs avec la boutique (multiboutique)**

    -   **Ce que fait ce paramètre :** Dans un environnement multiboutique, cela vous permet de spécifier quels groupes d'attributs sont pertinents pour quelles boutiques, empêchant ainsi l'apparition d'attributs non pertinents.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'configuré :* Seuls les attributs associés au contexte de la boutique actuelle seront affichés dans le tableau.
    -   **Valeur recommandée :** Configurez attentivement si vous gérez une multiboutique avec différents catalogues de produits.
    -   **Scénario / exemple de marchand :** La boutique A vend des vêtements (Taille, Couleur), la boutique B vend de l'électronique (Stockage, RAM). Cela empêche "Stockage" d'apparaître dans le tableau des déclinaisons de la boutique A.
-   **Inclure l'étiquette au nom de l'attribut**

    -   **Ce que fait ce paramètre :** Ajoute le nom du groupe d'attributs comme préfixe à la valeur de l'attribut (par exemple, "Taille : S", "Couleur : Rouge").
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Les valeurs d'attributs seront plus descriptives.
        -   *Lorsqu'désactivé :* Seule la valeur de l'attribut sera affichée (par exemple, "S", "Rouge").
    -   **Valeur recommandée :** OUI (améliore la clarté, surtout si les valeurs d'attributs ne sont pas explicites).
    -   **Scénario / exemple de marchand :** Un produit a une valeur d'attribut "Standard". Est-ce une taille standard, une couleur standard ou une finition standard ? "Finition : Standard" le clarifie.
-   **Attribut de couleur**

    -   **Ce que fait ce paramètre :** Vous permet de spécifier quel groupe d'attributs représente la "couleur" dans votre boutique. Ceci est important pour que le module affiche correctement les échantillons de couleur ou la logique spécifique à la couleur.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'sélectionné :* Le module traitera les valeurs de ce groupe d'attributs comme des couleurs, les affichant potentiellement comme des échantillons de couleur au lieu de texte.
    -   **Valeur recommandée :** Sélectionnez votre groupe d'attributs "Couleur" principal.
    -   **Scénario / exemple de marchand :** Vous avez un groupe d'attributs nommé "Couleur" avec des valeurs comme "Rouge", "Bleu", "Vert". La sélection de ce groupe garantit qu'elles sont affichées comme de véritables échantillons de couleur.

#### Options d'affichage

-   **Masquer l'en-tête du tableau**

    -   **Ce que fait ce paramètre :** Supprime la ligne d'en-tête du tableau des déclinaisons (par exemple, "Image | Taille | Couleur | Prix | Quantité").
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Le tableau commencera directement par les lignes de déclinaisons, sans titres de colonnes.
        -   *Lorsqu'désactivé :* La ligne d'en-tête sera visible.
    -   **Valeur recommandée :** NON (les en-têtes sont généralement importants pour la clarté, sauf si votre tableau est très simple et explicite).
    -   **Scénario / exemple de marchand :** Pour un produit très simple avec un seul attribut (par exemple, "Taille du paquet"), vous pourriez masquer l'en-tête si le contenu de la colonne est évident.
-   **Masquer les déclinaisons en rupture de stock**

    -   **Ce que fait ce paramètre :** Empêche les déclinaisons actuellement en rupture de stock d'être affichées dans le tableau.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Seules les déclinaisons en stock seront visibles, réduisant l'encombrement et évitant la frustration des clients.
        -   *Lorsqu'désactivé :* Les déclinaisons en rupture de stock seront toujours affichées, souvent avec une étiquette "Épuisé" ou un bouton "Ajouter au panier" désactivé.
    -   **Valeur recommandée :** OUI (généralement meilleure pour l'expérience utilisateur, sauf si vous souhaitez afficher toutes les options pour les précommandes ou les notifications de retour en stock).
    -   **Scénario / exemple de marchand :** Un modèle de chaussure populaire est en rupture de stock pour la taille 10. Le masquer empêche les clients d'essayer de le sélectionner.
-   **Masquer les déclinaisons avec un prix = 0**

    -   **Ce que fait ce paramètre :** Exclut les déclinaisons dont le prix est nul d'être affichées dans le tableau.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Les déclinaisons avec un prix nul n'apparaîtront pas.
        -   *Lorsqu'désactivé :* Les déclinaisons avec un prix nul seront listées.
    -   **Valeur recommandée :** OUI (sauf si vous proposez intentionnellement des déclinaisons gratuites, ce qui est rare).
    -   **Scénario / exemple de marchand :** Parfois, en raison d'une mauvaise configuration, une déclinaison peut se retrouver avec un prix nul. Les masquer évite toute confusion.
-   **Afficher uniquement les déclinaisons avec des images**

    -   **Ce que fait ce paramètre :** Filtre le tableau pour n'afficher que les déclinaisons auxquelles une image spécifique est attribuée.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Seules les déclinaisons avec des images uniques seront listées.
        -   *Lorsqu'désactivé :* Toutes les déclinaisons seront affichées, qu'elles aient ou non une image spécifique.
    -   **Valeur recommandée :** NON (il est généralement préférable d'afficher toutes les déclinaisons, en utilisant des images par défaut si nécessaire, sauf si la différenciation visuelle est primordiale).
    -   **Scénario / exemple de marchand :** Si vous ne souhaitez présenter que les déclinaisons qui ont des différences visuelles distinctes, et que vous n'avez pas téléchargé d'images pour toutes.
-   **Afficher le prix**

    -   **Ce que fait ce paramètre :** Contrôle si le prix de chaque déclinaison est affiché dans le tableau.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Une colonne "Prix" sera visible.
        -   *Lorsqu'désactivé :* La colonne de prix sera masquée.
    -   **Valeur recommandée :** OUI (le prix est un facteur critique pour les clients).
    -   **Scénario / exemple de marchand :** Un client souhaite comparer les prix entre différentes tailles ou matériaux d'un produit.
-   **Afficher le prix unitaire**

    -   **Ce que fait ce paramètre :** Affiche le prix unitaire (par exemple, prix par kg, par litre) pour chaque déclinaison, le cas échéant.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Une colonne "Prix unitaire" supplémentaire apparaîtra.
        -   *Lorsqu'désactivé :* Cette colonne ne sera pas affichée.
    -   **Valeur recommandée :** OUI (si vos produits sont vendus au poids/volume et que le prix unitaire est pertinent).
    -   **Scénario / exemple de marchand :** Vendre des grains de café dans différentes tailles de sacs, et les clients veulent comparer le prix par 100g.
-   **Afficher le prix uniquement pour les clients connectés**

    -   **Ce que fait ce paramètre :** Masque les prix des déclinaisons aux visiteurs qui ne sont pas connectés à leur compte client.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Les invités ne verront pas les prix ; ils pourraient voir un message les invitant à se connecter.
        -   *Lorsqu'désactivé :* Les prix sont visibles pour tout le monde.
    -   **Valeur recommandée :** NON (sauf si vous gérez une boutique B2B ou avez des stratégies de tarification spécifiques nécessitant une connexion).
    -   **Scénario / exemple de marchand :** Un magasin de gros où la tarification est négociée ou spécifique aux comptes professionnels enregistrés.
-   **Afficher l'étiquette de taxe**

    -   **Ce que fait ce paramètre :** Affiche une étiquette indiquant si les prix affichés incluent ou excluent la taxe (par exemple, "TTC", "HT").
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Le statut de la taxe sera clairement indiqué à côté des prix.
        -   *Lorsqu'désactivé :* Aucune étiquette de taxe ne sera affichée.
    -   **Valeur recommandée :** OUI (améliore la transparence et est conforme aux exigences légales dans de nombreuses régions).
    -   **Scénario / exemple de marchand :** Les clients en Europe s'attendent à voir des prix "TTC", tandis que les clients B2B pourraient préférer "HT".

#### Autres clés de configuration (Avancé/Interne)

Ces paramètres sont généralement gérés en interne par le module ou sont moins fréquemment ajustés par les marchands.

-   `mypresta_updates`, `update_`, `updatev_` : Clés internes pour les mises à jour du module et le suivi des versions.
-   `ctp_position` : Contrôle la position du hook où le tableau est affiché.
-   `ctp_lasttab` : Lié à l'affichage du tableau dans un onglet produit.
-   `ctp_reference`, `ctp_ean`, `ctp_mpn` : Contrôle l'affichage des colonnes Référence, EAN13/JAN et MPN.
-   `ctp_cname` : Contrôle l'affichage du nom de la déclinaison.
-   `ctp_atc`, `ctp_atcq` : Contrôle le bouton "Ajouter au panier" et la saisie de la quantité.
-   `ctp_ajax` : Détermine si AJAX est utilisé pour l'ajout au panier.
-   `ctp_sort` : Options de tri pour les déclinaisons dans le tableau.
-   `ctp_quantity`, `ctp_quantity_sum` : Affichage de la quantité en stock et de la somme des quantités.
-   `ctp_availability`, `ctp_availability_d` : Affichage du statut et de la date de disponibilité.
-   `ctp_imagetype`, `ctp_imagetype_zoom`, `ctp_grid_imagetype`, `ctp_grid_defimg` : Paramètres de type d'image (couverts ci-dessus).
-   `ctp_attributes_method` : Méthode d'affichage des attributs (couverte ci-dessus).
-   `ctp_prices_tax` : Paramètres d'affichage des taxes (couverts ci-dessus).
-   `ctp_color_method` : Comment les attributs de couleur sont affichés (par exemple, échantillons).
-   `ctp_hide_default`, `ctp_hide_r` : Masquer la déclinaison par défaut, masquer les déclinaisons avec un prix nul (couverts ci-dessus).
-   `ctp_where`, `ctp_tabtype` : Placement du tableau (hook, type d'onglet).
-   `ctp_quantity_pm` : Boutons plus/moins pour la saisie de la quantité.
-   `ctp_view_mode` : Mode d'affichage global du tableau (tableau, grille, etc.).
-   `ctp_grid_row_attr`, `ctp_grid_col_attr` : Paramètres pour la mise en page en grille (quels attributs forment les lignes/colonnes).

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### AdminCombinationstabSearchController (Back Office > Modules > Tableau des déclinaisons sur la page produit > Recherche)

Ce contrôleur fournit une interface dédiée dans le back office de PrestaShop, probablement pour gérer ou rechercher des déclinaisons, potentiellement sur plusieurs produits, ou pour une configuration avancée liée à l'affichage des déclinaisons.

-   **Nom de l'écran et emplacement du menu :** Vous trouverez généralement un nouvel élément de menu sous **Modules > Tableau des déclinaisons sur la page produit** (ou similaire, selon la version de PrestaShop) intitulé "Recherche" ou "Recherche de déclinaisons".
-   **Actions et paramètres disponibles :** Cet écran présente probablement une grille ou une vue de gestion des déclinaisons de produits. Il pourrait vous permettre de :
    -   Rechercher des déclinaisons spécifiques par attributs, référence, EAN ou nom de produit.
    -   Afficher les détails des déclinaisons, tels que le stock, le prix et le produit associé.
    -   Potentiellement effectuer des actions en masse comme la mise à jour du stock ou du prix pour plusieurs déclinaisons (bien que cela soit souvent géré par la page produit principale de PrestaShop).
    -   Cet écran est principalement destiné à *gérer* et *visualiser* les données de déclinaisons de manière structurée, séparément de la page d'édition du produit principal.
-   **Effet des modifications :** Toute modification apportée ici (si l'édition est activée) mettrait directement à jour les données de déclinaisons dans votre base de données PrestaShop, affectant les prix, le stock et la disponibilité sur le front office.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Utilisez cet écran pour auditer rapidement les données de déclinaisons, trouver des déclinaisons spécifiques ou vérifier les niveaux de stock sans naviguer vers les pages de produits individuelles. C'est un outil puissant pour les boutiques avec un grand catalogue de produits et de déclinaisons.

#### index.php (combinationstab/controllers/admin/index.php)

Ce fichier sert généralement de marqueur de position ou de redirigeur pour le contrôleur d'administration principal du module. Il peut simplement charger le `AdminCombinationstabSearchController` ou présenter une page d'accueil de base pour la section d'administration du module. Il n'a généralement pas de paramètres configurables directs mais agit comme un point d'entrée.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activer la fonction de filtres | OUI | Active les filtres d'attributs pour le tableau des déclinaisons. |
| | Mettre en évidence le meilleur prix | OUI | Met visuellement en évidence la déclinaison la moins chère. |
| | Afficher la colonne des économies | OUI | Affiche le montant/pourcentage de réduction dans une colonne dédiée. |
| | Astuce de seuil de réduction de quantité | OUI | Affiche des astuces pour les réductions basées sur la quantité. |
| | Mise en page mobile en carte | OUI | Optimise l'affichage du tableau pour les appareils mobiles. |
| | Ordre des colonnes | Personnalisable | Définit la séquence des colonnes dans le tableau. |
| | Cliquer et changer de déclinaison | OUI | Met à jour l'image/les détails principaux du produit lors du clic sur une ligne. |
| | Afficher l'image | OUI | Affiche les images des déclinaisons dans le tableau. |
| | Afficher la colonne d'image s'il y a au moins une déclinaison avec image | OUI | Garantit que la colonne d'image apparaît si une déclinaison a une image. |
| | Utiliser l'image par défaut du produit | OUI | Retourne à l'image principale du produit si la déclinaison n'a pas d'image spécifique. |
| | Activer le zoom Fancybox | OUI | Permet le zoom des images de déclinaisons. |
| | Type d'image à afficher | `medium_default` | Définit la taille des miniatures dans le tableau. |
| | Type d'image utilisé pour agrandir la miniature | `large_default` | Définit la taille de l'image zoomée. |
| | Méthode d'affichage des attributs | Nom complet | Comment les en-têtes d'attributs sont étiquetés (par exemple, "Taille"). |
| | Associations d'attributs avec la boutique (multiboutique) | Configurer selon les besoins | Filtre les attributs par boutique en multiboutique. |
| | Inclure l'étiquette au nom de l'attribut | OUI | Ajoute le nom du groupe d'attributs à la valeur (par exemple, "Taille : S"). |
| | Attribut de couleur | Sélectionnez votre attribut de couleur | Identifie l'attribut de couleur pour un affichage spécial. |
| | Masquer l'en-tête du tableau | NON | Garde les titres de colonnes visibles pour plus de clarté. |
| | Masquer les déclinaisons en rupture de stock | OUI | Supprime les déclinaisons indisponibles du tableau. |
| | Masquer les déclinaisons avec un prix = 0 | OUI | Supprime les déclinaisons à prix nul. |
| | Afficher uniquement les déclinaisons avec des images | NON | Affiche toutes les déclinaisons, en utilisant les images par défaut si nécessaire. |
| | Afficher le prix | OUI | Affiche le prix de chaque déclinaison. |
| | Afficher le prix unitaire | OUI (si applicable) | Affiche le prix par unité (par exemple, par kg). |
| | Afficher le prix uniquement pour les clients connectés | NON | Rend les prix visibles à tous les visiteurs. |
| | Afficher l'étiquette de taxe | OUI | Indique si les prix incluent/excluent la taxe. |
| **AdminCombinationstabSearchController** | Vue grille / Gestion | N/A | Rechercher, afficher et potentiellement gérer les déclinaisons sur les produits. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Le tableau des déclinaisons n'apparaît pas sur ma page produit.**
R1 :

-   **Vérifier la position du module :** Allez dans **Design > Positions** (ou **Modules > Positions** dans les anciennes versions de PrestaShop) dans votre Back Office. Recherchez le module "Tableau des déclinaisons sur la page produit". Assurez-vous qu'il est accroché à un hook d'affichage pertinent comme `displayProductFooter`, `displayProductExtraContent` ou `displayProductTabContent`. Si ce n'est pas le cas, cliquez sur "Greffer un module" et ajoutez-le au hook souhaité.
-   **Configuration du module :** Vérifiez à nouveau la page de configuration du module pour vous assurer qu'il est activé et non masqué par d'autres paramètres (par exemple, "Masquer les déclinaisons avec un prix = 0" pourrait tout masquer si tout est à zéro).
-   **Le produit a des déclinaisons :** Assurez-vous que le produit que vous visualisez a bien des déclinaisons définies dans ses paramètres produit.
-   **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache". Parfois, un ancien contenu mis en cache empêche l'affichage de nouveaux modules.

**Q2 : Mes images de déclinaisons n'apparaissent pas ou ont la mauvaise taille.**
R2 :

-   **Paramètres d'image :** Vérifiez les paramètres "Type d'image à afficher" et "Type d'image utilisé pour agrandir la miniature" dans la configuration du module. Assurez-vous d'avoir sélectionné des types d'images appropriés qui existent dans votre thème PrestaShop.
-   **Images de déclinaisons téléchargées :** Vérifiez que vous avez bien téléchargé des images spécifiques pour vos déclinaisons de produits dans l'onglet "Déclinaisons" du produit dans le Back Office. Si ce n'est pas le cas, le module utilisera l'image principale du produit (si "Utiliser l'image par défaut du produit" est activé).
-   **Régénérer les miniatures :** Si vous avez modifié les types d'images ou téléchargé de nouvelles images, allez dans **Design > Paramètres des images** (ou **Préférences > Images**) et cliquez sur "Régénérer les miniatures" pour les types d'images pertinents (par exemple, `medium_default`, `large_default`).

**Q3 : Le tableau semble étrange ou mal aligné sur mon thème personnalisé.**
R3 :

-   **Conflits CSS :** Les thèmes personnalisés ont parfois des styles CSS conflictuels. Ce module essaie d'être compatible, mais des ajustements mineurs pourraient être nécessaires.
-   **Contacter le support :** Si vous êtes à l'aise avec le CSS, vous pouvez inspecter les éléments à l'aide des outils de développement de votre navigateur et essayer de remplacer les styles conflictuels. Sinon, contactez le support MyPresta.eu avec les détails de votre thème et une capture d'écran ; ils peuvent souvent fournir une solution rapide.
-   **Mises à jour du module :** Assurez-vous d'utiliser la dernière version du module, car les améliorations de compatibilité sont souvent incluses dans les mises à jour.

**Q4 : Les prix ne s'affichent pas correctement ou sont masqués.**
R4 :

-   **Paramètres d'affichage des prix :** Vérifiez "Afficher le prix" et "Afficher le prix uniquement pour les clients connectés" dans la configuration du module. Si ce dernier est activé, assurez-vous d'être connecté en tant que client pour voir les prix.
-   **Tarification de base de PrestaShop :** Vérifiez que les prix de vos déclinaisons sont correctement définis dans l'onglet "Déclinaisons" du produit.
-   **Paramètres de taxe :** Vérifiez "Afficher l'étiquette de taxe" et vos paramètres généraux de taxe PrestaShop (**International > Taxes**) pour vous assurer que les prix sont calculés et affichés comme prévu (TTC/HT).

**Q5 : Comment puis-je modifier l'ordre des attributs dans le tableau ?**
R5 :

-   Le paramètre "Ordre des colonnes" du module vous permet de réorganiser les colonnes. Pour l'ordre des attributs eux-mêmes (par exemple, "Taille" avant "Couleur"), cela est généralement géré dans le cœur de PrestaShop : **Catalogue > Attributs & Caractéristiques > Attributs** et **Groupes d'attributs**. L'ordre que vous définissez là-bas influence généralement leur apparition dans le tableau du module.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module "Tableau des déclinaisons sur la page produit" (`combinationstab`) suit une architecture de module PrestaShop standard, tirant fortement parti des hooks pour l'affichage front-office et des contrôleurs d'administration personnalisés pour la configuration avancée et la gestion des données. Il s'intègre profondément aux données de produit et de déclinaison de base de PrestaShop, rendant dynamiquement des tableaux ou des grilles HTML à l'aide de modèles Smarty. AJAX est utilisé pour des fonctionnalités telles que "Ajouter au panier" et le changement de déclinaison pour une expérience utilisateur fluide. Le module n'introduit pas de classes `ObjectModel` personnalisées mais fonctionne directement avec les objets `Product` et `Combination` existants.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs gèrent des requêtes AJAX spécifiques ou des fonctionnalités front-office dédiées.

-   `controllers/front/BackInStock.php`
    -   **Nom de la classe et classe parente :** `CombinationstabBackInStockModuleFrontController` étend `ModuleFrontController`.
    -   **Responsabilité :** Gère probablement les requêtes AJAX liées aux notifications de "retour en stock" pour des déclinaisons spécifiques. Cela pourrait impliquer la soumission d'un formulaire pour s'inscrire aux notifications lorsqu'une déclinaison en rupture de stock devient disponible.
-   `controllers/front/CsvImport.php`
    -   **Nom de la classe et classe parente :** `CombinationstabCsvImportModuleFrontController` étend `ModuleFrontController`.
    -   **Responsabilité :** Suggère une fonctionnalité d'importation de données de déclinaisons via CSV depuis le front-office, éventuellement pour des groupes d'utilisateurs spécifiques ou des scénarios B2B. Cela impliquerait l'analyse de fichiers CSV et la mise à jour des déclinaisons de produits.
-   `controllers/front/Export.php`
    -   **Nom de la classe et classe parente :** `CombinationstabExportModuleFrontController` étend `ModuleFrontController`.
    -   **Responsabilité :** Fournit une fonctionnalité pour exporter les données de déclinaisons, potentiellement pour des produits spécifiques ou des ensembles filtrés, probablement au format CSV ou similaire. Utile pour le B2B ou l'analyse de données.
-   `controllers/front/index.php`
    -   **Nom de la classe et classe parente :** `CombinationstabIndexModuleFrontController` étend `ModuleFrontController`.
    -   **Responsabilité :** Souvent un marqueur de position ou un répartiteur par défaut. Il pourrait gérer les requêtes AJAX générales liées au tableau des déclinaisons qui ne rentrent pas dans des contrôleurs plus spécifiques, ou simplement rediriger.
-   `controllers/front/PriceCalculator.php`
    -   **Nom de la classe et classe parente :** `CombinationstabPriceCalculatorModuleFrontController` étend `ModuleFrontController`.
    -   **Responsabilité :** Gère les requêtes AJAX pour calculer et renvoyer dynamiquement les prix des déclinaisons, particulièrement pertinent pour les réductions de quantité ou les règles de tarification complexes, garantissant des mises à jour de prix en temps réel sans rechargement de page.
-   `controllers/front/Reorder.php`
    -   **Nom de la classe et classe parente :** `CombinationstabReorderModuleFrontController` étend `ModuleFrontController`.
    -   **Responsabilité :** Facilite probablement la commande de déclinaisons précédemment achetées, potentiellement depuis la page de compte d'un client ou une liste de "recommande" dédiée.
-   `controllers/front/Wishlist.php`
    -   **Nom de la classe et classe parente :** `CombinationstabWishlistModuleFrontController` étend `ModuleFrontController`.
    -   **Responsabilité :** Gère les interactions AJAX avec une fonction de liste de souhaits intégrée au tableau des déclinaisons, permettant aux clients d'ajouter des déclinaisons spécifiques à leur liste de souhaits.

#### Contrôleurs d'administration Back-Office

Ces contrôleurs fournissent l'interface administrative du module.

-   `controllers/admin/AdminCombinationstabSearchController.php`
    -   **Nom de l'onglet et entité gérée :** "Recherche de déclinaisons" (ou similaire, accessible via le menu du module). Gère les déclinaisons de `Product`.
    -   **Responsabilité :** Implémente une interface de recherche et de gestion pour les déclinaisons de produits. Ce contrôleur utilise probablement un `HelperList` ou un `HelperForm` pour afficher une grille filtrable et triable de déclinaisons, permettant aux administrateurs de trouver et potentiellement de modifier rapidement les données de déclinaisons (par exemple, stock, prix, référence) sans naviguer vers les pages de produits individuelles. Il pourrait également gérer les actions en masse.
-   `controllers/admin/index.php`
    -   **Nom de l'onglet et entité gérée :** N/A (point d'entrée).
    -   **Responsabilité :** Un modèle courant pour les répertoires de contrôleurs d'administration. Ce fichier sert généralement de point d'entrée par défaut ou de redirigeur vers le `AdminCombinationstabSearchController` principal. Il ne contient généralement pas de logique directe mais garantit que l'élément de menu d'administration pointe vers un contrôleur valide.

### 4.3 Classes et modèles de base (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que le module étend principalement les fonctionnalités et objets de base de PrestaShop existants (`Product`, `Combination`, `Attribute`, `AttributeGroup`) plutôt que d'introduire de nouveaux modèles de données. Toute la logique métier est probablement encapsulée dans le fichier principal `combinationstab.php` et ses contrôleurs.

### 4.4 Actifs JavaScript (`views/js/`)

Le module utilise une variété de fichiers JavaScript pour fournir des fonctionnalités dynamiques front-office et back-office.

-   `combinationstab/js/admin.js`
    -   **Portée :** Back-office.
    -   **Détails :** Gère la logique JavaScript pour les pages d'administration du module, y compris les interactions de formulaire, les appels AJAX pour les mises à jour de configuration et potentiellement les éléments dynamiques au sein de l'interface `AdminCombinationstabSearchController`.
-   `combinationstab/js/atc.js`
    -   **Portée :** Front-office.
    -   **Détails :** Gère la fonctionnalité "Ajouter au panier" pour le tableau des déclinaisons. Il lie les événements de clic aux boutons "Ajouter au panier", gère les saisies de quantité et envoie des requêtes AJAX au contrôleur de panier de PrestaShop pour ajouter les déclinaisons sélectionnées (potentiellement plusieurs à la fois) sans rechargement de page.
-   `combinationstab/js/combinationstab-switch.js`
    -   **Portée :** Front-office.
    -   **Détails :** Implémente la fonction "Cliquer et changer de déclinaison". Il écoute les clics sur les lignes de déclinaisons dans le tableau et met à jour dynamiquement l'image principale du produit, le prix et d'autres détails du produit sur la page pour refléter la déclinaison sélectionnée.
-   `combinationstab/js/combinationstab.js`
    -   **Portée :** Front-office.
    -   **Détails :** Le fichier JavaScript principal du front-office pour le tableau des déclinaisons. Il initialise le tableau, gère les interactions générales, gère potentiellement l'affichage du stock, de la disponibilité et des mises à jour de prix en fonction de l'entrée ou des sélections de l'utilisateur.
-   `combinationstab/js/ctp-extras.js`
    -   **Portée :** Front-office.
    -   **Détails :** Contient des fonctionnalités JavaScript supplémentaires, non essentielles, pour le tableau des déclinaisons, telles que l'affichage d'info-bulles, des améliorations mineures de l'interface utilisateur ou des interactions spécifiques non couvertes par les scripts principaux.
-   `combinationstab/js/ctp-filters.js`
    -   **Portée :** Front-office.
    -   **Détails :** Implémente la logique de filtrage pour le tableau des déclinaisons. Il écoute les changements dans les listes déroulantes de filtres ou les champs de saisie, masque/affiche dynamiquement les lignes du tableau en fonction des valeurs d'attributs sélectionnées et met à jour les déclinaisons visibles.
-   `combinationstab/js/ctp-mobile.js`
    -   **Portée :** Front-office.
    -   **Détails :** Gère le comportement réactif du tableau des déclinaisons, en implémentant spécifiquement la fonction "Mise en page mobile en carte". Il détecte la taille de l'écran et transforme le tableau en une mise en page basée sur des cartes pour une meilleure convivialité mobile.
-   `combinationstab/js/ctp-wishlist-toast.js`
    -   **Portée :** Front-office.
    -   **Détails :** Fournit un retour visuel (par exemple, une notification toast) lorsqu'une déclinaison est ajoutée à une liste de souhaits, améliorant l'expérience utilisateur.
-   `combinationstab/lib/searchTool/views/js/autocomplete.js`
    -   **Portée :** Back-office (probablement).
    -   **Détails :** Fournit une fonctionnalité d'autocomplétion, probablement pour les champs de recherche de produits ou de déclinaisons dans les interfaces d'administration du module (par exemple, `AdminCombinationstabSearchController`).
-   `combinationstab/views/js/wishlist.js`
    -   **Portée :** Front-office.
    -   **Détails :** JavaScript dédié à l'intégration de la liste de souhaits, gérant les appels AJAX pour ajouter/supprimer des articles de la liste de souhaits directement depuis le tableau des déclinaisons.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module comprend plusieurs fichiers CSS pour le style du front-office et l'administration du back-office.

-   `combinationstab/css/admin.css`
    -   **Portée :** Style des formulaires d'administration du back-office.
    -   **Détails :** Style la page de configuration du module et toutes les interfaces d'administration personnalisées (comme `AdminCombinationstabSearchController`), garantissant une apparence cohérente dans le back office de PrestaShop.
-   `combinationstab/css/combinationstab.css`
    -   **Portée :** Style client du front-office.
    -   **Détails :** Contient le style de base pour le tableau des déclinaisons, y compris la mise en page du tableau, le rembourrage des cellules, l'alignement du texte et la réactivité de base.
-   `combinationstab/css.css`
    -   **Portée :** Style client du front-office.
    -   **Détails :** Potentiellement une feuille de style plus ancienne ou supplémentaire pour le front-office, ou des remplacements spécifiques.
-   `combinationstab/lib/searchTool/views/css/autocomplete.css`
    -   **Portée :** Back-office (probablement).
    -   **Détails :** Styles pour les champs de recherche d'autocomplétion utilisés dans le panneau d'administration.
-   `combinationstab/views/css/ctp-admin.css`
    -   **Portée :** Style des formulaires d'administration du back-office.
    -   **Détails :** Style d'administration supplémentaire ou spécifique, potentiellement pour de nouvelles fonctionnalités ou des remplacements de `admin.css`.
-   `combinationstab/views/css/wishlist.css`
    -   **Portée :** Style client du front-office.
    -   **Détails :** Styles pour le bouton de liste de souhaits et tous les éléments associés dans le tableau des déclinaisons.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module utilise des modèles Smarty pour le rendu de toutes ses vues front-office et back-office.

#### Modèles de hook (`views/templates/hook/`)

Ces modèles sont conçus pour être rendus lorsque des hooks PrestaShop spécifiques sont exécutés.

-   `views/templates/hook/columns/cells.tpl`
    -   **Hook :** Probablement rendu dans le modèle principal du tableau des déclinaisons.
    -   **Sortie :** Définit la structure et le contenu des cellules de données individuelles dans les lignes du tableau (par exemple, affichage des valeurs d'attributs, du prix, de la saisie de la quantité).
-   `views/templates/hook/columns/headers.tpl`
    -   **Hook :** Probablement rendu dans le modèle principal du tableau des déclinaisons.
    -   **Sortie :** Définit les cellules d'en-tête pour le tableau des déclinaisons, affichant les titres de colonnes comme "Image", "Taille", "Prix".
-   `views/templates/hook/columns/_wishlist_btn.tpl`
    -   **Hook :** Intégré aux lignes de déclinaisons.
    -   **Sortie :** Rend le bouton ou l'icône "Ajouter à la liste de souhaits" pour chaque déclinaison dans le tableau.
-   `views/templates/hook/customer_account.tpl`
    -   **Hook :** `displayCustomerAccount`
    -   **Sortie :** Ajoute un lien ou un bloc à la page de compte du client, potentiellement pour accéder aux listes de commande, aux données exportées ou à la gestion de la liste de souhaits.
-   `views/templates/hook/grid/_axis_label.tpl`
    -   **Hook :** Utilisé en interne lorsque `ctp_view_mode` est défini sur une mise en page en grille.
    -   **Sortie :** Rend les étiquettes pour les axes (lignes/colonnes) d'un affichage de déclinaisons de style grille.
-   `views/templates/hook/grid/_cell.tpl`
    -   **Hook :** Utilisé en interne lorsque `ctp_view_mode` est défini sur une mise en page en grille.
    -   **Sortie :** Rend les cellules individuelles dans un affichage de déclinaisons de style grille, contenant les détails de la déclinaison.
-   `views/templates/hook/productfooter.tpl`
    -   **Hook :** `displayProductFooter`
    -   **Sortie :** Le modèle principal pour le rendu du tableau des déclinaisons lorsqu'il est placé sous le contenu principal du produit. C'est souvent le placement par défaut ou le plus courant.
-   `views/templates/hook/productfooter_grid.tpl`
    -   **Hook :** `displayProductFooter` (conditionnel au mode d'affichage).
    -   **Sortie :** Un modèle alternatif pour `displayProductFooter` spécifiquement pour le rendu des déclinaisons dans une mise en page en grille au lieu d'un tableau traditionnel.
-   `views/templates/hook/quickViewScripts.tpl`
    -   **Hook :** Potentiellement `displayHeader` ou `actionFrontControllerSetMedia` (pour les modales de vue rapide).
    -   **Sortie :** Inclut le JavaScript nécessaire ou initialise la fonctionnalité du module spécifiquement pour les modales de vue rapide de produit, garantissant que le tableau des déclinaisons fonctionne dans ces fenêtres contextuelles.
-   `views/templates/hook/tab.tpl`
    -   **Hook :** `displayProductTabContent` (ou similaire pour les onglets de produit).
    -   **Sortie :** Rend le tableau des déclinaisons dans un onglet produit dédié sur la page produit.
-   `views/templates/hook/volume_discounts.tpl`
    -   **Hook :** Intégré aux lignes de déclinaisons ou en tant qu'info-bulle.
    -   **Sortie :** Affiche des informations sur les réductions de quantité pour des déclinaisons spécifiques.
-   `views/templates/hook/_filters.tpl`
    -   **Hook :** Rendu au-dessus du tableau des déclinaisons.
    -   **Sortie :** Rend l'interface de filtrage des attributs pour le tableau des déclinaisons.
-   `views/templates/hook/_toolbar.tpl`
    -   **Hook :** Rendu au-dessus du tableau des déclinaisons.
    -   **Sortie :** Rend une barre d'outils, contenant potentiellement des filtres, une recherche ou d'autres éléments interactifs pour le tableau des déclinaisons.

#### Modèles d'administration (`views/templates/admin/`)

Ces modèles sont utilisés pour la configuration du back-office du module et les écrans de gestion.

-   `views/templates/admin/b2b.tpl`
    -   **Sortie :** Modèle pour les paramètres ou fonctionnalités spécifiques au B2B dans le panneau d'administration.
-   `views/templates/admin/b2b_groups.tpl`
    -   **Sortie :** Modèle pour la gestion des groupes de clients B2B ou de leurs paramètres de prix/visibilité spécifiques.
-   `views/templates/admin/column_editor.tpl`
    -   **Sortie :** Fournit une interface permettant aux administrateurs de personnaliser l'ordre et la visibilité des colonnes dans le tableau des déclinaisons du front-office.
-   `views/templates/admin/getCombinations.tpl`
    -   **Sortie :** Utilisé par `AdminCombinationstabSearchController` pour afficher une liste ou une grille de déclinaisons.
-   `views/templates/admin/getProducts.tpl`
    -   **Sortie :** Utilisé par `AdminCombinationstabSearchController` ou d'autres outils d'administration pour afficher une liste de produits.
-   `views/templates/admin/grid_block_editor.tpl`
    -   **Sortie :** Interface pour configurer l'affichage des déclinaisons de style grille, définissant potentiellement quels attributs forment les lignes et les colonnes.
-   `views/templates/admin/menu.tpl`
    -   **Sortie :** Rend les éléments de sous-menu du module dans le back office de PrestaShop.
-   `views/templates/admin/overrides_entity.tpl`
    -   **Sortie :** Modèle pour la gestion des remplacements spécifiques à l'entité (par exemple, paramètres spécifiques au produit pour le tableau).
-   `views/templates/admin/overrides_fields.tpl`
    -   **Sortie :** Modèle pour la gestion des remplacements spécifiques aux champs.
-   `views/templates/admin/overrides_list.tpl`
    -   **Sortie :** Modèle pour lister et gérer les différents remplacements configurés pour le module.
-   `views/templates/admin/presets.tpl`
    -   **Sortie :** Interface pour enregistrer et charger des préréglages de configuration pour le tableau des déclinaisons.
-   `views/templates/admin/selectedProducts.tpl`
    -   **Sortie :** Affiche une liste de produits qui ont été sélectionnés pour des configurations ou des remplacements de module spécifiques.
-   `views/templates/admin/subtabs.tpl`
    -   **Sortie :** Rend les onglets de sous-navigation dans l'interface de configuration du module.
-   `views/templates/admin/tabs.tpl`
    -   **Sortie :** Rend les onglets de navigation principaux pour la configuration du module.
-   `views/templates/admin/tabstype.tpl`
    -   **Sortie :** Options de configuration liées à la manière dont le tableau des déclinaisons est affiché dans les onglets de produit.

#### Modèles Front-office (`views/templates/front/`)

-   `views/templates/front/wishlist.tpl`
    -   **Sortie :** Rend l'interface de liste de souhaits du front-office, potentiellement une page dédiée ou une modale, affichant les articles ajoutés à la liste de souhaits via le tableau des déclinaisons.

#### Autres modèles

-   `combinationstab/lib/searchTool/views/scripts.tpl`
    -   **Sortie :** Inclut des extraits JavaScript ou initialise des scripts pour la fonctionnalité de l'outil de recherche.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données

Le dossier du module n'indique aucun fichier SQL personnalisé. Cela implique que le module utilise principalement la table `ps_configuration` de PrestaShop pour stocker ses paramètres et s'appuie sur les tables de base existantes comme `ps_product_attribute`, `ps_product_attribute_combination`, `ps_product_attribute_shop`, `ps_stock_available`, etc., pour les données de déclinaisons.

-   **`ps_configuration`** : Stocke tous les paramètres du module (par exemple, `CTP_POSITION`, `CTP_IMAGE`, `CTP_PRICE_LOGGED`, `CTP_MOBILE_CARD_LAYOUT`).

#### Tableau des hooks enregistrés

Le module s'enregistre à divers hooks PrestaShop pour injecter son contenu et ses fonctionnalités.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `ActionAdminControllerSetMedia` | Lors de l'initialisation d'un contrôleur d'administration et de la définition des médias (JS/CSS). | Injecte les JS/CSS spécifiques au module dans le Back Office. |
| `displayRightColumn` | Rend le contenu dans la colonne de droite du front office. | Affiche le tableau des déclinaisons dans la colonne de droite (moins courant pour les tableaux). |
| `displayProductFooter` | Rend le contenu sous les informations principales du produit sur la page produit. | Hook principal pour afficher le tableau des déclinaisons sous le produit. |
| `displayHeader` | Rend le contenu dans la section `<head>` du front office. | Injecte les JS/CSS spécifiques au module, les balises meta ou d'autres éléments d'en-tête pour la fonctionnalité front-office. |
| `displayProductExtraContent` | Rend des blocs de contenu supplémentaires sur la page produit. | Offre la flexibilité de placer le tableau des déclinaisons dans un bloc de contenu personnalisé. |
| `displayRightColumnProduct` | Rend le contenu dans la colonne de droite spécifiquement sur la page produit. | Similaire à `displayRightColumn` mais ciblé sur les pages produit. |
| `displayCustomerAccount` | Rend le contenu sur la page de compte du client. | Ajoute des liens ou des informations liés aux commandes, aux listes de souhaits ou aux exportations. |
| `actionUpdateQuantity` | Après la mise à jour de la quantité (stock) d'un produit. | Déclenche potentiellement des mises à jour de l'affichage du tableau des déclinaisons (par exemple, le statut "en rupture de stock"). |
| `displayProductListFunctionalButtons` | Rend les boutons dans les listes de produits (par exemple, pages de catégorie). | Pourrait ajouter des boutons de vue rapide ou de comparaison liés aux déclinaisons. |
| `displayExtraLeft` | Rend le contenu dans une colonne gauche supplémentaire (si le thème le prend en charge). | Une autre option de placement pour le tableau des déclinaisons. |
| `CombinationsTable` | **Hook personnalisé** | Un hook personnalisé défini par le module lui-même, permettant à d'autres modules ou thèmes de s'intégrer ou de remplacer sa sortie de tableau. |
| `displayLeftColumnProduct` | Rend le contenu dans la colonne de gauche spécifiquement sur la page produit. | Similaire à `displayRightColumnProduct` mais pour la colonne de gauche. |
| `displayProductTabContent` | Rend le contenu dans un onglet produit. | Affiche le tableau des déclinaisons dans un onglet produit dédié. |
| `displayCombinationsTable` | **Hook personnalisé** | Un autre hook personnalisé, probablement pour le rendu principal du tableau des déclinaisons, offrant une alternative à `displayProductFooter`. |
| `displayProductActions` | Rend le contenu près du bouton "Ajouter au panier" sur la page produit. | Pourrait être utilisé pour un sélecteur de déclinaisons compact ou des boutons d'ajout rapide. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, le support technique et toute question concernant le module "Tableau des déclinaisons sur la page produit", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est prête à vous aider.
