---
title: "Importation de bons d'achat depuis CSV - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Importation de bons d'achat depuis CSV' par MyPresta.eu."
sidebar:
  label: "Importation de bons d'achat depuis CSV - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Import voucher from CSV sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/import-voucher-from-csv.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/import-voucher-from-csv/)
>
> ---


# Importation de bons d'achat depuis CSV

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge :** PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes et habituellement activées par défaut sur la plupart des environnements d'hébergement.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à l'écran de configuration principal du module. C'est ici que vous téléchargerez votre fichier CSV et définirez comment les codes de bon d'achat doivent être importés et quelles propriétés ils doivent avoir.

La page de configuration est généralement structurée en plusieurs sections, vous guidant à travers le processus d'importation.

#### **Étape 1 : Téléchargez votre fichier CSV**

-   **Ce que fait ce paramètre :** C'est ici que vous sélectionnez le fichier CSV contenant vos codes de bon d'achat depuis votre ordinateur.
-   **Effet de la modification de ce paramètre :** Cliquer sur « Parcourir » ou « Choisir un fichier » ouvre une boîte de dialogue de sélection de fichier. Une fois que vous avez sélectionné un fichier, son nom apparaîtra à côté du bouton, indiquant qu'il est prêt à être téléchargé.
-   **Valeur recommandée :** Sélectionnez le fichier CSV que vous avez préparé avec vos codes de bon d'achat.
-   **Scénario / exemple pour le marchand :** Vous avez reçu une liste de 1000 codes de bon d'achat uniques d'un partenaire comme Groupon. Vous avez enregistré ces codes dans un fichier CSV (par exemple, `groupon_vouchers.csv`). Vous cliqueriez sur « Choisir un fichier » et sélectionneriez ce fichier.

#### **Étape 2 : Paramètres du fichier CSV**

Cette section définit comment le module doit interpréter votre fichier CSV.

-   **Séparateur CSV :**

    -   **Ce que fait ce paramètre :** Spécifie le caractère utilisé pour séparer les valeurs (colonnes) dans votre fichier CSV. Les séparateurs courants sont la virgule (`,`), le point-virgule (`;`) ou la tabulation (`\t`).
    -   **Effet de la modification de ce paramètre :** Si le mauvais séparateur est choisi, le module ne pourra pas analyser correctement votre fichier, et toutes les données pourraient apparaître dans une seule colonne ou être mal divisées.
    -   **Valeur recommandée :** Faites correspondre le séparateur utilisé lorsque vous avez créé ou exporté votre fichier CSV. La plupart des logiciels de feuille de calcul utilisent la virgule par défaut.
    -   **Scénario / exemple pour le marchand :** Si votre CSV ressemble à `CODE123,10,USD`, vous choisiriez « Virgule ». Si c'est `CODE123;10;USD`, vous choisiriez « Point-virgule ».
-   **Délimiteur de texte :**

    -   **Ce que fait ce paramètre :** Spécifie le caractère utilisé pour encadrer les valeurs de texte, en particulier celles qui pourraient contenir le caractère séparateur. Souvent, il s'agit d'un guillemet double (`"`).
    -   **Effet de la modification de ce paramètre :** Si vos champs de texte contiennent le séparateur (par exemple, un nom de produit avec une virgule) et ne sont pas correctement délimités, le module pourrait mal interpréter les données, ce qui entraînerait une analyse incorrecte.
    -   **Valeur recommandée :** Faites correspondre le délimiteur utilisé dans votre CSV. Généralement « Guillemet double ».
    -   **Scénario / exemple pour le marchand :** Si une description de bon d'achat est `"10% de réduction, offre limitée dans le temps"` et que votre séparateur est une virgule, les guillemets doubles garantissent que « 10% de réduction, offre limitée dans le temps » est traité comme un seul champ.
-   **Sauter la première ligne (en-tête) :**

    -   **Ce que fait ce paramètre :** Si votre fichier CSV a une ligne d'en-tête (par exemple, `Code de bon d'achat,Montant de la réduction,Date d'expiration`) qui décrit les colonnes, l'activation de cette option indiquera au module d'ignorer cette première ligne lors de l'importation.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé :* La ligne d'en-tête est ignorée, et seules les lignes de données réelles sont importées.
        -   *Lorsque désactivé :* La première ligne de votre CSV sera traitée comme un code de bon d'achat ou des données, ce qui est généralement incorrect et peut entraîner des erreurs.
    -   **Valeur recommandée :** « OUI » si votre CSV a une ligne d'en-tête, « NON » s'il ne contient que des données.
    -   **Scénario / exemple pour le marchand :** Votre CSV commence par `code,valeur,devise`. Vous activeriez cette option pour empêcher que « code » ne soit importé comme un bon d'achat réel.

#### **Étape 3 : Paramètres du bon d'achat (Propriétés générales)**

Cette section définit les propriétés communes pour tous les bons d'achat que vous importez. Ces paramètres s'appliquent à *tous* les codes de votre fichier CSV.

-   **Nom :**

    -   **Ce que fait ce paramètre :** C'est le nom interne de la règle de bon d'achat dans votre Back Office. Il vous aide à identifier le groupe de bons d'achat.
    -   **Effet de la modification de ce paramètre :** Ce nom n'est visible que par vous dans le Back Office, pas par les clients.
    -   **Valeur recommandée :** Un nom descriptif, par exemple, « Codes Groupon - Mai 2024 ».
    -   **Scénario / exemple pour le marchand :** Vous importez des codes d'une campagne « Soldes d'été 2024 ». Vous le nommeriez « Bons d'achat Soldes d'été 2024 ».
-   **Description :**

    -   **Ce que fait ce paramètre :** Une description interne facultative pour la règle de bon d'achat.
    -   **Effet de la modification de ce paramètre :** Fournit plus de contexte à votre équipe dans le Back Office.
    -   **Valeur recommandée :** Une brève explication, par exemple, « Codes uniques pour 10% de réduction, usage unique, expire le 31/05/2024 ».
    -   **Scénario / exemple pour le marchand :** « Codes fournis par LivingSocial pour les nouveaux clients. »
-   **Mettre en avant :**

    -   **Ce que fait ce paramètre :** Détermine si le bon d'achat est mis en avant dans le récapitulatif du panier.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé :* Le bon d'achat sera affiché plus en évidence dans le récapitulatif du panier, attirant potentiellement plus l'attention sur la réduction.
        -   *Lorsque désactivé :* Le bon d'achat sera listé normalement.
    -   **Valeur recommandée :** « NON » pour une utilisation générale, « OUI » si vous souhaitez souligner la réduction.
    -   **Scénario / exemple pour le marchand :** Pour une offre spéciale à durée limitée, vous pourriez activer « OUI » pour vous assurer que les clients remarquent la réduction appliquée.
-   **Utilisation partielle :**

    -   **Ce que fait ce paramètre :** Permet aux clients d'utiliser seulement une partie de la valeur du bon d'achat et de conserver le reste pour de futurs achats.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé :* Si un client a un bon d'achat de 50 € et achète un article de 30 €, il conserve un solde de 20 € sur le bon d'achat.
        -   *Lorsque désactivé :* La valeur totale du bon d'achat doit être utilisée en une seule transaction ; tout solde restant est perdu.
    -   **Valeur recommandée :** « NON » pour la plupart des codes de réduction. « OUI » pour les cartes cadeaux ou le crédit en magasin.
    -   **Scénario / exemple pour le marchand :** Si vous importez des codes de carte cadeau, vous activeriez « OUI ». Pour un coupon standard « 10% de réduction », vous utiliseriez « NON ».
-   **Priorité :**

    -   **Ce que fait ce paramètre :** Détermine l'ordre dans lequel plusieurs bons d'achat sont appliqués si un client en utilise plus d'un. Les bons d'achat ayant une priorité plus élevée sont appliqués en premier.
    -   **Effet de la modification de ce paramètre :** Peut influencer le montant final de la réduction si plusieurs bons d'achat interagissent (par exemple, réductions en pourcentage vs réductions de montant fixe).
    -   **Valeur recommandée :** « 1 » pour la priorité la plus élevée, ou laisser par défaut si vous n'avez pas d'interactions complexes entre les bons d'achat.
    -   **Scénario / exemple pour le marchand :** Si vous avez un bon d'achat « Livraison gratuite » et un bon d'achat « 10% de réduction », vous pourriez donner une priorité plus élevée à « Livraison gratuite » pour vous assurer qu'il est appliqué en premier, puis la réduction en pourcentage.
-   **Statut :**

    -   **Ce que fait ce paramètre :** Active ou désactive la règle de bon d'achat.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé :* Les bons d'achat importés sous cette règle peuvent être utilisés par les clients.
        -   *Lorsque désactivé :* Les bons d'achat ne peuvent pas être utilisés, même s'ils sont valides.
    -   **Valeur recommandée :** « OUI » pour rendre les bons d'achat immédiatement utilisables. Vous pouvez le désactiver plus tard si nécessaire.
    -   **Scénario / exemple pour le marchand :** Vous souhaitez préparer des bons d'achat à l'avance mais ne les activer que le jour du lancement d'une campagne. Vous définiriez « NON » initialement, puis passeriez à « OUI » lorsque vous seriez prêt.

#### **Étape 4 : Paramètres du bon d'achat (Conditions)**

Cette section définit les conditions dans lesquelles les bons d'achat importés peuvent être utilisés.

-   **Montant minimum :**

    -   **Ce que fait ce paramètre :** Spécifie le total minimum de la commande (avant frais de port et taxes) requis pour que le bon d'achat soit valide.
    -   **Effet de la modification de ce paramètre :** Les clients doivent atteindre cette valeur d'achat minimale pour appliquer la réduction.
    -   **Valeur recommandée :** « 0 » si aucun minimum n'est requis, ou un montant spécifique (par exemple, « 50.00 »).
    -   **Scénario / exemple pour le marchand :** « Obtenez 10 € de réduction sur les commandes de plus de 100 €. » Vous définiriez « 100.00 ».
-   **Devise :**

    -   **Ce que fait ce paramètre :** Sélectionne la devise pour le montant minimum.
    -   **Effet de la modification de ce paramètre :** Garantit que le montant minimum est interprété correctement pour les boutiques multi-devises.
    -   **Valeur recommandée :** La devise par défaut de votre boutique (par exemple, « EUR », « USD »).
    -   **Scénario / exemple pour le marchand :** Si votre boutique opère dans plusieurs devises, assurez-vous que cela correspond à la devise que vous attendez que les clients utilisent pour ce bon d'achat.
-   **Cumulable avec d'autres bons d'achat :**

    -   **Ce que fait ce paramètre :** Détermine si ce bon d'achat peut être combiné avec d'autres bons d'achat actifs dans la même commande.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé :* Les clients peuvent utiliser ce bon d'achat avec d'autres bons d'achat valides.
        -   *Lorsque désactivé :* Ce bon d'achat ne peut pas être utilisé si un autre bon d'achat est déjà appliqué au panier.
    -   **Valeur recommandée :** « NON » pour la plupart des codes uniques afin d'éviter des réductions excessives. « OUI » pour des promotions spécifiques comme la « livraison gratuite » que vous souhaitez combiner.
    -   **Scénario / exemple pour le marchand :** Vous importez des codes « 10% de réduction ». Vous voudrez probablement « NON » pour empêcher les clients d'empiler plusieurs réductions en pourcentage.
-   **Date d'expiration (Du) :**

    -   **Ce que fait ce paramètre :** Définit la date de début à partir de laquelle les bons d'achat importés deviennent valides.
    -   **Effet de la modification de ce paramètre :** Les bons d'achat ne peuvent pas être utilisés avant cette date.
    -   **Valeur recommandée :** La date d'aujourd'hui ou une date future pour les promotions planifiées.
    -   **Scénario / exemple pour le marchand :** Vous souhaitez que les bons d'achat soient actifs à partir de lundi prochain. Vous sélectionneriez la date de lundi prochain.
-   **Date d'expiration (Au) :**

    -   **Ce que fait ce paramètre :** Définit la date de fin après laquelle les bons d'achat importés ne sont plus valides.
    -   **Effet de la modification de ce paramètre :** Les bons d'achat ne peuvent pas être utilisés après cette date.
    -   **Valeur recommandée :** Une date future correspondant à la fin de votre promotion.
    -   **Scénario / exemple pour le marchand :** Votre campagne se termine le 31 décembre. Vous sélectionneriez le 31 décembre.
-   **Quantité :**

    -   **Ce que fait ce paramètre :** Définit le nombre total de fois que *chaque code de bon d'achat individuel* peut être utilisé.
    -   **Effet de la modification de ce paramètre :**
        -   *Défini à 1 :* Chaque code de votre CSV ne peut être utilisé qu'une seule fois (le plus courant pour les codes uniques).
        -   *Défini à >1 :* Chaque code peut être utilisé plusieurs fois jusqu'à cette limite.
    -   **Valeur recommandée :** « 1 » pour les codes uniques à usage unique (par exemple, de Groupon).
    -   **Scénario / exemple pour le marchand :** Pour 1000 codes Groupon uniques, vous définiriez ceci à « 1 » afin que chaque client ne puisse utiliser son code spécifique qu'une seule fois.
-   **Quantité par utilisateur :**

    -   **Ce que fait ce paramètre :** Définit le nombre de fois qu'*un seul client* peut utiliser *n'importe quel* bon d'achat de ce lot importé.
    -   **Effet de la modification de ce paramètre :**
        -   *Défini à 1 :* Un client ne peut utiliser qu'un seul bon d'achat de ce lot, même s'il a plusieurs codes uniques.
        -   *Défini à >1 :* Un client peut utiliser plusieurs bons d'achat de ce lot, jusqu'à cette limite.
    -   **Valeur recommandée :** « 1 » pour la plupart des campagnes de codes uniques afin d'empêcher un seul client d'utiliser de nombreux codes.
    -   **Scénario / exemple pour le marchand :** Vous souhaitez que chaque client ne bénéficie que d'un seul bon d'achat « de bienvenue ». Vous définiriez ceci à « 1 ».

#### **Étape 5 : Paramètres du bon d'achat (Actions)**

Cette section définit le type de réduction que les bons d'achat importés fourniront.

-   **Livraison gratuite :**

    -   **Ce que fait ce paramètre :** Si activé, le bon d'achat accordera la livraison gratuite pour la commande.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé :* Les frais de port sont annulés lorsque le bon d'achat est appliqué.
        -   *Lorsque désactivé :* Les frais de port sont calculés normalement.
    -   **Valeur recommandée :** « NON » à moins que l'objectif principal de ces bons d'achat ne soit la livraison gratuite.
    -   **Scénario / exemple pour le marchand :** Vous importez des codes pour une promotion « Week-end de livraison gratuite ». Vous activeriez « OUI ».
-   **Appliquer une réduction :**

    -   **Ce que fait ce paramètre :** Détermine le type et la valeur de la réduction appliquée par le bon d'achat.
    -   **Effet de la modification de ce paramètre :** C'est le mécanisme de réduction principal.
    -   **Valeur recommandée :** Choisissez l'une des options ci-dessous en fonction de votre promotion.
    -   **Scénario / exemple pour le marchand :** Vous souhaitez offrir 10% de réduction.
    -   **Pourcentage :**

        -   **Ce que fait ce paramètre :** Applique une réduction en pourcentage à la commande.
        -   **Effet de la modification de ce paramètre :** Le champ `Valeur` sera interprété comme un pourcentage (par exemple, `10` pour 10%).
        -   **Valeur recommandée :** Sélectionnez ceci pour les réductions basées sur un pourcentage.
        -   **Scénario / exemple pour le marchand :** Pour une promotion « 15% de réduction », sélectionnez « Pourcentage » et entrez `15` dans le champ `Valeur`.
    -   **Montant :**

        -   **Ce que fait ce paramètre :** Applique une réduction monétaire fixe à la commande.
        -   **Effet de la modification de ce paramètre :** Le champ `Valeur` sera interprété comme un montant fixe dans la devise choisie (par exemple, `10.00` pour 10 € de réduction).
        -   **Valeur recommandée :** Sélectionnez ceci pour les réductions de montant fixe.
        -   **Scénario / exemple pour le marchand :** Pour une promotion « 20 € de réduction », sélectionnez « Montant » et entrez `20.00` dans le champ `Valeur`.
    -   **Aucun :**

        -   **Ce que fait ce paramètre :** Si sélectionné, le bon d'achat n'appliquera aucune réduction monétaire ou en pourcentage. Ceci est généralement utilisé lorsque la seule action du bon d'achat est « Livraison gratuite » ou « Envoyer un cadeau ».
        -   **Effet de la modification de ce paramètre :** Aucune valeur de réduction n'est appliquée.
        -   **Valeur recommandée :** Ne sélectionnez « Aucun » que si vous utilisez « Livraison gratuite » ou « Envoyer un cadeau » comme action principale.
        -   **Scénario / exemple pour le marchand :** Si vous souhaitez uniquement offrir la livraison gratuite, vous sélectionneriez « Aucun » ici et activeriez « Livraison gratuite » ci-dessus.
-   **Valeur :**

    -   **Ce que fait ce paramètre :** La valeur numérique réelle de la réduction. Son interprétation dépend de si « Pourcentage » ou « Montant » est sélectionné ci-dessus.
    -   **Effet de la modification de ce paramètre :** Contrôle directement la taille de la réduction.
    -   **Valeur recommandée :** Une valeur numérique (par exemple, `10` pour 10% ou 10 €).
    -   **Scénario / exemple pour le marchand :** Si vous avez choisi « Pourcentage » et que vous voulez 15% de réduction, entrez `15`. Si vous avez choisi « Montant » et que vous voulez 20 € de réduction, entrez `20.00`.
-   **Appliquer la réduction à :**

    -   **Ce que fait ce paramètre :** Détermine à quoi la réduction est appliquée.
    -   **Effet de la modification de ce paramètre :**
        -   *Commande (hors frais de port) :* La réduction s'applique à la valeur totale des produits dans le panier.
        -   *Produit spécifique :* La réduction s'applique uniquement à un produit particulier que vous spécifiez.
        -   *Produit le moins cher :* La réduction s'applique au produit le moins cher du panier.
        -   *Produits sélectionnés :* La réduction s'applique à une sélection de produits.
    -   **Valeur recommandée :** « Commande (hors frais de port) » pour les réductions générales.
    -   **Scénario / exemple pour le marchand :** Pour une campagne générale « 10% de réduction sur tout », choisissez « Commande (hors frais de port) ». S'il s'agit de « 10% de réduction sur tous les T-shirts », vous sélectionneriez « Produits sélectionnés » puis choisiriez votre catégorie/produits de T-shirts.
-   **Envoyer un cadeau :**

    -   **Ce que fait ce paramètre :** Si activé, le bon d'achat ajoutera un produit spécifique au panier du client en tant que cadeau gratuit.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé :* Il vous sera demandé de sélectionner un produit à ajouter en cadeau.
        -   *Lorsque désactivé :* Aucun cadeau n'est ajouté.
    -   **Valeur recommandée :** « NON » à moins que vous ne meniez une promotion de type « achetez X obtenez Y gratuit ».
    -   **Scénario / exemple pour le marchand :** « Achetez n'importe quel produit, obtenez un porte-clés gratuit. » Vous activeriez « OUI » et sélectionneriez le produit porte-clés.

Après avoir configuré tous les paramètres, vous trouverez généralement un bouton « Enregistrer » ou « Importer ». Cliquez dessus pour lancer le processus d'importation. Le module lira alors votre fichier CSV et créera les règles de bon d'achat correspondantes dans votre base de données PrestaShop en fonction des paramètres que vous avez définis.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Télécharger le fichier CSV | Votre CSV préparé | Sélectionne le fichier contenant les codes de bon d'achat. |
| | Séparateur CSV | Virgule (`,`) | Caractère séparant les colonnes de votre CSV. Doit correspondre à votre fichier. |
| | Délimiteur de texte | Guillemet double (`"`) | Caractère encadrant les champs de texte de votre CSV. Doit correspondre à votre fichier. |
| | Sauter la première ligne (en-tête) | OUI (si l'en-tête existe) | Ignore la première ligne de votre CSV si c'est un en-tête. |
| | **Paramètres du bon d'achat (Général)** | | |
| | Nom | Nom descriptif | Nom interne de la règle de bon d'achat dans le BO. |
| | Description | Texte facultatif | Description interne de la règle de bon d'achat. |
| | Mettre en avant | NON | Met en avant le bon d'achat dans le récapitulatif du panier. |
| | Utilisation partielle | NON | Permet l'utilisation partielle de la valeur du bon d'achat. OUI pour les cartes cadeaux. |
| | Priorité | 1 | Ordre d'application pour plusieurs bons d'achat. |
| | Statut | OUI | Active/désactive la règle de bon d'achat. |
| | **Paramètres du bon d'achat (Conditions)** | | |
| | Montant minimum | 0 | Total minimum de la commande pour la validité du bon d'achat. |
| | Devise | Devise par défaut de la boutique | Devise pour le montant minimum. |
| | Cumulable avec d'autres bons d'achat | NON | Permet de combiner avec d'autres bons d'achat. |
| | Date d'expiration (Du) | Date d'aujourd'hui | Date de début de validité du bon d'achat. |
| | Date d'expiration (Au) | Date future | Date de fin de validité du bon d'achat. |
| | Quantité | 1 | Utilisations totales par code de bon d'achat *individuel*. |
| | Quantité par utilisateur | 1 | Utilisations totales par *client* de ce lot. |
| | **Paramètres du bon d'achat (Actions)** | | |
| | Livraison gratuite | NON | Accorde la livraison gratuite. |
| | Appliquer une réduction | Pourcentage / Montant | Type de réduction (pourcentage ou montant fixe). |
| | Valeur | Valeur numérique | La valeur réelle de la réduction (par exemple, 10 pour 10% ou 10 €). |
| | Appliquer la réduction à | Commande (hors frais de port) | À quoi la réduction s'applique (commande, produit spécifique, etc.). |
| | Envoyer un cadeau | NON | Ajoute un produit gratuit en cadeau. |

## 3. Dépannage pour le marchand et questions fréquemment posées (FAQ)

**Q : J'ai importé mon CSV, mais les bons d'achat ne fonctionnent pas ou n'apparaissent pas.**
R :

1.  **Vérifier le statut du module :** Assurez-vous que le module lui-même est activé dans **Modules > Gestionnaire de modules**.
2.  **Vérifier le statut du bon d'achat :** Allez dans **Catalogue > Réductions > Règles panier** (ou **Règles de prix > Règles panier** dans les versions antérieures). Trouvez la règle de bon d'achat créée par l'importation (elle aura le « Nom » que vous avez spécifié lors de la configuration). Assurez-vous que son « Statut » est défini sur « OUI » (actif).
3.  **Dates d'expiration :** Vérifiez à nouveau les paramètres « Date d'expiration (Du) » et « Date d'expiration (Au) ». Si la date actuelle est en dehors de cette plage, les bons d'achat ne fonctionneront pas.
4.  **Montant minimum :** Vérifiez si le panier du client respecte la condition de « Montant minimum » que vous avez définie.
5.  **Codes de bon d'achat :** Assurez-vous que les codes de votre CSV sont exactement tels que les clients les saisissent (sensible à la casse, pas d'espaces supplémentaires).

**Q : Mon fichier CSV n'est pas analysé correctement. Toutes les données sont dans une seule colonne, ou les colonnes sont mélangées.**
R : Cela est presque toujours dû à des paramètres « Séparateur CSV » ou « Délimiteur de texte » incorrects.

1.  **Ouvrez votre fichier CSV** dans un éditeur de texte brut (comme Notepad, Sublime Text, VS Code, ou même Excel/Google Sheets mais enregistrez-le ensuite à nouveau en CSV).
2.  **Identifiez le séparateur :** Regardez comment les valeurs sont séparées. Est-ce une virgule (`,`), un point-virgule (`;`) ou une tabulation ? Sélectionnez le bon dans les paramètres du module.
3.  **Identifiez le délimiteur :** Recherchez les caractères encadrant le texte, généralement des guillemets doubles (`"`). S'ils sont présents, assurez-vous que le « Délimiteur de texte » est défini sur « Guillemet double ».
4.  **Ligne d'en-tête :** Si votre CSV a un en-tête, assurez-vous que « Sauter la première ligne (en-tête) » est défini sur « OUI ».

**Q : J'ai importé des bons d'achat, mais maintenant je veux les supprimer ou les désactiver.**
R :

1.  Allez dans **Catalogue > Réductions > Règles panier** (ou **Règles de prix > Règles panier**).
2.  Trouvez la règle de bon d'achat que vous avez créée avec le module (en utilisant le « Nom » que vous avez attribué).
3.  Vous pouvez soit :
    -   **Désactiver :** Cliquez sur la coche verte à côté de la règle pour la transformer en un « X » rouge. Cela désactive tous les bons d'achat sous cette règle.
    -   **Supprimer :** Sélectionnez la règle et utilisez les actions en masse ou cliquez sur l'icône de suppression pour supprimer la règle entière et tous les codes de bon d'achat associés.

La suppression d'une règle panier est permanente et ne peut pas être annulée.

**Q : Puis-je mettre à jour des bons d'achat existants avec ce module ?**
R : Non, ce module est conçu pour importer de *nouveaux* bons d'achat. Il n'a pas de fonctionnalité pour mettre à jour des codes de bon d'achat ou des règles panier existants. Si vous devez modifier un bon d'achat existant, vous devez le faire manuellement via **Catalogue > Réductions > Règles panier**.

**Q : Pourquoi mes bons d'achat importés ne sont-ils pas cumulables avec d'autres réductions ?**
R : Vérifiez le paramètre « Cumulable avec d'autres bons d'achat » dans la configuration du module. Si vous l'avez défini sur « NON » (ce qui est souvent recommandé pour les codes uniques), les clients ne pourront pas utiliser ces bons d'achat avec d'autres réductions actives dans leur panier. Si vous souhaitez qu'ils soient cumulables, définissez-le sur « OUI » lors de l'importation.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module « Importation de bons d'achat depuis CSV ».

### 4.1 Vue d'ensemble de l'architecture

Le module `importvoucher` est un module PrestaShop standard principalement axé sur les fonctionnalités du Back Office. Il utilise les ObjectModels `CartRule` et `CartRuleProduct` du cœur de PrestaShop pour créer et gérer les codes de réduction. La logique principale du module réside dans son fichier PHP principal, gérant les téléchargements de fichiers, l'analyse CSV et les interactions avec la base de données. Il n'introduit pas de modèles MVC complexes avec des contrôleurs front ou admin dédiés, mais utilise plutôt la méthode `getContent()` pour son interface de configuration.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs front-office ou back-office dédiés dans les répertoires `controllers/front` ou `controllers/admin`. Toute la logique administrative, y compris le formulaire de configuration et le processus d'importation CSV, est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles de base (`classes/`)

Le module ne définit pas de classes personnalisées dans un répertoire `classes/`. Il interagit directement avec les ObjectModels `CartRule` et `CartRuleProduct` du cœur de PrestaShop pour créer et gérer les codes de réduction.

-   **`CartRule` (Classe de base de PrestaShop) :**

    -   Interagit avec la table de base de données `ps_cart_rule`.
    -   Le module remplit les propriétés des objets `CartRule` (par exemple, `name`, `description`, `code`, `quantity`, `quantity_per_user`, `date_from`, `date_to`, `minimum_amount`, `reduction_percent`, `reduction_amount`, `free_shipping`, `active`, `highlight`, `partial_use`, `priority`, `cumulative_with_other_rules`) en fonction de la configuration et des données CSV.
    -   La méthode `add()` de `CartRule` est utilisée pour persister les nouvelles règles de bon d'achat dans la base de données.
-   **`CartRuleProduct` (Classe de base de PrestaShop) :**

    -   Interagit avec les tables `ps_cart_rule_product_rule_group` et `ps_cart_rule_product_rule`.
    -   Utilisé lorsque l'option « Appliquer la réduction à : Produits sélectionnés » est choisie, pour lier la règle panier à des produits, catégories ou fabricants spécifiques.

### 4.4 Actifs JavaScript (`views/js/`)

-   `importvoucher/lib/voucherengine/script.js` :
    -   **Portée :** Back-office.
    -   **Objectif :** Ce script gère probablement les interactions dynamiques sur la page de configuration du module. Cela pourrait inclure :
        -   Affichage/masquage de champs en fonction des options sélectionnées (par exemple, affichage de l'entrée « Valeur » uniquement lorsque le type de réduction « Pourcentage » ou « Montant » est sélectionné).
        -   Appels AJAX pour la validation ou le traitement du formulaire.
        -   Initialisation du sélecteur de date pour « Date d'expiration (Du) » et « Date d'expiration (Au) ».
        -   Potentiellement des aperçus d'analyse CSV côté client ou la gestion des erreurs.
    -   **Interaction :** Lie des écouteurs d'événements aux éléments du formulaire (par exemple, événements `change` sur les boutons radio, `click` sur les boutons).

### 4.5 Feuilles de style CSS (`views/css/`)

-   `importvoucher/lib/voucherengine/ps16.css` :

    -   **Portée :** Back-office (probablement pour la compatibilité PrestaShop 1.6, mais peut être chargé sur des versions plus récentes pour un style général).
    -   **Objectif :** Fournit le style pour l'interface de configuration du module, garantissant son intégration visuelle avec le thème du Back Office de PrestaShop 1.6. Peut contenir un style général des éléments de formulaire, des ajustements de mise en page et des styles spécifiques basés sur des classes pour les composants du module.
    -   **Sélecteurs clés :** Cible probablement les éléments de formulaire génériques (`.form-group`, `.control-label`, `.form-control`) et potentiellement les wrappers spécifiques au module (par exemple, `#module_form_importvoucher`).
-   `importvoucher/views/css/css.css` :

    -   **Portée :** Back-office.
    -   **Objectif :** Contient des règles de style générales ou spécifiques pour la page de configuration du module. Cela pourrait remplacer ou étendre `ps16.css` pour les versions plus récentes de PrestaShop ou fournir un style unique pour les éléments personnalisés dans le modèle du module.
    -   **Sélecteurs clés :** Similaire à `ps16.css`, se concentrant sur les éléments de l'interface utilisateur du module. Les développeurs doivent inspecter ce fichier pour les noms de classe spécifiques à remplacer dans leurs thèmes d'administration personnalisés si nécessaire.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module utilise des modèles Smarty pour rendre son interface de configuration du Back Office.

-   **`importvoucher/views/backoffice.tpl`** :

    -   **Portée :** Modèle d'administration.
    -   **Objectif :** Il s'agit probablement du fichier de modèle principal rendu par la méthode `getContent()`. Il sert de conteneur pour l'ensemble du formulaire de configuration du module, y compris tous les paramètres, champs de saisie et boutons. Il inclut probablement d'autres modèles partiels.
    -   **Contenu :** Contient la structure HTML de la page de configuration du module, y compris les balises de formulaire, les groupes de champs et potentiellement des appels pour inclure d'autres fichiers `.tpl`.
-   **`importvoucher/views/csv.tpl`** :

    -   **Portée :** Modèle d'administration.
    -   **Objectif :** Ce modèle gère probablement l'affichage de la section de téléchargement du fichier CSV et des paramètres associés (séparateur, délimiteur, saut d'en-tête). C'est un modèle partiel inclus dans `backoffice.tpl`.
-   **`importvoucher/views/csv_file.tpl`** :

    -   **Portée :** Modèle d'administration.
    -   **Objectif :** Un modèle partiel plus granulaire, éventuellement spécifiquement pour le champ de saisie de fichier lui-même, ou pour afficher des informations sur le fichier CSV téléchargé.
-   **`importvoucher/views/file_settings.tpl`** :

    -   **Portée :** Modèle d'administration.
    -   **Objectif :** Ce modèle rend probablement la section « Paramètres du fichier CSV », y compris les entrées pour le séparateur CSV, le délimiteur de texte et la case à cocher « sauter la première ligne ».

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données :**
    Le module ne crée pas de tables de base de données personnalisées. Il interagit directement avec les tables de base de PrestaShop liées aux règles panier :

    -   `ps_cart_rule` : Stocke les propriétés principales de chaque règle de réduction (nom, code, dates, montant minimum, etc.).
    -   `ps_cart_rule_lang` : Stocke les champs spécifiques à la langue pour les règles panier (par exemple, `name` s'il est multilingue).
    -   `ps_cart_rule_product_rule_group` : Utilisé lors de l'application de réductions à des produits/catégories spécifiques.
    -   `ps_cart_rule_product_rule` : Définit les règles de produit réelles au sein d'un groupe.
    -   `ps_cart_rule_product_rule_exclusion` : Pour exclure des produits spécifiques d'une règle.
    -   `ps_cart_rule_carrier` : Pour les restrictions de transporteur.
    -   `ps_cart_rule_country` : Pour les restrictions de pays.
    -   `ps_cart_rule_group` : Pour les restrictions de groupe de clients.
    -   `ps_cart_rule_shop` : Pour le contexte multi-boutique.
-   **Table des hooks enregistrés :**
    La fonction principale du module est la configuration du Back Office. Bien que la description du module mentionne « Hooks Front-Office : Header, Columns, Product, or Footer », l'inventaire des fichiers fourni et la fonctionnalité typique d'un module d'importation suggèrent qu'il ne rend pas activement de contenu dans ces hooks front-office. Ces mentions pourraient être génériques ou faire référence à l'endroit où les *effets* des bons d'achat importés sont visibles (par exemple, un bon d'achat appliqué dans le panier, qui fait partie du flux de commande, potentiellement influencé par des hooks).

    Le module utilise principalement le hook suivant pour son interface Back Office :

    | Nom du hook | Moment d'exécution | Objectif technique |
    | --- | --- | --- |
    | `displayBackOfficeHeader` | Rendu dans la section `<head>` des pages du Back Office. | Utilisé pour inclure les actifs CSS et JavaScript pour la page de configuration du module. |
    | `moduleRoutes` (PrestaShop 1.7+) | Lors de l'initialisation des routes du module. | Si le module avait des contrôleurs frontaux personnalisés, ce hook définirait leurs URL. (Non applicable ici car aucun contrôleur frontal personnalisé n'est présent). |

    La logique principale du module pour *créer* des bons d'achat ne repose pas sur des hooks PrestaShop spécifiques, mais plutôt sur des appels directs aux méthodes `CartRule` déclenchés par la soumission du formulaire dans `getContent()`.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Importation de bons d'achat depuis CSV », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
