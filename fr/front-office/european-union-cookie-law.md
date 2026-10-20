---
title: "Loi sur les cookies de l'Union Européenne - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Loi sur les cookies de l'Union Européenne par MyPresta.eu."
sidebar:
  label: "Loi sur les cookies de l'Union Européenne - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module European Union Cookie Law sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/european-union-cookie-law.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/european-union-cookie-law/)
>
> ---


# Loi sur les cookies de l'Union Européenne

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration spéciale du serveur n'est généralement nécessaire.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal et unique du module Loi sur les cookies de l'Union Européenne. Vous trouverez tous les paramètres ici pour personnaliser votre notification de cookies.

#### **Activer / Désactiver le module**

- **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la notification de cookies sur l'ensemble de votre boutique.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* La barre de notification de cookies apparaîtra sur votre front office selon vos autres paramètres.
  - *Lorsqu'il est désactivé :* La barre de notification de cookies ne sera affichée à aucun visiteur.
- **Valeur recommandée :** OUI (sauf si vous avez une autre méthode de conformité aux cookies).
- **Scénario / exemple de marchand :** Vous venez d'installer le module et souhaitez activer l'avis de cookies. Réglez ceci sur « OUI ». Si vous devez le masquer temporairement pour la maintenance ou les tests, vous pouvez le régler sur « NON ».

#### **Texte du cookie**

- **Ce que fait ce paramètre :** C'est le message réel qui sera affiché à vos clients concernant l'utilisation des cookies. Il prend en charge plusieurs langues, vous permettant de fournir un message localisé pour chaque langue activée dans votre boutique.
- **Effet de la modification de ce paramètre :** Le texte que vous saisissez ici sera affiché dans la barre de notification des cookies. Vous pouvez utiliser l'éditeur de texte enrichi pour formater le texte, ajouter des liens (par exemple, vers votre page de politique de confidentialité complète) et mettre en évidence les informations importantes.
- **Valeur recommandée :** Un message clair et concis qui informe les utilisateurs sur les cookies et inclut idéalement un lien vers votre politique de confidentialité complète ou votre page de politique de cookies.
- **Scénario / exemple de marchand :** Vous pourriez écrire : « Ce site web utilise des cookies pour vous garantir la meilleure expérience sur notre site web. [Lien vers la politique de confidentialité] ». Assurez-vous de traduire cela dans toutes les langues actives de votre boutique.

#### **Texte du bouton**

- **Ce que fait ce paramètre :** Il définit le texte affiché sur le bouton sur lequel les clients cliquent pour accuser réception ou accepter la politique en matière de cookies. Comme le texte du cookie, il prend en charge plusieurs langues.
- **Effet de la modification de ce paramètre :** Le bouton affichera le texte que vous spécifiez. Cliquer sur ce bouton masquera la notification de cookies pour l'utilisateur.
- **Valeur recommandée :** « J'ai compris », « Accepter », « D'accord », « Continuer » ou « OK ».
- **Scénario / exemple de marchand :** Pour indiquer clairement que les utilisateurs reconnaissent la politique, vous pouvez définir ceci sur « J'ai compris et j'accepte ».

#### **Position**

- **Ce que fait ce paramètre :** Détermine où la barre de notification de cookies apparaît sur votre site web.
- **Effet de la modification de ce paramètre :**
  - *Haut :* La barre apparaîtra fixée en haut de la fenêtre du navigateur.
  - *Bas :* La barre apparaîtra fixée en bas de la fenêtre du navigateur.
- **Valeur recommandée :** Bas (souvent moins intrusive que le haut, qui peut parfois interférer avec les éléments d'en-tête).
- **Scénario / exemple de marchand :** Vous souhaitez que l'avis de cookies soit visible mais n'obstrue pas votre navigation principale ou votre logo. Choisir « Bas » est généralement un bon compromis.

#### **Couleur de fond**

- **Ce que fait ce paramètre :** Vous permet de choisir la couleur de fond de la barre de notification de cookies. Cela aide à intégrer visuellement la barre au design de votre boutique.
- **Effet de la modification de ce paramètre :** L'arrière-plan de la barre de cookies changera pour la couleur sélectionnée. Un outil de sélection de couleurs est généralement fourni pour une sélection facile.
- **Valeur recommandée :** Une couleur qui contraste bien avec la couleur de votre texte et qui complète l'image de marque de votre boutique.
- **Scénario / exemple de marchand :** Votre boutique utilise beaucoup de bleu. Vous pouvez choisir un bleu clair ou un gris subtil pour l'arrière-plan afin de correspondre à votre thème.

#### **Couleur du texte**

- **Ce que fait ce paramètre :** Vous permet de choisir la couleur du texte dans la barre de notification de cookies.
- **Effet de la modification de ce paramètre :** Le texte de la barre de cookies changera pour la couleur sélectionnée.
- **Valeur recommandée :** Une couleur qui offre un bon contraste avec la couleur de fond choisie pour une meilleure lisibilité.
- **Scénario / exemple de marchand :** Si la couleur de votre arrière-plan est foncée, choisissez une couleur de texte claire (par exemple, blanc, gris clair). Si votre arrière-plan est clair, choisissez une couleur de texte foncée (par exemple, noir, gris foncé).

#### **Couleur du lien**

- **Ce que fait ce paramètre :** Vous permet de choisir la couleur de tous les liens inclus dans votre « Texte du cookie » (par exemple, un lien vers votre politique de confidentialité).
- **Effet de la modification de ce paramètre :** Toutes les balises `<a>` dans le texte de la barre de cookies s'afficheront dans cette couleur.
- **Valeur recommandée :** Une couleur qui se distingue de la couleur du texte principal mais qui correspond toujours à votre marque.
- **Scénario / exemple de marchand :** Vous voulez que le lien vers votre politique de confidentialité soit facilement visible. Vous pouvez choisir la couleur d'accentuation de votre marque pour le lien.

#### **Couleur de fond du bouton**

- **Ce que fait ce paramètre :** Définit la couleur de fond du bouton « Texte du bouton ».
- **Effet de la modification de ce paramètre :** Le bouton aura la couleur de fond sélectionnée.
- **Valeur recommandée :** Une couleur qui fait ressortir le bouton et encourage les clics, correspondant souvent à la couleur du bouton d'appel à l'action principal de votre boutique.
- **Scénario / exemple de marchand :** Les boutons « Ajouter au panier » de votre boutique sont verts. Vous pouvez choisir le vert pour l'arrière-plan du bouton de cookie afin de maintenir la cohérence.

#### **Couleur du texte du bouton**

- **Ce que fait ce paramètre :** Définit la couleur du texte sur le bouton « Texte du bouton ».
- **Effet de la modification de ce paramètre :** Le texte du bouton s'affichera dans cette couleur.
- **Valeur recommandée :** Une couleur qui offre un bon contraste avec la couleur de fond du bouton pour une meilleure lisibilité.
- **Scénario / exemple de marchand :** Si l'arrière-plan de votre bouton est vert foncé, choisissez le blanc ou une couleur très claire pour le texte du bouton.

#### **Expiration du cookie (en jours)**

- **Ce que fait ce paramètre :** Détermine combien de temps la notification de cookies reste masquée après qu'un utilisateur a cliqué sur le bouton « J'ai compris ». Après cette période, la notification réapparaîtra pour l'utilisateur.
- **Effet de la modification de ce paramètre :**
  - *Défini à 30 :* La notification sera masquée pendant 30 jours pour cet utilisateur spécifique.
  - *Défini à 0 :* La notification pourrait réapparaître à chaque visite ou session, ce qui n'est généralement pas recommandé car cela peut être gênant.
- **Valeur recommandée :** 30 à 365 jours. Une pratique courante est de 90 ou 180 jours.
- **Scénario / exemple de marchand :** Pour éviter de déranger à plusieurs reprises les clients qui reviennent, vous définissez ceci sur « 180 » jours. Cela signifie qu'un client qui accepte la politique ne reverra pas la barre pendant six mois.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | **Activer / Désactiver le module** | OUI | Interrupteur principal pour la visibilité de la barre de cookies. |
| Configuration du module | **Texte du cookie** | Personnalisable | Le message principal concernant l'utilisation des cookies, prend en charge le texte enrichi et le multilingue. |
| Configuration du module | **Texte du bouton** | Personnalisable | Texte sur le bouton pour masquer l'avis, multilingue. |
| Configuration du module | **Position** | Bas | Où la barre apparaît (Haut ou Bas de l'écran). |
| Configuration du module | **Couleur de fond** | Personnalisable | Couleur de fond de la barre de cookies. |
| Configuration du module | **Couleur du texte** | Personnalisable | Couleur du texte principal dans la barre de cookies. |
| Configuration du module | **Couleur du lien** | Personnalisable | Couleur de tous les liens dans le texte du cookie. |
| Configuration du module | **Couleur de fond du bouton** | Personnalisable | Couleur de fond du bouton de masquage. |
| Configuration du module | **Couleur du texte du bouton** | Personnalisable | Couleur du texte sur le bouton de masquage. |
| Configuration du module | **Expiration du cookie (en jours)** | 180-365 jours | Durée pendant laquelle l'avis reste masqué après acceptation par l'utilisateur. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q1 : La barre de cookies n'apparaît pas sur ma boutique.**
R1 :

- **Vérifiez « Activer / Désactiver le module » :** Assurez-vous que ce paramètre est défini sur « OUI » dans la configuration du module.
- **Videz le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » en haut à droite. Parfois, un ancien contenu mis en cache empêche les nouvelles modifications du module d'apparaître.
- **Vérifiez les conflits :** Désactivez temporairement les autres modules récemment installés pour voir s'il y a un conflit.
- **Cache du navigateur :** Essayez de vider le cache de votre navigateur ou d'ouvrir votre boutique dans une fenêtre de navigation privée/incognito.

**Q2 : J'ai mis à jour le texte, mais il ne change pas sur le front office.**
R2 :

- **Enregistrer les modifications :** Assurez-vous d'avoir cliqué sur le bouton « Enregistrer » après avoir effectué des modifications dans la configuration du module.
- **Vider le cache de PrestaShop :** Comme mentionné ci-dessus, vider le cache Smarty (sous **Paramètres avancés > Performances**) est souvent nécessaire pour que les modifications de modèle et de texte prennent effet.
- **Vérifiez la langue :** Assurez-vous que vous modifiez le texte pour la bonne langue si votre boutique est multilingue.

**Q3 : La barre de cookies a l'air étrange ou ne correspond pas à mon thème.**
R3 :

- **Ajustez les couleurs :** Utilisez les paramètres « Couleur de fond », « Couleur du texte », « Couleur du lien », « Couleur de fond du bouton » et « Couleur du texte du bouton » pour correspondre à la palette de votre thème.
- **Conflits de thème :** Certains thèmes personnalisés peuvent avoir des styles CSS conflictuels. Si l'ajustement des couleurs n'aide pas, vous pourriez avoir besoin d'un développeur web pour inspecter le CSS et apporter des ajustements mineurs.

**Q4 : Comment ajouter un lien vers ma politique de confidentialité dans le texte du cookie ?**
R4 :

- Dans le champ « Texte du cookie », utilisez l'éditeur de texte enrichi. Tapez le texte que vous souhaitez lier (par exemple, « Politique de confidentialité »), sélectionnez-le, puis cliquez sur l'icône « Lien » dans la barre d'outils de l'éditeur. Saisissez l'URL de votre page de politique de confidentialité.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs, les webmasters et les agences travaillant avec le module Loi sur les cookies de l'Union Européenne.

### 4.1 Aperçu de l'architecture

Le module `uecookie` est un module PrestaShop simple, principalement conçu pour injecter un modèle de front-office dans un hook d'affichage, contrôlé par une méthode de configuration `getContent()` standard. Il utilise la classe `Module` de PrestaShop pour l'installation, la désinstallation et la configuration, et utilise les modèles Smarty pour le rendu de la notification de cookies. La logique côté client pour masquer la barre de cookies est gérée via JavaScript.

### 4.2 Contrôleurs (`controllers/`)

- Ce module ne contient **pas** de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toutes les fonctionnalités sont gérées dans le fichier principal du module et ses modèles et ressources associés.

### 4.3 Classes et modèles principaux (`classes/`)

- Ce module ne contient **pas** de classes personnalisées ou de définitions `ObjectModel`. Toute la configuration est stockée directement dans `ps_configuration` à l'aide de `Configuration::get()` et `Configuration::updateValue()`.

### 4.4 Ressources JavaScript (`views/js/`)

- `uecookie/jscolor/jscolor.js` :
  - **Portée :** Back-office.
  - **Objectif :** Fournit une fonctionnalité de sélecteur de couleurs JavaScript pour le formulaire de configuration du module, permettant aux administrateurs de sélectionner visuellement les couleurs pour la barre de cookies.
- `uecookie/tinymce-original.js` :
  - **Portée :** Back-office.
  - **Objectif :** Une version complète de l'éditeur de texte enrichi TinyMCE, utilisée pour le champ « Texte du cookie » dans la configuration du module. Cela permet aux administrateurs de formater le texte, d'ajouter des liens, etc.
- `uecookie/tinymce16.inc.js` :
  - **Portée :** Back-office.
  - **Objectif :** Probablement un fichier d'inclusion ou de configuration pour TinyMCE, personnalisant éventuellement sa barre d'outils ou ses options pour la compatibilité PrestaShop 1.6 ou des besoins spécifiques du module.
- `uecookie/views/js/scripts.js` :
  - **Portée :** Front-office.
  - **Objectif :** Ce script gère la logique côté client pour la barre de notification de cookies.
    - **Écouteurs d'événements :** Écoute probablement un événement de clic sur le bouton « J'ai compris ».
    - **Manipulation du DOM :** Masque l'élément de la barre de cookies du DOM lors de la suppression.
    - **Gestion des cookies :** Définit un cookie de navigateur (par exemple, `uecookie_accepted`) avec une date d'expiration (déterminée par le paramètre « Expiration du cookie ») pour empêcher la barre de réapparaître pendant la durée spécifiée.
    - **Vérification initiale :** Au chargement de la page, il vérifie la présence du cookie `uecookie_accepted` pour déterminer s'il faut afficher la barre ou non.

### 4.5 Feuilles de style CSS (`views/css/`)

- Ce module ne contient **pas** de fichiers CSS personnalisés dans `views/css/`. Le style de la barre de cookies est probablement en ligne ou généré dynamiquement en fonction des paramètres de couleur, ou repose sur des styles de navigateur par défaut minimaux. Les développeurs souhaitant personnaliser davantage l'apparence devraient cibler la structure HTML générée par `top.tpl` à l'aide du CSS personnalisé de leur thème.

### 4.6 Structure du modèle Smarty (`views/templates/`)

- **Modèles de hook (`views/templates/hook/`)** :
  - `uecookie/top.tpl` :
    - **Hook :** Ce modèle est principalement conçu pour être rendu dans un hook de front-office tel que `displayHeader`, `displayFooter`, `displayTop` ou `displayBeforeBodyClosingTag`. La méthode `hookDisplayHeader` du module est généralement responsable de l'enregistrement et du rendu de ce modèle.
    - **Sortie :** Il génère la structure HTML de la barre de notification de cookies, y compris le texte personnalisable, le bouton et le style dynamique basé sur les paramètres de configuration du module (couleur de fond, couleur du texte, etc.). Il inclut également le JavaScript nécessaire (`scripts.js`) pour gérer la suppression et la définition des cookies.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Ce module ne crée aucune table de base de données personnalisée.
  - Tous les paramètres de configuration sont stockés dans la table `ps_configuration`. Les entrées de configuration clés incluraient :
    - `UECOOKIE_ENABLED` (booléen)
    - `UECOOKIE_TEXT` (chaîne multilingue)
    - `UECOOKIE_BUTTON_TEXT` (chaîne multilingue)
    - `UECOOKIE_POSITION` (chaîne : 'top' ou 'bottom')
    - `UECOOKIE_BG_COLOR` (chaîne : code couleur hexadécimal)
    - `UECOOKIE_TEXT_COLOR` (chaîne : code couleur hexadécimal)
    - `UECOOKIE_LINK_COLOR` (chaîne : code couleur hexadécimal)
    - `UECOOKIE_BUTTON_BG_COLOR` (chaîne : code couleur hexadécimal)
    - `UECOOKIE_BUTTON_TEXT_COLOR` (chaîne : code couleur hexadécimal)
    - `UECOOKIE_EXPIRATION` (entier : jours)
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Exécuté dans la section `<head>` de chaque page du front-office. | Utilisé pour injecter les fichiers CSS (le cas échéant) et JavaScript du module, et potentiellement la structure HTML initiale de la barre de cookies si elle est positionnée en haut. |
| `displayFooter` | Exécuté en bas de chaque page du front-office, avant la balise de fermeture `</body>`. | Peut être utilisé pour injecter le HTML et le JavaScript de la barre de cookies, surtout si elle est positionnée en bas. |
| `displayTop` | Exécuté dans la section d'en-tête du thème, généralement au-dessus du contenu principal. | Hook alternatif pour afficher la barre de cookies en haut. |
| `displayBeforeBodyClosingTag` | Exécuté juste avant la balise `</body>`. | Un hook robuste pour injecter des éléments JavaScript et HTML qui doivent apparaître à la toute fin de la page. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Loi sur les cookies de l'Union Européenne », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
