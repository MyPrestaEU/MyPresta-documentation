---
title: "Retour en haut de page - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Retour en haut de page par MyPresta.eu."
sidebar:
  label: "Retour en haut de page - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Scroll to top sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/scroll-to-top.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/scroll-to-top/)
>
> ---


# Retour en haut de page

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après avoir installé le module, naviguez vers **Modules > Gestionnaire de modules** et cliquez sur « Configurer » à côté de « Retour en haut de page ». Cette page vous permet de personnaliser l'apparence et le positionnement du bouton de retour en haut de page.

#### **Positionnement visuel**

- **Ce que fait ce paramètre :** Il s'agit d'une représentation visuelle de l'endroit où le bouton apparaîtra sur votre boutique. Ce n'est pas un paramètre direct mais plutôt une aide visuelle qui change en fonction de vos paramètres « Position X » et « Position Y ».
- **Effet de la modification de ce paramètre :** Lorsque vous ajustez « Position X » et « Position Y », l'aperçu du bouton sur cette page de configuration se déplacera, vous aidant à visualiser son emplacement final sur votre front office.
- **Valeur recommandée :** C'est dynamique.
- **Scénario / exemple pour le marchand :** Si vous voulez que le bouton soit plus proche du coin inférieur droit, vous verrez l'aperçu s'y déplacer lorsque vous ajusterez les valeurs X et Y.

#### **Schéma de couleurs**

- **Ce que fait ce paramètre :** Il contrôle la couleur d'arrière-plan du bouton de retour en haut de page.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur une couleur spécifique (par exemple, #007bff pour le bleu) :* Le bouton s'affichera avec cette couleur d'arrière-plan sur votre front office.
  - *Lorsqu'il est défini sur une couleur différente :* L'arrière-plan du bouton changera en conséquence.
- **Valeur recommandée :** Choisissez une couleur qui complète l'image de marque de votre boutique et qui est clairement visible sur l'arrière-plan de votre site web, mais pas trop distrayante.
- **Scénario / exemple pour le marchand :** Si les couleurs de votre marque sont le bleu et le blanc, vous pouvez définir cette couleur sur une nuance de bleu pour correspondre à votre thème.

#### **Opacité**

- **Ce que fait ce paramètre :** Il détermine la transparence ou l'opacité du bouton de retour en haut de page. Une opacité plus faible le rend plus transparent, permettant au contenu d'arrière-plan de transparaître.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur une valeur élevée (par exemple, 1.0 ou 100 %) :* Le bouton sera entièrement opaque, sans transparence.
  - *Lorsqu'il est défini sur une valeur inférieure (par exemple, 0.7 ou 70 %) :* Le bouton sera semi-transparent, se fondant subtilement avec l'arrière-plan de votre boutique.
- **Valeur recommandée :** Une valeur entre 0.8 et 1.0 (80 %-100 %) est généralement bonne. Trop faible, il pourrait être difficile à voir ; trop élevé, il pourrait sembler trop proéminent.
- **Scénario / exemple pour le marchand :** Si vous voulez que le bouton soit présent mais pas trop dominant, définir l'opacité à 0.8 pourrait être un bon choix.

#### **Position X (depuis la droite)**

- **Ce que fait ce paramètre :** Il contrôle la position horizontale du bouton, spécifiquement sa distance par rapport au bord droit de la fenêtre du navigateur.
- **Effet de la modification de ce paramètre :**
  - *Augmenter la valeur (par exemple, de 20px à 50px) :* Déplace le bouton plus à gauche, loin du bord droit.
  - *Diminuer la valeur (par exemple, de 50px à 20px) :* Déplace le bouton plus près du bord droit.
- **Valeur recommandée :** Commencez avec une valeur comme `20px` ou `30px` pour le maintenir confortablement éloigné du bord sans être trop loin dans la zone de contenu.
- **Scénario / exemple pour le marchand :** Si vous avez un widget de chat ou un autre élément fixe sur le côté droit de votre boutique, vous pouvez augmenter cette valeur à `60px` pour éviter que le bouton de retour en haut de page ne le chevauche.

#### **Position Y (depuis le bas)**

- **Ce que fait ce paramètre :** Il contrôle la position verticale du bouton, spécifiquement sa distance par rapport au bord inférieur de la fenêtre du navigateur.
- **Effet de la modification de ce paramètre :**
  - *Augmenter la valeur (par exemple, de 20px à 50px) :* Déplace le bouton plus vers le haut, loin du bord inférieur.
  - *Diminuer la valeur (par exemple, de 50px à 20px) :* Déplace le bouton plus près du bord inférieur.
- **Valeur recommandée :** Commencez avec une valeur comme `20px` ou `30px` pour le maintenir confortablement éloigné du bord inférieur, au-dessus du pied de page.
- **Scénario / exemple pour le marchand :** Si votre boutique a un pied de page fixe ou une barre de consentement aux cookies tout en bas, vous pouvez augmenter cette valeur à `70px` pour vous assurer que le bouton de retour en haut de page est toujours visible au-dessus de ces éléments.

#### **Tableau de référence rapide de la configuration**

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Positionnement visuel | Dynamique | Aide visuelle pour le placement du bouton basée sur les paramètres X/Y. |
| Configuration du module | Schéma de couleurs | Variable (par exemple, #007bff) | Définit la couleur d'arrière-plan du bouton de retour en haut de page. |
| Configuration du module | Opacité | 0.8 - 1.0 | Contrôle la transparence du bouton (0.0 = entièrement transparent, 1.0 = entièrement opaque). |
| Configuration du module | Position X (depuis la droite) | 20px - 30px | Définit la distance horizontale du bouton par rapport au bord droit de l'écran. |
| Configuration du module | Position Y (depuis le bas) | 20px - 30px | Définit la distance verticale du bouton par rapport au bord inférieur de l'écran. |

## 3. Dépannage pour le marchand et questions fréquemment posées (FAQ)

**Q : Le bouton de retour en haut de page n'apparaît pas sur ma boutique. Que dois-je faire ?**
R :

1.  **Vérifier le statut du module :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que le module « Retour en haut de page » est installé et activé.
2.  **Vider le cache :** PrestaShop utilise la mise en cache. Allez dans **Paramètres avancés > Performances**, faites défiler jusqu'à « Vider le cache » et cliquez sur « Vider le cache ». Ensuite, actualisez votre front office.
3.  **Faire défiler vers le bas :** N'oubliez pas que le bouton n'apparaît que lorsque vous faites défiler la page vers le bas. Assurez-vous d'avoir suffisamment fait défiler pour qu'il devienne visible.
4.  **Vérifier les positions :** Assurez-vous que « Position X » et « Position Y » ne sont pas définies sur des valeurs extrêmement élevées qui pourraient pousser le bouton hors de l'écran. Essayez de les définir à `20px` chacun pour un test.
5.  **Compatibilité du thème :** Bien que rare, certains thèmes très personnalisés peuvent avoir des conflits CSS. Si les étapes ci-dessus ne fonctionnent pas, passez temporairement au thème PrestaShop par défaut (Classic) pour voir si le bouton apparaît. Si c'est le cas, le développeur de votre thème pourrait avoir besoin d'aide.

**Q : Le bouton est visible mais ne défile pas vers le haut lorsqu'on clique dessus.**
R :

1.  **Vérifier JavaScript :** Cela indique généralement un conflit ou une erreur JavaScript. Ouvrez la console de développement de votre navigateur (généralement F12, puis allez dans l'onglet « Console ») et recherchez tout message d'erreur rouge.
2.  **Ordre des modules :** Assurez-vous qu'aucun autre module n'interfère avec la fonctionnalité JavaScript principale.
3.  **Réinstaller :** Essayez de désinstaller et de réinstaller le module. Cela peut parfois résoudre les fichiers corrompus.

**Q : Comment puis-je changer l'icône du bouton (par exemple, d'une flèche à autre chose) ?**
R : Le module utilise une icône de flèche standard. Changer cela nécessite une modification directe des fichiers CSS ou de modèle du module, ce qui relève de la personnalisation du développeur. Ce n'est pas une option disponible dans la configuration du module.

**Q : Le bouton est parfait sur ordinateur de bureau mais est trop grand/petit/mal placé sur mobile.**
R :

1.  **Ajuster X & Y :** Utilisez les paramètres « Position X » et « Position Y » pour affiner son placement spécifiquement pour le mobile. Vous pourriez avoir besoin de valeurs différentes pour éviter les conflits avec les éléments d'interface utilisateur spécifiques aux mobiles.
2.  **Réactivité du thème :** Le CSS du module est conçu pour être réactif, mais la réactivité globale de votre thème peut influencer son apparence. Testez sur des appareils réels ou utilisez les outils de développement de votre navigateur pour simuler différentes tailles d'écran.
3.  **CSS personnalisé (Tâche de développeur) :** Pour des changements de taille ou de style avancés spécifiques au mobile, un webmaster devrait ajouter des règles CSS personnalisées à votre thème, ciblant le bouton uniquement sur les écrans plus petits.

**Q : Ce module ralentira-t-il mon site web ?**
R : Non, le module « Retour en haut de page » est très léger. Il ajoute un minimum de CSS et de JavaScript, qui sont chargés efficacement. Tout impact sur les performances serait négligeable.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs, les webmasters et les agences souhaitant comprendre, déboguer ou étendre le module « Retour en haut de page ».

### 4.1 Aperçu de l'architecture

Le module « Retour en haut de page » est un module PrestaShop simple principalement axé sur l'amélioration de l'interface utilisateur du front-office. Il suit une structure de module PrestaShop classique, tirant parti des hooks pour injecter ses ressources HTML, CSS et JavaScript dans le front-office. Il n'introduit pas de contrôleurs personnalisés ni de modèles de données complexes, s'appuyant plutôt sur le système de configuration de PrestaShop pour ses paramètres. La fonctionnalité principale est gérée côté client via JavaScript.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. La fonctionnalité front-office du module est entièrement gérée par l'injection de ressources et d'un modèle via des hooks.
- **Contrôleurs d'administration Back-Office** : Aucun. Toute la configuration est gérée via la méthode `getContent()` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)

- Aucune classe personnalisée ou définition d'`ObjectModel` n'est présente dans ce module. Toute la logique réside dans le fichier `scrolltop.php` principal.

### 4.4 Ressources JavaScript (`views/js/`)

- **`scrolltop/scrolltop.js`**
  - **Portée :** Front-office.
  - **Responsabilité :** Ce script gère la logique principale côté client pour le bouton de retour en haut de page.
  - **Détails :**
    - Il attend que le DOM soit entièrement chargé (`$(document).ready()`).
    - Il attache un écouteur d'événements à l'événement `$(window).scroll()`.
    - À l'intérieur du gestionnaire d'événements de défilement, il vérifie `$(this).scrollTop()`. Si la position de défilement est supérieure à un certain seuil (par exemple, 100px), il affiche le bouton de retour en haut de page ; sinon, il le masque.
    - Il attache un écouteur d'événements de clic à l'élément du bouton de retour en haut de page.
    - Lorsqu'il est cliqué, il utilise `$('html, body').animate({scrollTop: 0}, 'slow');` pour animer en douceur le défilement de la page vers le haut.
    - Il empêche le comportement de lien par défaut (`return false;`).
  - **Dépendances :** jQuery (qui est généralement disponible dans le front office de PrestaShop).

### 4.5 Feuilles de style CSS (`views/css/`)

- **`scrolltop/scrolltop.css`**
  - **Portée :** Style client du front-office.
  - **Responsabilité :** Définit l'apparence visuelle et le positionnement fixe du bouton de retour en haut de page.
  - **Détails :**
    - Cible l'élément `#scroll-to-top`.
    - Utilise `position: fixed;` pour maintenir le bouton dans une position statique par rapport à la fenêtre d'affichage.
    - Applique les propriétés `bottom` et `right`, définies dynamiquement par la configuration du module, pour contrôler son emplacement exact.
    - Définit `z-index` pour s'assurer que le bouton apparaît au-dessus des autres contenus.
    - Définit `display: none;` initialement, car le JavaScript contrôle sa visibilité.
    - Styles pour `background-color`, `border-radius`, `padding`, `width`, `height`, `line-height`, `text-align`, `color` (pour l'icône de flèche), `font-size` et `cursor`.
    - Inclut une propriété `transition` pour des changements visuels fluides (par exemple, au survol ou lors de l'apparition/disparition).
    - Peut inclure des ajustements réactifs à l'aide de media queries pour optimiser l'apparence sur différentes tailles d'écran.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer :** `#scroll-to-top`, `#scroll-to-top i` (pour l'icône).

### 4.6 Structure du modèle Smarty (`views/templates/`)

- **Modèles de hook (`views/templates/hook/`)** :
  - **`scrolltop/footer.tpl`**
    - **Hook :** `displayFooter` (ou `displayHeader` pour le chargement des ressources).
    - **Objectif :** Ce modèle rend la structure HTML du bouton de retour en haut de page.
    - **Contenu :** Contient généralement une balise `<a>` ou `<div>` avec un ID comme `#scroll-to-top`, et une balise `<i>` (utilisant souvent Font Awesome ou une police d'icônes similaire) pour l'icône de flèche.
    - Il inclut également des attributs de style en ligne ou des attributs de données pour transmettre les valeurs configurées de `color`, `opacity`, `position X` et `position Y` des paramètres du module au CSS ou JavaScript du front-end pour un style dynamique.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Ce module ne crée aucune table SQL personnalisée.
  - Les paramètres de configuration (`st_color`, `st_x`, `st_y`, `st_o`, `mypresta_updates`, `update_`, `updatev_`) sont stockés dans la table `ps_configuration` de PrestaShop.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Utilisé pour enregistrer et charger les ressources CSS (`scrolltop.css`) et JavaScript (`scrolltop.js`) du module. |
| `displayFooter` | À la fin de la section `<body>` de chaque page du front-office, juste avant la balise de fermeture `</body>`. | Utilisé pour rendre la structure HTML du bouton de retour en haut de page (`footer.tpl`). Cela garantit que le HTML du bouton est présent dans le DOM pour que le JavaScript puisse le manipuler. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et les dernières versions du module « Retour en haut de page », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité et la compatibilité du module.
