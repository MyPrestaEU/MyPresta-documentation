---
title: "Exporter les clients avec adresse - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Exporter les clients avec adresse' par MyPresta.eu."
sidebar:
  label: "Exporter les clients avec adresse - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Export Customers with address sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/export-customers-with-address.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/export-customers-with-address/)
>
> ---


# Exporter les clients avec adresse

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes pour les modules PrestaShop. Aucune exigence d'hébergement particulière au-delà d'un environnement PrestaShop standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » sur le module vous mènera à sa page de configuration principale. Cet écran gère principalement les paramètres internes du module liés aux mises à jour.

-   **Ce que fait ce paramètre :** Cette section gère généralement les vérifications de mise à jour internes du module et les informations de version. Ces paramètres sont généralement destinés à l'utilisation interne du module pour s'assurer que vous utilisez la dernière version et pour fournir des notifications de mise à jour.
-   **Effet de la modification de ce paramètre :**
    -   *`mypresta_updates`* : Il s'agit probablement d'un indicateur interne pour activer ou désactiver les vérifications de mise à jour de MyPresta.eu.
    -   *`update_`* : Cela pourrait stocker la dernière fois qu'une vérification de mise à jour a été effectuée.
    -   *`updatev_`* : Cela pourrait stocker la dernière version disponible détectée.
-   **Valeur recommandée :** Il est généralement recommandé de laisser ces paramètres à leurs valeurs par défaut pour vous assurer de recevoir les notifications de mise à jour importantes.
-   **Scénario / exemple de marchand :** Vous n'interagissez généralement pas directement avec ces paramètres. Ils fonctionnent en arrière-plan pour vous informer si une nouvelle version du module est disponible, vous assurant ainsi d'avoir accès aux dernières fonctionnalités et corrections de bugs.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 Exporter les clients avec adresse (Back Office > Paramètres avancés > Exporter les clients avec adresse)

C'est l'écran principal où vous effectuerez l'exportation des clients. Vous pouvez le trouver sous le menu « Paramètres avancés » dans votre back office PrestaShop.

-   **Nom de l'écran et emplacement du menu :** **Paramètres avancés > Exporter les clients avec adresse**
-   **Actions et paramètres disponibles :**
    -   Lorsque vous naviguez vers cet écran, vous verrez un bouton ou un lien pour lancer le processus d'exportation. Le module prépare automatiquement un fichier CSV contenant toutes les données clients et leurs adresses associées.
    -   Le fichier exporté inclura les colonnes suivantes, formatées pour l'outil d'importation de PrestaShop :
        -   **ID client** : Identifiant unique pour le client.
        -   **Actif (0/1)** : Indique si le compte client est actif (1) ou inactif (0).
        -   **ID des titres (M. = 1, Mme = 2, autre = 0)** : L'ID correspondant au titre du client (par exemple, M., Mme).
        -   \*\*Email \*\*\*: L'adresse e-mail du client (obligatoire).
        -   \*\*Mot de passe \*\*\*: Le mot de passe du client (obligatoire, généralement haché).
        -   **Date de naissance (aaaa-mm-jj)** : La date de naissance du client.
        -   \*\*Nom de famille \*\*\*: Le nom de famille du client (obligatoire).
        -   \*\*Prénom \*\*\*: Le prénom du client (obligatoire).
        -   **Newsletter (0/1)** : Indique si le client est abonné à la newsletter (1) ou non (0).
        -   **Opt-in (0/1)** : Indique si le client a opté pour les offres partenaires (1) ou non (0).
        -   **Date d'inscription** : La date à laquelle le client a enregistré son compte.
        -   **Groupes (x,y,z…)** : Une liste d'ID de groupes de clients séparés par des virgules auxquels le client appartient.
        -   **ID du groupe par défaut** : L'ID du groupe par défaut du client.
        -   **ID / Nom de la boutique** : L'ID ou le nom de la boutique à laquelle le client est associé (utile dans les environnements multi-boutiques).
        -   **ID d'adresse** : Identifiant unique pour l'adresse du client.
        -   \*\*Alias \*\*\*: Un alias pour l'adresse (par exemple, « Mon adresse personnelle »).
        -   \*\*Email du client \*\*\*: L'e-mail associé à cette adresse (doit correspondre à l'e-mail du client).
        -   **Fabricant** : (Si applicable)
        -   **Fournisseur** : (Si applicable)
        -   **Société** : Le nom de la société associé à l'adresse.
        -   … et d'autres champs d'adresse standard comme `Adresse1`, `Adresse2`, `Code postal`, `Ville`, `Pays`, `Téléphone`, `Téléphone portable`, `Numéro de TVA`, etc.
-   **Effet des modifications :** Cliquer sur le bouton d'exportation générera et téléchargera un fichier CSV sur votre ordinateur. Cette action ne modifie aucune donnée dans votre boutique PrestaShop ; elle ne fait que les extraire.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  **Sauvegardes régulières :** Exportez périodiquement vos données clients en tant que sauvegarde, en particulier avant les mises à jour majeures de la boutique ou les migrations.
    2.  **Génération de listes marketing :** Exportez les données clients pour créer des listes pour les campagnes de marketing par e-mail, en segmentant par groupes ou dates d'inscription.
    3.  **Mises à jour CRM :** Si vous utilisez un CRM externe, exportez les données pour les maintenir synchronisées avec votre base de clients PrestaShop.

#### 2.2.2 AdminExportCustomersController (index.php)

Ce fichier sert probablement de point d'entrée ou d'aide pour le `AdminExportCustomersController`, garantissant que l'interface administrative du module fonctionne correctement dans le back office de PrestaShop. Il ne présente pas d'écran configurable séparé, mais facilite plutôt l'affichage et la fonctionnalité de l'écran d'exportation principal.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | `mypresta_updates` | Activé | Indicateur interne pour les vérifications de mise à jour MyPresta.eu. Garder activé pour les notifications. |
| Page de configuration du module | `update_` | (Interne) | Stocke l'horodatage de la dernière vérification de mise à jour. |
| Page de configuration du module | `updatev_` | (Interne) | Stocke la dernière version de module disponible. |
| Paramètres avancés > Exporter les clients avec adresse | Bouton Exporter | N/A | Lance le téléchargement d'un fichier CSV contenant toutes les données clients et adresses. |
| Paramètres avancés > Exporter les clients avec adresse | Colonnes CSV exportées | N/A | Inclut l'ID client, Actif, ID des titres, Email, Mot de passe, Date de naissance, Nom de famille, Prénom, Newsletter, Opt-in, Date d'inscription, Groupes, ID du groupe par défaut, ID/Nom de la boutique, ID d'adresse, Alias, Email du client, Société et tous les champs d'adresse standard. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai cliqué sur le bouton d'exportation, mais rien ne s'est passé ou le fichier est vide.**
**R1 :**

-   **Vérifiez les bloqueurs de fenêtres contextuelles du navigateur :** Votre navigateur pourrait bloquer le téléchargement du fichier. Recherchez une notification ou une icône dans la barre d'adresse de votre navigateur et autorisez les téléchargements depuis votre administration PrestaShop.
-   **Permissions du module :** Assurez-vous que le module dispose des permissions de système de fichiers nécessaires pour créer et servir le fichier CSV. Bien que rare, des permissions incorrectes peuvent empêcher la génération du fichier.
-   **Limites de mémoire du serveur :** Si vous avez un très grand nombre de clients, le processus d'exportation pourrait atteindre les limites de mémoire PHP sur votre serveur. Vérifiez les journaux d'erreurs PHP de votre serveur (souvent trouvés dans `var/logs` ou votre panneau de contrôle d'hébergement) pour les erreurs liées à la mémoire. Vous devrez peut-être augmenter temporairement `memory_limit` dans votre fichier `php.ini`.
-   **Base de données clients vide :** Vérifiez que vous avez bien des clients enregistrés dans votre boutique.

**Q2 : Le fichier CSV exporté semble illisible ou contient des caractères étranges.**
**R2 :** Il s'agit souvent d'un problème d'encodage.

-   **Ouvrir avec le bon encodage :** Lorsque vous ouvrez le fichier CSV dans un tableur (comme Excel), assurez-vous de sélectionner **UTF-8** comme origine du fichier ou encodage. La plupart des systèmes modernes utilisent l'UTF-8, et les exportations PrestaShop sont généralement dans ce format.
-   **Vérifiez les paramètres de langue de PrestaShop :** Assurez-vous que la langue par défaut et le jeu de caractères de votre boutique PrestaShop sont correctement configurés dans **International > Localisation**.

**Q3 : Puis-je choisir les champs à exporter ?**
**R3 :** Ce module exporte un ensemble prédéfini de champs client et d'adresse compatibles avec l'outil d'importation natif de PrestaShop. Il n'offre pas d'options pour sélectionner ou désélectionner des champs individuels. Si vous avez besoin d'une exportation hautement personnalisée, vous pourriez avoir besoin d'un module d'exportation plus avancé ou d'un développement personnalisé.

**Q4 : L'exportation des clients affectera-t-elle les performances de ma boutique ?**
**R4 :** Pour la plupart des boutiques, une exportation unique aura un impact négligeable. Pour les boutiques avec des centaines de milliers de clients, le processus d'exportation peut prendre quelques instants et consommer des ressources serveur. Il est généralement recommandé d'effectuer de grandes exportations pendant les heures creuses si vous anticipez un temps de traitement très long. Le module est conçu pour être efficace, mais les ressources serveur sont toujours un facteur.

**Q5 : Je souhaite réimporter les clients après avoir effectué des modifications. Comment faire ?**
**R5 :** Ce module ne gère que l'exportation. Pour réimporter, vous utiliseriez l'outil d'importation natif de PrestaShop :

1.  Allez dans **Paramètres avancés > Importer**.
2.  Sélectionnez « Clients » ou « Adresses » comme entité à importer.
3.  Téléchargez votre fichier CSV modifié.
4.  Mappez soigneusement les colonnes de votre CSV aux champs de la base de données PrestaShop.

Testez toujours les importations sur un environnement de développement ou de staging en premier, et assurez-vous d'avoir une sauvegarde complète de la base de données avant d'effectuer toute importation à grande échelle sur votre boutique en ligne. Des importations incorrectes peuvent entraîner une perte ou une corruption de données.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Exporter les clients avec adresse » (`exportcustomers`) est un module PrestaShop simple, principalement axé sur les fonctionnalités du back-office. Il suit un modèle MVC PrestaShop standard pour son interface administrative. La logique principale réside dans le fichier principal du module et un contrôleur d'administration dédié. Il n'introduit pas de nouvelles tables de base de données, mais utilise les structures `ObjectModel` `Customer` et `Address` existantes de PrestaShop pour récupérer et formater les données pour l'exportation. La simplicité du module signifie qu'il n'a pas de composants front-office, de classes personnalisées ou d'actifs JavaScript/CSS complexes.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Aucun. Ce module n'a aucune fonctionnalité front-office.
-   **Contrôleurs Admin Back-Office** :

    -   `exportcustomers/controllers/admin/AdminExportCustomers.php`
        -   **Nom de la classe et classe parente** : `AdminExportCustomersController` étendant `ModuleAdminController`.
        -   **Responsabilité** : C'est le contrôleur principal responsable de la logique d'exportation des clients et des adresses. Lorsqu'il est accédé via le menu du back-office de PrestaShop, il lance le processus de récupération des données clients et adresses de la base de données, les formate en une chaîne CSV et les envoie sous forme de fichier téléchargeable au navigateur. Il construit la ligne d'en-tête CSV avec tous les champs spécifiés (ID client, Email, ID d'adresse, Alias, etc.), puis itère sur les objets `Customer` et `Address` pour remplir les lignes de données.
    -   `exportcustomers/controllers/admin/index.php`
        -   **Responsabilité** : Il s'agit d'un fichier de substitution courant dans les répertoires des contrôleurs d'administration de modules PrestaShop. Il contient généralement une simple `header('Location: ../../index.php?controller=AdminHome')` ou une redirection similaire pour empêcher la liste directe des répertoires ou l'accès, assurant la sécurité et le routage approprié au sein du back-office de PrestaShop. Il ne contient aucune logique fonctionnelle pour le module lui-même.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module n'introduit aucune classe ou modèle personnalisé dans le répertoire `classes/`. Il utilise directement les classes `ObjectModel` `Customer` et `Address` de PrestaShop pour récupérer les données de la base de données.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé. Le processus d'exportation est généralement initié par une simple soumission de formulaire ou un lien direct, entièrement géré par le contrôleur PHP.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé. Son interface back-office repose entièrement sur le style par défaut du back-office de PrestaShop.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Ce module n'inclut aucun fichier de modèle Smarty personnalisé. Le `AdminExportCustomersController` rend probablement une vue très simple, éventuellement juste un bouton ou un message, directement dans sa méthode `renderForm()` ou `initContent()`, ou il déclenche directement un téléchargement de fichier sans rendre un modèle complexe.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** : Ce module ne crée aucune table de base de données personnalisée. Il lit les données des tables PrestaShop existantes, principalement `ps_customer` et `ps_address`.

    -   `ps_configuration` : Le module stocke ses paramètres de configuration internes (`mypresta_updates`, `update_`, `updatev_`) dans la table `ps_configuration`.
-   **Table des hooks enregistrés** :
    Ce module n'enregistre aucun hook front-office. Sa fonctionnalité est entièrement confinée au back-office.
    Il utilise probablement le hook `actionAdminControllerSetMedia` (implicitement ou explicitement) pour son contrôleur d'administration, et potentiellement `displayAdminProductsExtra` ou similaire pour son élément de menu du back-office.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Exécuté lors de l'initialisation d'un contrôleur d'administration. | Utilisé par `ModuleAdminController` pour ajouter des actifs CSS/JS (bien que ce module n'en ait pas). |
| `displayAdminAdvancedParameters` | Rend le contenu dans la section « Paramètres avancés » du back-office. | Probablement utilisé pour ajouter le lien/point d'entrée du module au menu « Paramètres avancés ». |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et les dernières versions du module « Exporter les clients avec adresse », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité et la compatibilité du module.
