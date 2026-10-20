---
title: "Homeslider en haut - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Homeslider en haut par MyPresta.eu."
sidebar:
  label: "Homeslider en haut - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Homeslider on top sur MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/homeslider-on-top.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/sliders-slideshows/homeslider-on-top/)
>
> ---


# Homeslider en haut

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour une installation PrestaShop et prendront en charge ce module.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

Ce module est conçu pour être extrêmement simple, agissant principalement comme un "pont" pour permettre au *slider d'images PrestaShop par défaut* d'être affiché à un nouvel emplacement. Par conséquent, son propre écran de configuration est minimal. Les images, liens et paramètres réels du slider (comme la vitesse, la pause au survol, etc.) sont gérés via le module standard "Slider d'images" de PrestaShop.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après avoir installé "Homeslider en haut", naviguez vers **Modules > Gestionnaire de modules**, recherchez "Homeslider en haut" et cliquez sur "Configurer".

Vous trouverez généralement une interface de configuration très simple, principalement axée sur l'activation ou la désactivation de la fonctionnalité principale du module.

-   **Ce que fait ce paramètre :** Ce paramètre contrôle si le module "Homeslider en haut" est actif et tente d'afficher votre slider d'images à la position supérieure désignée.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé :* Le module enregistrera ses hooks et tentera de rendre le slider d'images PrestaShop par défaut en haut de votre boutique.
    -   *Lorsqu'il est désactivé :* Le module cessera de fonctionner, et le slider d'images n'apparaîtra pas en position supérieure (il reviendra à son emplacement par défaut si le module Slider d'images standard est toujours actif et accroché ailleurs).
-   **Valeur recommandée :** **OUI** (Activé) si vous souhaitez que votre slider apparaisse en haut.
-   **Scénario / exemple de marchand :** Vous venez de lancer une nouvelle collection et souhaitez la présenter de manière proéminente avec une grande bannière tout en haut de votre site. Vous activeriez ce module. Si vous décidez plus tard que vous préférez le slider à un emplacement différent (par exemple, sous l'en-tête), vous pourriez désactiver ce module et ré-accrocher le module Slider d'images standard ailleurs.

**Note importante :** Ce module *ne gère pas* les images ou les paramètres du slider lui-même. Pour ajouter, modifier ou supprimer des diapositives, ou pour modifier le comportement du slider (comme la vitesse de transition, la lecture automatique, etc.), vous devez vous rendre dans la configuration du module **"Slider d'images"** (souvent trouvé sous **Modules > Gestionnaire de modules**, recherchez "Slider d'images" ou "ps\_imageslider").

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Module activé/désactivé | Activé | Contrôle si le module affiche activement le slider d'images en haut de la boutique. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mon slider ne s'affiche pas du tout, même après avoir activé le module.**
R :

1.  **Vérifiez le module "Slider d'images" :** Assurez-vous que le *module "Slider d'images" PrestaShop par défaut* (souvent nommé `ps_imageslider`) est installé, activé et que des diapositives sont configurées. Ce module "Homeslider en haut" ne fait que modifier la *position* de ce slider existant.
2.  **Videz le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions antérieures). Parfois, PrestaShop a besoin d'une actualisation du cache pour reconnaître les nouveaux emplacements de modules.
3.  **Compatibilité du thème :** Bien que conçu pour une large compatibilité, certains thèmes fortement personnalisés peuvent outrepasser les comportements de hook par défaut. Si les problèmes persistent, contactez le développeur de votre thème ou le support MyPresta.eu.

**Q : Le slider s'affiche, mais il a l'air étrange ou mal aligné.**
R :

1.  **Vérifiez les paramètres du "Slider d'images" :** Assurez-vous que les images que vous avez téléchargées dans le *module "Slider d'images" PrestaShop par défaut* ont des dimensions cohérentes et sont de haute qualité.
2.  **Style du thème :** Le CSS de votre thème pourrait être en conflit. Ce module gère principalement le placement. Si le style est incorrect, il s'agit probablement d'un problème CSS avec votre thème interagissant avec les styles par défaut du slider. Vous pourriez avoir besoin d'un développeur web pour inspecter le CSS.

**Q : Comment puis-je modifier les images ou la vitesse du slider ?**
R : Ce module ne contrôle que le *placement*. Pour gérer le contenu réel (images, liens, descriptions) et le comportement (vitesse, lecture automatique, pause au survol) du slider, vous devez vous rendre dans la configuration du module **"Slider d'images"** (le module PrestaShop standard, généralement trouvé en recherchant "Slider d'images" dans **Modules > Gestionnaire de modules**).

**Q : Puis-je avoir deux sliders, un en haut et un à la position par défaut ?**
R : Ce module déplace spécifiquement le slider d'images PrestaShop *par défaut* vers le haut. Si vous souhaitez un deuxième slider indépendant, vous auriez besoin d'un module différent conçu à cet effet.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique pour les développeurs et les webmasters souhaitant comprendre, personnaliser ou dépanner le module "Homeslider en haut".

### 4.1 Aperçu de l'architecture

Le module "Homeslider en haut" est un module PrestaShop léger principalement conçu pour modifier l'emplacement d'affichage du module `ps_imageslider` principal. Il y parvient en désenregistrant `ps_imageslider` de ses hooks par défaut (comme `displayHome`) et en le réenregistrant à un hook plus proéminent, généralement `displayHeader`. Il n'introduit pas de nouvelles tables de base de données, de classes complexes ou d'actifs front-office étendus, ce qui en fait un "gestionnaire de hooks" simple mais efficace pour la fonctionnalité de slider existante.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur Front-Office ou Back-Office personnalisé. Toute la configuration est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module n'introduit aucune classe ou modèle personnalisé. Il fonctionne en interagissant avec les fonctions de gestion des modules de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé. Le JavaScript pour la fonctionnalité du slider est fourni par le module `ps_imageslider` lui-même.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé. Le style du slider est fourni par le module `ps_imageslider` et/ou le thème PrestaShop actif.

### 4.6 Structure des templates Smarty (`views/templates/`)

Ce module n'inclut aucun fichier de template Smarty personnalisé. Il s'appuie sur les templates fournis par le module `ps_imageslider`.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** : Ce module ne crée aucune table de base de données personnalisée. Sa configuration est stockée dans `ps_configuration` en utilisant les clés de configuration PrestaShop standard.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `install()` | Lors de l'installation du module | Enregistre le module sur `displayHeader` et désenregistre potentiellement `ps_imageslider` de `displayHome` ou d'autres hooks par défaut. |
| `uninstall()` | Lors de la désinstallation du module | Désenregistre le module de `displayHeader` et réenregistre potentiellement `ps_imageslider` sur ses hooks par défaut. |
| `displayHeader` | Rend le contenu dans la section `<head>` ou tout en haut du `<body>` | C'est le hook principal où le module tente de rendre le contenu de `ps_imageslider`. |
| `hookDisplayHeader` | Lorsque `displayHeader` est appelé | La méthode du module qui s'exécute lorsque `displayHeader` est appelé. Elle appelle généralement `Module::hookDisplayHome()` du module `ps_imageslider` pour rendre son contenu. |

La logique principale réside dans le fichier `homeslider-on-top.php`, spécifiquement dans les méthodes `install()`, `uninstall()` et `hookDisplayHeader()`. La méthode `hookDisplayHeader()` est cruciale car elle est responsable de la récupération et du rendu du contenu du module `ps_imageslider` lorsque ce module est actif.

**Logique clé dans `homeslider-on-top.php` :**

-   **`__construct()`** : Configure les informations de base du module.
-   **`install()`** :
    -   Appelle `parent::install()`.
    -   Enregistre le module sur `displayHeader`.
    -   De manière cruciale, il tente souvent de désenregistrer le module `ps_imageslider` de `displayHome` pour éviter un affichage en double, puis enregistre `ps_imageslider` sur `displayHeader` s'il n'y est pas déjà, ou s'assure que son contenu est rendu via la méthode `hookDisplayHeader` de ce module.
-   **`uninstall()`** :
    -   Appelle `parent::uninstall()`.
    -   Désenregistre le module de `displayHeader`.
    -   Réenregistre `ps_imageslider` sur `displayHome` pour restaurer le comportement par défaut.
-   **`getContent()`** : Gère le formulaire de configuration du back-office du module (qui est généralement très simple, souvent juste un interrupteur d'activation/désactivation).
-   **`hookDisplayHeader()`** :
    -   Cette méthode est exécutée lorsque le hook `displayHeader` est appelé par PrestaShop.
    -   Elle vérifie généralement si le module `ps_imageslider` est installé et activé.
    -   Si c'est le cas, elle appelle directement la méthode `hookDisplayHome()` du module `ps_imageslider` pour récupérer son contenu rendu et le renvoyer, "déplaçant" efficacement la sortie du slider vers la position `displayHeader`.

Les développeurs souhaitant personnaliser ce module se concentreraient principalement sur la méthode `hookDisplayHeader()` s'ils voulaient modifier la façon dont le contenu de `ps_imageslider` est récupéré ou enveloppé, ou sur les méthodes `install()`/`uninstall()` s'ils avaient besoin de modifier les hooks spécifiques impliqués.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module "Homeslider en haut", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
