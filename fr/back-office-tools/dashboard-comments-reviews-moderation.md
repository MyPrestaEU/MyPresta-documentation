---
title: "Modération des commentaires / avis du tableau de bord - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop de modération des commentaires / avis du tableau de bord par MyPresta.eu."
sidebar:
  label: "Modération des commentaires / avis du tableau de bord"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Dashboard comments / reviews moderation sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/dashboard-comments-reviews-moderation.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/dashboard-comments-reviews-moderation/)
>
> ---


# Modération des commentaires / avis du tableau de bord

## 1. Exigences et Compatibilité
- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises pour PrestaShop lui-même et sont généralement disponibles sur tous les environnements d'hébergement modernes.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur "Configurer" vous mènera à l'écran de configuration principal du module. Ce module est conçu pour être très simple, avec un minimum de paramètres, car sa fonction principale est d'afficher des informations sur votre tableau de bord.

**Nom de l'écran :** Configuration de la modération des commentaires / avis du tableau de bord

**Emplacement du menu :** Back Office > Modules > Gestionnaire de modules > Modération des commentaires / avis du tableau de bord > Configurer

| Paramètre / Option | Ce que fait ce paramètre | Effet de la modification de ce paramètre | Valeur recommandée | Scénario / exemple pour le marchand |
|---|---|---|---|---|
| **Mises à jour MyPresta.eu** | Cette section concerne généralement la vérification des mises à jour pour les modules MyPresta.eu. Elle peut inclure des options pour activer/désactiver les vérifications de mise à jour ou afficher les notifications de mise à jour. | *Lorsqu'activé :* Le module vérifiera périodiquement MyPresta.eu pour les nouvelles versions et vous avertira dans le back office si une mise à jour est disponible. Cela vous aide à maintenir votre module à jour avec les dernières fonctionnalités et corrections de bugs. *Lorsqu'désactivé :* Le module ne vérifiera pas les mises à jour automatiquement. Vous devrez vérifier manuellement les mises à jour sur MyPresta.eu. | **Activé (Oui)** | Garder cette option activée garantit que vous êtes toujours informé des nouvelles versions, vous permettant de bénéficier des améliorations et des mises à jour de sécurité sans vérifications manuelles. |
| **Update_ (Interne)** | Il s'agit d'un paramètre interne, probablement lié au mécanisme de mise à jour lui-même. Il n'est généralement pas destiné à une interaction directe avec le marchand. | La modification de ce paramètre n'est pas recommandée car elle pourrait interférer avec la capacité du module à vérifier et à appliquer les mises à jour. | **Laisser par défaut** | Il s'agit d'un paramètre technique ; les propriétaires de boutique ne devraient pas le modifier. |
| **Updatev_ (Interne)** | Similaire à `update_`, il s'agit d'un paramètre interne lié à la version pour le mécanisme de mise à jour. | La modification de ce paramètre n'est pas recommandée car elle pourrait interférer avec la capacité du module à vérifier et à appliquer les mises à jour. | **Laisser par défaut** | Il s'agit d'un paramètre technique ; les propriétaires de boutique ne devraient pas le modifier. |

**Note importante :** La fonctionnalité principale d'affichage des commentaires et des avis sur votre tableau de bord ne nécessite pas une configuration étendue. Une fois installé, le module s'intègre automatiquement à votre tableau de bord pour afficher les avis en attente et les commentaires signalés, en supposant que vous ayez le module standard "Commentaires sur les produits" de PrestaShop (ou une alternative compatible) installé et actif.

### 2.2 Écrans d'administration dédiés et vues de contrôleur
Ce module n'introduit **pas** de nouveaux écrans d'administration dédiés ou de vues de contrôleur personnalisées. Sa fonctionnalité est intégrée directement au tableau de bord PrestaShop existant.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
|---|---|---|---|
| Page de configuration du module | Mises à jour MyPresta.eu | Activé (Oui) | Active les vérifications automatiques des mises à jour du module depuis MyPresta.eu. |
| Page de configuration du module | Update_ | Laisser par défaut | Paramètre interne pour le mécanisme de mise à jour. |
| Page de configuration du module | Updatev_ | Laisser par défaut | Paramètre interne de version pour les mises à jour. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai installé le module, mais je ne vois aucun commentaire/avis sur mon tableau de bord.**
**R1 :**
*   **Vérifiez le module "Commentaires sur les produits" :** Ce module s'appuie sur le module standard "Commentaires sur les produits" de PrestaShop (ou un module d'avis tiers compatible) pour fonctionner. Assurez-vous que le module "Commentaires sur les produits" est installé, activé et configuré correctement dans votre boutique.
*   **Videz le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" en haut à droite. Parfois, le cache de PrestaShop doit être rafraîchi pour que les nouveaux éléments du tableau de bord apparaissent.
*   **Vérifiez les avis en attente :** Avez-vous réellement des avis en attente de modération ou des commentaires signalés comme abusifs ? Le module n'affichera que le contenu qui nécessite votre attention. S'il n'y a pas de tels éléments, le bloc du tableau de bord peut apparaître vide ou ne pas s'afficher s'il n'y a rien à afficher.

**Q2 : Le bloc du tableau de bord semble étrange ou n'est pas stylisé correctement.**
**R2 :**
*   **Videz le cache du navigateur :** Parfois, votre navigateur web met en cache d'anciens fichiers CSS. Essayez de vider le cache de votre navigateur ou d'ouvrir votre back office dans une fenêtre de navigation privée/incognito.
*   **Vérifiez les conflits de thème :** Bien que rares pour les modules de tableau de bord, un thème d'administration fortement personnalisé pourrait potentiellement entrer en conflit. Si vous suspectez cela, essayez de passer temporairement au thème d'administration PrestaShop par défaut (si possible) pour voir si le problème persiste. Si cela résout le problème, consultez le développeur de votre thème.
*   **Videz le cache de PrestaShop :** Comme mentionné ci-dessus, vider le cache Smarty sous **Paramètres avancés > Performances** peut résoudre les problèmes d'affichage.

**Q3 : Comment traduire le texte du module dans une autre langue ?**
**R3 :**
*   Naviguez vers **International > Traductions** dans votre Back Office PrestaShop.
*   Sélectionnez "Traductions des modules installés" pour le "Type de traduction".
*   Choisissez votre thème (par exemple, "Classic") et la langue que vous souhaitez traduire.
*   Recherchez "Modération des commentaires / avis du tableau de bord" dans la liste, cliquez sur "Modifier", et vous pourrez alors traduire toutes les chaînes de texte disponibles.

**Q4 : J'ai cliqué sur "Configurer" mais je ne vois que les paramètres de mise à jour, pas les outils de modération.**
**R4 :** Le bouton "Configurer" de ce module mène à sa page de paramètres minimaux, principalement pour la gestion des mises à jour. Les outils de modération réels (la liste des commentaires/avis) sont affichés directement sur votre tableau de bord principal PrestaShop, généralement dans l'une des zones du "Tableau de bord". Naviguez vers votre "Tableau de bord" principal (la première page que vous voyez après vous être connecté) pour trouver la sortie du module.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture
Le module "Modération des commentaires / avis du tableau de bord" (`dashcomments`) est un module PrestaShop léger conçu pour étendre le tableau de bord du Back Office. Il utilise le système de hooks de PrestaShop pour injecter un bloc personnalisé dans le tableau de bord, affichant les avis produits en attente et les commentaires signalés. Il n'introduit pas de nouvelles tables de base de données ni de structures `ObjectModel` complexes, s'appuyant plutôt sur les données existantes du module `ps_product_comment`. Sa fonction principale est la présentation et l'interaction avec les données existantes via AJAX.

### 4.2 Contrôleurs (`controllers/`)
Ce module n'inclut **pas** de contrôleurs front-office ou back-office personnalisés. Toutes les interactions sont gérées soit directement au sein de la classe principale du module (`dashcomments.php`), soit via des appels AJAX traités par les méthodes `ajaxProcess` du module.

### 4.3 Classes et modèles principaux (`classes/`)
Ce module ne définit **pas** de classes ou de modèles personnalisés dans le répertoire `classes/`. Il interagit directement avec les fonctionnalités principales de PrestaShop et, implicitement, avec la classe `ProductComment` du module `ps_product_comments` (si installé).

### 4.4 Actifs JavaScript (`views/js/`)

-   **`dashcomments/js/dashcomments.js`**
    *   **Portée :** Back-office (Tableau de bord).
    *   **Objectif :** Gère les interactions AJAX pour la modération des commentaires et des avis directement depuis le widget du tableau de bord.
    *   **Fonctionnalité clé :**
        *   Lie les écouteurs d'événements de clic aux boutons "Approuver", "Désapprouver" et "Supprimer" au sein du widget du tableau de bord.
        *   Envoie des requêtes AJAX aux méthodes `ajaxProcess` du module (par exemple, `ajaxProcessApproveComment`, `ajaxProcessDisapproveComment`, `ajaxProcessDeleteComment`) pour effectuer des actions de modération.
        *   Met à jour le DOM (supprime la ligne de commentaire modérée, met à jour les compteurs) après une réponse AJAX réussie.
        *   Peut inclure une logique pour gérer les actions "signaler comme abusif" si implémentées pour les commentaires eux-mêmes.
        *   Utilise `$.ajax` pour la communication asynchrone.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`dashcomments/css/dashcomments.css`**
    *   **Portée :** Back-office (Tableau de bord).
    *   **Objectif :** Fournit le style pour le widget du tableau de bord qui affiche les commentaires et avis en attente.
    *   **Style clé :**
        *   Styles pour la liste des commentaires, les lignes de commentaires individuelles, les boutons d'action (approuver, désapprouver, supprimer) et potentiellement les compteurs pour les éléments en attente.
        *   Assure l'intégration visuelle du widget avec le thème du back-office de PrestaShop 1.7+/8+.
        *   **Sélecteurs de classe CSS clés :** Les développeurs peuvent inspecter le HTML généré pour des classes spécifiques (par exemple, `.dashcomments-widget`, `.dashcomments-item`, `.dashcomments-actions`) afin de remplacer ou d'étendre le style dans leurs thèmes d'administration personnalisés.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **`dashcomments/dashboardZoneOne.tpl`**
    *   **Portée :** Back-office (Tableau de bord).
    *   **Hook :** `displaydashboardZoneTwo` (ou `dashboardZoneTwo` dans les versions plus anciennes).
    *   **Objectif :** Ce template est responsable du rendu de la structure HTML du widget de modération des commentaires/avis sur le tableau de bord de PrestaShop.
    *   **Contenu :**
        *   Affiche une liste de commentaires produits en attente d'approbation.
        *   Affiche une liste de commentaires produits qui ont été signalés comme abusifs.
        *   Pour chaque commentaire, il affiche généralement le nom du produit, le nom du client, le contenu du commentaire, la note et les boutons d'action (Approuver, Désapprouver, Supprimer).
        *   Inclut la logique pour itérer sur les variables `$pending_comments` et `$reported_comments` passées depuis le module.
        *   Contient les éléments HTML et les attributs de données nécessaires pour que le script `dashcomments.js` attache ses écouteurs d'événements et effectue des actions AJAX.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** : Ce module ne crée aucune table de base de données personnalisée. Il s'appuie sur la table `ps_product_comment` (et les tables associées comme `ps_product_comment_grade`, `ps_product_comment_criterion`) qui sont créées par le module officiel `ps_product_comments`.
-   **Enregistrements de configuration** :
    *   `PS_DASHCOMMENTS_UPDATES` : Stocke l'état des vérifications de mise à jour.
    *   `PS_DASHCOMMENTS_UPDATE_` : Indicateur de mise à jour interne.
    *   `PS_DASHCOMMENTS_UPDATEV_` : Indicateur de version interne pour les mises à jour.

-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
|---|---|---|
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration configure ses ressources média (CSS/JS). | Utilisé pour enregistrer les fichiers `dashcomments.js` et `dashcomments.css` du module pour le tableau de bord du Back Office. |
| `displaydashboardZoneTwo` | Rend le contenu dans la deuxième zone du tableau de bord du Back Office de PrestaShop. | C'est le hook principal utilisé pour afficher le widget de modération des commentaires/avis. |
| `dashboardZoneTwo` | (Hook hérité, similaire à `displaydashboardZoneTwo`) | Fournit une compatibilité pour les versions plus anciennes de PrestaShop ou les mises en page de tableau de bord alternatives pour afficher le widget. |

## 5. Support officiel et mises à jour
Pour le support officiel, les mises à jour du module et toute assistance supplémentaire, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Vous pouvez télécharger les dernières versions du module depuis votre historique de commandes et accéder à nos canaux de support dédiés pour toute question technique ou problème.
