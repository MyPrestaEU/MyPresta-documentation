---
title: "Cacher des produits par pays - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Cacher des produits par pays' par MyPresta.eu."
sidebar:
  label: "Cacher des produits par pays - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Hide products by country sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/hide-products-by-country.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/hide-products-by-country/)
>
> ---


# Cacher des produits par pays

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge :** PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement nécessaire.

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Vous pouvez accéder à la configuration du module en naviguant vers **Modules > Gestionnaire de modules**, en recherchant « Cacher des produits par pays », puis en cliquant sur « Configurer ».

#### Paramètres généraux

- **Activé / Désactivé (Interrupteur)**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour l'ensemble du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module filtre activement les produits en fonction de vos paramètres.
    - *Lorsqu'il est désactivé :* Le module cesse de filtrer les produits, et tous les produits seront visibles pour tous les clients, quel que soit le pays.
  - **Valeur recommandée :** **Activé** une fois que vous avez configuré vos règles.
  - **Scénario / exemple de marchand :** Vous configurez le module pour la première fois et souhaitez le tester avant de le mettre en ligne, vous le laissez donc désactivé. Une fois prêt, vous l'activez.
- **Que voulez-vous faire ? (Liste déroulante)**

  - **Ce que fait ce paramètre :** Définit la logique principale de vos règles de masquage de produits.
  - **Effet de la modification de ce paramètre :**
    - *Cacher les produits pour les pays sélectionnés :* Les produits choisis dans les sections « Sélectionner des catégories » et « Sélectionner un fabricant » seront masqués aux clients des pays de la liste « Sélectionner des pays ». C'est le cas d'utilisation le plus courant.
    - *Afficher les produits uniquement pour les pays sélectionnés :* Les produits choisis ne seront visibles QUE pour les clients des pays de la liste « Sélectionner des pays ». Pour tous les autres pays, ces produits seront masqués.
  - **Valeur recommandée :** Généralement **Cacher les produits pour les pays sélectionnés**.
  - **Scénario / exemple de marchand :**
    - *Cacher les produits :* Vous vendez une marque spécifique qui ne peut pas être vendue en Allemagne. Vous sélectionnez « Cacher les produits pour les pays sélectionnés », choisissez la marque et sélectionnez l'Allemagne.
    - *Afficher les produits uniquement :* Vous avez une collection spéciale de produits exclusivement pour le marché américain. Vous sélectionnez « Afficher les produits uniquement pour les pays sélectionnés », choisissez la collection et sélectionnez les États-Unis.
- **Sélectionner des pays (Liste multi-sélection)**

  - **Ce que fait ce paramètre :** Vous permet de choisir les pays spécifiques auxquels votre règle « Que voulez-vous faire ? » s'appliquera.
  - **Effet de la modification de ce paramètre :** Seuls les clients identifiés comme étant originaires de ces pays sélectionnés seront affectés par les règles de visibilité des produits que vous avez définies.
  - **Valeur recommandée :** Sélectionnez tous les pays pertinents pour vos règles.
  - **Scénario / exemple de marchand :** Si vous masquez des produits pour les clients en France et en Espagne, vous sélectionneriez « France » et « Espagne » dans cette liste.
- **Sélectionner des catégories (Arborescence de catégories)**

  - **Ce que fait ce paramètre :** Vous permet de choisir des catégories de produits spécifiques dont les produits seront soumis à la règle de masquage/affichage.
  - **Effet de la modification de ce paramètre :** Tous les produits des catégories sélectionnées (et de leurs sous-catégories, si vous choisissez de les inclure) seront affectés par la règle « Que voulez-vous faire ? ».
  - **Valeur recommandée :** Sélectionnez les catégories contenant les produits que vous souhaitez contrôler.
  - **Scénario / exemple de marchand :** Vous souhaitez masquer tous les produits de votre catégorie « Électronique » aux clients au Canada. Vous sélectionneriez « Électronique » ici.
- **Sélectionner un fabricant (Liste multi-sélection)**

  - **Ce que fait ce paramètre :** Vous permet de choisir des fabricants spécifiques dont les produits seront soumis à la règle de masquage/affichage.
  - **Effet de la modification de ce paramètre :** Tous les produits des fabricants sélectionnés seront affectés par la règle « Que voulez-vous faire ? ».
  - **Valeur recommandée :** Sélectionnez les fabricants dont les produits vous souhaitez contrôler.
  - **Scénario / exemple de marchand :** Vous avez un accord de distribution qui vous empêche de vendre les produits « Marque X » en Australie. Vous sélectionneriez « Marque X » ici.
- **Exclure des groupes de clients (Liste multi-sélection)**

  - **Ce que fait ce paramètre :** Vous permet d'exempter certains groupes de clients des règles de masquage de produits du module.
  - **Effet de la modification de ce paramètre :** Les clients appartenant aux groupes sélectionnés verront toujours tous les produits, quel que soit leur pays ou les paramètres du module. Ceci est utile pour les partenaires B2B ou les VIP.
  - **Valeur recommandée :** Laissez vide, sauf si vous avez des groupes de clients spécifiques qui doivent contourner les règles.
  - **Scénario / exemple de marchand :** Vous avez un groupe de clients « Grossistes » qui devrait toujours voir votre catalogue complet, même si certains produits sont restreints pour les clients réguliers dans leur pays. Vous sélectionneriez « Grossistes » ici.
- **Exclure des clients (Champ de saisie avec recherche)**

  - **Ce que fait ce paramètre :** Vous permet d'exempter des clients individuels des règles de masquage de produits du module.
  - **Effet de la modification de ce paramètre :** Les clients spécifiques que vous sélectionnez verront toujours tous les produits, quel que soit leur pays ou les paramètres du module.
  - **Valeur recommandée :** Laissez vide, sauf si vous avez des clients individuels spécifiques qui doivent contourner les règles.
  - **Scénario / exemple de marchand :** Un responsable de compte clé spécifique doit voir tous les produits pour un client, même s'il navigue depuis un pays restreint. Vous rechercheriez et sélectionneriez ce client ici.

#### Paramètres de géolocalisation et de simulation

- **Définir la priorité des méthodes d'identification d'origine (Liste glisser-déposer)**

  - **Ce que fait ce paramètre :** Détermine l'ordre dans lequel le module tente d'identifier le pays d'un client. C'est crucial car différentes méthodes peuvent parfois donner des résultats différents.
  - **Effet de la modification de ce paramètre :** Le module essaiera les méthodes de haut en bas. La première identification réussie sera utilisée.
    - *Adresse de livraison :* Utilise le pays de l'adresse de livraison sélectionnée par le client (nécessite que le client soit connecté et ait une adresse).
    - *Adresse IP (Géolocalisation) :* Utilise l'adresse IP du client pour déterminer son pays (le plus courant pour les invités).
    - *Langue du navigateur :* Déduit le pays des paramètres de langue du navigateur du client (moins fiable pour une identification précise du pays).
  - **Valeur recommandée :**
    1. Adresse de livraison (si l'adresse du client connecté est la plus importante)
    2. Adresse IP (pour une précision générale pour tous les visiteurs)
    3. Langue du navigateur (en dernier recours, moins précise)
  - **Scénario / exemple de marchand :** Vous souhaitez prioriser l'adresse de livraison réelle du client s'il est connecté, car c'est la plus précise pour l'expédition. Pour les invités, vous souhaitez vous fier à la géolocalisation IP. Vous feriez glisser « Adresse de livraison » en haut, puis « Adresse IP ».
- **Utiliser l'adresse de livraison (Interrupteur)**

  - **Ce que fait ce paramètre :** Contrôle si le module prend en compte le pays de l'adresse de livraison choisie par le client pour le filtrage des produits.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Si un client est connecté et a une adresse de livraison sélectionnée, le module utilisera le pays de cette adresse pour déterminer la visibilité des produits.
    - *Lorsqu'il est désactivé :* Le module ignorera l'adresse de livraison et s'appuiera sur d'autres méthodes (comme l'adresse IP) même pour les clients connectés.
  - **Valeur recommandée :** **Activé** pour les clients connectés, car l'adresse de livraison est souvent l'indicateur le plus précis de l'endroit où le produit doit être livré.
  - **Scénario / exemple de marchand :** Un client des États-Unis navigue depuis le Canada. Si « Utiliser l'adresse de livraison » est activé et qu'il a une adresse de livraison aux États-Unis sélectionnée, il verra les produits disponibles aux États-Unis. Si désactivé, il pourrait voir les produits disponibles au Canada (en fonction de son IP).
- **Activer la liste blanche (Interrupteur)**

  - **Ce que fait ce paramètre :** Ce paramètre fonctionne en conjonction avec la fonction de géolocalisation intégrée de PrestaShop (trouvée sous **Paramètres de la boutique > Général > Géolocalisation**). Si la géolocalisation de PrestaShop est activée, ce module peut utiliser sa liste blanche.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Si la géolocalisation native de PrestaShop est active et configurée avec une liste blanche (pays autorisés à naviguer), ce module respectera cette liste blanche. Les visiteurs des pays *non* figurant sur la liste blanche de PrestaShop pourraient être bloqués ou redirigés avant même que ce module n'applique ses règles.
    - *Lorsqu'il est désactivé :* Ce module ignorera la liste blanche de géolocalisation de PrestaShop et appliquera ses règles en fonction de sa propre identification de pays.
  - **Valeur recommandée :** **Désactivé** sauf si vous utilisez et gérez activement la liste blanche de géolocalisation native de PrestaShop.
  - **Scénario / exemple de marchand :** Vous avez configuré la géolocalisation de PrestaShop pour n'autoriser que les visiteurs des pays de l'UE. Si vous activez « Activer la liste blanche » ici, les visiteurs extérieurs à l'UE seront gérés par le système central de PrestaShop, et ce module appliquera ensuite ses règles spécifiques aux produits aux visiteurs de l'UE autorisés.
- **Simuler la visite (Interrupteur)**

  - **Ce que fait ce paramètre :** C'est un outil de test puissant qui vous permet de faire comme si vous naviguiez depuis un pays différent sans réellement changer votre emplacement ou utiliser un VPN.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le champ « Simuler l'IP » devient actif, vous permettant de saisir une adresse IP. Le module traitera alors votre session de navigation actuelle comme si vous visitiez depuis le pays associé à cette IP.
    - *Lorsqu'il est désactivé :* Le module identifie votre pays normalement.
  - **Valeur recommandée :** **Désactivé** pour les boutiques en ligne. N'activez que temporairement pour les tests.
  - **Scénario / exemple de marchand :** Vous souhaitez vérifier que les produits sont correctement masqués pour les clients en Allemagne. Vous activez « Simuler la visite », saisissez une adresse IP allemande (par exemple, 85.214.132.112), puis naviguez sur votre boutique pour voir si les produits corrects sont masqués.
- **Simuler l'IP (Champ de texte)**

  - **Ce que fait ce paramètre :** Lorsque « Simuler la visite » est activé, vous saisissez une adresse IP ici pour simuler un visiteur du pays de cette IP.
  - **Effet de la modification de ce paramètre :** Votre session de navigation actuelle se comportera comme si vous étiez situé dans le pays associé à l'adresse IP saisie, vous permettant de tester les règles de visibilité des produits.
  - **Valeur recommandée :** Laissez vide, sauf si « Simuler la visite » est activé pour les tests.
  - **Scénario / exemple de marchand :** Après avoir activé « Simuler la visite », vous saisissez « 192.168.1.1 » (une IP locale courante, mais vous utiliseriez une vraie IP publique pour un pays) pour tester. Pour une IP allemande, vous pourriez utiliser « 85.214.132.112 ».

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | **Activé** | Activé | Interrupteur principal pour la fonctionnalité du module. |
| Configuration du module | **Que voulez-vous faire ?** | Cacher les produits pour les pays sélectionnés | Définit si les produits sont masqués pour les pays sélectionnés ou uniquement affichés pour eux. |
| Configuration du module | **Sélectionner des pays** | (Vide) / Sélectionner les pertinents | Pays affectés par la règle de visibilité des produits. |
| Configuration du module | **Sélectionner des catégories** | (Vide) / Sélectionner les pertinentes | Catégories dont les produits sont affectés. |
| Configuration du module | **Sélectionner un fabricant** | (Vide) / Sélectionner les pertinents | Fabricants dont les produits sont affectés. |
| Configuration du module | **Exclure des groupes de clients** | (Vide) | Groupes de clients exemptés des règles de masquage. |
| Configuration du module | **Exclure des clients** | (Vide) | Clients individuels exemptés des règles de masquage. |
| Configuration du module | **Définir la priorité des méthodes d'identification d'origine** | Adresse de livraison, Adresse IP, Langue du navigateur | Ordre des méthodes pour identifier le pays du client. |
| Configuration du module | **Utiliser l'adresse de livraison** | Activé | Utiliser le pays de l'adresse de livraison du client pour le filtrage. |
| Configuration du module | **Activer la liste blanche** | Désactivé | Respecter la liste blanche de géolocalisation native de PrestaShop. |
| Configuration du module | **Simuler la visite** | Désactivé | Activer pour tester la visibilité des produits depuis une IP spécifique. |
| Configuration du module | **Simuler l'IP** | (Vide) | Adresse IP à simuler lorsque « Simuler la visite » est activé. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : J'ai configuré le module, mais les produits sont toujours visibles/masqués incorrectement. Que dois-je vérifier en premier ?**
R :

1.  **Module activé :** Vérifiez que l'interrupteur principal « Activé » sur la page de configuration du module est bien sur ON.
2.  **Cache :** Videz le cache de votre PrestaShop (Allez dans **Paramètres avancés > Performances**, puis cliquez sur « Vider le cache » en haut à droite). Le cache du navigateur peut aussi parfois interférer, alors essayez un rafraîchissement forcé (Ctrl+F5 ou Cmd+Maj+R) ou une fenêtre de navigation privée/incognito.
3.  **Simulation :** Si vous testez, assurez-vous que « Simuler la visite » est activé et que « Simuler l'IP » est correctement défini. Si vous ne simulez pas, assurez-vous que « Simuler la visite » est désactivé.
4.  **Logique de la règle :** Vérifiez votre paramètre « Que voulez-vous faire ? » (« Cacher les produits pour les pays sélectionnés » vs « Afficher les produits uniquement pour les pays sélectionnés ») et assurez-vous qu'il correspond à votre intention.
5.  **Sélection du pays/catégorie/fabricant :** Assurez-vous d'avoir correctement sélectionné les pays, catégories et fabricants qui doivent être affectés.

**Q : Comment le module identifie-t-il le pays d'un client ?**
R : Le module utilise un système de priorité que vous configurez :

1.  **Adresse de livraison :** Si le client est connecté et a une adresse de livraison, c'est la plus précise.
2.  **Adresse IP (Géolocalisation) :** Pour les invités ou si aucune adresse de livraison n'est utilisée, il utilise l'adresse IP du visiteur pour déterminer son pays.
3.  **Langue du navigateur :** En dernier recours, il peut déduire le pays des paramètres de langue du navigateur, bien que ce soit moins précis. Vous pouvez ajuster la priorité dans les paramètres du module.

**Q : Ce module affectera-t-il mon référencement ? Google indexera-t-il toujours mes produits masqués ?**
R : Le module masque les produits de l'affichage front-office pour des pays spécifiques. Généralement, les robots des moteurs de recherche (comme Googlebot) explorent souvent à partir d'adresses IP spécifiques (par exemple, des IP basées aux États-Unis). Si vos produits sont masqués pour les États-Unis, Google pourrait ne pas les voir. S'ils sont masqués pour d'autres pays mais visibles pour les États-Unis, Google pourrait toujours les indexer. Pour les préoccupations critiques en matière de référencement, envisagez d'utiliser la fonction native « Désactiver le produit » de PrestaShop ou des règles `robots.txt` spécifiques si vous ne voulez absolument pas qu'un produit soit indexé nulle part. Ce module est principalement destiné à l'expérience utilisateur front-end et à la conformité, pas au contrôle du référencement.

**Q : Puis-je masquer des produits pour des clients ou des groupes de clients spécifiques, quel que soit leur pays ?**
R : Oui ! Le module inclut les paramètres « Exclure des groupes de clients » et « Exclure des clients ». Ceux-ci vous permettent de spécifier des groupes ou des clients individuels qui verront *toujours* tous les produits, contournant ainsi les règles de masquage basées sur le pays. Ceci est utile pour les VIP, les partenaires B2B ou le personnel interne.

**Q : Que se passe-t-il si un client d'un pays restreint tente d'accéder à un produit masqué via un lien direct ?**
R : Le module est conçu pour empêcher l'accès. Généralement, ils seront redirigés vers la page d'accueil ou une erreur « page introuvable », garantissant qu'ils ne peuvent pas visualiser ou ajouter le produit restreint à leur panier.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Cacher des produits par pays » (`hbc`) fonctionne principalement en surchargeant les classes PrestaShop de base et en utilisant des hooks pour intercepter et modifier les requêtes de produits avant qu'elles ne soient affichées au client. Il utilise l'`ObjectModel` de PrestaShop pour le stockage de la configuration et s'appuie sur la géolocalisation IP ou les données d'adresse client pour déterminer le pays du visiteur. La logique du module est injectée dans le processus de filtrage des produits, garantissant que les produits restreints sont supprimés des listes, des résultats de recherche et des tentatives d'accès direct.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient aucun contrôleur d'administration Front-Office ou Back-Office dédié. Sa configuration est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles de base (`classes/`)

Le module implémente des surcharges pour modifier le comportement de base de PrestaShop.

- **`hbc/override/classes/index.php`** : Fichier `index.php` vide standard pour empêcher la liste des répertoires.
- **`hbc/override/classes/shop/index.php`** : Fichier `index.php` vide standard pour empêcher la liste des répertoires.
- **`hbc/override/classes/shop/Shop.php`** :
  - **Nom de la classe** : `Shop` (surcharge la classe `Shop` de base de PrestaShop)
  - **Classe parente** : `ShopCore`
  - **Responsabilité** : Cette surcharge est critique. Elle modifie probablement la façon dont le contexte du produit ou le contexte de la boutique est déterminé, injectant potentiellement une logique de filtrage spécifique au pays à un niveau très fondamental du système multi-boutique et de récupération de produits de PrestaShop. Cela garantit que les règles de visibilité des produits sont appliquées de manière cohérente dans les différentes parties de la boutique. Les développeurs doivent savoir que la surcharge de `Shop.php` peut avoir des effets étendus et peut entrer en conflit avec d'autres modules qui surchargent également cette classe de base.

### 4.4 Actifs JavaScript (`views/js/`)

- **`hbc/lib/searchTool/views/js/autocomplete.js`** :
  - **Portée** : Back-office (probablement utilisé dans le formulaire de configuration du module).
  - **Objectif** : Ce script fournit une fonctionnalité d'autocomplétion, spécifiquement pour le champ de saisie « Exclure des clients » dans la configuration du module. Il effectue probablement des appels AJAX à un point de terminaison d'administration PrestaShop pour rechercher des clients au fur et à mesure que l'administrateur tape, améliorant ainsi la convivialité pour la sélection de clients individuels.
  - **Fonctionnalité clé** :
    - Initialise un widget d'autocomplétion sur un champ de saisie spécifique (par exemple, `#hbc_exclude_customer`).
    - Envoie des requêtes AJAX (par exemple, à `admin-ajax.php` ou à un contrôleur d'administration dédié) avec la requête tapée.
    - Analyse les réponses JSON contenant les données client (ID, nom, e-mail).
    - Affiche les suggestions dans une liste déroulante.
    - Gère la sélection d'un client, remplissant un champ de saisie masqué avec l'ID du client et affichant le nom.
    - Gère la suppression des clients sélectionnés de la liste.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`hbc/lib/searchTool/views/css/autocomplete.css`** :
  - **Portée** : Back-office (style le widget d'autocomplétion).
  - **Objectif** : Fournit le style pour l'outil de recherche d'autocomplétion client utilisé dans la configuration du module. Cela inclut le style pour le champ de saisie, la liste déroulante des suggestions et potentiellement l'affichage des clients sélectionnés.
  - **Sélecteurs clés** : Cible probablement les classes et les ID associés au widget d'autocomplétion, tels que `.autocomplete-container`, `.autocomplete-results`, `.autocomplete-item` et les éléments pour l'affichage des balises/jetons sélectionnés.

### 4.6 Structure de modèle Smarty (`views/templates/`)

- **`hbc/lib/searchTool/views/scripts.tpl`** :

  - **Portée** : Back-office.
  - **Objectif** : Ce modèle inclut probablement les fichiers JavaScript et CSS nécessaires pour l'outil de recherche d'autocomplétion (`autocomplete.js` et `autocomplete.css`) et initialise potentiellement la logique JavaScript. Il est probablement inclus dans le modèle de configuration principal.
- **`hbc/views/templates/admin/AdminTab.tpl`** :

  - **Portée** : Back-office.
  - **Objectif** : Ce modèle est probablement un wrapper générique ou un composant utilisé dans la page de configuration du module. Il pourrait définir la structure d'une interface à onglets ou d'une section spécifique dans les paramètres du module.
- **`hbc/views/templates/admin/button-subcategories.tpl`** :

  - **Portée** : Back-office.
  - **Objectif** : Ce modèle rend probablement un bouton ou un élément d'interface utilisateur lié à la sélection de catégories, spécifiquement pour inclure/exclure des sous-catégories lors de la sélection de catégories parentes dans le formulaire de configuration.
- **`hbc/views/templates/admin/configuration.tpl`** :

  - **Portée** : Back-office.
  - **Objectif** : C'est le modèle Smarty principal pour la page de configuration du module. Il rend tous les paramètres, champs de saisie, interrupteurs et listes décrits dans la section 4.1. Il utilise les composants de formulaire d'aide de PrestaShop et inclut probablement `scripts.tpl` pour la fonctionnalité d'autocomplétion.
- **`hbc/views/templates/hook/displayHeader.tpl`** :

  - **Portée** : Front-office.
  - **Hook** : `displayHeader`
  - **Objectif** : Ce modèle est rendu dans la section `<head>` de chaque page du front-office. Il pourrait être utilisé pour :
    - Injecter du JavaScript en ligne pour la détection du pays côté client (moins probable étant donné le filtrage côté serveur).
    - Définir des variables JavaScript basées sur la configuration du module (par exemple, mode de simulation).
    - Inclure des fichiers CSS ou JS supplémentaires nécessaires globalement pour la fonctionnalité front-office du module (bien que le filtrage de base soit côté serveur).
    - Potentiellement gérer les redirections ou les vérifications initiales basées sur la géolocalisation avant que la page ne se charge complètement.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module utilise principalement la table `ps_configuration` de PrestaShop pour stocker ses paramètres.
  - Les clés de configuration incluent : `HBC_EXCLUDE_GROUP`, `HBC_EXCLUDE_CUSTOMER`, `HBC_SIMULATE_ON`, `HBC_SIMULATE_IP`, `HBC_DELIVERY`, `HBC_WHITELIST_ON`, `HBC_COUNTRY`, `HBC_WTD`, `HBC_MANUFACT`, `HBC_CATEGORIES`, `HBC_PRIORITY`.
  - Aucune table SQL personnalisée n'est créée par ce module.
- **Table des hooks enregistrés** :

| Nom du hook | Portée | Moment d'exécution | Objectif technique |
| --- | --- | --- | --- |
| `displayHeader` | Front-office | Dans la section `<head>` de chaque page. | Potentiellement pour injecter des scripts côté client, des balises meta ou des vérifications initiales. |
| `actionAdminControllerSetMedia` | Back-office | Lorsqu'un contrôleur d'administration définit ses ressources multimédias. | Utilisé pour charger le CSS/JS de la page de configuration du module (par exemple, `autocomplete.js`, `autocomplete.css`). |
| `actionDispatcherAfter` | Front-office | Après que le dispatcher a traité la requête. | Pourrait être utilisé pour effectuer des redirections ou des vérifications finales après qu'une page a été identifiée mais avant le rendu. |
| `displayFilterProductSearch` | Front-office | Pendant le filtrage de la recherche de produits. | **CRITIQUE** : Ce hook est utilisé pour injecter la logique du module dans la requête de recherche de produits, garantissant que les produits masqués sont exclus des résultats de recherche. |
| `actionProductUpdate` | Back-office | Après la mise à jour d'un produit dans le Back Office. | Pourrait être utilisé pour vider le cache lié à la visibilité des produits ou réévaluer les règles pour le produit mis à jour. |
| `displayAdminProductsExtra` | Back-office | Sur la page d'édition de produit dans le Back Office. | Pourrait être utilisé pour afficher des informations ou des paramètres supplémentaires liés au masquage de produits pour le produit spécifique en cours d'édition (bien que non explicitement identifié dans les paramètres). |
| `actionCartSave` | Front-office | Lorsque le panier est enregistré (par exemple, produit ajouté/supprimé). | Pourrait être utilisé pour empêcher l'ajout de produits masqués au panier ou pour les supprimer si le pays du client change. |
| `FilterProductSearch` | Front-office | Pendant le filtrage de la recherche de produits (similaire à `displayFilterProductSearch`). | **CRITIQUE** : Un autre hook pour modifier les requêtes de recherche de produits, garantissant un filtrage complet dans différents contextes de recherche. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Cacher des produits par pays », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez rencontrer.
