---
title: "Remises Conditionnelles sur les Commandes - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Remises Conditionnelles sur les Commandes par MyPresta.eu."
sidebar:
  label: "Remises Conditionnelles sur les Commandes - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Conditional Order Discounts sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-order-discounts.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/conditional-order-discounts/)
>
> ---


# Remises Conditionnelles sur les Commandes

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur "Configurer" vous mènera à la page principale des paramètres du module.

- **Activer les remises conditionnelles sur les commandes :**
  - **Ce que fait ce paramètre :** Il s'agit de l'interrupteur principal pour l'ensemble du module. Lorsqu'il est activé, la logique du module pour l'application des remises conditionnelles sera active sur votre boutique. Lorsqu'il est désactivé, aucune remise conditionnelle ne sera appliquée, quelles que soient les politiques que vous avez créées.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module commencera à évaluer vos politiques de remise définies et à appliquer des remises ou des cadeaux gratuits aux paniers des clients lorsqu'ils sont éligibles.
    - *Lorsqu'il est désactivé :* Toutes les politiques de remise conditionnelle créées avec ce module seront ignorées, et aucune remise ne sera appliquée.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** Vous venez de terminer la configuration de votre première politique "Achetez 2, obtenez 1 gratuit" et souhaitez la mettre en ligne. Vous activeriez ce paramètre. Si vous devez suspendre temporairement toutes les remises conditionnelles pour une vente à l'échelle de la boutique gérée par d'autres moyens, vous le désactiveriez.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module Remises Conditionnelles sur les Commandes ajoute un nouvel élément de menu principal à votre Back Office PrestaShop, généralement sous **Catalogue** ou **Marketing**, nommé **"Remises Conditionnelles"**. Ce menu contient plusieurs sous-éléments pour gérer vos politiques et consulter les journaux.

#### 2.2.1 Remises Conditionnelles > Politiques (AdminConorderdisPoliciesController)

C'est ici que vous définissez et gérez toutes vos politiques de remise conditionnelle.

- **Nom de l'écran et emplacement du menu :** Back Office > Remises Conditionnelles > Politiques
- **Actions et paramètres disponibles :**

  - **Liste des politiques :** Vous verrez un tableau listant toutes vos politiques de remise existantes. Chaque politique affichera son nom, son statut (actif/inactif) et d'autres détails clés.
  - **Ajouter une nouvelle politique :** Cliquez sur le bouton "Ajouter une nouvelle politique" pour créer une toute nouvelle règle de remise conditionnelle.
  - **Modifier la politique :** Cliquez sur l'icône "Modifier" à côté d'une politique existante pour modifier ses conditions, promotions ou paramètres.
  - **Dupliquer la politique :** C'est une fonctionnalité très utile ! Cliquez sur l'icône "Dupliquer" pour créer une copie exacte d'une politique existante. Cela permet de gagner beaucoup de temps si vous devez créer des promotions similaires.
  - **Activer/Désactiver la politique :** Vous pouvez rapidement activer ou désactiver des politiques individuelles directement depuis la liste.
  - **Supprimer la politique :** Supprimez une politique de votre boutique.
  - **Formulaire de configuration de la politique (lors de l'ajout/modification) :**
    - **Nom de la politique :** Un nom descriptif pour votre référence interne (par exemple, "T-shirts BOGO", "Dépensez 100 € Obtenez 10 % de réduction").
    - **Statut (Actif/Inactif) :** Contrôle si cette politique spécifique est actuellement en ligne sur votre boutique.
    - **Constructeur de conditions :** C'est le cœur du module. Vous utiliserez une interface visuelle pour définir *quand* la remise s'applique. Exemples :
      - "Le total du panier est supérieur à 100 €"
      - "Le client fait partie du groupe 'Grossistes'"
      - "Le produit 'X' est dans le panier avec une quantité >= 2"
      - "Tout produit de la catégorie 'Soldes d'été' est dans le panier"
      - Vous pouvez combiner plusieurs conditions avec la logique "ET" ou "OU".
    - **Constructeur de promotions :** Cela définit *quelle* remise ou quel cadeau le client reçoit si les conditions sont remplies. Exemples :
      - "Appliquer 10 % de réduction sur toute la commande"
      - "Offrir l'article le moins cher de la catégorie 'Accessoires' gratuitement"
      - "Ajouter le produit 'Boîte cadeau' au panier gratuitement"
      - "Appliquer 50 % de réduction sur la deuxième unité du produit 'Y'"
    - **Sélecteur de portée :** Définissez à quelles boutiques (pour les configurations multi-boutiques), groupes de clients ou devises cette politique s'applique.
    - **Priorité :** Si plusieurs politiques peuvent s'appliquer à un seul panier, cela détermine laquelle prend le pas. Les nombres inférieurs signifient une priorité plus élevée.
    - **Dates de validité :** Définissez une date de début et de fin pour la promotion.
    - **Simulateur de panier :** Un outil puissant dans l'éditeur de politique qui vous permet d'ajouter des produits à un panier simulé et de voir instantanément si votre politique s'applique et quelle remise est accordée. C'est crucial pour les tests !
- **Effet des changements :**

  - L'ajout d'une nouvelle politique rend une nouvelle promotion disponible (si active) sur votre boutique.
  - La modification d'une politique change les conditions ou les promotions d'une offre existante.
  - L'activation/désactivation des politiques contrôle directement leur visibilité et leur application sur le front office.
  - La duplication des politiques permet la création rapide de promotions similaires sans repartir de zéro.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**

  1. **Planifiez votre promotion :** Décidez de l'offre (par exemple, "Achetez 3, obtenez 1 gratuit sur toutes les chaussettes").
  2. **Créez une nouvelle politique :** Allez dans "Politiques" et cliquez sur "Ajouter une nouvelle politique".
  3. **Définissez les conditions :** Utilisez le constructeur visuel pour spécifier quels produits, catégories, quantités ou valeurs de panier déclenchent la remise.
  4. **Définissez les promotions :** Spécifiez le type de remise (pourcentage, montant fixe, cadeau gratuit) et ce à quoi elle s'applique.
  5. **Testez minutieusement avec le Simulateur de panier :** Avant de sauvegarder, utilisez le simulateur pour ajouter divers produits et quantités afin de vous assurer que la remise s'applique exactement comme prévu.
  6. **Définissez les dates de validité et la priorité :** Assurez-vous que la promotion ne s'exécute que lorsque vous le souhaitez et interagit correctement avec les autres promotions.
  7. **Activez la politique :** Une fois testée et prête, définissez son statut sur "Actif".
  8. **Surveillez avec le Journal d'audit :** Vérifiez le Journal d'audit (voir section suivante) pour confirmer que les politiques sont appliquées correctement dans les paniers en direct.

#### 2.2.2 Remises Conditionnelles > Journal d'audit (AdminConorderdisAuditLogController)

Cet écran fournit un historique détaillé de la manière dont vos politiques de remise conditionnelle ont été appliquées (ou ont tenté d'être appliquées) aux paniers des clients.

- **Nom de l'écran et emplacement du menu :** Back Office > Remises Conditionnelles > Journal d'audit
- **Actions et paramètres disponibles :**
  - **Liste des journaux :** Un tableau affichant les entrées pour chaque fois qu'une politique a été évaluée. Chaque entrée comprend généralement :
    - **Date/Heure :** Quand l'événement s'est produit.
    - **Client :** Quel client (si connecté) était impliqué.
    - **ID du panier :** L'ID du panier d'achat.
    - **Nom de la politique :** Quelle politique a été évaluée.
    - **Résultat :** Si les conditions de la politique ont été remplies et si une remise a été appliquée.
    - **Détails :** Des informations plus spécifiques sur les conditions remplies, la remise appliquée ou la raison pour laquelle elle n'a pas été appliquée.
  - **Filtrage et recherche :** Vous pouvez filtrer le journal par date, client, politique ou résultat pour trouver rapidement des événements spécifiques.
- **Effet des changements :** Il s'agit d'un écran en lecture seule. Vous n'apportez pas de modifications ici, mais vous observez plutôt le comportement du module.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  - **Dépannage :** Si un client signale un problème avec une remise qui ne s'applique pas, ou si vous soupçonnez qu'une politique ne fonctionne pas comme prévu, consultez le journal d'audit. Vous pouvez voir exactement ce qui s'est passé lorsque son panier a été évalué.
  - **Surveillance :** Examinez régulièrement le journal pour vous assurer que vos promotions sont déclenchées correctement et pour identifier tout comportement inattendu.
  - **Comprendre les interactions des politiques :** Si vous avez plusieurs politiques, le journal peut vous aider à comprendre quelles politiques sont prises en compte et laquelle s'applique finalement en fonction des priorités.

#### 2.2.3 Remises Conditionnelles > Tableau de bord (AdminConorderdisDashboardController)

Cet écran fournit un aperçu et potentiellement un accès rapide aux fonctionnalités clés du module.

- **Nom de l'écran et emplacement du menu :** Back Office > Remises Conditionnelles > Tableau de bord
- **Actions et paramètres disponibles :** Ce tableau de bord fournit généralement :
  - **Statistiques récapitulatives :** Des décomptes rapides des politiques actives, du total des politiques ou des entrées récentes du journal d'audit.
  - **Liens rapides :** Des raccourcis vers "Ajouter une nouvelle politique", "Afficher les politiques" ou "Afficher le journal d'audit".
  - **Accès au simulateur :** Un lien proéminent ou un outil intégré pour le simulateur de panier afin de tester rapidement les politiques.
  - **Statut du module :** Indication si le module est activé ou désactivé.
- **Effet des changements :** Il s'agit principalement d'un écran d'information et de navigation. Les modifications sont effectuées via les sections liées "Politiques" ou "Journal d'audit".
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Utilisez-le comme point de départ pour gérer vos promotions, obtenir un aperçu rapide de vos campagnes actives et accéder au simulateur pour les tests.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer les remises conditionnelles sur les commandes | OUI | Interrupteur principal pour activer/désactiver toutes les fonctionnalités du module. |
| Politiques (Ajouter/Modifier) | Nom de la politique | Nom descriptif | Libellé interne pour votre promotion. |
| Politiques (Ajouter/Modifier) | Statut | Actif | Contrôle si une politique spécifique est en ligne sur la boutique. |
| Politiques (Ajouter/Modifier) | Constructeur de conditions | Varie | Définit les critères d'éligibilité à la remise (par exemple, total du panier, produits dans le panier). |
| Politiques (Ajouter/Modifier) | Constructeur de promotions | Varie | Définit la remise ou le cadeau gratuit appliqué (par exemple, % de réduction, produit gratuit). |
| Politiques (Ajouter/Modifier) | Sélecteur de portée | Toutes les boutiques/groupes/devises | Limite l'application de la politique à des contextes spécifiques. |
| Politiques (Ajouter/Modifier) | Priorité | Nombre inférieur = priorité plus élevée | Détermine quelle politique s'applique si plusieurs sont éligibles. |
| Politiques (Ajouter/Modifier) | Dates de validité | Pas de date de fin | Définit la période d'activité de la promotion. |
| Politiques (Ajouter/Modifier) | Simulateur de panier | N/A | Outil pour tester l'application de la politique avant de sauvegarder. |
| Politiques (Liste) | Action Dupliquer la politique | N/A | Crée une copie d'une politique existante, ce qui permet de gagner du temps de configuration. |
| Journal d'audit | Entrées du journal | N/A | Enregistre chaque évaluation de politique, montrant le succès/l'échec et les détails. |
| Tableau de bord | Liens rapides / Résumé | N/A | Fournit un aperçu et des raccourcis vers les fonctionnalités clés du module. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Ma remise ne s'applique pas, même si j'ai configuré une politique.**
R1 :

- **Le module est-il activé ?** Vérifiez **Modules > Gestionnaire de modules > Remises Conditionnelles sur les Commandes** et assurez-vous que l'interrupteur principal est sur ON.
- **La politique spécifique est-elle active ?** Allez dans **Remises Conditionnelles > Politiques** et vérifiez la colonne "Statut" de votre politique.
- **Les conditions sont-elles remplies ?** Utilisez le **Simulateur de panier** dans l'éditeur de politique. Ajoutez des produits au panier simulé exactement comme un client le ferait. Le simulateur indique-t-il que la remise s'applique ? Si non, examinez attentivement vos conditions.
- **Vérifiez les dates de validité :** La politique est-elle dans sa plage de dates active ?
- **Vérifiez la priorité :** Si plusieurs politiques peuvent s'appliquer, assurez-vous que celle que vous attendez a la bonne priorité (nombre inférieur = priorité plus élevée).
- **Videz le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache". Parfois, les données mises en cache peuvent empêcher les nouvelles règles de prendre effet immédiatement.

**Q2 : La remise s'applique, mais ce n'est pas le bon montant ou le bon produit.**
R2 :

- **Examinez votre Constructeur de promotions :** Vérifiez le type de remise (pourcentage, montant fixe), la valeur et ce à quoi elle s'applique (commande entière, produits spécifiques, article le moins cher, etc.).
- **Vérifiez à nouveau les conditions :** Parfois, une condition subtile peut entraîner un résultat inattendu. Par exemple, si vous avez "tout produit de la catégorie X" mais que le client a des produits d'autres catégories qui répondent également à une règle "article le moins cher".
- **Utilisez le Simulateur de panier de manière intensive :** C'est votre meilleur ami pour vérifier les règles complexes. Testez les cas limites.
- **Journal d'audit :** Vérifiez **Remises Conditionnelles > Journal d'audit** pour voir les détails exacts de la façon dont le module a évalué le panier et quelle remise il a tenté d'appliquer. Cela peut révéler des divergences.

**Q3 : Mon thème personnalisé n'affiche pas clairement les messages de remise ou les cadeaux gratuits.**
R3 :

- Le module s'intègre aux règles de panier natives de PrestaShop, de sorte que la remise elle-même devrait apparaître dans le résumé du panier. Cependant, si vous souhaitez que des messages personnalisés comme "Vous avez droit à un cadeau gratuit !" ou "Achetez 2, obtenez 1 gratuit !" apparaissent dynamiquement sur les pages produits ou dans le panier, cela nécessite généralement des modifications de thème personnalisées.
- **Consultez un développeur :** Votre webmaster ou un développeur PrestaShop peut vous aider à intégrer des messages dynamiques dans les fichiers `product.tpl`, `cart.tpl` ou `checkout.tpl` de votre thème, potentiellement en utilisant les hooks du module (voir Guide du développeur).

**Q4 : Puis-je utiliser ce module avec d'autres modules de remise ou des règles de panier natives ?**
R4 :

- Oui, ce module fonctionne en créant et en gérant des règles de panier PrestaShop natives en arrière-plan. Cela signifie qu'il est généralement compatible avec d'autres modules qui reposent également sur le système de remise de base de PrestaShop.
- **La priorité est essentielle :** Soyez attentif aux paramètres de priorité de vos politiques de Remises Conditionnelles sur les Commandes et de toutes les autres règles de panier natives que vous avez créées manuellement. PrestaShop applique les remises en fonction de leur priorité. Testez minutieusement avec le Simulateur de panier et examinez le Journal d'audit si vous avez de nombreuses promotions qui se chevauchent.

**Q5 : Comment gérer les traductions multilingues pour les noms ou descriptions de politiques ?**
R5 :

- Les noms de politiques et tout texte personnalisé que vous saisissez pour les conditions ou les promotions sont généralement gérés directement dans l'écran d'édition de la politique. L'interface de traduction standard de PrestaShop (sous **International > Traductions**) peut ne pas s'appliquer directement au contenu dynamique généré par le constructeur de politiques du module.
- Si le module fournit des champs spécifiques pour différentes langues dans l'éditeur de politique, utilisez-les. Sinon, assurez-vous que les noms de vos politiques sont clairs et concis, ou envisagez d'ajouter des blocs d'informations statiques dans votre thème pour différentes langues afin d'expliquer les promotions.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une plongée approfondie dans l'architecture technique du module Remises Conditionnelles sur les Commandes, détaillant sa structure de fichiers, ses classes, ses contrôleurs et ses points d'intégration pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module Remises Conditionnelles sur les Commandes est construit selon le modèle MVC (Model-View-Controller) de PrestaShop. Il s'appuie fortement sur le système natif `CartRule` de PrestaShop, agissant efficacement comme un constructeur et un gestionnaire de règles avancé pour ces objets centraux. Il introduit plusieurs classes `ObjectModel` personnalisées pour gérer les politiques, les conditions, les promotions et un journal d'audit. Le module utilise un moteur robuste pour évaluer des conditions complexes par rapport à l'état du panier d'un client, puis matérialise les objets `CartRule` appropriés. Il comprend également un constructeur de conditions sophistiqué et un simulateur dans le Back Office pour faciliter l'utilisation.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `conorderdis/controllers/front/index.php`
  - **Nom de la classe :** `ConorderdisIndexModuleFrontController` (ou similaire, selon la version de PrestaShop et la structure du module, souvent `ModuleFrontController`).
  - **Responsabilité :** Ce fichier sert généralement de placeholder ou de point d'entrée par défaut pour les interactions du module en front-office. Dans le contexte de ce module, les contrôleurs front-office directs sont moins critiques car la plupart de la logique est gérée via des hooks qui interagissent avec le panier et le processus de commande. Il pourrait gérer les requêtes AJAX liées aux mises à jour du panier ou à des interactions front-end spécifiques si implémenté, mais la logique de remise principale s'exécute via des hooks.

#### Contrôleurs d'administration Back-Office

- `conorderdis/controllers/admin/AdminconorderdisAuditLog.php`
  - **Nom de l'onglet :** Remises Conditionnelles > Journal d'audit
  - **Entité gérée :** `ConorderdisAuditLog` (correspond à la table `ps_conorderdis_log`).
  - **Responsabilité :** Gère l'affichage et le filtrage des entrées du journal d'audit. Étend `AdminController` et utilise `HelperList` pour afficher le tableau du journal, permettant aux administrateurs de revoir comment les politiques ont été appliquées ou évaluées par rapport aux paniers des clients.
- `conorderdis/controllers/admin/AdminconorderdisPolicies.php`
  - **Nom de l'onglet :** Remises Conditionnelles > Politiques
  - **Entité gérée :** `ConorderdisPolicy` (correspond à la table `ps_conorderdis_policy`).
  - **Responsabilité :** C'est le contrôleur principal pour la gestion des politiques de remise. Il étend `AdminController` et fournit des fonctionnalités CRUD (Créer, Lire, Mettre à jour, Supprimer) pour les politiques. Il intègre les constructeurs visuels de conditions et de promotions, le sélecteur de produits et le simulateur de panier. Il utilise `HelperList` pour l'aperçu des politiques et `HelperForm` pour les formulaires d'ajout/modification de politiques.
- `conorderdis/controllers/admin/index.php`
  - **Responsabilité :** C'est une pratique standard de PrestaShop pour empêcher la liste des répertoires. Il contient généralement une simple instruction `die('No direct script access allowed');`. Il ne gère aucune entité spécifique et ne fournit aucune fonctionnalité au-delà de la sécurité.

### 4.3 Classes et modèles de base (`classes/`)

- `conorderdis/classes/ConorderdisAdmin.php`
  - **Responsabilité :** Contient probablement des méthodes d'aide ou des utilitaires spécifiquement pour l'administration du Back Office, tels que le rendu d'éléments de formulaire spécifiques, la gestion des requêtes AJAX des formulaires d'administration ou la gestion des configurations spécifiques au module.
- `conorderdis/classes/ConorderdisAuditLog.php`
  - **Étend :** `ObjectModel`
  - **Table de base de données :** `ps_conorderdis_log`
  - **Champs `$definition` :** Stocke les détails des évaluations de politique, y compris `id_cart`, `id_customer`, `id_policy`, `result`, `details`, `date_add`.
  - **Responsabilité :** Représente une entrée dans le journal d'audit. Fournit des méthodes pour enregistrer les événements d'application de politique, les succès et les échecs.
- `conorderdis/classes/ConorderdisCartRuleManager.php`
  - **Responsabilité :** Gère la création, la mise à jour et la suppression des objets `CartRule` natifs de PrestaShop basés sur les définitions `ConorderdisPolicy` du module. Cette classe est cruciale pour traduire les règles complexes du module en remises PrestaShop standard.
- `conorderdis/classes/ConorderdisCartState.php`
  - **Responsabilité :** Encapsule l'état actuel du panier d'un client, fournissant une couche d'abstraction pour que le moteur de remise évalue les conditions. Il peut inclure des méthodes pour récupérer le total du panier, les quantités de produits, le groupe de clients, etc.
- `conorderdis/classes/ConorderdisCompatibility.php`
  - **Responsabilité :** Gère les couches de compatibilité pour différentes versions de PrestaShop (par exemple, 1.7.x, 8.x, 9.x) ou des versions spécifiques de PHP. Il garantit que le module fonctionne correctement sur la plage d'environnements pris en charge en fournissant des polyfills ou des implémentations alternatives pour les fonctions/méthodes dépréciées.
- `conorderdis/classes/ConorderdisConditionTree.php`
  - **Responsabilité :** Gère la structure logique complexe des conditions (par exemple, groupes "ET", "OU", conditions imbriquées). Il analyse probablement les données de condition de la base de données et fournit des méthodes pour évaluer si un `ConorderdisCartState` donné répond aux conditions définies.
- `conorderdis/classes/ConorderdisContext.php`
  - **Responsabilité :** Un wrapper autour de l'objet `Context` global de PrestaShop, ajoutant potentiellement des données de contexte spécifiques au module ou simplifiant l'accès aux propriétés de contexte courantes.
- `conorderdis/classes/ConorderdisDashboard.php`
  - **Responsabilité :** Fournit des données et une logique pour la vue du tableau de bord du Back Office, résumant les statistiques clés et fournissant des liens rapides.
- `conorderdis/classes/ConorderdisEngine.php`
  - **Responsabilité :** Le moteur logique principal du module. Cette classe orchestre l'évaluation des politiques. Elle prend un `ConorderdisCartState`, itère sur les objets `ConorderdisPolicy` actifs, évalue leur `ConorderdisConditionTree`, et si les conditions sont remplies, demande à `ConorderdisPromoMaterializer` d'appliquer la remise.
- `conorderdis/classes/ConorderdisFreeGift.php`
  - **Responsabilité :** Gère spécifiquement la logique d'ajout de produits cadeaux gratuits au panier lorsqu'une promotion le dicte. Il interagit avec l'objet `Cart` pour s'assurer que le produit est ajouté correctement et marqué comme gratuit.
- `conorderdis/classes/ConorderdisListRenderer.php`
  - **Responsabilité :** Une classe d'aide pour le rendu des listes dans le Back Office, étendant potentiellement `HelperList` ou fournissant une logique de rendu personnalisée pour des colonnes ou des actions spécifiques (par exemple, l'action de duplication).
- `conorderdis/classes/ConorderdisLog.php`
  - **Étend :** `ObjectModel` (probablement un alias ou une ancienne version de `ConorderdisAuditLog`).
  - **Table de base de données :** `ps_conorderdis_log`
  - **Responsabilité :** Similaire à `ConorderdisAuditLog`, gère la journalisation des événements du module.
- `conorderdis/classes/ConorderdisPolicy.php`
  - **Étend :** `ObjectModel`
  - **Table de base de données :** `ps_conorderdis_policy`
  - **Champs `$definition` :** Stocke toutes les données liées à la politique, y compris `name`, `active`, `conditions_data` (tableau JSON sérialisé), `promotions_data` (tableau JSON sérialisé), `priority`, `date_from`, `date_to`, `id_shop`, `id_customer_group`, `id_currency`.
  - **Responsabilité :** Représente une seule politique de remise conditionnelle. Fournit des méthodes pour sauvegarder, charger et gérer les données de politique, y compris ses conditions et promotions.
- `conorderdis/classes/ConorderdisPolicyDuplicator.php`
  - **Responsabilité :** Gère la logique de duplication des objets `ConorderdisPolicy`, garantissant que toutes les données associées (conditions, promotions) sont correctement copiées.
- `conorderdis/classes/ConorderdisProductPicker.php`
  - **Responsabilité :** Fournit des fonctionnalités pour sélectionner des produits, des catégories ou des fabricants dans le constructeur de politiques du Back Office, probablement via un outil de recherche basé sur AJAX.
- `conorderdis/classes/ConorderdisPromoMaterializer.php`
  - **Responsabilité :** Prend la sortie du `ConorderdisEngine` (c'est-à-dire "cette promotion doit s'appliquer") et la traduit en modifications réelles dans le panier PrestaShop, principalement en créant ou en modifiant des objets `CartRule` via `ConorderdisCartRuleManager`.
- `conorderdis/classes/ConorderdisPromotionCalculator.php`
  - **Responsabilité :** Calcule le montant exact de la remise ou identifie le produit gratuit en fonction des règles de promotion définies et de l'état actuel du panier.
- `conorderdis/classes/ConorderdisPromotionType.php`
  - **Responsabilité :** Définit et gère différents types de promotions (par exemple, remise en pourcentage, montant fixe, cadeau gratuit, article le moins cher gratuit). Il contient probablement une logique spécifique à chaque type de promotion.
- `conorderdis/classes/ConorderdisRule.php`
  - **Responsabilité :** Une classe générique représentant une seule règle ou condition dans le `ConorderdisConditionTree`.
- `conorderdis/classes/ConorderdisSchema.php`
  - **Responsabilité :** Gère le schéma de base de données du module, y compris l'installation et la désinstallation des tables personnalisées (`ps_conorderdis_policy`, `ps_conorderdis_log`).
- `conorderdis/classes/ConorderdisUnitPool.php`
  - **Responsabilité :** Probablement utilisé dans des scénarios complexes "Achetez N, obtenez M" ou "article le moins cher gratuit" pour gérer et suivre les unités de produit individuelles dans le panier pour le calcul de la remise.
- `conorderdis/classes/index.php`
  - **Responsabilité :** Pratique standard de PrestaShop pour empêcher la liste des répertoires.

### 4.4 Actifs JavaScript (`views/js/`)

- `conorderdis/lib/searchTool/views/js/autocomplete.js`
  - **Portée :** Back-office (utilisé dans les formulaires d'administration).
  - **Détails :** Fournit une fonctionnalité d'autocomplétion pour les champs de saisie, probablement utilisée dans le constructeur de politiques pour sélectionner des produits, des catégories ou des fabricants. Se lie aux champs de saisie, effectue des appels AJAX à un contrôleur de recherche et affiche des suggestions.
- `conorderdis/views/js/adminConditionBuilder.js`
  - **Portée :** Back-office (contrôleur AdminConorderdisPolicies).
  - **Détails :** Alimente l'interface visuelle du constructeur de conditions. Gère l'ajout/la suppression de conditions, le regroupement de conditions (ET/OU), la sélection des types de conditions et la mise à jour dynamique de l'interface utilisateur en fonction de l'entrée de l'utilisateur. Gère la structure de données représentant l'arbre de conditions.
- `conorderdis/views/js/adminConorderdisDashboard.js`
  - **Portée :** Back-office (contrôleur AdminConorderdisDashboard).
  - **Détails :** Fournit des éléments interactifs ou du contenu dynamique pour le tableau de bord du module, tels que la récupération de statistiques récapitulatives via AJAX ou la gestion des clics sur les liens rapides.
- `conorderdis/views/js/adminConorderdisSearchTool.js`
  - **Portée :** Back-office (contrôleur AdminConorderdisPolicies).
  - **Détails :** Un outil de recherche plus général, potentiellement utilisé pour la sélection de produits/catégories dans le constructeur de politiques, similaire à `autocomplete.js` mais éventuellement avec des options de filtrage ou d'affichage plus avancées.
- `conorderdis/views/js/adminConorderdisSimulator.js`
  - **Portée :** Back-office (contrôleur AdminConorderdisPolicies).
  - **Détails :** Implémente le simulateur de panier interactif. Se lie aux champs de saisie pour ajouter des produits simulés, effectue des appels AJAX à un point de terminaison de simulation (probablement dans `AdminConorderdisPolicies`) et met à jour l'interface utilisateur avec l'état du panier simulé et les remises appliquées.
- `conorderdis/views/js/adminPolicyRules.js`
  - **Portée :** Back-office (contrôleur AdminConorderdisPolicies).
  - **Détails :** Gère l'interaction et la logique globales du formulaire de création/modification de politique, coordonnant entre le constructeur de conditions, le constructeur de promotions et le simulateur.
- `conorderdis/views/js/adminPromotionBuilder.js`
  - **Portée :** Back-office (contrôleur AdminConorderdisPolicies).
  - **Détails :** Alimente l'interface visuelle du constructeur de promotions. Gère l'ajout/la suppression de promotions, la sélection des types de promotions (par exemple, pourcentage, cadeau gratuit) et la mise à jour dynamique de l'interface utilisateur en fonction du type de promotion choisi.

### 4.5 Feuilles de style CSS (`views/css/`)

- `conorderdis/lib/searchTool/views/css/autocomplete.css`
  - **Portée :** Back-office (formulaires d'administration).
  - **Détails :** Style les listes déroulantes d'autocomplétion et les résultats de recherche fournis par le script `autocomplete.js`.
- `conorderdis/views/css/admin_conorderdis.css`
  - **Portée :** Back-office (formulaires et pages d'administration).
  - **Détails :** Contient le style général des interfaces Back Office du module, y compris la liste des politiques, l'éditeur de politiques (constructeurs de conditions et de promotions), le tableau de bord et le journal d'audit. Définit les mises en page, les couleurs et les composants d'interface utilisateur spécifiques pour une apparence cohérente dans l'administration de PrestaShop.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

- `conorderdis/views/templates/hook/admin_order.tpl`
  - **Hook :** `displayAdminOrder`
  - **Sortie :** Ce template est rendu dans le Back Office lors de la visualisation d'une commande. Il affiche probablement des informations relatives aux remises conditionnelles appliquées à cette commande spécifique, potentiellement en lien avec le journal d'audit ou en montrant quelles politiques étaient actives.

#### Templates d'administration (`views/templates/admin/`)

- `conorderdis/lib/searchTool/views/scripts.tpl`
  - **Sortie :** Contient l'initialisation ou la configuration JavaScript pour l'outil de recherche, souvent inclus dans les formulaires d'administration où l'outil de recherche est utilisé.
- `conorderdis/views/templates/admin/auditPreview.tpl`
  - **Sortie :** Rend un aperçu ou une vue détaillée d'une entrée du journal d'audit, éventuellement dans une modale ou une section spécifique de la page `AdminconorderdisAuditLog`.
- `conorderdis/views/templates/admin/dashboard.tpl`
  - **Sortie :** Le template principal du contrôleur `AdminConorderdisDashboard`, affichant les statistiques récapitulatives, les liens rapides et potentiellement le simulateur intégré.
- `conorderdis/views/templates/admin/helpers/list/list_action_duplicate.tpl`
  - **Sortie :** Un template personnalisé pour le rendu de l'icône et du lien d'action "Dupliquer" dans un tableau `HelperList`, spécifiquement pour les politiques.
- `conorderdis/views/templates/admin/policiesPreview.tpl`
  - **Sortie :** Rend un aperçu ou une vue détaillée d'une politique, éventuellement dans une modale ou une section spécifique de la page `AdminconorderdisPolicies`.
- `conorderdis/views/templates/admin/policyConditionBuilder.tpl`
  - **Sortie :** Le template Smarty pour l'interface visuelle du constructeur de conditions dans l'éditeur de politique. Il définit la structure pour l'ajout, le regroupement et la configuration des conditions.
- `conorderdis/views/templates/admin/policyRuleCard.tpl`
  - **Sortie :** Un template réutilisable pour afficher une seule règle ou condition dans le constructeur de conditions, souvent utilisé pour le rendu dynamique via JavaScript.
- `conorderdis/views/templates/admin/policyRulesTable.tpl`
  - **Sortie :** Rend le tableau ou la liste des règles/conditions dans l'éditeur de politique.
- `conorderdis/views/templates/admin/scopeSelector.tpl`
  - **Sortie :** Rend l'interface pour la sélection des boutiques, des groupes de clients et des devises pour une politique.

#### Templates Front-office (`views/templates/front/`)

- `conorderdis/controllers/front/index.php` (Aucun fichier `.tpl` spécifique n'est listé pour le front-office, ce qui implique un rendu front-end direct minimal, s'appuyant sur des hooks pour injecter du contenu ou modifier des éléments existants.)

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

- `ps_conorderdis_policy` : Stocke la définition de chaque politique de remise conditionnelle.
  - `id_conorderdis_policy` (Clé primaire)
  - `name` (Nom de la politique)
  - `active` (Booléen, 1 pour actif, 0 pour inactif)
  - `conditions_data` (TEXT, tableau de conditions encodé en JSON)
  - `promotions_data` (TEXT, tableau de promotions encodé en JSON)
  - `priority` (INT, nombre inférieur = priorité plus élevée)
  - `date_from` (DATETIME)
  - `date_to` (DATETIME)
  - `id_shop` (INT, pour la portée multi-boutiques)
  - `id_customer_group` (INT, pour la portée du groupe de clients)
  - `id_currency` (INT, pour la portée de la devise)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_conorderdis_log` : Stocke les entrées du journal d'audit pour les évaluations de politique.
  - `id_conorderdis_log` (Clé primaire)
  - `id_cart` (INT)
  - `id_customer` (INT)
  - `id_policy` (INT, clé étrangère vers `ps_conorderdis_policy`)
  - `result` (VARCHAR, par exemple, 'applied', 'not\_met', 'error')
  - `details` (TEXT, détails de l'évaluation encodés en JSON)
  - `date_add` (DATETIME)
- `ps_configuration` : Le module y stocke son paramètre principal `CONORDERDIS_ENABLED`.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page front-office. | Utilisé pour inclure les CSS/JS front-office du module, le cas échéant, ou pour injecter des balises meta. |
| `actionFrontControllerInitAfter` | Après l'initialisation du contrôleur front-office. | Point précoce pour modifier le contexte, enregistrer des services ou se préparer à l'évaluation des règles de panier. |
| `actionCartSave` | Après la sauvegarde d'un panier (par exemple, produit ajouté/supprimé). | Hook principal pour réévaluer les politiques de remise conditionnelle en fonction du contenu mis à jour du panier. |
| `actionValidateCartRule` | Avant la validation/application d'une règle de panier. | Permet au module d'intervenir ou de modifier le comportement natif des règles de panier, bien que moins probable pour ce module qui crée les siennes. |
| `actionValidateOrderBefore` | Avant la validation d'une commande. | Vérification finale des remises conditionnelles avant la création de la commande, garantissant que toutes les règles sont correctement appliquées. |
| `actionValidateOrder` | Après la validation réussie d'une commande. | Utilisé pour finaliser toute action spécifique au module après la commande, telle que l'enregistrement de l'application finale de la remise ou la suppression des données temporaires. |
| `actionObjectProductInCartDeleteBefore` | Avant la suppression d'un produit du panier. | Permet au module de réagir à la suppression d'un produit, potentiellement en ajustant les remises ou les cadeaux gratuits. |
| `actionObjectProductInCartDeleteAfter` | Après la suppression d'un produit du panier. | Similaire à `DeleteBefore`, mais pour la logique post-suppression, déclenchant potentiellement une réévaluation des règles de panier. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration définit ses médias (CSS/JS). | Utilisé pour inclure les fichiers CSS et JavaScript du Back Office du module pour ses pages de configuration et ses contrôleurs personnalisés. |
| `displayAdminOrder` | Sur la page de détail de la commande du Back Office. | Utilisé pour afficher les informations spécifiques au module relatives aux remises conditionnelles appliquées à la commande consultée (par exemple, via `admin_order.tpl`). |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Vous y trouverez vos modules achetés et l'accès à nos canaux de support.
