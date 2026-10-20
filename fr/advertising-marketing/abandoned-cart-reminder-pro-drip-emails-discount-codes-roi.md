---
title: "Abandoned Cart Reminder Pro – drip emails, discount codes & ROI - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Abandoned Cart Reminder Pro – drip emails, discount codes & ROI par MyPresta.eu."
sidebar:
  label: "Abandoned Cart Reminder Pro – drip emails, discount codes & ROI - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Abandoned Cart Reminder Pro – drip emails, discount codes & ROI sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/abandoned-cart-reminder-pro-drip-emails-discount-codes-roi.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/abandoned-cart-reminder-pro-drip-emails-discount-codes-roi/)
>
> ---


# Abandoned Cart Reminder Pro – drip emails, discount codes & ROI

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5 (Le module est écrit en tenant compte de PHP 5.6+, mais PrestaShop 9.x nécessite PHP 8.1+ pour la boutique elle-même. Nous recommandons d'utiliser la version PHP stable la plus élevée compatible avec votre installation PrestaShop, jusqu'à 8.5.)
- **Exigences d'hébergement** : Les extensions PHP standard comme cURL, JSON et OpenSSL sont requises. Votre environnement d'hébergement doit également prendre en charge les tâches cron (tâches planifiées) pour que le module fonctionne correctement, car il traite les rappels en arrière-plan.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

Le module « Abandoned Cart Reminder Pro » offre un ensemble complet d'outils pour gérer vos campagnes. Vous interagirez principalement avec ses éléments de menu dédiés dans le Back Office de PrestaShop.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Bien que le module dispose d'écrans d'administration dédiés, le bouton initial « Configurer » du Gestionnaire de modules peut mener à une configuration de base ou à une redirection. Le module utilise la clé de configuration `PS_SSL_ENABLED` de PrestaShop.

-   **Ce que fait ce paramètre :** Ce paramètre n'est pas directement contrôlé par le module, mais est un paramètre PrestaShop essentiel qui indique si votre boutique utilise HTTPS (connexion sécurisée). Le module s'appuie sur cela pour générer des liens corrects et sécurisés dans vos e-mails de rappel.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsque `PS_SSL_ENABLED` est OUI :* Tous les liens générés par le module (par exemple, vers les paniers abandonnés, les pages de désinscription) utiliseront `https://`, garantissant une expérience sécurisée et fiable pour vos clients.
    *   *Lorsque `PS_SSL_ENABLED` est NON :* Les liens pourraient être générés en utilisant `http://`, ce qui est moins sécurisé et peut déclencher des avertissements de navigateur, réduisant potentiellement la confiance des clients et les taux de conversion.
-   **Valeur recommandée :** **OUI**. Votre boutique doit toujours utiliser SSL pour des raisons de sécurité et de référencement. Assurez-vous que l'ensemble de votre boutique fonctionne en HTTPS.
-   **Scénario/exemple pour le marchand :** Si vos clients reçoivent un e-mail avec un lien `http://` vers leur panier, leur navigateur pourrait afficher un avertissement « Non sécurisé ». Cela peut les rendre hésitants à cliquer sur le lien ou à finaliser l'achat, même si votre paiement est sécurisé. Utilisez toujours HTTPS.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Une fois le module installé, vous trouverez un nouvel élément de menu dans votre Back Office PrestaShop, généralement sous **Marketing** ou une section dédiée à « Abandoned Cart Reminder Pro ». Ce menu mènera à plusieurs sous-sections :

#### 2.2.1 Campagnes (Back Office > Abandoned Cart Reminder Pro > Campagnes)

C'est ici que vous créez, gérez et optimisez vos campagnes de rappel de panier abandonné.

-   **Nom de l'écran et emplacement du menu :** **Abandoned Cart Reminder Pro > Campagnes**
-   **Actions et paramètres disponibles :**
    *   **Liste des campagnes :** Un tableau affichant toutes vos campagnes actives et inactives, y compris leur nom, leur statut et leurs statistiques clés.
    *   **Ajouter une nouvelle campagne :** Cliquez pour créer une nouvelle séquence d'e-mails en plusieurs étapes.
        *   **Nom de la campagne :** Un nom descriptif pour votre référence interne (par exemple, « Rappel standard en 2 étapes », « Remise panier de grande valeur »).
        *   **Règles de ciblage :**
            *   **Valeur minimale du panier :** Définissez une valeur totale minimale pour qu'un panier soit éligible à cette campagne.
                *   *Effet :* Les paniers dont la valeur est inférieure à ce seuil ne recevront pas d'e-mails de cette campagne.
                *   *Scénario marchand :* Créez une campagne spécifiquement pour les paniers de grande valeur, en offrant peut-être une remise plus importante.
            *   **Groupes de clients :** Ciblez des groupes de clients spécifiques (par exemple, « Visiteurs », « Clients », « Grossistes »).
                *   *Effet :* Seuls les clients appartenant aux groupes sélectionnés recevront des e-mails.
                *   *Scénario marchand :* Envoyez des rappels différents aux nouveaux visiteurs par rapport aux clients fidèles, ou excluez les clients B2B s'ils ont un processus d'achat différent.
            *   **Produits dans le panier :** Ciblez les paniers contenant des produits spécifiques ou des produits de certaines catégories.
                *   *Effet :* Seuls les paniers contenant les produits spécifiés déclencheront la campagne.
                *   *Scénario marchand :* Créez une campagne pour les clients qui ont abandonné un panier avec un produit spécifique à forte marge.
        *   **Étapes de la campagne (E-mails goutte à goutte) :** Définissez la séquence d'e-mails à envoyer.
            *   **Délai :** Combien de temps après l'abandon du panier cet e-mail doit-il être envoyé (par exemple, 1 heure, 24 heures, 3 jours).
                *   *Effet :* Contrôle le moment de votre suivi.
                *   *Scénario marchand :* Envoyez un rappel rapide après 1 heure, un rappel plus fort avec une remise après 24 heures, et un dernier après 3 jours.
            *   **Objet de l'e-mail :** La ligne d'objet de l'e-mail (prend en charge plusieurs langues).
            *   **Contenu de l'e-mail (Constructeur d'e-mails) :** Concevez le corps de votre e-mail à l'aide d'un éditeur de texte enrichi. Vous pouvez inclure des espaces réservés dynamiques comme le nom du client, le lien du panier, la liste des produits et les codes de réduction.
            *   **Code de réduction :** Option pour générer un code de réduction unique et à usage unique pour cet e-mail spécifique.
                *   *Effet :* Un code de bon d'achat unique est créé et inclus dans l'e-mail, encourageant la conversion.
                *   *Scénario marchand :* Offrez une remise de 10 % dans le deuxième e-mail de rappel pour inciter à la finalisation.
            *   **Test A/B :** Créez des variations de l'objet ou du contenu de votre e-mail pour tester ce qui fonctionne le mieux.
                *   *Effet :* Le module répartira les envois entre les variations et suivra les taux de conversion, vous permettant d'optimiser vos campagnes.
                *   *Scénario marchand :* Testez deux lignes d'objet différentes pour voir laquelle obtient un taux d'ouverture plus élevé.
    *   **Modifier/Dupliquer/Supprimer des campagnes :** Gérez les campagnes existantes. La duplication est utile pour créer rapidement des campagnes similaires.
-   **Effet des modifications :** Les modifications ici ont un impact direct sur les clients qui reçoivent des e-mails de rappel, le moment où ils les reçoivent, le contenu qu'ils voient et s'ils reçoivent des codes de réduction. Des campagnes bien configurées peuvent augmenter considérablement le taux de récupération de votre boutique.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Commencez par une campagne simple en 2 étapes : un rappel après 1 à 2 heures (sans remise) et un autre après 24 heures (avec une petite remise).
    2.  Surveillez votre Tableau de bord (voir 4.2.2) pour voir quelles campagnes sont les plus performantes.
    3.  Expérimentez avec les tests A/B sur les lignes d'objet ou les montants de remise pour optimiser les taux de conversion.
    4.  Envisagez de créer des campagnes ciblées pour des segments de clients spécifiques ou des produits de grande valeur.

#### 2.2.2 Tableau de bord (Back Office > Abandoned Cart Reminder Pro > Tableau de bord)

Cet écran offre un aperçu clair des performances de votre module et des statistiques clés.

-   **Nom de l'écran et emplacement du menu :** **Abandoned Cart Reminder Pro > Tableau de bord**
-   **Actions et paramètres disponibles :**
    *   **Indicateurs Clés de Performance (KPI) :** Affiche des métriques telles que :
        *   **Paniers abandonnés :** Nombre total de paniers abandonnés.
        *   **E-mails envoyés :** Nombre d'e-mails de rappel expédiés.
        *   **Paniers récupérés :** Nombre de paniers abandonnés ayant abouti à une commande finalisée après réception d'un rappel.
        *   **Taux de récupération :** Pourcentage de paniers abandonnés récupérés.
        *   **Revenus attribués :** Le chiffre d'affaires total généré par les paniers récupérés.
        *   **ROI :** Retour sur investissement de vos campagnes.
    *   **Répartition des performances des campagnes :** Une représentation visuelle (par exemple, des diagrammes, des graphiques) des performances de chaque campagne.
    *   **Activité récente :** Un aperçu rapide des paniers récemment abandonnés, des e-mails envoyés et des commandes récupérées.
-   **Effet des modifications :** Il s'agit d'un écran de rapport ; vous n'y apportez pas de modifications directes, mais les données vous aident à comprendre l'impact de vos campagnes et guident vos efforts d'optimisation dans la section « Campagnes ».
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Consultez ce tableau de bord régulièrement (par exemple, chaque semaine) pour identifier les tendances, voir quelles campagnes sont les plus efficaces et repérer tout problème. Utilisez ces données pour affiner vos stratégies de campagne.

#### 2.2.3 Journaux (Back Office > Abandoned Cart Reminder Pro > Journaux)

La section Journaux fournit un historique détaillé de toutes les actions effectuées par le module, vous aidant à dépanner et à vérifier son fonctionnement.

-   **Nom de l'écran et emplacement du menu :** **Abandoned Cart Reminder Pro > Journaux**
-   **Actions et paramètres disponibles :**
    *   **Grille des entrées de journal :** Un tableau consultable et filtrable affichant :
        *   **Horodatage :** Quand l'événement s'est produit.
        *   **Client :** Le client associé à l'événement.
        *   **ID du panier :** L'ID du panier abandonné.
        *   **Campagne/Étape :** Quelle campagne et quelle étape ont déclenché l'événement.
        *   **Type d'événement :** (par exemple, « Panier abandonné », « E-mail envoyé », « E-mail ouvert », « Lien cliqué », « Panier récupéré », « Remise appliquée »).
        *   **Statut :** Succès ou échec.
        *   **Détails :** Informations supplémentaires, telles qu'un aperçu du contenu de l'e-mail ou des messages d'erreur.
    *   **Aperçu de l'e-mail :** Option pour afficher le contenu exact d'un e-mail qui a été envoyé.
-   **Effet des modifications :** Il s'agit d'un écran de diagnostic et d'audit. Vous n'y apportez pas de modifications, mais il est crucial pour comprendre pourquoi un client n'a pas reçu un e-mail ou si une campagne ne fonctionne pas comme prévu.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Si un client signale ne pas avoir reçu un e-mail, ou si votre taux de récupération diminue de manière inattendue, consultez les journaux. Vous pouvez voir si les e-mails ont été envoyés avec succès, s'il y a eu des erreurs, ou si les clients se sont désabonnés.

#### 2.2.4 Paramètres (Back Office > Abandoned Cart Reminder Pro > Paramètres)

Cet écran contient des paramètres globaux qui affectent le comportement général du module.

-   **Nom de l'écran et emplacement du menu :** **Abandoned Cart Reminder Pro > Paramètres**
-   **Actions et paramètres disponibles :**
    *   **Paramètres généraux :**
        *   **Activer le module :** Active ou désactive l'ensemble du module.
            *   *Effet :* Lorsqu'il est désactivé, aucun panier ne sera suivi et aucun e-mail ne sera envoyé.
            *   *Recommandé :* OUI, sauf si vous le désactivez temporairement pour la maintenance.
        *   **Valeur minimale du panier pour le suivi :** Définissez une valeur minimale globale du panier pour que tout panier soit considéré comme « abandonné » et suivi par le module.
            *   *Effet :* Les paniers dont la valeur est inférieure à ce seuil seront ignorés par toutes les campagnes.
            *   *Scénario marchand :* Évitez d'envoyer des rappels pour de très petits paniers où l'effort de récupération pourrait ne pas en valoir la peine.
        *   **Temps pour considérer le panier abandonné :** Combien de temps après la dernière activité du panier un panier doit-il être considéré comme abandonné (par exemple, 30 minutes, 1 heure).
            *   *Effet :* Cela détermine quand le module commence à compter le délai pour le premier e-mail de rappel.
            *   *Recommandé :* 30-60 minutes. Trop court pourrait agacer les clients, trop long pourrait manquer la fenêtre d'opportunité.
        *   **Limites anti-spam :**
            *   **Max d'e-mails par client :** Limitez le nombre total d'e-mails de panier abandonné qu'un seul client peut recevoir sur une période (par exemple, 3 e-mails par 30 jours).
                *   *Effet :* Empêche les clients d'être submergés par trop d'e-mails, réduisant les taux de désabonnement.
                *   *Recommandé :* Définissez des limites raisonnables pour maintenir une expérience client positive.
            *   **Temps min. entre les e-mails :** Assurez un délai minimum entre deux e-mails envoyés au même client.
                *   *Effet :* Empêche l'envoi de plusieurs e-mails de différentes campagnes trop rapprochés.
        *   **Paramètres RGPD / Désinscription :**
            *   **Activer le lien de désinscription :** Incluez un lien dans les e-mails de rappel permettant aux clients de se désabonner des futurs rappels.
                *   *Effet :* Crucial pour la conformité au RGPD et le respect de la vie privée des clients.
                *   *Recommandé :* OUI.
            *   **Contenu de la page de désinscription :** Personnalisez le texte affiché sur la page de confirmation de désinscription.
        *   **URL de la tâche Cron :** Affiche l'URL exacte que vous devez configurer comme tâche cron sur votre serveur.
            *   *Effet :* Cette URL déclenche le traitement en arrière-plan du module, l'envoi d'e-mails et la mise à jour des statistiques.
            *   *Recommandé :* Copiez cette URL et configurez la tâche cron de votre serveur pour qu'elle s'exécute toutes les 5 à 15 minutes.
    *   **Paramètres d'e-mail :**
        *   **Nom et e-mail de l'expéditeur :** Le nom et l'adresse e-mail qui apparaîtront comme expéditeur de vos e-mails de rappel.
            *   *Effet :* Impacte la délivrabilité des e-mails et la façon dont les clients perçoivent votre marque.
            *   *Recommandé :* Utilisez un nom de boutique reconnaissable et une adresse e-mail professionnelle (par exemple, `ventes@votreboutique.com`, `noreply@votreboutique.com`).
        *   **Modèle d'e-mail :** Choisissez un modèle de base pour vos e-mails de rappel (si plusieurs sont disponibles).
            *   *Effet :* Détermine la conception et la mise en page globales de vos e-mails.
    *   **Paramètres avancés :**
        *   **Mode débogage :** Activez pour une journalisation détaillée (pour les développeurs).
            *   *Effet :* Fournit des informations plus détaillées dans les journaux, utiles pour le dépannage.
            *   *Recommandé :* NON, sauf demande spécifique du support.
-   **Effet des modifications :** Ces paramètres contrôlent le comportement fondamental du module, depuis le suivi des paniers jusqu'au respect de la vie privée des clients et l'envoi d'e-mails. Des paramètres incorrects peuvent entraîner des opportunités manquées ou une mauvaise expérience client.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Examinez ces paramètres lors de la configuration initiale et périodiquement pour vous assurer qu'ils correspondent aux politiques et à la stratégie marketing de votre boutique. Portez une attention particulière aux paramètres anti-spam et RGPD.

#### 2.2.5 index.php (cartrempro/controllers/admin/index.php)

Ce fichier est une pratique standard de PrestaShop pour empêcher la liste directe des répertoires dans les dossiers d'administration et ne représente généralement pas un écran configurable en soi. Il assure la sécurité en redirigeant ou en affichant une page blanche si quelqu'un tente d'accéder directement au dossier.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | `PS_SSL_ENABLED` (Noyau PrestaShop) | OUI | Assure des liens HTTPS sécurisés dans les e-mails. |
| **Campagnes** | Nom de la campagne | Descriptif | Identification interne de vos campagnes. |
| | Valeur minimale du panier | 0 (ou votre seuil) | Filtre les paniers en fonction de leur valeur pour des campagnes spécifiques. |
| | Groupes de clients | Tous (ou spécifiques) | Cible des segments de clients spécifiques. |
| | Produits dans le panier | Aucun (ou spécifiques) | Cible les paniers contenant des produits/catégories spécifiques. |
| | Délai de l'étape de campagne | 1h, 24h, 3j | Contrôle le timing des e-mails de rappel. |
| | Objet de l'e-mail | Accrocheur | Crucial pour les taux d'ouverture. |
| | Contenu de l'e-mail | Personnalisé | Message principal pour récupérer le panier. |
| | Code de réduction | Optionnel | Incitation à la conversion. |
| | Test A/B | Optionnel | Optimise les performances de la campagne. |
| **Tableau de bord** | Tous les KPI | N/A (Rapport) | Fournit un aperçu des performances et du ROI. |
| **Journaux** | Toutes les entrées de journal | N/A (Rapport) | Historique détaillé pour le dépannage et l'audit. |
| **Paramètres** | Activer le module | OUI | Active/désactive le module. |
| | Valeur min. du panier pour le suivi | 0 (ou votre seuil) | Filtre global pour tous les paniers suivis. |
| | Temps pour considérer le panier abandonné | 30-60 minutes | Définit quand un panier est « abandonné ». |
| | Max. d'e-mails par client | Limite raisonnable | Empêche le spamming des clients. |
| | Temps min. entre les e-mails | Limite raisonnable | Empêche les e-mails rapides. |
| | Activer le lien de désinscription | OUI | Conformité RGPD, choix du client. |
| | URL de la tâche Cron | Copier depuis le module | **CRITIQUE :** Active le traitement en arrière-plan. |
| | Nom et e-mail de l'expéditeur | Nom de votre boutique, e-mail professionnel | Impacte la délivrabilité et la confiance de la marque. |
| | Mode débogage | NON | Pour le dépannage des développeurs uniquement. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes clients ne reçoivent pas les e-mails de rappel. Que dois-je vérifier ?**
R1 :

-   **Tâche Cron :** C'est le problème le plus courant. Assurez-vous que votre tâche cron est correctement configurée sur votre serveur et qu'elle s'exécute régulièrement (toutes les 5 à 15 minutes). L'URL exacte se trouve dans **Abandoned Cart Reminder Pro > Paramètres**.
-   **Module activé :** Vérifiez dans **Abandoned Cart Reminder Pro > Paramètres** que le module est globalement activé.
-   **Campagnes actives :** Vérifiez que vos campagnes sont activées et qu'elles comportent des étapes actives dans **Abandoned Cart Reminder Pro > Campagnes**.
-   **Configuration des e-mails :** Vérifiez les paramètres de messagerie de votre PrestaShop (Paramètres avancés > E-mail) pour vous assurer que votre boutique peut envoyer des e-mails en général.
-   **Filtres anti-spam :** Demandez à un client test de vérifier son dossier de spam/courrier indésirable. Assurez-vous que votre adresse e-mail d'expéditeur est professionnelle et non blacklistée.
-   **Journaux :** Allez dans **Abandoned Cart Reminder Pro > Journaux** pour voir si les e-mails sont mis en file d'attente, envoyés, ou s'il y a des messages d'erreur.

**Q2 : Pourquoi certains paniers abandonnés ne déclenchent-ils pas de campagne ?**
R2 :

-   **Valeur minimale du panier :** Vérifiez la « Valeur minimale du panier pour le suivi » globale dans **Abandoned Cart Reminder Pro > Paramètres** et la « Valeur minimale du panier » spécifique pour vos campagnes dans **Abandoned Cart Reminder Pro > Campagnes**. Les paniers dont la valeur est inférieure à ces seuils seront ignorés.
-   **Temps pour considérer le panier abandonné :** Assurez-vous que le temps défini dans **Abandoned Cart Reminder Pro > Paramètres** s'est écoulé depuis la dernière activité du panier.
-   **Groupes de clients/Ciblage de produits :** Si votre campagne a un ciblage spécifique de groupes de clients ou de produits, assurez-vous que le panier abandonné répond à ces critères.
-   **Limites anti-spam :** Le client a peut-être atteint les limites « Max d'e-mails par client » ou « Temps min. entre les e-mails » définies dans **Abandoned Cart Reminder Pro > Paramètres**.
-   **Désinscription du client :** Le client a peut-être déjà choisi de ne plus recevoir de rappels. Vérifiez les journaux.

**Q3 : Comment m'assurer que les e-mails de rappel s'affichent correctement sur les appareils mobiles ?**
R3 : Le module utilise des modèles d'e-mail réactifs. Cependant, le contenu que vous ajoutez dans l'éditeur d'e-mails peut affecter cela.

-   **Restez simple :** Évitez les mises en page trop complexes ou les images très larges.
-   **Testez :** Envoyez toujours un e-mail de test à vous-même et visualisez-le sur différents appareils (ordinateur de bureau, tablette, téléphone) avant d'activer une campagne.
-   **Thème PrestaShop :** Assurez-vous que votre thème PrestaShop principal est réactif aux mobiles, car les liens dans les e-mails renverront à votre boutique.

**Q4 : Puis-je traduire le contenu des e-mails et les lignes d'objet ?**
R4 : Oui ! Lors de l'édition d'une étape de campagne, vous verrez des onglets de langue pour l'objet et le contenu de l'e-mail. Vous pouvez fournir différentes traductions pour chaque langue installée dans votre boutique PrestaShop. C'est crucial pour les boutiques internationales.

**Q5 : J'ai vidé mon cache Smarty, et maintenant quelque chose semble bizarre. Que s'est-il passé ?**
R5 : Vider le cache Smarty (sous **Paramètres avancés > Performances**) est une étape de dépannage courante pour les problèmes d'affichage. Bien que généralement sûr, cela peut parfois affecter temporairement la façon dont les modules rendent leur contenu jusqu'à ce que le cache soit reconstruit. Si vous remarquez des problèmes d'affichage après avoir vidé le cache, essayez de rafraîchir la page plusieurs fois ou de réenregistrer la configuration du module (même sans rien changer) pour forcer une reconstruction du cache pour le module. Ce module utilise ses propres mécanismes de mise en cache, donc vider le cache Smarty ne devrait pas avoir d'impact direct sur sa fonctionnalité principale, mais plutôt sur l'affichage de son interface d'administration.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de la structure technique du module « Abandoned Cart Reminder Pro » pour les développeurs, les webmasters et les agences techniques.

### 4.1 Aperçu de l'architecture

Le module suit une architecture robuste, basée sur les événements, adhérant au modèle MVC de PrestaShop lorsque cela est approprié, mais tirant également parti d'un conteneur de services personnalisé et de l'auto-chargement pour une meilleure organisation et testabilité. Il s'appuie fortement sur les tâches cron pour le traitement en arrière-plan, garantissant que l'envoi d'e-mails et le suivi des paniers n'affectent pas les performances du front-office. Les composants clés comprennent :

-   **Suivi du panier :** S'accroche à `ActionCartSave` et `ActionValidateOrder` pour surveiller l'état du panier.
-   **Moteur de campagne :** Gère les séquences d'e-mails en plusieurs étapes, le ciblage et la génération de remises.
-   **Processeur de file d'attente :** Gère l'envoi asynchrone d'e-mails via cron.
-   **Analyse et attribution :** Suit les taux de récupération et les revenus.
-   **Contrôleurs d'administration :** Contrôleurs dédiés à la gestion des campagnes, à la consultation des journaux et à la configuration des paramètres.
-   **Conformité RGPD :** Inclut un mécanisme de désinscription.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs gèrent des interactions spécifiques du front-office, principalement pour l'exécution cron, le suivi et la désinscription.

-   `controllers/front/cron.php`
    *   **Nom de la classe :** `CartRemProCronModuleFrontController` (étend `ModuleFrontController`)
    *   **Responsabilité :** C'est le point d'entrée principal de la tâche cron du module. Lorsqu'il est accédé, il déclenche le `CartRemProQueueProcessor` pour traiter la file d'attente des paniers abandonnés, envoyer les e-mails planifiés et mettre à jour les statistiques. Il est conçu pour être appelé par une tâche cron côté serveur, et non directement par les utilisateurs.
-   `controllers/front/index.php`
    *   **Nom de la classe :** `CartRemProIndexModuleFrontController` (étend `ModuleFrontController`)
    *   **Responsabilité :** Une pratique standard de PrestaShop pour empêcher la liste directe des répertoires. Redirige généralement vers la page d'accueil de la boutique ou affiche une page blanche.
-   `controllers/front/optout.php`
    *   **Nom de la classe :** `CartRemProOptoutModuleFrontController` (étend `ModuleFrontController`)
    *   **Responsabilité :** Gère les demandes des clients de se désinscrire des rappels de panier abandonné. Il traite l'action `optout`, met à jour la préférence du client et affiche une page de confirmation (`optout.tpl`).
-   `controllers/front/track.php`
    *   **Nom de la classe :** `CartRemProTrackModuleFrontController` (étend `ModuleFrontController`)
    *   **Responsabilité :** Utilisé pour suivre les ouvertures d'e-mails et les clics sur les liens dans les e-mails de rappel. Il enregistre ces événements dans les journaux du module, permettant l'analyse de l'engagement par e-mail.

#### Contrôleurs d'administration Back-Office

Ces contrôleurs gèrent l'interface du module dans le Back Office de PrestaShop.

-   `controllers/admin/AdminCartRemProCampaignsController.php`
    *   **Nom de l'onglet :** Abandoned Cart Reminder Pro > Campagnes
    *   **Responsabilité :** Gère la création, l'édition, la duplication et la suppression des campagnes de panier abandonné. Il gère la soumission de formulaire pour les détails de la campagne, les étapes, les règles de ciblage et les configurations de test A/B. Il interagit avec les classes `CartRemProCampaign` et `CartRemProCampaignStep`.
-   `controllers/admin/AdminCartRemProDashboardController.php`
    *   **Nom de l'onglet :** Abandoned Cart Reminder Pro > Tableau de bord
    *   **Responsabilité :** Affiche les métriques de performance du module, y compris les paniers abandonnés, les paniers récupérés, les revenus attribués et le ROI. Il agrège les données de `CartRemProAnalytics` et `CartRemProAbandoned` pour présenter un aperçu complet.
-   `controllers/admin/AdminCartRemProLogsController.php`
    *   **Nom de l'onglet :** Abandoned Cart Reminder Pro > Journaux
    *   **Responsabilité :** Fournit un journal détaillé de toutes les activités du module, telles que les abandons de panier, les envois d'e-mails, les ouvertures, les clics et les récupérations. Il permet de filtrer et de rechercher dans ces journaux pour le dépannage et l'audit.
-   `controllers/admin/AdminCartRemProSettingsController.php`
    *   **Nom de l'onglet :** Abandoned Cart Reminder Pro > Paramètres
    *   **Responsabilité :** Gère les paramètres de configuration globaux du module, y compris l'activation/désactivation, les limites anti-spam, les options RGPD et l'affichage de l'URL de la tâche cron. Il interagit avec la classe `Configuration` de PrestaShop.
-   `controllers/admin/index.php`
    *   **Responsabilité :** Fichier de sécurité standard de PrestaShop pour empêcher la liste directe des répertoires.

### 4.3 Classes et modèles de base (`classes/`)

Le module utilise un riche ensemble de classes personnalisées pour sa logique métier, beaucoup étendant `ObjectModel` pour l'interaction avec la base de données.

-   `classes/CartRemProAbandoned.php`
    *   **Table de base de données :** `ps_cartrempro_abandoned`
    *   **Étend :** `ObjectModel`
    *   **Champs `$definition` :** `id_cart`, `id_customer`, `id_shop`, `id_lang`, `cart_value`, `date_add`, `date_upd`, `is_recovered`, `is_optout`
    *   **Méthodes publiques clés :** Gère le suivi et le statut des paniers abandonnés.
-   `classes/CartRemProAbTesting.php`
    *   **Responsabilité :** Gère la logique des tests A/B dans les étapes de campagne, y compris la répartition du trafic et le suivi des taux de conversion pour différentes variations.
-   `classes/CartRemProAdminController.php`
    *   **Étend :** `ModuleAdminController`
    *   **Responsabilité :** Une classe de base pour les contrôleurs d'administration du module, fournissant des fonctionnalités et des utilitaires communs spécifiques à l'interface back-office du module.
-   `classes/CartRemProAdminUi.php`
    *   **Responsabilité :** Classe d'aide pour générer et rendre les éléments d'interface utilisateur courants dans le panneau d'administration, assurant la cohérence.
-   `classes/CartRemProAnalytics.php`
    *   **Responsabilité :** Collecte et traite les données pour le tableau de bord, calculant les KPI comme le taux de récupération, les revenus attribués et le ROI.
-   `classes/CartRemProAntiSpam.php`
    *   **Responsabilité :** Implémente la logique des limites anti-spam, garantissant que les clients ne reçoivent pas trop d'e-mails sur une période donnée.
-   `classes/CartRemProAttribution.php`
    *   **Responsabilité :** Détermine si un panier récupéré peut être attribué à une campagne de rappel de panier abandonné spécifique.
-   `classes/CartRemProAutoload.php`
    *   **Responsabilité :** Auto-chargeur personnalisé pour les classes du module, garantissant qu'elles sont chargées efficacement sans entrer en conflit avec l'auto-chargeur par défaut de PrestaShop.
-   `classes/CartRemProCampaign.php`
    *   **Table de base de données :** `ps_cartrempro_campaign`
    *   **Étend :** `ObjectModel`
    *   **Champs `$definition` :** `name`, `active`, `min_cart_value`, `customer_groups`, `products`, `categories`, `date_add`, `date_upd`
    *   **Méthodes publiques clés :** Représente une campagne de panier abandonné, gérant ses paramètres, ses règles de ciblage et ses étapes associées.
-   `classes/CartRemProCampaignEngine.php`
    *   **Responsabilité :** La logique principale pour évaluer les paniers abandonnés par rapport aux campagnes actives, déterminer quelle campagne (le cas échéant) doit être déclenchée et planifier la prochaine étape d'e-mail.
-   `classes/CartRemProCampaignStep.php`
    *   **Table de base de données :** `ps_cartrempro_campaign_step`
    *   **Étend :** `ObjectModel`
    *   **Champs `$definition` :** `id_cartrempro_campaign`, `delay_hours`, `subject`, `content`, `discount_type`, `discount_value`, `ab_test_active`, `ab_test_variations`
    *   **Méthodes publiques clés :** Définit une seule étape dans une campagne, y compris le contenu de l'e-mail, le délai et la remise.
-   `classes/CartRemProCartTracker.php`
    *   **Responsabilité :** Surveille les paniers des clients, identifie quand ils sont abandonnés et les enregistre dans la table `ps_cartrempro_abandoned`.
-   `classes/CartRemProChannelEmail.php`
    *   **Implémente :** `CartRemProChannelInterface`
    *   **Responsabilité :** Gère l'envoi réel des e-mails de rappel, y compris le rendu des modèles d'e-mails et l'intégration avec la classe Mail de PrestaShop.
-   `classes/CartRemProChannelInterface.php`
    *   **Responsabilité :** Définit une interface commune pour différents canaux de communication (actuellement uniquement l'e-mail, mais extensible pour les SMS, les notifications push web).
-   `classes/CartRemProCompat.php`
    *   **Responsabilité :** Fournit des couches de compatibilité pour différentes versions de PrestaShop (1.7, 8.x, 9.x) pour assurer un fonctionnement fluide sur la plage prise en charge.
-   `classes/CartRemProDiscountGenerator.php`
    *   **Responsabilité :** Crée des codes de réduction uniques et à usage unique (Règles de panier) pour les clients qui reçoivent un e-mail de rappel avec une offre de réduction.
-   `classes/CartRemProEmailRenderer.php`
    *   **Responsabilité :** Rend les modèles Smarty pour les e-mails de rappel, en injectant des données dynamiques comme les détails du panier, les informations client et les codes de réduction.
-   `classes/CartRemProGdpr.php`
    *   **Responsabilité :** Gère les fonctionnalités de conformité au RGPD, en particulier le mécanisme de désinscription du client.
-   `classes/CartRemProProductBlocks.php`
    *   **Responsabilité :** Aide à générer des blocs liés aux produits dans les modèles d'e-mails, tels que les listes de produits de panier abandonné ou les produits recommandés.
-   `classes/CartRemProQueueProcessor.php`
    *   **Responsabilité :** Le cœur de la tâche cron. Il récupère les tâches planifiées de la file d'attente (par exemple, envoyer un e-mail, vérifier l'état du panier), les traite et met à jour les journaux.
-   `classes/CartRemProScheduleGuard.php`
    *   **Responsabilité :** Garantit que les tâches planifiées ne sont exécutées qu'une seule fois et dans les délais prévus, empêchant les e-mails ou actions en double.
-   `classes/CartRemProSegmentation.php`
    *   **Responsabilité :** Implémente la logique de segmentation des clients et des paniers en fonction des règles de ciblage de la campagne (par exemple, valeur du panier, groupe de clients, produits).
-   `classes/CartRemProServiceContainer.php`
    *   **Responsabilité :** Un conteneur d'injection de dépendances personnalisé pour gérer et fournir des instances des services et classes de base du module, améliorant la modularité et la testabilité.
-   `classes/CartRemProStockChecker.php`
    *   **Responsabilité :** Vérifie les niveaux de stock des produits avant d'envoyer des rappels pour s'assurer que les articles d'un panier abandonné sont toujours disponibles.
-   `classes/CartRemProTabInstaller.php`
    *   **Responsabilité :** Gère l'installation et la désinstallation des onglets de menu d'administration du module dans le Back Office de PrestaShop.
-   `classes/index.php`
    *   **Responsabilité :** Fichier de sécurité standard de PrestaShop pour empêcher la liste directe des répertoires.

### 4.4 Actifs JavaScript (`views/js/`)

-   `cartrempro/devtools/crp-ab-stats-demo-console.js`
    *   **Portée :** Back-office (outils de développement)
    *   **Responsabilité :** Probablement un script de développement pour démontrer ou déboguer les statistiques de test A/B dans la console du navigateur. Pas pour une utilisation en production.
-   `cartrempro/devtools/crp-dashboard-demo-console.js`
    *   **Portée :** Back-office (outils de développement)
    *   **Responsabilité :** Similaire à ce qui précède, pour démontrer ou déboguer les données du tableau de bord. Pas pour une utilisation en production.
-   `cartrempro/lib/searchTool/views/js/autocomplete.js`
    *   **Portée :** Back-office (formulaires d'administration)
    *   **Responsabilité :** Fournit une fonctionnalité d'autocomplétion pour les champs de saisie, probablement utilisée pour sélectionner des produits ou des catégories dans le ciblage de campagne. Se lie aux événements de saisie et effectue des appels AJAX pour les suggestions de recherche.
-   `cartrempro/views/js/admin-common.js`
    *   **Portée :** Back-office (administration globale)
    *   **Responsabilité :** Contient des fonctions JavaScript communes et des écouteurs d'événements utilisés sur divers écrans d'administration du module, tels que la gestion générale des formulaires, les fonctions utilitaires AJAX et les améliorations de l'interface utilisateur.
-   `cartrempro/views/js/admin-dashboard.js`
    *   **Portée :** Back-office (Tableau de bord)
    *   **Responsabilité :** Gère les éléments interactifs et la visualisation des données sur le tableau de bord du module, rendant potentiellement des graphiques ou mettant à jour les statistiques dynamiquement.
-   `cartrempro/views/js/campaigns-admin.js`
    *   **Portée :** Back-office (Campagnes)
    *   **Responsabilité :** Gère l'interface utilisateur complexe pour la création et l'édition de campagnes, y compris l'ajout/suppression d'étapes de campagne, la configuration des règles de ciblage, la gestion des options de réduction et la gestion des variations de test A/B. Se lie aux événements de clic sur les boutons, aux événements de modification sur les boîtes de sélection et aux soumissions de formulaires.
-   `cartrempro/views/js/email-builder.js`
    *   **Portée :** Back-office (Campagnes - Contenu de l'e-mail)
    *   **Responsabilité :** Améliore l'éditeur de texte enrichi utilisé pour le contenu de l'e-mail, ajoutant potentiellement des boutons personnalisés pour les espaces réservés dynamiques (par exemple, `{{customer_name}}`, `{{cart_link}}`) ou fournissant des aperçus en temps réel.
-   `cartrempro/views/js/logs-admin.js`
    *   **Portée :** Back-office (Journaux)
    *   **Responsabilité :** Fournit des fonctionnalités interactives pour le tableau des journaux, telles que le filtrage, la recherche, la pagination et potentiellement des fenêtres modales pour afficher les aperçus d'e-mails.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `cartrempro/lib/searchTool/views/css/autocomplete.css`
    *   **Portée :** Back-office (formulaires d'administration)
    *   **Composants d'interface utilisateur principaux :** Style les suggestions de la liste déroulante d'autocomplétion et les champs de saisie utilisés dans l'outil de recherche.
    *   **Sélecteurs de classe CSS clés :** `.autocomplete-suggestions`, `.autocomplete-selected`, `.autocomplete-suggestion`
-   `cartrempro/views/css/admin.css`
    *   **Portée :** Back-office (administration globale)
    *   **Composants d'interface utilisateur principaux :** Fournit un style général pour l'interface d'administration du module, y compris les mises en page du tableau de bord, les formulaires de campagne, les tableaux de journaux et le style général des boutons/champs de saisie.
    *   **Sélecteurs de classe CSS clés :** `.cartrempro-dashboard`, `.cartrempro-campaign-form`, `.cartrempro-logs-table`, `.crp-badge`, `.crp-stat-card`, etc.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)

Le module ne liste pas explicitement les modèles dans un répertoire `hook/`, ce qui suggère que le rendu front-office pour les hooks pourrait être géré directement dans le fichier principal du module ou via des contrôleurs frontaux spécifiques.

#### Modèles d'administration (`views/templates/admin/`)

Ces modèles rendent l'interface Back Office du module.

-   `cartrempro/views/templates/admin/ab_email_preview.tpl`
    *   **Objectif :** Affiche un aperçu d'une variation d'e-mail de test A/B.
-   `cartrempro/views/templates/admin/campaigns.tpl`
    *   **Objectif :** Le modèle principal pour l'écran d'administration « Campagnes », listant les campagnes et fournissant des formulaires pour ajouter/modifier.
-   `cartrempro/views/templates/admin/dashboard.tpl`
    *   **Objectif :** Le modèle principal pour l'écran « Tableau de bord », affichant les KPI et les graphiques de performance.
-   `cartrempro/views/templates/admin/logs.tpl`
    *   **Objectif :** Le modèle principal pour l'écran « Journaux », présentant le tableau des activités du module.
-   `cartrempro/views/templates/admin/logs_email_preview.tpl`
    *   **Objectif :** Affiche un aperçu d'un e-mail des journaux.
-   `cartrempro/views/templates/admin/settings.tpl`
    *   **Objectif :** Le modèle principal pour l'écran « Paramètres », contenant les options de configuration globales.
-   `cartrempro/views/templates/admin/_partials/ab_stats.tpl`
    *   **Objectif :** Rend les statistiques pour les variations de test A/B au sein d'une campagne.
-   `cartrempro/views/templates/admin/_partials/campaign_form.tpl`
    *   **Objectif :** Partiel réutilisable pour le formulaire de création/édition de campagne, y compris les étapes, le ciblage et les paramètres généraux.
-   `cartrempro/views/templates/admin/_partials/campaign_list_compact.tpl`
    *   **Objectif :** Rend une liste compacte de campagnes, éventuellement pour des widgets de tableau de bord ou des aperçus rapides.
-   `cartrempro/views/templates/admin/_partials/campaign_targeting.tpl`
    *   **Objectif :** Rend la section des règles de ciblage dans le formulaire de campagne.
-   `cartrempro/views/templates/admin/_partials/copy_box.tpl`
    *   **Objectif :** Un composant réutilisable pour afficher du texte qui peut être facilement copié (par exemple, l'URL de la tâche cron).
-   `cartrempro/views/templates/admin/_partials/empty_state.tpl`
    *   **Objectif :** Affiche un message lorsqu'une liste ou une section est vide (par exemple, « Aucune campagne trouvée »).
-   `cartrempro/views/templates/admin/_partials/icon_duplicate.tpl`
    *   **Objectif :** Rend une icône de duplication.
-   `cartrempro/views/templates/admin/_partials/icon_edit.tpl`
    *   **Objectif :** Rend une icône d'édition.
-   `cartrempro/views/templates/admin/_partials/icon_trash.tpl`
    *   **Objectif :** Rend une icône de corbeille/suppression.
-   `cartrempro/views/templates/admin/_partials/page_header.tpl`
    *   **Objectif :** Rend un en-tête cohérent pour les pages d'administration du module.
-   `cartrempro/views/templates/admin/_partials/status_badge.tpl`
    *   **Objectif :** Rend un badge visuel indiquant le statut (par exemple, « Actif », « Inactif »).
-   `cartrempro/views/templates/admin/_partials/stat_card.tpl`
    *   **Objectif :** Rend une seule carte statistique pour le tableau de bord (par exemple, « Paniers récupérés »).
-   `cartrempro/views/templates/admin/_partials/step_subject_lang.tpl`
    *   **Objectif :** Rend le champ de saisie de la ligne d'objet avec des onglets de langue pour les étapes de campagne.
-   `cartrempro/views/templates/admin/_partials/toggle_row.tpl`
    *   **Objectif :** Rend une ligne avec un interrupteur à bascule (par exemple, pour activer/désactiver un paramètre).

#### Modèles Front-office (`views/templates/front/`)

-   `cartrempro/views/templates/front/optout.tpl`
    *   **Objectif :** Affiche la page de confirmation après qu'un client se soit désinscrit des rappels de panier abandonné.

#### Modèles d'e-mail (`views/templates/email/`)

-   `cartrempro/views/templates/email/default_recovery.tpl`
    *   **Objectif :** Le modèle de base par défaut pour les e-mails de rappel de panier abandonné. Il inclut des espaces réservés pour le contenu dynamique comme le nom du client, le lien du panier, la liste des produits et les codes de réduction. Les développeurs peuvent personnaliser ce modèle ou en créer de nouveaux pour différentes conceptions d'e-mails.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

Le module crée les tables personnalisées suivantes lors de l'installation :

-   `ps_cartrempro_abandoned` : Stocke les détails des paniers abandonnés.
    *   `id_cartrempro_abandoned` (PK)
    *   `id_cart` (FK vers `ps_cart`)
    *   `id_customer` (FK vers `ps_customer`)
    *   `id_shop` (FK vers `ps_shop`)
    *   `id_lang` (FK vers `ps_lang`)
    *   `cart_value` (décimal)
    *   `date_add` (datetime)
    *   `date_upd` (datetime)
    *   `is_recovered` (tinyint)
    *   `is_optout` (tinyint)
-   `ps_cartrempro_campaign` : Stocke les détails de chaque campagne de rappel.
    *   `id_cartrempro_campaign` (PK)
    *   `name` (varchar)
    *   `active` (tinyint)
    *   `min_cart_value` (décimal)
    *   `customer_groups` (texte - tableau sérialisé)
    *   `products` (texte - tableau sérialisé)
    *   `categories` (texte - tableau sérialisé)
    *   `date_add` (datetime)
    *   `date_upd` (datetime)
-   `ps_cartrempro_campaign_step` : Stocke les détails de chaque étape d'une campagne.
    *   `id_cartrempro_campaign_step` (PK)
    *   `id_cartrempro_campaign` (FK vers `ps_cartrempro_campaign`)
    *   `delay_hours` (int)
    *   `subject` (texte - multi-langue)
    *   `content` (texte - multi-langue)
    *   `discount_type` (varchar)
    *   `discount_value` (décimal)
    *   `ab_test_active` (tinyint)
    *   `ab_test_variations` (texte - tableau sérialisé)
-   `ps_cartrempro_log` : Stocke les journaux détaillés des activités du module.
    *   `id_cartrempro_log` (PK)
    *   `id_cart`
    *   `id_customer`
    *   `id_cartrempro_campaign`
    *   `id_cartrempro_campaign_step`
    *   `event_type` (varchar)
    *   `details` (texte)
    *   `date_add` (datetime)
-   `ps_cartrempro_queue` : Stocke les tâches planifiées pour la tâche cron.
    *   `id_cartrempro_queue` (PK)
    *   `id_cart`
    *   `id_cartrempro_campaign`
    *   `id_cartrempro_campaign_step`
    *   `task_type` (varchar)
    *   `scheduled_at` (datetime)
    *   `processed_at` (datetime)
    *   `status` (varchar)
    *   `error_message` (texte)

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `ActionObjectCartUpdateAfter` | Après la mise à jour d'un objet `Cart` (par exemple, produit ajouté/supprimé, quantité modifiée). | Utilisé pour suivre les modifications des paniers clients et identifier les abandons potentiels. |
| `actionDispatcher` | Avant la distribution d'un contrôleur. | Potentiellement utilisé pour le routage, la réécriture d'URL ou l'initialisation précoce. |
| `ActionCronJob` | Lorsque la tâche cron native de PrestaShop s'exécute (si configurée). | Déclenche le contrôleur `cron.php` du module pour traiter la file d'attente. |
| `ActionFrontControllerInit` | Avant l'initialisation de tout contrôleur frontal. | Utilisé pour la configuration précoce, comme l'enregistrement des actifs du module ou un routage spécifique. |
| `moduleRoutes` | Pendant la génération du routage d'URL. | Permet au module de définir des URL conviviales personnalisées pour ses contrôleurs frontaux (par exemple, `/cartrempro/optout`). |
| `displayModuleRoutes` | Similaire à `moduleRoutes`, souvent utilisé pour afficher ou déboguer les routes. | Moins courant pour la logique fonctionnelle, plus pour le débogage. |
| `ActionCartSave` | Après l'enregistrement d'un panier dans la base de données. | Crucial pour suivre l'activité du panier et identifier quand un panier est abandonné. |
| `ActionValidateOrder` | Après la validation réussie d'une commande. | Utilisé pour marquer un panier abandonné comme « récupéré » s'il aboutit à un achat finalisé. |
| `ActionCustomerAccountAdd` | Après la création d'un nouveau compte client. | Potentiellement utilisé pour la segmentation ou le suivi initial des clients, bien que moins critique pour la logique de base du panier abandonné. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe est dédiée à fournir une assistance rapide et à assurer le bon fonctionnement de votre module.

-   **Historique des commandes et téléchargements MyPresta.eu :** <https://mypresta.eu/my-account/orders/>
-   **Contact support :** [support@mypresta.eu](mailto:support@mypresta.eu)
