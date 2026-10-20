---
title: "Block Search Pro - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Block Search Pro par MyPresta.eu."
sidebar:
  label: "Block Search Pro - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Block Search Pro sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/block-search-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/block-search-pro/)
>
> ---


# Block Search Pro

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement nécessaire au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Block Search Pro)

C'est l'écran de configuration principal où vous contrôlez le comportement et l'apparence du module Block Search Pro sur votre boutique.

#### 2.1.1 Paramètres généraux

**1. Activer la recherche AJAX**

- **Ce que fait ce paramètre :** Il contrôle si les résultats de recherche apparaissent instantanément au fur et à mesure que le client tape (AJAX) ou s'il doit appuyer sur Entrée/cliquer sur le bouton de recherche pour voir les résultats.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'activé (OUI) :* Au fur et à mesure que les clients tapent dans la barre de recherche, une liste déroulante de produits correspondants apparaîtra en temps réel sous le champ de recherche. Cela fournit un retour immédiat et accélère le processus de recherche.
  - *Lorsqu'désactivé (NON) :* Les clients doivent taper leur requête de recherche complète, puis appuyer sur Entrée ou cliquer sur le bouton de recherche pour être redirigés vers la page de résultats de recherche.
- **Valeur recommandée :** OUI. Cela améliore considérablement l'expérience utilisateur en offrant une gratification instantanée et en réduisant les étapes pour trouver un produit.
- **Scénario/exemple marchand :** Un client tape "robe" et voit immédiatement apparaître des suggestions comme "Robe de soirée rouge", "Robe longue d'été" et "Robe de cocktail noire", ce qui lui permet de cliquer directement sur une page produit sans attendre.

**2. Recherche instantanée**

- **Ce que fait ce paramètre :** Similaire à la recherche AJAX, cela fait spécifiquement référence à l'affichage "instantané" des résultats de recherche sur la page de résultats de recherche elle-même, se mettant à jour au fur et à mesure que l'utilisateur affine sa requête. (Note : Dans de nombreuses versions modernes de PrestaShop, la "recherche AJAX" englobe souvent le menu déroulant instantané, tandis que la "recherche instantanée" peut faire référence au comportement sur la page de résultats de recherche réelle).
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'activé (OUI) :* Si un client est sur la page de résultats de recherche et modifie sa requête de recherche dans la barre de recherche, les résultats sur cette page se mettront à jour instantanément sans rechargement complet de la page.
  - *Lorsqu'désactivé (NON) :* Le client devrait soumettre à nouveau la requête de recherche modifiée pour que la page de résultats se rafraîchisse.
- **Valeur recommandée :** OUI. Cela offre une expérience de recherche plus dynamique et réactive.
- **Scénario/exemple marchand :** Un client recherche "chaussures", arrive sur la page de résultats de recherche, puis tape "rouge" dans la barre de recherche de cette page. Avec la recherche instantanée, les résultats filtrent immédiatement pour n'afficher que les chaussures rouges.

**3. Autoriser la soumission de la recherche avec un champ de mot-clé vide**

- **Ce que fait ce paramètre :** Détermine si un client peut cliquer sur le bouton de recherche ou appuyer sur Entrée sans taper de mots-clés.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'activé (OUI) :* Si un client clique sur rechercher avec une saisie vide, il sera dirigé vers la page générale des résultats de recherche, qui peut afficher tous les produits ou un message par défaut selon votre thème. Cela peut parfois être utilisé pour parcourir tous les produits.
  - *Lorsqu'désactivé (NON) :* Le bouton de recherche sera inactif ou affichera un message d'erreur si le champ de saisie est vide, obligeant le client à taper un mot-clé avant de rechercher.
- **Valeur recommandée :** NON. Généralement, il est préférable de guider les clients à saisir une requête pour éviter toute confusion ou des pages de résultats de recherche vides.
- **Scénario/exemple marchand :** Si un client clique accidentellement sur rechercher sans taper, la désactivation de cette option l'empêche d'atterrir sur une page vide potentiellement déroutante.

**4. Longueur minimale du mot (en caractères)**

- **Ce que fait ce paramètre :** Définit le nombre minimum de caractères qu'un client doit taper avant que la fonction de recherche (y compris la recherche AJAX/instantanée) ne commence à chercher des résultats.
- **Effet de la modification de ce paramètre :**
  - *Défini à 3 :* Les clients doivent taper au moins trois caractères (par exemple, "rouge") avant que des suggestions de recherche n'apparaissent ou qu'une recherche puisse être soumise.
  - *Défini à 1 :* Même un seul caractère (par exemple, "a") déclenchera la recherche.
- **Valeur recommandée :** 3. Cela équilibre la réactivité et la pertinence. Une valeur trop basse (par exemple, 1-2 caractères) peut générer trop de suggestions non pertinentes, tandis qu'une valeur trop élevée peut frustrer les utilisateurs.
- **Scénario/exemple marchand :** Si défini à 3, taper "ch" n'affichera pas de résultats, mais taper "cha" commencera à afficher des suggestions pour "chaussures", "chapeaux", etc.

#### 2.1.2 Options de filtrage de recherche

**5. Sélectionner les catégories**

- **Ce que fait ce paramètre :** Vous permet de restreindre la recherche à des catégories de produits spécifiques uniquement. Le module ne renverra des résultats que des catégories que vous sélectionnez ici.
- **Effet de la modification de ce paramètre :**
  - *Lorsque des catégories spécifiques sont sélectionnées :* La recherche ne cherchera des produits qu'au sein de ces catégories choisies. Les produits des catégories non sélectionnées n'apparaîtront pas dans les résultats de recherche, même s'ils correspondent au mot-clé.
  - *Lorsqu'aucune catégorie n'est sélectionnée :* La recherche par défaut s'effectuera dans toutes les catégories de votre boutique.
- **Valeur recommandée :** Sélectionnez des catégories si vous souhaitez guider les clients vers des types de produits spécifiques, ou laissez vide si vous souhaitez une recherche large.
- **Scénario/exemple marchand :** Si vous vendez à la fois des vêtements et des appareils électroniques, mais que vous souhaitez que la barre de recherche dans l'en-tête ne trouve que des vêtements, vous ne sélectionneriez que vos catégories de vêtements ici.

**6. Rechercher dans les sous-catégories**

- **Ce que fait ce paramètre :** Cette option fonctionne conjointement avec "Sélectionner les catégories". Elle détermine si la recherche doit également inclure les produits des sous-catégories des catégories parentes sélectionnées.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'activé (OUI) :* Si vous sélectionnez "Électronique" comme catégorie, la recherche cherchera également dans "Ordinateurs portables", "Smartphones" et toute autre sous-catégorie d'"Électronique".
  - *Lorsqu'désactivé (NON) :* La recherche ne cherchera que les produits directement assignés aux catégories parentes sélectionnées, ignorant leurs sous-catégories.
- **Valeur recommandée :** OUI. La plupart des marchands souhaitent que les recherches soient complètes au sein d'une arborescence de catégories choisie.
- **Scénario/exemple marchand :** Si vous sélectionnez "Vêtements" et activez "Rechercher dans les sous-catégories", une recherche de "chemise" trouvera des chemises dans "T-shirts pour hommes", "Blouses pour femmes", etc.

**7. Fabricants**

- **Ce que fait ce paramètre :** Vous permet de restreindre la recherche aux produits de fabricants spécifiques uniquement.
- **Effet de la modification de ce paramètre :**
  - *Lorsque des fabricants spécifiques sont sélectionnés :* La recherche ne renverra que les produits fabriqués par les fabricants choisis. Les produits des fabricants non sélectionnés n'apparaîtront pas.
  - *Lorsqu'aucun fabricant n'est sélectionné :* La recherche par défaut s'effectuera dans tous les fabricants de votre boutique.
- **Valeur recommandée :** Sélectionnez des fabricants si vous souhaitez offrir une recherche spécifique à une marque, ou laissez vide pour une recherche générale.
- **Scénario/exemple marchand :** Si vous avez un bloc de recherche dédié aux "Marques Premium", vous pourriez sélectionner uniquement les fabricants haut de gamme ici.

#### 2.1.3 Paramètres d'affichage

**8. Taille du bloc de recherche**

- **Ce que fait ce paramètre :** Contrôle la largeur visuelle du champ de saisie de recherche en pixels.
- **Effet de la modification de ce paramètre :**
  - *Défini à 280px :* La barre de recherche aura une largeur de 280 pixels.
  - *Défini à 100% (ou laisser vide pour la détection automatique) :* La barre de recherche s'adaptera à l'espace disponible, remplissant souvent son conteneur.
- **Valeur recommandée :** Laissez vide pour la détection automatique ou définissez une valeur en pourcentage (par exemple, 100%) pour assurer la réactivité. Si vous avez besoin d'une largeur fixe pour des raisons de conception, spécifiez une valeur en pixels.
- **Scénario/exemple marchand :** Si votre thème a un en-tête très étroit, vous devrez peut-être ajuster cela pour vous assurer que la barre de recherche s'adapte sans casser la mise en page. Pour la plupart des thèmes modernes, il est préférable de laisser le thème gérer la largeur.

#### 2.1.4 Autres paramètres

**9. Paramètres de mise à jour en direct MyPresta.eu (`mypresta_updates`, `update_`, `updatev_`)**

- **Ce que fait ce paramètre :** Ce sont des paramètres internes liés au système de mise à jour des modules de MyPresta.eu. Ils permettent au module de vérifier et de vous informer des nouvelles versions.
- **Effet de la modification de ce paramètre :** Ceux-ci ne sont pas configurables par l'utilisateur directement via l'interface mais sont gérés par le module lui-même. Assurer que votre boutique a un accès Internet sortant permet à ces vérifications de fonctionner.
- **Valeur recommandée :** Ceux-ci sont internes et ne doivent pas être modifiés manuellement.
- **Scénario/exemple marchand :** Vous recevrez une notification dans votre back office PrestaShop si une nouvelle version de Block Search Pro est disponible, vous assurant de pouvoir maintenir votre module à jour avec les dernières fonctionnalités et correctifs de sécurité.

**10. `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`**

- **Ce que fait ce paramètre :** Ce sont des variables de configuration PrestaShop standard liées à la langue par défaut de votre boutique et si les employés peuvent changer la langue des formulaires dans le back office. Le module les utilise pour s'assurer qu'il s'affiche correctement dans la langue active du back office.
- **Effet de la modification de ce paramètre :** Ce sont des paramètres PrestaShop globaux et ne sont pas directement contrôlés par Block Search Pro. Le module les lit simplement pour adapter son affichage.
- **Valeur recommandée :** Géré par votre configuration générale de PrestaShop.
- **Scénario/exemple marchand :** Si votre back office est défini en français, les étiquettes de configuration du module apparaîtront en français (si des traductions sont disponibles).

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer la recherche AJAX | OUI | Affiche des suggestions de produits instantanées au fur et à mesure que le client tape. |
| Configuration du module | Recherche instantanée | OUI | Met à jour la page de résultats de recherche instantanément lors du changement de requête. |
| Configuration du module | Autoriser la soumission de la recherche avec un champ de mot-clé vide | NON | Empêche la recherche avec un champ de saisie vide. |
| Configuration du module | Longueur minimale du mot (en caractères) | 3 | Nombre minimum de caractères requis pour déclencher la recherche. |
| Configuration du module | Sélectionner les catégories | Laisser vide (recherche tout) | Restreint la recherche aux catégories choisies. |
| Configuration du module | Rechercher dans les sous-catégories | OUI | Inclut les sous-catégories lorsque les catégories parentes sont sélectionnées. |
| Configuration du module | Fabricants | Laisser vide (recherche tout) | Restreint la recherche aux fabricants choisis. |
| Configuration du module | Taille du bloc de recherche | Laisser vide (détection automatique) | Largeur visuelle du champ de saisie de recherche. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Mes résultats de recherche n'affichent pas de produits dont je sais qu'ils existent. Qu'est-ce qui ne va pas ?**
R1 : Vérifiez vos paramètres "Sélectionner les catégories" et "Fabricants" dans la configuration du module. Si vous avez restreint la recherche à certaines catégories ou fabricants, les produits en dehors de ces sélections n'apparaîtront pas. Assurez-vous également que vos produits sont actifs et visibles dans les catégories sélectionnées.

**Q2 : La recherche instantanée (AJAX) ne fonctionne pas, ou les suggestions déroulantes n'apparaissent pas.**
R2 :
\* **Activer la recherche AJAX :** Assurez-vous que "Activer la recherche AJAX" est défini sur OUI dans la configuration du module.
\* **Longueur minimale du mot :** Vérifiez "Longueur minimale du mot". Si elle est trop élevée, les suggestions n'apparaîtront pas tant que suffisamment de caractères n'auront pas été tapés.
\* **Vider le cache :** Allez dans **Paramètres avancés > Performances** et videz le cache de votre PrestaShop (cache Smarty, cache du système de fichiers).
\* **Conflits de thème :** Parfois, des thèmes personnalisés ou d'autres modules peuvent entrer en conflit avec la fonctionnalité AJAX. Désactivez temporairement d'autres modules ou passez au thème PrestaShop par défaut pour diagnostiquer.
\* **Erreurs JavaScript :** Ouvrez la console de développement de votre navigateur (F12) et vérifiez les erreurs JavaScript. Si vous voyez des erreurs, contactez le support MyPresta.eu.

**Q3 : Le bloc de recherche a l'air étrange ou ne correspond pas à mon thème.**
R3 :
\* **Taille du bloc de recherche :** Ajustez le paramètre "Taille du bloc de recherche" dans la configuration du module. Essayez de le laisser vide pour la détection automatique ou de le définir sur un pourcentage (par exemple, 100%).
\* **Conflits CSS :** Le CSS de votre thème pourrait remplacer les styles du module. Cela nécessite généralement qu'un webmaster inspecte le CSS.
\* **Placement du hook :** Assurez-vous que le module est accroché à une position appropriée (par exemple, `displayTop`) qui dispose de suffisamment d'espace dans votre thème. Vous pouvez gérer les positions des modules sous **Design > Positions**.

**Q4 : Comment traduire le texte du bloc de recherche (par exemple, "Rechercher dans notre catalogue") ?**
R4 :
\* Allez dans **International > Traductions** dans votre back office PrestaShop.
\* Sélectionnez "Traductions des modules installés", choisissez votre thème, puis sélectionnez votre langue.
\* Trouvez le module "Block Search Pro" dans la liste et vous pourrez y modifier les chaînes de texte.

**Q5 : Je souhaite placer le bloc de recherche à un autre endroit de mon site.**
R5 :
\* Naviguez vers **Design > Positions** (ou **Modules > Positions** dans les anciennes versions de PS).
\* Trouvez le module "Block Search Pro" dans la liste des modules.
\* Vous pouvez "transplanter" (accrocher) le module à différents hooks disponibles comme `displayHeader`, `displayTop`, `displayLeftColumn`, `displayRightColumn` ou `displayNav`. Faites glisser et déposez pour changer l'ordre au sein d'un hook.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé du module Block Search Pro pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module Block Search Pro étend la fonctionnalité de recherche principale de PrestaShop en surchargeant la classe `Search`, ce qui lui permet d'injecter une logique de filtrage personnalisée (catégories, fabricants) dans la requête de recherche. Il utilise les modèles MVC PrestaShop standard pour son affichage front-office (hooks, templates) et sa configuration back-office (méthode `getContent()` dans le fichier principal du module). La fonctionnalité AJAX est gérée via un fichier JavaScript dédié qui interagit avec le mécanisme de recherche principal de PrestaShop.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit pas de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Sa fonctionnalité front-office est principalement gérée par la classe `Search` surchargée et son affichage via les hooks du module. La configuration back-office est gérée directement dans la méthode `getContent()` du fichier de module `blocksearchpro.php`.

### 4.3 Classes et modèles de base (`classes/`)

- **`blocksearchpro/override/classes/index.php`** :

  - Il s'agit d'un fichier `index.php` vide standard, généralement placé dans les répertoires pour empêcher la liste des répertoires. Il n'a aucun impact fonctionnel sur la logique du module.
- **`blocksearchpro/override/classes/Search.php`** :

  - **Nom de la classe** : `Search` (surcharge la classe `Search` de base)
  - **Classe parente** : `SearchCore`
  - **Responsabilité** : C'est le fichier le plus critique. Il surcharge la classe `Search` par défaut de PrestaShop, modifiant spécifiquement la méthode `find()` (ou des méthodes similaires liées à la recherche) pour incorporer la logique de filtrage personnalisée du module.
    - Il lit les valeurs de configuration (`bsp_cat_exc`, `bsp_subcat`, `bsp_cat`, `bsp_man`) de `ps_configuration`.
    - Il modifie la requête SQL utilisée pour la recherche de produits afin d'inclure des clauses `WHERE` qui filtrent par catégories et/ou fabricants sélectionnés.
    - Il garantit que la recherche respecte le paramètre "Rechercher dans les sous-catégories" lorsque des filtres de catégorie sont appliqués.
    - Cette surcharge est ce qui permet au module d'injecter ses capacités de filtrage directement dans le mécanisme de recherche principal de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

- **`blocksearchpro/blocksearchpro.js`** :
  - **Portée** : Front-office.
  - **Responsabilité** : Ce script améliore l'expérience utilisateur pour le bloc de recherche.
    - Il lie probablement des écouteurs d'événements au champ de saisie de recherche (par exemple, `keyup`, `focus`, `blur`).
    - Il gère les requêtes AJAX pour les suggestions de recherche instantanée, envoyant la valeur de saisie actuelle au point de terminaison AJAX de recherche principal de PrestaShop.
    - Il traite la réponse JSON de l'appel AJAX et remplit dynamiquement la liste déroulante des suggestions de produits sous la barre de recherche.
    - Il gère l'affichage et la masquage de la liste de suggestions, la navigation au clavier au sein des suggestions et les événements de clic sur les suggestions pour rediriger vers les pages de produits.
    - Il peut également gérer la logique "Autoriser la soumission de la recherche avec un champ de mot-clé vide" côté client.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`blocksearchpro/blocksearchpro.css`** :
  - **Portée** : Style client front-office.
  - **Principaux composants et conteneurs d'interface utilisateur qu'il stylise** :
    - Le champ de saisie de recherche lui-même (`#search_query_top`, `.search_query`).
    - Le bouton de recherche (`#search_button`, `.button-search`).
    - Le conteneur pour les suggestions de recherche AJAX (`.ac_results`, `.block_search_pro_results`).
    - Les éléments de suggestion individuels dans le menu déroulant.
    - Assure la réactivité pour différentes tailles d'écran.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger** :
    - `.block_search_pro` (conteneur principal)
    - `.search_query` (champ de saisie)
    - `.button-search` (bouton de soumission)
    - `.ac_results` (conteneur de résultats AJAX)
    - `.ac_odd`, `.ac_even`, `.ac_over` (style pour les éléments de suggestion et les états de survol)
    - Les développeurs peuvent surcharger ces styles dans le fichier `custom.css` de leur thème ou en créant un thème enfant.

### 4.6 Structure du template Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :
  - **`blocksearchpro/blocksearchpro-top.tpl`** :
    - **Hook** : `displayTop`, `displayNav` (et potentiellement `displayHeader` selon le thème).
    - **Objectif** : Rend le champ de saisie de recherche et le bouton, généralement pour la barre de recherche de l'en-tête principal. Il inclut la structure HTML nécessaire pour le formulaire de recherche et le conteneur des résultats AJAX.
  - **`blocksearchpro/blocksearchpro.tpl`** :
    - **Hook** : `displayLeftColumn`, `displayRightColumn`.
    - **Objectif** : Rend un bloc de recherche pour les colonnes latérales. Ce template peut avoir une mise en page ou un style légèrement différent par rapport à la barre de recherche supérieure, optimisé pour des espaces de colonne plus étroits. Il inclut également le formulaire de recherche et le conteneur de résultats AJAX.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Ce module ne crée pas de tables SQL personnalisées.
  - Il stocke ses paramètres de configuration dans la table `ps_configuration` standard de PrestaShop.
  - Clés de configuration utilisées : `mypresta_updates`, `update_`, `updatev_`, `PS_SEARCH_AJAX`, `bsp_cat_exc`, `PS_INSTANT_SEARCH`, `bsp_empty`, `PS_SEARCH_MINWORDLEN`, `bsp_subcat`, `bsp_cat`, `bsp_man`, `bsp_size`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Injecte les actifs CSS (`blocksearchpro.css`) et JavaScript (`blocksearchpro.js`) pour la fonctionnalité front-office. |
| `displayTop` | Généralement dans la zone d'en-tête principale de la boutique. | Rend le bloc de recherche à l'aide de `blocksearchpro-top.tpl`. |
| `displayNav` | Souvent dans la barre de navigation tout en haut (au-dessus de `displayTop`). | Rend le bloc de recherche à l'aide de `blocksearchpro-top.tpl`. |
| `displayLeftColumn` | Dans la barre latérale gauche des pages qui en ont une. | Rend le bloc de recherche à l'aide de `blocksearchpro.tpl`. |
| `displayRightColumn` | Dans la barre latérale droite des pages qui en ont une. | Rend le bloc de recherche à l'aide de `blocksearchpro.tpl`. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | (Non directement utilisé par ce module pour sa fonctionnalité de recherche principale, mais un hook courant pour d'autres modules. Aucune action spécifique ici pour Block Search Pro.) |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et une assistance supplémentaire avec le module Block Search Pro, veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est prête à vous aider pour toute question ou problème que vous pourriez rencontrer.
