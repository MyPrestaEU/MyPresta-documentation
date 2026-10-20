---
title: "Taux de change et devise BdE (Banque d'Espagne) - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Taux de change et devise BdE (Banque d'Espagne)' par MyPresta.eu."
sidebar:
  label: "Taux de change et devise BdE (Banque d'Espagne) - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module BdE Exchange Rates & Currency (Bank of Spain) sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/bde-exchange-rates-currency-bank-of-spain.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/bde-exchange-rates-currency-bank-of-spain/)
>
> ---


# Taux de change et devise BdE (Banque d'Espagne)

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard comme cURL (pour la récupération de données externes), JSON (pour le traitement des données) et OpenSSL (pour les connexions sécurisées) sont généralement requises et sont standard sur la plupart des environnements d'hébergement modernes.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à la page principale des paramètres du module « Taux de change et devise BdE (Banque d'Espagne) ». C'est ici que vous contrôlez la manière dont le module récupère et applique les taux de change.

#### **Mises à jour en direct MyPresta.eu**

-   **Ce que fait ce paramètre :** Cette section vous permet de gérer la connexion du module à MyPresta.eu pour les mises à jour automatiques et le support.
-   **Effet de la modification de ce paramètre :**
    *   *Saisir votre ID de commande et votre e-mail MyPresta.eu :* Permet au module de vérifier les nouvelles versions et de recevoir les mises à jour directement de MyPresta.eu. Cela garantit que vous disposez toujours des dernières fonctionnalités et corrections de bugs.
    *   *Laisser vide :* Le module ne pourra pas vérifier les mises à jour automatiques. Vous devrez télécharger et installer manuellement les nouvelles versions depuis votre compte MyPresta.eu.
-   **Valeur recommandée :** Saisissez toujours votre ID de commande MyPresta.eu et l'adresse e-mail associée à votre achat. C'est crucial pour recevoir des mises à jour et un support en temps opportun.
-   **Scénario / exemple de marchand :** Vous avez acheté le module en utilisant `votre.email@example.com` et votre ID de commande était `MP12345`. Saisir ces détails ici signifie que vous serez averti directement dans votre back office PrestaShop lorsqu'une nouvelle version du module sera publiée, et vous pourrez la mettre à jour en un seul clic.

#### **URL de la tâche CRON**

-   **Ce que fait ce paramètre :** Il affiche une URL unique que vous pouvez utiliser pour configurer une « tâche CRON » sur votre serveur. Une tâche CRON est une tâche planifiée qui exécute automatiquement une commande ou une URL spécifique à intervalles réguliers (par exemple, une fois par jour).
-   **Effet de la modification de ce paramètre :**
    *   *Configuration d'une tâche CRON avec cette URL :* Le module récupérera automatiquement les derniers taux de change de la Banque d'Espagne à la fréquence que vous définissez (par exemple, quotidiennement). Cela garantit que vos taux de devise sont toujours à jour sans aucune intervention manuelle.
    *   *Ne pas configurer de tâche CRON :* Les taux de change ne seront pas mis à jour automatiquement. Vous devrez visiter manuellement cette URL dans votre navigateur chaque fois que vous souhaitez mettre à jour les taux, ce qui est très peu pratique et va à l'encontre de l'objectif d'automatisation.
-   **Valeur recommandée :** Copiez cette URL et configurez une tâche CRON quotidienne sur votre serveur d'hébergement. La plupart des panneaux de contrôle d'hébergement (comme cPanel, Plesk) ont une section « Tâches Cron » où vous pouvez facilement ajouter cette URL pour qu'elle s'exécute une fois toutes les 24 heures.
-   **Scénario / exemple de marchand :** Vous souhaitez que vos taux de change Euro soient mis à jour tous les matins à 3h00. Vous copiez l'URL CRON fournie, accédez à votre panneau de contrôle d'hébergement, créez une nouvelle tâche CRON, collez l'URL et la configurez pour qu'elle s'exécute quotidiennement à 3h00. À partir de ce moment, vos taux seront automatiquement mis à jour.

#### **Ajustement de la marge (%)**

-   **Ce que fait ce paramètre :** Cela vous permet d'ajouter un petit pourcentage de marge aux taux de change récupérés. Cela peut être utile pour couvrir d'éventuels frais de transaction, coûts de conversion de devises, ou simplement pour vous donner une petite marge de sécurité.
-   **Effet de la modification de ce paramètre :**
    *   *Définir un pourcentage positif (par exemple, 2 %) :* Le module augmentera le taux de change officiel de ce pourcentage. Par exemple, si le taux officiel est de 1 EUR = 1,10 USD, et que vous définissez une marge de 2 %, le module utilisera 1 EUR = 1,122 USD (1,10 \* 1,02). Cela signifie que les produits dont le prix est en EUR apparaîtront légèrement plus chers lorsqu'ils seront convertis en USD.
    *   *Définir 0 % (par défaut) :* Le module utilisera les taux de change officiels exacts sans aucun ajustement.
-   **Valeur recommandée :** 0 % à moins que vous n'ayez des raisons commerciales spécifiques (comme couvrir des frais bancaires) d'ajouter une marge. La transparence est souvent préférable pour la confiance des clients.
-   **Scénario / exemple de marchand :** Votre passerelle de paiement facture des frais de 1,5 % pour les conversions de devises internationales. Pour compenser cela, vous pourriez définir l'ajustement de la marge à 1,5 %. Cela garantit que vos prix convertis tiennent légèrement compte de ce coût.

#### **Mettre à jour les taux de devise**

-   **Ce que fait ce paramètre :** Il s'agit d'un bouton de déclenchement manuel pour récupérer et mettre à jour immédiatement tous les taux de change de la Banque d'Espagne.
-   **Effet de la modification de ce paramètre :**
    *   *Cliquer sur le bouton :* Le module se connectera instantanément à la Banque d'Espagne, récupérera les derniers taux et les mettra à jour dans votre boutique PrestaShop. C'est utile pour les tests ou pour une mise à jour immédiate en dehors de votre calendrier de tâches CRON.
-   **Valeur recommandée :** Utilisez ce bouton pour les tests de configuration initiale ou si vous avez besoin d'une mise à jour immédiate. Pour les mises à jour régulières, fiez-vous à la tâche CRON.
-   **Scénario / exemple de marchand :** Vous venez d'installer le module et souhaitez vérifier qu'il fonctionne correctement et qu'il récupère les derniers taux. Vous cliquez sur ce bouton pour voir l'effet immédiat.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | ID de commande MyPresta.eu | Votre ID de commande | Active les mises à jour automatiques du module et le support. |
| Configuration du module | E-mail MyPresta.eu | Votre e-mail | Active les mises à jour automatiques du module et le support. |
| Configuration du module | URL de la tâche CRON | (URL unique) | Configurez une tâche CRON quotidienne avec cette URL pour les mises à jour automatiques des taux. |
| Configuration du module | Ajustement de la marge (%) | 0% | Ajoute une marge en pourcentage aux taux de change (par exemple, pour les frais). |
| Configuration du module | Mettre à jour les taux de devise | Cliquer pour déclencher | Récupère et met à jour manuellement les taux de change immédiatement. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes taux de devise ne se mettent pas à jour automatiquement.**
R :

1.  **Vérifiez la configuration de votre tâche CRON :** Vérifiez à nouveau que vous avez correctement configuré la tâche CRON sur votre serveur d'hébergement en utilisant l'URL exacte fournie dans la configuration du module. Assurez-vous qu'elle est programmée pour s'exécuter au moins une fois par jour.
2.  **Vérifiez l'exécution de la tâche CRON :** Certains panneaux d'hébergement fournissent des journaux pour l'exécution des tâches CRON. Vérifiez ces journaux pour voir si la tâche CRON s'exécute réellement et s'il y a des erreurs.
3.  **Connectivité du serveur :** Assurez-vous que votre serveur a un accès sortant aux sites Web externes (spécifiquement l'API de la Banque d'Espagne). Parfois, les pare-feu peuvent bloquer cela. Contactez votre hébergeur si vous pensez que c'est le problème.
4.  **Configuration du module :** Assurez-vous que vos détails MyPresta.eu sont correctement saisis pour d'éventuels problèmes de mise à jour.

**Q : Les prix en EUR semblent légèrement décalés, même après une mise à jour.**
R :

1.  **Vérifiez l'ajustement de la marge :** Vérifiez le paramètre « Ajustement de la marge (%) » dans la configuration du module. S'il est défini sur une valeur supérieure à 0, vos prix seront ajustés de ce pourcentage. Définissez-le à 0 % si vous souhaitez des taux officiels exacts.
2.  **Arrondi PrestaShop :** PrestaShop a ses propres règles d'arrondi pour les prix. Assurez-vous que les paramètres de votre devise dans **International > Devises** sont configurés à la précision décimale souhaitée.
3.  **Cache :** Videz votre cache PrestaShop (Paramètres avancés > Performances) et le cache de votre navigateur.

**Q : Que se passe-t-il les jours fériés bancaires ou les week-ends lorsque la Banque d'Espagne ne publie pas de nouveaux taux ?**
R : Le module est conçu pour gérer cela intelligemment. Si de nouveaux taux ne sont pas disponibles pour un jour donné, il continuera à utiliser les derniers taux récupérés avec succès. Une fois que de nouveaux taux sont publiés, le module les mettra à jour lors de sa prochaine exécution programmée.

**Q : Puis-je utiliser ce module avec d'autres modules de devise ?**
R : Ce module se concentre spécifiquement sur la récupération et l'application des taux officiels de la Banque d'Espagne. Il fonctionne généralement bien avec les fonctionnalités multidevises natives de PrestaShop. Cependant, si vous avez d'autres modules qui tentent *également* de récupérer ou de remplacer les taux de change à partir de différentes sources, il pourrait y avoir des conflits. Il est préférable d'utiliser une source principale pour les mises à jour des taux de change afin d'éviter les incohérences.

**Q : Je vois une section « Mises à jour MyPresta.eu ». À quoi sert-elle ?**
R : Cette section vous permet de saisir votre ID de commande et votre e-mail MyPresta.eu. Cela permet au module de vérifier les nouvelles versions et de recevoir les mises à jour directement de MyPresta.eu, garantissant que vous disposez toujours des dernières fonctionnalités et corrections de bugs. Il est fortement recommandé de la remplir.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module `Taux de change et devise BdE` est un module PrestaShop léger principalement conçu pour s'intégrer à l'API officielle des taux de change de la Banque d'Espagne. Il suit une structure de module PrestaShop standard, exploitant la classe `Module` pour l'installation et la configuration, et `ModuleFrontController` pour la gestion des requêtes de tâches CRON. Sa fonctionnalité principale tourne autour de la récupération de données externes, de leur analyse et de la mise à jour des taux de change natifs de la `Currency` de PrestaShop.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   **`controllers/front/cronjob.php`**
    *   **Nom de la classe et classe parente :** `BderatesCronjobModuleFrontController` étendant `ModuleFrontController`.
    *   **Responsabilité :** Ce contrôleur est le point d'entrée de la tâche CRON planifiée. Lorsqu'il est accédé, il initie le processus de récupération des derniers taux de change de la Banque d'Espagne. Il gère la requête API, analyse la réponse et met à jour les taux de change pour les devises configurées dans PrestaShop. Il est conçu pour être appelé en externe par un planificateur CRON côté serveur et renvoie généralement un simple message de succès/échec.
-   **`controllers/front/index.php`**
    *   **Nom de la classe et classe parente :** `BderatesIndexModuleFrontController` étendant `ModuleFrontController`.
    *   **Responsabilité :** Il s'agit d'un contrôleur de substitution, souvent inclus dans les modules mais non activement utilisé dans la fonctionnalité principale de ce module spécifique. Il peut être présent à des fins de routage ou comme point d'entrée par défaut, mais la logique principale pour les mises à jour de taux se trouve dans `cronjob.php`.

#### Contrôleurs d'administration Back-Office

Ce module n'implémente aucun contrôleur d'administration Back-Office personnalisé. Toute la configuration est gérée via la méthode `getContent()` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée ou `ObjectModel` dans le répertoire `classes/`. Il interagit directement avec la classe `Currency` de PrestaShop pour mettre à jour les taux de change.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles d'administration (`views/templates/admin/`)

-   **`views/templates/admin/admin.tpl`**
    *   **Objectif :** Ce modèle est utilisé pour afficher le formulaire de configuration du module dans le Back Office de PrestaShop. Il affiche les champs de saisie pour les mises à jour MyPresta.eu, l'URL de la tâche CRON, l'ajustement de la marge et le bouton de mise à jour manuelle.
    *   **Contexte :** Rendu par la méthode `getContent()` du fichier de module principal `bderates.php`.
    *   **Éléments clés :** Éléments de formulaire pour les paramètres `mypresta_updates`, `update_`, `updatev_`, `currency_`.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

Ce module ne crée aucune table SQL personnalisée. Il stocke ses paramètres de configuration directement dans la table `ps_configuration` de PrestaShop en utilisant des clés telles que :

-   `BDERATES_MYPRESTA_ID`
-   `BDERATES_MYPRESTA_EMAIL`
-   `BDERATES_MARGIN`
-   `BDERATES_LAST_UPDATE`

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Non utilisé activement pour la sortie visuelle par ce module, mais souvent enregistré par les modules pour la configuration générale ou le chargement d'actifs. |
| `displayRightColumn` | Dans la colonne de droite des pages du front-office. | Non utilisé activement pour la sortie visuelle par ce module. |
| `displayLeftColumn` | Dans la colonne de gauche des pages du front-office. | Non utilisé activement pour la sortie visuelle par ce module. |
| `displayFooter` | Dans la section du pied de page de chaque page du front-office. | Non utilisé activement pour la sortie visuelle par ce module. |
| `displayProductAdditionalInfo` | Sur la page produit, sous les informations principales du produit. | Non utilisé activement pour la sortie visuelle par ce module. |
| `actionUpdateCurrency` | Déclenché après la mise à jour du taux de change d'une devise. | Ce module *déclenche* ce hook lorsqu'il met à jour les taux de devise, permettant à d'autres modules de réagir au changement. |
| `actionCronJob` | Un hook personnalisé souvent utilisé par les modules pour enregistrer leurs tâches CRON. | Le contrôleur `cronjob.php` du module est le mécanisme principal pour les mises à jour planifiées, mais ce hook peut être enregistré pour la compatibilité ou une extension future. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et les dernières versions du module « Taux de change et devise BdE (Banque d'Espagne) », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
