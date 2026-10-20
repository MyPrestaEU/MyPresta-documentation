---
title: "Limiter la quantité de produits dans le panier pour les utilisateurs non connectés - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Limiter la quantité de produits dans le panier pour les utilisateurs non connectés par MyPresta.eu."
sidebar:
  label: "Limiter la quantité de produits dans le panier pour les utilisateurs non connectés - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Limit quantity of products in cart for unlogged users sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/limit-quantity-of-products-in-cart-for-unlogged-users.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/limit-quantity-of-products-in-cart-for-unlogged-users/)
>
> ---


# Limiter la quantité de produits dans le panier pour les utilisateurs non connectés

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal et unique du module. Vous le trouverez en naviguant vers **Modules > Gestionnaire de modules**, en recherchant « Limiter la quantité de produits dans le panier pour les utilisateurs non connectés », et en cliquant sur « Configurer ».

#### **Quantité maximale de produits dans le panier pour les utilisateurs non connectés**

- **Ce que fait ce paramètre :** C'est le paramètre principal du module. Il définit la quantité totale maximale absolue d'articles qu'un client non connecté peut avoir dans son panier.
- **Effet de la modification de ce paramètre :**
  - *Si défini sur 0 :* Le module sera effectivement désactivé, et les utilisateurs non connectés pourront ajouter une quantité illimitée de produits à leur panier, tout comme les utilisateurs connectés.
  - *Si défini sur un nombre supérieur à 0 (par exemple, 5) :* Un client non connecté pourra ajouter des articles à son panier jusqu'à ce que la quantité totale de tous les articles atteigne ce nombre. S'il essaie d'ajouter un autre article qui dépasserait cette limite, le module empêchera l'ajout et affichera la fenêtre contextuelle d'avertissement.
- **Valeur recommandée :** Cela dépend entièrement de votre stratégie commerciale.
  - *Pour les boutiques B2C souhaitant encourager doucement la connexion :* Une valeur comme `3` ou `5` peut être efficace.
  - *Pour les boutiques B2B ou les boutiques avec des articles de grande valeur :* Une valeur inférieure comme `1` ou `2` pourrait être appropriée pour s'assurer que seuls les acheteurs sérieux et connectés peuvent réserver du stock.
  - *Si vous ne voulez aucune limite :* Définissez sur `0`.
- **Scénario/exemple pour le marchand :** Vous vendez des t-shirts personnalisés. Vous voulez que les navigateurs occasionnels voient quelques designs dans leur panier, mais pour qu'ils s'engagent sur une commande plus importante, vous préférez qu'ils se connectent. Vous définissez cela sur `3`. Un client non connecté ajoute un t-shirt (quantité 1), puis un autre (quantité 1), puis un troisième (quantité 1). Son panier contient maintenant 3 articles. S'il essaie d'ajouter un quatrième t-shirt, il verra le message contextuel, l'invitant à se connecter.

#### **Message pour les utilisateurs non connectés**

- **Ce que fait ce paramètre :** Cela vous permet de personnaliser le texte du message contextuel qui apparaît lorsqu'un utilisateur non connecté tente de dépasser la limite de quantité de panier définie.
- **Effet de la modification de ce paramètre :**
  - *Si vous le laissez par défaut :* Le message standard « En tant que client non connecté, vous ne pouvez pas ajouter plus de produits au panier. Veuillez vous connecter pour continuer le processus d'ajout au panier. » sera affiché.
  - *Si vous le personnalisez :* Votre message personnalisé sera affiché à la place. Cela vous permet d'adapter le ton, d'ajouter des instructions spécifiques, ou même d'inclure un lien (bien que les liens directs dans les fenêtres contextuelles puissent être délicats sans personnalisation supplémentaire).
- **Valeur recommandée :** Le message par défaut est clair et efficace. Ne le modifiez que si vous avez une voix de marque spécifique ou des instructions supplémentaires que vous souhaitez transmettre. Gardez-le concis.
- **Scénario/exemple pour le marchand :** Vous voulez un ton légèrement plus doux. Vous modifiez le message en : « Pour ajouter plus d'articles à votre panier, veuillez vous connecter ou créer un compte. Nous serions ravis de vous voir rejoindre notre communauté ! »

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | **Quantité maximale de produits dans le panier pour les utilisateurs non connectés** | `0` (désactivé) / `3-5` (recommandé pour le B2C) | Définit le nombre total d'articles qu'un client non connecté peut ajouter à son panier. Empêche les ajouts supplémentaires et affiche une fenêtre contextuelle si la limite est dépassée. |
| Configuration du module | **Message pour les utilisateurs non connectés** | « En tant que client non connecté, vous ne pouvez pas ajouter plus de produits au panier. Veuillez vous connecter pour continuer le processus d'ajout au panier. » | Personnalise le texte affiché dans la fenêtre contextuelle lorsqu'un utilisateur non connecté atteint la limite du panier. |

## 3. Dépannage pour le marchand et Foire aux questions (FAQ)

**Q : J'ai défini une limite, mais les utilisateurs non connectés peuvent toujours ajouter des produits illimités. Qu'est-ce qui ne va pas ?**
R :

1.  **Vérifiez le paramètre « Quantité maximale » :** Assurez-vous qu'il est défini sur un nombre supérieur à `0`. S'il est `0`, le module est désactivé.
2.  **Videz le cache de votre navigateur :** Votre navigateur pourrait vous montrer une ancienne version de la page. Essayez de vider le cache et les cookies de votre navigateur, ou testez dans une fenêtre de navigation privée/incognito.
3.  **Videz le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » en haut à droite.
4.  **Assurez-vous que vous êtes réellement déconnecté :** Vérifiez que vous n'êtes pas connecté à un compte client dans votre navigateur. Le moyen le plus simple de tester est d'ouvrir une nouvelle fenêtre de navigation privée/incognito.

**Q : Le message contextuel ne s'affiche pas ou semble étrange.**
R :

1.  **Vérifiez le paramètre « Message pour les utilisateurs non connectés » du module :** Assurez-vous qu'il n'est pas vide si vous attendez un message personnalisé.
2.  **Compatibilité du thème :** Bien que le module soit conçu pour être compatible, des thèmes très fortement personnalisés peuvent parfois interférer avec JavaScript ou CSS. Si la fenêtre contextuelle n'apparaît pas du tout, vérifiez la console de développement de votre navigateur pour les erreurs JavaScript (touche F12, puis onglet Console). Si elle semble étrange, il pourrait s'agir d'un conflit CSS. Contactez le support MyPresta.eu avec les détails de votre thème.

**Q : Ce module affecte-t-il les clients connectés ?**
R : Non, ce module cible spécifiquement les utilisateurs *non connectés*. Une fois qu'un client se connecte à son compte, la limite de quantité imposée par ce module ne s'applique plus à lui.

**Q : Puis-je définir des limites différentes pour différentes catégories de produits ?**
R : Non, ce module applique une seule limite de quantité globale pour tous les produits du panier pour les utilisateurs non connectés. Il ne prend pas en charge les limites spécifiques à une catégorie ou à un produit.

**Q : Que se passe-t-il si un utilisateur non connecté ajoute 3 articles, puis se connecte, puis essaie d'en ajouter d'autres ?**
R : Une fois que l'utilisateur se connecte, il n'est plus considéré comme « non connecté ». La restriction du module est levée, et il peut continuer à ajouter des produits à son panier sans aucune limite de quantité de la part de ce module.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Limiter la quantité de produits dans le panier pour les utilisateurs non connectés » (`lqfu`) est un module PrestaShop léger principalement implémenté via une classe de module principale (`lqfu/index.php`) et un fichier JavaScript personnalisé (`lqfu/views/js/lqfu.js`). Il utilise le système de hooks de PrestaShop pour injecter son JavaScript dans le front office et utilise AJAX pour communiquer avec la logique côté serveur afin de vérifier et d'appliquer la limite de quantité du panier pour les utilisateurs invités. Le module stocke sa configuration dans `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. La logique front-office du module est gérée directement via le fichier du module principal `hookDisplayHeader` et les requêtes AJAX, qui sont traitées par le `CartController` ou `ProductController` de PrestaShop et interceptées par la logique du module.
- **Contrôleurs d'administration Back-Office** : Aucun. Toute la configuration est gérée dans la méthode `getContent()` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)

- Aucune classe personnalisée étendant `ObjectModel` n'est définie dans ce module. Toute la logique réside dans la classe `Lqfu` principale dans `index.php`.

### 4.4 Actifs JavaScript (`views/js/`)

- **`lqfu/views/js/lqfu.js`**
  - **Portée :** Front-office.
  - **Objectif :** Ce script est responsable de l'interception des actions « Ajouter au panier », de la vérification de la quantité actuelle du panier pour les utilisateurs non connectés et de l'affichage du message contextuel personnalisé si la limite est dépassée.
  - **Fonctionnalité clé :**
    - Lie des écouteurs d'événements aux boutons « Ajouter au panier » (ou formulaires) dans toute la boutique (par exemple, page produit, listes de catégories).
    - Lors d'une tentative d'« Ajouter au panier », il vérifie d'abord si l'utilisateur est connecté.
    - Si l'utilisateur n'est pas connecté, il récupère la quantité actuelle du panier (soit à partir d'un élément caché, soit en effectuant un appel AJAX si nécessaire).
    - Compare la quantité actuelle du panier + la quantité ajoutée par rapport à la limite maximale configurée.
    - Si la limite est dépassée, il empêche l'action par défaut « Ajouter au panier », affiche une modale/fenêtre contextuelle personnalisée avec le message configuré, et désactive potentiellement le bouton « Ajouter au panier » temporairement.
    - Le script utilise probablement jQuery pour la manipulation du DOM et la gestion des événements, ce qui est courant dans le front-office de PrestaShop.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`lqfu/views/css/lqfu.css`**
  - **Portée :** Style client du front-office.
  - **Objectif :** Fournit un style de base pour le message contextuel qui apparaît lorsqu'un utilisateur non connecté dépasse la limite de quantité du panier.
  - **Sélecteurs de classe CSS clés :** Les développeurs peuvent s'attendre à des classes liées au conteneur de la fenêtre contextuelle, au texte du message et éventuellement aux boutons de fermeture. Ceux-ci peuvent être remplacés dans le fichier `custom.css` ou `theme.css` d'un thème personnalisé pour correspondre à l'image de marque de la boutique.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **Modèles de hook (`views/templates/hook/`)** : Aucun explicitement listé, mais le module pourrait implicitement rendre du contenu via `displayHeader` ou des hooks similaires s'il doit injecter des données cachées ou des variables JS initiales.
- **Modèles d'administration (`views/templates/admin/`)** :
  - **`lqfu/views/templates/admin/json.tpl`** : Ce modèle est probablement utilisé pour rendre des données JSON de manière structurée dans le Back Office, éventuellement pour le débogage ou des réponses AJAX spécifiques de la page de configuration du module, bien que son utilisation directe pour la configuration principale soit moins courante. Il pourrait s'agir d'un vestige ou être utilisé pour une fonction interne spécifique du module.
- **Modèles Front-office (`views/templates/front/`)** : Aucun. La fenêtre contextuelle est probablement générée dynamiquement via JavaScript.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :
  - Le module ne crée aucune table SQL personnalisée.
  - Les paramètres de configuration sont stockés dans la table `ps_configuration` :
    - `PS_LQFU_MAX_QUANTITY` : Stocke la valeur entière de la quantité maximale de produits pour les utilisateurs non connectés.
    - `PS_LQFU_MESSAGE` : Stocke la valeur de la chaîne de caractères pour le message personnalisé affiché dans la fenêtre contextuelle.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Injecte les fichiers CSS (`lqfu.css`) et JavaScript (`lqfu.js`) du module dans le front-office. Peut également transmettre des variables de configuration (comme la quantité maximale et le message) au JavaScript. |
| `actionCartSave` | Après l'enregistrement d'un panier (par exemple, produit ajouté/supprimé). | Le module intercepte probablement ce hook (ou un hook similaire comme `actionObjectCartAddAfter`) pour réévaluer la quantité du panier et potentiellement empêcher l'ajout d'articles si la limite est dépassée pour un utilisateur non connecté. C'est là que la validation côté serveur se produirait avant que la fenêtre contextuelle JS ne soit déclenchée. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et toute assistance supplémentaire concernant le module « Limiter la quantité de produits dans le panier pour les utilisateurs non connectés », veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez rencontrer.
