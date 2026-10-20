---
title: "Taux de change de la Banca Nationala a Romaniei - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Taux de change de la Banca Nationala a Romaniei par MyPresta.eu."
sidebar:
  label: "Taux de change de la Banca Nationala a Romaniei - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Currency rates from Banca Nationala a Romaniei sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/currency-rates-from-banca-nationala-a-romaniei.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/currency-rates-from-banca-nationala-a-romaniei/)
>
> ---


# Taux de change de la Banca Nationala a Romaniei

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour récupérer des flux de données externes, ce qui est standard sur la plupart des environnements d'hébergement modernes.

## 2. Parcours complet de configuration (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du nom du module pour accéder à ses paramètres.

#### **Paramètres et Options**

1.  **Vérifier les mises à jour du module**

    -   **Ce que fait ce paramètre :** Cet interrupteur contrôle si le module vérifie périodiquement MyPresta.eu pour de nouvelles versions ou des mises à jour importantes.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé (OUI) :* Le module se connectera occasionnellement à MyPresta.eu pour voir si une version plus récente est disponible. Si une mise à jour est trouvée, une notification pourrait apparaître dans votre back office PrestaShop, vous invitant à la télécharger et à l'installer.
        -   *Lorsqu'il est désactivé (NON) :* Le module ne vérifiera pas les mises à jour automatiquement. Vous devrez vérifier manuellement votre compte MyPresta.eu pour les nouvelles versions.
    -   **Valeur recommandée :** **OUI**. Il est toujours recommandé de maintenir vos modules à jour pour bénéficier des nouvelles fonctionnalités, des corrections de bugs et des améliorations de sécurité.
    -   **Scénario / exemple pour le marchand :** Vous voulez vous assurer que votre module de taux de change exécute toujours la dernière version la plus stable sans avoir à vérifier constamment manuellement. L'activation de cette option vous avertira lorsqu'une mise à jour est prête.
2.  **Mettre à jour les taux de change**

    -   **Ce que fait ce paramètre :** C'est la fonction principale du module. Lorsque vous cliquez sur ce bouton, le module récupérera immédiatement les derniers taux de change de la Banca Naţională a României (BNR) et les appliquera aux devises configurées dans votre boutique PrestaShop.
    -   **Effet de la modification de ce paramètre :** Cliquer sur ce bouton déclenche une mise à jour immédiate de tous les taux de change dans votre boutique sur la base du flux BNR. C'est un déclencheur manuel pour le processus de mise à jour.
    -   **Valeur recommandée :** C'est un bouton d'action, pas un paramètre. Cliquez dessus chaque fois que vous avez besoin d'une mise à jour immédiate, ou après avoir configuré vos devises.
    -   **Scénario / exemple pour le marchand :** C'est le début de la journée de trading, et vous voulez vous assurer que tous vos prix reflètent les tout derniers taux de change avant que les clients ne commencent à passer des commandes. Vous cliqueriez sur ce bouton.
3.  **URL du Cronjob**

    -   **Ce que fait ce paramètre :** Ce champ affiche une URL unique que vous pouvez utiliser pour automatiser les mises à jour des taux de change. Cette URL est conçue pour être appelée par une « tâche cron » sur votre serveur web, qui est une tâche planifiée qui s'exécute automatiquement à des intervalles spécifiés (par exemple, une fois par jour, toutes les heures).
    -   **Effet de la modification de ce paramètre :** C'est un champ d'affichage uniquement. Copier et définir cette URL dans le planificateur de tâches cron de votre panneau d'hébergement garantira que vos taux de change sont mis à jour automatiquement sans que vous ayez à cliquer manuellement sur le bouton « Mettre à jour les taux de change ».
    -   **Valeur recommandée :** Copiez cette URL et configurez une tâche cron sur votre serveur pour l'exécuter au moins une fois par jour, ou plus fréquemment si votre entreprise l'exige.
    -   **Scénario / exemple pour le marchand :** Vous voulez que vos taux de change se mettent à jour automatiquement tous les matins à 6h, même lorsque vous n'êtes pas devant votre ordinateur. Vous copieriez cette URL et configureriez une tâche cron sur votre serveur d'hébergement pour l'exécuter quotidiennement à 6h.
4.  **Devise à mettre à jour**

    -   **Ce que fait ce paramètre :** Cette liste déroulante vous permet de sélectionner les devises spécifiques de votre boutique PrestaShop qui doivent être mises à jour par le flux BNR. Le flux BNR fournit principalement des taux par rapport au RON. Le module convertira ensuite ceux-ci dans la devise par défaut de votre boutique, puis dans d'autres devises sélectionnées.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'une devise spécifique est sélectionnée :* Seul le taux de change de cette devise sera mis à jour par le module.
        -   *Lorsque « Toutes les devises » est sélectionné :* Le module tentera de mettre à jour toutes les devises actives de votre boutique PrestaShop en utilisant le flux BNR.
    -   **Valeur recommandée :** **Toutes les devises**, sauf si vous avez une raison spécifique de n'en mettre à jour qu'une seule. Cela garantit que tous vos prix internationaux sont cohérents.
    -   **Scénario / exemple pour le marchand :** Votre boutique accepte l'EUR, l'USD et le GBP. Vous voulez que toutes ces devises soient mises à jour quotidiennement sur la base de la conversion du flux BNR en RON, puis dans la devise par défaut de votre boutique. Vous sélectionneriez « Toutes les devises ». Si vous ne vouliez mettre à jour que l'EUR pour une raison quelconque, vous sélectionneriez « EUR ».

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et Impact |
| --- | --- | --- | --- |
| Configuration du module | Vérifier les mises à jour du module | OUI | Active les vérifications automatiques des nouvelles versions du module. |
| Configuration du module | Mettre à jour les taux de change | N/A (Bouton d'action) | Déclenche manuellement une mise à jour immédiate de tous les taux de change sélectionnés depuis la BNR. |
| Configuration du module | URL du Cronjob | N/A (Affichage uniquement) | Fournit l'URL pour configurer une tâche planifiée automatisée pour les mises à jour des taux de change. |
| Configuration du module | Devise à mettre à jour | Toutes les devises | Détermine quelles devises de votre boutique recevront des mises à jour automatiques des taux depuis la BNR. |

## 3. Dépannage pour le marchand et questions fréquemment posées (FAQ)

**Q1 : Mes taux de change ne se mettent pas à jour. Que dois-je vérifier en premier ?**
R1 :

1.  **Mise à jour manuelle :** Allez sur la page de configuration du module et cliquez sur le bouton « Mettre à jour les taux de change ». Si cela fonctionne, le problème vient probablement de la configuration de votre tâche cron.
2.  **Tâche Cron :** Vérifiez à nouveau que votre tâche cron est correctement configurée sur votre serveur d'hébergement en utilisant l'« URL du Cronjob » exacte fournie par le module. Assurez-vous qu'elle est configurée pour s'exécuter à la fréquence souhaitée.
3.  **Paramètres du module :** Vérifiez que « Toutes les devises » ou les devises spécifiques que vous souhaitez mettre à jour sont sélectionnées dans la liste déroulante « Devise à mettre à jour ».
4.  **Devises PrestaShop :** Assurez-vous que les devises que vous attendez être mises à jour sont actives dans votre boutique PrestaShop (International > Devises).
5.  **Connectivité du serveur :** Assurez-vous que votre serveur peut accéder aux sites web externes (spécifiquement le flux BNR). Parfois, les règles de pare-feu ou les problèmes de réseau peuvent empêcher cela.

**Q2 : Le module indique qu'il a été mis à jour, mais les prix sur mon front office ne semblent pas corrects.**
R2 :

1.  **Vider le cache :** PrestaShop utilise la mise en cache. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). Cela garantit que votre boutique affiche les dernières données.
2.  **Cache du navigateur :** Videz le cache et les cookies de votre navigateur, ou essayez de visualiser votre boutique dans une fenêtre de navigation privée/incognito pour exclure les problèmes de cache local.
3.  **Sélection de la devise :** Assurez-vous que vous visualisez les prix dans la bonne devise sur le front office.

**Q3 : Puis-je mettre à jour les taux plus fréquemment qu'une fois par jour ?**
R3 : Oui, vous le pouvez. Lors de la configuration de votre tâche cron, vous pouvez la configurer pour qu'elle s'exécute toutes les heures, toutes les quelques heures, ou à tout intervalle pris en charge par le planificateur de tâches cron de votre hébergeur. Soyez simplement attentif à la charge potentielle du serveur si vous la configurez pour qu'elle s'exécute extrêmement fréquemment (par exemple, toutes les minutes), bien que pour les mises à jour de devises, cela soit rarement un problème.

**Q4 : Que se passe-t-il si le flux BNR est temporairement indisponible ?**
R4 : Si le flux BNR est indisponible, le module ne parviendra probablement pas à récupérer de nouveaux taux. Il ne supprimera ni ne réinitialisera vos taux existants ; ils resteront simplement inchangés jusqu'à ce que le flux redevienne disponible et qu'une mise à jour réussie ait lieu. Vous pourriez voir un message d'erreur dans les journaux de votre tâche cron si la mise à jour échoue.

**Q5 : La devise par défaut de ma boutique n'est pas le RON. Ce module fonctionnera-t-il toujours ?**
R5 : Oui, absolument. Le module est conçu pour fonctionner quelle que soit la devise par défaut de votre boutique. Il récupère les taux BNR (qui sont généralement par rapport au RON) et les convertit ensuite intelligemment dans la devise par défaut de votre boutique, puis dans toutes les autres devises actives que vous avez activées pour la mise à jour.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module « Taux de change de la Banca Nationala a Romaniei » est un module PrestaShop simple, principalement axé sur une seule tâche : la récupération et la mise à jour des taux de change. Il suit une structure de module PrestaShop de base, tirant parti de la classe `Module` pour l'installation et la configuration, et de `ModuleFrontController` pour sa fonctionnalité de tâche cron. Il n'introduit pas de classes `ObjectModel` personnalisées ni de tables de base de données, s'appuyant plutôt sur la classe `Currency` et la table `Configuration` de PrestaShop pour les paramètres. La logique principale implique l'analyse d'un flux XML de la BNR et la mise à jour des taux de change existants.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs sont conçus pour être accessibles en externe, principalement pour l'automatisation des tâches cron.

-   `controllers/front/cronjob.php`
    -   **Nom de la classe et classe parente :** `BnrratesCronjobModuleFrontController` étendant `ModuleFrontController`.
    -   **Responsabilité :** C'est le point d'accès dédié pour la tâche cron de mise à jour automatique des devises. Lorsqu'il est accédé, il déclenche la logique principale du module pour récupérer les derniers taux de change de la BNR et les mettre à jour dans la base de données PrestaShop. Il renvoie généralement un simple message de succès ou d'erreur, adapté à la journalisation des tâches cron. Il ne rend aucune sortie visuelle pour un navigateur.
-   `controllers/front/index.php`
    -   **Nom de la classe et classe parente :** `BnrratesIndexModuleFrontController` étendant `ModuleFrontController`.
    -   **Responsabilité :** Ce contrôleur sert probablement de solution de repli ou de point d'entrée par défaut, bien que sa fonction principale puisse être minimale étant donné le contrôleur `cronjob.php` explicite. Dans de nombreux modules, un contrôleur frontal `index.php` pourrait rediriger ou afficher un simple message s'il est accédé directement sans paramètres spécifiques. Pour ce module, son utilisation pratique est probablement limitée, `cronjob.php` gérant l'interaction principale du front-office.

#### Contrôleurs d'administration Back-Office

Le module n'implémente aucune classe `AdminController` personnalisée. Toute la configuration du back-office est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

Le module n'introduit aucune classe personnalisée ou définition `ObjectModel` dans le répertoire `classes/`. Il interagit directement avec les classes `Currency` et `Configuration` de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

Le module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module n'inclut aucun fichier CSS personnalisé.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles d'administration (`views/templates/admin/`)** :
    -   `bnrrates/views/admin.tpl`
        -   **Objectif :** Ce modèle est responsable du rendu du formulaire de configuration du module dans le Back Office de PrestaShop. Il affiche les paramètres tels que « Vérifier les mises à jour du module », le bouton « Mettre à jour les taux de change », l'« URL du Cronjob » et la liste déroulante « Devise à mettre à jour ».
        -   **Variables :** Il recevrait généralement des variables de la méthode `getContent()` du fichier principal du module, telles que les valeurs actuelles des paramètres de configuration et l'URL de la tâche cron générée.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :

    -   Le module ne crée aucune table SQL personnalisée.
    -   Il stocke ses paramètres de configuration dans la table `ps_configuration` de PrestaShop. Les clés de configuration pertinentes sont :
        -   `BNRRATES_MYPRESTA_UPDATES` : Stocke la valeur booléenne pour la vérification des mises à jour du module.
        -   `BNRRATES_CURRENCY_TO_UPDATE` : Stocke l'ID de la devise à mettre à jour, ou une valeur spéciale (par exemple, `0` ou `all`) pour toutes les devises.
        -   `BNRRATES_LAST_UPDATE_TIME` : (Probablement) Stocke un horodatage de la dernière mise à jour réussie.
        -   `BNRRATES_CRON_TOKEN` : Stocke un jeton unique utilisé dans l'URL de la tâche cron pour la sécurité.
-   **Table des hooks enregistrés** :
    Le module utilise principalement les hooks `action` pour sa fonctionnalité principale et potentiellement les hooks `display` pour les notifications ou le contenu spécifique (bien qu'aucun hook d'affichage front-office spécifique ne soit explicitement listé dans les informations fournies, la description du module mentionne « En-tête, Colonnes, Produit ou Pied de page » comme zones potentielles, ce qui impliquerait `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons`, `displayFooter` etc. Cependant, étant donné l'objectif du module, ceux-ci seraient probablement destinés à afficher une notification ou un statut, et non à la fonctionnalité principale).

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionModuleInstall` | Lors de l'installation du module | Enregistre la configuration du module, crée les paramètres par défaut. |
| `actionModuleUninstall` | Lors de la désinstallation du module | Nettoie la configuration du module de `ps_configuration`. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration est chargé | Enregistre potentiellement le CSS/JS pour la page de configuration de l'administration (bien qu'aucun ne soit présent dans ce module). |
| `displayBackOfficeHeader` | Dans l'en-tête du Back Office | Affiche potentiellement les notifications de mise à jour ou d'autres contenus spécifiques à l'administration. |
| `displayHeader` | Dans la section `<head>` du front office | Non directement utilisé pour la fonctionnalité principale, mais pourrait être utilisé pour les balises meta ou JS/CSS si nécessaire. |
| `displayLeftColumn` | Dans la colonne de gauche du front office | Non directement utilisé pour la fonctionnalité principale, mais pourrait être utilisé pour afficher un bloc de devises. |
| `displayRightColumn` | Dans la colonne de droite du front office | Non directement utilisé pour la fonctionnalité principale, mais pourrait être utilisé pour afficher un bloc de devises. |
| `displayProductButtons` | Sur la page produit, près du bouton ajouter au panier | Non directement utilisé pour la fonctionnalité principale, mais pourrait être utilisé pour des informations liées aux devises. |
| `displayFooter` | Dans le pied de page du front office | Non directement utilisé pour la fonctionnalité principale, mais pourrait être utilisé pour des informations liées aux devises. |

La logique principale de mise à jour des devises est déclenchée en accédant au contrôleur frontal `cronjob.php`, qui n'est pas un hook PrestaShop standard mais un point d'accès externe.

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour télécharger les dernières versions du module « Taux de change de la Banca Nationala a Romaniei », veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la configuration du module.
