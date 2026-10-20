---
title: "Actualités de la page d'accueil - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Actualités de la page d'accueil par MyPresta.eu."
sidebar:
  label: "Actualités de la page d'accueil - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Homepage news sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-news.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/homepage-news/)
>
> ---


# Actualités de la page d'accueil

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont suffisantes pour ce module.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module « Actualités de la page d'accueil », où vous contrôlez la façon dont vos articles d'actualité sont affichés sur la page d'accueil.

#### **Sélectionner la catégorie de pages CMS**

- **Ce que fait ce paramètre :** Ce menu déroulant vous permet de choisir la catégorie CMS spécifique qui sera utilisée comme source pour vos actualités de la page d'accueil. Seules les pages CMS appartenant à cette catégorie sélectionnée seront prises en compte pour l'affichage par le module.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une catégorie est sélectionnée :* Le module récupérera et affichera les articles d'actualité uniquement à partir des pages CMS de cette catégorie.
  - *Lorsqu'aucune catégorie n'est sélectionnée (ou une catégorie inappropriée) :* Le module pourrait ne pas afficher d'actualités, ou il pourrait afficher des pages que vous n'aviez pas l'intention d'être des articles d'actualité.
- **Valeur recommandée :** Sélectionnez la catégorie CMS que vous avez spécifiquement créée ou désignée pour vos articles d'actualité (par exemple, « Actualités », « Blog », « Mises à jour »).
- **Scénario / exemple de marchand :** Vous avez créé une catégorie CMS appelée « Actualités de l'entreprise » et y avez ajouté plusieurs pages CMS, telles que « Lancement d'un nouveau produit », « Vente d'été annoncée » et « Horaires d'ouverture des fêtes ». En sélectionnant « Actualités de l'entreprise » ici, seules ces pages apparaîtront comme actualités sur votre page d'accueil.

#### **Afficher le contenu complet de la dernière page CMS**

- **Ce que fait ce paramètre :** Ce commutateur détermine si le tout dernier article d'actualité (page CMS) de votre catégorie sélectionnée sera affiché avec son contenu complet directement sur la page d'accueil.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Le contenu complet de l'article d'actualité le plus récent sera visible sur votre page d'accueil, fournissant des informations immédiates sans nécessiter de clic.
  - *Lorsqu'il est désactivé (NON) :* Seuls le titre, la miniature et une courte description (si configurée) du dernier article d'actualité seront affichés, de manière similaire aux autres miniatures. Les clients devront cliquer pour lire le contenu complet.
- **Valeur recommandée :** « OUI » si vous souhaitez mettre en évidence vos actualités les plus importantes immédiatement ; « NON » si vous préférez une section d'actualités plus compacte où tous les articles nécessitent un clic.
- **Scénario / exemple de marchand :** Vous avez une annonce majeure, comme l'ouverture d'une nouvelle boutique. L'activation de cette option garantit que les clients voient tous les détails immédiatement. Si vous préférez une page d'accueil plus propre, vous pouvez la désactiver et n'afficher que des extraits.

#### **Afficher les miniatures des pages CMS**

- **Ce que fait ce paramètre :** Ce commutateur contrôle si des versions plus petites et résumées (miniatures) de vos articles d'actualité sont affichées sur la page d'accueil. Ces miniatures comprennent généralement un titre, une petite image et une courte description.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Le module affichera une série de blocs d'actualités miniatures, chacun représentant une page CMS récente de votre catégorie sélectionnée.
  - *Lorsqu'il est désactivé (NON) :* Aucune miniature ne sera affichée. Si « Afficher le contenu complet de la dernière page CMS » est également désactivé, aucune actualité n'apparaîtra du tout.
- **Valeur recommandée :** « OUI » pour fournir un aperçu de plusieurs articles d'actualité et encourager l'exploration.
- **Scénario / exemple de marchand :** Vous souhaitez afficher les 3 à 5 derniers articles d'actualité pour donner aux clients un aperçu rapide des mises à jour récentes. L'activation des miniatures permet d'y parvenir.

#### **Nombre de miniatures à afficher**

- **Ce que fait ce paramètre :** Si « Afficher les miniatures des pages CMS » est activé, ce champ de saisie détermine combien des miniatures d'articles d'actualité les plus récentes seront affichées sur votre page d'accueil.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur un nombre plus élevé (par exemple, 5) :* Plus de miniatures d'articles d'actualité seront visibles, offrant un aperçu plus large.
  - *Lorsqu'il est défini sur un nombre plus faible (par exemple, 2) :* Moins de miniatures seront affichées, rendant la section d'actualités plus concise.
- **Valeur recommandée :** 3 à 5, selon la mise en page de votre page d'accueil et l'espace que vous souhaitez consacrer aux actualités.
- **Scénario / exemple de marchand :** Vous avez beaucoup d'actualités mais souhaitez garder votre page d'accueil propre. Le fait de le définir sur « 3 » garantit que seuls les trois articles les plus récents sont mis en évidence.

#### **Nombre de caractères utilisés dans la description des miniatures**

- **Ce que fait ce paramètre :** Ce champ de saisie contrôle la longueur de la courte description (extrait) affichée dans chaque miniature d'actualité.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur un nombre plus élevé (par exemple, 200) :* Les descriptions dans les miniatures seront plus longues, fournissant plus de contexte.
  - *Lorsqu'il est défini sur un nombre plus faible (par exemple, 50) :* Les descriptions seront plus courtes, rendant les miniatures plus compactes.
- **Valeur recommandée :** 100 à 150 caractères, suffisamment pour donner un bon résumé sans surcharger la miniature.
- **Scénario / exemple de marchand :** Vous souhaitez donner aux clients juste assez d'informations dans la miniature pour piquer leur intérêt. Le fait de le définir sur « 120 » garantit un extrait concis mais informatif.

#### **Style des miniatures**

- **Ce que fait ce paramètre :** Cette option (probablement un menu déroulant ou des boutons radio) vous permet de choisir la mise en page visuelle ou le style de présentation des miniatures d'actualité sur votre page d'accueil. Les styles disponibles peuvent inclure des options telles qu'une grille, une liste ou un carrousel.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur « Grille » :* Les miniatures peuvent apparaître en lignes et en colonnes, adaptées à l'affichage compact de plusieurs éléments.
  - *Lorsqu'il est défini sur « Liste » :* Les miniatures peuvent apparaître les unes en dessous des autres, ce qui est bon pour des descriptions plus détaillées.
  - *Lorsqu'il est défini sur « Carrousel » :* Les miniatures peuvent glisser horizontalement, économisant de l'espace et permettant aux utilisateurs de parcourir plus d'éléments.
- **Valeur recommandée :** Expérimentez avec les styles disponibles pour voir lequel correspond le mieux au design de votre thème et à l'esthétique souhaitée de votre page d'accueil.
- **Scénario / exemple de marchand :** Votre page d'accueil a un espace horizontal limité. Le choix d'un style « Carrousel » vous permet d'afficher de nombreux articles d'actualité sans rendre la page trop longue. Si vous avez amplement d'espace, une « Grille » pourrait être plus attrayante.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Sélectionner la catégorie de pages CMS | Votre catégorie CMS « Actualités » désignée | Définit les pages CMS utilisées comme source d'actualités. |
| Configuration du module | Afficher le contenu complet de la dernière page CMS | OUI | Affiche le contenu complet du dernier article directement sur la page d'accueil. |
| Configuration du module | Afficher les miniatures des pages CMS | OUI | Active l'affichage des blocs d'actualités résumés. |
| Configuration du module | Nombre de miniatures à afficher | 3-5 | Contrôle le nombre de miniatures d'actualités récentes affichées. |
| Configuration du module | Nombre de caractères utilisés dans la description des miniatures | 100-150 | Définit la longueur de l'extrait de texte dans les miniatures. |
| Configuration du module | Style des miniatures | Varie (par exemple, Grille, Liste, Carrousel) | Détermine la mise en page visuelle des miniatures d'actualités. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Ma section d'actualités n'apparaît pas sur la page d'accueil. Que dois-je vérifier ?**
R :

1. **Module activé :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que « Actualités de la page d'accueil » est installé et activé.
2. **Catégorie CMS sélectionnée :** Dans la configuration du module, vérifiez que vous avez sélectionné une catégorie CMS valide sous « Sélectionner la catégorie de pages CMS ».
3. **Pages CMS existantes :** Assurez-vous qu'il existe des pages CMS publiées dans la catégorie sélectionnée.
4. **Paramètres de visibilité :** Vérifiez si « Afficher les miniatures des pages CMS » et/ou « Afficher le contenu complet de la dernière page CMS » sont activés dans la configuration du module. Si les deux sont désactivés, rien ne s'affichera.
5. **Cache :** Videz le cache de votre PrestaShop (**Paramètres avancés > Performances > Vider le cache**).

**Q : Les images de mes miniatures d'actualités n'apparaissent pas.**
R : Le module essaie généralement d'extraire la première image du contenu de votre page CMS.

1. **Image dans la page CMS :** Assurez-vous que le contenu de votre page CMS inclut réellement une image.
2. **Chemin de l'image :** Vérifiez que le chemin de l'image dans votre page CMS est correct et que le fichier image existe sur votre serveur.
3. **Compatibilité du thème :** Certains thèmes personnalisés peuvent interférer avec le rendu des images. Si tout le reste échoue, consultez le développeur de votre thème ou le support MyPresta.eu.

**Q : Comment traduire les titres et les descriptions des actualités ?**
R : Les titres et le contenu des actualités proviennent directement de vos pages CMS.

1. **Traductions des pages CMS :** Allez dans **Design > Pages** (ou **CMS** dans les versions plus anciennes), modifiez votre page CMS d'actualités.
2. **Modifier dans toutes les langues :** Pour chaque langue que vous prenez en charge, assurez-vous d'avoir fourni le titre et le contenu traduits pour cette page CMS spécifique. Le module affichera automatiquement la langue correcte en fonction de la langue de la boutique sélectionnée par le client.

**Q : La section d'actualités semble étrange ou mal alignée sur ma page d'accueil.**
R : Il s'agit souvent d'un conflit CSS avec le thème de votre boutique.

1. **Vider le cache :** Commencez toujours par vider le cache de votre PrestaShop (**Paramètres avancés > Performances > Vider le cache**).
2. **Configuration du module :** Vérifiez si la modification du paramètre « Style des miniatures » aide.
3. **Personnalisation du thème :** Le CSS de votre thème peut remplacer les styles du module. Vous devrez peut-être consulter un développeur web pour ajouter du CSS personnalisé à votre thème afin d'ajuster l'apparence. Le support MyPresta.eu peut offrir des conseils mais ne peut pas fournir de développement de thème personnalisé.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Actualités de la page d'accueil » (`hnews`) est un module PrestaShop simple principalement conçu pour afficher le contenu des pages CMS existantes sur la page d'accueil du front-office. Il exploite la classe `Module` de PrestaShop et les hooks standard. La logique du module réside principalement dans son fichier PHP principal, `hnews.php`, qui gère la configuration, l'enregistrement des hooks et la récupération des données. Il n'introduit pas de contrôleurs personnalisés ni d'ObjectModels complexes, s'appuyant plutôt sur les classes natives `CMSCategory` et `CMS` de PrestaShop pour les données.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. La logique d'affichage front-office du module est entièrement gérée par sa méthode `hookDisplayHome` dans `hnews.php` et rendue via un template Smarty.
- **Contrôleurs d'administration Back-Office** : Aucun. Toute la configuration est gérée via la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

- Aucune classe ou modèle d'objet personnalisé n'est introduit par ce module. Il interroge directement la base de données ou utilise les classes `CMSCategory` et `CMS` de PrestaShop pour récupérer les données.

### 4.4 Actifs JavaScript (`views/js/`)

- Aucun fichier JavaScript personnalisé n'est inclus dans ce module.

### 4.5 Feuilles de style CSS (`views/css/`)

- `hnews/views/admin/css/hnews.css` :
  - **Portée :** Style du formulaire d'administration du back-office.
  - **Composants d'interface utilisateur principaux :** Contient probablement des styles spécifiques à la page de configuration du module, garantissant une mise en page cohérente et lisible dans le back-office de PrestaShop.
  - **Sélecteurs de classe CSS clés :** Peut inclure des styles pour les éléments de formulaire, les étiquettes et les conteneurs spécifiques utilisés dans `getContent()`.
- `hnews/views/css/hnews.css` :
  - **Portée :** Style client du front-office.
  - **Composants d'interface utilisateur principaux :** Style la section d'actualités affichée sur la page d'accueil, y compris l'article d'actualité principal (si le contenu complet est affiché) et les miniatures d'actualités individuelles.
  - **Sélecteurs de classe CSS clés :** Contient des sélecteurs pour le conteneur principal des actualités, les blocs de miniatures individuels, les titres, les descriptions et les images. Les développeurs peuvent remplacer ces classes dans le `custom.css` ou `theme.css` de leur thème pour correspondre au design de la boutique.

### 4.6 Structure du template Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :
  - `hnews/views/hnews.tpl` : C'est le template principal du front-office.
    - **Hook :** Rendu dans `displayHome`.
    - **Bloc visuel :** Affiche toute la section d'actualités sur la page d'accueil, y compris le contenu complet du dernier article d'actualité (si activé) et la liste des miniatures d'actualités. Il itère sur les articles d'actualité passés par la logique PHP du module.
- **Templates d'administration (`views/templates/admin/`)** :
  - `hnews/views/admin/elements.tpl` :
    - **Hook :** Non directement hooké, mais inclus/rendu par la méthode `getContent()` dans `hnews.php`.
    - **Bloc visuel :** Rend les éléments du formulaire de configuration du module dans le back-office de PrestaShop. Cela inclut généralement le menu déroulant pour les catégories CMS, les commutateurs pour les options d'affichage et les champs de saisie pour les comptes et les limites de caractères.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :
  - Le module ne crée aucune table SQL personnalisée.
  - Il stocke ses paramètres de configuration dans la table `ps_configuration` en utilisant des clés comme `HNEWS_ID_CMSCAT`, `HNEWS_NB_MIN`, `HNEWS_LATEST`, `HNEWS_SIZE_MIN`, `HNEWS_CHR_MIN`, `HNEWS_MINIATURES`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHome` | Rend le contenu dans la zone principale de la page d'accueil. | Affiche la section d'actualités avec les dernières pages CMS. |
| `displayHeader` | Exécuté dans la section `<head>` de la page du front-office. | Potentiellement utilisé pour charger les actifs CSS ou JS du front-office (bien qu'aucun JS ne soit présent, le CSS est chargé). |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses médias (CSS/JS). | Utilisé pour charger le CSS du back-office pour la page de configuration du module. |
| `header` | Similaire à `displayHeader`, souvent utilisé pour le chargement d'actifs. | Potentiellement utilisé pour charger les actifs CSS ou JS du front-office. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Actualités de la page d'accueil », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes liés au module.
