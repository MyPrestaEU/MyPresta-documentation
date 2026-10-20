---
title: "Google Login Connect - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Google Login Connect par MyPresta.eu."
sidebar:
  label: "Google Login Connect"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Google Login Connect sur MyPresta.eu](https://mypresta.eu/modules/social-networks/google-login-connect.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/google-login-connect/)
>
> ---


# Google Login Connect

## 1. Exigences et Compatibilité

-   **Versions PrestaShop prises en charge** : PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilité PHP** : PHP 5.6 - 8.5
-   **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour une communication sécurisée avec l'API de Google.

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Google Login Connect)

Ceci est l'écran de configuration principal où vous configurerez vos identifiants d'API Google et déciderez où le bouton "Se connecter avec Google" apparaît dans votre boutique.

#### **Identifiants API Google**

Avant de configurer le module, vous devez créer un projet API Google et obtenir votre ID client. Ceci est crucial pour que le module communique en toute sécurité avec Google.

**Comment obtenir votre ID client Google :**
1.  Accédez à la [Console Google Cloud](https://console.cloud.google.com/).
2.  Créez un nouveau projet ou sélectionnez un projet existant.
3.  Naviguez vers **API et services > Identifiants**.
4.  Cliquez sur **"Créer des identifiants"** et choisissez **"ID client OAuth"**.
5.  Sélectionnez **"Application Web"** comme type d'application.
6.  Sous **"Origines JavaScript autorisées"**, ajoutez l'URL de votre boutique (par exemple, `https://www.votreboutique.com`).
7.  Sous **"URI de redirection autorisés"**, ajoutez l'URL de votre boutique suivie du chemin de rappel du module (par exemple, `https://www.votreboutique.com/module/glogin/index`).
8.  Après la création, Google vous fournira un **ID client**. Copiez cette valeur.

-   **ID client Google (ggl_appid)**
    -   **Ce que fait ce paramètre :** C'est l'identifiant unique de votre application (votre boutique PrestaShop) que Google utilise pour reconnaître vos demandes de connexion. Il est essentiel pour que la fonctionnalité "Se connecter avec Google" fonctionne.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est correctement saisi :* Vos boutons de connexion Google fonctionneront, permettant aux clients de s'authentifier via Google.
        -   *Lorsqu'il est incorrect ou vide :* Les boutons de connexion Google ne fonctionneront pas, ou les clients rencontreront des erreurs en essayant de se connecter avec Google.
    -   **Valeur recommandée :** L'ID client obtenu depuis votre Console Google Cloud.
    -   **Scénario/exemple pour le marchand :** Vous venez de créer votre projet API Google et avez reçu `1234567890-abcdefg.apps.googleusercontent.com`. Vous devez coller cette chaîne exacte ici.

#### **Paramètres du compte client**

-   **Groupe de clients pour les utilisateurs Google (glogin_groupid)**
    -   **Ce que fait ce paramètre :** Détermine à quel groupe de clients les nouveaux utilisateurs qui s'inscrivent via Google seront automatiquement attribués.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est défini sur "Client" (par défaut) :* Les nouveaux utilisateurs Google seront des clients standard.
        -   *Lorsqu'il est défini sur "Visiteur" ou un autre groupe personnalisé :* Les nouveaux utilisateurs Google seront attribués à ce groupe spécifique, ce qui pourrait affecter leur accès aux réductions, aux prix spéciaux ou au contenu.
    -   **Valeur recommandée :** "Client" (ou votre groupe de clients par défaut).
    -   **Scénario/exemple pour le marchand :** Vous souhaitez que toutes les nouvelles inscriptions Google fassent partie de votre groupe "Clients professionnels" pour leur accorder automatiquement des prix B2B. Vous sélectionneriez "Clients professionnels" dans la liste déroulante.

-   **Envoyer un e-mail de bienvenue aux nouveaux utilisateurs Google (glogin_semail)**
    -   **Ce que fait ce paramètre :** Contrôle si PrestaShop envoie un e-mail de bienvenue standard aux clients qui s'inscrivent en utilisant leur compte Google.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé (OUI) :* Les nouveaux utilisateurs Google recevront l'e-mail de bienvenue standard de PrestaShop, confirmant la création de leur compte.
        -   *Lorsqu'il est désactivé (NON) :* Les nouveaux utilisateurs Google ne recevront pas d'e-mail de bienvenue.
    -   **Valeur recommandée :** OUI (pour confirmer la création du compte et donner une bonne première impression).
    -   **Scénario/exemple pour le marchand :** Vous voulez vous assurer que les nouveaux clients se sentent accueillis et que les détails de leur compte sont confirmés, vous activez donc cette option.

#### **Options d'affichage**

-   **Style du bouton de connexion Google (glogin_button_style)**
    -   **Ce que fait ce paramètre :** Vous permet de choisir le style visuel du bouton "Se connecter avec Google". Les options incluent généralement différentes tailles, formes ou schémas de couleurs fournis par Google.
    -   **Effet de la modification de ce paramètre :** Modifie l'apparence de tous les boutons de connexion Google dans votre boutique.
    -   **Valeur recommandée :** Choisissez le style qui correspond le mieux au design de votre boutique.
    -   **Scénario/exemple pour le marchand :** Votre thème utilise de grands boutons arrondis. Vous sélectionneriez un style de bouton qui correspond à cette esthétique pour plus de cohérence.

-   **Afficher le bouton de connexion Google dans une fenêtre pop-up (ggl_popuplogin)**
    -   **Ce que fait ce paramètre :** Si activé, lorsqu'un client clique sur un lien de connexion, une fenêtre pop-up apparaîtra avec l'option de connexion Google, au lieu de le rediriger vers une page de connexion complète.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé (OUI) :* Offre une expérience de connexion plus rapide et moins perturbatrice via une pop-up modale.
        -   *Lorsqu'il est désactivé (NON) :* Les clients seront redirigés vers la page de connexion standard.
    -   **Valeur recommandée :** OUI (pour une expérience utilisateur moderne et fluide).
    -   **Scénario/exemple pour le marchand :** Vous souhaitez maintenir les clients sur la page actuelle autant que possible, vous activez donc la connexion pop-up.

#### **Emplacement du bouton (Sélection du hook)**

Ces paramètres contrôlent l'endroit où le bouton "Se connecter avec Google" apparaît dans votre boutique. Vous pouvez activer ou désactiver le bouton pour divers hooks d'affichage de PrestaShop.

-   **Afficher dans l'en-tête (ggl_top)**
    -   **Ce que fait ce paramètre :** Contrôle la visibilité du bouton de connexion Google dans la section d'en-tête de votre boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *Activé :* Le bouton apparaît dans l'en-tête (par exemple, près de "Mon compte" ou "Connexion").
        -   *Désactivé :* Le bouton est masqué de l'en-tête.
    -   **Valeur recommandée :** OUI (pour un accès facile depuis n'importe quelle page).

-   **Afficher dans la barre de navigation (ggl_displayNav, ggl_displayNav1, ggl_displayNav2)**
    -   **Ce que font ces paramètres :** Contrôlent la visibilité du bouton de connexion Google dans différentes positions de la barre de navigation, selon votre version de PrestaShop et votre thème. `displayNav` est courant pour les thèmes plus anciens, tandis que `displayNav1` et `displayNav2` sont souvent utilisés dans PrestaShop 1.7+ pour la navigation en haut de page.
    -   **Effet de la modification de ce paramètre :**
        -   *Activé :* Le bouton apparaît dans la barre de navigation sélectionnée.
        -   *Désactivé :* Le bouton est masqué de cette barre de navigation.
    -   **Valeur recommandée :** Activez un ou deux qui conviennent le mieux à votre thème, en évitant la redondance.

-   **Afficher dans le panier (ggl_shoppingCart, ggl_shoppingCartExtra)**
    -   **Ce que font ces paramètres :** Contrôlent la visibilité du bouton de connexion Google sur la page du panier. `ggl_shoppingCart` est généralement pour le contenu principal du panier, tandis que `ggl_shoppingCartExtra` pourrait être pour des blocs ou des résumés supplémentaires.
    -   **Effet de la modification de ce paramètre :**
        -   *Activé :* Le bouton apparaît sur la page du panier, permettant une connexion rapide avant la commande.
        -   *Désactivé :* Le bouton est masqué de la page du panier.
    -   **Valeur recommandée :** OUI (pour encourager une connexion rapide et réduire l'abandon).

-   **Afficher dans la colonne de gauche (ggl_leftcolumn)**
    -   **Ce que fait ce paramètre :** Contrôle la visibilité du bouton de connexion Google dans la barre latérale gauche de votre boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *Activé :* Le bouton apparaît dans la colonne de gauche.
        -   *Désactivé :* Le bouton est masqué de la colonne de gauche.
    -   **Valeur recommandée :** OUI (si votre thème utilise une colonne de gauche et que vous souhaitez un placement proéminent).

-   **Afficher dans la colonne de droite (ggl_rightoclumn)**
    -   **Ce que fait ce paramètre :** Contrôle la visibilité du bouton de connexion Google dans la barre latérale droite de votre boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *Activé :* Le bouton apparaît dans la colonne de droite.
        -   *Désactivé :* Le bouton est masqué de la colonne de droite.
    -   **Valeur recommandée :** OUI (si votre thème utilise une colonne de droite et que vous souhaitez un placement proéminent).

-   **Afficher sur la page d'accueil (ggl_home)**
    -   **Ce que fait ce paramètre :** Contrôle la visibilité du bouton de connexion Google sur la page d'accueil de votre boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *Activé :* Le bouton apparaît sur la page d'accueil.
        -   *Désactivé :* Le bouton est masqué de la page d'accueil.
    -   **Valeur recommandée :** OUI (pour une visibilité maximale et un accès rapide pour les nouveaux visiteurs).

-   **Afficher après le formulaire de connexion client (ggl_displayCustomerLoginFormAfter)**
    -   **Ce que fait ce paramètre :** Contrôle la visibilité du bouton de connexion Google directement après le formulaire de connexion client standard de PrestaShop (par exemple, sur la page `/mon-compte`).
    -   **Effet de la modification de ce paramètre :**
        -   *Activé :* Le bouton apparaît sous le formulaire de connexion traditionnel.
        -   *Désactivé :* Le bouton est masqué de cette position.
    -   **Valeur recommandée :** OUI (c'est un emplacement principal pour les boutons de connexion sociale).

-   **Afficher sur le formulaire de création de compte (ggl_createAccountForm, ggl_createAccountTop)**
    -   **Ce que font ces paramètres :** Contrôlent la visibilité du bouton de connexion Google sur la page de création de compte client. `ggl_createAccountForm` le place généralement dans ou près du formulaire, tandis que `ggl_createAccountTop` le place tout en haut de la page de création de compte.
    -   **Effet de la modification de ce paramètre :**
        -   *Activé :* Le bouton apparaît sur la page de création de compte, offrant une alternative d'inscription rapide.
        -   *Désactivé :* Le bouton est masqué de cette page.
    -   **Valeur recommandée :** OUI (pour simplifier l'inscription des nouveaux clients).

-   **Afficher dans la colonne supérieure (ggl_topColumn)**
    -   **Ce que fait ce paramètre :** Contrôle la visibilité du bouton de connexion Google dans le hook `displayTopColumn`, souvent utilisé pour les bannières ou le contenu juste en dessous de l'en-tête.
    -   **Effet de la modification de ce paramètre :**
        -   *Activé :* Le bouton apparaît dans la colonne supérieure.
        -   *Désactivé :* Le bouton est masqué de la colonne supérieure.
    -   **Valeur recommandée :** À considérer en fonction de la mise en page de votre thème ; souvent moins critique que d'autres positions.

-   **Afficher les informations personnelles en haut (ggl_displayPersonalInformationTop)**
    -   **Ce que fait ce paramètre :** Contrôle la visibilité du bouton de connexion Google sur la page "Mes informations personnelles", généralement lorsqu'un client est déjà connecté. Cela pourrait être moins courant pour un bouton de connexion mais pourrait être utilisé pour la liaison de compte.
    -   **Effet de la modification de ce paramètre :**
        -   *Activé :* Le bouton apparaît sur la page des informations personnelles.
        -   *Désactivé :* Le bouton est masqué de cette page.
    -   **Valeur recommandée :** NON (généralement pas un point de connexion principal).

#### **Autres paramètres (Internes/Hérités)**

-   **mypresta_updates, update_, updatev_** : Ce sont des paramètres internes utilisés par MyPresta.eu pour les vérifications de mise à jour du module et la gestion des versions. Vous ne devez pas les modifier.
-   **PS_CUSTOMER_GROUP, PS_CUSTOMER_CREATION_EMAIL, PS_CART_FOLLOWING** : Ce sont des variables de configuration PrestaShop standard que le module peut référencer mais ne permet généralement pas de modifier directement via son interface. Elles reflètent les paramètres de base de votre boutique.
-   **glogin_identity** : Il s'agit probablement d'un identifiant interne utilisé par le module. Ne pas modifier.
-   **ggl_** : Tout autre paramètre commençant par `ggl_` qui n'est pas explicitement listé ci-dessus est probablement un indicateur interne ou une option héritée. Il est préférable de les laisser à leurs valeurs par défaut, sauf indication contraire du support.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
|---|---|---|---|
| Configuration du module | ID client Google | Votre ID client Google | Essentiel pour la fonctionnalité de connexion Google. |
| Configuration du module | Groupe de clients pour les utilisateurs Google | Client | Attribue les nouveaux utilisateurs Google à un groupe de clients spécifique. |
| Configuration du module | Envoyer un e-mail de bienvenue aux nouveaux utilisateurs Google | OUI | Envoie un e-mail de bienvenue aux nouvelles inscriptions Google. |
| Configuration du module | Style du bouton de connexion Google | (Choisissez le meilleur ajustement) | Modifie l'apparence visuelle du bouton. |
| Configuration du module | Afficher le bouton de connexion Google dans une fenêtre pop-up | OUI | Active la connexion pop-up pour une meilleure UX. |
| Configuration du module | Afficher dans l'en-tête (ggl_top) | OUI | Affiche le bouton dans l'en-tête de la boutique. |
| Configuration du module | Afficher dans la barre de navigation (ggl_displayNav, ggl_displayNav1, ggl_displayNav2) | OUI (selon les besoins) | Affiche le bouton dans diverses barres de navigation. |
| Configuration du module | Afficher dans le panier (ggl_shoppingCart, ggl_shoppingCartExtra) | OUI | Affiche le bouton sur la page du panier. |
| Configuration du module | Afficher dans la colonne de gauche (ggl_leftcolumn) | OUI (si applicable) | Affiche le bouton dans la barre latérale gauche. |
| Configuration du module | Afficher dans la colonne de droite (ggl_rightoclumn) | OUI (si applicable) | Affiche le bouton dans la barre latérale droite. |
| Configuration du module | Afficher sur la page d'accueil (ggl_home) | OUI | Affiche le bouton sur la page d'accueil de la boutique. |
| Configuration du module | Afficher après le formulaire de connexion client (ggl_displayCustomerLoginFormAfter) | OUI | Affiche le bouton sous le formulaire de connexion standard. |
| Configuration du module | Afficher sur le formulaire de création de compte (ggl_createAccountForm, ggl_createAccountTop) | OUI | Affiche le bouton sur la page de création de compte. |
| Configuration du module | Afficher dans la colonne supérieure (ggl_topColumn) | NON (ou selon les besoins) | Affiche le bouton dans le hook de la colonne supérieure. |
| Configuration du module | Afficher les informations personnelles en haut (ggl_displayPersonalInformationTop) | NON | Affiche le bouton sur la page des informations personnelles (moins courant). |

## 3. Dépannage pour le marchand et Foire aux questions (FAQ)

**Q : Le bouton de connexion Google apparaît, mais rien ne se passe lorsque je clique dessus, ou j'obtiens une erreur.**
R : C'est presque toujours un problème avec votre ID client Google ou les URI de redirection autorisés dans votre Console Google Cloud.
    *   **Vérifiez l'ID client :** Vérifiez à nouveau que l'`ID client Google` saisi dans la configuration du module est exactement celui fourni par Google, sans espaces supplémentaires.
    *   **Vérifiez les URI de redirection autorisés :** Dans votre Console Google Cloud, assurez-vous d'avoir ajouté `https://www.votreboutique.com/module/glogin/index` (remplacez `votreboutique.com` par votre domaine réel) à la liste des "URI de redirection autorisés". Il doit correspondre exactement, y compris `https://` si votre boutique utilise SSL.
    *   **Vérifiez les origines JavaScript autorisées :** Assurez-vous également que l'URL principale de votre boutique (par exemple, `https://www.votreboutique.com`) est répertoriée sous "Origines JavaScript autorisées".

**Q : Les nouveaux clients s'inscrivent avec Google, mais ils ne reçoivent pas d'e-mail de bienvenue.**
R : Vérifiez le paramètre "Envoyer un e-mail de bienvenue aux nouveaux utilisateurs Google" dans la configuration du module. Assurez-vous qu'il est réglé sur "OUI". Vérifiez également que les paramètres généraux d'e-mail de votre boutique PrestaShop sont correctement configurés et que d'autres e-mails transactionnels (comme les confirmations de commande) sont envoyés avec succès.

**Q : Le bouton de connexion Google n'apparaît pas à un endroit spécifique (par exemple, l'en-tête) même si je l'ai activé.**
R :
    *   **Videz le cache :** Tout d'abord, videz le cache de votre PrestaShop (**Paramètres avancés > Performances > Vider le cache**).
    *   **Position du module :** Allez dans **Design > Positions** (ou **Modules > Positions** dans les versions antérieures). Recherchez le module `glogin`. Assurez-vous qu'il est accroché aux hooks `displayHeader`, `displayNav` ou autres hooks pertinents que vous avez activés. Parfois, les thèmes peuvent remplacer les comportements de hook par défaut.
    *   **Conflits de thème :** Votre thème peut avoir des modèles personnalisés qui n'appellent pas explicitement tous les hooks PrestaShop standard. Si le bouton n'apparaît pas après avoir vidé le cache et vérifié les positions du module, vous devrez peut-être demander à un webmaster d'inspecter les fichiers `.tpl` de votre thème.

**Q : Les clients peuvent-ils lier un compte PrestaShop existant à leur compte Google ?**
R : Ce module facilite principalement les nouvelles inscriptions et les connexions. Si un client se connecte avec Google et qu'un compte avec cette adresse e-mail existe déjà dans votre boutique PrestaShop, le module le connectera généralement à son compte existant. Il n'offre généralement pas de fonctionnalité distincte de "lier un compte existant" après la connexion, mais il effectue une correspondance intelligente par e-mail.

**Q : Je souhaite modifier le texte ou l'apparence du bouton au-delà des options du module.**
R : Le module fournit des styles de bouton Google standard. Pour une personnalisation avancée (par exemple, changer le texte, ajouter des icônes personnalisées), vous auriez besoin de CSS personnalisé et potentiellement de modifications JavaScript, qui devraient être gérées par un développeur web.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module Google Login Connect.

### 4.1 Aperçu de l'architecture
Le module `Google Login Connect` suit une architecture de module PrestaShop standard, exploitant principalement les contrôleurs frontaux pour la gestion des rappels OAuth 2.0 et divers hooks d'affichage pour l'injection de boutons. Il s'appuie sur la classe `Configuration` de PrestaShop pour le stockage des paramètres et sur l'`ObjectModel` `Customer` pour la gestion des utilisateurs. Le module s'intègre à l'API JavaScript de Google pour l'authentification côté client, qui envoie ensuite le jeton à un contrôleur frontal du module pour la vérification côté serveur et la création de session utilisateur.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :
    *   `glogin/controllers/front/index.php`
        *   **Nom de la classe et classe parente** : `GloginIndexModuleFrontController` étend `ModuleFrontController`
        *   **Responsabilité** : C'est le point de terminaison de rappel principal pour le flux OAuth 2.0 de Google. Après qu'un utilisateur s'est authentifié avec Google, Google redirige vers ce contrôleur. Il reçoit le jeton d'identification Google, le vérifie, extrait les informations de l'utilisateur (e-mail, nom), puis connecte un client PrestaShop existant ou en crée un nouveau. Il gère la gestion de session et redirige l'utilisateur vers la boutique.
    *   `glogin/controllers/front/loginloader.php`
        *   **Nom de la classe et classe parente** : `GloginLoginloaderModuleFrontController` étend `ModuleFrontController`
        *   **Responsabilité** : Ce contrôleur sert probablement un petit morceau de JavaScript ou initialise le client API Google sur les pages où le bouton de connexion est affiché. Il peut être utilisé pour charger dynamiquement la bibliothèque Google Platform (`platform.js`) ou pour fournir des variables de configuration (comme le `ggl_appid`) au JavaScript frontal.

-   **Contrôleurs d'administration Back-Office** :
    *   Aucun. Toute la configuration est gérée via la méthode `getContent()` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)
-   Aucune classe `ObjectModel` personnalisée n'est définie dans le répertoire `classes/`. Le module interagit directement avec l'`ObjectModel` `Customer` et la classe `Configuration` de PrestaShop.
-   Le fichier de module principal `glogin/glogin.php` agit comme la classe principale, étendant `Module` et contenant toute la logique d'installation, de désinstallation et de configuration.

### 4.4 Actifs JavaScript (`views/js/`)

-   `glogin/views/js/glogin.js`
    *   **Portée** : Front-office.
    *   **Responsabilité** : Ce script est responsable de l'initialisation de la bibliothèque cliente Google Sign-In. Il inclut probablement :
        *   Le chargement de la bibliothèque Google Platform (`https://apis.google.com/js/platform.js`).
        *   Le rendu du bouton "Se connecter avec Google" à l'aide de `gapi.signin2.render()`.
        *   La gestion de la fonction de rappel `onSignIn`, qui est déclenchée après une connexion Google réussie. Ce rappel extrait le jeton d'identification et l'envoie via AJAX au contrôleur frontal du module (`index.php`) pour un traitement côté serveur.
        *   Potentiellement la gestion de la fonctionnalité de connexion pop-up (`ggl_popuplogin`), affichant dynamiquement le bouton Google dans un modal.
        *   Les écouteurs d'événements pour les clics sur les boutons de connexion Google.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `glogin/css.css`
    *   **Portée** : Front-office.
    *   **Responsabilité** : Style général pour les boutons de connexion Google et potentiellement tous les conteneurs ou pop-ups personnalisés introduits par le module. Peut contenir des ajustements de mise en page de base.
-   `glogin/views/css/glogin.css`
    *   **Portée** : Front-office.
    *   **Responsabilité** : Similaire à `css.css`, contient probablement le style de base pour les boutons de connexion Google, garantissant qu'ils sont correctement alignés et dimensionnés dans divers thèmes PrestaShop.
-   `glogin/views/css/glogin17-new.css`
    *   **Portée** : Front-office.
    *   **Responsabilité** : Règles CSS spécifiques adaptées aux thèmes PrestaShop 1.7+, traitant des différences de mise en page potentielles ou des remplacements de style requis pour les versions plus récentes. Cela peut inclure des ajustements Flexbox ou Grid.
-   `glogin/views/css/glogin17.css`
    *   **Portée** : Front-office.
    *   **Responsabilité** : Une autre feuille de style spécifiquement pour PrestaShop 1.7.x, contenant potentiellement des styles supplémentaires ou alternatifs par rapport à `glogin17-new.css`, selon la structure exacte du thème.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module utilise de nombreux modèles pour injecter le bouton de connexion Google dans divers hooks de PrestaShop. La plupart de ces modèles contiendront un appel à la logique de rendu du bouton Google Sign-In (par exemple, `<div class="g-signin2" data-onsuccess="onSignIn"></div>`) et potentiellement du HTML environnant pour le style.

-   **Modèles de hook (`views/templates/hook/`)** :
    *   `glogin/views/templates/createAccountForm.tpl` : Rend le bouton Google dans le formulaire de création de compte client.
    *   `glogin/views/templates/createAccountTop.tpl` : Rend le bouton Google en haut de la page de création de compte.
    *   `glogin/views/templates/dashboardZoneOne.tpl` : Rend le bouton Google dans le hook `dashboardZoneOne` (moins courant pour la connexion, éventuellement pour l'intégration du tableau de bord d'administration ou un thème spécifique).
    *   `glogin/views/templates/displayCustomerLoginFormAfter.tpl` : Rend le bouton Google directement après le formulaire de connexion client standard.
    *   `glogin/views/templates/displayNav.tpl` : Rend le bouton Google dans le hook `displayNav` (souvent la navigation supérieure).
    *   `glogin/views/templates/displayNav1.tpl` : Rend le bouton Google dans le hook `displayNav1` (navigation PrestaShop 1.7+).
    *   `glogin/views/templates/displayNav2.tpl` : Rend le bouton Google dans le hook `displayNav2` (navigation PrestaShop 1.7+).
    *   `glogin/views/templates/displayPopUpLogin.tpl` : Contient la structure HTML pour le modal de connexion pop-up, y compris le bouton Google.
    *   `glogin/views/templates/footer.tpl` : Rend le bouton Google dans le hook `displayFooter`.
    *   `glogin/views/templates/glogin.tpl` : Un modèle générique, éventuellement utilisé comme solution de repli ou pour la logique de rendu interne.
    *   `glogin/views/templates/header.tpl` : Rend le bouton Google dans le hook `displayHeader`.
    *   `glogin/views/templates/home.tpl` : Rend le bouton Google dans le hook `displayHome`.
    *   `glogin/views/templates/leftcolumn.tpl` : Rend le bouton Google dans le hook `displayLeftColumn`.
    *   `glogin/views/templates/rightcolumn.tpl` : Rend le bouton Google dans le hook `displayRightColumn`.
    *   `glogin/views/templates/shoppingCart.tpl` : Rend le bouton Google dans le hook `displayShoppingCart`.
    *   `glogin/views/templates/shoppingCartExtra.tpl` : Rend le bouton Google dans le hook `displayShoppingCartExtra`.
    *   `glogin/views/templates/top.tpl` : Rend le bouton Google dans le hook `displayTop`.
    *   `glogin/views/templates/topColumn.tpl` : Rend le bouton Google dans le hook `displayTopColumn`.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    *   Le module ne crée aucune table SQL personnalisée.
    *   Les paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide de clés telles que `GLOGIN_GROUPID`, `GLOGIN_SEMAIL`, `GGL_APPID`, `GGL_POPUP_LOGIN`, `GGL_BUTTON_STYLE` et diverses balises `GGL_DISPLAY[HOOK_NAME]`.

-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
|---|---|---|
| `displayHeader` | Dans la section `<head>` ou au tout début du `<body>` | Injecter CSS, JS et potentiellement le bouton Google dans l'en-tête. |
| `displayFooter` | À la fin du `<body>` | Injecter le bouton Google dans le pied de page. |
| `displayHome` | Dans la zone de contenu de la page d'accueil | Injecter le bouton Google sur la page d'accueil. |
| `displayShoppingCart` | Sur la page du panier | Injecter le bouton Google sur la page du panier. |
| `displayRightColumn` | Dans la barre latérale droite | Injecter le bouton Google dans la colonne de droite. |
| `displayCustomerLoginFormAfter` | Après le formulaire de connexion client standard | Injecter le bouton Google pour une connexion alternative. |
| `displayNav` | Dans la barre de navigation principale (anciens thèmes) | Injecter le bouton Google dans la navigation. |
| `displayCreateAccountTop` | En haut de la page de création de compte | Injecter le bouton Google pour une inscription rapide. |
| `displayTop` | Dans la section supérieure de la page (souvent au-dessus de l'en-tête) | Injecter le bouton Google dans la section tout en haut. |
| `displayNav2` | Dans une barre de navigation secondaire (PS 1.7+) | Injecter le bouton Google dans la navigation. |
| `displayShoppingCartExtra` | Zone de contenu supplémentaire sur la page du panier | Injecter le bouton Google sur la page du panier. |
| `displayTopColumn` | Dans la zone de contenu sous l'en-tête (souvent pour les bannières) | Injecter le bouton Google dans la colonne supérieure. |
| `displayNav1` | Dans une barre de navigation principale (PS 1.7+) | Injecter le bouton Google dans la navigation. |
| `dashboardZoneOne` | Dans la première zone du tableau de bord d'administration | Potentiellement pour des informations côté administration ou un bouton spécifique. |
| `displayLeftColumn` | Dans la barre latérale gauche | Injecter le bouton Google dans la colonne de gauche. |

## 5. Support officiel et mises à jour
Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Assurez-vous d'utiliser la dernière version compatible du module pour votre boutique PrestaShop.
