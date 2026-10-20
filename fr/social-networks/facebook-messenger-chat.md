---
title: "Chat Facebook Messenger - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop de chat Facebook Messenger par MyPresta.eu."
sidebar:
  label: "Chat Facebook Messenger - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Facebook Messenger chat sur MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-messenger-chat.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/facebook-messenger-chat/)
>
> ---


# Chat Facebook Messenger

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont habituellement disponibles sur tous les environnements d'hébergement modernes. Aucune extension spéciale n'est nécessaire pour ce module au-delà des exigences standard de PrestaShop.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal de votre module de chat Facebook Messenger. Vous y trouverez toutes les options pour personnaliser l'apparence et le fonctionnement du chat sur votre boutique.

- **Ce que fait ce paramètre :** Il s'agit d'un paramètre général pour les modules MyPresta.eu afin de vérifier les mises à jour.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (Oui) :* Le module vérifiera périodiquement MyPresta.eu pour de nouvelles versions.
  - *Lorsqu'il est désactivé (Non) :* Le module ne vérifiera pas les mises à jour.
- **Valeur recommandée :** **Oui** (Il est toujours bon de rester à jour pour la sécurité et les nouvelles fonctionnalités).
- **Scénario / exemple pour le marchand :** Garder cette option activée garantit que vous êtes informé lorsqu'une nouvelle version avec des corrections de bugs ou de nouvelles fonctionnalités est disponible, aidant votre boutique à rester à jour et sécurisée.

---

- **Ce que fait ce paramètre :** Cette option vous permet de choisir entre deux types d'intégration de chat Facebook : un simple chat de Page Facebook ou le chat Facebook Messenger plus avancé.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur « Chat de Page Facebook » :* Un widget de chat plus simple apparaîtra, principalement pour envoyer des messages à votre Page Facebook.
  - *Lorsqu'il est défini sur « Chat Facebook Messenger » :* Le widget de chat Facebook Messenger complet apparaîtra, offrant une expérience de conversation plus riche, y compris des messages de bienvenue et potentiellement des fonctionnalités plus avancées de Facebook.
- **Valeur recommandée :** **Chat Facebook Messenger** (Offre une meilleure expérience utilisateur et plus de fonctionnalités).
- **Scénario / exemple pour le marchand :** Si vous souhaitez l'expérience Messenger complète et interactive avec des messages de bienvenue, choisissez « Chat Facebook Messenger ». Si vous préférez un expéditeur de messages très basique et léger, « Chat de Page Facebook » pourrait être suffisant.

---

- **Ce que fait ce paramètre :** Ce paramètre aide à améliorer les scores de performance de votre boutique sur des outils comme Google PageSpeed Insights en empêchant le chat Facebook de se charger immédiatement, ce qui peut parfois bloquer le rendu de votre page.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (Oui) :* Le script de chat Facebook se chargera avec un léger délai ou de manière non bloquante, ce qui peut améliorer vos scores Google PageSpeed.
  - *Lorsqu'il est désactivé (Non) :* Le script de chat Facebook se chargera normalement, ce qui pourrait légèrement impacter les métriques de performance de chargement de page.
- **Valeur recommandée :** **Oui** (Recommandé pour un meilleur SEO et une meilleure expérience utilisateur).
- **Scénario / exemple pour le marchand :** Si vous êtes préoccupé par les métriques de performance de votre boutique et que vous voulez vous assurer que le chat n'a pas d'impact négatif, activez cette option.

---

- **Ce que fait ce paramètre :** Il contrôle si le SDK (Software Development Kit) de l'application Facebook est inclus sur votre site web. Le SDK est nécessaire pour la pleine fonctionnalité du chat Facebook Messenger, en particulier pour des fonctionnalités comme l'identification des utilisateurs connectés.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (Oui) :* Le SDK Facebook sera chargé, activant toutes les fonctionnalités du chat Messenger.
  - *Lorsqu'il est désactivé (Non) :* Certaines fonctionnalités avancées de Messenger, notamment celles liées à l'identification de l'utilisateur et aux salutations personnalisées, pourraient ne pas fonctionner correctement.
- **Valeur recommandée :** **Oui** (Requis pour la pleine fonctionnalité du chat Messenger).
- **Scénario / exemple pour le marchand :** Si vous souhaitez que le chat reconnaisse si un client est connecté à Facebook et affiche un message de bienvenue personnalisé, vous devez activer cette option.

---

- **Ce que fait ce paramètre :** C'est votre identifiant unique pour votre application Facebook. Vous devez créer une application Facebook sur le site des développeurs Facebook pour obtenir cet ID. Il relie votre site web à votre page Facebook pour les fonctionnalités avancées de Messenger.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est correctement saisi :* Active la pleine fonctionnalité du chat Facebook Messenger, y compris les messages de bienvenue personnalisés et potentiellement une identification plus précise de l'utilisateur.
  - *Lorsqu'il est incorrect ou vide :* Le chat Messenger pourrait ne pas fonctionner correctement ou pas du tout.
- **Valeur recommandée :** Votre **ID d'application Facebook** réel. (Laissez vide si « Inclure le SDK de l'application Facebook » est désactivé).
- **Scénario / exemple pour le marchand :** Pour utiliser les fonctionnalités avancées du chat Messenger, vous devrez vous rendre sur [developers.facebook.com](https://developers.facebook.com/), créer une application, la lier à votre page Facebook, puis copier l'ID de l'application ici.

---

- **Ce que fait ce paramètre :** Ce paramètre vous permet de spécifier la langue de l'interface du chat Facebook Messenger.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'un code de langue est sélectionné :* Le widget de chat affichera le texte (comme « Envoyez-nous un message ») dans la langue choisie.
  - *Lorsqu'il est laissé vide ou incorrect :* Le chat pourrait utiliser l'anglais par défaut ou la langue du navigateur.
- **Valeur recommandée :** Sélectionnez la langue principale de votre boutique, par exemple, `fr_FR` pour le français (France), `en_US` pour l'anglais (États-Unis), `es_ES` pour l'espagnol (Espagne).
- **Scénario / exemple pour le marchand :** Si votre boutique dessert principalement des clients en Allemagne, définir cette option sur `de_DE` garantira que l'interface de chat est en allemand, la rendant plus conviviale pour vos clients locaux.

---

- **Ce que fait ce paramètre :** C'est l'URL de votre Page Fan Facebook. C'est crucial car cela indique au widget de chat où envoyer les messages.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est correctement saisi :* Les messages envoyés via le widget de chat iront directement dans la boîte de réception de votre Page Facebook.
  - *Lorsqu'il est incorrect ou vide :* Le widget de chat ne pourra pas se connecter à votre page, et les messages ne seront pas livrés.
- **Valeur recommandée :** L'URL complète de votre Page Fan Facebook, par exemple, `https://www.facebook.com/MyPresta.eu`.
- **Scénario / exemple pour le marchand :** Si votre Page Facebook est `https://www.facebook.com/MaSuperBoutique/`, vous entreriez cette URL ici afin que les clients puissent vous joindre.

---

- **Ce que fait ce paramètre :** C'est le message initial affiché aux clients déjà connectés à Facebook lorsqu'ils ouvrent le chat.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini :* Les clients connectés verront ce message de bienvenue personnalisé, rendant l'interaction plus accueillante.
  - *Lorsqu'il est vide :* Un message de bienvenue Facebook par défaut pourrait être utilisé, ou aucun message n'apparaîtra.
- **Valeur recommandée :** Un message de bienvenue amical et concis, par exemple, « Bonjour [Nom du client], comment pouvons-nous vous aider aujourd'hui ? »
- **Scénario / exemple pour le marchand :** Vous pourriez définir ceci sur « Bienvenue de retour ! Comment pouvons-nous vous aider avec vos achats aujourd'hui ? » pour que les clients réguliers se sentent valorisés.

---

- **Ce que fait ce paramètre :** C'est le message initial affiché aux clients qui ne sont PAS connectés à Facebook lorsqu'ils ouvrent le chat.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini :* Les clients non connectés verront ce message de bienvenue, les encourageant à démarrer une conversation.
  - *Lorsqu'il est vide :* Un message de bienvenue Facebook par défaut pourrait être utilisé, ou aucun message n'apparaîtra.
- **Valeur recommandée :** Un message clair et invitant, par exemple, « Bonjour ! Nous sommes là pour vous aider. Posez-nous n'importe quelle question ! »
- **Scénario / exemple pour le marchand :** Pour les nouveaux visiteurs, vous pourriez utiliser « Bonjour ! Une question sur nos produits ? Discutez avec nous ! »

---

- **Ce que fait ce paramètre :** C'est l'ID numérique de votre Page Facebook. Vous pouvez le trouver dans la section « À propos » de votre Page Facebook ou en utilisant un outil de recherche d'ID de Page Facebook. Il est essentiel pour lier le widget de chat à votre page spécifique.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est correctement saisi :* Le widget de chat identifiera et se connectera correctement à votre Page Facebook.
  - *Lorsqu'il est incorrect ou vide :* Le widget de chat ne fonctionnera pas, car il ne saura pas à quelle page se connecter.
- **Valeur recommandée :** Votre **ID de Page Facebook** réel.
- **Scénario / exemple pour le marchand :** Si l'ID de votre Page Facebook est `123456789012345`, vous entreriez ce numéro ici. C'est distinct de l'ID d'application.

---

- **Ce que fait ce paramètre :** Il contrôle la position du widget de chat sur votre site web.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur « Gauche » :* L'icône/le panneau de chat apparaîtra sur le côté inférieur gauche de votre écran.
  - *Lorsqu'il est défini sur « Droite » :* L'icône/le panneau de chat apparaîtra sur le côté inférieur droit de votre écran.
- **Valeur recommandée :** **Droite** (C'est une position courante et souvent moins intrusive, car de nombreux sites web ont une navigation ou d'autres éléments sur la gauche).
- **Scénario / exemple pour le marchand :** Si la navigation principale de votre site web ou une bannière cruciale se trouve à gauche, vous choisiriez « Droite » pour éviter de l'obscurcir.

---

- **Ce que fait ce paramètre :** C'est le texte qui apparaît comme titre de la fenêtre de chat ou du panneau coulissant avant le début d'une conversation.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini :* Les clients verront ce titre, indiquant clairement l'objet du chat.
  - *Lorsqu'il est vide :* Un titre par défaut pourrait être utilisé, ou aucun titre n'apparaîtra, ce qui peut être déroutant.
- **Valeur recommandée :** Un titre clair et invitant, par exemple, « Discutez avec nous ! », « Support client » ou « Questions ? ».
- **Scénario / exemple pour le marchand :** Définir ceci sur « Besoin d'aide ? » indique clairement aux clients qu'ils peuvent obtenir de l'aide via le chat.

---

- **Ce que fait ce paramètre :** Il vous permet de personnaliser la couleur du texte à l'intérieur du widget de chat Facebook.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'un code couleur est saisi :* Le texte du widget de chat s'affichera dans la couleur choisie.
  - *Lorsqu'il est vide :* La couleur de texte par défaut de Facebook Messenger sera utilisée.
- **Valeur recommandée :** Choisissez une couleur qui contraste bien avec votre couleur de fond et correspond à votre marque. Utilisez un code couleur hexadécimal (par exemple, `#FFFFFF` pour le blanc, `#000000` pour le noir).
- **Scénario / exemple pour le marchand :** Si les couleurs de votre marque sont le bleu foncé et le blanc, vous pourriez définir la couleur de la police sur `#FFFFFF` (blanc) si votre couleur de fond est le bleu foncé.

---

- **Ce que fait ce paramètre :** Il vous permet de personnaliser la couleur de fond du widget de chat Facebook.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'un code couleur est saisi :* L'arrière-plan du widget de chat s'affichera dans la couleur choisie.
  - *Lorsqu'il est vide :* La couleur de fond par défaut de Facebook Messenger sera utilisée.
- **Valeur recommandée :** Choisissez une couleur qui complète le design de votre boutique. Utilisez un code couleur hexadécimal (par exemple, `#F0F2F5` pour le gris clair, `#3B5998` pour le bleu Facebook).
- **Scénario / exemple pour le marchand :** Pour intégrer le chat de manière transparente au design de votre boutique, vous pourriez définir la couleur de fond sur un gris subtil ou une couleur de votre palette de marque.

---

- **Ce que fait ce paramètre :** Il vous permet de personnaliser la couleur d'accentuation principale du chat Facebook Messenger, comme le bouton d'envoi ou les éléments actifs.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'un code couleur est saisi :* Les éléments interactifs clés du widget de chat s'afficheront dans la couleur choisie.
  - *Lorsqu'il est vide :* La couleur d'accentuation par défaut de Facebook Messenger (généralement le bleu Facebook) sera utilisée.
- **Valeur recommandée :** Choisissez une couleur qui correspond à la couleur d'accentuation principale ou secondaire de votre marque. Utilisez un code couleur hexadécimal (par exemple, `#1877F2` pour le bleu Facebook, ou la couleur d'appel à l'action de votre marque).
- **Scénario / exemple pour le marchand :** Si les boutons d'appel à l'action de votre boutique sont verts, définir cette option sur un vert similaire (`#28A745`) donnera au widget de chat une sensation plus intégrée à votre site.

---

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Mises à jour MyPresta.eu | Oui | Active les vérifications de mise à jour du module pour la sécurité et les fonctionnalités. |
| Configuration du module | Type de chat | Chat Facebook Messenger | Choisit entre le chat de page Facebook basique et l'expérience Messenger complète. |
| Configuration du module | Désactiver le chat pour Google Insights | Oui | Améliore les scores PageSpeed en retardant le chargement du script de chat. |
| Configuration du module | Inclure le SDK de l'application Facebook | Oui | Active les fonctionnalités avancées de Messenger comme les messages de bienvenue personnalisés. |
| Configuration du module | Votre ID d'application | Votre ID d'application Facebook | Lie votre site web à votre application Facebook pour la pleine fonctionnalité de Messenger. |
| Configuration du module | Codes de langue de l'application Facebook | `fr_FR` (ou la langue de votre boutique) | Définit la langue de l'interface du chat. |
| Configuration du module | URL de la page fan Facebook (récepteur de messages) | L'URL de votre page Facebook | Dirige les messages des clients vers la boîte de réception de votre page Facebook. |
| Configuration du module | Message de bienvenue pour les utilisateurs connectés | « Bonjour [Nom du client], comment pouvons-nous vous aider aujourd'hui ? » | Message de bienvenue personnalisé pour les utilisateurs Facebook connectés. |
| Configuration du module | Message de bienvenue pour les utilisateurs non connectés | « Bonjour ! Nous sommes là pour vous aider. Posez-nous n'importe quelle question ! » | Message invitant pour les utilisateurs non connectés à Facebook. |
| Configuration du module | Votre ID de page Facebook | Votre ID de page Facebook | Identifie votre page Facebook spécifique pour la connexion du chat. |
| Configuration du module | Où afficher ? | Droite | Positionne le widget de chat sur le côté gauche ou droit de l'écran. |
| Configuration du module | Titre du panneau coulissant | « Discutez avec nous ! » | Texte affiché comme titre de la fenêtre de chat. |
| Configuration du module | Couleur de la police du chat Facebook | `#000000` (noir) ou la couleur de votre marque | Personnalise la couleur du texte à l'intérieur du widget de chat. |
| Configuration du module | Couleur de fond du chat Facebook | `#F0F2F5` (gris clair) ou la couleur de votre marque | Personnalise la couleur de fond du widget de chat. |
| Configuration du module | Couleur de Facebook Messenger | `#1877F2` (bleu Facebook) ou la couleur de votre marque | Personnalise la couleur d'accentuation des éléments interactifs du chat. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Le widget de chat n'apparaît pas sur ma boutique. Que dois-je faire ?**
R :

1. **Vérifiez l'état du module :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que le module « Chat Facebook Messenger » est installé et activé.
2. **Vérifiez la configuration :** Revérifiez tous les paramètres sur la page de configuration du module, en particulier « Votre ID d'application », « URL de la page fan Facebook » et « Votre ID de page Facebook ». Même un seul caractère incorrect peut l'empêcher de fonctionner.
3. **Videz le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures). Parfois, d'anciens fichiers mis en cache empêchent l'affichage de nouveaux modules.
4. **Compatibilité du thème :** Si vous utilisez un thème très personnalisé, il pourrait y avoir un conflit. Passez temporairement au thème PrestaShop par défaut pour voir si le chat apparaît. Si c'est le cas, votre thème pourrait nécessiter un petit ajustement.

**Q : Mes messages de bienvenue n'apparaissent pas, ou le chat ne reconnaît pas les utilisateurs connectés.**
R :

1. **Activez le SDK :** Assurez-vous que « Inclure le SDK de l'application Facebook » est défini sur **Oui**.
2. **Fournissez l'ID d'application :** Assurez-vous que « Votre ID d'application » est correctement saisi. Vous devez créer une application Facebook et la lier à votre page pour l'obtenir.
3. **Connexion Facebook :** Le client doit être connecté à Facebook dans son navigateur pour que le message de bienvenue personnalisé fonctionne.

**Q : Le widget de chat semble déplacé ou ne correspond pas au design de ma boutique.**
R :

1. **Utilisez les paramètres de couleur :** Allez dans la configuration du module et ajustez « Couleur de la police du chat Facebook », « Couleur de fond du chat Facebook » et « Couleur de Facebook Messenger » pour correspondre à la palette de votre marque.
2. **Positionnement :** Expérimentez avec le paramètre « Où afficher ? » (Gauche/Droite) pour trouver la position la moins intrusive pour votre site.

**Q : Comment trouver mon ID de page Facebook et mon ID d'application ?**
R :

- **ID de page Facebook :** Allez sur votre page Facebook, cliquez sur « À propos » dans le menu de gauche. Faites défiler vers le bas, et vous devriez voir « ID de page ».
- **ID d'application Facebook :** Vous devez créer un compte développeur Facebook, puis créer une nouvelle application. Une fois créée, l'ID d'application sera visible dans votre tableau de bord d'application. Assurez-vous de lier cette application à votre page Facebook.

**Q : Ce module va-t-il ralentir mon site web ?**
R : Le SDK de Facebook peut parfois impacter les temps de chargement des pages. Cependant, le module inclut une option « Désactiver le chat pour Google Insights ». L'activation de cette option peut aider à atténuer les impacts sur les performances en chargeant le script de manière non bloquante, améliorant ainsi vos scores PageSpeed.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module `Chat Facebook Messenger` (`fbchat`) est un module PrestaShop standard suivant un modèle de type MVC dans le cadre du module. Il exploite principalement le système de hooks de PrestaShop pour injecter du JavaScript et du HTML dans le front-office. La configuration est gérée via la méthode `getContent()` dans la classe principale du module, stockant les paramètres dans `ps_configuration`. Le module s'intègre directement avec le SDK de la plateforme Facebook Messenger, s'appuyant sur des ressources Facebook externes pour sa fonctionnalité principale.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient **pas** de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la logique est gérée dans le fichier principal du module (`fbchat.php`) et injectée via des hooks.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit **pas** de classes personnalisées ou d'instances `ObjectModel` dans le répertoire `classes/`. Toute la gestion des données est effectuée directement via la classe `Configuration` pour les paramètres.

### 4.4 Actifs JavaScript (`views/js/`)

- **`fbchat/jscolor/jscolor.js`**

  - **Portée :** Back-office (page de configuration de l'administration).
  - **Objectif :** Il s'agit d'une bibliothèque JavaScript tierce pour un sélecteur de couleurs. Elle est utilisée sur la page de configuration du module pour fournir une interface conviviale pour la sélection des couleurs du widget de chat (par exemple, couleur de la police, couleur de fond).
  - **Interaction :** Elle attache la fonctionnalité de sélecteur de couleurs à des champs de saisie spécifiques du formulaire d'administration.
- **`fbchat/js/fbchat.js`**

  - **Portée :** Front-office.
  - **Objectif :** Ce JavaScript personnalisé gère le chargement dynamique et l'initialisation du widget de chat Facebook Messenger. Il contient la logique pour charger conditionnellement le SDK Facebook et le chat Messenger en fonction des paramètres du module et potentiellement des drapeaux d'optimisation des performances.
  - **Interaction :**
    - Vérifie la configuration `fbchat_hack` pour déterminer si le chargement différé pour Google Insights est activé.
    - Crée et ajoute dynamiquement le script du SDK Facebook (`sdk.js`) au `<body>` si `fbchat_appsdk` est activé.
    - Initialise le plugin `FB.CustomerChat` avec les paramètres récupérés de la configuration du module (par exemple, `page_id`, `app_id`, `theme_color`, `logged_in_greeting`, `logged_out_greeting`, `locale`).
    - Gère le positionnement du widget de chat en fonction de `fbchat_side`.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`fbchat/css.css`**

  - **Portée :** Back-office (page de configuration de l'administration).
  - **Objectif :** Contient le style spécifique au formulaire de configuration du module dans le Back Office de PrestaShop. Cela peut inclure des styles pour les champs de saisie, les boutons ou les éléments de mise en page personnalisés dans la sortie de `getContent()`.
  - **Sélecteurs clés :** Cible probablement les éléments du formulaire de configuration du module.
- **`fbchat/css/fbchat_left.css`**

  - **Portée :** Front-office.
  - **Objectif :** Fournit des ajustements de style pour le widget de chat Facebook Messenger lorsque sa position est définie sur le côté « Gauche » de l'écran. Cela peut inclure des propriétés CSS `right` ou `left` pour contrôler sa position fixe.
  - **Sélecteurs clés :** Cible le conteneur de chat principal ou son enveloppe pour assurer un alignement correct à gauche.
- **`fbchat/css/fbchat_right.css`**

  - **Portée :** Front-office.
  - **Objectif :** Fournit des ajustements de style pour le widget de chat Facebook Messenger lorsque sa position est définie sur le côté « Droit » de l'écran. Cela peut inclure des propriétés CSS `right` ou `left` pour contrôler sa position fixe.
  - **Sélecteurs clés :** Cible le conteneur de chat principal ou son enveloppe pour assurer un alignement correct à droite.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **`fbchat/admin-script.tpl`**

  - **Portée :** Back-office (page de configuration de l'administration).
  - **Objectif :** Ce modèle est probablement utilisé pour injecter du code JavaScript (par exemple, pour l'initialisation du sélecteur de couleurs à partir de `jscolor.js`) ou un style spécifique dans la page de configuration du module. Il est rendu dans la méthode `getContent()`.
  - **Variables :** Peut recevoir des variables de configuration pour définir dynamiquement les valeurs initiales du sélecteur de couleurs.
- **`fbchat/fbchat.tpl`**

  - **Portée :** Front-office.
  - **Objectif :** C'est le modèle principal du front-office responsable du rendu de la structure HTML et de l'initialisation JavaScript nécessaires pour le widget de chat Facebook Messenger. Il est généralement accroché à `displayFooter` ou `displayHeader`.
  - **Variables :** Reçoit toutes les variables de configuration nécessaires des méthodes `hookDisplayFooter` ou `hookDisplayHeader` du module, telles que `fbchat_fanid`, `fbchat_appid`, `fbchat_theme`, `fbchat_bg`, `fbchat_color`, `fbchat_langarray`, `fbchat_hello_logged`, `fbchat_hello_unlogged`, `fbchat_hack`, `fbchat_appsdk`, `fbchat_type`, `fbchat_side`.
  - **Sortie :** Génère l'élément `<div class="fb-customerchat">` et la balise `<script>` pour l'initialisation du SDK Facebook.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Ce module ne crée aucune table SQL personnalisée.
  - Tous les paramètres de configuration sont stockés dans la table `ps_configuration` en utilisant des clés comme `mypresta_updates`, `fbchat_theme`, `fbchat_bg`, `fbchat_color`, `fbchat_fanpage`, `fbchat_positions`, `fbchat_hack`, `fbchat_appsdk`, `fbchat_type`, `fbchat_fanid`, `fbchat_appid`, `fbchat_title`, `fbchat_langarray`, `fbchat_hello_logged`, `fbchat_hello_unlogged`, `fbchat_side`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Exécuté dans la section `<head>` de chaque page du front-office. | Utilisé pour inclure les fichiers CSS (`fbchat_left.css`, `fbchat_right.css`) et potentiellement du JavaScript initial si nécessaire tôt dans le chargement de la page. |
| `displayFooter` | Exécuté juste avant la balise `</body>` fermante de chaque page du front-office. | C'est le hook principal pour le rendu du modèle `fbchat.tpl`, qui inclut le HTML du chat Facebook Messenger et initialise le script `fbchat.js`. Le placer ici garantit que le contenu principal de la page se charge en premier, améliorant la performance perçue. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et les dernières versions du module « Chat Facebook Messenger », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité ou l'intégration du module.
