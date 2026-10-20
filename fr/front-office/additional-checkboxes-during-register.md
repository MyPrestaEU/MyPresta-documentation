---
title: "Cases à cocher supplémentaires lors de l'inscription - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Cases à cocher supplémentaires lors de l'inscription' par MyPresta.eu."
sidebar:
  label: "Cases à cocher supplémentaires lors de l'inscription - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Additional checkboxes during register sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/additional-checkboxes-during-register.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/additional-checkboxes-during-register/)
>
> ---


# Cases à cocher supplémentaires lors de l'inscription

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises, qui sont généralement disponibles sur la plupart des environnements d'hébergement compatibles PrestaShop.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal du module, accessible en cliquant sur « Configurer » après l'installation.

-   **Ce que fait ce paramètre :** Cet écran gère principalement les paramètres généraux du module et vous permet de gérer les mises à jour.
-   **Effet de la modification de ce paramètre :**
    *   `mypresta_updates` : Il s'agit d'un paramètre général pour les modules MyPresta.eu afin de vérifier les mises à jour.
        *   *Lorsqu'il est activé :* Le module vérifiera périodiquement MyPresta.eu pour les nouvelles versions, vous informant dans le Back Office si une mise à jour est disponible. Cela vous aide à maintenir votre module sécurisé et à jour avec les dernières fonctionnalités et corrections de bugs.
        *   *Lorsqu'il est désactivé :* Le module ne vérifiera pas automatiquement les mises à jour. Vous devrez vérifier manuellement votre compte MyPresta.eu pour les nouvelles versions.
    *   `update_` : Ce paramètre est lié à la fonctionnalité de vérification des mises à jour.
    *   `updatev_` : Ce paramètre est lié à la fonctionnalité de vérification des mises à jour.
-   **Valeur recommandée :** Pour `mypresta_updates`, il est généralement **recommandé de le laisser activé** pour vous assurer d'être toujours informé des dernières versions du module. Les deux autres paramètres sont internes et doivent généralement être laissés tels quels.
-   **Scénario / exemple de marchand :** Vous voulez vous assurer que votre boutique utilise toujours la version la plus sécurisée et la plus riche en fonctionnalités du module. L'activation des vérifications de mise à jour signifie que vous serez averti directement dans votre administration PrestaShop lorsqu'une nouvelle version sera publiée, ce qui facilitera la mise à jour.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### AdminAddTosListController (Back Office > Modules > Cases à cocher supplémentaires > Liste des cases à cocher)

Cet écran est l'endroit où vous définissez et gérez toutes les cases à cocher individuelles qui apparaîtront lors de l'inscription du client.

-   **Nom de l'écran et emplacement du menu :** Vous pouvez trouver cet écran en naviguant vers **Modules > Cases à cocher supplémentaires > Liste des cases à cocher** dans le menu de votre Back Office PrestaShop.
-   **Actions et paramètres disponibles :**
    *   **Liste des cases à cocher :** Cette page affiche un tableau de toutes les cases à cocher personnalisées que vous avez créées. Chaque ligne indique le nom de la case à cocher, si elle est obligatoire, son statut (activée/désactivée) et sa position.
    *   **Ajouter une nouvelle case à cocher :** Il y aura un bouton (par exemple, « Ajouter une nouvelle case à cocher » ou une icône plus) pour créer une toute nouvelle case à cocher. Lors de l'ajout/modification d'une case à cocher, vous configurerez généralement :
        *   **Nom/Libellé :** Le texte qui apparaît à côté de la case à cocher (par exemple, « J'accepte la politique de confidentialité »). Il doit être clair et concis.
        *   **Lien (Facultatif) :** Une URL vers une page (par exemple, votre page de politique de confidentialité, une page de conditions spécifiques) sur laquelle les clients peuvent cliquer pour lire tous les détails. C'est crucial pour la transparence.
        *   **Obligatoire :** Un interrupteur (Oui/Non) pour déterminer si le client *doit* cocher cette case pour terminer l'inscription.
            *   *Lorsqu'il est activé (Oui) :* Les clients ne peuvent pas s'inscrire sans cocher cette case. C'est idéal pour les accords légaux essentiels.
            *   *Lorsqu'il est désactivé (Non) :* Les clients peuvent s'inscrire même s'ils ne cochent pas cette case. Cela convient aux consentements facultatifs comme les abonnements à la newsletter.
        *   **Actif :** Un interrupteur (Oui/Non) pour activer ou désactiver l'affichage de la case à cocher sur le front office.
            *   *Lorsqu'il est activé (Oui) :* La case à cocher sera visible sur le formulaire d'inscription.
            *   *Lorsqu'il est désactivé (Non) :* La case à cocher sera masquée du formulaire d'inscription mais conservée dans le Back Office pour une utilisation future.
        *   **Position :** Un entier pour contrôler l'ordre dans lequel les cases à cocher apparaissent sur le formulaire d'inscription. Les nombres inférieurs apparaissent plus haut.
    *   **Modifier/Supprimer :** Chaque case à cocher de la liste aura des actions pour modifier ses détails ou la supprimer entièrement.
-   **Effet des modifications :**
    *   **Ajout d'une nouvelle case à cocher :** La nouvelle case à cocher apparaîtra immédiatement sur votre formulaire d'inscription client (si active) et sur la page « Mes informations personnelles » du client.
    *   **Modification d'une case à cocher :** Les modifications apportées au libellé, au lien, au statut obligatoire ou au statut actif seront instantanément reflétées sur le front office.
    *   **Suppression d'une case à cocher :** La case à cocher sera supprimée du front office. Les consentements clients existants pour cette case à cocher spécifique resteront enregistrés dans l'historique mais aucun nouveau consentement ne pourra être donné.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  **Identifier les besoins en consentement :** Avant d'ajouter, déterminez les consentements spécifiques dont vous avez besoin (par exemple, Politique de confidentialité, Newsletter, Vérification de l'âge, conditions de service spécifiques).
    2.  **Créer des pages de contenu :** Assurez-vous d'avoir des pages CMS dédiées (ou des liens externes) pour chaque politique ou terme auquel vous souhaitez lier.
    3.  **Ajouter des cases à cocher :** Allez dans « Liste des cases à cocher » et cliquez sur « Ajouter une nouvelle case à cocher ». Remplissez le libellé, le lien, définissez-le comme obligatoire/facultatif et activez-le.
    4.  **Ordonner les cases à cocher :** Utilisez le champ « Position » pour les organiser logiquement.
    5.  **Vérifier le Front Office :** Testez toujours le processus d'inscription sur le front office de votre boutique après avoir apporté des modifications pour vous assurer que tout s'affiche et fonctionne comme prévu.

#### AdminAddTosHistoryController (Back Office > Modules > Cases à cocher supplémentaires > Historique)

Cet écran fournit un enregistrement historique des consentements des clients pour chaque case à cocher.

-   **Nom de l'écran et emplacement du menu :** Vous pouvez trouver cet écran en naviguant vers **Modules > Cases à cocher supplémentaires > Historique** dans le menu de votre Back Office PrestaShop.
-   **Actions et paramètres disponibles :**
    *   **Tableau de l'historique des consentements :** Cette page affiche un journal détaillé du moment où chaque client a accepté (ou refusé) une case à cocher spécifique.
    *   **Les colonnes incluent généralement :**
        *   **Nom du client :** Le nom du client.
        *   **Nom de la case à cocher :** Le libellé de la case à cocher avec laquelle ils ont interagi.
        *   **Statut du consentement :** S'ils ont accepté (coché) ou refusé (décoché) la case.
        *   **Date :** L'horodatage de l'enregistrement du consentement.
        *   **Adresse IP :** L'adresse IP à partir de laquelle le consentement a été donné (important pour la conformité légale).
    *   **Filtrage/Recherche :** Vous pouvez généralement filtrer cette liste par client, case à cocher ou plage de dates pour trouver des enregistrements de consentement spécifiques.
-   **Effet des modifications :** Cet écran est principalement destiné à la visualisation et à l'audit. Vous ne pouvez pas modifier directement les enregistrements de consentement ici, car ils représentent des faits historiques.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    *   **Audit et conformité :** Utilisez cet écran pour vérifier les consentements des clients en cas de litige ou pour des audits de conformité internes.
    *   **Demandes de confidentialité des données :** Si un client demande à savoir quelles données vous détenez ou à quoi il a consenti, cet historique fournit un enregistrement clair.

#### index.php (addtos/controllers/admin/index.php)

Ce fichier est un espace réservé et contient généralement une simple `header('Location: ../../../index.php?controller=AdminHome');` ou une redirection similaire pour empêcher l'accès direct au répertoire. Il ne représente pas un écran configurable pour le marchand.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Vérification des mises à jour MyPresta.eu | Activé | Vous informe des nouvelles versions du module pour la sécurité et les fonctionnalités. |
| **Liste des cases à cocher** | Nom/Libellé de la case à cocher | N/A (Défini par l'utilisateur) | Le texte visible à côté de la case à cocher sur le formulaire d'inscription. |
| **Liste des cases à cocher** | Lien (URL) | N/A (Défini par l'utilisateur) | URL vers une page de politique ; fournit des détails pour la case à cocher. |
| **Liste des cases à cocher** | Obligatoire | Non (Facultatif) | Si Oui, le client *doit* cocher pour s'inscrire. Si Non, c'est facultatif. |
| **Liste des cases à cocher** | Actif | Oui | Si Oui, la case à cocher est visible sur le front office. Si Non, elle est masquée. |
| **Liste des cases à cocher** | Position | N/A (Défini par l'utilisateur) | Détermine l'ordre d'affichage des cases à cocher sur le formulaire. |
| **Historique** | Nom du client | N/A (Lecture seule) | Affiche quel client a donné son consentement. |
| **Historique** | Nom de la case à cocher | N/A (Lecture seule) | Affiche quelle case à cocher a été utilisée. |
| **Historique** | Statut du consentement | N/A (Lecture seule) | Indique si le client a accepté ou refusé. |
| **Historique** | Date | N/A (Lecture seule) | Horodatage de l'enregistrement du consentement. |
| **Historique** | Adresse IP | N/A (Lecture seule) | Adresse IP à partir de laquelle le consentement a été donné. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai ajouté une nouvelle case à cocher, mais elle n'apparaît pas sur la page d'inscription.**
**R1 :**

-   **Vérifiez le statut « Actif » :** Allez dans **Modules > Cases à cocher supplémentaires > Liste des cases à cocher** et assurez-vous que l'interrupteur « Actif » de votre case à cocher est réglé sur « Oui ».
-   **Videz le cache :** Parfois, le cache de PrestaShop peut empêcher l'apparition immédiate de nouveau contenu. Allez dans **Paramètres avancés > Performance**, faites défiler jusqu'à « Vider le cache » et cliquez sur « Vider le cache ».
-   **Position du module :** Assurez-vous que le module est correctement accroché. Bien que le module gère généralement cela automatiquement, si vous avez apporté des modifications au thème, il peut être utile de vérifier les hooks du module dans **Design > Positions** (ou **Modules > Positions** dans les versions antérieures). Le module utilise généralement `displayAdditionalCustomerFormFields` ou des hooks similaires.

**Q2 : Le texte de ma case à cocher est trop long et s'affiche mal sur mobile.**
**R2 :**

-   **Soyez concis :** Essayez de raccourcir le libellé de la case à cocher à son essence (par exemple, « Accepter la politique de confidentialité » au lieu de « J'ai lu et j'accepte les termes et conditions de la politique de confidentialité de ce site Web »).
-   **Utilisez des liens :** Placez les informations détaillées sur une page CMS distincte et liez-y depuis le libellé de la case à cocher. Cela permet de garder le formulaire propre tout en offrant une transparence totale.
-   **Personnalisation du thème :** Si le problème persiste, le CSS de votre thème pourrait limiter l'affichage. Un webmaster peut ajuster le CSS pour les classes `.addtos-checkbox` ou similaires afin d'améliorer la réactivité.

**Q3 : Puis-je traduire les libellés des cases à cocher dans différentes langues ?**
**R3 :** Oui ! Lorsque vous modifiez une case à cocher dans **Modules > Cases à cocher supplémentaires > Liste des cases à cocher**, vous devriez voir un sélecteur de langue à côté du champ « Nom/Libellé » (souvent une icône de drapeau). Cliquez sur le drapeau pour passer à une autre langue et saisissez le texte traduit pour cette langue. N'oubliez pas d'enregistrer vos modifications pour chaque langue.

**Q4 : Que se passe-t-il si je supprime une case à cocher ? Cela supprime-t-il l'historique des consentements du client ?**
**R4 :** Non, la suppression d'une case à cocher de la « Liste des cases à cocher » la supprimera du formulaire d'inscription du front-office, mais elle **ne supprimera pas les enregistrements de consentement historiques** que les clients ont précédemment donnés pour cette case à cocher. Ces enregistrements restent dans la section « Historique » à des fins d'audit et de conformité. Les nouveaux clients ne verront tout simplement plus cette case à cocher.

**Q5 : Je souhaite modifier l'ordre des cases à cocher sur la page d'inscription.**
**R5 :** Allez dans **Modules > Cases à cocher supplémentaires > Liste des cases à cocher**. Dans le tableau, vous devriez voir une colonne « Position ». Vous pouvez généralement faire glisser et déposer les lignes pour les réorganiser, ou il peut y avoir des flèches haut/bas ou un champ numérique modifiable pour modifier la position. N'oubliez pas d'enregistrer vos modifications si nécessaire.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Cases à cocher supplémentaires lors de l'inscription » suit un modèle MVC (Modèle-Vue-Contrôleur) PrestaShop standard, étendant principalement `Module` pour sa fonctionnalité principale et `AdminController` pour la gestion du Back Office. Il utilise le système de hooks de PrestaShop pour injecter des champs personnalisés dans les formulaires d'inscription et d'identité des clients et pour enregistrer les données de consentement. Le module introduit des tables de base de données personnalisées pour stocker les définitions des cases à cocher et l'historique des consentements des clients.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Ce module n'utilise pas de contrôleurs frontaux dédiés. Toutes les interactions front-office (affichage des cases à cocher, traitement du consentement) sont gérées directement via les contrôleurs client principaux de PrestaShop en utilisant des hooks spécifiques.
-   **Contrôleurs d'administration Back-Office** :

    -   `addtos/controllers/admin/AdminAddTosHistory.php`
        -   **Nom de la classe et classe parente** : `AdminAddTosHistoryController` étend `ModuleAdminController`.
        -   **Nom de l'onglet et entité gérée** : Gère les enregistrements historiques des consentements des clients. Il est accessible via l'onglet « Historique » sous le menu principal du module. Ce contrôleur affiche une vue `list` des objets `TosHistory`, montrant le client, la case à cocher, le statut du consentement, la date et l'IP. Il ne permet pas de modifier ou d'ajouter des enregistrements, car il s'agit d'un journal historique.
    -   `addtos/controllers/admin/AdminAddTosList.php`
        -   **Nom de la classe et classe parente** : `AdminAddTosListController` étend `ModuleAdminController`.
        -   **Nom de l'onglet et entité gérée** : Gère la définition des cases à cocher personnalisées. Il est accessible via l'onglet « Liste des cases à cocher ». Ce contrôleur fournit des vues `list`, `add` et `edit` pour les objets `Tos`, permettant aux administrateurs de définir le libellé de la case à cocher, le lien, le statut obligatoire, le statut actif et la position.
    -   `addtos/controllers/admin/index.php`
        -   Il s'agit d'un fichier d'espace réservé standard pour empêcher l'affichage du répertoire. Il contient généralement `header('Location: ../../../index.php?controller=AdminHome');` ou similaire. Il n'a aucun rôle fonctionnel dans la logique du module.

### 4.3 Classes et modèles principaux (`classes/`)

Les classes principales du module sont probablement définies dans le fichier `addtos.php` principal ou directement dans le répertoire `classes/` si présent (bien que l'inventaire suggère qu'elles pourraient être dans le fichier principal).

-   `Tos` (Probablement défini dans `addtos.php` ou `classes/Tos.php`) :

    -   **Table de base de données** : `ps_addtos_tos` (ou similaire, basé sur le nom de l'entité `tos`).
    -   **Étend `ObjectModel`** : Oui.
    -   **Champs `$definition`** :
        -   `id_tos` : Clé primaire.
        -   `name` : Champ `HTML`, `isLang` (multilingue) - le libellé de la case à cocher.
        -   `link` : Champ `HTML`, `isLang` (multilingue) - l'URL pour plus d'informations.
        -   `required` : `BOOL` - si la case à cocher est obligatoire.
        -   `active` : `BOOL` - si la case à cocher est actuellement affichée.
        -   `position` : `INT` - ordre d'affichage.
    -   **Méthodes publiques clés** : Méthodes `ObjectModel` standard pour les opérations CRUD.
-   `TosHistory` (Probablement défini dans `addtos.php` ou `classes/TosHistory.php`) :

    -   **Table de base de données** : `ps_addtos_toshistory` (ou similaire, basé sur le nom de l'entité `toshistory`).
    -   **Étend `ObjectModel`** : Oui.
    -   **Champs `$definition`** :
        -   `id_toshistory` : Clé primaire.
        -   `id_customer` : `INT` - ID du client qui a donné son consentement.
        -   `id_tos` : `INT` - ID de la case à cocher.
        -   `accepted` : `BOOL` - `1` si accepté, `0` si refusé (ou `NULL` si facultatif et non coché).
        -   `date_add` : `DATE` - horodatage du consentement.
        -   `ip_address` : `STRING` - adresse IP du client au moment du consentement.
    -   **Méthodes publiques clés** : Principalement pour les opérations `add` et `read`, car les enregistrements d'historique sont immuables.

### 4.4 Actifs JavaScript (`views/js/`)

L'inventaire n'indique aucun fichier JavaScript spécifique. Cela suggère que toute validation côté client ou comportement dynamique pour les cases à cocher est géré soit par le JS principal de PrestaShop, le JS du thème, soit n'est pas une fonctionnalité principale de ce module (s'appuyant sur la validation côté serveur).

### 4.5 Feuilles de style CSS (`views/css/`)

L'inventaire n'indique aucun fichier CSS spécifique. Cela implique que le module s'appuie sur le style PrestaShop par défaut pour les éléments de formulaire ou le CSS du thème actif pour styliser les cases à cocher. Les développeurs souhaitant personnaliser l'apparence cibleraient les sélecteurs d'entrée de formulaire standard ou potentiellement les classes ajoutées par le module dans ses modèles.

### 4.6 Structure du modèle Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** :
    -   `addtos/views/templates/hook/addtos_bo.tpl` : Ce modèle est probablement utilisé dans le Back Office, éventuellement pour afficher un bloc de module ou des informations dans une page d'administration, ou pour rendre du contenu dans la page de configuration du module (par exemple, les notifications de mise à jour).
-   **Modèles d'administration (`views/templates/admin/`)** : Aucun modèle d'administration dédié n'est répertorié, ce qui suggère que `AdminAddTosListController` et `AdminAddTosHistoryController` s'appuient sur les modèles `list.tpl` et `form.tpl` par défaut de PrestaShop pour rendre leurs vues.
-   **Modèles Front-office (`views/templates/front/`)** :
    -   `addtos/views/templates/front/identity.tpl` : Ce modèle est probablement accroché à la page « Mes informations personnelles » (Identité) du client. Il afficherait la liste des cases à cocher et le statut de consentement actuel du client, lui permettant potentiellement de mettre à jour ses préférences.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   `ps_addtos_tos` : Stocke les définitions de chaque case à cocher personnalisée (libellé, lien, statut obligatoire, statut actif, position).
    -   `ps_addtos_tos_lang` : Stocke le contenu multilingue pour les champs `name` et `link` de la table `ps_addtos_tos`.
    -   `ps_addtos_toshistory` : Stocke les enregistrements historiques des consentements des clients (ID client, ID de la case à cocher, statut accepté, horodatage, adresse IP).
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionValidateOrder` | Après la validation d'une commande. | Potentiellement utilisé pour enregistrer le consentement lié aux conditions spécifiques à la commande, bien que moins courant pour les cases à cocher d'inscription. |
| `validateCustomerFormFields` | Lors de la validation de la soumission du formulaire d'inscription client. | Crucial pour la validation côté serveur des cases à cocher obligatoires. Si une case à cocher obligatoire n'est pas cochée, ce hook empêcherait l'inscription. |
| `displayAdditionalCustomerFormFields` | Rend des champs supplémentaires sur le formulaire d'inscription client. | Hook principal pour afficher les cases à cocher personnalisées sur la page d'inscription du front-office. |
| `displaytermsAndConditions` | Rend le contenu des conditions générales. | Pourrait être utilisé pour afficher des cases à cocher près des CGV standard, ou comme alternative. |
| `displayvalidateCustomerFormFields` | Rend les messages de validation pour les champs du formulaire client. | Utilisé pour afficher les messages d'erreur si une case à cocher obligatoire n'est pas cochée. |
| `additionalCustomerFormFields` | Similaire à `displayAdditionalCustomerFormFields`, potentiellement pour différents contextes ou versions. | Un autre hook pour injecter des champs personnalisés dans les formulaires client. |
| `termsAndConditions` | Similaire à `displaytermsAndConditions`. | Un autre hook pour injecter les conditions générales. |
| `actionCustomerAccountAdd` | Après la création réussie d'un nouveau compte client. | Utilisé pour enregistrer les choix de consentement du client pour toutes les cases à cocher actives dans la table `ps_addtos_toshistory`. |
| `displayAdminCustomers` | Rend le contenu sur la page de liste/modification des clients de l'administration. | Pourrait être utilisé pour afficher un résumé des consentements d'un client directement dans son profil Back Office. |
| `displayCustomerAccountForm` | Rend le contenu sur la page « Mes informations personnelles » (Identité) du client. | Utilisé pour afficher les cases à cocher et permettre aux clients de consulter/mettre à jour leurs préférences de consentement après l'inscription. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Cases à cocher supplémentaires lors de l'inscription », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la configuration du module.
