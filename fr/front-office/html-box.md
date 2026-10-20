---
title: "Html box - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Html box par MyPresta.eu."
sidebar:
  label: "Html box - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Html box sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/html-box.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/html-box/)
>
> ---


# Html box

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour une installation PrestaShop et sont suffisantes pour ce module.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Html box)

C'est l'écran de configuration principal où vous définissez le contenu de vos boîtes HTML et leur emplacement.

#### Paramètres généraux

- **Activer SSL (https) pour ce module ?** (`htmlbox_ssl`)

  - **Ce que fait ce paramètre :** Détermine si le contenu du module doit être chargé en toute sécurité via HTTPS.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (OUI) :* Garantit que tout contenu généré par ce module est servi via HTTPS, évitant les avertissements de « contenu mixte » dans les navigateurs si votre boutique utilise SSL.
    - *Lorsqu'il est désactivé (NON) :* Le contenu pourrait être servi via HTTP, ce qui peut provoquer des avertissements de sécurité sur les boutiques activées en HTTPS.
  - **Valeur recommandée :** **OUI**
  - **Scénario / exemple marchand :** Si votre boutique utilise HTTPS (ce qui devrait être le cas !), l'activation de ce paramètre garantit que votre contenu personnalisé ne déclenche pas d'alertes de sécurité pour vos clients.
- **Désactiver l'éditeur TinyMCE ?** (`htmlbox_disabletiny`)

  - **Ce que fait ce paramètre :** Contrôle si l'éditeur de texte enrichi (TinyMCE) est utilisé pour saisir votre contenu HTML.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (OUI) :* Vous verrez une zone de texte brut pour saisir votre HTML, JavaScript ou CSS. Ceci est utile si vous collez du code complexe que TinyMCE pourrait essayer de « nettoyer » ou si vous préférez écrire du HTML brut.
    - *Lorsqu'il est désactivé (NON) :* Vous disposerez d'un éditeur de texte enrichi convivial, similaire à un traitement de texte, vous permettant de formater du texte, d'ajouter des images et de créer des liens sans écrire directement du HTML.
  - **Valeur recommandée :** **NON** (sauf si vous êtes un développeur ou si vous collez du code complexe).
  - **Scénario / exemple marchand :** Si vous souhaitez ajouter rapidement une annonce en gras, laissez-le désactivé. Si vous collez un code de widget Facebook, activez-le pour empêcher l'éditeur de modifier votre code.
- **Afficher uniquement pour les clients connectés ?** (`htmlbox_logged`)

  - **Ce que fait ce paramètre :** Restreint la visibilité du contenu de la boîte HTML aux seuls clients connectés à leur compte.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (OUI) :* Seuls les clients enregistrés et connectés verront le contenu de la boîte HTML.
    - *Lorsqu'il est désactivé (NON) :* Tous les visiteurs, qu'ils soient connectés ou non, verront le contenu.
  - **Valeur recommandée :** **NON** (sauf si vous avez un contenu spécifique pour les utilisateurs connectés).
  - **Scénario / exemple marchand :** Vous pourriez l'activer si vous souhaitez afficher un message de programme de fidélité spécial ou des offres exclusives visibles uniquement par votre clientèle existante.
- **Afficher uniquement pour les clients NON connectés ?** (`htmlbox_unlogged`)

  - **Ce que fait ce paramètre :** Restreint la visibilité du contenu de la boîte HTML aux seuls clients qui ne sont *pas* connectés à leur compte.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (OUI) :* Seuls les visiteurs non connectés verront le contenu de la boîte HTML.
    - *Lorsqu'il est désactivé (NON) :* Tous les visiteurs, qu'ils soient connectés ou non, verront le contenu.
  - **Valeur recommandée :** **NON** (sauf si vous avez un contenu spécifique pour les invités).
  - **Scénario / exemple marchand :** Vous pourriez l'activer pour afficher un message « Connectez-vous ou inscrivez-vous pour des offres exclusives » afin d'encourager les nouvelles inscriptions ou les clients de retour à se connecter.

#### Champs de contenu de la boîte HTML

Ces champs sont l'endroit où vous saisissez le contenu HTML, JavaScript ou CSS réel pour chaque hook spécifique. Chaque champ correspond à un emplacement différent dans votre boutique.

- **HTML pour l'en-tête (displayTop, displayNav1, displayNav2)** (`htmlbox_header`)

  - **Ce que fait ce paramètre :** C'est le contenu qui apparaîtra dans la section d'en-tête de votre boutique. Selon votre thème, cela pourrait être `displayTop`, `displayNav1` ou `displayNav2`.
  - **Effet de la modification de ce paramètre :** Le contenu que vous saisissez ici sera visible tout en haut de votre site web.
  - **Valeur recommandée :** Laisser vide si non nécessaire.
  - **Scénario / exemple marchand :** Une bannière d'annonce à l'échelle du site (« Livraison gratuite sur toutes les commandes de plus de 50 $ ! »), une petite barre d'icônes de médias sociaux ou une barre de recherche personnalisée.
- **HTML pour la colonne supérieure (displayTopColumn)** (`htmlbox_top`)

  - **Ce que fait ce paramètre :** Ce contenu apparaît juste en dessous de l'en-tête, s'étendant souvent sur toute la largeur de la zone de contenu principale.
  - **Effet de la modification de ce paramètre :** Le contenu que vous saisissez ici sera affiché de manière proéminente en haut de votre zone de contenu principale, généralement au-dessus des listes de produits principales ou du contenu de la page d'accueil.
  - **Valeur recommandée :** Laisser vide si non nécessaire.
  - **Scénario / exemple marchand :** Une grande bannière promotionnelle pour une vente saisonnière, un carrousel de produits phares ou une introduction vidéo à votre marque.
- **HTML pour la colonne gauche (displayLeftColumn)** (`htmlbox_leftcol`)

  - **Ce que fait ce paramètre :** Ce contenu apparaît dans la barre latérale gauche de votre boutique (si votre thème en a une et qu'elle est activée).
  - **Effet de la modification de ce paramètre :** Le contenu que vous saisissez ici sera affiché dans la colonne gauche, à côté d'autres modules comme les filtres de catégorie ou la navigation.
  - **Valeur recommandée :** Laisser vide si non nécessaire.
  - **Scénario / exemple marchand :** Une liste « Acheter par marque », un formulaire d'inscription à la newsletter, une petite publicité pour une catégorie de produits spécifique ou une boîte Facebook J'aime.
- **HTML pour la colonne droite (displayRightColumn)** (`htmlbox_rightcol`)

  - **Ce que fait ce paramètre :** Ce contenu apparaît dans la barre latérale droite de votre boutique (si votre thème en a une et qu'elle est activée).
  - **Effet de la modification de ce paramètre :** Le contenu que vous saisissez ici sera affiché dans la colonne droite, de manière similaire à la colonne gauche.
  - **Valeur recommandée :** Laisser vide si non nécessaire.
  - **Scénario / exemple marchand :** Une liste des « Meilleures ventes », un bloc de contact du service client, un flux Pinterest ou une section « Produits récemment consultés ».
- **HTML pour le pied de page (displayFooter)** (`htmlbox_footercol`)

  - **Ce que fait ce paramètre :** Ce contenu apparaît dans la section du pied de page en bas de chaque page.
  - **Effet de la modification de ce paramètre :** Le contenu que vous saisissez ici sera visible tout en bas de votre site web.
  - **Valeur recommandée :** Laisser vide si non nécessaire.
  - **Scénario / exemple marchand :** Logos de méthodes de paiement, sceaux de confiance, un court texte « À propos de nous », liens de médias sociaux ou un avis de copyright personnalisé.
- **HTML pour la page d'accueil (displayHome)** (`htmlbox_homecol`)

  - **Ce que fait ce paramètre :** Ce contenu est spécifiquement affiché sur la page d'accueil de votre boutique.
  - **Effet de la modification de ce paramètre :** Le contenu que vous saisissez ici sera une partie centrale de la mise en page de votre page d'accueil.
  - **Valeur recommandée :** Laisser vide si non nécessaire.
  - **Scénario / exemple marchand :** Une grille de catégories en vedette, une section « Pourquoi acheter chez nous », des témoignages de clients ou un grand bouton d'appel à l'action.
- **HTML pour le corps (displayBody)** (`htmlbox_body`)

  - **Ce que fait ce paramètre :** Ce contenu est injecté dans la balise `<body>` de votre HTML, généralement à la toute fin avant la balise de fermeture `</body>`. Il est souvent utilisé pour des scripts globaux ou des éléments qui doivent être disponibles sur l'ensemble du site mais ne sont pas visuellement liés à une section spécifique.
  - **Effet de la modification de ce paramètre :** Le contenu sera présent sur chaque page de votre boutique, mais son placement visuel peut dépendre du CSS de votre thème. Il est excellent pour les codes de suivi ou les pop-ups.
  - **Valeur recommandée :** Laisser vide si non nécessaire.
  - **Scénario / exemple marchand :** Code de suivi Google Analytics, Pixel Facebook, une bannière de consentement aux cookies globale (si non gérée par un autre module) ou un script de widget de chat.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer SSL (https) pour ce module ? | OUI | Assure que le contenu est chargé en toute sécurité, évitant les avertissements de contenu mixte. |
| Configuration du module | Désactiver l'éditeur TinyMCE ? | NON | Contrôle l'éditeur de texte enrichi pour la saisie de contenu. Activer pour le code brut. |
| Configuration du module | Afficher uniquement pour les clients connectés ? | NON | Restreint la visibilité du contenu aux utilisateurs connectés. |
| Configuration du module | Afficher uniquement pour les clients NON connectés ? | NON | Restreint la visibilité du contenu aux utilisateurs invités. |
| Configuration du module | HTML pour l'en-tête | Vide | Contenu personnalisé dans la zone d'en-tête (par exemple, annonces, bannières supérieures). |
| Configuration du module | HTML pour la colonne supérieure | Vide | Contenu personnalisé sous l'en-tête, souvent pleine largeur (par exemple, promotions principales). |
| Configuration du module | HTML pour la colonne gauche | Vide | Contenu personnalisé dans la barre latérale gauche (par exemple, flux sociaux, newsletter). |
| Configuration du module | HTML pour la colonne droite | Vide | Contenu personnalisé dans la barre latérale droite (par exemple, meilleures ventes, service client). |
| Configuration du module | HTML pour le pied de page | Vide | Contenu personnalisé dans le pied de page (par exemple, logos de paiement, sceaux de confiance). |
| Configuration du module | HTML pour la page d'accueil | Vide | Contenu spécifiquement sur la page d'accueil (par exemple, produits phares). |
| Configuration du module | HTML pour le corps | Vide | Contenu/scripts globaux injectés dans le `<body>` (par exemple, analyses, widgets de chat). |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : Mon HTML personnalisé ne s'affiche pas ou semble cassé.**
R :

1. **Vérifiez le Hook :** Assurez-vous d'avoir saisi le contenu dans le champ de la boîte HTML correct pour l'emplacement souhaité (par exemple, `HTML pour la page d'accueil` pour la page d'accueil).
2. **Videz le cache :** Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures). PrestaShop met souvent le contenu en cache, et les nouveaux paramètres du module peuvent ne pas apparaître immédiatement.
3. **Inspectez le HTML :** Si vous êtes à l'aise, utilisez les outils de développement de votre navigateur (F12) pour inspecter la zone où le contenu devrait se trouver. Recherchez les erreurs dans la console ou vérifiez si votre HTML est présent mais mal stylisé.
4. **Interférence de TinyMCE :** Si vous collez du code complexe (en particulier du JavaScript ou des iframes), essayez d'activer « Désactiver l'éditeur TinyMCE ? » pour vous assurer que l'éditeur ne supprime pas ou ne modifie pas votre code.

**Q : Le contenu apparaît, mais il ne s'affiche pas correctement sur mobile.**
R : Le module lui-même est réactif, mais le *contenu que vous ajoutez* doit également l'être.

1. **Utilisez du HTML/CSS réactif :** Si vous écrivez du HTML personnalisé, assurez-vous d'utiliser les principes de conception réactive (par exemple, `max-width: 100%` pour les images, les requêtes média CSS).
2. **Widgets tiers :** Si vous intégrez un widget (comme Facebook ou Twitter), vérifiez si le fournisseur du widget propose des codes d'intégration ou des paramètres réactifs.
3. **Contenu simple :** Pour le contenu mobile critique, gardez-le simple : texte brut, petites images et appels à l'action clairs.

**Q : J'ai ajouté du JavaScript, mais il ne s'exécute pas.**
R :

1. **Placement :** Le JavaScript ajouté au champ `HTML pour le corps` est généralement l'endroit le plus sûr pour les scripts globaux, car il est chargé à la fin de la page.
2. **Erreurs de syntaxe :** Vérifiez votre code JavaScript pour toute erreur de syntaxe. Une seule erreur peut empêcher l'exécution de l'intégralité du script.
3. **Conflits jQuery :** Si votre script dépend de jQuery, assurez-vous qu'il est chargé correctement et qu'il n'y a pas de conflits avec la version de jQuery de PrestaShop. Vous devrez peut-être envelopper votre code dans `(function($){ /* votre code */ })(jQuery);` ou utiliser `jQuery.noConflict();`.
4. **Scripts externes :** Si vous liez à un fichier `.js` externe, assurez-vous que l'URL est correcte et accessible.

**Q : Comment traduire le contenu de mes boîtes HTML pour différentes langues ?**
R : La version actuelle du module n'offre pas de champs multilingues intégrés pour chaque boîte HTML. Pour obtenir un contenu multilingue, vous avez deux options principales :

1. **Détection manuelle de la langue (Avancé) :** Vous pouvez intégrer une logique conditionnelle dans le contenu de votre boîte HTML en utilisant des variables Smarty (si votre thème permet le traitement Smarty dans les hooks) ou JavaScript pour détecter la langue actuelle et afficher un contenu différent. C'est une solution plus avancée.
   *Exemple (Smarty) :*

   ```
   {if $language.iso\_code == 'en'} <p>Welcome to our English store!</p>{elseif $language.iso\_code == 'fr'} <p>Bienvenue dans notre boutique française !</p>{/if}
   ```
2. **Modules séparés (Solution de contournement) :** Pour le contenu critique, vous pourriez envisager d'installer des instances séparées du module « Html box » (si autorisé par le développeur du module ou en dupliquant le module) et d'attribuer chacune à une langue spécifique, puis de gérer leur affichage via les positions de module de PrestaShop. C'est une solution de contournement plus complexe.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module Html box.

### 4.1 Vue d'ensemble de l'architecture

Le module `Html box` est un module PrestaShop simple principalement conçu pour injecter du contenu HTML/JS/CSS personnalisé dans divers hooks du front-office. Il suit une structure de module PrestaShop classique, tirant parti de la classe `Module` pour l'installation, la désinstallation et la configuration, et utilisant les méthodes `hook` pour rendre le contenu dans le front-office. La configuration est gérée via la méthode `getContent()`, qui rend un formulaire de configuration PrestaShop standard. Le module stocke son contenu directement dans la table `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient **pas** de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toutes les fonctionnalités, y compris la configuration et le rendu du front-office, sont gérées directement dans le fichier principal du module `htmlbox.php`.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit **pas** de classes personnalisées ou d'instances `ObjectModel`. Toutes les données sont stockées en tant que valeurs de configuration.

### 4.4 Actifs JavaScript (`views/js/`)

- **`htmlbox/tinymce16.inc.js`**
  - **Portée :** Back-office (spécifiquement la page de configuration du module).
  - **Objectif :** Ce fichier est responsable de l'initialisation et de la configuration de l'éditeur de texte enrichi TinyMCE dans le formulaire de configuration du module. Il transforme les éléments `<textarea>` standard en un éditeur WYSIWYG convivial, permettant aux marchands de formater du texte, d'insérer des images et de gérer le contenu HTML sans codage direct. Il inclut probablement des paramètres personnalisés pour intégrer TinyMCE au gestionnaire de fichiers de PrestaShop pour le téléchargement d'images.
  - **Notes du développeur :** Si `htmlbox_disabletiny` est activé, ce script ne sera pas chargé ou sa fonctionnalité sera contournée. Les développeurs souhaitant personnaliser l'expérience TinyMCE (par exemple, ajouter des boutons personnalisés, modifier la disposition de la barre d'outils) devront modifier ce fichier ou remplacer son chargement/sa configuration.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut **pas** de fichiers CSS personnalisés. Tout style pour le contenu HTML injecté doit être fourni dans le contenu HTML lui-même (styles en ligne ou balises `<style>`) ou par le thème PrestaShop actif.

### 4.6 Structure du modèle Smarty (`views/templates/`)

- **`views/templates/hook/html.tpl`**
  - **Portée :** Front-office.
  - **Rendu du hook :** C'est le fichier de modèle principal utilisé par le module pour rendre le contenu HTML personnalisé dans tous les hooks front-office enregistrés.
  - **Contenu :** Il contient probablement une structure simple pour afficher la variable `$html_content`, qui est passée par les méthodes de hook du module.
  - **Notes du développeur :** Ce modèle est minimal. Le contenu réel est chargé dynamiquement à partir de la table `ps_configuration` en fonction du hook. Les développeurs peuvent remplacer ce modèle dans leur thème (par exemple, `themes/votreetheme/modules/htmlbox/html.tpl`) pour envelopper le contenu dans des `div` personnalisés, ajouter des classes spécifiques ou appliquer une logique conditionnelle, bien que la plupart des personnalisations soient effectuées directement dans le contenu de la boîte HTML elle-même.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de la base de données** :
  Le module ne crée aucune table de base de données personnalisée. Toutes les configurations et le contenu sont stockés dans la table `ps_configuration` standard de PrestaShop en utilisant les clés suivantes :

  - `mypresta_updates`
  - `update_`
  - `updatev_`
  - `htmlbox_header`
  - `htmlbox_top`
  - `htmlbox_leftcol`
  - `htmlbox_rightcol`
  - `htmlbox_footercol`
  - `htmlbox_homecol`
  - `htmlbox_body`
  - `htmlbox_ssl`
  - `htmlbox_origtiny`
  - `htmlbox_disabletiny`
  - `htmlbox_home`
  - `htmlbox_hook`
  - `htmlbox_logged`
  - `htmlbox_unlogged`
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Principalement pour ajouter des balises meta, des liens CSS ou du JavaScript qui doivent être chargés tôt. |
| `displayTop` | Section supérieure de la page, généralement au-dessus du contenu principal. | Contenu général pour le haut de la page, souvent dépendant du thème. |
| `displayNav1` | Barre de navigation, souvent la barre tout en haut avec des liens rapides. | Contenu pour la première barre de navigation. |
| `displayNav2` | Barre de navigation secondaire, souvent sous `displayNav1`. | Contenu pour la deuxième barre de navigation. |
| `displayTopColumn` | Zone pleine largeur sous l'en-tête, au-dessus du contenu principal. | Zone de contenu proéminente, souvent utilisée pour des bannières ou des sliders. |
| `displayLeftColumn` | Barre latérale gauche sur les pages où elle est activée. | Contenu pour la barre latérale gauche (par exemple, filtres, catégories, blocs personnalisés). |
| `displayRightColumn` | Barre latérale droite sur les pages où elle est activée. | Contenu pour la barre latérale droite (par exemple, publicités, widgets sociaux). |
| `displayHome` | Zone de contenu principale de la page d'accueil. | Contenu spécifiquement pour la page d'accueil. |
| `displayFooter` | Section inférieure de chaque page. | Contenu pour le pied de page (par exemple, copyright, logos de paiement, liens). |
| `displayBody` | À la fin de la balise `<body>`. | Idéal pour le JavaScript global (par exemple, analyses, widgets de chat) ou les éléments qui doivent être chargés en dernier. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). MyPresta.eu fournit un support dédié pour tous ses modules.
