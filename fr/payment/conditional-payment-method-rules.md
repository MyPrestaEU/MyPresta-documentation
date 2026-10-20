---
title: "Règles de Méthodes de Paiement Conditionnelles - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Règles de Méthodes de Paiement Conditionnelles par MyPresta.eu."
sidebar:
  label: "Règles de Méthodes de Paiement Conditionnelles - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Conditional Payment Method Rules sur MyPresta.eu](https://mypresta.eu/modules/payment-process/conditional-payment-method-rules.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/payment/conditional-payment-method-rules/)
>
> ---


# Règles de Méthodes de Paiement Conditionnelles

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

La configuration du module est principalement gérée via des écrans d'administration dédiés, vous permettant de créer et de gérer vos politiques de méthodes de paiement.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est le point d'entrée principal du module. Après l'installation, cliquer sur « Configurer » vous mènera à un tableau de bord ou à une page de paramètres généraux.

#### Paramètres généraux et tableau de bord

Cet écran offre un aperçu de l'état de votre module et un accès rapide aux fonctionnalités clés.

- **Ce que fait cet écran :** Affiche un résumé de vos politiques actives, des entrées récentes du journal d'audit et des liens rapides pour gérer les politiques ou consulter le journal d'audit. C'est votre centre névralgique pour surveiller l'activité du module.
- **Effet de la modification des paramètres :** Cet écran fournit principalement des informations et de la navigation. Toute modification que vous apportez ici (par exemple, activer/désactiver une politique) aura un impact direct sur la façon dont les méthodes de paiement sont affichées au moment du paiement.
- **Valeur recommandée :** Gardez un œil sur le tableau de bord pour tout conflit de politique ou comportement inattendu.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module introduit plusieurs nouveaux éléments de menu sous la section « Paiement » dans votre Back Office PrestaShop.

#### 2.2.1 Politiques de méthodes de paiement (Back Office > Paiement > Règles de méthodes de paiement > Politiques)

C'est ici que vous définissez et gérez toutes vos règles pour afficher ou masquer les méthodes de paiement.

- **Nom de l'écran et emplacement du menu :** **Paiement > Règles de méthodes de paiement > Politiques**
- **Actions et paramètres disponibles :**

  - **Liste des politiques :** Un tableau affichant toutes vos politiques créées, leur statut (activé/désactivé) et les méthodes de paiement qu'elles affectent.
  - **Ajouter une nouvelle politique :** Cliquez sur ce bouton pour créer une nouvelle règle.
  - **Modifier/Supprimer une politique :** Gérez les politiques individuelles à partir de la liste.
  - **Dupliquer une politique :** Créez rapidement une copie d'une politique existante pour la modifier.
  - **Activer/Désactiver une politique :** Basculez le statut actif d'une politique sans la supprimer.
  - **Importer/Exporter des politiques (JSON) :** Sauvegardez vos politiques ou transférez-les entre les boutiques.
- **Création/Modification d'une politique :**
  Lorsque vous ajoutez ou modifiez une politique, vous configurerez plusieurs aspects clés :

  1. **Nom de la politique :**

     - **Ce que fait ce paramètre :** Un nom descriptif pour votre politique (par exemple, « Masquer le paiement à la livraison pour les commandes internationales »).
     - **Effet de la modification de ce paramètre :** Vous aide à identifier la politique dans la liste.
     - **Valeur recommandée :** Rendez-le clair et concis.
     - **Scénario marchand :** Nommer une politique « Livraison gratuite uniquement avec PayPal » vous indique immédiatement son objectif.
  2. **Statut (Activé/Désactivé) :**

     - **Ce que fait ce paramètre :** Contrôle si la politique est active et appliquée au moment du paiement.
     - **Effet de la modification de ce paramètre :**
       - *Lorsqu'activé :* Les règles de cette politique seront évaluées et affecteront la visibilité des méthodes de paiement.
       - *Lorsqu'désactivé :* La politique est ignorée et ses règles n'ont aucun effet.
     - **Valeur recommandée :** Activez les politiques uniquement lorsque vous êtes sûr qu'elles sont correctement configurées.
     - **Scénario marchand :** Vous pourriez désactiver temporairement une politique pendant une promotion ou si vous rencontrez des problèmes.
  3. **Méthodes de paiement affectées :**

     - **Ce que fait ce paramètre :** Sélectionnez les méthodes de paiement spécifiques que cette politique contrôlera.
     - **Effet de la modification de ce paramètre :** Seules les méthodes de paiement sélectionnées seront soumises aux règles de cette politique.
     - **Valeur recommandée :** Sélectionnez toutes les méthodes de paiement pertinentes pour cette politique.
     - **Scénario marchand :** Si vous souhaitez masquer « Paiement à la livraison » et « Virement bancaire » sous certaines conditions, vous les sélectionneriez tous les deux ici.
  4. **Type de politique (Afficher/Masquer) :**

     - **Ce que fait ce paramètre :** Détermine si les conditions de la politique *afficheront* les méthodes de paiement sélectionnées ou les *masqueront*.
     - **Effet de la modification de ce paramètre :**
       - *Lorsqu'il est défini sur « Afficher » :* Les méthodes de paiement sélectionnées ne seront visibles que si TOUTES les conditions de cette politique sont remplies. Si les conditions ne sont pas remplies, elles sont masquées.
       - *Lorsqu'il est défini sur « Masquer » :* Les méthodes de paiement sélectionnées seront masquées si TOUTES les conditions de cette politique sont remplies. Si les conditions ne sont pas remplies, elles sont visibles.
     - **Valeur recommandée :** Choisissez en fonction de votre objectif principal. « Masquer » est souvent plus facile pour des restrictions spécifiques, tandis que « Afficher » est bon pour des offres exclusives.
     - **Scénario marchand :**
       - *Masquer :* « Masquer le paiement à la livraison si le total du panier dépasse 500 € ».
       - *Afficher :* « Afficher le 'Plan de paiement échelonné' UNIQUEMENT si le groupe de clients est 'VIP' ET que le total du panier dépasse 1000 € ».
  5. **Constructeur de conditions :**

     - **Ce que fait ce paramètre :** C'est le cœur de votre politique. Vous construisez des règles complexes en utilisant la logique « ET » et « OU » basée sur divers critères.
     - **Effet de la modification de ce paramètre :** Les conditions que vous définissez ici déterminent *quand* l'action « Afficher » ou « Masquer » de la politique est déclenchée.
     - **Conditions disponibles (Exemples) :**
       - **Total du panier :** Basé sur la valeur totale du panier du client.
       - **Groupe de clients :** Basé sur le groupe auquel appartient le client (par exemple, Invité, Client, VIP, Grossiste).
       - **Pays :** Basé sur le pays de livraison ou de facturation du client.
       - **Transporteur :** Basé sur le transporteur sélectionné.
       - **Produits dans le panier :** Basé sur des produits, catégories, fabricants ou fournisseurs spécifiques dans le panier.
       - **Devise :** Basé sur la devise utilisée pour la commande.
       - **Poids :** Basé sur le poids total du panier.
       - **Date/Heure :** Basé sur des dates ou heures spécifiques (par exemple, pour les promotions).
       - **Boutique :** Pour les configurations multi-boutiques.
     - **Valeur recommandée :** Commencez par des conditions simples et testez minutieusement. Utilisez « ET » pour des exigences plus strictes et « OU » pour une applicabilité plus large.
     - **Scénario marchand :**
       - « Masquer PayPal si (Pays EST 'France' ET Total du panier EST INFÉRIEUR À 10 €) OU (Groupe de clients EST 'Grossiste') ».
       - « Afficher le virement bancaire si (Groupe de clients EST 'B2B') ET (Total du panier EST SUPÉRIEUR À 1000 €) ».
  6. **Message d'indisponibilité :**

     - **Ce que fait ce paramètre :** Un message personnalisé affiché au client si une méthode de paiement est masquée par cette politique.
     - **Effet de la modification de ce paramètre :** Fournit une communication claire au client sur la raison pour laquelle une option de paiement n'est pas disponible, évitant la confusion.
     - **Valeur recommandée :** Restez poli et informatif (par exemple, « Le paiement à la livraison n'est pas disponible pour les commandes de plus de 500 €. Veuillez choisir une autre méthode de paiement. »).
     - **Scénario marchand :** « Cette méthode de paiement n'est disponible que pour les clients VIP. » ou « Veuillez sélectionner une méthode de livraison différente pour utiliser cette option de paiement. »
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**

  1. **Identifier un besoin :** « Je veux arrêter d'offrir le paiement à la livraison pour les commandes de plus de 200 €. »
  2. **Créer une nouvelle politique :** Nommez-la « Limite paiement à la livraison 200 € ».
  3. **Sélectionnez « Masquer »** comme type de politique.
  4. **Sélectionnez « Paiement à la livraison »** comme méthode de paiement affectée.
  5. **Ajoutez une condition :** « Total du panier EST SUPÉRIEUR À 200 € ».
  6. **Ajoutez un message d'indisponibilité :** « Le paiement à la livraison n'est pas disponible pour les commandes dépassant 200 €. Veuillez choisir une autre méthode de paiement. »
  7. **Activez et enregistrez.**
  8. **Testez à l'aide du simulateur** (voir section suivante).

#### 2.2.2 Journal d'audit (Back Office > Paiement > Règles de méthodes de paiement > Journal d'audit)

Cet écran fournit un historique détaillé de la façon dont vos règles de paiement ont été appliquées.

- **Nom de l'écran et emplacement du menu :** **Paiement > Règles de méthodes de paiement > Journal d'audit**
- **Actions et paramètres disponibles :**
  - **Liste des journaux :** Un tableau affichant chaque instance où la visibilité d'une méthode de paiement a été affectée par une politique.
  - **Détails :** Affichez des informations spécifiques sur chaque entrée de journal, y compris le client, les détails du panier, les politiques évaluées et le résultat final (quelles méthodes de paiement ont été affichées/masquées).
  - **Filtrage :** Filtrez les entrées de journal par date, client, politique ou méthode de paiement pour trouver rapidement des événements spécifiques.
- **Effet des modifications :** Cet écran est destiné à la visualisation et à l'audit. Vous ne pouvez pas y apporter de modifications, mais il est inestimable pour comprendre pourquoi certaines méthodes de paiement ont été ou n'ont pas été affichées à un client.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vérifiez régulièrement le journal d'audit si vous recevez des demandes de clients concernant des méthodes de paiement manquantes ou si vous soupçonnez qu'une politique ne fonctionne pas comme prévu. C'est votre outil de débogage.

#### 2.2.3 Simulateur (Back Office > Paiement > Règles de méthodes de paiement > Simulateur)

Le simulateur est un outil puissant pour tester vos politiques sans passer de commande réelle.

- **Nom de l'écran et emplacement du menu :** **Paiement > Règles de méthodes de paiement > Simulateur**
- **Actions et paramètres disponibles :**
  - **Champs de saisie :** Saisissez divers critères comme le groupe de clients, le pays, le transporteur, le total du panier, et même ajoutez des produits spécifiques à un panier simulé.
  - **Bouton Simuler :** Cliquez pour voir quelles méthodes de paiement seraient disponibles en fonction de vos critères saisis et de vos politiques actives.
  - **Affichage des résultats :** Affiche une liste des méthodes de paiement disponibles et indisponibles, ainsi que les raisons (quelles politiques les ont fait masquer/afficher).
- **Effet des modifications :** Cet écran vous permet d'expérimenter différents scénarios et de voir immédiatement l'impact de vos politiques. Il n'affecte pas votre boutique en direct.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** *Utilisez toujours* le simulateur après avoir créé ou modifié une politique. Testez les cas limites et les scénarios courants pour vous assurer que vos règles fonctionnent exactement comme prévu avant qu'elles ne soient mises en ligne.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Politiques (Ajouter/Modifier)** | Nom de la politique | Nom descriptif | Identification interne de la règle. |
| | Statut | Activé | Active/désactive la politique. |
| | Méthodes de paiement affectées | Sélectionnez les méthodes pertinentes | Spécifie les passerelles de paiement que cette politique contrôle. |
| | Type de politique | Masquer | Détermine si les conditions *masquent* ou *affichent* les méthodes sélectionnées. |
| | Constructeur de conditions | Varie selon la règle | Définit les critères (par exemple, total du panier, groupe de clients) pour que la politique s'applique. |
| | Message d'indisponibilité | Texte clair et informatif | Message affiché aux clients lorsqu'une méthode de paiement est masquée. |
| **Journal d'audit** | Entrées de journal | N/A | Fournit un historique des évaluations de politiques. |
| | Filtres | N/A | Aide à rechercher et analyser des événements de journal spécifiques. |
| **Simulateur** | Entrées de simulation | N/A | Permet de tester les politiques avec divers scénarios client/panier. |
| | Résultats de simulation | N/A | Affiche les méthodes de paiement qui seraient disponibles/indisponibles pour le scénario simulé. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : Une méthode de paiement n'apparaît pas, mais je n'ai aucune politique configurée pour la masquer. Quel est le problème ?**
R : Tout d'abord, vérifiez le **Journal d'audit** du module pour toute entrée liée à cette méthode de paiement et à ce client. Le journal vous indiquera si une politique l'a *effectivement* masquée. Si ce n'est pas le cas, le problème pourrait être en dehors de ce module :
\* La méthode de paiement elle-même est-elle activée dans **Paiement > Méthodes de paiement** ?
\* Y a-t-il des restrictions définies directement sur le module de paiement (par exemple, restrictions de pays, de devise, de groupe dans la propre configuration du module de paiement) ?
\* Videz votre cache PrestaShop (**Paramètres avancés > Performances**).

**Q : Mes politiques ne semblent pas fonctionner. Que dois-je faire ?**
R :
1. **Vérifiez le statut de la politique :** Assurez-vous que la politique est « Activée » sur l'écran **Politiques**.
2. **Utilisez le simulateur :** Allez dans **Paiement > Règles de méthodes de paiement > Simulateur** et saisissez les conditions exactes que vous testez. Voyez ce que le simulateur prédit. C'est le moyen le plus rapide de déboguer vos conditions.
3. **Examinez les conditions :** Vérifiez attentivement votre logique « ET » et « OU ». Une seule condition incorrecte peut empêcher le déclenchement de toute la politique.
4. **Vérifiez les méthodes de paiement affectées :** Assurez-vous que la méthode de paiement que vous vous attendez à voir affectée est réellement sélectionnée dans la politique.
5. **Videz le cache :** Videz toujours votre cache PrestaShop (**Paramètres avancés > Performances**) après avoir apporté des modifications importantes aux paramètres ou aux politiques du module.

**Q : Comment gérer plusieurs politiques qui affectent la même méthode de paiement ?**
R : Le module évalue toutes les politiques actives.
\* Si plusieurs politiques « Masquer » s'appliquent à la même méthode de paiement, et que *l'une d'entre elles* se déclenche, la méthode de paiement sera masquée.
\* Si plusieurs politiques « Afficher » s'appliquent à la même méthode de paiement, et que *l'une d'entre elles* se déclenche, la méthode de paiement sera affichée.
\* **Résolution des conflits :** Si une politique dit « Afficher » et une autre dit « Masquer » pour la même méthode de paiement dans les mêmes conditions, le module a une stratégie de fusion définie (généralement, « Masquer » a la priorité pour assurer la sécurité et prévenir une disponibilité involontaire). Utilisez le **Simulateur** et le **Journal d'audit** pour comprendre le résultat exact des politiques conflictuelles.

**Q : Puis-je traduire le « Message d'indisponibilité » pour différentes langues ?**
R : Oui, lors de la modification d'une politique, le champ « Message d'indisponibilité » aura généralement un sélecteur de langue (une icône de drapeau) à côté. Cliquez sur le drapeau pour saisir les traductions pour chaque langue activée dans votre boutique.

**Q : Mon thème personnalisé n'affiche pas correctement les messages d'indisponibilité. Que puis-je faire ?**
R : Cela indique généralement un conflit CSS ou une surcharge de modèle manquante dans votre thème.
\* **Vérifiez `front.css` :** Le module inclut son propre `front.css` pour le style de base. Votre thème pourrait le surcharger.
\* **Inspecter l'élément :** Utilisez les outils de développement de votre navigateur (F12) pour inspecter la zone où le message devrait apparaître. Recherchez les règles CSS qui pourraient le masquer ou le mal positionner.
\* **Contactez le développeur du thème :** Si vous n'êtes pas à l'aise avec le CSS, contactez le développeur de votre thème ou un expert PrestaShop pour obtenir de l'aide. Ils peuvent vous aider à intégrer le style du module à votre thème.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module Règles de Méthodes de Paiement Conditionnelles suit un modèle de conception robuste et orienté objet au sein du framework MVC de PrestaShop. Il utilise intensivement `ObjectModel` pour la gestion des politiques et des journaux d'audit, une structure `ConditionTree` dédiée pour l'évaluation de règles complexes, et un `PaymethodrulesEngine` pour appliquer ces règles à l'étape de paiement. Le module injecte sa logique principalement via des hooks, spécifiquement `actionPaymentOptionsModifier` (ou similaire pour les anciennes versions de PS) pour manipuler la liste des méthodes de paiement disponibles. Les contrôleurs d'administration fournissent une interface utilisateur riche pour la gestion des politiques, la simulation et l'audit.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `controllers/front/index.php`
  - **Nom de la classe :** `PaymethodrulesIndexModuleFrontController` (ou similaire, étendant généralement `ModuleFrontController`)
  - **Responsabilité :** Ce contrôleur peut servir de solution de repli ou de simple point d'entrée, mais la logique principale de modification des méthodes de paiement est généralement gérée via des hooks. Il pourrait être utilisé pour des requêtes AJAX spécifiques liées à l'évaluation des règles en front-office si nécessaire, bien que l'évaluation principale se produise lors du rendu des options de paiement.
- `controllers/front/simulate.php`
  - **Nom de la classe :** `PaymethodrulesSimulateModuleFrontController` (ou similaire, étendant `ModuleFrontController`)
  - **Responsabilité :** Bien que le simulateur principal soit dans le BO, un contrôleur front pourrait exister pour une simulation front-end simplifiée ou pour exposer les résultats de simulation via AJAX à des fins de débogage.

#### Contrôleurs d'administration Back-Office

- `controllers/admin/AdminPaymethodrulesAuditLog.php`
  - **Nom de la classe :** `AdminPaymethodrulesAuditLogController` (étend `ModuleAdminController`)
  - **Nom de l'onglet :** Règles de méthodes de paiement -> Journal d'audit
  - **Entité gérée :** `PaymethodrulesAuditLog` (mappée à la table `ps_paymethodrules_log`)
  - **Responsabilité :** Gère l'affichage et le filtrage des entrées du journal d'audit. Il utilise `HelperList` pour rendre la vue en grille et fournit des actions pour afficher les détails du journal.
- `controllers/admin/AdminPaymethodrulesPolicies.php`
  - **Nom de la classe :** `AdminPaymethodrulesPoliciesController` (étend `ModuleAdminController`)
  - **Nom de l'onglet :** Règles de méthodes de paiement -> Politiques
  - **Entité gérée :** `PaymethodrulesPolicy` (mappée à la table `ps_paymethodrules_policy`)
  - **Responsabilité :** C'est le contrôleur central pour la gestion des politiques de paiement. Il gère :
    - La liste des politiques à l'aide de `HelperList`.
    - L'ajout/modification de politiques à l'aide de `HelperForm` avec un rendu de champ complexe pour le constructeur de conditions.
    - L'activation/désactivation, la duplication et la suppression de politiques.
    - La gestion de l'import/export JSON des politiques.
- `controllers/admin/index.php`
  - **Nom de la classe :** `AdminPaymethodrulesDashboardController` (ou similaire, étend `ModuleAdminController`)
  - **Nom de l'onglet :** Règles de méthodes de paiement -> Tableau de bord (ou lien de configuration du module principal)
  - **Entité gérée :** N/A (vue du tableau de bord)
  - **Responsabilité :** Fournit le point d'entrée principal et la vue du tableau de bord pour le module dans le Back Office. Il agrège les informations d'autres contrôleurs (par exemple, le nombre de politiques, les entrées de journal récentes) et fournit la navigation. Il utilise généralement des templates Smarty pour le rendu des widgets du tableau de bord.

### 4.3 Classes et modèles principaux (`classes/`)

- `classes/index.php` : Fichier vide standard pour empêcher la liste des répertoires.
- `classes/PaymethodrulesAdmin.php` : Probablement une classe d'aide pour les fonctions courantes liées à l'administration, telles que l'enregistrement de menus, la gestion des onglets ou la logique de rendu de formulaire partagée.
- `classes/PaymethodrulesAuditLog.php`
  - **Étend :** `ObjectModel`
  - **Table de base de données :** `ps_paymethodrules_log`
  - **Champs `$definition` :** `id_paymethodrules_log`, `id_cart`, `id_customer`, `id_shop`, `context_data` (JSON), `policies_applied` (JSON), `payment_methods_before` (JSON), `payment_methods_after` (JSON), `date_add`.
  - **Méthodes publiques clés :** Méthodes pour enregistrer des événements, récupérer des entrées de journal et éventuellement nettoyer les anciens journaux.
- `classes/PaymethodrulesCompatibility.php` : Gère les couches de compatibilité pour différentes versions de PrestaShop (par exemple, différences dans les noms de hook, les structures d'objets ou les fonctions `Tools`).
- `classes/PaymethodrulesCondition.php`
  - **Étend :** `ObjectModel` (ou une classe de base pour les conditions)
  - **Table de base de données :** `ps_paymethodrules_condition` (si les conditions sont stockées individuellement)
  - **Champs `$definition` :** `id_paymethodrules_condition`, `id_paymethodrules_policy`, `type`, `operator`, `value`, `id_parent_group`.
  - **Méthodes publiques clés :** Méthodes pour définir les types de conditions, les opérateurs et les valeurs. Fait partie de la structure de l'arbre de conditions.
- `classes/PaymethodrulesConditionEvaluator.php` : Contient la logique principale pour évaluer une seule `PaymethodrulesCondition` par rapport à un contexte donné (panier, client, etc.).
- `classes/PaymethodrulesConditionGroup.php`
  - **Étend :** `ObjectModel` (ou une classe de base pour les groupes de conditions)
  - **Table de base de données :** `ps_paymethodrules_condition_group` (si les groupes sont stockés individuellement)
  - **Champs `$definition` :** `id_paymethodrules_condition_group`, `id_paymethodrules_policy`, `operator` (`AND`/`OR`), `id_parent_group`.
  - **Méthodes publiques clés :** Gère une collection de conditions ou de groupes de conditions imbriqués, en appliquant la logique `AND`/`OR`.
- `classes/PaymethodrulesConditionTree.php` : Représente l'ensemble de la structure hiérarchique des conditions et des groupes de conditions pour une politique. Fournit des méthodes pour construire, parcourir et évaluer l'arbre.
- `classes/PaymethodrulesContext.php` : Une classe utilitaire qui encapsule toutes les données pertinentes nécessaires à l'évaluation des règles (panier actuel, client, adresse, transporteur, devise, etc.). Elle agit comme un fournisseur de données pour le `PaymethodrulesEngine`.
- `classes/PaymethodrulesDashboard.php` : Classe d'aide pour récupérer des données et préparer des statistiques/résumés pour la vue du tableau de bord du module.
- `classes/PaymethodrulesEngine.php` : La classe centrale responsable de l'orchestration de l'évaluation des règles.
  - **Méthodes publiques clés :** `evaluatePolicies(PaymethodrulesContext $context, array $payment_options)` : Prend le contexte actuel et une liste d'options de paiement disponibles, applique toutes les politiques actives et renvoie la liste modifiée. Il utilise `PaymethodrulesConditionTree` et `PaymethodrulesConditionEvaluator`.
- `classes/PaymethodrulesListRenderer.php` : Un helper spécialisé pour le rendu des listes dans le Back Office, étendant potentiellement `HelperList` ou fournissant un rendu de colonne personnalisé.
- `classes/PaymethodrulesLog.php` : Alias ou implémentation spécifique pour `PaymethodrulesAuditLog`.
- `classes/PaymethodrulesPolicy.php`
  - **Étend :** `ObjectModel`
  - **Table de base de données :** `ps_paymethodrules_policy`
  - **Champs `$definition` :** `id_paymethodrules_policy`, `name`, `active`, `policy_type` (`show`/`hide`), `payment_methods` (tableau JSON des noms de modules), `unavailable_message` (multilingue), `conditions_tree` (représentation JSON de l'arbre de conditions), `date_add`, `date_upd`.
  - **Méthodes publiques clés :** Méthodes pour enregistrer/charger les données de politique, récupérer les conditions associées et fournir une logique spécifique à la politique.
- `classes/PaymethodrulesPolicyDuplicator.php` : Classe utilitaire spécifiquement pour dupliquer les objets `PaymethodrulesPolicy`, garantissant que toutes les conditions et groupes associés sont également copiés correctement.
- `classes/PaymethodrulesPreset.php` : Gère probablement des ensembles prédéfinis de conditions ou de politiques qui peuvent être rapidement chargés par le marchand.
- `classes/PaymethodrulesRule.php` : Pourrait être un nom plus ancien ou alternatif pour `PaymethodrulesCondition` ou `PaymethodrulesPolicy`, ou une classe de base pour les composants de règle.
- `classes/PaymethodrulesTreeRepository.php` : Gère la persistance et la récupération de la structure `PaymethodrulesConditionTree`, la convertissant probablement en/depuis JSON pour le stockage dans l'objet `PaymethodrulesPolicy`.

### 4.4 Actifs JavaScript (`views/js/`)

- `paymethodrules/lib/searchTool/views/js/autocomplete.js` : Fonctionnalité d'autocomplétion générique, probablement utilisée pour sélectionner des produits, des catégories ou d'autres entités dans le constructeur de conditions.
- `paymethodrules/lib/searchTool/views/views/js/autocomplete.js` : Version dupliquée ou spécifique du script d'autocomplétion.
- `paymethodrules/views/js/adminConditionBuilder.js` :
  - **Portée :** Back-office (écran de création/modification de politique).
  - **Fonctionnalité :** Gère la création, la modification et la suppression dynamiques des conditions et des groupes de conditions dans le formulaire de politique. Gère la logique « ET »/« OU », ajoute de nouvelles lignes de conditions, gère les changements de type de condition (par exemple, affichage de différents champs de saisie pour « Total du panier » vs « Produit »).
- `paymethodrules/views/js/adminPaymethodrulesDashboard.js` :
  - **Portée :** Back-office (écran du tableau de bord).
  - **Fonctionnalité :** Peut gérer les appels AJAX pour les widgets du tableau de bord, actualiser les données ou fournir des éléments interactifs sur le tableau de bord.
- `paymethodrules/views/js/adminPaymethodrulesSearchTool.js` :
  - **Portée :** Back-office (constructeur de conditions).
  - **Fonctionnalité :** Intègre la bibliothèque `autocomplete.js` pour rechercher et sélectionner des entités (produits, catégories, clients, transporteurs) lors de la construction de conditions.
- `paymethodrules/views/js/adminPaymethodrulesSimulator.js` :
  - **Portée :** Back-office (écran du simulateur).
  - **Fonctionnalité :** Capture les entrées utilisateur pour les critères de simulation, envoie des requêtes AJAX au contrôleur du simulateur et met à jour dynamiquement l'affichage avec la disponibilité simulée des méthodes de paiement.
- `paymethodrules/views/js/adminPolicyRules.js` :
  - **Portée :** Back-office (liste des politiques et écrans d'édition).
  - **Fonctionnalité :** JS général pour la gestion des politiques, tel que la gestion des bascules d'activation/désactivation, des actions de duplication et potentiellement la logique de soumission de formulaire pour les détails de la politique.
- `paymethodrules/views/js/checkout.js` :
  - **Portée :** Front-office (page de paiement).
  - **Fonctionnalité :** C'est crucial. Il écoute les changements dans le processus de paiement (par exemple, sélection de la méthode de livraison, changement d'adresse, mise à jour du panier) et peut déclencher des appels AJAX pour réévaluer la disponibilité des méthodes de paiement ou mettre à jour dynamiquement l'affichage des messages d'indisponibilité. Il garantit que les options de paiement sont toujours à jour.
- `paymethodrules/views/js/unavailableUi.js` :
  - **Portée :** Front-office (page de paiement).
  - **Fonctionnalité :** Gère l'affichage et le style du « message d'indisponibilité » pour les méthodes de paiement masquées. Il peut injecter dynamiquement le message, appliquer des classes CSS ou gérer des animations.

### 4.5 Feuilles de style CSS (`views/css/`)

- `paymethodrules/lib/searchTool/views/css/autocomplete.css` : Styles pour l'outil de recherche d'autocomplétion dans le Back Office.
- `paymethodrules/lib/searchTool/views/views/css/autocomplete.css` : Version dupliquée ou spécifique du CSS d'autocomplétion.
- `paymethodrules/views/css/admin_paymethodrules.css` :
  - **Portée :** Back-office (tous les écrans d'administration du module).
  - **Fonctionnalité :** Fournit le style pour la liste des politiques, le constructeur de conditions, le tableau de bord, le simulateur et le journal d'audit. Inclut des styles pour les éléments de formulaire, les tableaux et les composants d'interface utilisateur personnalisés spécifiques au module.
  - **Sélecteurs de classe CSS clés :** `.paymethodrules-policy-card`, `.condition-group`, `.condition-row`, `.paymethodrules-dashboard-widget`.
- `paymethodrules/views/css/front.css` :
  - **Portée :** Front-office (page de paiement).
  - **Fonctionnalité :** Fournit un style de base pour les messages de méthode de paiement indisponible ou toute indication visuelle liée aux options de paiement masquées sur la page de paiement.
  - **Sélecteurs de classe CSS clés :** `.paymethodrules-unavailable-message`, `.paymethodrules-hidden-payment`.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

- `paymethodrules/views/templates/hook/payment_top.tpl` :
  - **Hook :** `displayPaymentTop` (ou similaire, selon la version de PS)
  - **Bloc visuel :** Ce template pourrait être utilisé pour afficher un message général ou des informations liées aux règles de paiement en haut de la section de sélection de paiement. Cependant, l'interaction principale consiste généralement à modifier directement le tableau des options de paiement. Il pourrait également être utilisé pour injecter les scripts `checkout.js` et `unavailableUi.js`.

#### Templates d'administration (`views/templates/admin/`)

- `paymethodrules/lib/searchTool/views/scripts.tpl` : Inclut JS/CSS pour l'outil de recherche dans l'administration.
- `paymethodrules/lib/searchTool/views/views/scripts.tpl` : Version dupliquée ou spécifique des scripts de l'outil de recherche.
- `paymethodrules/views/templates/admin/auditPreview.tpl` : Rend la vue détaillée pour une seule entrée du journal d'audit, affichant le contexte, les politiques appliquées et les modifications des méthodes de paiement.
- `paymethodrules/views/templates/admin/dashboard.tpl` : Rend le tableau de bord principal du module, y compris les widgets pour le résumé des politiques, les journaux récents et les liens rapides.
- `paymethodrules/views/templates/admin/helpers/list/list_action_duplicate.tpl` : Template personnalisé pour le bouton d'action « dupliquer » dans le `HelperList` pour les politiques.
- `paymethodrules/views/templates/admin/policiesPreview.tpl` : Pourrait être utilisé pour un aperçu rapide des règles d'une politique sans entrer dans le formulaire d'édition complet, ou pour afficher les détails de la politique dans le journal d'audit.
- `paymethodrules/views/templates/admin/policyConditionBuilder.tpl` : Le template principal pour le rendu de l'interface dynamique du constructeur de conditions dans le formulaire d'ajout/modification de politique. Il inclut des partiels pour les conditions et les groupes individuels.
- `paymethodrules/views/templates/admin/policyRuleCard.tpl` : Rend une seule politique sous forme de carte ou de ligne dans une liste, potentiellement utilisée dans le tableau de bord ou une vue de politique simplifiée.
- `paymethodrules/views/templates/admin/policyRulesTable.tpl` : Rend le tableau principal des politiques sur l'écran `AdminPaymethodrulesPolicies`.
- `paymethodrules/views/templates/admin/scopeSelector.tpl` : Un template réutilisable pour sélectionner la portée (par exemple, boutique, langue) dans les formulaires d'administration.

#### Templates Front-office (`views/templates/front/`)

- Aucun template de page front-office dédié n'est listé, ce qui indique que le module s'intègre principalement dans les templates de paiement existants en modifiant les données, plutôt que de rendre des pages entièrement nouvelles.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données

- `ps_paymethodrules_policy` : Stocke les définitions principales des politiques, y compris le nom, le statut, les méthodes de paiement affectées, le type de politique, les messages d'indisponibilité (multilingues) et la représentation JSON de l'arbre de conditions.
- `ps_paymethodrules_log` : Stocke les entrées du journal d'audit, y compris `id_cart`, `id_customer`, `context_data`, `policies_applied`, `payment_methods_before`, `payment_methods_after` et `date_add`.
- (Potentiellement) `ps_paymethodrules_condition` et `ps_paymethodrules_condition_group` si l'arbre de conditions est stocké de manière normalisée plutôt qu'entièrement en JSON dans `ps_paymethodrules_policy`. Le fichier `install.sql` le confirmera.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionPaymentOptionsModifier` | Pendant le processus de paiement, avant l'affichage des méthodes de paiement. | **Hook principal :** Le `PaymethodrulesEngine` du module est invoqué ici pour filtrer et modifier le tableau des options de paiement disponibles en fonction des politiques actives et du contexte actuel du panier. |
| `displayBackOfficeHeader` | À chaque chargement de page du Back Office. | Injecte le CSS et le JS spécifiques au module pour les contrôleurs d'administration (par exemple, `admin_paymethodrules.css`, `adminConditionBuilder.js`). |
| `displayHeader` | À chaque chargement de page du Front-Office. | Injecte le CSS et le JS spécifiques au module pour le Front Office (par exemple, `front.css`, `checkout.js`, `unavailableUi.js`), en particulier sur la page de paiement. |
| `moduleRoutes` | Pendant la compilation des routes de PrestaShop. | Enregistre les routes front-office et back-office personnalisées pour les contrôleurs du module (par exemple, `/module/paymethodrules/simulate`). |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration est chargé. | Injecte le CSS et le JS spécifiques au module pour le contrôleur d'administration actuel, garantissant que les actifs sont chargés uniquement lorsque cela est nécessaire. |
| `actionObject*AddAfter` / `actionObject*UpdateAfter` | Après l'ajout ou la mise à jour d'un objet (par exemple, `Cart`, `Customer`). | Potentiellement utilisé pour vider les caches internes ou déclencher une réévaluation si le module maintient des données en cache. |
| `displayAdminProductsExtra` (ou similaire) | Sur la page d'édition de produit dans le BO. | Pourrait être utilisé pour ajouter des conditions spécifiques au produit directement sur la page du produit, bien que non explicitement mentionné dans la liste des fichiers. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Règles de Méthodes de Paiement Conditionnelles », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour aider les marchands et les développeurs avec tout problème ou question concernant la fonctionnalité et l'intégration du module.
