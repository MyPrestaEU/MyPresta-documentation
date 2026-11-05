---
title: "AI Translations with Grok - documentation et manuel utilisateur"
description: "Guide de configuration et de dépannage pour les boutiques qui utilisent déjà AI Translations with Grok."
sidebar:
  label: "AI Translations with Grok - documentation et manuel utilisateur"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module AI Translations with Grok sur MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-grok.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ai-artificial-intelligence/ai-translations-with-grok/)
>
> ---


## 1. Prérequis

Le module fonctionne sur PrestaShop 1.7.0.0 et les versions suivantes, y compris PrestaShop 8 et 9.

- **PrestaShop :** 1.7.0.0 ou plus récent.
- **PHP :** 5.6 ou plus récent.
- **Extensions PHP :** cURL, OpenSSL, SimpleXML et mbstring.
- **Autres modules :** aucun n'est nécessaire.
- **Hors de la boutique :** un compte xAI et une clé API Grok, à récupérer dans la console xAI. Le serveur de la boutique doit pouvoir joindre `https://api.x.ai/v1/chat/completions`.
- **Facultatif :** une tâche planifiée sur le serveur qui appelle l'adresse cron indiquée dans **Paramètres**. Sans elle, vous traitez les tâches vous-même dans **Tâches**.
- **Grands catalogues :** un domaine de plusieurs milliers de chaînes représente beaucoup d'appels API. Une tâche est découpée en tranches dont la taille correspond à **Taille du lot (Batch size)**. Avant de lancer une tâche, appuyez sur **Estimer** dans **En masse (Bulk)** pour voir le nombre de chaînes et le coût attendu.
- La boutique doit avoir au moins deux langues. Avec une seule, le back-office affiche **La boutique a besoin d'au moins deux langues.** et il n'y a rien à traduire.

## 2. Installation

1. Ouvrez **Modules**, puis **Gestionnaire de modules**. Choisissez l'option d'envoi d'un module, envoyez le fichier ZIP, puis appuyez sur **Installer** à côté de **AI Translations with Grok**.
2. Une fois l'installation terminée, **AI Translations with Grok** apparaît dans le menu **International**.
3. L'installation ne vide pas le cache de la boutique. Le module le vide lorsqu'il enregistre une traduction.

Ouvrez ensuite **AI Translations with Grok**, allez dans **Paramètres** et collez votre clé Grok. Tant qu'aucune clé n'est enregistrée, chaque page du module affiche **Pas de clé API Grok.** avec le lien **Ouvrir les paramètres**.

**Désinstallation.** Dans le **Gestionnaire de modules**, appuyez sur **Désinstaller**, puis confirmez **Supprimer ce module et ses données (tâches, glossaire, cache) ?**

- L'entrée de menu disparaît. Sont supprimés : les tâches, le glossaire, les motifs d'exclusion, l'historique des appels, la file **Révision**, les copies d'annulation, le registre des coûts et les réglages du module, clé API comprise.
- Le texte que le module a déjà écrit dans la boutique reste en place : traductions du catalogue et fichiers de traduction des modules classiques écrits par ce module. Votre choix concernant la vérification des mises à jour est conservé.
- Une nouvelle installation ne restaure pas les tâches, le glossaire ni l'historique supprimés. Elle rétablit les valeurs par défaut et crée une nouvelle adresse cron.

## 3. Configuration et utilisation quotidienne

Tout le module tient sur une seule page : **International**, puis **AI Translations with Grok**. Les onglets sont **Tableau de bord**, **Manuel**, **En masse (Bulk)**, **Tâches**, **Révision**, **Catalogue**, **Glossaire**, **Exclusions**, **Historique** et **Paramètres**. **Mises à jour** se trouve à la fin de la barre. **Aide** ouvre le panneau de l'onglet en cours. L'onglet **Mises à jour** n'a pas de bouton **Aide**.

Les captures d'écran de ce manuel proviennent du back-office en anglais. Les noms des boutons et des champs cités dans le texte sont ceux du back-office en français.

Un travail courant se déroule en quatre étapes.

1. **Connexion.** Dans **Paramètres**, collez la clé, choisissez le modèle, appuyez sur **Tester la connexion**, puis sur **Enregistrer**.
2. **Petit essai.** Dans **Manuel**, filtrez un domaine, cochez quelques chaînes vides et traduisez-les. Vérifiez le résultat avant de traduire tout le catalogue.
3. **Tâche.** Dans **En masse (Bulk)**, choisissez la section, les langues et les domaines, appuyez sur **Estimer**, puis sur **Démarrer la tâche**. Ouvrez la tâche et appuyez sur **Traiter la tranche** ou **Traitement auto**, ou laissez l'adresse cron s'en charger.
4. **Contrôle.** Ouvrez **Révision** pour les lignes que le contrôle qualité a mises de côté, et **Historique** lorsqu'un appel échoue. **Annuler** sur une tâche rétablit le texte précédent, à condition que le module ait gardé une copie.

Le module ne lance jamais une traduction de lui-même. **Estimer**, **Filtrer** et **Enregistrer** dans **Paramètres** n'écrivent aucun texte de catalogue. Une tâche reste dans **Tâches** tant que vous ne la traitez pas ou que l'adresse cron ne l'appelle pas.

### 3.1. Configuration du module

Ouvrez **Modules**, **Gestionnaire de modules**, trouvez **AI Translations with Grok** et appuyez sur **Configurer**. Le **Tableau de bord** s'ouvre. Passez à **Paramètres**.

**Enregistrer** et **Tester la connexion** se trouvent en bas du formulaire. Enregistrer ce formulaire ne lance aucune traduction et ne réécrit pas les traductions déjà enregistrées.

![Paramètres, back-office en anglais. Haut du formulaire : clé API, modèle, ajout de modèle, tonalité et paramètres régionaux source.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-settings.webp)

**Connexion**

| Champ | Valeur par défaut | Effet |
|---|---|---|
| **Clé API Grok** | vide | La clé secrète que la boutique envoie à Grok. Collez la clé depuis la console xAI. Laisser le champ vide conserve la clé déjà enregistrée. Saisir une nouvelle valeur la remplace. Un champ vide ne supprime pas la clé. Lorsqu'une clé est enregistrée, l'aide affiche **Clé enregistrée :** suivi de la clé masquée. |
| **Modèle** | grok-4.7 | Le modèle Grok qui rédige la traduction. Les modèles intégrés figurent dans la liste : grok-4.7, grok-4.6, grok-4.5, grok-4.3, grok-4.20-0309-non-reasoning et grok-4.20-0309-reasoning. Les modèles que vous ajoutez peuvent être retirés. La traduction suivante utilise le modèle choisi. Si votre compte ne peut pas utiliser un modèle, l'appel échoue et l'erreur apparaît dans **Historique**. |
| **Ajouter un modèle Grok** | vide | Saisissez l'identifiant exact du modèle dans votre compte xAI, puis appuyez sur **Ajouter un modèle**. L'exemple affiché est grok-4.7. Le nouvel identifiant apparaît dans **Modèle** et devient le modèle actif. **Supprimer** ne retire que les identifiants ajoutés ici. Les modèles intégrés ne peuvent pas être supprimés. |

Messages possibles : **Modèle ajouté.**, **Modèle supprimé.**, **Ce modèle est déjà dans la liste. Il est désormais le modèle actif.**, **Entrez un identifiant de modèle, par exemple grok-4.7.**, **Les modèles intégrés ne peuvent pas être supprimés.**

**Voix et source**

| Champ | Valeur par défaut | Effet |
|---|---|---|
| **Tonalité** | Formel | Ajoute une consigne de style à chaque prompt. **Formel** convient aux textes de la boutique et du back-office, **Décontracté** est plus léger, et **Marque** s'utilise avec **Voix de la marque**. Les nouvelles traductions suivent ce style. Les traductions déjà enregistrées restent telles quelles jusqu'à leur nouvelle exécution. |
| **Voix de la marque** | vide | Visible lorsque **Tonalité** vaut **Marque**. Quelques phrases simples décrivant le ton de la boutique, ou un champ vide. Le texte est ajouté au prompt suivant. Un champ vide signifie qu'aucune voix supplémentaire n'est ajoutée. Les traductions existantes ne sont pas réécrites. |
| **Paramètres régionaux source (Locale)** | vide | La langue que le modèle considère comme l'original. L'option vide apparaît comme un tiret dans la liste : la source est alors l'écran que vous traduisez. En général, vous choisissez les paramètres régionaux dans lesquels vos catalogues sont rédigés, souvent en-US. **Manuel**, **En masse (Bulk)** et les icônes de **International → Traductions** utilisent ces paramètres comme source. La langue par défaut de la boutique ne change pas. |
| **Boutons de champ individuel — formulaires de boutique** | Oui | Un bouton à côté de chaque champ multilingue des formulaires de la boutique : produit, catégorie, CMS et autres formulaires du back-office. Le bouton ne traduit que ce champ. **Non** masque ces boutons dans toute la boutique. Les traductions enregistrées ne changent pas. |
| **Cases à cocher de champ individuel — formulaires de boutique** | Oui | Chaque champ de ce type reçoit une case à cocher, et la barre ne traduit que les champs cochés. **Non** masque les cases et la barre. Les boutons ci-dessus ont leur propre interrupteur. |
| **Boutons de champ individuel — International → Traductions** | Oui | Un bouton sur chaque champ de **International → Traductions**. **Non** masque ces boutons. Les formulaires de la boutique ne sont pas concernés. Un clic remplit ce champ. Le bouton **Enregistrer** de PrestaShop enregistre toujours la page. |
| **Cases à cocher de champ individuel — International → Traductions** | Oui | Cases et barre sur **International → Traductions**. **Non** les masque. Les formulaires de la boutique ne sont pas concernés. |

**Limites**

![Paramètres, back-office en anglais. Taille du lot et les champs de limite en dessous.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-settings-limits.webp)

| Champ | Valeur par défaut | Effet |
|---|---|---|
| **Taille du lot (Batch size)** | 25 | Nombre de chaînes envoyées dans un seul appel API. Pour un premier essai, prenez une valeur entre 10 et 25. La valeur doit rester comprise entre 1 et 100. Un lot plus grand termine une tâche en moins d'appels, mais en cas d'échec, c'est un morceau plus gros qui est relancé. |
| **Échantillon de test (Dry-run sample)** | 10 | Nombre de chaînes d'exemple affichées par **Estimer** avant une tâche en masse. La valeur doit rester entre 1 et 50. **Estimer** affiche autant de chaînes source et une estimation du coût. Il n'enregistre aucune traduction. |
| **Jetons max (Max tokens, 0 = par défaut)** | 0 | Plafond de longueur d'une réponse. Laissez 0 pour utiliser la longueur par défaut de Grok. Saisissez un nombre si les réponses sont coupées ou si vous voulez des réponses plus courtes. Le plafond ne s'applique qu'à l'appel suivant et ne raccourcit pas les traductions déjà enregistrées. |
| **Budget USD / mois** | 0 | Plafond mensuel en dollars, calculé à partir du registre d'utilisation. 0 signifie qu'il n'y a pas de plafond. Saisissez le montant que vous acceptez de dépenser à partir du premier jour du mois. Lorsque le registre atteint ce montant, les nouvelles traductions s'arrêtent et l'écran affiche **Monthly API budget has been exhausted.** Le travail déjà enregistré reste en place. |
| **Limite de débit / min (Rate limit)** | 60 | Nombre d'appels API que cette boutique peut lancer en une minute. 60 est un bon point de départ. 0 désactive cette limite locale. Les appels au-delà de la limite sont ignorés et consignés dans **Historique**. Grok peut appliquer sa propre limite en plus. |
| **Jours de conservation des journaux** | 30 | Nombre de jours pendant lesquels les lignes restent dans **Historique**. Le minimum est 1. Les lignes plus anciennes sont supprimées lorsqu'un nouvel appel est enregistré. Ce nombre ne supprime ni les tâches, ni le glossaire, ni les traductions enregistrées. |
| **Température** | 0.2 | Liberté laissée au modèle pour reformuler une phrase. Une valeur proche de 0,2 reste fidèle à la source. Les valeurs proches de 1 modifient davantage les phrases. La valeur enregistrée doit rester entre 0 et 1. Les variables et le HTML sont vérifiés ensuite. La traduction suivante utilise cette valeur. |
| **Autoriser la publication / l'enregistrement** | Oui | Indique si le module peut écrire une traduction dans PrestaShop. **Non** bloque l'enregistrement depuis **Manuel**, les tâches en masse et **Catalogue**. Les icônes de la page de traduction et des formulaires de la boutique ne font que remplir le formulaire. Le bouton **Enregistrer** de PrestaShop est distinct. |

Après **Enregistrer**, vous pouvez voir l'un de ces messages :

- **Paramètres enregistrés. Aucune traduction n'a été lancée.** Les réglages sont enregistrés et rien n'a été traduit.
- **Paramètres enregistrés. Aucune clé API n'étant stockée, aucune traduction ne peut être effectuée tant que vous n'en collez pas une.** Collez la clé dans **Clé API Grok** et appuyez de nouveau sur **Enregistrer**.

**E-mail et cron**

| Champ | Valeur par défaut | Effet |
|---|---|---|
| **Notification par e-mail à la fin** | Non | Envoie un e-mail lorsqu'une tâche en masse se termine. La tâche s'exécute de toute façon. Seul l'envoi de l'e-mail change. |
| **E-mail de notification** | vide | L'adresse qui reçoit cet e-mail. Le champ n'apparaît que si l'interrupteur ci-dessus est activé. Si le champ est vide, l'e-mail de la boutique est utilisé. Enregistrer l'adresse n'envoie aucun message. L'objet commence par le nom du module, le numéro de tâche et le statut. |
| **URL CRON** | adresse avec jeton | L'adresse secrète que le serveur peut appeler pour traiter une tranche d'une tâche en attente. Copiez-la dans le planificateur du serveur et ne la publiez pas. Quiconque connaît l'adresse peut lancer une tranche. Ouvrir **Paramètres** ne démarre aucune tâche. |

**Tester la connexion** vérifie la clé et le modèle avec un court appel. Il ne traduit rien et n'enregistre rien.

- **Connexion OK (N ms). Aucune traduction n'a été lancée.** La connexion fonctionne.
- **La connexion n'a pas pu être établie. Rien n'a été traduit.** suivi immédiatement de la raison. Vérifiez la clé et le modèle. Les détails sont dans **Historique**.

Pour bien démarrer : collez la clé, choisissez le modèle et les paramètres régionaux source, appuyez sur **Tester la connexion**, puis sur **Enregistrer**. Gardez les valeurs numériques par défaut tant qu'une tâche se comporte normalement.

### 3.2. Tableau de bord

Ouvrez l'onglet **Tableau de bord**. Il compte les chaînes de catalogue manquantes, puis affiche l'utilisation de Grok sous forme de cartes, de graphiques et des dix dernières invites. La page ne traduit rien et ne modifie aucune chaîne.

![Tableau de bord, back-office en anglais. Couverture d'une locale, ligne cron et filtres de l'historique.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-dashboard.webp)

**Couverture**

- **Locale :** la locale de la boutique dont on compte les chaînes manquantes.
- **Afficher :** redessine le tableau pour cette locale.
- Colonnes : **Section**, **Total**, **Manquant**, **Terminé** et une barre de progression. Les sections sont **Back-office**, **Thèmes**, **Modules installés**, **E-mails** et **Autres**. **Manquant** correspond au nombre de chaînes sans traduction dans cette locale.
- Sous le tableau, **CRON** affiche la même adresse que **URL CRON** dans **Paramètres**.
- Un tableau vide signifie que la boutique n'a pas encore de catalogue pour cette locale. Créez-le dans **International → Traductions**.

Après **Afficher**, le message est **Couverture pour {locale}. Cette page compte uniquement les chaînes. Rien n'a été traduit.**

**Usage**

- Préréglages : **Aujourd'hui**, **7 jours**, **30 jours**, **Ce mois-ci** et **Tout le temps**.
- Filtres : **Du**, **Au**, **Modèle**, **Type**, **Statut** (**Tous**, **Succès**, **Erreur**), **Langue**, **Employé** et **L'invite ou la réponse contient**. Appuyez sur **Filtrer**.
- Cartes : **Requêtes**, **Succès**, **Erreurs**, **Jetons envoyés**, **Jetons reçus**, **Total des jetons**, **Temps moyen** et **Coût estimé**. Le coût estimé est un calcul local, pas une facture xAI. Un tiret signifie que Grok n'a pas renvoyé le nombre de jetons pour cet appel.
- Graphiques : **Requêtes et erreurs**, **Jetons envoyés et reçus**, **Requêtes par modèle**. En dessous, les regroupements **Par jour**, **Par modèle**, **Par type**, **Par langue** et **Par employé**, avec les colonnes **Groupe**, **Appels**, **Envoyé**, **Reçu** et **Total**. Un groupe vide affiche **Aucune requête sur cette période.**
- **Dernières invites** liste les dix derniers appels. **Voir** ouvre l'invite et la réponse. **Tout voir** ouvre **Historique** (section 3.10). Si la liste est vide, vous lisez **Aucune requête pour le moment.**

Filtrer n'efface pas l'historique et ne modifie pas les traductions.

Si une section est presque vide, ouvrez **Manuel** pour quelques chaînes, ou **En masse (Bulk)** pour un domaine entier.

### 3.3. Manuel

Ouvrez **Manuel**. Cet onglet traduit un domaine ou un module classique, par quelques dizaines de chaînes à la fois. Filtrer n'enregistre rien.

![Manuel, back-office en anglais. Section, source, cible, domaine, uniquement vides et recherche.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-manual.webp)

| Champ | Valeur par défaut | Effet |
|---|---|---|
| **Section** | Back-office | Catalogue lu : **Back-office**, **Thèmes**, **Modules installés**, **E-mails** ou **Autres**. Changer de section recharge la page et n'affiche que les champs de cette section. Grok n'est pas appelé. |
| **Thème** | vide | Visible uniquement pour **Thèmes**. Limite la liste à un thème. |
| **Module** | vide | Visible uniquement pour **Modules installés**. Limite la liste à un module. Un module classique sans domaine charge toutes les chaînes de ce module. |
| **Domaine** | vide | Le même regroupement que dans **International → Traductions**. Choisissez-le puis appuyez sur **Filtrer**. Masqué pour un module classique et pour les sections sans domaine. La ligne vide affiche un tiret avec le texte de choix. |
| **Source** | **Paramètres régionaux source (Locale)** de **Paramètres**, sinon en-US | La langue d'où sont prises les chaînes. Choisissez une langue qui possède déjà un bon texte. |
| **Cible** | la première langue de la liste | La langue que vous voulez compléter. Elle doit exister dans **International → Localisation → Langues**. |
| **Uniquement vides** | Oui | N'affiche que les chaînes sans traduction. Désactivé, toutes les chaînes apparaissent. Les traductions enregistrées ne sont pas supprimées. |
| **Rechercher** | vide | Ne conserve que les chaînes source qui contiennent le mot saisi. |

Étapes :

1. Réglez **Section**, **Source** et **Cible**.
2. Pour **Thèmes**, choisissez un **Thème**. Pour **Modules installés**, choisissez un **Module**.
3. Appuyez sur **Filtrer**. La liste **Domaine** se recharge. Choisissez un domaine et appuyez de nouveau sur **Filtrer**. Pour un module classique, laissez le domaine vide : **Filtrer** charge toutes les chaînes du module.
4. Cochez les lignes voulues. **Tout cocher** et **Tout décocher** cochent ou vident la liste.
5. Appuyez sur **Traduire la sélection (avec révision)**. Le tableau **Réviser avant d'enregistrer** s'ouvre avec les colonnes **Source**, **Proposition de l'IA** et **Avertissements**. Décochez les lignes que vous ne voulez pas, corrigez la proposition directement dans le champ, puis appuyez sur **Enregistrer les approuvés**.
6. Vous pouvez aussi cocher **Enregistrer maintenant (ignorer la révision)** avant de traduire. Les lignes valides sont alors enregistrées immédiatement, sans passer par le tableau de révision.

Les colonnes de la liste de chaînes sont **Source**, **Actuel** et **Statut** (**vide** ou **rempli**).

Messages possibles :

- **N chaînes chargées. Cochez les lignes voulues, puis cliquez sur Traduire la sélection. Rien n'est encore enregistré.**
- **N chaînes chargées pour tout le module. Cochez les lignes voulues, puis cliquez sur Traduire la sélection. Rien n'est encore enregistré.** C'est la liste d'un module classique.
- **Ce module n'a pas de domaine de traduction. Appuyez sur Filtrer pour charger toutes les chaînes du module. Rien n'a été envoyé à Grok.**
- **Aucune chaîne ne correspond à ce filtre. Rien n'a été envoyé à Grok.**
- **Aucune chaîne ne correspond à ce filtre. Désactivez Uniquement vides, ou ce module ne contient pas de chaînes classiques. Rien n'a été envoyé à Grok.**
- **Rien n'a été traduit. Choisissez un domaine, puis appuyez sur Filtrer pour charger les chaînes.**
- **Rien n'a été traduit. Choisissez un thème, puis appuyez sur Filtrer.**
- **Rien n'a été traduit. Choisissez un module, puis appuyez sur Filtrer.**
- **Rien n'a été traduit. Cochez au moins une ligne.**
- **Rien n'a été traduit. Aucune clé API Grok. Ouvrez Paramètres et collez la clé.**
- **La révision est prête. Rien n'est enregistré tant que vous n'appuyez pas sur Enregistrer les approuvés.**
- **Enregistré. Les chaînes approuvées ont été écrites pour la langue cible.**
- **N enregistrées. Seules les lignes cochées ont été écrites.**
- **Rien n'a été enregistré. Cochez OK sur les lignes que vous voulez conserver.**
- **Non enregistré à cause de variables ou de HTML invalides : N.** Ces lignes ont été ignorées. Alignez les variables et les balises sur la source, puis enregistrez à nouveau.
- **Rien n'a été enregistré. Activez Autoriser la publication dans les Paramètres.**
- **Rien n'a été traduit. Ces lignes ne figurent pas dans la liste actuelle. Appuyez sur Filtrer et cochez-les de nouveau.**

Changer de section affiche aussi une courte ligne, par exemple **La section est Back-office. Le thème et le module ne sont pas utilisés.**, avec **Rien n'a été envoyé à Grok.** Le même principe vaut pour **Thèmes**, **Modules installés**, **E-mails** et **Autres**.

### 3.4. En masse

Ouvrez **En masse (Bulk)**. Cet onglet crée une seule tâche pour plusieurs domaines et langues. **Estimer** n'enregistre rien. **Démarrer la tâche** ajoute une ligne dans **Tâches**. Rien n'est écrit tant que la tâche n'est pas traitée et que **Autoriser la publication / l'enregistrement** est activé.

![En masse, back-office en anglais. Section, source, cibles, domaines, politique et tâche de simulation.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-bulk.webp)

| Champ | Valeur par défaut | Effet |
|---|---|---|
| **Section** | Back-office | Catalogue lu par la tâche. La page se recharge et n'affiche **Thème** que pour **Thèmes**, et **Module** que pour **Modules installés**. Les chaînes hors de cette section ne sont pas incluses. Changer de section ne démarre pas la tâche. |
| **Thème** | vide | Visible uniquement pour **Thèmes**. Les autres thèmes sont écartés. |
| **Module** | vide | Visible uniquement pour **Modules installés**. Un module classique n'a pas de domaine : **Estimer** et **Démarrer la tâche** couvrent toutes les chaînes du module. |
| **Source** | **Paramètres régionaux source (Locale)** de **Paramètres**, sinon en-US | La locale que la tâche traite comme original. Chaque cible est traduite à partir de cette locale. |
| **Cibles** | aucune cochée | Les locales que la tâche va compléter. Cochez-en une ou plusieurs. Un clic sans Ctrl remplace la sélection. La tâche conserve un jeu de chaînes par locale cochée. |
| **Domaines** | aucun coché | Les domaines inclus dans la tâche. Maintenez Ctrl ou Cmd pour cocher plusieurs lignes. Les domaines non cochés sont ignorés. Ne laissez tout décoché que si vous voulez une tâche vide. Masqué pour un module classique. |
| **Politique** | Remplir les vides | **Remplir les vides** ignore les chaînes qui ont déjà une traduction. **Tout écraser** envoie chaque chaîne et remplace le travail déjà fait, dans la mesure où la tâche peut enregistrer. **Obsolète si identique à la source** envoie les chaînes dont la traduction est encore identique à la source. |
| **Tâche de simulation (Dry-run)** | Non | Appelle le modèle sans écrire la réponse dans PrestaShop. La tâche apparaît tout de même dans **Tâches**. Les fichiers du catalogue et les traductions en base restent inchangés. |

Étapes :

1. Réglez **Section**, **Source** et **Cibles**.
2. Pour **Thèmes**, choisissez un **Thème**. Pour **Modules installés**, choisissez un **Module**.
3. Choisissez les **Domaines** lorsque la liste est affichée. Maintenez Ctrl ou Cmd.
4. Appuyez sur **Estimer**. Vérifiez le nombre de chaînes, l'estimation de jetons, l'estimation du coût et l'**Échantillon**. Rien n'a été envoyé à Grok et rien n'a été enregistré. Message : **Estimation uniquement : N chaînes, ~N jetons, ~$N. Rien n'a été envoyé à Grok ni enregistré.**
5. Appuyez sur **Démarrer la tâche**. Le module ouvre cette tâche. Message : **La tâche n°N est en attente (N chaînes, est. $N). Elle n'a pas encore été lancée.**

Si un choix obligatoire manque, vous voyez l'un de ces messages :

- **Rien n'a été lancé. Sélectionnez au moins une langue cible.**
- **Rien n'a été lancé. Choisissez un thème.**
- **Rien n'a été lancé. Choisissez un module.**
- **Rien n'a été lancé. Aucune clé API Grok. Ouvrez Paramètres et collez la clé. Aucune tâche n'a été créée.**

### 3.5. Tâches

Ouvrez **Tâches**. La liste affiche toutes les tâches. Si elle est vide, vous lisez **Aucune tâche pour le moment.**

![Tâches, back-office en anglais. La liste des tâches avec statut, langues, progression, coût, employé et date.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-jobs.webp)

Colonnes : **#**, **Statut**, **Langues**, **Progression**, **Coût**, **Employé**, **Date** et **Ouvrir**.

Les statuts affichés sur cet écran restent en anglais : **pending**, **running**, **paused**, **cancelled**, **completed**, **completed_with_errors** et **failed**.

Appuyez sur **Ouvrir** sur une ligne. Le détail affiche le **Statut**, la progression en faits/total, les **échecs**, les **ignorés**, le coût, le numéro d'employé et **simulation (dry-run)** si cet interrupteur était activé. Une barre de progression se trouve sous ces informations.

Boutons de la tâche ouverte :

- **Traiter la tranche** traduit un lot puis s'arrête. Message : **Une tranche a été traitée. Vérifiez les lignes ci-dessous pour voir ce qui a été enregistré, ignoré ou a échoué.** S'il ne reste rien à faire, vous voyez : **La tâche n'a plus de chaînes en attente.**
- **Traitement auto** demande la tranche suivante jusqu'à la fin de la tâche ou jusqu'à son arrêt.
- **Mettre en pause** arrête les tranches suivantes. Message : **Tâche en pause. Elle ne traduira plus de chaînes tant que vous ne la reprendrez pas.**
- **Reprendre** remet une tâche en pause dans l'état en attente. Message : **La tâche est de nouveau en attente. Elle ne s'exécute pas toute seule. Appuyez sur Traiter la tranche, sur Traitement auto, ou laissez le cron l'appeler.**
- **Relancer les échecs** remet les lignes en échec dans la file. Message : **N éléments en échec relancés.**
- **Annuler** demande **Annuler cette tâche ?** et rétablit le texte précédent là où le module a gardé une copie. Message : **Annulation (rollback) : N traductions restaurées.**
- **CSV des erreurs** télécharge les lignes en échec.
- **Échecs uniquement** n'affiche que les lignes au statut **failed**.
- **File de révision** ouvre **Révision**.

Cet écran n'a pas de bouton pour abandonner une tâche. Si vous ne voulez pas qu'une tâche aille à son terme, laissez-la en **paused**.

Les colonnes du tableau des lignes sont **ID**, **Domaine**, **Locale**, **Statut**, **Source**, **Nouveau** et **Erreur**. Les statuts des éléments restent en anglais : **pending**, **processing**, **done**, **failed**, **skipped** et **rolled_back**.

Si la boutique atteint sa propre limite par minute pendant une tranche, la tâche se met en pause et la ligne d'erreur reste en anglais : **Rate limit — job auto-paused. Resume later.** Appuyez plus tard sur **Reprendre**, puis sur **Traiter la tranche**.

Une tâche de simulation appelle Grok et conserve la proposition sur la tâche. Elle n'écrit pas dans le catalogue.

### 3.6. Révision

Ouvrez **Révision**. C'est la file des éléments à relire issus des tâches en masse. La page indique **File de révision (score de qualité / indicateurs).** Si la file est vide, vous lisez **La file d'attente est vide.**

![Révision, back-office en anglais. La file à relire.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-review.webp)

Colonnes : **ID**, **Score**, **Domaine**, **Source**, **IA**, **Indicateurs**, **Approuver** et **Rejeter**.

Une ligne arrive ici lorsque le contrôle qualité lui attribue un score inférieur à 70, lorsque les variables ou le HTML ne correspondent pas, ou lorsque la traduction est nettement plus longue que la source. Si la tâche pouvait publier et que la chaîne a passé la validation, le catalogue contient peut-être déjà la proposition. **Approuver** et **Rejeter** ne modifient que cette file. Ils n'écrivent pas de nouvelle traduction et ne rétablissent pas l'ancienne. Après l'un ou l'autre bouton, le message **Révision mise à jour.** apparaît et la ligne quitte la file.

Le tableau de révision de **Manuel** est un autre écran. Il comporte le bouton **Enregistrer les approuvés**.

### 3.7. Catalogue

Ouvrez **Catalogue**. Cet onglet traduit les champs des produits, des catégories ou des pages CMS. Ce n'est pas le même catalogue que **International → Traductions**. Un seul appui traite au maximum 100 enregistrements.

![Catalogue, back-office en anglais. Entité, champs, langue source, langue cible, uniquement vides et commencer après l'ID.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-catalog.webp)

| Champ | Valeur par défaut | Effet |
|---|---|---|
| **Entité** | product | Enregistrements lus : **product**, **category** ou **cms**. Ces trois mots restent en anglais. La page se recharge et n'affiche que la liste des champs de ce type. Changer d'entité ne traduit rien. Message : **Affichage des champs pour {entité}. Rien n'a été traduit.** |
| **Champs** | tous les champs de l'entité | Les textes envoyés par ce lot. Maintenez Ctrl ou Cmd pour en sélectionner plusieurs. **Titre** correspond au nom du produit, au nom de la catégorie ou au titre de la page CMS. **Contenu** est le corps de la page CMS. Si les liens doivent rester inchangés, ne sélectionnez pas **URL réécrite**. Seuls les champs sélectionnés sont traduits. |
| **Langue source** | la liste des langues de la boutique | La langue à partir de laquelle les champs sont copiés. La langue source elle-même n'est pas modifiée. |
| **Langue cible** | la liste des langues de la boutique | La langue qui reçoit la traduction. Elle doit être différente de la source. Jusqu'à 100 enregistrements sont écrits. |
| **Uniquement vides** | Oui | Ignore les champs qui ont déjà du texte dans la langue cible. **Non** permet de remplacer ce texte lorsque la publication est autorisée. |
| **Commencer après l'ID** | 0 | Ignore les enregistrements jusqu'à cet ID. Laissez 0 pour commencer au premier enregistrement. Après un lot, le champ affiche le dernier ID lu. Appuyez de nouveau sur le bouton pour continuer. |

Champs produit : **Titre**, **Description courte**, **Description**, **Méta-titre**, **Méta-description**, **URL réécrite**.

Champs catégorie : **Titre**, **Description**, **Méta-titre**, **Méta-description**, **URL réécrite**.

Champs CMS : **Titre**, **Méta-description**, **Mots-clés méta**, **Contenu**, **URL réécrite**.

Appuyez sur **Traduire le lot (max 100)**. Le message final est **Catalogue terminé : N enregistrés, N échecs.** Sous le formulaire, vous voyez aussi les compteurs **Enregistré** et **échoué**.

- **Rien n'a été traduit. Aucune clé API Grok. Ouvrez Paramètres et collez la clé.**
- **Rien n'a été enregistré. Activez Autoriser la publication dans les Paramètres.**
- **Rien n'a été traduit. Les langues source et cible doivent être différentes.**
- **Rien n'a été traduit. Sélectionnez au moins un champ.**

### 3.8. Glossaire

Ouvrez **Glossaire**. La liste contient les mots que le modèle doit conserver ou rendre d'une façon fixe. Ajouter un terme ne réécrit pas les traductions déjà enregistrées, mais la traduction suivante utilisera la liste.

![Glossaire, back-office en anglais. Ajout d'un terme et le formulaire CSV.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-glossary.webp)

| Champ | Valeur par défaut | Effet |
|---|---|---|
| **Terme source** | vide | La formulation telle qu'elle apparaît dans la langue source. Saisissez le mot ou la phrase exacte, avec les majuscules si elles comptent. Obligatoire. |
| **Locale cible** | vide | Limite cette ligne à une locale cible, par exemple fr-FR. Si le champ est vide, la ligne s'applique à toutes les cibles. Une locale renseignée est ignorée pour les autres langues. |
| **Terme cible** | vide | La formulation qui doit apparaître dans la traduction. Ne laissez ce champ vide que si **Ne pas traduire** est activé. |
| **Ne pas traduire** | Non | **Oui** demande au modèle de recopier le terme source sans le modifier. Utilisez-le pour les noms de marque, les références SKU et les variables. **Non** signifie que le **Terme cible** est la traduction voulue. |

Appuyez sur **Ajouter**.

- **Terme de glossaire ajouté. Les traductions déjà enregistrées n'ont pas été modifiées.**
- **Rien n'a été ajouté. Saisissez un terme source.**

Les colonnes du tableau sont **Source**, **Locale**, **Cible**, **Ne pas traduire** (**Oui** ou **Non**) et **Supprimer**. Si le tableau est vide, vous lisez **Aucun terme dans le glossaire pour le moment.** **Supprimer** retire la ligne. Message : **Terme de glossaire supprimé.**

**CSV du glossaire**

| Champ | Valeur par défaut | Effet |
|---|---|---|
| **Fichier CSV** | vide | Le fichier doit comporter les colonnes source_term, target_locale, target_term et do_not_translate. **Importer CSV** ajoute les lignes lisibles. **Exporter CSV** télécharge la liste actuelle et ignore le champ de fichier. L'export ne modifie pas le glossaire. |

- **N lignes importées.**
- **Fichier CSV manquant.** Choisissez un fichier et appuyez de nouveau sur **Importer CSV**.
- **Impossible d'ouvrir le fichier CSV.** Enregistrez le fichier au format CSV, puis réessayez.

### 3.9. Exclusions

Ouvrez **Exclusions**. La liste contient les chaînes source que le module doit ignorer. Une chaîne qui correspond n'est pas envoyée à Grok et n'est pas supprimée de PrestaShop. Enregistrer un motif ne modifie pas les chaînes déjà enregistrées.

![Exclusions, back-office en anglais. Motif, type et le tableau des motifs.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-excludes.webp)

| Champ | Valeur par défaut | Effet |
|---|---|---|
| **Motif** | vide | Le texte comparé à chaque chaîne source. Obligatoire. |
| **Type** | exact | **exact** correspond à la chaîne entière, **prefix** au début, **contains** à un fragment, et **regex** est une expression régulière PHP appliquée exactement telle qu'elle est écrite. Testez d'abord un motif court. Un mauvais type peut exclure trop de chaînes, ou aucune. |

Appuyez sur **Ajouter**.

- **Motif d'exclusion ajouté. Les chaînes correspondantes seront ignorées lors de la prochaine exécution. Rien n'a été traduit pour l'instant.**
- **Rien n'a été ajouté. Saisissez un motif.**

Les colonnes du tableau sont **Motif**, **Type**, **Activé** et **Supprimer**. **Activé** affiche 1 lorsque le motif est utilisé. Si le tableau est vide, vous lisez **Aucun motif pour le moment.** **Supprimer** retire la ligne. Message : **Motif supprimé.**

### 3.10. Historique

Ouvrez **Historique**. C'est la liste complète des appels à Grok, y compris les tests de connexion et les appels bloqués avant l'envoi. Les graphiques et les dix dernières invites se trouvent sur le **Tableau de bord**, où **Tout voir** ouvre cet onglet.

![Historique, back-office en anglais. La liste des appels et effacer l'historique.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-history.webp)

Colonnes : **ID**, **Date**, **Statut**, **Type**, **Modèle**, **Langues**, **Envoyé**, **Reçu**, **Total**, **Temps**, **Prompt** et **Voir**.

**Type** est l'une des valeurs suivantes : **Manuel**, **Page de traduction**, **Tâche en masse**, **Catalogue**, **Test de connexion**, **Traduire** ou **Non envoyé**. **Statut** est **Succès** ou **Erreur**.

**Voir** ouvre l'invite et la **Réponse**, ainsi que **HTTP**, **Envoyé**, **Reçu** et **Total**. **Retour à la liste** revient au tableau. Si la ligne a été supprimée, la page affiche **Cette ligne d'historique n'existe plus.** Si le détail ne peut pas être chargé, la page affiche **Impossible de charger cette requête.**

**Précédent** et **Suivant** changent de page. La ligne indique **Page N / N**.

**Effacer l'historique** demande **Effacer l'historique enregistré ? Les traductions enregistrées restent en place.** La confirmation ne supprime que ces lignes. Message : **Historique effacé. Les traductions enregistrées n'ont pas été modifiées.** Si la liste est vide, vous lisez **Aucune requête pour le moment.**

**Jours de conservation des journaux** dans **Paramètres** supprime aussi les lignes plus anciennes que ce nombre de jours lorsqu'un nouvel appel est enregistré.

### 3.11. Mises à jour

Ouvrez **Mises à jour**. Cette page vérifie si un paquet plus récent est publié. Elle ne traduit rien.

![Mises à jour, back-office en anglais. Vérification manuelle, notifications automatiques et page produit.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-updates.webp)

| Champ | Valeur par défaut | Effet |
|---|---|---|
| **Vérification manuelle** | le bouton **Vérifier maintenant** | Interroge l'éditeur une fois. **Le module est à jour !** signifie que cette installation correspond au paquet actuel. **Nouvelle version disponible !** signifie qu'un paquet plus récent est publié. Téléchargez-le depuis la page du produit et installez-le via le **Gestionnaire de modules**. |
| **Notifications automatiques** | Activées | **Activées** permet au back-office d'afficher un avis lorsqu'un paquet plus récent existe. **Désactivées** masque cet avis. Appuyez sur **Enregistrer** pour conserver votre choix. La désinstallation du module ne supprime pas ce choix. |
| **Page produit** | un lien avec le nom du module | Ouvre la page du module. L'adresse figure à la section 7. |

Lorsqu'un paquet plus récent existe, le back-office peut aussi afficher **Nouvelle version disponible, consultez MyPresta.eu pour plus d'informations** avec le lien **Plus de détails dans le journal des modifications**.

### 3.12. Boutons sur International → Traductions

Ouvrez **International**, puis **Traductions**, et ouvrez un catalogue. Lorsque **Boutons de champ individuel — International → Traductions** est sur **Oui**, chaque champ dispose d'un bouton **Traduire**. Un clic remplit ce champ. Le bouton **Enregistrer** de PrestaShop enregistre toujours la page.

Lorsque **Cases à cocher de champ individuel — International → Traductions** est sur **Oui**, la page affiche aussi une barre **Traductions Grok**.

- **Source** est renseignée à partir des **Paramètres régionaux source (Locale)** des **Paramètres**. Si ce réglage est vide, la barre utilise en-US. Vous pouvez modifier le champ.
- **Cible** correspond à la langue du catalogue ouvert.
- **Tout cocher**, **Tout décocher** et **Cocher les vides** modifient les coches.
- **Traduire les vides** remplit les champs vides. **Traduire la sélection** remplit les champs cochés.
- L'indication affichée est **Remplit les champs. Enregistrez avec le bouton PrestaShop.**
- Pendant le traitement, la barre affiche **Traduction en cours…**, puis **Terminé** à la fin.
- **Sélectionné** indique combien de champs sont cochés.
- **Cochez au moins un champ.** apparaît lorsque vous appuyez sur **Traduire la sélection** sans rien avoir coché.
- **Remplissez d'abord le champ de la langue source.** apparaît lorsque le texte source est vide.
- **Le fichier d'e-mail de la langue source est introuvable.** apparaît sur un écran d'e-mail lorsque le fichier de courrier source manque.
- **Traduire les vides dans cette section** remplit les chaînes vides de la section affichée.

Ces boutons ne remplacent pas **Enregistrer** sur la page PrestaShop. **Autoriser la publication / l'enregistrement** ne les bloque pas, car ils se contentent de remplir le formulaire.

### 3.13. Boutons sur les formulaires produit, catégorie et CMS

Ouvrez un produit, une catégorie, une page CMS ou un autre formulaire du back-office qui comporte un champ par langue. Lorsque **Boutons de champ individuel — formulaires de boutique** est sur **Oui**, chacun de ces champs dispose d'un bouton **Traduire**. Un clic remplit ce champ à partir de la langue source du même formulaire.

![Formulaire produit, back-office en anglais. La barre Traductions Grok sous les champs de description.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-product.webp)

Lorsque **Cases à cocher de champ individuel — formulaires de boutique** est sur **Oui**, le formulaire affiche aussi la barre **Traductions Grok**.

- **Source** part des **Paramètres régionaux source (Locale)**, ou de en-US si ce réglage est vide.
- **Cible** liste les autres langues de la boutique, ainsi que **toutes les autres langues**.
- **Tout cocher**, **Tout décocher**, **Cocher les vides**, **Traduire les vides** et **Traduire la sélection** fonctionnent comme sur la page de traduction.
- L'indication affichée est **Remplit les champs. Enregistrez avec le bouton PrestaShop.**
- **Cochez au moins un champ.**, **Remplissez d'abord le champ de la langue source.** et **Le champ de la langue source n'est pas sur cette page.** indiquent ce qu'il faut corriger.
- **La cible n'est pas une langue de cette boutique.** signifie que la cible ne correspond à aucune langue de la boutique.
- La ligne au-dessus d'un champ peut indiquer **Traduire de** le nom de la source **vers** le nom de la cible.

Appuyez sur le bouton **Enregistrer** de PrestaShop sur ce formulaire pour conserver les champs remplis. La barre n'enregistre pas le produit par elle-même.

## 4. Boutique

Le thème de la boutique n'affiche rien de ce module. Le client ne voit ni bouton de traduction, ni formulaire, ni page d'état.

La seule adresse accessible hors du back-office est l'**URL CRON** des **Paramètres**, répétée sous le tableau de couverture du **Tableau de bord**. Copiez cette adresse dans le planificateur du serveur. Chaque appel traite une tranche de la première tâche en attente ou en cours, puis s'arrête. Ouvrir **Paramètres** ne l'appelle pas.

| Ce que vous voyez | Que faire |
|---|---|
| Une ligne JSON avec le résultat de la tranche | La tranche a été traitée. Ouvrez **Tâches** et lisez les lignes. |
| **No pending jobs** | Aucune tâche n'est en attente. Créez-en une dans **En masse (Bulk)**, ou la précédente est déjà terminée, en pause ou annulée. Ce texte reste en anglais. |
| **Forbidden** | L'adresse est fausse, ou le jeton a été régénéré lors d'une réinstallation. Copiez à nouveau l'**URL CRON**. Ne publiez pas l'adresse. Ce texte reste en anglais. |

N'ajoutez aucun paramètre personnel. L'adresse que vous copiez est exactement celle que lit le module.

## 5. Problèmes

**Pas de clé API Grok.** et **Ouvrir les paramètres** apparaissent sur chaque onglet. Collez la clé dans **Paramètres**, appuyez sur **Tester la connexion**, puis sur **Enregistrer**.

**La boutique a besoin d'au moins deux langues.** Ajoutez une langue dans **International → Localisation → Langues**, puis rouvrez le module.

**La connexion n'a pas pu être établie. Rien n'a été traduit.** La raison est indiquée juste après cette phrase. Vérifiez la clé, le modèle, et que le serveur atteint bien l'adresse de Grok. Ouvrez **Historique** et appuyez sur **Voir** sur la ligne en erreur.

**Monthly API budget has been exhausted.** Ce message reste en anglais. Augmentez **Budget USD / mois**, ou mettez 0 si vous ne voulez pas de plafond, puis appuyez sur **Enregistrer**. Le texte déjà enregistré reste en place.

**Grok rate limit (429). Try again later.** Ce message reste en anglais. Attendez, puis relancez la tranche. Si la tâche affiche **Rate limit — job auto-paused. Resume later.**, appuyez sur **Reprendre**, puis sur **Traiter la tranche**. Si cela se répète, baissez la **Taille du lot (Batch size)** ou allongez la pause entre les appels cron. **Limite de débit / min (Rate limit)** est le plafond propre à cette boutique, et Grok peut quand même refuser un appel.

**Rien n'a été enregistré. Activez Autoriser la publication dans les Paramètres.** Réglez **Autoriser la publication / l'enregistrement** sur **Oui**, appuyez sur **Enregistrer**, puis relancez l'enregistrement. Les icônes des formulaires ne font toujours que remplir le formulaire.

**Non enregistré à cause de variables ou de HTML invalides : N.** La proposition a modifié une variable ou une balise. Alignez la proposition sur la source, ou laissez la ligne décochée, puis appuyez de nouveau sur **Enregistrer les approuvés**.

**Rien n'a été traduit. Choisissez un thème, puis appuyez sur Filtrer.** ou **Choisissez un module.** La section a besoin de ce choix avant que la liste puisse se charger.

**Aucune chaîne ne correspond à ce filtre. Rien n'a été envoyé à Grok.** Désactivez **Uniquement vides**, effacez **Rechercher** ou choisissez un autre domaine.

**Fichier CSV manquant.** ou **Impossible d'ouvrir le fichier CSV.** Choisissez un CSV à quatre colonnes et appuyez de nouveau sur **Importer CSV**.

**Le fichier d'e-mail de la langue source est introuvable.** Dans **International → Traductions**, ouvrez la section e-mail d'une langue qui possède déjà le fichier, ou générez d'abord les traductions d'e-mails dans PrestaShop.

**Cette ligne d'historique n'existe plus.** La ligne a été effacée, ou supprimée par **Jours de conservation des journaux**. La traduction enregistrée reste présente dans la boutique.

L'entrée de menu manque, ou le back-office indique que le contrôleur est introuvable. Ouvrez le **Gestionnaire de modules**, trouvez **AI Translations with Grok** et appuyez sur **Configurer**. Cela recrée l'entrée du menu **International**. Si le module n'apparaît plus du tout dans la liste, réinstallez le ZIP.

L'installation s'arrête sur **Impossible de créer les tables du module.** L'utilisateur de la base de données ne peut pas créer de tables. Corrigez les droits de la base, puis appuyez de nouveau sur **Installer**. **Impossible d'ajouter l'onglet du menu.** signifie que l'entrée de menu n'a pas pu être créée. Après une installation réussie, appuyez sur **Configurer**, ou réinstallez.

## 6. Pour les développeurs

### 6.1. Vue d'ensemble

Nom technique `myaitranslationsgrok`, version `1.2.0`, auteur MyPresta.eu, onglet du module `administration`. Le nom dans la liste des modules et le libellé du menu **International** sont **AI Translations with Grok**. La classe est `myaitranslationsgrok`. Le minimum de `ps_versions_compliancy` est `1.7.0.0`.

`getContent()` appelle `ensureTab()` et redirige vers `AdminMyaitranslationsgrok`. Les réglages sont lus par `MyaitgkConfigService` (clés `MYAITGK_*`). La clé API est chiffrée et stockée dans `MYAITGK_API_KEY_ENC`. Les appels de traduction passent par `MyaitgkTranslateService`, puis par `MyaitgkGrokTranslationProvider`, qui envoie un JSON en POST à `https://api.x.ai/v1/chat/completions`. Les écritures dans le catalogue passent par `MyaitgkTranslationAdapter`. Les écritures pour les produits, les catégories et les CMS passent par `MyaitgkCatalogTranslateService`. Une traduction de catalogue enregistrée appelle `Tools::clearCache()`.

Le module ne définit ni `enable()` ni `disable()`. Le désactiver dans le **Gestionnaire de modules** ne lance aucun nettoyage supplémentaire. C'est la désinstallation qui supprime l'onglet de menu, les tables et les clés `MYAITGK_*`.

### 6.2. Fichiers

- `myaitranslationsgrok.php` - installation, désinstallation, hooks, onglet et configuration des boutons de champ.
- `controllers/admin/AdminMyaitranslationsgrokController.php` - chaque onglet du back-office et les actions AJAX.
- `controllers/front/cron.php` - traite une tranche de tâche pour l'adresse cron.
- `lib/updateChecker.php` - l'onglet **Mises à jour** et la vérification de version.
- `sql/install.php`, `sql/uninstall.php` - création et suppression des tables.
- `src/Admin/MyaitgkForms.php` - champs HelperForm et textes `desc`.
- `src/Admin/MyaitgkSectionHelp.php` - le panneau **Aide**.
- `src/Service/MyaitgkConfigService.php` - clés, liste des modèles, jeton cron.
- `src/Service/MyaitgkTranslateService.php` - budget, limite, glossaire, exclusions, enregistrement.
- `src/Service/MyaitgkBulkJobFactory.php` - crée une tâche depuis **En masse (Bulk)**.
- `src/Service/MyaitgkCatalogTranslateService.php` - lots de produits, de catégories et de CMS.
- `src/Service/MyaitgkDashboardService.php` - compteurs de couverture.
- `src/Service/MyaitgkRateLimiter.php` - plafond par minute stocké dans `var/rate_limit.json`.
- `src/Provider/MyaitgkGrokTranslationProvider.php` - la requête vers xAI.
- `src/Provider/MyaitgkPromptBuilder.php` - prompts système et utilisateur.
- `src/Job/MyaitgkJobWorker.php` - tranche, nouvel essai et e-mail de fin.
- `src/Job/MyaitgkJobRepository.php`, `src/Job/MyaitgkJobStatuses.php` - lignes de tâche et constantes de statut.
- `src/Quality/MyaitgkPlaceholderValidator.php`, `MyaitgkHtmlValidator.php`, `MyaitgkPsNativeValidator.php`, `MyaitgkEmailHtmlPipeline.php`, `MyaitgkQualityScorer.php` - contrôles avant enregistrement.
- `src/Glossary/MyaitgkGlossaryRepository.php`, `MyaitgkExcludePatternRepository.php` - glossaire et exclusions.
- `src/Audit/MyaitgkRequestLogRepository.php` - **Historique** et le rapport du tableau de bord.
- `src/Audit/MyaitgkSnapshotService.php` - copies d'annulation.
- `src/Security/MyaitgkApiKeyEncryptor.php` - chiffrement OpenSSL de la clé.
- `src/Adapter/MyaitgkTranslationAdapter.php`, `MyaitgkLegacyModuleCatalogue.php` - catalogues PrestaShop et modules classiques `translations/{iso}.php`.
- `views/templates/admin/configure.tpl` et `views/templates/admin/_partials/*.tpl` - les onglets.
- `views/js/admin.js`, `admin-help.js`, `history-charts.js`, `translations-tool.js`, `entity-fields.js`, `chart.min.js`.
- `views/css/admin.css`.
- `translations/{iso}.php` - textes du back-office.

### 6.3. Contrôleurs

`AdminMyaitranslationsgrok` étend `ModuleAdminController`. La classe parente de l'onglet est `AdminInternational` (solution de repli : `IMPROVE`). Le paramètre de requête est `myaitgk_tab` et accepte `dashboard`, `manual`, `bulk`, `jobs`, `review`, `catalog`, `glossary`, `excludes`, `logs`, `settings` et `updates`. Les valeurs inconnues reviennent à `dashboard`.

Les actions visibles sont les boutons d'envoi décrits au chapitre 3. Points d'administration supplémentaires utilisés par les scripts de la page : `ajax=1&action=HistoryDetail` pour **Voir**, l'interrogation du statut de tâche pour **Traitement auto**, et les actions de traduction de champs de `translations-tool.js` et `entity-fields.js`.

`MyaitranslationsgrokCronModuleFrontController` (`controllers/front/cron.php`) lit le paramètre `token`. Un jeton absent ou incorrect renvoie HTTP 403 avec `{"ok":false,"error":"Forbidden"}`. Un jeton correct sans `id_job` traite une tranche de la première tâche `pending` ou `running`. Avec `id_job`, c'est cette tâche qui est traitée. Lorsqu'aucune tâche n'attend, le corps de la réponse est `{"ok":true,"message":"No pending jobs"}`.

`job_action` sur l'onglet des tâches accepte `process`, `pause`, `resume`, `cancel`, `retry_failed`, `rollback` et `export_errors`. Le modèle affiche toutes ces actions sauf `cancel`.

### 6.4. Hooks

Enregistrés dans `install()` :

- `displayBackOfficeHeader` - corrige le libellé technique de l'onglet et charge les ressources du back-office.
- `actionAdminControllerSetMedia` - charge les mêmes ressources.

Sur `AdminMyaitranslationsgrok`, le module ajoute `views/css/admin.css`, `views/js/admin.js` et `views/js/admin-help.js`. Le **Tableau de bord** ajoute en plus `chart.min.js` et `history-charts.js`. Sur **International → Traductions**, il ajoute `translations-tool.js` lorsque les interrupteurs de cette page sont activés. Sur les autres formulaires du back-office, il ajoute `entity-fields.js` lorsque les interrupteurs des formulaires de boutique sont activés. Les deux scripts transmettent l'objet `myaitgkTr` à JavaScript.

Le module n'enregistre aucun hook côté boutique et n'expose pas de hook propre.

### 6.5. Surcharges

Le module ne surcharge aucune classe ni aucun contrôleur de PrestaShop.

### 6.6. Base de données

La désinstallation exécute `sql/uninstall.php` et supprime chacune des tables listées ci-dessous. L'installation utilise `CREATE TABLE IF NOT EXISTS` : une table restée en place est donc conservée.

| Table | Contenu |
|---|---|
| `myaitgk_glossary` | `source_term`, `target_locale`, `target_term`, `do_not_translate`, `id_shop`. |
| `myaitgk_exclude_pattern` | `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`. |
| `myaitgk_job` | Une tâche en masse : locales, `scope_json`, `policy_json`, `dry_run`, compteurs, coût, statut et employé. |
| `myaitgk_job_item` | Une chaîne d'une tâche : domaine, clé, thème, locales, source, texte précédent, nouveau texte, statut et avertissements. |
| `myaitgk_memory` | Traduction réutilisée, identifiée par `memory_hash`, le modèle et `hit_count`. |
| `myaitgk_usage_ledger` | Lignes quotidiennes de jetons et de coût, utilisées pour **Budget USD / mois**. |
| `myaitgk_snapshot` | Le texte précédant une écriture de tâche, utilisé par **Annuler**. |
| `myaitgk_api_log` | Contexte court de l'erreur. La clé API est retirée avant l'insertion. |
| `myaitgk_request` | Les lignes de l'**Historique** : invite, réponse, jetons, modèle, statut et durée. Le dépôt recrée la table si elle manque. |
| `myaitgk_review` | Lignes de la file avec `needs_review`, `approved` ou `rejected`, plus `quality_score` et `flags_json`. |
| `myaitgk_catalog_item` | Lignes des lots de catalogue : entité, champ, langues, source, texte précédent, nouveau texte et statut. |

`var/rate_limit.json` est un fichier, pas une table. La désinstallation ne supprime pas `mypresta_updates`, `update_myaitranslationsgrok` ni `updatev_myaitranslationsgrok`.

### 6.7. Clés et traductions

Préfixe `MYAITGK_`. `installDefaults()` n'écrit une clé que si elle est absente. Valeurs utilisées lorsque la clé manque :

| Clé | Valeur si absente |
|---|---|
| `API_KEY_ENC` | vide |
| `MODEL` | `grok-4.7` |
| `EXTRA_MODELS` | vide |
| `PROVIDER` | `grok` |
| `TONE` | `formal` |
| `CUSTOM_VOICE` | vide |
| `BATCH_SIZE` | `25` (enregistré entre 1 et 100) |
| `MONTHLY_BUDGET` | `0` |
| `SOURCE_LOCALE` | vide |
| `TEMPERATURE` | `0.2` (enregistré entre 0 et 1) |
| `DRY_RUN_SAMPLE` | `10` (enregistré entre 1 et 50) |
| `RATE_LIMIT_PER_MIN` | `60` |
| `LOG_RETENTION_DAYS` | `30` (enregistré au minimum à 1) |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` |
| `NOTIFY_EMAIL` | vide |
| `PERM_ALLOW_PUBLISH` | `1` |
| `ENTITY_FIELD_BUTTONS` | `1` |
| `ENTITY_BULK` | `1` |
| `TR_FIELD_BUTTONS` | `1` |
| `TR_BULK` | `1` |
| `MAX_TOKENS` | `0` (omis du corps de la traduction lorsqu'il vaut 0 ; envoyé comme `max_tokens` lorsqu'il est supérieur à 0) |
| `CRON_TOKEN` | 32 caractères hexadécimaux, régénéré lorsqu'il est vide |

L'enregistrement des **Paramètres** force `PROVIDER` à `grok` et supprime les anciennes clés `MYAITGK_DEEPL_API_KEY` et `MYAITGK_CLAUDE_API_KEY` si elles existent encore. Un champ de clé API vide ne vide pas `API_KEY_ENC`.

Les identifiants de modèles intégrés sont `grok-4.7`, `grok-4.6`, `grok-4.5`, `grok-4.3`, `grok-4.20-0309-non-reasoning` et `grok-4.20-0309-reasoning`. Un interrupteur absent est considéré comme activé : les boutiques installées avant l'existence de ces interrupteurs conservent donc leurs icônes.

Les descriptions de champs sont produites par `MyaitgkForms::help()` sous les intitulés **Ce que ça fait :**, **Comment configurer :** et **Effet :**. Les panneaux d'aide proviennent de `MyaitgkSectionHelp`. Les textes du back-office passent par `$this->l()`. Pour ajouter une langue, copiez `translations/en.php` vers `translations/{iso}.php`. Quelques messages sont écrits en anglais directement dans le PHP et s'affichent donc tels quels : `No Grok API key.`, `Monthly API budget has been exhausted.`, `Grok rate limit (429). Try again later.`, `Rate limit — job auto-paused. Resume later.`, ainsi que les messages JSON du cron.

### 6.8. Extensions

Le thème de la boutique n'a pas de modèle à surcharger. Le module ne rend aucun fichier Smarty côté boutique. Le balisage du back-office se trouve dans `views/templates/admin/`. Les boutons de champs sont injectés par `views/js/translations-tool.js` et `views/js/entity-fields.js`. Il n'existe aucun hook côté boutique auquel se raccorder.

## 7. Aide

Page du module : [AI Translations with Grok](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-grok.html).

Pour écrire au sujet de ce module, connectez-vous à votre compte client sur mypresta.eu, ouvrez le formulaire de contact et choisissez le sujet **Support for paid modules**. Le formulaire indique que la connexion est obligatoire pour les modules payants. Une fois connecté, sélectionnez ce module dans votre historique d'achats.
