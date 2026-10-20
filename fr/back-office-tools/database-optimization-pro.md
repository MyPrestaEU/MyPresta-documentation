---
title: "Database Optimization Pro - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Database Optimization Pro par MyPresta.eu."
sidebar:
  label: "Database Optimization Pro - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Database Optimization Pro sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/database-optimization-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/database-optimization-pro/)
>
> ---


# Database Optimization Pro

## 1. Exigences et Compatibilité

- **Versions de PrestaShop prises en charge :** PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. L'accès à votre panneau de contrôle d'hébergement (cPanel, Plesk, etc.) pour configurer les tâches cron est fortement recommandé pour les capacités d'automatisation complètes du module.

## 2. Présentation complète de la configuration (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à l'écran de configuration principal de Database Optimization Pro. C'est ici que vous configurerez le nettoyage automatique et obtiendrez les informations nécessaires pour votre tâche cron.

La page de configuration est simple et fournit les outils essentiels pour gérer l'optimisation de votre base de données.

#### **URL de la tâche Cron**

- **Ce que fait ce paramètre :** C'est l'adresse web unique (URL) qui, lorsqu'elle est visitée, déclenche le processus d'optimisation de la base de données. Elle est conçue pour être appelée par un système automatisé (une tâche cron) plutôt que par un humain qui la consulte.
- **Effet de la modification de ce paramètre :** Vous ne pouvez pas modifier cette URL directement depuis la configuration du module. Elle est générée automatiquement par le module.
- **Valeur recommandée :** Copiez cette URL exactement telle qu'elle apparaît. Vous en aurez besoin pour configurer votre tâche cron sur votre serveur d'hébergement.
- **Scénario / exemple pour le marchand :** Vous copierez cette URL et la collerez dans l'interface de configuration des tâches cron fournie par votre hébergeur (par exemple, cPanel, Plesk, ou un gestionnaire de tâches cron personnalisé). Cela indique à votre serveur « toutes les X heures/jours, visitez cette URL pour nettoyer ma base de données. »

#### **Exécuter l'optimisation maintenant**

- **Ce que fait ce paramètre :** C'est un déclencheur manuel pour exécuter le processus d'optimisation de la base de données immédiatement. Il effectue les mêmes actions de nettoyage que l'URL de la tâche cron, mais à la demande.
- **Effet de la modification de ce paramètre :**
  - *Lorsque cliqué :* Le module commencera instantanément à nettoyer votre base de données. Vous verrez un message de confirmation une fois l'opération terminée.
- **Valeur recommandée :** Utilisez ce bouton pour les tests initiaux après l'installation, ou si vous avez besoin d'effectuer un nettoyage immédiat en dehors de vos tâches cron planifiées.
- **Scénario / exemple pour le marchand :** Vous venez d'installer le module et souhaitez le voir en action, ou vous avez effectué de nombreux changements dans votre boutique (par exemple, importé de nombreux produits) et souhaitez nettoyer immédiatement sans attendre la prochaine tâche cron planifiée.

#### **Configuration de la tâche Cron**

C'est la partie la plus cruciale de l'automatisation de l'optimisation de votre base de données. Une tâche cron est un planificateur de tâches basé sur le temps dans les systèmes d'exploitation de type Unix. Elle vous permet de planifier l'exécution automatique de commandes ou de scripts à une heure ou un intervalle spécifié.

**Étapes pour configurer une tâche cron (guide général - les étapes spécifiques peuvent varier selon l'hébergeur) :**

1. **Connectez-vous à votre panneau de contrôle d'hébergement :** Il s'agit généralement de cPanel, Plesk ou d'un panneau de contrôle personnalisé fourni par votre hébergeur.
2. **Recherchez « Tâches Cron » ou « Tâches planifiées » :** Cherchez une section liée aux tâches cron, souvent sous « Avancé » ou « Outils ».
3. **Ajoutez une nouvelle tâche Cron :**
   - Vous devrez généralement spécifier la fréquence (par exemple, une fois par jour, une fois par semaine). Un bon point de départ est une fois par jour ou une fois tous les quelques jours.
   - Vous devrez fournir la « Commande » ou « URL à appeler ». C'est ici que vous collez l'**URL de la tâche Cron** que vous avez copiée depuis la page de configuration du module.
   - Le format de la commande ressemble souvent à ceci :

     Terminal window

     ```
     wget -q -O /dev/null "VOTRE\_URL\_DE\_TACHE\_CRON\_ICI"
     ```

     Remplacez `"VOTRE_URL_DE_TACHE_CRON_ICI"` par l'URL exacte du module. La commande `wget` récupère l'URL, et `-q -O /dev/null` garantit qu'elle s'exécute silencieusement sans enregistrer la sortie, ce qui est idéal pour les tâches en arrière-plan.
4. **Enregistrez la tâche Cron :** Confirmez vos paramètres pour activer la tâche planifiée.

**Exemples de fréquences de tâches Cron :**

- **Une fois par jour (par exemple, 3h du matin) :**
  `0 3 * * * wget -q -O /dev/null "VOTRE_URL_DE_TACHE_CRON_ICI"`
- **Une fois par semaine (par exemple, tous les dimanches à 4h du matin) :**
  `0 4 * * 0 wget -q -O /dev/null "VOTRE_URL_DE_TACHE_CRON_ICI"`

Choisissez une heure où votre boutique a généralement peu de trafic pour minimiser tout impact potentiel (bien que généralement négligeable) sur les performances pendant le nettoyage.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et Impact |
| --- | --- | --- | --- |
| Configuration du module | URL de la tâche Cron | (Générée automatiquement) | L'URL à appeler par le système de tâche cron de votre hébergement pour déclencher l'optimisation automatique de la base de données. Copiez-la exactement. |
| Configuration du module | Exécuter l'optimisation maintenant | Cliquer pour exécuter | Déclenche manuellement un nettoyage immédiat de la base de données. Utile pour les tests ou l'optimisation à la demande. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai configuré la tâche cron, mais je ne vois aucune différence dans la vitesse de ma boutique.**
R : L'optimisation de la base de données apporte des améliorations progressives. Si votre boutique était déjà relativement rapide, le changement pourrait ne pas être spectaculaire.
- **Vérifiez votre tâche cron :** Assurez-vous qu'elle est correctement configurée sur votre hébergeur et qu'elle s'exécute. Certains hébergeurs fournissent des journaux d'exécution des tâches cron.
- **Exécutez manuellement :** Cliquez sur « Exécuter l'optimisation maintenant » dans la configuration du module. Si cela fonctionne, le problème vient probablement de la configuration de votre tâche cron.
- **Videz le cache Smarty :** Parfois, les changements visuels ou les améliorations de vitesse nécessitent de vider le cache de PrestaShop. Allez dans **Paramètres avancés > Performances**, faites défiler jusqu'à « Vider le cache » et cliquez sur « Vider le cache ».

**Q : Quelles données ce module nettoie-t-il réellement ?**
R : Le module cible divers types de données temporaires et obsolètes qui s'accumulent dans votre base de données, telles que :
- Les anciens paniers invités qui n'ont jamais été convertis en commandes.
- Les sessions expirées.
- Les anciennes entrées de journal (journaux d'accès, journaux de pages introuvables).
- Les fichiers temporaires et les données de cache stockées dans la base de données.
Il ne supprime PAS les données clients, les commandes, les produits ou toute information essentielle de la boutique.

**Q : Ce module peut-il casser ma boutique ?**
R : Ce module est conçu pour supprimer en toute sécurité uniquement les données non essentielles, temporaires ou obsolètes. Il ne touche pas aux données critiques de la boutique comme les produits, les commandes, les clients ou les catégories. Cependant, comme pour tout module qui interagit avec votre base de données, il est toujours recommandé d'avoir une sauvegarde récente avant l'installation et la configuration.

**Q : Mon hébergeur ne prend pas en charge les tâches cron, ou j'ai du mal à les configurer.**
R : Si vous ne pouvez pas configurer une tâche cron, vous pouvez toujours utiliser le module en cliquant manuellement sur le bouton « Exécuter l'optimisation maintenant » sur la page de configuration du module chaque fois que vous estimez que votre boutique a besoin d'un nettoyage (par exemple, une fois par semaine ou une fois par mois). Bien que non automatique, cela offre toujours les avantages de l'optimisation de la base de données. Contactez le support de votre hébergeur pour obtenir de l'aide sur la configuration des tâches cron ; ils sont généralement très utiles pour cette tâche courante.

**Q : Ce module affecte-t-il mon référencement ?**
R : Indirectement, oui. Des temps de chargement de page plus rapides sont un facteur de classement positif pour les moteurs de recherche comme Google. En améliorant la vitesse de votre site, ce module contribue à une meilleure expérience utilisateur, ce qui peut influencer positivement vos performances SEO.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Vue d'ensemble de l'architecture

Le module `Database Optimization Pro` est un outil d'administration léger principalement axé sur la maintenance de la base de données. Sa fonctionnalité principale repose sur l'exécution d'une série de requêtes SQL pour nettoyer les données non essentielles. L'aspect « Pro » introduit un mécanisme automatisé via un contrôleur de front-office conçu pour être déclenché par une tâche cron, permettant une optimisation planifiée et sans surveillance. Il adhère à la structure des modules de PrestaShop, utilisant un fichier de module principal pour l'installation/configuration et un contrôleur frontal dédié pour l'exécution cron.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs de Front-Office** :

  - `controllers/front/CronCleaner.php`
    - **Nom de la classe** : `DboptimizationproCronCleanerModuleFrontController`
    - **Classe parente** : `ModuleFrontController`
    - **Responsabilité** : C'est le contrôleur critique pour la fonctionnalité de tâche cron. Lorsqu'il est accédé, il exécute la logique de nettoyage de la base de données. Il est conçu pour être appelé en externe (par exemple, par `wget` via une tâche cron) et ne rend pas de page visible à l'utilisateur. Il exécute les requêtes d'optimisation de la base de données.
  - `controllers/front/index.php`
    - **Nom de la classe** : (Pas une classe, généralement un fichier vide ou une redirection)
    - **Responsabilité** : Ce fichier est souvent inclus dans les modules PrestaShop pour empêcher la liste des répertoires lors de la navigation `votreboutique.com/modules/dboptimizationpro/controllers/front/`. Il contient généralement un simple `header('Location: ../../../index.php'); exit;` ou similaire pour rediriger vers la page d'accueil, assurant la sécurité.
- **Contrôleurs d'administration du Back-Office** :

  - Aucun contrôleur d'administration dédié n'est présent. Toute la configuration du back-office est gérée directement dans la méthode `getContent()` du fichier de module principal.

### 4.3 Classes et modèles principaux (`classes/`)

Aucune classe personnalisée ou définition d'`ObjectModel` n'est présente dans le répertoire `classes/`. La logique du module est encapsulée dans le fichier de module principal (`dboptimizationpro/cronjob.php`) et le contrôleur frontal `CronCleaner`. Les interactions avec la base de données sont probablement des requêtes SQL directes exécutées via `Db::getInstance()->execute()`.

### 4.4 Actifs JavaScript (`views/js/`)

Aucun fichier JavaScript personnalisé n'est trouvé dans l'archive du module. La fonctionnalité du module est côté serveur.

### 4.5 Feuilles de style CSS (`views/css/`)

Aucun fichier CSS personnalisé n'est trouvé dans l'archive du module. La page de configuration du module utilise le style standard du back-office de PrestaShop.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Aucun fichier de modèle Smarty personnalisé (`.tpl`) n'est trouvé dans l'archive du module. Le formulaire de configuration du module est rendu directement dans la méthode `getContent()` du fichier de module principal à l'aide des formulaires d'aide de PrestaShop ou de HTML brut.

### 4.7 Schéma de la base de données et carte des Hooks

- **Tables de la base de données** :

  - Le module ne crée aucune table de base de données personnalisée.
  - Il interagit avec les tables PrestaShop existantes pour supprimer les données obsolètes (par exemple, `ps_cart`, `ps_connections`, `ps_log`, `ps_guest`, `ps_pagenotfound`).
  - Les paramètres de configuration (comme l'URL de la tâche cron ou un indicateur de la dernière exécution) sont stockés dans la table `ps_configuration`, généralement avec des clés préfixées par `DBOPTIMIZATIONPRO_`.
- **Table des Hooks enregistrés** :
  Le module n'enregistre explicitement aucun hook de front-office (par exemple, `displayHeader`, `displayRightColumn`, `displayFooter`) pour afficher du contenu. Son interaction principale avec le système de hooks de PrestaShop est pour l'installation/désinstallation du module et potentiellement pour l'intégration du menu du back-office (bien que non explicitement listé comme un contrôleur d'administration, le module lui-même apparaît dans la liste des Modules).

  La fonctionnalité principale du module est déclenchée par :

  - L'accès à la méthode `getContent()` dans le back office pour la configuration et l'exécution manuelles.
  - L'accès au contrôleur frontal `CronCleaner` via une tâche cron externe.

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour télécharger les dernières versions du module « Database Optimization Pro », veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir concernant la fonctionnalité et la configuration du module.
