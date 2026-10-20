---
title: "Loi sur les cookies de l'Union Européenne Pro - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Loi sur les cookies de l'Union Européenne Pro par MyPresta.eu."
sidebar:
  label: "Loi sur les cookies de l'Union Européenne Pro - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module European Union Cookie Law Pro sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/european-union-cookie-law-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/european-union-cookie-law-pro/)
>
> ---


# Loi sur les cookies de l'Union Européenne Pro

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration spéciale du serveur n'est généralement nécessaire.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Loi sur les cookies de l'Union Européenne Pro)

Ceci est l'écran de configuration principal où vous définirez l'apparence, le contenu et le comportement de votre avis de cookies. Le module offre une fonction de prévisualisation en direct, vous permettant de voir vos modifications en temps réel dans le back office avant de les enregistrer.

#### **Paramètres généraux**

- **Activer le module Loi sur les cookies :**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver l'avis de cookies sur l'ensemble de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (OUI) :* L'avis de cookies sera affiché aux visiteurs selon vos autres paramètres.
    - *Lorsqu'il est désactivé (NON) :* L'avis de cookies n'apparaîtra pas sur votre boutique, et aucun consentement aux cookies ne sera collecté par ce module.
  - **Valeur recommandée :** OUI (pour assurer la conformité légale).
  - **Scénario / exemple de marchand :** Vous le désactiveriez temporairement pendant la maintenance ou si vous testez une solution de cookies différente.
- **Durée d'expiration des cookies (en jours) :**

  - **Ce que fait ce paramètre :** Détermine la durée pendant laquelle le consentement aux cookies d'un utilisateur est mémorisé par votre boutique. Après cette période, l'utilisateur sera invité à donner son consentement à nouveau.
  - **Effet de la modification de ce paramètre :**
    - *Si défini à 365 :* Le consentement d'un utilisateur sera valide pendant un an.
    - *Si défini à 30 :* Le consentement sera valide pendant un mois.
  - **Valeur recommandée :** 365 (un an) est une période courante et raisonnable pour la plupart des réglementations. Vérifiez les lois locales pour les exigences spécifiques.
  - **Scénario / exemple de marchand :** Si vos réglementations locales exigent un nouveau consentement tous les 6 mois, vous le définiriez à 180.
- **Afficher sur les appareils mobiles :**

  - **Ce que fait ce paramètre :** Contrôle si l'avis de cookies est affiché aux utilisateurs naviguant sur les smartphones et les tablettes.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (OUI) :* L'avis de cookies apparaîtra sur les appareils mobiles, adaptant sa mise en page pour les écrans plus petits.
    - *Lorsqu'il est désactivé (NON) :* Les utilisateurs mobiles ne verront pas l'avis de cookies.
  - **Valeur recommandée :** OUI (pour une conformité totale sur tous les appareils).
  - **Scénario / exemple de marchand :** Vous devriez toujours l'activer, car les utilisateurs mobiles sont soumis aux mêmes lois sur la confidentialité.
- **Afficher uniquement aux visiteurs des pays de l'UE :**

  - **Ce que fait ce paramètre :** S'il est activé, l'avis de cookies ne sera affiché qu'aux visiteurs dont l'adresse IP indique qu'ils naviguent depuis un État membre de l'UE.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (OUI) :* Les visiteurs non-UE ne verront pas la bannière.
    - *Lorsqu'il est désactivé (NON) :* Tous les visiteurs, quelle que soit leur localisation, verront la bannière.
  - **Valeur recommandée :** Dépend de votre public cible et de vos conseils juridiques. Si vous ne servez que des clients de l'UE, OUI pourrait être approprié. Si vous servez un public mondial et que vous voulez être sûr, NON est préférable.
  - **Scénario / exemple de marchand :** Une boutique australienne servant principalement des clients australiens pourrait activer cette option pour éviter d'afficher la bannière à son public principal, tout en respectant la conformité pour les quelques visiteurs de l'UE. Une boutique mondiale pourrait la désactiver pour être universellement conforme.

#### **Contenu et liens**

- **Message de la Loi sur les cookies :**

  - **Ce que fait ce paramètre :** C'est le texte principal affiché dans l'avis de cookies, informant les utilisateurs de l'utilisation des cookies. Vous pouvez utiliser un éditeur de texte enrichi pour le formater.
  - **Effet de la modification de ce paramètre :** Le texte que vous saisissez ici sera le message principal que vos clients liront.
  - **Valeur recommandée :** Un message clair et concis comme « Ce site web utilise des cookies pour vous garantir la meilleure expérience sur notre site. [En savoir plus] »
  - **Scénario / exemple de marchand :** Vous pourriez inclure des informations sur les types de cookies utilisés (par exemple, « Nous utilisons des cookies pour l'analyse et pour améliorer votre expérience d'achat. »).
- **Texte du bouton « Accepter » :**

  - **Ce que fait ce paramètre :** Définit le texte affiché sur le bouton sur lequel les utilisateurs cliquent pour accepter les cookies.
  - **Effet de la modification de ce paramètre :** Modifie l'étiquette du bouton d'acceptation.
  - **Valeur recommandée :** « Accepter », « Compris », « OK », « J'ai compris ».
  - **Scénario / exemple de marchand :** Vous pourriez utiliser « Accepter et continuer » pour encourager les utilisateurs à poursuivre.
- **Texte du bouton « Plus d'infos » :**

  - **Ce que fait ce paramètre :** Définit le texte affiché sur le bouton sur lequel les utilisateurs cliquent pour en savoir plus sur votre politique de cookies.
  - **Effet de la modification de ce paramètre :** Modifie l'étiquette du bouton d'information.
  - **Valeur recommandée :** « En savoir plus », « Plus d'infos », « Politique de confidentialité ».
  - **Scénario / exemple de marchand :** Vous pourriez utiliser « Paramètres des cookies » si vous avez un système détaillé de gestion des préférences.
- **Lien vers la page de politique de confidentialité :**

  - **Ce que fait ce paramètre :** Spécifie l'URL où les utilisateurs peuvent trouver votre politique de confidentialité ou de cookies complète. Ce lien sera attaché au bouton « Plus d'infos » ou à une partie spécifique de votre message.
  - **Effet de la modification de ce paramètre :** Lorsque les utilisateurs cliquent sur le bouton « Plus d'infos », ils seront redirigés vers cette URL.
  - **Valeur recommandée :** L'URL complète de votre page CMS (par exemple, `https://votreboutique.com/content/3-conditions-generales-de-vente`).
  - **Scénario / exemple de marchand :** Vous créez une page CMS dédiée dans PrestaShop (Design > Pages) pour votre « Politique de cookies » et la liez ici.

#### **Options d'affichage et style**

- **Position de l'avis de cookies :**

  - **Ce que fait ce paramètre :** Détermine où l'avis de cookies apparaît sur votre site web.
  - **Effet de la modification de ce paramètre :**
    - *Barre supérieure :* La bannière apparaît en haut de la fenêtre du navigateur.
    - *Barre inférieure :* La bannière apparaît en bas de la fenêtre du navigateur.
    - *Modale centrale :* Une fenêtre pop-up au milieu de l'écran.
    - *Boîte flottante (Haut-Gauche, Haut-Droit, Bas-Gauche, Bas-Droit) :* Une boîte plus petite et fixe dans l'un des coins.
  - **Valeur recommandée :** La barre inférieure ou la boîte flottante sont généralement moins intrusives. La modale centrale est très visible mais peut être perturbatrice.
  - **Scénario / exemple de marchand :** Une boutique de mode pourrait préférer une « Barre inférieure » subtile pour maintenir l'attention sur les produits, tandis qu'une entreprise de services pourrait utiliser une « Modale centrale » pour une visibilité maximale.
- **Couleur de fond :**

  - **Ce que fait ce paramètre :** Définit la couleur de fond principale de la bannière d'avis de cookies.
  - **Effet de la modification de ce paramètre :** Modifie l'arrière-plan visuel de l'avis.
  - **Valeur recommandée :** Une couleur qui contraste bien avec votre texte et correspond à votre marque.
  - **Scénario / exemple de marchand :** Utilisez la couleur principale de votre marque ou un gris neutre.
- **Couleur du texte :**

  - **Ce que fait ce paramètre :** Définit la couleur du texte du message principal dans l'avis.
  - **Effet de la modification de ce paramètre :** Modifie la couleur du texte du message.
  - **Valeur recommandée :** Une couleur qui offre une bonne lisibilité par rapport à l'arrière-plan choisi.
  - **Scénario / exemple de marchand :** Texte blanc sur fond sombre, ou texte gris foncé sur fond clair.
- **Couleur du lien :**

  - **Ce que fait ce paramètre :** Définit la couleur de tous les liens dans votre message de cookies (par exemple, le lien « En savoir plus » s'il fait partie du message).
  - **Effet de la modification de ce paramètre :** Modifie la couleur du texte cliquable dans le message.
  - **Valeur recommandée :** La couleur d'accentuation de votre marque ou un bleu standard pour les liens.
  - **Scénario / exemple de marchand :** Utilisez une couleur vive pour faire ressortir le lien « En savoir plus ».
- **Couleur de fond du bouton :**

  - **Ce que fait ce paramètre :** Définit la couleur de fond des boutons « Accepter » et « Plus d'infos ».
  - **Effet de la modification de ce paramètre :** Modifie l'arrière-plan visuel des boutons.
  - **Valeur recommandée :** Une couleur qui rend les boutons clairement visibles et cliquables.
  - **Scénario / exemple de marchand :** Utilisez la couleur d'appel à l'action de votre marque.
- **Couleur du texte du bouton :**

  - **Ce que fait ce paramètre :** Définit la couleur du texte sur les boutons « Accepter » et « Plus d'infos ».
  - **Effet de la modification de ce paramètre :** Modifie la couleur des étiquettes des boutons.
  - **Valeur recommandée :** Une couleur qui offre un bon contraste avec l'arrière-plan du bouton.
  - **Scénario / exemple de marchand :** Texte blanc sur un bouton coloré, ou texte noir sur un bouton clair.
- **Couleur de fond du bouton au survol :**

  - **Ce que fait ce paramètre :** Définit la couleur de fond des boutons lorsqu'un utilisateur passe sa souris dessus.
  - **Effet de la modification de ce paramètre :** Fournit un retour visuel à l'utilisateur indiquant que le bouton est interactif.
  - **Valeur recommandée :** Une nuance légèrement plus foncée ou plus claire de la couleur de fond normale du bouton.
  - **Scénario / exemple de marchand :** Un changement subtil de couleur pour indiquer l'interactivité.
- **Couleur du texte du bouton au survol :**

  - **Ce que fait ce paramètre :** Définit la couleur du texte des boutons lorsqu'un utilisateur passe sa souris dessus.
  - **Effet de la modification de ce paramètre :** Fournit un retour visuel.
  - **Valeur recommandée :** Souvent la même que la couleur de texte normale du bouton, ou une couleur contrastante si l'arrière-plan change de manière significative.
  - **Scénario / exemple de marchand :** Si l'arrière-plan de votre bouton devient sombre au survol, vous pourriez changer le texte en blanc.
- **Rayon de la bordure (px) :**

  - **Ce que fait ce paramètre :** Contrôle l'arrondi des coins de l'avis de cookies et de ses boutons. Une valeur de 0 signifie des coins nets, des valeurs plus élevées signifient des coins plus arrondis.
  - **Effet de la modification de ce paramètre :**
    - *0px :* Coins nets et carrés.
    - *5px :* Coins légèrement arrondis.
    - *20px :* Coins très arrondis, en forme de pilule.
  - **Valeur recommandée :** 0-5px pour un look moderne et épuré ; plus élevé pour une sensation plus douce et plus conviviale.
  - **Scénario / exemple de marchand :** Faites correspondre cela au `border-radius` utilisé dans votre thème pour la cohérence.
- **Effet verre :**

  - **Ce que fait ce paramètre :** Applique un effet translucide, de verre dépoli, à l'arrière-plan de l'avis de cookies.
  - **Effet de la modification de ce paramètre :** Rend l'arrière-plan légèrement transparent et flou, permettant au contenu derrière de transparaître subtilement.
  - **Valeur recommandée :** Essayez-le et voyez s'il correspond à votre design. Il peut ajouter une touche premium.
  - **Scénario / exemple de marchand :** Utilisez-le si votre thème a une esthétique moderne et minimaliste.
- **Fond dégradé :**

  - **Ce que fait ce paramètre :** Vous permet d'utiliser une transition douce entre deux couleurs pour l'arrière-plan de l'avis de cookies au lieu d'une seule couleur unie.
  - **Effet de la modification de ce paramètre :** Crée un mélange de couleurs visuellement attrayant. Vous aurez généralement des options pour une couleur de début et de fin.
  - **Valeur recommandée :** Utilisez des couleurs qui se complètent et complètent votre marque.
  - **Scénario / exemple de marchand :** Une boutique de technologie pourrait utiliser un dégradé bleu-violet pour un look moderne.
- **Couleur de fond de la superposition (pour la modale centrale) :**

  - **Ce que fait ce paramètre :** Lors de l'utilisation de la position « Modale centrale », cela définit la couleur de la couche semi-transparente qui couvre le reste de la page derrière la modale.
  - **Effet de la modification de ce paramètre :** Contrôle la focalisation visuelle sur la modale. Une superposition plus foncée et plus opaque fait ressortir davantage la modale.
  - **Valeur recommandée :** Un noir semi-transparent (`rgba(0,0,0,0.7)`) ou une teinte foncée qui correspond à votre thème.
  - **Scénario / exemple de marchand :** Utilisez une superposition sombre et légèrement transparente pour vous assurer que la modale de cookies est la principale cible lorsque celle-ci apparaît.
- **CSS personnalisé :**

  - **Ce que fait ce paramètre :** Fournit une zone de texte où vous pouvez ajouter vos propres règles CSS personnalisées pour styliser davantage l'avis de cookies, en remplaçant les styles par défaut du module.
  - **Effet de la modification de ce paramètre :** Permet une personnalisation avancée au-delà des options fournies.
  - **Valeur recommandée :** Laissez vide, sauf si vous avez des exigences de conception spécifiques et des connaissances en CSS.
  - **Scénario / exemple de marchand :** Vous pourriez l'utiliser pour modifier la taille de la police du message, ajouter une ombre ou ajuster le rembourrage si les options intégrées ne suffisent pas.

#### **Préréglages et prévisualisation en direct**

- **Charger un préréglage :**

  - **Ce que fait ce paramètre :** Vous permet d'appliquer rapidement un ensemble prédéfini d'options de style (couleurs, positions, effets) à partir d'une bibliothèque de designs prêts à l'emploi.
  - **Effet de la modification de ce paramètre :** Transforme instantanément l'apparence de votre avis de cookies pour correspondre au préréglage choisi. Tous les paramètres de style individuels seront mis à jour.
  - **Valeur recommandée :** Parcourez les préréglages pour en trouver un qui correspond étroitement à votre marque, puis affinez-le.
  - **Scénario / exemple de marchand :** Vous recherchez une bannière sombre et minimaliste. Vous sélectionnez un préréglage « Thème sombre » et ajustez ensuite les nuances exactes de noir et de gris.
- **Prévisualisation en direct :**

  - **Ce que fait ce paramètre :** Cette section de la page de configuration affiche un aperçu en temps réel de votre avis de cookies au fur et à mesure que vous ajustez les paramètres.
  - **Effet de la modification de ce paramètre :** Vous montre exactement à quoi ressemblera votre bannière sur le front office, sans avoir besoin d'enregistrer et de rafraîchir votre boutique.
  - **Valeur recommandée :** Utilisez toujours la prévisualisation en direct pour vérifier vos choix de conception avant d'enregistrer.
  - **Scénario / exemple de marchand :** Vous expérimentez différentes couleurs de boutons ; la prévisualisation en direct vous montre immédiatement quelle combinaison est la plus esthétique.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer le module Loi sur les cookies | OUI | Interrupteur principal pour l'avis de cookies. |
| | Durée d'expiration des cookies (jours) | 365 | Durée de mémorisation du consentement. |
| | Afficher sur les appareils mobiles | OUI | Afficher la bannière sur les téléphones/tablettes. |
| | Afficher uniquement aux visiteurs de l'UE | NON (pour une conformité globale) | Cibler les visiteurs de l'UE ou tous les visiteurs. |
| | Message de la Loi sur les cookies | Personnalisable | Texte principal de l'avis de cookies. |
| | Texte du bouton « Accepter » | « Accepter » | Étiquette du bouton de consentement. |
| | Texte du bouton « Plus d'infos » | « En savoir plus » | Étiquette du bouton d'information. |
| | Lien vers la page de politique de confidentialité | Votre URL de politique | URL pour la politique de cookies détaillée. |
| | Position de l'avis de cookies | Barre inférieure / Boîte flottante | Où la bannière apparaît (Barre supérieure/inférieure, Modale centrale, Boîte flottante). |
| | Couleur de fond | Personnalisable | Couleur de fond principale de l'avis. |
| | Couleur du texte | Personnalisable | Couleur du texte du message. |
| | Couleur du lien | Personnalisable | Couleur des liens dans le message. |
| | Couleur de fond du bouton | Personnalisable | Couleur de fond des boutons d'action. |
| | Couleur du texte du bouton | Personnalisable | Couleur du texte sur les boutons d'action. |
| | Couleur de fond du bouton au survol | Personnalisable | Couleur de fond au survol du bouton. |
| | Couleur du texte du bouton au survol | Personnalisable | Couleur du texte au survol du bouton. |
| | Rayon de la bordure (px) | 0-5 | Arrondi des coins. |
| | Effet verre | NON | Ajoute un effet translucide et dépoli. |
| | Fond dégradé | NON | Utilise un dégradé de couleurs pour l'arrière-plan. |
| | Couleur de fond de la superposition | Sombre semi-transparent | Couleur de la superposition d'arrière-plan pour la modale centrale. |
| | CSS personnalisé | Vide | Pour les surcharges de style avancées. |
| | Charger un préréglage | Choisir un | Appliquer des options de style prédéfinies. |
| | Prévisualisation en direct | N/A | Retour visuel en temps réel des paramètres. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : J'ai configuré le module, mais la bannière de cookies n'apparaît pas sur ma boutique.**
R :

1.  **Vérifiez « Activer le module Loi sur les cookies » :** Assurez-vous qu'il est réglé sur OUI dans la configuration du module.
2.  **Videz le cache :** Allez dans **Paramètres avancés > Performances** dans votre back office PrestaShop et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures). Le cache du navigateur peut également nécessiter d'être vidé (Ctrl+F5 ou Cmd+R).
3.  **Vérifiez le paramètre Pays de l'UE :** Si « Afficher uniquement aux visiteurs des pays de l'UE » est activé, assurez-vous que vous testez depuis une adresse IP de l'UE. Essayez de désactiver temporairement ce paramètre pour les tests.
4.  **Compatibilité du thème :** Bien que le module soit conçu pour être compatible, certains thèmes très personnalisés peuvent avoir des conflits. Vérifiez la console de développement de votre navigateur (F12) pour les erreurs JavaScript.

**Q : La bannière a un aspect différent sur ma boutique que dans la prévisualisation en direct.**
R :

1.  **Videz le cache :** Videz toujours votre cache PrestaShop (**Paramètres avancés > Performances**) après avoir effectué des modifications. Le cache de votre navigateur peut également afficher une version plus ancienne.
2.  **Conflits CSS personnalisés :** Si vous avez ajouté du « CSS personnalisé » ou si votre thème a des styles conflictuels, ils peuvent remplacer les paramètres du module. Supprimez temporairement votre CSS personnalisé pour voir si cela résout le problème.
3.  **Surcharges de thème :** Votre thème peut avoir des règles CSS spécifiques qui sont plus spécifiques que celles du module. Un développeur peut vous aider à identifier et à résoudre ces problèmes.

**Q : Comment traduire le message des cookies et les textes des boutons dans d'autres langues ?**
R :

1.  Allez dans **International > Traductions** dans votre back office PrestaShop.
2.  Sélectionnez « Traductions des modules installés » comme Type de traduction.
3.  Choisissez votre thème.
4.  Sélectionnez la langue que vous souhaitez traduire.
5.  Recherchez le module « Loi sur les cookies de l'Union Européenne Pro » dans la liste. Vous pourrez y traduire le « Message de la Loi sur les cookies », le « Texte du bouton Accepter » et le « Texte du bouton Plus d'infos ».

**Q : La bannière de cookies couvre une partie importante de mon site web (par exemple, un widget de chat, un élément de menu).**
R :

1.  **Ajustez la position :** Expérimentez avec le paramètre « Position de l'avis de cookies ». Si une barre inférieure couvre un widget de chat, essayez une barre supérieure ou une boîte flottante dans un coin différent.
2.  **CSS personnalisé (Avancé) :** Si aucune position ne fonctionne, un développeur peut utiliser le champ « CSS personnalisé » pour ajuster la propriété `z-index` de la bannière de cookies ou de l'élément en conflit afin de s'assurer que le bon élément est au-dessus.

**Q : Ce module gère-t-il différentes catégories de cookies (par exemple, essentiels, analytiques, marketing) ?**
R : Ce module se concentre principalement sur l'affichage d'un avis général de consentement aux cookies et la collecte d'un consentement unique « accepter » ou « refuser » (en n'acceptant pas). Pour une gestion plus avancée et granulaire des catégories de cookies (où les utilisateurs peuvent sélectionner les types de cookies qu'ils autorisent), vous auriez généralement besoin d'une solution plus complexe ou d'une intégration avec une plateforme de gestion du consentement (CMP) dédiée. Ce module est conçu pour une conformité simple.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique pour les développeurs et les webmasters souhaitant comprendre, personnaliser ou déboguer le module « Loi sur les cookies de l'Union Européenne Pro ».

### 4.1 Aperçu de l'architecture

Le module `uecookiepro` suit une architecture de module PrestaShop standard, exploitant principalement la classe `Module` pour sa fonctionnalité principale et `getContent()` pour la configuration du back-office. Il injecte son contenu front-office directement dans un hook choisi, rendant dynamiquement la bannière de cookies en fonction des paramètres de configuration. Le style est géré via des styles en ligne et potentiellement du CSS personnalisé, avec JavaScript gérant l'interaction utilisateur et le stockage du consentement.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient aucun contrôleur front-office ou back-office personnalisé. Toute la configuration est gérée dans la méthode `getContent()` du fichier principal du module, et l'affichage front-office est géré via des hooks.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée ou instance `ObjectModel`. Toute la configuration est stockée directement dans la table `ps_configuration` à l'aide de clés de configuration PrestaShop standard.

### 4.4 Actifs JavaScript (`views/js/`)

Le module inclut plusieurs fichiers JavaScript, principalement pour les améliorations de la configuration du back-office et l'interaction front-office.

-   `uecookiepro/jscolor/jscolor.js` :
    -   **Portée :** Back-office.
    -   **Responsabilité :** Fournit la fonctionnalité de sélecteur de couleurs utilisée dans le formulaire de configuration du module, permettant aux marchands de sélectionner visuellement les couleurs de la bannière.
-   `uecookiepro/tinymce-original.js` :
    -   **Portée :** Back-office.
    -   **Responsabilité :** La bibliothèque principale de l'éditeur de texte enrichi TinyMCE. Elle est utilisée pour le champ « Message de la Loi sur les cookies », permettant aux marchands de formater leur message avec du HTML.
-   `uecookiepro/tinymce16.inc.js` :
    -   **Portée :** Back-office.
    -   **Responsabilité :** Un fichier d'inclusion contenant probablement des paramètres d'initialisation et de configuration spécifiques de TinyMCE adaptés aux environnements PrestaShop 1.6.x, garantissant que l'éditeur fonctionne correctement dans la configuration du module.
-   `uecookiepro/views/js/patterns.js` :
    -   **Portée :** Back-office.
    -   **Responsabilité :** Contient probablement des motifs ou des configurations prédéfinis pour les préréglages de style du module, utilisés pour charger rapidement différents thèmes visuels pour la bannière de cookies.
-   `uecookiepro/views/js/presets-community.js` :
    -   **Portée :** Back-office.
    -   **Responsabilité :** Contient des préréglages supplémentaires contribués par la communauté ou étendus pour le style visuel de la bannière de cookies, offrant plus d'options de conception prêtes à l'emploi.
-   `uecookiepro/views/js/scripts.js` :
    -   **Portée :** Front-office et Back-office.
    -   **Responsabilité :** C'est le fichier JavaScript personnalisé principal du module.
        -   **Front-office :** Gère la logique d'affichage de la bannière de cookies, écoute les clics sur le bouton « Accepter », définit le cookie de consentement et masque la bannière. Il gère également la visibilité en fonction de la `Durée d'expiration des cookies`.
        -   **Back-office :** Contient probablement la logique de la fonctionnalité de prévisualisation en direct, mettant à jour dynamiquement la bannière de prévisualisation au fur et à mesure que les paramètres sont modifiés dans le formulaire de configuration. Il pourrait également gérer les interactions avec la fonction « Charger un préréglage ».

### 4.5 Feuilles de style CSS (`views/css/`)

Le module ne liste explicitement aucun fichier `.css` dans l'inventaire fourni. Cela suggère que le style est principalement géré par :

1.  **Styles en ligne :** Générés dynamiquement par le module en fonction des paramètres de configuration (couleurs, positions, etc.).
2.  **CSS interne de `jscolor.js` :** Pour l'interface utilisateur du sélecteur de couleurs.
3.  **CSS interne de `tinymce` :** Pour l'interface utilisateur de l'éditeur de texte enrichi.
4.  **Champ CSS personnalisé :** Permettant aux marchands d'injecter leurs propres styles.
    Les développeurs souhaitant remplacer les styles doivent inspecter le HTML rendu de la bannière de cookies et cibler ses éléments avec des règles CSS plus spécifiques dans la feuille de style de leur thème ou via le champ CSS personnalisé du module.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** :
    -   `uecookiepro/top.tpl` :
        -   **Hook :** Ce modèle est conçu pour être rendu dans divers hooks front-office tels que `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, ou même directement dans les fichiers `product.tpl` ou `index.tpl` du thème, selon la « Position de l'avis de cookies » choisie et la manière dont les méthodes `hookDisplay*` du module sont implémentées.
        -   **Sortie :** Il produit la structure HTML de la bannière de consentement aux cookies, y compris le texte du message, le bouton « Accepter » et le lien « Plus d'infos ». Le style dynamique (couleurs, position, effets) est injecté dans ce modèle, soit sous forme de styles en ligne, soit par manipulation JavaScript.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :
    Le module ne crée aucune table SQL personnalisée. Tous les paramètres de configuration sont stockés dans la table standard `ps_configuration` de PrestaShop. Les clés de configuration suivent généralement le modèle `UECOOKIEPRO_NOM_DU_PARAMETRE`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rendu dans la section `<head>` de chaque page. | Potentiellement utilisé pour charger des actifs CSS/JS ou pour injecter la bannière tout en haut de la page. |
| `displayFooter` | Rendu en bas de chaque page, avant la balise `</body>` de fermeture. | Hook courant pour injecter la bannière de cookies (position barre inférieure) ou son JavaScript associé. |
| `displayLeftColumn` | Rendu dans la colonne latérale gauche (si activé par le thème). | Moins courant pour les bannières de cookies, mais pourrait être utilisé pour une boîte flottante dans la colonne gauche. |
| `displayRightColumn` | Rendu dans la colonne latérale droite (si activé par le thème). | Moins courant pour les bannières de cookies, mais pourrait être utilisé pour une boîte flottante dans la colonne droite. |
| `displayProductAdditionalInfo` (ou hook de page produit similaire) | Rendu sur la page produit, souvent sous la description ou les détails du produit. | Pourrait être utilisé pour placer une boîte flottante spécifiquement sur les pages produit. |
| `actionFrontControllerSetMedia` | Exécuté lorsqu'un contrôleur frontal définit ses médias (CSS/JS). | Idéal pour charger conditionnellement le CSS et le JavaScript spécifiques au module uniquement lorsque cela est nécessaire, améliorant ainsi les performances. |

Le module choisit dynamiquement le hook à utiliser en fonction du paramètre « Position de l'avis de cookies ». Par exemple, si « Barre inférieure » est sélectionné, il utilise probablement `displayFooter`. Si « Barre supérieure » est sélectionné, il pourrait utiliser `displayHeader`. Les positions « Boîte flottante » ou « Modale centrale » sont généralement gérées en injectant le HTML dans un hook général comme `displayFooter`, puis en utilisant le CSS (`position: fixed;`) et le JavaScript pour contrôler son placement et sa visibilité exacts.

## 5. Support officiel et mises à jour

Pour le support officiel, les mises à jour du module et toute assistance supplémentaire, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à fournir un support rapide et à garantir le fonctionnement optimal de votre module.
