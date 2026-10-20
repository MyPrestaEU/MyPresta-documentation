---
title: "Notification de nouveau compte client - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Notification de nouveau compte client par MyPresta.eu."
sidebar:
  label: "Notification de nouveau compte client - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Notification about new customer account sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/notification-about-new-customer-account.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/notification-about-new-customer-account/)
>
> ---


# Notification de nouveau compte client

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes et sont habituellement activées par défaut sur la plupart des environnements d'hébergement.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Notification de nouveau compte client ». L'écran de configuration principal s'affichera.

#### **1. Envoyer une notification au propriétaire de la boutique concernant un nouveau compte client**

-   **Ce que fait ce paramètre :** Ce commutateur contrôle si vous, le propriétaire de la boutique, recevez une notification par e-mail lorsqu'un nouveau client s'inscrit sur votre boutique.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'activé (OUI) :* Chaque fois qu'un client crée un compte avec succès sur le front office de votre boutique, un e-mail sera envoyé à l'adresse(s) e-mail spécifiée(s) dans le champ « Adresse(s) e-mail pour les notifications » ci-dessous.
    -   *Lorsqu'désactivé (NON) :* Vous ne recevrez aucune notification par e-mail concernant les nouvelles inscriptions de clients.
-   **Valeur recommandée :** OUI.
-   **Scénario / exemple de marchand :** Vous souhaitez être immédiatement informé des nouvelles inscriptions de clients pour suivre la croissance ou identifier des prospects potentiels pour une campagne de bienvenue. L'activation de cette option vous assure d'obtenir cette information cruciale.

#### **2. Adresse(s) e-mail pour les notifications**

-   **Ce que fait ce paramètre :** Ce champ spécifie l'adresse(s) e-mail où les notifications de nouvelle inscription client seront envoyées.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'une ou plusieurs adresses e-mail sont définies :* Les notifications seront livrées à ces adresses. Si vous entrez plusieurs adresses, séparez-les par une virgule (par exemple, `admin@votreboutique.com, support@votreboutique.com`).
    -   *Lorsqu'il est laissé vide :* Même si « Envoyer une notification au propriétaire de la boutique » est activé, aucun e-mail ne sera envoyé car il n'y a pas de destinataire.
-   **Valeur recommandée :** Votre adresse e-mail d'administration principale de la boutique, ou une adresse e-mail d'équipe dédiée (par exemple, `info@votreboutique.com`).
-   **Scénario / exemple de marchand :** Vous souhaitez que vous-même et votre équipe de support client receviez les alertes de nouvelle inscription. Vous entreriez `votrenom@votreboutique.com, support@votreboutique.com` ici.

#### **3. Envoyer une notification au client si l'administrateur crée un nouveau compte**

-   **Ce que fait ce paramètre :** Ce commutateur détermine si un e-mail de bienvenue est automatiquement envoyé à un client si son compte est créé manuellement par un administrateur dans le Back Office de PrestaShop (par exemple, via Clients > Ajouter un nouveau client).
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'activé (OUI) :* Lorsque vous ou un autre administrateur créez un nouveau compte client dans le Back Office, le client nouvellement créé recevra automatiquement un e-mail de bienvenue. Cet e-mail inclut généralement ses identifiants de connexion ou une confirmation de la création de son compte.
    -   *Lorsqu'désactivé (NON) :* Les clients dont les comptes sont créés manuellement dans le Back Office ne recevront aucun e-mail de bienvenue automatique du module. Vous devrez les informer manuellement si vous le souhaitez.
-   **Valeur recommandée :** OUI.
-   **Scénario / exemple de marchand :** Vous créez fréquemment des comptes pour des clients B2B ou pour des clients qui passent des commandes par téléphone. L'activation de cette option garantit qu'ils reçoivent un e-mail de bienvenue immédiat et professionnel sans que vous ayez à le composer et à l'envoyer manuellement à chaque fois.

#### **4. Bouton Enregistrer**

-   **Ce que cela fait :** Après avoir apporté des modifications aux paramètres ci-dessus, vous devez cliquer sur ce bouton pour appliquer et enregistrer votre nouvelle configuration.
-   **Effet du clic :** Vos modifications sont enregistrées dans la base de données, et le module commencera à fonctionner immédiatement selon les nouveaux paramètres.
-   **Action recommandée :** Cliquez toujours sur « Enregistrer » après avoir modifié un paramètre.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Envoyer une notification au propriétaire de la boutique concernant un nouveau compte client | OUI | Contrôle si le propriétaire de la boutique reçoit un e-mail lors de l'inscription d'un nouveau client. |
| Configuration du module | Adresse(s) e-mail pour les notifications | E-mail principal de votre boutique | Spécifie le(s) destinataire(s) des notifications du propriétaire (séparées par des virgules). |
| Configuration du module | Envoyer une notification au client si l'administrateur crée un nouveau compte | OUI | Contrôle si le client reçoit un e-mail de bienvenue lorsque l'administrateur crée son compte. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Je ne reçois pas les notifications de nouveaux clients, mais le module est activé. Que dois-je vérifier ?**
R1 :

-   **Vérifiez les adresses e-mail :** Vérifiez à nouveau le champ « Adresse(s) e-mail pour les notifications » dans la configuration du module. Assurez-vous qu'il est correctement saisi et qu'il n'y a pas de fautes de frappe. S'il y en a plusieurs, assurez-vous qu'elles sont séparées par des virgules.
-   **Dossier Spam :** Vérifiez le dossier spam ou courrier indésirable de votre e-mail. Les notifications pourraient y être filtrées.
-   **Paramètres e-mail de PrestaShop :** Vérifiez que les paramètres e-mail principaux de votre PrestaShop (Paramètres avancés > E-mail) sont correctement configurés et envoient des e-mails avec succès. Vous pouvez envoyer un e-mail de test à partir de là.
-   **Problèmes d'e-mail d'hébergement :** Contactez votre fournisseur d'hébergement pour vous assurer qu'il n'y a pas de restrictions d'envoi d'e-mails côté serveur ou de problèmes avec votre serveur de messagerie.

**Q2 : Mes clients ne reçoivent pas d'e-mails de bienvenue lorsque je crée leurs comptes dans le Back Office.**
R2 :

-   **Paramètre du module :** Assurez-vous que « Envoyer une notification au client si l'administrateur crée un nouveau compte » est défini sur OUI dans la configuration du module.
-   **E-mail du client :** Vérifiez que l'adresse e-mail saisie pour le client dans le Back Office est correcte et valide.
-   **Dossier Spam du client :** Conseillez au client de vérifier son dossier spam ou courrier indésirable.
-   **Paramètres e-mail de PrestaShop :** Comme ci-dessus, assurez-vous que les paramètres généraux d'e-mail de votre boutique sont fonctionnels.

**Q3 : Puis-je personnaliser le contenu des e-mails de notification ?**
R3 : Ce module, dans sa version actuelle, envoie des e-mails système PrestaShop standard. La personnalisation du contenu nécessiterait généralement une modification directe des modèles d'e-mail de PrestaShop (situés dans le répertoire `mails/` pour votre langue) ou du code principal du module, ce qui n'est pas recommandé pour les marchands. Pour une personnalisation avancée, consultez un développeur.

**Q4 : Ce module va-t-il ralentir ma boutique ?**
R4 : Non. Ce module effectue une opération très légère (envoi d'un e-mail) uniquement lorsqu'un nouveau compte client est créé. Il n'ajoute aucune surcharge aux chargements de page ou aux performances générales de la boutique.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module « Notification de nouveau compte client ».

### 4.1 Aperçu de l'architecture

Le module `registernotification` est un module PrestaShop standard suivant le modèle de type MVC. Il utilise principalement le système de hooks de PrestaShop pour intercepter les événements liés à l'inscription des clients et utilise ensuite la classe `Mail` de PrestaShop pour envoyer des notifications. Il stocke sa configuration directement dans la table `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise aucun contrôleur front-office ou back-office personnalisé. Toute la logique est encapsulée dans la classe principale du module et sa méthode `getContent()` pour la configuration.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée ou instance `ObjectModel`. Toute la logique principale réside dans la classe `registernotification` principale.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Ce module n'inclut aucun fichier de modèle Smarty personnalisé. Il s'appuie sur les modèles d'e-mail par défaut de PrestaShop pour les notifications aux clients.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :
    Le module ne crée aucune table de base de données personnalisée. Tous ses paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide de clés préfixées par `REGISTERNOTIFICATION_`.

    -   Entrées `PS_CONFIGURATION` :
        -   `REGISTERNOTIFICATION_SEND_OWNER` : Stocke la valeur booléenne (0 ou 1) pour l'envoi de notifications au propriétaire de la boutique.
        -   `REGISTERNOTIFICATION_EMAIL_ADDRESSES` : Stocke la chaîne d'adresses e-mail séparées par des virgules pour les notifications du propriétaire.
        -   `REGISTERNOTIFICATION_SEND_CUSTOMER_ADMIN` : Stocke la valeur booléenne (0 ou 1) pour l'envoi de notifications aux clients lorsque créés par un administrateur.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionCustomerAccountAdd` | Exécuté immédiatement après qu'un nouveau compte client est ajouté avec succès à la base de données. | Ce hook est utilisé pour déclencher la notification par e-mail au propriétaire de la boutique lorsqu'un client s'inscrit via le front office. Il déclenche également l'e-mail de bienvenue au client si son compte a été créé par un administrateur dans le back office. |
| `displayBackOfficeHeader` | Exécuté lorsque l'en-tête du Back Office est rendu. | Généralement utilisé pour ajouter du CSS/JS ou afficher des alertes dans le Back Office. Bien que listé comme un hook potentiel, son utilisation principale dans ce module serait pour afficher un message de succès/erreur après l'enregistrement de la configuration, ou potentiellement pour ajouter des actifs spécifiques au module (bien qu'aucun ne soit présent). |

### 4.8 Structure des fichiers du module (`registernotification/`)

-   `index.php` : Le fichier principal du module. Ce fichier contient la classe `registernotification`, qui étend `Module`. Il gère :
    -   `__construct()` : Initialisation du module, configuration du nom, de l'onglet, de la version, de l'auteur, etc.
    -   `install()` : Enregistre les hooks nécessaires (`actionCustomerAccountAdd`, `displayBackOfficeHeader`) et définit les valeurs de configuration par défaut dans `ps_configuration`.
    -   `uninstall()` : Désenregistre les hooks et supprime les valeurs de configuration.
    -   `getContent()` : Rend le formulaire de configuration du module dans le Back Office, gère la soumission du formulaire et met à jour `ps_configuration`.
    -   `hookActionCustomerAccountAdd($params)` : La logique principale pour l'envoi d'e-mails. Il vérifie la configuration du module et utilise `Mail::Send()` pour envoyer des e-mails au propriétaire et/ou au nouveau client en fonction du contexte de création du compte.
    -   `hookDisplayBackOfficeHeader()` : Potentiellement utilisé pour afficher des messages de confirmation après l'enregistrement de la configuration.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Notification de nouveau compte client », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir.
