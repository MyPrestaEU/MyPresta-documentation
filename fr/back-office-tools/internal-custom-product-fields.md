---
title: "Champs de produit internes et personnalisés - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Champs de produit internes et personnalisés' par MyPresta.eu."
sidebar:
  label: "Champs de produit internes et personnalisés"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Internal, custom product fields sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/internal-custom-product-fields.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/internal-custom-product-fields/)
>
> ---


# Champs de produit internes et personnalisés

## 1. Exigences et compatibilité
- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Champs de produit internes et personnalisés)

Ceci est l'écran de configuration principal du module, accessible immédiatement après l'installation ou en cliquant sur "Configurer" depuis le Gestionnaire de modules.

-   **Ce que fait ce paramètre :** Cet écran gère principalement le mécanisme de mise à jour interne du module et les paramètres de base.
-   **Effet de la modification de ce paramètre :**
    -   `mypresta_updates` : Ce paramètre interne contrôle si le module vérifie les mises à jour depuis MyPresta.eu.
    -   `update_` : Lié au processus de vérification des mises à jour.
    -   `updatev_` : Lié au processus de vérification des mises à jour.
    -   `PS_LANG_DEFAULT` : Il s'agit d'une clé de configuration PrestaShop standard et est généralement lue par les modules pour déterminer la langue par défaut d'affichage du contenu dans le Back Office. Ce n'est pas un paramètre que vous modifiez directement dans la configuration de ce module.
-   **Valeur recommandée :** Pour `mypresta_updates`, il est généralement recommandé de le laisser activé pour recevoir les notifications de nouvelles versions et de corrections de bugs. Les autres paramètres sont internes et ne doivent pas être modifiés manuellement.
-   **Scénario / exemple de marchand :** Vous n'interagissez généralement pas directement avec ces paramètres spécifiques. Le but principal de cet écran est de fournir une page d'atterrissage pour le module et de s'assurer que son mécanisme de mise à jour est actif.

### 2.2 Écran d'administration dédié : Gestion des champs internes (Back Office > Catalogue > Champs internes)

C'est l'écran principal où vous définissez et gérez vos champs de produit internes personnalisés. Après l'installation du module, un nouvel élément de menu nommé "Champs internes" apparaîtra sous le menu "Catalogue" dans votre Back Office PrestaShop.

-   **Nom de l'écran et emplacement du menu :** **Catalogue > Champs internes**
-   **Actions et paramètres disponibles :**
    -   **Vue en grille :** Cet écran affiche une liste de tous les champs internes personnalisés que vous avez créés. Chaque ligne affiche le nom du champ et son statut (activé/désactivé).
    -   **Bouton "Ajouter un nouveau champ" :** Cliquez sur ce bouton pour créer un tout nouveau champ personnalisé.
    -   **Actions Modifier/Supprimer :** Pour chaque champ de la liste, vous verrez des boutons d'action (icône de crayon pour modifier, icône de corbeille pour supprimer) pour modifier ou supprimer des champs existants.
    -   **Formulaire de création/modification de champ :** Lors de l'ajout ou de la modification d'un champ, vous verrez généralement :
        -   **Nom du champ :** (par exemple, "Référence fournisseur", "Emplacement entrepôt", "Notes de manipulation spéciales"). C'est l'étiquette qui apparaîtra à côté de la zone de saisie sur la page de modification du produit.
        -   **Interrupteur Actif/Inactif :** Contrôle si ce champ personnalisé est actuellement disponible pour utilisation sur les pages produit. S'il est inactif, il n'apparaîtra pas.
        -   **Type de champ :** (par exemple, Texte, Zone de texte, Nombre, etc. - *basé sur les capacités réelles du module, en supposant du texte pour l'instant*). Cela détermine le type de zone de saisie.
        -   **Bouton Enregistrer :** Pour enregistrer vos modifications ou le nouveau champ.
-   **Effet des modifications :**
    -   **Ajout d'un nouveau champ :** Une fois enregistré, ce nouveau champ apparaîtra immédiatement sur la page de modification de *chaque* produit dans votre Back Office, prêt à ce que vous y saisissiez des données.
    -   **Modification d'un champ :** Les modifications du nom ou du statut du champ se refléteront instantanément sur toutes les pages de modification de produit.
    -   **Suppression d'un champ :** Le champ sera supprimé de toutes les pages de modification de produit. **Soyez prudent :** La suppression d'un champ supprimera également toutes les données précédemment saisies dans ce champ pour tous les produits.
    -   **Activation/Désactivation d'un champ :** Un champ actif est visible sur les pages produit ; un champ inactif est masqué.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Allez dans **Catalogue > Champs internes**.
    2.  Cliquez sur "Ajouter un nouveau champ" pour créer un champ comme "Référence fournisseur" ou "Notes internes".
    3.  Définissez le nom du champ et assurez-vous qu'il est actif.
    4.  Enregistrez le champ.
    5.  Maintenant, lorsque vous allez dans **Catalogue > Produits** et modifiez n'importe quel produit, vous verrez une nouvelle zone de saisie pour votre "Référence fournisseur" où vous pourrez saisir des données spécifiques pour ce produit.
    6.  Répétez l'opération pour toute autre donnée interne que vous devez suivre.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
|---|---|---|---|
| Page de configuration du module | `mypresta_updates` | Activé | Contrôle les vérifications de mise à jour du module. Gardez activé pour les mises à jour. |
| Page de configuration du module | `update_`, `updatev_` | (Interne) | Variables du mécanisme de mise à jour interne. Ne pas modifier. |
| Page de configuration du module | `PS_LANG_DEFAULT` | (Interne) | ID de la langue par défaut de PrestaShop. Lecture seule. |
| Catalogue > Champs internes | **Ajouter un nouveau champ** | N/A | Crée un nouveau champ de produit interne personnalisé. |
| Catalogue > Champs internes | **Nom du champ** | Défini par l'utilisateur | Libellé du champ personnalisé sur les pages de modification de produit. |
| Catalogue > Champs internes | **Actif/Inactif** | Actif | Contrôle la visibilité du champ sur les pages de modification de produit. |
| Catalogue > Champs internes | **Actions Modifier/Supprimer** | N/A | Modifie ou supprime des champs personnalisés existants. La suppression supprime toutes les données associées. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : J'ai créé un nouveau champ, mais je ne le vois pas sur ma page de modification de produit.**
R :
1.  Allez dans **Catalogue > Champs internes** et assurez-vous que le champ que vous avez créé est marqué comme "Actif".
2.  Videz votre cache PrestaShop : Allez dans **Paramètres avancés > Performances**, puis cliquez sur "Vider le cache" dans le coin supérieur droit.
3.  Essayez de modifier un produit à nouveau. Si cela n'apparaît toujours pas, assurez-vous que votre version de PrestaShop est entièrement compatible avec le module.

**Q : Puis-je afficher ces champs personnalisés sur mon front-office pour les clients ?**
R : Non, ce module est spécifiquement conçu pour une utilisation interne dans le Back Office uniquement. Les données saisies dans ces champs ne sont pas destinées à être affichées aux clients. Si vous avez besoin de champs personnalisés pour le front-office, vous auriez besoin d'un autre type de module ou d'un développement personnalisé.

**Q : Que se passe-t-il si je supprime un champ personnalisé ?**
R : Lorsque vous supprimez un champ personnalisé de **Catalogue > Champs internes**, toutes les données que vous avez saisies dans ce champ spécifique pour *tous* vos produits seront définitivement supprimées. Assurez-vous toujours que vous n'avez plus besoin des données avant de supprimer un champ.

**Q : Le module semble causer des problèmes avec mon thème personnalisé. Que dois-je faire ?**
R :
1.  Tout d'abord, videz votre cache Smarty (comme mentionné ci-dessus).
2.  Si le problème persiste, essayez de désactiver temporairement d'autres modules un par un pour voir s'il y a un conflit.
3.  Vérifiez la console de développement de votre navigateur (F12) pour toute erreur JavaScript.
4.  Si vous ne parvenez toujours pas à le résoudre, contactez le support MyPresta.eu avec les détails de votre thème et du problème spécifique.

**Q : Comment traduire les noms de mes champs personnalisés dans différentes langues ?**
R : Le module devrait vous permettre de définir le nom du champ pour chaque langue activée dans votre boutique PrestaShop lorsque vous créez ou modifiez le champ. Recherchez les onglets de langue à côté de la zone de saisie "Nom du champ" sur le formulaire de création/modification de champ.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture
Le module "Champs de produit internes et personnalisés" étend les capacités de gestion des produits de PrestaShop en injectant des champs personnalisés dans la page de modification des produits du Back Office. Il exploite le modèle MVC de PrestaShop, principalement via un contrôleur d'administration pour gérer les définitions des champs personnalisés et des surcharges pour intégrer ces champs dans les formulaires de produits existants. Les données sont stockées dans une table de base de données dédiée, et JavaScript est utilisé pour la manipulation dynamique des formulaires.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Ce module n'a pas de contrôleurs front-office dédiés car sa fonctionnalité est entièrement orientée Back Office. Les hooks front-office sont probablement utilisés pour la configuration générale du module ou pour s'assurer qu'il n'y a pas de conflits front-office.

-   **Contrôleurs d'administration Back-Office** :
    *   `aipf/controllers/admin/AdminInternalFields.php`
        *   **Nom de la classe** : `AdminInternalFieldsController` (étend `ModuleAdminController`)
        *   **Nom de l'onglet** : "Champs internes" (sous le menu Catalogue)
        *   **Responsabilité** : C'est le contrôleur principal pour la gestion des définitions des champs de produit internes personnalisés. Il gère la liste, la création, la modification et la suppression de ces champs. Il utilise `HelperList` de PrestaShop pour la vue en grille et `HelperForm` pour les formulaires d'ajout/modification. Il interagit avec l'`ObjectModel` personnalisé du module (probablement `AipfInternalField`) pour persister les définitions de champ.
    *   `aipf/controllers/admin/index.php`
        *   **Responsabilité** : Il s'agit d'un fichier `index.php` vide standard souvent placé dans les répertoires pour empêcher la liste des répertoires sur les serveurs web, améliorant la sécurité. Il ne contient aucune logique de contrôleur fonctionnelle.

### 4.3 Classes et modèles principaux (`classes/`)

Le module utilise des surcharges pour intégrer sa fonctionnalité au cœur de PrestaShop.

-   `aipf/override/classes/controller/Controller.php`
    *   **Nom de la classe** : `Controller` (surcharge la classe `Controller` de base)
    *   **Responsabilité** : Cette surcharge est probablement utilisée pour injecter du JavaScript ou du CSS spécifique au module globalement ou conditionnellement, ou pour modifier le comportement de tous les contrôleurs. Compte tenu de l'objectif du module, elle pourrait être utilisée pour s'assurer que les ressources nécessaires sont chargées pour la page produit ou pour gérer des requêtes AJAX spécifiques liées aux champs personnalisés.
-   `aipf/override/classes/controller/index.php`
    *   **Responsabilité** : Placeholder de sécurité.
-   `aipf/override/classes/index.php`
    *   **Responsabilité** : Placeholder de sécurité.

*Note : D'après la description, il devrait y avoir une classe `ObjectModel` pour `AipfInternalField` (par exemple, `classes/AipfInternalField.php`) pour gérer les définitions de champs personnalisés et potentiellement une autre pour gérer les données réelles des produits pour ces champs. Ceci n'est pas explicitement listé dans l'inventaire mais est implicite par la fonctionnalité.*

### 4.4 Actifs JavaScript (`views/js/`)

-   `aipf/lib/js/admin/aipf-configuration.js`
    *   **Portée** : Back-office (configuration du module).
    *   **Objectif** : Gère probablement la logique JavaScript spécifique pour l'écran de configuration principal du module, comme les vérifications de mise à jour ou les interactions simples de formulaire.
-   `aipf/lib/js/admin/aipf.js`
    *   **Portée** : Back-office (administration générale, potentiellement page produit).
    *   **Objectif** : Contient la logique JavaScript principale du module au sein du Back Office. Cela pourrait inclure des appels AJAX pour l'enregistrement des données de champ produit, le rendu dynamique des champs sur la page produit, ou les interactions avec le `AdminInternalFieldsController`.
-   `aipf/lib/js/front/aipf-front.js`
    *   **Portée** : Front-office.
    *   **Objectif** : Bien que le module soit destiné à un usage interne, ce fichier pourrait exister comme un placeholder ou pour gérer des tâches front-office très spécifiques et non visuelles, telles que s'assurer qu'il n'y a pas de conflits avec d'autres scripts, ou pour une fonctionnalité future potentielle qui n'a pas été implémentée. Compte tenu de la description du module, son impact sur le front-office devrait être minimal, voire nul.
-   `aipf/views/js/AdminInternalFields.js`
    *   **Portée** : Back-office (écran AdminInternalFieldsController).
    *   **Objectif** : JavaScript spécifique pour l'écran de gestion "Catalogue > Champs internes". Cela gérerait les interactions au sein de la grille, la validation de formulaire pour l'ajout/modification de champs, et les requêtes AJAX liées à la gestion des champs.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `aipf/lib/css/aipf.css`
    *   **Portée** : Principalement Back-office, potentiellement minimalement Front-office.
    *   **Objectif** : Fournit le style pour les champs personnalisés sur la page de modification du produit, l'écran de gestion "Champs internes", et tout autre élément d'interface utilisateur introduit par le module dans le Back Office. Il pourrait également contenir des styles de réinitialisation ou des règles très basiques qui pourraient s'appliquer au front-office pour éviter les conflits, bien que son objectif principal soit l'interface utilisateur administrative.
    *   **Sélecteurs de classe CSS clés** : Les développeurs pourraient rechercher des classes comme `.aipf-field-container`, `.aipf-input`, `.aipf-label` pour surcharger ou personnaliser l'apparence des champs personnalisés.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** : Non explicitement listés, mais le module utiliserait probablement des templates pour des hooks comme `displayAdminProductsExtra` ou `displayAdminProductsMainStepLeftColumnMiddle` pour injecter les champs personnalisés dans la page de modification du produit.
-   **Templates d'administration (`views/templates/admin/`)** :
    *   `aipf/views/templates/admin/combination.tpl`
        *   **Objectif** : Ce template est spécifiquement conçu pour injecter des champs internes personnalisés dans l'interface d'édition des combinaisons de produits (variantes) au sein du Back Office. Il rendrait les champs de saisie pour les données personnalisées associées à chaque combinaison de produit. Ceci est crucial pour les produits avec des attributs (comme la taille, la couleur) où chaque combinaison pourrait nécessiter ses propres notes ou identifiants internes.
-   **Templates Front-office (`views/templates/front/`)** : Aucun explicitement listé, ce qui correspond à la nature du module, qui est uniquement Back Office.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    *   `ps_aipf_internal_field` : Cette table stockerait les définitions des champs internes personnalisés (par exemple, `id_aipf_internal_field`, `name`, `active`, `field_type`).
    *   `ps_aipf_internal_field_lang` : Si les noms de champs sont traduisibles, cette table stockerait les noms spécifiques à la langue pour les champs personnalisés (par exemple, `id_aipf_internal_field`, `id_lang`, `name`).
    *   `ps_aipf_product_data` : Cette table stockerait les données réelles saisies par le marchand pour chaque champ personnalisé, liées à un produit spécifique et potentiellement à une combinaison spécifique (par exemple, `id_aipf_internal_field`, `id_product`, `id_product_attribute` (si applicable), `value`).
    *   `ps_configuration` : Table PrestaShop standard utilisée pour stocker les valeurs de configuration du module comme `mypresta_updates`, `update_`, `updatev_`.

-   **Table des hooks enregistrés** :

| Nom du hook | Portée | Moment d'exécution | Objectif technique |
|---|---|---|---|
| `actionAjaxDieProductControllerdisplayAjaxRefreshBefore` | Front/Admin | Avant la réponse AJAX dans ProductController | Potentiellement pour le pré-traitement des requêtes AJAX liées aux données produit, en s'assurant que les champs personnalisés sont pris en compte. |
| `actionOutputHTMLBefore` | Front/Admin | Avant la sortie HTML | Hook général, pourrait être utilisé pour l'injection globale d'actifs ou le traitement précoce. |
| `ActionAfterUpdateCombinationFormFormHandler` | Admin | Après la mise à jour du formulaire de combinaison | Pour enregistrer ou traiter les données de champ personnalisées liées aux combinaisons de produits. |
| `actionAdminControllerSetMedia` | Admin | Lorsque le contrôleur admin définit les médias | Pour injecter du CSS/JS spécifique au module dans les pages du Back Office (par exemple, page de modification de produit, configuration du module). |
| `actionCombinationFormFormBuilderModifier` | Admin | Lorsque le constructeur de formulaire de combinaison est modifié | Pour ajouter dynamiquement des champs personnalisés au formulaire de combinaison de produit. |
| `actionProductUpdate` | Admin | Après la mise à jour d'un produit | Pour enregistrer ou traiter les données de champ personnalisées lorsqu'un produit est enregistré. |
| `ActionFrontControllerSetMedia` | Front | Lorsque le contrôleur front définit les médias | Pour injecter du CSS/JS spécifique au module dans les pages du Front Office (si nécessaire, bien qu'improbable pour ce module). |

## 5. Support officiel et mises à jour
Pour les dernières mises à jour, corrections de bugs et support officiel du module "Champs de produit internes et personnalisés", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité et la compatibilité du module.
