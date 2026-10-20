---
title: "Expert produit - Cartes de visite de spécialiste - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop « Expert produit - Cartes de visite de spécialiste » par MyPresta.eu."
sidebar:
  label: "Expert produit - Cartes de visite de spécialiste - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Product expert - Specialist Business Cards sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-expert-specialist-business-cards.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/product-expert-specialist-business-cards/)
>
> ---


# Expert produit - Cartes de visite de spécialiste

## 1. Exigences et compatibilité

Pour assurer le bon fonctionnement du module « Expert produit - Cartes de visite de spécialiste », veuillez consulter les exigences suivantes :

- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard telles que cURL, JSON et OpenSSL sont requises et généralement disponibles sur la plupart des environnements d'hébergement modernes. Aucune configuration de serveur spéciale n'est généralement nécessaire.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

Le module « Expert produit - Cartes de visite de spécialiste » offre de nombreuses options de configuration réparties sur plusieurs écrans de votre Back Office PrestaShop.

### 2.1 Page de configuration du module (Back Office > Modules > Gestionnaire de modules > Configurer Expert produit - Cartes de visite de spécialiste)

Ceci est l'écran de configuration principal pour les paramètres généraux du module, accessible directement après l'installation ou en cliquant sur « Configurer » depuis le Gestionnaire de modules.

-   **Activer/Désactiver le module :**

    -   **Ce que fait ce paramètre :** C'est l'interrupteur principal de la fonctionnalité du module.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Les fonctionnalités du module (cartes d'experts, attributions) seront actives sur votre front office.
        -   *Lorsqu'il est désactivé :* Toutes les fonctionnalités du module seront masquées du front office, et les cartes d'experts n'apparaîtront pas.
    -   **Valeur recommandée :** OUI (sauf si vous le désactivez temporairement pour la maintenance).
    -   **Scénario/exemple pour le marchand :** Vous pourriez le désactiver si vous effectuez une mise à jour majeure du thème et souhaitez vous assurer qu'il n'y a pas de conflits, puis le réactiver une fois les tests terminés.
-   **Afficher les experts sur la page produit :**

    -   **Ce que fait ce paramètre :** Contrôle si les cartes d'experts sont affichées sur les pages de produits individuelles.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Les experts attribués aux produits, catégories, marques ou fournisseurs apparaîtront sur les pages de produits pertinentes.
        -   *Lorsqu'il est désactivé :* Les experts ne seront pas affichés sur les pages de produits, quelles que soient leurs attributions.
    -   **Valeur recommandée :** OUI (c'est une fonctionnalité essentielle du module).
    -   **Scénario/exemple pour le marchand :** Si vous ne souhaitez utiliser les experts que pour les demandes B2B sur une page dédiée et non directement sur les listes de produits, vous pourriez désactiver cette option.
-   **Afficher les experts dans le hook :**

    -   **Ce que fait ce paramètre :** Vous permet de sélectionner un hook PrestaShop spécifique où les cartes d'experts seront affichées. Les hooks courants incluent `displayProductButtons`, `displayProductExtraContent`, `displayRightColumn`, `displayLeftColumn`, `displayFooter`.
    -   **Effet de la modification de ce paramètre :** Les cartes d'experts s'afficheront à l'emplacement choisi sur vos pages de produits ou d'autres pages où le hook est actif.
    -   **Valeur recommandée :** `displayProductExtraContent` ou `displayProductButtons` sont souvent de bons choix pour les pages de produits, car ils sont généralement bien visibles. Expérimentez pour trouver la meilleure adaptation à votre thème.
    -   **Scénario/exemple pour le marchand :** Si votre thème a un onglet ou une section « contenu supplémentaire » dédiée, `displayProductExtraContent` pourrait être idéal. Si vous souhaitez que les experts soient près du bouton « Ajouter au panier », `displayProductButtons` pourrait fonctionner.
-   **Activer le formulaire de contact :**

    -   **Ce que fait ce paramètre :** Détermine si un formulaire de contact est disponible pour que les clients puissent envoyer un message directement aux experts.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Un bouton ou un lien « Contacter l'expert » apparaîtra sur la carte de l'expert, ouvrant un formulaire permettant aux clients d'envoyer un message.
        -   *Lorsqu'il est désactivé :* L'option de formulaire de contact sera supprimée des cartes d'experts.
    -   **Valeur recommandée :** OUI (fortement recommandé pour l'engagement client).
    -   **Scénario/exemple pour le marchand :** L'activation de cette option permet aux clients de poser des questions spécifiques sur un produit directement à l'expert, ce qui conduit à des achats plus éclairés.
-   **Conformité RGPD pour le formulaire de contact :**

    -   **Ce que fait ce paramètre :** Si le formulaire de contact est activé, ce paramètre ajoute une case à cocher pour que les clients consentent au traitement des données, ce qui est crucial pour la conformité au RGPD.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Une case à cocher obligatoire apparaîtra sur le formulaire de contact, exigeant le consentement du client avant d'envoyer un message.
        -   *Lorsqu'il est désactivé :* Aucune case à cocher de consentement RGPD ne sera affichée.
    -   **Valeur recommandée :** OUI (essentiel pour la conformité légale dans de nombreuses régions).
    -   **Scénario/exemple pour le marchand :** Activez toujours cette option si votre public cible se trouve dans l'UE ou dans toute région ayant des lois similaires sur la protection des données.
-   **Mise en page par défaut de la carte d'expert :**

    -   **Ce que fait ce paramètre :** Vous permet de sélectionner une mise en page prédéfinie ou personnalisée pour l'affichage des cartes de visite d'experts individuelles. Cela inclut des options pour le placement de la photo, l'alignement du texte et la conception globale de la carte.
    -   **Effet de la modification de ce paramètre :** Modifie l'apparence visuelle de toutes les cartes d'experts dans votre boutique, sauf si elle est remplacée par les paramètres d'un expert spécifique.
    -   **Valeur recommandée :** Choisissez une mise en page qui correspond le mieux à l'esthétique de votre boutique. Vous pouvez prévisualiser différentes options.
    -   **Scénario/exemple pour le marchand :** Vous pouvez choisir une mise en page « Moderne » pour une boutique élégante et minimaliste, ou une mise en page « Classique » pour une ambiance plus traditionnelle.
-   **Mise en page par défaut de la liste d'experts :**

    -   **Ce que fait ce paramètre :** Détermine comment plusieurs cartes d'experts sont organisées lorsque plus d'un expert est affiché (par exemple, dans une grille, une liste ou un carrousel).
    -   **Effet de la modification de ce paramètre :** Contrôle la présentation globale de plusieurs experts sur une page.
    -   **Valeur recommandée :** « Grille » pour un affichage compact, « Carrousel » pour un gain de place et une navigation interactive, ou « Liste » pour une vue plus détaillée et empilée.
    -   **Scénario/exemple pour le marchand :** Si vous avez de nombreux experts pour une catégorie, un « Carrousel » peut économiser de l'espace. Si vous n'en avez qu'un ou deux, une « Grille » pourrait être plus propre.
-   **Afficher l'outil de recherche d'experts :**

    -   **Ce que fait ce paramètre :** Active une barre de recherche qui permet aux clients de trouver des experts par nom ou par spécialité.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Un champ de saisie de recherche apparaîtra, généralement près des cartes d'experts, permettant aux clients de filtrer les experts.
        -   *Lorsqu'il est désactivé :* L'outil de recherche d'experts ne sera pas visible.
    -   **Valeur recommandée :** OUI (améliore la convivialité, surtout avec de nombreux experts).
    -   **Scénario/exemple pour le marchand :** Si vous avez une grande équipe de spécialistes, l'activation de l'outil de recherche aide les clients à trouver rapidement la bonne personne.
-   **Hook de l'outil de recherche d'experts :**

    -   **Ce que fait ce paramètre :** Spécifie où l'outil de recherche d'experts sera affiché dans votre front office.
    -   **Effet de la modification de ce paramètre :** La barre de recherche apparaîtra à l'emplacement du hook choisi.
    -   **Valeur recommandée :** `displayTop` ou `displayNav` pour une visibilité globale, ou `displayLeftColumn`/`displayRightColumn` si vous souhaitez qu'il soit à côté d'autres filtres.
    -   **Scénario/exemple pour le marchand :** Le placer dans `displayTop` le rend facilement accessible depuis n'importe quelle page, similaire à une recherche de produit.

### 2.2 Écran d'administration dédié : Experts (Back Office > Expert produit > Experts)

Cet écran est l'endroit où vous gérez les profils d'experts individuels, créez de nouveaux experts et modifiez ceux qui existent déjà.

-   **Nom de l'écran et emplacement du menu :** **Expert produit > Experts**
-   **Actions et paramètres disponibles :**

    -   **Liste des experts (vue grille) :** Affiche un tableau de tous vos experts créés. Vous pouvez voir leur nom, leur rôle, leur statut (actif/inactif) et des actions comme « Modifier » ou « Supprimer ».
    -   **Bouton « Ajouter un nouvel expert » :** Cliquer sur ce bouton vous amène à un formulaire pour créer un nouveau profil d'expert.
    -   **Actions Modifier/Supprimer :** Pour chaque expert de la liste, vous pouvez cliquer sur « Modifier » pour modifier ses détails ou sur « Supprimer » pour le supprimer.
    -   **Actions en masse :** Vous permet de sélectionner plusieurs experts et d'effectuer des actions comme les « Activer », les « Désactiver » ou les « Supprimer » simultanément.
-   **Formulaire de création/modification d'expert :**

    -   **Nom :** Le nom complet de votre expert.
    -   **Rôle/Titre :** Leur titre professionnel ou leur rôle (par exemple, « Responsable des ventes senior », « Spécialiste du support technique », « Conseiller mode »).
    -   **Courte biographie :** Une brève description de leur expertise ou de leur parcours. Cela aide les clients à comprendre leurs qualifications.
    -   **Photo :** Téléchargez une photo professionnelle de l'expert. C'est crucial pour établir la confiance et la connexion personnelle.
    -   **Liens de contact :**
        -   **E-mail :** Adresse e-mail de l'expert.
        -   **Téléphone :** Numéro de téléphone de l'expert.
        -   **WhatsApp :** Numéro WhatsApp (générera un lien de chat direct).
        -   **LinkedIn :** Lien vers leur profil LinkedIn.
        -   **Autres liens personnalisés :** Vous pouvez ajouter des liens personnalisés supplémentaires avec des icônes (par exemple, un lien vers leur blog personnel, un portefeuille de produits spécifique).
    -   **Actif :** Un interrupteur pour activer ou désactiver l'expert.
        -   *Lorsqu'il est activé :* L'expert sera disponible pour l'attribution et l'affichage.
        -   *Lorsqu'il est désactivé :* L'expert n'apparaîtra pas sur le front office, même s'il est attribué.
    -   **Remplacement de la mise en page de la carte d'expert :** Vous permet de sélectionner une mise en page de carte spécifique pour *cet expert individuel*, remplaçant la valeur par défaut globale définie dans la configuration du module. Ceci est utile pour mettre en évidence certains experts ou pour correspondre à leur marque personnelle.
    -   **Attributions (Produits, Catégories, Marques, Fournisseurs) :** C'est ici que vous liez les experts à des entités spécifiques de la boutique.
        -   **Produits :** Recherchez et sélectionnez les produits individuels auxquels cet expert est associé.
        -   **Catégories :** Sélectionnez les catégories où la carte de cet expert doit apparaître sur les produits de ces catégories.
        -   **Marques :** Sélectionnez les marques spécifiques dans lesquelles cet expert est spécialisé.
        -   **Fournisseurs :** Sélectionnez les fournisseurs dont les produits cet expert peut conseiller.
        -   *Effet des modifications :* Lorsqu'un client consulte un produit qui correspond à l'une de ces attributions, la carte de l'expert sera affichée. Si plusieurs experts sont attribués, tous les experts pertinents seront affichés selon la mise en page de la liste.
-   **Effet des modifications :**

    -   L'ajout d'un nouvel expert le rend disponible pour l'attribution aux produits, catégories, etc.
    -   La modification d'un expert met à jour ses informations affichées et ses coordonnées dans toute la boutique.
    -   La suppression d'un expert le supprime, ainsi que ses attributions, de votre boutique.
    -   La modification des attributions affecte immédiatement les cartes d'experts qui apparaissent sur quelles pages de produits.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**

    1.  **Créer de nouveaux experts :** Lorsqu'un nouveau membre rejoint l'équipe ou qu'une nouvelle spécialisation est nécessaire, créez son profil ici.
    2.  **Attribuer des experts :** Examinez régulièrement votre catalogue de produits et attribuez des experts pertinents aux nouveaux produits, catégories ou marques.
    3.  **Mettre à jour les profils :** Maintenez à jour les photos, les biographies et les coordonnées des experts.
    4.  **Désactiver/Réactiver :** Utilisez l'interrupteur « Actif » pour masquer temporairement un expert (par exemple, s'il est en congé) sans supprimer son profil.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activer/Désactiver le module | OUI | Interrupteur principal pour la fonctionnalité du module. |
| | Afficher les experts sur la page produit | OUI | Afficher les cartes d'experts sur les pages produit. |
| | Afficher les experts dans le hook | `displayProductExtraContent` | Choisir où les cartes d'experts apparaissent sur les pages produit. |
| | Activer le formulaire de contact | OUI | Permettre aux clients d'envoyer un message directement aux experts. |
| | Conformité RGPD pour le formulaire de contact | OUI | Ajouter une case à cocher de consentement au formulaire de contact. |
| | Mise en page par défaut de la carte d'expert | (Choisir en fonction du thème) | Style visuel des cartes d'experts individuelles. |
| | Mise en page par défaut de la liste d'experts | Grille / Carrousel | Comment plusieurs cartes d'experts sont organisées. |
| | Afficher l'outil de recherche d'experts | OUI | Activer une barre de recherche pour les experts. |
| | Hook de l'outil de recherche d'experts | `displayTop` / `displayNav` | Où l'outil de recherche d'experts apparaît. |
| **Expert produit > Experts** | Ajouter un nouvel expert | N/A | Créer de nouveaux profils d'experts. |
| | Modifier l'expert | N/A | Modifier les détails de l'expert (nom, rôle, biographie, photo, contacts). |
| | Actif (Statut de l'expert) | OUI | Activer/désactiver la visibilité de l'expert individuel. |
| | Remplacement de la mise en page de la carte d'expert | N/A | Remplacer la mise en page globale de la carte pour un expert spécifique. |
| | Attribuer aux produits | N/A | Lier l'expert à des produits spécifiques. |
| | Attribuer aux catégories | N/A | Lier l'expert aux produits de catégories spécifiques. |
| | Attribuer aux marques | N/A | Lier l'expert aux produits de marques spécifiques. |
| | Attribuer aux fournisseurs | N/A | Lier l'expert aux produits de fournisseurs spécifiques. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

Voici quelques questions courantes et des conseils de dépannage pour les propriétaires de boutiques utilisant le module « Expert produit - Cartes de visite de spécialiste » :

**Q1 : Mes cartes d'experts n'apparaissent pas sur la page produit.**

-   **R :** Tout d'abord, vérifiez si le module est **activé** dans **Modules > Gestionnaire de modules**.
-   **R :** Ensuite, accédez à la page de configuration du module et assurez-vous que « Afficher les experts sur la page produit » est défini sur **OUI**.
-   **R :** Vérifiez que vous avez bien **attribué** un expert au produit spécifique, à sa catégorie, à sa marque ou à son fournisseur dans **Expert produit > Experts > [Modifier l'expert] > Attributions**.
-   **R :** Vérifiez l'interrupteur « Actif » pour l'expert individuel dans **Expert produit > Experts**. S'il est inactif, il ne s'affichera pas.
-   **R :** Videz votre cache PrestaShop : Allez dans **Paramètres avancés > Performances**, puis cliquez sur « Vider le cache » en haut à droite. Parfois, un ancien contenu mis en cache empêche l'apparition de nouveaux éléments du module.

**Q2 : Les cartes d'experts ont l'air étranges ou ne correspondent pas au design de mon thème.**

-   **R :** Le module propose une « Mise en page par défaut de la carte d'expert » et une « Mise en page par défaut de la liste d'experts » dans sa configuration. Expérimentez avec différentes options pour voir celle qui s'intègre le mieux à votre thème.
-   **R :** Si vous avez un thème personnalisé, il peut avoir des CSS spécifiques qui entrent en conflit avec le style du module. Vous pourriez avoir besoin d'un développeur web pour inspecter le CSS et apporter des ajustements mineurs.
-   **R :** Assurez-vous que votre thème est à jour. Les thèmes obsolètes peuvent parfois causer des problèmes d'affichage avec les modules plus récents.

**Q3 : Le formulaire de contact n'envoie pas d'e-mails.**

-   **R :** Tout d'abord, assurez-vous que « Activer le formulaire de contact » est défini sur **OUI** dans la configuration du module.
-   **R :** Vérifiez que l'adresse e-mail de l'expert est correctement saisie dans son profil (**Expert produit > Experts > [Modifier l'expert]**).
-   **R :** Vérifiez vos paramètres d'e-mail PrestaShop (**Paramètres avancés > E-mail**). Envoyez un e-mail de test depuis PrestaShop pour vous assurer que la configuration e-mail de votre boutique fonctionne correctement. Si PrestaShop ne peut pas envoyer d'e-mails, le module ne le pourra pas non plus.
-   **R :** Vérifiez les journaux de messagerie de votre serveur pour toute erreur. Cela pourrait nécessiter l'aide de votre hébergeur.

**Q4 : Comment traduire le texte du module dans d'autres langues ?**

-   **R :** Allez dans **International > Traductions** dans votre Back Office PrestaShop.
-   **R :** Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez le module « Expert produit - Cartes de visite de spécialiste ».
-   **R :** Vous pouvez ensuite traduire toutes les chaînes du module dans les langues souhaitées. N'oubliez pas d'enregistrer vos modifications.

**Q5 : Je souhaite afficher les experts à un emplacement différent des hooks disponibles.**

-   **R :** Le module propose une sélection de hooks PrestaShop standard. Si vous devez afficher les experts à un emplacement très spécifique et non standard (par exemple, à l'intérieur d'un onglet personnalisé ou d'une section unique de votre modèle de page produit), cela nécessitera un développement de thème personnalisé. Un développeur web devrait appeler manuellement la fonction de hook du module directement dans les fichiers `.tpl` de votre thème.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une plongée approfondie dans l'architecture technique et la base de code du module « Expert produit - Cartes de visite de spécialiste », destinée aux développeurs, webmasters et agences techniques.

### 4.1 Aperçu de l'architecture

Le module « Expert produit - Cartes de visite de spécialiste » suit un modèle MVC (Modèle-Vue-Contrôleur) PrestaShop standard, tirant fortement parti d'`ObjectModel` pour la persistance des données. Il introduit des contrôleurs d'administration personnalisés pour gérer les experts et leurs attributions, et des contrôleurs frontaux pour les interactions AJAX et l'affichage des informations d'experts. Le module utilise une structure de classe robuste pour gérer les mises en page des cartes d'experts, les styles et la logique de présentation, permettant une grande personnalisation. Il s'intègre à divers hooks PrestaShop pour injecter son contenu dynamiquement dans le front office.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   `controllers/front/ajax.php`
    -   **Nom de la classe :** `ProductexpertAjaxModuleFrontController` (étend `ModuleFrontController`)
    -   **Responsabilité :** Gère les requêtes AJAX du front office. Cela inclut généralement le traitement des soumissions de formulaires de contact d'experts, le chargement dynamique des données d'experts ou tout autre élément interactif nécessitant une communication côté serveur sans rechargement complet de la page. Il renvoie des réponses JSON.
-   `controllers/front/index.php`
    -   **Nom de la classe :** `ProductexpertIndexModuleFrontController` (étend `ModuleFrontController`)
    -   **Responsabilité :** Un contrôleur frontal de substitution ou par défaut. Dans de nombreux modules, cela pourrait gérer une page de module dédiée si elle existe, ou simplement rediriger si sa fonction principale est via des hooks ou AJAX. Pour ce module, son rôle principal est probablement minimal, `ajax.php` gérant la plupart des interactions front-end.

#### Contrôleurs d'administration Back-Office

-   `controllers/admin/AdminProductExpertController.php`
    -   **Nom de la classe :** `AdminProductExpertController` (étend `ModuleAdminController`)
    -   **Nom de l'onglet :** « Experts » sous le menu « Expert produit ».
    -   **Entité gérée :** `ProductExpertExpert` (via `classes/ProductExpertExpert.php`).
    -   **Responsabilité :** C'est le contrôleur d'administration principal pour la gestion des profils d'experts individuels. Il gère la liste des experts (en utilisant `HelperList`) et les formulaires de création/modification d'experts (en utilisant `HelperForm`). Il gère les opérations CRUD pour les données d'experts, y compris leur nom, rôle, biographie, photo, liens de contact, et surtout, leurs attributions aux produits, catégories, marques et fournisseurs. Il gère également les remplacements de mise en page pour les cartes d'experts individuelles.
-   `controllers/admin/index.php`
    -   **Nom de la classe :** (Pas de classe spécifique, souvent une redirection ou une mesure de sécurité)
    -   **Responsabilité :** Ce fichier est généralement une mesure de sécurité pour empêcher la liste ou l'accès direct au répertoire. Il contient souvent un simple `header('Location: ../../index.php'); exit;` ou similaire pour rediriger vers le panneau d'administration principal. Il ne gère pas d'entité ou de formulaire spécifique.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module dispose d'un riche ensemble de classes pour gérer ses fonctionnalités complexes, en particulier autour des mises en page et des configurations des cartes d'experts.

-   `classes/ProductExpertExpert.php`
    -   **Table de base de données :** `ps_productexpert_expert`
    -   **Étend :** `ObjectModel`
    -   **Champs `$definition` :** Définit le schéma des profils d'experts (id\_expert, name, role, bio, photo\_id, active, date\_add, date\_upd, layout\_preset\_id). Gère les champs multilingues si applicable.
    -   **Méthodes publiques clés :** Méthodes pour enregistrer, récupérer et supprimer les données d'experts. Inclut la logique pour gérer les téléchargements de photos et les associations.
-   `classes/ProductExpertExpertLinks.php`
    -   **Table de base de données :** `ps_productexpert_expert_link`
    -   **Étend :** `ObjectModel`
    -   **Champs `$definition` :** Définit le schéma des liens de contact d'experts (id\_expert\_link, id\_expert, type, value, icon, position).
    -   **Méthodes publiques clés :** Gère les différents liens de contact (e-mail, téléphone, WhatsApp, LinkedIn, personnalisé) associés à un expert.
-   `classes/ProductExpertExpertPhoto.php`
    -   **Table de base de données :** `ps_productexpert_expert_photo`
    -   **Étend :** `ObjectModel`
    -   **Champs `$definition` :** Gère les détails de la photo de l'expert (id\_photo, filename, mime\_type, size).
    -   **Méthodes publiques clés :** Gère le stockage et la récupération des images de profil d'experts.
-   `classes/ProductExpertConfig.php`
    -   **Table de base de données :** `ps_configuration` (stocke les valeurs de configuration)
    -   **Étend :** (Probablement pas `ObjectModel`, mais une classe utilitaire)
    -   **Méthodes publiques clés :** Fournit des méthodes statiques pour obtenir et définir les valeurs de configuration spécifiques au module (par exemple, `PE_DISPLAY_ON_PRODUCT_PAGE`, `PE_CONTACT_FORM_ENABLED`).
-   `classes/ProductExpertResolver.php`
    -   **Étend :** (Probablement une classe personnalisée)
    -   **Méthodes publiques clés :** Contient la logique principale pour déterminer quels experts doivent être affichés pour un produit donné en fonction de sa catégorie, de sa marque, de son fournisseur et des attributions directes de produits. Il résout la liste des experts pour le front office.
-   `classes/ProductExpertListPresenter.php`
    -   **Étend :** (Probablement une classe personnalisée)
    -   **Méthodes publiques clés :** Responsable de la préparation des données des experts résolus dans un format adapté à l'affichage dans les modèles Smarty, en appliquant les mises en page de liste sélectionnées (grille, carrousel, liste).
-   `classes/ExpertCardLayout.php`, `ExpertCardLayoutPresets.php`, `ExpertCardLayoutPresetsBuiltin.php`, `ExpertCardLayoutPresetsBuiltinData.php`, `ExpertCardLayoutPresetsFilesystem.php`, `ExpertCardLayoutInstances.php`
    -   **Étend :** (Probablement des classes personnalisées)
    -   **Responsabilité :** Un ensemble complexe de classes dédiées à la gestion de la conception visuelle et de la structure des cartes de visite d'experts. Cela inclut la définition des éléments de mise en page, des styles, des dégradés, et la gestion des préréglages intégrés ainsi que des mises en page personnalisées enregistrées par l'utilisateur. C'est le cœur de la fonctionnalité du « Concepteur de cartes de visite visuelles ».
-   `classes/ExpertCardAdminUi.php`, `ProductExpertSettingsAdminUi.php`, `ProductExpertListLayoutAdminUi.php`
    -   **Étend :** (Probablement des classes personnalisées)
    -   **Responsabilité :** Classes d'aide pour le rendu des éléments d'interface utilisateur complexes dans les formulaires de configuration du Back Office, en particulier pour le studio de mise en page et les paramètres généraux du module.
-   `classes/PeCompatibility.php`
    -   **Étend :** (Probablement une classe utilitaire)
    -   **Méthodes publiques clés :** Fournit des méthodes pour gérer les problèmes de compatibilité entre les différentes versions de PrestaShop (par exemple, différences dans les noms de hooks, les appels d'API ou les fonctions obsolètes).
-   `classes/ProductExpertInstallSamples.php`
    -   **Étend :** (Probablement une classe utilitaire)
    -   **Méthodes publiques clés :** Contient la logique pour installer des exemples de données (par exemple, des experts, des mises en page) lors de l'installation du module afin de fournir un démarrage rapide aux marchands.

### 4.4 Actifs JavaScript (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`
    -   **Portée :** Front-office.
    -   **Description :** Fournit une fonctionnalité d'autocomplétion pour l'outil de recherche d'experts, suggérant des noms d'experts ou des spécialités au fur et à mesure que l'utilisateur tape.
-   `lib/searchTool/views/pe-searchtool-init.js`
    -   **Portée :** Front-office.
    -   **Description :** Initialise l'outil de recherche d'experts, en liant les écouteurs d'événements à l'entrée de recherche et en intégrant la fonctionnalité d'autocomplétion.
-   `views/js/admin-element-editor.js`
    -   **Portée :** Back-office.
    -   **Description :** Alimente l'éditeur visuel pour les éléments individuels d'une mise en page de carte d'expert (par exemple, champs de texte, images, icônes). Gère le glisser-déposer, le redimensionnement et les ajustements des propriétés de style.
-   `views/js/admin-expert-photo.js`
    -   **Portée :** Back-office.
    -   **Description :** Gère la fonctionnalité de téléchargement et de prévisualisation de photos pour les profils d'experts dans le panneau d'administration.
-   `views/js/admin-layout-studio.js`
    -   **Portée :** Back-office.
    -   **Description :** Le JavaScript principal du « Concepteur de cartes de visite visuelles ». Il gère la toile de mise en page globale, la gestion des éléments, l'enregistrement/le chargement des mises en page et l'application des styles.
-   `views/js/admin-list-layout-studio.js`
    -   **Portée :** Back-office.
    -   **Description :** Gère le studio pour la conception de l'affichage de plusieurs cartes d'experts (grille, carrousel, liste), y compris les options de réactivité et de navigation.
-   `views/js/front.js`
    -   **Portée :** Front-office.
    -   **Description :** Contient le JavaScript général du front-office pour le module, y compris :
        -   Les écouteurs d'événements pour la soumission du formulaire de contact (appels AJAX à `ajax.php`).
        -   La logique pour afficher et masquer la modale du formulaire de contact.
        -   L'initialisation de toutes les fonctionnalités de carrousel ou de curseur pour les listes d'experts.
        -   Les améliorations générales de l'interface utilisateur pour les cartes d'experts.

### 4.5 Feuilles de style CSS (`views/css/`)

#### CSS Front-Office

-   `lib/searchTool/views/css/autocomplete.css`
    -   **Portée :** Front-office.
    -   **Description :** Styles pour les suggestions de la liste déroulante d'autocomplétion dans l'outil de recherche d'experts.
-   `views/css/front.css`
    -   **Portée :** Front-office.
    -   **Description :** Styles généraux du front-office pour le module, y compris la mise en page de base, la typographie et la réactivité pour les cartes et les listes d'experts.
-   `views/css/pe-expert-card-front.css`
    -   **Portée :** Front-office.
    -   **Description :** Style spécifique pour les cartes de visite d'experts individuelles, appliquant la mise en page et les styles d'éléments choisis.
-   `views/css/pe-front-contact.css`
    -   **Portée : :** Front-office.
    -   **Description :** Styles pour le formulaire de contact de l'expert, y compris la présentation modale, les champs de saisie et les boutons.
-   `views/css/pe-front-experts.css`
    -   **Portée :** Front-office.
    -   **Description :** Styles pour l'affichage global de plusieurs experts, tels que les mises en page en grille, les mises en page en liste ou la navigation en carrousel.

#### CSS Back-Office

-   `views/css/admin-config.css`
    -   **Portée :** Back-office.
    -   **Description :** Style général pour la page de configuration principale du module dans le panneau d'administration.
-   `views/css/admin-element-editor.css`
    -   **Portée :** Back-office.
    -   **Description :** Styles pour l'éditeur d'éléments visuels dans le studio de mise en page.
-   `views/css/admin-expert-card-studio.css`
    -   **Portée :** Back-office.
    -   **Description :** CSS principal pour l'interface du studio de mise en page des cartes d'experts.
-   `views/css/admin-expert-photo.css`
    -   **Portée :** Back-office.
    -   **Description :** Styles pour la zone de téléchargement et de prévisualisation des photos d'experts dans les formulaires d'administration.
-   `views/css/admin-experts-list.css`
    -   **Portée :** Back-office.
    -   **Description :** Styles pour la vue liste des experts dans `AdminProductExpertController`.
-   `views/css/admin-layout-builder.css`
    -   **Portée :** Back-office.
    -   **Description :** Styles liés aux composants de création de mise en page.
-   `views/css/admin-layout-studio.css`
    -   **Portée :** Back-office.
    -   **Description :** Styles généraux pour l'interface du studio de mise en page.
-   `views/css/admin-list-layout-studio.css`
    -   **Portée :** Back-office.
    -   **Description :** Styles pour l'interface du studio de mise en page de liste.
-   `views/css/admin-pe-overrides.css`
    -   **Portée :** Back-office.
    -   **Description :** Remplacements ou ajustements CSS spécifiques pour les styles d'administration par défaut de PrestaShop afin d'assurer la cohérence de l'interface utilisateur du module.
-   `views/css/admin-searchtool.css`
    -   **Portée :** Back-office.
    -   **Description :** Styles pour l'outil de recherche dans le panneau d'administration (le cas échéant, par exemple, pour la recherche de produits/catégories lors de l'attribution).

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   `lib/searchTool/views/scripts.tpl`
    -   **Portée :** Front-office.
    -   **Description :** Inclut probablement les fichiers JavaScript et CSS nécessaires pour l'outil de recherche, souvent accroché à `displayHeader` ou `displayFooter` pour charger les ressources.
-   `views/templates/admin/configure.tpl`
    -   **Portée :** Back-office.
    -   **Description :** Le modèle principal de la page de configuration du module (méthode `getContent()`), rendant le formulaire de paramètres généraux.
-   `views/templates/admin/list-layout.tpl`
    -   **Portée :** Back-office.
    -   **Description :** Modèle pour le studio de mise en page de liste dans l'administration, permettant la configuration de l'affichage de plusieurs cartes d'experts.
-   `views/templates/admin/product-tab.tpl`
    -   **Portée :** Back-office.
    -   **Description :** Ce modèle est probablement utilisé pour injecter un onglet ou une section personnalisée dans la page d'édition de produit de PrestaShop, permettant l'attribution directe d'experts à un produit depuis son écran d'édition.
-   `views/templates/hook/product-experts.tpl`
    -   **Portée :** Front-office.
    -   **Hook :** `displayProductButtons`, `displayProductExtraContent`, `displayRightColumn`, `displayLeftColumn`, `displayFooter` (selon la configuration).
    -   **Description :** Le modèle principal responsable du rendu du bloc de cartes d'experts sur le front office. Il itère sur les experts résolus et inclut `_pe-expert-card-element.tpl` pour chacun.
-   `views/templates/hook/_pe-expert-card-element.tpl`
    -   **Portée :** Front-office.
    -   **Hook :** Inclus par `product-experts.tpl`.
    -   **Description :** Rend une seule carte de visite d'expert, appliquant la mise en page choisie et affichant la photo, le nom, le rôle, la biographie et les liens de contact de l'expert. Il inclut probablement `_pe-expert-card-row.tpl` pour le contenu structuré.
-   `views/templates/hook/_pe-expert-card-row.tpl`
    -   **Portée :** Front-office.
    -   **Hook :** Inclus par `_pe-expert-card-element.tpl`.
    -   **Description :** Rend une seule ligne ou section dans une carte d'expert, utilisée pour structurer les éléments de contenu (par exemple, une ligne pour les icônes de contact, une ligne pour le nom et le rôle).

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

-   `ps_productexpert_expert` : Stocke les informations de profil d'expert de base (nom, rôle, biographie, ID de photo, statut actif, préréglage de mise en page).
-   `ps_productexpert_expert_lang` : Stocke les champs multilingues pour les experts (le cas échéant, par exemple, la biographie).
-   `ps_productexpert_expert_link` : Stocke les liens de contact individuels pour chaque expert (type, valeur, icône).
-   `ps_productexpert_expert_photo` : Stocke les métadonnées pour les images de profil d'expert.
-   `ps_productexpert_expert_product` : Table de relation plusieurs-à-plusieurs liant les experts aux produits.
-   `ps_productexpert_expert_category` : Table de relation plusieurs-à-plusieurs liant les experts aux catégories.
-   `ps_productexpert_expert_manufacturer` : Table de relation plusieurs-à-plusieurs liant les experts aux marques (fabricants).
-   `ps_productexpert_expert_supplier` : Table de relation plusieurs-à-plusieurs liant les experts aux fournisseurs.
-   `ps_productexpert_layout_preset` : Stocke les définitions des mises en page de cartes d'experts personnalisées créées par le marchand.
-   `ps_productexpert_list_layout` : Stocke les définitions des mises en page de listes d'experts personnalisées (grille, carrousel, etc.).
-   `ps_configuration` : Stocke les paramètres de configuration globaux du module (par exemple, `PE_DISPLAY_ON_PRODUCT_PAGE`, `PE_DEFAULT_CARD_LAYOUT_ID`).

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Charger les ressources CSS et JS du module pour le front-office. |
| `displayBackOfficeHeader` | Dans la section `<head>` de chaque page du Back Office. | Charger les ressources CSS et JS du module pour les écrans d'administration. |
| `displayModuleConfigureExtraButtons` | Sur la page du gestionnaire de modules, à côté du bouton « Configurer ». | Ajouter des liens rapides vers « Gérer les experts » ou « Studio de mise en page ». |
| `displayAdminProductsExtra` | Sur la page d'édition de produit dans le Back Office. | Injecter l'onglet/section d'attribution d'experts pour les produits. |
| `displayProductButtons` | Près du bouton « Ajouter au panier » sur les pages produit. | Afficher les cartes d'experts dans une zone proéminente spécifique au produit. |
| `displayProductExtraContent` | Dans une section/onglet dédié sur les pages produit. | Afficher les cartes d'experts comme contenu produit supplémentaire. |
| `displayLeftColumn` | Dans la barre latérale gauche des pages applicables. | Afficher les cartes d'experts ou l'outil de recherche d'experts dans la colonne de gauche. |
| `displayRightColumn` | Dans la barre latérale droite des pages applicables. | Afficher les cartes d'experts ou l'outil de recherche d'experts dans la colonne de droite. |
| `displayFooter` | Dans la section du pied de page de toutes les pages. | Afficher les cartes d'experts ou un lien vers une page d'experts dans le pied de page. |
| `displayTop` | Dans la section supérieure de la boutique (en-tête). | Afficher l'outil de recherche d'experts pour un accès global. |
| `displayNav` | Dans la barre de navigation (souvent au-dessus de `displayTop`). | Afficher l'outil de recherche d'experts pour un accès global. |
| `actionFrontControllerSetMedia` | Avant le rendu du contrôleur frontal, pour ajouter des ressources. | Ajouter dynamiquement des JS/CSS spécifiques au front-office en fonction du contexte. |
| `actionAdminControllerSetMedia` | Avant le rendu du contrôleur d'administration, pour ajouter des ressources. | Ajouter dynamiquement des JS/CSS spécifiques au back-office en fonction du contexte. |
| `actionObjectProductAddAfter` | Après l'ajout d'un nouveau produit. | Déclencher potentiellement la logique d'attribution d'experts ou la suppression du cache. |
| `actionObjectProductUpdateAfter` | Après la mise à jour d'un produit. | Déclencher potentiellement la logique d'attribution d'experts ou la suppression du cache. |
| `actionObjectProductDeleteAfter` | Après la suppression d'un produit. | Nettoyer toutes les attributions d'experts liées au produit supprimé. |
| `actionObjectCategoryUpdateAfter` | Après la mise à jour d'une catégorie. | Vider le cache lié aux attributions d'experts basées sur les catégories. |
| `actionObjectManufacturerUpdateAfter` | Après la mise à jour d'un fabricant (marque). | Vider le cache lié aux attributions d'experts basées sur les marques. |
| `actionObjectSupplierUpdateAfter` | Après la mise à jour d'un fournisseur. | Vider le cache lié aux attributions d'experts basées sur les fournisseurs. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support technique officiel, veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe est dédiée à fournir une assistance complète et à assurer le bon fonctionnement de votre module.

-   **Historique des commandes et téléchargements MyPresta.eu :** <https://mypresta.eu/my-account/orders/>
-   **Support MyPresta.eu :** Accédez à notre portail de support via votre compte pour une assistance directe.
