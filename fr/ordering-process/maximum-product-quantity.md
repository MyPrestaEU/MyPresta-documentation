---
title: "Quantité maximale de produit - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop « Quantité maximale de produit » par MyPresta.eu."
sidebar:
  label: "Quantité maximale de produit"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Maximum product quantity sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-product-quantity.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/maximum-product-quantity/)
>
> ---


# Quantité maximale de produit

## 1. Exigences et compatibilité
-   **Versions PrestaShop prises en charge :** PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilité PHP :** PHP 5.6 - 8.5
-   **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement requise.

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Quantité maximale de produit)

La page de configuration principale du module est l'endroit où vous définissez les paramètres globaux et gérez les limites de quantité spécifiques aux produits.

#### **Paramètres généraux**

-   **Ce que fait ce paramètre :** Ce sont les paramètres de base qui activent ou désactivent la fonctionnalité du module et définissent son comportement global.
-   **Effet de la modification de ce paramètre :**
    -   *Activer/Désactiver le module :* Active ou désactive l'ensemble du système de limitation de quantité.
    -   *Quantité maximale globale :* Définit une quantité maximale par défaut pour tous les produits si aucune limite spécifique n'est définie.
-   **Valeur recommandée :** Commencez par activer le module et définissez un maximum global raisonnable si vous souhaitez appliquer une règle générale.
-   **Scénario / exemple de marchand :** Si vous voulez vous assurer qu'aucun client ne peut jamais acheter plus de 100 unités de *n'importe quel* produit, définissez le maximum global à 100.

#### **Limites de quantité spécifiques aux produits**

Cette section est généralement un tableau ou une liste où vous pouvez rechercher des produits et définir des limites spécifiques pour eux.

-   **Ce que fait ce paramètre :** Vous permet de remplacer les paramètres globaux pour des produits individuels. Vous pouvez spécifier :
    -   **Quantité maximale par commande :** Le nombre le plus élevé d'unités de ce produit qu'un client peut ajouter à un seul panier.
    -   **Quantité maximale par client (total) :** Le nombre le plus élevé d'unités de ce produit qu'un client spécifique peut acheter *sur toutes ses commandes*.
    -   **Limites spécifiques au groupe de clients :** Appliquer des limites différentes en fonction du groupe de clients (par exemple, « Invités », « Clients », « Grossistes »).
-   **Effet de la modification de ce paramètre :**
    -   *Lorsque des limites sont définies :* Le module appliquera ces limites spécifiques pour le produit choisi, annulant tous les paramètres globaux.
    -   *Lorsque les limites sont supprimées :* Le produit reviendra à l'utilisation des paramètres de quantité maximale globale.
-   **Valeur recommandée :** Définissez des limites spécifiques pour les produits à forte demande, à faible stock ou stratégiquement importants.
-   **Scénario / exemple de marchand :**
    -   Vous avez un produit en édition limitée. Vous définissez la « Quantité maximale par commande » à 1 et la « Quantité maximale par client (total) » à 1 pour garantir une unité par client.
    -   Pour un article en vrac, vous pourriez définir la « Quantité maximale par commande » à 50 pour les « Clients » mais à 500 pour les « Grossistes ».

#### **Paramètres de suivi de l'historique des commandes**

-   **Ce que fait ce paramètre :** Contrôle si le module examine les commandes passées d'un client pour appliquer les limites de « quantité maximale par client (total) ». Vous pouvez souvent spécifier quels statuts de commande comptent pour la limite (par exemple, uniquement les commandes « Livrées » ou « Paiement accepté »).
-   **Effet de la modification de ce paramètre :**
    -   *Lorsque activé :* Le module interrogera l'historique des commandes du client pour calculer ses achats totaux d'un produit.
    -   *Lorsque désactivé :* Seule la quantité du panier actuel sera vérifiée par rapport à la limite de « quantité maximale par commande ». Les limites de « quantité maximale par client (total) » seront effectivement ignorées.
-   **Valeur recommandée :** Activez ceci si vous souhaitez appliquer de véritables limites par client au fil du temps. Sélectionnez les statuts de commande pertinents (par exemple, « Paiement accepté », « Livré ») pour suivre précisément les achats.
-   **Scénario / exemple de marchand :** Vous organisez une promotion où chaque client ne peut acheter qu'un maximum de 3 unités d'un produit spécifique *à vie*. Vous activez le suivi de l'historique des commandes et sélectionnez les statuts « Paiement accepté » et « Livré ». Si un client a déjà acheté 2 unités, il ne peut en ajouter qu'une de plus à son panier.

#### **Personnalisation du message d'erreur**

-   **Ce que fait ce paramètre :** Vous permet de personnaliser le message affiché aux clients lorsqu'ils dépassent une limite de quantité.
-   **Effet de la modification de ce paramètre :** Le message d'erreur générique par défaut sera remplacé par votre texte personnalisé, qui peut être plus informatif ou de marque.
-   **Valeur recommandée :** Fournissez un message clair, poli et utile. Vous pouvez utiliser des espaces réservés (si pris en charge par le module) comme `{max_quantity}` pour afficher la limite réelle.
-   **Scénario / exemple de marchand :** Au lieu de « La quantité dépasse le maximum », vous pourriez le définir à : « Désolé, vous ne pouvez acheter qu'un maximum de {max_quantity} unités de cet article. Cela nous aide à garantir un accès équitable à tous nos clients ! »

#### **Exportation et importation CSV / JSON (si disponible)**

-   **Ce que fait ce paramètre :** Fournit des outils pour exporter vos limites de quantité actuelles vers un fichier CSV ou JSON, et importer de nouvelles limites à partir de ces fichiers. Ceci est utile pour l'édition en masse ou la migration des paramètres.
-   **Effet de la modification de ce paramètre :**
    -   *Exportation :* Crée un fichier avec toutes vos limites de quantité de produit définies.
    -   *Importation :* Écrase ou ajoute de nouvelles limites de quantité basées sur les données du fichier téléchargé.
-   **Valeur recommandée :** Utilisez ceci pour les mises à jour à grande échelle ou la configuration initiale si vous avez de nombreux produits avec des limites spécifiques. Sauvegardez toujours vos paramètres actuels avant d'importer.
-   **Scénario / exemple de marchand :** Vous lancez un nouveau catalogue avec 500 produits, chacun nécessitant une quantité maximale unique. Au lieu de saisir manuellement chacun, vous préparez un fichier CSV et l'importez.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
|---|---|---|---|
| Configuration du module | Activer/Désactiver le module | Activé | Active/désactive toutes les fonctionnalités de limitation de quantité. |
| Configuration du module | Quantité maximale globale par commande | Varie / 100 | Définit une quantité maximale par défaut pour les produits sans limites spécifiques. |
| Configuration du module | Quantité maximale spécifique au produit par commande | Varie / Personnalisé | Remplace la limite globale pour les produits individuels dans un seul panier. |
| Configuration du module | Quantité maximale spécifique au produit par client (Total) | Varie / Personnalisé | Limite les achats totaux d'un produit par un client sur toutes les commandes. |
| Configuration du module | Limites spécifiques au groupe de clients | Varie / Personnalisé | Applique des limites différentes en fonction des groupes de clients (par exemple, Grossistes). |
| Configuration du module | Suivre l'historique des commandes | Activé | Vérifie les commandes passées pour appliquer la « Quantité maximale par client (Total) ». |
| Configuration du module | Statuts de commande pour le suivi | Paiement accepté, Livré | Définit quels statuts de commande comptent pour les achats totaux du client. |
| Configuration du module | Message d'erreur personnalisé | « La quantité dépasse la limite » | Personnalise le message affiché aux clients lorsqu'une limite est atteinte. |
| Configuration du module | Exporter/Importer CSV/JSON | N/A | Permet la gestion en masse des limites de quantité via le téléchargement/téléchargement de fichiers. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai défini des limites, mais les clients peuvent toujours ajouter plus que ce qui est autorisé. Qu'est-ce qui ne va pas ?**
R1 :
*   **Module activé ?** Tout d'abord, vérifiez que le module est activé dans la configuration principale.
*   **Produit spécifique vs. Global :** Assurez-vous que vous avez correctement défini les limites pour le *produit spécifique* en question, ou que les limites globales sont actives si aucune limite spécifique au produit n'existe.
*   **Groupe de clients :** Vérifiez que le groupe de clients auquel appartient le client a les limites correctes appliquées.
*   **Cache :** Videz votre cache PrestaShop (Paramètres avancés > Performances > Vider le cache). Parfois, d'anciens paramètres sont encore servis.
*   **Conflits de thème :** Rarement, un thème fortement personnalisé peut interférer avec la façon dont les entrées de quantité sont gérées. Testez avec le thème PrestaShop par défaut pour exclure cette possibilité.

**Q2 : La « quantité maximale par client (total) » ne fonctionne pas, même avec le suivi de l'historique des commandes activé.**
R2 :
*   **Statuts de commande :** Allez dans la configuration du module et vérifiez quels « Statuts de commande pour le suivi » sont sélectionnés. Si les commandes précédentes d'un client sont dans un statut non sélectionné (par exemple, « En attente » au lieu de « Livré »), elles ne seront pas prises en compte pour la limite. Assurez-vous que les statuts pertinents sont cochés.
*   **Connexion client :** Assurez-vous que le client est connecté. Le module ne peut suivre les achats précédents que pour les clients identifiés, pas les invités.

**Q3 : Comment traduire les messages d'erreur dans d'autres langues ?**
R3 :
*   Naviguez vers **International > Traductions** dans votre Back Office PrestaShop.
*   Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez votre langue.
*   Recherchez le module « Quantité maximale de produit » dans la liste. Vous devriez pouvoir modifier les messages d'erreur personnalisés que vous avez définis pour chaque langue.

**Q4 : Le module semble ralentir mes pages produits ou mon panier.**
R4 :
*   Bien que le module soit optimisé, si vous avez un très grand nombre de produits avec des limites complexes, spécifiques aux groupes et un suivi étendu de l'historique des commandes, cela pourrait ajouter une légère surcharge.
*   **Performances > CCC :** Assurez-vous que vos paramètres CCC (Combiner, Compresser, Mettre en cache) pour CSS et JavaScript sont activés dans **Paramètres avancés > Performances**.
*   **Ressources du serveur :** Vérifiez la limite de mémoire PHP et le temps d'exécution de votre serveur. S'ils sont trop bas, cela peut avoir un impact sur les performances.
*   **Optimisation de la base de données :** Assurez-vous que votre base de données PrestaShop est régulièrement optimisée.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module « Quantité maximale de produit ».

### 4.1 Aperçu de l'architecture
Le module `Quantité maximale de produit` (nom interne `mqc`) est un module PrestaShop standard conçu pour étendre le processus de commande principal. Il fonctionne principalement en se connectant à divers points du front-office (page produit, panier, commande) pour valider les quantités de produits par rapport aux limites configurées. La configuration est gérée via une seule méthode `getContent()` dans le fichier principal du module, en utilisant la classe `Configuration` de PrestaShop pour stocker les paramètres. Il utilise JavaScript pour la validation front-end et le retour utilisateur, et les templates Smarty pour afficher les messages et les formulaires de configuration.

### 4.2 Contrôleurs (`controllers/`)
Ce module ne contient pas de contrôleurs front-office ou back-office dédiés. Toute la logique front-office est gérée via des hooks et JavaScript, tandis que la configuration back-office est gérée directement dans la méthode `getContent()` du fichier `index.php` du module.

### 4.3 Classes et modèles principaux (`classes/`)
Le module ne définit pas de classes `ObjectModel` personnalisées. Toutes les données sont stockées directement dans la table `ps_configuration` à l'aide de clés de configuration PrestaShop standard. La logique principale réside dans le fichier `mqc/index.php`.

### 4.4 Assets JavaScript (`views/js/`)

-   **`mqc/views/js/mqc-17500.js`** :
    *   **Portée :** Front-office (spécifique à PrestaShop 1.7.5.0+).
    *   **Responsabilité :** Contient la logique JavaScript adaptée aux versions plus récentes de PrestaShop 1.7.x et 8.x. Il se connecte probablement à `prestashop.on('updateProduct', ...)` ou à des événements similaires pour revalider les quantités lorsque les attributs du produit changent ou lorsque l'entrée de quantité est modifiée sur la page du produit. Il peut également gérer les appels AJAX au fichier `index.php` du module pour obtenir une validation de quantité en temps réel.
    *   **Interaction :** Se lie aux champs de saisie de quantité, aux boutons d'ajout au panier et potentiellement aux sélecteurs d'attributs de produit pour fournir un retour immédiat à l'utilisateur si une limite de quantité est dépassée.

-   **`mqc/views/js/mqc-front.js`** :
    *   **Portée :** Front-office (général, potentiellement pour les anciennes versions de PrestaShop ou la logique commune).
    *   **Responsabilité :** Contient la logique JavaScript générale du front-office pour la validation de quantité. Cela peut inclure :
        *   Des écouteurs d'événements pour les changements d'entrée de quantité sur la page du produit ou dans le panier.
        *   Des appels AJAX au serveur pour vérifier les limites de quantité.
        *   L'affichage des messages d'erreur à l'utilisateur.
        *   Potentiellement la désactivation ou la limitation des champs de saisie de quantité.
    *   **Interaction :** Similaire à `mqc-17500.js` mais peut utiliser une liaison d'événements basée sur jQuery plus ancienne ou des événements PrestaShop moins spécifiques.

-   **`mqc/views/js/mqc.js`** :
    *   **Portée :** Back-office.
    *   **Responsabilité :** Gère le JavaScript pour la page de configuration du module dans le Back Office de PrestaShop. Cela pourrait inclure :
        *   Des éléments de formulaire dynamiques (par exemple, ajout/suppression de lignes de limite spécifiques au produit).
        *   La recherche AJAX de produits lors de la définition de limites individuelles.
        *   La validation des champs de saisie sur le formulaire de configuration.
        *   La logique pour les fonctionnalités d'import/export CSV/JSON.
    *   **Interaction :** Se lie aux éléments de formulaire sur la page de configuration du module, effectuant potentiellement des requêtes AJAX à la méthode `getContent()` du module pour la récupération ou la soumission de données.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`mqc/views/css/mqc.css`** :
    *   **Portée :** À la fois Front-office (pour les messages d'erreur) et Back-office (pour le style de la page de configuration).
    *   **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :**
        *   Conteneurs de messages d'erreur (par exemple, `div.alert.alert-danger` ou des classes personnalisées pour les messages spécifiques au module).
        *   Champs de saisie et étiquettes sur la page de configuration du back-office.
        *   Potentiellement le style des éléments dynamiques ajoutés par `mqc.js` (par exemple, les résultats de recherche de produits, les lignes de tableau pour les limites).
    *   **Sélecteurs de classes CSS clés que les développeurs peuvent remplacer :** Recherchez des classes comme `.mqc-error-message`, `.mqc-limit-table`, `.mqc-product-search-results` dans les templates du module et le HTML généré. Les développeurs peuvent les remplacer dans le `custom.css` de leur thème ou en créant un thème enfant.

### 4.6 Structure des templates Smarty (`views/templates/`)

Le module utilise des templates Smarty pour l'affichage front-office et la configuration back-office.

-   **Templates de hook (`views/templates/hook/`)** :
    *   **`product-details.tpl`** :
        *   **Hook :** Probablement `displayProductExtraContent` ou `displayProductButtons` (selon la version de PrestaShop et l'implémentation spécifique).
        *   **Sortie :** Pourrait afficher un petit message d'information sur les limites de quantité sur la page du produit, ou rendre un champ de saisie de quantité personnalisé si le module remplace celui par défaut.
    *   **`productActions.tpl`** :
        *   **Hook :** `displayProductActions` (sur la page du produit).
        *   **Sortie :** Potentiellement utilisé pour injecter des variables JavaScript ou des entrées cachées liées aux limites de quantité près du bouton d'ajout au panier, ou pour afficher un message d'erreur si une limite de quantité est dépassée avant d'ajouter au panier.
    *   **`shoppingCart.tpl`** :
        *   **Hook :** `displayShoppingCartFooter` ou `displayShoppingCart` (sur la page du panier).
        *   **Sortie :** Utilisé pour afficher des messages d'erreur directement dans le panier si les quantités dépassent les limites, empêchant le passage à la caisse.

-   **Templates d'administration (`views/templates/admin/`)** : Ces templates sont rendus dans la méthode `getContent()` de `mqc/index.php` pour construire l'interface de configuration du module.
    *   **`admintab.tpl`** : Probablement un wrapper ou un en-tête/pied de page commun pour la page de configuration de l'administration.
    *   **`button-subcategories-purchases.tpl`** : Pourrait être un bouton ou une section liée à la gestion des achats par sous-catégories, éventuellement pour des rapports avancés ou la définition de limites.
    *   **`button-subcategories.tpl`** : Similaire à ce qui précède, mais pour les sous-catégories en général.
    *   **`csv.tpl`** : Template pour la fonctionnalité d'exportation CSV, contenant potentiellement des éléments de formulaire pour la sélection des options d'exportation.
    *   **`csv_file.tpl`** : Template pour la fonctionnalité d'importation CSV, généralement un formulaire de téléchargement.
    *   **`json.tpl`** : Template pour l'exportation/importation JSON, similaire à `csv.tpl` et `csv_file.tpl`.
    *   **`main.tpl`** : Le template principal pour la page de configuration du module, contenant la structure principale du formulaire, les paramètres généraux et potentiellement un tableau pour les limites spécifiques aux produits.
    *   **`message.tpl`, `message2.tpl`, `message3.tpl`, `message4.tpl`, `message5.tpl`** : Templates de messages génériques utilisés pour afficher des messages de succès, d'erreur ou d'information dans la configuration du back-office.
    *   **`orderstates.tpl`** : Template pour la sélection des statuts de commande qui comptent pour la limite de « quantité maximale par client (total) ».

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    *   Le module ne crée pas de tables SQL personnalisées.
    *   Tous les paramètres de configuration sont stockés dans la table `ps_configuration`. Les clés de configuration suivront généralement un modèle comme `MQC_GLOBAL_MAX_QTY`, `MQC_PRODUCT_LIMITS_[id_product]`, `MQC_TRACK_HISTORY_STATUSES`, etc. Les limites spécifiques aux produits peuvent être stockées sous forme de tableaux sérialisés ou de chaînes JSON dans une seule clé de configuration, ou de clés individuelles par produit/groupe.
    *   Le suivi de l'historique des commandes repose sur l'interrogation des tables PrestaShop existantes : `ps_orders`, `ps_order_detail` et `ps_order_state`.

-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
|---|---|---|
| `displayHeader` | Dans la section `<head>` de chaque page. | Enregistre les assets CSS et JavaScript (`mqc.css`, `mqc-front.js`, `mqc-17500.js`) pour la fonctionnalité front-office. |
| `displayProductButtons` | Près du bouton « Ajouter au panier » sur la page du produit. | Injecte la logique de validation de quantité ou affiche des messages liés aux limites spécifiques au produit. |
| `displayProductExtraContent` | Sous la description du produit, au-dessus des produits connexes. | Peut être utilisé pour afficher des messages d'information sur les limites de quantité. |
| `displayShoppingCart` | Dans le résumé du panier. | Valide les quantités dans le panier et affiche des messages d'erreur si les limites sont dépassées. |
| `displayShoppingCartFooter` | En bas de la page du panier. | Similaire à `displayShoppingCart`, pour la validation finale avant le paiement. |
| `actionValidateOrder` | Après qu'une commande a été validée et enregistrée. | Potentiellement utilisé pour le traitement ou la journalisation post-commande, bien que la validation principale soit avant le paiement. |
| `actionCartSave` | Après qu'un panier est enregistré ou mis à jour (par exemple, changement de quantité). | Crucial pour la validation de quantité en temps réel lorsqu'un client modifie les quantités dans le panier ou ajoute de nouveaux produits. |
| `actionFrontControllerSetMedia` | Avant qu'un contrôleur frontal ne rende sa sortie. | Enregistre les assets front-office, similaire à `displayHeader` mais plus spécifique au contexte du contrôleur. |
| `actionAdminControllerSetMedia` | Avant qu'un contrôleur d'administration ne rende sa sortie. | Enregistre les assets back-office (`mqc.js`, `mqc.css`) pour la page de configuration du module. |

## 5. Support officiel et mises à jour
Pour les dernières mises à jour, corrections de bugs et support officiel du module « Quantité maximale de produit », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour aider les marchands et les développeurs avec tout problème ou question concernant la fonctionnalité et l'intégration du module.
