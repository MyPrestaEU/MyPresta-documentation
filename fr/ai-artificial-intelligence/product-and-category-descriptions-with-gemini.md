---
title: My AI Gemini - AI content generation - documentation et manuel d'utilisation
description: Guide de configuration, d'utilisation quotidienne et de dépannage pour les propriétaires de boutique qui ont déjà installé le module My AI Gemini dans le back office de PrestaShop.
sidebar:
  label: My AI Gemini - AI content generation - documentation et manuel d'utilisation
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Product and Category Descriptions with Gemini sur MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/product-and-category-descriptions-with-gemini.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ai-artificial-intelligence/product-and-category-descriptions-with-gemini/)
>
> ---


Les captures d'écran de ce manuel proviennent d'un back office en anglais. Chaque bouton et chaque nom de champ est écrit exactement comme il apparaît à l'écran.

## 1. Prérequis

Avant de commencer, vérifiez que votre boutique et votre serveur répondent aux points ci-dessous.

- **PrestaShop :** 1.6, 1.7, 8 et 9 (toutes les versions de la 1.6 à la 9.99.99).
- **PHP :** 7.0 ou plus récent. L'installateur refuse de continuer avec un PHP plus ancien et affiche le message "This module requires PHP 7.0.0 or newer. This server is running PHP …".
- **Extensions PHP :** cURL (chaque appel à Gemini et chaque téléchargement de page), JSON, DOM (lecture de pages web pour New product et pour la recherche de photos), mbstring et fileinfo (vérification des images téléchargées).
- **Connexion sortante :** votre serveur doit être autorisé à ouvrir des connexions sécurisées (HTTPS) vers le service Google Gemini. Si le serveur bloque les connexions sortantes, rien ne peut être généré.
- **Autres modules :** le module n'a besoin d'aucun autre module.
- **Compte Google :** vous avez besoin de votre propre clé d'API Google Gemini. Créez-la sur https://aistudio.google.com/apikey et gardez-la privée. Google facture ou limite l'utilisation selon votre propre compte Google, et non via ce module.
- **Durée et volume :** chaque champ correspond à une requête vers Gemini. Les textes longs et les modèles lents peuvent prendre plus d'une minute par requête. Une grande exécution en masse ou un grand lot de cron dure autant que toutes ses requêtes additionnées ; commencez donc par de petites listes.

## 2. Installation

1. Ouvrez **Modules**, puis **Module Manager**.
2. Cliquez sur **Upload a module** et déposez le fichier ZIP, ou téléversez-le par votre méthode habituelle.
3. Cliquez sur **Install** à côté du module lorsqu'il apparaît dans la liste, puis confirmez.
4. Après l'installation, une nouvelle entrée nommée **AI Content Generator** apparaît dans le menu de gauche, dans la section **Modules**. Cliquez dessus : le **Dashboard** du module s'ouvre. Les mêmes écrans sont aussi accessibles depuis **Module Manager**, **Configure**.
5. Avant de pouvoir générer quoi que ce soit, ouvrez **Settings**, puis **Gemini**, collez la clé dans **Google Gemini API KEY** et enregistrez (détails au chapitre 3).

L'installation crée 16 modèles de prompt prêts à l'emploi (noms de produits, descriptions, méta-titres, méta-descriptions et étiquettes) pour que vous puissiez essayer le module immédiatement. Elle ne vide pas le cache de la boutique. Si l'entrée de menu n'apparaît pas, ouvrez encore une fois n'importe quelle page du back office : le module remet l'entrée de menu en place à chaque chargement d'une page du back office.

**Désinstallation.** La désinstallation supprime l'entrée de menu **AI Content Generator**, efface les modèles de prompt et tout le History (les listes de restauration sur les produits disparaissent donc aussi), et supprime les réglages du module, y compris la clé d'API et les secrets de cron. Elle ne touche pas aux textes, images et produits déjà rédigés ou créés avec le module. Quelques filtres d'écran que vous avez utilisés sur les pages **Generate** peuvent rester enregistrés dans les réglages de la boutique ; ils sont sans danger. Une nouvelle installation repart d'un état propre : les 16 modèles par défaut reviennent, et les anciens réglages, modèles et History ne sont pas restaurés.

## 3. Configuration et travail quotidien dans le back office

### 3.1 Le processus complet, étape par étape

1. **Connecter Gemini.** **Settings**, **Gemini** : collez la clé d'API, gardez ou changez le modèle, enregistrez.
2. **Tester.** **Settings**, **Playground** : saisissez une courte instruction et appuyez sur **Generate**. Si vous voyez une réponse, la connexion fonctionne. Rien n'est enregistré dans votre catalogue.
3. **Définir le style de la boutique (facultatif).** **Settings**, **Studio** : rédigez la voix de marque, le public, le ton, les mots à conserver et les mots interdits.
4. **Préparer les instructions.** **Settings**, **Prompt templates** : gardez les modèles par défaut ou ajoutez les vôtres. Les modèles activés sont proposés partout ailleurs.
5. **Choisir comment travailler :**
   - Un produit à la fois : ouvrez le produit, puis **Modules**, **My AI Gemini**, et appuyez sur **Fill** à côté d'un champ (3.16).
   - Plusieurs produits ou catégories : **Generate**, **Products** ou **Categories** (3.9 et 3.10).
   - Un produit qui n'existe pas encore : **New product** (3.11).
   - Automatiquement, par petits lots, sans que personne ne clique : **Cron** (3.12).
6. **Vérifier le résultat.** **History** liste chaque requête avec son prompt, sa réponse, son statut et sa consommation de tokens. **Dashboard** montre les mêmes chiffres sous forme de graphiques.
7. **Annuler.** Sur un produit : **Modules**, **My AI Gemini**, **History** : **Restore** remet le texte précédent.

Les textes sont enregistrés directement dans le produit ou la catégorie dès que Gemini répond, sauf là où ce manuel indique autre chose (les boutons **Try**, le **Playground**, **Generate data** et les boutons **Generate with AI** à côté des champs, qui placent seulement le texte dans le formulaire ouvert jusqu'à ce que vous enregistriez).

### 3.2 Ouvrir le module et s'y déplacer

Ouvrez **AI Content Generator** dans le menu de gauche. La barre en haut de chaque écran comporte ces éléments : **Dashboard**, **Settings**, **Generate**, **New product**, **Cron**, **History**, **Images** et, tout à droite, **Updates**. Maintenez la souris sur un élément pour voir une courte explication. Sous **Settings**, une seconde rangée apparaît avec **General**, **Gemini**, **Studio**, **Prompt templates** et **Playground**. Sous **Generate**, la seconde rangée montre **Products** et **Categories**.

Le bouton rond **Help** au bord de chaque page du module ouvre un panneau latéral avec une courte explication de la page où vous vous trouvez. Une ligne de ce panneau fait encore référence à un compte OpenAI (voir le chapitre 5) ; utilisez votre clé Google Gemini.

Vous pouvez aussi accéder au module depuis **Module Manager** avec le bouton **Configure**, depuis le bouton de raccourci de la barre supérieure (3.18) et depuis un lien dans la liste des produits (3.18).

### 3.3 Dashboard

Le **Dashboard** est un rapport. Il n'écrit jamais de texte de produit ou de catégorie.

![My AI Gemini – Dashboard avec plage de dates, cartes et graphiques](https://mypresta.eu/docs/images/docs/myaigemini-dashboard.webp)

En haut, vous choisissez la période. La ligne **Active service** affiche toujours Gemini et le modèle enregistré sur l'écran **Gemini**.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time** | **30 days** | Boutons de période rapide. Celui choisi est mis en évidence. Seuls les chiffres et graphiques de cette page changent. |
| **From** et **To** | Dates des 30 derniers jours | Votre propre période. Appuyez sur **Apply** pour redessiner. Si From est postérieur à To, le module les inverse. |
| **Apply** | – | Redessine les cartes et graphiques pour les dates saisies. |
| **Requests** | Compté depuis History | Chaque appel enregistré dans la période, réussi ou échoué. |
| **Success** | Compté depuis History | Appels qui ne se sont pas terminés par une erreur. |
| **Errors** | Compté depuis History | Appels qui se sont terminés par une erreur. |
| **Tokens sent** | Compté depuis History | Taille totale de vos instructions envoyées à Gemini. |
| **Tokens received** | Compté depuis History | Taille totale des réponses. |
| Graphique **Requests and errors** | – | Courbe, un point par jour. Pour des périodes de plus de 120 jours, un point couvre une semaine. |
| Graphique **Tokens sent and received** | – | Même période, deux courbes. |
| Graphique **Requests by model** | – | Histogramme : combien de requêtes chaque modèle a traitées. |

Si les graphiques sont vides, rien n'a été généré durant cette période. Le Dashboard existe aussi sous la forme d'un petit bloc sur le dashboard principal de PrestaShop, mais ce bloc ne reçoit pas les chiffres de History ; ses cartes et graphiques restent donc vides. Utilisez le **Dashboard** du module.

### 3.4 Settings – General

Ouvrez **Settings**, puis **General**. Ces interrupteurs décident de ce que voient les employés dans le back office. L'enregistrement ne réécrit aucun texte de produit.

![Settings – General](https://mypresta.eu/docs/images/docs/myaigemini-settings-general.webp)

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Live mode** | Disabled | Indique que le module fonctionne sur la vraie boutique. Activez-le sur la boutique de production. Laissez-le désactivé sur une copie de test pour signaler que la configuration n'est pas celle de production. Les mêmes outils fonctionnent dans les deux états. |
| **Debug mode** | Disabled | Écrit des messages techniques supplémentaires dans le journal de PrestaShop (**Advanced Parameters**, **Logs**) lorsqu'un appel à Gemini échoue. Activez-le seulement pendant que vous étudiez une erreur, puis désactivez-le. Les clients ne le voient jamais. |
| **API timeout (seconds)** | 120 | Combien de secondes un appel à Gemini peut durer avant que le module abandonne. 120 convient aux descriptions normales. Montez jusqu'à 600 pour de longs textes SEO ou des modèles lents. Les valeurs inférieures à 10 deviennent 10, celles supérieures à 600 deviennent 600, une valeur vide ou non numérique devient 120. Un délai court échoue vite et enregistre une erreur. |
| **Product Edit History** | Enabled | Affiche l'onglet **History** avec des boutons **Restore** sur la page produit (**Modules**, **My AI Gemini**). Désactivé masque cette liste. Les lignes passées restent dans le **History** global de la boutique dans tous les cas. |
| **Admin Top Bar CTA** | Enabled | Place un petit bouton baguette magique dans la barre supérieure de chaque page du back office, qui ouvre une boîte de prompt. Désactivé supprime seulement ce bouton. Le menu du module reste. |
| **Product edit page Form** | Enabled | Affiche le panneau du générateur sous **Modules**, **My AI Gemini** sur la page produit. Activez-le pour les éditeurs du catalogue. Désactivez-le si seuls la génération en masse et le cron doivent être utilisés. |
| **AI Image Finder** | Enabled | Affiche l'onglet **Photos** sur la page produit. Désactivé le masque. Une image n'est importée qu'après avoir été cochée et confirmée. |
| **AI Image Search Prompt** | Une instruction anglaise intégrée demandant 5 adresses de pages | L'instruction envoyée quand quelqu'un cherche des images de produit. Les mots {product_name} et {product_description} sont remplacés par le produit courant. Conservez la demande d'une liste d'adresses de pages. Un prompt plus précis donne des pages plus pertinentes. |
| **Save** | – | Enregistre tous les champs ci-dessus. Message : **Settings Updated**. |

Les deux champs d'images apparaissent aussi bien ici que sur l'écran **Images** (3.14). Ce sont les deux mêmes réglages.

### 3.5 Settings – Gemini

Ouvrez **Settings**, puis **Gemini**. C'est ici que vous connectez le compte Google et réglez la variété de la formulation. Chaque génération (boutons produit, exécutions en masse, cron, New product, recherche de photos, Playground) utilise ces valeurs.

![Settings – Gemini](https://mypresta.eu/docs/images/docs/myaigemini-settings-gemini.webp)

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Google Gemini API KEY** | Vide | Le secret qui permet à votre boutique d'appeler votre compte Gemini. Collez la clé de https://aistudio.google.com/apikey. Les espaces au début et à la fin sont supprimés. Si vous ne touchez pas à la case, la clé enregistrée est conservée. Une clé vide ou erronée fait échouer les appels et l'erreur est écrite dans History. |
| **Model** | gemini-2.0-flash | Le modèle Gemini qui écrit le texte. Choix intégrés : gemini-2.0-flash, gemini-2.0-flash-lite, gemini-1.5-flash, gemini-1.5-flash-8b, gemini-1.5-pro, gemini-2.5-flash, gemini-2.5-pro. La génération suivante utilise le modèle que vous enregistrez. Un modèle que votre clé ne peut pas utiliser renvoie une erreur au lieu d'un texte. |
| **Add a Gemini model** (case avec **Add model**) | – | Ajoute un nom de modèle qui n'est pas dans la liste intégrée. Saisissez le nom exact de votre compte Gemini, appuyez sur **Add model**. Le nom apparaît dans **Model** et est sélectionné aussitôt. Les noms ajoutés ont un lien **Remove** à côté. Les noms intégrés ne peuvent pas être supprimés. |
| **Max Tokens** | 3200 | Limite supérieure de la longueur d'une réponse, comptée en tokens et non en mots. Environ 256 suffisent pour une méta-description, 1000 ou plus pour une description HTML complète. Une limite basse coupe la réponse. Une limite haute autorise un texte plus long. Certains modèles Gemini 2.5 dépensent une partie de cette limite à « réfléchir » ; gardez-la donc généreuse pour eux. |
| **Temperature** | 0.7 | Avec quelle liberté le modèle choisit les mots. Restez entre 0 et 1. Environ 0.2 convient aux fiches techniques et aux textes méta, environ 0.7 aux descriptions. Une valeur basse répète une structure semblable. Une valeur haute donne une formulation plus variée et un risque accru de s'écarter de la consigne. |
| **Top P** | 1 | Une seconde manière de restreindre le choix du mot suivant. Dans cette version, la valeur est enregistrée mais n'est pas envoyée à Gemini ; la modifier ne change donc pas les réponses. |
| **Frequency Penalty Value** | 0 | Destiné à décourager les formules répétées. Enregistré mais non envoyé à Gemini dans cette version, donc sans effet sur les réponses. |
| **Presence Penalty Value** | 0 | Destiné à pousser le texte vers de nouveaux points. Enregistré mais non envoyé à Gemini dans cette version, donc sans effet sur les réponses. |
| **Save** | – | Enregistre le formulaire. Message : **OpenAi Settings Updated** (le module utilise encore ici l'ancienne formulation). |

Messages que vous pouvez voir sur cet écran :

| Message | Cause | Que faire |
|---|---|---|
| **Google Gemini API KEY field is invalid!** | La case de la clé fait moins de 10 caractères et aucune clé n'est encore enregistrée. | Collez la clé complète et appuyez de nouveau sur **Save**. |
| **OpenAi Model field is invalid!** | Le nom du modèle fait moins de 3 caractères. | Choisissez un nom dans la liste **Model**. |
| **Google Gemini API Key has been automatically cleaned (whitespace removed).** | La clé enregistrée avait des espaces autour. | Rien : le module l'a corrigé. |
| **Model added.** | Le nouveau nom a été enregistré et sélectionné. | Appuyez sur **Save** si vous avez aussi modifié d'autres champs. |
| **That model is already built in.** | Le nom saisi figure déjà dans la liste. | Le module le sélectionne pour vous. |
| **Model removed.** | Un nom ajouté a été supprimé. | S'il s'agissait du modèle actif, choisissez de nouveau un modèle Gemini (voir le chapitre 5). |
| **Built-in models cannot be removed.** | Vous avez essayé de supprimer un nom intégré. | Rien à faire. |
| **Enter a model id such as gpt-4.1.** | La case du nom de modèle était vide ou contenait des caractères interdits. | Saisissez un nom Gemini, par exemple gemini-2.5-flash. L'exemple de ce message est un reste d'ancienne version. |

### 3.6 Settings – Studio

Ouvrez **Settings**, puis **Studio**. Studio ajoute des règles maison par-dessus chaque prompt : boutons produit, exécutions en masse, cron et Playground. Les champs vides sont ignorés. Le module demande aussi toujours à Gemini d'écrire dans la langue de l'élément généré.

![Settings – Studio](https://mypresta.eu/docs/images/docs/myaigemini-settings-studio.webp)

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Brand voice** | Vide | Dit au modèle qui parle afin que le texte ressemble à votre boutique. Rédigez une courte consigne, par exemple : atelier spécialisé, phrases courtes, pas de superlatifs. La modifier ne réécrit pas les textes déjà enregistrés. |
| **Audience** | Vide | Désigne le lecteur, par exemple des installateurs professionnels ou des acheteurs novices. Les nouvelles réponses emploient un vocabulaire adapté à ce lecteur. |
| **Tone** | Vide | Un ou deux mots pour l'ambiance : formel, chaleureux, technique. Cela ne change ni le modèle ni la température. |
| **Glossary** | Vide | Noms de marques, matières et graphies que le modèle doit recopier exactement. Un terme par ligne. Les termes non listés peuvent encore être reformulés. |
| **Forbidden words** | Vide | Mots et expressions qui ne doivent pas apparaître dans une réponse enregistrée. Un par ligne. La liste est aussi envoyée au modèle comme mots à éviter. Le rejet d'une réponse correspondante n'a lieu que lorsque **Quality gate** est activé. |
| **Monthly generation budget** | 0 | Nombre maximal de générations réussies dans le mois calendaire en cours, compté depuis History. 0 signifie sans limite. Quand le plafond est atteint, les nouvelles requêtes s'arrêtent avec un message de budget jusqu'au mois suivant. Les appels échoués ne sont pas comptés. |
| **Quality gate** | Enabled | Vérifie chaque réponse par rapport à **Forbidden words** avant que quoi que ce soit soit enregistré. Activé rejette une réponse correspondante : le produit reste inchangé et History enregistre une erreur. Désactivé enregistre la réponse même si elle contient un mot listé. Avec une liste Forbidden words vide, la barrière n'a rien à vérifier. |
| **Save studio** | – | Enregistre le formulaire. Message : **Studio settings saved.** |

### 3.7 Settings – Prompt templates

Ouvrez **Settings**, puis **Prompt templates**. Un modèle est une instruction enregistrée. Les éditeurs le choisissent par son titre au lieu de retaper la même consigne.

![Settings – Prompt templates](https://mypresta.eu/docs/images/docs/myaigemini-settings-templates.webp)

La liste affiche ces colonnes : **ID**, **Title**, **Prompt**, **Status** (cliquez sur la coche ou la croix pour activer ou désactiver le modèle), **Timestamp**. Chaque ligne a **Edit** et **Delete**. Cochez plusieurs lignes et utilisez l'action groupée **Delete** (on vous demande "Are you sure you want to delete the selected prompts?"). Le bouton vert plus au-dessus de la liste crée un nouveau modèle.

Le formulaire de modèle :

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Status** | Interrupteur Enabled / Disabled | Affiche ou masque le modèle dans les listes utilisées sur la page produit, dans la boîte de prompt de la barre supérieure, dans la génération en masse et dans le cron. Activez les modèles que votre équipe doit utiliser. Désactivez un brouillon plutôt que de le supprimer. |
| **Prompt title** | Vide (obligatoire) | Le nom que les éditeurs voient dans la liste. Il n'est pas envoyé à Gemini. Utilisez une étiquette courte, par exemple HTML description with features. |
| **Prompt content** | Vide (obligatoire) | L'instruction envoyée à Gemini. Rédigez-la comme vous briefiez un rédacteur : longueur, HTML, langue. Vous pouvez utiliser des variables (3.19). Les guillemets doubles sont remplacés par des guillemets simples à l'enregistrement. |
| **Save Prompt** | – | Enregistre le modèle. |
| **Go Back to Module Settings** | – | Revient à la liste sans enregistrer. |

Messages : **Prompt template successfully added!**, **Prompt template successfully updated!**, **Prompt template removed.**, **Unable to delete prompt template with id:** suivi d'un numéro, **Failed to edit prompt template! Please fill the form with the right informations!**.

Les 16 modèles par défaut sont : Product name 1–2, Product description 1–7 (le septième intègre les liens des images du produit), Product meta title 1–3, Product meta description 1–3 et Product tags. Deux des modèles de méta-description mentionnent une montre connectée ; modifiez-les avant de les utiliser si vous vendez autre chose. Les textes des modèles sont enregistrés dans la langue qu'utilisait la boutique lors de l'installation.

### 3.8 Settings – Playground

Ouvrez **Settings**, puis **Playground**. C'est un brouillon : il envoie une instruction libre au modèle actif et affiche la réponse sur la page.

![Settings – Playground](https://mypresta.eu/docs/images/docs/myaigemini-settings-playground.webp)

1. Saisissez l'instruction dans la grande case ("Ask the model anything about your catalog").
2. Appuyez sur **Generate**.
3. Lisez la réponse sous le bouton, avec le nombre de tokens utilisés.

Vous pouvez mentionner le nom de la boutique, son adresse, un nom de produit, une référence ou des caractéristiques si vous voulez que la réponse s'appuie sur les données du catalogue. Les règles de Studio sont appliquées. Aucun produit, aucune catégorie ni aucun champ méta n'est modifié, et l'appel est enregistré dans History. Si la case est vide, vous voyez "Write a prompt first." Utilisez le Playground pour tester la clé et peaufiner un prompt avant d'en faire un modèle.

### 3.9 Generate – Products

Ouvrez **Generate**, puis **Products**. La génération en masse comporte deux étapes. Rien n'est envoyé à Gemini pendant l'étape 1.

![Generate – Products](https://mypresta.eu/docs/images/docs/myaigemini-generate-products.webp)

**Étape 1 – filtrer les produits.** Tous les filtres sont facultatifs et ne sont pas enregistrés comme réglages de la boutique.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Product Categories** | Rien de coché | Conserve les produits qui se trouvent dans l'une des catégories cochées ou l'ont pour catégorie principale. Un arbre vide ne filtre pas par catégorie. |
| **Brand** | **Select brand** | Conserve les produits d'un fabricant. La première option signifie toutes les marques. |
| **Product status** | **Active** | **Active** conserve les produits en vente, **Disabled** les produits désactivés, **Both** tous. |
| **Product stock** | **All products** | **Only in stock products** écarte les produits sans quantité disponible. |
| **Update only** | **Update all** | Utilise History. La première option conserve les produits que ce module n'a jamais rédigés. La seconde conserve ceux qu'il a déjà rédigés. Les libellés disent encore "OpenAi content" (voir le chapitre 5). |
| **Product IDs** | Vide | Saisissez des ids séparés par des virgules, par exemple 12,45,103. Seuls ces produits peuvent apparaître. |
| **Product Reference** | Vide | Saisissez une ou plusieurs références séparées par des virgules. |
| **Product Add Date From** / **Product Add Date To** | Vide | Conservent les produits créés après la première date et avant la seconde. |
| **Minimum product ID** / **Maximum product ID** | Vide | Conservent les produits dans cette plage d'ids. |
| **Product Limit** | Vide | Nombre maximal de produits chargés dans la liste. Utilisez un petit nombre comme 20 la première fois. |
| **Go to next step** | – | Construit la liste. |
| **Module settings** | – | Bouton à côté de **Go to next step**. Il ouvre la page de réglages d'un autre module (voir le chapitre 5) ; utilisez plutôt **Settings** dans la barre du module. |

**Étape 2 – rédiger.** La page affiche maintenant le panneau **Mass product generation** avec un tableau des produits trouvés (colonnes **ID**, **Reference**, **Result**).

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Template** | **Choose a template** | Copie le texte d'un modèle activé dans la case ci-dessous. Le titre lui-même n'est pas envoyé. |
| Grande case de prompt | Vide | L'instruction envoyée pour chaque produit. Les variables sont remplies pour chaque produit (3.19). Si vous la laissez vide, une instruction standard pour chaque champ est utilisée. |
| **What to generate** | **Descriptions** | **Descriptions** rédige la description longue et la courte. **Meta title and meta description** rédige les deux champs méta. **Descriptions and meta together** rédige les quatre. Chaque champ est une requête distincte. Les autres champs (y compris le nom du produit et les étiquettes) ne sont jamais modifiés ici. |
| **Existing text** | **Replace** | **Replace** écrase le champ. **Skip if filled** laisse tranquille un champ rempli et n'envoie rien à Gemini pour lui. **Add above** et **Add below** conservent l'ancien texte et ajoutent le nouveau avant ou après. |
| **Languages** | La langue que vous utilisez dans le back office est cochée | Cochez chaque langue souhaitée. Chaque langue cochée est générée séparément. Au moins une doit être cochée ("Select at least one language."). |
| **Run on the list below** | – | Lance l'exécution. |

Pendant l'exécution, la ligne au-dessus du bouton montre la progression, par exemple "3 / 40 – description". Chaque ligne du tableau affiche un résultat tel que "description: success Content successfully generated and updated to product." ou "description: skipped Product skipped." ou un texte d'erreur. L'exécution prend les produits un par un et enregistre chaque réponse immédiatement ; l'échec sur un produit n'annule donc pas ceux déjà enregistrés. Ne fermez pas la page avant de voir "Finished … products."

### 3.10 Generate – Categories

Ouvrez **Generate**, puis **Categories**.

![Generate – Categories](https://mypresta.eu/docs/images/docs/myaigemini-generate-categories.webp)

**Étape 1 – filtrer les catégories.**

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Categories** | Rien de coché | Cochez les catégories à inclure. Un arbre vide inclut toutes les catégories correspondant au statut. |
| **Category status** | **Active** | **Active**, **Disabled** ou **Both**. |
| **Go to next step** | – | Construit la liste. Rien n'est encore généré. |
| **Module settings** | – | Ouvre la page de réglages d'un autre module (voir le chapitre 5). |

**Étape 2 – rédiger.** Le panneau **Mass category generation** liste les catégories (colonnes **ID**, **Result**).

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| Grande case de prompt | Vide | L'instruction envoyée pour chaque catégorie. Vous pouvez utiliser {category_name}, {category_description}, {category_parent_name} et les variables de la boutique (3.19). Saisissez toujours un prompt ici : pour les catégories, il n'existe pas d'instruction standard. |
| Liste de champs | **Description** | **Description**, **Name**, **Meta title**, **Meta description** ou **Additional description**. Seul ce champ est enregistré. |
| Liste du texte existant | **Replace** | **Replace** écrase. **Skip if filled** laisse tranquille un champ rempli. |
| Liste des langues | Votre langue du back office | Une langue par exécution. Relancez pour une autre langue. |
| **Run on the categories below** | – | Lance l'exécution. Chaque catégorie est enregistrée dès que sa réponse arrive. |

Sous le tableau se trouve un second formulaire intitulé **Generate category content** avec un bouton **Generate content**. Il ne génère rien : il vous ramène seulement au filtre des catégories. Utilisez toujours **Run on the categories below**.

### 3.11 New product

Ouvrez **New product**. Cet écran transforme une courte consigne en brouillon d'un produit qui n'existe pas encore.

![New product](https://mypresta.eu/docs/images/docs/myaigemini-new-product.webp)

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **What is the product?** | Vide | La consigne. Rédigez quelques phrases avec les matières, le public et les noms qui doivent être conservés. Une consigne plus riche donne un brouillon plus proche. Une consigne vide est refusée. |
| **Optional source URL** | Vide | L'adresse complète d'une page publique consacrée au produit. Le texte de la page (titre, description, prix) est ajouté à votre consigne. Une case vide ou une page que la boutique ne peut pas lire est ignorée. |
| **Language** | Langue par défaut de la boutique | La langue dans laquelle nom, descriptions, méta et étiquettes sont enregistrés. Les autres langues ne sont pas remplies. Choisissez la langue par défaut de la boutique, car PrestaShop attend un nom dans cette langue. |
| **Default category ID** | 2 | Le numéro de la catégorie dans Catalog, Categories. 2 est généralement Home. Le nouveau produit est placé dans cette catégorie et elle devient la catégorie par défaut. |
| **Generate data** | – | Demande un brouillon à Gemini et l'affiche en dessous sous forme de texte structuré (nom, descriptions, méta, étiquettes, référence, prix, caractéristiques). Aucun produit n'est enregistré. |
| **Create product** | – | Enregistre le brouillon comme nouveau produit actif. Il définit nom, descriptions, méta, étiquettes, caractéristiques, référence et prix à partir du brouillon, la visibilité partout, et un stock de 100. Aucune image n'est jointe ; ajoutez-les ensuite (3.16). Ligne de résultat : "Product #" suivi du numéro du nouveau produit. |

Si aucune clé d'API n'est enregistrée, vous voyez "Add an API key in the module settings first." Appuyer sur **Create product** avant **Generate data** affiche "Generate the product first." Après la création, vérifiez le prix, la taxe et les images : le module applique le premier groupe de règles de taxe et le prix suggéré par Gemini.

### 3.12 Cron

Ouvrez **Cron**. Le cron est destiné au serveur, pas à une personne : votre serveur appelle une adresse web secrète selon un calendrier et la boutique remplit à chaque fois un petit lot de produits ou de catégories. Il ne se passe rien tant que le serveur ne demande pas l'adresse.

![Cron](https://mypresta.eu/docs/images/docs/myaigemini-cron.webp)

L'écran comporte deux formulaires : un pour les produits et un pour les catégories. Chacun a son propre bouton **Save**, et aucun message de confirmation n'est affiché après l'enregistrement.

**Formulaire de cron des produits**

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Enable Cron Feature** | **No** | Interrupteur de tout le cron (produits et catégories). Tant qu'il est sur **No**, chaque appel est refusé avec "Cron Job feature is disabled. You can enable it from the module settings." Activez-le seulement après avoir enregistré les autres champs. |
| **Cron Job Secret Token** | Une longue valeur aléatoire | Le mot de passe qui doit figurer dans l'adresse. Sans lui, la boutique refuse l'appel. Le remplacer invalide l'ancienne adresse. Le bouton **Generate Token** à côté du champ peut ne rien faire dans cette version ; dans ce cas, saisissez vous-même une longue valeur. |
| **Update Field** | **description** | Quel unique champ de produit le cron réécrit : **name**, **description**, **description_short**, **meta_title**, **meta_description** ou **tags**. Pour remplir plusieurs champs, créez plusieurs commandes de cron. |
| **Selected Products** | **pendingGemini** | Quels produits attendent encore. **pendingGemini** : produits que ce module n'a jamais rédigés avec succès (n'importe quel champ). **pendingField** : produits pas encore générés pour le champ choisi, ce qui permet de traiter un catalogue avec plusieurs cron jobs. **emptyField** : seulement les produits dont le champ choisi est vide dans la langue choisie. |
| **Product Categories** | Rien de coché | Limite l'exécution aux catégories cochées (voir le chapitre 5 pour une mise en garde). |
| **Product ID list** | Vide | Ids de produits explicites séparés par des virgules. Les caractères autres que les chiffres sont supprimés à l'enregistrement. |
| **Language** | Langue par défaut de la boutique | La version linguistique qui est rédigée. |
| **Product to update** | 5 products | Taille du lot par appel : 2, 3, 5, 8, 10, 15, 20, 50, 100, 200, 300, 500 ou 1000. Commencez par 5 ou 10 pour qu'un modèle lent n'atteigne pas la limite de temps du serveur. Les produits sont pris dans l'ordre des ID. |
| **Prompt Template** | Premier modèle de la liste | L'instruction enregistrée utilisée pour chaque produit. Les variables sont remplies pour chaque produit (3.19). |
| **Enable Debug** | **No** | **Yes** fait afficher le plan à l'adresse (requête, produits sélectionnés, prompts finaux) et n'enregistre rien. Désactivez-le avant que le planificateur du serveur utilise l'adresse. |
| **CRON JOB interval** | **Every Hour** | Une suggestion affichée pour votre propre planification. Le module n'exécute aucun planificateur. Réglez le vrai calendrier sur votre serveur. |
| **Product Cron Job command** | – | Affiche le préfixe de l'adresse. Dans cette version, la ligne de commande à l'écran est incomplète (voir ci-dessous). |
| **Save** | – | Enregistre les réglages du cron des produits. |

Le **formulaire de cron des catégories** a son propre **Cron Job Secret Token**, **Update Field** (**name**, **description**, **meta_title**, **meta_description**), **Selected categories** (les mêmes trois modes), **Language**, **Categories to update** (2–1000), **Prompt Template**, **Enable Debug**, **CRON JOB interval** et **Save**. Il ignore toujours la catégorie racine de la boutique.

**L'adresse que vous donnez au serveur.** Au-dessus des formulaires, l'écran affiche une adresse pour les produits et une pour les catégories, chacune se terminant après le secret. Il faut aussi dire au serveur quelle tâche exécuter. Ajoutez ceci à la fin de l'adresse affichée à l'écran :

| Tâche | Adresse complète | Remarques |
|---|---|---|
| Produits | `https://your-shop.example/module/myaigemini/cron?secret=PRODUCT_SECRET&action=generateProductContent` | Utilisez le secret du formulaire des produits. |
| Catégories | `https://your-shop.example/module/myaigemini/cron?secret=CATEGORY_SECRET&action=generateCategoryContent` | La ligne des catégories à l'écran se termine par `&entity=category` ; remplacez cette fin par `&action=generateCategoryContent`. |

Ajouts facultatifs que vous pouvez joindre pour remplacer le formulaire enregistré le temps d'une commande : pour les produits `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug=1`, `categories` (ids séparés par des virgules), `productIds` ; pour les catégories `updatedField`, `categoryTarget`, `categoriesToUpdate`, `languageId`, `promptTemplateId`, `debug=1`. Les valeurs non ajoutées proviennent du formulaire enregistré.

**Planificateur.** Dans le panneau de votre hébergeur, créez une tâche planifiée qui ouvre l'adresse complète, par exemple avec `curl -s "ADDRESS"` toutes les heures. Testez d'abord dans un navigateur avec **Enable Debug** sur **Yes** : vous voyez quels produits seraient traités et les prompts finaux. Passez ensuite sur **No** et ouvrez l'adresse une fois de plus. Chaque appel réel met à jour un lot puis s'arrête.

Réponses que vous pouvez voir à l'ouverture de l'adresse :

| Réponse | Cause | Que faire |
|---|---|---|
| **N products have been updated.** / **N categories have been updated.** | Le lot a fonctionné. | Rien. |
| **N pending products.** | Le debug est activé, rien n'a été enregistré. | Désactivez le debug quand vous êtes satisfait. |
| **No products to update.** / **No categories to update.** | Plus rien ne correspond à **Selected Products** et aux autres filtres. | Le travail est terminé, ou modifiez la règle. |
| **Cron Job feature is disabled. You can enable it from the module settings.** | **Enable Cron Feature** est sur **No**. | Mettez-le sur **Yes** et appuyez sur **Save**. |
| **The token does not exist or it's wrong!** | Le secret est absent ou ne correspond pas. | Recopiez l'adresse depuis l'écran. |
| **Invalid action!** | L'adresse n'a pas de partie `action`, ou une partie erronée. | Ajoutez la partie `action` du tableau ci-dessus. |
| **updatedField parameter is wrong!** | Le champ n'est pas autorisé pour cette tâche. | Choisissez un champ du formulaire. |
| **All must include all mandatory parameters!** | Une valeur enregistrée (par exemple le modèle) est vide. | Choisissez un **Prompt Template** et enregistrez. |
| **productTarget parameter is wrong! Allowed values: …** | Le nom du mode dans l'adresse est erroné. | Utilisez l'un des trois modes. |
| **Error!** suivi d'un message | Gemini a refusé ou échoué. | Lisez le message, puis vérifiez History. |
| **Error! The model returned an empty response.** | Gemini n'a rien renvoyé, par exemple parce que la limite Max Tokens était trop basse. | Augmentez **Max Tokens** sur l'écran **Gemini**. |
| **Monthly generation budget reached.** | Le budget de Studio est épuisé. | Augmentez le budget ou attendez le mois prochain. |
| **Reply rejected by the studio quality gate.** | La réponse contenait un mot interdit. | Modifiez la liste ou le modèle. |
| **Error! Could not save product …** | PrestaShop a refusé le nouveau texte (par exemple trop long). | Vérifiez le champ et le prompt. |

Un appel de cron s'arrête à la première erreur et indique combien d'éléments avaient déjà été mis à jour avant elle.

### 3.13 History

Ouvrez **History**. C'est le journal de ce qui a été demandé et de ce qui est revenu. Ouvrir ou filtrer la page ne supprime rien et ne modifie pas les produits.

![History](https://mypresta.eu/docs/images/docs/myaigemini-history.webp)

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Today**, **7 days**, **30 days**, **This month**, **All time** | **This month** | Préréglages de dates. |
| **From** / **To** | Le mois en cours | Votre propre période. |
| **Model** | **Any** | Seulement les requêtes faites avec ce modèle. |
| **Type** | **Any** | Un seul type de tâche, par exemple une description de produit ou un méta-titre de catégorie. |
| **Status** | **Any** | **Success** ou **Error**. |
| **Language** | **Any** | Seulement les requêtes pour cette langue. |
| **Employee** | **Any** | Seulement les requêtes lancées par cet utilisateur du back office. |
| **Product / category ID** | Vide | Un numéro de produit ou de catégorie. |
| **Prompt or reply contains** | Vide | Un mot qui doit figurer dans le prompt, la réponse ou le texte d'erreur. |
| **Filter** | – | Applique les filtres. |

Cartes : **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time**. Un tiret dans une colonne de tokens signifie que Gemini n'a pas renvoyé de décompte pour cet appel. En dessous, cinq tableaux regroupent les requêtes filtrées : **By day**, **By model**, **By type**, **By language**, **By employee**, avec une petite barre montrant la part des tokens. Un petit nombre en italique à côté d'un nombre d'appels est le nombre d'erreurs.

La liste du bas comporte les colonnes **ID**, **Status** (**Success** en vert ou **Error** en rouge), **Prompt** (180 premiers caractères), **Reply / Error**, **Provider** (service, modèle et durée), **Sent**, **Received**, **Total**, **Entity ID**, **Type**, **Timestamp**, et un bouton **View** qui ouvre le prompt complet et la réponse avec **Back to the list**. La liste affiche 50 lignes par page.

Le bouton de la barre d'outils **Clear list** supprime d'un coup toutes les lignes de History, sans demander. Ne le faites que volontairement : les boutons de restauration sur les produits, le compteur du budget mensuel et les modes de cron **pendingGemini** et **pendingField** reposent tous sur History ; après l'avoir vidé, le cron considère donc chaque produit comme pas encore rédigé.

### 3.14 Images

Ouvrez **Images**. Cet écran active ou désactive seulement la recherche de photos de produit et enregistre son instruction. Il ne télécharge aucune image.

![Images](https://mypresta.eu/docs/images/docs/myaigemini-images.webp)

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **AI Image Finder** | Enabled | Affiche l'onglet **Photos** sur la page produit. Désactivé le masque. |
| **AI Image Search Prompt** | Instruction anglaise intégrée | L'instruction qui demande à Gemini des adresses de pages où se trouvent probablement des photos de ce produit. {product_name} et {product_description} sont remplacés pour le produit courant. Conservez la demande d'une simple liste d'adresses. |
| **Save** | – | Enregistre les deux champs. Message : **Settings saved.** |

La recherche trouve des pages web qui montrent déjà votre produit ; elle ne crée pas d'images. Vérifiez que vous avez le droit d'utiliser chaque image que vous importez.

### 3.15 Updates

Ouvrez **Updates** (tout à droite de la barre du module). La page interroge MyPresta.eu pour savoir s'il existe un fichier de module plus récent. Elle ne modifie pas votre catalogue et n'installe rien.

![Updates](https://mypresta.eu/docs/images/docs/myaigemini-updates.webp)

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Manual Check** (**Check Now**) | – | Interroge une fois, immédiatement. Vous voyez **Module is up to date!** ou **New version available!**. |
| **Automatic Notifications** | Interrupteur Enabled ou Disabled | Enabled : environ tous les trois jours, le back office vérifie et affiche une bannière d'avertissement avec un lien lorsqu'une version plus récente existe. Ce réglage est partagé avec les autres modules MyPresta de la même boutique. |
| **Product Page** | – | Un lien vers la page du module sur MyPresta.eu, où vous pouvez lire ce qui a changé et télécharger le fichier. |
| **Save** | – | Enregistre le réglage des notifications. Message : **Update settings saved.** |

### 3.16 Travailler sur la page d'édition du produit

Ouvrez **Catalog**, **Products**, modifiez un produit et ouvrez **Modules**, puis **My AI Gemini**. Le produit doit avoir déjà été enregistré une fois. Le panneau apparaît lorsque **Product edit page Form** ou **Product Edit History** (3.4) est activé.

![Page d'édition du produit – panneau My AI Gemini](https://mypresta.eu/docs/images/docs/myaigemini-product-edit.webp)

Le panneau comporte jusqu'à quatre onglets : **Generate**, **Simulate**, **Photos** et **History**.

**Onglet Generate**

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| Boutons **Language** | La première langue | Choisissez quelle version linguistique est rédigée. **Every language** rédige toutes les langues actives, l'une après l'autre. |
| **If the field already has text** | **Replace** | **Replace**, **Add above**, **Add below** ou **Skip if filled**. Skip n'envoie rien à Gemini pour un champ rempli. |
| Cartes de champs | – | **Description**, **Short description**, **Name**, **Meta title**, **Meta description**, **Tags**. Appuyez sur **Fill** sur la carte pour rédiger ce champ et l'enregistrer aussitôt sur le produit. |
| **SEO pack** – **Fill all** | – | Rédige le nom, les deux descriptions et les deux champs méta en une seule requête et les enregistre. |
| **Use your own instruction or a saved prompt** | Fermé | Ouvrez-le pour filtrer les modèles enregistrés par titre ou texte, choisir une vignette (**Standard brief** ou un modèle activé) et modifier la case **Instruction**. Si la case est vide, **Fill** utilise une instruction standard pour le champ. |

La réponse s'affiche sous le panneau. Le texte est enregistré aussitôt sur le produit, mais les champs du formulaire produit ouvert ne se rafraîchissent pas d'eux-mêmes : rechargez la page produit avant de modifier puis d'enregistrer dans le formulaire, sinon les anciennes valeurs du formulaire peuvent écraser le nouveau texte.

**Onglet Simulate.** Même choix de langue et mêmes cartes de champs, mais les boutons s'appellent **Try**. La réponse reste sur cette page et le produit n'est pas modifié. Utilisez-le pour vérifier d'abord la formulation.

![Page d'édition du produit – onglet Photos](https://mypresta.eu/docs/images/docs/myaigemini-product-photos.webp)

**Onglet Photos.** Appuyez sur **Find pages**. Le module demande à Gemini jusqu'à 5 pages qui montrent probablement ce produit, lit jusqu'à 24 images sur celles-ci et les affiche en petites vignettes. Cochez celles que vous voulez et appuyez sur **Add selected to this product**. La première image cochée devient l'image de couverture si vous en ajoutez plusieurs. Rien n'est enregistré avant que vous appuyiez sur le bouton. La ligne sous les boutons indique la progression : "Looking for photos…", "Reading photos…", "Tick the photos you want, then add them to this product." Après l'ajout, rechargez la page produit pour les voir. Si l'interrupteur est désactivé, vous voyez une note vous invitant à activer **AI Image Finder** sous **Settings**, **General**.

**Onglet History.** Un tableau avec **When**, **Type**, **Status** et un bouton **Restore** pour chaque écriture réussie qui a conservé une valeur précédente. Appuyez sur **Restore**, confirmez "Restore the previous value?" et le texte précédent revient. Les lignes en échec n'ont pas de bouton. Un SEO pack restauré rétablit le nom, les deux descriptions et les deux champs méta. Sans aucune ligne, vous voyez "No generations for this product yet."

**Boutons Generate with AI à côté des champs.** Sur la page produit, le module ajoute aussi un bouton **Generate with AI** à côté des champs description, description courte, méta-titre et méta-description. Si la boutique a plus d'une langue, il demande "Generate this field for the current language, or for every active language?" avec **Current language**, **All languages** et **Cancel**. Le texte va seulement dans le formulaire ouvert : "Text is in the field. Save the product to keep it." Les autres champs ne sont pas modifiés. Pour un produit qui n'a jamais été enregistré, vous voyez "Save the product once before generating."

### 3.17 Travailler sur la page d'édition de la catégorie

Modifiez une catégorie dans **Catalog**, **Categories**. À côté des champs description, description supplémentaire, méta-titre et méta-description, le module ajoute le bouton **Generate with AI**. Il fonctionne exactement comme sur les produits : choisissez la langue courante ou toutes les langues, le texte est placé dans le formulaire, et vous enregistrez la catégorie pour le conserver ("Text is in the field. Save the category to keep it."). Une catégorie qui n'a jamais été enregistrée affiche "Save the category once before generating." La même boîte de prompt de la barre supérieure (3.18) fonctionne aussi sur les pages de catégorie, de pages CMS et de marque et les enregistre dans History.

### 3.18 Raccourcis : barre supérieure, liste des produits et Help

- **Bouton de la barre supérieure.** Avec **Admin Top Bar CTA** activé, une icône baguette magique se trouve dans la barre supérieure. Elle ouvre la boîte **My AI Gemini** avec une liste **Template**, une zone de texte et **Generate**. La réponse est affichée sous le bouton, avec le nombre de tokens. Elle ne modifie aucun champ. Utilisez la **×** pour fermer.
- **Liste des produits.** Sur la liste des produits de **Catalog**, **Products**, le module ajoute un lien **My AI Gemini** à côté des actions groupées ou dans la barre d'outils. Il ouvre **Generate**, **Products**.
- **Help.** Le bouton **Help** de chaque page du module ouvre l'explication de la page.

### 3.19 Variables utilisables dans les prompts

Dans les modèles, la case **Instruction**, les cases de prompt en masse et le Playground, vous pouvez écrire des variables entre accolades. Le module les remplace par de vraies données pour chaque élément avant d'envoyer l'instruction.

| Variable | Fonctionne pour | Ce qu'elle devient |
|---|---|---|
| {product_name}, {product_description}, {product_description_short}, {product_tags}, {product_reference}, {product_ean13}, {product_weight} | Produits | Les données propres du produit dans la langue choisie. |
| {product_default_category}, {product_category_description}, {product_categories}, {product_brand} | Produits | Nom et description de la catégorie principale, noms de toutes les catégories (séparés par des virgules), nom de la marque. |
| {product_attributes}, {product_features}, {product_feature_values} | Produits | Attributs des déclinaisons, noms de caractéristiques et paires nom de caractéristique:valeur. |
| {product_images} | Produits | Les liens des images du produit, séparés par des virgules. |
| {category_name}, {category_description}, {category_parent_name} | Catégories | Les données propres de la catégorie et le nom du parent. |
| {cms_title}, {brand_name}, {brand_description}, {brand_short_description} | Pages CMS, marques (boîte de la barre supérieure) | Le titre de la page ou les données de la marque. |
| {shop_name}, {shop_url}, {shop_language}, {shop_country}, {shop_currency} | Tout | Nom de la boutique, domaine, nom de la langue, pays par défaut et code de la devise par défaut. |

Une variable sans données devient un texte vide. Les variables de catégories ne sont pas remplacées dans les prompts de produits, et inversement.

## 4. Vitrine de la boutique

My AI Gemini n'a pas d'interface client. Il n'ajoute rien aux pages produit, aux pages catégorie, au panier, au pied de page ni au compte client, et il n'y a rien à activer ou désactiver dans le thème. La vitrine ne reçoit aucun template du module ; aucune capture d'écran n'est donc présentée.

Le module possède deux adresses web qui ne sont pas des pages pour les clients :

| Adresse | Qui l'utilise | À savoir |
|---|---|---|
| Adresse du cron (`…/module/myaigemini/cron?secret=…&action=…`) | Le planificateur de votre serveur | Décrite en 3.12. Ouverte sans le bon secret, elle répond seulement "The token does not exist or it's wrong!". Gardez-la privée : quiconque la connaît peut lancer un lot. |
| Adresse interne utilisée par les écrans du module | Les propres boutons du module dans le back office | Ne l'ouvrez pas et ne la partagez pas. Elle rejette les requêtes sans le secret propre au module ("Error! Invalid token!"). |

## 5. Problèmes

**Rien n'est généré et je vois le message "The Gemini API key is not set. Add it in the module settings."**
La case de la clé sous **Settings**, **Gemini** est vide. Collez la clé de https://aistudio.google.com/apikey et appuyez sur **Save**.

**Une erreur de Google apparaît dans un résultat, dans History ou dans une réponse de cron (par exemple un message commençant par "Google Gemini API Error").**
Google a refusé l'appel : clé erronée ou désactivée, modèle que votre clé n'a peut-être pas le droit d'utiliser, quotas gratuits épuisés ou région bloquée. Ouvrez **History**, appuyez sur **View** sur la ligne rouge pour lire le texte complet. Corrigez la clé ou choisissez un autre modèle sous **Settings**, **Gemini**, puis réessayez.

**"Gemini request timed out after … seconds. The model may be overloaded, or the timeout is too low for this prompt."**
Le modèle a eu besoin de plus de temps que **API timeout (seconds)**. Augmentez le délai sous **Settings**, **General** (jusqu'à 600), raccourcissez le texte ou choisissez un modèle plus rapide comme gemini-2.0-flash.

**"The model hit the token limit before returning any text. Increase "Max Tokens" …" ou "The model returned an empty response."**
La réponse a été coupée ou est vide. Augmentez **Max Tokens** sous **Settings**, **Gemini**. Certains modèles Gemini 2.5 utilisent une partie de la limite pour « réfléchir ».

**"The response was blocked by the provider content filter. Try rewording the prompt."**
Google a refusé de répondre à l'instruction. Réécrivez le modèle ou le texte du produit qu'il utilise.

**"Monthly generation budget reached. Raise it in the studio settings or wait until next month."**
Le plafond sous **Settings**, **Studio**, **Monthly generation budget** est épuisé. Augmentez-le ou mettez 0 pour supprimer la limite.

**"The reply was rejected because it contains a forbidden word from the studio settings."**
**Quality gate** est activé et la réponse contenait une ligne de **Forbidden words**. Le produit est resté inchangé. Modifiez la liste, changez le prompt ou désactivez la barrière.

**"Error! Prompt is missing or too short!"**
L'instruction fait moins de 4 caractères. Saisissez une instruction complète ou choisissez un modèle.

**Une ligne d'exécution en masse affiche "skipped Product skipped."**
**Existing text** est sur **Skip if filled** et le champ contenait déjà du texte. Choisissez **Replace**, **Add above** ou **Add below** pour écrire malgré tout.

**Après avoir supprimé un modèle ajouté, toutes les requêtes échouent.**
Supprimer le modèle actif remet le nom du modèle à gpt-4o, que Gemini ne connaît pas. Ouvrez **Settings**, **Gemini**, choisissez un nom Gemini dans **Model** (par exemple gemini-2.0-flash) et appuyez sur **Save**.

**Les écrans parlent encore d'"OpenAi" ou de "gpt".**
Cette version conserve encore quelques formulations d'une version plus ancienne : la confirmation **OpenAi Settings Updated**, l'erreur **OpenAi Model field is invalid!**, les libellés de filtre "Products that have not been updated with OpenAi content" et "Products that already have been updated with OpenAi content" sous **Generate**, **Products**, l'exemple "gpt-4.1" dans la case du modèle et dans le message "Enter a model id such as gpt-4.1.", le nom de service "openai" dans la colonne **Provider** de History, et la ligne du panneau **Help** "Paste the secret key from your OpenAI account". Tout cela n'est que de la formulation. Le module appelle Google Gemini. Utilisez une clé de https://aistudio.google.com/apikey et des noms de modèles Gemini.

**Le bouton "Module settings" sur Generate ouvre la page d'un autre module ou une erreur.**
Ce bouton pointe vers les réglages d'un ancien module frère et non vers celui-ci. Utilisez **Settings** dans la barre du module.

**Le formulaire du bas "Generate category content" ne fait rien.**
Il recharge seulement le filtre des catégories. Appuyez sur **Run on the categories below** dans le panneau au-dessus.

**Le cron des produits ne fait rien.**
Vérifiez, dans cet ordre : **Enable Cron Feature** est sur **Yes** et enregistré ; l'adresse contient `&action=generateProductContent` ; le secret dans l'adresse correspond à l'écran ; un **Prompt Template** est choisi ; **Enable Debug** est sur **No** ; votre serveur appelle réellement l'adresse (consultez le journal de son planificateur). Un test dans le navigateur avec **Enable Debug** sur **Yes** affiche ce qui serait exécuté.

**La commande de cron à l'écran se termine juste après le secret et le bouton "Generate Token" ne fait rien.**
Limitation connue de cette version. La ligne de commande n'est pas complétée par la page et le bouton du token ne remplit pas le champ. Construisez vous-même l'adresse comme indiqué en 3.12 et saisissez un long secret si vous voulez le changer.

**Le cron réécrit sans cesse les produits d'une catégorie cochée.**
Quand **Product Categories** est coché, les produits dont la catégorie principale est cochée sont sélectionnés à chaque appel, même s'ils ont déjà été rédigés. Pour les exécutions planifiées, laissez l'arbre des catégories vide et limitez l'exécution avec **Product ID list**, ou utilisez **Enable Debug** pour vérifier quels produits sont choisis avant de planifier.

**Le cron traite de nouveau les mêmes produits après que j'ai vidé History.**
Les modes de cron **pendingGemini** et **pendingField** utilisent History pour savoir ce qui est déjà rédigé. Après **Clear list**, tout compte comme non rédigé. Utilisez **emptyField** si vous voulez que les champs remplis soient laissés tranquilles.

**Top P, Frequency Penalty et Presence Penalty ne changent rien.**
Dans cette version, seuls **Temperature** et **Max Tokens** sont envoyés à Gemini. Les trois autres sont enregistrés mais non utilisés.

**L'entrée de menu "AI Content Generator" est absente.**
Ouvrez encore une fois n'importe quelle page du back office ; le module remet l'entrée en place. Si elle manque toujours, désinstallez puis réinstallez le module (cela efface History et les réglages).

**Pas de panneau "Modules → My AI Gemini" sur la page produit.**
Vérifiez que **Product edit page Form** (ou **Product Edit History**) est activé sous **Settings**, **General**, que le produit a été enregistré une fois et que vous ouvrez l'onglet **Modules** du produit. Les boutons **Generate with AI** à côté des champs sont ajoutés séparément par le module et peuvent rester visibles même lorsque le panneau est désactivé.

**Le texte que j'ai généré a disparu après l'enregistrement du produit.**
Le formulaire produit était ouvert avec les anciennes valeurs. Rechargez la page produit après avoir utilisé **Fill** et ne modifiez qu'ensuite. Utilisez **Restore** dans l'onglet **History** pour récupérer un texte précédent.

**Le bloc Dashboard du dashboard principal de PrestaShop est vide.**
Ce bloc ne reçoit pas les chiffres de History. Ouvrez **AI Content Generator**, **Dashboard**.

**Recherche de photos : "The search did not return photos. Reload the product page and try again." ou "No photos were found on the suggested pages."**
Gemini a proposé des pages qui n'ont pas pu être lues ou ne contenaient pas d'images adaptées. Appuyez de nouveau sur **Find pages** ou améliorez **AI Image Search Prompt** sous **Images**. Les pages sur des adresses privées ou locales sont refusées.

**New product affiche "Failed to parse AI response. Please try again." ou "Failed to create product".**
Gemini n'a pas renvoyé de brouillon exploitable, ou la boutique a refusé les données (par exemple une langue sans nom dans la langue par défaut). Appuyez de nouveau sur **Generate data**, choisissez la langue par défaut de la boutique et vérifiez le numéro de catégorie.

## 6. Pour le développeur

### 6.1 Vue d'ensemble

| Élément | Valeur | Où c'est défini |
|---|---|---|
| Nom technique | `myaigemini` | Fichier principal du module |
| Classe principale | `myaigemini` (extends `Module`) | Fichier principal du module |
| Version | **1.1.0** | Fichier principal du module |
| Nom affiché | My AI Gemini - AI content generation | Fichier principal du module |
| Auteur | MyPresta.eu | Fichier principal du module |
| Tab | `front_office_features` | Fichier principal du module |
| PrestaShop | 1.6 – 9.99.99 (`ps_versions_compliancy`) | Fichier principal du module |
| PHP | 7.0 ou plus récent (`MIN_PHP_VERSION`, vérifié dans `install()`) | Fichier principal du module |
| API | Google Gemini sur `https://generativelanguage.googleapis.com/v1beta`, clé comme paramètre de requête `key` | Fichier principal du module |
| Source de la clé | https://aistudio.google.com/apikey | Fichier principal du module |
| Préfixe de configuration | `MYPRESTA_MYAIGEMINI_` | Fichier principal du module |
| Préfixe CSS | `.mag-` (plus `.myaigemini-ui`, `.myaigemini-stats`) | Fichier principal du module |

Flux de données : un écran (panneau produit, exécution en masse, boîte de la barre supérieure, Playground) envoie en POST au contrôleur front du module `ajax` avec le token secret ; le contrôleur construit le prompt (modèle, variables, `Studio::decorate`), appelle `OpenAIService` (un client Gemini conservé sous son ancien nom de classe), écrit le résultat dans le produit ou la catégorie et insère une ligne dans `myaigemini_log`. Le cron fonctionne de la même façon via le contrôleur front `cron`. Le texte généré est enregistré par `Product::save()` ou `Category::save()`.

Paramètres d'URL sur la page de configuration : `mag_tab` (`dashboard`, `settings`, `updates`), `mag_sub` (`general`, `openai`, `studio`, `templates`, `playground` ; `openai` est l'onglet **Gemini** ; sur **Generate** `products` et `categories`), plage du dashboard `mcg_preset` (`today`, `7`, `30`, `90`, `month`, `all`), `mag_from`, `mag_to`. Sur History : `stats_preset`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_entity`, `stats_q`.

### 6.2 Fichiers

| Fichier | Rôle | Zone |
|---|---|---|
| `myaigemini.php` | Classe principale : installation et désinstallation, formulaires de configuration (General, Gemini, Studio, modèles), Dashboard, hooks, placement du menu, catalogue de modèles. | Code du module |
| `autoload.php` | Charge les classes du module sans Composer. | Code du module |
| `src/OpenAIService.php` | Client Gemini (`generateContent`, `models`) ; délais d'expiration ; mémorise les paramètres qu'un modèle refuse. | Code du module |
| `src/Studio.php` | Décoration du prompt, budget mensuel, vérification des mots interdits, SEO pack et prompts de textes alt. | Code du module |
| `controllers/admin/AdminMyAIGeminiMain.php` | Entrée de menu ; redirige vers le Dashboard. | Code du module |
| `controllers/admin/AdminMyAIGeminiSettings.php` | Masqué ; redirige vers Settings. | Code du module |
| `controllers/admin/AdminMyAIGemini.php` | **Generate** (filtres et panneaux en masse). | Code du module |
| `controllers/admin/AdminMyAIGeminiProductCreator.php` | **New product**. | Code du module |
| `controllers/admin/AdminMyAIGeminiCron.php` | Formulaires **Cron**. | Code du module |
| `controllers/admin/AdminMyAIGeminiUsage.php` | **History**. | Code du module |
| `controllers/admin/AdminMyAIGeminiImageFinder.php` | Formulaire **Images** et actions de recherche de photos. | Code du module |
| `controllers/front/ajax.php` | Actions JSON utilisées par les écrans. | Code du module |
| `controllers/front/cron.php` | Point d'accès du cron. | Code du module |
| `lib/sectionHelp.php` | Texte du panneau Help. | Code du module |
| `lib/updateChecker.php` | Vérification des mises à jour (`myaigeminiUpdate`). | Code du module |
| `lib/prestashop9compatibility.php`, `lib/searchTool/` | Aide de compatibilité et outil de recherche du module. | Code du module |
| `views/templates/hook/*.tpl`, `views/templates/admin/product_creator.tpl` | Écrans. | Code du module |
| `views/js/back.js`, `product-fields.js`, `image-finder.js`, `admin-products-bulk.js`, `dashboard.js`, `admin-help.js`, `chart.min.js` | Comportement des écrans. | Code du module |
| `views/css/admin-nav.css`, `back.css`, `stats.css` | Styles. | Code du module |
| `translations/*.php` | Fichiers de langue (de nombreuses langues). | Code du module |

Ressources référencées mais non livrées : `views/js/admin.js`, `views/css/admin.css` (contrôleurs Main et Settings), `views/js/product_creator.js` et `views/css/product_creator.css` (contrôleur New product). Elles sont ignorées silencieusement ; les boutons de New product sont gérés par `back.js`.

### 6.3 Contrôleurs

| Contrôleur | Classe et parent du menu | Remarques |
|---|---|---|
| `AdminMyAIGeminiMain` | `AdminMyAIGeminiMainController` (parent : section Modules) | Entrée visible **AI Content Generator**. `initContent()` redirige vers la page de configuration avec `mag_tab=dashboard`. |
| `AdminMyAIGemini` | `AdminMyAIGeminiController` (parent : AdminMyAIGeminiMain) | Onglet masqué (`active = 0`). **Generate**. `mag_sub` `products` / `categories` ; noms de soumission `filterProducts`, `filterCategories`. |
| `AdminMyAIGeminiProductCreator` | `AdminMyAIGeminiProductCreatorController` (parent : AdminMyAIGeminiMain) | Masqué. AJAX `generateProductData`, `extractImages`, `createProduct`, `generateImages` (réponse de substitution "coming soon"). |
| `AdminMyAIGeminiSettings` | `AdminMyAIGeminiSettingsController` (parent : AdminMyAIGeminiMain) | Masqué. Redirection seulement. |
| `AdminMyAIGeminiCron` | `AdminMyAIGeminiCronController` (parent : AdminMyAIGeminiMain) | Masqué. Soumission `submitCronUpdate`, `submitCatCronUpdate`. |
| `AdminMyAIGeminiUsage` | `AdminMyAIGeminiUsageController` (parent : AdminMyAIGeminiMain) | Masqué. `clear_log` vide la table du journal. |
| `AdminMyAIGeminiImageFinder` | `AdminMyAIGeminiImageFinderController` (parent : AdminMyAIGeminiMain) | Masqué. Actions `searchImages`, `extractImages` (hôtes privés refusés), `saveImages`. Soumission du formulaire `submitImageFinder`. |
| `ajax` (front) | `myaigeminiajaxModuleFrontController` (parent : –) | Exige `secret_token` égal à `MYPRESTA_MYAIGEMINI_TOKEN`, sinon "Error! Invalid token!". Actions : `initiatePrompt`, `updateSettings`, `updateProduct`, `initiateProductRestore`, `updateCategory`, `generateSeoPack`, `generateAltTexts` (aucun bouton n'appelle cette dernière). |
| `cron` (front) | `MyAIGeminiCronModuleFrontController` (parent : –) | Exige `MYPRESTA_MYAIGEMINI_ENABLE_CRON` et un `secret` égal à `_SECRET` ou `_CAT_SECRET` (chaque secret ouvre les deux actions). `action` = `generateProductContent` ou `generateCategoryContent`. |

Les formulaires de filtre de Generate lient "Module settings" à `configure=mychatgpt`. La sortie du hook du panneau d'édition des produits est construite dans `renderProductModulesContent()`.

SQL de sélection du cron : le filtre de catégories et la liste d'ids de produits sont ajoutés à la clause WHERE ; la condition de catégorie (`id_product IN (…) OR id_category_default IN (…)`) n'est pas entourée de parenthèses, donc le OR élargit toute la condition. `pendingGemini` et `pendingField` utilisent `NOT EXISTS` sur des lignes de `myaigemini_log` dont le statut est vide ou différent de `error` ; `pendingField` fait aussi correspondre `type = product_<field>` / `category_<field>`. `emptyField` joint `product_lang` / `category_lang` pour la langue choisie. Longueurs de texte de produit à l'enregistrement : nom 128, description courte 799 (cron) ou 800 (ajax), méta-titre 69, méta-description 159.

### 6.4 Hooks

Enregistrés dans `install()` : `displayAdminProductsMainStepLeftColumnMiddle` (renvoie une chaîne vide), `displayAdminProductsMainStepLeftColumnBottom` (vide), `actionProductFormBuilderModifier` (aucune action), `displayAdminProductsExtra` (affiche le panneau dans l'onglet **Modules** du produit), `displayBackOfficeHeader` (charge les ressources, exécute `ensureLongSecrets()` et `placeModuleMenu()`, enregistre une fois l'onglet de recherche d'images, ajoute des variables JS), `displayBackOfficeTop` (la boîte de la barre supérieure lorsque `TOPCTA` est activé, et des variables JS pour les ids de catégorie, CMS et marque), `displayFooter` (vide), `displayHeader` (vide), `dashboardZoneTwo` (affiche `dashboard.tpl` sans ses données). `actionProductGridDataModifier` existe comme méthode mais n'est pas enregistré. Le module n'a ni méthode `enable()` ni méthode `disable()`. Le module n'expose aucun hook personnalisé.

`hookDisplayBackOfficeHeader` charge `product-fields.js` sur les pages d'édition de produit et de catégorie indépendamment de l'interrupteur `MYPRESTA_MYAIGEMINI_PRODUCT` (l'interrupteur ne commande que le panneau de l'onglet Modules).

### 6.5 Overrides

Le module n'a aucun override. Il ne remplace aucun fichier du cœur.

### 6.6 Base de données

| Table | Contenu | Remarques |
|---|---|---|
| `myaigemini_prompt` | `id_prompt` (PK), `status`, `title` (128), `prompt` (text), `date_generated`. 16 lignes insérées à l'installation. | Créée à l'installation, supprimée à la désinstallation |
| `myaigemini_log` | `id_log` (PK), `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, `type`, `method`, `status`, `ai_service`, `model`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `error_message`, `prompt`, `reply`, paires `old_` / `new_` pour `name`, `description`, `description_short`, `meta_title`, `meta_description`, `tags`, `date_updated`. Index sur `id_product` et `status`. | Créée à l'installation, supprimée à la désinstallation |

Les deux tables utilisent le moteur de la base de données de la boutique et sont supprimées à la désinstallation. Les trois colonnes de tokens sont aussi ajoutées à l'exécution par `ensureUsageColumns()` lorsque le Dashboard, History ou une écriture de journal de cron/ajax en a besoin et qu'elles manquent. `ai_service` stocke toujours la valeur `openai` (reste d'ancienne version). Le `postProcess()` du générateur en masse écrit les valeurs de filtre soumises dans des clés de configuration telles que `MYPRESTA_MYAIGEMINI_FIELD`, `_LANGUAGE`, `_CONTENT`, `_DELAY`, `_EXISTING`, `_HISTORY`, `_STATUS`, `_STOCK`, `_PROD_*`, `_CATEGORIES`, `_BRANDS` à chaque chargement de **Generate**. La désinstallation ne supprime pas ces clés.

### 6.7 Clés de configuration et traductions

Préfixe `MYPRESTA_MYAIGEMINI_`. Valeurs écrites par `install()` :

| Clé | Par défaut | Signification |
|---|---|---|
| `LIVE_MODE`, `DEBUG_MODE` | `0`, `0` | Interrupteurs live et debug (`PrestaShopLogger` avec le type d'objet `MyAIGemini`). |
| `TIMEOUT` | `120` | Secondes ; borné à 10–600 ; le délai du navigateur est cette valeur plus 15. |
| `PRODUCT_LOG`, `TOPCTA`, `PRODUCT` | `1`, `1`, `1` | Liste de restauration, boîte de la barre supérieure, panneau produit. |
| `IMAGEFINDER_ENABLE`, `IMAGEFINDER_PROMPT` | `1`, texte intégré | Interrupteur et instruction de la recherche de photos. `IMAGEFINDER_TAB_OK` marque la réparation unique de l'onglet. |
| `TOKEN`, `SECRET`, `CAT_SECRET` | 32 caractères aléatoires | Token ajax, secret du cron des produits, secret du cron des catégories. Les valeurs de moins de 24 caractères sont régénérées à la prochaine page du back office. |
| `API_KEY` | un seul espace | Enregistrée rognée ; le formulaire conserve la clé enregistrée si la case est vide. |
| `MODEL`, `EXTRA_MODELS` | `gemini-2.0-flash`, vide | Modèle actif et noms ajoutés (un par ligne). Supprimer le modèle ajouté actif définit `gpt-4o`. |
| `TEMPERATURE`, `MAX_TOKENS` | `0.7`, `3200` | Envoyés à Gemini sous les noms `temperature` et `maxOutputTokens`. |
| `TOP_P`, `FREQ_PEN`, `PRES_PEN` | `1`, `0`, `0` | Enregistrés ; non inclus dans la requête Gemini. |
| `MODEL_CAPS` | vide | Paramètres appris par modèle. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | vide | Textes de Studio. |
| `BUDGET`, `QUALITY` | `0`, `1` | Plafond mensuel ; quality gate. |
| `ENABLE_CRON` | `0` | Interrupteur global du cron. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | `6`, `6` | Choix d'intervalle (6 = Every Hour). Seulement enregistré ; utilisé pour l'affichage. |
| `updatedField`, `catupdatedField` | `description`, `description` | Champ du cron (les noms de clé sont écrits sous la forme `MYPRESTA_MYAIGEMINI_updatedField`, etc.). |
| `productTarget`, `categoryTarget` | `pendingGemini` | Mode de sélection du cron. |
| `productsToUpdate`, `categoriesToUpdate` | `5`, `5` | Taille du lot. |
| `promptTemplateId`, `catpromptTemplateId` | vide | Modèle du cron. |
| `languageId`, `catlanguageId` | `PS_LANG_DEFAULT` | Langue du cron. |
| `debug`, `catdebug`, `interval_select` | `0`, `0`, vide | Debug du cron et ancien sélecteur. |
| `productIdsList`, `categories` | vide | Filtres du cron. |

La désinstallation supprime les clés ci-dessus ainsi que `ACTIVE_SERVICE`, `GEMINI_API_KEY` et `GEMINI_MODEL` (anciens noms), les onglets et les deux tables. Le back office supprime aussi `GEMINI_API_KEY`, `GEMINI_MODEL` et `ACTIVE_SERVICE` à chaque chargement de la page de configuration. Les clés partagées `mypresta_updates`, `update_myaigemini` et `updatev_myaigemini` appartiennent au vérificateur de mises à jour et ne sont pas supprimées.

Traductions : ajoutez une langue en créant `translations/{iso}.php` (le module en livre beaucoup). Les textes passent par `$this->l()` dans la classe principale et par `l s='…' mod='myaigemini'` dans les templates. Les contrôleurs d'administration traduisent via `trans()` sur PrestaShop 8 et 9 et via le `l()` du module sur 1.6 et 1.7. Textes non traduits : le titre de colonne **ID**, le libellé **Cron Job Secret Token** et **Generate Token**, les messages JavaScript dans `back.js`, `image-finder.js` et la page du sélecteur de photos ("Write a prompt first.", "Looking for photos…" et similaires), et le brouillon renvoyé par New product. Les descriptions de champs sont des entrées `desc` construites avec `fieldHelp()` dans les définitions de formulaires, sous la forme "What it does / How to configure / Effect" ; le texte du panneau Help se trouve dans `lib/sectionHelp.php`.

Les variables sont remplacées dans `controllers/front/ajax.php` (exécutions interactives) et `controllers/front/cron.php` (cron) ; les listes sont identiques, sauf que le cron n'a pas de variables CMS ni de marque.

### 6.8 Extension

Il n'y a pas de template front à surcharger dans un thème. Pour ajouter des variables de prompt, étendez les blocs de remplacement dans `ajax.php` et `cron.php`. Pour modifier le comportement du service d'IA, éditez `src/OpenAIService.php` (`createChatCompletion()` construit la charge utile Gemini). Pour ajouter un modèle, utilisez **Add a Gemini model** ou étendez `getPopularGeminiModels()`. Un CSS personnalisé peut cibler les classes `.mag-` sur les écrans du module. Changer le format de l'adresse du cron nécessite de modifier `AdminMyAIGeminiCron.php` et les templates `cron.tpl` et `cron-info.tpl`.

## 7. Aide

Page du module : https://mypresta.eu/ai-artificial-intelligence/product-and-category-descriptions-with-gemini.html

Pour demander de l'aide :

1. Connectez-vous à votre compte client sur mypresta.eu.
2. Allez sur la page de contact.
3. Choisissez le sujet **Support for paid modules**. Pour les modules payants, le formulaire indique que vous devez être connecté ; après connexion, choisissez ce module dans votre historique d'achats.
4. Décrivez ce que vous avez fait, ce que vous attendiez et ce que vous avez vu. Joignez la ligne rouge de **History** (ouvrez-la avec **View**) ou le texte du message affiché à l'écran, ainsi que le nom du modèle que vous utilisez.
