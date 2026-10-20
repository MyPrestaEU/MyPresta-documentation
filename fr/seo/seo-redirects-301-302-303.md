---
title: "Redirections SEO 301, 302, 303 - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Redirections SEO 301, 302, 303 par MyPresta.eu."
sidebar:
  label: "Redirections SEO 301, 302, 303 - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Seo Redirects 301, 302, 303 sur MyPresta.eu](https://mypresta.eu/modules/seo/seo-redirects-301-302-303.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/seo/seo-redirects-301-302-303/)
>
> ---


# Redirections SEO 301, 302, 303

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement nécessaire au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

Le module « Redirections SEO 301, 302, 303 » offre une suite complète d'outils, accessibles via un menu dédié dans votre Back Office PrestaShop. Après l'installation, vous trouverez un nouvel élément de menu, généralement sous **« SEO & SEM »** ou **« Paramètres avancés »**, nommé **« Redirections SEO »** ou similaire. Ce menu contiendra plusieurs sous-éléments, chacun menant à un écran de configuration spécifique.

### 2.1 Page de configuration principale du module (Back Office > Modules > Configurer)

Cet écran de configuration initial (accessible en cliquant sur « Configurer » après l'installation) fournit les paramètres généraux du module.

- **Ce que fait ce paramètre :** Cet écran contient généralement l'activation de base du module et peut-être quelques paramètres globaux.
- **Effet de la modification de ce paramètre :**
  - *Activation du module :* Active la logique de redirection dans votre boutique.
  - *Désactivation du module :* Arrête toutes les redirections gérées par ce module.
- **Valeur recommandée :** **Activé** pour que le module fonctionne.
- **Scénario / exemple de marchand :** Après l'installation, vous voudrez vous assurer que le module est actif afin qu'il puisse commencer à gérer vos redirections.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module organise ses puissantes fonctionnalités en plusieurs sections distinctes, chacune gérée par un contrôleur d'administration dédié. Vous les trouverez sous l'élément de menu principal « Redirections SEO » dans votre Back Office PrestaShop.

#### 2.2.1 Tableau de bord (AdminSeoRedirectDashboardController)

**Nom de l'écran et emplacement du menu :** **Redirections SEO > Tableau de bord**
Cet écran fournit un aperçu des performances et de l'état de vos redirections. C'est votre centre névralgique pour comprendre rapidement comment vos redirections fonctionnent.

- **Actions et paramètres disponibles :**
  - **Aperçu des redirections :** Affiche des statistiques telles que le nombre total de redirections actives, les redirections créées et peut-être le nombre de fois où les redirections ont été déclenchées.
  - **Historique/Activité des redirections :** Peut afficher les tentatives de redirection récentes, y compris les erreurs 404 détectées et les URL redirigées avec succès.
  - **SEOR\_DASHBOARD\_PERIOD :** Ce paramètre contrôle probablement la période pour laquelle les statistiques du tableau de bord sont affichées (par exemple, les 7 derniers jours, les 30 derniers jours, depuis toujours).
- **Effet des modifications :** La modification de la période du tableau de bord mettra à jour les statistiques affichées pour refléter la période sélectionnée, vous aidant à analyser les tendances sur différentes durées.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vérifiez ce tableau de bord régulièrement pour surveiller la santé de vos redirections, identifier toute nouvelle erreur 404 nécessitant une attention et vous assurer que vos efforts SEO portent leurs fruits.

#### 2.2.2 Liste des redirections (AdminSeoRedirectListController)

**Nom de l'écran et emplacement du menu :** **Redirections SEO > Liste des redirections**
C'est le cœur du module, où vous créez, modifiez et gérez les règles de redirection individuelles.

- **Actions et paramètres disponibles :**
  - **Ajouter une nouvelle redirection :** Un formulaire pour créer une nouvelle règle de redirection.
    - **Ancienne URL (URL source) :** L'URL exacte qui n'est plus valide ou à partir de laquelle vous souhaitez rediriger.
    - **Nouvelle URL (URL cible) :** L'URL exacte vers laquelle les visiteurs et les moteurs de recherche doivent être envoyés.
    - **Type de redirection :**
      - **301 Redirection permanente :** Indique aux moteurs de recherche que la page a été déplacée de manière permanente. C'est le type le plus courant et le plus favorable au SEO, transmettant presque tout le « jus de lien ». Utilisez-le lorsqu'une page a disparu définitivement et est remplacée par une autre.
      - **302 Trouvé / Redirection temporaire :** Indique aux moteurs de recherche que le déplacement est temporaire. Utilisez-le si vous vous attendez à ce que l'ancienne URL redevienne active à l'avenir (par exemple, pour des produits saisonniers, des tests A/B). Moins de valeur SEO est transmise.
      - **303 Voir Autre :** Similaire au 302, souvent utilisé après une requête POST pour rediriger vers une nouvelle page afin d'éviter une nouvelle soumission. Moins courant pour les redirections SEO générales.
    - **Statut (Activé/Désactivé) :** Vous permet d'activer ou de désactiver une règle de redirection spécifique sans la supprimer.
  - **Modifier/Supprimer des redirections :** Modifiez les règles existantes ou supprimez-les.
  - **Rechercher/Filtrer :** Trouvez des redirections spécifiques par ancienne ou nouvelle URL.
  - **Actions en masse :** Appliquez des actions (activer, désactiver, supprimer) à plusieurs redirections sélectionnées.
- **Effet des modifications :**
  - *Ajout d'une redirection :* Commence immédiatement à rediriger le trafic de l'ancienne URL vers la nouvelle selon le type spécifié.
  - *Modification d'une redirection :* Met à jour le comportement de redirection.
  - *Suppression d'une redirection :* Supprime la règle, ce qui peut entraîner des erreurs 404 si l'ancienne URL est toujours consultée.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Chaque fois que vous supprimez un produit, modifiez l'URL d'une catégorie ou mettez à jour l'adresse d'une page, créez immédiatement une redirection 301 de l'ancienne URL vers la nouvelle.
  2. Vérifiez régulièrement vos journaux d'erreurs 404 (par exemple, dans Google Search Console ou la section Audit du module) et ajoutez des redirections pour les liens brisés fréquemment rencontrés.

#### 2.2.3 Importer des redirections (AdminSeoRedirectImportController)

**Nom de l'écran et emplacement du menu :** **Redirections SEO > Importer**
Cet écran vous permet de télécharger un fichier (généralement CSV) contenant de nombreuses règles de redirection, ce qui facilite la gestion d'un grand nombre de redirections.

- **Actions et paramètres disponibles :**
  - **Télécharger un fichier CSV :** Sélectionnez un fichier depuis votre ordinateur. Le fichier doit contenir des colonnes pour « Ancienne URL », « Nouvelle URL » et « Type de redirection ».
  - **IV\_COL\_DELIMITER :** Ce paramètre définit le caractère utilisé pour séparer les colonnes dans votre fichier CSV (par exemple, virgule, point-virgule, tabulation).
  - **SEOR\_SAFE\_ROLLOUT :** Ce paramètre contrôle probablement un « mode sécurisé » pour les importations, vous permettant peut-être de prévisualiser les modifications ou d'activer les redirections progressivement pour éviter les problèmes accidentels.
- **Effet des modifications :**
  - *Importation d'un fichier :* Crée plusieurs règles de redirection en masse, ce qui réduit considérablement l'effort manuel.
  - *Modification du délimiteur :* Garantit que le module analyse correctement votre fichier CSV.
  - *Déploiement sécurisé :* S'il est activé, peut permettre un déploiement échelonné des redirections, vous laissant le temps de vérifier avant qu'elles ne soient mises en ligne.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Utilisez cette fonctionnalité lors de la migration d'une boutique, d'une restructuration majeure du site ou du nettoyage d'un grand nombre d'erreurs 404 accumulées. Testez toujours un petit lot en premier si possible.

#### 2.2.4 Audit (AdminSeoRedirectAuditController)

**Nom de l'écran et emplacement du menu :** **Redirections SEO > Audit**
L'outil d'audit vous aide à identifier les liens brisés (erreurs 404) sur votre site web, qui sont des candidats privilégiés pour la redirection.

- **Actions et paramètres disponibles :**
  - **Rechercher les erreurs 404 :** Lance une analyse de votre site web (ou d'une partie spécifique) pour trouver les pages qui renvoient un statut 404.
  - **Liste des erreurs 404 :** Affiche un tableau des liens brisés détectés, souvent avec la page de référence (où le lien brisé a été trouvé) et le nombre de fois où il a été consulté.
  - **Option de création de redirection :** Créez directement une règle de redirection pour une erreur 404 détectée à partir de cet écran.
- **Effet des modifications :** L'exécution d'un audit vous aide à trouver et à corriger de manière proactive les problèmes qui nuisent au SEO et à l'expérience utilisateur.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Exécutez un audit périodiquement (par exemple, mensuellement) pour détecter les nouveaux liens brisés qui pourraient apparaître en raison de modifications de contenu ou de liens externes. Priorisez la correction des 404 fréquemment consultés ou liés à des pages importantes.

#### 2.2.5 Historique (AdminSeoRedirectHistoryController)

**Nom de l'écran et emplacement du menu :** **Redirections SEO > Historique**
Cet écran enregistre tous les événements de redirection, fournissant un enregistrement clair de quand et comment les redirections sont utilisées.

- **Actions et paramètres disponibles :**
  - **Tableau des événements de redirection :** Affiche des détails tels que l'URL d'origine demandée, la nouvelle URL vers laquelle elle a été redirigée, le type de redirection, la date/heure et potentiellement l'agent utilisateur ou l'adresse IP.
  - **Rechercher/Filtrer :** Vous aide à trouver des événements de redirection spécifiques.
- **Effet des modifications :** Il s'agit d'un outil de reporting et de diagnostic. Il ne modifie pas le comportement de la boutique mais fournit des informations précieuses sur la performance de vos redirections.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Utilisez l'historique pour vérifier que des redirections spécifiques fonctionnent comme prévu, résoudre les boucles de redirection inattendues ou analyser les modèles de trafic vers les pages redirigées.

#### 2.2.6 Paramètres (AdminSeoRedirectSettingsController)

**Nom de l'écran et emplacement du menu :** **Redirections SEO > Paramètres**
Cette section contient des options de configuration avancées qui contrôlent le comportement global du module.

- **Actions et paramètres disponibles :**
  - **seor\_pos\_exclude :**
    - **Ce que fait ce paramètre :** Vous permet d'exclure des URL ou des motifs spécifiques d'être automatiquement redirigés ou audités. Ceci est utile pour les pages que vous souhaitez intentionnellement renvoyer une 404 (par exemple, d'anciennes pages de test).
    - **Effet de la modification de ce paramètre :**
      - *Ajout d'URL :* Le module ignorera ces URL lors de l'exécution des redirections ou des audits.
      - *Suppression d'URL :* Ces URL seront soumises à la logique de redirection du module.
    - **Valeur recommandée :** Maintenez cette liste à jour avec toutes les URL qui devraient réellement être des 404 et non redirigées.
    - **Scénario / exemple de marchand :** Vous pourriez avoir une page de destination temporaire que vous souhaitez supprimer complètement, et vous ne voulez pas que le module essaie de la rediriger.
  - **seor\_unavorder :**
    - **Ce que fait ce paramètre :** Contrôle probablement la façon dont le module gère les redirections pour les produits indisponibles ou en rupture de stock.
    - **Effet de la modification de ce paramètre :**
      - *Activé :* Le module pourrait rediriger automatiquement les pages de produits indisponibles vers une page de catégorie ou une page personnalisée « produit introuvable ».
      - *Désactivé :* Les pages de produits indisponibles renverront une erreur 404 standard.
    - **Valeur recommandée :** **Activé** pour améliorer l'expérience utilisateur et le SEO des produits abandonnés.
    - **Scénario / exemple de marchand :** Lorsqu'un produit est retiré de votre catalogue, vous pouvez rediriger automatiquement son ancienne URL vers sa catégorie parente ou un produit similaire, plutôt que d'afficher une 404.
  - **seor\_pos\_category, seor\_pins\_category, seor\_pos\_exclude\_cat, seor\_oos\_cat\_include, seor\_emptycat\_exclusions, seor\_pos, seor\_emptycat :**
    - **Ce que font ces paramètres :** Il s'agit probablement d'un groupe de paramètres liés à la façon dont le module gère les redirections pour les catégories, en particulier les catégories vides, les produits en rupture de stock dans les catégories, ou les exclusions de catégories spécifiques.
      - `seor_pos_category` : Paramètre général pour les redirections de catégories.
      - `seor_pins_category` : Peut être lié aux catégories « épinglées » ou à un comportement de redirection de catégorie spécifique.
      - `seor_pos_exclude_cat` : Exclut des catégories spécifiques de la logique de redirection automatique.
      - `seor_oos_cat_include` : Inclut les produits en rupture de stock dans la logique de redirection de catégorie.
      - `seor_emptycat_exclusions` : Exclut des catégories vides spécifiques d'être redirigées.
      - `seor_pos` : Paramètre général pour les redirections de position de produit/catégorie.
      - `seor_emptycat` : Contrôle les redirections automatiques pour les catégories vides.
    - **Effet de la modification de ces paramètres :** Ces paramètres permettent un contrôle précis de la façon dont les URL de catégorie sont gérées lorsque les catégories sont vides, les produits sont en rupture de stock ou les catégories sont supprimées. Ils peuvent empêcher les 404 pour le contenu dynamique.
    - **Valeur recommandée :** Examinez-les en fonction des besoins spécifiques de votre boutique. Par exemple, la redirection automatique des catégories vides vers leur parent peut être bénéfique.
    - **Scénario / exemple de marchand :** Si une catégorie devient vide parce que tous les produits sont épuisés, vous pouvez vouloir rediriger automatiquement son URL vers la catégorie parente pour éviter une 404.

#### 2.2.7 Outils (AdminSeoRedirectToolsController)

**Nom de l'écran et emplacement du menu :** **Redirections SEO > Outils**
Cette section fournit des fonctions utilitaires, potentiellement y compris l'intégration avec des services externes.

- **Actions et paramètres disponibles :**
  - **SEOR\_GSC\_TOKEN, SEOR\_GSC\_SITE :** Ces paramètres suggèrent une intégration avec Google Search Console (GSC).
    - **Ce que font ces paramètres :** Vous permettent de connecter votre boutique PrestaShop à votre compte Google Search Console. Cela pourrait permettre au module de récupérer automatiquement les erreurs 404 signalées par Google ou de soumettre des sitemaps/redirections à GSC.
    - **Effet de la modification de ce paramètre :**
      - *Configuration de GSC :* Active l'échange de données entre votre boutique et Google Search Console, automatisant potentiellement la découverte de liens brisés et améliorant votre flux de travail SEO.
      - *Non configuré :* Vous devrez vérifier manuellement GSC pour les 404 et ajouter des redirections.
    - **Valeur recommandée :** Configurez si vous utilisez activement Google Search Console pour le SEO de votre boutique.
    - **Scénario / exemple de marchand :** Au lieu de vérifier manuellement Google Search Console pour les nouvelles erreurs 404, le module pourrait les récupérer directement, vous permettant de créer des redirections plus rapidement.

#### 2.2.8 Statistiques (AdminSeoRedirectStatsController)

**Nom de l'écran et emplacement du menu :** **Redirections SEO > Statistiques**
Cet écran fournit des statistiques liées à la santé globale de votre boutique, y compris potentiellement l'impact des redirections.

- **Actions et paramètres disponibles :**
  - **PS\_SHOP\_ENABLE :** Il s'agit d'une clé de configuration PrestaShop standard qui indique si votre boutique est actuellement activée ou en mode maintenance. Le module peut l'afficher comme une vérification rapide de l'état.
  - **Métriques de performance des redirections :** Peut afficher des données agrégées sur le nombre de redirections effectuées, les types les plus courants et leur impact global.
- **Effet des modifications :** Il s'agit principalement d'un écran d'information. Il vous aide à comprendre les performances globales et l'utilisation du module.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Examinez périodiquement ces statistiques pour comprendre le volume des redirections et vous assurer que le module contribue activement à un site sain.

#### 2.2.9 Contrôleur API (AdminSeoRedirectApiController)

**Nom de l'écran et emplacement du menu :** **Redirections SEO > API** (ou similaire, peut être une section technique)
Cet écran est destiné aux utilisateurs avancés ou aux développeurs qui souhaitent interagir avec la fonctionnalité de redirection du module de manière programmatique.

- **Actions et paramètres disponibles :**
  - **Documentation API :** Fournit des informations sur la façon d'utiliser l'API du module pour créer, récupérer, mettre à jour ou supprimer des redirections à partir d'applications externes ou de scripts personnalisés.
  - **Gestion des clés API :** Vous permet de générer et de gérer des clés API pour un accès sécurisé.
- **Effet des modifications :** La configuration de l'accès API permet aux systèmes externes (par exemple, un système de gestion des stocks personnalisé, un outil SEO tiers) d'interagir avec vos redirections.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** N'utilisez ceci que si vous avez des besoins d'intégration spécifiques et une expertise technique.

#### 2.2.10 Contrôleur CLI (AdminSeoRedirectCliController)

**Nom de l'écran et emplacement du menu :** **Redirections SEO > CLI** (ou similaire, peut être une section technique)
Cet écran fournit des informations et des outils pour les opérations d'interface de ligne de commande (CLI) liées au module.

- **Actions et paramètres disponibles :**
  - **Documentation des commandes CLI :** Explique comment exécuter des tâches spécifiques au module à partir de la ligne de commande de votre serveur (par exemple, `php bin/console seoredirect:audit`).
  - **Configuration des tâches Cron :** Fournit des instructions pour configurer des tâches cron afin d'automatiser des tâches telles que des audits réguliers ou des nettoyages de redirections.
- **Effet des modifications :** L'utilisation des outils CLI permet l'automatisation des tâches, ce qui est particulièrement utile pour les grandes boutiques ou les opérations complexes.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Consultez cette section si vous souhaitez automatiser des tâches telles que les audits 404 quotidiens ou les vérifications périodiques de la santé des redirections à l'aide de tâches cron du serveur.

#### 2.2.11 Contrôleur de recherche (AdminSeoredirectSearchController)

**Nom de l'écran et emplacement du menu :** **Redirections SEO > Recherche** (ou intégré à d'autres écrans)
Ce contrôleur alimente probablement les fonctionnalités de recherche avancées dans les différentes grilles et listes du module, vous aidant à trouver rapidement des redirections spécifiques, des erreurs 404 ou des entrées d'historique.

- **Actions et paramètres disponibles :**
  - **Filtres de recherche avancés :** Fournit des options de recherche plus granulaires au-delà de la simple recherche de texte, incluant éventuellement des plages de dates, des types de redirection ou des statuts.
- **Effet des modifications :** Améliore votre capacité à naviguer et à gérer de grands ensembles de données au sein du module.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Utilisez ceci lorsque vous avez besoin de localiser rapidement une règle de redirection spécifique ou d'analyser un sous-ensemble de vos données.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Tableau de bord** | `SEOR_DASHBOARD_PERIOD` | Les 30 derniers jours | Contrôle la période pour les statistiques du tableau de bord. |
| **Liste des redirections** | Ancienne URL | N/A | L'URL à rediriger DEPUIS. |
| | Nouvelle URL | N/A | L'URL à rediriger VERS. |
| | Type de redirection | 301 Permanent | Type de redirection (301, 302, 303). 301 est le meilleur pour le SEO. |
| | Statut | Activé | Active/désactive une règle de redirection spécifique. |
| **Importation** | `IV_COL_DELIMITER` | Virgule (`,`) | Caractère séparant les colonnes dans le fichier d'importation CSV. |
| | `SEOR_SAFE_ROLLOUT` | Non | Active un mode sécurisé pour les importations (par exemple, déploiement échelonné). |
| **Paramètres** | `seor_pos_exclude` | Vide | Liste des URL/motifs à exclure de la redirection/audit. |
| | `seor_unavorder` | Oui | Redirige automatiquement les produits indisponibles. |
| | `seor_pos_category` | Oui | Paramètre général pour les redirections de catégories. |
| | `seor_pins_category` | Non | Comportement de redirection de catégorie spécifique. |
| | `seor_pos_exclude_cat` | Vide | Exclut des catégories spécifiques de la redirection automatique. |
| | `seor_oos_cat_include` | Oui | Inclut les produits en rupture de stock dans la logique de redirection de catégorie. |
| | `seor_emptycat_exclusions` | Vide | Exclut des catégories vides spécifiques d'être redirigées. |
| | `seor_pos` | Oui | Paramètre général pour les redirections de position de produit/catégorie. |
| | `seor_emptycat` | Oui | Contrôle les redirections automatiques pour les catégories vides. |
| **Outils** | `SEOR_GSC_TOKEN` | Vide | Jeton API Google Search Console pour l'intégration. |
| | `SEOR_GSC_SITE` | Vide | L'URL de votre site web enregistrée dans Google Search Console. |
| **Statistiques** | `PS_SHOP_ENABLE` | Oui | Affiche l'état actuel de la boutique (activée/maintenance). |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai ajouté une redirection, mais elle ne fonctionne pas. Que dois-je faire ?**
R1 :

- **Vérifiez les fautes de frappe :** Assurez-vous que l'« Ancienne URL » et la « Nouvelle URL » sont tapées exactement correctement dans la Liste des redirections.
- **Videz le cache :** PrestaShop utilise la mise en cache. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ». Videz également le cache de votre navigateur.
- **Statut du module :** Assurez-vous que le module « Redirections SEO 301, 302, 303 » est activé dans **Modules > Gestionnaire de modules**.
- **Ordre des redirections :** Si vous avez plusieurs modules de redirection ou des règles `.htaccess`, il peut y avoir un conflit. Ce module prend généralement la précédence, mais vérifiez le fichier `.htaccess` de votre serveur pour toute règle conflictuelle.
- **URL complète ou URL relative :** Assurez-vous d'utiliser le format correct pour vos URL (par exemple, `/ancienne-page.html` pour les chemins relatifs, ou `https://www.votreboutique.com/ancienne-page.html` pour les chemins complets, selon la façon dont le module les attend).

**Q2 : Ce module va-t-il ralentir ma boutique ?**
R2 : Le module est conçu pour être efficace. Les redirections se produisent très tôt dans le processus de requête, minimisant l'impact. Cependant, avoir des dizaines de milliers de redirections pourrait ajouter une légère surcharge. L'audit et le nettoyage réguliers des redirections inutiles (par exemple, les anciennes 302 temporaires) peuvent aider à maintenir les performances.

**Q3 : Comment gérer les redirections pour les produits temporairement en rupture de stock ?**
R3 :

- Pour les situations temporaires, une **redirection temporaire 302** vers une page de catégorie pertinente ou une page « m'avertir quand disponible » est appropriée. Cela indique aux moteurs de recherche que le produit pourrait revenir.
- Vérifiez l'écran **Paramètres** pour des options comme `seor_unavorder` ou `seor_oos_cat_include`, qui pourraient offrir une gestion automatique des produits en rupture de stock.

**Q4 : Puis-je utiliser des caractères génériques dans mes règles de redirection (par exemple, rediriger toutes les pages d'un ancien répertoire) ?**
R4 : La documentation ou l'interface du module spécifiera s'il prend en charge les expressions régulières ou les caractères génériques (comme `*`). Si c'est le cas, vous pouvez créer des règles puissantes comme `/ancienne-categorie/*` vers `/nouvelle-categorie/$1` (où `$1` capture le reste de l'URL). Sinon, vous devrez lister chaque redirection individuellement ou utiliser la fonction d'importation. Testez toujours les redirections avec caractères génériques avec précaution !

**Q5 : Mon thème personnalisé n'affiche pas correctement les fonctionnalités du module (par exemple, dans la modale d'audit).**
R5 : Les interfaces du back-office du module sont généralement indépendantes de votre thème front-office. Si vous rencontrez des problèmes d'affichage dans le panneau d'administration, il peut s'agir d'un conflit avec un autre module d'administration ou d'une modification du fichier principal de PrestaShop.

- **Videz le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** et videz le cache.
- **Vérifiez la console du navigateur :** Ouvrez les outils de développement de votre navigateur (F12) et recherchez les erreurs JavaScript ou les avertissements CSS dans l'onglet Console lorsque vous êtes sur les pages de configuration du module. Cela peut donner des indices sur les conflits.
- **Contactez le support :** Si le problème persiste, fournissez des captures d'écran et toutes les erreurs de console au support de MyPresta.eu.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Redirections SEO 301, 302, 303 » est construit selon le modèle MVC (Modèle-Vue-Contrôleur) de PrestaShop, avec un fort accent sur le contrôle administratif et la gestion des données. Il utilise `ModuleAdminController` pour son interface back-office étendue, `ObjectModel` pour la gestion des données de redirection, et surcharge le `FrontController` pour intercepter les requêtes tôt et appliquer la logique de redirection. Le module comprend également des contrôleurs API et CLI pour une gestion programmatique et automatisée.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs gèrent les requêtes côté client de la boutique.

- `seoredirect/controllers/front/api.php`
  - **Nom de la classe et classe parente :** `SeoredirectApiModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur sert probablement de point d'accès API front-office, potentiellement pour que des services externes interrogent l'état des redirections ou pour des appels AJAX internes liés à la logique de redirection front-office (bien que la plupart des redirections soient gérées via la surcharge du `FrontController`). Il répondrait à des routes spécifiques définies par le module.
- `seoredirect/controllers/front/cronjob.php`
  - **Nom de la classe et classe parente :** `SeoredirectCronjobModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Fournit un point d'accès front-office pour l'exécution des tâches cron. Cela permet aux tâches cron côté serveur (par exemple, les commandes `wget` ou `curl`) de déclencher des fonctions du module comme l'audit, le nettoyage ou la synchronisation des données sans nécessiter d'authentification back-office.
- `seoredirect/controllers/front/index.php`
  - **Nom de la classe et classe parente :** `SeoredirectIndexModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Un contrôleur frontal de substitution ou par défaut. Dans de nombreux modules, cela pourrait gérer une simple route par défaut ou servir de base pour d'autres contrôleurs frontaux. Compte tenu de la nature du module, sa logique front-office principale se trouve probablement dans la surcharge du `FrontController`.

#### Contrôleurs d'administration Back-Office

Ces contrôleurs gèrent l'interface et les données du module dans le Back Office de PrestaShop.

- `seoredirect/controllers/admin/AdminSeoRedirectApiController.php`
  - **Nom de l'onglet et entité gérée :** « API » (ou similaire, sous le menu Redirections SEO). Gère les clés API et fournit la documentation API.
  - **Responsabilité :** Gère l'affichage et la gestion des identifiants API et de la documentation pour l'interaction programmatique avec le module.
- `seoredirect/controllers/admin/AdminSeoRedirectAuditController.php`
  - **Nom de l'onglet et entité gérée :** « Audit » (sous le menu Redirections SEO). Gère le processus d'audit des erreurs 404.
  - **Responsabilité :** Fournit l'interface pour scanner la boutique à la recherche d'erreurs 404, afficher les résultats et offrir des options pour créer des redirections à partir des liens brisés détectés.
- `seoredirect/controllers/admin/AdminSeoRedirectCliController.php`
  - **Nom de l'onglet et entité gérée :** « CLI » (ou similaire, sous le menu Redirections SEO). Fournit la documentation des commandes CLI.
  - **Responsabilité :** Affiche des informations et des instructions pour l'utilisation des outils d'interface de ligne de commande du module, utiles pour l'automatisation et les tâches avancées.
- `seoredirect/controllers/admin/AdminSeoRedirectDashboardController.php`
  - **Nom de l'onglet et entité gérée :** « Tableau de bord » (sous le menu Redirections SEO). Affiche les statistiques et l'aperçu du module.
  - **Responsabilité :** Présente les métriques clés et un aperçu de l'activité de redirection, potentiellement y compris des graphiques. Gère la configuration `SEOR_DASHBOARD_PERIOD`.
- `seoredirect/controllers/admin/AdminSeoRedirectHistoryController.php`
  - **Nom de l'onglet et entité gérée :** « Historique » (sous le menu Redirections SEO). Gère les enregistrements `seor_history`.
  - **Responsabilité :** Affiche un journal de tous les événements de redirection, y compris la source, la destination, le type et l'horodatage.
- `seoredirect/controllers/admin/AdminSeoRedirectImport.php`
  - **Nom de l'onglet et entité gérée :** « Importer » (sous le menu Redirections SEO). Gère l'importation en masse des redirections.
  - **Responsabilité :** Fournit l'interface pour télécharger des fichiers CSV afin de créer plusieurs règles de redirection. Gère les configurations `IV_COL_DELIMITER` et `SEOR_SAFE_ROLLOUT`.
- `seoredirect/controllers/admin/AdminSeoRedirectListController.php`
  - **Nom de l'onglet et entité gérée :** « Liste des redirections » (sous le menu Redirections SEO). Gère les enregistrements `seor` (redirection).
  - **Responsabilité :** L'interface principale pour ajouter, modifier, supprimer et lister les règles de redirection individuelles 301, 302, 303.
- `seoredirect/controllers/admin/AdminSeoredirectSearchController.php`
  - **Nom de l'onglet et entité gérée :** « Recherche » (ou intégré). Alimente la fonctionnalité de recherche.
  - **Responsabilité :** Fournit probablement des capacités de recherche et de filtrage avancées utilisées dans diverses grilles d'administration du module.
- `seoredirect/controllers/admin/AdminSeoRedirectSettings.php`
  - **Nom de l'onglet et entité gérée :** « Paramètres » (sous le menu Redirections SEO). Gère les paramètres `ps_configuration` liés au module.
  - **Responsabilité :** Fournit l'interface pour configurer le comportement global du module, tel que les exclusions, les redirections automatiques pour les produits indisponibles/catégories vides, et d'autres options avancées. Gère `seor_pos_exclude`, `seor_unavorder`, `seor_pos_category`, `seor_pins_category`, `seor_pos_exclude_cat`, `seor_oos_cat_include`, `seor_emptycat_exclusions`, `seor_pos`, `seor_emptycat`.
- `seoredirect/controllers/admin/AdminSeoRedirectStats.php`
  - **Nom de l'onglet et entité gérée :** « Statistiques » (sous le menu Redirections SEO). Affiche les statistiques générales de la boutique et du module.
  - **Responsabilité :** Fournit un aperçu de l'état de la boutique (`PS_SHOP_ENABLE`) et potentiellement des données agrégées sur les performances des redirections.
- `seoredirect/controllers/admin/AdminSeoRedirectToolsController.php`
  - **Nom de l'onglet et entité gérée :** « Outils » (sous le menu Redirections SEO). Fournit des fonctions utilitaires.
  - **Responsabilité :** Contient des outils comme l'intégration de Google Search Console (`SEOR_GSC_TOKEN`, `SEOR_GSC_SITE`) et d'autres fonctionnalités utilitaires.
- `seoredirect/controllers/admin/index.php`
  - **Nom de l'onglet et entité gérée :** Pas un contrôleur direct, généralement un fichier vide ou une mesure de sécurité pour empêcher la liste des répertoires.

### 4.3 Classes et modèles principaux (`classes/`)

- `seoredirect/override/classes/controller/FrontController.php`
  - **Ce qu'il fait :** Il s'agit d'une surcharge critique. Il étend la classe `FrontController` de base de PrestaShop.
  - **Méthodes publiques clés et logique métier :** La surcharge intercepte probablement la méthode `init()` ou `postProcess()` du `FrontController`. Avant que PrestaShop ne distribue la requête à un contrôleur de page spécifique, cette surcharge vérifie l'URL demandée par rapport aux règles de redirection stockées du module. Si une correspondance est trouvée, elle émet l'en-tête de redirection HTTP 301, 302 ou 303 approprié et termine la requête, empêchant une 404 et envoyant l'utilisateur vers la nouvelle URL. C'est là que réside la logique de redirection principale.
- `seoredirect/override/classes/controller/index.php`
  - **Ce qu'il fait :** Fichier de substitution, généralement pour la sécurité.
- `seoredirect/override/classes/index.php`
  - **Ce qu'il fait :** Fichier de substitution, généralement pour la sécurité.

*(Note : Le dossier du module n'a pas explicitement listé les classes `ObjectModel` personnalisées comme `SeoRedirect` ou `SeoRedirectHistory`. Cependant, étant donné la présence de `AdminSeoRedirectListController` gérant `seor` et `AdminSeoRedirectHistoryController` gérant `seor_history`, il est très probable qu'il existe des classes `SeoRedirect` et `SeoRedirectHistory` correspondantes (ou des noms similaires) étendant `ObjectModel` dans le répertoire principal du module ou un sous-répertoire `classes/` non explicitement listé dans l'inventaire. Celles-ci définiraient le schéma de base de données pour les redirections et les entrées d'historique.)*

### 4.4 Actifs JavaScript (`views/js/`)

- `seoredirect/examples/console-mock-dashboard-audit.js`
  - **Portée :** Probablement pour le développement/test, pas pour la production.
  - **Détails :** Exemple ou données/logique fictives pour les fonctionnalités du tableau de bord et d'audit, éventuellement utilisées pour le débogage de la console ou la démonstration.
- `seoredirect/views/js/adminSeoRedirectApi.js`
  - **Portée :** Back-office (AdminSeoRedirectApiController).
  - **Détails :** Gère les interactions côté client sur l'écran de configuration de l'API, telles que la génération de clés API, la copie de clés dans le presse-papiers ou l'affichage de modales de documentation API.
- `seoredirect/views/js/adminSeoRedirectAudit.js`
  - **Portée :** Back-office (AdminSeoRedirectAuditController).
  - **Détails :** Gère le processus d'audit, y compris les appels AJAX pour déclencher des analyses, la mise à jour des indicateurs de progression, l'affichage des résultats d'audit dans un tableau dynamique et la gestion des actions telles que la création de redirections à partir des résultats d'audit. Peut inclure des popups modaux pour la prévisualisation ou la confirmation des redirections.
- `seoredirect/views/js/adminSeoRedirectConfig.js`
  - **Portée :** Back-office (Configuration principale du module ou AdminSeoRedirectSettingsController).
  - **Détails :** JavaScript général pour les formulaires de configuration principaux du module. Cela pourrait inclure la validation de formulaire, la visibilité dynamique des champs basée sur d'autres paramètres, ou les appels AJAX pour l'enregistrement de la configuration.
- `seoredirect/views/js/adminSeoRedirectDashboard.js`
  - **Portée :** Back-office (AdminSeoRedirectDashboardController).
  - **Détails :** Alimente les éléments interactifs du tableau de bord, tels que le chargement des données via AJAX, le rendu des graphiques (le cas échéant) et la gestion des changements de sélection de période (`SEOR_DASHBOARD_PERIOD`).
- `seoredirect/views/js/adminSeoRedirectImport.js`
  - **Portée :** Back-office (AdminSeoRedirectImportController).
  - **Détails :** Gère le processus d'importation CSV, y compris la sélection de fichiers, les indicateurs de progression, l'affichage des résultats/erreurs d'importation et potentiellement la gestion de la logique `SEOR_SAFE_ROLLOUT` côté client.

### 4.5 Feuilles de style CSS (`views/css/`)

- `seoredirect/views/css/seoredirect-admin.css`
  - **Portée :** Style des formulaires d'administration du back-office.
  - **Détails :** Contient des styles spécifiques pour les différents écrans d'administration du module, garantissant une interface cohérente et conviviale dans le back-office de PrestaShop. Cela inclurait le style des grilles, des formulaires, des boutons, des modales et des éléments du tableau de bord.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger :** Recherchez les classes préfixées par `seor-` ou `admin-seoredirect-` pour les éléments spécifiques du module.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **Modèles de hook (`views/templates/hook/`)** :

  - La description du module mentionne des hooks front-office (En-tête, Colonnes, Produit, Pied de page), mais l'inventaire des fichiers ne liste pas de modèles de hook spécifiques dans `views/templates/hook/`. Cela suggère que l'interaction front-office est principalement gérée par la surcharge du `FrontController` pour les redirections, plutôt que par le rendu de contenu visible dans les hooks. Si des modèles de hook existent, ils seraient destinés à des éléments d'affichage très spécifiques, non liés aux redirections.
- **Modèles d'administration (`views/templates/admin/`)** :

  - `seoredirect/lib/searchTool/views/scripts.tpl` : Contient probablement du JavaScript ou de la logique Smarty pour un outil de recherche générique utilisé sur plusieurs écrans d'administration.
  - `seoredirect/views/admin/adminSearch.tpl` : Modèle pour une interface de recherche générique dans l'administration.
  - `seoredirect/views/admin/adminSearchCategory.tpl` : Modèle pour la recherche/sélection de catégories dans l'administration.
  - `seoredirect/views/admin/adminSearchCategoryToMove.tpl` : Modèle pour la recherche de déplacement de catégorie.
  - `seoredirect/views/admin/adminSearchCategoryToMoveInStock.tpl` : Modèle pour la recherche de déplacement de catégorie, spécifiquement pour les articles en stock.
  - `seoredirect/views/admin/adminSeoRedirectImport.tpl` : Le modèle principal pour l'écran d'importation (AdminSeoRedirectImportController).
  - `seoredirect/views/admin/stats.tpl` : Modèle pour l'écran des statistiques (AdminSeoRedirectStatsController).
  - `seoredirect/views/templates/admin/api.tpl` : Modèle pour l'écran de configuration de l'API (AdminSeoRedirectApiController).
  - `seoredirect/views/templates/admin/audit.tpl` : Modèle pour l'écran d'audit (AdminSeoRedirectAuditController).
  - `seoredirect/views/templates/admin/cli.tpl` : Modèle pour l'écran de documentation CLI (AdminSeoRedirectCliController).
  - `seoredirect/views/templates/admin/dashboard.tpl` : Modèle pour le tableau de bord du module (AdminSeoRedirectDashboardController).
  - `seoredirect/views/templates/admin/employee_permissions.tpl` : Modèle pour la gestion des permissions des employés liées aux onglets d'administration du module.
  - `seoredirect/views/templates/admin/import.tpl` : Un autre modèle pour la fonctionnalité d'importation (pourrait être un wrapper ou une partie spécifique du processus d'importation).
  - `seoredirect/views/templates/admin/seo_redirect_settings/helpers/options/options.tpl` : Un modèle partiel pour le rendu des options dans l'écran des paramètres (AdminSeoRedirectSettingsController).
  - `seoredirect/views/templates/admin/tools.tpl` : Modèle pour l'écran des outils (AdminSeoRedirectToolsController).
  - `seoredirect/views/templates/admin/_api_documentation_modal.tpl` : Un modèle modal pour l'affichage de la documentation API.
  - `seoredirect/views/templates/admin/_audit_preview_modal.tpl` : Un modèle modal pour la prévisualisation des résultats d'audit ou des créations de redirection.
  - `seoredirect/views/templates/admin/_cli_documentation_modal.tpl` : Un modèle modal pour l'affichage de la documentation CLI.
- **Modèles Front-office (`views/templates/front/`)** :

  - Aucun modèle front-office spécifique n'est listé, ce qui renforce l'idée que le fonctionnement front-end du module se fait principalement via la surcharge du `FrontController` pour la redirection, et non via du contenu visible.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - `ps_seor` : Stocke les règles de redirection principales (Ancienne URL, Nouvelle URL, Type de redirection, Statut, etc.). Cette table est gérée par `AdminSeoRedirectListController` et l'`ObjectModel` `SeoRedirect` (implicite).
  - `ps_seor_history` : Stocke un journal de toutes les redirections déclenchées (Requête d'origine, Redirigé vers, Type, Horodatage, etc.). Cette table est gérée par `AdminSeoRedirectHistoryController` et l'`ObjectModel` `SeoRedirectHistory` (implicite).
  - `ps_configuration` : Stocke les paramètres globaux spécifiques au module comme `SEOR_DASHBOARD_PERIOD`, `IV_COL_DELIMITER`, `SEOR_SAFE_ROLLOUT`, `seor_pos_exclude`, `seor_unavorder`, `seor_pos_category`, `seor_pins_category`, `seor_pos_exclude_cat`, `seor_oos_cat_include`, `seor_emptycat_exclusions`, `seor_pos`, `seor_emptycat`, `SEOR_GSC_TOKEN`, `SEOR_GSC_SITE`.
- **Table des hooks enregistrés** :

  | Nom du hook | Moment d'exécution | Objectif technique |
  | --- | --- | --- |
  | `actionFrontControllerSetMedia` | Avant que le contrôleur frontal ne rende le contenu | Charge potentiellement le JS/CSS du front-office s'il y en a, bien qu'improbable pour un module de redirection. |
  | `actionDispatcherBefore` | Très tôt dans le cycle de vie de la requête, avant la distribution à un contrôleur. | **CRITIQUE :** C'est le hook le plus probable pour que la surcharge du `FrontController` intercepte la requête et applique la logique de redirection. Il permet au module de rediriger avant même que PrestaShop n'essaie de trouver la page d'origine. |
  | `displayAdminProductsExtra` | Sur la page d'édition de produit dans le back-office. | Pourrait être utilisé pour afficher l'état de redirection d'un produit ou suggérer la création d'une redirection si l'URL du produit est modifiée. |
  | `displayAdminCategoriesExtra` | Sur la page d'édition de catégorie dans le back-office. | Similaire aux produits, pourrait afficher l'état de redirection ou suggérer des redirections pour les changements d'URL de catégorie. |
  | `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Improbable pour la logique de redirection principale, mais pourrait être utilisé pour ajouter des balises meta ou des canoniques liés aux redirections si nécessaire. |
  | `displayRightColumn` | Dans la colonne de droite des pages du front-office. | Improbable pour ce module. |
  | `displayFooter` | Dans le pied de page de chaque page du front-office. | Improbable pour ce module. |
  | `actionValidateOrder` | Après qu'une commande est validée avec succès. | Pourrait être utilisé pour enregistrer ou auditer les redirections liées aux processus de commande, bien que moins direct. |
  | `actionModuleInstall` | Lors de l'installation du module. | Crée les tables de base de données, enregistre les hooks, définit les valeurs de configuration par défaut. |
  | `actionModuleUninstall` | Lors de la désinstallation du module. | Nettoie les tables de base de données, désenregistre les hooks, supprime les valeurs de configuration. |
  | `actionAdminControllerSetMedia` | Avant qu'un contrôleur d'administration ne rende le contenu. | Charge le JS/CSS du back-office pour les pages d'administration du module. |
  | `actionAdminSeoRedirectSave` | Hook personnalisé, probablement déclenché après l'enregistrement d'une règle de redirection dans le back-office. | Permet à d'autres modules ou à du code personnalisé de réagir aux changements de redirection. |
  | `actionAdminSeoRedirectDelete` | Hook personnalisé, probablement déclenché après la suppression d'une règle de redirection. | Permet à d'autres modules ou à du code personnalisé de réagir aux suppressions de redirection. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant le module « Redirections SEO 301, 302, 303 ».
