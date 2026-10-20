---
title: "Sveriges Riksbank - taux de change - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Sveriges Riksbank - taux de change par MyPresta.eu."
sidebar:
  label: "Sveriges Riksbank - taux de change - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Sveriges Riksbank - currency exchange rates sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/sveriges-riksbank-currency-exchange-rates.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/sveriges-riksbank-currency-exchange-rates/)
>
> ---


# Sveriges Riksbank - taux de change

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour les appels d'API externes, ce qui est standard sur la plupart des environnements d'hébergement modernes.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » pour accéder à la page des paramètres principaux du module. C'est ici que vous configurerez la manière dont le module récupère et applique les taux de change.

#### **Paramètres généraux**

- **Activer le module :**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module sera actif, et sa tâche cron ainsi que sa logique de mise à jour des taux fonctionneront selon vos autres paramètres.
    - *Lorsqu'il est désactivé :* Le module sera inactif, et aucune mise à jour automatique des taux n'aura lieu. Vos taux de change resteront tels qu'ils ont été définis pour la dernière fois (manuellement ou par une mise à jour précédente du module).
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** Si vous êtes en train de configurer ou de dépanner, vous pourriez le désactiver temporairement. Pour un fonctionnement normal, il devrait toujours être activé.
- **URL de la tâche Cron :**

  - **Ce que fait ce paramètre :** Il affiche une URL unique que vous devez configurer comme une « tâche cron » sur votre serveur d'hébergement web. Une tâche cron est une tâche planifiée qui indique à votre serveur de visiter cette URL à intervalles réguliers (par exemple, une fois par jour). Lorsque l'URL est visitée, le module récupère et met à jour automatiquement les taux de change.
  - **Effet de la modification de ce paramètre :** Vous ne pouvez pas modifier cette URL directement. Elle est générée par le module. L'effet provient de l'*utilisation* de cette URL dans votre panneau d'hébergement.
    - *Lorsqu'elle est correctement configurée comme une tâche cron :* Vos taux de change seront automatiquement mis à jour à la fréquence spécifiée (par exemple, quotidiennement).
    - *Lorsqu'elle n'est pas configurée comme une tâche cron :* Les taux ne seront pas mis à jour automatiquement. Vous devrez visiter manuellement cette URL dans votre navigateur pour déclencher une mise à jour, ce qui va à l'encontre de l'automatisation.
  - **Valeur recommandée :** Copiez cette URL et configurez-la comme une tâche cron quotidienne sur votre serveur.
  - **Scénario / exemple de marchand :** Vous la configurerez généralement pour qu'elle s'exécute une fois toutes les 24 heures afin de garantir que vos taux sont toujours à jour. Consultez la documentation de votre hébergeur ou son support pour savoir comment configurer une tâche cron (souvent trouvée dans cPanel ou Plesk sous « Tâches Cron » ou « Tâches planifiées »).

#### **Paramètres spécifiques à la devise**

Sous les paramètres généraux, vous verrez une liste de toutes les devises actives dans votre boutique PrestaShop. Pour chaque devise, vous pouvez configurer des paramètres spécifiques :

- **Nom de la devise (par exemple, Euro, Dollar US) :**

  - **Ce que fait ce paramètre :** Identifie la devise que vous configurez.
  - **Effet de la modification de ce paramètre :** C'est juste une étiquette ; vous ne pouvez pas modifier le nom de la devise ici.
- **Majoration / Minoration (%) :**

  - **Ce que fait ce paramètre :** Cela vous permet d'appliquer un ajustement en pourcentage au taux de change récupéré auprès de la Sveriges Riksbank.
    - Une **valeur positive (majoration)** augmente le taux de change, ce qui signifie que vous obtenez plus de la devise étrangère pour votre devise de base. Ceci est utile pour couvrir les frais de transaction ou augmenter votre marge bénéficiaire.
    - Une **valeur négative (minoration)** diminue le taux de change, ce qui signifie que vous obtenez moins de la devise étrangère. Cela peut être utilisé à des fins promotionnelles ou si vous souhaitez offrir un taux légèrement meilleur aux clients.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur 0 :* Le taux de change sera exactement celui fourni par la Sveriges Riksbank.
    - *Lorsqu'il est défini sur 2 (majoration) :* Si le taux de la Riksbank est de 1 EUR = 10 SEK, avec une majoration de 2 %, votre boutique utilisera 1 EUR = 10,20 SEK. Cela signifie que lorsqu'un client paie en EUR, vous recevez effectivement plus de SEK.
    - *Lorsqu'il est défini sur -1 (minoration) :* Si le taux de la Riksbank est de 1 EUR = 10 SEK, avec une minoration de 1 %, votre boutique utilisera 1 EUR = 9,90 SEK. Cela signifie que lorsqu'un client paie en EUR, il obtient un taux légèrement meilleur.
  - **Valeur recommandée :** Dépend de votre stratégie commerciale. Une pratique courante consiste à ajouter une petite majoration (par exemple, 1 à 3 %) pour couvrir les frais de passerelle de paiement et les coûts de conversion de devises.
  - **Scénario / exemple de marchand :** Si votre processeur de paiement facture des frais de 1,5 % pour la conversion d'EUR en SEK, vous pourriez définir une majoration de 2 % pour l'EUR afin de couvrir ces frais et de conserver un petit profit.

#### **Bouton Enregistrer**

- **Ce que fait ce bouton :** Enregistre toutes les modifications que vous avez apportées sur la page de configuration.
- **Effet de cliquer sur ce bouton :** Vos nouveaux paramètres (activer/désactiver, pourcentages de majoration/minoration) seront appliqués. La prochaine fois que la tâche cron s'exécutera, ou que vous déclencherez manuellement une mise à jour, ces nouveaux paramètres seront utilisés.
- **Action recommandée :** Cliquez toujours sur « Enregistrer » après avoir effectué des modifications.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer le module | OUI | Active/désactive les mises à jour automatiques des taux du module. |
| Configuration du module | URL de la tâche Cron | (URL générée) | URL à configurer comme tâche planifiée sur votre serveur pour les mises à jour automatiques. |
| Configuration du module | Majoration / Minoration (%) (par devise) | 0 | Ajuste le taux de change récupéré d'un pourcentage pour couvrir les frais ou gérer les profits. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes taux de change ne se mettent pas à jour automatiquement. Que dois-je vérifier ?**
R1 :

- **Le module est-il activé ?** Allez dans Modules > Gestionnaire de modules > Sveriges Riksbank - taux de change et assurez-vous que « Activer le module » est réglé sur OUI.
- **La tâche cron est-elle correctement configurée ?** Vérifiez à nouveau votre panneau de contrôle d'hébergement (cPanel, Plesk, etc.) pour vous assurer que l'URL de la tâche Cron fournie dans la configuration du module est correctement saisie et planifiée pour s'exécuter. Assurez-vous que la commande est correcte (par exemple, `wget -q -O /dev/null "VOTRE_URL_CRON"` ou `curl -s "VOTRE_URL_CRON"`).
- **Y a-t-il des erreurs lors de la visite manuelle de l'URL de la tâche Cron ?** Essayez de coller l'URL de la tâche Cron dans votre navigateur. Si vous voyez un message d'erreur, cela peut indiquer un problème de serveur ou un problème de connexion du module à la Sveriges Riksbank.
- **Connectivité du serveur :** Assurez-vous que votre serveur peut établir des connexions sortantes vers des sites web externes (l'API de la Sveriges Riksbank). Parfois, les pare-feu peuvent bloquer cela. Contactez votre hébergeur si vous suspectez cela.

**Q2 : J'ai mis à jour les pourcentages de majoration, mais les prix sur ma boutique n'ont pas changé.**
R2 :

- **Avez-vous enregistré les paramètres ?** Cliquez toujours sur le bouton « Enregistrer » après avoir effectué des modifications sur la page de configuration du module.
- **La tâche cron s'est-elle exécutée depuis que vous avez enregistré ?** Les modifications ne prendront effet qu'après que le module aura effectué son prochain cycle de mise à jour. Vous pouvez soit attendre votre tâche cron planifiée, soit déclencher manuellement une mise à jour en visitant l'URL de la tâche Cron dans votre navigateur.
- **Vider le cache de PrestaShop :** Parfois, le cache de PrestaShop peut conserver d'anciennes données. Allez dans **Paramètres avancés > Performances**, et cliquez sur « Vider le cache » en haut à droite.

**Q3 : Les taux de change semblent incorrects ou ne correspondent pas à ce que j'attends de la Sveriges Riksbank.**
R3 :

- **Vérifiez vos paramètres de Majoration/Minoration :** Assurez-vous que vous n'avez pas accidentellement défini un pourcentage de majoration ou de minoration élevé qui fausse les taux.
- **Vérifiez les taux officiels de la Sveriges Riksbank :** Comparez les taux de votre boutique (après une mise à jour) avec les taux officiels publiés sur le site web de la Sveriges Riksbank pour voir s'il y a une divergence.
- **Devise de base du module :** Le module récupère les taux par rapport à la SEK. Assurez-vous que la devise par défaut de votre PrestaShop est correctement configurée si vous attendez une base différente.

**Q4 : Ce module fonctionnera-t-il avec mon thème personnalisé ?**
R4 : Oui, ce module fonctionne entièrement en arrière-plan et n'ajoute aucun élément visuel ni ne modifie aucun modèle sur le front-office. Par conséquent, il est entièrement compatible avec n'importe quel thème PrestaShop, personnalisé ou par défaut. Sa fonction est purement axée sur les données (mise à jour des taux de change).

**Q5 : Comment ajouter une nouvelle devise à ma boutique pour que ce module puisse la gérer ?**
R5 :

1. Allez dans **International > Devises** dans votre Back Office PrestaShop.
2. Cliquez sur « Ajouter une nouvelle devise » (ou l'icône plus).
3. Remplissez les détails de la nouvelle devise (code ISO, symbole, taux de change par rapport à votre devise par défaut).
4. Une fois ajoutée et activée, la nouvelle devise apparaîtra sur la page de configuration du module « Sveriges Riksbank - taux de change », vous permettant de définir sa majoration/minoration.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module « Sveriges Riksbank - taux de change ».

### 4.1 Aperçu de l'architecture

Le module suit une architecture de module PrestaShop standard, se concentrant principalement sur la configuration du back-office et l'exécution des tâches cron du front-office. Il utilise le système de configuration de PrestaShop pour le stockage des paramètres et `ModuleFrontController` pour gérer la requête de la tâche cron. La logique principale réside dans le fichier principal du module, qui gère l'installation, la désinstallation et la méthode `getContent()` pour le formulaire de configuration. La fonction principale du module est de récupérer des données externes (taux de change) et de mettre à jour les données de l'objet `Currency` de PrestaShop.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs sont conçus pour être accessibles publiquement, principalement pour la fonctionnalité de tâche cron.

- **`srrates/controllers/front/cronjob.php`**

  - **Nom de la classe et classe parente :** `SrratesCronjobModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** C'est le contrôleur crucial pour les mises à jour automatiques des devises. Lorsque cette URL est accédée (généralement par une tâche cron côté serveur), elle déclenche la logique du module pour récupérer les derniers taux de change de la Sveriges Riksbank et les mettre à jour dans la base de données PrestaShop. Il ne rend aucune sortie visuelle mais renvoie généralement un simple message de succès ou d'erreur. Il est conçu pour être léger et efficace pour les tâches planifiées.
- **`srrates/controllers/front/index.php`**

  - **Nom de la classe et classe parente :** `SrratesIndexModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur sert probablement de solution de repli ou de point d'entrée par défaut pour le routage front-office du module. Dans de nombreux modules, `index.php` dans un répertoire de contrôleur frontal est utilisé pour gérer la route de base du module si aucune action spécifique n'est demandée. Il peut rediriger ou simplement afficher une page blanche s'il n'est pas explicitement utilisé pour une fonctionnalité. Pour ce module, sa fonction principale est probablement minimale, car `cronjob.php` gère la logique principale du front-office.

#### Contrôleurs d'administration Back-Office

Le module n'utilise aucun contrôleur d'administration personnalisé. Toute la configuration est gérée via la méthode `getContent()` dans le fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne définit aucune classe personnalisée ou `ObjectModel` dans le répertoire `classes/`. Il interagit directement avec la classe `Currency` et la classe `Configuration` de PrestaShop pour gérer les paramètres et mettre à jour les taux.

### 4.4 Actifs JavaScript (`views/js/`)

Le module n'inclut aucun fichier JavaScript personnalisé. Toutes les interactions sur la page de configuration sont gérées par des éléments de formulaire PrestaShop standard et potentiellement jQuery s'il est utilisé directement dans la méthode `getContent()`.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module n'inclut aucun fichier CSS personnalisé. Le style de la page de configuration repose entièrement sur les styles par défaut du thème du Back Office de PrestaShop.

### 4.6 Structure du template Smarty (`views/templates/`)

- **`srrates/views/admin.tpl`**
  - **Portée :** Template d'administration.
  - **Objectif :** Ce template est utilisé pour rendre le formulaire de configuration du module dans le Back Office de PrestaShop. Il affiche l'interrupteur « Activer le module », l'« URL de la tâche Cron » et la liste dynamique des devises avec leurs champs de saisie « Majoration / Minoration (%) » respectifs. Il est responsable de la mise en page visuelle de la sortie de `getContent()`.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de la base de données** :
  Le module ne crée aucune table SQL personnalisée. Il stocke ses paramètres de configuration (comme `PS_SRRATES_ENABLED` et les majorations de devises individuelles) directement dans la table `ps_configuration` de PrestaShop.

  - `ps_configuration` : Stocke les paramètres du module. Les clés suivent généralement un modèle comme `PS_SRRATES_ENABLED` pour l'interrupteur principal, et potentiellement `PS_SRRATES_MARKUP_EUR` pour les majorations spécifiques aux devises.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Non explicitement utilisé par ce module pour la sortie, mais `install()` peut l'enregistrer comme pratique standard. |
| `displayRightColumn` | Dans la colonne de droite des pages du front-office. | Non explicitement utilisé par ce module pour la sortie. |
| `displayLeftColumn` | Dans la colonne de gauche des pages du front-office. | Non explicitement utilisé par ce module pour la sortie. |
| `displayFooter` | Dans la section du pied de page de chaque page du front-office. | Non explicitement utilisé par ce module pour la sortie. |
| `displayProductExtraContent` | Sur la page produit, sous le contenu principal. | Non explicitement utilisé par ce module pour la sortie. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | Non explicitement utilisé par ce module, car sa fonction est la mise à jour des taux, et non le traitement des commandes. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration est chargé, avant le rendu. | Potentiellement utilisé pour charger du CSS/JS pour la page de configuration du module, bien qu'aucun actif personnalisé ne soit présent. |
| `actionModuleInstall` | Lors de l'installation du module. | Utilisé pour effectuer la configuration initiale, créer des entrées de configuration et enregistrer des hooks. |
| `actionModuleUninstall` | Lors de la désinstallation du module. | Utilisé pour nettoyer les entrées de configuration et désenregistrer les hooks. |

La fonctionnalité principale du module (mise à jour des taux) est déclenchée par le contrôleur frontal `cronjob.php`, et non directement par un hook PrestaShop, bien que le module lui-même soit installé et géré via des hooks de module standard.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Sveriges Riksbank - taux de change », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Vous pouvez télécharger les nouvelles versions depuis l'historique de vos commandes et accéder aux ressources de support à cet endroit.
