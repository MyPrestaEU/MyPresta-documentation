---
title: "Banque Nationale de Slovaquie (NBS) - taux de change - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Banque Nationale de Slovaquie (NBS) - taux de change par MyPresta.eu."
sidebar:
  label: "Banque Nationale de Slovaquie (NBS) - taux de change - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module The National Bank of Slovakia (NBS) - currency rates sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/the-national-bank-of-slovakia-nbs-currency-rates.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/the-national-bank-of-slovakia-nbs-currency-rates/)
>
> ---


# Banque Nationale de Slovaquie (NBS) - taux de change

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour la récupération de données externes, et sont presque universellement disponibles sur les environnements d'hébergement modernes.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du nom du module pour accéder à ses paramètres.

#### **1. Activer / Désactiver le module**

- **Ce que fait ce paramètre :** Il s'agit d'un interrupteur PrestaShop standard pour activer ou désactiver la fonctionnalité principale du module.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Le module commencera à récupérer et à mettre à jour les taux de change selon vos paramètres.
  - *Lorsqu'il est désactivé :* Le module arrêtera toutes les opérations, et vos taux de change ne seront plus automatiquement mis à jour par les données de la NBS.
- **Valeur recommandée :** **OUI** (pour activer la fonctionnalité du module).
- **Scénario / exemple de marchand :** Si vous souhaitez temporairement arrêter les mises à jour automatiques (par exemple, pendant la maintenance ou si vous passez à la gestion manuelle des taux), vous pouvez le désactiver. Sinon, gardez-le activé pour des mises à jour continues.

#### **2. URL CRON pour les mises à jour automatiques**

- **Ce que fait ce paramètre :** Il affiche une URL unique que vous devez configurer comme une « tâche cron » sur votre serveur d'hébergement web. Une tâche cron est une tâche planifiée qui indique à votre serveur de visiter cette URL à intervalles réguliers, déclenchant le module pour récupérer et mettre à jour automatiquement les derniers taux de change de la NBS.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est correctement configuré comme une tâche cron :* Vos taux de change seront mis à jour automatiquement sans aucune intervention manuelle.
  - *Lorsqu'il n'est pas configuré comme une tâche cron :* Le module ne mettra pas à jour les taux automatiquement. Vous devrez visiter manuellement cette URL dans votre navigateur pour déclencher une mise à jour (ce qui va à l'encontre du but de l'automatisation).
- **Valeur recommandée :** Il s'agit d'une URL générée. Vous devez **copier cette URL** et la coller dans le planificateur de tâches cron de votre panneau de contrôle d'hébergement.
- **Scénario / exemple de marchand :** Vous souhaitez que vos taux de change soient mis à jour tous les jours à 3h du matin. Vous copieriez cette URL, iriez dans votre panneau d'hébergement (par exemple, cPanel, Plesk, ou demanderiez de l'aide à votre hébergeur), et créeriez une tâche cron qui exécute cette URL quotidiennement à 3h du matin.

#### **3. Ajouter une marge en pourcentage aux taux de change**

- **Ce que fait ce paramètre :** Cela vous permet d'ajouter une valeur en pourcentage en plus des taux de change officiels récupérés de la NBS. Cette marge est appliquée à toutes les devises mises à jour par le module.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur 0 (ou laissé vide) :* Vos taux de change seront exactement ceux fournis par la NBS.
  - *Lorsqu'il est défini sur une valeur positive (par exemple, 2) :* Le module augmentera le taux de change de la NBS de ce pourcentage (par exemple, si le taux est de 1 EUR = 1,10 USD, avec une marge de 2 %, il devient 1 EUR = 1,122 USD). Cela rend effectivement vos produits légèrement plus chers lorsqu'ils sont payés dans la devise non de base.
- **Valeur recommandée :** **0** (si vous voulez des taux NBS exacts) ou un petit pourcentage positif (par exemple, **1-3 %**) pour couvrir les frais de transaction ou la volatilité du marché.
- **Scénario / exemple de marchand :** Vous souhaitez tenir compte des éventuels frais bancaires lors de la conversion des paiements ou simplement avoir une petite marge sur vos ventes internationales. Le fait de le définir sur « 2 » ajoutera une marge de 2 % à tous les taux de change mis à jour.

#### **4. Mettre à jour uniquement les devises sélectionnées**

- **Ce que fait ce paramètre :** Cette option vous permet de choisir des devises spécifiques dans votre boutique PrestaShop qui doivent être mises à jour par le module NBS. Si vous avez de nombreuses devises mais que vous ne souhaitez que la NBS en gère quelques-unes, c'est utile.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il n'est pas coché :* Le module tentera de mettre à jour toutes les devises actives de votre boutique PrestaShop qui ont un taux correspondant disponible auprès de la NBS.
  - *Lorsqu'il est coché et que des devises spécifiques sont sélectionnées :* Seules les devises choisies verront leurs taux de change mis à jour par le module. Les autres devises conserveront leurs taux existants (manuels ou provenant d'autres sources).
- **Valeur recommandée :** **Cochez cette case** et sélectionnez uniquement les devises que vous gérez activement avec les données de la NBS. Cela évite les modifications involontaires d'autres devises.
- **Scénario / exemple de marchand :** Votre devise de base est l'EUR, et vous vendez également en USD et CZK. Vous souhaitez que la NBS mette à jour les taux USD et CZK, mais vous gérez manuellement les taux GBP. Vous cocherez cette case et sélectionnerez uniquement USD et CZK dans la liste.

#### **5. Liste des devises à mettre à jour**

- **Ce que fait ce paramètre :** Il s'agit d'une liste à sélection multiple qui apparaît uniquement si l'option « Mettre à jour uniquement les devises sélectionnées » est cochée. Elle affiche toutes les devises actives de votre boutique PrestaShop, vous permettant de choisir celles que le module doit mettre à jour.
- **Effet de la modification de ce paramètre :**
  - *Sélectionner des devises :* Ces devises verront leurs taux de change automatiquement mis à jour par le module NBS.
  - *Désélectionner des devises :* Ces devises seront ignorées par le module NBS et leurs taux ne seront pas modifiés.
- **Valeur recommandée :** Sélectionnez toutes les devises pour lesquelles vous souhaitez utiliser les taux de la NBS.
- **Scénario / exemple de marchand :** Suivant l'exemple précédent, vous cliqueriez sur « USD » et « CZK » dans cette liste pour vous assurer que seules celles-ci sont mises à jour.

#### **6. Bouton Enregistrer**

- **Ce que fait ce paramètre :** Applique toutes les modifications que vous avez apportées sur la page de configuration.
- **Effet de la modification de ce paramètre :** Les paramètres de votre module seront enregistrés et prendront effet immédiatement (pour les futures exécutions de tâches cron ou les mises à jour manuelles).
- **Valeur recommandée :** Cliquez toujours sur **« Enregistrer »** après avoir apporté des modifications.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer / Désactiver le module | OUI | Active/désactive la fonctionnalité du module. |
| Configuration du module | URL CRON pour les mises à jour automatiques | URL générée | Copiez et configurez comme tâche cron pour les mises à jour automatiques des taux. |
| Configuration du module | Ajouter une marge en pourcentage aux taux de change | 0 (ou 1-3 %) | Ajoute une marge en pourcentage aux taux de la NBS pour la stratégie de prix. |
| Configuration du module | Mettre à jour uniquement les devises sélectionnées | Cocher et sélectionner | Restreint les mises à jour de la NBS aux devises spécifiques choisies. |
| Configuration du module | Liste des devises à mettre à jour | Sélectionner les devises souhaitées | Choisit quelles devises actives reçoivent les mises à jour des taux de la NBS. |
| Configuration du module | Bouton Enregistrer | Cliquer après les modifications | Enregistre tous les paramètres de configuration du module. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes taux de change ne se mettent pas à jour automatiquement. Que dois-je faire ?**
R :

1. **Vérifier l'état du module :** Assurez-vous que le module est activé dans **Modules > Gestionnaire de modules**.
2. **Vérifier la tâche Cron :** Le problème le plus courant est une tâche cron mal configurée.
   - Retournez à la page de configuration du module et copiez à nouveau l'« URL CRON ».
   - Connectez-vous à votre panneau de contrôle d'hébergement (cPanel, Plesk, etc.) et naviguez vers la section « Tâches Cron » ou « Tâches planifiées ».
   - Vérifiez que l'URL est exactement celle fournie par le module et que la planification (par exemple, quotidienne, horaire) est correcte.
   - Assurez-vous que la commande utilise `wget` ou `curl` pour exécuter l'URL (par exemple, `wget -O /dev/null "VOTRE_URL_CRON_ICI"`).
   - En cas de doute, contactez le support de votre hébergeur avec l'URL CRON et demandez-leur de la configurer pour vous.
3. **Vérifier les journaux du serveur :** Votre hébergeur peut avoir des journaux d'exécution des tâches cron qui peuvent indiquer s'il y a une erreur.

**Q2 : Le module est activé, mais certaines devises ne se mettent pas à jour.**
R :

1. **Vérifiez « Mettre à jour uniquement les devises sélectionnées » :** Allez dans la configuration du module. Si « Mettre à jour uniquement les devises sélectionnées » est coché, assurez-vous que les devises spécifiques que vous attendez de mettre à jour sont sélectionnées dans la « Liste des devises à mettre à jour ».
2. **Disponibilité des données NBS :** La Banque Nationale de Slovaquie pourrait ne pas fournir de taux pour toutes les devises. Le module ne peut mettre à jour que les devises pour lesquelles la NBS publie des données. Vérifiez le site officiel de la NBS pour les paires de devises disponibles.
3. **Statut de la devise PrestaShop :** Assurez-vous que les devises en question sont actives dans votre boutique PrestaShop (**International > Devises**). Les devises inactives ne peuvent pas être mises à jour.

**Q3 : À quelle fréquence dois-je exécuter la tâche cron ?**
R : Pour la plupart des boutiques, exécuter la tâche cron une fois par jour est suffisant pour maintenir les taux à jour. Si votre entreprise nécessite des taux extrêmement en temps réel en raison de transactions internationales à volume élevé ou de marchés volatils, vous pourriez la configurer pour qu'elle s'exécute plus fréquemment (par exemple, toutes les 6 ou 12 heures), mais une exécution quotidienne est généralement adéquate.

**Q4 : J'ai ajouté une marge, mais les prix ne semblent pas la refléter.**
R :

1. **Enregistrer les paramètres :** Assurez-vous d'avoir cliqué sur le bouton « Enregistrer » après avoir défini la marge.
2. **Déclencher la mise à jour :** La marge ne s'appliquera que lors de la prochaine mise à jour des taux de change. Cela se produira lors de la prochaine exécution de votre tâche cron, ou vous pouvez déclencher manuellement une mise à jour en visitant l'URL CRON dans votre navigateur.
3. **Vider le cache :** Parfois, le cache de PrestaShop peut conserver d'anciennes valeurs. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes).

**Q5 : Ce module affectera-t-il ma devise de base ?**
R : Non, le module met à jour les taux de change *par rapport* à votre devise de base. La valeur de votre devise de base elle-même reste constante. Par exemple, si votre devise de base est l'EUR, le module mettra à jour combien de USD ou de CZK équivalent à 1 EUR.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Banque Nationale de Slovaquie (NBS) - taux de change » suit une architecture de module PrestaShop standard, tirant principalement parti d'une classe de module principale (`cronjob.php`) pour la configuration et la gestion des hooks, et d'un contrôleur frontal (`cronjob.php`) pour gérer l'exécution de la tâche cron. Il interagit avec la gestion des devises de base de PrestaShop pour mettre à jour les taux. La fonction principale du module est de récupérer des données externes (taux NBS) et de les intégrer dans le modèle d'objet `Currency` de PrestaShop.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :

  - `controllers/front/cronjob.php`
    - **Nom de la classe et classe parente :** `NbsratesCronjobModuleFrontController` étendant `ModuleFrontController`.
    - **Responsabilité :** Ce contrôleur est spécifiquement conçu pour être appelé par une tâche cron. Lorsqu'il est accédé, il initie le processus de récupération des derniers taux de change auprès de la Banque Nationale de Slovaquie et de leur mise à jour dans la base de données PrestaShop. Il ne rend aucune sortie visuelle au navigateur mais effectue un traitement en arrière-plan. Il gère la logique d'application de la marge en pourcentage configurée et de mise à jour uniquement des devises sélectionnées.
  - `controllers/front/index.php`
    - **Nom de la classe et classe parente :** Il s'agit généralement d'un fichier vide ou d'un espace réservé, souvent utilisé pour empêcher l'affichage du répertoire ou pour assurer un point d'entrée valide pour les anciennes versions de PrestaShop. Il ne contient pas de logique de module spécifique pour les taux NBS.
- **Contrôleurs d'administration Back-Office** : Aucun. Toute l'administration est gérée via la méthode `getContent()` du module principal.

### 4.3 Classes et modèles de base (`classes/`)

Le module ne définit pas de classes `ObjectModel` personnalisées. Il interagit directement avec la classe `Currency` de PrestaShop pour mettre à jour les taux de change.

### 4.4 Actifs JavaScript (`views/js/`)

Aucun. Le module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

Aucun. Le module n'inclut aucun fichier CSS personnalisé.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **Modèles d'administration (`views/templates/admin/`)** :
  - `views/templates/admin/admin.tpl`
    - **Objectif :** Ce modèle est rendu lorsque la page de configuration du module est accédée dans le Back Office de PrestaShop. Il affiche les champs de saisie pour activer/désactiver le module, l'URL CRON, le pourcentage de marge et les options de sélection de devise. Il utilise les assistants de formulaire et les éléments standard de PrestaShop.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :
  Le module ne crée pas de tables SQL personnalisées. Il stocke ses paramètres de configuration dans la table `ps_configuration` de PrestaShop.

  - `PS_NBS_RATES_ENABLED` : Stocke l'état activé/désactivé du module.
  - `PS_NBS_RATES_MARGIN` : Stocke la marge en pourcentage à appliquer.
  - `PS_NBS_RATES_SELECTED_CURRENCIES` : Stocke un tableau sérialisé d'ID de devises si « Mettre à jour uniquement les devises sélectionnées » est actif.
  - `PS_NBS_RATES_CRON_TOKEN` : Stocke un jeton unique pour l'URL cron à des fins de sécurité.
- **Table des hooks enregistrés** :
  Le module utilise principalement le hook `actionFrontControllerSetMedia` (implicitement, s'il devait charger des actifs, bien qu'il ne le fasse pas) et s'appuie sur ses méthodes `install()` et `uninstall()` pour la configuration et le nettoyage. Sa fonctionnalité principale est déclenchée par le contrôleur frontal `cronjob.php` plutôt que par un hook PrestaShop traditionnel.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `install()` | Lors de l'installation du module | Configure les valeurs de configuration par défaut dans `ps_configuration` et enregistre le module. |
| `uninstall()` | Lors de la désinstallation du module | Nettoie les valeurs de configuration de `ps_configuration`. |
| (Tâche Cron) | Requête HTTP externe vers `controllers/front/cronjob.php` | Récupère les taux NBS, applique la marge et met à jour la table `ps_currency`. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Banque Nationale de Slovaquie (NBS) - taux de change », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la configuration du module.
