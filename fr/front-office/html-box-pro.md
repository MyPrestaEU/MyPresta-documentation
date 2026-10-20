---
title: "HTML Box Pro - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop HTML Box Pro par MyPresta.eu."
sidebar:
  label: "HTML Box Pro - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module HTML Box Pro sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/html-box-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/html-box-pro/)
>
> ---


# HTML Box Pro

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises par PrestaShop lui-même et sont suffisantes pour ce module.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > HTML Box Pro)

C'est l'écran principal où vous gérez toutes vos boîtes HTML. Le module présente une liste des boîtes existantes et des options pour en ajouter de nouvelles ou modifier les paramètres globaux.

#### Section des paramètres globaux

En haut de la page de configuration, vous trouverez quelques paramètres globaux qui affectent le fonctionnement du module.

- **Utiliser le module interne**

  - **Ce que fait ce paramètre :** Il s'agit d'un paramètre hérité qui fait généralement référence au mécanisme de mise à jour interne du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé ("Oui") :* Le module pourrait utiliser ses propres méthodes internes pour vérifier les mises à jour.
    - *Lorsqu'il est désactivé ("Non") :* Le module s'appuiera sur les mécanismes de mise à jour standard de PrestaShop ou sur les mises à jour manuelles.
  - **Valeur recommandée :** "Oui" (sauf si vous rencontrez des problèmes, alors essayez "Non").
  - **Scénario/exemple marchand :** En général, laissez-le activé. Si vous rencontrez des problèmes avec les mises à jour ou les notifications du module, votre webmaster pourrait suggérer de le désactiver/réactiver.
- **Empêcher la suppression des URL des images**

  - **Ce que fait ce paramètre :** Lorsque vous utilisez l'éditeur TinyMCE intégré (l'éditeur de texte enrichi) pour ajouter des images, il peut parfois supprimer automatiquement le chemin d'URL complet, surtout si vous copiez-collez du contenu. Ce paramètre empêche ce comportement.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé ("Oui") :* Les URL d'image que vous insérez dans le contenu de la boîte HTML seront conservées exactement telles que vous les avez saisies, empêchant les liens d'image brisés.
    - *Lorsqu'il est désactivé ("Non") :* L'éditeur pourrait modifier ou supprimer des parties des URL d'image, ce qui pourrait entraîner un affichage incorrect des images.
  - **Valeur recommandée :** "Oui"
  - **Scénario/exemple marchand :** Si vous ajoutez des images provenant de sources externes (par exemple, un CDN ou un autre site web) ou même des images internes avec des chemins absolus, l'activation de ce paramètre garantit que vos images s'affichent toujours.
- **Ne pas charger les bibliothèques tinyMCE**

  - **Ce que fait ce paramètre :** TinyMCE est l'éditeur de texte enrichi qui vous permet de formater facilement du texte, d'ajouter des images et de créer des tableaux sans écrire directement de code HTML. Ce paramètre contrôle si le module charge sa propre version de l'éditeur TinyMCE.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé ("Oui") :* Le module NE chargera PAS son éditeur TinyMCE. Cela peut être utile si votre thème ou un autre module charge déjà TinyMCE, évitant ainsi les conflits ou le chargement en double. Cependant, vous perdrez l'éditeur visuel pour vos boîtes HTML et devrez écrire du HTML brut.
    - *Lorsqu'il est désactivé ("Non") :* Le module chargera son éditeur TinyMCE, vous offrant une interface conviviale pour créer et modifier le contenu de votre boîte HTML.
  - **Valeur recommandée :** "Non" (sauf si vous êtes un développeur et préférez écrire du HTML brut, ou si vous rencontrez des conflits avec d'autres instances TinyMCE).
  - **Scénario/exemple marchand :** Si vous souhaitez utiliser l'éditeur visuel pour ajouter facilement du texte, du gras, de l'italique, des images et des liens sans connaître le HTML, gardez ce paramètre sur "Non". Si vous constatez un comportement étrange avec l'éditeur ou des erreurs de console, un développeur pourrait suggérer de le passer à "Oui" pour le dépannage.

#### Section de gestion des boîtes HTML

Sous les paramètres globaux, vous trouverez un tableau listant toutes vos boîtes HTML créées. À partir de là, vous pouvez ajouter de nouvelles boîtes, modifier celles qui existent ou les supprimer.

- **Ajouter une nouvelle boîte HTML** (Bouton)

  - **Ce que cela fait :** Cliquer sur ce bouton vous amène à un nouveau formulaire où vous pouvez définir une toute nouvelle boîte HTML.
  - **Effet :** Ouvre le formulaire "Ajouter une nouvelle boîte HTML".
- **Modifier** (Icône à côté de chaque boîte)

  - **Ce que cela fait :** Vous permet de modifier les paramètres et le contenu d'une boîte HTML existante.
  - **Effet :** Ouvre le formulaire "Modifier la boîte HTML", pré-rempli avec les paramètres actuels de la boîte.
- **Supprimer** (Icône à côté de chaque boîte)

  - **Ce que cela fait :** Supprime définitivement une boîte HTML de votre boutique.
  - **Effet :** La boîte HTML n'apparaîtra plus sur votre front office. Cette action est irréversible.
  - **Valeur recommandée :** Ne supprimez que les boîtes dont vous n'avez plus besoin.

#### Formulaire Ajouter/Modifier une boîte HTML

Lorsque vous cliquez sur "Ajouter une nouvelle boîte HTML" ou "Modifier" une boîte existante, vous verrez un formulaire avec les champs suivants :

- **Nom**

  - **Ce que fait ce paramètre :** Il s'agit d'un nom interne pour votre boîte HTML, visible uniquement dans le Back Office. Il vous aide à identifier les différentes boîtes.
  - **Effet de la modification de ce paramètre :** Modifie l'étiquette de cette boîte dans votre liste de configuration de module. Aucun effet sur le front office.
  - **Valeur recommandée :** Un nom descriptif (par exemple, "Bannière page d'accueil - Soldes d'été", "Badges de confiance page produit", "Infos contact pied de page").
  - **Scénario/exemple marchand :** Nommer clairement vos boîtes vous aide à les trouver et à les gérer rapidement, surtout à mesure que votre boutique grandit et que vous ajoutez plus de contenu personnalisé.
- **Boutique** (Visible uniquement dans les environnements multi-boutiques)

  - **Ce que fait ce paramètre :** Si vous gérez plusieurs boutiques à partir d'une seule installation PrestaShop, cela vous permet de spécifier sur quelle(s) boutique(s) cette boîte HTML doit apparaître.
  - **Effet de la modification de ce paramètre :** La boîte HTML ne sera affichée que sur les boutiques sélectionnées.
  - **Valeur recommandée :** Sélectionnez les boutiques spécifiques où le contenu est pertinent.
  - **Scénario/exemple marchand :** Vous pourriez avoir une bannière promotionnelle différente pour votre boutique française que pour votre boutique allemande.
- **Position**

  - **Ce que fait ce paramètre :** C'est le paramètre le plus crucial, déterminant *où* sur votre boutique la boîte HTML apparaîtra. C'est une liste déroulante de tous les hooks PrestaShop disponibles.
  - **Effet de la modification de ce paramètre :** Le contenu de votre boîte HTML sera rendu à l'emplacement du hook sélectionné.
  - **Valeur recommandée :** Choisissez le hook qui correspond le mieux à l'objectif du contenu (par exemple, `displayHeader` pour une bannière supérieure, `displayLeftColumn` pour un bloc de barre latérale).
  - **Scénario/exemple marchand :** Si vous souhaitez ajouter un message "Livraison gratuite" au-dessus de vos descriptions de produits, vous sélectionneriez `displayProductAdditionalInfo`.
- **Actif**

  - **Ce que fait ce paramètre :** Contrôle si la boîte HTML est actuellement visible sur votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé ("Oui") :* La boîte HTML sera affichée sur votre front office.
    - *Lorsqu'il est désactivé ("Non") :* La boîte HTML sera masquée, mais son contenu et ses paramètres sont enregistrés, vous permettant de la réactiver plus tard.
  - **Valeur recommandée :** "Oui" pour le contenu actif, "Non" pour le contenu que vous souhaitez masquer temporairement ou préparer pour une utilisation future.
  - **Scénario/exemple marchand :** Vous pouvez préparer une boîte de promotion de Noël à l'avance, la garder sur "Non", puis la passer sur "Oui" le moment venu, sans avoir à la recréer.
- **Uniquement sur les pages sécurisées (SSL)**

  - **Ce que fait ce paramètre :** Restreint l'affichage de la boîte HTML aux pages chargées via HTTPS (connexion sécurisée).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé ("Oui") :* La boîte n'apparaîtra que sur les pages avec `https://` dans l'URL.
    - *Lorsqu'il est désactivé ("Non") :* La boîte apparaîtra sur les pages sécurisées (HTTPS) et non sécurisées (HTTP) (si votre boutique utilise toujours HTTP, ce qui n'est pas recommandé).
  - **Valeur recommandée :** "Oui" si le contenu contient des informations sensibles ou si vous souhaitez vous assurer qu'il ne se charge que sur les pages sécurisées. Généralement, toutes les boutiques modernes devraient être entièrement HTTPS, donc cela pourrait ne pas être strictement nécessaire, mais cela ajoute une couche de contrôle supplémentaire.
  - **Scénario/exemple marchand :** Si votre boîte HTML contient un badge de paiement ou un sceau de sécurité, vous pourriez vouloir vous assurer qu'il n'apparaît que sur les pages sécurisées pour renforcer la confiance.
- **Uniquement sur la page d'accueil**

  - **Ce que fait ce paramètre :** Restreint l'affichage de la boîte HTML uniquement à la page d'accueil de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé ("Oui") :* La boîte n'apparaîtra que lorsque les clients visiteront votre page d'accueil principale.
    - *Lorsqu'il est désactivé ("Non") :* La boîte apparaîtra sur toutes les pages où sa "Position" (hook) sélectionnée est disponible.
  - **Valeur recommandée :** "Non" sauf si le contenu est spécifiquement conçu pour la page d'accueil.
  - **Scénario/exemple marchand :** Une grande bannière promotionnelle pour une vente à l'échelle du site serait généralement réglée sur "Oui" pour cette option si vous ne la voulez que sur la page d'accueil, ou "Non" si vous voulez qu'elle apparaisse dans l'en-tête sur chaque page.
- **Contenu** (Ceci est l'éditeur de contenu principal)

  - **Ce que fait ce paramètre :** C'est ici que vous saisissez le code HTML, JavaScript ou CSS réel qui sera affiché. Il utilise l'éditeur de texte enrichi TinyMCE (s'il n'est pas désactivé globalement) pour une création de contenu facile.
  - **Effet de la modification de ce paramètre :** Le contenu que vous saisissez ici sera rendu sur votre front office dans le hook sélectionné.
  - **Valeur recommandée :** Saisissez le contenu souhaité. Vous pouvez utiliser :
    - Texte brut
    - HTML (par exemple, `<p>Bonjour le monde !</p>`, balises `<img>`, liens `<a>`)
    - CSS (à encapsuler dans des balises `<style>`, par exemple, `<style>.ma-classe { color: red; }</style>`)
    - JavaScript (à encapsuler dans des balises `<script>`, par exemple, `<script>alert('Bienvenue !');</script>`)
  - **Scénario/exemple marchand :**
    - *HTML :* Ajout d'une image de bannière personnalisée : `<img src="https://votreboutique.com/img/cms/banniere.jpg" alt="Soldes d'été" style="width:100%;">`
    - *JavaScript :* Intégration d'un code de suivi Google Analytics : `<script> (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){ (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o), m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m) })(window,document,'script','//www.google-analytics.com/analytics.js','ga'); ga('create', 'UA-XXXXX-Y', 'auto'); ga('send', 'pageview'); </script>`
    - *CSS :* Modification de la couleur d'un élément spécifique : `<style> #header .logo { border: 2px solid blue; } </style>`

#### 2.1.1 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration principale | Utiliser le module interne | Oui | Contrôle le mécanisme de mise à jour interne. |
| Page de configuration principale | Empêcher la suppression des URL des images | Oui | Garantit que les URL des images sont conservées dans l'éditeur. |
| Page de configuration principale | Ne pas charger les bibliothèques tinyMCE | Non | Active l'éditeur visuel pour une création de contenu facile. |
| Formulaire Ajouter/Modifier | Nom | Nom descriptif | Libellé interne de la boîte HTML. |
| Formulaire Ajouter/Modifier | Boutique | Toutes les boutiques | Sélectionne les boutiques qui affichent le contenu (multi-boutique). |
| Formulaire Ajouter/Modifier | Position | (Choisir le Hook) | Détermine où le contenu apparaît sur le front office. |
| Formulaire Ajouter/Modifier | Actif | Oui | Active/désactive la visibilité de la boîte HTML sur le front office. |
| Formulaire Ajouter/Modifier | Uniquement sur les pages sécurisées (SSL) | Non (ou Oui si critique) | Restreint l'affichage aux pages HTTPS. |
| Formulaire Ajouter/Modifier | Uniquement sur la page d'accueil | Non | Restreint l'affichage à la page d'accueil uniquement. |
| Formulaire Ajouter/Modifier | Contenu | (Votre HTML/JS/CSS) | Le contenu réel à afficher. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Ma boîte HTML n'apparaît pas sur le front office. Que dois-je vérifier ?**
R1 :

- **Est-elle active ?** Allez dans la configuration du module et assurez-vous que l'interrupteur "Actif" de votre boîte est réglé sur "Oui".
- **Position (Hook) correcte ?** Vérifiez à nouveau que vous avez sélectionné la bonne "Position" (hook) où vous vous attendez à ce que le contenu apparaisse. Certains hooks sont spécifiques à certaines pages (par exemple, `displayProductAdditionalInfo` uniquement sur les pages produits).
- **Page d'accueil uniquement ?** Si vous avez réglé "Uniquement sur la page d'accueil" sur "Oui", elle n'apparaîtra que sur votre page d'accueil principale.
- **SSL uniquement ?** Si "Uniquement sur les pages sécurisées (SSL)" est sur "Oui", assurez-vous que vous consultez une page HTTPS.
- **Cache :** Videz votre cache PrestaShop (Paramètres avancés > Performances > Vider le cache) et le cache de votre navigateur.
- **Erreurs de contenu :** Si votre contenu HTML/JS/CSS contient des erreurs, cela pourrait empêcher l'affichage de la boîte. Essayez un simple texte "Bonjour le monde" pour tester.

**Q2 : L'éditeur TinyMCE (éditeur visuel) ne fonctionne pas ou a un aspect étrange.**
R2 :

- **Paramètre "Ne pas charger les bibliothèques tinyMCE" :** Assurez-vous qu'il est réglé sur "Non" dans les paramètres globaux du module si vous souhaitez utiliser l'éditeur visuel.
- **Conflits de thème :** Parfois, des thèmes personnalisés ou d'autres modules peuvent interférer avec TinyMCE. Essayez de désactiver temporairement d'autres modules pour voir si le problème se résout.
- **Problèmes de navigateur :** Essayez un autre navigateur ou videz le cache et les cookies de votre navigateur.

**Q3 : Mes images ou mes liens sont brisés après avoir enregistré le contenu de la boîte HTML.**
R3 :

- **Paramètre "Empêcher la suppression des URL des images" :** Assurez-vous qu'il est réglé sur "Oui" dans les paramètres globaux du module.
- **Chemins absolus vs. relatifs :** Utilisez toujours des URL absolues (commençant par `http://` ou `https://`) pour les images et les liens, surtout s'ils sont externes ou si vous voulez qu'ils fonctionnent de manière cohérente sur votre site.
- **Vérifiez le HTML :** Inspectez le code HTML généré dans l'éditeur (généralement un bouton "Code source") pour vous assurer que vos attributs `src` et `href` sont corrects.

**Q4 : Comment traduire le contenu de mes boîtes HTML pour différentes langues ?**
R4 :

- HTML Box Pro prend en charge le contenu multilingue. Lorsque vous modifiez une boîte HTML, vous verrez des onglets de langue (par exemple, Anglais, Français, Espagnol) à côté du champ "Contenu".
- Cliquez sur chaque onglet de langue et saisissez le contenu traduit pour cette langue spécifique. Le module affichera automatiquement la version linguistique correcte à vos clients en fonction de la langue de leur boutique sélectionnée.

**Q5 : Le contenu s'affiche bien sur ordinateur mais est déformé sur mobile.**
R5 :

- **Conception responsive :** Assurez-vous que le contenu HTML que vous ajoutez est conçu pour être responsive. Utilisez des propriétés CSS comme `max-width: 100%; height: auto;` pour les images, et envisagez d'utiliser des requêtes média CSS dans vos balises `<style>` pour des mises en page plus complexes.
- **Réactivité du thème :** Bien que le module lui-même soit responsive, si votre HTML personnalisé ne l'est pas, cela pourrait casser la mise en page. Testez minutieusement sur différents appareils.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module HTML Box Pro suit une architecture de module PrestaShop standard, exploitant principalement la classe `Module` pour sa fonctionnalité principale et `getContent()` pour sa configuration Back Office. Il enregistre dynamiquement les hooks et rend le contenu en fonction de la configuration stockée. Le module utilise une bibliothèque `SmartyTemplatesManager` personnalisée pour gérer ses formulaires et modèles Back Office, offrant une interface utilisateur cohérente pour l'ajout et la modification de boîtes HTML. Le contenu est stocké dans la table `ps_configuration`, chaque boîte HTML étant représentée par une clé de configuration unique.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs front-office ou back-office dédiés dans les répertoires `controllers/front` ou `controllers/admin`. Toute la logique du Back Office est gérée dans la méthode `getContent()` du fichier `htmlboxpro.php`, qui rend les formulaires et traite les soumissions. Le rendu du contenu front-office est géré directement via l'exécution des hooks dans le fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne définit pas de classes `ObjectModel` personnalisées ou d'autres classes principales dans un répertoire `classes/`. Toute la gestion des données et la logique métier sont encapsulées dans le fichier principal du module `htmlboxpro.php`. Les configurations des boîtes HTML sont stockées directement dans la table `ps_configuration`, avec des clés comme `hbp_name_X`, `hbp_content_X_Y`, `hbp_hook_X`, etc., où `X` est l'ID de la boîte et `Y` est l'ID de la langue.

### 4.4 Actifs JavaScript (`views/js/`)

- `htmlboxpro/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`
  - **Portée :** Back-office.
  - **Responsabilité :** Fournit des fonctionnalités JavaScript pour la bibliothèque `SmartyTemplatesManager`, qui est utilisée pour rendre et gérer les formulaires de configuration du module (par exemple, ajouter/modifier des boîtes HTML). Cela inclut des éléments de formulaire dynamiques, des interactions AJAX pour l'enregistrement/le chargement des données de modèle et potentiellement la gestion des onglets.
- `htmlboxpro/views/js/script.js`
  - **Portée :** Back-office.
  - **Responsabilité :** Contient le JavaScript spécifique au module pour la page de configuration du Back Office. Cela peut inclure des écouteurs d'événements pour les soumissions de formulaires, des mises à jour dynamiques de la liste des boîtes HTML ou d'autres améliorations de l'interface utilisateur spécifiques à HTML Box Pro.
- `htmlboxpro/views/js/tinymce16-force-urls.inc.js`
  - **Portée :** Back-office.
  - **Responsabilité :** Ce script est chargé lorsque l'option "Empêcher la suppression des URL des images" est activée. Il contient la configuration et les plugins TinyMCE spécifiquement conçus pour empêcher l'éditeur de supprimer ou de modifier les URL absolues, en particulier pour les images. Il garantit que les attributs `src` restent intacts.
- `htmlboxpro/views/js/tinymce16.inc.js`
  - **Portée :** Back-office.
  - **Responsabilité :** Ce script contient l'initialisation et la configuration de l'éditeur TinyMCE pour le module. Il définit la barre d'outils, les plugins et le comportement général de l'éditeur lors de la modification du contenu de la boîte HTML. Il est chargé lorsque l'option "Ne pas charger les bibliothèques tinyMCE" est désactivée.

### 4.5 Feuilles de style CSS (`views/css/`)

- `htmlboxpro/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`
  - **Portée :** Style du formulaire d'administration du Back Office.
  - **Responsabilité :** Fournit le style pour les composants de l'interface utilisateur de la bibliothèque `SmartyTemplatesManager`, assurant une apparence cohérente pour les formulaires de configuration du module dans le Back Office de PrestaShop.
- `htmlboxpro/views/css/styles.css`
  - **Portée :** Style du formulaire d'administration du Back Office.
  - **Responsabilité :** Contient les règles CSS spécifiques au module pour la page de configuration de HTML Box Pro, telles que le style de la liste des boîtes HTML, des boutons ou d'autres éléments personnalisés dans l'interface d'administration du module.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module utilise intensivement les modèles Smarty pour son interface Back Office.

- **Modèles de hook (`htmlboxpro/`)** :
  - `htmlboxpro/html.tpl` : C'est le modèle principal du front-office. Il est responsable du rendu du contenu réel de la boîte HTML (`{$htmlboxpro_content}`) dans le hook sélectionné sur le front office.
- **Modèles d'administration (`views/templates/admin/`)** :
  - `htmlboxpro/views/templates/admin/_configure/helpers/form/form.tpl` : Ce modèle est probablement une surcharge ou un modèle spécifique utilisé par le formulaire de configuration du module, personnalisant éventuellement la façon dont le `HelperForm` standard de PrestaShop rend ses champs, en particulier pour l'éditeur TinyMCE.
- **Modèles d'administration (`views/templates/`)** :
  - `htmlboxpro/views/custom_hook_info.tpl` : Affiche probablement des informations ou des instructions relatives aux hooks personnalisés.
  - `htmlboxpro/views/form-add-new.tpl` : Modèle pour le formulaire "Ajouter une nouvelle boîte HTML".
  - `htmlboxpro/views/form-edit.tpl` : Modèle pour le formulaire "Modifier la boîte HTML".
  - `htmlboxpro/views/messages.tpl` : Utilisé pour afficher les messages de succès, d'erreur ou d'information dans le Back Office.
  - `htmlboxpro/views/scripts.tpl` : Inclut probablement les actifs JavaScript et CSS pour la page de configuration du Back Office.
- **Modèles de la bibliothèque SmartyTemplatesManager (`htmlboxpro/lib/smartyTemplatesManager/tpl/`, `htmlboxpro/lib/smartyTemplatesManager/views/`)** :
  - `htmlboxpro/lib/smartyTemplatesManager/tpl/example.tpl` : Un exemple de modèle, probablement à des fins de développement ou de démonstration au sein de la bibliothèque.
  - `htmlboxpro/lib/smartyTemplatesManager/views/buttonManager.tpl` : Rend les boutons ou les liens d'action dans l'interface `SmartyTemplatesManager`.
  - `htmlboxpro/lib/smartyTemplatesManager/views/createTemplateForm.tpl` : Utilisé pour créer de nouveaux modèles/éléments dans le contexte `SmartyTemplatesManager`.
  - `htmlboxpro/lib/smartyTemplatesManager/views/editTemplateForm.tpl` : Utilisé pour modifier des modèles/éléments existants dans le contexte `SmartyTemplatesManager`.
  - `htmlboxpro/lib/smartyTemplatesManager/views/mainForm.tpl` : L'enveloppe principale ou la structure des formulaires gérés par le `SmartyTemplatesManager`.
  - `htmlboxpro/lib/smartyTemplatesManager/views/selectInput.tpl` : Un modèle générique pour le rendu d'une entrée de liste déroulante de sélection.
  - `htmlboxpro/lib/searchTool/views/scripts.tpl` : Inclut probablement les actifs JavaScript et CSS pour un composant d'outil de recherche dans le Back Office.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne crée pas de tables SQL personnalisées. Toute la configuration des boîtes HTML est stockée dans la table standard `ps_configuration` de PrestaShop.
  - Les clés de configuration suivent un modèle comme :
    - `HBP_NAME_{ID}` : Nom de la boîte HTML.
    - `HBP_CONTENT_{ID}_{LANG_ID}` : Le contenu HTML/JS/CSS réel pour une boîte et une langue spécifiques.
    - `HBP_HOOK_{ID}` : Le nom du hook où la boîte est affichée.
    - `HBP_ACTIVE_{ID}` : Booléen (0/1) indiquant si la boîte est active.
    - `HBP_SSL_{ID}` : Booléen (0/1) indiquant si elle est uniquement sur les pages SSL.
    - `HBP_HOMEPAGE_{ID}` : Booléen (0/1) indiquant si elle est uniquement sur la page d'accueil.
    - `HBP_SHOP_{ID}` : Liste d'ID de boutiques séparés par des virgules (pour le multi-boutique).
    - `HBP_LAST_ID` : Stocke le dernier ID utilisé pour une boîte HTML afin de générer des ID uniques.
    - `HBP_NOTINYJS` : Paramètre global pour "Ne pas charger les bibliothèques tinyMCE".
    - `HBP_FORCEURLS` : Paramètre global pour "Empêcher la suppression des URL des images".
    - Autres clés comme `MYPRESTA_UPDATES`, `UPDATE_HTMLBOXPRO`, `UPDATEV_HTMLBOXPRO` pour la gestion des mises à jour.
- **Table des hooks enregistrés** :

| Nom du Hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayAfterCarrier` | Après la sélection du transporteur lors du paiement. | Afficher le contenu lié aux options d'expédition ou aux dernières étapes. |
| `displayFooterBefore` | Avant le contenu principal du pied de page. | Ajouter du contenu au-dessus du pied de page standard. |
| `displayLeftColumn` | Dans la barre latérale gauche des pages applicables. | Afficher des blocs de barre latérale (par exemple, catégories, filtres, informations personnalisées). |
| `displayCustomerAccountForm` | Dans le formulaire de création/modification de compte client. | Ajouter des champs personnalisés ou des informations liées aux comptes clients. |
| `displayRightColumnProduct` | Dans la barre latérale droite des pages produits. | Afficher le contenu de la barre latérale spécifique au produit (par exemple, produits connexes, badges de confiance). |
| `displayBanner` | En haut de la page, généralement pour une bannière à l'échelle du site. | Afficher des bannières promotionnelles ou des annonces. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration définit ses médias (CSS/JS). | Injecter du CSS/JS personnalisé dans le Back Office (utilisé par le module pour ses propres actifs d'administration). |
| `displayOrderConfirmation` | Sur la page de confirmation de commande après un achat réussi. | Afficher des messages de remerciement, des informations de suivi ou des ventes incitatives. |
| `displayHeader` | Dans la section `<head>` de chaque page. | Idéal pour injecter des balises meta, des scripts de suivi ou du CSS/JS global. |
| `displayCartExtraProductActions` | Dans le résumé du panier, près des actions sur les produits. | Ajouter du contenu lié aux articles du panier (par exemple, ventes incitatives, ventes croisées, informations d'expédition). |
| `displayFooter` | Dans la section principale du pied de page de la boutique. | Ajouter du contenu général au pied de page, des liens ou des informations de copyright. |
| `displayPaymentByBinaries` | Pendant le processus de sélection du paiement. | Afficher des informations liées au paiement ou des sceaux de confiance. |
| `displayCustomerLoginFormAfter` | Après le formulaire de connexion client. | Ajouter du contenu sous le formulaire de connexion (par exemple, liens "mot de passe oublié", invites d'inscription). |
| `displayReassurance` | Dans le bloc de réassurance du produit (souvent sous l'image du produit). | Afficher des éléments de confiance comme la livraison gratuite, le paiement sécurisé, les retours faciles. |
| `displayProductAdditionalInfo` | Sous la description du produit ou le bloc d'informations principal. | Ajouter des détails supplémentaires sur le produit, des guides des tailles ou du contenu personnalisé. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est prête à vous aider pour toute question ou problème concernant le module HTML Box Pro.
"""
