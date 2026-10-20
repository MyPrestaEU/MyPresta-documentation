---
title: "Optimisation de la Base de Données - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop d'Optimisation de la Base de Données par MyPresta.eu."
sidebar:
  label: "Optimisation de la Base de Données - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Database Optimization sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/database-optimization.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/database-optimization/)
>
> ---


# Optimisation de la Base de Données

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration serveur spéciale n'est requise.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal et unique du module Optimisation de la Base de Données. Vous le trouverez en naviguant vers **Modules > Gestionnaire de modules** et en cliquant sur "Configurer" à côté de "Optimisation de la Base de Données".

#### **Paniers indésirables**

-   **Ce que fait ce paramètre :** Cette option contrôle si le module supprimera les anciens paniers abandonnés de votre base de données. Ce sont des paniers que les clients ont commencés mais pour lesquels ils n'ont jamais terminé de commande.
-   **Effet de la modification de ce paramètre :**
    -   *Si défini sur "Oui" :* Le module supprimera périodiquement ces anciens paniers incomplets. Cela réduit la taille de votre base de données et peut améliorer les performances, car PrestaShop n'a pas à gérer les données de milliers de paniers abandonnés.
    -   *Si défini sur "Non" :* Les anciens paniers resteront dans votre base de données. Bien que cela conserve les données historiques, cela peut contribuer à l'encombrement de la base de données au fil du temps.
-   **Valeur recommandée :** **Oui**. À moins que vous n'ayez une raison commerciale spécifique de conserver toutes les données des paniers abandonnés (par exemple, pour une analyse historique très approfondie), les nettoyer est bénéfique pour les performances.
-   **Scénario / exemple pour le marchand :** Si vous remarquez que votre base de données devient très volumineuse et que votre boutique ralentit, l'activation de cette option est un gain rapide pour supprimer une source courante de données inutiles.

#### **Connexions**

-   **Ce que fait ce paramètre :** Cette option contrôle si le module supprimera les anciens journaux de connexion de votre base de données. PrestaShop enregistre chaque connexion de visiteur à votre boutique, ce qui peut s'accumuler rapidement.
-   **Effet de la modification de ce paramètre :**
    -   *Si défini sur "Oui" :* Le module supprimera périodiquement les anciens journaux de connexion. Cela réduit considérablement la taille de la base de données, car les journaux de connexion peuvent être l'une des plus grandes tables d'une boutique très fréquentée.
    -   *Si défini sur "Non" :* Les journaux de connexion seront conservés indéfiniment, ce qui peut entraîner une base de données très volumineuse.
-   **Valeur recommandée :** **Oui**. Pour la plupart des boutiques, les journaux de connexion très anciens ne sont pas critiques pour les opérations quotidiennes et peuvent être supprimés en toute sécurité pour améliorer les performances.
-   **Scénario / exemple pour le marchand :** Si votre boutique a un volume de trafic élevé, les journaux de connexion peuvent croître extrêmement rapidement. L'activation de cette option aide à empêcher votre base de données de devenir excessivement volumineuse et lente.

#### **Pages de connexion**

-   **Ce que fait ce paramètre :** Cette option cible spécifiquement les journaux de connexion liés aux pages individuelles visitées. Elle fonctionne en conjonction avec le paramètre "Connexions".
-   **Effet de la modification de ce paramètre :**
    -   *Si défini sur "Oui" :* Si "Connexions" est également "Oui", le module supprimera les anciens journaux détaillant les pages spécifiques que les visiteurs ont consultées.
    -   *Si défini sur "Non" :* Même si "Connexions" est "Oui", le module conservera les journaux de connexion spécifiques aux pages.
-   **Valeur recommandée :** **Oui**. Similaire aux connexions générales, les journaux spécifiques aux pages peuvent être très nombreux et ne sont souvent pas nécessaires pour une analyse à long terme si vous utilisez des outils d'analyse externes comme Google Analytics.
-   **Scénario / exemple pour le marchand :** Si vous comptez sur Google Analytics pour les statistiques de pages vues, vous n'avez probablement pas besoin que PrestaShop stocke ces données granulaires indéfiniment, ce qui rend leur nettoyage sûr.

#### **Source des connexions**

-   **Ce que fait ce paramètre :** Cette option cible spécifiquement les journaux de connexion liés à la source du visiteur (par exemple, direct, moteur de recherche, référence). Elle fonctionne en conjonction avec le paramètre "Connexions".
-   **Effet de la modification de ce paramètre :**
    -   *Si défini sur "Oui" :* Si "Connexions" est également "Oui", le module supprimera les anciens journaux détaillant d'où provenaient les visiteurs.
    -   *Si défini sur "Non" :* Même si "Connexions" est "Oui", le module conservera les journaux de connexion spécifiques à la source.
-   **Valeur recommandée :** **Oui**. Comme d'autres données de connexion, cela peut souvent être géré par des outils d'analyse externes.
-   **Scénario / exemple pour le marchand :** Si votre équipe marketing utilise des outils comme Google Analytics ou d'autres systèmes CRM pour suivre les sources de trafic, les journaux internes de PrestaShop pourraient être redondants et peuvent être nettoyés pour économiser de l'espace dans la base de données.

#### **Invités**

-   **Ce que fait ce paramètre :** Cette option contrôle si le module supprimera les anciens comptes invités inactifs de votre base de données. Ce sont des comptes créés pour les visiteurs qui ont commencé une commande en tant qu'invité mais ne l'ont jamais terminée, ou qui ont simplement navigué sans s'inscrire.
-   **Effet de la modification de ce paramètre :**
    -   *Si défini sur "Oui" :* Le module supprimera périodiquement ces anciens comptes invités. Cela aide à maintenir votre base de données clients propre et axée sur les utilisateurs actifs ou enregistrés.
    -   *Si défini sur "Non" :* Les anciens comptes invités resteront dans votre base de données indéfiniment.
-   **Valeur recommandée :** **Oui**. À moins que vous n'ayez un besoin spécifique de conserver chaque enregistrement d'invité, les nettoyer aide à maintenir une base de données ordonnée.
-   **Scénario / exemple pour le marchand :** Si votre boutique a de nombreux visiteurs qui naviguent mais ne s'inscrivent pas ou ne finalisent pas leurs achats, la table des invités peut croître considérablement. Les nettoyer aide à maintenir vos données clients gérables.

#### **Vérifier les mises à jour**

-   **Ce que fait ce paramètre :** Ce paramètre contrôle si le module vérifiera automatiquement les nouvelles versions et mises à jour disponibles sur MyPresta.eu.
-   **Effet de la modification de ce paramètre :**
    -   *Si défini sur "Activer" :* Le module se connectera périodiquement à MyPresta.eu pour voir si une version plus récente est disponible. Si c'est le cas, vous recevrez une notification dans votre Back Office PrestaShop.
    -   *Si défini sur "Désactiver" :* Le module ne vérifiera pas les mises à jour. Vous devrez vérifier manuellement votre compte MyPresta.eu pour les nouvelles versions.
-   **Valeur recommandée :** **Activer**. Cela garantit que vous êtes toujours informé des mises à jour disponibles, qui incluent souvent des corrections de bugs, des améliorations de performances et de nouvelles fonctionnalités.
-   **Scénario / exemple pour le marchand :** Vous voulez vous assurer que vos modules sont toujours à jour pour la sécurité et les performances. L'activation de cette option fournit des notifications pratiques.

#### **Notifications de mises à jour**

-   **Ce que fait ce paramètre :** Ce paramètre contrôle si vous recevez des notifications dans votre Back Office PrestaShop lorsqu'une mise à jour est disponible (si "Vérifier les mises à jour" est activé).
-   **Effet de la modification de ce paramètre :**
    -   *Si défini sur "Activer" :* Vous verrez une notification dans votre Back Office lorsqu'une nouvelle version du module est détectée.
    -   *Si défini sur "Désactiver" :* Même si "Vérifier les mises à jour" est activé et qu'une mise à jour est disponible, vous ne recevrez pas de notification visible dans le Back Office.
-   **Valeur recommandée :** **Activer**. Cela fonctionne de concert avec "Vérifier les mises à jour" pour vous tenir informé.
-   **Scénario / exemple pour le marchand :** Vous voulez être immédiatement alerté lorsqu'une mise à jour est prête afin de pouvoir planifier son installation, garantissant ainsi que votre boutique bénéficie des dernières améliorations.

#### **Page du module**

-   **Ce que fait ce paramètre :** Ce paramètre est probablement une option d'affichage pour la propre page ou les informations du module dans le Back Office. (Basé sur la structure typique des modules MyPresta.eu, cela pourrait contrôler un lien ou un élément d'affichage spécifique lié au module lui-même).
-   **Effet de la modification de ce paramètre :**
    -   *Si défini sur "Activer" :* Affiche probablement un lien ou une section liée aux informations du module ou à d'autres modules MyPresta.eu.
    -   *Si défini sur "Désactiver" :* Ce lien ou cette section sera masqué.
-   **Valeur recommandée :** **Activer**. Il fournit généralement un accès rapide au support ou à d'autres ressources utiles.
-   **Scénario / exemple pour le marchand :** Vous souhaitez un accès facile aux ressources MyPresta.eu directement depuis la page de configuration de votre module.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Paniers indésirables | Oui | Supprime les anciens paniers abandonnés pour réduire la taille de la base de données et améliorer les performances. |
| Configuration du module | Connexions | Oui | Supprime les anciens journaux de connexion des visiteurs pour réduire considérablement la taille de la base de données. |
| Configuration du module | Pages de connexion | Oui | Supprime les anciens journaux des pages spécifiques visitées par les connexions. |
| Configuration du module | Source des connexions | Oui | Supprime les anciens journaux des sources de trafic pour les connexions. |
| Configuration du module | Invités | Oui | Supprime les anciens comptes invités inactifs pour maintenir les données clients propres. |
| Configuration du module | Vérifier les mises à jour | Activer | Vérifie automatiquement les mises à jour du module sur MyPresta.eu. |
| Configuration du module | Notifications de mises à jour | Activer | Affiche les notifications du Back Office lorsque des mises à jour du module sont disponibles. |
| Configuration du module | Page du module | Activer | Contrôle l'affichage des liens/informations liés au module sur la page de configuration. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Après avoir activé le module, ma boutique ne semble pas plus rapide. Pourquoi ?**
R : L'optimisation de la base de données est une pièce du puzzle de la performance. Bien qu'elle nettoie les données inutiles, d'autres facteurs comme les ressources du serveur, l'optimisation des images, les modules lourds ou les thèmes personnalisés non optimisés peuvent toujours ralentir votre boutique. Assurez-vous également d'avoir vidé votre cache PrestaShop (Paramètres avancés > Performances) après la configuration.

**Q : Ce module supprimera-t-il des données clients ou des commandes importantes ?**
R : Non. Ce module est spécifiquement conçu pour cibler les données *indésirables* et *inactives* : paniers abandonnés, anciens journaux de connexion et comptes invités qui n'ont jamais été convertis. Il ne touche pas aux commandes terminées, aux comptes clients actifs, aux données produits ou à d'autres informations critiques de la boutique.

**Q : À quelle fréquence le module nettoie-t-il la base de données ? Est-ce automatique ?**
R : Le module effectue ses opérations de nettoyage lorsque sa configuration est enregistrée ou lorsque certaines tâches d'arrière-plan sont déclenchées par PrestaShop. Ce n'est pas un nettoyeur continu en temps réel. Le principal avantage provient de la suppression des anciennes données accumulées. Pour un nettoyage continu et planifié, vous pourriez avoir besoin de le combiner avec une tâche cron qui déclenche périodiquement la logique de nettoyage du module (bien que ce module se concentre principalement sur le nettoyage ponctuel ou lors de l'enregistrement).

**Q : J'ai désactivé "Vérifier les mises à jour" et "Notifications de mises à jour" mais maintenant je veux être informé des mises à jour. Comment les réactiver ?**
R : Retournez simplement à la page de configuration du module (Modules > Gestionnaire de modules > Configurer Optimisation de la Base de Données) et définissez "Vérifier les mises à jour" et "Notifications de mises à jour" sur "Activer". Enregistrez vos modifications, et le module reprendra la vérification et la notification des nouvelles versions.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module Optimisation de la Base de Données est un module PrestaShop simple principalement conçu pour exécuter des opérations de nettoyage de base de données. Il suit la structure standard des modules PrestaShop, tirant parti de la classe `Module` et de ses méthodes `install()` et `uninstall()` pour l'installation et la désinstallation. Sa fonctionnalité principale réside dans la méthode `getContent()`, qui gère le formulaire de configuration du Back Office et déclenche la logique d'optimisation de la base de données lors de la soumission du formulaire. Il n'introduit pas de contrôleurs, de modèles ou d'actifs front-office personnalisés, ce qui en fait un utilitaire léger et ciblé.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Aucun. Toutes les opérations sont gérées dans le Back Office ou via la classe principale du module.
-   **Contrôleurs d'administration Back-Office** : Aucun. La configuration est gérée directement dans la méthode `getContent()` du fichier `dboptimization.php`.

### 4.3 Classes et modèles principaux (`classes/`)

-   **Classe principale du module** : `dboptimization/dboptimization.php`
    -   **Nom de la classe** : `DbOptimization`
    -   **Classe parente** : `Module`
    -   **Responsabilité** :
        -   Gère l'installation (`install()`) et la désinstallation (`uninstall()`) du module.
        -   Gère l'affichage et la soumission du formulaire de configuration du Back Office (`getContent()`).
        -   Contient la logique principale pour le nettoyage de la base de données basée sur les options configurées.
        -   Enregistre et désenregistre les hooks (bien que ce module utilise principalement `displayBackOfficeHeader` pour les vérifications de mise à jour, et non l'affichage front-office).
        -   Gère les valeurs de configuration à l'aide de `Configuration::get()` et `Configuration::updateValue()`.
        -   Inclut la logique de vérification des mises à jour (`checkforupdates()`) et l'affichage des notifications.

### 4.4 Actifs JavaScript (`views/js/`)

-   Aucun. Le module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

-   Aucun. Le module n'inclut aucun fichier CSS personnalisé.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   Aucun. Le module rend son formulaire de configuration directement dans la méthode `getContent()` à l'aide de `HelperForm` de PrestaShop (ou d'une logique de rendu interne similaire), plutôt que de fichiers `.tpl` externes.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :

    -   Le module ne crée aucune table de base de données personnalisée.
    -   Il interagit avec les tables PrestaShop existantes, principalement :
        -   `ps_cart` : Pour les "Paniers indésirables".
        -   `ps_connections` : Pour les "Connexions".
        -   `ps_connections_page` : Pour les "Pages de connexion".
        -   `ps_connections_source` : Pour les "Sources de connexion".
        -   `ps_guest` : Pour les "Invités".
    -   Les valeurs de configuration sont stockées dans la table `ps_configuration` :
        -   `dbopt_cart`
        -   `dbopt_connections`
        -   `dbopt_connections_page`
        -   `dbopt_connections_source`
        -   `dbopt_guest`
        -   `update_dboptimization` (pour l l'horodatage de la vérification des mises à jour)
        -   `mypresta_updates` (paramètre global de notification de mise à jour)
        -   `dbopt_check_updates`
        -   `dbopt_updates_notifications`
        -   `dbopt_module_page`
-   **Table des hooks enregistrés** :

| Nom du hook | Fichier / Méthode | Moment d'exécution | Objectif technique |
| --- | --- | --- | --- |
| `displayBackOfficeHeader` | `dboptimization.php` | Rendu dans l'en-tête des pages du Back Office. | Utilisé par le module pour injecter des notifications de mise à jour si `dbopt_check_updates` et `dbopt_updates_notifications` sont activés. |
| `actionAdminControllerSetMedia` | `dboptimization.php` | Exécuté lorsqu'un contrôleur d'administration définit ses médias (CSS/JS). | Potentiellement utilisé pour les vérifications de mise à jour ou pour s'assurer que tous les actifs nécessaires (s'ils existaient) sont chargés dans l'administration. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et un support complet pour le module Optimisation de la Base de Données, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support dédiée est disponible pour aider les marchands et les développeurs avec toutes questions ou problèmes liés à la fonctionnalité et à l'intégration du module.
