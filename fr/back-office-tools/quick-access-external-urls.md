---
title: "Accès Rapide - URL externes - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Accès Rapide - URL externes par MyPresta.eu."
sidebar:
  label: "Accès Rapide - URL externes - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Quick Access - external urls sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/quick-access-external-urls.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/quick-access-external-urls/)
>
> ---


# Accès Rapide - URL externes

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

Ce module s'intègre directement au système de gestion des Accès Rapides existant de PrestaShop. Il n'y a pas d'écran de configuration séparé pour le module lui-même. Au lieu de cela, il modifie le comportement de la fonctionnalité "Accès Rapide" par défaut dans votre Back Office.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Lorsque vous cliquez sur « Configurer » pour le module « Accès Rapide - URL externes », vous verrez généralement une simple confirmation que le module est installé et actif. Il n'y a pas de paramètres spécifiques à ajuster sur cette page, car le module fonctionne en remplaçant le comportement de base de PrestaShop.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

La fonctionnalité du module est gérée via le menu Accès Rapide standard de PrestaShop.

**Nom de l'écran et emplacement du menu :**

-   **Back Office > Administration > Accès Rapide** (ou **Configurer > Paramètres avancés > Accès Rapide** dans les anciennes versions de PrestaShop 1.7.x).
-   Vous pouvez également y accéder directement depuis le menu Accès Rapide lui-même (la petite icône d'horloge en haut de votre Back Office), en cliquant sur « Gérer l'accès rapide ».

**Actions et paramètres disponibles :**
Sur cet écran, vous verrez une liste de vos liens d'Accès Rapide existants.

-   **Ajouter un nouveau lien d'Accès Rapide :**

    1.  Cliquez sur le bouton **« Ajouter un nouvel accès rapide »** (ou similaire, généralement une icône plus).
    2.  Vous verrez un formulaire avec des champs comme :
        -   **Nom :** Le texte qui apparaîtra dans votre menu Accès Rapide (par exemple, « Portail d'expédition DHL », « Tableau de bord Stripe », « Google Analytics »).
        -   **URL :** C'est le champ crucial. **Avec ce module installé, vous pouvez maintenant saisir N'IMPORTE QUELLE URL valide ici, y compris des sites web externes.** Par exemple :
            -   `https://www.dhl.com/global-en/home/tracking.html`
            -   `https://dashboard.stripe.com/`
            -   `https://analytics.google.com/`
            -   `https://mypresta.eu/`
        -   **Ouvrir dans une nouvelle fenêtre :** (Recommandé : OUI) Cette option détermine si le lien s'ouvre dans un nouvel onglet/fenêtre du navigateur.
            -   *Lorsque activé :* Le lien externe s'ouvrira dans un nouvel onglet, gardant votre Back Office PrestaShop ouvert dans l'onglet actuel. Ceci est généralement recommandé pour les liens externes afin d'éviter de quitter votre panneau d'administration.
            -   *Lorsque désactivé :* Le lien s'ouvrira dans le même onglet, remplaçant la vue de votre Back Office PrestaShop.
    3.  Cliquez sur **« Enregistrer »**.
-   **Modifier un lien d'Accès Rapide existant :**

    1.  Trouvez le lien dans la liste et cliquez sur l'icône « Modifier » (crayon).
    2.  Modifiez le Nom ou l'URL si nécessaire.
    3.  Cliquez sur « Enregistrer ».
-   **Supprimer un lien d'Accès Rapide :**

    1.  Trouvez le lien dans la liste et cliquez sur l'icône « Supprimer » (corbeille).
    2.  Confirmez la suppression.

**Effet des changements :**

-   Tous les liens d'Accès Rapide que vous ajoutez, modifiez ou supprimez sur cet écran se refléteront immédiatement dans le menu Accès Rapide (l'icône d'horloge) en haut de votre Back Office PrestaShop.
-   Lorsque vous cliquez sur un lien d'Accès Rapide qui pointe vers une URL externe, votre navigateur naviguera vers ce site externe (soit dans le même onglet, soit dans un nouvel onglet, selon votre paramètre « Ouvrir dans une nouvelle fenêtre »).

**Flux de travail recommandé pour la gestion quotidienne de la boutique :**

1.  **Identifiez les outils externes fréquemment utilisés :** Pensez aux sites web que vous visitez quotidiennement ou hebdomadairement pour gérer votre boutique (par exemple, expédition, paiement, marketing, support, portails fournisseurs).
2.  **Ajoutez-les à l'Accès Rapide :** Allez dans **Administration > Accès Rapide** et ajoutez chaque URL externe avec un nom clair et descriptif.
3.  **Activez « Ouvrir dans une nouvelle fenêtre » :** Pour tous les liens externes, définissez « Ouvrir dans une nouvelle fenêtre » sur OUI. Cela garantit que votre Back Office PrestaShop reste ouvert et accessible.
4.  **Organisez pour votre équipe :** Si vous avez plusieurs utilisateurs administrateurs, réfléchissez aux liens rapides qui seraient les plus bénéfiques pour chaque rôle.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Back Office > Administration > Accès Rapide** | **Nom** | Défini par l'utilisateur | Texte affiché dans le menu Accès Rapide. |
| | **URL** | Défini par l'utilisateur (URL externe) | L'adresse web vers laquelle le lien pointe. **Ce module active les URL externes ici.** |
| | **Ouvrir dans une nouvelle fenêtre** | OUI (pour les liens externes) | Détermine si le lien s'ouvre dans un nouvel onglet/fenêtre du navigateur. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai installé le module, mais je ne peux toujours pas ajouter d'URL externes à l'Accès Rapide. Qu'est-ce qui ne va pas ?**
R1 :

-   **Vider le cache :** Après l'installation, videz toujours le cache de votre PrestaShop. Allez dans **Paramètres avancés > Performances**, et cliquez sur « Vider le cache » en haut à droite.
-   **Vérifier l'état du module :** Assurez-vous que le module est activé. Allez dans **Modules > Gestionnaire de modules**, recherchez « Accès Rapide - URL externes », et vérifiez qu'il est actif.
-   **Vérifier l'installation :** Parfois, une installation peut échouer silencieusement. Essayez de désinstaller et de réinstaller le module.
-   **Cache du navigateur :** Videz le cache et les cookies de votre navigateur, ou essayez d'accéder au Back Office dans une fenêtre de navigation privée/incognito.

**Q2 : Mes liens d'Accès Rapide s'ouvrent dans le même onglet, même pour les sites externes. Comment puis-je résoudre ce problème ?**
R2 :

-   Lorsque vous ajoutez ou modifiez un lien d'Accès Rapide, assurez-vous que l'option **« Ouvrir dans une nouvelle fenêtre »** est définie sur **OUI**. Ce paramètre contrôle si le lien s'ouvre dans un nouvel onglet ou dans l'onglet actuel.

**Q3 : Ce module affectera-t-il les performances ou le référencement de ma boutique ?**
R3 :

-   Non. Ce module fonctionne entièrement dans le Back Office de PrestaShop. Il n'ajoute aucun code, style ou fonctionnalité au front office de votre boutique (ce que les clients voient). Par conséquent, il n'a aucun impact sur la vitesse de chargement de votre boutique, le référencement ou l'expérience client.

**Q4 : J'ai ajouté de nombreux liens d'Accès Rapide. Puis-je les organiser ?**
R4 :

-   La fonction d'Accès Rapide par défaut de PrestaShop n'offre pas d'organisation avancée comme des dossiers ou des catégories. Cependant, vous pouvez contrôler l'ordre des liens en les faisant glisser et déposer sur la page **Administration > Accès Rapide**. Vous pouvez également utiliser des noms descriptifs pour les rendre faciles à identifier.

**Q5 : Que se passe-t-il si je désinstalle ce module ? Mes liens d'Accès Rapide externes disparaîtront-ils ?**
R5 :

-   Si vous désinstallez ce module, la possibilité d'ajouter de *nouvelles* URL externes sera supprimée. Les URL externes existantes que vous avez ajoutées lorsque le module était actif *pourraient* continuer à fonctionner, mais la validation du cœur de PrestaShop pourrait empêcher leur modification ou causer des problèmes. Il est préférable de garder le module installé si vous comptez sur les liens d'Accès Rapide externes.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Accès Rapide - URL externes » (`qae`) réalise sa fonctionnalité en surchargeant les classes et contrôleurs PrestaShop de base. Plus précisément, il cible l'`ObjectModel` `QuickAccess` et l'`AdminQuickAccessesController` pour supprimer la validation qui restreint les URL d'Accès Rapide aux chemins internes du Back Office. Il s'agit d'un modèle de surcharge PrestaShop courant.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Ce module n'inclut aucun contrôleur front-office car sa fonctionnalité est exclusivement destinée au Back Office.
-   **Contrôleurs d'administration Back-Office** :

    -   **`qae/override/controllers/admin/AdminQuickAccessesController.php`**
        -   **Nom de la classe** : `AdminQuickAccessesController` (surcharge le `AdminQuickAccessesController` de base)
        -   **Classe parente** : `AdminController`
        -   **Responsabilité** : Cette surcharge est cruciale. L'`AdminQuickAccessesController` original contient une logique pour valider le champ `url` d'une entrée d'Accès Rapide, en s'assurant qu'il s'agit d'un chemin interne du Back Office PrestaShop. Cette surcharge modifie ou supprime cette validation, permettant l'enregistrement d'URL externes. Les développeurs doivent inspecter les méthodes `postProcess()` ou `renderForm()` pour les changements spécifiques liés à la validation d'URL.

### 4.3 Classes et modèles de base (`classes/`)

-   **`qae/override/classes/index.php`**

    -   Il s'agit généralement d'un fichier vide ou d'un fichier contenant uniquement `<?php exit; ?>` pour empêcher la liste directe des répertoires. C'est une mesure de sécurité et non une partie de la logique de base du module.
-   **`qae/override/classes/Link.php`**

    -   **Nom de la classe** : `Link` (surcharge la classe `Link` de base)
    -   **Classe parente** : `LinkCore`
    -   **Responsabilité** : La classe `Link` est responsable de la génération d'URL dans PrestaShop. Bien que le changement principal pour les URL externes se trouve dans `QuickAccess` et `AdminQuickAccessesController`, une surcharge de `Link` peut être présente pour s'assurer que toutes les méthodes de génération ou de validation d'URL internes sur lesquelles `QuickAccess` s'appuie sont compatibles avec la nouvelle autorisation d'URL externes, ou pour éviter des effets secondaires indésirables. Les développeurs doivent rechercher les modifications dans les méthodes liées à la validation ou à la désinfection d'URL.
-   **`qae/override/classes/QuickAccess.php`**

    -   **Nom de la classe** : `QuickAccess` (surcharge l'`ObjectModel` `QuickAccess` de base)
    -   **Classe parente** : `ObjectModel`
    -   **Table de base de données** : `ps_quick_access`
    -   Champs `$definition` : Cette classe définit la structure d'une entrée d'Accès Rapide, y compris `id_quick_access`, `name`, `url` et `new_window`.
    -   **Méthodes publiques clés et logique métier** : Cette surcharge est fondamentale. L'`ObjectModel` `QuickAccess` original inclut probablement des règles de validation pour le champ `url` dans ses méthodes `validateFields()` ou `add()`/`update()`. Cette surcharge supprime ou assouplit ces règles de validation, permettant au champ `url` de stocker n'importe quelle chaîne, y compris des URL externes, sans déclencher d'erreurs de validation.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé. Les modifications sont purement côté serveur (surcharges PHP).

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé. La présentation visuelle du menu Accès Rapide est gérée par le thème par défaut du Back Office de PrestaShop.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Ce module n'inclut aucun fichier de modèle Smarty personnalisé. Il utilise les modèles existants du Back Office de PrestaShop pour le rendu de la page de gestion des Accès Rapides et du menu Accès Rapide lui-même.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Ce module ne crée aucune nouvelle table de base de données. Il modifie le comportement de la manière dont les données sont stockées et validées pour la table `ps_quick_access` existante.
    -   Les enregistrements de configuration ne sont pas stockés dans `ps_configuration` par ce module, car il repose principalement sur des surcharges de classes/contrôleurs.
-   **Table des hooks enregistrés** :
    Ce module n'enregistre aucun hook spécifique au sens traditionnel (par exemple, `displayHeader`, `actionValidateOrder`). Sa fonctionnalité est implémentée via le système de surcharge de PrestaShop, qui modifie directement les classes et contrôleurs de base plutôt que d'injecter du code via des hooks.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Accès Rapide - URL externes », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question que vous pourriez avoir.
