---
title: "Générateur de Référence de Commande Personnalisée Pro - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Générateur de Référence de Commande Personnalisée Pro par MyPresta.eu."
sidebar:
  label: "Générateur de Référence de Commande Personnalisée Pro - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Custom Order Reference Generator Pro sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/custom-order-reference-generator-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/custom-order-reference-generator-pro/)
>
> ---


# Générateur de Référence de Commande Personnalisée Pro

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Générateur de Référence de Commande Personnalisée Pro)

C'est l'écran de configuration principal où vous définissez vos modèles et règles de référence de commande personnalisés. La page est généralement organisée en plusieurs onglets ou sections pour plus de clarté.

#### **Onglet Paramètres généraux**

Cet onglet contrôle le comportement fondamental du module.

- **Activer la génération de référence de commande personnalisée :**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal du module. Lorsqu'il est activé, le module prend en charge la génération des références de commande. Lorsqu'il est désactivé, PrestaShop revient à sa méthode de génération de référence de commande par défaut.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Toutes les nouvelles commandes recevront une référence générée par ce module selon vos règles définies.
    - *Lorsqu'il est désactivé :* Toutes les nouvelles commandes utiliseront le format de référence par défaut de PrestaShop. Les commandes existantes conserveront leurs références.
  - **Valeur recommandée :** OUI (pour activer la fonctionnalité du module).
  - **Scénario / exemple pour le marchand :** Si vous souhaitez commencer à utiliser des références personnalisées, activez-le. Si vous devez temporairement revenir aux valeurs par défaut de PrestaShop pour le dépannage, désactivez-le.
- **Modèle de référence par défaut :**

  - **Ce que fait ce paramètre :** Il définit la structure de base de vos références de commande personnalisées. Vous pouvez combiner du texte statique avec des « shortcodes » dynamiques qui extraient des informations de la commande, du client ou de la date.
  - **Effet de la modification de ce paramètre :** Cela dicte directement le format de vos références de commande lorsqu'aucune règle spécifique ne s'applique.
  - **Valeur recommandée :** Commencez par quelque chose de simple comme `MA_BOUTIQUE-{DATE:YMD}-{ID_ORDER}` ou `CMD-{RAND:6}`.
  - **Scénario / exemple pour le marchand :**
    - `MA_BOUTIQUE-{DATE:YMD}-{ID_ORDER}` : Génère des références comme `MA_BOUTIQUE-20231027-12345`. C'est excellent pour identifier facilement les commandes de votre boutique et voir la date à laquelle elles ont été passées, ainsi qu'un ID de commande séquentiel.
    - `CMD-{RAND:6}` : Génère des références comme `CMD-A1B2C3`. Cela fournit une référence courte, aléatoire et unique.
    - `{CUSTOMER_LASTNAME}-{ID_ORDER}` : Génère des références comme `DUPONT-12345`. Utile pour le B2B ou le service personnalisé.
  - **Shortcodes disponibles :**
    - `{ID_ORDER}` : L'ID unique de la commande (séquentiel).
    - `{ID_CUSTOMER}` : L'ID unique du client.
    - `{DATE:format}` : Date et heure actuelles. `format` utilise la syntaxe de la fonction `date()` de PHP (par exemple, `YMD` pour 20231027, `His` pour 143059).
    - `{RAND:length}` : Une chaîne aléatoire de caractères alphanumériques, `length` spécifie le nombre de caractères (par exemple, `RAND:6`).
    - `{CUSTOMER_FIRSTNAME}` : Prénom du client.
    - `{CUSTOMER_LASTNAME}` : Nom de famille du client.
    - `{CUSTOMER_EMAIL}` : Adresse e-mail du client.
    - `{PAYMENT_METHOD}` : La méthode de paiement utilisée pour la commande.
    - `{DELIVERY_COUNTRY_ISO}` : Code ISO du pays de livraison (par exemple, US, FR).
    - `{DELIVERY_CITY}` : Ville de l'adresse de livraison.
    - `{CART_TOTAL}` : Valeur totale du panier.
    - `{PRODUCT_SKU}` : SKU du premier produit du panier (à utiliser avec prudence, peut être long).
    - `{PRODUCT_NAME}` : Nom du premier produit du panier (à utiliser avec prudence).
    - `{SHOP_NAME}` : Nom de votre boutique PrestaShop.
- **Valeur de début du compteur séquentiel :**

  - **Ce que fait ce paramètre :** Si votre modèle de référence inclut `{ID_ORDER}` ou un élément séquentiel similaire, cela définit le numéro de départ de cette séquence.
  - **Effet de la modification de ce paramètre :** Les nouvelles commandes commenceront leur numérotation séquentielle à partir de cette valeur. C'est utile si vous migrez d'un autre système ou si vous souhaitez redémarrer la numérotation.
  - **Valeur recommandée :** 1 (pour un nouveau départ) ou un nombre plus élevé si vous devez continuer une séquence.
  - **Scénario / exemple pour le marchand :** Si vous aviez précédemment 1000 commandes et que vous souhaitez que vos nouvelles références personnalisées commencent à partir de 1001, définissez cette valeur sur 1001.
- **Limite de longueur de référence :**

  - **Ce que fait ce paramètre :** PrestaShop a une limite par défaut pour la longueur de la référence de commande. Cela vous permet de définir une longueur maximale pour vos références générées. Si une référence dépasse cette limite, elle sera tronquée.
  - **Effet de la modification de ce paramètre :** Garantit que vos références respectent les contraintes de la base de données et s'affichent correctement dans toutes les zones de PrestaShop.
  - **Valeur recommandée :** 9 (la valeur par défaut de PrestaShop est souvent 9, mais vous pouvez l'augmenter si votre thème/base de données le prend en charge, jusqu'à 32 caractères est généralement sûr).
  - **Scénario / exemple pour le marchand :** Si votre modèle `MA_BOUTIQUE-{DATE:YMD}-{ID_ORDER}` donne `MA_BOUTIQUE-20231027-12345` (21 caractères), et que vous définissez la limite à 9, il pourrait devenir `MA_BOUTIQUE-2`. Soyez attentif à la troncature.
- **Référence d'aperçu :**

  - **Ce que fait ce paramètre :** C'est un champ utilitaire qui vous permet de tester votre `Modèle de référence par défaut` avec un ID de commande factice pour voir à quoi ressemblerait la référence générée.
  - **Effet de la modification de ce paramètre :** Aucun effet direct sur votre boutique, c'est purement un outil de test.
  - **Valeur recommandée :** Utilisez-le fréquemment lors de la conception de vos modèles.
  - **Scénario / exemple pour le marchand :** Entrez `12345` comme ID de commande factice et cliquez sur « Générer l'aperçu » pour voir à quoi ressemblerait `MA_BOUTIQUE-{DATE:YMD}-{ID_ORDER}`.

#### **Onglet Règles**

Cet onglet est l'endroit où vous définissez des conditions spécifiques sous lesquelles différents modèles de référence de commande doivent être appliqués, en annulant le modèle par défaut. Les règles sont traitées de haut en bas, et la première règle correspondante est appliquée.

- **Ajouter une nouvelle règle / Modifier une règle :**

  - **Ce que cela fait :** Vous permet de créer une nouvelle règle ou de modifier une règle existante. Chaque règle se compose de :
    - **Nom de la règle :** Un nom descriptif pour votre référence interne (par exemple, « Commandes de grande valeur », « Clients français »).
    - **Modèle de règle :** Le modèle de référence personnalisé à utiliser si cette règle correspond (mêmes shortcodes que le modèle par défaut).
    - **Conditions :** Un ou plusieurs critères qui doivent être remplis pour que cette règle s'applique.
  - **Effet de la modification de ce paramètre :** Ajoute ou modifie un modèle de référence conditionnel.
  - **Valeur recommandée :** Créez des règles pour vos segments d'activité les plus importants.
  - **Scénario / exemple pour le marchand :**
    - **Règle 1 : Commandes de grande valeur**
      - **Modèle :** `VIP-{ID_ORDER}-{DATE:YMD}`
      - **Condition :** `Total du panier` est `supérieur à` `500`
      - **Effet :** Toute commande de plus de 500 € obtiendra une référence comme `VIP-12345-20231027`.
    - **Règle 2 : Clients français**
      - **Modèle :** `FR-{ID_ORDER}`
      - **Condition :** `Pays de livraison` est `France`
      - **Effet :** Les commandes expédiées en France obtiendront `FR-12345`.
    - **Règle 3 : Commandes de produits spécifiques**
      - **Modèle :** `PROD-XYZ-{ID_ORDER}`
      - **Condition :** `Produit dans le panier` est `Nom du produit XYZ`
      - **Effet :** Les commandes contenant « Nom du produit XYZ » obtiendront `PROD-XYZ-12345`.
- **Conditions de règle (pour chaque règle) :**

  - **Ce que cela fait :** Définit les critères pour qu'une règle soit active. Vous pouvez combiner plusieurs conditions en utilisant la logique « ET ».
  - **Conditions disponibles :**
    - **Total du panier :** Basé sur la valeur totale de la commande.
    - **Groupe de clients :** Basé sur le groupe auquel appartient le client (par exemple, Visiteurs, Clients, Invités ou groupes personnalisés).
    - **Pays de livraison :** Basé sur le pays de l'adresse de livraison.
    - **Méthode de paiement :** Basé sur le module de paiement utilisé (par exemple, Virement bancaire, PayPal).
    - **Produit dans le panier :** Basé sur la présence d'un produit spécifique (par ID ou nom) dans la commande.
    - **Transporteur :** Basé sur le transporteur choisi.
  - **Effet de la modification de ce paramètre :** Détermine quand un modèle de référence personnalisé spécifique est utilisé.
  - **Valeur recommandée :** Utilisez des conditions qui segmentent clairement vos commandes.
  - **Scénario / exemple pour le marchand :** Une règle pour les « Clients grossistes » pourrait utiliser `Groupe de clients est Grossiste`. Une règle pour l'« Expédition express » pourrait utiliser `Transporteur est DHL Express`.

#### **Onglet Paramètres avancés**

Cet onglet contient des paramètres pour des aspects plus techniques et la maintenance.

- **Sauvegarde / Restauration JSON :**

  - **Ce que cela fait :** Vous permet d'exporter la configuration de votre module (modèles, règles) vers un fichier JSON ou d'importer une configuration précédemment enregistrée.
  - **Effet de la modification de ce paramètre :**
    - *Sauvegarde :* Crée un fichier téléchargeable de vos paramètres.
    - *Restauration :* Écrase les paramètres actuels avec ceux du fichier JSON téléchargé.
  - **Valeur recommandée :** Sauvegardez toujours votre configuration avant d'apporter des modifications majeures ou de mettre à niveau votre boutique PrestaShop.
  - **Scénario / exemple pour le marchand :** Avant de mettre à jour PrestaShop ou de déplacer votre boutique vers un nouveau serveur, téléchargez une sauvegarde de vos règles de référence personnalisées. Si vous faites une erreur avec une règle, vous pouvez facilement restaurer une version précédente.
- **Réinitialiser la configuration du module :**

  - **Ce que cela fait :** Supprime tous les modèles et règles personnalisés, ramenant le module à son état par défaut, fraîchement installé.
  - **Effet de la modification de ce paramètre :** Tous vos modèles et règles de référence personnalisés seront perdus.
  - **Valeur recommandée :** À utiliser avec une extrême prudence, uniquement si vous souhaitez recommencer complètement.
  - **Scénario / exemple pour le marchand :** Si vos règles sont devenues trop complexes ou causent des problèmes, et que vous souhaitez repartir de zéro, vous pouvez utiliser cette option. Sauvegardez toujours d'abord !

#### **Tableau de référence rapide de la configuration**

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Paramètres généraux** | Activer la génération de référence de commande personnalisée | OUI | Active/désactive la logique de référence personnalisée du module. |
| | Modèle de référence par défaut | `CMD-{RAND:6}` (exemple) | Définit le format de référence de secours lorsqu'aucune règle ne correspond. |
| | Valeur de début du compteur séquentiel | 1 | Définit le numéro initial pour `{ID_ORDER}` dans les nouvelles références. |
| | Limite de longueur de référence | 9 (ou plus si sûr) | Limite la longueur maximale des références générées pour éviter les problèmes. |
| | Référence d'aperçu | (N/A) | Outil pour tester votre modèle avec un ID de commande factice. |
| **Onglet Règles** | Ajouter/Modifier une règle | N/A | Crée des modèles de référence conditionnels basés sur des critères. |
| | Nom de la règle | Descriptif (par exemple, « Commandes de grande valeur ») | Libellé interne de la règle. |
| | Modèle de règle | Personnalisé (par exemple, `VIP-{ID_ORDER}`) | Le format de référence pour cette règle spécifique. |
| | Conditions de règle | Varie (par exemple, `Total du panier > 500`) | Critères qui doivent être remplis pour que la règle s'applique. |
| **Paramètres avancés** | Sauvegarde / Restauration JSON | N/A | Exporte/importe la configuration du module pour la sécurité ou la migration. |
| | Réinitialiser la configuration du module | N/A | Supprime tous les paramètres et règles du module. À utiliser avec une extrême prudence. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes références personnalisées n'apparaissent pas, ou je vois toujours les références par défaut de PrestaShop.**
R1 : Tout d'abord, assurez-vous que le module est **activé** dans l'onglet « Paramètres généraux ». Vérifiez également si vous avez vidé votre cache PrestaShop (Paramètres avancés > Performances > Vider le cache). Si vous avez des règles spécifiques, assurez-vous que leurs conditions sont remplies et que les règles sont correctement ordonnées (la première règle correspondante s'applique).

**Q2 : Mes références personnalisées sont trop longues ou sont tronquées.**
R2 : Vérifiez la « Limite de longueur de référence » dans l'onglet « Paramètres généraux ». PrestaShop a une limite par défaut (souvent 9 caractères) pour les références de commande dans sa base de données. Si votre modèle personnalisé génère des références plus longues, vous devrez peut-être augmenter cette limite. Soyez prudent, car l'augmenter trop pourrait causer des problèmes d'affichage dans certains thèmes ou des versions plus anciennes de PrestaShop. Il est généralement sûr d'aller jusqu'à 32 caractères. Si vous avez besoin de plus long, consultez un développeur.

**Q3 : J'ai fait une erreur avec mes règles, et maintenant mes références sont incorrectes. Comment puis-je résoudre ce problème ?**
R3 : Si vous avez une sauvegarde JSON récente (depuis l'onglet « Paramètres avancés »), vous pouvez la restaurer. Sinon, vous devrez modifier ou supprimer manuellement les règles problématiques. Si vous souhaitez repartir complètement de zéro, utilisez l'option « Réinitialiser la configuration du module », mais sachez que cela supprimera *tous* vos modèles et règles personnalisés.

**Q4 : Puis-je utiliser ce module avec plusieurs boutiques (configuration multistore) ?**
R4 : Oui, le module est conçu pour être compatible avec la fonctionnalité multistore de PrestaShop. Vous pouvez configurer différents modèles de référence et règles pour chaque boutique depuis la page de configuration du module, en sélectionnant le contexte de boutique spécifique dans le back office de PrestaShop.

**Q5 : Que se passe-t-il pour les commandes existantes lorsque je modifie le modèle de référence ?**
R5 : La modification du modèle de référence ou des règles n'affecte que les *nouvelles* commandes passées après la modification. Les commandes existantes conserveront leurs références de commande d'origine. Le module ne modifie pas rétroactivement les données des commandes passées.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Générateur de Référence de Commande Personnalisée Pro » étend principalement la classe `Order` de PrestaShop via une surcharge pour intercepter et modifier le processus de génération de référence de commande. Il suit une approche événementielle où le module s'accroche au cycle de vie de la création de commande. La configuration est gérée via une méthode `getContent()` standard dans le fichier principal du module, stockant les paramètres dans `ps_configuration` et les règles personnalisées dans ses propres tables de base de données (bien qu'aucun fichier SQL spécifique ne soit listé, cela implique une création de table dynamique ou un stockage de configuration). Le module utilise un `RulesEngine` pour évaluer les conditions et un `ReferenceGenerator` pour construire la référence finale basée sur les modèles et les shortcodes définis.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne semble pas utiliser de contrôleurs front-office ou back-office personnalisés. Toute la configuration est gérée dans la méthode `getContent()` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)

- `refchangepro/classes/PayloadFactory.php`

  - **Nom de la classe :** `PayloadFactory`
  - **Classe parente :** Aucune (probablement une classe utilitaire)
  - **Responsabilité :** Responsable de la création d'une charge utile de données (contexte) que le `RulesEngine` et le `ReferenceGenerator` peuvent utiliser. Cette charge utile contiendrait des informations sur la commande en cours de traitement (par exemple, le total du panier, l'ID client, le pays de livraison, les produits). Elle agit comme une couche d'abstraction pour collecter toutes les données nécessaires à l'évaluation des règles et à la génération des références.
- `refchangepro/classes/ReferenceContext.php`

  - **Nom de la classe :** `ReferenceContext`
  - **Classe parente :** Aucune (probablement un objet de transfert de données ou un objet de valeur)
  - **Responsabilité :** Une classe simple pour contenir et gérer les données contextuelles (par exemple, ID de commande, détails client, détails du panier) qui sont transmises pendant le processus de génération de référence. Elle assure la cohérence de l'accès aux données pour le générateur et le moteur de règles.
- `refchangepro/classes/ReferenceGenerator.php`

  - **Nom de la classe :** `ReferenceGenerator`
  - **Classe parente :** Aucune (probablement une classe de service)
  - **Responsabilité :** La logique principale pour construire la chaîne de référence de commande finale. Elle prend un modèle (par exemple, `MA_BOUTIQUE-{DATE:YMD}-{ID_ORDER}`) et un objet `ReferenceContext`, puis remplace les shortcodes par des valeurs réelles. Elle gère le formatage de la date, la génération de chaînes aléatoires et l'insertion d'ID séquentiels.
- `refchangepro/classes/RulesEngine.php`

  - **Nom de la classe :** `RulesEngine`
  - **Classe parente :** Aucune (probablement une classe de service)
  - **Responsabilité :** Évalue les règles définies par rapport au contexte de commande actuel. Elle itère sur les règles configurées, vérifie si les conditions (par exemple, total du panier, groupe de clients, pays) sont remplies et renvoie le modèle de la première règle correspondante. Si aucune règle ne correspond, elle indique que le modèle par défaut doit être utilisé.
- `refchangepro/classes/Runtime.php`

  - **Nom de la classe :** `Runtime`
  - **Classe parente :** Aucune (probablement une classe utilitaire ou d'aide)
  - **Responsabilité :** Pourrait gérer les configurations d'exécution, la mise en cache ou d'autres aspects opérationnels du module. Pourrait être responsable du chargement des règles à partir de la configuration, de la gestion du compteur séquentiel ou de la fourniture de méthodes utilitaires utilisées dans tout le module.
- `refchangepro/override/classes/order/Order.php`

  - **Chemin exact du fichier :** `refchangepro/override/classes/order/Order.php`
  - **Nom de la classe :** `Order`
  - **Classe parente :** `OrderCore` (classe Order principale de PrestaShop)
  - **Responsabilité :** C'est la surcharge critique. Elle intercepte la méthode `generateReference()` (ou une méthode similaire responsable de la définition de la référence de commande) dans la classe `Order` principale de PrestaShop. Dans cette méthode surchargée, elle appelle le `RulesEngine` du module pour déterminer le bon modèle, puis le `ReferenceGenerator` pour créer la référence personnalisée, et enfin la définit pour l'objet commande. Cela garantit que chaque nouvelle commande créée utilise la logique du module.

### 4.4 Assets JavaScript (`views/js/`)

- `refchangepro/lib/searchTool/views/js/autocomplete.js`

  - **Portée :** Probablement Back-office.
  - **Description :** Fournit une fonctionnalité d'autocomplétion, éventuellement pour sélectionner des produits, des clients ou d'autres entités lors de la définition de règles. Il se lierait aux champs de saisie, effectuerait des requêtes AJAX à un contrôleur d'administration PrestaShop (ou à la méthode `getContent` du module) et afficherait des suggestions.
- `refchangepro/views/js/admin-tabs.js`

  - **Portée :** Back-office.
  - **Description :** Gère l'interface à onglets dans la page de configuration du module. Il lie les événements de clic aux en-têtes d'onglet, affiche/masque le contenu d'onglet correspondant et peut gérer les changements de hachage d'URL pour la liaison directe aux onglets.
- `refchangepro/views/js/rules-builder.js`

  - **Portée :** Back-office.
  - **Description :** C'est le JavaScript principal de l'onglet « Règles ». Il gère l'ajout, la modification et la suppression dynamiques des conditions de règle. Il lie les événements aux boutons « Ajouter une condition », gère les listes déroulantes pour les types de conditions (par exemple, « Total du panier », « Groupe de clients ») et rend dynamiquement les champs de saisie en fonction du type de condition sélectionné (par exemple, champ numérique pour le total du panier, liste déroulante pour les groupes de clients). Il sérialise probablement les données de la règle dans un champ de saisie masqué pour la soumission.

### 4.5 Feuilles de style CSS (`views/css/`)

- `refchangepro/lib/searchTool/views/css/autocomplete.css`

  - **Portée :** Style d'administration du Back-office.
  - **Description :** Style les listes de suggestions d'autocomplétion et les champs de saisie, en veillant à ce qu'ils soient visuellement cohérents et conviviaux dans le back office de PrestaShop.
- `refchangepro/views/css/admin.css`

  - **Portée :** Style d'administration du Back-office.
  - **Description :** Fournit un style général pour la page de configuration du module, y compris la mise en page, la typographie, les styles de boutons et la présentation visuelle globale pour s'intégrer de manière transparente au thème du back office de PrestaShop.
- `refchangepro/views/css/rules-builder.css`

  - **Portée :** Style d'administration du Back-office.
  - **Description :** Styles spécifiques pour l'interface du constructeur de règles, y compris la mise en page des blocs de règles individuels, des lignes de condition et de tout élément de glisser-déposer ou de réorganisation.

### 4.6 Structure du template Smarty (`views/templates/`)

- `refchangepro/lib/searchTool/views/scripts.tpl`
  - **Portée :** Administration du Back-office.
  - **Description :** Ce template inclut probablement le JavaScript et potentiellement le CSS nécessaires pour l'outil de recherche d'autocomplétion. Il serait inclus dans le template de configuration du module principal pour charger la fonctionnalité d'autocomplétion.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - La description du module mentionne « Des règles intelligentes appliquent différents modèles par valeur de panier, pays, produit ou groupe de clients. » Cela implique fortement la création de tables de base de données personnalisées pour stocker ces règles et leurs conditions associées.
  - Tables attendues (les noms sont illustratifs, les noms réels seraient préfixés par `ps_` et le nom du module) :
    - `ps_refchangepro_rules` : Stocke les définitions de règles principales (ID, nom, modèle, statut actif).
    - `ps_refchangepro_conditions` : Stocke les conditions individuelles pour chaque règle (ID de règle, type de condition, opérateur, valeur).
  - Les paramètres de configuration (comme `PS_REFCHANGEPRO_ENABLED`, `PS_REFCHANGEPRO_DEFAULT_PATTERN`, `PS_REFCHANGEPRO_COUNTER_START`) sont stockés dans la table `ps_configuration` de PrestaShop.
  - Le compteur séquentiel pour `{ID_ORDER}` pourrait être stocké dans `ps_configuration` ou une table dédiée pour un verrouillage plus robuste.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionOrderAdd` / `actionObjectOrderAddAfter` | Après la création d'un nouvel objet commande dans la base de données. | La surcharge de `Order::generateReference()` par le module est le mécanisme principal. Cependant, si le module doit effectuer des actions supplémentaires *après* que la commande est entièrement enregistrée avec sa nouvelle référence, ces hooks seraient utilisés. Par exemple, pour enregistrer la référence générée ou mettre à jour un compteur personnalisé. |
| `displayBackOfficeHeader` | Dans la section `<head>` du Back Office. | Utilisé pour charger les CSS spécifiques au module (`admin.css`, `rules-builder.css`, `autocomplete.css`) et le JavaScript (`admin-tabs.js`, `rules-builder.js`, `autocomplete.js`) pour la page de configuration. |
| `displayAdminProductsExtra` / `displayAdminCustomers` (Hypothétique) | Sur les pages d'édition de produits ou de clients dans le Back Office. | Si le module devait offrir des paramètres de référence spécifiques par produit ou par client, il se brancherait ici pour afficher ces options. (Non explicitement indiqué, mais courant pour les versions « Pro »). |
| `displayModuleConfigure` (Interne) | Lorsque la page de configuration du module est chargée. | La méthode `getContent()` du fichier principal du module est implicitement hookée ici pour rendre le formulaire de configuration. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et des informations supplémentaires concernant le module « Générateur de Référence de Commande Personnalisée Pro », veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes vos questions ou problèmes.
