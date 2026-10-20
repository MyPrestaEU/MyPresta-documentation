---
title: "Stylight - pixel de suivi des ventes - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Stylight - pixel de suivi des ventes par MyPresta.eu."
sidebar:
  label: "Stylight - pixel de suivi des ventes"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Stylight - sales tracking pixel sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/stylight-sales-tracking-pixel.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/stylight-sales-tracking-pixel/)
>
> ---


# Stylight - pixel de suivi des ventes

## 1. Exigences et compatibilité
- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL) généralement disponibles sur la plupart des environnements d'hébergement compatibles PrestaShop.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Le module "Stylight - pixel de suivi des ventes" est conçu pour être extrêmement simple à configurer, ne nécessitant aucun paramètre spécifique de la part du marchand. Sa fonctionnalité est principalement autonome, détectant et transmettant automatiquement les données de commande nécessaires.

En naviguant vers la page de configuration du module (Back Office > Modules > Gestionnaire de modules > Stylight - pixel de suivi des ventes > Configurer), vous trouverez généralement un message de confirmation indiquant que le module est installé et actif.

-   **Ce que fait cet écran :** Cette page sert de confirmation que le module est correctement installé et prêt à suivre les ventes. Il n'y a pas de champs de saisie ou d'interrupteurs à ajuster. Le module s'accroche automatiquement au processus de confirmation de commande et collecte toutes les données requises (montant total, devise, nombre d'articles, numéros SKU, ID de commande) directement à partir des détails de commande de PrestaShop.
-   **Effet de la modification de ce paramètre :** Puisqu'il n'y a pas de paramètres configurables, il n'y a rien à changer. Le module fonctionne dès l'installation.
-   **Valeur recommandée :** Aucune action requise.
-   **Scénario / exemple de marchand :** Après avoir installé le module, vous visitez simplement cette page pour confirmer sa présence. Vous n'avez pas besoin de saisir d'ID ou de clés spécifiques à Stylight, car le pixel lui-même est générique et conçu pour fonctionner avec le système de Stylight en envoyant des données e-commerce standard.

### 2.2 Tableau de référence rapide de la configuration
| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
|---|---|---|---|
| Page de configuration du module | *(Aucun paramètre configurable par l'utilisateur)* | N/A | Le module suit automatiquement les données de vente (montant total, devise, nombre d'articles, SKU, ID de commande) sur la page de confirmation de commande pour Stylight.com. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai installé le module, mais je ne vois aucune vente signalée dans mon compte Stylight. Que dois-je faire ?**
R : Tout d'abord, assurez-vous que le module est activé dans votre Back Office PrestaShop. Ensuite, essayez de vider le cache de votre PrestaShop (Paramètres avancés > Performances > Vider le cache). Si le problème persiste, effectuez vous-même une commande test. Si aucune donnée n'apparaît toujours, contactez le support MyPresta.eu avec les détails de votre version de PrestaShop et de tout autre module récemment installé.

**Q : Ce module ralentit-il ma page de confirmation de commande ?**
R : Le pixel de suivi est très léger et se charge de manière asynchrone, ce qui signifie qu'il n'a généralement pas d'impact significatif sur les temps de chargement des pages ou l'expérience client. Son effet sur les performances est minimal.

**Q : Dois-je saisir un ID Stylight ou une clé API dans le module ?**
R : Non, ce module est conçu pour fonctionner dès l'installation. Il implémente un pixel de suivi Stylight standard qui envoie automatiquement les données de commande nécessaires sans nécessiter d'ID spécifiques saisis par le marchand dans la configuration du module. Votre compte Stylight est lié à votre domaine, et leur système identifie votre boutique en fonction de l'origine du pixel.

**Q : Ce module est-il compatible avec les thèmes personnalisés ?**
R : Oui, le module s'accroche à un hook PrestaShop standard (`displayOrderConfirmation`) qui est généralement présent dans tous les thèmes bien codés. Il ne dépend pas d'éléments de thème spécifiques, il devrait donc fonctionner de manière transparente avec la plupart des thèmes personnalisés.

**Q : J'ai plusieurs langues/devises. Le module les suit-il correctement ?**
R : Oui, le module est conçu pour capturer automatiquement le montant total et la devise de la commande tels que traités par PrestaShop, garantissant un suivi précis pour les boutiques multi-devises et multi-langues.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture
Le module "Stylight - pixel de suivi des ventes" est un module PrestaShop simple, principalement axé sur le hooking d'événements front-office. Il utilise le hook `displayOrderConfirmation` pour injecter un pixel de suivi basé sur JavaScript sur la page de confirmation de commande finale. La logique du module est contenue dans son fichier PHP principal, `index.php`, qui gère l'installation, la désinstallation et l'enregistrement du hook. La collecte de données est dynamique, extrayant les détails de la commande directement des objets `Order` et `Product` disponibles dans le contexte de la page de confirmation de commande.

### 4.2 Contrôleurs (`controllers/`)
-   **Contrôleurs Front-Office** : Aucun. La fonctionnalité front-office du module est entièrement gérée en s'accrochant à `displayOrderConfirmation` et en rendant un template Smarty.
-   **Contrôleurs d'administration Back-Office** : Aucun. Le module n'a pas d'interface d'administration dédiée au-delà de la page de configuration standard du module (`getContent()`).

### 4.3 Classes et modèles principaux (`classes/`)
-   Aucun. Le module ne définit aucune classe personnalisée ni n'étend `ObjectModel`. Toute la logique réside dans le fichier principal `stylightpixel/index.php`.

### 4.4 Actifs JavaScript (`views/js/`)
-   Aucun. Le code du pixel de suivi est directement intégré dans le template Smarty (`displayOrderConfirmation.tpl`) pour s'assurer qu'il se déclenche immédiatement au chargement de la page.

### 4.5 Feuilles de style CSS (`views/css/`)
-   Aucun. Le module est purement fonctionnel et n'a pas de composants visuels ou d'exigences de style.

### 4.6 Structure du template Smarty (`views/templates/`)
-   **Templates de hook (`views/templates/hook/`)** :
    *   `stylightpixel/views/templates/hook/displayOrderConfirmation.tpl`
        *   **Hook** : `displayOrderConfirmation`
        *   **Objectif** : Ce template est rendu sur la page de confirmation de commande après un achat réussi. Il contient le code JavaScript du pixel de suivi Stylight.
        *   **Données disponibles** : Le template reçoit `$order` (un objet `Order`) et `$products` (un tableau d'objets `Product` associés à la commande) de la méthode `hookDisplayOrderConfirmation`.
        *   **Sortie** : Il génère un bloc `<script>` qui construit l'URL du pixel de suivi Stylight avec des paramètres dynamiques tels que `order_id`, `total_amount`, `currency`, `item_count` et `sku` pour chaque produit.

### 4.7 Schéma de base de données et carte des hooks
-   **Tables de base de données** : Le module ne crée aucune table de base de données personnalisée. Il s'appuie sur les tables PrestaShop standard (`ps_orders`, `ps_order_detail`, `ps_product`, etc.) pour récupérer les informations de commande.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
|---|---|---|
| `displayOrderConfirmation` | Exécuté sur la page de confirmation de commande finale après un achat réussi. | Injecte le JavaScript du pixel de suivi Stylight dans la page pour envoyer les données de conversion (ID de commande, total, devise, SKU des produits, nombre d'articles) à Stylight. |

## 5. Support officiel et mises à jour
Pour les mises à jour officielles, le support technique et toute assistance supplémentaire concernant le module "Stylight - pixel de suivi des ventes", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec les questions liées au module et s'assurer que votre pixel de suivi fonctionne correctement.
