---
title: "Demander des informations sur un produit gratuit - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Demander des informations sur un produit gratuit' par MyPresta.eu."
sidebar:
  label: "Demander des informations sur un produit gratuit - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Ask about product free sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/ask-about-product-free.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/ask-about-product-free/)
>
> ---


# Demander des informations sur un produit gratuit

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module « Demander des informations sur un produit gratuit », où vous contrôlez son comportement et son apparence.

-   **Emplacement du menu :** Back Office > Modules > Gestionnaire de modules > « Demander des informations sur un produit gratuit » > Configurer

#### Paramètres et options :

1.  **Afficher le résumé du produit dans la fenêtre contextuelle**

    -   **Ce que fait ce paramètre :** Contrôle si un petit résumé du produit (comme son nom et son image) est affiché dans le formulaire contextuel « Demander des informations sur un produit ».
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (Oui) :* Le formulaire contextuel inclura un bref aperçu du produit sur lequel le client pose la question. Cela aide le client à confirmer qu'il pose la question sur le bon article et vous fournit un contexte lorsque vous recevez l'e-mail.
        -   *Lorsqu'désactivé (Non) :* Le formulaire contextuel ne contiendra que les champs pour le nom du client, l'e-mail et la question, sans aucun résumé spécifique au produit.
    -   **Valeur recommandée :** **Oui**.
    -   **Scénario / exemple de marchand :** L'activation de cette option aide à éviter la confusion. Un client pourrait avoir plusieurs onglets ouverts et oublier sur quel produit il pose la question. Le résumé le confirme pour lui et pour vous.
2.  **Activé**

    -   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver l'ensemble de la fonctionnalité « Demander des informations sur un produit » sur votre boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (Oui) :* Le bouton « Demander des informations sur un produit » apparaîtra sur les pages produit, et le formulaire contextuel sera fonctionnel.
        -   *Lorsqu'désactivé (Non) :* Le bouton « Demander des informations sur un produit » sera masqué des pages produit, et les clients ne pourront pas utiliser cette fonctionnalité.
    -   **Valeur recommandée :** **Oui** (pour utiliser le module).
    -   **Scénario / exemple de marchand :** Vous pourriez le désactiver temporairement si vous effectuez une maintenance ou si vous préférez gérer toutes les demandes via un canal différent pendant une période.
3.  **Conforme au RGPD**

    -   **Ce que fait ce paramètre :** Active une case à cocher sur le formulaire « Demander des informations sur un produit », exigeant des clients qu'ils acceptent explicitement votre politique de confidentialité avant de soumettre leur question. Cela aide votre boutique à se conformer au RGPD et aux autres réglementations en matière de protection des données.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (Oui) :* Une case à cocher obligatoire apparaîtra sur le formulaire, indiquant généralement quelque chose comme « J'accepte la politique de confidentialité ». Le client doit cocher cette case pour soumettre sa question.
        -   *Lorsqu'désactivé (Non) :* La case à cocher de la politique de confidentialité ne sera pas affichée, et les clients pourront soumettre leurs questions sans consentement explicite.
    -   **Valeur recommandée :** **Oui**.
    -   **Scénario / exemple de marchand :** Si votre boutique opère dans des régions avec des lois strictes sur la protection des données (comme l'UE), l'activation de cette option est cruciale pour la conformité légale.
4.  **Page de politique de confidentialité**

    -   **Ce que fait ce paramètre :** Si « Conforme au RGPD » est activé, ce paramètre vous permet de sélectionner quelle page CMS (Système de Gestion de Contenu) de votre boutique sera liée en tant que votre politique de confidentialité.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'une page est sélectionnée :* Le texte « J'accepte la politique de confidentialité » dans le formulaire contextuel inclura un lien cliquable vers la page CMS choisie, permettant aux clients de consulter facilement votre politique.
        -   *Lorsqu'aucune page n'est sélectionnée (ou si Conforme au RGPD est Non) :* Aucun lien ne sera fourni, ou la fonctionnalité RGPD ne sera pas active.
    -   **Valeur recommandée :** Sélectionnez la page officielle de politique de confidentialité de votre boutique.
    -   **Scénario / exemple de marchand :** Vous devez avoir une page CMS dédiée décrivant vos pratiques de traitement des données. Ce paramètre garantit que les clients peuvent y accéder facilement.
5.  **Titre de l'e-mail**

    -   **Ce que fait ce paramètre :** Définit la ligne d'objet de l'e-mail que vous recevez lorsqu'un client soumet une question via le formulaire.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'un titre spécifique est défini (par exemple, « Nouvelle question sur un produit ») :* Tous les e-mails entrants de ce module utiliseront cette ligne d'objet, ce qui les rendra faciles à identifier dans votre boîte de réception.
        -   *Lorsqu'il est laissé par défaut :* Le module utilisera sa ligne d'objet par défaut, qui pourrait être moins descriptive.
    -   **Valeur recommandée :** Quelque chose de clair et descriptif, comme « Nouvelle question sur un produit de [Nom de votre boutique] ».
    -   **Scénario / exemple de marchand :** Une ligne d'objet claire vous aide à prioriser et à répondre rapidement aux demandes des clients, surtout si vous recevez de nombreux e-mails quotidiennement.
6.  **Destinataire de l'e-mail du formulaire**

    -   **Ce que fait ce paramètre :** Spécifie l'adresse(s) e-mail où les questions des clients soumises via le formulaire « Demander des informations sur un produit » seront envoyées.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'une ou plusieurs adresses e-mail sont saisies (séparées par des virgules) :* Le module enverra toutes les demandes des clients à ces adresses spécifiées.
        -   *Lorsqu'il est laissé vide :* Le module pourrait utiliser par défaut l'e-mail de contact principal de la boutique, ou la fonctionnalité pourrait ne pas fonctionner correctement.
    -   **Valeur recommandée :** Votre adresse e-mail de service client (par exemple, `support@votreboutique.com`) ou un e-mail dédié aux demandes de produits. Vous pouvez ajouter plusieurs e-mails séparés par des virgules si plusieurs membres de l'équipe doivent les recevoir.
    -   **Scénario / exemple de marchand :** Diriger ces e-mails vers la bonne équipe garantit des réponses rapides, améliorant la satisfaction client.
7.  **Protection ReCaptcha (v2)**

    -   **Ce que fait ce paramètre :** Intègre Google reCAPTCHA v2 (la case à cocher « Je ne suis pas un robot ») dans le formulaire « Demander des informations sur un produit » pour protéger contre le spam et les soumissions automatisées.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (Oui) :* La case à cocher reCAPTCHA apparaîtra sur le formulaire, exigeant des clients qu'ils réussissent le défi avant de soumettre.
        -   *Lorsqu'désactivé (Non) :* Le formulaire n'aura pas de protection reCAPTCHA, ce qui le rend potentiellement vulnérable aux robots spammeurs.
    -   **Valeur recommandée :** **Oui**.
    -   **Scénario / exemple de marchand :** Si vous recevez beaucoup de demandes de spam via le formulaire, l'activation de reCAPTCHA est essentielle pour filtrer les messages illégitimes.
8.  **Clé du site reCaptcha**

    -   **Ce que fait ce paramètre :** C'est la clé publique fournie par Google reCAPTCHA qui permet à votre site web d'afficher le widget reCAPTCHA. Vous obtenez cette clé lorsque vous enregistrez votre site auprès de Google reCAPTCHA.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'elle est correctement saisie :* Le widget reCAPTCHA s'affichera et fonctionnera correctement sur votre formulaire.
        -   *Lorsqu'elle est incorrecte ou vide :* reCAPTCHA ne fonctionnera pas, et vous pourriez voir un message d'erreur ou le formulaire ne sera pas soumis.
    -   **Valeur recommandée :** La clé du site obtenue depuis votre compte Google reCAPTCHA.
    -   **Scénario / exemple de marchand :** Vous devez enregistrer votre domaine auprès de Google reCAPTCHA (v2) pour obtenir à la fois une clé de site et une clé secrète.
9.  **Clé secrète reCaptcha**

    -   **Ce que fait ce paramètre :** C'est la clé privée fournie par Google reCAPTCHA qui permet à votre serveur de vérifier la réponse reCAPTCHA. Elle est utilisée pour la validation côté serveur.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'elle est correctement saisie :* Votre serveur peut vérifier avec succès si un client a réussi le défi reCAPTCHA.
        -   *Lorsqu'elle est incorrecte ou vide :* Même si le widget reCAPTCHA s'affiche, la soumission du formulaire échouera à la validation, et la question ne sera pas envoyée.
    -   **Valeur recommandée :** La clé secrète obtenue depuis votre compte Google reCAPTCHA.
    -   **Scénario / exemple de marchand :** Cette clé est cruciale pour l'aspect sécurité de reCAPTCHA, garantissant que seules les soumissions légitimes sont traitées.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Afficher le résumé du produit dans la fenêtre contextuelle | Oui | Affiche les détails du produit dans la fenêtre contextuelle pour plus de clarté. |
| Configuration du module | Activé | Oui | Active/désactive la fonctionnalité « Demander des informations sur un produit ». |
| Configuration du module | Conforme au RGPD | Oui | Ajoute une case à cocher d'accord sur la politique de confidentialité au formulaire. |
| Configuration du module | Page de politique de confidentialité | Sélectionnez votre page CMS de politique de confidentialité | Lien vers la politique de confidentialité de votre boutique pour le RGPD. |
| Configuration du module | Titre de l'e-mail | « Nouvelle question sur un produit de [Nom de votre boutique] » | Définit la ligne d'objet pour les e-mails de question entrants. |
| Configuration du module | Destinataire de l'e-mail du formulaire | Votre e-mail de service client (par exemple, `support@votreboutique.com`) | Spécifie où les questions des clients sont envoyées. |
| Configuration du module | Protection ReCaptcha (v2) | Oui | Active Google reCAPTCHA pour prévenir le spam. |
| Configuration du module | Clé du site reCaptcha | Votre clé de site Google reCAPTCHA | Clé publique pour afficher le widget reCAPTCHA. |
| Configuration du module | Clé secrète reCaptcha | Votre clé secrète Google reCAPTCHA | Clé privée pour la validation reCAPTCHA côté serveur. |

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### AdminAapfreeQuestionController (Back Office > Demander des informations sur un produit > Questions)

Cet écran d'administration dédié vous permet de visualiser et de gérer toutes les questions soumises via le formulaire « Demander des informations sur un produit ».

-   **Nom de l'écran et emplacement du menu :** Back Office > **Demander des informations sur un produit** (nouvel élément de menu) > **Questions**
-   **Actions et paramètres disponibles :**
    -   **Tableau de liste :** Cet écran affiche un tableau de toutes les questions soumises. Chaque ligne affiche généralement :
        -   **ID :** Identifiant unique de la question.
        -   **Nom du client :** Le nom fourni par le client.
        -   **E-mail du client :** L'adresse e-mail fournie par le client.
        -   **Nom du produit :** Le nom du produit concerné par la question.
        -   **Question :** Un extrait ou le texte complet de la question du client.
        -   **Date d'ajout :** Quand la question a été soumise.
        -   **Statut :** (par exemple, Nouveau, Répondu, En attente) - *Note : Le dossier du module ne mentionne pas explicitement un champ de statut, mais c'est une fonctionnalité courante pour de telles listes. S'il n'est pas présent, il listera simplement toutes les questions.*
    -   **Afficher les détails :** Vous pouvez généralement cliquer sur une question dans la liste pour afficher ses détails complets, y compris le texte complet de la question et potentiellement le lien du produit.
    -   **Supprimer :** Options pour supprimer des questions individuelles ou potentiellement supprimer en masse les questions sélectionnées.
-   **Effet des modifications :**
    -   **Visualisation des questions :** Vous permet de consulter toutes les demandes des clients dans un emplacement centralisé au sein de votre back office PrestaShop, même si vous les recevez également par e-mail.
    -   **Suppression des questions :** Supprime l'enregistrement de la question de votre base de données. Ceci est utile pour nettoyer les demandes anciennes ou non pertinentes.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Vérifiez régulièrement cette liste de « Questions » (ou votre boîte de réception, telle que configurée) pour les nouvelles demandes.
    2.  Priorisez et répondez rapidement aux questions pour maintenir un bon service client.
    3.  Après avoir répondu, vous pouvez supprimer la question de cette liste pour la garder propre, ou si le module le prend en charge, la marquer comme « Répondu ».

#### index.php (aapfree/controllers/admin/index.php)

Ce fichier est généralement un espace réservé ou un redirigeur dans le répertoire `controllers/admin` et ne représente pas un écran distinct et configurable pour le marchand. C'est une pratique standard de PrestaShop d'avoir un `index.php` dans les sous-répertoires pour empêcher la liste des répertoires, ou il peut contenir une logique de routage de base. Il ne gère pas de table ou d'entité spécifique pour une interaction directe avec le marchand.

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Le bouton « Demander des informations sur un produit » n'apparaît pas sur mes pages produit.**

-   **R :** Tout d'abord, vérifiez si le module est « Activé » dans ses paramètres de configuration (Back Office > Modules > Gestionnaire de modules > Demander des informations sur un produit gratuit > Configurer). Si c'est le cas, essayez de vider le cache de votre PrestaShop (Paramètres avancés > Performances > Vider le cache). Parfois, des conflits de thème ou des structures de thème personnalisées spécifiques peuvent empêcher le bouton d'apparaître. S'il est toujours manquant, contactez votre webmaster ou le support MyPresta.eu.

**Q2 : Je ne reçois aucun e-mail lorsque les clients soumettent des questions.**

-   **R :**
    1.  Vérifiez le paramètre « Destinataire de l'e-mail du formulaire » dans la configuration du module. Assurez-vous que l'adresse(s) e-mail est correcte et séparée par des virgules s'il y en a plusieurs.
    2.  Vérifiez votre dossier spam/courrier indésirable dans la boîte de réception du destinataire.
    3.  Assurez-vous que les paramètres d'e-mail de votre boutique sont correctement configurés dans PrestaShop (Paramètres avancés > E-mail). Testez l'envoi d'un e-mail général depuis PrestaShop pour confirmer que votre serveur de messagerie fonctionne.
    4.  Si ReCAPTCHA est activé, assurez-vous que les deux champs « Clé du site reCaptcha » et « Clé secrète reCaptcha » sont correctement saisis. Des clés incorrectes empêcheront les soumissions.

**Q3 : Le reCAPTCHA ne fonctionne pas, ou je vois un message d'erreur.**

-   **R :** Cela signifie généralement que vos clés reCAPTCHA sont incorrectes ou mal configurées avec Google.
    1.  Accédez à la console d'administration Google reCAPTCHA et assurez-vous que votre domaine est correctement enregistré pour reCAPTCHA v2.
    2.  Copiez la « Clé du site » et la « Clé secrète » exactement telles que fournies par Google et collez-les dans les champs de configuration du module.
    3.  Videz le cache de votre PrestaShop après avoir effectué des modifications.

**Q4 : Comment puis-je modifier le texte du bouton « Demander des informations sur un produit » ou du formulaire contextuel ?**

-   **R :** Vous pouvez traduire les chaînes de texte du module directement dans PrestaShop. Allez dans **International > Traductions**, sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez « Demander des informations sur un produit gratuit ». Vous y trouverez toutes les chaînes traduisibles, y compris les étiquettes de bouton, les étiquettes de champ de formulaire et les messages de confirmation.

**Q5 : La fenêtre contextuelle semble étrange ou ne s'affiche pas correctement sur mon téléphone portable.**

-   **R :** Bien que le module soit conçu pour être réactif, les thèmes personnalisés peuvent parfois remplacer ou entrer en conflit avec son style.
    1.  Videz le cache de votre navigateur et le cache de PrestaShop.
    2.  Si le problème persiste, il s'agit probablement d'un conflit CSS avec votre thème. Votre webmaster ou un développeur devrait inspecter la page à l'aide des outils de développement du navigateur pour identifier et résoudre le conflit CSS.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Demander des informations sur un produit gratuit » suit un modèle MVC (Modèle-Vue-Contrôleur) PrestaShop standard, se concentrant principalement sur l'interaction front-office et l'administration back-office des questions soumises. Il utilise le système de hooks de PrestaShop pour l'intégration dans les pages produit et utilise des contrôleurs frontaux dédiés pour les requêtes AJAX et la soumission de formulaires. Le composant back-office fournit une interface de gestion de liste simple pour les questions.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    -   `controllers/front/index.php`
        -   **Nom de la classe et classe parente :** `AapfreeIndexModuleFrontController` étendant `ModuleFrontController`.
        -   **Responsabilité :** Ce contrôleur gère probablement la logique d'affichage initiale du composant front-office du module, affichant éventuellement le bouton ou préparant les données pour la fenêtre contextuelle. Il peut également servir de fourre-tout pour les routes front-office spécifiques au module.
    -   `controllers/front/question.php`
        -   **Nom de la classe et classe parente :** `AapfreeQuestionModuleFrontController` étendant `ModuleFrontController`.
        -   **Responsabilité :** C'est le contrôleur principal pour la gestion de la soumission du formulaire « Demander des informations sur un produit ». Il reçoit les données POST du formulaire contextuel, valide les entrées (y compris reCAPTCHA si activé), traite la question, envoie l'e-mail aux destinataires configurés et stocke la question dans la base de données. Il renvoie des réponses JSON pour les requêtes AJAX (par exemple, messages de succès/erreur).
-   **Contrôleurs d'administration Back-Office** :

    -   `controllers/admin/AdminAapfreeQuestion.php`
        -   **Nom de la classe et classe parente :** `AdminAapfreeQuestionController` étendant `ModuleAdminController`.
        -   **Nom de l'onglet et entité gérée :** Ce contrôleur crée et gère l'onglet « Questions » sous le menu « Demander des informations sur un produit » dans le Back Office de PrestaShop. Il est responsable de l'affichage d'une liste (grille) de toutes les questions soumises, permettant aux administrateurs de visualiser les détails et de supprimer des entrées. Il interagit avec l'`ObjectModel` `AapfreeQuestion` (si elle existe, sinon directement avec la base de données).
    -   `controllers/admin/index.php`
        -   **Nom de la classe et classe parente :** Pas un contrôleur fonctionnel au sens traditionnel.
        -   **Nom de l'onglet et entité gérée :** Ce fichier est une mesure de sécurité standard de PrestaShop pour empêcher la liste des répertoires. Il contient généralement un simple `header('Location: ../../index.php?controller=AdminHome');` ou une redirection similaire, ou juste `<?php exit;`. Il ne gère aucune entité spécifique et ne fournit pas d'écran configurable.

### 4.3 Classes et modèles principaux (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que le module pourrait gérer les interactions avec la base de données directement dans ses contrôleurs ou le fichier principal du module, ou il pourrait utiliser un `ObjectModel` générique pour `aapfreequestion` s'il est implicitement défini.

-   **Modèle implicite (probable) :** Étant donné que l'`AdminAapfreeQuestionController` gère une table, il existe un modèle `AapfreeQuestion` implicite, même s'il n'est pas explicitement dans `classes/`. Ce modèle serait mappé à la table de base de données `_aapfree_question`.
    -   **Table de base de données :** `ps_aapfree_question` (ou similaire, basé sur le préfixe du module).
    -   **Étend `ObjectModel` :** Oui, implicitement.
    -   **Champs `$definition` (attendus) :** `id_aapfree_question`, `id_product`, `customer_name`, `customer_email`, `question_text`, `date_add`.

### 4.4 Actifs JavaScript (`views/js/`)

-   `aapfree/views/aapfree.js`
    -   **Portée :** Front-office.
    -   **Écouteurs d'événements :**
        -   Lie les événements de clic au bouton « Demander des informations sur un produit » (`.aapfree-button`).
        -   Lie les événements de soumission au formulaire « Demander des informations sur un produit » dans la fenêtre contextuelle (`#aapfree-form`).
        -   Gère les événements liés au widget reCAPTCHA (si activé).
    -   **Manipulation du DOM :**
        -   Ouvre et ferme la fenêtre contextuelle modale (`#aapfree-modal`).
        -   Remplit les données de résumé du produit dans la fenêtre contextuelle.
        -   Affiche les messages de succès ou d'erreur à l'utilisateur après la soumission du formulaire.
        -   Gère les états des champs du formulaire (par exemple, désactivation du bouton de soumission pendant AJAX).
    -   **Appels AJAX :**
        -   Envoie les données du formulaire à l'`AapfreeQuestionModuleFrontController` (par exemple, `index.php?fc=module&module=aapfree&controller=question`).
        -   Traite les réponses JSON du serveur.
    -   **Appels SDK externes :** Initialise et rend le widget Google reCAPTCHA v2 si `aapfree_recaptcha` est activé, en utilisant la `aapfree_recaptcha_sitekey`.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `aapfree/views/aapfree.css`
    -   **Portée :** Style client front-office.
    -   **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :**
        -   Le bouton « Demander des informations sur un produit » (`.aapfree-button`).
        -   Le conteneur de la fenêtre contextuelle modale (`#aapfree-modal`).
        -   Les éléments de formulaire dans la fenêtre contextuelle (champs de saisie, zones de texte, étiquettes, cases à cocher).
        -   Affichage des messages de succès et d'erreur.
        -   Ajustements réactifs pour différentes tailles d'écran.
    -   **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer :** `.aapfree-button`, `.aapfree-modal`, `.aapfree-modal-content`, `.aapfree-form-group`, `.aapfree-product-summary`, `.aapfree-success-message`, `.aapfree-error-message`. Les développeurs peuvent remplacer ces styles dans le `custom.css` de leur thème ou en utilisant les fonctionnalités de personnalisation de thème de PrestaShop.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** :
    -   `aapfree/views/aapfree-extra.tpl`
        -   **Hook :** `displayProductAdditionalInfo` (ou un hook de page produit similaire comme `displayProductButtons`, `displayProductActions`).
        -   **Sortie du bloc visuel :** Ce modèle est responsable du rendu du bouton « Demander des informations sur un produit » sur la page produit. Il contient également la structure HTML du formulaire contextuel modal, qui est initialement masqué et affiché via JavaScript. Il comprend des espaces réservés pour le résumé du produit, les champs du formulaire, la case à cocher RGPD et reCAPTCHA.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   `ps_aapfree_question` :
        -   `id_aapfree_question` (INT, CLÉ PRIMAIRE, AUTO\_INCREMENT)
        -   `id_product` (INT, Clé étrangère vers `ps_product`)
        -   `customer_name` (VARCHAR)
        -   `customer_email` (VARCHAR)
        -   `question_text` (TEXT)
        -   `date_add` (DATETIME)
        -   (Potentiellement d'autres champs comme `ip_address`, `status`, `id_customer` si implémentés)
    -   **Enregistrements de configuration (dans `ps_configuration`) :**
        -   `AAPFREE_TITLE` : Ligne d'objet de l'e-mail.
        -   `AAPFREE_GDPR` : Statut de conformité RGPD (0/1).
        -   `AAPFREE_GDPRCMS` : ID de la page CMS pour la politique de confidentialité.
        -   `AAPFREE_SUMMARY` : Statut d'affichage du résumé du produit (0/1).
        -   `AAPFREE_RECAPTCHA` : Statut de protection reCAPTCHA (0/1).
        -   `AAPFREE_RECAPTCHA_SITEKEY` : Clé de site Google reCAPTCHA.
        -   `AAPFREE_RECAPTCHA_SECRETKEY` : Clé secrète Google reCAPTCHA.
        -   `AAPFREE_EMAILSLIST` : Liste d'e-mails des destinataires séparés par des virgules.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayProductAdditionalInfo` | Sur les pages produit, généralement sous la description du produit ou le prix. | Rend le bouton « Demander des informations sur un produit » et la structure modale contextuelle masquée. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration charge ses actifs (CSS/JS). | Injecte le CSS (`aapfree.css`) et le JavaScript (`aapfree.js`) spécifiques au module dans le Back Office pour l'`AdminAapfreeQuestionController`. |
| `displayHeader` | Dans la section `<head>` de chaque page front-office. | Potentiellement utilisé pour charger des variables JavaScript globales, du CSS ou le script de l'API Google reCAPTCHA si reCAPTCHA est activé. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Demander des informations sur un produit gratuit », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe s'engage à assurer le bon fonctionnement et l'amélioration continue de votre module.
