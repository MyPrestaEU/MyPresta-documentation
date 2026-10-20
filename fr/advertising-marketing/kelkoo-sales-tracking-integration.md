---
title: "Intégration du suivi des ventes Kelkoo - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop d'intégration du suivi des ventes Kelkoo par MyPresta.eu."
sidebar:
  label: "Intégration du suivi des ventes Kelkoo"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Kelkoo sales tracking integration sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/kelkoo-sales-tracking-integration.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/kelkoo-sales-tracking-integration/)
>
> ---


# Intégration du suivi des ventes Kelkoo

## 1. Exigences et compatibilité
- **Versions de PrestaShop prises en charge** : PrestaShop 8.x, 1.7.x, 1.6.x, 1.5.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour la plupart des modules PrestaShop et sont habituellement disponibles sur tout environnement d'hébergement moderne. Aucune exigence spéciale ou inhabituelle pour ce module.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Après l'installation, cliquez sur "Configurer" à côté du module "Intégration du suivi des ventes Kelkoo". Un écran de configuration simple vous sera présenté.

#### ID de suivi Kelkoo
-   **Ce que fait ce paramètre :** C'est le paramètre le plus crucial. C'est là que vous entrez votre ID de suivi unique fourni par Kelkoo. Cet ID indique à Kelkoo à quel marchand (votre boutique) appartiennent les données de vente.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est correctement saisi :* Le module utilisera cet ID pour envoyer les données de vente à votre compte Kelkoo spécifique, permettant à Kelkoo d'attribuer les ventes à vos campagnes.
    -   *Lorsqu'il est laissé vide ou incorrect :* Le suivi des ventes ne fonctionnera pas correctement, et Kelkoo ne recevra pas de données sur les achats effectués via leur plateforme, rendant impossible la mesure de la performance de votre campagne.
-   **Valeur recommandée :** Entrez l'ID de suivi exact qui vous a été fourni par Kelkoo. Il s'agit généralement d'une chaîne numérique ou alphanumérique.
-   **Scénario / exemple de marchand :** Vous avez configuré un compte marchand avec Kelkoo. Ils vous fourniront un "ID de suivi Kelkoo" ou "ID de marchand" unique. Vous devez copier et coller cet ID précisément dans ce champ. Sans cela, l'intégration est incomplète.

#### Activer le suivi
-   **Ce que fait ce paramètre :** Il s'agit d'un simple interrupteur ON/OFF pour activer ou désactiver la fonctionnalité de suivi des ventes Kelkoo sur l'ensemble de votre boutique.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (OUI) :* Le module injectera activement les scripts de suivi nécessaires et enverra les données de vente à Kelkoo sur la page de confirmation de commande.
    -   *Lorsqu'il est désactivé (NON) :* Le module cessera toutes les activités de suivi. Aucun script ne sera injecté et aucune donnée de vente ne sera envoyée à Kelkoo.
-   **Valeur recommandée :** OUI. Vous ne devriez le désactiver que si vous souhaitez temporairement arrêter le suivi des ventes via Kelkoo ou si vous effectuez un dépannage.
-   **Scénario / exemple de marchand :** Vous avez terminé votre configuration Kelkoo et souhaitez commencer à suivre les ventes immédiatement. Réglez ce paramètre sur OUI. Si vous décidez de suspendre vos campagnes Kelkoo ou si vous devez effectuer une maintenance, vous pouvez temporairement le régler sur NON.

### 2.2 Tableau de référence rapide de la configuration
| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
|---|---|---|---|
| Configuration du module | ID de suivi Kelkoo | Votre ID Kelkoo | Identifiant unique de votre compte marchand Kelkoo. Essentiel pour l'attribution des ventes. |
| Configuration du module | Activer le suivi | OUI | Active/désactive la fonctionnalité de suivi des ventes Kelkoo. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai configuré le module, mais Kelkoo n'affiche aucune vente. Que dois-je faire ?**
R :
1.  **Vérifiez à nouveau votre ID de suivi Kelkoo :** Assurez-vous qu'il est saisi précisément tel que fourni par Kelkoo, sans espaces ou caractères supplémentaires.
2.  **Assurez-vous que "Activer le suivi" est sur OUI :** Cet interrupteur doit être actif pour que le module fonctionne.
3.  **Videz le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions plus anciennes). Parfois, le contenu mis en cache peut empêcher les nouveaux paramètres du module de prendre effet.
4.  **Effectuez un achat test :** Complétez une commande complète sur votre boutique pour déclencher le suivi.
5.  **Contactez le support Kelkoo :** Si tous les paramètres sont corrects et que vous avez vidé le cache, contactez l'équipe de support de Kelkoo. Ils peuvent souvent vérifier de leur côté si des données sont reçues ou s'il y a un problème avec la configuration de votre compte sur leur plateforme.

**Q : Ce module va-t-il ralentir mon site web ?**
R : Non, le module est très léger. Il n'injecte qu'un petit extrait JavaScript non bloquant dans l'en-tête et envoie des données sur la page de confirmation de commande. Ce processus est optimisé pour ne pas impacter la vitesse de chargement de votre boutique ou l'expérience client.

**Q : Ce module fonctionne-t-il avec les configurations multi-boutiques ?**
R : Oui, le module devrait fonctionner correctement dans un environnement multi-boutiques. Vous configurerez l'ID de suivi Kelkoo pour chaque boutique individuellement si elles ont des comptes Kelkoo distincts, ou utiliserez le même ID si vous suivez toutes les boutiques sous un seul compte Kelkoo.

**Q : J'utilise un thème personnalisé. Ce module fonctionnera-t-il toujours ?**
R : Oui, le module utilise les hooks PrestaShop standard (`displayHeader`, `displayOrderConfirmation`) qui sont presque universellement présents dans tous les thèmes bien codés. Il ne dépend pas d'éléments de thème spécifiques, il devrait donc être compatible avec les thèmes personnalisés. Si vous rencontrez des problèmes, assurez-vous que votre thème personnalisé implémente correctement ces hooks PrestaShop de base.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture
Le module "Intégration du suivi des ventes Kelkoo" est un module PrestaShop simple conçu pour intégrer le pixel de suivi des ventes de Kelkoo. Il exploite principalement le système de hooks de PrestaShop pour injecter un script de suivi global dans l'en-tête et un script de suivi des conversions sur la page de confirmation de commande. Il suit une structure de module PrestaShop de base, avec sa logique principale contenue dans le fichier de module principal et des fichiers de template pour le rendu des hooks. Il n'y a pas de contrôleurs, de modèles ou d'actifs JavaScript/CSS complexes personnalisés au-delà de ce qui est nécessaire pour le pixel de suivi.

### 4.2 Contrôleurs (`controllers/`)
- **Contrôleurs Front-Office** : Aucun. Toutes les fonctionnalités du front-office sont gérées via des hooks dans le fichier de module principal.
- **Contrôleurs d'administration Back-Office** : Aucun. La configuration est gérée directement par la méthode `getContent()` dans le fichier de module principal.

### 4.3 Classes et modèles principaux (`classes/`)
- Aucune classe personnalisée ou définition d'`ObjectModel` n'est présente dans ce module. Toute la logique réside dans le fichier de module principal `Kelkoo.php` (ou `index.php` dans les structures plus anciennes).

### 4.4 Actifs JavaScript (`views/js/`)
- Aucun fichier JavaScript dédié n'est inclus dans le module. Le script de suivi Kelkoo nécessaire est généré dynamiquement et injecté directement dans le code HTML via les templates Smarty ou le hook `displayHeader`.

### 4.5 Feuilles de style CSS (`views/css/`)
- Aucun fichier CSS dédié n'est inclus dans le module. Le module n'a pas de composants visuels côté front-office et sa configuration côté back-office utilise le style de formulaire standard de PrestaShop.

### 4.6 Structure des templates Smarty (`views/templates/`)
- **Templates de hook (`views/templates/hook/`)** :
    *   `kelkoo/views/templates/hook/displayOrderConfirmation.tpl` :
        *   **Hook** : `displayOrderConfirmation`
        *   **Objectif** : Ce template est rendu sur la page de confirmation de commande après un achat réussi. Il est responsable de la génération du pixel de suivi des ventes Kelkoo (KST) avec des détails de commande dynamiques (ID de commande, total, détails du produit). Il récupère les informations de commande passées au hook et les formate selon les spécifications de Kelkoo.
    *   `kelkoo/views/templates/hook/header.tpl` :
        *   **Hook** : `displayHeader`
        *   **Objectif** : Ce template est rendu dans la section `<head>` de chaque page. Il est destiné à inclure tous les scripts de suivi Kelkoo globaux ou initialiseurs qui doivent être présents sur l'ensemble du site, bien que pour un suivi des ventes simple, la logique principale se trouve souvent dans `displayOrderConfirmation`. Il peut contenir un pixel de base Kelkoo ou un espace réservé pour de futures fonctionnalités Kelkoo.

- **Templates d'administration (`views/templates/admin/`)** : Aucun. Le formulaire de configuration est construit directement dans `getContent()` à l'aide des classes d'aide de formulaire de PrestaShop.
- **Templates Front-Office (`views/templates/front/`)** : Aucun.

### 4.7 Schéma de la base de données et carte des hooks
- **Tables de la base de données** :
    *   Le module ne crée aucune table SQL personnalisée.
    *   Les paramètres de configuration (`ID de suivi Kelkoo`, `Activer le suivi`) sont stockés dans la table `ps_configuration` (ou préfixe `_configuration`) en utilisant des clés comme `KELKOO_TRACKING_ID` et `KELKOO_ENABLED`.

- **Table des hooks enregistrés** :
  | Nom du hook | Moment d'exécution | Objectif technique |
  |---|---|---|
  | `displayHeader` | Rendu dans la section `<head>` de chaque page. | Injecte des scripts de suivi Kelkoo globaux ou un pixel de base. |
  | `displayOrderConfirmation` | Rendu sur la page de confirmation de commande après un achat réussi. | Envoie des données de vente détaillées (ID de commande, montant, produits) à Kelkoo pour le suivi des conversions. |

## 5. Support officiel et mises à jour
Pour les mises à jour officielles, le support technique et pour accéder aux dernières versions du module "Intégration du suivi des ventes Kelkoo", veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
