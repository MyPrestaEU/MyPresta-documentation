---
title: "Liste de souhaits Facebook - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Liste de souhaits Facebook par MyPresta.eu."
sidebar:
  label: "Liste de souhaits Facebook - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Facebook Wishlist sur MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-wishlist.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/facebook-wishlist/)
>
> ---


# Liste de souhaits Facebook

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont généralement disponibles par défaut. Aucune exigence d'hébergement spéciale au-delà d'une configuration PrestaShop standard.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur "Configurer" à côté du module Liste de souhaits Facebook dans le Gestionnaire de modules. Cela vous mènera à l'écran de configuration principal.

#### **ID d'application Facebook**

- **Ce que fait ce paramètre :** Il s'agit d'un identifiant unique fourni par Facebook pour votre application spécifique (dans ce cas, l'intégration de votre boutique PrestaShop avec Facebook). Il indique à Facebook quelle application demande l'action de liste de souhaits.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est correctement saisi :* Le bouton "Ajouter à la liste de souhaits Facebook" fonctionnera correctement, permettant d'ajouter des produits aux chronologies Facebook.
  - *Lorsqu'il est incorrect ou vide :* Le bouton ne fonctionnera probablement pas, ou Facebook affichera une erreur, empêchant les clients d'ajouter des produits à leurs listes de souhaits.
- **Valeur recommandée :** Ce champ *doit* contenir votre ID d'application Facebook valide. Vous devrez créer une application Facebook sur le site [Facebook pour les développeurs](https://developers.facebook.com/) pour obtenir cet ID.
- **Scénario / exemple de marchand :** Vous avez créé une application Facebook pour votre boutique, et Facebook vous a donné un ID d'application comme `123456789012345`. Vous saisiriez ce numéro exact ici. Sans cela, Facebook ne saura pas quelle boutique essaie de partager du contenu.

#### **Secret d'application Facebook**

- **Ce que fait ce paramètre :** Il s'agit d'une clé secrète associée à votre ID d'application Facebook. Elle est utilisée pour une communication sécurisée entre votre boutique PrestaShop et les serveurs de Facebook. Elle aide à vérifier que les requêtes proviennent de votre application légitime.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est correctement saisi :* Une communication sécurisée est établie, et le module fonctionne comme prévu.
  - *Lorsqu'il est incorrect ou vide :* La communication avec Facebook peut échouer, entraînant des erreurs ou des fonctionnalités de liste de souhaits non fonctionnelles.
- **Valeur recommandée :** Ce champ *doit* contenir votre Secret d'application Facebook valide. Comme l'ID d'application, vous l'obtenez dans les paramètres de votre application Facebook sur le site [Facebook pour les développeurs](https://developers.facebook.com/). Gardez ce secret en sécurité et ne le partagez jamais publiquement.
- **Scénario / exemple de marchand :** Après avoir créé votre application Facebook, vous trouverez l'ID d'application et le Secret d'application dans le tableau de bord de votre application. Le secret peut ressembler à une longue chaîne de lettres et de chiffres (par exemple, `abcdef1234567890abcdef1234567890`). Saisissez-le précisément tel que fourni par Facebook.

#### **URL de la page Facebook**

- **Ce que fait ce paramètre :** Cela vous permet de lier la page Facebook officielle de votre boutique à la fonctionnalité de liste de souhaits. Lorsque les clients interagissent avec la liste de souhaits, cela peut parfois faire référence ou renvoyer à votre page Facebook principale.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est correctement saisi :* Améliore la visibilité de la marque sur Facebook et fournit un lien direct vers votre page officielle.
  - *Lorsqu'il est incorrect ou vide :* Le module fonctionnera toujours, mais vous pourriez manquer une opportunité de diriger les utilisateurs vers votre présence Facebook principale.
- **Valeur recommandée :** Saisissez l'URL complète de la page Facebook officielle de votre boutique (par exemple, `https://www.facebook.com/NomDeVotreBoutique`). Si vous n'avez pas de page officielle, vous pouvez laisser ce champ vide.
- **Scénario / exemple de marchand :** Votre boutique a une page Facebook à `https://www.facebook.com/MyPrestaEu`. Saisir cette URL ici garantit que tout partage social lié à la liste de souhaits peut potentiellement diriger les utilisateurs vers la page principale de votre marque sur Facebook.

#### **Position du bouton**

- **Ce que fait ce paramètre :** Cela contrôle l'emplacement du bouton "Ajouter à la liste de souhaits Facebook" sur vos pages produits.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur 'Page produit' :* Le bouton sera affiché de manière proéminente sur la page de détails du produit, généralement près du bouton "Ajouter au panier". C'est l'emplacement le plus courant et recommandé.
  - *Lorsqu'il est défini sur d'autres options (par exemple, 'En-tête', 'Colonnes', 'Pied de page') :* Le module pourrait tenter d'afficher le bouton dans ces zones, mais sa fonctionnalité est principalement liée à des informations produit spécifiques, ce qui fait de 'Page produit' le choix le plus logique. D'autres positions pourraient ne pas afficher le bouton ou ne pas fonctionner correctement sans un contexte produit spécifique.
- **Valeur recommandée :** **Page produit**. Cela garantit que le bouton est visible lorsque les clients consultent activement un produit qu'ils pourraient vouloir ajouter à leur liste de souhaits.
- **Scénario / exemple de marchand :** Vous voulez que les clients trouvent facilement le bouton de liste de souhaits au moment où ils envisagent d'acheter un produit. Définir cela sur 'Page produit' le place logiquement à côté d'autres actions liées à l'achat.

#### **Afficher le bouton sur la page produit**

- **Ce que fait ce paramètre :** Il s'agit d'un simple interrupteur ON/OFF pour activer ou désactiver l'affichage du bouton "Ajouter à la liste de souhaits Facebook" sur vos pages produits.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Le bouton sera visible et fonctionnel sur toutes les pages produits.
  - *Lorsqu'il est désactivé (NON) :* Le bouton sera masqué, et les clients ne pourront pas ajouter de produits à leurs listes de souhaits Facebook via votre boutique.
- **Valeur recommandée :** **OUI**. Pour utiliser la fonctionnalité principale du module, cela devrait toujours être activé.
- **Scénario / exemple de marchand :** Vous avez terminé toute la configuration et souhaitez que vos clients commencent à utiliser la fonctionnalité. Vous définiriez cela sur OUI. Si vous souhaitez temporairement masquer la fonctionnalité pour la maintenance ou une campagne, vous pourriez la définir sur NON.

#### **Afficher le bouton sur la page de catégorie**

- **Ce que fait ce paramètre :** Cela contrôle si le bouton "Ajouter à la liste de souhaits Facebook" apparaît sur les listes de produits des pages de catégorie.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Un bouton de liste de souhaits apparaîtra à côté de chaque produit sur les pages de catégorie et de liste. Cela peut être utile pour un ajout rapide à la liste de souhaits, mais pourrait encombrer la mise en page selon votre thème.
  - *Lorsqu'il est désactivé (NON) :* Le bouton n'apparaîtra que sur les pages produits individuelles, gardant les pages de catégorie plus propres.
- **Valeur recommandée :** **NON**. Bien que potentiellement utile, l'affichage du bouton sur les pages de catégorie peut parfois entraîner une expérience utilisateur moins optimale ou un encombrement visuel. Il est généralement plus efficace sur la page produit dédiée.
- **Scénario / exemple de marchand :** Vous avez une conception de page de catégorie très propre et souhaitez minimiser les distractions. Vous définiriez cela sur NON, garantissant que l'action de liste de souhaits n'est disponible que lorsqu'un client est concentré sur un seul produit.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | ID d'application Facebook | Votre ID d'application Facebook | Identifiant unique pour l'intégration Facebook de votre boutique. **Critique pour la fonctionnalité.** |
| Configuration du module | Secret d'application Facebook | Votre Secret d'application Facebook | Clé sécurisée pour la communication avec Facebook. **Critique pour la fonctionnalité.** |
| Configuration du module | URL de la page Facebook | `https://www.facebook.com/NomDeVotreBoutique` (si applicable) | Lien vers votre page Facebook officielle, améliorant la visibilité de la marque. |
| Configuration du module | Position du bouton | Page produit | Détermine l'emplacement du bouton de liste de souhaits. **Page produit est recommandé.** |
| Configuration du module | Afficher le bouton sur la page produit | OUI | Active/désactive le bouton sur les pages produits individuelles. **Recommandé : OUI.** |
| Configuration du module | Afficher le bouton sur la page de catégorie | NON | Active/désactive le bouton sur les listes de produits des pages de catégorie. **Recommandé : NON.** |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Le bouton "Ajouter à la liste de souhaits Facebook" n'apparaît pas sur mes pages produits.**
R :

- **Vérifier l'état du module :** Assurez-vous que le module est installé et activé dans **Modules > Gestionnaire de modules**.
- **Paramètres de configuration :** Accédez à la page de configuration du module et vérifiez que "Afficher le bouton sur la page produit" est défini sur **OUI**.
- **ID/Secret d'application Facebook :** Vérifiez à nouveau que votre ID d'application Facebook et votre Secret d'application sont correctement saisis. Des identifiants incorrects empêcheront le bouton de se charger ou de fonctionner.
- **Compatibilité du thème :** Certains thèmes très personnalisés peuvent nécessiter des ajustements mineurs. Si le bouton n'apparaît toujours pas, essayez de passer temporairement au thème PrestaShop par défaut (Classic) pour exclure un conflit de thème. S'il apparaît sur Classic, votre développeur de thème pourrait avoir besoin de l'intégrer.
- **Vider le cache :** Videz toujours le cache de votre PrestaShop (**Paramètres avancés > Performances**) et le cache de votre navigateur après avoir effectué des modifications de configuration.

**Q2 : Le bouton apparaît, mais rien ne se passe lorsque je clique dessus, ou j'obtiens une erreur Facebook.**
R :

- **ID/Secret d'application Facebook :** Cela est presque toujours dû à un ID d'application Facebook ou un Secret d'application incorrect ou manquant. Revoyez les paramètres de votre application Facebook pour les développeurs et assurez-vous que les valeurs sont copiées précisément.
- **Paramètres de l'application Facebook :** Sur la plateforme Facebook pour les développeurs, assurez-vous que votre application est "En ligne" (pas en mode développement) et que la plateforme "Site Web" est ajoutée avec l'URL de votre boutique correctement configurée.
- **Liste blanche de domaines :** Dans les paramètres de votre application Facebook, sous "Paramètres > Basique", assurez-vous que le domaine de votre site Web est répertorié dans le champ "Domaines d'application".
- **Balises Open Graph :** Le module s'appuie sur les balises méta Open Graph par défaut de PrestaShop pour les informations sur les produits. Assurez-vous que votre boutique PrestaShop les génère correctement (vous pouvez vérifier le code source de votre page produit pour les balises `<meta property="og:..."`).

**Q3 : Comment obtenir un ID d'application Facebook et un Secret d'application ?**
R :

1. Allez sur [Facebook pour les développeurs](https://developers.facebook.com/) et connectez-vous avec votre compte Facebook.
2. Cliquez sur "Mes applications" > "Créer une application".
3. Choisissez le type d'application (par exemple, "Consommateur" ou "Entreprise") et suivez les invites pour nommer votre application.
4. Une fois créée, naviguez vers "Paramètres > Basique" dans le tableau de bord de votre nouvelle application.
5. Vous y trouverez votre **ID d'application** et votre **Secret d'application**.
6. Assurez-vous d'ajouter le domaine de votre site Web (par exemple, `votreboutique.com`) au champ "Domaines d'application" et enregistrez les modifications.
7. Ajoutez une plateforme "Site Web" à votre application et saisissez l'URL de votre site.
8. Enfin, assurez-vous que votre application est définie en mode "En ligne" (il y a généralement un interrupteur en haut du tableau de bord).

**Q4 : Ce module ralentira-t-il mon site Web ?**
R : Le module lui-même est très léger. L'interaction principale est un petit bouton et une pop-up hébergée par Facebook, qui charge le contenu directement depuis les serveurs de Facebook. Tout ralentissement perçu est plus susceptible d'être lié aux propres temps de chargement de Facebook ou à des problèmes généraux de performance du site Web plutôt qu'au module lui-même.

**Q5 : Puis-je personnaliser l'apparence du bouton ?**
R : Le module utilise généralement le style de bouton Facebook standard ou s'intègre aux styles de bouton existants de votre thème. Bien qu'il n'y ait pas de paramètre direct dans le module pour modifier son apparence, un développeur Web peut le personnaliser à l'aide de CSS en ciblant les classes ou ID CSS spécifiques de l'élément du bouton.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module Liste de souhaits Facebook (`facebook-wishlist`) est un module PrestaShop simple principalement conçu pour injecter la fonctionnalité "Ajouter à la liste de souhaits" basée sur Open Graph dans le front-office. Il exploite le système de hooks de PrestaShop pour afficher son bouton sur les pages produits et s'appuie sur le SDK JavaScript de Facebook et le protocole Open Graph pour sa fonctionnalité principale. La configuration du module est gérée via la méthode standard `getContent()` dans le fichier principal du module, stockant les paramètres dans `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs front-office ou back-office personnalisés. Toute la logique est encapsulée dans le fichier principal du module et sa configuration.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée ou `ObjectModel`. Toute la configuration est gérée via `Configuration::get()` et `Configuration::updateValue()`.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut pas de fichiers JavaScript personnalisés. Il s'appuie sur le SDK JavaScript de Facebook, qui est généralement chargé de manière asynchrone et géré par Facebook lui-même une fois que les balises méta Open Graph et l'ID d'application corrects sont présents.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut pas de fichiers CSS personnalisés. L'apparence du bouton est soit gérée par le style par défaut de Facebook pour ses plugins sociaux, soit hérite des styles du thème PrestaShop actif.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Ce module ne contient pas de répertoire `views/templates`. Le code HTML du bouton est probablement généré directement dans les méthodes de hook du fichier principal du module.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :
  Ce module ne crée aucune table de base de données personnalisée. Tous les paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide de clés telles que `FACEBOOK_WISHLIST_APP_ID`, `FACEBOOK_WISHLIST_APP_SECRET`, `FACEBOOK_WISHLIST_PAGE_URL`, `FACEBOOK_WISHLIST_BUTTON_POSITION`, `FACEBOOK_WISHLIST_SHOW_PRODUCT_PAGE` et `FACEBOOK_WISHLIST_SHOW_CATEGORY_PAGE`.
- **Table des hooks enregistrés** :
  Le module enregistre et utilise les hooks PrestaShop suivants :

  | Nom du hook | Moment d'exécution | Objectif technique |
  | --- | --- | --- |
  | `displayHeader` | Dans la section `<head>` de chaque page. | Utilisé pour injecter le code d'initialisation du SDK JavaScript de Facebook et les balises méta Open Graph (si elles ne sont pas déjà présentes par le cœur de PrestaShop). Ceci est crucial pour que Facebook reconnaisse votre site et votre application. |
  | `displayProductButtons` | Sur la page produit, généralement près du bouton "Ajouter au panier". | Affiche le bouton "Ajouter à la liste de souhaits Facebook". C'est le hook principal pour l'affichage front-office du module. |
  | `displayProductListFunctionalButtons` | Sur les pages de catégorie/liste, à côté de chaque produit. | Affiche le bouton "Ajouter à la liste de souhaits Facebook" pour les produits dans les listes, si activé dans la configuration. |
  | `displayFooter` | Dans le pied de page de chaque page. | Potentiellement utilisé pour le chargement de scripts supplémentaires ou le placement de bouton de secours, bien que `displayProductButtons` soit le principal. |
  | `displayLeftColumn` | Dans la colonne de gauche des pages. | Position alternative pour le bouton, si configuré. |
  | `displayRightColumn` | Dans la colonne de droite des pages. | Position alternative pour le bouton, si configuré. |

  La fonctionnalité principale du module repose sur le hook `displayHeader` pour s'assurer que le SDK Facebook est chargé et sur le hook `displayProductButtons` (ou `displayProductListFunctionalButtons`) pour afficher le bouton interactif. Le bouton lui-même, lorsqu'il est cliqué, déclenche l'action Open Graph `og:product:wishlist` de Facebook, qui nécessite que des balises méta Open Graph spécifiques (comme `og:title`, `og:description`, `og:image`, `og:url`, `og:type=product`) soient présentes dans le code HTML de la page produit. PrestaShop génère généralement ces balises par défaut.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module Liste de souhaits Facebook, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
