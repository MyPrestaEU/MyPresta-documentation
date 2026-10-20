---
title: "Pièces jointes aux e-mails - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Pièces jointes aux e-mails par MyPresta.eu."
sidebar:
  label: "Pièces jointes aux e-mails - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Email attachments sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/email-attachments.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/email-attachments/)
>
> ---


# Pièces jointes aux e-mails

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur inhabituelle n'est requise.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

Le module « Pièces jointes aux e-mails » offre un processus de configuration simple, principalement via un écran d'administration dédié où vous gérez vos pièces jointes et les liez à des modèles d'e-mails spécifiques.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Lorsque vous cliquez pour la première fois sur « Configurer » après l'installation, vous serez dirigé vers la page de configuration principale du module. Cette page sert principalement de point d'entrée et peut contenir des informations générales ou un lien vers l'écran de gestion des pièces jointes dédié.

-   **Ce que fait cet écran :** Cet écran initial fournit un bref aperçu du module et vous dirige généralement vers l'interface principale pour la gestion des pièces jointes aux e-mails. Il pourrait également contenir des paramètres généraux si le module en avait, mais pour ce module, la fonctionnalité principale est gérée dans un contrôleur d'administration distinct.
-   **Effet de la modification des paramètres :** Tout paramètre ici affecterait le comportement général du module. Cependant, pour « Pièces jointes aux e-mails », l'action principale est de naviguer vers la page de gestion dédiée « Pièces jointes aux e-mails ».
-   **Valeur recommandée :** Suivez les instructions à l'écran, qui impliqueront généralement de cliquer sur un bouton ou un lien pour passer à la zone de gestion des pièces jointes.

### 2.2 Écran d'administration dédié : Pièces jointes aux e-mails (Back Office > Modules > Pièces jointes aux e-mails)

C'est le centre principal pour la gestion de toutes vos pièces jointes aux e-mails. Vous trouverez généralement un nouvel élément de menu sous **Modules** ou **Paramètres de la boutique** (selon votre version de PrestaShop et la conception du module) nommé « Pièces jointes aux e-mails » ou similaire.

**Emplacement du menu :** Back Office > Modules > Pièces jointes aux e-mails (ou similaire, vérifiez votre menu d'administration après l'installation)

#### Aperçu de l'écran de gestion des « Pièces jointes aux e-mails »

Cet écran présentera une liste (une « grille » ou un « tableau ») de toutes les pièces jointes aux e-mails que vous avez configurées. À partir de là, vous pouvez :

-   **Ajouter une nouvelle pièce jointe :** Créer une nouvelle règle de pièce jointe.
-   **Modifier une pièce jointe existante :** Modifier les paramètres d'une pièce jointe que vous avez déjà créée.
-   **Supprimer une pièce jointe :** Supprimer une règle de pièce jointe.

#### Ajout/Modification d'une pièce jointe à un e-mail

Lorsque vous cliquez sur « Ajouter une nouvelle pièce jointe » ou « Modifier » une pièce jointe existante, un formulaire vous sera présenté pour définir les propriétés de la pièce jointe.

**Champs et options du formulaire :**

1.  **Nom de la pièce jointe :**

    -   **Ce que fait ce paramètre :** C'est un nom interne pour votre référence dans le Back Office. Il vous aide à identifier facilement la règle de pièce jointe.
    -   **Effet de la modification de ce paramètre :** Ne modifie que l'étiquette que vous voyez dans la liste d'administration. Cela n'affecte pas le nom du fichier vu par le client.
    -   **Valeur recommandée :** Un nom descriptif, par exemple, « Guide de bienvenue PDF », « CGV confirmation de commande », « Manuel produit pour nouvelles commandes ».
    -   **Scénario marchand :** Vous avez plusieurs pièces jointes à des fins différentes ; un nom clair vous aide à les distinguer.
2.  **Sélectionner le(s) modèle(s) d'e-mail :**

    -   **Ce que fait ce paramètre :** Ce paramètre crucial détermine *à quel(s)* e-mail(s) PrestaShop cette pièce jointe sera ajoutée. Vous verrez généralement une liste de tous les modèles d'e-mails PrestaShop standard (par exemple, `account`, `order_conf`, `shipped`, `contact_form`). Vous pouvez sélectionner un ou plusieurs modèles.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque sélectionné :* La pièce jointe sera incluse dans chaque e-mail envoyé à l'aide du (des) modèle(s) choisi(s).
        -   *Lorsque non sélectionné :* La pièce jointe ne sera pas incluse dans les e-mails utilisant ce modèle.
    -   **Valeur recommandée :** Sélectionnez uniquement les modèles d'e-mails pertinents. Par exemple, un « Guide de bienvenue » ne doit être joint qu'à l'e-mail `account` (création de compte client).
    -   **Scénario marchand :** Vous souhaitez joindre un PDF de « Politique de retour » aux e-mails `order_conf` (confirmation de commande) et `shipped` (notification d'expédition).
3.  **Type de pièce jointe :**

    -   **Ce que fait ce paramètre :** Cela définit la source de votre fichier de pièce jointe. Le module offre différentes options :
        -   **Télécharger un fichier :** Joindre un fichier existant depuis votre ordinateur.
        -   **Générer un PDF à partir d'une page CMS :** Créer un PDF à partir de l'une de vos pages CMS PrestaShop existantes.
        -   **Créer un PDF à partir de l'éditeur de texte enrichi :** Concevoir du contenu PDF personnalisé directement dans le module à l'aide d'un éditeur visuel.
    -   **Effet de la modification de ce paramètre :** Détermine l'ensemble d'options suivant que vous verrez pour spécifier le contenu de la pièce jointe.
    -   **Valeur recommandée :** Choisissez le type qui correspond le mieux à votre source de contenu.
    -   **Scénario marchand :** Vous avez un « Garantie.pdf » pré-fait (Télécharger un fichier), ou vous souhaitez convertir votre page CMS « À propos de nous » en PDF (Générer un PDF à partir d'une page CMS), ou vous devez rédiger un PDF « Offre spéciale » personnalisé (Créer un PDF à partir de l'éditeur de texte enrichi).

    **Sous-paramètres basés sur le type de pièce jointe :**

    -   **Si « Télécharger un fichier » est sélectionné :**

        -   **Champ de téléchargement de fichier :**
            -   **Ce que fait ce paramètre :** Vous permet de parcourir votre ordinateur et de télécharger un fichier (par exemple, PDF, JPG, DOCX).
            -   **Effet de la modification de ce paramètre :** Le fichier sélectionné sera stocké sur votre serveur et utilisé comme pièce jointe.
            -   **Valeur recommandée :** Téléchargez un fichier qui n'est pas excessivement volumineux pour éviter les problèmes de livraison d'e-mails. Les PDF sont généralement préférés pour les documents.
            -   **Scénario marchand :** Joindre le PDF des « Conditions générales » de votre entreprise.
    -   **Si « Générer un PDF à partir d'une page CMS » est sélectionné :**

        -   **Sélectionner la page CMS :**
            -   **Ce que fait ce paramètre :** Fournit une liste déroulante de toutes vos pages CMS PrestaShop actives.
            -   **Effet de la modification de ce paramètre :** Le contenu de la page CMS choisie sera converti en PDF et joint.
            -   **Valeur recommandée :** Sélectionnez une page CMS avec un contenu adapté à un document PDF (par exemple, « À propos de nous », « Politique de confidentialité »).
            -   **Scénario marchand :** Joindre automatiquement votre page CMS « Politique de retour » en tant que PDF aux e-mails pertinents.
    -   **Si « Créer un PDF à partir de l'éditeur de texte enrichi » est sélectionné :**

        -   **Éditeur de texte enrichi (WYSIWYG) :**
            -   **Ce que fait ce paramètre :** Un éditeur visuel où vous pouvez taper et formater du contenu personnalisé, ajouter des images, des liens, etc. Ce contenu sera ensuite converti en PDF.
            -   **Effet de la modification de ce paramètre :** Le contenu que vous créez ici formera le corps du PDF joint.
            -   **Valeur recommandée :** Utilisez ceci pour du contenu dynamique ou unique qui n'existe pas en tant que fichier ou page CMS. Gardez la conception simple pour de meilleurs résultats de conversion PDF.
            -   **Scénario marchand :** Créer un message de « Remerciement » personnalisé avec un code de réduction en tant que pièce jointe PDF.
4.  **Nom du fichier de la pièce jointe (tel que vu par le client) :**

    -   **Ce que fait ce paramètre :** C'est le nom du fichier que le client verra dans son client de messagerie lorsqu'il recevra la pièce jointe.
    -   **Effet de la modification de ce paramètre :** Modifie la façon dont le fichier apparaît dans la boîte de réception du client.
    -   **Valeur recommandée :** Un nom de fichier clair, descriptif et professionnel (par exemple, `Votre-Confirmation-de-Commande.pdf`, `Informations-de-Garantie.pdf`). Incluez l'extension du fichier (par exemple, `.pdf`).
    -   **Scénario marchand :** Vous avez téléchargé `mon_doc_interne_v2.pdf`, mais vous voulez que le client voie `Guide-Produit.pdf`.
5.  **Actif :**

    -   **Ce que fait ce paramètre :** Un simple interrupteur ON/OFF pour activer ou désactiver cette règle de pièce jointe spécifique.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque activé :* La règle de pièce jointe est active et sera appliquée aux e-mails sélectionnés.
        -   *Lorsque désactivé :* La règle de pièce jointe est inactive et n'ajoutera pas de fichiers aux e-mails.
    -   **Valeur recommandée :** Réglez sur « OUI » lorsque vous souhaitez que la pièce jointe soit envoyée.
    -   **Scénario marchand :** Vous testez une pièce jointe et souhaitez la désactiver temporairement sans supprimer la configuration.

#### 2.2.1 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Pièces jointes aux e-mails (Contrôleur Admin)** | Nom de la pièce jointe | Texte descriptif | Étiquette interne pour une identification facile dans le BO. |
| | Sélectionner le(s) modèle(s) d'e-mail | Modèles spécifiques (par exemple, `order_conf`) | Détermine quels e-mails reçoivent la pièce jointe. |
| | Type de pièce jointe | Varie (Télécharger un fichier, Page CMS, Texte enrichi) | Définit la source du contenu de la pièce jointe. |
| | *Si Télécharger un fichier :* Champ de téléchargement de fichier | N/A | Télécharge un fichier existant depuis votre ordinateur. |
| | *Si Générer un PDF à partir d'une page CMS :* Sélectionner la page CMS | Page CMS spécifique | Convertit le contenu de la page CMS choisie en PDF. |
| | *Si Créer un PDF à partir de l'éditeur de texte enrichi :* Éditeur de texte enrichi | Contenu personnalisé | Crée un PDF à partir du contenu saisi dans l'éditeur. |
| | Nom du fichier de la pièce jointe | Nom de fichier descriptif (par exemple, `document.pdf`) | Le nom que les clients voient dans leur client de messagerie. |
| | Actif | OUI | Active/désactive la règle de pièce jointe. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Mes pièces jointes ne sont pas envoyées, ou les clients signalent ne pas les recevoir.**

-   **R :** Tout d'abord, vérifiez si la règle de pièce jointe est « Active » dans la configuration du module.
-   **R :** Assurez-vous d'avoir sélectionné le(s) bon(s) modèle(s) d'e-mail pour la pièce jointe. Testez en déclenchant vous-même l'un de ces e-mails (par exemple, passez une commande test, créez un nouveau compte client).
-   **R :** Vérifiez vos paramètres d'e-mail PrestaShop (Paramètres de la boutique > E-mail) pour vous assurer que les e-mails sont envoyés correctement en général. Essayez d'envoyer un e-mail test depuis PrestaShop.
-   **R :** Le fichier de la pièce jointe pourrait être trop volumineux, ce qui entraînerait le rejet de l'e-mail par les fournisseurs de messagerie. Essayez une taille de fichier plus petite.
-   **R :** Videz votre cache PrestaShop (Paramètres avancés > Performances > Vider le cache).

**Q2 : Le PDF généré à partir de ma page CMS semble étrange ou présente des problèmes de formatage.**

-   **R :** La génération de PDF à partir de HTML peut parfois être délicate. Assurez-vous que le contenu de votre page CMS est un HTML propre sans JavaScript complexe ou éléments très dynamiques.
-   **R :** Essayez de simplifier la mise en page de votre page CMS. Évitez les CSS trop complexes ou les images très larges qui pourraient ne pas bien s'adapter à une page PDF standard.
-   **R :** Si les problèmes persistent, envisagez de créer un fichier PDF dédié en externe et d'utiliser l'option « Télécharger un fichier ».

**Q3 : Puis-je joindre des fichiers différents en fonction du produit commandé ou du groupe de clients ?**

-   **R :** Ce module, dans sa configuration standard, joint des fichiers à *tous* les e-mails d'un type sélectionné, indépendamment du produit spécifique ou du groupe de clients. Pour des pièces jointes conditionnelles plus avancées, un développement personnalisé ou un module plus spécialisé pourrait être nécessaire.

**Q4 : Comment traduire le contenu d'un PDF créé avec l'éditeur de texte enrichi pour différentes langues ?**

-   **R :** Lorsque vous utilisez l'éditeur de texte enrichi, vous devriez voir des onglets de langue (par exemple, Anglais, Français, Espagnol) si votre boutique PrestaShop prend en charge plusieurs langues. Vous devrez saisir et formater le contenu pour chaque langue séparément dans l'éditeur. Le module joindra ensuite la version linguistique correcte en fonction de la langue sélectionnée par le client.

**Q5 : Où sont stockés les fichiers téléchargés sur mon serveur ?**

-   **R :** Les fichiers téléchargés sont généralement stockés dans le répertoire du module ou un dossier de téléchargement désigné dans le module. Vous n'avez généralement pas besoin d'interagir directement avec ces fichiers via FTP, car le module les gère.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module « Pièces jointes aux e-mails ».

### 4.1 Aperçu de l'architecture

Le module « Pièces jointes aux e-mails » (`mattach`) étend la fonctionnalité d'e-mail de base de PrestaShop en surchargeant la classe `Mail`. Cela lui permet d'injecter des pièces jointes personnalisées dans les e-mails sortants sans modifier directement les fichiers du cœur. Il suit un modèle MVC PrestaShop standard pour son interface de gestion Back Office, utilisant un `AdminController` pour gérer les entités `mailfile` qui représentent les configurations de pièces jointes. La génération de PDF est gérée en interne, soit en convertissant le contenu CMS, soit l'entrée de l'éditeur de texte enrichi.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    -   Ce module ne contient **aucun** contrôleur front-office dédié. Toutes ses opérations sont effectuées dans le Back Office ou en surchargeant les classes du cœur lors de l'envoi d'e-mails.
-   **Contrôleurs Admin Back-Office** :

    -   `mattach/controllers/admin/AdminMailAttachments.php`

        -   **Nom de la classe** : `AdminMailAttachmentsController`
        -   **Classe parente** : `ModuleAdminController`
        -   **Responsabilité** : C'est le contrôleur principal pour la gestion des règles de pièces jointes aux e-mails. Il gère les opérations CRUD (Créer, Lire, Mettre à jour, Supprimer) pour l'entité `mailfile`. Il affiche une liste des pièces jointes configurées, fournit des formulaires pour les ajouter/modifier, et gère les téléchargements de fichiers, la sélection de pages CMS et le contenu de l'éditeur de texte enrichi pour la génération de PDF. Il utilise `HelperList` de PrestaShop pour la vue en grille et `HelperForm` pour les formulaires d'ajout/modification.
        -   **Table / Entité gérée** : `mailfile` (table personnalisée pour les données du module).
        -   **Clés de configuration associées** : `PS_LANG_DEFAULT` (utilisé pour les champs multilingues).
    -   `mattach/controllers/admin/index.php`

        -   **Nom de la classe** : (Pas de classe explicite, généralement un espace réservé ou une redirection)
        -   **Responsabilité** : Ce fichier est souvent une mesure de sécurité (pour empêcher la liste directe des répertoires) ou une simple redirection dans la structure d'administration de PrestaShop. Il ne contient pas de logique de contrôleur active pour la fonctionnalité du module.

### 4.3 Classes et modèles du cœur (`classes/`)

-   `mattach/override/classes/index.php`

    -   **Responsabilité** : Fichier de sécurité PrestaShop standard pour empêcher la liste des répertoires.
-   `mattach/override/classes/Mail.php`

    -   **Nom de la classe** : `Mail` (surcharge la classe `Mail` du cœur de PrestaShop)
    -   **Classe parente** : `MailCore`
    -   **Responsabilité** : C'est la partie la plus critique de la fonctionnalité du module. En surchargeant la classe `Mail`, le module intercepte la méthode `send()`. Dans la méthode `send()` surchargée, il vérifie si des règles de pièces jointes sont configurées pour le modèle d'e-mail spécifique en cours d'envoi. Si des correspondances sont trouvées, il récupère les données de la pièce jointe (chemin du fichier téléchargé, contenu PDF généré), crée les objets `Swift_Attachment` nécessaires et les ajoute à l'e-mail avant qu'il ne soit envoyé. Cela garantit que les pièces jointes sont incluses de manière transparente dans tous les e-mails sortants pertinents.
    -   **Interaction avec la base de données** : Interagit avec la table personnalisée `mailfile` du module pour récupérer les configurations de pièces jointes.
    -   **Méthodes publiques clés** : Surcharge `send()` pour injecter la logique de pièce jointe.

### 4.4 Actifs JavaScript (`views/js/`)

-   `mattach/views/templates/admin/js/mattach.js`
    -   **Portée** : Back-office (AdminMailAttachmentsController).
    -   **Fonctionnalité** : Ce script gère probablement le comportement dynamique du formulaire de configuration des pièces jointes. Cela pourrait inclure :
        -   Afficher/masquer des champs de saisie spécifiques en fonction du « Type de pièce jointe » sélectionné (par exemple, afficher le champ de téléchargement de fichier uniquement lorsque « Télécharger un fichier » est choisi).
        -   Appels AJAX pour récupérer des listes de pages CMS ou d'autres données dynamiques.
        -   Initialisation de l'éditeur de texte enrichi (par exemple, TinyMCE ou CKEditor) pour l'option « Créer un PDF à partir de l'éditeur de texte enrichi ».
        -   Validation côté client ou améliorations de l'interface utilisateur pour l'interface de gestion des pièces jointes.

### 4.5 Feuilles de style CSS (`views/css/`)

-   Ce module ne semble **pas** contenir de fichiers CSS personnalisés dans l'inventaire fourni. Il s'appuie probablement sur le style par défaut du Back Office de PrestaShop pour ses formulaires et listes de configuration.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** :

    -   Ce module ne contient **aucun** modèle de hook spécifique dans l'inventaire fourni. Son impact sur le front-office se fait uniquement par le biais des pièces jointes aux e-mails, et non par des éléments visuels.
-   **Modèles d'administration (`views/templates/admin/`)** :

    -   `mattach/views/templates/admin/orderstates.tpl`
        -   **Objectif** : Le nom de ce modèle suggère qu'il pourrait être utilisé pour afficher ou gérer les statuts de commande en relation avec les pièces jointes, ou peut-être pour sélectionner des statuts de commande pour des pièces jointes conditionnelles (bien que la description du module ne mentionne pas explicitement cette fonctionnalité avancée). Il pourrait faire partie du formulaire `AdminMailAttachmentsController`, potentiellement pour sélectionner les changements de statut de commande qui déclenchent un e-mail avec une pièce jointe.
    -   `mattach/lib/searchTool/views/scripts.tpl`
        -   **Objectif** : Ce modèle contient probablement du JavaScript ou de la logique Smarty liée à un outil de recherche ou de filtrage utilisé dans l'interface d'administration, éventuellement pour rechercher des modèles d'e-mails ou des pages CMS. C'est un modèle utilitaire pour améliorer l'interface utilisateur d'administration.
-   **Modèles Front-office (`views/templates/front/`)** :

    -   Ce module ne contient **aucun** modèle front-office.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :

    -   `ps_mailfile` : C'est la table personnalisée principale créée par le module pour stocker chaque configuration de pièce jointe d'e-mail.
        -   `id_mailfile` : Clé primaire.
        -   `name` : Nom interne de la règle de pièce jointe.
        -   `file_name` : Nom réel du fichier (ou nom généré) de la pièce jointe.
        -   `file_path` : Chemin vers le fichier téléchargé ou où le PDF généré est temporairement stocké.
        -   `file_type` : Type de pièce jointe (par exemple, 'upload', 'cms', 'editor').
        -   `id_cms` : Si `file_type` est 'cms', stocke l'ID de la page CMS.
        -   `content` : Si `file_type` est 'editor', stocke le contenu de texte enrichi (multilingue).
        -   `mail_templates` : Un tableau sérialisé ou une chaîne de noms de modèles d'e-mails séparés par des virgules (par exemple, `account`, `order_conf`) auxquels cette pièce jointe s'applique.
        -   `active` : Booléen (0 ou 1) indiquant si la règle de pièce jointe est active.
    -   `ps_mailfile_lang` : Table complémentaire pour les champs multilingues comme `content` (si `file_type` est 'editor').
        -   `id_mailfile` : Clé étrangère vers `ps_mailfile`.
        -   `id_lang` : ID de la langue.
        -   `content` : Contenu de texte enrichi traduit.
-   **Table des hooks enregistrés** :

    -   Le module fonctionne principalement en surchargeant la classe `Mail` du cœur, ce qui est une méthode plus directe et puissante que de s'appuyer uniquement sur des hooks pour la modification des e-mails. Bien qu'il puisse enregistrer certains hooks standard pour l'installation/désinstallation du module ou l'intégration du menu du Back Office, sa logique d'injection de pièce jointe principale se trouve dans la surcharge de `Mail`.
    -   **Méthode `install()`** :
        -   Enregistre le module dans le menu du Back Office.
        -   Crée les tables de base de données `ps_mailfile` et `ps_mailfile_lang`.
        -   Installe la surcharge de la classe `Mail`.
    -   **Méthode `uninstall()`** :
        -   Supprime le module du menu du Back Office.
        -   Supprime les tables de base de données `ps_mailfile` et `ps_mailfile_lang`.
        -   Désinstalle la surcharge de la classe `Mail`.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Pièces jointes aux e-mails », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité et la configuration du module.
