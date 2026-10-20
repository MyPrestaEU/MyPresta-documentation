---
title: "Ajouter une commande dans le back office + frais de contre-remboursement - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Ajouter une commande dans le back office + frais de contre-remboursement par MyPresta.eu."
sidebar:
  label: "Ajouter une commande dans le back office + frais de contre-remboursement - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Add order in back office + cod fee sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/add-order-in-back-office-cod-fee.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/add-order-in-back-office-cod-fee/)
>
> ---


# Ajouter une commande dans le back office + frais de contre-remboursement

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).
- **Module prérequis** : Ce module nécessite l'installation et la configuration d'un module de paiement « Contre-remboursement avec frais » sur votre boutique. Ce module *étend* la fonctionnalité d'un tel module de paiement au sein du Back Office.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ce module possède une page de configuration très simple. Sa fonction principale est d'activer ou de désactiver la fonctionnalité principale du module.

**Accès :** Back Office > Modules > Gestionnaire de modules > Rechercher « Ajouter une commande dans le back office + frais de contre-remboursement » > Cliquer sur « Configurer »

#### **Activer / Désactiver la fonctionnalité du module**

- **Ce que fait ce paramètre :** Il s'agit d'un interrupteur à bascule standard qui contrôle si la fonctionnalité du module est active ou inactive. Lorsqu'il est activé, le module ajoutera automatiquement les frais de contre-remboursement aux commandes créées manuellement dans le Back Office. Lorsqu'il est désactivé, cette fonctionnalité cessera.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Le module surveillera activement le processus de création de commande du Back Office. Si vous sélectionnez un mode de paiement « Contre-remboursement avec frais » lors de la création d'une commande, les frais associés seront automatiquement calculés et ajoutés au total de la commande.
  - *Lorsqu'il est désactivé (NON) :* Le module n'interférera pas avec le processus de création de commande du Back Office. Si vous sélectionnez un mode de paiement « Contre-remboursement avec frais », les frais ne seront *pas* ajoutés automatiquement, et vous devrez ajuster manuellement le total de la commande si vous souhaitez les inclure.
- **Valeur recommandée :** **OUI**. Pour bénéficier de l'objectif principal du module d'automatisation de l'inclusion des frais de contre-remboursement, il doit être activé.
- **Scénario / exemple de marchand :** Vous prenez une commande par téléphone d'un client qui souhaite payer par contre-remboursement. Vous allez dans Back Office > Commandes > Ajouter une nouvelle commande. Après avoir ajouté les produits et sélectionné le client, vous choisissez votre mode de paiement « Contre-remboursement avec frais ». Si ce module est activé, les frais de contre-remboursement apparaîtront instantanément dans le récapitulatif de la commande, garantissant que le client est facturé correctement. S'il est désactivé, les frais seraient manquants, ce qui pourrait entraîner un total de commande incorrect.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer / Désactiver le module | OUI | Contrôle si le module ajoute automatiquement les frais de contre-remboursement aux commandes créées manuellement dans le Back Office. |

## 3. Dépannage marchand et Foire aux questions (FAQ)

**Q : J'ai installé le module, mais les frais de contre-remboursement n'apparaissent pas lorsque je crée une commande dans le Back Office.**
R :

1. **Vérifier l'état du module :** Allez dans Modules > Gestionnaire de modules et assurez-vous que « Ajouter une commande dans le back office + frais de contre-remboursement » est installé et **activé**.
2. **Vérifier les prérequis :** Ce module *nécessite* qu'un module de paiement « Contre-remboursement avec frais » distinct soit installé et configuré. Assurez-vous d'avoir un tel module et qu'il est correctement configuré avec ses frais. Ce module *étend* cette fonctionnalité, il ne fournit pas le mécanisme de frais de contre-remboursement lui-même.
3. **Vider le cache :** Parfois, le cache de PrestaShop peut empêcher l'apparition immédiate de nouvelles fonctionnalités de module. Allez dans Paramètres avancés > Performances, et cliquez sur « Vider le cache » en haut à droite.
4. **Vérifier le mode de paiement :** Assurez-vous de sélectionner le mode de paiement *spécifique* « Contre-remboursement avec frais » que votre autre module fournit, et non une option générique « Contre-remboursement » sans frais.

**Q : Ce module affectera-t-il les commandes passées par les clients sur le front-office de ma boutique ?**
R : Non, ce module n'affecte que le processus de création de commandes *manuellement* dans le Back Office de PrestaShop. Il n'altère pas la façon dont les clients passent des commandes ou la façon dont les frais sont calculés lors du processus de paiement front-end.

**Q : Que se passe-t-il si j'ai plusieurs modules « Contre-remboursement avec frais » ?**
R : Ce module est conçu pour s'intégrer à la manière standard dont PrestaShop gère les modules de paiement et leurs frais associés. Il devrait fonctionner avec tout module « Contre-remboursement avec frais » qui enregistre correctement son calcul de frais dans le cadre de paiement de PrestaShop. Si vous rencontrez des problèmes, veuillez contacter le support MyPresta.eu.

**Q : Ce module crée-t-il l'option de paiement « Contre-remboursement avec frais » lui-même ?**
R : Non, il ne le fait pas. Ce module est une *amélioration* pour un module de paiement « Contre-remboursement avec frais » existant. Vous devez avoir un module de paiement distinct installé qui fournit le mode de paiement contre-remboursement réel et sa configuration de frais.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Ajouter une commande dans le back office + frais de contre-remboursement » est un module PrestaShop léger principalement conçu pour étendre la fonctionnalité de `AdminOrdersController`. Il atteint son objectif en s'accrochant à des actions spécifiques dans le processus de création de commande du Back Office, en particulier lorsqu'un mode de paiement est sélectionné ou mis à jour. Sa logique principale réside dans le fichier principal du module, tirant parti du système de hooks de PrestaShop pour modifier le comportement existant sans modification directe des fichiers du cœur. Il repose sur la présence d'un module de paiement « Contre-remboursement avec frais » distinct pour fournir la logique de calcul des frais réelle.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur Front-Office ou Back-Office personnalisé. Sa fonctionnalité est injectée dans le `AdminOrdersController` existant via des hooks.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée ni aucune instance de `ObjectModel`. Toute la logique est contenue dans le fichier principal du module.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé. La fonctionnalité est gérée côté serveur.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Ce module n'inclut aucun fichier de modèle Smarty personnalisé. Sa configuration est gérée par la méthode standard `getContent()`, qui utilise généralement les formulaires d'aide de PrestaShop.

### 4.7 Schéma de base de données et carte des hooks

**Tables de base de données** :
Ce module ne crée aucune table de base de données personnalisée. Il stocke sa configuration (par exemple, état activé/désactivé) dans la table standard `ps_configuration`, en utilisant une clé comme `ADDORDERINBACKOFFICECODFEE_ENABLED`.

**Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses ressources multimédias. | Utilisé pour potentiellement injecter du JS/CSS si nécessaire, bien que ce module ne l'utilise pas à cette fin. C'est un hook courant pour les modifications côté administration. |
| `actionAdminOrdersControllerSaveAfter` | Exécuté après l'enregistrement d'une commande dans `AdminOrdersController`. | C'est le hook principal utilisé par le module. Il permet au module d'inspecter la commande nouvellement enregistrée, de vérifier le mode de paiement sélectionné, et si c'est un contre-remboursement avec frais, d'appliquer les frais. |
| `displayAdminOrder` | Exécuté sur la page de détail de la commande dans le Back Office. | Pourrait être utilisé pour afficher des informations supplémentaires relatives aux frais de contre-remboursement sur la vue de la commande, bien que la fonction principale du module soit d'*ajouter* les frais, pas seulement de les afficher. |

**Logique clé dans `add-order-in-back-office-cod-fee.php` :**

La fonctionnalité principale du module est probablement implémentée dans la méthode `hookActionAdminOrdersControllerSaveAfter`. Cette méthode :

1. Récupérerait l'objet `Order` qui vient d'être enregistré.
2. Identifierait le `PaymentModule` utilisé pour la commande.
3. Vérifierait si le module de paiement sélectionné est de type « Contre-remboursement avec frais » (cela implique généralement de vérifier le nom du module ou une propriété/méthode spécifique qu'il expose).
4. Si c'est le cas, il appellerait alors une méthode sur ce module de paiement (ou calculerait directement en fonction de sa configuration) pour obtenir les frais de contre-remboursement.
5. Enfin, il mettrait à jour le total de la commande, ajouterait un nouveau détail `OrderInvoice` (ou modifierait un existant) pour refléter les frais de contre-remboursement, et persisterait ces modifications dans la base de données. Cela pourrait impliquer la création d'une nouvelle entrée `OrderPayment` ou l'ajustement des champs `total_paid_tax_incl` et `total_paid_tax_excl` de l'objet `Order`.

Les développeurs doivent être conscients que ce module repose fortement sur la structure interne et le comportement du module de paiement « Contre-remboursement avec frais » avec lequel il interagit. Tout module de paiement contre-remboursement personnalisé pourrait nécessiter des ajustements ou des vérifications de compatibilité spécifiques.

## 5. Support officiel et mises à jour

Pour le support officiel, les mises à jour et des informations supplémentaires concernant le module « Ajouter une commande dans le back office + frais de contre-remboursement », veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/) ou contacter directement le support MyPresta.eu.
