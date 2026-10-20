---
title: "Taux de change et devise NBRB (Banque Nationale de Biélorussie) - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Taux de change et devise NBRB (Banque Nationale de Biélorussie) par MyPresta.eu."
sidebar:
  label: "Taux de change et devise NBRB (Banque Nationale de Biélorussie) - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module NBRB Exchange Rates & Currency (National Bank of Belarus) sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/nbrb-exchange-rates-currency-national-bank-of-belarus.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/nbrb-exchange-rates-currency-national-bank-of-belarus/)
>
> ---


# Taux de change et devise NBRB (Banque Nationale de Biélorussie)

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises et sont présentes sur la plupart des environnements d'hébergement modernes. L'accès à la configuration d'une tâche CRON est essentiel pour les mises à jour automatiques.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Taux de change et devise NBRB » pour accéder à ses paramètres.

#### **Activer les taux de change NBRB**

- **Ce que fait ce paramètre :** Il s'agit de l'interrupteur principal pour activer ou désactiver la fonctionnalité principale du module.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'activé (OUI) :* Le module commencera à récupérer et à appliquer les taux de change NBRB pour les conversions de devise BYN dans votre boutique.
  - *Lorsqu'désactivé (NON) :* Le module cessera de récupérer les taux, et vos taux de devise BYN reviendront à ce qui était défini manuellement dans la section « Devises » de PrestaShop ou par un autre module de devise actif.
- **Valeur recommandée :** OUI
- **Scénario / exemple de marchand :** Si vous vendez principalement en Biélorussie, activez ceci pour vous assurer que tous les prix BYN sont officiels. Si vous arrêtez temporairement de vendre en Biélorussie, vous pouvez le désactiver.

#### **URL de la tâche CRON**

- **Ce que fait ce paramètre :** Il affiche l'URL unique que vous devez configurer comme tâche CRON sur votre serveur. Lorsque cette URL est accédée, le module récupérera automatiquement les derniers taux de change de la NBRB.
- **Effet de la modification de ce paramètre :** Il s'agit d'un champ d'affichage uniquement. Vous copiez cette URL et la collez dans le planificateur de tâches CRON de votre panneau de contrôle d'hébergement.
- **Valeur recommandée :** Copiez cette URL exactement comme indiqué.
- **Scénario / exemple de marchand :** Vous copieriez cette URL et configureriez une tâche CRON pour qu'elle s'exécute, par exemple, une fois toutes les 24 heures (par exemple, à 3h du matin heure locale) pour vous assurer que vos taux sont toujours à jour. Consultez la documentation ou le support de votre hébergeur pour la configuration des tâches CRON.

#### **Ajustement de la marge (%)**

- **Ce que fait ce paramètre :** Vous permet d'ajouter une marge en pourcentage (majoration ou minoration) aux taux de change NBRB récupérés. Ceci est utile pour couvrir les frais de transaction, se prémunir contre les fluctuations mineures ou appliquer une légère remise/prime.
- **Effet de la modification de ce paramètre :**
  - *Saisie d'une valeur positive (par exemple, 2) :* Le taux de conversion BYN sera augmenté de 2 %, ce qui rendra les produits légèrement plus chers en BYN.
  - *Saisie d'une valeur négative (par exemple, -1) :* Le taux de conversion BYN sera diminué de 1 %, ce qui rendra les produits légèrement moins chers en BYN.
  - *Laisser à 0 :* Le taux officiel de la NBRB sera utilisé sans aucune modification.
- **Valeur recommandée :** 0 (sauf si vous avez une raison commerciale spécifique d'ajuster les taux).
- **Scénario / exemple de marchand :** Si votre passerelle de paiement facture des frais de 1,5 % pour les transactions en BYN, vous pouvez définir ceci à « 1,5 » pour absorber ce coût dans le taux de change.

#### **Dernière mise à jour**

- **Ce que fait ce paramètre :** Ce champ affiche la date et l'heure de la dernière mise à jour réussie des taux de change par le module (manuellement ou via une tâche CRON).
- **Effet de la modification de ce paramètre :** Il s'agit d'un champ d'information en lecture seule. Il vous aide à vérifier que votre tâche CRON s'exécute correctement et que les taux sont mis à jour.
- **Valeur recommandée :** N/A (surveillez ceci pour assurer des mises à jour régulières).
- **Scénario / exemple de marchand :** Si vous remarquez que cette date est vieille de plusieurs jours, cela indique un problème avec la configuration de votre tâche CRON, et vous devriez enquêter.

#### **Bouton Mettre à jour les taux manuellement**

- **Ce que fait ce paramètre :** Ce bouton vous permet de déclencher manuellement une mise à jour immédiate des taux de change de la NBRB, en dehors du calendrier de la tâche CRON.
- **Effet de la modification de ce paramètre :** Cliquer sur ce bouton récupérera instantanément les derniers taux et les mettra à jour dans votre boutique PrestaShop. Le champ « Dernière mise à jour » reflétera la nouvelle heure.
- **Valeur recommandée :** À utiliser au besoin pour des mises à jour immédiates ou des tests.
- **Scénario / exemple de marchand :** S'il y a un événement économique important et que vous voulez vous assurer que vos taux sont absolument à jour avant votre prochaine tâche CRON planifiée, vous pouvez cliquer sur ce bouton.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer les taux de change NBRB | OUI | Active/désactive la récupération et l'application des taux du module. |
| Configuration du module | URL de la tâche CRON | N/A (copier et coller) | URL pour configurer les mises à jour automatiques des taux sur votre serveur. |
| Configuration du module | Ajustement de la marge (%) | 0 | Ajoute une majoration/minoration en pourcentage aux taux NBRB récupérés. |
| Configuration du module | Dernière mise à jour | N/A (lecture seule) | Affiche l'horodatage de la dernière mise à jour réussie des taux. |
| Configuration du module | Bouton Mettre à jour les taux manuellement | N/A (cliquer pour activer) | Déclenche une mise à jour immédiate et manuelle des taux de change. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes prix en BYN ne se mettent pas à jour, ou ils semblent incorrects.**
R :

1. **Vérifiez « Activer les taux de change NBRB » :** Assurez-vous que ce paramètre est défini sur « OUI » dans la configuration du module.
2. **Vérifiez la tâche CRON :** Assurez-vous que votre tâche CRON est correctement configurée sur votre serveur à l'aide de l'URL fournie et qu'elle s'exécute régulièrement. Vérifiez l'horodatage « Dernière mise à jour » dans le module.
3. **Mise à jour manuelle :** Essayez de cliquer sur le bouton « Mettre à jour les taux manuellement ». Si cela fonctionne, le problème vient probablement de la configuration de votre tâche CRON.
4. **Vérifiez le statut de la devise BYN :** Allez dans **International > Devises** et assurez-vous que « Rouble biélorusse (BYN) » est activé et que son code ISO est `BYN`.
5. **Videz le cache :** Parfois, le cache de PrestaShop peut conserver d'anciennes valeurs. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ».

**Q : Que se passe-t-il les jours fériés bancaires ou les week-ends lorsque la NBRB ne publie pas de nouveaux taux ?**
R : Le module est conçu pour gérer cela intelligemment. Si l'API NBRB ne fournit pas de nouveaux taux pour un jour donné (par exemple, en raison d'un week-end ou d'un jour férié), le module continuera à utiliser le dernier taux récupéré avec succès. Il ne se mettra à jour que lorsque de nouveaux taux officiels seront disponibles.

**Q : Puis-je utiliser ce module avec d'autres modules de conversion de devises ?**
R : Il n'est généralement pas recommandé d'exécuter plusieurs modules de conversion de devises simultanément, car ils peuvent entrer en conflit et entraîner des résultats imprévisibles. Ce module cible spécifiquement les taux NBRB pour le BYN. Si vous avez besoin d'autres devises, assurez-vous que ce module est la source principale pour le BYN, et que les autres modules gèrent différentes devises sans chevauchement.

**Q : J'ai défini une marge, mais les prix ne semblent pas la refléter.**
R :

1. **Enregistrez les modifications :** Assurez-vous d'avoir enregistré la configuration du module après avoir défini la marge.
2. **Mettez à jour les taux :** La marge est appliquée lorsque les taux sont récupérés. Attendez la prochaine exécution de la tâche CRON ou cliquez sur « Mettre à jour les taux manuellement ».
3. **Videz le cache :** Videz le cache de votre PrestaShop (**Paramètres avancés > Performances**).
4. **Vérifiez la devise de base :** La marge est appliquée à la conversion de la devise de base de votre boutique vers le BYN. Assurez-vous que votre devise de base est correctement définie dans PrestaShop.

**Q : Je reçois une erreur lors de l'installation ou de la configuration du module.**
R :

1. **Version de PrestaShop :** Assurez-vous d'avoir téléchargé le fichier ZIP du module correct pour votre version spécifique de PrestaShop (1.6, 1.7, 8.x, 9.x).
2. **Compatibilité PHP :** Vérifiez que la version de PHP de votre serveur se situe dans la plage prise en charge (PHP 5.6 - 8.5).
3. **Journaux du serveur :** Vérifiez les journaux d'erreurs PHP de votre serveur (souvent trouvés dans votre panneau de contrôle d'hébergement) pour des messages d'erreur plus détaillés. Cela peut aider à identifier le problème exact.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module Taux de change et devise NBRB est un module PrestaShop léger principalement axé sur une tâche unique et critique : la récupération et la mise à jour du taux de change du rouble biélorusse (BYN) à partir de l'API de la Banque Nationale de la République de Biélorussie (NBRB). Il utilise l'objet `Currency` de PrestaShop pour mettre à jour le `conversion_rate` pour le BYN. Le module utilise une tâche CRON pour les mises à jour automatisées et fournit un déclencheur manuel dans le back office. Il adhère au modèle MVC de PrestaShop pour sa configuration et l'exécution de la tâche cron du front-office.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :

  - `controllers/front/cronjob.php`
    - **Nom de la classe et classe parente :** `NbrbratesCronjobModuleFrontController` étendant `ModuleFrontController`.
    - **Responsabilité :** Ce contrôleur est conçu pour être appelé par une tâche CRON externe. Lorsqu'il est accédé, il déclenche la logique de récupération des taux du module (`$this->module->updateRates()`). Il affiche un simple message de succès/échec, ce qui le rend adapté à une exécution automatisée sans navigateur. Il ne rend pas une page complète.
  - `controllers/front/index.php`
    - **Nom de la classe et classe parente :** `NbrbratesIndexModuleFrontController` étendant `ModuleFrontController`.
    - **Responsabilité :** Il s'agit d'un contrôleur de remplacement, souvent inclus dans les modules pour empêcher la liste des répertoires ou fournir une page « vide » par défaut si le contrôleur frontal du module est accédé directement sans actions spécifiques. Dans le contexte de ce module, il sert probablement de solution de secours et n'a pas de logique métier spécifique.
- **Contrôleurs d'administration Back-Office** :

  - Ce module n'utilise pas de contrôleurs d'administration dédiés. Toute la configuration du back-office est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée dans le répertoire `classes/`. Sa logique principale pour la récupération et la mise à jour des taux est encapsulée dans le fichier principal du module `nbrbrates/cronjob.php`.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé. Le style de la page de configuration de l'administration est généralement géré par le CSS par défaut du back-office de PrestaShop.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates d'administration (`views/templates/admin/`)** :
  - `nbrbrates/views/admin.tpl`
    - **Objectif :** Ce template est rendu par la méthode `getContent()` dans le fichier principal du module (`nbrbrates/cronjob.php`). Il définit la structure et l'affichage du formulaire de configuration du module dans le Back Office de PrestaShop. Il comprend des champs de saisie pour activer/désactiver le module, l'ajustement de la marge, l'affichage de l'URL de la tâche CRON, l'heure de la dernière mise à jour et le bouton de mise à jour manuelle.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Ce module ne crée aucune table SQL personnalisée.
  - Il stocke ses paramètres de configuration dans la table `ps_configuration` de PrestaShop. Les clés de configuration principales incluent :
    - `Nbrbrates_ENABLED` : (int) 1 si activé, 0 si désactivé.
    - `Nbrbrates_MARGIN` : (float) La marge en pourcentage à appliquer.
    - `Nbrbrates_LAST_UPDATE` : (datetime) Horodatage de la dernière mise à jour réussie des taux.
- **Table des hooks enregistrés** :
  Ce module n'enregistre pas explicitement de hooks qui affichent du contenu dans le front office (comme `displayHeader`, `displayRightColumn`, `displayFooter`). Son interaction principale avec PrestaShop se fait par :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionModuleInstall` | Exécuté lors de l'installation du module. | Initialise les valeurs de configuration par défaut dans `ps_configuration`. |
| `actionModuleUninstall` | Exécuté lors de la désinstallation du module. | Nettoie les valeurs de configuration de `ps_configuration`. |
| `actionUpdateCurrency` | (Implicite) Déclenché lorsqu'une devise est mise à jour. | La méthode `updateRates()` du module modifie directement le `conversion_rate` de l'objet devise BYN, agissant ainsi sur les mises à jour de devise. |

Le contrôleur `cronjob.php` du front-office agit comme un point d'entrée externe, et non comme un hook PrestaShop traditionnel.

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour accéder aux dernières versions du module Taux de change et devise NBRB, veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité ou l'intégration du module.
