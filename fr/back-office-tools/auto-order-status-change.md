---
title: "Changement automatique du statut de commande - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop « Changement automatique du statut de commande » par MyPresta.eu."
sidebar:
  label: "Changement automatique du statut de commande - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Auto order status change sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/auto-order-status-change.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/auto-order-status-change/)
>
> ---


# Changement automatique du statut de commande

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur inhabituelle n'est requise.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Changement automatique du statut de commande)

C'est l'écran de configuration principal et unique du module « Changement automatique du statut de commande ». Ici, vous définirez les règles de transition automatique des statuts de commande.

La page de configuration vous présentera une liste de vos statuts de commande actuels. Pour chaque statut, vous pourrez définir le nouveau statut vers lequel il doit changer automatiquement.

**Comment configurer une règle :**

1. **Identifier le statut « De » :** Sur le côté gauche du tableau de configuration, vous verrez une liste de tous vos statuts de commande existants (par exemple, « En attente de virement bancaire », « Paiement accepté », « Expédié », etc.). C'est le *statut de départ* qui déclenche le changement automatique.
2. **Sélectionner le statut « À » :** À côté de chaque statut « De », vous trouverez un menu déroulant. Ce menu contient tous les statuts de commande disponibles dans votre boutique. Sélectionnez le statut vers lequel vous souhaitez que la commande *change automatiquement* lorsqu'elle entre dans le statut « De ».
3. **Enregistrer vos modifications :** Après avoir configuré vos transitions souhaitées, assurez-vous de cliquer sur le bouton **« Enregistrer »** (généralement en bas de la page) pour appliquer vos règles.

Examinons les paramètres typiques que vous rencontrerez :

#### **Groupe de paramètres : Transitions automatiques de statut**

Cette section affichera un tableau ou une série de menus déroulants, vous permettant de mapper les statuts « De » aux statuts « À ».

- **Ce que fait ce paramètre :** C'est la fonctionnalité principale du module. Pour chaque statut de commande existant dans votre boutique, vous pouvez spécifier un *statut cible* vers lequel une commande passera automatiquement *si* son statut change vers le statut « De ».
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'un statut « À » est sélectionné pour un statut « De » :* Chaque fois que le statut d'une commande est mis à jour vers le statut « De » (manuellement par un administrateur, par une passerelle de paiement ou par un autre module), le module tentera immédiatement de le modifier vers le statut « À » sélectionné.
  - *Lorsque « Pas de changement » ou similaire est sélectionné (ou laissé vide) :* Si vous ne sélectionnez pas de statut « À » pour un statut « De » particulier, aucun changement automatique ne se produira pour les commandes entrant dans ce statut « De » spécifique. La commande restera simplement dans le statut « De » jusqu'à ce qu'elle soit modifiée manuellement ou qu'une autre règle/module agisse.
- **Valeur recommandée :** Cela dépend entièrement du flux de travail de votre boutique.
  - **Exemple 1 (Paiement accepté vers En cours de traitement) :**
    - **Statut De :** `Paiement accepté`
    - **Statut À :** `Préparation en cours` (ou `En cours de traitement`)
    - **Objectif et impact :** C'est une configuration très courante et fortement recommandée. Lorsqu'un client paie et que le paiement est confirmé (par exemple, par PayPal, Stripe, module de carte de crédit), le statut de la commande est automatiquement mis à jour vers « Paiement accepté ». Cette règle le déplace alors immédiatement vers « Préparation en cours », signalant à votre entrepôt ou à votre équipe d'exécution de commencer à préparer la commande sans aucune intervention manuelle. Cela permet de gagner du temps et d'assurer une exécution rapide.
  - **Exemple 2 (Expédié vers Livré) :**
    - **Statut De :** `Expédié`
    - **Statut À :** `Livré`
    - **Objectif et impact :** Alors que « Expédié » indique que l'article a quitté votre entrepôt, « Livré » confirme qu'il a atteint le client. Si l'intégration de votre transporteur ne met pas automatiquement à jour vers « Livré », vous pourriez définir cette règle. Cependant, soyez prudent : cela suppose que toutes les commandes « Expédiées » sont finalement « Livrées ». Il est souvent préférable de se fier au suivi du transporteur pour le statut « Livré » si possible. Utilisez ceci si vous souhaitez rapidement retirer les commandes « Expédiées » de votre liste active après un délai de livraison raisonnable, mais sachez que cela pourrait ne pas refléter la livraison réelle.
  - **Exemple 3 (En attente de virement bancaire vers Annulé - avec prudence) :**
    - **Statut De :** `En attente de virement bancaire`
    - **Statut À :** `Annulé`
    - **Objectif et impact :** Si vous avez une politique stricte selon laquelle les virements bancaires doivent être reçus dans un certain délai, et que vous modifiez manuellement les commandes en retard en « Annulé », ce module pourrait automatiser cela. Cependant, le module se déclenche *lorsque le statut change vers* « En attente de virement bancaire ». Si vous souhaitez annuler *après un délai*, ce module seul ne le fera pas. Vous auriez besoin d'un autre mécanisme (par exemple, une tâche cron ou un autre module) pour modifier le statut en « En attente de virement bancaire » *après* le délai, ce qui déclencherait alors ce module pour le modifier en « Annulé ». Ce cas d'utilisation spécifique est moins direct pour le déclencheur immédiat de ce module.
- **Scénario / exemple de marchand :**
  - « Je veux que toutes les commandes dont le paiement est réussi passent automatiquement à 'Préparation en cours' afin que mon équipe d'emballage sache qu'elle doit commencer à travailler dessus immédiatement. »
  - « Lorsqu'un client demande un remboursement et que je change le statut de la commande en 'Remboursé', je veux qu'elle passe automatiquement à 'Fermé' afin qu'elle ne figure plus dans ma liste de commandes actives. »

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | `Statut De` (par exemple, Paiement accepté) | Varie selon le flux de travail | Le statut initial qui déclenche un changement automatique. |
| Configuration du module | `Statut À` (menu déroulant pour chaque `Statut De`) | `Préparation en cours` (pour `Paiement accepté`) | Le statut cible vers lequel une commande passera automatiquement lorsqu'elle entre dans le `Statut De`. Automatise le flux de travail, fait gagner du temps. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes statuts de commande ne changent pas automatiquement. Que dois-je vérifier ?**

- **R :** Tout d'abord, allez dans **Modules > Gestionnaire de modules > Changement automatique du statut de commande > Configurer** et assurez-vous d'avoir correctement configuré les statuts « De » et « À ».
- **R :** Vérifiez que le changement de statut initial (le statut « De ») se produit réellement. Par exemple, si vous vous attendez à ce que « Paiement accepté » déclenche un changement, assurez-vous que la commande atteint d'abord « Paiement accepté ».
- **R :** Videz votre cache PrestaShop. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » en haut à droite. Parfois, les configurations de module nécessitent un rafraîchissement du cache pour prendre effet.

**Q2 : Ce module peut-il modifier les statuts en fonction d'un délai (par exemple, annuler une commande si elle n'est pas payée dans les 24 heures) ?**

- **R :** Non, ce module se déclenche *immédiatement* lorsqu'un statut de commande *change* vers un statut « De » spécifique. Il n'a pas de fonctionnalité intégrée pour les délais basés sur le temps ou les tâches cron. Pour les actions basées sur le temps, vous auriez besoin d'un module séparé ou d d'un développement personnalisé qui modifie le statut de la commande après un délai, ce qui déclencherait alors ce module.

**Q3 : Ce module interférera-t-il avec les mises à jour de statut de ma passerelle de paiement ?**

- **R :** Non, il fonctionne *avec* elles. Les passerelles de paiement mettent généralement à jour une commande vers un statut comme « Paiement accepté » ou « En attente de paiement ». Ce module prend alors le relais *après* cette mise à jour initiale, en appliquant votre prochaine règle. Il n'empêche pas la passerelle de paiement de définir son statut initial.

**Q4 : J'ai un thème personnalisé. Ce module fonctionnera-t-il ?**

- **R :** Oui, absolument. Ce module fonctionne entièrement dans le back-office de PrestaShop et sur la logique de traitement des commandes. Il n'a pas de composants visuels front-office ni de style spécifique au thème, il est donc entièrement compatible avec n'importe quel thème PrestaShop.

**Q5 : Comment traduire les paramètres du module si mon back-office est dans une autre langue ?**

- **R :** PrestaShop gère automatiquement la traduction des statuts de commande. Le module utilise les noms de vos statuts de commande existants. Si vous devez traduire les éléments d'interface propres au module (comme le bouton « Enregistrer » ou les titres de section), vous pouvez le faire via **International > Traductions** dans votre back-office PrestaShop. Sélectionnez « Traductions des modules installés », choisissez votre thème, votre langue, puis recherchez le module « schange ».

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module « Changement automatique du statut de commande ».

### 4.1 Aperçu de l'architecture

Le module « Changement automatique du statut de commande » (`schange`) est un module PrestaShop simple principalement conçu pour s'accrocher à l'événement `actionOrderStatusPostUpdate`. Il suit une structure de module PrestaShop standard, tirant parti de la classe `Module` pour l'installation, la désinstallation et la configuration. Sa logique principale réside dans le fichier principal du module, traitant les changements de statut en fonction des configurations stockées dans `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient **pas** de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la configuration est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit **pas** de classes personnalisées ou d'instances `ObjectModel` dans un répertoire `classes/`. Toute la logique est encapsulée dans la classe principale `schange`.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut **pas** de fichiers JavaScript personnalisés.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut **pas** de fichiers CSS personnalisés. Le style de la page de configuration est géré par le CSS par défaut du back-office de PrestaShop.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module utilise un seul modèle Smarty pour son interface de configuration.

- **Modèles d'administration (`views/templates/admin/`)** :
  - `schange/views/tpl/selectedProducts.tpl` : Ce modèle est utilisé dans la méthode `getContent()` pour rendre le formulaire de configuration du module. Il affiche généralement la liste des statuts de commande « De » et leurs menus déroulants de statut « À » correspondants. Les développeurs peuvent inspecter ce fichier pour comprendre la structure du formulaire de configuration et la manière dont le mappage des statuts est présenté.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Ce module ne crée **pas** de tables SQL personnalisées.
  - Tous les paramètres de configuration (les mappages de statut « De » à « À ») sont stockés dans la table `ps_configuration`. Chaque mappage est probablement stocké comme une clé de configuration distincte, ou un tableau sérialisé sous une seule clé, en utilisant le nom du module comme préfixe (par exemple, `SCHANGE_STATUS_FROM_X_TO_Y` ou `SCHANGE_STATUS_MAP`).
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionOrderStatusPostUpdate` | Déclenché immédiatement après la mise à jour réussie du statut d'une commande. | C'est le hook principal utilisé par le module. Lorsqu'un statut de commande change (par exemple, de « En attente de paiement » à « Paiement accepté »), ce hook se déclenche. Le module vérifie alors si le nouveau statut (le statut « De ») a un statut « À » configuré. Si un mappage existe, le module met à jour par programme la commande vers le statut « À » désigné. |

### 4.8 Fichier principal du module (`schange/index.php`)

- **Nom de la classe** : `schange`
- **Classe parente** : `Module`
- **Méthodes clés** :
  - `__construct()` : Initialise les métadonnées du module (nom, onglet, version, auteur, etc.).
  - `install()` : Enregistre le hook `actionOrderStatusPostUpdate` et définit potentiellement les valeurs de configuration par défaut.
  - `uninstall()` : Désenregistre le hook et nettoie les valeurs de configuration de `ps_configuration`.
  - `getContent()` : Rend la page de configuration du module dans le Back Office. Cette méthode gère la soumission du formulaire, enregistre les paramètres dans `ps_configuration` et affiche l'interface de mappage des statuts à l'aide de `selectedProducts.tpl`.
  - `hookActionOrderStatusPostUpdate($params)` : C'est le gestionnaire de logique principal.
    - Il reçoit `$params` contenant le `newOrderStatus` et `id_order`.
    - Il récupère les mappages de statut configurés à partir de `ps_configuration`.
    - Si le `newOrderStatus` correspond à un statut « De » configuré, il charge l'objet `Order` pour `id_order`.
    - Il tente ensuite de mettre à jour le statut de la commande vers le statut « À » correspondant à l'aide de `Order->setCurrentState()`.
    - Il s'assure que le changement de statut est valide et gère les erreurs potentielles.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Changement automatique du statut de commande », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
