---
title: "Widget de groupe Facebook - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Widget de groupe Facebook' par MyPresta.eu."
sidebar:
  label: "Widget de groupe Facebook - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Facebook join to group widget sur MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-join-to-group-widget.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/facebook-join-to-group-widget/)
>
> ---


# Widget de groupe Facebook

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement nécessaire.

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran principal où vous configurerez toutes les options de votre widget de groupe Facebook.

-   **Nom de l'écran et emplacement du menu :** Back Office > Modules > Gestionnaire de modules > « Widget de groupe Facebook » > Configurer

#### Paramètres et options :

1.  **URL du groupe** (Clé de configuration : `fbg_href`)

    -   **Ce que fait ce paramètre :** C'est le paramètre le plus crucial. Il définit le lien direct vers votre groupe Facebook. Lorsque les clients cliquent sur le bouton « Rejoindre le groupe », ils seront dirigés vers cette URL.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur une URL de groupe Facebook valide :* Le bouton « Rejoindre le groupe » redirigera correctement les utilisateurs vers votre groupe spécifié.
        -   *Lorsqu'il est laissé vide ou défini sur une URL invalide :* Le bouton pourrait ne pas fonctionner, ou il pourrait mener à une page d'erreur, frustrant vos clients.
    -   **Valeur recommandée :** Fournissez toujours l'URL complète et correcte de votre groupe Facebook (par exemple, `https://www.facebook.com/groups/votrenomdegroupe/`).
    -   **Scénario / exemple de marchand :** Vous voulez que les clients rejoignent votre groupe « Communauté de ma super boutique ». Vous colleriez `https://www.facebook.com/groups/macommunauteboutique/` ici.
2.  **Largeur de la boîte** (Clé de configuration : `fbg_width`)

    -   **Ce que fait ce paramètre :** Contrôle la largeur de la boîte du widget de groupe Facebook sur votre boutique. Vous pouvez la spécifier en pixels.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur une valeur en pixels spécifique (par exemple, `280`) :* La boîte tentera de s'afficher à cette largeur exacte.
        -   *Lorsqu'il est laissé vide ou défini sur `0` :* Le module tentera d'ajuster automatiquement sa largeur en fonction de l'espace disponible dans le hook où il est affiché, ou utilisera une valeur par défaut.
    -   **Valeur recommandée :** Commencez par `280` ou `300` pixels. Testez sur différents appareils. Si vous voulez qu'il remplisse l'espace disponible dans une colonne, vous pouvez le laisser vide, mais sachez qu'il pourrait s'étirer trop largement dans certains hooks.
    -   **Scénario / exemple de marchand :** Vous voulez que le widget s'intègre parfaitement dans votre colonne de gauche, qui fait 250px de large. Vous le définirez à `250`.
3.  **Où voulez-vous afficher la boîte ?** (Clé de configuration : `fbg_hook`)

    -   **Ce que fait ce paramètre :** Ce menu déroulant vous permet de sélectionner l'emplacement spécifique (hook PrestaShop) où le widget apparaîtra sur votre boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *Sélectionner `DisplayFooter` :* Le widget apparaîtra en bas de chaque page.
        -   *Sélectionner `DisplayHome` :* Le widget apparaîtra uniquement sur votre page d'accueil.
        -   *Sélectionner `DisplayRightColumn` :* Le widget apparaîtra dans la barre latérale droite sur les pages qui en ont une.
        -   *Sélectionner tout autre hook :* Le widget apparaîtra à cet emplacement spécifique.
    -   **Valeur recommandée :** Cela dépend entièrement de votre thème et de votre stratégie marketing. `DisplayRightColumn` ou `DisplayLeftColumn` sont courants pour les widgets latéraux. `DisplayFooter` est bon pour un placement moins intrusif. `DisplayHome` est excellent pour une visibilité élevée.
    -   **Scénario / exemple de marchand :** Vous voulez que le widget soit visible sur la plupart des pages mais n'interfère pas avec votre contenu principal. Vous choisissez `DisplayRightColumn`.
4.  **En-tête** (Clé de configuration : `fbg_header`)

    -   **Ce que fait ce paramètre :** C'est le texte du titre principal affiché en haut de votre widget de groupe Facebook.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur « Rejoignez notre communauté » :* Ce texte sera affiché de manière proéminente.
        -   *Lorsqu'il est laissé vide :* Aucun texte d'en-tête ne sera affiché, rendant le widget moins clair pour les clients.
    -   **Valeur recommandée :** Un titre clair et invitant comme « Rejoignez notre groupe Facebook », « Notre communauté » ou « Connectez-vous avec nous ».
    -   **Scénario / exemple de marchand :** Vous voulez clairement indiquer aux clients de quoi il s'agit. Vous le définissez à « Rejoignez notre groupe Facebook exclusif ! ».
5.  **Description** (Clé de configuration : `fbg_desc`)

    -   **Ce que fait ce paramètre :** Fournit un court texte explicatif sous l'en-tête, donnant aux clients plus de contexte sur votre groupe Facebook.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur « Obtenez des offres exclusives et des mises à jour ! » :* Ce message apparaîtra sous l'en-tête.
        -   *Lorsqu'il est laissé vide :* Le widget n'affichera que l'en-tête et le bouton, manquant potentiellement une opportunité d'attirer les utilisateurs.
    -   **Valeur recommandée :** Une phrase ou deux brèves et convaincantes expliquant les avantages de l'adhésion (par exemple, « Soyez le premier informé des nouveaux produits et des offres spéciales ! »).
    -   **Scénario / exemple de marchand :** Vous voulez encourager les inscriptions en soulignant les avantages. Vous le définissez à « Accédez à des réductions réservées aux membres, des aperçus et connectez-vous avec d'autres passionnés ! ».
6.  **Texte du bouton** (Clé de configuration : `fbg_btn_text`)

    -   **Ce que fait ce paramètre :** C'est le texte affiché sur le bouton sur lequel les clients cliquent pour rejoindre votre groupe.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur « Rejoindre le groupe » :* Ce texte apparaîtra sur le bouton.
        -   *Lorsqu'il est laissé vide :* Le bouton pourrait apparaître vide ou utiliser une valeur par défaut, ce qui est moins efficace.
    -   **Valeur recommandée :** Un appel à l'action clair comme « Rejoindre le groupe », « Rejoindre maintenant » ou « Connectez-vous sur Facebook ».
    -   **Scénario / exemple de marchand :** Vous voulez un appel à l'action direct. Vous le définissez à « Rejoindre notre groupe ».
7.  **Couleur du texte** (Clé de configuration : `fbg_text_color`)

    -   **Ce que fait ce paramètre :** Vous permet de définir la couleur du texte de l'en-tête et de la description dans le widget.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur `#000000` (noir) :* Le texte apparaîtra en noir.
        -   *Lorsqu'il est défini sur `#FFFFFF` (blanc) :* Le texte apparaîtra en blanc.
    -   **Valeur recommandée :** Choisissez une couleur qui contraste bien avec la couleur d'arrière-plan choisie et qui correspond à la palette de couleurs de votre marque. Utilisez un code hexadécimal (par exemple, `#333333`).
    -   **Scénario / exemple de marchand :** Votre widget a un arrière-plan sombre. Vous définissez la couleur du texte sur `#FFFFFF` pour la lisibilité.
8.  **Style de bordure** (Clé de configuration : `fbg_border_style`)

    -   **Ce que fait ce paramètre :** Définit le style visuel de la bordure autour de la boîte du widget.
    -   **Effet de la modification de ce paramètre :**
        -   *`solid` :* Une ligne unique et continue.
        -   *`dashed` :* Une série de courtes lignes.
        -   *`dotted` :* Une série de points.
        -   *`none` :* Aucune bordure ne sera affichée.
    -   **Valeur recommandée :** `solid` ou `none` sont les plus courants. `solid` fournit une limite claire.
    -   **Scénario / exemple de marchand :** Vous voulez un contour subtil pour la boîte. Vous choisissez `solid`.
9.  **Couleur de la bordure** (Clé de configuration : `fbg_border_color`)

    -   **Ce que fait ce paramètre :** Définit la couleur de la bordure autour de la boîte du widget.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur `#CCCCCC` (gris clair) :* La bordure sera gris clair.
        -   *Lorsqu'il est défini sur `#FF0000` (rouge) :* La bordure sera rouge.
    -   **Valeur recommandée :** Une couleur qui complète le design de votre boutique, souvent un gris subtil ou une couleur d'accent de la marque. Utilisez un code hexadécimal.
    -   **Scénario / exemple de marchand :** Votre marque utilise une nuance spécifique de bleu. Vous définissez la couleur de la bordure sur `#007bff`.
10. **Taille de la bordure** (Clé de configuration : `fbg_border_size`)

    -   **Ce que fait ce paramètre :** Détermine l'épaisseur de la bordure en pixels.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur `1` :* Une bordure fine apparaîtra.
        -   *Lorsqu'il est défini sur `5` :* Une bordure plus épaisse et plus proéminente apparaîtra.
    -   **Valeur recommandée :** `1` ou `2` pixels pour une bordure subtile.
    -   **Scénario / exemple de marchand :** Vous voulez une bordure très fine. Vous définissez la taille sur `1`.
11. **Rayon de la bordure** (Clé de configuration : `fbg_border_radius`)

    -   **Ce que fait ce paramètre :** Contrôle l'arrondi des coins de la boîte du widget. Une valeur plus élevée crée des coins plus arrondis.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur `0` :* La boîte aura des coins nets et carrés.
        -   *Lorsqu'il est défini sur `10` :* Les coins seront nettement arrondis.
    -   **Valeur recommandée :** `0` pour des coins nets, `3` à `5` pour légèrement arrondis, ou `10+` pour très arrondis, selon l'esthétique de votre thème.
    -   **Scénario / exemple de marchand :** Votre thème utilise des éléments légèrement arrondis. Vous définissez le rayon de la bordure sur `5`.
12. **Couleur d'arrière-plan** (Clé de configuration : `fbg_bg_color`)

    -   **Ce que fait ce paramètre :** Définit la couleur d'arrière-plan principale de la boîte du widget.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur `#F0F2F5` (gris clair, similaire à l'arrière-plan de Facebook) :* L'arrière-plan de la boîte sera gris clair.
        -   *Lorsqu'il est défini sur `#FFFFFF` (blanc) :* L'arrière-plan de la boîte sera blanc.
    -   **Valeur recommandée :** Une couleur qui rend le texte lisible et s'adapte au design de votre boutique. Utilisez un code hexadécimal.
    -   **Scénario / exemple de marchand :** Vous voulez que le widget se distingue légèrement d'un arrière-plan de page blanc. Vous définissez la couleur d'arrière-plan sur `#F8F8F8`.
13. **Dégradé d'arrière-plan** (Clé de configuration : `fbg_bg_gradient`)

    -   **Ce que fait ce paramètre :** Vous permet d'ajouter un dégradé CSS à l'arrière-plan de la boîte du widget, créant une transition douce entre deux couleurs ou plus. Cela annule la « Couleur d'arrière-plan » unique si elle est utilisée.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur `linear-gradient(to right, #FFD700, #FFA500)` :* L'arrière-plan passera de l'or à l'orange.
        -   *Lorsqu'il est laissé vide :* Le paramètre « Couleur d'arrière-plan » sera utilisé à la place.
    -   **Valeur recommandée :** Utilisez une chaîne de dégradé CSS si vous voulez un arrière-plan plus dynamique. Si vous n'êtes pas sûr, laissez ce champ vide et utilisez une seule « Couleur d'arrière-plan ».
    -   **Scénario / exemple de marchand :** Vous voulez un look subtil et moderne. Vous utilisez un dégradé comme `linear-gradient(to bottom, #e0eafc, #cfdef3)`.

#### Paramètres cachés/internes (pour référence développeur, non directement configurables par le marchand) :

-   `mypresta_updates`, `update_`, `updatev_` : Clés internes pour les mises à jour et les vérifications de version du module.
-   `fbg_app`, `fbg_appid` : Ces clés suggèrent un potentiel d'intégration d'application Facebook, mais ne sont pas exposées dans la configuration actuelle.
-   `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` : Paramètres de base de PrestaShop liés à la gestion des langues dans le back office.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | **URL du groupe** | Votre URL de groupe Facebook | Lien direct vers votre groupe Facebook pour le bouton « Rejoindre le groupe ». **CRITIQUE !** |
| Configuration du module | **Largeur de la boîte** | `280` ou `300`px | Définit la largeur de la boîte du widget. Laisser vide pour un ajustement automatique. |
| Configuration du module | **Où voulez-vous afficher la boîte ?** | `DisplayRightColumn` ou `DisplayFooter` | Sélectionne le hook PrestaShop où le widget apparaît. |
| Configuration du module | **En-tête** | « Rejoignez notre groupe Facebook » | Texte du titre principal pour le widget. |
| Configuration du module | **Description** | « Obtenez des offres exclusives et des mises à jour ! » | Court texte explicatif sous l'en-tête. |
| Configuration du module | **Texte du bouton** | « Rejoindre le groupe » | Texte affiché sur le bouton d'action. |
| Configuration du module | **Couleur du texte** | `#333333` (gris foncé) | Couleur du texte de l'en-tête et de la description. Utiliser un code hexadécimal. |
| Configuration du module | **Style de bordure** | `solid` ou `none` | Style visuel de la bordure de la boîte (solide, tirets, pointillés, aucun). |
| Configuration du module | **Couleur de la bordure** | `#CCCCCC` (gris clair) | Couleur de la bordure de la boîte. Utiliser un code hexadécimal. |
| Configuration du module | **Taille de la bordure** | `1` ou `2`px | Épaisseur de la bordure de la boîte. |
| Configuration du module | **Rayon de la bordure** | `0` ou `5`px | Arrondi des coins de la boîte. |
| Configuration du module | **Couleur d'arrière-plan** | `#F0F2F5` (gris clair) | Couleur d'arrière-plan principale de la boîte du widget. Utiliser un code hexadécimal. |
| Configuration du module | **Dégradé d'arrière-plan** | Laisser vide | Dégradé CSS pour l'arrière-plan. Annule la `Couleur d'arrière-plan` si défini. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

1.  **Le widget n'apparaît pas sur ma boutique.**

    -   **Vérification 1 :** Allez dans **Modules > Gestionnaire de modules**, recherchez « Widget de groupe Facebook » et assurez-vous qu'il est installé et activé.
    -   **Vérification 2 :** Dans la configuration du module, vérifiez que vous avez sélectionné un « Où voulez-vous afficher la boîte ? » (hook). Assurez-vous que le hook sélectionné existe réellement et est actif dans votre thème actuel. Certains thèmes peuvent ne pas utiliser tous les hooks PrestaShop standard.
    -   **Vérification 3 :** Videz votre cache PrestaShop (**Paramètres avancés > Performances > Vider le cache**). Parfois, les modifications n'apparaissent pas tant que le cache n'est pas actualisé.
    -   **Vérification 4 :** Si vous avez un thème personnalisé, il pourrait annuler les affichages de hook standard. Contactez le développeur de votre thème ou un webmaster.
2.  **Le bouton « Rejoindre le groupe » ne fonctionne pas ou mène à une erreur.**

    -   **Vérification :** Allez dans la configuration du module et saisissez à nouveau attentivement votre « URL du groupe ». Assurez-vous qu'il s'agit de l'URL complète et correcte de votre groupe Facebook (par exemple, `https://www.facebook.com/groups/votrenomdegroupe/`). Testez l'URL directement dans votre navigateur pour confirmer qu'elle fonctionne.
3.  **Le widget a l'air étrange ou ne correspond pas au design de mon thème.**

    -   **Vérification 1 :** Ajustez le paramètre « Largeur de la boîte ». S'il est trop large pour une colonne, il pourrait casser la mise en page. Essayez une valeur en pixels plus petite.
    -   **Vérification 2 :** Utilisez les paramètres « Couleur du texte », « Style de bordure », « Couleur de la bordure », « Taille de la bordure », « Rayon de la bordure », « Couleur d'arrière-plan » et « Dégradé d'arrière-plan » pour correspondre aux couleurs et aux styles de votre thème.
    -   **Vérification 3 :** Videz votre cache PrestaShop après avoir effectué des modifications de style.
    -   **Vérification 4 :** Si le problème persiste, il pourrait s'agir d'un conflit CSS avec votre thème. Un webmaster peut inspecter le CSS de votre site pour identifier et résoudre les conflits.
4.  **Puis-je afficher le widget à plusieurs endroits ?**

    -   La version actuelle du module vous permet de sélectionner un seul hook dans le menu déroulant. Si vous devez l'afficher à plusieurs endroits, vous devrez dupliquer le module (ce qui nécessite l'intervention d'un développeur) ou utiliser une solution personnalisée.
5.  **Mon texte n'apparaît pas dans la bonne langue.**

    -   Les champs « En-tête », « Description » et « Texte du bouton » sont généralement traduisibles si votre installation PrestaShop prend en charge plusieurs langues pour les configurations de module. Assurez-vous que vous modifiez la configuration du module dans le bon contexte linguistique dans le Back Office (vérifiez le menu déroulant de la langue en haut à droite de votre panneau d'administration).

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Widget de groupe Facebook » est un module PrestaShop simple suivant un modèle de type MVC de base inhérent à la structure des modules de PrestaShop. Il utilise principalement la classe `Module` pour sa fonctionnalité principale, la gestion de la configuration et l'enregistrement des hooks. Toute la configuration est gérée via la méthode `getContent()` dans le fichier principal du module, stockant les paramètres dans `ps_configuration`. L'affichage en front-office est géré via des templates Smarty rendus via des hooks enregistrés. Il n'y a pas de contrôleurs personnalisés ni d'ObjectModels.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Aucun. Tout le rendu front-office est géré directement via les méthodes `hook` dans le fichier principal du module `fbgroup.php`, qui rendent ensuite les templates Smarty.
-   **Contrôleurs d'administration Back-Office** : Aucun. Toute l'administration est gérée via la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

-   **`fbgroup/fbgroup.php` (Classe principale du module)**
    -   **Nom de la classe :** `Fbgroup`
    -   **Classe parente :** `Module`
    -   **Responsabilité :**
        -   Installation (`install()`) et désinstallation (`uninstall()`) du module.
        -   Enregistrement de tous les hooks spécifiés (`registerHook()`).
        -   Gestion des paramètres de configuration du module via la méthode `getContent()`, qui gère la soumission du formulaire et met à jour la table `ps_configuration`.
        -   Implémentation de diverses méthodes `hook` (par exemple, `hookDisplayHeader`, `hookDisplayFooter`, `hookDisplayHome`, etc.) pour afficher le widget en front-office.
        -   Récupération des valeurs de configuration de `ps_configuration` pour le rendu du template.
        -   Méthode `_clearCache()` pour vider le cache spécifique au module.
        -   Méthode `_displayForm()` pour rendre le formulaire de configuration dans le back-office.

### 4.4 Actifs JavaScript (`views/js/`)

-   Aucun fichier JavaScript personnalisé n'est inclus dans ce module. Toutes les fonctionnalités sont gérées côté serveur ou via HTML/CSS standard.

### 4.5 Feuilles de style CSS (`views/css/`)

-   Aucun fichier CSS personnalisé n'est inclus dans ce module. Tout le style est appliqué en ligne dans le template `displayHeader.tpl` ou directement via la méthode `hookDisplayHeader`, en utilisant les valeurs de configuration. Cela signifie que les développeurs souhaitant annuler les styles devront cibler directement le HTML généré ou utiliser le hook `displayHeader` pour injecter leur propre CSS.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :

    -   `fbgroup/views/displayHeader.tpl` :
        -   **Hook :** Principalement destiné à `displayHeader` (bien que la méthode `hookDisplayHeader` du module soit utilisée pour injecter du CSS, et non pour rendre le widget lui-même). Ce template n'est PAS utilisé pour l'affichage principal du widget. Il s'agit probablement d'un vestige ou utilisé pour l'injection de méta/CSS.
        -   **Objectif :** S'il était utilisé, il produirait du code HTML dans la section `<head>`. Dans le contexte de ce module, la méthode `hookDisplayHeader` est utilisée pour *injecter des styles CSS* dynamiquement en fonction des paramètres de configuration, plutôt que de rendre un template visible.
    -   `fbgroup/views/displayWidget.tpl` :
        -   **Hook :** C'est le template principal utilisé pour rendre le widget de groupe Facebook dans tous les hooks front-office sélectionnés (par exemple, `displayFooter`, `displayHome`, `displayRightColumn`, etc.).
        -   **Objectif :** Produit la structure HTML du widget, y compris l'en-tête, la description et le bouton « Rejoindre le groupe ». Il reçoit des variables comme `fbg_href`, `fbg_header`, `fbg_desc`, `fbg_btn_text` et des styles CSS dynamiques des méthodes de hook du module.
-   **Templates d'administration (`views/templates/admin/`)** : Aucun. Le formulaire de configuration est construit par programme dans `getContent()` à l'aide de `HelperForm` de PrestaShop.
-   **Templates Front-Office (`views/templates/front/`)** : Aucun.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :

    -   Le module ne crée aucune table de base de données personnalisée.
    -   Tous les paramètres de configuration sont stockés dans la table `ps_configuration` (ou le préfixe `_configuration`, selon votre configuration) en utilisant les clés de configuration listées dans la section 4.1 (par exemple, `FBG_HREF`, `FBG_WIDTH`, `FBG_HEADER`, etc.).
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Utilisé par le module pour injecter des styles CSS dynamiques pour le widget en fonction de la configuration. |
| `displayFooter` | En bas de chaque page, avant `</body>`. | Rend le template `displayWidget.tpl`, affichant le widget Facebook. |
| `displayHome` | Sur la page d'accueil, généralement dans la zone de contenu principale. | Rend le template `displayWidget.tpl`, affichant le widget Facebook. |
| `displayNav1` | Dans la barre de navigation, souvent en haut à gauche. | Rend le template `displayWidget.tpl`, affichant le widget Facebook. |
| `displayNav2` | Dans la barre de navigation, souvent en haut à droite. | Rend le template `displayWidget.tpl`, affichant le widget Facebook. |
| `displayNav` | Hook de navigation générique, dépendant du thème. | Rend le template `displayWidget.tpl`, affichant le widget Facebook. |
| `displayFbgroup` | Hook personnalisé, nécessite une intégration au thème. | Rend le template `displayWidget.tpl`, affichant le widget Facebook. |
| `displayTop` | Dans la section d'en-tête, souvent au-dessus du logo. | Rend le template `displayWidget.tpl`, affichant le widget Facebook. |
| `displayTopColumn` | Dans la zone de contenu principale de l'en-tête. | Rend le template `displayWidget.tpl`, affichant le widget Facebook. |
| `displayLeftColumn` | Dans la barre latérale gauche des pages qui en ont une. | Rend le template `displayWidget.tpl`, affichant le widget Facebook. |
| `displayRightColumn` | Dans la barre latérale droite des pages qui en ont une. | Rend le template `displayWidget.tpl`, affichant le widget Facebook. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Widget de groupe Facebook », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
