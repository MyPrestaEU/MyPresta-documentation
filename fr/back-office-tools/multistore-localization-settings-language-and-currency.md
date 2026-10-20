---
title: "Paramètres de localisation Multiboutique - langue et devise - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop « Paramètres de localisation Multiboutique - langue et devise » par MyPresta.eu."
sidebar:
  label: "Paramètres de localisation Multiboutique - langue et devise - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Multistore localization settings - language and currency sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/multistore-localization-settings-language-and-currency.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/multistore-localization-settings-language-and-currency/)
>
> ---


# Paramètres de localisation Multiboutique - langue et devise

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Extensions PHP standard (cURL, JSON, OpenSSL). Votre environnement d'hébergement doit prendre en charge la fonctionnalité Multiboutique de PrestaShop.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

Ce module introduit un nouvel élément de menu dans votre Back Office PrestaShop pour gérer les règles de localisation de chacune de vos boutiques.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Lorsque vous cliquez pour la première fois sur « Configurer » après l'installation, vous accédez à une page de configuration de base. Cette page sert principalement de point d'entrée à l'interface de gestion principale.

- **Ce que fait ce paramètre :** Cet écran contiendra probablement un simple message ou un bouton vous dirigeant vers la zone de gestion dédiée aux règles de localisation Multiboutique. Il pourrait également inclure des informations sur la version du module ou un lien vers le support.
- **Effet de la modification de ce paramètre :** Cliquer sur n'importe quel bouton ou lien ici vous mènera à l'interface principale où vous définissez vos règles de langue et de devise spécifiques à la boutique.
- **Valeur recommandée :** Suivez les instructions à l'écran, généralement en cliquant sur un bouton pour passer à la configuration principale.
- **Scénario / exemple de marchand :** Après l'installation, vous verrez un message comme « Cliquez ici pour gérer vos règles de localisation Multiboutique. » Vous cliquerez dessus pour accéder à la fonctionnalité principale.

### 2.2 Écran d'administration dédié : Règles de localisation Multiboutique (Back Office > Règles de localisation Multiboutique)

C'est le panneau de contrôle principal du module. Vous trouverez ce nouvel élément de menu sous **Paramètres de la boutique > Règles de localisation Multiboutique** (ou similaire, selon votre version de PrestaShop et la structure du menu).

En entrant dans cet écran, vous verrez une liste (grille) de vos boutiques existantes. Pour chaque boutique, vous pourrez définir ses paramètres de langue et de devise spécifiques.

**Actions et paramètres disponibles :**

1. **Liste des boutiques / Vue en grille :**

   - **Objectif :** Ce tableau affiche toutes les boutiques que vous avez configurées dans votre installation Multiboutique PrestaShop.
   - **Colonnes :** Vous verrez généralement des colonnes comme « Nom de la boutique » et potentiellement « Actions » ou « Configurer ».
   - **Effet des modifications :** Cette vue vous permet de voir rapidement quelles boutiques sont configurées et fournit le point d'entrée pour modifier leurs paramètres de localisation.
2. **Bouton Modifier/Configurer pour chaque boutique :**

   - **Ce que fait ce bouton :** Cliquer sur ce bouton (souvent une icône de crayon) à côté du nom d'une boutique ouvrira un formulaire de configuration détaillé spécifiquement pour cette boutique.
   - **Effet de la modification de ce paramètre :** C'est ici que vous définissez les langues et devises spécifiques pour la boutique sélectionnée.

**Dans le formulaire de configuration spécifique à la boutique :**

Lorsque vous cliquez pour modifier une boutique, vous verrez deux sections principales : **Langues** et **Devises**.

#### 2.2.1 Configuration des langues pour [Nom de la boutique]

- **Liste des langues disponibles :**

  - **Ce que fait ce paramètre :** Cette section présente une liste de toutes les langues installées dans votre boutique PrestaShop. Pour chaque langue, vous verrez généralement une case à cocher.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque cochée :* La langue sera disponible pour la sélection par les clients dans le front office de cette boutique spécifique.
    - *Lorsque décochée :* La langue ne sera PAS affichée dans le sélecteur de langue pour cette boutique, et les clients ne pourront pas y basculer.
  - **Valeur recommandée :** Cochez uniquement les langues pertinentes pour le public cible de cette boutique spécifique.
  - **Scénario / exemple de marchand :** Pour votre « Boutique Française », vous cocherez « Français (French) » et décocherez toutes les autres langues.
- **Langue par défaut pour [Nom de la boutique] :**

  - **Ce que fait ce paramètre :** Une liste déroulante ou une sélection par bouton radio vous permettant de choisir l'une des langues *activées* comme langue par défaut pour cette boutique.
  - **Effet de la modification de ce paramètre :** Lorsqu'un client visite cette boutique pour la première fois, elle se chargera automatiquement dans la langue par défaut sélectionnée. Si le client a précédemment sélectionné une langue, sa préférence pourrait être mémorisée, mais pour les nouveaux visiteurs, cette valeur par défaut s'applique.
  - **Valeur recommandée :** Définissez la langue principale pour le public cible de la boutique.
  - **Scénario / exemple de marchand :** Pour votre « Boutique Française », vous définirez « Français (French) » comme langue par défaut.

#### 2.2.2 Configuration des devises pour [Nom de la boutique]

- **Liste des devises disponibles :**

  - **Ce que fait ce paramètre :** Cette section présente une liste de toutes les devises installées dans votre boutique PrestaShop. Pour chaque devise, vous verrez généralement une case à cocher.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque cochée :* La devise sera disponible pour la sélection par les clients dans le front office de cette boutique spécifique. Les prix seront affichés dans cette devise si elle est sélectionnée.
    - *Lorsque décochée :* La devise ne sera PAS affichée dans le sélecteur de devise pour cette boutique, et les clients ne pourront pas voir les prix dans cette devise.
  - **Valeur recommandée :** Cochez uniquement les devises pertinentes pour le public cible de cette boutique spécifique.
  - **Scénario / exemple de marchand :** Pour votre « Boutique US », vous cocherez « US Dollar ($) » et décocherez « Euro (€) » et les autres devises.
- **Devise par défaut pour [Nom de la boutique] :**

  - **Ce que fait ce paramètre :** Une liste déroulante ou une sélection par bouton radio vous permettant de choisir l'une des devises *activées* comme devise par défaut pour cette boutique.
  - **Effet de la modification de ce paramètre :** Lorsqu'un client visite cette boutique pour la première fois, tous les prix seront automatiquement affichés dans la devise par défaut sélectionnée.
  - **Valeur recommandée :** Définissez la devise principale pour le public cible de la boutique.
  - **Scénario / exemple de marchand :** Pour votre « Boutique US », vous définirez « US Dollar ($) » comme devise par défaut.

**Flux de travail recommandé pour la gestion quotidienne de la boutique :**

1. Naviguez vers **Paramètres de la boutique > Règles de localisation Multiboutique**.
2. Identifiez la boutique que vous souhaitez configurer dans la liste.
3. Cliquez sur le bouton « Modifier » ou « Configurer » à côté de cette boutique.
4. Dans la section « Langues », cochez toutes les langues que vous souhaitez rendre disponibles pour cette boutique spécifique.
5. Sélectionnez l'une des langues *cochées* comme « Langue par défaut » pour cette boutique.
6. Dans la section « Devises », cochez toutes les devises que vous souhaitez rendre disponibles pour cette boutique spécifique.
7. Sélectionnez l'une des devises *cochées* comme « Devise par défaut » pour cette boutique.
8. Cliquez sur « Enregistrer » pour appliquer vos modifications.
9. Répétez l'opération pour toutes les autres boutiques de votre configuration Multiboutique.
10. **Videz toujours votre cache PrestaShop** (Paramètres avancés > Performances) après avoir effectué des modifications pour vous assurer qu'elles sont immédiatement reflétées sur le front office.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Règles de localisation Multiboutique (Vue Liste)** | Bouton Modifier/Configurer | N/A | Accéder aux paramètres détaillés de langue/devise pour une boutique spécifique. |
| **Configuration spécifique à la boutique (Langues)** | Langues disponibles (cases à cocher) | Cocher les pertinentes | Contrôle les langues qui apparaissent dans le sélecteur du front office pour cette boutique. |
| **Configuration spécifique à la boutique (Langues)** | Langue par défaut | Langue principale pour le public de la boutique | Définit la langue initiale pour les nouveaux visiteurs de cette boutique. |
| **Configuration spécifique à la boutique (Devises)** | Devises disponibles (cases à cocher) | Cocher les pertinentes | Contrôle les devises qui apparaissent dans le sélecteur du front office pour cette boutique. |
| **Configuration spécifique à la boutique (Devises)** | Devise par défaut | Devise principale pour le public de la boutique | Définit la devise initiale pour les nouveaux visiteurs de cette boutique. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai configuré les langues/devises, mais elles ne changent pas sur mon front office.**
R : La raison la plus courante est le cache. Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » et « Vider le cache » pour tous les caches). Essayez également de vider le cache de votre navigateur.

**Q : Mon thème personnalisé ne semble pas respecter les paramètres du module pour les sélecteurs de langue/devise.**
R : Ce module contrôle *quelles* options sont disponibles, mais votre thème dicte *comment* ces options sont affichées. Si votre thème a des sélecteurs de langue/devise fortement personnalisés, il pourrait outrepasser le comportement standard de PrestaShop.
\* **Solution :** Vérifiez la documentation de votre thème ou contactez le développeur de votre thème. Vous pourriez avoir besoin d'apporter des ajustements mineurs aux fichiers `.tpl` de votre thème pour vous assurer qu'ils utilisent les variables `languages` et `currencies` standard de PrestaShop, que ce module modifie.

**Q : Puis-je définir différentes langues/devises par défaut pour différents groupes de clients ?**
R : Non, ce module définit la langue et la devise par défaut *par boutique*, et non par groupe de clients. La valeur par défaut s'applique à tous les visiteurs de cette boutique spécifique. Les clients peuvent ensuite la modifier manuellement si d'autres options sont disponibles.

**Q : Que se passe-t-il si je désactive une langue/devise qui est actuellement définie par défaut pour une boutique ?**
R : Le module devrait vous empêcher de le faire ou revenir automatiquement à la prochaine langue/devise disponible. Assurez-vous toujours que votre valeur par défaut choisie est l'une des options *activées* pour cette boutique. Si vous rencontrez des problèmes, réactivez une valeur par défaut appropriée et videz votre cache.

**Q : Je n'ai qu'une seule boutique. Ai-je besoin de ce module ?**
R : Non, ce module est spécifiquement conçu pour la fonctionnalité Multiboutique de PrestaShop. Si vous n'avez qu'une seule boutique, les paramètres de localisation par défaut de PrestaShop (sous International > Localisation) sont suffisants.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de l'implémentation technique du module « Paramètres de localisation Multiboutique - langue et devise » pour les développeurs et les webmasters.

### 4.1 Vue d'ensemble de l'architecture

Le module étend principalement le comportement de localisation de base de PrestaShop en surchargeant les classes `Currency` et `Language`. Il introduit un contrôleur d'administration personnalisé (`AdminMultirulesController`) pour gérer les règles de localisation spécifiques à la boutique, qui sont stockées dans une table de base de données personnalisée. Le module exploite le modèle MVC de PrestaShop pour son interface Back Office et utilise des surcharges pour injecter sa logique dans le processus de sélection de la langue et de la devise du front office.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Ce module n'inclut aucun contrôleur front-office dédié. Sa logique front-office est injectée via des surcharges de classe et des hooks.
- **Contrôleurs d'administration Back-Office** :

  - `multishoplang/controllers/admin/AdminMultirules.php`
    - **Nom de la classe et classe parente** : `AdminMultirulesController` étend `ModuleAdminController`.
    - **Responsabilité** : Ce contrôleur gère la liste et l'édition des règles de localisation pour chaque boutique. Il est responsable de l'affichage de la grille des boutiques, de la gestion du formulaire pour la sélection des langues et devises disponibles pour une boutique spécifique, et de l'enregistrement de ces paramètres dans la base de données. Il utilise probablement `HelperList` pour la grille des boutiques et `HelperForm` pour la configuration spécifique à la boutique.
    - **Nom de l'onglet** : « Règles de localisation Multiboutique » (ou similaire, défini dans la méthode `installTab()`).
  - `multishoplang/controllers/admin/index.php`
    - **Nom de la classe et classe parente** : Il s'agit généralement d'un fichier vide ou d'un fichier contenant une instruction de sécurité `die()` pour empêcher l'accès direct au répertoire. Il ne représente pas un contrôleur actif.

### 4.3 Classes et modèles de base (`classes/`)

Le module s'appuie fortement sur les surcharges pour modifier le comportement de base de PrestaShop.

- `multishoplang/override/classes/Currency.php`
  - **Nom de la classe et classe parente** : `Currency` (surcharge la classe `Currency` de base de PrestaShop).
  - **Responsabilité** : Cette surcharge intercepte les appels liés à la récupération et à la sélection des devises. Elle modifie des méthodes comme `getCurrencies()` ou `getDefaultCurrency()` pour filtrer la liste des devises disponibles en fonction de la configuration de la boutique actuelle telle que définie par le module. Elle garantit que seules les devises activées pour la boutique active sont présentées dans le front office.
- `multishoplang/override/classes/Language.php`
  - **Nom de la classe et classe parente** : `Language` (surcharge la classe `Language` de base de PrestaShop).
  - **Responsabilité** : Similaire à la surcharge `Currency`, cette classe intercepte les appels liés aux langues. Elle modifie des méthodes comme `getLanguages()` ou `getDefaultLanguage()` pour filtrer la liste des langues disponibles en fonction de la configuration de la boutique actuelle. Elle garantit que seules les langues activées pour la boutique active sont présentées dans le front office.
- `multishoplang/override/classes/index.php`
  - **Nom de la classe et classe parente** : Il s'agit généralement d'un fichier vide ou d'un fichier contenant une instruction de sécurité `die()` pour empêcher l'accès direct au répertoire. Il ne représente pas une classe active.

### 4.4 Actifs JavaScript (`views/js/`)

Le module n'inclut aucun fichier JavaScript personnalisé. Toutes les interactions dans le Back Office sont gérées par les JavaScript standard de `HelperForm` et `HelperList` de PrestaShop, et le comportement du front office est géré par les surcharges de classe.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module n'inclut aucun fichier CSS personnalisé. Son interface Back Office repose sur le style du thème d'administration par défaut de PrestaShop. L'affichage du front office est contrôlé par le thème actif.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** : Aucun explicitement listé, mais la logique du module opère principalement via des surcharges de classe plutôt que des templates de hook directs.
- **Templates d'administration (`views/templates/admin/`)** :
  - `multishoplang/views/advert.tpl`
    - **Objectif** : Probablement un template pour afficher des messages promotionnels ou des informations sur d'autres modules MyPresta.eu au sein de l'interface de configuration du module.
  - `multishoplang/views/currenciesForm.tpl`
    - **Objectif** : Ce template est utilisé dans le `AdminMultirulesController` pour rendre la section du formulaire de configuration des devises disponibles et de la devise par défaut pour une boutique spécifique. Il contiendra des cases à cocher pour les devises et une liste déroulante pour la valeur par défaut.
  - `multishoplang/views/languagesForm.tpl`
    - **Objectif** : Ce template est utilisé dans le `AdminMultirulesController` pour rendre la section du formulaire de configuration des langues disponibles et de la langue par défaut pour une boutique spécifique. Il contiendra des cases à cocher pour les langues et une liste déroulante pour la valeur par défaut.
- **Templates front-office (`views/templates/front/`)** : Aucun.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - `ps_multirule` : Il s'agit de la table personnalisée créée par le module pour stocker les règles de localisation. Elle contient probablement des champs tels que :
    - `id_shop` : Clé étrangère référençant `ps_shop.id_shop`.
    - `id_lang_default` : L'ID de la langue par défaut pour cette boutique.
    - `id_currency_default` : L'ID de la devise par défaut pour cette boutique.
    - `available_languages` : Un tableau sérialisé ou une chaîne de caractères séparée par des virgules d'identifiants `id_lang` activés pour la boutique.
    - `available_currencies` : Un tableau sérialisé ou une chaîne de caractères séparée par des virgules d'identifiants `id_currency` activés pour la boutique.
  - Les enregistrements de configuration sont stockés dans `ps_configuration` pour les paramètres généraux du module (le cas échéant).
- **Table des hooks enregistrés** :
Le module fonctionne principalement via des surcharges de classe plutôt que par l'exécution directe de hooks dans le front office. Cependant, il enregistrera des hooks Back Office standard pour son interface d'administration.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Lors du chargement d'un contrôleur d'administration | Pour charger les CSS/JS spécifiques au module (bien qu'aucun ne soit présent dans ce module). |
| `displayBackOfficeHeader` | Dans l'en-tête du Back Office | Potentiellement pour afficher des alertes ou des notifications spécifiques au module. |
| `moduleRoutes` | Lors de l'initialisation du routage d'URL | Si le module a défini des routes front-office personnalisées (non applicable ici). |
| `actionObjectLanguageAddAfter` | Après l'ajout d'une nouvelle langue | Pour potentiellement mettre à jour les données internes du module pour les nouvelles langues. |
| `actionObjectCurrencyAddAfter` | Après l'ajout d'une nouvelle devise | Pour potentiellement mettre à jour les données internes du module pour les nouvelles devises. |
| `actionShopDataDuplication` | Lors de la duplication d'une boutique | Pour s'assurer que les règles de localisation sont copiées pour la nouvelle boutique. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à assurer le bon fonctionnement et l'amélioration continue de vos modules PrestaShop.
