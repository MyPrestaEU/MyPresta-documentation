---
title: "PrestaMind AI - documentation et manuel utilisateur"
sidebar:
  label: "PrestaMind AI - documentation et manuel utilisateur"
description: "Configuration et dépannage pour une boutique qui a déjà PrestaMind AI installé."
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module PrestaMind AI - AI assistant, live chat and chatbot sur MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot/)
>
> ---


Les noms de boutons et d'onglets ci-dessous sont les libellés anglais de l'écran du module. Si la langue de l'employé est le français, PrestaShop affiche la traduction de ce même libellé lorsque le module la contient.

## 1. Exigences

PrestaShop 1.7.6, 8 et 9. PHP dans la version exigée par cette installation de PrestaShop. Le module appelle l'extension cURL, et OpenSSL ou libsodium, pour enregistrer les clés des fournisseurs. Il n'exige pas un autre module.

Vous avez besoin d'un compte et d'une clé API chez le fournisseur choisi, sauf si vous restez sur la démo hors ligne. Un serveur local compatible OpenAI (Ollama, vLLM, LM Studio) doit avoir une adresse que le serveur de la boutique peut ouvrir. Le suivi DHL en direct exige une clé gratuite du site développeur DHL. Le suivi InPost en direct n'exige pas de clé.

Un grand catalogue allonge la première indexation. Les embeddings envoient le texte de chaque produit une fois au fournisseur d'embeddings, donc le premier passage consomme des jetons et du temps. La recherche par mots-clés ne le fait pas.

## 2. Installation

1. Envoyez le module dans **Module Manager** et appuyez sur **Install**.
2. La question **Delete this module and all its data (conversations, knowledge index, settings)?** apparaît à la désinstallation, pas à l'installation.
3. Après l'installation, l'entrée **PrestaMind AI** est sous **Customer service**. Si ce menu n'existe pas, l'entrée est sous **Improve**. **Configure** sur la ligne du module ouvre la même page.
4. L'installation ne vide pas le cache de la boutique. La bulle reste cachée tant que vous ne l'activez pas.

La désinstallation retire l'entrée de menu, les tables du module et les réglages enregistrés, y compris les clés. Les commandes, produits, pages CMS et règles de panier déjà enregistrés dans PrestaShop restent. Le dossier du module reste sur le disque tant que vous ne le supprimez pas. Une nouvelle installation commence avec des conversations vides et un index vide. Elle ne restaure pas les précédents.

## 3. Configuration et travail quotidien

### 3.1 Le processus complet

Vous commencez dans le back-office. Le visiteur commence sur la boutique.

1. Ouvrez **PrestaMind AI**. Dans **Settings**, puis **Health**, corrigez chaque ligne qui n'est pas OK.
2. Dans **Model provider**, cliquez sur la tuile du fournisseur, collez la clé API, choisissez le modèle principal et le modèle rapide, saisissez les prix et appuyez sur **Save and test the connection**.
3. Dans **Knowledge** de la page de réglages, choisissez ce qui est indexé. Puis ouvrez l'onglet **Knowledge** et appuyez sur **Reindex now**.
4. Dans **Playground**, envoyez une question produit, une question livraison et une question commande. Chaque envoi dépense des jetons chez le vrai fournisseur.
5. Dans **Settings**, puis **Widget**, laissez **Show the assistant to all visitors** sur off. Mettez votre IP publique dans **Preview only for these IP addresses**, enregistrez et ouvrez la boutique. Quand les réponses sont bonnes, activez le widget pour tout le monde et videz un cache de page entière si la bulle n'apparaît pas.
6. Le visiteur ouvre la bulle, écrit une question et appuie sur la flèche. Le module lit le prix, le stock, la livraison ou la commande dans la boutique quand la question en a besoin, et montre la réponse dans la même fenêtre.
7. Une remise n'existe que lorsqu'une offre que vous avez enregistrée correspond au panier. **Add to cart**, **Send the return request** et **Send the quote request** attendent le clic du visiteur.
8. Si le visiteur appuie sur **Talk to a person**, la ligne est dans **Escalations** et, si la console est active, aussi sur le bouton **Live chats**. Vous appuyez sur **Take over this conversation**, vous écrivez la réponse, vous appuyez sur **Send**, puis sur **Give back to the assistant**. Le statut **new**, **open** ou **done** n'envoie pas d'e-mail au visiteur.

### 3.2 Où sont les écrans

Onglets, dans cet ordre : **Dashboard**, **Live stats**, **History**, **Conversations**, **Knowledge**, **Triggers & offers**, **Playground**, **Quality tests**, **Escalations**, **Settings**, **Updates**.

**Settings** a sa propre rangée : **Health**, **Widget**, **Model provider**, **Knowledge**, **Limits & cost**, **Privacy**, **Escalation**, **Cart reminders**, **Couriers**, **Tools**. Chaque sous-page n'enregistre que ses champs. **Save** affiche **Settings saved.** L'enregistrement ne supprime ni les conversations ni l'index.

Le tableau de bord de la boutique, après la connexion, montre un bloc avec les chiffres de l'assistant, les clients qui attendent une personne et les dernières conversations.

### 3.3 Dashboard

![Dashboard](https://mypresta.eu/docs/images/docs/prestamindai-dashboard.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle Dashboard.

Lecture seule. Choisissez **today**, **7**, **30** ou **90** jours, ou réglez **From** et **To**. Vous pouvez limiter les appels IA par modèle, fournisseur, type (réponses ou embeddings) ou statut, puis appuyez sur **Filter**. **See full history** ouvre **History**.

L'écran montre le chiffre d'affaires des commandes passées dans les 7 jours après un chat, les conversations, combien ont été résolues sans personne, les notes, les jetons envoyés et reçus et le coût estimé. Le coût prend le prix enregistré sur chaque appel. Ce n'est pas une facture du fournisseur. Le groupe témoin se règle dans **Settings**, puis **Privacy**, si vous voulez comparer la valeur des commandes.

### 3.4 Live stats

![Live stats](https://mypresta.eu/docs/images/docs/prestamindai-live.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle Live stats.

Laissez la page ouverte. Les nouvelles lignes arrivent en haut toutes les quelques secondes. Les pastilles masquent les clients, l'assistant, l'équipe, les outils ou les escalades. Cherchez dans le texte ou saisissez un numéro de chat. **thumbs down only** garde les réponses que les visiteurs ont rejetées. **Pause** fige la vue. **Compact** resserre les lignes. **Reset filters** montre tout. **Clear** vide la vue de cette page. **Open chat** ouvre la conversation. **Take over** vous laisse répondre.

La page ne lit que les conversations enregistrées. Les filtres restent dans ce navigateur. Les numéros de carte, IBAN et PESEL masqués restent masqués.

### 3.5 History

![History](https://mypresta.eu/docs/images/docs/prestamindai-history.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle History.

La liste complète des appels de modèles, le plus récent d'abord : date, type, fournisseur, modèle, jetons envoyés, jetons reçus, le prix pour 1M de jetons valable alors, le coût estimé, le temps et le statut, avec un lien vers la conversation. Les mêmes filtres que sur **Dashboard**. Les cartes au-dessus de la liste utilisent ce filtre.

La liste ne garde pas le texte du message. Un prix modifié plus tard ne change pas les anciennes lignes. Le journal reste après la suppression des conversations par la rétention.

### 3.6 Conversations

![Conversations](https://mypresta.eu/docs/images/docs/prestamindai-conversations.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle Conversations.

Filtrez par **Waiting for a reply**, **Handled by a person**, escaladé ou sentiment négatif. L'icône œil ouvre le fil : messages, modèle, temps de réponse, pouces haut et bas, et chaque appel d'outil. La corbeille supprime cette conversation, ses messages et ses appels d'outils. La suppression est définitive.

Appuyez sur **Take over this conversation**. L'assistant se tait pour ce visiteur. Vos réponses apparaissent comme **Shop team**. **Send** publie la réponse. **Give back to the assistant** rend le chat.

**Live chats** est un bouton flottant en bas à droite de chaque page du back-office, si **Live chat console in the back office** est actif et si vous pouvez ouvrir **PrestaMind AI**. Le compteur montre les clients en attente. Vous pouvez garder plusieurs fenêtres ouvertes. L'éteindre cache le bouton. Cette page fonctionne encore.

### 3.7 Knowledge

![Knowledge](https://mypresta.eu/docs/images/docs/prestamindai-knowledge.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle Knowledge.

Appuyez sur **Reindex now** après l'installation, après un changement des exclusions et après un changement du fournisseur ou du modèle d'embeddings. **Clear answer cache** efface les réponses enregistrées aux questions de règles répétées. Le cache se vide aussi quand vous modifiez une FAQ ou un produit. Un document encore en attente n'est pas utilisé. Une nouvelle FAQ sert dès la question suivante.

Le prix et le stock ne sont pas dans l'index. Ils sont lus sur le produit au moment de la question.

**Add FAQ entry** / **Edit FAQ entry** : écrivez la question et la réponse comme l'assistant doit les dire, puis enregistrez.

### 3.8 Triggers

![Triggers](https://mypresta.eu/docs/images/docs/prestamindai-triggers.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle Triggers.

**Triggers & offers** a deux sous-pages. Créez d'abord l'offre, puis attachez-la à un déclencheur. Un visiteur voit au plus un message proactif par visite. Ce déclencheur se tait ensuite pendant le délai de refroidissement.

Colonnes : **Name**, **When**, **Threshold**, **Page**, **Message**, **Discount**, **Active**. Sur la ligne : modifier et supprimer. Le cadre d'état explique pourquoi une bulle peut ne pas sortir. **Open the shop in test mode** ignore le consentement, le refroidissement et la limite d'un message par visite.

| Champ | Sur un déclencheur neuf | Ce qu'il fait |
|---|---|---|
| **Name** | vide | Un libellé pour vous. Vide prend le texte du message. Le visiteur ne le voit pas. |
| **Type** | **Seconds on the page** | **Seconds on the page**, **Scrolled percent of the page**, **Exit intent (desktop)**, **Seconds idle on the cart page** ou **Product viewed N times in a visit**. Le message est à côté du bouton de chat. Un clic ouvre le chat. |
| **Threshold** | 30 | Secondes, pourcentage de défilement ou nombre de vues. Exit intent l'ignore. Le temps et le panier inactif utilisent au moins 5 secondes. |
| **Page type** | **Any page** | **Any page**, **Product page**, **Category page**, **Cart / checkout** ou **Home page**. Sur les autres pages ce déclencheur se tait. |
| **Message shown to the visitor** | vide, obligatoire | Une ou deux phrases par langue de la boutique, jusqu'à 300 caractères. Une langue vide prend la langue par défaut. Ce texte est aussi la première ligne quand le visiteur ouvre le chat depuis la bulle. |
| **Only for these categories** | aucune | Sur une fiche, le produit doit être dans l'une d'elles. Sur une catégorie, la catégorie doit correspondre. Vide signifie toutes. |
| **Only for these products** | aucun | Limite le déclencheur à ces produits. Vide signifie tous. |
| **Offer the assistant may grant after this trigger** | **None** | Choisissez une offre enregistrée ou **None**. Les règles décident. Le modèle n'invente pas un pourcentage. |
| **How the discount is handed out** | **Give the code at once when the visitor clicks the message** | **Only if the visitor asks or hesitates over the price**, ou tout de suite quand le chat s'ouvre depuis le message. Dans les deux cas le panier doit correspondre à l'offre. Si **apply_offer** est décoché dans **Tools**, le code est remis tout de suite. |
| **Cool-down (days)** | 7 | De 0 à 365. Après la bulle, ce visiteur ne revoit pas ce déclencheur avant la fin du délai. |

**Add trigger** ou **Save trigger** enregistre la ligne. **Allow proactive messages** doit être actif dans **Privacy**, sinon aucun déclencheur ne part.

### 3.9 Offers

![Offers](https://mypresta.eu/docs/images/docs/prestamindai-offers.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle Offers.

Colonnes : **Name**, **%**, **Min. cart**, **Valid (h)**, **Max / day**. Sur la ligne, modifier et supprimer. Sans offres, l'assistant ne donne jamais de remise. Une conversation reçoit au plus une offre. Le code est à usage unique, entre dans le panier et ne s'ajoute pas aux produits déjà remisés. Le visiteur voit le nom de règle **PrestaMind offer**.

| Champ | Sur une offre neuve | Ce qu'il fait |
|---|---|---|
| **Name** | vide | Votre libellé dans le formulaire du déclencheur. |
| **Discount percent (1-50)** | 5 | Pourcentage sur les produits qui ne sont pas déjà en promotion. |
| **Minimum cart value (tax incl.)** | 0 | 0 signifie n'importe quel panier. En dessous, l'offre est refusée. Le montant est dans la devise par défaut de la boutique. |
| **Valid for (hours)** | 24 | De 1 à 720. Ensuite le code expire. |
| **Maximum codes per day** | 20 | 0 signifie pas de plafond. Une fois atteint, cette offre s'arrête jusqu'au lendemain. |
| **No offer when the cart contains products from** | aucune | Si une ligne est dans ces catégories, tout le panier est refusé. |

**Add offer** ou **Save offer** enregistre la règle. Attachez-la à un déclencheur avant que l'assistant puisse l'utiliser. Les rappels de panier peuvent aussi joindre une offre.

### 3.10 Playground

![Playground](https://mypresta.eu/docs/images/docs/prestamindai-playground.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle Playground.

Utilise le vrai fournisseur. Dépense des jetons et compte dans le budget du jour. Le fil a le canal playground. Rien n'est envoyé aux visiteurs.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Page the customer is on** | **Other** | **Other**, **Home**, **Product page**, **Category** ou **Cart**. L'assistant reçoit cette page comme contexte. |
| **Product id (optional)** | vide | Seulement avec **Product page**. L'id de **Catalog**, puis **Products**. L'assistant voit le prix et le stock actuels. |
| **Customer message** | vide | La question. **Send** montre la réponse et la trace. **New conversation** recommence. |

### 3.11 Quality tests

![Quality tests](https://mypresta.eu/docs/images/docs/prestamindai-quality-tests.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle Quality tests.

Ajoutez une question, des mots que la réponse doit contenir et des mots qu'elle ne doit pas contenir. Appuyez sur **Run all tests**. Chaque passage interroge le vrai modèle et dépense des jetons. La liste montre réussi ou non, la raison et la réponse. Les conversations de test sont supprimées après le passage.

### 3.12 Escalations

![Escalations](https://mypresta.eu/docs/images/docs/prestamindai-escalations.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle Escalations.

Les lignes sont les clients qui ont demandé une personne, les demandes de retour et les demandes de devis, avec un résumé et le contact laissé. La destination se règle dans **Settings**, puis **Escalation**. Mettez le statut sur **new**, **open** ou **done**. Le statut n'envoie pas d'e-mail au visiteur. Répondez au contact de la ligne ou ouvrez le lien du chat.

### 3.13 Health

![Health](https://mypresta.eu/docs/images/docs/prestamindai-health.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle Health.

Une liste de contrôle. **OK** signifie prêt. **!** signifie pas prêt. **Repair hooks** enregistre les hooks manquants et affiche **All hooks are registered.** ou **Could not register:** avec les noms. **Test streaming** vérifie que le serveur ne met pas la réponse en direct dans un tampon. Regarder la page ne change rien d'autre. La ligne du widget n'est OK que lorsque la bulle est visible pour vous.

### 3.14 Widget

![Widget](https://mypresta.eu/docs/images/docs/prestamindai-widget.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle Widget.

| Champ | Après l'installation | Ce qu'il fait |
|---|---|---|
| **Show the assistant to all visitors** | Non | Activé : chaque visiteur voit la bulle, sauf le groupe témoin. Désactivé : personne, sauf les IP d'aperçu. Videz un cache de page entière après le changement. |
| **Preview only for these IP addresses** | vide | IP publiques séparées par des virgules. La page montre l'IP que la boutique voit maintenant. Derrière un proxy elle peut différer de celle que vous connaissez. |
| **Assistant name** | PrestaMind | Nom dans l'en-tête du chat, par langue, jusqu'à 60 caractères. Une langue vide prend la langue par défaut. |
| **Greeting** | vide | Premier message d'un chat vide, jusqu'à 300 caractères par langue. Vide prend une phrase intégrée. |
| **AI disclosure line** | vide | Ligne sous l'en-tête, jusqu'à 300 caractères par langue. Vide prend une phrase intégrée qui dit aussi que les réponses peuvent contenir des erreurs. |
| **Color** | #2563eb | Couleur principale du bouton, de l'en-tête, des boutons et des bulles du visiteur. |
| **Position** | **Bottom right** | **Bottom right** ou **Bottom left**. |
| **Button shape** | **Circle** | **Circle**, **Rounded square** ou **Square with sharp corners**. La fenêtre ne change pas. |
| **Button size** | **Medium (56 px)** | **Small (48 px)**, **Medium (56 px)** ou **Large (68 px)**. |
| **Window corners** | **Soft (default)** | **Sharp**, **Soft (default)** ou **Very round**. |
| **Button icon** | bulle intégrée | **Choose icon** ouvre Font Awesome et Material Icons. **Use the built-in bubble** restaure celle par défaut. L'icône est enregistrée dans la boutique. Enregistrez le formulaire. |
| **Button color** | vide (prend **Color**) | Fond du bouton de chat. |
| **Icon color** | #ffffff | Couleur de l'icône sur le bouton. |
| **Header color** | vide (prend **Color**) | Fond de la barre du haut. |
| **Header text color** | #ffffff | Nom et boutons de la barre du haut. |
| **Customer bubble color** | vide (prend **Color**) | Messages du visiteur, ainsi que les boutons et la flèche d'envoi. |
| **Customer bubble text color** | #ffffff | Texte des messages du visiteur et des boutons principaux. |
| **Preview** | aperçu | Change avec les champs. Rien n'est enregistré avant **Save**. |
| **Tone** | **Friendly** | **Friendly**, **Formal**, **Casual** ou **Expert**. Vaut pour les nouveaux messages. |
| **Your instructions to the assistant** | vide | Jusqu'à 1500 caractères, ajoutés à chaque conversation. Elles n'annulent pas les prix actuels, l'interdiction d'une remise inventée ni l'interdiction des données d'autres clients. Un texte long coûte des jetons à chaque message. |

### 3.15 Fournisseur du modèle et chaque modèle intégré

![Fournisseur du modèle et chaque modèle intégré](https://mypresta.eu/docs/images/docs/prestamindai-provider.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle Fournisseur du modèle et chaque modèle intégré.

Cliquez sur une tuile. Seul le fournisseur actif est appelé, plus le secours si vous en avez mis un et si l'actif échoue avant l'envoi du premier mot. Les modèles et les prix restent chez chaque fournisseur.

Après l'installation, l'actif est **Demo (offline)**. Pas de clé, pas de coût. Réponses préparées, seulement pour tester l'installation. Ce n'est pas un assistant de boutique.

| Champ | Après l'installation | Ce qu'il fait |
|---|---|---|
| **Fallback provider** | **None** | Deuxième fournisseur en cas de délai dépassé, de limite ou d'erreur serveur. Choisissez-en un dont la clé est enregistrée. Cet usage est facturé par ce deuxième fournisseur. La démo ne peut pas être le secours. |
| **API key** | vide | Collez la clé et enregistrez. Un champ vide conserve la clé enregistrée. La clé est chiffrée et n'est plus montrée, seulement les premiers et derniers caractères. **Remove the stored key** sur Yes, puis enregistrer, la supprime. Le serveur compatible peut rester sans clé. |
| **Base URL** | http://localhost:11434/v1 | Seulement pour **OpenAI-compatible / Ollama**. L'URL doit finir par /v1. Les requêtes vont là, pas dans le cloud. |
| **Main model** | tableau de ce fournisseur | Conseil produit, questions de commande et toute réponse qui a besoin d'outils. |
| **Fast model** | tableau de ce fournisseur | Questions de règles et bavardage. Mettez le même que le principal si vous voulez un seul modèle. |
| **Your own model id** | vide | Lettres, chiffres et . _ - : / @, jusqu'à 100 caractères. **Add model** enregistre tout de suite avec le reste de la page. **Model added. Choose it as the main or fast model and enter its price.** Déjà présent : **That model is already on the list.** Id incorrecte : **Enter a model id: letters, digits and . _ - : / @ only.** |
| Colonnes de prix | prix catalogue | **USD / 1M input tokens** et **USD / 1M output tokens**. Le point est le séparateur décimal. **set price** signifie qu'aucun prix par défaut n'est connu. Un modèle sans prix compte comme gratuit, donc le budget quotidien en dollars ne vous protège pas. |
| **Reset prices to defaults** | - | Remet les prix intégrés. **Prices set back to the built-in defaults.** Les prix que vous avez saisis sont perdus. |
| **Remove** | - | Seulement sur un modèle de chat personnel. **Model removed.** Un modèle intégré montre un cadenas et **Built-in models cannot be removed.** |

**Save and test the connection** enregistre et appelle le fournisseur actif avec le modèle principal. **No API key stored for the selected provider.** signifie que la clé manque encore.

Les prix ci-dessous sont en USD pour 1 million de jetons, d'abord l'entrée, puis la sortie. Ce sont les prix catalogue enregistrés dans le module le 2026-10-31. Le fournisseur peut les changer. Corrigez les deux colonnes si votre facture diffère. DeepSeek a un prix de pointe et un prix hors pointe. Le module garde le prix de pointe pour que l'estimation ne soit pas trop basse.

**OpenAI.** Flux, outils et embeddings. Modèle principal par défaut **gpt-6.1-sol**. Modèle rapide par défaut **gpt-6-luna**.

| Modèle | Type | Entrée / sortie USD pour 1M | Après l'installation |
|---|---|---|---|
| gpt-6.1-sol | chat | 2 / 10 | modèle principal |
| gpt-6.1-terra | chat | 1 / 5 | non |
| gpt-6-luna | chat | 0.10 / 0.50 | modèle rapide |
| gpt-5.5 | chat | 5 / 30 | non |
| gpt-5-mini | chat | 0.25 / 2 | non |
| gpt-4.1 | chat | 2 / 8 | non |
| gpt-4.1-mini | chat | 0.40 / 1.60 | non |
| gpt-4o-mini | chat | 0.15 / 0.60 | non |
| text-embedding-3-small | embeddings | 0.02 / 0 | modèle d'embeddings par défaut |
| text-embedding-3-large | embeddings | 0.13 / 0 | non |

**Anthropic Claude.** Flux et outils. Pas d'embeddings. Modèle principal par défaut **claude-sonnet-5-5**. Modèle rapide par défaut **claude-haiku-5-5**.

| Modèle | Type | Entrée / sortie USD pour 1M | Après l'installation |
|---|---|---|---|
| claude-fable-5-1 | chat | 10 / 50 | non |
| claude-opus-5-5 | chat | 4 / 20 | non |
| claude-opus-5 | chat | 5 / 25 | non |
| claude-sonnet-5-5 | chat | 2 / 10 | modèle principal |
| claude-sonnet-4-6 | chat | 3 / 15 | non |
| claude-haiku-5-5 | chat | 0.10 / 0.50 | modèle rapide |
| claude-haiku-4-5 | chat | 1 / 5 | non |

**Google Gemini.** Flux, outils et embeddings. Modèle principal par défaut **gemini-2.5-flash**. Modèle rapide par défaut **gemini-2.5-flash-lite**.

| Modèle | Type | Entrée / sortie USD pour 1M | Après l'installation |
|---|---|---|---|
| gemini-2.5-pro | chat | 1.25 / 10 | non |
| gemini-2.5-flash | chat | 0.30 / 2.50 | modèle principal |
| gemini-2.5-flash-lite | chat | 0.10 / 0.40 | modèle rapide |
| gemini-embedding-001 | embeddings | 0.15 / 0 | modèle d'embeddings par défaut |

**DeepSeek.** API compatible OpenAI. Pas d'embeddings. Le modèle principal et le modèle rapide par défaut sont tous les deux **deepseek-flash**.

| Modèle | Type | Entrée / sortie USD pour 1M | Après l'installation |
|---|---|---|---|
| deepseek-flash | chat | 0.30 / 1.20 | modèle principal et rapide |
| deepseek-v4-pro | chat | 1.32 / 3.96 | non |

**Mistral AI.** Flux, outils et embeddings. Modèle principal par défaut **mistral-large-latest**. Modèle rapide par défaut **mistral-small-latest**. Un prix vide signifie que le module n'a pas de prix catalogue : la ligne porte **set price** tant que vous n'en saisissez pas un.

| Modèle | Type | Entrée / sortie USD pour 1M | Après l'installation |
|---|---|---|---|
| mistral-large-latest | chat | 0.50 / 1.50 | modèle principal |
| mistral-medium-latest | chat | pas de prix intégré | non |
| mistral-small-latest | chat | pas de prix intégré | modèle rapide |
| open-mistral-nemo | chat | pas de prix intégré | non |
| mistral-embed | embeddings | pas de prix intégré | modèle d'embeddings par défaut |

**OpenAI-compatible / Ollama.** Votre serveur. Les prix intégrés sont 0 / 0, y compris pour les modèles locaux. Le modèle principal et le modèle rapide par défaut sont **llama3.1**. Le modèle d'embeddings par défaut est **nomic-embed-text**.

| Modèle | Type | Entrée / sortie USD pour 1M | Après l'installation |
|---|---|---|---|
| llama3.1 | chat | 0 / 0 | modèle principal et rapide |
| llama3.2 | chat | 0 / 0 | non |
| mistral | chat | 0 / 0 | non |
| qwen2.5 | chat | 0 / 0 | non |
| nomic-embed-text | embeddings | 0 / 0 | modèle d'embeddings par défaut |
| mxbai-embed-large | embeddings | 0 / 0 | non |
| bge-m3 | embeddings | 0 / 0 | non |
| snowflake-arctic-embed | embeddings | 0 / 0 | non |

**Demo (offline).** Pas de clé. Prix 0 / 0.

| Modèle | Type | Entrée / sortie USD pour 1M | Après l'installation |
|---|---|---|---|
| mock | chat | 0 / 0 | modèle principal et rapide, et ce fournisseur est l'actif |
| mock-64 | embeddings | 0 / 0 | quand le fournisseur d'embeddings est la démo |

Certains modèles OpenAI récents ignorent **Temperature**. Un id que le fournisseur ne connaît pas apparaît comme une erreur de fournisseur sur **Dashboard**.

### 3.16 Réglages Knowledge

![Réglages Knowledge](https://mypresta.eu/docs/images/docs/prestamindai-knowledge-settings.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle Réglages Knowledge.

L'adresse cron est sur cette page. Appelez-la toutes les 10 à 15 minutes. Chaque appel indexe les pages nouvelles et modifiées, construit les embeddings, envoie les rappels de panier si vous les avez activés, supprime les conversations plus anciennes que la rétention et vide le cache des réponses ainsi que les lignes de limite de plus de deux jours. Sans cron, l'index se met quand même à jour quand les visiteurs écrivent ou quand les hooks produit et CMS tournent. La rétention et les embeddings ne passent alors que par les boutons.

| Champ | Après l'installation | Ce qu'il fait |
|---|---|---|
| **Embeddings provider** | **None (keyword search)** | **None (keyword search)**, **openai**, **gemini**, **mistral**, **compatible** ou **demo**. Anthropic et DeepSeek ne sont pas dans cette liste. Le changement exige **Reindex now**. |
| **Embeddings model** | **Default for the chosen provider** | Un modèle du fournisseur ci-dessus. Les vecteurs de deux modèles ne se comparent pas. Un modèle d'un autre fournisseur est ignoré et le défaut est utilisé. Réindexez après le changement. |
| **Other embeddings model** | vide | Id exact d'un modèle absent de la liste, par exemple un modèle Ollama. S'il est rempli, il remplace le choix ci-dessus. |
| **Index products** | Oui | Indexe le nom, la marque, les catégories, les caractéristiques et les descriptions des produits actifs et visibles. Non : les questions produit n'ont pas de texte de catalogue. |
| **Index CMS pages** | Oui | Indexe les pages CMS actives. N'indexez pas les pages qui contiennent des notes internes. |
| **Never use these categories** | aucune | Les produits de ces catégories ne sont pas indexés et ne peuvent pas être montrés, comparés ou proposés au panier. Réindexez après le changement. |
| **Never use these products** | aucun | La même chose pour des produits isolés. |
| **Cache answers to repeated policy questions** | Oui | Visiteurs, première question seulement, et jamais une réponse qui contient un prix ou une commande. **Clear answer cache** sur l'onglet Knowledge après la modification d'une page de règles. |
| **Cache lifetime (hours)** | 24 | De 1 à 720. Ensuite le modèle répond de nouveau. |

### 3.17 Limites et coût

![Limites et coût](https://mypresta.eu/docs/images/docs/prestamindai-limits.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle Limites et coût.

La ligne du haut montre les requêtes, les jetons et le coût estimé du jour. Quand un budget quotidien est atteint, l'assistant envoie un court avis et propose de passer la question à votre équipe jusqu'au lendemain.

| Champ | Après l'installation | Ce qu'il fait |
|---|---|---|
| **Daily budget (USD)** | 0 | 0 signifie pas de plafond. Ne fonctionne que si les modèles utilisés ont un prix. Quand le coût du jour atteint le plafond, les appels au modèle s'arrêtent jusqu'à minuit. |
| **Daily token budget** | 0 | 0 signifie pas de plafond. Compte les jetons même si le prix est 0. 1000000 jetons, c'est environ quelques centaines de conversations. |
| **Messages per minute per visitor IP** | 8 | De 1 à 60. Un envoi plus rapide reçoit une demande d'attente et pas d'appel au modèle. |
| **Messages per conversation per day** | 60 | De 1 à 500. Ensuite la conversation est bloquée pour la journée. |
| **Max reply tokens** | 700 | De 150 à 3000. À 700, environ 450 mots. Une limite courte coupe la réponse. |
| **Max tool steps per message** | 5 | De 1 à 8. Combien de lectures en direct (recherche, produit, livraison) un message peut lancer. 1 arrête la recherche en plusieurs étapes. |
| **Max characters per customer message** | 800 | De 100 à 2000. Le texte plus long est coupé. |
| **Messages of history sent to the model** | 12 | De 2 à 30. 12, ce sont les six derniers échanges. Plus d'historique envoie plus de jetons. |
| **Temperature (0-1)** | 0.3 | De 0.2 à 0.4 reste plus près des données de la boutique. Plus haut varie la formulation. Certains modèles OpenAI récents l'ignorent. |

### 3.18 Privacy

![Privacy](https://mypresta.eu/docs/images/docs/prestamindai-privacy.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle Privacy.

| Champ | Après l'installation | Ce qu'il fait |
|---|---|---|
| **Mask card numbers, IBAN and PESEL** | Oui | Les remplace par [card], [iban] et [id] avant d'enregistrer le texte et avant de l'envoyer au fournisseur. |
| **Delete conversations after (days)** | 90 | 0 les conserve. L'URL cron supprime les conversations plus anciennes. Les statistiques de commandes restent. |
| **Order status without signing in, for registered customers** | Oui | Un visiteur peut demander avec la référence de commande et l'e-mail du paiement. Non : cette paire ne vaut que pour les commandes invité, et un client avec compte doit se connecter. Au plus 10 essais en 10 minutes. |
| **Allow proactive messages** | Oui | Non coupe tous les déclencheurs. |
| **Proactive triggers wait for consent** | Oui | Pas de bulle tant que la bannière de cookies n'appelle pas la fonction de consentement. Le chat lui-même fonctionne. Non : les déclencheurs partent pour tout le monde. |
| **Control group (% of visitors)** | 0 | De 0 à 50. Ces visiteurs ne voient jamais l'assistant. **Dashboard** peut comparer la valeur des commandes. |

**Delete old conversations** est un formulaire à part. **Older than (days)** y commence à 30. **Delete** supprime ces conversations tout de suite. Le message est **Deleted N conversations.** On ne peut pas revenir en arrière.

### 3.19 Réglages Escalation

![Réglages Escalation](https://mypresta.eu/docs/images/docs/prestamindai-escalation.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle Réglages Escalation.

| Champ | Après l'installation | Ce qu'il fait |
|---|---|---|
| **Live chat console in the back office** | Oui | Affiche le bouton **Live chats**. Seuls les employés qui peuvent ouvrir **PrestaMind AI** le voient. Off cache le bouton. **Conversations** fonctionne encore. |
| **E-mail for hand-offs** | vide | Chaque escalade envoie un résumé et le contact laissé par le visiteur. Vide signifie pas d'e-mail. Le courrier de la boutique doit fonctionner. |
| **Webhook type** | **Slack** | **Slack**, **Telegram** ou **Generic JSON**. |
| **Webhook URL** | vide | URL d'incoming webhook Slack, Telegram `https://api.telegram.org/bot<TOKEN>/sendMessage`, ou n'importe quelle URL https. Vide signifie pas de webhook. Le résultat est dans la liste **Escalations**. |
| **Telegram chat id** | vide | Id numérique du chat ou du groupe. Ignoré pour Slack et Generic JSON. |
| **Offer a person when sentiment falls below** | -0.5 | De -1 à 0. Plus près de 0 réagit plus tôt. L'assistant s'excuse et propose de passer le dossier à l'équipe. |

### 3.20 Rappels de panier

![Rappels de panier](https://mypresta.eu/docs/images/docs/prestamindai-reminders.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle Rappels de panier.

Rien ne part tant que **Send cart reminders** n'est pas sur Yes et que l'URL cron ne tourne pas. Un e-mail par panier abandonné, seulement vers un client avec compte. Les visiteurs sans compte ne reçoivent pas cet e-mail.

| Champ | Après l'installation | Ce qu'il fait |
|---|---|---|
| **Send cart reminders** | Non | Activé : le prochain passage cron envoie les rappels qui correspondent. Désactivé : rien de nouveau ne part. Les lignes déjà envoyées restent dans la liste. |
| **Only customers who subscribed to the newsletter** | Oui | Oui : les clients sans la case newsletter ne reçoivent rien. |
| **Send after (hours of inactivity)** | 3 | Au moins 1. Le panier doit rester ainsi pendant ce délai. |
| **Stop after (hours since the last change)** | 72 | Doit être plus grand que la valeur au-dessus. Les paniers plus anciens sont ignorés. |
| **Minimum cart value (tax incl.)** | 0 | 0 signifie n'importe quel panier. Le montant est dans la devise de la boutique. |
| **Discount code in the e-mail** | **No discount code** | Une de vos offres, ou aucune. Les règles de l'offre s'appliquent encore. Si le plafond du jour est atteint, l'e-mail part sans code. |
| **E-mail subject** | vide | Par langue. Vide prend un objet intégré. Le client reçoit l'objet de la langue de son compte. |

**Send a test e-mail** utilise **Send the test to** (d'abord votre e-mail du back-office) et **Send test**. Un échantillon part tout de suite. Il n'est pas enregistré et ne crée pas de code. **Test e-mail sent.** ou **The e-mail could not be sent. Check the e-mail settings of the shop.** Une adresse incorrecte affiche **Enter a valid e-mail address.**

**Latest reminders** liste la date, le panier, le client, le code et le statut.

### 3.21 Couriers

![Couriers](https://mypresta.eu/docs/images/docs/prestamindai-couriers.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle Couriers.

La page liste les modes de livraison de cette boutique. S'il n'y en a pas, vous voyez **Your shop has no shipping methods yet. Add them in Shipping > Carriers; they appear here automatically.**

Pour chaque mode, **tracking link** est une adresse par langue. Mettez `{n}` là où va le numéro de suivi. Une adresse sans `{n}`, ou qui ne commence pas par http ou https, est ignorée. Une langue vide prend la langue par défaut. Si le transporteur a déjà une URL de suivi dans **Shipping**, puis **Carriers**, cette URL passe en premier. Sans aucun lien, l'assistant ne cite que le numéro.

**live status** n'apparaît que si le nom contient InPost ou DHL, ou si vous l'avez choisi plus tôt. **No live status (tracking link only)** garde le lien. InPost n'a pas besoin de clé. DHL affiche **DHL API key** : inscrivez-vous sur le site développeur DHL, créez une application Shipment Tracking - Unified et collez la clé. La clé gratuite permet environ 250 appels par jour. La clé est enregistrée chiffrée. Sans elle, le statut DHL en direct est sauté et le lien est utilisé. Les réponses en direct sont en cache 10 minutes.

### 3.22 Tools

![Tools](https://mypresta.eu/docs/images/docs/prestamindai-tools.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle Tools.

Décochez un outil pour que le modèle ne le reçoive pas. Un outil coupé ne peut pas s'exécuter. En mode catalogue, les outils de panier, d'offre et de contenu du panier restent coupés. Une question de règles ou une conversation légère ne peut appeler que **create_ticket**.

| Outil | Risque à l'écran | A besoin de | Ce que le visiteur obtient |
|---|---|---|---|
| search_products | lecture | - | Jusqu'à six fiches. Prix maximum facultatif et seulement en stock. Le visiteur appuie sur **Add to cart**. |
| popular_products | lecture | - | Meilleures ventes des vraies commandes, 90 jours par défaut, de 7 à 365, jusqu'à six fiches. Pas de chiffres de ventes exacts. |
| get_product_live | lecture | - | Prix, stock, caractéristiques et variantes actuels d'un produit. |
| compare_products | lecture | - | Deux ou trois produits côte à côte. |
| suggest_substitute | lecture | - | Des équivalents qui sont en stock. |
| get_cart | lecture | un panier | Contenu et total. |
| add_to_cart | l'écran marque la confirmation | confirmation du client | Une fiche. Quantité de 1 à 20. Le module n'ajoute pas la ligne. Le visiteur appuie sur **Add to cart**. |
| check_shipping | lecture | - | Modes, délais et seuil de livraison gratuite. Code ISO de pays facultatif. |
| get_order_status | lecture | session, ou référence plus e-mail du paiement | Statut de cette commande. |
| track_parcel | lecture | la même identité que le statut de commande | Transporteur, numéro et lien. InPost en direct sans clé. DHL en direct avec la clé DHL. |
| start_return | confirmation | client connecté | Rien ne part avant **Send the return request**. |
| request_quote | confirmation | le formulaire | Articles, société et contact. Rien ne part avant **Send the quote request**. |
| create_ticket | passage | un visiteur sans compte est invité à donner un e-mail ou un téléphone | **Talk to a person** ouvre une escalade. |
| apply_offer | les règles décident | un panier | Un code seulement si une offre enregistrée correspond. Aucune règle correspondante signifie pas de code. |

**Save** enregistre les cases.

### 3.23 Updates

![Updates](https://mypresta.eu/docs/images/docs/prestamindai-updates.webp)

L'écran est en anglais. Dans ce manuel cette page s'appelle Updates.

**Check now** compare la version installée à celle des serveurs MyPresta.eu. Laissez les avis automatiques actifs pour voir un avis dans le back-office. Le module ne se met jamais à jour tout seul. Vous installez vous-même le nouveau paquet.

## 4. Boutique

La bulle est cachée tant que **Show the assistant to all visitors** n'est pas actif, sauf pour les IP de la liste d'aperçu. Les visiteurs du groupe témoin ne la voient pas.

Le visiteur appuie sur le bouton dans le coin que vous avez choisi. La fenêtre montre le nom de l'assistant, la ligne d'information et l'accueil. Le visiteur écrit et appuie sur la flèche. Sur la boutique il n'y a pas de bouton libellé Send. La réponse arrive dans la fenêtre si le serveur ne la met pas en tampon.

Les fiches montrent **Add to cart**. Un retour attend **Send the return request**. Un devis attend **Send the quote request**. **Talk to a person** passe le chat à l'équipe. Tant que vous avez repris la conversation, les nouveaux messages du visiteur sont enregistrés et vos réponses apparaissent comme **Shop team**.

Une bulle proactive n'apparaît que si les déclencheurs sont autorisés, si le visiteur correspond à la règle et si le consentement est donné quand vous l'exigez. Une bulle par visite. Le lien de test de **Triggers** est pour vous, pas pour les clients.

L'adresse cron n'est pas une page pour les visiteurs. Ouvrez-la seulement depuis le planificateur du serveur. Un mauvais jeton reçoit un refus et ne fait rien.

## 5. Problèmes

**La bulle manque.** **Show the assistant to all visitors** est sur off, ce visiteur est dans le groupe témoin, ou un cache de page entière garde l'ancienne page. Activez l'interrupteur ou ajoutez votre IP à la liste d'aperçu, enregistrez et videz le cache de page entière.

**Could not create the module tables.** L'installation s'est arrêtée avant l'entrée de menu. Lisez le message de la base, corrigez les droits de l'utilisateur de la base et réinstallez.

**Could not register hook** suivi d'un nom de hook, ou **Could not register:** dans **Health**. Appuyez sur **Repair hooks**. Si la ligne reste, l'utilisateur de la boutique ne peut pas écrire les hooks. Corrigez les droits de la base et appuyez de nouveau sur le bouton.

**Could not add the menu tab.** L'installation n'a pas fini le menu. Ouvrez **Module Manager**, désinstallez si le module est à moitié installé, et réinstallez. **Configure** essaie aussi de recréer l'entrée de menu.

**No API key stored for the selected provider.** Collez la clé dans **Model provider** et appuyez sur **Save and test the connection**. Un champ mot de passe vide ne supprime pas une clé. **Remove the stored key** la supprime.

**That model is already on the list.** Choisissez-le comme **Main model** ou **Fast model** au lieu de l'ajouter encore.

**Enter a model id: letters, digits and . _ - : / @ only.** Retapez l'id de la liste de modèles du fournisseur. Les espaces ne sont pas admis.

**Built-in models cannot be removed.** Laissez la ligne. Ajoutez un id personnel si vous avez besoin d'un autre modèle.

**Erreurs de fournisseur sur Dashboard.** La clé est fausse, le fournisseur ne connaît pas l'id du modèle, ou le fournisseur ne répond pas. Si un secours est réglé et que l'échec arrive avant le premier mot, le secours répond. Corrigez la clé ou le modèle, puis utilisez **Playground**.

**La réponse arrive en un bloc, pas mot à mot.** Appuyez sur **Test streaming** dans **Health**. Si le test échoue, le proxy ou l'hébergeur met la réponse en tampon. Demandez à l'hébergeur de le couper sur l'adresse de chat de la boutique.

**I cannot answer right now.** Le budget du jour ou le budget de jetons est atteint, ou le fournisseur a échoué et il n'y a pas de secours. Augmentez le budget, attendez le lendemain ou réparez le fournisseur. L'assistant propose de passer la question à l'équipe.

**Demande d'attendre, ou conversation bloquée.** Le visiteur a envoyé plus que **Messages per minute per visitor IP** ou plus que **Messages per conversation per day**. Attendez, ou augmentez la limite.

**Un déclencheur ne sort jamais.** Lisez le cadre de **Triggers**. **Allow proactive messages** est sur off, le déclencheur est inactif, **apply_offer** est sur off alors que le déclencheur attend que le visiteur demande, ou les déclencheurs attendent le consentement et la bannière n'appelle jamais la fonction. Utilisez **Open the shop in test mode**. Après un vrai test, le refroidissement cache ce déclencheur dans ce navigateur.

**La remise ne sort jamais.** Il n'y a pas d'offre, l'offre n'est pas attachée au déclencheur, le panier est sous le minimum, le plafond du jour est atteint, un produit est dans une catégorie exclue, ou le produit est déjà remisé. L'assistant n'invente pas un pourcentage.

**Add to cart n'ajoute rien tout seul.** La fiche n'est qu'une fiche. Le visiteur appuie sur **Add to cart**. En mode catalogue les outils de panier restent coupés.

**Test e-mail sent.** est un succès. **The e-mail could not be sent. Check the e-mail settings of the shop.** signifie que le courrier de la boutique a échoué. **Enter a valid e-mail address.** signifie que l'adresse de test est vide ou incorrecte. Les e-mails aux clients exigent aussi **Send cart reminders** sur Yes et une URL cron qui tourne.

**Deleted N conversations.** Vous avez appuyé sur **Delete** dans **Privacy**. Ces fils ont disparu.

## 6. Pour le développeur

### 6.1 Aperçu

Nom technique `prestamindai`, classe `prestamindai`, version dans le fichier `1.8.9`, nom affiché **PrestaMind AI**, auteur MyPresta.eu, onglet `front_office_features`. Compatibilité à partir de 1.7.6.0, maximum `99.99.99`. Il n'y a pas de `enable()` ni de `disable()` propre. Désactiver dans PrestaShop arrête les hooks enregistrés. Activer les réenregistre par le cœur.

`PmaiConfig` lit et écrit les clés `Configuration` avec le préfixe `PMAI_`. `PmaiProviderRouter` choisit `PmaiOpenAiProvider`, `PmaiAnthropicProvider`, `PmaiGeminiProvider` ou `PmaiMockProvider`. DeepSeek et l'URL compatible utilisent le client compatible OpenAI. `PmaiOrchestrator` construit le prompt, appelle le modèle et lance les outils de `PmaiToolRegistry`. Les prix utilisés pour un appel sont copiés sur la ligne d'usage.

### 6.2 Fichiers

| Fichier | Rôle |
|---|---|
| `prestamindai.php` | Installation, désinstallation, hooks, onglet de menu, redirection depuis **Configure**. |
| `sql/install.php` | Crée les 16 tables. |
| `sql/uninstall.php` | Supprime ces tables. |
| `controllers/admin/AdminPrestamindaiController.php` | Onglets du back-office et actions POST. |
| `controllers/front/chat.php` | Adresse du chat sur la boutique. |
| `controllers/front/cron.php` | Une URL cron. |
| `src/Service/PmaiConfig.php` | Valeurs de départ, listes de modèles, prix intégrés, modèles personnels. |
| `src/Admin/PmaiForms.php` | Chaque formulaire du back-office et les descriptions de champs. |
| `src/Admin/PmaiSectionHelp.php` | Texte d'aide de chaque onglet. |
| `src/Agent/PmaiToolRegistry.php` | Les 14 outils et le filtre du mode catalogue. |
| `src/Llm/PmaiOpenAiProvider.php` | OpenAI, DeepSeek et l'URL compatible. |
| `src/Llm/PmaiAnthropicProvider.php` | Anthropic. |
| `src/Llm/PmaiGeminiProvider.php` | Gemini. |
| `src/Llm/PmaiMockProvider.php` | Démo hors ligne. |
| `src/Knowledge/PmaiIndexer.php` | Découverte et réindexation. |
| `src/Safety/PmaiGuardrails.php` | Remplace carte, IBAN et PESEL. |
| `upgrade/` | Les mises à jour de version appellent `upgradeDb()`. |
| `translations/{iso}.php` | Chaînes du back-office. |
| `views/` | Modèles, CSS et JS du back-office et de la boutique. |

### 6.3 Contrôleurs

`AdminPrestamindai` est la classe de menu. Le parent est la première classe existante parmi `AdminParentCustomerThreads`, `AdminCustomerThreads` et `IMPROVE`. Le libellé de l'onglet est **PrestaMind AI**. `getContent()` redirige vers ce contrôleur.

`pmai_tab` est l'un de `dashboard`, `live`, `history`, `conversations`, `knowledge`, `triggers`, `playground`, `evals`, `escalations`, `settings`, `updates`. Les réglages lisent aussi `pmai_sub` : `health`, `widget`, `provider`, `knowledge`, `limits`, `privacy`, `escalation`, `reminders`, `couriers`, `tools`.

`controllers/front/chat.php` accepte les opérations boutique init, message, feedback, confirm, add_to_cart, escalate, poll, event et open_trigger. `controllers/front/cron.php` exige le jeton cron. Un mauvais jeton renvoie le JSON `ok: false` et `error: token`.

### 6.4 Hooks

Enregistrés à l'installation : `displayBackOfficeHeader`, `dashboardZoneTwo`, `actionAdminControllerSetMedia`, `displayHeader`, `displayBeforeBodyClosingTag`, `displayFooter`, `actionObjectProductAddAfter`, `actionObjectProductUpdateAfter`, `actionObjectProductDeleteAfter`, `actionObjectCmsAddAfter`, `actionObjectCmsUpdateAfter`, `actionObjectCmsDeleteAfter`, `actionValidateOrder`, `registerGDPRConsent`, `actionDeleteGDPRCustomer`, `actionExportGDPRData`.

`displayBeforeBodyClosingTag` affiche le widget, `displayFooter` est le repli. Les hooks produit et CMS marquent les documents à réindexer. `actionValidateOrder` relie la commande au chiffre d'affaires. Les hooks GDPR exportent ou suppriment les lignes de ce client. **Repair hooks** appelle `ensureHooks()` pour chaque nom manquant. Le module ne publie pas de hooks propres pour d'autres modules.

### 6.5 Surcharges

Le module ne surcharge aucune classe ni aucun contrôleur PrestaShop.

### 6.6 Base

La désinstallation fait `DROP TABLE` sur chaque table ci-dessous. L'installation utilise `CREATE TABLE IF NOT EXISTS`. Une désinstallation ratée qui aurait laissé les tables garderait les anciennes lignes. Une désinstallation normale les supprime, et l'installation suivante est vide.

| Table | Contenu |
|---|---|
| `PREFIX_pmai_thread` | Une conversation : boutique, client, visiteur, canal, statut, page. |
| `PREFIX_pmai_message` | Messages du fil, y compris le payload des fiches. |
| `PREFIX_pmai_tool_call` | Nom de l'outil, arguments et résultat d'un message. |
| `PREFIX_pmai_doc` | Document indexé produit, CMS ou FAQ. |
| `PREFIX_pmai_chunk` | Morceaux d'un document, embedding compris s'il existe. |
| `PREFIX_pmai_cache` | Réponses de règles mises en cache. |
| `PREFIX_pmai_trigger` | Règles de déclencheurs. |
| `PREFIX_pmai_offer` | Règles de remise. |
| `PREFIX_pmai_event` | Événements boutique pour les déclencheurs et les statistiques. |
| `PREFIX_pmai_usage` | Un appel de modèle : fournisseur, modèle, jetons, instantané de prix, coût, statut. Pas de texte de message. |
| `PREFIX_pmai_request` | Lignes de limite de requêtes. |
| `PREFIX_pmai_cart_reminder` | Un rappel de panier envoyé. |
| `PREFIX_pmai_escalation` | Passage, retour ou devis, et résultat de la notification. |
| `PREFIX_pmai_ratelimit` | Compteurs de la fenêtre courte. |
| `PREFIX_pmai_eval_case` | Une question de qualité et les mots exigés. |
| `PREFIX_pmai_eval_run` | Un passage de ces tests. |

`PmaiConfig::PRICES_CHECKED` vaut `2026-10-31`. Les id de chat et d'embeddings et les prix intégrés sont dans `PmaiConfig::builtinModels()`, `builtinEmbeddingModels()` et `builtinPrices()`. Les id personnels sont du JSON dans `PMAI_CUSTOM_MODELS`. Les prix modifiés sont du JSON dans `PMAI_MODEL_PRICES` et l'emportent sur le prix intégré.

### 6.7 Clés et traductions

Chaque clé est `PMAI_` plus le nom de `PmaiConfig::defaults()`. Les secrets de fournisseur sont `PMAI_KEY_OPENAI`, `PMAI_KEY_ANTHROPIC`, `PMAI_KEY_GEMINI`, `PMAI_KEY_DEEPSEEK`, `PMAI_KEY_MISTRAL`, `PMAI_KEY_COMPATIBLE`, `PMAI_KEY_MOCK` et `PMAI_KEY_DHLTRACK`. Ils sont chiffrés avec libsodium si `sodium_crypto_secretbox` existe, sinon avec OpenSSL. `PMAI_CRON_TOKEN` est un hex aléatoire créé à l'installation s'il est vide.

Les clés de choix de modèle sont `PMAI_MODEL_MAIN_{PROVIDER}` et `PMAI_MODEL_FAST_{PROVIDER}`. Après l'installation : OpenAI `gpt-6.1-sol` / `gpt-6-luna`, Anthropic `claude-sonnet-5-5` / `claude-haiku-5-5`, Gemini `gemini-2.5-flash` / `gemini-2.5-flash-lite`, DeepSeek `deepseek-flash` / `deepseek-flash`, Mistral `mistral-large-latest` / `mistral-small-latest`, compatible `llama3.1` / `llama3.1`, mock `mock` / `mock`. `PMAI_PROVIDER` vaut `mock`. `PMAI_EMBED_PROVIDER` vaut `none`. `PMAI_EMBED_MODEL` est vide, donc le premier modèle d'embeddings intégré du fournisseur choisi est utilisé.

`PMAI_BOT_NAME`, `PMAI_GREETING`, `PMAI_DISCLOSURE` et `PMAI_REMINDER_SUBJECT` sont multilingues. L'aide des champs est le HTML `desc` construit dans `PmaiForms`. Ajoutez une langue en traduisant `translations/{iso}.php`. Les chaînes qui ne passent pas par `$this->l()` restent telles qu'elles sont écrites dans les tableaux PHP (noms de tuiles, id de modèles, id d'outils).

### 6.8 Étendre

Le modèle et le CSS du widget de la boutique peuvent être surchargés dans le thème de la façon habituelle de PrestaShop, sous `modules/prestamindai/views/`. Le back-office n'est pas une surcharge de thème. Ne changez pas les id de modèles dans le thème. Ajoutez un modèle dans **Model provider**. Une bannière de cookies peut appeler `window.PrestaMindAI.setConsent(true)` après l'acceptation du visiteur. Le module ne fournit pas de bannière.

## 7. Aide

Page du module : [https://mypresta.eu/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot.html](https://mypresta.eu/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot.html)

Pour écrire au sujet de ce module, connectez-vous à votre compte client sur mypresta.eu, ouvrez le formulaire de contact et choisissez le sujet **Support for paid modules**. Le formulaire indique que la connexion est exigée pour les modules payants. Après la connexion, choisissez ce module dans l'historique des achats.
