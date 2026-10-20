---
title: "Banque Centrale de Turquie (TCMB) - taux de change - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Banque Centrale de Turquie (TCMB) - taux de change par MyPresta.eu."
sidebar:
  label: "Banque Centrale de Turquie (TCMB) - taux de change - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Central Bank of Turkey (TCMB) - currency exchange rates sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/central-bank-of-turkey-tcmb-currency-exchange-rates.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/central-bank-of-turkey-tcmb-currency-exchange-rates/)
>
> ---


# Banque Centrale de Turquie (TCMB) - taux de change

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour la récupération de données externes. Votre environnement d'hébergement doit autoriser les connexions sortantes vers le site web de la TCMB.

## 2. Présentation complète de la configuration (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du nom du module pour accéder à ses paramètres.

#### Paramètres généraux

- **Activer le module**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module commencera à récupérer les taux de change et à mettre à jour les prix des devises de votre boutique selon vos autres paramètres.
    - *Lorsqu'il est désactivé :* Le module cessera toutes ses opérations. Les taux de change ne seront pas mis à jour automatiquement, et vos prix resteront statiques jusqu'à ce qu'ils soient modifiés manuellement ou que le module soit réactivé.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** Si vous configurez le module pour la première fois, activez-le pour commencer à utiliser ses fonctionnalités. Si vous devez arrêter temporairement les mises à jour automatiques (par exemple, pour la maintenance), vous pouvez le désactiver.
- **URL CRON**

  - **Ce que fait ce paramètre :** Ce champ affiche une URL unique qui, lorsqu'elle est accédée, déclenche le module pour récupérer les derniers taux de change de la TCMB et mettre à jour les prix des devises de votre boutique.
  - **Effet de la modification de ce paramètre :** Il s'agit d'un champ en lecture seule. Copier et définir cette URL dans le planificateur de tâches CRON de votre panneau d'hébergement automatisera les mises à jour des taux.
  - **Valeur recommandée :** Copiez cette URL.
  - **Scénario / exemple de marchand :** Vous copierez cette URL et la collerez dans le panneau de contrôle de votre hébergement (par exemple, cPanel, Plesk, ou une interface de tâche CRON personnalisée) pour planifier des mises à jour automatiques. Par exemple, vous pourriez le configurer pour qu'il s'exécute une fois toutes les 24 heures afin d'assurer la précision quotidienne des prix.
- **Marge (%)**

  - **Ce que fait ce paramètre :** Vous permet d'ajouter une marge en pourcentage en plus des taux de change officiels récupérés de la TCMB. Cela peut être utilisé pour couvrir les frais de transaction, les coûts de conversion de devises, ou simplement pour ajuster votre stratégie de prix.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini à 0 :* Votre boutique utilisera les taux de change officiels exacts fournis par la TCMB.
    - *Lorsqu'il est défini à une valeur positive (par exemple, 2) :* Le module augmentera le taux de change calculé de ce pourcentage. Par exemple, si le taux officiel est de 1 USD = 30 TRY, et que vous définissez une marge de 2 %, le module utilisera 1 USD = 30,6 TRY pour les conversions. Cela signifie que les produits dont le prix est en USD apparaîtront légèrement plus chers en TRY, ou vice-versa, selon votre devise de base.
  - **Valeur recommandée :** 0 (si vous voulez des taux officiels exacts) ou un petit pourcentage positif (par exemple, 1-3 %) pour couvrir les coûts.
  - **Scénario / exemple de marchand :** Si votre passerelle de paiement facture des frais de 1,5 % pour les conversions de devises, vous pourriez définir une « Marge (%) » de 1,5 pour absorber ce coût et maintenir vos marges bénéficiaires.
- **Dernière mise à jour**

  - **Ce que fait ce paramètre :** Ce champ en lecture seule affiche la date et l'heure de la dernière récupération et application réussie des mises à jour des taux de change par le module.
  - **Effet de la modification de ce paramètre :** Ce champ se met à jour automatiquement après chaque exécution réussie de la tâche CRON ou mise à jour manuelle. Il vous aide à vérifier que le module fonctionne correctement et quand les taux ont été rafraîchis pour la dernière fois.
  - **Valeur recommandée :** Surveillez cette valeur pour assurer des mises à jour régulières.
  - **Scénario / exemple de marchand :** Après avoir configuré votre tâche CRON, vous pouvez vérifier ce champ pour confirmer que les mises à jour automatisées s'exécutent comme prévu. Si la date est ancienne, cela indique un problème avec la configuration de votre tâche CRON.

#### Mise à jour manuelle

- Bouton **Mettre à jour maintenant**
  - **Ce que fait ce paramètre :** Ce bouton vous permet de déclencher manuellement le processus de mise à jour des taux de change immédiatement, sans attendre la tâche CRON.
  - **Effet de la modification de ce paramètre :** Cliquer sur ce bouton récupérera instantanément les derniers taux de la TCMB et mettra à jour les prix des devises de votre boutique. Ceci est utile pour les tests ou pour les mises à jour urgentes.
  - **Valeur recommandée :** Cliquez lorsque vous avez besoin d'une mise à jour immédiate ou pour les tests.
  - **Scénario / exemple de marchand :** Vous venez de lancer un nouveau produit et vous voulez vous assurer que son prix est basé sur les tout derniers taux de change avant que les clients ne commencent à commander. Vous pouvez cliquer sur « Mettre à jour maintenant » pour rafraîchir tous les taux instantanément.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer le module | OUI | Active/désactive la fonctionnalité principale du module. |
| Configuration du module | URL CRON | Copiez cette URL | URL à configurer pour les mises à jour automatiques des taux de change via la tâche CRON de votre hébergement. |
| Configuration du module | Marge (%) | 0-3% | Ajoute une marge en pourcentage en plus des taux de change officiels de la TCMB pour une flexibilité de prix. |
| Configuration du module | Dernière mise à jour | Surveiller | Affiche la date/heure de la dernière mise à jour réussie des taux de change. |
| Configuration du module | Bouton Mettre à jour maintenant | Cliquer si nécessaire | Déclenche manuellement une mise à jour immédiate des taux de change. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes prix ne se mettent pas à jour, même après avoir configuré le module.**
R1 : Tout d'abord, vérifiez si le paramètre « Activer le module » est défini sur OUI. Deuxièmement, vérifiez la configuration de votre tâche CRON dans votre panneau d'hébergement. Assurez-vous que l'URL CRON est correcte et que la tâche est planifiée pour s'exécuter. Vous pouvez également essayer de cliquer sur le bouton « Mettre à jour maintenant » dans la configuration du module pour voir si une mise à jour manuelle fonctionne. Si c'est le cas, le problème vient probablement de votre tâche CRON.

**Q2 : Le champ « Dernière mise à jour » affiche une date ancienne, mais ma tâche CRON est configurée.**
R2 : Cela signifie généralement que votre tâche CRON ne s'exécute pas correctement ou que le module rencontre une erreur lors de la tentative de récupération des données.
- **Vérifiez les journaux de la tâche CRON :** De nombreux hébergeurs proposent des journaux pour les exécutions des tâches CRON. Recherchez-y d'éventuelles erreurs.
- **Accès au serveur :** Assurez-vous que votre serveur a un accès Internet sortant vers `www.tcmb.gov.tr` (le site web de la Banque Centrale de Turquie). Les pare-feu ou les restrictions réseau peuvent bloquer cela.
- **Version PHP :** Confirmez que votre version de PHP est dans la plage prise en charge (PHP 5.6 - 8.5).
- **Réinstallation du module :** En dernier recours, essayez de désinstaller et de réinstaller le module (après avoir sauvegardé votre boutique) pour vous assurer que tous les fichiers sont correctement en place.

**Q3 : Puis-je mettre à jour les taux plus fréquemment qu'une fois par jour ?**
R3 : Oui, vous pouvez configurer votre tâche CRON pour qu'elle s'exécute plus fréquemment (par exemple, toutes les 6 heures, toutes les heures). Cependant, tenez compte de l'impact sur les ressources de votre serveur et de la fréquence réelle des changements de taux de la TCMB. Les mises à jour quotidiennes sont généralement suffisantes pour la plupart des boutiques e-commerce, car les taux officiels changent généralement une fois par jour ouvrable.

**Q4 : J'ai plusieurs devises. Ce module les mettra-t-il toutes à jour ?**
R4 : Oui, le module récupère les taux de change officiels de la Livre Turque (TRY) par rapport aux autres devises majeures. Il utilise ensuite ces taux pour recalculer et mettre à jour les prix de toutes les devises actives dans votre boutique PrestaShop en fonction de votre devise de base et des taux TRY récupérés.

**Q5 : Que se passe-t-il si le site web de la TCMB est en panne ou inaccessible ?**
R5 : Si le module ne peut pas se connecter au site web de la TCMB, il échouera généralement à mettre à jour les taux. Vos taux de change existants resteront inchangés jusqu'à ce qu'une connexion et une mise à jour réussies puissent être effectuées. Le champ « Dernière mise à jour » ne changera pas, indiquant un problème.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Vue d'ensemble de l'architecture

Le module `tcmbrates` est conçu comme un module PrestaShop standard, exploitant principalement la classe `Module` pour sa fonctionnalité principale. Son objectif principal est de récupérer des données externes (taux de change de la TCMB) et de mettre à jour les taux de change internes de PrestaShop. Il utilise un contrôleur frontal pour l'exécution des tâches CRON, ce qui lui permet d'être déclenché en externe sans interaction directe avec le Back Office. La configuration est gérée via la méthode `getContent()` dans le fichier principal du module, affichant un formulaire simple pour les paramètres et un déclencheur de mise à jour manuelle.

### 4.2 Contrôleurs (`controllers/`)

Le module inclut des contrôleurs frontaux pour gérer les requêtes externes, spécifiquement pour la tâche CRON.

- **Contrôleurs Front-Office :**

  - `controllers/front/cronjob.php`
    - **Nom de la classe et classe parente :** `TcmbratesCronjobModuleFrontController` étendant `ModuleFrontController`.
    - **Responsabilité :** Ce contrôleur est conçu pour être appelé par un planificateur de tâches CRON externe. Lorsqu'il est accédé, il déclenche la logique principale du module pour récupérer les derniers taux de change de la Banque Centrale de Turquie et mettre à jour les taux de devise dans la base de données PrestaShop. Il affiche généralement un message de succès ou d'échec.
  - `controllers/front/index.php`
    - **Nom de la classe et classe parente :** `TcmbratesIndexModuleFrontController` étendant `ModuleFrontController`.
    - **Responsabilité :** Il s'agit d'un contrôleur frontal de substitution ou par défaut, souvent inclus dans les modules mais pas toujours activement utilisé pour des fonctionnalités spécifiques. Dans le contexte de ce module, il sert probablement de solution de repli ou de simple point d'entrée si aucun autre contrôleur frontal spécifique n'est demandé. Sa fonction principale est généralement de rediriger ou d'afficher un message générique.
- **Contrôleurs d'administration Back-Office :** Aucun. Toute l'administration est gérée via la méthode `getContent()` du module.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne définit pas de classes personnalisées étendant `ObjectModel`. Sa logique principale réside dans le fichier principal du module (`cronjob.php`).

### 4.4 Actifs JavaScript (`views/js/`)

Aucun fichier JavaScript personnalisé n'est inclus dans ce module.

### 4.5 Feuilles de style CSS (`views/css/`)

Aucun fichier CSS personnalisé n'est inclus dans ce module.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module utilise un seul modèle Smarty pour son interface de configuration Back Office.

- **Modèles d'administration (`views/templates/admin/`) :**
  - `views/admin.tpl`
    - **Objectif :** Ce modèle est rendu par la méthode `getContent()` du fichier principal du module (`cronjob.php`). Il affiche le formulaire de configuration du module dans le Back Office de PrestaShop, y compris les champs pour activer le module, définir la marge, afficher l'URL CRON et fournir un bouton de mise à jour manuelle.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données :** Le module ne crée aucune table SQL personnalisée. Il stocke ses paramètres de configuration (par exemple, `PS_TCMBRATES_ENABLED`, `PS_TCMBRATES_MARGIN`, `PS_TCMBRATES_LAST_UPDATE`) dans la table standard `ps_configuration`. Il interagit directement avec la table `ps_currency` de PrestaShop pour mettre à jour les taux de change.
- **Table des hooks enregistrés :** Le module ne s'enregistre pas explicitement aux hooks d'affichage standard comme `displayHeader` ou `displayFooter` pour le contenu du front-office. Son interaction principale avec le système PrestaShop se fait via sa logique interne déclenchée par la tâche CRON ou la mise à jour manuelle, qui modifie ensuite les données de devise existantes.

  | Nom du hook | Moment d'exécution | Objectif technique |
  | --- | --- | --- |
  | `install()` | Installation du module | Crée des entrées de configuration dans `ps_configuration`. |
  | `uninstall()` | Désinstallation du module | Supprime les entrées de configuration de `ps_configuration`. |
  | (Aucun hook d'affichage front-office explicite) | N/A | Le module fonctionne en arrière-plan pour mettre à jour les données, pas pour afficher du contenu. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Banque Centrale de Turquie (TCMB) - taux de change », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité et l'intégration du module.
