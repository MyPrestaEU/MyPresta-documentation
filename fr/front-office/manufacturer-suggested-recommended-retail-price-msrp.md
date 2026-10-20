---
title: "Prix de vente conseillé par le fabricant (PVC) - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Prix de vente conseillé par le fabricant (PVC)' par MyPresta.eu."
sidebar:
  label: "Prix de vente conseillé par le fabricant (PVC) - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Manufacturer suggested / recommended retail price (MSRP) sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/manufacturer-suggested-recommended-retail-price-msrp.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/manufacturer-suggested-recommended-retail-price-msrp/)
>
> ---


# Prix de vente conseillé par le fabricant (PVC)

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge :** PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module PVC, accessible après l'installation en cliquant sur le bouton « Configurer ». Ici, vous définirez comment les PVC sont affichés et gérés dans votre boutique.

#### **Activer l'affichage du PVC**

- **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonction PVC pour l'ensemble de votre boutique.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Le module commencera à afficher les informations sur le PVC sur vos pages produit et vos listes de produits, à condition que vous ayez saisi des PVC pour vos produits.
  - *Lorsqu'il est désactivé (NON) :* La fonction PVC sera complètement inactive et aucune information sur le PVC ne sera affichée aux clients, même si vous avez saisi des valeurs.
- **Valeur recommandée :** OUI (pour utiliser les fonctionnalités du module).
- **Scénario / exemple de marchand :** Si vous configurez le module pour la première fois, activez-le pour voir les changements. Si vous devez masquer temporairement les PVC pour une promotion ou une maintenance, vous pouvez le désactiver ici.

#### **Afficher le PVC sur la page produit**

- **Ce que fait ce paramètre :** Contrôle si le PVC est affiché sur les pages de détails de produits individuelles.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Le PVC, votre prix et les informations « Vous économisez » apparaîtront sur la page produit.
  - *Lorsqu'il est désactivé (NON) :* Le PVC ne sera pas affiché sur la page produit, même s'il est activé globalement.
- **Valeur recommandée :** OUI (C'est un emplacement principal pour que les clients voient la valeur).
- **Scénario / exemple de marchand :** Vous pourriez désactiver cela si vous préférez ne mettre en évidence les économies que sur les pages de catégories, ou si la conception de votre page produit est déjà très encombrée.

#### **Afficher le PVC sur la liste de produits**

- **Ce que fait ce paramètre :** Contrôle si le PVC est affiché sur les pages affichant plusieurs produits, telles que les pages de catégories, les résultats de recherche ou les blocs de produits en vedette.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Le PVC, votre prix et les informations « Vous économisez » apparaîtront pour chaque produit dans les listes de produits.
  - *Lorsqu'il est désactivé (NON) :* Le PVC ne sera pas affiché sur les pages de liste de produits.
- **Valeur recommandée :** OUI (Idéal pour des comparaisons rapides et pour mettre en évidence la valeur lors de la navigation).
- **Scénario / exemple de marchand :** L'activation de cette option aide les clients à identifier rapidement les bonnes affaires lors de la navigation dans les catégories, augmentant potentiellement les taux de clics vers les pages de produits.

#### **Afficher le prix TTC**

- **Ce que fait ce paramètre :** Détermine si le PVC affiché doit inclure les taxes ou être affiché hors taxes.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Le PVC sera affiché avec les taxes applicables déjà ajoutées, reflétant le prix final qu'un client paierait.
  - *Lorsqu'il est désactivé (NON) :* Le PVC sera affiché sans taxes.
- **Valeur recommandée :** OUI (Généralement, les clients préfèrent voir les prix finaux, surtout dans les contextes B2C).
- **Scénario / exemple de marchand :** Si votre boutique sert principalement des clients B2C, afficher les prix TTC est plus clair. Pour les boutiques B2B, les prix hors taxes pourraient être préférés.

#### **Afficher le prix HT**

- **Ce que fait ce paramètre :** Détermine si le PVC affiché doit exclure les taxes ou être affiché TTC.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Le PVC sera affiché sans taxes.
  - *Lorsqu'il est désactivé (NON) :* Le PVC sera affiché avec les taxes applicables déjà ajoutées.
- **Valeur recommandée :** NON (Sauf si vous ciblez spécifiquement des clients B2B ou opérez dans une région où les prix hors taxes sont la norme pour l'affichage initial).
- **Scénario / exemple de marchand :** Si vous activez « Afficher le prix TTC », vous désactiveriez généralement celui-ci pour éviter toute confusion. N'activez les deux que si vous souhaitez afficher les deux valeurs côte à côte (ce qui pourrait être déroutant pour les clients).

#### **Afficher les informations « Vous économisez »**

- **Ce que fait ce paramètre :** Contrôle si le module calcule et affiche la différence monétaire entre le PVC et le prix de vente de votre boutique.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Le module affichera un message comme « Vous économisez X,XX € » ou « Vous économisez X % » à côté du PVC et de votre prix.
  - *Lorsqu'il est désactivé (NON) :* Seuls le PVC et votre prix seront affichés, sans le calcul explicite des économies.
- **Valeur recommandée :** OUI (C'est un avantage clé de l'utilisation du module, motivant fortement les achats).
- **Scénario / exemple de marchand :** Cette fonctionnalité met directement en évidence la proposition de valeur. Si vos prix sont constamment inférieurs au PVC, l'activation de cette option augmentera considérablement la valeur perçue.

#### **Champ PVC pour les produits**

- **Ce que fait ce paramètre :** Ce paramètre définit où vous saisirez le PVC pour chaque produit dans votre Back Office PrestaShop.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est sélectionné :* Le module utilisera le champ produit choisi pour récupérer la valeur du PVC. Vous devrez saisir manuellement le PVC pour chaque produit dans le champ spécifié.
- **Valeur recommandée :** Le module crée généralement un champ personnalisé ou suggère d'en utiliser un existant. Suivez les instructions du module pour identifier le champ correct.
- **Scénario / exemple de marchand :** Après avoir installé le module, vous irez dans **Catalogue > Produits**, modifierez un produit et trouverez un nouveau champ de saisie (ou un champ existant réaffecté) où vous pourrez saisir le PVC pour ce produit spécifique.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer l'affichage du PVC | OUI | Interrupteur principal pour activer/désactiver la fonction PVC à l'échelle de la boutique. |
| Configuration du module | Afficher le PVC sur la page produit | OUI | Afficher le PVC sur les pages de détails de produits individuelles. |
| Configuration du module | Afficher le PVC sur la liste de produits | OUI | Afficher le PVC sur les pages de catégories/résultats de recherche. |
| Configuration du module | Afficher le prix TTC | OUI | Afficher le PVC taxes incluses (adapté au B2C). |
| Configuration du module | Afficher le prix HT | NON | Afficher le PVC sans taxes (adapté au B2B, éviter les conflits avec 'TTC'). |
| Configuration du module | Afficher les informations « Vous économisez » | OUI | Afficher les économies calculées (PVC - Votre prix). |
| Configuration du module | Champ PVC pour les produits | (Spécifique au module) | Définit quel champ produit dans le BO stocke la valeur du PVC. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai activé le module et saisi les PVC, mais rien ne s'affiche sur ma boutique. Qu'est-ce qui ne va pas ?**
R1 :

- **Vérifier l'activation globale :** Assurez-vous que « Activer l'affichage du PVC » est réglé sur OUI dans la configuration du module.
- **Vérifier les paramètres d'affichage spécifiques :** Vérifiez que « Afficher le PVC sur la page produit » et « Afficher le PVC sur la liste de produits » sont également réglés sur OUI pour les zones où vous vous attendez à le voir.
- **Vider le cache :** PrestaShop utilise la mise en cache. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures).
- **PVC spécifique au produit :** Vérifiez que vous avez réellement saisi une valeur de PVC pour les produits spécifiques que vous testez.
- **Compatibilité du thème :** Parfois, les thèmes très personnalisés peuvent nécessiter des ajustements mineurs pour afficher de nouveaux éléments. Si après avoir vidé le cache cela n'apparaît toujours pas, contactez le support MyPresta.eu.

**Q2 : Le montant « Vous économisez » semble incorrect ou n'apparaît pas.**
R2 :

- **Activer « Vous économisez » :** Assurez-vous que « Afficher les informations « Vous économisez » » est activé dans les paramètres du module.
- **PVC vs. Votre prix :** Le calcul « Vous économisez » dépend à la fois du PVC et du prix de vente de votre produit. Assurez-vous que les deux valeurs sont correctement définies pour le produit. Si votre prix de vente est supérieur ou égal au PVC, aucune économie ne sera affichée.
- **Paramètres de taxe :** Le calcul peut être affecté par le fait que vous affichiez des prix TTC ou HT. Assurez-vous que vos paramètres de taxe sont cohérents.

**Q3 : Comment saisir le PVC pour chaque produit ?**
R3 : Après avoir installé le module, naviguez vers **Catalogue > Produits** dans votre Back Office PrestaShop. Modifiez un produit existant ou créez-en un nouveau. Dans l'interface d'édition du produit, vous devriez trouver un nouveau champ spécifiquement pour le « PVC » (ou un champ existant réaffecté, tel que défini dans la configuration du module). Saisissez-y le prix de vente conseillé par le fabricant et enregistrez le produit.

**Q4 : Le texte du PVC ne correspond pas au design/à la police de ma boutique. Comment puis-je le modifier ?**
R4 : Le module utilise son propre CSS pour le style. Pour des ajustements mineurs (comme la taille de la police, la couleur), vous pouvez souvent remplacer ces styles dans le fichier CSS personnalisé de votre thème (par exemple, `themes/votretheme/assets/css/custom.css` ou `themes/votretheme/css/custom.css`). Pour des changements plus importants, vous pourriez avoir besoin d'un développeur web pour inspecter le CSS du module et appliquer des remplacements plus spécifiques.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Prix de vente conseillé par le fabricant (PVC) » est un module PrestaShop standard conçu pour étendre les fonctionnalités d'affichage des produits du front-office. Il fonctionne principalement en s'accrochant aux points d'affichage PrestaShop existants (comme les pages de produits et les listes de produits) pour injecter les informations sur le PVC. Il utilise le système de configuration de PrestaShop pour ses paramètres et les templates Smarty pour le rendu de la sortie du front-office. La logique principale du module réside dans son fichier PHP principal, gérant l'installation, la désinstallation, la configuration et l'enregistrement des hooks.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la configuration est gérée via la méthode `getContent()` dans le fichier principal du module, et l'affichage du front-office est géré via des hooks et le rendu des templates.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée ou instance `ObjectModel` dans le répertoire `classes/`. Il interagit directement avec les données de produits et la configuration PrestaShop existantes.

### 4.4 Actifs JavaScript (`views/js/`)

- **`msrp/views/admin/js/msrp.js`**

  - **Portée :** Back-office.
  - **Objectif :** Ce script gère probablement tout comportement dynamique ou validation au sein du formulaire de configuration du module dans le Back Office de PrestaShop. Cela pourrait inclure l'affichage/masquage de champs en fonction d'autres sélections, des appels AJAX pour l'enregistrement des paramètres ou la validation côté client.
  - **Détails :** Lie des écouteurs d'événements aux éléments du formulaire de configuration, gère la soumission du formulaire et met potentiellement à jour l'interface utilisateur en fonction de l'entrée de l'utilisateur.
- **`msrp/views/js/msrp.js`**

  - **Portée :** Front-office.
  - **Objectif :** Ce script est responsable de toute interaction côté client ou mise à jour dynamique liée à l'affichage du PVC sur le front-office. Cela pourrait impliquer la mise à jour dynamique du montant « Vous économisez » si les attributs du produit changent (par exemple, la sélection d'une taille/couleur différente qui affecte le prix), ou la gestion de la logique d'affichage.
  - **Détails :** Se lie aux événements `prestashop.on` (par exemple, `updatedProduct` pour les changements de prix de la page produit), manipule les éléments du DOM pour mettre à jour l'affichage du PVC ou des économies, et assure la réactivité.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`msrp/views/admin/css/msrp.css`**

  - **Portée :** Style du formulaire d'administration du Back-office.
  - **Objectif :** Fournit un style spécifique pour la page de configuration du module dans le Back Office de PrestaShop, garantissant une interface cohérente et conviviale.
  - **Sélecteurs clés :** Cible les éléments dans la sortie `getContent()` du module, tels que les champs de formulaire, les étiquettes et les sections.
- **`msrp/views/css/msrp.css`**

  - **Portée :** Style client du Front-office.
  - **Objectif :** Style le PVC affiché, votre prix et les informations « Vous économisez » sur les pages de produits et les listes de produits. Cela garantit que les informations sont clairement visibles et s'intègrent bien au design global de la boutique.
  - **Sélecteurs clés :** Cible des éléments `div` ou `span` spécifiques générés par les templates Smarty du module (par exemple, `.msrp-price`, `.msrp-you-save`, `.msrp-old-price`). Les développeurs peuvent remplacer ces classes dans le `custom.css` de leur thème pour correspondre à leur image de marque.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **`msrp/views/admin/msrp.tpl`**

  - **Portée :** Templates d'administration.
  - **Objectif :** Ce template rend le formulaire de configuration du module dans le Back Office de PrestaShop. Il contient la structure HTML de tous les paramètres décrits dans la Section 4.1.
  - **Détails :** Utilise les composants de formulaire d'aide de PrestaShop (par exemple, `helperForm`) pour créer des champs de saisie, des interrupteurs et des boutons pour les paramètres du module.
- **`msrp/views/templates/msrp-product-list.tpl`**

  - **Portée :** Templates de hook (par exemple, `displayProductPriceBlock` ou similaire pour les listes de produits).
  - **Objectif :** Ce template est responsable de l'affichage des informations sur le PVC sur les pages de liste de produits (catégories, résultats de recherche, etc.). Il reçoit généralement les données du produit et les paramètres de configuration du module pour rendre le PVC, le prix actuel et le message « Vous économisez ».
  - **Détails :** Contient la logique pour vérifier si le PVC est disponible, si « Vous économisez » doit être affiché, et formate les prix selon les paramètres de taxe.
- **`msrp/views/templates/msrp-product-page.tpl`**

  - **Portée :** Templates de hook (par exemple, `displayProductPriceBlock` ou `displayProductButtons` sur les pages de produits).
  - **Objectif :** Ce template rend les informations sur le PVC sur les pages de détails de produits individuelles. Il est conçu pour s'intégrer de manière transparente près du bloc de prix principal du produit.
  - **Détails :** Similaire à `msrp-product-list.tpl`, il gère l'affichage conditionnel du PVC, du prix actuel et des économies, en appliquant les règles de taxe et le formatage.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données :**

  - Ce module ne crée pas de tables SQL personnalisées.
  - Les paramètres de configuration sont stockés dans la table `ps_configuration`, généralement avec des clés préfixées par `MSRP_` (par exemple, `MSRP_ENABLE`, `MSRP_DISPLAY_PRODUCT_PAGE`).
  - Les valeurs de PVC pour les produits sont stockées dans un champ de produit existant, tel que configuré dans le module (par exemple, `ps_product_lang.description_short` ou un champ de produit personnalisé si créé par le module).
- **Table des hooks enregistrés :**
  Le module enregistre des hooks pour injecter son contenu dans le front-office et gérer son cycle de vie.

  | Nom du hook | Moment d'exécution | Objectif technique |
  | --- | --- | --- |
  | `install()` | Lors de l'installation du module | Crée des entrées de configuration, enregistre des hooks, ajoute potentiellement des champs de produit. |
  | `uninstall()` | Lors de la désinstallation du module | Nettoie les entrées de configuration, désenregistre les hooks, supprime les champs de produit. |
  | `displayHeader` | Dans la section `<head>` de chaque page | Injecte les fichiers CSS et JS du module pour l'affichage du front-office. |
  | `displayProductPriceBlock` | Dans le bloc de prix du produit sur les pages de produits et les listes | Hook principal pour le rendu du PVC, du prix actuel et des informations « Vous économisez ». Ce hook est appelé plusieurs fois avec différents paramètres (par exemple, `type='after_price'`). |
  | `actionProductUpdate` | Après la mise à jour d'un produit dans le Back Office | Potentiellement utilisé pour s'assurer que les données du PVC sont correctement enregistrées ou traitées. |
  | `actionProductSave` | Après l'enregistrement d'un produit dans le Back Office | Similaire à `actionProductUpdate`, assure l'intégrité des données du PVC. |
  | `actionProductDelete` | Après la suppression d'un produit | Nettoie toutes les données de PVC associées si elles sont stockées séparément. |
  | `displayAdminProductsExtra` | Dans la page d'édition de produit dans le Back Office | Ajoute le champ de saisie du PVC au formulaire du produit. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et toute assistance supplémentaire concernant le module « Prix de vente conseillé par le fabricant (PVC) », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support et nos développeurs sont prêts à vous aider à maximiser le potentiel de ce module pour votre boutique PrestaShop.
