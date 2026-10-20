---
title: "Customer Grid Pro - colonnes et mise en page de la liste des clients - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Customer Grid Pro - colonnes et mise en page de la liste des clients par MyPresta.eu."
sidebar:
  label: "Customer Grid Pro - colonnes et mise en page de la liste des clients"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Customer Grid Pro - columns & layout of list of customers sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/customer-grid-pro-columns-layout-of-list-of-customers.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/customer-grid-pro-columns-layout-of-list-of-customers/)
>
> ---


# Customer Grid Pro - colonnes et mise en page de la liste des clients

## 1. Exigences et compatibilité
- **Versions de PrestaShop prises en charge** : PrestaShop 9.x, 8.x, 1.7.8.x, 1.7.7.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Après avoir installé le module, cliquez sur "Configurer" pour accéder à ses paramètres. Cette page vous permet de sélectionner les colonnes qui apparaissent dans votre liste de clients et dans quel ordre.

La page de configuration affichera une liste de toutes les colonnes disponibles pour votre grille de clients. Celles-ci incluent les colonnes PrestaShop standard et les nouvelles ajoutées par le module (comme le téléphone, l'adresse, les statistiques de commande).

**Comment utiliser l'interface de configuration :**

1.  **Liste des colonnes disponibles :** Sur le côté gauche, vous verrez une liste de toutes les colonnes qui *peuvent* être affichées.
2.  **Liste des colonnes actives :** Sur le côté droit, vous verrez une liste des colonnes qui sont actuellement *actives* et qui seront affichées dans votre liste de clients.
3.  **Ajouter une colonne :** Pour ajouter une colonne à votre liste de clients, faites-la simplement glisser de la liste "Colonnes disponibles" à gauche et déposez-la dans la liste "Colonnes actives" à droite.
4.  **Supprimer une colonne :** Pour supprimer une colonne de votre liste de clients, faites-la glisser de la liste "Colonnes actives" à droite et déposez-la dans la liste "Colonnes disponibles" à gauche.
5.  **Réorganiser les colonnes :** Dans la liste "Colonnes actives", vous pouvez faire glisser et déposer des colonnes vers le haut ou vers le bas pour modifier leur ordre d'affichage dans votre grille de clients. La colonne en haut de la liste apparaîtra en premier (le plus à gauche) dans votre liste de clients.
6.  **Bouton Enregistrer :** Après avoir effectué des modifications (ajout, suppression ou réorganisation de colonnes), n'oubliez pas de cliquer sur le bouton **"Enregistrer"** en bas de la page pour appliquer votre nouvelle configuration.

**Liste des colonnes disponibles et leur objectif :**

| Nom de la colonne (Exemple) | Ce que fait ce paramètre | Effet de la modification de ce paramètre | Valeur recommandée | Scénario / exemple pour le marchand |
|---|---|---|---|---|
| **ID** | Affiche le numéro d'identification unique de chaque client. | *Si actif :* Affiche l'ID du client. *Si inactif :* Masque la colonne ID. | Actif | Utile pour référencer rapidement les clients par leur ID interne, notamment lors du traitement des tickets de support. |
| **Titre social** | Affiche le titre choisi par le client (par exemple, M., Mme). | *Si actif :* Affiche le titre social. *Si inactif :* Masque la colonne du titre social. | Actif (facultatif) | Bon pour la communication formelle ou si votre entreprise exige des salutations spécifiques. |
| **Prénom** | Affiche le prénom du client. | *Si actif :* Affiche le prénom. *Si inactif :* Masque la colonne du prénom. | Actif | Essentiel pour identifier les clients. |
| **Nom** | Affiche le nom de famille du client. | *Si actif :* Affiche le nom de famille. *Si inactif :* Masque la colonne du nom de famille. | Actif | Essentiel pour identifier les clients. |
| **Adresse e-mail** | Affiche l'adresse e-mail du client. | *Si actif :* Affiche l'adresse e-mail. *Si inactif :* Masque la colonne de l'e-mail. | Actif | Crucial pour contacter les clients et souvent utilisé comme identifiant principal. |
| **Âge** | Affiche l'âge du client (si la date de naissance est fournie). | *Si actif :* Affiche l'âge calculé du client. *Si inactif :* Masque la colonne de l'âge. | Actif (facultatif) | Utile pour la segmentation marketing ou les produits soumis à des restrictions d'âge. |
| **Date d'inscription** | Affiche la date à laquelle le client a enregistré son compte. | *Si actif :* Affiche la date d'inscription. *Si inactif :* Masque la colonne de la date d'inscription. | Actif | Aide à suivre l'acquisition de clients et à identifier les nouveaux clients par rapport aux anciens. |
| **Dernière visite** | Affiche la date de la dernière connexion/visite du client. | *Si actif :* Affiche la date de la dernière visite. *Si inactif :* Masque la colonne de la dernière visite. | Actif (facultatif) | Utile pour identifier les clients actifs par rapport aux inactifs pour les campagnes de réengagement. |
| **Total des commandes** | Affiche le nombre total de commandes passées par le client. | *Si actif :* Affiche un décompte de toutes les commandes. *Si inactif :* Masque cette colonne. | Actif | Excellent pour identifier les acheteurs fréquents ou les clients ayant plusieurs achats. |
| **Total dépensé** | Affiche la valeur monétaire totale dépensée par le client sur toutes les commandes. | *Si actif :* Affiche la somme de tous les totaux de commande. *Si inactif :* Masque cette colonne. | Actif | Critique pour identifier les clients à forte valeur (VIP) et pour la gestion des comptes B2B. |
| **Numéro de téléphone** | Affiche le numéro de téléphone principal du client (à partir de son adresse par défaut). | *Si actif :* Affiche le numéro de téléphone. *Si inactif :* Masque cette colonne. | Actif | Essentiel pour le contact direct, en particulier pour les problèmes de livraison ou les demandes urgentes. |
| **Téléphone portable** | Affiche le numéro de téléphone portable du client (à partir de son adresse par défaut). | *Si actif :* Affiche le numéro de téléphone portable. *Si inactif :* Masque cette colonne. | Actif | Fournit une méthode de contact alternative, souvent préférée pour une communication rapide. |
| **Adresse 1** | Affiche la première ligne de l'adresse par défaut du client. | *Si actif :* Affiche la ligne d'adresse. *Si inactif :* Masque cette colonne. | Actif (facultatif) | Utile pour une référence rapide de l'emplacement sans ouvrir l'adresse complète. |
| **Adresse 2** | Affiche la deuxième ligne de l'adresse par défaut du client. | *Si actif :* Affiche la ligne d'adresse. *Si inactif :* Masque cette colonne. | Actif (facultatif) | Fournit des détails d'adresse supplémentaires. |
| **Code postal** | Affiche le code postal de l'adresse par défaut du client. | *Si actif :* Affiche le code postal. *Si inactif :* Masque cette colonne. | Actif (facultatif) | Utile pour la segmentation géographique ou la planification des livraisons. |
| **Ville** | Affiche la ville de l'adresse par défaut du client. | *Si actif :* Affiche la ville. *Si inactif :* Masque cette colonne. | Actif (facultatif) | Utile pour la segmentation géographique ou le marketing local. |
| **État** | Affiche l'état/la province de l'adresse par défaut du client. | *Si actif :* Affiche l'état/la province. *Si inactif :* Masque cette colonne. | Actif (facultatif) | Important pour le ciblage régional et l'expédition. |
| **Pays** | Affiche le pays de l'adresse par défaut du client. | *Si actif :* Affiche le pays. *Si inactif :* Masque cette colonne. | Actif (facultatif) | Essentiel pour les magasins internationaux et la logistique d'expédition. |
| **Newsletter** | Indique si le client est abonné à votre newsletter. | *Si actif :* Affiche un indicateur "Oui" ou "Non". *Si inactif :* Masque cette colonne. | Actif | Aide à identifier les opportunités marketing et à gérer les listes d'e-mails. |
| **Opt-in** | Indique si le client a accepté de recevoir des offres de partenaires. | *Si actif :* Affiche un indicateur "Oui" ou "Non". *Si inactif :* Masque cette colonne. | Actif (facultatif) | Utile pour gérer les efforts de marketing des partenaires. |
| **Actif** | Indique si le compte client est actuellement actif. | *Si actif :* Affiche un indicateur "Oui" ou "Non". *Si inactif :* Masque cette colonne. | Actif | Aide à identifier les comptes désactivés. |
| **Groupe par défaut** | Affiche le groupe de clients principal du client. | *Si actif :* Affiche le nom du groupe par défaut. *Si inactif :* Masque cette colonne. | Actif | Crucial pour les magasins B2B ou les magasins avec des prix/accès échelonnés. |
| **Nom de la boutique** | Affiche le nom de la boutique si le mode multi-boutiques est utilisé. | *Si actif :* Affiche le nom de la boutique. *Si inactif :* Masque cette colonne. | Actif (si multi-boutiques) | Essentiel pour les environnements multi-boutiques afin de différencier les clients par boutique. |
| **Montant dû** | Affiche tout solde impayé dû par le client (le cas échéant, par exemple, pour le crédit B2B). | *Si actif :* Affiche le montant dû. *Si inactif :* Masque cette colonne. | Actif (le cas échéant) | Important pour la gestion du crédit B2B. |
| **Autoriser les précommandes** | Indique si le client est autorisé à passer des précommandes. | *Si actif :* Affiche "Oui" ou "Non". *Si inactif :* Masque cette colonne. | Actif (le cas échéant) | Pertinent pour la gestion des stocks et les accords clients spécifiques. |

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
|---|---|---|---|
| Page de configuration du module | Ordre des colonnes par glisser-déposer | Défini par l'utilisateur | Contrôle l'ordre visuel des colonnes dans la liste des clients du Back Office. |
| Page de configuration du module | Liste des colonnes actives | Défini par l'utilisateur | Détermine quelles colonnes sont visibles dans la liste des clients du Back Office. |
| Page de configuration du module | Liste des colonnes disponibles | Défini par l'utilisateur | Liste toutes les colonnes possibles qui peuvent être ajoutées à la liste des clients. |
| Page de configuration du module | Bouton Enregistrer | Cliquer après les modifications | Applique toutes les modifications de visibilité et d'ordre des colonnes à la grille des clients. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai configuré les colonnes, mais je ne vois aucun changement dans ma liste de clients.**
R :
1.  **Avez-vous cliqué sur "Enregistrer" ?** Après avoir effectué des modifications sur la page de configuration du module, vous devez cliquer sur le bouton "Enregistrer".
2.  **Videz le cache de PrestaShop :** Parfois, le cache de PrestaShop peut empêcher les modifications d'apparaître immédiatement. Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions antérieures).
3.  **Videz le cache du navigateur :** Essayez de vider le cache de votre navigateur ou d'ouvrir le Back Office dans une fenêtre de navigation privée/incognito.

**Q : Certaines colonnes que je m'attends à voir (comme "Nom de l'entreprise" ou "Montant dû") ne sont pas disponibles dans la liste.**
R :
1.  **Compatibilité du module :** Assurez-vous d'avoir téléchargé et installé la version correcte du module pour votre version spécifique de PrestaShop.
2.  **Fonctionnalités de PrestaShop :** Certaines colonnes (par exemple, "Montant dû") ne sont pertinentes que si vous avez activé des fonctionnalités spécifiques de PrestaShop (comme le mode B2B) ou installé d'autres modules qui fournissent ces données. Si les données n'existent pas dans votre boutique, le module pourrait ne pas être en mesure de les afficher.

**Q : La fonctionnalité de glisser-déposer ne fonctionne pas sur la page de configuration.**
R :
1.  **Compatibilité du navigateur :** Assurez-vous d'utiliser un navigateur web moderne (Chrome, Firefox, Edge, Safari) et que JavaScript est activé.
2.  **Modules en conflit :** Rarement, un autre module ou une modification de thème personnalisée pourrait interférer avec JavaScript. Essayez de désactiver temporairement d'autres modules pour voir si le problème se résout. Si c'est le cas, contactez le support MyPresta.eu.

**Q : Puis-je traduire les nouveaux noms de colonnes dans d'autres langues ?**
R : Oui, le système de traduction de PrestaShop devrait vous permettre de traduire les chaînes du module.
1.  Allez dans **International > Traductions**.
2.  Sélectionnez "Traductions des modules installés".
3.  Choisissez votre thème, votre langue, puis sélectionnez "Customer Grid Pro".
4.  Vous devriez y trouver les chaînes pour les noms de colonnes à traduire.

**Q : Ce module ralentira-t-il mon Back Office ?**
R : Le module est optimisé pour s'intégrer à la grille client principale de PrestaShop. Bien que l'ajout de nombreuses colonnes complexes (en particulier celles nécessitant des calculs comme "Total dépensé") puisse légèrement augmenter le temps de chargement par rapport à une liste basique, l'impact est généralement négligeable sur un serveur bien configuré. Les avantages en termes d'efficacité l'emportent généralement sur les différences de performances mineures.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture
Le module `Customer Grid Pro` étend principalement la fonctionnalité de la liste des clients du Back Office PrestaShop. Il y parvient en se connectant aux hooks `actionCustomerGridDefinitionModifier` et `actionCustomerGridDataModifier`, qui font partie du nouveau système de grille de PrestaShop introduit dans la version 1.7.x. Cela permet au module d'ajouter, de supprimer et de réorganiser dynamiquement les colonnes et leurs données associées sans modifier directement les fichiers du cœur. La configuration est gérée via une méthode `getContent()` standard dans le fichier principal du module, utilisant un JavaScript et un CSS personnalisés pour l'interface de glisser-déposer.

### 4.2 Contrôleurs (`controllers/`)
Ce module n'introduit aucun contrôleur Front-Office ou Back-Office personnalisé. Toute la configuration est gérée dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)
Ce module ne définit aucune classe personnalisée ou entité `ObjectModel` dans un répertoire `classes/`. Toute la logique est autonome dans le fichier principal du module `index.php`.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`mycustomergridpro/views/js/customer_grid_admin.js`**
    *   **Portée :** Back-office (spécifiquement la page de configuration du module).
    *   **Objectif :** Ce script fournit la fonctionnalité de glisser-déposer pour l'interface de sélection des colonnes sur la page de configuration du module. Il utilise le widget `sortable` de jQuery UI pour permettre la réorganisation et le déplacement d'éléments entre les listes "Colonnes disponibles" et "Colonnes actives".
    *   **Fonctionnalité clé :**
        *   Initialise deux listes triables : `#available_columns` et `#active_columns`.
        *   Configure `connectWith` pour permettre le déplacement d'éléments entre ces deux listes.
        *   Gère l'événement `update` pour les listes triables afin de potentiellement déclencher l'enregistrement ou la mise à jour des champs d'entrée masqués (bien que l'enregistrement réel soit géré par la soumission du formulaire).
        *   S'assure que l'ordre des éléments dans la liste `#active_columns` est correctement soumis avec le formulaire.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`mycustomergridpro/views/css/customer_grid_admin.css`**
    *   **Portée :** Back-office (spécifiquement la page de configuration du module).
    *   **Objectif :** Fournit le style pour l'interface de sélection de colonnes par glisser-déposer.
    *   **Style clé :**
        *   Styles pour les conteneurs de liste de colonnes (`#available_columns`, `#active_columns`).
        *   Styles pour les éléments de colonne individuels (`.column-item`).
        *   Indices visuels pour les opérations de glisser-déposer (par exemple, `ui-sortable-helper`, `ui-sortable-placeholder`).
        *   Garantit que les deux listes de colonnes sont affichées côte à côte ou dans une disposition claire pour la convivialité.

### 4.6 Structure du template Smarty (`views/templates/`)
Ce module n'utilise pas de fichiers `.tpl` séparés pour sa configuration ou son affichage front-office. L'intégralité du formulaire de configuration HTML est générée directement dans la méthode `getContent()` du fichier principal du module `index.php`.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    *   Ce module ne crée aucune table SQL personnalisée.
    *   Il stocke sa configuration (la liste des colonnes actives et leur ordre) dans la table `ps_configuration` en utilisant des clés comme `MYCUSTOMERGRIDPRO_ACTIVE_COLUMNS`. Cette configuration est stockée sous forme de tableau sérialisé ou de chaîne JSON.

-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
|---|---|---|
| `actionCustomerGridDefinitionModifier` | Exécuté lorsque la définition de la grille client est en cours de construction dans le Back Office. | Permet au module d'ajouter de nouvelles colonnes (par exemple, téléphone, total des commandes, total dépensé, champs d'adresse) et de supprimer des colonnes existantes de la définition de la grille. Ce hook reçoit l'objet `GridDefinition`. |
| `actionCustomerGridDataModifier` | Exécuté après que les données de la grille client ont été récupérées, mais avant leur rendu. | Permet au module de remplir les données pour les colonnes personnalisées ajoutées via `actionCustomerGridDefinitionModifier`. Ce hook reçoit l'objet `QueryResult`, permettant la modification des lignes de données. |
| `displayBackOfficeHeader` | Exécuté dans la section `<head>` des pages du Back Office. | Utilisé pour inclure les fichiers CSS (`customer_grid_admin.css`) et JavaScript (`customer_grid_admin.js`) personnalisés du module sur la page de configuration du module, activant l'interface de glisser-déposer. |

## 5. Support officiel et mises à jour
Pour les dernières mises à jour, corrections de bugs et support officiel du module "Customer Grid Pro - colonnes et mise en page de la liste des clients", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour aider les marchands et les développeurs avec tout problème ou question lié à la fonctionnalité et à l'intégration du module.
