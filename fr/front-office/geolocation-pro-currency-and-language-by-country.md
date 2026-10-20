---
title: "Géolocalisation pro - devise et langue par pays - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Géolocalisation pro - devise et langue par pays par MyPresta.eu."
sidebar:
  label: "Géolocalisation pro - devise et langue par pays - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Geolocation pro - currency and language by country sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/geolocation-pro-currency-and-language-by-country.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/geolocation-pro-currency-and-language-by-country/)
>
> ---


# Géolocalisation pro - devise et langue par pays

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises et habituellement disponibles sur la plupart des environnements d'hébergement.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Géolocalisation pro - devise et langue par pays)

C'est l'écran de configuration principal où vous activez ou désactivez la fonctionnalité principale du module et accédez aux outils de diagnostic.

- **Activer Géolocalisation Pro :**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour l'ensemble du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module détectera activement les emplacements des clients et appliquera vos règles de devise et de langue définies.
    - *Lorsqu'il est désactivé :* Le module sera inactif, et votre boutique reviendra à ses paramètres de devise et de langue par défaut pour tous les visiteurs, quelle que soit leur localisation.
  - **Valeur recommandée :** OUI (pour utiliser les fonctionnalités du module).
  - **Scénario / exemple de marchand :** Vous avez terminé de configurer toutes vos règles et êtes prêt à lancer des expériences personnalisées. Activez cet interrupteur. Si vous devez désactiver temporairement la fonctionnalité pour la maintenance, désactivez-la.
- **Afficher la bannière avec le choix du pays :**

  - **Ce que fait ce paramètre :** Détermine si une petite bannière ou une fenêtre contextuelle apparaît pour informer les clients du pays détecté et leur offrir un choix de le modifier.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Une bannière apparaîtra (généralement en haut ou en bas de l'écran) affichant le pays détecté et permettant potentiellement au client de remplacer manuellement la localisation, la devise ou la langue détectée. Cela peut être utile pour les clients utilisant des VPN ou ceux qui préfèrent les paramètres d'une autre région.
    - *Lorsqu'il est désactivé :* Aucune bannière ne sera affichée. Le module appliquera silencieusement les règles basées sur la détection IP.
  - **Valeur recommandée :** OUI (initialement, pour donner le contrôle aux clients, puis envisager NON si vous préférez une expérience complètement transparente et faites confiance à la détection IP).
  - **Scénario / exemple de marchand :** Un client des États-Unis visite votre boutique, et le module détecte correctement sa localisation. Si ce paramètre est activé, une bannière pourrait dire « Vous naviguez depuis les États-Unis. [Changer de pays ?] » Cela leur donne une chance de corriger si ils utilisent un VPN ou préfèrent acheter depuis une autre région.
- **Diagnostics et outils :**

  - **Ce que fait ce paramètre :** Cette section fournit des outils pour tester la fonctionnalité du module et vérifier la détection IP. Ce n'est pas un paramètre à modifier, mais un utilitaire.
  - **Effet de la modification de ce paramètre :** Cliquer sur les outils de diagnostic ouvrira de nouvelles vues ou des fenêtres contextuelles qui vous montreront des informations sur votre adresse IP actuelle, le pays détecté et comment le module appliquerait les règles.
  - **Valeur recommandée :** Utilisez ceci chaque fois que vous configurez de nouvelles règles ou que vous dépannez.
  - **Scénario / exemple de marchand :** Vous avez créé une règle pour l'Allemagne. Vous pouvez utiliser l'outil de diagnostic pour simuler une visite depuis l'Allemagne et voir si la devise et la langue correctes sont appliquées, en vous assurant que vos règles fonctionnent comme prévu.

### 2.2 Écran d'administration dédié : Règles géographiques (Back Office > Modules > Géolocalisation pro > Règles géographiques)

Cet écran vous permet de définir et de gérer les règles principales pour la devise et la langue en fonction du pays.

- **Nom de l'écran et emplacement du menu :** **Back Office > Modules > Géolocalisation pro - devise et langue par pays > Règles géographiques** (ou chemin similaire sous l'élément de menu principal du module).
- **Actions et paramètres disponibles :**
  - **Tableau de liste :** Affiche toutes vos règles géographiques existantes, montrant le pays, la devise assignée et la langue assignée.
  - **Ajouter une nouvelle règle géographique :** Un bouton pour créer une nouvelle règle.
  - **Actions Modifier/Supprimer :** Icônes à côté de chaque règle pour la modifier ou la supprimer.
- **Effet des modifications :**
  - **Ajout d'une nouvelle règle :** Lorsque vous ajoutez une règle (par exemple, pour « Allemagne » d'utiliser « EUR » et « Allemand »), tout visiteur détecté comme étant d'Allemagne aura automatiquement sa devise et sa langue définies sur ces valeurs.
  - **Modification d'une règle :** La modification d'une règle existante changera instantanément le comportement du module pour les visiteurs de ce pays spécifique.
  - **Suppression d'une règle :** La suppression d'une règle signifie que les visiteurs de ce pays n'auront plus de devise ou de langue spécifique appliquée par ce module et reviendront aux paramètres par défaut de votre boutique.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. **Identifier les pays cibles :** Décidez quels pays vous souhaitez cibler avec des devises et des langues spécifiques.
  2. **Assurez-vous que les devises/langues sont activées :** Assurez-vous que les devises et les langues que vous souhaitez attribuer sont déjà activées dans votre boutique PrestaShop (Back Office > International > Devises / Langues).
  3. **Créer des règles :** Pour chaque pays, cliquez sur « Ajouter une nouvelle règle géographique », sélectionnez le pays dans le menu déroulant, puis sélectionnez la devise et la langue souhaitées. Enregistrez la règle.
  4. **Tester avec les diagnostics :** Utilisez les outils de diagnostic du module pour vérifier que vos règles fonctionnent comme prévu.

### 2.3 Écran d'administration dédié : Règles de langue (Back Office > Modules > Géolocalisation pro > Règles de langue)

Cet écran semble être un doublon ou une interface alternative pour gérer les règles spécifiques à la langue, offrant potentiellement un contrôle plus granulaire ou une vue différente. Compte tenu de la description du module, l'écran « Règles géographiques » est probablement l'interface principale pour les attributions basées sur le pays. Cet écran pourrait être destiné à des remplacements plus avancés spécifiques à la langue non directement liés à un pays.

- **Nom de l'écran et emplacement du menu :** **Back Office > Modules > Géolocalisation pro - devise et langue par pays > Règles de langue** (ou chemin similaire).
- **Actions et paramètres disponibles :**
  - **Tableau de liste :** Affiche les règles de langue existantes.
  - **Ajouter une nouvelle règle de langue :** Bouton pour créer une nouvelle règle.
  - **Actions Modifier/Supprimer :** Icônes pour modifier ou supprimer des règles.
- **Effet des modifications :** Ces règles remplaceraient ou compléteraient probablement les règles basées sur le pays pour la langue. Par exemple, vous pourriez avoir une règle générale pour « Anglais » pour tous les pays non spécifiés, puis utiliser cet écran pour des exceptions ou des comportements linguistiques spécifiques.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Utilisez cet écran si vous devez gérer les paramètres de langue indépendamment des règles géographiques spécifiques au pays, ou si vous rencontrez des scénarios où une règle de pays n'est pas suffisante pour la gestion de la langue. Sinon, concentrez-vous sur l'écran « Règles géographiques ».

### 2.4 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activer Géolocalisation Pro | OUI | Interrupteur principal pour la fonctionnalité du module. OUI active la détection de devise/langue basée sur le pays. |
| | Afficher la bannière avec le choix du pays | OUI | Affiche une bannière informant les clients du pays détecté et permettant une annulation manuelle. |
| | Diagnostics et outils | N/A | Utilitaire pour tester la détection IP et l'application des règles. |
| **Règles géographiques** | Ajouter/Modifier une règle géographique (Pays, Devise, Langue) | N/A | Définit la devise et la langue qui sont automatiquement définies pour les visiteurs d'un pays spécifique. |
| **Règles de langue** | Ajouter/Modifier une règle de langue | N/A | (Potentiellement) Définit les remplacements de langue ou les comportements linguistiques spécifiques, éventuellement indépendamment du pays. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes clients voient toujours la mauvaise devise/langue même après avoir configuré les règles. Qu'est-ce qui ne va pas ?**
R1 :

- **Le module est-il activé ?** Vérifiez le paramètre « Activer Géolocalisation Pro » sur la page de configuration principale.
- **Vos règles sont-elles correctes ?** Allez dans « Règles géographiques » et assurez-vous que le pays, la devise et la langue sont correctement attribués.
- **Les devises/langues sont-elles activées dans PrestaShop ?** Assurez-vous que les devises et les langues que vous essayez d'attribuer sont actives dans votre PrestaShop (International > Devises / Langues).
- **Videz le cache de votre navigateur :** Parfois, votre navigateur peut mettre en cache d'anciens paramètres. Demandez aux clients de vider le cache de leur navigateur ou d'essayer une fenêtre de navigation privée.
- **Videz le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » en haut à droite.
- **Testez avec les diagnostics :** Utilisez les outils de diagnostic intégrés du module pour simuler une visite depuis un pays spécifique et voir quelle devise/langue il applique. Cela aide à identifier si le problème est lié à la détection ou à l'application des règles.

**Q2 : Le module détecte le mauvais pays pour certains clients. Pourquoi ?**
R2 :

- **VPN et Proxies :** Les clients utilisant des réseaux privés virtuels (VPN) ou des serveurs proxy apparaîtront comme naviguant depuis l'emplacement de leur VPN/proxy, et non depuis leur emplacement physique réel. Le module s'appuie sur la détection d'adresse IP, qui peut être falsifiée.
- **Précision de la base de données IP :** Les bases de données de géolocalisation sont généralement très précises mais pas parfaites à 100 %. Certaines plages d'adresses IP peuvent être mal identifiées.
- **« Afficher la bannière avec le choix du pays » :** Si ce paramètre est activé, les clients peuvent corriger manuellement le pays détecté, ce qui est la meilleure solution pour ces cas limites.

**Q3 : Comment ajouter une nouvelle devise ou langue à ma boutique pour pouvoir l'utiliser dans une règle géographique ?**
R3 :

- **Ajouter une devise :** Allez dans **International > Devises** dans votre Back Office PrestaShop. Cliquez sur « Ajouter une nouvelle devise », remplissez les détails et activez-la.
- **Ajouter une langue :** Allez dans **International > Langues** dans votre Back Office PrestaShop. Cliquez sur « Ajouter une nouvelle langue », remplissez les détails et activez-la. N'oubliez pas d'installer également les packs de langue et de traduire votre contenu pour la nouvelle langue.

**Q4 : Ce module ralentira-t-il mon site web ?**
R4 : Le module effectue une recherche IP rapide et une application de règles, ce qui est généralement très rapide et optimisé. Il ne devrait pas avoir d'impact notable sur la vitesse de chargement de votre site web. Si vous rencontrez des problèmes de performance, assurez-vous que le cache de votre PrestaShop est activé et régulièrement vidé.

**Q5 : Je souhaite styliser la bannière de choix de pays pour qu'elle corresponde à mon thème. Comment puis-je faire cela ?**
R5 : La bannière utilise des classes CSS spécifiques. Bien que la modification directe des fichiers du module ne soit pas recommandée (car les mises à jour les écraseraient), un développeur web peut utiliser le fichier CSS personnalisé de votre thème pour remplacer les styles par défaut. Il inspecterait la bannière à l'aide des outils de développement du navigateur pour identifier les sélecteurs CSS pertinents (par exemple, des classes comme `.progeo-banner`, `.progeo-choice`) et appliquerait ensuite ses propres styles.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Géolocalisation pro - devise et langue par pays » (`progeo`) est conçu pour s'intégrer profondément aux fonctionnalités d'internationalisation de base de PrestaShop. Il utilise principalement des surcharges pour modifier la façon dont PrestaShop détermine la `Configuration`, la `Currency` et la `Language` actives en fonction de l'adresse IP du visiteur. Il suit une structure de module PrestaShop standard, utilisant des contrôleurs front et admin, des classes personnalisées (en particulier pour les entités `ObjectModel`), et des templates Smarty pour la configuration et l'affichage front-office (par exemple, la bannière de choix de pays). La logique principale du module réside dans son `index.php` (fichier principal du module) et les classes de base surchargées.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `progeo/controllers/front/choice.php`
  - **Nom de la classe et classe parente :** `ProgeoChoiceModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur gère les requêtes AJAX liées à la bannière de choix de pays. Lorsqu'un client interagit avec la bannière (par exemple, sélectionne un pays, une devise ou une langue différente), ce contrôleur traite la requête, met à jour les variables de session ou les cookies, et redirige potentiellement l'utilisateur pour appliquer les nouveaux paramètres. Il est crucial pour l'aspect interactif de la bannière.
- `progeo/controllers/front/index.php`
  - **Nom de la classe et classe parente :** `ProgeoIndexModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur peut servir de solution de repli ou de simple point d'entrée pour les actions du module front-office, bien que `choice.php` soit plus spécifique à l'interactivité de la bannière. Dans de nombreux modules, `index.php` dans `controllers/front` est un espace réservé ou gère des requêtes front-office très basiques et non spécifiques.

#### Contrôleurs d'administration Back-Office

- `progeo/controllers/admin/AdminGeorulesController.php`
  - **Nom de l'onglet et entité gérée :** « Règles géographiques » (sous le menu principal du module). Gère les entités `Georule`.
  - **Responsabilité :** C'est le contrôleur principal pour la gestion des attributions de devise et de langue spécifiques au pays. Il fournit l'interface CRUD (Créer, Lire, Mettre à jour, Supprimer) pour les enregistrements `ps_progeo_georule`, permettant aux administrateurs de définir quelle devise et quelle langue doivent être actives pour les visiteurs de pays spécifiques. Il étend `AdminController` et utilise `HelperList` pour la grille et `HelperForm` pour les formulaires d'ajout/modification.
- `progeo/controllers/admin/AdminLangrules.php`
  - **Nom de l'onglet et entité gérée :** « Règles de langue » (sous le menu principal du module). Gère les entités `Langrule`.
  - **Responsabilité :** Ce contrôleur gère les règles spécifiques à la langue. Il fournit une interface CRUD pour les enregistrements `ps_progeo_langrule`. Il est probablement utilisé pour un contrôle linguistique plus granulaire, potentiellement en remplaçant ou en complétant la langue définie dans `AdminGeorulesController`.
- `progeo/controllers/admin/AdminLangrulesController.php`
  - **Nom de l'onglet et entité gérée :** « Règles de langue » (sous le menu principal du module). Gère les entités `Langrule`.
  - **Responsabilité :** Cela semble être un doublon ou une implémentation alternative de `AdminLangrules.php`. Dans un module PrestaShop typique, `AdminLangrulesController.php` serait la convention de nommage standard. Les développeurs doivent vérifier quel fichier est réellement utilisé par l'enregistrement du menu du module.
- `progeo/controllers/admin/index.php`
  - **Nom de l'onglet et entité gérée :** Pas un onglet direct, mais un espace réservé standard.
  - **Responsabilité :** Ce fichier est souvent présent dans les répertoires `controllers/admin` mais est généralement vide ou contient des mesures de sécurité de base (par exemple, `die('Forbidden');`). Il ne gère pas d'entité spécifique et ne fournit pas d'interface utilisateur.

### 4.3 Classes et modèles de base (`classes/`)

Le module utilise des surcharges pour injecter sa logique dans le comportement de base de PrestaShop.

- `progeo/override/classes/Configuration.php`
  - **Responsabilité :** Surcharge la classe `Configuration` de base. Ceci est essentiel pour que le module puisse modifier les valeurs de configuration globales (comme `PS_CURRENCY_DEFAULT` ou `PS_LANG_DEFAULT`) à la volée en fonction de la géolocalisation, sans réellement modifier les valeurs de la base de données pour les autres visiteurs. Il garantit que lorsque PrestaShop demande une valeur de configuration, le module peut intercepter et renvoyer une valeur localisée.
- `progeo/override/classes/Currency.php`
  - **Responsabilité :** Surcharge la classe `Currency` de base. Cette surcharge permet au module de manipuler la devise considérée comme « active » ou « par défaut » pour le visiteur actuel, garantissant que les prix sont affichés correctement selon la règle géographique.
- `progeo/override/classes/Language.php`
  - **Responsabilité :** Surcharge la classe `Language` de base. Similaire à `Currency.php`, cette surcharge permet au module de définir la langue active pour le visiteur actuel en fonction de la géolocalisation, garantissant que le contenu est affiché dans la bonne langue.
- `progeo/override/classes/index.php`
  - **Responsabilité :** Fichier `index.php` vide standard pour la sécurité dans un répertoire.
- `progeo/override/classes/_Configuration.php`
  - **Responsabilité :** Ce nom de fichier suggère une sauvegarde potentielle ou une version plus ancienne de la surcharge `Configuration`. Dans un environnement de production, une seule surcharge `Configuration.php` doit être active. Les développeurs doivent vérifier le processus d'installation du module pour s'assurer que la surcharge correcte est utilisée.

### 4.4 Actifs JavaScript (`views/js/`)

- `progeo/views/js/banner.js`
  - **Portée :** Front-office.
  - **Responsabilité :** Ce script gère la bannière interactive de choix de pays.
    - **Écouteurs d'événements :** Lie des événements aux éléments de la bannière (par exemple, événements de clic sur les boutons « changer de pays », changements de boîtes de sélection pour la devise/langue).
    - **Appels AJAX :** Effectue des requêtes AJAX au `ProgeoChoiceModuleFrontController` (par exemple, `choice.php`) pour mettre à jour le pays, la devise ou la langue sélectionnés par l'utilisateur.
    - **Manipulation du DOM :** Affiche/masque la bannière, met à jour le contenu textuel en fonction des sélections de l'utilisateur et redirige potentiellement le navigateur après qu'un choix a été fait.
    - **Cookies/Stockage local :** Peut stocker les préférences de l'utilisateur dans des cookies ou un stockage local pour se souvenir de son choix entre les sessions.

### 4.5 Feuilles de style CSS (`views/css/`)

- `progeo/views/css/admin.css`
  - **Portée :** Style des formulaires d'administration du Back-office.
  - **Responsabilité :** Fournit un style spécifique pour les pages de configuration du module et les contrôleurs d'administration (par exemple, `AdminGeorulesController`, `AdminLangrulesController`). Cela garantit une apparence cohérente dans le back office de PrestaShop et améliore la convivialité des formulaires et des listes du module.
- `progeo/views/css/banner.css`
  - **Portée :** Style client Front-office.
  - **Responsabilité :** Style la bannière de choix de pays qui apparaît sur le front office. Elle définit la position, les couleurs, les polices, la réactivité et la présentation visuelle globale de la bannière. Les développeurs peuvent remplacer ces styles dans le CSS personnalisé de leur thème pour intégrer la bannière de manière transparente au design de la boutique. Les sélecteurs clés peuvent inclure `.progeo-banner`, `.progeo-choice-form`, etc.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :
  - `progeo/views/displayHeader.tpl` : Ce template est probablement accroché à `displayHeader` (ou `actionFrontControllerSetMedia`) pour inclure les fichiers CSS et JS nécessaires à la bannière front-office, ou pour injecter des variables JavaScript initiales.
- **Templates d'administration (`views/templates/admin/`)** :
  - `progeo/views/advert.tpl` : Probablement utilisé pour afficher des messages promotionnels ou des liens vers d'autres modules MyPresta.eu dans la configuration du module.
  - `progeo/views/banner.tpl` : Ce template est probablement utilisé dans la configuration du module pour prévisualiser ou gérer les paramètres liés à la bannière front-office.
  - `progeo/views/currenciesForm.tpl` : Template pour la gestion des paramètres liés aux devises, éventuellement dans la configuration principale ou un écran d'administration dédié.
  - `progeo/views/diagnostics-layer1.tpl`, `progeo/views/diagnostics-layer2.tpl`, `progeo/views/diagnostics-overview.tpl`, `progeo/views/diagnostics-result.tpl`, `progeo/views/diagnostics.tpl` : Ces templates sont utilisés pour rendre les différents outils de diagnostic et leur sortie, aidant l'administrateur à dépanner la détection IP et l'application des règles.
  - `progeo/views/languagesForm.tpl` : Template pour la gestion des paramètres liés aux langues, similaire à `currenciesForm.tpl`.
  - `progeo/views/tabs.tpl` : Utilisé pour rendre les onglets de navigation dans l'interface de configuration du module, permettant à l'administrateur de basculer entre différentes sections de paramètres (par exemple, « Règles géographiques », « Règles de langue », « Configuration »).
  - `progeo/views/tools-hint.tpl`, `progeo/views/tools.tpl` : Templates pour afficher des astuces ou des outils généraux dans l'interface back-office du module.
- **Templates front-office (`views/templates/front/`)** :
  - `progeo/views/banner.tpl` : C'est le template réel de la bannière de choix de pays front-office, rendu au client. Il contient la structure HTML pour afficher le pays, la devise, la langue détectés et les options de sélection manuelle.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de la base de données** :

  - `ps_progeo_georule` : Stocke les règles de géolocalisation principales.
    - `id_progeo_georule` (Clé primaire)
    - `id_country` (Clé étrangère vers `ps_country`)
    - `id_currency` (Clé étrangère vers `ps_currency`)
    - `id_lang` (Clé étrangère vers `ps_lang`)
  - `ps_progeo_langrule` : Stocke les règles spécifiques à la langue (les détails dépendraient de son implémentation spécifique, mais probablement une structure similaire pour les remplacements de langue).
    - `id_progeo_langrule` (Clé primaire)
    - `id_lang` (Clé étrangère vers `ps_lang`)
    - (Potentiellement d'autres champs pour des comportements linguistiques spécifiques)
  - Enregistrements de configuration dans `ps_configuration` :
    - `PROGEO_ENABLED` : (1 ou 0) Interrupteur principal du module.
    - `PROGEO_SHOW_BANNER` : (1 ou 0) Indique si la bannière de choix de pays doit être affichée.
    - (Autres clés de configuration telles que définies dans `getContent()` et `install()`)
- **Tableau des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page front-office. | Pour inclure les actifs CSS et JavaScript (`banner.css`, `banner.js`) pour la bannière front-office, et potentiellement pour injecter des variables JavaScript initiales ou rendre la bannière elle-même. |
| `actionFrontControllerSetMedia` | Exécuté lorsqu'un contrôleur frontal définit ses actifs multimédias. | Similaire à `displayHeader`, utilisé pour ajouter des fichiers CSS et JS de manière conditionnelle ou d'une manière PrestaShop plus moderne. |
| `actionModuleInstall` | Lors de l'installation du module. | Pour créer des tables de base de données (`ps_progeo_georule`, `ps_progeo_langrule`), enregistrer des hooks et définir des valeurs de configuration par défaut. |
| `actionModuleUninstall` | Lors de la désinstallation du module. | Pour supprimer des tables de base de données, désenregistrer des hooks et nettoyer les valeurs de configuration. |
| `displayBackOfficeHeader` | Dans la section `<head>` de chaque page back-office. | Pour inclure `admin.css` pour les pages de configuration du module et potentiellement du JavaScript spécifique à l'administration. |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses actifs multimédias. | Similaire à `displayBackOfficeHeader`, pour ajouter du CSS et du JS d'administration. |
| `actionDispatcherBefore` | Avant que le répartiteur ne traite une requête. | Crucial pour la logique principale du module : détecter l'adresse IP du visiteur, appliquer la règle géographique et définir la devise et la langue `Context` correctes *avant* que PrestaShop ne rende la page. C'est là que les surcharges sont effectivement déclenchées. |
| `displayBanner` (Hook personnalisé) | Potentiellement un hook personnalisé pour le rendu de la bannière front-office. | Si `displayBanner` est un hook personnalisé, le module s'enregistrerait pour rendre `banner.tpl` à cet emplacement spécifique. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Géolocalisation pro - devise et langue par pays », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe s'engage à garantir que votre module fonctionne de manière optimale et s'intègre parfaitement à votre boutique PrestaShop.
