---
title: "Hooks Manager - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Hooks Manager par MyPresta.eu."
sidebar:
  label: "Hooks Manager - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Hooks Manager sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/hooks-manager.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/hooks-manager/)
>
> ---


# Hooks Manager

## 1. Exigences et Compatibilité

- **Versions PrestaShop Supportées** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'Hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Parcours de Configuration Complet (Chaque Paramètre Groupé par Écran)

### 2.1 Page de Configuration du Module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur "Configurer" à côté du module Hooks Manager. Vous verrez une liste de tous les hooks personnalisés que vous avez créés, ainsi que des options pour en ajouter de nouveaux.

#### Ajout d'un Nouveau Hook Personnalisé :

En haut de la page de configuration, vous trouverez les champs pour créer un nouveau hook.

- **Nom du Hook :**

  - **Ce que fait ce paramètre :** C'est le nom technique unique de votre nouveau hook. Il doit commencer par `display` (par exemple, `displayMyCustomHook`, `displayProductExtraInfo`). Ce nom est ce que vous utiliserez plus tard dans les fichiers `.tpl` de votre thème pour "appeler" le hook.
  - **Effet de la modification de ce paramètre :** Ce nom est crucial pour les développeurs afin de placer le hook dans votre thème. Le modifier après la création nécessiterait de mettre à jour les fichiers de votre thème.
  - **Valeur recommandée :** Utilisez des noms descriptifs en camelCase commençant par `display`. Exemple : `displayProductBelowAddToCart`, `displayHomepagePromoBanner`.
  - **Scénario / exemple marchand :** Vous souhaitez ajouter une bannière sous le bouton "Ajouter au panier" sur les pages produit. Vous pourriez nommer le hook `displayProductBelowAddToCart`.
- **Titre du Hook :**

  - **Ce que fait ce paramètre :** C'est un titre convivial et lisible pour votre hook qui apparaîtra dans votre Back Office PrestaShop (par exemple, lorsque vous allez dans **Design > Positions** pour attribuer des modules aux hooks).
  - **Effet de la modification de ce paramètre :** Facilite l'identification de votre hook personnalisé parmi les nombreux hooks standard du Back Office.
  - **Valeur recommandée :** Un titre clair et descriptif. Exemple : "Page Produit - Sous Ajouter au Panier", "Page d'Accueil - Bannière Promo Supérieure".
  - **Scénario / exemple marchand :** Pour le hook `displayProductBelowAddToCart`, vous définiriez le titre sur "Page Produit - Sous Ajouter au Panier".
- **Description du Hook :**

  - **Ce que fait ce paramètre :** Une description facultative et plus longue pour fournir plus de contexte sur l'objectif ou l'emplacement prévu du hook. Ceci est également pour un usage interne dans le Back Office.
  - **Effet de la modification de ce paramètre :** Vous aide, vous et votre équipe, à vous souvenir du cas d'utilisation spécifique de chaque hook personnalisé.
  - **Valeur recommandée :** Expliquez brièvement où le hook est destiné à être placé et quel type de contenu il doit contenir. Exemple : "Destiné aux badges de confiance ou aux petits messages promotionnels directement sous le bouton d'ajout au panier."
  - **Scénario / exemple marchand :** Pour le hook `displayProductBelowAddToCart`, vous pourriez ajouter "Utiliser pour de petits badges de confiance ou un message de livraison gratuite."
- **Visibilité :**

  - **Ce que fait ce paramètre :** Cela détermine si le hook est visible dans la liste des hooks disponibles lorsque vous allez dans **Design > Positions** dans votre Back Office PrestaShop.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Le hook apparaîtra dans la liste, vous permettant d'y attribuer facilement des modules.
    - *Lorsqu'désactivé :* Le hook existera toujours et fonctionnera s'il est appelé dans votre thème, mais il n'apparaîtra pas dans la liste "Design > Positions", ce qui rendra plus difficile la gestion des modules pour celui-ci.
  - **Valeur recommandée :** **Activé (Oui)**, sauf si vous avez une raison très spécifique de le masquer.
  - **Scénario / exemple marchand :** Vous avez créé un nouveau hook et souhaitez commencer immédiatement à lui attribuer des modules. Gardez-le activé.

#### Gestion des Hooks Personnalisés Existants :

Sous la section "Ajouter un Nouveau Hook", vous verrez un tableau listant tous les hooks personnalisés que vous avez créés.

- **Interrupteur Activé / Désactivé (pour chaque hook) :**

  - **Ce que fait ce paramètre :** Cet interrupteur vous permet d'activer ou de désactiver un hook personnalisé individuel.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Le hook est actif, et tous les modules qui lui sont attribués afficheront leur contenu lorsque le hook est appelé dans votre thème.
    - *Lorsqu'désactivé :* Le hook est inactif. Même s'il est appelé dans votre thème, il n'affichera aucun contenu des modules qui lui sont attribués. C'est un moyen doux de masquer temporairement du contenu sans désactiver les modules.
  - **Valeur recommandée :** **Activé** pour les hooks que vous souhaitez utiliser, **Désactivé** pour les hooks que vous souhaitez masquer temporairement.
  - **Scénario / exemple marchand :** Vous avez une bannière promotionnelle saisonnière placée via un hook personnalisé. Lorsque la promotion se termine, vous pouvez désactiver le hook pour masquer la bannière sans supprimer le module.
- **Modifier en direct (pour chaque hook) :**

  - **Ce que fait ce paramètre :** C'est un lien rapide vers la page "Design > Positions", filtré pour afficher uniquement le hook personnalisé sélectionné.
  - **Effet de la modification de ce paramètre :** Cliquer sur ce bouton vous amène directement à la page où vous pouvez "greffer" (attribuer) d'autres modules à ce hook personnalisé spécifique.
  - **Valeur recommandée :** Utilisez ce bouton chaque fois que vous souhaitez attribuer un module à votre hook personnalisé nouvellement créé.
  - **Scénario / exemple marchand :** Vous venez de créer `displayProductBelowAddToCart` et souhaitez maintenant y attribuer votre module "Badges de Confiance". Cliquez sur "Modifier en direct" à côté de `displayProductBelowAddToCart`.

#### Autres Clés de Configuration (Internes) :

Vous pourriez voir `mypresta_updates`, `update_`, `updatev_` dans la configuration interne du module. Celles-ci sont généralement liées aux mises à jour du module et aux vérifications de licence par MyPresta.eu et ne nécessitent pas d'interaction du marchand.

### 2.2 Tableau de Référence Rapide de la Configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et Impact |
| --- | --- | --- | --- |
| Configuration du Module | Nom du Hook | Descriptif, préfixe `display` | Identifiant technique unique pour le hook. Utilisé dans les fichiers de thème. |
| Configuration du Module | Titre du Hook | Clair, lisible par l'homme | Apparaît dans Design > Positions pour une identification facile. |
| Configuration du Module | Description du Hook | Facultatif, informatif | Fournit un contexte pour l'objectif du hook. |
| Configuration du Module | Visibilité | Activé (Oui) | Rend le hook visible dans Design > Positions pour l'attribution de modules. |
| Configuration du Module | Activé / Désactivé (par hook) | Activé | Active/désactive la capacité du hook personnalisé à afficher du contenu. |
| Configuration du Module | Modifier en direct (par hook) | N/A (Bouton d'action) | Lien direct vers Design > Positions pour attribuer des modules au hook. |

## 3. Dépannage Marchand et Questions Fréquemment Posées (FAQ)

**Q : J'ai créé un hook et attribué un module, mais rien n'apparaît sur ma boutique. Qu'est-ce qui ne va pas ?**
R : C'est le problème le plus courant. Le module Hooks Manager *crée* le hook, mais vous (ou votre webmaster) devez toujours *placer* ce hook dans les fichiers `.tpl` de votre thème.
- **Solution :** Vous devez modifier les fichiers de votre thème (par exemple, `product.tpl`, `index.tpl`, `header.tpl`, `footer.tpl`) et insérer l'extrait de code suivant à l'endroit où vous souhaitez que le hook apparaisse : `{$hook_name}`. Remplacez `hook_name` par le nom réel de votre hook (par exemple, `{$hook_displayProductBelowAddToCart}`).
- **Vérifiez également :**
1. Le hook est-il "Activé" dans la configuration de Hooks Manager ?
2. Le module que vous essayez d'afficher est-il réellement "greffé" à votre hook personnalisé sous **Design > Positions** ?
3. Avez-vous vidé votre cache PrestaShop (**Paramètres Avancés > Performances**) ?

**Q : Puis-je utiliser le même hook personnalisé plusieurs fois à différents endroits ?**
R : Oui, vous le pouvez. Si vous placez `{$hook_displayMyCustomHook}` dans `product.tpl` et aussi dans `category.tpl`, tout module attribué à `displayMyCustomHook` s'affichera aux deux emplacements. C'est puissant pour afficher un contenu cohérent sur différents types de pages.

**Q : Mon hook personnalisé apparaît, mais le style est incorrect. Que puis-je faire ?**
R : Le module Hooks Manager ne fournit que l'"emplacement". Le style du contenu dans cet emplacement est déterminé par le module que vous y avez placé et le CSS de votre thème.
- **Solution :** Vous devrez peut-être ajouter du CSS personnalisé à votre thème pour styliser le contenu rendu par le module dans votre hook personnalisé. Votre webmaster peut vous aider.

**Q : Je souhaite supprimer un hook personnalisé. Comment le faire en toute sécurité ?**
R : Dans la configuration de Hooks Manager, vous verrez un bouton "Supprimer" à côté de chaque hook personnalisé.
- **Important :** Avant de supprimer, assurez-vous d'avoir supprimé tous les appels à ce hook (`{$hook_yourCustomHookName}`) des fichiers `.tpl` de votre thème. Si vous supprimez le hook mais laissez l'appel dans votre thème, cela pourrait provoquer une erreur mineure ou simplement ne rien afficher. De plus, désactivez tous les modules qui y sont liés via **Design > Positions**.

**Q : Ce module affecte-t-il les performances de ma boutique ?**
R : Le module lui-même est très léger. L'ajout de plus de hooks et l'attribution de plus de modules *peuvent* augmenter progressivement le temps de chargement des pages, mais cela est vrai pour tout contenu supplémentaire sur votre page, quelle que soit la façon dont il est greffé. L'impact est généralement négligeable, sauf si vous ajoutez des dizaines de modules complexes à une seule page.

## 4. Guide Développeur et Webmaster (Architecture Technique et Carte du Code)

Cette section est strictement destinée aux développeurs, webmasters de boutiques et agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'Architecture

Le module Hooks Manager est un module PrestaShop simple conçu pour étendre le mécanisme de greffe de base. Il exploite principalement la classe `Module` de PrestaShop et la table `Configuration` pour gérer les définitions de hooks personnalisés. Il n'introduit pas de modèles MVC complexes ni de tables de base de données personnalisées, mais manipule plutôt les tables `ps_hook` et `ps_hook_module` indirectement via l'API de PrestaShop. La fonctionnalité principale du module réside dans son fichier PHP principal, `hooksmanager.php`, qui gère l'installation, la désinstallation et l'interface de configuration du Back Office.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. Tout le rendu front-office est géré par la méthode standard `Hook::exec()` de PrestaShop lorsque le hook personnalisé est appelé dans un fichier `.tpl`.
- **Contrôleurs Admin Back-Office** : Aucun. Toute l'administration est gérée directement dans la méthode `getContent()` du fichier `hooksmanager.php`.

### 4.3 Classes et Modèles de Base (`classes/`)

- Aucune classe personnalisée ou définition `ObjectModel` n'est présente dans le répertoire `classes/`. Le module interagit directement avec les classes `Hook` et `Module` de base de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

- Aucun fichier JavaScript personnalisé n'est présent dans le module. La configuration du Back Office repose sur les éléments de formulaire PrestaShop standard et potentiellement jQuery s'il est inclus globalement par PrestaShop.

### 4.5 Feuilles de Style CSS (`views/css/`)

- Aucun fichier CSS personnalisé n'est présent dans le module. La configuration du Back Office utilise le style du thème d'administration par défaut de PrestaShop.

### 4.6 Structure des Templates Smarty (`views/templates/`)

- Aucun fichier de template Smarty personnalisé n'est présent dans le module. L'interface de configuration entière est rendue directement dans la méthode `getContent()` de `hooksmanager.php` en utilisant du HTML brut et les classes d'aide de PrestaShop.

### 4.7 Schéma de Base de Données et Carte des Hooks

- **Tables de Base de Données** :

  - Le module ne crée pas ses propres tables de base de données personnalisées.
  - Il interagit principalement avec les tables PrestaShop de base suivantes :
    - `ps_hook` : Stocke les définitions de tous les hooks, y compris ceux créés par ce module.
    - `ps_hook_lang` : Stocke les titres et descriptions traduisibles pour les hooks.
    - `ps_module_hook` : Lie les modules aux hooks, définissant quel module est affiché dans quel hook.
    - `ps_configuration` : Stocke les valeurs de configuration spécifiques au module (par exemple, `mypresta_updates`, `update_`, `updatev_` pour la gestion interne du module).
- **Table des Hooks Enregistrés** :
  Le module lui-même n'enregistre aucun hook pour afficher son propre contenu. Son but est de *créer* de nouveaux hooks que d'autres modules pourront utiliser.

  La fonctionnalité principale du module implique :

  - `install()` :
    - Enregistre le module sur `displayAdminProductsExtra` (ou similaire, bien que non explicitement indiqué dans le dossier, c'est courant pour les outils d'administration d'afficher un lien).
    - Crée un nouvel onglet dans le Back Office (le cas échéant, bien que non explicitement indiqué pour ce module, c'est courant pour les outils d'administration).
    - Définit les valeurs de configuration par défaut dans `ps_configuration`.
  - `uninstall()` :
    - Supprime tous les hooks personnalisés créés par le module de `ps_hook` et `ps_hook_lang`.
    - Supprime les entrées `ps_module_hook` associées.
    - Nettoie les valeurs de configuration de `ps_configuration`.
  - `getContent()` :
    - Gère la soumission du formulaire de configuration du Back Office.
    - Traite la création, la mise à jour et la suppression des hooks personnalisés.
    - Rend le HTML pour la page de configuration, listant les hooks existants et fournissant le formulaire pour en ajouter de nouveaux.
    - Utilise les méthodes `Hook::add()` et `Hook::remove()` pour gérer les entrées de hook dans la base de données.

  **Note du Développeur sur l'Utilisation des Hooks Personnalisés :**
  Pour utiliser un hook personnalisé créé par ce module, un développeur doit insérer manuellement la variable Smarty `{$hook_YOUR_CUSTOM_HOOK_NAME}` dans le fichier `.tpl` souhaité au sein du thème PrestaShop actif. Par exemple, si un hook nommé `displayProductBelowAddToCart` est créé, le développeur ajouterait `{$hook_displayProductBelowAddToCart}` à `themes/your_theme/templates/catalog/_partials/product-details.tpl` ou `product.tpl` à l'emplacement souhaité. La méthode `Hook::exec()` de base de PrestaShop gérera alors le rendu des modules attribués à ce hook personnalisé.

## 5. Support Officiel et Mises à Jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module Hooks Manager, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à assurer le fonctionnement optimal de votre module et à vous aider pour toute question technique que vous pourriez avoir.
"""
