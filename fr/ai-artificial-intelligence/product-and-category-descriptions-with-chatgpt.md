---
title: "My ChatGPT - génération de contenu par IA - documentation et manuel d'utilisation"
description: "Utilisez ce manuel pour configurer OpenAI, générer les textes du catalogue avec le module que vous possédez déjà et résoudre les problèmes lorsqu'une génération échoue."
sidebar:
  label: "My ChatGPT - génération de contenu par IA - documentation et manuel d'utilisation"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Product and Category Descriptions with ChatGPT sur MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/product-and-category-descriptions-with-chatgpt.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ai-artificial-intelligence/product-and-category-descriptions-with-chatgpt/)
>
> ---


## 1. Prérequis

Vérifiez ces points avant de connecter le module à OpenAI.

- Utilisez PrestaShop 1.6, 1.7, 8 ou 9 (jusqu'à 9.99.99).
- Utilisez PHP 7.0 ou plus récent. L'installateur refuse de continuer avec une version de PHP plus ancienne.
- Activez les extensions PHP cURL et JSON. Chaque appel à OpenAI et la vérification des mises à jour utilisent cURL. Activez aussi mbstring, car le nettoyage de texte de la recherche d'images et de l'écran de nouveau produit l'utilise.
- N'utilisez le champ facultatif **URL source facultative** de **Nouveau produit** que si PHP peut lire des pages web (le réglage `allow_url_fopen`) et si l'extension DOM est disponible. Sans eux, le champ est ignoré et seul votre brief est utilisé.
- Disposez de votre propre compte OpenAI et d'une clé API de platform.openai.com. La clé doit pouvoir appeler le modèle que vous choisissez. Vous payez chaque requête à OpenAI. Le module n'inclut aucun crédit.
- Laissez le serveur accéder à internet sur le port 443. La boutique contacte OpenAI à chaque génération et le serveur de mises à jour de MyPresta.eu pour la vérification des mises à jour.
- Ajoutez une tâche planifiée (CRON) sur le serveur uniquement si vous voulez que la génération s'exécute sans que personne ne clique. Les adresses cron ne font rien tant que le serveur ne les appelle pas.
- Aucun autre module PrestaShop n'est requis.
- Prévoyez du temps pour les gros catalogues. Chaque champ de chaque langue est une requête distincte vers OpenAI. Une exécution en masse sur 500 produits avec quatre champs et deux langues envoie 4000 requêtes, l'une après l'autre, et occupe l'onglet de votre navigateur. Commencez par de petits lots de test ou utilisez des lots cron pour les gros catalogues.

## 2. Installation

1. Ouvrez **Modules**, puis **Gestionnaire de modules**.
2. Cliquez sur **Téléverser un module** et téléversez le fichier ZIP.
3. Cliquez sur **Installer** pour **Mon ChatGPT - Génération de contenu par IA**.
4. Ouvrez **Modules** dans le menu de gauche. Une nouvelle entrée **Générateur de Contenu IA** y apparaît. Cliquez dessus pour ouvrir le **Tableau de bord** du module. **Configurer** dans le **Gestionnaire de modules** ouvre le même endroit.

L'installation effectue les opérations suivantes :

- Elle ajoute l'entrée de menu **Générateur de Contenu IA** sous **Modules**. Tous les autres écrans du module s'ouvrent depuis le menu supérieur propre au module et n'ont pas d'entrées de menu séparées.
- Elle crée deux tables : une pour les modèles de prompt et une pour l'historique de chaque génération.
- Elle ajoute 16 modèles de prompt prêts à l'emploi (noms de produits, descriptions, titres méta, descriptions méta et mots-clés). Tous sont activés.
- Elle crée de longues valeurs secrètes pour les appels internes du module et pour les deux adresses cron.
- Elle désactive le filtre HTML de toute la boutique (HTMLPurifier). Les descriptions et les textes de catégories conservent alors leurs balises HTML, mais le même interrupteur est désactivé pour tous les autres textes de la boutique. Réactivez-le dans les réglages de la boutique si vous ne le souhaitez pas.
- Elle ne vide pas le cache de PrestaShop. Videz-le sous **Paramètres avancés**, puis **Performances**, uniquement si d'anciens styles ou un ancien écran restent visibles.

Si l'installateur affiche « Ce module nécessite PHP 7.0.0 ou une version plus récente », mettez d'abord PHP à jour. S'il affiche « Impossible de créer les tables de la base de données du module. », vérifiez que l'utilisateur de la base de données peut créer des tables, puis installez à nouveau.

Désinstallation :

- Elle supprime les entrées de menu, les deux tables (tous les modèles de prompt et tout l'**Historique** sont perdus) et presque tous les réglages du module, y compris la clé API et les secrets cron.
- Elle ne réactive pas le filtre HTML. Réactivez-le vous-même si vous le souhaitez.
- Elle ne supprime aucun texte de produit, texte de catégorie ni photo de produit créé par le module. Ils restent dans le catalogue.
- Elle laisse quelques restes inoffensifs dans la configuration de la boutique (le choix de catégories cron enregistré, les dernières valeurs de filtre de **Générer** et les valeurs de la vérification des mises à jour).
- Une nouvelle installation crée de nouveaux secrets, un Historique vide et de nouveau les 16 modèles par défaut. Les anciennes adresses cron cessent de fonctionner, copiez-les donc à nouveau.

## 3. Configuration et travail dans le back office

Ouvrez **Modules**, puis **Générateur de Contenu IA**. Le menu supérieur du module comporte ces entrées : **Tableau de bord**, **Paramètres**, **Générer**, **Nouveau produit**, **Cron**, **Historique**, **Images** et, à droite, **Mises à jour**. Un bouton rond **Aide** en bas de chaque écran du module ouvre une courte explication de l'écran où vous vous trouvez.

Les captures d'écran de ce manuel proviennent du back office en anglais. Les noms des boutons, champs et onglets sont donnés dans ce manuel en français. Dans la description de chaque capture, le libellé anglais de l'écran figure entre parenthèses.

Suivez ce processus :

1. Ouvrez **Paramètres**, puis **ChatGPT**. Collez la clé API OpenAI et choisissez un modèle. Cliquez sur **Enregistrer**.
2. Facultatif : ouvrez **Studio** et définissez la voix de la marque, le public, le ton, le glossaire, les mots interdits, le budget mensuel et le contrôle qualité.
3. Ouvrez **Modèles de prompt**. Passez en revue les 16 modèles, modifiez-les ou ajoutez les vôtres, et ne laissez activés que ceux que votre équipe doit utiliser.
4. Générez du texte de la manière qui convient à la tâche :
   - Un produit : ouvrez le produit, l'onglet **Modules**, et utilisez **Générer**, **Simuler** ou **Photos**. Les petits boutons **Générer avec l'IA** à côté des champs de description et méta fonctionnent aussi.
   - Beaucoup de produits ou de catégories à la fois : ouvrez **Générer**, construisez une liste avec des filtres et appuyez sur **Exécuter**.
   - Un nouveau produit à partir d'un bref brief : ouvrez **Nouveau produit**.
   - Des lots planifiés sans clic : ouvrez **Cron** et ajoutez l'adresse au planificateur du serveur.
5. Consultez l'**Historique** pour voir chaque prompt, réponse, erreur et nombre de jetons. Consultez le **Tableau de bord** pour les totaux et les graphiques.

Le module n'a pas de statuts de type commande. Un modèle de prompt est **Activé** ou **Désactivé**. Chaque appel de l'**Historique** est **Succès** ou **Erreur**. Une exécution en masse ou cron se termine lorsque le dernier élément a été écrit, et le texte est enregistré sur le produit ou la catégorie dès l'arrivée de chaque réponse.

Si **CTA de la barre supérieure d'administration** est activé, un petit bouton en forme de baguette magique **Mon ChatGPT** figure dans la barre supérieure de chaque page du back office. Il ouvre une petite boîte avec une liste de modèles, un champ de texte et **Générer**. Il fonctionne comme l'**Aire de jeu** (section 3.6) : la réponse s'affiche dans la boîte et rien n'est enregistré dans le catalogue.

Dans la liste des produits de **Catalogue**, **Produits**, le module ajoute aussi un bouton **Mon ChatGPT** qui ouvre **Générer**.

### 3.1 Tableau de bord

Ouvrez **Générateur de Contenu IA**, **Tableau de bord**. Cette page est un rapport. Elle n'écrit jamais de texte de produit ni de catégorie.

![Tableau de bord (Dashboard)](https://mypresta.eu/docs/images/docs/mychatgpt-dashboard.webp)

- Cliquez sur un bouton de période : **Aujourd'hui**, **7 jours**, **30 jours** (ouvert par défaut), **90 jours**, **Ce mois-ci** ou **Depuis toujours**. Ou saisissez **De** et **À** et cliquez sur **Appliquer**.
- La ligne **Service actif** affiche ChatGPT et le modèle enregistré dans **Paramètres**, **ChatGPT**.
- Lisez les cartes **Requêtes**, **Succès**, **Erreurs**, **Jetons envoyés** et **Jetons reçus** pour la période choisie. **Requêtes** compte chaque appel enregistré dans l'**Historique**. **Erreurs** compte ceux qui ont échoué. Les jetons envoyés correspondent à la taille de votre instruction, les jetons reçus à la taille de la réponse.
- Lisez les graphiques **Requêtes et erreurs**, **Jetons envoyés et reçus** et **Requêtes par modèle**.
- Des graphiques vides signifient que rien n'a été généré sur cette période. Changer les dates ne fait que redessiner la page. Rien n'est supprimé.

### 3.2 Paramètres – Général

Ouvrez **Paramètres**, puis **Général**. Cliquez sur **Enregistrer** après toute modification. Vous voyez « Paramètres mis à jour ».

![Paramètres généraux (General settings)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-general.webp)

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| **Mode production** | Non | Indique que le module fonctionne sur la vraie boutique et non dans une configuration d'essai. Activez-le en production. Désactivé, les mêmes outils restent disponibles mais le module signale qu'il ne s'agit pas de la configuration de production. |
| **Mode débogage** | Non | Écrit des détails techniques supplémentaires lorsqu'un appel à OpenAI échoue. Activez-le seulement pendant que vous étudiez un problème. Les détails apparaissent sous **Paramètres avancés**, **Logs**. Les clients ne les voient jamais. |
| **Délai d'attente API (secondes)** | 120 | Durée maximale d'un appel à OpenAI avant que le module abandonne. 120 convient aux descriptions normales. Augmentez jusqu'à 600 pour les textes longs ou les modèles lents. Les valeurs inférieures à 10 sont relevées à 10, celles supérieures à 600 abaissées à 600, et une valeur vide ou non numérique devient 120. Un délai court échoue rapidement et écrit une erreur dans l'Historique. |
| **Historique d'édition du produit** | Oui | Ajoute sur la page du produit une liste **Historique** avec un bouton **Restaurer** pour que les rédacteurs puissent remettre un ancien texte. Désactivé masque cette liste. Les lignes restent dans l'**Historique** dans tous les cas. |
| **CTA de la barre supérieure d'administration** | Oui | Ajoute le raccourci **Mon ChatGPT** à la barre supérieure du back office sur toutes les pages. Désactivé supprime uniquement ce bouton. L'entrée de menu **Générateur de Contenu IA** reste. |
| **Formulaire de la page d'édition du produit** | Oui | Affiche le panneau du générateur (**Générer**, **Simuler**, **Photos**) dans l'onglet **Modules** du produit et les boutons **Générer avec l'IA** à côté des champs de description et méta. Désactivé les masque. Désactivez-le lorsque seules la génération en masse et le cron doivent être utilisés. |
| **Recherche d'images IA** | Oui | Permet à un rédacteur de demander au modèle des pages web qui montrent probablement des photos du produit courant. Activé affiche l'onglet **Photos** sur le produit. Désactivé le masque. Rien n'est téléchargé tant que quelqu'un n'a pas confirmé des photos. Le même interrupteur se trouve dans **Images** (section 3.12). |
| **Prompt de recherche d'images IA** | Long texte par défaut | L'instruction envoyée lorsque quelqu'un cherche des photos. Par défaut, elle demande exactement cinq adresses de pages sous forme de liste simple, en privilégiant les pages de fabricants, les grands revendeurs et les catalogues. Les mots `{product_name}` et `{product_description}` sont remplacés par le produit courant. Conservez la demande d'une liste simple d'adresses. Un prompt précis renvoie des pages pertinentes. Un prompt vague renvoie des liens sans rapport. Le même texte se trouve dans **Images**. |

### 3.3 Paramètres – ChatGPT

Ouvrez **Paramètres**, puis **ChatGPT**. Le formulaire s'intitule **Paramètres OpenAI**. Chaque génération, y compris les boutons du produit, les exécutions en masse et le cron, utilise ces valeurs. Cliquez sur **Enregistrer**. Vous voyez « Paramètres OpenAI mis à jour ».

![Paramètres ChatGPT (ChatGPT settings)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-chatgpt.webp)

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| **Clé API OpenAI** | Vide | Le secret qui permet à cette boutique d'appeler votre compte OpenAI. Collez la clé créée sur platform.openai.com dans votre compte OpenAI. Les espaces autour sont supprimés à l'enregistrement. Laissez la case intacte pour conserver la clé déjà enregistrée. Une clé vide ou erronée fait échouer chaque génération, et l'erreur est écrite dans l'Historique. Si vous enregistrez une nouvelle clé de moins de 10 caractères alors qu'aucune clé n'est enregistrée, vous voyez « Le champ Clé API OpenAI est invalide ! ». |
| **Modèle** | gpt-3.5-turbo | Le modèle ChatGPT qui écrit le texte. La liste contient les modèles intégrés (gpt-4o, gpt-4o-mini, gpt-4-turbo, gpt-4, gpt-3.5-turbo, o4-mini, o3-mini, o1-mini et d'autres) et les modèles que vous avez ajoutés. Choisissez-en un et cliquez sur **Enregistrer**. Un modèle que votre clé ne peut pas utiliser renvoie une erreur OpenAI au lieu d'un texte. Un modèle vide donne « Le champ Modèle OpenAI est invalide ! ». |
| **Ajouter un modèle ChatGPT** | Vide | Ajoute un nom de modèle absent de la liste intégrée. Saisissez le nom exact de votre compte OpenAI (par exemple `gpt-4.1`) et cliquez sur **Ajouter un modèle**. Le nom apparaît dans **Modèle** et devient le modèle actif. **Supprimer** à côté d'un nom ajouté le supprime. Les noms intégrés ne peuvent pas être supprimés. Si vous supprimez le modèle ajouté qui est actif, le module bascule sur gpt-4o. Messages : « Modèle ajouté. », « Ce modèle est déjà intégré. », « Modèle supprimé. », « Les modèles intégrés ne peuvent pas être supprimés. », « Saisissez un identifiant de modèle tel que gpt-4.1. ». |
| **Jetons max** | 3200 | La limite supérieure de la longueur d'une réponse, comptée en jetons et non en mots. Utilisez environ 256 pour une description méta et 1000 ou plus pour une description HTML complète. Trop bas tronque la réponse. Trop haut autorise un texte long et alourdit votre facture OpenAI. Une valeur de 0 est traitée comme vide et remplacée par 256. |
| **Température** | 0.7 | Avec quelle liberté le modèle choisit les mots. Restez entre 0 et 1. Utilisez environ 0.2 pour les caractéristiques techniques et les textes méta, et environ 0.7 pour les descriptions. Modifiez cette valeur ou **Top P**, pas les deux. Les valeurs basses répètent une structure similaire. Les valeurs hautes varient davantage et peuvent s'éloigner du brief. Une valeur de 0 est traitée comme vide et remplacée par 0.7. |
| **Top P** | 1 | Une autre façon de limiter le caractère surprenant du mot suivant. 1 prend en compte toute la plage. Laissez 1 si vous avez déjà réglé la **Température**. Une valeur plus basse, comme 0.9, donne un vocabulaire plus serré. Une valeur de 0 est remplacée par 1. |
| **Valeur de la pénalité de fréquence** | 0 | Réduit les expressions qui se répètent dans une même réponse. Utilisez 0, sauf si les descriptions recopient sans cesse la même phrase ; essayez alors 0.3–0.6. Plage autorisée de -2 à 2. Elle ne compare pas les produits entre eux. |
| **Valeur de la pénalité de présence** | 0 | Pousse la réponse vers de nouveaux sujets. Utilisez 0 par défaut. Essayez un petit nombre positif si chaque paragraphe dit la même chose. Plage autorisée de -2 à 2. Certains modèles plus récents ignorent ce champ. |

Le module apprend de lui-même quels réglages un modèle refuse (certains modèles de raisonnement rejettent la température ou les pénalités) et cesse ensuite de les lui envoyer.

### 3.4 Paramètres – Studio

Ouvrez **Paramètres**, puis **Studio**. Le Studio ajoute des règles maison à chaque prompt : boutons du produit, exécutions en masse, cron et aire de jeu. Les cases vides sont ignorées. Cliquez sur **Enregistrer le studio**. Vous voyez « Paramètres du studio enregistrés. ». Le texte déjà présent dans le catalogue n'est pas réécrit.

![Paramètres du Studio (Studio settings)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-studio.webp)

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| **Voix de la marque** | Vide | Indique au modèle qui parle, afin que le texte corresponde à votre boutique et non à un assistant générique. Écrivez un bref brief, par exemple « atelier spécialisé, phrases courtes, pas de superlatifs ». Chaque génération ultérieure part de cette voix. |
| **Public** | Vide | Nomme le lecteur pour lequel écrire, par exemple « installateurs professionnels » ou « acheteurs novices ». Les réponses emploient un vocabulaire et des exemples adaptés à ce lecteur. |
| **Ton** | Vide | L'humeur de la rédaction : formel, chaleureux, technique. Un ou deux mots suffisent. Cela ne change ni le modèle ni la température. |
| **Glossaire** | Vide | Noms de marques, matériaux et orthographes que le modèle doit recopier exactement. Mettez un terme par ligne. Le nouveau texte privilégie ces orthographes. Les termes non listés peuvent encore être reformulés. |
| **Mots interdits** | Vide | Mots et expressions qui ne doivent pas apparaître dans une réponse enregistrée. Un par ligne. La liste ne fonctionne que si le **Contrôle qualité** est activé. Une réponse contenant l'une des lignes (même à l'intérieur d'un mot plus long) est rejetée, n'est pas écrite dans le produit et est enregistrée dans l'Historique comme erreur. |
| **Budget de génération mensuel** | 0 | Le nombre maximal de générations réussies que la boutique peut exécuter pendant le mois calendaire en cours. Saisissez un nombre entier. 0 signifie aucune limite. Le compteur repart à zéro le premier jour du mois. Quand le plafond est atteint, les nouvelles générations s'arrêtent avec un message de budget. Les appels échoués ne sont pas comptés. L'aire de jeu, les boutons du produit, les exécutions en masse et le cron comptent tous. |
| **Contrôle qualité** | Oui | Vérifie chaque réponse par rapport aux **Mots interdits** avant que quoi que ce soit soit enregistré. Activé bloque une réponse correspondante. Désactivé enregistre la réponse même si elle contient un mot de la liste. |

### 3.5 Paramètres – Modèles de prompt

Ouvrez **Paramètres**, puis **Modèles de prompt**. Un modèle est une instruction enregistrée que les rédacteurs choisissent par son titre au lieu de retaper le même brief. Le titre n'est qu'une étiquette pour la liste déroulante. Le modèle reçoit le texte du prompt. Les modèles activés apparaissent dans le panneau du produit, dans le générateur en masse et dans le formulaire cron. Les modèles désactivés restent dans la liste mais ne sont pas proposés (le formulaire cron les liste encore, choisissez donc un modèle activé).

![Modèles de prompt (Prompt templates)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-templates.webp)

La liste **Modèles de prompt** affiche **ID**, **Titre**, **Prompt**, **Statut** et **Horodatage**, du plus récent au plus ancien, 50 par page.

- Cliquez sur le bouton vert **+** pour créer un modèle.
- Cliquez sur la marque de statut d'une ligne pour basculer un modèle entre activé et désactivé.
- Utilisez **Modifier** ou **Supprimer** sur une ligne. Cochez plusieurs lignes et utilisez l'action groupée **Supprimer** (vous devez confirmer « Êtes-vous sûr de vouloir supprimer les prompts sélectionnés ? »).

Le formulaire **Générer un modèle de prompt** :

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| **Statut** | Désactivé pour un nouveau modèle | Affiche ou masque ce modèle dans les listes déroulantes de la page du produit, de la génération en masse et du cron. Activez les modèles que votre personnel doit utiliser. Désactivez un brouillon plutôt que de le supprimer. |
| **Titre du prompt** | Vide (obligatoire) | Le nom que les rédacteurs voient dans la liste déroulante, par exemple « Description HTML avec caractéristiques ». Il n'est pas envoyé au modèle. |
| **Contenu du prompt** | Vide (obligatoire) | L'instruction envoyée au modèle. Rédigez-la comme vous briefez un rédacteur : longueur, HTML, langue. Les variables sont remplies à partir de l'élément en cours d'écriture. Les guillemets doubles sont changés en guillemets simples à l'enregistrement. |

Cliquez sur **Enregistrer le prompt**. Vous voyez « Modèle d'invite ajouté avec succès ! » ou « Modèle d'invite mis à jour avec succès ! ». **Retourner aux paramètres du module** ramène à la liste. La suppression affiche « Modèle d'invite supprimé. ».

Variables utilisables dans un modèle :

| Pour | Variables | Remplacées par |
|---|---|---|
| Produits | `{product_name}`, `{product_description}`, `{product_description_short}`, `{product_tags}`, `{product_reference}`, `{product_ean13}`, `{product_weight}` | La valeur de ce produit dans la langue en cours d'écriture. |
| Produits | `{product_brand}`, `{product_default_category}`, `{product_category_description}`, `{product_categories}` | Les données de marque et de catégorie du produit. |
| Produits | `{product_attributes}`, `{product_features}`, `{product_feature_values}`, `{product_images}` | Les déclinaisons séparées par des virgules, les noms de caractéristiques, les paires nom:valeur de caractéristiques et les adresses des photos du produit. |
| Catégories | `{category_name}`, `{category_description}`, `{category_parent_name}` | La catégorie et sa catégorie parente. |
| Produits et catégories | `{shop_name}`, `{shop_url}`, `{shop_language}`, `{shop_country}`, `{shop_currency}` | Les données de votre boutique. |

Les 16 modèles par défaut sont **Nom du produit 1–2**, **Description du produit 1–7**, **Méta-titre du produit 1–3**, **Méta-description du produit 1–3** et **Mots-clés du produit**. Certains contiennent des formulations d'exemple (par exemple une montre connectée). Passez-les en revue avant la première exécution en masse.

### 3.6 Paramètres – Aire de jeu

Ouvrez **Paramètres**, puis **Aire de jeu**. L'aire de jeu est un brouillon qui appelle le modèle actif et affiche la réponse sur la page. Utilisez-la pour essayer un prompt avant de l'enregistrer comme modèle, ou pour vérifier que votre clé API fonctionne.

![Aire de jeu (Playground)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-playground.webp)

1. Saisissez une instruction dans la case. L'indication grise indique « Demandez au modèle n'importe quoi sur votre catalogue ».
2. Cliquez sur **Générer**.
3. Lisez la réponse et le nombre de jetons sous le bouton.

L'appel utilise le modèle, les valeurs d'échantillonnage et les règles du Studio que vous avez enregistrés. La réponse est stockée dans l'Historique. Aucun produit, catégorie ni champ méta n'est modifié. Écrivez de vrais noms et détails : les variables entre accolades ne sont pas remplies dans l'aire de jeu.

### 3.7 Générer – Produits

Ouvrez **Générer**, puis le sous-onglet **Produits**. Travaillez en deux étapes. L'étape 1 construit seulement une liste. Rien n'est envoyé à OpenAI et rien n'est enregistré comme réglage de la boutique.

![Générer des produits (Generate products)](https://mypresta.eu/docs/images/docs/mychatgpt-generate-products.webp)

Étape 1 – le formulaire **Filtrer les produits à mettre à jour**. Tous les filtres se combinent. Un filtre laissé vide est ignoré.

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| **Catégories de produits** | Rien de coché | Conserve les produits des catégories cochées (y compris les produits dont la catégorie par défaut est l'une d'elles). Une arborescence vide désactive ce filtre. |
| **Marque** | Sélectionner une marque | Conserve les produits d'un fabricant. L'option vide inclut toutes les marques. |
| **Statut du produit** | Actif | **Actif** conserve les produits en vente, **Désactivé** conserve les brouillons, **Les deux** conserve tout. |
| **Stock du produit** | Tous les produits | **Uniquement les produits en stock** supprime les produits sans quantité disponible. **Tous les produits** ignore le stock. |
| **Mettre à jour uniquement** | Tout mettre à jour | **Produits qui n'ont pas encore été mis à jour avec du contenu OpenAI** sert pour un premier passage (produits sans ligne dans l'Historique). **Produits qui ont déjà été mis à jour avec du contenu OpenAI** sert pour la réécriture. **Tout mettre à jour** ignore l'Historique. |
| **ID des produits** | Vide | Uniquement ces numéros de produits, séparés par des virgules, par exemple 12,45,103. |
| **Référence du produit** | Vide | Uniquement les produits ayant ces codes de référence, séparés par des virgules. |
| **Date d'ajout du produit : de** | Vide | Exclut les produits créés avant cette date et cette heure. |
| **Date d'ajout du produit : à** | Vide | Exclut les produits créés après cette date et cette heure. |
| **ID produit minimum** | Vide | Ignore les produits dont le numéro est plus petit. |
| **ID produit maximum** | Vide | Ignore les produits dont le numéro est plus grand. |
| **Limite de produits** | Vide | Le nombre maximal de produits chargés dans la liste, par exemple 20. La liste n'en affiche jamais plus, si bien qu'une exécution ne peut pas parcourir tout le catalogue par accident. |

Cliquez sur **Passer à l'étape suivante**. **Paramètres du module** ouvre la configuration du module.

Étape 2 – le panneau **Génération de produits en masse** et le tableau des produits (**ID**, **Référence**, **Résultat**) :

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| **Modèle** | Choisir un modèle | Remplit la case du prompt à partir d'un modèle activé. Vous pouvez aussi saisir votre propre prompt. Le titre n'est pas envoyé. Si la case reste vide, le module utilise un brief standard pour chaque champ. |
| Case du prompt | Vide | L'instruction pour chaque produit du tableau. Si vous saisissez un seul texte, le même texte est utilisé pour chaque champ choisi ; exécutez donc un champ à la fois lorsque les champs demandent des formulations différentes. |
| **Ce qu'il faut générer** | Descriptions | **Descriptions** écrit la description longue et la description courte. **Titre méta et description méta** écrit les deux champs méta. **Descriptions et méta ensemble** écrit les quatre. Chaque champ est une requête distincte. Les noms et les mots-clés sont écrits depuis la page du produit, pas d'ici. |
| **Texte existant** | Remplacer | **Remplacer** écrase. **Ignorer si rempli** laisse un champ rempli tranquille et n'appelle pas le modèle pour lui. **Ajouter au-dessus** et **Ajouter en dessous** conservent l'ancien texte et y joignent le nouveau. |
| **Langues** | Votre langue actuelle cochée | Cochez chaque langue à écrire. Chaque langue cochée est générée séparément. Les langues non cochées conservent leur texte. |

Cliquez sur **Exécuter sur la liste ci-dessous**. La ligne d'état affiche la progression, par exemple « 3 / 40 – description ». Chaque ligne affiche ses propres résultats dès que ce produit est terminé, par exemple « description: success Content successfully generated and updated to product. », « description_short: skipped Product skipped. » ou « meta_title: error … » avec la raison. À la fin, vous voyez « Finished N products. ». Sans langue cochée, vous voyez « Select at least one language. ».

Gardez l'onglet du navigateur ouvert jusqu'à la fin de l'exécution. Le fermer arrête l'exécution, et les produits déjà écrits restent enregistrés. Pour continuer, reconstruisez la liste avec **Mettre à jour uniquement** réglé sur les produits non mis à jour. Un échec sur un champ n'annule pas les champs déjà enregistrés. Commencez par une petite **Limite de produits**, par exemple 20, et vérifiez d'abord la rédaction.

### 3.8 Générer – Catégories

Ouvrez **Générer**, puis le sous-onglet **Catégories**. Les deux étapes fonctionnent comme sur l'écran des produits.

![Générer des catégories (Generate categories)](https://mypresta.eu/docs/images/docs/mychatgpt-generate-categories.webp)

Étape 1 – le formulaire **Filtrer les catégories à mettre à jour** :

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| **Catégories** | Rien de coché | Choisit les catégories pour l'étape suivante. Une arborescence vide ne restreint pas la liste par catégorie ; la liste contient alors toutes les catégories ayant le statut choisi, y compris **Accueil** et la catégorie racine. Cochez les catégories souhaitées. |
| **Statut de la catégorie** | Actif | **Actif**, **Désactivé** ou **Les deux**. |

Cliquez sur **Passer à l'étape suivante**.

Étape 2 – le panneau **Génération de catégories en masse** et le tableau des catégories (**ID**, **Résultat**) :

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| Case du prompt (première case) | Vide | L'instruction envoyée pour chaque catégorie. Décrivez le ton, la longueur et le HTML. Nommez le sujet dans le texte. Cette case n'insère pas de variables de produit. Ce panneau n'a pas de sélecteur de modèle. |
| Liste des champs | Description | Le champ à écrire : **Description**, **Nom**, **Titre méta**, **Description méta** ou **Description additionnelle**. Seul ce champ est enregistré. |
| Liste du texte existant | Remplacer | **Remplacer** écrase. **Ignorer si rempli** laisse un champ rempli tranquille et n'appelle pas le modèle pour cette catégorie. |
| Liste des langues | Votre langue actuelle | Une langue. Relancez pour une autre langue. |

Cliquez sur **Exécuter sur les catégories ci-dessous**. Les résultats apparaissent par ligne comme sur l'écran des produits. Une catégorie sans champ **Description additionnelle** dans votre version de PrestaShop affiche « Error! This PrestaShop version does not support the category Additional Description field. ».

Sous le tableau, l'écran affiche aussi le formulaire **Générer le contenu des catégories**. Son introduction dit « This form writes the filtered categories. Press Generate content to start. Each category is saved as soon as its reply arrives. » Dans cette version, ce formulaire ne lance pas d'exécution. Utilisez **Exécuter sur les catégories ci-dessous** au-dessus. Le formulaire comporte ces champs :

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| **Champ à mettre à jour** | Description | Le champ de catégorie que ce formulaire réécrirait : **Nom de la catégorie**, **Description**, **Titre méta**, **Description méta** ou **Description additionnelle**. Seul ce champ est envoyé au modèle et enregistré. Les autres champs restent inchangés. Description et méta sont des exécutions séparées. |
| **Données existantes** | Conserver les données existantes et ajouter le nouveau contenu généré en haut | Ce qui se passe lorsque le champ choisi contient déjà du texte : **Conserver les données existantes et ajouter le nouveau contenu généré en haut**, **Conserver les données existantes et ajouter le nouveau contenu généré à la fin**, **Conserver les données existantes et ignorer la catégorie** ou **Supprimer les données et ajouter le nouveau contenu généré**. Remplacer modifie le texte stocké. Ignorer n'appelle pas le modèle pour une catégorie qui a déjà ce champ. Ajouter conserve les deux versions dans un seul champ. |
| **Langue** | Première langue de la liste | La version linguistique qui est écrite. Seule cette langue change. |
| **Prompt de contenu** | Vide (obligatoire) | L'instruction pour chaque catégorie de la liste. Décrivez le ton, la longueur et le HTML. Nommez le sujet de la catégorie dans le texte, car les variables de produit ne sont pas insérées. |
| **Délai entre les appels API** | Vide | Une pause en secondes entre une catégorie et la suivante, afin de ne pas atteindre la limite de débit d'OpenAI. Utilisez 1 ou 2 avec une clé de niveau bas. Mettez 0 pour envoyer la requête suivante immédiatement. Le panneau **Exécuter** ci-dessus n'utilise pas cette pause. |

Les boutons **Générer le contenu** et **Retour au filtre des catégories** ne génèrent pas de texte. **Générer le contenu** enregistre seulement les valeurs saisies et affiche de nouveau le filtre. **Paramètres du module** ouvre la configuration du module.

### 3.9 Nouveau produit

Ouvrez **Nouveau produit**. Le panneau **Créer un produit à partir d'un brief** demande au modèle un brouillon de produit et peut insérer ce brouillon comme nouveau produit. Il sert pour les produits qui ne sont pas encore dans le catalogue. Pour remplir un produit existant, utilisez **Générer** ou la page du produit.

![Nouveau produit (New product)](https://mypresta.eu/docs/images/docs/mychatgpt-new-product.webp)

Si aucune clé n'est enregistrée, vous voyez « Ajoutez d'abord une clé API dans les paramètres du module. ».

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| **Quel est le produit ?** | Vide (obligatoire) | Le brief que le modèle développe en nom, descriptions, méta, mots-clés, caractéristiques, référence et prix. Écrivez quelques phrases avec la matière, le public et les noms qui doivent rester. Une case vide est refusée avec « Prompt is required ». |
| **URL source facultative** | Vide | Une adresse web complète d'une page publique sur le produit. Une page lisible ajoute au brief son titre, sa description et son texte de prix. Une page illisible est ignorée. |
| **Langue** | Langue par défaut de la boutique | La langue dans laquelle le texte est enregistré. Les autres langues ne sont pas remplies. Choisissez la langue par défaut de votre boutique, car PrestaShop a besoin d'un nom dans la langue par défaut pour créer un produit. |
| **ID de catégorie par défaut** | 2 | Le numéro de catégorie de **Catalogue**, **Catégories**. 2 est généralement **Accueil**. Le produit est placé dans cette catégorie et elle devient la catégorie par défaut. |

1. Cliquez sur **Générer les données**. Le brouillon apparaît sous forme de texte dans la case en dessous (nom, description, description courte, titre méta, description méta, mots-clés, tags, référence, prix, caractéristiques). Rien n'est encore enregistré. Cliquez de nouveau pour un nouveau brouillon. Vous ne pouvez pas modifier le brouillon dans cet écran.
2. Vérifiez le brouillon, en particulier le prix et la référence suggérés.
3. Cliquez sur **Créer le produit**. La ligne de résultat affiche « Product # » et le numéro du nouveau produit.

Le nouveau produit est actif, commandable, visible dans le catalogue et la recherche, à l'état neuf, avec le groupe de règles de taxe numéro 1, un stock de 100 pièces et le prix suggéré. Le nom, les descriptions, les méta, les mots-clés et les caractéristiques ne sont enregistrés que dans la langue choisie. Cet écran n'ajoute pas de photos. Ouvrez le nouveau produit, l'onglet **Modules**, **Photos**, pour en ajouter. Vérifiez le prix, la taxe, la quantité et la catégorie avant de publier. La génération ici n'est pas enregistrée dans l'Historique et ne compte pas dans le budget mensuel.

### 3.10 Cron

Ouvrez **Cron**. Le cron est destiné au serveur, pas à une personne qui clique sur **Exécuter**. Cet écran enregistre vos choix et affiche les adresses secrètes que votre serveur appelle selon un calendrier. Chaque appel réel écrit un petit lot et s'arrête. La boutique ne fait rien tant que le serveur ne demande pas l'adresse.

![Cron (Cron)](https://mypresta.eu/docs/images/docs/mychatgpt-cron.webp)

Le panneau supérieur **Tâche cron de catégorie** et le panneau **Paramètres Cron** affichent les adresses de votre boutique avec les secrets. Traitez les secrets comme des mots de passe : ne publiez jamais une adresse complète. Ce manuel les montre sous la forme `YOUR_SECURE_KEY`, par exemple `https://your-shop.example/module/mychatgpt/cron?secret=YOUR_SECURE_KEY`. Chaque adresse doit recevoir en plus les réglages du formulaire (champ, langue, modèle, taille du lot, etc.). La section 6.3 les énumère. Demandez à votre développeur ou à votre hébergeur de les ajouter lors de la configuration du planificateur.

Formulaire des produits **CRON JOB Settings – Generate product content using OpenAI**. Cliquez sur **Enregistrer** après modification.

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| **Activer la fonction cron** | Non | Autorise le serveur à générer les textes des produits et des catégories selon un calendrier. N'activez-la qu'après avoir enregistré le secret, le champ, la langue et le modèle. Tant qu'elle est désactivée, chaque adresse cron répond que la fonction est désactivée. Cet unique interrupteur est aussi nécessaire pour le cron des catégories. |
| **Jeton secret de la tâche cron** | Longue valeur aléatoire | Un long mot de passe qui doit faire partie de l'adresse cron des produits. Sans lui, la boutique refuse l'appel. Conservez la valeur générée. La modifier invalide immédiatement l'ancienne adresse. Le bouton **Générer le jeton** ne crée pas de nouvelle valeur dans cette version ; conservez donc la valeur créée à l'installation. |
| **Champ à mettre à jour** | description | Le champ de produit unique que ce cron écrit : name, description, description_short, meta_title, meta_description ou tags. Pour remplir plusieurs champs, créez plusieurs commandes cron. |
| **Produits sélectionnés** | pendingOpenAI | Décide quels produits attendent encore. **pendingOpenAI** : les produits que le module n'a pas encore écrits (n'importe quel champ). **pendingField** : les produits pas encore écrits pour ce champ précis, de sorte que plusieurs commandes (par exemple description et name) puissent travailler sur les mêmes produits. **emptyField** : uniquement les produits dont le champ choisi est vide. Chaque exécution ignore les produits qui ne correspondent plus, si bien qu'un catalogue terminé cesse de changer. |
| **Catégories de produits** | Rien de coché | Limite l'exécution aux catégories cochées. Une arborescence vide signifie que la catégorie n'est pas un filtre. |
| **Liste d'ID de produits** | Vide | Limite l'exécution à ces numéros de produits, séparés par des virgules. Les lettres et autres caractères sont supprimés à l'enregistrement. |
| **Langue** | Langue par défaut de la boutique | La version linguistique qui est écrite. Les autres langues nécessitent leur propre commande. |
| **Produits à mettre à jour** | 5 produits | Combien de produits correspondants un appel traite (2, 3, 5, 8, 10, 15, 20, 50, 100, 200, 300, 500 ou 1000). Commencez par 5 ou 10 pour qu'un modèle lent n'atteigne pas la limite de temps du serveur. |
| **Modèle de prompt** | Premier modèle de la liste | L'instruction enregistrée utilisée pour chaque produit de l'exécution. Les variables sont remplies par produit. Choisissez un modèle activé. |
| **Activer le débogage** | Non | Lorsque l'adresse est ouverte avec le débogage activé, elle affiche le plan (réglages, produits sélectionnés, prompts finaux) et n'écrit rien. Vérifiez ainsi une commande une fois. Désactivez-le avant que le planificateur utilise l'adresse. |
| **Intervalle de la tâche cron** | Toutes les heures | Le rythme que vous prévoyez (toutes les 1, 2, 5, 10 ou 30 minutes, toutes les heures, toutes les 2 ou toutes les 6 heures). Il documente votre plan. Le module ne démarre pas le planificateur. |
| **Commande de la tâche cron des produits** | – | Affiche la ligne de commande à copier dans le planificateur. Enregistrez d'abord le formulaire. |

Formulaire des catégories **CRON JOB Settings – Generate category content using OpenAI**. Il a son propre secret et son propre bouton **Enregistrer**, et n'a pas besoin de son propre interrupteur d'activation :

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| **Jeton secret de la tâche cron** | Longue valeur aléatoire | Le mot de passe de l'adresse des catégories. Il est distinct du secret des produits. Le modifier invalide l'ancienne adresse des catégories. |
| **Champ à mettre à jour** | description | Le champ de catégorie unique qui est écrit : name, description, meta_title ou meta_description. |
| **Catégories sélectionnées** | pendingOpenAI | Les mêmes trois règles que pour les produits, appliquées aux catégories. **pendingField** permet à plusieurs commandes de partager les mêmes catégories. |
| **Langue** | Langue par défaut de la boutique | La version linguistique qui est écrite. |
| **Catégories à mettre à jour** | 5 catégories | Combien de catégories un appel traite (de 2 à 1000). |
| **Modèle de prompt** | Premier modèle de la liste | Rédigez le modèle pour une catégorie, pas pour un produit, par exemple avec `{category_name}`. |
| **Activer le débogage** | Non | Affiche le plan et n'enregistre pas les catégories. |
| **Intervalle de la tâche cron** | Toutes les heures | Le rythme que vous prévoyez. |
| **Commande de la tâche cron des catégories** | – | La ligne de commande à copier après l'enregistrement. |

Le cron des catégories ne touche jamais **Accueil** ni la catégorie racine.

### 3.11 Historique

Ouvrez **Historique**. L'Historique est le journal de ce qui a été demandé et de ce qui est revenu. Ouvrir ou filtrer la page ne supprime rien et ne modifie aucun produit.

![Historique (History)](https://mypresta.eu/docs/images/docs/mychatgpt-history.webp)

La barre de filtres s'ouvre sur **Ce mois-ci**. Utilisez les boutons de période **Aujourd'hui**, **7 jours**, **30 jours**, **Ce mois-ci** et **Depuis toujours**, ou **De** et **À**. Vous pouvez aussi affiner par **Modèle**, **Type**, **Statut** (**N'importe lequel**, **Succès**, **Erreur**), **Langue**, **Employé**, **ID produit / catégorie** et **L'invite ou la réponse contient**. Cliquez sur **Filtrer**.

- Les cartes affichent **Requêtes**, **Succès**, **Erreurs**, **Jetons envoyés**, **Jetons reçus**, **Total des jetons** et **Temps moyen** pour le filtre. Un tiret signifie qu'OpenAI n'a renvoyé aucun nombre de jetons pour cet appel.
- Les panneaux **Par jour**, **Par modèle**, **Par type**, **Par langue** et **Par employé** regroupent les mêmes lignes par **Groupe**, **Appels**, **Envoyé**, **Reçu** et **Total**. Un petit nombre en italique à côté des appels est le nombre d'erreurs.
- La liste **Historique des prompts** comporte les colonnes **ID**, **Statut**, **Prompt**, **Réponse / Erreur**, **Fournisseur** (modèle, code d'erreur, secondes), **Envoyé**, **Reçu**, **Total**, **ID de l'entité**, **Type** et **Horodatage**. Le prompt et la réponse sont abrégés. Cliquez sur **Voir** dans une ligne pour lire le prompt complet et la réponse complète avec les jetons, puis sur **Retour à la liste**. Une ligne d'erreur affiche le texte de l'erreur au lieu d'une réponse. **Type** indique ce qui a été écrit, par exemple product_description ou category_meta_title. Les simulations et l'aire de jeu créent aussi des lignes.
- Le bouton **Vider la liste** supprime toutes les lignes d'un coup, sans confirmation, y compris celles hors de votre filtre. Ensuite, les compteurs du **Tableau de bord**, le filtre **Mettre à jour uniquement**, la règle **pendingOpenAI** et le compteur du budget mensuel repartent de zéro, et **Restaurer** n'est plus possible pour les anciens textes.

### 3.12 Images

Ouvrez **Images**. Cette page ne télécharge pas d'images. Elle active ou désactive la recherche d'images de la page du produit et enregistre l'instruction utilisée pour cette recherche.

![Images (Images)](https://mypresta.eu/docs/images/docs/mychatgpt-images.webp)

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| **Recherche d'images IA** | Activé | **Activé** affiche l'onglet **Photos** sur la page d'édition du produit. **Désactivé** le supprime. Une image n'est importée qu'après confirmation par quelqu'un. |
| **Prompt de recherche d'images IA** | Le même long texte par défaut que dans **Général** | L'instruction envoyée lorsque quelqu'un cherche. `{product_name}` et `{product_description}` sont remplacés par le produit courant. Conservez la demande d'une liste simple d'adresses de pages. |

Cliquez sur **Enregistrer**. Vous voyez « Paramètres enregistrés. ». La recherche de pages et l'importation de photos sont décrites à la section 3.13.

### 3.13 Édition du produit (onglet Modules)

Ouvrez **Catalogue**, **Produits**, modifiez un produit et ouvrez l'onglet **Modules**. Le panneau **Mon ChatGPT** comporte les onglets **Générer**, **Simuler**, **Photos** et **Historique**. Si **Formulaire de la page d'édition du produit** est désactivé, seul **Historique** reste. Si **Historique d'édition du produit** est aussi désactivé, rien n'apparaît. Enregistrez un nouveau produit une fois avant de générer, afin qu'il ait un numéro.

![Édition du produit (Product edit)](https://mypresta.eu/docs/images/docs/mychatgpt-product-edit.webp)

**Générer** écrit un champ et l'enregistre aussitôt sur le produit.

1. Choisissez une pastille **Langue**, ou **Toutes les langues**.
2. Sous **Si le champ contient déjà du texte**, choisissez **Remplacer**, **Ajouter au-dessus**, **Ajouter en dessous** ou **Ignorer si rempli**.
3. Cliquez sur **Remplir** sur une carte de champ : **Description** (texte long avec une courte introduction et une liste de caractéristiques), **Description courte** (résumé simple de moins de 400 caractères environ), **Nom**, **Titre méta** (environ 70 caractères), **Description méta** (environ 160 caractères) ou **Mots-clés** (mots séparés par des virgules).
4. **Pack SEO** avec **Tout remplir** écrit le nom, les deux descriptions et les deux champs méta d'un coup. Il remplace ces champs quel que soit votre choix sous **Si le champ contient déjà du texte**.
5. Facultatif : ouvrez **Utilisez votre propre instruction ou une invite enregistrée**. Saisissez dans **Filtrer par titre ou texte**, choisissez **Brief standard** (un brief prêt à l'emploi pour le champ sur lequel vous appuyez) ou un modèle activé, ou saisissez votre propre **Instruction**.

Sous les boutons, vous voyez l'instruction envoyée et la réponse, ainsi que « Content successfully generated and updated to product. ». Le formulaire du produit à l'écran n'est pas actualisé. Rechargez la page du produit avant de modifier à nouveau. Si vous appuyez sur **Enregistrer** dans l'ancien formulaire, PrestaShop réécrit l'ancien texte. Le module raccourcit les longues réponses à la taille du champ : nom 128 caractères, description courte 800, titre méta 69, description méta 159.

**Simuler** offre les mêmes choix et les boutons **Essayer**. Il affiche la réponse sur la page et ne modifie pas le produit. La tentative est écrite dans l'Historique.

**Photos** (nécessite **Recherche d'images IA** activée) :

1. Cliquez sur **Trouver des pages**. Le modèle suggère des pages susceptibles de montrer ce produit.
2. Cliquez sur l'adresse d'une page. La boutique lit la page (les adresses de réseaux privés ou locaux sont refusées) et liste jusqu'à 24 images. Les petites icônes et les pixels de suivi sont ignorés.
3. Cochez les photos souhaitées. La première photo cochée devient l'image de couverture du produit et remplace la couverture actuelle. Les autres sont ajoutées après les photos existantes.
4. Cliquez sur **Ajouter la sélection à ce produit**. Rien n'est enregistré avant ce clic. Rechargez le produit pour voir les photos.

Les recherches de photos ne sont pas écrites dans l'Historique et ne comptent pas dans le budget. Respectez les droits d'auteur des photos que vous importez.

**Historique** liste les écritures précédentes de ce produit avec **Quand**, **Type** et **Statut**. **Restaurer** remet le texte précédent après confirmation de « Restore the previous value? ». Vous voyez « Content successfully restored. Refresh this page to see changes. ». L'Historique de toute la boutique n'est pas supprimé.

À côté des champs de description, de description courte, de titre méta et de description méta (dans n'importe quel formulaire de produit), vous voyez aussi un petit bouton rond avec le logo OpenAI, **Générer avec l'IA**. Cliquez dessus. Si la boutique a plus d'une langue, choisissez **Langue actuelle**, **Toutes les langues** ou **Annuler**. Le champ reçoit un brief prêt à l'emploi pour ce champ, et le texte va uniquement dans le champ du formulaire, avec « Le texte est dans le champ. Enregistrez le produit pour le conserver. ». Cliquez sur **Enregistrer** sur le produit pour le conserver. Ce bouton n'utilise ni modèles ni la case **Instruction**.

### 3.14 Mises à jour

Ouvrez **Mises à jour** (côté droit du menu supérieur). Le formulaire **Mises à jour MyPresta** vérifie sur MyPresta.eu s'il existe un fichier de module plus récent. Il ne modifie pas votre catalogue et n'installe rien.

![Mises à jour (Updates)](https://mypresta.eu/docs/images/docs/mychatgpt-updates.webp)

| Champ | Par défaut | Ce qu'il fait |
|---|---|---|
| **Vérification manuelle** | – | Cliquez sur **Vérifier maintenant**. La boutique interroge une fois le serveur de mises à jour de MyPresta.eu et affiche « Le module est à jour ! » ou « Nouvelle version disponible ! » à côté du bouton. |
| **Notifications automatiques** | Activé | **Activé** laisse le back office vérifier environ tous les trois jours et afficher un avertissement avec un lien lorsqu'une version plus récente existe. **Désactivé** l'arrête. |
| **Page produit** | – | Un lien vers la page du module sur MyPresta.eu. |

Cliquez sur **Enregistrer** pour mémoriser le choix des notifications. Vous voyez « Paramètres de mise à jour enregistrés. ». Le numéro de version à côté du nom du module dans le menu est la version installée sur votre boutique, pas la plus récente.

## 4. Vitrine de la boutique

Le module n'affiche rien à vos clients. Il n'ajoute aucun bloc, aucune page, aucun script ni aucun style à la vitrine de la boutique. Le thème n'a rien à remplacer. Tout ce que vous voyez se trouve dans le back office : le bouton **Mon ChatGPT** de la barre supérieure, les écrans du module et le panneau de la page du produit.

Le module possède deux adresses web qui n'existent que pour les serveurs et pour le back office :

- L'**adresse cron**. Copiez-la depuis **Cron** (section 3.10) et placez-la uniquement dans le planificateur de votre serveur. Toute personne qui connaît l'adresse complète avec le secret peut lancer un lot ; ne la publiez donc jamais et ne la collez pas dans des discussions ou des tickets.
- Une adresse technique utilisée par les boutons du back office pour chaque génération. Ne l'ouvrez pas et ne la partagez pas.

Ouvrir l'adresse cron dans un navigateur affiche du texte brut. Voici les messages que vous pouvez lire :

| Ce que vous voyez | Que faire |
|---|---|
| Cron Job feature is disabled. You can enable it from the module settings. | Ouvrez **Cron**, réglez **Activer la fonction cron** sur **Oui** et cliquez sur **Enregistrer**. |
| The token does not exist or it’s wrong! | Le secret est absent ou ne correspond pas. Copiez à nouveau l'adresse depuis **Cron** après l'enregistrement. |
| Invalid action! | L'adresse n'a pas de partie tâche. Ajoutez les réglages énumérés à la section 6.3. |
| updatedField parameter is wrong! | Le nom du champ dans l'adresse n'est pas l'un des champs autorisés. Utilisez un champ listé dans **Champ à mettre à jour**. |
| All must include all mandatory parameters! | L'adresse n'a pas le champ, la règle de sélection, la taille du lot, la langue ou le modèle. Ajoutez-les (section 6.3). |
| productTarget parameter is wrong! Allowed values: … (ou categoryTarget) | Utilisez pendingOpenAI, pendingField ou emptyField. |
| No valid product IDs provided. | La **Liste d'ID de produits** ne contient aucun numéro utilisable. Corrigez ou videz la liste. |
| No products to update. / No categories to update. | Plus rien ne correspond à la règle. La tâche est terminée, ou modifiez **Produits sélectionnés** ou les filtres. |
| N products have been updated. / N categories have been updated. | Un lot a été écrit. L'appel suivant continue avec les éléments suivants. |
| N pending products. | Le débogage est activé. Rien n'a été écrit. Désactivez le débogage pour les exécutions réelles. |
| Error!Monthly generation budget reached. | Augmentez le **Budget de génération mensuel** ou attendez le mois prochain. |
| Error!Reply rejected by the studio quality gate. | La réponse contenait un mot interdit. Modifiez **Mots interdits** ou désactivez le **Contrôle qualité**. |
| Error! The model returned an empty response. | Augmentez **Jetons max**, essayez un autre modèle ou un autre modèle de prompt. |
| Error! suivi d'un message d'OpenAI | Lisez le message. Les causes typiques sont une mauvaise clé, un manque de crédit ou un modèle inconnu. |
| Error! Could not save product … (N product(s) updated before this one.) | PrestaShop a refusé le texte pour cet élément. Vérifiez le produit, puis relancez. |

## 5. Dépannage

### 5.1 Connexion et réglages

| Symptôme | Cause | Que faire |
|---|---|---|
| « The OpenAI API key is not set. Add it in the module settings. » ou « The ChatGPT API key is not set. Add it in the module settings. » | Aucune clé n'est enregistrée. | Ouvrez **Paramètres**, **ChatGPT**, collez la clé dans **Clé API OpenAI** et cliquez sur **Enregistrer**. |
| « Le champ Clé API OpenAI est invalide ! » | Vous avez enregistré une nouvelle clé de moins de 10 caractères alors qu'aucune clé n'était enregistrée. | Collez la clé complète. |
| « Le champ Modèle OpenAI est invalide ! » | **Modèle** compte moins de 3 caractères. | Choisissez un modèle dans la liste et enregistrez à nouveau. |
| Message d'OpenAI à propos d'une clé incorrecte, d'un quota ou d'un modèle inexistant | OpenAI a refusé l'appel. Le module affiche le texte propre à OpenAI. | Vérifiez la clé, la facturation OpenAI et le nom du modèle dans **Paramètres**, **ChatGPT**. Un modèle que vous avez ajouté doit être disponible pour votre compte. |
| « Error! Invalid token! » | La page a été ouverte avant que le module renouvelle son secret interne, ou est restée ouverte très longtemps. | Rechargez la page et réessayez. |
| « OpenAI request timed out after N seconds. The model may be overloaded, or the timeout is too low for this prompt. » | OpenAI a répondu trop lentement. | Augmentez **Délai d'attente API (secondes)** dans **Paramètres**, **Général** (jusqu'à 600), utilisez un modèle plus rapide ou demandez un texte plus court. |
| « The model hit the token limit before returning any text. Increase "Max Tokens" in the module settings – reasoning models spend part of that budget on thinking. » | **Jetons max** est trop bas pour ce modèle. | Augmentez **Jetons max** dans **Paramètres**, **ChatGPT**. |
| « The response was blocked by the provider content filter. Try rewording the prompt. » | Le filtre d'OpenAI a arrêté la réponse. | Reformulez le prompt ou les données du produit qu'il utilise. |
| « The model returned an empty response. » | Le modèle n'a renvoyé aucun texte. | Réessayez, avec un autre modèle ou un prompt moins strict. |
| « Monthly generation budget reached. Raise it in the studio settings or wait until next month. » | Le nombre de générations réussies a atteint le **Budget de génération mensuel**. | Augmentez le nombre dans **Paramètres**, **Studio**, mettez 0 ou attendez le mois prochain. Vider l'**Historique** remet aussi le compteur à zéro. |
| « The reply was rejected because it contains a forbidden word from the studio settings. » | Une ligne de **Mots interdits** apparaît dans la réponse, même à l'intérieur d'un mot plus long. | Raccourcissez ou modifiez la liste, ou réglez **Contrôle qualité** sur **Non**. Rien n'a été écrit dans le produit. |

### 5.2 Page du produit et résultats de génération

| Symptôme | Cause | Que faire |
|---|---|---|
| Le panneau **Mon ChatGPT** est absent de la page du produit. | **Formulaire de la page d'édition du produit** et **Historique d'édition du produit** sont tous deux désactivés, ou vous n'êtes pas dans l'onglet **Modules**. | Activez les interrupteurs dans **Paramètres**, **Général**, puis ouvrez l'onglet **Modules**. |
| « Enregistrez le produit une fois avant de générer. » | Le produit n'a pas encore de numéro. | Enregistrez le produit, puis générez. |
| Le nouveau texte a disparu après l'enregistrement du produit. | Le formulaire du produit à l'écran contenait encore l'ancien texte. | Après **Remplir**, rechargez la page du produit avant de modifier et d'enregistrer. |
| « Product skipped. » ou « Category skipped. » | **Ignorer si rempli** a trouvé du texte dans le champ. Ce n'est pas une erreur. | Choisissez **Remplacer**, **Ajouter au-dessus** ou **Ajouter en dessous** si vous voulez écrire malgré tout. |
| « Error! Content retrieve has failed! Details: … » | OpenAI ou le serveur a renvoyé une erreur. | Lisez les détails après « Details: ». Ouvrez l'**Historique**, filtrez **Statut** sur **Erreur** et ouvrez la ligne. |
| « Error! The generated content could not be saved to the product. » ou « … to the category. » | PrestaShop a refusé le texte, par exemple à cause d'un caractère interdit. | Lisez la raison après la phrase. Essayez un autre prompt ou un champ plus court. |
| « Error! Prompt is missing or too short! » | L'instruction compte moins de 4 caractères. | Rédigez une instruction plus longue ou laissez la case vide pour utiliser le brief standard. |
| « Error! Product not found! » / « Error! Category not found! » | L'élément a été supprimé ou le numéro est faux. | Reconstruisez la liste et relancez. |
| « Error! This log entry has no previous value to restore. » ou « Error! Nothing to restore for this entry. » | Cette ligne de l'Historique n'a pas d'ancien texte. | Utilisez une autre ligne. Les lignes écrites par **Simuler** ou les erreurs ne peuvent rien restaurer d'utile. |
| « The model did not return a usable SEO pack. » | La réponse n'avait pas le format attendu. | Cliquez de nouveau sur **Tout remplir** ou remplissez les champs un par un. |
| « Échec de la génération. » sur un bouton **Générer avec l'IA** | L'appel a échoué. | Réessayez. Consultez l'**Historique** pour la raison. |
| « Error! This PrestaShop version does not support the category Additional Description field. » | Votre boutique n'a pas ce champ de catégorie. | Choisissez un autre champ de catégorie. |

### 5.3 Génération en masse

| Symptôme | Cause | Que faire |
|---|---|---|
| Le tableau après **Passer à l'étape suivante** est vide. | Les filtres ne correspondent à rien. | Assouplissez les filtres. Vérifiez **Statut du produit**, **Stock du produit** et **Mettre à jour uniquement**. |
| « Select at least one language. » | Aucune langue n'est cochée. | Cochez au moins une langue. |
| L'exécution s'est arrêtée en cours de route. | L'onglet a été fermé, la connexion a été coupée ou le serveur s'est arrêté. | Reconstruisez la liste avec **Mettre à jour uniquement** réglé sur les produits non mis à jour et relancez. |
| De nombreuses lignes affichent des erreurs. | Un problème de budget, de clé ou de délai d'attente. | Ouvrez l'**Historique**, lisez la première erreur, corrigez-la et relancez. |
| Accueil et la catégorie racine figurent dans la liste des catégories. | **Catégories** a été laissé vide. | Cochez les catégories souhaitées avant **Passer à l'étape suivante**. |

### 5.4 Cron

| Symptôme | Cause | Que faire |
|---|---|---|
| Rien ne change dans le catalogue. | **Activer la fonction cron** est désactivé, le planificateur n'appelle pas l'adresse, ou aucun élément ne correspond à la règle. | Vérifiez l'interrupteur, le journal du planificateur et **Produits sélectionnés**. Ouvrez l'adresse une fois avec le débogage activé pour voir le plan. |
| L'adresse répond par un message du tableau de la section 4. | Voir ce tableau. | Faites ce que dit le tableau. |
| Les mêmes produits sont écrits encore et encore. | **Produits sélectionnés** est **emptyField** et le champ reste vide, ou **pendingOpenAI** est utilisé et l'Historique a été vidé. | Utilisez **pendingField**, ou corrigez le prompt pour que du texte soit écrit. |
| Une ancienne adresse ne fonctionne plus. | Le module remplace les secrets de moins de 24 caractères, ou le secret a été modifié, ou le module a été réinstallé. | Copiez à nouveau l'adresse depuis **Cron** et mettez à jour le planificateur. |
| **Générer le jeton** ne fait rien. | Le bouton n'a aucune fonction dans cette version. | Conservez le secret créé à l'installation. |

### 5.5 Images, nouveau produit et menu

| Symptôme | Cause | Que faire |
|---|---|---|
| L'onglet **Photos** est absent. | **Recherche d'images IA** est désactivée. | Activez-la dans **Paramètres**, **Général** ou **Images**, puis rechargez le produit. |
| « No pages were suggested. » ou « The search failed. » | Le modèle n'a renvoyé aucune adresse utilisable, ou la clé a un problème. | Cliquez de nouveau sur **Trouver des pages** ou vérifiez le **Prompt de recherche d'images IA**. |
| « That page could not be read. », « URL not allowed (private network) » ou une erreur commençant par HTTP | La page bloque la boutique, exige une connexion ou se trouve sur un réseau privé. | Choisissez une autre page. |
| « No photos were found on that page. » | La page n'a aucune image utilisable. | Choisissez une autre page. |
| « No images could be imported. Details: … » | Les images n'ont pas pu être téléchargées ou ne sont pas de vraies images. | Lisez les détails. Choisissez d'autres photos. |
| « Failed to parse AI response. Please try again. » sur **Nouveau produit** | La réponse n'avait pas le format attendu. | Cliquez de nouveau sur **Générer les données**. |
| « Error creating product: … » ou « Failed to create product » | PrestaShop a refusé le produit, souvent parce que la **Langue** choisie n'est pas la langue par défaut de la boutique. | Choisissez la langue par défaut et vérifiez le numéro de catégorie. |
| « Generate the product first. » | Vous avez cliqué sur **Créer le produit** avant **Générer les données**. | Cliquez d'abord sur **Générer les données**. |
| L'entrée de menu **Générateur de Contenu IA** est absente. | Le module est désactivé, ou l'entrée a été déplacée. | Activez le module dans le **Gestionnaire de modules** et ouvrez une fois une page quelconque du back office. Le module replace l'entrée sous **Modules**. Si elle manque toujours, vérifiez que votre profil d'employé peut ouvrir **Modules**. |
| Le Tableau de bord et l'Historique sont vides. | Rien n'a été généré sur la période choisie, ou **Vider la liste** a été utilisé. | Choisissez **Depuis toujours**. |

## 6. Pour les développeurs

### 6.1 Vue d'ensemble

| Élément | Valeur |
|---|---|
| Nom technique | mychatgpt |
| Version | 1.1.0 |
| Nom dans la liste des modules | My ChatGPT - AI content generation |
| Auteur | MyPresta.eu |
| Onglet du module | front_office_features |
| PrestaShop | 1.6 – 9.99.99 |
| PHP minimum | 7.0.0 (vérifié dans `install()`) |
| Classe principale | `mychatgpt extends Module`, avec les classes auxiliaires `mychatgptUpdate` et `searchToolmychatgpt` qui l'étendent |

Flux de données : le JavaScript du back office appelle le contrôleur front `ajax` avec `secret_token` (lu depuis `MYPRESTA_MYCHATGPT_TOKEN`) ou un contrôleur d'administration. Le contrôleur lit les clés de modèle et d'échantillonnage, applique le Studio (`MyChatGPT\Studio`), appelle OpenAI via `MyChatGPT\OpenAIService` (cURL vers le point de terminaison chat completions de l'API OpenAI), écrit le texte avec le modèle objet de PrestaShop et insère une ligne dans `mychatgpt_log`. `cron` fait la même chose sans navigateur. `getServiceName()` renvoie toujours `openai`. Le code résiduel pour d'autres fournisseurs a été supprimé. Les clés de réglage d'un ancien second fournisseur (`_GEMINI_API_KEY`, `_GEMINI_MODEL`, `_ACTIVE_SERVICE`) sont supprimées à chaque ouverture de l'écran des paramètres.

### 6.2 Fichiers

| Chemin | Rôle |
|---|---|
| `mychatgpt.php` | Classe principale : installation et désinstallation, onglets, formulaires de réglages, modèles de prompt, tableau de bord, hooks, onglet du produit, catalogue de modèles. |
| `autoload.php` | Petit chargeur de classes pour l'espace de noms `MyChatGPT\` (sans Composer). |
| `src/OpenAIService.php` | Client cURL pour chat completions et la liste des modèles. Délai d'attente 10–600 s, abandonne les paramètres qu'un modèle rejette (jusqu'à 6 nouvelles tentatives), désactive la vérification des certificats uniquement sur localhost. |
| `src/Studio.php` | Contrôle du budget, décoration du prompt (langue, voix, public, ton, glossaire, mots interdits), inspection de la réponse, pack SEO et prompts de texte alternatif. |
| `controllers/admin/*.php` | Sept contrôleurs d'administration (section 6.3). |
| `controllers/front/ajax.php` | Point de terminaison JSON pour toute génération déclenchée depuis le navigateur. |
| `controllers/front/cron.php` | Point de terminaison cron en texte brut. |
| `lib/updateChecker.php` | Vérification des mises à jour auprès de dev.mypresta.eu tous les 3 jours et formulaire Mises à jour. |
| `lib/sectionHelp.php` | Textes du tiroir d'Aide. |
| `lib/searchTool/` | Classe auxiliaire `searchToolmychatgpt` (outil d'autocomplétion dans les écrans du module). |
| `lib/prestashop9compatibility.php` | Enveloppes pour l'affichage des prix, le hachage et les redirections sur PrestaShop 9. |
| `views/templates/hook/*.tpl` | Écrans et panneaux du module (tableau de bord, navigation, sous-navigation, générateurs en masse, onglet du produit, historique, infos cron, boîte de la barre supérieure). |
| `views/templates/admin/product_creator.tpl` | Écran de nouveau produit. |
| `views/js/back.js` | Exécutions en masse, panneau du produit, aire de jeu, boîte de la barre supérieure, nouveau produit, restauration. |
| `views/js/product-fields.js` | Boutons **Générer avec l'IA** à côté des champs du produit. |
| `views/js/image-finder.js` | Onglet **Photos**. |
| `views/js/admin-products-bulk.js` | Ajoute le bouton **Mon ChatGPT** à la liste des produits. |
| `views/js/dashboard.js`, `chart.min.js`, `admin-help.js` | Graphiques et tiroir d'Aide. |
| `views/css/admin-nav.css`, `back.css`, `stats.css` | Styles. |
| `translations/*.php` | 34 fichiers de langue. |
| `upgrade/index.php` | Simple fichier de redirection. Il n'y a aucun script de mise à niveau. |

Les classes `AdminMyChatGPTMain` et `AdminMyChatGPTSettings` appellent `addJS`/`addCSS` pour `views/js/admin.js` et `views/css/admin.css`, et le contrôleur du nouveau produit pour `product_creator.js` et `product_creator.css`. Aucun de ces fichiers n'est livré. Le formulaire cron attend les fonctions JavaScript `generateTokenAndFill()` et `generateCategoryTokenAndFill()` et remplit les span `.cron-parameters`. Ce script n'est pas livré non plus.

### 6.3 Contrôleurs

| Contrôleur | Parent et route | Rôle |
|---|---|---|
| `AdminMyChatGPTMain` | Sous **Modules**, visible. Redirige vers la configuration du module, Tableau de bord. | L'entrée de menu **Générateur de Contenu IA**. |
| `AdminMyChatGPTSettings` | Onglet masqué (`active = 0`). Redirige vers la configuration, Paramètres. | Entrée de compatibilité. |
| `AdminMyChatGPT` (fichier `AdminMyChatGPT.php`, classe `AdminMyChatGPTController`) | Onglet masqué. `mcg_sub=products` ou `categories`. | Filtres et générateurs en masse. `renderProductUpdateForm()` et le formulaire de mise à jour des catégories n'ont pas de gestionnaire. Les envois `generateProductContent` et `generateCategoryContent` ne font qu'enregistrer les valeurs du formulaire. La génération s'exécute depuis `back.js`. |
| `AdminMyChatGPTProductCreator` | Onglet masqué. Actions Ajax `generateProductData`, `createProduct`, `extractImages`, `generateImages` (stub). | Nouveau produit. |
| `AdminMyChatGPTCron` | Onglet masqué. Formulaires `submitCronUpdate`, `submitCatCronUpdate`. | Réglages cron. |
| `AdminMyChatGPTUsage` | Onglet masqué. Paramètres `stats_*`, `view` et `clear_log`. | Historique. `clear_log` exécute `DELETE` sur toute la table de journal. |
| `AdminMyChatGPTImageFinder` | Onglet masqué. Actions Ajax `searchImages`, `extractImages`, `saveImages`. | Formulaire **Images** et recherche de photos. |

Tous les contrôleurs d'administration redirigent vers l'écran d'accueil si le module est inactif. La page de configuration du module (`getContent`) affiche Tableau de bord, Paramètres (`mcg_tab=settings`, `mcg_sub` general, openai, studio, templates, playground) et Mises à jour (`mcg_tab=updates`).

Contrôleur front `ajax` (`secret_token` doit être égal à `_TOKEN` ; il n'y a pas de contrôle d'employé). Actions : `initiatePrompt`, `updateSettings` (écrit max tokens, temperature, top p et les deux pénalités), `updateProduct`, `updateCategory`, `initiateProductRestore`, `generateAltTexts` (aucun bouton ne l'utilise ; 8 images au maximum), `generateSeoPack`. `updateProduct` et `updateCategory` acceptent `target` (champ), `behavior` (`replace`, `keep`, `keep_top`, `keep_end` ou `single_product` pour un aperçu non enregistré), `prompt`, la langue et le numéro de l'élément. Les réponses sont du JSON avec `status` (`success`, `error`, `skipped`), `msg` et `date`.

Contrôleur front `cron` : refuse avec le message « disabled » lorsque `_ENABLE_CRON` vaut 0. Le paramètre `secret` doit être égal à `_SECRET` ou `_CAT_SECRET` (l'un ou l'autre secret ouvre l'une ou l'autre tâche). Paramètres :

| Paramètre | Utilisé par | Signification |
|---|---|---|
| `secret` | les deux | Secret des produits ou des catégories. |
| `action` | les deux | `generateProductContent` ou `generateCategoryContent`. |
| `updatedField` | les deux | Produits : name, description, description_short, meta_title, meta_description, tags. Catégories : name, description, meta_title, meta_description, additional_description. |
| `productTarget` / `categoryTarget` | chacun | `pendingOpenAI`, `pendingField`, `emptyField`. |
| `productsToUpdate` / `categoriesToUpdate` | chacun | Taille du lot (`LIMIT`). |
| `languageId` | les deux | Numéro de langue. |
| `promptTemplateId` | les deux | Numéro de modèle de `mychatgpt_prompt`. |
| `debug` | les deux | Toute valeur autre que 0 affiche le plan et n'écrit rien. |
| `categories` | produits | Numéros de catégories séparés par des virgules. |
| `productIds` | produits | Numéros de produits séparés par des virgules. |

Exemple (utilisez `YOUR_SECURE_KEY` uniquement comme espace réservé) :

```text
https://your-shop.example/module/mychatgpt/cron?secret=YOUR_SECURE_KEY&action=generateProductContent&updatedField=description&productTarget=pendingField&productsToUpdate=5&languageId=1&promptTemplateId=3&debug=1
```

`pendingOpenAI` et `pendingField` examinent les lignes réussies de `mychatgpt_log` (les lignes avec le statut error sont ignorées, de sorte que les éléments échoués sont retentés). La tâche des catégories exclut les catégories dont le numéro va jusqu'à la catégorie d'accueil incluse.

### 6.4 Hooks

Enregistrés dans `install()` :

| Hook | Comportement |
|---|---|
| `displayAdminProductsExtra` | Affiche le panneau de l'onglet **Modules** (`product-tab-wrapper.tpl`) lorsque `_PRODUCT` ou `_PRODUCT_LOG` vaut 1. |
| `displayBackOfficeHeader` | Charge les ressources ; exécute `ensureLongSecrets()` (remplace `_TOKEN`, `_SECRET`, `_CAT_SECRET` de moins de 24 caractères) et `placeModuleMenu()` ; enregistre une fois l'onglet **Recherche d'images IA** (`_IMAGEFINDER_TAB_OK`) ; met en file `product-fields.js`, `admin-products-bulk.js` et `image-finder.js` sur `AdminProducts` ; réenregistre `dashboardZoneTwo` s'il manque. `product-fields.js` est mis en file sur chaque page de produit, quelle que soit la valeur de `_PRODUCT`. |
| `displayBackOfficeTop` | Définit des valeurs JavaScript (`admin_controller_url`, `idcms`, `idcategory`, `idmanufacturer`) et affiche la boîte de la barre supérieure lorsque `_TOPCTA` vaut 1. |
| `dashboardZoneTwo` | Affiche `dashboard.tpl`, qui lit des variables `mcg_*` que ce hook n'assigne pas. |
| `displayAdminProductsMainStepLeftColumnMiddle` | Stub vide, renvoie une chaîne vide. |
| `displayAdminProductsMainStepLeftColumnBottom` | Stub vide, renvoie une chaîne vide. |
| `actionProductFormBuilderModifier` | Sans effet, ne renvoie rien. |
| `displayHeader` | Stub vide. |
| `displayFooter` | Stub vide. |

La méthode `hookActionProductGridDataModifier` existe mais n'est pas enregistrée. Le module ne surcharge ni `enable()` ni `disable()` et n'expose aucun hook propre.

### 6.5 Surcharges

Le module n'a aucune surcharge.

### 6.6 Base de données

| Table | Contenu |
|---|---|
| `mychatgpt_prompt` | `id_prompt`, `status` (0/1), `title` (128), `prompt` (text), `date_generated`. Remplie avec 16 lignes. |
| `mychatgpt_log` | `id_log`, `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, `type`, `method`, `status`, `ai_service`, `model`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `error_message`, `prompt`, `reply`, paires `old_*` et `new_*` pour name, description, description_short, meta_title, meta_description et tags, `date_updated`. Index sur `id_product` et `status`. |

La désinstallation supprime les deux tables. `ensureUsageColumns()` ajoute les trois colonnes de jetons à l'ouverture d'un écran, si une table plus ancienne en est dépourvue. Les lignes de produits, de catégories et d'images écrites par le module sont des données standard de PrestaShop et ne sont pas touchées à la désinstallation.

### 6.7 Clés et traductions

Les clés utilisent le préfixe `MYPRESTA_MYCHATGPT_`. Valeurs définies à l'installation :

| Clé | Par défaut |
|---|---|
| `_LIVE_MODE`, `_DEBUG_MODE` | 0 |
| `_TOPCTA`, `_PRODUCT`, `_PRODUCT_LOG` | 1 |
| `_TOKEN`, `_SECRET`, `_CAT_SECRET` | 32 caractères aléatoires |
| `_API_KEY` | Un espace |
| `_MODEL` | gpt-3.5-turbo |
| `_EXTRA_MODELS`, `_MODEL_CAPS` | Vide (le second est rempli à l'exécution avec les paramètres rejetés par modèle) |
| `_TEMPERATURE`, `_TOP_P` | 0.7, 1 |
| `_MAX_TOKENS`, `_TIMEOUT` | 3200, 120 |
| `_FREQ_PEN`, `_PRES_PEN` | 0 |
| `_VOICE`, `_AUDIENCE`, `_TONE`, `_GLOSSARY`, `_FORBIDDEN` | Vide |
| `_BUDGET`, `_QUALITY` | 0, 1 |
| `_IMAGEFINDER_ENABLE`, `_IMAGEFINDER_PROMPT` | 1, long prompt par défaut |
| `_ENABLE_CRON`, `_CRON_INTERVAL`, `_CAT_CRON_INTERVAL` | 0, 6, 6 |
| `updatedField`, `productTarget`, `productsToUpdate`, `promptTemplateId`, `languageId`, `interval_select`, `debug`, `productIdsList` | description, pendingOpenAI, 5, vide, langue par défaut, vide, 0, vide |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catpromptTemplateId`, `catlanguageId`, `catdebug` | description, pendingOpenAI, 5, vide, langue par défaut, 0 |
| `PS_USE_HTMLPURIFIER` | Mis à 0 (pour toute la boutique) |

Les clés cron sans préfixe (`updatedField`, `debug` et les autres ci-dessus) sont des noms globaux et peuvent entrer en collision avec d'autres modules.

Créées plus tard : `_IMAGEFINDER_TAB_OK`, `categories` (choix de catégories cron), `mypresta_updates`, `update_mychatgpt`, `updatev_mychatgpt`. `AdminMyChatGPT::postProcess()` écrit aussi chaque champ de filtre (`_FIELD`, `_LANGUAGE`, `_CONTENT`, `_DELAY`, `_EXISTING`, `_HISTORY`, `_STATUS`, `_STOCK`, `_PROD_IDS`, `_PROD_REF`, `_PROD_DATE_FROM`, `_PROD_DATE_TO`, `_PROD_MIN_ID`, `_PROD_MAX_ID`, `_PROD_LIMIT`, `_CATEGORIES`, `_BRANDS`) dans la configuration à chaque requête de ce contrôleur, mais rien ne les relit.

La désinstallation supprime les clés listées dans `uninstall()`. Elle ne rétablit pas `PS_USE_HTMLPURIFIER`. Elle laisse `categories`, les clés de filtre ci-dessus et les clés de mise à jour.

Les générateurs, le cron et la validation habituelle utilisent `Tools::getValue` avec des listes blanches. La clé API est stockée en clair dans la table de configuration. `randomString()` utilise `rand()`.

Traductions : ajoutez `translations/{iso}.php` au format standard des modules PrestaShop (34 langues sont livrées). Les textes passent par `$this->l()` dans la classe principale, le vérificateur de mises à jour et le tiroir d'aide. Sur PrestaShop 8 et 9, les contrôleurs d'administration utilisent `trans()` avec les domaines `Admin.MyChatGPT`, `Admin.MyChatGPTCron` et `Admin.MyChatGPTUsage`. Non traduits : les messages dans `back.js` et `image-finder.js`, les instructions par défaut utilisées par **Remplir** et **Générer avec l'IA**, la sortie de `cron` et les textes d'erreur de `AdminMyChatGPTProductCreator` et `AdminMyChatGPTImageFinder`. Les longs textes d'aide (« What it does / How to configure / Effect ») sont construits par `fieldHelp()` et se trouvent dans les définitions de formulaires de `mychatgpt.php` et des contrôleurs d'administration (méthode `help()`), dans les gabarits et dans `lib/sectionHelp.php`. Les noms des modèles par défaut et les noms de menu sont écrits en base dans les langues de la boutique à l'installation.

### 6.8 Extension

- Ajoutez ou modifiez des modèles de prompt dans l'écran du module ou dans `mychatgpt_prompt`.
- Ajoutez des variables dans les constructeurs de prompts de `ajax.php` (`updateProduct`, `updateCategory`) et de `cron.php`.
- Ajoutez des modèles dans **Paramètres**, **ChatGPT** sans changer le code. Le module apprend de lui-même les paramètres non pris en charge.
- Modifiez les instructions standard pour **Remplir**, **Générer avec l'IA** et les exécutions en masse dans `back.js` et `product-fields.js`.
- Le front office n'a pas de gabarit, le thème n'a donc rien à remplacer. Les gabarits du back office dans `views/templates` se modifient dans le dossier du module.

## 7. Aide

Page du produit : https://mypresta.eu/modules/administration-tools/my-chatgpt.html

Pour nous écrire à propos du module :

1. Connectez-vous à votre compte client sur mypresta.eu.
2. Ouvrez la page de contact.
3. Choisissez **Support for paid modules**.
4. Décrivez le problème. Indiquez le message exact de l'écran et les étapes qui y mènent. Ne collez jamais votre clé API OpenAI ni une adresse cron complète avec le secret.
