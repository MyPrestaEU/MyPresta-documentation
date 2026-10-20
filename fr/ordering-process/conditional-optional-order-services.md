---
title: "Services optionnels conditionnels pour les commandes - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Services optionnels conditionnels pour les commandes par MyPresta.eu."
sidebar:
  label: "Services optionnels conditionnels pour les commandes - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Conditional Optional Order Services sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-optional-order-services.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/conditional-optional-order-services/)
>
> ---


# Services optionnels conditionnels pour les commandes

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises, qui sont généralement disponibles sur la plupart des environnements d'hébergement modernes.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

Le module « Services optionnels conditionnels pour les commandes » offre un ensemble puissant d'outils pour gérer vos services optionnels. Vous interagirez principalement avec le module via ses entrées de menu dédiées dans votre Back Office PrestaShop.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran initial que vous voyez après avoir installé le module ou cliqué sur « Configurer » depuis le Gestionnaire de modules. Il offre un moyen rapide d'activer ou de désactiver la fonctionnalité principale du module.

-   **Nom du paramètre :** Activer les services optionnels conditionnels pour les commandes
-   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour l'ensemble du module. Lorsqu'il est activé, la logique du module s'exécutera et vos services définis seront offerts aux clients en fonction de vos politiques. Lorsqu'il est désactivé, aucun service ne sera offert et le module sera effectivement inactif sur votre front-office.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'il est activé :* Le module commencera à évaluer vos politiques de service et à afficher les services pertinents aux clients dans le front-office (par exemple, la page de paiement).
    *   *Lorsqu'il est désactivé :* Tous les services conditionnels seront masqués aux clients et la logique du module ne s'exécutera pas.
-   **Valeur recommandée :** **OUI** (Activé) une fois que vous avez configuré vos politiques.
-   **Scénario / exemple pour le marchand :** Vous venez d'installer le module et êtes prêt à commencer à définir vos services. Vous activeriez ce paramètre pour rendre vos services visibles aux clients une fois qu'ils sont configurés. Si vous devez temporairement arrêter d'offrir tous les services (par exemple, pendant la maintenance ou une période de vacances), vous pouvez rapidement le désactiver ici sans supprimer vos politiques.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Après la configuration initiale, vous trouverez de nouvelles entrées de menu sous **Vendre > Services de commande** (ou un emplacement similaire, selon votre version de PrestaShop et votre thème).

#### 2.2.1 Politiques (Back Office > Vendre > Services de commande > Politiques)

C'est ici que vous définissez et gérez tous vos services optionnels conditionnels pour les commandes. Chaque « Politique » représente un service spécifique que vous souhaitez offrir, ainsi que les règles qui déterminent quand et à qui il est offert.

-   **Nom de l'écran et emplacement du menu :** Politiques (Sous **Vendre > Services de commande** dans le menu principal de PrestaShop).
-   **Actions et paramètres disponibles :**

    *   **Liste des politiques :** Un tableau affichant toutes vos politiques créées, montrant leur nom, leur statut (actif/inactif) et d'autres informations clés.
    *   **Ajouter une nouvelle politique :** Cliquez sur ce bouton pour créer un tout nouveau service optionnel.
    *   **Modifier la politique :** Cliquez sur l'icône « Modifier » à côté d'une politique existante pour modifier ses détails, ses conditions et ses règles.
    *   **Dupliquer la politique :** Une fonctionnalité très utile ! Cliquez sur l'icône « Dupliquer » pour créer une copie exacte d'une politique existante. Cela vous fait gagner du temps si vous devez créer des services similaires.
    *   **Supprimer la politique :** Supprimez une politique définitivement.
    *   **Actions groupées :** Sélectionnez plusieurs politiques et effectuez des actions telles que « Activer », « Désactiver » ou « Supprimer » simultanément.
-   **Lors de l'ajout/modification d'une politique, vous configurerez :**

    *   **Informations générales :**
        *   **Nom :** Un nom interne clair pour votre politique (par exemple, « Service d'emballage cadeau », « Assurance expédition express »).
        *   **Statut :** Activez ou désactivez cette politique spécifique. Une politique inactive ne sera jamais affichée aux clients.
        *   **Description :** Le texte que les clients verront expliquant le service. Soyez concis et mettez en évidence les avantages.
        *   **Prix :** Le coût de ce service optionnel. Il sera ajouté au panier du client s'il est sélectionné.
        *   **Règle de taxe :** Sélectionnez la règle de taxe applicable à ce service (par exemple, « Taux standard », « Taux réduit »).
        *   **Image/Icône :** Téléchargez une image ou une icône pour représenter visuellement le service aux clients. Cela le rend plus attrayant et plus facile à identifier.
    *   **Conditions :** C'est le cœur de la puissance du module. Ici, vous construisez des règles à l'aide d'un constructeur de conditions visuel pour déterminer *quand* ce service doit être offert.
        *   Vous pouvez combiner plusieurs conditions en utilisant la logique « ET » ou « OU ».
        *   **Exemples de conditions :**
            *   **Valeur du panier :** Offrir le service uniquement si le total du panier est supérieur/inférieur à un certain montant.
            *   **Produit dans le panier :** Offrir le service uniquement si des produits spécifiques ou des produits de certaines catégories/fabricants sont dans le panier.
            *   **Groupe de clients :** Offrir le service uniquement à des groupes de clients spécifiques (par exemple, « Grossistes », « Clients VIP »).
            *   **Transporteur :** Offrir le service uniquement si un transporteur spécifique est sélectionné.
            *   **Plage de dates :** Offrir le service uniquement pendant une période promotionnelle spécifique.
            *   **Pays/Zone :** Offrir le service uniquement aux clients de certains pays ou zones d'expédition.
    *   **Paramètres d'affichage :** Contrôlez la façon dont le service apparaît sur le front-office.
        *   **Position :** Si plusieurs services sont offerts, vous pouvez définir leur ordre d'affichage.
        *   **Visibilité :** Où exactement dans le processus de paiement le service apparaît.
-   **Effet des modifications :**

    *   L'ajout d'une nouvelle politique rend un nouveau service optionnel disponible pour affichage aux clients, sous réserve de ses conditions.
    *   La modification d'une politique change son nom, son prix, sa description, son image ou les conditions dans lesquelles elle est offerte. Ces modifications sont immédiatement reflétées dans le front-office.
    *   L'activation/désactivation d'une politique contrôle sa visibilité pour les clients.
    *   La suppression d'une politique la supprime entièrement, et elle ne sera plus offerte.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**

    1.  Commencez par définir vos services les plus courants (par exemple, emballage cadeau, assurance).
    2.  Utilisez le constructeur de conditions pour rendre ces services très pertinents. Par exemple, l'emballage cadeau ne peut être offert que pour les produits physiques, pas pour les téléchargements numériques.
    3.  Examinez régulièrement vos politiques, en particulier avant les promotions ou les ventes saisonnières, pour vous assurer qu'elles sont actives et correctement configurées.
    4.  Utilisez la fonction « Dupliquer » pour créer rapidement des variations de services existants (par exemple, « Emballage cadeau premium » vs « Emballage cadeau standard »).

#### 2.2.2 Journal d'audit (Back Office > Vendre > Services de commande > Journal d'audit)

Cet écran fournit un historique détaillé de toutes les actions liées aux politiques et services du module. C'est un outil précieux pour suivre les changements et résoudre les problèmes.

-   **Nom de l'écran et emplacement du menu :** Journal d'audit (Sous **Vendre > Services de commande** dans le menu principal de PrestaShop).
-   **Actions et paramètres disponibles :**
    *   **Liste des journaux :** Un tableau affichant une liste chronologique des événements.
    *   **Les colonnes incluent généralement :**
        *   **Date :** Quand l'événement s'est produit.
        *   **Employé :** Quel utilisateur du Back Office a effectué l'action.
        *   **Action :** Quelle action a été entreprise (par exemple, « Politique ajoutée », « Politique modifiée », « Politique supprimée », « Module activé/désactivé »).
        *   **Détails :** Informations spécifiques sur le changement (par exemple, quelle politique a été affectée, quelles valeurs ont été modifiées).
    *   **Filtrage/Recherche :** Outils pour filtrer le journal par date, employé ou type d'action pour trouver des événements spécifiques.
-   **Effet des modifications :** Cet écran est uniquement destiné à la visualisation ; vous ne pouvez pas y apporter de modifications directes. Il sert de registre de toutes les modifications apportées à la configuration et aux politiques du module.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    *   Utilisez le journal d'audit pour suivre qui a apporté des modifications à vos politiques de service, en particulier dans les environnements multi-utilisateurs.
    *   Si un service n'apparaît pas comme prévu, vérifiez le journal d'audit pour voir si une politique a été accidentellement désactivée ou modifiée.
    *   Surveillez tout comportement inattendu du module enregistré dans les journaux.

#### 2.2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activer les services optionnels conditionnels pour les commandes | OUI (après configuration) | Interrupteur principal pour la fonctionnalité front-office du module. |
| **Politiques (Liste)** | Ajouter une nouvelle politique | N/A | Créer un nouveau service optionnel avec ses propres règles et tarifs. |
| **Politiques (Liste)** | Modifier la politique | N/A | Modifier les détails, les conditions ou l'affichage d'un service existant. |
| **Politiques (Liste)** | Dupliquer la politique | N/A | Créer rapidement une copie d'une politique existante pour gagner du temps. |
| **Politiques (Liste)** | Supprimer la politique | N/A | Supprimer définitivement un service optionnel. |
| **Politiques (Formulaire d'édition)** | Nom | Nom descriptif | Identifiant interne du service. |
| **Politiques (Formulaire d'édition)** | Statut | Activé | Contrôle si ce service spécifique est actif et visible pour les clients. |
| **Politiques (Formulaire d'édition)** | Description | Explication claire | Texte affiché aux clients concernant le service. |
| **Politiques (Formulaire d'édition)** | Prix | 0.00 (définir la valeur) | Coût ajouté au panier si le service est sélectionné. |
| **Politiques (Formulaire d'édition)** | Règle de taxe | Règle de taxe par défaut | Taxe applicable au service. |
| **Politiques (Formulaire d'édition)** | Image/Icône | Image téléchargée | Représentation visuelle du service pour les clients. |
| **Politiques (Formulaire d'édition)** | Conditions (Constructeur) | Règles personnalisées | Définit *quand* et *à qui* le service est offert (par exemple, valeur du panier, produit dans le panier, groupe de clients). |
| **Politiques (Formulaire d'édition)** | Position | Auto (définir la valeur) | Ordre d'affichage si plusieurs services sont offerts. |
| **Journal d'audit** | (Toutes les entrées) | N/A | Fournit un enregistrement historique de toutes les modifications apportées aux paramètres et politiques du module. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes services optionnels n'apparaissent pas sur la page de paiement. Que dois-je vérifier ?**
R1 :

1.  **Module activé ?** Allez dans **Modules > Gestionnaire de modules**, trouvez « Services optionnels conditionnels pour les commandes » et assurez-vous qu'il est activé.
2.  **Statut de la politique ?** Allez dans **Vendre > Services de commande > Politiques**. Assurez-vous que la politique spécifique que vous vous attendez à voir est « Active ».
3.  **Conditions de la politique remplies ?** C'est la raison la plus courante. Examinez attentivement les conditions que vous avez définies pour la politique. Votre panier de test actuel remplit-il *toutes* les conditions « ET » et *l'une quelconque* des conditions « OU » ? Par exemple, si vous avez défini « Total du panier > 50 € » et que votre panier est de 45 €, le service n'apparaîtra pas.
4.  **Cache ?** Videz le cache de votre PrestaShop sous **Paramètres avancés > Performances**. Parfois, d'anciennes données mises en cache peuvent empêcher l'affichage des nouvelles configurations de module.
5.  **Compatibilité du thème ?** Bien que le module soit conçu pour une large compatibilité, des thèmes très fortement personnalisés peuvent nécessiter des ajustements mineurs. Vérifiez la console de développement de votre navigateur pour les erreurs JavaScript.

**Q2 : Le prix de mon service n'est pas ajouté correctement au total du panier.**
R2 :

1.  **Prix de la politique défini ?** Vérifiez le champ « Prix » dans la configuration de votre politique.
2.  **Règle de taxe appliquée ?** Assurez-vous que la « Règle de taxe » correcte est sélectionnée pour le service. Le prix final inclut les taxes basées sur cette règle.
3.  **Devise ?** Vérifiez que le prix est défini dans la devise par défaut de votre boutique ou que les paramètres multi-devises sont correctement gérés par PrestaShop.

**Q3 : Comment traduire les noms et descriptions des services dans d'autres langues ?**
R3 :

1.  Allez dans **International > Traductions** dans votre Back Office PrestaShop.
2.  Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez votre langue.
3.  Recherchez le module « Services optionnels conditionnels pour les commandes ». Vous devriez pouvoir traduire les noms et descriptions de vos politiques directement dans les formulaires de configuration du module, car ils sont généralement stockés comme des champs traduisibles. Sinon, ils apparaîtront ici.

**Q4 : Puis-je modifier l'ordre dans lequel les services apparaissent sur la page de paiement ?**
R4 : Oui, dans la configuration de chaque politique, il devrait y avoir un paramètre « Position ». Vous pouvez définir une valeur numérique (par exemple, 10, 20, 30) pour contrôler l'ordre d'affichage. Les nombres inférieurs apparaissent en premier.

**Q5 : Le module provoque un problème visuel ou un conflit avec un autre module.**
R5 :

1.  **Isolez le problème :** Désactivez temporairement les autres modules récemment installés ou mis à jour pour voir si le conflit disparaît.
2.  **Vérifiez les erreurs :** Utilisez la console de développement de votre navigateur (F12) pour rechercher les erreurs JavaScript ou CSS.
3.  **Contactez le support :** Si vous ne parvenez pas à le résoudre, fournissez au support MyPresta.eu les détails du problème, votre version de PrestaShop et tout autre module que vous soupçonnez d'être en conflit.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de la structure technique du module « Services optionnels conditionnels pour les commandes », destinée aux développeurs et aux webmasters.

### 4.1 Aperçu de l'architecture

Le module suit un modèle MVC (Modèle-Vue-Contrôleur) robuste, typique des modules PrestaShop. Il s'appuie fortement sur le système de hooks de PrestaShop pour injecter ses fonctionnalités à divers points du front-office (paiement, page produit) et du back-office (vue de commande admin, configuration du module).
Les composants architecturaux clés comprennent :

-   **Politiques (`conorderservicesPolicy`) :** L'entité principale représentant un service optionnel, étendant `ObjectModel`.
-   **Conditions (`conorderservicesCondition`, `conorderservicesConditionGroup`, `conorderservicesConditionTree`) :** Un système sophistiqué pour construire des règles complexes afin de déterminer l'éligibilité au service.
-   **Moteur (`conorderservicesEngine`) :** La classe centrale responsable de l'évaluation des conditions et de la détermination des services à présenter au client.
-   **Journal d'audit (`conorderservicesAuditLog`) :** Enregistre toutes les actions significatives au sein du module pour la traçabilité.
-   **Couche de compatibilité (`conorderservicesCompatibility`) :** Gère les différences entre PrestaShop 1.7, 8 et 9.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   `conorderservices/controllers/front/ajax.php`
    *   **Nom de la classe :** `ConorderservicesAjaxModuleFrontController` (étend `ModuleFrontController`)
    *   **Responsabilité :** Gère les requêtes AJAX du front-office, principalement pour la mise à jour dynamique des sélections de services ou le recalcul des totaux du panier lorsqu'un service est ajouté/supprimé par le client. Il délègue probablement au `conorderservicesEngine` pour effectuer les calculs et renvoie des réponses JSON.
-   `conorderservices/controllers/front/index.php`
    *   **Nom de la classe :** `ConorderservicesIndexModuleFrontController` (étend `ModuleFrontController`)
    *   **Responsabilité :** Un contrôleur de remplacement ou de secours. Souvent utilisé pour un accès direct au module si nécessaire, bien que la plupart des interactions front-office se fassent via des hooks ou AJAX.

#### Contrôleurs d'administration Back-Office

-   `conorderservices/controllers/admin/AdminconorderservicesAuditLog.php`
    *   **Nom de la classe :** `AdminconorderservicesAuditLogController` (étend `ModuleAdminController`)
    *   **Nom de l'onglet :** Journal d'audit (sous « Vendre > Services de commande »)
    *   **Entité gérée :** `conorderservicesAuditLog`
    *   **Responsabilité :** Gère l'affichage et le filtrage des entrées du journal d'audit. Il utilise `HelperList` de PrestaShop pour rendre le tableau du journal.
-   `conorderservices/controllers/admin/AdminconorderservicesPolicies.php`
    *   **Nom de la classe :** `AdminconorderservicesPoliciesController` (étend `ModuleAdminController`)
    *   **Nom de l'onglet :** Politiques (sous « Vendre > Services de commande »)
    *   **Entité gérée :** `conorderservicesPolicy`
    *   **Responsabilité :** Le contrôleur principal pour la gestion des politiques de services optionnels. Il gère la liste, l'ajout, la modification, la duplication et la suppression des objets `conorderservicesPolicy`. Il utilise `HelperList` pour la liste des politiques et `HelperForm` pour les formulaires d'ajout/modification de politique, y compris le constructeur de conditions complexe.
-   `conorderservices/controllers/admin/index.php`
    *   **Nom de la classe :** `AdminconorderservicesIndexController` (étend `ModuleAdminController`)
    *   **Nom de l'onglet :** (Probablement le point d'entrée principal « Services de commande »)
    *   **Entité gérée :** Aucune directement, redirige souvent vers `AdminconorderservicesPolicies` ou affiche un tableau de bord.
    *   **Responsabilité :** Sert de point d'entrée principal pour la section d'administration du module, affichant potentiellement un tableau de bord ou redirigeant vers la liste des politiques.

### 4.3 Classes et modèles principaux (`classes/`)

-   `conorderservices/classes/conorderservicesAdmin.php`
    *   **Objectif :** Classe utilitaire pour les fonctions spécifiques à l'administration, gérant potentiellement les permissions, la génération de menus ou les tâches administratives courantes.
-   `conorderservices/classes/conorderservicesAuditLog.php`
    *   **Étend :** `ObjectModel`
    *   **Table de base de données :** `ps_conorderservices_log`
    *   **Champs `$definition` :** `id_conorderservices_log`, `id_employee`, `action`, `details`, `date_add`
    *   **Objectif :** Représente une entrée dans le journal d'audit du module. Fournit des méthodes pour ajouter de nouvelles entrées de journal.
-   `conorderservices/classes/conorderservicesCartState.php`
    *   **Objectif :** Gère et persiste l'état des services optionnels sélectionnés dans le panier du client. Interagit probablement avec `Context::getContext()->cart` et stocke les sélections de services.
-   `conorderservices/classes/conorderservicesCompatibility.php`
    *   **Objectif :** Fournit une couche d'abstraction pour les fonctions ou comportements spécifiques à la version de PrestaShop, garantissant que le module fonctionne sur les versions 1.7, 8 et 9.
-   `conorderservices/classes/conorderservicesCondition.php`
    *   **Étend :** `ObjectModel` (probablement, ou une classe de base pour les conditions)
    *   **Table de base de données :** `ps_conorderservices_condition`
    *   **Champs `$definition` :** `id_conorderservices_condition`, `id_conorderservices_condition_group`, `type`, `operator`, `value`
    *   **Objectif :** Représente une seule condition au sein d'un groupe de conditions (par exemple, « Total du panier » « est supérieur à » « 100 »).
-   `conorderservices/classes/conorderservicesConditionEvaluator.php`
    *   **Objectif :** Le moteur logique pour évaluer un ensemble de conditions par rapport au panier, au client et au contexte produit actuels. Détermine si les conditions d'une politique sont remplies.
-   `conorderservices/classes/conorderservicesConditionGroup.php`
    *   **Étend :** `ObjectModel` (probablement)
    *   **Table de base de données :** `ps_conorderservices_condition_group`
    *   **Champs `$definition` :** `id_conorderservices_condition_group`, `id_conorderservices_policy`, `logic_operator` (AND/OR)
    *   **Objectif :** Regroupe plusieurs objets `conorderservicesCondition`, définissant la relation logique entre eux (ET/OU).
-   `conorderservices/classes/conorderservicesConditionTree.php`
    *   **Objectif :** Gère la structure hiérarchique des groupes de conditions et des conditions individuelles, permettant la construction de règles complexes.
-   `conorderservices/classes/conorderservicesContext.php`
    *   **Objectif :** Un wrapper ou une extension de la classe `Context` de PrestaShop, fournissant des données de contexte spécifiques au module (par exemple, panier actuel, client, langue) pour l'évaluation des conditions.
-   `conorderservices/classes/conorderservicesDashboard.php`
    *   **Objectif :** Fournit des données et une logique pour la vue du tableau de bord du module (le cas échéant), affichant potentiellement des analyses ou des statistiques rapides.
-   `conorderservices/classes/conorderservicesEngine.php`
    *   **Objectif :** L'unité de traitement centrale du module. Elle récupère les politiques actives, les transmet au `ConditionEvaluator` et détermine quels services sont éligibles pour le panier actuel. Elle gère également l'ajout/la suppression de produits de service du panier.
-   `conorderservices/classes/conorderservicesListRenderer.php`
    *   **Objectif :** Classe d'aide pour le rendu des listes dans le Back Office, étendant potentiellement `HelperList` ou fournissant une logique de rendu personnalisée.
-   `conorderservices/classes/conorderservicesLog.php`
    *   **Objectif :** Alias ou implémentation spécifique pour la journalisation, éventuellement distincte de `conorderservicesAuditLog` pour différents types de journalisation.
-   `conorderservices/classes/conorderservicesPolicy.php`
    *   **Étend :** `ObjectModel`
    *   **Table de base de données :** `ps_conorderservices_policy`
    *   **Champs `$definition` :** `id_conorderservices_policy`, `name`, `description`, `price`, `id_tax_rule`, `image`, `active`, `position`, `date_add`, `date_upd` (et champs `_lang` pour les champs traduisibles `name`, `description`).
    *   **Objectif :** Le modèle principal pour un service optionnel. Stocke toute la configuration d'un service, y compris ses détails, son prix, son image et les groupes de conditions associés.
-   `conorderservices/classes/conorderservicesPolicyDuplicator.php`
    *   **Objectif :** Gère la logique de duplication d'une politique entière, y compris ses conditions et les données associées.
-   `conorderservices/classes/conorderservicesPreset.php`
    *   **Objectif :** Fournit probablement des ensembles prédéfinis de conditions ou de politiques qui peuvent être rapidement chargés par le marchand.
-   `conorderservices/classes/conorderservicesRule.php`
    *   **Objectif :** Un terme plus générique pour une condition ou un ensemble de conditions. Pourrait être une classe de base abstraite ou un type de règle spécifique.
-   `conorderservices/classes/ConorderservicesRuleImage.php`
    *   **Objectif :** Gère les images/icônes associées aux politiques ou aux règles.
-   `conorderservices/classes/ConorderservicesServiceProduct.php`
    *   **Étend :** `Product` (ou un wrapper autour de celui-ci)
    *   **Objectif :** Représente le « produit virtuel » qui est ajouté au panier lorsqu'un client sélectionne un service optionnel. Il garantit que le service se comporte comme un produit régulier pour le traitement du panier et des commandes.
-   `conorderservices/classes/conorderservicesTreeRepository.php`
    *   **Objectif :** Gère le stockage et la récupération de la structure de l'arbre de conditions.
-   `conorderservices/classes/index.php`
    *   **Objectif :** Fichier vide standard pour empêcher la liste des répertoires.
-   `conorderservices/classes/load.php`
    *   **Objectif :** Fichier d'autoloading ou un fichier qui inclut d'autres définitions de classes.

### 4.4 Actifs JavaScript (`views/js/`)

-   `conorderservices/lib/searchTool/views/js/autocomplete.js`
    *   **Portée :** Back-office (pour la sélection de produits/catégories dans le constructeur de conditions)
    *   **Détails :** Fournit une fonctionnalité d'autocomplétion pour les champs de saisie, probablement utilisée lors de la sélection de produits, catégories ou fabricants dans le constructeur de conditions.
-   `conorderservices/lib/searchTool/views/views/js/autocomplete.js`
    *   **Portée :** Back-office (redondant ou spécifique à une vue différente de l'outil de recherche)
    *   **Détails :** Similaire à ce qui précède, probablement un doublon ou une version spécifique du script d'autocomplétion.
-   `conorderservices/views/js/adminConditionBuilder.js`
    *   **Portée :** Back-office (`AdminconorderservicesPoliciesController`)
    *   **Détails :** JS principal pour le constructeur de conditions visuel. Gère l'ajout/la suppression de conditions et de groupes de conditions, la gestion des opérateurs logiques (ET/OU) et la mise à jour de l'interface utilisateur en fonction de l'entrée de l'utilisateur.
-   `conorderservices/views/js/adminconorderservicesDashboard.js`
    *   **Portée :** Back-office (`AdminconorderservicesIndexController` ou vue Tableau de bord)
    *   **Détails :** Scripts pour les éléments interactifs du tableau de bord du module, tels que les graphiques, les statistiques ou les liens rapides.
-   `conorderservices/views/js/adminconorderservicesSearchTool.js`
    *   **Portée :** Back-office (`AdminconorderservicesPoliciesController`)
    *   **Détails :** Intègre l'outil de recherche (autocomplétion) avec le constructeur de conditions, permettant aux administrateurs de trouver et de sélectionner facilement des entités (produits, catégories, etc.) pour les conditions.
-   `conorderservices/views/js/adminconorderservicesSimulator.js`
    *   **Portée :** Back-office (`AdminconorderservicesPoliciesController` - probablement un onglet ou un modal dédié)
    *   **Détails :** Fournit des fonctionnalités pour un simulateur de politique, permettant aux administrateurs de tester les conditions avec des données de panier fictives pour voir quels services seraient offerts.
-   `conorderservices/views/js/adminPolicyRuleImage.js`
    *   **Portée :** Back-office (`AdminconorderservicesPoliciesController`)
    *   **Détails :** Gère les fonctionnalités de téléchargement et de prévisualisation d'images pour les icônes/images de politique.
-   `conorderservices/views/js/adminPolicyRules.js`
    *   **Portée :** Back-office (`AdminconorderservicesPoliciesController`)
    *   **Détails :** Scripts généraux pour la gestion des règles de politique, incluant potentiellement le réordonnancement par glisser-déposer ou d'autres interactions d'interface utilisateur sur la page d'édition de politique.
-   `conorderservices/views/js/adminSettingsOfferDisplay.js`
    *   **Portée :** Back-office (Configuration principale du module ou Édition de politique)
    *   **Détails :** Scripts liés à la configuration de la manière et de l'endroit où les services optionnels sont affichés sur le front-office.
-   `conorderservices/views/js/checkout.js`
    *   **Portée :** Front-office (Page de paiement)
    *   **Détails :** C'est le script front-office critique. Il écoute les interactions de l'utilisateur (par exemple, cocher/décocher un service), envoie des requêtes AJAX à `ajax.php` pour mettre à jour le panier et met à jour dynamiquement le résumé du panier et le total sur la page de paiement. Il se lie probablement aux événements `prestashop.on` pour les mises à jour du panier.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `conorderservices/lib/searchTool/views/css/autocomplete.css`
    *   **Portée :** Back-office
    *   **Détails :** Styles pour les listes déroulantes d'autocomplétion et les champs de saisie utilisés dans l'outil de recherche d'administration.
-   `conorderservices/lib/searchTool/views/views/css/autocomplete.css`
    *   **Portée :** Back-office (redondant ou spécifique à une vue différente de l'outil de recherche)
    *   **Détails :** Similaire à ce qui précède, probablement un doublon ou une version spécifique des styles d'autocomplétion.
-   `conorderservices/views/css/admin_conorderservices.css`
    *   **Portée :** Back-office
    *   **Détails :** Style général pour les pages d'administration du module, y compris la liste des politiques, le constructeur de conditions et le journal d'audit. Contient des styles pour les éléments de formulaire, les tableaux et les composants d'interface utilisateur personnalisés.
-   `conorderservices/views/css/front.css`
    *   **Portée :** Front-office
    *   **Détails :** Styles pour la façon dont les services optionnels sont affichés sur la page de paiement. Inclut le style pour le bloc de service, les lignes de service individuelles, les cases à cocher, les prix et les icônes. Les développeurs peuvent remplacer ces classes dans le `custom.css` ou `theme.css` de leur thème.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)

-   `conorderservices/views/templates/hook/admin_order.tpl`
    *   **Hook :** `displayAdminOrder`
    *   **Sortie :** Affiche des informations sur les services optionnels sélectionnés dans la vue de commande du Back Office de PrestaShop. Cela permet aux administrateurs de voir quels services ont été achetés avec une commande.
-   `conorderservices/views/templates/hook/checkout_services.tpl`
    *   **Hook :** `displayShoppingCart`, `displayShoppingCartFooter` (ou des hooks de paiement similaires)
    *   **Sortie :** Le modèle principal pour le rendu de la liste des services optionnels disponibles sur la page de paiement du front-office. Il itère sur les politiques éligibles et les affiche.
-   `conorderservices/views/templates/hook/partials/checkout_offer_row.tpl`
    *   **Hook :** Inclus par `checkout_services.tpl`
    *   **Sortie :** Rend une seule ligne ou carte pour un service optionnel dans la liste de paiement, y compris son nom, sa description, son prix et son champ de sélection (par exemple, case à cocher).

#### Modèles d'administration (`views/templates/admin/`)

-   `conorderservices/views/templates/admin/auditPreview.tpl`
    *   **Objectif :** Rend une vue détaillée ou un aperçu d'une entrée du journal d'audit.
-   `conorderservices/views/templates/admin/dashboard.tpl`
    *   **Objectif :** Le modèle principal pour le tableau de bord du module dans le Back Office, affichant potentiellement des analyses ou des informations récapitulatives.
-   `conorderservices/views/templates/admin/helpers/list/list_action_duplicate.tpl`
    *   **Objectif :** Modèle personnalisé pour le bouton d'action « Dupliquer » dans les vues `HelperList` (spécifiquement pour les politiques).
-   `conorderservices/views/templates/admin/policiesPreview.tpl`
    *   **Objectif :** Rend un aperçu d'une politique, potentiellement utilisé dans un simulateur ou une vue rapide.
-   `conorderservices/views/templates/admin/policyConditionBuilder.tpl`
    *   **Objectif :** Le modèle pour l'interface du constructeur de conditions visuel dans le formulaire d'édition de politique. C'est un modèle complexe qui ajoute/supprime dynamiquement des groupes de conditions et des conditions individuelles.
-   `conorderservices/views/templates/admin/policyRuleCard.tpl`
    *   **Objectif :** Rend une seule règle ou un groupe de conditions sous forme de carte dans le constructeur de conditions, la rendant visuellement distincte.
-   `conorderservices/views/templates/admin/policyRulesTable.tpl`
    *   **Objectif :** Rend une structure de type tableau pour afficher les règles, éventuellement une alternative ou un composant dans le constructeur de conditions.
-   `conorderservices/views/templates/admin/scopeSelector.tpl`
    *   **Objectif :** Modèle pour la sélection de la portée d'une condition (par exemple, produit, catégorie, client).

#### Modèles de bibliothèque (`conorderservices/lib/searchTool/views/`)

-   `conorderservices/lib/searchTool/views/helpers.tpl`
    *   **Objectif :** Modèles d'aide pour l'outil de recherche, éventuellement pour le rendu des résultats de recherche ou des champs de saisie.
-   `conorderservices/lib/searchTool/views/scripts.tpl`
    *   **Objectif :** Inclut le JavaScript pour l'outil de recherche.
-   `conorderservices/lib/searchTool/views/views/scripts.tpl`
    *   **Objectif :** Doublon ou version spécifique des scripts de l'outil de recherche.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

-   `ps_conorderservices_policy`
    *   Stocke les informations de politique de base : `id_conorderservices_policy`, `name`, `description`, `price`, `id_tax_rule`, `image`, `active`, `position`, `date_add`, `date_upd`.
    *   Comprend également des champs spécifiques à la langue pour `name` et `description` (par exemple, `ps_conorderservices_policy_lang`).
-   `ps_conorderservices_condition_group`
    *   Stocke les groupes de conditions : `id_conorderservices_condition_group`, `id_conorderservices_policy`, `logic_operator` (AND/OR).
-   `ps_conorderservices_condition`
    *   Stocke les conditions individuelles : `id_conorderservices_condition`, `id_conorderservices_condition_group`, `type`, `operator`, `value`.
-   `ps_conorderservices_log`
    *   Stocke les entrées du journal d'audit : `id_conorderservices_log`, `id_employee`, `action`, `details`, `date_add`.
-   `ps_conorderservices_cart_state` (probable)
    *   Stocke les services sélectionnés pour un panier donné : `id_cart`, `id_conorderservices_policy`, `date_add`.
-   `ps_configuration`
    *   `CONORDERSERVICES_ENABLED` : Stocke l'état d'activation/désactivation principal du module.
    *   `PS_CURRENCY_DEFAULT` : Utilisé pour afficher les prix dans l'administration.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `ActionObjectProductInCartDeleteBefore` | Avant la suppression d'un produit du panier. | S'assure que si un produit requis pour un service est supprimé, le service est également supprimé ou réévalué. |
| `actionPresentCart` | Lorsque les données du panier sont présentées (par exemple, sur la page de paiement). | Injecte la liste des services optionnels éligibles dans les données de présentation du panier. |
| `ActionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration est chargé et que ses médias (JS/CSS) sont définis. | Injecte les JS et CSS spécifiques au module pour les pages du Back Office (politiques, journal d'audit, constructeur de conditions). |
| `ActionPresentProductListing` | Lorsque les données de produit sont présentées dans une liste (par exemple, page de catégorie). | Potentiellement utilisé pour afficher des indicateurs de disponibilité de service sur les listes de produits. |
| `ActionValidateOrderBefore` | Avant la validation d'une commande. | Effectue les vérifications finales sur les services sélectionnés, s'assure qu'ils sont toujours valides et les ajoute comme détails de commande. |
| `ActionGetProductPropertiesAfter` | Après la récupération des propriétés du produit. | Potentiellement modifie les propriétés du produit si un service les affecte (par exemple, ajout d'un produit virtuel pour le service). |
| `DisplayAdminOrder` | Sur la page de détail de la commande du Back Office. | Affiche les services optionnels sélectionnés associés à la commande. |
| `ActionFrontControllerInitAfter` | Après l'initialisation d'un contrôleur frontal. | Initialise le contexte ou la logique front-office spécifique au module. |
| `ActionPresentProduct` | Lorsque les données d'un seul produit sont présentées (par exemple, page produit). | Potentiellement utilisé pour afficher des indicateurs de disponibilité de service sur les pages produits. |
| `ActionPresentCartProduct` | Lorsqu'un produit du panier est présenté. | Modifie la présentation des produits du panier si des services leur sont attachés. |
| `ActionProductPriceCalculation` | Pendant le calcul du prix du produit. | S'assure que les prix des services sont correctement pris en compte dans le total. |
| `DisplayShoppingCart` | Sur la page du panier. | Affiche le bloc des services optionnels. |
| `DisplayShoppingCartFooter` | Dans le pied de page de la page du panier. | Emplacement alternatif ou supplémentaire pour le bloc des services optionnels. |
| `ActionCartSave` | Après l'enregistrement d'un panier. | Persiste l'état des services optionnels sélectionnés dans le panier. |
| `ActionValidateOrder` | Après la validation d'une commande. | Finalise la commande avec les services sélectionnés, mettant potentiellement à jour l'inventaire ou déclenchant des actions de suivi. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Services optionnels conditionnels pour les commandes », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité et la compatibilité du module.
"""
