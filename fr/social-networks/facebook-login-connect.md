---
title: "Facebook Login Connect - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Facebook Login Connect par MyPresta.eu."
sidebar:
  label: "Facebook Login Connect - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Facebook Login Connect sur MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-login-connect.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/facebook-login-connect/)
>
> ---


# Facebook Login Connect

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour la communication avec l'API de Facebook. Celles-ci sont presque toujours disponibles sur tout hébergement web moderne.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal où vous configurerez le comportement du bouton de connexion Facebook et son emplacement.

#### Paramètres généraux

- **ID d'application Facebook (App ID) :**
  - **Ce que fait ce paramètre :** Il s'agit d'un identifiant unique fourni par Facebook pour votre application spécifique. Il est crucial pour que votre boutique puisse communiquer avec le système de connexion de Facebook.
  - **Effet de la modification de ce paramètre :** Sans un App ID valide, le bouton de connexion Facebook ne fonctionnera pas, car votre boutique ne peut pas s'authentifier auprès de Facebook.
  - **Valeur recommandée :** L'App ID que vous obtenez de votre compte développeur Facebook. Ce champ ne peut pas être vide.
  - **Scénario / exemple pour le marchand :** Vous devez créer une application Facebook sur [developers.facebook.com](https://developers.facebook.com/) pour obtenir cet ID. Suivez les instructions de Facebook pour configurer une application de base et activer la connexion Facebook.
- **Groupe de clients par défaut pour les nouveaux comptes :**
  - **Ce que fait ce paramètre :** Lorsqu'un nouveau client s'inscrit via Facebook, il sera automatiquement assigné à ce groupe de clients.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur « Client » (par défaut) :* Les nouveaux utilisateurs Facebook deviennent des clients réguliers, soumis aux prix et réductions standard de votre boutique.
    - *Lorsqu'il est défini sur un groupe personnalisé (par exemple, « Grossiste ») :* Les nouveaux utilisateurs Facebook pourraient immédiatement accéder à des prix ou du contenu spéciaux si ce groupe a des règles spécifiques.
  - **Valeur recommandée :** `Client` (ou votre groupe de clients par défaut pour les nouvelles inscriptions).
  - **Scénario / exemple pour le marchand :** Si vous avez un groupe de clients « VIP » avec des réductions spéciales, vous pourriez envisager d'assigner d'abord les nouveaux utilisateurs Facebook à un groupe « Client » standard, puis de les mettre à niveau manuellement s'ils répondent aux critères VIP.
- **Envoyer un e-mail de bienvenue aux nouveaux clients :**
  - **Ce que fait ce paramètre :** Contrôle si PrestaShop envoie son e-mail de bienvenue standard aux clients qui s'inscrivent via Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (Oui) :* Les nouveaux utilisateurs Facebook reçoivent un e-mail confirmant la création de leur compte.
    - *Lorsqu'il est désactivé (Non) :* Aucun e-mail de bienvenue n'est envoyé.
  - **Valeur recommandée :** `Oui`. Il est de bonne pratique d'accueillir les nouveaux clients et de leur fournir leurs informations de connexion (même s'ils utilisent Facebook, ils pourraient vouloir définir un mot de passe plus tard).
  - **Scénario / exemple pour le marchand :** Maintenir cette option activée garantit que les nouveaux clients se sentent accueillis et ont une trace de leur compte, même s'ils n'ont pas besoin de se souvenir d'un mot de passe immédiatement.
- **Activer la connexion via le navigateur intégré (pour les applications mobiles) :**
  - **Ce que fait ce paramètre :** Ce paramètre est principalement destiné aux boutiques accessibles via une application mobile dédiée (pas seulement un navigateur mobile). Il optimise le flux de connexion Facebook pour les navigateurs intégrés aux applications.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Améliore l'expérience de connexion pour les utilisateurs accédant à votre boutique via un WebView au sein d'une application mobile.
    - *Lorsqu'il est désactivé :* Le flux de connexion standard du navigateur est utilisé, ce qui pourrait être moins fluide dans une application dédiée.
  - **Valeur recommandée :** `Non`, sauf si vous avez une application mobile spécifique qui intègre votre boutique PrestaShop.
  - **Scénario / exemple pour le marchand :** Si vous avez développé une application native iOS ou Android qui affiche le contenu de votre boutique PrestaShop, l'activation de cette option pourrait être nécessaire pour une expérience de connexion Facebook fluide au sein de cette application.
- **Afficher la connexion Facebook dans une fenêtre pop-up :**
  - **Ce que fait ce paramètre :** Si votre thème utilise une fenêtre pop-up pour la connexion, cette option permet au bouton de connexion Facebook d'apparaître dans cette pop-up.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le bouton de connexion Facebook sera disponible dans la pop-up de connexion de votre thème.
    - *Lorsqu'il est désactivé :* Le bouton n'apparaîtra que sur les pages de connexion standard ou d'autres positions de hook.
  - **Valeur recommandée :** `Oui`, si votre thème utilise une pop-up de connexion.
  - **Scénario / exemple pour le marchand :** De nombreux thèmes modernes utilisent une pop-up de connexion rapide accessible depuis l'en-tête. L'activation de cette option rend l'option de connexion Facebook immédiatement visible à cet endroit.
- **Langue du bouton de connexion Facebook :**
  - **Ce que fait ce paramètre :** Vous permet de spécifier la langue du bouton de connexion Facebook et des messages associés.
  - **Effet de la modification de ce paramètre :** Le texte du bouton et toutes les invites générées par Facebook apparaîtront dans la langue sélectionnée.
  - **Valeur recommandée :** `Langue par défaut de PrestaShop` (pour correspondre à la langue principale de votre boutique) ou `Détection automatique` si disponible.
  - **Scénario / exemple pour le marchand :** Si votre boutique opère dans plusieurs langues, vous pourriez vouloir que cela corresponde à la langue actuelle du front-office pour une expérience utilisateur cohérente.
- **Autoriser Facebook à identifier les utilisateurs (Avancé) :**
  - **Ce que fait ce paramètre :** Il s'agit d'un paramètre avancé lié au suivi d'identité de Facebook. Il permet à Facebook de potentiellement suivre les utilisateurs sur votre site à des fins publicitaires.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Peut fournir plus de données pour la publicité Facebook mais pourrait avoir des implications en matière de confidentialité en fonction des réglementations locales (par exemple, le RGPD).
    - *Lorsqu'il est désactivé :* Limite la capacité de Facebook à suivre les utilisateurs sur votre site.
  - **Valeur recommandée :** `Non`, sauf si vous avez une stratégie marketing spécifique qui le requiert et que vous avez traité la conformité en matière de confidentialité.
  - **Scénario / exemple pour le marchand :** Consultez votre équipe marketing et votre conseiller juridique avant d'activer cette option, surtout si vous opérez dans des régions avec des lois strictes sur la confidentialité des données.

#### Options d'affichage (Où afficher le bouton de connexion Facebook)

Ces paramètres contrôlent dans quelles zones spécifiques (hooks) de votre boutique PrestaShop le bouton de connexion Facebook sera affiché. Vous pouvez activer ou désactiver chaque hook individuellement.

- **Afficher en haut (fbl\_displayTop) :**
  - **Ce que fait ce paramètre :** Affiche le bouton dans la section tout en haut de votre boutique, souvent près de la barre de recherche ou du logo.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le bouton apparaît dans l'en-tête.
    - *Désactivé :* Le bouton est masqué de l'en-tête.
  - **Valeur recommandée :** `Oui`, pour une grande visibilité.
- **Afficher dans la colonne supérieure (fbl\_displaytopColumn) :**
  - **Ce que fait ce paramètre :** Affiche le bouton dans la zone de contenu principale, généralement au-dessus des listes de produits principales ou du contenu de la page d'accueil.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le bouton apparaît dans la zone de contenu supérieure.
    - *Désactivé :* Le bouton est masqué de cette zone.
  - **Valeur recommandée :** `Non`, sauf si vous souhaitez un bouton très proéminent sur la page d'accueil.
- **Afficher sur la page d'accueil (fbl\_displayHome) :**
  - **Ce que fait ce paramètre :** Affiche le bouton spécifiquement sur la page d'accueil de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le bouton apparaît sur la page d'accueil.
    - *Désactivé :* Le bouton est masqué de la page d'accueil.
  - **Valeur recommandée :** `Oui`, pour encourager l'inscription immédiate.
- **Afficher dans la navigation (fbl\_displayNav) :**
  - **Ce que fait ce paramètre :** Affiche le bouton dans la barre de navigation principale, souvent à côté des liens « Mon compte » ou « Contactez-nous ».
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le bouton apparaît dans la navigation.
    - *Désactivé :* Le bouton est masqué de la navigation.
  - **Valeur recommandée :** `Oui`, pour un accès facile depuis n'importe quelle page.
- **Afficher dans la navigation 1 (fbl\_displayNav1) :**
  - **Ce que fait ce paramètre :** Similaire à `displayNav`, mais cible un hook de navigation spécifique que certains thèmes utilisent (souvent pour la barre tout en haut).
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le bouton apparaît dans la première zone de navigation.
    - *Désactivé :* Le bouton est masqué de cette zone.
  - **Valeur recommandée :** `Oui`, si votre thème utilise ce hook et que vous souhaitez le bouton à cet endroit.
- **Afficher dans la navigation 2 (fbl\_displayNav2) :**
  - **Ce que fait ce paramètre :** Similaire à `displayNav`, mais cible un deuxième hook de navigation que certains thèmes utilisent (souvent pour la barre de navigation principale).
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le bouton apparaît dans la deuxième zone de navigation.
    - *Désactivé :* Le bouton est masqué de cette zone.
  - **Valeur recommandée :** `Oui`, si votre thème utilise ce hook et que vous souhaitez le bouton à cet endroit.
- **Afficher dans le panier (fbl\_displayShoppingCart) :**
  - **Ce que fait ce paramètre :** Affiche le bouton sur la page de résumé du panier.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le bouton apparaît sur la page du panier, permettant une connexion rapide avant le paiement.
    - *Désactivé :* Le bouton est masqué de la page du panier.
  - **Valeur recommandée :** `Oui`, pour simplifier le paiement pour les clients récurrents.
- **Afficher après le formulaire de connexion client (fbl\_displayCustomerLoginFormAfter) :**
  - **Ce que fait ce paramètre :** Affiche le bouton directement sous le formulaire de connexion PrestaShop standard.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le bouton apparaît comme méthode de connexion alternative sur la page de connexion.
    - *Désactivé :* Le bouton est masqué de cette zone.
  - **Valeur recommandée :** `Oui`, c'est un emplacement privilégié pour les options de connexion alternatives.
- **Afficher en haut des informations personnelles (fbl\_displayPersonalInformationTop) :**
  - **Ce que fait ce paramètre :** Affiche le bouton en haut de la section « Informations personnelles » lors de la création ou de la modification d'un compte.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le bouton apparaît sur la page des informations personnelles.
    - *Désactivé :* Le bouton est masqué de cette zone.
  - **Valeur recommandée :** `Oui`, pour offrir la connexion Facebook comme alternative au remplissage du formulaire.
- **Afficher dans le panier supplémentaire (fbl\_displayShoppingCartExtra) :**
  - **Ce que fait ce paramètre :** Affiche le bouton dans une zone supplémentaire de la page du panier, souvent utilisée pour des modules ou informations supplémentaires.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le bouton apparaît dans la zone supplémentaire du panier.
    - *Désactivé :* Le bouton est masqué de cette zone.
  - **Valeur recommandée :** `Non`, sauf si votre thème utilise spécifiquement ce hook pour les options de connexion.
- **Afficher dans la colonne de gauche (fbl\_displayLeftColumn) :**
  - **Ce que fait ce paramètre :** Affiche le bouton dans la barre latérale gauche de votre boutique (si votre thème en a une).
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le bouton apparaît dans la colonne de gauche.
    - *Désactivé :* Le bouton est masqué de la colonne de gauche.
  - **Valeur recommandée :** `Non`, sauf si vous souhaitez qu'il soit affiché de manière proéminente dans la barre latérale.
- **Afficher dans la colonne de droite (fbl\_displayRightColumn) :**
  - **Ce que fait ce paramètre :** Affiche le bouton dans la barre latérale droite de votre boutique (si votre thème en a une).
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le bouton apparaît dans la colonne de droite.
    - *Désactivé :* Le bouton est masqué de la colonne de droite.
  - **Valeur recommandée :** `Non`, sauf si vous souhaitez qu'il soit affiché de manière proéminente dans la barre latérale.
- **Afficher dans le formulaire de création de compte (fbl\_displayCreateAccountForm) :**
  - **Ce que fait ce paramètre :** Affiche le bouton directement dans le formulaire de création de compte PrestaShop standard.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le bouton apparaît comme méthode d'inscription alternative sur la page de création de compte.
    - *Désactivé :* Le bouton est masqué de cette zone.
  - **Valeur recommandée :** `Oui`, c'est un emplacement crucial pour simplifier l'inscription.
- **Afficher en haut de la création de compte (fbl\_displayCreateAccountTop) :**
  - **Ce que fait ce paramètre :** Affiche le bouton tout en haut de la page de création de compte, au-dessus des champs du formulaire.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le bouton apparaît en haut de la page de création de compte.
    - *Désactivé :* Le bouton est masqué de cette zone.
  - **Valeur recommandée :** `Oui`, pour une visibilité maximale sur la page d'inscription.
- **Afficher dans le pied de page (fbl\_displayFooter) :**
  - **Ce que fait ce paramètre :** Affiche le bouton dans la section du pied de page de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le bouton apparaît dans le pied de page.
    - *Désactivé :* Le bouton est masqué du pied de page.
  - **Valeur recommandée :** `Non`, généralement pas un emplacement principal pour les boutons de connexion.
- **Afficher dans l'en-tête (fbl\_displayHeader) :**
  - **Ce que fait ce paramètre :** Affiche le bouton dans la section de l'en-tête de votre boutique. C'est un placement très courant et efficace.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le bouton apparaît dans l'en-tête.
    - *Désactivé :* Le bouton est masqué de l'en-tête.
  - **Valeur recommandée :** `Oui`, pour une grande visibilité sur toutes les pages.
- **Afficher dans la zone un du tableau de bord (fbl\_displayDashboardZoneOne) :**
  - **Ce que fait ce paramètre :** Ce hook est généralement destiné à afficher du contenu sur le tableau de bord du compte client.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le bouton apparaît sur le tableau de bord du client.
    - *Désactivé :* Le bouton est masqué de cette zone.
  - **Valeur recommandée :** `Non`, car les clients sont déjà connectés lorsqu'ils voient leur tableau de bord.
- **Afficher dans la connexion pop-up (fbl\_popuplogin) :**
  - **Ce que fait ce paramètre :** Cible spécifiquement les thèmes qui utilisent une modale pop-up pour la connexion.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le bouton apparaît dans la pop-up de connexion.
    - *Désactivé :* Le bouton est masqué de la pop-up de connexion.
  - **Valeur recommandée :** `Oui`, si votre thème utilise une pop-up de connexion.
- **Afficher la connexion Facebook (fbl\_fblogin) :**
  - **Ce que fait ce paramètre :** Il s'agit d'un hook générique pour le bouton de connexion Facebook. Il peut être utilisé par le module en interne ou par les thèmes pour un placement personnalisé.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le bouton apparaît dans ce hook générique.
    - *Désactivé :* Le bouton est masqué de ce hook.
  - **Valeur recommandée :** `Oui`, si d'autres hooks spécifiques ne fonctionnent pas ou si vous souhaitez une solution de repli.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | ID d'application Facebook (App ID) | *Votre App ID Facebook* | Essentiel pour la connexion à Facebook ; le bouton ne fonctionnera pas sans lui. |
| Configuration du module | Groupe de clients par défaut pour les nouveaux comptes | Client | Attribue les nouveaux utilisateurs Facebook à un groupe de clients spécifique. |
| Configuration du module | Envoyer un e-mail de bienvenue aux nouveaux clients | Oui | Détermine si les nouvelles inscriptions Facebook reçoivent un e-mail de bienvenue. |
| Configuration du module | Activer la connexion via le navigateur intégré | Non | Optimise la connexion pour les applications mobiles dédiées (pas les navigateurs mobiles). |
| Configuration du module | Afficher la connexion Facebook dans une fenêtre pop-up | Oui (si le thème utilise une pop-up) | Affiche le bouton dans la pop-up de connexion du thème. |
| Configuration du module | Langue du bouton de connexion Facebook | Langue par défaut de PrestaShop | Définit la langue du bouton et des invites Facebook. |
| Configuration du module | Autoriser Facebook à identifier les utilisateurs | Non | Option de suivi avancée ; consulter les services juridiques/marketing. |
| Configuration du module | Afficher en haut (fbl\_displayTop) | Oui | Affiche le bouton dans l'en-tête. |
| Configuration du module | Afficher dans la colonne supérieure (fbl\_displaytopColumn) | Non | Affiche le bouton dans la zone de contenu principale, généralement au-dessus des listes. |
| Configuration du module | Afficher sur la page d'accueil (fbl\_displayHome) | Oui | Affiche le bouton spécifiquement sur la page d'accueil. |
| Configuration du module | Afficher dans la navigation (fbl\_displayNav) | Oui | Affiche le bouton dans la barre de navigation principale. |
| Configuration du module | Afficher dans la navigation 1 (fbl\_displayNav1) | Oui (si le thème l'utilise) | Affiche le bouton dans une zone de navigation supérieure spécifique. |
| Configuration du module | Afficher dans la navigation 2 (fbl\_displayNav2) | Oui (si le thème l'utilise) | Affiche le bouton dans une zone de navigation principale spécifique. |
| Configuration du module | Afficher dans le panier (fbl\_displayShoppingCart) | Oui | Affiche le bouton sur la page de résumé du panier. |
| Configuration du module | Afficher après le formulaire de connexion client | Oui | Affiche le bouton sous le formulaire de connexion standard. |
| Configuration du module | Afficher en haut des informations personnelles | Oui | Affiche le bouton en haut de la page des informations personnelles. |
| Configuration du module | Afficher dans le panier supplémentaire | Non | Affiche le bouton dans une zone supplémentaire du panier. |
| Configuration du module | Afficher dans la colonne de gauche (fbl\_displayLeftColumn) | Non | Affiche le bouton dans la barre latérale gauche. |
| Configuration du module | Afficher dans la colonne de droite (fbl\_displayRightColumn) | Non | Affiche le bouton dans la barre latérale droite. |
| Configuration du module | Afficher dans le formulaire de création de compte | Oui | Affiche le bouton dans le formulaire de création de compte. |
| Configuration du module | Afficher en haut de la création de compte | Oui | Affiche le bouton en haut de la page de création de compte. |
| Configuration du module | Afficher dans le pied de page (fbl\_displayFooter) | Non | Affiche le bouton dans le pied de page. |
| Configuration du module | Afficher dans l'en-tête (fbl\_displayHeader) | Oui | Affiche le bouton dans la section de l'en-tête. |
| Configuration du module | Afficher dans la zone un du tableau de bord | Non | Affiche le bouton sur le tableau de bord du compte client. |
| Configuration du module | Afficher dans la connexion pop-up (fbl\_popuplogin) | Oui (si le thème utilise une pop-up) | Affiche le bouton dans la modale pop-up de connexion. |
| Configuration du module | Afficher la connexion Facebook (fbl\_fblogin) | Oui | Hook générique pour le bouton de connexion Facebook. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Le bouton de connexion Facebook apparaît, mais rien ne se passe lorsque je clique dessus, ou il affiche une erreur.**
R1 : Cela indique presque toujours un problème avec votre ID d'application Facebook ou la configuration de l'application Facebook elle-même.
- **Vérifiez votre ID d'application Facebook :** Allez dans la configuration de votre module dans PrestaShop et vérifiez que l'« ID d'application Facebook » est correctement saisi.
- **Vérifiez les paramètres de votre application Facebook :** Connectez-vous à [developers.facebook.com](https://developers.facebook.com/).
- Assurez-vous que votre application est « Live » (pas en mode développement).
- Allez dans « Connexion Facebook » > « Paramètres » et assurez-vous que « Connexion OAuth client » et « Connexion OAuth Web » sont activés.
- Sous « URI de redirection OAuth valides », vous *devez* ajouter le domaine complet de votre boutique (par exemple, `https://www.votreboutique.com/`). Parfois, vous devrez peut-être aussi ajouter `https://www.votreboutique.com/module/fblogin/index` ou `https://www.votreboutique.com/module/fblogin/loginloader` selon votre version de PrestaShop et la structure de votre URL.
- Assurez-vous que votre « URL de politique de confidentialité » et votre « URL des conditions d'utilisation » sont définies dans les « Paramètres de base » de votre application Facebook.
- **Videz le cache :** Après avoir effectué des modifications, videz le cache de votre PrestaShop (Paramètres avancés > Performances > Vider le cache).

**Q2 : Les nouveaux clients s'inscrivent via Facebook, mais leurs noms ou e-mails n'apparaissent pas correctement.**
R2 : Le module extrait les informations de profil public de Facebook.
- Assurez-vous que le client a accordé la permission à votre application d'accéder à son profil de base et à son e-mail.
- L'API de Facebook fournit le prénom, le nom et l'e-mail. Si ceux-ci sont manquants ou incorrects, il s'agit généralement d'un problème lié aux paramètres de confidentialité du profil Facebook du client ou d'un rare problème d'API.
- Le module crée un nouveau compte si aucune adresse e-mail correspondante n'est trouvée. Si une adresse e-mail existe déjà dans votre base de données PrestaShop, le module devrait tenter de connecter l'utilisateur à ce compte existant.

**Q3 : Le bouton Facebook n'apparaît pas à l'emplacement attendu, même après avoir activé le hook.**
R3 :
- **Videz le cache :** Videz toujours le cache de votre PrestaShop (Paramètres avancés > Performances > Vider le cache) après avoir modifié les paramètres des hooks.
- **Compatibilité du thème :** Certains thèmes personnalisés peuvent remplacer les hooks PrestaShop standard ou avoir des structures uniques. Si le bouton n'apparaît pas, votre thème pourrait ne pas afficher activement ce hook spécifique. Vous devrez peut-être consulter le développeur de votre thème ou un webmaster pour l'intégrer manuellement dans les fichiers `.tpl` de votre thème.
- **Vérifiez les positions des modules :** Allez dans Conception > Positions (ou Modules > Positions dans les versions antérieures) et recherchez `fblogin`. Assurez-vous que le module est « accroché » aux positions souhaitées. Si ce n'est pas le cas, vous pouvez « Greffer un module » manuellement au bon hook.

**Q4 : Les clients qui se sont inscrits avec Facebook peuvent-ils définir un mot de passe plus tard pour se connecter directement ?**
R4 : Oui. Une fois qu'un compte est créé via Facebook, il s'agit d'un compte client PrestaShop standard.
- Les clients peuvent utiliser le lien « Mot de passe oublié » sur la page de connexion de votre boutique. Ils recevront un e-mail pour définir un nouveau mot de passe, leur permettant de se connecter directement avec leur e-mail et le nouveau mot de passe, même sans Facebook.

**Q5 : Ce module prend-il en charge plusieurs langues pour le bouton ?**
R5 : Oui, le module dispose d'un paramètre pour la « Langue du bouton de connexion Facebook ». Vous pouvez le définir pour qu'il corresponde à la langue par défaut de votre boutique, ou dans certains cas, le SDK de Facebook peut détecter automatiquement la langue du navigateur de l'utilisateur.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module `Facebook Login Connect` intègre le SDK JavaScript de Facebook pour faciliter l'authentification des utilisateurs. Il fonctionne principalement en s'accrochant à divers points d'affichage du front-office pour afficher le bouton de connexion Facebook. Lors d'une connexion Facebook réussie, un contrôleur frontal gère le rappel, récupère les données utilisateur de Facebook et connecte un client PrestaShop existant ou en crée un nouveau. Le module utilise la classe `Module` de PrestaShop pour la configuration et la gestion des hooks, avec un minimum de classes personnalisées, s'appuyant fortement sur le fichier principal `fblogin.php` pour la logique de base.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :

  - `controllers/front/index.php`
    - **Nom de la classe :** `FbloginIndexModuleFrontController`
    - **Classe parente :** `ModuleFrontController`
    - **Responsabilité :** Ce contrôleur agit comme le point de terminaison de rappel principal pour le processus d'authentification de Facebook. Après qu'un utilisateur se soit connecté avec succès via Facebook, Facebook redirige vers ce contrôleur. Il gère la récupération du jeton d'accès Facebook, récupère les données de profil utilisateur (nom, e-mail), puis connecte un client PrestaShop existant ou en crée un nouveau. Il redirige ensuite l'utilisateur vers sa page de compte ou la page d'accueil.
  - `controllers/front/loginloader.php`
    - **Nom de la classe :** `FbloginLoginloaderModuleFrontController`
    - **Classe parente :** `ModuleFrontController`
    - **Responsabilité :** Ce contrôleur est probablement un point d'entrée de secours ou alternatif pour le processus de connexion Facebook, potentiellement utilisé pour des scénarios spécifiques ou des versions plus anciennes de PrestaShop. Il effectuerait des tâches d'authentification et de gestion des utilisateurs similaires à `index.php`.
- **Contrôleurs d'administration Back-Office** :

  - Aucun. Toute la configuration est gérée dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

- Aucun. Le module ne définit aucune classe `ObjectModel` personnalisée ni d'autres classes de logique métier principales dans le répertoire `classes/`. Toute la logique de base est encapsulée dans la classe `Fblogin` dans `fblogin.php`.

### 4.4 Actifs JavaScript (`views/js/`)

- `views/js/fblogin4.js`
  - **Portée :** Front-office.
  - **Responsabilité :** Ce script est responsable de l'initialisation du SDK JavaScript de Facebook. Il charge le SDK, configure la configuration `FB.init` (y compris l'ID d'application et les autorisations souhaitées), et gère l'appel `FB.login` lorsque le bouton de connexion Facebook est cliqué. Il écoute probablement l'événement `auth.statusChange` pour détecter les états de connexion/déconnexion et redirige l'utilisateur vers le contrôleur frontal PrestaShop approprié (`index.php` ou `loginloader.php`) après une authentification réussie. Il gère également l'affichage du bouton de connexion Facebook et son interaction.

### 4.5 Feuilles de style CSS (`views/css/`)

- `css.css`
  - **Portée :** Front-office.
  - **Responsabilité :** Il s'agit probablement d'une feuille de style générique pour le module, fournissant un style de base pour le bouton de connexion Facebook et tous les éléments d'interface utilisateur associés.
- `views/css/fblogin.css`
  - **Portée :** Front-office.
  - **Responsabilité :** Fournit des règles de style spécifiques pour le bouton de connexion Facebook et son conteneur, garantissant une apparence cohérente sur différents thèmes. Il peut inclure des styles pour la taille du bouton, la couleur, les effets de survol et l'alignement.
- `views/css/fblogin17.css`
  - **Portée :** Front-office.
  - **Responsabilité :** Cette feuille de style contient probablement des remplacements spécifiques ou des styles supplémentaires adaptés aux versions de PrestaShop 1.7.x et plus récentes, traitant des différences potentielles de mise en page ou de style dans les nouvelles structures de thème.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **Modèles de hook (`views/templates/hook/`)** :

  - `createAccountForm.tpl` : Rend le bouton de connexion Facebook dans le formulaire de création de compte standard.
  - `createAccountTop.tpl` : Rend le bouton de connexion Facebook en haut de la page de création de compte.
  - `dashboardZoneOne.tpl` : Rend le bouton de connexion Facebook dans la zone un du tableau de bord client (moins courant pour la connexion, mais disponible).
  - `displayCustomerLoginFormAfter.tpl` : Rend le bouton de connexion Facebook directement après le formulaire de connexion client standard.
  - `displayNav.tpl` : Rend le bouton de connexion Facebook dans la barre de navigation principale.
  - `displayPersonalInformationTop.tpl` : Rend le bouton de connexion Facebook en haut de la page d'informations personnelles.
  - `displayPopUpLogin.tpl` : Rend le bouton de connexion Facebook dans la modale de connexion pop-up d'un thème.
  - `fblogin.tpl` : Un modèle générique pour le bouton de connexion Facebook, potentiellement utilisé par `displayfblogin` ou comme solution de repli.
  - `footer.tpl` : Rend le bouton de connexion Facebook dans le pied de page de la boutique.
  - `header.tpl` : Rend le bouton de connexion Facebook dans l'en-tête de la boutique.
  - `home.tpl` : Rend le bouton de connexion Facebook sur la page d'accueil.
  - `leftcolumn.tpl` : Rend le bouton de connexion Facebook dans la barre latérale gauche.
  - `rightcolumn.tpl` : Rend le bouton de connexion Facebook dans la barre latérale droite.
  - `shoppingCart.tpl` : Rend le bouton de connexion Facebook sur la page du panier.
  - `shoppingCartExtra.tpl` : Rend le bouton de connexion Facebook dans une zone supplémentaire de la page du panier.
  - `top.tpl` : Rend le bouton de connexion Facebook dans la section tout en haut de la boutique.
  - `topColumn.tpl` : Rend le bouton de connexion Facebook dans la zone de contenu principale, généralement au-dessus des listes de produits.
- **Modèles d'administration (`views/templates/admin/`)** :

  - Aucun. La configuration du module est rendue directement via `getContent()` dans `fblogin.php` à l'aide des assistants de formulaire PrestaShop standard.
- **Modèles Front-office (`views/templates/front/`)** :

  - Aucun. Tout l'affichage du front-office est géré via des modèles de hook.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de la base de données** :

  - Le module ne crée aucune table SQL personnalisée.
  - Les paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide de clés telles que `FBL_APPID`, `FBL_GROUPID`, `FBL_POPUP_LOGIN`, `FBL_DISPLAYTOP`, etc.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayRightColumn` | Rend le contenu dans la barre latérale droite. | Affiche le bouton de connexion Facebook dans la colonne de droite. |
| `displaypopuplogin` | Rend le contenu dans la pop-up de connexion d'un thème. | Affiche le bouton de connexion Facebook dans la pop-up de connexion. |
| `displayCreateAccountForm` | Rend le contenu dans le formulaire de création de compte client. | Affiche le bouton de connexion Facebook comme méthode d'inscription alternative. |
| `displayPersonalInformationTop` | Rend le contenu en haut de la page d'informations personnelles. | Affiche le bouton de connexion Facebook pour une inscription/connexion rapide. |
| `displayTop` | Rend le contenu dans la section tout en haut de la boutique. | Affiche le bouton de connexion Facebook dans la barre supérieure de l'en-tête. |
| `displayCreateAccountTop` | Rend le contenu en haut de la page de création de compte. | Affiche le bouton de connexion Facebook au-dessus du formulaire d'inscription. |
| `displayHeader` | Rend le contenu dans la section `<head>` du HTML et potentiellement les éléments d'en-tête visibles. | Injecte le JavaScript du SDK Facebook et affiche le bouton de connexion dans l'en-tête. |
| `displayNav` | Rend le contenu dans la barre de navigation principale. | Affiche le bouton de connexion Facebook dans la navigation. |
| `displayDashboardZoneOne` | Rend le contenu dans la première zone du tableau de bord client. | Affiche le bouton de connexion Facebook (moins courant pour les utilisateurs connectés). |
| `displayNav2` | Rend le contenu dans une barre de navigation secondaire (dépend du thème). | Affiche le bouton de connexion Facebook dans la navigation secondaire. |
| `displayShoppingCart` | Rend le contenu sur la page de résumé du panier. | Affiche le bouton de connexion Facebook pour une connexion rapide avant le paiement. |
| `displayTopColumn` | Rend le contenu dans la zone de contenu principale, généralement au-dessus des listes. | Affiche le bouton de connexion Facebook dans la colonne de contenu supérieure. |
| `displayFooter` | Rend le contenu dans le pied de page de la boutique. | Affiche le bouton de connexion Facebook dans le pied de page. |
| `displayfblogin` | Un hook personnalisé défini par le module lui-même. | Fournit un point flexible pour que les thèmes intègrent le bouton de connexion Facebook. |
| `displayHome` | Rend le contenu sur la page d'accueil de la boutique. | Affiche le bouton de connexion Facebook sur la page d'accueil. |
| `displayLeftColumn` | Rend le contenu dans la barre latérale gauche. | Affiche le bouton de connexion Facebook dans la colonne de gauche. |
| `displayCustomerLoginFormAfter` | Rend le contenu directement après le formulaire de connexion client standard. | Affiche le bouton de connexion Facebook comme méthode de connexion alternative. |
| `displayShoppingCartExtra` | Rend le contenu dans une zone supplémentaire de la page du panier. | Affiche le bouton de connexion Facebook dans une zone de panier supplémentaire. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant le module « Facebook Login Connect ».
