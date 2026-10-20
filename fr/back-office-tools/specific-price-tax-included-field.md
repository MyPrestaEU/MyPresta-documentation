---
title: "Champ prix spécifique TTC - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Specific price tax included field' par MyPresta.eu."
sidebar:
  label: "Champ prix spécifique TTC - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Specific price tax included field sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/specific-price-tax-included-field.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/specific-price-tax-included-field/)
>
> ---


# Champ prix spécifique TTC

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Specific price tax included field » dans le Gestionnaire de modules. Cela vous mènera à l'écran de configuration principal du module.

#### Paramètres généraux

- **Ce que fait ce paramètre :** Cette section contient généralement les paramètres généraux liés aux mises à jour du module et aux vérifications de version.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Le module vérifiera périodiquement les nouvelles versions disponibles sur MyPresta.eu et vous en informera dans le Back Office. Cela garantit que vous utilisez toujours la version la plus récente, la plus sécurisée et la plus riche en fonctionnalités.
  - *Lorsqu'il est désactivé :* Le module n'effectuera pas de vérifications automatiques des mises à jour. Vous devrez vérifier manuellement les mises à jour en visitant votre compte MyPresta.eu.
- **Valeur recommandée :** **OUI** (ou activé). Garder cette option activée vous assure d'être informé des mises à jour importantes et des corrections de bugs.
- **Scénario / exemple de marchand :** Vous souhaitez être informé si une nouvelle version du module est publiée, incluant des correctifs de compatibilité pour une nouvelle version de PrestaShop ou des améliorations de performance. Garder cette option activée affichera une notification dans votre Back Office.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Vérifications des mises à jour (mypresta\_updates, update\_, updatev\_) | Activé | Vérifie périodiquement les nouvelles versions du module et vous en informe dans le Back Office. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : J'ai installé le module, mais je ne vois pas le nouveau champ « Prix TTC ».**
R : Tout d'abord, assurez-vous que le module est activé dans **Modules > Gestionnaire de modules**. Ensuite, naviguez vers une page produit, allez dans l'onglet « Prix » et cliquez sur « Ajouter un nouveau prix spécifique » ou « Modifier » un existant. Le nouveau champ devrait apparaître dans le formulaire de création/modification de prix spécifique. S'il n'est toujours pas visible, essayez de vider votre cache PrestaShop (**Paramètres avancés > Performances**, puis cliquez sur « Vider le cache »).

**Q : Le prix hors taxes calculé semble incorrect.**
R : Le module s'appuie sur la règle de taxe attribuée au produit.
1. **Vérifiez la règle de taxe du produit :** Allez sur la page du produit, onglet « Prix », et vérifiez que la « Règle de taxe » correcte est sélectionnée pour le produit.
2. **Vérifiez la configuration de la règle de taxe :** Allez dans **International > Taxes > Règles de taxes** et assurez-vous que les taux de taxe définis pour la règle de taxe sélectionnée sont corrects pour vos pays/zones cibles.
3. **Videz le cache :** Après avoir vérifié et éventuellement corrigé les paramètres de taxe, videz votre cache PrestaShop.

**Q : Ce module affecte-t-il les prix spécifiques existants ?**
R : Non, ce module ajoute seulement un nouveau champ de saisie au formulaire de création/modification de prix spécifique. Il n'altère ni ne recalcule aucun prix spécifique créé avant son installation ou en utilisant le champ par défaut « Prix hors taxes ». Il fournit simplement un moyen alternatif de saisir de nouveaux prix spécifiques.

**Q : Ce module fonctionnera-t-il avec mon thème personnalisé ?**
R : Oui, ce module modifie principalement un formulaire standard du Back Office de PrestaShop. Il utilise des hooks PrestaShop standard et du JavaScript pour injecter le nouveau champ. Il est très peu probable qu'il entre en conflit avec les thèmes personnalisés du front-office, car il n'a pas de composants d'affichage front-office.

**Q : Je reçois une erreur après la mise à jour de PrestaShop.**
R : Après toute mise à jour majeure de PrestaShop, il est recommandé de :
1. Vider votre cache PrestaShop (**Paramètres avancés > Performances**).
2. Vérifier si une nouvelle version du module « Specific price tax included field » est disponible dans votre compte MyPresta.eu, car les mises à jour incluent souvent des correctifs de compatibilité.
3. Si le problème persiste, contactez le support MyPresta.eu.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Specific price tax included field » (`sptincl`) est un module PrestaShop 1.7.x léger conçu pour améliorer l'interface de gestion des prix spécifiques dans le Back Office. Il fonctionne principalement en injectant du JavaScript dans le hook `actionAdminControllerSetMedia`, qui modifie ensuite le DOM du formulaire de prix spécifique pour ajouter le champ « Prix TTC » et implémenter la logique de calcul côté client nécessaire. Il n'introduit pas de nouvelles tables de base de données, de contrôleurs ou de logique métier complexe côté serveur au-delà de sa configuration.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur d'administration Front-Office ou Back-Office personnalisé. Toutes ses fonctionnalités sont injectées dans les pages d'administration PrestaShop existantes via des hooks et du JavaScript.

### 4.3 Classes et modèles de base (`classes/`)

Ce module n'introduit aucune classe PHP personnalisée ou définition d'`ObjectModel`. Sa logique principale réside dans le fichier principal du module (`sptincl.php`).

### 4.4 Actifs JavaScript (`views/js/`)

- **`sptincl/views/js/sptincl.js`**
  - **Portée :** Back-office (spécifiquement, le formulaire de création/modification de prix spécifique).
  - **Objectif :** Ce script est responsable de la fonctionnalité principale du module.
    - **Manipulation du DOM :** Il ajoute dynamiquement un nouveau champ de saisie pour le « Prix TTC » au formulaire de prix spécifique. Il modifie également le comportement du champ existant « Prix hors taxes ».
    - **Écouteurs d'événements :** Il attache des écouteurs d'événements (par exemple, `keyup`, `change`) au nouveau champ « Prix TTC » et au champ existant « Prix hors taxes », ainsi qu'au sélecteur de règle de taxe.
    - **Logique de calcul :** Lorsqu'un utilisateur saisit une valeur dans le champ « Prix TTC », ou modifie la règle de taxe, le script calcule la valeur correspondante « Prix hors taxes » en utilisant le taux de taxe sélectionné. Inversement, si le champ « Prix hors taxes » est modifié, il calcule la valeur « Prix TTC ».
    - **AJAX (Implicite) :** Bien qu'il n'effectue pas directement d'appels AJAX, il s'appuie sur les taux de taxe disponibles dans le DOM ou récupérés par les mécanismes existants de PrestaShop pour effectuer ses calculs. Il utilise la fonction `getTaxRate()` (qui peut être une fonction JS globale de PrestaShop ou une fonction personnalisée définie dans le script) pour récupérer le taux de taxe actuel basé sur la règle de taxe sélectionnée.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé. Il s'appuie sur le style par défaut de PrestaShop pour les éléments de formulaire, assurant une intégration transparente avec l'interface utilisateur du Back Office.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Ce module n'utilise pas de fichiers de modèle Smarty personnalisés. Sa configuration est gérée directement dans la méthode `getContent()` de la classe principale du module, et ses modifications front-end sont purement basées sur JavaScript.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** : Ce module ne crée aucune table de base de données personnalisée. Il stocke ses paramètres de configuration (comme `mypresta_updates`, `update_`, `updatev_`) dans la table standard `ps_configuration`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration est initialisé et que ses ressources multimédias (JS/CSS) sont définies. | C'est le hook principal utilisé par le module. Il injecte le fichier JavaScript `sptincl.js` dans le Back Office, ciblant spécifiquement le formulaire de création/modification de prix spécifique. Cela permet au module de modifier le DOM du formulaire et d'ajouter sa logique de calcul côté client. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Specific price tax included field », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
