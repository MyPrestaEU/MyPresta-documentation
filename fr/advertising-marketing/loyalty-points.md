---
title: "Points de fidélité - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Points de fidélité par MyPresta.eu."
sidebar:
  label: "Points de fidélité - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Loyalty points sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/loyalty-points/)
>
> ---


# Points de fidélité

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes pour ce module.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Pour accéder à la configuration du module, allez dans **Modules > Gestionnaire de modules** dans votre back office PrestaShop, recherchez « Points de fidélité » et cliquez sur le bouton « Configurer ».

Cet écran vous permet de définir les règles fondamentales de votre programme de fidélité.

#### **Taux d'échange des points de fidélité**

- **Ce que fait ce paramètre :** Ce paramètre crucial définit le nombre de points de fidélité qu'un client gagne pour un montant spécifique dépensé dans votre boutique. C'est la base de votre programme de fidélité.
- **Effet de la modification de ce paramètre :**
  - *Si défini sur « 1 point pour chaque 10 € dépensés » :* Un client dépensant 50 € gagnera 5 points.
  - *Si défini sur « 1 point pour chaque 5 € dépensés » :* Un client dépensant 50 € gagnera 10 points.
  - Une valeur plus élevée (par exemple, 10 €) signifie que les clients gagnent des points plus lentement, tandis qu'une valeur plus basse (par exemple, 1 €) signifie qu'ils gagnent des points plus rapidement.
- **Valeur recommandée :** Cela dépend de vos marges bénéficiaires et de l'incitation client souhaitée. Un point de départ courant est « 1 point pour chaque 10 € dépensés » ou « 1 point pour chaque 5 € dépensés ».
- **Scénario / exemple de marchand :** Si la valeur moyenne de votre commande est de 50 € et que vous souhaitez que les clients se sentent rapidement récompensés, « 1 point pour chaque 5 € dépensés » pourrait être préférable. Si vos marges sont plus serrées, « 1 point pour chaque 10 € dépensés » pourrait être plus durable.

#### **Valeur des points de fidélité**

- **Ce que fait ce paramètre :** Ce paramètre détermine la valeur monétaire de chaque point de fidélité lorsqu'un client décide de les convertir en bon de réduction.
- **Effet de la modification de ce paramètre :**
  - *Si défini sur « 1 point = 0,10 € » :* Un client avec 100 points peut obtenir un bon de 10 €.
  - *Si défini sur « 1 point = 0,05 € » :* Un client avec 100 points peut obtenir un bon de 5 €.
  - Une valeur plus élevée rend les points plus attrayants et précieux pour le client, mais coûte plus cher à votre boutique en termes de réductions.
- **Valeur recommandée :** Cela doit être équilibré avec le « Taux d'échange des points de fidélité » pour garantir que votre programme est à la fois attrayant pour les clients et financièrement viable pour votre entreprise. Un ratio courant est que 10 points (gagnés en dépensant 100 € si le taux est de 1 point pour 10 €) valent 1 €.
- **Scénario / exemple de marchand :** Si vous donnez 1 point pour chaque 10 € dépensés, et que 1 point vaut 0,10 €, alors un client dépensant 100 € obtient 10 points, qui peuvent être échangés contre un bon de 1 €. Cela signifie qu'il obtient une réduction de 1 % sur ses achats. Vous pourriez augmenter cela à 2 % ou 3 % pour être plus compétitif.

#### **Points minimums à convertir**

- **Ce que fait ce paramètre :** Cela définit le nombre minimum de points de fidélité qu'un client doit accumuler avant d'être autorisé à les convertir en bon de réduction.
- **Effet de la modification de ce paramètre :**
  - *Si défini sur « 50 points » :* Les clients ne peuvent pas échanger de points tant qu'ils n'en ont pas au moins 50.
  - *Si défini sur « 10 points » :* Les clients peuvent échanger des points beaucoup plus tôt.
  - Un minimum plus élevé encourage les clients à effectuer plus d'achats pour atteindre le seuil, augmentant potentiellement leur valeur à vie. Un minimum plus bas offre une gratification plus rapide.
- **Valeur recommandée :** Définissez une valeur qui encourage les achats répétés sans être si élevée que les clients la trouvent inatteignable. 50 à 100 points est une bonne fourchette de départ, selon votre taux de gain de points.
- **Scénario / exemple de marchand :** Si 1 point est gagné pour 10 €, et que 50 points sont nécessaires, un client doit dépenser 500 € pour obtenir son premier bon. Cela garantit qu'il est un client engagé avant de recevoir une réduction significative.

#### **Validité du bon (jours)**

- **Ce que fait ce paramètre :** Cela définit le nombre de jours pendant lesquels un bon de réduction généré à partir de points de fidélité sera valide.
- **Effet de la modification de ce paramètre :**
  - *Si défini sur « 30 jours » :* Le bon expire 30 jours après sa génération.
  - *Si défini sur « 365 jours » :* Le bon est valide pendant une année complète.
  - Une période de validité plus courte encourage les clients à utiliser leur bon plus tôt, stimulant des achats répétés plus rapides. Une période plus longue offre plus de flexibilité mais pourrait retarder les achats.
- **Valeur recommandée :** 30 à 90 jours est une fourchette courante. Cela crée un sentiment d'urgence sans être trop restrictif.
- **Scénario / exemple de marchand :** Une période de validité de 60 jours donne aux clients suffisamment de temps pour trouver quelque chose qu'ils veulent acheter sans laisser le bon inutilisé indéfiniment.

#### **Activer le programme de fidélité**

- **Ce que fait ce paramètre :** C'est un interrupteur principal pour activer ou désactiver l'ensemble du programme de points de fidélité.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'activé (OUI) :* Le programme de fidélité est actif. Les clients gagneront des points, verront les informations sur les points sur les pages produits et dans leur panier, et pourront gérer les points dans leur compte.
  - *Lorsqu'il est désactivé (NON) :* Le programme de fidélité est inactif. Aucun point ne sera gagné, aucune information sur les points ne sera affichée, et les clients ne pourront pas échanger de points. Les points existants seront conservés mais inaccessibles jusqu'à ce que le programme soit réactivé.
- **Valeur recommandée :** OUI, une fois que vous avez configuré tous les autres paramètres.
- **Scénario / exemple de marchand :** Vous pourriez le désactiver temporairement pour la maintenance ou si vous menez une campagne promotionnelle différente qui entre en conflit avec le programme de fidélité.

#### **Afficher les points de fidélité sur la page produit**

- **Ce que fait ce paramètre :** Cela contrôle si les informations sur les points de fidélité gagnés pour un produit sont affichées sur les pages produits individuelles de votre boutique.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'activé (OUI) :* Les clients verront un texte comme « Gagnez X points avec cet achat » sur chaque page produit.
  - *Lorsqu'il est désactivé (NON) :* Cette information n'apparaîtra pas sur les pages produits.
- **Valeur recommandée :** OUI. L'affichage de cette information de manière proéminente aide les clients à comprendre la proposition de valeur de votre programme de fidélité et encourage les achats.
- **Scénario / exemple de marchand :** Maintenir cette option activée garantit que les clients sont toujours conscients des récompenses qu'ils peuvent gagner, ce qui peut être un facteur décisif dans leur achat.

#### **Afficher les points de fidélité dans le panier**

- **Ce que fait ce paramètre :** Cela contrôle si le total des points de fidélité à gagner pour la commande actuelle est affiché dans le récapitulatif du panier.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'activé (OUI) :* Les clients verront un résumé des points qu'ils gagneront pour le contenu de leur panier actuel.
  - *Lorsqu'il est désactivé (NON) :* Cette information n'apparaîtra pas dans le panier.
- **Valeur recommandée :** OUI. Cela sert d'incitation finale avant le paiement, rappelant aux clients les avantages futurs de leur achat.
- **Scénario / exemple de marchand :** L'affichage des points dans le panier peut réduire l'abandon en ajoutant une autre couche de valeur à l'achat, surtout si le client hésite.

#### **Description du programme de points de fidélité**

- **Ce que fait ce paramètre :** Cela vous permet de fournir une description ou une explication personnalisée de votre programme de fidélité. Ce texte sera généralement affiché dans la section « Mon compte » du client où il gère ses points.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est rempli de texte :* Les clients verront votre message personnalisé expliquant le fonctionnement du programme, ses avantages ou toute règle spécifique.
  - *Lorsqu'il est laissé vide :* Aucune description personnalisée ne sera affichée, laissant potentiellement les clients avec moins d'informations.
- **Valeur recommandée :** Fournissez une description claire, concise et engageante. Expliquez comment les points sont gagnés, leur valeur et comment les échanger.
- **Scénario / exemple de marchand :** « Gagnez 1 point pour chaque 10 € dépensés ! Accumulez 50 points et obtenez un bon de 5 € pour votre prochain achat. C'est notre façon de vous remercier d'être un client fidèle ! »

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Taux d'échange des points de fidélité | 1 point pour chaque 10 € dépensés | Définit le nombre de points gagnés par unité monétaire dépensée. |
| Configuration du module | Valeur des points de fidélité | 1 point = 0,10 € | Définit la valeur monétaire de chaque point lorsqu'il est converti en bon d'achat. |
| Configuration du module | Points minimums à convertir | 50 points | Définit le nombre minimum de points requis avant qu'un client puisse les échanger contre un bon d'achat. |
| Configuration du module | Validité du bon (jours) | 60 jours | Durée de validité d'un bon généré. |
| Configuration du module | Activer le programme de fidélité | OUI | Interrupteur principal pour activer/désactiver l'ensemble du programme de fidélité. |
| Configuration du module | Afficher les points de fidélité sur la page produit | OUI | Affiche les informations de gain de points sur les pages produits individuelles. |
| Configuration du module | Afficher les points de fidélité dans le panier | OUI | Affiche le total des points à gagner dans le récapitulatif du panier. |
| Configuration du module | Description du programme de points de fidélité | Texte personnalisé | Fournit une explication détaillée du programme aux clients. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes clients ne voient pas les informations sur les points de fidélité sur les pages produits ou dans le panier. Qu'est-ce qui ne va pas ?**
R :

1.  **Vérifiez « Activer le programme de fidélité » :** Assurez-vous que ce paramètre est défini sur OUI dans la configuration du module.
2.  **Vérifiez les paramètres d'affichage :** Vérifiez que « Afficher les points de fidélité sur la page produit » et « Afficher les points de fidélité dans le panier » sont tous deux définis sur OUI.
3.  **Videz le cache :** Allez dans **Paramètres avancés > Performances** dans votre back office PrestaShop et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures). Parfois, les modifications n'apparaissent pas tant que le cache n'est pas actualisé.
4.  **Compatibilité du thème :** Bien que le module soit conçu pour la compatibilité, les thèmes personnalisés peuvent parfois remplacer les hooks d'affichage par défaut. Si vider le cache ne fonctionne pas, contactez le support MyPresta.eu.

**Q : Les clients gagnent des points, mais ils ne peuvent pas les convertir en bons d'achat.**
R :

1.  **Vérifiez « Points minimums à convertir » :** Assurez-vous que le client a accumulé au moins le nombre de points spécifié dans ce paramètre. Si le minimum est de 50 et qu'il n'en a que 45, il ne verra pas l'option de conversion.
2.  **Processus de génération de bons :** Guidez vos clients vers leur section « Mon compte », puis vers la section « Mes points de fidélité » (ou similaire), où ils devraient trouver une option pour convertir leurs points en bon d'achat.

**Q : Un client a généré un bon, mais il ne fonctionne pas ou a disparu.**
R :

1.  **Vérifiez « Validité du bon (jours) » :** Le bon a peut-être expiré si le client a attendu trop longtemps pour l'utiliser.
2.  **Code du bon :** Assurez-vous que le client saisit correctement le code du bon lors du paiement.
3.  **Statut du bon :** Dans le back office PrestaShop, allez dans **Catalogue > Réductions > Règles panier**. Recherchez le code du bon généré. Vérifiez ses dates de validité, son montant minimum et s'il a déjà été utilisé.

**Q : Puis-je ajouter ou supprimer manuellement des points de fidélité pour un client ?**
R : La version actuelle du module ne fournit pas d'interface directe dans le back office pour ajuster manuellement les points de fidélité des clients. Les points sont automatiquement calculés en fonction des commandes. Si vous devez effectuer des ajustements manuels, vous devrez peut-être envisager un développement personnalisé ou contacter le support MyPresta.eu pour des options avancées.

**Q : La description du programme de fidélité ne s'affiche pas correctement dans plusieurs langues.**
R : Lorsque vous définissez la « Description du programme de points de fidélité », assurez-vous d'utiliser le sélecteur de langue en haut à droite du champ de texte pour fournir des traductions pour toutes les langues activées dans votre boutique. Si vous ne saisissez du texte que dans une seule langue, il n'apparaîtra que dans cette langue.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Vue d'ensemble de l'architecture

Le module `Loyalty points` (`myprestaloyalty`) suit une architecture de module PrestaShop standard, exploitant principalement la classe `Module` pour sa fonctionnalité principale et sa configuration. Il s'intègre au front office via divers hooks pour afficher les informations de fidélité et fournit une page de compte client dédiée pour la gestion des points. Le module n'introduit pas de tables de base de données personnalisées ni de classes `ObjectModel`, s'appuyant sur la `Configuration` de PrestaShop pour les paramètres et étendant potentiellement les données client ou de commande existantes via des hooks.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :

  - `myprestaloyalty/controllers/front/default.php`
    - **Nom de la classe et classe parente** : `MyPrestaLoyaltyDefaultModuleFrontController` étendant `ModuleFrontController`.
    - **Responsabilité** : Ce contrôleur sert probablement de solution de repli ou de point d'entrée générique pour les actions front-office liées au module. Il pourrait gérer les requêtes initiales ou les redirections si un contrôleur plus spécifique n'est pas trouvé. Étant donné le contrôleur `index.php`, `default.php` pourrait être moins critique ou servir un objectif spécifique moins courant.
  - `myprestaloyalty/controllers/front/index.php`
    - **Nom de la classe et classe parente** : `MyPrestaLoyaltyIndexModuleFrontController` étendant `ModuleFrontController`.
    - **Responsabilité** : C'est le contrôleur front-office principal du module. Il est responsable de l'affichage des informations sur les points de fidélité du client et de la gestion de la logique de conversion des points en bons d'achat. Il récupère probablement les points actuels du client, calcule les valeurs potentielles des bons et traite la demande de génération de bons. Il rend le template `loyalty.tpl`.
- **Contrôleurs d'administration Back-Office** : Aucun identifié. Toute la configuration est gérée via la méthode `getContent()` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)

Aucune classe ou modèle personnalisé (extensions `ObjectModel`) n'a été identifié dans l'inventaire du module fourni. Le module gère probablement la logique des points de fidélité directement dans le fichier principal `myprestaloyalty.php` et via la `Configuration` de PrestaShop pour les paramètres.

### 4.4 Actifs JavaScript (`views/js/`)

- `myprestaloyalty/views/js/admin_manual_customer_search.js`
  - **Portée** : Back-office.
  - **Description** : Ce script suggère une fonctionnalité de recherche manuelle de clients dans le panneau d'administration. Bien qu'aucun contrôleur d'administration n'ait été explicitement listé, ce fichier JS implique qu'il pourrait y avoir une interface d'administration (peut-être intégrée à une page PrestaShop existante ou à un formulaire personnalisé dans `getContent()`) où un administrateur peut rechercher des clients, éventuellement pour afficher ou gérer leurs points de fidélité (bien que la modification directe des points ne soit pas confirmée par la description du module). Il utilise probablement AJAX pour récupérer les données client.
- `myprestaloyalty/views/js/myprestaloyalty.js`
  - **Portée** : Front-office.
  - **Description** : Il s'agit du JavaScript principal du front-office pour le module. Il gère probablement les interactions dynamiques sur la page de fidélité du client (`loyalty.tpl`), telles que :
    - L'affichage des points actuels et des valeurs potentielles des bons.
    - La gestion de l'événement de clic pour le bouton « Convertir les points en bon d'achat ».
    - L'envoi de requêtes AJAX au contrôleur frontal `index.php` pour traiter la génération du bon.
    - La mise à jour de l'interface utilisateur pour afficher le code du bon nouvellement généré ou les messages de succès/erreur.

### 4.5 Feuilles de style CSS (`views/css/`)

- `myprestaloyalty/views/css/myprestaloyalty.css`
  - **Portée** : Front-office (et potentiellement certains éléments du back-office si des styles communs sont utilisés).
  - **Description** : Cette feuille de style fournit le style visuel des composants front-office du module. Cela inclut :
    - L'affichage des points de fidélité sur les pages produits.
    - Le résumé des points dans le panier.
    - La mise en page et le style de la section « Mes points de fidélité » dans le compte client, y compris le solde des points, l'historique et le formulaire de génération de bons.
    - Sélecteurs de classe CSS clés que les développeurs peuvent surcharger dans leur thème : Recherchez les classes préfixées par `myprestaloyalty-` ou similaire, telles que `.myprestaloyalty-product-points`, `.myprestaloyalty-cart-summary`, `.myprestaloyalty-account-section`, `.myprestaloyalty-voucher-form`, etc.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates d'administration (`views/templates/admin/`)** :

  - `myprestaloyalty/views/templates/admin/advert.tpl`
    - **Description** : Ce template est probablement utilisé pour afficher du contenu promotionnel ou des publicités de MyPresta.eu dans la page de configuration du module dans le back office. C'est une pratique courante pour les développeurs de modules d'inclure de tels éléments.
  - `myprestaloyalty/views/templates/admin/_configure/helpers/form/form.tpl`
    - **Description** : Ce template est un template d'aide PrestaShop standard utilisé pour rendre le formulaire de configuration du module. Il n'est pas unique à ce module mais est inclus pour garantir que la page de configuration (`getContent()`) s'affiche correctement, potentiellement avec des champs personnalisés ou un style spécifique.
- **Templates Front-office (`views/templates/front/`)** :

  - `myprestaloyalty/views/templates/front/loyalty.tpl`
    - **Description** : C'est le template principal de la page dédiée « Mes points de fidélité » du client, rendu par le `MyPrestaLoyaltyIndexModuleFrontController`. Il affiche le solde actuel des points du client, l'historique des points gagnés et dépensés, et l'interface pour convertir les points en bons de réduction.
- **Templates de hook (`views/templates/hook/`)** :

  - `myprestaloyalty/views/templates/hook/my-account.tpl`
    - **Hook** : `displayCustomerAccount` (ou similaire, par exemple, `displayMyAccountBlock`).
    - **Description** : Ce template ajoute un lien ou un bloc à la page « Mon compte » du client, le dirigeant vers la page dédiée aux points de fidélité du module (`loyalty.tpl`).
  - `myprestaloyalty/views/templates/hook/product.tpl`
    - **Hook** : `displayProductExtraContent`, `displayProductButtons`, ou `displayProductActions` (selon la version de PrestaShop et le thème).
    - **Description** : Ce template affiche les informations sur le nombre de points de fidélité qu'un client gagnera en achetant le produit spécifique sur sa page produit.
  - `myprestaloyalty/views/templates/hook/shopping-cart.tpl`
    - **Hook** : `displayShoppingCartFooter`, `displayCartExtraProductActions`, ou `displayReassurance` (selon la version de PrestaShop et le thème).
    - **Description** : Ce template affiche un résumé du total des points de fidélité que le client gagnera pour les articles actuellement dans son panier.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** : Aucune table SQL personnalisée n'est créée par ce module. Tous les paramètres du module sont stockés dans la table `ps_configuration` de PrestaShop, généralement avec des clés préfixées par `MYPRESTALOYALTY_`.

  - Exemples de clés de configuration : `MYPRESTALOYALTY_EXCHANGE_RATE`, `MYPRESTALOYALTY_POINT_VALUE`, `MYPRESTALOYALTY_MIN_POINTS`, `MYPRESTALOYALTY_VOUCHER_VALIDITY`, `MYPRESTALOYALTY_ENABLED`, `MYPRESTALOYALTY_DISPLAY_PRODUCT`, `MYPRESTALOYALTY_DISPLAY_CART`, `MYPRESTALOYALTY_DESCRIPTION`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Pour inclure les actifs CSS et JS pour le front-office. |
| `displayCustomerAccount` | Sur la page « Mon compte » du client. | Pour ajouter un lien vers la section « Mes points de fidélité ». |
| `displayProductExtraContent` (ou similaire) | Sur la page produit, près des détails/boutons du produit. | Pour afficher les points gagnés pour le produit spécifique. |
| `displayShoppingCartFooter` (ou similaire) | Dans le récapitulatif du panier. | Pour afficher le total des points gagnés pour la commande actuelle. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | Pour calculer et attribuer des points de fidélité au client en fonction du total de la commande. |
| `displayLeftColumn` / `displayRightColumn` / `displayFooter` (facultatif) | Dans les zones de colonne/pied de page respectives. | Potentiellement utilisé pour afficher un lien rapide ou un résumé du programme de fidélité, si configuré. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support technique dédié pour le module « Points de fidélité », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour aider les marchands et les développeurs avec toutes les questions ou problèmes concernant la fonctionnalité et l'intégration du module.
