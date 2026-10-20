---
title: "Perfect Money - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module Perfect Money PrestaShop par MyPresta.eu."
sidebar:
  label: "Perfect Money - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Perfect Money sur MyPresta.eu](https://mypresta.eu/modules/payment-process/perfect-money.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/payment/perfect-money/)
>
> ---


# Perfect Money

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 1.6.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour une communication sécurisée avec la passerelle de paiement, et sont presque toujours disponibles sur les environnements d'hébergement modernes.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Perfect Money)

Ceci est l'écran de configuration principal du module Perfect Money, où vous entrerez les détails de votre compte Perfect Money et configurerez la façon dont la méthode de paiement apparaît et fonctionne dans votre boutique.

#### **Paramètres du compte Perfect Money**

- **Ce que fait ce paramètre :** Ces champs sont cruciaux pour connecter votre boutique PrestaShop à votre compte marchand Perfect Money. Ils indiquent au module à quel compte Perfect Money envoyer les paiements et comment vérifier les transactions.
- **Effet de la modification de ce paramètre :** Des valeurs incorrectes empêcheront les clients d'effectuer des paiements, ou les paiements pourraient ne pas être correctement attribués à votre compte.
  - *Lorsqu'il est correctement configuré :* Les paiements seront traités avec succès via votre compte Perfect Money.
  - *Lorsqu'il est mal configuré :* Les paiements échoueront, ou les clients rencontreront des erreurs lors du paiement.
- **Valeur recommandée :** Entrez les détails exacts fournis par votre compte marchand Perfect Money.
- **Scénario / exemple de marchand :** Vous avez enregistré un compte marchand auprès de Perfect Money. Ils vous fournissent un "ID de compte Perfect Money" (par exemple, U1234567) et un "Nom de compte Perfect Money" (par exemple, MyStorePayments). Vous configurez également une "Phrase secrète alternative Perfect Money" dans les paramètres de votre compte Perfect Money pour une sécurité renforcée. Vous devez entrer ces valeurs exactes ici.

#### **Paramètres d'affichage du paiement**

- **Ce que fait ce paramètre :** Cette section contrôle la façon dont l'option de paiement Perfect Money est présentée à vos clients lors du paiement.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Les clients verront l'option Perfect Money et pourront la choisir pour le paiement.
  - *Lorsqu'il est désactivé :* Perfect Money n'apparaîtra pas comme option de paiement.
- **Valeur recommandée :** "OUI" (Activé) si vous souhaitez proposer Perfect Money comme méthode de paiement.
- **Scénario / exemple de marchand :** Vous souhaitez proposer Perfect Money comme option de paiement. Vous l'activez. Si vous souhaitez le désactiver temporairement pour maintenance ou si vous ne souhaitez plus accepter Perfect Money, vous le réglerez sur "NON".

#### **Paramètres de statut de commande**

- **Ce que fait ce paramètre :** Ces paramètres déterminent le statut qu'une commande aura dans votre back office PrestaShop après qu'un client ait effectué un paiement via Perfect Money.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur "Paiement accepté" :* Les commandes payées via Perfect Money seront automatiquement marquées comme "Paiement accepté" dans votre back office PrestaShop, indiquant une transaction réussie.
  - *Lorsqu'il est défini sur "Erreur de paiement" :* Si un paiement échoue ou si un problème survient, la commande sera marquée avec ce statut.
- **Valeur recommandée :**
  - **Statut de commande pour un paiement réussi :** "Paiement accepté" (ou un statut similaire que vous avez configuré pour les paiements réussis).
  - **Statut de commande pour une erreur de paiement :** "Erreur de paiement" (ou un statut similaire pour les paiements échoués).
- **Scénario / exemple de marchand :** Un client paie avec succès avec Perfect Money. Vous souhaitez identifier rapidement ces commandes comme prêtes à être traitées. En définissant le "Statut de commande pour un paiement réussi" sur "Paiement accepté", votre équipe sait immédiatement que le paiement a été effectué. Si un client tente de payer mais que la transaction échoue, la commande sera marquée "Erreur de paiement", vous permettant de faire un suivi ou au client de réessayer.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et Impact |
| --- | --- | --- | --- |
| Configuration du module | ID de compte Perfect Money | Votre ID de compte Perfect Money (par exemple, U1234567) | Identifie votre compte marchand Perfect Money pour la réception des paiements. **CRITIQUE pour le traitement des paiements.** |
| Configuration du module | Nom de compte Perfect Money | Votre nom de compte Perfect Money | Le nom associé à votre compte Perfect Money. |
| Configuration du module | Phrase secrète alternative Perfect Money | Votre phrase secrète alternative Perfect Money | Clé de sécurité pour la vérification des transactions. Définissez-la dans votre compte Perfect Money. **CRITIQUE pour la sécurité.** |
| Configuration du module | Activer le paiement Perfect Money | OUI | Active ou désactive la visibilité de Perfect Money comme option de paiement sur votre page de paiement. |
| Configuration du module | Statut de commande pour un paiement réussi | Paiement accepté | Le statut de commande PrestaShop attribué aux commandes payées avec succès via Perfect Money. |
| Configuration du module | Statut de commande pour une erreur de paiement | Erreur de paiement | Le statut de commande PrestaShop attribué aux commandes où le paiement Perfect Money a échoué. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : Mes clients voient une erreur lorsqu'ils essaient de payer avec Perfect Money.**
R :

-   **Vérifiez les paramètres de votre compte Perfect Money :** Vérifiez à nouveau que votre "ID de compte Perfect Money", "Nom de compte Perfect Money" et "Phrase secrète alternative Perfect Money" sont saisis *exactement* tels qu'ils apparaissent dans votre compte marchand Perfect Money. Même une petite faute de frappe peut provoquer des erreurs.
-   **Vérifiez le statut du compte Perfect Money :** Connectez-vous directement à votre compte Perfect Money pour vous assurer qu'il est actif, en règle et configuré pour recevoir des paiements.
-   **Examinez les journaux d'erreurs de PrestaShop :** Dans votre back office PrestaShop, naviguez vers **Paramètres avancés > Journaux** pour voir si des erreurs spécifiques liées au module Perfect Money sont enregistrées.

**Q : Les commandes ne sont pas marquées "Paiement accepté" après un paiement Perfect Money réussi.**
R :

-   **Vérifiez les paramètres de statut de commande :** Allez dans la configuration du module et assurez-vous que "Statut de commande pour un paiement réussi" est défini sur le statut correct (par exemple, "Paiement accepté").
-   **IPN/Rappel Perfect Money :** Assurez-vous que votre compte Perfect Money est correctement configuré pour envoyer des notifications de paiement instantané (IPN) ou des rappels à votre boutique PrestaShop. Le module s'appuie sur ces notifications pour mettre à jour les statuts de commande. Bien que le module gère l'URL, les paramètres du compte Perfect Money peuvent parfois interférer.

**Q : Perfect Money n'apparaît pas comme option de paiement sur ma page de paiement.**
R :

-   **Module activé :** Dans la configuration du module, assurez-vous que "Activer le paiement Perfect Money" est défini sur "OUI".
-   **Module installé :** Vérifiez que le module est correctement installé et activé dans **Modules > Gestionnaire de modules**.
-   **Cache :** Videz le cache de votre PrestaShop (sous **Paramètres avancés > Performances**) et le cache de votre navigateur. Parfois, d'anciennes données mises en cache peuvent empêcher l'apparition de nouvelles options de paiement.
-   **Compatibilité du thème :** Bien que le module soit conçu pour être compatible, des thèmes très fortement personnalisés peuvent occasionnellement nécessiter des ajustements mineurs. Si vous suspectez un conflit de thème, essayez de passer temporairement au thème PrestaShop par défaut pour voir si l'option apparaît.

**Q : Puis-je personnaliser le logo ou le texte Perfect Money sur la page de paiement ?**
R : Le module utilise un modèle standard pour afficher l'option de paiement. Vous pouvez généralement personnaliser le texte en allant dans **International > Traductions** dans votre back office PrestaShop, en sélectionnant "Traductions des modules installés", en choisissant votre thème, puis en trouvant le module "Perfect Money". Pour les changements de logo, vous devrez modifier le fichier de modèle du module (`perfectmoney.tpl`) ou utiliser des remplacements CSS dans votre thème.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé du module Perfect Money pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module Perfect Money suit l'architecture standard des modules PrestaShop, utilisant principalement une classe de module principale (`PerfectMoney`) pour l'installation, la désinstallation et la configuration, et des classes `ModuleFrontController` pour gérer les processus de redirection et de validation des paiements. Il s'intègre à la passerelle de paiement Perfect Money en utilisant un modèle de communication de serveur à serveur (IPN/rappel) pour confirmer les transactions et mettre à jour les statuts de commande.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs gèrent les aspects du processus de paiement côté client, y compris la redirection vers Perfect Money et la gestion du rappel après le paiement.

-   **`perfectmoney/controllers/front/index.php`**

    -   **Nom de la classe** : `PerfectMoneyIndexModuleFrontController`
    -   **Classe parente** : `ModuleFrontController`
    -   **Responsabilité** : Ce contrôleur est généralement responsable de l'initialisation du processus de paiement. Lorsqu'un client sélectionne Perfect Money et confirme sa commande, ce contrôleur prépare les paramètres de la demande de paiement (ID du marchand, montant, devise, description de la commande, URL de retour) et redirige le navigateur du client vers la passerelle de paiement Perfect Money. Il collecte les détails de commande nécessaires à partir du panier et construit le formulaire de paiement.
-   **`perfectmoney/controllers/front/validation.php`**

    -   **Nom de la classe** : `PerfectMoneyValidationModuleFrontController`
    -   **Classe parente** : `ModuleFrontController`
    -   **Responsabilité** : C'est le contrôleur crucial qui gère le rappel (Instant Payment Notification - IPN) de Perfect Money après qu'un paiement a été traité.
        -   Il reçoit les données POST de Perfect Money contenant les détails de la transaction et un hachage de sécurité.
        -   Il vérifie l'intégrité et l'authenticité de la notification de paiement en utilisant la phrase secrète alternative configurée.
        -   Si le paiement est valide et réussi, il met à jour le statut de la commande PrestaShop (par exemple, vers "Paiement accepté"), crée une entrée d'historique de commande et envoie potentiellement des e-mails de confirmation de commande.
        -   Si le paiement échoue ou est invalide, il met à jour le statut de la commande en conséquence (par exemple, vers "Erreur de paiement").
        -   Il redirige ensuite le client vers la page PrestaShop appropriée (par exemple, page de confirmation de commande ou page d'erreur).

### 4.3 Classes et modèles de base (`classes/`)

Le module ne semble pas définir de classes personnalisées étendant `ObjectModel` ou d'autres classes PrestaShop de base dans un répertoire `classes/` dédié. Toute la logique de base est probablement encapsulée dans la classe de module principale `PerfectMoney` (`index.php`) et les contrôleurs frontaux.

### 4.4 Actifs JavaScript (`views/js/`)

Aucun fichier JavaScript personnalisé n'a été détecté dans l'archive du module. Le processus de paiement est principalement géré par des redirections côté serveur et l'interface de paiement propre à Perfect Money.

### 4.5 Feuilles de style CSS (`views/css/`)

Aucun fichier CSS personnalisé n'a été détecté dans l'archive du module. Le style de l'option de paiement sur la page de paiement est probablement hérité du thème PrestaShop ou des styles en ligne dans le modèle.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **`perfectmoney/views/admin.tpl`**

    -   **Portée** : Configuration d'administration du back-office.
    -   **Objectif** : Ce modèle est utilisé pour afficher le formulaire de configuration du module dans le back office de PrestaShop. Il affiche les champs de saisie pour l'ID de compte Perfect Money, le nom de compte, la phrase secrète alternative et les listes déroulantes de sélection du statut de commande. Il utilise les assistants de formulaire et le style standard de PrestaShop.
-   **`perfectmoney/views/perfectmoney.tpl`**

    -   **Portée** : Front-office (étape de paiement de la commande).
    -   **Objectif** : Ce modèle est responsable de l'affichage de l'option de paiement Perfect Money au client sur la page de paiement. Il inclut généralement le titre de la méthode de paiement, la description et potentiellement le logo Perfect Money. Il est rendu dans un hook de paiement (par exemple, `displayPaymentOptions` dans PS 1.7+ ou `displayPayment` dans PS 1.6).
-   **`perfectmoney/views/success_page.tpl`**

    -   **Portée** : Front-office (page de confirmation/succès de commande).
    -   **Objectif** : Ce modèle est probablement utilisé pour afficher un message de succès personnalisé ou des informations supplémentaires au client après un paiement Perfect Money réussi, avant ou dans le cadre de la page de confirmation de commande standard. Il pourrait être rendu par le contrôleur `validation.php`.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module ne semble pas créer de tables SQL personnalisées.
    -   Les paramètres de configuration (ID de compte Perfect Money, phrase secrète, etc.) sont stockés dans la table `ps_configuration`, en utilisant des clés préfixées par `PERFECTMONEY_`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayPaymentOptions` (PS 1.7+) | Sur la page de paiement, étape de paiement. | Affiche l'option de paiement Perfect Money en utilisant `perfectmoney.tpl`. |
| `displayPayment` (PS 1.6) | Sur la page de paiement, étape de paiement. | Affiche l'option de paiement Perfect Money en utilisant `perfectmoney.tpl`. |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Potentiellement utilisé pour charger des actifs spécifiques au module (JS/CSS) s'il y en avait, ou pour des balises méta. (Aucun actif détecté, donc probablement pour l'initialisation du module ou la compatibilité). |
| `actionPaymentConfirmation` | Après la confirmation du statut de paiement d'une commande. | Pourrait être utilisé pour le traitement post-paiement, bien que la mise à jour principale du statut soit gérée par le contrôleur `validation.php`. |
| `actionValidateOrder` | Après qu'une commande a été validée et créée avec succès. | Utilisé par le module pour créer la commande dans PrestaShop avec le statut initial avant la redirection vers Perfect Money. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module Perfect Money, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
