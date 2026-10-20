---
title: "Quantité minimale de produit - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Quantité minimale de produit' par MyPresta.eu."
sidebar:
  label: "Quantité minimale de produit - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Minimal product quantity sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimal-product-quantity.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/minimal-product-quantity/)
>
> ---


# Quantité minimale de produit

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration spéciale du serveur n'est généralement nécessaire.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à la page principale des paramètres du module « Quantité minimale de produit ». C'est ici que vous définissez les règles de base pour les quantités minimales.

La page de configuration est conçue pour être intuitive, vous permettant de définir des quantités minimales pour des produits individuels et des groupes de clients spécifiques.

**Comment définir une quantité minimale pour un produit :**

1.  **Rechercher un produit :**

    *   Vous verrez une barre de recherche ou une liste de produits. Commencez à taper le nom du produit que vous souhaitez configurer. Au fur et à mesure que vous tapez, le module suggérera des produits correspondants.
    *   *Ce que fait ce paramètre :* Vous permet de localiser rapidement le produit spécifique auquel vous souhaitez appliquer une règle de quantité minimale.
    *   *Effet de la modification de ce paramètre :* N/A (fonction de recherche).
    *   *Valeur recommandée :* Tapez le nom exact du produit pour plus de précision.
    *   *Scénario marchand :* Vous souhaitez définir un minimum pour « Grains de café bio (1kg) ». Tapez « Café bio ».
2.  **Sélectionner le produit :**

    *   Cliquez sur le produit souhaité dans les résultats de recherche. Cela l'ajoutera à une liste de produits configurés ci-dessous.
    *   *Ce que fait ce paramètre :* Confirme le produit auquel vous appliquez la règle.
    *   *Effet de la modification de ce paramètre :* Le produit apparaît dans la liste de configuration, prêt pour les paramètres de quantité et de groupe.
    *   *Valeur recommandée :* Sélectionnez le produit correct.
    *   *Scénario marchand :* Après avoir tapé « Café bio », vous cliquez sur « Grains de café bio (1kg) ».
3.  **Définir la quantité minimale :**

    *   À côté du produit sélectionné, il y aura un champ de saisie (par exemple, « Quantité minimale »). Entrez le nombre le plus bas d'unités qu'un client doit acheter pour ce produit spécifique.
    *   *Ce que fait ce paramètre :* Définit le nombre minimal absolu d'unités pour ce produit.
    *   *Effet de la modification de ce paramètre :*
        *   *Si défini à 5 :* Les clients doivent ajouter au moins 5 unités de ce produit à leur panier. S'ils essaient d'en ajouter 1, 2, 3 ou 4, ils recevront un message d'erreur.
        *   *Si défini à 1 (ou comportement par défaut de PrestaShop) :* Aucune quantité minimale spéciale n'est appliquée au-delà du comportement par défaut de PrestaShop.
    *   *Valeur recommandée :* Un nombre supérieur à 1, reflétant vos besoins commerciaux (par exemple, 6, 12, 24).
    *   *Scénario marchand :* Vous vendez des grains de café en vrac. Vous définissez la « Quantité minimale » à 5.
4.  **Sélectionner le groupe de clients (facultatif) :**

    *   Vous verrez probablement une liste déroulante ou une liste de groupes de clients (par exemple, « Visiteur », « Client », « Grossiste »). Vous pouvez sélectionner un ou plusieurs groupes pour lesquels cette quantité minimale s'applique.
    *   *Ce que fait ce paramètre :* Vous permet d'appliquer différentes règles de quantité minimale en fonction du groupe de clients. Si aucun groupe n'est sélectionné, la règle s'applique à tous les clients.
    *   *Effet de la modification de ce paramètre :*
        *   *Lorsque « Grossiste » est sélectionné :* Seuls les clients appartenant au groupe « Grossiste » seront soumis à cette quantité minimale. D'autres groupes pourraient avoir un minimum différent (ou pas de minimum).
        *   *Lorsqu'aucun groupe spécifique n'est sélectionné (ou « Tous les clients » est implicite) :* La quantité minimale s'applique à chaque client, quel que soit son groupe.
    *   *Valeur recommandée :* Sélectionnez des groupes spécifiques si vous avez des stratégies de prix ou de vente différentes pour eux. Sinon, laissez-le pour « Tous les clients ».
    *   *Scénario marchand :* Vous voulez que les grossistes achètent au moins 10 unités, mais les clients réguliers n'ont besoin d'en acheter que 5. Vous créeriez deux règles distinctes pour le même produit, une pour le groupe « Grossiste » avec une quantité de 10, et une autre pour le groupe « Client » avec une quantité de 5.
5.  **Enregistrer les modifications :**

    *   Après avoir configuré le(s) produit(s) et leurs quantités/groupes minimaux, n'oubliez pas de cliquer sur le bouton « Enregistrer » ou « Mettre à jour » pour appliquer vos paramètres.
    *   *Ce que fait ce paramètre :* Persiste vos modifications de configuration dans la base de données.
    *   *Effet de la modification de ce paramètre :* Les nouvelles règles de quantité minimale deviennent actives sur votre front office immédiatement.
    *   *Valeur recommandée :* Toujours enregistrer après avoir effectué des modifications.
    *   *Scénario marchand :* Vous avez configuré tous vos minimums ; maintenant vous cliquez sur « Enregistrer » pour les rendre actifs.

**Paramètres généraux du module (si présents) :**

Bien que la fonction principale soit les minimums par produit, certains modules peuvent inclure des paramètres généraux :

-   **Activer/Désactiver le module :**

    *   *Ce que fait ce paramètre :* Active ou désactive la fonctionnalité complète du module.
    *   *Effet de la modification de ce paramètre :*
        *   *Lorsqu'il est activé :* Les règles de quantité minimale sont appliquées.
        *   *Lorsqu'il est désactivé :* Toutes les règles de quantité minimale sont ignorées et les clients peuvent ajouter n'importe quelle quantité.
    *   *Valeur recommandée :* OUI (activé) une fois configuré.
    *   *Scénario marchand :* Vous testez le module et souhaitez le désactiver temporairement sans perdre vos paramètres.
-   **Type de message d'erreur à afficher (par exemple, Pop-up, En ligne) :**

    *   *Ce que fait ce paramètre :* Contrôle la manière dont le client est informé lorsqu'il tente d'ajouter moins que la quantité minimale.
    *   *Effet de la modification de ce paramètre :*
        *   *Si défini sur Pop-up :* Une fenêtre modale apparaît, interrompant le flux utilisateur, indiquant clairement le problème.
        *   *Si défini sur En ligne :* Un message apparaît directement sur la page produit ou le panier, sans pop-up.
    *   *Valeur recommandée :* Le pop-up est souvent plus efficace pour les erreurs critiques comme les quantités minimales, car il attire l'attention.
    *   *Scénario marchand :* Vous voulez vous assurer que les clients ne manquent pas l'exigence de quantité minimale, vous choisissez donc un pop-up.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Recherche de produit | N/A | Localiser les produits pour appliquer les règles de quantité minimale. |
| Page de configuration du module | Quantité minimale (par produit) | Varie (par exemple, 5, 10) | Définit le nombre le plus bas d'unités qu'un client doit acheter pour ce produit. |
| Page de configuration du module | Groupe de clients (par produit) | Tous les clients | Applique la règle de quantité minimale à des groupes de clients spécifiques ou à tous les clients. |
| Page de configuration du module | Bouton Enregistrer | N/A | Applique toutes les règles de quantité minimale configurées à la boutique. |
| Page de configuration du module | Activer/Désactiver le module | Activé | Active ou désactive globalement la fonctionnalité du module. |
| Page de configuration du module | Type de message d'erreur | Pop-up | Définit la manière dont les erreurs de quantité minimale sont affichées aux clients. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai défini une quantité minimale, mais cela ne fonctionne pas sur ma boutique. Quel est le problème ?**
R :

1.  **Le module est-il activé ?** Vérifiez à nouveau la page de configuration principale pour vous assurer que le module « Quantité minimale de produit » est actif.
2.  **Avez-vous enregistré vos modifications ?** Cliquez toujours sur le bouton « Enregistrer » ou « Mettre à jour » après avoir effectué des modifications de configuration.
3.  **Videz votre cache PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). Parfois, PrestaShop met en cache d'anciens paramètres.
4.  **Vérifiez les conflits de thème :** Si vous avez un thème très personnalisé, il pourrait interférer avec la façon dont le module affiche les messages ou interagit avec le bouton « Ajouter au panier ». Passez temporairement au thème PrestaShop par défaut (Classic ou Hummingbird) pour voir si le problème persiste. Si cela résout le problème, votre thème a besoin d'un ajustement.
5.  **Groupe de clients :** Assurez-vous que le client avec lequel vous testez appartient au groupe pour lequel la quantité minimale est définie. Si aucun groupe n'est spécifié, cela devrait s'appliquer à tous.

**Q2 : La notification pop-up semble étrange ou ne correspond pas au design de ma boutique.**
R : Le module utilise son propre CSS pour la pop-up. Si votre thème a des règles de style très spécifiques, elles pourraient les remplacer ou entrer en conflit.

1.  **Vérifiez les paramètres du module :** Voyez si le module offre des options pour personnaliser l'apparence de la pop-up ou choisir une méthode d'affichage différente (par exemple, message en ligne au lieu de pop-up).
2.  **CSS personnalisé :** Pour les développeurs ou les webmasters, un CSS personnalisé peut être ajouté au fichier `custom.css` de votre thème pour remplacer les styles par défaut du module. (Voir la section 7.5 pour les détails du fichier CSS).

**Q3 : Puis-je définir une quantité minimale pour les déclinaisons de produits (attributs) ?**
R : Le module applique généralement les quantités minimales au niveau du produit. Si vous avez besoin de minimums spécifiques pour les déclinaisons (par exemple, « T-shirt rouge, Taille S » vs « T-shirt bleu, Taille L »), vous devrez vérifier si le module prend explicitement en charge cela dans sa configuration. Sinon, vous définiriez le minimum pour le produit parent, qui s'applique à toute déclinaison de ce produit.

**Q4 : Comment traduire les messages du module dans d'autres langues ?**
R :

1.  Allez dans **International > Traductions** dans votre Back Office PrestaShop.
2.  Sélectionnez « Traductions des modules installés ».
3.  Choisissez votre thème, la langue que vous souhaitez traduire, puis sélectionnez « Quantité minimale de produit » dans la liste des modules.
4.  Vous trouverez toutes les chaînes traduisibles utilisées par le module (par exemple, « Vous devez ajouter au moins X unités de ce produit »). Traduisez-les et enregistrez.

**Q5 : Que se passe-t-il si un client a un produit dans son panier auquel une quantité minimale est ensuite appliquée ?**
R : Lorsque le client visitera son panier ou tentera de passer à la caisse, le module détectera la divergence. Il sera invité à afficher le message d'erreur et empêché de continuer tant qu'il n'aura pas ajusté la quantité pour atteindre le nouveau minimum.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Quantité minimale de produit » (`minqc`) suit une architecture de module PrestaShop standard, exploitant principalement les hooks pour injecter sa logique et ses ressources front-end. Il fonctionne en interceptant les changements de quantité et les ajouts au panier, en validant par rapport aux minimums configurés et en affichant des commentaires à l'utilisateur. La logique principale du module réside dans son fichier `index.php` principal, qui gère l'installation, la désinstallation, la configuration et l'enregistrement des hooks. L'interaction front-end est gérée par une suite de fichiers JavaScript adaptés aux différentes versions et contextes de PrestaShop (page produit, panier, vue rapide).

### 4.2 Contrôleurs (`controllers/`)

Ce module ne semble pas utiliser de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Sa configuration est gérée directement dans la méthode `getContent()` de la classe principale du module, et les interactions front-office sont gérées via JavaScript et des appels AJAX aux fonctionnalités principales de PrestaShop ou au propre `ajax.php` du module (s'il est présent, bien qu'il ne soit pas explicitement répertorié comme un contrôleur dédié, c'est un modèle courant pour les modules de gérer les requêtes AJAX via leur fichier principal ou un simple script).

### 4.3 Classes et modèles principaux (`classes/`)

D'après l'inventaire fourni, ce module ne définit pas de classes `ObjectModel` personnalisées ni d'autres classes PHP complexes dans un répertoire `classes/` dédié. Sa logique est probablement encapsulée dans le fichier `minqc/index.php` principal, interagissant directement avec `Configuration` pour les paramètres et potentiellement `Db` pour le stockage de données personnalisées si les minimums spécifiques aux produits sont stockés en dehors de `ps_configuration`.

### 4.4 Ressources JavaScript (`views/js/`)

Le module utilise intensivement JavaScript pour offrir une expérience utilisateur dynamique et appliquer les règles de quantité en temps réel.

-   `minqc/views/js/minqc.js` :
    *   **Portée :** Probablement un fichier JS principal, potentiellement chargé globalement ou sur plusieurs pages.
    *   **Responsabilité :** Contient des fonctions utilitaires générales, la liaison d'événements pour les éléments courants, et potentiellement la logique principale pour vérifier les quantités minimales avant d'ajouter au panier ou de mettre à jour le panier. Il pourrait gérer l'affichage de la notification pop-up.
    *   **Interactions :** Se lie aux événements `click` sur les boutons « Ajouter au panier », aux événements `change` sur les champs de saisie de quantité, et potentiellement aux événements `prestashop.on` pour les mises à jour du panier via AJAX.
-   `minqc/views/js/minqc-17500.js` :
    *   **Portée :** Front-office, spécifiquement pour PrestaShop 1.7.5.0 et les versions plus récentes (ou des plages de versions similaires).
    *   **Responsabilité :** Contient la logique JavaScript spécifique à la version pour s'adapter aux changements dans la structure du front-office de PrestaShop, le comportement du panier AJAX ou les éléments de la page produit introduits dans ces versions.
    *   **Interactions :** Remplace ou étend `minqc.js` pour les structures DOM et la gestion des événements spécifiques à PrestaShop 1.7+.
-   `minqc/views/js/minqc-admin-product.js` :
    *   **Portée :** Back-office, spécifiquement sur la page d'édition de produit (`AdminProducts`).
    *   **Responsabilité :** Si le module permet de définir des quantités minimales directement sur la page d'édition de produit, ce script gérerait l'interface utilisateur pour cela (par exemple, ajout de champs de saisie, enregistrement des valeurs via AJAX).
    *   **Interactions :** Se lie aux événements sur les éléments du formulaire produit, effectue des appels AJAX pour enregistrer les minimums spécifiques au produit.
-   `minqc/views/js/minqc-cart.js` :
    *   **Portée :** Front-office, spécifiquement sur la page du panier.
    *   **Responsabilité :** Surveille les changements de quantité dans le panier, valide par rapport aux minimums et empêche le passage à la caisse si les règles sont violées. Affiche des messages d'erreur ou des pop-ups sur la page du panier.
    *   **Interactions :** Se lie aux changements de saisie de quantité, aux clics sur le bouton « Passer à la caisse » et potentiellement aux événements `prestashop.on` liés aux mises à jour du panier.
-   `minqc/views/js/minqc-front.js` :
    *   **Portée :** Utilisation générale en front-office.
    *   **Responsabilité :** Pourrait être un script front-end plus générique, gérant potentiellement l'affichage des informations de quantité minimale sur les listes de produits ou d'autres pages non spécifiques aux produits/paniers.
    *   **Interactions :** Manipulation du DOM pour l'affichage des messages, potentiellement des appels AJAX pour la validation.
-   `minqc/views/js/minqc-no-autoadd.js` :
    *   **Portée :** Front-office.
    *   **Responsabilité :** Suggère un comportement spécifique lié à la prévention de l'ajout automatique de produits au panier si les minimums ne sont pas respectés, ou à la gestion des scénarios où un produit pourrait être ajouté automatiquement mais échoue ensuite à la validation.
    *   **Interactions :** Modifie le comportement par défaut du bouton « Ajouter au panier » pour s'assurer que la validation a lieu *avant* que l'article ne soit ajouté.
-   `minqc/views/js/minqc-product-classic.js` :
    *   **Portée :** Front-office, spécifiquement pour les thèmes basés sur le thème PrestaShop Classic (PrestaShop 1.7+).
    *   **Responsabilité :** Adapte l'application et l'affichage de la quantité minimale à la structure DOM et aux événements JavaScript spécifiques à la page produit du thème Classic.
    *   **Interactions :** Se lie au bouton « Ajouter au panier » et aux éléments de saisie de quantité sur la page produit du thème Classic.
-   `minqc/views/js/minqc-product-hummingbird.js` :
    *   **Portée :** Front-office, spécifiquement pour les thèmes basés sur le thème PrestaShop Hummingbird (PrestaShop 8+).
    *   **Responsabilité :** Adapte l'application et l'affichage de la quantité minimale à la structure DOM et aux événements JavaScript spécifiques à la page produit du thème Hummingbird.
    *   **Interactions :** Se lie au bouton « Ajouter au panier » et aux éléments de saisie de quantité sur la page produit du thème Hummingbird.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `minqc/views/css/minqc.css` :
    *   **Portée :** Front-office et potentiellement Back-office pour les éléments d'interface utilisateur spécifiques au module.
    *   **Composants d'interface utilisateur principaux :** Styles pour la notification pop-up (arrière-plan modal, boîte de contenu, bouton de fermeture, texte du message), messages d'erreur en ligne et potentiellement indicateurs visuels sur les pages produits.
    *   **Sélecteurs de classe CSS clés :** Les développeurs peuvent inspecter le HTML de sortie du module pour identifier des classes spécifiques (par exemple, `.minqc-popup`, `.minqc-error-message`, `.minqc-quantity-input-error`) et les remplacer dans le fichier `custom.css` ou `theme.css` de leur thème pour correspondre à l'image de marque de leur boutique.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** : Non explicitement listés, mais il est courant que les modules utilisent `displayHeader` pour JS/CSS, ou `displayProductActions` pour les messages de la page produit.
-   **Templates d'administration (`views/templates/admin/`)** :
    *   `minqc/views/templates/admin/admin.tpl` : Probablement le template de configuration principal du module, rendu par la méthode `getContent()`. Il contiendrait la recherche de produits, la liste des produits configurés et les paramètres généraux.
    *   `minqc/views/templates/admin/admintab.tpl` : Pourrait être un sous-template pour un onglet ou une section spécifique dans la configuration d'administration, ou un template hérité.
    *   `minqc/views/templates/admin/_configure/helpers/list/list_content.tpl` : Cela suggère que le module utilise le `HelperList` de PrestaShop pour afficher la liste des produits avec des quantités minimales configurées dans le back office. Ce template définirait la manière dont chaque ligne de cette liste est rendue.
-   **Templates Ajax (`views/templates/ajax/`)** :
    *   `minqc/views/templates/ajax/minqcErrors.tpl` : Ce template est probablement utilisé pour rendre le contenu HTML de la pop-up d'erreur ou des messages en ligne affichés au client lorsqu'une quantité minimale n'est pas respectée. Il serait chargé via AJAX.
-   **Templates Front-office (`views/templates/front/`)** :
    *   `minqc/views/templates/front/beforeShoppingCart.tpl` : Ce template est probablement accroché à une position avant le contenu principal du panier, potentiellement pour afficher un avertissement ou un résumé lié aux quantités minimales si le panier est invalide.
    *   `minqc/views/templates/front/product-details.tpl` : Ce template serait utilisé pour injecter des informations ou des avertissements de quantité minimale directement dans la page de détails du produit, souvent près du sélecteur de quantité ou du bouton « Ajouter au panier ».
    *   `minqc/views/templates/front/productActions.tpl` : Similaire à `product-details.tpl`, ce template serait accroché au hook `displayProductActions` (ou similaire) pour afficher des messages ou modifier le comportement du bouton « Ajouter au panier » en fonction des règles de quantité minimale.
    *   `minqc/views/templates/front/qv.tpl` : Ce template est spécifiquement destiné à la fonctionnalité de « Vue rapide », injectant des informations ou des avertissements de quantité minimale dans la modale de vue rapide.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    *   Le module stocke probablement sa configuration pour les quantités minimales spécifiques aux produits et les associations de groupes de clients dans la table `ps_configuration` pour les paramètres globaux simples.
    *   Pour les minimums spécifiques aux produits et aux groupes, il est très probable que le module crée sa propre table de base de données personnalisée (par exemple, `ps_minqc_product_quantity`) pour stocker les valeurs `id_product`, `id_customer_group` et `min_quantity`. Cette table serait créée pendant la méthode `install()` et supprimée pendant `uninstall()`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Injecte les fichiers CSS (`minqc.css`) et JavaScript (`minqc.js`, `minqc-front.js`, JS spécifiques à la version comme `minqc-17500.js`, `minqc-product-classic.js`, `minqc-product-hummingbird.js`, `minqc-cart.js`, `minqc-no-autoadd.js`) du module pour la fonctionnalité front-end. |
| `displayProductActions` | Sur la page produit, généralement près du bouton « Ajouter au panier ». | Injecte `productActions.tpl` pour afficher les exigences ou avertissements de quantité minimale directement sur la page produit. |
| `displayProductExtraContent` (ou similaire) | Sur la page produit, pour des blocs de contenu supplémentaires. | Pourrait être utilisé pour afficher `product-details.tpl` ou d'autres informations. |
| `displayShoppingCartFooter` (ou similaire) | En bas du récapitulatif du panier. | Injecte `beforeShoppingCart.tpl` ou similaire pour afficher des avertissements si les articles du panier ne respectent pas les minimums, empêchant le passage à la caisse. |
| `actionCartSave` | Après l'enregistrement ou la mise à jour d'un panier. | Déclenche la logique PHP du module pour revalider toutes les quantités du panier par rapport aux minimums configurés. |
| `actionValidateOrder` | Avant la validation officielle d'une commande. | Vérification finale pour s'assurer que toutes les quantités de produits dans le panier respectent leurs minimums avant que la commande ne soit passée. |
| `actionProductUpdate` / `actionProductAdd` | Lorsqu'un produit est mis à jour ou ajouté dans le Back Office. | Potentiellement utilisé pour mettre à jour ou effacer les données de quantité minimale mises en cache pour ce produit. |
| `displayAdminProductsExtra` | Sur la page d'édition de produit dans le Back Office. | Injecte des éléments d'interface utilisateur (par exemple, via `admintab.tpl` ou `admin.tpl`) pour permettre de définir des quantités minimales spécifiques au produit directement depuis le formulaire produit, en utilisant `minqc-admin-product.js`. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question lié au module « Quantité minimale de produit ».
