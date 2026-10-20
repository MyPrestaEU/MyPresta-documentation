---
title: "Bouton Google product plus + coupon - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Google product plus button + coupon par MyPresta.eu."
sidebar:
  label: "Bouton Google product plus + coupon - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Google product plus button + coupon sur MyPresta.eu](https://mypresta.eu/modules/social-networks/google-product-plus-button-coupon.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/google-product-plus-button-coupon/)
>
> ---


# Bouton Google product plus + coupon

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et tout module qui interagit avec des API externes.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal pour le module « Bouton Google product plus + coupon ». Vous trouverez ici tous les paramètres pour contrôler l'affichage du bouton Google +1 et la génération des coupons.

#### **Paramètres généraux**

-   **Update\_ / Updatev\_ (Paramètres internes)**

    -   **Ce que fait ce paramètre :** Ce sont des paramètres internes du module utilisés pour le suivi des mises à jour et du versioning. Ils ne sont pas destinés à une interaction directe avec le marchand.
    -   **Effet de la modification de ce paramètre :** Vous ne devriez **jamais** modifier manuellement ces valeurs. Cela pourrait interférer avec les mises à jour du module ou les processus internes.
    -   **Valeur recommandée :** Laisser tel quel.
    -   **Scénario / exemple de marchand :** Ces paramètres garantissent que votre module peut être mis à jour correctement lorsque de nouvelles versions sont publiées par MyPresta.eu.
-   **Code de bon (gc\_voucher)**

    -   **Ce que fait ce paramètre :** C'est le **pourcentage de réduction** qui sera appliqué au coupon généré pour les clients qui cliquent sur le bouton +1.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur `10` (pour 10 %) :* Les clients qui +1 un produit recevront un coupon de 10 % de réduction sur leur prochain achat.
        -   *Lorsqu'il est défini sur `0` ou laissé vide :* Aucune réduction ne sera appliquée, rendant le coupon sans valeur.
    -   **Valeur recommandée :** Un pourcentage de réduction raisonnable, par exemple, `5`, `10` ou `15`.
    -   **Scénario / exemple de marchand :** Vous souhaitez offrir une réduction de 10 % pour encourager le partage social. Vous entreriez `10` ici.
-   **Afficher les prix (gc\_show\_prices)**

    -   **Ce que fait ce paramètre :** Détermine si les prix originaux et réduits sont affichés avec l'offre de coupon.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé (Oui) :* Le client verra le prix original et le prix après application de la réduction, ce qui rend la valeur du coupon plus claire.
        -   *Lorsqu'il est désactivé (Non) :* Seul le code de coupon sera affiché, sans comparaisons de prix explicites.
    -   **Valeur recommandée :** `Oui`. Afficher la différence de prix augmente souvent la valeur perçue du coupon.
    -   **Scénario / exemple de marchand :** Un client voit un produit à 100 €. Si « Afficher les prix » est activé et que le coupon est de 10 %, il verra « 100 € -> 90 € avec coupon », ce qui est plus convaincant.
-   **Afficher le total (gc\_show\_total)**

    -   **Ce que fait ce paramètre :** Contrôle si la valeur totale de la commande (après réduction) est affichée avec le coupon. Ceci est généralement pertinent si le coupon s'applique à l'ensemble du panier.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé (Oui) :* Le client pourrait voir une valeur totale de commande estimée avec la réduction appliquée.
        -   *Lorsqu'il est désactivé (Non) :* L'accent reste mis sur le prix du produit ou le code de coupon lui-même.
    -   **Valeur recommandée :** `Oui`, surtout si le coupon s'applique à l'ensemble du panier, car cela aide le client à visualiser ses économies.
    -   **Scénario / exemple de marchand :** Si le coupon s'applique à l'ensemble du panier, afficher une économie totale potentielle peut encourager un achat plus important.
-   **Afficher les produits (gc\_show\_products)**

    -   **Ce que fait ce paramètre :** Détermine si le ou les produits spécifiques auxquels le coupon s'applique sont listés lorsque le coupon est affiché.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé (Oui) :* Le message du coupon pourrait explicitement indiquer « Ce coupon s'applique à [Nom du produit] ».
        -   *Lorsqu'il est désactivé (Non) :* Le coupon est présenté de manière plus générale, ou il pourrait être supposé s'appliquer au produit qui vient d'être +1.
    -   **Valeur recommandée :** `Oui`, pour plus de clarté, à moins que votre coupon ne soit toujours valable pour toute la boutique.
    -   **Scénario / exemple de marchand :** Si votre coupon n'est valable que pour le produit que le client a +1, afficher le nom du produit clarifie son utilisation.
-   **Afficher l'URL du produit (gc\_show\_product\_url)**

    -   **Ce que fait ce paramètre :** Contrôle si l'URL du produit qui a été +1 est incluse dans l'affichage du coupon.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé (Oui) :* Le client voit un lien direct vers la page du produit, ce qui peut être utile s'il navigue ailleurs.
        -   *Lorsqu'il est désactivé (Non) :* L'URL est omise.
    -   **Valeur recommandée :** `Oui`, pour une meilleure expérience utilisateur et navigation.
    -   **Scénario / exemple de marchand :** Un client obtient un coupon, puis ferme la fenêtre contextuelle. Avoir l'URL du produit l'aide à revenir rapidement au produit qui l'intéressait.
-   **Dernier onglet (gc\_lasttab)**

    -   **Ce que fait ce paramètre :** Ce paramètre contrôle probablement l'onglet ou la section de la page produit où le bouton Google +1 et les informations de coupon apparaîtront, si votre thème utilise une zone de description de produit à onglets.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur `1` (ou une valeur similaire) :* Le contenu du module apparaîtra dans le dernier onglet de la page produit.
        -   *Lorsqu'il est défini sur `0` (ou une valeur similaire) :* Le contenu du module apparaîtra dans le premier onglet ou à un emplacement par défaut.
    -   **Valeur recommandée :** Expérimentez avec `1` pour voir si cela correspond à la mise en page de votre thème. Si votre thème n'utilise pas d'onglets, ce paramètre pourrait n'avoir aucun effet visible.
    -   **Scénario / exemple de marchand :** Votre page produit a des onglets « Description », « Fiche technique » et « Avis ». Définir ceci sur `1` pourrait placer le bouton +1 et le coupon dans un nouvel onglet « Partage social » ou à la fin de l'onglet « Description ».
-   **Position (gc\_position)**

    -   **Ce que fait ce paramètre :** Détermine la zone générale de la page produit où le bouton Google +1 et l'offre de coupon seront affichés. Cela correspond au système de hooks de PrestaShop.
    -   **Effet de la modification de ce paramètre :**
        -   *Modification de la valeur :* Déplace le contenu du module vers différents emplacements sur la page produit (par exemple, au-dessus de « Ajouter au panier », sous la description, dans une colonne latérale).
    -   **Valeur recommandée :** `displayproductActions` ou `displayproductFooter` sont des emplacements courants et efficaces. Testez différentes positions pour voir ce qui s'intègre le mieux à votre thème et est le plus visible pour les clients.
    -   **Scénario / exemple de marchand :** Vous voulez que le bouton +1 soit très visible, vous choisissez donc `displayproductActions` pour le placer près du bouton « Ajouter au panier ».
-   **Nombre de J'aime (gc\_nblikes)**

    -   **Ce que fait ce paramètre :** Ce paramètre contrôle probablement le nombre minimum de +1 requis avant qu'un coupon ne soit émis, ou il pourrait s'agir d'un paramètre d'affichage pour le nombre de +1. Compte tenu de la fonctionnalité principale du module, il est plus probable qu'il soit lié au déclenchement du coupon.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur `1` (ou `0`) :* Un coupon est émis immédiatement après un seul +1.
        -   *Lorsqu'il est défini sur `5` :* Un coupon pourrait n'être émis qu'après 5 +1 uniques (moins probable étant donné la nature de la récompense instantanée, mais possible pour une fonctionnalité de « coupon de groupe »). Plus probablement, il contrôle l'affichage du nombre de +1.
    -   **Valeur recommandée :** `1` (ou `0` si cela signifie « toujours afficher »). La force du module est la gratification instantanée.
    -   **Scénario / exemple de marchand :** Vous voulez que chaque client qui +1 reçoive un coupon, vous définissez donc ceci sur `1`.
-   **Style du bouton (gc\_button\_style)**

    -   **Ce que fait ce paramètre :** Vous permet de choisir le style visuel ou la taille du bouton Google +1.
    -   **Effet de la modification de ce paramètre :**
        -   *Modification de la valeur :* Modifie l'apparence du bouton +1 (par exemple, petit, moyen, grand, haut, avec ou sans compteur).
    -   **Valeur recommandée :** Choisissez un style visible mais qui ne perturbe pas la conception de votre page produit. « Moyen » ou « Standard » sont généralement de bons points de départ.
    -   **Scénario / exemple de marchand :** Votre page produit a un espace limité, vous choisissez donc un style de bouton « petit ».
-   **Mode de partage (gcshare\_mode)**

    -   **Ce que fait ce paramètre :** Ce paramètre contrôle probablement le fonctionnement de la fonctionnalité de partage, offrant éventuellement différentes façons pour le client de partager ou d'interagir avec la plateforme Google+.
    -   **Effet de la modification de ce paramètre :**
        -   *Modification de la valeur :* Pourrait modifier le comportement de la fenêtre contextuelle ou la boîte de dialogue de partage Google+ spécifique qui apparaît.
    -   **Valeur recommandée :** Laissez la valeur par défaut à moins que vous n'ayez une raison spécifique de la modifier et que vous compreniez les implications pour l'intégration de Google+.
    -   **Scénario / exemple de marchand :** Vous pourriez expérimenter différents modes si vous trouvez que l'expérience de partage par défaut n'est pas optimale pour vos clients.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Code de bon (gc\_voucher) | 10 | Pourcentage de réduction pour le coupon généré. |
| Configuration du module | Afficher les prix (gc\_show\_prices) | Oui | Afficher les prix originaux et réduits avec le coupon. |
| Configuration du module | Afficher le total (gc\_show\_total) | Oui | Afficher la valeur totale estimée de la commande avec la réduction. |
| Configuration du module | Afficher les produits (gc\_show\_products) | Oui | Lister le ou les produits spécifiques auxquels le coupon s'applique. |
| Configuration du module | Afficher l'URL du produit (gc\_show\_product\_url) | Oui | Inclure l'URL du produit dans l'affichage du coupon. |
| Configuration du module | Dernier onglet (gc\_lasttab) | 1 (ou dépend du thème) | Position dans les onglets de la page produit (le cas échéant). |
| Configuration du module | Position (gc\_position) | displayproductActions / displayproductFooter | Emplacement général du bouton et du coupon sur la page produit. |
| Configuration du module | Nombre de J'aime (gc\_nblikes) | 1 | Minimum de +1 pour le coupon (probablement 1 pour une récompense instantanée). |
| Configuration du module | Style du bouton (gc\_button\_style) | Standard / Moyen | Taille et style visuels du bouton Google +1. |
| Configuration du module | Mode de partage (gcshare\_mode) | Par défaut | Contrôle l'interaction de partage Google+. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

-   **Q : Le bouton Google +1 n'apparaît pas sur mes pages produits.**

    -   **R :** Tout d'abord, vérifiez le paramètre « Position (gc\_position) » dans la configuration du module. Assurez-vous d'avoir sélectionné un hook qui est réellement rendu par votre thème sur la page produit. Certains thèmes personnalisés peuvent ne pas implémenter tous les hooks PrestaShop standard.
    -   **R :** Videz votre cache PrestaShop (Paramètres avancés > Performances > Vider le cache).
    -   **R :** Vérifiez les erreurs JavaScript dans la console de développement de votre navigateur (F12). Des conflits avec d'autres modules ou scripts de thème peuvent parfois empêcher les boutons de se charger.
    -   **R :** Assurez-vous que le module est activé dans le Gestionnaire de modules.
-   **Q : Les clients cliquent sur +1 mais ne reçoivent pas de coupon.**

    -   **R :** Vérifiez que le paramètre « Code de bon (gc\_voucher) » a un pourcentage de réduction valide (par exemple, `10` pour 10 %). S'il est `0` ou vide, aucun coupon effectif ne sera généré.
    -   **R :** Vérifiez le paramètre « Nombre de J'aime (gc\_nblikes) ». S'il est défini sur une valeur supérieure à 1, le coupon ne sera pas émis tant que ce seuil n'est pas atteint. Pour les coupons instantanés, il doit être de 1.
    -   **R :** Assurez-vous qu'il n'y a pas d'erreurs côté serveur empêchant la génération de coupons. Vérifiez vos journaux d'erreurs PrestaShop (Paramètres avancés > Journaux).
-   **Q : Le bouton semble étrange ou est mal aligné sur mon site mobile.**

    -   **R :** Il s'agit souvent d'un conflit CSS avec votre thème. Le module inclut son propre CSS, mais les styles de votre thème peuvent le remplacer ou entrer en conflit avec lui. Vous pourriez avoir besoin d'un développeur web pour inspecter le CSS et apporter des ajustements mineurs.
    -   **R :** Essayez différentes options de « Style du bouton (gc\_button\_style) » pour voir si une taille différente s'affiche mieux.
-   **Q : Puis-je personnaliser le message du coupon ou sa validité ?**

    -   **R :** La configuration du module contrôle principalement le pourcentage de réduction et les options d'affichage. Pour les règles de coupon avancées (par exemple, achat minimum, catégories spécifiques, période de validité), vous géreriez généralement celles-ci dans la section native « Règles de prix catalogue » ou « Règles panier » (Réductions) de PrestaShop, et le module générerait un code qui adhère à ces règles si applicable, ou vous pourriez avoir besoin de créer manuellement une règle spécifique qui correspond au coupon généré par le module. Le module lui-même génère une réduction en pourcentage de base.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse technique approfondie du module « Bouton Google product plus + coupon » pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module suit une architecture de module PrestaShop standard, exploitant principalement la classe `Module` et ses méthodes `install()`, `uninstall()` et `getContent()`. Il s'intègre au front-office via divers hooks d'affichage pour injecter le bouton Google +1 et la logique de coupon associée. La génération et l'affichage des coupons sont gérés dynamiquement à l'aide de JavaScript et de templates Smarty. Il n'y a pas de classes `ObjectModel` personnalisées ni de contrôleurs d'administration dédiés au-delà de la configuration principale du module.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office :** Aucun. Toutes les fonctionnalités du front-office sont gérées via les hooks du module et le rendu direct des templates.
-   **Contrôleurs d'administration Back-Office :** Aucun. La configuration est entièrement contenue dans la méthode `getContent()` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)

-   Aucune classe personnalisée ou définition `ObjectModel` n'est présente dans le répertoire `classes/`. Toute la logique principale réside dans `googlecoupon/googlecoupon.php`.

### 4.4 Actifs JavaScript (`views/js/`)

-   `googlecoupon/lib/voucherengine/script.js`
    -   **Portée :** Front-office.
    -   **Responsabilité :** Ce script est probablement responsable de la logique principale de la génération et de l'affichage des coupons. Il écouterait l'événement de clic sur le bouton Google +1, déclencherait le processus de génération de coupon (éventuellement via un appel AJAX au fichier principal du module ou une fonction JavaScript directe), puis afficherait le code de coupon à l'utilisateur. Il pourrait également gérer l'interaction avec l'API Google+ (bien que les API Google+ aient été largement dépréciées ou intégrées à d'autres services).
-   `googlecoupon/trusted.js`
    -   **Portée :** Front-office.
    -   **Responsabilité :** Le but de ce script est moins clair d'après son seul nom, mais il pourrait être lié à la garantie de l'intégrité de l'action +1, au suivi ou à l'intégration avec d'autres services de confiance. Il pourrait également être un vestige d'anciennes intégrations d'API Google+.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `googlecoupon/css.css`
    -   **Portée :** Front-office.
    -   **Responsabilité :** Fournit le style principal pour le bouton Google +1, la zone d'affichage des coupons et toutes les fenêtres contextuelles ou notifications associées.
    -   **Sélecteurs de classe CSS clés :** Les développeurs doivent inspecter ce fichier pour identifier les classes spécifiques (par exemple, `.googlecoupon-button-container`, `.googlecoupon-voucher-display`, `.googlecoupon-modal`) qui peuvent être remplacées dans le `custom.css` ou `theme.css` d'un thème personnalisé pour correspondre à l'image de marque de la boutique.
-   `googlecoupon/css/css.css`
    -   **Portée :** Front-office.
    -   **Responsabilité :** Cela semble être un doublon ou une feuille de style alternative. Il est important de vérifier si les deux sont chargés ou si l'un est un fallback. Il contiendrait probablement des règles de style similaires à `googlecoupon/css.css`.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`) :** Aucun explicitement listé, mais le `share.tpl` sert probablement à cet effet.
-   **Templates d'administration (`views/templates/admin/`) :** Aucun.
-   **Templates Front-office (`views/templates/front/`) :** Aucun explicitement listé, mais `share.tpl` est le template clé du front-office.
    -   `googlecoupon/share.tpl`
        -   **Portée :** Front-office.
        -   **Objectif :** Ce template est responsable du rendu du bouton Google +1 et du conteneur où les informations de coupon seront affichées. Il sera injecté dans les différents hooks du front-office configurés dans le module. Il contient probablement des espaces réservés pour le script Google+ et le code de coupon généré dynamiquement.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données :**

    -   Le module ne semble pas créer de tables SQL personnalisées.
    -   Les paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide de clés telles que `GC_VOUCHER`, `GC_SHOW_PRICES`, `GC_SHOW_TOTAL`, `GC_SHOW_PRODUCTS`, `GC_SHOW_PRODUCT_URL`, `GC_LASTTAB`, `GC_POSITION`, `GC_NBLIKES`, `GC_BUTTON_STYLE`, `GCSHARE_MODE`.
-   **Table des hooks enregistrés :**

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayproductActions` | Sur la page produit, généralement près du bouton « Ajouter au panier ». | Injecte le bouton Google +1 et l'affichage du coupon dans une zone proéminente. |
| `displayproductFooter` | Sur la page produit, en bas du bloc d'informations produit. | Injecte le bouton Google +1 et l'affichage du coupon après les détails principaux du produit. |
| `productFooter` | Sur la page produit, similaire à `displayproductFooter`, souvent utilisé pour du contenu additionnel. | Emplacement alternatif pour le bouton Google +1 et l'affichage du coupon. |
| `extraLeft` | Sur la page produit, dans la colonne de gauche (si activé par le thème). | Place le contenu du module dans la barre latérale gauche. |
| `productActions` | Sur la page produit, spécifiquement autour des sélecteurs « Ajouter au panier » et de quantité. | Emplacement alternatif pour le bouton Google +1 et l'affichage du coupon, souvent très proéminent. |
| `displayextraleft` | Sur la page produit, dans la colonne de gauche. | Similaire à `extraLeft`, pour injecter du contenu dans la barre latérale gauche. |
| `extraRight` | Sur la page produit, dans la colonne de droite (si activé par le thème). | Place le contenu du module dans la barre latérale droite. |
| `displayextraright` | Sur la page produit, dans la colonne de droite. | Similaire à `extraRight`, pour injecter du contenu dans la barre latérale droite. |
| `displayHeader` | Dans la section `<head>` de chaque page. | Utilisé pour inclure les fichiers CSS et JavaScript nécessaires au module. |
| `header` | Dans la section `<head>` de chaque page (anciennes versions de PrestaShop). | Similaire à `displayHeader`, pour inclure des actifs. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour télécharger les dernières versions du module « Bouton Google product plus + coupon », veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir.
