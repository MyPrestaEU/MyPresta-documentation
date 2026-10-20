---
title: "Virement bancaire avec récapitulatif de commande - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Virement bancaire avec récapitulatif de commande par MyPresta.eu."
sidebar:
  label: "Virement bancaire avec récapitulatif de commande - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Bank wire with order summary sur MyPresta.eu](https://mypresta.eu/modules/payment-process/bank-wire-with-order-summary.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/payment/bank-wire-with-order-summary/)
>
> ---


# Virement bancaire avec récapitulatif de commande

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises par PrestaShop lui-même et sont habituellement disponibles sur la plupart des environnements d'hébergement. Aucune extension inhabituelle spécifique n'est nécessaire pour ce module.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal où vous définissez les détails de votre compte bancaire et le comportement de la méthode de paiement par virement bancaire dans votre boutique.

#### **Paramètres du compte de virement bancaire**

Cette section vous permet de définir plusieurs profils de compte bancaire. Chaque profil peut avoir ses propres détails et peut être activé ou désactivé indépendamment. C'est utile si vous avez différents comptes bancaires pour différentes devises, pays ou même différentes marques.

- **Nom du profil :**

  - **Ce que fait ce paramètre :** C'est un nom interne pour votre profil de compte bancaire, vous aidant à l'identifier dans le back office. Il n'est pas visible pour les clients.
  - **Effet de la modification de ce paramètre :** La modification de ce paramètre n'affecte que la façon dont vous voyez le profil dans le panneau d'administration.
  - **Valeur recommandée :** Un nom descriptif, par exemple, « Compte Euro Principal », « Compte USD pour les commandes US ».
  - **Scénario / exemple de marchand :** Si vous avez un compte bancaire en Allemagne pour les paiements en EUR et un autre aux États-Unis pour les paiements en USD, vous créeriez deux profils, en les nommant en conséquence.
- **Actif :**

  - **Ce que fait ce paramètre :** Contrôle si ce profil de compte bancaire spécifique est disponible comme option de paiement pour les clients.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (Oui) :* Ce profil de compte bancaire sera proposé aux clients s'il répond à tous les autres critères d'éligibilité (devise, pays, etc.).
    - *Lorsqu'désactivé (Non) :* Ce profil ne sera pas affiché comme option de paiement, quelles que soient les autres configurations.
  - **Valeur recommandée :** « Oui » pour les comptes actifs, « Non » pour les comptes inactifs ou temporaires.
  - **Scénario / exemple de marchand :** Vous pourriez désactiver un profil si un compte bancaire est temporairement indisponible ou si vous supprimez progressivement une devise particulière.
- **Priorité :**

  - **Ce que fait ce paramètre :** Si plusieurs profils de virement bancaire sont actifs et éligibles pour la commande d'un client, ce nombre détermine lequel est affiché en premier ou préféré. Les nombres inférieurs signifient une priorité plus élevée.
  - **Effet de la modification de ce paramètre :** Influence l'ordre dans lequel les options de virement bancaire éligibles sont présentées au client.
  - **Valeur recommandée :** Utilisez des nombres séquentiels (par exemple, 1, 2, 3) pour classer vos préférences.
  - **Scénario / exemple de marchand :** Si vous préférez que les clients utilisent votre compte EUR principal plutôt qu'un compte secondaire, donnez au compte principal un numéro de priorité inférieur (par exemple, 1) à celui du compte secondaire (par exemple, 2).
- **Devise :**

  - **Ce que fait ce paramètre :** Spécifie la devise dans laquelle ce profil de compte bancaire est configuré pour recevoir les paiements.
  - **Effet de la modification de ce paramètre :** Ce profil ne sera proposé qu'aux clients dont le total de la commande est dans la devise sélectionnée.
  - **Valeur recommandée :** Sélectionnez la devise principale pour ce compte bancaire.
  - **Scénario / exemple de marchand :** Si vous avez un compte bancaire qui n'accepte que les EUR, sélectionnez « Euro ». Si un client passe une commande en USD, ce profil ne sera pas affiché.
- **Pays éligibles :**

  - **Ce que fait ce paramètre :** Détermine pour quels pays ce profil de compte bancaire est disponible. Vous pouvez sélectionner plusieurs pays.
  - **Effet de la modification de ce paramètre :** Ce profil ne sera proposé qu'aux clients dont l'adresse de facturation se trouve dans l'un des pays sélectionnés.
  - **Valeur recommandée :** Sélectionnez tous les pays à partir desquels vous êtes prêt à accepter des virements bancaires vers ce compte spécifique.
  - **Scénario / exemple de marchand :** Si votre compte bancaire allemand est uniquement destiné aux clients en Allemagne et en Autriche, sélectionnez « Allemagne » et « Autriche ».
- **Zones éligibles :**

  - **Ce que fait ce paramètre :** Détermine pour quelles zones géographiques ce profil de compte bancaire est disponible. Vous pouvez sélectionner plusieurs zones.
  - **Effet de la modification de ce paramètre :** Similaire aux pays, ce profil ne sera proposé qu'aux clients dont l'adresse de facturation se trouve dans l'une des zones sélectionnées.
  - **Valeur recommandée :** Sélectionnez les zones pertinentes pour ce compte bancaire.
  - **Scénario / exemple de marchand :** Si vous avez un compte bancaire spécifiquement pour les clients européens, vous pourriez sélectionner la zone « Europe ».
- **Groupes de clients éligibles :**

  - **Ce que fait ce paramètre :** Restreint cette option de paiement à des groupes de clients spécifiques (par exemple, « Visiteurs », « Invités », « Clients », « Grossistes »).
  - **Effet de la modification de ce paramètre :** Seuls les clients appartenant aux groupes sélectionnés verront cette option de virement bancaire.
  - **Valeur recommandée :** Généralement « Clients » et « Invités », mais peut être personnalisé pour le B2B.
  - **Scénario / exemple de marchand :** Vous ne souhaitez peut-être proposer le virement bancaire qu'à votre groupe de « Grossistes » pour les commandes B2B importantes, et non aux clients de détail réguliers.
- **Titulaire du compte :**

  - **Ce que fait ce paramètre :** Le nom complet du titulaire du compte (nom de votre entreprise ou nom personnel) tel qu'il apparaît sur le compte bancaire.
  - **Effet de la modification de ce paramètre :** Cette information est affichée au client sur la page de confirmation de paiement, afin qu'il sache à qui transférer l'argent.
  - **Valeur recommandée :** Votre nom légal exact d'entreprise ou votre nom personnel.
  - **Scénario / exemple de marchand :** « MyPresta.eu Sp. z o.o. »
- **IBAN :**

  - **Ce que fait ce paramètre :** Votre numéro de compte bancaire international (International Bank Account Number). C'est un identifiant de compte bancaire international standardisé.
  - **Effet de la modification de ce paramètre :** C'est une information cruciale affichée au client pour effectuer le virement bancaire.
  - **Valeur recommandée :** Votre IBAN complet et correct.
  - **Scénario / exemple de marchand :** « DE89370400440532013000 »
- **BIC / SWIFT :**

  - **Ce que fait ce paramètre :** Votre code d'identification bancaire (BIC) ou code SWIFT. Cela identifie votre banque au niveau mondial.
  - **Effet de la modification de ce paramètre :** C'est une information essentielle affichée au client pour effectuer des virements bancaires internationaux.
  - **Valeur recommandée :** Votre code BIC/SWIFT complet et correct.
  - **Scénario / exemple de marchand :** « COBADEFFXXX »
- **Numéro de compte / détails :**

  - **Ce que fait ce paramètre :** Votre numéro de compte bancaire traditionnel ou d'autres détails spécifiques requis par votre banque ou votre pays, si l'IBAN/BIC ne sont pas suffisants ou applicables.
  - **Effet de la modification de ce paramètre :** Cette information est affichée au client.
  - **Valeur recommandée :** Votre numéro de compte si l'IBAN n'est pas utilisé, ou tout autre détail spécifique. Laissez vide si l'IBAN/BIC sont suffisants.
  - **Scénario / exemple de marchand :** Dans certains pays, un numéro de compte local pourrait toujours être préféré en plus ou à la place de l'IBAN.
- **Adresse de la banque / du titulaire :**

  - **Ce que fait ce paramètre :** L'adresse de votre banque ou l'adresse enregistrée du titulaire du compte.
  - **Effet de la modification de ce paramètre :** Cette information est affichée au client, parfois requise pour les virements bancaires.
  - **Valeur recommandée :** L'adresse complète de votre agence bancaire ou l'adresse enregistrée de votre entreprise.
  - **Scénario / exemple de marchand :** « Banque de l'Exemple, Rue Principale 123, 10001 Ville, Pays »
- **Instructions supplémentaires :**

  - **Ce que fait ce paramètre :** Un champ de texte où vous pouvez fournir des notes supplémentaires au client concernant le virement bancaire (par exemple, « Veuillez inclure votre numéro de référence de commande dans la description du virement », « Les paiements prennent généralement 1 à 3 jours ouvrables pour être compensés »).
  - **Effet de la modification de ce paramètre :** Ce texte sera affiché au client sur la page de confirmation de paiement.
  - **Valeur recommandée :** Des instructions claires et concises pour aider les clients à effectuer le virement correctement.
  - **Scénario / exemple de marchand :** « Important : Veuillez utiliser votre ID de commande # [ORDER\_ID] comme référence de paiement pour assurer un traitement rapide. »

#### **Restrictions sur le total du panier**

Ces paramètres vous permettent de contrôler les valeurs minimales et maximales de commande pour lesquelles l'option de paiement par virement bancaire est disponible.

- **Total minimum du panier :**

  - **Ce que fait ce paramètre :** Active ou désactive la restriction du total minimum du panier pour cette méthode de paiement.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Le champ « Valeur minimale du total du panier » devient actif, et le virement bancaire ne sera disponible que pour les commandes supérieures à cette valeur.
    - *Lorsqu'désactivé :* Aucune restriction de total minimum du panier n'est appliquée.
  - **Valeur recommandée :** « Activé » si vous souhaitez définir un minimum, « Désactivé » sinon.
  - **Scénario / exemple de marchand :** Vous pourriez l'activer si les virements bancaires sont plus rentables pour les commandes importantes, ou pour décourager les virements bancaires pour de très petits achats.
- **Valeur minimale du total du panier :**

  - **Ce que fait ce paramètre :** La valeur monétaire réelle que le panier du client doit dépasser pour que l'option de virement bancaire apparaisse.
  - **Effet de la modification de ce paramètre :** Si le total du panier du client est inférieur à cette valeur, l'option de virement bancaire ne sera pas affichée.
  - **Valeur recommandée :** Un minimum raisonnable, par exemple, « 50.00 ».
  - **Scénario / exemple de marchand :** Définissez à « 50.00 » si vous ne souhaitez proposer le virement bancaire que pour les commandes de 50 € ou plus.
- **Total maximum du panier :**

  - **Ce que fait ce paramètre :** Active ou désactive la restriction du total maximum du panier pour cette méthode de paiement.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Le champ « Valeur maximale du total du panier » devient actif, et le virement bancaire ne sera disponible que pour les commandes inférieures à cette valeur.
    - *Lorsqu'désactivé :* Aucune restriction de total maximum du panier n'est appliquée.
  - **Valeur recommandée :** « Activé » si vous souhaitez définir un maximum, « Désactivé » sinon.
  - **Scénario / exemple de marchand :** Vous pourriez l'activer si vous préférez d'autres méthodes de paiement (comme la négociation directe ou la facturation personnalisée) pour les commandes extrêmement importantes.
- **Valeur maximale du total du panier :**

  - **Ce que fait ce paramètre :** La valeur monétaire réelle que le panier du client doit être inférieure pour que l'option de virement bancaire apparaisse.
  - **Effet de la modification de ce paramètre :** Si le total du panier du client est supérieur à cette valeur, l'option de virement bancaire ne sera pas affichée.
  - **Valeur recommandée :** Un maximum raisonnable, par exemple, « 5000.00 ».
  - **Scénario / exemple de marchand :** Définissez à « 5000.00 » si vous ne souhaitez pas accepter les virements bancaires pour les commandes dépassant 5000 €.

#### **Affichage du récapitulatif de commande**

Ces paramètres contrôlent les informations affichées au client sur la page de confirmation de paiement avant qu'il ne finalise sa commande. C'est crucial pour la conformité légale.

- **Récapitulatif de commande avant confirmation :**

  - **Ce que fait ce paramètre :** Contrôle si un récapitulatif détaillé de la commande est affiché au client sur la page de confirmation de paiement.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Un récapitulatif des produits, des prix et des totaux sera affiché.
    - *Lorsqu'désactivé :* Le récapitulatif détaillé ne sera pas affiché, ce qui pourrait avoir un impact sur la conformité légale dans certaines régions.
  - **Valeur recommandée :** « Activé » pour assurer la conformité légale et la clarté pour le client.
  - **Scénario / exemple de marchand :** Gardez toujours cette option activée pour offrir une transparence totale à vos clients avant qu'ils ne s'engagent dans l'achat.
- **Afficher le récapitulatif client avant confirmation :**

  - **Ce que fait ce paramètre :** Contrôle si le récapitulatif des adresses de facturation et de livraison du client est affiché sur la page de confirmation de paiement.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les détails de l'adresse du client seront affichés.
    - *Lorsqu'désactivé :* Les détails de l'adresse ne seront pas affichés.
  - **Valeur recommandée :** « Activé » pour une transparence totale.
  - **Scénario / exemple de marchand :** L'activation de cette option permet aux clients de vérifier une dernière fois leurs informations de livraison avant de passer la commande.

#### **Analyse avancée (interne)**

Ces paramètres sont généralement destinés à l'analyse et au reporting interne du module, n'ayant pas d'impact direct sur l'expérience client en front-office.

- **BANKWIREPRO\_ANALYTICS\_DEFAULT\_CHART, BANKWIREPRO\_ANALYTICS\_PERIOD, BANKWIREPRO\_ANALYTICS\_CHART\_WEEKS, BANKWIREPRO\_ANALYTICS\_CHART\_MONTHS, BANKWIREPRO\_ANALYTICS\_CHART\_YEARS :**
  - **Ce que font ces paramètres :** Ce sont des valeurs de configuration internes liées à la façon dont le module pourrait suivre ou afficher les statistiques de paiement dans le back office de PrestaShop (si une telle fonctionnalité est implémentée). Elles définissent les types de graphiques par défaut, les périodes de reporting et les délais pour l'analyse.
  - **Effet de la modification de ces paramètres :** Ceux-ci n'affectent pas le processus de paiement côté client. Ils pourraient influencer la façon dont les données sont présentées dans un tableau de bord d'analyse interne, si disponible.
  - **Valeur recommandée :** Laissez par défaut, sauf instruction spécifique du support.
  - **Scénario / exemple de marchand :** Non directement applicable à la prise de décision du marchand pour le traitement des paiements.

#### **Paramètres de langue (interne)**

- **PS\_LANG\_DEFAULT, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG :**

  - **Ce que font ces paramètres :** Ce sont des variables de configuration PrestaShop standard qui déterminent la langue par défaut de votre boutique et si les employés peuvent changer la langue des formulaires du back office. Elles sont affichées ici à titre de référence mais ne sont pas spécifiques à ce module.
  - **Effet de la modification de ces paramètres :** Les modifications de ceux-ci seraient effectuées dans les paramètres généraux de PrestaShop, pas ici. Elles influencent la langue par défaut des champs de texte dans le back office.
  - **Valeur recommandée :** La langue par défaut de votre boutique.
  - **Scénario / exemple de marchand :** Si la langue principale de votre boutique est l'anglais, `PS_LANG_DEFAULT` serait défini sur l'ID de la langue anglaise.
- **PS\_CURRENCY\_DEFAULT :**

  - **Ce que fait ce paramètre :** C'est la devise par défaut de votre boutique PrestaShop. Elle est affichée ici à titre de référence.
  - **Effet de la modification de ce paramètre :** C'est un paramètre global de PrestaShop. Le modifier affecterait tous les prix et affichages de devises dans votre boutique.
  - **Valeur recommandée :** La devise d'exploitation principale de votre boutique.
  - **Scénario / exemple de marchand :** Si votre boutique commerce principalement en Euros, cela serait défini sur « Euro ».

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Nom du profil | Nom descriptif | Identification interne du compte bancaire. |
| Configuration du module | Actif | Oui | Active/désactive ce profil de compte bancaire pour l'utilisation par le client. |
| Configuration du module | Priorité | 1 (ou séquentiel) | Ordonne l'affichage de plusieurs options de virement bancaire éligibles. |
| Configuration du module | Devise | Devise de votre boutique | Restreint le profil aux commandes dans cette devise. |
| Configuration du module | Pays éligibles | Tous les pays | Restreint le profil aux clients des pays sélectionnés. |
| Configuration du module | Zones éligibles | Toutes les zones | Restreint le profil aux clients des zones sélectionnées. |
| Configuration du module | Groupes de clients éligibles | Tous les groupes | Restreint le profil aux groupes de clients sélectionnés. |
| Configuration du module | Titulaire du compte | Votre entreprise/nom | Affiché au client pour le virement bancaire. |
| Configuration du module | IBAN | Votre IBAN | Affiché au client pour le virement bancaire. |
| Configuration du module | BIC / SWIFT | Votre BIC/SWIFT | Affiché au client pour le virement bancaire international. |
| Configuration du module | Numéro de compte / détails | (Facultatif) | Détails bancaires supplémentaires pour le client. |
| Configuration du module | Adresse de la banque / du titulaire | Adresse de votre banque/entreprise | Affiché au client pour le virement bancaire. |
| Configuration du module | Instructions supplémentaires | Instructions claires | Notes supplémentaires pour le client (par exemple, numéro de référence). |
| Configuration du module | Total minimum du panier | Désactivé | Active/désactive la restriction de la valeur minimale de commande. |
| Configuration du module | Valeur minimale du total du panier | 0.00 | Valeur minimale de commande pour que le virement bancaire soit disponible. |
| Configuration du module | Total maximum du panier | Désactivé | Active/désactive la restriction de la valeur maximale de commande. |
| Configuration du module | Valeur maximale du total du panier | 0.00 | Valeur maximale de commande pour que le virement bancaire soit disponible. |
| Configuration du module | Récapitulatif de commande avant confirmation | Activé | Affiche un récapitulatif détaillé des produits sur la page de confirmation. |
| Configuration du module | Afficher le récapitulatif client avant confirmation | Activé | Affiche un récapitulatif de l'adresse du client sur la page de confirmation. |
| Configuration du module | BANKWIREPRO\_ANALYTICS\_\* | Par défaut | Paramètres d'analyse interne (aucun impact sur le front-office). |
| Configuration du module | PS\_LANG\_DEFAULT | Par défaut de la boutique | Paramètre de langue par défaut de PrestaShop. |
| Configuration du module | PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG | Par défaut de la boutique | Paramètre de langue du formulaire employé de PrestaShop. |
| Configuration du module | PS\_CURRENCY\_DEFAULT | Par défaut de la boutique | Paramètre de devise par défaut de PrestaShop. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q1 : Pourquoi l'option Virement bancaire n'apparaît-elle pas pour mes clients ?**
R1 : Vérifiez les paramètres suivants dans la configuration du module :
\* L'interrupteur **« Actif »** pour le profil de compte bancaire : Assurez-vous qu'il est réglé sur « Oui ».
\* **« Devise »** : La devise de la commande du client correspond-elle à la devise du profil ?
\* **« Pays éligibles » / « Zones éligibles »** : Le pays/la zone de l'adresse de facturation du client est-il inclus ?
\* **« Groupes de clients éligibles »** : Le groupe du client est-il autorisé à utiliser cette méthode de paiement ?
\* **« Total minimum du panier » / « Total maximum du panier »** : La valeur du panier du client se situe-t-elle dans la plage autorisée ?
\* **Cache PrestaShop** : Parfois, vider le cache Smarty (Paramètres avancés > Performance > Vider le cache) peut résoudre les problèmes d'affichage.

**Q2 : Mes coordonnées bancaires sont incorrectes ou obsolètes. Comment les modifier ?**
R2 : Allez dans **Modules > Gestionnaire de modules**, trouvez « Virement bancaire avec récapitulatif de commande » et cliquez sur « Configurer ». Vous verrez vos profils de compte bancaire existants. Cliquez sur le bouton « Modifier » (icône en forme de crayon) à côté du profil que vous souhaitez mettre à jour, modifiez les champs « Titulaire du compte », « IBAN », « BIC / SWIFT », etc., puis enregistrez vos modifications.

**Q3 : Le récapitulatif de commande ne s'affiche pas sur la page de confirmation. Y a-t-il un problème ?**
R3 : Assurez-vous que les paramètres « Récapitulatif de commande avant confirmation » et « Afficher le récapitulatif client avant confirmation » sont tous deux réglés sur « Activé » dans la configuration du module. Si c'est le cas, et que vous avez vidé votre cache PrestaShop, il pourrait y avoir un conflit de thème. Testez avec le thème PrestaShop par défaut pour exclure cette possibilité.

**Q4 : Puis-je proposer différents comptes bancaires pour différents types de clients ou de produits ?**
R4 : Oui, absolument ! Ce module prend en charge plusieurs profils de compte bancaire. Vous pouvez créer des profils distincts et utiliser les paramètres « Groupes de clients éligibles », « Devise », « Pays éligibles » et « Total du panier » pour définir quand chaque compte bancaire spécifique est proposé. Par exemple, un compte pour les clients de détail en EUR, un autre pour les clients de gros en USD.

**Q5 : Après avoir mis à jour mon thème ou PrestaShop, la page de virement bancaire semble étrange. Que dois-je faire ?**
R5 : Cela indique souvent un conflit CSS ou un problème de surcharge de modèle.
1.  **Vider le cache :** Commencez toujours par vider votre cache PrestaShop (Paramètres avancés > Performance).
2.  **Vérifier les mises à jour du module :** Assurez-vous d'avoir la dernière version du module « Virement bancaire avec récapitulatif de commande » de MyPresta.eu, car les mises à jour incluent souvent des correctifs de compatibilité.
3.  **Conflit de thème :** Si le problème persiste, passez temporairement au thème PrestaShop par défaut (par exemple, « Classic ») pour voir si le problème disparaît. Si c'est le cas, votre thème personnalisé est probablement en conflit ou surcharge le style ou les modèles du module. Vous devrez peut-être consulter votre développeur de thème ou un webmaster pour ajuster le CSS ou les fichiers de modèle du thème.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module `bankwirepro` suit l'architecture standard des modules PrestaShop, tirant parti de `ModuleFrontController` pour les interactions front-office et de la classe `Module` principale pour la configuration. Il s'intègre dans le flux de paiement via des hooks de paiement (`displayPaymentOptions`, `paymentOptions`, `displayPaymentReturn`). La configuration est gérée via des entrées de la table `Configuration`, et les détails du compte bancaire sont stockés sous forme de tableaux sérialisés ou de clés `Configuration` individuelles, permettant plusieurs profils. La fonction principale du module est de présenter les coordonnées bancaires et un récapitulatif de commande au client avant et après la validation de la commande.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :
    -   `controllers/front/index.php`
        -   **Nom de la classe** : `BankwireproIndexModuleFrontController` (étend `ModuleFrontController`)
        -   **Responsabilité** : Ce contrôleur sert probablement de point d'entrée par défaut ou de solution de repli. Dans de nombreux modules, les contrôleurs `index.php` redirigent vers un contrôleur plus spécifique ou gèrent l'affichage de base du module si aucune autre action spécifique n'est demandée. Il pourrait gérer la configuration initiale ou la redirection vers la sélection du paiement.
    -   `controllers/front/payment.php`
        -   **Nom de la classe** : `BankwireproPaymentModuleFrontController` (étend `ModuleFrontController`)
        -   **Responsabilité** : Ce contrôleur est responsable du rendu de la page de sélection du paiement lorsque l'option de virement bancaire est choisie. Il collecte les détails du compte bancaire nécessaires en fonction du panier actuel, du client et de la devise, et les prépare pour l'affichage dans le template `payment.tpl`. Il agit comme le pont entre la sélection de l'option de paiement et l'étape de validation finale.
    -   `controllers/front/validation.php`
        -   **Nom de la classe** : `BankwireproValidationModuleFrontController` (étend `ModuleFrontController`)
        -   **Responsabilité** : C'est le contrôleur critique qui gère l'étape finale du processus de paiement par virement bancaire. Il valide la commande, crée la commande dans la base de données de PrestaShop, puis rend le template `validation.tpl`. Ce template affiche le récapitulatif complet de la commande, le récapitulatif de l'adresse du client et les détails du compte bancaire choisi, ainsi que des instructions supplémentaires, avant que le client ne soit redirigé vers la page standard `order-confirmation`. Il garantit que toutes les informations nécessaires sont présentées pour la conformité légale.

### 4.3 Classes et modèles principaux (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans `classes/`. La logique principale pour la gestion des profils de compte bancaire et de la configuration est probablement contenue dans le fichier `bankwirepro.php` principal, utilisant `Configuration::get()` et `Configuration::updateValue()` pour stocker les paramètres, potentiellement avec des tableaux sérialisés pour plusieurs profils de compte bancaire.

### 4.4 Actifs JavaScript (`views/js/`)

Le dossier du module n'indique aucun fichier JavaScript personnalisé. Cela suggère que la fonctionnalité front-office du module est principalement rendue côté serveur et repose sur le JavaScript standard de PrestaShop pour les interactions de base, ou que tout JS minimal est intégré dans les templates.

### 4.5 Feuilles de style CSS (`views/css/`)

Le dossier du module n'indique aucun fichier CSS personnalisé. Cela implique que le module s'appuie entièrement sur le style du thème par défaut de PrestaShop, ou que tout style minimal est intégré dans les templates. Les développeurs doivent être conscients que l'apparence du module sera largement dictée par le CSS du thème actif.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates d'administration (`views/templates/admin/`)** :

    -   `accountSelector.tpl` : Ce template est probablement utilisé dans la configuration du back-office du module pour afficher une liste des profils de compte bancaire configurés, permettant à l'administrateur de les sélectionner, de les modifier ou de les supprimer. Il rendrait généralement un tableau ou une liste avec les noms de profil, le statut et les boutons d'action.
-   **Templates Front-office (`views/templates/front/`)** :

    -   `validation.tpl` : C'est un template crucial rendu par `BankwireproValidationModuleFrontController`. Il affiche le récapitulatif complet de la commande (produits, totaux), le récapitulatif de l'adresse du client et les détails du compte bancaire sélectionné (titulaire du compte, IBAN, BIC/SWIFT, instructions) au client avant que la commande ne soit entièrement confirmée. Ce template est essentiel pour la conformité légale.
-   **Templates de hook (`views/templates/hook/`)** :

    -   `infos.tpl` : Ce template est probablement accroché à `displayPaymentReturn` ou à un hook similaire sur la page `order-confirmation`. Il réitère les instructions de paiement par virement bancaire et les coordonnées bancaires après que la commande a été passée avec succès, servant de rappel au client pour effectuer le virement.
    -   `payment.tpl` : Ce template est probablement utilisé pour le hook `displayPayment` (PrestaShop 1.6.x) ou `paymentOptions` (PrestaShop 1.7+). Il rend l'option de virement bancaire elle-même sur la page de sélection du paiement lors du processus de commande, la présentant comme une méthode de paiement disponible pour le client.
    -   `payment_return.tpl` : Similaire à `infos.tpl`, ce template est également probablement accroché à `displayPaymentReturn`. Il fournit le message de confirmation finale et les coordonnées bancaires sur la page de confirmation de commande, garantissant que le client dispose de toutes les informations pour procéder au virement bancaire.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module ne crée pas de tables SQL personnalisées. Tous les paramètres de configuration, y compris les profils de compte bancaire multiples, sont stockés dans la table `ps_configuration`.
    -   Clés de configuration utilisées :
        -   `BANK_WIRE_PRO_MINCART`, `BANK_WIRE_PRO_MINCART_V`, `BANK_WIRE_PRO_MAXCART`, `BANK_WIRE_PRO_MAXCART_V` : Pour les restrictions de total de panier.
        -   `BANK_WIRE_PRO_OWNER_`, `BANK_WIRE_PRO_DETAILS_`, `BANK_WIRE_PRO_ADDRESS_`, `BANK_WIRE_PRO_SWIFT_`, `BANK_WIRE_PRO_IBAN_`, `BANK_WIRE_PRO_MORE_` : Ce sont probablement des préfixes pour stocker les détails de *chaque* profil de compte bancaire, éventuellement avec un ID de langue ou un suffixe d'ID de profil (par exemple, `BANK_WIRE_PRO_OWNER_1_1` pour le profil 1, langue 1).
        -   `BANK_WIRE_PRO_OWNER_SUMMARY`, `BANK_WIRE_PRO_CSUMMARY`, `BANK_WIRE_PRO_ASUMMARY` : Pour contrôler l'affichage des récapitulatifs de commande et d'adresse.
        -   `BANKWIREPRO_ANALYTICS_*` : Paramètres d'analyse interne.
        -   Les clés PrestaShop standard comme `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `PS_CURRENCY_DEFAULT` sont lues mais non gérées par le module.
-   **Table des hooks enregistrés** :

| Nom du hook | Portée | Moment d'exécution | Objectif technique |
| --- | --- | --- | --- |
| `displayPayment` | Front-Office | Étape de sélection du paiement (PrestaShop 1.6.x) | Rend l'option de paiement par virement bancaire sur la page de commande. |
| `paymentOptions` | Front-Office | Étape de sélection du paiement (PrestaShop 1.7.x, 8.x, 9.x) | Fournit des objets `PaymentOption` pour le virement bancaire à la page de commande. |
| `displayPaymentReturn` | Front-Office | Page de confirmation de commande (`order-confirmation`) | Affiche les coordonnées bancaires et les instructions après la validation de la commande. |
| `displayPaymentOptions` | Front-Office | Étape de sélection du paiement (PrestaShop 1.7.x, 8.x, 9.x) | Hook alternatif ou supplémentaire pour le rendu des options de paiement. |
| `actionPaymentConfirmation` | Back-Office | Après qu'une commande est confirmée comme payée | (Implicite, courant pour les modules de paiement) Peut mettre à jour le statut de la commande ou effectuer des actions post-paiement. |
| `actionValidateOrder` | Back-Office | Après qu'une commande est validée | (Implicite, courant pour les modules de paiement) Utilisé pour définir le statut initial de la commande, enregistrer les détails de paiement. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour vous assurer que vous utilisez la version la plus sécurisée et compatible du module « Virement bancaire avec récapitulatif de commande », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité et l'intégration du module.
