---
title: "Sticky Cart Bar FREE - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Sticky Cart Bar FREE par MyPresta.eu."
sidebar:
  label: "Sticky Cart Bar FREE - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Sticky Cart Bar FREE sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/sticky-cart-bar-free.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/sticky-cart-bar-free/)
>
> ---


# Sticky Cart Bar FREE

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Sticky Cart Bar FREE)

C'est l'écran de configuration principal où vous contrôlez le comportement et l'apparence de la barre de panier collante sur vos pages produits.

#### **Activer la barre de panier collante**

- **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité de la barre de panier collante pour votre boutique.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'activé (OUI) :* La barre de panier collante apparaîtra sur les pages produits selon vos autres paramètres lorsque les clients feront défiler la page au-delà du bouton principal "Ajouter au panier".
  - *Lorsqu'il est désactivé (NON) :* La barre de panier collante n'apparaîtra sur aucune page produit, désactivant ainsi le module.
- **Valeur recommandée :** OUI (pour utiliser les avantages du module).
- **Scénario / exemple de marchand :** Si vous testez le module ou souhaitez le désactiver temporairement sans le désinstaller, définissez-le sur NON. Pour un fonctionnement en direct, il doit être sur OUI.

#### **Position de la barre de panier collante**

- **Ce que fait ce paramètre :** Détermine où la barre collante "collera" sur l'écran du client – soit en haut, soit en bas.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur "Haut" :* La barre collante apparaîtra tout en haut de la fenêtre du navigateur, sous l'en-tête.
  - *Lorsqu'il est défini sur "Bas" :* La barre collante apparaîtra tout en bas de la fenêtre du navigateur, au-dessus du pied de page.
- **Valeur recommandée :** "Bas" (souvent moins intrusive, car elle ne couvre pas la navigation principale ou le logo). Cependant, "Haut" peut être plus proéminent. Testez les deux pour voir ce qui fonctionne le mieux pour votre thème et votre public.
- **Scénario / exemple de marchand :** Si votre boutique a un en-tête très chargé ou un menu fixe en haut, placer la barre collante en "Bas" pourrait éviter l'encombrement visuel. Si vous souhaitez une visibilité maximale pour le bouton "Ajouter au panier", "Haut" pourrait être préféré.

#### **Afficher sur les appareils mobiles**

- **Ce que fait ce paramètre :** Contrôle si la barre de panier collante est affichée aux clients naviguant sur votre boutique depuis des smartphones ou d'autres appareils mobiles.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'activé (OUI) :* La barre de panier collante sera active et visible sur les pages produits mobiles.
  - *Lorsqu'il est désactivé (NON) :* La barre de panier collante n'apparaîtra pas sur les appareils mobiles, uniquement sur les ordinateurs de bureau/tablettes.
- **Valeur recommandée :** OUI (Les utilisateurs mobiles défilent beaucoup, et cette fonctionnalité leur est très bénéfique).
- **Scénario / exemple de marchand :** Compte tenu de l'espace d'écran limité sur mobile, garder le bouton "Ajouter au panier" visible est encore plus critique. Ne le désactivez que si vous rencontrez des conflits de mise en page spécifiques avec votre thème mobile.

#### **Afficher sur les appareils de bureau**

- **Ce que fait ce paramètre :** Contrôle si la barre de panier collante est affichée aux clients naviguant sur votre boutique depuis des ordinateurs de bureau ou des écrans de tablette plus grands.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'activé (OUI) :* La barre de panier collante sera active et visible sur les pages produits de bureau.
  - *Lorsqu'il est désactivé (NON) :* La barre de panier collante n'apparaîtra pas sur les appareils de bureau, uniquement sur mobile (si activé).
- **Valeur recommandée :** OUI (Même sur ordinateur de bureau, les pages produits longues bénéficient de cette fonctionnalité).
- **Scénario / exemple de marchand :** La plupart des boutiques voudront que cela soit activé pour tous les types d'appareils afin de maximiser le potentiel de conversion.

#### **Masquer le bouton "Ajouter au panier" original**

- **Ce que fait ce paramètre :** Cette option vous permet de masquer le bouton "Ajouter au panier" original sur la page produit une fois que la barre collante apparaît.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'activé (OUI) :* Lorsque la barre collante est visible, le bouton "Ajouter au panier" original sur la page produit sera masqué. Cela peut réduire la redondance visuelle.
  - *Lorsqu'il est désactivé (NON) :* Le bouton "Ajouter au panier" de la barre collante et le bouton "Ajouter au panier" original seront visibles simultanément (lorsque l'original est en vue).
- **Valeur recommandée :** NON (Généralement, il est plus sûr de garder le bouton original visible s'il est dans la fenêtre d'affichage, car certains clients pourraient le préférer. Le masquer pourrait causer de la confusion si la barre collante disparaît rapidement).
- **Scénario / exemple de marchand :** Si vous trouvez les doubles boutons "Ajouter au panier" visuellement distrayants ou déroutants lorsque la barre collante est active, vous pouvez activer cette option. Sinon, laissez-la désactivée.

#### **Compatibilité du thème**

- **Ce que fait ce paramètre :** Ce paramètre aide le module à adapter son style et son comportement aux différents thèmes PrestaShop, en particulier Classic et Hummingbird (le thème par défaut de PrestaShop 8+).
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur "Classic" :* Le module chargera le CSS et le JavaScript optimisés pour le thème PrestaShop Classic et les thèmes basés sur celui-ci.
  - *Lorsqu'il est défini sur "Hummingbird" :* Le module chargera le CSS et le JavaScript optimisés pour le thème PrestaShop Hummingbird (par défaut de PrestaShop 8.x et 9.x) et les thèmes basés sur celui-ci.
- **Valeur recommandée :** Sélectionnez le thème que votre boutique utilise actuellement. Si vous êtes sur PrestaShop 8.x ou 9.x, il s'agit probablement de "Hummingbird". Si vous êtes sur PrestaShop 1.7.x et utilisez le thème par défaut, il s'agit de "Classic". Si vous utilisez un thème personnalisé, essayez les deux pour voir lequel s'intègre le mieux.
- **Scénario / exemple de marchand :** Si votre boutique est sur PrestaShop 8.1 et que vous sélectionnez "Classic", la barre collante pourrait ne pas s'afficher ou fonctionner correctement. Faites toujours correspondre cela à votre thème actif.

#### **Aperçu de la version Pro**

- **Ce que fait ce paramètre :** Cette section est une zone promotionnelle pour le module "Sticky Cart Bar PRO", offrant des fonctionnalités avancées non disponibles dans la version GRATUITE. Elle n'affecte pas la fonctionnalité du module GRATUIT.
- **Effet de la modification de ce paramètre :** Aucun effet direct sur le comportement du module GRATUIT. Il fournit des informations sur la mise à niveau.
- **Valeur recommandée :** N/A (Informative uniquement).
- **Scénario / exemple de marchand :** Si vous trouvez le module GRATUIT bénéfique et avez besoin de plus de contrôle sur le ciblage, la conception ou les exclusions de produits spécifiques, vous pouvez consulter les fonctionnalités de la version PRO ici.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer la barre de panier collante | OUI | Interrupteur principal du module. OUI active la barre collante. |
| Configuration du module | Position de la barre de panier collante | Bas | Détermine si la barre reste en haut ou en bas de l'écran. |
| Configuration du module | Afficher sur les appareils mobiles | OUI | Contrôle la visibilité sur les smartphones/tablettes. OUI est recommandé. |
| Configuration du module | Afficher sur les appareils de bureau | OUI | Contrôle la visibilité sur les ordinateurs de bureau. OUI est recommandé. |
| Configuration du module | Masquer le bouton "Ajouter au panier" original | NON | Masque le bouton original lorsque la barre collante est active. NON est généralement plus sûr. |
| Configuration du module | Compatibilité du thème | Hummingbird (pour PS 8/9) | Assure un style et une fonctionnalité corrects pour votre thème actif. Faites correspondre votre thème. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : La barre de panier collante n'apparaît pas sur mes pages produits.**
R :

- **Vérifiez "Activer la barre de panier collante"** : Assurez-vous que ce paramètre est défini sur OUI dans la configuration du module.
- **Vérifiez "Compatibilité du thème"** : Assurez-vous d'avoir sélectionné le thème correct (Classic ou Hummingbird) qui correspond au thème actif de votre boutique. Une sélection incorrecte peut empêcher le chargement de la barre.
- **Videz le cache** : Allez dans **Paramètres avancés > Performances** dans votre back office PrestaShop et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions antérieures). Parfois, d'anciens fichiers de cache empêchent l'affichage des modifications du nouveau module.
- **Faites défiler au-delà du bouton original** : N'oubliez pas que la barre n'apparaît que lorsque vous faites défiler au-delà du bouton "Ajouter au panier" original. Assurez-vous de faire défiler suffisamment la page.
- **Vérifiez les paramètres de l'appareil** : Assurez-vous que "Afficher sur les appareils mobiles" et/ou "Afficher sur les appareils de bureau" sont activés pour l'appareil sur lequel vous testez.

**Q2 : La barre de panier collante semble étrange ou mal alignée avec mon thème personnalisé.**
R :

- **Compatibilité du thème** : Vérifiez à nouveau que vous avez sélectionné la bonne option de "Compatibilité du thème" dans les paramètres du module. Si vous avez un thème très personnalisé, il pourrait se comporter différemment. Essayez de basculer entre "Classic" et "Hummingbird" pour voir si l'un fonctionne mieux.
- **CSS personnalisé (développeur nécessaire)** : Si le problème persiste, votre thème personnalisé pourrait avoir des styles CSS conflictuels. Un développeur web peut inspecter la page à l'aide des outils de développement du navigateur et écrire quelques lignes de CSS personnalisé pour ajuster l'apparence de la barre collante. Cela implique généralement de remplacer les styles existants dans le fichier `custom.css` de votre thème.

**Q3 : Le bouton "Ajouter au panier" de la barre collante ne fonctionne pas.**
R :

- **Videz le cache** : Comme pour les problèmes d'affichage, vider le cache de votre PrestaShop (**Paramètres avancés > Performances**) peut résoudre les problèmes liés à JavaScript.
- **Compatibilité du thème** : Assurez-vous que le thème correct est sélectionné. Le JavaScript pourrait ne pas s'initialiser correctement si le mauvais thème est choisi.
- **Erreurs de la console du navigateur (développeur nécessaire)** : Demandez à votre développeur web de vérifier la console JavaScript du navigateur pour toute erreur. Les conflits avec d'autres modules ou le JavaScript du thème peuvent parfois empêcher le bouton de fonctionner.

**Q4 : Puis-je personnaliser les couleurs ou le contenu de la barre collante ?**
R :

- La version GRATUITE du module offre des options de style limitées (principalement l'adaptation à votre thème). Pour une personnalisation avancée comme le changement de couleurs, de polices, l'ajout de texte personnalisé ou un contrôle plus granulaire sur les informations affichées, vous devrez généralement passer au module **Sticky Cart Bar PRO**.
- Pour des ajustements visuels mineurs dans la version GRATUITE, un développeur web peut utiliser du CSS personnalisé pour remplacer les styles par défaut.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module Sticky Cart Bar FREE suit une architecture de module PrestaShop standard, exploitant principalement la classe `Module` pour l'installation, la désinstallation et la configuration. Il s'intègre au front-office via des hooks, injectant dynamiquement une barre collante basée sur le comportement de défilement de l'utilisateur. Le module utilise une combinaison de templates Smarty pour la structure, de CSS pour le style et de JavaScript pour la fonctionnalité collante et l'interaction avec le bouton principal "Ajouter au panier". La compatibilité avec différents thèmes PrestaShop (Classic vs Hummingbird) est gérée en chargeant des ressources spécifiques au thème.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la configuration est gérée via la méthode `getContent()` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)

- `stickycartbarfree/classes/index.php` :
  - **Description** : Il s'agit généralement d'un fichier vide utilisé pour empêcher l'affichage du contenu du répertoire, une pratique de sécurité courante dans les modules PrestaShop. Il ne contient aucun code fonctionnel.
- `stickycartbarfree/classes/ScbfCompatibility.php` :
  - **Nom de la classe** : `ScbfCompatibility`
  - **Classe parente** : Aucune (classe utilitaire autonome)
  - **Responsabilité** : Cette classe contient probablement des méthodes d'aide statiques pour gérer les différences de compatibilité entre les différentes versions ou thèmes de PrestaShop. Elle pourrait abstraire les différences dans la manière dont les données de produit sont récupérées ou dont les ressources sont enregistrées, garantissant que le module fonctionne dans les environnements pris en charge. Elle n'interagit pas directement avec une table de base de données spécifique mais pourrait interroger `ps_configuration` pour des informations sur le thème.
  - **Méthodes publiques clés** : Probablement des méthodes statiques pour vérifier le contexte du thème, la version de PrestaShop ou récupérer les valeurs de configuration de manière compatible.

### 4.4 Ressources JavaScript (`views/js/`)

- `stickycartbarfree/views/js/front.js` :
  - **Portée** : Front-office.
  - **Description** : Il s'agit du fichier JavaScript principal responsable du comportement collant de la barre de panier.
  - **Fonctionnalité** :
    - **Écouteurs d'événements** : Se lie à l'événement `scroll` sur la fenêtre pour détecter quand l'utilisateur fait défiler.
    - **Manipulation du DOM** :
      - Calcule la position du bouton "Ajouter au panier" original (sélecteur `#add_to_cart` ou similaire).
      - Surveille la position de défilement par rapport au bouton original.
      - Ajoute/supprime une classe CSS (par exemple, `is-visible`) au conteneur de la barre de panier collante (`#sticky-cart-bar`) pour l'afficher ou la masquer.
      - Masque potentiellement le bouton "Ajouter au panier" original si le paramètre de module correspondant est activé.
    - **Interaction** : Gère les clics sur le bouton "Ajouter au panier" dans la barre collante, imitant probablement le comportement du bouton original (par exemple, soumettre le formulaire produit, effectuer un appel AJAX pour ajouter au panier).
    - **Réactivité** : Peut inclure une logique pour réévaluer les positions lors des événements `resize`.
    - **Événements PrestaShop** : Utilise probablement `prestashop.on('updateProduct', ...)` ou des événements similaires pour mettre à jour le contenu de la barre collante (prix, quantité, attributs) lorsque les options du produit sont modifiées sur la page.

### 4.5 Feuilles de style CSS (`views/css/`)

- `stickycartbarfree/views/css/admin-config.css` :
  - **Portée** : Style du formulaire d'administration du Back-office.
  - **Description** : Contient des styles spécifiquement pour la page de configuration du module dans le back office de PrestaShop, garantissant une interface d'administration cohérente et conviviale.
  - **Composants d'interface utilisateur principaux** : Style les éléments de formulaire, les étiquettes, les boutons et potentiellement des éléments de mise en page spécifiques dans la sortie de `getContent()`.
- `stickycartbarfree/views/css/admin-pro-teaser.css` :
  - **Portée** : Style du formulaire d'administration du Back-office.
  - **Description** : Styles pour le contenu promotionnel lié à la version PRO du module affiché sur la page de configuration.
  - **Composants d'interface utilisateur principaux** : Style les boîtes d'aperçu, les boutons de mise à niveau, les listes de fonctionnalités et les images d'aperçu pour la version PRO.
- `stickycartbarfree/views/css/front-classic.css` :
  - **Portée** : Style client Front-office (thème Classic).
  - **Description** : Fournit des ajustements de style spécifiques pour la barre de panier collante lorsque l'option de compatibilité de thème "Classic" est sélectionnée. Cela garantit que la barre s'intègre visuellement à la conception du thème Classic.
  - **Sélecteurs de classe CSS clés** : Cible les éléments dans `sticky-cart-bar` pour correspondre aux polices, couleurs, espacements et styles de boutons du thème Classic.
- `stickycartbarfree/views/css/front-hummingbird.css` :
  - **Portée** : Style client Front-office (thème Hummingbird).
  - **Description** : Fournit des ajustements de style spécifiques pour la barre de panier collante lorsque l'option de compatibilité de thème "Hummingbird" est sélectionnée. Cela garantit que la barre s'intègre visuellement au thème par défaut de PrestaShop 8.x/9.x.
  - **Sélecteurs de classe CSS clés** : Cible les éléments dans `sticky-cart-bar` pour correspondre aux polices, couleurs, espacements et styles de boutons du thème Hummingbird.
- `stickycartbarfree/views/css/front.css` :
  - **Portée** : Style client Front-office (général).
  - **Description** : Contient les styles de base, communs pour la barre de panier collante qui s'appliquent quelle que soit la compatibilité de thème sélectionnée. Cela inclut le positionnement de base, la visibilité et la réactivité.
  - **Sélecteurs de classe CSS clés** : Définit les propriétés de `#sticky-cart-bar` comme `position: fixed`, `z-index`, `width`, `padding`, `background-color` et les requêtes média réactives.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :

  - `stickycartbarfree/views/templates/hook/sticky-cart-bar-classic.tpl` : Rendu lorsque la compatibilité de thème "Classic" est sélectionnée. Contient la structure principale de la barre collante, adaptée aux attentes HTML et CSS du thème Classic.
  - `stickycartbarfree/views/templates/hook/sticky-cart-bar-hummingbird.tpl` : Rendu lorsque la compatibilité de thème "Hummingbird" est sélectionnée. Contient la structure principale de la barre collante, adaptée aux attentes HTML et CSS du thème Hummingbird.
  - `stickycartbarfree/views/templates/hook/sticky-cart-bar-inner.tpl` : Ce template contient probablement le contenu principal de la barre collante (nom du produit, prix, champ de quantité, bouton ajouter au panier). Il est probablement inclus par `sticky-cart-bar-classic.tpl` et `sticky-cart-bar-hummingbird.tpl` pour éviter la duplication de code.
  - `stickycartbarfree/views/templates/hook/sticky-cart-bar.tpl` : Il pourrait s'agir d'un template enveloppant ou d'un fallback, ou il pourrait être le point d'entrée principal qui inclut conditionnellement `sticky-cart-bar-classic.tpl` ou `sticky-cart-bar-hummingbird.tpl` en fonction de la configuration.
  - **Objectif** : Ces templates sont généralement hookés dans `displayFooter` ou `displayBeforeBodyClosingTag` pour s'assurer que le HTML de la barre collante est présent sur les pages produits. Ils génèrent la structure HTML de la barre collante, remplie avec les données produit passées depuis le module.
- **Templates d'administration (`views/templates/admin/`)** :

  - `stickycartbarfree/views/templates/admin/configure.tpl` : C'est le template principal de la page de configuration du module dans le Back Office. Il rend tous les paramètres, champs de saisie et options définis dans la méthode `getContent()` du module.
  - `stickycartbarfree/views/templates/admin/pro-teaser-intro.tpl` : Rend la partie introductive de l'aperçu de la version PRO sur la page de configuration.
  - `stickycartbarfree/views/templates/admin/pro-teaser-preview.tpl` : Rend un aperçu ou une représentation visuelle des fonctionnalités de la version PRO.
  - `stickycartbarfree/views/templates/admin/pro-teaser.tpl` : Le template principal de la section d'aperçu de la version PRO, incluant probablement les templates d'introduction et d'aperçu.
  - **Objectif** : Ces templates fournissent l'interface utilisateur pour les paramètres du module et le contenu promotionnel dans le Back Office de PrestaShop.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** :

  - Ce module ne crée aucune table SQL personnalisée.
  - Les paramètres de configuration sont stockés dans la table standard `ps_configuration` de PrestaShop, avec des clés généralement préfixées par `SCBF_` (par exemple, `SCBF_ENABLE`, `SCBF_POSITION`).
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Utilisé pour enregistrer les ressources CSS et JavaScript (`front.js`, `front.css`, CSS spécifiques au thème) pour le front-office. |
| `displayFooter` | Avant la balise `</body>` fermante de chaque page. | Utilisé pour injecter la structure HTML principale de la barre de panier collante (`sticky-cart-bar.tpl` ou ses variantes) dans la page. |
| `actionFrontControllerSetMedia` | Après que les médias (CSS/JS) ont été définis par le contrôleur frontal. | Hook alternatif pour l'enregistrement des ressources, garantissant qu'elles sont chargées correctement. |
| `actionProductUpdate` | Après la mise à jour d'un produit dans le back office. | (Probablement non utilisé dans la version GRATUITE, mais courant pour les modules qui doivent vider le cache ou réindexer les données produit). |
| `actionCartUpdateQuantity` | Lorsqu'une quantité de produit est mise à jour dans le panier. | (Probablement non utilisé dans la version GRATUITE, mais pourrait être utilisé pour mettre à jour le sélecteur de quantité de la barre collante s'il était plus interactif). |
| `actionAjaxDieProduct` | Lorsqu'une requête AJAX liée aux données produit échoue. | (Pourrait être utilisé pour le débogage ou des interactions AJAX spécifiques). |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour explorer les fonctionnalités avancées disponibles dans la version PRO du module, veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant le module Sticky Cart Bar FREE.
