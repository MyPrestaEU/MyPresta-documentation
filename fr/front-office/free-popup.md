---
title: "Free PopUp - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Free PopUp par MyPresta.eu."
sidebar:
  label: "Free PopUp - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Free PopUp sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-popup.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/free-popup/)
>
> ---


# Free PopUp

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal et unique du module Free PopUp. Vous y trouverez tous les paramètres pour contrôler le contenu et le comportement de votre fenêtre contextuelle.

#### **1. Activer / Désactiver la fenêtre contextuelle**

-   **Ce que fait ce paramètre :** C'est l'interrupteur principal de votre fenêtre contextuelle.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (OUI) :* La fenêtre contextuelle apparaîtra sur votre front office selon vos autres paramètres.
    -   *Lorsqu'il est désactivé (NON) :* La fenêtre contextuelle n'apparaîtra pas sur votre front office, quels que soient les autres paramètres.
-   **Valeur recommandée :** OUI (lorsque vous voulez que la fenêtre contextuelle soit active), NON (lorsque vous voulez la masquer temporairement).
-   **Scénario / exemple pour le marchand :** Activez-le lorsque vous avez une nouvelle promotion en cours. Désactivez-le pendant la maintenance ou si vous souhaitez lancer une campagne différente temporairement.

#### **2. Contenu de la fenêtre contextuelle**

-   **Ce que fait ce paramètre :** C'est ici que vous saisissez le message, l'offre ou l'information que vous souhaitez afficher dans la fenêtre contextuelle. Il utilise un éditeur de texte enrichi (TinyMCE), vous permettant de formater le texte, d'ajouter des images, des liens, et plus encore.
-   **Effet de la modification de ce paramètre :** Tout ce que vous tapez et formatez ici sera affiché directement à vos clients dans la fenêtre contextuelle.
-   **Valeur recommandée :** Votre message promotionnel spécifique, texte de bienvenue ou annonce importante.
-   **Scénario / exemple pour le marchand :** "Bienvenue dans notre boutique ! Utilisez le code BIENVENUE10 pour 10 % de réduction sur votre première commande !" ou "Livraison gratuite sur toutes les commandes de plus de 50 € cette semaine !". Vous pouvez également ajouter une image d'un nouveau produit ou un logo de marque.

#### **3. Expiration du cookie (jours)**

-   **Ce que fait ce paramètre :** Il détermine combien de temps la fenêtre contextuelle reste masquée après qu'un client l'a fermée. Il définit un cookie dans le navigateur du client.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est défini sur 0 :* La fenêtre contextuelle apparaîtra à *chaque* chargement de page, même si le client vient de la fermer. Ce n'est généralement pas recommandé car cela peut être ennuyeux.
    -   *Lorsqu'il est défini sur un nombre positif (par exemple, 7) :* La fenêtre contextuelle apparaîtra lors de la première visite. Une fois fermée, elle ne réapparaîtra pas pendant les 7 jours suivants pour ce client spécifique sur ce navigateur spécifique.
-   **Valeur recommandée :** 7 (pour les promotions hebdomadaires), 30 (pour les messages de bienvenue mensuels), ou 1 (si vous voulez qu'elle réapparaisse quotidiennement).
-   **Scénario / exemple pour le marchand :** Si vous avez un message de bienvenue général, le définir à 30 jours est une bonne chose. Si vous organisez une vente hebdomadaire, 7 jours garantissent que les clients voient la nouvelle offre la semaine prochaine.

#### **4. Mode Test**

-   **Ce que fait ce paramètre :** Il vous permet de tester l'apparence et le contenu de votre fenêtre contextuelle sans attendre l'expiration du cookie.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (OUI) :* La fenêtre contextuelle apparaîtra à chaque rafraîchissement de page, même si vous venez de la fermer. Cela annule le paramètre "Expiration du cookie" à des fins de test.
    -   *Lorsqu'il est désactivé (NON) :* La fenêtre contextuelle se comportera normalement, en respectant le paramètre "Expiration du cookie".
-   **Valeur recommandée :** OUI (pendant que vous configurez et ajustez la fenêtre contextuelle), NON (une fois que vous êtes satisfait de la configuration et que vous voulez qu'elle fonctionne normalement pour les clients).
-   **Scénario / exemple pour le marchand :** Vous venez de mettre à jour le contenu de votre fenêtre contextuelle et vous voulez voir immédiatement à quoi il ressemble sur le front office. Activez le mode Test, rafraîchissez la page de votre boutique, et la fenêtre contextuelle apparaîtra. Une fois que vous êtes satisfait, désactivez le mode Test.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Activer / Désactiver la fenêtre contextuelle | OUI | Interrupteur principal pour afficher ou masquer la fenêtre contextuelle sur votre boutique. |
| Page de configuration du module | Contenu de la fenêtre contextuelle | Votre message | Le texte, les images et les liens réels affichés dans la fenêtre contextuelle. |
| Page de configuration du module | Expiration du cookie (jours) | 7 | Nombre de jours pendant lesquels la fenêtre contextuelle reste masquée après qu'un client l'a fermée. |
| Page de configuration du module | Mode Test | NON | Force l'affichage de la fenêtre contextuelle à chaque rafraîchissement à des fins de test. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Ma fenêtre contextuelle n'apparaît pas sur le front office, même après l'avoir activée.**

-   **R :** Tout d'abord, vérifiez si "Activer / Désactiver la fenêtre contextuelle" est réglé sur OUI. Si c'est le cas, essayez d'activer le "Mode Test" pour voir si elle apparaît. Si elle n'apparaît toujours pas, videz le cache de votre navigateur et le cache Smarty de PrestaShop (Allez dans **Paramètres avancés > Performances**, puis cliquez sur "Vider le cache" en haut à droite). Assurez-vous également d'avoir enregistré votre configuration après avoir effectué des modifications.

**Q2 : La fenêtre contextuelle est apparue une fois, mais maintenant elle ne s'affiche plus.**

-   **R :** C'est un comportement normal dû au paramètre "Expiration du cookie". Le module définit un cookie dans votre navigateur pour empêcher la fenêtre contextuelle de réapparaître pendant le nombre de jours spécifié. Pour la forcer à s'afficher à des fins de test, activez le "Mode Test" dans la configuration du module. Pour la voir comme un nouveau visiteur, effacez les cookies de votre navigateur pour le domaine de votre boutique ou utilisez une fenêtre de navigation privée/incognito.

**Q3 : Comment puis-je modifier l'apparence de la fenêtre contextuelle (changer les couleurs, les polices, etc.) ?**

-   **R :** Le module fournit une modale blanche de base avec une superposition à 70 %. Pour un style avancé, vous auriez besoin de CSS personnalisé. Cela est généralement géré par un développeur web. Vous pouvez ajouter du CSS personnalisé au fichier `custom.css` de votre thème ou modifier directement le fichier `front.css` du module (bien que ce dernier ne soit pas recommandé car les mises à jour l'écraseraient).

**Q4 : Puis-je avoir différentes fenêtres contextuelles pour différentes pages ou groupes de clients ?**

-   **R :** Le module Free PopUp est conçu pour une seule campagne à l'échelle de la boutique. Il affiche le même contenu à tous les visiteurs. Pour des fenêtres contextuelles plus avancées et ciblées, vous auriez besoin d'un module de fenêtre contextuelle plus riche en fonctionnalités (et probablement payant).

**Q5 : Mes images ou liens dans le contenu de la fenêtre contextuelle ne fonctionnent pas correctement.**

-   **R :** Assurez-vous d'utiliser des URL complètes et absolues pour les images et les liens (par exemple, `https://votreboutique.com/img/votreimage.jpg` au lieu de `/img/votreimage.jpg`). L'éditeur TinyMCE devrait gérer cela automatiquement, mais des problèmes peuvent parfois survenir si vous copiez-collez du contenu provenant de sources externes. Vérifiez le code source HTML si vous êtes à l'aise avec cela.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module Free PopUp est un module PrestaShop simple suivant un modèle MVC de base. Il utilise principalement la classe `Module` pour ses fonctionnalités principales, la gestion de la configuration et l'enregistrement des hooks. L'affichage du front-office est géré par un seul template rendu via un hook, et son comportement est contrôlé par un simple fichier JavaScript. Le style est géré par des fichiers CSS dédiés pour l'administration et le front-office.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs front-office ou back-office personnalisés. Toute la configuration est gérée dans la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée ni aucune instance d'`ObjectModel`. Toutes les données de configuration sont stockées directement dans la table `ps_configuration` de PrestaShop à l'aide des méthodes standard `Configuration::get()` et `Configuration::updateValue()`.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`myfreepopup/js/front.js`**
    -   **Portée :** Front-office.
    -   **Responsabilité :** Ce script est responsable du comportement côté client de la fenêtre contextuelle.
    -   **Détails :**
        -   Il vérifie la présence d'un cookie spécifique (`myfreepopup_closed`).
        -   Si le cookie n'est pas trouvé (ce qui signifie que l'utilisateur n'a pas fermé la fenêtre contextuelle récemment ou que c'est sa première visite), il affiche la fenêtre contextuelle en manipulant les propriétés CSS (par exemple, `display: block`).
        -   Il attache un écouteur d'événements au bouton de fermeture dans la fenêtre contextuelle.
        -   Lorsque le bouton de fermeture est cliqué, il masque la fenêtre contextuelle et définit le cookie `myfreepopup_closed` avec une expiration basée sur la configuration du module.
        -   Il gère également la logique du "Mode Test", garantissant que la vérification du cookie est ignorée lorsque le mode test est actif.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`myfreepopup/css/admin.css`**
    -   **Portée :** Style du formulaire d'administration du back-office.
    -   **Détails :** Contient des règles de style de base pour la page de configuration du module dans le back office de PrestaShop, assurant une apparence cohérente dans le panneau d'administration.
-   **`myfreepopup/css/front.css`**
    -   **Portée :** Style client du front-office.
    -   **Détails :** Définit l'apparence visuelle de la fenêtre contextuelle elle-même. Cela inclut :
        -   Le style de la superposition modale (par exemple, `position: fixed`, `background-color`, `opacity`, `z-index`).
        -   Le style de la boîte de contenu principale de la fenêtre contextuelle (par exemple, `background-color: #fff`, `border`, `box-shadow`, `max-width`, `padding`, `text-align`, `position: fixed`, `top`, `left`, `transform` pour le centrage).
        -   Le style du bouton de fermeture (par exemple, `position: absolute`, `font-size`, `cursor: pointer`).
        -   Des ajustements réactifs pour différentes tailles d'écran à l'aide de requêtes média.
    -   **Sélecteurs de classe CSS clés pour la surcharge :** `.myfreepopup_overlay`, `.myfreepopup_content`, `.myfreepopup_close`.

### 4.6 Structure du template Smarty (`views/templates/`)

-   **`myfreepopup/views/admin_banner.tpl`**
    -   **Portée :** Template d'administration.
    -   **Objectif :** Affiche une bannière promotionnelle ou un message d'information dans la page de configuration du module dans le back office.
-   **`myfreepopup/views/admin_locks.tpl`**
    -   **Portée :** Template d'administration.
    -   **Objectif :** Probablement utilisé pour afficher des informations relatives à la licence du module ou à des fonctionnalités supplémentaires, souvent avec une icône de cadenas.
-   **`myfreepopup/views/front.tpl`**
    -   **Portée :** Template de hook du front-office.
    -   **Objectif :** C'est le template principal responsable du rendu de la structure HTML de la fenêtre contextuelle sur le front office.
    -   **Rendu dans le hook :** `displayHeader` (ou un hook global similaire où JS/CSS peut être chargé).
    -   **Contenu :** Contient le HTML pour la superposition, la boîte de contenu de la fenêtre contextuelle, le bouton de fermeture, et insère dynamiquement la variable `{$popup_content}` (qui provient de l'éditeur TinyMCE dans le back office). Il inclut également les fichiers JavaScript et CSS nécessaires.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :

    -   Ce module ne crée pas de tables SQL personnalisées.
    -   Il stocke ses paramètres de configuration dans la table standard `ps_configuration` en utilisant des clés telles que `MYFREEPOPUP_ENABLED`, `MYFREEPOPUP_CONTENT`, `MYFREEPOPUP_COOKIE_DAYS`, `MYFREEPOPUP_TEST_MODE`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Exécuté dans la section `<head>` de chaque page du front-office. | Utilisé pour inclure les fichiers CSS et JavaScript du module, et pour rendre la structure HTML initiale de la fenêtre contextuelle (`front.tpl`) qui est ensuite contrôlée par JavaScript. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant le module Free PopUp.
