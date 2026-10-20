---
title: "Hot Info - bottom sidebar - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Hot Info - bottom sidebar par MyPresta.eu."
sidebar:
  label: "Hot Info - bottom sidebar - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Hot Info - bottom sidebar sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/hot-info-bottom-sidebar.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/hot-info-bottom-sidebar/)
>
> ---


# Hot Info - bottom sidebar

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont habituellement disponibles sur tout environnement d'hébergement moderne.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation du module, cliquez sur « Configurer » pour accéder à ses paramètres. C'est ici que vous définirez le contenu et l'apparence de votre barre latérale « Hot Info ».

#### **Contenu du bloc Hot Info**

- **Ce que fait ce paramètre :** C'est la zone principale où vous saisirez le contenu réel que les clients verront dans la barre latérale inférieure. C'est un éditeur de texte enrichi (WYSIWYG - What You See Is What You Get), similaire à ce que vous pourriez utiliser pour les descriptions de produits ou les articles de blog.
- **Effet de la modification de ce paramètre :**
  - *Lorsque du contenu est ajouté :* Le texte, les images, les liens ou le code HTML que vous saisissez ici seront affichés dans le bloc « Hot Info » sur votre boutique.
  - *Lorsque laissé vide :* Le bloc « Hot Info » pourrait toujours apparaître, mais il sera vide, ou le module pourrait ne pas s'afficher du tout (selon d'autres paramètres et le comportement du thème). Il est crucial d'ajouter du contenu ici pour que le module soit utile.
- **Valeur recommandée :** Saisissez ici vos « informations chaudes » souhaitées. Utilisez un langage clair et concis et des appels à l'action forts.
- **Scénario / exemple pour le marchand :** Vous pourriez ajouter « VENTE FLASH ! Obtenez 20 % de réduction sur tous les articles d'été avec le code ÉTÉ20 ! [Acheter maintenant] » avec un lien vers votre collection d'été. Ou « Livraison gratuite sur toutes les commandes de plus de 50 € ! »

#### **Couleur de fond**

- **Ce que fait ce paramètre :** Il contrôle la couleur de fond du bloc « Hot Info ». Vous pouvez sélectionner une couleur à l'aide d'un outil de sélection de couleurs.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une couleur spécifique est définie (par exemple, #FF0000 pour le rouge) :* L'arrière-plan du bloc « Hot Info » s'affichera dans la couleur choisie.
  - *Lorsqu'il est laissé par défaut ou transparent :* Il héritera généralement de la couleur de fond de votre thème ou sera transparent, ce qui pourrait le faire trop se fondre ou le rendre difficile à lire.
- **Valeur recommandée :** Choisissez une couleur qui complète l'image de marque de votre boutique ou qui se démarque pour attirer l'attention, selon votre objectif. Une couleur contrastante peut être très efficace.
- **Scénario / exemple pour le marchand :** Si votre boutique utilise beaucoup de bleu, vous pourriez choisir un orange ou un jaune vif pour faire ressortir une annonce de vente.

#### **Couleur de la bordure**

- **Ce que fait ce paramètre :** Il contrôle la couleur de la bordure autour du bloc « Hot Info ».
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une couleur spécifique est définie (par exemple, #000000 pour le noir) :* La bordure du bloc « Hot Info » s'affichera dans la couleur choisie.
  - *Lorsqu'il est laissé par défaut ou transparent :* Le bloc pourrait apparaître sans bordure visible, ou il pourrait hériter d'une couleur de bordure de votre thème.
- **Valeur recommandée :** Souvent, une couleur de bordure qui correspond à la couleur de votre texte ou une nuance légèrement plus foncée de votre couleur de fond fonctionne bien.
- **Scénario / exemple pour le marchand :** Si votre fond est bleu clair, une bordure bleu plus foncé peut lui donner un aspect propre et défini.

#### **Taille de la bordure (en pixels)**

- **Ce que fait ce paramètre :** Il détermine l'épaisseur de la bordure autour du bloc « Hot Info », mesurée en pixels.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une valeur comme « 2 » est définie :* Le bloc aura une bordure de 2 pixels d'épaisseur.
  - *Lorsqu'une valeur de « 0 » est définie :* Aucune bordure ne sera affichée.
- **Valeur recommandée :** Commencez par une petite valeur comme « 1 » ou « 2 » pour une bordure subtile. Augmentez-la si vous souhaitez un cadre plus prononcé.
- **Scénario / exemple pour le marchand :** Une bordure de 2px peut encadrer subtilement votre message, le faisant ressembler davantage à un élément distinct sur la page.

#### **Hauteur (en pixels)**

- **Ce que fait ce paramètre :** Il contrôle la hauteur fixe du bloc « Hot Info », mesurée en pixels.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une valeur comme « 50 » est définie :* Le bloc aura une hauteur de 50 pixels.
  - *Lorsque le contenu dépasse la hauteur :* Si votre contenu est plus grand que la hauteur spécifiée, une barre de défilement apparaîtra dans le bloc, permettant aux clients de faire défiler le contenu.
- **Valeur recommandée :** Gardez cette valeur relativement petite (par exemple, 40-60px) pour éviter de prendre trop d'espace d'écran, surtout sur mobile. Ajustez en fonction de la quantité de contenu que vous avez.
- **Scénario / exemple pour le marchand :** Si vous avez un message court, sur une seule ligne, une hauteur de 40px pourrait être parfaite. Si vous avez quelques lignes de texte, vous pourriez avoir besoin de 60-80px.

#### **Langue par défaut (PS\_LANG\_DEFAULT)**

- **Ce que fait ce paramètre :** C'est un paramètre PrestaShop standard qui définit la langue par défaut de votre boutique. Bien que non directement configuré par ce module, le champ de contenu du module affichera généralement le contenu pour la langue actuellement sélectionnée dans le back office, par défaut celle-ci.
- **Effet de la modification de ce paramètre :** Cela affecte la langue par défaut de l'ensemble de votre boutique PrestaShop et la façon dont le contenu multilingue est géré. Pour ce module, cela signifie que le contenu que vous saisissez sera associé à la langue que vous êtes en train de modifier dans le back office.
- **Valeur recommandée :** Cela devrait être défini sur la langue principale de votre boutique.
- **Scénario / exemple pour le marchand :** Si votre marché principal est la France, cela serait défini sur le français. Lorsque vous saisissez du contenu pour le bloc « Hot Info », assurez-vous que vous modifiez dans la bonne langue si votre boutique prend en charge plusieurs langues.

#### **Mises à jour MyPresta.eu (mypresta\_updates, update\_, updatev\_)**

- **Ce que font ces paramètres :** Ce sont des paramètres internes utilisés par les modules MyPresta.eu pour vérifier et gérer les mises à jour. Ils stockent généralement des informations sur la version du module et la date de la dernière vérification des mises à jour.
- **Effet de la modification de ces paramètres :**
  - *Lorsque activé/actif :* Le module peut communiquer avec les serveurs MyPresta.eu pour vous informer des nouvelles versions ou des correctifs de sécurité.
  - *Lorsque désactivé/inactif :* Le module ne vérifiera pas les mises à jour automatiquement.
- **Valeur recommandée :** Laissez ces paramètres tels quels. Ils sont essentiels pour maintenir votre module à jour et sécurisé.
- **Scénario / exemple pour le marchand :** Vous n'interagissez généralement pas directement avec ceux-ci. Ils garantissent que vous êtes invité dans votre back office PrestaShop lorsqu'une nouvelle version du module est disponible en téléchargement depuis votre compte MyPresta.eu.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | **Contenu du bloc Hot Info** | Votre message personnalisé | Le texte, les images, les liens réels affichés dans la barre latérale inférieure. |
| Configuration du module | **Couleur de fond** | Choisir pour correspondre/contraster avec le thème | Définit la couleur de fond du bloc d'informations. |
| Configuration du module | **Couleur de la bordure** | Choisir pour correspondre/contraster avec le thème | Définit la couleur de la bordure autour du bloc d'informations. |
| Configuration du module | **Taille de la bordure (en pixels)** | 1 ou 2 | Définit l'épaisseur de la bordure. Mettre à 0 pour aucune bordure. |
| Configuration du module | **Hauteur (en pixels)** | 40-60 | Définit la hauteur fixe du bloc d'informations. Le contenu dépassant cette hauteur défilera. |
| Configuration du module | **PS\_LANG\_DEFAULT** | Langue principale de votre boutique | Paramètre de langue par défaut de PrestaShop, affecte l'édition du contenu. |
| Configuration du module | **Mises à jour MyPresta.eu** | Activé | Paramètres internes pour les vérifications de mise à jour du module. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mon bloc « Hot Info » n'apparaît pas sur le front office.**

- **R :** Tout d'abord, assurez-vous que le module est installé et activé dans **Modules > Gestionnaire de modules**. Deuxièmement, vérifiez si vous avez réellement ajouté du contenu dans le champ « Contenu du bloc Hot Info » dans la configuration du module. Un bloc vide pourrait ne pas s'afficher. Enfin, videz votre cache PrestaShop (**Paramètres avancés > Performances > Vider le cache**) et le cache de votre navigateur.

**Q2 : Le bloc « Hot Info » a l'air étrange ou ne correspond pas au style de mon thème.**

- **R :** Le module fournit des options de style de base (arrière-plan, couleur/taille de la bordure, hauteur). S'il entre toujours en conflit avec votre thème, le CSS de votre thème pourrait annuler les styles du module.
  - **Solution pour les marchands :** Essayez d'ajuster les couleurs de fond et de bordure dans les paramètres du module pour voir si vous pouvez trouver une meilleure correspondance. Sinon, vous pourriez avoir besoin d'un webmaster pour ajouter du CSS personnalisé à votre thème afin de cibler et de styliser spécifiquement le bloc du module.
  - **Solution pour les webmasters :** Inspectez l'élément dans les outils de développement du navigateur pour identifier les règles CSS conflictuelles et appliquez des règles plus spécifiques ou `!important` dans le fichier CSS personnalisé de votre thème.

**Q3 : Comment ajouter des images ou des liens au contenu « Hot Info » ?**

- **R :** Utilisez l'éditeur de texte enrichi fourni pour le paramètre « Contenu du bloc Hot Info ». Il dispose de boutons pour insérer des images, créer des liens, formater du texte (gras, italique), et plus encore, comme un traitement de texte standard. Cliquez sur l'icône « Image » pour télécharger et insérer une image, ou sélectionnez du texte et cliquez sur l'icône « Lien » pour ajouter un hyperlien.

**Q4 : Puis-je faire apparaître le bloc « Hot Info » uniquement sur certaines pages ?**

- **R :** Ce module, dans sa version actuelle, est conçu pour apparaître globalement sur toutes les pages où le hook `displayHeader` est exécuté. Si vous avez besoin d'une visibilité spécifique à une page, vous auriez besoin d'un développement personnalisé pour modifier la logique d'affichage du module ou utiliser un module distinct conçu pour l'affichage de contenu conditionnel.

**Q5 : Le sélecteur de couleurs ne fonctionne pas ou n'apparaît pas.**

- **R :** Assurez-vous que le JavaScript de votre navigateur est activé. Parfois, des conflits avec d'autres modules ou le JavaScript du thème peuvent empêcher le sélecteur de couleurs de se charger correctement. Essayez de vider le cache et les cookies de votre navigateur. Si le problème persiste, cela pourrait indiquer un conflit JavaScript plus complexe, qu'un webmaster devrait examiner.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé du module « Hot Info - bottom sidebar » pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module `hotinfo` est un module PrestaShop standard suivant le modèle MVC le cas échéant. Il fonctionne principalement comme un module d'affichage, injectant du contenu dans le hook `displayHeader`. La configuration est gérée via la méthode `getContent()` de la classe principale du module, stockant les paramètres directement dans `ps_configuration`. Il utilise un éditeur de texte enrichi (TinyMCE) pour la saisie de contenu et un sélecteur de couleurs JavaScript pour les options de style.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs front-office ou back-office personnalisés. Toute la configuration est gérée dans le fichier principal du module `hotinfo.php` via la méthode `getContent()`.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée et n'étend pas `ObjectModel`. Toutes les données (configuration) sont stockées directement dans la table `ps_configuration`.

### 4.4 Actifs JavaScript (`views/js/`)

- **`hotinfo/jscolor/jscolor.js`**

  - **Portée :** Back-office (page de configuration du module).
  - **Description :** Il s'agit d'une bibliothèque JavaScript tierce qui fournit une interface de sélecteur de couleurs conviviale. Elle est généralement initialisée sur les champs de saisie avec une classe spécifique (par exemple, `jscolor`) pour permettre aux administrateurs de sélectionner visuellement les couleurs de fond et de bordure du bloc « Hot Info ». Elle se lie aux champs de saisie et met à jour leurs valeurs en fonction de la sélection de couleur de l'utilisateur.
- **`hotinfo/tinymce16.js`**

  - **Portée :** Back-office (page de configuration du module).
  - **Description :** Ce script initialise et configure probablement une version de l'éditeur de texte enrichi TinyMCE pour la zone de texte « Contenu du bloc Hot Info ». Il transforme une balise HTML `<textarea>` standard en un éditeur riche en fonctionnalités, permettant aux administrateurs de formater du texte, d'insérer des images, de créer des liens et de gérer le contenu HTML sans codage direct. Ce script se lierait à l'élément textarea pertinent et fournirait l'interface de l'éditeur.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`hotinfo/css/hotinfo.css`**
  - **Portée :** Front-office (boutique visible par le client).
  - **Description :** Cette feuille de style contient les règles CSS primaires pour la barre latérale inférieure « Hot Info ». Elle définit le positionnement fixe, les dimensions, l'arrière-plan, la bordure et le style du texte pour le bloc.
  - **Sélecteurs clés (les développeurs peuvent les surcharger) :**
    - `#hotinfo_block` : Le conteneur principal pour l'ensemble du bloc « Hot Info ». C'est là que `position: fixed; bottom: 0; width: 100%;` et d'autres styles globaux sont appliqués.
    - `#hotinfo_block .hotinfo_content` : Le conteneur interne pour le contenu réel, où `overflow-y: auto;` pourrait être appliqué si le contenu dépasse la hauteur définie.
    - Styles pour `p`, `a`, `img` dans `#hotinfo_block` pour garantir que le contenu est esthétique.
  - **Stratégie de surcharge :** Les développeurs peuvent surcharger ces styles en ajoutant des règles CSS plus spécifiques dans le fichier `custom.css` ou `theme.css` de leur thème, ou en créant un thème enfant et en modifiant directement le CSS du module si nécessaire.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **`hotinfo/hotinfo.tpl`**

  - **Portée :** Back-office (page de configuration du module).
  - **Description :** Ce template est utilisé pour rendre le formulaire de configuration dans le back office de PrestaShop lors de l'accès à la page de configuration du module. Il contient la structure HTML pour l'éditeur de texte enrichi, les sélecteurs de couleurs et les champs de saisie pour les paramètres de hauteur et de bordure. Il utilise des variables Smarty pour pré-remplir les champs du formulaire avec les valeurs de configuration actuelles.
- **`hotinfo/views/templates/hook/hotinfo.tpl`**

  - **Portée :** Front-office (boutique visible par le client).
  - **Description :** Ce template est responsable du rendu du bloc « Hot Info » sur la boutique. Il est accroché à `displayHeader`. Il récupère le contenu configuré, la couleur de fond, la couleur de la bordure, la taille de la bordure et la hauteur des variables Smarty passées par le module et les applique à la structure HTML.
  - **Éléments clés :**
    - Une `div` principale avec un ID comme `hotinfo_block` pour le positionnement fixe.
    - Une `div` interne pour le contenu, potentiellement avec `overflow: auto;` pour le défilement.
    - Le contenu réel est rendu à l'aide de `{html_entity_decode($hotinfo_body)}` pour afficher le HTML de l'éditeur de texte enrichi.
  - **Hook :** `displayHeader` (bien que visuellement il apparaisse en bas, le hook est dans l'en-tête pour s'assurer qu'il se charge tôt).

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de la base de données** :
  Le module ne crée aucune table SQL personnalisée. Tous les paramètres de configuration sont stockés dans la table standard `ps_configuration` de PrestaShop.

  - Entrées `PS_CONFIGURATION` :
    - `HOTINFO_BODY` : Stocke le contenu HTML du bloc « Hot Info » (multilingue).
    - `HOTINFO_BG_COLOR` : Stocke la valeur hexadécimale de la couleur de fond.
    - `HOTINFO_BR_COLOR` : Stocke la valeur hexadécimale de la couleur de la bordure.
    - `HOTINFO_BR_SIZE` : Stocke la valeur entière de l'épaisseur de la bordure.
    - `HOTINFO_HEIGHT` : Stocke la valeur entière de la hauteur du bloc.
    - `MYPRESTA_UPDATES`, `UPDATE_`, `UPDATEV_` : Clés internes pour le mécanisme de mise à jour de MyPresta.eu.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Exécuté dans la section `<head>` de chaque page. | Le module utilise ce hook pour injecter ses fichiers CSS et JavaScript, et pour rendre la structure HTML principale du bloc « Hot Info ». Bien que le bloc soit visuellement positionné en bas, le rendre via `displayHeader` garantit qu'il est disponible tôt dans le chargement de la page et peut être stylisé avec `position: fixed;` efficacement. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Hot Info - bottom sidebar », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Vous pouvez télécharger la version la plus récente du module depuis l'historique de vos commandes. Pour toute assistance technique ou question, veuillez contacter directement le support de MyPresta.eu.
