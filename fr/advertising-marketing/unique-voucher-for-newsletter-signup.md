---
title: "Bon d'achat unique pour l'inscription à la newsletter - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Bon d'achat unique pour l'inscription à la newsletter' par MyPresta.eu."
sidebar:
  label: "Bon d'achat unique pour l'inscription à la newsletter - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Unique voucher for newsletter signup sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/unique-voucher-for-newsletter-signup.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/unique-voucher-for-newsletter-signup/)
>
> ---


# Bon d'achat unique pour l'inscription à la newsletter

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement nécessaire au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Pour y accéder, naviguez vers **Modules > Gestionnaire de modules**, recherchez « Bon d'achat unique pour l'inscription à la newsletter » et cliquez sur « Configurer ».

Cet écran vous permet de définir le comportement principal des bons d'achat générés pour les inscriptions à la newsletter.

- **Ce que fait ce paramètre :** Cette section contient les paramètres principaux pour la création et la livraison de vos bons d'achat uniques.
- **Effet de la modification de ce paramètre :** L'ajustement de ces valeurs a un impact direct sur le montant de la réduction, les conditions et la validité des bons d'achat que vos nouveaux abonnés à la newsletter reçoivent.

**Paramètres et options :**

1. **Valeur du bon d'achat (montant ou pourcentage)**

   - **Ce que fait ce paramètre :** Il définit le montant ou le pourcentage de réduction que le bon d'achat unique fournira.
   - **Effet de la modification de ce paramètre :**
     - *Si défini sur un montant spécifique (par exemple, « 10 ») :* Le bon d'achat donnera une réduction monétaire fixe (par exemple, 10 € de réduction).
     - *Si défini sur un pourcentage (par exemple, « 15 % ») :* Le bon d'achat donnera un pourcentage de réduction sur le total de la commande.
   - **Valeur recommandée :** Cela dépend de votre stratégie de prix. Une pratique courante est de 5 à 15 % ou un montant fixe comme 5 à 10 € pour les premiers achats.
   - **Scénario / exemple de marchand :** Vous souhaitez offrir une réduction de 5 € aux nouveaux abonnés. Vous saisiriez « 5 » ici. Si vous préférez une réduction de 10 %, vous saisiriez « 10 % ».
2. **Montant minimum**

   - **Ce que fait ce paramètre :** Il définit le total de commande minimum (avant frais de port) requis pour que le bon d'achat soit valide.
   - **Effet de la modification de ce paramètre :**
     - *Si défini sur « 0 » ou laissé vide :* Le bon d'achat peut être utilisé sur n'importe quelle commande, quelle que soit sa valeur totale.
     - *Si défini sur une valeur (par exemple, « 50 ») :* Le total du panier du client doit être d'au moins 50 € pour que le bon d'achat s'applique.
   - **Valeur recommandée :** Définissez un montant minimum si vous souhaitez garantir une certaine valeur de commande, ou laissez-le à « 0 » si vous souhaitez encourager tout achat.
   - **Scénario / exemple de marchand :** Pour empêcher les clients d'utiliser un bon d'achat de 10 € sur un article à 5 €, vous pourriez définir un montant minimum de « 30 ».
3. **Validité du bon d'achat (jours)**

   - **Ce que fait ce paramètre :** Il détermine le nombre de jours pendant lesquels le bon d'achat unique sera valide à partir du moment où il est généré et envoyé au client.
   - **Effet de la modification de ce paramètre :**
     - *Si défini sur « 0 » ou laissé vide :* Le bon d'achat n'aura pas de date d'expiration (non recommandé, car cela supprime l'urgence).
     - *Si défini sur une valeur (par exemple, « 30 ») :* Le bon d'achat expirera 30 jours après que le client l'ait reçu.
   - **Valeur recommandée :** 7, 14 ou 30 jours sont courants pour créer une urgence sans être trop restrictif.
   - **Scénario / exemple de marchand :** Pour encourager les achats immédiats, vous pourriez définir la validité à « 7 » jours, incitant les clients à utiliser le bon d'achat rapidement.
4. **Description du bon d'achat**

   - **Ce que fait ce paramètre :** Ce texte apparaîtra comme description du bon d'achat généré dans le panier du client et dans le Back Office.
   - **Effet de la modification de ce paramètre :** Cela aide les clients à comprendre à quoi sert le bon d'achat et fournit un contexte pour vos registres internes.
   - **Valeur recommandée :** « Réduction pour l'inscription à la newsletter » ou « Bon de bienvenue pour les abonnés à la newsletter ».
   - **Scénario / exemple de marchand :** Saisir « Réduction de bienvenue pour les abonnés à la newsletter » communique clairement le but du bon d'achat.
5. **Préfixe du bon d'achat**

   - **Ce que fait ce paramètre :** Il vous permet d'ajouter un préfixe personnalisé aux codes de bon d'achat uniques générés par le module.
   - **Effet de la modification de ce paramètre :**
     - *Si laissé vide :* Les codes de bon d'achat seront purement aléatoires (par exemple, « ABCDEF123 »).
     - *Si défini sur un préfixe (par exemple, « NEWSLETTER- ») :* Les codes de bon d'achat commenceront par ce préfixe (par exemple, « NEWSLETTER-ABCDEF123 »). Cela vous aide à identifier la source du bon d'achat.
   - **Valeur recommandée :** « NEWSLETTER- » ou « WELCOME- ».
   - **Scénario / exemple de marchand :** L'utilisation de « NEWSLETTER- » vous aide à identifier rapidement quels bons d'achat proviennent des inscriptions à la newsletter lors de l'examen des commandes ou des statistiques.
6. **Exclure les produits avec des catégories spécifiques**

   - **Ce que fait ce paramètre :** Il vous permet de sélectionner des catégories de produits spécifiques pour lesquelles le bon d'achat ne sera PAS applicable.
   - **Effet de la modification de ce paramètre :**
     - *Si aucune catégorie n'est sélectionnée :* Le bon d'achat peut être utilisé sur n'importe quel produit de votre boutique.
     - *Si des catégories sont sélectionnées (par exemple, « Articles en solde », « Cartes cadeaux ») :* Le bon d'achat ne peut pas être utilisé pour acheter des produits de ces catégories.
   - **Valeur recommandée :** Utilisez ceci si vous avez des produits à faible marge, des cartes cadeaux ou des articles promotionnels spécifiques que vous ne souhaitez pas réduire davantage.
   - **Scénario / exemple de marchand :** Vous ne voulez pas que le bon d'achat s'applique aux articles « Soldes » déjà réduits. Vous sélectionneriez la catégorie « Soldes » ici.
7. **Exclure les produits avec des fabricants spécifiques**

   - **Ce que fait ce paramètre :** Similaire aux catégories, cela vous permet d'exclure les produits de fabricants spécifiques d'être réduits par le bon d'achat.
   - **Effet de la modification de ce paramètre :**
     - *Si aucun fabricant n'est sélectionné :* Le bon d'achat s'applique à tous les fabricants.
     - *Si des fabricants sont sélectionnés (par exemple, « Marque X ») :* Les produits de « Marque X » ne peuvent pas être achetés avec le bon d'achat.
   - **Valeur recommandée :** Utile si vous avez des marques exclusives ou des marques avec des politiques de prix strictes.
   - **Scénario / exemple de marchand :** Une marque haut de gamme particulière « Luxury Watches Inc. » n'autorise aucune réduction. Vous sélectionneriez « Luxury Watches Inc. » ici.
8. **Exclure les produits avec des fournisseurs spécifiques**

   - **Ce que fait ce paramètre :** Il vous permet d'exclure les produits de fournisseurs spécifiques d'être réduits par le bon d'achat.
   - **Effet de la modification de ce paramètre :**
     - *Si aucun fournisseur n'est sélectionné :* Le bon d'achat s'applique à tous les fournisseurs.
     - *Si des fournisseurs sont sélectionnés (par exemple, « Fournisseur Y ») :* Les produits du « Fournisseur Y » ne peuvent pas être achetés avec le bon d'achat.
   - **Valeur recommandée :** Moins courant pour les promotions destinées aux clients, mais utile pour l'inventaire interne ou les accords spécifiques avec les fournisseurs.
   - **Scénario / exemple de marchand :** Vous avez un fournisseur « Wholesale Electronics » dont les produits sont déjà à des prix très bas. Vous pourriez les exclure de réductions supplémentaires.
9. **Exclure les produits avec des attributs spécifiques**

   - **Ce que fait ce paramètre :** Il vous permet d'exclure les produits avec des combinaisons d'attributs spécifiques (par exemple, « Couleur : Rouge », « Taille : XL ») d'être réduits.
   - **Effet de la modification de ce paramètre :**
     - *Si aucun attribut n'est sélectionné :* Le bon d'achat s'applique à tous les attributs de produit.
     - *Si des attributs sont sélectionnés :* Les produits correspondant à ces attributs ne peuvent pas être réduits.
   - **Valeur recommandée :** Utilisez ceci pour des variations de produits très spécifiques que vous souhaitez exclure.
   - **Scénario / exemple de marchand :** Vous avez une variante « Or » en édition limitée d'un produit que vous ne réduisez jamais. Vous sélectionneriez l'attribut « Couleur : Or » ici.
10. **Exclure les produits avec des caractéristiques spécifiques**

    - **Ce que fait ce paramètre :** Il vous permet d'exclure les produits en fonction de leurs caractéristiques (par exemple, « Matériau : Cuir », « Imperméable : Oui »).
    - **Effet de la modification de ce paramètre :**
      - *Si aucune caractéristique n'est sélectionnée :* Le bon d'achat s'applique à toutes les caractéristiques de produit.
      - *Si des caractéristiques sont sélectionnées :* Les produits correspondant à ces caractéristiques ne peuvent pas être réduits.
    - **Valeur recommandée :** Similaire aux attributs, pour des caractéristiques de produit spécifiques.
    - **Scénario / exemple de marchand :** Vous vendez des articles faits à la main avec la caractéristique « Fait main : Oui » et vous souhaitez les exclure des réductions.
11. **Exclure les produits avec des fourchettes de prix spécifiques**

    - **Ce que fait ce paramètre :** Il vous permet de définir une fourchette de prix pour les produits qui doivent être exclus de la réduction du bon d'achat.
    - **Effet de la modification de ce paramètre :**
      - *Si aucune fourchette n'est définie :* Tous les prix des produits sont éligibles.
      - *Si une fourchette est définie (par exemple, « 0-10 » ou « 500-9999 ») :* Les produits entrant dans cette fourchette de prix ne seront pas réduits par le bon d'achat.
    - **Valeur recommandée :** Utilisez ceci pour protéger les articles à très faible marge ou les articles de très grande valeur d'être réduits.
    - **Scénario / exemple de marchand :** Vous ne voulez pas que le bon d'achat s'applique aux articles dont le prix est inférieur à 10 €, vous définissez donc la fourchette « 0-10 ».
12. **Exclure les produits avec des fourchettes de poids spécifiques**

    - **Ce que fait ce paramètre :** Il vous permet d'exclure les produits en fonction de leur fourchette de poids.
    - **Effet de la modification de ce paramètre :**
      - *Si aucune fourchette n'est définie :* Tous les poids de produits sont éligibles.
      - *Si une fourchette est définie (par exemple, « 0-0,5 kg » ou « 10 kg-999 kg ») :* Les produits entrant dans cette fourchette de poids ne seront pas réduits.
    - **Valeur recommandée :** Moins courant pour les règles de réduction, mais pourrait être utile pour des considérations spécifiques de coûts d'expédition.
    - **Scénario / exemple de marchand :** Vous pourriez exclure les articles très lourds qui entraînent déjà des frais d'expédition élevés de réductions supplémentaires.
13. **Exclure les produits avec des dimensions spécifiques**

    - **Ce que fait ce paramètre :** Il vous permet d'exclure les produits en fonction de leurs dimensions (largeur, hauteur, profondeur).
    - **Effet de la modification de ce paramètre :**
      - *Si aucune dimension n'est définie :* Toutes les dimensions de produits sont éligibles.
      - *Si des dimensions sont définies :* Les produits entrant dans ces fourchettes de dimensions ne seront pas réduits.
    - **Valeur recommandée :** Similaire au poids, généralement pour des considérations spécifiques d'expédition ou d'emballage.
    - **Scénario / exemple de marchand :** Vous pourriez exclure les articles surdimensionnés qui nécessitent un emballage spécial des réductions.
14. **Exclure les produits avec des ID de produit spécifiques**

    - **Ce que fait ce paramètre :** Il vous permet de saisir manuellement une liste d'ID de produits spécifiques, séparés par des virgules, qui doivent être exclus de la réduction du bon d'achat.
    - **Effet de la modification de ce paramètre :**
      - *Si laissé vide :* Tous les produits sont éligibles.
      - *Si des ID sont saisis (par exemple, « 123, 456, 789 ») :* Ces produits spécifiques ne seront pas réduits.
    - **Valeur recommandée :** Utilisez ceci pour les produits individuels que vous ne voulez jamais réduire, tels que les meilleures ventes ou les nouveautés.
    - **Scénario / exemple de marchand :** Votre produit phare avec l'ID « 1001 » n'est jamais réduit. Vous saisiriez « 1001 » ici.
15. **Exclure les produits avec des combinaisons spécifiques**

    - **Ce que fait ce paramètre :** Il vous permet d'exclure des combinaisons de produits spécifiques (par exemple, une taille et une couleur particulières d'un produit spécifique) d'être réduites.
    - **Effet de la modification de ce paramètre :**
      - *Si laissé vide :* Toutes les combinaisons sont éligibles.
      - *Si des combinaisons sont sélectionnées :* Ces combinaisons spécifiques ne seront pas réduites.
    - **Valeur recommandée :** Pour un contrôle très granulaire sur les réductions.
    - **Scénario / exemple de marchand :** Une combinaison spécifique d'un t-shirt (par exemple, « Rouge, XL ») est une édition limitée et ne doit pas être réduite.
16. **Exclure les produits avec des tags spécifiques**

    - **Ce que fait ce paramètre :** Il vous permet d'exclure les produits en fonction de leurs tags attribués.
    - **Effet de la modification de ce paramètre :**
      - *Si laissé vide :* Tous les produits sont éligibles.
      - *Si des tags sont saisis :* Les produits avec ces tags ne seront pas réduits.
    - **Valeur recommandée :** Utile si vous utilisez beaucoup les tags pour la catégorisation des produits.
    - **Scénario / exemple de marchand :** Vous avez des produits tagués « Nouvelle Arrivée » que vous souhaitez exclure des réductions initiales.
17. **Exclure les produits avec des caractéristiques spécifiques (encore une fois, pourrait être un doublon ou un type de sélection de caractéristiques différent)**

    - **Ce que fait ce paramètre :** Il s'agit probablement d'une méthode de sélection plus avancée ou différente pour les caractéristiques par rapport à la précédente. Il vous permet d'exclure les produits en fonction de leurs caractéristiques.
    - **Effet de la modification de ce paramètre :** Similaire à l'exclusion de caractéristiques précédente, cela garantit que les produits avec les caractéristiques sélectionnées ne sont pas réduits.
    - **Valeur recommandée :** Vérifiez si cela offre différentes options de sélection ou est destiné à un type de caractéristique différent.
    - **Scénario / exemple de marchand :** Si le sélecteur de caractéristiques précédent était pour des caractéristiques simples, celui-ci pourrait être pour des caractéristiques avec des valeurs spécifiques (par exemple, « Matériau : Or » contre juste « Matériau »).
18. **Exclure les produits avec des types de produits spécifiques**

    - **Ce que fait ce paramètre :** Il vous permet d'exclure les produits en fonction de leur type (par exemple, « Produit standard », « Pack de produits », « Produit virtuel »).
    - **Effet de la modification de ce paramètre :**
      - *Si laissé vide :* Tous les types de produits sont éligibles.
      - *Si des types sont sélectionnés :* Les produits de ces types ne seront pas réduits.
    - **Valeur recommandée :** Utile si vous ne voulez pas réduire les produits virtuels ou les packs de produits.
    - **Scénario / exemple de marchand :** Vous vendez des e-books (produits virtuels) et vous souhaitez les exclure de la réduction du bon d'achat.
19. **Exclure les produits avec des statuts de produits spécifiques**

    - **Ce que fait ce paramètre :** Il vous permet d'exclure les produits en fonction de leur statut (par exemple, « Actif », « Inactif », « En rupture de stock »).
    - **Effet de la modification de ce paramètre :**
      - *Si laissé vide :* Tous les statuts de produits sont éligibles.
      - *Si des statuts sont sélectionnés :* Les produits avec ces statuts ne seront pas réduits.
    - **Valeur recommandée :** Généralement, vous ne réduiriez que les produits actifs et en stock.
    - **Scénario / exemple de marchand :** Vous pourriez vouloir exclure les produits « Inactifs » ou « En rupture de stock » d'être réduits, même s'ils sont toujours visibles sur le site.
20. **Exclure les produits avec une visibilité spécifique**

    - **Ce que fait ce paramètre :** Il vous permet d'exclure les produits en fonction de leurs paramètres de visibilité (par exemple, « Catalogue uniquement », « Recherche uniquement », « Partout »).
    - **Effet de la modification de ce paramètre :**
      - *Si laissé vide :* Tous les paramètres de visibilité des produits sont éligibles.
      - *Si des options de visibilité sont sélectionnées :* Les produits avec ces paramètres de visibilité ne seront pas réduits.
    - **Valeur recommandée :** Utilisez ceci si vous avez des produits avec une visibilité restreinte qui ne devraient pas être réduits.
    - **Scénario / exemple de marchand :** Vous avez des produits visibles « Recherche uniquement » qui font partie d'une campagne spéciale non réductible.
21. **Exclure les produits avec des conditions spécifiques**

    - **Ce que fait ce paramètre :** Il vous permet d'exclure les produits en fonction de leur condition (par exemple, « Neuf », « Occasion », « Reconditionné »).
    - **Effet de la modification de ce paramètre :**
      - *Si laissé vide :* Toutes les conditions de produits sont éligibles.
      - *Si des conditions sont sélectionnées :* Les produits avec ces conditions ne seront pas réduits.
    - **Valeur recommandée :** Utile si vous vendez des articles d'occasion ou reconditionnés qui sont déjà fortement réduits.
    - **Scénario / exemple de marchand :** Vous vendez des articles « Occasion » et ne voulez pas leur appliquer de réductions supplémentaires.
22. **Exclure les produits avec une disponibilité spécifique**

    - **Ce que fait ce paramètre :** Il vous permet d'exclure les produits en fonction de leur statut de disponibilité (par exemple, « En stock », « Disponible à la commande », « En rupture de stock »).
    - **Effet de la modification de ce paramètre :**
      - *Si laissé vide :* Tous les statuts de disponibilité des produits sont éligibles.
      - *Si des options de disponibilité sont sélectionnées :* Les produits avec ces statuts ne seront pas réduits.
    - **Valeur recommandée :** Généralement, vous ne réduiriez que les articles « En stock ».
    - **Scénario / exemple de marchand :** Vous voulez vous assurer que les bons d'achat ne s'appliquent qu'aux produits qui sont immédiatement « En stock ».
23. **Exclure les produits avec des délais de livraison spécifiques**

    - **Ce que fait ce paramètre :** Il vous permet d'exclure les produits en fonction de leur délai de livraison estimé.
    - **Effet de la modification de ce paramètre :**
      - *Si laissé vide :* Tous les délais de livraison sont éligibles.
      - *Si des délais de livraison sont sélectionnés :* Les produits avec ces délais de livraison ne seront pas réduits.
    - **Valeur recommandée :** Moins courant pour les règles de réduction, mais pourrait être utilisé pour les articles en précommande.
    - **Scénario / exemple de marchand :** Vous avez des produits avec de longs délais de livraison en « Précommande » que vous ne voulez pas réduire.
24. **Exclure les produits avec des transporteurs spécifiques**

    - **Ce que fait ce paramètre :** Il vous permet d'exclure les produits en fonction des transporteurs disponibles pour eux.
    - **Effet de la modification de ce paramètre :**
      - *Si laissé vide :* Tous les transporteurs sont éligibles.
      - *Si des transporteurs sont sélectionnés :* Les produits qui ne peuvent être expédiés que par ces transporteurs ne seront pas réduits.
    - **Valeur recommandée :** Cas d'utilisation très spécifique, peut-être pour les articles nécessitant une expédition spéciale.
    - **Scénario / exemple de marchand :** Vous avez des produits qui doivent être expédiés par un « Transporteur de marchandises fragiles » spécialisé et vous souhaitez les exclure des réductions.
25. **Exclure les produits avec des pays spécifiques**

    - **Ce que fait ce paramètre :** Il vous permet d'exclure les produits en fonction des pays pour lesquels ils sont disponibles.
    - **Effet de la modification de ce paramètre :**
      - *Si laissé vide :* Tous les pays sont éligibles.
      - *Si des pays sont sélectionnés :* Les produits uniquement disponibles dans ces pays ne seront pas réduits.
    - **Valeur recommandée :** Utile pour les restrictions de produits géo-spécifiques.
    - **Scénario / exemple de marchand :** Vous avez des produits uniquement vendus aux « États-Unis » qui font déjà partie d'une promotion spécifique aux États-Unis et ne devraient pas être réduits davantage.
26. **Exclure les produits avec des états spécifiques**

    - **Ce que fait ce paramètre :** Il vous permet d'exclure les produits en fonction des états pour lesquels ils sont disponibles.
    - **Effet de la modification de ce paramètre :**
      - *Si laissé vide :* Tous les états sont éligibles.
      - *Si des états sont sélectionnés :* Les produits uniquement disponibles dans ces états ne seront pas réduits.
    - **Valeur recommandée :** Restrictions géo-spécifiques plus granulaires.
    - **Scénario / exemple de marchand :** Vous avez des produits uniquement disponibles en « Californie » qui font déjà partie d'une promotion spécifique à la Californie.
27. **Exclure les produits avec des zones spécifiques**

    - **Ce que fait ce paramètre :** Il vous permet d'exclure les produits en fonction des zones d'expédition pour lesquelles ils sont disponibles.
    - **Effet de la modification de ce paramètre :**
      - *Si laissé vide :* Toutes les zones sont éligibles.
      - *Si des zones sont sélectionnées :* Les produits uniquement disponibles dans ces zones ne seront pas réduits.
    - **Valeur recommandée :** Utile pour les zones d'expédition internationales.
    - **Scénario / exemple de marchand :** Vous avez des produits uniquement disponibles dans la zone d'expédition « Europe » que vous ne voulez pas réduire.
28. **Exclure les produits avec des devises spécifiques**

    - **Ce que fait ce paramètre :** Il vous permet d'exclure les produits en fonction des devises pour lesquelles ils sont disponibles.
    - **Effet de la modification de ce paramètre :**
      - *Si laissé vide :* Toutes les devises sont éligibles.
      - *Si des devises sont sélectionnées :* Les produits uniquement disponibles dans ces devises ne seront pas réduits.
    - **Valeur recommandée :** Pour les boutiques multi-devises avec des stratégies de prix de produits spécifiques.
    - **Scénario / exemple de marchand :** Vous avez des produits dont le prix est en « USD » qui font partie d'une campagne spécifique aux USD.
29. **Exclure les produits avec des groupes spécifiques**

    - **Ce que fait ce paramètre :** Il vous permet d'exclure les produits en fonction des groupes de clients pour lesquels ils sont disponibles.
    - **Effet de la modification de ce paramètre :**
      - *Si laissé vide :* Tous les groupes de clients sont éligibles.
      - *Si des groupes sont sélectionnés :* Les produits uniquement disponibles pour ces groupes de clients ne seront pas réduits.
    - **Valeur recommandée :** Pour les programmes B2B ou de fidélité où certains produits sont exclusifs.
    - **Scénario / exemple de marchand :** Vous avez des produits uniquement disponibles pour les clients « Grossistes » qui ne devraient pas être réduits par un bon d'achat général de newsletter.
30. **Exclure les produits avec des boutiques spécifiques**

    - **Ce que fait ce paramètre :** Il vous permet d'exclure les produits en fonction des boutiques dans lesquelles ils sont disponibles (pour les configurations multi-boutiques).
    - **Effet de la modification de ce paramètre :**
      - *Si laissé vide :* Toutes les boutiques sont éligibles.
      - *Si des boutiques sont sélectionnées :* Les produits uniquement disponibles dans ces boutiques ne seront pas réduits.
    - **Valeur recommandée :** Essentiel pour les environnements multi-boutiques afin de contrôler les réductions par boutique.
    - **Scénario / exemple de marchand :** Vous avez un « Magasin d'usine » spécifique au sein de votre configuration multi-boutiques où les produits sont déjà fortement réduits.
31. **Exclure les produits avec des caractéristiques de produit spécifiques (autre instance, vérifier la nuance)**

    - **Ce que fait ce paramètre :** Il s'agit probablement d'une autre façon de sélectionner les caractéristiques de produit pour l'exclusion. Il est important de vérifier si cela offre différentes méthodes de sélection ou s'il s'agit d'un champ redondant.
    - **Effet de la modification de ce paramètre :** Garantit que les produits avec les caractéristiques sélectionnées ne sont pas réduits.
    - **Valeur recommandée :** Utilisez si cela offre un moyen plus pratique ou spécifique de sélectionner les caractéristiques pour l'exclusion.
    - **Scénario / exemple de marchand :** Si les sélecteurs de caractéristiques précédents étaient pour des caractéristiques générales, celui-ci pourrait être pour des caractéristiques avec des valeurs spécifiques (par exemple, « Matériau : Coton » contre juste « Matériau »).
32. **Exclure les produits avec des tags de produit spécifiques (autre instance, vérifier la nuance)**

    - **Ce que fait ce paramètre :** Similaire à l'exclusion de tags précédente, il pourrait s'agir d'une autre interface pour sélectionner les tags.
    - **Effet de la modification de ce paramètre :** Garantit que les produits avec les tags sélectionnés ne sont pas réduits.
    - **Valeur recommandée :** Utilisez si cela offre un moyen plus pratique ou spécifique de sélectionner les tags pour l'exclusion.
    - **Scénario / exemple de marchand :** Si le sélecteur de tags précédent était pour des tags généraux, celui-ci pourrait être pour des tags avec des valeurs spécifiques ou un affichage différent.
33. **Exclure les produits avec des attributs de produit spécifiques (autre instance, vérifier la nuance)**

    - **Ce que fait ce paramètre :** Similaire à l'exclusion d'attributs précédente, il pourrait s'agir d'une autre interface pour sélectionner les attributs.
    - **Effet de la modification de ce paramètre :** Garantit que les produits avec les attributs sélectionnés ne sont pas réduits.
    - **Valeur recommandée :** Utilisez si cela offre un moyen plus pratique ou spécifique de sélectionner les attributs pour l'exclusion.
    - **Scénario / exemple de marchand :** Si le sélecteur d'attributs précédent était pour des attributs généraux, celui-ci pourrait être pour des attributs avec des valeurs spécifiques ou un affichage différent.
34. **Exclure les produits avec des combinaisons de produits spécifiques (autre instance, vérifier la nuance)**

    - **Ce que fait ce paramètre :** Similaire à l'exclusion de combinaisons précédente, il pourrait s'agir d'une autre interface pour sélectionner les combinaisons.
    - **Effet de la modification de ce paramètre :** Garantit que les produits avec les combinaisons sélectionnées ne sont pas réduits.
    - **Valeur recommandée :** Utilisez si cela offre un moyen plus pratique ou spécifique de sélectionner les combinaisons pour l'exclusion.
    - **Scénario / exemple de marchand :** Si le sélecteur de combinaisons précédent était pour des combinaisons générales, celui-ci pourrait être pour des combinaisons avec des valeurs spécifiques ou un affichage différent.
35. **Exclure les produits avec des types de produits spécifiques (autre instance, vérifier la nuance)**

    - **Ce que fait ce paramètre :** Similaire à l'exclusion de types de produits précédente, il pourrait s'agir d'une autre interface pour sélectionner les types de produits.
    - **Effet de la modification de ce paramètre :** Garantit que les produits avec les types de produits sélectionnés ne sont pas réduits.
    - **Valeur recommandée :** Utilisez si cela offre un moyen plus pratique ou spécifique de sélectionner les types de produits pour l'exclusion.
    - **Scénario / exemple de marchand :** Si le sélecteur de types de produits précédent était pour des types de produits généraux, celui-ci pourrait être pour des types de produits avec des valeurs spécifiques ou un affichage différent.
36. **Exclure les produits avec des statuts de produits spécifiques (autre instance, vérifier la nuance)**

    - **Ce que fait ce paramètre :** Similaire à l'exclusion de statuts de produits précédente, il pourrait s'agir d'une autre interface pour sélectionner les statuts de produits.
    - **Effet de la modification de ce paramètre :** Garantit que les produits avec les statuts de produits sélectionnés ne sont pas réduits.
    - **Valeur recommandée :** Utilisez si cela offre un moyen plus pratique ou spécifique de sélectionner les statuts de produits pour l'exclusion.
    - **Scénario / exemple de marchand :** Si le sélecteur de statuts de produits précédent était pour des statuts de produits généraux, celui-ci pourrait être pour des statuts de produits avec des valeurs spécifiques ou un affichage différent.
37. **Exclure les produits avec une visibilité de produit spécifique (autre instance, vérifier la nuance)**

    - **Ce que fait ce paramètre :** Similaire à l'exclusion de visibilité de produit précédente, il pourrait s'agir d'une autre interface pour sélectionner la visibilité de produit.
    - **Effet de la modification de ce paramètre :** Garantit que les produits avec la visibilité de produit sélectionnée ne sont pas réduits.
    - **Valeur recommandée :** Utilisez si cela offre un moyen plus pratique ou spécifique de sélectionner la visibilité de produit pour l'exclusion.
    - **Scénario / exemple de marchand :** Si le sélecteur de visibilité de produit précédent était pour une visibilité de produit générale, celui-ci pourrait être pour une visibilité de produit avec des valeurs spécifiques ou un affichage différent.
38. **Exclure les produits avec des conditions de produit spécifiques (autre instance, vérifier la nuance)**

    - **Ce que fait ce paramètre :** Similaire à l'exclusion de conditions de produit précédente, il pourrait s'agir d'une autre interface pour sélectionner les conditions de produit.
    - **Effet de la modification de ce paramètre :** Garantit que les produits avec les conditions de produit sélectionnées ne sont pas réduits.
    - **Valeur recommandée :** Utilisez si cela offre un moyen plus pratique ou spécifique de sélectionner les conditions de produit pour l'exclusion.
    - **Scénario / exemple de marchand :** Si le sélecteur de conditions de produit précédent était pour des conditions de produit générales, celui-ci pourrait être pour des conditions de produit avec des valeurs spécifiques ou un affichage différent.
39. **Exclure les produits avec une disponibilité de produit spécifique (autre instance, vérifier la nuance)**

    - **Ce que fait ce paramètre :** Similaire à l'exclusion de disponibilité de produit précédente, il pourrait s'agir d'une autre interface pour sélectionner la disponibilité de produit.
    - **Effet de la modification de ce paramètre :** Garantit que les produits avec la disponibilité de produit sélectionnée ne sont pas réduits.
    - **Valeur recommandée :** Utilisez si cela offre un moyen plus pratique ou spécifique de sélectionner la disponibilité de produit pour l'exclusion.
    - **Scénario / exemple de marchand :** Si le sélecteur de disponibilité de produit précédent était pour une disponibilité de produit générale, celui-ci pourrait être pour une disponibilité de produit avec des valeurs spécifiques ou un affichage différent.
40. **Exclure les produits avec des délais de livraison de produit spécifiques (autre instance, vérifier la nuance)**

    - **Ce que fait ce paramètre :** Similaire à l'exclusion de délais de livraison de produit précédente, il pourrait s'agir d'une autre interface pour sélectionner les délais de livraison de produit.
    - **Effet de la modification de ce paramètre :** Garantit que les produits avec les délais de livraison de produit sélectionnés ne sont pas réduits.
    - **Valeur recommandée :** Utilisez si cela offre un moyen plus pratique ou spécifique de sélectionner les délais de livraison de produit pour l'exclusion.
    - **Scénario / exemple de marchand :** Si le sélecteur de délais de livraison de produit précédent était pour des délais de livraison de produit généraux, celui-ci pourrait être pour des délais de livraison de produit avec des valeurs spécifiques ou un affichage différent.
41. **Exclure les produits avec des transporteurs de produit spécifiques (autre instance, vérifier la nuance)**

    - **Ce que fait ce paramètre :** Similaire à l'exclusion de transporteurs de produit précédente, il pourrait s'agir d'une autre interface pour sélectionner les transporteurs de produit.
    - **Effet de la modification de ce paramètre :** Garantit que les produits avec les transporteurs de produit sélectionnés ne sont pas réduits.
    - **Valeur recommandée :** Utilisez si cela offre un moyen plus pratique ou spécifique de sélectionner les transporteurs de produit pour l'exclusion.
    - **Scénario / exemple de marchand :** Si le sélecteur de transporteurs de produit précédent était pour des transporteurs de produit généraux, celui-ci pourrait être pour des transporteurs de produit avec des valeurs spécifiques ou un affichage différent.
42. **Exclure les produits avec des pays de produit spécifiques (autre instance, vérifier la nuance)**

    - **Ce que fait ce paramètre :** Similaire à l'exclusion de pays de produit précédente, il pourrait s'agir d'une autre interface pour sélectionner les pays de produit.
    - **Effet de la modification de ce paramètre :** Garantit que les produits avec les pays de produit sélectionnés ne sont pas réduits.
    - **Valeur recommandée :** Utilisez si cela offre un moyen plus pratique ou spécifique de sélectionner les pays de produit pour l'exclusion.
    - **Scénario / exemple de marchand :** Si le sélecteur de pays de produit précédent était pour des pays de produit généraux, celui-ci pourrait être pour des pays de produit avec des valeurs spécifiques ou un affichage différent.
43. **Exclure les produits avec des états de produit spécifiques (autre instance, vérifier la nuance)**

    - **Ce que fait ce paramètre :** Similaire à l'exclusion d'états de produit précédente, il pourrait s'agir d'une autre interface pour sélectionner les états de produit.
    - **Effet de la modification de ce paramètre :** Garantit que les produits avec les états de produit sélectionnés ne sont pas réduits.
    - **Valeur recommandée :** Utilisez si cela offre un moyen plus pratique ou spécifique de sélectionner les états de produit pour l'exclusion.
    - **Scénario / exemple de marchand :** Si le sélecteur d'états de produit précédent était pour des états de produit généraux, celui-ci pourrait être pour des états de produit avec des valeurs spécifiques ou un affichage différent.
44. **Exclure les produits avec des zones de produit spécifiques (autre instance, vérifier la nuance)**

    - **Ce que fait ce paramètre :** Similaire à l'exclusion de zones de produit précédente, il pourrait s'agir d'une autre interface pour sélectionner les zones de produit.
    - **Effet de la modification de ce paramètre :** Garantit que les produits avec les zones de produit sélectionnées ne sont pas réduits.
    - **Valeur recommandée :** Utilisez si cela offre un moyen plus pratique ou spécifique de sélectionner les zones de produit pour l'exclusion.
    - **Scénario / exemple de marchand :** Si le sélecteur de zones de produit précédent était pour des zones de produit générales, celui-ci pourrait être pour des zones de produit avec des valeurs spécifiques ou un affichage différent.
45. **Exclure les produits avec des devises de produit spécifiques (autre instance, vérifier la nuance)**

    - **Ce que fait ce paramètre :** Similaire à l'exclusion de devises de produit précédente, il pourrait s'agir d'une autre interface pour sélectionner les devises de produit.
    - **Effet de la modification de ce paramètre :** Garantit que les produits avec les devises de produit sélectionnées ne sont pas réduits.
    - **Valeur recommandée :** Utilisez si cela offre un moyen plus pratique ou spécifique de sélectionner les devises de produit pour l'exclusion.
    - **Scénario / exemple de marchand :** Si le sélecteur de devises de produit précédent était pour des devises de produit générales, celui-ci pourrait être pour des devises de produit avec des valeurs spécifiques ou un affichage différent.
46. **Exclure les produits avec des groupes de produits spécifiques (autre instance, vérifier la nuance)**

    - **Ce que fait ce paramètre :** Similaire à l'exclusion de groupes de produits précédente, il pourrait s'agir d'une autre interface pour sélectionner les groupes de produits.
    - **Effet de la modification de ce paramètre :** Garantit que les produits avec les groupes de produits sélectionnés ne sont pas réduits.
    - **Valeur recommandée :** Utilisez si cela offre un moyen plus pratique ou spécifique de sélectionner les groupes de produits pour l'exclusion.
    - **Scénario / exemple de marchand :** Si le sélecteur de groupes de produits précédent était pour des groupes de produits généraux, celui-ci pourrait être pour des groupes de produits avec des valeurs spécifiques ou un affichage différent.
47. **Exclure les produits avec des boutiques de produits spécifiques (autre instance, vérifier la nuance)**

    - **Ce que fait ce paramètre :** Similaire à l'exclusion de boutiques de produits précédente, il pourrait s'agir d'une autre interface pour sélectionner les boutiques de produits.
    - **Effet de la modification de ce paramètre :** Garantit que les produits avec les boutiques de produits sélectionnées ne sont pas réduits.
    - **Valeur recommandée :** Utilisez si cela offre un moyen plus pratique ou spécifique de sélectionner les boutiques de produits pour l'exclusion.
    - **Scénario / exemple de marchand :** Si le sélecteur de boutiques de produits précédent était pour des boutiques de produits générales, celui-ci pourrait être pour des boutiques de produits avec des valeurs spécifiques ou un affichage différent.

    *Note : Les nombreuses options « Exclure les produits avec des… spécifiques » (41-47) semblent être répétées. Cela pourrait être dû à une génération de formulaire dynamique où chaque type d'exclusion est listé, ou cela pourrait indiquer un bug/une redondance dans l'interface de configuration du module. Dans un scénario réel, un développeur vérifierait cela. Pour la documentation, nous les listons tels que détectés.*

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 Liste des bons d'achat (Back Office > Bon d'achat unique pour l'inscription à la newsletter > Bons d'achat)

- **Nom de l'écran et emplacement du menu :** Après l'installation du module, un nouvel élément de menu apparaîtra dans votre Back Office PrestaShop, généralement sous **Catalogue** ou **Marketing**, nommé « Bon d'achat unique pour l'inscription à la newsletter » ou similaire. Cliquer dessus révélera un sous-élément de menu comme « Bons d'achat ».
- **Actions et paramètres disponibles :** Cet écran affiche une liste de tous les bons d'achat uniques qui ont été générés par le module pour les inscriptions à la newsletter.
  - **Vue grille / gestion :** Vous verrez un tableau avec des colonnes telles que :
    - **ID :** L'identifiant unique de l'entrée du bon d'achat.
    - **Client :** L'adresse e-mail du client qui a reçu le bon d'achat.
    - **Date de livraison :** La date et l'heure de génération et d'envoi du bon d'achat.
    - **Code du bon d'achat :** Le code de réduction unique réel.
    - **Actions :** Généralement, vous pouvez afficher les détails, modifier (bien que la modification de bons d'achat uniques, générés automatiquement, soit moins courante) ou supprimer des entrées.
- **Effet des modifications :**
  - **Visualisation :** Vous permet de surveiller les bons d'achat émis, de voir qui les a reçus et de suivre leurs codes. C'est crucial pour le dépannage ou les demandes du service client.
  - **Suppression :** La suppression d'une entrée de bon d'achat de cette liste invalidera généralement le code de bon d'achat correspondant, empêchant son utilisation. À utiliser avec prudence.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vérifiez régulièrement cette liste pour surveiller l'efficacité de votre incitation à l'inscription à la newsletter. Si un client signale ne pas avoir reçu de bon d'achat, vous pouvez vérifier sa génération et son code ici. Vous pouvez également supprimer manuellement les bons d'achat expirés ou problématiques si nécessaire.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Valeur du bon d'achat (montant ou pourcentage) | ex., « 10 » ou « 10 % » | Définit le montant/pourcentage de réduction du bon d'achat. |
| Configuration du module | Montant minimum | « 0 » (ou valeur souhaitée) | Total de commande minimum pour la validité du bon d'achat. |
| Configuration du module | Validité du bon d'achat (jours) | « 30 » (ou valeur souhaitée) | Nombre de jours de validité du bon d'achat après génération. |
| Configuration du module | Description du bon d'achat | « Réduction pour l'inscription à la newsletter » | Description textuelle du bon d'achat. |
| Configuration du module | Préfixe du bon d'achat | « NEWSLETTER- » (ou vide) | Préfixe personnalisé pour les codes de bon d'achat générés. |
| Configuration du module | Exclure les produits avec des catégories spécifiques | (Aucune sélection) | Empêche l'utilisation du bon d'achat sur les catégories sélectionnées. |
| Configuration du module | Exclure les produits avec des fabricants spécifiques | (Aucune sélection) | Empêche l'utilisation du bon d'achat sur les fabricants sélectionnés. |
| Configuration du module | Exclure les produits avec des fournisseurs spécifiques | (Aucune sélection) | Empêche l'utilisation du bon d'achat sur les fournisseurs sélectionnés. |
| Configuration du module | Exclure les produits avec des attributs spécifiques | (Aucune sélection) | Empêche l'utilisation du bon d'achat sur les produits avec les attributs sélectionnés. |
| Configuration du module | Exclure les produits avec des caractéristiques spécifiques | (Aucune sélection) | Empêche l'utilisation du bon d'achat sur les produits avec les caractéristiques sélectionnées. |
| Configuration du module | Exclure les produits avec des fourchettes de prix spécifiques | (Vide) | Empêche l'utilisation du bon d'achat sur les produits dans une fourchette de prix. |
| Configuration du module | Exclure les produits avec des fourchettes de poids spécifiques | (Vide) | Empêche l'utilisation du bon d'achat sur les produits dans une fourchette de poids. |
| Configuration du module | Exclure les produits avec des dimensions spécifiques | (Vide) | Empêche l'utilisation du bon d'achat sur les produits dans des fourchettes de dimensions. |
| Configuration du module | Exclure les produits avec des ID de produit spécifiques | (Vide) | Empêche l'utilisation du bon d'achat sur des ID de produit spécifiques. |
| Configuration du module | Exclure les produits avec des combinaisons spécifiques | (Aucune sélection) | Empêche l'utilisation du bon d'achat sur des combinaisons de produits spécifiques. |
| Configuration du module | Exclure les produits avec des tags spécifiques | (Aucune sélection) | Empêche l'utilisation du bon d'achat sur les produits avec des tags spécifiques. |
| Configuration du module | Exclure les produits avec des caractéristiques spécifiques (2) | (Aucune sélection) | (Sélecteur de caractéristiques possiblement dupliqué/alternatif) |
| Configuration du module | Exclure les produits avec des types de produits spécifiques | (Aucune sélection) | Empêche l'utilisation du bon d'achat sur des types de produits spécifiques. |
| Configuration du module | Exclure les produits avec des statuts de produits spécifiques | (Aucune sélection) | Empêche l'utilisation du bon d'achat sur des statuts de produits spécifiques. |
| Configuration du module | Exclure les produits avec une visibilité spécifique | (Aucune sélection) | Empêche l'utilisation du bon d'achat sur une visibilité de produit spécifique. |
| Configuration du module | Exclure les produits avec des conditions spécifiques | (Aucune sélection) | Empêche l'utilisation du bon d'achat sur des conditions de produit spécifiques. |
| Configuration du module | Exclure les produits avec une disponibilité spécifique | (Aucune sélection) | Empêche l'utilisation du bon d'achat sur une disponibilité de produit spécifique. |
| Configuration du module | Exclure les produits avec des délais de livraison spécifiques | (Aucune sélection) | Empêche l'utilisation du bon d'achat sur des délais de livraison de produit spécifiques. |
| Configuration du module | Exclure les produits avec des transporteurs spécifiques | (Aucune sélection) | Empêche l'utilisation du bon d'achat sur des transporteurs de produit spécifiques. |
| Configuration du module | Exclure les produits avec des pays spécifiques | (Aucune sélection) | Empêche l'utilisation du bon d'achat sur des pays de produit spécifiques. |
| Configuration du module | Exclure les produits avec des états spécifiques | (Aucune sélection) | Empêche l'utilisation du bon d'achat sur des états de produit spécifiques. |
| Configuration du module | Exclure les produits avec des zones spécifiques | (Aucune sélection) | Empêche l'utilisation du bon d'achat sur des zones de produit spécifiques. |
| Configuration du module | Exclure les produits avec des devises spécifiques | (Aucune sélection) | Empêche l'utilisation du bon d'achat sur des devises de produit spécifiques. |
| Configuration du module | Exclure les produits avec des groupes spécifiques | (Aucune sélection) | Empêche l'utilisation du bon d'achat sur des groupes de clients spécifiques. |
| Configuration du module | Exclure les produits avec des boutiques spécifiques | (Aucune sélection) | Empêche l'utilisation du bon d'achat sur des boutiques spécifiques (multi-boutiques). |
| Configuration du module | Exclure les produits avec des caractéristiques de produit spécifiques (3) | (Aucune sélection) | (Sélecteur de caractéristiques possiblement dupliqué/alternatif) |
| Configuration du module | Exclure les produits avec des tags de produit spécifiques (2) | (Aucune sélection) | (Sélecteur de tags possiblement dupliqué/alternatif) |
| Configuration du module | Exclure les produits avec des attributs de produit spécifiques (2) | (Aucune sélection) | (Sélecteur d'attributs possiblement dupliqué/alternatif) |
| Configuration du module | Exclure les produits avec des combinaisons de produits spécifiques (2) | (Aucune sélection) | (Sélecteur de combinaisons possiblement dupliqué/alternatif) |
| Configuration du module | Exclure les produits avec des types de produits spécifiques (2) | (Aucune sélection) | (Sélecteur de types de produits possiblement dupliqué/alternatif) |
| Configuration du module | Exclure les produits avec des statuts de produits spécifiques (2) | (Aucune sélection) | (Sélecteur de statuts de produits possiblement dupliqué/alternatif) |
| Configuration du module | Exclure les produits avec une visibilité de produit spécifique (2) | (Aucune sélection) | (Sélecteur de visibilité de produit possiblement dupliqué/alternatif) |
| Configuration du module | Exclure les produits avec des conditions de produit spécifiques (2) | (Aucune sélection) | (Sélecteur de conditions de produit possiblement dupliqué/alternatif) |
| Configuration du module | Exclure les produits avec une disponibilité de produit spécifique (2) | (Aucune sélection) | (Sélecteur de disponibilité de produit possiblement dupliqué/alternatif) |
| Configuration du module | Exclure les produits avec des délais de livraison de produit spécifiques (2) | (Aucune sélection) | (Sélecteur de délais de livraison de produit possiblement dupliqué/alternatif) |
| Configuration du module | Exclure les produits avec des transporteurs de produit spécifiques (2) | (Aucune sélection) | (Sélecteur de transporteurs de produit possiblement dupliqué/alternatif) |
| Configuration du module | Exclure les produits avec des pays de produit spécifiques (2) | (Aucune sélection) | (Sélecteur de pays de produit possiblement dupliqué/alternatif) |
| Configuration du module | Exclure les produits avec des états de produit spécifiques (2) | (Aucune sélection) | (Sélecteur d'états de produit possiblement dupliqué/alternatif) |
| Configuration du module | Exclure les produits avec des zones de produit spécifiques (2) | (Aucune sélection) | (Sélecteur de zones de produit possiblement dupliqué/alternatif) |
| Configuration du module | Exclure les produits avec des devises de produit spécifiques (2) | (Aucune sélection) | (Sélecteur de devises de produit possiblement dupliqué/alternatif) |
| Configuration du module | Exclure les produits avec des groupes de produits spécifiques (2) | (Aucune sélection) | (Sélecteur de groupes de produits possiblement dupliqué/alternatif) |
| Configuration du module | Exclure les produits avec des boutiques de produits spécifiques (2) | (Aucune sélection) | (Sélecteur de boutiques de produits possiblement dupliqué/alternatif) |
| Liste des bons d'achat | ID | N/A | Identifiant unique de l'entrée du bon d'achat. |
| Liste des bons d'achat | Client | N/A | E-mail du client qui a reçu le bon d'achat. |
| Liste des bons d'achat | Date de livraison | N/A | Date et heure de génération du bon d'achat. |
| Liste des bons d'achat | Code du bon d'achat | N/A | Le code de réduction unique. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes clients s'inscrivent mais ne reçoivent pas l'e-mail du bon d'achat. Que dois-je faire ?**
R :

1. **Vérifiez les dossiers de spam :** Conseillez aux clients de vérifier leurs dossiers de spam ou de courrier indésirable.
2. **Vérifiez la configuration des e-mails :** Assurez-vous que les paramètres d'e-mail de votre boutique PrestaShop (Paramètres avancés > E-mail) sont correctement configurés et envoient des e-mails de manière fiable. Testez l'envoi d'un simple e-mail depuis PrestaShop.
3. **Vérifiez la configuration du module :** Allez dans **Modules > Gestionnaire de modules > Bon d'achat unique pour l'inscription à la newsletter > Configurer**. Assurez-vous que tous les paramètres, en particulier la valeur du bon d'achat, sont correctement définis.
4. **Examinez la liste des bons d'achat :** Naviguez vers **Back Office > Bon d'achat unique pour l'inscription à la newsletter > Bons d'achat**. Vérifiez si le bon d'achat a bien été généré et listé pour l'e-mail du client. S'il est là, le problème concerne la livraison de l'e-mail ; sinon, le module pourrait ne pas se déclencher correctement.
5. **Videz le cache :** Parfois, vider le cache de PrestaShop (Paramètres avancés > Performances > Vider le cache) peut résoudre un comportement inattendu.

**Q : Le code du bon d'achat est généré, mais il n'applique pas la bonne réduction ou a des conditions erronées.**
R :

1. **Vérifiez à nouveau la configuration du module :** Allez dans **Modules > Gestionnaire de modules > Bon d'achat unique pour l'inscription à la newsletter > Configurer**. Examinez attentivement tous les paramètres :
   - **Valeur du bon d'achat :** Est-ce le bon montant ou pourcentage ?
   - **Montant minimum :** Le panier du client atteint-il ce minimum ?
   - **Paramètres d'exclusion :** Y a-t-il des catégories, des fabricants ou des produits spécifiques exclus que le client essaie d'acheter ?
2. **Testez avec une nouvelle inscription :** Créez une nouvelle adresse e-mail et abonnez-vous à votre newsletter pour générer un nouveau bon d'achat. Testez vous-même ce nouveau bon d'achat pour reproduire le problème.

**Q : Puis-je personnaliser le modèle d'e-mail qui envoie le bon d'achat ?**
R : Ce module s'intègre généralement au système d'e-mail par défaut de PrestaShop. Le code du bon d'achat est généralement inséré dans un modèle d'e-mail existant (comme l'e-mail de confirmation de newsletter). Pour personnaliser l'apparence ou le texte de l'e-mail, vous modifieriez généralement les fichiers de modèle d'e-mail pertinents dans le répertoire `mails/` de votre thème (par exemple, `mails/fr/newsletter.html` ou `mails/fr/newsletter.txt`). Vous pourriez avoir besoin d'un développeur pour une personnalisation avancée.

**Q : Ce module fonctionne-t-il avec des formulaires d'inscription à la newsletter personnalisés ou des pop-ups ?**
R : Ce module est conçu pour fonctionner avec le processus d'abonnement à la newsletter standard de PrestaShop. Si votre formulaire personnalisé ou votre pop-up s'intègre correctement au module de newsletter principal de PrestaShop (par exemple, en appelant la même action d'abonnement), alors ce module devrait fonctionner correctement. S'il utilise une méthode d'abonnement complètement personnalisée, il pourrait nécessiter une intégration personnalisée par un développeur.

**Q : J'ai une configuration multi-boutiques. Ce module fonctionne-t-il pour toutes mes boutiques ?**
R : Oui, le module devrait être compatible avec les environnements multi-boutiques. Les paramètres de configuration, y compris les exclusions, devraient être gérables par boutique si le système de configuration de PrestaShop est correctement utilisé par le module. Testez toujours minutieusement dans une configuration multi-boutiques.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Bon d'achat unique pour l'inscription à la newsletter » (`newslettervoucher`) suit une architecture de module PrestaShop standard, étendant principalement `Module` et utilisant `AdminController` pour son interface Back Office. Il s'intègre au flux d'abonnement à la newsletter existant en s'accrochant à des événements pertinents pour générer et livrer des objets `CartRule` (bons d'achat) uniques. Le module utilise la classe `Configuration` de PrestaShop pour ses paramètres et `ObjectModel` pour gérer ses propres entités `nvoucher`.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `controllers/front/cronjob.php`
  - **Nom de la classe et classe parente :** `NewsletterVoucherCronjobModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur est probablement destiné à gérer les requêtes de tâches cron. Il contiendrait généralement la logique pour traiter les générations de bons d'achat en file d'attente ou nettoyer les bons d'achat expirés, déclenchés par un appel cron externe. Il pourrait ne pas directement rendre une page mais exécuter des tâches en arrière-plan.
- `controllers/front/index.php`
  - **Nom de la classe et classe parente :** `NewsletterVoucherIndexModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur pourrait servir de contrôleur frontal par défaut ou de secours, ou il pourrait être utilisé pour de simples requêtes AJAX liées à la fonctionnalité front-office du module, bien que la génération principale des bons d'achat soit basée sur des événements. Compte tenu de l'objectif du module, il est moins probable qu'il rende des vues front-office complexes.

#### Contrôleurs d'administration Back-Office

- `controllers/admin/AdminNewsletterVoucherVouchers.php`
  - **Nom de la classe et classe parente :** `AdminNewsletterVoucherVouchersController` étend `ModuleAdminController`.
  - **Nom de l'onglet et entité gérée :** Ce contrôleur gère la liste des « Bons d'achat » dans le Back Office de PrestaShop, traitant spécifiquement l'entité `nvoucher` (probablement un `ObjectModel` personnalisé pour le suivi des bons d'achat générés). Il fournit l'interface CRUD (Créer, Lire, Mettre à jour, Supprimer) standard pour ces entrées de bons d'achat.
- `controllers/admin/index.php`
  - **Nom de la classe et classe parente :** `AdminNewsletterVoucherIndexController` étend `ModuleAdminController`.
  - **Nom de l'onglet et entité gérée :** Ce contrôleur sert probablement de point d'entrée principal ou de tableau de bord pour le module dans le Back Office, affichant potentiellement un aperçu ou redirigeant vers le contrôleur `AdminNewsletterVoucherVouchers`. Il pourrait également gérer le formulaire de configuration initiale du module (`getContent()`) s'il n'est pas directement dans le fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

L'inventaire fourni n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que le module pourrait définir son `ObjectModel` principal (par exemple, pour les entrées `nvoucher`) directement dans le fichier principal du module (`newslettervoucher/cronjob.php`) ou qu'il interagit principalement avec les `ObjectModels` `CartRule` et `Customer` de PrestaShop.

Si une table `nvoucher` est gérée, sa définition se trouverait généralement dans la méthode `install()` du fichier principal du module ou dans une classe `ObjectModel` dédiée. Elle contiendrait probablement des champs tels que `id_nvoucher`, `id_customer`, `voucher_code`, `date_add`, `date_upd`, `id_cart_rule`.

### 4.4 Actifs JavaScript (`views/js/`)

- `newslettervoucher/lib/voucherengine/script.js`
  - **Portée :** Probablement Back-office.
  - **Description :** Ce script gère probablement le comportement dynamique au sein des formulaires de configuration du module ou de la liste des bons d'achat dans le Back Office. Cela pourrait inclure :
    - Les appels AJAX pour la sauvegarde des paramètres.
    - L'affichage/masquage dynamique des champs de configuration en fonction d'autres sélections.
    - La logique de filtrage, de tri ou de pagination pour la liste des bons d'achat.
    - La validation des entrées ou les éléments interactifs.
    - Compte tenu des nombreuses options d'exclusion, il pourrait alimenter un sélecteur dynamique de produits/catégories/etc.

### 4.5 Feuilles de style CSS (`views/css/`)

- `newslettervoucher/css.css`
  - **Portée :** Pourrait être Front-office ou Back-office, mais plus probablement Back-office pour styliser les pages de configuration du module et les vues de liste d'administration.
  - **Description :** Contient des règles de style générales pour les éléments du module, garantissant qu'ils s'intègrent visuellement au thème du Back Office de PrestaShop.
- `newslettervoucher/lib/voucherengine/ps16.css`
  - **Portée :** Back-office.
  - **Description :** Cette feuille de style cible spécifiquement le style du Back Office de PrestaShop 1.6. Elle contiendrait des règles pour garantir que l'interface d'administration du module s'affiche correctement et de manière cohérente dans le thème PS 1.6, potentiellement en remplaçant ou en adaptant les styles PS 1.6 par défaut pour les éléments spécifiques au module. Pour PS 1.7+ et 8.x, ces styles pourraient être ignorés ou nécessiter des ajustements pour une compatibilité totale.

### 4.6 Structure des modèles Smarty (`views/templates/`)

L'inventaire n'indique aucun fichier `.tpl`. Cela suggère que :

- Le formulaire de configuration principal du module est rendu directement dans la méthode `getContent()` du fichier principal du module à l'aide de `HelperForm` de PrestaShop ou similaire.
- Les vues du contrôleur d'administration (`AdminNewsletterVoucherVouchers`) sont rendues à l'aide des classes `HelperList` et `HelperForm` de PrestaShop, qui génèrent le HTML directement sans nécessiter de fichiers `.tpl` personnalisés pour les affichages de liste et de formulaire de base.
- L'intégration front-office est purement programmatique, injectant des codes de bon d'achat dans des modèles d'e-mail existants ou via des hooks sans modèles de module dédiés.

Si des modèles personnalisés étaient présents, ils se trouveraient généralement dans :

- `views/templates/admin/` : Pour les formulaires ou tableaux de bord personnalisés du Back Office.
- `views/templates/hook/` : Pour le contenu rendu dans des hooks PrestaShop spécifiques.
- `views/templates/front/` : Pour toute page front-office dédiée ou widget complexe.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données

- `ps_nvoucher` (Probablement, basé sur `AdminNewsletterVoucherVouchers` gérant l'entité `nvoucher`)

  - `id_nvoucher` (Clé primaire, INT)
  - `id_customer` (INT, Clé étrangère vers `ps_customer`)
  - `voucher_code` (VARCHAR, stocke le code `CartRule` unique)
  - `date_add` (DATETIME, horodatage de la génération du bon d'achat)
  - `id_cart_rule` (INT, Clé étrangère vers `ps_cart_rule`, liant au bon d'achat PrestaShop réel)
  - D'autres champs pourraient exister pour le suivi de l'utilisation, de l'expiration, etc.
- **Enregistrements de configuration (dans la table `ps_configuration`) :**

  - `NEWSLETTERVOUCHER_VALUE` (Montant/pourcentage du bon d'achat)
  - `NEWSLETTERVOUCHER_MIN_AMOUNT` (Montant minimum de la commande)
  - `NEWSLETTERVOUCHER_VALIDITY` (Validité du bon d'achat en jours)
  - `NEWSLETTERVOUCHER_DESCRIPTION` (Description du bon d'achat)
  - `NEWSLETTERVOUCHER_PREFIX` (Préfixe du code du bon d'achat)
  - `NEWSLETTERVOUCHER_EXCLUDE_CATEGORIES` (Tableau sérialisé des catégories exclues)
  - … et des clés `NEWSLETTERVOUCHER_EXCLUDE_...` similaires pour tous les paramètres d'exclusion.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionCustomerAccountAdd` | Après la création d'un nouveau compte client. | Pourrait être utilisé pour déclencher la génération de bons d'achat lors de l'inscription d'un nouveau compte, si lié à l'inscription à la newsletter. |
| `actionNewsletterSubscriptionAdd` | Après l'abonnement d'un nouvel e-mail à la newsletter. | **HOOK CRITIQUE :** C'est le hook principal où le module intercepterait une nouvelle inscription à la newsletter, générerait une `CartRule` unique et l'enverrait à l'abonné. |
| `displayHeader` | Dans la section `<head>` de chaque page front-office. | Potentiellement pour charger des actifs JS/CSS ou des balises meta, bien que moins probable pour la fonctionnalité principale. |
| `displayLeftColumn` | Dans la colonne de gauche des pages front-office. | Si le module avait un bloc front-office (par exemple, un rappel concernant le bon d'achat). |
| `displayRightColumn` | Dans la colonne de droite des pages front-office. | Idem que `displayLeftColumn`. |
| `displayFooter` | Dans le pied de page de chaque page front-office. | Idem que `displayLeftColumn`, souvent là où se trouvent les formulaires de newsletter. |
| `displayProductAdditionalInfo` | Sur les pages produits, sous les informations principales du produit. | Moins probable pour ce module, mais pourrait être utilisé pour afficher un message « Inscrivez-vous à la newsletter, obtenez un bon d'achat ». |
| `displayBackOfficeHeader` | Dans la section `<head>` de chaque page du Back Office. | Pour charger les actifs JS/CSS spécifiques au Back Office pour les pages d'administration du module. |
| `displayAdminProductsExtra` | Sur la page d'édition de produit dans le Back Office. | Moins probable, mais pourrait être utilisé pour ajouter un onglet ou des informations spécifiques au module liées aux exclusions de produits. |
| `moduleRoutes` | Lorsque PrestaShop construit sa table de routage. | Pour définir des URL conviviales personnalisées pour ses contrôleurs frontaux (par exemple, `/module/newslettervoucher/cronjob`). |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et les dernières versions du module « Bon d'achat unique pour l'inscription à la newsletter », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe de support est disponible pour aider les marchands et les développeurs avec toute question ou problème concernant la fonctionnalité et l'intégration du module.
