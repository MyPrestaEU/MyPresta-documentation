---
title: "Vendre des CDKeys / Clés de licence - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Vendre des CDKeys / Clés de licence' par MyPresta.eu."
sidebar:
  label: "Vendre des CDKeys / Clés de licence - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Sell CDKeys / License keys sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/sell-cdkeys-license-keys.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/sell-cdkeys-license-keys/)
>
> ---


# Vendre des CDKeys / Clés de licence

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement nécessaire au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Vendre des CDKeys / Clés de licence)

C'est la zone de configuration principale où vous définissez le comportement du module, le moment d'envoi des clés et les paramètres généraux.

#### Onglet Paramètres généraux

- **Activé :**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité principale du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module traitera les commandes, enverra les clés CD et affichera les clés client dans le front office selon vos autres paramètres.
    - *Lorsqu'il est désactivé :* Le module arrêtera toutes ses opérations. Aucune clé ne sera envoyée automatiquement, et la section « Mes clés » du client pourrait disparaître ou devenir inactive.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** Activez-le une fois que vous avez tout configuré pour commencer à vendre des clés. Désactivez-le temporairement si vous devez effectuer une maintenance ou arrêter de vendre des clés numériques.
- **Sélectionner les états de commande :**

  - **Ce que fait ce paramètre :** Détermine quels statuts de commande déclencheront l'envoi automatique des clés CD aux clients. Vous pouvez sélectionner plusieurs statuts.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'un état sélectionné est atteint :* Le module vérifiera la commande pour les produits avec clé CD et enverra les clés.
    - *Lorsqu'un état non sélectionné est atteint :* Aucune clé ne sera envoyée, même si la commande contient des produits avec clé CD.
  - **Valeur recommandée :** « Paiement accepté » et potentiellement « Livré » si vous souhaitez vous assurer que les produits physiques sont également livrés en premier.
  - **Scénario / exemple de marchand :** Si vous souhaitez que les clés soient envoyées immédiatement après le paiement, sélectionnez « Paiement accepté ». Si vous utilisez un mode de paiement manuel comme le virement bancaire, vous pouvez sélectionner « Paiement accepté » après avoir confirmé manuellement le paiement.
- **Groupes de clients autorisés à recevoir la clé CD :**

  - **Ce que fait ce paramètre :** Vous permet de restreindre la livraison des clés CD à des groupes de clients spécifiques (par exemple, « Clients », « Visiteurs », « Invités »).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'un client fait partie d'un groupe sélectionné :* Il recevra les clés CD si toutes les autres conditions sont remplies.
    - *Lorsqu'un client NE fait PAS partie d'un groupe sélectionné :* Il ne recevra pas les clés CD, même s'il achète un produit avec clé CD.
  - **Valeur recommandée :** « Client » (et « Invité » si vous autorisez les commandes en tant qu'invité pour les produits numériques).
  - **Scénario / exemple de marchand :** Vous pouvez restreindre cela aux « Clients » si vous souhaitez encourager la création de compte ou si vous avez des groupes B2B spéciaux qui reçoivent différents types de clés.
- **Valeur maximale de la commande :**

  - **Ce que fait ce paramètre :** Définit une limite supérieure sur la valeur totale d'une commande pour laquelle les clés CD seront automatiquement envoyées. Les commandes dépassant cette valeur ne déclencheront pas la livraison automatique des clés.
  - **Effet de la modification de ce paramètre :**
    - *Total de la commande inférieur ou égal au maximum :* Les clés sont envoyées automatiquement.
    - *Total de la commande supérieur au maximum :* Les clés NE sont PAS envoyées automatiquement. Vous devrez les envoyer manuellement.
  - **Valeur recommandée :** Laissez vide ou définissez une valeur très élevée (par exemple, 999999) si vous ne souhaitez aucune restriction de valeur.
  - **Scénario / exemple de marchand :** Utilisez ceci comme mesure de prévention de la fraude. Si vous remarquez de nombreuses commandes frauduleuses de grande valeur, vous pouvez définir une limite pour les examiner manuellement avant de libérer des clés coûteuses.
- **Envoyer plusieurs codes dans un seul e-mail :**

  - **Ce que fait ce paramètre :** Contrôle si plusieurs clés CD pour le même produit dans une seule commande sont envoyées dans un seul e-mail ou dans des e-mails séparés.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Si un client achète 3 unités de « Jeu X », il recevra un e-mail contenant les 3 clés pour « Jeu X ».
    - *Lorsqu'il est désactivé :* Si un client achète 3 unités de « Jeu X », il recevra 3 e-mails séparés, chacun avec une clé pour « Jeu X ».
  - **Valeur recommandée :** OUI (généralement meilleure pour l'expérience client et réduit l'encombrement des e-mails).
  - **Scénario / exemple de marchand :** Si un client achète un « pack de 4 » d'un jeu, l'envoi des 4 clés dans un seul e-mail est beaucoup plus clair que 4 e-mails séparés.
- **Titre de l'e-mail :**

  - **Ce que fait ce paramètre :** Vous permet de personnaliser l'objet de l'e-mail envoyé aux clients contenant leurs clés CD.
  - **Effet de la modification de ce paramètre :** L'objet de l'e-mail reflétera votre titre personnalisé, ce qui facilitera l'identification de l'e-mail par les clients.
  - **Valeur recommandée :** Quelque chose de clair et professionnel, par exemple, « Vos clés CD / Licences de [Nom de votre boutique] - Commande n°[ID de commande] ».
  - **Scénario / exemple de marchand :** Un objet clair comme « Vos clés de jeu pour la commande n°12345 » aide les clients à trouver rapidement leurs clés.
- **Changer le statut de la commande :**

  - **Ce que fait ce paramètre :** Une fois les clés CD envoyées avec succès, cette option vous permet de modifier automatiquement le statut de la commande vers un nouvel état spécifié.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé et qu'un état est sélectionné :* Le statut de la commande sera automatiquement mis à jour (par exemple, de « Paiement accepté » à « Clés CD envoyées »).
    - *Lorsqu'il est désactivé :* Le statut de la commande restera tel qu'il était après le déclenchement initial (par exemple, « Paiement accepté »).
  - **Valeur recommandée :** OUI, et sélectionnez un statut distinct comme « Clés CD envoyées » (vous devrez peut-être créer ce statut dans PrestaShop > Statuts de commande).
  - **Scénario / exemple de marchand :** Cela vous aide à identifier rapidement les commandes pour lesquelles les clés ont déjà été livrées, améliorant ainsi votre flux de travail de gestion des commandes.
- **Sélectionner l'état de la commande (pour le changement de statut) :**

  - **Ce que fait ce paramètre :** Si « Changer le statut de la commande » est activé, cette liste déroulante vous permet de choisir le statut de commande spécifique à appliquer après l'envoi des clés.
  - **Effet de la modification de ce paramètre :** Le statut choisi sera appliqué à la commande.
  - **Valeur recommandée :** Un statut personnalisé comme « Clés CD envoyées » ou « Produit numérique livré ».
  - **Scénario / exemple de marchand :** La création d'un statut spécifique comme « Clés CD envoyées » vous permet de filtrer les commandes et de voir exactement celles pour lesquelles les produits numériques ont été livrés.
- **Inclure les clés à la facture :**

  - **Ce que fait ce paramètre :** Détermine si les clés CD livrées doivent également être imprimées sur la facture du client.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clés apparaîtront sur la facture PDF générée pour la commande.
    - *Lorsqu'il est désactivé :* Les clés seront uniquement envoyées par e-mail et/ou apparaîtront dans la section « Mes clés », mais pas sur la facture.
  - **Valeur recommandée :** OUI (fournit un enregistrement supplémentaire pour le client).
  - **Scénario / exemple de marchand :** Certains clients préfèrent avoir tous les détails de l'achat, y compris les clés, sur leur facture à des fins de tenue de registres ou fiscales.
- **Activer la pagination :**

  - **Ce que fait ce paramètre :** Active la pagination pour la liste des clés CD affichées dans la section « Mes clés » du client dans le front office.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Si un client a de nombreuses clés, elles seront affichées sur plusieurs pages, améliorant les temps de chargement et la lisibilité.
    - *Lorsqu'il est désactivé :* Toutes les clés seront listées sur une seule page.
  - **Valeur recommandée :** OUI (surtout si les clients peuvent accumuler de nombreuses clés).
  - **Scénario / exemple de marchand :** Un client qui achète régulièrement des clés de jeu appréciera la pagination pour trouver rapidement des clés spécifiques sans faire défiler une très longue liste.
- **Nombre d'éléments par pagination :**

  - **Ce que fait ce paramètre :** Si la pagination est activée, cela définit le nombre de clés CD affichées par page dans la section « Mes clés » du client.
  - **Effet de la modification de ce paramètre :** Contrôle la densité de la liste des clés sur chaque page.
  - **Valeur recommandée :** 10-20 (un bon équilibre pour la lisibilité).
  - **Scénario / exemple de marchand :** Définir cela à 15 signifie qu'un client avec 30 clés verra 2 pages de clés.

#### Onglet Paramètres d'importation CSV

- **Délimiteur de ligne du fichier CSV :**

  - **Ce que fait ce paramètre :** Spécifie le caractère utilisé pour séparer les lignes individuelles dans votre fichier CSV lors de l'importation de clés CD.
  - **Effet de la modification de ce paramètre :** Le module utilise ce caractère pour analyser correctement votre fichier CSV en entrées de clés individuelles. Un délimiteur incorrect entraînera des erreurs d'importation.
  - **Valeur recommandée :** `\n` (caractère de nouvelle ligne, standard pour la plupart des fichiers CSV).
  - **Scénario / exemple de marchand :** Si votre liste de clés est `clé1\nclé2\nclé3`, le module doit savoir que `\n` sépare chaque clé.
- **Délimiteur de colonne du fichier CSV :**

  - **Ce que fait ce paramètre :** Spécifie le caractère utilisé pour séparer les colonnes (champs) dans chaque ligne de votre fichier CSV lors de l'importation de clés CD.
  - **Effet de la modification de ce paramètre :** Le module utilise ce caractère pour identifier correctement les différents points de données (par exemple, clé, ID de groupe) dans chaque ligne. Un délimiteur incorrect entraînera des erreurs d'importation.
  - **Valeur recommandée :** `;` (point-virgule) ou `,` (virgule), selon la façon dont vos fichiers CSV sont générés.
  - **Scénario / exemple de marchand :** Si votre CSV est `clé1;id_produit_1;id_groupe_1`, le module doit savoir que `;` sépare les champs.

#### Onglet Analyse et Fraude

- **CDKEYS\_ANALYTICS\_DEFAULT\_CHART, CDKEYS\_ANALYTICS\_PERIOD, CDKEYS\_ANALYTICS\_CHART\_DAYS, CDKEYS\_ANALYTICS\_CHART\_WEEKS, CDKEYS\_ANALYTICS\_CHART\_MONTHS, CDKEYS\_ANALYTICS\_PREDICTION\_DAYS, CDKEYS\_ANALYTICS\_TOP\_LIMIT, CDKEYS\_ANALYTICS\_MIN\_SALES, CDKEYS\_ANALYTICS\_SHOW\_EMPTY\_GROUPS, CDKEYS\_ANALYTICS\_INCLUDE\_INACTIVE :**

  - **Ce que font ces paramètres :** Ce sont des clés de configuration internes liées au tableau de bord d'analyse et de détection de fraude du module. Elles contrôlent la manière dont les données sont affichées, agrégées et filtrées dans la section d'analyse du back-office du module.
  - **Effet de la modification de ces paramètres :** Ajuste la représentation visuelle et les points de données affichés dans le tableau de bord du module, vous aidant à surveiller les ventes clés et les modèles de fraude potentiels.
  - **Valeur recommandée :** Les valeurs par défaut sont généralement bonnes. Ajustez uniquement si vous avez besoin de vues de rapport spécifiques.
  - **Scénario / exemple de marchand :** Vous pouvez ajuster `CDKEYS_ANALYTICS_PERIOD` pour afficher les tendances des ventes sur une semaine au lieu d'un mois, ou `CDKEYS_ANALYTICS_TOP_LIMIT` pour voir plus de groupes de clés les plus vendus.
- **CDKEYS\_ALERT\_COOLDOWN\_HOURS :**

  - **Ce que fait ce paramètre :** Définit une période de "cooldown" en heures pour les alertes de fraude. Si une alerte est déclenchée pour un client, une autre alerte pour le même client ne sera pas déclenchée pendant cette période de "cooldown".
  - **Effet de la modification de ce paramètre :** Empêche le spam d'alertes pour des tentatives de fraude répétées du même client dans un court laps de temps.
  - **Valeur recommandée :** 24-48 heures (pour laisser le temps à une révision manuelle sans ré-alerte constante).
  - **Scénario / exemple de marchand :** Si un client tente plusieurs commandes frauduleuses en une heure, cela vous empêche de recevoir une alerte pour chaque tentative, la consolidant en une seule alerte initiale.
- **CDKEYS\_EXPORT\_MASK\_CODES :**

  - **Ce que fait ce paramètre :** Lors de l'exportation des données de clés CD, ce paramètre détermine si les codes de clé réels doivent être masqués (cachés) pour des raisons de sécurité.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les données exportées afficheront des codes masqués (par exemple, `*****`).
    - *Lorsqu'il est désactivé :* Les données exportées afficheront les codes de clé complets et non masqués.
  - **Valeur recommandée :** OUI (pour la sécurité, surtout si vous partagez des fichiers d'exportation).
  - **Scénario / exemple de marchand :** Si vous devez partager une liste de clés utilisées avec un fournisseur mais que vous ne voulez pas exposer les valeurs réelles des clés, activez le masquage.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module ajoute plusieurs nouvelles sections à votre menu du Back Office de PrestaShop, généralement sous un onglet principal « Clés CD » ou « Licences ».

#### 2.2.1 Clés CD > Groupes (AdminCdKeysGroupsController)

- **Nom de l'écran et emplacement du menu :** **Back Office > Clés CD > Groupes**
- **Objectif :** Cet écran vous permet de créer et de gérer des groupes de clés CD. Un groupe est essentiellement un pool de clés qui peuvent être attribuées à un ou plusieurs produits. C'est crucial pour gérer votre inventaire de clés.
- **Actions et paramètres disponibles :**
  - **Ajouter un nouveau groupe :** Créez un nouveau groupe avec un nom (par exemple, « Clés Windows 11 Pro », « Jeu X Édition Deluxe »).
  - **Modifier le groupe :** Modifiez le nom d'un groupe existant.
  - **Supprimer le groupe :** Supprimez un groupe (assurez-vous qu'aucun produit actif n'y est lié et qu'aucune clé n'est attribuée).
  - **Afficher les clés du groupe :** Naviguez directement vers la liste des clés associées à un groupe spécifique.
- **Effet des modifications :**
  - La création d'un groupe vous permet de catégoriser vos clés et de les lier à des produits.
  - La suppression d'un groupe supprimera son association avec les produits et les clés, ce qui pourrait entraîner des problèmes si les clés sont toujours nécessaires.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Avant d'importer des clés, créez un groupe pour chaque produit distinct ou version d'un produit qui nécessite une clé.
  2. Attribuez le groupe approprié à vos produits (cela se fait sur la page de modification du produit, sous l'onglet « Modules » ou un onglet « Clés CD » dédié ajouté par le module).

#### 2.2.2 Clés CD > Liste (AdminCdKeysListController)

- **Nom de l'écran et emplacement du menu :** **Back Office > Clés CD > Liste**
- **Objectif :** C'est votre inventaire central pour toutes les clés CD individuelles. Ici, vous pouvez importer, afficher et gérer le statut de chaque clé.
- **Actions et paramètres disponibles :**
  - **Importer CSV :** Téléchargez un fichier CSV contenant vos clés. Vous spécifierez le groupe auquel ces clés appartiennent pendant le processus d'importation.
  - **Ajouter une nouvelle clé :** Ajoutez manuellement une seule clé, attribuez-la à un groupe et définissez son statut (par exemple, « Disponible », « Utilisée »).
  - **Modifier la clé :** Modifiez la valeur, le groupe ou le statut d'une clé existante.
  - **Supprimer la clé :** Supprimez une clé de l'inventaire.
  - **Filtrer/Rechercher :** Trouvez des clés spécifiques par valeur, groupe ou statut.
  - **Exporter :** Exportez votre inventaire de clés (avec masquage facultatif).
- **Effet des modifications :**
  - L'importation de clés remplit votre inventaire, les rendant disponibles à la vente.
  - La modification du statut d'une clé (par exemple, en « Utilisée ») l'empêche d'être attribuée à de nouvelles commandes.
  - La suppression d'une clé la supprime définitivement.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Importez régulièrement de nouveaux lots de clés de vos fournisseurs dans leurs groupes respectifs.
  2. Surveillez le statut « Utilisée » pour vous assurer que les clés sont attribuées correctement.
  3. Si un client signale un problème avec une clé, vous pouvez la trouver ici, vérifier son statut et potentiellement en attribuer une nouvelle.

#### 2.2.3 Clés CD > Archive (AdminCdKeysArchiveController)

- **Nom de l'écran et emplacement du menu :** **Back Office > Clés CD > Archive**
- **Objectif :** Cet écran fournit un historique de toutes les clés CD qui ont été attribuées aux commandes des clients. Il agit comme un journal d'audit pour la distribution des clés.
- **Actions et paramètres disponibles :**
  - **Afficher les clés attribuées :** Voir quelle clé a été attribuée à quelle commande, pour quel produit et à quel client.
  - **Filtrer/Rechercher :** Trouvez des clés archivées spécifiques par ID de commande, nom du client, produit ou valeur de la clé.
  - **Renvoyer l'e-mail :** Option pour renvoyer l'e-mail de clé CD au client (utile s'il prétend ne pas l'avoir reçu).
- **Effet des modifications :** Cet écran est principalement destiné à la visualisation et à l'audit. Les actions ici ne modifient pas le statut des clés dans la section « Liste » mais permettent des actions de support client comme le renvoi d'e-mails.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Utilisez cet écran pour rechercher rapidement les clés achetées par un client s'il contacte le support.
  2. Vérifiez que les clés ont été envoyées correctement pour des commandes spécifiques.
  3. Renvoyez les clés si l'e-mail d'un client a été perdu ou supprimé accidentellement.

#### 2.2.4 Page de modification du produit (Back Office > Catalogue > Produits > Modifier le produit)

- **Nom de l'écran et emplacement du menu :** Lors de la modification d'un produit, recherchez un nouvel onglet ou une nouvelle section liée aux « Clés CD » ou aux « Modules ».
- **Objectif :** C'est ici que vous liez un produit spécifique à un groupe de clés CD, le marquant comme un « produit clé CD ».
- **Actions et paramètres disponibles :**
  - **Activer la clé CD pour ce produit :** Un interrupteur ou une case à cocher pour indiquer que ce produit nécessite la livraison d'une clé CD.
  - **Sélectionner le groupe de clés CD :** Une liste déroulante pour choisir le groupe de clés à partir duquel ce produit doit puiser lors d'une commande.
- **Effet des modifications :**
  - *Lorsqu'il est activé et qu'un groupe est sélectionné :* Tout achat de ce produit déclenchera automatiquement le module pour attribuer une clé disponible du groupe choisi et l'envoyer au client.
  - *Lorsqu'il est désactivé :* Le produit sera traité comme un produit PrestaShop normal, et aucune clé ne sera attribuée ou envoyée.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Pour chaque produit numérique que vous vendez et qui nécessite une clé unique, accédez à sa page de modification.
  2. Activez l'option Clé CD et sélectionnez le groupe de clés correct que vous avez créé précédemment.
  3. Assurez-vous d'avoir suffisamment de clés dans le groupe sélectionné pour couvrir les ventes potentielles.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activé | OUI | Interrupteur principal pour la fonctionnalité du module. |
| | Sélectionner les états de commande | Paiement accepté | Déclenche la livraison de la clé lorsque la commande atteint ce statut. |
| | Groupes de clients autorisés à recevoir la clé CD | Client, Invité | Restreint la livraison de la clé aux groupes de clients spécifiés. |
| | Valeur maximale de la commande | Vide (aucune limite) | Définit un plafond de valeur pour la livraison automatique de la clé (prévention de la fraude). |
| | Envoyer plusieurs codes dans un seul e-mail | OUI | Regroupe plusieurs clés pour le même produit dans un seul e-mail. |
| | Titre de l'e-mail | Vos clés CD de [Nom de la boutique] | Personnalise l'objet des e-mails de livraison de clés. |
| | Changer le statut de la commande | OUI | Met à jour automatiquement le statut de la commande après la livraison de la clé. |
| | Sélectionner l'état de la commande (pour le changement de statut) | « Clés CD envoyées » (personnalisé) | Le statut spécifique à appliquer après l'envoi des clés. |
| | Inclure les clés à la facture | OUI | Imprime les clés livrées sur la facture PDF du client. |
| | Activer la pagination | OUI | Active la pagination pour « Mes clés » dans le compte client. |
| | Nombre d'éléments par pagination | 10-20 | Nombre de clés affichées par page dans « Mes clés ». |
| | Délimiteur de ligne du fichier CSV | `\n` | Caractère séparant les lignes lors de l'importation de clés CSV. |
| | Délimiteur de colonne du fichier CSV | `;` ou `,` | Caractère séparant les colonnes lors de l'importation de clés CSV. |
| | CDKEYS\_EXPORT\_MASK\_CODES | OUI | Masque les codes de clé dans les fichiers d'exportation pour la sécurité. |
| **Clés CD > Groupes** | Ajouter/Modifier le nom du groupe | N/A | Gère les catégories/pools de clés. |
| **Clés CD > Liste** | Importer CSV | N/A | Télécharge en masse les clés dans des groupes. |
| | Ajouter/Modifier la clé | N/A | Gère manuellement les valeurs et le statut des clés individuelles. |
| **Clés CD > Archive** | Renvoyer l'e-mail | N/A | Renvoie l'e-mail de livraison de la clé pour une commande spécifique. |
| **Page de modification du produit** | Activer la clé CD pour ce produit | OUI | Marque un produit comme nécessitant la livraison d'une clé CD. |
| | Sélectionner le groupe de clés CD | (Groupe spécifique) | Lie le produit à un pool de clés pour l'exécution. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes clients ne reçoivent pas leurs clés CD. Que dois-je vérifier en premier ?**
R1 :

1.  **Module activé ?** Allez dans `Modules > Gestionnaire de modules > Vendre des CDKeys / Clés de licence` et assurez-vous que le module est « Activé ».
2.  **Statut de la commande :** Vérifiez la configuration de votre module sous « Sélectionner les états de commande ». Le statut actuel de la commande du client (par exemple, « Paiement accepté ») est-il sélectionné dans cette liste ?
3.  **Produit lié au groupe :** Sur la page de modification du produit (`Catalogue > Produits > Modifier le produit`), assurez-vous que l'option « Activer la clé CD pour ce produit » est cochée et que le bon « Groupe de clés CD » est sélectionné.
4.  **Clés dans le groupe :** Allez dans `Clés CD > Liste` et vérifiez s'il y a des clés disponibles (non utilisées) dans le groupe attribué au produit. Si ce n'est pas le cas, importez plus de clés.
5.  **Groupe de clients :** Vérifiez que le groupe de clients est autorisé à recevoir des clés sous « Groupes de clients autorisés à recevoir la clé CD » dans la configuration du module.
6.  **Configuration des e-mails :** Vérifiez les paramètres d'e-mail de votre PrestaShop (`Paramètres avancés > E-mail`) pour vous assurer que les e-mails sont envoyés correctement depuis votre boutique. Demandez également au client de vérifier son dossier spam/courrier indésirable.

**Q2 : J'ai importé un fichier CSV, mais les clés n'apparaissent pas ou sont incorrectes.**
R2 :

1.  **Paramètres de délimiteur :** Vérifiez à nouveau vos paramètres « Délimiteur de ligne du fichier CSV » et « Délimiteur de colonne du fichier CSV » dans la configuration du module. Ceux-ci doivent correspondre exactement à la structure de votre fichier CSV. Les problèmes courants sont l'utilisation de la virgule (`,`) au lieu du point-virgule (`;`) ou vice-versa.
2.  **Format de fichier :** Assurez-vous que votre fichier CSV est un texte brut, et non un fichier Excel enregistré en CSV avec un formatage complexe.
3.  **Groupe cible :** Avez-vous sélectionné le bon groupe de clés CD pendant le processus d'importation ?

**Q3 : La section « Mes clés » n'apparaît pas dans le compte du client.**
R3 :

1.  **Module activé :** Assurez-vous que le module est actif.
2.  **Compatibilité du thème :** Bien que le module utilise des hooks PrestaShop standard, certains thèmes fortement personnalisés peuvent remplacer le hook `displayCustomerAccount` par défaut. Vérifiez si votre thème a modifié cette zone. Si c'est le cas, vous pourriez avoir besoin de légers ajustements de thème (reportez-vous à la section 7.6 pour les modèles de hook).
3.  **Cache :** Videz le cache de votre PrestaShop (`Paramètres avancés > Performances > Vider le cache`).

**Q4 : Comment créer un nouveau statut de commande comme « Clés CD envoyées » ?**
R4 :

1.  Allez dans `Paramètres de la boutique > Paramètres de commande > Statuts`.
2.  Cliquez sur « Ajouter un nouveau statut de commande ».
3.  Donnez-lui un nom clair (par exemple, « Clés CD envoyées »).
4.  Choisissez une couleur distincte (par exemple, bleu clair) pour l'identifier facilement dans votre liste de commandes.
5.  Assurez-vous que « Considérer la commande associée comme validée » est coché si vous souhaitez qu'elle compte comme une commande terminée.
6.  Enregistrez le nouveau statut, puis revenez à la configuration du module pour le sélectionner pour « Sélectionner l'état de la commande (pour le changement de statut) ».

**Q5 : Puis-je attribuer manuellement une clé à une commande ou à un client ?**
R5 : Le module automatise principalement cela. Si vous devez attribuer manuellement une clé (par exemple, pour un remplacement), vous devrez généralement :

1.  Allez dans `Clés CD > Liste`, trouvez une clé disponible et notez sa valeur.
2.  Allez dans la commande du client (`Commandes > Commandes`) et ajoutez une note privée avec la clé.
3.  Envoyez manuellement la clé par e-mail au client.
4.  Ensuite, revenez à `Clés CD > Liste`, trouvez cette clé et modifiez manuellement son statut en « Utilisée » pour l'empêcher d'être attribuée à nouveau.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de la structure technique du module « Vendre des CDKeys / Clés de licence », destinée aux développeurs, webmasters et agences techniques.

### 4.1 Aperçu de l'architecture

Le module suit un modèle MVC (Model-View-Controller) PrestaShop standard. Il étend `Module` pour sa fonctionnalité principale et `AdminController` pour ses interfaces Back Office. Il utilise `ObjectModel` de PrestaShop pour gérer les groupes de clés CD, les clés individuelles et leur historique d'utilisation. La livraison des clés est principalement basée sur des événements, déclenchée par les hooks `actionOrderStatusPostUpdate` et `actionOrderStatusUpdate`. L'interaction front-office est minimale, fournissant principalement une section « Mes clés » visible par le client.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `controllers/front/index.php` :
  - **Nom de la classe :** `CdkeysIndexModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** Probablement un espace réservé ou un contrôleur de redirection. Dans de nombreux modules, `index.php` dans le répertoire du contrôleur frontal peut gérer le routage par défaut ou simplement rediriger vers un contrôleur plus spécifique.
- `controllers/front/mykeys.php` :
  - **Nom de la classe :** `CdkeysMykeysModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** Gère l'affichage des clés CD achetées par le client dans sa section « Mon compte ». Il récupère les enregistrements `cdkey_used` associés au client actuel, applique la pagination si activée, et rend `views/templates/front/mykeys.tpl`.

#### Contrôleurs d'administration Back-Office

- `controllers/admin/AdminCdKeysArchiveController.php` :
  - **Nom de l'onglet :** Clés CD > Archive
  - **Entité gérée :** `cdkey_used` (enregistrements des clés attribuées)
  - **Responsabilité :** Fournit une interface de gestion de liste pour toutes les clés CD qui ont été attribuées aux commandes. Il permet de visualiser, de filtrer et potentiellement de renvoyer les e-mails de clés. Il utilise `HelperList` pour son affichage.
- `controllers/admin/AdminCdKeysGroupsController.php` :
  - **Nom de l'onglet :** Clés CD > Groupes
  - **Entité gérée :** `cdkey_group`
  - **Responsabilité :** Gère la création, la modification et la suppression des groupes de clés CD. Ces groupes agissent comme des catégories pour vos clés et sont liés aux produits. Il utilise `HelperList` et `HelperForm` pour ses interfaces.
- `controllers/admin/AdminCdKeysListController.php` :
  - **Nom de l'onglet :** Clés CD > Liste
  - **Entité gérée :** `cdkey`
  - **Responsabilité :** Gère l'inventaire des clés CD individuelles. Cela inclut l'importation de fichiers CSV, l'ajout/la modification/la suppression de clés et la visualisation de leur statut (disponible, utilisée). Il utilise `HelperList` et `HelperForm`.
- `controllers/admin/index.php` :
  - **Nom de l'onglet :** Clés CD (Tableau de bord principal)
  - **Entité gérée :** N/A (Tableau de bord)
  - **Responsabilité :** Cela sert probablement de tableau de bord principal pour le module, affichant des analyses, des statistiques clés et potentiellement des alertes de fraude. Il agrège les données des tables `cdkey_used` et `cdkey`.

### 4.3 Classes et modèles principaux (`classes/`)

Le dossier du module n'indique pas de répertoire `classes/` explicite. Cela suggère que les définitions `ObjectModel` principales et la logique métier de base sont probablement encapsulées dans le fichier `cdkeys.php` lui-même, ou dans les fichiers de contrôleur respectifs.

Si des définitions `ObjectModel` sont présentes dans `cdkeys.php`, elles ressembleraient généralement à :

- `CdKeyGroup` (pour la table `ps_cdkey_group`) : Gère les groupes de clés.
  - `$definition` inclurait `id_cdkey_group`, `name`.
- `CdKey` (pour la table `ps_cdkey`) : Gère les clés individuelles.
  - `$definition` inclurait `id_cdkey`, `id_cdkey_group`, `key_value`, `status` (par exemple, 'available', 'used').
- `CdKeyUsed` (pour la table `ps_cdkey_used`) : Gère les clés attribuées.
  - `$definition` inclurait `id_cdkey_used`, `id_cdkey`, `id_order`, `id_customer`, `id_product`, `date_add`.

### 4.4 Actifs JavaScript (`views/js/`)

- `cdkeys/lib/emailTemplatesManager/js/emailTemplatesManager.js` :
  - **Portée :** Back-office.
  - **Responsabilité :** Gère l'interface utilisateur pour la création, la modification et la sélection de modèles d'e-mail dans la configuration du module. Il gère probablement les appels AJAX pour enregistrer le contenu des modèles, prévisualiser les e-mails et basculer entre différentes versions de modèles.
- `cdkeys/lib/searchTool/views/js/autocomplete.js` :
  - **Portée :** Back-office.
  - **Responsabilité :** Fournit une fonctionnalité d'autocomplétion pour les champs de recherche dans les interfaces d'administration du module (par exemple, recherche de produits, de clients ou de groupes de clés). Il se lie aux champs de saisie et effectue des requêtes AJAX pour récupérer des suggestions.
- `cdkeys/views/js/adminCdKeysDashboard.js` :
  - **Portée :** Back-office (AdminCdKeysDashboardController ou tableau de bord principal du module).
  - **Responsabilité :** Alimente les éléments interactifs du tableau de bord principal du module. Cela pourrait inclure le rendu de graphiques (par exemple, en utilisant Chart.js ou une bibliothèque similaire), le filtrage des données et les mises à jour dynamiques des statistiques.
- `cdkeys/views/js/cdkeys-dashboard-demo-console.js` :
  - **Portée :** Back-office.
  - **Responsabilité :** Probablement un script de développement/débogage ou une console de démonstration pour le tableau de bord, enregistrant éventuellement des événements ou fournissant des données de test. Ne devrait pas être actif en production.
- `cdkeys/views/js/cdkeys-fraud-demo-console.js` :
  - **Portée :** Back-office.
  - **Responsabilité :** Similaire à la console de démonstration du tableau de bord, il s'agit probablement d'un script de développement/débogage pour les fonctionnalités de détection de fraude. Ne devrait pas être actif en production.
- `cdkeys/views/js/cdkeys-pagination.js` :
  - **Portée :** Front-office (`mykeys.tpl`).
  - **Responsabilité :** Gère la logique côté client pour la pagination dans la section « Mes clés » du client. Cela peut impliquer des appels AJAX pour charger de nouvelles pages de clés sans rechargement complet de la page, ou simplement la gestion de l'affichage des numéros de page et de la navigation.

### 4.5 Feuilles de style CSS (`views/css/`)

- `cdkeys/lib/emailTemplatesManager/css/emailTemplatesManager.css` :
  - **Portée :** Back-office.
  - **Composants d'interface utilisateur principaux :** Style l'interface de gestion des modèles d'e-mail, y compris les formulaires, les boutons et les zones de prévisualisation.
  - **Sélecteurs de classe CSS clés :** `.email-template-manager`, `.template-form`, `.template-preview`.
- `cdkeys/lib/searchTool/views/css/autocomplete.css` :
  - **Portée :** Back-office.
  - **Composants d'interface utilisateur principaux :** Style les listes déroulantes et les champs de saisie d'autocomplétion.
  - **Sélecteurs de classe CSS clés :** `.autocomplete-suggestions`, `.autocomplete-selected`, `.autocomplete-suggestion`.
- `cdkeys/views/css/admin_cdkeys.css` :
  - **Portée :** Back-office.
  - **Composants d'interface utilisateur principaux :** Style général pour les pages d'administration du module, y compris les listes, les formulaires et les éléments du tableau de bord.
  - **Sélecteurs de classe CSS clés :** `.cdkeys-admin-panel`, `.cdkeys-table`, `.cdkeys-form-group`.
- `cdkeys/views/css/cdkeys-admin.css` :
  - **Portée :** Back-office.
  - **Composants d'interface utilisateur principaux :** Style supplémentaire ou spécifique pour les interfaces d'administration, potentiellement en surchargeant ou en étendant `admin_cdkeys.css`.
  - **Sélecteurs de classe CSS clés :** `.cdkeys-dashboard-widget`, `.cdkeys-alert`.
- `cdkeys/views/css/css.css` :
  - **Portée :** Potentiellement à la fois Front-office et Back-office, ou styles utilitaires généraux.
  - **Composants d'interface utilisateur principaux :** Pourrait contenir des styles de base pour les éléments utilisés dans différentes parties du module.
  - **Sélecteurs de classe CSS clés :** Classes génériques qui pourraient être appliquées à divers éléments du module.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)

- `cdkeys/views/templates/hook/adminOrder.tpl` :
  - **Hook :** `displayAdminOrder`
  - **Sortie :** Affiche les informations de la clé CD directement dans la page de détails de la commande du Back Office de PrestaShop. Cela permet aux administrateurs de voir rapidement quelles clés ont été attribuées à une commande.
- `cdkeys/views/templates/hook/adminOrderFraud.tpl` :
  - **Hook :** `displayAdminOrderTop` (ou similaire, potentiellement `displayAdminOrder`)
  - **Sortie :** Affiche les informations ou les alertes liées à la fraude pour une commande sur la page de détails de la commande du Back Office.
- `cdkeys/views/templates/hook/my-account-16.tpl` :
  - **Hook :** `displayCustomerAccount` (pour PrestaShop 1.6.x)
  - **Sortie :** Ajoute un lien ou un bloc à la page « Mon compte » du client, le dirigeant vers sa section « Mes clés ».
- `cdkeys/views/templates/hook/my-account-17.tpl` :
  - **Hook :** `displayCustomerAccount` (pour PrestaShop 1.7.x, 8.x, 9.x)
  - **Sortie :** Similaire à `my-account-16.tpl`, mais adapté à la structure de modèle différente des versions plus récentes de PrestaShop, ajoutant un lien vers la section « Mes clés ».
- `cdkeys/views/templates/hook/orderDetailDisplayed.tpl` :
  - **Hook :** `displayOrderDetailDisplayed`
  - **Sortie :** Affiche les informations de la clé CD sur la page de détails de la commande du front-office du client.

#### Modèles d'administration (`views/templates/admin/`)

- `cdkeys/lib/emailTemplatesManager/views/buttonManager.tpl` :
  - **Objectif :** Rend les boutons ou les contrôles pour le gestionnaire de modèles d'e-mail.
- `cdkeys/lib/emailTemplatesManager/views/createTemplateForm.tpl` :
  - **Objectif :** Rend le formulaire de création de nouveaux modèles d'e-mail.
- `cdkeys/lib/emailTemplatesManager/views/editTemplateForm.tpl` :
  - **Objectif :** Rend le formulaire de modification des modèles d'e-mail existants.
- `cdkeys/lib/emailTemplatesManager/views/mainForm.tpl` :
  - **Objectif :** Le conteneur principal ou le formulaire pour l'interface de gestion des modèles d'e-mail.
- `cdkeys/lib/emailTemplatesManager/views/selectInput.tpl` :
  - **Objectif :** Rend un champ de sélection déroulant, probablement pour choisir des modèles d'e-mail ou des langues.
- `cdkeys/lib/searchTool/views/scripts.tpl` :
  - **Objectif :** Inclut des scripts JavaScript pour l'outil de recherche/la fonctionnalité d'autocomplétion.
- `cdkeys/views/templates/admin/cdkeys/helpers/list/list_action_email.tpl` :
  - **Objectif :** Rend un bouton d'action spécifique (par exemple, « Renvoyer l'e-mail ») dans un tableau `HelperList` dans les contrôleurs d'administration (par exemple, `AdminCdKeysArchiveController`).
- `cdkeys/views/templates/admin/customerGroups.tpl` :
  - **Objectif :** Rend l'interface de sélection des groupes de clients dans la configuration du module.
- `cdkeys/views/templates/admin/getCombinations.tpl` :
  - **Objectif :** Potentiellement utilisé pour afficher ou sélectionner des combinaisons de produits liées aux clés CD (par exemple, si différentes combinaisons nécessitent différents groupes de clés).
- `cdkeys/views/templates/admin/orderstates.tpl` :
  - **Objectif :** Rend la liste déroulante à sélection multiple pour « Sélectionner les états de commande » dans la configuration du module.
- `cdkeys/views/templates/admin/orderstatesRadio.tpl` :
  - **Objectif :** Rend la sélection par bouton radio pour « Sélectionner l'état de la commande » (pour le changement de statut) dans la configuration du module.
- `cdkeys/views/templates/admin/script.tpl` :
  - **Objectif :** Inclusion de script général pour les pages d'administration, éventuellement pour le JS spécifique au module.

#### Modèles Front-office (`views/templates/front/`)

- `cdkeys/views/templates/front/mykeys.tpl` :
  - **Objectif :** Le modèle principal pour afficher la liste des clés CD achetées par le client dans sa section « Mon compte ». Il itérera sur les données `cdkey_used` et présentera les clés, les détails de la commande et potentiellement les contrôles de pagination.

#### Modèles d'e-mail (`views/templates/email/`)

- `cdkeys/views/templates/email/multikey-instance.tpl` :
  - **Objectif :** C'est le modèle principal pour l'e-mail envoyé aux clients contenant leurs clés CD. Il sera rempli dynamiquement avec le nom du client, les détails de la commande et la ou les clés réelles.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

- `ps_cdkey_group` : Stocke les informations sur les groupes de clés CD.
  - `id_cdkey_group` (PK)
  - `name`
  - `date_add`
  - `date_upd`
- `ps_cdkey` : Stocke les clés CD individuelles.
  - `id_cdkey` (PK)
  - `id_cdkey_group` (FK vers `ps_cdkey_group`)
  - `key_value` (la chaîne de caractères de la clé CD réelle)
  - `status` (par exemple, 'available', 'used')
  - `date_add`
  - `date_upd`
- `ps_cdkey_used` : Stocke les enregistrements des clés CD attribuées aux commandes.
  - `id_cdkey_used` (PK)
  - `id_cdkey` (FK vers `ps_cdkey`)
  - `id_order` (FK vers `ps_orders`)
  - `id_customer` (FK vers `ps_customer`)
  - `id_product` (FK vers `ps_product`)
  - `date_add`

#### Enregistrements de configuration (`ps_configuration`)

- `CDKEYS_ENABLED` : (bool) Interrupteur principal.
- `CDKEYS_OSTATES` : (string) Liste des états de commande séparés par des virgules pour la livraison des clés.
- `CDKEYS_GROUPS` : (string) Liste des groupes de clients séparés par des virgules pour la livraison des clés.
- `CDKEYS_MAX_ORDERTOTAL` : (float) Valeur maximale de la commande pour la livraison automatique.
- `CDKEY_HOWDELIVER` : (bool) Envoyer plusieurs codes dans un seul e-mail.
- `CDKEYS_MULTITITLE` : (string) Titre de l'objet de l'e-mail.
- `CDKEY_STATUSCHANGE` : (bool) Changer le statut de la commande après la livraison.
- `CDKEYS_OSTATES_RADIO` : (int) ID de l'état de la commande à changer.
- `CDKEY_INC_INV` : (bool) Inclure les clés sur la facture.
- `CDKEY_PAGINATION` : (bool) Activer la pagination pour Mes clés.
- `CDKEY_PAGINATION_NB` : (int) Articles par page pour la pagination Mes clés.
- `IV_ROW_DELIMITER` : (string) Délimiteur de ligne CSV.
- `IV_COL_DELIMITER` : (string) Délimiteur de colonne CSV.
- `CDKEYS_ANALYTICS_*` : Divers paramètres pour l'analyse du tableau de bord.
- `CDKEYS_ALERT_COOLDOWN_HOURS` : (int) Temps de recharge pour les alertes de fraude.
- `CDKEYS_EXPORT_MASK_CODES` : (bool) Masquer les codes à l'exportation.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionOrderStatusPostUpdate` | Après la mise à jour (et l'enregistrement) du statut d'une commande. | Déclencheur principal pour la livraison des clés CD. Vérifie si le nouveau statut correspond aux états configurés et envoie les clés. |
| `displayAdminOrder` | Rend le contenu dans la page de détails de la commande du Back Office. | Affiche les clés CD attribuées pour la commande actuelle dans le panneau d'administration. |
| `ActionAdminControllerSetMedia` | Lors de l'initialisation d'un contrôleur d'administration et de la définition des médias (JS/CSS). | Injecte les fichiers JS et CSS spécifiques au module dans le Back Office pour les contrôleurs d'administration. |
| `displayCustomerAccount` | Rend le contenu dans la page « Mon compte » du client. | Ajoute un lien ou un bloc pour « Mes clés » dans le compte front-office du client. |
| `DisplayAdminOrderTop` | Rend le contenu en haut de la page de détails de la commande du Back Office. | Potentiellement utilisé pour afficher des alertes de fraude ou des informations récapitulatives liées aux clés CD pour la commande. |
| `actionOrderStatusUpdate` | Avant la mise à jour du statut d'une commande (ancien hook, `actionOrderStatusPostUpdate` est préféré). | Déclencheur secondaire ou de secours pour la livraison des clés CD, assurant la compatibilité avec les anciennes versions de PrestaShop ou des scénarios spécifiques. |
| `DisplayBackOfficeHeader` | Rend le contenu dans l'en-tête de toutes les pages du Back Office. | Injecte les JS/CSS globaux du Back Office ou les éléments de menu pour le module. |
| `displayHeader` | Rend le contenu dans la section `<head>` des pages du front-office. | Injecte les JS/CSS ou les balises meta spécifiques au front-office. |
| `displayOrderDetailDisplayed` | Rend le contenu dans la page de détails de la commande du front-office du client. | Affiche les clés CD attribuées directement sur la page de résumé de la commande du client. |
| `actionOrderHistoryAddAfter` | Après l'ajout d'une entrée d'historique de commande (changement de statut). | Pourrait être utilisé comme déclencheur alternatif pour la livraison des clés ou à des fins de journalisation liées aux changements de statut. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Vous y trouverez l'accès à vos modules achetés et aux canaux de support dédiés.
