---
title: "Valider la TVA dans VIES et appliquer 0% TVA - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Valider la TVA dans VIES et appliquer 0% TVA' par MyPresta.eu."
sidebar:
  label: "Valider la TVA dans VIES et appliquer 0% TVA"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Validate VAT in VIES and set 0% VAT sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/validate-vat-in-vies-and-set-0-vat.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/validate-vat-in-vies-and-set-0-vat/)
>
> ---


# Valider la TVA dans VIES et appliquer 0% TVA

## 1. Exigences et compatibilité

Pour assurer le bon fonctionnement du module "Valider la TVA dans VIES et appliquer 0% TVA", veuillez consulter les exigences suivantes :

*   **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
*   **Compatibilité PHP** : PHP 7.1 - 8.5
*   **Exigences d'hébergement** : Votre environnement d'hébergement doit prendre en charge les extensions PHP standard telles que `cURL` (pour la communication avec le système VIES), `JSON` et `OpenSSL`. Celles-ci sont généralement activées par défaut sur la plupart des hébergeurs modernes.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est la zone de configuration principale du module, où vous contrôlez son comportement et son apparence. Naviguez vers **Modules > Gestionnaire de modules**, recherchez "Valider la TVA dans VIES et appliquer 0% TVA", et cliquez sur "Configurer".

#### **Paramètres généraux**

*   **Votre pays :**
    *   **Ce que fait ce paramètre :** Définit le pays où votre entreprise est enregistrée. C'est crucial pour déterminer si le numéro de TVA d'un client est éligible à la TVA à 0% (c'est-à-dire s'il provient d'un *autre* pays de l'UE).
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur votre pays :* Le module identifiera correctement les ventes intracommunautaires.
        *   *Lorsqu'il est mal défini :* La logique de validation de la TVA pourrait échouer ou appliquer la TVA à 0% de manière incorrecte.
    *   **Valeur recommandée :** Le pays d'enregistrement officiel de votre boutique (par exemple, "France").
    *   **Scénario / exemple de marchand :** Si votre boutique est basée en Allemagne, vous sélectionneriez "Allemagne". Un client de France avec un numéro de TVA français valide serait alors éligible à la TVA à 0%.
*   **Pays éligibles :**
    *   **Ce que fait ce paramètre :** Vous permet de sélectionner les pays de l'UE éligibles à la règle de TVA à 0%. Vous pouvez choisir des pays spécifiques ou sélectionner tous les pays de l'UE.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsque des pays spécifiques sont sélectionnés :* Seuls les clients de ces pays (avec une TVA valide) bénéficieront de la TVA à 0%.
        *   *Lorsque tous les pays de l'UE sont sélectionnés :* Tous les pays de l'UE (sauf le vôtre) seront éligibles.
    *   **Valeur recommandée :** Sélectionnez tous les pays de l'UE, sauf si vous avez des raisons commerciales spécifiques d'en exclure certains.
    *   **Scénario / exemple de marchand :** Si vous ne souhaitez offrir la TVA à 0% qu'aux entreprises en France, en Allemagne et en Espagne, vous ne sélectionneriez que ces pays.
*   **Sélectionner la règle de taxe :**
    *   **Ce que fait ce paramètre :** Spécifie quelle règle de taxe PrestaShop doit être appliquée lorsque la TVA d'un client est validée à 0%. Vous devez avoir une règle de taxe configurée dans PrestaShop pour la TVA à 0%.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'une règle de taxe à 0% est sélectionnée :* Le module appliquera cette règle aux commandes éligibles.
        *   *Lorsqu'une règle de taxe incorrecte est sélectionnée :* Le mauvais taux de taxe pourrait être appliqué, ou le module pourrait ne pas fonctionner comme prévu.
    *   **Valeur recommandée :** Une règle de taxe que vous avez créée dans PrestaShop avec un taux de taxe de 0%.
    *   **Scénario / exemple de marchand :** Vous créeriez une règle de taxe nommée "TVA B2B UE 0%" avec un taux de 0% et la sélectionneriez ici.
*   **Désactiver le module pour les langues sélectionnées :**
    *   **Ce que fait ce paramètre :** Vous permet de désactiver la fonctionnalité de validation de la TVA pour des langues spécifiques dans votre boutique. Cela peut être utile si vous opérez dans des pays non membres de l'UE avec des réglementations fiscales différentes, mais que vous utilisez la même instance PrestaShop.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsque des langues sont sélectionnées :* Le formulaire et la logique de validation de la TVA n'apparaîtront pas ou ne s'appliqueront pas aux clients naviguant dans ces langues.
        *   *Lorsque aucune langue n'est sélectionnée :* Le module sera actif pour toutes les langues.
    *   **Valeur recommandée :** Laisser vide, sauf si vous avez des exigences fiscales spécifiques basées sur la langue.
    *   **Scénario / exemple de marchand :** Si vous avez une version anglaise de votre boutique ciblant à la fois les clients de l'UE et des États-Unis, mais que vous ne souhaitez la validation de la TVA que pour les clients de l'UE, vous pourriez ne pas la désactiver. Cependant, si vous avez une vue de boutique distincte pour un pays non membre de l'UE (par exemple, "Japon"), vous pourriez la désactiver pour la langue japonaise.

#### **Paramètres d'affichage (Visibilité Front-Office)**

Ces paramètres contrôlent où le formulaire de saisie de la TVA et les messages de statut apparaissent à vos clients.

*   **Afficher le formulaire de changement de TVA dans la barre d'en-tête :**
    *   **Ce que fait ce paramètre :** Affiche un petit formulaire ou une notification dans la zone d'en-tête de votre boutique, invitant les clients à saisir leur numéro de TVA.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Une barre apparaît en haut de votre site.
        *   *Lorsqu'il est désactivé :* Aucun formulaire/notification de TVA dans l'en-tête.
    *   **Valeur recommandée :** "Désactivé", sauf si vous souhaitez une grande visibilité pour les clients B2B.
    *   **Scénario / exemple de marchand :** Vous pourriez l'activer si votre boutique est principalement B2B et que vous souhaitez informer immédiatement les clients professionnels de la TVA à 0%.
*   **Afficher le formulaire de changement de TVA dans displayCustomhtml1 (thème personnalisé sp_topdeals) :**
    *   **Ce que fait ce paramètre :** Il s'agit d'un hook spécifique souvent utilisé par les thèmes personnalisés (comme 'sp_topdeals') pour afficher du contenu personnalisé. L'activation de ce paramètre placera le formulaire de TVA dans cette zone spécifique.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Le formulaire de TVA apparaît dans la zone du hook `displayCustomhtml1`.
        *   *Lorsqu'il est désactivé :* Le formulaire n'apparaîtra pas dans cette zone personnalisée spécifique.
    *   **Valeur recommandée :** "Désactivé", sauf si votre thème utilise ce hook et que vous souhaitez que le formulaire y figure.
    *   **Scénario / exemple de marchand :** Si votre thème a une zone de bannière proéminente en haut et que vous souhaitez y placer le formulaire de TVA, vous l'activeriez.
*   **Afficher la barre d'état de la TVA pour les clients connectés :**
    *   **Ce que fait ce paramètre :** Affiche une barre ou un message aux clients connectés, indiquant leur statut de TVA actuel (par exemple, "Votre TVA est valide, 0% appliquée").
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Les clients connectés voient leur statut de TVA.
        *   *Lorsqu'il est désactivé :* Aucune barre d'état de TVA spécifique pour les utilisateurs connectés.
    *   **Valeur recommandée :** "Activé" pour apporter clarté et réassurance à vos clients B2B.
    *   **Scénario / exemple de marchand :** Un client professionnel de retour se connecte et voit immédiatement "Votre TVA est valide, 0% de TVA appliquée à votre panier", ce qui améliore son expérience d'achat.
*   **Afficher la barre de TVA à l'étape des informations personnelles de la commande :**
    *   **Ce que fait ce paramètre :** Affiche le champ de saisie de la TVA et le statut de validation à la première étape du processus de commande (où les clients saisissent leur nom, adresse, etc.). C'est l'emplacement le plus courant et recommandé.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Le champ de TVA est visible et interactif à l'étape des informations personnelles.
        *   *Lorsqu'il est désactivé :* Le champ de TVA n'apparaîtra pas à cette étape, ce qui pourrait rendre plus difficile pour les clients d'appliquer la TVA à 0%.
    *   **Valeur recommandée :** "Activé" (Fortement recommandé).
    *   **Scénario / exemple de marchand :** Un client arrive à la caisse, saisit l'adresse de son entreprise, puis saisit son numéro de TVA dans le champ dédié. Le module le valide, et le prix est mis à jour.
*   **Afficher la barre de TVA sur le récapitulatif de la commande :**
    *   **Ce que fait ce paramètre :** Affiche le statut de la TVA (par exemple, "TVA : 0%") sur la page de récapitulatif de la commande, avant le paiement final.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Les clients voient leur statut de TVA sur le récapitulatif.
        *   *Lorsqu'il est désactivé :* Aucun statut de TVA spécifique sur le récapitulatif.
    *   **Valeur recommandée :** "Activé" pour la transparence.
    *   **Scénario / exemple de marchand :** Un client examine sa commande avant le paiement et voit une confirmation claire que la TVA à 0% a été appliquée.
*   **Afficher la barre de TVA à l'étape de paiement :**
    *   **Ce que fait ce paramètre :** Affiche le statut de la TVA à l'étape finale de paiement de la commande.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Les clients voient leur statut de TVA à l'étape de paiement.
        *   *Lorsqu'il est désactivé :* Aucun statut de TVA spécifique à l'étape de paiement.
    *   **Valeur recommandée :** "Activé" pour la confirmation finale.
    *   **Scénario / exemple de marchand :** Juste avant de cliquer sur "Payer maintenant", le client voit "Total : 100,00 € (TVA 0%)", confirmant l'application correcte de la taxe.
*   **Afficher la barre de changement de TVA sur la page produit :**
    *   **Ce que fait ce paramètre :** Affiche un formulaire de saisie de TVA ou un message de statut directement sur les pages produits individuelles.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Un formulaire/message de TVA apparaît sur les pages produits.
        *   *Lorsqu'il est désactivé :* Aucun formulaire/message de TVA sur les pages produits.
    *   **Valeur recommandée :** "Désactivé" pour éviter l'encombrement, sauf si vous avez une forte orientation B2B et que vous souhaitez afficher les prix hors TVA tôt.
    *   **Scénario / exemple de marchand :** Un client professionnel naviguant sur une page produit peut saisir son numéro de TVA pour voir immédiatement le prix sans TVA, ce qui l'aide dans ses décisions d'achat.
*   **Afficher le formulaire de changement de TVA dans displayProductAdditionalInfo :**
    *   **Ce que fait ce paramètre :** Il s'agit d'un hook PrestaShop standard sur la page produit, généralement utilisé pour des informations supplémentaires. L'activation de ce paramètre placera le formulaire de TVA dans cette zone.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Le formulaire de TVA apparaît dans la zone du hook `displayProductAdditionalInfo`.
        *   *Lorsqu'il est désactivé :* Le formulaire n'apparaîtra pas dans cette zone spécifique.
    *   **Valeur recommandée :** "Désactivé", sauf si vous le souhaitez spécifiquement à cet endroit.
    *   **Scénario / exemple de marchand :** Similaire au paramètre "Afficher la barre de changement de TVA sur la page produit", mais cible un hook spécifique.
*   **Afficher le formulaire de changement de TVA dans displayBanner :**
    *   **Ce que fait ce paramètre :** Affiche le formulaire ou le statut de la TVA dans le hook `displayBanner`, qui est souvent utilisé pour les bannières supérieures ou les messages promotionnels.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Le formulaire/statut de la TVA apparaît dans la zone de la bannière.
        *   *Lorsqu'il est désactivé :* Aucun formulaire/statut de la TVA dans la zone de la bannière.
    *   **Valeur recommandée :** "Désactivé" pour éviter l'encombrement, sauf si vous avez une conception de bannière spécifique pour cela.
    *   **Scénario / exemple de marchand :** Vous pourriez l'utiliser pour afficher un message "Êtes-vous une entreprise ? Saisissez votre TVA pour une taxe à 0% !" dans une bannière proéminente.
*   **Afficher le formulaire de changement de TVA dans displayCustomhtml1 (thème personnalisé sp_topdeals) :** (Dupliqué, déjà couvert ci-dessus)
*   **Afficher la barre d'état de la TVA pour les clients connectés :** (Dupliqué, déjà couvert ci-dessus)
*   **Afficher la barre de TVA à l'étape des informations personnelles de la commande :** (Dupliqué, déjà couvert ci-dessus)
*   **Afficher la barre de TVA sur le récapitulatif de la commande :** (Dupliqué, déjà couvert ci-dessus)
*   **Afficher la barre de TVA à l'étape de paiement :** (Dupliqué, déjà couvert ci-dessus)
*   **Note d'autoliquidation sur la facture :**
    *   **Ce que fait ce paramètre :** Lorsque la TVA à 0% est appliquée suite à une vérification VIES valide, ce paramètre garantit qu'une note "Autoliquidation" est automatiquement ajoutée à la facture du client. C'est une exigence légale pour les ventes B2B intracommunautaires.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Les factures pour les commandes à TVA 0% incluront la note d'autoliquidation.
        *   *Lorsqu'il est désactivé :* Les factures n'incluront pas la note, ce qui pourrait entraîner une non-conformité.
    *   **Valeur recommandée :** "Activé" (Fortement recommandé pour la conformité légale).
    *   **Scénario / exemple de marchand :** Un client professionnel allemand achète dans votre boutique polonaise avec un numéro de TVA valide. La facture indique automatiquement "Autoliquidation - TVA non applicable en vertu de l'article 196 de la directive 2006/112/CE du Conseil".

#### **Paramètres avancés**

*   **Revalider le numéro de TVA du client à chaque commande :**
    *   **Ce que fait ce paramètre :** Si activé, le module revérifiera le numéro de TVA du client auprès de VIES à chaque fois qu'il passe une commande, même s'il a été précédemment validé.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Garantit que le numéro de TVA est toujours à jour et valide, mais ajoute un léger délai à la commande.
        *   *Lorsqu'il est désactivé :* Repose sur la validation initiale, ce qui est plus rapide mais pourrait manquer des changements de statut de TVA.
    *   **Valeur recommandée :** "Activé" pour une conformité et une précision maximales.
    *   **Scénario / exemple de marchand :** Le numéro de TVA d'un client professionnel peut devenir invalide avec le temps. La revalidation garantit que vous n'appliquez pas par erreur la TVA à 0% à un numéro invalide.
*   **Prévenir les inondations de requêtes VIES (bloquer pendant X minutes) :**
    *   **Ce que fait ce paramètre :** Si un client saisit à plusieurs reprises des numéros de TVA invalides, ce paramètre bloque temporairement les tentatives de validation supplémentaires pendant une période spécifiée afin d'éviter les abus ou la surcharge du système VIES.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Après plusieurs tentatives échouées, le client est temporairement bloqué pour ne pas réessayer.
        *   *Lorsqu'il est désactivé :* Aucune protection contre les inondations, permettant des tentatives illimitées.
    *   **Valeur recommandée :** "Activé" avec un temps de blocage raisonnable (par exemple, 5-10 minutes).
    *   **Scénario / exemple de marchand :** Un bot ou un utilisateur malveillant tente de deviner des numéros de TVA. Ce paramètre les empêche de solliciter continuellement l'API VIES.
*   **Mettre en cache les résultats de validation VIES pendant X heures :**
    *   **Ce que fait ce paramètre :** Stocke les résultats des validations VIES réussies pendant un nombre d'heures spécifié. Cela réduit le nombre d'appels directs au système VIES, accélérant le processus et réduisant l'utilisation de l'API externe.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Validation plus rapide pour les clients récurrents ou pendant la période de cache.
        *   *Lorsqu'il est désactivé :* Chaque validation est un appel VIES en direct, ce qui peut être plus lent.
    *   **Valeur recommandée :** "Activé" avec un temps de cache de 24 à 72 heures (par exemple, 48 heures).
    *   **Scénario / exemple de marchand :** Un client valide son numéro de TVA. S'il revient sur votre site dans les 48 heures, le module utilise le résultat mis en cache au lieu de faire une nouvelle requête VIES.
*   **Revérifier le statut de la TVA du panier toutes les X secondes :**
    *   **Ce que fait ce paramètre :** Définit la fréquence à laquelle le module revérifie le statut de la TVA du panier en arrière-plan, particulièrement utile si les prix sont dynamiques ou si le client modifie son adresse/numéro de TVA pendant la commande.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur une valeur basse :* Mises à jour plus fréquentes, expérience potentiellement plus fluide mais charge serveur plus élevée.
        *   *Lorsqu'il est défini sur une valeur élevée :* Mises à jour moins fréquentes, pourrait nécessiter un rafraîchissement manuel de la page pour que les changements de TVA se reflètent.
    *   **Valeur recommandée :** 5-10 secondes.
    *   **Scénario / exemple de marchand :** Un client saisit son numéro de TVA, et dans les 5 secondes, le total du panier est mis à jour pour refléter la TVA à 0% sans rechargement de page.
*   **Activer la revalidation automatique du numéro de TVA (Tâche Cron) :**
    *   **Ce que fait ce paramètre :** Active une tâche en arrière-plan (tâche cron) qui revalide périodiquement tous les numéros de TVA client stockés auprès de VIES. Cela garantit que même les anciens numéros de TVA restent valides.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Les numéros de TVA sont périodiquement vérifiés pour leur validité, assurant la conformité.
        *   *Lorsqu'il est désactivé :* Les numéros de TVA ne sont vérifiés qu'au moment de la saisie ou de la commande, ce qui peut entraîner des informations obsolètes.
    *   **Valeur recommandée :** "Activé" (Fortement recommandé pour une conformité à long terme).
    *   **Scénario / exemple de marchand :** Un client a passé une commande il y a 6 mois avec un numéro de TVA valide. La tâche cron le revérifie et constate qu'il est maintenant invalide, ce qui vous permet de le signaler pour les futures commandes.
*   **Intervalle de revalidation de la tâche Cron (jours) :**
    *   **Ce que fait ce paramètre :** Définit la fréquence d'exécution de la tâche cron pour revalider les numéros de TVA.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur un nombre faible :* Revalidations plus fréquentes, plus grande précision, mais plus de requêtes VIES.
        *   *Lorsqu'il est défini sur un nombre élevé :* Revalidations moins fréquentes, moins grande précision, moins de requêtes VIES.
    *   **Valeur recommandée :** 30-90 jours (par exemple, 60 jours).
    *   **Scénario / exemple de marchand :** Le définir à 30 jours signifie que tous les numéros de TVA sont revérifiés une fois par mois.
*   **Clé API VIES (Optionnel) :**
    *   **Ce que fait ce paramètre :** Vous permet d'utiliser des API de validation de TVA alternatives (comme Apilayer, AbstractAPI, VATStack) au lieu du système VIES par défaut. Celles-ci peuvent parfois offrir des fonctionnalités plus robustes ou des options de secours.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'une clé est saisie :* Le module tentera d'utiliser l'API tierce spécifiée pour la validation.
        *   *Lorsqu'il est vide :* Le module utilise par défaut le système VIES officiel.
    *   **Valeur recommandée :** Laisser vide, sauf si vous rencontrez des problèmes avec VIES ou si vous avez besoin de fonctionnalités spécifiques d'une API tierce. Si vous en utilisez une, saisissez la clé fournie par ce service.
    *   **Scénario / exemple de marchand :** Si le système VIES est fréquemment en panne ou lent, vous pourriez vous abonner au service de validation de TVA d'Apilayer et saisir votre clé API ici comme alternative fiable.

#### **Clés API (Optionnel - pour les services de validation de TVA alternatifs)**

*   **Clé API Apilayer :**
    *   **Ce que fait ce paramètre :** Saisissez votre clé API si vous êtes abonné au service de validation de TVA d'Apilayer.
    *   **Effet de la modification de ce paramètre :** Active la validation via Apilayer.
    *   **Valeur recommandée :** Laisser vide, sauf si vous avez un compte Apilayer.
*   **Clé API AbstractAPI :**
    *   **Ce que fait ce paramètre :** Saisissez votre clé API si vous êtes abonné au service de validation de TVA d'AbstractAPI.
    *   **Effet de la modification de ce paramètre :** Active la validation via AbstractAPI.
    *   **Valeur recommandée :** Laisser vide, sauf si vous avez un compte AbstractAPI.
*   **Clé API VATStack :**
    *   **Ce que fait ce paramètre :** Saisissez votre clé API si vous êtes abonné au service de validation de TVA de VATStack.
    *   **Effet de la modification de ce paramètre :** Active la validation via VATStack.
    *   **Valeur recommandée :** Laisser vide, sauf si vous avez un compte VATStack.

#### **Tableau de référence rapide de la configuration**

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Config principale | Votre pays | Pays de votre boutique | Définit le pays de votre entreprise pour les ventes intracommunautaires. |
| Config principale | Pays éligibles | Tous les pays de l'UE | Sélectionne les pays de l'UE où la TVA à 0% s'applique. |
| Config principale | Sélectionner la règle de taxe | Votre règle de taxe à 0% | Spécifie la règle de taxe PrestaShop pour la TVA à 0%. |
| Config principale | Désactiver le module pour les langues sélectionnées | Vide | Désactive le module pour des langues spécifiques. |
| Config principale | Afficher le formulaire de changement de TVA dans la barre d'en-tête | Désactivé | Affiche le formulaire de TVA dans l'en-tête. |
| Config principale | Afficher le formulaire de changement de TVA dans displayCustomhtml1 | Désactivé | Affiche le formulaire de TVA dans le hook de thème personnalisé. |
| Config principale | Afficher la barre d'état de la TVA pour les clients connectés | Activé | Affiche le statut de la TVA aux utilisateurs connectés. |
| Config principale | Afficher la barre de TVA à l'étape des informations personnelles de la commande | Activé (Fortement recommandé) | Affiche le champ de TVA à la première étape de la commande. |
| Config principale | Afficher la barre de TVA sur le récapitulatif de la commande | Activé | Affiche le statut de la TVA sur le récapitulatif de la commande. |
| Config principale | Afficher la barre de TVA à l'étape de paiement | Activé | Affiche le statut de la TVA à l'étape de paiement. |
| Config principale | Afficher la barre de changement de TVA sur la page produit | Désactivé | Affiche le formulaire de TVA sur les pages produits. |
| Config principale | Afficher le formulaire de changement de TVA dans displayProductAdditionalInfo | Désactivé | Affiche le formulaire de TVA dans le hook d'informations supplémentaires du produit. |
| Config principale | Afficher le formulaire de changement de TVA dans displayBanner | Désactivé | Affiche le formulaire de TVA dans le hook de bannière. |
| Config principale | Note d'autoliquidation sur la facture | Activé (Fortement recommandé) | Ajoute la note légale "Autoliquidation" aux factures. |
| Config principale | Revalider le numéro de TVA du client à chaque commande | Activé | Revérifie la TVA pour chaque nouvelle commande. |
| Config principale | Prévenir les inondations de requêtes VIES (bloquer pendant X minutes) | Activé (5-10 minutes) | Bloque les tentatives répétées de TVA invalide. |
| Config principale | Mettre en cache les résultats de validation VIES pendant X heures | Activé (24-72 heures) | Met en cache les résultats VIES pour accélérer la validation. |
| Config principale | Revérifier le statut de la TVA du panier toutes les X secondes | 5-10 secondes | Fréquence de mise à jour du statut de la TVA du panier. |
| Config principale | Activer la revalidation automatique du numéro de TVA (Tâche Cron) | Activé (Fortement recommandé) | Active la revalidation en arrière-plan de tous les numéros de TVA. |
| Config principale | Intervalle de revalidation de la tâche Cron (jours) | 30-90 jours (par exemple, 60) | Fréquence de revalidation de la tâche cron. |
| Config principale | Clé API Apilayer | Vide | Clé pour le service de validation de TVA Apilayer. |
| Config principale | Clé API AbstractAPI | Vide | Clé pour le service de validation de TVA AbstractAPI. |
| Config principale | Clé API VATStack | Vide | Clé pour le service de validation de TVA VATStack. |

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### **Audit de validation de TVA (Back Office > Clients > Audit de validation de TVA)**

Cette section dédiée vous permet de consulter et de gérer toutes les tentatives de validation de TVA effectuées via votre boutique.

*   **Nom de l'écran et emplacement du menu :** **Clients > Audit de validation de TVA** (Ce nouvel élément de menu est ajouté par le module).
*   **Actions et paramètres disponibles :**
    *   **Vue Grille / Gestion :** Cet écran présente un tableau (grille) de toutes les tentatives de validation de TVA. Pour chaque entrée, vous verrez généralement :
        *   **Nom du client :** Le nom du client associé à la validation.
        *   **Numéro de TVA :** Le numéro de TVA qui a été saisi.
        *   **Pays :** Le code pays associé au numéro de TVA.
        *   **Statut de validation :** Si le numéro de TVA était "Valide", "Invalide" ou "Erreur" (par exemple, système VIES indisponible).
        *   **Date de validation :** Quand la tentative de validation a eu lieu.
        *   **ID de commande :** Si la validation a conduit à une commande, l'ID de commande associé.
        *   **Source :** Où la validation a eu lieu (par exemple, "Commande", "Compte client").
        *   **Détails/Raison :** Plus d'informations sur le résultat de la validation, en particulier pour les entrées invalides.
    *   **Filtrage et tri :** Vous pouvez généralement filtrer la liste par client, numéro de TVA, statut ou plage de dates pour trouver des entrées spécifiques. Le tri vous permet d'organiser les données.
    *   **Exportation :** Le module peut offrir une option pour exporter ce journal d'audit, ce qui est utile pour la comptabilité et les audits fiscaux.
*   **Effet des modifications :** Cet écran est principalement destiné à l'audit et au reporting. Vous ne pouvez pas modifier directement le statut de TVA d'un client ici, mais vous pouvez consulter l'historique des validations. Ces données sont cruciales pour prouver la conformité lors des inspections fiscales.
*   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Examinez périodiquement ce journal d'audit, surtout si vous remarquez des écarts dans l'application de la TVA ou si vous recevez des demandes de clients concernant la TVA.
    2.  Recherchez les statuts "Invalide" ou "Erreur" pour identifier les problèmes potentiels liés à la saisie du client ou à la disponibilité du système VIES.
    3.  Utilisez la fonction d'exportation pour fournir des données à votre comptable ou aux autorités fiscales si demandé.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Audit de validation de TVA | Vue Grille | N/A | Affiche un journal historique de toutes les tentatives de validation de TVA. |
| Audit de validation de TVA | Filtres et tri | N/A | Aide à localiser des entrées de validation spécifiques. |
| Audit de validation de TVA | Exporter les données | N/A | Permet d'exporter le journal d'audit à des fins d'archivage et fiscales. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes clients saisissent des numéros de TVA valides, mais la TVA à 0% n'est pas appliquée.**
*   **R :**
    1.  **Vérifiez le paramètre "Votre pays" :** Assurez-vous qu'il est correctement défini sur le pays de votre boutique dans la configuration du module.
    2.  **Vérifiez les "Pays éligibles" :** Assurez-vous que le pays du client est sélectionné dans la liste des pays éligibles.
    3.  **Confirmez la "Règle de taxe sélectionnée" :** Assurez-vous d'avoir créé une règle de taxe à 0% dans PrestaShop (**International > Taxes > Règles de taxe**) et qu'elle est correctement sélectionnée dans les paramètres du module.
    4.  **Videz le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache". Parfois, un ancien cache peut empêcher les nouveaux paramètres de prendre effet.
    5.  **Vérifiez la disponibilité de VIES :** Le système VIES peut parfois être temporairement indisponible. Vous pouvez vérifier son statut sur le site officiel de la Commission européenne.

**Q2 : Le formulaire de validation de la TVA n'apparaît pas sur ma page de paiement.**
*   **R :**
    1.  **Vérifiez les paramètres d'affichage :** Dans la configuration du module, assurez-vous que "Afficher la barre de TVA à l'étape des informations personnelles de la commande" (et d'autres options d'affichage pertinentes) est défini sur "Activé".
    2.  **Compatibilité du thème :** Si vous utilisez un thème fortement personnalisé, il pourrait remplacer les hooks PrestaShop standard. Vérifiez si votre thème a des zones spécifiques pour `displayProductAdditionalInfo`, `displayCustomhtml1` ou d'autres hooks où vous avez essayé de placer le formulaire. Vous devrez peut-être consulter le développeur de votre thème.
    3.  **Conflits de modules :** Désactivez temporairement d'autres modules liés à la caisse pour voir s'il y a un conflit.

**Q3 : Je vois des messages "Erreur" ou "VIES Indisponible" pendant la validation.**
*   **R :**
    1.  **Statut du système VIES :** Le système VIES peut connaître des temps d'arrêt. Vérifiez le site officiel de VIES pour connaître le statut actuel.
    2.  **Extension cURL :** Assurez-vous que votre hébergeur a activé l'extension PHP `cURL`. C'est essentiel pour que le module puisse communiquer avec des API externes comme VIES. Contactez votre hébergeur si vous n'êtes pas sûr.
    3.  **Pare-feu/Sécurité :** Le pare-feu ou les paramètres de sécurité de votre serveur peuvent bloquer les connexions sortantes vers le serveur VIES. Encore une fois, contactez votre hébergeur.
    4.  **Clés API :** Si vous essayez d'utiliser une API tierce (Apilayer, AbstractAPI, VATStack), assurez-vous que la clé API est correctement saisie et active auprès de ce service.

**Q4 : Comment m'assurer que la tâche cron pour la revalidation s'exécute ?**
*   **R :**
    1.  **Activer la tâche Cron :** Dans la configuration du module, assurez-vous que "Activer la revalidation automatique du numéro de TVA (Tâche Cron)" est "Activé".
    2.  **Module Cron PrestaShop :** Vous avez besoin d'un module de tâche cron PrestaShop séparé (par exemple, "Gestionnaire de tâches cron" par PrestaShop) installé et configuré pour déclencher périodiquement la tâche cron du module.
    3.  **Cron d'hébergement :** Alternativement, vous pouvez configurer une tâche cron au niveau du serveur (via cPanel, Plesk ou SSH) pour appeler l'URL cron du module. La configuration du module fournit généralement l'URL exacte à utiliser.
    4.  **Vérifier le journal d'audit :** Une fois que la tâche cron aurait dû s'exécuter, vérifiez l'écran "Audit de validation de TVA" dans le Back Office. Vous devriez voir de nouvelles entrées de validation avec une source "Cron".

**Q5 : Pourquoi certains pays de l'UE n'apparaissent-ils pas dans la liste des "Pays éligibles" ?**
*   **A :** Le module s'appuie sur la liste des pays de PrestaShop. Assurez-vous que tous les pays de l'UE souhaités sont activés dans votre boutique PrestaShop (**International > Localisation > Pays**) et qu'ils sont marqués comme "Est un pays de l'UE" et "Contient des états" (le cas échéant).

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une exploration approfondie de la structure technique du module "Valider la TVA dans VIES et appliquer 0% TVA", conçue pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module suit un modèle MVC (Modèle-Vue-Contrôleur) PrestaShop standard, exploitant fortement les hooks pour l'intégration dans le front et le back office. Il introduit plusieurs classes personnalisées pour la logique métier, l'interaction API et la gestion des données. Les composants clés comprennent :

*   **Classe de module principale (`eurovat.php`) :** Gère l'installation, la désinstallation, l'enregistrement des hooks et le formulaire de configuration principal (`getContent()`).
*   **Contrôleurs frontaux :** Gèrent les requêtes AJAX pour la validation de la TVA et les soumissions de formulaires.
*   **Contrôleurs d'administration :** Fournissent des interfaces dédiées pour l'audit de validation de la TVA.
*   **Classes de base :** Encapsulent la logique métier pour l'interaction VIES, la gestion des taxes, l'analyse et la persistance des données (souvent en étendant `ObjectModel` ou en utilisant un modèle de dépôt).
*   **Templates :** Templates Smarty pour le rendu des formulaires front-office, la configuration back-office et les vues d'audit.
*   **Hooks :** Utilisation extensive des hooks pour injecter des fonctionnalités à divers points du cycle de vie de PrestaShop (par exemple, page produit, caisse, traitement des commandes, vue client admin).

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

*   `controllers/front/cron.php`
    *   **Nom de la classe :** `EurovatCronModuleFrontController` (étend `ModuleFrontController`)
    *   **Responsabilité :** Gère l'exécution de la tâche cron du module. Ce contrôleur est généralement appelé par un service cron externe (par exemple, cron du serveur ou module `Cron tasks manager` de PrestaShop) pour déclencher des tâches en arrière-plan comme la revalidation des numéros de TVA. Il traite le hook `ActionCronJob`.
*   `controllers/front/form.php`
    *   **Nom de la classe :** `EurovatFormModuleFrontController` (étend `ModuleFrontController`)
    *   **Responsabilité :** Gère probablement l'affichage et la soumission du formulaire de saisie de TVA dans divers contextes front-office (par exemple, page produit, blocs HTML personnalisés). Il pourrait rendre `views/templates/front/form.tpl`.
*   `controllers/front/index.php`
    *   **Nom de la classe :** `EurovatIndexModuleFrontController` (étend `ModuleFrontController`)
    *   **Responsabilité :** Un contrôleur frontal générique, potentiellement utilisé pour un repli ou une logique d'affichage simple. Souvent, `index.php` dans un répertoire de contrôleur sert de placeholder ou de base pour d'autres contrôleurs.
*   `controllers/front/validate.php`
    *   **Nom de la classe :** `EurovatValidateModuleFrontController` (étend `ModuleFrontController`)
    *   **Responsabilité :** Le point d'accès AJAX principal pour la validation en temps réel des numéros de TVA. Il reçoit le numéro de TVA et les données du pays, interagit avec le client VIES et renvoie une réponse JSON indiquant la validité et potentiellement la mise à jour du statut fiscal du panier.

#### Contrôleurs d'administration Back-Office

*   `controllers/admin/AdminEurovatVatValidationAuditController.php`
    *   **Nom de la classe :** `AdminEurovatVatValidationAuditController` (étend `ModuleAdminController`)
    *   **Nom de l'onglet :** "Audit de validation de TVA" (sous le menu Clients)
    *   **Entité gérée :** `EurovatValidation` (table personnalisée `ps_eurovat_validation`)
    *   **Responsabilité :** Fournit l'interface administrative pour visualiser, filtrer et gérer le journal d'audit de toutes les tentatives de validation de TVA. Il utilise les composants `HelperList` ou `Grid` de PrestaShop pour afficher les données de la table `ps_eurovat_validation`.
*   `controllers/admin/index.php`
    *   **Nom de la classe :** `EurovatIndexAdminController` (étend `ModuleAdminController`)
    *   **Responsabilité :** Similaire à `index.php` du front-office, il s'agit probablement d'un placeholder ou d'un contrôleur de base. Il pourrait rediriger vers la configuration principale ou le contrôleur d'audit.

### 4.3 Classes et modèles de base (`classes/`)

*   `classes/EurovatAlertService.php`
    *   **Responsabilité :** Gère et affiche les alertes ou notifications au sein du module, éventuellement liées au statut VIES, aux problèmes de clé API ou aux problèmes de configuration.
*   `classes/EurovatAlertsHelper.php`
    *   **Responsabilité :** Une classe d'aide pour `EurovatAlertService`, fournissant des fonctions utilitaires pour la gestion des alertes.
*   `classes/EurovatAnalyticsService.php`
    *   **Responsabilité :** Collecte et traite les données liées à la validation de la TVA, telles que les taux de réussite, les types d'erreurs et l'utilisation de l'API, potentiellement pour l'affichage dans un widget de tableau de bord.
*   `classes/EurovatApiUsageHelper.php`
    *   **Responsabilité :** Suit et gère l'utilisation des API de validation de TVA externes (VIES, Apilayer, etc.), potentiellement en implémentant la limitation de débit ou la surveillance.
*   `classes/EurovatAuditHelper.php`
    *   **Responsabilité :** Aide `AdminEurovatVatValidationAuditController` à gérer et interroger la table `ps_eurovat_validation`.
*   `classes/EurovatConfiguration.php`
    *   **Responsabilité :** Une classe statique ou singleton pour centraliser l'accès aux valeurs de configuration du module (`Configuration::get('EUROVAT_...')`). Fournit un moyen plus propre de récupérer les paramètres.
*   `classes/EurovatCronHelper.php`
    *   **Responsabilité :** Contient la logique exécutée par la tâche cron, telle que l'itération des numéros de TVA des clients et l'initiation de la revalidation.
*   `classes/EurovatErrorClassifier.php`
    *   **Responsabilité :** Classe les erreurs de validation de TVA et fournit des messages conviviaux pour différents types d'erreurs (par exemple, format invalide, VIES indisponible, non-concordance de pays).
*   `classes/EurovatExportService.php`
    *   **Responsabilité :** Gère l'exportation des données d'audit de validation de TVA, probablement au format CSV ou Excel.
*   `classes/EurovatOrderProofHelper.php`
    *   **Responsabilité :** Rassemble et prépare les données liées à la validation de la TVA pour une commande spécifique, utilisées pour générer une preuve d'application de la TVA à 0%.
*   `classes/EurovatOrderTaxNormalizer.php`
    *   **Responsabilité :** Ajuste les détails de la taxe de commande lorsque la TVA à 0% est appliquée, assurant la cohérence entre le panier, la commande et la facture.
*   `classes/EurovatProofPackService.php`
    *   **Responsabilité :** Crée potentiellement un "pack de preuves" (par exemple, un document PDF) contenant toutes les preuves nécessaires pour une transaction à TVA 0%.
*   `classes/EurovatTaxManager.php`
    *   **Responsabilité :** La classe centrale pour appliquer et gérer les changements de taxe basés sur les résultats de validation de TVA, interagissant avec le système de taxe de PrestaShop.
*   `classes/EurovatTaxService.php`
    *   **Responsabilité :** Fournit des méthodes utilitaires liées aux calculs et à l'application des taxes au sein du module.
*   `classes/EurovatValidationRepository.php`
    *   **Table de base de données avec laquelle il interagit :** `ps_eurovat_validation`
    *   **Indique s'il étend `ObjectModel` :** Probablement pas directement, mais gère les objets `EurovatValidation` ou les requêtes de base de données brutes.
    *   **Méthodes publiques clés et logique métier encapsulée :** Opérations CRUD pour les enregistrements de validation de TVA, interrogation de l'historique de validation, stockage des résultats de validation.
*   `classes/EurovatViesClient.php`
    *   **Responsabilité :** L'interface principale pour communiquer avec le système VIES (ou des API alternatives comme Apilayer, AbstractAPI, VATStack). Gère les requêtes API, les réponses et la gestion des erreurs.
*   `classes/index.php`
    *   **Responsabilité :** Un placeholder de sécurité pour empêcher la liste des répertoires.

### 4.4 Actifs JavaScript (`views/js/`)

*   `eurovat/views/js/adminEurovatAlerts.js`
    *   **Portée :** Back-office
    *   **Description :** Gère l'affichage et l'interaction avec les alertes dans le panneau d'administration, potentiellement des mises à jour dynamiques ou des messages dismissibles.
*   `eurovat/views/js/adminEurovatCountries.js`
    *   **Portée :** Back-office
    *   **Description :** Gère l'interface de sélection de pays dans la configuration du module, éventuellement avec une fonctionnalité de sélection multiple ou un filtrage dynamique.
*   `eurovat/views/js/adminEurovatCron.js`
    *   **Portée :** Back-office
    *   **Description :** Fournit la logique d'interface utilisateur pour les paramètres de la tâche cron, affichant potentiellement les dernières heures d'exécution, la prochaine exécution planifiée ou les options de déclenchement manuel.
*   `eurovat/views/js/adminEurovatDashboard.js`
    *   **Portée :** Back-office
    *   **Description :** Alimente le widget du tableau de bord (le cas échéant) affichant des analyses ou des métriques clés liées à la validation de la TVA. Utilise AJAX pour récupérer les données et potentiellement des bibliothèques de graphiques.
*   `eurovat/views/js/adminEurovatTooltips.js`
    *   **Portée :** Back-office
    *   **Description :** Initialise et gère les info-bulles pour les options de configuration dans le panneau d'administration, fournissant un contexte utile.
*   `eurovat/views/js/eurovat.js`
    *   **Portée :** Front-office
    *   **Description :** Le JavaScript principal du front-office.
        *   **Écouteurs d'événements :** Se lie aux événements d'entrée sur le champ du numéro de TVA (par exemple, `keyup`, `change`), aux soumissions de formulaires et potentiellement à `prestashop.on('updateCart')` ou à des événements similaires.
        *   **Manipulation du DOM :** Affiche dynamiquement les messages de statut de validation (valide/invalide), met à jour les totaux du panier, affiche/masque des éléments en fonction du statut de la TVA.
        *   **Appels AJAX :** Envoie le numéro de TVA et les données du pays à `controllers/front/validate.php` pour une validation en temps réel.
        *   **Autres :** Implémente l'intervalle de "revérification du statut de la TVA du panier", la logique de protection contre les inondations.
*   `eurovat/views/js/eurovatBoMockConsole.js`
    *   **Portée :** Back-office (développement/débogage)
    *   **Description :** Probablement un utilitaire pour simuler la sortie de la console ou fournir des capacités de débogage améliorées au sein du Back Office de PrestaShop, non typiquement utilisé en production.

### 4.5 Feuilles de style CSS (`views/css/`)

*   `eurovat/views/css/admin_eurovat.css`
    *   **Portée :** Style du formulaire d'administration du Back-office.
    *   **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :** Éléments de la page de configuration, tableau de la liste d'audit, widgets du tableau de bord, alertes et info-bulles au sein de l'interface d'administration du module.
    *   **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger :** `.eurovat-admin-config`, `.eurovat-alert`, `.eurovat-dashboard-widget`, `.eurovat-audit-table`.
*   `eurovat/views/css/eurovat.css`
    *   **Portée :** Style client du Front-office.
    *   **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :** Champs de saisie de la TVA, messages de statut de validation (succès/erreur), barres d'état de la TVA dans l'en-tête/page produit/caisse, notes d'autoliquidation.
    *   **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger :** `.eurovat-vat-form`, `.eurovat-status-message.valid`, `.eurovat-status-message.invalid`, `.eurovat-header-bar`, `.eurovat-product-vat-info`, `.eurovat-checkout-vat-status`.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

*   `eurovat/views/templates/hook/adminDashboardWidget.tpl`
    *   **Hook :** Potentiellement `displayAdminHomeQuickview` ou un hook de tableau de bord personnalisé.
    *   **Sorties :** Un widget pour le tableau de bord d'administration de PrestaShop, affichant des analyses ou des statistiques rapides liées à la validation de la TVA.
*   `eurovat/views/templates/hook/adminOrderProofPack.tpl`
    *   **Hook :** `displayAdminOrder` ou `displayAdminOrderTabContent` (sur la page de visualisation de la commande).
    *   **Sorties :** Un bloc ou un onglet dans la page des détails de la commande de l'administration, permettant aux administrateurs de visualiser ou de générer des documents de preuve de TVA pour une commande spécifique.
*   `eurovat/views/templates/hook/customerHistory.tpl`
    *   **Hook :** `displayCustomerAccount` ou `displayMyAccountBlock`.
    *   **Sorties :** Informations sur l'historique de validation de la TVA du client ou son statut actuel dans sa zone de compte personnel.
*   `eurovat/views/templates/hook/displayBanner.tpl`
    *   **Hook :** `displayBanner` (ou un hook de bannière global similaire).
    *   **Sorties :** Le formulaire de saisie de la TVA ou un message promotionnel sur la TVA à 0%, généralement affiché en haut de la boutique.

#### Templates d'administration (`views/templates/admin/`)

*   `eurovat/views/templates/admin/alerts.tpl`
    *   **Sorties :** Structure HTML pour l'affichage de diverses alertes et notifications dans le Back Office.
*   `eurovat/views/templates/admin/audit.tpl`
    *   **Sorties :** Le template principal pour `AdminEurovatVatValidationAuditController`, rendant la liste d'audit de validation de TVA.
*   `eurovat/views/templates/admin/configure.tpl`
    *   **Sorties :** Le formulaire de configuration principal du module, rendu par `getContent()` dans `eurovat.php`. Contient tous les paramètres décrits dans la section 4.1.
*   `eurovat/views/templates/admin/countriesSelector.tpl`
    *   **Sorties :** Un template réutilisable pour l'interface de sélection de pays dans la configuration.
*   `eurovat/views/templates/admin/cron.tpl`
    *   **Sorties :** La section de configuration liée aux paramètres de la tâche cron, y compris l'intervalle et l'activation.
*   `eurovat/views/templates/admin/dashboard.tpl`
    *   **Sorties :** La vue complète du tableau de bord, intégrant potentiellement `adminDashboardWidget.tpl` et d'autres analyses.
*   `eurovat/views/templates/admin/hooksRepair.tpl`
    *   **Sorties :** Un template utilitaire, éventuellement pour diagnostiquer et réparer les hooks manquants ou mal enregistrés.
*   `eurovat/views/templates/admin/proof_pack_view.tpl`
    *   **Sorties :** Une vue détaillée pour un pack de preuves de TVA, probablement dans la page des détails de la commande.
*   `eurovat/views/templates/admin/vat_audit_list_settings.tpl`
    *   **Sorties :** Paramètres ou filtres spécifiques à l'affichage de la liste d'audit de TVA.
*   `eurovat/views/templates/admin/vat_audit_tabs.tpl`
    *   **Sorties :** Navigation par onglets pour la section d'audit de TVA, s'il existe plusieurs sous-sections (par exemple, journal d'audit, analyses).

#### Templates Front-Office (`views/templates/front/`)

*   `eurovat/views/templates/front/form.tpl`
    *   **Sorties :** La structure HTML principale pour le formulaire de saisie du numéro de TVA, utilisée dans divers hooks front-office (page produit, caisse, en-tête).

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

*   `ps_eurovat_validation`
    *   **Objectif :** Stocke un journal historique de toutes les tentatives de validation de TVA.
    *   **Champs clés (attendus) :**
        *   `id_eurovat_validation` (Clé primaire)
        *   `id_customer` (Clé étrangère vers `ps_customer`)
        *   `id_cart` (Clé étrangère vers `ps_cart`)
        *   `id_order` (Clé étrangère vers `ps_order`)
        *   `vat_number` (Le numéro de TVA saisi)
        *   `country_code` (Le code pays associé au numéro de TVA)
        *   `validation_status` (par exemple, 'valid', 'invalid', 'error')
        *   `validation_response` (Réponse brute de VIES/API)
        *   `validation_date` (Horodatage de la validation)
        *   `source` (par exemple, 'checkout', 'customer_account', 'cron')
        *   `ip_address` (Adresse IP de l'utilisateur qui a effectué la validation)

*   `ps_configuration`
    *   **Objectif :** Stocke tous les paramètres de configuration du module.
    *   **Clés de configuration principales :**
        *   `EUROVAT_YOUR_COUNTRY`
        *   `EUROVAT_ELIGIBLE_COUNTRIES`
        *   `EUROVAT_TAX_RULE`
        *   `EUROVAT_DISPLAY_HEADER`
        *   `EUROVAT_DISPLAY_CUSTOMHTML1`
        *   `EUROVAT_DISPLAY_LOGGED_STATUS`
        *   `EUROVAT_DISPLAY_CHECKOUT_PERSONAL`
        *   `EUROVAT_DISPLAY_CHECKOUT_SUMMARY`
        *   `EUROVAT_DISPLAY_CHECKOUT_PAYMENT`
        *   `EUROVAT_DISPLAY_PRODUCT_PAGE`
        *   `EUROVAT_REVERSE_CHARGE_NOTE`
        *   `EUROVAT_REVALIDATE_ON_ORDER`
        *   `EUROVAT_FLOOD_OFF_MINUTES`
        *   `EUROVAT_CACHE_TTL_HOURS`
        *   `EUROVAT_CART_RECHECK_INTERVAL`
        *   `EUROVAT_CRON_REVALIDATE_ENABLED`
        *   `EUROVAT_CRON_INTERVAL_DAYS`
        *   `EUROVAT_APILAYER_KEY`
        *   `EUROVAT_ABSTRACTAPI_KEY`
        *   `EUROVAT_VATSTACK_KEY`
        *   `EUROVAT_DISABLED_LANGS`

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Injecter CSS/JS, ou afficher une barre d'état de TVA globale. |
| `displayProductAdditionalInfo` | Sur la page produit, généralement sous la description du produit. | Afficher le formulaire de saisie de TVA ou le statut sur les pages produits. |
| `displayCustomhtml1` | Hook personnalisé, souvent dans la section supérieure du thème (par exemple, `sp_topdeals`). | Afficher le formulaire de saisie de TVA dans des zones de thème spécifiques. |
| `displayPaymentTop` | En haut de l'étape de paiement à la caisse. | Afficher le statut de la TVA ou le formulaire avant le paiement. |
| `displayBanner` | Dans une zone de bannière, généralement en haut du site. | Afficher le formulaire de saisie de TVA ou un message promotionnel. |
| `displayAdminCustomers` | Sur la liste des clients ou la page de détails du client dans le BO. | Ajouter des informations ou des actions liées à la TVA pour les clients. |
| `ActionDispatcher` | Avant qu'un contrôleur ne soit dispatché. | Modifier le routage ou le contexte en fonction du statut de la TVA. |
| `ActionGetProductPropertiesAfter` | Après la récupération des propriétés du produit. | Ajuster les prix des produits en fonction du statut de TVA du client. |
| `ActionProductPriceCalculation` | Pendant le calcul du prix du produit. | Appliquer la TVA à 0% aux prix des produits si éligible. |
| `ActionBeforeValidateOrder` | Juste avant la validation d'une commande. | Effectuer la validation finale de la TVA, ajuster les taxes de commande. |
| `ActionCronJob` | Déclenché par le module cron de PrestaShop. | Exécuter des tâches en arrière-plan comme la revalidation de la TVA. |
| `ActionObjectAddressUpdateAfter` | Après la mise à jour d'un objet adresse (par exemple, dans le compte client). | Revalider la TVA si les détails de l'adresse changent. |
| `ActionTaxManager` | Lorsque les règles de taxe sont gérées ou appliquées. | Intercepter et modifier l'application de la taxe en fonction de la validation de la TVA. |
| `ActionPresentCart` | Avant l'affichage du panier. | Mettre à jour les totaux du panier et afficher le statut de la TVA. |
| `ActionFilterDeliveryOptionList` | Filtre les options de livraison disponibles. | Potentiellement ajuster les coûts de livraison en fonction du statut de la TVA (moins courant). |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe s'engage à garantir le fonctionnement optimal du module et sa compatibilité avec les dernières versions de PrestaShop.

*   **Historique des commandes et téléchargements MyPresta.eu :** [https://mypresta.eu/my-account/orders/](https://mypresta.eu/my-account/orders/)
*   **Support MyPresta.eu :** [https://mypresta.eu/contact](https://mypresta.eu/contact)
---
