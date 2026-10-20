---
title: "Masquer les caractéristiques sélectionnées - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop « Masquer les caractéristiques sélectionnées » par MyPresta.eu."
sidebar:
  label: "Masquer les caractéristiques sélectionnées - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Hide selected features sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/hide-selected-features.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/hide-selected-features/)
>
> ---


# Masquer les caractéristiques sélectionnées

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Vous pouvez accéder à cette page en naviguant vers **Modules > Gestionnaire de modules** et en recherchant « Masquer les caractéristiques sélectionnées », puis en cliquant sur « Configurer ».

Cet écran présente une liste de toutes les caractéristiques de produit actuellement définies dans votre boutique PrestaShop. Pour chaque caractéristique, vous verrez un interrupteur à bascule pour contrôler sa visibilité.

- **Ce que fait ce paramètre :** Cette section liste toutes vos caractéristiques de produit existantes (par exemple, « Matériau », « Couleur », « Poids », « Dimensions »). À côté de chaque caractéristique, il y a un interrupteur qui contrôle si cette caractéristique spécifique sera affichée sur vos pages produit dans le front office.
- **Effet de la modification de ce paramètre :**
  - *Lorsque activé (interrupteur sur ON) :* La caractéristique sera visible par les clients sur toutes les pages produit où elle est assignée. C'est le comportement par défaut de PrestaShop.
  - *Lorsque désactivé (interrupteur sur OFF) :* La caractéristique sera masquée aux clients sur toutes les pages produit, même si elle est assignée à un produit. Elle existera toujours dans votre back office pour un usage interne ou un filtrage.
- **Valeur recommandée :** Cela dépend entièrement de vos besoins commerciaux.
  - **Activez** les caractéristiques qui sont cruciales pour la prise de décision du client (par exemple, « Matériau » pour les vêtements, « Capacité » pour l'électronique).
  - **Désactivez** les caractéristiques qui sont des notes internes, des spécifications techniques non pertinentes pour le client moyen, ou des informations redondantes.
- **Scénario / exemple de marchand :**
  - **Scénario 1 (Masquer les notes internes) :** Vous utilisez une caractéristique appelée « SKU Fournisseur » pour suivre les codes de produit internes. Cette information n'est pas utile pour les clients. Vous **désactiveriez** la caractéristique « SKU Fournisseur » ici pour garder vos pages produit propres.
  - **Scénario 2 (Simplifier l'affichage) :** Vous vendez des t-shirts et avez des caractéristiques comme « Matériau : Coton », « Longueur des manches : Courtes », « Encolure : Ronde ». Vous décidez que la « Longueur des manches » et l'« Encolure » sont généralement claires à partir de l'image du produit et vous voulez mettre l'accent sur le « Matériau ». Vous **désactiveriez** la « Longueur des manches » et l'« Encolure » et **activeriez** le « Matériau ».

**Autres clés de configuration (Internes/Avancées) :**
Vous pourriez voir d'autres clés de configuration comme `mypresta_updates`, `update_`, `updatev_`, `hidefeatures_OSTATE`, `PS_OS_PREPARATION`, `hidefeatures_MIN_CHARGE`. Celles-ci sont généralement des paramètres de module internes liés aux mises à jour, aux états de commande ou aux frais minimums, et ne sont pas directement configurables par le marchand via l'interface principale. Elles sont généralement gérées automatiquement par le module ou utilisées pour des scénarios spécifiques et avancés non exposés dans l'interface utilisateur principale. Pour ce module, la fonctionnalité principale est gérée par les interrupteurs de caractéristiques.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 AdminFeaturesController (Back Office > Catalogue > Attributs & Caractéristiques > Caractéristiques)

Ce module surcharge l'écran de gestion standard des « Caractéristiques » de PrestaShop.

- **Nom de l'écran et emplacement du menu :** **Back Office > Catalogue > Attributs & Caractéristiques > Caractéristiques**.
- **Actions et paramètres disponibles :** Lorsque vous accédez à cet écran, vous verrez une liste de toutes vos caractéristiques de produit. Le module ajoute une nouvelle colonne ou un indicateur à cette liste, généralement étiqueté **« Actif en front office »** ou similaire. Cette colonne vous montrera en un coup d'œil si une caractéristique est actuellement configurée pour être visible ou masquée sur le front office de votre boutique, en fonction des paramètres que vous avez définis dans la page de configuration principale du module.
- **Effet des modifications :** Bien que vous ne puissiez pas modifier directement la visibilité depuis cet écran (vous le faites sur la page de configuration du module), cet écran fournit un aperçu pratique. Il vous aide à vérifier rapidement le statut front office de chaque caractéristique sans avoir à revenir au module.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Utilisez cet écran comme référence rapide lors de la gestion de vos caractéristiques de produit. Si vous ajoutez une nouvelle caractéristique, n'oubliez pas de visiter la page de configuration du module « Masquer les caractéristiques sélectionnées » pour décider si elle doit être visible par les clients.

#### 2.2.2 index.php (hidefeatures/override/controllers/admin/index.php)

Ce fichier fait partie de la structure de surcharge et sert généralement de marqueur de position ou de point d'entrée pour la logique du contrôleur surchargé. Il ne représente pas un écran de configuration distinct et visible par l'utilisateur, mais facilite plutôt la modification des pages d'administration PrestaShop existantes par le module.

- **Table / Entité gérée :** Ce fichier ne gère pas directement une table ou une entité spécifique, mais assure plutôt le chargement et l'exécution corrects du `AdminFeaturesController` surchargé.
- **Champs de formulaire et colonnes :** Aucun champ de formulaire ou colonne n'est géré directement par ce fichier spécifique. Son but est architectural, garantissant que les modifications du module à la grille/vue de gestion des « Caractéristiques » sont appliquées.
- **Effet des modifications :** Ce fichier garantit que la colonne « Actif en front office » (ou un indicateur similaire) est correctement affichée dans la liste **Catalogue > Attributs & Caractéristiques > Caractéristiques**, offrant la vue de gestion améliorée.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Liste de toutes les caractéristiques avec des bascules ON/OFF | Varie selon la caractéristique (ON pour les nouvelles caractéristiques) | Contrôle si une caractéristique de produit spécifique est affichée sur les pages produit dans le front office. ON = Visible, OFF = Masquée. |
| **AdminFeaturesController** (Catalogue > Attributs & Caractéristiques > Caractéristiques) | Colonne/indicateur « Actif en front office » | Reflète la configuration du module | Fournit un aperçu rapide du statut de visibilité front office d'une caractéristique directement dans la liste des caractéristiques. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : J'ai masqué une caractéristique, mais elle apparaît toujours sur ma page produit. Qu'est-ce qui ne va pas ?**
R :

1. **Vider le cache :** La raison la plus courante est que votre cache PrestaShop (et éventuellement le cache de votre navigateur) n'a pas été mis à jour. Allez dans **Paramètres avancés > Performances** dans votre Back Office et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). Essayez également de vider le cache de votre navigateur ou de consulter la page dans une fenêtre de navigation privée/incognito.
2. **Configuration du module enregistrée ?** Vérifiez que vous avez cliqué sur « Enregistrer » après avoir effectué des modifications dans la page de configuration du module.
3. **Caractéristique correcte ?** Assurez-vous d'avoir désactivé la caractéristique exacte que vous souhaitez masquer. Les noms de caractéristiques peuvent parfois être similaires.

**Q : Puis-je masquer des caractéristiques uniquement pour des produits spécifiques, et non globalement ?**
R : Non, ce module masque les caractéristiques globalement sur tous les produits. Si vous avez besoin d'une visibilité de caractéristique spécifique à un produit, vous géreriez généralement cela en n'assignant pas la caractéristique au produit en premier lieu, ou en utilisant une solution personnalisée plus avancée. Ce module fournit un interrupteur à l'échelle de la boutique pour les types de caractéristiques.

**Q : Le fait de masquer une caractéristique affectera-t-il mes filtres de produits ou mes résultats de recherche ?**
R : Non, ce module n'affecte que l' *affichage* des caractéristiques sur la page produit du front office. Les données de la caractéristique elles-mêmes restent dans votre base de données. Si vous utilisez des caractéristiques pour la navigation à facettes (filtres) ou la recherche, elles devraient continuer à fonctionner comme prévu, tant que la caractéristique est assignée au produit.

**Q : La colonne « Actif en front office » n'apparaît pas dans ma liste de caractéristiques (Catalogue > Attributs & Caractéristiques > Caractéristiques).**
R :

1. **Module installé et activé ?** Assurez-vous que le module « Masquer les caractéristiques sélectionnées » est correctement installé et activé dans **Modules > Gestionnaire de modules**.
2. **Cache :** Videz votre cache PrestaShop comme décrit ci-dessus.
3. **Compatibilité du thème :** Dans de rares cas, un thème fortement personnalisé peut interférer avec les surcharges. Si vider le cache ne résout pas le problème, contactez le support MyPresta.eu.

**Q : Comment traduire le texte du module (le cas échéant) ?**
R : Bien que ce module utilise principalement les noms de caractéristiques PrestaShop existants, s'il y a des textes ou des étiquettes spécifiques au module, vous pouvez les traduire en allant dans **International > Traductions** dans votre Back Office. Sélectionnez « Traductions des modules installés », choisissez votre thème, sélectionnez votre langue, puis trouvez le module « Masquer les caractéristiques sélectionnées » pour modifier ses traductions.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Masquer les caractéristiques sélectionnées » fonctionne en surchargeant les classes et contrôleurs PrestaShop de base pour injecter sa logique de visibilité. Il étend les classes `Feature` et `Product` pour ajouter une nouvelle propriété pour la visibilité en front office et modifie l'`AdminFeaturesController` pour afficher ce statut dans le back office. Le module utilise un hook personnalisé (`displayHiddenFeatures`) pour rendre la liste réelle des caractéristiques sur la page produit, lui permettant de filtrer les caractéristiques masquées avant l'affichage.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Ce module n'introduit aucun contrôleur front-office personnalisé. Toute la logique front-office est gérée via des surcharges de classes de base et des hooks.
- **Contrôleurs d'administration Back-Office** :

  - `hidefeatures/override/controllers/admin/AdminFeaturesController.php`
    - **Nom de la classe et classe parente** : `AdminFeaturesController` (surcharge le `AdminFeaturesController` de base)
    - **Responsabilité** : Cette surcharge modifie l'`AdminFeaturesController` pour afficher le statut de visibilité front-office de chaque caractéristique dans la liste des caractéristiques. Elle ajoute probablement une nouvelle colonne au tableau de la liste, permettant aux administrateurs de voir rapidement quelles caractéristiques sont masquées/visibles sans avoir à accéder à la configuration du module. Elle utilise la surcharge de la classe `Feature` pour récupérer ce statut.
  - `hidefeatures/override/controllers/admin/index.php`
    - **Nom de la classe et classe parente** : Pas un fichier de classe, généralement un `index.php` vide pour empêcher la liste des répertoires.
    - **Responsabilité** : Pratique standard pour les répertoires `override` afin d'empêcher l'accès direct et d'assurer la sécurité. Il ne contient pas de code fonctionnel.

### 4.3 Classes et modèles de base (`classes/`)

- `hidefeatures/override/classes/Feature.php`

  - **Avec quelle table de base de données interagit-il** : `ps_feature` (table principale des caractéristiques) et `ps_configuration` (pour les paramètres du module).
  - **Étend `ObjectModel`** : Oui, il étend la classe `Feature` de base qui elle-même étend `ObjectModel`.
  - **Champs `$definition`** : Cette surcharge ajoute probablement un nouveau champ au tableau `$definition` de la classe `Feature`, ou plus communément, elle ajoute une propriété dynamique à l'objet `Feature` pour stocker son statut de visibilité front-office, qui est ensuite récupéré de `ps_configuration` ou d'une table personnalisée. Il contiendrait également des méthodes pour récupérer et définir ce statut de visibilité.
  - **Méthodes publiques clés et logique métier encapsulée** :
    - Méthodes pour récupérer le statut de visibilité d'une caractéristique spécifique.
    - Méthodes pour mettre à jour le statut de visibilité, interagissant probablement avec `Configuration::updateValue()`.
    - Modifie potentiellement `getFeatures()` ou des méthodes similaires pour filtrer les résultats en fonction de la visibilité.
- `hidefeatures/override/classes/index.php`

  - **Nom de la classe et classe parente** : Pas un fichier de classe, généralement un `index.php` vide pour empêcher la liste des répertoires.
  - **Responsabilité** : Pratique standard pour les répertoires `override` afin d'empêcher l'accès direct et d'assurer la sécurité. Il ne contient pas de code fonctionnel.
- `hidefeatures/override/classes/Product.php`

  - **Avec quelle table de base de données interagit-il** : `ps_product` et `ps_feature_product`.
  - **Étend `ObjectModel`** : Oui, il étend la classe `Product` de base qui elle-même étend `ObjectModel`.
  - **Champs `$definition`** : Aucune modification directe de `$definition` n'est attendue ici.
  - **Méthodes publiques clés et logique métier encapsulée** : Cette surcharge est cruciale pour filtrer les caractéristiques sur la page produit. Elle modifie probablement des méthodes comme `getFeatures()` ou `getFrontFeatures()` (si elles existent dans la classe `Product` de base) pour :
    1. Récupérer toutes les caractéristiques assignées à un produit.
    2. Itérer à travers ces caractéristiques.
    3. Pour chaque caractéristique, vérifier son statut de visibilité en utilisant la logique de la classe `Feature` surchargée.
    4. Retourner uniquement les caractéristiques qui sont marquées comme visibles.
       Cela garantit que lorsque les caractéristiques d'un produit sont récupérées pour l'affichage, celles qui sont masquées sont automatiquement exclues.

### 4.4 Actifs JavaScript (`views/js/`)

Le module ne semble pas contenir de fichiers JavaScript personnalisés. Sa fonctionnalité est principalement côté serveur via des surcharges PHP et la logique de template Smarty.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module ne semble pas contenir de fichiers CSS personnalisés. Tout style pour la colonne ajoutée dans l'AdminFeaturesController serait généralement géré par le CSS par défaut du back-office de PrestaShop.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :

  - `hidefeatures/views/templates/front/hook/displayHiddenFeatures.tpl`
    - **Hook** : `displayHiddenFeatures` (hook personnalisé, probablement appelé dans la classe `Product` surchargée ou le `product.tpl` d'un thème)
    - **Sortie** : Ce template est responsable du rendu de la liste des caractéristiques du produit sur la page produit du front office. Il reçoit la liste filtrée des caractéristiques (après que les caractéristiques masquées aient été supprimées par la surcharge de la classe `Product`) et les affiche dans le format standard de tableau/liste des caractéristiques de PrestaShop. Les développeurs peuvent inspecter ce template pour comprendre comment les caractéristiques sont itérées et affichées.
- **Templates d'administration (`views/templates/admin/`)** :

  - `hidefeatures/views/templates/admin/_configure/helpers/list/list_content.tpl`
    - **Objectif** : Ce template est une surcharge du template de contenu de liste standard de PrestaShop, spécifiquement utilisé dans l'`AdminFeaturesController`. Il est responsable du rendu des lignes du tableau de la liste des caractéristiques dans le back office.
    - **Contenu** : Il contiendra la logique pour afficher la colonne « Actif en front office » (ou similaire) pour chaque caractéristique, montrant un indicateur visuel (par exemple, une coche, une croix rouge ou un interrupteur) basé sur le statut de visibilité de la caractéristique. Ce template fonctionne en conjonction avec la surcharge de l'`AdminFeaturesController` pour présenter les informations supplémentaires.
- **Templates front-office (`views/templates/front/`)** :

  - Pas de templates de page front-office autonomes dédiés.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne crée pas de nouvelles tables de base de données personnalisées.
  - Il stocke sa configuration (quelles caractéristiques sont masquées/visibles) dans la table `ps_configuration`. Les clés de configuration suivraient généralement un modèle comme `HIDEFEATURES_FEATURE_ID_X` ou similaire, où `X` est l'`id_feature`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHiddenFeatures` | Hook personnalisé, probablement appelé dans `product.tpl` ou via la surcharge de `Product::getFrontFeatures()`. | Rend la liste filtrée des caractéristiques du produit sur la page produit du front-office, garantissant que seules les caractéristiques visibles sont affichées. |
| `actionProductUpdate` | Après la mise à jour d'un produit. | (Implicite, si le module doit réévaluer la visibilité des caractéristiques lors de l'enregistrement du produit, bien que non explicitement listé comme un hook principal pour la fonction principale de ce module). |
| `actionFeatureSave` / `actionFeatureDelete` | Après l'enregistrement ou la suppression d'une caractéristique. | (Implicite, si le module doit mettre à jour sa configuration interne lorsque des caractéristiques sont ajoutées/supprimées). |
| `displayBackOfficeHeader` | Rend le contenu dans la section `<head>` du Back Office. | (Possible, pour injecter du JS/CSS si nécessaire pour l'interface utilisateur d'administration, mais non présent dans l'inventaire). |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et toute question concernant le module « Masquer les caractéristiques sélectionnées », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir.
