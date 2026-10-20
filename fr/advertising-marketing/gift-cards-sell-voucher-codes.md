---
title: "Cartes Cadeaux - vendre des codes de bon d'achat - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Cartes Cadeaux - vendre des codes de bon d'achat par MyPresta.eu."
sidebar:
  label: "Cartes Cadeaux - vendre des codes de bon d'achat - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Gift Cards - sell voucher codes sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/gift-cards-sell-voucher-codes.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/gift-cards-sell-voucher-codes/)
>
> ---


# Cartes Cadeaux - vendre des codes de bon d'achat

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises, qui sont généralement disponibles sur la plupart des environnements d'hébergement web modernes.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

Le module « Cartes Cadeaux - vendre des codes de bon d'achat » offre plusieurs écrans de configuration pour gérer efficacement vos cartes cadeaux.

### 2.1 Page de configuration principale du module (Back Office > Modules > Gestionnaire de modules > Configurer Cartes Cadeaux - vendre des codes de bon d'achat)

C'est l'écran de configuration principal du module, où vous définissez le comportement général et accédez à d'autres sections de gestion.

- **Ce que fait ce paramètre :** Cette section contient généralement les paramètres globaux du module, tels que l'activation/désactivation des fonctionnalités, les liens vers d'autres écrans de gestion et potentiellement la définition des comportements par défaut pour les cartes cadeaux.
- **Effet de la modification de ce paramètre :** Les modifications ici affecteront la façon dont les cartes cadeaux sont affichées, achetées et gérées dans l'ensemble de votre boutique.
- **Valeur recommandée :** Examinez attentivement chaque option. En général, activez les fonctionnalités que vous avez l'intention d'utiliser et suivez les recommandations par défaut du module, sauf si vous avez une raison spécifique de les modifier.
- **Scénario / exemple de marchand :** Vous pourriez trouver un paramètre ici pour activer un lien dédié « Cartes Cadeaux » dans le pied de page de votre boutique. L'activation de cette option faciliterait la recherche et l'achat de cartes cadeaux par les clients.

### 2.2 Gestion des groupes de cartes cadeaux (Back Office > Cartes Cadeaux > Groupes de cartes cadeaux)

Cet écran vous permet de définir différentes catégories ou groupes pour vos cartes cadeaux. Considérez-les comme des modèles ou des types de cartes cadeaux que vous souhaitez offrir.

- **Nom de l'écran et emplacement du menu :** **Back Office > Cartes Cadeaux > Groupes de cartes cadeaux**
- **Actions et paramètres disponibles :**
  - **Tableau de liste :** Affiche tous les groupes de cartes cadeaux existants. Vous verrez des colonnes comme Nom du groupe, Valeur, Statut (actif/inactif) et actions (Modifier, Supprimer).
  - **Ajouter un nouveau groupe de cartes cadeaux :** Cliquez sur ce bouton pour créer un nouveau type de carte cadeau.
    - **Nom du groupe :** (par exemple, « Carte Cadeau Anniversaire », « Bon de Noël », « Carte Cadeau Toute Occasion »)
      - *Ce que fait ce paramètre :* C'est le nom interne de votre groupe de cartes cadeaux. Il vous aide à organiser et à identifier différents types de cartes cadeaux dans le back office.
      - *Effet de la modification de ce paramètre :* Affecte uniquement l'organisation de votre back office.
      - *Valeur recommandée :* Descriptif et clair.
    - **Valeur :** (par exemple, « 25.00 », « 50.00 », « 100.00 »)
      - *Ce que fait ce paramètre :* Cela définit la valeur monétaire de la carte cadeau dans ce groupe.
      - *Effet de la modification de ce paramètre :* C'est le montant que les clients paieront et que les destinataires recevront comme crédit.
      - *Valeur recommandée :* Dénominations courantes et attrayantes pour votre marché cible.
    - **Actif :** (Interrupteur Oui/Non)
      - *Ce que fait ce paramètre :* Contrôle si les cartes cadeaux de ce groupe sont disponibles à l'achat dans votre boutique.
      - *Effet de la modification de ce paramètre :*
        - *Lorsqu'activé :* Les clients peuvent voir et acheter des cartes cadeaux de cette valeur.
        - *Lorsqu'désactivé :* Les cartes cadeaux de cette valeur sont masquées du front office et ne peuvent pas être achetées.
      - *Valeur recommandée :* OUI pour les cartes cadeaux actives que vous souhaitez vendre.
    - **Autres champs :** Peuvent inclure des options pour la période de validité, le montant minimum d'achat pour l'utilisation ou des restrictions de produits spécifiques.
      - *Ce que fait ce paramètre :* Ces champs vous permettent d'affiner les conditions dans lesquelles la carte cadeau peut être utilisée.
      - *Effet de la modification de ce paramètre :* Impacte directement l'utilisabilité et les restrictions de la carte cadeau pour le destinataire.
      - *Valeur recommandée :* Définir selon votre politique commerciale (par exemple, validité d'un an, pas d'achat minimum).
- **Effet des modifications :** La création de nouveaux groupes vous permet d'offrir diverses dénominations de cartes cadeaux. La modification de groupes change la valeur ou la disponibilité des types de cartes cadeaux existants. La suppression d'un groupe supprime l'option d'acheter ce type de carte cadeau spécifique.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Commencez par créer quelques valeurs de cartes cadeaux courantes (par exemple, 25 €, 50 €, 100 €).
  2. Au fur et à mesure que votre entreprise se développe ou pour des promotions saisonnières, ajoutez de nouveaux groupes avec des valeurs différentes ou des périodes de validité spécifiques.
  3. Désactivez les groupes que vous ne souhaitez plus vendre, plutôt que de les supprimer, afin de préserver les données historiques.

### 2.3 Historique des cartes cadeaux (Back Office > Cartes Cadeaux > Historique des cartes cadeaux)

Cet écran offre un aperçu complet de toutes les cartes cadeaux qui ont été achetées et de leur statut actuel.

- **Nom de l'écran et emplacement du menu :** **Back Office > Cartes Cadeaux > Historique des cartes cadeaux**
- **Actions et paramètres disponibles :**
  - **Tableau de liste :** Affiche une liste de tous les bons cadeaux générés. Les colonnes incluent généralement :
    - **Code du bon :** Le code unique associé à la carte cadeau.
    - **Valeur originale :** La valeur initiale de la carte cadeau.
    - **Solde actuel :** Le solde restant sur la carte cadeau (si partiellement utilisée).
    - **E-mail du destinataire :** L'adresse e-mail de la personne qui a reçu la carte cadeau.
    - **Nom de l'expéditeur :** Le nom de la personne qui a acheté la carte cadeau.
    - **ID de commande :** L'ID de la commande par laquelle la carte cadeau a été achetée.
    - **Statut :** (par exemple, « En attente », « Actif », « Utilisé », « Expiré »).
    - **Actions :** Peut inclure des options pour afficher les détails de la commande, renvoyer l'e-mail de la carte cadeau ou ajuster manuellement le solde (à utiliser avec prudence).
  - **Recherche et filtre :** Outils pour trouver des cartes cadeaux spécifiques par code, e-mail, ID de commande ou statut.
- **Effet des modifications :** Cet écran est principalement destiné à la surveillance et à la gestion. Vous pouvez suivre l'utilisation des cartes cadeaux, identifier les soldes impayés et aider les clients avec leurs demandes de cartes cadeaux.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Vérifiez régulièrement cette section pour surveiller les ventes et l'utilisation des cartes cadeaux.
  2. Utilisez la fonction de recherche pour trouver rapidement une carte cadeau si un client a une question sur son solde ou son statut.
  3. Si un client signale ne pas avoir reçu son e-mail de carte cadeau, vous pouvez vérifier son statut et potentiellement le renvoyer à partir d'ici.

### 2.4 Gestion des bons de cartes cadeaux (Back Office > Cartes Cadeaux > Bons de cartes cadeaux)

Cet écran est dédié à la gestion des codes de bon d'achat individuels générés pour chaque achat de carte cadeau.

- **Nom de l'écran et emplacement du menu :** **Back Office > Cartes Cadeaux > Bons de cartes cadeaux**
- **Actions et paramètres disponibles :**
  - **Tableau de liste :** Affiche les codes de bon d'achat individuels. Les colonnes peuvent inclure :
    - **Code du bon :** Le code unique.
    - **Groupe de cartes cadeaux associé :** À quel type de carte cadeau ce bon appartient.
    - **Valeur :** La valeur de ce bon spécifique.
    - **Client :** Le client associé au bon (expéditeur ou destinataire).
    - **Date d'ajout/génération :** Quand le bon a été créé.
    - **Statut :** (par exemple, « Actif », « Utilisé », « Expiré »).
    - **Actions :** Options pour afficher les détails, modifier (par exemple, changer le statut, prolonger la validité) ou supprimer (à utiliser avec une extrême prudence car cela supprime le bon).
- **Effet des modifications :** Cet écran permet un contrôle granulaire sur les bons de cartes cadeaux individuels. Vous pouvez activer/désactiver manuellement les bons, prolonger leur validité, ou même modifier leur valeur si nécessaire (par exemple, pour des problèmes de service client).
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Utilisez cet écran pour les tâches de gestion avancées, telles que l'émission manuelle d'une carte cadeau en guise de geste commercial ou la résolution de problèmes clients spécifiques liés à un bon.
  2. Soyez prudent lors de la modification ou de la suppression de bons, car cela a un impact direct sur le crédit client.
  3. Cet écran offre une vue détaillée du cycle de vie de chaque bon.

### 2.5 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | *Paramètres généraux* | Variable | Comportement global du module, options d'affichage et liens vers d'autres zones de gestion. |
| **Groupes de cartes cadeaux** | **Nom du groupe** | Descriptif | Nom interne du type de carte cadeau. |
| | **Valeur** | Dénominations courantes (par exemple, 25 €, 50 €) | Valeur monétaire de la carte cadeau. |
| | **Actif** | OUI | Contrôle la visibilité et la possibilité d'achat du type de carte cadeau. |
| | *Période de validité* | Selon la politique | Définit la durée de validité de la carte cadeau après l'achat. |
| | *Achat min. pour utilisation* | Selon la politique | Définit une valeur de commande minimale pour que la carte cadeau puisse être utilisée. |
| **Historique des cartes cadeaux** | *Code du bon* | N/A | Identifiant unique pour chaque carte cadeau achetée. |
| | *Solde actuel* | N/A | Crédit restant sur la carte cadeau. |
| | *Statut* | N/A | Suivi du cycle de vie de la carte cadeau (Active, Utilisée, Expirée). |
| **Bons de cartes cadeaux** | *Code du bon* | N/A | Identifiant unique pour chaque bon généré. |
| | *Statut* | N/A | Suivi de l'état du bon individuel. |
| | *Actions Modifier/Supprimer* | À utiliser avec prudence | Permet la modification ou la suppression manuelle de bons individuels. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes clients ne trouvent pas les cartes cadeaux dans ma boutique.**

- **R :** Tout d'abord, assurez-vous que les « Groupes de cartes cadeaux » que vous avez créés sont marqués comme « Actifs » dans le Back Office sous **Cartes Cadeaux > Groupes de cartes cadeaux**. Deuxièmement, vérifiez la page de configuration principale de votre module (Modules > Gestionnaire de modules > Configurer Cartes Cadeaux - vendre des codes de bon d'achat) pour les options d'affichage des liens dans l'en-tête, le pied de page ou les colonnes. Si votre thème a une gestion de menu personnalisée, vous devrez peut-être ajouter manuellement un lien vers la page des cartes cadeaux (généralement accessible via une URL conviviale comme `votreboutique.com/cadeaux`).

**Q2 : Un client a acheté une carte cadeau, mais le destinataire n'a pas reçu l'e-mail.**

- **R :** Allez dans **Cartes Cadeaux > Historique des cartes cadeaux** dans votre Back Office. Trouvez la carte cadeau spécifique par ID de commande ou e-mail de l'expéditeur/destinataire. Vérifiez son statut – il doit être « Actif » ou « En attente » si elle n'a pas encore été utilisée. Cherchez une option pour « Renvoyer l'e-mail » pour ce bon spécifique. De plus, conseillez au client de vérifier son dossier de courrier indésirable/spam. Assurez-vous que les paramètres d'e-mail de votre boutique (Paramètres avancés > E-mail) sont correctement configurés et que votre serveur peut envoyer des e-mails de manière fiable.

**Q3 : La réduction de la carte cadeau ne s'applique pas à la commande.**

- **R :** Vérifiez les points suivants :
  1. **Saisie du code :** Assurez-vous que le client saisit le code de carte cadeau correct et complet, sans fautes de frappe ni espaces supplémentaires.
  2. **Validité :** Vérifiez le statut de la carte cadeau dans **Cartes Cadeaux > Historique des cartes cadeaux** ou **Cartes Cadeaux > Bons de cartes cadeaux**. Est-elle « Active » ? A-t-elle expiré ? Y a-t-il un solde restant ?
  3. **Achat minimum :** La carte cadeau a-t-elle une exigence d'achat minimum que le total du panier actuel ne satisfait pas ?
  4. **Restrictions de produits :** Y a-t-il des catégories de produits ou des produits spécifiques exclus de l'utilisation de la carte cadeau ? (Ceci serait configuré dans les paramètres du Groupe de cartes cadeaux).
  5. **Cache :** Parfois, vider le cache de votre PrestaShop (Paramètres avancés > Performances) peut résoudre les problèmes d'affichage ou de fonctionnalité.

**Q4 : Puis-je personnaliser le modèle d'e-mail pour les cartes cadeaux ?**

- **R :** Oui, le module comprend un gestionnaire de modèles d'e-mail. Vous devriez trouver des options dans la configuration du module ou une section dédiée (par exemple, sous **Cartes Cadeaux > Modèles d'e-mail**) pour modifier le contenu et l'apparence de l'e-mail envoyé aux destinataires des cartes cadeaux. Cela vous permet de personnaliser l'e-mail avec votre marque et d'inclure des instructions ou des messages spécifiques.

**Q5 : Que se passe-t-il si le total de la commande d'un client est inférieur à la valeur de la carte cadeau ?**

- **R :** Le module est conçu pour gérer cela. Si le total de la commande est inférieur à la valeur de la carte cadeau, le solde restant devrait rester sur la carte cadeau, permettant au destinataire de l'utiliser pour de futurs achats jusqu'à ce que le solde soit épuisé ou que la carte expire. Vous pouvez vérifier le solde restant dans la section **Cartes Cadeaux > Historique des cartes cadeaux**.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Cartes Cadeaux - vendre des codes de bon d'achat » suit un modèle MVC (Modèle-Vue-Contrôleur) PrestaShop standard, bien qu'il ne définisse pas explicitement de classes `ObjectModel` personnalisées dans le répertoire `classes/`. Au lieu de cela, il exploite la fonctionnalité de base de `CartRule` (bon d'achat) de PrestaShop et étend les capacités d'administration via des `AdminController`s dédiés pour la gestion des groupes de cartes cadeaux, de l'historique et des bons individuels. L'interaction avec le front-office est gérée par des `ModuleFrontController`s, principalement pour l'affichage des cartes cadeaux et la gestion des comptes utilisateur. Le module s'appuie fortement sur le système de configuration de PrestaShop (`Configuration::get()`) pour ses paramètres et s'intègre à divers hooks pour afficher du contenu et gérer les processus de commande.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `controllers/front/gifts.php`
  - **Nom de la classe et classe parente** : `GiftcertificateGiftsModuleFrontController` étendant `ModuleFrontController`
  - **Responsabilité** : Ce contrôleur est responsable de l'affichage de la page principale des cartes cadeaux dans le front office. Il récupère les groupes de cartes cadeaux disponibles et les rend à l'aide du modèle `gifts.tpl`, permettant aux clients de parcourir et de sélectionner des cartes cadeaux à acheter.
- `controllers/front/index.php`
  - **Nom de la classe et classe parente** : `GiftcertificateIndexModuleFrontController` étendant `ModuleFrontController`
  - **Responsabilité** : Il s'agit d'un contrôleur de remplacement ou de secours, souvent utilisé pour rediriger ou gérer le routage de base du module. Dans de nombreux cas, il peut simplement rediriger vers le contrôleur `gifts.php` ou servir de base pour d'autres actions du front-office.

#### Contrôleurs d'administration Back-Office

- `controllers/admin/AdminGiftcertificateGroupController.php`
  - **Nom de l'onglet et entité gérée** : « Groupes de cartes cadeaux » (sous le menu principal « Cartes Cadeaux »). Gère les entités `gift_group`.
  - **Responsabilité** : Ce contrôleur fournit l'interface pour créer, modifier et supprimer des groupes de cartes cadeaux. Il gère la soumission du formulaire pour définir les valeurs, les noms et d'autres paramètres spécifiques au groupe des cartes cadeaux. Il utilise `HelperList` et `HelperForm` de PrestaShop pour le rendu de la grille et des formulaires.
- `controllers/admin/AdminGiftcertificateHistoryController.php`
  - **Nom de l'onglet et entité gérée** : « Historique des cartes cadeaux » (sous le menu principal « Cartes Cadeaux »). Gère les entités `giftcertlist`.
  - **Responsabilité** : Ce contrôleur affiche un aperçu historique de toutes les cartes cadeaux achetées. Il liste les codes de bon d'achat, les valeurs, les destinataires et les statuts. Il permet aux administrateurs de suivre l'utilisation des cartes cadeaux et potentiellement de renvoyer des e-mails. Il utilise `HelperList` de PrestaShop pour la vue en grille et interagit avec des clés de configuration comme `mowner`, `PS_SHOP_EMAIL`, `PS_SHOP_NAME` pour les actions liées aux e-mails.
- `controllers/admin/AdminGiftcertificateVoucherController.php`
  - **Nom de l'onglet et entité gérée** : « Bons de cartes cadeaux » (sous le menu principal « Cartes Cadeaux »). Gère les entités `gift_voucher`.
  - **Responsabilité** : Ce contrôleur fournit une gestion détaillée des codes de bon d'achat individuels. Il permet aux administrateurs de visualiser, modifier (par exemple, changer le statut, prolonger la validité) ou supprimer des bons spécifiques. Il utilise `HelperList` et `HelperForm` de PrestaShop pour gérer les enregistrements de bons individuels.
- `controllers/admin/index.php`
  - **Nom de l'onglet et entité gérée** : N/A
  - **Responsabilité** : Ce fichier sert généralement de mesure de sécurité pour empêcher la liste ou l'accès direct au répertoire. Il contient généralement un simple `header('Location: ../../../index.php'); exit;` ou similaire pour rediriger vers l'administration principale de PrestaShop.

### 4.3 Classes et modèles de base (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que le module :

1. Manipule directement les tables de la base de données à l'aide de `Db::getInstance()` sans `ObjectModel`s.
2. S'appuie sur la classe `CartRule` (bon d'achat) de base de PrestaShop pour la logique réelle des bons, et ses propres contrôleurs d'administration gèrent l'aspect « carte cadeau » comme un wrapper autour de la création et de la gestion de `CartRule`.
3. Le fichier principal du module (`ajax_giftcertificate.php`) ou ses bibliothèques incluses contiennent la logique de base et la gestion des données.

### 4.4 Actifs JavaScript (`views/js/`)

- `giftcertificate/js/script.js`
  - **Portée** : Probablement Front-office ou fonctionnalité générale du module.
  - **Détails** : Contient du JavaScript général pour le module, gérant potentiellement les requêtes AJAX pour l'ajout de cartes cadeaux au panier, les mises à jour dynamiques sur la page des cartes cadeaux ou les validations de formulaires front-end.
- `giftcertificate/lib/emailTemplatesManager/js/emailTemplatesManager.js`
  - **Portée** : Back-office (Admin).
  - **Détails** : Gère la fonctionnalité d'édition et de création de modèles d'e-mail dans la configuration du module. Cela inclurait la gestion des soumissions de formulaires, les appels AJAX pour l'enregistrement des modèles et potentiellement les intégrations d'éditeurs de texte enrichi.
- `giftcertificate/lib/pdfTemplatesManager/js/pdfTemplatesManager.js`
  - **Portée** : Back-office (Admin).
  - **Détails** : Similaire au gestionnaire de modèles d'e-mail, mais pour les modèles PDF, probablement utilisé pour générer des cartes cadeaux imprimables. Gère les interactions de formulaire, l'enregistrement des conceptions de modèles PDF et la fonctionnalité de prévisualisation.
- `giftcertificate/lib/searchTool/views/js/autocomplete.js`
  - **Portée** : Back-office (Admin).
  - **Détails** : Fournit une fonctionnalité d'autocomplétion pour les champs de recherche dans les contrôleurs d'administration, tels que la recherche de clients ou de produits lors de la création/modification de cartes cadeaux ou de bons.
- `giftcertificate/lib/voucherengine/script.js`
  - **Portée** : Probablement Front-office ou fonctionnalité générale du module.
  - **Détails** : Contient du JavaScript spécifique à la logique de génération et d'utilisation des bons, interagissant potentiellement avec le panier ou le processus de commande pour appliquer les réductions de cartes cadeaux.

### 4.5 Feuilles de style CSS (`views/css/`)

- `giftcertificate/css.css`
  - **Portée** : Générale, pourrait être front-office ou back-office.
  - **Détails** : Contient le style de base pour les éléments du module, y compris potentiellement la mise en page générale, les styles de boutons ou les composants courants.
- `giftcertificate/lib/emailTemplatesManager/css/emailTemplatesManager.css`
  - **Portée** : Back-office (Admin).
  - **Détails** : Styles pour l'interface de gestion des modèles d'e-mail, assurant une apparence cohérente dans le back office de PrestaShop.
- `giftcertificate/lib/pdfTemplatesManager/css/pdfTemplatesManager.css`
  - **Portée** : Back-office (Admin).
  - **Détails** : Styles pour l'interface de gestion des modèles PDF, similaire au gestionnaire de modèles d'e-mail.
- `giftcertificate/lib/searchTool/views/css/autocomplete.css`
  - **Portée** : Back-office (Admin).
  - **Détails** : Style pour les résultats de recherche d'autocomplétion et les champs de saisie.
- `giftcertificate/lib/voucherengine/ps16.css`
  - **Portée** : Front-office (spécifiquement pour les thèmes PrestaShop 1.6).
  - **Détails** : Contient des styles de compatibilité pour les thèmes PrestaShop 1.6, traitant les différences potentielles de mise en page ou d'éléments pour assurer un affichage correct des composants de la carte cadeau.
- `giftcertificate/views/css/giftcertificate.css`
  - **Portée** : Front-office (côté client).
  - **Détails** : Feuille de style principale pour l'affichage des cartes cadeaux dans le front-office, y compris la page dédiée aux cartes cadeaux, les éléments de la page produit et potentiellement le style de la section « Mon Compte ». Les développeurs peuvent remplacer ces classes dans le `custom.css` de leur thème ou dans un thème enfant.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)

- `giftcertificate/views/templates/hook/displayAdminOrder.tpl`
  - **Hook** : `displayAdminOrder`
  - **Sortie** : Rend les informations relatives aux cartes cadeaux dans la page de détail de la commande PrestaShop dans le Back Office. Cela peut afficher quelles cartes cadeaux ont été achetées dans la commande ou quelles cartes cadeaux ont été utilisées pour payer la commande.
- `giftcertificate/views/templates/hook/displayMyAccountBlock.tpl`
  - **Hook** : `displayMyAccountBlock` (PrestaShop 1.6)
  - **Sortie** : Ajoute un lien ou un bloc à la page « Mon Compte » du client, le dirigeant vers ses cartes cadeaux achetées ou son historique de cartes cadeaux.
- `giftcertificate/views/templates/hook/my-account-16.tpl`
  - **Hook** : `displayCustomerAccount` (PrestaShop 1.6)
  - **Sortie** : Modèle spécifique pour ajouter un lien à la page « Mon Compte » pour les thèmes PrestaShop 1.6.
- `giftcertificate/views/templates/hook/my-account-17.tpl`
  - **Hook** : `displayCustomerAccount` (PrestaShop 1.7+)
  - **Sortie** : Modèle spécifique pour ajouter un lien à la page « Mon Compte » pour les thèmes PrestaShop 1.7 et plus récents.
- `giftcertificate/views/templates/hook/my-account.tpl`
  - **Hook** : `displayCustomerAccount` (Général/Fallback)
  - **Sortie** : Un modèle de lien « Mon Compte » général, potentiellement utilisé comme fallback ou pour les versions plus anciennes.

#### Modèles d'administration (`views/templates/admin/`)

- `giftcertificate/views/templates/admin/admin.tpl`
  - **Portée** : Configuration générale de l'administration.
  - **Sortie** : Probablement le formulaire de configuration principal du module, rendu via `getContent()` dans le fichier principal du module. Il peut inclure des onglets ou des sections pour divers paramètres.
- `giftcertificate/views/templates/admin/adminOrder.tpl`
  - **Portée** : Vue de commande de l'administration.
  - **Sortie** : Similaire à `displayAdminOrder.tpl` mais potentiellement pour une vue plus intégrée dans une page de commande d'administration personnalisée, si le module la surcharge ou l'étend.
- `giftcertificate/views/templates/admin/list/list_action_email.tpl`
  - **Portée** : Vues de liste de l'administration (par exemple, Historique des cartes cadeaux).
  - **Sortie** : Un bouton d'action ou un lien spécifique pour l'envoi d'e-mails, généralement trouvé dans la colonne d'action d'un tableau `HelperList`, permettant aux administrateurs de renvoyer des e-mails de cartes cadeaux.

#### Modèles Front-office (`views/templates/front/`)

- `giftcertificate/views/templates/front/gifts.tpl`
  - **Portée** : Page front-office dédiée.
  - **Sortie** : Le modèle principal pour afficher la liste des cartes cadeaux disponibles aux clients, rendu par `GiftcertificateGiftsModuleFrontController`.

#### Modèles de bibliothèque (`lib/`)

- `giftcertificate/lib/emailTemplatesManager/views/*.tpl`
  - **Portée** : Back-office (Admin).
  - **Sortie** : Modèles pour l'interface de gestion des modèles d'e-mail (par exemple, `buttonManager.tpl`, `createTemplateForm.tpl`, `editTemplateForm.tpl`, `mainForm.tpl`, `selectInput.tpl`).
- `giftcertificate/lib/helpers/views/orderStates.tpl`
  - **Portée** : Back-office (Admin).
  - **Sortie** : Un modèle d'aide, probablement pour afficher ou sélectionner des états de commande dans les configurations ou formulaires du module.
- `giftcertificate/lib/pdfTemplatesManager/views/*.tpl`
  - **Portée** : Back-office (Admin).
  - **Sortie** : Modèles pour l'interface de gestion des modèles PDF (par exemple, `buttonManager.tpl`, `createTemplateForm.tpl`, `editTemplateForm.tpl`, `mainForm.tpl`, `selectInput.tpl`).
- `giftcertificate/lib/searchTool/views/scripts.tpl`
  - **Portée** : Back-office (Admin).
  - **Sortie** : Contient du JavaScript ou de la logique Smarty liée à l'outil de recherche, y compris potentiellement des scripts d'initialisation pour l'autocomplétion.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

Le module crée probablement des tables personnalisées pour gérer ses données, bien qu'aucune classe explicite avec des définitions `ObjectModel` n'ait été trouvée. Basé sur les contrôleurs d'administration, les tables suivantes sont implicites :

- `ps_gift_group` : Stocke les définitions des groupes de cartes cadeaux (par exemple, valeur, nom, validité, restrictions).
- `ps_giftcertlist` : Stocke l'historique des cartes cadeaux achetées, y compris leurs codes uniques, leur valeur initiale, leur solde actuel, le destinataire, l'expéditeur et la commande associée.
- `ps_gift_voucher` : Stocke les détails des codes de bon d'achat individuels, potentiellement liés à `ps_cart_rule` s'il exploite le système de bons natif de PrestaShop.

Les enregistrements de configuration stockés dans `ps_configuration` incluraient :

- Les paramètres spécifiques au module configurés via `getContent()`, tels que les ID de modèle d'e-mail, les ID de modèle PDF, les options d'affichage, etc.
- `mowner`, `PS_SHOP_EMAIL`, `PS_SHOP_NAME` sont des configurations PrestaShop de base utilisées par le module pour l'envoi d'e-mails.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Injecter des actifs CSS/JS, des balises meta ou des données spécifiques au module. |
| `displayLeftColumn` / `displayRightColumn` | Dans la colonne gauche/droite du front office. | Afficher un bloc pour la promotion des cartes cadeaux ou un lien vers la page des cartes cadeaux. |
| `displayProductAdditionalInfo` / `displayProductButtons` | Sur la page produit. | Potentiellement afficher un bouton « Acheter une carte cadeau » ou des informations connexes. |
| `displayFooter` | Dans la section du pied de page de chaque page. | Ajouter un lien vers la page des cartes cadeaux. |
| `displayCustomerAccount` | Sur la page « Mon Compte » du client. | Ajouter un lien vers l'historique/les détails des cartes cadeaux du client. |
| `displayMyAccountBlock` | Sur la page « Mon Compte » du client (spécifique à PrestaShop 1.6). | Ajouter un lien vers l'historique/les détails des cartes cadeaux du client. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | Déclencher la génération et l'envoi des bons de cartes cadeaux lorsqu'un produit carte cadeau est acheté. Mettre à jour l'historique des cartes cadeaux. |
| `displayAdminOrder` | Sur la page de détail de la commande du Back Office. | Afficher les informations de la carte cadeau liées à la commande (achetée ou utilisée). |
| `actionOrderStatusUpdate` | Lorsque le statut d'une commande change. | Potentiellement activer/désactiver les cartes cadeaux en fonction du statut de la commande (par exemple, activer lors de « Paiement accepté »). |
| `actionFrontControllerSetMedia` | Avant qu'un contrôleur frontal ne rende son modèle. | Charger les actifs CSS et JavaScript spécifiques au front-office. |
| `actionAdminControllerSetMedia` | Avant qu'un contrôleur d'administration ne rende son modèle. | Charger les actifs CSS et JavaScript spécifiques au back-office. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour vous assurer que vous utilisez la version la plus récente et la plus sécurisée du module « Cartes Cadeaux - vendre des codes de bon d'achat », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe s'engage à fournir une assistance rapide et des améliorations continues à nos modules.
