---
title: "Taux de change NBU - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'NBU Currency Exchange & Rates' par MyPresta.eu."
sidebar:
  label: "Taux de change NBU"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module NBU Currency Exchange & Rates (National Bank of Ukraine) sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/nbu-currency-exchange-rates-national-bank-of-ukraine.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/nbu-currency-exchange-rates-national-bank-of-ukraine/)
>
> ---


# Taux de change NBU

## 1. Exigences et compatibilité
- **Versions de PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises pour récupérer les données des API externes. La plupart des environnements d'hébergement modernes répondent à ces exigences par défaut.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Après l'installation, cliquez sur "Configurer" pour accéder aux paramètres du module. C'est ici que vous définirez comment les taux de la NBU sont appliqués à votre boutique.

**Nom de l'écran :** Configuration des taux de change NBU

**Paramètres et options :**

1.  **URL de la tâche CRON :**
    -   **Ce que fait ce paramètre :** Il affiche l'URL unique que le planificateur CRON de votre serveur doit appeler périodiquement. Lorsque cette URL est accédée, le module récupère automatiquement les derniers taux de change de la NBU et les met à jour dans votre boutique PrestaShop.
    -   **Effet de la modification de ce paramètre :** Vous ne pouvez pas modifier cette URL directement. Elle est générée par le module. Si vous ne configurez pas de tâche CRON pour appeler cette URL, les taux de change ne seront pas mis à jour automatiquement, et vous devrez déclencher les mises à jour manuellement (si une telle option existe, ce qui n'est pas le cas pour la fonction principale de ce module).
    -   **Valeur recommandée :** Copiez cette URL et configurez-la dans le planificateur de tâches CRON de votre panneau de contrôle d'hébergement.
    -   **Scénario / exemple de marchand :** Vous copiez `https://votreboutique.com/module/nburates/cronjob?token=VOTRE_JETON_SÉCURISÉ` et l'ajoutez à vos tâches CRON cPanel ou Plesk pour qu'elle s'exécute une fois par jour (par exemple, à 3h du matin). Cela garantit que vos prix en UAH sont toujours à jour avant que vos clients ne commencent leurs achats.

2.  **Fréquence de la tâche CRON :**
    -   **Ce que fait ce paramètre :** Il s'agit d'une recommandation sur la fréquence à laquelle vous devriez exécuter la tâche CRON. La NBU met généralement à jour les taux une fois par jour.
    -   **Effet de la modification de ce paramètre :** C'est purement informatif. La modification de la fréquence réelle de votre tâche CRON (dans votre panneau d'hébergement) affectera la fréquence de mise à jour des taux. L'exécuter trop fréquemment (par exemple, toutes les minutes) est inutile et peut consommer des ressources serveur sans avantage, car les taux de la NBU ne changent pas si souvent. L'exécuter trop rarement (par exemple, une fois par semaine) signifie que vos taux pourraient être obsolètes.
    -   **Valeur recommandée :** Une fois par jour.
    -   **Scénario / exemple de marchand :** Vous configurez la tâche CRON de votre serveur pour qu'elle s'exécute `0 3 * * *` (tous les jours à 3h du matin) pour correspondre aux mises à jour quotidiennes de la NBU.

3.  **Devise à mettre à jour (UAH) :**
    -   **Ce que fait ce paramètre :** Ce champ vous permet de spécifier l'ID de la devise Hryvnia ukrainienne (UAH) dans votre boutique PrestaShop. Le module a besoin de savoir quelle devise cibler pour les mises à jour.
    -   **Effet de la modification de ce paramètre :** Si l'ID est incorrect ou laissé vide, le module ne pourra pas trouver et mettre à jour la devise UAH, et vos prix ne refléteront pas les taux de la NBU.
    -   **Valeur recommandée :** L'ID de votre devise UAH. Vous pouvez le trouver en naviguant vers **International > Devises** dans votre Back Office PrestaShop, en modifiant la devise UAH et en regardant l'URL (par exemple, `id_currency=3` signifie que l'ID est 3).
    -   **Scénario / exemple de marchand :** Votre devise UAH a un ID de `3`. Vous entrez `3` dans ce champ. Maintenant, lorsque la tâche CRON s'exécute, le module sait qu'il doit mettre à jour le taux de change pour la devise avec l'ID `3`.

4.  **Marge (%) :**
    -   **Ce que fait ce paramètre :** Cela vous permet d'ajouter une marge en pourcentage (majoration ou minoration) aux taux de change NBU récupérés. Une valeur positive augmente le taux (rendant les prix en UAH plus élevés), et une valeur négative le diminue (rendant les prix en UAH plus bas).
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque défini à 0 :* Le module utilise le taux NBU exact.
        -   *Lorsque défini à 2 :* Le taux de change UAH sera 2% plus élevé que le taux officiel de la NBU. Par exemple, si la NBU indique 1 EUR = 40 UAH, avec une marge de 2%, votre boutique utilisera 1 EUR = 40,8 UAH. Cela peut aider à couvrir les frais de transaction ou à fournir une légère marge bénéficiaire.
        -   *Lorsque défini à -1 :* Le taux de change UAH sera 1% plus bas que le taux officiel de la NBU. Cela pourrait être utilisé pour une tarification promotionnelle ou pour offrir une légère réduction.
    -   **Valeur recommandée :** Dépend de votre stratégie commerciale. `0` pour des taux NBU exacts, ou un petit pourcentage positif (par exemple, `1` ou `2`) pour couvrir les coûts.
    -   **Scénario / exemple de marchand :** Vous souhaitez compenser légèrement les frais de passerelle de paiement pour les transactions en UAH. Vous définissez la marge à `1.5`. Désormais, tous les prix en UAH seront calculés en utilisant le taux NBU plus 1,5% supplémentaire.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
|---|---|---|---|
| Configuration du module | URL de la tâche CRON | N/A (Générée) | L'URL pour déclencher les mises à jour quotidiennes des taux. Doit être configurée dans le CRON de l'hébergement. |
| Configuration du module | Fréquence de la tâche CRON | Une fois par jour | Recommandation informative pour la planification de la tâche CRON. |
| Configuration du module | Devise à mettre à jour (UAH) | ID de la devise UAH | Spécifie quelle devise dans PrestaShop doit être mise à jour avec les taux NBU. Essentiel pour le fonctionnement du module. |
| Configuration du module | Marge (%) | 0 | Ajoute une majoration/minoration en pourcentage au taux NBU pour une flexibilité de tarification. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes prix en UAH ne sont pas mis à jour. Que dois-je faire ?**
R1 :
*   **Vérifiez la tâche CRON :** La raison la plus courante est une tâche CRON mal configurée ou manquante. Vérifiez que l'URL de la tâche CRON de la configuration du module est correctement ajoutée à votre panneau d'hébergement et qu'elle est planifiée pour s'exécuter.
*   **Vérifiez l'ID de la devise UAH :** Assurez-vous que le paramètre "Devise à mettre à jour (UAH)" dans la configuration du module correspond à l'ID exact de votre devise UAH dans PrestaShop (**International > Devises**).
*   **Vérifiez la disponibilité de la NBU :** Occasionnellement, l'API de la NBU peut être temporairement indisponible. Attendez quelques heures et vérifiez à nouveau. Le module est conçu pour utiliser le dernier taux connu si l'API est en panne.
*   **Journaux du serveur :** Vérifiez les journaux de la tâche CRON de votre serveur (si disponibles) pour toute erreur lorsque l'URL CRON est appelée.

**Q2 : Le module est installé, mais je ne vois aucun changement visuel dans ma boutique.**
R2 : Ce module fonctionne en arrière-plan pour mettre à jour les taux de devise. Il n'ajoute pas de nouveaux blocs ou éléments visuels à votre boutique. Son effet est visible dans le calcul précis des prix des produits lorsque l'UAH est la devise sélectionnée.

**Q3 : Puis-je mettre à jour manuellement les taux si la tâche CRON échoue ?**
R3 : Le mécanisme principal du module est la tâche CRON. Bien que vous puissiez mettre à jour manuellement les taux de devise dans PrestaShop (**International > Devises**), cela annulerait les taux de la NBU. La meilleure pratique est de s'assurer que votre tâche CRON fonctionne correctement. Si vous avez besoin d'une mise à jour immédiate, vous pouvez déclencher manuellement l'URL CRON une fois en la visitant dans votre navigateur (bien que ce ne soit pas la solution à long terme prévue).

**Q4 : Que se passe-t-il les jours fériés bancaires lorsque la NBU ne publie pas de nouveaux taux ?**
R4 : Le module est conçu pour gérer cela intelligemment. Si la NBU ne publie pas de nouveaux taux un jour donné (par exemple, week-ends ou jours fériés), le module conservera généralement le dernier taux récupéré avec succès. Cela garantit que vos prix en UAH restent stables et cohérents.

**Q5 : Comment vider le cache Smarty si j'apporte des modifications et que je ne les vois pas ?**
R5 : Bien que les modifications de ce module soient principalement basées sur les données (taux de devise) et moins sur les modèles visuels, vider le cache peut parfois aider. Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop. Définissez "Compilation des modèles" sur "Recompiler les modèles si les fichiers ont été mis à jour" ou "Forcer la compilation" et cliquez sur "Vider le cache". N'oubliez pas de revenir à "Ne jamais recompiler les fichiers de modèles" pour les performances en production après le dépannage.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)
Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters.

### 4.1 Vue d'ensemble de l'architecture
Le module `NBU Currency Exchange & Rates` est un module PrestaShop léger conçu pour intégrer les taux de change externes de l'API de la Banque Nationale d'Ukraine (NBU). Il suit un modèle simple de type MVC au sein de la structure du module PrestaShop. La logique principale réside dans le fichier principal du module (`cronjob.php`), qui gère la configuration, l'installation et l'exécution de la tâche CRON principale. Il utilise la classe `Configuration` de PrestaShop pour stocker les paramètres et l'ObjectModel `Currency` pour mettre à jour les taux. La fonctionnalité principale du module est exposée via un contrôleur frontal, spécifiquement conçu pour être appelé par une tâche CRON côté serveur.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :
    *   `nburates/controllers/front/cronjob.php`
        *   **Nom de la classe :** `NburatesCronjobModuleFrontController` (étend `ModuleFrontController`)
        *   **Responsabilité :** C'est le point d'accès critique pour la tâche CRON. Lorsqu'il est accédé, il effectue les actions suivantes :
            1.  Valide un jeton sécurisé (`token`) passé dans l'URL pour empêcher tout accès non autorisé.
            2.  Récupère les paramètres de configuration du module (ID de la devise UAH, marge).
            3.  Récupère les derniers taux de change de la NBU depuis l'API officielle de la NBU (probablement `https://bank.gov.ua/NBUStatService/v1/statdirectory/exchangenew?json`).
            4.  Analyse la réponse JSON pour extraire les taux de devise pertinents.
            5.  Applique la marge configurée aux taux récupérés.
            6.  Met à jour le taux de change pour la devise UAH spécifiée dans la table `ps_currency` en utilisant l'ObjectModel `Currency` de PrestaShop.
            7.  Gère les conditions d'erreur (par exemple, API inaccessible, réponse invalide) en les enregistrant ou en revenant aux taux précédents.
            8.  Affiche un simple message de succès ou d'erreur, adapté à la journalisation des tâches CRON.
    *   `nburates/controllers/front/index.php`
        *   **Nom de la classe :** `NburatesIndexModuleFrontController` (étend `ModuleFrontController`)
        *   **Responsabilité :** Il s'agit d'un contrôleur frontal `index.php` standard vide, souvent inclus dans les modules pour empêcher l'affichage des répertoires ou pour servir de placeholder. Il ne contient généralement pas de logique spécifique pour la fonction principale de ce module.

-   **Contrôleurs d'administration Back-Office** :
    *   Aucun. Toute la configuration est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)
-   Aucun. Le module interagit directement avec l'ObjectModel `Currency` et la classe `Configuration` de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)
-   Aucun. Le module n'utilise aucun JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)
-   Aucun. Le module n'utilise aucun CSS personnalisé. La page de configuration de l'administration s'appuie sur le style par défaut du Back Office de PrestaShop.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles d'administration (`views/templates/admin/`)** :
    *   `nburates/views/admin.tpl`
        *   **Objectif :** Ce modèle rend le formulaire de configuration du module dans le Back Office de PrestaShop.
        *   **Contenu :** Il affiche l'URL de la tâche CRON, la recommandation de fréquence CRON, les champs de saisie pour l'ID de la devise UAH et le pourcentage de marge. Il utilise généralement les assistants de formulaire et le style standard de PrestaShop.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    *   Le module ne crée aucune table de base de données personnalisée.
    *   Il interagit avec la table `ps_configuration` pour stocker ses paramètres (par exemple, `NBU_RATES_UAH_CURRENCY_ID`, `NBU_RATES_MARGIN`, `NBU_RATES_SECURE_TOKEN`).
    *   Il met à jour la table `ps_currency`, spécifiquement la colonne `conversion_rate` pour la devise UAH.

-   **Table des hooks enregistrés** :
    Le module n'enregistre aucun hook d'affichage traditionnel (`displayHeader`, `displayFooter`, etc.) qui affiche du contenu dans le front office. Son "hook" principal est l'`action` qu'il effectue lorsque son contrôleur frontal est appelé par la tâche CRON.

| Nom du hook | Moment d'exécution | Objectif technique |
|---|---|---|
| `actionModuleInstall` | Lors de l'installation du module | Crée les entrées de configuration, génère un jeton sécurisé. |
| `actionModuleUninstall` | Lors de la désinstallation du module | Nettoie les entrées de configuration. |
| (Implicite) `ModuleFrontController::initContent()` pour `NburatesCronjobModuleFrontController` | Lorsque l'URL CRON est accédée | Récupère les taux NBU, applique la marge, met à jour le taux de la devise UAH. |

## 5. Support officiel et mises à jour
Pour les mises à jour officielles, les corrections de bugs et le support développeur pour le module "NBU Currency Exchange & Rates", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe s'engage à fournir une assistance rapide et à assurer la compatibilité du module avec les dernières versions de PrestaShop.
