---
title: "Expertise Clients - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Expertise Clients par MyPresta.eu."
sidebar:
  label: "Expertise Clients - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Customers Expertise sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/customers-expertise.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/customers-expertise/)
>
> ---


# Expertise Clients

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont habituellement présentes sur tout environnement d'hébergement moderne. Aucune exigence d'hébergement spéciale au-delà d'une configuration PrestaShop standard.

## 2. Présentation complète de la configuration (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Expertise Clients)

C'est l'écran de configuration principal où vous définissez vos réalisations, leurs critères et les récompenses. La configuration du module est gérée via une interface dédiée qui vous permet d'ajouter, de modifier et de supprimer des réalisations.

**Nom de l'écran et emplacement du menu :**
Vous pouvez accéder à cet écran en naviguant vers **Modules > Gestionnaire de modules**, en recherchant « Expertise Clients » et en cliquant sur le bouton « Configurer ».

**Actions et paramètres disponibles :**
La page de configuration présentera une liste de vos réalisations actuellement définies. Vous trouverez généralement des options pour :

- **Ajouter une nouvelle réalisation :** Un bouton ou un lien pour créer une nouvelle réalisation.
- **Modifier une réalisation existante :** Une icône (par exemple, un crayon) à côté de chaque réalisation dans la liste pour modifier ses paramètres.
- **Supprimer une réalisation :** Une icône (par exemple, une corbeille) à côté de chaque réalisation pour la supprimer.

Lors de l'ajout ou de la modification d'une réalisation, vous rencontrerez généralement les paramètres suivants :

#### **Détails de la réalisation**

- **Nom de la réalisation :**

  - **Ce que fait ce paramètre :** C'est le titre de la réalisation que vos clients verront (par exemple, « Premier Acheteur », « Maître des Avis », « Acheteur VIP »).
  - **Effet de la modification de ce paramètre :** Ce nom est affiché dans la section « Mes réalisations » du client. Un nom clair et attrayant encourage l'engagement.
  - **Valeur recommandée :** Quelque chose de descriptif et de motivant.
  - **Scénario / exemple marchand :** « Héros de la première commande » pour le premier achat d'un client.
- **Description de la réalisation :**

  - **Ce que fait ce paramètre :** Une brève explication de ce qu'est la réalisation et comment l'obtenir. Cela aide les clients à comprendre l'objectif.
  - **Effet de la modification de ce paramètre :** Cette description apparaît à côté du nom. Une bonne description clarifie les critères de la réalisation.
  - **Valeur recommandée :** Concise et encourageante.
  - **Scénario / exemple marchand :** « Effectuez votre tout premier achat dans notre boutique pour gagner ce badge ! »
- **Image/Icône de la réalisation :**

  - **Ce que fait ce paramètre :** Vous permet de télécharger une représentation visuelle (badge, icône) pour la réalisation.
  - **Effet de la modification de ce paramètre :** Cette image est affichée à côté du nom de la réalisation, la rendant visuellement attrayante et reconnaissable.
  - **Valeur recommandée :** Une image unique et de haute qualité qui reflète le thème de la réalisation.
  - **Scénario / exemple marchand :** Une icône « étoile » pour une réalisation « Meilleur évaluateur ».
- **Actif / Activé :**

  - **Ce que fait ce paramètre :** Un interrupteur pour activer ou désactiver la réalisation.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* La réalisation est active, les clients peuvent l'obtenir et elle apparaîtra dans leur liste de réalisations.
    - *Lorsqu'il est désactivé :* La réalisation est masquée, les clients ne peuvent pas l'obtenir et elle n'apparaîtra pas dans le front-office. Utile pour les réalisations saisonnières ou celles que vous êtes encore en train de préparer.
  - **Valeur recommandée :** OUI pour les réalisations actives.
  - **Scénario / exemple marchand :** Désactiver une réalisation « Acheteur de Noël » après la saison des fêtes.

#### **Critères de réalisation (Comment l'obtenir)**

C'est le cœur du module, où vous définissez les conditions qu'un client doit remplir. Le module offre probablement différents types de critères. Les exemples courants incluent :

- **Nombre de commandes :**

  - **Ce que fait ce paramètre :** Le client doit passer un nombre spécifié de commandes.
  - **Effet de la modification de ce paramètre :** Détermine le nombre de commandes réussies requises.
  - **Valeur recommandée :** Commencez par de petits nombres pour les réalisations initiales (par exemple, 1, 3) et augmentez pour les niveaux supérieurs.
  - **Scénario / exemple marchand :** Définir à « 1 » pour « Premier acheteur », « 5 » pour « Client fidèle ».
- **Montant total dépensé :**

  - **Ce que fait ce paramètre :** Les dépenses cumulées du client sur toutes les commandes doivent atteindre un certain montant.
  - **Effet de la modification de ce paramètre :** Définit le seuil monétaire.
  - **Valeur recommandée :** Adaptez-le à votre valeur de commande moyenne et à vos segments de clientèle.
  - **Scénario / exemple marchand :** Définir à « 100 € » pour « Dépensier Bronze », « 500 € » pour « Dépensier Argent ».
- **Nombre de produits achetés :**

  - **Ce que fait ce paramètre :** Le client doit acheter une quantité totale spécifique de produits (sur toutes les commandes).
  - **Effet de la modification de ce paramètre :** Définit le seuil de quantité.
  - **Valeur recommandée :** Utile pour encourager les achats en gros ou l'essai de différents produits.
  - **Scénario / exemple marchand :** Définir à « 10 » pour « Collectionneur de produits ».
- **Nombre d'avis produits :**

  - **Ce que fait ce paramètre :** Le client doit soumettre un certain nombre d'avis produits approuvés.
  - **Effet de la modification de ce paramètre :** Encourage le contenu généré par les utilisateurs et la preuve sociale.
  - **Valeur recommandée :** Définir à « 1 » pour « Premier évaluateur », « 5 » pour « Maître des avis ».
  - **Scénario / exemple marchand :** Récompenser les clients pour leur contribution précieuse.
- **Achat de produit/catégorie spécifique :**

  - **Ce que fait ce paramètre :** Le client doit acheter un produit d'une catégorie spécifique ou un produit spécifique lui-même.
  - **Effet de la modification de ce paramètre :** Propose des articles ou des catégories spécifiques.
  - **Valeur recommandée :** Utiliser pour les lancements de nouveaux produits ou les stocks à faible rotation.
  - **Scénario / exemple marchand :** « A acheté un article de la nouvelle collection » pour un achat dans une catégorie « Nouveautés ».

#### **Récompense de réalisation (Bon de réduction)**

- **Type de bon :**

  - **Ce que fait ce paramètre :** Définit le type de code de réduction que le client reçoit (par exemple, pourcentage, montant fixe, livraison gratuite).
  - **Effet de la modification de ce paramètre :** Détermine la nature de la récompense.
  - **Valeur recommandée :** Les réductions en pourcentage sont souvent populaires, mais les montants fixes peuvent être bons pour les petits achats.
  - **Scénario / exemple marchand :** « Réduction en pourcentage » pour 10 % de réduction sur la prochaine commande.
- **Valeur du bon :**

  - **Ce que fait ce paramètre :** La valeur réelle de la réduction (par exemple, « 10 » pour 10 %, « 5 € » pour un montant fixe).
  - **Effet de la modification de ce paramètre :** Impacte directement l'incitation pour le client.
  - **Valeur recommandée :** Équilibrez la générosité avec vos marges bénéficiaires.
  - **Scénario / exemple marchand :** « 15 » pour une réduction de 15 %.
- **Période de validité du bon (Jours) :**

  - **Ce que fait ce paramètre :** Combien de jours le bon généré est valide à partir du moment où le client le réclame.
  - **Effet de la modification de ce paramètre :** Crée une urgence pour le client d'utiliser le bon.
  - **Valeur recommandée :** 7 à 30 jours est courant. Trop court peut frustrer, trop long réduit l'urgence.
  - **Scénario / exemple marchand :** Définir à « 14 » jours pour encourager un achat répété rapide.
- **Montant minimum de commande pour le bon :**

  - **Ce que fait ce paramètre :** Si le bon nécessite une valeur d'achat minimale pour être utilisé.
  - **Effet de la modification de ce paramètre :** Aide à protéger vos marges et encourage les clients à dépenser plus.
  - **Valeur recommandée :** Définissez un minimum raisonnable qui encourage une vente incitative sans être prohibitif.
  - **Scénario / exemple marchand :** « 30 € » de commande minimum pour une réduction de 5 €.
- **Préfixe du bon :**

  - **Ce que fait ce paramètre :** Un préfixe personnalisé pour les codes de réduction générés (par exemple, « REALISATION- », « BADGE- »).
  - **Effet de la modification de ce paramètre :** Vous aide à identifier la source des codes de réduction dans vos rapports de vente PrestaShop.
  - **Valeur recommandée :** Un préfixe court et mémorable.
  - **Scénario / exemple marchand :** « EXPERT- » pour savoir que le bon provient du module Expertise Clients.

**Flux de travail recommandé pour la gestion quotidienne de la boutique :**

1. **Planifiez vos réalisations :** Avant de créer, décidez quels comportements vous souhaitez récompenser et combien de niveaux de réalisations vous souhaitez.
2. **Commencez simple :** Commencez par 2-3 réalisations de base (par exemple, première commande, total dépensé, nombre d'avis) pour tester le terrain.
3. **Créez chaque réalisation :** Parcourez le processus « Ajouter une nouvelle réalisation », en définissant soigneusement les critères et les récompenses.
4. **Surveillez l'engagement client :** Vérifiez vos ventes et vos comptes clients pour voir comment les clients interagissent avec les réalisations.
5. **Ajustez et développez :** En fonction des performances, affinez les réalisations existantes ou introduisez de nouvelles réalisations plus complexes.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Nom de la réalisation | Descriptif | Titre affiché au client. |
| | Description de la réalisation | Informative | Explique comment obtenir la réalisation. |
| | Image/Icône de la réalisation | Image unique | Représentation visuelle du badge. |
| | Actif / Activé | OUI | Active/désactive la visibilité et l'éligibilité de la réalisation. |
| | **Critères : Nombre de commandes** | 1, 3, 5 | Le client doit passer X commandes. |
| | **Critères : Montant total dépensé** | 50 €, 100 €, 500 € | Les dépenses totales du client doivent atteindre X. |
| | **Critères : Nombre de produits achetés** | 5, 10, 20 | Le client doit acheter X produits au total. |
| | **Critères : Nombre d'avis produits** | 1, 3, 5 | Le client doit soumettre X avis approuvés. |
| | **Critères : Achat de produit/catégorie spécifique** | (Sélectionner produit/catégorie) | Le client doit acheter un produit d'une catégorie spécifique. |
| | **Récompense : Type de bon** | Pourcentage | Type de réduction (%, fixe, livraison gratuite). |
| | **Récompense : Valeur du bon** | 10 (pour %) | Le montant de la réduction. |
| | **Récompense : Période de validité du bon (Jours)** | 14-30 | Durée de validité du bon après réclamation. |
| | **Récompense : Montant minimum de commande pour le bon** | (Optionnel) | Valeur minimale du panier requise pour utiliser le bon. |
| | **Récompense : Préfixe du bon** | EXPERT- | Préfixe personnalisé pour les codes de réduction générés. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : Mes clients ne voient pas la section des réalisations dans leur compte.**
R : Tout d'abord, assurez-vous que le module « Expertise Clients » est installé et activé dans votre Back Office. Vérifiez la configuration du module pour vous assurer que vous avez au moins une réalisation créée et définie comme « Active ». Vérifiez également que le fichier `customer-account.tpl` de votre thème (ou équivalent) est correctement accroché pour afficher le lien du module. Si vous avez un thème personnalisé, vous pourriez avoir besoin d'un webmaster pour vous assurer que le hook est rendu.

**Q : Les clients obtiennent des réalisations mais ne reçoivent pas de codes de réduction.**
R : Allez dans la configuration du module et modifiez la réalisation spécifique. Vérifiez que le « Type de bon » et la « Valeur du bon » sont correctement définis pour la récompense. Assurez-vous qu'il n'y a pas de fautes de frappe ou de paramètres incorrects dans les paramètres du bon. Vérifiez également vos « Règles panier » (ou « Réductions » dans les anciennes versions) de PrestaShop pour voir si les bons générés y apparaissent.

**Q : Les images des réalisations ne s'affichent pas correctement.**
R : Cela indique généralement un problème avec le téléchargement de l'image ou les permissions de fichier. Assurez-vous que le fichier image que vous avez téléchargé est un format web standard (JPG, PNG, GIF) et qu'il n'est pas trop volumineux. Vérifiez les permissions de fichier de votre serveur pour le répertoire d'images du module (par exemple, `modules/customersexpertise/img/`) pour vous assurer que PrestaShop peut y écrire et lire des fichiers. Vider votre cache PrestaShop (Paramètres avancés > Performances) peut également aider.

**Q : Puis-je traduire les noms et descriptions des réalisations dans plusieurs langues ?**
R : Oui, comme la plupart des modules PrestaShop, les champs de texte pour les noms et descriptions des réalisations devraient prendre en charge la saisie multilingue. Lors de la modification d'une réalisation, recherchez les drapeaux de langue à côté des champs de saisie, vous permettant de fournir des traductions pour chaque langue installée dans votre boutique.

**Q : Que se passe-t-il si un client obtient une réalisation mais que je la désactive plus tard ?**
R : Si une réalisation est désactivée, les nouveaux clients ne pourront plus l'obtenir, et elle sera généralement masquée du front-office. Les clients qui l'ont déjà obtenue conserveront généralement leur statut acquis et tous les bons associés qu'ils ont réclamés avant que la réalisation ne soit désactivée. Cependant, ils ne pourront pas réclamer de bons si la réalisation est réactivée et qu'ils en ont déjà un.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module Expertise Clients.

### 4.1 Vue d'ensemble de l'architecture

Le module Expertise Clients suit une architecture de module PrestaShop standard, exploitant principalement les contrôleurs frontaux pour les interactions côté client et la classe de module principale pour la configuration et la gestion des hooks. Il intègre la logique de gamification en suivant les actions des clients (commandes, avis) et en générant dynamiquement des objets `CartRule` (bon d'achat) de PrestaShop comme récompenses. La logique principale du module réside dans son fichier PHP principal et ses contrôleurs frontaux dédiés, avec des templates Smarty gérant la couche de présentation.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs gèrent la logique côté client et l'affichage des réalisations et des fonctionnalités associées.

- `controllers/front/achievements.php`

  - **Nom de la classe et classe parente :** `CustomersExpertiseAchievementsModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** C'est le contrôleur principal pour afficher les réalisations d'un client. Il récupère toutes les réalisations définies, vérifie l'éligibilité et le statut acquis du client actuel pour chacune, et prépare les données pour le template `achievements.tpl`. Il gère probablement la logique de réclamation des bons une fois qu'une réalisation est obtenue.
  - **Routes :** Généralement accessible via une URL comme `votreboutique.com/module/customersexpertise/achievements`.
- `controllers/front/affiliationlink.php`

  - **Nom de la classe et classe parente :** `CustomersExpertiseAffiliationlinkModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Bien que la description du module ne mentionne pas explicitement l'affiliation, ce contrôleur suggère une fonctionnalité potentielle permettant aux clients de générer et de gérer des liens d'affiliation, éventuellement comme récompense de réalisation ou comme fonctionnalité autonome. Il gérerait l'affichage et la génération de ces liens.
  - **Routes :** Probablement `votreboutique.com/module/customersexpertise/affiliationlink`.
- `controllers/front/index.php`

  - **Nom de la classe et classe parente :** `CustomersExpertiseIndexModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Sert souvent de contrôleur frontal par défaut ou de secours. Il pourrait rediriger vers le contrôleur `achievements` ou afficher une page d'accueil générale pour le module si aucune action spécifique n'est demandée.
  - **Routes :** `votreboutique.com/module/customersexpertise/index` ou `votreboutique.com/module/customersexpertise`.
- `controllers/front/voucher.php`

  - **Nom de la classe et classe parente :** `CustomersExpertiseVoucherModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur est probablement responsable du processus réel de génération et d'attribution d'un bon de réduction à un client une fois qu'il a réclamé une réalisation obtenue. Il interagirait avec l'objet `CartRule` de PrestaShop pour créer le bon et potentiellement mettre à jour le statut de réalisation du client.
  - **Routes :** Pourrait être un point d'API AJAX ou une URL directe pour la réclamation de bons, par exemple, `votreboutique.com/module/customersexpertise/voucher`.

#### Contrôleurs d'administration Back-Office

Le module ne semble pas avoir de contrôleurs d'administration personnalisés dédiés. La configuration est gérée via la méthode `getContent()` de la classe de module principale.

### 4.3 Classes et modèles principaux (`classes/`)

L'inventaire fourni n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que la logique principale du module, les définitions de réalisations et le suivi des clients sont probablement gérés directement dans le fichier de module principal (`ajax_customersexpertise.php`) et potentiellement en exploitant les classes `ObjectModel` existantes de PrestaShop comme `Customer`, `Order`, `Product` et `CartRule`.

Le module gérerait en interne les données de réalisation, éventuellement par :

- Stockage des définitions de réalisations (nom, description, critères, récompense) dans la table `ps_configuration` sous forme de tableaux sérialisés ou de JSON.
- Stockage du statut de réalisation du client (obtenu, bon réclamé) dans une table personnalisée créée lors de l'installation ou également dans les champs méta de `ps_configuration` ou `ps_customer`.

### 4.4 Actifs JavaScript (`views/js/`)

- `customersexpertise/lib/voucherengine/script.js`
  - **Portée :** Probablement Front-office.
  - **Détails :** Ce script est probablement responsable de l'amélioration de l'expérience utilisateur sur la page des réalisations du client. Il pourrait gérer :
    - Les requêtes AJAX pour réclamer des bons (par exemple, lorsqu'un client clique sur un bouton « Réclamer le bon »).
    - Les mises à jour dynamiques de la page après la réclamation d'un bon (par exemple, affichage du code du bon, marquage de la réalisation comme réclamée).
    - La validation côté client ou les éléments interactifs liés aux fonctionnalités de gamification.
    - Potentiellement, il pourrait interagir avec le contrôleur frontal `voucher.php`.

### 4.5 Feuilles de style CSS (`views/css/`)

- `customersexpertise/css/customersexpertise.css`

  - **Portée :** Style client Front-office.
  - **Détails :** C'est la feuille de style principale pour les composants front-office du module. Elle définit l'apparence visuelle de la liste des réalisations, des cartes de réalisations individuelles, de l'affichage des bons et de tout autre élément d'interface utilisateur présenté au client.
  - **Sélecteurs de classe CSS clés :** Les développeurs peuvent s'attendre à des classes comme `.customersexpertise-achievements`, `.achievement-item`, `.achievement-badge`, `.voucher-code`, etc., qui peuvent être remplacées dans le `custom.css` ou `theme.css` d'un thème personnalisé pour correspondre à l'image de marque de la boutique.
- `customersexpertise/lib/voucherengine/ps16.css`

  - **Portée :** Style client Front-office, spécifiquement pour la compatibilité PrestaShop 1.6.
  - **Détails :** Cette feuille de style contient probablement des remplacements spécifiques ou des styles supplémentaires pour garantir que l'affichage front-office du module est correct et visuellement cohérent avec les thèmes PrestaShop 1.6. Elle pourrait aborder les différences de mise en page ou le style d'éléments spécifiques qui ont changé entre les versions de PrestaShop. Pour les versions plus récentes de PrestaShop (1.7, 8.x, 9.x), ce fichier pourrait être chargé conditionnellement ou ses styles pourraient être moins pertinents, s'appuyant davantage sur `customersexpertise.css`.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates Front-office (`views/templates/front/`)** :

  - `customersexpertise/views/templates/front/achievements.tpl`
    - **Objectif :** C'est le template principal pour afficher la page des réalisations du client. Il itère sur les données des réalisations passées par le contrôleur `achievements.php`, affichant les badges obtenus, les critères pour ceux non obtenus, et les options pour réclamer des bons.
  - `customersexpertise/views/templates/front/affiliation-link.tpl`
    - **Objectif :** Si le contrôleur `affiliationlink.php` est actif, ce template rendrait l'interface permettant aux clients de visualiser ou de générer leurs liens d'affiliation.
  - `customersexpertise/views/templates/front/voucher.tpl`
    - **Objectif :** Ce template pourrait être utilisé pour afficher un seul code de bon ou un message de confirmation après qu'un bon a été réclamé, potentiellement dans le cadre d'une réponse AJAX ou d'une page dédiée.
- **Templates de hook (`views/templates/hook/`)** :

  - `customersexpertise/views/templates/hook/customer-account.tpl`
    - **Hook :** `displayCustomerAccount` (ou similaire, selon la version de PrestaShop).
    - **Objectif :** Ce template rend le lien ou le bloc qui apparaît dans le tableau de bord « Mon compte » du client, le dirigeant vers la page « Mes réalisations ». Il est crucial pour la découverte des fonctionnalités du module par le client.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :
  La description du module et l'inventaire des fichiers ne listent pas explicitement de fichiers SQL personnalisés pour la création de tables. Cela suggère que le module pourrait stocker ses données de l'une des manières suivantes :

  - **`ps_configuration`** : Les définitions de réalisations (critères, récompenses) pourraient être stockées sous forme de tableaux sérialisés ou de chaînes JSON dans la table `ps_configuration`, en utilisant des clés de configuration uniques (par exemple, `CUSTOMERS_EXPERTISE_ACHIEVEMENTS`).
  - **Tables PrestaShop existantes** : Le statut de réalisation du client (quelles réalisations il a obtenues, quels bons il a réclamés) pourrait être stocké dans un champ personnalisé ajouté aux tables `ps_customer` ou `ps_customer_group`, ou dans une table personnalisée créée dynamiquement par la méthode `install()` du module sans fichier `.sql` dédié.
  - **`ps_cart_rule`** : Le module interagit directement avec le système `CartRule` (bon de réduction) de PrestaShop pour générer des récompenses.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de toutes les pages du front-office. | Pour inclure des actifs CSS et JavaScript globalement, ou pour ajouter des balises meta. |
| `displayLeftColumn` / `displayRightColumn` | Dans la colonne gauche/droite des pages du front-office. | Pour afficher un petit bloc promotionnel ou un lien vers la page des réalisations. |
| `displayProductButtons` / `displayProductExtraContent` (ou hooks similaires de page produit) | Sur la page produit. | Potentiellement pour suivre les vues/achats de produits pour les critères de réalisation, ou pour suggérer la gamification. |
| `displayFooter` | Dans le pied de page de toutes les pages du front-office. | Pour afficher un lien vers la page des réalisations ou une promotion générale de gamification. |
| `displayCustomerAccount` | Dans le tableau de bord « Mon compte » du client. | **CRITIQUE :** Pour ajouter le lien « Mes réalisations » pour les clients. |
| `actionValidateOrder` | Après qu'une commande client a été validée avec succès. | **CRITIQUE :** Pour vérifier si la commande remplit des critères de réalisation (par exemple, première commande, total dépensé, achat de produit) et attribuer des réalisations. |
| `actionObjectProductAddAfter` / `actionObjectProductUpdateAfter` | Après l'ajout ou la mise à jour d'un produit. | Moins probable, mais pourrait être utilisé pour mettre à jour les critères de réalisation s'ils sont liés aux attributs du produit. |
| `actionObjectCustomerAddAfter` | Après l'inscription d'un nouveau client. | Pour initialiser le suivi des réalisations pour les nouveaux clients. |
| `actionObjectReviewAddAfter` (ou similaire pour les modules d'avis) | Après qu'un client a soumis un avis produit. | **CRITIQUE :** Pour vérifier si l'avis remplit des critères de réalisation (par exemple, nombre d'avis). |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module Expertise Clients, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à assurer le fonctionnement optimal du module avec votre boutique PrestaShop.
"""
