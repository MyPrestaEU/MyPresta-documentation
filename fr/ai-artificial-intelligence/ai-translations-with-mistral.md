---
title: "AI Translations with Mistral – documentation et manuel d'utilisation"
description: "Guide de configuration et de dépannage pour les personnes qui utilisent le module AI Translations with Mistral."
sidebar:
  label: "AI Translations with Mistral – documentation et manuel d'utilisation"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module AI Translations with Mistral sur MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-mistral.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ai-artificial-intelligence/ai-translations-with-mistral/)
>
> ---


## 1. Prérequis

Le module fonctionne avec PrestaShop à partir de la version 1.7.0.0.

- **PrestaShop :** 1.7.0.0 ou plus récent.
- **PHP :** la version exigée par votre PrestaShop. Le module ne fixe pas de minimum propre.
- **Extensions PHP :** cURL (connexion à Mistral), OpenSSL (chiffrement de la clé API), SimpleXML (lecture des fichiers de traduction XLF), mbstring.
- **Autres modules :** le module ne dépend d'aucun autre module.
- **En dehors de la boutique :** un compte Mistral AI et une clé API à créer sur https://console.mistral.ai/api-keys. Le serveur de la boutique doit pouvoir joindre `api.mistral.ai` en HTTPS.
- **Facultatif :** une tâche planifiée sur le serveur qui appelle l'adresse cron (décrite en 3.1). Sans elle, vous traitez les tâches à la main dans l'onglet **Jobs**.
- **Gros catalogues :** traduire un domaine entier de plusieurs milliers de textes représente beaucoup d'appels à l'API et un temps de traitement plus long. La tâche est découpée en lots dont la taille est définie par **Batch size**. Avant de vous lancer, exécutez toujours **Estimate** dans **Bulk**.
- La boutique doit avoir au moins deux langues. Avec une seule langue, le back office affiche un avertissement, car il n'y a rien à traduire.

## 2. Installation

1. Ouvrez **Modules** → **Module Manager**. Cliquez sur **Upload a module**, envoyez le fichier ZIP du module, puis cliquez sur **Install** à côté de **AI Translations with Mistral**.
2. Une fois l'installation terminée, **AI Translations with Mistral** apparaît dans le menu **International**.
3. L'installation ne vide pas le cache de la boutique. Le module vide lui-même le cache de PrestaShop lorsqu'il enregistre une traduction.
4. Ouvrez **AI Translations with Mistral** → **Settings** et collez votre clé Mistral. Tant qu'aucune clé n'est enregistrée, le back office affiche **No Mistral API key.**

**Désinstallation.** Dans **Module Manager**, cliquez sur **Uninstall** et confirmez le message **Delete this module and its data (jobs, glossary, cache)?**

- Sont supprimés : l'entrée de menu, toutes les tâches, le glossaire, les exclusions, l'historique des appels, la file **Review**, les copies de sauvegarde servant à l'annulation, le récapitulatif des coûts et les réglages du module (clé API comprise).
- Sont conservés : les textes que le module a enregistrés dans la boutique, à savoir les traductions du catalogue PrestaShop et les fichiers de traduction des modules classiques dans lesquels il a écrit. Les réglages de vérification des mises à jour sont également conservés.
- Réinstaller le module ne restaure ni les tâches, ni le glossaire, ni l'historique supprimés. Les valeurs par défaut sont rétablies et une nouvelle adresse cron est créée.

## 3. Configuration et utilisation au quotidien

Tout le module se trouve sur une seule page : **International** → **AI Translations with Mistral**. Les onglets en haut sont **Dashboard**, **Manual**, **Bulk**, **Jobs**, **Review**, **Catalog**, **Glossary**, **Excludes**, **History** et **Settings**. L'onglet **Updates** se trouve tout à droite de la barre. Le bouton **Help** ouvre un panneau qui explique l'onglet affiché.

Les noms des champs et des boutons de ce manuel correspondent à ceux du back office en anglais. Si votre back office est dans une autre langue, vous verrez leur traduction. Les captures d'écran proviennent également du back office en anglais.

Chaque onglet commence par une phrase qui indique ce qu'il fait, comment s'en servir et quel effet il produit. La même explication, découpée en trois parties, se trouve aussi sous les champs du formulaire. Le bouton **Help**, en bas à droite, l'affiche pour l'onglet en cours. Ouvrir **Help** ne traduit rien.

**Le déroulement, du début à la fin**

Une traduction est toujours lancée par un employé de la boutique depuis le back office. Les clients ne déclenchent rien.

1. **Réglages.** Dans **Settings**, collez votre clé Mistral, puis choisissez le modèle et la langue source. Cliquez sur **Test connection**, puis sur **Save**. Sans clé, aucune méthode ne peut envoyer de texte à Mistral.
2. **Choisissez votre façon de travailler.**
   - Quelques phrases ou un domaine, avec relecture avant enregistrement : **Manual** (3.3).
   - Un grand domaine, un thème ou un module : **Bulk**, puis suivez la tâche dans **Jobs** (3.4, 3.5).
   - Les champs des produits, des catégories et des pages CMS : **Catalog** (lots de 100 enregistrements au maximum, 3.7).
   - Les champs isolés sur la page **International → Translations** (3.12) et dans les formulaires produit, catégorie et CMS (3.13).
3. **Contrôle qualité.** Chaque texte traduit est vérifié : variables, balises et HTML. Un texte qui ne passe pas ce contrôle n'est pas enregistré. Un texte dont la note est inférieure à 70, qui est trop long (plus de deux fois et demie la longueur de l'original) ou qui contient encore des mots anglais est envoyé dans **Review**.
4. **Enregistrement.** Il dépend de la façon de travailler :
   - **Manual :** après **Translate selected (review)**, rien n'est enregistré tant que vous ne cliquez pas sur **Save approved**. Cocher **Save now (skip review)** enregistre immédiatement les lignes valides.
   - **Bulk :** la tâche attend dans **Jobs** et n'enregistre qu'au moment où vous la traitez (**Process slice**, **Auto-process**) ou où le cron s'en charge. Une tâche en dry-run n'enregistre jamais rien.
   - **Catalog :** enregistre les lignes tout de suite dans la langue cible choisie.
   - **La page International → Translations et les formulaires de la boutique :** les boutons remplissent seulement les champs. Le texte arrive dans la boutique lorsque vous cliquez sur **Save** dans PrestaShop.
   - Avec **Allow publish / save** désactivé, aucune de ces voies n'enregistre de texte dans la boutique.
5. **Fin du travail.** Une tâche dans **Jobs** se termine avec le statut **completed** (tout est enregistré) ou **completed_with_errors** (certains textes ont échoué ; voir 3.5). Les lignes de **Review** disparaissent après **Approve** ou **Reject**. Le résultat de **Catalog** indique combien de lignes ont été enregistrées et combien ont échoué.

### 3.1. Page de configuration du module

Allez dans **Modules** → **Module Manager**, repérez **AI Translations with Mistral** et cliquez sur **Configure**. Le **Dashboard** s'ouvre. Passez à l'onglet **Settings**.

**Settings** est un formulaire unique. Les champs se suivent dans l'ordre décrit ci-dessous. Les boutons **Save** et **Test connection** se trouvent en bas du formulaire, et non en haut.

![Settings : clé, modèle, ton et langue source. Écran en anglais.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-settings.webp)

![Settings : interrupteurs des boutons à côté des champs et limites. Écran en anglais.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-settings-fields.webp)

![Settings : coût, e-mail, adresse cron et boutons Test connection et Save. Écran en anglais.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-settings-cron.webp)

**Connexion**

| Champ | Par défaut | Rôle |
|---|---|---|
| **Mistral API key** | vide | La clé de votre compte Mistral. Collez-la depuis https://console.mistral.ai/api-keys. Laissez le champ vide pour conserver la clé déjà enregistrée. Une nouvelle valeur remplace la clé enregistrée ; un champ vide, lui, ne la supprime pas. La clé enregistrée s'affiche masquée. |
| **Model** | mistral-small-latest | Le modèle Mistral qui traduit. La liste comprend mistral-small-latest, mistral-medium-latest, mistral-large-latest, ministral-8b-latest, ministral-3b-latest et codestral-latest. Le modèle choisi s'applique dès la traduction suivante. Si votre compte n'a pas accès à un modèle, l'appel échoue et l'erreur est enregistrée dans **History**. |
| **Add a Mistral model** | vide | Champ situé sous la liste des modèles. Saisissez l'identifiant exact du modèle tel qu'il apparaît dans votre compte, puis cliquez sur **Add model**. Le nouveau modèle apparaît dans la liste et devient actif. Sous le champ figurent les modèles ajoutés à la main, chacun avec un bouton **Remove**. Les modèles intégrés ne peuvent pas être supprimés. |

Messages après ces actions : **Model added.**, **Model removed.**, **That model is already in the list. It is now the active model.**, **Enter a model id, for example mistral-small-latest.**, **Built-in models cannot be removed.**

**Style et langue**

| Champ | Par défaut | Rôle |
|---|---|---|
| **Tone** | Formal | Ajoute un style à chaque consigne : **Formal** pour un ton officiel dans la boutique et le back office, **Casual** pour un ton plus léger, **Brand** combiné au champ **Brand voice**. Les nouvelles traductions adoptent le style choisi. Les traductions existantes restent inchangées tant que vous ne les relancez pas. |
| **Brand voice** | vide | Apparaît lorsque vous choisissez **Tone: Brand**. Quelques phrases décrivant le ton de la boutique. Un champ vide n'ajoute aucune description. Le texte est pris en compte dans les consignes suivantes, mais ne modifie pas les traductions déjà enregistrées. |
| **Source locale** | — | La langue que le modèle considère comme l'original. En général, on choisit en-US, c'est-à-dire la langue dans laquelle vous rédigez vos catalogues. Le signe **—** indique que la langue source est donnée par l'écran depuis lequel vous traduisez. Ce réglage ne modifie pas la langue par défaut de la boutique. |
| **Individual field buttons — shop forms** | Yes | Un bouton de traduction à côté de chaque champ multilingue des formulaires de la boutique : produit, catégorie, CMS et autres. Chaque bouton traduit uniquement son champ. Avec **No**, ces boutons disparaissent de toute la boutique. Les traductions enregistrées ne changent pas. |
| **Individual field checkboxes — shop forms** | Yes | Les champs multilingues des formulaires de la boutique reçoivent des cases à cocher. La barre au bas du formulaire traduit les champs cochés, l'un après l'autre. Avec **No**, les cases et la barre disparaissent. |
| **Individual field buttons — International → Translations** | Yes | Un bouton à côté de chaque champ sur la page **International → Translations**. Les formulaires de la boutique ne sont pas modifiés. |
| **Individual field checkboxes — International → Translations** | Yes | Cases à cocher et barre sur la page **International → Translations**. Avec **No**, elles disparaissent de cette seule page. |

**Limites et coûts**

| Champ | Par défaut | Rôle |
|---|---|---|
| **Batch size** | 25 | Le nombre de textes envoyés dans un même appel. Au premier lancement, choisissez une valeur entre 10 et 25. La valeur doit rester entre 1 et 100. Un lot plus grand termine la tâche avec moins d'appels ; en cas d'erreur, un lot plus grand est relancé. |
| **Dry-run sample** | 10 | Le nombre de textes d'exemple affichés par **Estimate** dans **Bulk**. La valeur doit rester entre 1 et 50. L'estimation n'enregistre rien. |
| **Max tokens (0 = default)** | 0 | La longueur maximale d'une réponse. Saisissez 0 pour utiliser la limite par défaut de Mistral. Indiquez un nombre si les réponses sont tronquées ou trop longues. Le changement prend effet à partir de l'appel suivant. |
| **Budget USD / month** | 0 | Un plafond mensuel en dollars, calculé à partir du récapitulatif des coûts. Saisissez 0 pour ne pas avoir de plafond. Une fois le montant atteint, les nouvelles traductions s'arrêtent. Le travail déjà fait est conservé. |
| **Rate limit / min** | 60 | Le nombre d'appels à l'API que la boutique peut effectuer en une minute. Saisissez 0 pour désactiver cette limite locale. Les appels au-delà de la limite sont ignorés et consignés dans **History**. Mistral peut appliquer sa propre limite. |
| **Temperature** | 0.2 | La liberté que prend le modèle pour reformuler le texte. Vers 0.2, le texte reste proche de l'original ; des valeurs plus proches de 1 modifient davantage les phrases. La plage va de 0 à 1. Les contrôles des variables et du HTML restent actifs. |
| **Log retention days** | 30 | Le nombre de jours pendant lesquels les entrées de **History** sont conservées. Le minimum est 1. Les entrées plus anciennes sont supprimées. Les tâches, le glossaire et les traductions enregistrées ne sont pas effacés. |
| **Allow publish / save** | Yes | Indique si le module peut enregistrer une traduction dans la boutique. Avec **No**, l'enregistrement est bloqué dans **Manual** (boutons **Save approved** et **Save now**), dans **Bulk** (tâches hors dry-run) et dans **Catalog**. Les boutons des pages ne font que remplir les champs ; c'est PrestaShop qui enregistre. |

Messages après **Save** :

- **Settings saved. No translation was started.** (vert) – réglages enregistrés, rien n'a été traduit.
- **Settings saved. No API key is stored, so nothing can be translated until you paste one.** (jaune) – aucune clé n'est enregistrée ; collez-la.

**E-mail et cron**

| Champ | Par défaut | Rôle |
|---|---|---|
| **Email notify on complete** | No | Envoie un e-mail lorsqu'une tâche **Bulk** se termine. La tâche fonctionne de la même manière ; seul l'envoi change. |
| **Notify email** | vide | L'adresse qui reçoit l'e-mail de fin de tâche. Le champ apparaît une fois **Email notify on complete** activé. Enregistrer l'adresse ne déclenche aucun envoi. |
| **CRON URL** | adresse avec jeton | Adresse que le serveur peut appeler pour traiter un lot d'une tâche en attente. Chaque appel traite un lot puis se termine. Ne publiez pas cette adresse : quiconque la connaît peut déclencher un lot. Ouvrir **Settings** ne lance aucune tâche. |

**Test connection** vérifie la clé et le modèle à l'aide d'une requête brève. Il ne traduit rien et n'enregistre rien. Résultat possible :

- **Connection OK (N ms). No translation was started.** – la connexion fonctionne.
- **Connection was not made. Nothing was translated.** suivi d'un motif – vérifiez la clé et le modèle.

Pour bien démarrer : collez la clé, choisissez le modèle et la langue source, puis cliquez sur **Test connection**. Laissez les autres valeurs par défaut tant que les tâches se déroulent correctement.

### 3.2. Dashboard

Accès : le premier onglet, **Dashboard**.

![Dashboard : récapitulatif des manques, filtres de l'historique et cartes des appels. Écran en anglais.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-dashboard.webp)

![Dashboard : graphiques des appels et des tokens. Écran en anglais.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-dashboard-charts.webp)

![Dashboard : récapitulatifs et dix derniers appels. Écran en anglais.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-dashboard-latest.webp)

Le **Dashboard** comporte deux parties. La première récapitule les textes qui n'ont pas encore de traduction. La seconde présente l'historique des appels à Mistral, sous forme de cartes et de graphiques. La page ne traduit rien et ne modifie aucun texte.

**Récapitulatif des textes manquants**

- **Locale :** choisissez la langue dont vous voulez compter les textes manquants.
- **Show :** actualise le tableau pour la langue choisie.
- Le tableau comporte les colonnes **Section**, **Total**, **Missing** et **Done**. La colonne **Done** contient une barre de progression. Les sections sont **Back office**, **Themes**, **Installed modules**, **Emails** et **Others**. **Missing** indique le nombre de textes sans traduction dans cette langue.
- Après un clic sur **Show**, le message **Coverage for [langue]. This page only counts strings. Nothing was translated.** apparaît.
- Sous le tableau, la ligne **CRON** affiche l'adresse cron, identique à celle de **Settings**.
- Un tableau vide signifie que la boutique n'a pas encore de catalogue pour cette langue. Vous le créez dans **International → Translations**.

**Historique des appels**

- **Filter** fonctionne avec les préréglages **Today**, **7 days**, **30 days**, **This month** et **All time**, ainsi qu'avec les champs **From**, **To**, **Model**, **Type**, **Status** (**Any**, **Success**, **Error**), **Language**, **Employee** et **Prompt or reply contains**.
- Les cartes affichent **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** et **Estimated cost**. Le coût est une estimation, pas une facture.
- Graphiques : **Requests and errors**, **Tokens sent and received**, **Requests by model**.
- Sous les graphiques, cinq récapitulatifs : **By day**, **By model**, **By type**, **By language** et **By employee**. Lorsque la période contient des appels, chaque récapitulatif est un tableau avec les colonnes **Group**, **Calls**, **Sent**, **Received** et **Total**. Sinon, vous voyez **No requests in this range.**
- **Latest prompts** affiche les dix derniers appels, avec les colonnes **When**, **Status**, **Type**, **Languages** et **Preview**. Si la liste est vide, le message **No requests yet.** s'affiche. **View** ouvre une fenêtre contenant la consigne envoyée et la réponse. **See all** mène à **History** (3.10).

Et ensuite : si la plupart des textes d'une section manquent, ouvrez **Manual** pour en traduire quelques-uns, ou **Bulk** pour traduire tout le domaine.

### 3.3. Manual

Accès : onglet **Manual**.

![Manual : filtre. Le bouton Filter se trouve sous le champ Search. Écran en anglais.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-manual.webp)

**Manual** traduit un domaine ou un module, quelques dizaines de textes à la fois. Le filtrage n'enregistre rien.

**Champs du filtre**

| Champ | Par défaut | Rôle |
|---|---|---|
| **Section** | Back office | Choisit le catalogue PrestaShop à lire : **Back office**, **Themes**, **Installed modules**, **Emails** ou **Others**. Changer de section recharge la page, n'affiche que les champs de cette section et n'appelle pas Mistral. |
| **Theme** | — | Visible uniquement pour **Themes**. Limite la liste à un seul thème. Les autres thèmes sont ignorés. |
| **Module** | — | Visible uniquement pour **Installed modules**. Limite la liste à un seul module. Un module sans domaine (classique) affiche tous ses textes d'un coup. |
| **Domain** | — | Un groupe de textes, identique à celui de **International → Translations**. Choisissez-le et cliquez sur **Filter**. Masqué pour un module classique et pour les sections sans domaine. |
| **Source** | en-US ou la valeur de **Settings** | La langue d'où vous prenez les textes. Choisissez une langue qui a déjà de bonnes traductions. |
| **Target** | première langue de la liste | La langue que vous voulez compléter. Elle doit exister dans **International → Localization → Languages**. |
| **Only empty** | Yes | N'affiche que les textes sans traduction. Désactivé, il affiche tous les textes. Les traductions enregistrées ne sont pas supprimées. |
| **Search** | vide | Ne conserve que les textes source contenant le mot saisi. |

Étapes :

1. Réglez **Section**, **Source** et **Target**.
2. Pour **Themes**, choisissez un **Theme**. Pour **Installed modules**, choisissez un **Module**.
3. Cliquez sur **Filter**. La liste **Domain** se met à jour. Choisissez un domaine et cliquez de nouveau sur **Filter**. Pour un module classique, ignorez le domaine : **Filter** charge tous les textes du module.
4. Cochez les lignes voulues. Pour cocher, utilisez **Check all**, **Uncheck all** ou les cases situées devant chaque ligne.
5. Après **Filter**, la liste affiche les colonnes **Source**, **Current** et **Status** (**empty** ou **filled**). Au-dessus de la liste se trouvent **Translate selected (review)** et la case **Save now (skip review)**.
6. Cliquez sur **Translate selected (review)**. Le tableau **Review before save** apparaît, avec les colonnes case à cocher, **Source**, **AI proposal** et **Warnings**. Les lignes qui passent le contrôle sont déjà cochées. Décochez celles que vous ne voulez pas et, si besoin, corrigez la proposition directement dans son champ. Cliquez sur **Save approved** pour enregistrer les lignes cochées.
7. À la place de l'étape 6, vous pouvez cocher **Save now (skip review)** avant de traduire. Les lignes valides sont alors enregistrées immédiatement, sans passer par le tableau de relecture.

**Messages**

- **Loaded N strings. Tick the rows you want, then press Translate selected. Nothing is saved yet.** – la liste est prête.
- **No strings match this filter. Nothing was sent to Mistral.** – modifiez le filtre ou désactivez **Only empty**.
- **Nothing was translated. Choose a domain, then press Filter to load the strings.** – choisissez un domaine.
- **Nothing was translated. Tick at least one row.** – cochez au moins une ligne.
- **Review is ready. Nothing is saved until you press Save approved.** – les traductions sont prêtes ; rien n'est enregistré avant que vous cliquiez sur **Save approved**.
- **Saved. The approved strings were written for the target language.** – après **Save now (skip review)**, les lignes valides ont été enregistrées.
- **Saved N. Only the ticked rows were written.** – après **Save approved**, les lignes cochées ont été enregistrées.
- **Nothing was saved. Tick OK on the rows you want to keep.** – aucune ligne n'est cochée dans le tableau de relecture. Cochez les lignes à conserver et cliquez de nouveau sur **Save approved**.
- **Not saved because of broken placeholders or HTML: N.** – N lignes n'ont pas passé le contrôle et ont été ignorées. Corrigez-les à la main dans le tableau pour que les variables et les balises HTML soient identiques à l'original.
- **Nothing was saved. Turn on Allow publish in Settings.** – activez **Allow publish / save**.
- **Nothing was translated. Those rows are not in the current list. Press Filter and tick them again.** – la liste a changé. Cliquez sur **Filter** et cochez de nouveau les lignes.
- **Loaded N strings from the whole module. Tick the rows you want, then press Translate selected. Nothing is saved yet.** – module classique, sans domaine. La liste complète est chargée.
- **This module has no translation domain. Press Filter to load every string in the module. Nothing was sent to Mistral.** – le même cas, avant que vous cliquiez sur **Filter**.
- **Nothing was translated. Pick a theme, then press Filter.** / **Nothing was translated. Pick a module, then press Filter.** – choisissez un thème ou un module.

### 3.4. Bulk

Accès : onglet **Bulk**.

![Bulk : périmètre de la tâche. Écran en anglais.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-bulk.webp)

![Bulk : politique, essai sans enregistrement et boutons Start job et Estimate. Écran en anglais.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-bulk-actions.webp)

**Bulk** crée une seule tâche couvrant plusieurs domaines et plusieurs langues. L'estimation n'enregistre rien. **Start job** ajoute la tâche à la liste **Jobs**. Rien ne sera enregistré tant que la tâche n'est pas traitée et que **Allow publish / save** est activé.

**Champs**

| Champ | Par défaut | Rôle |
|---|---|---|
| **Section** | Back office | Le catalogue que la tâche lit. Même choix que dans **Manual**. |
| **Theme** / **Module** | — | N'apparaissent que pour la section correspondante, comme dans **Manual**. |
| **Source** | en-US ou la valeur de **Settings** | La langue considérée comme l'original. Chaque langue cible est traduite à partir de celle-ci. |
| **Targets** | aucune | Une ou plusieurs langues à compléter. Pour en sélectionner plusieurs, maintenez la touche Ctrl (Cmd sur Mac). Un simple clic remplace la sélection. |
| **Domains** | aucun | Les domaines couverts par la tâche. Sélectionnez-en plusieurs avec Ctrl ou Cmd. Si vous n'en sélectionnez aucun, la tâche couvre tous les domaines de la section choisie. |
| **Policy** | Fill empty | **Fill empty** n'envoie que les textes sans traduction. **Overwrite all** envoie tous les textes, y compris ceux déjà traduits, et peut les écraser. **Outdated if equals source** n'envoie que les textes dont la traduction est identique à l'original. |
| **Dry-run job** | No | Le modèle fait le travail et la tâche apparaît dans **Jobs**, mais les réponses ne sont pas envoyées à la boutique. Pratique pour vérifier le coût et la qualité. |

**Étapes**

1. Choisissez la section, la langue source, les langues cibles, les domaines et la politique.
2. Cliquez sur **Estimate**. Au-dessus du formulaire s'affiche l'estimation : nombre de textes, nombre de tokens prévu, coût et échantillon de textes.
3. Si l'estimation vous convient, cliquez sur **Start job**. **Jobs** s'ouvre avec la nouvelle tâche.
4. Traitez la tâche dans **Jobs** (3.5), ou laissez-la au cron.

**Messages**

- **Estimate only: N strings, ~N tokens, ~$X. Nothing was sent to Mistral and nothing was saved.** – résultat de l'estimation.
- **Job #N is waiting (N strings, est. $X). It has not run yet.** – la tâche est créée et attend.
- **Nothing was started. Select at least one target language.** – aucune langue cible sélectionnée.
- **Nothing was started. Pick a theme.** / **Nothing was started. Pick a module.** – choisissez un thème ou un module.
- **Nothing was started. There is no Mistral API key. Open Settings and paste the key. No job was created.** – aucune clé enregistrée.

### 3.5. Jobs

Accès : onglet **Jobs**.

![Jobs : liste des tâches. Une liste vide affiche No jobs yet. Écran en anglais.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-jobs.webp)

**Liste des tâches**

Lorsqu'il n'existe aucune tâche, le tableau affiche **No jobs yet.**

Chaque ligne correspond à un lancement depuis **Bulk**. Colonnes : **#**, **Status**, **Locales** (langue source → langues cibles), **Progress** (effectué/total), **Cost**, **Employee** et **Date**. **Open** ouvre la tâche.

Statuts d'une tâche, exactement tels qu'ils apparaissent à l'écran :

- `pending` – en attente, rien n'a encore été traité. Elle ne démarre pas toute seule.
- `running` – en cours.
- `paused` – suspendue. Elle ne traite plus rien tant que vous ne la reprenez pas.
- `cancelled` – annulée. Les textes encore en attente n'ont pas été traduits.
- `completed` – tous les textes ont été traités sans erreur.
- `completed_with_errors` – terminée, mais certains textes ont échoué.
- `failed` – la tâche s'est arrêtée sur une erreur.

**Écran de la tâche**

Une fois la tâche ouverte, vous voyez l'en-tête **Job #N**, le statut, la progression (**done/total**), le nombre de **failed** et de **skipped**, le coût, l'employé et l'étiquette **dry-run** si la tâche est un essai. La barre de progression se met à jour toute seule toutes les 2 à 3 secondes tant que la tâche reste ouverte. Le tableau en dessous présente les lignes de la tâche : **ID**, **Domain**, **Locale**, **Status**, **Source**, **New** et **Error**.

Statuts des lignes : `pending`, `processing`, `done`, `failed`, `skipped` (ignorée, car elle correspond à une exclusion ou parce que le texte était déjà traduit) et `rolled_back` (annulée).

**Boutons**

- **Process slice** – traite un lot (**Batch size** textes), puis s'arrête. Message : **One slice was processed. Check the rows below to see what was saved, skipped or failed.** S'il ne reste plus rien à faire : **The job has no more strings waiting.**
- **Auto-process** – enchaîne les lots jusqu'à la fin de la tâche ou jusqu'à une erreur. Il tourne dans le navigateur, donc uniquement tant que l'onglet reste ouvert. Fermer l'onglet l'arrête ; la tâche reste en place et peut être terminée avec un nouveau **Process slice** ou par le cron.
- **Pause** – suspend la tâche. Message : **Job paused. It will not translate more strings until you resume it.**
- **Resume** – la remet dans la file d'attente. Message : **Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.** La tâche ne repart pas toute seule.
- **Retry failed** – les textes en erreur repassent en attente, et la tâche revient à l'état d'attente. Message : **Retried N failed items.**
- **Rollback** – rétablit la traduction précédente lorsque le module a enregistré une copie avant la modification. Vous devez d'abord confirmer **Roll back this job?** Message après exécution : **Rollback: restored N translations.**
- **Error CSV** – télécharge un fichier CSV contenant les lignes en erreur. Colonnes : **id**, **domain**, **locale**, **source**, **error**.
- **Failed only** – n'affiche dans le tableau que les lignes en erreur.
- **Review queue** – ouvre **Review** (3.6).

L'écran de la tâche ne comporte pas de bouton d'annulation. Pour l'arrêter, utilisez **Pause**.

**Suspension automatique**

Lorsque Mistral refuse des appels en raison d'une limite, la tâche se met toute seule en pause avec le statut `paused`. Le champ d'erreur affiche alors **Rate limit — job auto-paused. Resume later.** Patientez, puis cliquez sur **Resume**. Le réglage **Rate limit / min** dans **Settings** réduit le nombre d'appels par minute.

**Messages d'erreur**

- **Nothing was translated.** suivi de **No Mistral API key. Nothing was translated.** – aucune clé : la tâche ne démarre pas. Collez la clé dans **Settings**.
- **Allow publish is off in Settings.** – une tâche hors dry-run ne démarrera pas tant que vous n'aurez pas activé **Allow publish / save**.
- **Monthly API budget has been exhausted.** – le budget mensuel est épuisé. Augmentez **Budget USD / month** ou saisissez 0.

### 3.6. Review

Accès : onglet **Review**, ou bouton **Review queue** sur l'écran d'une tâche.

![Review : file de relecture. Une liste vide affiche The queue is empty. Écran en anglais.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-review.webp)

Au-dessus du tableau figure l'en-tête **Needs-review queue (quality score / flags).** **Review** liste les textes que le contrôle qualité n'a pas laissés passer automatiquement. Elle affiche jusqu'aux 100 lignes les plus récentes.

Colonnes : **ID**, **Score**, **Domain**, **Source**, **AI** (proposition), **Flags**, ainsi que les boutons **Approve** et **Reject**. Une liste vide affiche **The queue is empty.**

**Lire une ligne**

- **Score** – une note de 0 à 100. En dessous de 70, la ligne passe en relecture.
- **Flags** – les raisons de la mise en attente :
  - `validation_failed` – le texte n'a pas passé le contrôle des variables ou du HTML.
  - `warning` – une remarque mineure du contrôle.
  - `length_explosion` – la traduction est plus de deux fois et demie plus longue que l'original.
  - `too_short` – la traduction est nettement plus courte que l'original, qui est le plus long des deux.
  - `possible_untranslated` – des mots anglais sont restés dans la traduction, par exemple the, and, with, your ou please.
- **Source** – le texte d'origine. **AI** – la proposition du modèle.

**Approve** et **Reject** ne modifient que le statut de la ligne. Message : **Review updated.** La ligne disparaît de la liste. Cette action n'envoie aucun texte à la boutique et ne touche pas au reste du domaine.

Si la tâche a déjà enregistré des résultats, la proposition est peut-être déjà dans la boutique. Pour annuler les modifications apportées par une tâche, utilisez **Rollback** sur l'écran de cette tâche, dans **Jobs**.

### 3.7. Catalog

Accès : onglet **Catalog**.

![Catalog : lot du catalogue. Le bouton Translate batch (max 100) se trouve sous le champ Start after ID. Écran en anglais.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-catalog.webp)

**Catalog** traduit les champs des produits, des catégories et des pages CMS enregistrés dans les langues de la boutique. Il ne concerne pas **International → Translations**. Un seul clic traite au maximum 100 enregistrements. L'enregistrement se fait immédiatement dans les données de la langue cible choisie.

**Champs**

| Champ | Par défaut | Rôle |
|---|---|---|
| **Entity** | product | Ce que vous traduisez : **product**, **category** ou **cms**. Le changement recharge la page et n'affiche que les champs de ce type. Le changement seul ne traduit rien. |
| **Fields** | tous les champs de la liste | Les textes que le lot envoie. Cochez uniquement ceux qui doivent changer. Les champs non cochés ne sont pas envoyés et restent inchangés. Pour un produit : **Title**, **Short description**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. Pour une catégorie : **Title**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. Pour un CMS : **Title**, **Meta description**, **Meta keywords**, **Content**, **Friendly URL**. |
| **Source language** | première langue de la liste | La langue d'où les textes sont pris. |
| **Target language** | première langue de la liste | La langue dans laquelle va la traduction. Elle doit être différente de la langue source. |
| **Only empty** | Yes | Ignore les champs qui ont déjà un texte dans la langue cible. Désactivez-le uniquement si vous voulez remplacer un texte existant. |
| **Start after ID** | 0 | Ignore les enregistrements dont l'ID est inférieur ou égal à la valeur saisie. Après un lot, le champ se place sur le dernier ID traité. Cliquez de nouveau sur le bouton pour continuer. |

Bouton : **Translate batch (max 100)**.

**Étapes**

1. Choisissez **Entity** et cochez les champs.
2. Choisissez **Source language** et **Target language**.
3. Laissez **Only empty** activé.
4. Cliquez sur **Translate batch (max 100)**. Le résultat s'affiche sous la forme : **Catalog finished: saved N, failed M.**
5. Ouvrez un produit dans la langue cible et vérifiez le résultat. Ce n'est qu'ensuite que vous désactivez **Only empty** ou passez au lot suivant.

**Messages**

- **Nothing was translated. Select at least one field.** – cochez des champs.
- **Nothing was translated. Source and target language must be different.** – choisissez deux langues différentes.
- **Nothing was saved. Turn on Allow publish in Settings.** – activez **Allow publish / save**.
- **Nothing was translated. There is no Mistral API key. Open Settings and paste the key.** – aucune clé enregistrée.

### 3.8. Glossary

Accès : onglet **Glossary**.

![Glossary : ajout d'un terme. Écran en anglais.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-glossary.webp)

![Glossary : import et export CSV et liste de termes vide. Écran en anglais.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-glossary-csv.webp)

Le glossaire est une liste de mots et d'expressions que le modèle doit conserver ou toujours traduire de la même façon. Ajouter une ligne ne modifie pas les traductions déjà enregistrées, mais la traduction suivante tiendra compte de la liste.

**Ajouter un terme**

| Champ | Par défaut | Rôle |
|---|---|---|
| **Source term** | vide, obligatoire | Le mot ou l'expression dans la langue source. Saisissez-le exactement comme il apparaît, avec les majuscules si elles comptent. |
| **Target locale** | vide | Limite la ligne à une seule langue, par exemple pl-PL. Vide signifie que la ligne vaut pour toute langue cible. |
| **Target term** | vide | La traduction validée du terme. Ce champ ne peut rester vide que si **Do not translate** est activé. |
| **Do not translate** | No | Activé : le modèle recopie le terme sans le modifier, par exemple un nom de marque, un SKU ou un marqueur. Désactivé : il utilise **Target term**. |

Bouton : **Add**. Messages : **Glossary term added. Translations already stored were not changed.** ou **Nothing was added. Type a source term.**

**Tableau**

Colonnes : **Source**, **Locale**, **Target**, **Do not translate** (Yes ou No) et un bouton **Delete** sur chaque ligne. Il ne supprime que cette ligne. Message : **Glossary term deleted.** Liste vide : **No glossary terms yet.**

**Import et export CSV**

- **CSV file** – choisissez un fichier, puis cliquez sur **Import CSV**. Message : **Imported N rows.**
- Format du fichier : la première ligne est l'en-tête `source_term`, `target_locale`, `target_term`, `do_not_translate`. Elle est toujours ignorée. Les lignes qui ont moins de trois colonnes sont aussi ignorées. Dans la quatrième colonne, une valeur vide ou 0 signifie **No**, et toute autre valeur signifie **Yes**.
- L'import ajoute les lignes du fichier. Il ne vérifie pas si un terme existe déjà ; réimporter le même fichier crée donc des doublons.
- **Export CSV** télécharge la liste actuelle sous forme de fichier `glossary.csv`. Il ne demande aucun fichier d'entrée et ne modifie rien.

Conseil : utilisez des termes courts et précis. Un terme trop général sera imposé à chaque fois qu'il apparaîtra.

### 3.9. Excludes

Accès : onglet **Excludes**.

![Excludes : motifs d'exclusion. Une liste vide affiche No patterns yet. Écran en anglais.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-excludes.webp)

Une exclusion est un motif de texte source que le module n'envoie jamais à Mistral. Le texte reste tel quel dans la boutique. Les exclusions s'appliquent à toutes les façons de travailler : **Manual**, **Bulk**, **Catalog** et les pages de traduction.

**Ajouter un motif**

| Champ | Par défaut | Rôle |
|---|---|---|
| **Pattern** | vide, obligatoire | Le texte ou l'expression comparé à chaque texte source. La comparaison dépend de **Type**. |
| **Type** | exact | **exact** – le texte entier doit être identique. **prefix** – le texte commence par le motif. **contains** – le motif apparaît à n'importe quel endroit. **regex** – expression régulière PHP. |

Bouton : **Add**. Message : **Exclude pattern added. Matching strings will be skipped on the next run. Nothing was translated now.** Si le champ est vide : **Nothing was added. Type a pattern.**

Un motif de type **regex** est appliqué exactement tel que vous l'avez saisi. Une expression erronée ne correspond à rien. Commencez par un motif court et vérifiez ce qu'il a ignoré.

**Tableau**

Colonnes : **Pattern**, **Type**, **On** et **Delete**. La colonne **On** affiche 1 pour un motif actif. Cet écran ne propose pas d'interrupteur : pour désactiver un motif, supprimez-le puis ajoutez-le de nouveau. **Delete** ne supprime que ce motif ; les traductions existantes sont conservées. Message : **Pattern deleted.** Liste vide : **No patterns yet.**

Utilisez les exclusions pour les textes qui doivent rester dans la langue source, par exemple une dénomination légale ou un marqueur technique. Pour les textes qui doivent toujours être traduits de la même façon, utilisez **Glossary**.

### 3.10. History

Accès : onglet **History**, ou bouton **See all** sur le **Dashboard**.

![History : liste de l'historique. Une liste vide affiche No requests yet. Écran en anglais.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-history.webp)

**History** est la liste complète des appels enregistrés à Mistral : traductions manuelles, pages de traduction, tâches **Bulk**, **Catalog** et tests de connexion. Chaque entrée contient le texte envoyé, la réponse, le modèle, les langues, le nombre de tokens et la durée de l'appel. Les cartes, les graphiques et les filtres se trouvent sur le **Dashboard**, et non sur cette page. Ouvrir cette page n'envoie aucune requête et ne modifie aucune traduction. La phrase sous le champ **Model** dans **Settings** parle de **Logs** : ces entrées sont bien ici. Il n'y a pas d'onglet Logs séparé.

**Colonnes de la liste :** **ID**, **When**, **Status**, **Type**, **Model**, **Languages**, **Sent**, **Received**, **Total**, **Time** et **Prompt**. Types : **Manual**, **Translation page**, **Bulk job**, **Catalog**, **Connection test**, **Translate** et **Not sent** (l'appel n'est jamais parti, par exemple à cause de la limite locale ou du budget). Pour une entrée **Bulk job**, le numéro de la tâche est affiché.

- **View** ouvre une fenêtre contenant la consigne envoyée et la réponse. En cas d'erreur, le message d'erreur remplace la réponse.
- Une entrée avec une erreur d'accès signifie que la clé dans **Settings** est incorrecte, ou que le compte n'a pas le droit d'utiliser le modèle choisi.
- **Previous**, **Next** et le champ **Page** permettent de naviguer entre les pages de la liste.
- **Clear history** supprime ces entrées. Vous devez confirmer avec le message **Clear the stored history? Saved translations stay.** Après exécution, le message **History cleared. Saved translations were not changed.** s'affiche.

Si les traductions s'arrêtent soudainement, ouvrez l'entrée en erreur la plus récente sur cette page avant de modifier le glossaire.

### 3.11. Updates

Accès : onglet **Updates**, à droite du menu.

![Updates : vérification des mises à jour. Écran en anglais.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-updates.webp)

Le panneau s'appelle **MyPresta Updates**.

- **Manual Check** – le bouton **Check Now** vérifie la version immédiatement.
- **Automatic Notifications** – **Enabled** ou **Disabled**. Lorsqu'il est activé, le module vérifie si une version plus récente existe sur le serveur MyPresta et affiche un avertissement dans le back office.
- **Product Page** – lien vers la page du module.
- **Save** – enregistre le choix fait pour **Automatic Notifications**.

Messages : **Update settings saved.**, **New version available!**, **Module is up to date!**

### 3.12. Boutons sur la page International → Translations

Accès : **International** → **Translations**. Choisissez le type de traduction et la langue, puis cliquez sur **Modify**. Les boutons à côté des champs apparaissent lorsque **Individual field buttons — International → Translations** est activé dans **Settings**. Les cases à cocher et la barre apparaissent lorsque **Individual field checkboxes — International → Translations** est activé.

![Barre Mistral translations en bas de la page International → Translations. Écran en anglais.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-translations-page.webp)

**Ce que vous voyez**

- À côté de chaque champ de texte, un bouton qui traduit ce champ.
- À côté de chaque champ, une case à cocher (si les cases sont activées).
- Une barre intitulée **Mistral translations** : le champ **Source** (en-US par défaut, ou la valeur de **Settings**), la liste **Target**, les boutons **Check all**, **Uncheck all**, **Check empty**, **Translate empty** et **Translate selected**, ainsi que l'indication **Fills the fields. Save with the PrestaShop button.**

**Étapes**

1. Choisissez **Target**.
2. Cochez les champs à remplir, ou cliquez sur **Check empty**.
3. Cliquez sur **Translate selected**, ou sur **Translate empty**, qui remplit les champs vides de la section.
4. Attendez que la barre affiche **Done (N)**. La progression apparaît sous la forme **Translating… N/M**.
5. Vérifiez les champs remplis, puis enregistrez la page avec le bouton **Save** de PrestaShop.

Les boutons ne font que remplir les champs. Sans **Save** dans PrestaShop, le texte n'atteint pas la boutique. Lorsque **Allow publish / save** est désactivé, les champs sont tout de même remplis, et c'est PrestaShop qui enregistre.

**Messages**

- **Target is not a language from this shop.** – la langue choisie n'existe pas dans cette boutique.
- **Fill the source language field first.** – remplissez d'abord le champ de la langue source.
- **The source language field is not on this page.** – cette page ne contient pas de champ pour la langue source.
- **The source language mail file was not found.** – le fichier source de l'e-mail est introuvable. Dans **Settings**, choisissez un autre **Source locale** pour lequel des fichiers d'e-mail existent.

Pour la section **Emails**, le texte source provient du fichier source du modèle d'e-mail, et non d'un champ de la page.

### 3.13. Boutons dans les formulaires produit, catégorie et CMS

Accès : le formulaire d'un produit, d'une catégorie, d'une page CMS ou de tout autre formulaire de la boutique comportant des champs multilingues. Les boutons sont visibles lorsque **Individual field buttons — shop forms** et **Individual field checkboxes — shop forms** sont activés dans **Settings**.

![Barre en bas du formulaire produit et case à cocher à côté d'un champ multilingue. Écran en anglais.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-product-form.webp)

**Ce que vous voyez**

- À côté de chaque champ multilingue, un bouton qui traduit ce champ.
- À côté des champs, une case pour l'ajouter à la barre.
- Une barre au bas de la page du produit, avec l'étiquette **Mistral translations**, la liste de langues **Translate from … to …**, les boutons **Check all**, **Uncheck all**, **Check empty**, **Translate empty** et **Translate selected**, ainsi que l'indication **Fills the fields. Save with the PrestaShop button.**

**Étapes**

1. Remplissez le champ dans la langue source. Sans cela, la barre affiche **Fill the source language field first.**
2. Choisissez la langue cible sur la barre.
3. Cliquez sur le bouton d'un champ, ou cochez plusieurs champs et cliquez sur **Translate selected**. **Translate empty** remplit les champs vides.
4. Une fois terminé, cliquez sur **Save** dans le formulaire PrestaShop. Sans cela, le texte n'est pas enregistré.

Le bouton remplit seulement le champ du formulaire. L'enregistrement se fait avec le bouton **Save** du formulaire de produit, de catégorie ou de CMS. Les champs que vous n'avez pas cochés restent inchangés.

## 4. Côté boutique

Le module n'ajoute rien aux pages de la boutique que voient les clients. Ceux-ci n'ont aucun écran ni bouton lié au module : il n'y a donc rien à vérifier dans le thème.

La seule adresse en dehors du back office est l'adresse cron. Elle est destinée à une tâche planifiée sur le serveur et ne doit pas être utilisée par les clients.

- **Où copier l'adresse :** **Settings** → **CRON URL**, ou **Dashboard** → ligne **CRON**.
- **Que faire :** collez l'adresse dans le planificateur de tâches du serveur, par exemple toutes les quelques minutes. Chaque appel traite un lot d'une tâche en attente.
- **L'adresse fonctionne en HTTPS.** Si la boutique utilise SSL, utilisez l'adresse qui commence par `https://`.

| Ce que vous voyez à l'ouverture de l'adresse | Que faire |
|---|---|
| Le message **Forbidden** | L'adresse est incomplète ou a été modifiée. Copiez-la de nouveau depuis **Settings**. |
| Le message **No pending jobs** | Aucune tâche n'est en attente ou en cours. Créez une tâche dans **Bulk**, ou reprenez une tâche suspendue dans **Jobs**. |
| Des données au format JSON avec le résultat du lot (champs `ok`, `finished`, `counts`) | Un lot de la tâche a été traité. Vérifiez la progression dans **Jobs**. |

Le cron ne prend en charge que les tâches au statut `pending` ou `running`. Une tâche `paused` doit être reprise à la main.

## 5. Problèmes courants

| Symptôme (ce que vous voyez) | Cause | Que faire |
|---|---|---|
| **No Mistral API key.** sur chaque page du module | La clé n'a pas été enregistrée. | Allez dans **Settings**, collez la clé dans **Mistral API key** et cliquez sur **Save**. |
| **Settings saved. No API key is stored, so nothing can be translated until you paste one.** | Les réglages ont été enregistrés sans clé. | Collez la clé dans **Mistral API key** et cliquez sur **Save**. |
| **Connection was not made. Nothing was translated.** après **Test connection** | Clé incorrecte, pas de connexion au serveur, ou modèle indisponible pour le compte. | Vérifiez la clé, choisissez un autre **Model** ou ajoutez un identifiant correct dans **Add a Mistral model**. Les détails figurent dans **History**. |
| Les appels échouent avec une erreur d'accès dans **History** | La clé est incorrecte, ou le compte ne peut pas utiliser le modèle choisi. | Corrigez la clé ou choisissez un modèle disponible pour le compte. |
| **Nothing was started. There is no Mistral API key.** dans **Bulk** | Aucune clé n'est enregistrée. | Collez la clé dans **Settings**, puis refaites **Estimate** et **Start job**. |
| La tâche reste en `pending` et rien ne se passe | La tâche ne démarre pas toute seule. | Cliquez sur **Process slice** ou **Auto-process** dans **Jobs**, ou configurez le cron (section 4). |
| Une tâche est en `paused` avec le message **Rate limit — job auto-paused. Resume later.** | Mistral a refusé des appels à cause d'une limite. | Patientez quelques minutes et cliquez sur **Resume**. Réduisez **Batch size** ou **Rate limit / min**. |
| **Monthly API budget has been exhausted.** | Le **Budget USD / month** a été dépassé. | Augmentez le montant ou saisissez 0. Un nouveau mois repart de zéro. |
| **Nothing was saved. Turn on Allow publish in Settings.** | **Allow publish / save** est désactivé. | Activez **Allow publish / save** dans **Settings**. |
| **Not saved because of broken placeholders or HTML: N.** dans **Manual** | La traduction a modifié des variables ou des balises HTML. | Corrigez la ligne à la main dans le tableau de relecture, pour que les variables et les balises soient identiques à l'original, puis enregistrez. |
| Une tâche se termine avec le statut `completed_with_errors` | Une partie des textes a échoué. | Ouvrez la tâche, cochez **Failed only**, téléchargez **Error CSV**, puis cliquez sur **Retry failed**. |
| Les lignes de **Review** ont un **Score** faible | Le contrôle qualité ne les a pas laissées passer. | Comparez **Source** et **AI**. Validez avec **Approve** ou rejetez avec **Reject**. Si un enregistrement est erroné, utilisez **Rollback** dans la tâche. |
| La traduction est enregistrée, mais la boutique affiche toujours l'ancien texte | L'enregistrement vide le cache de PrestaShop, mais le thème ou le navigateur peuvent conserver l'ancienne page. | Allez dans **Advanced Parameters** → **Performance**, videz le cache et actualisez la page de la boutique. |
| Une **Exclude pattern** n'ignore pas le texte | Mauvais **Type** ou expression **regex** incorrecte. | Dans **Excludes**, changez le type, ou supprimez le motif et ajoutez-le de nouveau avec un texte plus court. |
| Un nouveau terme du glossaire ne s'applique pas aux traductions enregistrées | Le glossaire agit sur les nouvelles traductions ; les textes déjà enregistrés ne sont pas modifiés. | Relancez la traduction de ces textes dans **Bulk** avec la politique **Overwrite all**, après vérification dans **Estimate**. |
| **The source language mail file was not found.** | Il n'existe pas de fichier d'e-mail pour la langue source choisie. | Choisissez dans **Settings**, ou sur la page des traductions, un autre **Source locale** pour lequel des fichiers d'e-mail existent. |
| **No strings match this filter. Nothing was sent to Mistral.** | Le filtre ne correspond à aucun texte. | Désactivez **Only empty**, effacez **Search** ou choisissez un autre domaine. |
| **Nothing was translated. Tick at least one row.** | Aucune ligne n'est cochée. | Cochez des lignes et cliquez sur **Translate selected (review)**. |
| **Nothing was translated. Source and target language must be different.** dans **Catalog** | La même langue est choisie comme source et comme cible. | Choisissez une autre **Target language**. |
| Le Dashboard affiche un récapitulatif vide | La boutique n'a pas encore de catalogue pour la langue choisie. | Créez le catalogue dans **International → Translations**, puis revenez sur le **Dashboard**. |
| L'historique contient des entrées **Not sent** | La limite locale ou le budget a bloqué l'appel. | Vérifiez **Rate limit / min** et **Budget USD / month** dans **Settings**. |

## 6. Pour les développeurs

### 6.1. Vue d'ensemble

- **Classe principale :** `myaitranslationsmistral`, fichier `myaitranslationsmistral.php`.
- **Version :** 1.2.0.
- **Nom technique :** `myaitranslationsmistral`. Dans la liste des modules, il apparaît sous le nom **AI Translations with Mistral**.
- **Auteur :** MyPresta.eu. Onglet du module dans Module Manager : `administration`.
- **Onglet du back office :** `AdminMyaitranslationsmistral`, rattaché à `AdminInternational` (solution de repli : `IMPROVE`).
- **Installation :** `parent::install()`, tables définies dans `sql/install.php` (`CREATE TABLE IF NOT EXISTS`), valeurs par défaut via `installDefaults()` (seules les clés manquantes sont définies), enregistrement des hooks `displayBackOfficeHeader` et `actionAdminControllerSetMedia`, création de l'onglet.
- **Désinstallation :** suppression de l'onglet, exécution de `sql/uninstall.php` (supprime 11 tables), suppression des clés `MYAITMI_*` via `removeConfiguration()`, puis `parent::uninstall()`.
- Le module n'a **pas** de méthodes `enable()` ni `disable()`.
- **Configuration :** `getContent()` redirige vers `AdminMyaitranslationsmistral` (onglet `dashboard` par défaut).

**Flux de données**

1. Les formulaires de `MyaitmiForms` (onglet `settings`) envoient leurs valeurs à `AdminMyaitranslationsmistralController::initContent()`.
2. `MyaitmiConfigService::saveFromForm()` enregistre les clés `MYAITMI_*` dans `Configuration`. `MyaitmiApiKeyEncryptor` chiffre la clé API (AES-256-CBC, clé dérivée de `_COOKIE_KEY_`) et la stocke sous `MYAITMI_API_KEY_ENC`.
3. Traduction : `MyaitmiTranslateService::translateMessages()` construit les consignes (`MyaitmiPromptBuilder`), les envoie via `MyaitmiMistralTranslationProvider` (cURL, POST vers `https://api.mistral.ai/v1/chat/completions`), contrôle la réponse (`MyaitmiPlaceholderValidator`, `MyaitmiHtmlValidator`, `MyaitmiPsNativeValidator`), lui attribue une note (`MyaitmiQualityScorer`) et l'enregistre via `MyaitmiTranslationAdapter`.
4. Enregistrement de la traduction : passe par le service `prestashop.service.translation` ; s'il est absent, la table `_DB_PREFIX_translation` est écrite directement. Les clés des modules classiques (de la forme `<{nom}prestashop>…`) sont écrites dans le fichier `translations/{iso}.php` de ce module (`MyaitmiLegacyModuleCatalogue`).
5. Bulk : `MyaitmiBulkJobFactory` crée la tâche et ses lignes dans `myaitmi_job` et `myaitmi_job_item`. `MyaitmiJobWorker::processSlice()` traite un lot (taille issue de `BATCH_SIZE`). Il est appelé par le bouton **Process slice** (requête de l'onglet **Jobs**), par la boucle **Auto-process** dans le navigateur (AJAX `ProcessJob`) ou par le cron (`controllers/front/cron.php`).
6. Catalog : `MyaitmiCatalogTranslateService` sélectionne les enregistrements (`collect()`, 100 au maximum) et les écrit directement dans `_DB_PREFIX_product_lang`, `_DB_PREFIX_category_lang` ou `_DB_PREFIX_cms_lang`.
7. Chaque appel est consigné dans `myaitmi_request` (onglet **History**) et les erreurs dans `myaitmi_api_log`. Le coût est enregistré dans `myaitmi_usage_ledger`. Avant qu'une tâche ne modifie un texte, `MyaitmiSnapshotService` en copie l'ancienne valeur dans `myaitmi_snapshot`, ce qui permet l'annulation via **Rollback**.

### 6.2. Fichiers

| Fichier | Rôle |
|---|---|
| `myaitranslationsmistral.php` | Classe principale : installation, désinstallation, onglet de menu, hooks, chargement des assets, `translationClientConfig()`, `getContent()`. |
| `lib/updateChecker.php` | Vérification des mises à jour (onglet **Updates**, avertissement dans le back office). |
| `logo.png`, `logo.gif` | Logo dans l'en-tête des onglets et dans le menu du module. |
| `controllers/admin/AdminMyaitranslationsmistralController.php` | Tout le back office : onglets, enregistrements, actions sur les tâches, glossaire, exclusions, catalogue, CSV, réponses AJAX. |
| `controllers/front/cron.php` | Adresse cron : traite un lot de tâche et renvoie du JSON. |
| `sql/install.php`, `sql/uninstall.php` | Création et suppression des tables. |
| `src/Adapter/MyaitmiTranslationAdapterInterface.php` | Interface de lecture et d'écriture des traductions PrestaShop. |
| `src/Adapter/MyaitmiAbstractTranslationAdapter.php` | Logique commune de l'adaptateur : listes de sections, domaines et langues, enregistrement via le service ou la table `translation`, vidage du cache. |
| `src/Adapter/MyaitmiTranslationAdapter.php` | Adaptateur concret (créé par la fabrique). |
| `src/Adapter/MyaitmiTranslationAdapterFactory.php` | Crée l'adaptateur. |
| `src/Adapter/MyaitmiFilesystemCatalogueTrait.php` | Lecture des catalogues XLF des thèmes et des modules (domaines). |
| `src/Adapter/MyaitmiLegacyModuleCatalogue.php` | Modules classiques : lecture et écriture de `translations/{iso}.php`, vidage de l'OPcache après écriture. |
| `src/Admin/MyaitmiForms.php` | Construction de tous les formulaires du back office et des descriptions de champs (`desc`). |
| `src/Admin/MyaitmiSectionHelp.php` | Textes du panneau **Help** pour chaque onglet. |
| `src/Audit/MyaitmiRequestLogRepository.php` | Historique des appels, cartes, graphiques, filtres, nettoyage, rétention. |
| `src/Audit/MyaitmiApiLogRepository.php` | Journal des erreurs et avertissements de l'API, rétention. |
| `src/Audit/MyaitmiTranslationMemory.php` | Mémoire de traduction (cache) : réutilisation d'un résultat pour le même texte, la même langue, le même modèle et le même glossaire. |
| `src/Audit/MyaitmiUsageLedger.php` | Coût d'après la grille tarifaire du code, budget mensuel. |
| `src/Audit/MyaitmiSnapshotService.php` | Copies avant enregistrement et annulation d'une tâche. |
| `src/Glossary/MyaitmiGlossaryRepository.php` | Glossaire : liste, enregistrement, suppression. |
| `src/Glossary/MyaitmiExcludePatternRepository.php` | Exclusions : ajout, suppression, correspondance. |
| `src/Job/MyaitmiJobStatuses.php` | Constantes des statuts des tâches et des lignes. |
| `src/Job/MyaitmiJobRepository.php` | Tâches et lignes : lecture, changement de statut, récupération des lots, recalcul des compteurs. |
| `src/Job/MyaitmiJobWorker.php` | Traitement des lots, nouvelle tentative des erreurs, clôture de la tâche, file de relecture, e-mail de fin. |
| `src/Provider/MyaitmiTranslationProviderInterface.php` | Interface du fournisseur de traduction. |
| `src/Provider/MyaitmiMistralTranslationProvider.php` | Appels à Mistral (cURL), test de connexion, enregistrement de l'historique des appels. |
| `src/Provider/MyaitmiPromptBuilder.php` | Construction des consignes système et utilisateur (ton, voix de la marque, glossaire). |
| `src/Provider/MyaitmiProviderFactory.php` | Crée le fournisseur. |
| `src/Quality/MyaitmiPlaceholderValidator.php` | Contrôle des variables et des balises dans le texte. |
| `src/Quality/MyaitmiHtmlValidator.php` | Contrôle de la validité du HTML. |
| `src/Quality/MyaitmiPsNativeValidator.php` | Contrôle avant enregistrement dans la section **Manual**. |
| `src/Quality/MyaitmiEmailHtmlPipeline.php` | Protection du HTML des modèles d'e-mail avant envoi, et restauration après la réponse. |
| `src/Quality/MyaitmiQualityScorer.php` | Note de 0 à 100, indicateurs, décision de relecture. |
| `src/Security/MyaitmiApiKeyEncryptor.php` | Chiffrement et déchiffrement de la clé API. |
| `src/Service/MyaitmiConfigService.php` | Lecture et écriture des réglages, des modèles, du jeton cron, validation des plages de valeurs. |
| `src/Service/MyaitmiRateLimiter.php` | Limite locale d'appels par minute (fichier `var/rate_limit.json`). |
| `src/Service/MyaitmiTranslateService.php` | Circuit principal de traduction : exclusions, mémoire, appels, validation, notation, enregistrement, estimation. |
| `src/Service/MyaitmiBulkJobFactory.php` | Construction de la tâche **Bulk** et de l'estimation. |
| `src/Service/MyaitmiCatalogTranslateService.php` | Collecte et enregistrement des lignes de **Catalog**. |
| `src/Service/MyaitmiDashboardService.php` | Récapitulatif des textes manquants sur le **Dashboard**. |
| `translations/*.php` | Traductions de l'interface (un fichier par langue). |
| `views/templates/admin/configure.tpl` | Modèle de toute la page du back office et du panneau **Help**. |
| `views/templates/admin/_partials/*.tpl` | Onglets : `bulk`, `catalog`, `dashboard`, `excludes`, `glossary`, `history-stats`, `jobs`, `logs`, `manual`, `review`, `settings`. |
| `views/css/admin.css` | Styles du back office. |
| `views/js/admin.js` | Onglet **Jobs** (progression, **Auto-process**), sélection des lignes, réponses AJAX. |
| `views/js/admin-help.js` | Panneau **Help**. |
| `views/js/translations-tool.js` | Boutons et barre sur **International → Translations**. |
| `views/js/entity-fields.js` | Boutons et barre dans les formulaires produit, catégorie et CMS. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Graphiques du **Dashboard**. |
| `var/rate_limit.json` | Compteur de la limite locale d'appels pour la minute en cours. |
| `index.php` (dans chaque dossier) | Protection contre l'affichage du contenu des dossiers. |

### 6.3. Contrôleurs

**Back office : `AdminMyaitranslationsmistralController`** (classe `ModuleAdminController`, onglet sous `AdminInternational`).

- Adresse : `index.php?controller=AdminMyaitranslationsmistral&token=…`, éventuellement `&myaitmi_tab=…`.
- Valeurs autorisées pour `myaitmi_tab` : `dashboard`, `settings`, `manual`, `bulk`, `jobs`, `glossary`, `excludes`, `logs` (**History**), `review`, `catalog`, `updates`. Toute autre valeur donne `dashboard`.
- Paramètres d'entrée (GET/POST) :
  - Réglages : champs `MYAITMI_*` du formulaire, `new_mistral_model`, `delete_mistral_model`, boutons `submitMyaitranslationsmistralSettings`, `…Ping`, `…AddModel`.
  - Filtres et traduction : `section`, `theme`, `module`, `domain`, `source_locale`, `target_locale`, `only_empty`, `search`, `selected_keys[]`, `save_now`, `review_key[]`, `review_value[]`, `review_approve[]`, `review_source[]`.
  - Bulk : `target_locales[]`, `domains[]`, `policy_mode` (`fill_empty`, `overwrite`, `outdated_if_changed`), `dry_run`, `bulk_step` (`estimate`).
  - Tâches : `id_job`, `job_action` (`pause`, `resume`, `cancel`, `process`, `retry_failed`, `rollback`, `export_errors`), `filter_failed`.
  - Relecture : `review_action` (`approve`, `reject`) et `id_review`.
  - Catalogue : `entity_type` (`product`, `category`, `cms`), `id_lang_source`, `id_lang_target`, `catalog_fields_{entity}[]`, `catalog_start_id`, `only_empty`.
  - Glossaire et exclusions : `source_term`, `target_locale`, `target_term`, `do_not_translate`, `glossary_csv` (fichier), `pattern`, `pattern_type`, `delete_glossary`, `delete_exclude`.
  - Historique et cartes : `dash_locale`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_q`, `stats_preset`, `hist_id`.
- Renvoie une page HTML (`configure.tpl`) ou un fichier : `glossary.csv` (export du glossaire) ou `job-{id}-errors.csv` (erreurs de la tâche).
- Les messages de réussite et d'erreur sont transmis dans les paramètres `flash` et `flash_kind` (`info`, `success`, `warning`, `danger`).

**Actions AJAX du back office** (`index.php?controller=AdminMyaitranslationsmistral&ajax=1&action=…`) :

| `action` | Paramètres | Renvoie |
|---|---|---|
| `ProcessJob` | `id_job` | Résultat du lot : `ok`, `finished`, `paused`, `rate_limited`, `counts`, `job`. |
| `JobStatus` | `id_job` | `ok` et l'objet `job`. |
| `TranslatePageLines` | `items` (JSON), `source_locale`, `target_locale` | `translations` (id → texte), `error`. N'enregistre rien. |
| `MailSource` | `template`, `kind` (`html`/`txt`), `module`, `theme` | Le fichier source de l'e-mail. |
| `ListDomains` | `section`, `locale`, `theme`, `module` | La liste `domains`. |
| `HistoryDetail` | `hist_id` | Détails de l'appel. |

**Front : `MyaitranslationsmistralCronModuleFrontController`** (`ajax = true`, `ssl = true`).

- Adresse : `index.php?fc=module&module=myaitranslationsmistral&controller=cron&token=…`, éventuellement `&id_job=N`.
- `token` est obligatoire et comparé à `MYAITMI_CRON_TOKEN` avec `hash_equals()`. Un mauvais jeton renvoie le code 403 et le JSON `{"ok":false,"error":"Forbidden"}`.
- Avec `id_job` : traite un lot de cette tâche.
- Sans `id_job` : prend la première tâche au statut `pending` ou `running` parmi les 20 dernières. S'il n'y en a aucune, la réponse est `{"ok":true,"message":"No pending jobs"}`.

### 6.4. Hooks

Enregistrés lors de l'installation :

- `displayBackOfficeHeader` → `hookDisplayBackOfficeHeader()` : remplace le nom technique de l'onglet par son libellé (`renameTabIfTechnical()`) et charge les assets du back office (`loadBoAssets()`).
- `actionAdminControllerSetMedia` → `hookActionAdminControllerSetMedia()` : charge les assets (`loadBoAssets()`).

Assets chargés par `loadBoAssets()` :

- Sur l'onglet du module : `admin.css`, `admin.js`, `admin-help.js`, et sur l'onglet **Dashboard**, en plus, `chart.min.js` et `history-charts.js`. `Media::addJsDef` avec `aitHelpLabels`.
- Sur la page **International → Translations** (`AdminTranslations` ou l'adresse `/international/translations`), lorsque les boutons de cette page sont activés : `admin.css` et `translations-tool.js`.
- Sur les autres pages du back office (formulaires de produits, de catégories, de CMS), lorsque les boutons des formulaires sont activés : `admin.css` et `entity-fields.js`.
- Données pour le JS : `Media::addJsDef(['myaitmiTr' => …])` avec la liste des langues, les locales, les indicateurs des boutons et les libellés (`translationClientConfig()`).

Le module n'expose aucun hook propre (pas de `Hook::exec`).

### 6.5. Surcharges

Le module ne surcharge aucune classe ni aucun contrôleur de PrestaShop. Il n'existe pas de dossier `override`.

### 6.6. Base de données

Tables créées dans `sql/install.php` (`_DB_PREFIX_` est le préfixe de la boutique, `ps_` par défaut). Toutes utilisent le moteur `_MYSQL_ENGINE_` et `utf8mb4_unicode_ci`.

| Table | Contenu |
|---|---|
| `myaitmi_glossary` | `id_myaitmi_glossary`, `id_shop`, `source_term`, `target_locale`, `target_term`, `do_not_translate`, `date_add`, `date_upd`. Clé `idx_shop_locale` (`id_shop`, `target_locale`). Lecture : `id_shop` IN (0, boutique). |
| `myaitmi_exclude_pattern` | `id_myaitmi_exclude_pattern`, `pattern` (VARCHAR 512), `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled` (toujours 1 à l'ajout), `date_add`. |
| `myaitmi_job` | `id_myaitmi_job`, `uuid` (unique), `status`, `source_locale`, `target_locales`, `scope_json`, `policy_json`, `dry_run`, `items_total`, `items_done`, `items_failed`, `items_skipped`, `tokens_prompt`, `tokens_completion`, `cost_usd_estimate`, `cost_usd_actual`, `id_employee`, `error_summary`, `started_at`, `finished_at`, `date_add`, `date_upd`. Clé `idx_status`. |
| `myaitmi_job_item` | `id_myaitmi_job_item`, `id_myaitmi_job`, `domain`, `translation_key`, `theme`, `target_locale`, `source_text`, `previous_translation`, `new_translation`, `status`, `skip_reason`, `error_message`, `tokens_used`, `source_hash`, `validated_ok`, `validation_warnings`, `date_add`, `date_upd`. Clé `idx_job_status`. Un lot correspond à une seule langue cible. |
| `myaitmi_memory` | Mémoire de traduction : `memory_hash` (unique), `source_text`, `target_locale`, `translation`, `model`, `hit_count`. |
| `myaitmi_usage_ledger` | `usage_date`, `id_myaitmi_job`, `model`, `tokens_prompt`, `tokens_completion`, `cost_usd`, `date_add`. La somme mensuelle sert à calculer le budget. |
| `myaitmi_snapshot` | Copie avant enregistrement : `id_myaitmi_job`, `id_myaitmi_job_item`, `locale`, `domain`, `translation_key`, `theme`, `value_before`. |
| `myaitmi_api_log` | Journal des erreurs et avertissements : `id_myaitmi_job`, `level`, `provider`, `http_code`, `message`, `context_json`, `date_add`. Rétention selon `MYAITMI_LOG_RETENTION_DAYS`. |
| `myaitmi_review` | File de relecture : `id_myaitmi_job_item`, `status` (`needs_review`, `approved`, `rejected`), `quality_score`, `flags_json`, `id_employee`, `date_add`, `date_upd`. |
| `myaitmi_catalog_item` | Créée à l'installation et supprimée à la désinstallation. Le code du module n'y écrit pas ; **Catalog** écrit directement dans les tables de langues de la boutique. |
| `myaitmi_request` | Historique des appels : `request_type` (`translate`, `manual`, `page`, `job`, `catalog`, `ping`, `blocked`), `status`, `model`, `source_locale`, `target_locale`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `cost_usd`, `id_employee`, `id_myaitmi_job`, `item_count`, `prompt`, `reply`, `error_message`, `date_add`. `ensure()` crée aussi la table lors de la première écriture ou de l'ouverture de **History**, si elle n'existe pas. |

La désinstallation supprime les 11 tables de la liste ci-dessus. Les tables de traductions de PrestaShop (`_DB_PREFIX_translation`) et les tables de langues des produits, des catégories et des CMS ne sont pas supprimées.

### 6.7. Clés et traductions

**Clés `Configuration`** (préfixe `MYAITMI_`), valeurs par défaut issues de `installDefaults()` :

| Clé | Par défaut | Remarques |
|---|---|---|
| `API_KEY_ENC` | `''` | Clé API chiffrée. Lecture via `MyaitmiConfigService::getApiKey()`. |
| `MODEL` | `mistral-small-latest` | Modèle actif. |
| `EXTRA_MODELS` | `''` | Identifiants de modèles ajoutés à la main, un par ligne. |
| `PROVIDER` | `mistral` | Toujours `mistral` après l'enregistrement du formulaire. |
| `TONE` | `formal` | `formal`, `casual` ou `brand`. |
| `CUSTOM_VOICE` | `''` | Texte de **Brand voice**. |
| `BATCH_SIZE` | `25` | Plage 1–100. |
| `MONTHLY_BUDGET` | `0` | USD ; 0 = sans plafond. |
| `SOURCE_LOCALE` | `''` | Vide = la langue est donnée par l'écran. |
| `TEMPERATURE` | `0.2` | Plage 0–1. |
| `DRY_RUN_SAMPLE` | `10` | Plage 1–50. |
| `RATE_LIMIT_PER_MIN` | `60` | 0 désactive la limite locale. |
| `LOG_RETENTION_DAYS` | `30` | Minimum 1. |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` | Envoi d'un e-mail à la fin d'une tâche (modèle `contact`). |
| `NOTIFY_EMAIL` | `''` | Adresse du destinataire. Si elle est vide, `PS_SHOP_EMAIL` est utilisé. |
| `PERM_ALLOW_PUBLISH` | `1` | Enregistrement dans la boutique. |
| `ENTITY_FIELD_BUTTONS`, `ENTITY_BULK` | `1` | Boutons et barre dans les formulaires de la boutique. |
| `TR_FIELD_BUTTONS`, `TR_BULK` | `1` | Boutons et barre sur la page des traductions. |
| `MAX_TOKENS` | `0` | 0 = limite par défaut du fournisseur. |
| `CRON_TOKEN` | hexadécimal aléatoire de 32 caractères | Jeton de l'adresse cron. Généré aussi à la première lecture s'il est absent. |

Clés supprimées lors de l'enregistrement du formulaire ou de la désinstallation : `DEEPL_API_KEY` et `CLAUDE_API_KEY` (restes des versions précédentes). Les clés de vérification des mises à jour (`mypresta_updates`, `update_{nom}`, `updatev_{nom}`) ne sont pas supprimées.

**Traductions de l'interface.** Chaque langue correspond à `translations/{iso}.php` (par exemple `pl.php`, `de.php`, `fr.php`). Le fichier `en.php` est la source des libellés. Les libellés passent par `$this->l()` ou par les domaines `myaitmiforms` et `sectionhelp` (descriptions des champs et panneau **Help**). Les libellés des modèles s'écrivent `{l s='…' mod='myaitranslationsmistral'}`. Les libellés transmis au JS (`labels` dans `translationClientConfig()` et `aitHelpLabels`) passent eux aussi par `$this->l()`.

Pour ajouter une langue : copiez `translations/en.php` vers `translations/{iso}.php`, traduisez les valeurs et conservez les identifiants des clés.

### 6.8. Extension

- **Thème de la boutique :** le module ne génère rien dans le thème ; il n'y a donc aucun modèle à surcharger.
- **Fournisseur de traduction :** un nouveau fournisseur demande une classe conforme à `MyaitmiTranslationProviderInterface` et une modification de `MyaitmiProviderFactory`. Pour l'instant, la fabrique ne renvoie que Mistral.
- **Adaptateur de catalogue :** l'interface `MyaitmiTranslationAdapterInterface` et la fabrique `MyaitmiTranslationAdapterFactory`.
- **Grille tarifaire :** les tarifs au million de tokens sont définis dans `MyaitmiUsageLedger::estimateCost()`. Si Mistral change ses prix, il faut les mettre à jour dans le code.
- **Limite locale :** le fichier `var/rate_limit.json` est créé dans le dossier du module.

## 7. Aide

Page du module : https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-mistral.html

Si vous avez besoin d'aide au sujet du module :

1. Connectez-vous à votre compte client sur mypresta.eu.
2. Rendez-vous sur la page de contact et choisissez le sujet **Support for paid modules**. Le formulaire indique que la connexion est obligatoire pour les modules payants.
3. Une fois connecté, sélectionnez ce module dans votre historique d'achats.
