---
title: "Règles de Méthodes de Livraison Conditionnelles - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Règles de Méthodes de Livraison Conditionnelles par MyPresta.eu."
sidebar:
  label: "Règles de Méthodes de Livraison Conditionnelles"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Conditional Shipping Method Rules sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-shipping-method-rules.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/conditional-shipping-method-rules/)
>
> ---


# Règles de Méthodes de Livraison Conditionnelles

## 1. Exigences et Compatibilité

-   **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilité PHP** : PHP 7.1 - 8.5
-   **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises, qui sont généralement disponibles sur la plupart des environnements d'hébergement PrestaShop modernes.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Vous pouvez accéder à cet écran en naviguant vers **Modules > Gestionnaire de modules**, en recherchant "Règles de Méthodes de Livraison Conditionnelles" et en cliquant sur "Configurer".

Cette page fournit les paramètres généraux du comportement du module.

-   **Activer le module :**
    -   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver toutes les fonctionnalités du module.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Toutes vos règles de livraison définies seront actives et influenceront les méthodes de livraison affichées au paiement.
        -   *Lorsqu'il est désactivé :* Le module sera inactif, et la sélection par défaut des méthodes de livraison de PrestaShop s'appliquera, ignorant toutes vos règles personnalisées.
    -   **Valeur recommandée :** OUI
    -   **Scénario / exemple marchand :** Vous pourriez le désactiver temporairement pendant la maintenance ou si vous avez besoin de revenir rapidement au comportement de livraison par défaut. Pour un fonctionnement normal, gardez-le activé.

-   **Stratégie de fusion pour plusieurs règles :**
    -   **Ce que fait ce paramètre :** Détermine comment le module combine les résultats de plusieurs règles actives lorsqu'elles s'appliquent à la même méthode de livraison.
    -   **Effet de la modification de ce paramètre :**
        -   *Option A (Prioriser "AFFICHER") :* Si *une* règle active dit "AFFICHER" un transporteur, il sera affiché, même si d'autres règles disent de le "MASQUER". C'est une stratégie plus permissive.
        -   *Option B (Prioriser "MASQUER") :* Si *une* règle active dit "MASQUER" un transporteur, il sera masqué, même si d'autres règles disent de l' "AFFICHER". C'est une stratégie plus restrictive.
        -   *Option C (Stratégie de fusion personnalisée 1) :* [Explication détaillée de la logique spécifique, par exemple, "Afficher uniquement si TOUTES les règles applicables disent AFFICHER"]
        -   *Option D (Stratégie de fusion personnalisée 2) :* [Explication détaillée de la logique spécifique]
        -   *Option E (Stratégie de fusion personnalisée 3) :* [Explication détaillée de la logique spécifique]
    -   **Valeur recommandée :** Prioriser "MASQUER" (pour la sécurité, en s'assurant qu'aucun transporteur indésirable n'est affiché). Cependant, cela dépend fortement de votre configuration de règles spécifique.
    -   **Scénario / exemple marchand :** Si vous avez une règle pour "AFFICHER" la livraison gratuite pour les commandes de plus de 100 €, mais une autre règle pour "MASQUER" la livraison gratuite pour un produit spécifique, la stratégie de fusion détermine quelle règle l'emporte. "Prioriser MASQUER" masquerait la livraison gratuite pour ce produit, même si la commande est supérieure à 100 €.

-   **Afficher les messages de méthode de livraison indisponible :**
    -   **Ce que fait ce paramètre :** Contrôle si les clients voient une explication lorsqu'une méthode de livraison est masquée par une règle.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Si un transporteur est masqué, un message (que vous définissez par règle) sera affiché au client, expliquant pourquoi il n'est pas disponible.
        -   *Lorsqu'il est désactivé :* Les transporteurs masqués disparaîtront simplement de la liste sans aucune explication.
    -   **Valeur recommandée :** OUI (Améliore l'expérience client et réduit la confusion).
    -   **Scénario / exemple marchand :** Si la "Livraison Express" est masquée parce que le panier du client contient un "Article Fragile" qui ne peut pas être expédié via express, l'activation de ce paramètre affichera un message comme "La livraison express n'est pas disponible pour les articles fragiles."

-   **Rétention du journal d'audit (jours) :**
    -   **Ce que fait ce paramètre :** Définit la durée pendant laquelle le module conserve les enregistrements des évaluations de règles et de leurs résultats dans le journal d'audit.
    -   **Effet de la modification de ce paramètre :**
        -   *Définir un nombre (par exemple, 30) :* Le module supprimera automatiquement les entrées de journal plus anciennes que ce nombre de jours.
        -   *Définir à 0 ou vide :* Le module conservera toutes les entrées de journal indéfiniment (peut entraîner une base de données volumineuse au fil du temps).
    -   **Valeur recommandée :** 30-90 jours (suffisant pour le dépannage sans croissance excessive de la base de données).
    -   **Scénario / exemple marchand :** Si un client se plaint de ne pas voir une méthode de livraison spécifique, vous pouvez consulter le journal d'audit pour les évaluations récentes. La conservation des journaux pendant 30 jours vous permet d'enquêter sur les problèmes récents sans stocker des années de données.

-   **Activer le simulateur de paiement :**
    -   **Ce que fait ce paramètre :** Active un outil dans le back-office qui vous permet de tester vos règles de livraison en simulant différents scénarios de clients et de paniers.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* L'onglet "Simulateur de paiement" apparaîtra dans la configuration du module, offrant un environnement de test puissant.
        -   *Lorsqu'il est désactivé :* Le simulateur ne sera pas disponible.
    -   **Valeur recommandée :** OUI (Essentiel pour tester des règles complexes avant le déploiement).
    -   **Scénario / exemple marchand :** Avant de lancer une nouvelle promotion de livraison, vous pouvez utiliser le simulateur pour vous assurer que vos règles affichent/masquent correctement la livraison promotionnelle pour diverses valeurs de panier, groupes de clients et adresses.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 Politiques de livraison (Back Office > Modules > Règles de Méthodes de Livraison Conditionnelles > Politiques de livraison)
C'est l'écran principal où vous définissez et gérez toutes vos règles de livraison.

-   **Nom de l'écran et emplacement du menu :** **Règles de Méthodes de Livraison Conditionnelles > Politiques de livraison** (situé dans la section "Modules" de votre menu de back office PrestaShop).
-   **Actions et paramètres disponibles :**
    -   **Liste des politiques :** Un tableau affichant toutes vos politiques de livraison créées. Chaque politique a un nom, un statut (activé/désactivé) et des actions.
    -   **Ajouter une nouvelle politique :** Un bouton pour créer une nouvelle politique de livraison.
    -   **Modifier la politique :** Cliquez sur une politique existante pour modifier ses règles, conditions et paramètres.
    -   **Dupliquer la politique :** Créez rapidement une copie d'une politique existante, utile pour apporter des variations mineures.
    -   **Activer/Désactiver la politique :** Basculez le statut actif d'une politique sans la supprimer.
    -   **Supprimer la politique :** Supprimez une politique de manière permanente.
    -   **Formulaire de configuration de la politique (lors de l'ajout/modification) :**
        -   **Nom de la politique :** Un nom descriptif pour votre ensemble de règles (par exemple, "Livraison gratuite au-delà de 100 €", "Restrictions de livraison express").
        -   **Statut :** Activez ou désactivez cette politique spécifique.
        -   **Priorité :** Si plusieurs politiques s'appliquent, cela détermine l'ordre dans lequel elles sont évaluées. Les nombres inférieurs signifient une priorité plus élevée.
        -   **Transporteurs cibles :** Sélectionnez les transporteurs spécifiques que cette politique affectera.
        -   **Action (AFFICHER/MASQUER) :** Choisissez si cette politique doit *afficher* les transporteurs sélectionnés si les conditions sont remplies, ou les *masquer*.
        -   **Message d'indisponibilité :** Si vous avez choisi "MASQUER" et que "Afficher les messages de méthode de livraison indisponible" est activé dans la configuration principale, c'est le message que les clients verront (multilingue).
        -   **Constructeur de conditions :** C'est ici que vous définissez la partie "SI" de votre règle. Vous pouvez ajouter plusieurs groupes de conditions (logique ET/OU) basés sur :
            -   Total du panier, poids, quantité
            -   Produits ou catégories spécifiques dans le panier
            -   Groupe de clients, pays, état, code postal
            -   Date et heure
            -   Et bien d'autres critères.
-   **Effet des modifications :**
    -   L'ajout, la modification ou la suppression de politiques a un impact direct sur les méthodes de livraison présentées aux clients au paiement, en fonction des conditions définies.
    -   La modification du statut d'une politique (activer/désactiver) active ou désactive immédiatement son effet sur le front office.
    -   L'ajustement de la priorité peut résoudre les conflits si plusieurs politiques s'appliquent au même transporteur.
-   **Flux de travail recommandé pour la gestion quotidienne du magasin :**
    1.  **Planifiez votre règle :** Avant de créer, définissez clairement ce que vous voulez accomplir (par exemple, "Si le total du panier > 50 € ET le client est aux États-Unis, ALORS AFFICHER 'Livraison Standard'").
    2.  **Créez une nouvelle politique :** Donnez-lui un nom clair.
    3.  **Sélectionnez les transporteurs cibles :** Choisissez les transporteurs que cette politique affectera.
    4.  **Définissez l'action :** Décidez si la politique doit AFFICHER ou MASQUER ces transporteurs.
    5.  **Construisez les conditions :** Utilisez le constructeur de conditions intuitif pour configurer vos déclarations "SI". Utilisez "Ajouter un groupe de conditions" pour la logique OU et "Ajouter une condition" dans un groupe pour la logique ET.
    6.  **Testez avec le simulateur :** Surtout, utilisez le "Simulateur de paiement" (voir section suivante) pour vérifier que vos règles fonctionnent comme prévu pour divers scénarios.
    7.  **Activez :** Une fois testée, activez la politique.

#### 2.2.2 Journal d'audit (Back Office > Modules > Règles de Méthodes de Livraison Conditionnelles > Journal d'audit)
Cet écran fournit un historique de la façon dont vos règles de livraison ont été évaluées.

-   **Nom de l'écran et emplacement du menu :** **Règles de Méthodes de Livraison Conditionnelles > Journal d'audit** (situé dans la section "Modules" de votre menu de back office PrestaShop).
-   **Actions et paramètres disponibles :**
    -   **Tableau des journaux :** Une liste détaillée de chaque fois que le module a évalué les règles de livraison pour le panier d'un client.
    -   **Colonnes :** Inclut des informations telles que :
        -   Date et heure de l'évaluation
        -   ID client (si connecté)
        -   ID panier
        -   Politiques appliquées : Quelles politiques ont été prises en compte.
        -   Résultat : Quels transporteurs ont été affichés/masqués et pourquoi.
        -   Instantané de commande : Un lien pour afficher l'état exact du panier au moment de l'évaluation.
    -   **Filtrage et tri :** Fonctionnalités de liste PrestaShop standard pour filtrer par date, client ou ID panier.
-   **Effet des modifications :** Il s'agit d'un écran en lecture seule pour la surveillance et le dépannage. Vous ne pouvez pas apporter de modifications directes ici, mais les données vous aident à comprendre comment vos règles fonctionnent.
-   **Flux de travail recommandé pour la gestion quotidienne du magasin :**
    -   Utilisez ce journal pour diagnostiquer les problèmes signalés par les clients (par exemple, "Je n'ai pas vu la livraison gratuite"). Vous pouvez trouver leur ID de panier ou ID de client et voir exactement quelles règles ont été appliquées et quel a été le résultat.
    -   Examinez périodiquement le journal pour vous assurer que les règles se déclenchent comme prévu, surtout après avoir apporté des modifications aux politiques.

#### 2.2.3 Simulateur de paiement (Back Office > Modules > Règles de Méthodes de Livraison Conditionnelles > Simulateur de paiement)
Cet outil puissant vous permet de tester vos règles de livraison sans passer de commande réelle.

-   **Nom de l'écran et emplacement du menu :** **Règles de Méthodes de Livraison Conditionnelles > Simulateur de paiement** (situé dans la section "Modules" de votre menu de back office PrestaShop, visible uniquement si "Activer le simulateur de paiement" est actif dans la configuration principale).
-   **Actions et paramètres disponibles :**
    -   **Sélection du client :** Choisissez un client existant dans votre boutique, ou simulez un invité.
    -   **Sélection de l'adresse :** Sélectionnez une adresse spécifique pour le client choisi, ou saisissez manuellement les détails de l'adresse.
    -   **Contenu du panier :** Ajoutez des produits, des quantités et des combinaisons spécifiques pour simuler le panier d'un client.
    -   **Bouton Simuler :** Cliquez dessus pour lancer la simulation.
    -   **Affichage des résultats :** Affiche les méthodes de livraison qui seraient disponibles (et celles qui seraient masquées avec leurs messages) pour le scénario simulé. Il détaille également les politiques qui ont été appliquées et pourquoi.
-   **Effet des modifications :** Cet écran ne modifie aucune donnée de la boutique en direct. C'est purement un environnement de test.
-   **Flux de travail recommandé pour la gestion quotidienne du magasin :**
    -   **Avant d'activer de nouvelles politiques :** Testez-les toujours minutieusement ici.
    -   **Dépannage :** Recréez le problème signalé par un client en simulant son panier et son adresse exacts pour voir pourquoi un transporteur a été ou n'a pas été affiché.
    -   **Scénarios complexes :** Testez les cas limites, comme les valeurs de commande minimales/maximales, les combinaisons de produits spécifiques ou les différents groupes de clients.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
|---|---|---|---|
| **Configuration du module** | Activer le module | OUI | Interrupteur principal pour la fonctionnalité du module. |
| | Stratégie de fusion pour plusieurs règles | Prioriser "MASQUER" | Comment les règles conflictuelles sont résolues (AFFICHER vs. MASQUER). |
| | Afficher les messages de méthode de livraison indisponible | OUI | Afficher des explications pour les transporteurs masqués aux clients. |
| | Rétention du journal d'audit (jours) | 30-90 | Durée de conservation des journaux d'évaluation des règles. |
| | Activer le simulateur de paiement | OUI | Active l'outil de test dans le back office. |
| **Politiques de livraison** | Nom de la politique | Nom descriptif | Identifie l'ensemble de règles. |
| | Statut | Activé | Active/désactive cette politique spécifique. |
| | Priorité | Nombre inférieur = priorité plus élevée | Détermine l'ordre d'évaluation pour les politiques conflictuelles. |
| | Transporteurs cibles | Transporteurs spécifiques | Quelles méthodes de livraison cette politique affecte. |
| | Action (AFFICHER/MASQUER) | AFFICHER/MASQUER | Afficher ou masquer les transporteurs cibles si les conditions sont remplies. |
| | Message d'indisponibilité | Texte personnalisé (multilingue) | Message affiché lorsque le transporteur est masqué (si activé). |
| | Constructeur de conditions | Varie | Définit les critères "SI" pour que la politique s'applique. |
| **Journal d'audit** | (Toutes les colonnes) | N/A (Lecture seule) | Fournit des enregistrements historiques des évaluations de règles pour le dépannage. |
| **Simulateur de paiement** | (Tous les champs) | N/A (Outil de test) | Permet de simuler des scénarios client/panier pour tester les règles. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Mes règles ne fonctionnent pas, ou je vois des options de livraison inattendues. Que dois-je faire ?**
R1 :
1.  **Vérifier le statut du module :** Assurez-vous que le paramètre "Activer le module" sur la page de configuration principale est défini sur OUI.
2.  **Vérifier le statut de la politique :** Allez dans "Politiques de livraison" et vérifiez que les politiques spécifiques que vous attendez être actives sont activées.
3.  **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache". Parfois, PrestaShop met en cache d'anciennes configurations.
4.  **Utiliser le simulateur de paiement :** C'est votre meilleur ami ! Recréez le scénario exact (client, adresse, contenu du panier) dans le simulateur. Il vous montrera exactement quelles règles ont été appliquées et pourquoi, vous aidant à identifier le problème.
5.  **Examiner le journal d'audit :** Si un client a signalé un problème, vérifiez le "Journal d'audit" pour son ID de panier/client afin de voir comment les règles ont été évaluées pour sa commande spécifique.
6.  **Stratégie de fusion :** Examinez votre paramètre "Stratégie de fusion pour plusieurs règles". Si vous avez des règles AFFICHER et MASQUER conflictuelles, ce paramètre détermine le résultat.

**Q2 : Pourquoi mon "Message d'indisponibilité" personnalisé ne s'affiche-t-il pas ?**
R2 :
1.  **Activer l'affichage des messages :** Sur la page de configuration principale du module, assurez-vous que "Afficher les messages de méthode de livraison indisponible" est défini sur OUI.
2.  **Action de la politique :** Vérifiez que l'"Action" de la politique est définie sur "MASQUER" pour le transporteur cible. Les messages ne s'affichent que lorsqu'un transporteur est masqué.
3.  **Contenu du message :** Assurez-vous d'avoir réellement saisi un message dans le champ "Message d'indisponibilité" pour la politique spécifique, et qu'il est traduit pour les langues pertinentes.

**Q3 : Le module ralentit mon paiement. Est-ce normal ?**
R3 : Le module est hautement optimisé, mais des règles très complexes (par exemple, des centaines de conditions, de nombreuses politiques) peuvent ajouter une légère surcharge.
1.  **Simplifier les règles :** Examinez vos politiques. Peuvent-elles être combinées ou simplifiées ?
2.  **Prioriser :** Assurez-vous que vos règles les plus fréquemment déclenchées ont une priorité plus élevée (nombre inférieur) afin qu'elles soient évaluées en premier.
3.  **Taille de la base de données :** Vérifiez votre paramètre "Rétention du journal d'audit". S'il est configuré pour conserver les journaux indéfiniment, une très grande table de journaux peut avoir un impact sur les performances. Définissez-le sur un nombre de jours raisonnable (par exemple, 30-90).

**Q4 : Comment m'assurer que mon thème personnalisé affiche correctement les options de livraison ?**
R4 : Le module s'intègre au processus de paiement standard de PrestaShop.
1.  **Hooks standard :** Le module utilise les hooks standard de PrestaShop. Si votre thème personnalise fortement le paiement, assurez-vous qu'il appelle toujours correctement les hooks `displayCarrierList` ou similaires où les options de livraison sont rendues.
2.  **Conflits CSS :** Si l'affichage semble incorrect (par exemple, les messages sont mal alignés), il peut y avoir un conflit CSS avec votre thème. Utilisez les outils de développement de votre navigateur (F12) pour inspecter les éléments et identifier les règles CSS conflictuelles. Vous devrez peut-être ajouter du CSS personnalisé à votre thème pour remplacer les styles du module ou du thème.
3.  **Contacter le support :** Si vous utilisez un thème fortement personnalisé et rencontrez des problèmes d'affichage persistants, fournissez les détails au support MyPresta.eu.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture
Le module "Règles de Méthodes de Livraison Conditionnelles" (`shipmethodrules`) est construit en suivant le modèle MVC (Modèle-Vue-Contrôleur) de PrestaShop, en utilisant fortement `ObjectModel` pour la persistance des données et un moteur de politiques personnalisé pour l'évaluation des règles. Il introduit plusieurs contrôleurs d'administration personnalisés pour gérer les politiques, afficher les journaux d'audit et simuler des scénarios de paiement. La logique principale tourne autour des objets `ShipmethodrulesPolicy`, qui encapsulent les entités `ShipmethodrulesConditionGroup` et `ShipmethodrulesCondition`, permettant une logique complexe imbriquée ET/OU. Le `ShipmethodrulesEngine` est responsable de l'évaluation de ces politiques par rapport à un `ShipmethodrulesContext` donné (représentant le panier, le client et l'adresse actuels) et de la détermination de la visibilité des transporteurs.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office
-   `controllers/front/index.php` :
    -   Nom de la classe : `ShipmethodrulesIndexModuleFrontController`
    -   Classe parente : `ModuleFrontController`
    -   Responsabilité : Probablement un espace réservé ou un contrôleur de base. Dans de nombreux modules, cela pourrait gérer la configuration initiale ou la redirection si une page front-office dédiée est nécessaire. Pour ce module, la logique front-office principale est intégrée via des hooks dans le processus de paiement.
-   `controllers/front/simulate.php` :
    -   Nom de la classe : `ShipmethodrulesSimulateModuleFrontController`
    -   Classe parente : `ModuleFrontController`
    -   Responsabilité : Gère les requêtes AJAX liées au simulateur de paiement. Il reçoit les données simulées du panier, du client et de l'adresse, puis utilise le `ShipmethodrulesEngine` pour évaluer les politiques et renvoie la visibilité des transporteurs résultante.
-   `controllers/front/visibility.php` :
    -   Nom de la classe : `ShipmethodrulesVisibilityModuleFrontController`
    -   Classe parente : `ModuleFrontController`
    -   Responsabilité : Ce contrôleur est crucial pour les mises à jour en temps réel sur la page de paiement. Il répond aux requêtes AJAX (par exemple, lorsqu'un client change d'adresse ou de contenu de panier) pour réévaluer les règles de livraison et renvoyer la liste mise à jour des transporteurs disponibles et leurs messages associés.

#### Contrôleurs d'administration Back-Office
-   `controllers/admin/AdminShipmethodrulesAuditLog.php` :
    -   Nom de la classe : `AdminShipmethodrulesAuditLogController`
    -   Classe parente : `ModuleAdminController`
    -   Nom de l'onglet : "Journal d'audit"
    -   Entité gérée : `ShipmethodrulesLog`
    -   Responsabilité : Gère l'affichage et le filtrage de la table `ps_shipmethodrules_log`. Il fournit une vue en grille de toutes les évaluations de règles, y compris les détails sur le panier, le client, les politiques appliquées et le résultat final (quels transporteurs ont été affichés/masqués).
-   `controllers/admin/AdminShipmethodrulesPolicies.php` :
    -   Nom de la classe : `AdminShipmethodrulesPoliciesController`
    -   Classe parente : `ModuleAdminController`
    -   Nom de l'onglet : "Politiques de livraison"
    -   Entité gérée : `ShipmethodrulesPolicy`
    -   Responsabilité : C'est le contrôleur principal pour la gestion des politiques de livraison. Il gère la liste, l'ajout, la modification, la duplication, l'activation/désactivation et la suppression des objets `ShipmethodrulesPolicy`. Il orchestre également l'interface du constructeur de conditions.
-   `controllers/admin/index.php` :
    -   Nom de la classe : `ShipmethodrulesAdminController` (ou similaire, s'il s'agit d'un contrôleur de base pour la section d'administration du module)
    -   Classe parente : `ModuleAdminController`
    -   Responsabilité : Agit souvent comme un répartiteur ou un contrôleur par défaut pour l'entrée principale du menu d'administration du module, redirigeant vers la configuration principale ou la liste des politiques.

### 4.3 Classes et modèles principaux (`classes/`)

-   `classes/ShipmethodrulesAdmin.php` : Probablement une classe d'aide pour les fonctionnalités courantes liées à l'administration ou les statistiques du tableau de bord.
-   `classes/ShipmethodrulesAuditLog.php` : Étend `ObjectModel`. Mappe à la table `ps_shipmethodrules_log`. Stocke les détails de chaque événement d'évaluation de règle à des fins d'audit.
    -   Champs `$definition` : `id_cart`, `id_customer`, `id_address_delivery`, `policies_applied`, `carriers_visibility`, `timestamp`.
-   `classes/ShipmethodrulesCompatibility.php` : Fournit des méthodes pour gérer les différences entre PrestaShop 1.7, 8 et 9, assurant la compatibilité inter-versions pour les fonctionnalités de base (par exemple, l'enregistrement des hooks, l'accès à la configuration).
-   `classes/ShipmethodrulesCondition.php` : Étend `ObjectModel`. Représente une seule condition au sein d'un groupe de conditions (par exemple, "Total du panier > 100 €").
    -   Champs `$definition` : `id_shipmethodrules_condition_group`, `type`, `operator`, `value`, `id_product`, `id_category`, etc.
-   `classes/ShipmethodrulesConditionEvaluator.php` : Contient la logique pour évaluer une seule `ShipmethodrulesCondition` par rapport au `ShipmethodrulesContext` actuel.
-   `classes/ShipmethodrulesConditionGroup.php` : Étend `ObjectModel`. Représente un groupe de conditions liées par un opérateur ET. Plusieurs groupes peuvent être liés par un opérateur OU au sein d'une politique.
    -   Champs `$definition` : `id_shipmethodrules_policy`, `logic_operator` (implicitement ET pour les conditions internes, OU pour les groupes).
-   `classes/ShipmethodrulesConditionTree.php` : Gère la structure hiérarchique des conditions et des groupes de conditions pour une politique, facilitant leur stockage et leur récupération.
-   `classes/ShipmethodrulesContext.php` : Un objet qui encapsule toutes les données pertinentes pour l'évaluation des règles : `Cart`, `Customer`, `Address`, `Currency`, `Language` actuels, etc. Cela fournit une interface cohérente pour le `ShipmethodrulesEngine`.
-   `classes/ShipmethodrulesDashboard.php` : Classe d'aide pour générer des statistiques ou des résumés du tableau de bord liés à l'activité du module.
-   `classes/ShipmethodrulesEngine.php` : La classe centrale pour l'évaluation des règles. Elle prend un `ShipmethodrulesContext` et une liste d'objets `ShipmethodrulesPolicy`, applique la stratégie de fusion configurée et renvoie le statut de visibilité final pour chaque transporteur.
-   `classes/ShipmethodrulesListRenderer.php` : Rendu personnalisé pour les listes d'administration, ajoutant potentiellement des actions spécifiques (comme dupliquer) ou un formatage de colonne personnalisé.
-   `classes/ShipmethodrulesLog.php` : Alias ou implémentation spécifique pour `ShipmethodrulesAuditLog`.
-   `classes/ShipmethodrulesOrderSnapshot.php` : Capture et stocke un instantané de l'état d'une commande (panier, client, adresse) au moment de l'évaluation des règles, utile pour le débogage.
-   `classes/ShipmethodrulesPolicy.php` : Étend `ObjectModel`. Le modèle principal pour une règle de livraison. Il contient le nom de la politique, le statut, la priorité, les transporteurs cibles, l'action (AFFICHER/MASQUER), le message d'indisponibilité et une collection d'objets `ShipmethodrulesConditionGroup`.
    -   Champs `$definition` : `name`, `active`, `priority`, `action`, `unavailable_message`, `target_carriers`.
-   `classes/ShipmethodrulesPolicyDuplicator.php` : Gère la logique de duplication d'une `ShipmethodrulesPolicy`, y compris tous ses groupes de conditions et conditions associés.
-   `classes/ShipmethodrulesPreset.php` : Gère probablement des ensembles prédéfinis de conditions ou de politiques qui peuvent être rapidement appliqués.
-   `classes/ShipmethodrulesRule.php` : Une représentation plus générique d'une règle, éventuellement une classe de base abstraite ou une itération plus ancienne de `ShipmethodrulesPolicy`.
-   `classes/ShipmethodrulesTreeRepository.php` : Gère la persistance et la récupération de la structure de l'arbre de conditions.

### 4.4 Actifs JavaScript (`views/js/`)

-   `shipmethodrules/lib/searchTool/views/js/autocomplete.js` : Fonctionnalité d'autocomplétion générique, probablement utilisée pour rechercher des produits, des catégories ou des clients dans le constructeur de conditions.
-   `shipmethodrules/lib/searchTool/views/views/js/autocomplete.js` : Duplicata ou instance spécifique du script d'autocomplétion.
-   `shipmethodrules/views/js/adminConditionBuilder.js` : Gère la création, la modification et la suppression dynamiques des conditions et des groupes de conditions dans l'interface d'édition des politiques. Gère l'interface utilisateur complexe pour la construction de règles.
-   `shipmethodrules/views/js/adminPolicyRules.js` : JS spécifique pour le contrôleur `AdminShipmethodrulesPolicies`, gérant la liste des politiques, les actions en masse et potentiellement les interactions avec le constructeur de conditions.
-   `shipmethodrules/views/js/adminShipmethodrulesDashboard.js` : Scripts pour tous les widgets ou statistiques du tableau de bord affichés dans la section d'administration du module.
-   `shipmethodrules/views/js/adminShipmethodrulesSearchTool.js` : Intègre l'outil de recherche (autocomplétion) spécifiquement pour les formulaires d'administration du module.
-   `shipmethodrules/views/js/adminShipmethodrulesSimulator.js` : Alimente l'interface du "Simulateur de paiement", gérant la saisie de l'utilisateur pour le client, l'adresse et le panier, et effectuant des appels AJAX à `controllers/front/simulate.php`.
-   `shipmethodrules/views/js/checkout.js` : Script front-office injecté dans le processus de paiement. Il écoute les changements dans le panier ou l'adresse de livraison, puis effectue des appels AJAX à `controllers/front/visibility.php` pour mettre à jour dynamiquement les méthodes de livraison affichées.
-   `shipmethodrules/views/js/unavailableUi.js` : Gère l'affichage et le style des messages de méthode de livraison indisponible sur la page de paiement du front office.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `shipmethodrules/lib/searchTool/views/css/autocomplete.css` : Styles pour l'outil de recherche d'autocomplétion.
-   `shipmethodrules/lib/searchTool/views/views/css/autocomplete.css` : Duplicata ou instance spécifique des styles d'autocomplétion.
-   `shipmethodrules/views/css/admin_order_snapshot.css` : Styles pour l'affichage des détails de l'instantané de commande dans le journal d'audit ou le simulateur.
-   `shipmethodrules/views/css/admin_shipmethodrules.css` : Style général pour les interfaces back-office du module, y compris les listes de politiques, le constructeur de conditions et le simulateur.
-   `shipmethodrules/views/css/front.css` : Styles front-office pour l'affichage des messages de méthode de livraison indisponible ou la mise en évidence d'options de livraison spécifiques sur la page de paiement.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)
-   `shipmethodrules/views/templates/hook/carrier_guard.tpl` : Rend un champ de saisie caché ou un script pour "protéger" contre les sélections de transporteurs invalides, garantissant que seuls les transporteurs autorisés peuvent être soumis.
-   `shipmethodrules/views/templates/hook/carrier_list.tpl` : Remplace ou étend le template de liste de transporteurs par défaut dans le paiement pour appliquer les règles de visibilité et afficher les messages d'indisponibilité. C'est là que la liste filtrée des transporteurs est réellement rendue.

#### Templates d'administration (`views/templates/admin/`)
-   `shipmethodrules/views/templates/admin/auditPreview.tpl` : Template pour afficher un aperçu détaillé d'une entrée du journal d'audit.
-   `shipmethodrules/views/templates/admin/dashboard.tpl` : Template pour la configuration principale du module ou la vue du tableau de bord.
-   `shipmethodrules/views/templates/admin/helpers/list/list_action_duplicate.tpl` : Template personnalisé pour le bouton d'action "dupliquer" dans les listes d'administration (par exemple, pour les politiques).
-   `shipmethodrules/views/templates/admin/policiesPreview.tpl` : Template pour afficher un aperçu d'une politique de livraison.
-   `shipmethodrules/views/templates/admin/policyConditionBuilder.tpl` : Le template complexe qui rend l'interface utilisateur pour la construction des conditions (listes déroulantes, champs de saisie, logique ET/OU).
-   `shipmethodrules/views/templates/admin/policyRuleCard.tpl` : Rend une seule règle ou politique sous forme de carte dans une vue de liste.
-   `shipmethodrules/views/templates/admin/policyRulesTable.tpl` : Rend le tableau des politiques de livraison.
-   `shipmethodrules/views/templates/admin/scopeSelector.tpl` : Template pour sélectionner la portée d'une condition (par exemple, "Total du panier", "Groupe de clients").

#### Autres templates
-   `shipmethodrules/lib/searchTool/views/scripts.tpl` : Inclut le JavaScript pour l'outil de recherche.
-   `shipmethodrules/lib/searchTool/views/views/scripts.tpl` : Duplicata ou instance spécifique des scripts de l'outil de recherche.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données
-   `ps_shipmethodrules_policy` : Stocke les définitions principales des politiques de livraison (nom, statut actif, priorité, action, message d'indisponibilité, transporteurs cibles).
-   `ps_shipmethodrules_condition_group` : Stocke les groupes de conditions associés à une politique.
-   `ps_shipmethodrules_condition` : Stocke les conditions individuelles (type, opérateur, valeur, entités associées comme les ID de produit/catégorie).
-   `ps_shipmethodrules_log` : Stocke les entrées du journal d'audit des évaluations de règles (ID de panier, ID de client, horodatage, politiques appliquées, visibilité des transporteurs).
-   `ps_shipmethodrules_order_snapshot` : Stocke des instantanés détaillés des données de panier/commande pour les entrées du journal d'audit.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
|---|---|---|
| `displayHeader` | Dans la section `<head>` de toutes les pages front-office. | Injecte les fichiers CSS et JS nécessaires pour la fonctionnalité front-office (par exemple, `checkout.js`, `front.css`). |
| `displayCarrierList` | Sur la page de paiement, où les méthodes de livraison sont listées. | Le hook principal pour filtrer et rendre les méthodes de livraison disponibles en fonction des politiques définies. |
| `actionCarrierProcess` | Après la sélection d'un transporteur mais avant la validation de la commande. | Agit comme une "garde" pour revalider le transporteur sélectionné par rapport aux règles, empêchant la soumission d'un choix invalide. |
| `actionValidateOrder` | Après la validation réussie d'une commande. | Enregistre potentiellement la méthode de livraison finale choisie et les règles appliquées dans le journal d'audit. |
| `actionAdminControllerSetMedia` | Dans le back office, lorsqu'un contrôleur d'administration est chargé. | Injecte le CSS et le JS pour les interfaces d'administration du module (constructeur de politiques, simulateur, journal d'audit). |
| `actionObjectCarrierAddAfter` | Après l'ajout d'un nouveau transporteur. | Met potentiellement à jour les données internes du module ou les caches liés aux transporteurs. |
| `actionObjectCarrierUpdateAfter` | Après la mise à jour d'un transporteur. | Met potentiellement à jour les données internes du module ou les caches liés aux transporteurs. |
| `actionObjectCarrierDeleteAfter` | Après la suppression d'un transporteur. | Nettoie toutes les références au transporteur supprimé dans les politiques. |
| `displayBackOfficeHeader` | Dans l'en-tête de toutes les pages back-office. | Injecte le CSS/JS d'administration global ou des scripts spécifiques pour les pages d'administration du module. |

## 5. Support officiel et mises à jour
Pour les dernières mises à jour, corrections de bugs et support officiel du module "Règles de Méthodes de Livraison Conditionnelles", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour aider les marchands et les développeurs avec toutes les questions ou problèmes concernant la fonctionnalité et l'intégration du module.
