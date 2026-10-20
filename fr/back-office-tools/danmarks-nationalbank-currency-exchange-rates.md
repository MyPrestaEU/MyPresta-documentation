---
title: "Danmarks Nationalbank - taux de change - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Danmarks Nationalbank - taux de change par MyPresta.eu."
sidebar:
  label: "Danmarks Nationalbank - taux de change - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Danmarks Nationalbank - currency exchange rates sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/danmarks-nationalbank-currency-exchange-rates.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/danmarks-nationalbank-currency-exchange-rates/)
>
> ---


# Danmarks Nationalbank - taux de change

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour récupérer des données externes. Celles-ci sont presque toujours disponibles sur les environnements d'hébergement modernes.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du nom du module pour accéder à ses paramètres. C'est ici que vous gérerez la manière dont les taux de change sont récupérés et appliqués.

La page de configuration affichera une liste de toutes les devises actives dans votre boutique, vous permettant de gérer le taux de change et la marge bénéficiaire pour chacune.

**Pour chaque devise listée (par exemple, USD, EUR, GBP) :**

- **Taux de change actuel :**

  - **Ce que fait ce paramètre :** Ce champ affiche le taux de change actuel pour cette devise par rapport à la devise par défaut de votre boutique (par exemple, DKK si votre boutique est basée au Danemark). Cette valeur est automatiquement mise à jour par le module lorsque la tâche cron s'exécute.
  - **Effet de la modification de ce paramètre :** Vous pouvez l'ajuster manuellement si nécessaire, mais le but principal du module est d'automatiser cela. Toute modification manuelle sera écrasée par la prochaine exécution de la tâche cron.
  - **Valeur recommandée :** Laissez le module mettre à jour cela automatiquement. N'ajustez manuellement que pour des besoins temporaires et spécifiques.
  - **Scénario / exemple de marchand :** Si le module n'a pas encore été exécuté, ou si vous avez besoin d'ajuster rapidement un taux avant la prochaine mise à jour programmée, vous pouvez le modifier manuellement. Cependant, pour une précision à long terme, fiez-vous aux mises à jour automatiques.
- **Majoration / Minoration (%) :**

  - **Ce que fait ce paramètre :** Cela vous permet d'ajouter une marge bénéficiaire basée sur un pourcentage (majoration) ou une réduction (minoration) au taux de change récupéré.
    - Une valeur positive (par exemple, `+2%`) augmentera le taux de change, ce qui signifie que les clients paient légèrement plus dans cette devise, vous assurant de couvrir les frais de conversion ou de réaliser un petit profit.
    - Une valeur négative (par exemple, `-1%`) diminuera le taux de change, rendant le prix en devise étrangère légèrement inférieur.
  - **Effet de la modification de ce paramètre :** Ce pourcentage est appliqué *après* que le taux officiel est récupéré de la Danmarks Nationalbank.
    - *Si défini à `+2%` pour USD :* Si le taux officiel est 1 USD = 6,50 DKK, votre boutique utilisera 1 USD = 6,63 DKK (6,50 \* 1,02).
    - *Si défini à `-1%` pour EUR :* Si le taux officiel est 1 EUR = 7,45 DKK, votre boutique utilisera 1 EUR = 7,3755 DKK (7,45 \* 0,99).
  - **Valeur recommandée :** Commencez par `0%` et ajustez en fonction de votre modèle commercial, des frais de passerelle de paiement et des marges bénéficiaires souhaitées. De nombreux marchands ajoutent une petite majoration (par exemple, `0,5%` à `2%`) pour couvrir les coûts de transaction.
  - **Scénario / exemple de marchand :** Votre processeur de paiement facture des frais de 1,5% pour la conversion d'EUR en DKK. Vous pouvez définir une majoration de `+1,5%` pour l'EUR afin de répercuter efficacement ce coût sur le client et de maintenir votre marge bénéficiaire.

**URL de la tâche Cron :**

- **Ce que fait ce paramètre :** Affiche une URL unique que vous devez configurer comme tâche cron sur votre serveur. Lorsque cette URL est accédée, le module se connecte à la Danmarks Nationalbank, récupère les derniers taux de change, applique vos majorations/minorations définies et les met à jour dans votre boutique PrestaShop.
- **Effet de la modification de ce paramètre :** Vous ne pouvez pas modifier cette URL directement. Elle est générée par le module.
- **Valeur recommandée :** Copiez cette URL et configurez-la dans votre panneau de contrôle d'hébergement (cPanel, Plesk, etc.) ou avec un service cron.
- **Scénario / exemple de marchand :** Vous souhaitez que vos taux de change soient mis à jour quotidiennement à 3h du matin. Vous copieriez cette URL et configureriez une tâche cron sur votre serveur pour l'exécuter tous les jours à 3h du matin.

**Bouton Enregistrer :**

- **Ce que fait ce paramètre :** Applique toutes les modifications que vous avez apportées aux pourcentages de majoration/minoration.
- **Effet de la modification de ce paramètre :** Vos nouvelles marges bénéficiaires seront enregistrées et appliquées la prochaine fois que la tâche cron s'exécutera et mettra à jour les taux.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et Impact |
| --- | --- | --- | --- |
| Page de configuration du module | **Taux de change actuel** (par devise) | Mis à jour automatiquement par cron | Affiche le taux actuel ; les modifications manuelles sont temporaires. |
| Page de configuration du module | **Majoration / Minoration (%)** (par devise) | `0%` (ajuster au besoin) | Ajoute un pourcentage au taux récupéré pour gérer les marges bénéficiaires ou couvrir les frais. |
| Page de configuration du module | **URL de la tâche Cron** | URL unique (copier et configurer) | L'URL pour déclencher les mises à jour automatiques des taux de la Danmarks Nationalbank. |
| Page de configuration du module | **Bouton Enregistrer** | N/A | Enregistre vos pourcentages de majoration/minoration personnalisés. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes taux de change ne se mettent pas à jour. Que dois-je faire ?**
R :

1.  **Vérifier la tâche Cron :** La raison la plus courante est une tâche cron mal configurée ou qui ne s'exécute pas. Vérifiez auprès de votre hébergeur que l'URL de la tâche cron fournie dans la configuration du module est correctement planifiée et exécutée.
2.  **Statut du module :** Assurez-vous que le module est activé dans votre Back Office PrestaShop.
3.  **Connectivité du serveur :** Confirmez que votre serveur a un accès Internet sortant pour se connecter à l'API de la Danmarks Nationalbank.
4.  **Vider le cache :** Parfois, le cache de PrestaShop peut empêcher l'affichage immédiat des taux mis à jour. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ».

**Q : Puis-je définir des majorations différentes pour différentes devises ?**
R : Oui, absolument ! C'est l'une des fonctionnalités principales de ce module. Sur la page de configuration du module, vous trouverez un champ « Majoration / Minoration (%) » distinct pour chaque devise active dans votre boutique.

**Q : Que se passe-t-il si le service de la Danmarks Nationalbank est temporairement indisponible ?**
R : Le module tentera de récupérer les taux. S'il échoue, il conservera généralement les derniers taux mis à jour avec succès. Il est conçu pour être résilient, mais des échecs constants pourraient indiquer un problème de connectivité du serveur de votre côté ou une panne prolongée de la source.

**Q : Ce module affectera-t-il mon SEO ou les URL de mes produits ?**
R : Non, ce module gère uniquement les taux de change. Il ne modifie pas les URL des produits, les méta-descriptions ou tout autre élément lié au SEO. Son impact est purement sur l'affichage des prix.

**Q : Mon thème personnalisé ne semble pas afficher correctement les prix mis à jour.**
R : Ce module met à jour les taux de change de base de PrestaShop. Si votre thème utilise les fonctions standard de PrestaShop pour afficher les prix, il devrait refléter les changements. Sinon, il pourrait s'agir d'un problème de cache (vider le cache comme ci-dessus) ou d'un thème hautement personnalisé qui contourne le rendu standard des prix de PrestaShop. Dans de tels cas rares, vous pourriez avoir besoin d'un développeur web pour examiner la logique d'affichage des prix de votre thème.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module « Danmarks Nationalbank - taux de change ».

### 4.1 Vue d'ensemble de l'architecture

Le module suit une architecture de module PrestaShop standard, utilisant principalement une approche basée sur cron pour mettre à jour les taux de change. Il s'intègre au système de configuration de PrestaShop pour les paramètres et utilise des contrôleurs frontaux pour l'exécution du cron. La logique principale réside dans le fichier principal du module, gérant les appels API à la Danmarks Nationalbank et la mise à jour des entrées de la table `ps_currency`.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :

  - `dnbrates/controllers/front/cronjob.php`
    - **Nom de classe et classe parente** : `DnbratesCronjobModuleFrontController` étendant `ModuleFrontController`.
    - **Responsabilité** : Ce contrôleur est le point d'entrée de la tâche cron. Lorsqu'il est accédé via l'URL unique fournie dans la configuration back-office du module, il déclenche le processus de mise à jour des taux. Il est conçu pour être appelé en externe par un planificateur cron côté serveur. Il gère la logique de récupération des données de la Danmarks Nationalbank et de mise à jour de la table `ps_currency`.
  - `dnbrates/controllers/front/index.php`
    - **Nom de classe et classe parente** : `DnbratesIndexModuleFrontController` étendant `ModuleFrontController`.
    - **Responsabilité** : Il s'agit d'un contrôleur de remplacement, souvent inclus dans les modules mais non activement utilisé pour un affichage spécifique en front-office dans le contexte de ce module. Il pourrait servir de point d'entrée par défaut ou pour une expansion future.
- **Contrôleurs d'administration Back-Office** : Aucun. Toute la configuration back-office est gérée directement dans la méthode `getContent()` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)

Aucune classe personnalisée ou définition d'`ObjectModel` n'est trouvée dans le répertoire `classes/`. Le module interagit directement avec la classe `Currency` et la classe `Configuration` de PrestaShop pour gérer les taux de change et les paramètres.

### 4.4 Actifs JavaScript (`views/js/`)

Aucun fichier JavaScript personnalisé n'est trouvé dans l'archive du module.

### 4.5 Feuilles de style CSS (`views/css/`)

Aucun fichier CSS personnalisé n'est trouvé dans l'archive du module.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **Modèles d'administration (`views/templates/admin/`)** :
  - `dnbrates/views/admin.tpl`
    - **Objectif** : Ce modèle rend le formulaire de configuration du module dans le Back Office de PrestaShop. Il affiche la liste des devises, leurs taux de change actuels, les champs de saisie pour les pourcentages de majoration/minoration et l'URL de la tâche cron. Il est rendu par la méthode `getContent()` du fichier principal du module.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne crée aucune table SQL personnalisée.
  - Il interagit principalement avec la table `ps_currency` (spécifiquement la colonne `conversion_rate`) pour mettre à jour les taux de change.
  - Les paramètres spécifiques au module (comme les pourcentages de majoration/minoration pour chaque devise et l'URL cron) sont stockés dans la table `ps_configuration` en utilisant des clés généralement préfixées par `DNBRATES_`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rend le contenu dans la section `<head>` des pages du front-office. | Non directement utilisé pour la sortie de contenu, mais les modules s'enregistrent souvent ici pour le chargement d'actifs ou l'initialisation. |
| `displayLeftColumn` | Rend le contenu dans la colonne de gauche des pages du front-office. | Non directement utilisé pour la sortie de contenu par ce module. |
| `displayRightColumn` | Rend le contenu dans la colonne de droite des pages du front-office. | Non directement utilisé pour la sortie de contenu par ce module. |
| `displayFooter` | Rend le contenu dans le pied de page des pages du front-office. | Non directement utilisé pour la sortie de contenu par ce module. |
| `displayProductAdditionalInfo` | Rend le contenu sur la page produit, généralement sous les informations principales du produit. | Non directement utilisé pour la sortie de contenu par ce module. |
| `actionUpdateCurrency` | Exécuté après la mise à jour des détails d'une devise. | Le module utilise probablement ce hook ou un hook similaire en interne pour s'assurer que sa logique est appliquée lorsque les données de devise changent. |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses médias (JS/CSS). | Pourrait être utilisé pour charger des actifs spécifiques pour la page de configuration du module, bien qu'aucun fichier JS/CSS personnalisé ne soit présent. |

*Note : La fonction principale du module (mise à jour des taux) est déclenchée par le contrôleur frontal via cron, et non par un hook PrestaShop standard dans le cycle de vie de la requête.*

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Danmarks Nationalbank - taux de change », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
