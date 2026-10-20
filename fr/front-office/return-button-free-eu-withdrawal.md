---
title: "Bouton de Retour Gratuit - Retrait UE - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Bouton de Retour Gratuit - Retrait UE par MyPresta.eu."
sidebar:
  label: "Bouton de Retour Gratuit - Retrait UE"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Return Button Free - EU Withdrawal sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/return-button-free-eu-withdrawal.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/return-button-free-eu-withdrawal/)
>
> ---


# Bouton de Retour Gratuit - Retrait UE

## 1. Exigences et Compatibilité
-   **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilité PHP** : PHP 7.1 - 8.5
-   **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises, qui sont généralement disponibles sur la plupart des environnements d'hébergement modernes.

## 2. Configuration complète (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
C'est l'écran de configuration principal du module, où vous contrôlez son comportement général et son apparence.

#### Onglet Paramètres généraux

-   **Activer le module :**
    -   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité du module sur votre boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Le bouton de rétractation et la fonctionnalité seront actifs et visibles pour les clients selon vos autres paramètres.
        -   *Lorsqu'il est désactivé :* Les fonctionnalités du module seront complètement masquées du front office, et les clients ne pourront pas soumettre de demandes de rétractation via celui-ci.
    -   **Valeur recommandée :** OUI
    -   **Scénario / exemple de marchand :** Vous l'activeriez lorsque vous êtes prêt à offrir l'option de rétractation à vos clients. Vous pourriez le désactiver temporairement pendant la maintenance ou si vous devez apporter des modifications importantes à votre politique de retour.

-   **Afficher le bouton de rétractation dans :**
    -   **Ce que fait ce paramètre :** Détermine où le bouton principal "Demande de rétractation" apparaît sur le front office de votre boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *En-tête :* Le bouton apparaît dans la section supérieure de votre site web, souvent visible globalement.
        -   *Colonne de gauche :* Le bouton apparaît dans la barre latérale gauche (si votre thème en a une).
        -   *Colonne de droite :* Le bouton apparaît dans la barre latérale droite (si votre thème en a une).
        -   *Page produit :* Le bouton apparaît sur les pages de produits individuelles.
        -   *Pied de page :* Le bouton apparaît dans la section inférieure de votre site web.
    -   **Valeur recommandée :** Pied de page (souvent un bon emplacement discret pour les liens légaux) ou En-tête (pour une visibilité maximale). Choisissez en fonction de la mise en page de votre thème et de votre préférence pour la proéminence.
    -   **Scénario / exemple de marchand :** Si vous souhaitez que les clients trouvent facilement l'option, la placer dans l'En-tête ou le Pied de page est courant. Si vous préférez qu'elle soit moins proéminente mais toujours accessible, une colonne pourrait convenir.

-   **Autoriser les demandes de rétractation des invités :**
    -   **Ce que fait ce paramètre :** Contrôle si les clients qui ont passé commande sans créer de compte peuvent toujours soumettre une demande de rétractation.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Les invités pourront accéder au formulaire de rétractation en fournissant leur référence de commande et leur adresse e-mail.
        -   *Lorsqu'il est désactivé :* Seuls les clients enregistrés qui sont connectés à leur compte pourront soumettre des demandes de rétractation.
    -   **Valeur recommandée :** OUI (Fortement recommandé pour la conformité européenne, car le droit de rétractation s'applique à tous les consommateurs, pas seulement aux enregistrés).
    -   **Scénario / exemple de marchand :** L'activation de cette option garantit que vous respectez les droits des consommateurs pour tous les clients, quelle que soit leur méthode de paiement, et évite de frustrer les invités qui ne trouvent pas de moyen de se rétracter.

-   **États de commande pour l'éligibilité à la rétractation :**
    -   **Ce que fait ce paramètre :** Définit quels statuts de commande rendent une commande éligible à une demande de rétractation. Par exemple, vous ne pouvez autoriser les rétractations que pour les commandes qui ont été "Livrée" ou "Expédiée".
    -   **Effet de la modification de ce paramètre :** Les clients ne verront l'option de rétractation que pour les commandes qui correspondent à l'un des statuts sélectionnés dans leur historique de commandes ou lors de la saisie d'une référence de commande invité.
    -   **Valeur recommandée :** Sélectionnez des statuts comme "Paiement accepté", "Préparation en cours", "Expédiée", "Livrée". Évitez les statuts comme "Annulée" ou "Remboursée" car les rétractations ne sont pas applicables dans ces cas.
    -   **Scénario / exemple de marchand :** Vous souhaitez autoriser les rétractations pour les commandes déjà traitées ou livrées, mais pas pour les commandes en attente de paiement ou déjà annulées.

-   **États de commande pour la confirmation de rétractation :**
    -   **Ce que fait ce paramètre :** Spécifie le statut de commande qui doit être automatiquement appliqué à une commande une fois qu'une demande de rétractation a été soumise avec succès par le client. Cela vous aide à identifier rapidement les commandes avec des demandes de rétractation en attente.
    -   **Effet de la modification de ce paramètre :** Lorsqu'un client soumet une rétractation, le statut de la commande passera à celui que vous sélectionnez ici.
    -   **Valeur recommandée :** Créez un nouveau statut de commande distinct comme "Rétractation demandée" ou "Retrait UE en attente" dans les paramètres de statut de commande de votre PrestaShop (sous Paramètres de la boutique > Paramètres de commande > Statuts) et sélectionnez-le ici.
    -   **Scénario / exemple de marchand :** La définition d'un statut spécifique comme "Rétractation demandée" permet à votre équipe de service client de filtrer et de gérer facilement les commandes qui nécessitent une attention pour un processus de rétractation.

-   **États de commande pour la finalisation de la rétractation :**
    -   **Ce que fait ce paramètre :** Spécifie le statut de commande qui doit être automatiquement appliqué à une commande une fois que vous, le marchand, avez traité et finalisé la rétractation (par exemple, émis un remboursement).
    -   **Effet de la modification de ce paramètre :** Après avoir marqué une demande de rétractation comme terminée dans l'interface d'administration du module, le statut de la commande associée sera mis à jour vers ce statut choisi.
    -   **Valeur recommandée :** Sélectionnez un statut existant comme "Remboursée" ou créez-en un nouveau comme "Retrait UE terminé".
    -   **Scénario / exemple de marchand :** Une fois que vous avez traité le remboursement et clôturé le dossier de rétractation, la mise à jour du statut de la commande à "Remboursée" fournit un enregistrement clair pour vous et le client.

-   **Activer les statistiques :**
    -   **Ce que fait ce paramètre :** Contrôle si le module collecte des statistiques anonymes sur son utilisation. Ces données aident le développeur du module à l'améliorer.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Le module enverra des données d'utilisation anonymes.
        -   *Lorsqu'il est désactivé :* Aucune donnée d'utilisation ne sera envoyée.
    -   **Valeur recommandée :** OUI (Aide à améliorer le module pour tous).
    -   **Scénario / exemple de marchand :** Vous activez cette option pour contribuer au développement du module, ou la désactivez si vous avez des politiques de confidentialité strictes qui empêchent toute transmission de données externes.

#### Onglet Informations légales

-   **Délai de rétractation (jours) :**
    -   **Ce que fait ce paramètre :** Définit le nombre de jours calendaires dont dispose un client pour exercer son droit de rétractation, à compter du jour où il reçoit les marchandises.
    -   **Effet de la modification de ce paramètre :** Le module affichera cette période aux clients et l'utilisera en interne pour tout calcul de date ou vérification d'éligibilité.
    -   **Valeur recommandée :** 14 (C'est l'exigence légale minimale dans l'UE, mais vous pouvez offrir une période plus longue si vous le souhaitez).
    -   **Scénario / exemple de marchand :** Vous définissez cela à 14 jours pour vous conformer à la loi européenne. Si vous offrez une politique de retour plus généreuse, vous pourriez le définir à 30 jours.

-   **Texte du formulaire de rétractation :**
    -   **Ce que fait ce paramètre :** Vous permet de personnaliser le texte d'introduction affiché en haut du formulaire de demande de rétractation. Il s'agit d'un champ multilingue.
    -   **Effet de la modification de ce paramètre :** Le texte que vous saisissez apparaîtra aux clients lorsqu'ils accèdent au formulaire de rétractation.
    -   **Valeur recommandée :** Fournissez des instructions claires et concises ou une brève explication du processus de rétractation.
    -   **Scénario / exemple de marchand :** Vous pourriez ajouter un message comme : "Veuillez remplir ce formulaire pour exercer votre droit de rétractation. Vous disposez de 14 jours à compter de la réception de votre commande pour soumettre cette demande."

-   **Texte de l'e-mail de confirmation :**
    -   **Ce que fait ce paramètre :** Vous permet de personnaliser le texte inclus dans l'e-mail de confirmation envoyé aux clients après qu'ils ont soumis une demande de rétractation. Il s'agit d'un champ multilingue.
    -   **Effet de la modification de ce paramètre :** Le texte que vous saisissez fera partie de l'e-mail que les clients reçoivent, servant de preuve sur support durable de leur demande.
    -   **Valeur recommandée :** Incluez des informations importantes telles que les prochaines étapes, où envoyer les marchandises et toute instruction de retour spécifique.
    -   **Scénario / exemple de marchand :** Vous pourriez écrire : "Merci pour votre demande de rétractation. Votre demande a été reçue et sera traitée sous peu. Veuillez retourner les marchandises à [Votre adresse de retour] dans les 14 jours. Pour plus de détails, veuillez consulter notre politique de retour."

-   **Lien vers la politique de rétractation :**
    -   **Ce que fait ce paramètre :** Vous permet de fournir un lien vers la page détaillée de la politique de rétractation ou de retour de votre boutique.
    -   **Effet de la modification de ce paramètre :** Un lien sera affiché sur le formulaire de rétractation, dirigeant les clients vers votre politique complète.
    -   **Valeur recommandée :** Fournissez l'URL de votre page CMS dédiée aux retours/rétractations.
    -   **Scénario / exemple de marchand :** Vous avez une page CMS intitulée "Politique de retours et remboursements" à `votreboutique.com/content/retours-remboursements`. Vous saisiriez cette URL ici.

#### 2.1.1 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
|---|---|---|---|
| **Onglet Paramètres généraux** | Activer le module | OUI | Active/désactive la fonctionnalité du module. |
| | Afficher le bouton de rétractation dans | Pied de page / En-tête | Définit l'emplacement du bouton principal de rétractation. |
| | Autoriser les demandes de rétractation des invités | OUI | Active la rétractation pour les clients non enregistrés. |
| | États de commande pour l'éligibilité à la rétractation | Paiement accepté, Expédiée, Livrée | Définit quels statuts de commande autorisent les demandes de rétractation. |
| | États de commande pour la confirmation de rétractation | "Rétractation demandée" (Personnalisé) | Statut appliqué à la commande lors de la soumission par le client. |
| | États de commande pour la finalisation de la rétractation | "Remboursée" (Existant) / "Retrait UE terminé" (Personnalisé) | Statut appliqué à la commande lors de la finalisation par le marchand. |
| | Activer les statistiques | OUI | Permet la collecte de données d'utilisation anonymes pour l'amélioration du module. |
| **Onglet Informations légales** | Délai de rétractation (jours) | 14 | Définit la période légale de rétractation. |
| | Texte du formulaire de rétractation | Personnalisable | Texte d'introduction sur le formulaire de rétractation. |
| | Texte de l'e-mail de confirmation | Personnalisable | Texte inclus dans l'e-mail de confirmation de rétractation. |
| | Lien vers la politique de rétractation | URL de votre page CMS | Lien vers votre politique détaillée de retour/rétractation. |

### 2.2 Écrans d'administration dédiés et vues du contrôleur

#### Demandes de rétractation (Back Office > Modules > Bouton de Retour Gratuit > Demandes de rétractation)
Cet écran d'administration dédié est l'endroit où vous gérez toutes les demandes de rétractation entrantes de vos clients.

-   **Nom de l'écran et emplacement du menu :** **Demandes de rétractation** (situé sous le menu principal "Modules", puis le sous-menu "Bouton de Retour Gratuit").
-   **Actions et paramètres disponibles :**
    -   **Tableau de liste :** Affiche une liste complète de toutes les demandes de rétractation.
        -   **ID :** Identifiant unique pour chaque demande.
        -   **Soumise :** Date et heure de soumission de la demande.
        -   **Commande :** La référence de commande PrestaShop associée.
        -   **Prénom, Nom, E-mail :** Coordonnées du client.
        -   **Portée :** Indique s'il s'agit d'une rétractation de commande complète (cette version gratuite ne prend en charge que la rétractation de commande complète).
        -   **Type :** Le type de rétractation (par exemple, "Retrait UE").
        -   **Statut :** Le statut actuel de la demande de rétractation (par exemple, "En attente", "Traitée", "Annulée").
    -   **Afficher les détails :** Cliquez sur n'importe quelle demande dans la liste pour ouvrir une vue détaillée.
        -   Cette vue fournit toutes les informations soumises par le client, y compris les détails de la commande, les produits et toute note supplémentaire.
        -   Vous pouvez ajouter des notes internes, modifier le statut de la rétractation (par exemple, de "En attente" à "Traitée" ou "Annulée") et suivre l'historique des modifications.
        -   Le paramètre "États de commande pour la finalisation de la rétractation" (de la configuration principale) sera appliqué à la commande associée lorsque vous marquerez une rétractation comme terminée ici.
    -   **Filtrage et recherche :** Vous pouvez filtrer la liste par statut, nom du client, ID de commande, etc., pour trouver rapidement des demandes spécifiques.
-   **Effet des modifications :**
    -   **Modification du statut :** La mise à jour du statut d'une demande de rétractation (par exemple, à "Traitée" ou "Terminée") mettra à jour l'enregistrement dans le module et, si configuré, le statut de la commande PrestaShop associée. Cela vous aide à suivre les progrès et à communiquer avec les clients.
    -   **Ajout de notes :** Les notes internes sont destinées à la référence de votre équipe et ne sont pas visibles par le client. Elles aident à documenter la communication et les actions entreprises pour chaque rétractation.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Vérifiez régulièrement l'écran "Demandes de rétractation" pour les nouvelles demandes "En attente".
    2.  Cliquez sur une demande pour afficher ses détails.
    3.  Examinez les informations du client et la commande associée.
    4.  Communiquez avec le client si nécessaire (par exemple, fournissez des instructions d'expédition de retour).
    5.  Une fois les marchandises reçues et inspectées, traitez le remboursement dans la gestion des commandes de PrestaShop.
    6.  Mettez à jour le statut de la demande de rétractation dans le module à "Traitée" ou "Terminée". Cela mettra également à jour le statut de la commande principale si vous avez configuré "États de commande pour la finalisation de la rétractation".
    7.  Ajoutez toutes les notes internes pertinentes concernant le remboursement, les numéros de suivi ou la communication.

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

-   **Q : Le bouton de rétractation n'apparaît pas sur ma boutique.**
    -   **R :** Tout d'abord, vérifiez si le module est "Activé" dans sa configuration. Ensuite, vérifiez que vous avez sélectionné un emplacement "Afficher le bouton de rétractation dans" (par exemple, Pied de page, En-tête). Si votre thème est fortement personnalisé, il se peut qu'il ne se connecte pas correctement. Essayez de sélectionner un emplacement d'affichage différent. Assurez-vous également que votre cache Smarty est vidé (Paramètres avancés > Performances > Vider le cache).
-   **Q : Les clients soumettent des demandes de rétractation, mais le statut de la commande ne change pas.**
    -   **R :** Allez dans la configuration du module et vérifiez le paramètre "États de commande pour la confirmation de rétractation". Assurez-vous d'avoir sélectionné un statut de commande approprié. Si vous avez créé un nouveau statut, assurez-vous qu'il est correctement configuré dans PrestaShop (Paramètres de la boutique > Paramètres de commande > Statuts).
-   **Q : Les clients peuvent-ils retirer des produits individuels d'une commande avec ce module ?**
    -   **R :** Non, le module gratuit "Bouton de Retour Gratuit - Retrait UE" est conçu uniquement pour le **retrait de commande complète**, conformément à la Directive européenne. Si vous avez besoin de gérer les retours partiels pour des produits individuels, vous auriez besoin d'un module de gestion des retours plus avancé.
-   **Q : Le module est installé, mais le texte du formulaire ou de l'e-mail est dans la mauvaise langue ou semble générique.**
    -   **R :** Les paramètres "Texte du formulaire de rétractation" et "Texte de l'e-mail de confirmation" sont des champs multilingues. Assurez-vous d'avoir saisi le texte souhaité pour chaque langue activée dans votre boutique. Vous pouvez basculer entre les langues à l'aide de l'icône de drapeau à côté de la zone de texte dans la configuration du module.
-   **Q : J'ai mis à jour le module, et maintenant quelque chose ne va pas. Que dois-je faire ?**
    -   **R :** Après toute mise à jour de module, il est recommandé de vider le cache de votre PrestaShop. Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache". Si le problème persiste, vérifiez les paramètres de configuration du module pour vous assurer qu'ils sont toujours tels que vous les attendez.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de la structure technique du module "Bouton de Retour Gratuit - Retrait UE", destinée aux développeurs et aux webmasters.

### 4.1 Aperçu de l'architecture
Le module suit un modèle MVC (Modèle-Vue-Contrôleur) PrestaShop standard. Il utilise `ModuleFrontController` pour les interactions front-office et `AdminController` pour la gestion back-office. `ObjectModel` est utilisé pour le stockage persistant des données liées aux demandes de rétractation. Les services clés et les classes d'assistance encapsulent la logique métier et assurent la compatibilité entre les versions de PrestaShop. Le module s'intègre à divers hooks PrestaShop pour afficher ses fonctionnalités.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office
Ces contrôleurs gèrent les interactions côté client liées aux demandes de rétractation.

-   `rbfree/controllers/front/confirm.php`
    *   Nom de la classe : `RbfConfirmModuleFrontController` (étend `RbfModuleFrontController`)
    *   Responsabilité : Affiche l'étape de confirmation finale du formulaire de rétractation, permettant au client de revoir et de soumettre sa demande. Gère la soumission POST pour créer une nouvelle entrée `RbfWithdrawal`.
-   `rbfree/controllers/front/form.php`
    *   Nom de la classe : `RbfFormModuleFrontController` (étend `RbfModuleFrontController`)
    *   Responsabilité : Rend le formulaire initial de demande de rétractation. Gère la validation des entrées pour la référence de commande, l'e-mail et les détails du client.
-   `rbfree/controllers/front/print.php`
    *   Nom de la classe : `RbfPrintModuleFrontController` (étend `RbfModuleFrontController`)
    *   Responsabilité : Fournit une version imprimable du formulaire de demande de rétractation, généralement après soumission, pour les dossiers du client.
-   `rbfree/controllers/front/RbfModuleFrontController.php`
    *   Nom de la classe : `RbfModuleFrontController` (étend `ModuleFrontController`)
    *   Responsabilité : Classe de base pour tous les contrôleurs front-office du module, fournissant des utilitaires communs, des vérifications de sécurité et des affectations de variables Smarty.
-   `rbfree/controllers/front/status.php`
    *   Nom de la classe : `RbfStatusModuleFrontController` (étend `RbfModuleFrontController`)
    *   Responsabilité : Affiche le statut actuel d'une demande de rétractation spécifique au client.
-   `rbfree/controllers/front/track.php`
    *   Nom de la classe : `RbfTrackModuleFrontController` (étend `RbfModuleFrontController`)
    *   Responsabilité : Permet aux clients (y compris les invités) de suivre leur demande de rétractation en saisissant une référence de commande et un e-mail.

#### Contrôleurs d'administration Back-Office
Ces contrôleurs gèrent l'interface d'administration des demandes de rétractation.

-   `rbfree/controllers/admin/AdminRbfWithdrawalController.php`
    *   Nom de la classe : `AdminRbfWithdrawalController` (étend `ModuleAdminController`)
    *   Nom de l'onglet : "Demandes de rétractation" (sous "Modules > Bouton de Retour Gratuit")
    *   Entité gérée : `RbfWithdrawal`
    *   Responsabilité : Fournit l'interface CRUD (Créer, Lire, Mettre à jour, Supprimer) pour la gestion des demandes de rétractation. Affiche une liste de demandes, permet de visualiser des informations détaillées, de mettre à jour le statut et d'ajouter des notes. Gère les soumissions de formulaires pour les changements de statut et les notes.

### 4.3 Classes et modèles principaux (`classes/`)

-   `rbfree/classes/RbfCompatibility.php`
    *   Nom de la classe : `RbfCompatibility`
    *   Responsabilité : Fournit des méthodes d'assistance pour assurer la compatibilité entre les différentes versions de PrestaShop (par exemple, gérer les différences dans les méthodes `Context` ou `Tools`).
-   `rbfree/classes/RbfSecurity.php`
    *   Nom de la classe : `RbfSecurity`
    *   Responsabilité : Contient des méthodes d'assistance liées à la sécurité, telles que la génération et la validation de jetons, pour protéger les formulaires contre les attaques CSRF.
-   `rbfree/classes/RbfSelfHeal.php`
    *   Nom de la classe : `RbfSelfHeal`
    *   Responsabilité : Implémente la logique d'auto-réparation ou de vérifications diagnostiques, assurant l'intégrité du module et la cohérence des données.
-   `rbfree/classes/RbfStatsService.php`
    *   Nom de la classe : `RbfStatsService`
    *   Responsabilité : Gère la collecte et la soumission de statistiques d'utilisation anonymes si activé par le marchand.
-   `rbfree/classes/RbfWithdrawal.php`
    *   Nom de la classe : `RbfWithdrawal` (étend `ObjectModel`)
    *   Table de base de données : `ps_rbf_withdrawal`
    *   Champs `$definition` : Définit la structure d'une demande de rétractation, y compris `id_order`, `id_customer`, `firstname`, `lastname`, `email`, `status`, `date_add`, `date_upd`, etc.
    *   Méthodes publiques clés : `add()`, `update()`, `delete()`, méthodes pour récupérer les détails de la rétractation, gérer les transitions de statut.
-   `rbfree/classes/RbfWithdrawalAttachment.php`
    *   Nom de la classe : `RbfWithdrawalAttachment` (étend `ObjectModel`)
    *   Table de base de données : `ps_rbf_withdrawal_attachment`
    *   Champs `$definition` : Stocke les informations sur les fichiers joints à une demande de rétractation (si la version Pro le prend en charge).
    *   Méthodes publiques clés : Méthodes pour gérer les pièces jointes.
-   `rbfree/classes/RbfWithdrawalHistory.php`
    *   Nom de la classe : `RbfWithdrawalHistory` (étend `ObjectModel`)
    *   Table de base de données : `ps_rbf_withdrawal_history`
    *   Champs `$definition` : Enregistre les modifications apportées au statut d'une demande de rétractation ou à d'autres attributs clés.
    *   Méthodes publiques clés : `add()`, méthodes pour récupérer l'historique.
-   `rbfree/classes/RbfWithdrawalNote.php`
    *   Nom de la classe : `RbfWithdrawalNote` (étend `ObjectModel`)
    *   Table de base de données : `ps_rbf_withdrawal_note`
    *   Champs `$definition` : Stocke les notes internes ajoutées par les administrateurs à une demande de rétractation.
    *   Méthodes publiques clés : `add()`, méthodes pour récupérer les notes.
-   `rbfree/classes/RbfWithdrawalProduct.php`
    *   Nom de la classe : `RbfWithdrawalProduct` (étend `ObjectModel`)
    *   Table de base de données : `ps_rbf_withdrawal_product`
    *   Champs `$definition` : Stocke les détails des produits inclus dans une demande de rétractation.
    *   Méthodes publiques clés : Méthodes pour gérer les produits associés.
-   `rbfree/classes/RbfWithdrawalService.php`
    *   Nom de la classe : `RbfWithdrawalService`
    *   Responsabilité : Encapsule la logique métier principale pour la gestion des demandes de rétractation, telles que la création de nouvelles demandes, la mise à jour des statuts de commande, l'envoi d'e-mails et la validation de l'éligibilité.

### 4.4 Actifs JavaScript (`views/js/`)

-   `rbfree/views/js/admin-order-state-picker.js`
    *   Portée : Back-office
    *   Détails : Gère la sélection interactive des états de commande dans la configuration du module, probablement pour les paramètres "États de commande pour l'éligibilité/confirmation/finalisation de la rétractation".
-   `rbfree/views/js/front.js`
    *   Portée : Front-office
    *   Détails : Contient le JavaScript général du front-office pour le module. Cela peut inclure la validation de formulaire, les soumissions AJAX pour les formulaires de rétractation, le chargement de contenu dynamique ou les interactions avec le bouton de rétractation.
-   `rbfree/views/js/order-history.js`
    *   Portée : Front-office (Compte client > Historique des commandes)
    *   Détails : Gère spécifiquement l'intégration du lien/bouton de rétractation dans la page d'historique des commandes du client, ajoutant potentiellement des écouteurs d'événements pour afficher/masquer dynamiquement les options en fonction du statut de la commande.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `rbfree/views/css/admin-config.css`
    *   Portée : Back-office (Configuration du module)
    *   Détails : Styles pour la page de configuration principale du module (`configure.tpl`), assurant une apparence cohérente dans l'administration de PrestaShop.
-   `rbfree/views/css/admin-dashboard.css`
    *   Portée : Back-office (Tableau de bord `AdminRbfWithdrawalController`)
    *   Détails : Style pour la vue du tableau de bord des demandes de rétractation, y compris les mises en page de tableau, les indicateurs de statut et la mise en page générale.
-   `rbfree/views/css/admin-order-state-picker.css`
    *   Portée : Back-office
    *   Détails : Styles pour l'interface de sélection de l'état de commande utilisée dans la configuration du module.
-   `rbfree/views/css/admin-pro-teaser.css`
    *   Portée : Back-office
    *   Détails : Style pour les éléments de teaser de la version "Pro" dans l'interface d'administration du module gratuit.
-   `rbfree/views/css/admin-searchtool.css`
    *   Portée : Back-office
    *   Détails : Styles pour les outils de recherche et de filtrage dans la liste d'administration des rétractations.
-   `rbfree/views/css/admin-withdrawal-view.css`
    *   Portée : Back-office (Vue `AdminRbfWithdrawalController`)
    *   Détails : Style pour la vue détaillée d'une seule demande de rétractation dans l'administration, y compris les notes, l'historique et les listes de produits.
-   `rbfree/views/css/front-classic.css`
    *   Portée : Front-office (Thème Classic)
    *   Détails : Ajustements de style spécifiques pour le thème Classic de PrestaShop, assurant une cohérence visuelle avec la conception du thème.
-   `rbfree/views/css/front-hummingbird.css`
    *   Portée : Front-office (Thème Hummingbird)
    *   Détails : Ajustements de style spécifiques pour le thème Hummingbird de PrestaShop, assurant une cohérence visuelle avec la conception du thème.
-   `rbfree/views/css/front.css`
    *   Portée : Front-office
    *   Détails : Style général du front-office pour les formulaires de rétractation, les boutons et les pages de statut, appliqué à tous les thèmes.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)
-   `rbfree/views/templates/hook/account-link-classic.tpl`
    *   Hook : `displayCustomerAccount` (ou similaire)
    *   Sorties : Un lien dans le tableau de bord du compte client pour le thème Classic.
-   `rbfree/views/templates/hook/account-link-hummingbird.tpl`
    *   Hook : `displayCustomerAccount` (ou similaire)
    *   Sorties : Un lien dans le tableau de bord du compte client pour le thème Hummingbird.
-   `rbfree/views/templates/hook/button-classic.tpl`
    *   Hook : `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (ou similaire)
    *   Sorties : Le bouton principal de rétractation pour le thème Classic.
-   `rbfree/views/templates/hook/button-hummingbird.tpl`
    *   Hook : `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (ou similaire)
    *   Sorties : Le bouton principal de rétractation pour le thème Hummingbird.
-   `rbfree/views/templates/hook/button.tpl`
    *   Hook : `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (ou similaire)
    *   Sorties : Bouton principal de rétractation générique, utilisé comme solution de repli ou pour les éléments communs.
-   `rbfree/views/templates/hook/order-detail-classic.tpl`
    *   Hook : `displayOrderDetail` (ou similaire)
    *   Sorties : Un lien/bouton de rétractation dans la page de détails de la commande pour le thème Classic.
-   `rbfree/views/templates/hook/order-detail-hummingbird.tpl`
    *   Hook : `displayOrderDetail` (ou similaire)
    *   Sorties : Un lien/bouton de rétractation dans la page de détails de la commande pour le thème Hummingbird.
-   `rbfree/views/templates/hook/order-detail.tpl`
    *   Hook : `displayOrderDetail` (ou similaire)
    *   Sorties : Lien/bouton de rétractation générique dans la page de détails de la commande.
-   `rbfree/views/templates/hook/order-withdrawal-notice.tpl`
    *   Hook : `displayAdminOrder` (ou similaire)
    *   Sorties : Une notification ou un résumé du statut de rétractation sur la page de visualisation de la commande dans le Back Office.

#### Modèles d'administration (`views/templates/admin/`)
-   `rbfree/views/templates/admin/configure.tpl`
    *   Utilisé par : `getContent()` dans `rbfree/index.php`
    *   Sorties : Le formulaire de configuration principal du module dans le Back Office.
-   `rbfree/views/templates/admin/dashboard.tpl`
    *   Utilisé par : `AdminRbfWithdrawalController`
    *   Sorties : La vue du tableau de bord listant toutes les demandes de rétractation.
-   `rbfree/views/templates/admin/order-state-picker.tpl`
    *   Utilisé par : Configuration du module
    *   Sorties : Le widget interactif de sélection de l'état de commande.
-   `rbfree/views/templates/admin/order-withdrawal-notice.tpl`
    *   Utilisé par : Hook `displayAdminOrder`
    *   Sorties : Une notification concernant le statut de rétractation sur la page de visualisation de la commande dans le Back Office.
-   `rbfree/views/templates/admin/pro-teaser-dashboard-intro.tpl`
    *   Utilisé par : `AdminRbfWithdrawalController`
    *   Sorties : Teaser d'introduction pour la version Pro sur le tableau de bord.
-   `rbfree/views/templates/admin/pro-teaser-dashboard.tpl`
    *   Utilisé par : `AdminRbfWithdrawalController`
    *   Sorties : Teaser général de la version Pro sur le tableau de bord.
-   `rbfree/views/templates/admin/pro-teaser-exclusions.tpl`
    *   Utilisé par : Configuration du module
    *   Sorties : Teaser pour les fonctionnalités de la version Pro liées aux exclusions.
-   `rbfree/views/templates/admin/pro-teaser-order-states.tpl`
    *   Utilisé par : Configuration du module
    *   Sorties : Teaser pour les fonctionnalités de la version Pro liées aux états de commande.
-   `rbfree/views/templates/admin/pro-teaser-withdrawal-scope.tpl`
    *   Utilisé par : Configuration du module
    *   Sorties : Teaser pour les fonctionnalités de la version Pro liées à la portée de la rétractation.
-   `rbfree/views/templates/admin/pro-teaser.tpl`
    *   Utilisé par : Diverses sections d'administration
    *   Sorties : Teaser générique de la version Pro.
-   `rbfree/views/templates/admin/updates.tpl`
    *   Utilisé par : Configuration du module
    *   Sorties : Affiche des informations sur les mises à jour du module.
-   `rbfree/views/templates/admin/view.tpl`
    *   Utilisé par : `AdminRbfWithdrawalController`
    *   Sorties : La page de vue détaillée pour une seule demande de rétractation dans le Back Office.

#### Modèles Front-office (`views/templates/front/`)
-   `rbfree/views/templates/front/confirm_step.tpl`
    *   Utilisé par : `RbfConfirmModuleFrontController`
    *   Sorties : La deuxième étape du formulaire de rétractation, pour confirmation.
-   `rbfree/views/templates/front/error.tpl`
    *   Utilisé par : Divers contrôleurs frontaux
    *   Sorties : Une page de message d'erreur générique.
-   `rbfree/views/templates/front/form.tpl`
    *   Utilisé par : `RbfFormModuleFrontController`
    *   Sorties : Le formulaire initial de demande de rétractation.
-   `rbfree/views/templates/front/print.tpl`
    *   Utilisé par : `RbfPrintModuleFrontController`
    *   Sorties : La version imprimable du formulaire de rétractation.
-   `rbfree/views/templates/front/status.tpl`
    *   Utilisé par : `RbfStatusModuleFrontController`
    *   Sorties : La page affichant le statut d'une demande de rétractation spécifique.
-   `rbfree/views/templates/front/success.tpl`
    *   Utilisé par : `RbfConfirmModuleFrontController`
    *   Sorties : Un message de succès après la soumission d'une demande de rétractation.
-   `rbfree/views/templates/front/track.tpl`
    *   Utilisé par : `RbfTrackModuleFrontController`
    *   Sorties : Le formulaire permettant aux clients de suivre leur demande de rétractation.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données
-   `ps_rbf_withdrawal` : Stocke les détails principaux de la demande de rétractation (id, id_order, id_customer, status, dates, infos client).
-   `ps_rbf_withdrawal_attachment` : Stocke les détails de toutes les pièces jointes à une demande de rétractation.
-   `ps_rbf_withdrawal_history` : Stocke un journal des changements de statut et d'autres mises à jour pour chaque demande de rétractation.
-   `ps_rbf_withdrawal_note` : Stocke les notes internes ajoutées par les administrateurs à une demande de rétractation.
-   `ps_rbf_withdrawal_product` : Stocke les détails des produits inclus dans une demande de rétractation.
-   `ps_configuration` : Les paramètres du module sont stockés ici avec des clés comme `RBFREE_ENABLED`, `RBFREE_BUTTON_HOOK`, `RBFREE_ALLOW_GUEST`, etc.

#### Tableau des hooks enregistrés

| Nom du Hook | Moment d'exécution | Objectif technique |
|---|---|---|
| `displayHeader` | Dans la section `<head>` de chaque page. | Injecter CSS/JS, ou rendre le bouton de rétractation si configuré. |
| `displayLeftColumn` | Dans la barre latérale gauche des pages applicables. | Rendre le bouton de rétractation si configuré. |
| `displayRightColumn` | Dans la barre latérale droite des pages applicables. | Rendre le bouton de rétractation si configuré. |
| `displayFooter` | Dans la section du pied de page de chaque page. | Rendre le bouton de rétractation si configuré. |
| `displayProductButtons` | Sur la page produit, près du bouton "ajouter au panier". | Rendre le bouton de rétractation si configuré. |
| `displayCustomerAccount` | Dans le tableau de bord "Mon compte" du client. | Ajouter un lien vers le formulaire de rétractation. |
| `displayOrderDetail` | Sur la page de détails de la commande du client. | Ajouter un lien/bouton pour initier la rétractation pour cette commande spécifique. |
| `displayAdminOrder` | Sur la page de visualisation de la commande du Back Office. | Afficher une notification ou un résumé de toute demande de rétractation associée. |
| `actionOrderStatusUpdate` | Lorsqu'un statut de commande est modifié. | Potentiellement déclencher des actions comme la mise à jour du statut de rétractation ou l'envoi de notifications. |
| `actionFrontControllerSetMedia` | Avant qu'un contrôleur frontal ne rende son modèle. | Mettre en file d'attente les fichiers CSS et JavaScript du front-office. |
| `actionAdminControllerSetMedia` | Avant qu'un contrôleur d'administration ne rende son modèle. | Mettre en file d'attente les fichiers CSS et JavaScript du back-office. |
| `actionModuleInstall` | Lors de l'installation du module. | Créer des tables de base de données, définir la configuration par défaut. |
| `actionModuleUninstall` | Lors de la désinstallation du module. | Supprimer les tables de base de données, supprimer la configuration. |

## 5. Support officiel et mises à jour
Pour les dernières mises à jour, corrections de bugs et support officiel du module "Bouton de Retour Gratuit - Retrait UE", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question que vous pourriez avoir concernant la fonctionnalité du module.
