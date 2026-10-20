---
title: "Slider de contenu personnalisé - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Slider de contenu personnalisé par MyPresta.eu."
sidebar:
  label: "Slider de contenu personnalisé - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Custom contents slider sur MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/custom-contents-slider.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/sliders-slideshows/custom-contents-slider/)
>
> ---


# Slider de contenu personnalisé

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement nécessaire.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à la page principale des paramètres du module « Slider de contenu personnalisé ». C'est ici que vous définissez le contenu, l'apparence et le comportement de vos sliders.

La page de configuration est alimentée par la bibliothèque `SmartyTemplatesManager`, qui vous permet de créer et de gérer plusieurs blocs de contenu personnalisé.

#### **Formulaire principal (mainForm.tpl)**

Cette section fournit un aperçu de vos sliders existants et vous permet d'en ajouter de nouveaux.

- **Ce que fait cette section :** Affiche une liste de tous les sliders de contenu personnalisé que vous avez créés. Chaque entrée affiche des informations de base comme le nom, la position et le statut du slider.
- **Effet de la modification de cette section :** À partir d'ici, vous pouvez rapidement voir quels sliders sont actifs et où ils sont affichés. Vous pouvez également cliquer pour modifier des sliders existants ou en ajouter de nouveaux.
- **Action recommandée :** Passez en revue vos sliders existants. Si vous configurez pour la première fois, vous voudrez cliquer sur le bouton « Ajouter un nouveau modèle ».

#### **Formulaire de création/modification de modèle (createTemplateForm.tpl / editTemplateForm.tpl)**

Lorsque vous cliquez sur « Ajouter un nouveau modèle » ou « Modifier » un slider existant, vous accédez à un formulaire où vous définissez tous les détails de ce slider spécifique.

- **Nom du modèle :**

  - **Ce que fait ce paramètre :** Il s'agit d'un nom interne pour votre slider, visible uniquement dans le back office. Il vous aide à identifier les différents sliders.
  - **Effet de la modification de ce paramètre :** La modification de ce paramètre n'affecte que la façon dont vous le voyez dans le panneau d'administration ; cela n'a aucun impact sur le front-office.
  - **Valeur recommandée :** Un nom descriptif, par exemple, « Slider gauche soldes d'été », « Inscription newsletter bas ».
  - **Scénario / exemple de marchand :** Si vous avez plusieurs promotions, les nommer clairement vous aide à les gérer.
- **Contenu du modèle :**

  - **Ce que fait ce paramètre :** C'est le cœur de votre slider. Vous pouvez y saisir n'importe quel HTML, texte ou même code Smarty. Ce contenu sera affiché à l'intérieur du panneau coulissant.
  - **Effet de la modification de ce paramètre :** Cela modifie directement ce que vos clients voient lorsque le slider s'agrandit. Vous pouvez inclure des images, des liens, des paragraphes, des formulaires, etc.
  - **Valeur recommandée :** Utilisez le HTML standard. Gardez-le concis et visuellement attrayant. Pour les images, utilisez des URL absolues ou l'aide d'image de PrestaShop.
  - **Scénario / exemple de marchand :**

    ```
    <h3>Offre à durée limitée !</h3><p>Obtenez <strong>15 % de réduction</strong> sur tous les articles de la collection d'été !</p><a href="{$link->getPageLink('category', true, null, ['id\_category' => 123])}" class="button btn btn-primary">Achetez maintenant !</a>
    ```

    (Remarque : les variables Smarty comme `{$link->getPageLink(...)` nécessitent que le traitement Smarty soit activé pour le contenu, ce que ce module prend en charge.)
- **Position :**

  - **Ce que fait ce paramètre :** Détermine où le slider apparaîtra sur l'écran du client.
  - **Effet de la modification de ce paramètre :**
    - *Gauche :* Le slider apparaît depuis le bord gauche.
    - *Droite :* Le slider apparaît depuis le bord droit.
    - *Bas :* Le slider apparaît depuis le bord inférieur.
  - **Valeur recommandée :** Choisissez en fonction de votre design et des autres éléments de votre page. La droite et le bas sont souvent moins intrusifs que la gauche.
  - **Scénario / exemple de marchand :** Utilisez « Droite » pour un formulaire de contact rapide, « Bas » pour une bannière de consentement aux cookies, ou « Gauche » pour un code de réduction spécial.
- **Ouvrir sur :**

  - **Ce que fait ce paramètre :** Définit comment le slider s'agrandit pour afficher son contenu.
  - **Effet de la modification de ce paramètre :**
    - *Clic :* Le slider s'agrandit uniquement lorsque le client clique sur son onglet de déclenchement.
    - *Survol :* Le slider s'agrandit lorsque le client déplace son curseur de souris sur son onglet de déclenchement.
  - **Valeur recommandée :** « Clic » est généralement moins intrusif et évite les ouvertures accidentelles. « Survol » peut être bon pour un contenu très subtil et rapide à consulter.
  - **Scénario / exemple de marchand :** Pour les annonces importantes ou les formulaires, « Clic » est préférable. Pour un bouton de chat rapide « Bonjour, comment puis-je vous aider ? », « Survol » pourrait fonctionner.
- **Actif :**

  - **Ce que fait ce paramètre :** Active ou désactive la visibilité de ce slider spécifique sur votre front office.
  - **Effet de la modification de ce paramètre :**
    - *Activé (Oui) :* Le slider apparaîtra sur votre boutique selon ses paramètres.
    - *Désactivé (Non) :* Le slider sera masqué de votre boutique, mais sa configuration sera sauvegardée.
  - **Valeur recommandée :** « Oui » pour les sliders actifs, « Non » pour les sliders que vous souhaitez masquer temporairement ou sur lesquels vous travaillez encore.
  - **Scénario / exemple de marchand :** Vous pourriez désactiver un slider de promotion de Noël après les fêtes, puis le réactiver l'année suivante.

#### **Gestionnaire de boutons (buttonManager.tpl)**

Cette section fait partie du `SmartyTemplatesManager` et vous permet de gérer les boutons ou les déclencheurs de vos sliders. Bien que le module utilise principalement le paramètre « Ouvrir sur », cette section peut offrir une personnalisation supplémentaire pour le déclencheur visuel lui-même.

- **Ce que fait cette section :** Fournit des options pour personnaliser l'apparence de l'onglet ou du bouton avec lequel les clients interagissent pour ouvrir le slider. Cela peut inclure du texte, des icônes ou un style de base.
- **Effet de la modification de cette section :** Modifie l'apparence visuelle du déclencheur du slider sur le front office.
- **Valeur recommandée :** Gardez le déclencheur clair et invitant. Utilisez un texte concis ou une icône pertinente.
- **Scénario / exemple de marchand :** Vous pouvez définir le texte du bouton sur « Soldes ! », « Contactez-nous », ou utiliser une petite icône de chat.

#### **Sélection d'entrée (selectInput.tpl)**

Ceci est un modèle générique pour les sélections déroulantes au sein du `SmartyTemplatesManager`. Il est utilisé pour des paramètres comme « Position » et « Ouvrir sur ».

- **Ce que fait cette section :** Présente une liste déroulante d'options prédéfinies pour un paramètre particulier.
- **Effet de la modification de cette section :** Vous permet de choisir parmi un ensemble limité d'options pour une configuration donnée.
- **Valeur recommandée :** Sélectionnez l'option qui correspond le mieux au comportement souhaité du slider.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Formulaire principal | (Liste des sliders) | N/A | Aperçu de tous les sliders créés ; permet d'ajouter/modifier. |
| Créer/Modifier le modèle | **Nom du modèle** | Nom descriptif | Identifiant interne du slider dans le back office. |
| Créer/Modifier le modèle | **Contenu du modèle** | HTML/Texte personnalisé | Le contenu réel affiché à l'intérieur du slider. |
| Créer/Modifier le modèle | **Position** | Droite / Bas | Où le slider apparaît sur l'écran (Gauche, Droite, Bas). |
| Créer/Modifier le modèle | **Ouvrir sur** | Clic | Comment le slider s'agrandit (Clic ou Survol). |
| Créer/Modifier le modèle | **Actif** | Oui | Active/désactive la visibilité du slider sur le front office. |
| Gestionnaire de boutons | (Options des boutons) | N/A | Personnalise le déclencheur visuel du slider (texte, icône, style). |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : Mon slider n'apparaît pas sur le front office. Que dois-je vérifier ?**
R :

1. **Le slider est-il « Actif » ?** Allez dans la configuration du module, modifiez votre slider et assurez-vous que le paramètre « Actif » est défini sur « Oui ».
2. **Le contenu est-il valide ?** Assurez-vous qu'il n'y a pas de balises HTML non fermées ou d'erreurs JavaScript dans votre « Contenu du modèle » qui pourraient empêcher l'affichage.
3. **Videz votre cache :** Allez dans **Paramètres avancés > Performances** dans votre back office PrestaShop et videz le cache Smarty (et éventuellement l'intégralité du cache).
4. **Vérifiez les conflits :** Désactivez temporairement les autres modules qui pourraient ajouter des éléments flottants ou modifier la mise en page pour voir s'il y a un conflit.

**Q : Le slider apparaît, mais le style semble incorrect ou ne correspond pas à mon thème.**
R :

1. **CSS par défaut du module :** Le module est livré avec son propre CSS. Le CSS de votre thème pourrait le remplacer, ou vice-versa.
2. **Style de thème personnalisé :** Vous devrez peut-être ajouter des règles CSS personnalisées à la feuille de style de votre thème pour ajuster l'apparence du slider. Utilisez les outils de développement de votre navigateur (F12) pour inspecter les éléments du slider et identifier les classes CSS à cibler.
3. **Style du contenu :** Si vous insérez du HTML brut dans le « Contenu du modèle », assurez-vous d'utiliser des classes ou des styles en ligne appropriés qui fonctionnent avec votre thème.

**Q : Puis-je avoir plusieurs sliders actifs en même temps ?**
R : Oui, le module prend en charge plusieurs sliders. Cependant, soyez attentif à l'expérience utilisateur. Avoir trop de sliders (par exemple, un à gauche, un à droite et un en bas) peut encombrer l'interface et submerger les clients. Il est généralement préférable d'en utiliser un ou deux de manière stratégique.

**Q : Comment ajouter des images ou des liens à mon contenu de slider ?**
R : Vous pouvez utiliser des balises HTML standard dans le champ « Contenu du modèle » :

- **Images :** `<img src="votre_url_image.jpg" alt="Description" style="width:100px;">` (Utilisez des URL absolues pour les images).
- **Liens :** `<a href="votre_url_page.html">Cliquez ici</a>` (Vous pouvez également utiliser des variables Smarty pour les liens PrestaShop, par exemple, `<a href="{$link->getPageLink('contact')}">Contactez-nous</a>`).

**Q : Fonctionne-t-il avec le multilingue et le multi-boutique ?**
R : Oui, le module est conçu pour fonctionner correctement dans des environnements multilingues et multi-boutiques. Vous pouvez créer différents sliders ou différents contenus pour le même slider pour chaque langue et boutique, permettant une messagerie très ciblée.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Slider de contenu personnalisé » (`saslider`) est construit comme un module PrestaShop standard, tirant principalement parti de la classe `Module` pour son cycle de vie et de `SmartyTemplatesManager` pour la création et la gestion de contenu dynamique. Il s'intègre au système de hooks de PrestaShop pour injecter ses ressources et son contenu front-office. La logique principale du module réside dans son fichier `index.php` principal, gérant la configuration, l'installation et le rendu front-office. Il n'utilise pas de contrôleurs front ou admin dédiés, mais s'appuie plutôt sur la méthode `getContent()` pour sa configuration back-office et l'enregistrement direct des hooks pour l'affichage front-office.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. Tout le rendu front-office est géré directement via des hooks enregistrés dans le fichier principal du module.
- **Contrôleurs Admin Back-Office** : Aucun. Toute la configuration back-office est gérée via la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne définit pas de classes personnalisées étendant `ObjectModel`. Son stockage de données principal pour les configurations de slider est probablement géré via `Configuration::updateValue()` pour les paramètres au niveau du module et potentiellement des données sérialisées stockées dans `ps_configuration` pour le contenu et les propriétés des sliders individuels, gérées par la bibliothèque `SmartyTemplatesManager`.

### 4.4 Ressources JavaScript (`views/js/`)

Le module inclut plusieurs fichiers JavaScript, principalement responsables de l'animation coulissante et de la logique d'interaction (clic/survol) pour différentes positions de slider.

- `saslider/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`

  - **Portée** : Back-office.
  - **Responsabilité** : Ce script fait partie de la bibliothèque `SmartyTemplatesManager`. Il gère probablement la création, l'édition et la gestion dynamiques des modèles (sliders) au sein de l'interface de configuration du module. Il peut gérer les soumissions de formulaires, les appels AJAX pour la sauvegarde/le chargement de contenu et les interactions de l'interface utilisateur pour le système de gestion des modèles.
- `saslider/views/js/saslider-click-bottom.js`

  - **Portée** : Front-office.
  - **Responsabilité** : Implémente la logique JavaScript pour un slider positionné en bas qui s'agrandit/se réduit lors d'un événement de clic. Il liera des écouteurs de clic à l'élément déclencheur du slider, basculera les classes CSS ou manipulera directement les propriétés `style` pour animer l'expansion et la contraction du slider.
- `saslider/views/js/saslider-click-left.js`

  - **Portée** : Front-office.
  - **Responsabilité** : Similaire à `saslider-click-bottom.js`, mais spécifiquement pour un slider positionné à gauche, gérant son expansion/contraction basée sur le clic.
- `saslider/views/js/saslider-click-right.js`

  - **Portée** : Front-office.
  - **Responsabilité** : Similaire à `saslider-click-bottom.js`, mais spécifiquement pour un slider positionné à droite, gérant son expansion/contraction basée sur le clic.
- `saslider/views/js/saslider-hover-bottom.js`

  - **Portée** : Front-office.
  - **Responsabilité** : Implémente la logique JavaScript pour un slider positionné en bas qui s'agrandit/se réduit lors d'un événement de survol. Il liera des écouteurs `mouseenter` et `mouseleave` à l'élément déclencheur du slider, basculant sa visibilité et sa position.
- `saslider/views/js/saslider-hover-left.js`

  - **Portée** : Front-office.
  - **Responsabilité** : Similaire à `saslider-hover-bottom.js`, mais spécifiquement pour un slider positionné à gauche, gérant son expansion/contraction basée sur le survol.
- `saslider/views/js/saslider-hover-right.js`

  - **Portée** : Front-office.
  - **Responsabilité** : Similaire à `saslider-hover-bottom.js`, mais spécifiquement pour un slider positionné à droite, gérant son expansion/contraction basée sur le survol.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module inclut plusieurs fichiers CSS pour le style de configuration du back-office et l'apparence du slider front-office.

- `saslider/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`

  - **Portée** : Style du formulaire d'administration du back-office.
  - **Composants d'interface utilisateur principaux** : Style les éléments de l'interface `SmartyTemplatesManager`, y compris les formulaires, les boutons, les champs de saisie et potentiellement les tableaux de liste pour la gestion des modèles.
  - **Sélecteurs de classe CSS clés** : Inclut probablement des classes pour les mises en page de formulaires, les groupes de saisie et les composants généraux de l'interface utilisateur administrative.
- `saslider/views/css/saslider-bottom.css`

  - **Portée** : Style client front-office.
  - **Composants d'interface utilisateur principaux** : Définit le positionnement spécifique, l'état initial (réduit) et les propriétés d'animation pour le slider positionné en bas.
  - **Sélecteurs de classe CSS clés** : `body #saslider_bottom`, `.saslider-bottom-tab`, `.saslider-bottom-content`, classes pour les états `open`/`closed`.
- `saslider/views/css/saslider-left.css`

  - **Portée** : Style client front-office.
  - **Composants d'interface utilisateur principaux** : Définit le positionnement spécifique, l'état initial et les propriétés d'animation pour le slider positionné à gauche.
  - **Sélecteurs de classe CSS clés** : `body #saslider_left`, `.saslider-left-tab`, `.saslider-left-content`, classes pour les états `open`/`closed`.
- `saslider/views/css/saslider-right.css`

  - **Portée** : Style client front-office.
  - **Composants d'interface utilisateur principaux** : Définit le positionnement spécifique, l'état initial et les propriétés d'animation pour le slider positionné à droite.
  - **Sélecteurs de classe CSS clés** : `body #saslider_right`, `.saslider-right-tab`, `.saslider-right-content`, classes pour les états `open`/`closed`.
- `saslider/views/css/saslider.css`

  - **Portée** : Style client front-office.
  - **Composants d'interface utilisateur principaux** : Contient des styles généraux et communs applicables à toutes les positions de slider, tels que les styles de conteneur de base, les tailles de police, les couleurs, le z-index et les propriétés de transition.
  - **Sélecteurs de classe CSS clés** : `.saslider-container`, `.saslider-tab`, `.saslider-content`, et potentiellement des ajustements réactifs.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module utilise des modèles Smarty pour son interface de configuration back-office et le rendu du contenu front-office.

- **Modèles d'administration (`saslider/lib/smartyTemplatesManager/views/`)** :

  - `buttonManager.tpl` : Rend probablement l'interface utilisateur pour la gestion du bouton/onglet de déclenchement du slider.
  - `createTemplateForm.tpl` : Le modèle de formulaire utilisé lors de la création d'un nouveau slider.
  - `editTemplateForm.tpl` : Le modèle de formulaire utilisé lors de la modification d'un slider existant.
  - `mainForm.tpl` : Le modèle de page de configuration principal, listant probablement tous les sliders et fournissant le bouton « Ajouter nouveau ».
  - `selectInput.tpl` : Un modèle réutilisable pour le rendu des éléments `<select>` déroulants dans les formulaires d'administration.
- **Modèles de hook (`saslider/views/`)** :

  - `footer-bottom.tpl` : Rend la structure HTML pour un slider positionné en bas. Ce modèle est probablement accroché à `displayFooter` ou à un hook global similaire. Il contient les `div` d'enveloppe pour le slider, son onglet de déclenchement et la zone de contenu.
  - `footer-left.tpl` : Rend la structure HTML pour un slider positionné à gauche. Probablement accroché à `displayFooter` ou similaire.
  - `footer-right.tpl` : Rend la structure HTML pour un slider positionné à droite. Probablement accroché à `displayFooter` ou similaire.
- **Modèles d'exemple/utilitaires (`saslider/lib/smartyTemplatesManager/tpl/`)** :

  - `example.tpl` : Un modèle d'exemple, éventuellement pour la démonstration ou les tests internes du `SmartyTemplatesManager`.
  - `MyShortCode.tpl` : Suggère que le `SmartyTemplatesManager` pourrait prendre en charge une forme de shortcode ou d'insertion de contenu dynamique.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne définit pas explicitement de tables SQL personnalisées via `install.sql`.
  - La configuration des sliders individuels (contenu, position, statut actif, ouverture sur) est stockée dans la table `ps_configuration`, probablement sous forme de données sérialisées sous des clés de configuration spécifiques gérées par la bibliothèque `SmartyTemplatesManager`. Par exemple, `PS_SASLIDER_TEMPLATES` ou similaire.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Utilisé pour enregistrer les ressources CSS et JavaScript (par exemple, `saslider.css`, `saslider-click-right.js`) requises pour l'affichage et la fonctionnalité du slider en front-office. |
| `displayFooter` | À la fin de la section `<body>` de chaque page, avant la balise de fermeture `</body>`. | Utilisé pour rendre la structure HTML réelle du slider (par exemple, `footer-bottom.tpl`, `footer-left.tpl`, `footer-right.tpl`) dans la page, en s'assurant qu'il flotte correctement. |
| `displayLeftColumn` | Dans la colonne de gauche de la boutique. | *Potentiellement* utilisé pour rendre le slider, bien que `displayFooter` soit plus courant pour les éléments flottants. |
| `displayRightColumn` | Dans la colonne de droite de la boutique. | *Potentiellement* utilisé pour rendre le slider, bien que `displayFooter` soit plus courant pour les éléments flottants. |
| `displayProductAdditionalInfo` | Sur la page produit, sous les informations principales du produit. | *Potentiellement* utilisé pour rendre un slider spécifiquement sur les pages produit, par exemple pour des offres connexes. |
| `actionFrontControllerSetMedia` | Après qu'un contrôleur front a défini ses médias, permettant aux modules d'ajouter les leurs. | Utilisé pour ajouter conditionnellement des fichiers CSS/JS en fonction de la page actuelle ou d'autres conditions, garantissant un chargement optimal. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Slider de contenu personnalisé », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à fournir une assistance rapide et à garantir que votre module fonctionne correctement avec votre boutique PrestaShop.
"""
