---
title: "Bon d'achat pour commentaire produit - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Bon d'achat pour commentaire produit' par MyPresta.eu."
sidebar:
  label: "Bon d'achat pour commentaire produit - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Voucher for product comment sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-for-product-comment.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/voucher-for-product-comment/)
>
> ---


# Bon d'achat pour commentaire produit

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour que PrestaShop fonctionne correctement. Aucune extension supplémentaire spécifique n'est nécessaire pour ce module.

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est la zone de configuration principale du module « Bon d'achat pour commentaire produit ». Vous y trouverez tous les paramètres liés aux rappels de commentaires et à la génération de bons d'achat.

#### **Paramètres de rappel de commentaire**

-   **Demander la permission d'envoyer des rappels**

    *   **Ce que fait ce paramètre :** Si activé, une case à cocher apparaîtra sur vos formulaires d'inscription client et de mise à jour d'identité (Mon Compte > Informations) demandant aux clients s'ils acceptent de recevoir des rappels de commentaires. Ceci est important pour la conformité au RGPD et le respect de la vie privée des clients.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'activé :* Les clients doivent explicitement accepter de recevoir des rappels. Seuls les clients qui cochent cette case recevront des e-mails de rappel.
        *   *Lorsqu'désactivé :* Tous les clients qui remplissent d'autres critères (par exemple, produits achetés, n'ont pas commenté) recevront des rappels, sans consentement explicite.
    *   **Valeur recommandée :** OUI (Fortement recommandé pour la conformité au RGPD et de meilleures relations client).
    *   **Scénario / exemple de marchand :** Vous voulez vous assurer que vos pratiques marketing sont conformes aux réglementations sur la protection des données. L'activation de cette option donne aux clients le contrôle de leurs préférences de communication.
-   **Envoyer un rappel de commentaire**

    *   **Ce que fait ce paramètre :** C'est l'interrupteur principal de la fonction de rappel de commentaire. Si désactivé, aucun e-mail de rappel de commentaire ne sera envoyé, quels que soient les autres paramètres.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'activé :* Le module enverra activement des e-mails de rappel en fonction de vos autres paramètres.
        *   *Lorsqu'désactivé :* Aucun e-mail de rappel ne sera envoyé.
    *   **Valeur recommandée :** OUI
    *   **Scénario / exemple de marchand :** Vous avez décidé de collecter activement plus d'avis et souhaitez commencer à envoyer des rappels.
-   **Rappeler les commentaires après :**

    *   **Ce que fait ce paramètre :** Définit le nombre de jours après qu'une commande atteint un statut spécifique (défini ci-dessous) que le premier e-mail de rappel de commentaire sera envoyé.
    *   **Effet de la modification de ce paramètre :**
        *   *Modification du nombre :* Détermine le délai. Un délai plus court signifie que les clients reçoivent des rappels plus tôt ; un délai plus long leur donne plus de temps avant d'être sollicités.
    *   **Valeur recommandée :** 7 jours (Donne aux clients suffisamment de temps pour recevoir et utiliser le produit).
    *   **Scénario / exemple de marchand :** Vous voulez donner aux clients une semaine pour recevoir leur produit et se forger une opinion avant de demander un avis.
-   **Répéter le rappel**

    *   **Ce que fait ce paramètre :** Si un client n'a toujours pas laissé de commentaire après le rappel initial, ce paramètre détermine si et quand un deuxième rappel doit être envoyé.
    *   **Effet de la modification de ce paramètre :**
        *   *Définir un nombre (par exemple, 14) :* Un deuxième rappel sera envoyé 14 jours après le *premier* rappel, si aucun commentaire n'a été laissé.
        *   *Définir à 0 ou laisser vide :* Aucun deuxième rappel ne sera envoyé.
    *   **Valeur recommandée :** 14 (Fournit un suivi doux sans être trop agressif).
    *   **Scénario / exemple de marchand :** Certains clients pourraient manquer le premier e-mail ou simplement oublier. Un deuxième rappel après deux semaines peut attirer leur attention à nouveau.
-   **Titre de l'e-mail**

    *   **Ce que fait ce paramètre :** Vous permet de personnaliser l'objet des e-mails de rappel de commentaire. Ceci est crucial pour les taux d'ouverture des e-mails.
    *   **Effet de la modification de ce paramètre :**
        *   *Modification du texte :* Modifie directement l'objet que les clients voient dans leur boîte de réception.
    *   **Valeur recommandée :** « Nous aimerions connaître votre avis sur votre récent achat ! » ou « Partagez votre expérience et aidez d'autres acheteurs ! »
    *   **Scénario / exemple de marchand :** Vous voulez rendre l'objet de l'e-mail engageant et clair, encourageant les clients à l'ouvrir.
-   **Sélectionner les statuts de commande**

    *   **Ce que fait ce paramètre :** Détermine quels statuts de commande déclenchent le processus de rappel de commentaire. Les rappels ne seront envoyés que pour les produits des commandes qui ont atteint l'un des statuts sélectionnés.
    *   **Effet de la modification de ce paramètre :**
        *   *Sélection de statuts (par exemple, « Livré ») :* Les rappels ne seront envoyés que pour les commandes marquées comme livrées.
        *   *Ne pas sélectionner un statut pertinent :* Les rappels pourraient ne pas être envoyés au moment opportun (par exemple, si vous ne sélectionnez que « Paiement accepté » mais que les produits n'ont pas encore été expédiés).
    *   **Valeur recommandée :** « Livré » (Ceci garantit que les clients ont reçu leurs produits avant qu'on leur demande de les évaluer).
    *   **Scénario / exemple de marchand :** Vous ne voulez demander des avis qu'une fois que le client a effectivement reçu sa commande, vous sélectionnez donc « Livré » et « Expédié ».
-   **Groupe de clients (pour les rappels)**

    *   **Ce que fait ce paramètre :** Vous permet de cibler des groupes de clients spécifiques pour les rappels de commentaires. Seuls les clients appartenant aux groupes sélectionnés recevront des rappels.
    *   **Effet de la modification de ce paramètre :**
        *   *Sélection de groupes (par exemple, « Clients ») :* Seuls les clients du groupe « Clients » recevront des rappels.
        *   *Ne pas sélectionner de groupe :* Les rappels seront envoyés à tous les clients (sauf si d'autres filtres s'appliquent).
    *   **Valeur recommandée :** « Clients » (Généralement, vous voulez rappeler à tous vos clients réguliers).
    *   **Scénario / exemple de marchand :** Vous avez un groupe de clients « VIP » spécial et souhaitez leur envoyer des rappels personnalisés, ou vous voulez exclure les clients grossistes des rappels.
-   **Envoyer des rappels de commentaires pour les produits des commandes :**

    *   **Ce que fait ce paramètre :** Il s'agit d'un filtre de date. Les rappels ne seront envoyés que pour les produits achetés dans des commandes passées *après* cette date spécifiée.
    *   **Effet de la modification de ce paramètre :**
        *   *Définir une date :* Empêche l'envoi de rappels pour des commandes très anciennes, en se concentrant sur les achats récents.
        *   *Laisser vide :* Les rappels pourraient potentiellement être envoyés pour toutes les commandes passées, ce qui pourrait ne pas être souhaitable.
    *   **Valeur recommandée :** Définir une date récente, ou la date d'installation du module, pour éviter de spammer les anciens clients.
    *   **Scénario / exemple de marchand :** Vous venez d'installer le module et ne voulez pas envoyer de rappels pour des commandes d'il y a un an ; vous ne vous souciez que des commandes des 3 derniers mois.
-   **Taille de l'image pour les photos de produits**

    *   **Ce que fait ce paramètre :** Détermine la taille des images de produits incluses dans les e-mails de rappel.
    *   **Effet de la modification de ce paramètre :**
        *   *Sélection d'une taille (par exemple, « home\_default ») :* Les images de produits dans l'e-mail seront rendues à cette taille spécifique, affectant la mise en page de l'e-mail et le temps de chargement.
    *   **Valeur recommandée :** « home\_default » ou « small\_default » (Une image de taille moyenne qui a l'air bien sans rendre l'e-mail trop lourd).
    *   **Scénario / exemple de marchand :** Vous voulez que les images de produits dans vos e-mails de rappel soient claires mais pas excessivement grandes, vous choisissez donc une taille d'image appropriée définie dans votre thème.

#### **Paramètres de génération de bons d'achat**

-   **Envoyer un code de bon d'achat pour un commentaire**

    *   **Ce que fait ce paramètre :** C'est l'interrupteur principal de la fonction de génération de bons d'achat. Si désactivé, aucun bon d'achat ne sera généré ou envoyé, même si des commentaires sont laissés.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'activé :* Le module générera et enverra un code de bon d'achat unique aux clients qui laissent un commentaire produit.
        *   *Lorsqu'désactivé :* Aucun bon d'achat ne sera envoyé.
    *   **Valeur recommandée :** OUI (C'est une fonctionnalité essentielle pour inciter aux commentaires).
    *   **Scénario / exemple de marchand :** Vous voulez récompenser les clients pour leur effort à laisser un avis, les encourageant à acheter à nouveau.
-   **Envoyer un bon d'achat uniquement aux clients ayant acheté le produit**

    *   **Ce que fait ce paramètre :** Si activé, un bon d'achat ne sera envoyé *que* si le client qui a laissé le commentaire a également acheté le produit. Cela empêche les personnes qui n'ont pas acheté dans votre boutique d'obtenir des bons d'achat simplement en laissant des commentaires.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'activé :* Les bons d'achat sont limités aux acheteurs vérifiés.
        *   *Lorsqu'désactivé :* Toute personne qui laisse un commentaire (par exemple, un invité, ou quelqu'un qui n'a pas acheté le produit) pourrait recevoir un bon d'achat.
    *   **Valeur recommandée :** OUI (Fortement recommandé pour s'assurer que les bons d'achat sont donnés à de vrais clients et prévenir les abus).
    *   **Scénario / exemple de marchand :** Vous voulez récompenser les clients fidèles qui ont déjà effectué un achat, pas seulement n'importe qui qui laisse un commentaire.
-   **Quand générer le bon d'achat ?**

    *   **Ce que fait ce paramètre :** Détermine quand le bon d'achat est généré et envoyé au client.
    *   **Effet de la modification de ce paramètre :**
        *   *Option 1 (par exemple, « Après l'ajout du commentaire ») :* Le bon d'achat est envoyé immédiatement après que le client a soumis son commentaire.
        *   *Option 2 (par exemple, « Après l'approbation du commentaire ») :* Le bon d'achat est envoyé uniquement après qu'un administrateur a manuellement approuvé le commentaire dans le Back Office.
    *   **Valeur recommandée :** « Après l'approbation du commentaire » (Empêche de donner des bons d'achat pour des spams ou des commentaires inappropriés).
    *   **Scénario / exemple de marchand :** Vous modérez tous les commentaires produits pour maintenir la qualité. Vous voulez vous assurer que seuls les commentaires approuvés et précieux reçoivent un bon d'achat.
-   **Générer des bons d'achat pour les commentaires :**

    *   **Ce que fait ce paramètre :** Cette section vous permet de définir les propriétés du bon d'achat qui sera généré. Cela inclut le type de réduction (pourcentage, montant), la valeur, l'achat minimum, la validité, et plus encore.
    *   **Effet de la modification de ce paramètre :**
        *   *Chaque champ ici (par exemple, « Type de réduction », « Valeur », « Montant minimum ») :* Configure directement les règles et les avantages du bon de réduction généré.
        *   *Laisser les champs vides ou mal configurés :* Pourrait entraîner des bons d'achat invalides ou des bons d'achat qui ne répondent pas à vos objectifs marketing.
    *   **Valeur recommandée :**
        *   **Type de réduction :** Pourcentage (par exemple, 10 %) ou Montant (par exemple, 5 €).
        *   **Valeur :** Une incitation raisonnable (par exemple, 5, 10, 15).
        *   **Montant minimum :** Définir un achat minimum pour assurer la rentabilité (par exemple, 50 €).
        *   **Validité :** 30 jours (Encourage une utilisation rapide).
        *   **Description :** « Merci pour votre avis produit ! »
    *   **Scénario / exemple de marchand :** Vous voulez offrir une réduction de 10 % sur leur prochaine commande, valable 30 jours, avec un achat minimum de 50 €, en guise de remerciement pour leur avis.
-   **Groupe de clients (pour les bons d'achat)**

    *   **Ce que fait ce paramètre :** Similaire au paramètre de rappel, cela vous permet de restreindre la génération de bons d'achat à des groupes de clients spécifiques.
    *   **Effet de la modification de ce paramètre :**
        *   *Sélection de groupes :* Seuls les clients des groupes sélectionnés recevront des bons d'achat.
        *   *Ne pas sélectionner de groupe :* Les bons d'achat seront envoyés à tous les clients (sauf si d'autres filtres s'appliquent).
    *   **Valeur recommandée :** « Clients »
    *   **Scénario / exemple de marchand :** Vous ne voulez donner des bons d'achat qu'à votre groupe de « Clients » standard, pas aux « Invités » ou aux « Grossistes ».
-   **Limiter le nombre d'e-mails**

    *   **Ce que fait ce paramètre :** C'est une fonction de sécurité pour empêcher votre serveur d'envoyer trop d'e-mails en peu de temps, ce qui pourrait entraîner le marquage de vos e-mails comme spam ou l'imposition de limites par votre hébergeur.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'activé :* Le module respectera le paramètre « Limite d'e-mails ».
        *   *Lorsqu'désactivé :* Aucune limite d'envoi d'e-mails ne sera appliquée par le module lui-même.
    *   **Valeur recommandée :** OUI
    *   **Scénario / exemple de marchand :** Vous avez un grand nombre de rappels en attente et souhaitez les envoyer progressivement pour éviter de surcharger votre serveur de messagerie.
-   **Limite d'e-mails :**

    *   **Ce que fait ce paramètre :** Spécifie le nombre maximum d'e-mails (rappels ou bons d'achat) que le module peut envoyer en un seul cycle d'exécution (par exemple, lorsque la tâche cron s'exécute).
    *   **Effet de la modification de ce paramètre :**
        *   *Définir un nombre (par exemple, 50) :* Le module enverra un maximum de 50 e-mails par exécution de tâche cron. S'il y en a plus, ils seront envoyés lors des exécutions suivantes.
    *   **Valeur recommandée :** 50-100 (Ajuster en fonction des limites d'envoi d'e-mails de votre hébergeur et de la capacité du serveur).
    *   **Scénario / exemple de marchand :** Votre hébergeur autorise 100 e-mails par heure. Vous définissez cette limite à 50 pour rester largement dans leurs directives.

#### **Filtres de produits (pour les rappels et les bons d'achat)**

-   **Activer les filtres**

    *   **Ce que fait ce paramètre :** Active des options de filtrage supplémentaires pour les rappels et les bons d'achat, vous permettant de spécifier quels produits ou fabricants sont éligibles.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'activé :* Le filtre « Fabricants » devient actif.
        *   *Lorsqu'désactivé :* Aucun filtre spécifique au produit ne sera appliqué.
    *   **Valeur recommandée :** NON (Sauf si vous avez un besoin spécifique de filtrer).
    *   **Scénario / exemple de marchand :** Vous ne voulez envoyer des rappels ou des bons d'achat que pour les produits de certains fabricants.
-   **Fabricants**

    *   **Ce que fait ce paramètre :** Si « Activer les filtres » est actif, cela vous permet de sélectionner des fabricants spécifiques. Les rappels et les bons d'achat ne seront envoyés que pour les produits des fabricants sélectionnés.
    *   **Effet de la modification de ce paramètre :**
        *   *Sélection de fabricants :* Réduit la portée de l'opération du module aux seuls produits de ces marques.
    *   **Valeur recommandée :** Laisser tout non sélectionné (sauf si vous avez un besoin spécifique).
    *   **Scénario / exemple de marchand :** Vous menez une promotion avec une marque spécifique et ne voulez inciter aux commentaires que pour leurs produits.

#### **Tableau de référence rapide de la configuration**

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Demander la permission d'envoyer des rappels | OUI | Assure la conformité au RGPD ; les clients acceptent les rappels. |
| Configuration du module | Envoyer un rappel de commentaire | OUI | Interrupteur principal pour l'envoi d'e-mails de rappel. |
| Configuration du module | Rappeler les commentaires après : | 7 jours | Délai (en jours) après le changement de statut de commande pour le premier rappel. |
| Configuration du module | Répéter le rappel | 14 jours | Délai (en jours) après le premier rappel pour un second (0 pour aucun). |
| Configuration du module | Titre de l'e-mail (Rappel) | Personnalisable | Objet des e-mails de rappel. |
| Configuration du module | Sélectionner les statuts de commande | Livré | Statuts de commande qui déclenchent le processus de rappel. |
| Configuration du module | Groupe de clients (Rappel) | Clients | Restreint les rappels aux groupes de clients sélectionnés. |
| Configuration du module | Envoyer des rappels de commentaires pour les produits des commandes : | Date récente / Vide | Filtre de date pour les commandes éligibles. |
| Configuration du module | Taille de l'image pour les photos de produits | home\_default | Taille des images de produits dans les e-mails de rappel. |
| Configuration du module | Envoyer un code de bon d'achat pour un commentaire | OUI | Interrupteur principal pour la génération et l'envoi de bons d'achat. |
| Configuration du module | Envoyer un bon d'achat uniquement aux clients ayant acheté le produit | OUI | Restreint les bons d'achat aux acheteurs réels. |
| Configuration du module | Quand générer le bon d'achat ? | Après l'approbation du commentaire | Moment de la génération du bon d'achat (après soumission ou approbation). |
| Configuration du module | Générer des bons d'achat pour les commentaires : (Propriétés du bon d'achat) | Personnalisable | Définit le type de réduction, la valeur, la validité, etc., du bon d'achat. |
| Configuration du module | Groupe de clients (Bon d'achat) | Clients | Restreint les bons d'achat aux groupes de clients sélectionnés. |
| Configuration du module | Limiter le nombre d'e-mails | OUI | Active la limitation du taux d'envoi d'e-mails. |
| Configuration du module | Limite d'e-mails : | 50-100 | Nombre max d'e-mails envoyés par exécution de tâche cron. |
| Configuration du module | Activer les filtres | NON | Active le filtrage par produit/fabricant. |
| Configuration du module | Fabricants | Tous non sélectionnés | Filtre les produits éligibles par fabricant. |

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module ajoute plusieurs écrans dédiés à votre Back Office PrestaShop pour gérer les rappels, les bons d'achat et les clients désabonnés. Vous pouvez les trouver sous l'élément de menu **« Bon d'achat pour commentaire »**, généralement situé sous **« Catalogue »** ou **« Marketing »**.

#### **4.2.1 AdminComRemCommentsController : Gestion des rappels de commentaires**

-   **Nom de l'écran et emplacement du menu :** **Bon d'achat pour commentaire > Rappels de commentaires**
-   **Actions et paramètres disponibles :** Cet écran affiche une liste de tous les rappels de commentaires en attente, envoyés ou échoués. Vous verrez des détails tels que le nom du client, son e-mail, le produit sur lequel il doit commenter, l'ID de la commande, la date d'envoi (ou de planification) du rappel et son statut actuel.
    *   **Vue grille / Gestion :** Vous pouvez afficher, filtrer et rechercher dans la liste des rappels. Cela vous permet de surveiller l'activité du module.
    *   **Actions groupées :** Selon la version du module, vous pourriez être en mesure d'envoyer manuellement des rappels ou de supprimer des entrées.
-   **Effet des modifications :** Cet écran est principalement destiné à la surveillance. La suppression d'une entrée ici empêcherait l'envoi d'un rappel programmé. L'envoi manuel d'un rappel déclencherait un e-mail au client.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vérifiez périodiquement cet écran pour vous assurer que les rappels sont envoyés comme prévu. Si vous remarquez qu'un client n'a pas reçu de rappel, vous pouvez enquêter ou le déclencher manuellement.

#### **4.2.2 AdminComUnsubController : Clients désabonnés**

-   **Nom de l'écran et emplacement du menu :** **Bon d'achat pour commentaire > Clients désabonnés**
-   **Actions et paramètres disponibles :** Cet écran liste les clients qui se sont désabonnés des rappels de commentaires (si le paramètre « Demander la permission » est activé). Vous verrez leur ID client et leur adresse e-mail.
    *   **Vue grille / Gestion :** Vous permet d'afficher et de gérer la liste des clients désabonnés.
-   **Effet des modifications :** La suppression d'un client de cette liste le rendrait à nouveau éligible pour recevoir des rappels (en supposant qu'il remplisse d'autres critères et ne se soit pas explicitement désabonné ailleurs).
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Il s'agit d'un écran lié à la conformité. Vous n'aurez généralement pas besoin d'interagir avec lui quotidiennement, mais il est important de savoir où trouver et gérer les préférences de désinscription des clients.

#### **4.2.3 AdminComVouCommentsController : Bons d'achat pour commentaires**

-   **Nom de l'écran et emplacement du menu :** **Bon d'achat pour commentaire > Bons d'achat pour commentaires**
-   **Actions et paramètres disponibles :** Cet écran fournit une liste complète de tous les bons d'achat générés par le module en réponse aux commentaires produits. Vous verrez des détails tels que le client qui a reçu le bon d'achat, le produit sur lequel il a commenté, le code du bon d'achat généré, sa valeur, sa validité et s'il a été utilisé.
    *   **Vue grille / Gestion :** Vous pouvez filtrer, rechercher et trier les bons d'achat. C'est utile pour suivre l'efficacité de votre programme d'incitation.
    *   **Clés de configuration associées :** Les options d'affichage et de filtrage ici pourraient être influencées par `cvo_filters` et `cvo_fil_manuf` de la configuration principale.
-   **Effet des modifications :** Cet écran est principalement destiné à la surveillance. Vous pouvez voir quels bons d'achat ont été émis et s'ils ont été utilisés.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Examinez cet écran pour suivre le nombre de bons d'achat émis et leurs taux d'utilisation. Ces données peuvent vous aider à évaluer le succès de votre programme d'incitation aux avis.

#### **4.2.4 index.php (Espace réservé du contrôleur d'administration)**

-   **Nom de l'écran et emplacement du menu :** Ce fichier `index.php` sert généralement de placeholder ou de redirection dans le répertoire `controllers/admin` du module, garantissant que l'accès direct au répertoire n'expose pas d'informations sensibles. Il ne représente pas un écran visible par l'utilisateur dans le Back Office de PrestaShop.

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes clients ne reçoivent pas les e-mails de rappel. Que dois-je vérifier ?**
R1 :

-   **Module activé :** Assurez-vous que « Envoyer un rappel de commentaire » est réglé sur OUI dans la configuration du module.
-   **Statuts de commande :** Vérifiez que les commandes en question ont atteint l'un des « Statuts de commande sélectionnés » que vous avez choisis (par exemple, « Livré »).
-   **Délai de rappel :** Vérifiez « Rappeler les commentaires après : » pour vous assurer que suffisamment de jours se sont écoulés depuis le changement de statut de la commande.
-   **Tâche Cron :** Le module s'appuie sur la tâche cron de PrestaShop pour envoyer des e-mails. Assurez-vous que votre tâche cron est configurée correctement et s'exécute régulièrement sur votre serveur. Vous pouvez généralement trouver les instructions de la tâche cron dans votre panneau d'hébergement ou dans la section « Paramètres avancés > Informations » de PrestaShop.
-   **Configuration des e-mails :** Vérifiez vos paramètres d'e-mail PrestaShop (Paramètres avancés > E-mail) pour vous assurer que les e-mails sont envoyés correctement depuis votre boutique en général.
-   **Consentement du client :** Si « Demander la permission d'envoyer des rappels » est activé, assurez-vous que les clients ont effectivement donné leur consentement.
-   **Limites d'e-mails :** Vérifiez les paramètres « Limiter le nombre d'e-mails » et « Limite d'e-mails ». Si la limite est atteinte, les e-mails seront envoyés lors de la prochaine exécution de la tâche cron.
-   **Dossiers de spam :** Demandez aux clients de vérifier leurs dossiers de spam ou de courrier indésirable.

**Q2 : Les bons d'achat ne sont pas envoyés après que les commentaires ont été laissés.**
R2 :

-   **Module activé :** Assurez-vous que « Envoyer un code de bon d'achat pour un commentaire » est réglé sur OUI.
-   **Moment de la génération du bon d'achat :** Vérifiez « Quand générer le bon d'achat ? ». S'il est réglé sur « Après l'approbation du commentaire », assurez-vous que les commentaires ont effectivement été approuvés dans votre Back Office PrestaShop (Catalogue > Commentaires produits, si vous utilisez le module par défaut, ou votre module d'avis tiers).
-   **Acheteur uniquement :** Si « Envoyer un bon d'achat uniquement aux clients ayant acheté le produit » est activé, vérifiez que le client qui a laissé le commentaire a bien acheté ce produit spécifique.
-   **Configuration du bon d'achat :** Vérifiez à nouveau tous les paramètres sous « Générer des bons d'achat pour les commentaires » pour vous assurer qu'un bon d'achat valide peut être créé (par exemple, valeur de la réduction, validité).
-   **Configuration des e-mails et tâche Cron :** Similaire aux problèmes de rappel, assurez-vous que vos paramètres d'e-mail et votre tâche cron fonctionnent.

**Q3 : Le module envoie trop d'e-mails, ou les e-mails sont retardés.**
R3 :

-   **Limite d'e-mails :** Accédez à la configuration du module et assurez-vous que « Limiter le nombre d'e-mails » est activé et que « Limite d'e-mails » est réglé sur un nombre raisonnable (par exemple, 50-100). Cela évite de surcharger votre serveur.
-   **Fréquence de la tâche Cron :** Si votre tâche cron s'exécute très fréquemment (par exemple, toutes les minutes) et que vous avez une limite d'e-mails élevée, elle pourrait envoyer de nombreux e-mails rapidement. Ajustez la fréquence de la tâche cron ou la limite d'e-mails.
-   **Limites d'hébergement :** Contactez votre hébergeur pour comprendre leurs limites d'envoi d'e-mails par heure/jour. Ajustez la « Limite d'e-mails » du module en conséquence.

**Q4 : Comment traduire les textes ou les modèles d'e-mail du module ?**
R4 :

-   **Traduction du Back Office :** Allez dans **International > Traductions**.
-   **Type de traduction :** Sélectionnez « Traductions des modules installés ».
-   **Sélectionnez votre thème :** Choisissez votre thème actuel.
-   **Sélectionnez votre langue :** Choisissez la langue que vous souhaitez traduire.
-   **Module :** Trouvez « Bon d'achat pour commentaire produit » dans la liste.
-   Vous pouvez ensuite modifier les chaînes de texte pour la configuration du module, les éléments du front-office (comme la case à cocher d'opt-in) et les modèles d'e-mail. N'oubliez pas d'enregistrer vos modifications.

**Q5 : La case à cocher du front-office du module (pour les permissions) ne s'affiche pas correctement sur mon thème.**
R5 :

-   **Compatibilité du thème :** Les thèmes personnalisés nécessitent parfois des ajustements CSS mineurs pour les nouveaux éléments de module.
-   **Vider le cache :** Tout d'abord, essayez de vider le cache de votre PrestaShop (Paramètres avancés > Performances > Vider le cache).
-   **Contacter le support :** Si le problème persiste, cela pourrait nécessiter une petite modification CSS. Contactez le support MyPresta.eu avec des captures d'écran et le nom de votre thème.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé du module « Bon d'achat pour commentaire produit » pour les développeurs et les webmasters.

### 4.1 Vue d'ensemble de l'architecture

Le module suit une architecture de module PrestaShop standard, tirant parti des modèles MVC lorsque cela est approprié. Il s'intègre au cœur de PrestaShop via des hooks pour l'affichage en front-office et les actions en back-office. Il utilise des `AdminController` personnalisés pour gérer ses entités de données (rappels, bons d'achat, désabonnements) et un `FrontController` pour l'exécution des tâches cron. La configuration est gérée via `Configuration::get()` et `Configuration::updateValue()`. Le module ne semble pas utiliser de classes `ObjectModel` personnalisées, gérant plutôt ses données directement ou via des entités PrestaShop existantes (comme `CartRule` pour les bons d'achat).

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   `comvou/controllers/front/CronJob.php`
    *   **Nom de la classe et classe parente :** `ComvouCronJobModuleFrontController` étendant `ModuleFrontController`.
    *   **Responsabilité :** Ce contrôleur est conçu pour être exécuté via une tâche cron. Il gère les tâches d'arrière-plan du module, telles que la vérification des commandes éligibles, l'envoi de rappels de commentaires et la génération/l'envoi de bons d'achat basés sur de nouveaux commentaires. Il ne rend généralement pas de page visuelle mais exécute des actions et se termine. C'est le cœur de l'automatisation du module.

#### Contrôleurs d'administration Back-Office

-   `comvou/controllers/admin/AdminComRemComments.php`

    *   **Nom de l'onglet et entité gérée :** « Rappels de commentaires » (sous le menu « Bon d'achat pour commentaire »). Gère les entités `cvor` (Comment Voucher Order Reminder), qui représentent les rappels planifiés ou envoyés.
    *   **Responsabilité :** Fournit une liste (vue grille) de tous les rappels de commentaires. Il permet aux administrateurs de visualiser le statut des rappels, de les filtrer et potentiellement d'effectuer des actions comme l'envoi manuel d'un rappel ou la suppression d'une entrée. Il étend `AdminController` et utilise `HelperList` pour l'affichage.
-   `comvou/controllers/admin/AdminComUnsub.php`

    *   **Nom de l'onglet et entité gérée :** « Clients désabonnés » (sous le menu « Bon d'achat pour commentaire »). Gère les entités `cunsub` (Comment Unsubscribe).
    *   **Responsabilité :** Affiche une liste des clients qui se sont désabonnés des rappels de commentaires. Ce contrôleur fournit une interface pour visualiser et gérer ces préférences de désinscription, généralement en utilisant `HelperList`.
-   `comvou/controllers/admin/AdminComVouComments.php`

    *   **Nom de l'onglet et entité gérée :** « Bons d'achat pour commentaires » (sous le menu « Bon d'achat pour commentaire »). Gère les entités `cvov` (Comment Voucher Order Voucher), représentant les bons d'achat générés.
    *   **Responsabilité :** Présente une liste de tous les bons d'achat générés par le module, détaillant quel client l'a reçu, pour quel produit, le code du bon d'achat, sa valeur et son statut d'utilisation. Il utilise `HelperList` pour l'affichage et permet le filtrage. L'affichage peut incorporer une logique basée sur les clés de configuration `cvo_filters` et `cvo_fil_manuf`.
-   `comvou/controllers/admin/index.php`

    *   **Nom de l'onglet et entité gérée :** Pas un écran directement visible par l'utilisateur.
    *   **Responsabilité :** Il s'agit d'une mesure de sécurité standard dans PrestaShop. Il contient généralement `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../../../"); exit;` pour empêcher l'affichage du répertoire et rediriger vers la racine de la boutique.

### 4.3 Classes et modèles principaux (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que le module pourrait gérer ses données directement dans le fichier principal `comvou.php` ou ses contrôleurs, potentiellement en utilisant les `ObjectModel`s PrestaShop existants (comme `Order`, `Customer`, `Product`, `CartRule`) et des requêtes directes à la base de données pour son stockage de données personnalisé (par exemple, pour les rappels et les enregistrements de bons d'achat).

### 4.4 Actifs JavaScript (`views/js/`)

-   `comvou/lib/voucherengine/script.js`
    *   **Portée :** Probablement Back-office.
    *   **Détails :** Ce script est probablement associé aux paramètres de génération de bons d'achat dans la configuration du module ou au contrôleur `AdminComVouComments`. Il pourrait gérer des éléments de formulaire dynamiques, la validation ou les interactions AJAX liées aux paramètres de création de bons d'achat (par exemple, afficher/masquer des champs en fonction du type de réduction, calculer des valeurs). Il pourrait également être utilisé pour des améliorations générales de l'interface utilisateur dans les pages d'administration du module.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `comvou/lib/voucherengine/ps16.css`
    *   **Portée :** Style du formulaire d'administration Back-office.
    *   **Détails :** Cette feuille de style fournit un style spécifique pour la page de configuration du module et potentiellement ses vues de contrôleur d'administration personnalisées, garantissant qu'elles sont cohérentes avec la conception du back-office de PrestaShop 1.6. Elle pourrait contenir des règles pour les mises en page de formulaire, les champs de saisie, les boutons et les affichages de grille. Les développeurs qui la remplaceraient cibleraient des ID ou des classes spécifiques utilisés par les modèles d'administration du module.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)

-   `comvou/views/templates/hook/form.tpl`

    *   **Hook :** Potentiellement `displayAdditionalCustomerFormFields` ou `displayCustomerAccountForm`.
    *   **Sortie :** Ce modèle rend probablement la case à cocher « Demander la permission d'envoyer des rappels » sur les formulaires d'inscription client ou de mise à jour d'identité en front-office. Il contiendrait le HTML de la case à cocher et de son étiquette associée.
-   `comvou/views/templates/hook/header.tpl`

    *   **Hook :** `displayHeader`
    *   **Sortie :** Ce modèle est généralement utilisé pour inclure des fichiers CSS ou JavaScript qui doivent être chargés dans la section `<head>` des pages du front-office. Il pourrait charger conditionnellement des actifs en fonction des paramètres du module ou de la page actuelle.
-   `comvou/views/templates/hook/identity.tpl`

    *   **Hook :** Potentiellement `displayCustomerAccountForm` ou des hooks similaires sur la page d'identité du client.
    *   **Sortie :** Similaire à `form.tpl`, ce modèle rend probablement la case à cocher d'opt-in spécifiquement sur la page « Mon Compte > Informations » du client, permettant aux clients existants de gérer leurs préférences de rappel.

#### Modèles d'administration (`views/templates/admin/`)

-   `comvou/views/templates/admin/com_rem_comments/helpers/form/form.tpl`

    *   **Objectif :** Ce modèle est utilisé par `AdminComRemCommentsController` pour rendre le formulaire (le cas échéant) pour ajouter/modifier un rappel de commentaire, ou plus probablement, pour personnaliser l'affichage de l'aide de liste.
-   `comvou/views/templates/admin/com_vou_comments/helpers/form/form.tpl`

    *   **Objectif :** Ce modèle est utilisé par `AdminComVouCommentsController` pour rendre le formulaire (le cas échéant) pour ajouter/modifier une entrée de bon d'achat, ou pour personnaliser l'affichage de l'aide de liste pour les bons d'achat générés.
-   `comvou/views/templates/admin/orderstates.tpl`

    *   **Objectif :** Ce modèle est probablement utilisé dans la configuration principale du module (`getContent()`) pour rendre la liste de sélection multiple des statuts de commande, permettant au marchand de choisir quels statuts déclenchent les rappels.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

La description du module et l'analyse du code suggèrent que le module stocke ses données personnalisées (rappels, bons d'achat, désabonnements) dans des tables de base de données dédiées. Bien que des fichiers SQL spécifiques ne soient pas listés, les `AdminComRemCommentsController`, `AdminComUnsubController` et `AdminComVouCommentsController` impliquent l'existence de tables telles que :

-   `ps_cvor` : Stocke les enregistrements liés aux rappels de commentaires (par exemple, ID client, ID produit, ID commande, statut du rappel, date du dernier envoi).
-   `ps_cunsub` : Stocke les enregistrements des clients qui se sont désabonnés des rappels (par exemple, ID client, e-mail).
-   `ps_cvov` : Stocke les enregistrements des bons d'achat générés (par exemple, ID client, ID produit, `id_cart_rule` généré, code du bon d'achat, statut).
-   Les valeurs de configuration sont stockées dans `ps_configuration` avec des clés comme `cvo_r_d`, `cvo_r`, `cvo_repeat`, `cvo_orderstates`, `CR_ALLOWED`, `cvo_v`, `cvo_v_fn`, `cvo_v_t`, `cvo_filters`, `cvo_fil_manuf`, `CVOR_TITLE`, `CVOV_TITLE`, `cvo_customergroups_reminder`, `cvo_customergroups_voucher`, `cvo_r_fn`, `cvo_r_date`, `cvo_vonlycust`, `cvo_v_date`, `cvo_img_type`, `CVO_LIM_M_V`, `CVO_LIM_M`.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Lors de l'initialisation d'un `AdminController` et de la définition de ses médias (JS/CSS). | Pour injecter des JS/CSS spécifiques au module dans le Back Office. |
| `actionOrderStatusUpdate` | Après la mise à jour du statut d'une commande. | Pour détecter quand une commande atteint un statut « livré » ou pertinent, déclenchant le processus de rappel. |
| `actionCustomerAccountAdd` | Après la création d'un nouveau compte client. | Pour vérifier les préférences d'opt-in initiales pour les nouveaux clients. |
| `displayHeader` | Dans la section `<head>` des pages du front-office. | Pour inclure des CSS/JS ou des balises meta du front-office. |
| `displayCustomerAccountForm` | Sur la page « Mon Compte > Informations » du client. | Pour afficher la case à cocher d'opt-in pour les clients existants. |
| `displayAdditionalCustomerFormFields` | Sur le formulaire d'inscription client. | Pour afficher la case à cocher d'opt-in pour les nouvelles inscriptions client. |
| `validateCustomerFormFields` | Lors de la soumission d'un formulaire client (inscription/identité). | Pour traiter la sélection de la case à cocher d'opt-in et enregistrer la préférence du client. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support technique professionnel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Assurez-vous d'utiliser la dernière version compatible du module pour votre boutique PrestaShop afin de bénéficier de toutes les améliorations et correctifs de sécurité.
