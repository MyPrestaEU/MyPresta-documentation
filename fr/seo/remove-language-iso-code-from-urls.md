---
title: "Supprimer le code ISO de la langue des URLs - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop « Supprimer le code ISO de la langue des URLs » par MyPresta.eu."
sidebar:
  label: "Supprimer le code ISO de la langue des URLs - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Remove language ISO code from urls sur MyPresta.eu](https://mypresta.eu/modules/seo/remove-language-iso-code-from-urls.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/seo/remove-language-iso-code-from-urls/)
>
> ---


# Supprimer le code ISO de la langue des URLs

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration spéciale de serveur n'est généralement nécessaire au-delà de ce que PrestaShop lui-même exige.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du nom du module « Supprimer le code ISO de la langue des URLs » pour accéder à ses paramètres.

La page de configuration de ce module est intentionnellement simple, car sa fonction principale est directe.

**Nom de l'écran :** Configuration de la suppression du code ISO de la langue des URLs
**Emplacement du menu :** Back Office > Modules > Gestionnaire de modules > Supprimer le code ISO de la langue des URLs > Configurer

Sur cet écran, vous trouverez généralement un seul paramètre crucial :

- **Nom du paramètre :** Activer / Désactiver le module
  - **Ce que fait ce paramètre :** Il s'agit de l'interrupteur principal de la fonctionnalité du module. Il contrôle si le module supprime activement le code ISO de la langue de vos URLs de langue par défaut ou non.
  - **Effet de la modification de ce paramètre :**
    - **Lorsqu'il est activé (OUI) :** Le module deviendra actif. Pour la langue par défaut de votre boutique, le code ISO de la langue (par exemple, `/en/` si l'anglais est la langue par défaut) sera supprimé de toutes les URLs générées. Les URLs pour les autres langues resteront inchangées.
    - **Lorsqu'il est désactivé (NON) :** Le module sera inactif. Toutes les URLs, y compris celles de votre langue par défaut, continueront d'afficher le code ISO de la langue (par exemple, `/en/`, `/fr/`).
  - **Valeur recommandée :** **OUI**. Le but principal de l'installation de ce module est d'utiliser sa fonctionnalité, il est donc recommandé de l'activer.
  - **Scénario / exemple de marchand :**
    - Vous venez d'installer le module et souhaitez que vos URLs en anglais (par défaut) ressemblent à `www.votreboutique.com/mon-produit`. Vous devez définir ce paramètre sur **OUI**.
    - Si vous décidez plus tard que vous préférez que le code ISO de la langue soit présent dans toutes les URLs pour une raison quelconque (par exemple, un changement de stratégie SEO spécifique), vous pouvez définir ce paramètre sur **NON** pour rétablir le comportement sans désinstaller le module.

**Note importante après la configuration :**
Après avoir activé ou désactivé le module, il est fortement recommandé de :

1. **Vider votre cache PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » en haut à droite.
2. **Regénérer votre fichier `.htaccess` :** Allez dans **Paramètres de la boutique > Trafic & SEO**, faites défiler jusqu'à la section « Configurer les URLs » et cliquez sur « Enregistrer » (même si vous ne modifiez rien). Cela garantit que les règles de réécriture d'URL sont correctement mises à jour.
3. **Tester vos URLs :** Parcourez votre boutique dans votre langue par défaut et vérifiez que le code ISO de la langue est bien supprimé des URLs. Testez également d'autres langues pour vous assurer que leurs URLs contiennent toujours le code ISO.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer / Désactiver le module | OUI | Contrôle si le module supprime le code ISO de la langue des URLs de la langue par défaut. **OUI** pour des URLs plus propres, **NON** pour conserver les codes ISO pour toutes les langues. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai activé le module, mais le code ISO de la langue apparaît toujours dans les URLs de ma langue par défaut. Que dois-je faire ?**
R : Il s'agit généralement d'un problème de cache ou de `.htaccess` non régénéré.
1. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ».
2. Allez dans **Paramètres de la boutique > Trafic & SEO**, faites défiler jusqu'à « Configurer les URLs » et cliquez sur « Enregistrer ».
3. Vérifiez également le cache de votre navigateur, ou essayez de naviguer dans une fenêtre incognito/privée.

**Q : Ce module affectera-t-il les URLs de mes langues non par défaut ?**
R : Non, le module est spécifiquement conçu pour ne supprimer le code ISO de la langue que pour votre langue *par défaut*. Toutes les autres versions linguistiques continueront d'afficher leurs codes ISO respectifs (par exemple, `/fr/`, `/de/`).

**Q : Ce module va-t-il casser mon SEO existant ou créer des erreurs 404 pour les anciennes URLs ?**
R : Le module fonctionne en remplaçant la génération et la distribution d'URL de base de PrestaShop. Il devrait gérer les redirections en interne. Cependant, pour une sécurité maximale, en particulier sur les boutiques établies, il est toujours bon de :
1. **Sauvegarder votre base de données et vos fichiers** avant l'installation.
2. **Tester minutieusement** sur un environnement de staging d'abord.
3. Après l'activation, surveillez les journaux d'accès de votre serveur et la Google Search Console pour toute erreur 404. Si vous en trouvez, vous devrez peut-être ajouter manuellement des redirections 301 pour des anciennes URLs spécifiques vers leurs nouvelles versions plus propres dans votre fichier `.htaccess`, bien que cela soit rarement nécessaire avec ce module.

**Q : Mon thème personnalisé rencontre des problèmes après l'installation du module. Qu'est-ce qui pourrait ne pas aller ?**
R : Ce module affecte principalement la génération et le routage des URLs, et non l'affichage visuel. Il est peu probable qu'il cause directement des problèmes de thème. Cependant, si votre thème a des structures d'URL très spécifiques et codées en dur ou s'appuie sur du JavaScript qui analyse les URLs d'une manière inhabituelle, il y a une très faible chance de conflit.
\* Tout d'abord, videz votre cache Smarty (**Paramètres avancés > Performances**).
\* Si le problème persiste, désactivez temporairement le module pour voir si le problème disparaît. Si c'est le cas, contactez le support MyPresta.eu avec les détails du problème.

**Q : Ce module prend-il en charge toutes les langues installées dans PrestaShop ?**
R : Oui, il prend en charge toutes les langues. Il identifie votre langue *par défaut* et supprime son code ISO, tout en laissant intacts les codes ISO de toutes les autres langues installées.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de l'implémentation technique du module « Supprimer le code ISO de la langue des URLs », destinée aux développeurs, webmasters et agences techniques.

### 4.1 Vue d'ensemble de l'architecture

Le module « Supprimer le code ISO de la langue des URLs » réalise sa fonctionnalité en surchargeant les classes PrestaShop de base responsables de la génération d'URL (`Link`) et de la distribution d'URL (`Dispatcher`). Cela lui permet d'intercepter et de modifier la façon dont les URLs sont construites et interprétées par PrestaShop, ciblant spécifiquement la suppression du code ISO de la langue pour la langue par défaut. Il utilise le système de surcharge de PrestaShop pour injecter sa logique personnalisée sans modifier directement les fichiers du cœur.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur front-office ou back-office personnalisé. Sa logique est principalement implémentée via des surcharges de classe.

### 4.3 Classes et modèles de base (`classes/`)

La fonctionnalité principale du module réside dans ses surcharges de classe. Ces fichiers sont placés dans `removeiso/override/classes/` pour garantir que le système de surcharge de PrestaShop les prenne en compte.

- **`removeiso/override/classes/Dispatcher.php`**
  - **Nom de la classe :** `Dispatcher` (surcharge la classe `Dispatcher` de base de PrestaShop)
  - **Classe parente :** `DispatcherCore`
  - **Responsabilité :** Cette surcharge est cruciale pour la façon dont PrestaShop *interprète* les URLs entrantes. Elle modifie la méthode `dispatch()` (ou une méthode connexe) pour acheminer correctement les requêtes qui ne contiennent plus le code ISO de la langue par défaut. Lorsqu'une URL comme `www.votreboutique.com/mon-produit` arrive, ce `Dispatcher` surchargé garantit que PrestaShop la comprend comme appartenant à la langue par défaut, même sans le segment `/en/`. Il gère également probablement la logique pour s'assurer que si l'ISO de la langue par défaut *est* présent (par exemple, `www.votreboutique.com/en/mon-produit`), il est redirigé vers l'URL plus propre.
- **`removeiso/override/classes/Link.php`**
  - **Nom de la classe :** `Link` (surcharge la classe `Link` de base de PrestaShop)
  - **Classe parente :** `LinkCore`
  - **Responsabilité :** Cette surcharge est responsable de la façon dont PrestaShop *génère* les URLs sortantes. Elle modifie des méthodes comme `getLanguageLink()`, `getProductLink()`, `getCategoryLink()`, etc., pour empêcher l'inclusion du code ISO de la langue lorsque la langue cible est la langue par défaut de la boutique. Cela garantit que tous les liens générés par PrestaShop (par exemple, dans les templates, les modules) pour la langue par défaut sont propres.
- **`removeiso/override/classes/Tools.php`**
  - **Nom de la classe :** `Tools` (surcharge la classe `Tools` de base de PrestaShop)
  - **Classe parente :** `ToolsCore`
  - **Responsabilité :** La classe `Tools` contient de nombreuses fonctions utilitaires. Cette surcharge pourrait être utilisée pour modifier la façon dont certains paramètres globaux ou chaînes liées aux URL sont gérés, éventuellement en conjonction avec les surcharges `Dispatcher` et `Link` pour assurer la cohérence entre diverses tâches de manipulation d'URL. Elle pourrait, par exemple, affecter la façon dont `$_SERVER['REQUEST_URI']` est interprété ou comment `Tools::redirect()` se comporte dans des scénarios spécifiques liés aux codes de langue.
- **`removeiso/override/classes/index.php`**
  - **Nom de la classe :** N/A (fichier vide)
  - **Classe parente :** N/A
  - **Responsabilité :** Il s'agit d'une pratique de sécurité standard dans les modules PrestaShop pour empêcher la liste des répertoires si le fichier `index.php` est directement accessible. Il ne contient aucun code exécutable.

### 4.4 Actifs JavaScript (`views/js/`)

- **`removeiso/views/js/removeiso.js`**
  - **Portée :** Back-office (probablement chargé sur la page de configuration du module).
  - **Responsabilité :** Compte tenu de la fonction du module, ce fichier JS est probablement minimal. Il pourrait contenir :
    - De simples écouteurs d'événements pour le formulaire de configuration (par exemple, un clic sur le bouton « Enregistrer »).
    - Des appels AJAX pour enregistrer les paramètres de configuration si le formulaire utilise une soumission asynchrone.
    - Des améliorations ou validations d'interface utilisateur de base pour l'unique interrupteur « Activer/Désactiver ».
    - Il ne semble pas avoir de responsabilités front-office ou de logique complexe côté client liée à la manipulation d'URL, car cela est géré côté serveur par les surcharges PHP.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module n'inclut aucun fichier CSS personnalisé. Cela indique que son interface de configuration repose sur le style par défaut du Back Office de PrestaShop.

### 4.6 Structure du template Smarty (`views/templates/`)

- **`removeiso/views/templates/admin/removeiso.tpl`**
  - **Portée :** Template d'administration pour la page de configuration du module.
  - **Responsabilité :** Ce template rend le formulaire de configuration du module dans le Back Office de PrestaShop. Il contiendra la structure HTML pour l'interrupteur « Activer / Désactiver le module » et les éléments de formulaire PrestaShop standard (par exemple, bouton `submit`, messages `alert`). Il est généralement rendu par la méthode `getContent()` de la classe principale du module.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :
  - Ce module ne crée aucune table de base de données personnalisée.
  - Ses paramètres de configuration (par exemple, l'état « Activer/Désactiver ») sont stockés dans la table `ps_configuration`, en utilisant des clés généralement préfixées par `REMOVEISO_` ou similaire (par exemple, `PS_REMOVEISO_ENABLED`).
- **Table des hooks enregistrés** :
  Ce module ne s'enregistre pas explicitement à de nombreux hooks PrestaShop standard pour sa fonctionnalité principale, car son mécanisme principal est la surcharge de classe. La méthode `install()` du module pourrait s'enregistrer à `actionModuleInstall` ou `actionModuleUninstall` pour le nettoyage, mais son comportement d'exécution est piloté par les classes surchargées.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rend le contenu dans la section `<head>` des pages du front-office. | Bien que non directement utilisé pour sa logique d'URL principale, un module pourrait s'accrocher ici pour charger du JS/CSS ou effectuer des vérifications initiales. (Non directement utilisé par ce module pour sa fonction principale). |
| `displayRightColumn` / `displayLeftColumn` | Rend le contenu dans les colonnes latérales. | (Non directement utilisé par ce module). |
| `displayProduct` | Rend le contenu sur la page produit. | (Non directement utilisé par ce module). |
| `displayFooter` | Rend le contenu dans la section du pied de page. | (Non directement utilisé par ce module). |
| `actionDispatcherBefore` | Avant que le dispatcher ne traite la requête. | La classe `Dispatcher` surchargée gère implicitement cela, mais un module pourrait également utiliser ce hook pour la logique de pré-dispatch. |
| `actionDispatcherAfter` | Après que le dispatcher a traité la requête. | (Non directement utilisé par ce module). |
| `actionModuleInstall` | Exécuté lors de l'installation du module. | Pour effectuer des tâches de configuration comme l'enregistrement des surcharges, l'ajout de la configuration à `ps_configuration`. |
| `actionModuleUninstall` | Exécuté lors de la désinstallation du module. | Pour effectuer des tâches de nettoyage comme la suppression des surcharges, la suppression de la configuration de `ps_configuration`. |

Le cœur du fonctionnement de ce module réside dans ses surcharges de classe, qui sont chargées automatiquement par le système d'autoloader de PrestaShop lorsque le module est activé, plutôt que de s'appuyer sur des enregistrements de hooks explicites pour sa manipulation d'URL principale.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Supprimer le code ISO de la langue des URLs », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question que vous pourriez avoir concernant la fonctionnalité du module.
