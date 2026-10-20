---
title: "Portefeuille prépayé et crédit en magasin - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Portefeuille prépayé et crédit en magasin par MyPresta.eu."
sidebar:
  label: "Portefeuille prépayé et crédit en magasin - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Prepaid Wallet & Store Credit sur MyPresta.eu](https://mypresta.eu/modules/payment-process/prepaid-wallet-store-credit.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/payment/prepaid-wallet-store-credit/)
>
> ---


# Portefeuille prépayé et crédit en magasin

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises, qui sont généralement disponibles sur la plupart des environnements d'hébergement modernes.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal où vous définirez le comportement de base de votre système de portefeuille prépayé.

#### Onglet Paramètres généraux

- **Activer le module :**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver l'ensemble du système de portefeuille prépayé pour votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clients verront les options de portefeuille, pourront recharger, utiliser le crédit, et vous pourrez gérer les portefeuilles dans le back office.
    - *Lorsqu'il est désactivé :* Toutes les fonctionnalités du portefeuille sont masquées aux clients, et ils ne peuvent pas utiliser ou gérer leur crédit. La gestion administrative peut toujours être accessible mais n'affectera pas le front office.
  - **Valeur recommandée :** OUI (pour activer le module).
  - **Scénario / exemple de marchand :** Vous êtes prêt à lancer votre programme de fidélité. Activez ce paramètre. Si vous devez le désactiver temporairement pour la maintenance, désactivez-le.
- **Autoriser les clients à recharger leur portefeuille :**

  - **Ce que fait ce paramètre :** Détermine si les clients peuvent activement ajouter des fonds à leur portefeuille eux-mêmes.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clients verront une option « Recharger le portefeuille » dans leur compte, leur permettant d'acheter du crédit en magasin.
    - *Lorsqu'il est désactivé :* Les clients ne peuvent recevoir de crédit que via des codes-cadeaux ou des remboursements/bonus émis par l'administrateur. Ils ne peuvent pas acheter de crédit directement.
  - **Valeur recommandée :** OUI (pour encourager la fidélité en libre-service).
  - **Scénario / exemple de marchand :** Vous voulez que les clients puissent acheter du crédit en magasin quand ils le souhaitent. Activez ceci. Si vous ne voulez émettre du crédit que sous forme de récompenses ou de cartes-cadeaux, désactivez-le.
- **Montant minimum de recharge :**

  - **Ce que fait ce paramètre :** Définit le montant le plus bas qu'un client peut ajouter à son portefeuille en une seule transaction.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'une valeur est définie (par exemple, 10.00) :* Les clients ne peuvent pas recharger moins que ce montant.
    - *Lorsqu'il est défini sur 0 ou vide :* Aucun montant minimum de recharge n'est appliqué.
  - **Valeur recommandée :** 10.00 (ou un montant raisonnable pour votre entreprise afin de couvrir les frais de transaction et d'encourager des recharges significatives).
  - **Scénario / exemple de marchand :** Vous ne voulez pas que les clients rechargent 0.50 EUR. Définissez ceci à 5.00 EUR pour assurer une valeur minimale.
- **Montant maximum de recharge :**

  - **Ce que fait ce paramètre :** Définit le montant le plus élevé qu'un client peut ajouter à son portefeuille en une seule transaction.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'une valeur est définie (par exemple, 500.00) :* Les clients ne peuvent pas recharger plus que ce montant.
    - *Lorsqu'il est défini sur 0 ou vide :* Aucun montant maximum de recharge n'est appliqué.
  - **Valeur recommandée :** 500.00 (ou une limite supérieure appropriée pour gérer les risques et les transactions importantes).
  - **Scénario / exemple de marchand :** Vous voulez empêcher des recharges uniques extrêmement importantes pour des raisons de sécurité ou de trésorerie. Définissez ceci à 1000.00 EUR.
- **Autoriser les clients à acheter des codes-cadeaux :**

  - **Ce que fait ce paramètre :** Contrôle si les clients peuvent acheter des codes-cadeaux pour les offrir à d'autres.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clients peuvent acheter des codes-cadeaux d'une valeur spécifiée, qui peuvent ensuite être utilisés par n'importe qui.
    - *Lorsqu'il est désactivé :* Les codes-cadeaux ne peuvent être générés et émis que par l'administrateur du magasin.
  - **Valeur recommandée :** OUI (pour étendre vos options de cadeaux).
  - **Scénario / exemple de marchand :** Vous souhaitez proposer des cartes-cadeaux numériques. Activez ceci pour que les clients puissent les acheter pour leurs amis et leur famille.
- **Expiration du code-cadeau (jours) :**

  - **Ce que fait ce paramètre :** Définit le nombre de jours pendant lesquels un code-cadeau reste valide après son achat ou sa génération.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'un nombre est défini (par exemple, 365) :* Les codes-cadeaux expireront après ce nombre de jours.
    - *Lorsqu'il est défini sur 0 ou vide :* Les codes-cadeaux n'expireront pas.
  - **Valeur recommandée :** 365 (une durée courante pour les cartes-cadeaux, ou 0 pour aucune expiration).
  - **Scénario / exemple de marchand :** Vous voulez que les codes-cadeaux soient utilisés dans l'année. Définissez ceci à 365.
- **Expiration du solde du portefeuille (jours) :**

  - **Ce que fait ce paramètre :** Définit le nombre de jours pendant lesquels les fonds du portefeuille restent valides après avoir été ajoutés (soit par recharge, utilisation de code-cadeau ou crédit administrateur).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'un nombre est défini (par exemple, 180) :* Les fonds du portefeuille du client expireront après ce nombre de jours.
    - *Lorsqu'il est défini sur 0 ou vide :* Les fonds du portefeuille n'expireront pas.
  - **Valeur recommandée :** 0 (pas d'expiration, pour maximiser la satisfaction client), ou 180/365 si vous souhaitez encourager l'utilisation.
  - **Scénario / exemple de marchand :** Vous voulez encourager les clients à utiliser le solde de leur portefeuille dans les 6 mois. Définissez ceci à 180. Soyez conscient des lois de protection des consommateurs concernant l'expiration des cartes-cadeaux dans votre région.
- **Envoyer un e-mail de rappel d'expiration (jours avant l'expiration) :**

  - **Ce que fait ce paramètre :** Si l'expiration du solde du portefeuille est activée, ce paramètre détermine combien de jours avant l'expiration un e-mail de rappel est envoyé au client.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'un nombre est défini (par exemple, 7) :* Les clients recevront un e-mail 7 jours avant l'expiration du solde de leur portefeuille.
    - *Lorsqu'il est défini sur 0 ou vide :* Aucun e-mail de rappel d'expiration ne sera envoyé.
  - **Valeur recommandée :** 7 (donne aux clients suffisamment de temps pour réagir).
  - **Scénario / exemple de marchand :** Vous avez une expiration de 180 jours. Définissez ceci à 7 pour rappeler aux clients d'utiliser leurs fonds avant de les perdre.
- **Autoriser les paiements partiels avec le portefeuille :**

  - **Ce que fait ce paramètre :** Contrôle si les clients peuvent utiliser le solde de leur portefeuille pour payer seulement une partie de leur commande, en le combinant avec un autre mode de paiement.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Si le solde du portefeuille est inférieur au total de la commande, les clients peuvent utiliser le solde complet et payer le reste avec une autre méthode.
    - *Lorsqu'il est désactivé :* Les clients ne peuvent utiliser leur portefeuille que s'il couvre le total *entier* de la commande. Sinon, ils doivent choisir un autre mode de paiement.
  - **Valeur recommandée :** OUI (pour maximiser l'utilisation du portefeuille et réduire l'abandon de panier).
  - **Scénario / exemple de marchand :** Un client a 10 EUR dans son portefeuille et une commande de 50 EUR. Si activé, il paie 10 EUR avec le portefeuille et 40 EUR avec une carte de crédit. Si désactivé, il ne peut pas utiliser le portefeuille du tout pour cette commande.
- **Option de remboursement vers le portefeuille :**

  - **Ce que fait ce paramètre :** Vous permet d'offrir aux clients la possibilité de recevoir des remboursements pour les commandes retournées directement dans leur portefeuille de magasin au lieu de les renvoyer à leur mode de paiement original.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Lors du traitement d'un remboursement dans le back office, vous verrez une option pour rembourser vers le portefeuille du client.
    - *Lorsqu'il est désactivé :* Les remboursements doivent être traités via les méthodes PrestaShop standard (par exemple, vers la carte de crédit).
  - **Valeur recommandée :** OUI (pour garder les fonds dans votre magasin et simplifier les remboursements).
  - **Scénario / exemple de marchand :** Un client retourne un article. Au lieu d'un remboursement par carte de crédit, vous proposez de mettre l'argent dans son portefeuille, l'encourageant à acheter autre chose dans votre magasin.
- **Activer la prise en charge multi-devises :**

  - **Ce que fait ce paramètre :** Active la capacité du module à gérer les soldes et les transactions du portefeuille dans plusieurs devises, correspondant aux devises configurées de votre magasin.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les soldes du portefeuille sont gérés par devise. Un client qui recharge en EUR aura un solde en EUR, et un client qui recharge en USD aura un solde en USD.
    - *Lorsqu'il est désactivé :* Toutes les transactions du portefeuille sont converties dans la devise par défaut de votre magasin, ce qui peut entraîner des problèmes de taux de conversion.
  - **Valeur recommandée :** OUI (si votre magasin opère dans plusieurs devises).
  - **Scénario / exemple de marchand :** Vous avez des clients dans l'UE et aux États-Unis. L'activation de cette option garantit qu'un client qui recharge 50 EUR a 50 EUR dans son portefeuille, et un client qui recharge 50 USD a 50 USD, évitant ainsi les pertes de conversion de devises.

#### Onglet Bonus de recharge

- **Activer les bonus de recharge :**

  - **Ce que fait ce paramètre :** Active le système de récompense des clients avec un crédit supplémentaire lorsqu'ils rechargent leur portefeuille au-dessus de certains seuils.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les règles de bonus que vous définissez ci-dessous seront appliquées aux recharges des clients.
    - *Lorsqu'il est désactivé :* Aucun bonus ne sera accordé pour les recharges.
  - **Valeur recommandée :** OUI (pour inciter à des recharges plus importantes et augmenter la VMC).
  - **Scénario / exemple de marchand :** Vous voulez donner aux clients un crédit supplémentaire de 5 % s'ils rechargent 100 EUR ou plus. Activez ceci.
- **Niveaux de bonus (Ajouter/Modifier/Supprimer) :**

  - **Ce que fait ce paramètre :** Vous permet de définir des règles de bonus spécifiques basées sur le montant de la recharge. Chaque niveau se compose d'une valeur de recharge minimale et d'un pourcentage de bonus.
  - **Effet de la modification de ce paramètre :**
    - *Ajout d'un niveau (par exemple, « Montant min : 100, Bonus % : 5 ») :* Les clients rechargeant 100 EUR ou plus recevront 5 % supplémentaires de ce montant dans leur portefeuille.
    - *Modification d'un niveau :* Modifie les règles de bonus pour ce seuil spécifique.
    - *Suppression d'un niveau :* Supprime une règle de bonus.
  - **Valeur recommandée :** Créez 2-3 niveaux (par exemple, 5 % pour 100 EUR, 10 % pour 200 EUR) pour encourager des recharges progressivement plus importantes.
  - **Scénario / exemple de marchand :**
    - Niveau 1 : Montant min = 50 EUR, Bonus % = 2 % (Le client recharge 50 EUR, obtient 51 EUR dans son portefeuille)
    - Niveau 2 : Montant min = 100 EUR, Bonus % = 5 % (Le client recharge 100 EUR, obtient 105 EUR dans son portefeuille)
    - Niveau 3 : Montant min = 200 EUR, Bonus % = 10 % (Le client recharge 200 EUR, obtient 220 EUR dans son portefeuille)

#### Onglet Options d'affichage

- **Afficher le solde du portefeuille dans l'en-tête :**

  - **Ce que fait ce paramètre :** Affiche le solde actuel du portefeuille du client de manière proéminente dans la section d'en-tête de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clients connectés verront leur solde (par exemple, « Votre portefeuille : 25.00 EUR ») près de leur lien de compte.
    - *Lorsqu'il est désactivé :* Le solde n'est visible que sur la page dédiée « Mon portefeuille ».
  - **Valeur recommandée :** OUI (pour une grande visibilité et commodité).
  - **Scénario / exemple de marchand :** Vous voulez que les clients soient toujours conscients de leur crédit disponible, les encourageant à l'utiliser.
- **Afficher le lien du portefeuille dans le menu du compte client :**

  - **Ce que fait ce paramètre :** Ajoute un lien direct vers la page « Mon portefeuille » dans le menu de navigation du compte client.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un lien « Mon portefeuille » ou « Crédit en magasin » apparaît dans le menu de gauche du tableau de bord du compte client.
    - *Lorsqu'il est désactivé :* Les clients devraient naviguer vers la page du portefeuille via un autre lien (par exemple, depuis l'en-tête si activé).
  - **Valeur recommandée :** OUI (essentiel pour un accès facile).
  - **Scénario / exemple de marchand :** Vous voulez que les clients trouvent et gèrent facilement les fonds de leur portefeuille.
- **Afficher le lien du portefeuille dans le pied de page :**

  - **Ce que fait ce paramètre :** Ajoute un lien vers la page « Mon portefeuille » dans la section de pied de page de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un lien « Mon portefeuille » ou « Crédit en magasin » apparaît dans le pied de page, accessible depuis n'importe quelle page.
    - *Lorsqu'il est désactivé :* Pas de lien de portefeuille dans le pied de page.
  - **Valeur recommandée :** NON (généralement redondant si dans l'en-tête/menu du compte, mais peut être OUI pour une visibilité maximale).
  - **Scénario / exemple de marchand :** Si le menu de votre compte client n'est pas très proéminent, ou si vous voulez mettre en évidence la fonction de portefeuille plus largement, vous pourriez activer ceci.
- **Afficher le lien du portefeuille dans la colonne gauche/droite :**

  - **Ce que fait ce paramètre :** Ajoute un lien vers la page « Mon portefeuille » dans l'une des colonnes latérales de votre boutique (si votre thème les prend en charge).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un lien « Mon portefeuille » ou « Crédit en magasin » apparaît dans la colonne choisie.
    - *Lorsqu'il est désactivé :* Pas de lien de portefeuille dans les colonnes.
  - **Valeur recommandée :** NON (peut encombrer la mise en page, généralement mieux dans l'en-tête/compte).
  - **Scénario / exemple de marchand :** Si vous avez un en-tête/pied de page très minimaliste et que vous souhaitez utiliser une colonne pour la navigation, cela pourrait être une option.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Paramètres généraux** | Activer le module | OUI | Active/désactive toutes les fonctionnalités du portefeuille. |
|  | Autoriser les clients à recharger leur portefeuille | OUI | Les clients peuvent acheter du crédit en magasin. |
|  | Montant minimum de recharge | 10.00 | Montant le plus bas que le client peut ajouter. |
|  | Montant maximum de recharge | 500.00 | Montant le plus élevé que le client peut ajouter. |
|  | Autoriser les clients à acheter des codes-cadeaux | OUI | Les clients peuvent acheter des cartes-cadeaux. |
|  | Expiration du code-cadeau (jours) | 365 | Période de validité des codes-cadeaux (0 pour aucune expiration). |
|  | Expiration du solde du portefeuille (jours) | 0 | Période de validité des fonds du portefeuille (0 pour aucune expiration). |
|  | Envoyer un e-mail de rappel d'expiration (jours avant l'expiration) | 7 | Jours avant l'expiration pour envoyer un e-mail de rappel. |
|  | Autoriser les paiements partiels avec le portefeuille | OUI | Les clients peuvent combiner le portefeuille avec d'autres modes de paiement. |
|  | Option de remboursement vers le portefeuille | OUI | Option de rembourser les commandes directement vers le portefeuille du client. |
|  | Activer la prise en charge multi-devises | OUI (si magasin multi-devises) | Gère des soldes séparés pour chaque devise. |
| **Bonus de recharge** | Activer les bonus de recharge | OUI | Active le système de bonus pour les recharges. |
|  | Niveaux de bonus | (Personnalisé) | Définir les pourcentages de bonus pour différents montants de recharge. |
| **Options d'affichage** | Afficher le solde du portefeuille dans l'en-tête | OUI | Affiche le solde dans l'en-tête du magasin pour les utilisateurs connectés. |
|  | Afficher le lien du portefeuille dans le menu du compte client | OUI | Ajoute le lien « Mon portefeuille » à la navigation du compte client. |
|  | Afficher le lien du portefeuille dans le pied de page | NON | Ajoute le lien « Mon portefeuille » au pied de page du magasin. |
|  | Afficher le lien du portefeuille dans la colonne gauche/droite | NON | Ajoute le lien « Mon portefeuille » aux colonnes latérales. |

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module fournit des écrans d'administration dédiés pour gérer les portefeuilles clients et les codes-cadeaux.

#### 2.2.1 Gestion des portefeuilles (Back Office > Modules > Portefeuille prépayé et crédit en magasin > Portefeuilles)

- **Nom de l'écran et emplacement du menu :** **Portefeuilles** (trouvé sous l'élément de menu « Portefeuille prépayé et crédit en magasin », qui apparaît sous « Modules » ou « Paiement » selon votre version de PrestaShop et la configuration du menu).
- **Actions et paramètres disponibles :** Cet écran affiche une liste de tous les clients qui ont un portefeuille, ainsi que leur solde actuel, le total des recharges et d'autres informations pertinentes.
  - **Liste des clients :** Un tableau consultable et filtrable affichant le nom, l'e-mail, le solde actuel du portefeuille de chaque client (par devise si le multi-devises est activé) et le montant total rechargé.
  - **Afficher/Modifier le portefeuille :** Cliquez sur la ligne d'un client ou sur une icône « Modifier » pour afficher l'historique détaillé de son portefeuille et effectuer des ajustements.
    - **Ajouter/Supprimer des fonds :** Ajoutez ou soustrayez manuellement des fonds du portefeuille d'un client. Ceci est utile pour émettre un crédit de bonne volonté, une compensation ou corriger des erreurs.
    - **Afficher l'historique des transactions :** Consultez un journal détaillé de toutes les activités du portefeuille pour ce client (recharges, achats, remboursements, bonus, expiration).
    - **Définir la date d'expiration :** Définissez ou ajustez manuellement la date d'expiration pour des fonds spécifiques dans le portefeuille d'un client.
- **Effet des modifications :**
  - *Ajout/Suppression de fonds :* Impacte directement le solde disponible du client dans le front office.
  - *Modification des dates d'expiration :* Affecte le moment où les fonds deviennent inutilisables pour le client.
  - *Affichage de l'historique :* Fournit une piste d'audit complète pour le service client et la comptabilité.
- **Flux de travail recommandé pour la gestion quotidienne du magasin :**
  1. **Demande du client :** Si un client pose des questions sur son solde ou une transaction spécifique, utilisez cet écran pour consulter rapidement son portefeuille et son historique.
  2. **Émission de crédit :** Si vous devez accorder un crédit en magasin à un client (par exemple, pour une plainte, une récompense de fidélité), accédez à son portefeuille et utilisez l'option « Ajouter des fonds ».
  3. **Remboursements vers le portefeuille :** Lors du traitement d'un remboursement pour une commande, vous pouvez choisir d'envoyer l'argent vers le portefeuille du client depuis la page des détails de la commande. Cette action sera reflétée ici.

#### 2.2.2 Gestion des codes-cadeaux (Back Office > Modules > Portefeuille prépayé et crédit en magasin > Codes)

- **Nom de l'écran et emplacement du menu :** **Codes** (trouvé sous l'élément de menu « Portefeuille prépayé et crédit en magasin »).
- **Actions et paramètres disponibles :** Cet écran vous permet de générer, gérer et suivre tous les codes-cadeaux de votre système.
  - **Liste des codes :** Un tableau affichant tous les codes-cadeaux générés, leur valeur, leur statut actuel (actif, utilisé, expiré), qui l'a acheté (le cas échéant), qui l'a utilisé et la date d'expiration.
  - **Générer un nouveau code :** Créez de nouveaux codes-cadeaux avec une valeur, une devise et une date d'expiration facultative spécifiées. Ceux-ci peuvent être utilisés pour des promotions, des cadeaux ou des crédits manuels du service client.
  - **Modifier le code :** Modifiez la valeur, le statut ou l'expiration d'un code existant (s'il n'a pas encore été utilisé).
  - **Supprimer le code :** Supprimez un code (uniquement s'il n'est pas utilisé).
  - **Rechercher/Filtrer :** Trouvez facilement des codes spécifiques par valeur, statut ou client.
- **Effet des modifications :**
  - *Génération d'un code :* Crée un nouveau code-cadeau utilisable qui peut être donné à un client.
  - *Modification d'un code :* Modifie ses propriétés, affectant sa possibilité d'utilisation et sa valeur.
  - *Suppression d'un code :* L'empêche d'être utilisé.
- **Flux de travail recommandé pour la gestion quotidienne du magasin :**
  1. **Campagnes promotionnelles :** Générez un lot de codes-cadeaux pour une campagne marketing (par exemple, « 10 EUR de réduction pour les nouvelles inscriptions »).
  2. **Service client :** Si un client rencontre un problème, vous pouvez rapidement générer un code-cadeau unique pour le dédommager.
  3. **Suivi de l'utilisation :** Surveillez quels codes ont été utilisés et par qui, ce qui vous aide à analyser l'efficacité de la campagne.

#### 2.2.3 Journal d'audit (Back Office > Modules > Portefeuille prépayé et crédit en magasin > Audit)

- **Nom de l'écran et emplacement du menu :** **Audit** (trouvé sous l'élément de menu « Portefeuille prépayé et crédit en magasin »).
- **Actions et paramètres disponibles :** Cet écran fournit un journal complet de toutes les activités liées au portefeuille dans votre boutique.
  - **Liste des activités :** Un tableau détaillé affichant chaque transaction, recharge, utilisation, ajustement administratif et événement d'expiration.
  - **Détails :** Chaque entrée comprend la date, le client concerné, le type d'activité, le montant et toute note pertinente (par exemple, ID de commande, administrateur ayant effectué la modification).
  - **Rechercher/Filtrer :** Filtrez le journal d'audit par client, plage de dates ou type d'activité pour trouver rapidement des événements spécifiques.
- **Effet des modifications :** Il s'agit d'un journal en lecture seule ; aucune modification ne peut être effectuée ici. Il sert de registre crucial pour la responsabilité et le dépannage.
- **Flux de travail recommandé pour la gestion quotidienne du magasin :**
  1. **Dépannage :** Si un client signale un solde incorrect, utilisez le journal d'audit pour retracer toutes les transactions et identifier les éventuels écarts.
  2. **Conformité :** Maintenez un registre clair de tous les mouvements financiers liés au système de portefeuille à des fins comptables et juridiques.
  3. **Examen des performances :** Analysez l'activité globale du portefeuille pour comprendre l'engagement des clients et l'utilisation du module.

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q1 : Mes clients ne voient pas les options de portefeuille dans le front office.**
R1 :

- **Vérifier l'activation du module :** Allez dans **Modules > Gestionnaire de modules**, trouvez « Portefeuille prépayé et crédit en magasin » et assurez-vous que le module est activé.
- **Vérifier les paramètres généraux :** Sur la page de configuration du module, assurez-vous que « Activer le module » est défini sur OUI. Vérifiez également que les options d'affichage spécifiques comme « Afficher le lien du portefeuille dans le menu du compte client » sont activées.
- **Connexion client :** Les fonctionnalités du portefeuille ne sont généralement visibles que pour les clients connectés. Demandez à votre client de se connecter.
- **Compatibilité du thème :** Bien que le module soit conçu pour la compatibilité, certains thèmes très personnalisés peuvent nécessiter des ajustements mineurs. Si vous suspectez un conflit de thème, essayez de passer temporairement au thème PrestaShop par défaut pour voir si le problème se résout.

**Q2 : Le solde du portefeuille d'un client semble incorrect.**
R2 :

- **Vérifier le journal d'audit :** Allez dans **Modules > Portefeuille prépayé et crédit en magasin > Audit**. Recherchez le nom du client et examinez l'intégralité de son historique de transactions. Cela affichera toutes les recharges, achats, remboursements, bonus et ajustements administratifs.
- **Vérifier les détails du portefeuille :** Allez dans **Modules > Portefeuille prépayé et crédit en magasin > Portefeuilles**, trouvez le client et cliquez pour afficher son portefeuille détaillé. Comparez le solde avec le journal d'audit.
- **Problème de devise :** Si « Activer la prise en charge multi-devises » est actif, assurez-vous que vous consultez le solde dans la bonne devise. Un client peut avoir des soldes dans plusieurs devises.
- **Expiration :** Vérifiez si des fonds ont expiré. Le journal d'audit affichera les événements d'expiration.

**Q3 : Mes clients ne reçoivent pas les e-mails de rappel d'expiration.**
R3 :

- **Vérifier les paramètres d'expiration :** Assurez-vous que « Expiration du solde du portefeuille (jours) » est défini sur une valeur supérieure à 0, et que « Envoyer un e-mail de rappel d'expiration (jours avant l'expiration) » est également défini sur une valeur supérieure à 0.
- **Tâche Cron :** Le module utilise probablement une tâche cron pour déclencher ces e-mails. Assurez-vous que votre tâche cron PrestaShop est correctement configurée et s'exécute régulièrement. (Voir la section 7.2 pour `cron.php`).
- **Configuration des e-mails :** Vérifiez que les paramètres de votre e-mail PrestaShop (**Paramètres avancés > E-mail**) sont correctement configurés et envoient des e-mails avec succès. Testez l'envoi d'un e-mail général depuis PrestaShop.
- **Dossiers de spam :** Conseillez aux clients de vérifier leurs dossiers de spam ou de courrier indésirable.

**Q4 : Comment vider le cache Smarty si je vois du contenu ancien ou des problèmes d'affichage ?**
R4 :

- Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop.
- Dans la section « Smarty », définissez « Compilation des templates » sur « Recompiler les templates si les fichiers ont été mis à jour » (ou « Forcer la compilation » temporairement).
- Cliquez sur « Vider le cache » dans le coin supérieur droit.
- Après avoir vidé, vous pouvez revenir à « Ne jamais recompiler les fichiers de template » pour de meilleures performances.

**Q5 : Le module ne s'affiche pas correctement sur mon thème personnalisé.**
R5 :

- **Remplacements CSS :** Le CSS de votre thème personnalisé pourrait remplacer les styles par défaut du module.
- **Inspecter l'élément :** Utilisez les outils de développement de votre navigateur (clic droit, « Inspecter ») pour identifier les règles CSS affectant les éléments du module. Vous pouvez ensuite ajouter du CSS personnalisé à la feuille de style de votre thème pour les remplacer.
- **Contacter le développeur :** Si vous n'êtes pas à l'aise avec le CSS, contactez le développeur de votre thème ou le support MyPresta.eu pour obtenir de l'aide. Fournissez des captures d'écran et le nom de votre thème.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de la structure technique du module « Portefeuille prépayé et crédit en magasin », conçue pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module « Portefeuille prépayé et crédit en magasin » suit le modèle MVC (Modèle-Vue-Contrôleur) standard de PrestaShop. Il étend les fonctionnalités de base de PrestaShop via des hooks, des contrôleurs personnalisés et des classes dédiées.

- **Contrôleurs :** Gère les interactions du front-office (recharges, utilisation de codes, traitement des paiements) et l'administration du back-office (gestion des portefeuilles/codes).
- **Modèles :** Les classes `ObjectModel` personnalisées (`PrepaidWalletService`, `PrepaidCodeService`, etc.) gèrent la persistance des données pour les portefeuilles, les codes et les transactions, en interagissant avec des tables de base de données dédiées.
- **Vues :** Les fichiers Smarty `.tpl` affichent à la fois les interfaces client du front-office (page du portefeuille, formulaires de recharge) et les grilles/formulaires d'administration du back-office.
- **Services :** Plusieurs classes d'aide encapsulent une logique métier spécifique (par exemple, `PrepaidCartCreditService` pour l'intégration au panier, `PrepaidExpiry` pour la gestion de l'expiration des fonds).
- **Hooks :** Le module utilise intensivement les hooks PrestaShop pour injecter ses fonctionnalités dans diverses parties du magasin (en-tête, compte client, processus de paiement, détails de commande).

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `prepaidpayment/controllers/front/applycode.php`
  - **Nom de la classe et classe parente :** `PrepaidPaymentApplyCodeModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Gère la requête AJAX pour appliquer un code-cadeau pendant le processus de commande ou sur la page de rachat dédiée. Il valide le code et met à jour le crédit du panier.
- `prepaidpayment/controllers/front/buycode.php`
  - **Nom de la classe et classe parente :** `PrepaidPaymentBuyCodeModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Gère le processus d'achat de codes-cadeaux par les clients. Il gère l'affichage du formulaire d'achat de codes-cadeaux et la création du produit code-cadeau dans le panier.
- `prepaidpayment/controllers/front/cron.php`
  - **Nom de la classe et classe parente :** `PrepaidPaymentCronModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur est conçu pour être appelé par une tâche cron. Il exécute des tâches en arrière-plan telles que la vérification des fonds de portefeuille expirés, l'envoi d'e-mails de rappel d'expiration et potentiellement d'autres maintenances planifiées.
- `prepaidpayment/controllers/front/entercode.php`
  - **Nom de la classe et classe parente :** `PrepaidPaymentEnterCodeModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Affiche la page dédiée où les clients peuvent saisir un code-cadeau pour l'utiliser et ajouter des fonds à leur portefeuille.
- `prepaidpayment/controllers/front/index.php`
  - **Nom de la classe et classe parente :** `PrepaidPaymentIndexModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Sert probablement de contrôleur frontal par défaut ou de secours, ou de base pour d'autres contrôleurs frontaux. Dans de nombreux modules, cela peut rediriger ou afficher une page de module générale.
- `prepaidpayment/controllers/front/payment.php`
  - **Nom de la classe et classe parente :** `PrepaidPaymentPaymentModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Gère le processus de paiement lorsqu'un client choisit de payer avec son portefeuille. Il valide le solde du portefeuille par rapport au total de la commande et traite le paiement.
- `prepaidpayment/controllers/front/redeempay.php`
  - **Nom de la classe et classe parente :** `PrepaidPaymentRedeemPayModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur gère probablement l'utilisation d'un code-cadeau et son application au panier actuel, combinant potentiellement la logique de `applycode.php` et `payment.php` dans un flux spécifique.
- `prepaidpayment/controllers/front/topup.php`
  - **Nom de la classe et classe parente :** `PrepaidPaymentTopupModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Gère le processus de recharge du portefeuille client. Il affiche le formulaire de recharge, gère la sélection des montants de recharge (et des bonus associés) et ajoute le produit de recharge au panier.

#### Contrôleurs d'administration Back-Office

- `prepaidpayment/controllers/admin/index.php`
  - **Nom de l'onglet et entité gérée :** Ce contrôleur sert de point d'entrée principal pour l'interface d'administration du module. Il distribue probablement vers diverses vues (Portefeuilles, Codes, Audit) et gère la configuration globale et les données du module. Il ne gère pas directement un seul `ObjectModel` mais orchestre la gestion des données de `PrepaidWalletService` et `PrepaidCodeService`.

### 4.3 Classes et modèles de base (`classes/`)

- `prepaidpayment/classes/index.php`
  - **Objectif :** Généralement un fichier vide ou contient une instruction `die()` de base pour empêcher la liste directe des répertoires, une pratique de sécurité courante.
- `prepaidpayment/classes/PrepaidAdmin.php`
  - **Objectif :** Probablement une classe d'aide pour les tâches administratives, contenant potentiellement des méthodes pour rendre les formulaires d'administration, gérer les requêtes AJAX dans le back office, ou des manipulations de données spécifiques pour les vues d'administration.
- `prepaidpayment/classes/PrepaidCartCreditService.php`
  - **Objectif :** Encapsule la logique d'application du crédit de portefeuille ou des codes-cadeaux au panier d'un client pendant le processus de commande. Il gère les calculs, les validations et les mises à jour du total du panier.
- `prepaidpayment/classes/PrepaidCodeService.php`
  - **Objectif :** Gère le cycle de vie des codes-cadeaux.
  - **Interaction ObjectModel :** Étend probablement `ObjectModel` et interagit avec une table de base de données personnalisée (par exemple, `ps_prepaid_codes`).
  - **Champs `$definition` :** Inclurait des champs comme `id_prepaid_code`, `code`, `value`, `id_currency`, `id_customer_buyer`, `id_customer_redeemer`, `date_add`, `date_redeem`, `date_expiry`, `active`.
  - **Méthodes publiques clés :** `generateCode()`, `redeemCode()`, `getCodeByCode()`, `isCodeValid()`, `getCodesForCustomer()`.
- `prepaidpayment/classes/PrepaidCurrency.php`
  - **Objectif :** Une classe d'aide pour gérer les aspects multi-devises du portefeuille, garantissant des conversions de devises et un affichage corrects. Elle pourrait étendre `Currency` ou fournir des méthodes utilitaires pour les opérations sensibles aux devises.
- `prepaidpayment/classes/PrepaidExpiry.php`
  - **Objectif :** Gère la logique d'expiration pour les codes-cadeaux et les soldes de portefeuille. Il contient des méthodes pour calculer les dates d'expiration, vérifier les fonds expirés et potentiellement déclencher des actions d'expiration (par exemple, rendre les fonds inactifs).
- `prepaidpayment/classes/PrepaidThemeCompat.php`
  - **Objectif :** Fournit des couches de compatibilité ou des ajustements spécifiques pour différents thèmes PrestaShop (par exemple, Classic, Hummingbird) ou versions, garantissant que les éléments front-office du module s'affichent correctement dans divers environnements.
- `prepaidpayment/classes/PrepaidTopupCart.php`
  - **Objectif :** Gère la logique spécifique du panier lorsqu'un client recharge son portefeuille. Il pourrait créer un produit virtuel dans le panier représentant le montant de la recharge et gérer les bonus associés.
- `prepaidpayment/classes/PrepaidWalletService.php`
  - **Objectif :** La classe principale pour la gestion des portefeuilles clients.
  - **Interaction ObjectModel :** Étend probablement `ObjectModel` et interagit avec une table de base de données personnalisée (par exemple, `ps_prepaid_wallets` pour les soldes et `ps_prepaid_wallet_history` pour les transactions).
  - **Champs `$definition` :** Pour `ps_prepaid_wallets` : `id_prepaid_wallet`, `id_customer`, `id_currency`, `balance`, `date_update`. Pour `ps_prepaid_wallet_history` : `id_prepaid_wallet_history`, `id_customer`, `id_currency`, `amount`, `type` (topup, purchase, refund, bonus, expiry), `id_order`, `date_add`, `notes`.
  - **Méthodes publiques clés :** `getBalance()`, `addFunds()`, `deductFunds()`, `getHistory()`, `getWalletsForCustomer()`, `processRefundToWallet()`.

### 4.4 Actifs JavaScript (`views/js/`)

- `prepaidpayment/lib/searchTool/views/js/autocomplete.js`
  - **Portée :** Probablement Back-office.
  - **Détails :** Fournit une fonctionnalité d'autocomplétion, probablement pour la recherche de clients ou de produits dans l'interface d'administration, par exemple, lors de l'attribution d'un code-cadeau à un client spécifique ou de la gestion d'un portefeuille.
- `prepaidpayment/views/js/adminPrepaid.js`
  - **Portée :** Back-office.
  - **Détails :** JavaScript général pour les pages d'administration du module. Il peut gérer les soumissions de formulaires, les mises à jour AJAX pour les listes (portefeuilles, codes), les améliorations générales de l'interface utilisateur et les interactions sur la page de configuration principale.
- `prepaidpayment/views/js/adminPrepaidBonusBuilder.js`
  - **Portée :** Back-office.
  - **Détails :** Gère spécifiquement la création et la gestion dynamiques des niveaux de bonus sur la page de configuration du module. Il ajoute/supprime probablement des champs de saisie pour les pourcentages de bonus et les montants minimums, et valide ces entrées.
- `prepaidpayment/views/js/adminPrepaidDashboard.js`
  - **Portée :** Back-office.
  - **Détails :** JavaScript pour le tableau de bord d'administration ou l'écran de présentation, gérant potentiellement la visualisation des données, les statistiques rapides ou les éléments interactifs liés à l'utilisation globale du portefeuille.
- `prepaidpayment/views/js/adminPrepaidSelector.js`
  - **Portée :** Back-office.
  - **Détails :** Gère les composants de sélection dans l'administration, éventuellement pour choisir des clients, des devises ou des codes spécifiques dans divers formulaires ou listes.

### 4.5 Feuilles de style CSS (`views/css/`)

- `prepaidpayment/lib/searchTool/views/css/autocomplete.css`
  - **Portée :** Style d'administration Back-office.
  - **Détails :** Styles pour l'outil de recherche d'autocomplétion utilisé dans le back office, garantissant que les listes déroulantes et les suggestions sont visuellement cohérentes.
- `prepaidpayment/views/css/admin_prepaidpayment.css`
  - **Portée :** Style d'administration Back-office.
  - **Détails :** CSS de base pour les pages d'administration du module, stylisant les formulaires, les tableaux, les boutons et la mise en page générale dans le back office de PrestaShop.
- `prepaidpayment/views/css/front-hummingbird.css`
  - **Portée :** Style client Front-office (spécifiquement pour le thème Hummingbird).
  - **Détails :** Fournit des ajustements de style spécifiques ou des remplacements pour assurer une intégration visuelle optimale avec le thème PrestaShop Hummingbird.
- `prepaidpayment/views/css/front.css`
  - **Portée :** Style client Front-office (général).
  - **Détails :** CSS général pour les composants front-office du module, tels que la page « Mon portefeuille », les formulaires de recharge, les formulaires d'utilisation de codes-cadeaux et l'affichage du portefeuille dans l'en-tête/le panier.
- `prepaidpayment/views/css/prepaidpayment.css`
  - **Portée :** Front-office et Back-office (ou styles généraux à l'échelle du module).
  - **Détails :** Contient des styles communs utilisés à la fois dans le front et le back office, ou des styles fondamentaux pour les éléments uniques du module.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

- `prepaidpayment/views/templates/hook/adminOrder.tpl`
  - **Hook :** `displayAdminOrder` ou similaire.
  - **Sortie :** Affiche des informations ou des actions liées au portefeuille sur la page de détail de la commande PrestaShop dans le back office (par exemple, option de remboursement vers le portefeuille, détails du paiement par portefeuille).
- `prepaidpayment/views/templates/hook/customerAccount-hummingbird.tpl`
  - **Hook :** `displayCustomerAccount` (spécifiquement pour le thème Hummingbird).
  - **Sortie :** Ajoute un lien ou un bloc « Mon portefeuille » au tableau de bord du compte client, stylisé pour le thème Hummingbird.
- `prepaidpayment/views/templates/hook/customerAccount.tpl`
  - **Hook :** `displayCustomerAccount`.
  - **Sortie :** Ajoute un lien ou un bloc « Mon portefeuille » au tableau de bord du compte client, pour les thèmes généraux.
- `prepaidpayment/views/templates/hook/orderDetail.tpl`
  - **Hook :** `displayOrderDetail` ou similaire.
  - **Sortie :** Affiche les détails du paiement par portefeuille sur la page de détail de la commande du client dans le front office.
- `prepaidpayment/views/templates/hook/payment.tpl`
  - **Hook :** `displayPayment` (PrestaShop 1.6) ou `paymentOptions` (PrestaShop 1.7+).
  - **Sortie :** Rend l'option « Payer avec le portefeuille » sur la page de sélection du paiement lors de la commande.
- `prepaidpayment/views/templates/hook/paymentReturn.tpl`
  - **Hook :** `displayPaymentReturn`.
  - **Sortie :** Affiche des informations sur les paiements par portefeuille sur la page de confirmation de commande après le paiement.
- `prepaidpayment/views/templates/hook/paymentTop.tpl`
  - **Hook :** `displayPaymentTop`.
  - **Sortie :** Peut afficher un résumé du solde du portefeuille ou une option pour appliquer un code-cadeau en haut de la page de paiement.
- `prepaidpayment/views/templates/hook/walletNav.tpl`
  - **Hook :** `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`.
  - **Sortie :** Rend le solde du portefeuille ou un lien vers la page du portefeuille dans diverses zones de navigation du magasin.

#### Templates d'administration (`views/templates/admin/`)

- `prepaidpayment/views/templates/admin/audit.tpl`
  - **Sortie :** Rend le tableau du journal d'audit et les options de filtrage dans le back office.
- `prepaidpayment/views/templates/admin/codes.tpl`
  - **Sortie :** Rend la liste des codes-cadeaux, le formulaire de génération de nouveaux codes et la modification des codes existants dans le back office.
- `prepaidpayment/views/templates/admin/dashboard.tpl`
  - **Sortie :** Rend le tableau de bord principal ou la page de présentation du module dans le back office, affichant potentiellement des statistiques ou des liens rapides.
- `prepaidpayment/views/templates/admin/scopeSelector.tpl`
  - **Sortie :** Un template réutilisable pour sélectionner des portées spécifiques, telles que des devises ou des groupes de clients, dans les formulaires d'administration.
- `prepaidpayment/views/templates/admin/wallets.tpl`
  - **Sortie :** Rend la liste des portefeuilles clients, la vue détaillée du portefeuille et les options d'ajout/suppression de fonds dans le back office.

#### Templates Front-office (`views/templates/front/`)

- `prepaidpayment/views/templates/front/buycode.tpl`
  - **Sortie :** Rend le formulaire et l'interface permettant aux clients d'acheter des codes-cadeaux.
- `prepaidpayment/views/templates/front/entercode.tpl`
  - **Sortie :** Rend la page dédiée où les clients peuvent saisir un code-cadeau pour l'utiliser.
- `prepaidpayment/views/templates/front/topup.tpl`
  - **Sortie :** Rend le formulaire et les options permettant aux clients de recharger leur portefeuille, y compris les informations sur les bonus.

#### Templates de bibliothèque (`prepaidpayment/lib/searchTool/views/scripts.tpl`)

- `prepaidpayment/lib/searchTool/views/scripts.tpl`
  - **Sortie :** Contient la logique JavaScript ou Smarty pour l'outil de recherche, probablement incluse dans les templates d'administration où l'autocomplétion est nécessaire.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de base de données

- `ps_prepaid_wallets` : Stocke le solde actuel pour chaque client et devise.
  - `id_prepaid_wallet` (PK)
  - `id_customer` (FK vers `ps_customer`)
  - `id_currency` (FK vers `ps_currency`)
  - `balance` (décimal)
  - `date_upd` (datetime)
- `ps_prepaid_wallet_history` : Enregistre toutes les transactions et modifications des portefeuilles clients.
  - `id_prepaid_wallet_history` (PK)
  - `id_customer` (FK vers `ps_customer`)
  - `id_currency` (FK vers `ps_currency`)
  - `amount` (décimal, positif pour le crédit, négatif pour le débit)
  - `type` (varchar, par exemple, 'topup', 'purchase', 'refund', 'bonus', 'expiry', 'admin_add', 'admin_deduct')
  - `id_order` (FK vers `ps_order`, nullable)
  - `id_prepaid_code` (FK vers `ps_prepaid_codes`, nullable)
  - `notes` (texte, par exemple, "Ajustement admin", "Utilisation de code-cadeau")
  - `date_add` (datetime)
  - `date_expiry` (datetime, nullable)
- `ps_prepaid_codes` : Stocke les informations sur les codes-cadeaux générés et achetés.
  - `id_prepaid_code` (PK)
  - `code` (varchar, unique, la chaîne de caractères du code-cadeau)
  - `value` (décimal, valeur initiale du code)
  - `id_currency` (FK vers `ps_currency`)
  - `id_customer_buyer` (FK vers `ps_customer`, nullable, si acheté par le client)
  - `id_customer_redeemer` (FK vers `ps_customer`, nullable, une fois utilisé)
  - `date_add` (datetime)
  - `date_redeem` (datetime, nullable)
  - `date_expiry` (datetime, nullable)
  - `active` (tinyint, 0 ou 1)
- `ps_prepaid_bonus_tiers` : Stocke les règles de bonus de recharge configurées.
  - `id_prepaid_bonus_tier` (PK)
  - `min_amount` (décimal)
  - `bonus_percentage` (décimal)
  - `position` (int)
- `ps_configuration` : Les paramètres du module sont stockés ici avec des clés comme `PREPAIDPAYMENT_ENABLED`, `PREPAIDPAYMENT_MIN_TOPUP`, etc.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Injecter CSS/JS, afficher le solde du portefeuille pour les utilisateurs connectés. |
| `displayLeftColumn` | Dans la colonne de gauche du magasin. | Afficher le lien du portefeuille. |
| `displayRightColumn` | Dans la colonne de droite du magasin. | Afficher le lien du portefeuille. |
| `displayFooter` | Dans la section du pied de page de chaque page. | Afficher le lien du portefeuille. |
| `displayCustomerAccount` | Sur la page « Mon compte » du client. | Ajouter le lien/bloc « Mon portefeuille ». |
| `displayPayment` (PS 1.6) / `paymentOptions` (PS 1.7+) | Sur la page de sélection du paiement lors de la commande. | Afficher l'option de paiement « Payer avec le portefeuille ». |
| `displayPaymentReturn` | Sur la page de confirmation de commande après le paiement. | Afficher les détails du paiement par portefeuille. |
| `displayPaymentTop` | En haut de la page de paiement. | Potentiellement afficher le solde du portefeuille ou la saisie du code-cadeau. |
| `displayAdminOrder` | Sur la page de détail de la commande dans le back office. | Ajouter l'option de remboursement vers le portefeuille, afficher les informations de paiement par portefeuille. |
| `displayOrderDetail` | Sur la page de détail de la commande du client dans le front office. | Afficher les détails du paiement par portefeuille. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | Déduire les fonds du portefeuille, enregistrer la transaction. |
| `actionOrderStatusPostUpdate` | Après la mise à jour du statut d'une commande. | Potentiellement déclencher des remboursements vers le portefeuille en fonction du changement de statut. |
| `actionFrontControllerSetMedia` | Avant qu'un contrôleur frontal ne rende son contenu. | Ajouter le CSS et le JS spécifiques au module aux pages du front-office. |
| `actionAdminControllerSetMedia` | Avant qu'un contrôleur d'administration ne rende son contenu. | Ajouter le CSS et le JS spécifiques au module aux pages du back-office. |
| `actionCronJob` (hook personnalisé) | Déclenché par le contrôleur cron du module. | Exécuter des tâches planifiées comme les vérifications d'expiration et les rappels par e-mail. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et toute assistance supplémentaire concernant le module « Portefeuille prépayé et crédit en magasin », veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe est dédiée à fournir un support complet et à garantir le bon fonctionnement de votre module.

- **Historique des commandes et téléchargements MyPresta.eu :** <https://mypresta.eu/my-account/orders/>
- **Contact support MyPresta.eu :** <https://mypresta.eu/contact>
