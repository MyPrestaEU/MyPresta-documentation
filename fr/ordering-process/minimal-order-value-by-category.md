---
title: "Valeur de commande minimale par catégorie - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Valeur de commande minimale par catégorie' par MyPresta.eu."
sidebar:
  label: "Valeur de commande minimale par catégorie - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Minimal order value by category sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimal-order-value-by-category.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/minimal-order-value-by-category/)
>
> ---


# Valeur de commande minimale par catégorie

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont habituellement disponibles par défaut sur la plupart des environnements d'hébergement.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module, accessible immédiatement après l'installation ou en cliquant sur « Configurer » depuis le Gestionnaire de modules.

- **Ce que fait ce paramètre :** Cet écran sert principalement de point d'entrée. Bien que la logique principale du module soit gérée via un écran d'administration dédié, cette page de configuration initiale garantit que le module est correctement installé et fournit un lien ou une redirection vers l'interface de gestion principale.
- **Effet de la modification de ce paramètre :** Généralement, cet écran n'a pas de commutateurs directs ou de champs de saisie pour le marchand. Son objectif principal est de confirmer le statut du module et de vous guider vers l'étape suivante.
- **Valeur recommandée :** Aucune valeur directe à définir ici. Assurez-vous simplement que le module est activé.
- **Scénario / exemple pour le marchand :** Après l'installation, vous atterrirez ici. Vous pourriez voir un message confirmant l'installation et un bouton ou un lien vers « Gérer les valeurs de commande minimales » ou similaire, qui vous mènera à l'écran `AdminMobcController` dédié.

### 2.2 Écran d'administration dédié : Gestion de la valeur de commande minimale par catégorie (Back Office > Modules > Valeur de commande minimale par catégorie)

Ceci est l'interface de gestion principale où vous définissez et contrôlez toutes vos valeurs de commande minimales spécifiques à une catégorie. Vous trouverez généralement un nouvel élément de menu sous « Modules » ou « Catalogue » (selon votre version de PrestaShop et le hook du module) nommé « Valeur de commande minimale par catégorie » ou similaire.

**Nom de l'écran et emplacement du menu :**
Vous trouverez cet écran en naviguant vers **Modules > Valeur de commande minimale par catégorie** dans le menu de votre Back Office PrestaShop.

**Actions et paramètres disponibles :**
Cet écran présente une liste (grille) de toutes vos règles de valeur de commande minimale actuellement définies. Pour chaque règle, vous verrez généralement :

- **Nom de la catégorie :** Le nom de la catégorie PrestaShop à laquelle la règle s'applique.
- **Valeur minimale :** Le montant de commande minimum requis pour les produits de cette catégorie.
- **Devise :** La devise dans laquelle la valeur minimale est définie (généralement la devise par défaut de votre boutique, par exemple, USD, EUR).
- **Actions :** Boutons pour « Modifier » ou « Supprimer » une règle existante.

Vous trouverez également un bouton, généralement en haut à droite, pour **« Ajouter une nouvelle règle »** ou **« Ajouter une nouvelle valeur de commande minimale »**. Cliquer dessus ouvrira un formulaire où vous pourrez :

1. **Sélectionner la catégorie :**

   - **Ce que fait ce paramètre :** Vous permet de choisir à quelle catégorie PrestaShop existante cette règle de valeur de commande minimale s'appliquera.
   - **Effet de la modification de ce paramètre :** La sélection d'une catégorie lie la règle à tous les produits de cette catégorie (et de ses sous-catégories, selon la logique du module).
   - **Valeur recommandée :** Sélectionnez la catégorie spécifique à laquelle vous souhaitez appliquer la valeur de commande minimale.
   - **Scénario / exemple pour le marchand :** Vous souhaitez définir un minimum pour votre catégorie « Vente en gros ». Vous sélectionneriez « Vente en gros » dans la liste déroulante.
2. **Valeur de commande minimale :**

   - **Ce que fait ce paramètre :** Définit le montant monétaire que les clients doivent dépenser pour des produits *au sein de la catégorie sélectionnée* avant de pouvoir poursuivre leur commande.
   - **Effet de la modification de ce paramètre :**
     - *Lorsqu'une valeur est définie (par exemple, 50.00) :* Les clients doivent avoir au moins 50.00 unités de votre devise par défaut de produits de la catégorie sélectionnée dans leur panier. Sinon, ils seront bloqués au paiement avec un message.
     - *Lorsqu'il est laissé vide ou défini à 0 :* Cette règle serait effectivement désactivée pour la catégorie, permettant n'importe quelle valeur. Cependant, il est préférable de supprimer la règle si vous n'en avez pas besoin.
   - **Valeur recommandée :** Une valeur numérique positive reflétant votre minimum souhaité (par exemple, `25.00`, `100.00`).
   - **Scénario / exemple pour le marchand :** Pour votre catégorie « Vente en gros », vous définissez ceci à `100.00`. Un client avec 90 € de produits en gros ne peut pas passer à la caisse tant qu'il n'a pas ajouté 10 € supplémentaires.
3. **Bouton Enregistrer :**

   - **Ce que cela fait :** Applique les modifications ou crée la nouvelle règle.
   - **Effet :** La nouvelle règle sera active immédiatement, et le système commencera à appliquer la valeur de commande minimale pour la catégorie sélectionnée.

**Flux de travail recommandé pour la gestion quotidienne de la boutique :**

1. **Examiner les règles existantes :** Vérifiez périodiquement votre liste de règles pour vous assurer qu'elles sont toujours pertinentes pour votre stratégie commerciale.
2. **Ajouter de nouvelles règles :** Si vous introduisez de nouvelles catégories de produits qui nécessitent des minimums spécifiques (par exemple, une nouvelle ligne B2B), ajoutez une règle pour celles-ci.
3. **Modifier les règles existantes :** Ajustez les valeurs minimales en fonction des changements de prix des produits, des conditions du marché ou des stratégies promotionnelles.
4. **Supprimer les règles obsolètes :** Supprimez les règles pour les catégories qui ne nécessitent plus de minimum ou qui ont été abandonnées.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | (Aucun paramètre direct) | N/A | Point d'entrée du module ; confirme l'installation et redirige vers l'écran de gestion. |
| Gestion de la valeur de commande minimale par catégorie | Ajouter une nouvelle règle / Modifier une règle > Sélectionner la catégorie | N/A | Lie une valeur de commande minimale à une catégorie de produit PrestaShop spécifique. |
| Gestion de la valeur de commande minimale par catégorie | Ajouter une nouvelle règle / Modifier une règle > Valeur de commande minimale | Votre minimum souhaité (par exemple, `50.00`) | Définit le montant monétaire requis pour les produits de la catégorie choisie. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai défini une valeur minimale, mais cela ne fonctionne pas. Les clients peuvent toujours passer à la caisse avec moins.**
R :

- **Vérifier l'état du module :** Assurez-vous que le module est activé dans **Modules > Gestionnaire de modules**.
- **Vérifier la configuration de la règle :** Allez dans **Modules > Valeur de commande minimale par catégorie** et confirmez que la règle pour la catégorie spécifique est active, a une valeur supérieure à zéro et est correctement attribuée à la catégorie prévue.
- **Vider le cache :** Parfois, le cache de PrestaShop peut empêcher les modifications d'apparaître immédiatement. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes).
- **Affectation de la catégorie de produit :** Vérifiez à nouveau que les produits en question sont bien affectés à la catégorie pour laquelle vous avez défini le minimum.

**Q2 : Le message affiché aux clients n'est pas clair ou ne correspond pas à la langue de ma boutique.**
R :

- **Traductions du module :** Le module devrait prendre en charge le système de traduction de PrestaShop. Allez dans **International > Traductions**, sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez « Valeur de commande minimale par catégorie ». Vous pouvez ensuite personnaliser les messages d'avertissement pour qu'ils soient plus spécifiques ou les traduire dans d'autres langues.
- **Style de thème personnalisé :** Si le message apparaît mais semble déplacé, le CSS de votre thème pourrait remplacer les styles du module. Un webmaster peut vous aider à ajuster le fichier `mobc.css` ou à ajouter du CSS personnalisé à votre thème pour assurer un affichage correct.

**Q3 : Puis-je définir des minimums différents pour différents groupes de clients (par exemple, vente au détail vs vente en gros) ?**
R : La version actuelle du module « Valeur de commande minimale par catégorie » se concentre sur les minimums à l'échelle de la catégorie, et non sur ceux spécifiques aux groupes de clients. Si vous avez besoin de cette fonctionnalité avancée, vous devrez peut-être utiliser des catégories distinctes pour différents groupes de clients (par exemple, « Produits en gros » vs « Produits au détail ») et appliquer des règles à ces catégories distinctes.

**Q4 : Que se passe-t-il si un produit est dans plusieurs catégories, et qu'une seule a un minimum ?**
R : Le module calcule la valeur totale des produits *dans chaque* catégorie qui a une règle de minimum. Si un produit est dans la Catégorie A (pas de minimum) et la Catégorie B (minimum 50 €), sa valeur contribuera au total de la Catégorie B s'il est ajouté au panier. Le client doit atteindre le minimum pour la Catégorie B en fonction de la somme de tous les produits de son panier qui appartiennent à la Catégorie B.

**Q5 : J'ai supprimé une catégorie, mais la règle correspondante est toujours affichée dans la configuration du module.**
R : Si vous supprimez une catégorie directement depuis le menu Catalogue de PrestaShop, la règle du module associée à cette catégorie pourrait devenir orpheline. Vous devez vous rendre manuellement dans **Modules > Valeur de commande minimale par catégorie** et supprimer la règle correspondante de la liste pour maintenir votre configuration propre.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Valeur de commande minimale par catégorie » (`mobc`) suit un modèle MVC PrestaShop standard. Il étend principalement `Module` pour sa fonctionnalité principale et `AdminController` pour son interface de gestion du back-office. Les interactions du front-office sont gérées via `ModuleFrontController` pour les requêtes AJAX et le rendu des templates. Le module n'utilise pas de classes `ObjectModel` personnalisées mais s'appuie sur les entités `Category` et `Product` du cœur de PrestaShop pour la récupération des données. La configuration est stockée dans `ps_configuration` et une table de base de données personnalisée pour les mappages catégorie-valeur.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :

  - `controllers/front/ajax.php`
    - **Nom de la classe :** `MobcAjaxModuleFrontController` (étend `ModuleFrontController`)
    - **Responsabilité :** Gère les requêtes AJAX du front-office, principalement pour vérifier le contenu du panier par rapport aux valeurs de commande minimales définies par catégorie. Il reçoit probablement les données du panier et renvoie une réponse JSON indiquant si les minimums sont respectés et, si non, quelles catégories sont déficientes et de combien. Ceci est crucial pour la validation en temps réel sur la page du panier sans rechargement complet de la page.
  - `controllers/front/index.php`
    - **Nom de la classe :** `MobcIndexModuleFrontController` (étend `ModuleFrontController`)
    - **Responsabilité :** Ce contrôleur pourrait servir de solution de repli ou de simple point d'entrée, mais étant donné la fonctionnalité du module, son rôle principal est probablement minimal, redirigeant éventuellement ou servant une page de base s'il est directement accédé. La logique principale du front-office est attendue dans `ajax.php`.
- **Contrôleurs Admin Back-Office** :

  - `controllers/admin/AdminMobc.php`
    - **Nom de la classe :** `AdminMobcController` (étend `ModuleAdminController`)
    - **Nom de l'onglet :** Valeur de commande minimale par catégorie (ou similaire, généralement sous « Modules » ou « Catalogue »).
    - **Entité gérée :** Gère l'entité `mobc` personnalisée, qui représente les mappages catégorie-valeur minimale.
    - **Responsabilité :** Fournit l'interface CRUD (Créer, Lire, Mettre à jour, Supprimer) pour la gestion des règles de valeur de commande minimale. Il gère l'affichage des règles existantes dans une grille, l'affichage des formulaires pour ajouter/modifier des règles (sélection des catégories, saisie des valeurs minimales) et le traitement des soumissions de formulaires. Il interagit avec la table de base de données du module pour les entrées `mobc`.
  - `controllers/admin/index.php`
    - **Nom de la classe :** `AdminMobcIndexController` (étend `ModuleAdminController`)
    - **Responsabilité :** Similaire au `index.php` du front-office, cela pourrait être un espace réservé ou un simple redirigeur. La logique d'administration principale réside dans `AdminMobc.php`.

### 4.3 Classes et modèles principaux (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que la gestion des données du module pour les mappages catégorie-valeur est effectuée directement dans le `AdminMobcController` ou `index.php` (fichier principal du module) à l'aide de `Db::getInstance()` ou en étendant un `ObjectModel` générique dans le fichier principal du module lui-même sans créer de fichier de classe dédié.

Étant donné que l'`AdminMobcController` gère une entité « mobc », il est fort probable que l'`AdminMobcController` définisse ses `$this->object` et `$this->fields_list` directement, ou qu'il y ait une définition `ObjectModel` implicite dans le fichier `mobc.php` principal que le contrôleur utilise.

### 4.4 Actifs JavaScript (`views/js/`)

- `mobc/views/js/mobc.js`
  - **Portée :** Front-office.
  - **Responsabilité :** Ce script est crucial pour la validation en temps réel du panier. Il est probable qu'il :
    - Lie des écouteurs d'événements aux changements de quantité du panier, aux suppressions de produits ou aux chargements de page sur la page du panier.
    - Déclenche des appels AJAX vers `controllers/front/ajax.php` pour envoyer les données actuelles du panier.
    - Reçoit la réponse JSON du contrôleur AJAX.
    - Met à jour dynamiquement le DOM sur la page du panier pour afficher des messages d'avertissement si les minimums ne sont pas respectés.
    - Désactive/active le bouton de paiement en fonction du résultat de la validation.
    - Peut inclure une logique pour afficher des messages pop-up ou mettre en évidence les catégories problématiques.

### 4.5 Feuilles de style CSS (`views/css/`)

- `mobc/views/css/mobc.css`
  - **Portée :** Style client du front-office.
  - **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :** Cette feuille de style est responsable de la présentation visuelle des messages d'avertissement affichés sur la page du panier. Elle définira les styles pour :
    - Les conteneurs des messages d'avertissement (par exemple, `div.mobc-warning-message`).
    - Les éléments de texte dans les avertissements (par exemple, `span.mobc-category-name`, `span.mobc-remaining-amount`).
    - Potentiellement le style du bouton de paiement désactivé ou d'autres repères visuels.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer dans leur thème :** Les développeurs peuvent inspecter le code HTML généré sur la page du panier pour identifier les noms de classe spécifiques (par exemple, `.mobc-alert`, `.mobc-error-list`, `.mobc-checkout-blocked`) et les remplacer dans le `custom.css` ou `theme.css` de leur thème pour correspondre à l'image de marque de la boutique.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :
  - `mobc/views/templates/front/displayShoppingCart.tpl`
    - **Hook :** Ce template est probablement rendu dans un hook sur la page du panier, tel que `displayShoppingCartFooter` ou `displayShoppingCartExtraContent`.
    - **Sortie de bloc visuel :** Il génère la structure HTML des messages d'avertissement qui informent les clients des valeurs de commande minimales non atteintes pour les catégories. Ce template contiendra des espaces réservés pour les noms de catégorie, les montants requis et le montant restant nécessaire, qui sont remplis par le JavaScript et le contrôleur AJAX.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - `ps_mobc_category_value` (ou similaire, basé sur l'entité de `AdminMobcController`) : Cette table personnalisée stocke le mappage entre les ID de catégorie et leurs valeurs de commande minimales respectives.
    - `id_mobc_category_value` (Clé primaire, INT)
    - `id_category` (INT, Clé étrangère vers `ps_category.id_category`)
    - `min_value` (DECIMAL, stocke le montant monétaire minimum)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - `ps_configuration` : Table de configuration standard de PrestaShop. Le module pourrait y stocker ses paramètres généraux (s'il y en a, bien qu'aucun n'ait été explicitement détecté), préfixés par `MOBC_`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Pour inclure `mobc.css` et `mobc.js` pour la fonctionnalité du front-office. |
| `displayShoppingCart` | Sur la page du panier, généralement avant ou après le résumé du panier. | Pour rendre `displayShoppingCart.tpl` afin d'afficher les messages d'avertissement. |
| `actionCartSave` | Après l'enregistrement d'un panier (par exemple, produit ajouté/supprimé, quantité modifiée). | Pour déclencher la logique du module afin de réévaluer les minimums de catégorie et potentiellement mettre à jour l'état du panier ou les variables de session. |
| `actionFrontControllerSetMedia` | Avant qu'un contrôleur frontal ne rende sa sortie, permettant aux modules d'ajouter du JS/CSS. | Pour enregistrer les fichiers JavaScript et CSS spécifiques au module pour le front-office. |
| `actionAdminControllerSetMedia` | Avant qu'un contrôleur d'administration ne rende sa sortie. | Pour enregistrer les fichiers JavaScript et CSS spécifiques au module pour le back-office (par exemple, pour l'`AdminMobcController`). |
| `displayAdminProductsExtra` (ou similaire) | Sur la page d'édition du produit dans le back-office. | Potentiellement pour afficher des informations sur les minimums de catégorie liés au produit actuel, bien que non explicitement confirmé par le dossier. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Valeur de commande minimale par catégorie », veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes concernant la fonctionnalité et la configuration du module.
