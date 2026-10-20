---
title: "Connexion Amazon (inscription + connexion) - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Connexion Amazon (inscription + connexion) par MyPresta.eu."
sidebar:
  label: "Connexion Amazon (inscription + connexion) - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Amazon connect (register + login) sur MyPresta.eu](https://mypresta.eu/modules/social-networks/amazon-connect-register-login.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/amazon-connect-register-login/)
>
> ---


# Connexion Amazon (inscription + connexion)

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge :** PrestaShop 1.6.x, 1.7.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour une communication API sécurisée.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal du module de connexion Amazon, où vous lierez votre boutique PrestaShop à votre compte développeur Amazon.

- **aml\_ClientID (ID client Amazon)**
  - **Ce que fait ce paramètre :** C'est un identifiant unique fourni par Amazon lorsque vous enregistrez votre application (votre boutique PrestaShop) auprès de leur service Login with Amazon. Il indique à Amazon quelle application demande l'authentification de l'utilisateur.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est correctement saisi :* Votre bouton « Se connecter avec Amazon » fonctionnera correctement, permettant aux clients de s'authentifier via leur compte Amazon.
    - *Lorsqu'il est incorrect ou vide :* Le bouton « Se connecter avec Amazon » ne fonctionnera pas, ou les clients rencontreront une erreur en essayant de l'utiliser.
  - **Valeur recommandée :** L'ID client obtenu depuis votre console développeur Amazon. Ce champ ne peut pas être laissé vide pour que le module fonctionne.
  - **Scénario/exemple pour le marchand :** Vous avez enregistré votre boutique PrestaShop en tant qu'application sur la console développeur Amazon. Amazon vous fournit un « ID client » (par exemple, `amzn1.oauth-client.xxxxxxxxxxxxxxxxxxxxxxxxxxxx`). Vous devez copier et coller cet ID exact dans ce champ.
- **aml\_ClientSecret (Secret client Amazon)**
  - **Ce que fait ce paramètre :** C'est une clé confidentielle également fournie par Amazon, utilisée conjointement avec l'ID client pour authentifier votre application en toute sécurité auprès des serveurs d'Amazon. Il garantit que seule votre application légitime peut demander des données utilisateur.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est correctement saisi :* Votre module peut communiquer en toute sécurité avec l'API d'Amazon pour vérifier les identités des utilisateurs.
    - *Lorsqu'il est incorrect ou vide :* Le processus d'authentification échouera, car votre boutique ne peut pas s'identifier en toute sécurité auprès d'Amazon.
  - **Valeur recommandée :** Le secret client obtenu depuis votre console développeur Amazon. Ce champ ne peut pas être laissé vide pour que le module fonctionne.
  - **Scénario/exemple pour le marchand :** Parallèlement à l'ID client, Amazon vous donne également un « Secret client » (par exemple, `yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy`). Ce secret doit être gardé confidentiel et saisi avec précision ici.
- **aml\_RedirectURI (URI de redirection Amazon)**
  - **Ce que fait ce paramètre :** C'est l'URL de votre boutique PrestaShop vers laquelle Amazon redirigera le navigateur de l'utilisateur *après* qu'il se soit connecté ou ait autorisé votre application sur le site d'Amazon. C'est crucial pour le flux sécurisé du processus d'authentification.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est correctement configuré des deux côtés (module et console développeur Amazon) :* Les utilisateurs sont renvoyés de manière transparente à votre boutique après la connexion Amazon.
    - *Lorsqu'il est incorrect :* Les utilisateurs rencontreront une erreur après s'être connectés avec Amazon, ou ils ne seront pas redirigés correctement vers votre boutique. Cette URI doit également être enregistrée dans les paramètres de votre console développeur Amazon pour votre application.
  - **Valeur recommandée :** Cela devrait généralement être généré automatiquement par le module ou être une URL spécifique comme `https://votreboutique.com/module/amlogin/ajax_amlogin` (vérifiez le chemin exact fourni par le module ou la documentation d'Amazon). Assurez-vous qu'il correspond à l'URI que vous avez enregistrée dans votre console développeur Amazon.
  - **Scénario/exemple pour le marchand :** Lors de la configuration de votre application sur la console développeur Amazon, il vous sera demandé des « URL de retour autorisées ». Vous devez saisir l'URL exacte que ce module utilise pour la redirection (par exemple, `https://www.votreboutique.com/module/amlogin/ajax_amlogin`).
- **Afficher le bouton de connexion Amazon dans l'en-tête**
  - **Ce que fait ce paramètre :** Contrôle si le bouton « Se connecter avec Amazon » apparaît dans la section d'en-tête de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le bouton sera visible dans l'en-tête, offrant un accès immédiat à la connexion Amazon.
    - *Lorsqu'il est désactivé :* Le bouton n'apparaîtra pas dans l'en-tête.
  - **Valeur recommandée :** OUI, pour une visibilité maximale et une facilité d'accès.
  - **Scénario/exemple pour le marchand :** Vous souhaitez que les clients voient l'option de connexion Amazon dès qu'ils arrivent sur votre site, vous l'activez donc.
- **Afficher le bouton de connexion Amazon dans la colonne de gauche**
  - **Ce que fait ce paramètre :** Contrôle si le bouton « Se connecter avec Amazon » apparaît dans la colonne latérale gauche de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le bouton sera visible dans la colonne de gauche, souvent à côté d'autres blocs de navigation ou de compte.
    - *Lorsqu'il est désactivé :* Le bouton n'apparaîtra pas dans la colonne de gauche.
  - **Valeur recommandée :** OUI, si votre thème utilise une colonne de gauche et que vous souhaitez une visibilité persistante.
  - **Scénario/exemple pour le marchand :** Votre boutique a une colonne de gauche proéminente, et vous souhaitez y offrir l'option de connexion Amazon pendant que les clients parcourent les catégories.
- **Afficher le bouton de connexion Amazon dans la colonne de droite**
  - **Ce que fait ce paramètre :** Contrôle si le bouton « Se connecter avec Amazon » apparaît dans la colonne latérale droite de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le bouton sera visible dans la colonne de droite.
    - *Lorsqu'il est désactivé :* Le bouton n'apparaîtra pas dans la colonne de droite.
  - **Valeur recommandée :** OUI, si votre thème utilise une colonne de droite et que vous souhaitez une visibilité persistante.
  - **Scénario/exemple pour le marchand :** Similaire à la colonne de gauche, si votre thème utilise une colonne de droite, vous pourriez y placer le bouton pour la visibilité.
- **Afficher le bouton de connexion Amazon sur la page produit**
  - **Ce que fait ce paramètre :** Contrôle si le bouton « Se connecter avec Amazon » apparaît sur les pages de détails de produits individuels.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le bouton sera affiché sur les pages produit, potentiellement près du bouton « Ajouter au panier » ou de la description du produit.
    - *Lorsqu'il est désactivé :* Le bouton n'apparaîtra pas sur les pages produit.
  - **Valeur recommandée :** OUI, car cela peut encourager une connexion ou une inscription immédiate avant d'ajouter au panier.
  - **Scénario/exemple pour le marchand :** Un client consulte un produit et décide de l'acheter. Voir le bouton de connexion Amazon lui permet de se connecter rapidement ou de créer un compte avant de passer à la caisse.
- **Afficher le bouton de connexion Amazon dans le pied de page**
  - **Ce que fait ce paramètre :** Contrôle si le bouton « Se connecter avec Amazon » apparaît dans la section de pied de page de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le bouton sera visible dans le pied de page, offrant un point de connexion alternatif.
    - *Lorsqu'il est désactivé :* Le bouton n'apparaîtra pas dans le pied de page.
  - **Valeur recommandée :** NON, sauf si vous avez une raison de conception spécifique. D'autres emplacements offrent une meilleure visibilité.
  - **Scénario/exemple pour le marchand :** Vous souhaitez offrir l'option de connexion Amazon mais préférez qu'elle ne soit pas trop proéminente, vous la placez donc dans le pied de page.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | `aml_ClientID` | Votre ID client Amazon | Identifiant unique de votre application auprès d'Amazon. **Requis pour la fonctionnalité.** |
| Page de configuration du module | `aml_ClientSecret` | Votre secret client Amazon | Clé confidentielle pour une authentification sécurisée avec Amazon. **Requis pour la fonctionnalité.** |
| Page de configuration du module | `aml_RedirectURI` | URL auto-générée / spécifique | URL vers laquelle Amazon redirige les utilisateurs après la connexion. **Doit correspondre à la console développeur Amazon.** |
| Page de configuration du module | Afficher dans l'en-tête | OUI | Affiche le bouton dans l'en-tête de la boutique. |
| Page de configuration du module | Afficher dans la colonne de gauche | OUI | Affiche le bouton dans la barre latérale gauche. |
| Page de configuration du module | Afficher dans la colonne de droite | OUI | Affiche le bouton dans la barre latérale droite. |
| Page de configuration du module | Afficher sur la page produit | OUI | Affiche le bouton sur les pages de produits individuels. |
| Page de configuration du module | Afficher dans le pied de page | NON | Affiche le bouton dans le pied de page de la boutique. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Le bouton de connexion Amazon apparaît, mais rien ne se passe lorsque je clique dessus, ou j'obtiens une erreur.**
R : Cela indique généralement un problème avec votre `aml_ClientID`, `aml_ClientSecret` ou `aml_RedirectURI`.
- **Vérification 1 :** Vérifiez à nouveau que vous avez copié l'ID client et le secret client exactement de votre console développeur Amazon dans la configuration du module. Même une seule erreur de caractère entraînera un échec.
- **Vérification 2 :** Vérifiez que l'`aml_RedirectURI` dans la configuration du module correspond exactement à l'une des « URL de retour autorisées » que vous avez enregistrées dans votre console développeur Amazon pour votre application. Faites attention à `http` vs `https` et aux barres obliques finales.
- **Vérification 3 :** Videz votre cache PrestaShop (Paramètres avancés > Performances > Vider le cache) et le cache de votre navigateur.

**Q : Mes clients sont redirigés vers Amazon, mais obtiennent ensuite une erreur ou ne sont pas renvoyés vers ma boutique.**
R : Il s'agit presque certainement d'une non-concordance de l'`aml_RedirectURI`. Allez dans votre console développeur Amazon, trouvez votre application et assurez-vous que la liste des « URL de retour autorisées » contient l'URL *exacte* que votre module PrestaShop est configuré pour utiliser. Cela doit être une correspondance exacte, y compris `http/https` et tous les sous-répertoires.

**Q : Le bouton de connexion Amazon n'apparaît pas aux emplacements que j'ai activés.**
R :
- **Vérification 1 :** Assurez-vous que le module est activé et configuré correctement dans le Back Office.
- **Vérification 2 :** Videz votre cache PrestaShop (Paramètres avancés > Performances > Vider le cache). Parfois, les modifications de modèle ne se reflètent pas immédiatement.
- **Vérification 3 :** Votre thème pourrait remplacer les hooks PrestaShop standard. Si le bouton n'apparaît toujours pas, vous pourriez avoir besoin d'un développeur web pour insérer manuellement l'appel de hook du module dans les fichiers `.tpl` de votre thème (voir Section 7.6 pour les modèles pertinents).

**Q : Ce module fonctionne-t-il avec les boutiques multilingues ?**
R : Oui, le module devrait hériter des capacités multilingues de PrestaShop pour tout texte qu'il affiche. Le processus de connexion Amazon lui-même est géré par Amazon et s'adaptera généralement aux paramètres de langue du compte Amazon de l'utilisateur.

**Q : Puis-je personnaliser l'apparence du bouton de connexion Amazon ?**
R : Le module utilise les ressources standard du bouton de connexion Amazon. Bien que vous ne puissiez pas modifier la conception de base du bouton Amazon (conformément aux directives de marque d'Amazon), vous pouvez utiliser du CSS personnalisé (voir Section 7.5) pour ajuster son placement, ses marges ou le conteneur qui l'entoure afin de mieux l'adapter à votre thème.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Connexion Amazon (inscription + connexion) » intègre le service Login with Amazon (LWA) d'Amazon à PrestaShop. Il fonctionne principalement comme un module PrestaShop standard, exploitant les hooks pour afficher le bouton de connexion à divers emplacements du front-office. La logique principale de gestion du flux OAuth 2.0 d'Amazon (redirection vers Amazon, réception du code d'autorisation, échange contre un jeton d'accès et récupération des données de profil utilisateur) est encapsulée dans le fichier principal du module et son contrôleur AJAX associé. Les données utilisateur reçues d'Amazon sont ensuite utilisées pour connecter un client PrestaShop existant ou en créer un nouveau.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs front ou admin dédiés dans le répertoire `controllers/`. Toutes les requêtes AJAX du front-office et la configuration principale du module sont gérées par le fichier principal du module (`amlogin/ajax_amlogin.php`) qui agit comme un pseudo-contrôleur pour les actions AJAX.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne contient aucune classe ou modèle personnalisé dans un répertoire `classes/` dédié. La logique principale réside dans le fichier principal du module `amlogin/ajax_amlogin.php`.

### 4.4 Actifs JavaScript (`views/js/`)

- `amlogin/js/amlogin.js`
  - **Portée :** Front-office.
  - **Description :** Ce script est responsable de l'initialisation du SDK de connexion Amazon, de la gestion des événements de clic sur le bouton de connexion Amazon et de la gestion du flux OAuth 2.0. Il utilise probablement la méthode `amazon.Login.authorize` pour initier le processus de connexion et gère le rappel d'Amazon. Il effectuera ensuite un appel AJAX au backend du module pour traiter les données utilisateur Amazon et connecter le client à PrestaShop. Il peut également mettre à jour l'interface utilisateur (par exemple, afficher l'état connecté) après une authentification réussie.

### 4.5 Feuilles de style CSS (`views/css/`)

- `amlogin/css.css`
  - **Portée :** Front-office.
  - **Description :** Style général pour le bouton de connexion Amazon et tous les éléments d'interface utilisateur associés. Cela peut contenir des ajustements de mise en page de base, de remplissage ou de marge.
- `amlogin/css/amlogin.css`
  - **Portée :** Front-office.
  - **Description :** Style spécifique pour le bouton de connexion Amazon, incluant potentiellement des ajustements réactifs ou des remplacements spécifiques au thème pour PrestaShop 1.6.
- `amlogin/css/amlogin17.css`
  - **Portée :** Front-office.
  - **Description :** Style spécifique adapté aux thèmes PrestaShop 1.7, traitant les différences potentielles dans les structures de thème par défaut ou les frameworks CSS (par exemple, Bootstrap 4 vs Bootstrap 3). Les développeurs peuvent remplacer ces styles dans le `custom.css` de leur thème ou en créant un thème enfant.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module utilise un ensemble complet de modèles Smarty pour afficher le bouton de connexion Amazon via divers hooks PrestaShop.

- **Modèles de hook (`views/templates/hook/`)** :
  - `amlogin/ajax-amlogin.tpl` : Probablement utilisé pour les réponses AJAX ou le contenu dynamique lié au processus de connexion Amazon.
  - `amlogin/amlogin.tpl` : Un modèle générique pour le bouton de connexion Amazon, souvent inclus par d'autres modèles de hook.
  - `amlogin/createAccountForm.tpl` : Rend le bouton de connexion Amazon dans le formulaire de création de compte PrestaShop standard.
  - `amlogin/createAccountTop.tpl` : Rend le bouton de connexion Amazon en haut de la page de création de compte.
  - `amlogin/dashboardZoneOne.tpl` : Rend le bouton de connexion Amazon dans la première zone du tableau de bord client (par exemple, `displayCustomerAccount`).
  - `amlogin/displayCustomerLoginFormAfter.tpl` : Rend le bouton de connexion Amazon après le formulaire de connexion client standard.
  - `amlogin/displayNav.tpl` : Rend le bouton de connexion Amazon dans la barre de navigation (par exemple, hook `displayNav`).
  - `amlogin/displayPopUpLogin.tpl` : Rend le bouton de connexion Amazon dans une modale de connexion pop-up (si implémentée par le thème ou le module).
  - `amlogin/footer.tpl` : Rend le bouton de connexion Amazon dans le pied de page de la boutique (hook `displayFooter`).
  - `amlogin/header.tpl` : Rend le bouton de connexion Amazon dans l'en-tête de la boutique (hook `displayHeader`).
  - `amlogin/home.tpl` : Rend le bouton de connexion Amazon sur la page d'accueil (hook `displayHome`).
  - `amlogin/leftcolumn.tpl` : Rend le bouton de connexion Amazon dans la barre latérale gauche (hook `displayLeftColumn`).
  - `amlogin/rightcolumn.tpl` : Rend le bouton de connexion Amazon dans la barre latérale droite (hook `displayRightColumn`).
  - `amlogin/shoppingCart.tpl` : Rend le bouton de connexion Amazon dans le résumé du panier.
  - `amlogin/shoppingCartExtra.tpl` : Rend le bouton de connexion Amazon dans une section supplémentaire du panier.
  - `amlogin/top.tpl` : Rend le bouton de connexion Amazon dans la section supérieure de la page (par exemple, hook `displayTop`).
  - `amlogin/topColumn.tpl` : Rend le bouton de connexion Amazon dans la zone de la colonne supérieure (hook `displayTopColumn`).

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données :** Ce module ne semble pas créer de tables SQL personnalisées. Les paramètres de configuration (ID client, secret client, etc.) sont stockés dans la table `ps_configuration` en utilisant des clés comme `AML_CLIENT_ID`, `AML_CLIENT_SECRET`, `AML_REDIRECT_URI` et `AML_DISPLAY_HEADER`, etc.
- **Table des hooks enregistrés :**

  | Nom du hook | Moment d'exécution | Objectif technique |
  | --- | --- | --- |
  | `displayHeader` | Dans la section `<head>` de la page. | Injecte CSS, JS et potentiellement le bouton de connexion Amazon. |
  | `displayNav` | Dans la barre de navigation supérieure. | Affiche le bouton de connexion Amazon dans la navigation. |
  | `displayLeftColumn` | Dans la barre latérale gauche. | Affiche le bouton de connexion Amazon dans la colonne de gauche. |
  | `displayRightColumn` | Dans la barre latérale droite. | Affiche le bouton de connexion Amazon dans la colonne de droite. |
  | `displayProductButtons` (ou similaire) | Sur la page produit, près des boutons d'action. | Affiche le bouton de connexion Amazon sur les pages produit. |
  | `displayFooter` | Dans le pied de page de la boutique. | Affiche le bouton de connexion Amazon dans le pied de page. |
  | `displayCustomerAccount` | Sur le tableau de bord du compte client. | Affiche le bouton de connexion Amazon dans la zone du compte client. |
  | `displayCustomerLoginFormAfter` | Après le formulaire de connexion standard. | Intègre le bouton de connexion Amazon dans la page de connexion. |
  | `displayBeforeBodyClosingTag` | Avant la balise `</body>`. | Peut injecter du JavaScript pour le SDK Amazon ou des pop-ups. |
  | `displayShoppingCart` | Sur la page de résumé du panier. | Affiche le bouton de connexion Amazon dans le panier. |
  | `displayShoppingCartExtra` | Zone de contenu supplémentaire dans le panier. | Affiche le bouton de connexion Amazon dans une zone de panier supplémentaire. |
  | `displayTop` | En haut de la page, au-dessus de l'en-tête. | Affiche le bouton de connexion Amazon dans la section tout en haut. |
  | `displayTopColumn` | Dans la zone principale de la colonne supérieure. | Affiche le bouton de connexion Amazon dans la colonne supérieure. |
  | `displayHome` | Sur la page d'accueil de la boutique. | Affiche le bouton de connexion Amazon sur la page d'accueil. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour votre module « Connexion Amazon (inscription + connexion) », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe s'engage à garantir que votre module fonctionne parfaitement et s'intègre de manière transparente à votre boutique PrestaShop.
