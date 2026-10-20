---
title: "Produits Similaires Gratuit - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Produits Similaires Gratuit par MyPresta.eu."
sidebar:
  label: "Produits Similaires Gratuit - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Related Products Free sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/related-products-free.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/related-products-free/)
>
> ---


# Produits Similaires Gratuit

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Extensions PHP standard (cURL, JSON, OpenSSL), qui sont généralement disponibles sur la plupart des environnements d'hébergement compatibles PrestaShop.

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Produits Similaires Gratuit)

C'est l'écran de configuration principal et unique pour le module « Produits Similaires Gratuit ». Ici, vous définirez le comportement du bloc de produits similaires et les produits qu'il affiche.

#### **Afficher les produits similaires de la catégorie**

- **Ce que fait ce paramètre :** Ce paramètre crucial détermine *quels* produits seront affichés comme « similaires ». Au lieu de choisir manuellement des produits pour chaque article, ce module simplifie les choses en vous permettant de sélectionner une catégorie spécifique. Tous les produits appartenant à cette catégorie choisie seront alors affichés comme produits similaires sur *chaque* page produit de votre boutique.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une catégorie est sélectionnée (par exemple, « Accessoires ») :* Sur chaque page produit de votre boutique, un bloc apparaîtra affichant les produits qui appartiennent à la catégorie « Accessoires ».
  - *Lorsque « Aucun » ou aucune catégorie n'est sélectionnée :* Le module n'affichera aucun produit similaire, car il ne sait pas quels produits afficher.
- **Valeur recommandée :** Choisissez une catégorie qui contient des articles généraux, complémentaires ou les plus vendus qui pourraient être pertinents pour un large éventail de vos produits principaux. Par exemple, si vous vendez des vêtements, « Accessoires » ou « Articles en solde » pourraient être de bons choix.
- **Scénario / exemple marchand :** Vous vendez différents types d'électronique. Vous créez une catégorie appelée « Accessoires gadgets indispensables » et y ajoutez des articles comme des chargeurs universels, des protecteurs d'écran et des écouteurs. En sélectionnant cette catégorie ici, chaque page produit (par exemple, pour un smartphone, un ordinateur portable ou une tablette) affichera ces « Accessoires gadgets indispensables » comme produits similaires, encourageant les ventes croisées.

#### **Nombre de produits à afficher**

- **Ce que fait ce paramètre :** Cela contrôle le nombre de produits similaires qui seront affichés dans le bloc sur vos pages produits.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur '4' :* Le module affichera quatre produits de votre catégorie choisie.
  - *Lorsqu'il est défini sur '8' :* Le module affichera huit produits.
- **Valeur recommandée :** 4 ou 5. Trop de produits peuvent submerger le client ou rendre la page encombrée, surtout sur mobile. Une sélection plus petite et organisée est souvent plus efficace.
- **Scénario / exemple marchand :** Vous souhaitez afficher une sélection concise d'articles similaires sans rendre la page produit trop longue. Le réglage sur '4' assure une mise en page propre tout en offrant de bonnes opportunités de vente croisée.

#### **Afficher les produits de la catégorie sélectionnée uniquement**

- **Ce que fait ce paramètre :** Ce paramètre détermine si les produits similaires affichés proviennent *uniquement* de la catégorie que vous avez sélectionnée ci-dessus, ou s'il peut également inclure des produits de la *propre catégorie du produit actuel*.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Seuls les produits de la catégorie choisie dans « Afficher les produits similaires de la catégorie » seront affichés.
  - *Lorsqu'il est désactivé (NON) :* Le module affichera les produits de la catégorie sélectionnée *et* potentiellement les produits de la catégorie du produit que le client consulte actuellement. Cela peut conduire à des suggestions plus pertinentes si la catégorie du produit actuel contient également de bons articles de vente croisée.
- **Valeur recommandée :** « OUI » si votre catégorie de « produits similaires » choisie est très générale (comme « Accessoires »). « NON » si vous souhaitez mélanger des articles similaires plus spécifiques de la catégorie du produit actuel. Testez les deux pour voir ce qui fonctionne le mieux pour votre boutique.
- **Scénario / exemple marchand :** Vous avez sélectionné « Accessoires » comme catégorie similaire. Si vous définissez cela sur « OUI », seuls les accessoires s'afficheront. Si vous le définissez sur « NON », et qu'un client consulte un « T-shirt » (qui est dans la catégorie « Hauts »), le module pourrait afficher à la fois des « Accessoires » et d'autres « Hauts » comme produits similaires.

#### **Hook pour afficher les produits similaires**

- **Ce que fait ce paramètre :** C'est ici que vous décidez *où* sur la page produit le bloc de produits similaires apparaîtra. PrestaShop utilise des « hooks » comme points spécifiques dans le code de la page où les modules peuvent insérer leur contenu.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur `displayFooterProduct` (Recommandé) :* Le bloc de produits similaires apparaîtra en bas de la section d'informations sur le produit, généralement au-dessus du pied de page de l'ensemble de la page. C'est un emplacement courant et efficace.
  - *Lorsqu'il est défini sur `displayProductExtraContent` (PrestaShop 1.7+) :* Le bloc pourrait apparaître dans un onglet ou une section spécifique de la zone de contenu principal de la page produit, selon votre thème.
  - *Autres hooks (par exemple, `displayLeftColumnProduct`, `displayRightColumnProduct`) :* Le bloc apparaîtra dans la barre latérale gauche ou droite de la page produit, si votre thème prend en charge les barres latérales sur les pages produits.
- **Valeur recommandée :** `displayFooterProduct`. Ce hook est largement pris en charge par les thèmes et offre un placement clair et discret pour les articles similaires. Expérimentez avec d'autres si vous avez un design spécifique en tête.
- **Scénario / exemple marchand :** Vous voulez que les produits similaires soient visibles mais n'interfèrent pas avec la description principale du produit et le bouton « Ajouter au panier ». Choisir `displayFooterProduct` le place proprement sous le contenu principal, permettant aux clients de faire défiler et de découvrir plus.

#### **Afficher les produits en carrousel**

- **Ce que fait ce paramètre :** Cela détermine si les produits similaires sont affichés dans une grille statique (tous visibles en même temps) ou dans un carrousel dynamique et défilable (où les clients peuvent cliquer sur des flèches ou glisser pour en voir plus).
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Les produits similaires apparaîtront sous forme de carrousel, vous permettant d'afficher plus de produits dans un espace compact.
  - *Lorsqu'il est désactivé (NON) :* Les produits seront affichés dans une grille statique, montrant tous les produits sélectionnés en même temps (jusqu'à la limite « Nombre de produits à afficher »).
- **Valeur recommandée :** « OUI » si vous voulez économiser de l'espace ou afficher plus de produits qu'il ne peut en tenir confortablement sur une seule ligne. « NON » si vous préférez que tous les produits soient immédiatement visibles sans interaction.
- **Scénario / exemple marchand :** Vous voulez afficher 8 produits similaires, mais les afficher tous dans une grille rend la page trop longue. L'activation du carrousel vous permet d'afficher 8 produits tout en n'occupant que l'espace de 4, les clients faisant défiler pour voir le reste.

#### **Afficher les produits dans un ordre aléatoire**

- **Ce que fait ce paramètre :** Cela contrôle l'ordre dans lequel les produits similaires de votre catégorie choisie sont affichés.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Chaque fois qu'un client visite une page produit, les produits similaires apparaîtront dans un ordre différent et aléatoire.
  - *Lorsqu'il est désactivé (NON) :* Les produits apparaîtront dans un ordre cohérent, généralement basé sur leur ID ou leur position dans la catégorie sélectionnée.
- **Valeur recommandée :** « OUI ». La randomisation de l'ordre garantit que tous les produits de votre catégorie choisie ont une chance d'être vus au fil du temps, empêchant les mêmes quelques produits d'être toujours en haut.
- **Scénario / exemple marchand :** Vous avez 20 produits dans votre catégorie « Accessoires », mais vous n'en affichez que 5. Si l'ordre est toujours le même, seuls les 5 premiers seront toujours vus. En activant l'ordre aléatoire, différents accessoires apparaîtront à chaque fois, augmentant la visibilité pour tous.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Afficher les produits similaires de la catégorie | Sélectionner une catégorie pertinente | Définit la catégorie source des produits similaires. |
| Configuration du module | Nombre de produits à afficher | 4-5 | Contrôle le nombre de produits similaires affichés. |
| Configuration du module | Afficher les produits de la catégorie sélectionnée uniquement | OUI / NON (Tester les deux) | Détermine si seuls les produits de la catégorie sélectionnée sont affichés, ou si la catégorie du produit actuel peut également contribuer. |
| Configuration du module | Hook pour afficher les produits similaires | `displayFooterProduct` | Spécifie l'emplacement du bloc de produits similaires sur la page produit. |
| Configuration du module | Afficher les produits en carrousel | OUI | Affiche les produits similaires dans un carrousel défilable pour un affichage compact. |
| Configuration du module | Afficher les produits dans un ordre aléatoire | OUI | Randomise l'ordre des produits similaires affichés pour une exposition variée. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : J'ai configuré le module, mais je ne vois aucun produit similaire sur mes pages produits.**
R :

1. **Vérifier la sélection de catégorie :** Assurez-vous d'avoir sélectionné une catégorie valide dans le paramètre « Afficher les produits similaires de la catégorie » et que cette catégorie contient réellement des produits.
2. **Vérifier le statut du produit :** Assurez-vous que les produits de votre catégorie sélectionnée sont actifs, en stock et visibles dans votre boutique.
3. **Vider le cache :** Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop et cliquez sur « Vider le cache » (ou « Vider le cache Smarty »). Parfois, PrestaShop a besoin d'une actualisation du cache pour afficher le nouveau contenu du module.
4. **Compatibilité du thème :** Bien que le module utilise des hooks PrestaShop standard, certains thèmes très personnalisés peuvent avoir des surcharges spécifiques. Essayez de passer temporairement au thème PrestaShop par défaut pour voir si le bloc apparaît. Si c'est le cas, votre thème pourrait nécessiter des ajustements mineurs.

**Q : Le bloc de produits similaires semble étrange ou non stylisé sur mon site.**
R : Il s'agit généralement d'un conflit CSS (style) avec votre thème.

1. **Vider le cache :** Commencez toujours par vider le cache de votre PrestaShop.
2. **Surcharges de thème :** Votre thème peut avoir son propre style pour les listes de produits ou les carrousels qui entrent en conflit. Vous pourriez avoir besoin d'un développeur web pour inspecter le CSS et appliquer des styles personnalisés pour qu'il corresponde au design de votre thème. Le module fournit un style de base, mais les styles de votre thème ont souvent la priorité.

**Q : Puis-je avoir des produits similaires différents pour différents produits principaux ?**
R : Le module « Produits Similaires Gratuit » est conçu pour la simplicité, affichant des produits d'une *seule catégorie choisie* sur toutes les pages produits. Pour des attributions de produits similaires plus avancées et spécifiques aux produits, vous auriez besoin d'un module plus complet (payant).

**Q : Le carrousel ne fonctionne pas ou ne s'affiche pas correctement.**
R :

1. **Vérifier les conflits JavaScript :** Un autre module ou votre thème pourrait avoir un JavaScript conflictuel qui empêche l'initialisation du carrousel. Vérifiez la console de développement de votre navigateur pour les erreurs JavaScript.
2. **Vider le cache :** Encore une fois, videz le cache de votre PrestaShop.
3. **Désactiver et réactiver :** Essayez de désactiver le paramètre « Afficher les produits en carrousel », d'enregistrer, puis de le réactiver et d'enregistrer à nouveau.

**Q : Comment traduire le titre du module (par exemple, « Produits similaires ») dans d'autres langues ?**
R :

1. Allez dans **International > Traductions** dans votre Back Office PrestaShop.
2. Sélectionnez « Traductions des modules installés » pour le « Type de traduction ».
3. Choisissez votre thème (ou « Core » si votre thème n'est pas listé).
4. Sélectionnez la langue que vous souhaitez traduire.
5. Trouvez le module « relatedfree » dans la liste et traduisez les chaînes pertinentes.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique pour les développeurs et les webmasters travaillant avec le module « Produits Similaires Gratuit ».

### 4.1 Vue d'ensemble de l'architecture

Le module « Produits Similaires Gratuit » est un module PrestaShop simple suivant un modèle de type MVC de base dans le cadre du module. Il utilise principalement la méthode `getContent()` de la classe `Module` pour sa configuration Back Office et enregistre un seul hook (`displayFooterProduct` par défaut, mais configurable) pour injecter son template front-office. Il n'introduit pas de contrôleurs personnalisés, d'ObjectModels ou d'actifs JavaScript/CSS complexes au-delà de sa fonctionnalité principale.

### 4.2 Contrôleurs (`controllers/`)

- Ce module ne contient **pas** de contrôleurs Front-Office ou Back-Office personnalisés. Toute la configuration est gérée dans la méthode `getContent()` du fichier de module principal.

### 4.3 Classes et modèles principaux (`classes/`)

- Ce module ne contient **pas** de classes ou d'ObjectModels personnalisés dans le répertoire `classes/`. Toute la logique est encapsulée dans la classe principale `RelatedFree` (définie dans `index.php`).

### 4.4 Actifs JavaScript (`views/js/`)

- Ce module ne contient **pas** de fichiers JavaScript personnalisés. Si l'option carrousel est activée, il s'appuie sur les bibliothèques JavaScript de base de PrestaShop (par exemple, Owl Carousel si disponible dans le thème, ou une simple implémentation personnalisée dans le TPL sinon).

### 4.5 Feuilles de style CSS (`views/css/`)

- Ce module ne contient **pas** de fichiers CSS personnalisés. Le style est censé être géré par le thème ou s'appuie sur des styles/structures en ligne de base que les thèmes stylisent généralement. Les développeurs doivent appliquer un CSS personnalisé pour correspondre à l'esthétique de leur thème.

### 4.6 Structure du template Smarty (`views/templates/`)

- **Templates d'administration (`views/templates/admin/`)** :

  - `views/templates/admin/tabs.tpl` : Ce template est utilisé pour rendre le formulaire de configuration du module dans le Back Office. Il définit la structure des paramètres, y compris les champs de saisie pour la sélection de catégorie, le nombre de produits, la sélection de hook et les commutateurs pour le carrousel et l'ordre aléatoire. Il est rendu par `getContent()` dans `index.php`.
- **Templates de hook (`views/templates/hook/`)** :

  - `views/templates/hook/productFooter.tpl` : C'est le template front-office principal. Il est rendu lorsque le module est accroché (par exemple, `displayFooterProduct`). Ce template contient la structure HTML du bloc de produits similaires, y compris le titre, et itère sur la variable `$products` (passée depuis le module) pour afficher l'image, le nom et le prix de chaque produit similaire. Il contient également la logique pour rendre un carrousel si l'option de configuration correspondante est activée.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :
  Le module ne crée aucune table de base de données personnalisée. Tous les paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide de clés de configuration PrestaShop standard.

  - `PS_RELATEDFREE_CATEGORY` : Stocke l'ID de la catégorie sélectionnée pour les produits similaires.
  - `PS_RELATEDFREE_NUMBER` : Stocke le nombre de produits à afficher.
  - `PS_RELATEDFREE_ONLY_SELECTED` : Stocke un booléen (0/1) pour n'afficher que les produits de la catégorie sélectionnée.
  - `PS_RELATEDFREE_HOOK` : Stocke le nom du hook où le module est affiché.
  - `PS_RELATEDFREE_CAROUSEL` : Stocke un booléen (0/1) pour activer le carrousel.
  - `PS_RELATEDFREE_RANDOM` : Stocke un booléen (0/1) pour afficher les produits dans un ordre aléatoire.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Utilisé pour enregistrer des actifs (bien que ce module ne l'utilise pas pour les actifs). |
| `displayLeftColumn` | Dans la barre latérale gauche des pages qui en ont une. | Emplacement alternatif pour le bloc de produits similaires. |
| `displayRightColumn` | Dans la barre latérale droite des pages qui en ont une. | Emplacement alternatif pour le bloc de produits similaires. |
| `displayFooter` | En bas de chaque page, avant la balise de fermeture `</body>`. | Emplacement alternatif pour le bloc de produits similaires. |
| `displayProductExtraContent` | Dans la zone de contenu principal du produit, souvent dans des onglets (PrestaShop 1.7+). | Emplacement alternatif pour le bloc de produits similaires. |
| `displayFooterProduct` | En bas de la section d'informations sur le produit sur les pages produits. | **Hook principal utilisé par le module** pour afficher les produits similaires. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Produits Similaires Gratuit », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité du module.
