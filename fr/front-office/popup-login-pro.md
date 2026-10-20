---
title: "PopUp Login Pro - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop PopUp Login Pro par MyPresta.eu."
sidebar:
  label: "PopUp Login Pro - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module PopUp Login Pro sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/popup-login-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/popup-login-pro/)
>
> ---


# PopUp Login Pro

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 9.x, 8.x, 1.7.x, 1.6.x, 1.5.x, 1.4.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour une boutique PrestaShop et ce module n'a pas d'exigences inhabituelles au-delà de cela.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > PopUp Login Pro)

Ceci est l'écran de configuration principal du module PopUp Login Pro. Ici, vous pouvez personnaliser l'apparence et le comportement de la pop-up sur votre boutique.

#### Paramètres généraux

| Paramètre / Option | Ce que fait ce paramètre | Effet de la modification de ce paramètre | Valeur recommandée | Scénario / exemple pour le marchand |
| --- | --- | --- | --- | --- |
| **Activer la connexion pop-up** | Ce commutateur contrôle si la fonctionnalité de connexion pop-up est active sur votre boutique. | *Lorsqu'activé :* Le module interceptera les clics sur les liens de connexion et affichera la pop-up. *Lorsqu'désactivé :* Votre boutique reviendra aux redirections de page de connexion PrestaShop par défaut. | OUI | Vous souhaitez utiliser la fonctionnalité de connexion pop-up. |
| **Type de formulaire pop-up** | Cette option vous permet de choisir parmi plusieurs styles visuels prédéfinis pour votre formulaire de connexion pop-up. | *Lorsqu'il est défini sur Option A :* La pop-up s'affichera avec le design de l'Option A. *Lorsqu'il est défini sur Option B :* La pop-up s'affichera avec le design de l'Option B. Chaque option offre un aspect et une sensation distincts. | Choisissez celui qui correspond le mieux au design de votre boutique. | Vous souhaitez un formulaire de connexion minimaliste (Option 1) ou un formulaire plus visuellement attrayant avec une image (Option 3). |
| **Largeur de la pop-up (pixels)** | Définit la largeur de la fenêtre pop-up en pixels. | *Lorsqu'il est défini sur 400px :* La pop-up aura une largeur de 400 pixels. *Lorsqu'il est défini sur 600px :* La pop-up aura une largeur de 600 pixels. Une largeur plus petite peut être plus esthétique sur mobile, tandis qu'une plus grande peut accueillir plus de contenu ou un design spécifique. | 400-500px (ajuster en fonction du type de formulaire sélectionné) | Le type de formulaire choisi semble à l'étroit à 400px, vous l'augmentez donc à 500px pour une meilleure lisibilité. |
| **Hauteur de la pop-up (pixels)** | Définit la hauteur de la fenêtre pop-up en pixels. | *Lorsqu'il est défini sur 300px :* La pop-up aura une hauteur de 300 pixels. *Lorsqu'il est défini sur 500px :* La pop-up aura une hauteur de 500 pixels. Assurez-vous qu'elle est suffisamment haute pour afficher tous les champs du formulaire sans défilement. | 300-450px (ajuster en fonction du type de formulaire sélectionné) | Le type de formulaire choisi a de nombreux champs, et à 300px, les clients doivent faire défiler. Vous l'augmentez à 450px pour tout afficher. |
| **Couleur de fond de la pop-up** | Définit la couleur de fond de la fenêtre pop-up. Vous pouvez généralement utiliser un sélecteur de couleurs ou entrer un code couleur hexadécimal (par exemple, #FFFFFF pour le blanc). | *Lorsqu'il est défini sur #FFFFFF :* Le fond de la pop-up sera blanc. *Lorsqu'il est défini sur #F0F0F0 :* Le fond de la pop-up sera gris clair. Cela aide à assortir la pop-up au schéma de couleurs de votre boutique. | #FFFFFF (Blanc) ou une couleur qui complète votre thème. | Votre boutique utilise un thème sombre, vous définissez donc le fond sur un gris foncé (#333333) pour la cohérence. |
| **Couleur de la bordure de la pop-up** | Définit la couleur de la bordure autour de la fenêtre pop-up. | *Lorsqu'il est défini sur #CCCCCC :* La bordure de la pop-up sera gris clair. *Lorsqu'il est défini sur transparent :* Aucune bordure visible ne sera affichée. | #CCCCCC (Gris clair) ou transparent | Vous voulez une bordure subtile pour définir la pop-up, vous choisissez donc un gris clair. |
| **Rayon de la bordure de la pop-up (pixels)** | Contrôle l'arrondi des coins de la fenêtre pop-up. Une valeur de 0 signifie des coins nets, des valeurs plus élevées créent des coins plus arrondis. | *Lorsqu'il est défini sur 0 :* La pop-up aura des coins nets et carrés. *Lorsqu'il est défini sur 10 :* La pop-up aura des coins légèrement arrondis. | 5-10px | Vous préférez un look plus doux et moderne, vous définissez donc le rayon de la bordure à 8px. |
| **Couleur de fond de la superposition** | Définit la couleur de l'arrière-plan assombri qui apparaît derrière la pop-up. Cela aide à concentrer l'attention sur la pop-up. | *Lorsqu'il est défini sur #000000 :* La superposition sera noire. *Lorsqu'il est défini sur #FFFFFF :* La superposition sera blanche. | #000000 (Noir) | Vous voulez une superposition sombre et transparente pour séparer clairement la pop-up du contenu principal. |
| **Opacité de la superposition (0-1)** | Contrôle la transparence de l'arrière-plan de la superposition. 0 est entièrement transparent, 1 est entièrement opaque. | *Lorsqu'il est défini sur 0.5 :* La superposition sera 50% transparente. *Lorsqu'il est défini sur 0.8 :* La superposition sera 80% opaque. | 0.7-0.8 | Vous voulez que le contenu de l'arrière-plan soit légèrement visible mais toujours clairement assombri, vous le définissez donc à 0.7. |
| **Couleur du bouton de fermeture** | Définit la couleur du bouton 'X' (fermer) de la pop-up. | *Lorsqu'il est défini sur #000000 :* Le bouton de fermeture sera noir. *Lorsqu'il est défini sur #FF0000 :* Le bouton de fermeture sera rouge. | #000000 (Noir) | Votre boutique utilise une couleur d'accent rouge, vous rendez donc le bouton de fermeture rouge pour la cohérence. |
| **Couleur de fond du bouton de fermeture** | Définit la couleur de fond du bouton 'X' (fermer). | *Lorsqu'il est défini sur #FFFFFF :* Le fond du bouton de fermeture sera blanc. *Lorsqu'il est défini sur transparent :* Aucune couleur de fond ne sera appliquée. | transparent | Vous voulez que le bouton de fermeture se fonde dans la pop-up, vous définissez donc son fond sur transparent. |
| **Activer Google reCAPTCHA** | Active Google reCAPTCHA pour les formulaires de connexion et d'inscription dans la pop-up, aidant à prévenir le spam et les inscriptions de bots. | *Lorsqu'activé :* reCAPTCHA apparaîtra sur les formulaires, exigeant des utilisateurs qu'ils vérifient qu'ils ne sont pas des robots. *Lorsqu'désactivé :* Aucun reCAPTCHA ne sera présent. | OUI (si vous avez des clés reCAPTCHA) | Vous rencontrez beaucoup d'inscriptions de spam, vous activez donc reCAPTCHA pour les filtrer. |
| **Clé de site reCAPTCHA** | Votre clé de site reCAPTCHA publique, obtenue auprès de Google. Requise si reCAPTCHA est activé. | *Lorsqu'elle est correctement saisie :* reCAPTCHA fonctionnera. *Lorsqu'elle est incorrecte ou vide :* reCAPTCHA ne fonctionnera pas, bloquant potentiellement les utilisateurs légitimes ou ne parvenant pas à empêcher les bots. | Votre clé de site Google reCAPTCHA réelle | Vous avez enregistré votre site auprès de Google reCAPTCHA et collez la clé de site fournie ici. |
| **Clé secrète reCAPTCHA** | Votre clé secrète reCAPTCHA privée, obtenue auprès de Google. Requise si reCAPTCHA est activé. | *Lorsqu'elle est correctement saisie :* reCAPTCHA fonctionnera. *Lorsqu'elle est incorrecte ou vide :* reCAPTCHA ne fonctionnera pas. | Votre clé secrète Google reCAPTCHA réelle | Vous avez enregistré votre site auprès de Google reCAPTCHA et collez la clé secrète fournie ici. |

#### 2.1.1 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer la connexion pop-up | OUI | Active/désactive la fonctionnalité de connexion pop-up. |
| Configuration du module | Type de formulaire pop-up | (Choisir en fonction du design) | Sélectionne le style visuel du formulaire de connexion. |
| Configuration du module | Largeur de la pop-up (pixels) | 400-500px | Contrôle la largeur de la fenêtre pop-up. |
| Configuration du module | Hauteur de la pop-up (pixels) | 300-450px | Contrôle la hauteur de la fenêtre pop-up. |
| Configuration du module | Couleur de fond de la pop-up | #FFFFFF | Définit la couleur de fond de la pop-up. |
| Configuration du module | Couleur de la bordure de la pop-up | #CCCCCC ou transparent | Définit la couleur de la bordure de la pop-up. |
| Configuration du module | Rayon de la bordure de la pop-up (pixels) | 5-10px | Contrôle l'arrondi des coins de la pop-up. |
| Configuration du module | Couleur de fond de la superposition | #000000 | Définit la couleur de l'arrière-plan assombri derrière la pop-up. |
| Configuration du module | Opacité de la superposition (0-1) | 0.7-0.8 | Contrôle la transparence de l'arrière-plan de la superposition. |
| Configuration du module | Couleur du bouton de fermeture | #000000 | Définit la couleur du bouton de fermeture de la pop-up. |
| Configuration du module | Couleur de fond du bouton de fermeture | transparent | Définit la couleur de fond du bouton de fermeture. |
| Configuration du module | Activer Google reCAPTCHA | OUI (si les clés sont disponibles) | Active reCAPTCHA pour la protection contre les bots. |
| Configuration du module | Clé de site reCAPTCHA | Votre clé réelle | Clé publique pour la vérification reCAPTCHA. |
| Configuration du module | Clé secrète reCAPTCHA | Votre clé réelle | Clé privée pour la vérification reCAPTCHA. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : La pop-up n'apparaît pas lorsque je clique sur "Se connecter". Que dois-je faire ?**
R :

1.  **Vérifier l'état du module :** Assurez-vous que le paramètre "Activer la connexion pop-up" est défini sur OUI dans la configuration du module.
2.  **Vider le cache :** Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions antérieures). Parfois, d'anciens fichiers mis en cache empêchent le chargement de nouvelles fonctionnalités du module.
3.  **Compatibilité du thème :** Certains thèmes très personnalisés peuvent utiliser des méthodes non standard pour gérer les liens de connexion. Vérifiez si votre thème a des paramètres ou des remplacements spécifiques pour la connexion. Si les problèmes persistent, contactez le support MyPresta.eu.

**Q2 : La pop-up a l'air étrange ou ne correspond pas au style de mon thème.**
R :

1.  **Ajuster les paramètres de style :** Allez dans la configuration du module et expérimentez avec "Couleur de fond de la pop-up", "Couleur de la bordure de la pop-up", "Rayon de la bordure de la pop-up", "Couleur de fond de la superposition" et "Opacité de la superposition".
2.  **Type de formulaire :** Essayez différentes options de "Type de formulaire pop-up" pour voir si un autre design s'intègre mieux à votre thème.
3.  **CSS personnalisé :** Si les paramètres de base ne suffisent pas, votre webmaster pourrait avoir besoin d'ajouter du CSS personnalisé à votre thème pour remplacer les styles par défaut du module (voir Section 7.5 pour les détails du fichier CSS).

**Q3 : reCAPTCHA ne fonctionne pas sur les formulaires pop-up.**
R :

1.  **Activer reCAPTCHA :** Assurez-vous que "Activer Google reCAPTCHA" est défini sur OUI.
2.  **Vérifier les clés :** Vérifiez à nouveau que vos "Clé de site reCAPTCHA" et "Clé secrète reCAPTCHA" sont correctement saisies dans la configuration du module. Elles sont sensibles à la casse.
3.  **Configuration de Google reCAPTCHA :** Assurez-vous que votre domaine est correctement enregistré dans votre compte Google reCAPTCHA.
4.  **Vider le cache :** Videz toujours votre cache PrestaShop après avoir modifié les paramètres reCAPTCHA.

**Q4 : La pop-up est trop grande/petite sur mon téléphone portable.**
R :

1.  **Ajuster la largeur/hauteur :** Modifiez "Largeur de la pop-up (pixels)" et "Hauteur de la pop-up (pixels)" dans la configuration du module. Bien que ce soient des valeurs en pixels, le module est conçu pour être réactif, donc l'ajustement de celles-ci influencera son échelle sur différents appareils.
2.  **Tester la réactivité :** Utilisez les outils de développement de votre navigateur (F12) pour simuler différents appareils mobiles et affiner les dimensions.

**Q5 : Comment traduire le texte dans la pop-up ?**
R :

1.  **Traduire le module :** Dans votre Back Office PrestaShop, allez dans **International > Traductions**.
2.  **Sélectionner les options :**
    -   Type de traduction : "Traductions des modules installés"
    -   Sélectionnez votre thème : Votre thème actuel
    -   Sélectionnez votre langue : La langue que vous souhaitez traduire
3.  **Trouver le module :** Recherchez "PopUp Login Pro" (ou `popuplogin`).
4.  **Traduire les champs :** Vous trouverez toutes les chaînes traduisibles utilisées par le module. Saisissez vos traductions et enregistrez.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module PopUp Login Pro suit une architecture de module PrestaShop standard, exploitant principalement les contrôleurs frontaux pour les requêtes AJAX et les hooks pour l'intégration dans le thème. Il utilise JavaScript pour intercepter les clics sur les liens de connexion standard et afficher la pop-up, chargeant dynamiquement le contenu via AJAX. La configuration est gérée par la méthode `getContent()` de la classe principale du module, stockant les paramètres dans `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :
    -   `controllers/front/index.php`
        -   **Nom de la classe** : `PopUpLoginIndexModuleFrontController`
        -   **Classe parente** : `ModuleFrontController`
        -   **Responsabilité** : Ce contrôleur sert probablement de point d'entrée général ou gère la configuration initiale des interactions front-office, bien que ses méthodes spécifiques définiraient son rôle exact. Il pourrait être responsable du rendu de la structure initiale de la pop-up ou de la gestion des appels AJAX non liés à la connexion.
    -   `controllers/front/loginbox.php`
        -   **Nom de la classe** : `PopUpLoginLoginBoxModuleFrontController`
        -   **Classe parente** : `ModuleFrontController`
        -   **Responsabilité** : C'est le contrôleur principal pour la gestion de la logique du formulaire de connexion et d'inscription. Il répond aux requêtes AJAX pour afficher le contenu du formulaire de connexion/inscription, traiter les tentatives de connexion, gérer les nouvelles inscriptions et gérer les requêtes "mot de passe oublié". Il renvoie probablement des fragments HTML ou des réponses JSON au JavaScript pour une insertion dynamique dans la pop-up.

### 4.3 Classes et modèles principaux (`classes/`)

D'après l'inventaire fourni, il n'y a pas de classes personnalisées ou de définitions `ObjectModel` dans le répertoire `classes/`. Le module utilise probablement les classes de base PrestaShop existantes pour la gestion des clients (`Customer`, `Context`, `Tools`) et le stockage de configuration standard.

### 4.4 Actifs JavaScript (`views/js/`)

-   `popuplogin/popuplogin.js`
    -   **Portée** : Front-office.
    -   **Détails** : C'est le fichier JavaScript principal pour la fonctionnalité front-end du module.
        -   **Écouteurs d'événements** : Il lie des écouteurs d'événements à divers éléments, le plus important étant les liens de connexion/compte standard (par exemple, `a[href*="controller=authentication"]`, `a[href*="my-account"]`). Il intercepte les événements de clic sur ces liens.
        -   **Appels AJAX** : Lorsqu'un lien de connexion est cliqué, il empêche la navigation par défaut et initie une requête AJAX vers `popuplogin/controllers/front/loginbox.php` (ou similaire) pour récupérer le HTML du formulaire de connexion/inscription.
        -   **Manipulation du DOM** : Il crée et insère dynamiquement la superposition de la pop-up et le contenu du formulaire de connexion dans le DOM. Il gère l'affichage/masquage de la pop-up, la gestion de la superposition et potentiellement le basculement entre les vues de connexion et d'inscription dans la pop-up.
        -   **Soumission de formulaire** : Il intercepte probablement les soumissions de formulaire dans la pop-up (connexion, inscription, mot de passe oublié) et les envoie via AJAX au contrôleur `loginbox.php`, traitant les réponses (par exemple, affichant des messages de succès, des messages d'erreur ou redirigeant après une connexion réussie).
        -   **UI/UX** : Gère les effets visuels de la pop-up (par exemple, fondu en entrée/sortie, centrage).
        -   **Intégration reCAPTCHA** : Si reCAPTCHA est activé, ce script est responsable du rendu du widget reCAPTCHA et de l'inclusion de son jeton dans les soumissions de formulaire AJAX.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `popuplogin/css.css`
    -   **Portée** : Style client front-office.
    -   **Détails** : Ce fichier contient probablement des styles généraux et fondamentaux pour le conteneur de la pop-up, la superposition et potentiellement les éléments de formulaire courants. Il peut inclure des styles de réinitialisation ou des règles de mise en page de base.
    -   **Sélecteurs clés** : `.popuplogin-overlay`, `.popuplogin-popup`, `.popuplogin-close-btn`.
-   `popuplogin/popuplogin.css`
    -   **Portée** : Style client front-office.
    -   **Détails** : Ce fichier contient probablement le style plus spécifique et détaillé pour les différents types de formulaires pop-up, y compris les champs de saisie, les boutons, les messages d'erreur et les ajustements réactifs. Il définira les différences visuelles entre les options "Type de formulaire pop-up".
    -   **Sélecteurs clés** : `.popuplogin-form-type-1`, `.popuplogin-form-type-2`, `.popuplogin-input`, `.popuplogin-button`, `.popuplogin-error-message`.
    -   **Remplacement par le développeur** : Les développeurs peuvent remplacer ces styles dans le fichier `custom.css` de leur thème ou en créant un thème enfant pour modifier l'apparence sans modifier directement les fichiers du module.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** :
    -   `popuplogin/dashboardZoneOne.tpl`
        -   **Hook** : Probablement `displayDashboardZoneOne` (ou un hook de tableau de bord similaire).
        -   **Objectif** : Ce modèle est probablement destiné à afficher un petit bloc d'informations ou des statistiques rapides liées au module PopUp Login Pro sur le tableau de bord du Back Office de PrestaShop. C'est un modèle destiné à l'administrateur.
    -   `popuplogin/displayPopUpLogin.tpl`
        -   **Hook** : Ce modèle est probablement rendu par le contrôleur frontal `loginbox.php` et contient la structure HTML réelle du formulaire de connexion/inscription qui apparaît à l'intérieur de la pop-up. Il n'est pas directement accroché à un hook `display` dans le thème, mais plutôt chargé dynamiquement.
        -   **Objectif** : Rend les formulaires de connexion, d'inscription et de mot de passe oublié, y compris les champs de saisie, les boutons et potentiellement les espaces réservés reCAPTCHA.
    -   `popuplogin/header.tpl`
        -   **Hook** : Probablement `displayHeader`.
        -   **Objectif** : Ce modèle est responsable de l'inclusion des fichiers CSS et JavaScript du module (`popuplogin.js`, `css.css`, `popuplogin.css`) dans la section `<head>` des pages front-office, garantissant qu'ils sont chargés avant que la fonctionnalité du module ne soit déclenchée.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :
    -   Le module ne crée pas de tables SQL personnalisées.
    -   Les paramètres de configuration sont stockés dans la table `ps_configuration` en utilisant des clés généralement préfixées par `POPUPLOGIN_` (par exemple, `POPUPLOGIN_ENABLED`, `POPUPLOGIN_FORM_TYPE`, `POPUPLOGIN_WIDTH`, `POPUPLOGIN_RECAPTCHA_SITE_KEY`).
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page front-office. | Injecte les fichiers CSS et JavaScript du module pour la fonctionnalité front-end. |
| `displayDashboardZoneOne` | Sur le tableau de bord du Back Office de PrestaShop. | Affiche un bloc d'informations ou un widget pour le module dans le panneau d'administration. |
| (Hooks implicites) | Déclenchés par l'interception JavaScript des liens de connexion standard. | Le JavaScript du module intercepte les clics sur les éléments qui mèneraient normalement aux contrôleurs `authentication` ou `my-account`, puis utilise AJAX pour charger dynamiquement le contenu de ses propres contrôleurs frontaux. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module PopUp Login Pro, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe s'engage à garantir que votre module fonctionne parfaitement et s'intègre de manière transparente à votre boutique PrestaShop.
