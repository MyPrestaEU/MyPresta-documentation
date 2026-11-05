---
title: "Combinations Tab Pro - documentation et manuel utilisateur"
description: "Configurez la matrice de déclinaisons, les réglages quotidiens de la fiche produit et résolvez les problèmes courants de vitrine si vous possédez déjà Combinations Tab Pro."
sidebar:
  label: "Combinations Tab Pro - documentation et manuel utilisateur"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Product page combinations table sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-combinations-table.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/product-page-combinations-table/)
>
> ---


Les captures d’écran de ce manuel proviennent d’un back-office en anglais. Utilisez les mêmes noms d’onglets et de champs ci-dessous même si la langue de votre employé diffère.

## 1. Prérequis

Combinations Tab Pro affiche une liste de déclinaisons ou une matrice 2D sur la fiche produit afin que les clients puissent filtrer, trier, saisir des quantités et ajouter des variantes au panier.

- PrestaShop : 1.7, 8 et 9
- PHP : une version prise en charge par votre boutique PrestaShop
- Extensions PHP utilisées par le module : JSON
- Autres modules : aucun requis. En option, **Product combination features** débloque les colonnes description de déclinaison et caractéristiques de déclinaison lorsque ce module est installé dans la boutique
- Hors boutique : rien. Les vérifications de mise à jour contactent MyPresta lorsque les notifications sont activées
- Gros catalogues : de nombreuses déclinaisons par produit ralentissent la page si vous laissez toutes les colonnes et les extras liste et grille actifs ; utilisez des filtres, la pagination ou un preset adapté à votre catalogue

## 2. Installation

1. Téléversez le ZIP du module dans **Modules** → **Module Manager**, puis installez et activez **Combinations Tab Pro**.
2. Ouvrez la configuration depuis la liste des modules avec **Configure**. Il n’y a pas d’entrée de menu back-office séparée pour l’usage quotidien ; tous les réglages se trouvent sur cette page de configuration.
3. L’installation ne vide pas elle-même le cache PrestaShop. Videz le cache Smarty / du thème dans **Advanced Parameters** → **Performance** si le tableau n’apparaît pas après l’installation.

**Après désinstallation :** le module est retiré du Module Manager. Les tables de base de données pour la wishlist, les alertes de réapprovisionnement et les profils d’override par entité sont supprimées. Les valeurs de configuration restent dans la base de la boutique, de sorte qu’une réinstallation ultérieure peut reprendre les interrupteurs précédents jusqu’à ce que vous les modifiiez à nouveau. Les overrides de templates du module dans le thème (si vous en avez ajouté) ne sont pas supprimés par la désinstallation.

## 3. Configuration et travail en back-office

Ouvrez **Modules** → **Module Manager** → **Combinations Tab Pro** → **Configure**. La page utilise des onglets en haut : **Overview**, **Display**, **Cart**, **B2B**, **Visibility**, **Exclusions**, **Integrations**, **Overrides**, **Updates**. La recherche de produits sur **Visibility**, **Exclusions** et **Overrides** s’exécute en arrière-plan (AJAX) ; il n’y a pas de menu Orders séparé pour ce module.

### 3.1 Processus complet

1. Le marchand configure le placement, le mode d’affichage, les colonnes ou les cellules de grille, les règles panier, les outils B2B optionnels, la visibilité, les exclusions, les intégrations et les overrides.
2. Le client ouvre un produit qui a des déclinaisons et qui passe les règles de visibilité.
3. La vitrine affiche une liste (une ligne par déclinaison) ou une grille 2D (matrice lorsque le produit a deux groupes d’attributs et que le mode d’affichage le permet), dans le pied de produit ou sous un onglet **Product variants**.
4. Le client peut utiliser les filtres d’attributs, trier les en-têtes de liste, saisir des quantités et ajouter une ou plusieurs lignes au panier (y compris l’ajout en masse).
5. Outils optionnels : cœur wishlist, notification de réapprovisionnement, collage de quantités CSV, feuille d’export, remplir la dernière commande.
6. Le checkout se poursuit comme une commande PrestaShop normale. Le module n’utilise pas de statuts de type devis ; le succès est un tableau visible, des quantités remplies et un panier contenant les déclinaisons sélectionnées.

### 3.2 Overview & presets

![Overview and presets — English back office](https://mypresta.eu/docs/images/docs/combinationstab-overview.webp)

**Overview & presets** est l’onglet de départ. Les configurations prêtes activent ou désactivent de nombreux interrupteurs d’un coup. Utilisez **Preview** pour voir les valeurs prévues, puis **Apply**. Confirmation : *Preset applied. Review Display & Columns and Cart & prices if you want to fine-tune.* Ouvrez ensuite **Display** et **Cart** pour affiner les détails.

Principaux presets par nom :

| Preset | Tag | What it prepares |
|---|---|---|
| **Fashion** | B2C | Photos, filtres, pastilles de couleur, wishlist, cartes mobiles pour les vêtements avec de nombreuses tailles et couleurs |
| **B2B Wholesale** | B2B | Matrice orientée SKU, ajout en masse au panier, import CSV, export, remises de volume |
| **Minimal** | Simple | Nom de déclinaison, prix et ajout au panier uniquement |
| **Replace buy block** | UX | Masque le bloc d’achat PrestaShop par défaut pour que les clients commandent depuis le tableau |
| **2D size × color** | Grid | Force la grille 2D avec un contenu de cellule riche lorsque les produits ont Color + Size |
| **Detailed list** | List | Liste complète avec images, SKU, EAN, stock, tri, pagination |
| **Electronics** | B2C | Référence, EAN, prix unitaire, dates de disponibilité pour appareils et gadgets |
| **Beauty & cosmetics** | B2C | Case couleur + texte, photos, wishlist et réapprovisionnement pour teintes et kits |
| **Catalog only** | Display | Déclinaisons sans commande ; les prix peuvent rester pour les clients connectés |
| **Logged-in pricing** | B2B | Prix et ajout au panier uniquement pour les clients connectés |
| **Mobile first** | UX | Liste avec cartes mobiles, quantité +/- , ajout en masse sticky |
| **Restock & alerts** | Conversion | Lignes en rupture avec dates et alertes de réapprovisionnement |
| **Luxury / lookbook** | B2C | Grandes photos, zoom, stock exact masqué, mises en avant d’économies |
| **Food & packaging** | Retail | Prix unitaire, poids, qté min, remises de volume |
| **Quick order sheet** | B2B | Grille + ajout en masse + CSV/export/réassort sans images |

### 3.3 Display — Placement

![Display settings — English back office](https://mypresta.eu/docs/images/docs/combinationstab-display.webp)

Sous-onglet **Placement**. Placement au niveau de la page et habillage autour du tableau (liste et grille 2D). L’enregistrement affiche *Display settings saved.*

| Field | At the start | What it does |
|---|---|---|
| **Position on the product page** | Product footer (below product content) | Choisit où les clients voient le tableau de déclinaisons. Utilisez **Product footer** sous le produit, ou **Product tabs section** pour un onglet nommé comme **Product variants**. Choisissez l’emplacement adapté à votre thème — un mauvais choix peut masquer le tableau ou le placer trop bas. |
| **Tab style (legacy themes)** | Classic tabs (PS 1.5 style) | Ne compte que si vous utilisez la position Product tabs sur d’anciens thèmes. Laissez la valeur par défaut sauf si votre thème utilise encore des onglets style PrestaShop 1.5. Modifie la façon dont le titre d’onglet est injecté ; les thèmes modernes 1.7/8/9 l’ignorent généralement. Options : Classic tabs (PS 1.5 style) ou Accordion bars (PS 1.6 style). |
| **Custom HTML above the table** | Empty | Contenu libre (note de livraison, lien guide des tailles, etc.) au-dessus de la matrice. Optionnel par langue. Visible au-dessus de la liste et de la grille 2D. |
| **Hide default PrestaShop buy block** | No | Masque les listes déroulantes d’attributs classiques et l’ajout au panier sur la fiche produit. Mettez **Yes** lorsque le tableau doit être le seul moyen d’acheter. Page plus claire ; assurez-vous que le tableau lui-même autorise l’ajout au panier. |
| **Hide default buy block only when table has combinations** | No | Conserve le bloc d’achat normal sur les produits simples ; le masque lorsque la matrice est affichée. **Yes** est en général le plus sûr pour que les produits simples fonctionnent encore normalement. |
| **Also hide default buy block based on product restrictions** | No | Appariement avancé avec les règles Visibility. Laissez **No** sauf si vous utilisez des listes complexes d’affichage/masquage. Peut masquer le bloc d’achat natif sur des produits sélectionnés même sans le tableau. |

### 3.4 Display — View mode

| Field | At the start | What it does |
|---|---|---|
| **View mode** | List (classic table — one row per combination) | Choisit tableau liste ou matrice 2D. **List** = toujours des lignes ; **2D grid** = forcer la matrice si possible ; **Auto** = matrice pour 2 groupes d’attributs, liste sinon. Les boutiques fashion/B2B avec Color+Size conviennent à Grid/Auto ; les produits à un attribut restent en liste. |
| **Click combination to open that variant** | Off | Un clic sur une ligne/cellule ouvre l’URL produit de cette déclinaison. Mettez **Yes** si vous voulez parcourir les variantes depuis le tableau. Utile avec des photos ; désactivez si les clics ne doivent que changer la quantité. |

### 3.5 Display — Filters

Ces règles s’appliquent à la fois au tableau liste et à la grille 2D.

| Field | At the start | What it does |
|---|---|---|
| **Attribute filters above the table / grid** | Off | Affiche des pastilles cliquables (par ex. Red, XL) pour filtrer lignes/colonnes. Mettez **Yes** pour les produits à nombreuses déclinaisons. Les clients réduisent la liste et la matrice sans défiler indéfiniment. |
| **Hide out-of-stock combinations** | Off | Retire les déclinaisons en rupture de la liste et de la grille 2D. Mettez **Yes** pour ne vendre que les variantes disponibles. Tableau/matrice plus courts ; les clients ne voient pas les tailles manquantes. |
| **Hide combinations with price = 0** | Off | Masque les variantes gratuites/à prix zéro de la liste et de la grille. Mettez **Yes** si zéro signifie « non vendu ». Les matrices peuvent paraître incomplètes si certaines cellules sont volontairement à 0. |
| **Show only combinations that have a picture** | Off | Masque les déclinaisons sans image dans la liste et la grille. Mettez **Yes** pour les lookbooks ; **No** si chaque SKU doit être commandable. Les catalogues incomplets sont plus jolis mais certaines variantes disparaissent. |
| **Multistore: disabled attribute values** | Hide the whole combination | Lorsqu’une valeur d’attribut est désactivée pour la boutique courante. Multiboutique uniquement — choisir masquer la déclinaison, afficher « - », ou ignorer. S’applique avant la construction de la liste et de la grille ; les boutiques mono-magasin peuvent laisser la valeur par défaut. |

### 3.6 Display — Stock format

Comment les quantités de stock sont affichées dans la liste et la grille lorsque le stock est montré. La visibilité colonne/cellule est sous List columns ou Grid cells.

| Field | At the start | What it does |
|---|---|---|
| **Show negative stock as zero** | Off | Affiche 0 au lieu de nombres négatifs. Mettez **Yes** si votre stock peut passer sous zéro. Chiffres de stock plus clairs dans la liste et la grille. |
| **Hide exact stock above a threshold** | Off | Affiche par exemple « 20+ » au lieu du nombre réel. Mettez **Yes** et le seuil. Masque les grands stocks d’entrepôt aux concurrents dans la liste et la grille. |
| **Stock threshold (show as X+)** | Empty | Lorsque masquer le stock exact est **Yes**, les quantités au-dessus s’affichent comme « N+ ». Exemple : 20 fait apparaître le stock 45 comme « 20+ ». |

### 3.7 Display — Grid axes, images, cells

Une grille 2D est une matrice style taille×couleur. Elle fonctionne lorsque le produit a exactement deux groupes d’attributs et que View mode est **Grid** ou **Auto**. Un mauvais appariement d’axes (même groupe deux fois) casse la grille et bascule vers la liste.

**Grid axes**

| Field | At the start | What it does |
|---|---|---|
| **Grid rows = attribute group** | -- automatic -- | Quel attribut devient le côté gauche de la matrice (par ex. Color). Choisissez un groupe ou laissez Automatic (premier groupe d’attributs par position). Un mauvais couple casse la grille et bascule vers la liste. |
| **Grid columns = attribute group** | -- automatic -- | Quel attribut devient le haut de la matrice (par ex. Size). Choisissez un groupe différent des lignes, ou Automatic. Chaque cellule est une déclinaison où les clients saisissent la quantité. |

**Grid images** (grille 2D uniquement)

| Field | At the start | What it does |
|---|---|---|
| **Show image in cells** | Off | Miniature dans chaque cellule de la matrice. Mettez **Yes** pour les matrices fashion couleur×taille. Cellules plus denses ; utilise l’image de déclinaison ou le fallback couverture ci-dessous. |
| **Use product cover when combination has no image** | Yes | Affiche la photo principale du produit en secours dans les cellules. Mettez **Yes** pour ne jamais montrer une image vide dans la matrice. N’affecte que la grille 2D, pas la liste. |
| **Grid thumbnail image type** | Empty (shop image types) | Taille d’image PrestaShop utilisée dans les cellules. Choisissez un type petit (par ex. cart / small_default). Grille 2D uniquement ; la liste utilise List images → Thumbnail type. |

**Grid cells** — glissez **Cell block order** (haut→bas), puis Save. Seuls les blocs activés apparaissent. Wishlist/BIS nécessitent encore **Integrations** ; l’ajout au panier nécessite l’interrupteur maître sous **Cart**.

| Field | At the start | What it does |
|---|---|---|
| **Cell block order** | Default block order | Ordre des blocs dans chaque cellule de la matrice. Glissez, puis Save. Seuls les blocs activés ci-dessous apparaissent. Image on/off et taille sous Grid images. |
| **Grid: show reference (SKU)** | Off | SKU sous le contenu de la cellule. Mettez **Yes** en B2B pour que les acheteurs identifient les SKU sans ouvrir le produit. |
| **Grid: show price** | Off | Prix dans la cellule (règles taxe/remise suivent Cart). Mettez **Yes** pour presque toutes les boutiques afin de comparer les variantes par prix dans la matrice. |
| **Grid: show unit price** | Off | Prix unitaire dans la cellule. Mettez **Yes** si vous utilisez le prix unitaire. Ligne compacte sous le prix principal. |
| **Grid: show stock quantity** | Off | Nombre de stock disponible dans la cellule. Mettez **Yes** pour la transparence ; révèle l’inventaire par taille/couleur. |
| **Grid: show availability** | Off | Libellé In stock / Out of stock dans la cellule. Mettez **Yes** lorsque les chiffres de stock sont masqués. Statut clair sans la qté exacte. |
| **Grid: show minimal quantity** | Off | Qté min de commande dans la cellule. Mettez **Yes** pour les packs B2B ; réduit les mauvaises quantités panier. |
| **Grid: show savings badge** | Off | % économisé vs la déclinaison la plus chère. Mettez **Yes** pour la conversion ; met en avant les tailles/couleurs moins chères. |
| **Grid: quantity input** | Off | Champ qté dans chaque cellule (fonctionne avec Bulk Add to cart). Mettez **Yes** pour la commande en matrice afin que les clients remplissent les quantités par taille. |
| **Grid: Add to cart button (when bulk ATC is off)** | Off | Bouton d’ajout par cellule lorsque Bulk add to cart est désactivé. Mettez **Yes** pour des ajouts en un clic sans bulk. Ignoré tant que le bulk ATC est actif. |
| **Grid: wishlist heart** | Off | Bouton cœur dans la cellule. Activez d’abord Wishlist sous Integrations. Les clients enregistrent une taille/couleur depuis la matrice. |
| **Grid: back-in-stock alert** | Off | Bouton de notification sur les cellules en rupture. Activez d’abord Back in stock sous Integrations. Capture la demande pour les tailles manquantes. |

### 3.8 Display — List layout, images, columns

Ces réglages n’affectent que la liste classique (une ligne par déclinaison), pas les cellules de grille 2D.

**List layout & sorting**

| Field | At the start | What it does |
|---|---|---|
| **Column order (list only)** | Default column order | Définit l’ordre gauche-droite des colonnes en vue liste. Glissez les éléments, puis Save. Les clients voient les colonnes dans cet ordre (seules les colonnes activées apparaissent). |
| **Mobile card layout (list)** | Yes | Sur téléphone, transforme les larges lignes de tableau en cartes empilées. Mettez **Yes** pour une meilleure UX mobile. Chaque déclinaison ressemble à une petite carte ; le bureau reste un tableau normal. |
| **Hide table header (list)** | Off | Retire la ligne du haut avec les noms de colonnes. Laissez en général **No**. Aspect plus épuré mais colonnes plus difficiles à comprendre. |
| **Paginate long tables (list)** | Off | Découpe de nombreuses déclinaisons en pages. Mettez **Yes** si un produit a des dizaines de variantes. Sensation de page plus rapide ; réglez Rows per page ci-dessous. |
| **Rows per page** | 10 when pagination is used without a custom value | Combien de déclinaisons par page lorsque la pagination est active. Exemple : 10 ou 20. Nombre plus petit = pages plus courtes, plus de clics. |
| **Allow sorting by column headers** | Yes | En-têtes cliquables pour trier la liste. Mettez **Yes** pour les longues listes. Les clients trient par prix, référence, etc. (vue liste uniquement). |
| **Default sort by price** | Off | Le tri initial utilise le prix. Optionnel. Moins cher/plus cher en premier selon la direction. |
| **Default sort by attribute** | Off | Tri initial par un groupe d’attributs choisi. Réglez l’ID d’attribut et la direction ci-dessous. Exemple : tailles S→XL. |
| **Attribute sort uses** | Attribute value position | Trier par position d’attribut (ordre catalogue) ou par nom A→Z. La position convient généralement mieux aux tailles. Change l’ordre des lignes par défaut lorsque le tri par attribut est activé. |
| **Attribute group ID to sort by** | Empty | ID numérique du groupe d’attributs utilisé pour le tri par défaut. Dans Catalog → Attributes, ouvrez le groupe et lisez l’ID dans l’URL. Mauvais ID = ordre inattendu. |
| **Sort direction** | Ascending | Ordre par défaut ascendant ou descendant. Ascending pour S→XL ; Descending pour prix haut→bas lors du tri par prix. Contrôle les premières lignes que voient les clients. |

**List images**

| Field | At the start | What it does |
|---|---|---|
| **Show image column** | Yes | Ajoute une miniature pour chaque déclinaison. Mettez **Yes** lorsque les variantes ont des photos différentes pour les reconnaître plus vite. |
| **Show image column only if at least one combination has a photo** | Off | Masque la colonne image vide lorsqu’aucune déclinaison n’a de photo. Mettez **Yes** pour éviter une colonne vide inutile. Le tableau reste propre sur les produits sans images de déclinaison. |
| **Use product cover when combination has no image** | Off | Affiche la photo principale du produit en secours dans la liste. Mettez **Yes** pour ne jamais montrer une cellule image vide. N’affecte que la vue liste, pas la grille 2D. |
| **Click image to zoom** | Off | Ouvre une image plus grande en lightbox. Mettez **Yes** pour les produits visuels ; réglez la taille de zoom ci-dessous. Les clients inspectent les détails sans quitter la page. |
| **Thumbnail image type** | Empty (shop image types) | Taille d’image PrestaShop utilisée dans la colonne liste. Choisissez un type petit (par ex. cart / small_default). Liste uniquement ; la grille utilise Grid images → Thumbnail type. |
| **Zoom image type** | Empty (shop image types) | Taille d’image ouverte dans la lightbox lorsque le zoom est activé. Choisissez un type grand (par ex. large_default). Aperçu zoom plus net en vue liste. |

**List columns** — visibilité pour la liste classique. Description / caractéristiques de déclinaison nécessitent le module optionnel Combination features ; sinon ces contrôles restent verrouillés avec un lien boutique.

| Field | At the start | What it does |
|---|---|---|
| **How attributes are shown** | All attributes in one column | Une colonne combinée « Combination name » vs colonnes séparées par attribut (Color, Size…). Les colonnes séparées sont plus faciles à parcourir et à trier. La mise en page de la vue liste change immédiatement. |
| **Include attribute label in the name** | Off | Affiche « Color: Red, Size: L » au lieu de « Red, L ». Mettez **Yes** pour plus de clarté ; s’applique uniquement à la méthode une colonne. Noms plus longs mais plus clairs. |
| **Color attribute display** | Text only | Aspect des valeurs de couleur (pastille, texte, ou les deux). Case couleur pour la mode ; Texte si les couleurs sont nommées spécialement. N’affecte que les attributs de type « color ». |
| **Show combination / attribute columns** | Yes | Interrupteur maître des colonnes de nom d’attribut. Presque toujours **Yes**. **No** masque comment les variantes diffèrent — uniquement pour des mises en page très particulières. |
| **Show combination description** | Off (locked without Combination features) | Affiche la description personnalisée assignée à la déclinaison par Combination features. Mettez **Yes** lorsque les variantes ont un texte unique. Colonne liste supplémentaire ; les cellules vides affichent « - ». |
| **Show combination features** | Off (locked without Combination features) | Affiche les valeurs de caractéristiques assignées à la déclinaison par Combination features. Mettez **Yes** lorsque les variantes ont leur propre fiche. Colonne liste supplémentaire avec nom de caractéristique + valeurs. |
| **Show reference (SKU)** | Yes | Affiche la référence de déclinaison. Mettez **Yes** pour B2B / gros afin que les acheteurs commandent plus vite par SKU. |
| **Show EAN** | No | Affiche le code-barres EAN-13. Mettez **Yes** si le personnel/les clients scannent des codes. Colonne supplémentaire ; désactivez pour la mode B2C si inutilisé. |
| **Show MPN** | No | Colonne numéro de pièce fabricant. Mettez **Yes** lorsque vous renseignez le MPN dans le catalogue. Les cellules vides affichent « - » si le MPN est vide. |
| **Show weight** | Off | Poids produit + impact de déclinaison. Mettez **Yes** pour les biens sensibles à la livraison afin d’estimer les frais. |
| **Show stock quantity** | Yes | Stock disponible par déclinaison. Mettez **Yes** pour la transparence ; couplez avec Stock format pour « 10+ ». Renforce la confiance ; révèle l’inventaire. |
| **Show total product stock in header** | No | Ajoute la somme du stock à côté de l’en-tête Quantity. Aperçu optionnel rapide de la disponibilité totale. |
| **Show availability text** | Yes | « In stock » / « Out of stock » (ou vos libellés boutique). Mettez **Yes** pour la clarté afin que les clients voient le statut sans lire le chiffre. |
| **Show availability date when out of stock** | Yes | Affiche la date de disponibilité de la déclinaison sous le statut en rupture. Mettez **Yes** si vous renseignez les dates de disponibilité. Fixe les attentes de réassort. |
| **Show minimal quantity** | Off | Affiche la qté minimale de commande de la déclinaison. Mettez **Yes** pour les packs B2B ; réduit les erreurs d’ajout au panier. |
| **Show price** | Yes | Colonne prix par déclinaison (liste uniquement). Mettez **Yes** pour presque toutes les boutiques. Les clients comparent les variantes par prix. La grille utilise Grid cells → show price. |
| **Show unit price** | Off | Colonne prix unitaire (liste uniquement). Mettez **Yes** si vous utilisez le prix unitaire. Valeurs vides/étranges si l’unité n’est pas définie sur le produit. |
| **Show savings column** | No | Combien une déclinaison est moins chère vs la plus chère (liste uniquement). Mettez **Yes** pour la psychologie d’upsell. Colonne supplémentaire avec % et montant économisé. La grille utilise Grid cells → savings badge. |
| **Show volume (quantity) discounts column** | Off | Liste les paliers de remise quantité par déclinaison (liste uniquement). Mettez **Yes** pour le gros. Tableau plus large ; idéal en B2B. |
| **Hide volume discount rows that do not apply** | Off | Nettoie les listes de remises vides dans la colonne liste. Mettez **Yes** pour réduire le bruit et ne garder que les paliers utiles. |

### 3.9 Cart — Prices

![Cart settings — English back office](https://mypresta.eu/docs/images/docs/combinationstab-cart.webp)

Sous-onglet **Prices**. Règles globales d’affichage des prix pour la liste et la grille 2D. L’enregistrement affiche *Cart & price settings saved.*

| Field | At the start | What it does |
|---|---|---|
| **Show prices only to logged-in customers** | No | Les invités voient une invite de connexion au lieu des prix. Mettez **Yes** pour les prix B2B masqués. Les invités doivent se connecter pour voir les montants dans la liste et la grille. |
| **Tax display** | Tax included | Taxes incluses, exclues, ou suivre le réglage du groupe client. Alignez sur la politique de prix de votre boutique. Un mauvais choix confond acheteurs B2B et B2C. |
| **Show “tax incl./excl.” label next to price** | Off | Petit texte après le prix. Mettez **Yes** pour la clarté légale dans l’UE. Cellules un peu plus chargées. |
| **Show discount % badge on reduced prices** | Off | Affiche -X% lorsqu’une réduction de prix spécifique existe. Mettez **Yes** pour mettre en avant les offres. Attire l’attention sur les déclinaisons remisées dans la liste et la grille. |
| **Highlight the cheapest combination** | Yes | Marque la ligne/cellule au prix le plus bas. Mettez **Yes** pour guider les achats impulsifs. Surbrillance verte du meilleur prix dans la liste et la grille. |

### 3.10 Cart — Add to cart

| Field | At the start | What it does |
|---|---|---|
| **Show add to cart controls** | Yes | Champ quantité et/ou bouton par déclinaison. Mettez **Yes** pour vendre depuis le tableau. **No** = matrice d’affichage uniquement. |
| **Add to cart only for logged-in customers** | Off | Les invités ne peuvent pas ajouter depuis le tableau. Mettez **Yes** pour le B2B. Les invités voient un message à la place des boutons. |
| **Show quantity input** | Yes | Case qté éditable. **Yes** toujours recommandé. **No** masque la qté (plus difficile d’acheter plusieurs unités). |
| **Qty box also in the table header (fill all rows)** | Off | Une qté d’en-tête se copie sur toutes les lignes. Commodité optionnelle. Accélère le remplissage en masse ; à utiliser avec prudence. |
| **Plus / minus buttons** | No | Boutons +/- à côté de la qté. Mettez **Yes** pour les appareils tactiles. Changements de quantité plus faciles. |
| **Block qty higher than stock** | Off | Empêche de commander plus que le disponible (lorsque les commandes hors stock ne sont pas autorisées). Mettez **Yes** pour éviter le survente. Le bouton + s’arrête au stock. |
| **AJAX add to cart** | Yes | Ajoute sans rechargement complet de la page. Mettez **Yes** sur les thèmes modernes. UX plus fluide ; désactivez uniquement en cas de conflit de thème. |
| **Bulk add to cart (one button for many rows)** | Off | Le client remplit plusieurs champs qté, puis un **Add to cart** envoie tout. Mettez **Yes** pour B2B/mode. Les boutons par ligne peuvent être masqués ; une barre sticky apparaît sur mobile. |
| **Show live total price of selected quantities** | Off | Calcule la somme des lignes sélectionnées (respecte les remises quantité si possible). Mettez **Yes** avec l’ajout en masse. Les clients voient la valeur du panier avant de cliquer Add. |
| **Tip: how many units until next quantity discount** | Yes | Sous la barre en masse, indique au client « add X more to unlock the next discount ». Mettez **Yes** si vous utilisez les remises quantité. Encourage des paniers plus grands. |
| **Use Font Awesome cart icon** | Off | Icône FA au lieu de l’icône Material. Mettez **Yes** uniquement si votre thème charge Font Awesome. FA manquant = icône cassée. |

### 3.11 B2B Tools and Groups

![B2B tools — English back office](https://mypresta.eu/docs/images/docs/combinationstab-b2b.webp)

**Tools** — aides gros. Les interrupteurs globaux sont des valeurs par défaut ; utilisez **Groups** pour autoriser ou refuser par groupe de clients PrestaShop. L’enregistrement affiche *B2B settings saved.*

| Field | At the start | What it does |
|---|---|---|
| **CSV quantity import on product page** | No | Les acheteurs collent des lignes comme SKU;5 (ou EAN;qty) pour remplir les quantités. Mettez **Yes** pour le gros ; puis autorisez-le par groupe si besoin. Gain de temps énorme pour les réassortiments. |
| **Export order sheet (CSV / XLSX / PDF)** | No | Télécharge les déclinaisons avec les quantités saisies. Mettez **Yes** pour les acheteurs qui envoient des feuilles à la comptabilité. Les boutons apparaissent à côté de l’ajout en masse. |
| **Fill last order button** | No | Restaure les quantités du dernier ajout en masse / export pour ce produit. Mettez **Yes** pour les commandes gros répétées. Un clic remplit à nouveau la matrice. |

**Groups** — pour chaque groupe de clients réglez **Show table**, **Add to cart**, **CSV import**, **Export**, **Reorder** (Yes/No). Défauts sans règle personnalisée : show table Yes, add to cart Yes, CSV/export/reorder suivent les interrupteurs globaux Tools (off après installation). Si **Show table** est No pour le groupe du visiteur, la matrice n’apparaît pas. Si **Add to cart** est No, le visiteur ne peut pas ajouter depuis le tableau même lorsque les interrupteurs Cart globaux sont actifs.

### 3.12 Visibility

![Visibility — English back office](https://mypresta.eu/docs/images/docs/combinationstab-visibility.webp)

Contrôlez sur quels produits les clients voient le tableau de déclinaisons. Recherchez des produits avec le sélecteur à l’écran (recherche AJAX). Confirmation : *Successfully updated*.

| Field | At the start | What it does |
|---|---|---|
| **Visibility rule** | Show on all products | Décide si le tableau apparaît sur tous les produits, seulement sur les sélectionnés, ou partout sauf les sélectionnés. Choisissez une règle, puis cochez des catégories / ajoutez des produits dans le sélecteur ci-dessous. « All products » est le plus simple ; utilisez Include/Exclude lorsque seule une partie du catalogue a besoin de la matrice. |
| **Selected categories & products** | None | La liste des catégories et produits utilisés par la règle ci-dessus. Cochez des catégories et/ou recherchez des produits et cliquez Add. Utilisé uniquement lorsque la règle est Include ou Exclude — ignoré pour « all products ». |
| **Hide table when product has too few attribute groups** | Off | Masque le tableau sur les produits qui n’ont que peu de groupes d’attributs (par ex. seulement Color, pas de Size). Mettez **Yes** et le nombre ci-dessous. Exemple : seuil 1 masque les produits avec 1 groupe d’attributs ou moins — utile si vous ne voulez la matrice que pour les produits Color+Size. |
| **Hide when attribute groups ≤** | Empty | Seuil pour l’interrupteur ci-dessus. Entrez 1 pour masquer les produits à un attribut ; 0 ne masque pratiquement jamais via cette règle. Comparé au nombre de groupes d’attributs du produit. |

### 3.13 Exclusions

Masquez définitivement des déclinaisons choisies du tableau (tous les produits). Recherchez un produit, choisissez des déclinaisons avec **Select**, puis **Save**. Confirmation : *Settings saved*. Ces variantes restent dans PrestaShop mais n’apparaissent jamais dans la matrice — utile pour des tailles obsolètes ou des SKU internes. La recherche produit et déclinaison utilise la même recherche AJAX produit que Visibility.

| Field | At the start | What it does |
|---|---|---|
| **Search for product** | Empty | Trouvez le produit dont vous voulez exclure les déclinaisons. |
| **Combination** | None selected | Marquez les déclinaisons à masquer de la matrice vitrine, puis Save. |

### 3.14 Integrations

![Integrations — English back office](https://mypresta.eu/docs/images/docs/combinationstab-integrations.webp)

L’enregistrement affiche *Integrations saved.* Le formulaire indique Advanced Stock Management lorsqu’il est détecté ; sans ASM, laissez l’interrupteur entrepôt sur Off.

| Field | At the start | What it does |
|---|---|---|
| **Combination wishlist** | No | Le bouton cœur enregistre une variante dans une wishlist légère (compte ou cookie). Mettez **Yes** si les clients marquent des tailles. Le lien apparaît dans My Account ; ce n’est pas une suite wishlist complète. |
| **Back-in-stock email alerts** | No | Les lignes en rupture obtiennent un bouton de notification ; lorsque le stock revient, le module e-mail le client. Mettez **Yes** et assurez-vous que votre boutique peut envoyer des e-mails. Récupère la demande sur les tailles manquantes. |
| **Warehouse stock column** | No | Liste les quantités par entrepôt lorsque Advanced Stock est activé. Mettez **Yes** uniquement avec ASM. Sans ASM la colonne reste vide — laissez Off. |

### 3.15 Overrides

![Overrides — English back office](https://mypresta.eu/docs/images/docs/combinationstab-overrides.webp)

Les profils cascadenent **Product → deepest Category → Manufacturer → Global**. Seuls les champs surchargés modifient la couche inférieure. Filtrez la liste avec **All / Products / Categories / Manufacturers**. Créez avec **Product override**, **Category override** ou **Manufacturer override**.

Sur l’écran d’édition : recherchez et sélectionnez une entité, activez uniquement les champs à surcharger, laissez les champs non cochés hériter. Utilisez **Copy all from global** pour préremplir les valeurs, puis **Save override**. Succès : *Override profile saved.* La suppression demande *Delete this override profile ?* Succès : *Override profile deleted.*

Raisons typiques d’utiliser des overrides : une marque a toujours besoin du mode grille ; une catégorie masque les prix pour les invités ; un produit a besoin de colonnes SKU supplémentaires sans changer toute la boutique.

### 3.16 Updates

**Check now** demande à MyPresta si une version plus récente existe. Messages : *New version available!* ou *Module is up to date!*

| Field | At the start | What it does |
|---|---|---|
| **Check updates** | — | Lance une vérification immédiate et indique si une nouvelle version existe. |
| **Updates notifications** | Select / as previously saved | Activez cette option si vous souhaitez vérifier automatiquement MyPresta.eu pour les mises à jour du module. Cette option affichera une notification sur les nouvelles versions de cet addon. |
| **Module page** | Link on screen | Lien direct vers la page officielle de l’addon où vous pouvez lire les changements du module (changelog). Utilisez Support (chapitre 7) pour les demandes d’aide. |

## 4. Front office

- **Placement :** pied de produit sous le contenu produit, ou un onglet **Product variants** dans la zone d’onglets produit, selon Display → Placement.
- **List vs 2D grid :** la liste est une ligne par déclinaison. La grille est une matrice lorsque le produit a exactement deux groupes d’attributs et que View mode est Grid ou Auto ; sinon la vitrine bascule vers la liste.
- **Filters :** pastilles d’attributs au-dessus du tableau/grille lorsque activées.
- **Sorting / pagination / mobile cards :** liste uniquement, lorsque ces options Display sont activées.
- **Add to cart :** contrôles par ligne et/ou **Add to cart** en masse avec total live optionnel et tip « units until next discount ».
- **Toolbar :** lorsque activée — **Fill last order**, **Export** (CSV / XLSX / PDF), zone de texte **Import quantities** avec des lignes comme `REF001;5`, puis **Apply**.
- **Wishlist :** cœur sur les lignes/cellules lorsque Integrations + interrupteurs colonne/cellule le permettent. Les clients connectés obtiennent **My combination wishlist** sur la page compte client.
- **Back in stock :** contrôle de notification sur les lignes en rupture ; e-mail lorsque le stock revient (le mail boutique doit fonctionner).
- **Guest prices :** avec « prices only for logged-in », les invités voient une invite de connexion au lieu des montants ; avec « ATC only for logged-in », les invités ne peuvent pas ajouter depuis le tableau.

Aucune capture vitrine séparée n’est requise ici ; la mise en page du thème décide de l’habillage exact autour du bloc du module.

## 5. Problèmes courants

### 5.1 Tableau non visible sur la fiche produit

Vérifiez module activé, produit avec déclinaisons, règle **Visibility** qui inclut le produit, groupe client **Show table** à Yes, et position adaptée à votre thème (pied vs onglets). Videz le cache. Confirmez qu’Exclusions n’a pas masqué toutes les déclinaisons.

### 5.2 Mauvaise position ou onglet vide

Changez **Position on the product page**. Sur les thèmes modernes, ignorez Tab style. Si vous utilisez des onglets, ouvrez le produit et cherchez **Product variants**.

### 5.3 Grille 2D attendue mais liste affichée

La grille nécessite exactement deux groupes d’attributs et View mode Grid ou Auto. Un attribut, ou trois ou plus, force la liste. Le même groupe d’attributs pour les deux axes bascule aussi vers la liste — définissez des groupes de lignes et de colonnes différents.

### 5.4 Bloc d’achat par défaut manquant ou encore visible

Vérifiez **Hide default PrestaShop buy block** et **Hide default buy block only when table has combinations**. Si le bloc natif est masqué mais que le tableau n’a pas d’ajout au panier, les clients ne peuvent pas acheter — activez Cart → **Show add to cart controls**.

### 5.5 L’ajout en masse ne fait rien ou recharge mal

Activez **AJAX add to cart** pour les thèmes modernes. Confirmez que **Bulk add to cart** est Yes et que les quantités sont remplies. La règle de groupe **Add to cart** doit être Yes pour ce groupe client.

### 5.6 Les règles de groupe bloquent l’ajout au panier ou masquent le tableau

Sous **B2B** → **Groups**, mettez **Show table** et **Add to cart** à Yes pour le groupe du visiteur (Guest, Customer, ou votre groupe gros).

### 5.7 Prix masqués pour les invités

Attendu lorsque **Show prices only to logged-in customers** est Yes. Mettez Off pour les prix publics, ou demandez aux invités de se connecter.

### 5.8 Wishlist ou réapprovisionnement manquant

Activez-les sous **Integrations**, puis activez les interrupteurs de colonne liste ou de cellule grille correspondants. Pour BIS, confirmez que PrestaShop peut envoyer des mails et que le stock se met à jour lors du réassort.

### 5.9 Colonnes description / caractéristiques de déclinaison verrouillées

Installez et activez le module optionnel **Product combination features**. Jusque-là ces colonnes restent verrouillées dans Display et Overrides.

### 5.10 CSV / export / remplir dernière commande manquants

Activez les outils sous **B2B** → **Tools**, et mettez Yes pour ce groupe client sous **Groups**.

## 6. Guide développeur

### 6.1 Vue d’ensemble

- Nom technique : `combinationstab`
- Version : 3.0.5
- Nom affiché : Combinations Tab Pro
- Auteur : mypresta.eu
- Onglet module : `smart_shopping`
- Classe principale : `Combinationstab`
- UI BO : `CtpAdminBo` (`lib/CtpAdminBo.php`)
- Résolution des réglages : `CtpSettingsResolver` (Product → Category → Manufacturer → Global)
- Optionnel : `CtpCombfeat` — le fichier peut être absent ; `class_exists('CtpCombfeat')` contrôle description/caractéristiques de déclinaison. Sans la classe, ces options restent verrouillées.

Flux : Configuration / réglages d’entité → les hooks FO rendent les templates liste ou grille → les contrôleurs front gèrent les aides AJAX panier, wishlist, BIS, CSV, export, réassort, calculateur de prix.

### 6.2 Fichiers importants

| Path | Role |
|---|---|
| `combinationstab.php` | Classe module, install/uninstall, hooks, formulaires visibility/exclusions |
| `lib/CtpAdminBo.php` | Onglets de la page Configure et champs HelperForm |
| `lib/CtpColumnRegistry.php` | Colonnes liste, presets, JSON d’ordre |
| `lib/CtpGridRegistry.php` | Blocs de cellules grille et JSON d’ordre |
| `lib/CtpGrid2d.php` | Construction matrice 2D / `shouldUseGrid` |
| `lib/CtpCombinationsData.php` | Lignes de déclinaison pour le FO |
| `lib/CtpGroupRules.php` | Par groupe show/atc/csv/export/reorder |
| `lib/CtpWishlist.php` / `CtpBackInStock.php` / `CtpExport.php` / `CtpReorder.php` | Aides de fonctionnalités |
| `lib/CtpSettingsResolver.php` | Table d’override et cascade |
| `views/templates/admin/tabs.tpl` | Habillage onglets BO |
| `views/templates/hook/productfooter.tpl` / `productfooter_grid.tpl` | Liste / grille FO |
| `views/templates/hook/_toolbar.tpl` | Barre bulk / export / CSV |
| `controllers/front/*.php` | Endpoints front |
| `controllers/admin/AdminCombinationstabSearchController.php` | Recherche AJAX produit pour les sélecteurs BO |

### 6.3 Contrôleurs

**Admin :** `AdminCombinationstabSearchController` — recherche AJAX produit/déclinaison utilisée par Visibility, Exclusions, Overrides. Pas une page de menu pour les marchands.

**Front :**

| Controller | Purpose |
|---|---|
| `Wishlist` | Basculer / lister la wishlist (JSON + page compte) |
| `BackInStock` | S’abonner aux alertes OOS (JSON) |
| `CsvImport` | Appliquer les quantités SKU/EAN collées (JSON) |
| `Export` | Télécharger la feuille CSV/XLSX/PDF |
| `Reorder` | Enregistrer / restaurer les dernières quantités (JSON) |
| `PriceCalculator` | Total sélectionné en live / tip volume (corps JSON, pas de curl) |

### 6.4 Hooks (enregistrés à l’installation)

`displayHeader`, `displayProductFooter`, `displayFooterProduct`, `displayProductTab`, `displayProductExtraContent`, `displayProductTabContent`, `CombinationsTable`, `ActionAdminControllerSetMedia`, `displayCustomerAccount`, `actionUpdateQuantity`.

Pas de `enable()` / `disable()` personnalisés au-delà des défauts PrestaShop. Uninstall supprime les tables de fonctionnalités puis `parent::uninstall()`.

### 6.5 Overrides

Le module ne livre aucun override de classe/contrôleur sous `override/`. Les overrides de templates `.tpl` du module dans le thème sont optionnels et côté marchand.

### 6.6 Base de données

Uninstall supprime ces tables ; les clés Configuration sont conservées.

| Table | Content |
|---|---|
| `ctp_wishlist` | `id_ctp_wishlist`, customer/guest, product, combination, shop, `date_add` |
| `ctp_backinstock` | Abonnements e-mail, product/combination, shop, lang, `notified`, dates |
| `ctp_entity_settings` | `entity_type`, `id_entity`, JSON `settings`, `date_upd` |

### 6.7 Clés de configuration et défauts (installation)

Défauts sélectionnés écrits à l’installation : `ctp_position` = `productFooter`, `ctp_where` = `1`, `ctp_view_mode` = `list`, `ctp_image`/`ctp_price`/`ctp_reference`/`ctp_cname`/`ctp_atc`/`ctp_atcq`/`ctp_ajax`/`ctp_sort`/`ctp_quantity`/`ctp_availability`/`ctp_availability_d` = `1`, `ctp_ean`/`ctp_mpn` = `0`, `ctp_wishlist`/`ctp_bis`/`ctp_export`/`ctp_csv_import`/`ctp_reorder` = `0`, `ctp_group_rules` = `{}`, `ctp_column_order` = JSON de `CtpColumnRegistry::defaultKeys()`, plus clés taxe/masquer/grille associées comme dans `install()`. L’ordre colonnes/cellules utilise aussi du JSON (`ctp_column_order`, `ctp_grid_cell_order`). Traductions : `translations/{iso}.php`. Les textes `desc` des champs vivent principalement dans `CtpAdminBo`.

### 6.8 Extension

Surchargez les templates FO depuis le thème sous `modules/combinationstab/...` sans éditer le paquet du module. Le thème doit toujours appeler les hooks produit enregistrés pour la sortie. L’intégration optionnelle Combination features exige `lib/CtpCombfeat.php` présent et `CtpCombfeat::isAvailable()` true.

## 7. Support

Page produit : https://mypresta.eu/modules/front-office-features/product-page-combinations-table.html

Pour obtenir de l’aide : connectez-vous à votre compte client sur mypresta.eu, ouvrez Contact et choisissez **Support for paid modules**. Le formulaire exige une connexion pour les modules payants ; après connexion, sélectionnez ce module dans votre historique d’achats.
