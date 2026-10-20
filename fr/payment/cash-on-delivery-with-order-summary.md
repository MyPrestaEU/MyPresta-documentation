---
title: "Paiement à la livraison avec récapitulatif de commande - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Paiement à la livraison avec récapitulatif de commande par MyPresta.eu."
sidebar:
  label: "Paiement à la livraison avec récapitulatif de commande"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Cash on delivery with order summary sur MyPresta.eu](https://mypresta.eu/modules/payment-process/cash-on-delivery-with-order-summary.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/payment/cash-on-delivery-with-order-summary/)
>
> ---


# Paiement à la livraison avec récapitulatif de commande

## 1. Exigences et compatibilité

-   **Versions de PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilité PHP** : PHP 5.6 - 8.5
-   **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises par PrestaShop lui-même et sont suffisantes pour ce module.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal où vous définissez le comportement de base et les frais pour votre méthode de paiement à la livraison.

-   **Emplacement du menu :** Back Office > Modules > Gestionnaire de modules > Rechercher "Paiement à la livraison avec récapitulatif de commande" > Cliquer sur "Configurer".

#### Paramètres généraux

1.  **Désactiver le paiement à la livraison pour des transporteurs spécifiques**
    -   **Ce que fait ce paramètre :** Vous permet d'empêcher l'option de paiement à la livraison d'être disponible si un client choisit certains transporteurs.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (coché pour des transporteurs spécifiques) :* Si un client sélectionne l'un des transporteurs choisis lors du paiement, l'option de paiement à la livraison n'apparaîtra pas.
        -   *Lorsqu'désactivé (décoché pour tous les transporteurs) :* Le paiement à la livraison sera disponible quel que soit le transporteur choisi (sauf si d'autres restrictions s'appliquent).
    -   **Valeur recommandée :** Dépend de votre logistique d'expédition. Si certains transporteurs ne prennent pas en charge le paiement à la livraison ou facturent des frais excessifs, activez cette option.
    -   **Scénario / exemple de marchand :** Vous utilisez un service de messagerie spécifique qui ne gère pas les paiements en espèces. Vous cocheriez ce transporteur dans cette liste pour désactiver le paiement à la livraison pour eux.

2.  **Comment inclure les frais ?**
    -   **Ce que fait ce paramètre :** Détermine comment les frais de paiement à la livraison sont calculés et appliqués à la commande.
    -   **Effet de la modification de ce paramètre :**
        -   *Inclure aux frais de port :* Les frais de paiement à la livraison seront ajoutés directement aux frais de port affichés au client. Cela peut simplifier l'affichage du paiement mais pourrait masquer les frais de paiement à la livraison séparés.
        -   *Inclure comme produit séparé :* Les frais de paiement à la livraison apparaîtront comme une ligne distincte dans le panier et le récapitulatif de commande, souvent étiquetés "Frais de paiement à la livraison" ou similaire. Cela offre une transparence maximale.
    -   **Valeur recommandée :** "Inclure comme produit séparé" pour la clarté et la conformité légale, en particulier dans l'UE.
    -   **Scénario / exemple de marchand :** Pour montrer clairement aux clients le coût exact de l'utilisation du paiement à la livraison, vous sélectionneriez "Inclure comme produit séparé".

3.  **Statut de la commande après achat avec le module de paiement à la livraison**
    -   **Ce que fait ce paramètre :** Définit le statut initial d'une commande passée en utilisant la méthode de paiement à la livraison.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur "Paiement accepté" :* La commande sera immédiatement marquée comme payée, ce qui pourrait être trompeur car l'argent n'a pas encore été collecté.
        -   *Lorsqu'il est défini sur "En attente de validation du paiement à la livraison" (ou similaire) :* La commande sera dans un état en attente, indiquant que le paiement est attendu à la livraison. C'est généralement plus sûr et plus précis.
    -   **Valeur recommandée :** Un statut en attente comme "En attente de validation du paiement à la livraison" ou "Paiement en attente" pour refléter précisément le statut du paiement.
    -   **Scénario / exemple de marchand :** Pour éviter d'expédier prématurément une commande qui n'a pas été payée, vous définiriez ce statut sur un statut en attente.

4.  **Afficher un récapitulatif supplémentaire avant la confirmation**
    -   **Ce que fait ce paramètre :** Contrôle si le module affiche la page dédiée de récapitulatif de commande avant confirmation. C'est la fonctionnalité de conformité principale du module.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Après avoir sélectionné le paiement à la livraison, les clients verront un récapitulatif détaillé de leur commande, y compris tous les coûts, avant de pouvoir cliquer sur le bouton final "Confirmer la commande".
        -   *Lorsqu'désactivé :* Le module ignorera cette page de récapitulatif, et les clients passeront directement à la confirmation de commande standard de PrestaShop (ce qui pourrait ne pas être légalement conforme dans certaines régions).
    -   **Valeur recommandée :** **Activé**. C'est une fonctionnalité clé pour la conformité légale et la confiance des clients.
    -   **Scénario / exemple de marchand :** Pour vous conformer aux lois européennes sur la consommation exigeant un récapitulatif de commande clair avant la confirmation finale, vous **devez** activer ce paramètre.

#### Restrictions de valeur du panier

5.  **Valeur minimale du panier**
    -   **Ce que fait ce paramètre :** Définit la valeur totale minimale qu'une commande doit avoir pour que l'option de paiement à la livraison soit disponible.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur une valeur (par exemple, 10.00) :* Si le total du panier du client est inférieur à ce montant, le paiement à la livraison ne sera pas proposé comme option de paiement.
        -   *Lorsqu'il est laissé vide ou défini sur 0 :* Il n'y aura pas de restriction de valeur minimale du panier pour le paiement à la livraison.
    -   **Valeur recommandée :** Définissez un minimum raisonnable si le coût opérationnel de traitement des petites commandes en paiement à la livraison est trop élevé. Sinon, laissez vide.
    -   **Scénario / exemple de marchand :** Si le coût de traitement d'une commande en paiement à la livraison (frais de messagerie, travail administratif) est de 5 €, vous pourriez définir une valeur minimale du panier de 10 € pour assurer la rentabilité.

6.  **Valeur maximale du panier**
    -   **Ce que fait ce paramètre :** Définit la valeur totale maximale qu'une commande peut avoir pour que l'option de paiement à la livraison soit disponible.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur une valeur (par exemple, 500.00) :* Si le total du panier du client dépasse ce montant, le paiement à la livraison ne sera pas proposé comme option de paiement.
        -   *Lorsqu'il est laissé vide ou défini sur 0 :* Il n'y aura pas de restriction de valeur maximale du panier pour le paiement à la livraison.
    -   **Valeur recommandée :** Définissez un maximum si vous souhaitez limiter votre risque pour les commandes de très grande valeur qui pourraient être sujettes à la fraude ou au non-recouvrement. Sinon, laissez vide.
    -   **Scénario / exemple de marchand :** Pour atténuer le risque de non-paiement pour des commandes très coûteuses, vous pourriez définir une valeur maximale du panier de 200 € pour le paiement à la livraison.

#### Paramètres des frais de paiement à la livraison

7.  **Type de frais de paiement à la livraison (Pourcentage ou Montant)**
    -   **Ce que fait ce paramètre :** Détermine si les frais de paiement à la livraison sont un montant fixe ou un pourcentage du total de la commande.
    -   **Effet de la modification de ce paramètre :**
        -   *Pourcentage :* Les frais seront calculés en pourcentage du total de la commande.
        -   *Montant :* Les frais seront une valeur monétaire fixe.
    -   **Valeur recommandée :** Choisissez en fonction de votre structure de coûts. Si vos coûts varient avec la valeur de la commande, utilisez un pourcentage. S'il s'agit de frais de traitement fixes, utilisez un montant.
    -   **Scénario / exemple de marchand :** Si votre banque facture un pourcentage de la valeur de la transaction pour la gestion des espèces, vous choisiriez "Pourcentage". Si votre coursier facture des frais fixes pour le paiement à la livraison, vous choisiriez "Montant".

8.  **Valeur des frais de paiement à la livraison (Pourcentage)** (Apparaît si "Pourcentage" est sélectionné ci-dessus)
    -   **Ce que fait ce paramètre :** La valeur en pourcentage à facturer comme frais de paiement à la livraison.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur 5 :* Les frais de paiement à la livraison seront de 5 % du total de la commande.
    -   **Valeur recommandée :** Un pourcentage qui couvre vos coûts sans dissuader les clients.
    -   **Scénario / exemple de marchand :** Pour couvrir des frais bancaires de 2 % pour les dépôts en espèces, vous pourriez définir cette valeur sur "2".

9.  **Valeur des frais de paiement à la livraison (Montant)** (Apparaît si "Montant" est sélectionné ci-dessus)
    -   **Ce que fait ce paramètre :** La valeur monétaire fixe à facturer comme frais de paiement à la livraison.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur 2.50 :* Les frais de paiement à la livraison seront de 2,50 € (ou votre devise par défaut) quel que soit le total de la commande.
    -   **Valeur recommandée :** Un montant fixe qui couvre vos frais de traitement fixes.
    -   **Scénario / exemple de marchand :** Si votre coursier facture 3 € fixes pour le service de paiement à la livraison, vous définiriez cette valeur sur "3".

10. **Frais de paiement à la livraison minimum**
    -   **Ce que fait ce paramètre :** Définit un montant minimum pour les frais de paiement à la livraison, quelle que soit la méthode de calcul en pourcentage.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur 1.00 et que le pourcentage calcule 0.50 :* Les frais seront de 1.00.
        -   *Lorsqu'il est défini sur 1.00 et que le pourcentage calcule 2.00 :* Les frais seront de 2.00.
    -   **Valeur recommandée :** Utile si vous avez un coût minimum associé au paiement à la livraison, même pour les petites commandes.
    -   **Scénario / exemple de marchand :** Si 5 % d'une commande de 10 € ne représente que 0,50 €, mais que votre coût de traitement minimum est de 1 €, vous définiriez cette valeur sur "1.00".

11. **Frais de paiement à la livraison maximum**
    -   **Ce que fait ce paramètre :** Définit un montant maximum pour les frais de paiement à la livraison, quelle que soit la méthode de calcul en pourcentage.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur 10.00 et que le pourcentage calcule 15.00 :* Les frais seront de 10.00.
        -   *Lorsqu'il est défini sur 10.00 et que le pourcentage calcule 5.00 :* Les frais seront de 5.00.
    -   **Valeur recommandée :** Utile pour éviter que les frais de paiement à la livraison ne deviennent excessivement élevés sur les très grosses commandes.
    -   **Scénario / exemple de marchand :** Pour s'assurer que les frais de paiement à la livraison ne deviennent pas prohibitifs pour les grosses commandes, vous pourriez les plafonner à 15 €.

12. **Appliquer la taxe aux frais de paiement à la livraison**
    -   **Ce que fait ce paramètre :** Détermine si les frais de paiement à la livraison eux-mêmes sont soumis à la taxe de vente.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Vous pourrez sélectionner une règle de taxe à appliquer aux frais de paiement à la livraison.
        -   *Lorsqu'désactivé :* Les frais de paiement à la livraison seront exonérés de taxe.
    -   **Valeur recommandée :** Consultez vos réglementations fiscales locales. Dans de nombreuses régions, les frais de traitement des paiements sont imposables.
    -   **Scénario / exemple de marchand :** Si les lois fiscales de votre pays vous obligent à facturer la TVA sur les frais de service de paiement, vous activeriez cette option et sélectionneriez la règle de taxe appropriée.

13. **Règle de taxe pour les frais de paiement à la livraison** (Apparaît si "Appliquer la taxe aux frais de paiement à la livraison" est activé)
    -   **Ce que fait ce paramètre :** Vous permet de sélectionner une règle de taxe existante dans votre boutique PrestaShop à appliquer aux frais de paiement à la livraison.
    -   **Effet de la modification de ce paramètre :** Le taux de taxe sélectionné sera appliqué aux frais de paiement à la livraison calculés.
    -   **Valeur recommandée :** Sélectionnez la règle de taxe qui correspond aux frais de traitement des paiements dans votre juridiction.
    -   **Scénario / exemple de marchand :** Si vous avez une règle de taxe "TVA 20%", vous la sélectionneriez ici pour appliquer 20% de TVA aux frais de paiement à la livraison.

#### Paramètres d'affichage avancés

14. **Sélecteur CSS pour le total du panier**
    -   **Ce que fait ce paramètre :** Vous permet de spécifier le sélecteur CSS pour l'élément qui affiche la valeur totale du panier sur votre page de paiement. Cela aide le module à mettre à jour avec précision le total lorsqu'un frais de paiement à la livraison est appliqué.
    -   **Effet de la modification de ce paramètre :** S'il est correctement défini, le module peut mettre à jour dynamiquement le total sur la page de paiement pour inclure les frais de paiement à la livraison. S'il est incorrect, le total pourrait ne pas être mis à jour, ce qui entraînerait une confusion.
    -   **Valeur recommandée :** Laissez vide sauf si vous rencontrez des problèmes d'affichage avec le total qui ne se met pas à jour. Si nécessaire, consultez le développeur de votre thème ou utilisez les outils de développement du navigateur pour trouver le sélecteur correct (par exemple, `.cart-total-value`).
    -   **Scénario / exemple de marchand :** Si votre thème utilise une classe personnalisée comme `.mytheme-total-price` pour le total du panier, vous la saisiriez ici.

15. **Sélecteur CSS pour le sous-total du panier**
    -   **Ce que fait ce paramètre :** Similaire au total du panier, cela spécifie le sélecteur CSS pour le sous-total du panier.
    -   **Effet de la modification de ce paramètre :** Aide le module à identifier et potentiellement mettre à jour correctement l'affichage du sous-total.
    -   **Valeur recommandée :** Laissez vide sauf si des problèmes d'affichage surviennent.
    -   **Scénario / exemple de marchand :** Si votre thème a un élément spécifique pour le sous-total, vous pourriez avoir besoin de saisir son sélecteur ici.

16. **Sélecteur CSS pour les frais de port du panier**
    -   **Ce que fait ce paramètre :** Similaire au total du panier, cela spécifie le sélecteur CSS pour l'affichage des frais de port.
    -   **Effet de la modification de ce paramètre :** Aide le module à identifier et potentiellement mettre à jour correctement l'affichage des frais de port, surtout si les frais de paiement à la livraison sont inclus dans les frais de port.
    -   **Valeur recommandée :** Laissez vide sauf si des problèmes d'affichage surviennent.
    -   **Scénario / exemple de marchand :** Si votre thème a un élément spécifique pour les frais de port, vous pourriez avoir besoin de saisir son sélecteur ici.

17. **Logo de paiement à la livraison**
    -   **Ce que fait ce paramètre :** Vous permet de télécharger un logo personnalisé qui sera affiché à côté de l'option de paiement à la livraison lors du paiement.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est téléchargé :* Une icône ou un logo visuel apparaîtra, rendant l'option de paiement à la livraison plus proéminente et visuellement attrayante.
        -   *Lorsqu'il est vide :* Aucun logo personnalisé ne sera affiché.
    -   **Valeur recommandée :** Téléchargez un petit logo clair (par exemple, une icône d'argent) pour améliorer l'expérience utilisateur.
    -   **Scénario / exemple de marchand :** Pour faire ressortir l'option de paiement à la livraison, vous pourriez télécharger une petite image de billets de banque ou de pièces de monnaie.

#### Paramètres d'analyse (Utilisation interne du module)

Ces paramètres sont généralement destinés à l'analyse interne du module et ne nécessitent généralement pas d'intervention du marchand.

18. **CODPRO_ANALYTICS_DEFAULT_CHART, CODPRO_ANALYTICS_PERIOD, CODPRO_ANALYTICS_IMPACT_DAYS, CODPRO_ANALYTICS_CHART_WEEKS, CODPRO_ANALYTICS_CHART_MONTHS**
    -   **Ce que font ces paramètres :** Ce sont des clés de configuration internes utilisées par le module pour d'éventuelles futures fonctionnalités d'analyse ou des affichages de tableau de bord au sein de l'administration du module. Elles contrôlent la manière dont les données pourraient être collectées ou affichées pour le suivi des performances.
    -   **Effet de la modification de ces paramètres :** Il est peu probable qu'ils aient un impact direct et immédiat sur l'expérience client en front-office. Affecte principalement les rapports potentiels en back-office.
    -   **Valeur recommandée :** Laissez leurs valeurs par défaut.
    -   **Scénario / exemple de marchand :** Ceux-ci ne sont généralement pas ajustés par les marchands.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module fournit deux écrans d'administration supplémentaires pour un contrôle plus granulaire des frais de paiement à la livraison, particulièrement utiles pour les stratégies d'expédition et de tarification complexes.

#### 2.2.1 AdminCodProCarriersFeesController : Frais de paiement à la livraison spécifiques au transporteur

-   **Nom de l'écran et emplacement du menu :** Back Office > Modules > Gestionnaire de modules > Rechercher "Paiement à la livraison avec récapitulatif de commande" > Cliquer sur "Configurer" > Rechercher un onglet ou un lien intitulé "Frais de transporteur" ou similaire (cela peut être intégré à la configuration principale ou à un élément de menu séparé selon la version de PrestaShop).
-   **Actions et paramètres disponibles :** Cet écran présente généralement une grille ou un tableau où vous pouvez définir différents frais de paiement à la livraison en fonction du transporteur sélectionné. Vous pouvez ajouter, modifier ou supprimer ces règles de frais spécifiques au transporteur.
    -   **Sélection du transporteur :** Choisissez un transporteur spécifique.
    -   **Type de frais :** Sélectionnez si les frais sont un montant fixe ou un pourcentage.
    -   **Valeur des frais :** Saisissez le montant ou le pourcentage.
    -   **Règle de taxe :** Appliquez une règle de taxe spécifique aux frais de paiement à la livraison de ce transporteur.
-   **Effet des modifications :** Lorsqu'un client sélectionne un transporteur pour lequel vous avez défini des frais de paiement à la livraison spécifiques ici, ces frais remplaceront les frais de paiement à la livraison généraux définis dans la configuration principale du module. Cela permet une tarification hautement personnalisée.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Accédez à cet écran si vous devez facturer des frais de paiement à la livraison différents en fonction du coursier qui livre le colis.
    2.  Cliquez sur "Ajouter de nouveaux frais de transporteur" (ou un bouton similaire).
    3.  Sélectionnez le transporteur, définissez le type de frais (montant/pourcentage), la valeur et la règle de taxe.
    4.  Enregistrez vos modifications.
    5.  Vérifiez la liste pour vous assurer que tous les frais spécifiques au transporteur sont correctement définis.
-   **Scénario / exemple de marchand :** Votre service postal national facture 2 € fixes pour le paiement à la livraison, mais un coursier express privé facture 3 % de la valeur de la commande. Vous utiliseriez cet écran pour définir ces frais distincts pour chaque transporteur.

#### 2.2.2 AdminCodProCarriersRangeFeesController : Frais de paiement à la livraison spécifiques au transporteur et à la fourchette de total

-   **Nom de l'écran et emplacement du menu :** Back Office > Modules > Gestionnaire de modules > Rechercher "Paiement à la livraison avec récapitulatif de commande" > Cliquer sur "Configurer" > Rechercher un onglet ou un lien intitulé "Frais par fourchette" ou similaire.
-   **Actions et paramètres disponibles :** Cet écran offre un niveau de contrôle des frais encore plus avancé. Vous pouvez définir des frais de paiement à la livraison qui varient non seulement par transporteur, mais aussi par la *valeur totale du panier du client*. Cela est souvent présenté sous forme de grille où vous définissez des fourchettes (par exemple, "Total de la commande de 0 € à 50 €", "Total de la commande de 50 € à 100 €").
    -   **Sélection du transporteur :** Choisissez un transporteur spécifique.
    -   **Total minimum de la commande :** La limite inférieure de la fourchette de valeur de la commande.
    -   **Total maximum de la commande :** La limite supérieure de la fourchette de valeur de la commande.
    -   **Type de frais :** Montant fixe ou pourcentage.
    -   **Valeur des frais :** Le montant ou le pourcentage pour ce transporteur et cette fourchette de total de commande spécifiques.
    -   **Règle de taxe :** Appliquez une règle de taxe spécifique.
-   **Effet des modifications :** Ces frais basés sur des fourchettes ont la priorité sur les frais de paiement à la livraison généraux et les frais simples spécifiques au transporteur. Ils permettent des stratégies de tarification très dynamiques.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Utilisez cet écran pour les structures de frais de paiement à la livraison les plus complexes.
    2.  Cliquez sur "Ajouter de nouveaux frais par fourchette" (ou similaire).
    3.  Sélectionnez le transporteur, définissez le total minimum et maximum de la commande pour cette règle.
    4.  Spécifiez le type de frais, la valeur et la règle de taxe pour cette fourchette particulière.
    5.  Enregistrez et répétez pour toutes les fourchettes et transporteurs nécessaires.
-   **Scénario / exemple de marchand :** Pour un transporteur spécifique, vous pourriez facturer des frais de paiement à la livraison de 3 € pour les commandes inférieures à 50 €, mais des frais de 2 % pour les commandes comprises entre 50 € et 200 €, et des frais fixes de 5 € pour les commandes supérieures à 200 €. Cet écran vous permet de configurer une telle tarification échelonnée.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
|---|---|---|---|
| **Configuration du module** | Désactiver le paiement à la livraison pour des transporteurs spécifiques | Non (tous activés) | Restreindre la disponibilité du paiement à la livraison par transporteur choisi. |
| | Comment inclure les frais ? | Inclure comme produit séparé | Détermine comment les frais de paiement à la livraison apparaissent dans le panier/la commande. "Produit séparé" pour la clarté. |
| | Statut de la commande après achat avec le module de paiement à la livraison | En attente de validation du paiement à la livraison | Définit le statut initial de la commande ; "En attente de validation du paiement à la livraison" est recommandé pour la précision. |
| | Afficher un récapitulatif supplémentaire avant la confirmation | Activé | **CRITIQUE :** Affiche le récapitulatif légal avant confirmation. **Activé** pour la conformité. |
| | Valeur minimale du panier | Vide / 0 | Valeur minimale de la commande pour le paiement à la livraison. Définir si les petites commandes ne sont pas rentables. |
| | Valeur maximale du panier | Vide / 0 | Valeur maximale de la commande pour le paiement à la livraison. Définir pour atténuer les risques sur les grosses commandes. |
| | Type de frais de paiement à la livraison | Montant | Choisir si les frais sont fixes ou basés sur un pourcentage. |
| | Valeur des frais de paiement à la livraison (Pourcentage) | 0 | Pourcentage du total de la commande pour les frais de paiement à la livraison. |
| | Valeur des frais de paiement à la livraison (Montant) | 0 | Montant monétaire fixe pour les frais de paiement à la livraison. |
| | Frais de paiement à la livraison minimum | 0 | Assure qu'un minimum de frais est facturé, même si le pourcentage est faible. |
| | Frais de paiement à la livraison maximum | 0 | Plafonne les frais de paiement à la livraison pour éviter qu'ils ne deviennent trop élevés. |
| | Appliquer la taxe aux frais de paiement à la livraison | Non | Détermine si la taxe est appliquée aux frais de paiement à la livraison. Consulter les lois fiscales locales. |
| | Règle de taxe pour les frais de paiement à la livraison | (Aucune) | Sélectionne la règle de taxe si "Appliquer la taxe" est activé. |
| | Sélecteur CSS pour le total du panier | Vide | Avancé : Sélecteur CSS pour l'affichage du total du panier. Laisser vide sauf en cas de problèmes. |
| | Sélecteur CSS pour le sous-total du panier | Vide | Avancé : Sélecteur CSS pour l'affichage du sous-total du panier. Laisser vide sauf en cas de problèmes. |
| | Sélecteur CSS pour les frais de port du panier | Vide | Avancé : Sélecteur CSS pour l'affichage des frais de port. Laisser vide sauf en cas de problèmes. |
| | Logo de paiement à la livraison | Vide | Télécharger un logo personnalisé pour l'option de paiement à la livraison. |
| **AdminCodProCarriersFees** | Frais spécifiques au transporteur | N/A | Définir les frais de paiement à la livraison qui varient par transporteur. |
| **AdminCodProCarriersRangeFees** | Frais spécifiques au transporteur et à la fourchette | N/A | Définir les frais de paiement à la livraison qui varient par transporteur ET par fourchette de total de commande. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : L'option de paiement à la livraison n'apparaît pas pour les clients.**
R1 : Vérifiez les points suivants :
    *   **Module activé :** Le module "Paiement à la livraison avec récapitulatif de commande" est-il activé dans **Modules > Gestionnaire de modules** ?
    *   **Restrictions de paiement :** Allez dans **Paramètres de la boutique > Paramètres de commande > Paiement** (ou **Paiement > Préférences** dans les versions antérieures). Assurez-vous que "Paiement à la livraison avec récapitulatif de commande" n'est pas restreint par groupe de clients, devise ou pays.
    *   **Restrictions de transporteur :** Dans la configuration du module, vérifiez "Désactiver le paiement à la livraison pour des transporteurs spécifiques". Le transporteur choisi par le client est-il accidentellement coché ?
    *   **Restrictions de valeur du panier :** Vérifiez "Valeur minimale du panier" et "Valeur maximale du panier" dans la configuration du module. Le panier du client se situe-t-il dans ces limites ?
    *   **Zones géographiques :** Assurez-vous que le module est activé pour le pays du client dans **Paramètres de la boutique > Paramètres de commande > Paiement > Restrictions par zone/pays**.

**Q2 : Les frais de paiement à la livraison n'apparaissent pas ou ne sont pas calculés correctement.**
R2 :
    *   **Paramètres des frais :** Vérifiez à nouveau vos paramètres "Type de frais de paiement à la livraison" (Pourcentage/Montant) et "Valeur des frais de paiement à la livraison" dans la configuration principale du module.
    *   **Frais de transporteur/fourchette :** Si vous utilisez `AdminCodProCarriersFees` ou `AdminCodProCarriersRangeFees`, assurez-vous que les règles sont correctement définies pour le transporteur et le total de la commande spécifiques. Ces règles spécifiques remplacent les paramètres généraux.
    *   **Règles de taxe :** Si "Appliquer la taxe aux frais de paiement à la livraison" est activé, assurez-vous qu'une règle de taxe valide est sélectionnée.
    *   **Cache :** Videz votre cache PrestaShop (**Paramètres avancés > Performances > Vider le cache**). Parfois, d'anciennes données peuvent empêcher la mise à jour des frais.

**Q3 : La page de récapitulatif avant confirmation ne s'affiche pas, ou la commande passe directement à la confirmation.**
R3 :
    *   **Paramètre "Afficher un récapitulatif supplémentaire avant la confirmation" :** Dans la configuration principale du module, assurez-vous que ce paramètre est **Activé**. C'est crucial pour que la page de récapitulatif apparaisse.
    *   **Compatibilité du thème :** Bien que le module soit conçu pour être compatible, certains thèmes fortement personnalisés peuvent interférer. Si la page de récapitulatif ne s'affiche toujours pas, passez temporairement au thème PrestaShop par défaut pour exclure un conflit de thème. Si cela fonctionne sur le thème par défaut, contactez le développeur de votre thème ou un expert PrestaShop.

**Q4 : Les frais de paiement à la livraison n'apparaissent pas sur la facture PDF.**
R4 :
    *   **Le module est actif :** Assurez-vous que le module est activé.
    *   **Génération de facture :** Régénérez la facture PDF pour une commande passée avec paiement à la livraison *après* que le module ait été correctement configuré. Les anciennes factures pourraient ne pas refléter les nouveaux paramètres.
    *   **Version de PrestaShop :** Assurez-vous que votre version de PrestaShop est entièrement prise en charge. Bien que le module vise une large compatibilité, des versions très anciennes ou très récentes peuvent présenter des bizarreries d'affichage mineures.

**Q5 : Comment puis-je modifier le texte "Paiement à la livraison" ou la description des frais ?**
R5 :
    *   **Traductions :** Allez dans **International > Traductions**. Sélectionnez "Traductions des modules installés", choisissez votre thème, puis sélectionnez "Paiement à la livraison avec récapitulatif de commande". Vous pouvez ensuite trouver et modifier toutes les chaînes traduisibles utilisées par le module.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture
Le module "Paiement à la livraison avec récapitulatif de commande" (`codpro`) est un module de paiement PrestaShop standard suivant le modèle MVC (Model-View-Controller). Il étend `PaymentModule` et utilise divers hooks PrestaShop pour injecter son option de paiement, afficher le récapitulatif avant confirmation et gérer le statut de la commande et les frais. Il utilise des valeurs de configuration stockées dans `ps_configuration` pour ses paramètres et inclut des contrôleurs d'administration personnalisés pour la gestion avancée des frais. Le module calcule et affiche dynamiquement les frais de paiement à la livraison, en les intégrant dans le panier et les totaux de commande.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office
-   `controllers/front/index.php`
    *   **Nom de la classe :** `CodProIndexModuleFrontController` (probable, basé sur la convention de nommage des fichiers)
    *   **Classe parente :** `ModuleFrontController`
    *   **Responsabilité :** Ce contrôleur pourrait être un espace réservé ou gérer le routage initial pour les composants front-office du module. Étant donné le contrôleur `validation.php`, `index.php` pourrait ne pas avoir de route directe visible par l'utilisateur, mais pourrait être utilisé pour la logique interne du module ou les redirections.
-   `controllers/front/validation.php`
    *   **Nom de la classe :** `CodProValidationModuleFrontController`
    *   **Classe parente :** `ModuleFrontController`
    *   **Responsabilité :** C'est le contrôleur critique pour le traitement de la confirmation finale de la commande. Il reçoit les données POST de la page de récapitulatif avant confirmation, valide la commande, crée la commande dans PrestaShop et redirige le client vers la page de confirmation de commande (`paymentReturn`). Il gère la logique d'application des frais de paiement à la livraison à la commande.

#### Contrôleurs d'administration Back-Office
-   `controllers/admin/AdminCodProCarriersFees.php`
    *   **Nom de la classe :** `AdminCodProCarriersFeesController`
    *   **Classe parente :** `ModuleAdminController`
    *   **Nom de l'onglet :** Probablement un sous-onglet sous la configuration principale du module ou une entrée de menu personnalisée.
    *   **Entité gérée :** Gère les entrées de configuration liées aux frais de paiement à la livraison spécifiques au transporteur.
    *   **Responsabilité :** Fournit l'interface (un `HelperList` ou `HelperForm` basé sur les modèles `AdminController`) permettant aux administrateurs de définir, modifier et supprimer les frais de paiement à la livraison spécifiques aux transporteurs individuels. Il gère les opérations CRUD pour ces règles de frais.
-   `controllers/admin/AdminCodProCarriersRangeFees.php`
    *   **Nom de la classe :** `AdminCodProCarriersRangeFeesController`
    *   **Classe parente :** `ModuleAdminController`
    *   **Nom de l'onglet :** Probablement un sous-onglet sous la configuration principale du module.
    *   **Entité gérée :** Gère les entrées dans la table `codprototal` (ou similaire, basée sur les clés de configuration `CODPRO_MOD_MAXCART_V` et `CODPRO_MOD_MINCART_V`).
    *   **Responsabilité :** Fournit l'interface permettant aux administrateurs de définir, modifier et supprimer les frais de paiement à la livraison qui dépendent à la fois du transporteur sélectionné et de la valeur totale du panier du client (c'est-à-dire les frais basés sur des fourchettes). Il gère les opérations CRUD pour ces règles de frais complexes.
-   `controllers/admin/index.php`
    *   **Nom de la classe :** (Pas une classe de contrôleur typique, généralement une redirection ou une mesure de sécurité)
    *   **Classe parente :** N/A
    *   **Responsabilité :** Souvent une mesure de sécurité pour empêcher la liste directe des répertoires ou pour rediriger vers la configuration principale du module. Il contient généralement un simple `header('Location: ../../index.php?controller=AdminModules&token=...')` ou `die('Forbidden');`.

### 4.3 Classes et modèles de base (`classes/`)
Les informations du module fournies n'indiquent aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que la logique de base du module, la gestion des données et potentiellement les définitions `ObjectModel` (si des tables personnalisées sont utilisées au-delà de `ps_configuration`) sont encapsulées directement dans le fichier `codpro.php` principal ou gérées via les `ObjectModel` standard de PrestaShop comme `Order` et `Cart`.

### 4.4 Actifs JavaScript (`views/js/`)

-   `codpro/views/js/adminCodProCarriersFees.js`
    *   **Portée :** Back-office (AdminCodProCarriersFeesController)
    *   **Responsabilité :** Gère probablement les interactions dynamiques sur la page d'administration des frais spécifiques au transporteur. Cela pourrait inclure des appels AJAX pour ajouter/modifier des frais, la validation de formulaires ou la mise à jour de l'affichage de la liste des frais.
-   `codpro/views/js/adminCodProDashboard.js`
    *   **Portée :** Back-office (potentiellement la page de configuration principale du module si elle inclut des analyses)
    *   **Responsabilité :** Compte tenu des clés de configuration `CODPRO_ANALYTICS_`, ce script est probablement responsable du rendu des graphiques, diagrammes ou autres données analytiques liées aux commandes en paiement à la livraison au sein de l'interface back-office du module. Il pourrait utiliser une bibliothèque de graphiques (par exemple, Chart.js) et effectuer des requêtes AJAX pour récupérer des données.
-   `codpro/views/js/codpro-checkout.js`
    *   **Portée :** Front-office (Page de paiement)
    *   **Responsabilité :** C'est un script crucial pour l'expérience front-office. Il écoute les changements dans le processus de paiement (par exemple, sélection du paiement à la livraison comme méthode de paiement, changement de transporteur, mise à jour de la quantité du panier). Il met à jour dynamiquement les affichages du total du panier, du sous-total et des frais de port (en utilisant les sélecteurs CSS définis dans la configuration du module) pour refléter les frais de paiement à la livraison calculés. Il peut également gérer la redirection vers la page de récapitulatif avant confirmation.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `codpro/views/css/admin_codpro.css`
    *   **Portée :** Back-office (Pages d'administration liées au module)
    *   **Responsabilité :** Fournit le style pour les formulaires de configuration du module, les listes et potentiellement tout élément de tableau de bord personnalisé au sein du back office de PrestaShop. Assure une interface d'administration cohérente et conviviale.
    *   **Sélecteurs de classe CSS clés :** Cible probablement les éléments des modèles `HelperForm` ou `HelperList` du module, ou les éléments personnalisés spécifiques aux vues d'administration du module.
-   `codpro/views/css/codpro.css`
    *   **Portée :** Front-office (Page de paiement, récapitulatif avant confirmation, détails de la commande)
    *   **Responsabilité :** Style l'affichage de l'option de paiement à la livraison, la page de récapitulatif avant confirmation et l'affichage des frais de paiement à la livraison sur les pages de détails de commande et les factures. Assure que les éléments du module s'intègrent visuellement au thème de la boutique.
    *   **Sélecteurs de classe CSS clés :** Ciblera des éléments tels que le bloc d'option de paiement à la livraison, le tableau récapitulatif, les lignes de frais et potentiellement toute alerte ou message personnalisé introduit par le module. Les développeurs peuvent les remplacer dans le `custom.css` de leur thème ou en utilisant des sélecteurs plus spécifiques.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)
-   `codpro/views/templates/hook/confirmation.tpl`
    *   **Hook :** `displayPaymentReturn`
    *   **Sortie :** Contenu affiché sur la page de confirmation de commande après une commande réussie en paiement à la livraison. Peut inclure un message rappelant au client le paiement en espèces à la livraison.
-   `codpro/views/templates/hook/displayAdminOrder16.tpl`
    *   **Hook :** `displayAdminOrder` (pour PrestaShop 1.6.x)
    *   **Sortie :** Ajoute des informations spécifiques liées au paiement à la livraison (par exemple, détails des frais) à la page de visualisation de la commande dans le back office de PrestaShop 1.6.
-   `codpro/views/templates/hook/displayAdminOrder17.tpl`
    *   **Hook :** `displayAdminOrder` (pour PrestaShop 1.7.x, 8.x, 9.x)
    *   **Sortie :** Similaire à `displayAdminOrder16.tpl`, mais adapté à la vue de commande du back office de PrestaShop 1.7+, affichant les détails du paiement à la livraison.
-   `codpro/views/templates/hook/displayOrderDetail.tpl`
    *   **Hook :** `displayOrderDetail`
    *   **Sortie :** Affiche des informations spécifiques au paiement à la livraison (par exemple, la ventilation des frais) sur la page de détails de commande du client en front office.
-   `codpro/views/templates/hook/payment.tpl`
    *   **Hook :** `paymentOptions` ou `displayPaymentOptions`
    *   **Sortie :** Rend le bloc d'option de paiement "Paiement à la livraison" sur la page de paiement, y compris le logo du module et les frais affichés.
-   `codpro/views/templates/hook/pdf.tpl`
    *   **Hook :** `displayPDFInvoice`
    *   **Sortie :** Injecte les frais de paiement à la livraison comme ligne ou résumé dans les factures PDF générées.

#### Modèles Front-office (`views/templates/front/`)
-   `codpro/views/templates/front/validation.tpl`
    *   **Sortie :** C'est le modèle de la page cruciale de récapitulatif de commande avant confirmation. Il affiche le récapitulatif complet du panier, l'adresse de livraison, les coûts totaux (y compris les frais de paiement à la livraison) et le bouton final "Confirmer la commande". Ce modèle est rendu par le contrôleur frontal `validation.php`.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données
Le module utilise principalement la table standard `ps_configuration` pour stocker ses paramètres (par exemple, `CODPRO_MOD_MAXCART`, `CODPRO_FEEPAY`, `CODPRO_CHARGEP_V`, etc.).

Basé sur le contrôleur `AdminCodProCarriersRangeFeesController` gérant l'entité `codprototal`, il est très probable que le module crée une table de base de données personnalisée, probablement nommée `ps_codprototal` (ou similaire, suivant la convention de préfixe `ps_` de PrestaShop).
-   **`ps_codprototal` (Table probable) :**
    *   **Objectif :** Stocke les règles de frais de paiement à la livraison basées sur des fourchettes, liant les transporteurs, les totaux min/max du panier, les montants/pourcentages des frais et les règles de taxe.
    *   **Champs probables :** `id_codprototal` (PK), `id_carrier`, `min_total`, `max_total`, `fee_type` (par exemple, 'amount', 'percentage'), `fee_value`, `id_tax_rule`.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
|---|---|---|
| `displayHeader` | Dans la section `<head>` de chaque page. | Pour inclure les actifs CSS/JS du module (par exemple, `codpro-checkout.js`, `codpro.css`) sur les pages front-office pertinentes. |
| `paymentOptions` | Pendant le processus de paiement, lorsque les options de paiement sont listées. | Pour injecter l'option de paiement "Paiement à la livraison" dans la liste. |
| `displayPaymentOptions` | (Alias ou alternative à `paymentOptions` pour certaines versions) | Pour injecter l'option de paiement "Paiement à la livraison" dans la liste. |
| `paymentReturn` | Sur la page de confirmation de commande après une commande réussie. | Pour afficher un message de confirmation spécifique aux commandes en paiement à la livraison. |
| `displayAdminOrder` | Sur la page de détails de la commande dans le back office de PrestaShop. | Pour afficher les détails des frais de paiement à la livraison et les informations sur la méthode de paiement pour l'administrateur. |
| `displayOrderDetail` | Sur la page de détails de commande du client en front office. | Pour afficher les détails des frais de paiement à la livraison au client. |
| `displayPDFInvoice` | Lorsqu'une facture PDF est générée. | Pour s'assurer que les frais de paiement à la livraison sont correctement inclus et affichés sur la facture. |
| `ActionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration est initialisé et que ses actifs multimédias sont définis. | Pour inclure les actifs CSS/JS spécifiques à l'administration du module (par exemple, `admin_codpro.css`, `adminCodProCarriersFees.js`, `adminCodProDashboard.js`). |

## 5. Support officiel et mises à jour
Pour les dernières mises à jour du module, les corrections de bugs et le support officiel des développeurs, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Assurez-vous d'utiliser toujours la version du module compatible avec votre installation PrestaShop spécifique.
