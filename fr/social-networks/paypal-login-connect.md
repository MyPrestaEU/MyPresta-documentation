---
title: "Connexion PayPal - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop de connexion PayPal par MyPresta.eu."
sidebar:
  label: "Connexion PayPal - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module PayPal login connect sur MyPresta.eu](https://mypresta.eu/modules/social-networks/paypal-login-connect.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/paypal-login-connect/)
>
> ---


# Connexion PayPal

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur "Configurer" à côté du module "Connexion PayPal" pour accéder à ses paramètres.

#### **Identifiants API PayPal**

Ces paramètres connectent votre boutique à votre compte développeur PayPal, permettant au module d'authentifier les utilisateurs en toute sécurité.

-   **Ce que fait ce paramètre :** Ces champs nécessitent votre ID client et votre secret client uniques obtenus depuis votre compte développeur PayPal. Ces identifiants sont essentiels pour que votre boutique puisse communiquer avec le service de connexion de PayPal.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'ils sont correctement saisis :* Le bouton "Se connecter avec PayPal" fonctionnera, permettant aux clients de se connecter.
    -   *Lorsqu'ils sont incorrects ou vides :* Le module ne pourra pas se connecter à PayPal, et la fonction de connexion échouera ou n'apparaîtra pas.
-   **Valeur recommandée :** Saisissez l'ID client et le secret client exacts fournis par PayPal.
-   **Scénario / exemple de marchand :** Vous avez créé un compte développeur PayPal et configuré une application "Connexion avec PayPal". PayPal vous fournit un ID client (une longue chaîne de caractères) et un secret client (une autre longue chaîne sécurisée). Vous les copiez et les collez dans les champs respectifs ici.

#### **Activer la connexion PayPal**

C'est l'interrupteur principal de la fonctionnalité du module.

-   **Ce que fait ce paramètre :** Contrôle si la fonction "Connexion avec PayPal" est active et visible sur votre boutique.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (OUI) :* Les boutons de connexion PayPal apparaîtront aux emplacements sélectionnés, et la fonctionnalité sera active.
    -   *Lorsqu'il est désactivé (NON) :* Les boutons de connexion PayPal seront masqués, et les clients ne pourront pas utiliser cette fonction.
-   **Valeur recommandée :** OUI
-   **Scénario / exemple de marchand :** Vous avez terminé de configurer le module et souhaitez le rendre actif pour vos clients. Vous le réglez sur OUI. Si vous devez le désactiver temporairement pour la maintenance, vous pouvez le régler sur NON.

#### **Afficher le bouton dans**

Cette section vous permet de choisir où le bouton "Se connecter avec PayPal" apparaîtra dans votre boutique.

-   **Ce que fait ce paramètre :** Détermine les emplacements spécifiques (hooks) où le bouton de connexion PayPal sera affiché sur votre front office.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'un emplacement est coché :* Le bouton de connexion PayPal apparaîtra dans cette zone spécifique de votre boutique.
    -   *Lorsqu'un emplacement est décoché :* Le bouton ne sera pas affiché dans cette zone.
-   **Valeur recommandée :** Sélectionnez les emplacements les plus pertinents pour la connexion/inscription des clients, tels que `displayNav` (navigation supérieure), `displayCustomerLoginFormAfter` (après le formulaire de connexion standard) et `createAccountForm` (sur la page d'inscription).
-   **Scénario / exemple de marchand :** Vous souhaitez que le bouton soit facilement accessible dans l'en-tête et sur la page de connexion principale. Vous cocherez `displayNav` et `displayCustomerLoginFormAfter`. Si votre thème a une connexion pop-up personnalisée, vous pourriez également cocher `displayPopUpLogin`.

#### **Style du bouton**

Personnalisez l'apparence visuelle du bouton de connexion PayPal.

-   **Ce que fait ce paramètre :** Vous permet de choisir parmi différents styles prédéfinis pour le bouton "Se connecter avec PayPal" afin de correspondre au design de votre boutique ou aux directives de marque de PayPal.
-   **Effet de la modification de ce paramètre :** Modifie l'apparence visuelle (par exemple, couleur, taille, texte) des boutons de connexion PayPal dans votre boutique.
-   **Valeur recommandée :** Choisissez un style qui s'intègre le mieux au design de votre boutique tout en restant clairement identifiable comme un bouton PayPal.
-   **Scénario / exemple de marchand :** Votre boutique utilise un thème sombre, vous pourriez donc choisir un bouton PayPal blanc avec du texte sombre pour un meilleur contraste. Ou vous pourriez préférer le bouton PayPal bleu standard pour une reconnaissance maximale de la marque.

#### **URL de redirection après connexion**

Spécifiez où les clients sont envoyés après s'être connectés avec succès via PayPal.

-   **Ce que fait ce paramètre :** Définit la page vers laquelle un client est redirigé immédiatement après s'être authentifié avec succès via PayPal et être revenu sur votre boutique.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est défini sur "Mon compte" :* Les clients atterrissent sur leur tableau de bord de compte personnel.
    -   *Lorsqu'il est défini sur "Page d'accueil" :* Les clients sont ramenés à la page principale de votre boutique.
    -   *Lorsqu'il est défini sur "Page précédente" :* Les clients sont ramenés à la page sur laquelle ils se trouvaient avant d'initier la connexion.
-   **Valeur recommandée :** "Page précédente" ou "Mon compte" pour une expérience fluide. "Page précédente" est souvent préférée lors du paiement.
-   **Scénario / exemple de marchand :** Un client est sur une page produit et clique sur "Se connecter avec PayPal". Si "Page précédente" est sélectionné, il retournera à cette page produit. S'il était dans le processus de paiement, il retournerait à l'étape de paiement.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | ID client PayPal | (Vide) / Votre ID client PayPal | Identifiant unique de votre application PayPal. **Requis pour que le module fonctionne.** |
| Configuration du module | Secret client PayPal | (Vide) / Votre secret client PayPal | Clé secrète de votre application PayPal. **Requis pour que le module fonctionne.** |
| Configuration du module | Activer la connexion PayPal | OUI | Interrupteur principal pour activer/désactiver la fonction de connexion PayPal. |
| Configuration du module | Afficher le bouton dans : `displayNav` | OUI | Affiche le bouton dans la barre de navigation principale. |
| Configuration du module | Afficher le bouton dans : `displayCustomerLoginFormAfter` | OUI | Affiche le bouton après le formulaire de connexion standard. |
| Configuration du module | Afficher le bouton dans : `createAccountForm` | OUI | Affiche le bouton sur la page d'inscription client. |
| Configuration du module | Afficher le bouton dans : `displayFooter` | NON | Affiche le bouton dans le pied de page de la boutique. |
| Configuration du module | Afficher le bouton dans : `displayHome` | NON | Affiche le bouton sur la page d'accueil. |
| Configuration du module | Afficher le bouton dans : `displayLeftColumn` | NON | Affiche le bouton dans la colonne de gauche. |
| Configuration du module | Afficher le bouton dans : `displayNav1` | NON | Affiche le bouton dans un hook de navigation alternatif (dépend du thème). |
| Configuration du module | Afficher le bouton dans : `displayNav2` | NON | Affiche le bouton dans un autre hook de navigation alternatif (dépend du thème). |
| Configuration du module | Afficher le bouton dans : `displayPopUpLogin` | OUI | Affiche le bouton dans les formulaires de connexion pop-up (si votre thème les utilise). |
| Configuration du module | Afficher le bouton dans : `displayRightColumn` | NON | Affiche le bouton dans la colonne de droite. |
| Configuration du module | Afficher le bouton dans : `displayTop` | NON | Affiche le bouton dans la section tout en haut de la page (dépend du thème). |
| Configuration du module | Afficher le bouton dans : `header` | NON | Affiche le bouton dans la section HTML `<head>` (moins courant pour les boutons visibles). |
| Configuration du module | Afficher le bouton dans : `shoppingCart` | NON | Affiche le bouton dans le résumé du panier. |
| Configuration du module | Afficher le bouton dans : `shoppingCartExtra` | NON | Affiche le bouton dans une section supplémentaire du panier (dépend du thème). |
| Configuration du module | Style du bouton | (Style PayPal par défaut) | Apparence visuelle du bouton de connexion PayPal. |
| Configuration du module | URL de redirection après connexion | Page précédente | Page de destination après une connexion PayPal réussie. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Le bouton de connexion PayPal n'apparaît pas sur ma boutique.**
R :

1.  **Vérifiez "Activer la connexion PayPal" :** Assurez-vous que ce paramètre est défini sur OUI dans la configuration du module.
2.  **Vérifiez les paramètres "Afficher le bouton dans" :** Assurez-vous d'avoir sélectionné au moins un hook (par exemple, `displayNav`, `displayCustomerLoginFormAfter`) où vous souhaitez que le bouton apparaisse.
3.  **Videz le cache :** Allez dans **Paramètres avancés > Performances** et videz le cache de votre PrestaShop (cache Smarty, cache du système de fichiers). Le cache de votre navigateur pourrait également avoir besoin d'être vidé.
4.  **Compatibilité du thème :** Certains thèmes très personnalisés peuvent nécessiter des ajustements mineurs. Si le bouton n'apparaît toujours pas, contactez le support MyPresta.eu.

**Q : Lorsque je clique sur le bouton PayPal, rien ne se passe ou j'obtiens une erreur.**
R :

1.  **Vérifiez les identifiants API :** Vérifiez à nouveau votre ID client PayPal et votre secret client dans la configuration du module. Même un seul caractère incorrect empêchera la connexion.
2.  **Configuration de l'application PayPal :** Assurez-vous que votre application "Connexion avec PayPal" dans votre compte développeur PayPal est correctement configurée, en particulier l'"URL de retour" ou l'"URI de redirection" qui doit pointer vers la page d'authentification de votre boutique (par exemple, `https://votreboutique.com/authentication?paypal_login=1`).
3.  **Compatibilité PHP :** Vérifiez que la version PHP de votre serveur se situe dans la plage prise en charge (PHP 5.6 - 8.5).

**Q : Mes clients sont redirigés vers la mauvaise page après s'être connectés.**
R :

1.  **Vérifiez "URL de redirection après connexion" :** Examinez ce paramètre dans la configuration du module. Sélectionnez l'option souhaitée (par exemple, "Mon compte", "Page précédente").
2.  **Videz le cache :** Après avoir modifié ce paramètre, videz le cache de votre PrestaShop et de votre navigateur.

**Q : Puis-je modifier le texte du bouton de connexion PayPal ?**
R : Le module utilise généralement la marque PayPal standard pour le texte et le style du bouton. La modification directe du texte n'est généralement pas une option dans la configuration du module elle-même, car elle est conçue pour adhérer aux directives de PayPal. Si vous avez besoin d'un texte personnalisé, cela nécessiterait des remplacements au niveau du thème ou une personnalisation du module (voir le Guide du développeur).

**Q : Ce module fonctionne-t-il avec les boutiques multilingues ?**
R : Oui, le module est conçu pour être compatible avec les fonctionnalités multilingues de PrestaShop. L'interface de connexion PayPal elle-même est gérée par PayPal, qui s'adapte généralement à la langue du navigateur de l'utilisateur. Tous les textes spécifiques au module (s'ils sont présents) peuvent être traduits via **International > Traductions** dans votre back office PrestaShop.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module "Connexion PayPal" (`plogin`) est un module PrestaShop standard principalement implémenté dans son fichier `index.php` principal, qui agit comme point d'entrée du module et gestionnaire de configuration. Il exploite le système de hooks de PrestaShop pour injecter le bouton "Se connecter avec PayPal" dans divers emplacements du front-office. Le module gère le flux OAuth 2.0 avec PayPal pour l'authentification de l'utilisateur, créant un compte client s'il n'existe pas, et connectant l'utilisateur. Il n'introduit pas de tables de base de données personnalisées ni de structures `ObjectModel` complexes, s'appuyant sur les classes natives `Customer` et `Configuration` de PrestaShop.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs front-office ou back-office dédiés dans le répertoire `controllers/`. Toute la logique front-office liée au rappel PayPal est gérée directement dans le fichier `index.php` (la classe principale du module) via les paramètres `$_GET`, et la configuration back-office est gérée via la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne contient pas de classes ou de modèles personnalisés dans un répertoire `classes/`. Toute la logique principale, y compris l'interaction API et la gestion des clients, est encapsulée dans la classe `plogin` principale définie dans `index.php`.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`plogin/js/plogin.js`**
    -   **Portée :** Front-office.
    -   **Objectif :** Ce script gère probablement l'interaction côté client pour le bouton de connexion PayPal. Cela pourrait inclure :
        -   L'ouverture de la fenêtre d'authentification PayPal sous forme de pop-up.
        -   La gestion de la redirection après l'authentification PayPal.
        -   Potentiellement la gestion des requêtes AJAX pour l'état de connexion ou le rendu dynamique des boutons.
        -   La liaison des événements de clic aux boutons de connexion PayPal.
        -   Assurer la fonctionnalité du bouton sur différents navigateurs et appareils.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`plogin/css.css`**
    -   **Portée :** Front-office.
    -   **Objectif :** Cette feuille de style contient probablement le style général du bouton de connexion PayPal et de tous les éléments associés. Elle peut définir la mise en page de base, le rembourrage, les marges et les styles de police.
    -   **Sélecteurs clés :** Les développeurs peuvent inspecter ce fichier pour les noms de classes (par exemple, `.paypal-login-button`, `.plogin-container`) afin de remplacer les styles dans le fichier `custom.css` ou `theme.css` de leur thème.
-   **`plogin/css/plogin.css`**
    -   **Portée :** Front-office.
    -   **Objectif :** Similaire à `css.css`, ce fichier fournit un style supplémentaire ou plus spécifique pour le bouton de connexion PayPal, y compris potentiellement différents styles de bouton basés sur la configuration, les effets de survol ou les ajustements réactifs.
    -   **Sélecteurs clés :** Recherchez des classes de bouton spécifiques (par exemple, `.plogin-btn-blue`, `.plogin-btn-white`) à cibler et à personnaliser.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module utilise un ensemble complet de modèles Smarty pour injecter le bouton de connexion PayPal dans divers hooks PrestaShop.

-   **Modèles de hook (`views/templates/hook/`)** :
    -   `plogin/createAccountForm.tpl` : Rend le bouton PayPal sur le formulaire d'inscription client.
    -   `plogin/displayCustomerLoginFormAfter.tpl` : Rend le bouton PayPal après le formulaire de connexion client standard.
    -   `plogin/displayFooter.tpl` : Rend le bouton PayPal dans le pied de page de la boutique.
    -   `plogin/displayHome.tpl` : Rend le bouton PayPal sur la page d'accueil.
    -   `plogin/displayleftColumn.tpl` : Rend le bouton PayPal dans la colonne de gauche.
    -   `plogin/displayNav.tpl` : Rend le bouton PayPal dans la barre de navigation principale (hook courant pour les liens supérieurs).
    -   `plogin/displayNav1.tpl` : Rend le bouton PayPal dans un hook de navigation alternatif (dépend du thème).
    -   `plogin/displayNav2.tpl` : Rend le bouton PayPal dans un autre hook de navigation alternatif (dépend du thème).
    -   `plogin/displayPopUpLogin.tpl` : Rend le bouton PayPal dans un formulaire de connexion pop-up (s'il est utilisé par le thème).
    -   `plogin/displayrightColumn.tpl` : Rend le bouton PayPal dans la colonne de droite.
    -   `plogin/displayTop.tpl` : Rend le bouton PayPal dans la section tout en haut de la page (dépend du thème).
    -   `plogin/header.tpl` : Ce modèle est probablement utilisé pour inclure des actifs CSS/JS dans la section `<head>` lorsque le hook `displayHeader` est utilisé, plutôt que d'afficher un bouton visible.
    -   `plogin/shoppingCart.tpl` : Rend le bouton PayPal dans le résumé du panier.
    -   `plogin/shoppingCartExtra.tpl` : Rend le bouton PayPal dans une section supplémentaire du panier (dépend du thème).
    -   `plogin/top.tpl` : Similaire à `displayTop`, pour la section supérieure de la page.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :
    -   Le module ne crée pas de tables SQL personnalisées.
    -   Les paramètres de configuration (ID client, secret client, état activé, hooks sélectionnés, URL de redirection, style du bouton) sont stockés dans la table `ps_configuration` de PrestaShop, généralement avec des clés préfixées par `PLOGIN_` (par exemple, `PLOGIN_CLIENT_ID`, `PLOGIN_ENABLED`).
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution / Emplacement | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Pour inclure les actifs CSS et JavaScript globalement pour le module. |
| `displayNav` | Dans la barre de navigation principale, généralement en haut de la page. | Affiche le bouton de connexion PayPal dans une zone de navigation proéminente. |
| `displayNav1` | Hook de navigation alternatif (dépend du thème). | Offre une flexibilité pour les thèmes avec plusieurs zones de navigation. |
| `displayNav2` | Autre hook de navigation alternatif (dépend du thème). | Offre une flexibilité pour les thèmes avec plusieurs zones de navigation. |
| `displayTop` | Dans la section tout en haut de la page, au-dessus du contenu principal. | Affiche le bouton de connexion PayPal dans la barre supérieure. |
| `displayLeftColumn` | Dans la barre latérale gauche des pages qui en ont une. | Affiche le bouton de connexion PayPal dans la colonne de gauche. |
| `displayRightColumn` | Dans la barre latérale droite des pages qui en ont une. | Affiche le bouton de connexion PayPal dans la colonne de droite. |
| `displayFooter` | Dans la section du pied de page de la boutique. | Affiche le bouton de connexion PayPal dans le pied de page. |
| `displayHome` | Sur la page d'accueil de la boutique. | Affiche le bouton de connexion PayPal sur la page d'accueil principale. |
| `displayCustomerLoginFormAfter` | Après le formulaire de connexion standard sur la page d'authentification. | Fournit l'option de connexion PayPal comme alternative à l'e-mail/mot de passe. |
| `createAccountForm` | Sur la page d'inscription client. | Offre PayPal comme méthode d'inscription rapide. |
| `displayPopUpLogin` | Dans une modale de connexion pop-up (si implémentée par le thème). | S'intègre aux pop-ups de connexion des thèmes modernes. |
| `shoppingCart` | Dans le bloc de résumé du panier. | Offre la connexion/inscription pendant la phase de révision du panier. |
| `shoppingCartExtra` | Dans une section supplémentaire du panier (dépend du thème). | Offre une flexibilité de placement supplémentaire dans le panier. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module "Connexion PayPal", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question concernant la fonctionnalité du module.
