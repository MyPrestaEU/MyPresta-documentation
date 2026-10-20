---
title: "URLs hreflang et canoniques gratuites - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'URLs hreflang et canoniques gratuites' par MyPresta.eu."
sidebar:
  label: "URLs hreflang et canoniques gratuites - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Free hreflang & canonical urls sur MyPresta.eu](https://mypresta.eu/modules/seo/free-hreflang-canonical-urls.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/seo/free-hreflang-canonical-urls/)
>
> ---


# URLs hreflang et canoniques gratuites

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes et préinstallées sur la plupart des environnements d'hébergement. Aucune configuration spéciale du serveur n'est requise.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après avoir installé le module, naviguez vers **Modules > Gestionnaire de modules**, recherchez « URLs hreflang et canoniques gratuites », et cliquez sur « Configurer ». Vous serez présenté avec l'écran de configuration principal du module.

#### **Options de configuration :**

- **Activer les balises hreflang :**

  - **Ce que fait ce paramètre :** Cet interrupteur principal contrôle si le module générera et ajoutera des balises `hreflang` à l'en-tête HTML de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque activé (OUI) :* Le module générera et insérera activement des balises `hreflang` pour toutes les versions linguistiques disponibles de vos pages (pages produit, pages de catégorie, pages CMS, etc.). Ceci est crucial pour le SEO international.
    - *Lorsque désactivé (NON) :* Aucune balise `hreflang` ne sera ajoutée par ce module. Si vous avez une boutique multilingue, les moteurs de recherche pourraient traiter vos différentes versions linguistiques comme du contenu dupliqué, ce qui pourrait nuire à votre classement international.
  - **Valeur recommandée :** **OUI**. Activez toujours ceci si votre boutique prend en charge plusieurs langues ou cible différentes régions.
  - **Scénario / exemple de marchand :** Si vous vendez des produits en anglais et en espagnol, l'activation de cette option garantit qu'un client hispanophone recherchant sur Google verra la version espagnole de votre page produit, et un client anglophone verra la version anglaise.
- **Activer les URLs canoniques :**

  - **Ce que fait ce paramètre :** Cet interrupteur principal contrôle si le module générera et ajoutera des balises d'URL `canonical` à l'en-tête HTML de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque activé (OUI) :* Le module générera et insérera activement des balises `canonical` pour toutes les pages, pointant vers la version préférée de chaque page. Cela aide à consolider les signaux SEO et prévient les problèmes de contenu dupliqué.
    - *Lorsque désactivé (NON) :* Aucune balise `canonical` ne sera ajoutée par ce module. Votre boutique pourrait souffrir de problèmes de contenu dupliqué si le même contenu est accessible via plusieurs URLs (par exemple, avec ou sans barres obliques finales, avec différents paramètres, ou via différents chemins de catégorie).
  - **Valeur recommandée :** **OUI**. Les balises canoniques sont fondamentales pour un bon SEO sur presque tous les sites web.
  - **Scénario / exemple de marchand :** Une page produit peut être accessible via `votreboutique.com/nom-du-produit` et aussi `votreboutique.com/categorie/nom-du-produit`. L'activation des URLs canoniques indique à Google que `votreboutique.com/nom-du-produit` est la version principale, garantissant que tout le crédit SEO va à cette URL unique.
- **Utiliser x-default hreflang :**

  - **Ce que fait ce paramètre :** L'attribut `x-default` hreflang spécifie une page par défaut qui doit être affichée aux utilisateurs lorsqu'aucune autre langue/région ne correspond à leurs paramètres de navigateur ou à leur emplacement.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque activé (OUI) :* Le module ajoutera une balise hreflang `x-default`, pointant généralement vers la langue par défaut de votre boutique ou une version internationale générique. Ceci est utile pour les utilisateurs dont la langue ou la région n'est pas explicitement ciblée par vos autres balises hreflang.
    - *Lorsque désactivé (NON) :* Aucune balise hreflang `x-default` ne sera ajoutée. Les utilisateurs dont la langue/région ne correspond à aucun hreflang spécifique pourraient se voir afficher une page moins pertinente, ou les moteurs de recherche pourraient devoir deviner quelle page afficher.
  - **Valeur recommandée :** **OUI**. Il est généralement recommandé d'inclure un `x-default` pour un SEO international complet, surtout si vous avez une audience mondiale.
  - **Scénario / exemple de marchand :** Si vous avez des versions anglaise (US), anglaise (UK) et française, mais qu'un utilisateur allemand recherche en anglais, le `x-default` peut le diriger vers votre page anglaise (US) générale, garantissant qu'il reçoit toujours un contenu pertinent.
- **Utiliser uniquement le code de langue (par exemple, « en » au lieu de « en-us ») :**

  - **Ce que fait ce paramètre :** Ceci contrôle le format des codes de langue utilisés dans vos balises `hreflang`.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque activé (OUI) :* Le module utilisera uniquement le code de langue ISO à deux lettres (par exemple, `en`, `fr`, `de`). C'est plus simple et convient si vous ciblez une langue globalement plutôt que des régions spécifiques.
    - *Lorsque désactivé (NON) :* Le module utilisera à la fois le code de langue et de région (par exemple, `en-US`, `en-GB`, `fr-CA`). C'est plus précis et recommandé si vous avez un contenu ou des prix différents pour des pays spécifiques au sein de la même langue.
  - **Valeur recommandée :**
    - **NON** si vous avez un ciblage régional spécifique (par exemple, un contenu anglais différent pour les États-Unis par rapport au Royaume-Uni).
    - **OUI** si vos différentes versions linguistiques sont génériques et non spécifiques à un pays (par exemple, une version « Anglais » pour tous les anglophones).
  - **Scénario / exemple de marchand :** Si vous vendez en anglais et avez une seule version anglaise pour tous les pays, choisissez OUI. Si vous avez un contenu/prix anglais séparé pour les États-Unis et le Royaume-Uni, choisissez NON pour utiliser `en-US` et `en-GB`.

#### **Enregistrement de vos paramètres :**

Après avoir fait vos sélections, cliquez sur le bouton **« Enregistrer »** en bas de la page de configuration pour appliquer vos modifications.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer les balises hreflang | OUI | Active les balises hreflang pour le SEO international. |
| Configuration du module | Activer les URLs canoniques | OUI | Active les balises canoniques pour éviter le contenu dupliqué. |
| Configuration du module | Utiliser x-default hreflang | OUI | Fournit une page de secours pour les utilisateurs dont la langue/région ne correspond pas. |
| Configuration du module | Utiliser uniquement le code de langue (par exemple, « en » au lieu de « en-us ») | NON (dépend de la stratégie) | Détermine si hreflang utilise uniquement la langue (`en`) ou la langue-région (`en-US`). |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai activé le module, mais je ne vois aucun changement visuel sur mon site web. Fonctionne-t-il ?**
R1 : Oui, il fonctionne comme prévu ! Ce module opère entièrement en arrière-plan. Il ajoute un code spécial (balises hreflang et canoniques) à la section `<head>` du HTML de votre site web, qui est visible par les moteurs de recherche mais pas par vos clients. Pour vérifier qu'il fonctionne, vous pouvez faire un clic droit sur n'importe quelle page de votre boutique, sélectionner « Afficher la source de la page » (ou similaire), et rechercher « hreflang » ou « canonical ». Vous devriez y voir les balises.

**Q2 : Après avoir activé le module, mon classement de recherche ne s'est pas immédiatement amélioré. À quoi dois-je m'attendre ?**
R2 : Les changements SEO, en particulier ceux liés à l'exploration et à l'indexation, prennent du temps pour être reflétés dans les résultats des moteurs de recherche. Google et les autres moteurs de recherche doivent réexplorer votre site, traiter les nouvelles balises et mettre à jour leur index. Ce processus peut prendre de quelques jours à plusieurs semaines, voire des mois. Continuez à surveiller votre Google Search Console pour tout changement dans l'indexation ou les rapports de ciblage international.

**Q3 : Mon thème personnalisé a des structures d'URL uniques. Ce module fonctionnera-t-il toujours correctement ?**
R3 : Le module est conçu pour s'intégrer aux mécanismes de génération d'URL de base de PrestaShop. Dans la plupart des cas, il devrait fonctionner de manière transparente avec les thèmes personnalisés. Cependant, si votre thème modifie fortement le routage d'URL standard de PrestaShop ou le rendu des pages, il y a une petite chance de conflit. Si vous suspectez un problème, videz d'abord votre cache PrestaShop (**Paramètres avancés > Performance > Vider le cache**). Si les problèmes persistent, contactez le support MyPresta.eu avec les détails de votre thème et de toutes les pages spécifiques où vous rencontrez des problèmes.

**Q4 : J'ai une boutique multilingue, mais certaines pages n'ont pas de traductions pour toutes les langues. Comment le module gère-t-il cela ?**
R4 : Le module génère généralement des balises `hreflang` uniquement pour les langues qui ont réellement du contenu disponible pour une page donnée. Si un produit ou une catégorie n'est pas traduit dans une langue spécifique, le module ne devrait pas générer de balise `hreflang` pour cette traduction inexistante. Assurez-vous que vos traductions PrestaShop sont correctement gérées dans le Back Office.

**Q5 : Je vois plusieurs balises canoniques ou des balises hreflang incorrectes. Qu'est-ce qui pourrait ne pas aller ?**
R5 : Cela indique généralement un conflit avec un autre module SEO ou votre thème qui pourrait également essayer d'ajouter des balises canoniques ou hreflang.
1. **Vérifiez les autres modules SEO :** Désactivez les autres modules SEO un par un pour identifier celui qui est en conflit.
2. **Vérifiez votre thème :** Certains thèmes peuvent coder en dur des balises canoniques.
3. **Videz le cache :** Videz toujours votre cache PrestaShop (**Paramètres avancés > Performance > Vider le cache**) après avoir effectué des modifications de module.
Si le problème persiste, contactez le support MyPresta.eu pour obtenir de l'aide.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « URLs hreflang et canoniques gratuites » (`myhreflang`) est un module PrestaShop léger principalement conçu pour injecter des balises meta `hreflang` et `canonical` dans la section `<head>` des pages du front-office. Il adhère à l'architecture standard des modules PrestaShop, utilisant des hooks pour intégrer sa fonctionnalité sans modifier les fichiers du cœur. La logique du module réside principalement dans son fichier PHP principal, `index.php`, qui gère la configuration, l'installation, la désinstallation et la logique principale de génération des balises. Il utilise les classes `Context` et `Link` de PrestaShop pour déterminer la page actuelle, les langues disponibles et générer les URLs correctes.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient **pas** de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la logique est gérée dans le fichier principal du module et ses méthodes hookées.

### 4.3 Classes et modèles de base (`classes/`)

Ce module ne définit **pas** de classes personnalisées ou d'`ObjectModel` dans un répertoire `classes/`. Toute la logique de base est autonome au sein de la classe `myhreflang` dans `index.php`.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut **pas** de fichiers JavaScript personnalisés. Sa fonctionnalité est purement la génération de balises HTML côté serveur.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut **pas** de fichiers CSS personnalisés. Sa fonctionnalité est purement la génération de balises HTML côté serveur et n'a aucun impact visuel.

### 4.6 Structure des templates Smarty (`views/templates/`)

Le module utilise un seul template Smarty pour rendre les balises `hreflang` et `canonical`.

- **Templates de hook (`views/templates/hook/`)** :
  - `myhreflang/views/templates/hook/hreflang.tpl` : Ce template est responsable de la sortie des balises `<link rel="alternate" hreflang="..." href="..." />` et `<link rel="canonical" href="..." />` réelles.
    - **Rendu dans le hook** : `displayHeader`
    - **Objectif** : Il reçoit un tableau de `hreflang_links` et un `canonical_link` de la méthode `hookDisplayHeader` du module. Il itère ensuite sur ceux-ci pour générer les balises HTML `<link>` nécessaires.
    - **Variables disponibles** :
      - `$hreflang_links` : Un tableau de tableaux associatifs, chacun contenant `lang_code` (par exemple, 'en', 'en-US', 'x-default') et `url`.
      - `$canonical_link` : Une chaîne contenant l'URL canonique de la page actuelle.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de la base de données** :
  Ce module ne crée **pas** de tables SQL personnalisées. Il stocke ses paramètres de configuration directement dans la table `ps_configuration` en utilisant les méthodes standard `Configuration::get()` et `Configuration::updateValue()` de PrestaShop.

  - Clés de configuration stockées dans `ps_configuration` :
    - `MYHREFLANG_HREFLANG_ENABLED` (booléen)
    - `MYHREFLANG_CANONICAL_ENABLED` (booléen)
    - `MYHREFLANG_XDEFAULT_ENABLED` (booléen)
    - `MYHREFLANG_LANG_CODE_ONLY` (booléen)
- **Table des hooks enregistrés** :

  | Nom du hook | Moment d'exécution | Objectif technique |
  | --- | --- | --- |
  | `displayHeader` | Exécuté dans la section `<head>` de chaque page du front-office. | C'est le hook principal utilisé par le module. Il appelle la méthode `hookDisplayHeader()` pour générer et injecter les balises `<link>` `hreflang` et `canonical` dans le `<head>` HTML de la page. |

## 5. Support officiel et mises à jour

Pour le support officiel, les mises à jour du module et toute assistance supplémentaire concernant le module « URLs hreflang et canoniques gratuites », veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes techniques que vous pourriez rencontrer.
