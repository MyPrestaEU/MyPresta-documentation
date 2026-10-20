---
title: "Colonne et recherche de numéro de facture dans la liste des commandes - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Colonne et recherche de numéro de facture dans la liste des commandes par MyPresta.eu."
sidebar:
  label: "Colonne et recherche de numéro de facture dans la liste des commandes - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Order List Invoice Column & Search sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-list-invoice-column-search.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/order-list-invoice-column-search/)
>
> ---


# Colonne et recherche de numéro de facture dans la liste des commandes

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune exigence d'hébergement particulière au-delà d'une configuration PrestaShop standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du nom du module « Colonne et recherche de numéro de facture dans la liste des commandes ». Ce module a une configuration très simple et directe, car sa fonctionnalité principale est d'améliorer la liste des commandes existante.

La page de configuration de « Colonne et recherche de numéro de facture dans la liste des commandes » est simple. Elle sert principalement à activer ou désactiver la fonctionnalité du module.

- **Nom du paramètre :** Activer la colonne et la recherche de facture
- **Ce que fait ce paramètre :** Il s'agit de l'interrupteur principal pour activer ou désactiver les fonctionnalités du module. Lorsqu'il est activé, le module ajoutera la colonne « Numéro de facture » à votre liste de commandes et intégrera la fonctionnalité de recherche. Lorsqu'il est désactivé, votre liste de commandes retrouvera son apparence PrestaShop par défaut.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Une nouvelle colonne intitulée « Numéro de facture » apparaîtra dans votre Back Office sous **Commandes > Commandes**. Cette colonne affichera le numéro de facture pour chaque commande (si une facture a été générée). De plus, la barre de recherche de la page Commandes vous permettra désormais de rechercher par numéro de facture.
  - *Lorsqu'il est désactivé (NON) :* La colonne « Numéro de facture » sera supprimée de la liste des commandes, et la possibilité de rechercher par numéro de facture sera désactivée. Votre liste de commandes ressemblera exactement à ce qu'elle était avant l'installation de ce module.
- **Valeur recommandée :** **OUI**. Pour bénéficier des fonctionnalités du module, vous devez l'activer.
- **Scénario / exemple de marchand :** Si vous souhaitez trouver rapidement toutes les commandes liées à une facture spécifique (par exemple, « INV00123 »), vous activeriez ce paramètre. Ensuite, vous naviguerez vers **Commandes > Commandes**, taperez « INV00123 » dans la barre de recherche, et le système filtrerait la liste pour n'afficher que cette commande. Si vous le désactivez, vous devrez cliquer manuellement sur chaque commande pour vérifier son numéro de facture, ce qui est très chronophage.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer la colonne et la recherche de facture | OUI | Active/désactive la colonne de facture et la fonctionnalité de recherche sur la liste des commandes dans le Back Office. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : J'ai activé le module, mais je ne vois pas la colonne « Numéro de facture » ou la recherche ne fonctionne pas.**
R :

1. **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » dans le coin supérieur droit. Parfois, PrestaShop a besoin d'une actualisation du cache pour afficher de nouveaux éléments.
2. **Vérifier le statut du module :** Vérifiez à nouveau que le module est bien « Activé » sur sa page de configuration.
3. **Version de PrestaShop :** Assurez-vous que votre version de PrestaShop est compatible avec le module (1.7.x, 8.x, 9.x).
4. **Cache du navigateur :** Essayez de vider le cache de votre navigateur ou d'utiliser une fenêtre de navigation privée pour exclure les problèmes spécifiques au navigateur.

**Q : Les numéros de facture affichent « N/A » ou sont vides pour certaines commandes.**
R : Cela signifie généralement qu'une facture n'a pas encore été générée pour ces commandes spécifiques dans PrestaShop. Le module n'affiche le numéro de facture que s'il existe dans la base de données de PrestaShop. Vous devrez générer manuellement la facture pour ces commandes via le processus de gestion des commandes standard de PrestaShop.

**Q : Ce module va-t-il ralentir mon Back Office ?**
R : Non, le module est conçu pour être léger et efficace. Il étend principalement une fonctionnalité PrestaShop existante (la liste des commandes) plutôt que d'ajouter de nouveaux processus lourds. Son impact sur les performances devrait être négligeable.

**Q : Puis-je personnaliser la position de la colonne « Numéro de facture » ?**
R : Le module place la colonne dans une position logique au sein de la liste des commandes. La personnalisation directe de l'ordre des colonnes n'est pas une fonctionnalité intégrée de ce module. Pour des modifications de mise en page avancées, vous auriez généralement besoin d'un développement de thème personnalisé ou d'un autre module spécialisé.

**Q : Ce module crée-t-il de nouvelles factures ?**
R : Non, ce module ne génère pas de factures. Il affiche et permet uniquement la recherche par les numéros de facture qui ont déjà été générés par la fonctionnalité principale de PrestaShop.

## 4. Guide du développeur et du webmaster (architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Colonne et recherche de numéro de facture dans la liste des commandes » (`olistinv`) est un module PrestaShop classique qui étend les fonctionnalités de base en se connectant aux points d'affichage et d'action existants dans le Back Office. Il modifie principalement la vue de liste du contrôleur `AdminOrders` pour ajouter une nouvelle colonne et améliore les capacités de recherche sans introduire de nouvelles tables de base de données ou d'interactions complexes avec le front-office. Sa simplicité réside dans l'exploitation du système de hooks de PrestaShop et la surcharge de la logique de template si nécessaire.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur front-office ou back-office personnalisé. Toute sa logique est contenue dans le fichier principal du module, `olistinv/index.php`, et exécutée via des hooks.

### 4.3 Classes et modèles de base (`classes/`)

Ce module ne définit aucune classe personnalisée ou `ObjectModel`. Il interagit directement avec les classes de base et les structures de base de données existantes de PrestaShop.

### 4.4 Assets JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé. La fonctionnalité de recherche est intégrée en modifiant le comportement du formulaire de recherche existant, qui est géré par le JS de base de PrestaShop.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé. La nouvelle colonne héritera du style des tables existantes du Back Office de PrestaShop.

### 4.6 Structure des templates Smarty (`views/templates/`)

Ce module n'inclut aucun fichier de template Smarty personnalisé. Il réalise sa fonctionnalité en injectant dynamiquement du contenu dans les templates PrestaShop existants via des hooks, spécifiquement en modifiant l'affichage de la liste `AdminOrders`.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** : Ce module ne crée aucune nouvelle table de base de données. Il lit à partir de la table `ps_orders` (spécifiquement le champ `invoice_number`) et potentiellement `ps_order_invoice` pour les détails de la facture, et stocke sa configuration dans `ps_configuration`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayAdminOrderListHeader` | Rendu avant l'en-tête du tableau de la liste des commandes dans le Back Office. | Utilisé pour ajouter l'en-tête de colonne « Numéro de facture » à la liste des commandes. |
| `displayAdminOrderList` | Rendu pour chaque ligne (commande) dans le tableau de la liste des commandes dans le Back Office. | Utilisé pour afficher le numéro de facture réel pour chaque commande dans la colonne nouvellement ajoutée. |
| `actionAdminOrdersListingFieldsModifier` | Modifie le tableau de champs utilisé pour construire la requête et l'affichage de la liste des commandes. | Utilisé pour ajouter le champ `invoice_number` à la liste des champs recherchables et affichables pour le contrôleur `AdminOrders`. Ceci est crucial à la fois pour l'affichage de la colonne et l'activation de la recherche. |
| `actionAdminOrdersFilterModifier` | Modifie la requête de filtre pour la liste des commandes. | Utilisé pour étendre la fonctionnalité de recherche afin d'inclure le champ `invoice_number` lorsqu'une requête de recherche est soumise. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Colonne et recherche de numéro de facture dans la liste des commandes », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité du module.
"""
