---
title: "Mise à jour gratuite des prix de produits en masse - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Mise à jour gratuite des prix de produits en masse' par MyPresta.eu."
sidebar:
  label: "Mise à jour gratuite des prix de produits en masse - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Free mass products prices update sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/free-mass-products-prices-update.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/free-mass-products-prices-update/)
>
> ---


# Mise à jour gratuite des prix de produits en masse

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration serveur spéciale n'est requise au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Mise à jour gratuite des prix de produits en masse)

Ceci est l'écran de configuration principal et unique du module « Mise à jour gratuite des prix de produits en masse ». Ici, vous définirez comment vous souhaitez ajuster les prix de vos produits.

#### **Type d'ajustement de prix**

- **Ce que fait ce paramètre :** Ce paramètre crucial détermine si vous souhaitez augmenter ou diminuer les prix de vos produits.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur « Augmenter » :* Le module ajoutera le pourcentage spécifié au prix actuel de chaque produit.
  - *Lorsqu'il est défini sur « Diminuer » :* Le module soustraira le pourcentage spécifié du prix actuel de chaque produit.
- **Valeur recommandée :** Choisissez en fonction de votre besoin commercial immédiat (par exemple, « Augmenter » pour une hausse de prix générale, « Diminuer » pour une vente).
- **Scénario / exemple de marchand :** Si vos coûts fournisseurs ont augmenté, vous sélectionneriez « Augmenter ». Si vous organisez une vente flash, vous sélectionneriez « Diminuer ».

#### **Valeur en pourcentage**

- **Ce que fait ce paramètre :** Ce champ vous permet de saisir le pourcentage exact par lequel vous souhaitez ajuster vos prix.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur « 10 » :* Si « Augmenter » est sélectionné, les prix augmenteront de 10 %. Si « Diminuer » est sélectionné, les prix diminueront de 10 %.
  - *Lorsqu'il est défini sur « 0 » :* Aucun changement de prix ne se produira.
- **Valeur recommandée :** Saisissez le pourcentage précis dont vous avez besoin. Utilisez des nombres entiers ou décimaux (par exemple, « 5 » pour 5 %, « 2.5 » pour 2.5 %).
- **Scénario / exemple de marchand :** Pour offrir une réduction de 15 % sur l'ensemble de la boutique, vous définiriez « Type d'ajustement de prix » sur « Diminuer » et « Valeur en pourcentage » sur « 15 ». Pour augmenter les prix de 7.5 %, vous définiriez « Type d'ajustement de prix » sur « Augmenter » et « Valeur en pourcentage » sur « 7.5 ».

#### **Bouton Appliquer les modifications**

- **Ce que cela fait :** Ce bouton lance le processus de mise à jour des prix.
- **Effet de cliquer sur ce bouton :** Une fois cliqué, le module traitera tous les produits de votre boutique selon le « Type d'ajustement de prix » et la « Valeur en pourcentage » que vous avez définis. **Cette action est irréversible sans une sauvegarde de la base de données.**
- **Action recommandée :** Vérifiez toujours votre « Type d'ajustement de prix » et votre « Valeur en pourcentage » avant de cliquer sur ce bouton. Assurez-vous d'avoir une sauvegarde récente de la base de données.
- **Scénario / exemple de marchand :** Après avoir soigneusement défini « Diminuer » et « 20 » pour une vente de week-end, vous cliquez sur « Appliquer les modifications » pour mettre à jour instantanément tous les prix des produits de -20 %.

:::warning NOTE IMPORTANTE
Le module « Mise à jour gratuite des prix de produits en masse » effectue une mise à jour directe de vos prix de produits. **Il n'y a pas de bouton « annuler »**. Avant d'appliquer des modifications, il est **CRUCIAL** de créer une sauvegarde complète de votre base de données PrestaShop. Cela vous permettra de restaurer vos prix à leur état précédent si vous faites une erreur ou changez d'avis.
:::

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Type d'ajustement de prix | (Sélectionner Augmenter/Diminuer) | Détermine si les prix augmenteront ou diminueront. |
| Configuration du module | Valeur en pourcentage | (Saisir le pourcentage souhaité) | Le pourcentage exact pour l'ajustement des prix. |
| Configuration du module | Bouton Appliquer les modifications | (Cliquer avec prudence) | Exécute la mise à jour des prix en masse. **Irréversible sans sauvegarde.** |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai mis à jour les prix, mais ils n'apparaissent pas sur ma boutique. Qu'est-ce qui ne va pas ?**
R1 : Après toute modification importante des données dans PrestaShop, en particulier celles liées aux produits, il est recommandé de vider le cache de votre boutique.
\* Allez dans **Paramètres avancés > Performances** dans votre Back Office.
\* Cliquez sur le bouton « Vider le cache » en haut à droite de la page.
\* Assurez-vous également que le cache de votre navigateur est vidé, ou essayez de visualiser votre boutique dans une fenêtre de navigation privée/incognito.

**Q2 : J'ai fait une erreur et mis à jour les prix incorrectement. Comment puis-je revenir en arrière ?**
R2 : Comme mentionné, ce module n'a pas de bouton « annuler ». C'est pourquoi une sauvegarde de la base de données est cruciale.
\* Si vous avez effectué une sauvegarde *avant* d'appliquer les modifications, vous devrez restaurer votre base de données à partir de cette sauvegarde. Cela nécessite généralement un accès à votre panneau de contrôle d'hébergement (par exemple, cPanel, Plesk) ou l'utilisation d'un module de sauvegarde PrestaShop.
\* Si vous *n'avez pas* effectué de sauvegarde, vous devrez ressaisir manuellement les prix corrects pour vos produits, ou utiliser le module à nouveau avec un calcul inverse (par exemple, si vous avez diminué de 20 %, vous devrez augmenter de 25 % pour revenir à la valeur d'origine, mais cela pourrait ne pas être parfaitement précis en raison des arrondis).

**Q3 : Ce module affecte-t-il les prix spécifiques ou les combinaisons ?**
R3 : Le module met à jour le *prix de base* de vos produits. Il ne gère pas directement les prix spécifiques (remises, remises par quantité) ou les impacts de prix des combinaisons de produits. Si vous avez des prix spécifiques configurés, le changement de prix de base affectera le point de départ de ces prix spécifiques.

**Q4 : Est-il possible de mettre à jour les prix uniquement pour des catégories ou des fabricants spécifiques ?**
R4 : Non, cette version gratuite du module effectue une mise à jour en masse sur *tous* les produits de votre boutique. Elle n'offre pas de filtrage par catégorie, fabricant ou autres critères. Pour des mises à jour de prix plus avancées et filtrées, vous auriez généralement besoin d'un module d'import/export ou de mise à jour en masse plus sophistiqué, souvent payant.

**Q5 : Le module semble bloqué ou ne répond pas lorsque je clique sur « Appliquer les modifications ».**
R5 : Pour les boutiques avec un très grand nombre de produits (des milliers), le processus de mise à jour peut prendre un certain temps.
\* Assurez-vous que la limite de temps d'exécution PHP de votre serveur est suffisante. Vous pourriez voir une « Erreur interne du serveur 500 » ou un délai d'attente si elle est trop faible. Il s'agit d'un problème de configuration du serveur, pas d'un bug du module.
\* Vérifiez les journaux d'erreurs de votre PrestaShop (situés dans `var/logs/` dans PrestaShop 1.7/8/9) pour toute erreur spécifique.
\* Si le problème persiste, contactez votre hébergeur ou un développeur web pour vérifier les journaux du serveur et les paramètres PHP.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Mise à jour gratuite des prix de produits en masse » est un module PrestaShop simple, principalement conçu pour l'administration du Back Office. Il suit une structure de module PrestaShop de base, tirant parti de la classe `Module` et de sa méthode `getContent()` pour la configuration. Il interagit directement avec la base de données PrestaShop pour mettre à jour les prix des produits sans contrôleurs, modèles ou interactions JavaScript complexes personnalisés. La logique du module est autonome dans son fichier PHP principal.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise **aucun** contrôleur d'administration Front-Office ou Back-Office personnalisé. Toutes les fonctionnalités sont gérées directement dans la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit **aucune** classe personnalisée et n'étend pas `ObjectModel`. Il interagit directement avec les méthodes `Product` et `Product::updatePrice()` fournies par le cœur de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut **aucun** fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut **aucun** fichier CSS personnalisé. Le style de la page de configuration est géré par le thème Back Office par défaut de PrestaShop.

### 4.6 Structure des templates Smarty (`views/templates/`)

Le module utilise deux templates Smarty simples :

- **`masspricefree/views/advert.tpl`** :
  - **Portée :** Back-office (page de configuration du module).
  - **Objectif :** Probablement utilisé pour afficher une publicité ou un message promotionnel de MyPresta.eu dans l'interface de configuration du module. Il est généralement rendu en haut ou en bas de la sortie de `getContent()`.
- **`masspricefree/views/script.tpl`** :
  - **Portée :** Back-office (page de configuration du module).
  - **Objectif :** Ce template pourrait contenir du JavaScript en ligne ou de simples éléments HTML faisant partie du formulaire de configuration du module, bien que la description du module suggère un JS minimal. Compte tenu de la simplicité du module, il est plus probable qu'il s'agisse d'un espace réservé ou qu'il contienne des éléments d'interface utilisateur très basiques.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de la base de données** :

  - Ce module ne crée **aucune** table de base de données personnalisée.
  - Il modifie directement les données dans la table `ps_product` (spécifiquement la colonne `price`) et potentiellement `ps_product_shop` (pour les contextes multi-boutiques) en appelant les méthodes principales de PrestaShop.
  - Les paramètres de configuration (Type d'ajustement de prix, Valeur en pourcentage) sont stockés dans la table `ps_configuration` à l'aide de clés de configuration PrestaShop standard (par exemple, `PS_MASS_PRICE_FREE_TYPE`, `PS_MASS_PRICE_FREE_VALUE`).
- **Table des hooks enregistrés** :
  Ce module n'enregistre **aucun** hook spécifique pour l'affichage front-office ou les actions back-office au-delà des standards `displayBackOfficeHeader` (implicitement pour la configuration du module) et `actionModuleInstall`/`actionModuleUninstall`. Sa fonction principale est une manipulation directe de la base de données déclenchée par la soumission du formulaire d'administration.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayBackOfficeHeader` | Rendu dans la section `<head>` du Back Office. | Utilisé par `getContent()` pour potentiellement charger des actifs ou afficher des avis, bien que non explicitement utilisé pour des actifs personnalisés dans ce module. |
| `actionModuleInstall` | Déclenché lors de l'installation du module. | Utilisé pour définir les valeurs de configuration par défaut dans `ps_configuration`. |
| `actionModuleUninstall` | Déclenché lors de la désinstallation du module. | Utilisé pour nettoyer les valeurs de configuration de `ps_configuration`. |

### 4.8 Fichier principal du module (`masspricefree/index.php`)

La logique principale réside dans `masspricefree/index.php`.

- **Nom de la classe :** `MassPriceFree`
- **Classe parente :** `Module`
- **Méthodes clés :**
  - `__construct()` : Initialise les propriétés du module (nom, onglet, version, auteur, need\_instance, bootstrap).
  - `install()` : Enregistre le module, définit les valeurs de configuration par défaut (par exemple, `PS_MASS_PRICE_FREE_TYPE` sur 'increase', `PS_MASS_PRICE_FREE_VALUE` sur '0').
  - `uninstall()` : Supprime les valeurs de configuration.
  - `getContent()` : C'est la méthode principale pour la fonctionnalité du module.
    - Gère la soumission du formulaire (`Tools::isSubmit('submitMassPriceFree')`).
    - Récupère `price_type` et `price_value` du formulaire soumis.
    - Met à jour `ps_configuration` avec les nouveaux paramètres.
    - **De manière cruciale, elle itère sur tous les produits actifs (`Product::getProducts(Context::getContext()->language->id, 0, 0, 'id_product', 'ASC', false, true)`) et met à jour leurs prix en fonction du pourcentage et du type configurés.** Elle utilise `Product::updatePrice()` pour cela.
    - Rend le formulaire de configuration à l'aide de `displayForm()` et inclut les templates `advert.tpl` et `script.tpl`.
  - `displayForm()` : Génère le HTML pour le formulaire de configuration du module, y compris les boutons radio pour l'augmentation/diminution et le champ de saisie pour le pourcentage.

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, les corrections de bugs et le support dédié du module « Mise à jour gratuite des prix de produits en masse », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité du module.
