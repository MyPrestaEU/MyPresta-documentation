---
title: "Activation de compte par lien e-mail - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Activation de compte par lien e-mail' par MyPresta.eu."
sidebar:
  label: "Activation de compte par lien e-mail - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Account activation by email link sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/account-activation-by-email-link.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/account-activation-by-email-link/)
>
> ---


# Activation de compte par lien e-mail

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement nécessaire au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module « Activation de compte par lien e-mail ». Vous pouvez y accéder en naviguant vers **Modules > Gestionnaire de modules** et en cliquant sur « Configurer » à côté du nom du module.

#### **Paramètres généraux**

- **Envoyer un e-mail avec le lien d'activation du compte à l'administrateur :**

  - **Ce que fait ce paramètre :** Contrôle si une notification par e-mail est également envoyée à l'administrateur de la boutique (vous) chaque fois qu'un nouveau client s'inscrit et doit activer son compte.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (« Oui ») :* Vous recevrez une notification par e-mail à l'adresse e-mail de contact principale de votre boutique (généralement `PS_SHOP_EMAIL`) chaque fois qu'un nouveau client s'inscrit et est en attente d'activation. Cela peut être utile pour surveiller les nouvelles inscriptions.
    - *Lorsqu'désactivé (« Non ») :* Aucune notification par e-mail ne sera envoyée à l'administrateur lors de l'inscription d'un nouveau client.
  - **Valeur recommandée :** « Non » pour la plupart des boutiques afin d'éviter l'encombrement des e-mails, sauf si vous avez spécifiquement besoin de surveiller chaque nouvelle inscription.
  - **Scénario/exemple pour le marchand :** Si vous gérez une petite boutique de niche et que vous souhaitez accueillir personnellement ou examiner chaque nouveau client, l'activation de cette option peut vous tenir informé. Pour les grandes boutiques, c'est généralement inutile.
- **Titre de l'e-mail à l'administrateur :**

  - **Ce que fait ce paramètre :** Définit l'objet de l'e-mail envoyé à l'administrateur lorsqu'un nouveau compte est enregistré (si « Envoyer un e-mail avec le lien d'activation du compte à l'administrateur » est activé).
  - **Effet de la modification de ce paramètre :** Modifie l'objet de l'e-mail de notification de l'administrateur.
  - **Valeur recommandée :** « Nouvelle inscription client en attente d'activation - {shop\_name} » (ou similaire, en utilisant `{shop_name}` pour le nom de votre boutique).
  - **Scénario/exemple pour le marchand :** Vous pourriez vouloir inclure le nom de votre boutique dans le titre pour une identification facile dans votre boîte de réception, par exemple, « Nouveau client chez Ma Super Boutique - Activation en attente. »
- **Connexion automatique du client après activation :**

  - **Ce que fait ce paramètre :** Détermine si un client est automatiquement connecté à son compte immédiatement après avoir cliqué sur le lien d'activation dans son e-mail.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (« Oui ») :* Après avoir cliqué sur le lien d'activation, le client est connecté de manière transparente à son compte nouvellement activé et généralement redirigé vers son tableau de bord de compte ou la page d'accueil. Cela offre une expérience utilisateur plus fluide.
    - *Lorsqu'désactivé (« Non ») :* Après avoir cliqué sur le lien d'activation, le compte du client est activé, mais il n'est *pas* automatiquement connecté. Il sera redirigé vers la page de connexion et invité à saisir ses identifiants manuellement.
  - **Valeur recommandée :** « Oui » pour une meilleure expérience client, réduisant les frictions.
  - **Scénario/exemple pour le marchand :** L'activation de cette option rend le processus d'activation plus complet et convivial, car le client n'a pas d'étape supplémentaire à effectuer après avoir vérifié son e-mail.
- **Activer le compte sur une page spécifique :**

  - **Ce que fait ce paramètre :** Vous permet de définir une page spécifique de votre boutique vers laquelle le client sera redirigé *après* que son compte ait été activé avec succès.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (« Oui ») :* Le module utilisera l'URL spécifiée dans le champ « Lien de la page d'activation spécifique » pour la redirection après activation.
    - *Lorsqu'désactivé (« Non ») :* Le client sera redirigé vers la page par défaut (généralement la page d'accueil ou sa page de compte client) après activation.
  - **Valeur recommandée :** « Non » par défaut, sauf si vous avez une stratégie marketing ou d'intégration spécifique.
  - **Scénario/exemple pour le marchand :** Vous pourriez vouloir rediriger les nouveaux clients vers une page « Bienvenue » avec des offres spéciales, un guide de votre boutique ou une catégorie de produits spécifique pour encourager leur premier achat.
- **Lien de la page d'activation spécifique :**

  - **Ce que fait ce paramètre :** Ce champ apparaît uniquement si « Activer le compte sur une page spécifique » est activé. C'est là que vous entrez l'URL complète de la page vers laquelle vous souhaitez rediriger les clients après activation.
  - **Effet de la modification de ce paramètre :** Définit l'URL de destination exacte pour la redirection post-activation.
  - **Valeur recommandée :** Laisser vide si « Activer le compte sur une page spécifique » est « Non ». Si activé, fournir une URL complète et valide (par exemple, `https://votreboutique.com/content/1-livraison`).
  - **Scénario/exemple pour le marchand :** Si vous avez une page « Bienvenue aux nouveaux clients » à l'adresse `https://votreboutique.com/bienvenue-nouveaux-clients`, vous saisiriez cette URL ici.

#### **Paramètres de contenu de l'e-mail**

- **Titre de l'e-mail au client :**
  - **Ce que fait ce paramètre :** Définit l'objet de l'e-mail d'activation envoyé au client.
  - **Effet de la modification de ce paramètre :** Modifie l'objet que les clients voient dans leur boîte de réception pour l'e-mail d'activation.
  - **Valeur recommandée :** « Activez votre compte sur {shop\_name} » ou « Veuillez vérifier votre e-mail pour {shop\_name} » (en utilisant `{shop_name}` pour le nom de votre boutique).
  - **Scénario/exemple pour le marchand :** Un objet clair et concis aide les clients à identifier l'e-mail et les encourage à l'ouvrir, réduisant ainsi le risque qu'il soit marqué comme spam.

#### **Autres paramètres (internes / techniques)**

- **mypresta\_updates, update\_, updatev\_ :** Ce sont des paramètres internes utilisés par les modules MyPresta.eu pour les vérifications de mise à jour et la gestion des versions. Vous ne devriez généralement **pas** les modifier.
- **PS\_SHOP\_EMAIL, PS\_SHOP\_NAME, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG, PS\_CART\_FOLLOWING :** Ce sont des valeurs de configuration PrestaShop standard que le module peut lire ou afficher pour le contexte, mais qui ne sont pas directement configurables dans le module lui-même. Elles reflètent vos paramètres généraux de PrestaShop.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Envoyer un e-mail avec le lien d'activation du compte à l'administrateur | Non | Contrôle la notification de l'administrateur pour les nouvelles inscriptions. |
| Configuration du module | Titre de l'e-mail à l'administrateur | « Nouvelle inscription client en attente d'activation - {shop\_name} » | Objet de l'e-mail de notification de l'administrateur. |
| Configuration du module | Connexion automatique du client après activation | Oui | Connecte automatiquement le client après une activation réussie. |
| Configuration du module | Activer le compte sur une page spécifique | Non | Active la redirection vers une page personnalisée après l'activation. |
| Configuration du module | Lien de la page d'activation spécifique | (Vide si désactivé) | URL pour la redirection post-activation (si activé). |
| Configuration du module | Titre de l'e-mail au client | « Activez votre compte sur {shop\_name} » | Objet de l'e-mail d'activation du client. |

## 3. Dépannage pour le marchand et questions fréquemment posées (FAQ)

**Q1 : Mes clients ne reçoivent pas l'e-mail d'activation. Que dois-je faire ?**

- **R :**
  1. **Vérifier les dossiers de spam/courrier indésirable :** Conseillez aux clients de vérifier leurs dossiers de spam ou de courrier indésirable.
  2. **Vérifier les paramètres d'e-mail de la boutique :** Allez dans **Paramètres de la boutique > Contact > Magasins** (ou **Paramètres avancés > E-mail** dans les versions antérieures) dans votre Back Office PrestaShop. Assurez-vous que la configuration de l'e-mail de votre boutique est correcte et que les e-mails sont envoyés avec succès (testez en envoyant un e-mail de test).
  3. **Fonctionnalité de messagerie du serveur :** Contactez votre hébergeur pour vous assurer que la fonction de messagerie de votre serveur (PHP `mail()` ou SMTP) fonctionne correctement et n'est pas bloquée.
  4. **Configuration du module :** Vérifiez à nouveau le « Titre de l'e-mail au client » dans les paramètres du module. Un titre très générique ou suspect pourrait déclencher les filtres anti-spam.
  5. **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures). Parfois, des problèmes de cache peuvent empêcher l'envoi d'e-mails.

**Q2 : Un client a activé son compte mais ne peut toujours pas se connecter.**

- **R :**
  1. **Vérifier le statut du client :** Dans votre Back Office PrestaShop, allez dans **Clients > Clients**. Trouvez le compte du client et vérifiez que son statut « Activé » est défini sur « Oui ». Si ce n'est pas le cas, activez-le manuellement.
  2. **Réinitialisation du mot de passe :** Suggérez au client d'essayer le lien « Mot de passe oublié » sur votre page de connexion. Cela peut résoudre les problèmes s'il se trompe de mot de passe.
  3. **Cache/cookies du navigateur :** Demandez au client de vider le cache et les cookies de son navigateur, ou d'essayer de se connecter à partir d'un navigateur différent ou d'une fenêtre de navigation privée.
  4. **Conflit de module :** Désactivez temporairement les autres modules qui interagissent avec les comptes clients ou les processus de connexion pour exclure les conflits.

**Q3 : Comment puis-je activer manuellement le compte d'un client s'il ne peut pas recevoir l'e-mail ?**

- **R :** Vous pouvez activer manuellement le compte d'un client depuis le Back Office de PrestaShop :
  1. Allez dans **Clients > Clients**.
  2. Trouvez le nom du client dans la liste et cliquez sur « Modifier » (l'icône en forme de crayon).
  3. Sur la page des détails du client, localisez l'interrupteur « Activé » et réglez-le sur « Oui ».
  4. Cliquez sur « Enregistrer ». Le client pourra désormais se connecter.

**Q4 : Le lien d'activation redirige vers la mauvaise page ou affiche une erreur.**

- **R :**
  1. **Vérification du « Lien de la page d'activation spécifique » :** Si vous avez activé « Activer le compte sur une page spécifique », vérifiez que l'URL saisie dans « Lien de la page d'activation spécifique » est absolument correcte et accessible. Une faute de frappe ou une URL invalide entraînera des problèmes de redirection.
  2. **URL conviviales :** Assurez-vous que vos URL conviviales sont activées et fonctionnent correctement (**Paramètres de la boutique > Trafic & SEO**).
  3. **Vider le cache :** Videz le cache de votre PrestaShop (**Paramètres avancés > Performances**).
  4. **Vérifier .htaccess :** Si vous avez effectué des modifications manuelles à votre fichier `.htaccess`, annulez-les ou assurez-vous qu'elles n'interfèrent pas avec la réécriture d'URL.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Activation de compte par lien e-mail » (`acactiv`) est un module PrestaShop standard principalement conçu pour intercepter le processus d'inscription des clients. Il utilise le système de hooks de PrestaShop pour modifier le comportement par défaut, spécifiquement `actionCustomerAccountAdd` pour marquer les nouveaux comptes comme inactifs et envoyer des e-mails d'activation, et `displayHeader` pour injecter le JavaScript nécessaire. Le module n'introduit pas de nouvelles tables de base de données ou de structures `ObjectModel` complexes, mais s'appuie plutôt sur la modification des propriétés existantes de l'objet `Customer` et l'utilisation de `ps_configuration` pour ses paramètres.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs dédiés au front-office ou au back-office. Toute la logique est gérée dans le fichier principal du module (`acactiv.php`) et ses hooks enregistrés. Le lien d'activation lui-même pointe vers la distribution principale du module, qui gère ensuite la logique d'activation.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module n'introduit aucune classe ou modèle personnalisé dans le répertoire `classes/`. Il interagit directement avec la classe `Customer` et la classe `Configuration` de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

- **`acactiv/views/acactiv-compat.js`**

  - **Portée :** Front-office.
  - **Objectif :** Ce script contient probablement des correctifs de compatibilité ou des polyfills pour les anciennes versions de PrestaShop ou les navigateurs, garantissant que la fonctionnalité front-end du module fonctionne sur un plus large éventail d'environnements. Il pourrait aborder les différences dans les versions de jQuery ou les méthodes de manipulation du DOM.
  - **Écouteurs d'événements/Manipulation du DOM :** Les détails nécessiteraient une revue de code, mais impliquent généralement de s'assurer que les éléments sont présents ou d'ajuster les comportements en fonction de la version de PrestaShop.
- **`acactiv/views/acactiv.js`**

  - **Portée :** Front-office.
  - **Objectif :** Il s'agit du fichier JavaScript principal pour les interactions front-office. Il est responsable de l'affichage des messages à l'utilisateur après l'inscription (par exemple, « Vérifiez votre e-mail pour le lien d'activation ») et potentiellement de la gestion des aspects côté client du processus d'activation.
  - **Écouteurs d'événements/Manipulation du DOM :**
    - Peut écouter les soumissions de formulaires sur la page d'inscription pour afficher des messages personnalisés.
    - Pourrait manipuler le DOM pour afficher/masquer des éléments, afficher des notifications pop-up ou rediriger l'utilisateur après certaines actions.
    - Pourrait utiliser `prestashop.on('updatedProduct', function(event) { ... });` ou des écouteurs d'événements PrestaShop similaires s'il doit réagir aux mises à jour de contenu dynamique, bien que moins probable pour la fonction principale de ce module.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`acactiv/views/acactiv.css`**
  - **Portée :** Style client du front-office.
  - **Objectif :** Fournit un style de base pour tous les messages ou éléments personnalisés introduits par le module sur le front-office. Cela pourrait inclure le style du message « compte en attente d'activation » ou de la confirmation « compte activé ».
  - **Sélecteurs de classe CSS clés :** Les développeurs doivent inspecter le code HTML de sortie du module pour identifier les classes spécifiques (par exemple, `.acactiv-message`, `.acactiv-success`, `.acactiv-error`) qui peuvent être remplacées dans le `custom.css` ou `theme.css` de leur thème pour correspondre à l'image de marque de la boutique.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **Modèles de hook (`views/templates/hook/`)** :

  - **`acactiv/views/checkout_notice.tpl`**
    - **Hook :** Non explicitement indiqué comme modèle de hook, mais son nom suggère qu'il pourrait être rendu dans un contexte lié à la commande ou à la création de compte, éventuellement via `displayCustomerAccountForm` ou similaire, pour afficher un avis concernant l'activation.
    - **Sortie :** Affiche probablement un message d'information au client après l'inscription, lui demandant de vérifier son e-mail pour le lien d'activation.
  - **`acactiv/views/displayHeader.tpl`**
    - **Hook :** `displayHeader`
    - **Sortie :** Ce modèle est généralement utilisé pour inclure des fichiers CSS et JavaScript dans la section `<head>` des pages du front-office. Il contiendra des balises `<link>` pour `acactiv.css` et des balises `<script>` pour `acactiv-compat.js` et `acactiv.js`, garantissant que ces actifs sont chargés sur les pages pertinentes.
- **Modèles d'administration (`views/templates/admin/`)** : Aucun identifié. La configuration est gérée directement dans `getContent()` au sein de `acactiv.php`.
- **Modèles de front-office (`views/templates/front/`)** : Aucun identifié comme pages autonomes dédiées.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Ce module ne crée pas de tables SQL personnalisées.
  - Il modifie la colonne `active` de la table `ps_customer` (en la définissant à `0` pour les nouvelles inscriptions jusqu'à l'activation).
  - Les paramètres de configuration sont stockés dans la table `ps_configuration` avec des clés comme `ACACTIV_SENDTOME`, `ACACTIV_SPECURLFEATURE`, `ACACTIV_SPECURL`, `ACACTIV_AUTOLOGIN`, `ACACTIV_ATITLE`, `ACACTIV_CTITLE`.
- **Table des hooks enregistrés** :
"""
