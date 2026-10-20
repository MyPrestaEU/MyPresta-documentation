---
title: "Virement bancaire avec remise - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Virement bancaire avec remise' par MyPresta.eu."
sidebar:
  label: "Virement bancaire avec remise - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Bankwire with discount sur MyPresta.eu](https://mypresta.eu/modules/payment-process/bankwire-with-discount.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/payment/bankwire-with-discount/)
>
> ---


# Virement bancaire avec remise

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises pour PrestaShop lui-même et généralement disponibles sur tous les environnements d'hébergement modernes.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Virement bancaire avec remise)

C'est l'écran de configuration principal où vous configurerez toutes les fonctionnalités essentielles du module.

#### **Paramètres généraux**

- **Activer le paiement par virement bancaire :**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la méthode de paiement « Virement bancaire avec remise » dans votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients verront « Payer par virement bancaire » comme option de paiement lors du processus de commande.
    - *Lorsqu'désactivé :* L'option de paiement par virement bancaire sera masquée aux clients.
  - **Valeur recommandée :** OUI (pour utiliser les fonctionnalités du module).
  - **Scénario marchand :** Vous souhaitez proposer les paiements par virement bancaire.
- **Titre du virement bancaire :**

  - **Ce que fait ce paramètre :** Définit le titre affiché pour l'option de paiement par virement bancaire sur la page de paiement.
  - **Effet de la modification de ce paramètre :** Modifie le texte que les clients voient lorsqu'ils choisissent cette méthode de paiement.
  - **Valeur recommandée :** « Payer par virement bancaire », « Virement bancaire (avec remise !) », ou similaire.
  - **Scénario marchand :** Vous souhaitez étiqueter clairement la méthode de paiement pour les clients.
- **Instructions de paiement (Résumé sur le paiement) :**

  - **Ce que fait ce paramètre :** Un court texte affiché sur la page de sélection du paiement (avant confirmation) pour donner aux clients des instructions rapides ou des informations sur le virement bancaire.
  - **Effet de la modification de ce paramètre :** Fournit un contexte immédiat au client concernant la méthode de virement bancaire.
  - **Valeur recommandée :** « Vous recevrez les coordonnées bancaires après avoir confirmé votre commande. Remise appliquée ! »
  - **Scénario marchand :** Vous souhaitez informer les clients des prochaines étapes ou mettre en évidence l'avantage de la remise tôt.
- **Instructions de paiement (Après confirmation de commande) :**

  - **Ce que fait ce paramètre :** Instructions détaillées affichées sur la page de confirmation de commande après qu'un client a passé une commande par virement bancaire. C'est ici que vous mettez les détails de votre compte bancaire.
  - **Effet de la modification de ce paramètre :** Fournit les informations essentielles aux clients pour effectuer le virement bancaire.
  - **Valeur recommandée :** Incluez le nom de votre banque, le titulaire du compte, l'IBAN, le SWIFT/BIC, et toute note spécifique (par exemple, « Veuillez inclure votre référence de commande dans la description du virement »).
  - **Scénario marchand :** C'est crucial pour que les clients puissent finaliser leur paiement avec succès.

#### **Détails du compte bancaire**

Ces champs sont utilisés pour fournir les informations de votre compte bancaire aux clients.

- **Titulaire du compte :**

  - **Ce que fait ce paramètre :** Le nom du titulaire du compte bancaire.
  - **Effet de la modification de ce paramètre :** Affiche ce nom au client.
  - **Valeur recommandée :** Le nom de votre entreprise ou votre nom personnel.
  - **Scénario marchand :** Essentiel pour le virement bancaire.
- **Nom de la banque :**

  - **Ce que fait ce paramètre :** Le nom de votre banque.
  - **Effet de la modification de ce paramètre :** Affiche ce nom au client.
  - **Valeur recommandée :** par exemple, « Deutsche Bank », « Bank of America ».
  - **Scénario marchand :** Essentiel pour le virement bancaire.
- **Adresse :**

  - **Ce que fait ce paramètre :** L'adresse de votre banque.
  - **Effet de la modification de ce paramètre :** Affiche cette adresse au client.
  - **Valeur recommandée :** L'adresse de l'agence de votre banque.
  - **Scénario marchand :** Peut être requis pour les virements internationaux.
- **IBAN (International Bank Account Number) :**

  - **Ce que fait ce paramètre :** Votre IBAN, un numéro de compte bancaire international standardisé.
  - **Effet de la modification de ce paramètre :** Affiche ce numéro au client.
  - **Valeur recommandée :** Votre IBAN complet.
  - **Scénario marchand :** Crucial pour les virements bancaires, en particulier en Europe.
- **SWIFT/BIC (Bank Identifier Code) :**

  - **Ce que fait ce paramètre :** Votre code SWIFT/BIC, utilisé pour les virements bancaires internationaux.
  - **Effet de la modification de ce paramètre :** Affiche ce code au client.
  - **Valeur recommandée :** Votre code SWIFT/BIC complet.
  - **Scénario marchand :** Essentiel pour les virements bancaires internationaux.
- **Informations supplémentaires :**

  - **Ce que fait ce paramètre :** Toute note ou instruction supplémentaire que vous souhaitez fournir concernant le virement bancaire (par exemple, « Veuillez prévoir 1 à 3 jours ouvrables pour le traitement »).
  - **Effet de la modification de ce paramètre :** Fournit des conseils supplémentaires au client.
  - **Valeur recommandée :** Toute instruction spécifique non couverte par d'autres champs.
  - **Scénario marchand :** Vous souhaitez gérer les attentes des clients concernant les délais de virement.

#### **Paramètres de remise et de supplément**

Cette section vous permet de configurer des remises ou des suppléments pour l'utilisation du virement bancaire.

- **Type de remise :**

  - **Ce que fait ce paramètre :** Détermine comment la remise est calculée.
  - **Effet de la modification de ce paramètre :**
    - *Pourcentage :* La remise est un pourcentage du total de la commande.
    - *Montant fixe :* La remise est un montant forfaitaire, quel que soit le total de la commande.
  - **Valeur recommandée :** Pourcentage (souvent plus attrayant pour des valeurs de commande variables).
  - **Scénario marchand :** Vous souhaitez offrir 5 % de réduction ou une remise fixe de 10 €.
- **Valeur de la remise :**

  - **Ce que fait ce paramètre :** La valeur réelle de la remise (par exemple, « 5 » pour 5 % ou « 10 € » pour un montant fixe).
  - **Effet de la modification de ce paramètre :** Applique directement la remise au total de la commande si le virement bancaire est choisi.
  - **Valeur recommandée :** Une valeur qui rend le virement bancaire attrayant sans nuire à vos marges.
  - **Scénario marchand :** Vous décidez d'offrir une remise de 3 % ou une remise de 5 €.
- **Base du pourcentage (si le type de remise est un pourcentage) :**

  - **Ce que fait ce paramètre :** Spécifie à quelle partie du total de la commande la remise en pourcentage est appliquée.
  - **Effet de la modification de ce paramètre :** Modifie le montant de base pour le calcul de la remise.
    - *Total de la commande (avec taxes) :* Remise calculée sur le prix total TTC.
    - *Total de la commande (sans taxes) :* Remise calculée sur le prix HT.
    - *Total des produits (avec taxes) :* Remise uniquement sur la valeur des produits, TTC.
    - *Total des produits (sans taxes) :* Remise uniquement sur la valeur des produits, HT.
  - **Valeur recommandée :** Total de la commande (avec taxes) pour la simplicité et la clarté pour le client.
  - **Scénario marchand :** Vous souhaitez offrir 5 % de réduction sur le prix final total que le client voit.
- **Valeur minimale du panier :**

  - **Ce que fait ce paramètre :** La valeur totale minimale qu'une commande doit avoir pour que la remise par virement bancaire soit appliquée.
  - **Effet de la modification de ce paramètre :** La remise n'apparaîtra et ne sera appliquée que si le total du panier atteint ou dépasse cette valeur.
  - **Valeur recommandée :** Laissez vide si aucun minimum, ou définissez une valeur pour encourager les commandes plus importantes.
  - **Scénario marchand :** Vous ne souhaitez offrir une remise que sur les commandes de plus de 100 €.
- **Valeur maximale du panier :**

  - **Ce que fait ce paramètre :** La valeur totale maximale qu'une commande peut avoir pour que la remise par virement bancaire soit appliquée.
  - **Effet de la modification de ce paramètre :** La remise ne sera pas appliquée si le total du panier dépasse cette valeur.
  - **Valeur recommandée :** Laissez vide si aucun maximum, ou définissez une valeur pour limiter l'exposition à la remise sur les très grosses commandes.
  - **Scénario marchand :** Vous ne souhaitez pas accorder de remise sur les commandes de plus de 1000 €.
- **Devises :**

  - **Ce que fait ce paramètre :** Sélectionnez les devises pour lesquelles la méthode de paiement par virement bancaire (et sa remise) sera disponible.
  - **Effet de la modification de ce paramètre :** L'option de paiement n'apparaîtra que pour les clients qui achètent dans les devises sélectionnées.
  - **Valeur recommandée :** Sélectionnez toutes les devises que vous acceptez.
  - **Scénario marchand :** Vous n'acceptez les virements bancaires qu'en EUR et USD.
- **Zones :**

  - **Ce que fait ce paramètre :** Sélectionnez les zones géographiques pour lesquelles la méthode de paiement par virement bancaire (et sa remise) sera disponible.
  - **Effet de la modification de ce paramètre :** L'option de paiement n'apparaîtra que pour les clients dont l'adresse de livraison se trouve dans les zones sélectionnées.
  - **Valeur recommandée :** Sélectionnez toutes les zones vers lesquelles vous expédiez.
  - **Scénario marchand :** Vous ne proposez le virement bancaire qu'en Europe.
- **Pays :**

  - **Ce que fait ce paramètre :** Sélectionnez les pays spécifiques où la méthode de paiement par virement bancaire (et sa remise) sera disponible.
  - **Effet de la modification de ce paramètre :** Remplace les paramètres de zone pour des pays spécifiques.
  - **Valeur recommandée :** Sélectionnez tous les pays vers lesquels vous expédiez.
  - **Scénario marchand :** Vous souhaitez exclure un pays spécifique des paiements par virement bancaire.
- **Groupes de clients :**

  - **Ce que fait ce paramètre :** Sélectionnez les groupes de clients qui peuvent voir et utiliser la méthode de paiement par virement bancaire (et sa remise).
  - **Effet de la modification de ce paramètre :** Seuls les clients appartenant aux groupes sélectionnés verront cette option de paiement.
  - **Valeur recommandée :** Sélectionnez tous les groupes de clients pertinents (par exemple, « Client », « Visiteur », « Invité »).
  - **Scénario marchand :** Vous ne souhaitez proposer le virement bancaire qu'aux clients enregistrés.

#### **Gestion des commandes impayées**

Ces fonctionnalités vous aident à gérer les commandes passées par virement bancaire mais non encore payées.

- **Envoyer des rappels pour les commandes impayées :**

  - **Ce que fait ce paramètre :** Active ou désactive les rappels par e-mail automatisés aux clients pour les commandes par virement bancaire impayées.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Le module enverra des e-mails de rappel.
    - *Lorsqu'désactivé :* Aucun rappel ne sera envoyé.
  - **Valeur recommandée :** OUI (aide à réduire les paiements abandonnés).
  - **Scénario marchand :** Vous souhaitez rappeler doucement aux clients de finaliser leur paiement.
- **Premier rappel après (jours) :**

  - **Ce que fait ce paramètre :** Le nombre de jours après qu'une commande est passée avant l'envoi du premier e-mail de rappel.
  - **Effet de la modification de ce paramètre :** Contrôle le moment du premier rappel.
  - **Valeur recommandée :** 2-3 jours (donne aux clients le temps de payer, mais pas trop longtemps).
  - **Scénario marchand :** Vous souhaitez envoyer un rappel si le paiement n'est pas reçu dans les 2 jours.
- **Max de rappels par commande :**

  - **Ce que fait ce paramètre :** Le nombre maximum d'e-mails de rappel qu'une commande déclenchera.
  - **Effet de la modification de ce paramètre :** Empêche d'envoyer trop de rappels aux clients.
  - **Valeur recommandée :** 1-2 (suffisant pour rappeler sans agacer).
  - **Scénario marchand :** Vous souhaitez n'envoyer qu'un seul e-mail de rappel.
- **Annulation automatique des commandes impayées :**

  - **Ce que fait ce paramètre :** Active ou désactive l'annulation automatique des commandes par virement bancaire qui restent impayées après une période spécifiée.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les commandes seront automatiquement annulées, libérant ainsi l'inventaire.
    - *Lorsqu'désactivé :* Les commandes resteront en statut « En attente de paiement par virement bancaire » indéfiniment.
  - **Valeur recommandée :** OUI (automatise la gestion des stocks et maintient la liste des commandes propre).
  - **Scénario marchand :** Vous ne souhaitez pas conserver l'inventaire pour les commandes impayées trop longtemps.
- **Annuler après (jours) :**

  - **Ce que fait ce paramètre :** Le nombre de jours après qu'une commande est passée avant qu'elle ne soit automatiquement annulée si elle est impayée.
  - **Effet de la modification de ce paramètre :** Contrôle le moment où les commandes impayées sont annulées.
  - **Valeur recommandée :** 5-7 jours (permet un délai raisonnable pour le paiement, mais empêche les retenues indéfinies).
  - **Scénario marchand :** Vous souhaitez annuler les commandes si le paiement n'est pas reçu dans les 7 jours.
- **Mettre automatiquement les fraudeurs sur liste noire :**

  - **Ce que fait ce paramètre :** Si activé, les clients qui passent à plusieurs reprises des commandes par virement bancaire et les font ensuite annuler en raison de non-paiement seront ajoutés à une liste noire.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients dépassant le seuil seront mis sur liste noire.
    - *Lorsqu'désactivé :* Aucun client ne sera mis sur liste noire automatiquement.
  - **Valeur recommandée :** OUI (aide à dissuader les clients frauduleux ou qui perdent du temps).
  - **Scénario marchand :** Vous souhaitez empêcher les clients qui ne paient jamais de passer de futures commandes par virement bancaire.
- **Seuil de commandes annulées :**

  - **Ce que fait ce paramètre :** Le nombre de commandes par virement bancaire annulées qu'un client peut avoir avant d'être automatiquement mis sur liste noire.
  - **Effet de la modification de ce paramètre :** Définit la tolérance au non-paiement avant la mise sur liste noire.
  - **Valeur recommandée :** 2-3 (permet des erreurs authentiques mais détecte les récidivistes).
  - **Scénario marchand :** Vous souhaitez mettre un client sur liste noire après 3 commandes par virement bancaire impayées et annulées.

#### **Paramètres avancés**

- **Jeton de tâche Cron :**

  - **Ce que fait ce paramètre :** Un jeton de sécurité unique utilisé pour sécuriser l'URL de la tâche cron du module. C'est essentiel pour que les fonctionnalités de rappel et d'annulation automatisées fonctionnent.
  - **Effet de la modification de ce paramètre :** La tâche cron ne s'exécutera que si ce jeton est correctement inclus dans l'URL.
  - **Valeur recommandée :** Laissez tel quel. Ne modifiez pas sauf si vous savez ce que vous faites.
  - **Scénario marchand :** Vous devez configurer une tâche cron sur votre serveur pour exécuter les tâches automatisées du module. L'URL cron ressemblera à `votreboutique.com/module/bankwiredis/cron?token=VOTRE_JETON_ICI`.
- **Sélecteurs CSS pour les mises à jour dynamiques :**

  - **Ce que fait ce paramètre :** Ces champs vous permettent de spécifier les sélecteurs CSS pour les éléments de votre page de paiement qui affichent le total du panier, le sous-total et les frais de port. Le module les utilise pour mettre à jour dynamiquement les prix lorsqu'une remise est appliquée.
  - **Effet de la modification de ce paramètre :** Si votre thème utilise des classes CSS non standard pour ces éléments, l'ajustement de ces sélecteurs garantit que la remise est correctement reflétée dans les prix affichés lors du paiement.
  - **Valeur recommandée :** Laissez par défaut, sauf si la remise ne s'affiche pas correctement sur votre page de paiement. En cas de problème, consultez le développeur de votre thème ou un webmaster.
  - **Scénario marchand :** Votre thème personnalisé utilise `.my-custom-total-price` au lieu du `.cart-total-price` par défaut. Vous mettriez à jour ce champ pour vous assurer que la remise est appliquée visuellement.
- **Modèle d'e-mail :**

  - **Ce que fait ce paramètre :** Vous permet de sélectionner un modèle d'e-mail personnalisé pour les instructions de paiement par virement bancaire et les rappels.
  - **Effet de la modification de ce paramètre :** Modifie la conception et le contenu des e-mails envoyés par le module.
  - **Valeur recommandée :** Par défaut (sauf si vous avez un modèle personnalisé).
  - **Scénario marchand :** Vous souhaitez utiliser un modèle d'e-mail de marque pour les communications par virement bancaire.

#### **Règles de visibilité (Ciblage avancé des remises)**

Cette section vous permet de créer des règles très spécifiques pour l'offre de la remise par virement bancaire.

- **Nom de la règle :**

  - **Ce que fait ce paramètre :** Un nom descriptif pour votre règle de remise (par exemple, « Remise de vacances pour virement bancaire »).
  - **Effet de la modification de ce paramètre :** Vous aide à identifier et à gérer différentes règles.
  - **Valeur recommandée :** Nom clair et concis.
  - **Scénario marchand :** Vous avez plusieurs règles de remise et devez les distinguer.
- **Active :**

  - **Ce que fait ce paramètre :** Active ou désactive cette règle de remise spécifique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* La règle est active et ses conditions seront vérifiées.
    - *Lorsqu'désactivé :* La règle est ignorée.
  - **Valeur recommandée :** OUI (si vous souhaitez que la règle s'applique).
  - **Scénario marchand :** Vous souhaitez désactiver temporairement une remise saisonnière.
- **Position (priorité) :**

  - **Ce que fait ce paramètre :** Détermine l'ordre dans lequel les règles sont évaluées si plusieurs règles peuvent s'appliquer. Les nombres inférieurs ont une priorité plus élevée.
  - **Effet de la modification de ce paramètre :** Si le panier d'un client correspond à plusieurs règles, celle avec la position la plus basse sera appliquée.
  - **Valeur recommandée :** Utilisez des nombres séquentiels (1, 2, 3…) pour gérer la priorité.
  - **Scénario marchand :** Si un client est éligible à la fois à une règle « 5 % de réduction générale » (position 10) et à une règle « 10 % de réduction VIP » (position 5), la règle VIP sera appliquée.
- **Type de remise, Valeur de la remise, Base du pourcentage, Valeur minimale du panier, Valeur maximale du panier, Devises, Zones, Pays, Groupes de clients :**

  - **Ce que fait ce paramètre :** Ce sont les mêmes paramètres que ceux décrits dans la section « Paramètres de remise et de supplément » ci-dessus, mais appliqués spécifiquement à *cette règle individuelle*. Cela vous permet d'avoir des montants de remise ou des conditions différents pour différents scénarios.
  - **Effet de la modification de ce paramètre :** La remise définie dans cette règle ne s'appliquera que si toutes ses conditions spécifiques sont remplies.
  - **Valeur recommandée :** Configurez en fonction de votre stratégie promotionnelle spécifique.
  - **Scénario marchand :** Vous souhaitez offrir une remise de 10 % pour les paiements par virement bancaire uniquement aux clients du groupe « Grossiste », et uniquement pour les commandes de plus de 500 €.
- **Produits :**

  - **Ce que fait ce paramètre :** Vous permet de spécifier que cette règle de remise ne s'applique que si certains produits sont dans le panier.
  - **Effet de la modification de ce paramètre :** La remise par virement bancaire ne sera offerte que si un ou plusieurs des produits sélectionnés sont présents dans le panier du client.
  - **Valeur recommandée :** Laissez vide pour appliquer à tous les produits, ou sélectionnez des produits spécifiques pour des promotions ciblées.
  - **Scénario marchand :** Vous souhaitez offrir une remise par virement bancaire uniquement si un client achète un article de grande valeur spécifique.
- **Catégories :**

  - **Ce que fait ce paramètre :** Vous permet de spécifier que cette règle de remise ne s'applique que si des produits de certaines catégories sont dans le panier.
  - **Effet de la modification de ce paramètre :** La remise par virement bancaire ne sera offerte que si un ou plusieurs produits des catégories sélectionnées sont présents dans le panier du client.
  - **Valeur recommandée :** Laissez vide pour appliquer à toutes les catégories, ou sélectionnez des catégories spécifiques pour des promotions ciblées.
  - **Scénario marchand :** Vous souhaitez offrir une remise par virement bancaire uniquement pour les produits de votre catégorie « Électronique ».

#### **Tableau de référence rapide de la configuration**

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activer le paiement par virement bancaire | OUI | Active/désactive la méthode de paiement. |
| | Titre du virement bancaire | « Payer par virement bancaire » | Texte affiché pour l'option de paiement. |
| | Instructions de paiement (paiement) | Texte court et clair | Informations affichées sur la page de sélection du paiement. |
| | Instructions de paiement (confirmation) | Informations bancaires détaillées | Détails bancaires et instructions après la commande. |
| | Titulaire du compte | Nom de votre entreprise | Nom sur le compte bancaire. |
| | Nom de la banque | Votre banque | Nom de votre banque. |
| | Adresse | Adresse de votre banque | Adresse de votre banque. |
| | IBAN | Votre IBAN | Numéro de compte bancaire international. |
| | SWIFT/BIC | Votre SWIFT/BIC | Code d'identification bancaire pour les virements internationaux. |
| | Informations supplémentaires | Notes facultatives | Instructions supplémentaires pour les clients. |
| | Type de remise | Pourcentage | Comment la remise est calculée (pourcentage/fixe). |
| | Valeur de la remise | 0 (ou valeur souhaitée) | Le montant ou le pourcentage réel de la remise. |
| | Base du pourcentage | Total de la commande (avec taxes) | Montant sur lequel la remise en pourcentage s'applique. |
| | Valeur minimale du panier | Vide (ou valeur souhaitée) | Valeur minimale de la commande pour la remise. |
| | Valeur maximale du panier | Vide (ou valeur souhaitée) | Valeur maximale de la commande pour la remise. |
| | Devises | Toutes actives | Devises où le virement bancaire est disponible. |
| | Zones | Toutes actives | Zones géographiques où le virement bancaire est disponible. |
| | Pays | Tous actifs | Pays spécifiques où le virement bancaire est disponible. |
| | Groupes de clients | Tous actifs | Groupes de clients qui peuvent utiliser le virement bancaire. |
| | Envoyer des rappels pour les commandes impayées | OUI | Active les rappels par e-mail pour les commandes impayées. |
| | Premier rappel après (jours) | 2-3 jours | Délai avant le premier rappel. |
| | Max de rappels par commande | 1-2 | Nombre maximum d'e-mails de rappel. |
| | Annulation automatique des commandes impayées | OUI | Annule automatiquement les commandes impayées. |
| | Annuler après (jours) | 5-7 jours | Délai avant l'annulation automatique. |
| | Mettre automatiquement les fraudeurs sur liste noire | OUI | Met sur liste noire les clients ayant trop de commandes annulées. |
| | Seuil de commandes annulées | 2-3 | Nombre de commandes annulées avant la mise sur liste noire. |
| | Jeton de tâche Cron | Généré automatiquement | Jeton de sécurité pour la tâche cron. |
| | Sélecteurs CSS | Par défaut (ou spécifiques au thème) | Pour les mises à jour dynamiques des prix lors du paiement. |
| | Modèle d'e-mail | Par défaut | Modèle d'e-mail pour les communications par virement bancaire. |
| | **Règles de visibilité** | Nom descriptif |
| | Active | OUI | Active/désactive une règle spécifique. |
| | Position (priorité) | 1, 2, 3… | Ordre d'évaluation des règles (inférieur = priorité plus élevée). |
| | Produits | Vide (ou produits spécifiques) | La remise s'applique uniquement si ces produits sont dans le panier. |
| | Catégories | Vide (ou catégories spécifiques) | La remise s'applique uniquement si des produits de ces catégories sont dans le panier. |

### 2.2 Écran du contrôleur Back-Office : AdminBankwiredisSearchController

- **Nom de l'écran et emplacement du menu :** Ce contrôleur est généralement utilisé pour gérer des entités spécifiques liées au module, telles que les clients mis sur liste noire ou des règles de remise spécifiques, souvent accessibles via un sous-onglet sous la configuration principale du module ou un élément de menu dédié. Dans ce module, il est probablement utilisé pour gérer les règles de visibilité ou les clients mis sur liste noire.
  - **Emplacement du menu :** Probablement accessible via un onglet ou un lien dans la page de configuration principale du module « Virement bancaire avec remise », ou potentiellement sous **Vendre > Commandes > Liste noire Virement bancaire avec remise** (exemple, l'emplacement réel peut varier en fonction de la version de PrestaShop et de la conception du module).
- **Actions et paramètres disponibles :** Cet écran fournit une vue de gestion basée sur une grille.
  - **Tableau de liste :** Affiche une liste d'éléments (par exemple, clients mis sur liste noire, règles de remise). Chaque ligne affiche généralement des détails pertinents tels que l'ID client, l'e-mail du client, la raison de la mise sur liste noire, le nom de la règle, le statut actif, etc.
  - **Boutons Ajouter/Modifier :** Permet d'ajouter manuellement de nouvelles entrées (par exemple, mettre manuellement un client sur liste noire) ou de modifier celles existantes.
  - **Actions en masse :** Options pour effectuer des actions sur plusieurs éléments sélectionnés (par exemple, supprimer plusieurs clients mis sur liste noire).
  - **Recherche/Filtre :** Outils pour trouver des entrées spécifiques dans la liste.
- **Effet des modifications :**
  - **Ajout/Modification d'entrées de liste noire :** Impacte directement les clients qui sont empêchés d'utiliser la méthode de paiement par virement bancaire.
  - **Ajout/Modification de règles de remise :** Modifie les conditions dans lesquelles les remises sont appliquées, affectant les prix et les incitations pour les clients.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Examinez régulièrement la liste des clients mis sur liste noire pour vous assurer qu'elle est à jour.
  2. Si vous devez mettre manuellement un client sur liste noire (par exemple, après une communication directe), utilisez la fonction « Ajouter » ici.
  3. Si vous devez ajuster ou créer de nouvelles règles de remise, c'est ici que vous les géreriez, en vous assurant qu'elles correspondent à vos promotions actuelles.

### 2.3 Écran du contrôleur Back-Office : index.php (Contrôleur Admin)

- **Nom de l'écran et emplacement du menu :** Le fichier `index.php` dans un répertoire de contrôleur admin sert souvent de placeholder ou de redirection, ou dans certains cas, il peut être le point d'entrée pour un tableau de bord ou une simple liste. Compte tenu des fonctionnalités du module, il pourrait s'agir d'un tableau de bord pour les statistiques de virement bancaire ou d'une simple liste des commandes par virement bancaire en attente.
  - **Emplacement du menu :** Potentiellement un sous-onglet sous la configuration principale du module, ou un élément de menu dédié comme **Vendre > Commandes > Tableau de bord Virement bancaire avec remise**.
- **Actions et paramètres disponibles :** Cet écran présente probablement une grille ou un tableau de bord.
  - **Vue Grille / Gestion :** Pourrait afficher une liste des commandes récentes par virement bancaire, leur statut, les rappels de paiement envoyés ou le statut d'annulation.
  - **Analyses/Statistiques :** Pourrait afficher des graphiques ou des résumés liés aux paiements par virement bancaire, tels que les taux de conversion, la remise moyenne appliquée ou le nombre de commandes impayées.
- **Effet des modifications :** Cet écran est généralement destiné à la surveillance et au reporting, plutôt qu'à des modifications directes de la configuration. Toute action entreprise ici (par exemple, marquer manuellement une commande comme payée) mettrait à jour le statut de la commande dans PrestaShop.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Vérifiez périodiquement ce tableau de bord pour surveiller les performances de votre méthode de paiement par virement bancaire.
  2. Examinez les commandes par virement bancaire en attente pour vous assurer qu'elles sont traitées ou rappelées/annulées comme prévu.
  3. Utilisez toutes les statistiques disponibles pour évaluer l'efficacité de vos remises par virement bancaire et de votre système de rappel.

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : L'option de paiement par virement bancaire n'apparaît pas sur ma page de paiement.**

- **R :** Tout d'abord, vérifiez si « Activer le paiement par virement bancaire » est défini sur OUI dans la configuration du module.
- **R :** Ensuite, vérifiez vos paramètres « Devises », « Zones », « Pays » et « Groupes de clients ». Si le contexte du client (devise, adresse de livraison ou groupe) ne correspond pas à vos sélections, la méthode de paiement n'apparaîtra pas.
- **R :** Si vous avez des règles de visibilité spécifiques, assurez-vous que le panier du client remplit toutes les conditions (valeur min/max du panier, produits/catégories spécifiques).
- **R :** Videz votre cache PrestaShop (Paramètres avancés > Performances > Vider le cache).

**Q2 : La remise n'est pas appliquée ou affichée correctement sur la page de paiement.**

- **R :** Vérifiez à nouveau vos paramètres « Type de remise » et « Valeur de la remise ».
- **R :** Examinez les paramètres « Valeur minimale du panier » ou « Valeur maximale du panier » – le total du panier doit se situer dans ces fourchettes.
- **R :** Si vous utilisez un thème personnalisé, le module pourrait ne pas être en mesure de trouver les sélecteurs CSS corrects pour mettre à jour les prix dynamiquement. Allez dans la section « Paramètres avancés » et assurez-vous que les « Sélecteurs CSS pour les mises à jour dynamiques » correspondent aux sélecteurs réels de votre thème pour le total du panier, le sous-total et les frais de port. Vous pourriez avoir besoin d'un webmaster pour inspecter le code de votre thème.
- **R :** Videz votre cache PrestaShop.

**Q3 : Les rappels ou annulations automatiques ne fonctionnent pas.**

- **R :** Il s'agit presque toujours d'un problème de tâche cron. Vous devez configurer une tâche cron sur votre serveur pour exécuter périodiquement les tâches du module.
- **R :** Dans les « Paramètres avancés » du module, copiez le « Jeton de tâche Cron » et l'URL cron complète.
- **R :** Accédez à votre panneau de contrôle d'hébergement (cPanel, Plesk, etc.) et trouvez la section « Tâches Cron ».
- **R :** Ajoutez une nouvelle tâche cron qui exécute l'URL fournie toutes les quelques heures (par exemple, `wget -O /dev/null "https://votreboutique.com/module/bankwiredis/cron?token=VOTRE_JETON_ICI"`).
- **R :** Assurez-vous que « Envoyer des rappels pour les commandes impayées » et « Annulation automatique des commandes impayées » sont activés, et que les jours sont correctement définis.

**Q4 : Comment traduire les textes du module dans d'autres langues ?**

- **R :** Dans votre Back Office PrestaShop, allez dans **International > Traductions**.
- **R :** Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez « Virement bancaire avec remise » dans la liste déroulante des modules.
- **R :** Vous pouvez alors modifier toutes les chaînes traduisibles du module. N'oubliez pas d'enregistrer vos modifications.

**Q5 : Un client a été mis sur liste noire, mais je souhaite lui permettre d'utiliser à nouveau le virement bancaire.**

- **R :** Naviguez vers l'écran d'administration dédié du module (probablement sous **Vendre > Commandes > Liste noire Virement bancaire avec remise** ou similaire, ou un onglet dans la configuration du module).
- **R :** Trouvez le client dans la liste et supprimez son entrée de liste noire ou modifiez-la pour désactiver la liste noire pour lui.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Virement bancaire avec remise » (`bankwiredis`) étend la fonctionnalité de paiement de PrestaShop, en adhérant au modèle MVC. Il s'intègre au processus de paiement via les hooks `PaymentOptions`, gère les états de commande et implémente des tâches automatisées (rappels, annulations, mise sur liste noire) via une tâche cron. La logique de remise est appliquée dynamiquement lors du paiement et persiste avec la commande. Des contrôleurs d'administration personnalisés fournissent des interfaces de gestion pour les règles de remise et les clients mis sur liste noire.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `controllers/front/cron.php`
  - **Nom de la classe :** `BankwiredisCronModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** Ce contrôleur gère l'exécution des tâches planifiées. Il est conçu pour être appelé par une tâche cron côté serveur à l'aide d'un jeton sécurisé. Il traite les rappels de commandes impayées, les annulations automatiques et la mise sur liste noire des clients en fonction de la configuration du module. Il ne rend aucun contenu front-office directement mais effectue des opérations en arrière-plan.
- `controllers/front/index.php`
  - **Nom de la classe :** `BankwiredisIndexModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** Souvent un placeholder ou un point d'entrée par défaut. Dans ce module, il pourrait gérer les redirections ou servir de fallback si d'autres contrôleurs frontaux spécifiques ne sont pas trouvés. Il n'a généralement pas de fonction directement visible par l'utilisateur.
- `controllers/front/payment.php`
  - **Nom de la classe :** `BankwiredisPaymentModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** Ce contrôleur est responsable de l'affichage des détails et des instructions de paiement par virement bancaire au client *après* qu'il a sélectionné le virement bancaire comme méthode de paiement mais *avant* que la commande ne soit entièrement validée. Il prépare les données (détails bancaires, montant final avec remise) pour le template `payment.tpl` ou `validation.tpl`.
- `controllers/front/validation.php`
  - **Nom de la classe :** `BankwiredisValidationModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** C'est le contrôleur crucial qui traite la validation finale d'une commande par virement bancaire. Après que le client a confirmé son choix, ce contrôleur crée la commande dans PrestaShop, définit son statut initial (par exemple, « En attente de paiement par virement bancaire »), applique la remise calculée et redirige le client vers la page de confirmation de commande.

#### Contrôleurs d'administration Back-Office

- `controllers/admin/AdminBankwiredisSearchController.php`
  - **Nom de la classe :** `AdminBankwiredisSearchController` (étend `ModuleAdminController`)
  - **Nom de l'onglet :** Probablement un sous-onglet sous la configuration principale du module ou une entrée de menu dédiée.
  - **Entité gérée :** Ce contrôleur gère les entités personnalisées du module, en particulier les règles de visibilité des remises et potentiellement les clients mis sur liste noire. Il fournit une interface standard PrestaShop `HelperList` ou `HelperForm` pour visualiser, ajouter, modifier et supprimer ces enregistrements.
- `controllers/admin/index.php`
  - **Nom de la classe :** `AdminBankwiredisIndexController` (étend `ModuleAdminController`)
  - **Nom de l'onglet :** Similaire à `AdminBankwiredisSearchController`, il s'agirait d'une page d'administration dédiée.
  - **Entité gérée :** Compte tenu des fonctionnalités du module, ce contrôleur sert probablement de tableau de bord ou d'interface de gestion pour les données principales du module, telles qu'une liste des commandes par virement bancaire en attente, des statistiques ou une vue simplifiée des clients mis sur liste noire.

### 4.3 Classes et modèles de base (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que les données du module (comme les règles de remise, les clients mis sur liste noire) pourraient être stockées directement dans `ps_configuration` ou gérées via des instances génériques `ObjectModel` définies dans le fichier principal `bankwiredis.php` ou directement dans les contrôleurs d'administration.

- **Note :** Si des tables personnalisées sont utilisées, leurs définitions `ObjectModel` résideraient généralement ici. Le module utilise probablement `Configuration::get()` et `Configuration::updateValue()` pour la plupart des paramètres et potentiellement `Db::getInstance()` pour les interactions directes avec la base de données pour des structures de données plus complexes comme les règles de remise ou les clients mis sur liste noire, si elles ne sont pas mappées à un `ObjectModel` personnalisé.

### 4.4 Actifs JavaScript (`views/js/`)

- `bankwiredis/lib/searchTool/views/js/autocomplete.js`
  - **Portée :** Back-office.
  - **Fonctionnalité :** Fournit une fonctionnalité d'autocomplétion, probablement utilisée dans les formulaires d'administration (par exemple, `AdminBankwiredisSearchController`) pour sélectionner des produits ou des catégories lors de la définition des règles de visibilité des remises. Il écoute la saisie de l'utilisateur dans des champs de texte spécifiques et effectue des requêtes AJAX pour suggérer des éléments correspondants.
- `bankwiredis/views/js/adminBankwiredisAccounts.js`
  - **Portée :** Back-office.
  - **Fonctionnalité :** Gère probablement le comportement dynamique sur la page de configuration du module lié aux détails du compte bancaire. Cela pourrait inclure l'affichage/masquage de champs en fonction des options sélectionnées, la validation des entrées ou les appels AJAX pour enregistrer les informations de compte.
- `bankwiredis/views/js/adminBankwiredisDashboard.js`
  - **Portée :** Back-office.
  - **Fonctionnalité :** Gère les éléments interactifs et la visualisation des données sur le tableau de bord d'administration du module (par exemple, `AdminBankwiredisIndexController`). Cela pourrait impliquer la récupération de données via AJAX pour remplir des graphiques, des tableaux ou mettre à jour des statistiques, et la gestion des interactions de l'utilisateur avec les widgets du tableau de bord.
- `bankwiredis/views/js/bankwiredis-checkout.js`
  - **Portée :** Front-office.
  - **Fonctionnalité :** C'est un script essentiel pour l'expérience client. Il écoute la sélection de l'option de paiement par virement bancaire sur la page de paiement. Lors de la sélection, il effectue un appel AJAX au contrôleur frontal du module pour calculer et afficher la remise dynamique, mettant à jour le total de la commande, le sous-total et les éléments de coût d'expédition sur la page. Il utilise les sélecteurs CSS configurés dans le back office (`BDIS_CSS_PAY_INPUT`, `BDIS_CSS_CART_TOTAL`, etc.) pour cibler les éléments DOM corrects à mettre à jour.

### 4.5 Feuilles de style CSS (`views/css/`)

- `bankwiredis/lib/searchTool/views/css/autocomplete.css`
  - **Portée :** Back-office.
  - **Fonctionnalité :** Style les suggestions de la liste déroulante d'autocomplétion et les champs de saisie utilisés dans les outils de recherche d'administration.
- `bankwiredis/views/css/admin_bankwiredis.css`
  - **Portée :** Back-office.
  - **Fonctionnalité :** Fournit un style spécifique pour la page de configuration du module et les vues du contrôleur d'administration personnalisé, garantissant une interface cohérente et conviviale dans le back office de PrestaShop.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

- `bankwiredis/views/templates/hook/infos.tpl`
  - **Hook :** Probablement `displayPaymentInfo` ou similaire.
  - **Sortie :** Affiche des informations générales ou un résumé sur la méthode de paiement par virement bancaire, potentiellement y compris l'offre de remise, sur la page de sélection du paiement ou dans le résumé de la commande.
- `bankwiredis/views/templates/hook/payment.tpl`
  - **Hook :** `displayPaymentOptions` (PrestaShop 1.7+), `displayPayment` (PrestaShop 1.6).
  - **Sortie :** Rend l'option de paiement par virement bancaire réelle sur la page de paiement, y compris son titre, sa description et le montant de la remise calculé dynamiquement. C'est là que le client sélectionne « Payer par virement bancaire ».
- `bankwiredis/views/templates/hook/payment_return.tpl`
  - **Hook :** `displayPaymentReturn`.
  - **Sortie :** Affiche les détails du compte bancaire et les instructions de paiement sur la page de confirmation de commande après qu'un client a passé avec succès une commande par virement bancaire.
- `bankwiredis/views/templates/hook/payment_return_pdf_invoice.tpl`
  - **Hook :** `displayPDFInvoice` (ou similaire pour la génération de PDF).
  - **Sortie :** Fournit le contenu nécessaire (détails bancaires, résumé de la remise) à inclure dans la facture PDF générée pour les commandes par virement bancaire.

#### Templates d'administration (`views/templates/admin/`)

- `bankwiredis/lib/searchTool/views/scripts.tpl`
  - **Sortie :** Inclut probablement les actifs JavaScript et CSS pour l'outil de recherche d'autocomplétion dans les formulaires d'administration.
- `bankwiredis/views/templates/admin/scopeSelector.tpl`
  - **Sortie :** Un template pour sélectionner la portée (par exemple, boutique, groupe, toutes les boutiques) dans un environnement multi-boutiques, souvent utilisé dans les formulaires de configuration.
- `bankwiredis/views/templates/admin/selectedProducts.tpl`
  - **Sortie :** Affiche une liste de produits qui ont été sélectionnés pour une règle de remise spécifique (par exemple, dans `AdminBankwiredisSearchController` lors de la configuration d'une règle basée sur les produits).

#### Templates Front-office (`views/templates/front/`)

- `bankwiredis/views/templates/front/validation.tpl`
  - **Sortie :** Ce template est rendu par `BankwiredisPaymentModuleFrontController` ou `BankwiredisValidationModuleFrontController` pour afficher les détails bancaires finaux et les instructions *avant* que la commande ne soit entièrement confirmée ou immédiatement après, fournissant une page dédiée aux instructions de paiement.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

Le module utilise principalement la table `ps_configuration` de PrestaShop pour la plupart de ses paramètres (par exemple, `BANK_WIRE_DIS_OWNER_`, `BDIS_CRON_TOKEN`, `BANK_WIRE_DIS_CHARGEP`).
Pour des données plus complexes comme les règles de visibilité des remises et les clients mis sur liste noire, le module crée probablement des tables personnalisées lors de sa méthode `install()`. Basé sur les options de configuration, ces tables seraient généralement :

- `ps_bankwiredis_rules` : Stocke la définition de chaque règle de remise (nom de la règle, statut actif, type de remise, valeur, panier min/max, devises, zones, pays, groupes de clients, produits, catégories).
- `ps_bankwiredis_blacklist` : Stocke les enregistrements des clients mis sur liste noire (ID client, e-mail, raison, date de mise sur liste noire).
- `ps_bankwiredis_reminders` : Stocke un journal des e-mails de rappel envoyés pour chaque commande afin de suivre le `Max reminders per order`.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page front-office. | Utilisé pour charger les actifs CSS et JavaScript front-office (`bankwiredis-checkout.js`) pour l'affichage dynamique des remises. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration charge ses actifs multimédias. | Utilisé pour charger les actifs CSS et JavaScript back-office (`admin_bankwiredis.css`, `adminBankwiredisAccounts.js`, `autocomplete.js`) pour la configuration du module et les pages d'administration. |
| `displayPaymentOptions` | Sur la page de paiement, lorsque les options de paiement sont listées. | Rend l'option de paiement par virement bancaire, y compris la remise calculée, à l'aide de `payment.tpl`. |
| `displayPaymentReturn` | Sur la page de confirmation de commande après une commande réussie. | Affiche les détails du compte bancaire et les instructions de paiement au client, à l'aide de `payment_return.tpl`. |
| `displayPDFInvoice` | Lorsqu'une facture PDF est générée. | Injecte les détails du compte bancaire et les informations de remise dans la facture PDF, à l'aide de `payment_return_pdf_invoice.tpl`. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | Utilisé pour capturer les détails de la commande, appliquer la remise finale et potentiellement enregistrer la commande pour le traitement des rappels/annulations. |
| `displayPaymentInfo` | (Implicite) Souvent utilisé pour afficher des informations supplémentaires sur la sélection du paiement. | Rend `infos.tpl` avec des informations générales sur le virement bancaire. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel des développeurs, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Assurez-vous d'utiliser la dernière version compatible du module pour votre boutique PrestaShop.
