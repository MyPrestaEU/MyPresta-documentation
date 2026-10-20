---
title: "Onglet de page d'accueil en promotion (promotions) - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Onglet de page d'accueil en promotion (promotions)' par MyPresta.eu."
sidebar:
  label: "Onglet de page d'accueil en promotion (promotions)"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Homepage tab on sale (promotions) sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tab-on-sale-promotions.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/homepage-tab-on-sale-promotions/)
>
> ---


# Onglet de page d'accueil en promotion (promotions)

## 1. Exigences et compatibilité
- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
C'est l'écran de configuration principal et unique pour le module "Onglet de page d'accueil en promotion (promotions)". Vous pouvez y accéder en naviguant vers **Modules > Gestionnaire de modules** et en recherchant "Onglet de page d'accueil en promotion (promotions)", puis en cliquant sur le bouton "Configurer".

#### Paramètres et options :

-   **Nombre de produits à afficher**
    -   **Ce que fait ce paramètre :** Ce paramètre détermine le nombre maximum de produits à prix réduit qui seront affichés dans l'onglet "En promotion" sur la page d'accueil de votre boutique. Si vous avez plus de produits actuellement en promotion que le nombre spécifié ici, le module n'affichera que cette quantité définie.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé / défini sur un nombre plus élevé (par exemple, 12) :* Vos clients verront une plus grande sélection de produits promotionnels lorsqu'ils cliqueront sur l'onglet "En promotion". Cela peut être bénéfique pour les boutiques avec de nombreuses réductions actives, offrant plus de choix et augmentant potentiellement la probabilité d'un achat. Cependant, afficher trop de produits pourrait rendre la page plus longue et pourrait légèrement augmenter le temps de chargement.
        -   *Lorsqu'il est désactivé / défini sur un nombre inférieur (par exemple, 4) :* Moins de produits en promotion seront visibles. Cela peut créer un affichage plus propre et plus ciblé, ce qui pourrait être préféré si vous n'avez que quelques promotions clés ou si vous souhaitez garder votre page d'accueil très concise. Cela peut également entraîner un chargement de page plus rapide.
    -   **Valeur recommandée :** Un bon point de départ est de **8 à 10 produits**. Cela offre une sélection décente sans submerger le client ni rendre la page excessivement longue. Vous pouvez ajuster cela en fonction de votre nombre moyen d'articles en promotion et de la mise en page de votre thème.
    -   **Scénario / exemple de marchand :**
        -   *Scénario 1 (Grand inventaire, ventes fréquentes) :* Vous organisez des promotions hebdomadaires avec plus de 50 produits en promotion. Vous pourriez définir ce paramètre sur **12** pour donner aux clients un bon aperçu de la variété des offres disponibles directement depuis la page d'accueil.
        -   *Scénario 2 (Boutique, peu de promotions clés) :* Vous n'avez généralement que 3 à 5 articles de grande valeur en promotion à un moment donné. Vous pourriez définir ce paramètre sur **6** pour vous assurer que toutes vos promotions clés sont visibles sans espaces vides ni défilement inutile.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue                | Paramètre / Option               | Valeur par défaut / Recommandée | Objectif et impact
| :--- | :--- | :--- | :---
