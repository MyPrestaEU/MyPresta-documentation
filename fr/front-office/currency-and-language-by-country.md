---
title: "Devise et langue par pays - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Devise et langue par pays' par MyPresta.eu."
sidebar:
  label: "Devise et langue par pays - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Currency and language by country sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/currency-and-language-by-country.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/currency-and-language-by-country/)
>
> ---


# Devise et langue par pays

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont habituellement disponibles sur tout environnement d'hébergement moderne. Aucune extension spéciale n'est nécessaire pour ce module.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal et unique pour le module « Devise et langue par pays ». Vous trouverez ici tous les paramètres pour définir comment votre boutique s'adapte aux visiteurs de pays spécifiques.

**Accès :** Back Office > Modules > Gestionnaire de modules > Recherchez « Devise et langue par pays » > Cliquez sur « Configurer ».

#### **1. Sélectionner le pays**

-   **Ce que fait ce paramètre :** Ce menu déroulant vous permet de choisir le pays spécifique pour lequel vous souhaitez appliquer les changements automatiques de langue et de devise.
-   **Effet de la modification de ce paramètre :** Lorsque vous sélectionnez un pays (par exemple, « France »), le module appliquera alors les paramètres de langue et de devise que vous définissez ci-dessous *uniquement* pour les visiteurs détectés comme provenant de ce pays. Si vous ne sélectionnez pas de pays, le module n'appliquera aucune règle de géolocalisation.
-   **Valeur recommandée :** Sélectionnez d'abord le pays que vous souhaitez cibler. Vous ne pouvez configurer qu'un seul pays à la fois avec cette version gratuite.
-   **Scénario / exemple pour le marchand :** Si vous souhaitez que les visiteurs d'Allemagne voient votre boutique en allemand avec la devise Euro, vous sélectionneriez « Allemagne » ici.

#### **2. Activer le changement de langue par visiteur**

-   **Ce que fait ce paramètre :** Ce commutateur contrôle si le module doit automatiquement changer la langue de la boutique pour les visiteurs du pays sélectionné.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (« Activé ») :* Le module tentera de changer la langue du front-office de la boutique pour celle que vous spécifiez dans le paramètre « Sélectionner la langue » ci-dessous, pour les visiteurs du pays choisi.
    -   *Lorsqu'il est désactivé (« Désactivé ») :* La langue ne sera pas automatiquement changée, même si vous avez sélectionné une langue ci-dessous. Le visiteur verra la boutique dans votre langue par défaut ou la langue préférée de son navigateur (si le comportement par défaut de PrestaShop le permet).
-   **Valeur recommandée :** « Activé » si vous souhaitez offrir une expérience linguistique localisée.
-   **Scénario / exemple pour le marchand :** Si vous avez sélectionné « France » comme pays, l'activation de ce paramètre signifie que vous pouvez ensuite choisir « Français » comme langue pour les visiteurs français.

#### **3. Sélectionner la langue**

-   **Ce que fait ce paramètre :** Ce menu déroulant apparaît uniquement si « Activer le changement de langue par visiteur » est activé. Il vous permet de choisir la langue qui sera définie pour les visiteurs du pays sélectionné.
-   **Effet de la modification de ce paramètre :** La langue du front-office de la boutique passera automatiquement à la langue sélectionnée pour les visiteurs du pays choisi. Assurez-vous que cette langue est déjà installée et activée dans votre boutique PrestaShop (Back Office > International > Langues).
-   **Valeur recommandée :** La langue officielle du pays que vous avez sélectionné.
-   **Scénario / exemple pour le marchand :** Si vous avez sélectionné « Espagne » comme pays et activé le changement de langue, vous sélectionneriez « Espagnol » ici.

#### **4. Activer le changement de devise par visiteur**

-   **Ce que fait ce paramètre :** Ce commutateur contrôle si le module doit automatiquement changer la devise de la boutique pour les visiteurs du pays sélectionné.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (« Activé ») :* Le module tentera de changer la devise du front-office de la boutique pour celle que vous spécifiez dans le paramètre « Sélectionner la devise » ci-dessous, pour les visiteurs du pays choisi.
    -   *Lorsqu'il est désactivé (« Désactivé ») :* La devise ne sera pas automatiquement changée. Les prix seront affichés dans la devise par défaut de votre boutique ou la devise sélectionnée manuellement par le client.
-   **Valeur recommandée :** « Activé » si vous souhaitez afficher les prix dans la devise locale.
-   **Scénario / exemple pour le marchand :** Si vous avez sélectionné « États-Unis » comme pays, l'activation de ce paramètre signifie que vous pouvez ensuite choisir « Dollar américain » comme devise pour les visiteurs américains.

#### **5. Sélectionner la devise**

-   **Ce que fait ce paramètre :** Ce menu déroulant apparaît uniquement si « Activer le changement de devise par visiteur » est activé. Il vous permet de choisir la devise qui sera définie pour les visiteurs du pays sélectionné.
-   **Effet de la modification de ce paramètre :** Tous les prix du front-office de la boutique passeront automatiquement à la devise sélectionnée pour les visiteurs du pays choisi. Assurez-vous que cette devise est déjà installée et activée dans votre boutique PrestaShop (Back Office > International > Devises).
-   **Valeur recommandée :** La devise officielle du pays que vous avez sélectionné.
-   **Scénario / exemple pour le marchand :** Si vous avez sélectionné « Japon » comme pays et activé le changement de devise, vous sélectionneriez « Yen japonais » ici.

#### **Remarque importante sur les surcharges (Overrides) :**

Ce module utilise le système de surcharge de PrestaShop pour modifier le comportement de base de la devise et de la langue. Si vous avez d'autres modules qui utilisent également des surcharges pour `Currency.php` ou `Language.php`, il pourrait y avoir des conflits. Testez toujours minutieusement après l'installation.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Sélectionner le pays | Votre pays cible | Définit le pays pour lequel les règles s'appliquent. |
| Configuration du module | Activer le changement de langue par visiteur | Activé | Active le changement de langue automatique pour le pays sélectionné. |
| Configuration du module | Sélectionner la langue | Langue officielle du pays | Définit la langue spécifique pour les visiteurs du pays choisi. |
| Configuration du module | Activer le changement de devise par visiteur | Activé | Active le changement de devise automatique pour le pays sélectionné. |
| Configuration du module | Sélectionner la devise | Devise officielle du pays | Définit la devise spécifique pour les visiteurs du pays choisi. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : La langue/devise ne change pas pour les visiteurs du pays sélectionné. Que dois-je vérifier ?**
R :

1.  **Module activé :** Assurez-vous que le module « Devise et langue par pays » est installé et activé dans le Gestionnaire de modules.
2.  **Configuration enregistrée :** Vérifiez que vous avez sélectionné un pays, activé les options de changement de langue/devise respectives, choisi la langue/devise correcte et cliqué sur « Enregistrer » sur la page de configuration du module.
3.  **Langue/Devise installée et activée :** Vérifiez que la langue et la devise cibles sont installées et activées dans votre Back Office PrestaShop (International > Langues et International > Devises).
4.  **Cache :** Videz le cache de votre PrestaShop (Paramètres avancés > Performances > Vider le cache) et le cache de votre navigateur.
5.  **Précision de la géolocalisation :** Les services de géolocalisation ne sont pas toujours précis à 100 %. Testez avec un VPN pour vous assurer que votre IP est correctement identifiée comme provenant du pays cible.

**Q : Puis-je configurer différentes langues/devises pour plusieurs pays ?**
R : Le module gratuit « Devise et langue par pays » vous permet de configurer des règles pour un seul pays à la fois. Si vous avez besoin d'un ciblage multi-pays avancé, envisagez de passer au module « Geolocation Pro » de MyPresta.eu, qui offre des fonctionnalités plus étendues.

**Q : La langue/devise par défaut de ma boutique s'affiche toujours même après la configuration.**
R : Ce module cible spécifiquement les visiteurs du pays *sélectionné*. Pour tous les autres visiteurs, la langue et la devise par défaut de votre boutique s'appliqueront, ou les paramètres préférés de leur navigateur si PrestaShop est configuré pour les respecter. Assurez-vous de tester depuis le pays exact que vous avez configuré.

**Q : J'ai installé un autre module, et maintenant le changement de langue/devise ne fonctionne plus.**
R : Ce module utilise le système de surcharge de PrestaShop. Si un autre module surcharge également `classes/Currency.php` ou `classes/Language.php`, il pourrait y avoir un conflit. Vérifiez votre `app/config/parameters.php` (pour PS 1.7+) ou `config/settings.inc.php` (pour PS 1.6) pour `_PS_MODE_DEV_` et définissez-le sur `true` pour voir les messages d'erreur. Vous devrez peut-être contacter le support pour obtenir de l'aide afin de résoudre les conflits de surcharge.

**Q : Comment le module détecte-t-il le pays du visiteur ?**
R : Le module utilise l'adresse IP du visiteur pour déterminer sa localisation géographique. C'est une méthode standard pour la géolocalisation.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module « Devise et langue par pays ».

### 4.1 Aperçu de l'architecture

Le module « Devise et langue par pays » (`freegeo`) est un module PrestaShop léger principalement conçu pour modifier la langue et la devise par défaut en fonction de l'adresse IP d'un visiteur. Il y parvient en tirant parti du système de surcharge de PrestaShop pour les classes `Currency` et `Language` de base, et en s'accrochant à l'événement `actionDispatcherBefore` pour exécuter la logique de géolocalisation avant que le contenu de la page principale ne soit rendu. La configuration du module est gérée via la méthode standard `getContent()` dans le fichier principal du module.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur Front-Office ou Back-Office personnalisé. Sa logique est principalement exécutée via des hooks et des surcharges de classes.

### 4.3 Classes et modèles de base (`classes/`)

Le module utilise le système de surcharge de PrestaShop pour injecter sa logique dans les fonctionnalités de base.

-   **`freegeo/override/classes/Currency.php`**

    -   **Nom de la classe :** `Currency` (surcharge la classe `Currency` de base)
    -   **Classe parente :** `CurrencyCore`
    -   **Responsabilité :** Cette surcharge est cruciale pour définir la devise en fonction de la géolocalisation. Elle modifie le comportement de la façon dont la devise active est déterminée. La logique du module dans cette surcharge vérifiera si le paramètre `FREEGEO_CURRENCY_ON` est activé et si le pays du visiteur correspond au `FREEGEO_COUNTRY` configuré. Si c'est le cas, il tentera de forcer la devise à `FREEGEO_CURRENCY`.
    -   **Méthodes clés :** La surcharge modifie probablement les méthodes liées à `getCurrent()` ou `getCurrency()` pour injecter l'ID de la devise géolocalisée.
-   **`freegeo/override/classes/Language.php`**

    -   **Nom de la classe :** `Language` (surcharge la classe `Language` de base)
    -   **Classe parente :** `LanguageCore`
    -   **Responsabilité :** Similaire à la surcharge `Currency`, cette classe est responsable de la définition de la langue en fonction de la géolocalisation. Elle vérifie `FREEGEO_LANGUAGE_ON` et `FREEGEO_COUNTRY` et, si les conditions sont remplies, force la langue à `FREEGEO_LANGUAGE`.
    -   **Méthodes clés :** La surcharge modifie probablement les méthodes liées à `getCurrentLanguage()` ou `getLanguage()` pour injecter l'ID de la langue géolocalisée.
-   **`freegeo/override/classes/index.php`**

    -   **Objectif :** Il s'agit d'un fichier `index.php` vide standard, généralement placé dans les répertoires pour empêcher la liste des répertoires sur les serveurs web, améliorant ainsi la sécurité. Il n'a aucun impact fonctionnel sur la logique du module.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé. Toutes ses fonctionnalités sont gérées côté serveur.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé. Ses fonctionnalités n'impliquent aucun style spécifique du front-office.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **`freegeo/views/advert.tpl`**
    -   **Portée :** Back-office (page de configuration du module).
    -   **Objectif :** Ce template est probablement utilisé pour afficher une publicité ou un message promotionnel pour le module « Geolocation Pro » de MyPresta.eu sur la page de configuration du module. Il sert d'élément marketing au sein de l'interface d'administration.
    -   **Hook :** Ce template est rendu dans la méthode `getContent()` du fichier principal du module, généralement avant ou après le formulaire de configuration principal.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :
    Le module ne crée aucune table de base de données personnalisée. Il stocke ses paramètres de configuration directement dans la table `ps_configuration` de PrestaShop.
-   **Enregistrements de configuration dans `ps_configuration`** :

    -   `FREEGEO_CURRENCY_ON` : Stocke un booléen (0 ou 1) indiquant si le changement de devise est activé.
    -   `FREEGEO_LANGUAGE_ON` : Stocke un booléen (0 ou 1) indiquant si le changement de langue est activé.
    -   `FREEGEO_CURRENCY` : Stocke l'ID de la devise à définir (par exemple, `id_currency`).
    -   `FREEGEO_LANGUAGE` : Stocke l'ID de la langue à définir (par exemple, `id_lang`).
    -   `FREEGEO_COUNTRY` : Stocke le code ISO ou l'ID du pays à cibler.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses ressources média (JS/CSS). | Bien que listé, ce module l'utilise probablement de manière minimale ou pour le chargement de scripts/styles spécifiques côté administration s'il y en avait (aucun détecté dans l'inventaire). |
| `actionDispatcherBefore` | Exécuté très tôt dans le cycle de vie de la requête PrestaShop, avant que le dispatcher ne traite l'URL. | **HOOK CRITIQUE :** C'est là que réside la logique de géolocalisation principale du module. Il est utilisé pour détecter l'adresse IP du visiteur, déterminer son pays, puis, en fonction des paramètres du module, potentiellement remplacer `Context::getContext()->language` et `Context::getContext()->currency` avant que la page ne soit rendue. |
| `actionFrontControllerAfterInit` | Exécuté après l'initialisation d'un contrôleur frontal. | Ce hook pourrait être utilisé pour effectuer des vérifications ou des ajustements supplémentaires après la configuration du contrôleur principal, mais avant le rendu. Il pourrait servir de point de repli ou supplémentaire pour les ajustements de langue/devise si `actionDispatcherBefore` n'est pas suffisant dans tous les scénarios. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Devise et langue par pays », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
