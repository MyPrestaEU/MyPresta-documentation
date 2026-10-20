---
title: "Récupération de mot de passe simple - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Récupération de mot de passe simple' par MyPresta.eu."
sidebar:
  label: "Récupération de mot de passe simple - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Simple password recovery sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/simple-password-recovery.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/simple-password-recovery/)
>
> ---


# Récupération de mot de passe simple

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur inhabituelle n'est requise.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Le module « Récupération de mot de passe simple » est conçu pour être largement plug-and-play, remplaçant le flux de récupération de mot de passe par défaut de PrestaShop avec une configuration minimale requise.

Lorsque vous naviguez vers **Modules > Gestionnaire de modules** et cliquez sur « Configurer » à côté de « Récupération de mot de passe simple », vous trouverez généralement une interface de configuration simple.

**Ce que fait ce paramètre :** Cet écran vous permet d'activer ou de désactiver la fonctionnalité principale du module et potentiellement d'ajuster des paramètres comportementaux mineurs. L'objectif principal est d'activer le processus simplifié de récupération de mot de passe.

**Effet de la modification de ce paramètre :**

- **Lorsqu'il est activé :** Le module prend le relais du mécanisme de récupération de mot de passe par défaut de PrestaShop. Lorsqu'un client demande une réinitialisation de mot de passe, il recevra un e-mail avec un lien unique et sécurisé qui le dirigera vers une page dédiée pour définir son nouveau mot de passe. Cela simplifie considérablement l'expérience utilisateur.
- **Lorsqu'il est désactivé :** La fonctionnalité du module est désactivée. Votre boutique PrestaShop reviendra à son processus de récupération de mot de passe standard par défaut, qui peut impliquer plus d'étapes ou différentes méthodes de vérification pour le client.

**Valeur recommandée :** **Activé (OUI)**. L'avantage principal de ce module est de simplifier le processus de récupération de mot de passe. Le maintenir activé garantit que vos clients bénéficient de cette expérience améliorée.

**Scénario / exemple de marchand :**
Vous avez remarqué que les clients contactent fréquemment le support car ils ont des difficultés avec la récupération de mot de passe par défaut. En activant ce module, vous fournissez un lien direct en un clic dans l'e-mail, leur permettant de définir instantanément un nouveau mot de passe. Cela réduit la confusion et les ramène plus rapidement aux achats.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Statut du module (Activer/Désactiver) | Activé | Active ou désactive le processus simplifié de récupération de mot de passe. Lorsqu'il est activé, les clients reçoivent un lien direct pour définir un nouveau mot de passe. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes clients ne reçoivent pas les e-mails de réinitialisation de mot de passe.**
R :

- **Vérifier les dossiers de spam :** Conseillez aux clients de vérifier leurs dossiers de spam ou de courrier indésirable.
- **Configuration des e-mails :** Vérifiez les paramètres de votre e-mail PrestaShop sous **Paramètres avancés > E-mail**. Assurez-vous que vos paramètres SMTP sont corrects ou que la fonction PHP `mail()` fonctionne.
- **Conflits de modules :** Désactivez temporairement d'autres modules qui pourraient interférer avec l'envoi d'e-mails ou la gestion des comptes clients pour exclure les conflits.
- **Journaux du serveur :** Vérifiez les journaux de courrier de votre serveur pour toute erreur liée aux e-mails sortants.

**Q : Le lien de réinitialisation de mot de passe dirige les clients vers une page blanche ou une erreur.**
R :

- **Vider le cache :** Allez dans **Paramètres avancés > Performances** et videz votre cache Smarty, le cache du navigateur et le cache du module.
- **Réécriture d'URL :** Assurez-vous que la réécriture d'URL est activée dans PrestaShop (**Paramètres de la boutique > SEO & URL**) et que votre fichier `.htaccess` est correctement configuré.
- **Intégrité du module :** Téléchargez à nouveau les fichiers du module via FTP pour vous assurer qu'aucun fichier n'est corrompu ou manquant.
- **Compatibilité du thème :** Bien que rare, un thème fortement personnalisé pourrait avoir des conflits JavaScript. Vérifiez la console de développement de votre navigateur pour toute erreur JavaScript.

**Q : Puis-je personnaliser l'apparence de la nouvelle page de mot de passe ?**
R : Oui, le module utilise le système de templating standard de PrestaShop. L'apparence est principalement contrôlée par le CSS de votre thème PrestaShop actif et le propre CSS du module (`spreset/views/css/spreset.css`). Les développeurs peuvent surcharger ces styles dans le CSS personnalisé de votre thème ou en modifiant les fichiers de template du module (`views/templates/front/password-change-form.tpl`, `views/templates/front/simple-reset-page.tpl`, `views/templates/front/simple-reset.tpl`).

**Q : Ce module fonctionne-t-il avec les boutiques multilingues ?**
R : Oui, comme la plupart des modules PrestaShop, les chaînes de texte sont traduisibles. Vous pouvez traduire les phrases du module via **International > Traductions** dans votre Back Office, en sélectionnant « Traductions des modules installés » puis en trouvant « Récupération de mot de passe simple ».

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module « Récupération de mot de passe simple ».

### 4.1 Vue d'ensemble de l'architecture

Le module « Récupération de mot de passe simple » remplace le mécanisme de récupération de mot de passe par défaut de PrestaShop en introduisant des contrôleurs frontaux personnalisés pour gérer la génération de jetons, l'envoi d'e-mails et le processus de définition du nouveau mot de passe. Il tire parti du modèle MVC de PrestaShop, avec des contrôleurs dédiés pour les différentes étapes de la récupération. Le fichier principal du module (`index.php`) gère l'installation, la désinstallation et le formulaire de configuration principal.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :

  - `controllers/front/changepass.php`
    - **Nom de la classe** : `SpresetChangepassModuleFrontController` (étend `ModuleFrontController`)
    - **Responsabilité** : Ce contrôleur est responsable de l'affichage du formulaire où un client peut définir son nouveau mot de passe après avoir cliqué sur le lien de réinitialisation sécurisé. Il valide le jeton fourni dans l'URL et gère la soumission du nouveau mot de passe.
  - `controllers/front/index.php`
    - **Nom de la classe** : `SpresetIndexModuleFrontController` (étend `ModuleFrontController`)
    - **Responsabilité** : Ce contrôleur sert probablement de solution de repli ou de point d'entrée général pour la fonctionnalité front-office du module, potentiellement en redirigeant ou en gérant les requêtes initiales liées au processus de réinitialisation de mot de passe. Dans de nombreux cas, il peut s'agir d'un espace réservé ou être utilisé pour un routage spécifique.
  - `controllers/front/simplereset.php`
    - **Nom de la classe** : `SpresetSimpleresetModuleFrontController` (étend `ModuleFrontController`)
    - **Responsabilité** : Ce contrôleur est le cœur du processus de réinitialisation simplifié. Il reçoit la demande initiale de réinitialisation de mot de passe (par exemple, à partir du formulaire standard « Mot de passe oublié » de PrestaShop), génère le jeton sécurisé, envoie l'e-mail avec le lien de réinitialisation unique et gère la validation initiale de l'adresse e-mail du client.
- **Contrôleurs d'administration Back-Office** : Aucun. La configuration du module est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne semble pas définir de classes personnalisées étendant `ObjectModel` ou d'autres classes PrestaShop principales dans un répertoire `classes/` dédié. Sa logique est principalement encapsulée dans le fichier principal du module et ses contrôleurs frontaux.

### 4.4 Actifs JavaScript (`views/js/`)

- `views/js/spreset.js`
  - **Portée** : Front-office.
  - **Détails** : Ce script gère probablement la validation côté client pour le nouveau formulaire de mot de passe (par exemple, vérifier si les mots de passe correspondent, les exigences de longueur minimale) et potentiellement les soumissions AJAX pour le changement de mot de passe. Il peut également inclure des améliorations d'interface utilisateur ou des interactions spécifiques à la page de réinitialisation de mot de passe. Les développeurs doivent inspecter ce fichier pour des écouteurs d'événements spécifiques (par exemple, `submit` sur le formulaire de mot de passe) et toute fonction personnalisée.

### 4.5 Feuilles de style CSS (`views/css/`)

- `views/css/spreset.css`
  - **Portée** : Style client Front-office.
  - **Détails** : Cette feuille de style fournit un style spécifique pour les composants front-office du module, principalement le formulaire de saisie du nouveau mot de passe et les pages associées. Elle garantit que l'interface de récupération de mot de passe est présentable et s'intègre raisonnablement bien avec divers thèmes. Les développeurs peuvent inspecter ce fichier pour identifier les sélecteurs de classe CSS clés (par exemple, `.spreset-form`, `.spreset-input`, `.spreset-button`) qui peuvent être surchargés dans le fichier CSS personnalisé de leur thème pour correspondre à l'image de marque de la boutique.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates Front-office (`views/templates/front/`)** :

  - `views/templates/front/password-change-form.tpl`
    - **Objectif** : Ce template rend probablement le formulaire réel où le client saisit et confirme son nouveau mot de passe. Il contiendrait des champs de saisie pour « Nouveau mot de passe » et « Confirmer le nouveau mot de passe », ainsi qu'un bouton de soumission.
  - `views/templates/front/simple-reset-page.tpl`
    - **Objectif** : Ce template pourrait servir d'enveloppe principale ou de mise en page pour le processus simplifié de réinitialisation de mot de passe, incluant potentiellement des messages, des instructions et l'intégration d'autres templates partiels comme `password-change-form.tpl`.
  - `views/templates/front/simple-reset.tpl`
    - **Objectif** : Similaire à `simple-reset-page.tpl`, ce template fait partie de l'affichage front-office pour le flux de réinitialisation de mot de passe. Il pourrait être utilisé pour le formulaire initial « saisir votre e-mail » ou pour afficher des messages de succès/erreur liés à la demande de réinitialisation.
- **Templates spécifiques au module (`views/templates/`)** :

  - `views/templates/spreset.tpl`
    - **Objectif** : Ce template est probablement utilisé pour la configuration principale du module dans le Back Office (si `getContent()` rend un template) ou pour un hook d'affichage générique si le module a une sortie simple pour un hook. Compte tenu de la nature du module, il est plus probable qu'il s'agisse de la configuration du Back Office.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** : Le module ne semble pas créer de tables SQL personnalisées. Il utilise probablement les tables PrestaShop existantes (par exemple, `ps_customer` pour les données client, `ps_configuration` pour les paramètres du module) et génère des jetons temporaires sans stockage persistant dans une table dédiée. Les jetons sont généralement stockés dans la session ou passés via des paramètres d'URL avec une courte expiration.
- **Table des hooks enregistrés** :
  Le module ne liste pas explicitement les hooks enregistrés dans les informations fournies, mais basé sur sa fonctionnalité, il interagirait implicitement avec le flux de récupération de mot de passe standard de PrestaShop, qui est souvent déclenché par les hooks `displayCustomerAccountForm` ou `actionAuthenticationBefore`, ou en surchargeant les contrôleurs PrestaShop principaux.
  Le fichier principal du module (`index.php`) enregistrerait ses contrôleurs frontaux pour gérer des routes spécifiques, s'« accrochant » efficacement au système de routage d'URL plutôt qu'aux hooks `display` ou `action` traditionnels pour la sortie visuelle.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Récupération de mot de passe simple », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe s'engage à assurer la performance et la compatibilité optimales de nos modules avec les dernières versions de PrestaShop.
