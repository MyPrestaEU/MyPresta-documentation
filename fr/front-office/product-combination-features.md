---
title: "Caractéristiques de la déclinaison - manuel marchand"
description: "Manuel de configuration et de dépannage pour les équipes qui ont déjà le module installé."
sidebar:
  label: "Caractéristiques de la déclinaison - manuel marchand"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Product combination features sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-combination-features.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/product-combination-features/)
>
> ---


Nom technique : `combfeat`. Version **1.4.0**. Dans le back-office le module s’appelle **Caractéristiques de la déclinaison**.

## 1. Prérequis et compatibilité

- **PrestaShop :** 1.7.0.0 à 9.x (`ps_versions_compliancy` jusqu’à 9.99.99).
- **PHP :** la version exigée par cette version de PrestaShop.
- **Fiche produit :** le thème doit exposer la déclinaison choisie dans l’attribut `data-product` de `#product-details` (standard PrestaShop) et émettre l’événement `updatedProduct` quand les attributs changent. Classic et les thèmes qui en dérivent le font.
- **PrestaShop 8 et 9, onglet Modules du produit :** le fichier `src/PrestaShopBundle/Resources/views/Admin/Sell/Catalog/Product/Blocks/modules-content.html.twig` doit être accessible en écriture à l’installation ou à la première ouverture de la configuration. Voir la section 3.
- **Navigation à facettes (facultatif) :** `ps_facetedsearch` installé, droit de créer une vue SQL, et écriture sur `modules/ps_facetedsearch/src/Adapter/MySQL.php`.
- **Vérification des mises à jour (facultatif) :** `allow_url_fopen` pour que le module appelle `https://dev.mypresta.eu`.

## 2. Où travailler dans le back-office

| Endroit | Chemin | Rôle |
| --- | --- | --- |
| Configuration du module | **Modules > Gestionnaire de modules**, chercher **Caractéristiques de la déclinaison**, **Configurer** | Interrupteurs, sélecteurs CSS, mode de titre, navigation à facettes, import CSV, mises à jour |
| Contenu de la déclinaison | **Catalogue > Produits**, modifier le produit, onglet **Modules**, bloc **Contenu de la déclinaison** | Caractéristiques, description et titres de chaque déclinaison |
| Catalogue des caractéristiques | **Catalogue > Attributs et caractéristiques** (libellé selon la version de PrestaShop) | Créer les caractéristiques et les valeurs avant de les attacher au produit. L’import CSV peut créer celles qui manquent |
| Modèle de navigation à facettes | Configuration du module Navigation à facettes | Ajouter la caractéristique au modèle de filtres. Ce module ne le fait pas à votre place |

Le module n’a pas d’entrée de menu propre et pas de contrôleur front-office ou back-office.

## 3. Fichiers que le module modifie

### 3.1 Onglet Modules du produit sous PrestaShop 8 et 9

À l’installation, et à chaque ouverture de la page de configuration, le module modifie :

`src/PrestaShopBundle/Resources/views/Admin/Sell/Catalog/Product/Blocks/modules-content.html.twig`

Il remplace `{{ module.content|raw_purified }}` par `{{ module.content|raw }}`. La première fois, il copie le fichier d’origine vers `modules-content.html.twig.raw.bak` à côté.

PrestaShop 8 et 9 purifient sinon le HTML affiché par les modules sur la fiche produit. Sans ce changement, l’éditeur **Contenu de la déclinaison** est vide ou ses champs ne partent pas avec l’enregistrement du produit. Sous PrestaShop 1.7 ce fichier Twig n’existe pas. Le module ignore le changement.

Si le fichier ne peut pas être lu ou écrit, le module n’affiche pas d’erreur. Vérifiez les droits si l’onglet Modules reste vide.

### 3.2 Adaptateur de la navigation à facettes

Quand **Filter combination features in Faceted Search** est activé (valeur par défaut), le module crée la vue SQL `{prefix}combfeat_feature_product` et fait pointer `modules/ps_facetedsearch/src/Adapter/MySQL.php` vers cette vue. La vue est la liste des caractéristiques du produit plus les caractéristiques actives des déclinaisons.

Désactiver l’option, désactiver le module ou le désinstaller réécrit la source d’origine de l’adaptateur. La désinstallation supprime aussi la vue quand l’adaptateur n’y fait plus référence.

La page de configuration affiche un avertissement si la vue ne peut pas être créée, si le fichier d’adaptateur est absent, illisible, non inscriptible, ou s’il ne correspond pas à la source Faceted Search attendue. Les messages (en anglais dans le module) :

- Could not create the Faceted Search feature view. Combination features will not appear in category filters.
- Faceted Search is installed, but its database adapter was not found. Combination features will not appear in category filters.
- Faceted Search adapter could not be read. Combination features will not appear in category filters.
- This Faceted Search version does not use the expected feature table. Combination features will not appear in category filters.
- Faceted Search adapter is not writable. Make modules/ps_facetedsearch/src/Adapter/MySQL.php writable so combination features can be filtered.
- Faceted Search adapter could not be updated. Combination features will not appear in category filters.

## 4. Configuration du module

Ouvrez **Configurer**. Deux formulaires sont sur la page, puis le panneau **Mises à jour MyPresta**. **Enregistrer** sur le formulaire des paramètres envoie `submitCombfeatSettings`. **Import** envoie `submitCombfeatImport`.

### 4.1 Activer les caractéristiques pour les déclinaisons

Clé : `combfeat_p_feat`. Défaut : **Activé**.

Quand l’option est activée, chaque déclinaison de l’onglet **Modules** du produit a un onglet **Caractéristiques**. Vous y attachez des valeurs déjà existantes.

Quand elle est désactivée, cet onglet est masqué. Le script de la boutique est un autre sujet : caractéristiques et descriptions sont mises à jour par le même script, décrit à la section 6.

**Enregistrer un produit pendant que cet interrupteur est coupé efface les caractéristiques de déclinaison de ce produit.** Le formulaire ne contient plus les champs de caractéristiques. Un enregistrement vide les lignes de caractéristiques du module pour le produit, puis réécrit seulement ce que le formulaire a envoyé. Les descriptions et les titres restent. Réactivez l’option avant de modifier le produit si ces caractéristiques doivent rester.

### 4.2 Classe CSS de la fiche technique

Clé : `combfeat_ds`. Défaut : `.data-sheet`.

Un sélecteur jQuery. Le module remplace le **HTML interne** de l’élément trouvé par des paires :

```html
<dt class="name">Caractéristique</dt><dd class="value">Valeur</dd>
```

Pointez-le vers le `<dl>` qui contient déjà ces lignes. Dans le thème Classic, c’est `dl.data-sheet` : la valeur par défaut convient. Un bloc plus large, comme `.product-features` ou `#product-details`, est entièrement remplacé par les paires `<dt>` / `<dd>`.

Si le sélecteur ne trouve rien et que la déclinaison choisie a des caractéristiques, le module remplace tout le contenu de `#product-details` par une nouvelle section de fiche technique. La référence, la marque et le reste du contenu de `#product-details` disparaissent. Réglez le sélecteur pour que ce repli ne serve pas.

### 4.3 Flux de travail

Clé : `combfeat_workflow`. Défaut : **Remplacer les caractéristiques existantes du produit** (valeur `0`).

| Option | Valeur | Fiche technique après le choix d’une déclinaison |
| --- | --- | --- |
| **Remplacer les caractéristiques existantes du produit** | `0` | Les caractéristiques de la déclinaison remplacent la fiche technique. Si la déclinaison n’en a pas, les caractéristiques du produit sont réécrites. |
| **Ajouter à la liste existante des caractéristiques du produit** | `1` | Les caractéristiques du produit restent en premier. Celles de la déclinaison suivent. Si la déclinaison n’en a pas, seules celles du produit s’affichent. |

La même valeur présente sur le produit et sur la déclinaison apparaît deux fois en mode **Ajouter**. Le module ne retire pas les doublons.

Plusieurs valeurs d’une même caractéristique sont autorisées. Chaque valeur est une ligne. L’ordre suit la position de la caractéristique dans le catalogue.

**Le flux de travail ne change que la fiche technique.** La description est toujours remplacée, dans les deux modes. Voir la section 6.4.

Le script de la boutique dépend de ce réglage : `views/js/combfeat.js` pour Remplacer, `views/js/combfeat-append.js` pour Ajouter.

### 4.4 Filter combination features in Faceted Search

Clé : `combfeat_faceted`. Défaut : **Enabled**.

Le libellé à l’écran est en anglais : **Filter combination features in Faceted Search**. Ce texte n’est pas encore dans les fichiers de traduction du module. Le texte d’aide en dessous est aussi en anglais : les valeurs qui n’existent que sur des déclinaisons apparaissent dans `ps_facetedsearch`, et un produit est compté si la valeur est sur le produit ou sur n’importe quelle déclinaison. Il faut ajouter la caractéristique au modèle Faceted Search. La liste de caractéristiques du produit ne change pas.

Quand `ps_facetedsearch` est installé et que l’interrupteur est activé :

- Les filtres de catégorie peuvent afficher des valeurs qui n’existent que sur des déclinaisons.
- Un produit est compté si la valeur est sur le produit **ou sur n’importe laquelle de ses déclinaisons**. Le filtre ne dépend pas de la déclinaison que le visiteur choisira ensuite. Un produit compte une fois, même si plusieurs déclinaisons portent la valeur.
- Vous ajoutez quand même la caractéristique au modèle de navigation à facettes. Le module ne modifie pas les modèles.
- La liste de caractéristiques sur la fiche produit du catalogue reste telle quelle.

Après l’enregistrement des caractéristiques de déclinaison, ou après un import CSV, le module vide le cache de blocs de la navigation à facettes (`layered_filter_block`) pour que les filtres se reconstruisent.

### 4.5 Activer les descriptions pour les déclinaisons

Clé : `combfeat_p_desc`. Défaut : **Activé**.

Dans la source anglaise, le libellé est **Turn on descriptionsfor combinations** (pas d’espace avant « for »). La traduction française est **Activer les descriptions pour les déclinaisons**.

Quand l’option est activée, chaque déclinaison a un onglet **Description** avec un champ de texte riche par langue de la boutique.

Quand elle est désactivée, cet onglet est masqué et l’enregistrement du produit ne change pas les descriptions déjà stockées. Si les caractéristiques restent activées, le script de la boutique tourne encore et applique une description enregistrée plus tôt. Videz les champs, enregistrez, puis seulement ensuite coupez l’interrupteur si la boutique ne doit plus s’en servir.

### 4.6 Description de la classe CSS / ID de l objet

Clé : `combfeat_description`. Défaut : `#description`.

Le libellé affiché est exactement **Description de la classe CSS / ID de l objet**.

Sélecteur jQuery du bloc dont le HTML est remplacé par la description de la déclinaison. Dans le thème Classic, `#description` est l’onglet de la description longue : la valeur par défaut vise ce bloc.

Si le sélecteur ne trouve rien, la description de la page n’est pas touchée.

Le texte utilisé quand une déclinaison n’a pas de description est la **description longue** du produit (`description`), dans la langue courante. Ce n’est pas la description courte et ce n’est pas la méta description. Si ce sélecteur pointe vers le bloc de description courte, une déclinaison sans texte propre remplit ce bloc avec la description longue.

### 4.7 Activer le méta titre pour les déclinaisons

Clé : `combfeat_p_title`. Défaut : **Activé**.

Quand l’option est activée, la fiche produit charge `views/js/combfeat-title.js`. Choisir une déclinaison met à jour `document.title` et, s’il est présent, `<meta property="og:title">`.

Le titre dans le HTML envoyé par le serveur reste le méta titre du produit. Le visiteur voit le titre de la déclinaison après l’exécution du JavaScript. Un robot qui n’exécute pas JavaScript garde le titre du produit.

Quand l’option est désactivée, l’onglet **Méta titre** est masqué, le script n’est pas chargé, et l’enregistrement ne change pas les titres stockés.

### 4.8 Mode de titre par défaut

Clé : `combfeat_title_default`. Défaut : **Ajouter le nom de l attribut et la valeur (séparés par une virgule)** (valeur `1`).

Utilisé seulement quand cette déclinaison n’a ni **Titre complet** ni **Ajouter au titre** dans la langue courante.

Le titre d’origine est le titre du navigateur mémorisé au premier chargement de la page. Les changements suivants ne le mémorisent pas de nouveau : les fragments ajoutés ne s’empilent pas.

| Option | Valeur | Résultat |
| --- | --- | --- |
| **Ne pas modifier le titre par défaut** | `0` | Le titre de document d’origine reste. |
| **Ajouter le nom de l attribut et la valeur (séparés par une virgule)** | `1` | Titre d’origine, puis le séparateur, puis les groupes et les valeurs, par exemple `Couleur : Rouge, Taille : M`. |
| **Ajouter uniquement les valeurs d attribut (séparées par une virgule)** | `2` | Titre d’origine, puis le séparateur, puis les valeurs seules, par exemple `Rouge, M`. |

Les noms de groupes et les valeurs viennent de la langue courante de la boutique.

### 4.9 Séparateur de titre

Clé : `combfeat_title_separator`. Défaut : ` - ` (espace, trait d’union, espace).

Placé entre le titre de document d’origine et la partie ajoutée. La partie ajoutée est soit le texte du mode par défaut, soit **Ajouter au titre** de la déclinaison. Le séparateur est utilisé tel qu’il est enregistré, espaces compris.

**Titre complet** n’utilise pas le séparateur. Il remplace seul le titre du document.

Si le titre d’origine est vide, seule la partie ajoutée est utilisée.

### 4.10 Récapitulatif des réglages

| Réglage | Clé | Défaut |
| --- | --- | --- |
| Activer les caractéristiques pour les déclinaisons | `combfeat_p_feat` | Activé (`1`) |
| Classe CSS de la fiche technique | `combfeat_ds` | `.data-sheet` |
| Flux de travail | `combfeat_workflow` | Remplacer (`0`) |
| Filter combination features in Faceted Search | `combfeat_faceted` | Activé (`1`) |
| Activer les descriptions pour les déclinaisons | `combfeat_p_desc` | Activé (`1`) |
| Description de la classe CSS / ID de l objet | `combfeat_description` | `#description` |
| Activer le méta titre pour les déclinaisons | `combfeat_p_title` | Activé (`1`) |
| Mode de titre par défaut | `combfeat_title_default` | Nom d’attribut et valeur (`1`) |
| Séparateur de titre | `combfeat_title_separator` | ` - ` |

## 5. Import des caractéristiques de déclinaison

Deuxième formulaire de la page de configuration. Ces libellés sont pour l’instant les textes sources anglais dans toutes les langues (ils ne sont pas encore dans les fichiers de traduction).

L’import affecte des valeurs de caractéristiques à des déclinaisons. Il n’importe ni descriptions ni titres, et il n’écrit pas de lignes dans la liste de caractéristiques du produit (`feature_product`). Une caractéristique ou une valeur absente est créée dans le catalogue.

### 5.1 Import mode

| Mode | Effet |
| --- | --- |
| **Append to combination features** (défaut) | Conserve les affectations déjà stockées. Une ligne déjà présente sur cette déclinaison est ignorée. |
| **Replace features of listed combinations** | Pour chaque déclinaison présente dans le fichier, supprime les caractéristiques de cette déclinaison dans le module, puis écrit les lignes du fichier. Les déclinaisons absentes du fichier restent. Les descriptions et les titres ne sont pas supprimés. |

### 5.2 Règles du fichier

- UTF-8, extension `.csv` ou `.txt`. Un BOM en tête est accepté. Taille maximale **8 Mo**.
- Le séparateur est détecté sur la ligne d’en-tête : point-virgule, virgule ou tabulation. Si aucun n’apparaît, le point-virgule est utilisé.
- L’en-tête doit identifier la déclinaison par `id_product_attribute` ou `combination_reference`.
- L’en-tête doit identifier la caractéristique par `feature` et `value`, ou par `id_feature_value`.
- Les lignes vides sont ignorées. Au plus 30 erreurs de ligne sont listées ; le reste est compté.

Noms de colonnes acceptés (espaces et traits d’union deviennent des soulignés, la casse est ignorée) :

| Colonne | Également accepté |
| --- | --- |
| `id_product` | `product_id` |
| `id_product_attribute` | `id_combination`, `combination_id` |
| `product_reference` | — |
| `combination_reference` | `combination_ref`, `attribute_reference` |
| `feature` | `feature_name`, `id_feature` |
| `value` | `feature_value` |
| `id_feature_value` | `feature_value_id` |

`id_product` et `product_reference` sont facultatifs. Quand vous les remplissez, ils doivent appartenir à cette déclinaison. Un écart rejette la ligne.

Recherche de la déclinaison :

- `id_product_attribute` est utilisé quand il est supérieur à zéro. Si l’ID et `combination_reference` sont tous deux remplis, la référence doit correspondre à cette ligne.
- Sinon la référence de déclinaison est utilisée. Si plusieurs déclinaisons la partagent, ajoutez `id_product` ou `id_product_attribute`. Message : Combination reference matches more than one combination.

Recherche de la valeur :

- `id_feature_value` supérieur à zéro charge cette valeur. Les cellules de nom et de valeur sont ignorées.
- Sinon `feature` et `value` sont obligatoires. Une cellule de caractéristique composée uniquement de chiffres est un ID de caractéristique.
- Les noms sont cherchés exactement, puis sans tenir compte de la casse. Si plus d’une caractéristique ou valeur correspond, la ligne est rejetée. Rien n’est deviné.
- Une caractéristique absente est créée. Son nom est copié dans chaque langue de la boutique. Longueur maximale 128.
- Une valeur absente est créée comme valeur normale (pas personnalisée), avec le même texte dans chaque langue. Longueur maximale 255. Modifiez ensuite **Catalogue > Attributs et caractéristiques** si les langues doivent différer.

**Download sample file** envoie `import/combfeat-features-sample.csv` :

```csv
id_product;id_product_attribute;product_reference;combination_reference;feature;value;id_feature_value
12;45;DEMO-1;DEMO-1-RED;Material;Cotton;
12;46;DEMO-1;DEMO-1-BLUE;Material;Wool;
;;DEMO-2;DEMO-2-XL;Composition;100% cotton;
10;25;;;;;83
```

Les lignes de l’exemple signifient :

1. Déclinaison 45 du produit 12, les références doivent correspondre, caractéristique Material / Cotton (créée si elle manque).
2. Déclinaison 46 du produit 12, Material / Wool.
3. La déclinaison dont la référence est `DEMO-2-XL` sur le produit dont la référence est `DEMO-2`, caractéristique Composition / 100% cotton. Pas d’ID numériques.
4. Déclinaison 25 du produit 10, valeur de caractéristique existante 83. Nom et valeur vides.

Après un import réussi, le cache de blocs de la navigation à facettes est vidé. La confirmation indique combien d’affectations ont été enregistrées, combien étaient déjà présentes, et quelles lignes ont échoué.

## 6. Contenu de la déclinaison sur le produit

**Catalogue > Produits**, modifier le produit, onglet **Modules**. Titre du bloc : **Contenu de la déclinaison**. Sous-titre : **Caractéristiques, descriptions et méta titres par déclinaison**.

Créez d’abord les déclinaisons (onglet **Déclinaisons** du produit). Si le produit n’en a pas, le bloc le dit et il n’y a rien à modifier.

### 6.1 La liste

- **Tout développer** / **Tout réduire**.
- **Filtrer les déclinaisons…** correspond au nom de la déclinaison, à l’ID de déclinaison et à la référence de déclinaison.
- Chaque ligne montre l’image de la déclinaison (ou un substitut), les noms d’attributs, **Combination ID**, **Reference** quand la déclinaison en a une, et des pastilles. Les pastilles **Caractéristiques**, **Description** et **Titre** s’allument quand cette partie est remplie. La pastille des caractéristiques indique le nombre de valeurs. Combination ID et Reference sont les textes sources anglais.
- La première déclinaison est ouverte. **Configurer** ouvre une ligne, **Fermer** la replie.
- Dans la ligne, les onglets des interrupteurs activés : **Caractéristiques**, **Description**, **Méta titre**.

Si les trois interrupteurs sont coupés, le bloc affiche : Toutes les options de déclinaison sont désactivées. Activez les caractéristiques, descriptions ou titres dans la configuration du module.

### 6.2 Caractéristiques

Texte d’aide : Recherchez et associez les valeurs de caractéristiques utilisées pour cette déclinaison sur la page produit.

Saisissez au moins **2 caractères** du nom de caractéristique ou de la valeur, dans la langue courante de l’employé. Jusqu’à 20 correspondances apparaissent, libellées `Caractéristique : valeur`. En choisir une ajoute un jeton. La recherche ne trouve que des valeurs qui existent déjà. Créez-les dans le catalogue, ou par l’import CSV.

La même valeur ne peut pas être ajoutée deux fois. Plusieurs valeurs de la même caractéristique peuvent l’être. **×** retire un jeton. Le retrait est enregistré avec le produit.

### 6.3 Description

Un champ de texte riche par langue. La liste des langues apparaît quand la boutique a plus d’une langue. Un HTML vide signifie qu’il n’y a pas de description : en boutique la description longue du produit revient, et à l’enregistrement la ligne de cette langue est supprimée.

### 6.4 Méta titre

Les deux champs sont par langue, 512 caractères chacun. Un champ vide ignore cette surcharge.

| Champ | Effet en boutique |
| --- | --- |
| **Titre complet (remplace tout le titre)** | Remplace tout le titre du document. Le séparateur et le mode par défaut ne sont pas utilisés. Si les deux champs sont remplis, celui-ci l’emporte. |
| **Ajouter au titre (fragment ajouté à la fin)** | Titre de document d’origine, puis le séparateur, puis ce fragment. Utilisé quand le titre complet est vide. |

Quand les deux sont vides, le mode de titre par défaut de la section 4.8 s’applique.

### 6.5 Enregistrement

Les changements sont stockés avec le produit. Utilisez le bouton **Enregistrer** du produit (y compris enregistrer et prévisualiser, selon la version de PrestaShop). Le bloc n’a pas de bouton d’enregistrement propre.

À l’enregistrement, le module :

1. Supprime chaque ligne de caractéristique de déclinaison de ce produit et insère les jetons présents dans le formulaire.
2. Enregistre ou supprime la description pour chaque langue.
3. Enregistre la ligne de titre pour chaque langue, ou la supprime quand les deux champs de titre sont vides.
4. Vide le cache de blocs de la navigation à facettes quand cette option est activée.

Le formulaire envoie un champ caché `combfeat_submitted`. Si ce champ manque, le module ne touche pas aux données. Sous PrestaShop 8 et 9, cela dépend du changement Twig de la section 3.1.

Supprimer une déclinaison dans PrestaShop ne supprime pas ses lignes dans ce module. Les lignes ne servent plus, parce que la déclinaison n’existe plus. Les caractéristiques disparaissent quand vous enregistrez le produit (le formulaire n’envoie que les déclinaisons actuelles). Les lignes de description et de titre d’une déclinaison supprimée restent jusqu’à ce que vous les retiriez de la base.

## 7. Boutique

Les scripts ne sont ajoutés que sur la fiche produit, seulement si la requête n’est pas un rafraîchissement ajax de tout le contrôleur, seulement si le produit a des déclinaisons, et seulement si au moins un des trois interrupteurs est activé.

| Interrupteur | Script |
| --- | --- |
| Caractéristiques ou descriptions, flux = Remplacer | `views/js/combfeat.js` |
| Caractéristiques ou descriptions, flux = Ajouter | `views/js/combfeat-append.js` |
| Méta titre | `views/js/combfeat-title.js` |

Changer de déclinaison ne provoque pas de requête supplémentaire. Les données de toutes les déclinaisons sont imprimées dans la page pour la **langue courante**. Le script lit la déclinaison choisie dans l’attribut `data-product` de `#product-details` (`id_product_attribute`) et se relance sur l’événement `updatedProduct`.

`displayProductAdditionalInfo` imprime aussi un élément caché `#product-details-combfeat` avec la déclinaison résolue pour le premier affichage (groupes d’attributs de l’URL, `id_product_attribute` de la requête, ou déclinaison par défaut). Les déclinaisons indisponibles suivent le réglage de stock de PrestaShop et **Afficher les attributs indisponibles**. L’élément caché n’est utilisé que lorsque `#product-details` lui-même est absent. Un thème qui garde `#product-details` doit poser `data-product` sur cet élément. C’est le cas du modèle produit standard.

Le module ne charge pas de feuille de style en boutique. Les nouveaux `<dt class="name">` et `<dd class="value">` utilisent les règles de fiche technique du thème.

### 7.1 Caractéristiques et descriptions partagent un script

`combfeat.js` et `combfeat-append.js` mettent à jour la fiche technique **et** la description dès qu’ils sont chargés. Ils ne relisent pas les deux interrupteurs.

- Caractéristiques activées et descriptions désactivées : une description enregistrée plus tôt est encore appliquée, jusqu’à ce que vous la vidiez et enregistriez.
- Descriptions activées et caractéristiques désactivées : les caractéristiques encore stockées sont encore appliquées. Enregistrer le produit avec l’interrupteur des caractéristiques coupé supprime ces caractéristiques stockées. Voir la section 4.1.

Le script de titre est séparé et ne tourne que si l’interrupteur de titre est activé.

### 7.2 Fiche technique

Remplacer et Ajouter sont décrits à la section 4.3. À chaque passage, le module reconstruit les lignes. Le balisage supplémentaire que le thème avait dans la fiche technique (liens, classes en plus sur une valeur) n’est pas conservé.

### 7.3 Description

Si la déclinaison a une description dans la langue courante, ce HTML remplace le contenu du sélecteur de description. Sinon, la description longue du produit le remplace. Le mode Ajouter n’ajoute pas de texte de description.

### 7.4 Titre

Priorité pour la déclinaison choisie, dans la langue courante :

1. **Titre complet**, quand il n’est pas vide.
2. Sinon **Ajouter au titre**, joint par le séparateur de la section 4.9.
3. Sinon le mode de titre par défaut de la section 4.8.

`og:title` reçoit le même texte quand cette balise méta existe.

## 8. Navigation à facettes

Avec l’option activée, les filtres de catégorie lisent une vue qui réunit :

- `feature_product` — caractéristiques affectées au produit ;
- `combfeat` — caractéristiques actives affectées aux déclinaisons, jointes à `feature_value` pour obtenir l’ID de caractéristique.

Reconstruisez l’index de la navigation à facettes ou videz le cache PrestaShop si un filtre reste périmé après la résolution de l’avertissement sur la page de configuration. L’enregistrement des caractéristiques de déclinaison et l’import CSV vident déjà `layered_filter_block`.

La fiche produit en boutique continue d’afficher les caractéristiques produit de PrestaShop jusqu’à ce que le script de ce module s’exécute. Le filtre et la fiche technique sont deux sources distinctes.

## 9. Mises à jour MyPresta

Le panneau sous les formulaires :

| Commande | Comportement |
| --- | --- |
| **Vérifier maintenant** | Contacte MyPresta et affiche **Nouvelle version disponible !** ou **Le module est à jour !** |
| **Notifications de mise à jour** | **Activer** affiche un avertissement dans le back-office quand une version plus récente est publiée : **Nouvelle version disponible, consultez http://MyPresta.eu pour plus d informations**, avec le lien **Plus de détails dans le journal des modifications**. **Désactiver** masque cet avertissement. |
| **Page du module** | Ouvre la page de l’addon : [Product combination features](https://mypresta.eu/modules/front-office-features/product-combination-features.html) |

Tant qu’un employé est dans le back-office, le module contacte le serveur de mises à jour au plus une fois tous les 3 jours. La vérification a besoin de `allow_url_fopen`. S’il n’est pas disponible, la version installée est conservée et aucune version plus récente n’est signalée.

## 10. Dépannage

**Le bloc de l’onglet Modules est vide sous PrestaShop 8 ou 9.**  
Vérifiez que `modules-content.html.twig` contient `{{ module.content|raw }}` et que la boutique a pu écrire ce fichier. Rouvrez la configuration du module pour que le changement soit retenté. Videz ensuite le cache Symfony (**Paramètres avancés > Performances**).

**La fiche technique ne change pas.**  
Le produit doit avoir des déclinaisons, l’interrupteur des caractéristiques doit être activé ou des caractéristiques doivent déjà être stockées, et la déclinaison doit avoir au moins une valeur (en mode Remplacer, une déclinaison sans valeur restaure les caractéristiques du produit, ce qui peut ressembler à une absence de réaction). Contrôlez le sélecteur dans la console du navigateur : `document.querySelectorAll('.data-sheet')` avec votre sélecteur réel. Le thème doit mettre à jour `data-product` sur `#product-details` et émettre `updatedProduct`.

**Tout le bloc product-details a été remplacé par une courte liste de caractéristiques.**  
Le sélecteur de fiche technique n’a rien trouvé. Réglez-le sur le vrai `<dl>`, en général `.data-sheet`.

**La description ne change pas, ou la description courte a été remplacée par la description longue.**  
Le sélecteur par défaut `#description` est la description longue dans Classic. Le texte de repli est toujours la description longue. Dans **Description de la classe CSS / ID de l objet**, pointez l’élément qui doit changer.

**J’ai coupé les descriptions et l’ancien texte s’affiche encore.**  
Videz les champs, enregistrez le produit, puis coupez l’interrupteur. Ou coupez aussi les caractéristiques pour qu’aucun de ces scripts ne se charge. Couper les caractéristiques et enregistrer efface les caractéristiques de déclinaison stockées.

**J’ai coupé les caractéristiques et elles ont disparu après l’enregistrement du produit.**  
C’est le fonctionnement de l’enregistrement quand les champs de caractéristiques ne sont pas dans le formulaire. Réactivez l’interrupteur avant de modifier le produit si les données sont encore nécessaires. Réimportez le CSV si vous avez le fichier.

**Le titre de l’onglet du navigateur ne change pas.**  
Activez l’interrupteur de titre. Un titre complet vide et un champ Ajouter au titre vide ensemble signifient que le mode par défaut est utilisé. Le mode **Ne pas modifier le titre par défaut** laisse le titre tel quel. Le changement est côté navigateur : ouvrez la page, changez de déclinaison, lisez le titre de l’onglet. La source HTML a toujours le méta titre du produit.

**Une caractéristique manque dans le filtre de catégorie.**  
Activez **Filter combination features in Faceted Search**, ajoutez la caractéristique au modèle de navigation à facettes, et lisez l’avertissement sur la page de configuration du module. Le fichier d’adaptateur doit être inscriptible. La valeur doit être stockée sur le produit ou sur une déclinaison.

**Erreurs de lignes CSV.**

| Message | Cause |
| --- | --- |
| The CSV must contain id_product_attribute or combination_reference | L’en-tête n’identifie pas une déclinaison |
| The CSV must contain feature and value, or id_feature_value | L’en-tête n’identifie pas une valeur de caractéristique |
| Combination was not found | L’ID ou la référence n’existe pas |
| Product ID does not match this combination | `id_product` est rempli et pointe vers un autre produit |
| Product reference does not match this combination | `product_reference` ne correspond pas |
| Combination reference does not match this combination ID | L’ID et la référence sont remplis et se contredisent |
| Combination reference matches more than one combination | Ajoutez `id_product` ou `id_product_attribute` |
| Feature name or value matches more than one | Deux fiches du catalogue partagent ce libellé. Utilisez `id_feature_value` |
| Feature and value are required when id_feature_value is empty | La cellule du nom ou de la valeur est vide |
| The CSV file is larger than 8 MB | Découpez le fichier |

**Plusieurs langues.**  
Les descriptions et les deux champs de titre sont stockés par langue. Les valeurs de caractéristiques utilisent la traduction PrestaShop de la caractéristique dans la langue du visiteur. L’affectation elle-même n’est pas par langue.

## 11. Référence technique

### 11.1 Hooks

| Hook | Quand | Rôle |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Back-office, contrôleurs `AdminProducts` et `AdminModules` | Charge `views/css/combfeat.css`, `views/js/acplt.js`, `views/js/admin-combfeat.js` et l’autocomplétion jQuery. Assure aussi la configuration et l’intégration Faceted Search |
| `displayAdminProductsExtra` | Édition du produit, onglet Modules | Affiche `views/templates/admin/combfeat.tpl` |
| `actionProductUpdate` | Enregistrement du produit | Écrit caractéristiques, descriptions et titres quand `combfeat_submitted` est présent |
| `displayHeader` | Fiche produit, hors ajax | Imprime les données de déclinaison pour la langue courante et ajoute les scripts de la boutique |
| `displayProductAdditionalInfo` | Fiche produit | Affiche le fichier caché `views/templates/hook/product-details.tpl` |

Enregistrés à l’installation : `actionProductUpdate`, `displayProductAdditionalInfo`, `displayAdminProductsExtra`, `actionAdminControllerSetMedia`, `displayHeader`.

La page de configuration répond aussi à la recherche de caractéristiques. Une requête avec `ajax=1` et `q` renvoie les correspondances JSON et s’arrête. L’éditeur produit appelle cette URL via `AdminModules` avec `configure=combfeat`.

### 11.2 Base de données

Le préfixe est celui de la boutique. La désinstallation **ne** supprime **pas** ces tables : le contenu des déclinaisons survit à la désinstallation et est encore là après une installation ultérieure (`CREATE TABLE IF NOT EXISTS`).

`combfeat` — une ligne par valeur de caractéristique sur une déclinaison :

| Colonne | Rôle |
| --- | --- |
| `id_combfeat` | Clé primaire |
| `id_product` | Produit |
| `id_product_attribute` | Déclinaison |
| `id_feature_value` | Valeur de caractéristique du catalogue |
| `active` | `1` quand la ligne est utilisée. La boutique et la vue Faceted Search lisent les lignes actives |

`combfeat_details` — description, une ligne par déclinaison et par langue :

| Colonne | Rôle |
| --- | --- |
| `id_combfeat` | Clé primaire |
| `id_product`, `id_product_attribute`, `id_lang` | Cible |
| `details` | HTML |
| `active` | Enregistré à `1` |

`combfeat_title` — titres, une ligne par déclinaison et par langue :

| Colonne | Rôle |
| --- | --- |
| `id_combfeat` | Clé primaire |
| `id_product`, `id_product_attribute`, `id_lang` | Cible |
| `title_full` | Jusqu’à 512 caractères. Remplace le titre du document |
| `title_append` | Jusqu’à 512 caractères. Ajouté après le titre d’origine |
| `active` | Enregistré à `1` |

`{prefix}combfeat_feature_product` — vue SQL, pas une table de contenu à modifier. Union de `feature_product` et des lignes actives de `combfeat`. La valeur de configuration `COMBFEAT_FEATURE_VIEW` garde la version de la vue (`1`).

Autres clés de configuration : `update_combfeat` et `updatev_combfeat` (vérification des mises à jour), `mypresta_updates` (interrupteur des notifications).

### 11.3 Classes PHP

| Fichier | Classe | Rôle |
| --- | --- | --- |
| `combfeat.php` | `combfeat` | Classe du module : installation, configuration, hooks, données de l’éditeur produit, charge utile boutique |
| `combfeat.php` | `combfeatUpdate` | Comparaison de version et requête vers le serveur de mises à jour |
| `classes/CombfeatImporter.php` | `CombfeatImporter` | Analyse CSV, résolution de la déclinaison et de la caractéristique, téléchargement de l’exemple |
| `classes/CombfeatFacetedSearch.php` | `CombfeatFacetedSearch` | Vue, correctif de l’adaptateur, restauration, vidage du cache des filtres |
| `models/cfeat.php` | `cfeat` | Lignes `combfeat`. `getAllByProductId`, `getFeaturesStaticByIdProduct`, `assign`, `insertDatas`, suppressions |
| `models/cfeatdesc.php` | `cfeatdesc` | Lignes `combfeat_details` |
| `models/cfeattitle.php` | `cfeattitle` | Lignes `combfeat_title`. `saveTitleRow` supprime la ligne quand les deux titres sont vides |

Il n’y a pas de répertoire `controllers/`.

### 11.4 Ressources et modèles

| Fichier | Où | Rôle |
| --- | --- | --- |
| `views/js/acplt.js` | Back-office | Autocomplétion de la recherche de caractéristiques |
| `views/js/admin-combfeat.js` | Back-office | Accordéon, filtre, onglets, drapeaux de langue, jetons, rafraîchissement TinyMCE, copie du contenu de l’éditeur avant l’enregistrement du produit |
| `views/css/combfeat.css` | Back-office seulement | Mise en page de **Contenu de la déclinaison** |
| `views/js/combfeat.js` | Boutique, mode Remplacer | Reconstruit la fiche technique et la description |
| `views/js/combfeat-append.js` | Boutique, mode Ajouter | Identique, avec les caractéristiques du produit avant celles de la déclinaison |
| `views/js/combfeat-title.js` | Boutique | `document.title` et `og:title` |
| `views/templates/admin/combfeat.tpl` | Onglet Modules du produit | L’éditeur |
| `views/templates/hook/product-details.tpl` | Fiche produit | `#product-details-combfeat` caché, avec `data-product` |
| `import/combfeat-features-sample.csv` | Téléchargement depuis la configuration | Exemple d’import |

### 11.5 Installation et désinstallation

L’installation crée les trois tables, écrit la configuration par défaut, enregistre les cinq hooks, applique le changement Twig et applique l’intégration Faceted Search.

`disable` restaure l’adaptateur de la navigation à facettes. `enable` écrit les clés de configuration manquantes et réapplique l’intégration quand l’interrupteur Faceted Search est activé.

La désinstallation restaure l’adaptateur, supprime la vue quand elle n’est plus référencée, et désinstalle le module. Les lignes de déclinaison des trois tables restent dans la base.

## 12. Assistance

Journal des modifications et mises à jour : [Product combination features sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-combination-features.html).

Commandes et assistance : [compte client MyPresta.eu](https://mypresta.eu/my-account/orders/). E-mail : support@mypresta.eu.
