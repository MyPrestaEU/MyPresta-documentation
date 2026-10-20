---
title: "Bouton de retour UE – Formulaire de rétractation en ligne - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Bouton de retour UE – Formulaire de rétractation en ligne' par MyPresta.eu."
sidebar:
  label: "Bouton de retour UE – Formulaire de rétractation en ligne - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module EU Return Button – Online Withdrawal Form sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/eu-return-button-online-withdrawal-form.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/eu-return-button-online-withdrawal-form/)
>
> ---


# Bouton de retour UE – Formulaire de rétractation en ligne

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises, qui sont généralement disponibles sur la plupart des environnements d'hébergement modernes.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal où vous contrôlez le comportement général et l'apparence du bouton de retour et du formulaire.

#### Onglet Paramètres généraux

- **Activer le module :**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour l'ensemble du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le bouton de retour et le formulaire de rétractation en ligne deviennent actifs et visibles pour les clients selon vos autres paramètres.
    - *Lorsqu'il est désactivé :* Le module est complètement désactivé. Le bouton n'apparaîtra pas et les formulaires ne seront pas accessibles.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** Vous ne le désactiveriez que si vous souhaitez temporairement arrêter d'offrir des retours en ligne, peut-être pendant une maintenance ou un changement de politique.
- **Afficher le bouton de retour dans :**

  - **Ce que fait ce paramètre :** Détermine où le bouton principal « Retour » ou « Rétractation » apparaîtra sur le front-office de votre boutique. Vous pouvez sélectionner plusieurs emplacements.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est sélectionné (par exemple, En-tête) :* Un bouton apparaîtra à l'emplacement choisi, fournissant un lien direct vers le formulaire de retour.
    - *Lorsqu'il est désélectionné :* Le bouton n'apparaîtra pas à cet emplacement spécifique.
  - **Valeur recommandée :** En-tête et/ou Pied de page pour un accès facile, et Page produit pour informer les clients à l'avance.
  - **Scénario / exemple de marchand :** Si vous souhaitez que les clients trouvent facilement l'option de retour depuis n'importe quelle page, activez « En-tête » et « Pied de page ». Si vous souhaitez mettre l'accent sur votre politique de retour sur les pages produits, activez « Page produit ».
- **Texte du bouton :**

  - **Ce que fait ce paramètre :** Vous permet de personnaliser le texte affiché sur le bouton de retour.
  - **Effet de la modification de ce paramètre :** Le texte sur le bouton changera pour la valeur que vous avez spécifiée.
  - **Valeur recommandée :** « Demande de retour », « Formulaire de rétractation en ligne » ou « Démarrer un retour ».
  - **Scénario / exemple de marchand :** Vous pourriez le changer de « Retour » à « Formulaire de rétractation » pour l'aligner sur la terminologie légale spécifique de votre région.
- **Statut de commande minimum pour la rétractation :**

  - **Ce que fait ce paramètre :** Définit le statut de commande le plus ancien à partir duquel un client peut initier une demande de retour pour une commande. Les commandes avec un statut inférieur à celui-ci ne seront pas éligibles.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur « Paiement accepté » :* Les clients ne peuvent demander un retour qu'une fois leur paiement traité avec succès.
    - *Lorsqu'il est défini sur « Expédié » :* Les clients ne peuvent demander un retour qu'après que leur commande a été marquée comme expédiée.
  - **Valeur recommandée :** « Paiement accepté » ou « Expédié », selon votre politique.
  - **Scénario / exemple de marchand :** Si vous n'acceptez les retours que pour les articles qui ont effectivement été payés et traités, définissez-le sur « Paiement accepté ». Si vous n'acceptez les retours que pour les articles qui ont déjà quitté votre entrepôt, définissez-le sur « Expédié ».
- **Nombre maximal de jours pour la rétractation :**

  - **Ce que fait ce paramètre :** Définit le nombre maximal de jours après qu'une commande a été passée (ou expédiée, selon votre politique) pendant lesquels un client peut soumettre une demande de retour.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur 14 :* Les clients ont 14 jours à compter de la date de commande pour demander un retour. Après 14 jours, l'option ne sera plus disponible pour cette commande.
    - *Lorsqu'il est défini sur 30 :* Les clients ont 30 jours.
  - **Valeur recommandée :** 14 (pour la conformité standard de l'UE) ou 30 (si vous offrez une période de retour prolongée).
  - **Scénario / exemple de marchand :** Pour se conformer au droit de rétractation standard de 14 jours de l'UE, définissez-le sur 14. Si vous offrez une politique plus généreuse, vous pouvez l'étendre à 30 jours ou plus.
- **Autoriser les rétractations des invités :**

  - **Ce que fait ce paramètre :** Détermine si les clients qui ont passé commande en tant qu'invités (sans créer de compte) peuvent utiliser le formulaire de rétractation en ligne.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clients invités peuvent accéder au formulaire en fournissant leur référence de commande et leur adresse e-mail.
    - *Lorsqu'il est désactivé :* Seuls les clients enregistrés et connectés peuvent initier un retour.
  - **Valeur recommandée :** OUI (pour un maximum de commodité pour le client et de conformité avec l'UE).
  - **Scénario / exemple de marchand :** L'activation de cette option garantit que tous les clients, quelle que soit leur méthode de paiement, peuvent facilement initier un retour, ce qui est crucial pour la conformité et la satisfaction du client.
- **Autoriser les pièces jointes :**

  - **Ce que fait ce paramètre :** Permet aux clients de télécharger des fichiers (par exemple, des photos de produits endommagés, une preuve d'achat) lors de la soumission de leur demande de retour.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un champ de téléchargement apparaîtra sur le formulaire.
    - *Lorsqu'il est désactivé :* Les clients ne peuvent pas télécharger de fichiers.
  - **Valeur recommandée :** OUI (surtout pour les produits où une preuve visuelle pourrait être nécessaire pour les dommages ou les défauts).
  - **Scénario / exemple de marchand :** Si vous vendez des articles fragiles, autoriser les pièces jointes aide les clients à fournir rapidement des preuves de dommages, accélérant ainsi le processus de résolution.
- **Taille maximale des pièces jointes (Mo) :**

  - **Ce que fait ce paramètre :** Définit la taille maximale de chaque fichier que le client peut télécharger.
  - **Effet de la modification de ce paramètre :** Les fichiers plus grands que cette limite seront rejetés par le formulaire.
  - **Valeur recommandée :** 2-5 Mo.
  - **Scénario / exemple de marchand :** Définir une limite raisonnable empêche les clients de télécharger des fichiers excessivement volumineux qui pourraient ralentir votre serveur ou votre système de messagerie.
- **Extensions de pièces jointes autorisées (séparées par des virgules) :**

  - **Ce que fait ce paramètre :** Spécifie les types de fichiers (par exemple, jpg, png, pdf) que les clients sont autorisés à télécharger.
  - **Effet de la modification de ce paramètre :** Seuls les fichiers avec ces extensions seront acceptés.
  - **Valeur recommandée :** jpg, jpeg, png, gif, pdf.
  - **Scénario / exemple de marchand :** Limiter aux formats d'image et de document courants garantit que vous recevez des fichiers utilisables et empêche les téléchargements malveillants.
- **Exiger un message de statut :**

  - **Ce que fait ce paramètre :** Lorsque vous modifiez le statut d'une demande de retour dans le back-office, ce paramètre détermine si vous êtes tenu d'ajouter un message au client.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un champ de saisie pour un message sera obligatoire lors de la mise à jour d'un statut de retour.
    - *Lorsqu'il est désactivé :* Vous pouvez modifier les statuts sans ajouter de message.
  - **Valeur recommandée :** OUI (pour une communication claire et des pistes d'audit).
  - **Scénario / exemple de marchand :** L'activation de cette option garantit que votre équipe fournit toujours une raison ou une mise à jour au client lors du changement de statut, améliorant la transparence.

#### Onglet États de commande

Cet onglet vous permet de définir les différents statuts des demandes de retour et la manière dont ils interagissent avec vos statuts de commande PrestaShop existants.

- **Nouveau statut de rétractation :**

  - **Ce que fait ce paramètre :** Sélectionne le statut de commande PrestaShop qui sera attribué à une nouvelle demande de retour lorsqu'elle est soumise pour la première fois par un client.
  - **Effet de la modification de ce paramètre :** Toutes les nouvelles demandes de retour seront automatiquement marquées avec ce statut dans votre back-office.
  - **Valeur recommandée :** Créez un nouveau statut de commande personnalisé comme « Retour demandé » ou « Rétractation en attente » pour une identification claire.
  - **Scénario / exemple de marchand :** En créant un statut spécifique « Retour demandé », votre équipe de service client peut facilement filtrer et identifier les nouvelles demandes de retour qui nécessitent leur attention.
- **Statut de rétractation accepté :**

  - **Ce que fait ce paramètre :** Sélectionne le statut de commande PrestaShop qui sera attribué lorsque vous, en tant que marchand, acceptez la demande de retour d'un client.
  - **Effet de la modification de ce paramètre :** Lorsque vous marquez un retour comme « Accepté » dans le module, son statut passera à ce statut de commande sélectionné.
  - **Valeur recommandée :** Créez un nouveau statut de commande personnalisé comme « Retour accepté » ou « Rétractation approuvée ».
  - **Scénario / exemple de marchand :** Une fois que vous avez examiné une demande et l'avez approuvée, changer son statut en « Retour accepté » peut déclencher l'envoi d'un e-mail au client avec des instructions supplémentaires.
- **Statut de rétractation refusé :**

  - **Ce que fait ce paramètre :** Sélectionne le statut de commande PrestaShop qui sera attribué lorsque vous refusez la demande de retour d'un client.
  - **Effet de la modification de ce paramètre :** Lorsque vous marquez un retour comme « Refusé » dans le module, son statut passera à ce statut de commande sélectionné.
  - **Valeur recommandée :** Créez un nouveau statut de commande personnalisé comme « Retour refusé » ou « Rétractation rejetée ».
  - **Scénario / exemple de marchand :** Si une demande de retour ne respecte pas votre politique (par exemple, hors délai de retour), vous changeriez son statut en « Retour refusé » et enverriez idéalement un message expliquant pourquoi.
- **Statut de rétractation clôturé :**

  - **Ce que fait ce paramètre :** Sélectionne le statut de commande PrestaShop qui sera attribué lorsqu'une demande de retour est terminée ou résolue (par exemple, remboursement émis, remplacement envoyé).
  - **Effet de la modification de ce paramètre :** Lorsque vous marquez un retour comme « Clôturé » dans le module, son statut passera à ce statut de commande sélectionné.
  - **Valeur recommandée :** Créez un nouveau statut de commande personnalisé comme « Retour terminé » ou « Rétractation clôturée ».
  - **Scénario / exemple de marchand :** Une fois qu'un remboursement a été traité, marquer le retour comme « Retour terminé » fournit une piste d'audit claire et le supprime de votre file d'attente de retours actifs.
- **États de commande à exclure de la rétractation :**

  - **Ce que fait ce paramètre :** Vous permet de sélectionner des statuts de commande PrestaShop spécifiques pour lesquels les clients *ne peuvent pas* initier une demande de retour, même s'ils remplissent d'autres critères.
  - **Effet de la modification de ce paramètre :** Les commandes avec l'un des statuts sélectionnés n'afficheront pas l'option de retour au client.
  - **Valeur recommandée :** « Annulé », « Remboursé » ou tout autre statut qui signifie qu'une commande n'est plus éligible à une nouvelle demande de retour.
  - **Scénario / exemple de marchand :** Si une commande a déjà été « Remboursée », vous ne voudriez pas qu'un client puisse soumettre une autre demande de retour pour celle-ci.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### Demandes de rétractation (Back Office > Commandes > Demandes de rétractation)

C'est le centre de gestion de toutes les demandes de retour et de rétractation soumises par vos clients.

- **Nom de l'écran et emplacement du menu :** Vous pouvez trouver cet écran en naviguant vers **Commandes > Demandes de rétractation** dans le menu de votre back-office PrestaShop.
- **Actions et paramètres disponibles :**
  - **Tableau de liste :** Affiche une liste complète de toutes les demandes de retour, y compris :
    - **ID :** Identifiant unique de la demande.
    - **Nom du client :** Le client qui a soumis la demande.
    - **Référence de commande :** La commande PrestaShop associée.
    - **Date :** Date de soumission de la demande.
    - **Statut :** Le statut actuel de la demande (par exemple, « Retour demandé », « Retour accepté »).
    - **Actions :** Boutons pour « Afficher » les détails de la demande, modifier son statut ou effectuer d'autres tâches de gestion.
  - **Filtrage et recherche :** Vous pouvez filtrer la liste par statut, client, référence de commande et plage de dates pour trouver rapidement des demandes spécifiques.
  - **Actions en masse :** Vous permet de sélectionner plusieurs demandes et d'effectuer des actions comme changer leur statut simultanément.
  - **Afficher les détails :** Cliquer sur « Afficher » pour une demande spécifique ouvre une page détaillée où vous pouvez :
    - Voir toutes les informations fournies par le client (raison, commentaires, fichiers joints).
    - Examiner les produits inclus dans la demande de retour.
    - Afficher un historique des changements de statut et des notes internes.
    - Ajouter des notes privées pour la communication interne de l'équipe.
    - Changer le statut de la demande (par exemple, de « Retour demandé » à « Retour accepté »).
    - Envoyer des messages au client (si « Exiger un message de statut » est activé).
    - Télécharger les pièces jointes.
    - Imprimer le formulaire de rétractation.
- **Effet des modifications :**
  - **Changement de statut :** Met à jour le statut de la demande de retour, ce qui peut déclencher des notifications par e-mail au client et mettre à jour l'affichage dans son compte client.
  - **Ajout de notes :** Enregistre la communication interne ou les décisions liées à la demande, visible uniquement par les utilisateurs du back-office.
  - **Envoi de messages :** Communique directement avec le client concernant sa demande de retour.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Vérifiez régulièrement la liste « Demandes de rétractation » pour les nouvelles demandes (statut « Retour demandé »).
  2. Examinez chaque nouvelle demande, en vérifiant les détails de la commande, les commentaires du client et les pièces jointes.
  3. Décidez d'accepter ou de refuser la demande en fonction de la politique de retour de votre boutique.
  4. Changez le statut en conséquence (par exemple, en « Retour accepté » ou « Retour refusé »). Si « Exiger un message de statut » est activé, fournissez un message clair au client.
  5. Suivez les étapes suivantes (par exemple, émettre un remboursement, organiser l'expédition de retour) et mettez à jour le statut en « Retour terminé » une fois résolu.
  6. Utilisez les notes internes pour la communication d'équipe ou pour enregistrer les actions spécifiques entreprises.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Activer le module | OUI | Active/désactive l'ensemble du module. |
|  | Afficher le bouton de retour dans | En-tête, Pied de page, Page produit | Contrôle où le bouton de retour apparaît sur le front-office. |
|  | Texte du bouton | « Demande de retour » | Personnalise le texte sur le bouton de retour. |
|  | Statut de commande minimum pour la rétractation | « Paiement accepté » | Définit le statut de commande le plus ancien pour l'éligibilité au retour. |
|  | Nombre maximal de jours pour la rétractation | 14 | Définit la fenêtre de retour en jours à partir de la date de commande. |
|  | Autoriser les rétractations des invités | OUI | Permet aux clients non enregistrés d'utiliser le formulaire. |
|  | Autoriser les pièces jointes | OUI | Active/désactive le téléchargement de fichiers sur le formulaire. |
|  | Taille maximale des pièces jointes (Mo) | 2-5 Mo | Définit la taille maximale des fichiers téléchargés. |
|  | Extensions de pièces jointes autorisées | jpg, jpeg, png, gif, pdf | Spécifie les types de fichiers autorisés pour les téléchargements. |
|  | Exiger un message de statut | OUI | Rend un message obligatoire lors du changement de statut de retour. |
| **Onglet États de commande** | Nouveau statut de rétractation | « Retour demandé » (personnalisé) | Statut pour les demandes nouvellement soumises. |
|  | Statut de rétractation accepté | « Retour accepté » (personnalisé) | Statut lorsque le marchand approuve une demande. |
|  | Statut de rétractation refusé | « Retour refusé » (personnalisé) | Statut lorsque le marchand rejette une demande. |
|  | Statut de rétractation clôturé | « Retour terminé » (personnalisé) | Statut lorsqu'une demande est entièrement résolue. |
|  | États de commande à exclure de la rétractation | « Annulé », « Remboursé » | Empêche les retours pour les commandes avec ces statuts. |
| **Demandes de rétractation (Admin)** | Afficher/Modifier la demande | N/A | Gérer les demandes de retour individuelles, changer le statut, ajouter des notes. |
|  | Filtrer/Rechercher | N/A | Localiser des demandes spécifiques par divers critères. |
|  | Actions en masse | N/A | Effectuer des actions sur plusieurs demandes sélectionnées. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Le bouton de retour n'apparaît pas sur ma boutique. Que dois-je faire ?**
R1 :

- **Vérifier le statut du module :** Allez dans **Modules > Gestionnaire de modules**, trouvez « Bouton de retour UE – Formulaire de rétractation en ligne » et assurez-vous qu'il est « Activé ».
- **Vérifier les emplacements d'affichage :** Dans la configuration du module, sous l'onglet « Paramètres généraux », vérifiez que vous avez sélectionné au moins un emplacement « Afficher le bouton de retour dans » (par exemple, En-tête, Pied de page).
- **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures). Parfois, un ancien contenu mis en cache empêche l'apparition de nouveaux éléments de module.
- **Compatibilité du thème :** Bien que le module soit conçu pour une large compatibilité, les thèmes personnalisés peuvent nécessiter des ajustements mineurs. Si le bouton n'apparaît toujours pas, contactez le support MyPresta.eu avec les détails de votre thème.

**Q2 : Des clients signalent qu'ils ne peuvent pas soumettre de retour pour une commande spécifique, même si elle est dans la période de retour.**
R2 :

- **Vérifier le statut de commande minimum :** Dans la configuration du module, sous « Paramètres généraux », examinez « Statut de commande minimum pour la rétractation ». Assurez-vous que la commande du client a atteint ce statut. Par exemple, s'il est défini sur « Expédié » et que la commande est toujours « Paiement accepté », ils ne verront pas l'option.
- **Vérifier les états de commande exclus :** Dans la configuration du module, sous l'onglet « États de commande », vérifiez « États de commande à exclure de la rétractation ». Si la commande du client a l'un de ces statuts (par exemple, « Annulé », « Remboursé »), il ne pourra pas initier un nouveau retour.
- **Nombre maximal de jours pour la rétractation :** Vérifiez à nouveau le paramètre « Nombre maximal de jours pour la rétractation ». La fenêtre de retour pourrait avoir expiré pour cette commande spécifique.

**Q3 : J'ai modifié un paramètre, mais il n'est pas reflété sur le front-office.**
R3 :

- **Vider le cache :** C'est la raison la plus courante. Videz toujours votre cache PrestaShop après avoir effectué des modifications de configuration dans n'importe quel module. Naviguez vers **Paramètres avancés > Performances** et cliquez sur « Vider le cache ». Si vous utilisez un module de mise en cache tiers ou un CDN, videz également leurs caches.
- **Cache du navigateur :** Demandez à vos clients (ou à vous-même) de vider leur cache de navigateur ou essayez d'afficher la page dans une fenêtre incognito/privée pour exclure les problèmes de mise en cache côté navigateur.

**Q4 : Comment traduire le texte du module dans d'autres langues ?**
R4 :

- Allez dans **International > Traductions** dans votre back-office PrestaShop.
- Sélectionnez « Traductions des modules installés ».
- Choisissez votre thème, la langue que vous souhaitez traduire, puis sélectionnez « Bouton de retour UE – Formulaire de rétractation en ligne » dans la liste des modules.
- Vous verrez alors une liste de toutes les chaînes traduisibles dans le module, y compris le texte du bouton, les étiquettes de formulaire et les messages. Saisissez vos traductions et enregistrez.

**Q5 : Je souhaite personnaliser l'apparence du formulaire de retour pour qu'il corresponde à mon thème.**
R5 :

- Le module comprend des fichiers CSS (`front-classic.css`, `front-hummingbird.css`, `front.css`) conçus pour les thèmes PrestaShop courants.
- Pour un style avancé, vous aurez besoin d'un développeur web. Il pourra inspecter la structure HTML du module et remplacer ses règles CSS dans le fichier `custom.css` de votre thème ou en créant une nouvelle feuille de style qui se charge après le CSS du module. Évitez de modifier directement les fichiers CSS du module, car vos modifications seraient perdues lors des mises à jour.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Bouton de retour UE – Formulaire de rétractation en ligne » (`rbpro`) suit l'architecture MVC (Modèle-Vue-Contrôleur) standard de PrestaShop. Il utilise `ModuleFrontController` pour les interactions côté client et `AdminController` pour la gestion du back-office. La logique métier principale est encapsulée dans des classes de service et ObjectModel dédiées, garantissant l'intégrité des données et la séparation des préoccupations. Le module s'intègre au système de hooks de PrestaShop pour l'injection de contenu dynamique et utilise Smarty pour le templating. Il comprend également des couches de compatibilité pour différentes versions de PrestaShop et une classe de sécurité pour la validation des entrées.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs gèrent les interactions client liées au formulaire de retour et au suivi du statut.

- `rbpro/controllers/front/confirm.php`

  - **Nom de la classe :** `RbpConfirmModuleFrontController` (étend `RbpModuleFrontController`)
  - **Responsabilité :** Affiche l'étape de confirmation finale du formulaire de rétractation. Traite les données du formulaire soumis, crée l'entrée `RbpWithdrawal` et redirige vers la page de succès ou d'erreur. Gère la validation des données avant l'enregistrement.
- `rbpro/controllers/front/form.php`

  - **Nom de la classe :** `RbpFormModuleFrontController` (étend `RbpModuleFrontController`)
  - **Responsabilité :** Rend le formulaire principal de rétractation en ligne. Gère l'affichage initial des commandes/produits éligibles, traite les sélections de l'utilisateur et prépare les données pour l'étape de confirmation. Gère l'accès des invités via la référence de commande et l'e-mail.
- `rbpro/controllers/front/print.php`

  - **Nom de la classe :** `RbpPrintModuleFrontController` (étend `RbpModuleFrontController`)
  - **Responsabilité :** Fournit une version imprimable du formulaire de rétractation ou des détails de la demande. Généralement utilisé par les clients pour l'inclure avec leur colis retourné.
- `rbpro/controllers/front/RbpModuleFrontController.php`

  - **Nom de la classe :** `RbpModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** C'est une classe de base pour tous les contrôleurs front-office du module `rbpro`. Elle fournit des fonctionnalités communes comme la configuration des fils d'Ariane, la gestion des actifs spécifiques au module et potentiellement des vérifications de sécurité partagées ou l'initialisation des données.
- `rbpro/controllers/front/status.php`

  - **Nom de la classe :** `RbpStatusModuleFrontController` (étend `RbpModuleFrontController`)
  - **Responsabilité :** Affiche le statut actuel et l'historique d'une demande de retour spécifique au client. Accessible via un lien de suivi unique ou depuis le compte du client.
- `rbpro/controllers/front/track.php`

  - **Nom de la classe :** `RbpTrackModuleFrontController` (étend `RbpModuleFrontController`)
  - **Responsabilité :** Fournit une interface simple permettant aux clients (en particulier les invités) de saisir une référence de commande et un e-mail pour suivre le statut de leur demande de rétractation.

#### Contrôleurs d'administration Back-Office

- `rbpro/controllers/admin/AdminRbpWithdrawalController.php`
  - **Nom de la classe :** `AdminRbpWithdrawalController` (étend `ModuleAdminController`)
  - **Nom de l'onglet :** « Demandes de rétractation » (sous « Commandes »)
  - **Entité gérée :** `RbpWithdrawal`
  - **Responsabilité :** Gère la liste, la visualisation, l'édition et les mises à jour de statut de toutes les demandes de rétractation des clients dans le back-office de PrestaShop. Implémente `renderList()` pour le tableau d'aperçu et `renderForm()` pour la vue détaillée d'une seule demande. Gère les actions comme le changement de statut, l'ajout de notes et la gestion des pièces jointes.

### 4.3 Classes et modèles principaux (`classes/`)

- `rbpro/classes/index.php`

  - **Responsabilité :** Fichier `index.php` vide standard pour empêcher l'affichage du répertoire.
- `rbpro/classes/RbpCompatibility.php`

  - **Responsabilité :** Fournit des méthodes statiques pour gérer les problèmes de compatibilité entre les différentes versions de PrestaShop (par exemple, logique spécifique à `_PS_VERSION_`, remplacements de fonctions obsolètes). Garantit que le module fonctionne correctement de PS 1.6 à 9.x.
- `rbpro/classes/RbpSecurity.php`

  - **Responsabilité :** Contient des méthodes statiques pour les tâches liées à la sécurité, telles que la validation des entrées, la désinfection et potentiellement la génération/vérification de jetons CSRF pour les formulaires spécifiques au module.
- `rbpro/classes/RbpStatsService.php`

  - **Responsabilité :** Une classe de service responsable de la collecte et potentiellement du traitement des statistiques liées aux demandes de rétractation (par exemple, nombre de demandes, temps de traitement moyen).
- `rbpro/classes/RbpWithdrawal.php`

  - **Étend :** `ObjectModel`
  - **Table de base de données :** `rbp_withdrawal`
  - **Champs `$definition` :** Définit la structure d'une demande de rétractation, y compris des champs comme `id_customer`, `id_order`, `id_order_state`, `reference`, `email`, `date_add`, `date_upd`, `status`, `reason`, `message`, etc.
  - **Méthodes publiques clés :** Méthodes pour les opérations CRUD sur les demandes de rétractation, la récupération des produits associés, l'historique et les notes.
- `rbpro/classes/RbpWithdrawalAttachment.php`

  - **Étend :** `ObjectModel`
  - **Table de base de données :** `rbp_withdrawal_attachment`
  - **Champs `$definition` :** Définit la structure des pièces jointes liées à une demande de rétractation, y compris `id_rbp_withdrawal`, `filename`, `original_filename`, `mime_type`, `date_add`.
  - **Méthodes publiques clés :** Méthodes pour la gestion des fichiers joints (téléchargement, récupération, suppression).
- `rbpro/classes/RbpWithdrawalHistory.php`

  - **Étend :** `ObjectModel`
  - **Table de base de données :** `rbp_withdrawal_history`
  - **Champs `$definition` :** Définit l'historique des changements de statut pour une demande de rétractation, y compris `id_rbp_withdrawal`, `id_order_state`, `id_employee`, `message`, `date_add`.
  - **Méthodes publiques clés :** Méthodes pour l'enregistrement et la récupération des changements de statut et des messages associés.
- `rbpro/classes/RbpWithdrawalNote.php`

  - **Étend :** `ObjectModel`
  - **Table de base de données :** `rbp_withdrawal_note`
  - **Champs `$definition` :** Définit les notes internes ajoutées par les employés à une demande de rétractation, y compris `id_rbp_withdrawal`, `id_employee`, `note`, `date_add`.
  - **Méthodes publiques clés :** Méthodes pour l'ajout et la récupération des notes internes.
- `rbpro/classes/RbpWithdrawalProduct.php`

  - **Étend :** `ObjectModel`
  - **Table de base de données :** `rbp_withdrawal_product`
  - **Champs `$definition` :** Définit les produits spécifiques inclus dans une demande de rétractation, en les liant à `id_rbp_withdrawal`, `id_order_detail`, `id_product`, `id_product_attribute`, `quantity`, `reason`.
  - **Méthodes publiques clés :** Méthodes pour la gestion de la liste des produits dans une demande de retour.
- `rbpro/classes/RbpWithdrawalService.php`

  - **Responsabilité :** Une classe de couche de service qui orchestre la logique métier complexe impliquant plusieurs ObjectModels liés à `RbpWithdrawal`. Des exemples incluent la création d'une nouvelle demande de rétractation (qui implique `RbpWithdrawal`, `RbpWithdrawalProduct`, `RbpWithdrawalHistory`), la mise à jour de son statut, l'envoi de notifications par e-mail et la gestion des pièces jointes.

### 4.4 Actifs JavaScript (`views/js/`)

- `rbpro/lib/searchTool/views/js/autocomplete.js`

  - **Portée :** Back-office (probablement pour la recherche de commandes/clients dans les formulaires d'administration).
  - **Détails :** Implémente la fonctionnalité d'autocomplétion pour les champs de saisie, généralement pour la recherche de clients ou de commandes lors de la création/modification manuelle de demandes de rétractation dans le back-office. Se lie aux événements `keyup` et effectue des appels AJAX pour récupérer des suggestions.
- `rbpro/views/js/admin-order-state-picker.js`

  - **Portée :** Back-office (configuration du module et `AdminRbpWithdrawalController`).
  - **Détails :** Améliore les listes déroulantes de sélection d'état de commande dans la configuration du module et potentiellement dans la vue détaillée de la rétractation. Peut ajouter des repères visuels ou des capacités de filtrage.
- `rbpro/views/js/front.js`

  - **Portée :** Front-office (formulaires de rétractation et pages de statut).
  - **Détails :** Gère les interactions côté client sur le formulaire de rétractation, telles que :
    - Sélection dynamique des produits en fonction de la commande.
    - Validation des champs du formulaire avant soumission.
    - Appels AJAX pour la soumission du formulaire ou le chargement des données.
    - Affichage des messages ou gestion des téléchargements de fichiers.
- `rbpro/views/js/order-history.js`

  - **Portée :** Front-office (compte client > historique des commandes).
  - **Détails :** Intègre le bouton ou le lien « Demander un retour » dans la page d'historique des commandes du client. Peut utiliser AJAX pour vérifier l'éligibilité de la commande ou afficher/masquer dynamiquement le bouton.

### 4.5 Feuilles de style CSS (`views/css/`)

- `rbpro/lib/searchTool/views/css/autocomplete.css`

  - **Portée :** Back-office.
  - **Détails :** Styles pour les listes déroulantes d'autocomplétion et les champs de saisie de recherche utilisés dans le panneau d'administration.
- `rbpro/views/css/admin-config.css`

  - **Portée :** Back-office (page de configuration du module).
  - **Détails :** Styles pour le formulaire de configuration principal du module, y compris les onglets, les champs de saisie et la mise en page générale.
- `rbpro/views/css/admin-dashboard.css`

  - **Portée :** Back-office (potentiellement pour un tableau de bord de module ou une vue de statistiques).
  - **Détails :** Styles pour tous les éléments de tableau de bord personnalisés ou les affichages statistiques au sein de l'interface d'administration du module.
- `rbpro/views/css/admin-order-state-picker.css`

  - **Portée :** Back-office.
  - **Détails :** Styles spécifiques pour les éléments de sélection d'état de commande améliorés dans l'administration.
- `rbpro/views/css/admin-searchtool.css`

  - **Portée :** Back-office.
  - **Détails :** Styles généraux pour les outils de recherche et les composants de filtrage au sein de l'interface d'administration.
- `rbpro/views/css/admin-withdrawal-view.css`

  - **Portée :** Back-office (vue détaillée de `AdminRbpWithdrawalController`).
  - **Détails :** Styles pour la vue détaillée d'une seule demande de rétractation, y compris les sections pour les informations client, les produits, l'historique et les notes.
- `rbpro/views/css/front-classic.css`

  - **Portée :** Front-office (pour la compatibilité avec le thème Classic).
  - **Détails :** Ajustements de style spécifiques pour le formulaire de rétractation et les boutons afin de s'intégrer parfaitement au thème Classic de PrestaShop.
- `rbpro/views/css/front-hummingbird.css`

  - **Portée :** Front-office (pour la compatibilité avec le thème Hummingbird).
  - **Détails :** Ajustements de style spécifiques pour le formulaire de rétractation et les boutons afin de s'intégrer parfaitement au thème Hummingbird de PrestaShop.
- `rbpro/views/css/front.css`

  - **Portée :** Front-office (style général).
  - **Détails :** CSS de base pour le formulaire de rétractation, les boutons et les pages de statut du front-office, fournissant un style de base qui peut être remplacé par des feuilles de style spécifiques au thème.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

Ces templates sont rendus lorsque le module est accroché à des points d'affichage spécifiques.

- `rbpro/views/templates/hook/account-link-classic.tpl`

  - **Hook :** `displayCustomerAccount` (ou similaire)
  - **Sorties :** Un lien dans la section « Mon compte » du client pour le thème Classic, menant au formulaire de rétractation ou à la page de suivi.
- `rbpro/views/templates/hook/account-link-hummingbird.tpl`

  - **Hook :** `displayCustomerAccount` (ou similaire)
  - **Sorties :** Un lien dans la section « Mon compte » du client pour le thème Hummingbird.
- `rbpro/views/templates/hook/button-classic.tpl`

  - **Hook :** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons` (ou similaire)
  - **Sorties :** Le bouton principal « Retour » ou « Rétractation », stylisé pour le thème Classic.
- `rbpro/views/templates/hook/button-hummingbird.tpl`

  - **Hook :** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons` (ou similaire)
  - **Sorties :** Le bouton principal « Retour » ou « Rétractation », stylisé pour le thème Hummingbird.
- `rbpro/views/templates/hook/button.tpl`

  - **Hook :** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons` (ou similaire)
  - **Sorties :** Un bouton générique « Retour » ou « Rétractation », utilisé comme solution de repli ou base pour les boutons spécifiques au thème.
- `rbpro/views/templates/hook/order-detail-classic.tpl`

  - **Hook :** `displayOrderDetail` (ou similaire)
  - **Sorties :** Une option ou un bouton sur la page de détails de commande individuelle du client pour le thème Classic, lui permettant d'initier un retour pour cette commande spécifique.
- `rbpro/views/templates/hook/order-detail-hummingbird.tpl`

  - **Hook :** `displayOrderDetail` (ou similaire)
  - **Sorties :** Une option ou un bouton sur la page de détails de commande individuelle du client pour le thème Hummingbird.
- `rbpro/views/templates/hook/order-detail.tpl`

  - **Hook :** `displayOrderDetail` (ou similaire)
  - **Sorties :** Une option ou un bouton générique sur la page de détails de commande individuelle du client.
- `rbpro/views/templates/hook/order-withdrawal-notice.tpl`

  - **Hook :** `displayAdminOrder` (ou similaire)
  - **Sorties :** Une notification ou un résumé des demandes de rétractation liées à une commande spécifique, affiché dans la vue d'administration des commandes de PrestaShop.

#### Templates d'administration (`views/templates/admin/`)

Ces templates sont utilisés pour l'interface back-office du module.

- `rbpro/lib/searchTool/views/scripts.tpl`

  - **Sorties :** Inclusions JavaScript et CSS pour la bibliothèque d'outils de recherche, généralement incluses dans les formulaires d'administration qui utilisent l'autocomplétion.
- `rbpro/views/templates/admin/configure.tpl`

  - **Sorties :** Le formulaire de configuration principal du module, rendu par `getContent()` dans `index.php`. Contient tous les paramètres décrits dans la section 4.1.
- `rbpro/views/templates/admin/dashboard.tpl`

  - **Sorties :** Un tableau de bord ou une vue récapitulative pour le module, affichant potentiellement des statistiques ou des demandes de rétractation récentes.
- `rbpro/views/templates/admin/order-state-picker.tpl`

  - **Sorties :** Un template personnalisé pour la sélection des états de commande, utilisé dans la configuration du module ou la vue d'administration des rétractations.
- `rbpro/views/templates/admin/order-withdrawal-notice.tpl`

  - **Sorties :** Un petit widget ou une notification affiché dans la page de détails de commande de PrestaShop dans le back-office, indiquant s'il y a une demande de rétractation active pour cette commande.
- `rbpro/views/templates/admin/updates.tpl`

  - **Sorties :** Un template pour afficher les notifications de mise à jour du module ou les journaux de modifications dans l'interface d'administration.
- `rbpro/views/templates/admin/view.tpl`

  - **Sorties :** Le template de vue détaillée pour une seule demande de rétractation, rendu par `AdminRbpWithdrawalController::renderForm()`. Affiche tous les détails de la demande, les produits, l'historique, les notes et les options de changement de statut.

#### Templates Front-office (`views/templates/front/`)

Ce sont des templates de page autonomes pour le processus de rétractation côté client.

- `rbpro/views/templates/front/confirm_step.tpl`

  - **Sorties :** L'étape de confirmation du formulaire de rétractation, résumant les sélections du client avant la soumission finale.
- `rbpro/views/templates/front/error.tpl`

  - **Sorties :** Une page d'erreur générique affichée si quelque chose ne va pas pendant le processus de rétractation (par exemple, commande invalide, problème technique).
- `rbpro/views/templates/front/form.tpl`

  - **Sorties :** Le formulaire principal de demande de rétractation en ligne, permettant aux clients de sélectionner des commandes, des produits et de fournir des détails.
- `rbpro/views/templates/front/print.tpl`

  - **Sorties :** Une version imprimable de la demande de rétractation, généralement une mise en page simplifiée sans navigation.
- `rbpro/views/templates/front/status.tpl`

  - **Sorties :** La page affichant le statut actuel et l'historique d'une demande de rétractation spécifique.
- `rbpro/views/templates/front/success.tpl`

  - **Sorties :** Une page de message de succès affichée après qu'une demande de rétractation a été soumise avec succès.
- `rbpro/views/templates/front/track.tpl`

  - **Sorties :** Le formulaire où les clients peuvent saisir leur référence de commande et leur e-mail pour suivre une demande de rétractation.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

Le module crée et gère plusieurs tables personnalisées :

- `ps_rbp_withdrawal` : Stocke les détails principaux de la demande de rétractation (client, commande, statut, raison, etc.).
- `ps_rbp_withdrawal_attachment` : Stocke les détails des fichiers téléchargés par les clients pour une demande de rétractation.
- `ps_rbp_withdrawal_history` : Enregistre tous les changements de statut et les messages associés pour chaque demande de rétractation.
- `ps_rbp_withdrawal_note` : Stocke les notes internes ajoutées par les employés à une demande de rétractation.
- `ps_rbp_withdrawal_product` : Lie des produits spécifiques d'une commande à une demande de rétractation, y compris la quantité et la raison.

Les enregistrements de configuration sont stockés dans `ps_configuration` avec des clés généralement préfixées par `RBP_` (par exemple, `RBP_ALLOW_GUEST_WITHDRAWAL`, `RBP_MIN_ORDER_STATUS`).

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Injecter CSS/JS, afficher le bouton de retour (si configuré). |
| `displayFooter` | Dans le pied de page de chaque page. | Afficher le bouton de retour (si configuré). |
| `displayLeftColumn` | Dans la colonne de gauche des pages. | Afficher le bouton de retour (si configuré). |
| `displayRightColumn` | Dans la colonne de droite des pages. | Afficher le bouton de retour (si configuré). |
| `displayProductButtons` | Sur la page produit, près du bouton d'ajout au panier. | Afficher le bouton de retour (si configuré). |
| `displayCustomerAccount` | Sur la page « Mon compte » du client. | Ajouter un lien vers le formulaire de rétractation/suivi. |
| `displayOrderDetail` | Sur la page de détails de commande individuelle du client. | Ajouter une option pour demander un retour pour cette commande. |
| `displayAdminOrder` | Dans le back-office de PrestaShop, sur la page de détails de commande. | Afficher une notification ou un résumé des demandes de rétractation associées. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | Potentiellement enregistrer les détails de la commande pour de futures vérifications d'éligibilité à la rétractation. |
| `actionOrderStatusUpdate` | Après qu'un statut de commande a été modifié. | Vérifier si le statut de la commande affecte l'éligibilité à la rétractation ou déclencher des notifications. |
| `actionFrontControllerSetMedia` | Avant qu'un contrôleur frontal ne rende son contenu. | Charger les actifs CSS et JavaScript spécifiques au front-office. |
| `actionAdminControllerSetMedia` | Avant qu'un contrôleur d'administration ne rende son contenu. | Charger les actifs CSS et JavaScript spécifiques au back-office. |
| `actionModuleInstall` | Lors de l'installation du module. | Créer des tables de base de données, définir les valeurs de configuration par défaut. |
| `actionModuleUninstall` | Lors de la désinstallation du module. | Supprimer les tables de base de données, nettoyer les valeurs de configuration. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et toute question concernant le module « Bouton de retour UE – Formulaire de rétractation en ligne », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support et nos développeurs sont disponibles pour vous aider avec tout problème ou question.
