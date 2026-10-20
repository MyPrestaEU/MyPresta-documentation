---
title: "Happy Birthday Coupon - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Happy Birthday Coupon par MyPresta.eu."
sidebar:
  label: "Happy Birthday Coupon - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Happy Birthday Coupon sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/happy-birthday-coupon.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/happy-birthday-coupon/)
>
> ---


# Happy Birthday Coupon

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Assurez-vous que la fonctionnalité de tâche cron de votre serveur est activée pour l'envoi automatisé des coupons.

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Happy Birthday Coupon)

Ceci est l'écran de configuration principal où vous définissez comment vos coupons d'anniversaire seront générés et envoyés.

#### Paramètres généraux

-   **Jours avant l'anniversaire du client pour envoyer le coupon (bp\_daysbefore)**

    -   **Ce que fait ce paramètre :** Il détermine combien de jours *avant* l'anniversaire réel d'un client l'e-mail de coupon sera envoyé.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est réglé sur 0 :* Le coupon sera envoyé le jour de l'anniversaire du client.
        -   *Lorsqu'il est réglé sur 7 :* Le coupon sera envoyé 7 jours avant l'anniversaire du client. Cela leur donne une semaine pour planifier un achat.
    -   **Valeur recommandée :** `7` jours. Cela donne aux clients suffisamment de temps pour parcourir votre boutique et prendre une décision d'achat, plutôt que de le recevoir le jour même où ils pourraient être occupés.
    -   **Scénario / exemple marchand :** Vous souhaitez que les clients reçoivent leur cadeau d'anniversaire une semaine à l'avance afin qu'ils aient le temps de l'utiliser pour un achat spécial d'anniversaire. Régler ceci sur `7` garantit qu'ils reçoivent l'e-mail avec amplement de temps.
-   **Activer l'option newsletter (bpro\_nletter)**

    -   **Ce que fait ce paramètre :** Il contrôle si la fonctionnalité de coupon d'anniversaire est liée au statut d'abonnement à la newsletter du client.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé (OUI) :* Seuls les clients abonnés à votre newsletter recevront un coupon d'anniversaire.
        -   *Lorsqu'il est désactivé (NON) :* Tous les clients ayant une date de naissance valide dans leur compte recevront un coupon d'anniversaire, quel que soit leur abonnement à la newsletter.
    -   **Valeur recommandée :** `NON`. Pour maximiser l'impact et la portée, il est généralement préférable d'envoyer des coupons d'anniversaire à tous les clients ayant une date de naissance, car il s'agit d'un geste personnel. Cependant, si vous souhaitez récompenser spécifiquement les abonnés à la newsletter, réglez-le sur `OUI`.
    -   **Scénario / exemple marchand :** Vous souhaitez récompenser tous vos clients fidèles pour leur anniversaire, pas seulement ceux abonnés à votre newsletter. Vous régleriez ceci sur `NON`.
-   **Groupes de clients à inclure (birthdaypro\_groups)**

    -   **Ce que fait ce paramètre :** Il vous permet de sélectionner des groupes de clients spécifiques éligibles pour recevoir des coupons d'anniversaire.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque des groupes spécifiques sont sélectionnés :* Seuls les clients appartenant à ces groupes choisis recevront des coupons d'anniversaire.
        -   *Lorsqu'aucun groupe n'est sélectionné (ou que tous sont sélectionnés) :* Tous les clients (sous réserve d'autres paramètres comme l'option newsletter) seront éligibles.
    -   **Valeur recommandée :** Sélectionnez `Client` et tout autre groupe que vous souhaitez inclure. Évitez de sélectionner `Visiteur` ou `Invité` car ils n'ont généralement pas de comptes avec des dates de naissance.
    -   **Scénario / exemple marchand :** Vous avez un groupe "Clients VIP" et un groupe "Grossiste". Vous ne voulez envoyer des coupons d'anniversaire qu'à votre groupe "Client" régulier et aux "Clients VIP", mais pas à vos partenaires grossistes. Vous sélectionneriez "Client" et "Clients VIP" dans la liste.
-   **Liste des clients (Informationnel)**

    -   **Ce que fait ce paramètre :** Ce n'est pas un paramètre à modifier, mais une section informative qui affiche probablement une liste de clients ayant reçu ou étant éligibles pour des coupons d'anniversaire. Cela vous aide à surveiller l'activité du module.
    -   **Effet de la modification de ce paramètre :** Aucun effet direct car il s'agit d'une fonctionnalité d'affichage uniquement.
    -   **Valeur recommandée :** N/A
    -   **Scénario / exemple marchand :** Vous souhaitez voir rapidement quels clients ont des dates de naissance enregistrées et pourraient bientôt recevoir des coupons.

#### Paramètres du bon de réduction (Personnalisation avancée)

Le module permet une personnalisation étendue des bons de réduction générés. Ces paramètres reflètent les options standard des règles panier (bons de réduction) de PrestaShop.

-   **Préfixe du code de bon de réduction :** (par exemple, `ANNIVERSAIRE-`)

    -   **Ce que fait ce paramètre :** Définit un préfixe pour tous les codes de coupon d'anniversaire générés.
    -   **Effet de la modification de ce paramètre :** Tous les codes uniques commenceront par ce préfixe, ce qui les rendra facilement identifiables.
    -   **Valeur recommandée :** `ANNIVERSAIRE-` ou `BDP-`.
    -   **Scénario / exemple marchand :** Vous souhaitez distinguer facilement les coupons d'anniversaire des autres promotions dans votre historique de commandes.
-   **Type de réduction :** (par exemple, Pourcentage, Montant, Livraison gratuite)

    -   **Ce que fait ce paramètre :** Détermine le type de réduction que le coupon offre.
    -   **Effet de la modification de ce paramètre :**
        -   *Pourcentage :* Applique une réduction en pourcentage à la commande.
        -   *Montant :* Applique une réduction monétaire fixe.
        -   *Livraison gratuite :* Offre la livraison gratuite.
    -   **Valeur recommandée :** `Pourcentage` ou `Montant`, selon votre stratégie marketing.
    -   **Scénario / exemple marchand :** Vous souhaitez offrir une réduction de 15 % pour les anniversaires. Vous sélectionneriez `Pourcentage` et définiriez la valeur à `15`.
-   **Valeur de la réduction :** (par exemple, `15` pour un pourcentage, `10.00` pour un montant)

    -   **Ce que fait ce paramètre :** La valeur réelle de la réduction.
    -   **Effet de la modification de ce paramètre :** Impacte directement la réduction appliquée à la commande du client.
    -   **Valeur recommandée :** Une valeur attrayante mais également rentable pour votre boutique (par exemple, `10` pour 10 % ou `5.00` pour 5 €).
    -   **Scénario / exemple marchand :** Suite à l'exemple ci-dessus, vous saisiriez `15` ici.
-   **Montant minimum :**

    -   **Ce que fait ce paramètre :** Définit un montant d'achat minimum requis pour que le coupon soit valide.
    -   **Effet de la modification de ce paramètre :** Encourage les clients à dépenser davantage pour bénéficier de la réduction.
    -   **Valeur recommandée :** Un montant raisonnable qui encourage la vente incitative sans être prohibitif.
    -   **Scénario / exemple marchand :** Vous souhaitez que les clients dépensent au moins 50 € pour utiliser leur coupon d'anniversaire. Vous définiriez ceci à `50.00`.
-   **Période de validité :** (par exemple, `30` jours)

    -   **Ce que fait ce paramètre :** Définit le nombre de jours pendant lesquels le coupon est valide à partir de la date d'envoi.
    -   **Effet de la modification de ce paramètre :** Crée une urgence pour le client d'utiliser le coupon.
    -   **Valeur recommandée :** `30` jours. Cela donne aux clients une bonne fenêtre pour utiliser leur cadeau sans se sentir pressés.
    -   **Scénario / exemple marchand :** Vous souhaitez que les clients utilisent leur coupon d'anniversaire dans le mois suivant sa réception. Vous définiriez ceci à `30`.
-   **Appliquer à des produits/catégories spécifiques :**

    -   **Ce que fait ce paramètre :** Vous permet de restreindre l'utilisation du coupon à certains produits ou catégories.
    -   **Effet de la modification de ce paramètre :** Peut être utilisé pour promouvoir des articles spécifiques ou écouler d'anciens stocks.
    -   **Valeur recommandée :** Laisser vide sauf si vous avez un objectif promotionnel spécifique.
    -   **Scénario / exemple marchand :** Vous souhaitez que le coupon d'anniversaire ne soit valide que pour les articles de votre catégorie "Nouveautés".
-   **Autres options de bon de réduction :** (par exemple, cumulable avec d'autres bons, produits offerts, etc.)

    -   **Ce que fait ce paramètre :** Le module expose probablement d'autres options avancées de règles panier de PrestaShop, telles que la possibilité de combiner le bon avec d'autres réductions, s'il s'applique à des transporteurs spécifiques, ou s'il offre un cadeau gratuit.
    -   **Effet de la modification de ce paramètre :** Vous donne un contrôle précis sur le comportement et les restrictions du bon.
    -   **Valeur recommandée :** Configurez en fonction de votre stratégie promotionnelle spécifique. Soyez prudent avec la cumulativité pour éviter des réductions excessives.
    -   **Scénario / exemple marchand :** Vous voulez vous assurer que le coupon d'anniversaire ne peut pas être combiné avec d'autres promotions en cours. Vous désactiveriez l'option "Cumulable avec d'autres bons".

#### Paramètres du modèle d'e-mail

-   **Objet de l'e-mail :** (par exemple, `Joyeux Anniversaire de {shop_name} ! Voici un cadeau pour vous !`)

    -   **Ce que fait ce paramètre :** Définit la ligne d'objet de l'e-mail d'anniversaire.
    -   **Effet de la modification de ce paramètre :** C'est la première chose que les clients voient ; un objet attrayant augmente les taux d'ouverture.
    -   **Valeur recommandée :** Quelque chose de chaleureux, personnel et indiquant clairement un cadeau. Utilisez `{shop_name}` et `{customer_firstname}` si disponibles.
    -   **Scénario / exemple marchand :** Vous voulez une ligne d'objet accrocheuse qui fasse sentir les clients spéciaux.
-   **Contenu de l'e-mail :** (éditeur HTML)

    -   **Ce que fait ce paramètre :** Vous permet de personnaliser le contenu complet de l'e-mail d'anniversaire.
    -   **Effet de la modification de ce paramètre :** C'est ici que vous transmettez vos vœux d'anniversaire, expliquez la réduction et encouragez les achats.
    -   **Valeur recommandée :** Incluez un message chaleureux, indiquez clairement le code de réduction et sa valeur, expliquez comment l'utiliser et ajoutez un appel à l'action. Utilisez des espaces réservés comme `{customer_firstname}`, `{voucher_code}`, `{shop_name}`, `{shop_url}`.
    -   **Scénario / exemple marchand :** Vous voulez écrire un message sincère, inclure le logo de votre marque et afficher clairement le code de réduction.

#### Informations sur la tâche Cron

-   **URL de la tâche Cron :** (par exemple, `http://votreboutique.com/modules/birthdaypro/controllers/front/cron.php?token=VOTRE_TOKEN_SÉCURISÉ`)
    -   **Ce que fait ce paramètre :** Affiche l'URL que vous devez configurer comme tâche cron sur votre serveur. Cette tâche cron est essentielle pour que le module vérifie automatiquement les anniversaires à venir et envoie les coupons.
    -   **Effet de la modification de ce paramètre :** Ce n'est pas un paramètre à modifier, mais une instruction. Si la tâche cron n'est pas configurée correctement, aucun coupon d'anniversaire ne sera envoyé automatiquement.
    -   **Valeur recommandée :** Configurez une tâche cron pour exécuter cette URL une fois toutes les 24 heures (par exemple, quotidiennement à minuit).
    -   **Scénario / exemple marchand :** Vous avez configuré tous les paramètres, mais aucun e-mail n'est envoyé. La première chose à vérifier est si votre hébergeur a correctement configuré la tâche cron en utilisant cette URL.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Jours avant l'anniversaire du client pour envoyer le coupon | `7` | Envoie le coupon X jours avant l'anniversaire, encourageant les achats planifiés. |
| Configuration du module | Activer l'option newsletter | `NON` | Détermine si seuls les abonnés à la newsletter reçoivent des coupons. `NON` pour une portée plus large. |
| Configuration du module | Groupes de clients à inclure | `Client` (et autres si nécessaire) | Restreint l'envoi de coupons à des segments de clients spécifiques. |
| Configuration du module | Préfixe du code de bon de réduction | `ANNIVERSAIRE-` | Ajoute un préfixe unique aux codes de coupon générés pour une identification facile. |
| Configuration du module | Type de réduction | `Pourcentage` ou `Montant` | Définit la nature de la réduction (par exemple, 15 % de réduction, 10 € de réduction). |
| Configuration du module | Valeur de la réduction | `10` (pour 10 %) ou `5.00` (pour 5 €) | La valeur réelle de la réduction. |
| Configuration du module | Montant minimum | (Vide ou valeur spécifique) | Définit une valeur de commande minimale pour que le coupon soit valide. |
| Configuration du module | Période de validité | `30` jours | Durée de validité du coupon à partir de la date d'envoi, créant une urgence. |
| Configuration du module | Appliquer à des produits/catégories spécifiques | (Vide ou sélection spécifique) | Restreint l'utilisation du coupon à certains produits ou catégories. |
| Configuration du module | Autres options de bon de réduction | (Selon la stratégie) | Contrôle précis du comportement du bon (par exemple, cumulativité). |
| Configuration du module | Objet de l'e-mail | `Joyeux Anniversaire de {shop_name} !` | La ligne d'objet de l'e-mail d'anniversaire. |
| Configuration du module | Contenu de l'e-mail | (HTML personnalisé) | Le corps de l'e-mail d'anniversaire, y compris les salutations et les détails du coupon. |
| Configuration du module | URL de la tâche Cron | (URL affichée) | Essentiel pour les vérifications quotidiennes automatisées et l'envoi de coupons. Doit être configuré sur le serveur. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Mes clients ne reçoivent pas les e-mails d'anniversaire. Que dois-je vérifier en premier ?**
R1 :

1.  **Tâche Cron :** La raison la plus courante. Assurez-vous que l'URL de la tâche cron fournie dans la configuration du module est correctement configurée sur votre serveur d'hébergement pour s'exécuter quotidiennement. Sans cela, le module ne peut pas envoyer automatiquement d'e-mails.
2.  **Dates de naissance des clients :** Vérifiez que vos clients ont bien leurs dates de naissance saisies dans leurs comptes PrestaShop. Le module s'appuie sur ces données.
3.  **Configuration des e-mails :** Vérifiez les paramètres d'e-mail de votre PrestaShop (Paramètres avancés > E-mail) pour vous assurer que votre boutique peut envoyer des e-mails avec succès. Testez l'envoi d'un e-mail général depuis PrestaShop.
4.  **Dossiers de spam :** Conseillez aux clients de vérifier leurs dossiers de spam ou de courrier indésirable.
5.  **Paramètres du module :** Vérifiez à nouveau "Jours avant l'anniversaire du client", "Activer l'option newsletter" et "Groupes de clients à inclure" pour vous assurer que les clients sont éligibles.

**Q2 : Le code de réduction ne fonctionne pas pour mes clients.**
R2 :

1.  **Validité du bon :** Vérifiez le paramètre "Période de validité" dans le module. Le coupon a-t-il expiré ?
2.  **Montant minimum :** Le panier du client atteint-il l'exigence de "Montant minimum" définie pour le bon ?
3.  **Restrictions de produit/catégorie :** Si vous avez appliqué des restrictions, le client essaie-t-il d'acheter un produit éligible ?
4.  **Cumulable avec d'autres bons :** Si vous avez désactivé cette option, assurez-vous que le client n'essaie pas de le combiner avec une autre réduction.
5.  **Fautes de frappe :** Demandez au client de vérifier les fautes de frappe lors de la saisie du code.

**Q3 : Comment puis-je modifier l'apparence de l'e-mail d'anniversaire ?**
R3 : Vous pouvez entièrement personnaliser le contenu de l'e-mail à l'aide de l'éditeur HTML dans le paramètre "Contenu de l'e-mail" sur la page de configuration du module. Vous pouvez ajouter votre logo, modifier les polices, les couleurs et la mise en page. Assurez-vous d'utiliser les espaces réservés disponibles (comme `{customer_firstname}`, `{voucher_code}`, `{shop_name}`) pour personnaliser le message.

**Q4 : Puis-je envoyer différents coupons d'anniversaire à différents groupes de clients ?**
R4 : Le module Happy Birthday Coupon, dans sa configuration standard, envoie un seul type de coupon basé sur les paramètres que vous définissez. Pour envoyer différents coupons à différents groupes (par exemple, une réduction de 10 % pour les clients réguliers et une réduction de 20 % pour les VIP), vous devrez soit :
a) Créer et envoyer manuellement des bons séparés pour des groupes spécifiques (ce qui annule l'automatisation).
b) Utiliser les "Règles panier" natives de PrestaShop pour des groupes spécifiques et les gérer manuellement.
c) Envisager une personnalisation avancée ou une solution d'automatisation marketing plus complexe si c'est une exigence critique.

**Q5 : Le module semble fonctionner, mais je ne vois aucune preuve de coupons générés dans la section "Règles panier" de PrestaShop.**
R5 : Le module génère des règles panier (bons de réduction) uniques dynamiquement à l'approche de l'anniversaire d'un client. Ce sont de véritables règles panier PrestaShop. Vous devriez pouvoir les voir dans **Catalogue > Réductions > Règles panier** (ou **Règles de prix > Règles panier** dans les versions antérieures). Recherchez les règles avec le préfixe que vous avez défini (par exemple, `ANNIVERSAIRE-`). Si elles n'apparaissent pas, vérifiez à nouveau la configuration de votre tâche cron et du module.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module Happy Birthday Coupon.

### 4.1 Aperçu de l'architecture

Le module Happy Birthday Coupon (`birthdaypro`) suit une architecture de module PrestaShop standard, utilisant `Module` comme base. Il fonctionne principalement via une tâche cron qui déclenche un contrôleur frontal pour identifier les clients éligibles et générer des objets `CartRule` de PrestaShop. Le module n'étend pas `ObjectModel` pour ses propres données mais s'appuie sur les données client existantes de PrestaShop et la fonctionnalité `CartRule`. Il utilise un moteur de bon de réduction personnalisé et un outil de recherche à saisie semi-automatique, probablement pour la sélection de clients en back-office ou les tests.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs sont conçus pour être accessibles en externe, principalement via des tâches cron.

-   **`controllers/front/cron.php`**

    -   **Nom de la classe et classe parente :** `BirthdayproCronModuleFrontController` étendant `ModuleFrontController`.
    -   **Responsabilité :** C'est la logique principale pour la génération et l'envoi automatisés de coupons. Il est conçu pour être appelé par une tâche cron côté serveur.
        -   Il récupère les dates de naissance des clients.
        -   Détermine quels clients sont éligibles en fonction de la configuration `bp_daysbefore`, `bpro_nletter` et `birthdaypro_groups`.
        -   Pour chaque client éligible, il génère une `CartRule` (bon de réduction) PrestaShop unique avec les paramètres configurés.
        -   Envoie un e-mail d'anniversaire contenant le code du bon de réduction au client.
        -   Comprend une vérification de jeton de sécurité pour empêcher tout accès non autorisé.
-   **`controllers/front/index.php`**

    -   **Nom de la classe et classe parente :** `BirthdayproIndexModuleFrontController` étendant `ModuleFrontController`.
    -   **Responsabilité :** Ce contrôleur sert probablement de substitut ou de simple point d'entrée, éventuellement pour des tests ou pour gérer des requêtes qui ne correspondent pas à d'autres contrôleurs frontaux spécifiques. Dans de nombreux modules, un `index.php` dans un répertoire de contrôleur est un contrôleur de secours ou un contrôleur de type "hello world" de base. Il pourrait ne pas avoir de logique métier significative.

#### Contrôleurs d'administration Back-Office

Le module ne semble pas avoir de contrôleurs d'administration personnalisés dédiés d'après l'inventaire fourni. Toute la configuration du back-office est gérée dans la méthode `getContent()` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)

L'inventaire fourni n'indique aucune classe ou modèle personnalisé dans le répertoire `classes/`. Le module utilise probablement directement les classes natives `Customer`, `CartRule` et `Mail` de PrestaShop. Les mentions de "voucherengine" et "searchTool" dans les chemins JS/CSS suggèrent des classes ou fonctions d'aide internes au sein de `birthdaypro.php` ou de ses bibliothèques incluses, plutôt que des fichiers `classes/` autonomes.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`lib/searchTool/views/js/autocomplete.js`**

    -   **Portée :** Probablement Back-office.
    -   **Détails :** Ce script fournit une fonctionnalité de saisie semi-automatique, probablement pour la recherche de clients ou de produits dans la configuration du module ou une interface d'administration associée. Il se lierait aux champs de saisie, effectuerait des requêtes AJAX vers un point de terminaison backend (éventuellement le fichier du module principal ou un contrôleur d'administration dédié s'il en existait un), et afficherait des suggestions.
-   **`lib/voucherengine/script.js`**

    -   **Portée :** Probablement Back-office.
    -   **Détails :** Ce script fait partie du "moteur de bon de réduction" du module. Il gère probablement les éléments de formulaire dynamiques liés à la création de bons de réduction dans la page de configuration du module. Cela pourrait inclure l'affichage/masquage de champs en fonction de la sélection du type de réduction, la validation de la saisie pour les valeurs de bon de réduction ou l'interaction avec d'autres paramètres liés aux bons de réduction.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`lib/searchTool/views/css/autocomplete.css`**

    -   **Portée :** Probablement Back-office.
    -   **Détails :** Fournit un style pour la liste déroulante des suggestions de saisie semi-automatique et éventuellement le champ de saisie lui-même, garantissant son intégration visuelle avec le back-office de PrestaShop.
-   **`lib/voucherengine/ps16.css`**

    -   **Portée :** Probablement Back-office.
    -   **Détails :** Cette feuille de style fournit un style spécifique pour les éléments de configuration des bons de réduction, ciblant potentiellement l'esthétique du back-office de PrestaShop 1.6. Elle pourrait inclure des styles pour les groupes de formulaires, les champs de saisie et les étiquettes liés aux paramètres des bons de réduction.
-   **`views/css/css.css`**

    -   **Portée :** Probablement Back-office.
    -   **Détails :** Une feuille de style générale pour le module, contenant potentiellement des styles pour la page de configuration principale (`admin.tpl`) ou tout élément personnalisé introduit par le module dans le back-office. Elle pourrait inclure un style de base pour la mise en page, les boutons ou les alertes.

### 4.6 Structure du modèle Smarty (`views/templates/`)

-   **`lib/searchTool/views/scripts.tpl`**

    -   **Portée :** Back-office.
    -   **Détails :** Ce modèle inclut probablement du code JavaScript ou des variables Smarty nécessaires au bon fonctionnement du script `autocomplete.js`, tels que les URL AJAX, les chaînes de langue ou les données initiales. Il serait inclus dans le modèle de configuration d'administration principal.
-   **`views/templates/admin.tpl`**

    -   **Portée :** Back-office.
    -   **Détails :** C'est le modèle principal de la page de configuration du module, rendu par la méthode `getContent()` dans `birthdaypro.php`. Il contient la structure HTML de tous les paramètres décrits dans la section 4.1, y compris les champs de formulaire, les boutons et potentiellement les inclusions pour d'autres modèles comme `scripts.tpl`.
-   **`views/templates/script.tpl`**

    -   **Portée :** Back-office.
    -   **Détails :** Similaire à `scripts.tpl` dans la bibliothèque `searchTool`, ce modèle contient probablement du JavaScript spécifique au module ou des variables Smarty qui sont injectées dans la page de configuration du back-office. Il pourrait gérer le comportement dynamique ou le passage de données pour le moteur de bon de réduction.
-   **`views/templates/test.tpl`**

    -   **Portée :** Back-office ou tests internes.
    -   **Détails :** Le but de ce modèle est moins clair d'après le nom seul. Il pourrait s'agir d'un modèle utilisé pour les tests internes pendant le développement, d'un modèle de sortie de débogage ou d'un simple substitut. Il est peu probable qu'il fasse partie de la configuration standard destinée au marchand.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module ne crée pas de tables de base de données personnalisées d'après l'inventaire fourni.
    -   Il stocke ses paramètres de configuration (par exemple, `bp_daysbefore`, `bpro_nletter`, `birthdaypro_groups`) dans la table `ps_configuration` de PrestaShop.
    -   Il interagit avec les tables PrestaShop existantes : `ps_customer` (pour les dates de naissance), `ps_cart_rule` (pour la création de bons de réduction), `ps_cart_rule_lang`, `ps_cart_rule_shop`, `ps_cart_rule_product_rule_group`, etc.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment / Contexte d'exécution | But technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page front-office. | Généralement utilisé pour ajouter du CSS, du JS ou des balises meta. La description du module le mentionne, mais sa fonction principale est basée sur cron, donc ce hook pourrait être utilisé pour une configuration front-end minimale ou ne pas être activement utilisé pour la fonctionnalité principale. |
| `displayRightColumn` | Dans la colonne de droite des pages front-office. | Affiche du contenu dans la barre latérale droite. Peu susceptible d'être utilisé par ce module étant donné son fonctionnement en arrière-plan. |
| `displayLeftColumn` | Dans la colonne de gauche des pages front-office. | Affiche du contenu dans la barre latérale gauche. Peu susceptible d'être utilisé par ce module étant donné son fonctionnement en arrière-plan. |
| `displayFooter` | Dans la section du pied de page de chaque page front-office. | Affiche du contenu dans le pied de page. Peu susceptible d'être utilisé par ce module étant donné son fonctionnement en arrière-plan. |
| `displayProductButtons` / `displayProductExtraContent` (ou hooks de produit similaires) | Sur la page produit. | Peu susceptible d'être utilisé par ce module. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | Pourrait potentiellement être utilisé pour suivre l'utilisation des coupons ou le comportement des clients après l'application d'un coupon d'anniversaire, bien que non explicitement listé comme une fonction principale. |
| `actionCustomerAccountAdd` / `actionCustomerAccountUpdate` | Lorsqu'un compte client est créé ou mis à jour. | Pourrait être utilisé pour vérifier la saisie de la date de naissance ou déclencher la configuration initiale pour les nouveaux clients, bien que la tâche cron soit le déclencheur principal. |
| (Implicite) Exécution de la tâche Cron | Quotidiennement, via cron externe du serveur. | **CRITIQUE :** C'est le "hook" principal pour la fonctionnalité essentielle du module, déclenchant `controllers/front/cron.php` pour traiter les anniversaires et envoyer des e-mails. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module Happy Birthday Coupon, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe est dédiée à garantir que votre module fonctionne de manière optimale et vous aide à atteindre vos objectifs e-commerce.
