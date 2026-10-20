---
title: "tinyMCE pro - éditeur de texte enrichi étendu - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop tinyMCE pro - éditeur de texte enrichi étendu par MyPresta.eu."
sidebar:
  label: "tinyMCE pro - éditeur de texte enrichi étendu - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module tinyMCE pro - extended rich text editor sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/tinymce-pro-extended-rich-text-editor.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/tinymce-pro-extended-rich-text-editor/)
>
> ---


# tinyMCE pro - éditeur de texte enrichi étendu

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement nécessaire au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » pour accéder aux paramètres principaux du module. Cet écran vous permet d'activer ou de désactiver l'éditeur amélioré et de gérer ses fonctionnalités principales.

La page de configuration de « tinyMCE pro » est conçue pour être simple, car le module fonctionne principalement en remplaçant et en améliorant l'éditeur existant sans paramètres utilisateur étendus au-delà de son activation.

-   **Ce que fait ce paramètre :** Ce module fonctionne principalement en remplaçant l'éditeur PrestaShop par défaut par une version améliorée de tinyMCE. La page de configuration contiendra généralement un interrupteur « Activer/Désactiver » pour le module lui-même, et potentiellement des options pour contrôler les zones spécifiques du back office auxquelles l'éditeur amélioré doit s'appliquer.
-   **Effet de la modification de ce paramètre :**

    -   *Lorsqu'il est activé :* L'éditeur de texte standard, souvent limité, dans des zones comme les descriptions de produits, les pages CMS et les descriptions de catégories sera remplacé par l'éditeur « tinyMCE pro ». Ce nouvel éditeur présentera une barre d'outils plus riche avec des options pour les icônes Font Awesome, l'intégration de vidéos YouTube, l'acceptation de code HTML/JavaScript avancé, et plus encore.
    -   *Lorsqu'il est désactivé :* Le module cessera de fonctionner et PrestaShop reviendra à son éditeur de texte par défaut. Toutes les fonctionnalités avancées fournies par « tinyMCE pro » ne seront plus disponibles.
-   **Valeur recommandée :** **Activé**. Pour bénéficier des fonctionnalités du module, il doit toujours être activé.
-   **Scénario/exemple pour le marchand :** Vous modifiez la description d'un nouveau produit. Avec « tinyMCE pro » activé, vous pouvez facilement ajouter une vidéo YouTube présentant le produit, inclure des icônes Font Awesome pour les fonctionnalités (par exemple, une icône de coche pour « En stock ») et utiliser une mise en forme avancée pour créer une mise en page visuellement attrayante, le tout directement dans l'éditeur. S'il est désactivé, vous seriez limité à la mise en forme de texte de base.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | **Statut du module (Activer/Désactiver)** | Activé | Contrôle si l'éditeur tinyMCE amélioré remplace l'éditeur PrestaShop par défaut dans le back office. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai activé le module, mais l'éditeur a toujours la même apparence. Que dois-je faire ?**
**R1 :** Après avoir activé tout module qui modifie le back office, il est recommandé de vider le cache de votre navigateur et le cache Smarty de PrestaShop.
-   **Cache du navigateur :** Actualisez votre navigateur (Ctrl+F5 ou Cmd+Maj+R).
-   **Cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** dans votre back office PrestaShop. Cliquez sur le bouton « Vider le cache » dans le coin supérieur droit.

**Q2 : Certaines des nouvelles fonctionnalités de l'éditeur (comme les icônes Font Awesome) ne s'affichent pas correctement sur mon front office.**
**R2 :** Cela indique généralement un conflit avec le CSS ou le JavaScript de votre thème personnalisé.
-   **Vérifier les conflits :** Basculez temporairement vers le thème PrestaShop par défaut (Classic ou Hummingbird) et vérifiez si les fonctionnalités s'affichent correctement. Si c'est le cas, le problème vient de votre thème personnalisé.
-   **Personnalisation du thème :** Votre thème pourrait remplacer ou ne pas inclure le CSS/JS nécessaire pour ces éléments. Vous devrez peut-être consulter votre développeur de thème ou un webmaster pour intégrer correctement les ressources front-office du module dans votre thème.

**Q3 : Puis-je utiliser cet éditeur pour toutes les langues de ma boutique ?**
**R3 :** Oui, l'éditeur tinyMCE est conçu pour fonctionner de manière transparente avec les capacités multilingues de PrestaShop. Lorsque vous changez de langue dans le back office, l'éditeur sera toujours disponible pour que vous puissiez saisir du contenu dans la langue sélectionnée. Le module comprend également des fichiers de langue pour plusieurs de ses plugins (par exemple, Font Awesome, PowerPaste), garantissant une expérience localisée là où elle est disponible.

**Q4 : Je vois une erreur après l'installation du module, ou mon back office est lent.**
**R4 :**
-   **Vérifiez les journaux d'erreurs du serveur :** La première étape est toujours de vérifier les journaux d'erreurs PHP de votre serveur. Ces journaux fournissent souvent des détails spécifiques sur ce qui n'a pas fonctionné.
-   **Désactivez d'autres modules :** Désactivez temporairement d'autres modules récemment installés ou complexes pour exclure les conflits.
-   **Version de PHP :** Assurez-vous que votre version de PHP se situe dans la plage prise en charge (PHP 7.1 - 8.5). Une version de PHP incompatible peut causer divers problèmes.
-   **Contactez le support :** Si le problème persiste, rassemblez tous les messages d'erreur et contactez le support MyPresta.eu pour obtenir de l'aide.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Vue d'ensemble de l'architecture

Le module `tinyMCE pro` fonctionne principalement en surchargeant la classe `Validate` par défaut de PrestaShop pour assurer la compatibilité avec le contenu HTML étendu généré par l'éditeur tinyMCE amélioré. Il injecte sa propre version de la bibliothèque tinyMCE et une multitude de plugins dans le back office, remplaçant ainsi l'éditeur standard. La logique principale du module réside dans `index.php`, qui gère l'installation, la désinstallation et le formulaire de configuration. Il utilise le système de hooks de PrestaShop pour charger ses ressources et initialiser l'éditeur là où c'est nécessaire.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur front-office ou back-office personnalisé. Sa fonctionnalité est principalement intégrée via le fichier de module principal (`index.php`) et en surchargeant les classes PrestaShop de base.

### 4.3 Classes et modèles de base (`classes/`)

-   **`tinymcepro/override/classes/index.php`** : Ce fichier est généralement un espace réservé vide pour empêcher l'affichage du répertoire, une pratique de sécurité courante. Il ne contient aucune définition de classe fonctionnelle.
-   **`tinymcepro/override/classes/Validate.php`** :
    -   **Objectif** : Il s'agit d'une surcharge cruciale. La classe `Validate` de PrestaShop est responsable de la désinfection et de la validation de diverses entrées, y compris le contenu HTML. La méthode `isCleanHtml()` par défaut peut être trop restrictive pour le contenu riche, supprimant des éléments HTML5, des attributs ou du JavaScript valides que l'éditeur tinyMCE étendu pourrait générer.
    -   **Logique de surcharge** : Cette surcharge modifie ou étend probablement la méthode `isCleanHtml()` (ou les méthodes de validation associées) pour autoriser une gamme plus large de HTML, d'attributs et potentiellement de scripts/styles intégrés, garantissant que le contenu généré par tinyMCE pro n'est pas supprimé ou jugé invalide par la validation de base de PrestaShop.
    -   **Impact** : Les développeurs doivent être conscients que cette surcharge modifie le comportement de validation de base. Si des règles de validation personnalisées sont en place ou si d'autres modules dépendent d'un `isCleanHtml()` strict, des conflits pourraient survenir.

### 4.4 Ressources JavaScript (`views/js/`)

Le module comprend un grand nombre de fichiers JavaScript, principalement pour la bibliothèque tinyMCE de base et ses nombreux plugins.

-   **`tinymcepro/js/accordion.js`** : Probablement un script personnalisé pour gérer la fonctionnalité d'accordéon sur le front-office, éventuellement lié au plugin tinyMCE `bootstrapaccordion`.
-   **`tinymcepro/js/alerts.js`** : Script personnalisé pour gérer les messages d'alerte, potentiellement lié à un plugin d'alerte Bootstrap.
-   **`tinymcepro/js/fancybox.js`** : Intégration de la bibliothèque Fancybox pour les lightboxes, probablement utilisée pour l'affichage d'images ou de médias dans la sortie de l'éditeur.
-   **`tinymcepro/js/readmore.js`** : Script pour implémenter la fonctionnalité « lire la suite », réduisant les longues sections de contenu.
-   **`tinymcepro/js/tinymce-cmscategory.js`** : Script d'initialisation ou de configuration spécifique pour tinyMCE lorsqu'il est utilisé dans les champs de description de CMS ou de catégorie.
-   **`tinymcepro/lib/htmlTemplatesManager/js/htmlTemplatesManager.js`** : JavaScript principal pour le plugin HTML Templates Manager, permettant la création, l'édition et l'insertion de snippets HTML prédéfinis.
-   **`tinymcepro/lib/plugins/bootstrapaccordion/plugin.js`** : Plugin tinyMCE pour insérer et gérer des accordéons de style Bootstrap.
-   **`tinymcepro/lib/plugins/codesample/plugin.js`** : Plugin tinyMCE pour insérer et mettre en évidence la syntaxe des exemples de code. Inclut `prism.css` pour le style.
-   **`tinymcepro/lib/plugins/editattributes/plugin.js`** : Plugin tinyMCE pour éditer facilement les attributs HTML des éléments sélectionnés.
-   **`tinymcepro/lib/plugins/fontawesome/langs/*.js`** : Fichiers de langue pour le plugin tinyMCE Font Awesome.
-   **`tinymcepro/lib/plugins/lineheight/index.js`, `langs/de.js`, `plugin.js`** : Plugin tinyMCE pour contrôler la hauteur de ligne du texte.
-   **`tinymcepro/lib/plugins/paragraph/*.js`** : Un plugin complexe pour gérer les styles de paragraphe et potentiellement afficher les éléments de bloc. Comprend plusieurs scripts utilitaires internes.
-   **`tinymcepro/lib/plugins/powerpaste/*.js`** : Plugin tinyMCE avancé pour nettoyer et désinfecter le contenu collé de Microsoft Word, Google Docs, etc. Comprend de nombreux fichiers de langue.
-   **`tinymcepro/lib/plugins/smileys/plugin.js`** : Plugin tinyMCE pour insérer des emoji/smileys.
-   **`tinymcepro/lib/plugins/youtube/includes/youtube.js`, `plugin.js`** : Plugin tinyMCE pour intégrer des vidéos YouTube.
-   **`tinymcepro/lib/tinymce.inc.js`** : Probablement le fichier de bibliothèque tinyMCE principal, ou un fichier de construction/configuration personnalisé pour l'éditeur.
-   **`tinymcepro/lib/tinymce_loader.js`** : Script responsable du chargement et de l'initialisation des instances de l'éditeur tinyMCE dans le back office de PrestaShop.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`tinymcepro/css/tinymcepro.css`** : Styles personnalisés généraux pour le module, potentiellement pour sa page de configuration ou les éléments du front-office.
-   **`tinymcepro/css.css`** : Une autre feuille de style générale, éventuellement pour les anciennes versions de PrestaShop ou des éléments d'interface utilisateur spécifiques.
-   **`tinymcepro/lib/editor.css`** : CSS de base pour l'éditeur tinyMCE lui-même, définissant son apparence dans le back office.
-   **`tinymcepro/lib/htmlTemplatesManager/css/htmlTemplatesManager.css`** : Styles pour l'interface du gestionnaire de modèles HTML.
-   **`tinymcepro/lib/iconset.css`** : Contient probablement des styles pour les icônes personnalisées utilisées dans l'éditeur ou le module.
-   **`tinymcepro/lib/plugins/bs_alert/assets/css/bootstrap.css`, `plugin.css`** : CSS Bootstrap et styles de plugin spécifiques pour le plugin tinyMCE Bootstrap Alert.
-   **`tinymcepro/lib/plugins/bs_images/assets/css/bootstrap.css`, `plugin.css`** : CSS Bootstrap et styles de plugin spécifiques pour le plugin tinyMCE Bootstrap Images.
-   **`tinymcepro/lib/plugins/codesample/css/prism.css`** : Feuille de style pour la coloration syntaxique utilisée par le plugin `codesample`.
-   **`tinymcepro/lib/plugins/powerpaste/css/editorcss.css`** : Styles spécifiques au plugin PowerPaste, potentiellement pour un retour visuel pendant le collage.
-   **`tinymcepro/lib/plugins/tinyplusBootstrapTools/flat-blue.css`, `res-show-blocks-style.css`** : Styles supplémentaires liés à Bootstrap ou à l'affichage des blocs, éventuellement pour des thèmes ou des outils d'éditeur spécifiques.
-   **`tinymcepro/lib/plugins/youtube/includes/youtube.css`** : Styles pour la fonctionnalité d'intégration de vidéos YouTube.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **`tinymcepro/header.tpl`** : Ce template est probablement accroché à `displayHeader` pour charger les ressources CSS et JavaScript nécessaires au module, à la fois dans le back office (pour l'éditeur lui-même) et potentiellement dans le front office (pour le contenu rendu comme les accordéons ou la fancybox).
-   **`tinymcepro/lib/htmlTemplatesManager/views/buttonManager.tpl`** : Template pour le bouton ou l'interface qui ouvre le gestionnaire de modèles HTML.
-   **`tinymcepro/lib/htmlTemplatesManager/views/createTemplateForm.tpl`** : Template de formulaire pour créer de nouveaux modèles HTML.
-   **`tinymcepro/lib/htmlTemplatesManager/views/editTemplateForm.tpl`** : Template de formulaire pour modifier des modèles HTML existants.
-   **`tinymcepro/lib/htmlTemplatesManager/views/mainForm.tpl`** : Le template d'interface principal pour le gestionnaire de modèles HTML.
-   **`tinymcepro/lib/htmlTemplatesManager/views/selectInput.tpl`** : Un template réutilisable pour un champ de sélection déroulant dans le gestionnaire de modèles.
-   **`tinymcepro/views/admin/fonts.tpl`** : Template lié à la sélection ou à l'affichage des polices, éventuellement pour l'intégration de polices personnalisées dans l'éditeur.
-   **`tinymcepro/views/admin/form.tpl`** : Le template de formulaire de configuration principal pour le module, rendu via `getContent()` dans `index.php`.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** : Ce module ne semble pas créer de tables SQL personnalisées. Ses paramètres de configuration sont stockés dans `ps_configuration` (par exemple, `PS_TINYMCEPRO_ENABLED`). Les modèles HTML créés via le `htmlTemplatesManager` pourraient être stockés dans une table personnalisée ou sérialisés dans `ps_configuration` également, bien qu'aucun fichier SQL explicite ne soit présent, suggérant une création dynamique ou un stockage de configuration.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayBackOfficeHeader` | Rendu dans la section `<head>` du back office de PrestaShop. | Injecte les fichiers CSS et JavaScript nécessaires au fonctionnement de l'éditeur tinyMCE et de ses plugins. C'est là que la bibliothèque tinyMCE principale et ses scripts d'initialisation sont chargés. |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses ressources média. | Permet au module d'ajouter ses fichiers JS/CSS spécifiques à la page d'administration actuelle, garantissant que l'éditeur tinyMCE n'est chargé que sur les pages où il est nécessaire (par exemple, édition de produit, édition de page CMS). |
| `actionGetContentEditor` | (Si hook personnalisé) | Ce hook serait utilisé pour remplacer l'instance d'éditeur par défaut par l'éditeur tinyMCE amélioré du module. |
| `displayHeader` | Rendu dans la section `<head>` du front office. | Charge potentiellement des ressources spécifiques au front office (comme `accordion.js`, `fancybox.js`, `tinymcepro.css`) si le contenu généré par l'éditeur nécessite un style ou un JavaScript spécial pour s'afficher correctement (par exemple, accordéons, lightboxes). |
| `displayRightColumn` | Rendu dans la colonne de droite du front office. | (Peu susceptible d'être utilisé directement pour la fonctionnalité de l'éditeur, mais pourrait être utilisé pour afficher du contenu *créé* par l'éditeur si le module avait un widget front-office). |
| `displayLeftColumn` | Rendu dans la colonne de gauche du front office. | (Similaire à `displayRightColumn`). |
| `displayFooter` | Rendu dans le pied de page du front office. | Pourrait être utilisé pour charger du JavaScript ou du CSS non critique pour l'affichage du front office. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et toute assistance supplémentaire concernant le module « tinyMCE pro - éditeur de texte enrichi étendu », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec l'installation, la configuration et le dépannage.
