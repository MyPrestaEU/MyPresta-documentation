---
title: "AI Translations with DeepSeek – documentation et manuel utilisateur (user manual)"
sidebar:
  label: "AI Translations with DeepSeek – documentation et manuel utilisateur (user manual)"
description: "Guide de configuration et de dépannage du module AI Translations with DeepSeek, destiné aux marchands qui possèdent déjà le module."
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module AI Translations with DeepSeek sur MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-deepseek.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ai-artificial-intelligence/ai-translations-with-deepseek/)
>
> ---


## 1. Prérequis

Le module fonctionne sous PrestaShop 1.7.0.0 ou une version ultérieure et nécessite une clé API issue de votre propre compte DeepSeek.

- **PrestaShop :** version 1.7.0.0 ou ultérieure.
- **PHP :** le module ne déclare pas sa propre version minimale de PHP. Le serveur doit exécuter la version de PHP requise par votre version de PrestaShop.
- **Extensions PHP :** cURL (connexion à DeepSeek), mbstring (comptage des caractères dans les textes), OpenSSL (chiffrement de la clé API) et JSON (enregistrement des données envoyées et reçues).
- **Autres modules :** le module ne nécessite aucun autre module.
- **Hors de la boutique :** un compte DeepSeek personnel avec une clé API. Sans clé, le module ne peut rien traduire.
- **Cron sur le serveur :** nécessaire uniquement si les tâches en masse doivent s'exécuter sans clic. Voir la section 3.1.
- **Catalogue volumineux :** une tâche en masse est découpée en tranches, et chaque tranche est un appel à DeepSeek. Les grands périmètres prennent du temps : vérifiez-les avec **Estimate** avant de lancer la tâche.

## 2. Installation

1. Envoyez le fichier ZIP du module dans **Module Manager** avec le bouton **Upload a module**, puis cliquez sur **Install**.
2. Après l'installation, une entrée apparaît dans le menu : **International → AI Translations with DeepSeek**. Cette entrée ouvre le panneau du module.
3. L'installation ne vide pas le cache de la boutique. Si la nouvelle entrée de menu n'apparaît pas, allez dans **Advanced Parameters → Performance** et cliquez sur **Clear cache**.

Après l'installation, le panneau est vide : il n'y a pas de clé API, et les réglages ont les valeurs de départ décrites dans la section 3.1.

**La désinstallation** supprime l'entrée de menu, les tâches en masse avec leur historique, le glossaire, la liste d'exclusions, la mémoire de traduction, les copies de sauvegarde utilisées par **Rollback**, l'historique des appels et des erreurs, la file de révision, la liste de l'onglet **Catalog** et tous les réglages, y compris la clé API et l'adresse cron.

La désinstallation **ne supprime pas** les traductions déjà enregistrées dans la boutique : les textes des produits, des catégories, des pages CMS et de International → Translations restent tels quels. Après la désinstallation, vous ne pourrez plus annuler ces traductions avec **Rollback**, car les copies de sauvegarde disparaissent avec le module.

Réinstaller **ne restaure pas** les données supprimées. Les tables sont recréées vides et les réglages reviennent à leurs valeurs de départ. L'adresse cron change également : copiez la nouvelle depuis **Settings** et mettez à jour la planification sur le serveur.

## 3. Configuration et travail dans le back-office

Les écrans du panneau sont en anglais. Dans ce manuel, les noms des champs, des onglets et des boutons sont donnés exactement tels qu'ils apparaissent à l'écran.

**Qui démarre le travail :** toujours un collaborateur dans le back-office. Les clients ne lancent pas de traductions.

**Le processus de bout en bout :**

1. Dans **Settings**, collez votre clé DeepSeek, choisissez un modèle et cliquez sur **Save**. Cliquez ensuite sur **Test connection** pour vérifier la clé.
2. Réglez **Source locale** (la langue de l'original) et vérifiez que **Allow publish / save** est activé.
3. Choisissez ce qu'il faut traduire. Les domaines et chaînes individuels se traduisent dans **Manual**. Les grands périmètres se confient à **Bulk**. Les champs des produits, catégories et pages CMS se traduisent dans **Catalog**. Les boutons placés à côté des champs des formulaires de la boutique et sur la page International → Translations fonctionnent directement là où vous travaillez.
4. Dans **Manual** et à côté des champs, vous obtenez d'abord une proposition de traduction. Vous l'enregistrez à une étape séparée : avec le bouton **Save approved** dans **Manual**, en cochant **Save now (skip review)**, ou avec le bouton **Save** de PrestaShop sur le formulaire.
5. Dans **Bulk**, cliquez sur **Estimate**. Rien n'est envoyé ni enregistré. Si l'estimation vous convient, cliquez sur **Start job**. La tâche part dans **Jobs** et attend. Elle ne s'exécute pas seule : cliquez sur **Process slice** ou **Auto-process**, ou laissez un appel cron sur le serveur traiter les tranches.
6. Les traductions qui n'ont pas passé le contrôle qualité atterrissent dans **Review**. Le bouton **Approve** change seulement l'état de la ligne. Il n'écrit pas le texte dans la boutique.
7. **Glossary** et **Excludes** agissent sur les traductions suivantes. Les traductions déjà enregistrées ne changent pas.
8. **Dashboard** affiche les manques et les coûts, **History** affiche chaque appel à DeepSeek.

**Comment se termine le travail :** une tâche en masse se termine avec le statut **completed** (tout est traduit) ou **completed_with_errors** (il y a eu des erreurs). Si la notification est activée, un e-mail est alors envoyé. Une traduction manuelle se termine lorsque les lignes sélectionnées sont enregistrées dans la boutique.

### 3.1 Settings (réglages du module)

Chemin : **Modules** → **Module Manager** → nom du module → **Configure**. Le bouton **Configure** ouvre le panneau du module, et l'onglet **Settings** se trouve dans la barre en haut.

![Onglet Settings](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings.webp)

Autres parties du même formulaire :

![Settings – interrupteurs des boutons de traduction et langue source](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings-buttons.webp)

![Settings – limites, budget et température](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings-limits.webp)

![Settings – e-mail, enregistrement et adresse cron avec les boutons Test connection et Save](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings-publish.webp)

Enregistrer le formulaire avec **Save** ne modifie pas les traductions terminées. Si le champ **DeepSeek API key** est vide et qu'aucune clé n'a été enregistrée avant, le message suivant apparaît : « Settings saved. No API key is stored, so nothing can be translated until you paste one. »

| Champ | Valeur de départ | Ce qu'il fait |
|---|---|---|
| **DeepSeek API key** | vide | La clé de votre compte DeepSeek. Un champ vide conserve la clé déjà enregistrée, et une nouvelle valeur la remplace. Un champ vide ne supprime pas la clé. Sous le champ, la clé enregistrée s'affiche masquée. Les requêtes partent vers api.deepseek.com. |
| **Model** | deepseek-flash | Le modèle DeepSeek qui rédige la traduction. Les modèles intégrés sont : deepseek-flash, deepseek-v4-pro, deepseek-v4-flash, deepseek-chat et deepseek-reasoner. Un modèle que le compte ne peut pas utiliser fait échouer l'appel, et l'erreur est enregistrée dans **History**. |
| **Add a DeepSeek model** | vide | Ajoute un identifiant de modèle absent de la liste. Saisissez-le exactement comme dans votre compte DeepSeek, puis cliquez sur **Add model**. Le modèle ajouté devient immédiatement le modèle actif. **Remove** supprime uniquement les modèles ajoutés ici. Les modèles intégrés ne peuvent pas être supprimés. |
| **Tone** | Formal | Un style ajouté à chaque consigne donnée au modèle. **Formal** convient aux textes de la boutique et du back-office, **Casual** est plus léger, et **Brand** fonctionne avec le champ **Brand voice**. Les nouvelles traductions suivent ce style. Les traductions enregistrées ne changent pas tant que vous ne les retraduisez pas. |
| **Brand voice** | vide | Quelques phrases décrivant le ton de la boutique. Le champ apparaît lorsque **Tone** vaut **Brand**. Le texte est ajouté à la consigne suivante et ne réécrit pas les traductions enregistrées. |
| **Source locale** | vide (—) | La langue considérée comme l'original, par exemple English (en-US). Le tiret « — » signifie que l'écran sur lequel vous traduisez fournit lui-même la langue source. Les traductions manuelles et en masse, ainsi que les boutons de International → Translations, envoient cette langue comme source. La langue par défaut de la boutique ne change pas. |
| **Individual field buttons — shop forms** | Oui | Un bouton à côté de chaque champ multilingue des formulaires de la boutique : produit, catégorie, CMS et autres formulaires. Le bouton traduit uniquement ce champ. **Non** masque ces boutons dans toute la boutique. Cela n'affecte pas International → Translations. |
| **Individual field checkboxes — shop forms** | Oui | Une case à cocher à côté des champs des formulaires de la boutique et une barre en bas qui traduit les champs cochés. **Non** masque les cases et la barre. Les boutons de la ligne au-dessus ont leur propre interrupteur. |
| **Individual field buttons — International → Translations** | Oui | Un bouton à côté de chaque champ de International → Translations. **Non** masque ces boutons uniquement sur cette page. Les formulaires de la boutique ne changent pas. |
| **Individual field checkboxes — International → Translations** | Oui | Cases à cocher et barre sur International → Translations. La barre traduit les champs cochés un par un. **Non** masque les cases et la barre sur cette page. |
| **Batch size** | 25 | Le nombre de chaînes envoyées dans un appel à DeepSeek. Les valeurs admises vont de 1 à 100. Pour un premier passage, choisissez entre 10 et 25. Un lot plus grand termine une tâche avec moins d'appels, mais après une erreur, une plus grande partie est répétée. |
| **Dry-run sample** | 10 | Le nombre de chaînes d'exemple affichées par **Estimate** avant une tâche en masse. Les valeurs admises vont de 1 à 50. **Estimate** n'enregistre aucune traduction. |
| **Max tokens (0 = default)** | 0 | Une limite de longueur pour une réponse. 0 correspond à la limite par défaut de DeepSeek. Indiquez un nombre si les réponses sont coupées ou trop longues. La limite s'applique seulement aux appels suivants. |
| **Budget USD / month** | 0 | Un plafond mensuel en dollars américains, calculé à partir de la consommation enregistrée. 0 signifie aucun plafond. Lorsque le plafond est atteint, les nouvelles traductions s'arrêtent, et les traductions déjà enregistrées restent en place. |
| **Rate limit / min** | 60 | Le nombre d'appels que la boutique peut effectuer par minute. 0 désactive cette limite locale. Les appels au-delà de la limite sont ignorés et consignés dans **History**. DeepSeek peut appliquer sa propre limite en plus. |
| **Log retention days** | 30 | Le nombre de jours de conservation des entrées de **History**. Le minimum est de 1 jour. Les entrées plus anciennes sont supprimées. Les tâches, le glossaire et les traductions enregistrées ne sont pas supprimés. |
| **Temperature** | 0.2 | La liberté avec laquelle le modèle reformule le texte. Une valeur proche de 0,2 reste fidèle à l'original, et les valeurs proches de 1 modifient davantage les phrases. Plage admise : de 0 à 1. Les espaces réservés et le HTML sont toujours vérifiés après chaque traduction. |
| **Email notify on complete** | Non | Envoie un e-mail lorsqu'une tâche en masse se termine. La tâche elle-même fonctionne de la même façon ; seul l'envoi change. |
| **Notify email** | vide | L'adresse qui reçoit l'e-mail de fin de tâche. Le champ n'agit que si **Email notify on complete** est activé. Un champ vide envoie l'e-mail à l'adresse de la boutique indiquée dans les informations de l'entreprise. Enregistrer l'adresse n'envoie aucun message. L'objet et le texte sont en anglais, par exemple « myaitranslationsdeepseek job #41 completed », et le texte contient le nombre de chaînes réussies, en échec et ignorées. |
| **Allow publish / save** | Oui | Autorise ou non le module à enregistrer des traductions dans la boutique. Avec **Non**, l'enregistrement est bloqué sur **Manual**, dans les tâches en masse et sur **Catalog**. Les boutons de International → Translations se contentent de remplir le formulaire, et c'est le bouton **Save** de PrestaShop qui l'enregistre. |
| **CRON URL** | adresse générée | Une adresse destinée au planificateur du serveur. Chaque appel traite une tranche d'une tâche en attente, puis s'arrête. Ne publiez pas cette adresse : quiconque la connaît peut lancer une tranche. Ouvrir **Settings** ne lance aucune tâche. |

Boutons en bas du formulaire : **Save** enregistre les réglages. **Test connection** vérifie la clé et n'enregistre aucune traduction.

Démarrage recommandé : collez la clé, choisissez un modèle, réglez **Source locale**, cliquez sur **Save**, puis sur **Test connection**. Laissez les autres valeurs à leur valeur de départ tant qu'une tâche ne se comporte pas comme prévu.

### 3.2 Dashboard

Le Dashboard indique combien de textes manquent dans chaque partie du catalogue pour la langue choisie, ainsi que la consommation de DeepSeek. Ouvrir **Dashboard** n'envoie aucune requête et ne modifie aucune traduction.

![Dashboard](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-dashboard.webp)

- **Locale** est la langue dont on compte les manques. La première fois, la première langue de la liste de la boutique est sélectionnée. Changez la langue et cliquez sur **Show** pour recalculer le tableau.
- **Tableau de couverture** avec les colonnes **Section**, **Done**, **Missing** et **Total**. Chaque ligne correspond à une partie du catalogue : back-office, thèmes, modules, e-mails ou autres. La barre indique la part déjà traduite.
- **Cartes et graphiques** comptent les appels de la période choisie. Les champs de filtre sont des dates (préréglages et **From** et **To**), puis **Model**, type, statut, langue, collaborateur et un mot dans le prompt ou dans la réponse. Le bouton **Filter** applique le filtre. Les cartes affichent le nombre d'appels, les tokens envoyés et reçus, la durée moyenne et le coût estimé. Le coût est une estimation locale, pas une facture.
- **Latest prompts** liste les dix appels les plus récents. **View** ouvre le prompt et la réponse dans une fenêtre. **See all** vous mène à **History**.
- Sous le tableau figure l'adresse cron. C'est le même secret que dans **Settings**.

![Dashboard – graphiques et récapitulatifs](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-dashboard-charts.webp)

Un tableau de couverture vide signifie que la boutique n'a pas encore de catalogue pour cette langue. Le catalogue est créé par International → Translations.

### 3.3 Manual

**Manual** traduit un domaine choisi, quelques chaînes à la fois. **Filter** charge seulement la liste et n'enregistre rien.

![Manual](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-manual.webp)

| Champ | Valeur de départ | Ce qu'il fait |
|---|---|---|
| **Section** | Back office | Choisit le catalogue PrestaShop à lire : **Back office**, **Themes**, **Installed modules**, **Emails** ou **Others**. Changer de section recharge le formulaire et n'appelle pas DeepSeek. |
| **Theme** | — | Apparaît seulement pour **Themes**. Limite la liste à un thème. |
| **Module** | — | Apparaît seulement pour **Installed modules**. Limite la liste à un module. Un module sans domaines charge immédiatement toutes ses chaînes. |
| **Source** | Source locale de **Settings** (en-US) | La langue dont proviennent les textes. Choisissez celle qui possède déjà une traduction fiable. La langue cible ne change pas. |
| **Target** | première langue de la boutique dans la liste | La langue que vous voulez compléter. Elle doit exister dans International → Localization → Languages. La liste et l'enregistrement ultérieur ne concernent que cette langue. |
| **Domain** | — | Le domaine de traduction, les mêmes regroupements que dans International → Translations. Cliquez sur **Filter** pour remplir la liste, choisissez un domaine, puis cliquez de nouveau sur **Filter**. Il n'apparaît pas pour un module sans domaines. |
| **Only empty** | Oui | Masque les chaînes qui ont déjà une traduction. **Non** affiche toutes les chaînes. Le tableau change ; les traductions enregistrées ne sont pas supprimées. |
| **Search** | vide | Ne garde que les chaînes dont la source contient le mot saisi. Le catalogue ne change pas. |

**Comment traduire :**

1. Cochez les lignes, ou cliquez sur **Check all** (coche les lignes visibles). **Uncheck all** décoche.
2. Cliquez sur **Translate selected (review)**. Le module envoie les chaînes cochées et affiche un tableau de révision. Rien n'est encore enregistré.
3. Dans le tableau de révision, décochez une ligne que vous ne voulez pas enregistrer, et corrigez la proposition dans le champ **AI proposal**.
4. Cliquez sur **Save approved**. Les lignes cochées sont enregistrées.

Si vous cochez **Save now (skip review)** avant de traduire, les lignes acceptées sont enregistrées immédiatement, sans le tableau de révision.

Le tableau des résultats comporte les colonnes **Source**, **Current** (la traduction actuelle), **AI proposal**, **Status** (**empty** ou **filled**), **Tokens** et **Warnings**. Une ligne avec un espace réservé ou un HTML cassé n'est pas enregistrée.

Messages que vous pouvez voir :

- « No strings match this filter. Nothing was sent to DeepSeek. » — le filtre n'a trouvé aucune chaîne. Rien n'a été envoyé.
- « Review is ready. Nothing is saved until you press Save approved. » — les propositions attendent dans le tableau. Seul **Save approved** les enregistre.
- « Saved. The approved strings were written for the target language. » — les lignes cochées ont été enregistrées.
- « Not saved because of broken placeholders or HTML: N. » — N lignes n'ont pas été enregistrées, car le modèle a modifié un espace réservé ou une balise HTML. Corrigez-les dans le tableau ou décochez-les.

### 3.4 Bulk

**Bulk** crée une tâche pour plusieurs domaines et langues. La tâche ne s'exécute pas sur cette page. Elle attend dans **Jobs**.

![Bulk](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-bulk.webp)

| Champ | Valeur de départ | Ce qu'il fait |
|---|---|---|
| **Section** | Back office | Le catalogue que lit la tâche. Le champ **Theme** n'apparaît que pour **Themes**, et le champ **Module** seulement pour **Installed modules**. Les chaînes hors de la section choisie ne font pas partie de la tâche. |
| **Source** | Source locale de **Settings** (en-US) | La langue que la tâche considère comme l'original. Chaque cible est traduite à partir d'elle. |
| **Targets** | vide | Les langues que la tâche complète. Vous pouvez en choisir plusieurs : maintenez Ctrl ou Cmd enfoncé et cliquez. La tâche crée des chaînes distinctes pour chaque langue choisie. |
| **Domains** | vide | Les domaines inclus dans la tâche. Les domaines non choisis ne sont pas traduits. |
| **Policy** | Fill empty | **Fill empty** ignore les chaînes qui ont déjà une traduction. **Overwrite all** envoie toutes les chaînes, y compris celles déjà traduites, et peut les remplacer. **Outdated if equals source** envoie les chaînes dont la traduction est identique à l'original. |
| **Dry-run job** | Non | La tâche appelle le modèle et enregistre le résultat dans l'historique de la tâche, mais n'écrit aucune traduction dans la boutique. Avec **Non**, la tâche enregistre les résultats, si **Allow publish / save** est activé. |

**Estimate** affiche le nombre de chaînes, les tokens et le coût estimés, ainsi que des chaînes d'exemple. Rien n'est envoyé ni enregistré. Message : « Estimate only: N strings, ~N tokens, ~$… Nothing was sent to DeepSeek and nothing was saved. »

**Start job** crée la tâche et vous amène dans **Jobs**, avec la nouvelle tâche ouverte. Message : « Job #N is waiting (N strings, est. $…). It has not run yet. »

Messages d'erreur qui empêchent le démarrage :

- « Nothing was started. Select at least one target language. » — aucune langue cible choisie.
- « Nothing was started. Pick a theme. » ou « Nothing was started. Pick a module. » — dans la section **Themes** ou **Installed modules**, aucun thème ou module n'a été choisi.
- « Nothing was started. There is no DeepSeek API key. Open Settings and paste the key. No job was created. » — pas de clé. Aucune tâche n'a été créée.

### 3.5 Jobs

**Jobs** est la file des tâches en masse. Ouvrir la liste n'appelle pas DeepSeek. Le catalogue ne change que pendant le traitement d'une tâche qui n'est pas un essai (dry-run).

![Jobs](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-jobs.webp)

**La liste des tâches** comporte les colonnes **ID**, **Status**, **Locales**, **Progress**, **Cost**, **Employee** et **Date**. Cliquez sur une tâche pour voir ses chaînes. Le filtre **Failed only** n'affiche que les erreurs, et **Error CSV** télécharge la liste des erreurs sous forme de fichier.

Statuts des tâches, exactement comme dans la colonne **Status** : **pending** (en attente), **running** (en cours), **paused** (en pause), **completed** (terminée), **completed_with_errors** (terminée avec des erreurs), **cancelled** (annulée) et **failed** (terminée sur une erreur). Statuts des chaînes dans le détail : **pending**, **processing**, **done**, **failed**, **skipped** et **rolled_back**. La mention **dry-run** signale une tâche d'essai.

**Boutons dans une tâche :**

- **Process slice** envoie le lot suivant (autant de chaînes que l'indique **Batch size**) puis s'arrête. Après le clic, vous voyez quelles lignes ont été enregistrées, ignorées ou ont échoué.
- **Auto-process** envoie les lots les uns après les autres jusqu'à la fin de la tâche ou jusqu'à un échec. Gardez la page ouverte, car la barre de progression se met à jour seule.
- **Pause** met la tâche en pause. Elle ne traduit plus de chaînes tant que vous ne la reprenez pas.
- **Resume** remet la tâche dans la file. La tâche ne démarre pas seule : cliquez sur **Process slice** ou **Auto-process**, ou attendez l'appel cron.
- **Retry failed** remet les chaînes en échec en attente.
- **Rollback** restaure les traductions précédentes là où le module a enregistré une copie de sauvegarde avant la modification. Avant l'exécution, on vous demande : « Roll back this job? ». Message après exécution : « Rollback: restored N translations. »
- **Error CSV** télécharge la liste des lignes en échec.

**Dans cette version du module, l'écran de la tâche ne comporte pas de bouton d'annulation.** N'essayez pas d'annuler une tâche ici. Arrêtez-la avec **Pause** et ne la reprenez pas.

Si DeepSeek refuse trop d'appels, la tâche s'arrête d'elle-même. Son erreur affiche : « Rate limit — job auto-paused. Resume later. »

### 3.6 Review

**Review** est la file des traductions que le contrôle qualité a retenues. Y arrivent les lignes avec un espace réservé ou un HTML cassé, une traduction très longue ou très courte, ou un score inférieur à 70.

![Review](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-review.webp)

| Colonne | Ce qu'elle affiche |
|---|---|
| **ID** | Le numéro de la ligne dans la file. |
| **Domain** | Le domaine d'origine du texte. |
| **Source** | Le texte original. |
| **AI** | La proposition du modèle. |
| **Score** | La note automatique de qualité, de 0 à 100. |
| **Flags** | Les raisons de la mise en attente, décrites ci-dessous. |

**Indicateurs (flags) :**

- **validation_failed** — un espace réservé ou une balise HTML manque ou a été modifié.
- **length_explosion** — la traduction compte plus de deux fois et demie le nombre de caractères de l'original.
- **too_short** — la traduction fait moins de 30 % de la longueur de l'original, et l'original compte plus de 20 caractères.
- **possible_untranslated** — des mots anglais comme « the », « and », « with » subsistent dans la traduction.
- **warning** — un avertissement du contrôle qui abaisse la note.

**Approve** marque la ligne comme acceptée, et **Reject** comme refusée. Aucun de ces deux boutons n'enregistre de texte dans la boutique. Une file vide affiche : « The queue is empty. » Une file vide ne signifie pas que toutes les langues sont traduites. Vérifiez-le dans le **Dashboard**.

Si la tâche était autorisée à enregistrer et que la chaîne a passé la validation, la traduction peut déjà se trouver dans la boutique. La file **Review** est une liste de vérification manuelle, pas un blocage d'enregistrement. L'enregistrement séparé de lignes choisies se fait dans **Manual**.

### 3.7 Catalog

**Catalog** traduit les champs des produits, des catégories et des pages CMS. Il ne couvre pas les textes de International → Translations. Un lot comporte au maximum 100 enregistrements.

![Catalog](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-catalog.webp)

| Champ | Valeur de départ | Ce qu'il fait |
|---|---|---|
| **Entity** | product | Choisit le type d'enregistrements : **product**, **category** ou **cms**. La liste des champs change avec ce choix. Le choix seul ne traduit rien. |
| **Fields** | champs sélectionnés par défaut pour le type | Les textes que le lot envoie. Pour les produits : **Title**, **Short description**, **Description**, **Meta title**, **Meta description** et **Friendly URL**. Pour les catégories : **Title**, **Description**, **Meta title**, **Meta description** et **Friendly URL**. Pour le CMS : **Title**, **Meta description**, **Meta keywords**, **Content** et **Friendly URL**. Sélectionnez en maintenant Ctrl ou Cmd. Les champs non sélectionnés ne sont ni envoyés ni modifiés. |
| **Source language** | première langue de la liste | La langue à partir de laquelle le texte est copié. Elle ne change pas. |
| **Target language** | première langue de la liste | La langue qui reçoit la traduction. Choisissez une langue différente de la source. |
| **Only empty** | Oui | Ignore les champs qui ont déjà du texte dans la langue cible. **Non** envoie aussi les champs remplis, et le lot peut alors remplacer ce texte. |
| **Start after ID** | 0 | Ignore les enregistrements jusqu'à cet ID. 0 commence au premier enregistrement. Après chaque lot, le champ se remplit tout seul, et le lot suivant commence après cet ID. |

Le bouton **Translate batch (max 100)** lance un lot. Le résultat indique combien de lignes ont été enregistrées et combien ont échoué.

Avant de passer **Only empty** sur **Non**, lancez un petit lot et ouvrez un produit dans la langue cible.

### 3.8 Glossary

**Glossary** est une liste de termes que le modèle doit conserver ou traduire d'une façon fixe. Ajouter un terme ne modifie pas les traductions enregistrées. Les traductions suivantes lisent la liste.

![Glossary](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-glossary.webp)

| Champ | Valeur de départ | Ce qu'il fait |
|---|---|---|
| **Source term** | vide (obligatoire) | Le mot ou l'expression dans la langue d'origine, avec les majuscules si elles comptent. Le modèle traite ce terme comme fixe lorsqu'il apparaît dans le texte source. |
| **Target locale** | vide | Limite la ligne à une langue, par exemple pl-PL. Un champ vide applique la ligne à toutes les langues cibles. |
| **Target term** | vide | La traduction approuvée du terme. Ne le laissez vide que si **Do not translate** est activé. |
| **Do not translate** | Non | Le modèle recopie le terme sans le modifier. Activez-le pour les noms de marque, les SKU et les espaces réservés. Désactivez-le lorsque **Target term** doit être la traduction. |

Le bouton **Add** ajoute le terme. Le tableau sous le formulaire comporte les colonnes **Source**, **Locale**, **Target** et **Do not translate**, et chaque ligne a un bouton **Delete** qui supprime uniquement cette ligne. Une liste vide affiche : « No glossary terms yet. »

**Import CSV** ajoute des lignes depuis un fichier. Le fichier doit comporter les colonnes : source_term, target_locale, target_term, do_not_translate. L'import n'ajoute que les lignes qu'il peut lire. **Export CSV** télécharge la liste actuelle et ne modifie rien.

Les termes courts et exacts fonctionnent le mieux. Un terme trop général sera imposé à chaque fois qu'il apparaît.

### 3.9 Excludes

**Excludes** sont des modèles de texte qui ne doivent pas être envoyés à DeepSeek. Le texte reste inchangé dans PrestaShop. Le module l'ignore lors de la prochaine traduction manuelle, de la tâche en masse et des actions de International → Translations.

![Excludes](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-excludes.webp)

| Champ | Valeur de départ | Ce qu'il fait |
|---|---|---|
| **Pattern** | vide (obligatoire) | Le texte ou l'expression comparé à chaque texte source. Selon **Type**, il s'agit du texte complet, du début, d'un fragment ou d'une expression régulière. |
| **Type** | exact | **exact** correspond au texte complet, **prefix** au début, **contains** à un fragment situé n'importe où, et **regex** à une expression régulière PHP. Un modèle trop large ignore plus que prévu. Commencez par un modèle court. |

Le bouton **Add** ajoute le modèle. Le tableau comporte les colonnes **Pattern**, **Type** et **On** (si le modèle est actif). Chaque ligne a un bouton **Delete** qui supprime uniquement ce modèle. Les traductions enregistrées ne sont pas effacées. Une liste vide affiche : « No patterns yet. »

Utilisez des modèles pour les textes qui doivent rester dans la langue source, comme des noms légaux ou des jetons techniques. Si un texte doit être traduit d'une façon fixe, utilisez **Glossary**.

### 3.10 History

**History** est la liste complète des appels enregistrés à DeepSeek : traduction manuelle, page International → Translations, tâches en masse, Catalog et test de connexion. Chaque ligne conserve le prompt, la réponse, le modèle, les langues, le nombre de tokens et la durée de réponse.

![History](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-history.webp)

- **When** est la date de l'appel. **Type** indique l'endroit où il a démarré. Pour une tâche en masse, le numéro qui suit le type est le numéro de la tâche.
- **View** ouvre le prompt envoyé et la réponse reçue dans une fenêtre de cette page. Une ligne en erreur affiche l'erreur à la place de la réponse.
- Filtres : dates, **Model**, type, statut, langue, collaborateur et un mot dans le prompt ou dans la réponse. Les boutons **Previous** et **Next** changent de page.
- **HTTP 401** ou **HTTP 403** signifie que la clé dans **Settings** est incorrecte ou que le compte n'a pas accès au modèle choisi.
- **Clear history** supprime ces entrées, et les traductions enregistrées restent. La question posée avant la suppression est : « Clear the stored history? Saved translations stay. »

Cette page n'envoie aucune nouvelle requête et ne modifie aucune traduction. Si les traductions s'arrêtent soudainement, regardez d'abord la ligne en erreur la plus récente avant de modifier le glossaire.

### 3.11 Updates

L'onglet **Updates** affiche la section **MyPresta Updates**. Le bouton **Check Now** à côté de **Manual Check** vérifie immédiatement si une version plus récente du module existe. Le champ **Automatic Notifications** (**Enabled** ou **Disabled**) décide si le module vérifie de lui-même. Enregistrez votre choix avec **Save**.

Lorsque les notifications automatiques sont activées, le module vérifie la version tous les 3 jours, à l'ouverture du back-office. Il envoie au serveur de MyPresta le nom du module, sa version, l'adresse de la boutique et l'identifiant de licence, s'il est enregistré. Désactiver cette option arrête ces vérifications automatiques.

![Updates](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-updates.webp)

### 3.12 Boutons à côté des champs des formulaires de la boutique

À côté des champs multilingues des formulaires de produits, de catégories, de CMS et des autres formulaires du back-office apparaît un bouton de traduction. Lorsque des champs sont cochés, une barre apparaît aussi en bas du formulaire.

![Produit – traduction d'un champ](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-product-translate.webp)

![Produit – champs meta](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-product-meta.webp)

![Produit – barre de traduction](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-product-bulk-bar.webp)

![Formulaire de catégorie avec la barre de traduction](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-category-translate.webp)

**La barre** en bas comporte les champs **Source** et **Target** ainsi que les boutons **Check all**, **Uncheck all**, **Check empty**, **Translate empty** et **Translate selected**. Le compteur **Selected** indique combien de champs sont cochés.

Le bouton à côté d'un champ remplit seulement ce champ. Pour que la modification reste dans la boutique, cliquez sur le bouton **Save** de PrestaShop au bas du formulaire. La barre fonctionne de la même façon : elle remplit les champs cochés et exige d'enregistrer le formulaire.

Messages de la barre :

- « Fill the source language field first. » — le champ source est vide. Saisissez un texte dans la langue source et réessayez.
- « Tick at least one field. » — aucun champ n'est coché.
- « Target is not a language from this shop. » — la langue cible choisie n'appartient pas à la boutique.
- « Translating… » et « Done » — traduction en cours ou terminée.

Les boutons et la barre disparaissent lorsque les interrupteurs de **Settings** sont désactivés. Pour les formulaires de la boutique, ce sont les interrupteurs **shop forms** qui les commandent.

### 3.13 Page International → Translations

Sur la page International → Translations, un bouton de traduction apparaît à côté de chaque champ, et la même barre apparaît en bas. La barre comporte le champ **Source** (en-US par défaut) et le champ **Target**. Choisissez la langue que vous voulez compléter.

![Page International → Translations](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-translations-page.webp)

- Le bouton à côté d'un champ le remplit avec la traduction. Seul le bouton **Save** de PrestaShop sur cette page l'enregistre.
- La barre traduit les champs cochés un par un.
- **Translate empty in this section** traduit les champs vides de la section ouverte.
- Dans la section **Emails**, le module lit le fichier source du modèle. S'il ne le trouve pas, le message suivant apparaît : « The source language mail file was not found. » Choisissez alors une autre langue source dans **Settings**.
- Le message « The source language field is not on this page. » signifie que cette page ne comporte pas de champ de langue source. Ouvrez un autre onglet ou une autre section qui contient cette langue.

Les interrupteurs **Individual field buttons** et **Individual field checkboxes — International → Translations** dans **Settings** masquent les boutons et la barre uniquement sur cette page.

## 4. Vitrine

Le module n'affiche rien aux clients. Il n'ajoute aucune page, aucun bloc, aucun bouton ni aucun message sur la vitrine, donc le thème ne montre aucun effet du module, et aucune capture de la vitrine n'est faite. Les clients n'ont aucune étape dans le module.

La seule adresse par laquelle un serveur externe peut appeler le module est l'adresse cron de **Settings**. Elle n'est pas destinée aux clients. Le serveur l'utilise pour traiter les tâches.

Ce que vous voyez lorsque vous ouvrez cette adresse dans un navigateur :

| Ce que vous voyez | Que faire |
|---|---|
| Le texte `{"ok":false,"error":"Forbidden"}` | L'adresse est incorrecte ou son jeton a expiré. Copiez de nouveau la CRON URL depuis **Settings** et collez-la dans le planificateur. |
| Le texte `{"ok":true,"message":"No pending jobs"}` | Aucune tâche n'attend. C'est normal, il n'y a rien à faire. |
| Le texte `{"ok":true,...}` avec des données de tranche | Une tranche a été traitée. Vous en verrez le détail dans **Jobs**. |
| Le texte `{"ok":false,"error":"..."}` avec un message | Lisez le message et reportez-vous à la section 5 de ce manuel. |

## 5. Problèmes

**Aucune entrée dans le menu International.** La cause habituelle est le cache de la boutique. Allez dans **Advanced Parameters → Performance** et cliquez sur **Clear cache**. Si l'entrée n'apparaît toujours pas, désinstallez le module puis réinstallez-le. La désinstallation supprime les réglages et l'historique des tâches : enregistrez donc votre clé API et vos réglages avant.

**« Nothing was started. There is no DeepSeek API key. Open Settings and paste the key. No job was created. »** Aucune clé n'a été saisie, ou elle a été supprimée. Ouvrez **Settings**, collez la clé de votre compte DeepSeek, cliquez sur **Save**, puis sur **Test connection**.

**« No DeepSeek API key. Nothing was translated. »** C'est le même cas : collez la clé dans **Settings** et enregistrez.

**« Settings saved. No API key is stored, so nothing can be translated until you paste one. »** Les réglages ont été enregistrés sans clé. Collez la clé et enregistrez de nouveau.

**Test connection échoue, ou History affiche HTTP 401 ou 403.** La clé est incorrecte, expirée, ou le compte n'a pas accès au modèle choisi. Collez la clé à nouveau. Si l'erreur concerne le modèle, choisissez-en un autre dans la liste, ou ajoutez un identifiant valide dans **Add a DeepSeek model**.

**« DeepSeek rate limit (429). Try again later. »** DeepSeek a limité le nombre d'appels. Attendez quelques minutes, puis reprenez la tâche dans **Jobs** avec **Resume** et **Process slice**. Si l'erreur revient, baissez **Batch size** dans **Settings**.

**« Rate limit — job auto-paused. Resume later. »** La tâche s'est mise en pause d'elle-même après trop d'appels refusés. Après un moment, cliquez sur **Resume** dans la tâche, puis sur **Process slice** ou **Auto-process**.

**« Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it. »** La tâche attend un démarrage manuel ou l'appel cron. Cliquez sur **Process slice** ou **Auto-process**. Pour que les tâches s'exécutent sans clic, ajoutez la CRON URL au planificateur du serveur et appelez-la régulièrement.

**« Monthly API budget has been exhausted. »** Le plafond mensuel **Budget USD / month** est atteint. Ouvrez **Settings**, augmentez le montant ou mettez 0 pour supprimer le plafond. Les nouvelles traductions reprennent lorsque la tâche est relancée.

**« Allow publish is off in Settings. »** L'enregistrement des traductions est bloqué. Ouvrez **Settings** et activez **Allow publish / save**. Sans cela, **Process slice** n'enregistrera aucun texte dans la boutique.

**« Not saved because of broken placeholders or HTML: N. »** N lignes n'ont pas été enregistrées, car le modèle a modifié un espace réservé ou une balise HTML. Ouvrez **Review** ou le tableau de **Manual**, corrigez la proposition et enregistrez de nouveau, ou refusez la ligne.

**La tâche s'est terminée avec le statut completed_with_errors.** Certaines chaînes ont échoué. Dans **Jobs**, activez le filtre **Failed only**, téléchargez le **Error CSV**, puis cliquez sur **Retry failed** pour relancer les chaînes en échec.

**Une traduction ne peut pas être annulée.** **Rollback** restaure uniquement les traductions pour lesquelles le module a enregistré une copie de sauvegarde avant la modification. Ces copies appartiennent à la tâche. Elles disparaissent lorsque le module est désinstallé.

**La traduction est enregistrée, mais la page affiche l'ancien texte.** Videz le cache : **Advanced Parameters → Performance → Clear cache**. Sur les formulaires de la boutique et sur International → Translations, rappelez-vous que les boutons et la barre ne font que remplir les champs. C'est le bouton **Save** de PrestaShop qui les enregistre.

**Les boutons de traduction n'apparaissent pas à côté des champs.** Les interrupteurs sont désactivés. Ouvrez **Settings** et activez l'interrupteur correspondant : **Individual field buttons** ou **Individual field checkboxes** pour les formulaires de la boutique, ou pour International → Translations.

**« Fill the source language field first. »** Le champ de la langue source est vide. Saisissez un texte dans cette langue et réessayez.

**« The source language mail file was not found. »** Il n'existe pas de fichier dans la langue source pour ce modèle d'e-mail. Choisissez un autre **Source locale** dans **Settings**, ou traduisez le modèle à la main.

**Après Start job, rien ne se passe.** Start job ne fait que créer la tâche ; il ne la lance pas. Ouvrez **Jobs** et cliquez sur **Process slice** ou **Auto-process**.

**L'e-mail de fin de tâche n'arrive pas.** Vérifiez que **Email notify on complete** est activé et que l'adresse de **Notify email** est correcte. Un champ vide envoie à l'adresse de la boutique. L'e-mail n'est envoyé qu'à la fin de la tâche. Vérifiez aussi que la boutique envoie bien des e-mails dans **Advanced Parameters → E-mail**.

**Une tâche ne peut pas être annulée.** Cette version du module n'a pas de bouton d'annulation sur l'écran de la tâche. Arrêtez la tâche avec **Pause** et ne la reprenez pas.

**History est vide ou affiche « No requests yet. »** Aucun appel à DeepSeek n'a encore été effectué. Le Dashboard affiche aussi des zéros tant que vous n'avez pas lancé de traduction.

## 6. Pour les développeurs

Cette section décrit le code du module. Les clés de configuration et les noms de classes n'apparaissent qu'ici.

### 6.1 Vue d'ensemble

- **Classe principale :** `myaitranslationsdeepseek` (étend `Module`), fichier `myaitranslationsdeepseek.php`.
- **Nom technique :** `myaitranslationsdeepseek`. Le préfixe des clés de configuration et des tables est `MYAITDS_` et `myaitds_`.
- **Version :** 1.2.0.
- **Nom dans la liste des modules :** AI Translations with DeepSeek.
- **Auteur dans le code :** MyPresta.eu. Onglet : `administration`.
- **Compatibilité :** PrestaShop de 1.7.0.0 à 99.99.99, `bootstrap = true`, `need_instance = 0`.
- **Onglet de menu :** classe `AdminMyaitranslationsdeepseek`, parent `AdminInternational` (solution de repli : `IMPROVE`).

Flux de données : les réglages sont lus par `MyaitdsConfigService` depuis `Configuration` (clés `MYAITDS_*`). Les services `MyaitdsTranslateService`, `MyaitdsJobWorker` et `MyaitdsCatalogTranslateService`, ainsi que le contrôleur du back-office, appellent `MyaitdsDeepSeekTranslationProvider`, qui envoie une requête cURL à `https://api.deepseek.com/chat/completions` (délai de 120 s, délai de connexion de 15 s). La réponse passe par les validateurs (`MyaitdsPlaceholderValidator`, `MyaitdsHtmlValidator`, `MyaitdsPsNativeValidator`) et par `MyaitdsQualityScorer`. L'enregistrement passe par `MyaitdsTranslationAdapterFactory` vers le service de traduction de PrestaShop, et vers la table `translation` si ce service est absent. Pour les modules classiques, l'enregistrement se fait dans le `translations/{iso}.php` du module concerné. Les appels sont consignés dans `myaitds_request` et `myaitds_api_log`, les coûts dans `myaitds_usage_ledger`. La mémoire de traduction (`myaitds_memory`) permet d'éviter un appel à l'API pour la même source, la même langue, le même modèle et la même version de glossaire.

### 6.2 Fichiers

| Fichier | Rôle |
|---|---|
| `myaitranslationsdeepseek.php` | Classe principale : installation, désinstallation, onglet de menu, hooks du back-office, redirection `getContent()` vers le contrôleur. |
| `sql/install.php` | Crée les 11 tables (`CREATE TABLE IF NOT EXISTS`). |
| `sql/uninstall.php` | Supprime les 11 tables (`DROP TABLE IF EXISTS`). |
| `controllers/admin/AdminMyaitranslationsdeepseekController.php` | Contrôleur du back-office : tous les onglets, actions des formulaires, actions des tâches et requêtes AJAX. |
| `controllers/front/cron.php` | Contrôleur front `cron` : traite une tranche de tâche. |
| `src/Admin/MyaitdsForms.php` | Formulaires HelperForm et leurs textes `desc`. |
| `src/Admin/MyaitdsSectionHelp.php` | Texte d'aide de chaque onglet. |
| `src/Service/MyaitdsConfigService.php` | Lit et écrit `MYAITDS_*`, liste des modèles, plages de valeurs, clé API. |
| `src/Service/MyaitdsTranslateService.php` | Traduction manuelle et par boutons : mémoire, budget, validation, enregistrement. |
| `src/Service/MyaitdsBulkJobFactory.php` | Estimation et création des tâches en masse. |
| `src/Service/MyaitdsCatalogTranslateService.php` | Champs des produits, catégories et CMS, lots de 100 enregistrements au maximum. |
| `src/Service/MyaitdsDashboardService.php` | Calcul de la couverture (textes manquants et traduits). |
| `src/Service/MyaitdsRateLimiter.php` | Limite d'appels par minute, enregistrée dans `var/rate_limit.json`. |
| `src/Job/MyaitdsJobWorker.php` | Traite les tranches, enregistre, snapshots, file de révision, e-mail de fin. |
| `src/Job/MyaitdsJobRepository.php` | Lit et écrit les tâches et leurs chaînes. |
| `src/Job/MyaitdsJobStatuses.php` | Constantes des statuts de tâches et de chaînes. |
| `src/Provider/MyaitdsDeepSeekTranslationProvider.php` | Appel de l'API DeepSeek (cURL), gestion des erreurs et des codes HTTP. |
| `src/Provider/MyaitdsPromptBuilder.php` | Construit le prompt avec le ton, la voix de marque et le glossaire. |
| `src/Provider/MyaitdsProviderFactory.php` | Crée le fournisseur (actuellement DeepSeek uniquement). |
| `src/Provider/MyaitdsTranslationProviderInterface.php` | Interface du fournisseur de traduction. |
| `src/Adapter/MyaitdsTranslationAdapterInterface.php` | Interface d'accès au catalogue PrestaShop. |
| `src/Adapter/MyaitdsAbstractTranslationAdapter.php` | Logique commune : sections, domaines, enregistrement, vidage du cache. |
| `src/Adapter/MyaitdsFilesystemCatalogueTrait.php` | Parcours des fichiers XLF et des répertoires de traduction. |
| `src/Adapter/MyaitdsLegacyModuleCatalogue.php` | Lit et écrit les `translations/{iso}.php` des modules classiques. |
| `src/Adapter/MyaitdsTranslationAdapter.php` | Implémentation concrète de l'adaptateur (étend l'adaptateur abstrait). |
| `src/Adapter/MyaitdsTranslationAdapterFactory.php` | Crée l'adaptateur. |
| `src/Quality/MyaitdsPlaceholderValidator.php` | Vérifie les espaces réservés dans la traduction. |
| `src/Quality/MyaitdsHtmlValidator.php` | Vérifie les balises HTML. |
| `src/Quality/MyaitdsPsNativeValidator.php` | Combine la vérification des espaces réservés et du HTML. Utilise les classes de PrestaShop (`Validate::isCleanHtml`) lorsqu'elles sont disponibles. |
| `src/Quality/MyaitdsEmailHtmlPipeline.php` | Protège les balises et variables des modèles d'e-mail contre la traduction. |
| `src/Quality/MyaitdsQualityScorer.php` | Note de 0 à 100, indicateurs et décision de mise en file de révision (seuil 70). |
| `src/Glossary/MyaitdsGlossaryRepository.php` | Lit et écrit le glossaire. L'import et l'export CSV sont dans le contrôleur. |
| `src/Glossary/MyaitdsExcludePatternRepository.php` | Modèles d'exclusion. |
| `src/Audit/MyaitdsRequestLogRepository.php` | Historique des appels (**History**) : enregistrement, filtres, affichage et nettoyage selon la rétention. |
| `src/Audit/MyaitdsApiLogRepository.php` | Journal de l'API et sa rétention. |
| `src/Audit/MyaitdsTranslationMemory.php` | Mémoire de traduction (empreinte de la source, de la langue, du modèle et du glossaire). |
| `src/Audit/MyaitdsUsageLedger.php` | Consommation mensuelle et coûts, source du budget. |
| `src/Audit/MyaitdsSnapshotService.php` | Valeurs avant modification et leur restauration (**Rollback**). |
| `src/Security/MyaitdsApiKeyEncryptor.php` | Chiffrement de la clé API (AES-256-CBC). |
| `views/templates/admin/configure.tpl` | Structure du panneau à onglets. |
| `views/templates/admin/_partials/*.tpl` | Contenu des onglets : dashboard, manual, bulk, jobs, review, catalog, glossary, excludes, logs, settings, history-stats. |
| `views/js/admin.js` | Logique du back-office : tâches, traitement automatique, formulaires. |
| `views/js/admin-help.js` | Fenêtres d'aide des onglets. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Graphiques du **Dashboard**. |
| `views/js/entity-fields.js` | Boutons et barre à côté des champs des formulaires de la boutique. |
| `views/js/translations-tool.js` | Boutons et barre sur International → Translations. |
| `views/css/admin.css` | Styles du panneau et des boutons. |
| `lib/updateChecker.php` | Vérification des versions auprès de MyPresta et onglet **Updates**. |
| `translations/*.php` | Traductions du module (27 langues, dont `pl.php`). |
| `var/rate_limit.json` | État de la limite d'appels par minute. |
| `logo.png`, `logo.gif` | Logo dans la liste des modules et dans le panneau. |

### 6.3 Contrôleurs

**Back-office :** `AdminMyaitranslationsdeepseekController`, onglet `AdminMyaitranslationsdeepseek`, parent `AdminInternational`. L'onglet est choisi par le paramètre `myaitds_tab`. Valeurs admises : `dashboard`, `settings`, `manual`, `bulk`, `jobs`, `glossary`, `excludes`, `logs` (l'onglet **History**), `review`, `catalog` et `updates`. Toute autre valeur ouvre `dashboard`. Le contrôleur ne définit pas de droits propres : ce sont les droits d'onglet configurés dans PrestaShop qui s'appliquent.

Actions de formulaire (`Tools::isSubmit`) : `submitMyaitranslationsdeepseekSettings`, `…Ping` (Test connection), `…AddModel`, `…GlossaryAdd`, `…GlossaryImport`, `…GlossaryExport`, `…ExcludeAdd`, `…BulkPreview`, `…Bulk`, `…ManualFilter`, `…ManualTranslate`, `…SaveReview`, `…Catalog`, `…Dashboard`, `…ClearHistory`.

Actions GET : `job_action` (`process`, `pause`, `resume`, `retry_failed`, `rollback`, `export_errors` ; `cancel` est gérée, mais aucun modèle ne crée de lien vers elle), `review_action` (`approve`, `reject`) avec `id_review`, `delete_deepseek_model`, `delete_glossary`, `delete_exclude`.

Actions AJAX (`?controller=AdminMyaitranslationsdeepseek&ajax=1&action=…`), traitées par les méthodes `displayAjax*` : `HistoryDetail` (détail d'une ligne d'historique, paramètre `hist_id`), `ProcessJob` (une tranche, `id_job`), `JobStatus` (état de la tâche), `TranslatePageLines` (lignes de la page de traduction), `MailSource` (fichier source d'un modèle d'e-mail), `ListDomains` (domaines d'une section).

**Front :** `MyaitranslationsdeepseekCronModuleFrontController` dans `controllers/front/cron.php`. L'adresse a la forme `index.php?fc=module&module=myaitranslationsdeepseek&controller=cron&token=…`. Réglages du contrôleur : `$ssl = true`, `$ajax = true`. Paramètres : `token` (obligatoire, comparé à `MYAITDS_CRON_TOKEN` avec `hash_equals`) et `id_job` facultatif. Sans `id_job`, le module prend la première tâche au statut `pending` ou `running` parmi les 20 plus récentes. Un jeton incorrect renvoie HTTP 403 avec `{"ok":false,"error":"Forbidden"}`. Sans tâche, il renvoie `{"ok":true,"message":"No pending jobs"}`. Une tranche traitée renvoie le résultat de `processSlice`.

### 6.4 Hooks

Enregistrés à l'installation :

- `displayBackOfficeHeader` → `hookDisplayBackOfficeHeader()` : renomme l'onglet si son nom est encore technique, et charge les ressources du back-office.
- `actionAdminControllerSetMedia` → `hookActionAdminControllerSetMedia()` : charge les mêmes ressources.

`loadBoAssets()` fonctionne ainsi : sur l'onglet `AdminMyaitranslationsdeepseek`, il ajoute `admin.css`, `admin.js`, `admin-help.js`, et sur **Dashboard** également `chart.min.js` et `history-charts.js`. Sur la page `AdminTranslations`, il ajoute `translations-tool.js` lorsque les boutons ou la barre de International → Translations sont activés (`MYAITDS_TR_BUTTONS` ou `MYAITDS_TR_BULK`). Sur les autres pages du back-office, il ajoute `entity-fields.js` lorsque les boutons ou la barre des formulaires de la boutique sont activés (`MYAITDS_ENTITY_BUTTONS` ou `MYAITDS_ENTITY_BULK`). Il transmet la configuration via `Media::addJsDef` sous les noms `myaitdsTr` et `aitHelpLabels`.

Le module **n'expose aucun hook** : il n'appelle pas `Hook::exec` et n'enregistre aucun hook côté front.

Le module **n'a pas** de méthodes `enable()` ni `disable()`. Activer ou désactiver ne déclenche aucune action du module. PrestaShop retire les hooks lors de la désinstallation.

### 6.5 Surcharges

Le module n'a pas de répertoire `override/` et ne surcharge aucune classe ni aucun contrôleur de PrestaShop.

Fichiers écrits par le module : les traductions passent par le service de traduction de PrestaShop (`prestashop.service.translation`), et par la table `translation` si le service est absent. Pour les modules classiques (clés au format `<{nom}>prestashop`), le module réécrit le `translations/{iso}.php` de ce module, d'abord dans un fichier temporaire, puis par renommage. Il vide le cache avec `Tools::clearCache()`. Il écrit aussi `var/rate_limit.json` et les valeurs `update_<module>`, `updatev_<module>` et `mypresta_updates` dans `Configuration`.

### 6.6 Base de données

Les tables utilisent le préfixe de la boutique (`_DB_PREFIX_`). Elles sont toutes créées avec le moteur `_MYSQL_ENGINE_` et le collationnement `utf8mb4_unicode_ci`.

| Table | Contenu |
|---|---|
| `myaitds_glossary` | Termes du glossaire : `id_shop`, `source_term`, `target_locale`, `target_term`, `do_not_translate`, dates. Index `idx_shop_locale`. |
| `myaitds_exclude_pattern` | Modèles d'exclusion : `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`, `date_add`. |
| `myaitds_job` | Tâches : `uuid` (unique), `status`, `source_locale`, `target_locales`, `scope_json`, `policy_json`, `dry_run`, compteurs `items_*`, tokens, `cost_usd_estimate` et `cost_usd_actual`, `id_employee`, `error_summary`, `started_at`, `finished_at`. |
| `myaitds_job_item` | Chaînes d'une tâche : `id_myaitds_job`, `domain`, `translation_key`, `theme`, `target_locale`, `source_text`, `previous_translation`, `new_translation`, `status`, `skip_reason`, `error_message`, `tokens_used`, `source_hash`, `validated_ok`, `validation_warnings`. |
| `myaitds_memory` | Mémoire de traduction : `memory_hash` (unique), `source_text`, `target_locale`, `translation`, `model`, `hit_count`. |
| `myaitds_usage_ledger` | Consommation quotidienne : `usage_date`, `id_myaitds_job`, `model`, tokens, `cost_usd`. Source du budget mensuel. |
| `myaitds_snapshot` | Valeurs avant modification : `id_myaitds_job`, `id_myaitds_job_item`, `locale`, `domain`, `translation_key`, `theme`, `value_before`. Source de **Rollback**. |
| `myaitds_api_log` | Journal de l'API : `id_myaitds_job`, `level`, `provider`, `http_code`, `message`, `context_json`. Nettoyée selon `MYAITDS_LOG_RETENTION_DAYS`. |
| `myaitds_request` | Historique des appels (**History**) : type, statut, modèle, langues, code HTTP, durée, tokens, coût, `prompt`, `reply`, `error_message`. Nettoyée selon la rétention. |
| `myaitds_review` | File de révision : `id_myaitds_job_item`, `status` (`needs_review`, `approved`, `rejected`), `quality_score`, `flags_json`, `id_employee`. |
| `myaitds_catalog_item` | Créée à l'installation, mais aucun code n'y écrit ni n'y lit. |

L'installation crée les tables uniquement avec `CREATE TABLE IF NOT EXISTS`. Le module n'ajoute aucune colonne à l'ouverture d'une page (il n'y a pas de `ALTER TABLE` dans le code).

La désinstallation supprime les 11 tables. Une réinstallation les recrée vides.

### 6.7 Clés et traductions

**Clés de configuration** (préfixe `MYAITDS_`) et valeurs de départ de `installDefaults()` :

| Clé | Valeur de départ | Notes |
|---|---|---|
| `API_KEY_ENC` | `''` | Clé chiffrée en AES-256-CBC ; la clé de chiffrement est dérivée de `_COOKIE_KEY_`. |
| `MODEL` | `deepseek-flash` | Le modèle utilisé pour les appels. |
| `EXTRA_MODELS` | `''` | Identifiants de modèles ajoutés (**Add a DeepSeek model**). |
| `PROVIDER` | `deepseek` | Le seul fournisseur. Il n'a pas de champ dans le panneau. |
| `TONE` | `formal` | `formal`, `casual`, `brand`. |
| `CUSTOM_VOICE` | `''` | Texte de la voix de marque. |
| `BATCH_SIZE` | `25` | Plage 1–100. |
| `MONTHLY_BUDGET` | `0` | 0 = aucun plafond. |
| `SOURCE_LOCALE` | `''` | Vide signifie que l'écran fournit la source. Valeur de repli dans le code : `en-US`. |
| `TEMPERATURE` | `0.2` | Plage 0–1. |
| `DRY_RUN_SAMPLE` | `10` | Plage 1–50. |
| `RATE_LIMIT_PER_MIN` | `60` | Le champ du formulaire s'appelle `MYAITDS_RATE_LIMIT`. 0 désactive la limite. |
| `LOG_RETENTION_DAYS` | `30` | Minimum 1. |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` | Interrupteur de l'e-mail. |
| `NOTIFY_EMAIL` | `''` | Vide = `PS_SHOP_EMAIL`. |
| `PERM_ALLOW_PUBLISH` | `1` | Bloque l'enregistrement depuis **Manual**, les tâches et **Catalog**. |
| `ENTITY_FIELD_BUTTONS`, `ENTITY_BULK` | `1` | Boutons et barre à côté des champs des formulaires de la boutique. |
| `TR_FIELD_BUTTONS`, `TR_BULK` | `1` | Boutons et barre sur International → Translations. |
| `MAX_TOKENS` | `0` | 0 = limite par défaut de DeepSeek. |
| `CRON_TOKEN` | 16 octets aléatoires (hex) | Jeton de l'adresse cron. |

La désinstallation supprime les clés ci-dessus, ainsi que `DEEPL_API_KEY` et `CLAUDE_API_KEY`, que le module n'utilise plus.

**Textes hors de `$this->l()`.** Les textes des champs et de l'aide passent par `l()` dans les domaines `myaitdsforms` (`MyaitdsForms`) et `sectionhelp` (`MyaitdsSectionHelp`). Les libellés JavaScript sont transmis à `Media::addJsDef` par `translationClientConfig()`. L'objet et le texte de l'e-mail de fin sont en anglais dans `MyaitdsJobWorker::notifyComplete()` et ne passent pas par `l()`. Les messages affichés via `$this->module->l()` dans le contrôleur utilisent le domaine `adminmyaitranslationsdeepseekcontroller`.

**Ajouter une langue :** créez un fichier `translations/{iso}.php` sur le modèle des fichiers existants (par exemple `translations/pl.php`). PrestaShop charge le fichier correspondant au code ISO de la boutique.

**Source des textes des champs :** `MyaitdsForms::help()` (le `desc` de chaque champ) ainsi que `MyaitdsSectionHelp::pages()` et `brief()` (texte d'aide des onglets).

### 6.8 Extension

- **Thème :** rien à surcharger. Le module ne rend aucun modèle front.
- **Modèles du back-office :** `views/templates/admin/`. Les modifications des fichiers du module sont perdues lors d'une mise à jour.
- **Nouveaux modèles DeepSeek :** aucune modification de code n'est nécessaire ; utilisez **Add a DeepSeek model** (`EXTRA_MODELS`).
- **Nouveau fournisseur :** implémentez `MyaitdsTranslationProviderInterface` et ajoutez une entrée dans `MyaitdsProviderFactory`.
- **Seuil de la file de révision :** 70 points, défini dans `MyaitdsQualityScorer::score()`.
- **Glossaire et exclusions :** gérés dans le panneau, sans modification de code.

## 7. Aide

Page du module : https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-deepseek.html

Connectez-vous à votre compte client sur mypresta.eu, rendez-vous dans la rubrique contact et choisissez le sujet **Support for paid modules**. Le formulaire indique que la connexion est obligatoire pour les modules payants. Après connexion, sélectionnez ce module dans votre historique d'achats.
