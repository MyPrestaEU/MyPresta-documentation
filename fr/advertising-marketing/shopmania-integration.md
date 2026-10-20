---
title: "Intégration Shopmania - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop d'intégration Shopmania par MyPresta.eu."
sidebar:
  label: "Intégration Shopmania"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Shopmania Integration sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/shopmania-integration.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/shopmania-integration/)
>
> ---


# Intégration Shopmania

## 1. Exigences et compatibilité
- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour le fonctionnement général de PrestaShop, mais ce module a des exigences spécifiques minimales au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Après l'installation, cliquez sur "Configurer" à côté du module "Intégration Shopmania" dans votre Gestionnaire de modules. Cela vous mènera à la page de configuration principale.

Le module d'intégration Shopmania est conçu pour être très simple, nécessitant souvent une configuration minimale car il se concentre principalement sur la génération d'un flux de produits.

| Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
|---|---|---|
| **URL du flux ShopMania** | Générée automatiquement | Il s'agit du lien direct vers le flux de produits généré par votre module. Vous devrez copier cette URL et la fournir à ShopMania lors de la configuration de votre compte marchand chez eux. Cette URL est ce que ShopMania utilisera pour récupérer régulièrement vos données produit. |

**Ce que fait ce paramètre :**
Cette section affiche l'URL que ShopMania utilisera pour accéder à votre flux de données produit. Ce flux contient toutes les informations nécessaires sur vos produits (nom, description, prix, images, disponibilité, etc.) dans un format que ShopMania peut comprendre et afficher sur sa plateforme.

**Effet de la modification de ce paramètre :**
Vous ne pouvez pas modifier directement cette URL. Elle est générée automatiquement par le module en fonction du domaine de votre boutique et de la logique interne du module.

**Valeur recommandée :**
Copiez cette URL exactement telle qu'elle apparaît. Ne la modifiez pas.

**Scénario / exemple de marchand :**
Après avoir installé et configuré le module, vous vous connecterez à votre compte marchand ShopMania (ou en créerez un). ShopMania vous demandera l'"URL du flux de produits" ou l'"URL du flux de données". Vous collerez ensuite l'URL fournie sur cette page de configuration dans le champ correspondant sur le site web de ShopMania. ShopMania visitera ensuite périodiquement cette URL pour mettre à jour vos listes de produits sur sa plateforme.

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes produits n'apparaissent pas sur ShopMania. Que dois-je faire ?**
R :
1.  **Vérifiez l'URL du flux :** Assurez-vous d'avoir correctement copié et collé l'URL exacte du flux depuis la page de configuration du module dans les paramètres de votre compte marchand ShopMania.
2.  **Temps de traitement de ShopMania :** Il peut falloir un certain temps (quelques heures à quelques jours) à ShopMania pour traiter votre flux pour la première fois. Soyez patient.
3.  **Accessibilité du flux :** Essayez d'ouvrir l'URL du flux dans votre navigateur web. Se charge-t-elle ? Affiche-t-elle des données produit ? Si elle affiche une erreur ou une page blanche, il pourrait y avoir un problème côté serveur ou un problème avec le processus de génération du module. Contactez le support MyPresta.eu.
4.  **Visibilité du produit :** Assurez-vous que vos produits sont actifs, en stock et visibles dans votre boutique PrestaShop. Les produits désactivés ou en rupture de stock pourraient ne pas être inclus dans le flux.

**Q : Ce module met-il automatiquement à jour les prix et les stocks sur ShopMania ?**
R : Oui, le flux généré par ce module reflétera les prix et les niveaux de stock actuels de votre boutique PrestaShop. ShopMania récupérera périodiquement ce flux pour maintenir ses listes à jour. La fréquence des mises à jour dépend du calendrier de récupération de ShopMania, que vous pourriez être en mesure de configurer dans votre compte marchand ShopMania.

**Q : Puis-je choisir quels produits sont inclus dans le flux ?**
R : La version de base de ce module inclut généralement tous les produits actifs et visibles. Si vous avez besoin d'un filtrage avancé (par exemple, exclure des catégories ou des produits spécifiques), cela nécessiterait un développement personnalisé ou un module de gestion de flux plus avancé. Le module "Intégration Shopmania" se concentre sur une intégration simple et complète du catalogue.

**Q : Je vois une erreur lorsque j'essaie de configurer le module.**
R :
1.  **Videz le cache :** Allez dans **Paramètres avancés > Performances** dans votre back office PrestaShop et cliquez sur "Vider le cache". Parfois, d'anciens fichiers de cache peuvent interférer avec la configuration du module.
2.  **Vérifiez les journaux d'erreurs du serveur :** Si le problème persiste, vérifiez les journaux d'erreurs PHP de votre serveur. Ces journaux peuvent fournir des détails techniques spécifiques sur ce qui n'a pas fonctionné. Vous pourriez avoir besoin de contacter votre hébergeur ou un développeur pour cela.
3.  **Contactez le support :** Si vous rencontrez toujours des problèmes, rassemblez tous les messages d'erreur ou captures d'écran et contactez le support MyPresta.eu pour obtenir de l'aide.

**Q : Que se passe-t-il si mon thème personnalisé cause des problèmes d'affichage (bien que ce module n'ait pas d'affichage front-office) ?**
R : Étant donné que ce module n'a pas d'affichage front-office, il est hautement improbable qu'il cause des problèmes visuels avec votre thème personnalisé. Son fonctionnement est purement backend, générant un fichier de données.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)
Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Vue d'ensemble de l'architecture
Le module `Shopmania Integration` est un module PrestaShop simple, à fichier unique, conçu pour générer un flux de produits XML compatible avec la plateforme ShopMania. Il suit une structure de module PrestaShop standard, utilisant principalement les méthodes `install()` et `uninstall()` pour la configuration et la méthode `getContent()` pour sa configuration back-office, qui, dans ce cas, affiche simplement l'URL du flux généré. La logique principale réside dans le fichier principal du module, responsable de la génération dynamique du flux XML lorsque l'URL spécifique du flux est accédée. Il n'utilise pas de contrôleurs, de modèles ou de fichiers de template dédiés pour sa fonctionnalité principale, s'appuyant sur une sortie directe pour le flux.

### 4.2 Contrôleurs (`controllers/`)
-   **Contrôleurs Front-Office** : Aucun. Le flux de produits est généré directement par le fichier principal du module lorsque son URL spécifique est accédée, plutôt que par un `ModuleFrontController` dédié.
-   **Contrôleurs d'administration Back-Office** : Aucun. Toute la configuration (affichage de l'URL du flux) est gérée dans la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)
-   Aucune classe personnalisée ou définition d'`ObjectModel` n'est présente dans ce module. Toute la logique est contenue dans la classe `ShopmaniaIntegration` du fichier principal du module.

### 4.4 Actifs JavaScript (`views/js/`)
-   Aucun fichier JavaScript n'est inclus ou utilisé par ce module.

### 4.5 Feuilles de style CSS (`views/css/`)
-   Aucun fichier CSS n'est inclus ou utilisé par ce module.

### 4.6 Structure des templates Smarty (`views/templates/`)
-   Aucun fichier de template Smarty (`.tpl`) personnalisé n'est utilisé par ce module. La méthode `getContent()` génère directement le HTML pour la page de configuration, et le flux de produits est généré en XML brut.

### 4.7 Schéma de base de données et carte des hooks
-   **Tables de base de données** : Ce module ne crée aucune table de base de données personnalisée. Il stocke sa configuration (si nécessaire au-delà de l'URL du flux) dans la table standard `ps_configuration`, bien que pour ce module, l'URL du flux soit générée dynamiquement et non stockée comme valeur de configuration.
-   **Table des hooks enregistrés** :
    Ce module n'enregistre explicitement aucun hook dans la méthode `install()` pour l'affichage ou l'action en front-office. Sa fonction principale est de répondre à une requête d'URL directe pour le flux XML. Bien que la description de la fonctionnalité mentionne "Hooks Front-Office : En-tête, Colonnes, Produit ou Pied de page", il s'agit probablement d'une description générique pour les modules qui *pourraient* les utiliser, mais ce module spécifique n'implémente aucun composant visuel en front-office. Son intégration est purement basée sur le flux de données.

| Nom du hook | Moment d'exécution | Objectif technique |
|---|---|---|
| `displayBackOfficeHeader` | Exécuté lors du rendu de l'en-tête du Back Office. | Utilisé pour inclure des CSS/JS spécifiques au module pour la page de configuration (bien que ce module n'en utilise pas). |
| `displayHeader` | Exécuté dans la section `<head>` des pages front-office. | (Non utilisé par ce module pour la sortie visuelle, mais pourrait être utilisé pour des balises meta ou des scripts si nécessaire). |
| `displayRightColumn` | Exécuté dans la colonne de droite des pages front-office. | (Non utilisé par ce module). |
| `displayLeftColumn` | Exécuté dans la colonne de gauche des pages front-office. | (Non utilisé par ce module). |
| `displayProductAdditionalInfo` | Exécuté sur la page produit. | (Non utilisé par ce module). |
| `displayFooter` | Exécuté dans le pied de page des pages front-office. | (Non utilisé par ce module). |

La fonctionnalité principale du module (génération du flux XML) est déclenchée lorsque l'URL spécifique du flux (par exemple, `votreboutique.com/modules/shopmania-integration/shopmania-feed.php` ou similaire, selon le routage de PrestaShop) est accédée. Il ne s'agit pas d'un hook PrestaShop standard mais d'une requête HTTP directe vers un point de terminaison spécifique au module.

## 5. Support officiel et mises à jour
Pour les mises à jour officielles, le support technique et toute assistance supplémentaire concernant le module d'intégration Shopmania, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec les problèmes liés au module et assurer le bon fonctionnement de votre intégration.
