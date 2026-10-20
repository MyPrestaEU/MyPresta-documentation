---
title: "Paiement à l'enlèvement en magasin (+frais) - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Paiement à l'enlèvement en magasin (+frais) par MyPresta.eu."
sidebar:
  label: "Paiement à l'enlèvement en magasin (+frais) - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Cash on pickup at store (+fee) sur MyPresta.eu](https://mypresta.eu/modules/payment-process/cash-on-pickup-at-store-fee.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/payment/cash-on-pickup-at-store-fee/)
>
> ---


# Paiement à l'enlèvement en magasin (+frais)

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises et sont habituellement activées par défaut sur la plupart des environnements d'hébergement.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal où vous définirez toutes les options pour votre méthode de paiement « Paiement à l'enlèvement en magasin ».

#### **Paramètres généraux**

- **Logo de paiement**

  - **Ce que fait ce paramètre :** Vous permet de télécharger une image personnalisée (logo) qui sera affichée à côté de l'option de paiement « Paiement à l'enlèvement en magasin » lors du processus de commande. Cela aide les clients à identifier visuellement la méthode de paiement.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'une image est téléchargée :* L'image choisie apparaîtra à côté du nom de la méthode de paiement sur la page de sélection du paiement.
    - *Lorsqu'aucune image n'est téléchargée :* Un logo par défaut ou aucun logo ne sera affiché, selon votre thème.
  - **Valeur recommandée :** Téléchargez un logo clair et petit qui représente « enlèvement » ou « espèces » pour une meilleure reconnaissance.
  - **Scénario / exemple de marchand :** Vous pourriez télécharger une icône de sac de courses ou de devanture de magasin pour faire ressortir l'option de paiement.
- **Titre de la méthode de paiement** (Clé de configuration : `COPPRO_TITLE`)

  - **Ce que fait ce paramètre :** Définit le nom de la méthode de paiement tel qu'il apparaît aux clients lors du processus de commande.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est modifié :* Le nouveau titre sera affiché sur la page de sélection du paiement, la confirmation de commande et les factures.
  - **Valeur recommandée :** « Paiement à l'enlèvement en magasin » ou « Payer lors du retrait en magasin ».
  - **Scénario / exemple de marchand :** Si vous avez un nom de marque spécifique pour votre service de retrait, vous pouvez l'utiliser ici, par exemple, « Retrait local MyStore ».
- **Statut de commande pour les nouvelles commandes** (Clé de configuration : `COPPRO_OS`)

  - **Ce que fait ce paramètre :** Sélectionne le statut initial qu'une commande aura dans votre Back Office lorsqu'un client choisit « Paiement à l'enlèvement en magasin ».
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur « En attente de paiement à l'enlèvement » :* Les nouvelles commandes se verront automatiquement attribuer ce statut, ce qui vous permettra d'identifier facilement les commandes qui doivent être préparées pour l'enlèvement et le paiement.
  - **Valeur recommandée :** Créez un statut de commande personnalisé comme « En attente de paiement à l'enlèvement » ou « Prêt pour l'enlèvement » pour plus de clarté.
  - **Scénario / exemple de marchand :** Vous pourriez le définir sur « En attente de paiement à l'enlèvement » afin que votre personnel sache qu'il doit préparer les articles mais ne pas les expédier.
- **Statut de commande lorsque payé** (Clé de configuration : `COPPRO_OS_READY`)

  - **Ce que fait ce paramètre :** Sélectionne le statut de commande vers lequel une commande doit être modifiée une fois que le client a payé et retiré ses articles avec succès dans votre magasin.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur « Paiement accepté » :* Une fois que vous avez mis à jour manuellement la commande dans le Back Office après l'enlèvement et le paiement, elle passera à ce statut, la marquant comme terminée.
  - **Valeur recommandée :** « Paiement accepté » ou « Livré ».
  - **Scénario / exemple de marchand :** Après que le client ait retiré et payé, vous changeriez le statut de la commande en « Paiement accepté » pour finaliser la transaction dans votre système.

#### **Restrictions de valeur du panier**

- **Valeur minimale totale du panier** (Clé de configuration : `COPPRO_MINCART`, `COPPRO_MINCART_V`)

  - **Ce que fait ce paramètre :** Vous permet de définir une valeur totale minimale pour qu'une commande soit éligible au « Paiement à l'enlèvement en magasin ». Si le total du panier est inférieur à cette valeur, la méthode de paiement ne sera pas affichée.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'une valeur est définie (par exemple, 10 €) :* Les clients avec un total de panier inférieur à 10 € ne verront pas « Paiement à l'enlèvement en magasin » comme option.
    - *Lorsqu'il est laissé vide ou à 0 :* Il n'y aura pas de restriction de valeur minimale du panier.
  - **Valeur recommandée :** Laissez vide ou à 0, sauf si vous avez des raisons opérationnelles spécifiques d'exiger un minimum.
  - **Scénario / exemple de marchand :** Vous pourriez définir un minimum de 5 € pour éviter les très petites commandes qui ne sont pas rentables pour votre personnel à traiter pour l'enlèvement.
- **Valeur maximale totale du panier** (Clé de configuration : `COPPRO_MAXCART`, `COPPRO_MAXCART_V`)

  - **Ce que fait ce paramètre :** Vous permet de définir une valeur totale maximale pour qu'une commande soit éligible au « Paiement à l'enlèvement en magasin ». Si le total du panier dépasse cette valeur, la méthode de paiement ne sera pas affichée.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'une valeur est définie (par exemple, 500 €) :* Les clients avec un total de panier supérieur à 500 € ne verront pas « Paiement à l'enlèvement en magasin » comme option.
    - *Lorsqu'il est laissé vide ou à 0 :* Il n'y aura pas de restriction de valeur maximale du panier.
  - **Valeur recommandée :** Laissez vide ou à 0, sauf si vous avez des préoccupations spécifiques concernant la gestion de très gros paiements en espèces.
  - **Scénario / exemple de marchand :** Vous pourriez définir un maximum de 1000 € si vous n'êtes pas à l'aise avec le fait que le personnel gère de très grosses sommes d'argent au point de retrait.

#### **Configuration des frais / réductions**

- **Appliquer une réduction (pas de frais)** (Clé de configuration : `COPPRO_DISCOUNT`)

  - **Ce que fait ce paramètre :** Il s'agit d'un interrupteur à bascule. S'il est activé, le module appliquera une *réduction* au total de la commande au lieu de *frais* lorsque « Paiement à l'enlèvement en magasin » est sélectionné.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* La valeur que vous définissez pour « Valeur de la charge en pourcentage » ou « Valeur de la charge fixe » sera soustraite du total de la commande.
    - *Lorsqu'il est désactivé :* La valeur que vous définissez sera ajoutée au total de la commande en tant que frais.
  - **Valeur recommandée :** Désactivé (pour appliquer des frais) si vous souhaitez couvrir les coûts opérationnels, ou Activé (pour appliquer une réduction) si vous souhaitez inciter aux enlèvements.
  - **Scénario / exemple de marchand :** Vous pourriez l'activer et définir une réduction de 5 % pour encourager les clients à retirer leurs commandes, ce qui vous ferait économiser sur les frais d'expédition.
- **Valeur des frais près de la méthode de paiement** (Clé de configuration : `COPPRO_FEEPAY`)

  - **Ce que fait ce paramètre :** Il s'agit d'un interrupteur à bascule. S'il est activé, le montant des frais ou de la réduction sera affiché directement à côté du nom de la méthode de paiement sur la page de commande.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clients verront « Paiement à l'enlèvement en magasin (+ X,XX € de frais) » ou « Paiement à l'enlèvement en magasin (- X,XX € de réduction) ».
    - *Lorsqu'il est désactivé :* Seul le nom de la méthode de paiement sera affiché, et les frais/réduction seront appliqués au total du panier sans mention explicite à côté de la méthode.
  - **Valeur recommandée :** Activé, pour la transparence avec vos clients.
  - **Scénario / exemple de marchand :** Vous voulez que les clients soient pleinement conscients de tout coût ou économie supplémentaire à l'avance, vous activez donc cela.
- **Charge en pourcentage** (Clé de configuration : `COPPRO_CHARGEP`, `COPPRO_CHARGEP_V`)

  - **Ce que fait ce paramètre :** Vous permet d'appliquer des frais ou une réduction basés sur un pourcentage du total de la commande.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé et qu'une valeur est saisie (par exemple, 5) :* Des frais de 5 % (ou une réduction si « Appliquer une réduction » est activé) seront ajoutés/soustraits du total de la commande.
    - *Lorsqu'il est désactivé :* Aucun frais/réduction basé sur un pourcentage ne sera appliqué.
  - **Valeur recommandée :** Désactivé, sauf si vous souhaitez spécifiquement une charge basée sur un pourcentage. S'il est activé, une valeur entre 1 et 10 % est courante pour les frais, ou 2 et 10 % pour les réductions.
  - **Scénario / exemple de marchand :** Vous souhaitez facturer des frais de 3 % pour couvrir le coût du traitement des espèces et de la manutention, vous activez donc cela et saisissez « 3 ».
- **Charge fixe** (Clé de configuration : `COPPRO_CHARGEA`, `COPPRO_CHARGEA_V`)

  - **Ce que fait ce paramètre :** Vous permet d'appliquer un montant fixe de frais ou de réduction au total de la commande.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé et qu'une valeur est saisie (par exemple, 2,50) :* Des frais fixes de 2,50 € (ou une réduction si « Appliquer une réduction » est activé) seront ajoutés/soustraits du total de la commande.
    - *Lorsqu'il est désactivé :* Aucun frais/réduction de montant fixe ne sera appliqué.
  - **Valeur recommandée :** Activé, avec un petit montant fixe (par exemple, 1,00 € - 3,00 €) si vous souhaitez des frais simples et cohérents.
  - **Scénario / exemple de marchand :** Vous souhaitez facturer des frais fixes de 2 € pour toutes les commandes à retirer, vous activez donc cela et saisissez « 2,00 ».

#### **Paramètres d'affichage avancés et de compatibilité**

- **Résumé du panier** (Clé de configuration : `COPPRO_CARTPRESENTER`)

  - **Ce que fait ce paramètre :** Il s'agit d'un interrupteur à bascule qui contrôle si les frais/réduction sont explicitement affichés dans le bloc de résumé du panier (par exemple, dans la colonne de droite ou en bas de la page du panier).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les frais/réduction seront détaillés dans le résumé du panier, montrant comment cela affecte le total.
    - *Lorsqu'il est désactivé :* Les frais/réduction seront appliqués au total mais pourraient ne pas être explicitement détaillés dans le résumé du panier avant l'étape de paiement.
  - **Valeur recommandée :** Activé, pour une transparence totale.
  - **Scénario / exemple de marchand :** Vous souhaitez que les clients voient la ligne « Frais d'enlèvement » dans le résumé de leur panier avant même d'atteindre l'étape de paiement, vous activez donc cela.
- **Résumé de l'adresse** (Clé de configuration : `COPPRO_HOWFEE`)

  - **Ce que fait ce paramètre :** Ce paramètre contrôle où les frais/réduction sont affichés dans la section de résumé de l'adresse du processus de commande.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les frais/réduction seront visibles dans le résumé de l'adresse, généralement près du coût d'expédition.
    - *Lorsqu'il est désactivé :* Les frais/réduction seront appliqués mais non explicitement affichés dans le résumé de l'adresse.
  - **Valeur recommandée :** Activé, pour la cohérence et la transparence.
  - **Scénario / exemple de marchand :** Vous souhaitez que les frais soient visibles à plusieurs étapes du processus de commande, y compris le résumé de l'adresse, vous activez donc cela.
- **Activé** (Clé de configuration : `COPPRO_EVENTLISTENER`)

  - **Ce que fait ce paramètre :** Il s'agit d'un interrupteur général pour activer ou désactiver la fonctionnalité principale du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* La méthode de paiement « Paiement à l'enlèvement en magasin » sera active et disponible pour les clients.
    - *Lorsqu'il est désactivé :* La méthode de paiement sera masquée et indisponible.
  - **Valeur recommandée :** Activé, une fois que vous avez configuré tous les autres paramètres.
  - **Scénario / exemple de marchand :** Vous avez terminé de configurer le module et êtes prêt à offrir cette méthode de paiement, vous l'activez donc.
- **Désactivé** (Clé de configuration : `PS_ONE_PAGE_CHECKOUT_ENABLED`)

  - **Ce que fait ce paramètre :** Ce paramètre est probablement lié à la compatibilité avec le processus de commande en une page de PrestaShop. Il pourrait s'agir d'un paramètre hérité ou d'un indicateur d'affichage.
  - **Effet de la modification de ce paramètre :** Il s'agit probablement d'un indicateur en lecture seule ou d'un paramètre qui devrait généralement être laissé à sa valeur par défaut, sauf indication contraire du support.
  - **Valeur recommandée :** Laisser par défaut.
  - **Scénario / exemple de marchand :** Aucune interaction directe du marchand n'est attendue.
- **Sélecteurs CSS pour les éléments du panier** (Clés de configuration : `COPPRO_CSS_CART_TOTAL`, `COPPRO_CSS_CART_SUBTOTAL`, `COPPRO_CSS_CART_SHIPPING`)

  - **Ce que font ces paramètres :** Ces champs vous permettent de spécifier les sélecteurs CSS pour les éléments de total, sous-total et frais de port de votre thème. Ceci est crucial pour que le module mette correctement à jour ces valeurs lorsqu'une taxe/réduction est appliquée, surtout si votre thème utilise des sélecteurs non standard.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est correctement configuré :* Le module mettra à jour avec précision les totaux du panier, les sous-totaux et les frais de port affichés sur la page de paiement pour refléter la taxe/réduction.
    - *Lorsqu'il est mal configuré ou laissé vide :* Les totaux du panier pourraient ne pas se mettre à jour correctement, ce qui entraînerait une confusion pour le client ou des prix affichés incorrects.
  - **Valeur recommandée :** Laissez vide initialement. Si vous remarquez que les totaux du panier ne se mettent pas à jour correctement après avoir sélectionné « Paiement à l'enlèvement en magasin », vous devrez peut-être consulter le développeur de votre thème ou un webmaster pour trouver les sélecteurs CSS corrects.
  - **Scénario / exemple de marchand :** Après avoir installé le module, vous remarquez que le prix total ne change pas sur la page de paiement lorsque les frais d'enlèvement sont appliqués. Votre webmaster inspecterait le code de votre thème pour trouver les sélecteurs CSS corrects (par exemple, `#cart-total-price`, `.product-total-price`) et les saisirait ici.

#### **Règles d'exclusion**

- **Exclure des produits** (Clé de configuration : `COPPRO_EXCL_PRODUCTS`)

  - **Ce que fait ce paramètre :** Vous permet d'empêcher l'achat de produits spécifiques avec la méthode de paiement « Paiement à l'enlèvement en magasin ». Si un produit exclu se trouve dans le panier, cette méthode de paiement ne sera pas disponible.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque des produits sont sélectionnés :* Si un client ajoute l'un de ces produits à son panier, l'option « Paiement à l'enlèvement en magasin » disparaîtra des méthodes de paiement.
    - *Lorsqu'aucun produit n'est sélectionné :* Tous les produits sont éligibles.
  - **Valeur recommandée :** Laissez vide, sauf si vous avez des produits spécifiques qui ne peuvent pas être retirés ou payés en espèces.
  - **Scénario / exemple de marchand :** Vous vendez des articles de très grande valeur (par exemple, des bijoux coûteux) pour lesquels vous préférez n'accepter que des paiements en ligne sécurisés. Vous ajouteriez ces produits à la liste d'exclusion.
- **Exclure des catégories** (Clé de configuration : `COPPRO_EXCL_CAT`)

  - **Ce que fait ce paramètre :** Similaire à l'exclusion de produits, cela vous permet d'empêcher l'achat de catégories entières de produits avec « Paiement à l'enlèvement en magasin ».
  - **Effet de la modification de ce paramètre :**
    - *Lorsque des catégories sont sélectionnées :* Si un client ajoute un produit de ces catégories à son panier, l'option « Paiement à l'enlèvement en magasin » ne sera pas disponible.
    - *Lorsqu'aucune catégorie n'est sélectionnée :* Toutes les catégories sont éligibles.
  - **Valeur recommandée :** Laissez vide, sauf si vous avez des catégories spécifiques qui ne conviennent pas à l'enlèvement.
  - **Scénario / exemple de marchand :** Vous avez une catégorie « Téléchargements numériques ». Étant donné que ces articles ne nécessitent pas d'enlèvement physique, vous excluriez cette catégorie.
- **Activer les exclusions** (Clé de configuration : `COPPRO_EXCL_ENABLE`)

  - **Ce que fait ce paramètre :** Il s'agit d'un interrupteur principal pour activer ou désactiver toutes les règles d'exclusion de produits et de catégories que vous avez configurées.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Vos règles d'exclusion de produits et de catégories seront actives.
    - *Lorsqu'il est désactivé :* Tous les produits et catégories seront éligibles au « Paiement à l'enlèvement en magasin », quelles que soient vos sélections dans les listes d'exclusion.
  - **Valeur recommandée :** Activé, si vous avez défini des règles d'exclusion.
  - **Scénario / exemple de marchand :** Vous avez configuré des exclusions pour certains produits, et vous souhaitez que ces règles soient actives, vous activez donc cet interrupteur.

#### **Paramètres d'analyse et internes**

- **Paramètres d'analyse** (Clés de configuration : `COPPRO_ANALYTICS_DEFAULT_CHART`, `COPPRO_ANALYTICS_PERIOD`, `COPPRO_ANALYTICS_IMPACT_DAYS`, `COPPRO_ANALYTICS_CHART_WEEKS`, `COPPRO_ANALYTICS_CHART_MONTHS`, `COPPRO_ANALYTICS_CHART_YEARS`)

  - **Ce que font ces paramètres :** Ce sont des paramètres internes liés à toutes les fonctionnalités d'analyse ou de rapport que le module pourrait avoir, vous permettant de configurer la manière dont les données sont collectées ou affichées pour un usage interne.
  - **Effet de la modification de ce paramètre :** Ceux-ci n'affectent généralement que les vues de rapport du Back Office, pas l'expérience client du front-office.
  - **Valeur recommandée :** Laissez par défaut, sauf si vous avez des besoins de rapport spécifiques.
  - **Scénario / exemple de marchand :** Aucune interaction directe du marchand n'est attendue pour les opérations quotidiennes.
- **Date de modification des frais / instantané** (Clés de configuration : `COPPRO_FEE_CHANGE_DATE`, `COPPRO_FEE_CHANGE_SNAPSHOT`)

  - **Ce que font ces paramètres :** Ce sont probablement des paramètres internes du module pour suivre la dernière modification des configurations de frais ou pour stocker un instantané des paramètres de frais précédents. Ceci est généralement à des fins d'audit ou de débogage.
  - **Effet de la modification de ce paramètre :** Aucun impact direct sur l'expérience client.
  - **Valeur recommandée :** Laissez par défaut.
  - **Scénario / exemple de marchand :** Aucune interaction directe du marchand n'est attendue.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Ce module ne semble pas avoir de contrôleurs d'administration personnalisés dédiés au-delà de sa page de configuration principale. Tous les paramètres sont gérés via la méthode `getContent()` du fichier de module principal.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Logo de paiement | Télécharger une image pertinente | Identification visuelle de la méthode de paiement. |
| Configuration du module | Titre de la méthode de paiement | « Paiement à l'enlèvement en magasin » | Nom affiché aux clients pour l'option de paiement. |
| Configuration du module | Statut de commande pour les nouvelles commandes | Personnalisé « En attente de paiement à l'enlèvement » | Statut initial des commandes utilisant cette méthode. |
| Configuration du module | Statut de commande lorsque payé | « Paiement accepté » / « Livré » | Statut final après que le client a payé et retiré. |
| Configuration du module | Valeur minimale totale du panier | Vide / 0 | Valeur minimale de commande pour que cette méthode de paiement apparaisse. |
| Configuration du module | Valeur maximale totale du panier | Vide / 0 | Valeur maximale de commande pour que cette méthode de paiement apparaisse. |
| Configuration du module | Appliquer une réduction (pas de frais) | Désactivé | Détermine si une réduction ou des frais sont appliqués. |
| Configuration du module | Valeur des frais près de la méthode de paiement | Activé | Affiche les frais/réduction à côté du nom de la méthode de paiement. |
| Configuration du module | Charge en pourcentage | Désactivé | Applique des frais/réduction basés sur un pourcentage. |
| Configuration du module | Valeur de la charge en pourcentage | 0 | La valeur en pourcentage pour la charge/réduction. |
| Configuration du module | Charge fixe | Activé (avec valeur) | Applique des frais/réduction de montant fixe. |
| Configuration du module | Valeur de la charge fixe | par exemple, 2,00 | Le montant fixe pour la charge/réduction. |
| Configuration du module | Résumé du panier | Activé | Affiche les frais/réduction détaillés dans le résumé du panier. |
| Configuration du module | Résumé de l'adresse | Activé | Affiche les frais/réduction dans le résumé de l'adresse. |
| Configuration du module | Activé | Activé | Active/désactive la méthode de paiement. |
| Configuration du module | Exclure des produits | Vide | Empêche l'utilisation de cette méthode pour des produits spécifiques. |
| Configuration du module | Exclure des catégories | Vide | Empêche l'utilisation de cette méthode pour les produits de catégories spécifiques. |
| Configuration du module | Activer les exclusions | Activé (si des règles sont définies) | Interrupteur principal pour les règles d'exclusion de produits/catégories. |
| Configuration du module | Sélecteurs CSS (Total du panier, Sous-total, Frais de port) | Vide (ajuster si nécessaire) | Assure des mises à jour correctes du total du panier avec le thème. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q1 : La méthode de paiement « Paiement à l'enlèvement en magasin » n'apparaît pas lors du processus de commande.**
R :

- **Vérifiez le paramètre « Activé » :** Allez dans Modules > Gestionnaire de modules > Configurer pour « Paiement à l'enlèvement en magasin (+frais) » et assurez-vous que l'interrupteur principal « Activé » est sur ON.
- **Vérifiez les restrictions de valeur du panier :** Vérifiez vos paramètres « Valeur minimale totale du panier » et « Valeur maximale totale du panier ». Si le total du panier du client se situe en dehors de cette plage, la méthode n'apparaîtra pas.
- **Vérifiez les exclusions :** Si vous avez configuré des exclusions de produits ou de catégories, assurez-vous que le panier actuel ne contient aucun article exclu. Vérifiez également si « Activer les exclusions » est sur ON.
- **Vérifiez les géo-restrictions :** Assurez-vous que la méthode de paiement n'est pas restreinte par pays ou devise dans les paramètres généraux de paiement de PrestaShop (Paiement > Préférences).
- **Videz le cache :** Parfois, le cache de PrestaShop peut empêcher les modifications d'apparaître immédiatement. Allez dans **Paramètres avancés > Performance** et cliquez sur « Vider le cache ».

**Q2 : Les frais/réduction ne sont pas appliqués ou affichés correctement sur la page de commande.**
R :

- **Vérifiez les paramètres de frais/réduction :** Vérifiez que « Charge en pourcentage » ou « Charge fixe » est activé, et que la valeur correspondante est correctement saisie. Assurez-vous également que « Appliquer une réduction (pas de frais) » est défini comme prévu.
- **Vérifiez les paramètres d'affichage :** Assurez-vous que « Valeur des frais près de la méthode de paiement », « Résumé du panier » et « Résumé de l'adresse » sont tous activés pour une visibilité maximale.
- **Sélecteurs CSS (Avancé) :** Si votre thème est fortement personnalisé, le module pourrait ne pas être en mesure de trouver les éléments corrects à mettre à jour. Vérifiez les paramètres « Sélecteurs CSS pour les éléments du panier ». Vous pourriez avoir besoin d'un webmaster pour identifier les sélecteurs corrects pour les éléments de total, sous-total et frais de port de votre thème.

**Q3 : Comment puis-je changer le texte « Paiement à l'enlèvement en magasin » en autre chose ?**
R :

- Vous pouvez modifier le nom d'affichage directement dans la configuration du module. Recherchez le paramètre « Titre de la méthode de paiement » sur la page de configuration principale.
- Pour les boutiques multilingues, assurez-vous de sélectionner la bonne langue dans le menu déroulant en haut de la page de configuration du module (si disponible) ou utilisez l'outil de traduction de PrestaShop (International > Traductions > Traductions des modules installés).

**Q4 : Puis-je restreindre cette méthode de paiement à certains transporteurs ou groupes de clients uniquement ?**
R :

- **Transporteurs :** Oui, les préférences de paiement de base de PrestaShop vous permettent de restreindre les méthodes de paiement par transporteur. Allez dans **Paiement > Préférences** dans votre Back Office. Dans la section « Restrictions par transporteur », assurez-vous que « Paiement à l'enlèvement en magasin (+frais) » est sélectionné pour les transporteurs avec lesquels vous souhaitez l'autoriser (par exemple, votre transporteur « Retrait local »).
- **Groupes de clients :** De même, dans **Paiement > Préférences**, vous pouvez restreindre les méthodes de paiement par groupe de clients. Assurez-vous que les groupes de clients pertinents (par exemple, « Client », « Visiteur ») sont sélectionnés pour cette méthode de paiement.

**Q5 : Quel statut de commande dois-je utiliser pour les commandes « Paiement à l'enlèvement » ?**
R :

- Il est fortement recommandé de créer un statut de commande personnalisé dans PrestaShop (Commandes > Statuts de commande) spécifiquement pour les commandes « Paiement à l'enlèvement », tel que « En attente de paiement à l'enlèvement » ou « Prêt pour l'enlèvement ». Cela vous aide à identifier facilement ces commandes dans votre Back Office.
- Ensuite, dans la configuration du module, définissez « Statut de commande pour les nouvelles commandes » sur ce statut personnalisé.
- Une fois que le client a payé et retiré, modifiez manuellement le statut de la commande en « Paiement accepté » ou « Livré » sur la page des détails de la commande.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module `Paiement à l'enlèvement en magasin (+frais)` (`coppro`) est un module de paiement PrestaShop standard suivant le modèle MVC. Il étend `PaymentModule` et s'intègre principalement via des hooks pour afficher les options de paiement, traiter la validation et afficher les informations de commande. Le module calcule dynamiquement les frais/réductions en fonction de la configuration et met à jour les totaux du panier via JavaScript sur le front-office. Il utilise `Configuration` pour le stockage des paramètres et n'introduit pas de classes `ObjectModel` personnalisées ni de tables de base de données.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :

  - `controllers/front/index.php`
    - Nom de la classe : `CopproIndexModuleFrontController` (étend probablement `ModuleFrontController`)
    - Responsabilité : Ce contrôleur pourrait servir de point d'entrée par défaut ou gérer les requêtes front-office générales liées au module qui ne s'intègrent pas dans des flux de paiement spécifiques. Compte tenu de son nom, il pourrait s'agir d'un contrôleur de secours ou d'affichage simple.
  - `controllers/front/store.php`
    - Nom de la classe : `CopproStoreModuleFrontController` (étend probablement `ModuleFrontController`)
    - Responsabilité : Gère potentiellement la logique liée aux emplacements des magasins ou aux points de retrait, bien que la description du module ne mentionne pas explicitement plusieurs emplacements de magasin. Il pourrait s'agir d'un espace réservé ou d'une future extension.
  - `controllers/front/validation.php`
    - Nom de la classe : `CopproValidationModuleFrontController` (étend probablement `ModuleFrontController`)
    - Responsabilité : C'est le contrôleur critique pour le traitement des paiements. Il reçoit la confirmation de paiement du processus de commande, valide la commande et redirige le client vers la page de confirmation de commande. Il interagit avec le module principal `coppro.php` pour finaliser la commande avec le statut correct et les frais/réductions appliqués.
- **Contrôleurs d'administration Back-Office** :

  - Ce module n'inclut aucun contrôleur d'administration personnalisé. Toute la configuration du Back Office est gérée directement dans la méthode `getContent()` du fichier de module principal `coppro.php`.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne semble pas définir de classes personnalisées dans un répertoire `classes/`. Sa logique principale réside dans le fichier de module principal `coppro.php`, qui étend `PaymentModule`.

### 4.4 Actifs JavaScript (`views/js/`)

- `coppro/lib/searchTool/views/js/autocomplete.js`
  - Portée : Probablement Back-office.
  - Responsabilité : Fournit une fonctionnalité d'autocomplétion, probablement pour la sélection de produits ou de catégories dans la configuration du module (par exemple, pour les listes d'exclusion). Il se lie aux champs de saisie et effectue des requêtes AJAX pour récupérer des suggestions.
- `coppro/views/js/adminCopproDashboard.js`
  - Portée : Back-office.
  - Responsabilité : Gère le JavaScript pour tout tableau de bord administratif ou fonctionnalités d'analyse dans la page de configuration du module. Il pourrait gérer le rendu des graphiques ou l'affichage des données.
- `coppro/views/js/adminCopproProductSearch.js`
  - Portée : Back-office.
  - Responsabilité : Gère spécifiquement l'interface de recherche de produits dans la configuration d'administration du module, probablement pour le paramètre « Exclure des produits ». Il gère la saisie de recherche, l'affichage des résultats et la sélection.
- `coppro/views/js/adminCopproSelector.js`
  - Portée : Back-office.
  - Responsabilité : Gère la logique de sélection pour divers éléments du panneau d'administration, éventuellement pour les catégories ou d'autres listes configurables.
- `coppro/views/js/coppro-checkout.js`
  - Portée : Front-office.
  - Responsabilité : C'est le script principal du front-office. Il écoute les changements dans la sélection de la méthode de paiement pendant le processus de commande. Lorsque « Paiement à l'enlèvement en magasin » est choisi, il met à jour dynamiquement le résumé du panier (total, sous-total, frais de port) pour refléter les frais ou la réduction calculés. Il utilise les sélecteurs CSS définis dans la configuration du module (`COPPRO_CSS_CART_TOTAL`, etc.) pour cibler et modifier les éléments du DOM. Il pourrait également gérer les appels AJAX pour recalculer les totaux si le backend est nécessaire.
- `coppro/views/js/copproBoMockConsole.js`
  - Portée : Back-office.
  - Responsabilité : Probablement un utilitaire de débogage ou de développement, éventuellement pour simuler la sortie de la console ou la journalisation dans le Back Office.

### 4.5 Feuilles de style CSS (`views/css/`)

- `coppro/lib/searchTool/views/css/autocomplete.css`
  - Portée : Back-office.
  - Responsabilité : Style les listes déroulantes d'autocomplétion et les champs de saisie de recherche utilisés dans la configuration d'administration.
- `coppro/views/css/admin_coppro.css`
  - Portée : Style du formulaire d'administration Back-office.
  - Responsabilité : Fournit un style spécifique pour la page de configuration du module dans le Back Office de PrestaShop, garantissant une interface cohérente et conviviale.
- `coppro/views/css/coppro.css`
  - Portée : Style client Front-office.
  - Responsabilité : Contient les styles pour l'affichage de l'option de paiement « Paiement à l'enlèvement en magasin », potentiellement pour le logo de paiement, le texte des frais/réduction, ou tout élément personnalisé introduit par le module sur la page de commande. Les développeurs peuvent remplacer ces styles dans le `custom.css` de leur thème ou dans un thème enfant.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **Modèles de hook (`views/templates/hook/`)** :

  - `coppro/views/templates/hook/confirmation.tpl`
    - Hook : Probablement `displayPaymentReturn` ou similaire.
    - Sorties : Contenu pour la page de confirmation de commande après une commande « Paiement à l'enlèvement » réussie, informant le client du paiement lors de l'enlèvement.
  - `coppro/views/templates/hook/displayAdminOrder16.tpl`
    - Hook : `displayAdminOrder` (pour PrestaShop 1.6.x).
    - Sorties : Informations ou actions supplémentaires liées aux commandes « Paiement à l'enlèvement » dans la page de détail de commande du Back Office pour PS 1.6.
  - `coppro/views/templates/hook/displayAdminOrder17.tpl`
    - Hook : `displayAdminOrder` (pour PrestaShop 1.7.x, 8.x, 9.x).
    - Sorties : Similaire à `displayAdminOrder16.tpl` mais adapté pour la page de détail de commande du Back Office de PS 1.7+, affichant potentiellement les instructions d'enlèvement ou les détails des frais.
  - `coppro/views/templates/hook/displayOrderDetail.tpl`
    - Hook : `displayOrderDetail`.
    - Sorties : Informations sur la méthode de paiement « Paiement à l'enlèvement » dans la page de détail de commande du front-office du client.
  - `coppro/views/templates/hook/payment.tpl`
    - Hook : `paymentOptions` (ou `displayPaymentOptions`).
    - Sorties : La structure HTML pour l'option de paiement « Paiement à l'enlèvement en magasin » sur la page de commande, y compris le logo de paiement, le titre et le texte des frais/réduction calculés dynamiquement.
- **Modèles d'administration (`views/templates/admin/`)** :

  - `coppro/lib/searchTool/views/scripts.tpl`
    - Hook : Probablement `actionAdminControllerSetMedia` ou inclus directement dans `getContent()`.
    - Sorties : Inclut les actifs JavaScript et CSS pour l'outil de recherche utilisé dans la configuration d'administration.
  - `coppro/views/templates/admin/productSearchTool.tpl`
    - Sorties : La structure HTML pour l'interface de recherche et de sélection de produits dans la configuration du module, utilisée pour le paramètre « Exclure des produits ».
  - `coppro/views/templates/admin/scopeSelector.tpl`
    - Sorties : HTML pour un sélecteur de portée générique, potentiellement utilisé pour les catégories ou d'autres listes filtrables dans la configuration d'administration.
- **Modèles Front-office (`views/templates/front/`)** :

  - `coppro/views/templates/front/validation.tpl`
    - Sorties : Contenu affiché par le `CopproValidationModuleFrontController` après la validation du paiement, généralement une redirection ou un simple message avant la page de confirmation finale.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** :
  Le module ne crée pas de tables de base de données personnalisées. Tous ses paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide des méthodes `Configuration::updateValue()` et `Configuration::get()`, avec des clés préfixées par `COPPRO_`.
  Exemples de clés de configuration :

  - `COPPRO_OS`
  - `COPPRO_OS_READY`
  - `COPPRO_MAXCART_V`
  - `COPPRO_MINCART_V`
  - `COPPRO_FEEPAY`
  - `COPPRO_DISCOUNT`
  - `COPPRO_CHARGEP_V`
  - `COPPRO_CHARGEA_V`
  - `COPPRO_EXCL_PRODUCTS`
  - `COPPRO_EXCL_CAT`
  - `COPPRO_TITLE`
  - `COPPRO_CARTPRESENTER`
  - `COPPRO_HOWFEE`
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Pour inclure les actifs CSS (`coppro.css`) et JavaScript (`coppro-checkout.js`) du front-office. |
| `displayPaymentOptions` | Pendant le processus de commande, pour lister les méthodes de paiement disponibles. | Pour afficher l'option de paiement « Paiement à l'enlèvement en magasin » avec son titre, son logo et les frais/réduction calculés. |
| `paymentOptions` | Alias de `displayPaymentOptions` (anciennes versions de PS). | Identique à `displayPaymentOptions`. |
| `displayPaymentReturn` | Sur la page de confirmation de commande après le paiement. | Pour afficher des instructions spécifiques ou des messages de confirmation pour les commandes « Paiement à l'enlèvement ». |
| `displayPDFInvoice` | Lorsqu'une facture PDF est générée. | Pour s'assurer que la méthode de paiement « Paiement à l'enlèvement en magasin » est correctement indiquée sur la facture. |
| `displayOrderDetail` | Sur la page de détail de commande du client dans le front-office. | Pour afficher la méthode de paiement choisie et tous les détails connexes. |
| `displayAdminOrder` | Sur la page de détail de commande dans le Back Office. | Pour afficher des informations supplémentaires ou des outils de gestion spécifiques aux commandes « Paiement à l'enlèvement » pour les administrateurs. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration charge ses actifs multimédias. | Pour inclure les actifs CSS (`admin_coppro.css`, `autocomplete.css`) et JavaScript (`adminCopproDashboard.js`, `adminCopproProductSearch.js`, `adminCopproSelector.js`, `autocomplete.js`) du Back-office pour la page de configuration du module. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | Pour effectuer toutes les actions post-validation, telles que la mise à jour du statut de la commande ou la journalisation des détails, spécifiques aux commandes « Paiement à l'enlèvement ». |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support technique officiel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant le module « Paiement à l'enlèvement en magasin (+frais) ».
