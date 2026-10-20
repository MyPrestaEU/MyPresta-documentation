---
title: "Récompenses - Codes de réduction après les commandes - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Récompenses - Codes de réduction après les commandes par MyPresta.eu."
sidebar:
  label: "Récompenses - Codes de réduction après les commandes - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Rewards - Voucher codes after orders sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/rewards-voucher-codes-after-orders.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/rewards-voucher-codes-after-orders/)
>
> ---


# Récompenses - Codes de réduction après les commandes

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour qu'une boutique PrestaShop fonctionne correctement. Ce module n'a pas d'exigences d'hébergement inhabituelles ou supplémentaires au-delà d'une configuration PrestaShop standard.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Récompenses - Codes de réduction après les commandes)

C'est l'écran de configuration principal où vous définissez les règles de génération et d'envoi des codes de réduction.

#### Paramètres généraux

- **Activer le module :**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module surveillera activement les commandes et générera/enverra des bons selon vos règles.
    - *Lorsqu'il est désactivé :* Le module sera inactif, et aucun bon ne sera généré ou envoyé, quelles que soient les autres configurations.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple pour le marchand :** Vous avez terminé de configurer toutes vos règles et êtes prêt à lancer votre programme de récompenses. Activez-le pour commencer à envoyer des bons. Si vous devez suspendre temporairement le programme pour maintenance, désactivez-le.
- **États de commande pour la génération de bons :**

  - **Ce que fait ce paramètre :** Détermine quels statuts de commande déclencheront le processus de génération de bons. Seules les commandes qui atteignent l'un de ces statuts sélectionnés seront éligibles à une récompense.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est sélectionné :* Les commandes avec ces statuts seront vérifiées pour l'éligibilité au bon.
    - *Lorsqu'il est désélectionné :* Les commandes avec ces statuts seront ignorées par le module.
  - **Valeur recommandée :** Généralement « Paiement accepté » et « Livré ». Vous pourriez également inclure « Expédié » si vous souhaitez envoyer le bon plus tôt.
  - **Scénario / exemple pour le marchand :** Vous voulez vous assurer que les clients ne reçoivent un bon qu'après que leur paiement soit confirmé et que la commande soit en cours de traitement ou ait été livrée. Sélectionnez « Paiement accepté » et « Livré » pour éviter d'envoyer des bons pour les commandes annulées ou en attente.
- **Montant minimum de commande pour le bon :**

  - **Ce que fait ce paramètre :** Définit une valeur totale minimale (hors frais de port) qu'une commande doit atteindre pour être éligible à un bon.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur une valeur (par exemple, 50) :* Seules les commandes dont le total est supérieur ou égal à 50 déclencheront un bon.
    - *Lorsqu'il est défini sur 0 (ou vide) :* Toutes les commandes, quelle que soit leur valeur, seront éligibles (si les autres conditions sont remplies).
  - **Valeur recommandée :** Une valeur qui a du sens pour votre valeur moyenne de commande, ou 0 si vous souhaitez récompenser toutes les commandes.
  - **Scénario / exemple pour le marchand :** Vous souhaitez encourager les achats plus importants. Définissez-le sur 50 € afin que seuls les clients dépensant 50 € ou plus reçoivent une réduction, faisant du bon une récompense pour les transactions de plus grande valeur.

#### Paramètres du code de réduction

- **Préfixe du code de réduction :**

  - **Ce que fait ce paramètre :** Une chaîne de caractères qui apparaîtra au début de chaque code de réduction généré. Cela vous aide à identifier les bons de ce module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini (par exemple, « RÉCOMPENSE ») :* Les codes ressembleront à « RÉCOMPENSEABCD123 ».
    - *Lorsqu'il est vide :* Les codes seront purement des caractères aléatoires.
  - **Valeur recommandée :** Un préfixe court et descriptif comme « RÉCOMPENSE », « MERCI », ou les initiales de votre boutique.
  - **Scénario / exemple pour le marchand :** Vous gérez plusieurs promotions. L'utilisation de « RÉCOMPENSE » comme préfixe vous aide à identifier rapidement quels bons proviennent de ce module dans vos règles de réduction PrestaShop.
- **Longueur du code de réduction :**

  - **Ce que fait ce paramètre :** Définit le nombre total de caractères dans le code de réduction généré (y compris le préfixe).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur 10 avec un préfixe « RÉCOMPENSE » :* La partie aléatoire aura 4 caractères (10 - 6 pour « RÉCOMPENSE »).
    - *Lorsqu'il est défini sur un nombre inférieur :* Codes plus courts, potentiellement plus faciles à taper mais moins uniques.
    - *Lorsqu'il est défini sur un nombre supérieur :* Codes plus longs, plus sécurisés mais plus difficiles à taper.
  - **Valeur recommandée :** 8-12 caractères (y compris le préfixe) pour un bon équilibre entre sécurité et convivialité.
  - **Scénario / exemple pour le marchand :** Vous voulez que les codes soient faciles à retenir mais toujours uniques. Une longueur de 10-12 caractères est généralement suffisante.
- **Type de valeur du bon :**

  - **Ce que fait ce paramètre :** Détermine si le bon offre une réduction en pourcentage ou un montant fixe.
  - **Effet de la modification de ce paramètre :**
    - *Pourcentage :* Le bon déduira un pourcentage du total de la commande.
    - *Montant fixe :* Le bon déduira une valeur monétaire spécifique.
  - **Valeur recommandée :** Dépend de votre stratégie marketing. Le pourcentage est bon pour encourager les commandes plus importantes, le montant fixe est plus simple et plus clair.
  - **Scénario / exemple pour le marchand :** Vous voulez offrir 10 % de réduction sur la prochaine commande, vous sélectionnez donc « Pourcentage ». Si vous voulez offrir une réduction forfaitaire de 5 €, sélectionnez « Montant fixe ».
- **Valeur du bon :**

  - **Ce que fait ce paramètre :** La valeur de réduction réelle. Ce sera un pourcentage (par exemple, 10) ou un montant fixe (par exemple, 5.00) selon le paramètre « Type de valeur du bon ».
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur 10 et « Pourcentage » :* Les clients obtiennent 10 % de réduction.
    - *Lorsqu'il est défini sur 5.00 et « Montant fixe » :* Les clients obtiennent 5 € de réduction.
  - **Valeur recommandée :** Une valeur qui rend l'offre attrayante mais qui est durable pour votre entreprise.
  - **Scénario / exemple pour le marchand :** Vous décidez d'offrir une réduction de 15 %, vous entrez donc « 15 » ici après avoir sélectionné « Pourcentage » ci-dessus.
- **Montant minimum de commande pour l'utilisation du bon :**

  - **Ce que fait ce paramètre :** Définit un montant d'achat minimum requis pour que le client puisse utiliser le code de réduction généré.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur 20 :* Le client doit dépenser au moins 20 € sur sa prochaine commande pour appliquer le bon.
    - *Lorsqu'il est défini sur 0 (ou vide) :* Le bon peut être utilisé sur n'importe quelle commande, quelle que soit sa valeur.
  - **Valeur recommandée :** Une valeur légèrement supérieure à votre valeur moyenne de commande pour encourager la vente incitative, ou 0 si vous souhaitez une utilisabilité maximale.
  - **Scénario / exemple pour le marchand :** Vous voulez vous assurer que le bon encourage un nouvel achat, pas seulement un petit ajout. Définissez-le sur 25 €, de sorte que le client doive acheter quelque chose de substantiel pour utiliser son bon de 5 €.
- **Validité du bon (jours) :**

  - **Ce que fait ce paramètre :** Définit le nombre de jours pendant lesquels le code de réduction généré sera valide à partir de la date de sa création.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur 30 :* Le bon expirera 30 jours après son envoi.
    - *Lorsqu'il est défini sur 0 (ou vide) :* Le bon sera valide indéfiniment (non recommandé, car cela supprime l'urgence).
  - **Valeur recommandée :** 30-90 jours pour créer une urgence sans être trop restrictif.
  - **Scénario / exemple pour le marchand :** Vous voulez que les clients utilisent leur bon dans un délai raisonnable. Définissez-le sur 60 jours pour leur donner deux mois pour effectuer un autre achat.
- **Appliquer le bon à des groupes de clients spécifiques :**

  - **Ce que fait ce paramètre :** Vous permet de restreindre l'utilisation du bon généré à des groupes de clients spécifiques (par exemple, « Clients VIP », « Grossistes »).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est sélectionné :* Seuls les clients appartenant aux groupes choisis peuvent utiliser le bon.
    - *Lorsqu'il est désélectionné (ou tous les groupes sélectionnés) :* Tout client peut utiliser le bon.
  - **Valeur recommandée :** Laissez tout sélectionné, sauf si vous avez une stratégie de segmentation spécifique.
  - **Scénario / exemple pour le marchand :** Vous souhaitez offrir une réduction spéciale uniquement à votre groupe de « Clients enregistrés ». Sélectionnez uniquement ce groupe ici.
- **Appliquer le bon à des produits/catégories spécifiques :**

  - **Ce que fait ce paramètre :** Vous permet de restreindre l'applicabilité du bon à certains produits ou catégories de produits.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est sélectionné :* Le bon ne s'appliquera qu'aux articles des produits/catégories choisis.
    - *Lorsqu'il est désélectionné (ou aucun sélectionné) :* Le bon s'applique à tous les produits du panier.
  - **Valeur recommandée :** Laissez désélectionné pour les réductions générales à l'échelle du magasin. Utilisez ceci pour des promotions ciblées.
  - **Scénario / exemple pour le marchand :** Vous souhaitez promouvoir une nouvelle collection spécifique. Vous pouvez configurer le bon pour qu'il ne s'applique qu'aux produits de cette catégorie.
- **Exclure les produits en promotion :**

  - **Ce que fait ce paramètre :** Si activé, le bon ne peut pas être utilisé sur des produits déjà en solde ou ayant un prix spécifique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Empêche le « cumul » des réductions, garantissant que les clients n'obtiennent pas de doubles réductions.
    - *Lorsqu'il est désactivé :* Les bons peuvent être appliqués aux articles déjà réduits.
  - **Valeur recommandée :** OUI, pour protéger vos marges bénéficiaires.
  - **Scénario / exemple pour le marchand :** Vous organisez une vente de 20 % sur tout le magasin. Vous ne voulez pas que les clients utilisent leur bon de récompense en plus de cela, leur donnant effectivement 30 % de réduction. Activez ceci pour l'empêcher.
- **Exclure les frais de port :**

  - **Ce que fait ce paramètre :** Détermine si la réduction du bon s'applique aux frais de port de la commande.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le bon ne réduit que le total des produits, pas les frais de port.
    - *Lorsqu'il est désactivé :* Le bon peut réduire la valeur totale de la commande, y compris les frais de port.
  - **Valeur recommandée :** OUI, car les frais de port sont souvent fixes et ne font pas partie de votre marge produit.
  - **Scénario / exemple pour le marchand :** Vous offrez la livraison gratuite au-delà d'un certain seuil. Vous voulez que le bon n'affecte que les prix des produits, pas les frais de port. Activez ceci.
- **Bon pour la N-ième commande :**

  - **Ce que fait ce paramètre :** C'est une fonctionnalité puissante qui vous permet de spécifier pour quel numéro de commande (1ère, 2ème, 3ème, etc.) un client reçoit un bon.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur 1 :* Seule la toute première commande du client déclenchera un bon.
    - *Lorsqu'il est défini sur 2 :* Seule sa deuxième commande déclenchera un bon.
    - *Lorsqu'il est défini sur 0 (ou vide) :* Chaque commande éligible déclenchera un bon (si les autres conditions sont remplies).
  - **Valeur recommandée :** 1 pour une offre de « bienvenue », ou 0 pour un programme de fidélité général. Vous pouvez également créer plusieurs règles (voir section 4.2) pour différentes N-ièmes commandes.
  - **Scénario / exemple pour le marchand :** Vous voulez offrir un « merci » spécial aux premiers acheteurs. Définissez-le sur « 1 ». Pour un programme de fidélité général, laissez-le à « 0 » ou créez des règles spécifiques pour les 2ème, 3ème, etc., commandes.

#### Paramètres du modèle d'e-mail

- **Objet de l'e-mail :**

  - **Ce que fait ce paramètre :** La ligne d'objet de l'e-mail que les clients reçoivent contenant leur code de réduction.
  - **Effet de la modification de ce paramètre :** C'est ce que les clients voient dans leur boîte de réception. Une ligne d'objet attrayante augmente les taux d'ouverture.
  - **Valeur recommandée :** Quelque chose d'engageant comme « Votre réduction spéciale pour votre prochaine commande ! » ou « Merci ! Voici un cadeau de notre part. »
  - **Scénario / exemple pour le marchand :** Vous voulez qu'il soit clair qu'il s'agit d'une récompense. Définissez l'objet sur « Votre bon exclusif de [Nom de votre boutique] ! »
- **Contenu de l'e-mail :**

  - **Ce que fait ce paramètre :** Le corps principal de l'e-mail. Vous pouvez utiliser des espaces réservés comme `{customer_name}`, `{voucher_code}`, `{voucher_value}`, `{min_order_total}`, `{validity_days}` pour personnaliser le message.
  - **Effet de la modification de ce paramètre :** C'est là que vous communiquez la valeur du bon et comment l'utiliser. Un message clair et amical encourage l'utilisation.
  - **Valeur recommandée :** Un message de bienvenue, des instructions claires et tous les détails pertinents du bon.
  - **Scénario / exemple pour le marchand :** « Cher {customer\_name}, merci pour votre récent achat ! En guise de remerciement, voici un code de réduction de {voucher\_value} pour votre prochaine commande : **{voucher\_code}**. Ce bon est valable {validity\_days} jours et peut être utilisé sur les commandes de plus de {min\_order\_total}. Bon shopping ! »
- **Envoyer l'e-mail au client :**

  - **Ce que fait ce paramètre :** Contrôle si l'e-mail contenant le bon est réellement envoyé au client.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clients reçoivent l'e-mail.
    - *Lorsqu'il est désactivé :* Les bons sont toujours générés (si activé), mais les clients ne reçoivent pas de notification par e-mail. Vous devrez alors communiquer le code de réduction par un autre canal.
  - **Valeur recommandée :** OUI, car l'e-mail est la méthode de livraison principale pour ce module.
  - **Scénario / exemple pour le marchand :** Vous avez tout configuré et souhaitez que les clients reçoivent leurs récompenses. Activez ceci. Si vous testez ou préférez envoyer les codes manuellement, vous pouvez le désactiver temporairement.

#### Paramètres de la tâche Cron

- **URL de la tâche Cron :**
  - **Ce que fait ce paramètre :** C'est une URL unique qui, lorsqu'elle est accédée, déclenche le module pour vérifier les nouvelles commandes éligibles et générer/envoyer des bons.
  - **Effet de la modification de ce paramètre :** Cette URL est cruciale pour l'automatisation du module. Elle doit être appelée régulièrement.
  - **Valeur recommandée :** NE PAS modifier cette URL. Copiez-la et configurez-la dans le panneau de contrôle de votre hébergement.
  - **Scénario / exemple pour le marchand :** Vous copiez cette URL et la collez dans le gestionnaire de tâches cron de votre hébergeur (par exemple, cPanel, Plesk) pour qu'elle s'exécute toutes les 15-30 minutes. Cela garantit que les bons sont envoyés rapidement après le traitement des commandes.

### 2.2 Écran d'administration dédié : Liste des récompenses (Back Office > Récompenses > Liste des récompenses)

Cet écran offre un aperçu complet de tous les codes de réduction qui ont été générés par le module. Il agit comme un journal et une interface de gestion pour votre programme de récompenses.

- **Nom de l'écran et emplacement du menu :** **Liste des récompenses** (trouvé sous un nouvel élément de menu « Récompenses » dans votre Back Office PrestaShop, ou potentiellement sous « Catalogue » ou « Marketing » selon votre version et thème PrestaShop).
- **Actions et paramètres disponibles :**
  - **Colonnes du tableau :** Vous verrez un tableau avec les colonnes suivantes :
    - **ID :** L'identifiant unique de l'entrée de récompense.
    - **ID de commande :** L'ID de la commande PrestaShop qui a déclenché cette récompense.
    - **Client :** Le nom du client qui a reçu le bon.
    - **E-mail :** L'adresse e-mail du client.
    - **Référence de commande :** Le numéro de référence unique de la commande.
    - **Code de récompense :** Le code de réduction réel généré et envoyé au client.
    - **Date de génération :** La date et l'heure de la génération du bon.
  - **Filtrage et recherche :** Vous pouvez généralement filtrer ou rechercher par l'une de ces colonnes (par exemple, rechercher un e-mail client spécifique, un ID de commande ou un code de réduction) pour trouver des entrées de récompense spécifiques.
  - **Pas de boutons « Ajouter/Modifier » :** Cet écran est principalement destiné à la visualisation des récompenses générées. Les bons sont créés automatiquement en fonction de votre configuration, et non ajoutés manuellement ici.
- **Effet des modifications :** Cet écran est un journal en lecture seule. Les modifications apportées à la configuration du module (Section 4.1) affecteront les *futures* générations de bons, mais les entrées existantes ici reflètent les événements passés.
- **Flux de travail recommandé pour la gestion quotidienne du magasin :**
  - Vérifiez périodiquement cette liste pour surveiller l'activité de votre programme de récompenses.
  - Si un client prétend ne pas avoir reçu de bon, vous pouvez rapidement rechercher sa commande ici, trouver le « Code de récompense » et confirmer sa date de génération. Vous pouvez ensuite fournir manuellement le code au client si nécessaire.
  - Utilisez les options de filtrage pour analyser quelles commandes déclenchent des récompenses ou pour résoudre des problèmes spécifiques de clients.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activer le module | OUI | Interrupteur principal pour la fonctionnalité du module. |
| | États de commande pour la génération de bons | Paiement accepté, Livré | Définit les statuts de commande qui déclenchent la génération de bons. |
| | Montant minimum de commande pour le bon | 0 (ou votre valeur souhaitée) | Valeur de commande minimale pour qu'une commande soit éligible à un bon. |
| | Préfixe du code de réduction | RÉCOMPENSE (ou votre choix) | Préfixe pour les codes de réduction générés. |
| | Longueur du code de réduction | 8-12 | Longueur totale du code de réduction. |
| | Type de valeur du bon | Pourcentage / Montant fixe | Choisissez entre une réduction en pourcentage ou un montant fixe. |
| | Valeur du bon | Votre valeur souhaitée (par exemple, 10 ou 5.00) | La valeur de réduction réelle du bon. |
| | Montant minimum de commande pour l'utilisation du bon | 0 (ou votre valeur souhaitée) | Valeur de commande minimale requise pour *utiliser* le bon. |
| | Validité du bon (jours) | 30-90 | Combien de jours le bon est valide après sa génération. |
| | Appliquer le bon à des groupes de clients spécifiques | Tous sélectionnés | Restreint l'utilisation du bon aux groupes de clients sélectionnés. |
| | Appliquer le bon à des produits/catégories spécifiques | Aucun sélectionné | Restreint l'utilisation du bon aux produits/catégories sélectionnés. |
| | Exclure les produits en promotion | OUI | Empêche les bons de s'appliquer aux articles déjà réduits. |
| | Exclure les frais de port | OUI | Empêche les bons de réduire les frais de port. |
| | Bon pour la N-ième commande | 0 (ou 1 pour la première commande) | Spécifie pour quel numéro de commande (1ère, 2ème, etc.) un bon est généré. |
| | Objet de l'e-mail | Votre réduction spéciale ! | Ligne d'objet de l'e-mail contenant le bon. |
| | Contenu de l'e-mail | Message personnalisé avec des espaces réservés | Corps de l'e-mail, y compris les détails du bon. |
| | Envoyer l'e-mail au client | OUI | Contrôle si l'e-mail du bon est envoyé au client. |
| | URL de la tâche Cron | NE PAS modifier | URL essentielle pour la génération automatisée de bons. |
| **Liste des récompenses** | ID, ID de commande, Client, E-mail, Référence de commande, Code de récompense, Date de génération | N/A (lecture seule) | Affiche un journal de tous les bons générés pour la surveillance et le dépannage. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes clients ne reçoivent pas les e-mails de bon. Que dois-je vérifier ?**
R :

1. **Module activé ?** Vérifiez que « Activer le module » est réglé sur OUI dans la configuration du module.
2. **Statuts de commande :** Assurez-vous que le statut de la commande correspond à l'un des « États de commande pour la génération de bons » que vous avez sélectionnés.
3. **Tâche Cron :** Vérifiez que votre tâche cron est correctement configurée et s'exécute régulièrement sur votre hébergement. L'« URL de la tâche Cron » doit être appelée pour que le module traite les commandes.
4. **Envoi d'e-mails activé :** Assurez-vous que « Envoyer l'e-mail au client » est réglé sur OUI.
5. **Dossier spam :** Demandez aux clients de vérifier leurs dossiers de spam ou de courrier indésirable.
6. **Paramètres d'e-mail PrestaShop :** Vérifiez la configuration principale des e-mails de votre PrestaShop (Paramètres avancés > E-mail) pour vous assurer que les e-mails sont envoyés avec succès depuis votre boutique.

**Q : Les bons sont générés, mais ils ne semblent pas fonctionner pour les clients.**
R :

1. **Validité du bon :** Vérifiez le paramètre « Validité du bon (jours) ». Le bon a-t-il expiré ?
2. **Montant minimum de commande pour l'utilisation :** Le panier actuel du client atteint-il le « Montant minimum de commande pour l'utilisation du bon » ?
3. **Groupes de clients :** Le client fait-il partie des « Appliquer le bon à des groupes de clients spécifiques » sélectionnés ?
4. **Restrictions de produits/catégories :** Les produits dans le panier du client sont-ils éligibles en fonction de « Appliquer le bon à des produits/catégories spécifiques » ?
5. **Produits en promotion exclus :** Le client essaie-t-il d'utiliser le bon sur un produit déjà en promotion, et « Exclure les produits en promotion » est-il activé ?
6. **Fautes de frappe :** Demandez au client de vérifier attentivement le code de réduction pour toute faute de frappe.

**Q : Je souhaite offrir différents bons pour différents numéros de commande (par exemple, 1ère, 2ème, 5ème commande). Comment faire ?**
R : La description du module indique la prise en charge de « nombreux types d'actions comme : bon pour la première commande, bon pour la deuxième commande, la cinquième, la sixième, etc. » Cela implique que le module dispose d'un mécanisme pour définir plusieurs règles basées sur la N-ième commande.

- **Vérifier les onglets de règles multiples :** Recherchez des onglets ou des sections supplémentaires dans la configuration du module qui vous permettent d'« Ajouter une nouvelle règle » ou de définir des configurations distinctes pour différentes valeurs de « N-ième commande ». Si une telle interface existe, vous créeriez une règle distincte pour chaque N-ième commande avec ses paramètres de bon spécifiques.
- **Si un seul champ « Bon pour la N-ième commande » existe :** Si le module ne présente qu'un seul champ « Bon pour la N-ième commande » sur la page de configuration principale, cela signifie que vous ne pouvez définir qu'une *seule* telle règle à la fois. Pour implémenter un système à plusieurs niveaux, vous devrez modifier manuellement ce paramètre après une certaine période ou déterminer si la version actuelle du module prend en charge cette fonctionnalité avancée via une interface moins évidente. Pour la plupart des utilisateurs, le régler sur `0` (chaque commande) ou `1` (première commande uniquement) est le cas d'utilisation principal.

**Q : Le module ralentit mon Back Office / Front Office.**
R : Ce module fonctionne principalement en arrière-plan via une tâche cron et a un impact minimal sur les performances du front-office. Si vous remarquez des ralentissements :

1. **Vider le cache :** Allez dans **Paramètres avancés > Performances** et videz le cache de votre PrestaShop.
2. **Vérifier les ressources du serveur :** Surveillez l'utilisation du CPU et de la mémoire de votre serveur, surtout lorsque la tâche cron s'exécute. Si votre serveur est sous-dimensionné, même des tâches simples peuvent provoquer des ralentissements.
3. **Autres modules :** Désactivez temporairement les autres modules récemment installés pour voir s'il y a un conflit.

**Q : Puis-je personnaliser davantage le modèle d'e-mail ?**
R : Oui, le module fournit les champs « Objet de l'e-mail » et « Contenu de l'e-mail » avec des espaces réservés pour une personnalisation de base. Pour des modifications de conception avancées (par exemple, ajouter le logo de votre boutique, changer les polices/couleurs), vous devrez généralement modifier directement les fichiers de modèle d'e-mail du module. Cela nécessite généralement un webmaster ou un développeur. La structure interne du module suggère qu'il utilise `lib/emailTemplatesManager`, ce qui pourrait offrir une gestion de modèles plus avancée au sein du module lui-même, mais la configuration principale se fait via les champs de texte.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Récompenses - Codes de réduction après les commandes » suit une architecture de module PrestaShop standard, tirant parti des principes MVC le cas échéant. Sa fonctionnalité principale repose sur un mécanisme de tâche cron qui vérifie périodiquement les commandes éligibles et, après les avoir trouvées, génère des objets `CartRule` (bons) PrestaShop et envoie des e-mails. Le module étend `Module` pour sa fonctionnalité principale et utilise `AdminController` pour son interface de gestion du Back Office. Il intègre également plusieurs bibliothèques utilitaires pour la gestion des modèles d'e-mail et la fonctionnalité de recherche.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `controllers/front/cronJob.php`
  - **Nom de la classe :** `OrdercouponsCronJobModuleFrontController` (probable, basé sur le nom du fichier)
  - **Classe parente :** `ModuleFrontController`
  - **Responsabilité :** Ce contrôleur est conçu pour être accédé via l'URL de la tâche Cron fournie dans la configuration du module. Lorsqu'il est invoqué, il déclenche la logique principale du fichier de module `cronjob.php` pour traiter les commandes, générer des bons et envoyer des e-mails. Il ne rend généralement aucun contenu front-office mais exécute des tâches en arrière-plan.
- `controllers/front/index.php`
  - **Nom de la classe :** `OrdercouponsIndexModuleFrontController` (probable)
  - **Classe parente :** `ModuleFrontController`
  - **Responsabilité :** Il s'agit souvent d'un espace réservé ou d'un simple contrôleur de redirection. Dans de nombreux modules, `index.php` dans un répertoire de contrôleur garantit simplement que l'accès direct au répertoire n'entraîne pas une liste de répertoires, ou il peut contenir une logique minimale pour une vue front-office par défaut si le module en avait une. Pour ce module, il est peu probable qu'il ait une responsabilité significative de rendu front-office.

#### Contrôleurs d'administration Back-Office

- `controllers/admin/AdminOrderCouponsRewards.php`
  - **Nom de la classe :** `AdminOrderCouponsRewardsController`
  - **Classe parente :** `ModuleAdminController` (ou `AdminController` dans les versions plus anciennes)
  - **Nom de l'onglet :** « Liste des récompenses » (sous un élément de menu « Récompenses »)
  - **Entité gérée :** `orewards_list` (probablement une table de base de données personnalisée pour l'enregistrement des récompenses générées).
  - **Responsabilité :** Ce contrôleur gère la « Liste des récompenses » dans le Back Office de PrestaShop. Il affiche une liste de tous les codes de réduction générés, les ID de commande associés, les détails du client et les dates de génération. Il utilise `HelperList` pour le rendu du tableau et offre des capacités de filtrage. Il n'autorise pas la création ou la modification manuelle des récompenses, car elles sont générées automatiquement.
- `controllers/admin/index.php`
  - **Nom de la classe :** `AdminOrdercouponsIndexController` (probable)
  - **Classe parente :** `ModuleAdminController` (ou `AdminController`)
  - **Responsabilité :** Similaire à `index.php` du front-office, il s'agit probablement d'un espace réservé ou d'un contrôleur par défaut pour la section d'administration, assurant la protection du répertoire ou fournissant une vue de secours. La fonctionnalité d'administration principale est gérée par `AdminOrderCouponsRewards.php`.

### 4.3 Classes et modèles principaux (`classes/`)

L'inventaire fourni n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que la logique principale du module pour la génération de bons pourrait être directement dans le fichier de module `cronjob.php` ou utilise l'`ObjectModel` `CartRule` (Réduction) intégré à PrestaShop et ses méthodes associées.

- **Interaction `CartRule` :** Le module interagirait directement avec la classe `CartRule` de PrestaShop pour créer de nouveaux codes de réduction. Cela implique de définir des propriétés comme `code`, `value`, `reduction_type`, `minimum_amount`, `date_from`, `date_to`, `quantity`, `quantity_per_user`, `id_customer`, `id_group`, `id_product`, `id_category`, `reduction_exclude_special`, `free_shipping`, etc., en fonction de la configuration du module.
- **Table personnalisée `orewards_list` :** Bien qu'aucun `ObjectModel` ne soit explicitement listé, l'`AdminOrderCouponsRewardsController` gère `orewards_list`. Cela implique fortement qu'une table de base de données personnalisée `ps_orewards_list` (ou un préfixe similaire) existe pour enregistrer les récompenses générées. Le contrôleur interrogerait directement cette table ou utiliserait une couche d'accès aux données simple.

### 4.4 Actifs JavaScript (`views/js/`)

- `ordercoupons/js/script.js`
  - **Portée :** Probablement Back-office.
  - **Responsabilité :** JavaScript général pour la page de configuration du module ou les écrans d'administration. Cela pourrait inclure la validation de formulaire, les appels AJAX pour l'enregistrement des paramètres, les mises à jour dynamiques de l'interface utilisateur ou les écouteurs d'événements pour des options de configuration spécifiques.
- `ordercoupons/lib/emailTemplatesManager/js/emailTemplatesManager.js`
  - **Portée :** Back-office.
  - **Responsabilité :** Gère l'interface d'édition des modèles d'e-mail. Ce script gérerait l'insertion dynamique des espaces réservés, les capacités d'édition de texte enrichi, la fonctionnalité de prévisualisation et l'enregistrement du contenu des e-mails.
- `ordercoupons/lib/searchTool/views/js/autocomplete.js`
  - **Portée :** Back-office.
  - **Responsabilité :** Fournit une fonctionnalité d'autocomplétion pour les champs de saisie, probablement utilisée pour sélectionner des produits, des catégories ou des groupes de clients spécifiques dans les formulaires de configuration du module. Il gérerait les requêtes AJAX pour récupérer les résultats de recherche et les afficher à l'utilisateur.
- `ordercoupons/lib/voucherengine/script.js`
  - **Portée :** Back-office.
  - **Responsabilité :** JavaScript spécifique lié au moteur de génération de bons. Cela pourrait inclure la logique pour le calcul dynamique de la longueur du code de bon, la validation des valeurs de bon ou l'interaction avec les paramètres `CartRule` dans le formulaire de configuration.

### 4.5 Feuilles de style CSS (`views/css/`)

- `ordercoupons/css.css`
  - **Portée :** Principalement Back-office, potentiellement quelques éléments front-office si le module avait des éléments visibles. Compte tenu de la nature du module, il s'agit principalement de style d'administration.
  - **Composants d'interface utilisateur principaux :** Style général pour la page de configuration du module et le tableau « Liste des récompenses ».
  - **Sélecteurs de classe CSS clés :** `.ordercoupons-config`, `.ordercoupons-table`, `.ordercoupons-form-group`.
- `ordercoupons/lib/emailTemplatesManager/css/emailTemplatesManager.css`
  - **Portée :** Back-office.
  - **Composants d'interface utilisateur principaux :** Styles pour l'interface de l'éditeur de modèles d'e-mail, y compris les zones de texte, les boutons et les sections de prévisualisation.
  - **Sélecteurs de classe CSS clés :** `.email-template-editor`, `.template-preview`.
- `ordercoupons/lib/searchTool/views/css/autocomplete.css`
  - **Portée :** Back-office.
  - **Composants d'interface utilisateur principaux :** Style pour les listes déroulantes d'autocomplétion et les champs de saisie.
  - **Sélecteurs de classe CSS clés :** `.autocomplete-container`, `.autocomplete-results`, `.autocomplete-item`.
- `ordercoupons/lib/voucherengine/ps16.css`
  - **Portée :** Back-office.
  - **Composants d'interface utilisateur principaux :** Ajustements de style spécifiques pour la compatibilité PrestaShop 1.6 ou des éléments spécifiques liés au moteur de bons, garantissant une apparence cohérente sur différentes versions de PS.
  - **Sélecteurs de classe CSS clés :** `.voucher-engine-settings`, `.ps16-compat`.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)

L'inventaire ne liste aucun modèle directement sous `views/templates/hook/`. Cela confirme que le module ne rend aucun contenu visuel directement dans les hooks PrestaShop standard comme `displayHeader`, `displayRightColumn`, `displayFooter`, etc. Son interaction front-office est purement par e-mail.

#### Modèles d'administration (`views/templates/admin/`)

- `ordercoupons/views/templates/admin/admin.tpl`
  - **Objectif :** Le modèle principal pour la page de configuration du module (accessible via `getContent()` dans `cronjob.php`). Il contiendrait la structure du formulaire pour tous les paramètres décrits dans la section 4.1.
- `ordercoupons/views/templates/admin/customerGroups.tpl`
  - **Objectif :** Un modèle partiel probablement utilisé dans `admin.tpl` pour rendre l'interface de sélection des « Appliquer le bon à des groupes de clients spécifiques ».
- `ordercoupons/views/templates/admin/orderstates.tpl`
  - **Objectif :** Un modèle partiel probablement utilisé dans `admin.tpl` pour rendre l'interface de sélection des « États de commande pour la génération de bons ».
- `ordercoupons/views/templates/admin/scripts.tpl`
  - **Objectif :** Un modèle partiel utilisé pour inclure des fichiers JavaScript ou du JavaScript en ligne spécifique à la page de configuration de l'administration. C'est une pratique courante pour séparer le JS de la structure HTML principale.

#### Modèles Front-office (`views/templates/front/`)

L'inventaire ne liste aucun modèle directement sous `views/templates/front/`. Cela est cohérent avec le comportement du module qui n'affiche pas de contenu front-office.

#### Modèles de bibliothèque

- `ordercoupons/lib/emailTemplatesManager/views/buttonManager.tpl`
- `ordercoupons/lib/emailTemplatesManager/views/createTemplateForm.tpl`
- `ordercoupons/lib/emailTemplatesManager/views/editTemplateForm.tpl`
- `ordercoupons/lib/emailTemplatesManager/views/mainForm.tpl`
- `ordercoupons/lib/emailTemplatesManager/views/selectInput.tpl`
  - **Objectif :** Ces modèles font partie de la bibliothèque `emailTemplatesManager` et sont utilisés pour rendre l'interface de gestion et d'édition des modèles d'e-mail dans la configuration du module. `mainForm.tpl` serait probablement le point d'entrée principal, les autres étant des partiels pour des éléments d'interface utilisateur spécifiques.
- `ordercoupons/lib/searchTool/views/scripts.tpl`
  - **Objectif :** Un modèle pour inclure des fichiers JavaScript ou des scripts en ligne pour la bibliothèque `searchTool`, spécifiquement pour la fonctionnalité d'autocomplétion.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

- **`ps_configuration`** : Le module stocke ses paramètres de configuration (par exemple, `ORDERCOUPONS_ENABLED`, `ORDERCOUPONS_ORDER_STATES`, `ORDERCOUPONS_VOUCHER_VALUE`) dans la table `ps_configuration` standard de PrestaShop.
- **`ps_orewards_list` (Table personnalisée implicite)** : Basé sur l'`AdminOrderCouponsRewardsController` gérant `orewards_list`, il est très probable que le module crée une table de base de données personnalisée, probablement nommée `ps_orewards_list`, pour enregistrer chaque bon généré.
  - **Schéma (Champs probables) :**
    - `id_orewards_list` (CLÉ PRIMAIRE, INT)
    - `id_order` (INT)
    - `id_customer` (INT)
    - `customer_email` (VARCHAR)
    - `order_reference` (VARCHAR)
    - `reward_code` (VARCHAR)
    - `date_add` (DATETIME)

#### Tableau des hooks enregistrés

La description du module mentionne « Hooks Front-Office : Header, Columns, Product, ou Footer ». Cependant, l'inventaire des fichiers et la fonction principale du module (envoi de bons par e-mail) suggèrent que ceux-ci ne sont probablement *pas* utilisés pour afficher du contenu, mais peut-être pour le traitement interne ou le chargement d'actifs si le module avait des composants front-end. Compte tenu de la nature du module, les hooks les plus critiques sont les hooks d'action.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionValidateOrder` | Après qu'une commande a été validée et enregistrée avec succès dans la base de données. | C'est le hook le plus probable pour que le module détecte les nouvelles commandes qui doivent être traitées pour la génération de bons. Le module écouterait cet événement pour identifier les candidats potentiels. |
| `actionOrderStatusPostUpdate` | Après qu'un statut de commande a été modifié dans le Back Office. | Crucial pour que le module vérifie si une commande a atteint l'un des « États de commande pour la génération de bons » configurés (par exemple, « Paiement accepté », « Livré »). C'est là que la tâche cron déclencherait probablement la logique de génération de bons. |
| `displayBackOfficeHeader` | Rend le contenu dans la section `<head>` du Back Office. | Utilisé pour inclure les fichiers CSS et JavaScript spécifiques au module pour les pages de configuration de l'administration et l'écran « Liste des récompenses ». |
| `moduleRoutes` | Permet aux modules de définir des URL conviviales personnalisées. | Moins probable pour ce module, mais possible s'il avait besoin d'une route spécifique pour sa tâche cron ou d'autres processus internes. |
| `displayHeader` | Rend le contenu dans la section `<head>` du front office. | Si le module devait charger des JS/CSS globaux pour d'éventuelles futures fonctionnalités front-end, ou à des fins de suivi. (Improbable pour la fonctionnalité actuelle). |
| `displayRightColumn` / `displayLeftColumn` | Rend le contenu dans les colonnes latérales du front office. | Non utilisé pour la fonctionnalité actuelle de ce module. |
| `displayFooter` | Rend le contenu dans le pied de page du front office. | Non utilisé pour la fonctionnalité actuelle de ce module. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Récompenses - Codes de réduction après les commandes », veuillez vous référer à votre compte client sur MyPresta.eu. Vous pouvez télécharger les nouvelles versions depuis votre historique de commandes et accéder aux canaux de support dédiés pour toute assistance technique ou question.
