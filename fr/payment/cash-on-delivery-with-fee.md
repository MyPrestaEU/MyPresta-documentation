---
title: "Paiement à la livraison avec frais - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Paiement à la livraison avec frais par MyPresta.eu."
sidebar:
  label: "Paiement à la livraison avec frais - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Cash on delivery with fee sur MyPresta.eu](https://mypresta.eu/modules/payment-process/cash-on-delivery-with-fee.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/payment/cash-on-delivery-with-fee/)
>
> ---


# Paiement à la livraison avec frais

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont généralement disponibles sur tout environnement d'hébergement moderne.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module « Paiement à la livraison avec frais », accessible directement après l'installation ou en naviguant vers **Modules > Gestionnaire de modules**, en recherchant « Paiement à la livraison avec frais » et en cliquant sur « Configurer ».

#### **Paramètres généraux**

- **Désactivé / Activé / Désactivé (Statut principal du module)**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver l'ensemble de la méthode de paiement Paiement à la livraison avec frais dans votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* L'option de paiement COD, ainsi que ses frais configurés, seront disponibles pour les clients lors du paiement.
    - *Lorsqu'désactivé :* L'option de paiement COD ne sera pas affichée aux clients, quelles que soient les autres configurations.
  - **Valeur recommandée :** `Activé` si vous avez l'intention de proposer le COD.
  - **Scénario / exemple de marchand :** Si vous testez le module ou souhaitez temporairement arrêter de proposer le COD, vous le réglerez sur `Désactivé`.
- **Valeur (Valeur des frais COD)**

  - **Ce que fait ce paramètre :** Ce champ détermine le montant de base ou le pourcentage des frais COD. L'interprétation exacte (montant fixe ou pourcentage) dépend du paramètre « Comment inclure les frais ? » ci-dessous.
  - **Effet de la modification de ce paramètre :** Modifie directement le coût ajouté aux commandes COD.
  - **Valeur recommandée :** Commencez par `0.00` et ajustez en fonction de vos frais de transporteur.
  - **Scénario / exemple de marchand :** Si votre transporteur facture 2,50 € pour le COD, vous pouvez saisir `2.50`. S'il facture 1 % de la commande, vous pouvez saisir `1`.
- **Comment inclure les frais ?**

  - **Ce que fait ce paramètre :** Définit la manière dont la « Valeur » (du paramètre précédent) est appliquée au total de la commande.
  - **Effet de la modification de ce paramètre :**
    - *Inclure aux frais de port :* Les frais COD sont ajoutés aux frais de port affichés au client. Cela peut simplifier l'affichage du paiement en combinant les frais.
    - *Inclure comme produit/service séparé :* Les frais COD apparaissent comme une ligne distincte dans le récapitulatif du panier et la facture, souvent étiquetés comme « Frais COD » ou similaire. Cela offre une transparence maximale.
  - **Valeur recommandée :** `Inclure comme produit/service séparé` pour plus de clarté et de conformité légale.
  - **Scénario / exemple de marchand :** Si vous souhaitez que les clients voient clairement les frais COD comme un article distinct, choisissez « Inclure comme produit/service séparé ». Si vous préférez un coût d'expédition plus propre et combiné, choisissez « Inclure aux frais de port ».
- **Statut de la commande après achat avec le module COD**

  - **Ce que fait ce paramètre :** Spécifie le statut initial d'une commande passée en utilisant la méthode de paiement COD.
  - **Effet de la modification de ce paramètre :** Détermine comment les commandes COD apparaissent dans votre Back Office immédiatement après leur placement.
  - **Valeur recommandée :** `Paiement accepté` (ou un statut similaire « en attente de paiement » que vous avez configuré). Cela vous permet de différencier les commandes COD qui sont confirmées mais pas encore physiquement payées.
  - **Scénario / exemple de marchand :** Vous pouvez définir ceci sur « En attente de paiement à la livraison » (si vous avez créé un tel statut) pour filtrer et gérer facilement les commandes COD en attente de paiement physique à la livraison.
- **Afficher un récapitulatif supplémentaire avant la confirmation**

  - **Ce que fait ce paramètre :** Contrôle si un bloc de récapitulatif supplémentaire est affiché à l'étape finale du paiement, juste avant que le client ne confirme sa commande.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Une ventilation détaillée incluant le total du panier, les frais d'expédition et les frais COD sera affichée.
    - *Lorsqu'désactivé :* Le récapitulatif PrestaShop standard sera utilisé, ce qui pourrait ne pas détailler explicitement les frais COD comme une ligne distincte.
  - **Valeur recommandée :** `Activé` pour une transparence maximale et une conformité légale.
  - **Scénario / exemple de marchand :** Pour s'assurer que les clients sont pleinement conscients de tous les frais avant de s'engager, en particulier les frais COD, activez cette option.
- **Récapitulatif du panier / Récapitulatif de l'adresse / Valeur minimale du total du panier (Sélecteurs CSS)**

  - **Ce que fait ce paramètre :** Ces champs vous permettent de spécifier des sélecteurs CSS pour divers éléments de votre page de paiement. Le module utilise ces sélecteurs pour injecter correctement les informations sur les frais COD dans le récapitulatif de paiement de votre thème.
  - **Effet de la modification de ce paramètre :** Si votre thème utilise des classes CSS non standard pour ces éléments, l'ajustement de ces sélecteurs garantit que les frais COD sont affichés correctement. Des valeurs incorrectes peuvent entraîner l'absence d'affichage des frais ou leur affichage au mauvais endroit.
  - **Valeur recommandée :** Laissez vide pour la détection automatique ou utilisez les valeurs par défaut fournies par le module. Ne modifiez que si l'affichage des frais COD est cassé dans votre thème personnalisé.
  - **Scénario / exemple de marchand :** Si vous avez installé un thème personnalisé et que les frais COD n'apparaissent pas dans le récapitulatif du panier, votre développeur web pourrait avoir besoin d'inspecter le HTML de votre thème et de mettre à jour ces sélecteurs pour correspondre à la structure de votre thème.

#### **Calcul des frais et conditions**

- **Désactivé / Activé / Désactivé (Condition de valeur maximale du panier)**

  - **Ce que fait ce paramètre :** Active ou désactive une condition selon laquelle la méthode de paiement COD n'est disponible que si le total du panier est *inférieur* à une certaine valeur maximale.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients dont le panier dépasse la valeur maximale spécifiée ne verront pas le COD comme option de paiement.
    - *Lorsqu'désactivé :* Aucune restriction de valeur maximale du panier ne s'applique au COD.
  - **Valeur recommandée :** `Désactivé` sauf si vous avez des raisons spécifiques de limiter les commandes COD de grande valeur.
  - **Scénario / exemple de marchand :** Si vous avez eu des problèmes avec des commandes COD frauduleuses ou non collectées de grande valeur, vous pouvez activer ceci et définir un `CODPRO_MOD_MAXCART_V` à 500 € pour atténuer les risques.
- **CODPRO\_MOD\_MAXCART\_V (Valeur maximale du panier)**

  - **Ce que fait ce paramètre :** La valeur monétaire spécifique pour la condition de total de panier maximal.
  - **Effet de la modification de ce paramètre :** Définit la limite supérieure d'éligibilité au COD.
  - **Valeur recommandée :** Définissez une valeur qui correspond à votre tolérance au risque pour les commandes COD.
  - **Scénario / exemple de marchand :** Si `Désactivé / Activé / Désactivé (Condition de valeur maximale du panier)` est activé, et que vous définissez ceci à `500.00`, les clients avec des commandes de plus de 500 € ne peuvent pas utiliser le COD.
- **Désactivé / Activé / Désactivé (Condition de valeur minimale du panier)**

  - **Ce que fait ce paramètre :** Active ou désactive une condition selon laquelle la méthode de paiement COD n'est disponible que si le total du panier est *supérieur* à une certaine valeur minimale.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients dont le panier est inférieur à la valeur minimale spécifiée ne verront pas le COD comme option de paiement.
    - *Lorsqu'désactivé :* Aucune restriction de valeur minimale du panier ne s'applique au COD.
  - **Valeur recommandée :** `Désactivé` sauf si vous avez des raisons spécifiques d'éviter les très petites commandes COD.
  - **Scénario / exemple de marchand :** Si les frais COD fixes rendent les très petites commandes non rentables, vous pouvez activer ceci et définir un `CODPRO_MOD_MINCART_V` à 10 €.
- **CODPRO\_MOD\_MINCART\_V (Valeur minimale du panier)**

  - **Ce que fait ce paramètre :** La valeur monétaire spécifique pour la condition de total de panier minimal.
  - **Effet de la modification de ce paramètre :** Définit la limite inférieure d'éligibilité au COD.
  - **Valeur recommandée :** Définissez une valeur qui rend le COD rentable pour vous.
  - **Scénario / exemple de marchand :** Si `Désactivé / Activé / Désactivé (Condition de valeur minimale du panier)` est activé, et que vous définissez ceci à `10.00`, les clients avec des commandes de moins de 10 € ne peuvent pas utiliser le COD.
- **CODPRO\_CHARGEP\_V (Valeur des frais en pourcentage)**

  - **Ce que fait ce paramètre :** Ce champ définit la valeur en pourcentage des frais COD.
  - **Effet de la modification de ce paramètre :** Si « Comment inclure les frais ? » est défini sur une option basée sur un pourcentage, cette valeur sera utilisée pour calculer les frais.
  - **Valeur recommandée :** `0.00` initialement, ajustez en fonction des frais en pourcentage de votre transporteur.
  - **Scénario / exemple de marchand :** Si votre transporteur facture 1,5 % de la valeur de la commande pour le COD, vous saisirez `1.5` ici.
- **CODPRO\_PERCENTAGE\_TYPE (Base de calcul du pourcentage)**

  - **Ce que fait ce paramètre :** Détermine sur quoi le pourcentage des frais est calculé.
  - **Effet de la modification de ce paramètre :**
    - *Total du panier (avec frais de port) :* Le pourcentage est calculé sur le montant total incluant les produits et les frais de port.
    - *Total du panier (sans frais de port) :* Le pourcentage est calculé uniquement sur le sous-total des produits.
  - **Valeur recommandée :** `Total du panier (avec frais de port)` car c'est généralement ainsi que les transporteurs calculent leurs frais COD.
  - **Scénario / exemple de marchand :** Si votre transporteur facture 1 % du *montant total* qu'il perçoit du client (produits + frais de port), choisissez « Total du panier (avec frais de port) ».
- **CODPRO\_CHARGEA\_V (Valeur des frais fixes)**

  - **Ce que fait ce paramètre :** Ce champ définit le montant monétaire fixe des frais COD.
  - **Effet de la modification de ce paramètre :** Si « Comment inclure les frais ? » est défini sur une option de montant fixe, cette valeur sera utilisée.
  - **Valeur recommandée :** `0.00` initialement, ajustez en fonction des frais fixes de votre transporteur.
  - **Scénario / exemple de marchand :** Si votre transporteur facture un forfait de 3,00 € pour le COD, vous saisirez `3.00` ici.
- **CODPRO\_MIN\_CHARGEV (Frais minimum pour les frais en pourcentage)**

  - **Ce que fait ce paramètre :** Si vous utilisez des frais basés sur un pourcentage, cela définit un montant fixe minimum que les frais COD représenteront, même si le pourcentage calculé est inférieur.
  - **Effet de la modification de ce paramètre :** Garantit que vous récupérez toujours au moins un certain montant pour le COD, en particulier sur les petites commandes où un pourcentage pourrait être très faible.
  - **Valeur recommandée :** `0.00` (pas de minimum) ou un petit montant comme `1.00` ou `2.00` si vous avez un coût minimum.
  - **Scénario / exemple de marchand :** Si vos frais en pourcentage sont de 1 %, et qu'une commande de 50 € entraînerait des frais de 0,50 €, mais que vous souhaitez garantir un minimum de 1,50 €, vous définirez ceci à `1.50`.
- **CODPRO\_MAX\_CHARGEV (Frais maximum pour les frais en pourcentage)**

  - **Ce que fait ce paramètre :** Si vous utilisez des frais basés sur un pourcentage, cela définit un montant fixe maximum que les frais COD représenteront, même si le pourcentage calculé est plus élevé.
  - **Effet de la modification de ce paramètre :** Empêche les frais COD de devenir excessivement élevés sur les très grandes commandes.
  - **Valeur recommandée :** `0.00` (pas de maximum) ou un plafond raisonnable comme `10.00` ou `15.00`.
  - **Scénario / exemple de marchand :** Si vos frais en pourcentage sont de 1 % et qu'une commande de 2000 € entraînerait des frais de 20 €, mais que vous souhaitez plafonner les frais COD à 10 €, vous définirez ceci à `10.00`.
- **CODPRO\_FEETAX (Appliquer la taxe aux frais)**

  - **Ce que fait ce paramètre :** Détermine si les frais COD eux-mêmes doivent être soumis à la TVA/aux taxes.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les frais COD seront taxés selon la règle de taxe sélectionnée.
    - *Lorsqu'désactivé :* Les frais COD seront traités comme exonérés de taxe.
  - **Valeur recommandée :** `Activé` si vos réglementations fiscales locales exigent que les frais soient taxés. Consultez votre comptable.
  - **Scénario / exemple de marchand :** Dans de nombreux pays, les frais de service comme les frais COD sont soumis à la TVA. Vous activeriez ceci pour assurer la conformité.
- **CODPRO\_FEETAXRULE (Règle de taxe pour les frais)**

  - **Ce que fait ce paramètre :** Si `CODPRO_FEETAX` est activé, ce menu déroulant vous permet de sélectionner la règle de taxe PrestaShop qui s'applique aux frais COD.
  - **Effet de la modification de ce paramètre :** Le taux de taxe sélectionné sera appliqué aux frais COD.
  - **Valeur recommandée :** Sélectionnez la règle de taxe appropriée pour les services dans votre pays.
  - **Scénario / exemple de marchand :** Si vous avez une règle de taxe « TVA standard (20 %) » pour les services, vous la sélectionnerez ici.

#### **Frais spécifiques au transporteur**

- **codpro\_carrier (Sélection du transporteur)**
  - **Ce que fait ce paramètre :** Cette section vous permet de définir différents frais COD pour chaque transporteur que vous proposez.
  - **Effet de la modification de ce paramètre :** Lorsqu'un client sélectionne un transporteur spécifique lors du paiement, les frais COD associés à ce transporteur seront appliqués au lieu des frais généraux.
  - **Valeur recommandée :** Configurez les frais pour tous les transporteurs qui proposent le COD.
  - **Scénario / exemple de marchand :** Si le transporteur A facture 3,00 € pour le COD et le transporteur B facture 1,5 % de la valeur de la commande, vous pouvez définir ces frais distincts ici.

#### **Paramètres avancés (généralement pour les développeurs/scénarios spécifiques)**

- **PS\_LANG\_DEFAULT / PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG (Paramètres de langue)**

  - **Ce que fait ce paramètre :** Ce sont des valeurs de configuration PrestaShop standard liées à la langue par défaut et à la langue du formulaire d'employé. Le module peut les afficher à titre de référence mais ne nécessite généralement pas de modification ici.
  - **Effet de la modification de ce paramètre :** Aucun effet direct sur la fonctionnalité principale du module, mais assure un affichage correct de la langue dans le Back Office.
  - **Valeur recommandée :** Laissez par défaut.
- **CODPRO\_ANALYTICS\_DEFAULT\_CHART / CODPRO\_ANALYTICS\_PERIOD / CODPRO\_ANALYTICS\_IMPACT\_DAYS / CODPRO\_ANALYTICS\_CHART\_WEEKS / CODPRO\_ANALYTICS\_CHART\_MONTHS (Paramètres d'analyse)**

  - **Ce que fait ce paramètre :** Ces paramètres sont liés aux fonctionnalités d'analyse interne ou de tableau de bord potentielles du module (si implémentées). Ils contrôlent la manière dont les données peuvent être affichées ou filtrées.
  - **Effet de la modification de ce paramètre :** Modifie la manière dont les données analytiques liées aux commandes COD peuvent être présentées dans le Back Office.
  - **Valeur recommandée :** Laissez par défaut, sauf si vous avez des exigences analytiques spécifiques.
  - **Scénario / exemple de marchand :** Si le module inclut un tableau de bord, ces paramètres peuvent contrôler la vue par défaut (par exemple, les 7 derniers jours, le mois dernier) pour les performances des commandes COD.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### **4.2.1 AdminCodProCarriersFeesController (Back Office > Modules > Paiement à la livraison avec frais > Frais de transporteur)**

- **Nom de l'écran et emplacement du menu :** « Frais de transporteur » (généralement sous l'élément de menu « Paiement à la livraison avec frais » dans le Back Office de PrestaShop).
- **Actions et paramètres disponibles :** Cet écran fournit une vue en grille ou en liste pour gérer les frais COD spécifiquement pour chaque transporteur. Vous pouvez ajouter de nouvelles règles spécifiques au transporteur, modifier celles existantes ou les supprimer. Pour chaque transporteur, vous pouvez définir :
  - Si les frais sont un montant fixe ou un pourcentage.
  - Le montant fixe ou la valeur en pourcentage spécifique.
  - Les frais minimum et maximum pour les frais en pourcentage.
  - Si la taxe s'applique et quelle règle de taxe utiliser.
- **Effet des modifications :** Toutes les règles configurées ici remplaceront les paramètres généraux des frais COD pour les transporteurs spécifiés. Si un transporteur a une règle ici, les frais de cette règle seront appliqués. Si un transporteur n'est pas répertorié ici, les paramètres généraux des frais COD s'appliqueront.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Examinez régulièrement cette section si vos contrats de transporteur ou vos frais COD changent. Ajoutez de nouveaux transporteurs au fur et à mesure que vous les introduisez dans votre boutique et configurez leurs frais COD spécifiques.

#### **4.2.2 AdminCodProCarriersRangeFeesController (Back Office > Modules > Paiement à la livraison avec frais > Frais par tranche)**

- **Nom de l'écran et emplacement du menu :** « Frais par tranche » (généralement sous l'élément de menu « Paiement à la livraison avec frais » dans le Back Office de PrestaShop).
- **Actions et paramètres disponibles :** Cet écran vous permet de définir les frais COD en fonction de la valeur totale du panier du client. Vous pouvez configurer différentes structures de frais pour différentes tranches de prix (par exemple, commandes de 0 € à 50 €, de 50 € à 100 €, etc.). Pour chaque tranche, vous pouvez définir :
  - La valeur minimale et maximale du panier pour la tranche.
  - Si les frais sont un montant fixe ou un pourcentage.
  - Le montant fixe ou la valeur en pourcentage spécifique.
  - Les frais minimum et maximum pour les frais en pourcentage dans cette tranche.
  - Si la taxe s'applique et quelle règle de taxe utiliser.
- **Effet des modifications :** Ces règles basées sur les tranches offrent une couche de flexibilité supplémentaire. Si le total du panier d'un client se situe dans une tranche définie, les frais spécifiés pour cette tranche seront appliqués. Ces règles peuvent interagir avec les règles spécifiques au transporteur, permettant potentiellement un contrôle très granulaire (par exemple, le transporteur A facture X pour les commandes de moins de 50 €, et Y pour les commandes de plus de 50 €).
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Utilisez cette section pour implémenter une tarification dynamique pour le COD basée sur la valeur de la commande. Ceci est particulièrement utile pour gérer les risques sur les commandes de grande valeur ou pour rendre le COD plus attractif pour les commandes de moyenne gamme.

#### **4.2.3 index.php (Back Office > Modules > Paiement à la livraison avec frais > Tableau de bord/Analytique)**

- **Nom de l'écran et emplacement du menu :** Ce contrôleur `index.php` sert généralement de placeholder ou de point d'entrée par défaut pour la section d'administration d'un module. Dans le contexte de ce module, il pourrait être utilisé pour afficher un tableau de bord ou des analyses liées aux commandes COD.
- **Actions et paramètres disponibles :** Si ce contrôleur est utilisé pour un tableau de bord, il afficherait probablement des graphiques, des statistiques ou des indicateurs de performance clés (KPI) liés aux commandes COD (par exemple, nombre de commandes COD, revenus totaux du COD, frais COD moyens collectés). Il pourrait y avoir des filtres pour les plages de dates ou d'autres paramètres.
- **Effet des modifications :** L'interaction avec un tableau de bord ici ne modifierait que les données affichées, et non la configuration de la boutique.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vérifiez périodiquement ce tableau de bord (s'il est disponible) pour surveiller les performances et l'impact de votre méthode de paiement COD.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration principale du module** | Activé / Désactivé | Activé | Interrupteur principal pour la méthode de paiement COD. |
| | Valeur (Frais de base) | 0.00 | Montant/pourcentage des frais par défaut. |
| | Comment inclure les frais ? | Inclure comme produit/service séparé | Détermine comment les frais apparaissent dans le panier/la facture. |
| | Statut de la commande après achat | Paiement accepté | Statut initial des commandes COD. |
| | Afficher un récapitulatif supplémentaire | Activé | Affiche une ventilation détaillée des frais avant confirmation. |
| | Condition de valeur maximale du panier | Désactivé | Restreint le COD pour les commandes supérieures à une valeur. |
| | Valeur maximale du panier | 0.00 | La valeur maximale spécifique du panier. |
| | Condition de valeur minimale du panier | Désactivé | Restreint le COD pour les commandes inférieures à une valeur. |
| | Valeur minimale du panier | 0.00 | La valeur minimale spécifique du panier. |
| | Valeur des frais en pourcentage | 0.00 | La valeur en pourcentage des frais COD. |
| | Base de calcul du pourcentage | Total du panier (avec frais de port) | Sur quoi le pourcentage est calculé. |
| | Valeur des frais fixes | 0.00 | La valeur du montant fixe des frais COD. |
| | Frais minimum (pour %) | 0.00 | Assure des frais minimum pour les calculs en pourcentage. |
| | Frais maximum (pour %) | 0.00 | Plafonne les frais pour les calculs en pourcentage. |
| | Appliquer la taxe aux frais | Activé (si applicable) | Détermine si les frais COD sont taxés. |
| | Règle de taxe pour les frais | Sélectionner la règle de taxe appropriée | Quelle règle de taxe s'applique aux frais. |
| **AdminCodProCarriersFees** | Règles de frais spécifiques au transporteur | Configurer selon les besoins | Remplace les frais généraux pour des transporteurs spécifiques. |
| **AdminCodProCarriersRangeFees** | Règles de frais par tranche de valeur de commande | Configurer selon les besoins | Applique des frais différents en fonction des tranches de total du panier. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Les frais COD n'apparaissent pas sur ma page de paiement, ou ils sont au mauvais endroit.**
R1 : Cela se produit généralement avec les thèmes personnalisés.
- **Vérifiez « Afficher un récapitulatif supplémentaire avant la confirmation » :** Assurez-vous que cette option est `Activée` dans la configuration principale du module.
- **Sélecteurs CSS :** Si votre thème utilise des classes CSS non standard, le module pourrait ne pas trouver les bons endroits pour injecter les frais. Accédez à la page de configuration du module et vérifiez les champs de sélecteur CSS « Récapitulatif du panier », « Récapitulatif de l'adresse » et « Valeur minimale du total du panier ». Vous pourriez avoir besoin d'un développeur web pour inspecter le HTML de votre thème et fournir les sélecteurs corrects.
- **Vider le cache :** Videz toujours le cache de votre PrestaShop (Paramètres avancés > Performances > Vider le cache) après avoir effectué des modifications de configuration.

**Q2 : J'ai configuré des frais, mais ils ne sont pas appliqués aux commandes.**
R2 :
- **Module activé :** Assurez-vous que l'interrupteur principal « Activé / Désactivé » du module est réglé sur `Activé`.
- **Valeur des frais :** Vérifiez que vous avez saisi une « Valeur » non nulle dans la configuration principale, ou configuré des frais spécifiques dans les sections « Frais de transporteur » ou « Frais par tranche ».
- **Conditions remplies :** Vérifiez que le panier du client respecte toutes les conditions de « Valeur minimale du panier » ou de « Valeur maximale du panier » que vous avez définies.
- **Priorités spécifiques au transporteur :** Si vous avez configuré des frais dans « Frais de transporteur », assurez-vous que le client sélectionne l'un de ces transporteurs. Sinon, les frais généraux devraient s'appliquer.
- **Règle de taxe :** Si vous utilisez une règle de taxe pour les frais, assurez-vous que la règle de taxe elle-même est correctement configurée dans PrestaShop.

**Q3 : Comment traduire le texte du module (par exemple, « Frais COD ») dans d'autres langues ?**
R3 : Vous pouvez traduire les chaînes de caractères du module directement dans PrestaShop :
- Naviguez vers **International > Traductions**.
- Sélectionnez « Traductions des modules installés ».
- Choisissez votre thème, votre langue, puis sélectionnez « Paiement à la livraison avec frais » dans la liste déroulante des modules.
- Vous verrez une liste de toutes les chaînes de caractères traduisibles du module. Saisissez vos traductions et enregistrez.

**Q4 : Puis-je proposer le COD uniquement pour des groupes de clients ou des pays spécifiques ?**
R4 : Le module « Paiement à la livraison avec frais » lui-même n'a pas d'options intégrées pour les restrictions de groupe de clients ou de pays. Cependant, les restrictions de module de paiement de base de PrestaShop peuvent être utilisées :
- Allez dans **Paramètres de la boutique > Paramètres de commande > Paiement**.
- Vous pouvez restreindre les méthodes de paiement par devise, pays ou groupe. Trouvez « Paiement à la livraison avec frais » et appliquez-y les restrictions souhaitées.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Vue d'ensemble de l'architecture

Le module « Paiement à la livraison avec frais » (`codpro`) suit une architecture de module PrestaShop standard, étendant `PaymentModule` pour s'intégrer au flux de paiement. Il utilise plusieurs contrôleurs front-office et admin pour des fonctionnalités spécifiques telles que la validation des paiements, la gestion des frais spécifiques aux transporteurs et les configurations de frais basées sur des tranches. Le module s'appuie fortement sur le système de hooks de PrestaShop pour injecter sa logique et afficher des éléments à différentes étapes du front-office (paiement, confirmation de commande, facture) et du back-office (vue de commande). La configuration est principalement stockée dans `ps_configuration`, avec des tables personnalisées probablement utilisées pour les définitions de frais basées sur les transporteurs et les tranches.

### 4.2 Contrôleurs (`controllers/`)

#### **Contrôleurs Front-Office**

- `controllers/front/index.php`
  - Nom de la classe : `CodProIndexModuleFrontController` (étend probablement `ModuleFrontController`)
  - Responsabilité : Ce contrôleur pourrait servir de point d'entrée par défaut ou gérer le routage de base pour les actions du module côté front-office. Compte tenu de l'objectif du module, il pourrait s'agir d'un placeholder ou être utilisé pour de simples requêtes AJAX liées aux mises à jour du calcul des frais pendant le paiement.
- `controllers/front/validation.php`
  - Nom de la classe : `CodProValidationModuleFrontController` (étend probablement `ModuleFrontController`)
  - Responsabilité : C'est le contrôleur critique pour le traitement du paiement lorsqu'un client choisit « Paiement à la livraison avec frais ». Il gère la validation finale de la commande, applique les frais COD calculés au panier et redirige le client vers la page de confirmation de commande. Il interagit avec la classe de module principale `codpro.php` pour récupérer les paramètres de frais et mettre à jour la commande.

#### **Contrôleurs d'administration Back-Office**

- `controllers/admin/AdminCodProCarriersFees.php`
  - Nom de la classe : `AdminCodProCarriersFeesController` (étend `ModuleAdminController`)
  - Nom de l'onglet : « Frais de transporteur » (ou similaire, accessible via le menu du module).
  - Entité gérée : `Configuration` (bien qu'il gère des entrées de configuration spécifiques liées aux transporteurs).
  - Responsabilité : Fournit l'interface pour gérer les frais COD par transporteur. Il affiche une liste des frais de transporteur configurés, permet d'en ajouter de nouveaux et de modifier/supprimer les entrées existantes. Il utilise probablement les `HelperList` et `HelperForm` de PrestaShop pour son interface utilisateur.
- `controllers/admin/AdminCodProCarriersRangeFees.php`
  - Nom de la classe : `AdminCodProCarriersRangeFeesController` (étend `ModuleAdminController`)
  - Nom de l'onglet : « Frais par tranche » (ou similaire, accessible via le menu du module).
  - Entité gérée : `CodProTotal` (probablement un `ObjectModel` personnalisé pour les frais basés sur des tranches).
  - Responsabilité : Gère les frais COD basés sur les tranches de total de commande. Il fournit une grille pour définir, modifier et supprimer les règles de frais pour différentes tranches de valeur de panier. Ce contrôleur utilise également les `HelperList` et `HelperForm` de PrestaShop pour son interface administrative.
- `controllers/admin/index.php`
  - Nom de la classe : `AdminCodProIndexController` (étend probablement `ModuleAdminController`)
  - Nom de l'onglet : Placeholder ou Tableau de bord.
  - Entité gérée : Aucune directement.
  - Responsabilité : Ce contrôleur sert probablement de point d'entrée pour un tableau de bord de module ou une vue par défaut lors de la navigation vers la section d'administration du module. Il pourrait afficher des analyses ou un résumé des commandes COD.

### 4.3 Classes et modèles principaux (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que la logique principale pour la gestion des frais de transporteur et de tranche pourrait être gérée directement dans `AdminCodProCarriersFeesController` et `AdminCodProCarriersRangeFeesController` en utilisant des interactions directes avec la base de données ou en définissant de simples tableaux pour la configuration. Cependant, `AdminCodProCarriersRangeFeesController` gérant `codprototal` implique qu'il *devrait* y avoir un `ObjectModel` nommé `CodProTotal` (ou similaire) dans le répertoire `classes/`, même s'il n'est pas explicitement listé dans le dossier. Sinon, cela signifie que des requêtes SQL directes sont utilisées, ce qui est moins idéal.

### 4.4 Actifs JavaScript (`views/js/`)

- `views/js/adminCodProCarriersFees.js`
  - Portée : Back-office (AdminCodProCarriersFeesController).
  - Fonctionnalité : Gère probablement le comportement dynamique sur la page de configuration des frais de transporteur. Cela pourrait inclure des appels AJAX pour l'enregistrement/le chargement des données, la validation des formulaires ou des éléments interactifs pour l'ajout/la suppression de règles de frais de transporteur.
- `views/js/adminCodProDashboard.js`
  - Portée : Back-office (AdminCodProIndexController ou vue de tableau de bord similaire).
  - Fonctionnalité : Responsable du rendu des graphiques, de la mise à jour des statistiques et de la gestion des éléments interactifs sur le tableau de bord du module. Il pourrait utiliser des bibliothèques de graphiques (par exemple, Chart.js) et effectuer des requêtes AJAX pour récupérer des données analytiques.
- `views/js/codpro-checkout.js`
  - Portée : Front-office (page de paiement).
  - Fonctionnalité : Ceci est crucial pour l'expérience utilisateur front-end. Il écoute les changements dans la sélection de la méthode de paiement (spécifiquement pour « Paiement à la livraison avec frais »), met à jour dynamiquement le récapitulatif de la commande pour refléter les frais COD, et gère potentiellement les requêtes AJAX pour recalculer les frais si le transporteur ou le contenu du panier changent. Il garantit que les frais sont visibles avant la confirmation de la commande.

### 4.5 Feuilles de style CSS (`views/css/`)

- `views/css/admin_codpro.css`
  - Portée : Back-office (Panneau d'administration).
  - Fonctionnalité : Fournit le style pour les pages de configuration du module, la gestion des frais de transporteur, la gestion des frais par tranche et tous les éléments du tableau de bord. Il assure une apparence cohérente dans le Back Office de PrestaShop.
  - Sélecteurs clés : Cible probablement des ID ou des classes spécifiques dans les formulaires et listes d'administration du module (par exemple, `.codpro-admin-form`, `.codpro-dashboard-chart`).
- `views/css/codpro.css`
  - Portée : Front-office (Page de paiement, confirmation de commande, facture).
  - Fonctionnalité : Style l'affichage des frais COD dans le récapitulatif du paiement, les options de paiement, la page de confirmation de commande et potentiellement la facture PDF. Il garantit que les frais sont clairement visibles et intégrés au thème de la boutique.
  - Sélecteurs clés : Cible les éléments où les frais COD sont injectés (par exemple, `.codpro-fee-display`, `.payment_option_codpro`, `.order-summary-cod-fee`). Les développeurs pourraient avoir besoin de les remplacer dans leur thème pour une intégration visuelle parfaite.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### **Modèles de hook (`views/templates/hook/`)**

- `views/templates/hook/confirmation.tpl`
  - Hook : `paymentReturn` ou similaire.
  - Sorties : Les détails des frais COD sur la page de confirmation de commande après une commande COD réussie.
- `views/templates/hook/displayAdminOrder16.tpl`
  - Hook : `displayAdminOrder` (pour PrestaShop 1.6).
  - Sorties : Informations supplémentaires sur les frais COD dans la page de détails de la commande dans le Back Office de PrestaShop 1.6.
- `views/templates/hook/displayAdminOrder17.tpl`
  - Hook : `displayAdminOrder` (pour PrestaShop 1.7+).
  - Sorties : Similaire à `displayAdminOrder16.tpl`, mais adapté à la mise en page de la page de détails de commande du Back Office de PrestaShop 1.7+.
- `views/templates/hook/displayOrderDetail.tpl`
  - Hook : `displayOrderDetail` (historique des commandes client front-office).
  - Sorties : Affiche les frais COD dans le récapitulatif de la commande lorsqu'un client consulte les détails de ses commandes passées dans sa section « Mon compte ».
- `views/templates/hook/payment.tpl`
  - Hook : `displayPaymentOptions` ou `paymentOptions`.
  - Sorties : L'option de paiement « Paiement à la livraison avec frais » sur la page de paiement, y compris le montant des frais calculé dynamiquement.
- `views/templates/hook/pdf.tpl`
  - Hook : `displayPDFInvoice`.
  - Sorties : Les frais COD comme ligne sur la facture PDF générée pour la commande.

#### **Modèles Front-office (`views/templates/front/`)**

- `views/templates/front/validation.tpl`
  - Objectif : Ce modèle est probablement utilisé par le contrôleur frontal `validation.php`. Il pourrait afficher un simple message pendant le processus de validation du paiement ou servir de page de redirection.

### 4.7 Schéma de la base de données et carte des hooks

#### **Tables de la base de données**

- `ps_configuration` : Stocke tous les paramètres généraux du module (par exemple, `CODPRO_MOD_MAXCART_V`, `CODPRO_CHARGEP_V`, `CODPRO_FEETAX`).
- `ps_codpro_carrier_fees` (probable) : Une table personnalisée pour stocker les règles de frais COD spécifiques aux transporteurs.
  - Colonnes : `id_codpro_carrier_fee`, `id_carrier`, `fee_type` (fixe/pourcentage), `fee_value`, `min_charge`, `max_charge`, `tax_enabled`, `id_tax_rule`.
- `ps_codpro_range_fees` (probable) : Une table personnalisée pour stocker les règles de frais COD basées sur la valeur de la commande.
  - Colonnes : `id_codpro_range_fee`, `min_value`, `max_value`, `fee_type`, `fee_value`, `min_charge`, `max_charge`, `tax_enabled`, `id_tax_rule`.

#### **Table des hooks enregistrés**

| Nom du hook | Portée | Moment d'exécution | Objectif technique |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | Dans la section `<head>` de toutes les pages. | Pour inclure le CSS front-office (`codpro.css`) et le JS (`codpro-checkout.js`) sur les pages pertinentes (par exemple, paiement). |
| `displayPaymentOptions` | Front-Office | Pendant la sélection de la méthode de paiement lors du paiement. | Pour afficher « Paiement à la livraison avec frais » comme option de paiement, y compris les frais calculés. |
| `paymentOptions` | Front-Office | Équivalent PrestaShop 1.6 de `displayPaymentOptions`. | Pour afficher « Paiement à la livraison avec frais » comme option de paiement. |
| `paymentReturn` | Front-Office | Sur la page de confirmation de commande après le paiement. | Pour afficher les détails des frais COD sur la page de confirmation. |
| `displayPaymentReturn` | Front-Office | Équivalent PrestaShop 1.6 de `paymentReturn`. | Pour afficher les détails des frais COD sur la page de confirmation. |
| `displayPDFInvoice` | Front-Office (Génération PDF) | Lors de la génération d'une facture PDF. | Pour ajouter les frais COD comme ligne sur la facture. |
| `displayOrderDetail` | Front-Office (Mon Compte) | Lorsqu'un client consulte les détails de sa commande. | Pour afficher les frais COD dans l'historique des commandes du client. |
| `displayAdminOrder` | Back-Office (Vue de commande) | Lorsqu'un administrateur consulte une commande dans le Back Office. | Pour afficher les détails des frais COD dans le récapitulatif de la commande pour examen par l'administrateur. |
| `ActionAdminControllerSetMedia` | Back-Office (Pages d'administration) | Avant qu'un contrôleur d'administration ne rende sa vue. | Pour inclure le CSS back-office (`admin_codpro.css`) et le JS (`adminCodProCarriersFees.js`, `adminCodProDashboard.js`) sur les pages d'administration du module. |
| `actionValidateOrder` | Back-Office (Traitement des commandes) | Après la validation d'une commande. | Pour potentiellement effectuer des actions supplémentaires ou l'enregistrement de données liées aux commandes COD. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur MyPresta.eu.

- **Historique des commandes et téléchargements MyPresta.eu :** <https://mypresta.eu/my-account/orders/>
- **Support MyPresta.eu :** <https://mypresta.eu/contact>
"""
