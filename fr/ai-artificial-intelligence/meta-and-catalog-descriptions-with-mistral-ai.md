---
title: "My AI Mistral - AI content generation - documentation et manuel d'utilisation"
description: "Instructions de configuration, d'utilisation quotidienne et de dépannage pour les marchands qui ont déjà installé My AI Mistral dans leur boutique PrestaShop."
sidebar:
  label: "My AI Mistral - AI content generation - documentation et manuel d'utilisation"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Meta and catalog descriptions with Mistral AI sur MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/meta-and-catalog-descriptions-with-mistral-ai.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ai-artificial-intelligence/meta-and-catalog-descriptions-with-mistral-ai/)
>
> ---


## 1. Prérequis

### 1.1 Boutique et serveur

| Élément | Nécessaire | Remarques |
|---|---|---|
| PrestaShop | 1.6 jusqu'à 9.x | Le module déclare la prise en charge des versions 1.6 à 9.99.99. L'onglet **My AI Mistral** de la page d'édition du produit et les petits boutons "Generate with AI" sont conçus pour PrestaShop 1.7, 8 et 9. |
| PHP | 7.0 ou plus récent | L'installation s'arrête avec un message lorsque le serveur utilise un PHP plus ancien. |
| Extensions PHP | cURL, JSON, mbstring, DOM | cURL est utilisé pour chaque appel à Mistral AI. DOM et mbstring servent à lire les pages web du chercheur de photos et à mesurer et couper le texte généré. |
| Connexion sortante | HTTPS (port 443) vers `api.mistral.ai` | Le serveur doit être autorisé à appeler l'API Mistral AI. Les offres d'hébergement qui bloquent les connexions sortantes ne fonctionnent pas. |
| Adresse du front de la boutique | Accessible depuis le navigateur | Les boutons du back-office envoient leurs requêtes à une adresse du front de votre boutique. Une demande de mot de passe, une règle de pare-feu ou une page de maintenance qui bloque cette adresse fait échouer les boutons. |

### 1.2 Compte Mistral AI

1. Créez un compte dans la console Mistral AI et ouvrez la page des clés d'API : https://console.mistral.ai/api-keys/
2. Créez une clé et copiez-la. La console ne l'affiche qu'une seule fois.
3. Assurez-vous que le compte peut utiliser l'API (un forfait ou une facturation incluant l'accès à l'API). Chaque texte généré correspond à une requête d'API payante ou décomptée de votre quota.

Le module n'a besoin d'aucun autre module et n'ajoute aucun override. Il n'affiche rien à vos clients.

### 1.3 Coûts et charge

- Un champ généré dans une langue correspond à une requête. Un lot de 40 produits avec descriptions et balises meta dans deux langues représente 40 × 4 × 2 = 320 requêtes, car l'option descriptions écrit deux champs et l'option meta en écrit deux autres.
- Chaque requête attend la réponse au maximum pendant la durée définie dans **API timeout (seconds)** (120 secondes par défaut). Un gros lot lancé depuis le navigateur est lent par nature ; utilisez cron pour les grands catalogues.
- Le module peut cesser de générer après un nombre mensuel de requêtes réussies (**Monthly generation budget** dans Studio).

## 2. Installation

### 2.1 Installer le module

1. Ouvrez **Modules > Module Manager** (**Modules and Services** dans PrestaShop 1.6).
2. Cliquez sur **Upload a module** (**Add a new module** en 1.6) et choisissez le fichier ZIP du module.
3. Cliquez sur **Install**, puis sur **Configure**.

Ce que l'installation fait pour vous :

- Elle ajoute l'entrée de menu du back-office **AI Content Generator** sous **Modules**. Elle ouvre la page de réglages du module, et tous les autres écrans sont accessibles depuis la barre de menu en haut de cette page.
- Elle crée deux tables de base de données : une pour les modèles de prompt et une pour l'historique des requêtes.
- Elle enregistre 16 modèles de prompt prêts à l'emploi (noms de produit, descriptions, meta titres, meta descriptions et tags). Tous sont activés au départ.
- Elle génère les codes secrets pour les boutons du back-office et pour cron, et sélectionne le modèle **mistral-small-latest**.
- Elle ne vide pas le cache de PrestaShop. Si l'entrée de menu n'apparaît pas, videz le cache dans **Advanced Parameters > Performance**.

À la première visite, vous verrez peut-être un message vert "Mistral AI API Key has been automatically cleaned (whitespace removed)". Il signifie seulement que la clé vide de remplacement a été nettoyée. Tout va bien.

### 2.2 Premiers pas après l'installation

1. Ouvrez **AI Content Generator > Settings > Mistral** et collez votre clé d'API.
2. Gardez le modèle par défaut pour un premier test et cliquez sur **Save**.
3. Ouvrez **Settings > Playground**, écrivez une courte instruction et cliquez sur **Generate**. Une réponse montre que la connexion fonctionne.
4. Ouvrez un produit existant, allez dans son onglet **Modules**, choisissez **My AI Mistral**, ouvrez **Simulate** et cliquez sur **Try** à côté de **Meta title**. Le texte s'affiche et rien n'est enregistré.

### 2.3 Mise à jour

Téléversez le nouveau ZIP dans Module Manager de la même façon que pour la première installation. Les réglages, les modèles et l'historique sont conservés. La page **Updates** du module indique si une version plus récente existe (section 3.15).

### 2.4 Désinstallation

La désinstallation supprime les entrées de menu, les modèles de prompt, tout l'historique des requêtes et les réglages du module, y compris la clé d'API et les secrets de cron. Une réinstallation repart de zéro et crée de nouveaux secrets ; chaque adresse donnée à un planificateur de tâches doit donc être remplacée.

Les textes déjà écrits dans les produits et les catégories, les photos importées, les produits créés avec **New product** et les tags restent dans votre boutique. Les réglages de la vérification des mises à jour et quelques valeurs de filtre résiduelles ne sont pas supprimés.

## 3. Configuration et travail dans le back-office

Les captures d'écran de ce manuel montrent le back-office en anglais. Les noms de menus, de champs et de boutons sont donnés en anglais et en gras, tels que vous les voyez à l'écran.

### 3.1 Comment le travail se déroule

1. **Connect** – collez la clé d'API et choisissez le modèle (Settings – Mistral).
2. **Set the rules** – règles de la maison, budget et contrôle qualité (Settings – Studio).
3. **Prepare prompts** – modifiez ou ajoutez des modèles de prompt (Settings – Prompt templates) et essayez-les dans le Playground.
4. **Generate** – choisissez l'une des trois méthodes :
   - un produit à la fois, depuis la page d'édition du produit (section 3.16) ou avec les petits boutons "Generate with AI" à côté des champs (section 3.17) ;
   - de nombreux produits ou catégories à la fois, depuis les pages Generate (sections 3.9 et 3.10) ;
   - automatiquement par petits lots, avec cron (section 3.12).
5. **Check** – chaque requête est enregistrée dans History (section 3.13). Un texte erroné peut être restauré depuis l'onglet History du produit lui-même.

Chaque page de réglages a son propre bouton **Save**. Enregistrez une page avant de la quitter, car les pages ne partagent pas un formulaire unique.

### 3.2 Ouvrir le module et barre de menu

Ouvrez **Modules > AI Content Generator**, ou cliquez sur **Configure** dans Module Manager. Chaque écran affiche la même barre de menu en haut :

| Élément de menu | Ce qu'il ouvre |
|---|---|
| Dashboard | Cartes d'utilisation et graphiques (section 3.3). |
| Settings | Un groupe de cinq sous-pages : General, Mistral, Studio, Prompt templates, Playground (sections 3.4 à 3.8). |
| Generate | Génération en masse pour les produits et pour les catégories (sections 3.9 et 3.10). |
| New product | Créer un produit à partir d'un court brief (section 3.11). |
| Cron | Adresses pour la génération planifiée (section 3.12). |
| History | Liste de toutes les requêtes avec filtres et totaux de tokens (section 3.13). |
| Images | Réglages du chercheur de photos (section 3.14). |
| Updates | Vérification des mises à jour (section 3.15). |

Chaque écran a un bouton **Help**. Il ouvre un panneau latéral avec une courte explication de cet écran. Survoler un élément de menu affiche une indication d'une ligne. Sous chaque champ, vous trouverez une description en trois parties : ce que fait le champ, comment le régler et quel en est l'effet.

### 3.3 Dashboard

![Dashboard with usage cards and charts](https://mypresta.eu/docs/images/docs/myaimistral-dashboard.webp)

Le Dashboard compte ce que le module a fait pendant la période sélectionnée. La ligne du haut indique le service actif et le modèle.

| Élément | Par défaut | Ce qu'il montre |
|---|---|---|
| Period buttons | 30 days | Today, 7 days, 30 days, 90 days, This month, All time. |
| From / To and Apply | rempli selon la période | Une plage personnalisée. Si From est postérieur à To, les deux dates sont échangées. |
| Requests | – | Chaque appel enregistré à Mistral AI sur la période. |
| Success | – | Appels ayant renvoyé un texte. |
| Errors | – | Appels ayant échoué. Ouvrez History pour voir pourquoi. |
| Tokens sent | – | Taille des instructions que vous avez envoyées. |
| Tokens received | – | Taille des réponses. |
| Requests and errors | – | Graphique en courbes par jour. |
| Tokens sent and received | – | Graphique en courbes par jour. |
| Requests by model | – | Graphique en barres. |

La page ne fait que rapporter. Rien dans le catalogue n'est généré ni modifié depuis ici, et History n'est pas supprimé.

### 3.4 Settings – General

![Settings – General](https://mypresta.eu/docs/images/docs/myaimistral-settings-general.webp)

Ouvrez **Settings > General**. Cette page décide de ce que les employés voient dans le back-office. L'enregistrer ne modifie aucun texte de produit.

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| Live mode | Disabled | Indique que le module fonctionne sur la vraie boutique plutôt que dans une configuration d'essai. Activez-le sur la boutique de production. |
| Debug mode | Disabled | Écrit des détails de diagnostic supplémentaires dans le journal de PrestaShop lorsqu'un appel au fournisseur échoue. Activez-le seulement pendant que vous étudiez une erreur. Les clients ne le voient jamais. Ce n'est pas la même chose que **Enable Debug** sur la page Cron. |
| API timeout (seconds) | 120 | Combien de secondes un appel à Mistral peut durer avant que le module abandonne. La valeur est maintenue entre 10 et 600. Une valeur vide ou non numérique est enregistrée comme 120. Augmentez-la vers 600 pour les textes longs et les modèles lents. |
| Product Edit History | Enabled | Affiche le sous-onglet **History** sur la page d'édition du produit, afin de pouvoir remettre une ancienne valeur. Les lignes passées restent de toute façon dans History. |
| Admin Top Bar CTA | Enabled | Affiche la petite icône de baguette dans la barre supérieure du back-office. La désactiver ne supprime que ce bouton, pas le menu du module. |
| Product edit page Form | Enabled | Affiche le panneau **My AI Mistral** (Generate, Simulate, Photos) dans l'onglet **Modules** de la page d'édition du produit. Désactivez-le lorsque seules la génération en masse et cron doivent être utilisés. Les petits boutons "Generate with AI" à côté des champs (section 3.17) ne sont pas désactivés par ce réglage dans cette version. |
| AI Image Finder | Enabled | Affiche ou masque la recherche de photos sur la page d'édition du produit. Une image n'est importée qu'après votre confirmation. |
| AI Image Search Prompt | Instruction intégrée | L'instruction envoyée lorsque quelqu'un cherche des photos. `{product_name}` et `{product_description}` sont remplacés par le produit courant. Conservez la demande d'une liste d'adresses de pages au format JSON. Les deux mêmes champs sont répétés sur la page **Images**. |

Cliquez sur **Save**. La confirmation est "Settings Updated".

### 3.5 Settings – Mistral

![Settings – Mistral](https://mypresta.eu/docs/images/docs/myaimistral-settings-mistral.webp)

Ouvrez **Settings > Mistral**. La page relie la boutique à votre compte Mistral AI et règle la variété du vocabulaire. Les champs d'échantillonnage ne changent pas les produits mis à jour.

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| Mistral AI API KEY | vide | La clé de https://console.mistral.ai/api-keys/. Les espaces sont supprimés à l'enregistrement. Laissez le champ intact pour conserver la clé enregistrée. Une valeur de moins de 10 caractères est refusée tant qu'aucune clé n'est enregistrée. |
| Model | mistral-small-latest | Le modèle qui écrit le texte. La liste contient les modèles intégrés et ceux que vous avez ajoutés. Un modèle que votre clé ne peut pas utiliser renvoie une erreur d'API au lieu d'un texte. |
| Add a Mistral model | vide | Saisissez le nom exact du modèle depuis votre compte Mistral et appuyez sur **Add model**. Le nouveau nom apparaît dans la liste **Model** et devient aussitôt le modèle actif. Les noms peuvent contenir des lettres, des chiffres et les caractères `.`, `_`, `:` et `-`. À côté de chaque nom ajouté se trouve un lien **Remove**. Les modèles intégrés ne peuvent pas être supprimés. |
| Max Tokens | 3200 | La réponse la plus longue en tokens. Utilisez environ 256 pour une meta description et 1000 ou plus pour une description HTML complète. Une valeur trop basse coupe le texte. Une valeur élevée coûte plus cher. |
| Temperature | 0.7 | La liberté avec laquelle le modèle choisit les mots, de 0 à 1. Environ 0.2 convient aux textes meta, environ 0.7 aux descriptions. Modifiez Temperature ou Top P, pas les deux. |
| Top P | 1 | Une autre façon de limiter le caractère surprenant du mot suivant, de 0 à 1. Laissez 1 si vous réglez Temperature. |
| Frequency Penalty Value | 0 | De -2 à 2. Une valeur positive comme 0.3 à 0.6 réduit les expressions répétées dans une même réponse. |
| Presence Penalty Value | 0 | De -2 à 2. Une valeur positive répartit le texte sur davantage de points. Certains modèles l'ignorent. |

Les modèles intégrés sont : mistral-small-latest, mistral-medium-latest, mistral-large-latest, ministral-8b-latest, ministral-3b-latest, codestral-latest et open-mistral-nemo.

Si Mistral refuse l'un des réglages numériques pour un modèle donné, le module s'en souvient, omet ce réglage pour ce modèle et réessaie. Vous n'avez rien à faire.

Le champ du nom du modèle doit contenir au moins 3 caractères à l'enregistrement, sinon la page affiche "OpenAi Model field is invalid!". La confirmation après l'enregistrement est "OpenAi Settings Updated". Les messages "Model added.", "Model removed." et "That model is already built in." concernent les boutons d'ajout et de suppression.

### 3.6 Settings – Studio

![Settings – Studio](https://mypresta.eu/docs/images/docs/myaimistral-settings-studio.webp)

Studio s'applique par-dessus chaque prompt, quel que soit l'endroit d'où part la requête : page produit, pages Generate, cron, Playground ou barre supérieure. Les champs vides sont ignorés.

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| Brand voice | vide | Un court brief indiquant au modèle qui s'exprime, par exemple "specialist workshop, short sentences, no hype". |
| Audience | vide | Le lecteur pour qui écrire, par exemple "professional installers". |
| Tone | vide | L'ambiance de la rédaction. Un ou deux mots suffisent. |
| Glossary | vide | Noms de marque, matériaux et graphies que le modèle doit reproduire exactement. Un terme par ligne. |
| Forbidden words | vide | Mots et expressions qui ne doivent pas apparaître dans une réponse enregistrée. Un par ligne. Utilisé seulement lorsque Quality gate est Enabled. |
| Monthly generation budget | 0 | Le nombre maximal de générations réussies autorisées dans le mois calendaire en cours. 0 signifie aucune limite. Le compteur repart le premier jour du mois. Lorsque le nombre est atteint, la génération s'arrête avec un message de budget. Les appels échoués ne sont pas comptés. |
| Quality gate | Enabled | Vérifie chaque réponse par rapport à Forbidden words avant d'enregistrer quoi que ce soit. Une réponse contenant un mot de la liste est rejetée, n'est pas écrite dans le produit et est enregistrée dans History comme erreur. Avec Disabled, la réponse est enregistrée quand même. |

Cliquez sur **Save studio**. La confirmation est "Studio settings saved.".

### 3.7 Settings – Prompt templates

![Settings – Prompt templates](https://mypresta.eu/docs/images/docs/myaimistral-settings-templates.webp)

Un modèle de prompt est une instruction enregistrée. La page affiche la liste **Prompt Templates** avec un bouton pour en créer un nouveau.

#### La liste

| Colonne | Ce qu'elle montre |
|---|---|
| ID | Numéro du modèle. |
| Title | Le nom que vous voyez dans les listes de modèles. |
| Prompt | Le texte de l'instruction. |
| Status | Cliquez sur l'icône pour activer ou désactiver un modèle. |
| Timestamp | Heure de création. |

Chaque ligne a **Edit** et **Delete**. Cochez plusieurs lignes et utilisez le **Delete** groupé pour les supprimer. Les modèles les plus récents sont en haut.

#### Le formulaire "Generate Prompt Template"

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| Status | non défini | Les modèles activés sont proposés dans le panneau produit, la page Generate – Products et la barre supérieure. Les modèles désactivés restent dans le tableau mais n'y sont pas proposés. Choisissez **Enabled** avant d'enregistrer, car un nouveau modèle démarre sans choix. |
| Prompt title | vide | Le nom affiché dans les listes déroulantes. Il n'est pas envoyé au modèle. Obligatoire. |
| Prompt content | vide | L'instruction envoyée au modèle. Les marqueurs entre accolades sont remplacés pour chaque élément avant l'envoi. Les guillemets doubles sont remplacés par des guillemets simples à l'enregistrement. Obligatoire. |

Cliquez sur **Save Prompt**. Les confirmations sont "Prompt template successfully added!", "Prompt template successfully updated!" et "Prompt template removed.". **Go Back to Module Settings** ramène à la liste.

#### Marqueurs (placeholders)

| Marqueur | Remplacé par | Fonctionne dans |
|---|---|---|
| {product_name} | Nom du produit | Génération de produits |
| {product_description} | Description longue | Génération de produits |
| {product_description_short} | Description courte | Génération de produits |
| {product_tags} | Tags actuels | Génération de produits |
| {product_reference} | Référence | Génération de produits |
| {product_ean13} | Code EAN-13 | Génération de produits |
| {product_weight} | Poids | Génération de produits |
| {product_brand} | Nom de la marque | Génération de produits |
| {product_default_category} | Nom de la catégorie par défaut | Génération de produits |
| {product_category_description} | Description de la catégorie par défaut | Génération de produits |
| {product_categories} | Noms de toutes les catégories du produit | Génération de produits |
| {product_attributes} | Attributs de la déclinaison (groupe et valeur) | Génération de produits |
| {product_features} | Noms des caractéristiques | Génération de produits |
| {product_feature_values} | Caractéristiques avec leurs valeurs | Génération de produits |
| {product_images} | Adresses des photos du produit | Génération de produits |
| {category_name} | Nom de la catégorie | Génération de catégories |
| {category_description} | Description de la catégorie | Génération de catégories |
| {category_parent_name} | Nom de la catégorie parente | Génération de catégories |
| {shop_name} | Nom de la boutique | Génération de produits et de catégories |
| {shop_url} | Domaine de la boutique | Génération de produits et de catégories |
| {shop_language} | Nom de la langue | Génération de produits et de catégories |
| {shop_country} | Pays par défaut | Génération de produits et de catégories |
| {shop_currency} | Code de la devise par défaut | Génération de produits et de catégories |

"Génération de produits" désigne le panneau produit, Generate – Products et le cron produits. "Génération de catégories" désigne Generate – Categories et le cron catégories. Les marqueurs ne sont pas remplacés dans le Playground ni dans la boîte de la barre supérieure, car aucun produit ni aucune catégorie n'y est sélectionné. Un marqueur sans donnée est remplacé par un texte vide.

#### Les 16 modèles livrés avec le module

| N° | Titre | Objectif |
|---|---|---|
| 1 | Product name 1 | Un nom plus court et meilleur, basé sur le nom actuel. |
| 2 | Product name 2 | Un titre vendeur qui utilise la marque et la catégorie par défaut. |
| 3 | Product description 1 | Description HTML avec trois intertitres et les tags en gras. |
| 4 | Product description 2 | Description en trois sections simples. |
| 5 | Product description 3 | Un long brief SEO qui demande aussi des idées d'intertitres, des mots-clés et des textes meta. |
| 6 | Product description 4 | Une courte demande de "description captivante". |
| 7 | Product description 5 | Description qui utilise les tags du produit comme mots-clés. |
| 8 | Product description 6 | Description qui utilise la marque et la catégorie par défaut. |
| 9 | Product description 7 - using product images | Description qui intègre les photos du produit via {product_images}. |
| 10 | Product meta title 1 | Meta titre SEO, jusqu'à 60 caractères. |
| 11 | Product meta title 2 | Une seconde variante de meta titre. |
| 12 | Product meta title 3 | Meta titre qui inclut la marque. |
| 13 | Product meta description 1 | Meta description SEO, jusqu'à 160 caractères. |
| 14 | Product meta description 2 | Une seconde variante ; le texte d'exemple mentionne une montre connectée. |
| 15 | Product meta description 3 | Le même texte que le numéro 14. |
| 16 | Product tags | Cinq tags sur une ligne, séparés par des virgules. |

Lisez et adaptez les modèles avant de les utiliser sur de vrais produits :

- Le modèle 3 demande au modèle d'ajouter quelques fautes d'orthographe au texte. Supprimez cette phrase.
- Le modèle 5 renvoie plus qu'une description (idées d'intertitres, liste de mots-clés et textes meta). Utilisez-le comme source d'inspiration, pas pour enregistrer directement dans le champ de description.
- Les modèles 5, 10, 13 et 16 demandent une réponse en anglais. Modifiez cette ligne si votre boutique utilise une autre langue.
- Les modèles 14 et 15 sont écrits pour une montre connectée. Remplacez l'exemple avant de les utiliser.

### 3.8 Settings – Playground

![Settings – Playground](https://mypresta.eu/docs/images/docs/myaimistral-settings-playground.webp)

Le Playground envoie un prompt libre au modèle actif et affiche la réponse sous le bouton. La réponse reste sur cette page. Aucun produit ni aucune catégorie n'est enregistré.

| Élément | Par défaut | Ce qu'il fait |
|---|---|---|
| Prompt box | vide | L'instruction pour cet unique appel. Les règles de Studio y sont ajoutées. |
| Generate | – | Envoie le prompt. Pendant l'attente, la zone de réponse affiche "Working…". |
| Answer area | – | La réponse du modèle avec le nombre de tokens utilisés. |

Messages : "Write a prompt first." (la boîte est vide) et "The request timed out or the shop blocked it." (voir la section 5.2).

La requête est enregistrée dans History comme toutes les autres.

### 3.9 Generate – Products

![Generate – Products](https://mypresta.eu/docs/images/docs/myaimistral-generate-products.webp)

Ouvrez **Generate** et restez sur **Products**. Le travail se fait en deux étapes : construire une liste, puis lancer la génération dessus.

#### Étape 1 – construire la liste ("Filter products to update")

Rien n'est envoyé au modèle dans cette étape. Les filtres démarrent avec les valeurs ci-dessous à chaque ouverture de la page.

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| Product Categories | aucune cochée | Arborescence des catégories. Seuls les produits situés dans une catégorie cochée, ou l'ayant comme catégorie par défaut, sont listés. Laissez l'arborescence vide pour ignorer la catégorie. |
| Brand | Select brand (all) | Seulement les produits d'une marque. |
| Product status | Active | **Active**, **Disabled** ou **Both**. |
| Product stock | All products | **All products** ou **Only in stock products**. |
| Update only | Update all | Utilise History : **Products that have not been updated with OpenAi content** liste les produits sans ligne dans History, **Products that already have been updated with OpenAi content** liste les produits avec une ligne, **Update all** ignore History. Le mot "OpenAi" dans les deux premiers choix est une ancienne étiquette ; il désigne ce module. Une ligne de n'importe quel statut compte, y compris une ligne en échec. |
| Product IDs | vide | ID de produits séparés par des virgules, par exemple 12,45,103. Saisissez uniquement des chiffres et des virgules. |
| Product Reference | vide | Une ou plusieurs références séparées par des virgules. La référence doit correspondre exactement. |
| Product Add Date From | vide | Seulement les produits créés après cette date et cette heure. |
| Product Add Date To | vide | Seulement les produits créés avant cette date et cette heure. |
| Minimum product ID | vide | Le plus petit ID de produit dans la liste. |
| Maximum product ID | vide | Le plus grand ID de produit dans la liste. |
| Product Limit | vide | Le nombre maximal de produits à charger. Utilisez un petit nombre comme 20 sur un grand catalogue. |

Cliquez sur **Go to next step**. Le bouton **Module settings** à côté est un ancien raccourci et n'ouvre pas les réglages de ce module.

#### Étape 2 – lancer la génération ("Mass product generation")

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| Template | Choose a template | Copie un modèle activé dans la boîte de prompt. Le titre lui-même n'est pas envoyé. |
| Prompt box | vide | L'instruction envoyée pour chaque produit, avec les marqueurs remplacés produit par produit. Si la boîte est vide, un brief standard est utilisé pour chaque champ. |
| What to generate | Descriptions | **Descriptions** (description longue et courte), **Meta title and meta description** ou **Descriptions and meta together** (les quatre). Chaque champ est une requête distincte. |
| Existing text | Replace | **Replace** écrase le texte. **Skip if filled** laisse tranquille un champ rempli et n'appelle pas le modèle pour lui. **Add above** et **Add below** conservent l'ancien texte et y ajoutent le nouveau. |
| Languages | votre langue du back-office cochée | Cochez chaque langue à écrire. Chaque langue cochée représente une requête de plus par champ. |

Cliquez sur **Run on the list below**. Le tableau liste les produits par ID et par référence. L'exécution parcourt un par un chaque produit, champ et langue. La ligne au-dessus du bouton montre la progression, par exemple "3 / 120 – description", et la colonne **Result** montre la réponse pour chaque étape. "skipped" signifie que le champ avait déjà du texte et que vous avez choisi **Skip if filled**. À la fin, la ligne indique "Finished N products.".

Vous ne pouvez pas décocher des produits individuels dans le tableau. Modifiez le filtre de l'étape 1 pour changer la liste. Les noms et les tags ne font pas partie de cette exécution ; utilisez la page d'édition du produit ou cron. Le texte est enregistré au fur et à mesure que chaque réponse arrive. Fermer la page arrête l'exécution, et les produits déjà traités conservent leur nouveau texte.

### 3.10 Generate – Categories

![Generate – Categories](https://mypresta.eu/docs/images/docs/myaimistral-generate-categories.webp)

Ouvrez **Generate** et passez à **Categories**.

#### Étape 1 – construire la liste ("Filter categories to update")

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| Categories | aucune cochée | Cochez les catégories à lister. Sans rien de coché, la liste contient toutes les catégories correspondant au statut, y compris Root et Home. Cochez des catégories précises pour l'éviter. |
| Category status | Active | **Active**, **Disabled** ou **Both**. |

Cliquez sur **Go to next step**.

#### Étape 2 – lancer la génération ("Mass category generation")

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| Prompt box | vide | L'instruction envoyée pour chaque catégorie. Utilisez {category_name}, {category_description}, {category_parent_name} et les marqueurs de la boutique. Cette page n'a pas de liste de modèles. |
| Field | Description | Le champ à écrire : **Description**, **Name**, **Meta title**, **Meta description** ou **Additional description**. Seul ce champ est enregistré. |
| Existing text | Replace | **Replace** ou **Skip if filled**. |
| Language | votre langue du back-office | Une seule langue. Relancez pour une autre langue. |

Cliquez sur **Run on the categories below**. Le tableau liste les ID de catégories et montre un résultat pour chacune.

Si la boîte de prompt est vide, un brief standard est utilisé pour la description, le meta titre et la meta description. Pour **Name** et **Additional description**, le brief de description serait utilisé ; saisissez donc toujours votre propre prompt pour ces deux champs.

Sous la liste, la page affiche aussi l'ancien formulaire **Generate category content** avec son bouton **Generate content**. Il ne génère rien. Utilisez le bouton d'exécution situé au-dessus.

### 3.11 New product

![New product](https://mypresta.eu/docs/images/docs/myaimistral-new-product.webp)

**New product** demande au modèle un brouillon complet de produit et peut l'insérer dans le catalogue.

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| What is the product? | vide | Quelques phrases : ce qu'est le produit, matériaux, public, noms à conserver. Un brief plus riche donne un brouillon plus proche. Une boîte vide est refusée. |
| Optional source URL | vide | Une adresse http ou https complète d'une page publique. Son texte lisible est ajouté au brief. Une page que la boutique ne peut pas lire est ignorée. |
| Language | langue par défaut de la boutique | La langue dans laquelle le nom, les descriptions, les meta et les tags sont enregistrés. Les autres langues ne sont pas remplies. |
| Default category ID | 2 | Le numéro de la catégorie depuis **Catalog > Categories**. 2 est généralement Home. Le produit y est placé. |

Boutons :

- **Generate data** affiche le brouillon en texte brut dans la boîte sous les boutons. Il n'enregistre rien. Le brouillon contient le nom, les descriptions, les textes meta, les tags, la référence, un prix suggéré et des caractéristiques.
- **Create product** insère le dernier brouillon généré. Le nouveau produit est **actif**, a un stock de **100**, utilise le premier groupe de règles de taxe de la boutique et est placé dans la catégorie que vous avez saisie. Après un succès, la boîte affiche "Product #" et le numéro du nouveau produit.

Le brouillon ne peut pas être modifié sur cette page. Vérifiez ensuite le prix, la taxe, les photos et la catégorie dans le produit ; le prix est celui que le modèle a suggéré et peut valoir 0. La page affiche "Add an API key in the module settings first." lorsqu'aucune clé n'est enregistrée.

### 3.12 Cron

![Cron](https://mypresta.eu/docs/images/docs/myaimistral-cron.webp)

Cron permet à votre serveur de mettre à jour quelques produits ou catégories chaque fois qu'un planificateur ouvre une adresse. La page affiche : le panneau **Category cron**, le formulaire **CRON JOB Settings - Generate product content using Mistral AI**, le formulaire **CRON JOB Settings - Generate category content using Mistral AI** et le panneau **Cron parameters**. Les formulaires ne font que construire et enregistrer des réglages ; rien ne s'exécute tant que votre serveur n'appelle pas l'adresse.

#### L'adresse cron

L'adresse des produits ressemble à ceci :

```text
https://YOUR-SHOP.EXAMPLE/module/myaimistral/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent
```

L'adresse des catégories ressemble à ceci :

```text
https://YOUR-SHOP.EXAMPLE/module/myaimistral/cron?secret=YOUR_CATEGORY_SECRET&action=generateCategoryContent
```

- Remplacez `YOUR-SHOP.EXAMPLE` par l'adresse de votre boutique.
- Remplacez le secret par le **Cron Job Secret Token** du formulaire correspondant. Ne le publiez jamais.
- La partie `&action=generateProductContent` ou `&action=generateCategoryContent` est obligatoire. Sans elle, l'adresse répond "Invalid action!".
- Les panneaux de la page n'affichent l'adresse que jusqu'au secret. Le panneau des catégories ajoute `&entity=category`, que la boutique n'utilise pas. Ajoutez vous-même la partie `action` comme indiqué ci-dessus.
- La ligne "Command:" à l'intérieur de chaque formulaire n'affiche que l'adresse simple, sans le secret ni l'action. Construisez vous-même l'adresse complète.

#### Formulaire produits

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| Enable Cron Feature | No | L'interrupteur général pour le cron des produits et des catégories. Avec No, chaque adresse cron répond que la fonction est désactivée. |
| Cron Job Secret Token | aléatoire, 32 caractères | Le mot de passe dans l'adresse des produits. Il doit comporter au moins 24 caractères. Un secret plus court est remplacé par un secret aléatoire au chargement de la page du module. |
| Update Field | description | Un champ par entrée du planificateur : name, description, description_short, meta_title, meta_description ou tags. Pour remplir plusieurs champs, créez plusieurs entrées. |
| Selected Products | pendingMistral | Quels produits attendent encore. **pendingMistral** prend les produits qui n'ont aucune ligne réussie dans History pour aucun champ. **pendingField** prend les produits sans ligne réussie pour le champ choisi, de sorte que plusieurs entrées peuvent remplir différents champs des mêmes produits. **emptyField** prend les produits dont le champ choisi est vide dans la langue choisie. |
| Product Categories | aucune cochée | Limite l'exécution aux produits des catégories cochées. Voir l'avertissement ci-dessous. |
| Product ID list | vide | Une liste fixe d'ID de produits séparés par des virgules. Les lettres sont supprimées à l'enregistrement. |
| Language | langue par défaut de la boutique | La langue à écrire. Les autres langues nécessitent leur propre entrée. |
| Product to update | 5 products | Combien de produits traiter par appel : 2, 3, 5, 8, 10, 15, 20, 50, 100, 200, 300, 500 ou 1000. Commencez par 5 ou 10 afin qu'un modèle lent n'atteigne pas la limite de temps du serveur. |
| Prompt Template | premier modèle de la liste | L'instruction enregistrée utilisée pour chaque produit. Voir la remarque ci-dessous. |
| Enable Debug | No | Avec Yes, l'adresse affiche ce qu'elle ferait et n'enregistre rien. |
| CRON JOB interval | Every Hour | Un rappel de la fréquence à laquelle vous prévoyez d'appeler l'adresse (de chaque minute à toutes les 6 heures). Le module ne lance rien par lui-même. |

Cliquez sur **Save**. La liste de **Prompt Template** n'a pas de choix vide et affiche chaque modèle enregistré, y compris les désactivés, le plus récent en premier. Tant que vous n'en avez pas enregistré un, le formulaire affiche le modèle le plus récent (Product tags). Choisissez toujours le modèle voulu et enregistrez, sinon c'est le modèle affiché qui est enregistré.

Avertissement : lorsque **Product Categories** comporte des catégories cochées, la boutique choisit aussi des produits dont la catégorie par défaut est cochée, même s'ils ont déjà été traités. Le cron peut alors réécrire les mêmes premiers produits à chaque appel. Laissez l'arborescence des catégories vide et utilisez plutôt **Product ID list**.

#### Formulaire catégories

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| Cron Job Secret Token | aléatoire, 32 caractères | Le mot de passe dans l'adresse des catégories. Au moins 24 caractères. |
| Update Field | description | name, description, meta_title ou meta_description. |
| Selected categories | pendingMistral | **pendingMistral**, **pendingField** ou **emptyField**, avec la même signification que pour les produits. |
| Language | langue par défaut de la boutique | La langue à écrire. |
| Categories to update | 5 categories | Combien de catégories par appel (mêmes choix que pour les produits). |
| Prompt Template | premier modèle de la liste | L'instruction enregistrée. Rédigez-la pour une catégorie, pas pour un produit. |
| Enable Debug | No | Avec Yes, l'adresse affiche le plan et n'enregistre rien. |
| CRON JOB interval | Every Hour | Simple rappel. |

Cliquez sur **Save** sous le formulaire. Root et Home ne sont jamais traités par le cron des catégories. L'interrupteur **Enable Cron Feature** se trouve dans le formulaire des produits et commande aussi le cron des catégories.

#### Secrets et "Generate Token"

Si vous voulez un nouveau secret, saisissez-le à la main dans le champ, au moins 24 caractères, lettres et chiffres. Le bouton **Generate Token** peut ne pas remplir le champ dans cette version ; ne comptez donc pas dessus. Après avoir enregistré un nouveau secret, modifiez-le aussi dans votre planificateur, car l'ancienne adresse cesse de fonctionner. N'importe lequel des deux secrets ouvre n'importe laquelle des deux actions ; gardez donc les deux privés.

#### Configurer le planificateur

Sur un serveur Linux, ajoutez à la crontab une ligne comme celle-ci (toutes les heures) :

```text
0 * * * * curl -s -o /dev/null "https://YOUR-SHOP.EXAMPLE/module/myaimistral/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent"
```

Gardez l'adresse entre guillemets, car elle contient le signe `&`. Sous Windows, utilisez le Planificateur de tâches avec `curl.exe` et la même adresse. Les panneaux d'hébergement dotés d'un écran "cron job" acceptent la même commande.

#### Tester en toute sécurité

1. Enregistrez le formulaire avec **Enable Cron Feature** sur Yes et **Enable Debug** sur Yes.
2. Ouvrez l'adresse complète dans un navigateur. Vous voyez les réglages lus, la requête et le prompt final, et rien n'est enregistré.
3. Mettez **Enable Debug** sur No, enregistrez et rouvrez l'adresse. La page répond maintenant par un court texte tel que "5 products have been updated.".

Si **Enable Debug** reste activé, les appels planifiés n'enregistrent rien. C'est la raison la plus fréquente pour laquelle un cron "ne fait rien".

Le texte enregistré est coupé à la longueur autorisée par PrestaShop : nom 128, description courte 799, meta titre 69 et meta description 159 caractères. L'ancien texte est conservé dans History, de sorte que vous pouvez le restaurer depuis la page du produit.

### 3.13 History

![History](https://mypresta.eu/docs/images/docs/myaimistral-history.webp)

Chaque requête vers Mistral AI est écrite dans History avec son instruction, sa réponse ou son erreur, le modèle, le nombre de tokens et le temps qu'elle a pris.

#### Filtres et totaux

| Élément | Par défaut | Ce qu'il fait |
|---|---|---|
| Period buttons | This month | Today, 7 days, 30 days, This month, All time. |
| From / To | rempli selon la période | Une plage personnalisée. |
| Model | Any | Un seul modèle. |
| Type | Any | Un seul type de requête, par exemple product_description ou category_meta_title. |
| Status | Any | Success ou Error. |
| Language | Any | Une seule langue. |
| Employee | Any | Seulement les requêtes faites par un employé. |
| Product / category ID | vide | Seulement les requêtes pour cet enregistrement. |
| Prompt or reply contains | vide | Un mot recherché dans l'instruction et dans la réponse. |
| Filter | – | Applique les filtres. |

Les cartes affichent Requests, Success, Errors, Tokens sent, Tokens received, Tokens total et Average time. Un tiret signifie que Mistral n'a pas renvoyé de nombre de tokens pour cet appel. Sous les cartes se trouvent les tableaux **By day**, **By model**, **By type**, **By language** et **By employee** avec les colonnes Group, Calls, Sent, Received et Total. Un petit nombre à côté de Calls est le nombre d'erreurs de ce groupe.

#### La liste "Prompt history"

La liste suit les filtres et affiche 50 lignes par page.

| Colonne | Ce qu'elle montre |
|---|---|
| ID | Numéro de la ligne de journal. |
| Status | Success ou Error. |
| Prompt | Le début de l'instruction. |
| Reply / Error | Le début de la réponse, ou le texte de l'erreur. |
| Provider | Le nom du fournisseur, le modèle, le code HTTP et la durée en secondes, séparés par des points. Le nom du fournisseur indique toujours "openai". |
| Sent / Received / Total | Tokens. |
| Entity ID | Le produit ou la catégorie visé par la requête. |
| Type | Le type de requête. |
| Timestamp | Le moment où la requête a été faite. |

Cliquez sur **View** sur une ligne pour lire le prompt et la réponse en entier. **Back to the list** ramène à la liste.

**Clear list** (barre d'outils) supprime toutes les lignes, pas seulement les lignes filtrées, et affiche "Log list successfully deleted.". Il réinitialise aussi les informations que cron utilise pour savoir quels éléments ont déjà été mis à jour (les cibles "pending" repartent du début), réinitialise le compteur du budget mensuel et supprime les textes précédents nécessaires à **Restore**. Il n'y a pas d'annulation possible.

### 3.14 Images

![Images](https://mypresta.eu/docs/images/docs/myaimistral-images.webp)

La page **AI Image Finder** contient les mêmes deux réglages que la fin de Settings – General. Les enregistrer ne télécharge aucune image et ne modifie aucun texte.

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| AI Image Finder | Enabled | Affiche ou masque la recherche de photos sur la page d'édition du produit. |
| AI Image Search Prompt | Instruction intégrée | L'instruction envoyée lorsque quelqu'un cherche des photos. `{product_name}` et `{product_description}` sont remplacés par le produit courant. Le texte intégré demande exactement 5 adresses de pages sous forme de liste JSON. Modifiez la formulation si vous préférez les sites de fabricants. Un prompt vague renvoie des liens sans rapport. |

Cliquez sur **Save**. La confirmation est "Settings saved.".

Fonctionnement : le modèle suggère des pages web qui montrent probablement le produit, le module ouvre ces pages et liste les photos qu'il trouve, et vous cochez les photos à importer. Le module ne vérifie pas à qui appartiennent les photos. N'utilisez que des photos que vous avez le droit d'utiliser.

### 3.15 Updates

![Updates](https://mypresta.eu/docs/images/docs/myaimistral-updates.webp)

| Élément | Par défaut | Ce qu'il fait |
|---|---|---|
| Manual Check – Check Now | – | Interroge une fois le serveur de mises à jour sur la dernière version. La réponse est "Module is up to date!" ou "New version available!". |
| Automatic Notifications | Enabled | Environ tous les trois jours, le module vérifie en arrière-plan. Lorsqu'une version plus récente existe, les employés voient une bannière d'avertissement dans le back-office. Choisissez Disabled pour gérer les mises à jour à la main. |
| Product Page | – | Un lien vers la page du module. |

Cliquez sur **Save**. La confirmation est "Update settings saved.". La vérification envoie à MyPresta.eu le nom du module, sa version et l'adresse de votre boutique.

### 3.16 Page d'édition du produit

![Product edit page – My AI Mistral tab](https://mypresta.eu/docs/images/docs/myaimistral-product-edit.webp)

Ouvrez **Catalog > Products**, modifiez un produit existant et ouvrez l'onglet **Modules**. Choisissez **My AI Mistral**. L'onglet comporte les sous-onglets **Generate**, **Simulate**, **Photos** et **History**. Les trois premiers apparaissent lorsque **Product edit page Form** est Enabled ; **History** apparaît lorsque **Product Edit History** est Enabled.

#### Commandes communes à Generate et Simulate

| Élément | Par défaut | Ce qu'il fait |
|---|---|---|
| Language | première langue | Cliquez sur une langue, ou sur **Every language** pour les écrire toutes l'une après l'autre. |
| If the field already has text | Replace | **Replace**, **Add above**, **Add below** ou **Skip if filled**. Affiché uniquement dans le sous-onglet Generate. |
| Use your own instruction or a saved prompt | fermé | Ouvre une boîte de filtre et des tuiles : **Standard brief** et chaque modèle activé. Cliquez sur une tuile pour l'utiliser. |
| Instruction | vide | Votre propre texte. Lorsqu'il est vide, le brief standard du champ dont vous appuyez sur le bouton est utilisé. Les marqueurs sont remplacés pour ce produit. |

La boîte Instruction conserve le texte de la dernière exécution. Après avoir appuyé sur un bouton, la boîte affiche le brief utilisé, et le bouton suivant le réutilise. Videz la boîte avant d'appuyer sur le bouton d'un autre champ.

#### Generate

Chaque carte a un bouton **Fill** : **Description** ("The long text on the product page, with a short intro and a feature list."), **Short description**, **Name**, **Meta title**, **Meta description** et **Tags**. Le texte est **enregistré immédiatement sur le produit** et affiché sous les cartes avec le nombre de tokens. La carte **SEO pack** a le bouton **Fill all** ; il remplit le nom, les deux descriptions et les deux champs meta en une seule requête et répond "SEO pack saved. Refresh the product to see it.".

Important : le formulaire produit ouvert dans votre navigateur contient toujours les anciens textes. Rechargez la page du produit avant de cliquer sur **Save** dans PrestaShop, sinon les anciens textes écrasent les nouveaux.

#### Simulate

Les mêmes cartes avec le bouton **Try**. Le texte s'affiche sur la page et le produit n'est pas modifié. Utilisez-le pour comparer des prompts et des modèles avant que le module n'écrive.

#### Photos

![Photos sub-tab](https://mypresta.eu/docs/images/docs/myaimistral-product-photos.webp)

1. Cliquez sur **Find pages**. Le modèle suggère des pages qui montrent probablement le produit, et le module liste les photos trouvées sur celles-ci.
2. Cochez les photos souhaitées. Le message indique "Tick the photos you want, then add them to this product.".
3. Cliquez sur **Add selected to this product**. Les photos sont téléchargées et rattachées au produit. Le message indique "Done. Reload the product to see the new photos." ou le nombre de photos ajoutées.

Lorsque le chercheur est désactivé, l'onglet le dit et renvoie à Settings – General. Autres messages : "No photos were found on the suggested pages.", "The search failed." et "The photos could not be added.".

#### History

Un tableau avec **When**, **Type**, **Status** et un bouton **Restore** pour les 50 dernières requêtes du produit. **Restore** demande "Restore the previous value?", remet le texte précédent et répond "Content successfully restored. Refresh this page to see changes.". Le bouton n'est affiché que pour les modifications réussies qui ont conservé un texte précédent. S'il n'y en a pas, la page indique "No generations for this product yet.".

### 3.17 Boutons "Generate with AI" à côté des champs

Sur la page d'édition du produit, un petit bouton avec le logo Mistral se trouve à côté des éditeurs de **Description**, **Short description**, **Meta title** et **Meta description**. Sur la page d'édition de catégorie, il se trouve à côté de **Description**, **Additional description**, **Meta title** et **Meta description**.

1. Cliquez sur le bouton. Si la boutique compte plusieurs langues, choisissez **Current language**, **All languages** ou **Cancel**.
2. Patientez. Le bouton affiche un état occupé pendant l'exécution de la requête.
3. Le texte apparaît dans le champ. Cliquez sur **Save** sur le produit ou la catégorie pour le conserver. Rien n'est enregistré avant.

L'enregistrement doit déjà exister. Sur un nouveau produit, le bouton répond "Save the product once before generating." et sur une nouvelle catégorie "Save the category once before generating.". Les erreurs apparaissent dans une boîte de message, par exemple "Generation failed.".

Ces boutons utilisent toujours le brief standard du champ, pas vos modèles. Les règles de la maison, le budget et le contrôle qualité de Studio ainsi que le modèle de Settings s'appliquent toujours.

### 3.18 Autres raccourcis

| Endroit | Ce qu'il fait |
|---|---|
| Icône de baguette dans la barre supérieure | Ouvre une petite boîte : **Template** facultatif, une zone de texte et **Generate**. La réponse s'affiche dans la boîte ; copiez-la là où vous en avez besoin. Rien n'est enregistré et les marqueurs ne sont pas remplacés. Masquez l'icône avec **Admin Top Bar CTA** dans Settings – General. |
| Liste des produits | Un bouton **My AI Mistral** à côté des actions groupées ou de la barre d'outils de **Catalog > Products** ouvre la page Generate. |
| PrestaShop Dashboard | Un petit panneau avec les raccourcis **Mass content**, **Log** et **Cron** et le lien vers le support de MyPresta.eu. |

## 4. Front de la boutique

My AI Mistral n'a aucune partie visible par les clients. Il n'ajoute ni blocs, ni pages, ni scripts, ni styles aux pages de votre boutique, et les clients ne peuvent pas voir que le module existe. Ses deux adresses front ne sont utilisées que par le back-office et par votre planificateur.

### 4.1 Adresses

| Adresse | Utilisée par | Que faire |
|---|---|---|
| /module/myaimistral/cron | Votre planificateur (section 3.12) | Appelez-la avec le secret et l'action comme indiqué à la section 3.12. |
| /module/myaimistral/ajax | Les boutons du back-office | Ne l'appelez pas à la main et ne la mettez pas dans un planificateur. |

### 4.2 Ce que répond l'adresse cron

L'adresse répond en texte brut. Une exécution s'arrête à la première erreur ; les éléments déjà terminés restent enregistrés.

| Réponse | Signification | Que faire |
|---|---|---|
| Cron Job feature is disabled. You can enable it from the module settings. | **Enable Cron Feature** est sur No. | Mettez Yes et enregistrez. |
| The token does not exist or it's wrong! | Le secret est absent, erroné ou ancien. | Copiez le secret actuel du formulaire. |
| Invalid action! | La partie `action` est absente ou mal orthographiée. | Ajoutez `&action=generateProductContent` ou `&action=generateCategoryContent`. |
| updatedField parameter is wrong! | Le champ ne fait pas partie des champs autorisés. | Choisissez à nouveau le champ et enregistrez le formulaire. |
| All must include all mandatory parameters! | Un réglage enregistré est vide. | Enregistrez à nouveau le formulaire, avec une langue et un modèle choisis. |
| productTarget parameter is wrong! Allowed values: … | La valeur de la cible est inconnue. | Choisissez à nouveau **Selected Products**. Idem pour le formulaire des catégories. |
| No valid product IDs provided. | **Product ID list** contient du texte mais aucun nombre valide. | Corrigez ou videz la liste. |
| No products to update. / No categories to update. | Rien ne correspond aux réglages. | Modifiez les filtres ou la cible, ou considérez que le travail est terminé. |
| 5 products have been updated. / 5 categories have been updated. | L'exécution est terminée. Le nombre est le total. | Consultez History pour le détail. |
| 5 pending products. | Debug est activé ; rien n'a été enregistré. | Mettez **Enable Debug** sur No. |
| Error! followed by a text | Le fournisseur a renvoyé une erreur. | Lisez le texte, voir la section 5.2. |
| Error! The model returned an empty response. | Mistral n'a envoyé aucun texte. | Augmentez **Max Tokens** ou changez de modèle de prompt. |
| Error! Could not save product 12: … | PrestaShop a refusé le texte pour ce produit. | Lisez la raison qui suit ; l'exécution s'est arrêtée là. |

## 5. Problèmes

### 5.1 Installation et menu

| Symptôme | Cause | Que faire |
|---|---|---|
| L'installateur indique que le module nécessite PHP 7.0 ou plus récent | Le serveur utilise un PHP plus ancien. | Changez la version de PHP dans votre panneau d'hébergement et réinstallez. |
| "Could not create the module database tables." | L'utilisateur de la base de données ne peut pas créer de tables. | Donnez ce droit à l'utilisateur ou demandez à votre hébergeur. |
| L'entrée de menu AI Content Generator est absente | Ancien cache, module désactivé, ou le profil de l'employé n'a pas la permission. | Videz le cache, activez le module et vérifiez **Administration > Permissions** pour le profil. |
| La page produit n'a pas de panneau My AI Mistral dans l'onglet Modules | **Product edit page Form** et **Product Edit History** sont tous deux Disabled, ou la page est en cache. | Activez le réglage dans Settings – General et rechargez la page du produit. |

### 5.2 Connexion à Mistral AI

| Symptôme | Cause | Que faire |
|---|---|---|
| "The Mistral API key is not set. Add it in the module settings." | Aucune clé n'est enregistrée. | Collez la clé dans Settings – Mistral. |
| "Mistral AI API KEY field is invalid!" | Moins de 10 caractères et aucune clé enregistrée. | Copiez la clé entière depuis la console. |
| "Mistral AI API Error (401): …" | La clé est erronée, révoquée ou issue d'un autre compte. | Créez une nouvelle clé et collez-la à nouveau. |
| "Mistral AI API Error (429): …" | Une limite de Mistral a été atteinte. | Attendez une minute et réessayez, utilisez des lots plus petits ou augmentez votre forfait. |
| "Mistral request timed out after N seconds…" | Le modèle est lent ou le texte est long. | Augmentez **API timeout (seconds)** dans Settings – General ou utilisez un modèle plus rapide. |
| "The request timed out or the shop blocked it." | Le serveur, un pare-feu ou le front de la boutique a bloqué la requête. | Autorisez le HTTPS sortant vers l'API Mistral et rendez l'adresse du front de la boutique accessible. |
| Le modèle est introuvable | Un nom de modèle que votre compte Mistral ne peut pas utiliser. | Choisissez un autre modèle dans la liste. |
| La liste Model est passée à gpt-4o après la suppression d'un modèle | Le module se rabat sur un ancien nom par défaut. | Choisissez à nouveau un modèle Mistral et enregistrez. |
| "Error! Invalid token!" | Le secret que détient la page ouverte du back-office ne correspond plus à celui de la boutique, par exemple après une réinstallation. | Rechargez la page. |

### 5.3 Génération

| Symptôme | Cause | Que faire |
|---|---|---|
| "Error! Content retrieve has failed! Details: …" | L'API a renvoyé une erreur. Les détails la nomment. | Lisez les détails et la ligne dans History. |
| "Monthly generation budget reached. Raise it in the studio settings or wait until next month." | La limite de Studio est épuisée. | Augmentez le budget ou attendez le mois suivant. |
| "The reply was rejected because it contains a forbidden word from the studio settings." | Quality gate a trouvé un mot de votre liste. | Modifiez la liste ou le prompt et relancez. |
| "The model returned an empty response." ou "The model hit the token limit before returning any text…" | **Max Tokens** est trop bas ou le modèle l'a dépensé en réflexion. | Augmentez **Max Tokens**. |
| "The response was blocked by the provider content filter. Try rewording the prompt." | Mistral a refusé le contenu. | Reformulez le prompt. |
| "Error! Prompt is missing or too short!" | Le prompt compte moins de 4 caractères. | Écrivez une instruction plus longue ou laissez la boîte vide. |
| Un meta titre ou une meta description se termine brusquement lors d'une exécution cron | Le cron coupe les meta titres à 69 et les meta descriptions à 159 caractères. | Demandez un texte plus court dans le prompt. |
| Le produit affiche l'ancien texte après la génération | Le formulaire produit ouvert dans le navigateur a été enregistré par-dessus. | Rechargez la page du produit avant de cliquer sur Save. |
| Une ligne indique "skipped" | Le champ avait du texte et vous avez choisi Skip if filled. | Choisissez Replace pour écraser. |
| Le même brief est utilisé pour deux champs | La boîte Instruction contient encore le brief précédent. | Videz la boîte avant d'appuyer sur un autre champ. |
| Name ou Additional description reçoit un texte de type description dans Generate – Categories | Le prompt vide utilise le brief de description pour ces deux champs. | Saisissez votre propre prompt. |
| "Error! This log entry has no previous value to restore." | La ligne n'a conservé aucun ancien texte, ou la liste a été vidée. | Le module ne peut pas récupérer l'ancien texte. |
| "Error! This PrestaShop version does not support the category Additional Description field." | PrestaShop ancien. | Ignorez ce champ. |

### 5.4 Photos et New product

| Symptôme | Cause | Que faire |
|---|---|---|
| L'onglet Photos indique que le chercheur est désactivé | **AI Image Finder** est Disabled. | Activez-le dans Settings – General ou Images et rechargez la page du produit. |
| "No photos were found on the suggested pages." | Les pages suggérées n'ont pas de photos exploitables. | Cliquez à nouveau sur **Find pages** ou ajoutez les photos à la main. |
| "The photos could not be added." | Le serveur n'a pas pu les télécharger. | Choisissez d'autres photos. |
| "Failed to parse AI response. Please try again." | Le modèle a renvoyé des données que le module ne peut pas lire. | Cliquez à nouveau sur **Generate data** ou augmentez **Max Tokens**. |
| "Generate the product first." | **Create product** a été cliqué avant **Generate data**. | Générez d'abord. |
| "Prompt is required" | **What is the product?** est vide. | Décrivez le produit. |

### 5.5 Cron

| Symptôme | Cause | Que faire |
|---|---|---|
| L'adresse répond mais rien ne change | **Enable Debug** est sur Yes. | Mettez No et enregistrez. |
| L'adresse indique que la fonction est désactivée | **Enable Cron Feature** est sur No. | Mettez Yes. |
| Le secret a changé tout seul | Un secret de moins de 24 caractères a été remplacé. | Copiez le nouveau secret depuis le formulaire et mettez à jour le planificateur. |
| Les mêmes produits sont réécrits à chaque fois | **Product Categories** est coché (voir la section 3.12). | Laissez l'arborescence des catégories vide et utilisez **Product ID list**. |
| Le cron utilise le mauvais modèle | Le formulaire affichait le modèle le plus récent et ce choix a été enregistré. | Choisissez le bon **Prompt Template** et enregistrez. |
| "Generate Token" ne fait rien | Le script du bouton n'est pas livré dans cette version. | Saisissez vous-même le nouveau secret. |
| "Command:" dans le formulaire n'affiche aucun secret | Il n'affiche que l'adresse simple. | Construisez l'adresse comme à la section 3.12. |
| L'adresse se termine par un dépassement de délai | Trop d'éléments par appel. | Diminuez **Product to update**. |
| Tout est retraité après un moment | **Clear list** dans History a supprimé le journal qui marque les éléments terminés. | Ne videz pas History pendant qu'un cron tourne, ou utilisez **Product ID list**. |

### 5.6 Textes qui mentionnent OpenAI ou ChatGPT

Le module a été conçu à partir d'un module antérieur pour un autre fournisseur d'IA. Quelques textes affichent encore l'ancien nom. Ils ne changent rien au fonctionnement du module.

| Où | Ce que vous voyez | Signification |
|---|---|---|
| Settings – Mistral | L'exemple de nom de modèle dans le champ d'ajout est un nom GPT ; les messages "OpenAi Settings Updated" et "OpenAi Model field is invalid!". | Seulement des exemples et des formulations. Saisissez un nom de modèle Mistral. |
| Generate – Products | "OpenAi content" dans **Update only**. | Désigne le contenu de ce module. |
| Generate pages | Bouton **Module settings**. | Un ancien raccourci qui n'ouvre pas ce module. Utilisez la barre de menu. |
| History | Le fournisseur affiche "openai". | Simple étiquette. |

## 6. Pour le développeur

### 6.1 Vue d'ensemble

| Élément | Valeur |
|---|---|
| Nom du module | `myaimistral` |
| Nom affiché | My AI Mistral - AI content generation |
| Version | 1.0.0 |
| Classe principale | `myaimistral` (`myaimistral.php`) |
| PrestaShop | 1.6 à 9.99.99 |
| PHP | 7.0.0 ou plus récent (vérifié à l'installation, constante `MIN_PHP_VERSION`) |
| Base de l'API | `https://api.mistral.ai/v1` (`/chat/completions`, `/models`) |
| Préfixe de configuration | `MYPRESTA_MYAIMISTRAL_` |
| Tables | `PREFIX_myaimistral_prompt`, `PREFIX_myaimistral_log` |
| Préfixe CSS | `.mam-` |
| Paramètres d'URL | `mam_tab`, `mam_sub`, `mcg_preset`, `mam_from`, `mam_to` et `stats_*` sur History |

Dossiers : `controllers/admin`, `controllers/front`, `src` (classes autochargées `OpenAIService` et `Studio` dans l'espace de noms `MyAIMistral`), `lib` (vérificateur de mises à jour, aide de section, compatibilité PrestaShop 9), `views/templates`, `views/js`, `views/css`, `translations`.

Le module n'a ni overrides ni templates de front. L'aide des champs est écrite avec le helper `fieldHelp($does,$how,$effect)`, qui construit le texte "What it does / How to configure / Effect" de chaque `desc` de HelperForm.

### 6.2 Contrôleurs d'administration, hooks et routage

| Classe du contrôleur | Nom de l'onglet | Objectif |
|---|---|---|
| `AdminMyAIMistralMain` | AI Content Generator (menu entry) | Redirige vers `AdminModules&configure=myaimistral`. |
| `AdminMyAIMistral` | Mass Content Creator | Pages Generate (produits et catégories). |
| `AdminMyAIMistralProductCreator` | AI Product Creator | New product. |
| `AdminMyAIMistralSettings` | Module Settings | Point d'entrée des réglages. |
| `AdminMyAIMistralCron` | Cron Job Settings | Formulaires cron. |
| `AdminMyAIMistralUsage` | Module Log and Usage | History. |
| `AdminMyAIMistralImageFinder` | AI Image Finder | Page Images et actions photo `searchImages`, `extractImages`, `saveImages`. |

Les contrôleurs d'administration redirigent vers `AdminHome` lorsque le module est inactif.

Hooks enregistrés à l'installation : `displayBackOfficeHeader` (ressources et valeurs `Media::addJsDef` telles que `myaimistralField`, `myaimistralAdminLink`, `mamHelpLabels`), `displayBackOfficeTop` (icône de la barre supérieure et menu déroulant), `displayAdminProductsExtra` et `actionProductFormBuilderModifier` (onglet produit), `actionProductGridDataModifier` (liste des produits), `dashboardZoneTwo` (panneau du PrestaShop Dashboard), `displayAdminProductsMainStepLeftColumnMiddle` et `displayAdminProductsMainStepLeftColumnBottom` (vides), `displayHeader` et `displayFooter` (vides).

La navigation à l'intérieur de la page du module utilise des paramètres d'URL :

| Paramètre | Valeurs | Signification |
|---|---|---|
| `mam_tab` | dashboard, settings, updates (page du module) ; les autres onglets sont des contrôleurs | L'onglet principal de la page de configuration du module. |
| `mam_sub` | general, openai, studio, templates, playground (settings) ; products, categories (Generate) | Le sous-onglet. `openai` est l'onglet Mistral. |
| `mcg_preset` | today, 7, 30, 90, month, all | Période prédéfinie du Dashboard. |
| `mam_from`, `mam_to` | `YYYY-MM-DD` | Plage personnalisée du Dashboard. |
| `stats_preset`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_entity`, `stats_q` | voir History | Filtres de History. `clear_log` supprime le journal. |

### 6.3 Contrat du cron

```text
GET /module/myaimistral/cron?secret=SECRET&action=generateProductContent
GET /module/myaimistral/cron?secret=SECRET&action=generateCategoryContent
```

| Règle | Comportement |
|---|---|
| Interrupteur | `MYPRESTA_MYAIMISTRAL_ENABLE_CRON` ne doit pas valoir 0. |
| Authentification | `secret` doit être égal à `SECRET` ou `CAT_SECRET`. L'un ou l'autre fonctionne pour l'une ou l'autre action. |
| Remplacements facultatifs (produits) | `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `categories`, `productIds`. Ils remplacent les valeurs enregistrées pour cet appel uniquement. |
| Remplacements facultatifs (catégories) | `updatedField`, `categoryTarget`, `categoriesToUpdate`, `languageId`, `promptTemplateId`, `debug`. |
| Champs autorisés | Produits : name, description, description_short, meta_title, meta_description, tags. Catégories : name, description, meta_title, meta_description, additional_description. |
| Cibles | `pendingMistral` : aucune ligne de journal réussie pour l'élément. `pendingField` : aucune ligne de journal réussie de type `product_FIELD` ou `category_FIELD`. `emptyField` : le champ est vide dans la langue. Les lignes de statut `error` ne comptent pas. |
| Ordre et limite | `ORDER BY id ASC LIMIT n`. Les requêtes de catégories commencent après `PS_HOME_CATEGORY`. |
| Debug | Lorsque `debug` vaut 1, le SQL, les éléments sélectionnés et les prompts finaux sont affichés et rien n'est enregistré. Une valeur debug enregistrée à 1 arrête aussi l'enregistrement planifié. |
| Troncature | name 128, description courte 799, meta titre 69, meta description 159. Les tags passent par `Tag::addTags`. |
| Secrets | `ensureLongSecrets()` remplace les secrets de moins de 24 caractères. |
| Journal | Chaque élément enregistré écrit une ligne avec `method` `cron` et l'ancienne et la nouvelle valeur. |

Le filtre de catégories du cron des produits est construit comme `... AND p.id_product IN (...) OR p.id_category_default IN (...)` sans parenthèses, de sorte que les produits dont la catégorie par défaut est cochée contournent les autres conditions. Le filtre de Generate – Products utilise des parenthèses et n'est pas concerné.

### 6.4 Contrôleur AJAX

`/module/myaimistral/ajax` est un contrôleur de module front. Chaque appel porte `secret_token` (la valeur `TOKEN`) et répond en JSON `{status, msg, date}`.

| Action | Objectif |
|---|---|
| `initiatePrompt` | Playground et barre supérieure. Peut porter `id_category`, `id_cms` ou `id_manufacturer` pour remplacer `{category_*}`, `{cms_title}`, `{brand_name}`, `{brand_description}`, `{brand_short_description}`. |
| `updateProduct` | Génère un champ d'un produit. Comportements : `replace`, `keep`, `keep_top`, `keep_end`, `single_product` (sans enregistrement). `keep` répond avec le statut `skipped`. |
| `updateCategory` | La même chose pour les catégories (`single_category` n'enregistre rien). |
| `generateSeoPack` | Écrit le nom, les descriptions et les champs meta en une seule requête. |
| `generateAltTexts` | Écrit les textes alternatifs des images. Pas de bouton dans l'interface. |
| `initiateProductRestore` | Restaure une valeur précédente depuis une ligne de journal. |
| `updateSettings` | Enregistre Max Tokens, Temperature, Top P et les pénalités. |

Le jeton est imprimé dans les pages du back-office et le contrôleur ne vérifie pas la session d'un employé. Traitez le jeton comme un secret.

`Studio::gate()` applique les règles de la maison, le budget mensuel (compte les lignes qui ne sont pas des erreurs) et la vérification des mots interdits. `OpenAIService` appelle Mistral avec cURL, maintient le délai d'attente entre 10 et 600 secondes, réessaie jusqu'à six fois sans les paramètres que l'API rejette (mémorisés dans `MODEL_CAPS`) et assouplit la vérification SSL uniquement sur localhost. Le contrôleur ajax prolonge le `max_execution_time` de PHP pour qu'il corresponde au délai d'attente.

### 6.5 Clés de configuration

Toutes les clés commencent par `MYPRESTA_MYAIMISTRAL_`.

| Suffixe de clé | Par défaut | Objectif |
|---|---|---|
| `LIVE_MODE` | 0 | Live mode. |
| `DEBUG_MODE` | 0 | Debug mode. |
| `TOPCTA` | 1 | Admin Top Bar CTA. |
| `PRODUCT` | 1 | Product edit page Form. |
| `PRODUCT_LOG` | 1 | Product Edit History. |
| `TOKEN` | aléatoire | Secret AJAX. |
| `SECRET` | aléatoire | Secret du cron produits. |
| `CAT_SECRET` | aléatoire | Secret du cron catégories. |
| `API_KEY` | un seul espace | Clé Mistral. |
| `MODEL` | mistral-small-latest | Modèle actif. |
| `EXTRA_MODELS` | vide | Modèles ajoutés par le marchand, un par ligne. |
| `MODEL_CAPS` | vide | Paramètres rejetés par modèle. |
| `TEMPERATURE` | 0.7 | Température d'échantillonnage. |
| `MAX_TOKENS` | 3200 | Limite de réponse. |
| `TOP_P` | 1 | Top P. |
| `FREQ_PEN`, `PRES_PEN` | 0 | Pénalités. |
| `TIMEOUT` | 120 | Secondes, de 10 à 600. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | vide | Textes de Studio. |
| `BUDGET` | 0 | Limite mensuelle de requêtes. |
| `QUALITY` | 1 | Vérification des mots interdits. |
| `IMAGEFINDER_ENABLE` | 1 | Interrupteur du chercheur de photos. |
| `IMAGEFINDER_PROMPT` | texte intégré | Instruction du chercheur de photos. |
| `ENABLE_CRON` | 0 | Interrupteur du cron. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 6 | Rappel d'intervalle (6 correspond à Every Hour). |
| `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `productIdsList`, `categories` | description, pendingMistral, 5, langue par défaut de la boutique, vide, 0, vide, vide | Formulaire du cron produits. |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catlanguageId`, `catpromptTemplateId`, `catdebug` | description, pendingMistral, 5, langue par défaut de la boutique, vide, 0 | Formulaire du cron catégories. |

Les filtres de la page Generate utilisent le même préfixe : `CATEGORIES`, `BRANDS`, `STATUS`, `STOCK`, `HISTORY`, `PROD_IDS`, `PROD_REF`, `PROD_DATE_FROM`, `PROD_DATE_TO`, `PROD_MIN_ID`, `PROD_MAX_ID`, `PROD_LIMIT`, `CATEGORIESC`, ainsi que `FIELD`, `LANGUAGE`, `CONTENT`, `DELAY` et `EXISTING` de l'ancien formulaire des catégories. Ils sont écrits à chaque requête du contrôleur Generate et ne sont pas supprimés à la désinstallation. La valeur de Product IDs est insérée dans la requête telle que saisie, espaces retirés ; réservez donc cette page aux employés de confiance.

### 6.6 Base de données

| Table | Colonnes | Remarques |
|---|---|---|
| `myaimistral_prompt` | `id_prompt`, `status`, `title`, `prompt`, `date_generated` | 16 lignes à l'installation. |
| `myaimistral_log` | `id_log`, `type`, `method`, `status`, `ai_service`, `model`, `prompt`, `reply`, `error_message`, `http_code`, `duration_ms`, `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, valeurs de champs `old_*` et `new_*`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `date_updated` | Les colonnes de tokens sont ajoutées à la demande par `ensureUsageColumns()`. Les deux tables sont supprimées à la désinstallation. |

Les valeurs de `type` sont par exemple `general`, `singleCategory`, `singleCMS`, `singleBrand`, `product_name`, `product_description`, `product_description_short`, `product_meta_title`, `product_meta_description`, `product_tags`, `category_description` et `error`. Les valeurs de `method` sont `initiatePrompt`, `updateProduct`, `updateCategory` et `cron`.

### 6.7 Briques du front-end

| Élément | Remarques |
|---|---|
| Classes | Les styles d'administration commencent par `.mam-` (navigation, dashboard, cartes, chips, tuiles, tiroir d'aide). Le panneau produit utilise `.myaimistral-ui` et les boutons de champ utilisent `.myaimistral-field-btn`. |
| `views/js/back.js` | Playground, boutons du panneau produit, exécuteur en masse, New product, restore, onglets, menu déroulant de la barre supérieure. Attributs de données du panneau produit : `data-myaimistral`, `data-myaimistral-product`, `data-mam-fill`, `data-mam-for`. |
| `views/js/product-fields.js` | Les boutons de champ sur les pages produit et catégorie. Lit `window.myaimistralField`. |
| `views/js/image-finder.js` | Recherche et import de photos. |
| `views/js/admin-products-bulk.js` | Le bouton dans la liste des produits. Lit `myaimistralAdminLink`. |
| Styles | `back.css`, `admin-nav.css`, `stats.css`. |

### 6.8 Étendre

- Nouveaux modèles de prompt : insérez une ligne dans `myaimistral_prompt` avec `status` 1.
- Nouveaux marqueurs : étendez les constructeurs de prompts de produit et de catégorie dans `controllers/front/ajax.php` et dans `controllers/front/cron.php`. Les marqueurs de la boutique sont traités dans `applyShopShortcodes()`.
- Nouveaux modèles : ajoutez-les dans Settings – Mistral, ou ajoutez le nom à la liste intégrée dans `myaimistral.php`.
- Autre fournisseur : modifiez l'URL de base et le corps de la requête dans `src/OpenAIService.php`. Tout le reste ne dialogue qu'avec cette classe.
- Traductions : utilisez `$this->l()` dans le module et `trans()` dans les contrôleurs sous PrestaShop 8 et 9. Les chaînes se trouvent dans `translations/`.

## 7. Aide

Page du produit : https://mypresta.eu/modules/administration-tools/my-ai-mistral.html

Pour obtenir de l'aide sur le module, connectez-vous à mypresta.eu, ouvrez **contact** et choisissez **Support for paid modules**. Décrivez le problème, vos versions de PrestaShop et de PHP et le texte du message que vous voyez. N'envoyez jamais la clé d'API ni un secret de cron.
