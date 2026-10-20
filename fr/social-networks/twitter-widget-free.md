---
title: "Widget Twitter gratuit - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Widget Twitter gratuit par MyPresta.eu."
sidebar:
  label: "Widget Twitter gratuit - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Twitter widget free sur MyPresta.eu](https://mypresta.eu/modules/social-networks/twitter-widget-free.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/twitter-widget-free/)
>
> ---


# Widget Twitter gratuit

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune exigence particulière au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal et unique pour le module « Widget Twitter gratuit ». Ici, vous définirez comment votre chronologie Twitter apparaît et fonctionne sur votre boutique.

| Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- |
| **Nom d'utilisateur Twitter** | `mypresta` (exemple) | **Ce que fait ce paramètre :** C'est le paramètre le plus crucial. Il spécifie le compte Twitter (X) dont les tweets publics seront affichés. Vous devez entrer le nom d'utilisateur de votre compte (par exemple, `mypresta`, `lenomdevotreboutique`).   **Effet de la modification de ce paramètre :**   *Lorsqu'il est défini sur votre nom d'utilisateur :* Le widget récupérera et affichera les tweets de votre compte spécifié.   *Lorsqu'il est laissé vide ou incorrect :* Le widget n'affichera aucun tweet ou affichera un message d'erreur, car il ne saura pas de quel compte extraire les données.   **Valeur recommandée :** Votre nom d'utilisateur Twitter (X) officiel, sans le symbole « @ ».   **Scénario / exemple pour le marchand :** Si votre identifiant Twitter est `@MaSuperBoutique`, vous entreriez `MaSuperBoutique` ici. |
| **ID du widget** | `(vide)` | **Ce que fait ce paramètre :** C'est un paramètre avancé pour des configurations spécifiques de widgets Twitter. Twitter vous permet de créer des widgets personnalisés sur leur plateforme, qui génèrent un ID unique. Cet ID peut être utilisé pour afficher une chronologie hautement personnalisée (par exemple, une chronologie de listes spécifiques, de résultats de recherche ou de collections).   **Effet de la modification de ce paramètre :**   *Lorsqu'il est laissé vide :* Le module générera une chronologie standard basée sur votre « Nom d'utilisateur Twitter ». C'est généralement suffisant pour la plupart des marchands.   *Lorsqu'un ID de widget valide est entré :* Le module affichera la chronologie spécifique et personnalisée associée à cet ID, remplaçant la chronologie utilisateur par défaut.   **Valeur recommandée :** Laissez vide, sauf si vous avez créé un widget personnalisé sur la plateforme développeur de Twitter et que vous souhaitez spécifiquement utiliser son ID.   **Scénario / exemple pour le marchand :** Vous pourriez créer un widget Twitter personnalisé qui n'affiche que les tweets contenant un hashtag spécifique lié à une campagne. Vous obtiendriez alors l'ID de ce widget de Twitter et l'entreriez ici. |
| **Thème** | `light` | **Ce que fait ce paramètre :** Contrôle le thème visuel du widget Twitter.   **Effet de la modification de ce paramètre :**   *Lorsqu'il est défini sur `light` (par défaut) :* Le widget aura un arrière-plan clair et un texte sombre, adapté à la plupart des boutiques PrestaShop à thème clair.   *Lorsqu'il est défini sur `dark` (si disponible) :* Le widget aura un arrière-plan sombre et un texte clair, idéal pour les boutiques à thème sombre ou pour créer un contraste.   **Valeur recommandée :** `light` pour la plupart des boutiques. Choisissez `dark` si le design de votre boutique utilise une palette de couleurs sombres.   **Scénario / exemple pour le marchand :** Si votre site web a un fond blanc et épuré, le thème `light` s'intégrera parfaitement. Si votre site utilise un fond gris foncé ou noir sophistiqué, le thème `dark` serait plus approprié. |
| **Couleur des liens** | `(vide)` | **Ce que fait ce paramètre :** Vous permet de personnaliser la couleur des liens dans le widget Twitter (par exemple, hashtags, mentions, URL).   **Effet de la modification de ce paramètre :**   *Lorsqu'il est laissé vide :* Le widget utilisera la couleur de lien par défaut de Twitter (généralement une nuance de bleu).   *Lorsqu'un code couleur hexadécimal valide est entré (par exemple, `#FF0000` pour le rouge) :* Tous les liens du widget s'afficheront dans cette couleur personnalisée.   **Valeur recommandée :** Laissez vide pour la valeur par défaut, ou entrez un code couleur hexadécimal qui correspond à l'image de marque de votre boutique.   **Scénario / exemple pour le marchand :** Si la couleur principale de votre marque est le vert, vous pourriez entrer `#008000` pour que les liens du widget correspondent à votre marque. |
| **Couleur de la bordure** | `(vide)` | **Ce que fait ce paramètre :** Vous permet de personnaliser la couleur de la bordure autour du widget Twitter.   **Effet de la modification de ce paramètre :**   *Lorsqu'il est laissé vide :* Le widget utilisera la couleur de bordure par défaut de Twitter.   *Lorsqu'un code couleur hexadécimal valide est entré :* La bordure du widget s'affichera dans cette couleur personnalisée.   **Valeur recommandée :** Laissez vide pour la valeur par défaut, ou entrez un code couleur hexadécimal qui correspond à l'image de marque de votre boutique ou qui s'harmonise avec votre mise en page.   **Scénario / exemple pour le marchand :** Pour faire ressortir le widget avec un cadre subtil, vous pourriez utiliser une bordure gris clair `#CCCCCC`. |
| **Limite de tweets** | `20` | **Ce que fait ce paramètre :** Détermine le nombre maximum de tweets qui seront affichés dans la chronologie.   **Effet de la modification de ce paramètre :**   *Lorsqu'il est défini sur un nombre inférieur (par exemple, `3`) :* Seuls les quelques tweets les plus récents seront visibles, rendant le widget plus court.   *Lorsqu'il est défini sur un nombre supérieur (par exemple, `20`) :* Plus de tweets seront chargés, rendant le widget plus long et permettant plus de défilement.   **Valeur recommandée :** `3` à `7` pour les colonnes latérales pour le garder concis, `10` à `20` pour les zones plus larges comme le pied de page ou le contenu principal.   **Scénario / exemple pour le marchand :** Si vous placez le widget dans une colonne gauche étroite, vous pouvez le régler sur `3` pour éviter de rendre la colonne trop longue. Dans le pied de page, vous pouvez le régler sur `10` pour afficher plus d'activité. |
| **Hauteur** | `300` | **Ce que fait ce paramètre :** Définit la hauteur fixe du widget Twitter en pixels.   **Effet de la modification de ce paramètre :**   *Lorsqu'il est défini sur un nombre inférieur (par exemple, `200`) :* Le widget sera plus court, nécessitant potentiellement plus de défilement pour voir tous les tweets (jusqu'à la limite de tweets).   *Lorsqu'il est défini sur un nombre supérieur (par exemple, `500`) :* Le widget sera plus grand, affichant plus de tweets à la fois sans défilement.   **Valeur recommandée :** `280` à `400` pixels, selon l'emplacement et l'espace disponible.   **Scénario / exemple pour le marchand :** Pour une colonne de droite, une hauteur de `300px` est souvent un bon équilibre. Pour un placement en pied de page, vous pouvez l'augmenter à `400px` si vous avez suffisamment d'espace vertical. |
| **Largeur** | `(vide)` | **Ce que fait ce paramètre :** Définit la largeur fixe du widget Twitter en pixels.   **Effet de la modification de ce paramètre :**   *Lorsqu'il est laissé vide :* Le widget tentera d'ajuster automatiquement sa largeur pour s'adapter au conteneur dans lequel il est placé (comportement réactif). C'est généralement recommandé.   *Lorsqu'il est défini sur un nombre spécifique (par exemple, `250`) :* Le widget conservera cette largeur fixe, ce qui pourrait entraîner un débordement ou un espace vide si le conteneur est plus grand ou plus petit.   **Valeur recommandée :** Laissez vide pour un comportement réactif, ou définissez une largeur spécifique si vous avez besoin d'un contrôle précis et comprenez les implications pour différentes tailles d'écran.   **Scénario / exemple pour le marchand :** Le laisser vide garantit qu'il s'affiche correctement sur mobile. Si vous avez absolument besoin d'une largeur fixe pour une mise en page très spécifique, vous pouvez le régler sur `280px` pour une colonne étroite. |
| **Langue** | `en` | **Ce que fait ce paramètre :** Détermine la langue dans laquelle l'interface du widget Twitter (par exemple, bouton « Voir sur Twitter », horodatages) est affichée.   **Effet de la modification de ce paramètre :**   *Lorsqu'il est défini sur `en` (anglais) :* L'interface du widget sera en anglais.   *Lorsqu'il est défini sur un autre code de langue valide (par exemple, `fr` pour le français, `es` pour l'espagnol) :* L'interface du widget sera localisée dans cette langue.   **Valeur recommandée :** La langue principale de votre boutique.   **Scénario / exemple pour le marchand :** Si votre boutique sert principalement des clients en France, le réglage sur `fr` rendra le widget plus convivial pour eux. |
| **Afficher l'en-tête** | `YES` | **Ce que fait ce paramètre :** Contrôle si la section d'en-tête du widget Twitter (affichant le nom de votre compte et l'étiquette « Tweets ») est visible.   **Effet de la modification de ce paramètre :**   *Lorsqu'il est activé (YES) :* L'en-tête sera affiché, fournissant un contexte clair sur les tweets affichés.   *Lorsqu'il est désactivé (NO) :* L'en-tête sera masqué, ce qui rendra le widget plus compact, mais potentiellement moins clair.   **Valeur recommandée :** `YES` pour la clarté, sauf si vous avez besoin d'un design très minimaliste.   **Scénario / exemple pour le marchand :** Si le widget est dans un endroit bien visible, `YES` est une bonne option. S'il s'agit d'un petit widget dans une zone encombrée, `NO` pourrait économiser de l'espace. |
| **Afficher le pied de page** | `YES` | **Ce que fait ce paramètre :** Contrôle si la section de pied de page du widget Twitter (affichant généralement le lien « Voir sur Twitter ») est visible.   **Effet de la modification de ce paramètre :**   *Lorsqu'il est activé (YES) :* Le pied de page sera affiché, fournissant un lien direct aux utilisateurs pour visiter votre profil Twitter complet.   *Lorsqu'il est désactivé (NO) :* Le pied de page sera masqué, rendant le widget plus compact.   **Valeur recommandée :** `YES` pour encourager les utilisateurs à vous suivre sur Twitter.   **Scénario / exemple pour le marchand :** Garder `YES` aide à générer du trafic vers votre profil Twitter. |
| **Afficher la bordure** | `YES` | **Ce que fait ce paramètre :** Contrôle si une bordure est affichée autour du widget Twitter.   **Effet de la modification de ce paramètre :**   *Lorsqu'il est activé (YES) :* Une bordure encadrera le widget, l'aidant à se distinguer du contenu environnant.   *Lorsqu'il est désactivé (NO) :* Le widget n'aura pas de bordure visible, se fondant plus harmonieusement avec l'arrière-plan.   **Valeur recommandée :** `YES` pour une meilleure séparation visuelle, surtout dans les colonnes.   **Scénario / exemple pour le marchand :** Si votre page contient beaucoup de contenu, une bordure aide à définir l'espace du widget. Si vous souhaitez un look très épuré et intégré, `NO` pourrait être préféré. |
| **Afficher la barre de défilement** | `YES` | **Ce que fait ce paramètre :** Contrôle si une barre de défilement apparaît dans le widget si le contenu (tweets) dépasse la hauteur définie.   **Effet de la modification de ce paramètre :**   *Lorsqu'il est activé (YES) :* Une barre de défilement apparaîtra, permettant aux utilisateurs de faire défiler tous les tweets chargés dans la hauteur fixe.   *Lorsqu'il est désactivé (NO) :* Aucune barre de défilement n'apparaîtra. Si les tweets dépassent la hauteur, ils seront coupés, ou le widget pourrait s'étendre (selon d'autres paramètres et le comportement du navigateur). Ce n'est généralement pas recommandé car cela masque le contenu.   **Valeur recommandée :** `YES` pour s'assurer que tous les tweets sont accessibles.   **Scénario / exemple pour le marchand :** Gardez toujours `YES` sauf si vous ne voulez afficher que 1 ou 2 tweets et ne voulez jamais de défilement. |
| **Fond transparent** | `YES` | **Ce que fait ce paramètre :** Contrôle si l'arrière-plan du widget Twitter est transparent.   **Effet de la modification de ce paramètre :**   *Lorsqu'il est activé (YES) :* L'arrière-plan du widget sera transparent, permettant à la couleur ou à l'image d'arrière-plan de votre boutique d'apparaître.   *Lorsqu'il est désactivé (NO) :* Le widget aura un arrière-plan solide (blanc pour le thème `light`, sombre pour le thème `dark`), créant potentiellement une apparence de boîte.   **Valeur recommandée :** `YES` pour une meilleure intégration avec votre thème.   **Scénario / exemple pour le marchand :** Si votre boutique a un arrière-plan texturé ou une couleur d'arrière-plan spécifique, `YES` fera en sorte que le widget ressemble à une partie naturelle de votre design. |
| **Afficher les réponses** | `YES` | **Ce que fait ce paramètre :** Contrôle si les réponses aux tweets sont incluses dans la chronologie.   **Effet de la modification de ce paramètre :**   *Lorsqu'il est activé (YES) :* Les réponses seront affichées, offrant un contexte de conversation plus complet.   *Lorsqu'il est désactivé (NO) :* Seuls les tweets originaux et les retweets seront affichés, rendant la chronologie potentiellement plus propre mais moins conversationnelle.   **Valeur recommandée :** `YES` pour un flux plus actif et engageant.   **Scénario / exemple pour le marchand :** Si vous interagissez fréquemment avec les clients via des réponses, `YES` est important pour montrer cette interaction. Si votre flux est purement destiné aux annonces, `NO` pourrait être préféré. |
| **Lecture automatique des vidéos** | `NO` | **Ce que fait ce paramètre :** Contrôle si les vidéos intégrées dans les tweets du widget seront lues automatiquement.   **Effet de la modification de ce paramètre :**   *Lorsqu'il est activé (YES) :* Les vidéos commenceront à être lues automatiquement lorsqu'elles apparaîtront dans la fenêtre d'affichage. Cela peut être engageant mais pourrait consommer de la bande passante et agacer certains utilisateurs.   *Lorsqu'il est désactivé (NO) :* Les vidéos nécessiteront un clic de l'utilisateur pour être lues.   **Valeur recommandée :** `NO` pour éviter de surprendre les clients avec du son ou de consommer leurs données sans consentement.   **Scénario / exemple pour le marchand :** Généralement, `NO` est préférable pour l'expérience utilisateur. Si vous avez une vidéo très spécifique, silencieuse et courte que vous souhaitez mettre en évidence, vous pouvez envisager `YES`, mais procédez avec prudence. |
| **Masquer la barre de défilement** | `NO` | **Ce que fait ce paramètre :** Ce paramètre est probablement redondant ou en conflit avec « Afficher la barre de défilement ». En général, si « Afficher la barre de défilement » est OUI, ce paramètre doit être NON.   **Effet de la modification de ce paramètre :**   *Lorsqu'il est activé (YES) :* Tente de masquer la barre de défilement. Cela peut rendre le contenu inaccessible si la hauteur est fixe et que les tweets la dépassent.   *Lorsqu'il est désactivé (NO) :* Permet à la barre de défilement d'être visible si « Afficher la barre de défilement » est également OUI.   **Valeur recommandée :** `NO` pour s'assurer que le contenu est toujours accessible.   **Scénario / exemple pour le marchand :** Gardez toujours `NO` en conjonction avec `Afficher la barre de défilement : YES`. |
| **Placer dans le hook** | `displayRightColumn` | **Ce que fait ce paramètre :** Détermine où le widget Twitter sera affiché dans votre boutique PrestaShop.   **Effet de la modification de ce paramètre :**   *Lorsqu'il est défini sur `displayRightColumn` (par défaut) :* Le widget apparaîtra dans la barre latérale droite.   *Lorsqu'il est défini sur `displayLeftColumn` (si disponible) :* Le widget apparaîtra dans la barre latérale gauche.   *Lorsqu'il est défini sur `displayFooter` (si disponible) :* Le widget apparaîtra dans la section du pied de page.   *Lorsqu'il est défini sur `displayHeader` (si disponible) :* Le widget apparaîtra dans la section de l'en-tête.   *Lorsqu'il est défini sur `displayProductButtons` ou similaire (si disponible) :* Le widget apparaîtra sur les pages produits.   **Valeur recommandée :** `displayRightColumn` ou `displayLeftColumn` pour une visibilité générale, `displayFooter` pour un placement moins intrusif. Choisissez en fonction de la mise en page de votre thème et de l'endroit où vous souhaitez attirer l'attention.   **Scénario / exemple pour le marchand :** Si votre thème a une barre latérale droite proéminente, `displayRightColumn` est un bon choix. Si vous voulez qu'il soit visible sur chaque page mais qu'il ne prenne pas beaucoup de place, `displayFooter` est approprié. |

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
|---|---|---|
| Configuration du module | Nom d'utilisateur Twitter | Votre nom d'utilisateur X | Spécifie le compte à partir duquel afficher les tweets. |
| Configuration du module | ID du widget | Vide | Avancé : Utiliser pour les widgets personnalisés générés par Twitter. |
| Configuration du module | Thème | `light` | Thème visuel du widget (clair/sombre). |
| Configuration du module | Couleur des liens | Vide | Personnalise les couleurs des liens dans le widget. |
| Configuration du module | Couleur de la bordure | Vide | Personnalise la couleur de la bordure du widget. |
| Configuration du module | Limite de tweets | `20` | Nombre maximum de tweets à afficher. |
| Configuration du module | Hauteur | `300` | Hauteur fixe du widget en pixels. |
| Configuration du module | Largeur | Vide | Largeur fixe du widget en pixels (laisser vide pour réactif). |
| Configuration du module | Langue | `en` | Langue de l'interface du widget. |
| Configuration du module | Afficher l'en-tête | `YES` | Afficher/masquer l'en-tête du widget (nom du compte). |
| Configuration du module | Afficher le pied de page | `YES` | Afficher/masquer le pied de page du widget (lien Voir sur Twitter). |
| Configuration du module | Afficher la bordure | `YES` | Afficher/masquer la bordure extérieure du widget. |
| Configuration du module | Afficher la barre de défilement | `YES` | Afficher/masquer la barre de défilement interne pour les tweets. |
| Configuration du module | Fond transparent | `YES` | Rendre l'arrière-plan du widget transparent. |
| Configuration du module | Afficher les réponses | `YES` | Inclure/exclure les réponses dans la chronologie. |
| Configuration du module | Lecture automatique des vidéos | `NO` | Lecture automatique des vidéos dans les tweets. |
| Configuration du module | Masquer la barre de défilement | `NO` | (Redondant avec Afficher la barre de défilement) Garder NON. |
| Configuration du module | Placer dans le hook | `displayRightColumn` | Où le widget apparaît dans votre boutique. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mon widget Twitter n'apparaît pas sur ma boutique. Que dois-je faire ?**
R :

1.  **Vérifier la configuration :** Allez dans **Modules > Gestionnaire de modules > Widget Twitter gratuit > Configurer**. Assurez-vous d'avoir entré votre « Nom d'utilisateur Twitter » correct et d'avoir enregistré les paramètres.
2.  **Vérifier le placement du hook :** Vérifiez que le paramètre « Placer dans le hook » est défini sur un hook qui est réellement rendu par votre thème (par exemple, `displayRightColumn`). Certains thèmes peuvent ne pas afficher tous les hooks standard.
3.  **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). Parfois, le cache de PrestaShop empêche le nouveau contenu du module d'apparaître immédiatement.
4.  **Compatibilité du thème :** Bien que le module soit largement compatible, les thèmes très fortement personnalisés peuvent nécessiter des ajustements mineurs. Si le problème persiste, contactez le support MyPresta.eu.

**Q : Le widget apparaît, mais il est vide ou affiche un message d'erreur.**
R :

1.  **Nom d'utilisateur incorrect :** Vérifiez à nouveau votre « Nom d'utilisateur Twitter » dans la configuration du module. Même une petite faute de frappe l'empêchera de récupérer les tweets.
2.  **Compte privé :** Assurez-vous que votre compte Twitter est public. Le widget ne peut pas afficher les tweets des comptes privés (protégés).
3.  **Problèmes d'API Twitter :** Occasionnellement, il peut y avoir des problèmes temporaires avec l'API de Twitter. Attendez un peu et vérifiez à nouveau.

**Q : Comment changer la langue du widget ?**
R : Dans la configuration du module, trouvez le paramètre « Langue » et sélectionnez le code de langue à deux lettres approprié (par exemple, `fr` pour le français, `es` pour l'espagnol).

**Q : Le widget semble trop large/étroit ou trop haut/court.**
R :

1.  **Largeur :** Pour un comportement réactif, laissez le paramètre « Largeur » vide. Si vous avez défini une valeur en pixels spécifique, essayez de la supprimer.
2.  **Hauteur :** Ajustez le paramètre « Hauteur » (en pixels) pour rendre le widget plus haut ou plus court.
3.  **Limite de tweets :** Réduisez la « Limite de tweets » pour rendre le widget plus court si vous avez une hauteur fixe et souhaitez afficher moins de tweets.

**Q : Puis-je afficher des tweets d'un hashtag ou d'une liste spécifique au lieu de mon compte principal ?**
R : Oui, mais cela nécessite une configuration avancée. Vous devrez créer un widget de chronologie intégré personnalisé directement sur la plateforme développeur de Twitter (developer.twitter.com), le configurer pour afficher un hashtag ou une liste, puis obtenir l'« ID du widget » unique qu'il fournit. Vous devrez ensuite entrer cet « ID du widget » dans la configuration du module, en laissant le « Nom d'utilisateur Twitter » vide.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Widget Twitter gratuit » est un module PrestaShop simple conçu pour intégrer la fonctionnalité de chronologie intégrée de Twitter. Il utilise principalement la structure de module standard de PrestaShop, en utilisant le fichier `index.php` principal pour l'installation/désinstallation et la configuration (`getContent()`). Le module injecte un widget Twitter basé sur JavaScript dans le front-office à l'aide d'un template Smarty et d'un fichier CSS pour le style de base. Il s'appuie sur le fichier `widgets.js` de Twitter pour le rendu de la chronologie, qui est chargé de manière asynchrone.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Aucun. L'affichage front-office du module est entièrement géré via des hooks et un template Smarty.
-   **Contrôleurs Admin Back-Office** : Aucun. Toute la configuration est gérée via la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

-   Aucune classe personnalisée ou définition d'`ObjectModel` n'est présente dans ce module. Toute la logique est autonome dans le fichier principal `twitterwidget/index.php`.

### 4.4 Actifs JavaScript (`views/js/`)

-   Aucun fichier JavaScript personnalisé n'est inclus directement dans le répertoire `views/js/` du module.
-   Le module s'appuie fortement sur le script officiel Twitter `widgets.js`, qui est chargé dynamiquement dans le template front-office (`rightcolumn.tpl`) pour rendre la chronologie intégrée. Ce script gère toute la logique complexe de récupération et d'affichage des tweets.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `twitterwidget/twitterwidget.css` :
    *   **Portée** : Style client front-office.
    *   **Principaux composants d'interface utilisateur et conteneurs qu'il stylise** : Ce fichier contient probablement un style minimal, principalement pour garantir que le widget Twitter s'intègre bien avec divers thèmes PrestaShop. Il peut inclure des règles pour le conteneur `.twitter-widget`, des réinitialisations de base ou des ajustements réactifs.
    *   **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger** : Les développeurs peuvent inspecter ce fichier pour identifier des sélecteurs spécifiques (par exemple, `.twitter-widget-container`, `.twitter-timeline`) et les surcharger dans le fichier `custom.css` ou `theme.css` de leur thème pour personnaliser davantage l'apparence du widget.

### 4.6 Structure du template Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :
    *   `twitterwidget/rightcolumn.tpl` :
        *   **Hook(s) rendu(s) dans** : Ce template est conçu pour être rendu dans divers hooks d'affichage, tels que configurés par le marchand (par exemple, `displayRightColumn`, `displayLeftColumn`, `displayFooter`, `displayHeader`, `displayProductButtons`). Les méthodes `hookDisplay*` du module appelleront ce template.
        *   **Sortie du bloc visuel** : Ce template génère la structure HTML requise pour la chronologie intégrée de Twitter. Il inclut généralement une balise `<a>` avec des attributs `data-` (par exemple, `data-tweet-limit`, `data-theme`, `data-link-color`, `data-border-color`, `data-height`, `data-width`, `data-lang`, `data-chrome`, `data-dnt`, `data-show-replies`, `data-autoplay`) que le script `widgets.js` de Twitter lit pour rendre la chronologie. Il inclut également la balise `<script>` pour charger `widgets.js` de manière asynchrone.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    *   Ce module ne crée aucune table SQL personnalisée.
    *   Les paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide des clés de configuration PrestaShop standard (par exemple, `TWITTERWIDGET_USERNAME`, `TWITTERWIDGET_WIDGETID`, `TWITTERWIDGET_THEME`, etc.).
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Potentiellement utilisé pour charger le script du widget Twitter globalement, ou pour afficher le widget dans la zone d'en-tête. |
| `displayRightColumn` | Dans la barre latérale droite des pages qui en ont une. | Affiche le widget Twitter dans la colonne de droite. |
| `displayLeftColumn` | Dans la barre latérale gauche des pages qui en ont une. | Affiche le widget Twitter dans la colonne de gauche. |
| `displayFooter` | Dans la section du pied de page de chaque page. | Affiche le widget Twitter dans le pied de page. |
| `displayProductButtons` | Sur la page produit, généralement près du bouton d'ajout au panier ou de la description du produit. | Affiche le widget Twitter sur les pages produits. |
| `actionFrontControllerSetMedia` | Après que le contrôleur frontal a défini ses médias, permettant aux modules d'ajouter les leurs. | Utilisé pour enregistrer les fichiers CSS et potentiellement JS du module (bien que ce module charge le JS de Twitter directement dans le TPL). |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Widget Twitter gratuit », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question que vous pourriez avoir.
