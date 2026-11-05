---
title: "AI Translations with ChatGPT - documentation et manuel d'utilisation"
description: "Configuration et dépannage pour les boutiques qui ont déjà AI Translations with ChatGPT."
sidebar:
  label: "AI Translations with ChatGPT - documentation et manuel d'utilisation"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module AI Translations with ChatGPT sur MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-chatgpt.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ai-artificial-intelligence/ai-translations-with-chatgpt/)
>
> ---


## 1. Prérequis

Le module fonctionne sur PrestaShop 1.7.0.0 et les versions plus récentes, y compris PrestaShop 8 et 9.

- **PrestaShop :** 1.7.0.0 ou plus récent.
- **PHP :** 5.6 ou plus récent.
- **Extensions PHP :** cURL, OpenSSL, SimpleXML et mbstring.
- **Autres modules :** ce module n'en exige aucun autre.
- **Hors boutique :** un compte OpenAI et une clé d'API. Le serveur de la boutique doit pouvoir ouvrir `https://api.openai.com/v1/chat/completions`.
- **Facultatif :** une tâche planifiée sur le serveur qui ouvre l'adresse cron de **Settings**. Sans elle, vous traitez les travaux vous-même dans **Jobs**.
- **Grands catalogues :** un domaine de plusieurs milliers de chaînes représente de nombreux appels d'API. Le travail est découpé en tranches de la taille de **Batch size**. Lancez **Estimate** dans **Bulk** avant de commencer.
- La boutique a besoin d'au moins deux langues. Avec une seule langue, le back-office affiche **The shop needs at least two languages.** et il n'y a rien à traduire.

## 2. Installation

1. Ouvrez **Modules**, puis **Module Manager**. Choisissez **Upload a module**, envoyez le ZIP et appuyez sur **Install** pour **AI Translations with ChatGPT**.
2. Après l'installation, **AI Translations with ChatGPT** apparaît dans le menu **International**.
3. L'installation ne vide pas le cache de la boutique. Le module vide le cache lorsqu'il enregistre une traduction.

Ouvrez **AI Translations with ChatGPT**, puis **Settings**, et collez la clé ChatGPT. Tant qu'aucune clé n'est enregistrée, chaque page du module affiche **No ChatGPT API key.** et le lien **Open Settings**.

**Désinstallation.** Dans **Module Manager**, appuyez sur **Uninstall** et confirmez **Delete this module and its data (jobs, glossary, cache)?**

- L'entrée de menu disparaît. Les travaux, le glossaire, les motifs d'exclusion, l'historique des appels, la file **Review**, les copies de retour arrière, le registre des coûts et les réglages du module (y compris la clé d'API) sont supprimés.
- Le texte que le module a déjà écrit dans la boutique reste : traductions de catalogue, et fichiers de traduction des modules classiques que ce module a écrits. Le choix du contrôle de mise à jour reste aussi.
- Une nouvelle installation ne ramène pas les travaux, le glossaire ni l'historique supprimés. Elle pose les valeurs par défaut et crée une nouvelle adresse cron.

## 3. Configuration et travail quotidien

Tout le module tient sur une page : **International**, puis **AI Translations with ChatGPT**. Les onglets sont **Dashboard**, **Manual**, **Bulk**, **Jobs**, **Review**, **Catalog**, **Glossary**, **Excludes**, **History** et **Settings**. **Updates** est au bout de la barre. **Help** ouvre un panneau pour l'onglet en cours.

Les noms de boutons et de champs de ce manuel sont ceux du back-office anglais. Dans une autre langue du panneau, vous voyez la traduction du même contrôle. Les captures viennent du back-office anglais.

Un passage habituel a quatre parties.

1. **Connexion.** Dans **Settings**, collez la clé, choisissez le modèle et appuyez sur **Test connection**, puis sur **Save**.
2. **Un petit essai.** Dans **Manual**, filtrez un domaine, cochez quelques chaînes vides et traduisez-les. Vérifiez le résultat avant de lancer un catalogue entier.
3. **Un travail.** Dans **Bulk**, choisissez la section, les langues et les domaines, appuyez sur **Estimate**, puis sur **Start job**. Ouvrez le travail et appuyez sur **Process slice** ou **Auto-process**, ou laissez l'adresse cron l'appeler.
4. **Un contrôle.** Ouvrez **Review** pour les lignes retenues par le contrôle de qualité, et **History** lorsqu'un appel échoue. **Rollback** sur le travail rétablit le texte précédent là où le module a gardé une copie.

Le module ne lance pas une traduction tout seul. **Estimate**, **Filter** et **Save** dans **Settings** n'écrivent pas le texte du catalogue. Un travail reste dans **Jobs** jusqu'à ce que vous le traitiez ou que l'adresse cron soit appelée.

### 3.1. Configuration du module

Ouvrez **Modules**, **Module Manager**, trouvez **AI Translations with ChatGPT** et appuyez sur **Configure**. Cela ouvre **Dashboard**. Allez dans **Settings**.

**Save** et **Test connection** sont en bas du formulaire. Enregistrer ce formulaire ne lance pas de traduction et ne réécrit pas les traductions déjà stockées.

![Réglages, back-office anglais. Haut du formulaire : ChatGPT API key, Model, Add a ChatGPT model, Tone et Source locale.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-settings.webp)

**Connexion**

| Champ | À l'installation | Effet |
|---|---|---|
| **ChatGPT API key** | vide | Le secret que cette boutique envoie à ChatGPT. Collez la clé de votre compte OpenAI. Laissez la case vide pour garder la clé déjà enregistrée. Une nouvelle valeur remplace la clé stockée. Une case vide ne la supprime pas. Lorsqu'une clé est stockée, l'aide affiche **Key saved:** et une clé masquée. |
| **Model** | gpt-4.1-mini | Le modèle ChatGPT qui écrit la traduction. Les noms intégrés restent dans la liste : gpt-4.1, gpt-4.1-mini, gpt-4.1-nano, gpt-4o, gpt-4o-mini, gpt-4-turbo, gpt-4-turbo-preview, gpt-4, gpt-4-0613, gpt-3.5-turbo, gpt-3.5-turbo-0125, o4-mini, o3-mini et o1-mini. La traduction suivante utilise le modèle choisi. Un modèle que le compte ne peut pas utiliser fait échouer l'appel, et l'erreur est listée dans **History**. |
| **Add a ChatGPT model** | vide | Saisissez l'identifiant exact du compte OpenAI, puis appuyez sur **Add model**. L'exemple dans la case est gpt-4.1. Le nouvel identifiant apparaît dans **Model** et devient le modèle actif. **Remove** ne supprime que les identifiants ajoutés ici. Les identifiants intégrés ne peuvent pas être supprimés. |

Messages : **Model added.**, **Model removed.**, **That model is already in the list. It is now the active model.**, **Enter a model id, for example gpt-4.1.**, **Built-in models cannot be removed.**

**Voix et source**

| Champ | À l'installation | Effet |
|---|---|---|
| **Tone** | Formal | Ajoute une consigne de style à chaque prompt. **Formal** convient aux textes de boutique et de back-office, **Casual** est plus léger, **Brand** s'utilise avec **Brand voice**. Les nouvelles traductions suivent ce style. Les traductions existantes restent jusqu'à ce que vous les relanciez. |
| **Brand voice** | vide | Affiché lorsque **Tone** vaut **Brand**. Quelques phrases simples sur le ton de la boutique, ou une case vide. Le texte entre dans le prompt suivant. Vide signifie qu'il n'y a pas de voix supplémentaire. Cela ne réécrit pas les traductions déjà enregistrées. |
| **Source locale** | vide | La langue que le modèle traite comme l'original. Le choix vide est un tiret dans la liste : l'écran que vous traduisez fournit la source. Choisissez la locale dans laquelle vos catalogues sont écrits, en général en-US. **Manual**, **Bulk** et les icônes de **International → Translations** envoient cette locale comme source. La langue par défaut de la boutique ne change pas. |
| **Individual field buttons — shop forms** | Yes | Un bouton sur chaque champ multilingue des formulaires de boutique : produit, catégorie, CMS et les autres formulaires du back-office. Le bouton ne traduit que ce champ. **No** masque ces boutons dans toute la boutique. Les traductions enregistrées ne changent pas. |
| **Individual field checkboxes — shop forms** | Yes | Chacun de ces champs reçoit une case, et la barre ne traduit que les champs que vous cochez. **No** masque les cases et la barre. Les boutons au-dessus suivent leur propre interrupteur. |
| **Individual field buttons — International → Translations** | Yes | Un bouton sur chaque champ de **International → Translations**. **No** masque ces boutons. Les formulaires de boutique ne sont pas touchés. Un clic remplit ce champ. **Save** de PrestaShop écrit toujours la page. |
| **Individual field checkboxes — International → Translations** | Yes | Cases et barre sur **International → Translations**. **No** les masque. Les formulaires de boutique ne sont pas touchés. |

**Limites**

![Réglages, back-office anglais. Batch size et les champs de limite en dessous.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-settings-limits.webp)

| Champ | À l'installation | Effet |
|---|---|---|
| **Batch size** | 25 | Combien de chaînes partent dans un appel d'API. Prenez 10 à 25 pour un premier passage. La valeur est maintenue entre 1 et 100. Une tranche plus grande termine un travail en moins d'appels. Un échec recommence alors un morceau plus gros. |
| **Dry-run sample** | 10 | Combien de chaînes d'exemple **Estimate** montre avant un travail groupé. La valeur est maintenue entre 1 et 50. **Estimate** n'écrit pas de traductions. |
| **Max tokens (0 = default)** | 0 | Le formulaire enregistre ce nombre. La requête de traduction ne l'envoie pas, donc elle ne raccourcit pas la réponse et n'arrête pas une réponse coupée. Le test de connexion utilise sa propre requête courte. Les traductions déjà enregistrées ne sont pas tronquées. |
| **Budget USD / month** | 0 | Un plafond mensuel en dollars des États-Unis, compté dans le registre d'usage. 0 signifie qu'il n'y a pas de plafond. Lorsque le registre atteint le montant, les nouvelles traductions s'arrêtent. Ce qui est déjà enregistré reste. |
| **Rate limit / min** | 60 | Combien d'appels d'API cette boutique peut lancer en une minute. 0 coupe cette limite locale. Les appels au-dessus de la limite sont ignorés et listés dans **History**. ChatGPT peut encore appliquer sa propre limite. |
| **Log retention days** | 30 | Combien de jours de lignes garder dans **History**. Au moins 1. Les lignes plus anciennes sont retirées. Ce nombre ne supprime pas les travaux, le glossaire ni les traductions enregistrées. |
| **Temperature** | 0.2 | Avec quelle liberté le modèle peut reformuler. Environ 0,2 reste proche de la source. Les valeurs proches de 1 font varier davantage les phrases. La valeur enregistrée est maintenue entre 0 et 1. Les espaces réservés et le HTML sont encore contrôlés ensuite. La requête de traduction envoie cette valeur pour chaque modèle de la liste, y compris un identifiant que vous ajoutez. |
| **Allow publish / save** | Yes | Si ce module peut écrire une traduction dans PrestaShop. **No** bloque l'enregistrement dans **Manual**, les travaux groupés et **Catalog**. Les icônes de la page de traduction et des formulaires de boutique ne font toujours que remplir le formulaire. **Save** de PrestaShop est séparé. |

Après **Save** :

- **Settings saved. No translation was started.** Les réglages sont stockés et rien n'a été traduit.
- **Settings saved. No API key is stored, so nothing can be translated until you paste one.** Collez une clé dans **ChatGPT API key** et appuyez de nouveau sur **Save**.

**Courriel et cron**

| Champ | À l'installation | Effet |
|---|---|---|
| **Email notify on complete** | No | Envoie un courriel lorsqu'un travail groupé se termine. Le travail s'exécute dans les deux cas. Seul le courriel est ajouté ou omis. |
| **Notify email** | vide | L'adresse qui reçoit ce courriel. Le champ n'est affiché que lorsque l'interrupteur au-dessus est activé. Enregistrer l'adresse n'envoie pas un message à lui seul. |
| **CRON URL** | une adresse avec un jeton | Une adresse secrète que le serveur peut appeler pour traiter une tranche d'un travail en attente. Copiez-la dans le planificateur du serveur. Ne la publiez pas. Quiconque a l'adresse peut lancer une tranche. Ouvrir **Settings** ne démarre pas un travail. |

**Test connection** vérifie la clé et le modèle avec une requête courte. Il ne traduit pas et n'enregistre pas.

- **Connection OK (N ms). No translation was started.** La connexion fonctionne.
- **Connection was not made. Nothing was translated.** suivi de la raison. Vérifiez la clé et le modèle. Le détail est dans **History**.

Un démarrage pratique : collez la clé, choisissez le modèle et la locale source, appuyez sur **Test connection**, puis sur **Save**. Laissez les nombres aux valeurs d'installation tant qu'un travail se comporte mal.

### 3.2. Dashboard

Ouvrez l'onglet **Dashboard**. Il compte les chaînes de catalogue manquantes, puis montre l'usage de ChatGPT en cartes, graphiques et les dix prompts les plus récents. La page ne traduit pas et ne change pas les chaînes.

![Dashboard, back-office anglais. Couverture d'une locale, la ligne cron et les filtres d'historique.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-dashboard.webp)

**Couverture**

- **Locale :** la locale de la boutique dont les chaînes manquantes sont comptées.
- **Show :** redessine le tableau pour cette locale.
- Colonnes : **Section**, **Total**, **Missing**, **Done** et une barre de progression. Les sections sont **Back office**, **Themes**, **Installed modules**, **Emails** et **Others**. **Missing** est le nombre de chaînes sans traduction dans cette locale.
- Sous le tableau, **CRON** montre la même adresse que **CRON URL** dans **Settings**.
- Un tableau vide signifie que la boutique n'a pas encore de catalogue pour cette locale. Créez-le sous **International → Translations**.

Après **Show**, le message est **Coverage for {locale}. This page only counts strings. Nothing was translated.**

**Usage**

- Préréglages : **Today**, **7 days**, **30 days**, **This month**, **All time**.
- Filtres : **From**, **To**, **Model**, **Type**, **Status** (**Any**, **Success**, **Error**), **Language**, **Employee** et **Prompt or reply contains**. Appuyez sur **Filter**.
- Cartes : **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** et **Estimated cost**. Le coût estimé est un calcul local, pas une facture OpenAI.
- Graphiques : **Requests and errors**, **Tokens sent and received**, **Requests by model**. En dessous, les groupes **By day**, **By model**, **By type**, **By language** et **By employee**, avec les colonnes **Group**, **Calls**, **Sent**, **Received** et **Total**. Un groupe vide dit **No requests in this range.**
- **Latest prompts** liste dix appels. **View** ouvre le prompt et la réponse. **See all** ouvre **History** (3.10). Une liste vide dit **No requests yet.**

Filtrer ne supprime pas l'historique et ne change pas les traductions.

Si une section manque en grande partie, ouvrez **Manual** pour quelques chaînes ou **Bulk** pour un domaine entier.

### 3.3. Manual

Ouvrez **Manual**. Il traduit un domaine, ou un module classique, quelques dizaines de chaînes à la fois. Filtrer n'enregistre rien.

![Manual, back-office anglais. Section, Source, Target, Domain, Only empty et Search.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-manual.webp)

| Champ | À l'installation | Effet |
|---|---|---|
| **Section** | Back office | Quel catalogue est lu : **Back office**, **Themes**, **Installed modules**, **Emails** ou **Others**. Changer de section recharge la page et n'affiche que les champs de cette section. Cela n'appelle pas ChatGPT. |
| **Theme** | vide | Affiché seulement pour **Themes**. Limite la liste à un thème. |
| **Module** | vide | Affiché seulement pour **Installed modules**. Limite la liste à un module. Un module classique sans domaine charge chaque chaîne de ce module. |
| **Domain** | vide | Le même regroupement que sur **International → Translations**. Choisissez-le et appuyez sur **Filter**. Masqué pour un module classique et pour une section sans domaines. |
| **Source** | la **Source locale** de **Settings**, ou en-US | La langue d'où viennent les chaînes. Choisissez une langue qui a déjà un bon texte. |
| **Target** | la première langue de la liste | La langue que vous voulez remplir. Elle doit exister sous **International → Localization → Languages**. |
| **Only empty** | Yes | N'affiche que les chaînes sans traduction. Le désactiver affiche chaque chaîne. Les traductions enregistrées ne sont pas supprimées. |
| **Search** | vide | Ne garde que les chaînes source qui contiennent le mot saisi. |

Étapes :

1. Réglez **Section**, **Source** et **Target**.
2. Pour **Themes**, choisissez **Theme**. Pour **Installed modules**, choisissez **Module**.
3. Appuyez sur **Filter**. La liste **Domain** se rafraîchit. Choisissez un domaine et appuyez de nouveau sur **Filter**. Pour un module classique, passez le domaine : **Filter** charge chaque chaîne du module.
4. Cochez les lignes. **Check all** et **Uncheck all** sélectionnent ou vident la liste.
5. Appuyez sur **Translate selected (review)**. Un tableau **Review before save** s'ouvre avec **Source**, **AI proposal** et **Warnings**. Décochez les lignes que vous ne voulez pas. Modifiez la proposition dans la case. Appuyez sur **Save approved**.
6. Ou cochez **Save now (skip review)** avant de traduire. Les lignes valides sont écrites tout de suite, sans le tableau de relecture.

Les colonnes de la liste de chaînes sont **Source**, **Current** et **Status** (**empty** ou **filled**).

Messages :

- **Loaded N strings. Tick the rows you want, then press Translate selected. Nothing is saved yet.**
- **Loaded N strings from the whole module. Tick the rows you want, then press Translate selected. Nothing is saved yet.** C'est la liste d'un module classique.
- **This module has no translation domain. Press Filter to load every string in the module. Nothing was sent to ChatGPT.**
- **No strings match this filter. Nothing was sent to ChatGPT.**
- **No strings match this filter. Turn off Only empty, or this module has no classic strings. Nothing was sent to ChatGPT.**
- **Nothing was translated. Choose a domain, then press Filter to load the strings.**
- **Nothing was translated. Pick a theme, then press Filter.**
- **Nothing was translated. Pick a module, then press Filter.**
- **Nothing was translated. Tick at least one row.**
- **Nothing was translated. There is no ChatGPT API key. Open Settings and paste the key.**
- **Review is ready. Nothing is saved until you press Save approved.**
- **Saved. The approved strings were written for the target language.**
- **Saved N. Only the ticked rows were written.**
- **Nothing was saved. Tick OK on the rows you want to keep.**
- **Not saved because of broken placeholders or HTML: N.** Ces lignes ont été ignorées. Corrigez les espaces réservés et les balises pour qu'ils correspondent à la source, puis enregistrez de nouveau.
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. Those rows are not in the current list. Press Filter and tick them again.**

Changer de section affiche aussi une courte ligne telle que **Section is Back office. Theme and module are not used.** avec **Nothing was sent to ChatGPT.** Le même schéma vaut pour **Themes**, **Installed modules**, **Emails** et **Others**.

### 3.4. Bulk

Ouvrez **Bulk**. Il crée un travail pour de nombreux domaines et langues. **Estimate** n'enregistre pas. **Start job** crée une ligne dans **Jobs**. Rien n'est écrit tant que le travail n'est pas traité et que **Allow publish / save** est activé.

![Bulk, back-office anglais. Section, Source, Targets, Domains, Policy et Dry-run job.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-bulk.webp)

| Champ | À l'installation | Effet |
|---|---|---|
| **Section** | Back office | Quel catalogue le travail lit. Les mêmes choix que dans **Manual**. |
| **Theme** / **Module** | vide | Affiché seulement pour la section correspondante, comme dans **Manual**. |
| **Source** | la **Source locale** de **Settings**, ou en-US | La langue traitée comme l'original. Chaque cible est traduite depuis cette langue. |
| **Targets** | aucune | Une ou plusieurs langues à remplir. Maintenez Ctrl, ou Cmd sur un Mac, pour en choisir plusieurs. Un clic simple remplace la sélection. |
| **Domains** | aucun | Domaines inclus dans le travail. Maintenez Ctrl ou Cmd. Les domaines que vous ne sélectionnez pas ne sont pas traduits. Laissez-les tous non sélectionnés seulement si vous voulez un travail vide. L'exception est un module classique sans domaine : le travail couvre alors ce module. |
| **Policy** | Fill empty | **Fill empty** n'envoie que les chaînes sans traduction. **Overwrite all** envoie chaque chaîne, y compris celles qui ont déjà une traduction, et peut les remplacer. **Outdated if equals source** n'envoie que les chaînes dont la traduction est identique à la source. |
| **Dry-run job** | No | ChatGPT s'exécute quand même et le travail apparaît dans **Jobs**, mais les réponses ne sont pas écrites dans la boutique. |

Étapes :

1. Choisissez la section, la source, les cibles, les domaines et la politique.
2. Appuyez sur **Estimate**. La page montre **Estimate**, le nombre de chaînes, une estimation de jetons, une estimation de coût et un **Sample**.
3. Si l'estimation convient, appuyez sur **Start job**. **Jobs** s'ouvre avec le nouveau travail.
4. Traitez-le dans **Jobs** (3.5), ou laissez-le pour l'adresse cron.

Messages :

- **Estimate only: N strings, ~N tokens, ~$X. Nothing was sent to ChatGPT and nothing was saved.**
- **Job #N is waiting (N strings, est. $X). It has not run yet.**
- **Nothing was started. Select at least one target language.**
- **Nothing was started. Pick a theme.**
- **Nothing was started. Pick a module.**
- **Nothing was started. There is no ChatGPT API key. Open Settings and paste the key. No job was created.**

### 3.5. Jobs

Ouvrez **Jobs**. Chaque ligne est une exécution issue de **Bulk**.

![Jobs, back-office anglais. La liste de travaux vide.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-jobs.webp)

Colonnes : **#**, **Status**, **Locales** (source, puis cibles), **Progress** (fait/total), **Cost**, **Employee**, **Date** et **Open**. Une liste vide dit **No jobs yet.**

États du travail, tels qu'à l'écran :

- `pending` - en attente. Il ne démarre pas seul.
- `running` - en cours.
- `paused` - arrêté jusqu'à ce que vous le repreniez.
- `cancelled` - arrêté. Les chaînes qui attendaient encore n'ont pas été traduites.
- `completed` - chaque chaîne traitée, sans échec.
- `completed_with_errors` - terminé, et certaines chaînes ont échoué.
- `failed` - le travail s'est terminé sur une erreur.

**L'écran du travail**

**Open** montre **Job #N**, l'état, la progression (fait/total), **failed**, **skipped**, le coût, le numéro d'employé et l'étiquette **dry-run** lorsque le travail est un essai. La barre de progression se rafraîchit toute seule tant que le travail est ouvert. Le tableau en dessous a **ID**, **Domain**, **Locale**, **Status**, **Source**, **New** et **Error**.

États de ligne : `pending`, `processing`, `done`, `failed`, `skipped` (une exclusion a correspondu, ou la chaîne était déjà traduite) et `rolled_back`.

Boutons :

- **Process slice** - une tranche de la taille de **Batch size**, puis arrêt. Message : **One slice was processed. Check the rows below to see what was saved, skipped or failed.** Lorsqu'il ne reste rien : **The job has no more strings waiting.**
- **Auto-process** - répète les tranches jusqu'à la fin du travail ou jusqu'à ce qu'une erreur l'arrête. Cela tourne dans le navigateur, l'onglet doit rester ouvert. Fermer l'onglet arrête la boucle. Le travail reste et peut être terminé avec **Process slice** ou l'adresse cron.
- **Pause** - message : **Job paused. It will not translate more strings until you resume it.**
- **Resume** - message : **Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.**
- **Retry failed** - les chaînes en échec repassent en attente et le travail attend de nouveau. Message : **Retried N failed items.**
- **Rollback** - demande **Roll back this job?** et rétablit la traduction précédente là où le module a stocké une copie avant le changement. Message : **Rollback: restored N translations.**
- **Error CSV** - télécharge les lignes en échec. Colonnes : id, domain, locale, source, error.
- **Failed only** - n'affiche que les lignes en échec.
- **Review queue** - ouvre **Review** (3.6).

L'écran du travail n'a pas de bouton Cancel. Utilisez **Pause** pour arrêter la suite.

**Pause automatique**

Lorsque ChatGPT refuse des appels à cause d'une limite de débit, le travail se met en pause tout seul. La ligne d'erreur est **Rate limit — job auto-paused. Resume later.** Attendez, puis appuyez sur **Resume**. **Rate limit / min** dans **Settings** baisse le nombre d'appels que la boutique lance en une minute.

Autres messages sur cet écran :

- **Nothing was translated.** suivi de **No ChatGPT API key. Nothing was translated.** Collez la clé dans **Settings**.
- **Allow publish is off in Settings.** Un travail qui n'est pas un essai ne tourne pas tant que vous n'activez pas **Allow publish / save**.
- **Monthly API budget has been exhausted.** Augmentez **Budget USD / month**, ou mettez-le à 0.

### 3.6. Review

Ouvrez **Review**, ou appuyez sur **Review queue** sur un travail. La ligne de titre est **Needs-review queue (quality score / flags).** Elle liste les lignes les plus récentes que le contrôle de qualité n'a pas laissées passer tout seul, jusqu'à 100.

![Review, back-office anglais. La file de relecture vide.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-review.webp)

Colonnes : **ID**, **Score**, **Domain**, **Source**, **AI**, **Flags**, puis **Approve** et **Reject**. Une liste vide dit **The queue is empty.**

Comment lire une ligne :

- **Score** va de 0 à 100. Sous 70, la ligne entre dans la file.
- **Flags :**
  - `validation_failed` - les espaces réservés ou le HTML n'ont pas passé le contrôle.
  - `warning` - une note de contrôle plus petite.
  - `length_explosion` - la traduction fait plus de deux fois et demie la source.
  - `too_short` - la traduction est beaucoup plus courte qu'une source longue.
  - `possible_untranslated` - des mots anglais tels que the, and, with, your ou please sont encore dans la traduction.
- **Source** est l'original. **AI** est la proposition du modèle.

**Approve** et **Reject** ne changent que l'état de la ligne. Le message est **Review updated.** La ligne quitte la liste. Cette page ne colle pas le texte dans le catalogue toute seule.

Si le travail pouvait enregistrer, la proposition est peut-être déjà dans la boutique. Pour annuler un changement de ce travail, utilisez **Rollback** sur le travail dans **Jobs**.

### 3.7. Catalog

Ouvrez **Catalog**. Il traduit les champs produit, catégorie ou CMS stockés dans les langues de la boutique. Il ne modifie pas **International → Translations**. Une pression traite au plus 100 enregistrements. Les lignes enregistrées sont écrites dans la langue cible.

![Catalog, back-office anglais. Entité, champs, langues et Translate batch.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-catalog.webp)

| Champ | À l'installation | Effet |
|---|---|---|
| **Entity** | product | Ce qui est lu : **product**, **category** ou **cms**. Le changer recharge la page et n'affiche que cette liste de champs. Le changement lui-même ne traduit pas. |
| **Fields** | chaque champ de cette entité | Quels textes le lot envoie. Maintenez Ctrl ou Cmd. Les champs non sélectionnés ne sont pas envoyés et restent tels quels. Produit : **Title**, **Short description**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. Catégorie : **Title**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. CMS : **Title**, **Meta description**, **Meta keywords**, **Content**, **Friendly URL**. **Title** d'un produit ou d'une catégorie est le nom. Sur un CMS, **Title** est le titre de page et **Content** est le corps. Laissez **Friendly URL** non sélectionné lorsque les liens doivent rester. |
| **Source language** | la première langue de la boutique | La langue d'où les champs sont copiés. Cette langue n'est pas modifiée. |
| **Target language** | la première langue de la boutique | La langue qui reçoit la traduction. Elle doit être différente de la source. |
| **Only empty** | Yes | Ignore les champs qui ont déjà du texte dans la langue cible. Ne le coupez que lorsque vous voulez remplacer le texte existant. Activé : le texte cible existant reste. Désactivé : le lot peut le remplacer lorsque la publication est autorisée. |
| **Start after ID** | 0 | Ignore les enregistrements jusqu'à cet ID. 0 commence au premier enregistrement. Après un lot, le champ prend l'ID le plus élevé de ce lot, y compris les lignes en échec. Appuyez de nouveau sur le bouton pour continuer. Pour réessayer une ligne en échec, remettez l'ID en dessous de cet enregistrement avant la pression suivante. |

Bouton : **Translate batch (max 100)**.

Étapes :

1. Choisissez **Entity** et cochez les champs.
2. Choisissez **Source language** et **Target language**.
3. Laissez **Only empty** activé.
4. Appuyez sur **Translate batch (max 100)**. Le message est **Catalog finished: saved N, failed M.** La page montre aussi les comptes **Saved** et **failed**.
5. Ouvrez un enregistrement dans la langue cible et vérifiez le résultat avant de couper **Only empty** ou de lancer le lot suivant.

Messages :

- **Nothing was translated. Select at least one field.**
- **Nothing was translated. Source and target language must be different.**
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. There is no ChatGPT API key. Open Settings and paste the key.**
- Changer **Entity** affiche **Showing fields for {entity}. Nothing was translated.**

### 3.8. Glossary

Ouvrez **Glossary**. Le glossaire est une liste de mots et de tournures que le modèle doit garder ou toujours traduire de la même façon. Ajouter une ligne ne change pas les traductions déjà stockées. La traduction suivante lit la liste.

![Glossary, back-office anglais. Ajout d'un terme et liste des termes.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-glossary.webp)

**Un terme**

| Champ | À l'installation | Effet |
|---|---|---|
| **Source term** | vide, obligatoire | Le mot ou la tournure dans la langue source. Saisissez-le exactement tel qu'il apparaît, majuscules comprises lorsqu'elles comptent. |
| **Target locale** | vide | Limite la ligne à une locale, par exemple pl-PL. Vide signifie que la ligne sert pour chaque langue cible. Une locale remplie est ignorée pour les autres langues. |
| **Target term** | vide | La traduction approuvée. Elle ne peut être vide que lorsque **Do not translate** est activé. |
| **Do not translate** | No | Activé : le modèle copie le terme tel quel, par exemple une marque, un SKU ou une balise. Désactivé : il utilise **Target term**. |

Appuyez sur **Add**. Messages : **Glossary term added. Translations already stored were not changed.** ou **Nothing was added. Type a source term.**

**Le tableau**

Colonnes : **Source**, **Locale**, **Target**, **Do not translate** (**Yes** ou **No**) et **Delete**. **Delete** ne retire que cette ligne. Message : **Glossary term deleted.** Une liste vide dit **No glossary terms yet.**

**CSV**

- Choisissez **CSV file** et appuyez sur **Import CSV**. Message : **Imported N rows.** Si le fichier manque : **CSV file is missing.** S'il ne peut pas être lu : **Cannot open the CSV file.**
- La première ligne est un en-tête : `source_term`, `target_locale`, `target_term`, `do_not_translate`. Cette première ligne est toujours ignorée. Les lignes de moins de trois colonnes sont ignorées. Dans la quatrième colonne, une valeur vide ou 0 signifie **No**. Toute autre valeur signifie **Yes**.
- L'import ajoute les lignes qu'il peut lire. Il ne cherche pas un terme existant pour le remplacer, donc importer le même fichier une seconde fois ajoute des doublons.
- **Export CSV** télécharge la liste actuelle sous le nom `glossary.csv`. Il n'a pas besoin d'un fichier d'entrée et ne change pas la liste.

Utilisez des termes courts et exacts. Un terme très large est imposé chaque fois qu'il apparaît.

### 3.9. Excludes

Ouvrez **Excludes**. Une exclusion est un motif de texte source que le module n'envoie pas à ChatGPT. Le texte reste dans la boutique sans changement. Le motif s'applique dans **Manual**, **Bulk**, **Catalog** et sur les pages de traduction.

![Excludes, back-office anglais. Pattern, Type et la liste des motifs.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-excludes.webp)

| Champ | À l'installation | Effet |
|---|---|---|
| **Pattern** | vide, obligatoire | Le texte comparé à chaque chaîne source. La comparaison dépend de **Type**. |
| **Type** | exact | **exact** est la chaîne entière. **prefix** est le début. **contains** est un fragment n'importe où dans la chaîne. **regex** est une expression régulière PHP, appliquée telle qu'elle est écrite. Une expression fausse ne correspond à rien. Commencez par un motif court et vérifiez ce qui a été ignoré. Un mauvais type peut ignorer trop ou rien. |

Appuyez sur **Add**. Message : **Exclude pattern added. Matching strings will be skipped on the next run. Nothing was translated now.** Un motif vide : **Nothing was added. Type a pattern.**

Colonnes : **Pattern**, **Type**, **On** et **Delete**. **On** affiche 1 lorsque le motif est actif. Cet écran n'a pas d'interrupteur pour couper un motif. Pour cesser de l'utiliser, **Delete** et ajoutez-le de nouveau si vous en avez encore besoin. **Delete** ne retire que ce motif. Les traductions existantes ne sont pas supprimées. Message : **Pattern deleted.** Une liste vide dit **No patterns yet.**

Utilisez les exclusions pour un texte qui doit rester dans la langue source, comme un nom juridique ou un jeton technique. Pour un terme qui doit toujours être traduit d'une seule façon, utilisez **Glossary**.

### 3.10. History

Ouvrez **History**, ou appuyez sur **See all** dans **Dashboard**.

![History, back-office anglais. La liste des requêtes.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-history.webp)

**History** est la liste complète des appels ChatGPT stockés : passages manuels, page de traduction, travaux groupés, lots de catalogue et test de connexion. Chaque ligne garde le prompt, la réponse, le modèle, les langues, les comptes de jetons et la durée de l'appel. Les cartes et les graphiques sont dans **Dashboard**. Ouvrir cette page n'envoie pas une nouvelle requête et ne change pas les traductions.

Les filtres sont les mêmes que dans **Dashboard** (3.2).

Colonnes : **ID**, **When**, **Status**, **Type**, **Model**, **Languages**, **Sent**, **Received**, **Total**, **Time** et **Prompt**. Types : **Manual**, **Translation page**, **Bulk job**, **Catalog**, **Connection test**, **Translate** et **Not sent** (l'appel n'a pas été envoyé, par exemple à cause de la limite locale ou du budget). Une ligne **Bulk job** montre le numéro du travail.

- **View** ouvre le prompt et la réponse, avec **HTTP**, **Sent**, **Received** et **Total**. En cas d'erreur, la réponse est le texte de l'erreur. **Back to the list** revient au tableau. Si la ligne a disparu : **This history row no longer exists.**
- Une erreur d'accès signifie que la clé dans **Settings** est fausse, ou que le compte ne peut pas utiliser le modèle choisi.
- **Previous**, **Next** et **Page** parcourent la liste.
- **Clear history** demande **Clear the stored history? Saved translations stay.** Ensuite : **History cleared. Saved translations were not changed.** L'aide du bouton dit **Clear history deletes these rows only. Saved translations stay.**

Une liste vide dit **No requests yet.**

Lorsque les traductions s'arrêtent d'un coup, ouvrez ici la ligne d'erreur la plus récente avant de changer le glossaire.

### 3.11. Updates

Ouvrez **Updates** à l'extrémité droite de la barre du module. Le titre du formulaire est **MyPresta Updates**.

![Updates, back-office anglais. Manual Check, Automatic Notifications et Product Page.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-updates.webp)

- **Manual Check** contient **Check Now**. Il vérifie la version tout de suite.
- **Automatic Notifications** vaut **Enabled** ou **Disabled**. **Enabled** est la valeur lorsque le choix n'a jamais été enregistré. Lorsqu'il est activé, le module vérifie si MyPresta a une version plus récente et peut afficher un avertissement dans le back-office.
- **Product Page** est un lien qui ouvre la page de contact utilisée par ce module.
- **Save** enregistre le choix. Message : **Update settings saved.**

Après **Check Now** : **New version available!** ou **Module is up to date!**

### 3.12. Boutons sur International → Translations

Ouvrez **International → Translations**. Les boutons de champ apparaissent lorsque **Individual field buttons — International → Translations** est activé. Les cases et la barre apparaissent lorsque **Individual field checkboxes — International → Translations** est activé.

Ce que vous voyez :

- Un bouton **Translate** sur chaque champ de texte.
- Une case sur chaque champ, lorsque les cases sont activées.
- Une barre **ChatGPT translations**, avec **Source** (en-US, ou la **Source locale** de **Settings**), **Target**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected** et l'indication **Fills the fields. Save with the PrestaShop button.** **Translate empty in this section** remplit les champs vides de la section en cours.

Étapes :

1. Choisissez **Target**.
2. Cochez les champs, ou appuyez sur **Check empty**.
3. Appuyez sur **Translate selected**, ou sur **Translate empty**.
4. Attendez que la barre affiche **Done**. Pendant le travail, l'état est **Translating…** avec le compte. Si vous ne cochez rien, la barre dit **Tick at least one field.**
5. Vérifiez les champs remplis. Enregistrez la page avec le bouton **Save** de PrestaShop.

Les boutons ne font que remplir les champs. Sans **Save** de PrestaShop, le texte n'entre pas dans la boutique. Avec **Allow publish / save** coupé, les champs sont quand même remplis, et **Save** de PrestaShop écrit la page.

Messages :

- **Target is not a language from this shop.**
- **Fill the source language field first.**
- **The source language field is not on this page.**
- **The source language mail file was not found.** Pour **Emails**, le texte source vient du fichier de modèle de courriel, pas du champ de la page. Choisissez une autre **Source locale** qui possède ces fichiers de courriel.

### 3.13. Boutons sur les formulaires produit, catégorie et CMS

Ouvrez un produit, une catégorie, une page CMS ou un autre formulaire de boutique avec des champs multilingues. Les boutons sont visibles lorsque **Individual field buttons — shop forms** est activé. Les cases et la barre sont visibles lorsque **Individual field checkboxes — shop forms** est activé.

Ce que vous voyez :

- Un bouton **Translate** sur chaque champ multilingue.
- Une case pour la barre.
- Une barre **ChatGPT translations**, avec **Translate from** et **to**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected** et l'indication **Fills the fields. Save with the PrestaShop button.**

Étapes :

1. Remplissez le champ dans la langue source. S'il est vide, la barre dit **Fill the source language field first.**
2. Choisissez la langue cible sur la barre.
3. Appuyez sur le bouton d'un champ, ou cochez des champs et appuyez sur **Translate selected**. **Translate empty** remplit les champs vides.
4. Appuyez sur **Save** sur le formulaire PrestaShop. Sans cela, le texte n'est pas stocké.

Le bouton ne remplit que le champ du formulaire. Les champs que vous ne cochez pas restent inchangés.

## 4. Boutique

Le module n'ajoute rien à la page que le client voit. Il n'y a pas de bloc, de bouton ni de message en vitrine, donc le thème n'a rien à afficher pour ce module.

La seule adresse hors back-office est l'adresse cron. Elle sert à une tâche planifiée sur le serveur. Elle n'est pas destinée aux clients.

- Copiez-la depuis **Settings**, **CRON URL**, ou depuis la ligne **CRON** du **Dashboard**.
- Collez-la dans le planificateur du serveur, par exemple toutes les quelques minutes. Chaque appel traite une tranche d'un travail en attente.
- Utilisez l'adresse `https://` lorsque la boutique a SSL activé.

| Ce que vous voyez en ouvrant l'adresse | Que faire |
|---|---|
| **Forbidden** | L'adresse est incomplète ou a été changée. Copiez-la de nouveau depuis **Settings**. |
| **No pending jobs** | Il n'y a pas de travail en `pending` ni en `running`. Créez-en un dans **Bulk**, ou reprenez un travail en pause dans **Jobs**. |
| Un résultat JSON avec `ok`, `finished` et `counts` | Une tranche a été traitée. Vérifiez la progression dans **Jobs**. |

L'adresse cron ne traite que les travaux en `pending` et `running`. Un travail `paused` doit être repris dans **Jobs**.

## 5. Problèmes

| Ce que vous voyez | Cause | Que faire |
|---|---|---|
| **No ChatGPT API key.** sur chaque page du module | Aucune clé n'est stockée. | Ouvrez **Settings**, collez la clé dans **ChatGPT API key** et appuyez sur **Save**. |
| **Settings saved. No API key is stored, so nothing can be translated until you paste one.** | Les réglages ont été enregistrés sans clé. | Collez la clé et appuyez sur **Save**. |
| **Connection was not made. Nothing was translated.** après **Test connection** | Mauvaise clé, pas de route vers OpenAI, ou un modèle que le compte ne peut pas utiliser. | Vérifiez la clé, choisissez un autre **Model**, ou ajoutez le bon identifiant sous **Add a ChatGPT model**. Lisez la ligne dans **History**. |
| Erreurs d'accès dans **History** | La clé est fausse, ou le compte ne peut pas utiliser le modèle choisi. | Corrigez la clé, ou choisissez un modèle que le compte peut appeler. |
| **Nothing was started. There is no ChatGPT API key.** dans **Bulk** | Pas de clé. | Collez la clé dans **Settings**, puis relancez **Estimate** et **Start job**. |
| Un travail reste sur `pending` | Un travail ne démarre pas seul. | Appuyez sur **Process slice** ou **Auto-process** dans **Jobs**, ou mettez en place l'adresse cron (section 4). |
| Un travail est `paused` avec **Rate limit — job auto-paused. Resume later.** | ChatGPT a refusé des appels à cause d'une limite de débit. La réponse dans **History** peut aussi dire **ChatGPT rate limit (429). Try again later.** | Attendez quelques minutes et appuyez sur **Resume**. Baissez **Batch size** ou **Rate limit / min**. |
| **Monthly API budget has been exhausted.** | **Budget USD / month** a été atteint. | Augmentez le montant, ou mettez 0. Un nouveau mois repart de zéro. |
| **Nothing was saved. Turn on Allow publish in Settings.** | **Allow publish / save** est coupé. | Activez **Allow publish / save**. |
| **Not saved because of broken placeholders or HTML: N.** dans **Manual** | La traduction a changé des espaces réservés ou des balises HTML. | Modifiez la ligne dans **Review before save** pour que les espaces réservés et les balises correspondent à la source, puis appuyez sur **Save approved**. |
| Un travail se termine en `completed_with_errors` | Certaines chaînes ont échoué. | Ouvrez le travail, appuyez sur **Failed only**, téléchargez **Error CSV**, puis appuyez sur **Retry failed**. |
| Une ligne est dans **Review** | Le score est sous 70, le contrôle de longueur a échoué, ou les espaces réservés ont échoué. | Lisez **Flags**. **Approve** ou **Reject** ne change que la file. Utilisez **Rollback** sur le travail lorsque le texte a déjà été écrit. |
| **The shop needs at least two languages.** | La boutique n'a qu'une langue. | Ajoutez une langue sous **International → Localization → Languages**, puis rouvrez le module. |
| Des boutons manquent sur un formulaire produit | Les interrupteurs des formulaires de boutique sont coupés. | Dans **Settings**, activez **Individual field buttons — shop forms** et, si vous voulez la barre, **Individual field checkboxes — shop forms**. |
| La page de traduction n'a pas de barre | Les interrupteurs de la page de traduction sont coupés. | Activez les deux interrupteurs **International → Translations** dans **Settings**. |
| **Max tokens** ne change pas la longueur des réponses | La requête de traduction n'envoie pas ce nombre. | Laissez-le à 0. Raccourcissez un résultat en le modifiant avant **Save approved**. |
| L'import d'un CSV de glossaire a créé des doublons | L'import ajoute des lignes. Il ne remplace pas un terme déjà stocké. | Supprimez les lignes en trop, ou exportez, nettoyez le fichier, supprimez les anciennes lignes et importez une seule fois. |

## 6. Pour les développeurs

### 6.1. Vue d'ensemble

- Classe principale : `myaitranslationsgpt`, fichier `myaitranslationsgpt.php`.
- Version : 1.2.0.
- Nom technique : `myaitranslationsgpt`. Nom dans la liste des modules : **AI Translations with ChatGPT**.
- Auteur : MyPresta.eu. Onglet du Module Manager : `administration`.
- Onglet du back-office : `AdminMyaitranslationsgpt`, parent `AdminInternational`, parent de repli `IMPROVE`. L'étiquette visible est `AI Translations with ChatGPT`. `ensureTab()` répare un onglet manquant. `renameTabIfTechnical()` remplace un nom d'onglet qui est encore le nom technique.
- Installation : `parent::install()`, tables de `sql/install.php` (`CREATE TABLE IF NOT EXISTS`), `installDefaults()` (n'écrit une clé que lorsqu'elle manque), hooks `displayBackOfficeHeader` et `actionAdminControllerSetMedia`, puis l'onglet.
- Désinstallation : supprime l'onglet, `sql/uninstall.php` (supprime 11 tables), `removeConfiguration()` supprime les clés `MYAITGPT_*` qui y sont listées, puis `parent::uninstall()`. Elle ne supprime pas `mypresta_updates`, `update_myaitranslationsgpt` ni `updatev_myaitranslationsgpt`.
- Il n'y a pas de `enable()` ni de `disable()`.
- `getContent()` appelle `ensureTab()` et redirige vers `AdminMyaitranslationsgpt` (onglet par défaut `dashboard`).

Flux de données :

1. Le formulaire de réglages poste vers `AdminMyaitranslationsgptController::initContent()`.
2. `ConfigService::saveFromForm()` stocke `MYAITGPT_*` dans `Configuration`. `ApiKeyEncryptor` chiffre la clé d'API en AES-256-CBC. La clé est `hash('sha256', _COOKIE_KEY_ . '|myaitranslationsgpt|v1', true)`. La valeur stockée est préfixée par `MYAITGPT1:`. Une clé postée vide, ou une valeur masquée, ne remplace pas la clé stockée.
3. Traduction : `TranslateService::translateMessages()` construit les prompts (`PromptBuilder`), les envoie par `OpenAiTranslationProvider` (cURL POST vers `https://api.openai.com/v1/chat/completions`, en-tête `Authorization: Bearer`), contrôle la réponse (`PlaceholderValidator`, `HtmlValidator`, `PsNativeValidator`), la note (`QualityScorer`) et l'enregistre par `TranslationAdapter`.
4. `translateBatch()` envoie `temperature` depuis les réglages et n'envoie pas `max_tokens`. Le test de connexion (`ping`) envoie `max_tokens` 5 et `temperature` 0. `MYAITGPT_MAX_TOKENS` est stocké et n'est pas lu par `translateBatch()`.
5. L'enregistrement du catalogue utilise le service de traduction PrestaShop lorsqu'il existe, sinon la table `_DB_PREFIX_translation`. Les clés des modules classiques sont écrites dans `translations/{iso}.php` de ce module par `LegacyModuleCatalogue`.
6. Bulk : `BulkJobFactory` insère `myaitgpt_job` et `myaitgpt_job_item`. Une liste de domaines vide ne produit pas d'éléments, sauf un module classique, qui utilise `LegacyModuleCatalogue::DOMAIN`. `JobWorker::processSlice()` exécute une tranche de `BATCH_SIZE`. Il est appelé par **Process slice**, par la boucle **Auto-process** (AJAX `ProcessJob`) et par `controllers/front/cron.php`.
7. Catalog : `CatalogTranslateService::collect()` est appelé avec une limite de 100. `translateAndSave()` écrit `_DB_PREFIX_product_lang`, `_DB_PREFIX_category_lang` ou `_DB_PREFIX_cms_lang`. Les résultats sont appariés par id. Après le lot, **Start after ID** devient le plus haut `id_entity` de l'ensemble collecté, y compris les lignes en échec.
8. Chaque appel est stocké dans `myaitgpt_request` (**History**). Les erreurs vont aussi dans `myaitgpt_api_log` (la colonne `provider` vaut `openai` par défaut). Le coût va dans `myaitgpt_usage_ledger`. `SnapshotService` copie la valeur précédente dans `myaitgpt_snapshot` pour **Rollback**. `clearTranslationCache()` appelle `Tools::clearCache()` après un enregistrement de catalogue, après une tranche qui n'est pas un essai, et après un retour arrière.

`QualityScorer` part de 100. `validation_failed` retire 40. Chaque avertissement retire 5. Un rapport de longueur supérieur à 2,5 pose `length_explosion` et retire 20. Un rapport inférieur à 0,3 lorsque la source dépasse 20 caractères pose `too_short` et retire 15. Les mots anglais the, and, with, your ou please restants posent `possible_untranslated` et retirent 10. La ligne a besoin d'une relecture lorsque le score est sous 70, ou lorsque `validation_failed` ou `length_explosion` est posé.

### 6.2. Fichiers

| Fichier | Rôle |
|---|---|
| `myaitranslationsgpt.php` | Installation, désinstallation, onglet, hooks, ressources, `translationClientConfig()`, `getContent()`. |
| `lib/updateChecker.php` | Contrôle de mise à jour pour l'onglet **Updates** et l'avertissement du back-office. Classe `myaitranslationsgptUpdate`. |
| `logo.png`, `logo.gif` | Logo dans l'en-tête du module. |
| `controllers/admin/AdminMyaitranslationsgptController.php` | Chaque onglet du back-office, enregistrements, actions de travail, glossaire, exclusions, catalogue, CSV, AJAX. |
| `controllers/front/cron.php` | Adresse cron. Traite une tranche et renvoie du JSON. |
| `sql/install.php`, `sql/uninstall.php` | Création et suppression des tables. |
| `src/Adapter/TranslationAdapterInterface.php` | Interface de lecture et d'écriture des traductions PrestaShop. |
| `src/Adapter/AbstractTranslationAdapter.php` | Sections, domaines, locales, enregistrement par le service ou la table `translation`, vidage du cache. |
| `src/Adapter/TranslationAdapter.php` | Adaptateur concret. |
| `src/Adapter/TranslationAdapterFactory.php` | Construit l'adaptateur. |
| `src/Adapter/FilesystemCatalogueTrait.php` | Lit les catalogues XLF des thèmes et des modules. |
| `src/Adapter/LegacyModuleCatalogue.php` | Modules classiques : lecture et écriture de `translations/{iso}.php`. |
| `src/Admin/MyaitgptForms.php` | Formulaires du back-office et texte `desc` des champs. |
| `src/Admin/MyaitgptSectionHelp.php` | Texte du panneau **Help** de chaque onglet. |
| `src/Audit/RequestLogRepository.php` | **History** : lignes, cartes, graphiques, filtres, vidage, rétention. |
| `src/Audit/ApiLogRepository.php` | Journal des erreurs et avertissements d'API, rétention. |
| `src/Audit/TranslationMemory.php` | Réutilise un résultat pour le même texte, la même locale, le même modèle et le même glossaire. |
| `src/Audit/UsageLedger.php` | Estimation du coût et budget mensuel. |
| `src/Audit/SnapshotService.php` | Copies avant une écriture, et restauration lors de **Rollback**. |
| `src/Glossary/GlossaryRepository.php` | Liste du glossaire, insertion, suppression. |
| `src/Glossary/ExcludePatternRepository.php` | Insertion, suppression et correspondance des exclusions. |
| `src/Job/JobStatuses.php` | Constantes d'état des travaux et des lignes. |
| `src/Job/JobRepository.php` | Travaux et lignes : lecture, état, tranche suivante, compteurs. |
| `src/Job/JobWorker.php` | Traitement de tranche, nouvel essai, fin, file de relecture, courriel de fin. |
| `src/Provider/TranslationProviderInterface.php` | Interface du fournisseur. |
| `src/Provider/OpenAiTranslationProvider.php` | Appels ChatGPT, test de connexion, journal des requêtes. |
| `src/Provider/PromptBuilder.php` | Prompts système et utilisateur : ton, voix de marque, glossaire. |
| `src/Provider/ProviderFactory.php` | Construit le fournisseur. |
| `src/Quality/PlaceholderValidator.php` | Contrôle des espaces réservés et des balises. |
| `src/Quality/HtmlValidator.php` | Contrôle HTML. |
| `src/Quality/PsNativeValidator.php` | Contrôle avant un enregistrement dans **Manual**. |
| `src/Quality/EmailHtmlPipeline.php` | Protège le HTML du courriel avant l'appel et le rétablit après la réponse. |
| `src/Quality/QualityScorer.php` | Note 0-100, drapeaux, décision de relecture. |
| `src/Security/ApiKeyEncryptor.php` | Chiffre et déchiffre la clé d'API. |
| `src/Service/ConfigService.php` | Lecture et enregistrement des réglages, modèles, jeton cron, plages. |
| `src/Service/RateLimiter.php` | Limite locale par minute, fichier `var/rate_limit.json`. |
| `src/Service/TranslateService.php` | Exclusions, mémoire, appels, validation, note, enregistrement, estimation. |
| `src/Service/BulkJobFactory.php` | Construit un travail **Bulk** et l'estimation. |
| `src/Service/CatalogTranslateService.php` | Collecte et enregistre les lignes de **Catalog**. |
| `src/Service/DashboardService.php` | Comptes de couverture dans **Dashboard**. |
| `translations/*.php` | Textes d'interface, un fichier par langue. |
| `views/templates/admin/configure.tpl` | La page du module et le tiroir **Help**. |
| `views/templates/admin/_partials/*.tpl` | Onglets : `bulk`, `catalog`, `dashboard`, `excludes`, `glossary`, `history-stats`, `jobs`, `logs`, `manual`, `review`, `settings`. |
| `views/css/admin.css` | Styles du back-office. |
| `views/js/admin.js` | Progression de **Jobs** et **Auto-process**, cases de ligne, AJAX. Affiche **Brand voice** seulement lorsque **Tone** vaut **Brand**, et **Notify email** seulement lorsque l'avis par courriel est activé. |
| `views/js/admin-help.js` | Panneau **Help**. |
| `views/js/translations-tool.js` | Boutons et barre sur **International → Translations**. |
| `views/js/entity-fields.js` | Boutons et barre sur les formulaires produit, catégorie et CMS. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Graphiques de **Dashboard**. |
| `var/rate_limit.json` | Compteur de la limite locale par minute. |
| `index.php` dans chaque répertoire | Bloque le listage du répertoire. |

### 6.3. Contrôleurs

**Back-office : `AdminMyaitranslationsgptController`** (`ModuleAdminController`).

- URL : `index.php?controller=AdminMyaitranslationsgpt&token=…`, facultatif `&myaitgpt_tab=` avec `dashboard`, `manual`, `bulk`, `jobs`, `review`, `catalog`, `glossary`, `excludes`, `logs` (l'étiquette de l'onglet est **History**), `settings`, `updates`.
- Actions de travail, requête `job_action` plus `id_job` : `process`, `pause`, `resume`, `cancel`, `retry_failed`, `rollback`, `export_errors`. Le modèle ne dessine pas de bouton Cancel. `filter_failed=1` limite le tableau des lignes. `cancel` met le travail à `cancelled` et laisse les chaînes en attente non traduites. Message : **Job cancelled. Strings still waiting were not translated.**
- Actions de relecture : `review_action=approve|reject` et `id_review`.
- Glossaire : `delete_glossary`. Exclusions : `delete_exclude`. Modèles : `delete_openai_model`, et POST `new_openai_model` avec `submitMyaitranslationsgptAddModel`.
- CSV du glossaire : `importGlossaryCsv()` ignore l'en-tête et toute ligne de moins de trois colonnes, puis insère chaque ligne restante. Il ne met pas à jour un terme existant.
- AJAX : `displayAjaxProcessJob`, `displayAjaxJobStatus`, `displayAjaxHistoryDetail`, `displayAjaxTranslatePageLines`, `displayAjaxMailSource`, `displayAjaxListDomains`.

**Vitrine : `MyaitranslationsgptCronModuleFrontController`** (`controllers/front/cron.php`).

- URL de la boutique : `module/myaitranslationsgpt/cron`.
- La requête `token` doit correspondre à `MYAITGPT_CRON_TOKEN` (`hash_equals`). Un jeton absent ou faux renvoie HTTP 403 et le JSON `{"ok":false,"error":"Forbidden"}`.
- Un `id_job` facultatif traite ce travail. Sans lui, le premier travail `pending` ou `running` est traité.
- Une tranche réussie renvoie un JSON avec `ok`, `finished` et `counts`. Lorsqu'aucun travail n'attend, le corps est `{"ok":true,"message":"No pending jobs"}`.
- `ssl` du contrôleur est true.

### 6.4. Hooks

Hooks enregistrés :

- `displayBackOfficeHeader` - renomme une étiquette d'onglet technique, puis charge le CSS et le JS.
- `actionAdminControllerSetMedia` - charge les mêmes ressources.

`translations-tool.js` est ajouté sur le contrôleur de traductions. `entity-fields.js` est ajouté sur les formulaires de boutique lorsque les interrupteurs de champ sont activés. `Media::addJsDef` publie `myaitgptTr` (URL ajax, locale source, langues et libellés de la barre). Le libellé de la barre est **ChatGPT translations**.

Le module n'enregistre pas de hook propre que d'autres modules devraient implémenter. Il n'y a pas de `enable()` ni de `disable()`.

### 6.5. Surcharges

Le module ne surcharge aucune classe ni aucun contrôleur PrestaShop.

### 6.6. Base de données

| Table | Contenu |
|---|---|
| `myaitgpt_glossary` | `source_term`, `target_locale`, `target_term`, `do_not_translate`, id boutique, dates. |
| `myaitgpt_exclude_pattern` | `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`. |
| `myaitgpt_job` | Une exécution groupée : locales, `scope_json`, `policy_json`, `dry_run`, compteurs, totaux de jetons, coût, employé, erreur, horodatages. |
| `myaitgpt_job_item` | Une chaîne d'un travail : domaine, clé, thème, locale, source, valeur précédente, nouvelle valeur, état, motif d'omission, erreur, jetons, validation. |
| `myaitgpt_memory` | Mémoire de traduction : hash, source, locale, traduction, modèle, nombre de touches. |
| `myaitgpt_usage_ledger` | Lignes quotidiennes de jetons et de coût, id de travail facultatif, modèle. |
| `myaitgpt_snapshot` | Valeur avant une écriture de travail, utilisée par **Rollback**. |
| `myaitgpt_api_log` | Lignes d'erreur et d'avertissement : niveau, fournisseur (défaut `openai`), code HTTP, message, contexte. |
| `myaitgpt_request` | Lignes de **History** : type, état, modèle, locales, code HTTP, durée, jetons, coût, employé, travail, prompt, réponse, erreur. |
| `myaitgpt_review` | File de relecture : élément de travail, état, note, drapeaux, employé. |
| `myaitgpt_catalog_item` | Lignes de lot de catalogue : entité, champ, langues, source, précédente, nouvelle, état, erreur. |

La désinstallation supprime les onze tables. L'installation utilise `CREATE TABLE IF NOT EXISTS`, donc une réinstallation sur une base qui a encore les tables conserve ces lignes. Une désinstallation normale les retire d'abord. Aucune colonne n'est ajoutée à la première visite d'une page.

### 6.7. Clés et traductions

Préfixe `MYAITGPT_`. Valeurs lorsque la clé manque, ce qui est aussi la valeur écrite à l'installation :

| Clé | Lorsqu'elle manque |
|---|---|
| `API_KEY_ENC` | vide |
| `MODEL` | `gpt-4.1-mini` |
| `EXTRA_MODELS` | vide |
| `PROVIDER` | `openai` |
| `TONE` | `formal` |
| `CUSTOM_VOICE` | vide |
| `BATCH_SIZE` | `25` (réécrite bornée à 1-100) |
| `MONTHLY_BUDGET` | `0` |
| `SOURCE_LOCALE` | vide |
| `TEMPERATURE` | `0.2` (réécrite bornée à 0-1) |
| `DRY_RUN_SAMPLE` | `10` (réécrite bornée à 1-50) |
| `RATE_LIMIT_PER_MIN` | `60` |
| `LOG_RETENTION_DAYS` | `30` (minimum 1) |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` |
| `NOTIFY_EMAIL` | vide |
| `PERM_ALLOW_PUBLISH` | `1` |
| `ENTITY_FIELD_BUTTONS` | `1` |
| `ENTITY_BULK` | `1` |
| `TR_FIELD_BUTTONS` | `1` |
| `TR_BULK` | `1` |
| `MAX_TOKENS` | `0` (stocké seulement ; `translateBatch()` ne l'envoie pas) |
| `CRON_TOKEN` | 16 octets aléatoires en hexadécimal, générés à l'installation |

`removeConfiguration()` supprime aussi les noms restants `DEEPL_API_KEY` et `CLAUDE_API_KEY` sous le même préfixe. Il ne supprime pas les clés du contrôle de mise à jour.

Les descriptions de champs sont les chaînes `desc` de `src/Admin/MyaitgptForms.php`, construites par `help()` comme but, réglage et effet. L'aide de **Max tokens** dit de laisser 0 pour la valeur par défaut de ChatGPT. La requête ignore la valeur stockée. L'aide des onglets est `src/Admin/MyaitgptSectionHelp.php`.

Les chaînes d'interface passent par `$this->l()` / `{l s=... mod='myaitranslationsgpt'}`. Ajoutez une langue avec `translations/{iso}.php`. L'erreur de travail **Rate limit — job auto-paused. Resume later.**, **Allow publish is off in Settings.**, **No ChatGPT API key. Nothing was translated.** et **Monthly API budget has been exhausted.** sont des chaînes anglaises renvoyées par `JobWorker` et `TranslateService`, pas des appels à `$this->l()`. Les chaînes de **Updates** utilisent le domaine de traduction `updatechecker`. `OpenAiTranslationProvider` renvoie **ChatGPT rate limit (429). Try again later.** sur HTTP 429.

### 6.8. Extension

La vitrine ne rend pas de modèle du module, donc le thème n'a rien à surcharger.

Les modèles du back-office sont dans `views/templates/admin/`. PrestaShop n'offre pas de surcharge de thème pour ces modèles d'administration. Changez les libellés par `translations/{iso}.php`. Les boutons de **International → Translations** et des formulaires de boutique sont injectés par `views/js/translations-tool.js` et `views/js/entity-fields.js` depuis `myaitgptTr`. Il n'y a pas de hook qu'un thème puisse utiliser pour remplacer cette barre.

## 7. Aide

Page du module : https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-chatgpt.html

Pour écrire au sujet de ce module, connectez-vous à votre compte client sur mypresta.eu, ouvrez le formulaire de contact et choisissez **Support for paid modules**. Le formulaire indique qu'une connexion est exigée pour les modules payants. Après la connexion, choisissez ce module dans l'historique d'achat.
