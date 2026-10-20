---
title: "Pied de page avancé - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Pied de page avancé par MyPresta.eu."
sidebar:
  label: "Pied de page avancé - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Advanced Footer sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/advanced-footer.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/advanced-footer/)
>
> ---


# Pied de page avancé

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune exigence de serveur inhabituelle.

## 2. Parcours complet de configuration (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran principal où vous définirez l'apparence de votre pied de page avancé.

- **Emplacement du menu :** Back Office > Modules > Gestionnaire de modules > Recherchez "Pied de page avancé" > Cliquez sur "Configurer".

#### **Paramètres et options :**

1.  **Largeur du pied de page (`advf_f_width`)**

    *   **Ce que fait ce paramètre :** Il contrôle la largeur globale de votre zone de pied de page personnalisée. Vous pouvez le définir sur une valeur en pixels fixe ou un pourcentage.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur une valeur en pixels fixe (par exemple, `1200px`) :* Le pied de page aura toujours cette largeur exacte, centré sur la page. Sur des écrans très larges, il peut y avoir un espace vide sur les côtés. Sur des écrans plus étroits, il peut introduire des barres de défilement horizontales si la valeur est trop grande.
        *   *Lorsqu'il est défini sur un pourcentage (par exemple, `100%`) :* Le pied de page s'étirera pour remplir la largeur disponible de l'écran, s'adaptant dynamiquement. Ceci est généralement recommandé pour les designs réactifs.
    *   **Valeur recommandée :** `100%` pour un pied de page pleine largeur et réactif, ou `1200px` si la zone de contenu principale de votre boutique a une largeur fixe et que vous souhaitez que le pied de page corresponde.
    *   **Scénario / exemple pour le marchand :** Si la zone de contenu principale de votre boutique a une largeur de 1200px, définir la largeur du pied de page à `1200px` le fera s'aligner parfaitement, créant un design cohérent. Si vous voulez que le pied de page s'étende toujours sur toute la fenêtre du navigateur, `100%` est la solution.
2.  **Hauteur du pied de page (`advf_f_height`)**

    *   **Ce que fait ce paramètre :** Il définit la hauteur minimale de votre zone de pied de page. Si votre contenu est plus haut que cela, le pied de page s'étendra automatiquement.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur une valeur en pixels spécifique (par exemple, `280px`) :* Le pied de page aura toujours au moins cette hauteur. Cela peut être utile pour maintenir une présence visuelle cohérente même si certaines pages ont moins de contenu de pied de page.
        *   *Lorsqu'il est laissé vide ou défini sur `auto` (si disponible) :* La hauteur du pied de page sera déterminée uniquement par son contenu.
    *   **Valeur recommandée :** `280px` ou `300px` est un bon point de départ pour donner à votre pied de page une présence substantielle. Vous pouvez ajuster cela en fonction de la quantité de contenu que vous prévoyez d'y mettre.
    *   **Scénario / exemple pour le marchand :** Vous voulez que votre pied de page occupe toujours un espace notable en bas de la page, même si vous n'avez que quelques liens. Définir une hauteur minimale garantit qu'il ne semble pas trop fin.
3.  **Couleur de fond du pied de page (`advf_f_bg`)**

    *   **Ce que fait ce paramètre :** Il vous permet de choisir une couleur de fond unie pour toute votre zone de pied de page.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur une couleur (par exemple, `#333333` pour le gris foncé) :* L'arrière-plan du pied de page affichera cette couleur.
        *   *Lorsqu'il est laissé vide :* Le pied de page peut hériter d'un arrière-plan de votre thème ou être transparent.
    *   **Valeur recommandée :** Une couleur qui complète l'image de marque de votre boutique. Les couleurs plus foncées (comme le gris foncé ou le noir) sont courantes pour les pieds de page, mais une couleur plus claire peut également fonctionner selon votre design.
    *   **Scénario / exemple pour le marchand :** Votre marque utilise une nuance spécifique de bleu. Vous pouvez définir l'arrière-plan du pied de page sur ce bleu pour renforcer votre identité de marque.
4.  **Couleur du texte du pied de page (`advf_f_color`)**

    *   **Ce que fait ce paramètre :** Il définit la couleur par défaut de tout le texte de votre pied de page, y compris les liens.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur une couleur (par exemple, `#ffffff` pour le blanc) :* Tout le texte du pied de page apparaîtra dans cette couleur.
        *   *Lorsqu'il est laissé vide :* La couleur du texte peut hériter des paramètres par défaut de votre thème, ce qui pourrait ne pas être lisible sur l'arrière-plan de pied de page choisi.
    *   **Valeur recommandée :** Une couleur qui offre un bon contraste avec la `Couleur de fond du pied de page` choisie. Si votre arrière-plan est foncé, choisissez une couleur de texte claire (par exemple, blanc, gris clair). Si votre arrière-plan est clair, choisissez une couleur de texte foncée.
    *   **Scénario / exemple pour le marchand :** Vous avez un arrière-plan de pied de page gris foncé. Définir la couleur du texte en blanc (`#ffffff`) garantit que tous vos liens et informations sont facilement lisibles.
5.  **Couleur de survol des liens du pied de page (`advf_f_color_hover`)**

    *   **Ce que fait ce paramètre :** Il définit la couleur que les liens de votre pied de page prendront lorsqu'un client passe sa souris dessus.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur une couleur (par exemple, `#cccccc` pour le gris clair) :* Les liens changeront visuellement à cette couleur au survol, fournissant un retour à l'utilisateur que l'élément est interactif.
        *   *Lorsqu'il est laissé vide :* Les liens peuvent ne pas avoir d'effet de survol, ou ils peuvent hériter d'une couleur de survol par défaut de votre thème, qui pourrait ne pas correspondre à votre design de pied de page.
    *   **Valeur recommandée :** Une nuance légèrement différente de votre `Couleur du texte du pied de page` ou une couleur d'accent de la palette de votre marque. Elle doit être perceptible mais pas choquante.
    *   **Scénario / exemple pour le marchand :** Vos liens de pied de page sont blancs. Définir la couleur de survol sur un bleu clair (`#ADD8E6`) offre une interaction subtile et de marque lorsque les clients passent leur souris dessus.
6.  **URL de l'image de fond du pied de page (`advf_f_bg_url`)**

    *   **Ce que fait ce paramètre :** Vous permet d'utiliser une image comme arrière-plan pour votre pied de page au lieu ou en plus d'une couleur unie. Vous devez fournir l'URL complète de l'image.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'une URL valide est fournie :* L'image apparaîtra comme arrière-plan du pied de page. La `Couleur de fond du pied de page` transparaîtra si l'image est transparente ou si l'image ne couvre pas tout le pied de page.
        *   *Lorsqu'il est laissé vide :* Aucune image de fond ne sera utilisée.
    *   **Valeur recommandée :** Laissez vide sauf si vous avez une image de fond spécifique et optimisée. Si utilisée, assurez-vous que l'image est légère et pertinente.
    *   **Scénario / exemple pour le marchand :** Vous avez une image de texture subtile que vous souhaitez utiliser comme arrière-plan pour votre pied de page afin d'ajouter de la profondeur visuelle. Vous téléchargeriez cette image sur votre serveur et colleriez son URL ici.
7.  **Position de l'image de fond du pied de page (`advf_f_bg_pos`)**

    *   **Ce que fait ce paramètre :** Contrôle la façon dont une image de fond (si définie) est positionnée dans la zone du pied de page. Les valeurs courantes incluent `center center`, `top left`, `bottom right`, etc.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur `center center` :* L'image sera centrée horizontalement et verticalement.
        *   *Lorsqu'il est défini sur `top left` :* L'image commencera à partir du coin supérieur gauche.
    *   **Valeur recommandée :** `center center` pour la plupart des images, ou `top left` si votre image est un motif destiné à commencer à partir du coin.
    *   **Scénario / exemple pour le marchand :** Votre image de fond est un petit logo que vous souhaitez voir apparaître une fois au centre du pied de page. Vous le définiriez sur `center center`.
8.  **Répétition de l'image de fond du pied de page (`advf_f_bg_repeat`)**

    *   **Ce que fait ce paramètre :** Détermine si et comment une image de fond (si définie) doit se répéter pour remplir la zone du pied de page.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur `repeat` :* L'image se répétera horizontalement et verticalement.
        *   *Lorsqu'il est défini sur `no-repeat` :* L'image n'apparaîtra qu'une seule fois.
        *   *Lorsqu'il est défini sur `repeat-x` :* L'image se répétera uniquement horizontalement.
        *   *Lorsqu'il est défini sur `repeat-y` :* L'image se répétera uniquement verticalement.
    *   **Valeur recommandée :** `no-repeat` pour les images uniques (comme un logo), ou `repeat` si votre image est un petit motif conçu pour se répéter.
    *   **Scénario / exemple pour le marchand :** Vous avez une petite image de motif sans couture. Définir ceci sur `repeat` la fera couvrir toute la zone du pied de page avec ce motif. S'il s'agit d'un seul élément décoratif, `no-repeat` est préférable.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Largeur du pied de page (`advf_f_width`) | `100%` | Définit la largeur globale du pied de page. `100%` pour une pleine largeur réactive, `1200px` pour une largeur fixe. |
| Configuration du module | Hauteur du pied de page (`advf_f_height`) | `280px` | Définit la hauteur minimale du pied de page. Assure une présence visuelle cohérente. |
| Configuration du module | Couleur de fond du pied de page (`advf_f_bg`) | (Couleur de votre marque) | Définit la couleur de fond unie du pied de page. Crucial pour l'image de marque et le contraste. |
| Configuration du module | Couleur du texte du pied de page (`advf_f_color`) | (Couleur contrastante) | Définit la couleur de texte par défaut dans le pied de page. Assure la lisibilité par rapport à l'arrière-plan. |
| Configuration du module | Couleur de survol des liens du pied de page (`advf_f_color_hover`) | (Accent subtil) | Définit la couleur des liens au survol. Améliore le retour d'interaction utilisateur. |
| Configuration du module | URL de l'image de fond du pied de page (`advf_f_bg_url`) | Laisser vide | URL d'une image à utiliser comme arrière-plan du pied de page. Ajoute une texture visuelle ou une image de marque. |
| Configuration du module | Position de l'image de fond du pied de page (`advf_f_bg_pos`) | `center center` | Comment l'image de fond est positionnée. `center center` pour la plupart des images uniques. |
| Configuration du module | Répétition de l'image de fond du pied de page (`advf_f_bg_repeat`) | `no-repeat` | Comment l'image de fond se répète. `no-repeat` pour les images uniques, `repeat` pour les motifs. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes modifications de pied de page n'apparaissent pas sur le front office.**
**R1 :** Il s'agit généralement d'un problème de cache.
\* Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop.
\* Cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions plus anciennes).
\* Si vous utilisez un module de mise en cache tiers ou une mise en cache au niveau du serveur (comme Varnish), videz également ces caches.
\* Essayez également de vider le cache de votre navigateur (Ctrl+F5 ou Cmd+Maj+R).

**Q2 : Le pied de page semble différent sur les appareils mobiles que sur les ordinateurs de bureau.**
**R2 :** C'est normal et généralement une bonne chose ! Les thèmes PrestaShop modernes sont réactifs, ce qui signifie qu'ils adaptent la mise en page aux différentes tailles d'écran. Les paramètres du module (comme `Largeur du pied de page : 100%`) sont conçus pour fonctionner avec cela. Si des éléments spécifiques semblent cassés, il peut s'agir d'un conflit avec le CSS de votre thème.
\* **Dépannage :** Vérifiez le CSS spécifique aux mobiles de votre thème. Si vous avez ajouté du contenu HTML personnalisé au pied de page, assurez-vous que ce contenu est également réactif. Vous pourriez avoir besoin d'un webmaster pour inspecter le CSS.

**Q3 : Comment ajouter du contenu réel (liens, texte, images) à ce pied de page avancé ?**
**R3 :** Ce module fournit principalement le cadre de *style* (arrière-plan, couleurs, dimensions) pour votre pied de page. Le *contenu* du pied de page est généralement géré par les hooks de pied de page de votre thème PrestaShop (comme `displayFooter`) ou par d'autres modules conçus pour les blocs de contenu (par exemple, un module de bloc HTML personnalisé, ou le module Liste de liens intégré de PrestaShop).
\* **Solution :** Après avoir configuré le style du pied de page avancé, vous devrez utiliser les options de votre thème ou d'autres modules de contenu pour remplir le hook `displayFooter` avec les liens, le texte et les images souhaités. Le module Pied de page avancé appliquera ensuite son style à ce contenu.

**Q4 : Les couleurs que j'ai définies ne semblent pas être appliquées à tous les éléments de mon pied de page.**
**R4 :** Cela peut arriver si votre thème a des règles CSS très spécifiques qui remplacent les styles du module.
\* **Dépannage :** Le module applique un style général au pied de page. Si votre thème a des règles plus spécifiques (par exemple, pour `ul li a` à l'intérieur du pied de page), celles-ci pourraient avoir la priorité. Vous pourriez avoir besoin de consulter un webmaster pour ajouter du CSS personnalisé à votre thème afin de remplacer des éléments spécifiques, ou d'ajuster les paramètres de votre thème s'il dispose d'une section de personnalisation de pied de page dédiée.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module Pied de page avancé est un module PrestaShop standard principalement axé sur le style du front-office. Il exploite le système de configuration de PrestaShop (`Configuration::updateValue`) pour stocker ses paramètres et s'accroche à `displayFooter` pour injecter son CSS et son JavaScript personnalisés. Il n'introduit pas de nouvelles tables de base de données ou d'ObjectModels complexes, ce qui le rend léger et axé sur sa tâche principale : la personnalisation du pied de page. Le module utilise une méthode `getContent()` pour sa configuration back-office, rendant un formulaire PrestaShop standard.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Aucun. Le module s'accroche directement à `displayFooter` et `footer` pour rendre son contenu et appliquer les styles.
-   **Contrôleurs d'administration Back-Office** : Aucun. Toute la configuration est gérée dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles de base (`classes/`)

-   Aucune classe ou ObjetModèle personnalisé n'est défini dans le répertoire `classes/`. Toute la logique est contenue dans le fichier principal du module `advfooter.php`.

### 4.4 Actifs JavaScript (`views/js/`)

-   `advfooter/js/advajax.js` :
    *   **Portée :** Back-office.
    *   **Responsabilité :** Gère probablement les requêtes AJAX liées à la sauvegarde des paramètres de configuration du module sans rechargement complet de la page, ou fournit un retour dynamique dans le formulaire de configuration.
-   `advfooter/js/foscript.js` :
    *   **Portée :** Front-office.
    *   **Responsabilité :** Ce script contiendrait toute logique côté client ou comportement dynamique spécifique au pied de page avancé côté client. Cela pourrait inclure des ajustements réactifs, des effets de survol spécifiques non gérés par CSS, ou des interactions avec du contenu intégré.
-   `advfooter/js/jscolor/jscolor.js` :
    *   **Portée :** Back-office.
    *   **Responsabilité :** Il s'agit d'une bibliothèque JavaScript tierce pour fournir un widget de sélecteur de couleurs dans le Back Office. Elle est utilisée pour permettre aux marchands de sélectionner visuellement les couleurs pour l'arrière-plan, le texte et les effets de survol.
-   `advfooter/js/script.js` :
    *   **Portée :** Back-office.
    *   **Responsabilité :** Script à usage général pour la page de configuration Back Office du module. Il pourrait initialiser le sélecteur `jscolor`, gérer la validation du formulaire ou d'autres améliorations de l'interface utilisateur pour l'interface d'administration.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `advfooter/css/fancybox.css` :
    *   **Portée :** Front-office (potentiellement, si le module utilise Fancybox pour tout contenu ou image intégré).
    *   **Responsabilité :** Fournit le style pour la bibliothèque lightbox Fancybox, qui est couramment utilisée pour afficher des images, des vidéos ou d'autres contenus dans une superposition modale. Sa présence suggère que le module pourrait prendre en charge une telle fonctionnalité, ou qu'il est inclus comme utilitaire général.
    *   **Sélecteurs de classe CSS clés :** `.fancybox-overlay`, `.fancybox-wrap`, `.fancybox-inner`, etc. Les développeurs peuvent les remplacer pour personnaliser l'apparence de la lightbox.

### 4.6 Structure du modèle Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** :

    *   `advfooter/footer.tpl` :
        *   **Hook :** `displayFooter` (et potentiellement `footer` pour les thèmes plus anciens).
        *   **Sortie :** Ce modèle est responsable du rendu de la structure principale du pied de page avancé. Il contiendra probablement un élément HTML `div` ou `footer` avec des styles en ligne dynamiques ou des attributs de classe remplis par les paramètres de configuration du module (par exemple, `width`, `height`, `background-color`, `background-image`, `color`). Il agit comme le conteneur pour tout contenu que d'autres modules ou le thème placent dans le hook `displayFooter`.
-   **Modèles d'administration (`views/templates/admin/`)** : Aucun. Le formulaire de configuration est probablement rendu directement dans `getContent()` à l'aide de `HelperForm` de PrestaShop ou similaire.
-   **Modèles Front-office (`views/templates/front/`)** : Aucun.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    *   Le module ne crée aucune table SQL personnalisée.
    *   Les paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide des clés : `ADVF_F_WIDTH`, `ADVF_F_HEIGHT`, `ADVF_F_BG`, `ADVF_F_COLOR`, `ADVF_F_COLOR_HOVER`, `ADVF_F_BG_URL`, `ADVF_F_BG_POS`, `ADVF_F_BG_REPEAT`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Exécuté dans la section `<head>` de chaque page. | Utilisé pour enregistrer les actifs CSS et JavaScript (`foscript.js`, `fancybox.css`) pour le front-office, et potentiellement injecter des styles en ligne basés sur la configuration du module. |
| `displayBackOfficeHeader` | Exécuté dans la section `<head>` de chaque page du Back Office. | Utilisé pour enregistrer les actifs CSS et JavaScript (`advajax.js`, `jscolor.js`, `script.js`) pour la page de configuration du module. |
| `displayFooter` | Exécuté en bas de page, généralement avant la balise de fermeture `</body>`. | Rend le modèle `footer.tpl`, qui applique le style personnalisé et agit comme le conteneur pour le contenu du pied de page. |
| `footer` | (PrestaShop 1.6 et versions antérieures, ou pour une compatibilité de thème spécifique) | Similaire à `displayFooter`, utilisé pour rendre le contenu du pied de page. Le module s'enregistre probablement aux deux pour une compatibilité plus large. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Vous y trouverez vos modules achetés et un accès direct aux ressources de support.
