---
title: "Taux de change de la Česká národní banka (CNB) - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Taux de change de la Česká národní banka (CNB)' par MyPresta.eu."
sidebar:
  label: "Taux de change de la Česká národní banka (CNB) - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Currency rates from Česká národní banka (CNB) sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/currency-rates-from-ceska-narodni-banka-cnb.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/currency-rates-from-ceska-narodni-banka-cnb/)
>
> ---


# Taux de change de la Česká národní banka (CNB)

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour récupérer des données externes, et sont presque universellement disponibles sur les environnements d'hébergement modernes.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du nom du module pour accéder à ses paramètres. C'est l'écran de configuration principal et unique du module.

#### **Paramètres et options**

**1. `mypresta_updates` (Mises à jour MyPresta.eu)**

- **Ce que fait ce paramètre :** Il s'agit d'un paramètre standard que l'on retrouve dans de nombreux modules MyPresta.eu. Il contrôle si le module vérifie les mises à jour de MyPresta.eu et affiche des notifications dans votre back office PrestaShop.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Le module vérifiera périodiquement les nouvelles versions disponibles sur MyPresta.eu. Si une mise à jour est trouvée, vous pourriez voir une notification dans votre panneau d'administration PrestaShop, vous invitant à télécharger et installer la nouvelle version. Cela vous aide à rester à jour avec les corrections de bugs et les nouvelles fonctionnalités.
  - *Lorsqu'il est désactivé (NON) :* Le module ne vérifiera pas les mises à jour. Vous ne recevrez aucune notification concernant les nouvelles versions, ce qui signifie que vous devrez vérifier manuellement votre compte MyPresta.eu pour les mises à jour.
- **Valeur recommandée :** **OUI**. Il est toujours recommandé de maintenir les modules à jour pour la sécurité, la compatibilité et les nouvelles fonctionnalités.
- **Scénario / exemple de marchand :** Vous voulez vous assurer que votre module exécute toujours la dernière version la plus stable sans avoir à vérifier constamment manuellement. L'activation de cette option vous avertira lorsqu'une mise à jour est disponible.

**2. `update_` (Fréquence de mise à jour)**

- **Ce que fait ce paramètre :** Ce paramètre détermine la fréquence à laquelle le module tente de récupérer et de mettre à jour les taux de change à partir du flux de la CNB.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est réglé sur un intervalle plus court (par exemple, « Toutes les heures ») :* Vos taux de change seront actualisés plus fréquemment, garantissant que vos prix sont très actuels, ce qui est bénéfique sur les marchés volatils. Cependant, cela pourrait légèrement augmenter la charge du serveur (bien que généralement négligeable pour ce type d'opération).
  - *Lorsqu'il est réglé sur un intervalle plus long (par exemple, « Une fois par jour ») :* Les taux sont mis à jour moins fréquemment. Cela est généralement suffisant car la CNB fournit généralement des taux quotidiens. Cela réduit la charge du serveur.
- **Valeur recommandée :** **Une fois par jour**. La CNB publie généralement des taux quotidiens, donc une mise à jour plus fréquente qu'une fois par jour est souvent inutile et ne fournit pas de données plus récentes.
- **Scénario / exemple de marchand :** Vous gérez une boutique internationale où les fluctuations des taux de change peuvent avoir un impact sur vos marges bénéficiaires. Régler cette option sur « Une fois par jour » garantit que vous disposez toujours des derniers taux officiels sans surcharger votre serveur.

**3. `updatev_` (Méthode de mise à jour)**

- **Ce que fait ce paramètre :** Ce paramètre définit la manière dont le module déclenche le processus de mise à jour des taux de change.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est réglé sur « Tâche Cron » :* Le module s'attend à ce que vous configuriez une tâche cron côté serveur (une tâche planifiée) qui appellera périodiquement une URL spécifique fournie par le module. C'est la méthode la plus fiable et recommandée car elle garantit que les mises à jour se produisent précisément au moment prévu, même si personne ne visite votre boutique.
  - *Lorsqu'il est réglé sur « Au chargement de la page » :* Le module tentera de mettre à jour les taux lorsqu'un client ou un administrateur visite n'importe quelle page de votre boutique. C'est moins fiable car les mises à jour ne se produisent que lorsque du trafic arrive sur votre site, et si votre site a peu de trafic, les mises à jour pourraient être retardées. Cela peut également ralentir légèrement le premier chargement de page pour un visiteur si une mise à jour est due.
- **Valeur recommandée :** **Tâche Cron**. C'est la méthode la plus robuste et la plus efficace pour les tâches planifiées. Le module vous fournira l'URL exacte à utiliser pour votre tâche cron.
- **Scénario / exemple de marchand :** Vous voulez garantir que les taux de change sont mis à jour tous les matins à 3h du matin, quel que soit le trafic du site web. Régler cette option sur « Tâche Cron » et configurer le cron de votre serveur y parviendra de manière fiable.

**4. `currency_` (Devises à mettre à jour)**

- **Ce que fait ce paramètre :** Cela vous permet de sélectionner les devises spécifiques de votre boutique PrestaShop dont les taux de change doivent être mis à jour par le flux de la CNB.
- **Effet de la modification de ce paramètre :**
  - *Lorsque des devises spécifiques sont sélectionnées :* Seules les devises choisies verront leurs taux de change mis à jour par le module. Les autres devises (si vous en avez) conserveront leurs taux définis manuellement ou le mécanisme de mise à jour par défaut de PrestaShop (s'il est actif). Cela vous donne un contrôle granulaire.
  - *Lorsqu'aucune devise n'est sélectionnée (ou toutes sont sélectionnées) :* Le module tentera de mettre à jour toutes les devises actives de votre boutique qui sont présentes dans le flux de la CNB.
- **Valeur recommandée :** Sélectionnez **toutes les devises que vous utilisez activement pour les transactions et qui sont prises en charge par le flux de la CNB**. Généralement, cela inclut l'EUR, l'USD, le GBP et d'autres devises majeures.
- **Scénario / exemple de marchand :** Votre boutique accepte les paiements en EUR, USD et CZK. Vous souhaitez que les taux EUR et USD soient mis à jour par la CNB, mais le CZK est votre devise par défaut et n'a pas besoin de mises à jour externes. Vous sélectionneriez EUR et USD dans cette liste.

#### **URL de la tâche Cron (affichée après la sauvegarde des paramètres)**

- **Ce que cela fait :** Après avoir configuré et enregistré les paramètres du module, surtout si vous choisissez « Tâche Cron » comme méthode de mise à jour, le module affichera une URL unique. Cette URL est ce que la tâche cron de votre serveur doit appeler pour déclencher le processus de mise à jour.
- **Effet de l'utilisation de cette URL :** Lorsque cette URL est accédée (soit par la tâche cron de votre serveur, soit manuellement dans un navigateur), le module exécute sa logique pour récupérer les derniers taux de change de la CNB et les met à jour dans la base de données de votre PrestaShop.
- **Action recommandée :** Copiez cette URL et configurez-la comme une tâche cron sur votre serveur d'hébergement. Consultez la documentation ou le support de votre hébergeur pour savoir comment configurer une tâche cron. Une tâche cron typique pourrait ressembler à `wget -q -O /dev/null "VOTRE_URL_CRON_ICI"`.
- **Scénario / exemple de marchand :** Vous avez défini la fréquence de mise à jour sur « Une fois par jour » et la méthode sur « Tâche Cron ». Le module affiche `https://votreboutique.com/module/cnbrates/cronjob?token=VOTRE_JETON_UNIQUE`. Vous configurerez alors le cron de votre serveur pour exécuter `wget -q -O /dev/null "https://votreboutique.com/module/cnbrates/cronjob?token=VOTRE_JETON_UNIQUE"` une fois toutes les 24 heures.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Mises à jour MyPresta.eu | OUI | Contrôle les notifications de mise à jour de MyPresta.eu. |
| Configuration du module | Fréquence de mise à jour | Une fois par jour | À quelle fréquence le module récupère les nouveaux taux de la CNB. |
| Configuration du module | Méthode de mise à jour | Tâche Cron | Comment le processus de mise à jour est déclenché (tâche planifiée vs. chargement de page). |
| Configuration du module | Devises à mettre à jour | Sélectionner toutes les devises pertinentes | Spécifie quelles devises de votre boutique sont mises à jour par la CNB. |
| Configuration du module | URL de la tâche Cron | (Affichée après la sauvegarde) | L'URL à utiliser pour les tâches cron côté serveur afin de déclencher les mises à jour. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes taux de change ne se mettent pas à jour. Que dois-je vérifier en premier ?**
R : La raison la plus courante est un problème avec la tâche cron.

1.  Allez dans **Modules > Gestionnaire de modules > Configurer** pour le module Taux CNB.
2.  Vérifiez le paramètre « Méthode de mise à jour ». S'il s'agit de « Tâche Cron », assurez-vous d'avoir correctement configuré la tâche cron sur votre serveur d'hébergement en utilisant l'URL fournie. Contactez le support de votre hébergeur si vous ne savez pas comment faire.
3.  Si « Au chargement de la page » est sélectionné, assurez-vous que votre boutique reçoit un trafic régulier. Sinon, passez à « Tâche Cron » pour des mises à jour plus fiables.
4.  Vérifiez également que les devises que vous vous attendez à voir mises à jour sont sélectionnées dans la liste « Devises à mettre à jour ».

**Q : Ce module fonctionne-t-il si la devise par défaut de ma boutique n'est pas le CZK ?**
R : Oui, absolument ! Le module est conçu pour fonctionner même si votre devise par défaut n'est pas le CZK. Il récupère les taux de la CNB, qui fournit des taux de change pour diverses devises par rapport au CZK. Le module convertit ensuite intelligemment ces taux pour mettre à jour les devises non par défaut de votre boutique par rapport à votre devise par défaut réelle.

**Q : À quelle fréquence la CNB met-elle à jour ses taux ?**
R : La Česká národní banka (CNB) publie généralement ses taux de change officiels une fois par jour, généralement les jours ouvrables. Par conséquent, régler la « Fréquence de mise à jour » de votre module sur « Une fois par jour » est généralement suffisant pour capturer les dernières données disponibles.

**Q : J'ai mis à jour le module, mais je ne vois aucun changement. Que puis-je faire ?**
R : Parfois, le système de mise en cache de PrestaShop peut empêcher l'affichage immédiat des changements.

1.  Allez dans **Paramètres avancés > Performance** dans votre back office PrestaShop.
2.  Cliquez sur « Vider le cache » (ou « Vider le cache Smarty » si disponible).
3.  Actualisez votre navigateur (Ctrl+F5 ou Cmd+R) pour vous assurer que vous ne voyez pas une version mise en cache de la page.

**Q : Puis-je déclencher une mise à jour manuellement ?**
R : Oui, si votre « Méthode de mise à jour » est réglée sur « Tâche Cron », vous pouvez visiter manuellement l'URL de la tâche cron (affichée dans la configuration du module) dans votre navigateur web. Cela déclenchera une mise à jour immédiate. Cependant, ceci est uniquement pour les tests/dépannage ; pour les mises à jour régulières, fiez-vous à la tâche cron automatisée.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Taux de change de la Česká národní banka (CNB) » est un module PrestaShop léger conçu pour une tâche unique et ciblée : récupérer et mettre à jour les taux de change. Il utilise principalement un contrôleur front-office pour exposer un point d'accès de tâche cron, permettant des mises à jour automatisées et planifiées. Le module n'introduit pas de nouvelles tables de base de données ou de structures `ObjectModel` complexes, s'appuyant plutôt sur la classe `Currency` et la `Configuration` existantes de PrestaShop pour ses paramètres. Il suit une structure de module PrestaShop de base, s'intégrant aux méthodes `install()` et `uninstall()` pour la configuration et le nettoyage.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    -   `controllers/front/cronjob.php`
        -   **Nom de la classe et classe parente** : `CnbratesCronjobModuleFrontController` étend `ModuleFrontController`.
        -   **Responsabilité** : Ce contrôleur est le cœur de l'automatisation du module. Il répond aux requêtes vers l'URL de la tâche cron (par exemple, `votreboutique.com/module/cnbrates/cronjob?token=...`). Sa méthode `initContent()` (ou une méthode de cycle de vie similaire) contient la logique pour :
            1.  Valider le paramètre `token` par rapport à la configuration stockée pour empêcher tout accès non autorisé.
            2.  Récupérer les derniers taux de change du flux XML de la CNB (généralement `https://www.cnb.cz/cs/financni_trhy/devizovy_trh/kurzy_devizoveho_trhu/denni_kurz.xml`).
            3.  Analyser les données XML.
            4.  Itérer à travers les devises configurées dans PrestaShop.
            5.  Pour chaque devise sélectionnée, calculer son nouveau taux de change basé sur les données de la CNB (qui est généralement relatif au CZK) et la devise par défaut de la boutique.
            6.  Mettre à jour le champ `exchange_rate` pour l'objet `Currency` respectif dans la table `ps_currency`.
            7.  Afficher un simple message de succès ou d'erreur, principalement pour la journalisation des tâches cron.
    -   `controllers/front/index.php`
        -   **Nom de la classe et classe parente** : `CnbratesIndexModuleFrontController` étend `ModuleFrontController`.
        -   **Responsabilité** : Il s'agit d'un contrôleur de remplacement ou de secours. Dans de nombreux modules, un contrôleur front `index.php` sert de point d'entrée par défaut si aucune action spécifique n'est demandée. Pour ce module, sa fonction principale est probablement de rediriger vers la page d'accueil ou d'afficher un simple message, car la fonctionnalité principale est gérée par `cronjob.php`. Il ne contient pas de logique métier significative pour les mises à jour de devises.
-   **Contrôleurs d'administration Back-Office** : Aucun. La configuration du module est entièrement gérée dans `cnbrates.php` via `getContent()`.

### 4.3 Classes et modèles principaux (`classes/`)

Il n'y a pas de classes personnalisées ou de définitions `ObjectModel` dans le répertoire `classes/` pour ce module. Le module interagit directement avec les classes `Currency` et `Configuration` de PrestaShop pour la gestion des données.

### 4.4 Actifs JavaScript (`views/js/`)

Il n'y a pas de fichiers JavaScript personnalisés dans ce module. Toutes les fonctionnalités sont côté serveur PHP.

### 4.5 Feuilles de style CSS (`views/css/`)

Il n'y a pas de fichiers CSS personnalisés dans ce module. Le module n'introduit aucun élément visuel front-office ou style back-office complexe au-delà des éléments de formulaire PrestaShop standard.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** : Aucun. Le module n'affiche pas de contenu via des hooks.
-   **Modèles d'administration (`views/templates/admin/`)** :
    -   `views/admin.tpl`
        -   **Objectif** : Ce modèle est rendu par la méthode `getContent()` dans `cnbrates.php` pour afficher le formulaire de configuration du module dans le back office de PrestaShop.
        -   **Contenu** : Il contient la structure HTML pour les paramètres décrits dans la Section 4.1, y compris les champs de saisie pour la fréquence de mise à jour, la méthode de mise à jour, la sélection de devise et l'affichage de l'URL de la tâche cron. Il utilise les assistants de formulaire et le style PrestaShop standard.
-   **Modèles Front-Office (`views/templates/front/`)** : Aucun.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module ne crée **pas** de tables SQL personnalisées.
    -   Il stocke ses paramètres de configuration dans la table `ps_configuration` de PrestaShop. Les clés de configuration principales incluent :
        -   `CNBRATES_UPDATE_FREQUENCY`
        -   `CNBRATES_UPDATE_METHOD`
        -   `CNBRATES_CURRENCIES` (probablement une liste d'ID de devises séparés par des virgules)
        -   `CNBRATES_CRON_TOKEN` (un jeton unique pour la sécurité de la tâche cron)
        -   `MYPRESTA_UPDATES_CNBRATES` (pour les vérifications de mise à jour MyPresta.eu)
    -   Il met à jour la colonne `exchange_rate` dans la table `ps_currency` pour les devises sélectionnées.
-   **Table des hooks enregistrés** :
    Le module enregistre les hooks suivants, principalement pour sa propre gestion du cycle de vie et potentiellement pour les vérifications de mise à jour, plutôt que pour l'affichage de contenu :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | À chaque chargement de page dans le front office (avant la sortie HTML). | Souvent utilisé pour l'inclusion de JS/CSS, ou dans ce cas, potentiellement pour la méthode de mise à jour « Au chargement de la page » si configurée, ou pour les vérifications de mise à jour MyPresta.eu. |
| `displayRightColumn` | Rend le contenu dans la colonne de droite du front office. | Non utilisé pour l'affichage de contenu par ce module, éventuellement un enregistrement de hook hérité ou pour des vérifications internes. |
| `displayLeftColumn` | Rend le contenu dans la colonne de gauche du front office. | Non utilisé pour l'affichage de contenu par ce module, éventuellement un enregistrement de hook hérité ou pour des vérifications internes. |
| `displayFooter` | Rend le contenu dans le pied de page du front office. | Non utilisé pour l'affichage de contenu par ce module, éventuellement un enregistrement de hook hérité ou pour des vérifications internes. |
| `displayBackOfficeHeader` | À chaque chargement de page dans le back office. | Utilisé pour inclure le CSS/JS spécifique au module pour la page de configuration, ou pour afficher les notifications de mise à jour de MyPresta.eu. |
| `actionAdminCurrenciesControllerSaveAfter` | Après l'enregistrement d'une devise dans le back office. | Pourrait être utilisé pour réévaluer les paramètres de devise ou déclencher une mise à jour si le statut d'une devise change. |
| `actionAdminCurrenciesControllerDeleteAfter` | Après la suppression d'une devise dans le back office. | Pourrait être utilisé pour supprimer la devise supprimée de la liste de mise à jour du module. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et les dernières versions du module « Taux de change de la Česká národní banka (CNB) », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité ou l'intégration du module.
