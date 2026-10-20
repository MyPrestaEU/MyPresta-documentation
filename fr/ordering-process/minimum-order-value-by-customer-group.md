---
title: "Valeur minimale de commande par groupe de clients - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Valeur minimale de commande par groupe de clients' par MyPresta.eu."
sidebar:
  label: "Valeur minimale de commande par groupe de clients - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Minimum order value by customer group sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimum-order-value-by-customer-group.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/minimum-order-value-by-customer-group/)
>
> ---


# Valeur minimale de commande par groupe de clients

## 1. Exigences et Compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal où vous définissez les valeurs minimales de commande pour chaque groupe de clients.

#### Paramètres généraux

-   **Exclure des groupes de clients spécifiques de la règle de valeur minimale de commande :**
    *   **Ce que fait ce paramètre :** Cela vous permet de sélectionner les groupes de clients qui ne seront *pas* soumis à une valeur minimale de commande, même si vous en avez défini une pour eux ci-dessous. Ils peuvent toujours passer commande quel que soit le total de leur panier.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsque activé (groupes sélectionnés) :* Les clients appartenant aux groupes sélectionnés contourneront toutes les vérifications de valeur minimale de commande.
        *   *Lorsque désactivé (aucun groupe sélectionné) :* Tous les groupes de clients seront soumis aux valeurs minimales de commande que vous définissez.
    *   **Valeur recommandée :** Dépend de votre modèle commercial. Si vous avez des VIP ou des clients B2C spécifiques que vous souhaitez exempter, sélectionnez-les ici. Sinon, laissez vide.
    *   **Scénario / exemple marchand :** Vous avez un groupe "Clients VIP" que vous souhaitez toujours pouvoir passer commande, même si leur commande est petite. Sélectionnez "Clients VIP" ici.
-   **Inclure la taxe dans la valeur minimale de commande :**
    *   **Ce que fait ce paramètre :** Détermine si la valeur minimale de commande que vous définissez doit inclure ou exclure le montant de la taxe calculé pour les produits dans le panier.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsque activé (OUI) :* Le module vérifiera le total du panier *incluant* les taxes par rapport à votre minimum défini.
        *   *Lorsque désactivé (NON) :* Le module vérifiera le total du panier *excluant* les taxes par rapport à votre minimum défini.
    *   **Valeur recommandée :** "OUI" pour la plupart des boutiques B2C, car les clients voient et paient généralement le prix total incluant la taxe. "NON" pourrait être préféré pour les boutiques B2B où les prix sont souvent indiqués hors taxes.
    *   **Scénario / exemple marchand :** Si vous définissez un minimum de 100 $ et que cela est activé, un total de panier de 90 $ (hors taxes) + 10 $ (taxes) = 100 $ serait accepté. Si désactivé, le même panier échouerait car 90 $ est inférieur à 100 $.
-   **Inclure les frais de port dans la valeur minimale de commande :**
    *   **Ce que fait ce paramètre :** Détermine si les frais de port de la commande doivent être ajoutés au total du panier avant de vérifier par rapport à la valeur minimale de commande.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsque activé (OUI) :* Le module vérifiera (Total du panier + Frais de port) par rapport à votre minimum défini.
        *   *Lorsque désactivé (NON) :* Le module vérifiera uniquement le Total du panier (produits) par rapport à votre minimum défini.
    *   **Valeur recommandée :** "NON" dans la plupart des cas, car les minimums concernent généralement la valeur des produits. Cependant, si vos frais de port sont très élevés et que vous souhaitez assurer une certaine valeur totale de transaction, vous pourriez activer cela.
    *   **Scénario / exemple marchand :** Vous voulez que les clients achètent au moins 50 $ de produits. Si c'est "NON", un panier de produits de 50 $ passe. Si c'est "OUI" et que les frais de port sont de 10 $, le client aurait besoin de 50 $ de produits + 10 $ de frais de port = 60 $ au total pour passer, ce qui signifie qu'il aurait besoin de 60 $ de produits pour atteindre le minimum de 50 $. Ce paramètre est généralement "NON" pour éviter toute confusion.
-   **Appliquer la valeur minimale de commande uniquement pour la première commande :**
    *   **Ce que fait ce paramètre :** Si activé, les règles de valeur minimale de commande ne s'appliqueront qu'à la toute première commande d'un client dans votre boutique. Les commandes ultérieures ne seront pas soumises aux minimums.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsque activé (OUI) :* Seuls les nouveaux clients (ceux qui n'ont pas passé de commande auparavant) seront soumis aux restrictions de valeur minimale de commande.
        *   *Lorsque désactivé (NON) :* Toutes les commandes, qu'il s'agisse de la première ou de la dixième commande d'un client, seront vérifiées par rapport à la valeur minimale de commande.
    *   **Valeur recommandée :** "NON" pour la plupart des scénarios où vous souhaitez des minimums cohérents. "OUI" pourrait être utile pour encourager des achats initiaux plus importants de la part de nouveaux clients, puis assouplir les règles pour les affaires récurrentes.
    *   **Scénario / exemple marchand :** Vous souhaitez que les nouveaux clients B2B passent une première commande substantielle de 500 $ pour établir leur compte, mais après cela, ils peuvent commander n'importe quel montant. Activez ceci et définissez le minimum de 500 $ pour votre groupe B2B.

#### Valeurs minimales de commande par groupe de clients

Sous les paramètres généraux, vous trouverez une liste de tous vos groupes de clients. Pour chaque groupe, vous pouvez définir une valeur minimale de commande.

-   **Nom du groupe de clients (par exemple, "Visiteur", "Invité", "Client", "Grossiste") :**
    *   **Ce que fait ce paramètre :** C'est ici que vous saisissez le montant minimum de commande spécifique requis pour les clients appartenant à ce groupe particulier.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'une valeur est saisie (par exemple, 50.00) :* Les clients de ce groupe doivent avoir un total de panier égal ou supérieur à cette valeur pour passer à la caisse.
        *   *Lorsqu'il est laissé vide ou défini à 0.00 :* Il n'y a pas de valeur minimale de commande pour ce groupe de clients. Ils peuvent passer commande avec n'importe quel total de panier.
    *   **Valeur recommandée :** Définissez une valeur qui a du sens commercial pour chaque groupe. Laissez vide pour des groupes comme "Visiteur" ou "Invité" à moins que vous ne vouliez spécifiquement les empêcher de commander.
    *   **Scénario / exemple marchand :**
        *   Pour le groupe "Client" : Définissez à `25.00` pour encourager des achats au détail légèrement plus importants.
        *   Pour le groupe "Grossiste" : Définissez à `200.00` pour assurer la rentabilité des commandes B2B.
        *   Pour le groupe "Invité" : Laissez vide (`0.00`) pour permettre des achats rapides sans inscription.

#### Considérations multi-boutiques et multi-devises

-   **Multi-boutique :** Si vous avez plusieurs boutiques activées, vous verrez une liste déroulante en haut de la page de configuration (généralement à côté du bouton "Enregistrer") vous permettant de sélectionner la boutique que vous configurez. Les valeurs minimales de commande peuvent être définies indépendamment pour chaque boutique.
-   **Multi-devises :** Les valeurs minimales de commande que vous saisissez sont toujours dans la *devise par défaut* de votre boutique PrestaShop. Le module convertit automatiquement ces valeurs dans la devise sélectionnée par le client au taux de change actuel lors de la vérification du total du panier.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Exclure des groupes de clients spécifiques | Vide | Sélectionnez les groupes pour contourner les règles de commande minimale. |
| Configuration du module | Inclure la taxe dans la valeur minimale de commande | OUI | Détermine si la taxe fait partie du total minimum. |
| Configuration du module | Inclure les frais de port dans la valeur minimale de commande | NON | Détermine si les frais de port font partie du total minimum. |
| Configuration du module | Appliquer la valeur minimale de commande uniquement pour la première commande | NON | Applique les minimums uniquement à l'achat initial d'un client. |
| Configuration du module | Valeur minimale de commande pour [Nom du groupe de clients] | 0.00 (vide) | Définissez le total de panier requis pour chaque groupe de clients. |

## 3. Dépannage marchand et Foire Aux Questions (FAQ)

**Q : Mes clients voient le message de commande minimale même si le total de leur panier semble correct. Qu'est-ce qui ne va pas ?**
R :

1.  **Vérifiez les paramètres de taxe/livraison :** Vérifiez si "Inclure la taxe dans la valeur minimale de commande" ou "Inclure les frais de port dans la valeur minimale de commande" sont activés. Le total du panier affiché pourrait être différent de la valeur par rapport à laquelle le module effectue la vérification.
2.  **Conversion de devise :** Si vous opérez dans plusieurs devises, assurez-vous que les taux de change sont à jour. Le module convertit vos minimums en devise par défaut dans la devise sélectionnée par le client.
3.  **Affectation du groupe de clients :** Vérifiez que le client est correctement affecté au groupe de clients que vous souhaitez, et que la valeur minimale pour ce groupe est définie comme prévu.
4.  **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions plus anciennes). Parfois, d'anciennes données mises en cache peuvent causer des problèmes.

**Q : J'ai défini un minimum, mais un groupe de clients spécifique peut toujours passer commande avec n'importe quel montant. Pourquoi ?**
R : Vérifiez le paramètre "Exclure des groupes de clients spécifiques de la règle de valeur minimale de commande" sur la page de configuration du module. Si ce groupe de clients y est sélectionné, il contournera toutes les vérifications de commande minimale. Supprimez-le de cette liste d'exclusion si vous souhaitez que le minimum s'applique.

**Q : Le message du module n'apparaît pas, ou il semble étrange sur mon thème personnalisé.**
R :

1.  **Compatibilité du thème :** Les thèmes personnalisés peuvent remplacer les modèles ou le CSS standard de PrestaShop, ce qui peut affecter la façon dont les messages du module sont affichés.
2.  **Conflits CSS :** Un autre module ou le CSS de votre thème pourrait être en conflit avec le style du module.
3.  **Cache Smarty :** Videz votre cache Smarty (Paramètres avancés > Performances > Vider le cache) pour vous assurer que les derniers fichiers de modèle sont utilisés.
    Pour les problèmes visuels, vous devrez peut-être consulter un développeur web pour inspecter le CSS et les fichiers de modèle de votre thème.

**Q : Puis-je définir des minimums différents pour différents produits ?**
R : Non, ce module définit un minimum pour la *valeur totale du panier* en fonction du groupe de clients, et non pour des produits individuels. Si vous avez besoin de minimums spécifiques aux produits, vous auriez besoin d'un autre type de module.

**Q : Comment ce module gère-t-il les configurations multi-boutiques ?**
R : Le module est compatible multi-boutiques. Lors de la configuration, utilisez le sélecteur de "Contexte de boutique" en haut du back office de PrestaShop (généralement à côté du bouton "Enregistrer") pour basculer entre vos boutiques. Vous pouvez ensuite définir des valeurs minimales de commande uniques pour chaque groupe de clients, par boutique.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module "Valeur minimale de commande par groupe de clients" (`cgma`) est construit selon l'architecture de module standard de PrestaShop. Il utilise principalement des hooks pour injecter sa logique dans le processus de panier et de commande du front-office. La configuration est gérée via la méthode `getContent()` de la classe principale du module, stockant les paramètres dans `ps_configuration`. L'interaction front-office est gérée par un contrôleur AJAX dédié pour la validation du panier en temps réel.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :
    *   `cgma/controllers/front/ajax.php`
        *   **Nom de la classe :** `CgmaAjaxModuleFrontController` (étend `ModuleFrontController`)
        *   **Responsabilité :** Ce contrôleur gère les requêtes AJAX depuis le front-office, principalement pour la validation en temps réel du total du panier par rapport à la valeur minimale de commande du groupe de clients. Il renvoie probablement une réponse JSON indiquant si le panier répond aux exigences et potentiellement un message à afficher à l'utilisateur. Ceci est crucial pour les mises à jour dynamiques sans rechargement complet de la page.
    *   `cgma/controllers/front/index.php`
        *   **Nom de la classe :** `CgmaIndexModuleFrontController` (étend `ModuleFrontController`)
        *   **Responsabilité :** Il s'agit d'un contrôleur de remplacement ou de secours. Dans de nombreux modules, si une action spécifique n'est pas définie, les requêtes peuvent être redirigées vers un contrôleur `index`. Il peut également être utilisé pour de simples redirections ou pour s'assurer qu'une route de module valide existe, bien que sa fonction principale dans ce module soit probablement minimale par rapport à `ajax.php`.
-   **Contrôleurs d'administration Back-Office** :
    *   Aucun n'est explicitement défini dans l'inventaire. Toute la configuration du back-office est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

-   Aucune classe personnalisée ou définition d'`ObjectModel` n'est explicitement listée dans l'inventaire. Le module s'appuie probablement sur les classes `Customer`, `Group`, `Cart` et `Configuration` de PrestaShop pour sa fonctionnalité. Les valeurs de configuration sont stockées directement dans la table `ps_configuration`.

### 4.4 Assets JavaScript (`views/js/`)

-   `cgma/views/js/cgma.js`
    *   **Portée :** Front-office.
    *   **Détails :** Ce script est responsable de l'interaction et de la validation côté client. Il écoute probablement les changements dans le panier (par exemple, mises à jour de quantité, suppressions de produits) ou les tentatives de passer à la caisse. Il déclencherait ensuite des appels AJAX à `cgma/controllers/front/ajax.php` pour valider le total du panier par rapport à la valeur minimale de commande. Après avoir reçu une réponse, il mettrait à jour dynamiquement le résumé du panier ou les boutons de paiement, affichant des messages à l'utilisateur si le minimum n'est pas atteint et désactivant potentiellement le bouton "Passer à la caisse". Il pourrait également gérer l'affichage du message de valeur minimale de commande à divers endroits du front-office.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `cgma/css.css`
    *   **Portée :** Probablement front-office.
    *   **Détails :** Cette feuille de style fournit le style de base pour les messages ou éléments du front-office du module, tels que le message d'avertissement affiché lorsque la valeur minimale de commande n'est pas atteinte.
    *   **Sélecteurs de classe CSS clés :** Les développeurs doivent inspecter ce fichier pour des classes comme `.cgma-warning-message`, `.cgma-disabled-button`, ou similaires, qui peuvent être remplacées dans un thème personnalisé.
-   `cgma/views/css/cgma.css`
    *   **Portée :** Probablement front-office.
    *   **Détails :** Similaire à `cgma/css.css`, ce fichier fournit un style supplémentaire ou plus spécifique pour les composants du front-office du module. Il peut contenir des ajustements responsives ou des règles de mise en page spécifiques.
    *   **Sélecteurs de classe CSS clés :** Vérifiez les sélecteurs liés au résumé du panier, aux boutons de paiement ou aux conteneurs de messages spécifiques.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** :
    *   Aucun n'est explicitement listé dans l'inventaire, mais l'implémentation du hook `displayShoppingCart` du module rendrait probablement un modèle. Il est possible que `displayShoppingCart.tpl` soit directement dans `views/templates/front/` et utilisé par le hook.
-   **Modèles d'administration (`views/templates/admin/`)** :
    *   `cgma/admin.tpl`
        *   **Portée :** Configuration du Back-office.
        *   **Détails :** Ce modèle est rendu par la méthode `getContent()` de la classe principale du module (`cgma.php`). Il contient la structure HTML du formulaire de configuration du module, y compris les champs de saisie pour les paramètres généraux (groupes à exclure, inclusion de taxe/frais de port, première commande uniquement) et les champs dynamiques pour définir les valeurs minimales de commande pour chaque groupe de clients.
-   **Modèles Front-office (`views/templates/front/`)** :
    *   `cgma/views/templates/front/displayShoppingCart.tpl`
        *   **Portée :** Front-office, spécifiquement la page du panier.
        *   **Détails :** Ce modèle est probablement rendu lorsque le module s'accroche à `displayShoppingCart`. Il affiche le message d'avertissement au client si le total de son panier n'atteint pas la valeur minimale de commande pour son groupe. Il peut également contenir une logique pour désactiver le bouton "Passer à la caisse" ou fournir des instructions sur la façon d'atteindre le minimum.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :
    *   Le module ne crée pas de tables SQL personnalisées.
    *   Les paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide de clés telles que `CGMA_EXCV`, `CGMA_TAX`, `CGMA_FREE`, `CGMA_FIRST_ORDER` et `CGMA_[GROUP_ID]_[CURRENCY_ID]` pour les valeurs minimales par groupe et par devise. `PS_CURRENCY_DEFAULT` est également référencé.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `stepBeforePaymentOPC` | Avant l'étape de paiement dans la commande en une page. | Empêche les clients de passer au paiement si la valeur minimale de commande n'est pas atteinte. |
| `displayPaymentTop` | En haut de la section des options de paiement lors du passage en caisse. | Affiche un message d'avertissement si la valeur minimale de commande n'est pas atteinte. |
| `displaystepBeforePaymentOPC` | Similaire à `stepBeforePaymentOPC`, souvent utilisé pour afficher du contenu ou des vérifications supplémentaires. | S'assure que la valeur minimale de commande est atteinte avant le paiement, affichant potentiellement un message. |
| `displayShoppingCart` | Sur la page de résumé du panier. | Valide le total du panier et affiche un message d'avertissement si le minimum n'est pas atteint, désactivant potentiellement les boutons de paiement. |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Injecte les fichiers CSS (`cgma.css`) et JavaScript (`cgma.js`) nécessaires pour la fonctionnalité et le style du front-office. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour accéder aux dernières versions du module "Valeur minimale de commande par groupe de clients", veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir.
