---
title: "Onglet Nouveaux produits sur la page d'accueil - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Onglet Nouveaux produits sur la page d'accueil' par MyPresta.eu."
sidebar:
  label: "Onglet Nouveaux produits sur la page d'accueil"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Homepage tab new products sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tab-new-products.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/homepage-tab-new-products/)
>
> ---


# Onglet Nouveaux produits sur la page d'accueil

## 1. Exigences et compatibilité
- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Après l'installation, cliquez sur "Configurer" à côté du module "Onglet Nouveaux produits sur la page d'accueil" dans le Gestionnaire de modules. Vous serez dirigé vers l'écran de configuration principal.

#### **Nombre de produits à afficher**
-   **Ce que fait ce paramètre :** Il contrôle le nombre de vos produits les plus récents qui seront affichés dans l'onglet "Nouveaux produits" sur votre page d'accueil.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est défini sur un nombre plus élevé (par exemple, 12) :* Plus de nouveaux produits seront visibles par les clients sans qu'ils aient besoin de naviguer vers une page "Nouveaux produits" complète. Cela peut être excellent pour les boutiques avec un volume élevé de nouvelles arrivées.
    -   *Lorsqu'il est défini sur un nombre plus faible (par exemple, 4) :* Moins de produits seront affichés, ce qui donnera un aspect plus propre et moins encombré. Cela pourrait être préféré si vous souhaitez mettre en évidence uniquement les articles les plus frais ou si vous avez un espace limité.
-   **Valeur recommandée :** Commencez par `8` ou `12`. Ajustez en fonction de la mise en page de votre thème et du nombre de produits que vous ajoutez généralement.
-   **Scénario / exemple de marchand :** Si vous gérez un magasin de mode et ajoutez 20 nouveaux articles par semaine, le fait de le régler sur `12` garantit qu'une bonne sélection est toujours visible. Si vous vendez des produits de niche de grande valeur et n'ajoutez que 2 à 3 nouveaux articles par mois, `4` pourrait être suffisant pour éviter les espaces vides.

#### **Classes de la liste de produits**
-   **Ce que fait ce paramètre :** Ce paramètre avancé vous permet d'ajouter des classes CSS personnalisées au conteneur qui contient la liste des nouveaux produits. Il est principalement utilisé à des fins de style, souvent pour s'intégrer de manière transparente à la conception spécifique de votre thème PrestaShop.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsque des classes sont ajoutées (par exemple, `product-grid-container my-custom-style`) :* Le CSS de votre thème ou votre CSS personnalisé peut alors cibler ces classes pour appliquer un style spécifique (par exemple, modifier la disposition des colonnes, l'espacement, la taille des polices, les couleurs) à la liste des nouveaux produits.
    -   *Lorsqu'il est laissé vide :* Le module utilisera son style par défaut ou héritera des styles de la liste de produits générale de votre thème.
-   **Valeur recommandée :** Laissez vide, sauf si vous ou votre développeur web avez besoin d'appliquer un style personnalisé spécifique à la liste de produits. Si vous n'êtes pas sûr, ne modifiez pas ce paramètre.
-   **Scénario / exemple de marchand :** Votre thème affiche des grilles de produits avec 3 colonnes, mais vous souhaitez que l'onglet "Nouveaux produits" affiche 4 colonnes. Votre développeur web pourrait vous dire d'ajouter une classe comme `col-lg-3` (si votre thème utilise les classes de grille Bootstrap) ici, puis d'ajouter du CSS personnalisé pour que cela fonctionne.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact
| Écran / Vue
"""
