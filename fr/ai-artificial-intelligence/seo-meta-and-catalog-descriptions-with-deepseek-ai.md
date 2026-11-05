---
title: "My AI DeepSeek - AI content generation - documentation et manuel d'utilisation"
description: "Manuel de configuration, d'utilisation quotidienne et de dépannage pour les propriétaires de boutique qui ont déjà installé le module My AI DeepSeek dans PrestaShop."
sidebar:
  label: "My AI DeepSeek - AI content generation - documentation et manuel d'utilisation"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module SEO meta and catalog descriptions with DeepSeek AI sur MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-deepseek-ai.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-deepseek-ai/)
>
> ---


## 1. Prérequis

Le module rédige les textes du catalogue via le service DeepSeek. Votre boutique a donc besoin d'une connexion fonctionnelle à DeepSeek et de votre propre compte DeepSeek.

- **PrestaShop :** versions 1.6 à 9.99.99.
- **PHP :** 7.0 ou plus récent. Avec une version de PHP plus ancienne, l'installation est refusée avec un message indiquant la version requise et la version détectée.
- **Extension PHP :** cURL. Le serveur de la boutique doit pouvoir ouvrir des connexions HTTPS sortantes vers `https://api.deepseek.com/v1`. Si votre hébergeur bloque les connexions sortantes, demandez-lui de les autoriser.
- **Autres modules :** aucun. Le module ne dépend d'aucun autre module.
- **Compte DeepSeek :** vous avez besoin d'une clé d'API. Créez-la sur https://platform.deepseek.com/api_keys. L'utilisation est facturée par DeepSeek sur votre compte, et non par MyPresta.eu.
- **Langue du back-office :** dans ce manuel, les écrans sont présentés en anglais et les captures d'écran proviennent du back-office en anglais. Les noms en gras sont les noms que vous voyez à l'écran.
- **Gros catalogues :** chaque champ généré correspond à une requête vers DeepSeek et prend quelques secondes. Un traitement portant sur des centaines de produits prend beaucoup de temps, et l'onglet du navigateur doit rester ouvert pendant tout le traitement sur les écrans Generate. Pour les gros catalogues, privilégiez l'écran Cron, qui travaille en arrière-plan par petits lots.

## 2. Installation

### 2.1 Téléverser et installer

1. Ouvrez **Modules**, puis **Module Manager**.
2. Cliquez sur **Upload a module** et sélectionnez le fichier ZIP. Ne le décompressez pas au préalable.
3. Lorsque le téléversement est terminé, cliquez sur **Install** (si le bouton est affiché), puis sur **Configure**.

L'installation enregistre les réglages par défaut, crée les tables du module, ajoute 16 modèles de prompt prêts à l'emploi et ajoute le module au menu du back-office.

### 2.2 Ce qui apparaît dans le menu

Une nouvelle entrée de menu **AI Content Generator** est ajoutée. Sa première page est **Dashboard**. À l'intérieur du module, vous passez d'un écran à l'autre grâce à la barre de navigation située en haut de chaque page :

| Élément de navigation | Ce qu'il ouvre |
|---|---|
| **Dashboard** | Graphiques des requêtes, des erreurs et des tokens. |
| **Settings** | Cinq sections : **General**, **DeepSeek**, **Studio**, **Prompt templates**, **Playground**. |
| **Generate** | Deux listes : **Products** et **Categories**. |
| **New product** | Crée un brouillon de produit à partir d'un bref descriptif. |
| **Cron** | Construit les adresses des tâches planifiées pour les produits et les catégories. |
| **History** | Chaque requête avec son prompt, sa réponse, son statut et ses tokens. |
| **Images** | Interrupteur et prompt de la recherche de photos de produit. |
| **Updates** | Vérifie si une version plus récente est publiée. |

Le survol d'un élément de navigation affiche une courte aide sous la forme What it does / How to configure / Effect.

### 2.3 Cache

L'installation ne vide pas le cache de PrestaShop. Si l'entrée **AI Content Generator** manque dans le menu après la première installation, videz le cache dans **Advanced Parameters**, **Performance** et rechargez le back-office.

### 2.4 Désinstallation et réinstallation

- **Supprimé :** l'entrée de menu, la liste des modèles de prompt, la table History avec toutes ses lignes et les réglages principaux du module, y compris la clé d'API.
- **Conservé :** tout texte déjà écrit dans les produits et les catégories. Le module ne supprime jamais les textes du catalogue.
- **Restes possibles :** quelques valeurs de filtre enregistrées des écrans Generate peuvent subsister dans la configuration de la boutique. Elles ne gênent en rien.
- **Réinstallation :** une nouvelle installation repart des valeurs par défaut. Les modèles de prompt, History et la clé d'API disparaissent. Notez donc vos propres modèles et vos règles Studio avant de désinstaller.

## 3. Configuration et travail quotidien dans le back-office

### 3.1 Tout le processus en un coup d'œil

Le module n'a aucune étape côté client. Vos collaborateurs lancent chaque action dans le back-office.

1. **Une seule fois :** collez la clé d'API DeepSeek et choisissez un modèle dans **Settings**, **DeepSeek**. Renseignez éventuellement **Studio** (voix de marque, mots interdits, limite mensuelle).
2. **Un seul produit :** ouvrez un produit, allez dans l'onglet **Modules**, **My AI DeepSeek**. Utilisez **Generate** pour rédiger des champs, **Simulate** pour essayer d'abord, **Photos** pour trouver des images et **History** pour restaurer un ancien texte.
3. **Plusieurs produits ou catégories :** ouvrez **Generate**, filtrez la liste, choisissez un prompt et une portée, puis appuyez sur **Run**. Chaque ligne affiche son propre résultat lorsqu'elle est terminée.
4. **Sans surveillance :** ouvrez **Cron**, enregistrez une définition de lot, copiez l'adresse et donnez-la au planificateur de tâches du serveur.
5. **Contrôle :** **History** affiche chaque requête. **Dashboard** affiche les totaux. Rien n'est perdu : le texte précédent de chaque champ écrit est conservé pour **Restore** sur le produit.
6. **Nouveau produit à partir d'une idée :** **New product** crée un brouillon puis, une fois que vous l'avez accepté, un vrai produit.

Chaque requête est enregistrée dans **History** avec son statut **Success** ou **Error**. Une réponse qui enfreint la liste **Forbidden words**, ou qui arrive après l'épuisement du **Monthly generation budget**, n'est pas écrite dans le produit.

![Dashboard](https://mypresta.eu/docs/images/docs/myaideepseek-dashboard.webp)

### 3.2 Dashboard

Ouvrez **AI Content Generator**, puis **Dashboard**. La page représente sous forme de graphiques les requêtes DeepSeek, les tokens et les erreurs enregistrés dans **History** pour la période choisie. Depuis cette page, rien n'est généré ni modifié dans le catalogue.

| Élément | Valeur de départ | Ce qu'il fait |
|---|---|---|
| **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time** | le module s'ouvre avec une période par défaut | Périodes rapides. Cliquez sur l'une d'elles pour redessiner la page. |
| **From** / **To** et **Apply** | vide | Votre propre période. Les cartes et les graphiques la suivent. |
| Ligne **Active service** | – | Indique quel service le module utilise. |
| Cartes **Requests**, **Errors**, **Tokens sent**, **Tokens received** | – | Nombre d'appels enregistrés, d'appels en échec, taille des prompts et taille des réponses sur la période. |
| Graphiques **Requests and errors**, **Tokens sent and received**, **Requests by model** | – | Courbes jour par jour et répartition par modèle. |

La page apparaît aussi sous la forme d'un petit bloc sur le **Dashboard** standard de PrestaShop, avec des liens rapides vers **Generate**, **History** et **Cron**.

### 3.3 Settings – General

Ouvrez **Settings**, puis **General**. Ces interrupteurs décident de la durée maximale d'un appel et des outils que voient vos collaborateurs. L'enregistrement ici ne modifie aucun texte de produit.

![Settings – General](https://mypresta.eu/docs/images/docs/myaideepseek-settings-general.webp)

| Champ | Valeur de départ | Ce qu'il fait |
|---|---|---|
| **Live mode** | Disabled | Indique que le module fonctionne sur la vraie boutique et non sur une configuration d'essai. Activez-le sur la boutique de production. Sur une copie de préproduction (staging), laissez-le désactivé si vous ne voulez pas que le personnel considère les outils comme prêts. Les outils fonctionnent de la même façon dans les deux états. |
| **Debug mode** | Disabled | Écrit des détails de diagnostic supplémentaires lorsqu'un appel à DeepSeek échoue. Activez-le uniquement pendant que vous analysez une erreur, puis désactivez-le. Les messages techniques vont dans le journal de PrestaShop. Les clients ne les voient jamais. |
| **API timeout (seconds)** | 120 | Nombre de secondes pendant lesquelles un appel à DeepSeek peut durer avant que le module abandonne. Utilisez 120 pour des descriptions normales. Augmentez vers 600 pour de longs packs SEO ou pour le modèle de raisonnement. Ne descendez pas sous 10. Un délai court échoue vite et écrit une erreur dans History. Un délai long attend une réponse lente. |
| **Product Edit History** | Enabled | Affiche les écritures précédentes de l'IA sur la page du produit afin qu'un rédacteur puisse remettre une ancienne valeur. Désactivé masque cette liste. Les anciennes lignes restent dans **History** dans les deux cas. |
| **Admin Top Bar CTA** | Enabled | Ajoute un raccourci dans la barre supérieure du back-office qui ouvre le générateur sur chaque page. Désactivé supprime uniquement ce bouton. Le menu du module reste. |
| **Product edit page Form** | Enabled | Affiche le panneau du générateur et les boutons Generate with AI sur la page d'édition du produit (PrestaShop 1.7, 8 et 9). Désactivez-le si seuls la génération en masse et le cron doivent être utilisés. |
| **AI Image Finder** | Enabled | Permet à un rédacteur de demander au modèle des pages contenant probablement des photos du produit en cours. Rien n'est téléchargé tant que quelqu'un n'a pas confirmé une image. Désactivé masque la recherche, et l'onglet **Photos** explique alors comment l'activer. |
| **AI Image Search Prompt** | instruction anglaise prête à l'emploi | L'instruction envoyée lorsque quelqu'un recherche des images de produit. Le nom du produit et la description du produit sont renseignés pour le produit en cours. Conservez la demande d'une liste d'adresses de pages. Un prompt plus précis donne des pages plus pertinentes. |

Appuyez sur **Save**. Une confirmation verte apparaît. Les deux mêmes champs d'image existent dans **Images**.

### 3.4 Settings – DeepSeek

Ouvrez **Settings**, puis **DeepSeek**. Il s'agit du compte et de l'échantillonnage utilisés par chaque génération : les boutons du produit, les traitements en masse, le cron et le playground.

![Settings – DeepSeek](https://mypresta.eu/docs/images/docs/myaideepseek-settings-deepseek.webp)

| Champ | Valeur de départ | Ce qu'il fait |
|---|---|---|
| **DeepSeek API KEY** | vide | Le secret qui permet à cette boutique d'appeler votre compte DeepSeek. Collez la clé depuis https://platform.deepseek.com/api_keys. Les espaces sont supprimés à l'enregistrement (vous voyez une note indiquant que la clé a été nettoyée). Laissez le champ intact pour conserver la clé enregistrée. Une clé vide ou erronée fait échouer les appels et l'erreur est écrite dans History. |
| **Model** | `deepseek-chat` | Le modèle qui rédige le texte. Modèles intégrés : `deepseek-chat` (rapide, le choix normal) et `deepseek-reasoner` (modèle de raisonnement, plus lent). Les modèles que vous ajoutez vous-même sont également affichés. La génération suivante utilise le modèle sélectionné. Un modèle que votre clé ne peut pas utiliser renvoie une erreur d'API au lieu d'un texte. |
| **Add a DeepSeek model** | ligne vide | Saisissez un identifiant de modèle et appuyez sur le bouton d'ajout de cette ligne. Vous voyez **Model added.** Les modèles intégrés ne peuvent pas être supprimés (**Built-in models cannot be removed.**). Un modèle déjà intégré répond **That model is already built in.** Les modèles que vous avez ajoutés peuvent être supprimés depuis la même ligne (**Model removed.**). |
| **Max Tokens** | 3200 | Limite supérieure de la longueur de la réponse, comptée en tokens et non en mots. Utilisez environ 256 pour une meta description et 1000 ou plus pour une description HTML complète. Une limite basse coupe la réponse. Une limite élevée autorise un texte plus long et coûte plus cher. Avec `deepseek-reasoner`, une partie de la limite est consommée par le raisonnement ; donnez-lui donc une valeur plus grande. |
| **Temperature** | 0.7 | Avec quelle liberté le modèle choisit les mots. Restez entre 0 et 1. Utilisez environ 0.2 pour les spécifications et les textes meta, et environ 0.7 pour les descriptions. Modifiez Temperature ou Top P, pas les deux. |
| **Top P** | 1 | Une autre façon de limiter le caractère surprenant du mot suivant. Laissez 1 si vous avez déjà réglé Temperature. Une valeur plus basse, comme 0.9, donne un vocabulaire plus resserré. |
| **Frequency Penalty Value** | 0 | Réduit les lignes qui répètent la même formulation dans une même réponse. Essayez 0.3 à 0.6 uniquement si les descriptions recopient sans cesse la même phrase. Plage –2 à 2. |
| **Presence Penalty Value** | 0 | Pousse la réponse vers de nouveaux sujets. Utilisez 0 par défaut. Un petit nombre positif aide lorsque chaque paragraphe répète le même point. Plage –2 à 2. |

Appuyez sur **Save**. Les champs d'échantillonnage ne changent pas les produits mis à jour.

> Le modèle de raisonnement peut ignorer Temperature, Top P et les deux pénalités. Si une modification de ces champs n'a aucun effet visible avec `deepseek-reasoner`, passez à `deepseek-chat`.

### 3.5 Settings – Studio

Ouvrez **Settings**, puis **Studio**. Studio ajoute vos règles maison par-dessus chaque prompt : les boutons du produit, les traitements en masse et le cron. Les champs vides sont ignorés. Le texte déjà enregistré dans le catalogue n'est pas réécrit lorsque vous modifiez une règle.

![Settings – Studio](https://mypresta.eu/docs/images/docs/myaideepseek-settings-studio.webp)

| Champ | Valeur de départ | Ce qu'il fait |
|---|---|---|
| **Brand voice** | vide | Indique au modèle qui parle, afin que le texte du produit corresponde à votre boutique et non à un assistant générique. Rédigez un court brief, par exemple : atelier spécialisé, phrases courtes, pas de surenchère. |
| **Audience** | vide | Désigne le lecteur auquel le texte s'adresse, par exemple des installateurs professionnels ou des primo-acheteurs. |
| **Tone** | vide | Définit l'ambiance : formel, chaleureux, technique, etc. Un ou deux mots suffisent. Cela ne change ni le modèle ni la température. |
| **Glossary** | vide | Noms de marque, matériaux et graphies que le modèle doit recopier exactement. Un terme par ligne. Les termes non listés peuvent encore être reformulés. |
| **Forbidden words** | vide | Mots et expressions qui ne doivent pas apparaître dans une réponse enregistrée. Un par ligne. Utilisé uniquement lorsque **Quality gate** est activé. Une réponse qui contient une ligne de la liste est rejetée et n'est pas écrite dans le produit. La tentative reste dans History comme erreur. |
| **Monthly generation budget** | 0 | Plafonne le nombre de générations réussies que la boutique peut effectuer pendant le mois calendaire en cours. Saisissez un nombre entier. 0 signifie aucune limite. Le compteur repart le premier jour du mois. Après le plafond, vous voyez **Monthly generation budget reached. Raise it in the studio settings or wait until next month.** Les appels en échec ne sont pas comptés. |
| **Quality gate** | Enabled | Vérifie la réponse du modèle par rapport à **Forbidden words** avant d'enregistrer quoi que ce soit. Activé bloque une réponse correspondante. Désactivé l'enregistre même si elle contient un mot listé. |

Appuyez sur **Save studio**. Vous voyez **Studio settings saved.**

### 3.6 Settings – Prompt templates

Ouvrez **Settings**, puis **Prompt templates**. Un modèle est une instruction enregistrée. Les rédacteurs le choisissent au lieu de retaper le même brief. Seuls les modèles activés sont proposés sur la page du produit, dans la génération en masse et dans le cron.

![Settings – Prompt templates](https://mypresta.eu/docs/images/docs/myaideepseek-settings-templates.webp)

L'installation ajoute **16 modèles** : Product name 1 et 2 ; Product description 1 à 7 (le numéro 7 utilise les images du produit) ; Product meta title 1 à 3 ; Product meta description 1 à 3 ; Product tags.

**Colonnes de la liste :** ID, **Title**, **Prompt**, **Status** (cliquez sur la coche pour basculer Enabled/Disabled), **Timestamp**. Actions de ligne : **Edit** et **Delete**. Action groupée : **Delete** pour les lignes cochées (confirmation : *Are you sure you want to delete the selected prompts?*).

Utilisez le bouton **+** dans l'en-tête de la liste pour créer un modèle. Le formulaire **Generate Prompt Template** comporte ces champs :

| Champ | Valeur de départ | Ce qu'il fait |
|---|---|---|
| **Status** | interrupteur Enabled / Disabled | Affiche ou masque le modèle dans les listes utilisées sur la page du produit, dans la génération en masse et dans le cron. Désactivez un brouillon au lieu de le supprimer. |
| **Prompt title** | vide (obligatoire) | Le nom que les rédacteurs voient dans la liste des modèles, par exemple HTML description with features. Il n'est pas envoyé au modèle. |
| **Prompt content** | vide (obligatoire) | L'instruction envoyée au modèle. Rédigez-la comme si vous briefiez un rédacteur et mentionnez la longueur, le HTML et la langue s'ils comptent. Vous pouvez utiliser les marqueurs `{product_name}`, `{product_brand}`, `{product_features}` et `{product_tags}`. Ils sont remplacés par le produit pour lequel vous générez. |

Appuyez sur **Save Prompt**. Messages : **Prompt template successfully added!**, **Prompt template successfully updated!**, **Prompt template removed.** Si le formulaire est incomplet, vous voyez **Failed to edit prompt template! Please fill the form with the right informations!** Le bouton **Go Back to Module Settings** revient à la liste.

Rédigez les modèles de catégorie sans marqueurs de produit. Les écrans de catégories ne les insèrent pas.

### 3.7 Settings – Playground

Ouvrez **Settings**, puis **Playground**. C'est un bloc-notes qui appelle le modèle actif et affiche la réponse sous le bouton. Aucun produit, catégorie ou champ meta n'est modifié.

![Settings – Playground](https://mypresta.eu/docs/images/docs/myaideepseek-settings-playground.webp)

| Champ | Valeur de départ | Ce qu'il fait |
|---|---|---|
| Grande zone de texte (**Ask the model anything about your catalog**) | vide | L'instruction pour cet unique appel. Rédigez-la en langage simple. Vous pouvez mentionner le nom de la boutique, l'adresse de la boutique, un nom de produit, une référence ou des caractéristiques du produit si vous voulez que la réponse s'appuie sur les données du catalogue. Vos règles Studio sont également ajoutées. |
| **Generate** | – | Envoie l'instruction. La réponse apparaît sous le bouton. |

### 3.8 Generate – Products

Ouvrez **Generate**, puis **Products**. C'est un écran en deux étapes. La première étape construit seulement une liste. Rien n'est envoyé à DeepSeek avant que vous n'appuyiez sur **Run** à la seconde étape.

![Generate – Products](https://mypresta.eu/docs/images/docs/myaideepseek-generate-products.webp)

**Étape 1 – Filter products to update.** Les filtres ne sont pas enregistrés comme réglages de la boutique. Les filtres vides ne restreignent pas la liste.

| Champ | Valeur de départ | Ce qu'il fait |
|---|---|---|
| **Product Categories** | aucune cochée | Conserve les produits des catégories cochées. Un arbre vide désactive ce filtre. |
| **Brand** | première option (vide) | Conserve les produits d'un seul fabricant. |
| **Product status** | – | **Active** (en vente), **Disabled** (brouillons) ou **Both**. |
| **Product stock** | – | **Only in stock products** retire les produits sans quantité. **All products** ignore le stock. |
| **Update only** | – | Utilise l'historique de génération : produits jamais écrits par ce module, produits déjà écrits ou **Update all**. Utilisez "not yet updated" pour un premier passage et "already updated" pour réécrire. |
| **Product IDs** | vide | Numéros de produit séparés par des virgules, par exemple 12,45,103. |
| **Product Reference** | vide | Un ou plusieurs codes de référence séparés par des virgules. |
| **Product Add Date From** / **Product Add Date To** | vide | Période de date de création. Vide signifie aucune limite de ce côté. |
| **Minimum product ID** / **Maximum product ID** | vide | Plus petit et plus grand numéro de produit à inclure. |
| **Product Limit** | vide | Plafonne le nombre de produits chargés dans la liste. Sur un gros catalogue, utilisez un petit nombre comme 20 afin qu'un traitement ne parcoure pas par accident tout le catalogue. |

Appuyez sur **Go to next step**. Le bouton **Module settings** revient aux réglages du module.

**Étape 2 – Run.** Vous voyez **Mass product generation** avec le tableau des produits filtrés (colonnes **ID**, **Reference**, **Result**).

| Champ | Valeur de départ | Ce qu'il fait |
|---|---|---|
| **Template** | **Choose a template** | Remplit la zone de prompt à partir d'un modèle activé. Laissez la première option et saisissez votre propre prompt si vous préférez. Le titre lui-même n'est pas envoyé. |
| Zone de prompt | vide | Le texte envoyé pour chaque ligne. Les marqueurs de produit sont remplacés ligne par ligne. |
| **What to generate** | **Descriptions** | **Descriptions** rédige la description longue et la description courte. **Meta title and meta description** rédige les deux champs meta. **Descriptions and meta together** rédige les quatre. Chaque champ est une requête distincte. Les autres champs restent inchangés. |
| **Existing text** | **Replace** | **Replace** écrase. **Skip if filled** conserve les champs remplis et n'appelle pas DeepSeek pour eux. **Add above** et **Add below** conservent l'ancien texte et y joignent le nouveau. |
| **Languages** | la langue de votre back-office, cochée | Cochez chaque langue souhaitée. Les langues non cochées conservent leur texte. Chaque langue cochée est générée séparément. |
| **Run on the list below** | – | Lance le traitement. Chaque ligne affiche son résultat dès que ce produit est terminé. Les produits hors du filtre ne sont pas touchés. |

Gardez l'onglet du navigateur ouvert jusqu'à ce que chaque ligne affiche un résultat. Une ligne en échec indique la raison ; les autres lignes continuent.

### 3.9 Generate – Categories

Ouvrez **Generate**, puis **Categories**. Il fonctionne comme l'écran des produits, avec moins de filtres.

![Generate – Categories](https://mypresta.eu/docs/images/docs/myaideepseek-generate-categories.webp)

**Étape 1 – Filter categories to update.**

| Champ | Valeur de départ | Ce qu'il fait |
|---|---|---|
| **Categories** | aucune cochée | Les catégories proposées dans la liste. Laissez l'arbre vide pour inclure toutes les catégories correspondant au statut. |
| **Category status** | – | **Active**, **Disabled** ou **Both**. |

Appuyez sur **Go to next step**.

**Étape 2 – Mass category generation.**

| Champ | Valeur de départ | Ce qu'il fait |
|---|---|---|
| Zone de prompt | vide | L'instruction envoyée pour chaque catégorie. Décrivez le ton, la longueur et le HTML. Les marqueurs de produit ne sont pas disponibles ici. |
| Sélecteur de champ | **Description** | Le seul champ écrit par ce traitement : **Description**, **Name**, **Meta title**, **Meta description** ou **Additional description**. |
| Existing data | **Replace** | **Replace** écrase. **Skip if filled** protège les champs remplis et n'appelle pas DeepSeek pour cette catégorie. |
| **Language** | la langue de votre back-office | Une langue par traitement. Relancez pour une autre langue. |
| **Run on the categories below** | – | Lance le traitement. Le tableau affiche **ID** et **Result** pour chaque catégorie. |

### 3.10 New product

Ouvrez **New product**. Cet écran transforme un bref descriptif en brouillon de produit et peut insérer ce produit dans le catalogue.

![New product](https://mypresta.eu/docs/images/docs/myaideepseek-new-product.webp)

| Champ | Valeur de départ | Ce qu'il fait |
|---|---|---|
| **What is the product?** | vide | Le descriptif que le modèle développe en nom, descriptions, champs meta, tags, caractéristiques, référence et prix. Quelques phrases avec les matériaux, le public et les noms à conserver donnent un brouillon plus proche. Une zone vide est refusée. |
| **Optional source URL** | vide | Une page publique (http ou https) qui décrit le produit. Son texte est ajouté comme contexte. Une zone vide, ou une page que la boutique ne peut pas lire, est ignorée. |
| **Language** | la langue de votre back-office | La langue dans laquelle le nom, les descriptions, les meta et les tags sont enregistrés. Les autres langues ne sont pas renseignées ici. |
| **Default category ID** | 2 | Le numéro de la catégorie de **Catalog**, **Categories**. 2 correspond généralement à Home. Le nouveau produit y est placé. |
| **Generate data** | – | Affiche le brouillon sous forme de texte. Aucun produit n'est enregistré. |
| **Create product** | – | Ajoute un produit **actif** dans cette langue et cette catégorie avec le nom, les descriptions, les meta, les tags, les caractéristiques, le prix et une quantité en stock issus du brouillon. |

Si aucune clé n'est enregistrée, vous voyez **Add an API key in the module settings first.** Relisez le brouillon, le prix et le stock avant de vendre : le brouillon est rédigé par un modèle.

### 3.11 Cron

Ouvrez **Cron**. La page construit des adresses que le planificateur du serveur appelle. Chaque appel remplit **un lot** et s'arrête. La boutique ne fait rien tant que votre serveur ne demande pas l'adresse.

![Cron](https://mypresta.eu/docs/images/docs/myaideepseek-cron.webp)

La page comporte deux formulaires : **CRON JOB Settings – Generate product content using DeepSeek** et le formulaire équivalent pour les catégories. Vous pouvez créer un nombre illimité de variantes de commande, une par champ.

**Formulaire de cron des produits**

| Champ | Valeur de départ | Ce qu'il fait |
|---|---|---|
| **Enable Cron Feature** | No | Un seul interrupteur pour toute la boutique (produits et catégories). Activez-le seulement après avoir enregistré le secret, le champ, la langue et le prompt ci-dessous. Le serveur doit encore appeler l'adresse. |
| **Cron Job Secret Token** | généré | Un long mot de passe qui doit faire partie de l'adresse des produits. Sans lui, la boutique refuse l'appel. Conservez la valeur affichée après l'installation. Si vous la remplacez, copiez aussitôt la nouvelle adresse dans le planificateur du serveur. Le bouton **Generate Token** du formulaire peut ne pas remplir de nouvelle valeur ; saisissez vous-même une longue chaîne aléatoire si vous devez la renouveler. |
| **Update Field** | description | Le seul champ de produit que cette commande réécrit : name, description, short description, meta title, meta description ou tags. Pour remplir plusieurs champs, créez plusieurs commandes. |
| **Selected Products** | pendingDeepSeek | Quels produits attendent encore. **pendingDeepSeek** : produits jamais édités par ce module (n'importe quel champ). **pendingField** : produits pour lesquels ce champ n'a pas encore été généré, pour plusieurs commandes sur les mêmes produits. **emptyField** : uniquement les produits dont le champ est vide. |
| **Product Categories** | aucune cochée | Limite le traitement aux catégories cochées. Vide signifie que la catégorie n'est pas un filtre. |
| **Product ID list** | vide | Uniquement ces numéros de produit, séparés par des virgules. Les lettres sont supprimées à l'enregistrement. |
| **Language** | langue par défaut de la boutique | Une langue par commande. Les autres langues nécessitent leur propre commande. |
| **Product to update** | 5 products | Taille du lot par appel, de 2 à 1000. Commencez avec 5 ou 10 afin qu'un modèle lent n'atteigne pas la limite de temps du serveur. |
| **Prompt Template** | none | Un modèle activé. Chaque produit du traitement est rédigé à partir de ce brief. |
| **Enable Debug** | No | **Yes** affiche le plan lorsque vous ouvrez l'adresse dans un navigateur et n'enregistre rien. Réglez sur **No** avant que le planificateur ne l'utilise. |
| **CRON JOB interval** | Every Hour | Simple suggestion utilisée pour construire le texte de la commande (de **Every 1 Minute** à **Every 6 Hours**). Le module ne démarre pas de planificateur. |
| **Product Cron Job command** | – | La commande terminée à copier. Enregistrez d'abord le formulaire. |

Le **formulaire de cron des catégories** a son propre **Cron Job Secret Token**, **Update Field** (name, description, meta title, meta description), **Selected categories** (les mêmes trois règles), **Language**, **Categories to update** (taille du lot), **Prompt Template** (rédigez le brief pour une catégorie), **Enable Debug**, **CRON JOB interval** et **Category Cron Job command**. Valeurs par défaut : description, pendingDeepSeek, 5 categories, Every Hour.

**Complétez l'adresse.** L'adresse affichée sur la page peut être incomplète. Vérifiez toujours que l'adresse finale contient l'action. Utilisez cette forme en remplaçant les marqueurs :

```text
https://YOUR-SHOP-DOMAIN/module/myaideepseek/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent&updatedField=description&productTarget=pendingDeepSeek&productsToUpdate=5&languageId=1&promptTemplateId=TEMPLATE_ID
https://YOUR-SHOP-DOMAIN/module/myaideepseek/cron?secret=YOUR_CATEGORY_SECRET&action=generateCategoryContent&updatedField=description&categoryTarget=pendingDeepSeek&categoriesToUpdate=5&languageId=1&promptTemplateId=TEMPLATE_ID
```

Utilisez `&action=generateProductContent` pour les produits et `&action=generateCategoryContent` pour les catégories. Sans cela, l'appel ne fait rien. Si votre boutique n'utilise pas les URL simplifiées, copiez l'adresse de base de la page et ajoutez les éléments avec `&`. Ne publiez pas ces adresses : le secret qu'elles contiennent est la seule protection.

Premier test recommandé : réglez **Enable Debug** sur **Yes**, ouvrez l'adresse dans votre navigateur et lisez le plan. Réglez ensuite sur **No**, planifiez l'adresse et vérifiez **History** après le premier appel.

### 3.12 History

Ouvrez **History**. Elle liste chaque prompt, réponse, statut et nombre de tokens. La page est un rapport : la filtrer ne supprime aucune ligne et ne modifie aucun produit.

![History](https://mypresta.eu/docs/images/docs/myaideepseek-history.webp)

| Élément | Ce qu'il fait |
|---|---|
| **7 days**, **30 days**, **This month**, **All time** | Périodes prédéfinies. |
| **From** / **To** | Période personnalisée. |
| **Model**, **Type**, **Status** (**Success** ou **Error**), **Language**, **Employee** | Restreignent la page à une tranche. |
| **Product / category ID** | Uniquement les requêtes concernant cet élément. |
| **Prompt or reply contains** | Un mot qui doit apparaître dans le prompt ou dans la réponse. |
| **Filter** | Applique les filtres. |
| Cartes **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** | Totaux des lignes filtrées. Un tiret signifie que DeepSeek n'a pas renvoyé de nombre de tokens pour cet appel. |
| Groupes **By day**, **By model**, **By type**, **By language**, **By employee** | Tableaux de répartition. |
| Colonnes de la liste **Status**, **Prompt**, **Reply / Error**, **Provider**, **Received**, **Entity ID**, **Timestamp** | Une ligne par requête. Ouvrez une ligne pour lire le prompt et la réponse complets ainsi que les tokens. **Back to the list** revient en arrière. |
| **Clear list** | Supprime les lignes de l'historique. Vous voyez **Log list successfully deleted.** Les points **Restore** de la page du produit disparaissent avec elles. Le texte du catalogue n'est pas modifié. |

### 3.13 Images

Ouvrez **Images**. Elle enregistre l'interrupteur et l'instruction de la recherche de photos de produit. L'ouverture de cette page ne télécharge rien.

![Images](https://mypresta.eu/docs/images/docs/myaideepseek-images.webp)

| Champ | Valeur de départ | Ce qu'il fait |
|---|---|---|
| **AI Image Finder** | Enabled | Affiche ou masque la recherche de photos sur la page d'édition du produit. Une image n'est importée qu'après confirmation par quelqu'un. |
| **AI Image Search Prompt** | instruction anglaise prête à l'emploi | L'instruction envoyée lors d'une recherche. Le nom du produit et la description courte sont renseignés. Conservez la demande d'une simple liste d'adresses de pages. |

Appuyez sur **Save**. Ce sont les deux mêmes réglages que dans **Settings**, **General**.

### 3.14 Updates

Ouvrez **Updates**. Elle demande à MyPresta.eu si une version plus récente de ce module est publiée.

![Updates](https://mypresta.eu/docs/images/docs/myaideepseek-updates.webp)

| Élément | Valeur de départ | Ce qu'il fait |
|---|---|---|
| **Automatic Notifications** | suit le réglage enregistré | Permet au back-office de vous avertir lorsqu'une version plus récente existe. |
| **Check Now** | – | Interroge une fois, immédiatement. La page indique ensuite que cette copie est à jour ou qu'une version plus récente existe. |
| Lien vers la page du module | – | Ouvre la page du module sur MyPresta.eu. |

Votre catalogue et les textes générés ne sont pas touchés par cette page.

### 3.15 La page d'édition du produit

Ouvrez **Catalog**, puis **Products**, modifiez un produit et ouvrez l'onglet **Modules**, puis **My AI DeepSeek**. Selon votre version de PrestaShop et les réglages de **General**, vous pouvez aussi voir de petits boutons **Generate with AI** à côté de la description, de la description courte et des champs meta.

![Product edit](https://mypresta.eu/docs/images/docs/myaideepseek-product-edit.webp)

L'onglet comporte quatre parties : **Generate**, **Simulate**, **Photos** et **History**. Si **Product edit page Form** est désactivé, seul **History** reste (lorsque **Product Edit History** est activé).

**Generate** – chaque bouton rédige un champ et enregistre le texte sur le produit.

| Commande | Ce qu'elle fait |
|---|---|
| Boutons **Language** | Choisissent une langue de la boutique. **Every language** les rédige toutes. |
| **If the field already has text** | **Replace** (par défaut), **Add above**, **Add below** ou **Skip if filled**. |
| **Description** | Le texte long, avec une courte introduction et une liste de caractéristiques. |
| **Short description** | Un court résumé simple, de moins d'environ 400 caractères. |
| **Name** | Le titre du produit que voient les clients. |
| **Meta title** | Le titre dans les résultats de recherche, environ 70 caractères. |
| **Meta description** | Le texte dans les résultats de recherche, environ 160 caractères. |
| **Tags** | Une liste de mots séparés par des virgules. |
| **SEO pack** – **Fill all** | Rédige le nom, les deux descriptions et les deux champs meta en une seule fois. Si la réponse est inutilisable, vous voyez **The model did not return a usable SEO pack.** |
| **Fill** | Apparaît sur chaque carte de champ : génère et enregistre ce champ. |
| **Use your own instruction or a saved prompt** | Ouvre une zone de filtre, des vignettes avec les modèles activés (**Standard brief** est celui par défaut) et une zone **Instruction**. Laissez la zone vide pour utiliser le brief standard du champ sur lequel vous appuyez. |

**Simulate** – les mêmes cartes de champ avec un bouton **Try**. La réponse s'affiche sur cette page et le produit n'est **pas** modifié. Utilisez-le pour tester un prompt, puis revenez à **Generate**.

**Photos** – voir la section 3.16.

**History** – le tableau **When**, **Type**, **Status** et un bouton **Restore**. **Restore** remet sur le produit le texte précédent de cette écriture. Les lignes sans valeur précédente, ou en erreur, n'ont pas de bouton. Le rapport **History** de toute la boutique n'est pas supprimé. Une liste vide indique **No generations for this product yet.**

![Product photos](https://mypresta.eu/docs/images/docs/myaideepseek-product-photos.webp)

### 3.16 Photos du produit

Ouvrez l'onglet **Photos** d'un produit. Si **AI Image Finder** est désactivé, l'onglet explique comment l'activer dans **Settings**, **General**.

1. Cliquez sur **Find pages**. DeepSeek suggère des pages web qui contiennent probablement des photos du produit.
2. Les pages et les images apparaissent. Cochez les images souhaitées.
3. Cliquez sur **Add selected to this product**. Rien n'est enregistré avant ce clic.

Le modèle suggère des pages à partir de ses propres connaissances, et non d'une recherche web en direct. Vérifiez les droits d'auteur et la qualité des images avant de les publier.

## 4. Front de la boutique

Le module n'affiche rien aux clients. Les deux hooks front qu'il enregistre sont vides, et aucun template, bouton ni bloc n'est ajouté à votre thème. Le texte rédigé par le module n'apparaît sur votre boutique que sous forme de champs ordinaires de produits et de catégories (nom, descriptions, balises meta, tags). Vous n'avez pas besoin de modifier le thème.

Le module dispose aussi de deux adresses qu'un navigateur ou un serveur peut ouvrir :

| Adresse | Qui l'utilise | Ce qui se passe |
|---|---|---|
| L'adresse **Cron** avec `&action=generateProductContent` ou `&action=generateCategoryContent` | Le planificateur de votre serveur, ou vous lors d'un test | Un lot est écrit. Avec **Enable Debug** réglé sur **Yes**, le plan est affiché et rien n'est enregistré. Un secret erroné ou manquant est refusé. |
| L'adresse interne de requête utilisée par les boutons du back-office | Votre navigateur pendant que vous travaillez dans le back-office | Elle nécessite un token que le back-office ajoute automatiquement. Vous ne le saisissez jamais. Si elle est refusée, rechargez la page du back-office. |

## 5. Problèmes

**Une génération échoue et History affiche une Error.**
Ouvrez **History**, ouvrez la ligne et lisez le message. Les causes courantes sont indiquées ci-dessous.

**La clé d'API est rejetée ou manquante.**
Ouvrez **Settings**, **DeepSeek**, collez de nouveau la clé depuis https://platform.deepseek.com/api_keys et appuyez sur **Save**. Sur la page du nouveau produit, l'avertissement **Add an API key in the module settings first.** disparaît ensuite. Si DeepSeek signale l'absence de solde, rechargez le compte chez DeepSeek.

**L'appel se termine par un dépassement de délai.**
Augmentez **API timeout (seconds)** dans **Settings**, **General** (pour `deepseek-reasoner`, utilisez plusieurs centaines de secondes). Pour le cron, réduisez **Product to update**.

**Le texte est coupé au milieu d'une phrase.**
Augmentez **Max Tokens** dans **Settings**, **DeepSeek**. Avec `deepseek-reasoner`, la limite couvre aussi son raisonnement.

**Les réglages ne semblent pas changer le style.**
Avec `deepseek-reasoner`, **Temperature**, **Top P** et les deux champs de pénalité peuvent être ignorés. Utilisez `deepseek-chat`. Vérifiez aussi que **Studio** est enregistré et que vous avez utilisé la bonne langue.

**Une réponse n'est pas enregistrée et rien ne change sur le produit.**
Causes possibles : la réponse contient une ligne de **Forbidden words** et **Quality gate** est activé (modifiez la liste ou désactivez le filtre) ; **Existing text** est sur **Skip if filled** et le champ contient du texte ; le plafond mensuel est atteint (**Monthly generation budget reached. Raise it in the studio settings or wait until next month.**).

**Le nom de modèle que j'ai saisi ne fonctionne pas.**
Vous avez ajouté un identifiant que votre compte ne peut pas appeler. Sélectionnez de nouveau le `deepseek-chat` intégré et supprimez votre propre entrée.

**La liste Generate est vide ou trop courte.**
Vérifiez **Product status**, **Product stock**, **Update only** et **Product Limit**. Une erreur fréquente est de laisser **Update only** sur "already updated" pour un premier traitement.

**Le cron ne fait rien.**
Vérifiez dans cet ordre : **Enable Cron Feature** est sur **Yes** ; l'adresse se termine par le bon `&action=…` ; le secret est celui actuellement affiché ; **Enable Debug** est sur **No** ; **Selected Products** contient encore des éléments en attente ; le serveur appelle réellement l'adresse. Un ensemble terminé cesse volontairement de changer. Pour plusieurs champs, utilisez **pendingField** au lieu de **pendingDeepSeek**, car le second ignore un produit dès qu'un champ quelconque a été généré.

**Le cron s'est arrêté après le changement du secret.**
L'ancienne adresse n'est plus valide. Copiez la nouvelle adresse (avec `&action=…`) dans le planificateur.

**La page indique "Error! Invalid token!" ou les boutons restent muets.**
La page est restée ouverte trop longtemps. Rechargez la page du back-office et réessayez.

**L'onglet Modules du produit n'a aucun contenu My AI DeepSeek.**
Vérifiez que **Product edit page Form** ou **Product Edit History** est activé, que le module est actif et que le cache a été vidé.

**Il n'y a pas de bouton "Restore".**
La ligne était une erreur, l'écriture n'avait pas de valeur précédente, ou **Clear list** a supprimé les lignes de History.

**Certains libellés indiquent encore "OpenAi".**
Quelques messages et libellés de filtre conservent un ancien nom, par exemple **OpenAi Settings Updated** après l'enregistrement du formulaire **DeepSeek**, les options "updated with OpenAi content" du filtre **Update only** ou un ancien nom de modèle d'exemple dans une aide. Le service utilisé est DeepSeek. Dans History, la colonne **Provider** peut afficher l'ancien nom interne. Cela n'affecte pas les résultats.

**Rien ne change sur le front de la boutique.**
Le module écrit des champs ordinaires de produit. Vérifiez le produit dans **Catalog** et le cache de votre thème.

## 6. Pour le développeur

### 6.1 Vue d'ensemble

- **Nom technique :** `myaideepseek`
- **Nom du module dans la liste :** My AI DeepSeek - AI content generation
- **Version :** 1.0.0
- **Auteur :** MyPresta.eu
- **Compatibilité PrestaShop :** 1.6 – 9.99.99
- **PHP :** 7.0 ou plus récent (l'installation refuse les versions plus anciennes)
- **Réseau :** cURL et HTTPS vers `https://api.deepseek.com/v1`
- **Préfixe de configuration :** `MYPRESTA_MYAIDEEPSEEK_`
- **Flux :** les réglages sont lus dans la table de configuration ; les prompts sont construits à partir du modèle ou de l'instruction plus les règles Studio ; une requête de chat est envoyée par champ ; la réponse est vérifiée (Quality gate, budget), enregistrée sur le produit ou la catégorie et journalisée dans `myaideepseek_log` avec la valeur précédente.

### 6.2 Fichiers

| Fichier | Rôle |
|---|---|
| `myaideepseek.php` | Classe principale : installation, désinstallation, formulaires de réglages, navigation, hooks, onglet produit. |
| `autoload.php` | Chargement des classes pour `src/` et `lib/`. |
| `src/OpenAIService.php` | Client HTTP pour l'appel de chat completion (conservé sous l'ancien nom de fichier). |
| `src/Studio.php` | Ajoute les règles Studio et le contrôle de qualité. |
| `lib/updateChecker.php` | Vérification des mises à jour auprès de MyPresta.eu. |
| `lib/sectionHelp.php` | Textes des aides contextuelles. |
| `lib/searchTool/` | Aide à l'autocomplétion. |
| `lib/prestashop9compatibility.php` | Aide de compatibilité pour PrestaShop 9. |
| `controllers/admin/` | Sept contrôleurs d'administration (voir 6.3). |
| `controllers/front/ajax.php` | Actions AJAX du back-office (générer, restaurer, recherche d'images). |
| `controllers/front/cron.php` | Génération planifiée. |
| `views/templates/hook/*.tpl` | Onglet produit, générateurs en masse, dashboard, cron, history, playground, navigation. |
| `views/templates/admin/product_creator.tpl` | Écran du nouveau produit. |
| `views/js/` | `back.js`, `product-fields.js`, `image-finder.js`, `dashboard.js`, `admin-help.js`, `admin-products-bulk.js`, `chart.min.js`. |
| `views/css/` | `back.css`, `admin-nav.css`, `stats.css`. |
| `translations/{iso}.php` | Traductions du module. |

### 6.3 Contrôleurs

| Classe | Rôle |
|---|---|
| `AdminMyAIDeepSeekMain` | Parent du menu **AI Content Generator**. |
| `AdminMyAIDeepSeek` | **Generate** (`mds_sub=products` ou `categories`). |
| `AdminMyAIDeepSeekProductCreator` | **New product**. |
| `AdminMyAIDeepSeekSettings` | Entrée des réglages (les formulaires se trouvent sur la page de configuration du module). |
| `AdminMyAIDeepSeekCron` | Formulaires **Cron**. |
| `AdminMyAIDeepSeekUsage` | **History**. |
| `AdminMyAIDeepSeekImageFinder` | **Images**. |
| `ModuleFrontController` ajax | Nécessite le paramètre `secret_token` égal à `MYPRESTA_MYAIDEEPSEEK_TOKEN` ; sinon il répond *Error! Invalid token!* |
| `ModuleFrontController` cron | Nécessite `secret` égal au secret des produits ou des catégories. |

La page de configuration du module utilise `mds_tab` (`dashboard`, `settings`, `updates`), `mds_sub` (`general`, `openai` = la section **DeepSeek**, `studio`, `templates`, `playground`) et `mcg_preset` pour les périodes prédéfinies.

Paramètres de requête du cron lus par `controllers/front/cron.php` :

| Paramètre | Utilisé pour | Valeur par défaut en son absence |
|---|---|---|
| `secret` | Secret des produits ou des catégories (obligatoire) | – |
| `action` | `generateProductContent` ou `generateCategoryContent` (obligatoire) | – |
| `updatedField` | Champ à écrire | valeur enregistrée |
| `productTarget` / `categoryTarget` | `pendingDeepSeek`, `pendingField`, `emptyField` | valeur enregistrée |
| `productsToUpdate` / `categoriesToUpdate` | Taille du lot | valeur enregistrée |
| `languageId` | Langue | valeur enregistrée |
| `promptTemplateId` | Modèle | valeur enregistrée |
| `debug` | Afficher uniquement le plan | valeur enregistrée |
| `categories` | Filtre de catégories (produits) | valeur enregistrée |
| `productIds` | Filtre d'identifiants de produit | valeur enregistrée |

### 6.4 Hooks

Enregistrés : `displayAdminProductsMainStepLeftColumnMiddle`, `displayAdminProductsMainStepLeftColumnBottom` (tous deux renvoient une chaîne vide), `actionProductFormBuilderModifier` (retourne sans sortie), `displayAdminProductsExtra` (le contenu de l'onglet **Modules**), `displayBackOfficeHeader` (ressources, chargeur de la page produit), `displayBackOfficeTop` (raccourci de la barre supérieure), `dashboardZoneTwo` (bloc sur le dashboard de PrestaShop), `displayHeader` et `displayFooter` (tous deux vides). Le module n'expose aucun hook propre. Il ne surcharge ni `enable()` ni `disable()`.

### 6.5 Overrides

Aucun.

### 6.6 Base de données

| Table | Contenu |
|---|---|
| `myaideepseek_prompt` | `id_prompt`, `status`, `title`, `prompt`, `date_generated`. 16 lignes après l'installation. |
| `myaideepseek_log` | Une ligne par requête : identifiants du produit, de la catégorie, du CMS, du fabricant, de la langue et du collaborateur ; `type`, `method`, `status`, service, `model`, code HTTP, durée, nombres de tokens, message d'erreur, `prompt`, `reply`, ainsi que les anciennes et nouvelles valeurs du nom, des descriptions, des champs meta et des tags. |

La désinstallation supprime les deux tables. Les onglets sont supprimés. Le texte des produits et des catégories n'est pas touché.

### 6.7 Clés et traductions

Toutes les clés portent le préfixe `MYPRESTA_MYAIDEEPSEEK_`.

| Suffixe de clé | Par défaut | Signification |
|---|---|---|
| `LIVE_MODE` | 0 | Live mode. |
| `DEBUG_MODE` | 0 | Debug mode. |
| `TIMEOUT` | 120 | Délai d'expiration de l'appel en secondes. |
| `PRODUCT_LOG` | 1 | Historique d'édition du produit. |
| `TOPCTA` | 1 | Raccourci de la barre supérieure. |
| `PRODUCT` | 1 | Générateur de la page produit. |
| `IMAGEFINDER_ENABLE` | 1 | Interrupteur de la recherche de photos. |
| `IMAGEFINDER_PROMPT` | texte anglais intégré | Instruction de la recherche de photos. |
| `API_KEY` | vide | Clé DeepSeek. |
| `MODEL` | `deepseek-chat` | Modèle actif. |
| `EXTRA_MODELS` | vide | Modèles ajoutés par le marchand, un par ligne. |
| `MODEL_CAPS` | vide | Paramètres appris par modèle à l'exécution. |
| `TEMPERATURE` | 0.7 | Échantillonnage. |
| `MAX_TOKENS` | 3200 | Limite de réponse. |
| `TOP_P`, `FREQ_PEN`, `PRES_PEN` | 1, 0, 0 | Échantillonnage et pénalités. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | vide | Règles Studio. |
| `BUDGET` | 0 | Plafond mensuel, 0 = aucun. |
| `QUALITY` | 1 | Quality gate. |
| `TOKEN` | aléatoire | Token de l'adresse AJAX. |
| `SECRET`, `CAT_SECRET` | aléatoire | Secrets de cron des produits et des catégories. |
| `ENABLE_CRON` | 0 | Interrupteur global du cron. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 6 | Intervalle suggéré (Every Hour). |
| `updatedField`, `catupdatedField` | `description` | Champ du cron. |
| `productTarget`, `categoryTarget` | `pendingDeepSeek` | Règle du cron. |
| `productsToUpdate`, `categoriesToUpdate` | 5 | Lot du cron. |
| `promptTemplateId`, `catpromptTemplateId` | vide | Modèle du cron. |
| `languageId`, `catlanguageId` | langue par défaut | Langue du cron. |
| `debug`, `catdebug` | 0 | Debug du cron. |
| `productIdsList`, `categories` | vide | Filtres du cron. |
| `interval_select`, `IMAGEFINDER_TAB_OK` | vide / défini à l'exécution | État de l'interface. |

Le modèle par défaut est `deepseek-chat`. Les modèles intégrés sont `deepseek-chat` et `deepseek-reasoner`. La désinstallation supprime les clés ci-dessus. Les clés de filtre de Generate (par exemple les filtres de catégorie, de marque et de statut des formulaires **Generate**) ne figurent pas dans la liste de désinstallation et peuvent subsister.

Traductions : ajoutez `translations/{iso}.php` au format standard de PrestaShop. Les textes d'aide des champs sont construits par `fieldHelp()` sous la forme What it does / How to configure / Effect et passent par `$this->l()`. Certaines chaînes de l'onglet produit et des templates de génération sont définies dans les fichiers `.tpl` avec `{l s=…}`. Quelques chaînes résiduelles contiennent encore l'ancien nom du fournisseur (voir Problèmes).

### 6.8 Extension

L'onglet produit, les écrans en masse et le cron utilisent les mêmes marqueurs de prompt et les mêmes actions AJAX ; un modèle personnalisé qui respecte `{product_name}`, `{product_brand}`, `{product_features}` et `{product_tags}` fonctionne donc partout. Les contrôleurs front ne rendent aucun template, de sorte qu'un thème n'a rien à surcharger. Les templates d'administration de `views/templates/hook/` peuvent être surchargés grâce à la surcharge standard des templates de module du thème de votre back-office.

## 7. Aide

Page du module : https://mypresta.eu/modules/administration-tools/my-ai-deepseek.html

Pour nous écrire au sujet du module :

1. Connectez-vous à votre compte client sur mypresta.eu.
2. Ouvrez la page de contact.
3. Choisissez le sujet **Support for paid modules**. Le formulaire indique que vous devez être connecté. Après la connexion, sélectionnez ce module dans votre historique d'achats.
4. Décrivez le problème. Joignez la ligne de **History** (statut et message) ainsi que les versions de PrestaShop et de PHP. N'envoyez jamais la clé d'API ni le secret du cron.
