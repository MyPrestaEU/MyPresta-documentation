---
title: "HomeFeatured Pro Rollover - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop HomeFeatured Pro Rollover par MyPresta.eu."
sidebar:
  label: "HomeFeatured Pro Rollover"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module HomeFeatured Pro Rollover sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/homefeatured-pro-rollover.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/homefeatured-pro-rollover/)
>
> ---


# HomeFeatured Pro Rollover

## 1. Exigences et compatibilité
- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes et préinstallées sur la plupart des environnements d'hébergement web.

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Après l'installation, cliquez sur "Configurer" à côté de "HomeFeatured Pro Rollover" dans le Gestionnaire de modules pour accéder à ses paramètres.

#### 2.1.1 Nombre de produits à afficher
-   **Ce que fait ce paramètre :** Il contrôle le nombre de produits phares qui seront affichés dans la section "Produits phares" de votre page d'accueil.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est défini sur un nombre spécifique (par exemple, 8) :* Votre page d'accueil affichera exactement ce nombre de produits de votre catégorie "Accueil" (ou de la catégorie que vous avez désignée pour les produits phares).
    -   *Lorsqu'il est défini sur un nombre différent :* Le nombre de produits affichés changera en conséquence. Si vous le définissez trop haut, cela pourrait rendre votre page d'accueil très longue ; si trop bas, vous pourriez ne pas présenter suffisamment de produits.
-   **Valeur recommandée :** Un nombre qui s'intègre bien dans la mise en page de votre page d'accueil, généralement entre 8 et 12 pour une grille standard.
-   **Scénario / exemple marchand :** Si vous souhaitez mettre en avant vos 8 meilleures ventes sur la page d'accueil, vous le définirez sur "8". Si vous avez une mise en page plus large et souhaitez montrer plus de variété, vous pourriez l'augmenter à "12".

#### 2.1.2 Afficher les attributs sur la page produit
-   **Ce que fait ce paramètre :** Il s'agit d'un paramètre PrestaShop standard qui contrôle si les attributs de produit (comme la taille, la couleur) sont affichés sur la page produit elle-même. Bien que ce module affecte principalement la page d'accueil, ce paramètre est souvent inclus dans les modules qui interagissent avec l'affichage des produits.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (Oui) :* Les attributs de produit seront visibles et sélectionnables sur les pages de produits individuelles.
    -   *Lorsqu'il est désactivé (Non) :* Les attributs de produit ne seront pas affichés sur les pages de produits, ce qui pourrait simplifier la page mais supprimer des options de sélection importantes pour les clients.
-   **Valeur recommandée :** **Oui**. La plupart des boutiques doivent afficher les attributs pour les produits avec des variations.
-   **Scénario / exemple marchand :** Pour une boutique de vêtements, les clients doivent sélectionner la taille et la couleur. L'activation de ce paramètre garantit que ces options apparaissent sur la page produit. Le désactiver rendrait impossible pour les clients de choisir des variations.

#### 2.1.3 Langue par défaut
-   **Ce que fait ce paramètre :** Ce paramètre spécifie la langue par défaut de votre boutique. C'est un paramètre PrestaShop essentiel souvent référencé par les modules pour assurer une gestion correcte des langues.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est défini sur votre langue principale (par exemple, Français) :* Le module utilisera cette langue pour toutes les données dépendantes de la langue ou les solutions de repli si des traductions sont manquantes.
-   **Valeur recommandée :** **La langue principale de votre boutique.** Cela devrait correspondre à la langue par défaut que vous avez définie dans les paramètres de localisation de PrestaShop.
-   **Scénario / exemple marchand :** Si le public principal de votre boutique est en France, vous le définirez sur "Français" pour vous assurer que tout le texte par défaut et les informations sur les produits sont correctement affichés en français.

#### 2.1.4 Nombre de produits à afficher (Duplicata de 4.1.1)
-   **Ce que fait ce paramètre :** Il s'agit d'un duplicata du paramètre "Nombre de produits à afficher" (`HOME_FEATURED_PRO_NBR`). Il contrôle le même aspect : combien de produits phares apparaissent sur votre page d'accueil.
-   **Effet de la modification de ce paramètre :** La modification de ce paramètre modifiera directement le nombre de produits affichés dans la section des produits phares.
-   **Valeur recommandée :** Se référer à la section 4.1.1.
-   **Scénario / exemple marchand :** Se référer à la section 4.1.1.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
|---|---|---|---|
| Configuration du module | Nombre de produits à afficher (`HOME_FEATURED_PRO_NBR`) | 8-12 (dépend de la mise en page) | Définit le nombre de produits phares sur la page d'accueil. |
| Configuration du module | Afficher les attributs sur la page produit (`PS_ATTRIBUTE_CATEGORY_DISPLAY`) | Oui | Contrôle la visibilité des attributs de produit sur les pages de produits. |
| Configuration du module | Langue par défaut (`PS_LANG_DEFAULT`) | Langue principale de votre boutique | Spécifie la langue par défaut de la boutique. |
| Configuration du module | Nombre de produits à afficher (`HOME_FEATURED_NBR`) | Identique à `HOME_FEATURED_PRO_NBR` | Paramètre dupliqué pour le nombre de produits phares. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : L'effet de survol ne fonctionne pas sur ma page d'accueil.**
R :
1.  **Vérifiez l'état du module :** Assurez-vous que le module "HomeFeatured Pro Rollover" est installé et activé dans **Modules > Gestionnaire de modules**.
2.  **Videz le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions antérieures). Parfois, un ancien cache empêche les nouvelles modifications du module d'apparaître.
3.  **Images de produits :** Vérifiez que les produits phares ont bien *au moins deux* images téléchargées dans leurs paramètres de produit (**Catalogue > Produits > [Modifier le produit] > Onglet Images**). Le module a besoin d'une deuxième image à afficher au survol.
4.  **Compatibilité du thème :** Bien que le module soit conçu pour une large compatibilité, les thèmes très fortement personnalisés peuvent nécessiter des ajustements CSS mineurs. Si le problème persiste, contactez le support MyPresta.eu.

**Q : Ma page d'accueil semble cassée après l'installation.**
R :
1.  **Action immédiate :** Si votre boutique devient inutilisable, désactivez immédiatement le module depuis **Modules > Gestionnaire de modules**.
2.  **Vérifiez la version de PrestaShop :** Assurez-vous d'avoir téléchargé la version correcte du module pour votre installation PrestaShop (par exemple, la version PS 8.x pour PrestaShop 8.x).
3.  **Conflits de thème :** Certains thèmes peuvent avoir leur propre logique de "produits phares" qui entre en conflit. Essayez de passer temporairement au thème PrestaShop par défaut (Classic) pour voir si le problème se résout. Si c'est le cas, le problème est lié au thème.
4.  **Contactez le support :** Fournissez au support MyPresta.eu les détails de votre version de PrestaShop, de votre thème et de tout message d'erreur que vous voyez.

**Q : Comment puis-je modifier les produits "phares" ?**
R : Le module utilise le mécanisme standard des "Produits phares" de PrestaShop. Pour modifier les produits qui apparaissent :
1.  Allez dans **Catalogue > Catégories**.
2.  Trouvez la catégorie nommée "Accueil" (ou la catégorie que vous avez désignée comme catégorie de votre page d'accueil).
3.  Modifiez cette catégorie et allez dans l'onglet "Produits".
4.  Vous pouvez ajouter ou supprimer des produits de cette catégorie pour contrôler ce qui apparaît dans votre section des produits phares.

**Q : Les images ne sont pas parfaitement alignées ou dimensionnées lors du survol.**
R : Cela indique généralement un conflit CSS avec votre thème.
1.  **Dimensions des images :** Assurez-vous que toutes les images de produits (en particulier les première et deuxième) sont téléchargées avec des rapports d'aspect cohérents et des dimensions similaires. PrestaShop les redimensionne automatiquement, mais de grandes différences peuvent entraîner des décalages de mise en page.
2.  **Personnalisation du thème :** Le CSS de votre thème peut annuler le style du module. Un webmaster peut inspecter l'élément à l'aide des outils de développement du navigateur pour identifier les règles CSS conflictuelles et appliquer un correctif dans le fichier CSS personnalisé de votre thème.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture
Le module HomeFeatured Pro Rollover (`homefeaturedpro`) est un module PrestaShop simple conçu pour remplacer et améliorer la fonctionnalité du module `homefeatured` par défaut. Il se concentre principalement sur l'affichage en front-office, injectant spécifiquement du JavaScript et du CSS pour activer l'effet de survol d'image sur les produits phares de la page d'accueil. Il utilise le système de hooks de PrestaShop pour intégrer sa logique et ses templates. Le module n'introduit pas de nouvelles tables de base de données ou d'ObjectModels complexes, s'appuyant plutôt sur les données de produits PrestaShop existantes.

### 4.2 Contrôleurs (`controllers/`)
Ce module n'introduit aucun contrôleur d'administration Front-Office ou Back-Office personnalisé. Toute la configuration est gérée via la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)
Ce module n'introduit aucune classe ou ObjetModel personnalisé. Il fonctionne en étendant les fonctionnalités existantes de PrestaShop et en rendant ses propres templates.

### 4.4 Actifs JavaScript (`views/js/`)
Ce module n'inclut aucun fichier JavaScript personnalisé. L'effet de survol est obtenu uniquement via CSS.

### 4.5 Feuilles de style CSS (`views/css/`)
-   **`homefeaturedpro/homefeatured.css`**
    *   **Portée :** Style client en front-office.
    *   **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :** Cette feuille de style contient les règles CSS principales responsables de l'effet de survol d'image. Elle cible les conteneurs d'images de produits dans la section des produits phares, utilisant probablement des sélecteurs comme `.product-container .product-image`, `.product-image-container`, ou similaires, pour masquer la deuxième image par défaut et l'afficher au survol.
    *   **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer dans leur thème :**
        *   `.product-image-container .img-hover` : Contrôle probablement la visibilité et le positionnement de la deuxième image.
        *   `.product-image-container .img-primary` : Contrôle l'image principale.
        *   Styles liés aux propriétés `transition` pour des changements d'image fluides.
        *   `overflow: hidden` sur le conteneur d'image pour gérer l'échange d'images.

### 4.6 Structure du template Smarty (`views/templates/`)

-   **`homefeaturedpro/homefeatured.tpl`**
    *   **Portée :** Front-office.
    *   **Hook :** Principalement rendu dans `displayHome` ou `Home` (selon la version de PrestaShop et la configuration du thème).
    *   **Objectif :** C'est le template principal responsable du rendu de la grille des produits phares sur la page d'accueil. Il itère sur la variable `$products` (passée depuis la méthode `hookDisplayHome` du module) et pour chaque produit, il génère la structure HTML incluant les images primaire et secondaire, le nom du produit, le prix et d'autres détails. Il est conçu pour fonctionner avec PrestaShop 1.7.x et versions plus récentes. La logique au sein de ce template est cruciale pour afficher les deux images et appliquer les classes CSS nécessaires à l'effet de survol.

-   **`homefeaturedpro/homefeatured14.tpl`**
    *   **Portée :** Front-office.
    *   **Hook :** Probablement destiné aux anciennes versions de PrestaShop (par exemple, 1.4.x, 1.5.x, 1.6.x) si le module les prend en charge, ou comme alternative pour des structures de thème spécifiques.
    *   **Objectif :** Ce template a le même objectif que `homefeatured.tpl` mais est structuré pour être compatible avec les syntaxes de template et les structures HTML des anciennes versions de PrestaShop. Il itérerait également sur les produits et rendrait les éléments d'image nécessaires à l'effet de survol. Pour les versions modernes de PrestaShop (1.7+), `homefeatured.tpl` est le template principal utilisé.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données :**
    *   Le module ne crée aucune table de base de données personnalisée.
    *   Il stocke ses paramètres de configuration dans la table `ps_configuration` en utilisant les clés suivantes :
        *   `HOME_FEATURED_PRO_NBR` : Stocke le nombre de produits phares à afficher.
        *   `PS_ATTRIBUTE_CATEGORY_DISPLAY` : (Configuration PrestaShop standard, potentiellement référencée ou définie par le module).
        *   `PS_LANG_DEFAULT` : (Configuration PrestaShop standard, potentiellement référencée ou définie par le module).
        *   `HOME_FEATURED_NBR` : (Duplicata de `HOME_FEATURED_PRO_NBR`, probablement pour la rétrocompatibilité ou la cohérence interne).

-   **Table des hooks enregistrés :**

| Nom du hook | Moment d'exécution | Objectif technique |
|---|---|---|
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Utilisé pour inclure la feuille de style CSS du module (`homefeatured.css`) afin de s'assurer que les styles de survol sont chargés avant le contenu de la page. |
| `header` | Alias de `displayHeader`. | Identique à `displayHeader`. |
| `Home` | Sur la page d'accueil, généralement dans la zone de contenu principale. | Rend le template des produits phares du module (`homefeatured.tpl` ou `homefeatured14.tpl`) et lui transmet les données du produit. |
| `displayHome` | Alias de `Home` dans les versions modernes de PrestaShop. | Identique à `Home`. |

## 5. Support officiel et mises à jour
Pour les mises à jour officielles, le support technique et toute assistance supplémentaire concernant le module HomeFeatured Pro Rollover, veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez rencontrer.
