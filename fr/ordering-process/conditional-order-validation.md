---
title: "Validation Conditionnelle de Commande - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop de Validation Conditionnelle de Commande par MyPresta.eu."
sidebar:
  label: "Validation Conditionnelle de Commande - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Conditional Order Validation sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-order-validation.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/conditional-order-validation/)
>
> ---


# Validation Conditionnelle de Commande

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Validation Conditionnelle de Commande)

C'est le point d'entrée principal pour les paramètres globaux du module.

- **Emplacement du menu :** Back Office > Modules > Gestionnaire de modules > Validation Conditionnelle de Commande > Configurer

#### 2.1.1 Paramètres généraux

| Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- |
| **Activer la validation conditionnelle de commande** | OUI | **Ce que fait ce paramètre :** C'est l'interrupteur principal pour l'ensemble du module. S'il est désactivé, aucune de vos politiques définies ne sera active, et les clients pourront passer commande sans aucune restriction de ce module.   **Effet de la modification de ce paramètre :**   *Lorsqu'il est activé :* Le module commencera à évaluer toutes les politiques actives que vous avez créées. Si un panier enfreint une politique, le client verra des avertissements ou sera bloqué au paiement selon les paramètres de votre politique.   *Lorsqu'il est désactivé :* Le module devient inactif. Aucune politique n'est vérifiée et aucun message n'est affiché.   **Valeur recommandée :** OUI (une fois que vous avez configuré vos politiques).   **Scénario marchand :** Activez ceci après avoir configuré vos premières politiques et les avoir testées à l'aide du simulateur. |
| **Afficher les messages de validation sur** | Panier & Paiement | **Ce que fait ce paramètre :** Contrôle où les messages d'avertissement ou de blocage du module sont affichés au client.   **Effet de la modification de ce paramètre :**   *Lorsqu'il est défini sur « Panier & Paiement » :* Les messages apparaîtront à la fois sur la page du panier d'achat et pendant les différentes étapes du processus de paiement. Cela offre une visibilité maximale et un retour d'information précoce au client.   *Lorsqu'il est défini sur « Panier uniquement » :* Les messages n'apparaîtront que sur la page du panier d'achat. Les clients pourraient avancer plus loin dans le paiement avant d'être bloqués s'ils ignorent l'avertissement du panier.   *Lorsqu'il est défini sur « Paiement uniquement » :* Les messages n'apparaîtront que pendant le processus de paiement. Les clients ne verront pas d'avertissements sur la page du panier, ce qui pourrait entraîner de la frustration plus tard dans le processus.   **Valeur recommandée :** Panier & Paiement.   **Scénario marchand :** Pour une meilleure expérience client, affichez les messages tôt et souvent (Panier & Paiement) afin que les clients puissent corriger leur panier avant d'investir du temps dans le processus de paiement. |
| **Autoriser le paiement avec avertissements** | NON | **Ce que fait ce paramètre :** Détermine si les clients peuvent procéder au paiement même si leur panier déclenche une politique d'« avertissement » (par opposition à une politique de « blocage »).   **Effet de la modification de ce paramètre :**   *Lorsqu'il est activé (OUI) :* Si une politique est définie sur « Avertissement », le client verra le message d'avertissement mais pourra toujours cliquer sur le bouton « Procéder au paiement » ou « Passer commande ». Ceci est utile pour des recommandations douces ou des problèmes non critiques.   *Lorsqu'il est désactivé (NON) :* Si une politique est définie sur « Avertissement », le client verra le message d'avertissement, et le bouton « Procéder au paiement » ou « Passer commande » sera désactivé jusqu'à ce que la condition d'avertissement soit résolue. Cela fait effectivement en sorte que les « avertissements » se comportent comme des « blocages » à l'étape du paiement.   **Valeur recommandée :** NON (sauf si vous avez des avertissements « doux » très spécifiques).   **Scénario marchand :** Si vous avez une politique comme « Les clients achetant plus de 100 $ bénéficient de la livraison gratuite », et que vous voulez *suggérer* qu'ils ajoutent plus à leur panier mais ne pas les *forcer*, vous pourriez activer ceci. Cependant, pour la plupart des règles commerciales, vous voudrez le désactiver pour assurer la conformité. |

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module introduit deux nouvelles sections puissantes dans le menu de votre Back Office PrestaShop : « Politiques » et « Journal d'audit ».

#### 2.2.1 Politiques (Back Office > Validation Conditionnelle de Commande > Politiques)

C'est ici que vous définissez, gérez et activez vos règles de validation conditionnelle de commande. Chaque « politique » est un ensemble de conditions qui, si elles sont remplies, bloqueront ou avertiront le client.

- **Emplacement du menu :** Back Office > Validation Conditionnelle de Commande > Politiques
- **Actions et paramètres disponibles :**

  - **Liste des politiques :** Un tableau affichant toutes vos politiques créées, montrant leur nom, leur statut (activé/désactivé), leur type (blocage/avertissement) et leur priorité.
  - **Ajouter une nouvelle politique :** Cliquez sur ce bouton pour créer une nouvelle politique de validation.
  - **Modifier la politique :** Modifiez le nom, les conditions, les messages et le statut d'une politique existante.
  - **Dupliquer la politique :** Créez rapidement une copie d'une politique existante pour l'utiliser comme point de départ pour une nouvelle. Cela permet de gagner du temps lors de la création de règles similaires.
  - **Activer/Désactiver la politique :** Basculez le statut actif d'une politique sans la supprimer.
  - **Supprimer la politique :** Supprimez une politique définitivement.
  - **Simulateur :** Un outil crucial (souvent trouvé sur l'écran de création/modification de politique ou comme onglet dédié) qui vous permet de tester vos politiques avec un panier simulé avant qu'elles ne soient mises en ligne. Cela aide à prévenir le blocage involontaire de commandes légitimes.
- **Formulaire de création/modification de politique :**

  - **Nom de la politique :** Un nom descriptif pour votre politique (par exemple, « Valeur de commande minimale pour la vente en gros », « Restriction d'âge pour l'alcool »).
  - **Statut :** Activez ou désactivez la politique.
  - **Type de politique :**
    - **Blocage :** Si les conditions sont remplies, le client est *empêché* de passer commande.
    - **Avertissement :** Si les conditions sont remplies, le client voit un message d'avertissement mais *peut ou non* être en mesure de continuer, selon le paramètre global « Autoriser le paiement avec avertissements ».
  - **Priorité :** Si plusieurs politiques sont actives et déclenchées, cela détermine l'ordre dans lequel les messages sont affichés ou quelle politique a la priorité (nombre inférieur = priorité plus élevée).
  - **Constructeur de conditions :** C'est le cœur de la politique. Vous construirez un arbre de conditions en utilisant la logique « ET » / « OU ».
    - **Types de conditions :** Vous pouvez généralement choisir parmi un large éventail de conditions :
      - **Niveau du panier :** Valeur totale du panier, quantité totale d'articles, nombre de produits uniques.
      - **Niveau du produit :** ID de produit spécifiques, catégories, fabricants, fournisseurs, attributs de produit, quantité minimale/maximale d'un produit spécifique.
      - **Niveau du client :** Groupe de clients, ID de client spécifique, pays du client.
      - **Niveau d'expédition :** Transporteur sélectionné, zone d'expédition.
    - **Opérateurs :** (par exemple, « est égal à », « est supérieur à », « contient », « n'est pas »).
    - **Valeurs :** Le point de données spécifique à comparer (par exemple, « 100 » pour une valeur minimale, « Électronique » pour une catégorie).
  - **Message client :** Le message affiché au client dans le front office lorsque cette politique est déclenchée. Rendez-le clair, utile et exploitable (par exemple, « Votre panier doit contenir au moins 5 unités du produit X pour continuer. »).
  - **Message administrateur (facultatif) :** Une note interne pour vous-même ou d'autres administrateurs.
- **Effet des modifications :**

  - L'ajout/la modification d'une politique a un impact direct sur l'expérience de paiement en front office pour les clients.
  - L'activation d'une politique active ses règles. La désactivation les désactive sans suppression.
  - Le simulateur vous permet de tester les modifications sans affecter les clients en direct.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**

  1. Identifiez une règle commerciale que vous souhaitez appliquer (par exemple, « Les clients grossistes doivent commander un minimum de 500 $ »).
  2. Allez dans « Politiques » et cliquez sur « Ajouter une nouvelle politique ».
  3. Donnez-lui un nom clair, définissez-la sur « Blocage » et définissez les conditions (par exemple, « Groupe de clients EST Grossiste » ET « Total du panier EST SUPÉRIEUR OU ÉGAL À 500 »).
  4. Rédigez un message client utile (par exemple, « Les commandes en gros nécessitent un total minimum de 500 $. Veuillez ajouter plus d'articles à votre panier. »).
  5. Utilisez le « Simulateur » pour tester divers scénarios (par exemple, un client grossiste avec un panier de 400 $, un client de détail avec un panier de 400 $, un client grossiste avec un panier de 600 $).
  6. Une fois satisfait, activez la politique.

#### 2.2.2 Journal d'audit (Back Office > Validation Conditionnelle de Commande > Journal d'audit)

Le Journal d'audit fournit un enregistrement historique des moments où les politiques ont été déclenchées, par qui et quel a été le résultat. Ceci est inestimable pour le dépannage et la compréhension du comportement des clients.

- **Emplacement du menu :** Back Office > Validation Conditionnelle de Commande > Journal d'audit
- **Actions et paramètres disponibles :**

  - **Liste des journaux :** Un tableau affichant les entrées pour chaque fois qu'une politique a été évaluée et déclenchée.
  - **Colonnes :**
    - **Date/Heure :** Quand l'événement s'est produit.
    - **Client :** Le client qui a déclenché la politique (s'il est connecté).
    - **ID du panier :** L'ID du panier d'achat concerné.
    - **Nom de la politique :** Le nom de la politique qui a été déclenchée.
    - **Type de politique :** S'il s'agissait d'une politique de « Blocage » ou d'« Avertissement ».
    - **Message :** Le message affiché au client.
    - **Statut :** Si la commande a finalement été validée, bloquée ou avertie.
  - **Filtrage/Recherche :** Le filtrage de liste standard de PrestaShop vous permet de rechercher par client, politique, plage de dates, etc.
  - **Afficher les détails du panier :** Souvent, vous pouvez cliquer sur un ID de panier pour inspecter le contenu du panier au moment où la politique a été déclenchée.
- **Effet des modifications :** Cet écran est uniquement destiné à la visualisation et à l'audit ; vous ne pouvez pas y apporter de modifications. C'est un enregistrement des événements.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**

  - Si un client signale un problème avec le paiement, vérifiez le Journal d'audit pour voir si des politiques ont été déclenchées pour son panier. Cela peut rapidement identifier si une politique est mal configurée ou si le client n'a tout simplement pas satisfait aux exigences.
  - Examinez périodiquement le journal pour comprendre quelles politiques sont les plus fréquemment déclenchées et si des ajustements sont nécessaires.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
|---|---|---|
| **Configuration du module** | Activer la validation conditionnelle de commande | OUI | Interrupteur principal pour la fonctionnalité du module. |
| **Configuration du module** | Afficher les messages de validation sur | Panier & Paiement | Où les messages client apparaissent (panier, paiement, ou les deux). |
| **Configuration du module** | Autoriser le paiement avec avertissements | NON | Détermine si les politiques d'« avertissement » bloquent le paiement ou se contentent d'informer. |
| **Politiques (Admin)** | Nom de la politique | N/A | Identifiant descriptif de votre règle. |
| **Politiques (Admin)** | Statut | Activé | Active ou désactive une politique spécifique. |
| **Politiques (Admin)** | Type de politique | Blocage / Avertissement | Définit si la politique empêche le paiement ou affiche simplement un message. |
| **Politiques (Admin)** | Priorité | N/A | Ordre d'évaluation/affichage pour plusieurs politiques déclenchées. |
| **Politiques (Admin)** | Constructeur de conditions | N/A | Définit les règles logiques pour le déclenchement de la politique. |
| **Politiques (Admin)** | Message client | N/A | Le message affiché au client lorsque la politique est déclenchée. |
| **Politiques (Admin)** | Message administrateur | N/A | Notes internes pour les administrateurs. |
| **Journal d'audit (Admin)** | (Toutes les colonnes) | N/A | Enregistre toutes les instances de déclenchement de politiques pour examen. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : Mes politiques ne fonctionnent pas, ou les clients continuent de passer commande alors qu'ils ne devraient pas.**
R :

1.  **Le module est-il activé ?** Vérifiez « Activer la validation conditionnelle de commande » dans la configuration principale du module.
2.  **Les politiques spécifiques sont-elles activées ?** Allez dans « Politiques » et assurez-vous que la colonne « Statut » de vos politiques est définie sur « Activé ».
3.  **Vérifiez le type de politique :** Est-il défini sur « Blocage » ou « Avertissement » ? Si « Avertissement », vérifiez le paramètre global « Autoriser le paiement avec avertissements ». Si celui-ci est activé, les clients peuvent ignorer les avertissements.
4.  **Videz le cache :** Parfois, le cache de PrestaShop peut empêcher les modifications de prendre effet immédiatement. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ».
5.  **Simulateur :** Utilisez le « Simulateur » intégré sur l'écran de création/modification de politique pour tester vos conditions avec divers scénarios de panier. C'est le moyen le plus efficace de déboguer.
6.  **Journal d'audit :** Vérifiez le « Journal d'audit » pour voir si vos politiques sont déclenchées du tout et quel a été le résultat.

**Q : Les messages d'avertissement/de blocage ne s'affichent pas correctement sur mon thème.**
R : Le module utilise le style standard de PrestaShop dans la mesure du possible, mais les thèmes personnalisés peuvent le remplacer ou nécessiter des ajustements CSS spécifiques.

1.  **CSS de base :** Le CSS du module est conçu pour être générique. Si votre thème a un style très spécifique, vous devrez peut-être demander à un webmaster d'ajouter du CSS personnalisé au fichier `custom.css` de votre thème pour correspondre à votre marque.
2.  **Surcharges de template :** Les utilisateurs avancés peuvent surcharger les fichiers de template du module (par exemple, `views/templates/hook/validation_banner.tpl`) dans leur thème pour personnaliser entièrement la structure HTML et l'apparence.

**Q : Puis-je traduire les messages pour différentes langues ?**
R : Oui, tous les messages destinés aux clients que vous définissez dans vos politiques sont traduisibles.

1.  Allez dans **International > Traductions** dans votre Back Office.
2.  Sélectionnez « Traductions des modules installés », choisissez votre thème et sélectionnez la langue.
3.  Recherchez le module « Validation Conditionnelle de Commande » et traduisez les messages de politique à cet endroit.

**Q : J'ai créé une politique, mais elle bloque *toutes* les commandes, même les valides.**
R : Cela signifie généralement que vos conditions sont trop larges ou mal configurées.

1.  **Examinez les conditions :** Relisez attentivement chaque condition de votre politique. Assurez-vous que les opérateurs (par exemple, « EST », « N'EST PAS », « SUPÉRIEUR À ») et les valeurs sont corrects.
2.  **Logique ET/OU :** Portez une attention particulière à l'utilisation de « ET » ou « OU » entre les groupes de conditions. « ET » signifie que *toutes* les conditions doivent être vraies ; « OU » signifie qu'*une seule* condition doit être vraie. Une erreur courante est d'utiliser « OU » lorsque « ET » est prévu, ou vice versa.
3.  **Utilisez le simulateur :** C'est essentiel. Simulez divers paniers « bons » et « mauvais » pour voir exactement pourquoi la politique se déclenche.

**Q : Comment gérer les configurations multi-boutiques ?**
R : Le module est conçu pour être compatible multi-boutiques. Lors de la création ou de la modification de politiques, vous devriez voir une option pour sélectionner les boutiques auxquelles la politique s'applique. Assurez-vous que vos politiques sont attribuées aux contextes de boutique corrects.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une plongée approfondie dans la structure technique du module de Validation Conditionnelle de Commande pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module de Validation Conditionnelle de Commande suit un modèle MVC (Modèle-Vue-Contrôleur) robuste au sein du framework PrestaShop. Il s'appuie fortement sur `ObjectModel` pour la persistance des données (politiques, journaux d'audit), des contrôleurs d'administration personnalisés pour la gestion de ces entités, et un moteur d'évaluation de conditions sophistiqué pour traiter les règles en temps réel. Le module s'intègre profondément dans les hooks de validation de commande et de présentation du panier, garantissant que les politiques sont appliquées aux étapes critiques du parcours client. Un aspect clé est le `ConordervalidEngine` qui orchestre l'évaluation des objets `ConordervalidPolicy`, chacun contenant un `ConordervalidConditionTree`.

### 4.2 Contrôleurs (`controllers/`)

#### 4.2.1 Contrôleurs Front-Office

- `conordervalid/controllers/front/index.php`
  - **Nom de la classe :** `ConordervalidIndexModuleFrontController` (étend probablement `ModuleFrontController`)
  - **Responsabilité :** Ce contrôleur pourrait servir de point d'entrée général ou gérer des requêtes AJAX spécifiques du front-office liées à la validation du panier ou à l'affichage des messages. Compte tenu de son nom, il pourrait s'agir d'un contrôleur de secours ou d'affichage simple.
- `conordervalid/controllers/front/validate.php`
  - **Nom de la classe :** `ConordervalidValidateModuleFrontController` (étend probablement `ModuleFrontController`)
  - **Responsabilité :** Ce contrôleur est crucial pour la validation du panier en temps réel. Il gère probablement les requêtes AJAX des pages du panier ou de paiement pour vérifier si l'état actuel du panier enfreint des politiques actives. Il renverrait des réponses JSON indiquant si le panier est valide, des messages d'avertissement ou des raisons de blocage. C'est ici que le `ConordervalidEngine` serait invoqué.

#### 4.2.2 Contrôleurs d'administration Back-Office

- `conordervalid/controllers/admin/AdminconordervalidAuditLog.php`
  - **Nom de la classe :** `AdminconordervalidAuditLogController` (étend `ModuleAdminController`)
  - **Nom de l'onglet :** Journal d'audit (sous le menu Validation Conditionnelle de Commande)
  - **Entité gérée :** `ConordervalidAuditLog` (mappé à la table `ps_conordervalid_log`)
  - **Responsabilité :** Gère l'affichage et le filtrage des entrées du journal d'audit. Il utilise `HelperList` pour le rendu de la grille, permettant aux administrateurs de consulter les enregistrements historiques des déclenchements de politiques.
- `conordervalid/controllers/admin/AdminconordervalidPolicies.php`
  - **Nom de la classe :** `AdminconordervalidPoliciesController` (étend `ModuleAdminController`)
  - **Nom de l'onglet :** Politiques (sous le menu Validation Conditionnelle de Commande)
  - **Entité gérée :** `ConordervalidPolicy` (mappé à la table `ps_conordervalid_policy`)
  - **Responsabilité :** C'est le contrôleur principal pour la gestion des politiques de validation. Il gère les opérations CRUD pour les politiques, y compris l'interface complexe du constructeur de conditions. Il utilise `HelperList` pour l'aperçu des politiques et `HelperForm` pour la création/modification de politiques, intégrant la logique de `ConordervalidConditionTree` et `ConordervalidConditionBuilder`.
- `conordervalid/controllers/admin/index.php`
  - **Nom de la classe :** (Probablement une simple redirection ou un espace réservé)
  - **Responsabilité :** Souvent, `index.php` dans un répertoire de contrôleur est une mesure de sécurité pour empêcher la liste directe du répertoire ou une simple redirection vers la configuration principale du module ou le tableau de bord.

### 4.3 Classes et modèles de base (`classes/`)

- `conordervalid/classes/ConordervalidAdmin.php`
  - **Responsabilité :** Contient probablement des méthodes d'aide ou des utilitaires spécifiquement pour l'interface d'administration, tels que l'enregistrement de menu, la gestion des onglets ou la logique de rendu de formulaire courante.
- `conordervalid/classes/ConordervalidAuditLog.php`
  - **Étend :** `ObjectModel`
  - **Table de base de données :** `ps_conordervalid_log`
  - **Champs `$definition` :** `id_conordervalid_log`, `id_cart`, `id_customer`, `id_policy`, `policy_name`, `policy_type`, `message`, `date_add`.
  - **Responsabilité :** Représente une seule entrée dans le journal d'audit, stockant les détails d'une politique déclenchée.
- `conordervalid/classes/ConordervalidCartState.php`
  - **Responsabilité :** Une classe utilitaire pour encapsuler l'état actuel du panier d'un client (produits, quantités, total, informations client, transporteur sélectionné, etc.). Cet objet est passé à l'`ConordervalidConditionEvaluator`.
- `conordervalid/classes/ConordervalidCompatibility.php`
  - **Responsabilité :** Gère les couches de compatibilité pour différentes versions de PrestaShop (par exemple, différences dans les noms de hook, les structures de classe ou les appels d'API entre PS 1.7, 8.x et 9.x).
- `conordervalid/classes/ConordervalidCondition.php`
  - **Étend :** (Probablement une classe de base ou `ObjectModel` si les conditions sont stockées individuellement)
  - **Responsabilité :** Représente une seule condition au sein d'une politique (par exemple, « Total du panier > 100 »). Elle définit le type de condition, l'opérateur et la valeur.
- `conordervalid/classes/ConordervalidConditionEvaluator.php`
  - **Responsabilité :** La logique principale pour évaluer une `ConordervalidCondition` ou `ConordervalidConditionGroup` par rapport à un objet `ConordervalidCartState`. Elle contient des méthodes pour comparer différents types de données et appliquer des opérateurs.
- `conordervalid/classes/ConordervalidConditionGroup.php`
  - **Étend :** (Probablement une classe de base)
  - **Responsabilité :** Représente un regroupement logique de conditions (par exemple, « Condition A ET (Condition B OU Condition C) »). Gère la logique `ET`/`OU`.
- `conordervalid/classes/ConordervalidConditionTree.php`
  - **Étend :** (Probablement une classe de base ou `ObjectModel`)
  - **Responsabilité :** Représente l'ensemble de la structure hiérarchique des conditions pour une politique. C'est une structure de données arborescente composée d'objets `ConordervalidConditionGroup` et `ConordervalidCondition`.
- `conordervalid/classes/ConordervalidContext.php`
  - **Responsabilité :** Un wrapper ou une extension de la classe `Context` de PrestaShop, ajoutant potentiellement des données de contexte spécifiques au module ou des méthodes d'aide.
- `conordervalid/classes/ConordervalidDashboard.php`
  - **Responsabilité :** Fournit probablement des données et de la logique pour un tableau de bord de module potentiel dans le Back Office, résumant les performances des politiques ou les statistiques du journal d'audit.
- `conordervalid/classes/ConordervalidEngine.php`
  - **Responsabilité :** L'orchestrateur central. Il récupère les objets `ConordervalidPolicy` actifs, les parcourt et utilise `ConordervalidConditionEvaluator` pour vérifier si un panier donné enfreint une politique. Il détermine le résultat final (bloqué, averti, valide) et collecte les messages.
- `conordervalid/classes/ConordervalidListRenderer.php`
  - **Responsabilité :** Une classe utilitaire pour le rendu de listes ou de tableaux dans le Back Office, personnalisant potentiellement le comportement de `HelperList` ou fournissant un formatage de colonne spécifique.
- `conordervalid/classes/ConordervalidLog.php`
  - **Étend :** `ObjectModel` (probablement un alias ou une ancienne version de `ConordervalidAuditLog`)
  - **Table de base de données :** `ps_conordervalid_log`
  - **Champs `$definition` :** Similaires à `ConordervalidAuditLog`.
  - **Responsabilité :** Stocke les entrées du journal d'audit.
- `conordervalid/classes/ConordervalidPolicy.php`
  - **Étend :** `ObjectModel`
  - **Table de base de données :** `ps_conordervalid_policy`
  - **Champs `$definition` :** `id_conordervalid_policy`, `name`, `active`, `type` (blocage/avertissement), `priority`, `conditions_json` (stocke le `ConordervalidConditionTree` au format JSON), `customer_message`, `admin_message`, `date_add`, `date_upd`.
  - **Responsabilité :** Représente une seule politique de validation, y compris ses conditions, messages et paramètres.
- `conordervalid/classes/ConordervalidPolicyDuplicator.php`
  - **Responsabilité :** Gère la logique de duplication des objets `ConordervalidPolicy`, garantissant que toutes les conditions et paramètres associés sont correctement copiés.
- `conordervalid/classes/ConordervalidPreset.php`
  - **Responsabilité :** Définit probablement des ensembles prédéfinis de conditions ou de modèles de politiques qui peuvent être rapidement chargés par les administrateurs.
- `conordervalid/classes/ConordervalidRule.php`
  - **Étend :** (Probablement une classe de base ou `ObjectModel`)
  - **Responsabilité :** Pourrait être un alias pour `ConordervalidCondition` ou une abstraction de niveau supérieur pour une seule règle au sein d'une politique.
- `conordervalid/classes/ConordervalidTreeRepository.php`
  - **Responsabilité :** Gère le stockage et la récupération des objets `ConordervalidConditionTree`, les sérialisant/désérialisant probablement vers/depuis le champ `conditions_json` dans `ConordervalidPolicy`.
- `conordervalid/classes/index.php`
  - **Responsabilité :** Mesure de sécurité standard pour empêcher la liste des répertoires.

### 4.4 Actifs JavaScript (`views/js/`)

- `conordervalid/lib/searchTool/views/js/autocomplete.js`
  - **Portée :** Back-office (formulaires d'administration)
  - **Responsabilité :** Fournit une fonctionnalité d'autocomplétion pour les champs de saisie dans l'administration, probablement utilisée lors de la sélection de produits, catégories, clients, etc., dans le constructeur de conditions.
- `conordervalid/lib/searchTool/views/views/js/autocomplete.js`
  - **Portée :** Back-office (formulaires d'administration)
  - **Responsabilité :** Duplicata de ce qui précède, probablement une erreur d'empaquetage ou un chemin hérité.
- `conordervalid/views/js/adminConditionBuilder.js`
  - **Portée :** Back-office (`AdminconordervalidPoliciesController`)
  - **Responsabilité :** Alimente l'interface interactive de construction de conditions dans le formulaire de création/modification de politique. Gère l'ajout/la suppression de conditions, la gestion de la logique ET/OU et la mise à jour de la structure JSON sous-jacente de l'arbre de conditions.
- `conordervalid/views/js/adminConordervalidDashboard.js`
  - **Portée :** Back-office (Tableau de bord d'administration, si implémenté)
  - **Responsabilité :** Fournit des fonctionnalités dynamiques pour un tableau de bord de module potentiel, telles que le rendu de graphiques, le filtrage de données ou les mises à jour AJAX.
- `conordervalid/views/js/adminConordervalidSearchTool.js`
  - **Portée :** Back-office (formulaires d'administration)
  - **Responsabilité :** Intègre l'outil de recherche (par exemple, pour les produits, les catégories) dans divers formulaires d'administration, probablement utilisé par le constructeur de conditions.
- `conordervalid/views/js/adminConordervalidSimulator.js`
  - **Portée :** Back-office (`AdminconordervalidPoliciesController`)
  - **Responsabilité :** Gère la logique du simulateur de politique. Il capture les données de panier simulées, les envoie via AJAX à un contrôleur frontal (par exemple, `validate.php`) et affiche les résultats de la validation.
- `conordervalid/views/js/adminPolicyRules.js`
  - **Portée :** Back-office (`AdminconordervalidPoliciesController`)
  - **Responsabilité :** Contient une logique JS spécifique pour gérer l'affichage et l'interaction des règles de politique dans l'interface d'administration, potentiellement liée au réordonnancement par glisser-déposer ou aux modifications rapides.
- `conordervalid/views/js/validation.js`
  - **Portée :** Front-office (pages Panier, Paiement)
  - **Responsabilité :** C'est le JS principal du front-office. Il écoute les changements de panier (par exemple, mise à jour de quantité, suppression de produit), déclenche des appels AJAX au contrôleur frontal `validate.php`, puis met à jour dynamiquement l'interface utilisateur pour afficher les messages d'avertissement/de blocage ou activer/désactiver les boutons de paiement en fonction de la réponse. Il utilise probablement `prestashop.on` pour la liaison d'événements.

### 4.5 Feuilles de style CSS (`views/css/`)

- `conordervalid/lib/searchTool/views/css/autocomplete.css`
  - **Portée :** Back-office (formulaires d'administration)
  - **Composants d'interface utilisateur principaux :** Styles pour les listes déroulantes d'autocomplétion et les champs de saisie utilisés dans l'outil de recherche d'administration.
  - **Sélecteurs clés :** `.autocomplete-suggestions`, `.autocomplete-selected`, `.autocomplete-suggestion`.
- `conordervalid/lib/searchTool/views/views/css/autocomplete.css`
  - **Portée :** Back-office (formulaires d'administration)
  - **Composants d'interface utilisateur principaux :** Duplicata de ce qui précède.
  - **Sélecteurs clés :** Identiques à ci-dessus.
- `conordervalid/views/css/admin_conordervalid.css`
  - **Portée :** Back-office (formulaires et listes d'administration)
  - **Composants d'interface utilisateur principaux :** Styles pour la liste des politiques, le formulaire de création/modification de politique, le constructeur de conditions et le journal d'audit.
  - **Sélecteurs clés :** `.conordervalid-policy-card`, `.conordervalid-condition-group`, `.conordervalid-condition-row`, `.conordervalid-simulator-results`.
- `conordervalid/views/css/front.css`
  - **Portée :** Front-office (pages Panier, Paiement)
  - **Composants d'interface utilisateur principaux :** Styles pour les bannières et messages d'avertissement/de blocage affichés aux clients.
  - **Sélecteurs clés :** `.conordervalid-validation-banner`, `.conordervalid-warning`, `.conordervalid-blocking`, `.conordervalid-message-list`.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### 4.6.1 Templates de hook (`views/templates/hook/`)

- `conordervalid/views/templates/hook/admin_order.tpl`
  - **Hook :** `DisplayAdminOrder`
  - **Sorties :** Un bloc dans la vue de commande du Back Office, affichant potentiellement les politiques qui ont été déclenchées pour une commande ou un panier spécifique.
- `conordervalid/views/templates/hook/validation_banner.tpl`
  - **Hook :** `DisplayPaymentTop`, `DisplayShoppingCartFooter`, `DisplayCheckoutSummaryTop`
  - **Sorties :** La structure HTML pour les messages d'avertissement/de blocage du front-office affichés au client. Ce template reçoit des variables comme `$validation_messages`, `$is_blocked`, etc.

#### 4.6.2 Templates d'administration (`views/templates/admin/`)

- `conordervalid/lib/searchTool/views/scripts.tpl`
  - **Sorties :** Template Smarty pour inclure les actifs JS/CSS liés à l'outil de recherche dans l'administration.
- `conordervalid/lib/searchTool/views/views/scripts.tpl`
  - **Sorties :** Duplicata de ce qui précède.
- `conordervalid/views/templates/admin/auditPreview.tpl`
  - **Sorties :** Un template partiel pour afficher un aperçu ou un résumé des entrées du journal d'audit, éventuellement utilisé dans un tableau de bord ou une vue spécifique.
- `conordervalid/views/templates/admin/dashboard.tpl`
  - **Sorties :** Le template principal pour un tableau de bord de module potentiel dans le Back Office, affichant des statistiques, des journaux récents ou des résumés de politiques.
- `conordervalid/views/templates/admin/helpers/list/list_action_duplicate.tpl`
  - **Sorties :** Bouton d'action personnalisé pour dupliquer les politiques dans la vue `HelperList` pour `AdminconordervalidPoliciesController`.
- `conordervalid/views/templates/admin/policiesPreview.tpl`
  - **Sorties :** Un template partiel pour afficher un aperçu ou un résumé des politiques, similaire à `auditPreview.tpl`.
- `conordervalid/views/templates/admin/policyConditionBuilder.tpl`
  - **Sorties :** La structure HTML complexe pour l'interface interactive de construction de conditions utilisée lors de la création ou de la modification d'une politique. Ce template fonctionne en étroite collaboration avec `adminConditionBuilder.js`.
- `conordervalid/views/templates/admin/policyRuleCard.tpl`
  - **Sorties :** Un template plus petit et réutilisable pour afficher une seule règle ou condition dans le constructeur de conditions.
- `conordervalid/views/templates/admin/policyRulesTable.tpl`
  - **Sorties :** Une structure de type tableau pour afficher une liste de règles, éventuellement utilisée dans l'aperçu des politiques ou le simulateur.
- `conordervalid/views/templates/admin/scopeSelector.tpl`
  - **Sorties :** Template pour sélectionner la portée d'une politique (par exemple, des boutiques spécifiques dans un environnement multi-boutiques).

#### 4.6.3 Templates Front-office (`views/templates/front/`)

- (Aucun template front-office autonome identifié, car l'affichage front-office est géré via des templates de hook comme `validation_banner.tpl`.)

### 4.7 Schéma de base de données et carte des hooks

#### 4.7.1 Tables de base de données

- `ps_conordervalid_policy`
  - **Objectif :** Stocke la définition de chaque politique de validation.
  - **Champs clés :** `id_conordervalid_policy` (PK), `name`, `active` (booléen), `type` (enum : 'blocking', 'warning'), `priority`, `conditions_json` (TEXT, stocke le `ConordervalidConditionTree` sérialisé), `customer_message` (TEXT), `admin_message` (TEXT), `date_add`, `date_upd`.
- `ps_conordervalid_log`
  - **Objectif :** Stocke les entrées du journal d'audit pour les politiques déclenchées.
  - **Champs clés :** `id_conordervalid_log` (PK), `id_cart`, `id_customer`, `id_policy`, `policy_name`, `policy_type`, `message`, `date_add`.
- `ps_configuration`
  - **Objectif :** Stocke les paramètres globaux du module.
  - **Champs clés :** `CONORDERVALID_DISPLAY_SURFACES` (par exemple, 'cart,checkout'), `CONORDERVALID_ENABLED` (booléen), `CONORDERVALID_ALLOW_WARN_CHECKOUT` (booléen).

#### 4.7.2 Tableau des hooks enregistrés

| Nom du hook | Moment et contexte d'exécution | Objectif technique |
| --- | --- | --- |
| `DisplayHeader` | Rendu dans la section `<head>` de toutes les pages du front-office. | Injecte les actifs CSS (`front.css`) et JS (`validation.js`) du front-office. |
| `ActionFrontControllerInitAfter` | Après l'initialisation d'un contrôleur frontal. | Potentiellement utilisé pour initialiser le contexte du module, charger les politiques ou effectuer des vérifications de validation précoces. |
| `ActionObjectProductInCartDeleteBefore` | Avant la suppression d'un produit du panier. | Pourrait être utilisé pour enregistrer l'état du panier avant un changement, ou pour empêcher la suppression si cela enfreint une politique. |
| `ActionObjectProductInCartDeleteAfter` | Après la suppression d'un produit du panier. | Réévalue les politiques du panier après la suppression d'un produit, déclenche une mise à jour AJAX. |
| `ActionCartSave` | Après l'enregistrement d'un panier (par exemple, mise à jour de quantité, ajout/suppression de produit). | Déclenche la réévaluation de toutes les politiques actives par rapport au panier mis à jour. |
| `actionPresentCart` | Lorsque le panier est préparé pour l'affichage (par exemple, sur la page du panier). | Injecte les messages de validation dans le template de la page du panier. |
| `DisplayShoppingCartFooter` | En bas de la page du panier d'achat. | Rend le `validation_banner.tpl` avec tous les messages d'avertissement/de blocage. |
| `DisplayPaymentTop` | En haut de la section de sélection du paiement pendant le processus de paiement. | Rend le `validation_banner.tpl` avec tous les messages d'avertissement/de blocage, désactivant potentiellement les options de paiement. |
| `DisplayCheckoutSummaryTop` | En haut de la page de résumé du paiement (avant la confirmation finale de la commande). | Rend le `validation_banner.tpl` avec tous les messages d'avertissement/de blocage, désactivant potentiellement le bouton de confirmation de commande. |
| `ActionFilterPaymentOptions` | Filtre les options de paiement disponibles pendant le processus de paiement. | Peut être utilisé pour masquer ou désactiver les méthodes de paiement si une politique est enfreinte (par exemple, « COD non autorisé pour les commandes de plus de X $ »). |
| `ActionValidateOrderBefore` | Juste avant qu'une commande ne soit officiellement validée. | La dernière vérification critique pour bloquer une commande si des politiques de blocage sont enfreintes. Enregistre la tentative. |
| `ActionValidateOrder` | Après qu'une commande a été validée et créée avec succès. | Enregistre la validation réussie de la commande, enregistre potentiellement les politiques qui n'ont *pas* été enfreintes. |
| `DisplayAdminOrder` | Rend un bloc dans la page de détail de la commande du Back Office. | Affiche des informations sur les politiques qui ont été déclenchées (ou passées) pour la commande spécifique, en utilisant `admin_order.tpl`. |
| `ActionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration définit ses médias (JS/CSS). | Injecte les JS (`adminConditionBuilder.js`, `adminConordervalidSimulator.js`) et CSS (`admin_conordervalid.css`) spécifiques au Back Office pour la gestion des politiques. |
| `DisplayReassurance` | Souvent utilisé pour afficher des éléments de confiance (par exemple, icônes de paiement sécurisé). | Pourrait potentiellement être utilisé pour afficher un petit avertissement ou un statut persistant si un panier n'est pas valide. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module de Validation Conditionnelle de Commande, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la configuration du module.
