---
title: "Désactiver les bons de réduction pour les articles en promotion - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Désactiver les bons de réduction pour les articles en promotion' par MyPresta.eu."
sidebar:
  label: "Désactiver les bons de réduction pour les articles en promotion - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Disable vouchers for items on sale sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/disable-vouchers-for-items-on-sale.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/disable-vouchers-for-items-on-sale/)
>
> ---


# Désactiver les bons de réduction pour les articles en promotion

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises, qui sont généralement disponibles sur tout environnement d'hébergement PrestaShop moderne.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal et unique pour le module « Désactiver les bons de réduction pour les articles en promotion ». Vous pouvez y accéder en naviguant vers **Modules > Gestionnaire de modules**, en recherchant « Désactiver les bons de réduction pour les articles en promotion », puis en cliquant sur le bouton « Configurer ».

#### **Paramètres généraux**

-   **Désactiver les bons de réduction pour les articles en promotion :**

    -   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité principale du module.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé (OUI) :* Si le panier d'un client contient *tout* produit actuellement en promotion (ayant un prix spécial), il sera empêché d'appliquer *tout* code de bon de réduction.
        -   *Lorsqu'il est désactivé (NON) :* Le module sera inactif. Les clients pourront appliquer des codes de bon de réduction même si leur panier contient des articles en promotion, permettant le « double-cumul de réductions ».
    -   **Valeur recommandée :** **OUI** si vous souhaitez empêcher le double-cumul de réductions et protéger vos marges.
    -   **Scénario / exemple de marchand :** Vous organisez une « Vente d'été » avec 20 % de réduction sur certains articles. Vous avez également un bon de réduction « Bienvenue10 » pour les nouveaux clients. Si ce paramètre est **OUI**, un nouveau client ne pourra pas utiliser « Bienvenue10 » si son panier inclut des articles de la Vente d'été.
-   **Désactiver le module pour les codes qui commencent par :**

    -   **Ce que fait ce paramètre :** Cela vous permet de créer une exception. Si un code de bon de réduction commence par une chaîne spécifique que vous définissez ici, la restriction du module ne s'appliquera *pas* à ce bon de réduction, même s'il y a des articles en promotion dans le panier.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'une chaîne est saisie (par exemple, « LIVRAISONGRATUITE ») :* Tout code de bon de réduction commençant par « LIVRAISONGRATUITE » (par exemple, « LIVRAISONGRATUITE2023 », « LIVRAISONGRATUITENOW ») contournera la restriction du module. Les clients peuvent utiliser ces bons de réduction spécifiques même avec des articles en promotion dans leur panier.
        -   *Lorsqu'il est laissé vide :* Aucune exception n'est faite en fonction des préfixes de code de bon de réduction. Tous les bons de réduction sont soumis à la règle « Désactiver les bons de réduction pour les articles en promotion ».
    -   **Valeur recommandée :** Laissez vide, sauf si vous avez des bons de réduction spécifiques que vous souhaitez *toujours* autoriser, quels que soient les articles en promotion.
    -   **Scénario / exemple de marchand :** Vous avez un bon de réduction spécial « LIVRAISONGRATUITE » qui offre la livraison gratuite. Vous décidez que la livraison gratuite doit toujours être autorisée, même sur les articles en promotion, pour encourager les commandes plus importantes. Vous saisiriez « LIVRAISONGRATUITE » dans ce champ.
-   **Message pour le client :**

    -   **Ce que fait ce paramètre :** C'est le message personnalisé que les clients verront dans leur panier lorsqu'ils essaieront d'appliquer un code de bon de réduction mais seront bloqués en raison d'articles en promotion.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'un message est saisi (par exemple, « Les bons de réduction ne peuvent pas être utilisés avec les articles en promotion. ») :* Ce message exact sera affiché au client.
        -   *Lorsqu'il est laissé vide :* Le module affichera probablement un message d'erreur par défaut ou générique, ce qui pourrait être moins clair pour le client.
    -   **Valeur recommandée :** Un message clair, poli et informatif.
    -   **Scénario / exemple de marchand :** Vous souhaitez informer clairement les clients : « Ce bon de réduction ne peut pas être appliqué car votre panier contient des articles déjà en promotion. Veuillez retirer les articles en promotion ou utiliser un autre bon de réduction. »

#### **Tableau de référence rapide de la configuration**

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Désactiver les bons de réduction pour les articles en promotion | OUI | Active/désactive la fonctionnalité principale pour bloquer les bons de réduction sur les articles en promotion. |
| Configuration du module | Désactiver le module pour les codes qui commencent par : | Laisser vide | Permet à des codes de bon de réduction spécifiques (par préfixe) de contourner les restrictions du module. |
| Configuration du module | Message pour le client | « Les bons de réduction ne peuvent pas être utilisés avec les articles en promotion. » (ou similaire) | Personnalise le message d'erreur affiché aux clients lorsqu'un bon de réduction est bloqué. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : J'ai activé le module, mais les clients peuvent toujours utiliser des bons de réduction sur les articles en promotion. Qu'est-ce qui ne va pas ?**
R :

1.  **Vérifiez le paramètre « Désactiver les bons de réduction pour les articles en promotion » :** Assurez-vous qu'il est réglé sur **OUI** dans la configuration du module.
2.  **Videz le cache :** Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures). Les modifications de module nécessitent parfois un rafraîchissement du cache.
3.  **Vérifiez le statut de la promotion :** Vérifiez à nouveau que les produits avec lesquels vous testez sont réellement marqués comme « en promotion » dans PrestaShop (par exemple, ils ont un prix spécifique défini qui les rend moins chers que leur prix normal).
4.  **Vérifiez l'exception de préfixe de code de bon de réduction :** Si vous avez saisi une chaîne dans « Désactiver le module pour les codes qui commencent par : », assurez-vous que le bon de réduction que vous testez ne commence pas par cette chaîne.

**Q : Le module bloque les bons de réduction, mais le message ne s'affiche pas, ou il affiche une erreur générique.**
R :

1.  **Personnalisez le message :** Allez dans la configuration du module et assurez-vous d'avoir saisi un message personnalisé dans le champ « Message pour le client ».
2.  **Compatibilité du thème :** Bien que le module essaie de s'intégrer de manière transparente, certains thèmes très personnalisés peuvent remplacer les mécanismes d'affichage d'erreur par défaut de PrestaShop. Si le message n'apparaît pas, il peut s'agir d'un problème de thème front-office. Contactez le développeur de votre thème ou un webmaster pour obtenir de l'aide.

**Q : Puis-je désactiver ce module pour des groupes de clients spécifiques ou des produits individuels ?**
R : Non, ce module fonctionne globalement en fonction de la présence de *tout* article en promotion dans le panier. Il n'offre pas de contrôle granulaire pour des groupes de clients spécifiques ou des exclusions de produits au-delà de l'exception de préfixe de code de bon de réduction. Si vous avez besoin d'une logique plus avancée, un développement personnalisé pourrait être nécessaire.

**Q : Ce module affectera-t-il mon référencement ou mes listes de produits ?**
R : Non, ce module fonctionne uniquement sur la logique d'application des bons de réduction dans le panier. Il ne modifie pas les prix des produits, les descriptions, les URL ou tout autre élément du front-office qui aurait un impact sur le référencement.

**Q : J'ai mis à jour ma version de PrestaShop, et maintenant le module ne fonctionne plus.**
R :

1.  **Vérifiez la compatibilité du module :** Assurez-vous d'avoir téléchargé et installé la version du module spécifiquement conçue pour votre version de PrestaShop depuis votre compte MyPresta.eu.
2.  **Réinstaller/Reconfigurer :** Parfois, après une mise à jour majeure de PrestaShop, les modules peuvent avoir besoin d'être réinstallés ou reconfigurés. Essayez de désinstaller puis de réinstaller le module (n'oubliez pas de sauvegarder vos paramètres si possible, bien que ce module ait des données minimales).
3.  **Videz le cache :** Videz toujours votre cache PrestaShop après toute mise à jour ou modification de module.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Désactiver les bons de réduction pour les articles en promotion » (`dvfis`) fonctionne principalement en surchargeant le `CartController` principal pour intercepter le processus d'application des bons de réduction. Il utilise le mécanisme de surcharge de PrestaShop pour injecter sa logique avant qu'un bon de réduction ne soit validé et appliqué. La configuration du module est stockée dans `ps_configuration` et accessible via la classe principale du module.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    -   `dvfis/override/controllers/front/CartController.php`
        -   **Nom de la classe et classe parente** : `CartController` (surcharge la classe `CartController` principale)
        -   **Responsabilité** : C'est le fichier le plus critique. Il étend le `CartController` principal pour modifier la méthode `postProcess()`. Plus précisément, il intercepte la logique lorsqu'un client tente d'ajouter un bon de réduction (`addDiscount()`). Il vérifie si le module est activé et si le panier contient des produits avec un prix spécial. Si les deux conditions sont remplies (et que le code du bon de réduction ne correspond pas à un préfixe d'exclusion), il empêche l'ajout du bon de réduction et affiche un message d'erreur personnalisé.
    -   `dvfis/override/controllers/front/index.php`
        -   **Nom de la classe et classe parente** : Pas un fichier de classe, généralement un fichier vide ou un fichier avec un `<?php exit;` de base pour empêcher la liste directe des répertoires. C'est une pratique standard pour les répertoires de surcharge de PrestaShop.
-   **Contrôleurs d'administration Back-Office** : Aucun. Le module utilise la méthode `getContent()` standard dans son fichier de module principal pour la configuration.

### 4.3 Classes et modèles principaux (`classes/`)

Aucun. Le module ne définit aucune classe `ObjectModel` personnalisée ou d'autres classes PHP autonomes dans le répertoire `classes/`. Toute la logique est contenue dans le fichier de module principal et la surcharge du `CartController`.

### 4.4 Actifs JavaScript (`views/js/`)

Aucun. Le module n'inclut aucun fichier JavaScript personnalisé. Toutes les interactions front-office sont gérées côté serveur par la surcharge du `CartController`.

### 4.5 Feuilles de style CSS (`views/css/`)

Aucun. Le module n'inclut aucun fichier CSS personnalisé. Tous les messages affichés au client hériteront du style des messages d'erreur/notification du thème PrestaShop actif.

### 4.6 Structure du modèle Smarty (`views/templates/`)

Aucun. Le module n'utilise pas de fichiers de modèle Smarty personnalisés. Les messages d'erreur sont transmis directement au tableau `errors` du `CartController`, qui sont ensuite rendus par le mécanisme d'affichage d'erreur standard du thème.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    Le module ne crée aucune table de base de données personnalisée. Tous ses paramètres de configuration sont stockés dans la table `ps_configuration` :

    -   `DVFIS_MESSAGE` : Stocke le message personnalisé pour les clients.
    -   `DVFIS_ENABLED` : Stocke la valeur booléenne (0 ou 1) pour activer/désactiver le module.
    -   `DVFIS_STR` : Stocke le préfixe de chaîne pour les exceptions de code de bon de réduction.
    -   `DVFIS_STRV` : (Probablement une clé de version héritée ou interne, non directement configurable par l'utilisateur).
    -   `mypresta_updates`, `update_`, `updatev_` : Clés liées au système de mise à jour de MyPresta.eu.
    -   `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` : Clés de configuration PrestaShop standard utilisées pour la gestion des langues dans le `getContent()` du module.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Lors de l'initialisation du contrôleur Back Office | Utilisé par le module pour inclure ses propres fichiers CSS/JS (le cas échéant) dans le Back Office. Dans le cas de ce module, il est probablement utilisé pour le système de mise à jour de MyPresta.eu ou la configuration générale du module, pas pour le style/scripting personnalisé. |
| `actionFrontControllerInitAfter` | Après l'initialisation d'un contrôleur Front Office | Utilisé par le module pour potentiellement effectuer des actions ou modifier le comportement du contrôleur tôt dans le cycle de vie de la requête. Pour ce module, il est probablement utilisé pour s'assurer que la surcharge du `CartController` est correctement chargée et active. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Désactiver les bons de réduction pour les articles en promotion », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
