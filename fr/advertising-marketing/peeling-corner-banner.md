---
title: "Bannière d'angle déroulante - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Bannière d'angle déroulante par MyPresta.eu."
sidebar:
  label: "Bannière d'angle déroulante - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Peeling Corner Banner sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/peeling-corner-banner.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/peeling-corner-banner/)
>
> ---


# Bannière d'angle déroulante

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement nécessaire.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après avoir installé le module, cliquez sur "Configurer" pour accéder à ses paramètres. C'est ici que vous personnaliserez l'apparence et le comportement de votre bannière déroulante.

#### **Image pour le coin (petite image)**

- **Ce que fait ce paramètre :** C'est la petite image qui apparaît sur le coin recourbé de votre page. C'est l'accroche initiale qui attire l'œil du client.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une image est téléchargée :* Cette image sera affichée sur le petit coin recourbé.
  - *Lorsqu'aucune image n'est téléchargée :* Le coin peut apparaître vide ou utiliser un style par défaut, ce qui est moins efficace.
- **Valeur recommandée :** Téléchargez une petite image attrayante (par exemple, une petite icône, une étiquette "Soldes" ou un extrait de logo) qui fait allusion à la promotion sans tout révéler.
- **Scénario / exemple de marchand :** Vous organisez une vente d'été. Vous pouvez télécharger une petite image d'une icône de soleil ou un petit badge "SOLDES" pour ce paramètre.

#### **Image pour la bannière (grande image)**

- **Ce que fait ce paramètre :** C'est l'image de bannière principale qui est révélée lorsqu'un client survole le coin. C'est là que votre message principal, l'image du produit ou l'appel à l'action doit se trouver.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une image est téléchargée :* Cette image plus grande sera affichée lorsque le coin se déroule.
  - *Lorsqu'aucune image n'est téléchargée :* La zone déroulée sera vide, rendant le module inefficace.
- **Valeur recommandée :** Téléchargez une image claire et convaincante qui contient votre message promotionnel complet, une photo de produit ou un appel à l'action fort. Assurez-vous qu'elle est dimensionnée de manière appropriée pour une bannière (par exemple, 200-300px de large, hauteur similaire).
- **Scénario / exemple de marchand :** En suivant l'exemple de la vente d'été, cette image serait une bannière complète annonçant "Soldes d'été ! Jusqu'à 50 % de réduction sur tous les maillots de bain !" avec des photos de produits attrayantes.

#### **Lien pour la bannière**

- **Ce que fait ce paramètre :** C'est l'URL (adresse web) vers laquelle les clients seront dirigés lorsqu'ils cliqueront sur la bannière révélée.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une URL valide est saisie :* Cliquer sur la bannière mènera le client à cette page.
  - *Lorsqu'il est laissé vide ou qu'une URL invalide est saisie :* Cliquer sur la bannière pourrait ne rien faire ou mener à une page d'erreur, frustrant les clients.
- **Valeur recommandée :** Fournissez toujours une URL complète et valide (par exemple, `https://votreboutique.com/categorie-soldes-ete`).
- **Scénario / exemple de marchand :** Vous lieriez cela à votre page de catégorie "Soldes d'été" dédiée ou à une page de produit spécifique que vous souhaitez mettre en évidence.

#### **Position de la bannière**

- **Ce que fait ce paramètre :** Cela contrôle dans quel coin de votre site web la bannière déroulante apparaît.
- **Effet de la modification de ce paramètre :**
  - *Gauche :* La bannière apparaîtra dans le coin supérieur gauche de la fenêtre du navigateur.
  - *Droite :* La bannière apparaîtra dans le coin supérieur droit de la fenêtre du navigateur.
- **Valeur recommandée :** Choisissez le coin qui correspond le mieux au design de votre site web et n'obstrue pas les éléments importants. "Droite" est souvent une bonne valeur par défaut car il est moins courant que la navigation ou les logos s'y trouvent.
- **Scénario / exemple de marchand :** Si votre logo principal et votre navigation sont à gauche, vous choisiriez "Droite" pour éviter l'encombrement visuel.

#### **Activer/Désactiver le module**

- **Ce que fait ce paramètre :** C'est un interrupteur principal pour activer ou désactiver la fonction de bannière déroulante sans désinstaller le module.
- **Effet de la modification de ce paramètre :**
  - *Activé :* La bannière déroulante sera visible sur votre front office selon vos autres paramètres.
  - *Désactivé :* La bannière déroulante n'apparaîtra pas sur votre front office.
- **Valeur recommandée :** "Activé" lorsque vous souhaitez utiliser la bannière, "Désactivé" si vous devez la masquer temporairement pour la maintenance ou pendant des périodes spécifiques.
- **Scénario / exemple de marchand :** Vous avez terminé votre promotion des fêtes et souhaitez masquer temporairement la bannière jusqu'à votre prochaine campagne. Vous la désactiveriez ici.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Image pour le coin | Télécharger une petite image d'accroche | Petite image sur le coin recourbé. Attire l'attention. |
| Configuration du module | Image pour la bannière | Télécharger une image promotionnelle plus grande | Image de bannière principale révélée au survol. Contient le message principal. |
| Configuration du module | Lien pour la bannière | URL complète (par exemple, `https://votreboutique.com/promo`) | URL de destination lorsque la bannière est cliquée. Dirige le trafic. |
| Configuration du module | Position de la bannière | Droite | Quel coin de l'écran la bannière apparaît (Gauche/Droite). |
| Configuration du module | Activer/Désactiver le module | Activé | Interrupteur principal pour afficher ou masquer la bannière sur la boutique. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Ma bannière n'apparaît pas après la configuration. Que dois-je faire ?**
R :

1.  **Vérifiez "Activer/Désactiver le module" :** Assurez-vous que le module est activé dans sa configuration.
2.  **Vérifiez les téléchargements d'images :** Assurez-vous que les deux "Image pour le coin" et "Image pour la bannière" ont été téléchargées avec succès.
3.  **Videz le cache :** Allez dans **Paramètres avancés > Performances** dans votre back office PrestaShop et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions plus anciennes). Parfois, d'anciens fichiers mis en cache empêchent l'affichage du nouveau contenu du module.
4.  **Hook du module :** Le module devrait automatiquement s'accrocher à `displayHeader`. S'il ne s'affiche pas, assurez-vous qu'il est correctement accroché. Vous pouvez vérifier cela sous **Design > Positions** (ou **Modules > Positions**). Recherchez `peelingcornerbanner` et confirmez qu'il est associé à `displayHeader`.

**Q : Les images de la bannière semblent floues ou étirées.**
R : Cela signifie généralement que les images que vous avez téléchargées ne sont pas optimisées pour la taille d'affichage de la bannière.

1.  **Dimensions de l'image :** Vérifiez la taille réelle de la bannière lorsqu'elle se déroule (vous devrez peut-être utiliser les outils de développement de votre navigateur). Ensuite, redimensionnez votre "Image pour la bannière" pour qu'elle corresponde à ces dimensions ou soit légèrement plus grande, garantissant une bonne qualité.
2.  **Taille du fichier :** Bien que la qualité soit importante, gardez la taille des fichiers image aussi petite que possible (moins de 100-200 Ko) pour assurer un chargement rapide de la page. Utilisez des outils comme TinyPNG ou des optimiseurs d'images en ligne.

**Q : La bannière apparaît, mais cliquer dessus ne fait rien.**
R :

1.  **Vérifiez "Lien pour la bannière" :** Retournez à la configuration du module et vérifiez l'URL que vous avez saisie pour le lien de la bannière. Assurez-vous qu'il s'agit d'une URL complète et valide (par exemple, `https://www.votreboutique.com/categorie/produit.html`).
2.  **Testez le lien :** Copiez et collez le lien directement dans votre navigateur pour vous assurer qu'il fonctionne correctement en dehors du module.

**Q : La bannière chevauche d'autres éléments de ma page.**
R :

1.  **Changez la position :** Essayez de changer la "Position de la bannière" de Gauche à Droite (ou vice-versa) dans la configuration du module.
2.  **Conflits de thème :** Si changer la position n'aide pas, il peut s'agir d'un conflit avec le CSS de votre thème PrestaShop spécifique. Cela pourrait nécessiter qu'un webmaster ajuste le CSS du module ou du thème (voir la section 7 pour les détails du développeur).

**Q : Puis-je avoir plusieurs bannières déroulantes ?**
R : Non, ce module est conçu pour afficher une seule bannière déroulante à la fois. Si vous en avez besoin de plusieurs, vous devrez dupliquer et modifier le module, ce qui nécessite une expertise de développeur.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module Bannière d'angle déroulante (`pcb`) est un module PrestaShop simple principalement conçu pour injecter un effet visuel piloté par JavaScript dans le front-office. Il suit une structure de module PrestaShop de base, utilisant la classe `Module` pour l'installation, la désinstallation et la configuration (`getContent()`). La fonctionnalité principale repose sur un fichier JavaScript personnalisé (`peelback.js`) qui gère la manipulation du DOM et l'animation, et un template Smarty (`header.tpl`) pour rendre la structure HTML initiale dans le hook `displayHeader`. Les paramètres de configuration sont stockés dans `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

- Pas de contrôleurs Front-Office personnalisés.
- Pas de contrôleurs d'administration Back-Office personnalisés.
  La configuration du module est gérée directement dans la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

- Pas de classes personnalisées ni de définitions `ObjectModel`.
  Toute la configuration est gérée via `Configuration::get()` et `Configuration::updateValue()`.

### 4.4 Actifs JavaScript (`views/js/`)

- `pcb/peelback.js`
  - **Portée :** Front-office.
  - **Description :** C'est le fichier JavaScript principal responsable de l'animation de la bannière d'angle déroulante. Il initialise probablement un plugin jQuery ou un script personnalisé qui :
    - Détecte la présence de la structure HTML de la bannière (par exemple, une `div` avec un ID spécifique comme `#peelback`).
    - Attache des écouteurs d'événements, principalement `mouseover` et `mouseout`, à l'élément du coin.
    - Au `mouseover`, il anime l'image de la bannière plus grande pour qu'elle "se déroule" en vue (par exemple, en modifiant les propriétés CSS comme `width`, `height`, `top`, `left`, `z-index`).
    - Au `mouseout`, il anime la bannière pour qu'elle revienne à son état initial recourbé.
    - Gère l'événement de clic sur la bannière pour rediriger vers l'URL configurée.
    - Il utilise probablement la fonction `animate()` de jQuery pour des transitions fluides.

### 4.5 Feuilles de style CSS (`views/css/`)

- Aucun fichier CSS dédié n'est trouvé dans l'archive du module.
  Cela implique que le style de la bannière (position initiale, dimensions, z-index, etc.) est soit :
  1. Injecté directement via des styles en ligne dans le template `header.tpl`.
  2. Entièrement géré par le JavaScript, qui définit dynamiquement les propriétés CSS.
  3. Repose sur un style de navigateur par défaut minimal ou s'attend à ce que le thème fournisse des réinitialisations de base.
     Les développeurs souhaitant personnaliser l'apparence devront inspecter le HTML généré et le JavaScript pour les styles en ligne ou les classes/styles appliqués dynamiquement.

### 4.6 Structure du template Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :
  - `pcb/header.tpl`
    - **Hook :** `displayHeader` (ou `displayTop` dans les versions plus anciennes, mais `displayHeader` est la norme pour injecter des éléments globaux).
    - **Sortie :** Ce template rend la structure HTML initiale de la bannière déroulante. Il inclut généralement :
      - Une `div` conteneur pour l'ensemble de la bannière.
      - Une balise `img` pour la petite image du coin.
      - Une balise `img` pour l'image de la bannière plus grande (initialement cachée ou partiellement cachée).
      - Une balise `<a>` enveloppant ces images, liée à l'URL configurée.
      - Il utilisera probablement des variables Smarty passées depuis la méthode `hookDisplayHeader()` du module pour afficher les URL des images, l'URL du lien et la position de la bannière (gauche/droite).
      - Peut contenir des balises `<style>` en ligne ou s'appuyer sur `peelback.js` pour appliquer dynamiquement des styles.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne crée pas de tables SQL personnalisées.
  - Les paramètres de configuration sont stockés dans la table `ps_configuration` (ou préfixe `_configuration`) avec des clés telles que :
    - `PCB_CORNER_IMAGE` (chemin vers la petite image du coin)
    - `PCB_BANNER_IMAGE` (chemin vers la grande image de la bannière)
    - `PCB_BANNER_LINK` (l'URL de la bannière)
    - `PCB_BANNER_POSITION` (par exemple, 'left' ou 'right')
    - `PCB_ENABLED` (1 pour activé, 0 pour désactivé)
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Exécuté dans la section `<head>` de chaque page. | Injecte la structure HTML nécessaire pour la bannière et enregistre le script `peelback.js`. |
| `actionFrontControllerSetMedia` | Exécuté lorsque les médias (JS/CSS) sont définis pour un contrôleur frontal. | (Utilisé implicitement par `displayHeader` ou `hookDisplayHeader` pour enregistrer JS/CSS, bien que non explicitement listé comme un hook séparé dans la méthode `install()` du module, c'est ainsi que PrestaShop gère l'enregistrement des médias). |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module Bannière d'angle déroulante, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à assurer le bon fonctionnement et l'amélioration continue de nos modules.
