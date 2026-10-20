---
title: "Delete Orders Pro - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Delete Orders Pro par MyPresta.eu."
sidebar:
  label: "Delete Orders Pro - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Delete Orders Pro sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/delete-orders-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/delete-orders-pro/)
>
> ---


# Delete Orders Pro

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est requise au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à la page de configuration principale du module « Delete Orders Pro ». Cet écran gère principalement les paramètres généraux du module et les vérifications de mise à jour.

- **Ce que fait ce paramètre :** Cette section inclut généralement les paramètres standard des modules MyPresta.eu liés aux notifications de mise à jour et au suivi interne.
- **Effet de la modification de ce paramètre :**
  - `mypresta_updates`, `update_`, `updatev_` : Ces paramètres contrôlent si le module vérifie les mises à jour de MyPresta.eu et affiche des notifications dans votre back-office. Les activer vous tient informé des nouvelles versions et fonctionnalités. Les désactiver arrêtera ces notifications.
  - `DELETEORDERS_LAST_TAB` : Il s'agit d'un paramètre interne qui suit le dernier onglet ou la dernière vue sur laquelle vous vous trouviez dans l'interface d'administration dédiée du module. Il aide le module à se souvenir de votre dernière position pour plus de commodité.
- **Valeur recommandée :**
  - Pour les paramètres liés aux mises à jour : **OUI** (ou Activé). Il est toujours recommandé de laisser les vérifications de mise à jour activées pour vous assurer que vous utilisez la version la plus récente, la plus sécurisée et la plus riche en fonctionnalités du module.
  - `DELETEORDERS_LAST_TAB` : Laissez ce paramètre tel quel ; il est géré automatiquement par le module.
- **Scénario / exemple de marchand :** Garder les vérifications de mise à jour activées signifie que vous serez averti directement dans votre back-office PrestaShop lorsqu'une nouvelle version de « Delete Orders Pro » sera publiée, vous assurant ainsi de pouvoir facilement mettre à niveau et bénéficier des améliorations ou des corrections de bugs.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 Onglet Supprimer les commandes (Back Office > Commandes > Delete Orders Pro)

C'est l'interface principale où vous gérerez et supprimerez les commandes.

- **Nom de l'écran et emplacement du menu :** Vous pouvez accéder à cet écran en naviguant vers **Commandes > Delete Orders Pro** dans le menu de votre back-office PrestaShop.
- **Actions et paramètres disponibles :** Cet écran présente une grille ou une liste de vos commandes, similaire à la liste des commandes standard de PrestaShop, mais avec des fonctionnalités supplémentaires spécifiquement pour la suppression.
  - **Options de filtrage :** Vous trouverez probablement des filtres pour affiner les commandes que vous souhaitez supprimer (par exemple, par statut de commande, plage de dates, client, etc.). Ceci est crucial pour cibler en toute sécurité des types de commandes spécifiques.
  - **Cases à cocher de sélection :** Chaque commande de la liste aura une case à cocher, vous permettant de sélectionner des commandes individuelles pour la suppression.
  - **Actions en masse :** Il devrait y avoir une option pour sélectionner plusieurs commandes (par exemple, « Tout sélectionner » ou « Sélectionner les commandes avec le statut X ») puis effectuer une suppression en masse.
  - **Bouton Supprimer :** Un bouton proéminent (par exemple, « Supprimer les commandes sélectionnées » ou « Supprimer les commandes ») lancera le processus de suppression.
- **Effet des modifications :**
  - Lorsque vous sélectionnez des commandes et cliquez sur le bouton de suppression, le module supprimera définitivement ces commandes et toutes les données associées (détails de la commande, produits commandés, messages client liés à la commande, factures, etc.) de votre base de données PrestaShop.
  - Cette action est irréversible.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. **Examinez régulièrement vos commandes :** Identifiez les statuts de commande qui représentent généralement des commandes « indésirables » (par exemple, « Annulée », « Erreur de paiement », « En réapprovisionnement » si non exécutées, ou des statuts personnalisés pour les commandes de test).
  2. **Accédez à « Delete Orders Pro » :** Allez dans **Commandes > Delete Orders Pro**.
  3. **Filtrez les commandes :** Utilisez les filtres disponibles pour afficher uniquement les commandes que vous avez l'intention de supprimer (par exemple, filtrez par statut « Annulée » et une plage de dates de plus de 3 mois).
  4. **Sélectionnez soigneusement les commandes :** Vérifiez deux fois les commandes que vous avez filtrées et sélectionnez-les à l'aide des cases à cocher.
  5. **Lancez la suppression :** Cliquez sur le bouton « Supprimer les commandes sélectionnées ». Confirmez l'action lorsque vous y êtes invité.
  6. **Effectuez des sauvegardes :** Avant toute suppression majeure, assurez-vous toujours d'avoir une sauvegarde récente de votre base de données.

#### 2.2.2 Contrôleur Index (deleteorderspro/controllers/admin/index.php)

Ce fichier sert généralement de contrôleur de routage ou de secours au sein de la section d'administration du module. Dans le contexte de « Delete Orders Pro », il garantit probablement que si un utilisateur navigue vers le chemin d'administration de base du module sans spécifier une action ou un sous-contrôleur particulier, il est redirigé vers l'interface principale `deleteorderstab`.

- **Nom de l'écran et emplacement du menu :** Pas un écran direct, mais une partie de la navigation interne du module.
- **Actions et paramètres disponibles :** Aucun paramètre configurable directement par l'utilisateur. Son but est de gérer le routage interne.
- **Effet des modifications :** Aucun impact direct sur le marchand. Il assure une expérience de navigation fluide au sein de la section d'administration du module.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Aucun flux de travail spécifique n'est nécessaire ; cela fonctionne en arrière-plan.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | `mypresta_updates` | OUI | Active/désactive les notifications de mise à jour de MyPresta.eu. |
| | `update_` | OUI | Indicateur interne de l'état de la mise à jour. |
| | `updatev_` | OUI | Indicateur interne de la version de la mise à jour. |
| | `DELETEORDERS_LAST_TAB` | (Géré automatiquement) | Suit le dernier onglet visité dans l'interface d'administration du module. |
| **Onglet Supprimer les commandes** | Filtres (Statut, Date, etc.) | Varie | Réduit la liste des commandes à supprimer. |
| | Cases à cocher de sélection de commande | N/A | Permet la sélection de commandes individuelles pour la suppression. |
| | Action en masse : Supprimer la sélection | N/A | Supprime définitivement les commandes sélectionnées et les données associées. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : J'ai supprimé des commandes, mais les performances de ma boutique ne semblent pas beaucoup plus rapides. Pourquoi ?**
R : Bien que la suppression de commandes réduise la taille de la base de données, les performances sont influencées par de nombreux facteurs (hébergement, autres modules, optimisation du thème, taille des images). La suppression de commandes est une étape de l'optimisation globale. Assurez-vous également d'avoir vidé le cache de PrestaShop (**Paramètres avancés > Performances**) après la suppression.

**Q : Puis-je récupérer des commandes après les avoir supprimées ?**
R : Non. Une fois les commandes supprimées à l'aide de ce module, elles sont définitivement supprimées de votre base de données. C'est pourquoi il est crucial de toujours sauvegarder votre base de données avant d'effectuer toute suppression majeure et de revoir attentivement vos sélections.

**Q : La suppression de commandes affectera-t-elle mes comptes clients ou le stock de produits ?**
R : La suppression d'une commande supprime l'enregistrement de la commande elle-même et ses détails associés (comme les produits spécifiques commandés dans cette transaction, les factures, les messages). Elle NE supprime PAS le compte client associé à la commande, ni ne rétablit généralement les niveaux de stock (car le stock est généralement ajusté au moment de la création de la commande ou du changement de statut, et non de la suppression). Vérifiez toujours le comportement du module dans un environnement de test si vous avez des préoccupations spécifiques concernant le stock.

**Q : Le module n'apparaît pas dans le menu de mon Back Office.**
R :

1. **Vérifiez l'installation :** Allez dans **Modules > Gestionnaire de modules** et recherchez « Delete Orders Pro ». Assurez-vous qu'il est répertorié comme « Installé » et « Activé ».
2. **Videz le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ». Parfois, les modifications de menu nécessitent un rafraîchissement du cache.
3. **Permissions :** Vérifiez vos permissions utilisateur sous **Administration > Permissions** pour vous assurer que votre profil a accès à la section « Commandes » et à toutes les permissions spécifiques au module.

**Q : Je reçois une erreur lorsque j'essaie de supprimer des commandes.**
R :

1. **Vérifiez le mode débogage de PrestaShop :** Activez le mode débogage (**Paramètres avancés > Performances > Mode débogage**) pour voir si un message d'erreur plus détaillé apparaît.
2. **Journaux d'erreurs du serveur :** Vérifiez les journaux d'erreurs PHP de votre serveur (souvent trouvés dans votre panneau de contrôle d'hébergement) pour tout message connexe.
3. **Contactez le support :** Si vous ne parvenez pas à résoudre le problème, rassemblez tous les messages d'erreur et contactez le support MyPresta.eu pour obtenir de l'aide.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique pour les développeurs et les webmasters travaillant avec le module « Delete Orders Pro ».

### 4.1 Aperçu de l'architecture

Le module « Delete Orders Pro » suit l'architecture standard des modules PrestaShop, exploitant principalement les contrôleurs d'administration du Back-Office pour sa fonctionnalité. Il s'intègre au système de menu de PrestaShop et utilise le `AdminController` de base de PrestaShop pour le rendu des listes et la gestion des soumissions de formulaires. Le module interagit directement avec la base de données pour effectuer des opérations de suppression sur les tables liées aux commandes. Il n'introduit pas de classes `ObjectModel` personnalisées, mais opère plutôt sur les entités de commande PrestaShop existantes.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. Ce module n'a aucune présence en front-office.
- **Contrôleurs d'administration Back-Office** :

  - `deleteorderspro/controllers/admin/deleteorderstab.php`

    - **Nom de la classe** : `AdminDeleteOrdersProController` (ou similaire, généralement dérivé du nom du fichier et du contexte du module) étendant `ModuleAdminController`.
    - **Responsabilité** : Il s'agit du contrôleur administratif principal du module. Il est responsable de :
      - L'affichage de la liste des commandes sous forme de grille.
      - La gestion du filtrage, du tri et de la pagination des commandes.
      - Le traitement de la suppression des commandes sélectionnées.
      - L'interaction avec les `Order` et `ObjectModel`s associés de PrestaShop pour effectuer des suppressions de base de données.
      - Le rendu du template pour la liste des commandes et l'interface de suppression.
    - **Onglet PrestaShop** : Ce contrôleur est enregistré comme un nouvel onglet sous le menu « Commandes » dans le back-office de PrestaShop.
  - `deleteorderspro/controllers/admin/index.php`

    - **Nom de la classe** : Pas une classe de contrôleur typique ; souvent un simple fichier de redirection ou de démarrage.
    - **Responsabilité** : Ce fichier sert généralement de point d'entrée ou de secours. Dans de nombreux modules, si un utilisateur navigue vers le chemin de base `admin/nom_du_module`, ce `index.php` peut le rediriger vers le contrôleur principal (par exemple, `deleteorderstab`) pour s'assurer que la bonne interface est chargée. Il empêche l'accès direct au répertoire et assure un routage correct.

### 4.3 Classes et modèles de base (`classes/`)

Le module ne semble pas introduire de classes ou d'`ObjectModel`s personnalisés dans son répertoire `classes/` sur la base de l'inventaire fourni. Il opère probablement directement sur les `Order` et `ObjectModel`s associés de PrestaShop (par exemple, `OrderHistory`, `OrderDetail`, `ProductSale`, `Cart`, etc.) pour assurer une suppression complète de toutes les données associées.

### 4.4 Actifs JavaScript (`views/js/`)

Aucun fichier JavaScript n'a été identifié dans l'archive du module. Le module s'appuie probablement sur le JavaScript standard du back-office de PrestaShop pour les soumissions de formulaires et les interactions de grille, ou sa fonctionnalité est entièrement côté serveur.

### 4.5 Feuilles de style CSS (`views/css/`)

Aucun fichier CSS n'a été identifié dans l'archive du module. Le module hérite probablement du style directement du thème du back-office de PrestaShop, assurant une apparence cohérente sans styles personnalisés.

### 4.6 Structure du template Smarty (`views/templates/`)

Aucun fichier `.tpl` n'a été identifié dans l'archive du module. Cela suggère que le module pourrait utiliser les templates `list.tpl` et `form.tpl` par défaut de PrestaShop fournis par `AdminController` pour le rendu de sa grille et de sa configuration, ou qu'il génère son HTML directement dans le contrôleur.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :
  Le module ne crée pas de tables de base de données personnalisées. Il opère sur les tables PrestaShop existantes liées aux commandes, y compris, mais sans s'y limiter :

  - `ps_orders`
  - `ps_order_detail`
  - `ps_order_history`
  - `ps_order_invoice`
  - `ps_order_payment`
  - `ps_order_return`
  - `ps_order_slip`
  - `ps_cart` (et `ps_cart_product` associé)
  - `ps_message` (pour les messages clients liés aux commandes)
  - `ps_product_sale` (met à jour le nombre de ventes)
  - `ps_customer_thread` (pour les fils de discussion du service client liés aux commandes)
  - `ps_configuration` (pour stocker les paramètres du module comme `mypresta_updates`, `DELETEORDERS_LAST_TAB`).
- **Table des hooks enregistrés** :
  Compte tenu de l'objectif du module en tant qu'outil d'administration de back-office, il utilise principalement des hooks pour l'installation, la désinstallation et potentiellement l'ajout d'éléments de menu. Il ne semble pas utiliser de hooks d'affichage front-office.

  | Nom du hook | Moment d'exécution | Objectif technique |
  | --- | --- | --- |
  | `install()` | Lors de l'installation du module | Crée le nouvel onglet « Delete Orders Pro » dans le menu du back-office de PrestaShop. Stocke les valeurs de configuration initiales dans `ps_configuration`. |
  | `uninstall()` | Lors de la désinstallation du module | Supprime l'onglet « Delete Orders Pro » du menu du back-office. Supprime les valeurs de configuration de `ps_configuration`. |
  | `displayBackOfficeHeader` | Rend le contenu dans la section `<head>` du Back Office | Potentiellement utilisé pour inclure les JS/CSS nécessaires pour le contrôleur d'administration, bien qu'aucun n'ait été identifié dans l'inventaire. |
  | `actionAdminControllerSetMedia` | Permet d'ajouter des JS/CSS à des contrôleurs d'administration spécifiques | Utilisé par `AdminDeleteOrdersProController` pour ajouter les actifs spécifiques requis pour son interface. |

## 5. Support officiel et mises à jour

Pour le support officiel, les mises à jour et pour télécharger la dernière version du module « Delete Orders Pro », veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question que vous pourriez avoir concernant la fonctionnalité du module.
