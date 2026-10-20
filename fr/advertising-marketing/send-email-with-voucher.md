---
title: "Envoyer un e-mail avec un bon de réduction - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Envoyer un e-mail avec un bon de réduction' par MyPresta.eu."
sidebar:
  label: "Envoyer un e-mail avec un bon de réduction - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Send email with voucher sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/send-email-with-voucher.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/send-email-with-voucher/)
>
> ---


# Envoyer un e-mail avec un bon de réduction

## 1. Exigences et Compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont habituellement disponibles sur tout environnement d'hébergement moderne.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Envoyer un e-mail avec un bon de réduction)

Ceci est l'écran de configuration principal où vous gérez les paramètres d'envoi de vos e-mails de bons de réduction.

#### **Section Gestionnaire de modèles d'e-mail**

Cette section est l'endroit où vous définissez le contenu et l'apparence des e-mails qui contiendront vos codes de bon de réduction.

-   **Ce que fait cette section :** Cet outil puissant vous permet de créer, modifier et gérer différents modèles d'e-mail. Chaque modèle peut avoir sa propre ligne d'objet et son propre contenu, ce qui facilite l'envoi de divers types d'offres de bons de réduction (par exemple, « Remise de bienvenue », « Cadeau d'anniversaire », « Offre de panier abandonné »).
-   **Effet de la modification des paramètres :**
    *   *Création d'un nouveau modèle :* Vous définissez un nouveau design d'e-mail et une ligne d'objet que vous pourrez sélectionner ultérieurement lors de l'envoi de bons de réduction.
    *   *Modification d'un modèle existant :* Les modifications apportées à l'objet ou au contenu s'appliqueront à tous les futurs e-mails envoyés à l'aide de ce modèle spécifique.
    *   *Suppression d'un modèle :* Le modèle ne sera plus disponible pour la sélection.
-   **Flux de travail recommandé :** Commencez par créer quelques modèles standard pour vos campagnes de bons de réduction les plus courantes. Par exemple, un modèle « Bienvenue » pour les nouveaux clients, un modèle « Fidélité » pour les acheteurs réguliers et un modèle « Offre spéciale » pour les promotions.

#### **Section Moteur de bons de réduction**

Cette section est l'endroit où vous générez et envoyez réellement les codes de bon de réduction.

-   **Ce que fait cette section :** C'est la fonctionnalité principale pour créer des règles de réduction (bons de réduction) et les envoyer à des adresses e-mail spécifiques. Vous pouvez définir le type de réduction (pourcentage, montant fixe), la valeur, les conditions (achat minimum, produits spécifiques) et la période de validité.
-   **Effet de la modification des paramètres :**
    *   *Création d'un nouveau bon de réduction :* Une nouvelle règle de réduction est créée dans votre catalogue PrestaShop, et un code unique est généré.
    *   *Envoi d'un bon de réduction :* Un e-mail contenant le code unique et le contenu du modèle sélectionné est envoyé au(x) destinataire(s) spécifié(s).
    *   *Association avec un client :* Le bon de réduction peut être lié au compte d'un client spécifique, ce qui signifie que seul ce client peut l'utiliser.
-   **Flux de travail recommandé :**
    1.  Tout d'abord, créez ou sélectionnez un modèle d'e-mail approprié dans la section « Gestionnaire de modèles d'e-mail ».
    2.  Ensuite, utilisez le « Moteur de bons de réduction » pour définir vos paramètres de réduction (par exemple, 10 % de réduction, valable 30 jours, achat minimum de 50 €).
    3.  Spécifiez la ou les adresses e-mail du destinataire.
    4.  Choisissez d'associer ou non le bon de réduction à un compte client existant.
    5.  Cliquez sur « Envoyer » pour générer et envoyer le bon de réduction personnalisé.

#### **Paramètres spécifiques au sein de la page de configuration**

Bien que l'interface principale du module se fasse via les sections « Gestionnaire de modèles d'e-mail » et « Moteur de bons de réduction », il existe des clés de configuration sous-jacentes qui contrôlent le comportement par défaut. Celles-ci sont souvent gérées implicitement par l'interface du module, mais il est bon de comprendre leur objectif.

-   **Titre de l'e-mail**

    *   **Ce que fait ce paramètre :** C'est la ligne d'objet par défaut pour les e-mails envoyés avec des bons de réduction, si elle n'est pas remplacée par un modèle spécifique.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur « Votre réduction spéciale » :* Les e-mails auront par défaut cette ligne d'objet.
        *   *Lorsqu'il est modifié en « Offre exclusive de [Nom de votre boutique] » :* Tous les nouveaux e-mails (sans modèle spécifique le remplaçant) utiliseront cette nouvelle ligne d'objet.
    *   **Valeur recommandée :** Quelque chose de clair et d'attrayant, comme « Votre bon de réduction exclusif de [Nom de votre boutique] ».
    *   **Scénario / exemple pour le marchand :** Vous souhaitez que tous vos e-mails de bons de réduction aient un message de marque cohérent dans la ligne d'objet.
-   **Fichier de modèle d'e-mail**

    *   **Ce que fait ce paramètre :** Il fait référence au fichier de modèle d'e-mail par défaut utilisé pour l'envoi de bons de réduction. La section « Gestionnaire de modèles d'e-mail » offre un moyen plus convivial de gérer et de sélectionner des modèles.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur `voucher_email.html` :* Le module utilisera ce fichier spécifique pour le corps de l'e-mail si aucun autre modèle n'est sélectionné.
    *   **Valeur recommandée :** Utilisez l'interface du « Gestionnaire de modèles d'e-mail » pour créer et sélectionner des modèles, car elle est plus flexible et ne nécessite pas de manipulation directe de fichiers.
    *   **Scénario / exemple pour le marchand :** Vous avez un fichier de modèle d'e-mail HTML personnalisé que vous souhaitez utiliser comme base pour tous vos e-mails de bons de réduction.

#### **Autres clés de configuration (Internes)**

Ce sont des clés de configuration internes de PrestaShop que le module peut référencer pour ses opérations, mais vous ne les configurerez généralement pas directement dans l'interface du module.

-   `PS_SHOP_EMAIL` : L'adresse e-mail de contact principale de votre boutique. Utilisée comme e-mail de l'expéditeur pour les bons de réduction.
-   `PS_SHOP_NAME` : Le nom de votre boutique. Utilisé dans les objets ou corps des e-mails.
-   `PS_LANG_DEFAULT` : La langue par défaut de votre boutique.
-   `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` : Paramètre lié à la langue de l'employé dans le back-office.
-   `mypresta_updates`, `update_`, `updatev_` : Clés internes utilisées par les modules MyPresta.eu pour les vérifications de mise à jour et la gestion des versions.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | **Gestionnaire de modèles d'e-mail** | N/A (créer au besoin) | Créez et gérez des modèles d'e-mail personnalisés pour les e-mails de bons de réduction. |
| Page de configuration du module | **Moteur de bons de réduction** | N/A (créer au besoin) | Générez des codes de bons de réduction uniques avec des règles spécifiques et envoyez-les par e-mail. |
| Page de configuration du module | Titre de l'e-mail | « Votre réduction spéciale » (exemple) | Ligne d'objet par défaut pour les e-mails de bons de réduction. |
| Page de configuration du module | Fichier de modèle d'e-mail | `voucher_email.html` (exemple) | Fichier HTML par défaut utilisé pour le contenu de l'e-mail. Utilisez le Gestionnaire de modèles d'e-mail pour un meilleur contrôle. |

## 3. Dépannage pour les marchands et Foire aux questions (FAQ)

**Q : Mes clients ne reçoivent pas les e-mails de bons de réduction. Que dois-je vérifier ?**
R :

1.  **Vérifiez les paramètres d'e-mail de votre boutique :** Allez dans **Paramètres avancés > E-mail** dans votre back-office PrestaShop. Assurez-vous que votre configuration d'e-mail (SMTP ou PHP mail) est correcte et testez l'envoi d'un e-mail général.
2.  **Dossiers de spam :** Demandez à vos clients de vérifier leurs dossiers de spam ou de courrier indésirable.
3.  **Contenu du modèle d'e-mail :** Assurez-vous que vos modèles d'e-mail ne sont pas trop « spammy » (par exemple, utilisation excessive de majuscules, trop de points d'exclamation).
4.  **Journaux du module :** Vérifiez si le module fournit des journaux ou des messages d'erreur pendant le processus d'envoi. (Cela peut nécessiter l'aide d'un développeur).

**Q : Le code du bon de réduction a été envoyé, mais le client dit qu'il ne fonctionne pas.**
R :

1.  **Vérifiez la validité du bon de réduction :** Dans votre back-office PrestaShop, allez dans **Catalogue > Réductions > Règles panier**. Trouvez le code du bon de réduction et vérifiez ses dates de validité, le montant minimum, les restrictions client et s'il a déjà été utilisé.
2.  **Association client :** Si le bon de réduction a été associé à un client spécifique, assurez-vous que le client est connecté au bon compte lorsqu'il essaie de l'utiliser.
3.  **Fautes de frappe :** Demandez au client de vérifier attentivement les fautes de frappe lors de la saisie du code.

**Q : Puis-je envoyer le même code de bon de réduction à plusieurs clients ?**
R : Oui, vous pouvez générer un seul code de bon de réduction et l'envoyer à plusieurs adresses e-mail. Cependant, pour un meilleur suivi et pour éviter une utilisation excessive, il est généralement recommandé de générer des codes uniques pour chaque destinataire, en particulier pour les offres personnalisées. Le « Moteur de bons de réduction » du module est conçu pour générer des codes uniques.

**Q : Comment personnaliser l'apparence des modèles d'e-mail ?**
R : Utilisez la section « Gestionnaire de modèles d'e-mail » dans la configuration du module. Elle fournit une interface pour modifier l'objet et le corps de vos modèles d'e-mail. Pour une personnalisation HTML/CSS avancée, vous devrez peut-être modifier les fichiers de modèles sous-jacents (voir la section 7 pour les développeurs).

**Q : Le module ne s'affiche pas correctement après l'installation, ou je vois une page blanche.**
R :

1.  **Videz le cache Smarty :** Allez dans **Paramètres avancés > Performances** dans votre back-office PrestaShop. Définissez « Compilation des templates » sur « Recompiler les templates si les fichiers ont été mis à jour » et « Cache » sur « Non ». Ensuite, cliquez sur « Vider le cache » en haut à droite. Après vérification, vous pouvez remettre « Cache » sur « Oui » et « Compilation des templates » sur « Ne jamais recompiler... » pour des raisons de performance.
2.  **Vérifiez la version de PHP :** Assurez-vous que votre version de PHP se situe dans la plage prise en charge (PHP 5.6 - 8.5).
3.  **Journaux d'erreurs du serveur :** Vérifiez les journaux d'erreurs PHP de votre serveur pour tout message d'erreur spécifique. Cela nécessite généralement un accès à votre panneau de contrôle d'hébergement.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Envoyer un e-mail avec un bon de réduction » suit une architecture de module PrestaShop standard, exploitant principalement la classe `Module` pour sa fonctionnalité principale et sa configuration. Il intègre du JavaScript et du CSS personnalisés pour son interface de back-office, en particulier pour les outils de gestion des modèles d'e-mail et de génération de bons de réduction. Le module n'introduit pas de contrôleurs de front-office personnalisés ni d'entités `ObjectModel` complexes, mais interagit plutôt avec les classes `CartRule` (réduction) et `Mail` intégrées de PrestaShop.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient aucun contrôleur de front-office ou de back-office personnalisé dans le répertoire `controllers/`. Toute la logique administrative et la configuration sont gérées dans la méthode `getContent()` du fichier principal du module (`sendvouchers.php`).

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe ou modèle personnalisé dans un répertoire `classes/`. Il s'appuie sur les classes principales de PrestaShop, telles que `CartRule` pour la gestion des réductions et `Mail` pour l'envoi d'e-mails.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`sendvouchers/lib/emailTemplatesManager/js/emailTemplatesManager.js`**

    *   **Portée :** Back-office (page de configuration du module).
    *   **Responsabilité :** Gère les éléments interactifs de l'interface de création, d'édition et de suppression des modèles d'e-mail. Ce script gère probablement les appels AJAX pour enregistrer/mettre à jour les données des modèles, rend les formulaires dynamiquement et gère les interactions utilisateur dans la section « Gestionnaire de modèles d'e-mail ». Il peut utiliser jQuery pour la manipulation du DOM et la liaison d'événements.
-   **`sendvouchers/lib/voucherengine/script.js`**

    *   **Portée :** Back-office (page de configuration du module).
    *   **Responsabilité :** Alimente la section « Moteur de bons de réduction ». Ce script est responsable de la génération des codes de bons de réduction, de la configuration des règles de réduction (par exemple, pourcentage, montant fixe, conditions), de la sélection des modèles d'e-mail et du lancement du processus d'envoi des bons de réduction. Il effectue probablement une validation côté client et des requêtes AJAX à la méthode `getContent()` du module pour le traitement côté serveur.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`sendvouchers/lib/emailTemplatesManager/css/emailTemplatesManager.css`**

    *   **Portée :** Style du formulaire d'administration du back-office.
    *   **Responsabilité :** Fournit le style pour l'interface du « Gestionnaire de modèles d'e-mail », y compris les formulaires de création/édition de modèles, les boutons et potentiellement les vues de liste.
    *   **Sélecteurs de classe CSS clés :** Les développeurs peuvent inspecter la sortie HTML du module dans le back-office pour identifier des classes spécifiques (par exemple, `.email-template-form`, `.template-list-item`) à surcharger dans leurs thèmes d'administration personnalisés ou via `override.css`.
-   **`sendvouchers/lib/voucherengine/ps16.css`**

    *   **Portée :** Style du formulaire d'administration du back-office, spécifiquement pour la compatibilité PrestaShop 1.6.
    *   **Responsabilité :** Fournit le style pour la section « Moteur de bons de réduction », y compris potentiellement les mises en page des formulaires, les champs de saisie et les boutons, avec des ajustements pour s'adapter au thème du back-office de PrestaShop 1.6. Ce fichier peut également être chargé sur les versions plus récentes de PS pour la rétrocompatibilité, mais son objectif principal est pour PS 1.6.
    *   **Sélecteurs de classe CSS clés :** Similaire à `emailTemplatesManager.css`, les développeurs doivent inspecter le HTML généré pour des sélecteurs spécifiques à cibler pour les surcharges.

### 4.6 Structure des templates Smarty (`views/templates/`)

Tous les templates sont situés dans le répertoire `sendvouchers/lib/emailTemplatesManager/views/`, indiquant qu'ils sont principalement utilisés pour le rendu de l'interface du back-office du gestionnaire de templates d'e-mail.

-   **`sendvouchers/lib/emailTemplatesManager/views/buttonManager.tpl`**

    *   **Portée :** Template d'administration.
    *   **Objectif :** Rend probablement les boutons ou les contrôles liés à la gestion des templates d'e-mail (par exemple, « Ajouter un nouveau template », « Gérer les templates »).
-   **`sendvouchers/lib/emailTemplatesManager/views/createTemplateForm.tpl`**

    *   **Portée :** Template d'administration.
    *   **Objectif :** Rend le formulaire HTML pour créer un nouveau template d'e-mail, y compris les champs pour l'objet, le corps et potentiellement la sélection de la langue.
-   **`sendvouchers/lib/emailTemplatesManager/views/editTemplateForm.tpl`**

    *   **Portée :** Template d'administration.
    *   **Objectif :** Rend le formulaire HTML pour modifier un template d'e-mail existant, pré-remplissant les champs avec les données du template actuel.
-   **`sendvouchers/lib/emailTemplatesManager/views/mainForm.tpl`**

    *   **Portée :** Template d'administration.
    *   **Objectif :** Il s'agit probablement du template d'enveloppe principal pour la section « Gestionnaire de templates d'e-mail », orchestrant l'affichage de la liste des templates, du formulaire de création et du formulaire d'édition.
-   **`sendvouchers/lib/emailTemplatesManager/views/selectInput.tpl`**

    *   **Portée :** Template d'administration.
    *   **Objectif :** Un extrait de template réutilisable pour rendre un champ de saisie HTML `<select>`, éventuellement pour la sélection de la langue ou le choix d'un template existant.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** :

    *   Le module ne crée pas explicitement de tables SQL personnalisées lors de l'`install()`.
    *   Il stocke ses paramètres de configuration (comme `sendvouchersTemplate`, `sendvouchersTitle`) dans la table `ps_configuration` de PrestaShop.
    *   Il interagit avec les tables principales `ps_cart_rule` et `ps_cart_rule_lang` de PrestaShop lors de la création et de la gestion des bons de réduction.
-   **Table des hooks enregistrés** :
    La fonctionnalité principale du module est exécutée via sa méthode `getContent()` dans le back-office. Bien que la description du module mentionne « Hooks Front-Office : En-tête, Colonnes, Produit ou Pied de page », l'inventaire du code fourni ne montre pas de fichiers de template correspondants ou de méthodes `hook` explicites dans `sendvouchers.php` qui rendraient du contenu dans ces hooks de front-office. Cela suggère que si des hooks de front-office sont enregistrés, ils sont soit pour un traitement interne (par exemple, `actionFrontControllerSetMedia` pour le chargement des actifs), soit des vestiges de versions précédentes et ne sont pas activement utilisés pour afficher du contenu visuel.

    La fonctionnalité principale d'envoi d'e-mails avec des bons de réduction est déclenchée par l'action de l'utilisateur dans le back-office, et non par le chargement des pages du front-office.

| Nom du Hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayBackOfficeHeader` | À chaque chargement de page du back-office. | Potentiellement utilisé pour charger le CSS/JS spécifique au module pour sa page de configuration. |
| `moduleRoutes` | Lors de l'initialisation du routage d'URL. | (Si implémenté) Pour définir des URL conviviales personnalisées pour les pages du module. (Non explicitement détecté dans ce module). |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration est chargé. | Pour ajouter des fichiers JavaScript et CSS spécifiques au module à la page de configuration du back-office. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour télécharger les dernières versions du module « Envoyer un e-mail avec un bon de réduction », veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
