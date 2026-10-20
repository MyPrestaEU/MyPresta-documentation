---
title: "Taux de change de la Banque Centrale Européenne - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Taux de change de la Banque Centrale Européenne par MyPresta.eu."
sidebar:
  label: "Taux de change de la Banque Centrale Européenne - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module European Central Bank currency rates sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/european-central-bank-currency-rates.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/european-central-bank-currency-rates/)
>
> ---


# Taux de change de la Banque Centrale Européenne

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour récupérer des données externes, et sont presque universellement disponibles sur les environnements d'hébergement modernes.

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » pour accéder aux paramètres principaux du module. C'est ici que vous contrôlez comment et quand vos taux de change sont mis à jour.

L'écran de configuration présentera généralement un formulaire avec des options pour activer/désactiver la fonctionnalité du module et potentiellement un moyen de déclencher manuellement une mise à jour ou de configurer une tâche cron.

**URL de la tâche cron :**

- **Ce que fait ce paramètre :** Il affiche une URL unique qui, lorsqu'elle est accédée, déclenche le module pour récupérer les derniers taux de change auprès de la Banque Centrale Européenne et les mettre à jour dans votre boutique PrestaShop. C'est le mécanisme central des mises à jour automatisées.
- **Effet de la modification de ce paramètre :** Il s'agit d'une URL en lecture seule générée par le module. Vous ne la modifiez pas directement.
  - *Lorsqu'elle est utilisée dans une tâche cron :* Vos taux de change seront automatiquement mis à jour à intervalles réguliers sans aucune intervention manuelle.
  - *Lorsqu'elle n'est pas utilisée :* Les taux ne seront mis à jour que si vous cliquez manuellement sur le bouton « Mettre à jour maintenant » (si disponible) ou si le mécanisme de mise à jour de devise par défaut de PrestaShop, moins fiable, est utilisé.
- **Valeur recommandée :** Copiez cette URL et configurez-la comme une tâche cron sur votre serveur d'hébergement. C'est le moyen le plus efficace et le plus fiable de maintenir vos taux à jour.
- **Scénario / exemple de marchand :** Vous souhaitez que vos taux de change soient mis à jour tous les jours à 3h du matin. Vous copiez cette URL et l'ajoutez au planificateur de tâches cron de votre panneau de contrôle d'hébergement, configuré pour s'exécuter quotidiennement à 3h du matin.

**Bouton Mettre à jour maintenant (si présent) :**

- **Ce que fait ce paramètre :** C'est un déclencheur manuel pour récupérer et mettre à jour immédiatement tous les taux de change de la BCE.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est cliqué :* Le module se connectera instantanément à la BCE, récupérera les derniers taux de change et les appliquera aux devises de votre boutique. C'est utile pour les mises à jour immédiates ou les tests.
- **Valeur recommandée :** Utilisez-le pour les tests de configuration initiale ou si vous avez besoin d'une mise à jour immédiate en dehors de vos tâches cron planifiées. Pour les mises à jour régulières, fiez-vous à la tâche cron.
- **Scénario / exemple de marchand :** Vous venez d'installer le module et souhaitez vous assurer qu'il fonctionne correctement. Vous cliquez sur « Mettre à jour maintenant », puis vérifiez vos taux de change dans PrestaShop pour confirmer qu'ils ont changé.

**Configuration générale du module (si présente, par exemple, Activer/Désactiver) :**

- **Ce que fait ce paramètre :** Il s'agit d'un interrupteur de module PrestaShop standard pour activer ou désactiver la fonctionnalité principale du module.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Le module sera actif et son URL de tâche cron fonctionnera, permettant des mises à jour automatiques des devises.
  - *Lorsqu'il est désactivé :* Le module n'effectuera aucune mise à jour et l'URL de la tâche cron ne fonctionnera pas. Vos taux de change ne seront pas mis à jour par ce module.
- **Valeur recommandée :** **OUI** (Activé) pour garantir que vos taux de change sont automatiquement mis à jour.
- **Scénario / exemple de marchand :** Vous souhaitez que le module gère vos taux de change, vous vous assurez donc qu'il est activé. Si, pour une raison quelconque, vous souhaitiez arrêter temporairement les mises à jour automatiques, vous le désactiveriez.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Ce module n'introduit aucun nouvel écran d'administration dédié ni contrôleur personnalisé au-delà de sa page de configuration principale. Toutes les interactions se déroulent directement sur le formulaire de configuration du module.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | URL de la tâche cron | Copier et configurer sur l'hébergement | Déclenche les mises à jour automatiques des taux de change de la BCE. Essentiel pour un fonctionnement mains libres. |
| Page de configuration du module | Bouton Mettre à jour maintenant | Utiliser pour les tests/mises à jour manuelles | Récupère et applique immédiatement les derniers taux de la BCE. |
| Page de configuration du module | Module Activé/Désactivé | Activé (OUI) | Active ou désactive la fonctionnalité de mise à jour des devises du module. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes taux de change ne se mettent pas à jour automatiquement. Que dois-je vérifier ?**
R :

1. **Configuration de la tâche Cron :** Le problème le plus courant est une tâche cron mal configurée. Vérifiez l'URL que vous avez utilisée dans votre panneau d'hébergement et assurez-vous que le calendrier est actif et correct.
2. **Module activé :** Assurez-vous que le module « Taux de change de la Banque Centrale Européenne » est activé dans votre Back Office PrestaShop (**Modules > Gestionnaire de modules**).
3. **Version PHP :** Assurez-vous que votre version de PHP est dans la plage de compatibilité du module (PHP 5.6 - 8.5).
4. **Journaux du serveur :** Vérifiez les journaux de tâches cron de votre serveur (si votre hébergeur les fournit) pour toute erreur lorsque la tâche cron tente de s'exécuter.
5. **Mise à jour manuelle :** Essayez de cliquer sur le bouton « Mettre à jour maintenant » sur la page de configuration du module. Si cela fonctionne, le problème vient certainement de la configuration de votre tâche cron.

**Q : Les taux ont été mis à jour, mais ils semblent incorrects ou différents de ce à quoi je m'attendais.**
R :

1. **Source BCE :** Ce module récupère les taux directement auprès de la Banque Centrale Européenne. Ce sont des taux interbancaires officiels, qui peuvent différer légèrement des taux de consommation que vous voyez sur Google ou d'autres sites financiers en raison des frais bancaires, des écarts ou des heures de mise à jour différentes.
2. **Devise de base :** Assurez-vous que la devise par défaut de votre PrestaShop est correctement configurée. Le module met à jour les taux par rapport à la devise de base.
3. **Cache :** Videz le cache de votre PrestaShop (**Paramètres avancés > Performances**) après une mise à jour pour vous assurer de voir les données les plus récentes.

**Q : Ce module fonctionne-t-il avec des thèmes personnalisés ?**
R : Oui, absolument. Ce module fonctionne en arrière-plan pour mettre à jour les données (taux de change) dans votre base de données. Il n'affiche aucun élément visuel ni ne modifie la conception de votre thème, il est donc entièrement compatible avec n'importe quel thème PrestaShop.

**Q : À quelle fréquence dois-je mettre à jour les taux de change ?**
R : Pour la plupart des boutiques e-commerce, une mise à jour quotidienne est suffisante. Si vous traitez des articles de grande valeur ou opérez sur des marchés très volatils, vous pourriez envisager une mise à jour deux fois par jour. La BCE publie généralement ses taux de référence une fois par jour, vers 16h00 HEC.

**Q : Je vois une « Erreur interne du serveur 500 » lorsque j'essaie d'accéder directement à l'URL de la tâche cron.**
R : Cela indique généralement une erreur PHP. Vérifiez les journaux d'erreurs PHP de votre serveur pour plus de détails. Les causes courantes peuvent être des permissions de fichier incorrectes, une extension PHP manquante ou un conflit avec un autre module. Contactez votre hébergeur ou un développeur avec les détails du journal d'erreurs.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module « Taux de change de la Banque Centrale Européenne » (`ecbrates`) est un module PrestaShop léger principalement conçu pour automatiser la mise à jour des taux de change de `ps_currency`. Il suit un modèle de conception simple :

- Un seul fichier de module principal (`cronjob.php`) gère l'installation, la désinstallation et la logique principale pour la récupération et la mise à jour des taux de change.
- Le module expose une méthode `getContent()` pour sa configuration Back Office, qui rend un modèle de base.
- La fonctionnalité principale est déclenchée via un appel direct au fichier `cronjob.php` du module, généralement par une tâche cron côté serveur, contournant le routage standard du contrôleur PrestaShop front/admin pour plus d'efficacité.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas les contrôleurs d'administration Front-Office ou Back-Office standard de PrestaShop. Sa logique de mise à jour principale est directement accessible via le fichier `cronjob.php`, qui agit comme un script autonome lorsqu'il est appelé via l'URL cron.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée et n'étend pas `ObjectModel`. Toute la logique est contenue dans le fichier principal `ecbrates/cronjob.php`. Il interagit directement avec la classe `Currency` et la classe `Configuration` de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **Modèles d'administration (`views/templates/admin/`)** :
  - `ecbrates/views/admin.tpl` : Ce modèle est rendu par la méthode `getContent()` du fichier de module principal. Il affiche le formulaire de configuration du module, y compris l'URL de la tâche cron et potentiellement un bouton de mise à jour manuelle. C'est un modèle simple pour les paramètres du module.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Ce module ne crée aucune table de base de données personnalisée.
  - Il interagit avec la table `ps_currency` standard de PrestaShop pour mettre à jour la colonne `conversion_rate` pour les devises actives.
  - Il stocke sa configuration (par exemple, l'état activé du module) dans la table `ps_configuration`, en utilisant des clés comme `ECBRATES_LAST_UPDATE` ou similaire, bien que les clés spécifiques ne soient pas explicitement détaillées dans les informations fournies.
- **Table des hooks enregistrés** :
  Ce module ne s'enregistre explicitement à aucun hook PrestaShop standard au sens traditionnel (par exemple, `displayHeader`, `actionValidateOrder`) pour sa fonctionnalité principale. Son mécanisme principal est un appel direct à son fichier `cronjob.php`.

  Cependant, en tant que module PrestaShop, il utilise implicitement :

  | Nom du hook | Moment d'exécution | Objectif technique |
  | --- | --- | --- |
  | `install()` | Lors de l'installation du module | Crée des entrées de configuration, potentiellement définit les taux initiaux. |
  | `uninstall()` | Lors de la désinstallation du module | Nettoie les entrées de configuration. |
  | `getContent()` | Lors de l'accès à la configuration du module dans le BO | Rend le formulaire de configuration du module. |

  La fonctionnalité principale du module (récupération et mise à jour des taux) est déclenchée par un accès HTTP direct à `cronjob.php`, et non par un hook PrestaShop.

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et une assistance supplémentaire concernant le module « Taux de change de la Banque Centrale Européenne », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Vous pouvez télécharger les dernières versions du module depuis l'historique de vos commandes. Pour le support, veuillez utiliser les canaux de support dédiés fournis sur le site web de MyPresta.eu.
