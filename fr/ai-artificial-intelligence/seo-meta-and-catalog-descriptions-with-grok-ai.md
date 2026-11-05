---
title: "My AI Grok - AI content generation - documentation et manuel d'utilisation"
description: "Un guide pour les marchands qui possèdent déjà le module : connectez votre compte Grok (xAI), générez les textes du catalogue depuis le back-office et résolvez les problèmes lorsque quelque chose ne fonctionne pas."
sidebar:
  label: "My AI Grok - AI content generation - documentation et manuel d'utilisation"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module SEO meta and catalog descriptions with Grok AI sur MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-grok-ai.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-grok-ai/)
>
> ---


## 1. Prérequis

Ce chapitre énumère ce dont votre boutique et votre serveur ont besoin avant que le module puisse rédiger des textes pour vous.

- **PrestaShop :** versions 1.6 à 9.x.
- **PHP :** version 7.0 ou plus récente. Avec un PHP plus ancien, l'installation est refusée avec un message.
- **Extensions PHP :** cURL. Le module communique avec Grok via cURL.
- **Connexion sortante :** le serveur doit être autorisé à ouvrir des connexions sécurisées (HTTPS) vers `https://api.x.ai/v1`. Si un pare-feu les bloque, chaque génération échoue.
- **Autres modules :** aucun. Le module fonctionne seul.
- **Un compte xAI :** vous avez besoin de votre propre compte sur https://console.x.ai pour obtenir une clé API Grok. Les appels à Grok sont facturés par xAI à votre compte, et non par le module.
- **Gros catalogues :** le module écrit un champ d'un produit par requête. Un long traitement en masse dure donc aussi longtemps que toutes ces requêtes mises bout à bout. Utilisez les limites de lot des écrans Generate et Cron, et gardez le délai d'attente de l'API assez élevé pour les modèles lents (voir la section 3.4).

## 2. Installation

### 2.1 Téléverser, installer et activer

1. Dans le back-office, ouvrez **Modules**, puis **Module Manager**.
2. Téléversez le ZIP du module, ou repérez-le dans la liste s'il est déjà sur le serveur.
3. Cliquez sur **Install**. L'installation vérifie la version de PHP, crée les données du module, puis active le module.
4. Si l'installation s'arrête avec un message, lisez la section 5.1.

### 2.2 Ce qui apparaît dans le menu

- Une nouvelle entrée nommée **AI Content Generator** apparaît sous **Modules**. Un clic ouvre l'écran **Dashboard** du module.
- Tous les autres écrans du module (Settings, Generate, New product, Cron, History, Images, Updates) s'atteignent depuis la barre de navigation en haut du module, et non depuis le menu de gauche.
- Sur la page d'édition du produit, un bloc **My AI Grok** apparaît dans l'onglet **Modules**, et de petits boutons **Generate with AI** apparaissent à côté des champs de texte (voir la section 3.16).
- Un raccourci en forme de baguette magique peut apparaître dans la barre supérieure de chaque page du back-office (voir **Admin Top Bar CTA** à la section 3.4).

Vous pouvez aussi atteindre les réglages par **Modules**, **Module Manager**, le nom du module, **Configure**.

### 2.3 Cache

L'installation ne vide pas le cache de PrestaShop. Si l'entrée de menu ou le bloc produit n'apparaît pas juste après l'installation, videz vous-même le cache dans **Advanced Parameters**, **Performance**, puis rechargez la page.

### 2.4 Désinstallation et réinstallation

- **Ce qui disparaît :** l'entrée de menu **AI Content Generator** et ses écrans cachés, les 16 modèles de prompt prêts à l'emploi ainsi que ceux que vous avez ajoutés, toute la History (chaque prompt enregistré, réponse et nombre de tokens), et les réglages enregistrés du module (clé API, modèle, règles Studio, choix cron, secrets).
- **Ce qui reste :** tous les textes déjà écrits dans les produits et les catégories. Le module ne supprime jamais les textes générés.
- **Résidus :** quelques choix mémorisés des écrans Generate (filtres tels que la dernière langue ou le dernier statut choisis) peuvent rester stockés dans la boutique. Ils n'ont aucun effet.
- **Réinstallation :** une nouvelle installation repart des valeurs par défaut indiquées au chapitre 3. Votre clé API, les règles Studio, les modèles personnalisés et la History ne sont pas restaurés ; notez ou exportez donc au préalable ce dont vous avez besoin.

## 3. Configuration et travail dans le back-office

C'est le chapitre principal. Il commence par l'ensemble du processus de travail, puis décrit chaque écran dans l'ordre de la barre de navigation.

Les captures d'écran proviennent d'un back-office en anglais. Dans ce chapitre, les noms des boutons, champs et messages sont en gras tels qu'ils apparaissent dans l'interface anglaise ; les explications sont en français.

### 3.1 Tout le processus, étape par étape

1. **Connectez Grok.** Ouvrez **Settings**, puis **Grok**. Collez votre clé API depuis https://console.x.ai et choisissez un modèle. Enregistrez.
2. **Définissez votre style maison (facultatif).** Ouvrez **Settings**, puis **Studio**. Renseignez la voix, le public, le ton, un glossaire de noms à conserver, les mots interdits, un budget mensuel et le contrôle qualité. Laissez vide ce dont vous n'avez pas besoin.
3. **Testez en toute sécurité.** Utilisez **Settings**, puis **Playground** pour envoyer une instruction libre et lire la réponse. Sur une page produit, utilisez l'onglet **Simulate** et **Try**. Rien n'est enregistré dans le catalogue à ces deux endroits.
4. **Remplissez un produit.** Ouvrez le produit, allez dans l'onglet **Modules**, **My AI Grok**, **Generate**, choisissez la langue et appuyez sur **Fill** à côté du champ. Ou utilisez les boutons **Generate with AI** à côté des champs du produit, puis enregistrez le produit.
5. **Remplissez de nombreux produits.** Ouvrez **Generate**, **Products**. Filtrez la liste, appuyez sur **Go to next step**, choisissez un modèle ou rédigez une instruction, choisissez ce qu'il faut générer, comment traiter le texte existant et pour quelles langues, puis appuyez sur **Run on the list below**. Faites de même pour les catégories dans **Generate**, **Categories**.
6. **Lots sans surveillance.** Ouvrez **Cron**, enregistrez vos choix et copiez l'adresse dans le planificateur de tâches de votre serveur (voir les sections 3.12 et 4.2).
7. **Auditer et annuler.** **History** affiche chaque appel avec son prompt, sa réponse, son statut et ses tokens. Sur un produit, l'onglet **History** vous permet de remettre un texte antérieur avec **Restore**.

Le texte généré est écrit directement dans le catalogue dès que chaque réponse arrive. Avant un premier gros traitement, testez sur quelques produits avec **Simulate** ou avec les filtres **Product IDs** et **Product Limit**.

### 3.2 Navigation et panneau Help

![Dashboard with the navigation bar and date presets](https://mypresta.eu/docs/images/docs/myaigrok-dashboard.webp)

*Dashboard : la barre de navigation se trouve en haut de chaque écran du module.*

La barre affiche le nom du module avec sa version et ces éléments, dans cet ordre :

| Élément | Ce que vous y trouvez |
|---|---|
| **Dashboard** | Graphiques des requêtes, des tokens et des erreurs. |
| **Settings** | Cinq sous-onglets : **General**, **Grok**, **Studio**, **Prompt templates**, **Playground**. |
| **Generate** | Deux sous-onglets : **Products** et **Categories** pour les traitements en masse. |
| **New product** | Crée un nouveau produit à partir d'un bref descriptif. |
| **Cron** | Construit des adresses que le serveur peut appeler selon un calendrier. |
| **History** | La liste complète des appels avec filtres. |
| **Images** | Interrupteur et instruction pour la recherche d'images de produit. |
| **Updates** | Vérifie si une version plus récente du module est publiée. |

Survolez un élément pour lire une courte explication. Un bouton rond **Help** au bord de l'écran ouvre un panneau latéral avec l'aide de la page où vous vous trouvez. Fermez-le avec la croix.

Chaque champ du module est expliqué à l'écran en trois parties : **What it does**, **How to configure** et **Effect**. Les tableaux ci-dessous reformulent ces textes en termes simples et ajoutent la valeur du champ juste après l'installation.

### 3.3 Dashboard

Ouvrez **AI Content Generator** sous **Modules**, ou l'élément **Dashboard** de la barre.

- **Périodes prédéfinies :** **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time**. La page s'ouvre sur **30 days**.
- **From** et **To :** choisissez vos propres dates et appuyez sur **Apply**. Si From est postérieure à To, les dates sont inversées.
- **Active service :** affiche Grok et le modèle sélectionné dans Settings.
- **Cartes :** **Requests** (chaque appel enregistré), **Success**, **Errors**, **Tokens sent** (taille des prompts) et **Tokens received** (taille des réponses).
- **Graphiques :** **Requests and errors**, **Tokens sent and received** et **Requests by model**. Pour les plages de plus de quatre mois environ, les jours sont regroupés par semaine.

| Contrôle | À l'installation | Ce qu'il fait |
|---|---|---|
| **Presets** | 30 days | Compte les générations Grok enregistrées dans History entre les dates choisies. La clé API et le modèle ne se choisissent pas ici mais dans Settings. |
| **From / To / Apply** | 30 derniers jours | Ne trace que cette tranche. Rien n'est généré ni modifié dans le catalogue depuis cette page, et la History n'est pas supprimée. |

### 3.4 Settings – General

Ouvrez **Settings**, puis **General**.

![Settings, General tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-general.webp)

*Settings – General : interrupteurs valables pour toute la boutique et délai d'attente de l'API.*

Ces interrupteurs déterminent ce que les employés voient dans le back-office. Enregistrer ici ne modifie pas à lui seul le texte des produits. Appuyez sur **Save** ; la confirmation indique **Settings Updated**.

| Champ | À l'installation | Ce qu'il fait |
|---|---|---|
| **Live mode** | Désactivé | Indique que le module fonctionne sur la vraie boutique et non sur une installation d'essai. Activez-le sur la boutique de production. Laissez-le désactivé sur une copie de préproduction (staging) si vous ne voulez pas que le personnel considère les outils comme prêts. Désactivé conserve les mêmes outils mais signale que ce n'est pas l'installation de production. |
| **Debug mode** | Désactivé | Écrit des détails de diagnostic supplémentaires lorsqu'un appel à Grok échoue. Activez-le uniquement pendant que vous enquêtez sur une erreur, puis désactivez-le. Activé ajoute des messages techniques au journal PrestaShop (**Advanced Parameters**, **Logs**). Désactivé limite le journal à l'historique normal des générations. Les clients ne le voient jamais. |
| **API timeout (seconds)** | 120 | Combien de secondes un appel à Grok peut durer avant que le module abandonne. Utilisez 120 pour des descriptions normales. Montez vers 600 pour de longs packs SEO ou des modèles lents. Ne descendez pas sous 10. Les valeurs inférieures à 10 sont enregistrées comme 10 et celles supérieures à 600 comme 600 ; une valeur vide ou non numérique est enregistrée comme 120. Un délai court échoue vite et enregistre une erreur. Un délai long attend un modèle lent au lieu d'interrompre une bonne réponse. |
| **Product Edit History** | Activé | Affiche sur la page produit les écritures précédentes de l'IA afin de pouvoir remettre une ancienne valeur. Activez-le si les éditeurs doivent pouvoir annuler une génération. Activé ajoute un onglet **History** avec **Restore** au bloc du module sur le produit. Désactivé le masque. Les lignes passées restent dans History dans les deux cas. |
| **Admin Top Bar CTA** | Activé | Place un raccourci dans la barre supérieure du back-office qui ouvre le générateur. Activez-le pour les boutiques où le personnel génère souvent des textes. Désactivez-le si la barre est déjà encombrée. Activé affiche le bouton sur chaque page du back-office. Désactivé retire uniquement ce bouton. Le menu du module reste. |
| **Product edit page Form** | Activé | Affiche le panneau du générateur sur la page d'édition du produit : les onglets **Generate**, **Simulate** et **Photos** du bloc **My AI Grok**. Activez-le pour les éditeurs du catalogue. Désactivez-le si seuls la génération en masse et le cron doivent être utilisés. |
| **AI Image Finder** | Activé | Permet à un éditeur de demander au modèle des pages susceptibles de contenir des photos du produit courant. Activez-le si vous voulez ce bouton sur la page produit. C'est toujours vous qui choisissez les images à importer. Désactivé masque le contenu de l'onglet **Photos**. Rien n'est téléchargé tant que quelqu'un n'a pas confirmé une image. |
| **AI Image Search Prompt** | Demande exactement 5 adresses de pages | L'instruction envoyée lorsqu'on recherche des images de produit. `{product_name}` et `{product_description}` sont remplacés par le produit courant. Conservez la demande d'une liste d'adresses de pages. Modifiez la formulation si vous voulez des sites de fabricants ou un autre nombre. Un prompt plus précis renvoie des pages plus pertinentes. Un prompt vague renvoie des liens sans rapport. Rien n'est enregistré tant que vous n'avez pas choisi d'images. |

Le même interrupteur **AI Image Finder** et le même prompt existent aussi sur l'écran **Images** (section 3.14) ; les deux endroits modifient le même réglage.

### 3.5 Settings – Grok

Ouvrez **Settings**, puis **Grok**.

![Settings, Grok tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-grok.webp)

*Settings – Grok : clé API, modèle et valeurs d'échantillonnage.*

Ce formulaire contient le compte Grok utilisé pour toute génération, y compris le cron et les boutons du produit. Les champs d'échantillonnage modifient la variété de la formulation. Ils ne modifient pas les produits qui sont mis à jour.

Messages que vous pouvez voir après **Save** : **OpenAi Settings Updated** (succès ; l'intitulé est un reliquat, mais l'écran appartient à Grok), **Grok API KEY field is invalid!** (aucune clé enregistrée et celle collée fait moins de 10 caractères) et **OpenAi Model field is invalid!** (le nom du modèle est trop court). Une clé entourée d'espaces est nettoyée automatiquement et vous pouvez voir **Grok API Key has been automatically cleaned (whitespace removed).**

| Champ | À l'installation | Ce qu'il fait |
|---|---|---|
| **Grok API KEY** | vide | Le secret qui permet à cette boutique d'appeler votre compte Grok. Collez la clé de https://console.x.ai. Les espaces sont supprimés à l'enregistrement. Laissez le champ intact pour conserver la clé déjà enregistrée. Une clé valide autorise les générations Grok. Une clé vide ou erronée fait échouer ces appels et l'erreur est écrite dans History. |
| **Model** | grok-4.7 | Le modèle Grok qui écrit le texte. Les noms intégrés sont grok-4.7, grok-4.6, grok-4.5, grok-4.3, grok-4.20-0309-non-reasoning et grok-4.20-0309-reasoning. Ils restent dans la liste. Les noms que vous ajoutez à la ligne suivante peuvent être supprimés. La génération suivante utilise ce modèle. Un modèle auquel votre clé n'a pas accès renvoie une erreur au lieu d'un texte. |
| **Add a Grok model** | aucun modèle supplémentaire | Ajoute un identifiant de modèle Grok absent de la liste intégrée afin de pouvoir le sélectionner ci-dessus. Saisissez l'identifiant exact de votre compte Grok (par exemple grok-4.6), puis cliquez sur **Add model**. Le nouvel identifiant apparaît dans la liste **Model** et devient le modèle actif. **Remove** à côté d'un identifiant ajouté ne supprime que les identifiants ajoutés ici. Les identifiants intégrés ne peuvent pas être supprimés. Si vous supprimez le modèle actif, grok-4.7 devient actif. Messages : **Model added.**, **Model removed.**, **That model is already built in.**, **Built-in models cannot be removed.**, **Enter a model id such as grok-4.6.** |
| **Max Tokens** | 3200 | Limite supérieure de la longueur de la réponse, comptée en tokens et non en mots. Utilisez environ 256 pour une méta-description et 1000 ou plus pour une description HTML complète. Une limite basse coupe la réponse. Une limite haute autorise un texte plus long et coûte plus cher sur la facture du fournisseur. Elle ne modifie pas le prompt. |
| **Temperature** | 0.7 | Avec quelle liberté le modèle choisit les mots. Plus bas, c'est plus stable ; plus haut, c'est plus varié. Restez entre 0 et 1. Utilisez environ 0,2 pour les fiches techniques et les textes méta, environ 0,7 pour les descriptions. Modifiez cette valeur ou **Top P**, pas les deux. Une valeur basse répète une structure similaire. Une valeur haute produit des formulations plus différentes et davantage de risque de s'éloigner de la consigne. |
| **Top P** | 1 | Une autre façon de limiter le caractère surprenant du mot suivant. 1 considère toute la plage. Laissez 1 si vous avez déjà réglé **Temperature**. N'utilisez une valeur plus basse, comme 0,9, que si vous voulez un vocabulaire plus resserré. Les valeurs plus basses rendent les réponses plus sûres et plus répétitives. |
| **Frequency Penalty Value** | 0 | Réduit les lignes qui répètent la même expression dans une réponse. Utilisez 0 sauf si les descriptions recopient sans cesse la même phrase. Essayez de 0,3 à 0,6. Restez entre -2 et 2. Une valeur positive rend la répétition de formulations moins probable. Elle ne regarde pas les autres produits. |
| **Presence Penalty Value** | 0 | Pousse la réponse vers de nouveaux sujets plutôt que de rester sur les mots déjà employés. Utilisez 0 par défaut. Essayez un petit nombre positif si chaque paragraphe traite le même point. Restez entre -2 et 2. Certains modèles récents ignorent ce champ. |

Le module mémorise de lui-même lesquelles de ces valeurs un modèle refuse et cesse de les lui envoyer ; vous ne verrez donc pas d'erreur à ce sujet.

### 3.6 Settings – Studio

Ouvrez **Settings**, puis **Studio**.

![Settings, Studio tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-studio.webp)

*Settings – Studio : règles maison ajoutées à chaque prompt.*

Studio s'applique en plus de chaque prompt, y compris les boutons du produit, la génération en masse et le cron. Les champs vides sont ignorés. Un budget de 0 signifie aucune limite mensuelle. Le module indique aussi au modèle dans quelle langue écrire, d'après la langue du produit, de la catégorie ou de l'écran utilisé. Appuyez sur **Save studio** ; la confirmation indique **Studio settings saved.** Le texte déjà enregistré dans le catalogue n'est pas réécrit.

| Champ | À l'installation | Ce qu'il fait |
|---|---|---|
| **Brand voice** | vide | Dit au modèle qui s'exprime, afin que les textes produit correspondent à la boutique et non à un assistant générique. Rédigez un bref descriptif, par exemple : atelier spécialisé, phrases courtes, sans emphase. Toute génération ultérieure part de cette voix. La modifier ne réécrit pas le texte déjà enregistré. |
| **Audience** | vide | Désigne le lecteur pour lequel le modèle doit écrire. Utilisez une expression simple comme installateurs professionnels ou acheteurs novices. Les réponses emploient un vocabulaire et des exemples adaptés à ce lecteur. |
| **Tone** | vide | Fixe l'ambiance de la formulation : formel, chaleureux, technique, etc. Un ou deux mots suffisent. Laissez vide pour que le prompt décide. Cela ne modifie ni le modèle ni la température. |
| **Glossary** | vide | Une liste de noms de marques, de matériaux et d'orthographes que le modèle doit recopier exactement. Saisissez un terme par ligne, sous la forme que vous voulez conserver. Le nouveau texte privilégie ces orthographes. Les termes non listés peuvent être reformulés. |
| **Forbidden words** | vide | Des mots et expressions qui ne doivent pas apparaître dans une réponse enregistrée. Un mot ou une expression par ligne. La liste n'est vérifiée que lorsque le **Quality gate** est activé. Une réponse qui contient l'une de ces lignes est rejetée et n'est pas écrite dans le produit. La tentative reste néanmoins enregistrée dans History comme une erreur. |
| **Monthly generation budget** | 0 | Plafonne le nombre de générations réussies que la boutique peut exécuter durant le mois civil en cours. Saisissez un nombre entier. Utilisez 0 pour aucun plafond. Le compteur repart le premier jour du mois. Une fois le plafond atteint, les nouvelles générations s'arrêtent avec un message de budget jusqu'au mois suivant. Les appels en échec ne sont pas comptés. Les nombres négatifs sont enregistrés comme 0. |
| **Quality gate** | Activé | Vérifie la réponse du modèle par rapport à la liste d'interdits avant que quoi que ce soit soit enregistré. Activez-le après avoir rempli **Forbidden words**. Désactivez-le si vous voulez seulement conserver la liste pour plus tard. Activé bloque une réponse qui correspond. Désactivé enregistre la réponse même si elle contient un mot de la liste. |

Le budget compte les lignes de History ; utiliser **Clear list** sur l'écran History remet donc à zéro le décompte du mois.

### 3.7 Settings – Prompt templates

Ouvrez **Settings**, puis **Prompt templates**.

![Settings, Prompt templates tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-templates.webp)

*Settings – Prompt templates : la liste des instructions enregistrées.*

Un modèle est une instruction enregistrée. Les éditeurs le choisissent au lieu de retaper le même descriptif. Les marqueurs (placeholders) sont remplacés par le produit ou la catégorie pour lesquels vous générez. La boutique démarre avec 16 modèles prêts à l'emploi pour les noms de produit, les descriptions, les méta-titres, les méta-descriptions et les tags, tous activés.

**La liste** affiche **ID**, **Title**, **Prompt**, **Status** (cliquez sur la coche ou la croix pour activer ou désactiver un modèle) et **Timestamp**. Chaque ligne a **Edit** et **Delete**. Cochez plusieurs lignes et utilisez l'action groupée **Delete** (on vous demande : **Are you sure you want to delete the selected prompts?**). Le bouton **Add new** au-dessus de la liste crée un modèle.

**Le formulaire** (**Generate Prompt Template**) comporte trois champs. Appuyez sur **Save Prompt**, ou sur **Go Back to Module Settings** pour quitter sans enregistrer. Messages : **Prompt template successfully added!**, **Prompt template successfully updated!**, **Prompt template removed.** Les guillemets doubles saisis dans le prompt sont enregistrés comme des guillemets simples.

| Champ | À l'installation | Ce qu'il fait |
|---|---|---|
| **Status** | Désactivé pour un nouveau modèle | Affiche ou masque ce modèle dans les listes déroulantes utilisées sur la page produit, dans la génération en masse et dans le cron. Activez les modèles que le personnel doit utiliser. Désactivez un brouillon plutôt que de le supprimer. Les modèles activés apparaissent dans les listes. Les modèles désactivés restent dans ce tableau mais ne sont pas proposés. |
| **Prompt title** | vide (obligatoire) | Le nom que les éditeurs voient dans la liste déroulante des modèles. Il n'est pas envoyé au modèle. Utilisez une étiquette courte comme HTML description with features. |
| **Prompt content** | vide (obligatoire) | L'instruction envoyée au modèle. Rédigez la consigne comme vous la diriez à un rédacteur et mentionnez la longueur, le HTML et la langue s'ils comptent. Lorsque quelqu'un exécute le modèle, les marqueurs sont remplis à partir de l'élément courant et la réponse est écrite dans le champ qu'il a choisi. |

**Marqueurs** (placeholders) que vous pouvez saisir dans un prompt (ils sont remplis pour chaque produit, catégorie ou page lors de l'exécution du modèle) :

| Marqueur | Remplacé par |
|---|---|
| `{product_name}` `{product_description}` `{product_description_short}` `{product_tags}` `{product_reference}` `{product_ean13}` `{product_weight}` | Les données propres du produit dans la langue rédigée. |
| `{product_brand}` `{product_default_category}` `{product_category_description}` `{product_categories}` | La marque du produit, le nom et la description de sa catégorie par défaut, et les noms de toutes ses catégories. |
| `{product_attributes}` `{product_features}` `{product_feature_values}` `{product_images}` | Les attributs de déclinaison du produit, les noms de caractéristiques, les paires nom et valeur de caractéristique, et les liens vers ses images. |
| `{category_name}` `{category_description}` `{category_parent_name}` | La catégorie rédigée, et le nom de sa catégorie parente. |
| `{cms_title}` `{brand_name}` `{brand_description}` `{brand_short_description}` | Les données de la page de contenu ou de la marque ouverte lorsque vous utilisez le raccourci de la barre supérieure. |
| `{shop_name}` `{shop_url}` `{shop_language}` `{shop_country}` `{shop_currency}` | Les données de toute la boutique : nom, domaine, langue, pays par défaut et code de la devise par défaut. |

N'utilisez que les marqueurs qui ont un sens là où le modèle sera exécuté. Un marqueur de produit dans une consigne de catégorie reste du texte saisi.

### 3.8 Settings – Playground

Ouvrez **Settings**, puis **Playground**.

![Settings, Playground tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-playground.webp)

*Settings – Playground : un bloc-notes pour une instruction libre.*

Le Playground envoie une instruction libre au modèle actif et affiche la réponse sous le bouton. Vous pouvez mentionner le nom de la boutique, l'URL de la boutique, un nom de produit, une référence ou des caractéristiques de produit afin que le module substitue des données du catalogue. La réponse reste sur cette page. Aucun champ de produit ou de catégorie n'est enregistré.

| Champ | À l'installation | Ce qu'il fait |
|---|---|---|
| **Instruction box** | vide | Saisissez l'instruction en langage courant et appuyez sur **Generate**. Le fournisseur actif reçoit ce texte avec les règles Studio. La réponse apparaît sous le bouton avec le nombre de tokens utilisés. Le catalogue n'est pas mis à jour. |

Si vous appuyez sur **Generate** avec une zone vide, vous voyez **Write a prompt first.** Chaque appel est enregistré dans History avec le type **general**.

### 3.9 Generate – Products

Ouvrez **Generate**, puis **Products**. Vous pouvez aussi cliquer sur le bouton **My AI Grok** qui apparaît à côté des actions groupées de la liste des produits.

La génération en masse comporte deux étapes : un filtre qui construit une liste, puis un traitement sur cette liste.

**Étape 1 : Filter products to update.** Cette étape se contente de construire la liste de produits. Rien n'est écrit dans les produits tant que vous n'avez pas choisi une portée et des langues sur l'écran suivant et appuyé sur **Run**. Ces filtres ne sont pas enregistrés comme réglages de la boutique. Appuyez sur **Go to next step** lorsque vous êtes prêt. Laissez un filtre vide pour l'ignorer.

| Champ | À l'installation | Ce qu'il fait |
|---|---|---|
| **Product Categories** | aucune cochée | Limite la liste de produits à ceux qui se trouvent dans les catégories cochées (ou qui ont l'une d'elles comme catégorie par défaut). Cochez les catégories voulues. Laissez l'arbre vide si la catégorie ne doit pas compter. |
| **Brand** | Select brand (no filter) | Conserve les produits d'un fabricant. Choisissez une marque, ou laissez la première option vide si toutes les marques doivent être incluses. |
| **Product status** | Active | Conserve les produits en vente, désactivés, ou les deux. Choisissez **Active** pour le catalogue en ligne, **Disabled** pour les brouillons ou **Both**. |
| **Product stock** | All products | Écarte éventuellement les produits en rupture de stock. **Only in stock products** retire de la liste les produits sans quantité disponible. **All products** laisse le stock en dehors du filtre. |
| **Update only** | Update all | Utilise l'historique de génération pour inclure les produits jamais rédigés par ce module (**Products that have not been updated with OpenAi content**), uniquement ceux qui l'ont été (**Products that already have been updated with OpenAi content**), ou tous les produits (**Update all**). Choisissez « pas encore mis à jour » pour une première passe et « déjà mis à jour » lorsque vous voulez réécrire. Un produit compte comme déjà mis à jour lorsque History contient une entrée quelconque pour lui, même une tentative en échec. |
| **Product IDs** | vide | Restreint la liste à des identifiants de produit précis. Saisissez les identifiants séparés par des virgules, par exemple 12,45,103. |
| **Product Reference** | vide | Restreint la liste à des codes de référence précis. Saisissez une ou plusieurs références séparées par des virgules. |
| **Product Add Date From** | vide | La date de création la plus ancienne qu'un produit peut avoir pour être inclus. Les produits créés avant ce moment sont écartés. |
| **Product Add Date To** | vide | La date de création la plus récente qu'un produit peut avoir pour être inclus. Les produits créés après ce moment sont écartés. |
| **Minimum product ID** | vide | Le plus petit identifiant de produit pouvant apparaître dans la liste. Saisissez un nombre entier. |
| **Maximum product ID** | vide | Le plus grand identifiant de produit pouvant apparaître dans la liste. Saisissez un nombre entier. |
| **Product Limit** | vide (aucune limite) | Plafonne le nombre de produits chargés dans la liste de génération. Utilisez un petit nombre, comme 20, sur un gros catalogue. L'écran suivant n'en affiche jamais plus, de sorte qu'un traitement ne puisse pas parcourir tout le catalogue par accident. |

**Étape 2 : Mass product generation.** L'écran suivant affiche un tableau des produits correspondants (**ID**, **Reference**, **Result**) avec les contrôles de traitement au-dessus.

![Mass product generation with the filtered list](https://mypresta.eu/docs/images/docs/myaigrok-generate-products.webp)

*Generate – Products : modèle, portée, texte existant, langues et la liste sur laquelle le traitement s'exécute.*

Écrit les produits filtrés un par un avec le modèle actif. Chaque produit du tableau est mis à jour dans les langues cochées. Les produits qui n'étaient pas dans le filtre ne sont pas touchés. Une ligne affiche son résultat dès que ce produit est terminé.

| Champ | À l'installation | Ce qu'il fait |
|---|---|---|
| **Template** | **Choose a template** (aucun) | Remplit la zone du prompt à partir d'un modèle enregistré dans Settings. Choisissez un titre, ou laissez la première option et saisissez votre propre prompt dans la zone en dessous. Le modèle reçoit le texte de la zone avec les marqueurs de produit remplacés pour chaque ligne. Le titre lui-même n'est pas envoyé. Si la zone reste vide, une brève consigne toute prête est utilisée pour chaque champ. |
| **What to generate** | Descriptions | **Descriptions** écrit la description longue et la courte. **Meta title and meta description** écrit les deux champs méta. **Descriptions and meta together** écrit les quatre. Les champs en dehors de ce choix restent tels quels. Chaque champ a sa propre requête. |
| **Existing text** | Replace | **Replace** écrase le champ. **Skip if filled** laisse un champ rempli et n'appelle pas le modèle pour lui. **Add above** et **Add below** conservent l'ancien texte et ajoutent le nouveau avant ou après. Replace modifie la valeur enregistrée. Skip protège les champs remplis. Add conserve les deux versions dans le même champ. |
| **Languages** | la langue de votre propre session de back-office est cochée | Cochez chaque langue à rédiger. Décochez une langue pour ne pas y toucher. Chaque langue cochée est générée séparément. Les langues décochées gardent leur texte actuel. |
| **Run on the list below** | – | Lance le traitement. Une ligne d'état affiche la progression (par exemple 3 / 24 suivi du nom du champ) et se termine par **Finished N products.** Si aucune langue n'est cochée, vous voyez **Select at least one language.** |

Chaque ligne de la colonne **Result** indique une ligne par champ et par langue, par exemple le nom du champ suivi de **success**, **skipped** ou **error** et d'un court message. **skipped** avec **Product skipped.** signifie que le champ avait déjà du texte et que **Skip if filled** était choisi. Les lignes **error** portent la raison ; le même échec est enregistré dans History.

Gardez cet onglet du navigateur ouvert jusqu'à ce que le traitement affiche **Finished**. Le traitement est piloté par la page : elle envoie une requête à la fois, et fermer ou recharger l'onglet l'arrête. Les produits déjà terminés restent écrits. Un texte très long est raccourci pour respecter les limites de PrestaShop : noms à 128 caractères, descriptions courtes à 800, méta-titres à 69 et méta-descriptions à 159.

### 3.10 Generate – Categories

Ouvrez **Generate**, puis **Categories**. Il fonctionne comme l'écran des produits avec moins de filtres.

**Étape 1 : Filter categories to update.** Cette étape se contente de construire la liste de catégories. Rien n'est envoyé au modèle tant que vous n'avez pas rédigé un prompt sur l'écran suivant et lancé le traitement. Les filtres ici ne sont pas enregistrés comme réglages de la boutique. Appuyez sur **Go to next step**.

| Champ | À l'installation | Ce qu'il fait |
|---|---|---|
| **Categories** | aucune cochée | Choisit les catégories qui apparaîtront dans la liste à l'étape suivante. Cochez une ou plusieurs catégories. Laissez l'arbre vide pour inclure toutes les catégories correspondant au statut ci-dessous. |
| **Category status** | Active | Conserve les catégories actives, désactivées, ou les deux (**Active**, **Disabled**, **Both**). L'étape suivante ne liste que les catégories ayant ce statut. |

**Étape 2 : Mass category generation.**

![Mass category generation](https://mypresta.eu/docs/images/docs/myaigrok-generate-categories.webp)

*Generate – Categories : l'instruction, le champ, le texte existant, la langue et la liste des catégories.*

Écrit un champ pour chaque catégorie de la liste filtrée. Chaque catégorie listée est mise à jour dans cette langue. Les autres champs et les autres langues restent tels quels.

| Champ | À l'installation | Ce qu'il fait |
|---|---|---|
| **Instruction box** (au-dessus de la liste des champs) | vide | L'instruction envoyée pour chaque catégorie. Décrivez le ton, la longueur et le HTML. Utilisez `{category_name}` si vous voulez le nom de la catégorie dans la consigne. Chaque catégorie est générée à partir de ce même texte. Si la zone est vide, une brève consigne toute prête est utilisée. |
| **Field selector** | Description | Le champ de catégorie que ce traitement écrit : **Description**, **Name**, **Meta title**, **Meta description** ou **Additional description**. Seul ce champ est enregistré. Les autres champs de la catégorie restent tels quels. Si votre PrestaShop n'a pas de champ Additional description pour les catégories, vous voyez **Error! This PrestaShop version does not support the category Additional Description field.** |
| **Existing text selector** | Replace | **Replace** écrase le champ. **Skip if filled** le laisse et n'appelle pas le modèle pour cette catégorie. |
| **Language selector** | la langue de votre back-office | La version linguistique qui sera écrite. Choisissez une langue. Relancez pour une autre langue. Seule cette langue change. |
| **Run on the categories below** | – | Lance le traitement. Les résultats apparaissent par ligne, comme sur l'écran des produits. |

Sous la liste, l'écran affiche aussi un second formulaire appelé **Generate category content**. Pour générer, utilisez le bouton **Run on the categories below** situé au-dessus. Ce second formulaire se contente de mémoriser ses choix et vous ramène au filtre des catégories (voir la section 5.12).

### 3.11 New product

Ouvrez **New product**. Cet écran transforme un bref descriptif en brouillon de produit et peut insérer ce brouillon dans le catalogue.

![New product screen](https://mypresta.eu/docs/images/docs/myaigrok-new-product.webp)

*New product : descriptif, page source facultative, langue et catégorie par défaut.*

**Generate data** affiche le brouillon et n'enregistre pas de produit. **Create product** ajoute un produit actif dans cette langue et cette catégorie, copie du brouillon le nom, les descriptions, les méta, les tags, les caractéristiques, le prix et la référence, lui donne un stock initial de 100 pièces et le place dans la catégorie choisie.

| Champ | À l'installation | Ce qu'il fait |
|---|---|---|
| **What is the product?** | vide | Le descriptif que le modèle développe en un nom, des descriptions, des méta, des tags, des caractéristiques, une référence et un prix. Décrivez le produit en quelques phrases. Mentionnez les matériaux, le public et les noms à conserver. Un descriptif plus riche produit un brouillon plus proche. Une zone vide est refusée avec **Prompt is required**. |
| **Optional source URL** | vide | Ajoute au descriptif du texte lu sur une page publique afin que le brouillon puisse suivre une page produit existante. Collez une adresse web complète, ou laissez vide. Une page lisible est ajoutée comme contexte supplémentaire. Une page que la boutique ne peut pas lire est ignorée et seul le descriptif est utilisé. |
| **Language** | la langue par défaut de la boutique | La langue de la boutique dans laquelle le texte du nouveau produit est enregistré. Les autres langues ne sont pas remplies par cet écran. Le nom, les descriptions, les méta et les tags ne sont enregistrés que dans cette langue. |
| **Default category ID** | 2 | L'identifiant de catégorie attribué comme catégorie par défaut du produit. Saisissez l'identifiant numérique depuis **Catalog**, **Categories**. 2 correspond généralement à Home. Le nouveau produit est placé dans cette catégorie. |
| **Generate data** | – | Demande le brouillon au modèle et l'affiche sous forme de texte structuré sous les boutons. Si la réponse ne peut pas être lue, vous voyez **Failed to parse AI response. Please try again.** |
| **Create product** | – | Insère le brouillon. En cas de succès, la zone affiche **Product #** suivi de l'identifiant du nouveau produit. Appuyer dessus avant de générer affiche **Generate the product first.** |

Le produit est créé sans photos, avec la première règle de taxe de la boutique et un prix tiré du brouillon ; ouvrez-le ensuite pour vérifier le prix, la taxe, les photos et le stock. Si aucune clé API n'est enregistrée, l'écran affiche **Add an API key in the module settings first.**

### 3.12 Cron

Ouvrez **Cron**. Cet écran construit des adresses que votre serveur appelle selon un calendrier pour remplir des champs de produits ou de catégories par petits lots. Rien ne s'exécute tout seul. La boutique ne fait rien tant que le serveur n'a pas demandé l'adresse.

![Cron screen](https://mypresta.eu/docs/images/docs/myaigrok-cron.webp)

*Cron : le panneau de l'adresse des catégories, puis le formulaire des produits avec son adresse et ses interrupteurs.*

**Ce que contient l'écran, de haut en bas :** un panneau **Category cron** avec l'adresse des catégories ; le formulaire **CRON JOB Settings – Generate product content using Grok** ; le formulaire **CRON JOB Settings - Generate category content using Grok** ; et un panneau **Cron parameters** avec l'adresse des produits, le champ choisi, la cible et la taille du lot.

**Important :** les adresses affichées sur cet écran se terminent au secret. Pour que l'appel fasse quelque chose, vous devez ajouter l'action à l'adresse. Les formes complètes d'adresse figurent à la section 4.2. De plus, **Enable Cron Feature** doit être sur **Yes**, sinon chaque appel cron, pour les produits comme pour les catégories, répond que la fonction est désactivée.

**Formulaire des produits** (appuyez sur **Save** en bas du formulaire) :

| Champ | À l'installation | Ce qu'il fait |
|---|---|---|
| **Enable Cron Feature** | No | Autorise le serveur à générer du texte selon un calendrier, sans qu'un employé clique dans le catalogue. Activez-le seulement après avoir enregistré le secret, le champ, la langue et le prompt ci-dessous. Le serveur doit toujours appeler l'adresse. Activé fait travailler l'adresse enregistrée. Cet interrupteur conditionne aussi l'adresse des catégories. |
| **Cron Job Secret Token** | une longue valeur aléatoire créée à l'installation | Un long mot de passe qui doit figurer dans l'adresse des produits. Sans lui, la boutique refuse l'appel. Conservez la valeur générée. Si vous la remplacez, copiez la nouvelle adresse dans le planificateur du serveur. Quiconque ne connaît pas ce secret ne peut pas exécuter le cron des produits. Le modifier invalide immédiatement l'ancienne adresse. Utilisez au moins 24 caractères (voir la section 5.10). |
| **Update Field** | description | L'unique champ de produit que cette commande cron réécrit : **name**, **description**, **description_short**, **meta_title**, **meta_description** ou **tags**. Pour remplir la description et les méta, créez deux commandes cron avec deux champs différents. Chaque exécution n'écrit que ce champ dans la langue choisie ci-dessous. |
| **Selected Products** | pendingGrok | Décide quels produits attendent encore. **pendingGrok** prend les produits jamais écrits avec succès par ce module dans aucun champ. **pendingField** prend les produits pas encore écrits pour ce champ précis, ce qui permet de lancer plusieurs tâches cron (par exemple description et nom) sur les mêmes produits. **emptyField** ne prend que les produits dont le champ choisi est vide dans la langue choisie. Chaque exécution ignore les produits qui ne correspondent plus, de sorte qu'un catalogue terminé cesse de changer. Les tentatives antérieures en échec ne comptent pas comme écrites et sont retentées. |
| **Product Categories** | aucune cochée | Limite le cron aux produits qui se trouvent dans les catégories cochées. Cochez une ou plusieurs catégories. Laissez l'arbre vide pour ignorer la catégorie et n'utiliser que les autres filtres. Voir la section 5.10 avant de cocher des catégories. |
| **Product ID list** | vide | Restreint le traitement à une liste explicite d'identifiants de produit. Saisissez les identifiants séparés par des virgules, par exemple 12,45,103. Les lettres et autres caractères sont supprimés à l'enregistrement. Seuls ces produits peuvent être mis à jour par cette commande. |
| **Language** | la langue par défaut de la boutique au moment de l'installation | La version linguistique du champ de produit que ce cron écrit. Choisissez une langue de la boutique. Les autres langues nécessitent leur propre commande cron. |
| **Product to update** | 5 products | Combien de produits correspondants sont traités à chaque appel de l'adresse (de 2 à 1000). Commencez par 5 ou 10 pour qu'un modèle lent n'atteigne pas la limite de temps du serveur. Augmentez dès qu'un traitement se termine proprement. |
| **Prompt Template** | aucun sélectionné | L'instruction enregistrée envoyée au modèle pour chaque produit de ce traitement. Choisissez un modèle activé dans Settings. Les marqueurs de ce modèle sont remplis produit par produit. Choisissez un modèle avant le premier appel. Changer le modèle plus tard n'affecte que le traitement suivant. |
| **Enable Debug** | No | Affiche ce que ferait le cron lorsque vous ouvrez l'adresse dans un navigateur, sans enregistrer de produits. Activez-le pendant que vous vérifiez la commande. Désactivez-le avant que le planificateur du serveur utilise la même adresse. Activé affiche le plan et n'écrit aucun texte dans le catalogue. |
| **CRON JOB interval** | Every Hour | Le rythme que vous comptez utiliser sur le serveur (de **Every 1 Minute** à **Every 6 Hours**). Faites-le correspondre au planificateur que vous créerez. Le module ne démarre pas le planificateur lui-même et n'impose pas cette valeur. |
| **Product Cron Job command** | – | Affiche l'adresse de base. Copiez-la, ajoutez l'action comme décrit à la section 4.2 et collez le résultat dans le planificateur de votre serveur. Vous pouvez créer autant de commandes cron que vous le souhaitez. |

**Le formulaire des catégories** suit la même logique avec son propre secret et son propre lot :

| Champ | À l'installation | Ce qu'il fait |
|---|---|---|
| **Cron Job Secret Token** | une longue valeur aléatoire créée à l'installation | Un long mot de passe qui doit figurer dans l'adresse des catégories. Il est distinct du secret des produits. Conservez la valeur générée. Les appels sans ce secret sont refusés. Le modifier invalide immédiatement l'ancienne adresse des catégories. |
| **Update Field** | description | L'unique champ de catégorie que cette commande réécrit : **name**, **description**, **meta_title** ou **meta_description**. Le nom, la description et les méta nécessitent chacun leur propre commande si vous voulez tous les remplir. |
| **Selected categories** | pendingGrok | Les trois mêmes choix que pour les produits (**pendingGrok**, **pendingField**, **emptyField**), appliqués aux catégories. Chaque exécution ignore les catégories qui ne correspondent plus. |
| **Language** | la langue par défaut de la boutique au moment de l'installation | La version linguistique du champ de catégorie que ce cron écrit. Les autres langues nécessitent leur propre commande. |
| **Categories to update** | 5 categories | Combien de catégories correspondantes sont traitées à chaque appel de l'adresse. Commencez par 5 ou 10. |
| **Prompt Template** | aucun sélectionné | L'instruction enregistrée envoyée au modèle pour chaque catégorie de ce traitement. Rédigez la consigne pour une catégorie, non pour un produit (par exemple avec `{category_name}`). |
| **Enable Debug** | No | Affiche ce que ferait le cron des catégories lorsque vous ouvrez l'adresse dans un navigateur, sans enregistrer de catégories. Désactivez-le avant que le planificateur utilise l'adresse. |
| **CRON JOB interval** | Every Hour | Le rythme que vous comptez utiliser sur le serveur. Ce n'est qu'un rappel. |
| **Category Cron Job command** | – | Affiche l'adresse de base à copier. Ajoutez l'action comme décrit à la section 4.2. |

Le cron des catégories ne touche jamais la catégorie racine (home) elle-même.

### 3.13 History

Ouvrez **History**. Cet écran est un rapport de chaque appel à Grok et sert de piste d'audit.

![History screen](https://mypresta.eu/docs/images/docs/myaigrok-history.webp)

*History : filtres, totaux, tableaux de répartition et liste des appels.*

Restreignez les cartes, les tableaux de répartition et la liste de l'historique à une tranche de générations. Cliquez sur une période prédéfinie ou réglez **From** et **To**. Puis, si vous le souhaitez, limitez par modèle, type, statut, langue, employé, un identifiant de produit ou de catégorie, ou un mot qui doit apparaître dans le prompt ou la réponse. Appuyez sur **Filter**. Seules les lignes correspondantes restent visibles. L'historique enregistré n'est pas supprimé et aucun produit n'est modifié.

| Contrôle | À l'installation | Ce qu'il fait |
|---|---|---|
| **Date presets** | This month | **Today**, **7 days**, **30 days**, **This month**, **All time**. |
| **From / To** | du premier jour du mois à aujourd'hui | Une plage de dates personnalisée. |
| **Model** | Any | Uniquement les appels effectués avec ce modèle. |
| **Type** | Any | Uniquement ce type d'appel (voir le tableau ci-dessous). |
| **Status** | Any | **Success** ou **Error**. |
| **Language** | Any | Uniquement les appels pour cette langue. |
| **Employee** | Any | Uniquement les appels lancés par cet employé. Les appels lancés par le cron n'ont pas d'employé. |
| **Product / category ID** | vide | Uniquement les lignes de cet identifiant (un produit, une catégorie, une page de contenu ou une marque portant ce numéro). |
| **Prompt or reply contains** | vide | Uniquement les lignes dont le prompt, la réponse ou le texte d'erreur contient le mot. |
| **Filter** | – | Applique les filtres. |

**Cartes :** **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total** et **Average time**. Un tiret signifie que Grok n'a pas renvoyé de nombre de tokens pour cet appel.

**Tableaux de répartition :** **By day**, **By model**, **By type**, **By language**, **By employee**, chacun avec **Group**, **Calls**, **Sent**, **Received** et **Total**. Un petit nombre à côté de Calls est le nombre d'erreurs de ce groupe.

**La liste** s'intitule **Prompt history** et affiche 50 lignes par page avec les colonnes **ID**, **Status** (un badge vert **Success** ou rouge **Error**), **Prompt**, **Reply / Error**, **Provider** (service, modèle et durée, plus un code de statut de Grok s'il y en a un), **Sent**, **Received**, **Total**, **Entity ID**, **Type** et **Timestamp**. L'action de ligne **View** ouvre le prompt et la réponse complets avec les tokens, et **Back to the list** revient en arrière. Si la ligne a été supprimée entre-temps, vous voyez **This log entry no longer exists.**

| Valeur de type | Signification |
|---|---|
| **general** | Une instruction libre du Playground ou du raccourci de la barre supérieure. |
| **singleCategory**, **singleCMS**, **singleBrand** | Le raccourci de la barre supérieure a été utilisé alors qu'une catégorie, une page de contenu ou une marque était ouverte. |
| **product_name**, **product_description**, **product_description_short**, **product_meta_title**, **product_meta_description**, **product_tags** | Un champ de produit a été écrit (ou tenté) par un bouton, un traitement en masse ou le cron. |
| **product_seo_pack** | Le pack SEO a écrit le nom, les descriptions et les méta en une seule fois. |
| **category_name**, **category_description**, **category_meta_title**, **category_meta_description**, **category_additional_description** | Un champ de catégorie a été écrit. |
| **error** | Un appel de produit en échec. |

Le bouton de barre d'outils **Clear list** supprime définitivement chaque ligne de History et le confirme par **Log list successfully deleted.** Cela supprime aussi les points de restauration des pages produit et remet à zéro le décompte du budget mensuel ; utilisez-le donc avec précaution.

### 3.14 Images

Ouvrez **Images**. Cet écran active ou désactive la recherche d'images sur la page produit et enregistre l'instruction envoyée au modèle.

![Images screen](https://mypresta.eu/docs/images/docs/myaigrok-images.webp)

*Images : l'interrupteur AI Image Finder et son prompt.*

Ces deux champs commandent la recherche d'images sur la page produit. Les enregistrer ne télécharge pas d'images et ne modifie pas le texte des produits. Appuyez sur **Save** ; la confirmation indique **Settings saved.**

| Champ | À l'installation | Ce qu'il fait |
|---|---|---|
| **AI Image Finder** | Activé | Affiche ou masque la recherche d'images sur la page d'édition du produit. Activez-le lorsque les éditeurs doivent chercher des photos du produit courant. Désactivez-le pour retirer ce bouton. Activé affiche la recherche. Désactivé la masque. Une image n'est importée qu'après confirmation par quelqu'un. |
| **AI Image Search Prompt** | Demande exactement 5 adresses de pages | L'instruction envoyée lorsqu'on recherche des images de produit. Les marqueurs du nom et de la description du produit sont remplacés par le produit courant. Conservez la demande d'une liste d'adresses de pages (l'écran parle d'un tableau JSON d'URL de pages). Modifiez la formulation si vous voulez des sites de fabricants ou un autre nombre de liens. Un prompt plus précis renvoie des pages plus pertinentes. Un prompt vague renvoie des liens sans rapport. Rien n'est enregistré tant qu'un éditeur n'a pas choisi d'image. |

### 3.15 Updates

Ouvrez **Updates** (à l'extrême droite de la barre).

![Updates screen](https://mypresta.eu/docs/images/docs/myaigrok-updates.webp)

*Updates : vérification manuelle, notifications automatiques et lien vers la page produit.*

L'écran s'intitule **MyPresta Updates**. Il vérifie auprès de MyPresta.eu s'il existe une version plus récente du module et peut vous avertir dans le back-office. Le catalogue et les textes générés restent tels quels.

| Champ | À l'installation | Ce qu'il fait |
|---|---|---|
| **Manual Check** | – | Contacte une fois les serveurs de mise à jour de MyPresta.eu et compare la version distante à celle de cette boutique. Cliquez sur **Check Now** après l'installation ou si vous soupçonnez une nouvelle version. **Module is up to date!** ou **New version available!** s'affiche à côté du bouton. |
| **Automatic Notifications** | Activé | Vérifie périodiquement (environ tous les 3 jours) les mises à jour dans le back-office. Réglez sur **Enabled** pour recevoir une bannière d'avertissement lorsqu'une version plus récente existe. Les employés voient alors une notification avec un lien vers plus de détails. Réglez sur **Disabled** si vous gérez les mises à jour uniquement à la main. Enregistrez avec **Save** ; la confirmation est **Update settings saved.** |
| **Product Page** | lien | Ouvre dans un nouvel onglet la page produit officielle de MyPresta pour ce module. |

### 3.16 Travailler sur la page d'édition du produit

Ouvrez un produit (**Catalog**, **Products**, le produit), puis l'onglet **Modules**, puis **My AI Grok**. Le bloc comporte jusqu'à quatre onglets : **Generate**, **Simulate**, **Photos** et **History**. Les onglets que vous voyez dépendent de **Product edit page Form** et **Product Edit History** à la section 3.4. Le produit doit avoir été enregistré au moins une fois.

![My AI Grok block on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-edit.webp)

*Page d'édition du produit, onglet Generate : pastilles de langue, comportement du texte existant et une carte par champ.*

**Onglet Generate.** Chaque bouton écrit un champ du produit et le texte est enregistré immédiatement sur le produit.

- **Language :** une pastille par langue active, plus **Every language**, qui exécute chaque langue l'une après l'autre.
- **If the field already has text :** **Replace**, **Add above**, **Add below** ou **Skip if filled**. Ils se comportent comme décrit à la section 3.9.
- **Cartes de champ :** **Description** (long texte avec une courte introduction et une liste de caractéristiques), **Short description** (un bref résumé simple, de moins de 400 caractères environ), **Name**, **Meta title** (environ 70 caractères), **Meta description** (environ 160 caractères) et **Tags** (une liste séparée par des virgules). Appuyez sur **Fill** sur la carte.
- **SEO pack :** **Fill all** remplit le nom, les deux descriptions et les deux champs méta en une seule requête. Il n'est disponible que dans l'onglet Generate. Rafraîchissez ensuite la page produit pour voir les nouvelles valeurs.
- **Use your own instruction or a saved prompt :** ouvrez cette section pour filtrer vos modèles enregistrés par titre ou texte, en choisir un (la première tuile **Standard brief** utilise une consigne toute prête pour le champ sur lequel vous appuyez) ou saisir votre propre texte dans **Instruction**. Laissez vide pour utiliser la consigne standard. Si aucun modèle ne correspond au filtre, vous voyez **No prompt matches that filter.**
- Le résultat est aussi affiché dans un panneau sous les cartes, avec le nombre de tokens.

Après un **Fill**, rechargez la page produit pour voir le nouveau texte dans le formulaire.

**Onglet Simulate.** Essayez d'abord un champ. La réponse reste sur cette page et le produit n'est pas modifié. Il a les mêmes pastilles de langue et cartes de champ, mais chaque carte a **Try** au lieu de **Fill**. Chaque Try crée tout de même une ligne dans History.

![Simulate tab on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-simulate.webp)

*Onglet Simulate : **Try** affiche la réponse sans enregistrer.*

**Onglet Photos.** Lorsque **AI Image Finder** est activé, Grok cherche des photos de ce produit.

![Photos tab on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-photos.webp)

*Onglet Photos : trouver des pages, cocher des photos, les ajouter au produit.*

1. Appuyez sur **Find pages**. Grok suggère des pages web, et le module lit des photos sur cinq d'entre elles au maximum (jusqu'à 24 photos).
2. Cochez les photos que vous voulez.
3. Appuyez sur **Add selected to this product**. Les photos sont téléchargées et rattachées ; la première photo que vous avez cochée devient l'image de couverture. Rien n'est enregistré avant cette étape.

Les adresses de réseaux privés ne sont jamais ouvertes. Si le moteur de recherche est désactivé, l'onglet indique que vous devez activer **AI Image Finder** sous Settings, General, puis rouvrir le produit.

**Onglet History.** Liste les écritures antérieures pour ce produit avec **When**, **Type**, **Status** et un bouton **Restore**. **Restore** demande **Restore the previous value?** et, une fois confirmé, remet le texte antérieur et vous invite à rafraîchir la page. La History de toute la boutique n'est pas supprimée. **Restore** n'est proposé que pour les lignes réussies qui ont conservé une valeur précédente. L'onglet affiche **No generations for this product yet.** lorsque la liste est vide.

![History tab on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-history.webp)

*Onglet History : écritures antérieures avec un bouton Restore.*

### 3.17 Autres endroits où le module apparaît

- **Boutons Generate with AI à côté des champs.** Dans le formulaire d'édition du produit, un petit bouton apparaît à côté de la description, de la description courte, du méta-titre et de la méta-description de chaque langue. Dans le formulaire d'édition de la catégorie, il apparaît à côté de la description, de la description complémentaire, du méta-titre et de la méta-description. Cliquez dessus. Si la boutique a plus d'une langue, on vous demande de choisir **Current language**, **All languages** ou **Cancel**. Le texte est placé dans le champ du formulaire. Enregistrez le produit ou la catégorie pour le conserver. Une consigne toute prête pour ce champ est utilisée, et vos règles Studio s'appliquent toujours. Si l'élément n'a jamais été enregistré, vous voyez **Save the product once before generating.** (ou **Save the category once before generating.**). L'interrupteur **Product edit page Form** ne masque que le bloc du module dans l'onglet **Modules** ; il ne supprime pas ces petits boutons.
- **Raccourci de la barre supérieure.** Avec **Admin Top Bar CTA** activé, une icône de baguette magique dans la barre supérieure ouvre une petite fenêtre : choisissez un **Template** (facultatif), saisissez l'instruction et appuyez sur **Generate**. Lorsque vous êtes sur l'écran d'édition d'une catégorie, d'une page de contenu ou d'une marque, les marqueurs correspondants sont remplis. La réponse s'affiche dans la fenêtre et rien n'est enregistré.
- **Liste des produits.** Un bouton **My AI Grok** à côté des actions groupées ouvre **Generate**, **Products**.

## 4. Front de la boutique

Le module n'a aucun écran destiné aux clients. Il n'affiche rien dans l'en-tête, le pied de page ou sur une page produit, catégorie ou de commande, et le thème n'a rien à afficher ni à surcharger. Les clients ne voient jamais d'outil de génération de texte ; ils ne voient que le texte que vous avez déjà enregistré dans le catalogue.

### 4.1 Adresses utilisées par le module lui-même

Deux adresses web de votre boutique appartiennent au module. Vous n'ouvrez jamais la première vous-même.

- L'**adresse du générateur** est appelée par les boutons du back-office (Fill, Try, Run, Playground, etc.). Elle est protégée par un secret intégré aux pages du back-office.
- L'**adresse cron** est appelée par le planificateur de votre serveur, ou par vous dans un navigateur lors des tests. Elle est décrite ci-dessous.

### 4.2 Adresse cron

L'adresse a la forme de l'adresse de votre boutique, suivie du chemin du module, du secret et de l'action. Remplacez les marqueurs par vos propres valeurs. Utilisez le secret que vous voyez sur l'écran **Cron** et ne le publiez jamais.

Pour les produits :

`https://YOUR-SHOP/module/myaigrok/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent`

Pour les catégories :

`https://YOUR-SHOP/module/myaigrok/cron?secret=YOUR_CATEGORY_SECRET&action=generateCategoryContent`

L'adresse affichée sur l'écran Cron s'arrête après le secret (le panneau des catégories ajoute une autre fin que la boutique n'utilise pas). Ajoutez vous-même la partie `action`. Sans action, la boutique répond **Invalid action!**

Le lot utilise les choix enregistrés sur l'écran Cron : champ, règle de sélection, langue, modèle, taille du lot et débogage. Chaque appel met à jour un lot puis s'arrête. Chaque écriture réussie apparaît aussi dans History avec la méthode **cron**.

Pour le planifier sur un serveur Linux, créez une tâche cron qui récupère l'adresse, par exemple toutes les dix minutes :

```
*/10 * * * * curl -s "https://YOUR-SHOP/module/myaigrok/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent" > /dev/null
```

Gardez l'adresse entre guillemets, car elle contient une esperluette. Sous Windows, utilisez le Planificateur de tâches avec une tâche qui ouvre l'adresse. Pour tester, réglez **Enable Debug** sur **Yes**, enregistrez et ouvrez l'adresse dans un navigateur : la page affiche le plan (les paramètres, les produits ou catégories sélectionnés et l'instruction finale) et n'enregistre rien. Ne partagez pas cette sortie, car elle contient les paramètres de votre adresse. Remettez le débogage sur **No** avant que le planificateur utilise l'adresse.

### 4.3 Ce que répond l'adresse cron

| Ce que vous voyez | Que faire |
|---|---|
| **Cron Job feature is disabled. You can enable it from the module settings.** | Réglez **Enable Cron Feature** sur **Yes** sur l'écran Cron et enregistrez. |
| **The token does not exist or it's wrong!** | Le secret est absent ou ne correspond pas. Recopiez le secret depuis l'écran Cron. |
| **Invalid action!** | La partie `action` est absente ou mal orthographiée. Utilisez l'une des deux formes de la section 4.2. |
| **All must include all mandatory parameters!** | Une valeur telle que le champ, la cible, la taille du lot, la langue ou le modèle est vide. Ouvrez l'écran Cron, remplissez-la et enregistrez. |
| **No valid product IDs provided.** | La Product ID list ne contient aucun nombre utilisable. Corrigez ou videz la liste et enregistrez. |
| **No products to update.** ou **No categories to update.** | Plus rien ne correspond à la règle. C'est la fin normale d'une tâche terminée. Changez la règle de sélection ou les filtres pour en traiter davantage. |
| **N products have been updated.** ou **N categories have been updated.** | Le lot est terminé. Le planificateur prendra le lot suivant à son prochain appel. |
| **Error!** suivi d'un message (par exemple **Monthly generation budget reached.** ou **Reply rejected by the studio quality gate.**) | Lisez le message et suivez le chapitre 5. Le traitement s'arrête à la première erreur. |
| **Error! The model returned an empty response.** | Augmentez **Max Tokens** dans Settings, Grok, ou essayez un autre modèle. |
| **Error! Could not save product** suivi d'un identifiant | Le produit n'a pas pu être enregistré avec le nouveau texte, par exemple parce que PrestaShop a refusé le texte. Vérifiez ce produit et relancez. |

## 5. Problèmes

### 5.1 L'installation est refusée

- **Symptôme :** **This module requires PHP 7.0.0 or newer. This server is running PHP** suivi de votre version, ou **Could not create the module database tables.**
- **Cause :** le PHP du serveur est trop ancien, ou l'utilisateur de la base de données n'a pas le droit de créer des tables.
- **Que faire :** demandez à votre hébergeur de passer à PHP 7.0 ou plus récent, ou de donner à l'utilisateur de la base de données la permission de créer des tables, puis réinstallez.

### 5.2 L'entrée de menu ou le bloc produit est absent

- **Symptôme :** pas d'**AI Content Generator** sous **Modules**, ou pas de bloc **My AI Grok** dans l'onglet **Modules** du produit.
- **Cause :** un cache périmé, des droits manquants sur le profil de votre employé, ou un interrupteur désactivé.
- **Que faire :** videz le cache dans **Advanced Parameters**, **Performance**. Dans **Advanced Parameters**, **Team**, **Permissions**, vérifiez que votre profil peut ouvrir les écrans du module. Si le menu manque toujours, désinstallez puis réinstallez le module. Pour le bloc produit, vérifiez **Product edit page Form** et **Product Edit History** dans Settings, General, et enregistrez le produit une fois pour qu'il ait un identifiant.

### 5.3 La clé est refusée ou manquante

- **Symptôme :** **Grok API KEY field is invalid!** à l'enregistrement, ou **The Grok API key is not set. Add it in the module settings.** lors de la génération, ou une ligne d'erreur dans History après chaque tentative.
- **Cause :** le champ de la clé est vide ou trop court, ou la clé a été copiée avec une faute de frappe ou a été révoquée chez xAI.
- **Que faire :** ouvrez **Settings**, **Grok**, collez une clé neuve depuis https://console.x.ai et appuyez sur **Save**. Puis ouvrez **History**, filtrez **Status** sur **Error** et ouvrez la ligne la plus récente pour lire la réponse exacte de Grok.

### 5.4 Le modèle est refusé

- **Symptôme :** **OpenAi Model field is invalid!**, ou des erreurs dans History indiquant que le modèle n'existe pas ou que vous n'y avez pas accès.
- **Cause :** le nom du modèle est trop court, mal saisi, ou votre compte xAI ne peut pas appeler ce modèle.
- **Que faire :** dans **Settings**, **Grok**, choisissez l'un des modèles intégrés, ou ajoutez l'identifiant exact de votre compte xAI avec **Add model**, puis enregistrez.

### 5.5 L'appel dépasse le délai d'attente

- **Symptôme :** **Grok request timed out after N seconds. The model may be overloaded, or the timeout is too low for this prompt.** ou, sur un écran, **The request timed out or the shop blocked it.**
- **Cause :** un modèle lent, une réponse très longue, un service xAI chargé, ou un serveur qui bloque les requêtes longues.
- **Que faire :** augmentez **API timeout (seconds)** dans **Settings**, **General** (jusqu'à 600), réduisez **Max Tokens** pour les champs courts, ou essayez un modèle plus rapide. Pour le cron, réduisez **Product to update** afin qu'un lot tienne dans la limite de temps du serveur.

### 5.6 La réponse est vide ou coupée

- **Symptôme :** **The model hit the token limit before returning any text. Increase "Max Tokens" in the module settings — reasoning models spend part of that budget on thinking.** ou **The response was blocked by the provider content filter. Try rewording the prompt.** ou **The model returned an empty response.**
- **Que faire :** augmentez **Max Tokens** dans **Settings**, **Grok**. Pour une réponse bloquée, reformulez l'instruction. Puis réessayez.

### 5.7 Le budget mensuel est atteint

- **Symptôme :** **Monthly generation budget reached. Raise it in the studio settings or wait until next month.**
- **Que faire :** ouvrez **Settings**, **Studio**, augmentez **Monthly generation budget** ou réglez-le sur 0, et enregistrez. Les appels en échec ne sont pas comptés.

### 5.8 Une réponse est rejetée à cause d'un mot interdit

- **Symptôme :** **The reply was rejected because it contains a forbidden word from the studio settings.** (le cron affiche **Reply rejected by the studio quality gate.**). Le produit reste inchangé et History affiche une ligne d'erreur.
- **Que faire :** relancez la génération (la formulation diffère à chaque fois), raccourcissez **Forbidden words** dans **Settings**, **Studio**, ou réglez **Quality gate** sur **Disabled**.

### 5.9 Un champ est ignoré ou le texte est incorrect

- **Symptôme :** une ligne indique **skipped** avec **Product skipped.** (ou **Category skipped.**), ou le texte a été ajouté à l'ancien au lieu de le remplacer.
- **Cause :** **Existing text** était réglé sur **Skip if filled**, **Add above** ou **Add below**.
- **Que faire :** choisissez **Replace** et relancez. Pour annuler une écriture indésirable sur un produit, utilisez l'onglet **History** du produit et appuyez sur **Restore**.

### 5.10 Le cron ne fait rien, se répète, ou l'adresse cesse de fonctionner

- **Symptôme :** le planificateur s'exécute mais rien n'est écrit, ou les mêmes produits sont réécrits, ou une adresse qui fonctionnait hier répond maintenant **The token does not exist or it's wrong!**
- **Cron désactivé :** **Cron Job feature is disabled.** Réglez **Enable Cron Feature** sur **Yes** sur l'écran Cron et enregistrez.
- **Pas d'action dans l'adresse :** vous obtenez **Invalid action!** Ajoutez l'action comme indiqué à la section 4.2.
- **Débogage laissé actif :** le débogage affiche le plan et n'enregistre jamais. Réglez **Enable Debug** sur **No** et enregistrez.
- **Pas de modèle :** si **Prompt Template** est vide, l'instruction envoyée est vide. Choisissez un modèle activé et enregistrez.
- **Secret remplacé :** le bouton **Generate Token** à côté du secret n'a aucune fonction dans cette version ; saisissez ou collez donc vous-même un long secret aléatoire. Un secret de moins de 24 caractères est remplacé par un nouveau secret aléatoire la prochaine fois qu'une page quelconque du back-office s'ouvre, et l'ancienne adresse cesse alors de fonctionner. Recopiez le secret depuis l'écran Cron.
- **Toujours les mêmes produits :** lorsque vous cochez **Product Categories**, les produits dont la catégorie par défaut est cochée sont sélectionnés à chaque appel, même si la règle de sélection indique qu'ils ne sont plus en attente. Laissez l'arbre des catégories vide et limitez le cron avec **Product ID list**, ou utilisez l'écran **Generate** pour un travail limité par catégorie.
- **Erreurs du serveur :** les erreurs du cron ne sont affichées que dans la réponse de l'adresse ; elles ne sont pas enregistrées dans History. Exécutez l'adresse dans un navigateur avec le débogage activé pour les lire.

### 5.11 Un traitement en masse s'arrête à mi-chemin

- **Symptôme :** la ligne d'état ne bouge plus, ou certaines lignes n'ont pas de résultat.
- **Cause :** l'onglet du navigateur a été fermé ou rechargé, l'ordinateur s'est mis en veille, ou un appel a dépassé le délai d'attente.
- **Que faire :** appuyez de nouveau sur **Run**. Choisissez **Skip if filled** sous **Existing text** pour ne pas payer deux fois les champs terminés. Les lignes en erreur indiquent la raison ; la même raison figure dans History.

### 5.12 Le formulaire Generate category content ne fait rien

- **Symptôme :** après avoir appuyé sur **Generate content** dans le formulaire sous la liste des catégories, vous arrivez sur le filtre des catégories et rien n'est écrit.
- **Que faire :** utilisez le bouton **Run on the categories below** situé au-dessus de ce formulaire. Sur les écrans de filtre des produits et des catégories, le bouton **Module settings** n'ouvre pas les réglages de ce module ; utilisez l'élément **Settings** de la barre de navigation.

### 5.13 Problèmes avec les photos du produit (Photos)

- **Symptôme :** **Find pages** n'affiche aucune photo, ou vous voyez **No images could be imported.** suivi de détails.
- **Cause :** Grok a suggéré des pages sans photos exploitables, la page a bloqué le téléchargement de la boutique, l'adresse pointait vers un réseau privé, ou le fichier n'était pas une image valide.
- **Que faire :** appuyez de nouveau sur **Find pages**, reformulez **AI Image Search Prompt** sur l'écran **Images** (par exemple en demandant des sites de fabricants), ou téléversez les photos à la main.

### 5.14 L'écran New product échoue

- **Symptôme :** **Add an API key in the module settings first.**, **Prompt is required**, **Failed to parse AI response. Please try again.** ou **Failed to create product**.
- **Que faire :** enregistrez la clé API dans **Settings**, **Grok**, rédigez un descriptif et appuyez de nouveau sur **Generate data**. Augmentez **Max Tokens** si la réponse semble coupée. Si **Create product** échoue, vérifiez que le brouillon n'a pas un nom vide.

### 5.15 La restauration est impossible

- **Symptôme :** **Error! This log entry has no previous value to restore.** ou **Error! Nothing to restore for this entry.**
- **Cause :** cette ligne n'a pas conservé de valeur antérieure (par exemple un prompt libre, ou un champ qui était vide).
- **Que faire :** utilisez une autre ligne du même produit, ou corrigez le texte à la main.

### 5.16 L'écran indique que le token est invalide

- **Symptôme :** **Error! Invalid token!** en appuyant sur un bouton après une longue pause.
- **Cause :** la page du back-office a été ouverte avant le renouvellement du secret interne du module.
- **Que faire :** rechargez la page et réessayez.

### 5.17 Le texte est plus court que prévu

- **Cause :** PrestaShop limite certains champs. Le module raccourcit un nom à 128 caractères, une description courte à 800, un méta-titre à 69 et une méta-description à 159.
- **Que faire :** utilisez une instruction plus concise, par exemple en demandant un titre de moins de 60 caractères.

### 5.18 Journal technique et débogage

- **Symptôme :** vous avez besoin de plus de détails sur un appel en échec, ou le journal de PrestaShop grossit.
- **Que faire :** activez **Debug mode** dans **Settings**, **General**, répétez l'action, lisez les nouvelles entrées dans **Advanced Parameters**, **Logs**, puis désactivez de nouveau le débogage. Remettez aussi **Enable Debug** de l'écran Cron sur **No** après les essais.

### 5.19 Notifications de mise à jour

- **Symptôme :** **Check Now** n'affiche ni **Module is up to date!** ni **New version available!**
- **Cause :** votre serveur ne peut pas joindre le serveur de mise à jour de MyPresta.eu, qui est interrogé avec un court délai.
- **Que faire :** autorisez les connexions sortantes ou réessayez plus tard. Le module fonctionne sans cette vérification.

## 6. Pour les développeurs

### 6.1 Vue d'ensemble

- **Classe principale :** `myaigrok` (fichier `myaigrok.php`), étend `Module`, version `1.1.0`, `bootstrap = true`, `need_instance = 0`.
- **Nom dans la liste des modules :** `My AI Grok - AI content generation`. **Auteur :** `MyPresta.eu`. **Tab :** `front_office_features`.
- **Compatibilité :** PrestaShop 1.6 jusqu'à 9.99.99 (`ps_versions_compliancy`). PHP minimum 7.0.0 (`MIN_PHP_VERSION`) ; `install()` refuse un PHP plus ancien avec un message traduit.
- **Classes :** l'espace de noms `MyAIGrok\` est chargé par `autoload.php` (sans Composer). `MyAIGrok\OpenAIService` est un client cURL pour `https://api.x.ai/v1` (`/chat/completions`, `/models`) ; `MyAIGrok\Studio` applique le style maison, le budget mensuel et le contrôle qualité. Le vérificateur de mise à jour `myaigrokUpdate` (dans `lib/updateChecker.php`) étend `myaigrok`.
- **Flux de données :** les réglages sont dans `ps_configuration` (préfixe `MYPRESTA_MYAIGROK_`). Les boutons du back-office et les traitements en masse appellent le contrôleur front `ajax` ; les planificateurs appellent le contrôleur front `cron`. Les deux lisent les réglages, font passer le prompt par `Studio::gate()` (vérification du budget et `Studio::decorate()`), l'envoient avec `OpenAIService::createChatCompletion()`, vérifient la réponse avec `Studio::inspect()`, écrivent le texte dans l'objet produit ou catégorie et insèrent une ligne dans `myaigrok_log`.
- **Appels au fournisseur :** les paramètres de modèle `temperature`, `max_tokens`, `top_p`, `frequency_penalty`, `presence_penalty` sont envoyés ; les paramètres qu'un modèle rejette sont appris et enregistrés dans `MYPRESTA_MYAIGROK_MODEL_CAPS`. La vérification du certificat n'est désactivée que lorsque la boutique elle-même tourne sur localhost.

### 6.2 Fichiers

| Chemin | Rôle |
|---|---|
| `myaigrok.php` | Classe du module : installation, désinstallation, hooks, écrans Settings (HelperForm), Dashboard, placement du menu, onglet Modules du produit. |
| `autoload.php` | Chargeur de classes pour l'espace de noms `MyAIGrok\`. |
| `src/OpenAIService.php` | Client cURL pour Grok : chat completions, liste des modèles, délais d'attente, adaptation des paramètres. |
| `src/Studio.php` | `gate()`, `decorate()`, `inspect()`, `overBudget()`, prompts du pack SEO et des textes alt. |
| `controllers/admin/AdminMyAIGrok.php` | Écrans Generate (filtres de produits et de catégories, panneaux de traitement en masse). |
| `controllers/admin/AdminMyAIGrokProductCreator.php` | Écran New product et ses actions Ajax. |
| `controllers/admin/AdminMyAIGrokCron.php` | Formulaires Cron. |
| `controllers/admin/AdminMyAIGrokUsage.php` | Rapport et liste History. |
| `controllers/admin/AdminMyAIGrokImageFinder.php` | Écran Images et actions de recherche et d'import d'images. |
| `controllers/admin/AdminMyAIGrokMain.php`, `AdminMyAIGrokSettings.php` | Redirigent vers la page de configuration du module. |
| `controllers/front/ajax.php` | Point d'accès de génération utilisé par le back-office. |
| `controllers/front/cron.php` | Point d'accès cron. |
| `lib/sectionHelp.php` | Contenu du panneau latéral Help. |
| `lib/updateChecker.php` | Vérification des mises à jour MyPresta.eu (`dev.mypresta.eu/update/get.php` ; envoie le nom du module, la version, un marqueur de clé de licence et l'adresse de la boutique). |
| `lib/prestashop9compatibility.php` | Aides de compatibilité (chiffrement des tokens pour PS 9). |
| `lib/searchTool/` | Petit assistant d'autocomplétion chargé sur la page de configuration. |
| `views/templates/hook/*.tpl` | Modèles de hooks et d'écrans (nav, subnav, dashboard, usage, générateurs en masse, playground, onglets produit, panneaux cron). |
| `views/templates/admin/product_creator.tpl` | Écran New product. |
| `views/js/back.js`, `product-fields.js`, `image-finder.js`, `admin-products-bulk.js`, `admin-help.js`, `dashboard.js`, `chart.min.js` | Scripts du back-office. |
| `views/css/back.css`, `admin-nav.css`, `stats.css` | Styles du back-office. |
| `translations/{iso}.php` | Fichiers de traduction (nombreuses langues). |

### 6.3 Contrôleurs

| Contrôleur | Parent et route | Remarques |
|---|---|---|
| `AdminMyAIGrokMain` | Enfant de l'onglet parent Modules (`AdminParentModulesSf`, sinon `AdminParentModules`, sinon `AdminModules`), nom de menu **AI Content Generator** | Redirige vers `AdminModules&configure=myaigrok&mds_tab=dashboard`. |
| `AdminMyAIGrokSettings` | Enfant caché (`active = 0`) de Main | Redirige vers `mds_tab=settings`. |
| `AdminMyAIGrok` | Enfant caché de Main | `mds_sub=products` ou `categories` ; actions de soumission `filterProducts`, `filterCategories`. |
| `AdminMyAIGrokProductCreator` | Enfant caché de Main | Actions Ajax `generateProductData`, `extractImages`, `createProduct`, `generateImages` (marqueur). |
| `AdminMyAIGrokCron` | Enfant caché de Main | Soumission `submitCronUpdate`, `submitCatCronUpdate`. |
| `AdminMyAIGrokUsage` | Enfant caché de Main | Filtres `stats_preset`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_entity`, `stats_q` ; `clear_log` supprime toutes les lignes ; action de ligne `view`. |
| `AdminMyAIGrokImageFinder` | Enfant caché de Main | Actions `searchImages`, `extractImages`, `saveImages` ; hôtes de réseaux privés refusés ; jusqu'à 5 pages et 24 photos. |

Les permissions sont les droits d'onglet standard du back-office pour ces contrôleurs. Chaque contrôleur d'administration redirige vers `AdminHome` lorsque le module est désactivé. `AdminModules` avec `configure=myaigrok` accepte `mds_tab` (`dashboard`, `settings`, `updates`), `mds_sub` (`general`, `openai`, `studio`, `templates`, `playground` ; `openai` est l'onglet Grok) et `mcg_preset` (`today`, `7`, `30`, `90`, `month`, `all`) ainsi que `mds_from`, `mds_to`.

**Front `ajax`** (`module/myaigrok/ajax`) : exige `secret_token` égal à `MYPRESTA_MYAIGROK_TOKEN`, sinon `Error! Invalid token!`. Il n'y a aucune vérification d'employé ; le token présent dans la page est la seule protection. Actions : `initiatePrompt`, `updateSettings` (écrit les clés d'échantillonnage), `updateProduct`, `updateCategory`, `initiateProductRestore`, `generateSeoPack`, `generateAltTexts` (pas de bouton dans l'interface). `updateProduct` et `updateCategory` acceptent les valeurs de `behavior` `replace`, `keep`, `keep_top`, `keep_end` et `single_product` / `single_category` (essai à blanc, rien n'est enregistré).

**Front `cron`** (`module/myaigrok/cron`) : le constructeur fait tout le travail. Il se termine avec un message lorsque `ENABLE_CRON` vaut 0, puis exige `secret` égal à `MYPRESTA_MYAIGROK_SECRET` ou à `MYPRESTA_MYAIGROK_CAT_SECRET` (l'un ou l'autre secret est accepté pour l'une ou l'autre action). `action` doit être `generateProductContent` ou `generateCategoryContent`, sinon `Invalid action!`. Le paramètre `entity` affiché dans l'adresse des catégories de l'écran Cron n'est pas lu. Des paramètres facultatifs remplacent les choix enregistrés : pour les produits `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `categories`, `productIds` ; pour les catégories `updatedField`, `categoryTarget`, `categoriesToUpdate`, `languageId`, `promptTemplateId`, `debug`. Cibles autorisées : `pendingGrok`, `pendingField`, `emptyField` ; une valeur erronée répond `productTarget parameter is wrong! Allowed values: ...`, un champ erroné `updatedField parameter is wrong!`. La condition de liste de catégories pour les produits est ajoutée sous la forme `p.id_product IN (...) OR p.id_category_default IN (...)` sans parenthèses ; elle se combine donc avec les autres conditions selon la précédence SQL (voir la section 5.10). Les erreurs du cron sont affichées (echo) et la requête se termine ; elles ne sont pas écrites dans `myaigrok_log`.

Ressources référencées mais non livrées dans le paquet : `views/js/admin.js` et `views/css/admin.css` (contrôleurs Main et Settings, inaccessibles car ils redirigent d'abord) et `views/js/product_creator.js` et `views/css/product_creator.css` (écran New product ; l'écran utilise `back.js`). Les fonctions `generateTokenAndFill()` et `generateCategoryTokenAndFill()` appelées par les boutons **Generate Token** ne sont définies dans aucun script livré. Les boutons **Module settings** des formulaires de filtre de Generate pointent vers `configure=mychatgpt`.

### 6.4 Hooks

Enregistrés dans `install()` :

| Hook | Comportement |
|---|---|
| `displayAdminProductsExtra` | Affiche le bloc My AI Grok (`product-tab-wrapper.tpl`) dans l'onglet Modules du produit. Ne renvoie rien lorsque `PRODUCT` et `PRODUCT_LOG` valent tous deux 0. |
| `displayBackOfficeHeader` | Appelle `ensureLongSecrets()` et `placeModuleMenu()`, ajoute le CSS et le JS, publie des variables JS, enregistre une fois l'onglet Image Finder (`IMAGEFINDER_TAB_OK`), charge `product-fields.js` sur les pages produit et catégorie ainsi que le script du bouton de la liste des produits. |
| `displayBackOfficeTop` | Publie `admin_controller_url` et les identifiants de la catégorie, de la page CMS ou de la marque en cours d'édition, et renvoie le générateur de la barre supérieure lorsque `TOPCTA` vaut 1. |
| `dashboardZoneTwo` | Affiche `dashboard.tpl`. Réenregistré dans `displayBackOfficeHeader` s'il manque. |
| `displayHeader`, `displayFooter` | Enregistrés ; les méthodes sont vides. |
| `displayAdminProductsMainStepLeftColumnMiddle`, `displayAdminProductsMainStepLeftColumnBottom`, `actionProductFormBuilderModifier` | Enregistrés ; les méthodes renvoient une chaîne vide ou rien. |

Le module ne surcharge ni `enable()` ni `disable()`. Désactiver le module fait seulement que ses contrôleurs d'administration redirigent vers le tableau de bord de PrestaShop. La méthode `hookActionProductGridDataModifier` existe mais n'est pas enregistrée. Le module n'expose aucun hook qui lui soit propre.

### 6.5 Overrides

Le module n'a aucun override.

### 6.6 Base de données

| Table | Contenu |
|---|---|
| `{prefix}myaigrok_prompt` | `id_prompt`, `status`, `title` (128), `prompt` (text), `date_generated`. Alimentée avec 16 modèles à l'installation. |
| `{prefix}myaigrok_log` | `id_log`, `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, `type`, `method`, `status`, `ai_service`, `model`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `error_message`, `prompt`, `reply`, paires `old_` et `new_` pour name, description, description_short, meta_title, meta_description et tags, `date_updated`. Clés sur `id_product` et `status`. |

Les trois colonnes de tokens sont ajoutées par `ensureUsageColumns()` à la première utilisation lorsqu'une table plus ancienne en est dépourvue. La désinstallation supprime les deux tables, tous les onglets d'administration (y compris l'ancien `AdminMyAIGrokChangelog`) et les clés de configuration principales. Les textes générés pour les produits et les catégories ne sont pas touchés.

### 6.7 Clés et traductions

Toutes les clés commencent par `MYPRESTA_MYAIGROK_`. Valeurs après l'installation :

| Clé | Valeur |
|---|---|
| `LIVE_MODE`, `DEBUG_MODE` | 0, 0 |
| `TIMEOUT` | 120 (borné à 10–600 à l'enregistrement) |
| `PRODUCT_LOG`, `TOPCTA`, `PRODUCT`, `IMAGEFINDER_ENABLE` | 1 chacune |
| `IMAGEFINDER_PROMPT` | Prompt par défaut demandant 5 URL de pages sous forme de tableau JSON |
| `TOKEN`, `SECRET`, `CAT_SECRET` | 32 caractères aléatoires ; `ensureLongSecrets()` régénère tout secret de moins de 24 caractères |
| `API_KEY`, `MODEL`, `EXTRA_MODELS`, `MODEL_CAPS` | un seul espace, `grok-4.7`, vide, vide |
| `TEMPERATURE`, `MAX_TOKENS`, `TOP_P`, `FREQ_PEN`, `PRES_PEN` | 0.7, 3200, 1, 0, 0 |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | vide |
| `BUDGET`, `QUALITY` | 0, 1 |
| `ENABLE_CRON`, `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 0, 6, 6 |
| `updatedField`, `productTarget`, `productsToUpdate`, `promptTemplateId`, `languageId`, `interval_select`, `debug`, `productIdsList`, `categories` | `description`, `pendingGrok`, 5, vide, langue par défaut de la boutique, vide, 0, vide, vide |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catpromptTemplateId`, `catlanguageId`, `catdebug` | `description`, `pendingGrok`, 5, vide, langue par défaut de la boutique, 0 |
| `IMAGEFINDER_TAB_OK` | Défini après le premier chargement du back-office |

Les écrans Generate enregistrent aussi leurs dernières valeurs de filtre sous `MYPRESTA_MYAIGROK_FIELD`, `_LANGUAGE`, `_CONTENT`, `_DELAY`, `_EXISTING`, `_HISTORY`, `_STATUS`, `_STOCK`, `_PROD_IDS`, `_PROD_REF`, `_PROD_DATE_FROM`, `_PROD_DATE_TO`, `_PROD_MIN_ID`, `_PROD_MAX_ID`, `_PROD_LIMIT`, `_CATEGORIES`, `_BRANDS`. La désinstallation ne les supprime pas. Le vérificateur de mise à jour utilise `mypresta_updates`, `update_myaigrok` et `updatev_myaigrok`. Chaque chargement de la page de configuration dans le back-office supprime les clés obsolètes `GEMINI_API_KEY`, `GEMINI_MODEL` et `ACTIVE_SERVICE`.

**Traductions :** pour ajouter une langue, créez `translations/{iso}.php`. Les chaînes du module utilisent `$this->l()` et `{l s='...' mod='myaigrok'}`. Les contrôleurs d'administration utilisent `trans()` avec des domaines tels que `Admin.MyAIGrok` et `Admin.MyAIGrokCron` sur PrestaShop 8 et 9, et le `l()` du module sur 1.6 et 1.7. Ces chaînes ne sont pas traduites : les messages construits dans `back.js` et les textes de repli de `product-fields.js`, les réponses en texte brut du cron, les textes d'erreur d'Image Finder et de New product, et les prompts en anglais construits par `Studio`. Les descriptions des champs (What it does / How to configure / Effect) sont construites par `fieldHelp()` dans `myaigrok.php` et par l'enveloppe `help()` de chaque contrôleur d'administration ; les textes du générateur en masse et du Playground se trouvent dans les modèles ; les textes du panneau Help sont dans `lib/sectionHelp.php`.

### 6.8 Étendre

- Ajoutez ou modifiez des modèles de prompt dans `myaigrok_prompt` (ou sur l'écran Prompt templates) ; les marqueurs sont remplacés dans `ajax.php` et `cron.php`.
- Ajoutez des identifiants de modèle via **Add a Grok model** ; ils sont enregistrés dans `EXTRA_MODELS`.
- Façonnez la sortie avec les règles Studio ; elles sont appliquées dans `Studio::decorate()`.
- Appelez le point d'accès cron avec des paramètres de remplacement pour exécuter différentes tâches sans toucher au formulaire enregistré.
- Le front office n'affiche aucun modèle du module, le thème n'a donc rien à surcharger.

## 7. Aide

Page produit du module : https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-grok-ai.html

Pour contacter le support au sujet du module :

1. Connectez-vous à votre compte client sur mypresta.eu.
2. Allez au formulaire de contact.
3. Choisissez le sujet **Support for paid modules**.
4. Décrivez ce que vous avez fait et ce que vous avez vu. Ajoutez le numéro de version affiché à côté du nom du module en haut de ses écrans et, si une génération a échoué, le texte de l'erreur de la colonne **Reply / Error** de **History**.
