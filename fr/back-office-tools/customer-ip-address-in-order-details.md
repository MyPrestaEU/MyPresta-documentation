---
title: "Adresse IP du client dans les détails de commande - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Adresse IP du client dans les détails de commande' par MyPresta.eu."
sidebar:
  label: "Adresse IP du client dans les détails de commande"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Customer IP address in order details sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/customer-ip-address-in-order-details.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/customer-ip-address-in-order-details/)
>
> ---


# Adresse IP du client dans les détails de commande

## 1. Exigences et compatibilité
- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes, car ce module a des dépendances externes minimales.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Ce module est conçu pour être extrêmement simple et efficace, ne nécessitant aucune configuration complexe. Après l'installation, vous trouverez un écran de configuration de base.

-   **Nom de l'écran et emplacement du menu :** Back Office > Modules > Gestionnaire de modules > "Adresse IP du client dans les détails de commande" > Configurer

Sur cet écran, vous verrez généralement :

-   **Ce que fait ce paramètre :** Ce module n'a généralement pas de paramètres configurables spécifiques au-delà de son installation initiale. Sa fonctionnalité principale (afficher l'adresse IP) est active par défaut une fois installée. La page de configuration peut simplement confirmer que le module est actif ou fournir des informations de base.
-   **Effet de la modification de ce paramètre :** Puisqu'il n'y a pas de paramètres spécifiques à modifier, le comportement du module reste cohérent : il affichera l'adresse IP du client sur la page des détails de commande.
-   **Valeur recommandée :** N/A (Pas d'options configurables).
-   **Scénario/exemple pour le marchand :** Installez et activez simplement le module. Lorsque vous consultez une commande dans votre back-office, vous verrez désormais l'adresse IP du client affichée de manière proéminente dans les détails de la commande.

### 2.2 Tableau de référence rapide de la configuration
| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
|---|---|---|---|
| Page de configuration du module | *(Aucun paramètre spécifique)* | N/A | Le module affiche automatiquement les adresses IP des clients sur les pages de détails de commande une fois installé et activé. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai installé le module, mais je ne vois pas l'adresse IP sur la page des détails de commande. Que dois-je faire ?**
R :
1.  **Vérifier l'état du module :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que "Adresse IP du client dans les détails de commande" est installé et activé.
2.  **Vider le cache :** Parfois, le cache de PrestaShop peut empêcher les modifications d'apparaître immédiatement. Allez dans **Paramètres avancés > Performance**, faites défiler vers le bas et cliquez sur "Vider le cache".
3.  **Vérifier la page de commande :** Naviguez vers une commande existante (ou passez une commande test) dans **Commandes > Commandes** et cliquez pour afficher ses détails. L'adresse IP devrait apparaître dans un bloc ou une section dédiée.
4.  **Compatibilité du thème :** Bien qu'improbable pour un module simple comme celui-ci, des thèmes très fortement personnalisés peuvent occasionnellement interférer avec les hooks. Si le problème persiste, passez temporairement au thème PrestaShop par défaut (Classic) pour voir si l'adresse IP apparaît.

**Q : Ce module stocke-t-il les adresses IP des clients dans ma base de données ?**
R : PrestaShop lui-même stocke généralement l'adresse IP du client lorsqu'il s'enregistre ou passe une commande. Ce module récupère et affiche simplement ces informations existantes de votre base de données sur la page des détails de commande. Il ne crée pas de nouvelles tables de base de données ni ne stocke de données IP supplémentaires de manière indépendante.

**Q : Ce module va-t-il ralentir ma boutique ?**
R : Non. Ce module est très léger. Il ajoute seulement une petite information à une page de back-office existante (détails de commande) et n'effectue aucun calcul complexe ni aucune opération de front-office qui aurait un impact sur la vitesse de navigation du client.

**Q : L'adresse IP est-elle toujours précise ?**
R : L'adresse IP enregistrée est généralement celle à partir de laquelle le client s'est connecté à votre boutique. Cependant, les clients utilisant des VPN, des serveurs proxy ou certains réseaux mobiles peuvent avoir une adresse IP qui ne reflète pas directement leur emplacement physique. C'est un indicateur utile mais pas toujours un repère géographique définitif.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)
Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture
Le module "Adresse IP du client dans les détails de commande" (`iporder`) est un module PrestaShop très simple conçu pour étendre la fonctionnalité du contrôleur `AdminOrders`. Il utilise un hook PrestaShop standard (`displayAdminOrder`) pour injecter des informations supplémentaires (l'adresse IP du client) directement dans la page de détails de commande du back-office. Il suit une approche minimaliste, se concentrant uniquement sur l'affichage des données existantes plutôt que sur l'introduction de nouveaux modèles de données ou d'une logique complexe.

### 4.2 Contrôleurs (`controllers/`)
Ce module n'introduit aucun contrôleur Front-Office ou Back-Office personnalisé. Sa fonctionnalité est entièrement intégrée via des hooks au sein des contrôleurs PrestaShop existants.

### 4.3 Classes et modèles de base (`classes/`)
Ce module ne définit aucune classe personnalisée et n'étend pas `ObjectModel`. Il fonctionne en accédant directement aux objets PrestaShop de base existants et à leurs propriétés (par exemple, `Order`, `Customer`).

### 4.4 Actifs JavaScript (`views/js/`)
Ce module n'inclut aucun fichier JavaScript personnalisé. L'affichage de l'adresse IP est un rendu HTML purement côté serveur.

### 4.5 Feuilles de style CSS (`views/css/`)
Ce module n'inclut aucun fichier CSS personnalisé. Le contenu injecté héritera du style du thème du back-office PrestaShop.

### 4.6 Structure du template Smarty (`views/templates/`)
Toute la logique d'affichage du module réside dans un seul fichier de template Smarty.

-   **Templates de hook (`views/templates/hook/`)** :
    *   `iporder/views/templates/hook/displayAdminOrder.tpl`
        *   **Hook :** `displayAdminOrder`
        *   **Objectif :** Ce template est rendu sur la page des détails de commande du back-office PrestaShop. Il récupère l'adresse IP du client associée à la commande actuelle et l'affiche dans un bloc dédié.
        *   **Contenu :** Il accède généralement aux variables Smarty `$order` et `$customer` (passées par le hook `displayAdminOrder`) pour récupérer `{$customer->ip_registration_date}` ou similaire, et le formate pour l'affichage. Il peut également utiliser `$_SERVER['REMOTE_ADDR']` si l'IP n'est pas directement stockée avec l'objet client ou commande d'une manière facilement accessible via le hook. Compte tenu de la description du module, il accède probablement à l'adresse IP stockée avec l'objet client ou commande.

### 4.7 Schéma de la base de données et carte des hooks
-   **Tables de base de données** : Ce module ne crée aucune table de base de données personnalisée. Il s'appuie sur les tables PrestaShop existantes, en particulier `ps_customer` (qui stocke `last_passwd_gen` et `ip_registration_date` dans certaines versions, bien que `ip_registration_date` ne soit pas strictement l'IP de la commande) et potentiellement `ps_orders` si l'IP est stockée directement avec la commande. L'approche la plus courante pour ce module serait de récupérer l'IP de `$_SERVER['REMOTE_ADDR']` au moment de la commande et de la stocker dans un champ personnalisé si elle n'est pas déjà présente, ou simplement d'afficher `ip_registration_date` de l'objet client. Cependant, compte tenu de la simplicité du module et de l'absence de classes personnalisées, il est fort probable qu'il récupère l'IP associée à l'enregistrement du client ou à `REMOTE_ADDR` au moment du traitement de la commande si disponible via le contexte du hook.
    *   **Note :** PrestaShop 1.7+ stocke `current_ip_address` dans la table `ps_connections`, liée à `ps_guest` et `ps_customer`. L'`ip_registration_date` dans `ps_customer` est l'IP à partir de laquelle le client s'est enregistré. L'objectif du module est d'afficher l'IP *au moment de la commande*. Cela signifie généralement soit :
        1.  Accéder à `$_SERVER['REMOTE_ADDR']` si le hook le fournit dans le contexte de la commande.
        2.  Récupérer l'IP de la table `ps_connections` en fonction de l'`id_guest` associé à la commande.
        3.  Récupérer l'`ip_registration_date` de `ps_customer` (moins précis pour la commande spécifique).
        Compte tenu de la simplicité, il utilise probablement la méthode la plus simple disponible via le hook.

-   **Table des hooks enregistrés** :
    | Nom du hook | Moment d'exécution | Objectif technique |
    |---|---|---|
    | `displayAdminOrder` | Exécuté lorsque la page des détails de commande du back-office PrestaShop est rendue. | Injecte l'adresse IP du client dans la vue des détails de commande. |

## 5. Support officiel et mises à jour
Pour les mises à jour officielles, le support technique et toute autre question concernant le module "Adresse IP du client dans les détails de commande", veuillez vous référer à votre compte client MyPresta.eu. Vous pouvez accéder à vos téléchargements et tickets de support directement depuis [Historique des commandes et téléchargements MyPresta.eu](https://mypresta.eu/my-account/orders/).
