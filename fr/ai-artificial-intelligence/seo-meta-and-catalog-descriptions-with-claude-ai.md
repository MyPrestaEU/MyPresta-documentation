---
title: My AI Claude - AI content generation - documentation et manuel d'utilisation
description: Guide de configuration, d'utilisation quotidienne et de dépannage pour les propriétaires de boutique qui ont déjà installé My AI Claude et veulent le relier à leur compte Anthropic Claude et l'utiliser sur leur catalogue.
sidebar:
  label: My AI Claude - AI content generation - documentation et manuel d'utilisation
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module SEO meta and catalog descriptions with Claude AI sur MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-claude-ai.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-claude-ai/)
>
> ---


## 1. Prérequis

My AI Claude fonctionne dans le back-office de PrestaShop et envoie vos prompts à Anthropic Claude. Il a besoin des éléments suivants.

| Élément | Exigence | Remarques |
|---|---|---|
| PrestaShop | 1.6, 1.7, 8 et 9 (de 1.6 à 9.99.99) | Fonctionne dans la page produit classique et dans la nouvelle. |
| PHP | 7.0 ou plus récent | Avec une version inférieure, l'installation s'arrête et affiche un message avec la version PHP de votre serveur. |
| Extensions PHP | cURL, JSON, mbstring, DOM, fileinfo, GD | Standard chez la plupart des hébergeurs. cURL dialogue avec Claude, DOM lit la page source dans **New product**, GD redimensionne les photos importées. |
| Réglage PHP | `allow_url_fopen` activé | Nécessaire uniquement pour **New product** (lecture de l'adresse de la page source). |
| Autres modules | Aucun | Aucun autre module n'a besoin d'être installé. |
| Base de données | Aucune exigence supplémentaire | Le module utilise la version de MySQL ou MariaDB sur laquelle PrestaShop fonctionne déjà. |
| Compte hors boutique | Un compte Anthropic avec accès à l'API et du crédit | Créez la clé sur https://console.anthropic.com/settings/keys. Chaque génération est facturée par Anthropic selon les tokens utilisés. |
| Réseau | Le serveur peut ouvrir des connexions HTTPS | La boutique contacte `api.anthropic.com` à chaque génération. La vérification des mises à jour contacte le serveur de MyPresta.eu. La fonction Images ouvre des pages web publiques. |
| Navigateur | JavaScript activé | Tous les boutons du module sont des scripts exécutés dans le back-office. |

**Temps et mémoire.** Une génération correspond à une requête vers Claude et dure de quelques secondes à environ une minute. La limite d'attente se règle dans **Settings, General** sous **API timeout (seconds)** (120 secondes au départ, toute valeur de 10 à 600). Réglez la limite de temps PHP de votre serveur au-dessus de cette valeur. Une exécution en masse envoie une requête par produit, par champ et par langue, l'une après l'autre, et ne fonctionne que tant que sa page reste ouverte dans le navigateur. Le module ne lance aucun processus en arrière-plan et n'a besoin d'aucune mémoire supplémentaire par rapport à une page normale du back-office.

## 2. Installation

### 2.1 Téléverser et installer

1. Ouvrez **Modules → Module Manager** (PrestaShop 1.6 : **Modules and Services**).
2. Cliquez sur **Upload a module** (PrestaShop 1.6 : **Add a new module**).
3. Sélectionnez le fichier ZIP du module et attendez la fin du téléversement.
4. Cliquez sur **Install** lorsque PrestaShop le propose.
5. Attendez la confirmation. L'installation crée l'entrée de menu, deux tables de base de données et les modèles de prompt prêts à l'emploi (voir 3.6).

L'installateur ne vide pas le cache. Si l'entrée de menu n'apparaît pas, ouvrez **Advanced Parameters → Performance**, cliquez sur **Clear cache** et rechargez la page.

Après l'installation, le module ne fait rien tant que vous n'avez pas saisi votre clé Anthropic. Passez au chapitre 3, section 3.1.

### 2.2 Où le module apparaît

Le module ajoute une entrée de menu nommée **AI Content Generator** sous **Modules**. Cliquez dessus pour ouvrir le module sur son **Dashboard**. Tous les autres écrans sont accessibles depuis le menu horizontal en haut de la page du module :

**Dashboard**, **Settings** (avec les sous-pages **General**, **Claude**, **Studio**, **Prompt templates**, **Playground**), **Generate**, **New product**, **Cron**, **History**, **Images**, **Updates**.

Le module ajoute aussi un panneau **Modules → My AI Claude** sur chaque page produit, de petits boutons **Generate with AI** à côté des champs de texte dans les formulaires produit et catégorie, un raccourci dans la barre supérieure du back-office et un bouton **My AI Claude** au-dessus de la liste des produits. Les sections 3.16 et 3.17 décrivent chacun d'eux.

Si un employé qui n'est pas super-administrateur ne peut pas ouvrir l'entrée de menu, donnez au profil de cet employé l'accès aux écrans du module dans **Advanced Parameters → Team → Permissions**.

### 2.3 Désactivation et désinstallation

- **Désactivez** le module dans le Module Manager pour masquer ses écrans. Tant qu'il est désactivé, toute adresse du module vous renvoie au tableau de bord principal de PrestaShop. Toutes les données sont conservées.
- **Désinstaller** supprime les entrées de menu, la table des modèles de prompt, la table de l'historique des générations et tous les réglages du module (clé API, modèle, règles Studio, réglages cron et secrets cron). L'History disparaît avec ses points de restauration, tout comme les chiffres du Dashboard.
- La désinstallation laisse tout ce que le module a déjà écrit dans votre boutique : textes des produits et des catégories, photos importées et produits créés avec **New product**.
- La désinstallation laisse aussi quelques choix d'écran enregistrés des filtres **Generate** et les réglages de la vérification des mises à jour de MyPresta.
- **Réinstaller** repart de zéro : la clé API est vide, les secrets sont nouveaux (les adresses cron changent, mettez donc à jour le planificateur de votre serveur), l'History est vide et les modèles prêts à l'emploi retrouvent leur formulation d'origine.

## 3. Configuration et travail quotidien dans le back-office

### 3.1 Tout le processus, étape par étape

1. Créez une clé API Anthropic sur https://console.anthropic.com/settings/keys et vérifiez que le compte dispose de crédit.
2. Ouvrez **AI Content Generator → Settings → Claude**. Collez la clé dans **Anthropic Claude API KEY**, choisissez un **Model** et cliquez sur **Save**.
3. Ouvrez **Settings → Playground**, saisissez une courte question et cliquez sur **Generate**. Une réponse sur la page confirme que la clé fonctionne.
4. Facultatif : ouvrez **Settings → Studio** et décrivez la voix de votre marque, votre public, le ton, les termes préférés et les mots interdits. Ces règles sont ajoutées à chaque génération.
5. Ouvrez **Settings → Prompt templates** et lisez les modèles prêts à l'emploi. Modifiez ceux que vous voulez garder, désactivez les autres.
6. Ouvrez un produit, allez dans **Modules → My AI Claude**, appuyez sur **Try** sur la carte de description pour lire un résultat sans modifier le produit, puis appuyez sur **Fill** pour l'écrire dans le produit.
7. Ouvrez **History** et vérifiez l'entrée. Appuyez sur **Restore** dans le panneau du produit si vous voulez retrouver l'ancien texte.
8. Pour de nombreux produits, ouvrez **Generate → Products**, filtrez la liste, écrivez ou choisissez un prompt et cliquez sur **Run on the list below**. Testez d'abord sur une petite liste.
9. Pour des exécutions automatiques par le serveur, configurez **Cron** (section 3.12).
10. Surveillez le coût et le volume sur **Dashboard** et **History**. Définissez un **Monthly generation budget** dans **Studio** pour plafonner l'utilisation.

### 3.2 Ouvrir le module et s'y repérer

Cliquez sur **AI Content Generator** sous **Modules**. Le menu supérieur du module contient **Dashboard**, **Settings**, **Generate**, **New product**, **Cron**, **History**, **Images** et **Updates**. Certaines pages ont une deuxième ligne : **Settings** propose **General**, **Claude**, **Studio**, **Prompt templates** et **Playground** ; **Generate** propose **Products** et **Categories**.

Les noms en gras sont les libellés du back-office en anglais, et les captures d'écran de ce manuel montrent le back-office en anglais. Si votre back-office est dans une autre langue, cherchez les entrées correspondantes au même endroit.

Chaque page du module comporte un bouton rond **Help** en bas à droite. Il ouvre un panneau latéral avec une courte explication de la page où vous vous trouvez.

### 3.3 Dashboard

![My AI Claude dashboard with request and token cards and three charts](https://mypresta.eu/docs/images/docs/myaiclaude-dashboard.webp)

Le Dashboard montre dans quelle mesure le module a été utilisé. La première ligne indique le service et le modèle actifs.

Choisissez la période avec l'un des boutons **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time**, ou saisissez vos propres dates dans **From** et **To** puis cliquez sur **Apply**. La page s'ouvre sur **30 days**.

| Élément | Signification | Remarques |
|---|---|---|
| Requests | Nombre d'appels faits à Claude sur la période | Compte chaque ligne de l'History : exécutions en masse, panneau produit, Playground, barre supérieure, cron. |
| Success | Appels qui ont renvoyé du texte | |
| Errors | Appels qui ont échoué | La raison est enregistrée dans la ligne de l'History. |
| Tokens sent | Tokens de vos prompts | Les tokens sont l'unité selon laquelle Anthropic facture. |
| Tokens received | Tokens des réponses | |
| Requests and errors | Graphique par jour | Les longues périodes sont regroupées par semaine. |
| Tokens sent and received | Graphique par jour | |
| Requests by model | Graphique | Montre quels modèles ont fait le travail. |

Le module ajoute aussi un bloc au tableau de bord principal de PrestaShop. Les chiffres complets et les graphiques sont sur cette page.

### 3.4 Settings – General

![Settings General page with switches and the image search prompt](https://mypresta.eu/docs/images/docs/myaiclaude-settings-general.webp)

Ouvrez **Settings → General**, modifiez les champs et cliquez sur **Save**. Le message **Settings Updated** le confirme.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| Live mode | No | Une étiquette pour vous qui indique que la boutique est en production. Elle n'active ni ne désactive aucune fonction. |
| Debug mode | No | Écrit dans le journal de PrestaShop (**Advanced Parameters → Logs**) des lignes techniques sur les appels échoués. Activez-le quand le support demande des détails, puis désactivez-le. |
| API timeout (seconds) | 120 | Le temps pendant lequel la boutique attend Claude avant d'abandonner. Les valeurs inférieures à 10 deviennent 10, celles supérieures à 600 deviennent 600, une valeur vide ou invalide devient 120. Augmentez-le pour les longues descriptions. |
| Product Edit History | Yes | Affiche l'onglet **History** dans le panneau produit et permet d'y restaurer un texte antérieur. Désactivé, l'onglet disparaît. Les générations restent enregistrées dans l'History principale. |
| Admin Top Bar CTA | Yes | Affiche la petite icône My AI Claude dans la barre supérieure du back-office (section 3.17). |
| Product edit page Form | Yes | Affiche le panneau **Modules → My AI Claude** sur la page produit. Si cet interrupteur et **Product Edit History** sont tous deux désactivés, le panneau est vide. |
| AI Image Finder | Yes | Autorise l'onglet **Photos** sur la page produit. Le même interrupteur se trouve sur la page **Images**. |
| AI Image Search Prompt | Texte prêt à l'emploi | L'instruction utilisée pour trouver des pages contenant des photos d'un produit. Le même champ se trouve sur la page **Images** (section 3.14). |

### 3.5 Settings – Claude

![Settings Claude page with API key, model and sampling fields](https://mypresta.eu/docs/images/docs/myaiclaude-settings-claude.webp)

Cette page relie la boutique à votre compte Claude. À la première ouverture, le module peut afficher un avis indiquant que des espaces ont été supprimés du champ de la clé. C'est normal.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| Anthropic Claude API KEY | Vide | Le secret qui permet à la boutique d'appeler votre compte Claude. Collez la clé depuis https://console.anthropic.com/settings/keys. Les espaces sont supprimés à l'enregistrement. Laissez le champ intact pour conserver la clé enregistrée. L'absence de clé fait échouer chaque appel, et l'erreur apparaît dans **History**. |
| Model | claude-sonnet-4-5 | Le modèle Claude qui écrit le texte. Noms intégrés : claude-sonnet-4-5, claude-opus-4-5, claude-haiku-4-5, claude-3-5-sonnet-latest, claude-3-5-haiku-latest, claude-3-opus-latest, plus les noms que vous avez ajoutés. Un modèle que votre clé ne peut pas utiliser renvoie une erreur au lieu de texte. |
| Add a Claude model | Vide | Saisissez le nom exact du modèle de votre compte Claude et cliquez sur **Add model**. Le nom apparaît dans la liste **Model**. À côté de chaque nom ajouté se trouve un lien **Remove**. Les noms intégrés ne peuvent pas être supprimés. |
| Max Tokens | 3200 | Limite supérieure de la longueur de la réponse, comptée en tokens. Utilisez environ 256 pour une méta-description et 1000 ou plus pour une description complète. Une valeur trop faible coupe la réponse. Une valeur vide est remplacée par 256. |
| Temperature | 0.7 | Le degré de variété de la formulation, de 0 à 1. Plus bas est plus régulier, plus haut est plus créatif. Saisissez 0.1 pour le style le plus régulier, car un simple 0 est lu comme la valeur de départ 0.7. |
| Top P | 1 | Enregistré avec les autres champs, mais My AI Claude ne l'envoie pas à Claude. Le modifier n'a aucun effet. |
| Frequency Penalty Value | 0 | Enregistré, mais non envoyé à Claude. Le modifier n'a aucun effet. |
| Presence Penalty Value | 0 | Enregistré, mais non envoyé à Claude. Le modifier n'a aucun effet. |

Cliquez sur **Save** en bas du formulaire. Une confirmation apparaît lorsque les valeurs sont valides. Le message **Anthropic Claude API KEY field is invalid!** signifie que le champ de la clé est vide et qu'aucune clé n'est encore enregistrée.

Si un modèle refuse l'un des réglages (par exemple la température), le module retire ce réglage, réessaie et s'en souvient pour ce modèle. Vous n'avez rien à faire.

Les valeurs d'échantillonnage (Max Tokens, Temperature) sont utilisées par les exécutions en masse, le panneau produit, le Playground, la barre supérieure et le cron. **Images** utilise ses propres valeurs fixes.

### 3.6 Settings – Prompt templates

![Prompt templates list with title, prompt, status and actions](https://mypresta.eu/docs/images/docs/myaiclaude-settings-templates.webp)

Un modèle est une instruction enregistrée que vous pouvez choisir dans les exécutions en masse, le panneau produit, la barre supérieure et le cron. L'installation crée 16 modèles, tous activés.

| Modèle | Usage | Remarques |
|---|---|---|
| Product name 1, Product name 2 | Noms de produit plus courts ou meilleurs | Name 2 utilise la marque et la catégorie par défaut. |
| Product description 1 to 6 | Descriptions de produit | Description 1 construit une mise en page HTML avec des titres et demande des fautes d'orthographe volontaires. Supprimez cette phrase avant de l'utiliser. Description 3 demande aussi des idées de H1, des mots-clés, un méta-titre et une méta-description, qui se retrouvent tous dans le champ de description. |
| Product description 7 - using product images | Description avec photos intégrées | Utilise les liens des images du produit. |
| Product meta title 1 to 3 | Méta-titres | Meta title 1 demande la langue anglaise et 60 caractères. |
| Product meta description 1 to 3 | Méta-descriptions | Meta description 1 demande la langue anglaise et 160 caractères. Les Meta descriptions 2 et 3 sont identiques et mentionnent une montre connectée, réécrivez-les donc pour vos propres produits. |
| Product tags | Cinq étiquettes sur une ligne | Demande la langue anglaise. |

Plusieurs modèles demandent l'anglais dans le texte lui-même. Si vous vendez dans une autre langue, modifiez ces modèles et supprimez la ligne.

La liste affiche **ID**, **Title**, **Prompt**, **Status** (cliquez sur l'interrupteur pour activer ou désactiver), **Timestamp** et les actions de ligne pour modifier ou supprimer. Sélectionnez plusieurs lignes et utilisez l'action groupée **Delete** (la question **Are you sure you want to delete the selected prompts?** demande confirmation). Les modèles les plus récents sont en haut et la liste affiche 50 lignes par page.

Pour créer un modèle, cliquez sur le bouton **new** de la barre d'outils. Pour en modifier un, cliquez sur l'action de modification de sa ligne.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| Status | Enabled pour un nouveau modèle | Seuls les modèles activés apparaissent dans les sélecteurs du module. |
| Prompt title | Vide (obligatoire) | Le nom que vous voyez dans les sélecteurs et dans la liste. |
| Prompt content | Vide (obligatoire) | L'instruction envoyée à Claude. Vous pouvez utiliser des espaces réservés tels que `{product_name}` (section 3.18). Les guillemets doubles sont remplacés par des guillemets simples à l'enregistrement. |

Cliquez sur **Save Prompt** pour enregistrer le modèle. Les messages sont **Prompt template successfully added!** et **Prompt template successfully updated!**. Un modèle supprimé affiche **Prompt template removed.**. Cliquez sur **Go Back to Module Settings** pour quitter le formulaire sans enregistrer.

Un modèle dit à Claude quoi écrire. Le module ajoute aussi les règles de **Studio** et la langue de l'exécution (la section 3.8 décrit les règles Studio).

### 3.7 Settings – Playground

![Playground with a text box and the Generate button](https://mypresta.eu/docs/images/docs/myaiclaude-settings-playground.webp)

Le Playground est une zone de texte libre pour essayer un prompt. Saisissez votre prompt et cliquez sur **Generate**. La réponse apparaît sur la page. Rien n'est écrit dans un produit ni dans une catégorie.

L'appel est enregistré dans l'History comme une génération générale ; il compte donc pour le Dashboard et pour le budget mensuel. Utilisez le Playground pour vérifier la clé API, le modèle et l'effet des règles Studio.

### 3.8 Settings – Studio

![Studio page with brand voice, audience, tone, glossary and forbidden words](https://mypresta.eu/docs/images/docs/myaiclaude-settings-studio.webp)

Studio contient les règles qui sont ajoutées à chaque génération : exécutions en masse, panneau produit, catégories, cron, Playground et barre supérieure. Même avec tous les champs Studio vides, le module indique à Claude dans quelle langue écrire (la langue de cette exécution).

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| Brand voice | Vide | Décrit la façon dont votre boutique s'exprime. Claude la suit dans chaque texte. |
| Audience | Vide | Décrit le client pour lequel vous écrivez. |
| Tone | Vide | L'ambiance du texte, par exemple chaleureux, technique ou neutre. |
| Glossary | Vide | Termes que Claude doit conserver exactement comme vous les écrivez. Un par ligne. |
| Forbidden words | Vide | Mots que Claude ne doit pas utiliser. Un par ligne. Claude reçoit l'instruction de ne pas les employer, et lorsque le quality gate est activé, une réponse qui en contient encore un est rejetée. |
| Monthly generation budget | 0 | Nombre maximal de générations réussies dans le mois civil en cours. 0 signifie aucune limite. Lorsque le nombre est atteint, les nouveaux appels s'arrêtent avec le message **Monthly generation budget reached. Raise it in the studio settings or wait until next month.** Les appels échoués ne sont pas comptés. |
| Quality gate | Yes | Vérifie chaque réponse à la recherche de mots interdits avant l'enregistrement. Une réponse rejetée n'est pas écrite et affiche **The reply was rejected because it contains a forbidden word from the studio settings.** |

Cliquez sur **Save studio**. Le message **Studio settings saved.** le confirme.

Le budget compte toutes les lignes réussies de l'History dans le mois : exécutions en masse, panneau produit (**Try** inclus), Playground, barre supérieure et cron. **New product** n'est pas compté.

### 3.9 Generate – Products

![Generate Products filter form](https://mypresta.eu/docs/images/docs/myaiclaude-generate-products.webp)

Ouvrez **Generate → Products**. La page fonctionne en deux étapes : d'abord un filtre choisit les produits, puis un panneau lance Claude sur cette liste.

**Étape 1 – le filtre.** Remplissez les champs et cliquez sur **Go to next step**. Le formulaire s'ouvre toujours avec les valeurs indiquées ci-dessous.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| Product Categories | Rien de coché | Cochez des catégories pour limiter la liste aux produits qu'elles contiennent. Vide signifie toutes les catégories. |
| Brand | All | Limite la liste à une marque. |
| Product status | Active | Active, Disabled ou Both. |
| Product stock | All products | **Only in stock products** conserve les produits dont la quantité est supérieure à zéro. |
| Update only | Update all | Trois options : seulement les produits qui n'ont pas encore d'entrée dans l'History, seulement ceux qui en ont déjà une, ou tous les produits. Toute entrée compte, y compris les appels échoués et les exécutions **Try**. |
| Product IDs | Vide | Une liste d'ID de produits. |
| Product Reference | Vide | Limite la liste aux produits ayant cette référence. |
| Product Add Date From, Product Add Date To | Vide | Limite la liste selon la date de création du produit. |
| Minimum product ID, Maximum product ID | Vide | Limite la liste à une plage d'ID. |
| Product Limit | Vide | Le nombre maximal de produits dans la liste. |

**Étape 2 – le panneau Mass product generation.** Les produits correspondants apparaissent dans un tableau avec **ID**, **Reference** et **Result**. Au-dessus du tableau, vous réglez l'exécution.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| Template | Rien de choisi | Choisit un modèle activé et copie son texte dans la zone du prompt. Vous pouvez ensuite modifier le texte. |
| Prompt | Vide | L'instruction pour Claude, avec des espaces réservés tels que `{product_name}`. Lorsque la zone est vide, le module utilise une consigne intégrée pour chaque champ : une description HTML avec introduction et liste de caractéristiques, un court résumé en texte brut de moins de 400 caractères, un méta-titre d'environ 70 caractères et une méta-description d'environ 160 caractères. |
| What to generate | Descriptions | **Descriptions** (description longue et courte), **Meta title and meta description** ou **Descriptions and meta together**. |
| Existing text | Replace | **Replace**, **Skip if filled**, **Add above** ou **Add below**. |
| Languages | La langue actuelle cochée | Cochez chaque langue à rédiger. |

Cliquez sur **Run on the list below**. Une ligne d'état indique la progression (par exemple `3 / 40` avec le nom du champ) et se termine par **Finished N products.** Chaque ligne affiche le champ, le résultat et le message, par exemple **Content successfully generated and updated to product.** ou **Product skipped.**

Règles d'une exécution :

- L'exécution envoie une requête par produit, par champ et par langue, l'une après l'autre. Comptez les requêtes avant de commencer, car chacune est facturée.
- Gardez la page ouverte. La fermer ou la recharger arrête l'exécution. Les produits déjà écrits restent écrits.
- Un échec sur une ligne n'arrête pas les autres. La raison figure dans la ligne et dans **History**.
- Limites à l'enregistrement : nom du produit 128 caractères, description courte 800, méta-titre 69, méta-description 159. Un texte plus long est tronqué.
- Le texte est enregistré directement dans le produit. Utilisez le panneau produit (section 3.16) pour restaurer un texte antérieur.

### 3.10 Generate – Categories

![Generate Categories filter form](https://mypresta.eu/docs/images/docs/myaiclaude-generate-categories.webp)

Ouvrez **Generate → Categories**. Le premier formulaire comporte **Categories** (un arbre, vide signifie toutes) et **Category status** (Active, Disabled ou Both, Active au départ). Cliquez sur **Go to next step**. La liste peut inclure les catégories Root et Home, cochez donc les catégories voulues.

Sous le filtre apparaît le panneau **Run on the categories below** avec un tableau **ID** et **Result**.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| Prompt | Vide | L'instruction pour Claude. Utilisez des espaces réservés de catégorie tels que `{category_name}`, `{category_description}` et `{category_parent_name}`. Les espaces réservés de produit ne sont pas remplis ici. |
| Field | Description | **Description**, **Name**, **Meta title**, **Meta description** ou **Additional description**. |
| Existing text | Replace | **Replace** ou **Skip if filled**. |
| Language | La langue actuelle | Une langue par exécution. |

Cliquez sur **Run on the categories below**. Chaque ligne affiche le résultat, par exemple **Content successfully generated and updated to category.** ou **Category skipped.**

Sous le panneau, la page affiche un second formulaire nommé **Generate category content**. Son bouton ne lance pas d'exécution. Utilisez **Run on the categories below** et ignorez le second formulaire. Le bouton **Go Back to Category Filter** ramène au filtre.

Les limites à l'enregistrement sont les mêmes que pour les produits : nom 128 caractères, méta-titre 69, méta-description 159. Le champ **Additional description** n'existe que dans les versions de PrestaShop qui le possèdent. Sinon, la ligne affiche une erreur.

### 3.11 New product

![New product page with the product brief and the generated draft](https://mypresta.eu/docs/images/docs/myaiclaude-new-product.webp)

**New product** crée un produit complet à partir d'une courte description. Claude rédige un brouillon, vous le lisez, puis le module crée le produit dans votre catalogue.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| What is the product? | Vide | Décrivez le produit en quelques phrases : ce que c'est, à qui il s'adresse, ses principales caractéristiques. C'est le seul champ obligatoire. Le texte est tronqué à 8000 caractères. |
| Optional source URL | Vide | L'adresse d'une page consacrée au produit. Le module lit son titre, sa méta-description et son prix, et les transmet à Claude. |
| Language | La langue par défaut de la boutique | La langue du brouillon. |
| Default category ID | 2 | L'ID de la catégorie dans laquelle le produit est placé. 2 est la catégorie Home d'une boutique standard. |

1. Remplissez les champs et cliquez sur **Generate data**. Le brouillon apparaît sur la page sous forme d'un bloc de données (nom, descriptions, champs méta, étiquettes, caractéristiques, prix). Rien n'est encore enregistré.
2. Lisez le brouillon. S'il ne convient pas, modifiez la description et cliquez de nouveau sur **Generate data**.
3. Cliquez sur **Create product** seulement lorsque vous acceptez le brouillon. La page affiche alors **Product #** suivi du numéro du nouveau produit. Retrouvez le produit dans **Catalog → Products**.

Le nouveau produit est créé avec ces réglages : actif, disponible à la commande, prix affiché, visible dans le catalogue et la recherche, état neuf, la première règle de taxe de la boutique, un stock de 100 pièces et le prix du brouillon (0 si le brouillon n'en a pas). Claude renseigne aussi le nom, les descriptions, les champs méta, les étiquettes, les caractéristiques et la référence (32 caractères maximum). Ouvrez ensuite le produit, vérifiez le prix, la taxe, le stock et les photos, et ajoutez des photos avec l'onglet **Photos** du panneau produit.

Si aucune clé n'est enregistrée, la page affiche **Add an API key in the module settings first.** Cette page n'applique ni les règles Studio ni le budget mensuel, et ses appels n'apparaissent ni dans **History** ni sur le **Dashboard**.

### 3.12 Cron

![Cron page with enable switch, secret and product cron form](https://mypresta.eu/docs/images/docs/myaiclaude-cron.webp)

Le cron permet à votre serveur de générer du texte selon un calendrier sans que personne ne clique. La page construit l'adresse que le serveur doit ouvrir. Elle ne lance aucun planificateur. Vous créez la tâche planifiée chez votre hébergeur ou sur votre serveur, et chaque appel traite un lot puis s'arrête.

La page comporte deux formulaires : le cron des produits et le cron des catégories. Le formulaire des produits est décrit ci-dessous. Celui des catégories suit la même logique, avec son propre secret et ses propres réglages.

Sous l'introduction de chaque formulaire, la page affiche l'adresse du cron. L'adresse des produits ressemble à ceci : `https://your-shop/module/myaiclaude/cron?secret=...`. L'adresse des catégories se termine par `&entity=category`.

**Complétez l'adresse avant de l'utiliser.** Ajoutez `&action=generateProductContent` à la fin de l'adresse des produits et `&action=generateCategoryContent` à la fin de celle des catégories. Sans cela, l'adresse répond **Invalid action!** et ne fait rien.

Exemple pour les produits :

`https://your-shop/module/myaiclaude/cron?secret=YOUR_SECRET&action=generateProductContent`

L'adresse utilise les choix enregistrés dans le formulaire : champ, cible, nombre de produits, langue et modèle. Vous pouvez les remplacer dans l'adresse (la section 6.3 liste les paramètres).

**Formulaire du cron des produits**

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| Enable Cron Feature | No | Interrupteur principal des deux adresses cron (produits et catégories). Lorsqu'il est désactivé, l'adresse répond **Cron Job feature is disabled. You can enable it from the module settings.** |
| Cron Job Secret Token | Texte aléatoire | Le long mot de passe dans l'adresse. Sans le bon, l'adresse répond **The token does not exist or it's wrong!** Le bouton **Generate Token** ne fonctionne pas dans cette version (section 5.5). Saisissez votre propre secret d'au moins 24 lettres et chiffres, enregistrez et copiez la nouvelle adresse dans votre planificateur. |
| Update Field | description | Le champ unique écrit par cette adresse : name, description, description_short, meta_title, meta_description ou tags. Pour plusieurs champs, créez plusieurs tâches. |
| Selected Products | pendingClaude | **pendingClaude** prend les produits qui n'ont pas encore de génération My AI Claude réussie (n'importe quel champ). **pendingField** prend les produits sans génération réussie pour ce champ, ce qui vous permet de lancer une tâche pour la description et une autre pour le nom sur les mêmes produits. **emptyField** prend les produits dont le champ choisi est vide. |
| Product Categories | Rien de coché | Limite l'exécution aux produits des catégories cochées. |
| Product ID list | Vide | Uniquement ces ID de produits, séparés par des virgules. Les lettres sont supprimées à l'enregistrement. |
| Language | La langue par défaut de la boutique | La version linguistique qui est écrite. Les autres langues nécessitent leur propre tâche. |
| Product to update | 5 | Combien de produits un appel traite. Commencez avec 5 ou 10 pour qu'une réponse lente n'atteigne pas la limite de temps du serveur. L'appel suivant continue avec les produits qui correspondent encore. |
| Prompt Template | Rien d'enregistré | L'instruction enregistrée utilisée pour chaque produit de l'exécution. Choisissez-en une et cliquez sur **Save**. Sans modèle enregistré, l'adresse répond **All must include all mandatory parameters!** |
| Enable Debug | No | Lorsque vous ouvrez l'adresse dans un navigateur, affiche le plan, la requête de base de données et le prompt final, et n'enregistre rien. Désactivez-le avant que le planificateur n'utilise l'adresse. |
| CRON JOB interval | Every Hour | Une note pour vous sur le rythme de votre planificateur (de chaque minute à toutes les 6 heures). Elle ne planifie rien et ne modifie pas l'adresse. |
| Product Cron Job command | L'adresse | L'adresse du cron. Ajoutez la partie `&action=` comme décrit ci-dessus. |

Cliquez sur **Save** sous le formulaire. Le formulaire des catégories comporte les champs **Enable Debug**, **CRON JOB interval**, **Language**, **Prompt Template**, **Selected categories**, **Update Field** (name, description, meta_title, meta_description), **Categories to update** et le secret, ainsi que son propre bouton **Save**.

Ce que fait chaque appel :

- Il remplace le champ choisi. Le cron n'a pas d'option pour conserver ou ajouter du texte.
- Il applique les règles Studio et le budget mensuel. Lorsque le budget est atteint, l'appel répond **Error!Monthly generation budget reached.**
- Il écrit une ligne d'History pour chaque texte, ce qui permet de le restaurer ou de le relire.
- Les deux secrets ouvrent les deux actions. Le cron reste désactivé tant que **Enable Cron Feature** n'est pas sur **Yes**.

Testez avec **Enable Debug** sur **Yes** et l'adresse ouverte dans un navigateur. Lorsque le plan est correct, mettez-le sur **No**, enregistrez et créez la tâche.

### 3.13 History

![History page with filters, cards, breakdown panels and the prompt list](https://mypresta.eu/docs/images/docs/myaiclaude-history.webp)

L'History est le journal de tout ce qui a été envoyé à Claude. La page s'ouvre sur **This month**.

**Filtres.** Boutons rapides : **Today**, **7 days**, **30 days**, **This month**, **All time**. Champs : **From**, **To**, **Model**, **Type**, **Status**, **Language**, **Employee**, **Product / category ID**, **Prompt or reply contains**. Cliquez sur **Filter**.

**Cartes.** **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time**.

**Panneaux de répartition.** **By day**, **By model**, **By type**, **By language**, **By employee**. Chacun affiche les appels, les tokens envoyés, les tokens reçus et le total. Les lignes sans employé (tous les appels cron) apparaissent comme Unknown.

**Liste de l'historique des prompts.**

| Colonne | Signification | Remarques |
|---|---|---|
| ID | Numéro de ligne | |
| Status | Pastille **Success** ou **Error** | |
| Prompt | Le texte envoyé | Tronqué à 180 caractères dans la liste. |
| Reply / Error | La réponse ou le message d'erreur | Tronqué à 180 caractères dans la liste. |
| Provider | Le service, le modèle, le numéro d'état d'erreur lorsque Claude en a renvoyé un, et la durée en secondes | |
| Sent, Received, Total | Tokens | |
| Entity ID | Le produit ou la catégorie | Vide pour les appels du Playground et de la barre supérieure. |
| Type | Ce qui a été généré | Voir le tableau suivant. |
| Timestamp | Date et heure | |

Cliquez sur l'action d'affichage d'une ligne pour voir le prompt et la réponse complets et le lien **Back to the list**. La liste affiche 50 lignes par page.

| Type | Signification | Remarques |
|---|---|---|
| general | Playground et barre supérieure | Ni produit ni catégorie. |
| product_name, product_description, product_description_short, product_meta_title, product_meta_description, product_tags | Un champ de produit | Écrit par les exécutions en masse, le panneau produit, les boutons à logo et le cron. |
| product_seo_pack | Le pack SEO du panneau produit | Nom, descriptions et champs méta en une seule requête. |
| category_name, category_description, category_meta_title, category_meta_description, category_additional_description | Un champ de catégorie | |
| error | Un appel échoué | La raison figure dans **Reply / Error**. |

**Clear list** dans la barre d'outils supprime **toutes** les lignes après confirmation et affiche **Log list successfully deleted.** Cette action est irréversible. Elle supprime aussi les points de restauration de chaque produit, vide le Dashboard, remet à zéro le compteur du budget mensuel et modifie les produits comptés comme déjà traités dans **Update only** et dans les cibles du cron. Exportez ou notez d'abord ce dont vous avez besoin.

Lorsqu'il n'y a aucune ligne sur la période choisie, la page affiche **No generations in this range.**

### 3.14 Images

![Images page with the image finder switch and search prompt](https://mypresta.eu/docs/images/docs/myaiclaude-images.webp)

Cette page contrôle l'onglet **Photos** de la page produit. Le formulaire s'appelle **AI Image Finder**.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| AI Image Finder | Yes | Active l'onglet **Photos** sur la page produit. Désactivé, l'onglet vous indique de l'activer dans **Settings → General**. |
| AI Image Search Prompt | Texte prêt à l'emploi | L'instruction envoyée à Claude pour trouver des pages web qui montrent le produit. Utilisez `{product_name}` et `{product_description}` comme espaces réservés. Conservez la demande d'exactement cinq adresses de pages renvoyées sous forme de liste, car le module lit cette liste. |

Le prompt prêt à l'emploi demande exactement cinq adresses de pages qui montrent le produit, sous forme de liste JSON, en utilisant le nom et la description du produit.

Cliquez sur **Save**. Le message **Settings saved.** le confirme. La page et l'onglet de **Settings → General** partagent le même interrupteur et le même prompt.

### 3.15 Updates

![Updates page with manual check and automatic notifications](https://mypresta.eu/docs/images/docs/myaiclaude-updates.webp)

La page **Updates** vérifie s'il existe une version plus récente de My AI Claude. La vérification envoie le nom du module, sa version et l'adresse de la boutique au serveur de MyPresta.eu.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| Manual Check | Bouton **Check Now** | Lance la vérification maintenant. La réponse est **Module is up to date!** ou **New version available!** |
| Automatic Notifications | Enabled | Lorsqu'il est activé, le module vérifie environ tous les trois jours et affiche un avis dans le back-office lorsqu'une nouvelle version existe. |
| Product Page | Un lien | Ouvre la page du module sur MyPresta.eu. |

Cliquez sur **Save**. Le message **Update settings saved.** le confirme.

### 3.16 Page produit – Modules → My AI Claude

![Product page with the My AI Claude panel and field cards](https://mypresta.eu/docs/images/docs/myaiclaude-product-edit.webp)

Ouvrez un produit quelconque, allez dans l'onglet **Modules** et trouvez **My AI Claude**. Le panneau comporte les onglets **Generate**, **Simulate**, **Photos** et **History**. Enregistrez un nouveau produit une fois avant d'utiliser le panneau, car le panneau travaille sur un produit enregistré.

**Generate et Simulate.**

1. Choisissez la pastille de langue, ou **Every language**. La première langue de la boutique est sélectionnée au départ.
2. Sous **If the field already has text**, choisissez **Replace**, **Add above**, **Add below** ou **Skip if filled**. **Replace** est sélectionné au départ.
3. Appuyez sur **Fill** sur une carte : **Description**, **Short description**, **Name**, **Meta title**, **Meta description** ou **Tags**. Le texte est écrit directement dans le produit.
4. La carte **SEO pack** comporte **Fill all**. Une seule requête renvoie le nom, les deux descriptions et les deux champs méta. Elle écrase ces champs, y compris le nom. Le message **SEO pack saved. Refresh the product to see it.** le confirme. Si Claude ne renvoie pas de pack exploitable, le panneau indique **The model did not return a usable SEO pack.**
5. Ouvrez **Use your own instruction or a saved prompt** pour filtrer et choisir **Standard brief** ou un modèle activé, ou saisissez votre propre texte dans la zone **Instruction**. Avec une zone vide, la consigne standard de la carte est utilisée.
6. La réponse et le nombre de tokens apparaissent sous les cartes.

Dans l'onglet **Simulate**, les mêmes cartes comportent **Try**. **Try** affiche la réponse et laisse le produit inchangé. Il est tout de même enregistré dans l'History et compté pour le budget, et il fait compter le produit comme déjà traité pour **Update only** et pour le cron.

**Après Fill, rechargez la page produit.** Le formulaire ouvert contient encore l'ancien texte. Si vous appuyez sur **Save** dans PrestaShop sans recharger, PrestaShop écrase le nouveau texte avec l'ancien.

**Photos.**

![Photos tab with found photos ready to be added](https://mypresta.eu/docs/images/docs/myaiclaude-product-photos.webp)

1. Ouvrez l'onglet **Photos** et cliquez sur **Find pages**. Messages : **Looking for photos…** et **Reading photos…**.
2. Cochez les photos souhaitées. La page affiche **Tick the photos you want, then add them to this product.**
3. Cliquez sur **Add selected to this product**. Le message **Adding the photos to this product…** apparaît, puis le nombre d'images importées.
4. Rechargez la page produit pour voir les photos.

Le chercheur lit jusqu'à 5 pages et propose jusqu'à 24 photos. La première photo cochée devient la couverture du produit. Les photos sont téléchargées dans votre boutique et redimensionnées dans toutes les tailles d'image de votre boutique. Vérifiez que vous avez le droit de les utiliser. Lorsque le chercheur est désactivé, l'onglet vous demande de l'activer dans **Settings → General**.

**History.** L'onglet affiche **When**, **Type**, **Status** et un bouton **Restore** pour les 50 dernières entrées de ce produit. La ligne d'introduction indique **Earlier writes for this product. Restore puts the previous text back…** Sans entrée, elle indique **No generations for this product yet.** Cliquez sur **Restore** et confirmez. Le message **Content successfully restored. Refresh this page to see changes.** apparaît. Une ligne sans valeur précédente affiche **Error! This log entry has no previous value to restore.** L'onglet n'apparaît que lorsque **Product Edit History** est activé.

### 3.17 Autres endroits où le module apparaît

**Boutons Generate with AI à côté des champs.** Un petit bouton à logo apparaît à côté de ces champs.

| Endroit | Champs | Ce qui se passe |
|---|---|---|
| Formulaire produit | Description, Short description, Meta title, Meta description | Claude écrit dans le champ du formulaire ouvert. |
| Formulaire catégorie | Description, Additional description, Meta title, Meta description | Claude écrit dans le champ du formulaire ouvert. |

Si la boutique compte plus d'une langue, le bouton demande s'il faut écrire la langue actuelle ou toutes les langues. Le texte apparaît dans le champ mais n'est pas enregistré. La note **Text is in the field. Save the product to keep it.** (pour les catégories : **Save the category**) vous le rappelle. Sur un élément nouveau et non enregistré, le bouton indique **Save the product once before generating.** (pour les catégories : **Save the category once…**). Chaque utilisation est enregistrée dans l'History et fait compter le produit comme déjà traité.

**Raccourci de la barre supérieure.** L'icône magique de la barre supérieure du back-office ouvre une petite fenêtre nommée **My AI Claude** avec une liste **Template**, une zone de texte, **Generate** et un bouton de fermeture. Elle fonctionne comme le Playground et n'enregistre rien. L'interrupteur est **Admin Top Bar CTA** dans **Settings → General**.

**Liste des produits.** Un bouton **My AI Claude** dans la barre d'outils au-dessus de la liste des produits ouvre **Generate → Products**.

### 3.18 Espaces réservés pour les prompts

Les espaces réservés sont des mots entre accolades que le module remplace par de vraies données avant d'envoyer le prompt. Ils fonctionnent dans les modèles, dans la zone de prompt des exécutions en masse, dans le panneau produit et dans le cron.

| Espace réservé | Fonctionne pour | Remplacé par |
|---|---|---|
| `{product_name}`, `{product_description}`, `{product_description_short}`, `{product_tags}` | Produits | Le nom, la description, la description courte et les étiquettes actuels dans la langue de l'exécution. |
| `{product_reference}`, `{product_ean13}`, `{product_weight}` | Produits | Référence, code EAN-13 et poids. |
| `{product_brand}`, `{product_default_category}`, `{product_category_description}`, `{product_categories}` | Produits | Marque, catégorie par défaut avec sa description, et toutes les catégories. |
| `{product_attributes}`, `{product_features}`, `{product_feature_values}` | Produits | Déclinaisons, noms des caractéristiques et valeurs des caractéristiques. |
| `{product_images}` | Produits | Liens vers les photos du produit. |
| `{category_name}`, `{category_description}`, `{category_parent_name}` | Catégories | Nom, description et nom de la catégorie parente. |
| `{shop_name}`, `{shop_url}`, `{shop_language}`, `{shop_country}`, `{shop_currency}` | Partout | Nom de la boutique, adresse, langue, pays et devise. |

Un espace réservé sans données est remplacé par un texte vide.

## 4. Boutique en ligne (front-office)

My AI Claude n'ajoute rien que vos clients puissent voir ou utiliser. Il n'a ni page de front-office, ni bloc, ni widget, ni réglage côté client. Les textes qu'il écrit ne deviennent visibles que parce qu'ils sont enregistrés dans vos produits et catégories, et vous les voyez via votre thème habituel.

Le module possède deux adresses qui appartiennent au domaine de la boutique mais ne sont pas destinées aux clients.

| Adresse | Qui l'utilise | Ce qu'elle renvoie |
|---|---|---|
| `…/module/myaiclaude/cron?secret=…&action=…` | Le planificateur de votre serveur | Une réponse en texte brut telle que **N products have been updated.**, **N categories have been updated.**, **No products to update.**, **No categories to update.** ou l'un des messages du tableau suivant. |
| `…/module/myaiclaude/ajax` | Les propres écrans du module dans le back-office | Rien d'utile lorsqu'elle est ouverte à la main. Elle ne répond qu'aux requêtes qui portent le secret des écrans. |

| Message de l'adresse cron | Signification | Que faire |
|---|---|---|
| Cron Job feature is disabled. You can enable it from the module settings. | **Enable Cron Feature** est sur **No**. | Mettez-le sur **Yes** et enregistrez. |
| The token does not exist or it's wrong! | Le secret de l'adresse ne correspond à aucun secret enregistré. | Copiez de nouveau l'adresse depuis la page **Cron**. |
| Invalid action! | La partie `&action=` est absente ou mal orthographiée. | Ajoutez `&action=generateProductContent` ou `&action=generateCategoryContent`. |
| All must include all mandatory parameters! | Un choix obligatoire manque, le plus souvent le modèle de prompt. | Choisissez un modèle dans le formulaire et cliquez sur **Save**. |
| updatedField parameter is wrong! | Le champ ne fait pas partie des champs autorisés. | Choisissez le champ dans le formulaire et enregistrez. |
| productTarget parameter is wrong! Allowed values: pendingClaude, pendingField, emptyField. | La cible dans l'adresse est mal orthographiée. | Utilisez l'une des trois valeurs. |
| No valid product IDs provided. | La **Product ID list** ne contient aucun nombre. | Corrigez la liste ou videz-la. |
| Error!… | Claude ou la boutique a renvoyé une erreur. Le texte après le mot Error l'explique. | Lisez le texte, voir le chapitre 5. |

Les hooks du module pour la boutique sont vides, il n'ajoute donc aucune sortie aux pages de votre boutique.

## 5. Dépannage

### 5.1 Menu et écrans

| Symptôme | Cause | Sur quoi cliquer |
|---|---|---|
| **AI Content Generator** n'est pas dans le menu. | Le cache n'a pas été vidé, le module est désactivé ou l'employé n'a pas accès. | **Advanced Parameters → Performance → Clear cache**. Vérifiez **Modules → Module Manager**. Vérifiez **Advanced Parameters → Team → Permissions**. |
| Toute adresse du module renvoie au tableau de bord principal. | Le module est désactivé. | Activez-le dans **Module Manager**. |
| Le panneau **Modules → My AI Claude** de la page produit est vide. | **Product edit page Form** et **Product Edit History** sont tous deux désactivés. | Activez-en au moins un dans **Settings → General**. |
| Le panneau produit ne fonctionne pas sur un nouveau produit. | Le produit n'est pas encore enregistré. | Enregistrez le produit une fois, puis utilisez le panneau. |
| L'onglet **History** est absent du panneau produit. | **Product Edit History** est désactivé. | Activez-le dans **Settings → General**. |
| Le bloc My AI Claude du tableau de bord principal de PrestaShop affiche des chiffres vides ou à zéro. | Le bloc de la page d'accueil ne contient pas les données du rapport. | Ouvrez **AI Content Generator → Dashboard** pour les vrais chiffres. |

### 5.2 Connexion à Claude

| Symptôme | Cause | Sur quoi cliquer |
|---|---|---|
| Le message indique que la clé API Anthropic Claude n'est pas définie (**The Anthropic Claude API key is not set. Add it in the module settings.**). | Aucune clé n'est enregistrée. | **Settings → Claude**, collez la clé dans **Anthropic Claude API KEY**, **Save**. |
| **Anthropic Claude API KEY field is invalid!** | Le champ de la clé est vide et aucune clé n'est enregistrée. | Collez la clé et enregistrez. |
| Le message commence par **Anthropic Claude API Error** suivi d'un texte d'Anthropic. | Claude a refusé l'appel. Les raisons typiques sont une mauvaise clé, un modèle que votre compte ne peut pas utiliser, l'absence de crédit ou trop de requêtes. | Lisez le texte après les deux-points. Vérifiez la clé, le crédit et le modèle dans votre compte Anthropic. Choisissez un autre **Model**. |
| **Claude request timed out after N seconds. The model may be overloaded, or the timeout is too low for this prompt.** | Claude a répondu trop lentement. | Augmentez **API timeout (seconds)** dans **Settings → General** (maximum 600) ou réduisez **Max Tokens**. Réessayez plus tard. |
| Un message qui commence par **cURL Error** | Le serveur ne peut pas joindre Claude, ou un pare-feu le bloque. | Demandez à votre hébergeur d'autoriser le HTTPS sortant vers `api.anthropic.com`. |
| Un nouveau modèle Claude est absent de la liste **Model**. | La liste ne contient que les noms intégrés et ceux que vous avez ajoutés. | Saisissez le nom exact dans **Add a Claude model** et cliquez sur **Add model**. |
| Après **Remove**, la liste **Model** affiche un modèle qui n'appartient pas à Claude. | La suppression du modèle ajouté actif fait passer la boutique à un nom de secours que Claude ne connaît pas. | Choisissez un modèle Claude dans **Model** et cliquez sur **Save**. |
| Le module affiche **OpenAi Settings Updated** ou **OpenAi Model field is invalid!**, la colonne **Provider** de l'History affiche `openai`, l'aide de la page parle d'un compte OpenAI et l'exemple de **Add a Claude model** mentionne un nom GPT. | Ce sont des textes résiduels de l'ancienne version du module. | Rien. Le module ne parle qu'à Claude. Lisez ces textes comme du Claude. |
| Le bouton **Module settings** des formulaires de filtre de **Generate** ouvre une mauvaise page. | Le bouton pointe vers les réglages d'un autre module (My ChatGPT), pas vers My AI Claude. | Ouvrez **Settings** dans le menu supérieur du module. |
| Le journal de PrestaShop se remplit de lignes sur la liste des modèles. | **Debug mode** est activé. | Désactivez **Debug mode** dans **Settings → General**. |

### 5.3 Problèmes de génération

| Symptôme | Cause | Sur quoi cliquer |
|---|---|---|
| **Error! Prompt is missing or too short!** | Le prompt compte moins de 4 caractères. | Écrivez un prompt plus long ou choisissez un modèle. |
| **Error! Product not found!** | Le produit n'existe plus. | Rechargez la liste. |
| **The model hit the token limit … Increase "Max Tokens" …** | La réponse a consommé tous les tokens avant tout texte. | Augmentez **Max Tokens** dans **Settings → Claude**. |
| **The model returned an empty response.** | Claude n'a renvoyé aucun texte. | Réessayez, reformulez le prompt ou augmentez **Max Tokens**. |
| **The response was blocked by the provider content filter…** | Claude a refusé le sujet. | Reformulez le prompt. |
| Le texte s'arrête au milieu d'une phrase. | **Max Tokens** est trop bas. | Augmentez **Max Tokens**. Utilisez 1000 ou plus pour une description complète. |
| La description contient des fautes d'orthographe, des titres non voulus, des idées de H1 ou des listes de mots-clés. | Le modèle prêt à l'emploi le demande. | Modifiez le modèle dans **Settings → Prompt templates** (section 3.6). |
| Le texte est en anglais alors que la boutique est dans une autre langue. | Un modèle prêt à l'emploi demande l'anglais, ou la mauvaise langue a été sélectionnée. | Modifiez le modèle et cochez la bonne langue dans l'exécution. |
| **The reply was rejected because it contains a forbidden word from the studio settings.** | Le **Quality gate** a trouvé un mot de **Forbidden words**. | Relancez, retirez le mot de **Studio** ou désactivez **Quality gate**. |
| **Monthly generation budget reached. Raise it in the studio settings or wait until next month.** | Le nombre de générations de ce mois a atteint **Monthly generation budget**. | Augmentez la valeur dans **Settings → Studio** ou mettez 0. |
| **Error! The generated content could not be saved to the product.** | PrestaShop a refusé le texte, par exemple un nom de produit contenant des caractères non autorisés. | Lisez les détails dans la ligne et dans **History**. Modifiez le prompt et relancez. |
| **Error! This PrestaShop version does not support the category Additional Description field.** | Votre version de PrestaShop n'a pas ce champ. | Choisissez un autre champ. |
| Une ligne indique **Product skipped.** ou **Category skipped.** | **Skip if filled** est sélectionné et le champ contient déjà du texte. | Choisissez **Replace** pour écraser. |
| Après **Fill**, l'ancien texte est de retour. | Le formulaire a été enregistré sans recharger la page. | Rechargez la page produit après chaque **Fill**, puis continuez. |
| Une exécution en masse s'est arrêtée. | La page a été fermée ou rechargée. | Recommencez avec **Update only** réglé sur l'option des produits pas encore mis à jour. Les appels échoués y comptent comme mis à jour. |
| La page des catégories a un second formulaire avec **Generate content** qui ne fait rien. | Ce formulaire n'est pas relié. | Utilisez **Run on the categories below**. |
| **Error! This log entry has no previous value to restore.** | La ligne de l'History n'a pas de texte antérieur. | Modifiez le champ à la main. |
| Le résultat de **Try** n'apparaît pas dans le produit, mais une ligne d'History existe. | **Try** n'écrit jamais dans le produit. | Appuyez sur **Fill** pour l'écrire. |

### 5.4 Photos et nouveaux produits

| Symptôme | Cause | Sur quoi cliquer |
|---|---|---|
| L'onglet **Photos** vous demande d'activer le chercheur. | **AI Image Finder** est désactivé. | Activez-le dans **Settings → General** ou sur **Images**. |
| **Claude API key is not configured. Please check module settings.** | Aucune clé n'est enregistrée. | **Settings → Claude**. |
| **The search failed.** | Claude ou le réseau n'a pas répondu. | Cliquez de nouveau sur **Find pages**, vérifiez la clé et le délai d'attente. |
| **No photos were found on the suggested pages.** | Les pages n'avaient aucune photo exploitable. | Modifiez le nom ou la description du produit, ou modifiez **AI Image Search Prompt**. |
| **URL not allowed (private network).** | L'adresse pointe vers un réseau privé ou local. | Utilisez uniquement des pages web publiques. |
| **No images selected** | Rien n'a été coché. | Cochez au moins une photo. |
| **No images could be imported. Details: …** | Les photos n'ont pas pu être téléchargées ou n'étaient pas des images valides. | Lisez les détails. Essayez d'autres photos. |
| La photo de couverture a changé. | La première photo cochée devient la couverture. | Réorganisez les photos dans la page produit. |
| **Add an API key in the module settings first.** (**New product**) | Aucune clé n'est enregistrée. | **Settings → Claude**. |
| **Failed to parse AI response. Please try again.** | Claude a renvoyé un texte qui n'est pas un brouillon valide. | Cliquez de nouveau sur **Generate data**. Décrivez le produit plus en détail. |
| **Prompt is required**, **Invalid product data**, **Failed to create product** | La description est vide, le brouillon est incomplet ou PrestaShop n'a pas pu enregistrer le produit. | Remplissez **What is the product?**, générez de nouveau, vérifiez l'ID de catégorie. |

### 5.5 Problèmes de cron

| Symptôme | Cause | Sur quoi cliquer |
|---|---|---|
| L'adresse répond **Invalid action!** | L'adresse cron copiée depuis la page n'a pas la partie `&action=`. | Ajoutez `&action=generateProductContent` (produits) ou `&action=generateCategoryContent` (catégories). |
| L'adresse répond **Cron Job feature is disabled…** | **Enable Cron Feature** est désactivé. | Mettez **Yes** et **Save**. |
| **Generate Token** ne fait rien. | Le bouton n'est pas relié dans cette version. | Saisissez un secret d'au moins 24 lettres et chiffres dans **Cron Job Secret Token** et **Save**. Un secret plus court est remplacé par un secret aléatoire à la prochaine ouverture d'une page d'administration. |
| L'adresse répond **All must include all mandatory parameters!** | Le formulaire n'a jamais été enregistré, aucun modèle n'est donc stocké. | Choisissez un **Prompt Template**, puis **Save**. |
| L'adresse répond **No products to update.** alors que des produits ont besoin de texte. | **Selected Products** les exclut. **pendingClaude** ignore tout produit ayant une génération réussie, y compris les exécutions **Try**. | Utilisez **emptyField** ou **pendingField**, ou renseignez la **Product ID list**. |
| Le texte d'un produit a de nouveau été réécrit. | Le cron remplace toujours le champ. | Utilisez **emptyField** pour ne toucher que les champs vides. |
| **Error!Monthly generation budget reached.** | Le budget mensuel est épuisé. | Augmentez-le dans **Settings → Studio**. |
| **Error! Could not save product N: … (X product(s) updated before this one.)** | PrestaShop a refusé le texte du produit N. | Corrigez ce produit ou excluez-le, relancez. |
| La commande affichée sur la page ne change pas quand vous modifiez le formulaire. | La commande n'affiche que l'adresse de base. | Ajoutez `&action=` vous-même. Les valeurs du formulaire sont lues depuis les réglages enregistrés. |
| L'intervalle du formulaire n'a aucun effet. | C'est une note pour vous. | Créez le calendrier dans le panneau de votre hébergeur. |

### 5.6 History et données

| Symptôme | Cause | Sur quoi cliquer |
|---|---|---|
| Le Dashboard et l'History sont vides après **Clear list**. | **Clear list** supprime toutes les lignes. | Il n'y a rien à restaurer. Prévoyez des exports avant de vider. |
| **This log entry no longer exists.** | La ligne a été supprimée. | Retournez à la liste. |
| **Update only** n'affiche aucun produit. | Le filtre utilise les entrées de l'History, et chaque produit en a déjà une. | Choisissez **Update all**. |
| Certains produits sont exclus de **Update only**. | Les appels échoués et les exécutions **Try** comptent aussi comme des entrées. | Choisissez **Update all**. |

## 6. Pour les développeurs

### 6.1 Vue d'ensemble

My AI Claude (`myaiclaude`, version 1.1.0, auteur MyPresta.eu) est un module PrestaShop pour l'onglet `front_office_features`. Il prend en charge PrestaShop de 1.6 à 9.99.99 et PHP 7.0 et plus récent. Il appelle l'API Messages d'Anthropic Claude à `https://api.anthropic.com/v1` (point d'accès `/messages`) et écrit les résultats dans les produits et les catégories.

- La classe `myaiclaude` dans `myaiclaude.php` contient l'installation, la désinstallation, les pages de configuration et les hooks.
- La classe `MyAIClaude\OpenAIService` (`src/OpenAIService.php`) est le client. Elle envoie `model`, `max_tokens`, `messages`, un `system` facultatif et un `temperature` facultatif, avec les en-têtes `x-api-key` et `anthropic-version: 2023-06-01`. Top P et les deux pénalités sont enregistrés mais non envoyés. Elle associe `input_tokens` et `output_tokens` aux tokens envoyés et reçus. `listModels()` répond toujours que la liste des modèles est fournie par le catalogue du module ; la liste des modèles est donc l'ensemble intégré plus les noms conservés dans `EXTRA_MODELS`. Le délai d'attente est limité à 10–600 secondes. Lorsque l'API répond 400 et nomme un paramètre, le client abandonne ce paramètre, réessaie et mémorise la décision par modèle dans `MODEL_CAPS`.
- La classe `MyAIClaude\Studio` (`src/Studio.php`) enveloppe les prompts avec la ligne de langue, la voix, le public, le ton, le glossaire et les termes interdits, applique le budget mensuel et le filtre des mots interdits, et construit le prompt du pack SEO.
- Les onglets de la page de configuration utilisent les paramètres d'URL `mac_tab` (`dashboard`, `settings`, `updates`) et `mac_sub` (`general`, `openai`, `studio`, `templates`, `playground`). La valeur `openai` de `mac_sub` ouvre l'onglet Claude. Le Dashboard utilise `mcg_preset` et les dates `mac_from` et `mac_to`.
- Les classes CSS du back-office utilisent le préfixe `.mac-`.
- Les tâches en masse exécutent un élément par requête AJAX depuis `back.js`.

### 6.2 Fichiers

| Chemin | Rôle | Remarques |
|---|---|---|
| `myaiclaude.php` | Classe du module | Installation, désinstallation, formulaires, hooks, placement de l'onglet. |
| `autoload.php` | Chargeur de l'espace de noms `MyAIClaude\` | |
| `src/OpenAIService.php`, `src/Studio.php` | Client API et règles Studio | |
| `controllers/admin/AdminMyAIClaude*.php` | Contrôleurs du back-office | Voir 6.3. |
| `controllers/front/ajax.php`, `controllers/front/cron.php` | Contrôleurs front | AJAX et cron. |
| `lib/updateChecker.php` | Vérification des mises à jour de MyPresta | Contacte `dev.mypresta.eu/update/get.php`. |
| `lib/sectionHelp.php` | Textes du tiroir **Help** | |
| `lib/prestashop9compatibility.php` | Aides de compatibilité | |
| `lib/searchTool` | Aide à l'autocomplétion pour les formulaires d'administration | |
| `views/templates/` | Templates Smarty | Hooks, pages d'administration, panneaux de masse. |
| `views/js/` | `back.js`, `product-fields.js`, `image-finder.js`, `admin-products-bulk.js`, `dashboard.js`, `admin-help.js`, `chart.min.js` | |
| `views/css/` | Styles avec le préfixe `.mac-` | |
| `translations/` | 34 fichiers de langue | |
| `upgrade/index.php` | Espace réservé | Le module n'a aucun script de mise à jour. |

### 6.3 Contrôleurs

| Contrôleur | Menu ou route | Rôle |
|---|---|---|
| AdminMyAIClaudeMain | **AI Content Generator** sous **Modules** | Redirige vers le Dashboard. Parent des onglets cachés. |
| AdminMyAIClaude | Onglet caché **Mass Content Creator** | Generate : produits et catégories. |
| AdminMyAIClaudeProductCreator | Onglet caché **AI Product Creator** | New product. |
| AdminMyAIClaudeSettings | Onglet caché **Module Settings** | Redirige vers l'onglet Settings. |
| AdminMyAIClaudeCron | Onglet caché **Cron Job Settings** | Les deux formulaires cron. |
| AdminMyAIClaudeUsage | Onglet caché **Module Log and Usage** | History. |
| AdminMyAIClaudeImageFinder | Onglet caché **AI Image Finder** | Images. |
| Front `ajax` | `module/myaiclaude/ajax` | Actions `initiatePrompt`, `updateProduct`, `updateCategory`, `initiateProductRestore`, `updateSettings`, `generateAltTexts`, `generateSeoPack`. Exige `secret_token` égal à `TOKEN`. Il n'est pas lié à une session d'employé. Aucun écran de cette version n'appelle `generateAltTexts`. |
| Front `cron` | `module/myaiclaude/cron` | Exige `secret` égal à `SECRET` ou `CAT_SECRET` et `ENABLE_CRON=1`. Paramètres : `action` (`generateProductContent`, `generateCategoryContent`), `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `categories`, `productIds`, `categoryTarget`, `categoriesToUpdate`. Les paramètres manquants sont lus depuis les réglages enregistrés. |

Les onglets enfants sont créés avec `active=0` sous `AdminMyAIClaudeMain`. Sur `displayBackOfficeHeader`, le module place l'onglet principal sous l'onglet parent Modules, le renomme et régénère les secrets de moins de 24 caractères. La classe d'icône est `icon-openai`. L'onglet Image Finder est enregistré à la demande et marqué par `IMAGEFINDER_TAB_OK`.

Le cron des produits accepte les cibles `pendingClaude`, `pendingField` et `emptyField` et ne compte que les lignes de journal dont le statut n'est pas `error`. Le filtre **Update only** de Generate compte toutes les lignes de journal. Les lignes de journal du cron utilisent la méthode `cron`.

### 6.4 Hooks

| Hook | Comportement | Remarques |
|---|---|---|
| `displayAdminProductsExtra` | Affiche le panneau **Modules → My AI Claude** | Onglets Generate, Simulate, Photos, History. |
| `displayBackOfficeHeader` | Charge les ressources, place le menu, régénère les secrets courts | S'exécute sur chaque page d'administration. |
| `displayBackOfficeTop` | Affiche le raccourci de la barre supérieure | |
| `dashboardZoneTwo` | Affiche `dashboard.tpl` sur le tableau de bord de PrestaShop | Le template est rendu sans ses variables de rapport. |
| `displayAdminProductsMainStepLeftColumnMiddle`, `displayAdminProductsMainStepLeftColumnBottom` | Enregistrés, renvoient une chaîne vide | |
| `actionProductFormBuilderModifier` | Enregistré, ne fait rien | |
| `displayHeader`, `displayFooter` | Enregistrés, vides | La boutique ne reçoit aucune sortie. |

Le module n'a pas de méthode `enable()` ni `disable()`. `displayCustomTop` et `top.tpl` existent mais ne sont pas appelés.

### 6.5 Overrides

Le module n'a pas de répertoire `override` et ne modifie aucun fichier du cœur. Les photos de produits sont écrites avec les classes d'image de PrestaShop et le module écrit les produits et les catégories avec les objets PrestaShop (`Product`, `Category`, `Tag::addTags`).

### 6.6 Base de données

Tables (préfixe comme dans votre boutique, moteur comme PrestaShop) :

| Table | Colonnes | Remarques |
|---|---|---|
| `myaiclaude_prompt` | `id_prompt` (clé primaire), `status`, `title`, `prompt`, `date_generated` | Contient les 16 modèles installés et les vôtres. |
| `myaiclaude_log` | Prompt, réponse, statut, type, modèle, ID de produit ou de catégorie, langue, employé, nombres de tokens, durée, date | Une ligne par appel. Les colonnes de tokens sont ajoutées à la demande pour les anciennes installations. |

Les écritures de produits et de catégories touchent les tables du cœur des données modifiées (`product`, `product_lang`, `category_lang`, `tag`, `image` et les tables associées). La désinstallation supprime les deux tables du module.

### 6.7 Clés et traductions

Les clés de configuration utilisent le préfixe `MYPRESTA_MYAICLAUDE_`.

| Clé (après le préfixe) | Au départ | Signification |
|---|---|---|
| `LIVE_MODE`, `DEBUG_MODE` | 0 | Étiquette et journalisation de débogage. |
| `TIMEOUT` | 120 | Délai d'attente de l'API. |
| `PRODUCT_LOG`, `TOPCTA`, `PRODUCT`, `IMAGEFINDER_ENABLE` | 1 | Interrupteurs de la page General. |
| `IMAGEFINDER_PROMPT` | Texte prêt à l'emploi | Utilise `{product_name}` et `{product_description}`. |
| `API_KEY` | Un seul espace | Clé Anthropic. |
| `MODEL`, `EXTRA_MODELS`, `MODEL_CAPS` | `claude-sonnet-4-5`, vide, vide | Modèle actif, modèles ajoutés, prise en charge des paramètres apprise. |
| `TEMPERATURE`, `MAX_TOKENS`, `TOP_P`, `FREQ_PEN`, `PRES_PEN` | 0.7, 3200, 1, 0, 0 | Champs d'échantillonnage. Les trois derniers ne sont pas envoyés. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | Vide | Champs texte de Studio. |
| `BUDGET`, `QUALITY` | 0, 1 | Budget mensuel et quality gate. |
| `TOKEN` | 32 caractères aléatoires | Secret AJAX. |
| `SECRET`, `CAT_SECRET` | 32 caractères aléatoires | Secrets du cron des produits et des catégories. |
| `ENABLE_CRON` | 0 | Interrupteur du cron. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 6 | Notes d'intervalle. |
| `updatedField`, `productTarget`, `productsToUpdate`, `promptTemplateId`, `languageId`, `interval_select`, `debug`, `productIdsList` | description, pendingClaude, 5, vide, langue par défaut, vide, 0, vide | Formulaire enregistré du cron des produits. |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catpromptTemplateId`, `catlanguageId`, `catdebug`, `categories` | description, pendingClaude, 5, vide, langue par défaut, 0, vide | Formulaire enregistré du cron des catégories. |

Les écrans Generate enregistrent aussi leurs derniers choix de filtre dans des clés telles que `FIELD`, `LANGUAGE`, `CONTENT`, `DELAY`, `EXISTING`, `HISTORY`, `STATUS`, `STOCK`, `CATEGORIES`, `BRANDS`, `CATEGORIESC` et plusieurs clés `PROD_*`. La désinstallation ne les supprime pas, pas plus que `mypresta_updates`, `update_myaiclaude` et `updatev_myaiclaude` de la vérification des mises à jour. La désinstallation supprime les autres clés ainsi que les anciennes clés du fournisseur précédent.

Les textes d'aide des champs des formulaires sont construits avec `fieldHelp()` en trois parties : **What it does**, **How to configure** et **Effect**. Les chaînes passent par le système de traduction de PrestaShop (domaines de traduction du module et du contrôleur). Ajoutez une langue en plaçant un fichier `translations/<iso>.php`. Les textes du tiroir Help proviennent de `lib/sectionHelp.php`. Les réponses du cron, les prompts Studio et les textes de prompt par défaut sont de simples chaînes anglaises dans le code.

### 6.8 Extension

- Ajoutez des modèles avec le champ **Add a Claude model**, ou en ajoutant l'identifiant à `EXTRA_MODELS`.
- Ajoutez des prompts comme modèles, ou envoyez votre propre texte via les actions `ajax` avec le secret.
- Les espaces réservés sont remplacés dans `controllers/front/ajax.php`. Les espaces réservés `{cms_title}`, `{brand_name}`, `{brand_description}` et `{brand_short_description}` sont reconnus lorsque la requête porte un ID de page CMS ou de marque. Aucun écran de cette version n'envoie ces ID.
- Construisez votre propre calendrier avec l'adresse du cron et ses paramètres (section 6.3).
- Le module n'affiche aucun template de boutique, un thème n'a donc rien à remplacer.

## 7. Aide

Page du module : https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-claude-ai.html

Pour obtenir de l'assistance :

1. Connectez-vous à mypresta.eu.
2. Allez dans **contact**.
3. Choisissez **Support for paid modules**.
4. Indiquez le nom du module (My AI Claude), sa version (1.1.0), vos versions de PrestaShop et de PHP, et ce que vous avez fait avant l'apparition du problème. Ajoutez le texte du message affiché.
