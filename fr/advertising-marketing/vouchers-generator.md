---
title: "Générateur de bons de réduction - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Générateur de bons de réduction par MyPresta.eu."
sidebar:
  label: "Générateur de bons de réduction - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Vouchers Generator sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/vouchers-generator.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/vouchers-generator/)
>
> ---


# Générateur de bons de réduction

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur inhabituelle n'est requise.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après avoir installé le module, naviguez vers **Modules > Gestionnaire de modules** et cliquez sur "Configurer" à côté de "Générateur de bons de réduction". C'est l'écran principal où vous gérerez tous les paramètres et générerez vos bons de réduction.

La page de configuration est conçue pour être intuitive, vous permettant de définir les règles de vos nouveaux bons de réduction, puis de les générer.

#### **1. Paramètres de génération de bons de réduction**

Cette section vous permet de définir les propriétés principales des bons de réduction que vous souhaitez générer.

- **Nom :**

  - **Ce que fait ce paramètre :** C'est le nom qui apparaîtra dans votre Back Office PrestaShop sous "Catalogue > Réductions > Règles panier" pour le lot de bons de réduction générés. C'est aussi le nom de base pour les codes de bons de réduction individuels (par exemple, si vous définissez "ÉTÉ2024", les codes pourraient être "ÉTÉ2024-ABCDE", "ÉTÉ2024-FGHIJ").
  - **Effet de la modification de ce paramètre :** Un nom clair et descriptif vous aide à identifier le but du lot de bons de réduction plus tard.
  - **Valeur recommandée :** Quelque chose de descriptif comme "Soldes d'été 2024", "Bienvenue nouveau client" ou "Récupération de panier abandonné".
  - **Scénario / exemple marchand :** Vous lancez une promotion estivale. Vous pourriez la nommer "ÉTÉ2024".
- **Description :**

  - **Ce que fait ce paramètre :** Une note interne pour votre référence, visible uniquement dans le Back Office. Elle vous aide à vous souvenir des détails spécifiques ou des objectifs de cette campagne de bons de réduction.
  - **Effet de la modification de ce paramètre :** Fournit un contexte pour vous et votre équipe.
  - **Valeur recommandée :** Une brève explication, par exemple, "20 % de réduction sur toutes les commandes de plus de 50 €, valable 1 mois, distribué via la newsletter par e-mail."
  - **Scénario / exemple marchand :** Pour la campagne "ÉTÉ2024", vous pourriez ajouter "20 % de réduction sur tous les produits, achat minimum de 50 €, valable jusqu'au 31 août."
- **Mettre en avant :**

  - **Ce que fait ce paramètre :** Si activé, ce bon de réduction sera affiché dans le récapitulatif du panier pour tous les clients, même s'ils ne l'ont pas saisi. Ceci est généralement utilisé pour les promotions générales et publiques.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Le bon de réduction apparaît automatiquement dans le récapitulatif du panier, encourageant les clients à l'utiliser.
    - *Lorsqu'désactivé :* Le bon de réduction n'est appliqué que si le client saisit explicitement le code.
  - **Valeur recommandée :** "NON" pour les bons de réduction uniques et ciblés ; "OUI" pour les promotions publiques à l'échelle de la boutique.
  - **Scénario / exemple marchand :** Si vous donnez des codes uniques à des clients spécifiques, désactivez ceci. S'il s'agit d'une promotion générale "10 % de réduction sur tout", activez-le.
- **Utilisation partielle :**

  - **Ce que fait ce paramètre :** Détermine si un bon de réduction peut être utilisé plusieurs fois si sa valeur dépasse le total de la commande.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Si un client a un bon de réduction de 50 € et achète un article de 30 €, il lui restera un solde de 20 € sur ce même bon de réduction pour un futur achat.
    - *Lorsqu'désactivé :* Si un client a un bon de réduction de 50 € et achète un article de 30 €, l'intégralité du bon de réduction de 50 € est consommée, et aucun solde ne reste.
  - **Valeur recommandée :** "NON" pour la plupart des promotions afin d'encourager une utilisation complète ou d'éviter un suivi complexe. "OUI" pour les cartes-cadeaux ou le crédit en magasin.
  - **Scénario / exemple marchand :** Pour une réduction standard, vous désactiveriez généralement ceci. Pour un chèque-cadeau, vous l'activeriez.
- **Priorité :**

  - **Ce que fait ce paramètre :** Définit l'ordre dans lequel les règles panier sont appliquées si plusieurs règles sont actives. Un nombre inférieur signifie une priorité plus élevée (appliquée en premier).
  - **Effet de la modification de ce paramètre :** Influence la façon dont les réductions s'empilent. Si deux bons de réduction s'appliquent, celui avec la priorité la plus élevée est traité en premier.
  - **Valeur recommandée :** Laissez par défaut (1) sauf si vous avez des règles d'empilement complexes.
  - **Scénario / exemple marchand :** Si vous avez un bon de réduction "Livraison gratuite" (priorité 1) et un bon de réduction "10 % de réduction" (priorité 2), la livraison gratuite sera calculée avant la réduction en pourcentage.
- **Statut :**

  - **Ce que fait ce paramètre :** Active ou désactive les bons de réduction générés.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les bons de réduction sont actifs et peuvent être utilisés par les clients.
    - *Lorsqu'désactivé :* Les bons de réduction sont inactifs et ne peuvent pas être utilisés.
  - **Valeur recommandée :** "OUI" si vous souhaitez que les bons de réduction soient immédiatement utilisables. Vous pouvez les désactiver plus tard si nécessaire.
  - **Scénario / exemple marchand :** Vous générez des bons de réduction pour une future vente. Vous pourriez les activer le jour du début de la vente.

#### **2. Conditions des bons de réduction**

Cette section définit quand et comment les bons de réduction générés peuvent être utilisés.

- **Valide à partir de :**

  - **Ce que fait ce paramètre :** Définit la date de début à partir de laquelle les bons de réduction deviennent actifs.
  - **Effet de la modification de ce paramètre :** Les bons de réduction ne peuvent pas être utilisés avant cette date.
  - **Valeur recommandée :** La date du jour si vous souhaitez qu'ils soient actifs immédiatement, ou une date future pour une promotion planifiée.
  - **Scénario / exemple marchand :** Définir sur "2024-07-01" pour une promotion de juillet.
- **Valide jusqu'à :**

  - **Ce que fait ce paramètre :** Définit la date de fin après laquelle les bons de réduction expirent.
  - **Effet de la modification de ce paramètre :** Les bons de réduction ne peuvent pas être utilisés après cette date.
  - **Valeur recommandée :** Une date d'expiration raisonnable pour votre promotion (par exemple, 1 semaine, 1 mois, fin de saison).
  - **Scénario / exemple marchand :** Définir sur "2024-07-31" pour une promotion de juillet.
- **Montant minimum :**

  - **Ce que fait ce paramètre :** Le montant total d'achat minimum (avant frais de port et taxes) requis pour que le bon de réduction soit valide.
  - **Effet de la modification de ce paramètre :** Si le total du panier du client est inférieur à ce montant, le bon de réduction ne peut pas être appliqué.
  - **Valeur recommandée :** Définir une valeur qui encourage des valeurs de commande moyennes plus élevées, ou 0 si aucun minimum n'est requis.
  - **Scénario / exemple marchand :** Définir sur "50.00" pour offrir une réduction uniquement sur les commandes de plus de 50 €.
- **Total disponible :**

  - **Ce que fait ce paramètre :** Le nombre total de fois où *tous* les bons de réduction générés dans ce lot peuvent être utilisés par *tous* les clients.
  - **Effet de la modification de ce paramètre :** Une fois cette limite atteinte, aucun autre bon de réduction de ce lot ne peut être utilisé, même si des codes individuels ont encore des utilisations restantes.
  - **Valeur recommandée :** Un nombre élevé (par exemple, 99999) si vous souhaitez que les limites de codes individuels s'appliquent, ou un nombre spécifique pour une campagne à durée limitée et à utilisation totale.
  - **Scénario / exemple marchand :** Si vous générez 100 codes uniques et définissez "Total disponible" à 50, seules les 50 premières utilisations de tous les codes seront valides.
- **Total disponible pour chaque utilisateur :**

  - **Ce que fait ce paramètre :** Le nombre maximum de fois où *chaque client individuel* peut utiliser *n'importe quel* des bons de réduction de ce lot.
  - **Effet de la modification de ce paramètre :** Empêche un seul client d'utiliser à plusieurs reprises différents codes du même lot.
  - **Valeur recommandée :** "1" pour la plupart des campagnes de bons de réduction uniques afin de garantir que chaque client n'obtienne qu'une seule utilisation. "0" pour des utilisations illimitées par client (non recommandé pour les codes uniques).
  - **Scénario / exemple marchand :** Définir sur "1" pour s'assurer que chaque client ne peut bénéficier que d'un seul de vos codes générés.

#### **3. Actions des bons de réduction**

Cette section définit ce que le bon de réduction fait réellement lorsqu'il est appliqué.

- **Livraison gratuite :**

  - **Ce que fait ce paramètre :** Détermine si le bon de réduction accorde la livraison gratuite.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les frais de port sont annulés pour les commandes utilisant ce bon de réduction.
    - *Lorsqu'désactivé :* Les frais de port standard s'appliquent.
  - **Valeur recommandée :** "NON" sauf s'il s'agit d'une promotion spécifique de livraison gratuite.
  - **Scénario / exemple marchand :** Pour une promotion "Week-end livraison gratuite", vous activeriez ceci.
- **Appliquer une réduction :**

  - **Ce que fait ce paramètre :** C'est ici que vous définissez le montant ou le pourcentage de réduction réel.
  - **Effet de la modification de ce paramètre :** Détermine la valeur monétaire de la réduction.
  - **Valeur recommandée :** Choisissez un type de réduction (pourcentage, montant ou produit spécifique) et remplissez les détails.
  - **Scénario / exemple marchand :** Vous souhaitez offrir 15 % de réduction.
  - **Pourcentage :**

    - **Ce que fait ce paramètre :** Applique une réduction en pourcentage au total de la commande.
    - **Effet de la modification de ce paramètre :** Réduit le total de la commande du pourcentage spécifié.
    - **Valeur recommandée :** Un pourcentage courant comme 5, 10, 15, 20.
    - **Scénario / exemple marchand :** Saisissez "15" pour 15 % de réduction.
  - **Montant :**

    - **Ce que fait ce paramètre :** Applique une réduction monétaire fixe au total de la commande.
    - **Effet de la modification de ce paramètre :** Réduit le total de la commande du montant spécifié.
    - **Valeur recommandée :** Un montant fixe comme 5.00, 10.00, 25.00.
    - **Scénario / exemple marchand :** Saisissez "10.00" pour 10 € de réduction.
  - **Appliquer la réduction à :**

    - **Ce que fait ce paramètre :** Spécifie à quelle partie de la commande la réduction s'applique.
    - **Effet de la modification de ce paramètre :**
      - *Commande (hors frais de port) :* La réduction s'applique uniquement au total des produits.
      - *Produit spécifique :* La réduction s'applique uniquement à un produit ou à une sélection de produits particuliers.
      - *Produit le moins cher :* La réduction s'applique à l'article le moins cher du panier.
      - *Produits sélectionnés :* La réduction s'applique à une liste spécifique de produits que vous définissez.
    - **Valeur recommandée :** "Commande (hors frais de port)" pour les réductions générales.
    - **Scénario / exemple marchand :** Pour une réduction générale de 15 %, choisissez "Commande (hors frais de port)". Si vous voulez 20 % de réduction uniquement sur les "T-shirts", vous sélectionneriez "Produits sélectionnés" puis choisiriez la catégorie/les produits T-shirt.
- **Envoyer un cadeau :**

  - **Ce que fait ce paramètre :** Vous permet d'ajouter automatiquement un produit spécifique en tant que cadeau gratuit lorsque le bon de réduction est utilisé.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Un produit choisi est ajouté gratuitement au panier du client.
    - *Lorsqu'désactivé :* Aucun cadeau gratuit n'est fourni.
  - **Valeur recommandée :** "NON" sauf s'il s'agit d'une promotion spécifique de cadeau avec achat.
  - **Scénario / exemple marchand :** Vous souhaitez offrir un "Porte-clés" gratuit avec chaque commande de plus de 100 €. Vous activeriez ceci et sélectionneriez le produit Porte-clés.

#### **4. Génération de bons de réduction**

C'est la dernière étape où vous définissez le nombre de codes à générer, puis exécutez la génération.

- **Nombre de bons de réduction à générer :**

  - **Ce que fait ce paramètre :** Spécifie le nombre de codes de bons de réduction uniques que vous souhaitez que le module crée.
  - **Effet de la modification de ce paramètre :** Détermine la quantité de codes de réduction individuels qui seront ajoutés à vos Règles panier PrestaShop.
  - **Valeur recommandée :** Le nombre exact de codes uniques dont vous avez besoin pour votre campagne (par exemple, 100 pour une liste d'e-mails, 500 pour un concours sur les réseaux sociaux).
  - **Scénario / exemple marchand :** Vous avez besoin de 250 codes uniques pour une campagne marketing. Saisissez "250".
- **Bouton Générer les bons de réduction :**

  - **Ce que fait ce paramètre :** Ce bouton lance le processus de création de tous les bons de réduction en fonction des paramètres que vous avez configurés ci-dessus.
  - **Effet de la modification de ce paramètre :** Cliquer sur ce bouton créera le nombre spécifié de règles panier uniques dans votre boutique PrestaShop. Un message de confirmation apparaîtra, et vous pourrez télécharger un fichier CSV/Excel contenant les codes générés.
  - **Valeur recommandée :** Cliquez uniquement après être absolument certain que tous vos paramètres sont corrects.
  - **Scénario / exemple marchand :** Après avoir examiné tous les paramètres de votre campagne "ÉTÉ2024" et défini le nombre de bons de réduction à 250, vous cliquez sur "Générer les bons de réduction".

#### **5. Mises à jour et informations MyPresta.eu**

Cette section contient généralement des informations sur la version du module, la disponibilité des mises à jour et des liens vers MyPresta.eu.

- **Mises à jour MyPresta.eu / Vérification des mises à jour :**
  - **Ce que fait ce paramètre :** Permet au module de vérifier les nouvelles versions disponibles sur MyPresta.eu.
  - **Effet de la modification de ce paramètre :** Vous aide à maintenir votre module à jour avec les dernières fonctionnalités et corrections de bugs.
  - **Valeur recommandée :** Laissez ceci activé pour recevoir des notifications concernant les mises à jour.
  - **Scénario / exemple marchand :** Vous voyez une notification qu'une nouvelle version est disponible, vous assurant d'avoir la version la plus stable et la plus riche en fonctionnalités.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Nom | Texte descriptif | Nom interne du lot de bons de réduction. |
| Configuration du module | Description | Texte facultatif | Notes internes pour les détails de la campagne. |
| Configuration du module | Mettre en avant | NON | Afficher le bon de réduction dans le récapitulatif du panier (OUI pour public, NON pour privé). |
| Configuration du module | Utilisation partielle | NON | Autoriser l'utilisation multiple du bon de réduction si la valeur > commande. |
| Configuration du module | Priorité | 1 | Ordre d'application pour plusieurs règles panier (inférieur = priorité plus élevée). |
| Configuration du module | Statut | OUI | Activer/désactiver les bons de réduction générés. |
| Configuration du module | Valide à partir de | Date actuelle | Date de début de validité du bon de réduction. |
| Configuration du module | Valide jusqu'à | Date future | Date de fin de validité du bon de réduction. |
| Configuration du module | Montant minimum | 0.00 | Achat minimum requis pour l'utilisation du bon de réduction. |
| Configuration du module | Total disponible | Nombre élevé (par exemple, 99999) | Utilisations totales pour TOUS les bons de réduction de ce lot. |
| Configuration du module | Total disponible pour chaque utilisateur | 1 | Utilisations max par client pour tout bon de réduction de ce lot. |
| Configuration du module | Livraison gratuite | NON | Accorder la livraison gratuite avec le bon de réduction. |
| Configuration du module | Appliquer une réduction | OUI | Activer l'application de la réduction. |
| Configuration du module | Pourcentage | (par exemple, 10) | Réduction en pourcentage. |
| Configuration du module | Montant | (par exemple, 10.00) | Réduction monétaire fixe. |
| Configuration du module | Appliquer la réduction à | Commande (hors frais de port) | Portée de la réduction (commande, produit spécifique, etc.). |
| Configuration du module | Envoyer un cadeau | NON | Ajouter un produit gratuit en cadeau. |
| Configuration du module | Nombre de bons de réduction à générer | (par exemple, 100) | Quantité de codes uniques à créer. |
| Configuration du module | Bouton Générer les bons de réduction | Cliquer lorsque prêt | Lance la création des bons de réduction et l'exportation CSV. |
| Configuration du module | Mises à jour MyPresta.eu | OUI | Vérifier les mises à jour du module. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : J'ai généré des bons de réduction, mais ils ne semblent pas fonctionner en front office.**
R1 :

- **Vérifier le statut et les dates :** Allez dans "Catalogue > Réductions > Règles panier" dans votre Back Office PrestaShop. Trouvez les bons de réduction que vous avez générés. Assurez-vous que leur "Statut" est défini sur "Oui" et que les dates "Valide à partir de" et "Valide jusqu'à" sont actuelles.
- **Montant minimum :** Vérifiez si le panier du client respecte l'exigence de "Montant minimum" définie pour le bon de réduction.
- **Conditions :** Vérifiez à nouveau toutes les autres conditions que vous avez définies (par exemple, produits spécifiques, groupes de clients).
- **Cache :** Videz le cache de votre PrestaShop (Paramètres avancés > Performances > Vider le cache).

**Q2 : Puis-je modifier les bons de réduction générés après leur création ?**
R2 : Oui, une fois généré, chaque bon de réduction devient une "Règle panier" standard dans PrestaShop. Vous pouvez aller dans "Catalogue > Réductions > Règles panier" dans votre Back Office, trouver les bons de réduction individuels (ils partageront généralement le même nom de base que vous avez fourni), et modifier leurs propriétés (par exemple, date d'expiration, montant de la réduction, conditions) individuellement. Cependant, il est généralement préférable de bien définir tous les paramètres avant la génération.

**Q3 : Comment obtenir la liste des codes de bons de réduction générés ?**
R3 : Immédiatement après avoir cliqué sur le bouton "Générer les bons de réduction", le module vous invitera à télécharger un fichier CSV/Excel contenant tous les codes uniques. Si vous avez manqué cela, vous ne pouvez pas retélécharger la liste directement depuis le module. Vous devrez exporter manuellement les "Règles panier" depuis "Catalogue > Réductions > Règles panier" dans PrestaShop, ou accéder directement à la base de données (tâche de développeur). Il est crucial de sauvegarder le fichier CSV immédiatement après la génération.

**Q4 : Le module indique "Mises à jour MyPresta.eu" mais n'affiche pas de nouvelle version.**
R4 : Cela signifie que votre module est actuellement à jour avec la dernière version officielle disponible sur MyPresta.eu. Aucune action n'est requise.

**Q5 : Mon thème personnalisé n'affiche pas correctement le champ de saisie du bon de réduction.**
R5 : Le module Générateur de bons de réduction n'ajoute pas d'éléments au front-office. Le champ de saisie du bon de réduction est une fonctionnalité standard de PrestaShop. S'il ne s'affiche pas correctement, il s'agit probablement d'un problème avec le style de votre thème personnalisé ou les surcharges de modèle pour les pages de panier/commande. Vous devrez consulter votre développeur de thème ou un webmaster pour ajuster les fichiers CSS ou TPL liés aux hooks `displayCart` ou `displayPaymentTop` où le champ de bon de réduction apparaît généralement.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module Générateur de bons de réduction (`vouchers`) est un module PrestaShop standard fonctionnant principalement dans le Back Office. Il exploite la fonctionnalité `CartRule` de base de PrestaShop pour créer efficacement plusieurs codes de réduction. La logique principale du module réside dans son fichier `vouchers.php`, gérant la configuration et le processus de génération. Il n'introduit pas de modèles MVC complexes ni de tables de base de données personnalisées, mais interagit directement avec le modèle d'objet `CartRule` existant de PrestaShop.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. Le module n'ajoute aucun contrôleur front-office personnalisé. Toutes les interactions front-office liées aux bons de réduction sont gérées par les contrôleurs natifs `CartController` ou `OrderController` de PrestaShop.
- **Contrôleurs Admin Back-Office** : Aucun. La logique de configuration et de génération du module est entièrement contenue dans la méthode `getContent()` de la classe principale du module, qui est rendue par le `AdminModulesController` standard.

### 4.3 Classes et modèles de base (`classes/`)

- Aucun. Le module ne définit aucune classe personnalisée ni n'étend `ObjectModel`. Il utilise directement la classe native `CartRule` de PrestaShop pour créer et gérer les bons de réduction.

### 4.4 Actifs JavaScript (`views/js/`)

- `vouchers/lib/voucherengine/script.js`
  - **Portée :** Back-office.
  - **Objectif :** Ce script contient probablement la logique côté client pour la page de configuration du module. Cela pourrait inclure :
    - La validation du formulaire avant la génération des bons de réduction.
    - Des appels AJAX à la méthode `getContent()` du module pour des mises à jour ou un traitement dynamique.
    - Des améliorations de l'interface utilisateur ou des interactions spécifiques au formulaire de génération de bons de réduction.
    - Potentiellement la gestion du téléchargement du fichier CSV généré.
  - **Écouteurs d'événements :** Se lie probablement aux événements de soumission de formulaire, aux événements de changement de saisie et aux clics de bouton sur la page de configuration du module.
  - **Manipulation du DOM :** Peut afficher/masquer des éléments en fonction des sélections de l'utilisateur (par exemple, afficher des champs de sélection de produits spécifiques si "Appliquer la réduction à : Produit spécifique" est choisi).

### 4.5 Feuilles de style CSS (`views/css/`)

- `vouchers/lib/voucherengine/ps16.css`
  - **Portée :** Style du formulaire d'administration du Back-office.
  - **Objectif :** Fournit un style spécifique pour l'interface de configuration du module, potentiellement pour assurer une apparence cohérente sur différentes versions de PrestaShop (par exemple, en s'adaptant à la structure spécifique du thème d'administration de PrestaShop 1.6).
  - **Composants principaux de l'interface utilisateur :** Style les champs de formulaire, les boutons et les éléments de mise en page dans la sortie `getContent()` du module.
  - **Sélecteurs de classe CSS clés :** Les développeurs peuvent inspecter la page de configuration du module dans le navigateur pour identifier des classes spécifiques (par exemple, `.vouchers-generator-form`, `.mypresta-update-block`) qui peuvent être remplacées dans un thème d'administration personnalisé si nécessaire.

### 4.6 Structure du modèle Smarty (`views/templates/`)

- `vouchers/views/pdf.tpl`
  - **Portée :** Back-office / Utilitaire.
  - **Objectif :** Ce modèle est probablement utilisé pour générer un document PDF imprimable ou téléchargeable contenant la liste des bons de réduction générés. Bien que la description du module mentionne l'exportation CSV/Excel, un modèle PDF suggère un format de sortie alternatif ou supplémentaire pour la liste des bons de réduction, éventuellement pour l'impression de bons physiques.
  - **Utilisation :** Il serait rendu lorsque le module doit présenter les codes de bons de réduction générés dans un format structuré et imprimable. Il recevrait un tableau de données de bons de réduction (code, valeur, expiration, etc.) de la logique PHP.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne crée aucune table de base de données personnalisée.
  - Il interagit avec les tables natives `ps_cart_rule` et `ps_cart_rule_lang` de PrestaShop pour stocker les bons de réduction générés.
  - Les paramètres de configuration (comme `vg_counter`, `mypresta_updates`) sont stockés dans la table `ps_configuration`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration est initialisé et que ses médias (JS/CSS) sont définis. | Utilisé par le module pour inclure ses fichiers JavaScript (`script.js`) et CSS (`ps16.css`) du Back Office spécifiquement sur sa page de configuration, garantissant qu'ils ne sont chargés que lorsque cela est nécessaire. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module Générateur de bons de réduction, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
