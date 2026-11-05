---
title: "AI Translations with Claude - documentation et manuel d'utilisation"
description: "Ce manuel explique la configuration et le dépannage pour les boutiques qui utilisent déjà le module AI Translations with Claude."
sidebar:
  label: "AI Translations with Claude - documentation et manuel d'utilisation"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module AI Translations with Claude sur MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-claude.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ai-artificial-intelligence/ai-translations-with-claude/)
>
> ---


## 1. Prérequis

Le module fonctionne sur PrestaShop 1.7.0.0 et les versions suivantes, y compris PrestaShop 8 et 9.

- **PrestaShop :** 1.7.0.0 ou plus récent.
- **PHP :** 5.6 ou plus récent.
- **Extensions PHP :** cURL, OpenSSL, SimpleXML et mbstring.
- **Autres modules :** ce module n'exige aucun autre module.
- **Hors de la boutique :** un compte Anthropic et une clé API, à créer sur https://console.anthropic.com/settings/keys. Le serveur de la boutique doit pouvoir joindre `https://api.anthropic.com/v1/messages`.
- **Facultatif :** une tâche planifiée sur le serveur qui appelle l'adresse cron indiquée dans **Settings**. Sans elle, vous traitez les travaux vous-même dans **Jobs**.
- **Grands catalogues :** un domaine de plusieurs milliers de chaînes représente de nombreux appels API. Le travail est découpé en tranches de la taille de **Batch size**. Avant de commencer, lancez **Estimate** dans **Bulk** pour voir l'estimation.
- La boutique doit avoir au moins deux langues. Avec une seule langue, le back-office affiche **The shop needs at least two languages.** et il n'y a rien à traduire.

## 2. Installation

1. Ouvrez **Modules**, puis **Module Manager**. Choisissez **Upload a module**, envoyez le fichier ZIP et cliquez sur **Install** à côté de **AI Translations with Claude**.
2. Après l'installation, **AI Translations with Claude** apparaît dans le menu **International**.
3. L'installation ne vide pas le cache de la boutique. Le module vide le cache lorsqu'il enregistre une traduction.

Ouvrez ensuite **AI Translations with Claude**, allez dans **Settings** et collez votre clé Claude. Tant qu'aucune clé n'est enregistrée, chaque page du module affiche **No Claude API key.** avec un lien **Open Settings**.

**Désinstallation.** Dans **Module Manager**, cliquez sur **Uninstall** et confirmez **Delete this module and its data (jobs, glossary, cache)?**

- L'entrée de menu disparaît. Les travaux, le glossaire, les motifs d'exclusion, l'historique des appels, la file **Review**, les copies de restauration, le journal des coûts et les réglages du module (clé API comprise) sont supprimés.
- Les textes que le module a déjà écrits dans la boutique restent : traductions du catalogue et fichiers de traduction des modules classiques écrits par ce module. Votre choix concernant la vérification des mises à jour reste aussi en place.
- Une nouvelle installation ne restaure pas les travaux, le glossaire ni l'historique supprimés. Elle rétablit les valeurs par défaut et crée une nouvelle adresse cron.

## 3. Configuration et utilisation courante

Tout le module tient sur une seule page : **International**, puis **AI Translations with Claude**. Les onglets sont **Dashboard**, **Manual**, **Bulk**, **Jobs**, **Review**, **Catalog**, **Glossary**, **Excludes**, **History** et **Settings**. **Updates** se trouve à l'extrémité de la barre. **Help** ouvre un panneau d'aide pour l'onglet affiché.

Les noms de boutons et de champs de ce manuel sont ceux du back-office en anglais. Dans une autre langue de back-office, vous verrez la traduction du même élément.

**Du premier clic à la traduction enregistrée**

Le travail est lancé par un employé dans le back-office. Le client ne le déclenche jamais.

1. **Settings.** Collez la clé Claude, choisissez le modèle et la langue source, cliquez sur **Test connection**, puis sur **Save**. Sans clé, aucun outil n'envoie de texte à Claude.
2. **Choisissez votre mode de travail.**
   - Quelques chaînes, ou un domaine, avec une vérification avant l'enregistrement : **Manual** (3.3).
   - Un grand domaine, un thème ou un module : **Bulk**, puis le travail dans **Jobs** (3.4 et 3.5).
   - Champs produit, catégorie et CMS : **Catalog**, jusqu'à 100 fiches à la fois (3.7).
   - Champs isolés dans **International → Translations** (3.12) et dans les formulaires produit, catégorie et CMS (3.13).
3. **Contrôle qualité.** Chaque chaîne traduite est vérifiée : espaces réservés et HTML. Une chaîne qui échoue à cette vérification n'est pas enregistrée. Vont dans **Review** les chaînes notées sous 70, celles qui dépassent deux fois et demie la longueur de la source, et celles qui contiennent encore des mots anglais comme *the*, *and*, *with*, *your* ou *please*.
4. **Enregistrement.**
   - **Manual :** **Translate selected (review)** n'enregistre rien tant que vous n'avez pas cliqué sur **Save approved**. **Save now (skip review)** écrit immédiatement les lignes valides.
   - **Bulk :** le travail attend dans **Jobs**. Il n'écrit qu'après **Process slice**, **Auto-process** ou un appel à l'adresse cron. Un travail avec **Dry-run job** activé n'écrit rien.
   - **Catalog :** les lignes valides sont écrites immédiatement dans la langue cible.
   - **International → Translations** et les formulaires de la boutique : les boutons remplissent seulement les champs. Le bouton **Save** de PrestaShop les enregistre.
   - Avec **Allow publish / save** désactivé, **Manual**, **Bulk** et **Catalog** n'écrivent rien dans la boutique.
5. **Fin du travail.** Dans **Jobs**, le statut passe à **completed** ou **completed_with_errors**. Les lignes de **Review** disparaissent de la liste après **Approve** ou **Reject**. **Catalog** indique combien de lignes ont été enregistrées et combien ont échoué.

### 3.1. Configuration du module

Ouvrez **Modules**, puis **Module Manager**, trouvez **AI Translations with Claude** et cliquez sur **Configure**. **Dashboard** s'ouvre. Passez à **Settings**.

**Save** et **Test connection** se trouvent en bas du formulaire. Enregistrer ce formulaire ne lance aucune traduction et ne modifie pas les traductions déjà enregistrées dans la boutique.

![Réglages, back-office en anglais. Haut du formulaire : Claude API key, Model, Add a Claude model, Tone et Source locale.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-settings.webp)

**Connexion**

| Champ | À l'installation | Ce que ça fait |
|---|---|---|
| **Claude API key** | vide | Le secret que cette boutique envoie à Claude. Collez la clé obtenue sur https://console.anthropic.com/settings/keys. Laissez le champ vide pour conserver la clé déjà enregistrée. Une nouvelle valeur remplace la clé enregistrée. Un champ vide ne supprime pas la clé. Une fois la clé enregistrée, le texte d'aide affiche **Key saved:** et la clé masquée. |
| **Model** | claude-haiku-4-5 | Le modèle Claude qui rédige les traductions. Les noms intégrés restent dans la liste : claude-haiku-4-5, claude-sonnet-4-5 et claude-opus-4-5. La traduction suivante utilise le modèle sélectionné. Si votre compte ne peut pas utiliser un modèle, l'appel échoue et l'erreur est consignée dans **History**. |
| **Add a Claude model** | vide | Saisissez l'identifiant exact de votre compte Anthropic, puis cliquez sur **Add model**. Le nouvel identifiant apparaît dans **Model** et devient le modèle actif. **Remove** ne supprime que les identifiants ajoutés ici. Les identifiants intégrés ne peuvent pas être supprimés. |

Messages : **Model added.**, **Model removed.**, **That model is already in the list. It is now the active model.**, **Enter a model id, for example claude-haiku-4-5.**, **Built-in models cannot be removed.**

**Ton et source**

| Champ | À l'installation | Ce que ça fait |
|---|---|---|
| **Tone** | Formal | Ajoute une consigne de style à chaque requête. **Formal** convient aux textes de la boutique et du back-office, **Casual** donne une voix plus légère, et **Brand** s'utilise avec **Brand voice**. Les nouvelles traductions suivent ce style. Les traductions déjà en place restent inchangées tant que vous ne les relancez pas. |
| **Brand voice** | vide | Visible lorsque **Tone** vaut **Brand**. Quelques phrases simples décrivant le ton de la boutique. Le texte est ajouté à la requête suivante. Un champ vide n'ajoute aucune consigne de voix. Les traductions déjà enregistrées ne sont pas réécrites. |
| **Source locale** | vide | La langue que le modèle considère comme l'original. Le choix vide est un tiret dans la liste : c'est alors l'écran traduit qui fournit la source. Choisissez la locale dans laquelle vos catalogues sont rédigés, en général en-US. **Manual**, **Bulk** et les icônes de **International → Translations** utilisent cette locale comme source. La langue par défaut de la boutique ne change pas. |
| **Individual field buttons — shop forms** | Yes | Un bouton à côté de chaque champ multilingue des formulaires de la boutique : produit, catégorie, CMS et les autres formulaires du back-office. Le bouton ne traduit que ce champ. **No** masque ces boutons dans toute la boutique. Les traductions enregistrées ne changent pas. |
| **Individual field checkboxes — shop forms** | Yes | Chaque champ concerné reçoit une case, et la barre ne traduit que les champs cochés. **No** masque les cases et la barre. Les boutons ci-dessus ont leur propre interrupteur. |
| **Individual field buttons — International → Translations** | Yes | Un bouton à côté de chaque champ de **International → Translations**. **No** masque ces boutons. Les formulaires de la boutique ne sont pas concernés. Un clic remplit ce champ. Le bouton **Save** de PrestaShop enregistre toujours la page. |
| **Individual field checkboxes — International → Translations** | Yes | Cases et barre sur **International → Translations**. **No** les masque. Les formulaires de la boutique ne sont pas concernés. |

![Réglages, back-office en anglais. Bas du formulaire : limites, e-mail, adresse cron, Test connection et Save.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-settings-limits.webp)

**Limites**

| Champ | À l'installation | Ce que ça fait |
|---|---|---|
| **Batch size** | 25 | Nombre de chaînes envoyées dans un appel API. Pour une première utilisation, prenez une valeur entre 10 et 25. La valeur reste entre 1 et 100. Un lot plus grand termine le travail avec moins d'appels. En cas d'échec, la nouvelle tentative porte sur un bloc plus gros. |
| **Dry-run sample** | 10 | Nombre de chaînes d'exemple affichées par **Estimate** avant un travail en masse. La valeur reste entre 1 et 50. **Estimate** n'écrit aucune traduction. |
| **Max tokens (0 = default)** | 0 | Plafond de longueur d'une réponse. 0 envoie un plafond de 4096 tokens. Indiquez un nombre si les réponses sont coupées ou si vous les voulez plus courtes. Seul l'appel suivant utilise ce plafond. Les traductions déjà enregistrées ne sont pas raccourcies. |
| **Budget USD / month** | 0 | Plafond mensuel en dollars américains, calculé à partir du journal de consommation. 0 signifie aucun plafond. Quand le journal atteint ce montant, les nouvelles traductions s'arrêtent. Le travail déjà enregistré reste en place. |
| **Rate limit / min** | 60 | Nombre d'appels API que cette boutique peut lancer en une minute. 0 désactive cette limite locale. Les appels au-delà sont ignorés et listés dans **History**. Claude peut appliquer sa propre limite. |
| **Log retention days** | 30 | Nombre de jours de lignes conservées dans **History**. Minimum 1. Les lignes plus anciennes sont supprimées. Ce nombre ne supprime ni les travaux, ni le glossaire, ni les traductions enregistrées. |
| **Temperature** | 0.2 | Liberté de reformulation du modèle. Autour de 0.2, le texte reste proche de la source. Des valeurs proches de 1 modifient davantage les phrases. La valeur enregistrée reste entre 0 et 1. Les espaces réservés et le HTML sont vérifiés ensuite de toute façon. Les modèles intégrés reçoivent cette valeur. Un identifiant de modèle que vous ajoutez et qui n'est pas un Claude Haiku, Sonnet ou Opus 4.0, 4.1, 4.5 ou 4.6 ne la reçoit pas : ce champ n'a alors aucun effet sur ce modèle. |
| **Allow publish / save** | Yes | Indique si ce module peut écrire une traduction dans PrestaShop. **No** bloque l'enregistrement dans **Manual**, dans les travaux en masse et dans **Catalog**. Les icônes de la page de traduction et des formulaires de la boutique se contentent toujours de remplir le formulaire. Le bouton **Save** de PrestaShop est distinct. |

Après **Save** :

- **Settings saved. No translation was started.** Les réglages sont enregistrés et rien n'a été traduit.
- **Settings saved. No API key is stored, so nothing can be translated until you paste one.** Collez une clé dans **Claude API key** puis cliquez de nouveau sur **Save**.

**E-mail et cron**

| Champ | À l'installation | Ce que ça fait |
|---|---|---|
| **Email notify on complete** | No | Envoie un e-mail à la fin d'un travail en masse. Le travail s'exécute dans tous les cas. Seul l'e-mail est ajouté ou ignoré. |
| **Notify email** | vide | L'adresse qui reçoit cet e-mail. Ce champ n'est utilisé que si l'interrupteur ci-dessus est activé. Enregistrer l'adresse seule n'envoie aucun message. |
| **CRON URL** | une adresse avec jeton | Adresse secrète que le serveur peut appeler pour traiter une tranche d'un travail en attente. Copiez-la dans le planificateur du serveur. Ne la publiez pas. Toute personne qui connaît l'adresse peut lancer une tranche. Ouvrir **Settings** ne lance aucun travail. |

**Test connection** vérifie la clé et le modèle avec une courte requête. Il ne traduit rien et n'enregistre rien.

- **Connection OK (N ms). No translation was started.** La connexion fonctionne.
- **Connection was not made. Nothing was translated.** suivi du motif. Vérifiez la clé et le modèle. Le détail se trouve dans **History**.

Pour démarrer : collez la clé, choisissez le modèle et la locale source, cliquez sur **Test connection**, puis sur **Save**. Laissez les valeurs numériques à leurs réglages d'installation tant qu'un travail ne pose pas de problème.

### 3.2. Dashboard

Ouvrez l'onglet **Dashboard**. Il compte les chaînes manquantes du catalogue, puis affiche la consommation de Claude sous forme de cartes, de graphiques et des dix dernières requêtes. La page ne traduit rien et ne modifie aucune chaîne.

![Dashboard, back-office en anglais. Couverture d'une locale, la ligne CRON et les filtres de l'historique.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-dashboard.webp)

**Couverture**

- **Locale :** la locale de la boutique dont on compte les chaînes manquantes.
- **Show :** redessine le tableau pour cette locale.
- Colonnes : **Section**, **Total**, **Missing**, **Done** et une barre de progression. Les sections sont **Back office**, **Themes**, **Installed modules**, **Emails** et **Others**. **Missing** est le nombre de chaînes sans traduction dans cette locale.
- Sous le tableau, **CRON** affiche la même adresse que **CRON URL** dans **Settings**.
- Un tableau vide signifie que la boutique n'a pas encore de catalogue pour cette locale. Créez-en un dans **International → Translations**.

Après **Show**, le message est **Coverage for {locale}. This page only counts strings. Nothing was translated.**

**Consommation**

- Périodes prédéfinies : **Today**, **7 days**, **30 days**, **This month**, **All time**.
- Filtres : **From**, **To**, **Model**, **Type**, **Status** (**Any**, **Success**, **Error**), **Language**, **Employee** et **Prompt or reply contains**. Cliquez sur **Filter**.
- Cartes : **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** et **Estimated cost**. Le coût estimé est un calcul local, pas une facture d'Anthropic.
- Graphiques : **Requests and errors**, **Tokens sent and received**, **Requests by model**. Sous eux, les groupes **By day**, **By model**, **By type**, **By language** et **By employee**, avec les colonnes **Group**, **Calls**, **Sent**, **Received** et **Total**. Un groupe vide affiche **No requests in this range.**
- **Latest prompts** liste dix appels. **View** ouvre le prompt et la réponse. **See all** ouvre **History** (3.10). Une liste vide affiche **No requests yet.**

Filtrer ne supprime pas l'historique et ne change aucune traduction.

Si la majeure partie d'une section manque, ouvrez **Manual** pour quelques chaînes ou **Bulk** pour un domaine entier.

### 3.3. Manual

Ouvrez **Manual**. L'onglet traduit un domaine ou un module classique, quelques dizaines de chaînes à la fois. Filtrer seul n'enregistre rien.

![Manual, back-office en anglais. Section, Source, Target, Domain, Only empty et Search.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-manual.webp)

| Champ | À l'installation | Ce que ça fait |
|---|---|---|
| **Section** | Back office | Le catalogue lu : **Back office**, **Themes**, **Installed modules**, **Emails** ou **Others**. Changer de section recharge la page et n'affiche que les champs de cette section. Claude n'est pas sollicité. |
| **Theme** | vide | Visible seulement pour **Themes**. Limite la liste à un thème. |
| **Module** | vide | Visible seulement pour **Installed modules**. Limite la liste à un module. Un module classique sans domaine charge toutes les chaînes de ce module. |
| **Domain** | vide | Le même regroupement que sur **International → Translations**. Choisissez-le et cliquez sur **Filter**. Masqué pour un module classique et pour une section sans domaine. |
| **Source** | la **Source locale** de **Settings**, ou en-US | La langue d'où sont tirées les chaînes. Choisissez une langue qui a déjà un bon texte. |
| **Target** | la première langue de la liste | La langue que vous voulez compléter. Elle doit exister dans **International → Localization → Languages**. |
| **Only empty** | Yes | N'affiche que les chaînes sans traduction. Désactivé, il affiche toutes les chaînes. Les traductions enregistrées ne sont pas supprimées. |
| **Search** | vide | Ne conserve que les chaînes source qui contiennent le mot saisi. |

Étapes :

1. Réglez **Section**, **Source** et **Target**.
2. Pour **Themes**, choisissez **Theme**. Pour **Installed modules**, choisissez **Module**.
3. Cliquez sur **Filter**. La liste **Domain** se rafraîchit. Choisissez un domaine et cliquez de nouveau sur **Filter**. Pour un module classique, ignorez le domaine : **Filter** charge toutes les chaînes du module.
4. Cochez les lignes voulues. **Check all** et **Uncheck all** sélectionnent ou vident la liste.
5. Cliquez sur **Translate selected (review)**. Un tableau **Review before save** s'ouvre, avec **Source**, **AI proposal** et **Warnings**. Décochez les lignes à écarter. Modifiez une proposition directement dans son champ si elle doit être corrigée. Cliquez sur **Save approved**.
6. Ou cochez **Save now (skip review)** avant de traduire. Les lignes valides sont alors écrites immédiatement, sans passer par le tableau de relecture.

Les colonnes de la liste de chaînes sont **Source**, **Current** et **Status** (**empty** ou **filled**).

Messages :

- **Loaded N strings. Tick the rows you want, then press Translate selected. Nothing is saved yet.**
- **Loaded N strings from the whole module. Tick the rows you want, then press Translate selected. Nothing is saved yet.** C'est la liste d'un module classique.
- **This module has no translation domain. Press Filter to load every string in the module. Nothing was sent to Claude.**
- **No strings match this filter. Nothing was sent to Claude.**
- **No strings match this filter. Turn off Only empty, or this module has no classic strings. Nothing was sent to Claude.**
- **Nothing was translated. Choose a domain, then press Filter to load the strings.**
- **Nothing was translated. Pick a theme, then press Filter.**
- **Nothing was translated. Pick a module, then press Filter.**
- **Nothing was translated. Tick at least one row.**
- **Nothing was translated. There is no Claude API key. Open Settings and paste the key.**
- **Review is ready. Nothing is saved until you press Save approved.**
- **Saved. The approved strings were written for the target language.**
- **Saved N. Only the ticked rows were written.**
- **Nothing was saved. Tick OK on the rows you want to keep.**
- **Not saved because of broken placeholders or HTML: N.** Ces lignes ont été ignorées. Corrigez les espaces réservés et les balises pour qu'ils correspondent à la source, puis enregistrez de nouveau.
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. Those rows are not in the current list. Press Filter and tick them again.**

Changer de section affiche aussi une courte ligne, par exemple **Section is Back office. Theme and module are not used.**, avec **Nothing was sent to Claude.** Le même schéma vaut pour **Themes**, **Installed modules**, **Emails** et **Others**.

### 3.4. Bulk

Ouvrez **Bulk**. L'onglet crée un seul travail pour plusieurs domaines et plusieurs langues. **Estimate** n'enregistre rien. **Start job** ajoute une ligne dans **Jobs**. Rien n'est écrit dans la boutique tant que le travail n'est pas traité et que **Allow publish / save** est activé.

![Bulk, back-office en anglais. Section, Source, Targets, Domains, Policy et Dry-run job.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-bulk.webp)

| Champ | À l'installation | Ce que ça fait |
|---|---|---|
| **Section** | Back office | Le catalogue lu par le travail. Mêmes choix que **Manual**. |
| **Theme** / **Module** | vide | Visibles seulement pour la section correspondante, comme sur **Manual**. |
| **Source** | la **Source locale** de **Settings**, ou en-US | La langue traitée comme original. Chaque langue cible est traduite à partir de celle-ci. |
| **Targets** | aucune | Une ou plusieurs langues à compléter. Maintenez Ctrl (ou Cmd sur Mac) pour en sélectionner plusieurs. Un simple clic remplace la sélection. |
| **Domains** | aucun | Domaines inclus dans le travail. Maintenez Ctrl ou Cmd. Si vous n'en choisissez aucun, le travail couvre tous les domaines de la section choisie. |
| **Policy** | Fill empty | **Fill empty** n'envoie que les chaînes sans traduction. **Overwrite all** envoie toutes les chaînes, y compris celles qui ont déjà une traduction, et peut les remplacer. **Outdated if equals source** n'envoie que les chaînes dont la traduction est identique à la source. |
| **Dry-run job** | No | Claude travaille quand même et le travail apparaît dans **Jobs**, mais les réponses ne sont pas écrites dans la boutique. |

Étapes :

1. Choisissez la section, la source, les langues cibles, les domaines et la politique.
2. Cliquez sur **Estimate**. La page affiche **Estimate**, le nombre de chaînes, une estimation des tokens, une estimation du coût et un **Sample**.
3. Si l'estimation vous convient, cliquez sur **Start job**. **Jobs** s'ouvre avec le nouveau travail.
4. Traitez-le dans **Jobs** (3.5) ou laissez l'adresse cron s'en charger.

Messages :

- **Estimate only: N strings, ~N tokens, ~$X. Nothing was sent to Claude and nothing was saved.**
- **Job #N is waiting (N strings, est. $X). It has not run yet.**
- **Nothing was started. Select at least one target language.**
- **Nothing was started. Pick a theme.**
- **Nothing was started. Pick a module.**
- **Nothing was started. There is no Claude API key. Open Settings and paste the key. No job was created.**

### 3.5. Jobs

Ouvrez **Jobs**. Chaque ligne correspond à une exécution lancée depuis **Bulk**.

![Jobs, back-office en anglais. La liste des travaux. Cette boutique n'a pas encore de travail.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-jobs.webp)

Colonnes : **#**, **Status**, **Locales** (la source, puis les langues cibles), **Progress** (fait/total), **Cost**, **Employee**, **Date** et **Open**. Une liste vide affiche **No jobs yet.**

Statuts des travaux, tels qu'ils s'affichent :

- `pending` - en attente. Il ne démarre pas tout seul.
- `running` - en cours.
- `paused` - arrêté jusqu'à ce que vous le repreniez.
- `cancelled` - arrêté. Les chaînes qui attendaient encore n'ont pas été traduites.
- `completed` - toutes les chaînes ont été traitées, sans échec.
- `completed_with_errors` - terminé, mais certaines chaînes ont échoué.
- `failed` - le travail s'est arrêté sur une erreur.

**L'écran du travail**

**Open** affiche **Job #N**, le statut, la progression (fait/total), **failed**, **skipped**, le coût, le numéro d'employé et le libellé **dry-run** si le travail est un essai. La barre de progression se met à jour seule tant que le travail est ouvert. Le tableau en dessous comporte les colonnes **ID**, **Domain**, **Locale**, **Status**, **Source**, **New** et **Error**.

Statuts des lignes : `pending`, `processing`, `done`, `failed`, `skipped` (une exclusion a correspondu, ou la chaîne était déjà traduite) et `rolled_back`.

Boutons :

- **Process slice** - traite une tranche de la taille de **Batch size**, puis s'arrête. Message : **One slice was processed. Check the rows below to see what was saved, skipped or failed.** S'il ne reste rien : **The job has no more strings waiting.**
- **Auto-process** - répète les tranches jusqu'à la fin du travail ou jusqu'à une erreur qui l'arrête. Le traitement se fait dans le navigateur : l'onglet doit rester ouvert. Le fermer arrête la boucle. Le travail reste en place et peut être terminé avec **Process slice** ou par l'adresse cron.
- **Pause** - message : **Job paused. It will not translate more strings until you resume it.**
- **Resume** - message : **Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.**
- **Retry failed** - les chaînes en échec repassent en attente, et le travail attend de nouveau. Message : **Retried N failed items.**
- **Rollback** - demande **Roll back this job?** et rétablit la traduction précédente là où le module avait conservé une copie avant la modification. Message : **Rollback: restored N translations.**
- **Error CSV** - télécharge les lignes en échec. Colonnes : id, domain, locale, source, error.
- **Failed only** - n'affiche que les lignes en échec.
- **Review queue** - ouvre **Review** (3.6).

L'écran du travail n'a pas de bouton Cancel. Pour arrêter la suite du travail, utilisez **Pause**.

**Pause automatique**

Quand Claude refuse des appels à cause d'une limite de fréquence, le travail se met en pause tout seul. La ligne d'erreur indique **Rate limit — job auto-paused. Resume later.** Attendez un peu, puis cliquez sur **Resume**. **Rate limit / min** dans **Settings** diminue le nombre d'appels lancés par la boutique en une minute.

Autres messages sur cet écran :

- **Nothing was translated.** suivi de **No Claude API key. Nothing was translated.** Collez la clé dans **Settings**.
- **Allow publish is off in Settings.** Un travail qui n'est pas un essai ne démarrera pas tant que vous n'aurez pas activé **Allow publish / save**.
- **Monthly API budget has been exhausted.** Augmentez **Budget USD / month** ou mettez 0.

### 3.6. Review

Ouvrez **Review**, ou cliquez sur **Review queue** à côté d'un travail. Le titre de la page est **Needs-review queue (quality score / flags).** La liste présente les lignes les plus récentes que le contrôle qualité n'a pas validées automatiquement, jusqu'à 100.

![Review, back-office en anglais. La file de relecture est vide.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-review.webp)

Colonnes : **ID**, **Score**, **Domain**, **Source**, **AI**, **Flags**, puis **Approve** et **Reject**. Une liste vide affiche **The queue is empty.**

Lire une ligne :

- **Score** va de 0 à 100. En dessous de 70, la ligne entre dans la file.
- **Flags :**
  - `validation_failed` - les espaces réservés ou le HTML n'ont pas passé le contrôle.
  - `warning` - une remarque de contrôle plus légère.
  - `length_explosion` - la traduction dépasse deux fois et demie la longueur de la source.
  - `too_short` - la traduction est beaucoup plus courte qu'une source longue.
  - `possible_untranslated` - des mots anglais comme *the*, *and*, *with*, *your* ou *please* subsistent dans la traduction.
- **Source** est l'original. **AI** est la proposition du modèle.

**Approve** et **Reject** ne modifient que le statut de la ligne. Le message est **Review updated.** La ligne quitte la liste. Cette action n'écrit pas le texte dans la boutique et ne change pas le reste du domaine.

Si le travail était autorisé à enregistrer, la proposition est peut-être déjà dans la boutique. Pour annuler les modifications de ce travail, utilisez **Rollback** sur le travail dans **Jobs**.

### 3.7. Catalog

Ouvrez **Catalog**. L'onglet traduit les champs produit, catégorie ou CMS stockés dans les langues de la boutique. Il ne modifie pas **International → Translations**. Un clic traite au maximum 100 fiches. Les lignes enregistrées sont écrites dans la langue cible.

![Catalog, back-office en anglais. Entity, Fields, langues, Only empty et Start after ID.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-catalog.webp)

| Champ | À l'installation | Ce que ça fait |
|---|---|---|
| **Entity** | product | Ce qui est lu : **product**, **category** ou **cms**. Changer ce choix recharge la page et n'affiche que la liste des champs de cette entité. Le changement lui-même ne traduit rien. |
| **Fields** | tous les champs de cette entité | Les textes envoyés par le lot. Maintenez Ctrl ou Cmd. Les champs non sélectionnés ne sont pas envoyés et restent tels quels. Produit : **Title**, **Short description**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. Catégorie : **Title**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. CMS : **Title**, **Meta description**, **Meta keywords**, **Content**, **Friendly URL**. Pour un produit ou une catégorie, **Title** est le nom. Pour un CMS, **Title** est le titre de la page et **Content** le contenu de la page. Laissez **Friendly URL** non sélectionné si vos liens doivent rester inchangés. |
| **Source language** | la première langue de la boutique | La langue à partir de laquelle les champs sont copiés. Cette langue n'est pas modifiée. |
| **Target language** | la première langue de la boutique | La langue qui reçoit la traduction. Elle doit être différente de la source. |
| **Only empty** | Yes | Ignore les champs qui ont déjà du texte dans la langue cible. Ne le désactivez que si vous voulez remplacer un texte existant. Activé : le texte cible existant est conservé. Désactivé : le lot peut l'écraser, si l'enregistrement est autorisé. |
| **Start after ID** | 0 | Ignore les fiches jusqu'à cet ID. 0 commence à la première fiche. Après un lot, le champ prend l'ID le plus élevé de ce lot, y compris les lignes en échec. Cliquez de nouveau sur le bouton pour continuer. Pour retenter une ligne en échec, remettez l'ID en dessous de cette fiche avant le clic suivant. |

Bouton : **Translate batch (max 100)**.

Étapes :

1. Choisissez **Entity** et cochez les champs.
2. Choisissez **Source language** et **Target language**.
3. Laissez **Only empty** activé.
4. Cliquez sur **Translate batch (max 100)**. Le message est **Catalog finished: saved N, failed M.** La page affiche aussi les compteurs **Saved** et **failed**.
5. Ouvrez une fiche dans la langue cible et vérifiez le résultat avant de désactiver **Only empty** ou de lancer le lot suivant.

Messages :

- **Nothing was translated. Select at least one field.**
- **Nothing was translated. Source and target language must be different.**
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. There is no Claude API key. Open Settings and paste the key.**
- Changer **Entity** affiche **Showing fields for {entity}. Nothing was translated.**

### 3.8. Glossary

Ouvrez **Glossary**. Le glossaire est une liste de mots et d'expressions que le modèle doit conserver tels quels ou toujours traduire de la même façon. Ajouter une ligne ne modifie pas les traductions déjà enregistrées. La traduction suivante lit cette liste.

![Glossary, back-office en anglais. Ajout d'un terme et import CSV.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-glossary.webp)

**Un terme**

| Champ | À l'installation | Ce que ça fait |
|---|---|---|
| **Source term** | vide, obligatoire | Le mot ou l'expression dans la langue source. Saisissez-le exactement comme il apparaît, avec les majuscules là où elles comptent. |
| **Target locale** | vide | Limite la ligne à une locale, par exemple pl-PL. Vide : la ligne s'applique à toutes les langues cibles. Une locale renseignée est ignorée pour les autres langues. |
| **Target term** | vide | La traduction approuvée. Ce champ ne peut rester vide que si **Do not translate** est activé. |
| **Do not translate** | No | Activé : le modèle recopie le terme sans le modifier, par exemple une marque, une référence SKU ou une balise. Désactivé : il utilise **Target term**. |

Cliquez sur **Add**. Messages : **Glossary term added. Translations already stored were not changed.** ou **Nothing was added. Type a source term.**

**Le tableau**

Colonnes : **Source**, **Locale**, **Target**, **Do not translate** (**Yes** ou **No**) et **Delete**. **Delete** ne supprime que cette ligne. Message : **Glossary term deleted.** Une liste vide affiche **No glossary terms yet.**

**CSV**

- Choisissez **CSV file** et cliquez sur **Import CSV**. Message : **Imported N rows.** Si le fichier manque : **CSV file is missing.** S'il ne peut pas être lu : **Cannot open the CSV file.**
- La première ligne est un en-tête : `source_term`, `target_locale`, `target_term`, `do_not_translate`. Cette ligne est toujours ignorée. Les lignes qui ont moins de trois colonnes sont ignorées. Dans la quatrième colonne, une valeur vide ou 0 signifie **No**. Toute autre valeur signifie **Yes**.
- L'import ajoute les lignes du fichier. Il ne vérifie pas si le terme existe déjà : importer deux fois le même fichier crée des doublons.
- **Export CSV** télécharge la liste actuelle sous le nom `glossary.csv`. Il n'a pas besoin de fichier d'entrée et ne modifie pas la liste.

Utilisez des termes courts et précis. Un terme trop général est imposé à chaque apparition.

### 3.9. Excludes

Ouvrez **Excludes**. Une exclusion est un motif de texte source que le module n'envoie pas à Claude. Le texte reste inchangé dans la boutique. Le motif s'applique dans **Manual**, **Bulk**, **Catalog** et les pages de traduction.

![Excludes, back-office en anglais. Pattern, Type et la liste vide.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-excludes.webp)

| Champ | À l'installation | Ce que ça fait |
|---|---|---|
| **Pattern** | vide, obligatoire | Le texte comparé à chaque chaîne source. La manière de comparer dépend de **Type**. |
| **Type** | exact | **exact** correspond à toute la chaîne. **prefix** correspond au début. **contains** correspond à un fragment situé n'importe où. **regex** est une expression régulière PHP, appliquée telle que vous l'écrivez. Une expression invalide ne correspond à rien. Commencez par un motif court et vérifiez ce qui a été ignoré. Un mauvais type peut ignorer trop de chaînes, ou aucune. |

Cliquez sur **Add**. Message : **Exclude pattern added. Matching strings will be skipped on the next run. Nothing was translated now.** Motif vide : **Nothing was added. Type a pattern.**

Colonnes : **Pattern**, **Type**, **On** et **Delete**. **On** affiche 1 quand le motif est actif. Cet écran n'a pas d'interrupteur pour désactiver un motif. Pour cesser de l'utiliser, cliquez sur **Delete**, puis ajoutez-le de nouveau si vous en avez encore besoin. **Delete** ne supprime que ce motif. Les traductions existantes ne sont pas supprimées. Message : **Pattern deleted.** Une liste vide affiche **No patterns yet.**

Utilisez les exclusions pour un texte qui doit rester dans la langue source, comme une raison sociale ou un jeton technique. Pour un terme qui doit toujours être traduit d'une seule façon, utilisez **Glossary**.

### 3.10. History

Ouvrez **History**, ou cliquez sur **See all** dans **Dashboard**.

![History, back-office en anglais. La liste des appels et Clear history.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-history.webp)

**History** est la liste complète des appels à Claude enregistrés : exécutions manuelles, page de traduction, travaux en masse, lots du catalogue et test de connexion. Chaque ligne conserve le prompt, la réponse, le modèle, les langues, le nombre de tokens et la durée de l'appel. Les cartes et les graphiques se trouvent dans **Dashboard**. Ouvrir cette page n'envoie aucune nouvelle requête et ne modifie aucune traduction.

Les filtres et les graphiques restent dans **Dashboard**. Cette page n'est que la liste.

Colonnes : **ID**, **When**, **Status**, **Type**, **Model**, **Languages**, **Sent**, **Received**, **Total**, **Time** et **Prompt**. Types : **Manual**, **Translation page**, **Bulk job**, **Catalog**, **Connection test**, **Translate** et **Not sent** (l'appel n'a pas été envoyé, par exemple à cause de la limite locale ou du budget). Une ligne **Bulk job** affiche le numéro du travail.

- **View** ouvre le prompt et la réponse, avec **HTTP**, **Sent**, **Received** et **Total**. En cas d'erreur, la réponse est le texte de l'erreur. **Back to the list** revient au tableau. Si la ligne n'existe plus : **This history row no longer exists.**
- Une erreur d'accès signifie que la clé de **Settings** est incorrecte, ou que le compte ne peut pas utiliser le modèle choisi.
- **Previous**, **Next** et **Page** parcourent la liste.
- **Clear history** demande **Clear the stored history? Saved translations stay.** Après l'action : **History cleared. Saved translations were not changed.** L'aide du bouton indique **Clear history deletes these rows only. Saved translations stay.**

Une liste vide affiche **No requests yet.**

Si les traductions s'arrêtent brusquement, ouvrez ici la ligne d'erreur la plus récente avant de modifier le glossaire.

### 3.11. Updates

Ouvrez **Updates** à l'extrémité droite de la barre du module. Le titre du formulaire est **MyPresta Updates**.

![Updates, back-office en anglais. Manual Check, Automatic Notifications et Product Page.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-updates.webp)

- **Manual Check** contient **Check Now**, qui vérifie la version immédiatement.
- **Automatic Notifications** est à **Enabled** ou **Disabled**. **Enabled** est la valeur tant que vous n'avez jamais enregistré de choix. Lorsqu'il est activé, le module vérifie si MyPresta propose une version plus récente et peut afficher un avertissement dans le back-office.
- **Product Page** est un lien vers la page de contact utilisée par ce module.
- **Save** enregistre votre choix. Message : **Update settings saved.**

Après **Check Now** : **New version available!** ou **Module is up to date!**

### 3.12. Boutons sur International → Translations

Ouvrez **International → Translations**. Les boutons des champs apparaissent quand **Individual field buttons — International → Translations** est activé. Les cases et la barre apparaissent quand **Individual field checkboxes — International → Translations** est activé.

Ce que vous voyez :

- Un bouton **Translate** sur chaque champ de texte.
- Une case sur chaque champ, lorsque les cases sont activées.
- Une barre intitulée **Claude translations**, avec **Source** (en-US, ou la **Source locale** de **Settings**), **Target**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected** et l'indication **Fills the fields. Save with the PrestaShop button.** **Translate empty in this section** remplit les champs vides de la section en cours.

Étapes :

1. Choisissez **Target**.
2. Cochez les champs ou cliquez sur **Check empty**.
3. Cliquez sur **Translate selected** ou **Translate empty**.
4. Attendez que la barre affiche **Done**. Pendant le traitement, le statut indique **Translating…** avec un compteur. Si vous n'avez rien coché, la barre affiche **Tick at least one field.**
5. Vérifiez les champs remplis, puis enregistrez la page avec le bouton **Save** de PrestaShop.

Les boutons se contentent de remplir les champs. Sans le bouton **Save** de PrestaShop, le texte n'entre pas dans la boutique. Avec **Allow publish / save** désactivé, les champs sont tout de même remplis, et c'est le bouton **Save** de PrestaShop qui enregistre la page.

Messages :

- **Target is not a language from this shop.**
- **Fill the source language field first.**
- **The source language field is not on this page.**
- **The source language mail file was not found.** Pour **Emails**, le texte source provient du fichier de modèle d'e-mail, et non d'un champ de la page. Choisissez une autre **Source locale** pour laquelle ces fichiers d'e-mail existent.

### 3.13. Boutons sur les formulaires produit, catégorie et CMS

Ouvrez un produit, une catégorie, une page CMS ou un autre formulaire de la boutique comportant des champs multilingues. Les boutons apparaissent quand **Individual field buttons — shop forms** est activé. Les cases et la barre apparaissent quand **Individual field checkboxes — shop forms** est activé.

Ce que vous voyez :

- Un bouton **Translate** sur chaque champ multilingue.
- Une case pour la barre.
- Une barre intitulée **Claude translations**, avec **Translate from** et **to**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected** et l'indication **Fills the fields. Save with the PrestaShop button.**

Étapes :

1. Remplissez le champ dans la langue source. S'il est vide, la barre affiche **Fill the source language field first.**
2. Choisissez la langue cible sur la barre.
3. Cliquez sur le bouton d'un champ, ou cochez des champs puis cliquez sur **Translate selected**. **Translate empty** remplit les champs vides.
4. Cliquez sur **Save** dans le formulaire PrestaShop. Sans cela, le texte n'est pas enregistré.

Le bouton ne remplit que le champ du formulaire. Les champs que vous ne cochez pas restent inchangés.

## 4. Vitrine

Le module n'ajoute rien à la page que voit le client. Il n'y a ni bloc, ni bouton, ni message sur la boutique : le thème n'a donc rien à afficher pour ce module.

La seule adresse en dehors du back-office est l'adresse cron. Elle sert à une tâche planifiée sur le serveur. Elle n'est pas destinée aux clients.

- Copiez-la depuis **Settings**, champ **CRON URL**, ou depuis la ligne **CRON** du **Dashboard**.
- Collez-la dans le planificateur du serveur, par exemple toutes les quelques minutes. Chaque appel traite une tranche d'un travail en attente.
- Utilisez l'adresse `https://` lorsque le SSL est activé sur la boutique.

| Ce que vous voyez en ouvrant l'adresse | Que faire |
|---|---|
| **Forbidden** | L'adresse est incomplète ou a été modifiée. Copiez-la de nouveau depuis **Settings**. |
| **No pending jobs** | Aucun travail n'est en `pending` ou `running`. Créez-en un dans **Bulk**, ou reprenez un travail en pause dans **Jobs**. |
| Un résultat JSON avec `ok`, `finished` et `counts` | Une tranche a été traitée. Vérifiez la progression dans **Jobs**. |

L'adresse cron ne traite que les travaux en `pending` et `running`. Un travail `paused` doit être repris dans **Jobs**.

## 5. Problèmes

| Ce que vous voyez | Cause | Que faire |
|---|---|---|
| **No Claude API key.** sur chaque page du module | Aucune clé n'est enregistrée. | Ouvrez **Settings**, collez la clé dans **Claude API key** et cliquez sur **Save**. |
| **Settings saved. No API key is stored, so nothing can be translated until you paste one.** | Les réglages ont été enregistrés sans clé. | Collez la clé et cliquez sur **Save**. |
| **Connection was not made. Nothing was translated.** après **Test connection** | Clé incorrecte, pas de connexion vers Anthropic, ou modèle que le compte ne peut pas utiliser. | Vérifiez la clé, choisissez un autre **Model** ou ajoutez le bon identifiant dans **Add a Claude model**. Lisez la ligne dans **History**. |
| Erreurs d'accès dans **History** | La clé est incorrecte, ou le compte ne peut pas utiliser le modèle choisi. | Corrigez la clé ou choisissez un modèle que le compte peut appeler. |
| **Nothing was started. There is no Claude API key.** dans **Bulk** | Pas de clé. | Collez la clé dans **Settings**, puis relancez **Estimate** et **Start job**. |
| Un travail reste en `pending` | Un travail ne démarre pas tout seul. | Cliquez sur **Process slice** ou **Auto-process** dans **Jobs**, ou configurez l'adresse cron (section 4). |
| Un travail est `paused` avec **Rate limit — job auto-paused. Resume later.** | Claude a refusé des appels à cause d'une limite de fréquence. | Attendez quelques minutes, puis cliquez sur **Resume**. Baissez **Batch size** ou **Rate limit / min**. |
| **Monthly API budget has been exhausted.** | **Budget USD / month** a été atteint. | Augmentez le montant ou mettez 0. Un nouveau mois repart de zéro. |
| **Nothing was saved. Turn on Allow publish in Settings.** | **Allow publish / save** est désactivé. | Activez **Allow publish / save**. |
| **Not saved because of broken placeholders or HTML: N.** dans **Manual** | La traduction a modifié les espaces réservés ou les balises HTML. | Corrigez la ligne dans **Review before save** pour que les espaces réservés et les balises correspondent à la source, puis cliquez sur **Save approved**. |
| Un travail se termine en `completed_with_errors` | Certaines chaînes ont échoué. | Ouvrez le travail, cliquez sur **Failed only**, téléchargez **Error CSV**, puis cliquez sur **Retry failed**. |
| Des lignes de **Review** ont un **Score** bas | Le contrôle qualité les a placées dans la file. | Lisez **Source** et **AI**, puis cliquez sur **Approve** ou **Reject**. Si un mauvais texte a déjà été enregistré, utilisez **Rollback** sur le travail. |
| La traduction a été enregistrée, mais la boutique affiche encore l'ancien texte | Le cache de la page ne s'est pas actualisé. Le module vide le cache lorsqu'il enregistre une traduction du catalogue, une tranche de travail en masse ou un rollback. | Videz le cache dans le back-office PrestaShop. |
| Une exclusion ne saute pas la chaîne | Mauvais **Type**, ou **regex** qui ne correspond à rien. | Dans **Excludes**, supprimez le motif et ajoutez-en un plus court avec le bon **Type**. |
| Un nouveau terme du glossaire ne modifie pas les traductions enregistrées | Le glossaire est lu lors de la traduction suivante. Les textes enregistrés restent. | Relancez ces chaînes dans **Bulk** avec **Overwrite all**, après avoir consulté **Estimate**. |
| **The source language mail file was not found.** | La source choisie n'a pas de fichier d'e-mail. | Choisissez une autre **Source locale** dans **Settings**, ou une autre **Source** sur la page de traduction, qui possède les fichiers d'e-mail. |
| **No strings match this filter. Nothing was sent to Claude.** | Le filtre ne correspond à rien. | Désactivez **Only empty**, videz **Search** ou choisissez un autre domaine. |
| **Nothing was translated. Tick at least one row.** | Aucune ligne n'était cochée. | Cochez des lignes et cliquez sur **Translate selected (review)**. |
| **Nothing was translated. Source and target language must be different.** dans **Catalog** | La source et la cible sont la même langue. | Choisissez une autre **Target language**. |
| **Catalog finished** a fait passer **Start after ID** au-delà des lignes en échec | Le champ prend l'ID le plus élevé du lot, y compris les lignes en échec. | Placez **Start after ID** en dessous de la fiche en échec et relancez le lot. |
| La couverture du Dashboard est vide | La boutique n'a pas encore de catalogue pour cette locale. | Créez-en un dans **International → Translations**, puis revenez au **Dashboard**. |
| **History** affiche **Not sent** | La limite locale ou le budget a arrêté l'appel avant l'envoi. | Vérifiez **Rate limit / min** et **Budget USD / month** dans **Settings**. |
| **The shop needs at least two languages.** | La boutique n'a qu'une langue. | Ajoutez une langue dans **International → Localization → Languages**. |

## 6. Pour les développeurs

### 6.1. Vue d'ensemble

- Classe principale : `myaitranslationsclaude`, fichier `myaitranslationsclaude.php`.
- Version : 1.2.0.
- Nom technique : `myaitranslationsclaude`. Nom dans la liste des modules : **AI Translations with Claude**.
- Auteur : MyPresta.eu. Onglet du Module Manager : `administration`.
- Onglet du back-office : `AdminMyaitranslationsclaude`, parent `AdminInternational`, parent de repli `IMPROVE`. Le libellé visible de l'onglet est `AI Translations with Claude`. `ensureTab()` répare un onglet manquant. `renameTabIfTechnical()` remplace un nom d'onglet qui est encore le nom technique.
- Installation : `parent::install()`, tables définies dans `sql/install.php` (`CREATE TABLE IF NOT EXISTS`), `installDefaults()` (n'écrit une clé que si elle manque), hooks `displayBackOfficeHeader` et `actionAdminControllerSetMedia`, puis l'onglet.
- Désinstallation : supprime l'onglet, exécute `sql/uninstall.php` (supprime 11 tables), `removeConfiguration()` supprime les clés `MYAITCL_*` listées, puis `parent::uninstall()`. `mypresta_updates`, `update_myaitranslationsclaude` et `updatev_myaitranslationsclaude` ne sont pas supprimées.
- Il n'y a ni `enable()` ni `disable()`.
- `getContent()` appelle `ensureTab()` et redirige vers `AdminMyaitranslationsclaude` (onglet par défaut `dashboard`).

Enchaînement :

1. Le formulaire de réglages envoie un POST à `AdminMyaitranslationsclaudeController::initContent()`.
2. `MyaitclConfigService::saveFromForm()` enregistre les `MYAITCL_*` dans `Configuration`. `MyaitclApiKeyEncryptor` chiffre la clé API en AES-256-CBC, avec une clé dérivée de `_COOKIE_KEY_`, et la stocke dans `MYAITCL_API_KEY_ENC`. Une clé envoyée vide, ou une valeur masquée, ne remplace pas la clé enregistrée.
3. Traduction : `MyaitclTranslateService::translateMessages()` construit les prompts (`MyaitclPromptBuilder`), les envoie via `MyaitclClaudeTranslationProvider` (POST cURL vers `https://api.anthropic.com/v1/messages`, en-tête `anthropic-version: 2023-06-01`), contrôle la réponse (`MyaitclPlaceholderValidator`, `MyaitclHtmlValidator`, `MyaitclPsNativeValidator`), la note (`MyaitclQualityScorer`) et l'enregistre via `MyaitclTranslationAdapter`.
4. Quand **Max tokens** vaut 0, le fournisseur envoie `max_tokens` 4096. `acceptsTemperature()` n'envoie **Temperature** que si l'identifiant du modèle correspond à `claude-(opus|sonnet|haiku)-4-(0|1|5|6)`.
5. L'enregistrement du catalogue utilise le service de traduction de PrestaShop s'il existe, sinon la table `_DB_PREFIX_translation`. Les clés des modules classiques sont écrites dans `translations/{iso}.php` du module par `MyaitclLegacyModuleCatalogue`.
6. **Bulk** : `MyaitclBulkJobFactory` insère dans `myaitcl_job` et `myaitcl_job_item`. `MyaitclJobWorker::processSlice()` traite une tranche de `BATCH_SIZE`. Elle est appelée par **Process slice**, par la boucle **Auto-process** (AJAX `ProcessJob`) et par `controllers/front/cron.php`.
7. Catalogue : `MyaitclCatalogTranslateService::collect()` lit au maximum 100 lignes. `translateAndSave()` écrit dans `_DB_PREFIX_product_lang`, `_DB_PREFIX_category_lang` ou `_DB_PREFIX_cms_lang`. Les résultats sont rapprochés par id. Après le lot, **Start after ID** prend la valeur du plus grand `id_entity` de l'ensemble collecté, y compris les lignes en échec.
8. Chaque appel est enregistré dans `myaitcl_request` (**History**). Les erreurs vont aussi dans `myaitcl_api_log`. Le coût est enregistré dans `myaitcl_usage_ledger`. `MyaitclSnapshotService` copie la valeur précédente dans `myaitcl_snapshot` pour **Rollback**. `clearTranslationCache()` appelle `Tools::clearCache()` après un enregistrement du catalogue, après une tranche qui n'est pas un essai, et après un rollback.

### 6.2. Fichiers

| Fichier | Rôle |
|---|---|
| `myaitranslationsclaude.php` | Installation, désinstallation, onglet, hooks, ressources, `translationClientConfig()`, `getContent()`. |
| `lib/updateChecker.php` | Vérification des mises à jour pour l'onglet **Updates** et l'avertissement du back-office. Classe `myaitranslationsclaudeUpdate`. |
| `logo.png`, `logo.gif` | Logo dans l'en-tête du module. |
| `controllers/admin/AdminMyaitranslationsclaudeController.php` | Tous les onglets du back-office, enregistrements, actions sur les travaux, glossaire, exclusions, catalogue, CSV, AJAX. |
| `controllers/front/cron.php` | Adresse cron. Traite une tranche et renvoie du JSON. |
| `sql/install.php`, `sql/uninstall.php` | Création et suppression des tables. |
| `src/Adapter/MyaitclTranslationAdapterInterface.php` | Interface de lecture et d'écriture des traductions PrestaShop. |
| `src/Adapter/MyaitclAbstractTranslationAdapter.php` | Sections, domaines, locales, enregistrement par le service ou la table `translation`, vidage du cache. |
| `src/Adapter/MyaitclTranslationAdapter.php` | Adaptateur concret. |
| `src/Adapter/MyaitclTranslationAdapterFactory.php` | Construit l'adaptateur. |
| `src/Adapter/MyaitclFilesystemCatalogueTrait.php` | Lit les catalogues XLF des thèmes et des modules. |
| `src/Adapter/MyaitclLegacyModuleCatalogue.php` | Modules classiques : lecture et écriture de `translations/{iso}.php`. |
| `src/Admin/MyaitclForms.php` | Formulaires du back-office et texte `desc` des champs. |
| `src/Admin/MyaitclSectionHelp.php` | Texte du panneau **Help** de chaque onglet. |
| `src/Audit/MyaitclRequestLogRepository.php` | **History** : lignes, cartes, graphiques, filtres, vidage, rétention. |
| `src/Audit/MyaitclApiLogRepository.php` | Journal des erreurs et avertissements de l'API, rétention. |
| `src/Audit/MyaitclTranslationMemory.php` | Réutilise un résultat pour le même texte, la même locale, le même modèle et le même glossaire. |
| `src/Audit/MyaitclUsageLedger.php` | Estimation du coût d'après la table de prix de ce fichier, et budget mensuel. |
| `src/Audit/MyaitclSnapshotService.php` | Copie avant une écriture, et restauration lors d'un **Rollback**. |
| `src/Glossary/MyaitclGlossaryRepository.php` | Liste du glossaire, insertion, suppression. |
| `src/Glossary/MyaitclExcludePatternRepository.php` | Insertion, suppression et correspondance des exclusions. |
| `src/Job/MyaitclJobStatuses.php` | Constantes de statut des travaux et des lignes. |
| `src/Job/MyaitclJobRepository.php` | Travaux et lignes : lecture, statut, tranche suivante, compteurs. |
| `src/Job/MyaitclJobWorker.php` | Traitement d'une tranche, nouvelle tentative, fin, file de relecture, e-mail de fin. |
| `src/Provider/MyaitclTranslationProviderInterface.php` | Interface du fournisseur. |
| `src/Provider/MyaitclClaudeTranslationProvider.php` | Appels à Claude, test de connexion, journal des requêtes. |
| `src/Provider/MyaitclPromptBuilder.php` | Prompts système et utilisateur : ton, voix de marque, glossaire. |
| `src/Provider/MyaitclProviderFactory.php` | Construit le fournisseur. |
| `src/Quality/MyaitclPlaceholderValidator.php` | Contrôle des espaces réservés et des balises. |
| `src/Quality/MyaitclHtmlValidator.php` | Contrôle HTML. |
| `src/Quality/MyaitclPsNativeValidator.php` | Contrôle avant un enregistrement depuis **Manual**. |
| `src/Quality/MyaitclEmailHtmlPipeline.php` | Protège le HTML des e-mails avant l'appel et le rétablit après la réponse. |
| `src/Quality/MyaitclQualityScorer.php` | Note de 0 à 100, flags, décision de relecture. |
| `src/Security/MyaitclApiKeyEncryptor.php` | Chiffrement et déchiffrement de la clé API. |
| `src/Service/MyaitclConfigService.php` | Lecture et enregistrement des réglages, des modèles, du jeton cron et des plages de valeurs. |
| `src/Service/MyaitclRateLimiter.php` | Limite locale par minute, fichier `var/rate_limit.json`. |
| `src/Service/MyaitclTranslateService.php` | Exclusions, mémoire, appels, validation, notation, enregistrement, estimation. |
| `src/Service/MyaitclBulkJobFactory.php` | Construit un travail **Bulk** et son estimation. |
| `src/Service/MyaitclCatalogTranslateService.php` | Collecte et enregistre les lignes **Catalog**. |
| `src/Service/MyaitclDashboardService.php` | Comptes de couverture sur **Dashboard**. |
| `translations/*.php` | Traductions de l'interface, un fichier par langue. |
| `views/templates/admin/configure.tpl` | Page du module et tiroir **Help**. |
| `views/templates/admin/_partials/*.tpl` | Onglets : `bulk`, `catalog`, `dashboard`, `excludes`, `glossary`, `history-stats`, `jobs`, `logs`, `manual`, `review`, `settings`. |
| `views/css/admin.css` | Styles du back-office. |
| `views/js/admin.js` | Progression de **Jobs** et **Auto-process**, cases des lignes, AJAX. |
| `views/js/admin-help.js` | Panneau **Help**. |
| `views/js/translations-tool.js` | Boutons et barre sur **International → Translations**. |
| `views/js/entity-fields.js` | Boutons et barre sur les formulaires produit, catégorie et CMS. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Graphiques de **Dashboard**. |
| `var/rate_limit.json` | Compteur de la limite locale par minute. |
| `index.php` dans chaque répertoire | Bloque le listage du répertoire. |

### 6.3. Contrôleurs

**Back-office : `AdminMyaitranslationsclaudeController`** (`ModuleAdminController`).

- URL : `index.php?controller=AdminMyaitranslationsclaude&token=…`, avec `&myaitcl_tab=` facultatif et les valeurs `dashboard`, `manual`, `bulk`, `jobs`, `review`, `catalog`, `glossary`, `excludes`, `logs` (le libellé de l'onglet est **History**), `settings` ou `updates`.
- Actions sur les travaux, paramètre `job_action` accompagné de `id_job` : `process`, `pause`, `resume`, `cancel`, `retry_failed`, `rollback`, `export_errors`. Le template n'affiche pas de bouton Cancel. `filter_failed=1` limite le tableau des lignes.
- Actions de relecture : `review_action=approve|reject` et `id_review`.
- Glossaire : `delete_glossary`. Exclusions : `delete_exclude`. Modèles : `delete_claude_model`, et POST `new_claude_model` avec `submitMyaitranslationsclaudeAddModel`.
- AJAX : `displayAjaxProcessJob`, `displayAjaxJobStatus`, `displayAjaxHistoryDetail`, ainsi que les points d'entrée de traduction de champ utilisés par `translations-tool.js` et `entity-fields.js`.

**Front : `MyaitranslationsclaudeCronModuleFrontController`** (`controllers/front/cron.php`).

- URL de la boutique : `module/myaitranslationsclaude/cron`.
- Le paramètre `token` doit correspondre à `MYAITCL_CRON_TOKEN` (`hash_equals`). Un jeton absent ou incorrect renvoie HTTP 403 et le JSON `{"ok":false,"error":"Forbidden"}`.
- `id_job` facultatif traite ce travail. Sans lui, le premier travail `pending` ou `running` est traité.
- Une tranche réussie renvoie du JSON avec `ok`, `finished` et `counts`. Quand aucun travail n'attend, le corps est `{"ok":true,"message":"No pending jobs"}`.
- `ssl` vaut true sur le contrôleur.

### 6.4. Hooks

Hooks enregistrés :

- `displayBackOfficeHeader` - renomme le libellé technique de l'onglet, puis charge le CSS et le JS.
- `actionAdminControllerSetMedia` - charge les mêmes ressources.

`translations-tool.js` est ajouté au contrôleur des traductions. `entity-fields.js` est ajouté aux formulaires de la boutique lorsque les interrupteurs de champs sont activés. `Media::addJsDef` publie `myaitclTr` (URL AJAX, locale source, langues et libellés de la barre).

Le module n'enregistre aucun hook propre que d'autres modules pourraient implémenter. Il n'y a ni `enable()` ni `disable()`.

### 6.5. Surcharges

Le module ne surcharge aucune classe ni aucun contrôleur de PrestaShop.

### 6.6. Base de données

| Table | Contenu |
|---|---|
| `myaitcl_glossary` | `source_term`, `target_locale`, `target_term`, `do_not_translate`, id de la boutique, dates. |
| `myaitcl_exclude_pattern` | `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`. |
| `myaitcl_job` | Une exécution en masse : locales, `scope_json`, `policy_json`, `dry_run`, compteurs, totaux de tokens, coût, employé, erreur, horodatages. |
| `myaitcl_job_item` | Une chaîne d'un travail : domaine, clé, thème, locale, source, valeur précédente, nouvelle valeur, statut, motif d'omission, erreur, tokens, validation. |
| `myaitcl_memory` | Mémoire de traduction : hash, source, locale, traduction, modèle, nombre de réutilisations. |
| `myaitcl_usage_ledger` | Lignes quotidiennes de tokens et de coût, id de travail facultatif, modèle. |
| `myaitcl_snapshot` | Valeur précédant une écriture du travail, utilisée par **Rollback**. |
| `myaitcl_api_log` | Lignes d'erreur et d'avertissement : niveau, fournisseur `claude`, code HTTP, message, contexte. |
| `myaitcl_request` | Lignes de **History** : type, statut, modèle, locales, code HTTP, durée, tokens, coût, employé, travail, prompt, réponse, erreur. |
| `myaitcl_review` | File de relecture : élément du travail, statut, note, flags, employé. |
| `myaitcl_catalog_item` | Lignes d'un lot du catalogue : entité, champ, langues, source, valeur précédente, nouvelle valeur, statut, erreur. |

La désinstallation supprime les onze tables. L'installation utilise `CREATE TABLE IF NOT EXISTS` : une réinstallation sur une base qui contient encore les tables conserve ces lignes. Une désinstallation normale les retire d'abord. Aucune colonne n'est ajoutée lors de la première visite d'une page.

### 6.7. Clés et traductions

Préfixe : `MYAITCL_`. Valeurs utilisées quand une clé manque ; ce sont aussi les valeurs écrites à l'installation :

| Clé | Valeur si absente |
|---|---|
| `API_KEY_ENC` | vide |
| `MODEL` | `claude-haiku-4-5` |
| `EXTRA_MODELS` | vide |
| `PROVIDER` | `claude` |
| `TONE` | `formal` |
| `CUSTOM_VOICE` | vide |
| `BATCH_SIZE` | `25` (ramenée à 1-100 lors de l'enregistrement) |
| `MONTHLY_BUDGET` | `0` |
| `SOURCE_LOCALE` | vide |
| `TEMPERATURE` | `0.2` (ramenée à 0-1 lors de l'enregistrement) |
| `DRY_RUN_SAMPLE` | `10` (ramenée à 1-50 lors de l'enregistrement) |
| `RATE_LIMIT_PER_MIN` | `60` |
| `LOG_RETENTION_DAYS` | `30` (minimum 1) |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` |
| `NOTIFY_EMAIL` | vide |
| `PERM_ALLOW_PUBLISH` | `1` |
| `ENTITY_FIELD_BUTTONS` | `1` |
| `ENTITY_BULK` | `1` |
| `TR_FIELD_BUTTONS` | `1` |
| `TR_BULK` | `1` |
| `MAX_TOKENS` | `0` (le fournisseur envoie alors 4096) |
| `CRON_TOKEN` | 16 octets aléatoires en hexadécimal, générés à l'installation |

`removeConfiguration()` supprime aussi les anciens noms `DEEPL_API_KEY` et `CLAUDE_API_KEY` sous le même préfixe. Elle ne supprime pas les clés de vérification des mises à jour.

Les descriptions des champs sont les chaînes `desc` de `src/Admin/MyaitclForms.php`, assemblées par `help()` à partir de l'objectif, de la manière de le régler et de son effet. L'aide des onglets se trouve dans `src/Admin/MyaitclSectionHelp.php`.

Les chaînes de l'interface passent par `$this->l()` ou `{l s=... mod='myaitranslationsclaude'}`. Pour ajouter une langue, créez `translations/{iso}.php`. Les erreurs de travail **Rate limit — job auto-paused. Resume later.**, **Allow publish is off in Settings.**, **No Claude API key. Nothing was translated.** et **Monthly API budget has been exhausted.** sont des chaînes anglaises renvoyées par `MyaitclJobWorker` et `MyaitclTranslateService`, et non des appels à `$this->l()`. Les chaînes de **Updates** utilisent le domaine de traduction `updatechecker`.

### 6.8. Extension

La vitrine n'affiche aucun template du module, donc le thème n'a rien à surcharger.

Les templates du back-office se trouvent dans `views/templates/admin/`. PrestaShop ne propose pas de surcharge par le thème pour ces templates d'administration. Modifiez les libellés via `translations/{iso}.php`. Les boutons de **International → Translations** et des formulaires de la boutique sont injectés par `views/js/translations-tool.js` et `views/js/entity-fields.js` à partir de `myaitclTr`. Aucun hook ne permet à un thème de remplacer cette barre.

## 7. Aide

Page du module : https://mypresta.eu/fr/ia-intelligence-artificielle/traductions-ia-avec-claude.html

Pour écrire au sujet de ce module, connectez-vous à votre compte client sur mypresta.eu, ouvrez le formulaire de contact et choisissez **Support for paid modules**. Le formulaire indique qu'une connexion est nécessaire pour les modules payants. Une fois connecté, choisissez ce module dans votre historique d'achats.
