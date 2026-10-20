---
title: "Augmenter la limite de caractères dans la description de produit - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Augmenter la limite de caractères dans la description de produit' par MyPresta.eu."
sidebar:
  label: "Augmenter la limite de caractères dans la description de produit - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Increase characters limit in product description sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/increase-characters-limit-in-product-description.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/increase-characters-limit-in-product-description/)
>
> ---


# Augmenter la limite de caractères dans la description de produit

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5 (Toujours étendu à PHP 8.5 pour l'avenir)
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est requise au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du nom du module pour accéder à ses paramètres. Il s'agit de l'écran de configuration principal et unique pour ce module.

#### Paramètres et options :

1.  **Longueur de la description du produit**

    *   **Ce que fait ce paramètre :** Ce champ contrôle le nombre maximal de caractères autorisés dans le champ principal « Description » pour tous vos produits dans le Back Office de PrestaShop. La limite par défaut de PrestaShop est de 21 844 caractères.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur un nombre plus élevé :* Vous pourrez saisir plus de caractères dans le champ de description du produit lors de l'édition des produits. Cela permet un contenu plus détaillé.
        *   *Lorsqu'il est défini sur un nombre inférieur (non recommandé) :* Vous restreindriez votre capacité à ajouter du contenu détaillé, tronquant potentiellement les descriptions plus longues existantes.
    *   **Valeur recommandée :** Un nombre significativement plus élevé comme `65535` ou `16777215` (ce qui correspond aux limites `MEDIUMTEXT` ou `LONGTEXT` de MySQL, supprimant efficacement les limites pratiques pour la plupart des contenus). Vous pouvez également le définir sur `0` ou le laisser vide pour supprimer entièrement la limite et utiliser le maximum possible.
    *   **Scénario / exemple de marchand :** Vous vendez des gadgets de haute technologie et devez inclure des spécifications techniques étendues, des listes de compatibilité et des guides d'utilisation directement dans la description du produit. Le fait de définir cette valeur sur `65535` vous assure un espace suffisant.
2.  **Longueur du nom du produit**

    *   **Ce que fait ce paramètre :** Ce champ contrôle le nombre maximal de caractères autorisés pour le champ « Nom du produit » pour tous vos produits. La limite par défaut de PrestaShop est généralement de 128 ou 255 caractères, selon la version.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur un nombre plus élevé :* Vous pouvez utiliser des noms de produits plus longs, ce qui peut être utile pour des produits très spécifiques, y compris les numéros de modèle, ou à des fins de référencement où des titres plus longs et descriptifs sont bénéfiques.
        *   *Lorsqu'il est défini sur un nombre inférieur (non recommandé) :* Vous restreindriez la dénomination des produits, ce qui pourrait causer des problèmes avec les produits existants ou rendre plus difficile la différenciation des articles.
    *   **Valeur recommandée :** Un nombre plus élevé comme `512` ou `1024` si vous avez besoin de noms de produits très longs. Pour la plupart des boutiques, la valeur par défaut est suffisante, mais si vous avez des besoins spécifiques (par exemple, inclure des numéros de pièce complets ou des descriptions de modèle détaillées), l'augmentation de cette valeur est utile.
    *   **Scénario / exemple de marchand :** Vous vendez des équipements industriels, et les noms de produits incluent souvent le fabricant, le modèle, les caractéristiques spécifiques et les numéros de version (par exemple, « Mélangeur industriel robuste XYZ Corp. Modèle 5000-A avec contrôle de vitesse variable et trémie en acier inoxydable »). L'augmentation de cette limite à `512` vous permet d'adapter le nom complet et descriptif.
3.  **PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG** (Ceci est un paramètre PrestaShop standard, non directement contrôlé par le module, mais souvent pertinent pour l'édition de contenu)

    *   **Ce que fait ce paramètre :** Ce paramètre de base de PrestaShop détermine si les employés peuvent sélectionner la langue d'un champ de formulaire directement dans le formulaire, ou si la langue du formulaire est déterminée par la langue du back office de l'employé. Ce n'est pas un paramètre de module mais il est souvent visible ou pertinent lors de la gestion de contenu multilingue.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Les employés peuvent changer la langue des champs de texte (comme les descriptions de produits) directement sur la page d'édition du produit, ce qui leur permet de saisir du contenu pour différentes langues sans changer toute la langue de leur back office.
        *   *Lorsqu'il est désactivé :* La langue des champs de texte correspondra à la langue actuelle du back office de l'employé. Pour modifier le contenu dans une autre langue, l'employé doit changer la langue de son back office.
    *   **Valeur recommandée :** Généralement **OUI** pour les boutiques multilingues avec plusieurs éditeurs de contenu, car cela améliore le flux de travail.
    *   **Scénario / exemple de marchand :** Vous avez un éditeur de contenu francophone et un éditeur de contenu anglophone. Si cette option est activée, l'éditeur français peut rédiger la description française, puis basculer le menu déroulant de la langue vers l'anglais pour rédiger la description anglaise, le tout sur la même page produit.

#### 2.1.1 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Config du module | Longueur de la description du produit | `65535` ou `0` (aucune limite) | Augmente le nombre maximal de caractères pour les descriptions de produits. Permet un contenu plus détaillé et un meilleur référencement. |
| Config du module | Longueur du nom du produit | `512` ou `1024` | Augmente le nombre maximal de caractères pour les noms de produits. Utile pour les titres de produits très spécifiques ou descriptifs. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : J'ai augmenté la limite de caractères, mais mes descriptions de produits semblent toujours tronquées sur le front office. Qu'est-ce qui ne va pas ?**
R : Il s'agit généralement d'un problème lié au thème, et non au module.
- **Vérifiez les paramètres d'affichage de votre thème :** Certains thèmes peuvent avoir leur propre CSS ou JavaScript qui tronque les textes longs pour s'adapter à une mise en page spécifique. Vous devrez peut-être consulter la documentation de votre thème ou un développeur web pour les ajuster.
- **Videz le cache Smarty :** Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop, faites défiler jusqu'à « Vider le cache » et cliquez sur « Vider le cache ». Parfois, d'anciens fichiers de modèle sont mis en cache.
- **Vérifiez dans le Back Office :** Vérifiez que la description complète est correctement enregistrée sur la page d'édition du produit dans votre Back Office. Si elle est tronquée là, alors le module n'a peut-être pas été appliqué correctement (bien que cela soit rare).

**Q : Ce module affecte-t-il le référencement ?**
R : Indirectement, oui, de manière très positive. En vous permettant de rédiger des descriptions de produits plus longues, plus détaillées et riches en mots-clés, vous fournissez plus de contenu aux moteurs de recherche à explorer et à indexer. Cela peut conduire à de meilleurs classements pour les requêtes de recherche pertinentes et attirer plus de trafic organique vers vos pages de produits.

**Q : Ce module va-t-il ralentir ma boutique ?**
R : Non, ce module a un impact négligeable sur les performances de la boutique. Il modifie principalement les définitions de colonnes de la base de données lors de l'installation/configuration. Une fois configuré, il n'ajoute aucun traitement complexe ni script front-office qui ralentirait les temps de chargement des pages. Le seul « ralentissement » potentiel pourrait être si vous écrivez des descriptions extrêmement longues qui prennent plus de temps à charger depuis la base de données, mais cela est généralement minime et compensé par les avantages du référencement.

**Q : J'ai modifié les limites, mais je ne vois pas le changement sur la page d'édition du produit. Que dois-je faire ?**
R :
- **Enregistrez la configuration du module :** Assurez-vous d'avoir cliqué sur le bouton « Enregistrer » après avoir modifié les limites de caractères sur la page de configuration du module.
- **Videz le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ».
- **Actualisez votre navigateur :** Parfois, le navigateur met en cache d'anciens formulaires. Effectuez une actualisation forcée (Ctrl+F5 ou Cmd+Maj+R).
- **Déconnectez-vous et reconnectez-vous :** Pour certaines modifications administratives, se déconnecter et se reconnecter au Back Office peut garantir que toutes les données de session sont actualisées.

**Q : Y a-t-il une limite maximale que je peux définir ?**
R : Bien que le module vous permette de définir pratiquement n'importe quel nombre, la limite pratique est déterminée par les capacités de votre base de données. Pour les champs `TEXT` dans MySQL, le maximum est de `65 535` caractères. Pour `MEDIUMTEXT`, c'est `16 777 215` caractères, et pour `LONGTEXT`, c'est `4 294 967 295` caractères. Définir `0` ou laisser le champ vide utilisera généralement le type `TEXT` le plus grand possible, supprimant efficacement toute limite pratique pour la plupart des contenus. Pour les noms de produits, `255` ou `512` caractères sont généralement plus que suffisants.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Augmenter la limite de caractères dans la description de produit » est un module PrestaShop léger principalement conçu pour modifier le schéma de la base de données pour les champs de texte liés aux produits. Il fonctionne en modifiant le `type` et la `size` de colonnes spécifiques dans la table `ps_product_lang` (pour les descriptions) et les tables `ps_product` / `ps_product_lang` (pour les noms) lors de son installation et de sa configuration. Il n'introduit pas de contrôleurs front-office, de classes personnalisées ou de JavaScript/CSS complexes. Sa fonctionnalité principale est exécutée via les méthodes `install()` et `getContent()` de la classe principale du module.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient **pas** de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la configuration est gérée directement dans la méthode `getContent()` du module.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module n'introduit **pas** de classes personnalisées ou de définitions `ObjectModel`. Il interagit directement avec les tables de base de données et les paramètres de configuration existants de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut **pas** de fichiers JavaScript personnalisés.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut **pas** de fichiers CSS personnalisés.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Ce module n'inclut **pas** de fichiers de modèle Smarty personnalisés. Le formulaire de configuration est rendu directement dans la méthode `getContent()` à l'aide des composants `HelperForm` standard de PrestaShop.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données

Le module interagit principalement avec les tables principales de PrestaShop suivantes :

-   `ps_product_lang` :
    *   **Colonne `description`** : Modifiée en un type `TEXT` plus grand (par exemple, `MEDIUMTEXT` ou `LONGTEXT`) pour accueillir plus de caractères.
    *   **Colonne `description_short`** : Non directement modifiée par ce module, mais souvent liée.
    *   **Colonne `name`** : Modifiée en un type `VARCHAR` plus grand (par exemple, `VARCHAR(512)`) pour accueillir plus de caractères.
-   `ps_configuration` :
    *   `chr_max_description_length` : Stocke la longueur maximale configurée pour les descriptions de produits.
    *   `chr_max_name_length` : Stocke la longueur maximale configurée pour les noms de produits.
    *   `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` : Une clé de configuration PrestaShop standard, non créée par le module, mais souvent référencée dans le contexte de l'édition de contenu.

La méthode `install()` du module contient des requêtes SQL pour modifier ces colonnes de table. La méthode `uninstall()` tente d'annuler ces modifications, bien qu'une vérification manuelle puisse être nécessaire en fonction de l'état de la base de données.

#### Tableau des hooks enregistrés

Ce module n'enregistre **aucun** hook d'affichage front-office ou back-office. Sa fonctionnalité est entièrement pilotée par le backend en modifiant le schéma de la base de données.

La méthode `install()` du module peut utiliser implicitement `Configuration::updateValue()` qui n'enregistre pas directement les hooks mais stocke les valeurs.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Augmenter la limite de caractères dans la description de produit », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
