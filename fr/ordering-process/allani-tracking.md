---
title: "Suivi Allani - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop de suivi Allani par MyPresta.eu."
sidebar:
  label: "Suivi Allani - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Allani tracking sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/allani-tracking.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/allani-tracking/)
>
> ---


# Suivi Allani

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Compatibilité PHP** : PHP 5.6 - 8.5 (Le module est conçu pour fonctionner sur une large gamme de versions PHP, jusqu'à la dernière version stable prise en charge par PrestaShop 1.7.x et les versions futures.)
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL) généralement disponibles sur tout environnement d'hébergement PrestaShop moderne.

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur "Configurer" à côté du module "Suivi Allani" pour accéder à ses paramètres.

#### Identification de la commande

Cette section contrôle la manière dont le module identifie et envoie les données de commande à Allani.

- **Ce que fait ce paramètre :** C'est le paramètre principal du module. Il détermine si le module est actif et envoie les données de commande à Allani.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Le module enverra automatiquement les détails de la commande (identifiants de produit, valeur de la commande, identifiant de la commande) à la plateforme Allani chaque fois qu'un client finalise une commande sur votre boutique PrestaShop. Ceci est essentiel pour qu'Allani puisse suivre vos ventes.
  - *Lorsqu'il est désactivé (NON) :* Le module cessera d'envoyer toute donnée de commande à Allani. Cela signifie qu'Allani ne recevra pas de mises à jour en temps réel sur vos ventes, ce qui pourrait avoir un impact sur vos analyses et rapports sur leur plateforme.
- **Valeur recommandée :** **OUI**. Pour utiliser pleinement le service de suivi Allani, ce paramètre doit toujours être activé.
- **Scénario / exemple de marchand :** Si vous venez de vous inscrire à Allani et souhaitez commencer à suivre vos ventes immédiatement, vous activeriez ce paramètre. Si vous souhaitez temporairement suspendre la transmission de données à Allani pour des raisons de maintenance ou de test, vous pourriez le désactiver, mais n'oubliez pas de le réactiver par la suite.

#### Autres paramètres internes (Non directement configurables par le marchand)

Vous pourriez voir d'autres clés de configuration comme `mypresta_updates`, `update_`, `updatev_`, `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`. Ce sont des paramètres internes utilisés par le module pour ses propres vérifications de mise à jour ou pour interagir avec les fonctionnalités principales de PrestaShop (comme la gestion des langues). Vous n'avez pas besoin de les configurer, et ils ne sont pas exposés comme des options modifiables par l'utilisateur.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Identification de la commande | OUI | Contrôle si les données de commande sont envoyées à Allani. **Activer** pour le suivi Allani. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai installé le module, mais je ne vois aucun changement sur ma boutique. Fonctionne-t-il ?**
R : Oui, c'est normal ! Le module de suivi Allani fonctionne entièrement en arrière-plan. Il n'ajoute aucun élément visible au front-office de votre boutique. Sa fonction est d'envoyer des données à Allani après qu'une commande a été passée. Pour confirmer qu'il fonctionne, passez une commande test, puis vérifiez votre compte Allani pour les nouvelles données de commande.

**Q : Allani ne reçoit pas mes données de commande. Que dois-je vérifier ?**
R :

1. **Module activé :** Allez dans **Modules > Gestionnaire de modules**, trouvez "Suivi Allani" et assurez-vous qu'il est installé et activé.
2. **Paramètre de configuration :** Cliquez sur "Configurer" pour le module et assurez-vous que "Identification de la commande" est réglé sur **OUI**.
3. **Vider le cache :** Parfois, le cache de PrestaShop peut empêcher les nouveaux paramètres de prendre effet. Allez dans **Paramètres avancés > Performance** et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions plus anciennes).
4. **Compte Allani :** Vérifiez à nouveau les paramètres de votre compte Allani ou contactez le support Allani pour vous assurer que votre boutique est correctement liée de leur côté.
5. **Version de PrestaShop :** Assurez-vous d'avoir téléchargé la version correcte du module pour votre installation PrestaShop (par exemple, 1.7.x, 1.6.x).

**Q : Ce module va-t-il ralentir ma boutique ?**
R : Non, l'impact sur les performances de votre boutique est négligeable. Le script de suivi n'est exécuté que sur la page de confirmation de commande, qui est généralement la dernière étape du parcours client. Le transfert de données est rapide et asynchrone, ce qui signifie qu'il ne retardera pas le chargement de la page pour vos clients.

**Q : Ce module prend-il en charge les configurations multi-langues ou multi-boutiques ?**
R : Le module envoie principalement des données numériques et des identifiants de produit, qui sont indépendants de la langue. Pour le multi-boutique, tant que le module est activé et configuré pour chaque contexte de boutique où vous souhaitez suivre les commandes, il devrait fonctionner correctement.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module `Suivi Allani` est un module PrestaShop léger conçu dans un seul but : envoyer les données de confirmation de commande à la plateforme Allani. Il suit une structure de module PrestaShop standard, utilisant principalement des hooks pour injecter sa logique de suivi. La fonctionnalité principale réside dans la classe principale du module (`allanitracking.php`), qui gère l'installation, la désinstallation, la configuration et l'enregistrement des hooks. Il n'introduit pas de contrôleurs, de modèles ou d'actifs JavaScript/CSS complexes personnalisés, se concentrant uniquement sur la transmission de données via un template Smarty injecté dans le hook `displayOrderConfirmation`.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. La logique front-office du module est gérée directement dans le hook `displayOrderConfirmation` via un template Smarty.
- **Contrôleurs d'administration Back-Office** : Aucun. La configuration est gérée directement via la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

- Aucune classe personnalisée ou définition `ObjectModel` n'est introduite par ce module. Toute la logique est autonome dans `allanitracking.php`.

### 4.4 Actifs JavaScript (`views/js/`)

- Aucun fichier JavaScript personnalisé n'est inclus ou utilisé par ce module. Le script de suivi est intégré directement dans le template `displayOrderConfirmation.tpl`.

### 4.5 Feuilles de style CSS (`views/css/`)

- Aucun fichier CSS personnalisé n'est inclus ou utilisé par ce module, car il n'a pas de composants front-office visibles.

### 4.6 Structure des templates Smarty (`views/templates/`)

Le module utilise des templates Smarty pour injecter le script de suivi dans le front-office.

- **Templates de hook (`views/templates/hook/`)** :

  - `allanitracking/views/templates/hook/displayOrderConfirmation.tpl`
    - **Hook** : `displayOrderConfirmation`
    - **Objectif** : Ce template est rendu sur la page de confirmation de commande (après un achat réussi). Il contient la logique principale pour envoyer les données de commande à Allani. Il accède aux variables Smarty `$order` et `$products`, qui sont passées par PrestaShop à ce hook, pour extraire `orderValue`, `orderID` et `productIds`. Le template construit ensuite et exécute le JavaScript nécessaire pour transmettre ces données à la plateforme Allani.
  - `allanitracking/views/templates/hook/header.tpl`
    - **Hook** : `displayHeader` (ou `header` dans les versions plus anciennes)
    - **Objectif** : Ce template est généralement utilisé pour inclure du JavaScript ou du CSS global dans la section `<head>` de la page. Dans le contexte de ce module, il pourrait être utilisé pour inclure des scripts Allani globaux ou des balises meta nécessaires, bien que la transmission principale des données soit gérée par `displayOrderConfirmation.tpl`. Compte tenu de la description du module, il inclut probablement une configuration minimale ou un espace réservé.
- **Templates d'administration (`views/templates/admin/`)** : Aucun.
- **Templates front-office (`views/templates/front/`)** : Aucun.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne crée aucune table SQL personnalisée.
  - Il stocke sa configuration dans la table `ps_configuration`, spécifiquement la clé `ALLANI_ORDER_TRACK`.
  - Il utilise également les clés de configuration PrestaShop standard pour les vérifications de mise à jour (`mypresta_updates`, `update_`, `updatev_`).
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` / `header` | Dans la section `<head>` de chaque page du front-office. | Potentiellement utilisé pour l'initialisation globale du script Allani ou les balises meta. |
| `displayOrderConfirmation` | Sur la page de confirmation de commande, après un achat réussi. | **Hook principal pour ce module.** Injecte le code JavaScript pour envoyer les détails de la commande (identifiants de produit, valeur de la commande, identifiant de la commande) à la plateforme Allani. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module "Suivi Allani", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question que vous pourriez avoir concernant la fonctionnalité du module.
