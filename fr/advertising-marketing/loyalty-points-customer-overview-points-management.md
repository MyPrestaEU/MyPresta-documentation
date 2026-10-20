---
title: "Points de fidélité – Aperçu client et gestion des points - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Points de fidélité – Aperçu client et gestion des points par MyPresta.eu."
sidebar:
  label: "Points de fidélité – Aperçu client et gestion des points - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Loyalty points – Customer overview & points management sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points-customer-overview-points-management.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/loyalty-points-customer-overview-points-management/)
>
> ---


# Points de fidélité – Aperçu client et gestion des points

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises pour PrestaShop lui-même et sont généralement disponibles sur tous les environnements d'hébergement compatibles.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à la page de configuration principale du module « Points de fidélité – Aperçu client et gestion des points ». Cet écran fournit les paramètres généraux du comportement du module.

#### Activer la notification manuelle par e-mail

- **Ce que fait ce paramètre :** Ce commutateur contrôle si une notification par e-mail est envoyée au client lorsque vous ajustez manuellement ses points de fidélité.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Si vous ajoutez ou supprimez manuellement des points pour un client, il recevra un e-mail l'informant du changement et de son nouveau solde. Cela aide à maintenir les clients informés et à renforcer la transparence.
  - *Lorsqu'il est désactivé :* Les ajustements manuels de points se feront silencieusement, sans aucune notification par e-mail au client. Cela peut être préféré pour des corrections internes mineures ou si vous gérez la communication client par d'autres canaux.
- **Valeur recommandée :** OUI
- **Scénario / exemple de marchand :** Vous venez d'ajouter 50 points bonus au compte d'un client comme cadeau d'anniversaire. Si ce paramètre est activé, le client reçoit immédiatement un e-mail disant : « Joyeux anniversaire ! Nous avons ajouté 50 points de fidélité à votre compte. Votre nouveau solde est de X points. » Cela améliore l'expérience client et rend la récompense tangible.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### Gestion des points de fidélité client (Back Office > Catalogue > Points de fidélité)

C'est l'écran de gestion principal du module, accessible via un nouvel élément de menu dans votre back office PrestaShop.

- **Nom de l'écran et emplacement du menu :** **Catalogue > Points de fidélité** (ou similaire, selon votre version de PrestaShop et la personnalisation du menu).
- **Actions et paramètres disponibles :**
  - **Liste des clients :** Vous verrez une liste complète de tous vos clients, ainsi que leurs soldes de points de fidélité actuels.
  - **Recherche et filtre :** Trouvez facilement des clients spécifiques par nom, e-mail ou ID.
  - **Afficher l'historique :** Pour chaque client, vous pouvez cliquer pour afficher un journal détaillé de toutes les transactions de points de fidélité (gagnés, dépensés, expirés et ajustés manuellement).
  - **Ajouter/Supprimer des points :**
    - Cliquez sur la ligne d'un client ou sur une icône « Modifier » pour accéder à son interface de gestion de points individuelle.
    - Vous trouverez des champs pour ajouter ou soustraire manuellement un nombre spécifique de points de fidélité.
    - Un champ « Raison » vous permet de noter pourquoi l'ajustement a été effectué (par exemple, « Bonus d'anniversaire », « Compensation pour commande retardée », « Correction de points »). Cette raison est cruciale pour vos dossiers internes et pour le service client.
    - Lors de l'enregistrement, le solde du client est mis à jour, et si le paramètre « Activer la notification manuelle par e-mail » est actif, un e-mail est envoyé.
  - **Pagination :** La pagination standard de PrestaShop (`PS_LIST_LIMIT`) s'appliquera, vous permettant de contrôler le nombre de clients affichés par page.
- **Effet des changements :**
  - **Ajout de points :** Augmente le solde de points de fidélité du client. Cela peut être utilisé pour récompenser les clients, offrir une compensation ou lancer des promotions spéciales.
  - **Suppression de points :** Diminue le solde de points de fidélité du client. Cela peut être nécessaire pour corriger des erreurs, révoquer des points pour des commandes retournées ou gérer des activités frauduleuses.
  - **Affichage de l'historique :** Fournit une piste d'audit transparente de tous les mouvements de points, inestimable pour le support client et les rapports internes.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. **Vérifiez régulièrement les soldes de points des clients :** Surtout après des promotions ou si les clients signalent des écarts.
  2. **Utilisez le champ « Raison » avec diligence :** Fournissez toujours une raison claire et concise pour tout ajustement manuel. Cela vous fera gagner du temps et évitera la confusion plus tard lors de l'examen de l'historique ou de l'explication des changements aux clients.
  3. **Tirez parti des notifications par e-mail :** Pour les ajustements positifs (bonus, récompenses), l'activation des notifications par e-mail peut considérablement améliorer la satisfaction client et la connaissance de leurs avantages de fidélité. Pour les corrections, déterminez si un e-mail est nécessaire ou si des notes internes suffisent.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer la notification manuelle par e-mail | OUI | Contrôle si les clients reçoivent un e-mail lorsque leurs points de fidélité sont ajustés manuellement. |
| Catalogue > Points de fidélité | Liste des clients et recherche | N/A | Affiche tous les clients et leurs soldes de points de fidélité actuels. |
| Catalogue > Points de fidélité | Ajouter/Supprimer des points | N/A | Permet l'ajustement manuel des points de fidélité d'un client. |
| Catalogue > Points de fidélité | Raison de l'ajustement | N/A (Saisie requise) | Fournit une note interne expliquant pourquoi des points ont été ajoutés ou supprimés. |
| Catalogue > Points de fidélité | Afficher l'historique | N/A | Affiche un journal détaillé de toutes les transactions de points de fidélité pour un client spécifique. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q1 : J'ai ajouté des points, mais le client dit qu'il n'a pas reçu d'e-mail.**
R : Tout d'abord, vérifiez si « Activer la notification manuelle par e-mail » est défini sur OUI dans la configuration principale du module. Si c'est le cas, vérifiez les journaux d'e-mails de votre boutique (si disponibles) ou les journaux de courrier de votre serveur pour voir si l'e-mail a été envoyé. De plus, conseillez au client de vérifier son dossier de spam/courrier indésirable. Assurez-vous que les paramètres d'e-mail de votre PrestaShop sont correctement configurés et que votre serveur de messagerie fonctionne.

**Q2 : Je ne trouve pas l'élément de menu « Points de fidélité » dans mon Back Office.**
R : Après l'installation, le module devrait créer un nouvel élément de menu, généralement sous « Catalogue » ou « Clients ». S'il est manquant, essayez de vider le cache de votre PrestaShop (Paramètres avancés > Performances > Vider le cache). S'il n'apparaît toujours pas, assurez-vous que le module est activé et installé correctement. Vérifiez également vos permissions utilisateur dans **Paramètres avancés > Équipe > Profils** pour vous assurer que votre profil administrateur a accès au contrôleur du module.

**Q3 : Le solde des points de fidélité du client ne se met pas à jour sur le front office après que j'ai effectué une modification manuelle.**
R : Il s'agit généralement d'un problème de cache. Videz le cache de votre PrestaShop (Paramètres avancés > Performances > Vider le cache). Si vous utilisez un module de mise en cache tiers ou un CDN, videz également son cache. Le module met à jour directement la base de données, donc le front office devrait refléter les changements une fois le cache rafraîchi.

**Q4 : Puis-je importer/exporter des données de points de fidélité avec ce module ?**
R : Ce module se concentre sur la gestion manuelle et la visualisation dans le back office de PrestaShop. Il n'inclut pas de fonctionnalités d'importation/exportation intégrées pour les opérations de données en masse. Pour de telles tâches, vous devrez peut-être envisager des requêtes de base de données personnalisées ou d'autres modules spécialisés.

**Q5 : Que se passe-t-il si je désinstalle ce module ?**
R : Lors de la désinstallation, le module supprimera ses éléments de menu d'administration dédiés et potentiellement ses paramètres de configuration. Cependant, il est conçu pour gérer les points de fidélité existants, qui font généralement partie du système de fidélité de base de PrestaShop ou d'un autre module de fidélité. Les points eux-mêmes devraient rester dans la base de données, mais vous perdriez l'interface de gestion pratique fournie par ce module. Sauvegardez toujours votre base de données avant de désinstaller un module.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Points de fidélité – Aperçu client et gestion des points » (`myprestaloyalty_customerpoints`) est construit selon le modèle MVC de PrestaShop, étendant principalement `Module` pour sa fonctionnalité principale et `AdminController` pour son interface back-office dédiée. Il interagit avec le système de fidélité de base de PrestaShop (ou un module de fidélité compatible) en fournissant une couche de gestion améliorée. Le module introduit un `ObjectModel` personnalisé pour enregistrer les ajustements manuels de points, garantissant une piste d'audit.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Ce module n'inclut aucun contrôleur front-office dédié. Toutes les interactions client concernant les points de fidélité sont gérées par le module de fidélité de base de PrestaShop ou le thème lui-même.
- **Contrôleurs Admin Back-Office** :

  - `controllers/admin/AdminMyprestaloyaltyCustomerPointsController.php`
    - **Nom de la classe et classe parente** : `AdminMyprestaloyaltyCustomerPointsController` étend `ModuleAdminController`.
    - **Responsabilité** : C'est le contrôleur back-office principal pour la gestion des points de fidélité client. Il fournit la vue de liste des clients avec leurs soldes de fidélité, permet la recherche et le filtrage, et gère le formulaire pour ajouter/supprimer manuellement des points pour des clients individuels. Il gère l'entité `customer_points` (bien qu'il interagisse principalement avec les données de points de fidélité existantes, il enregistre également les modifications manuelles via `MyprestaloyaltyCustomerPointsManualLog`).
    - **Nom de l'onglet** : « Points de fidélité » (ou similaire, défini dynamiquement lors de l'installation).
    - **Entité gérée** : Il affiche et permet la modification des points de fidélité client, en enregistrant ces modifications.
  - `controllers/admin/index.php`
    - **Nom de la classe et classe parente** : Ce fichier sert généralement de placeholder ou de simple redirection dans les modules PrestaShop. Il peut contenir une instruction `die()` de base ou une redirection pour empêcher l'accès direct, garantissant que la logique du contrôleur est exécutée via le mécanisme de dispatching de PrestaShop. Il ne gère pas d'entité spécifique et ne fournit pas de vue distincte.

### 4.3 Classes et modèles principaux (`classes/`)

- `classes/MyprestaloyaltyCustomerPointsManualLog.php`
  - **Nom de la classe** : `MyprestaloyaltyCustomerPointsManualLog` étend `ObjectModel`.
  - **Table de base de données** : `_myprestaloyalty_customer_points_manual_log` (ou similaire, préfixé par `_DB_PREFIX_`).
  - **Champs `$definition`** :
    - `id_myprestaloyalty_customer_points_manual_log` : Clé primaire.
    - `id_customer` : L'ID du client dont les points ont été ajustés.
    - `id_employee` : L'ID de l'employé qui a effectué l'ajustement.
    - `points_change` : Le nombre de points ajoutés ou supprimés (peut être positif ou négatif).
    - `reason` : Un champ texte expliquant la raison de l'ajustement.
    - `date_add` : Horodatage de l'ajustement.
  - **Méthodes publiques clés et logique métier** : Cette classe est responsable de la persistance des détails de chaque ajustement manuel des points de fidélité effectué via l'interface back-office. Elle fournit un historique, crucial pour l'audit et le support client.

### 4.4 Actifs JavaScript (`views/js/`)

Le module n'inclut aucun fichier JavaScript personnalisé. Toutes les interactions sur l'écran de gestion du back-office sont gérées par les mécanismes par défaut de jQuery et de soumission de formulaire de PrestaShop.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module n'inclut aucun fichier CSS personnalisé. Il s'appuie sur le style par défaut du back-office de PrestaShop pour ses formulaires de configuration et ses vues de liste, garantissant une apparence cohérente.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module n'inclut aucun fichier de modèle Smarty personnalisé. Le formulaire de configuration et les vues de liste/édition de l'administration sont rendus à l'aide des modèles `getContent()` et `ModuleAdminController` par défaut de PrestaShop.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - `ps_myprestaloyalty_customer_points_manual_log` :
    - `id_myprestaloyalty_customer_points_manual_log` INT(10) UNSIGNED NOT NULL AUTO_INCREMENT
    - `id_customer` INT(10) UNSIGNED NOT NULL
    - `id_employee` INT(10) UNSIGNED NOT NULL
    - `points_change` INT(11) NOT NULL
    - `reason` TEXT NULL
    - `date_add` DATETIME NOT NULL
    - PRIMARY KEY (`id_myprestaloyalty_customer_points_manual_log`)
    - KEY `id_customer` (`id_customer`)
    - KEY `id_employee` (`id_employee`)
  - **Enregistrements de configuration (dans `ps_configuration`)** :
    - `PS_LOYALTY_MANUAL_EMAIL_ENABLED` : Stocke la valeur booléenne pour activer/désactiver les notifications par e-mail pour les ajustements manuels de points.
- **Table des hooks enregistrés** :
  Ce module fournit principalement des fonctionnalités back-office et n'enregistre aucun hook d'affichage front-office (`displayHeader`, `displayRightColumn`, `displayFooter`, `displayProductExtraContent`, etc.) ou hook d'action (`actionValidateOrder`, `actionProductUpdate`, etc.) dans sa méthode `install()` principale. Son intégration se fait via le `AdminController` et l'interaction directe avec la base de données pour la journalisation.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Points de fidélité – Aperçu client et gestion des points », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
