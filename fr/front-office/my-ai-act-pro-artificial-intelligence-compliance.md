---
title: "My AI Act Pro - Conformité à la loi sur l'IA - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop My AI Act Pro - Conformité à la loi sur l'IA par MyPresta.eu."
sidebar:
  label: "My AI Act Pro - Conformité à la loi sur l'IA - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module My AI Act Pro - Artificial Intelligence Compliance sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/my-ai-act-pro-artificial-intelligence-compliance.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/my-ai-act-pro-artificial-intelligence-compliance/)
>
> ---


# My AI Act Pro - Conformité à la loi sur l'IA

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.6.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL). Assurez-vous que votre serveur répond aux exigences générales de PrestaShop pour des performances optimales.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > My AI Act Pro)

C'est le panneau de contrôle principal de votre module de conformité à la loi sur l'IA. Ici, vous activerez les fonctionnalités, définirez les paramètres globaux et gérerez le comportement général des divulgations de l'IA.

#### Onglet Paramètres généraux

- **Activer la conformité à la loi sur l'IA :**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour l'ensemble du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Toutes les fonctionnalités du module (badges, bannières, journaux, etc.) deviendront actives sur votre boutique selon leurs paramètres individuels.
    - *Lorsqu'il est désactivé :* Le module cessera d'afficher tout contenu lié à la loi sur l'IA sur votre front office, et ses processus d'arrière-plan seront mis en pause.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** Activez-le une fois que vous êtes prêt à mettre en œuvre votre conformité à la loi sur l'IA. Si vous devez désactiver temporairement toutes les divulgations pour la maintenance, désactivez-le.
- **Afficher le badge de divulgation de l'IA sur les pages produit :**

  - **Ce que fait ce paramètre :** Contrôle si le badge de divulgation de l'IA apparaît sur les pages de produits individuelles.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le badge IA sera visible sur les pages de produits pour les produits marqués comme générés par l'IA.
    - *Lorsqu'il est désactivé :* Le badge ne s'affichera pas sur les pages de produits, même si les produits sont signalés.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** C'est crucial pour la transparence directe des produits. Gardez-le activé pour informer les clients directement sur le produit qu'ils consultent.
- **Afficher le badge de divulgation de l'IA sur les listes de produits :**

  - **Ce que fait ce paramètre :** Contrôle si le badge de divulgation de l'IA apparaît sur les pages de catégories, les résultats de recherche ou d'autres vues de listes de produits.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un badge IA plus petit apparaîtra sur les vignettes de produits dans les listes.
    - *Lorsqu'il est désactivé :* Aucun badge n'apparaîtra dans les listes de produits.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** L'activation de cette option offre une transparence immédiate lorsque les clients naviguent, les aidant à identifier le contenu généré par l'IA avant de cliquer sur une page de produit.
- **Position du badge de divulgation de l'IA (page produit) :**

  - **Ce que fait ce paramètre :** Détermine l'emplacement du badge IA sur la page produit. Les options incluent généralement « Au-dessus de l'image du produit », « Sous l'image du produit », « Près du nom du produit », « Dans la description du produit », etc.
  - **Effet de la modification de ce paramètre :** Le badge se déplacera à l'emplacement sélectionné sur la page produit.
  - **Valeur recommandée :** Expérimentez pour trouver la meilleure adaptation à votre thème, souvent « Au-dessus de l'image du produit » ou « Près du nom du produit » pour la visibilité.
  - **Scénario / exemple de marchand :** Si vos images de produits sont très grandes, placer le badge « Sous l'image du produit » pourrait être moins intrusif. Si vous voulez qu'il soit immédiatement visible, « Au-dessus de l'image du produit » est préférable.
- **Mise en page du badge de divulgation de l'IA :**

  - **Ce que fait ce paramètre :** Vous permet de choisir un style visuel prédéfini pour le badge IA à partir du « Studio de mise en page ».
  - **Effet de la modification de ce paramètre :** L'apparence du badge IA (icône, texte, couleurs, forme) changera en fonction de la mise en page sélectionnée.
  - **Valeur recommandée :** Sélectionnez une mise en page qui correspond à l'image de marque de votre boutique et qui est clairement visible.
  - **Scénario / exemple de marchand :** Vous pourriez créer une mise en page personnalisée avec les couleurs de votre marque et une icône spécifique pour vous assurer que le badge a l'air professionnel et s'intègre bien.
- **Lien vers la page de politique d'IA :**

  - **Ce que fait ce paramètre :** Vous permet de lier à une page CMS dédiée ou à une URL externe expliquant la politique d'IA de votre boutique.
  - **Effet de la modification de ce paramètre :** Le module utilisera cette URL lors de la liaison à votre politique d'IA à partir de badges, de bannières ou d'autres éléments de divulgation.
  - **Valeur recommandée :** Créez une page CMS détaillée (par exemple, « Notre politique de transparence de l'IA ») et liez-la ici.
  - **Scénario / exemple de marchand :** Ce lien est crucial pour fournir des informations complètes aux clients qui souhaitent en savoir plus sur votre utilisation de l'IA.
- **Activer la bannière de divulgation de l'IA :**

  - **Ce que fait ce paramètre :** Active une bannière à l'échelle du site pour informer les clients de votre utilisation de l'IA.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Une bannière apparaîtra dans le hook sélectionné (par exemple, en-tête ou pied de page).
    - *Lorsqu'il est désactivé :* Aucune bannière ne sera affichée.
  - **Valeur recommandée :** OUI, surtout pour le déploiement initial ou si votre boutique utilise l'IA de manière extensive.
  - **Scénario / exemple de marchand :** Utilisez cette bannière pour faire une déclaration générale sur la politique d'IA de votre boutique, en la liant peut-être à votre page de politique dédiée.
- **Position de la bannière de divulgation de l'IA (Hook) :**

  - **Ce que fait ce paramètre :** Sélectionne l'endroit où la bannière apparaîtra (par exemple, `displayHeader`, `displayFooter`).
  - **Effet de la modification de ce paramètre :** La bannière sera rendue à l'emplacement choisi.
  - **Valeur recommandée :** `displayHeader` pour une visibilité maximale, ou `displayFooter` pour une approche moins intrusive.
  - **Scénario / exemple de marchand :** Le placer dans `displayHeader` garantit que chaque visiteur le voit immédiatement en arrivant sur votre site.
- **Contenu de la bannière de divulgation de l'IA :**

  - **Ce que fait ce paramètre :** Vous permet de personnaliser le texte et le contenu HTML de la bannière.
  - **Effet de la modification de ce paramètre :** La bannière affichera votre message personnalisé.
  - **Valeur recommandée :** Un message concis comme « Nous utilisons l'IA pour améliorer votre expérience d'achat. [En savoir plus] » avec un lien vers votre page de politique.
  - **Scénario / exemple de marchand :** Vous pouvez l'utiliser pour expliquer brièvement votre utilisation de l'IA et diriger les clients vers votre politique complète.
- **Activer les informations de repli humain :**

  - **Ce que fait ce paramètre :** Affiche un message indiquant une supervision humaine ou offrant une assistance humaine pour le contenu généré par l'IA.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un message configurable apparaîtra sur les pages pertinentes.
    - *Lorsqu'il est désactivé :* Aucun message de repli humain ne sera affiché.
  - **Valeur recommandée :** OUI, si vous souhaitez rassurer les clients sur l'implication d'une révision humaine ou fournir un point de contact.
  - **Scénario / exemple de marchand :** Si vos descriptions de produits générées par l'IA sont toujours révisées par un éditeur humain, vous pouvez l'utiliser pour indiquer « Tout le contenu généré par l'IA est révisé par notre équipe. Contactez-nous si vous avez des questions. »
- **Message de repli humain :**

  - **Ce que fait ce paramètre :** Personnalise le texte pour les informations de repli humain.
  - **Effet de la modification de ce paramètre :** Le message sera affiché tel qu'il a été saisi.
  - **Valeur recommandée :** Un message clair et rassurant.
  - **Scénario / exemple de marchand :** « Nos outils d'IA sont supervisés par des experts humains. Pour toute préoccupation, veuillez contacter notre service client. »
- **Activer le journal d'audit :**

  - **Ce que fait ce paramètre :** Enregistre toutes les actions et divulgations liées à la loi sur l'IA dans un journal à des fins de conformité.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Chaque fois qu'une divulgation d'IA est faite ou qu'un produit est signalé, une entrée est enregistrée dans le journal d'audit du module.
    - *Lorsqu'il est désactivé :* Aucune piste d'audit ne sera conservée.
  - **Valeur recommandée :** OUI, c'est crucial pour démontrer la conformité et le dépannage.
  - **Scénario / exemple de marchand :** Si un organisme de réglementation demande une preuve de vos divulgations d'IA, le journal d'audit fournit un enregistrement historique.

#### Onglet API et intégrations

- **Activer l'API REST :**

  - **Ce que fait ce paramètre :** Active un point de terminaison d'API REST pour que les systèmes externes interagissent avec le module (par exemple, pour marquer des produits comme générés par l'IA).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* L'API devient active, permettant une interaction programmatique.
    - *Lorsqu'il est désactivé :* L'API est inactive.
  - **Valeur recommandée :** NON, sauf si vous avez un besoin technique spécifique d'intégration avec des outils ou des systèmes d'IA externes.
  - **Scénario / exemple de marchand :** Si vous utilisez un service externe de génération d'images par IA, vous pouvez utiliser l'API pour marquer automatiquement les images comme générées par l'IA dans PrestaShop.
- **Gestion des clés API :**

  - **Ce que fait ce paramètre :** Vous permet de générer et de gérer des clés API pour un accès sécurisé à l'API REST du module.
  - **Effet de la modification de ce paramètre :** De nouvelles clés peuvent être créées, les clés existantes révoquées, contrôlant qui peut accéder à l'API.
  - **Valeur recommandée :** Générez une clé forte et unique pour chaque intégration.
  - **Scénario / exemple de marchand :** Créez une clé API spécifique pour votre générateur d'images IA et une autre pour votre rédacteur de contenu IA, en les révoquant si une intégration n'est plus nécessaire.
- **Activer le CRON de filigrane :**

  - **Ce que fait ce paramètre :** Active une tâche planifiée (tâche CRON) pour appliquer automatiquement des filigranes aux images générées par l'IA.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* La tâche CRON s'exécutera périodiquement, appliquant un filigrane configurable aux images signalées.
    - *Lorsqu'il est désactivé :* Aucun filigrane automatique ne sera appliqué.
  - **Valeur recommandée :** NON, sauf si vous avez spécifiquement besoin de filigranes pour les images IA.
  - **Scénario / exemple de marchand :** Si vous souhaitez un indicateur visuel directement sur l'image elle-même (par exemple, un petit logo « IA ») pour toutes les images de produits générées par l'IA, activez cette option.
- **Image/Texte du filigrane :**

  - **Ce que fait ce paramètre :** Définit le filigrane à appliquer (par exemple, un fichier image ou une chaîne de texte).
  - **Effet de la modification de ce paramètre :** La tâche CRON utilisera ce filigrane.
  - **Valeur recommandée :** Un indicateur subtil et clair s'il est utilisé.
  - **Scénario / exemple de marchand :** Téléchargez une petite image semi-transparente « Généré par l'IA » ou saisissez « IA » comme texte.

#### Onglet Shortcodes

- **Liste et utilisation des shortcodes :**
  - **Ce que fait ce paramètre :** Fournit une liste de shortcodes disponibles qui peuvent être insérés dans les descriptions de produits, les pages CMS ou d'autres zones de texte.
  - **Effet de la modification de ce paramètre :** Aucun changement direct, mais l'utilisation de ces shortcodes dans votre contenu affichera les éléments de divulgation d'IA correspondants.
  - **Valeur recommandée :** Utilisez ces shortcodes pour intégrer des divulgations spécifiques là où les paramètres globaux pourraient ne pas suffire.
  - **Scénario / exemple de marchand :** Vous pourriez avoir un produit où seul un paragraphe spécifique de la description a été généré par l'IA. Vous pouvez envelopper ce paragraphe avec un shortcode pour afficher un petit badge à côté.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 Loi sur l'IA > Gestion de produits en masse (AdminMyAiActBulkController)

- **Nom de l'écran et emplacement du menu :** Dans votre Back Office PrestaShop, naviguez vers **Loi sur l'IA > Gestion de produits en masse**.
- **Actions et paramètres disponibles :** Cet écran fournit une vue en grille puissante pour gérer le statut de conformité à la loi sur l'IA de plusieurs produits à la fois.
  - **Liste de produits :** Affiche une liste de tous vos produits avec des colonnes pour le nom du produit, l'ID et, surtout, leur statut de conformité à la loi sur l'IA.
  - **Filtres et recherche :** Vous permet de filtrer les produits par divers critères (par exemple, catégorie, fournisseur, statut de conformité à la loi sur l'IA) pour trouver rapidement des articles spécifiques.
  - **Actions en masse :**
    - **Marquer comme généré par l'IA :** Sélectionnez plusieurs produits et appliquez-leur simultanément le drapeau « généré par l'IA ».
    - **Démarquer comme généré par l'IA :** Supprimez le drapeau « généré par l'IA » des produits sélectionnés.
    - **Appliquer des balises spécifiques à la loi sur l'IA :** Attribuez des balises ou des règles personnalisées (si configurées) à plusieurs produits.
- **Effet des modifications :**
  - Lorsque vous marquez des produits comme générés par l'IA, les badges et les divulgations du front-office apparaîtront pour ces produits conformément aux paramètres généraux de votre module.
  - Le fait de démarquer les produits supprime ces divulgations.
  - L'application de balises permet un contrôle plus granulaire sur des types de divulgation ou des messages spécifiques.
- **Flux de travail recommandé pour la gestion quotidienne du magasin :**
  1. Après avoir importé de nouveaux produits ou généré du contenu avec l'IA, utilisez les filtres pour localiser rapidement ces produits.
  2. Sélectionnez tous les produits pertinents à l'aide des cases à cocher.
  3. Utilisez l'action en masse « Marquer comme généré par l'IA » pour appliquer le drapeau.
  4. Examinez périodiquement les produits pour vous assurer que leur statut de conformité à la loi sur l'IA est exact.

#### 2.2.2 Loi sur l'IA > Journaux d'audit (AdminMyAiActLogsController)

- **Nom de l'écran et emplacement du menu :** Dans votre Back Office PrestaShop, naviguez vers **Loi sur l'IA > Journaux d'audit**.
- **Actions et paramètres disponibles :** Cet écran affiche un journal détaillé de tous les événements et divulgations liés à la loi sur l'IA, à condition que le paramètre « Activer le journal d'audit » soit actif.
  - **Entrées de journal :** Chaque entrée comprend généralement :
    - **Horodatage :** Quand l'événement s'est produit.
    - **Action/Événement :** Ce qui s'est passé (par exemple, « Produit X marqué comme IA », « Badge IA affiché pour le produit Y »).
    - **Utilisateur/Système :** Qui a initié l'action (par exemple, « Utilisateur admin Z », « Tâche CRON », « Visiteur du Front Office »).
    - **ID produit/Contexte :** Quel produit ou entité a été affecté.
    - **Détails :** Toute information pertinente supplémentaire.
  - **Filtres et recherche :** Vous permet de filtrer les entrées de journal par plage de dates, type d'événement ou produit pour enquêter sur des incidents spécifiques.
- **Effet des modifications :** Cet écran est uniquement destiné à la visualisation ; vous ne pouvez pas y apporter de modifications directes. Il sert de registre historique.
- **Flux de travail recommandé pour la gestion quotidienne du magasin :**
  1. Examinez régulièrement les journaux d'audit, surtout après avoir apporté des modifications importantes aux paramètres de la loi sur l'IA ou aux données des produits, pour vous assurer que tout fonctionne comme prévu.
  2. En cas d'audit de conformité ou de demande de client, utilisez ce journal pour récupérer des événements de divulgation spécifiques.

#### 2.2.3 Loi sur l'IA > Studio de mise en page (AdminMyAiActLayoutsController - *Déduit des modèles et de la description*)

- **Nom de l'écran et emplacement du menu :** Dans votre Back Office PrestaShop, naviguez vers **Loi sur l'IA > Studio de mise en page** (ou similaire, basé sur la structure du menu du module).
- **Actions et paramètres disponibles :** Cet écran est l'endroit où vous concevez et gérez l'apparence visuelle de vos badges de divulgation d'IA et d'autres éléments.
  - **Liste des mises en page :** Un tableau affichant toutes les mises en page de badges existantes.
  - **Ajouter une nouvelle mise en page / Modifier une mise en page :**
    - **Nom de la mise en page :** Un nom descriptif pour votre mise en page.
    - **Type de badge :** Choisissez entre icône uniquement, texte uniquement ou icône + texte.
    - **Sélecteur d'icônes :** Sélectionnez dans un catalogue d'icônes ou téléchargez la vôtre.
    - **Contenu textuel :** Saisissez le texte à afficher sur le badge (par exemple, « Généré par l'IA »).
    - **Options de style :**
      - **Couleurs :** Couleur d'arrière-plan, couleur du texte, couleur de l'icône.
      - **Bordures :** Style de bordure, largeur, couleur.
      - **Ombres :** Effets d'ombre portée.
      - **Dégradés :** Options de dégradé d'arrière-plan.
      - **Rembourrage et marges :** Espacement autour du badge.
      - **Paramètres de police :** Taille de police, graisse.
    - **Aperçu :** Un aperçu en direct de votre badge au fur et à mesure que vous le concevez.
- **Effet des modifications :**
  - La création de nouvelles mises en page vous offre plus d'options pour l'apparence de vos divulgations d'IA.
  - La modification d'une mise en page existante mettra immédiatement à jour l'apparence de tous les badges utilisant cette mise en page dans votre boutique.
- **Flux de travail recommandé pour la gestion quotidienne du magasin :**
  1. Commencez par une mise en page par défaut et personnalisez-la pour qu'elle corresponde à l'esthétique de votre marque.
  2. Créez différentes mises en page pour différents types de divulgations d'IA si nécessaire (par exemple, une pour les images d'IA, une autre pour le texte d'IA).
  3. Testez les mises en page sur différents appareils pour vous assurer qu'elles sont visibles et qu'elles ont une belle apparence.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activer la conformité à la loi sur l'IA | OUI | Interrupteur principal pour toutes les fonctionnalités du module. |
|  | Afficher le badge de divulgation de l'IA sur les pages produit | OUI | Affiche le badge sur les pages de détails du produit. |
|  | Afficher le badge de divulgation de l'IA sur les listes de produits | OUI | Affiche le badge sur les pages de catégorie/recherche. |
|  | Position du badge de divulgation de l'IA (page produit) | *Dépend du thème* | Contrôle le placement du badge sur les pages produit. |
|  | Mise en page du badge de divulgation de l'IA | *Personnalisable* | Style visuel du badge IA. |
|  | Lien vers la page de politique d'IA | *URL de votre page CMS* | Lien vers la politique d'IA de votre boutique. |
|  | Activer la bannière de divulgation de l'IA | OUI | Active une bannière d'information à l'échelle du site. |
|  | Position de la bannière de divulgation de l'IA (Hook) | `displayHeader` | Placement de la bannière (par exemple, haut/bas de page). |
|  | Contenu de la bannière de divulgation de l'IA | *Texte/HTML personnalisable* | Message affiché dans la bannière. |
|  | Activer les informations de repli humain | OUI | Affiche un message sur la supervision humaine. |
|  | Message de repli humain | *Texte personnalisable* | Contenu du message de repli humain. |
|  | Activer le journal d'audit | OUI | Enregistre toutes les actions liées à la loi sur l'IA pour la conformité. |
|  | Activer l'API REST | NON | Active l'API pour les intégrations externes. |
|  | Gestion des clés API | *N/A* | Générer/gérer les clés API pour un accès sécurisé. |
|  | Activer le CRON de filigrane | NON | Applique automatiquement des filigranes aux images générées par l'IA. |
|  | Image/Texte du filigrane | *N/A* | Définit le contenu du filigrane. |
|  | Liste et utilisation des shortcodes | *N/A* | Fournit des shortcodes pour une divulgation de contenu granulaire. |
| **Loi sur l'IA > Gestion de produits en masse** | Marquer comme généré par l'IA (Action en masse) | N/A | Marque plusieurs produits comme générés par l'IA. |
|  | Démarquer comme généré par l'IA (Action en masse) | N/A | Supprime le drapeau "généré par l'IA" des produits. |
|  | Appliquer des balises spécifiques à la loi sur l'IA (Action en masse) | N/A | Attribue des balises de divulgation personnalisées aux produits. |
| **Loi sur l'IA > Journaux d'audit** | Afficher les entrées de journal | N/A | Fournit un enregistrement historique des événements de la loi sur l'IA. |
| **Loi sur l'IA > Studio de mise en page** | Créer/Modifier des mises en page | N/A | Concevoir des styles visuels personnalisés pour les badges IA. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai configuré le module, mais je ne vois aucun badge ou bannière IA sur ma boutique. Qu'est-ce qui ne va pas ?**
R1 :

- **Vérifier l'interrupteur principal :** Tout d'abord, assurez-vous que « Activer la conformité à la loi sur l'IA » est réglé sur OUI dans la configuration principale du module.
- **Interrupteurs de fonctionnalités individuelles :** Vérifiez que « Afficher le badge de divulgation de l'IA sur les pages produit », « Afficher le badge de divulgation de l'IA sur les listes de produits » et « Activer la bannière de divulgation de l'IA » sont également réglés sur OUI si vous souhaitez que ces fonctionnalités soient actives.
- **Statut du produit :** Pour que les badges apparaissent, les produits doivent être explicitement marqués comme « générés par l'IA ». Vérifiez cela sur la page d'édition du produit (sous un onglet dédié) ou via « Loi sur l'IA > Gestion de produits en masse ».
- **Cache :** Videz le cache de votre PrestaShop (Paramètres avancés > Performances > Vider le cache) et le cache de votre navigateur. Parfois, du contenu ancien est affiché.
- **Compatibilité du thème :** Bien que le module soit conçu pour être compatible, certains thèmes très personnalisés peuvent nécessiter des ajustements mineurs. Vérifiez la console de développement de votre navigateur pour les erreurs JavaScript.

**Q2 : Le badge IA apparaît, mais il ne s'harmonise pas bien avec le design de mon thème. Comment puis-je modifier son apparence ?**
R2 :

- **Studio de mise en page :** Naviguez vers **Loi sur l'IA > Studio de mise en page** dans votre Back Office. Ici, vous pouvez créer et modifier des mises en page de badges. Vous disposez de nombreuses options pour les couleurs, les icônes, le texte, les ombres et les dégradés.
- **Sélectionner la mise en page :** Après avoir créé ou modifié une mise en page, revenez à la configuration principale du module et sélectionnez la mise en page souhaitée sous « Mise en page du badge de divulgation de l'IA ».
- **Substitutions CSS (Avancé) :** Si le Studio de mise en page n'offre pas suffisamment de personnalisation, un webmaster peut utiliser du CSS personnalisé dans votre thème pour remplacer les styles par défaut du module (voir la section 7.5 pour les emplacements des fichiers CSS).

**Q3 : Comment puis-je marquer efficacement les produits comme générés par l'IA, surtout si j'en ai beaucoup ?**
R3 :

- **Gestion de produits en masse :** Allez dans **Loi sur l'IA > Gestion de produits en masse**. Cet écran vous permet de filtrer vos produits et de sélectionner plusieurs articles pour les marquer ou les démarquer comme générés par l'IA en une seule fois. C'est la méthode la plus efficace pour les grands catalogues.
- **Page produit individuelle :** Pour les produits individuels, vous trouverez un onglet dédié (par exemple, « Conformité à la loi sur l'IA ») lors de la modification d'un produit dans le Back Office, où vous pouvez basculer son statut IA.

**Q4 : Je souhaite fournir une explication détaillée de ma politique d'IA. Où dois-je la mettre ?**
R4 :

- **Page CMS dédiée :** Créez une nouvelle page CMS (Design > Pages) intitulée par exemple « Notre politique de transparence de l'IA » ou « Comment nous utilisons l'IA ». Rédigez votre politique complète ici.
- **Lien dans le module :** Dans la configuration principale du module, définissez le « Lien vers la page de politique d'IA » sur l'URL de votre nouvelle page CMS. Ce lien sera ensuite utilisé par les bannières et les badges pour diriger les clients vers votre politique.

**Q5 : La tâche CRON pour le filigrane ne fonctionne pas. Que dois-je vérifier ?**
R5 :

- **Activer le CRON de filigrane :** Assurez-vous que « Activer le CRON de filigrane » est réglé sur OUI dans la configuration du module.
- **Configuration de la tâche CRON :** Vérifiez que la tâche CRON elle-même est correctement configurée sur votre serveur. Le module fournit généralement la ligne de commande exacte à ajouter au gestionnaire CRON de votre panneau d'hébergement. Si vous n'êtes pas sûr, contactez votre hébergeur ou un webmaster.
- **Permissions :** Assurez-vous que le module et les dossiers d'images ont les bonnes permissions d'écriture.
- **Journaux d'erreurs :** Vérifiez les journaux d'erreurs PHP de votre serveur et le mode débogage de PrestaShop pour toute erreur connexe.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « My AI Act Pro » suit l'architecture MVC (Modèle-Vue-Contrôleur) standard de PrestaShop. Il utilise `ObjectModel` pour les interactions avec la base de données, enregistre divers hooks pour l'affichage en front-office et inclut des contrôleurs d'administration dédiés pour la configuration et la gestion des données. Le module introduit plusieurs classes personnalisées pour encapsuler la logique métier spécifique liée à la conformité à la loi sur l'IA, telles que la gestion de l'API, la gestion de la mise en page des badges et la journalisation d'audit. Il comprend également des contrôleurs frontaux pour l'API et l'exécution des tâches CRON, permettant des intégrations externes et des tâches planifiées.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `controllers/front/api.php`
  - **Nom de la classe et classe parente :** `MyaiactproApiModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur gère les points de terminaison de l'API REST du module. Il traite les requêtes entrantes (par exemple, pour marquer des produits comme générés par l'IA, récupérer le statut de l'IA) et renvoie des réponses JSON. Il est responsable de la validation des clés API et de la répartition des requêtes vers les méthodes appropriées de la classe `AiActApi`.
- `controllers/front/cron.php`
  - **Nom de la classe et classe parente :** `MyaiactproCronModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur sert de point de terminaison pour les tâches CRON du module, spécifiquement pour l'application de filigrane. Lorsqu'il est accédé via une tâche planifiée, il déclenche le processus de filigrane pour les images générées par l'IA.
- `controllers/front/index.php`
  - **Nom de la classe et classe parente :** `MyaiactproIndexModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Un contrôleur frontal de substitution ou par défaut. Dans de nombreux modules, cela pourrait gérer une route par défaut ou une redirection. Pour ce module, il pourrait s'agir d'un repli ou être utilisé pour des interactions front-office spécifiques et simples non couvertes par `api.php` ou `cron.php`.

#### Contrôleurs d'administration Back-Office

- `controllers/admin/AdminMyAiActBulkController.php`
  - **Nom de la classe et classe parente :** `AdminMyAiActBulkController` étend `ModuleAdminController`.
  - **Nom de l'onglet et entité gérée :** Accessible via **Loi sur l'IA > Gestion de produits en masse**. Gère indirectement l'entité `product` en permettant des mises à jour en masse de leur statut de conformité à la loi sur l'IA.
  - **Responsabilité :** Fournit une interface de grille pour lister les produits et appliquer des actions en masse liées à la conformité à la loi sur l'IA (par exemple, marquer des produits comme générés par l'IA, appliquer des balises). Il gère les soumissions de formulaires pour les mises à jour en masse.
- `controllers/admin/AdminMyAiActLogsController.php`
  - **Nom de la classe et classe parente :** `AdminMyAiActLogsController` étend `ModuleAdminController`.
  - **Nom de l'onglet et entité gérée :** Accessible via **Loi sur l'IA > Journaux d'audit**. Gère l'entité `aiact_audit_log`.
  - **Responsabilité :** Affiche une liste paginée des entrées du journal d'audit, fournissant un enregistrement historique des événements liés à la loi sur l'IA. Il gère le filtrage et la visualisation des détails du journal.
- `controllers/admin/index.php`
  - **Nom de la classe et classe parente :** `MyaiactproAdminIndexModuleAdminController` étend `ModuleAdminController`.
  - **Nom de l'onglet et entité gérée :** Généralement un contrôleur d'administration par défaut ou d'introduction pour l'entrée de menu principale du module.
  - **Responsabilité :** Peut servir de redirection vers la configuration principale ou un tableau de bord pour le module.

### 4.3 Classes et modèles de base (`classes/`)

- `classes/AiActApi.php`
  - **Table de base de données :** Aucune interaction directe avec la table, mais interagit avec `AiActApiKey` et `AiActAuditLog`.
  - **Étend `ObjectModel` :** Non.
  - **Méthodes publiques clés :** Gère l'analyse des requêtes API, l'authentification et distribue les actions pour mettre à jour le statut IA du produit.
- `classes/AiActApiDocumentation.php`
  - **Table de base de données :** Aucune.
  - **Étend `ObjectModel` :** Non.
  - **Méthodes publiques clés :** Génère et fournit la documentation pour l'API REST du module, généralement pour l'affichage dans le Back Office.
- `classes/AiActApiKey.php`
  - **Table de base de données :** `ps_myaiactpro_api_key`
  - **Étend `ObjectModel` :** Oui.
  - **Champs `$definition` :** `id_myaiactpro_api_key`, `key_value`, `description`, `active`, `date_add`, `date_upd`.
  - **Méthodes publiques clés :** Gère la création, la récupération, la validation et la suppression des clés API pour un accès sécurisé à l'API.
- `classes/AiActAuditLog.php`
  - **Table de base de données :** `ps_myaiactpro_audit_log`
  - **Étend `ObjectModel` :** Oui.
  - **Champs `$definition` :** `id_myaiactpro_audit_log`, `id_employee`, `id_customer`, `id_product`, `action`, `details`, `ip_address`, `date_add`.
  - **Méthodes publiques clés :** Enregistre et récupère les entrées du journal d'audit pour les actions de conformité à la loi sur l'IA.
- `classes/AiActBadgeLayout.php`
  - **Table de base de données :** `ps_myaiactpro_badge_layout`
  - **Étend `ObjectModel` :** Oui.
  - **Champs `$definition` :** `id_myaiactpro_badge_layout`, `name`, `type`, `icon_class`, `text_content`, `styles_json`, `active`.
  - **Méthodes publiques clés :** Gère la création, le stockage et la récupération des mises en page visuelles personnalisées pour les badges de divulgation d'IA.
- `classes/AiActConfigureUi.php`
  - **Table de base de données :** Aucune.
  - **Étend `ObjectModel` :** Non.
  - **Méthodes publiques clés :** Classe d'aide pour la construction et le rendu des formulaires de configuration du module dans le Back Office, en abstraisant les éléments d'interface utilisateur.
- `classes/AiActDisplayResolver.php`
  - **Table de base de données :** Aucune.
  - **Étend `ObjectModel` :** Non.
  - **Méthodes publiques clés :** Détermine quelles divulgations de la loi sur l'IA (badges, bannières, etc.) doivent être affichées sur le front office en fonction des paramètres du module, du statut du produit et du contexte actuel.
- `classes/AiActFlag.php`
  - **Table de base de données :** `ps_myaiactpro_product_flag` (ou similaire, liant les produits au statut IA)
  - **Étend `ObjectModel` :** Oui (probablement, ou une classe personnalisée gérant les relations produit-statut IA).
  - **Champs `$definition` :** `id_product`, `is_ai_generated`, `id_myaiactpro_badge_layout`, `date_add`, `date_upd`.
  - **Méthodes publiques clés :** Gère le statut généré par l'IA des produits individuels et leurs mises en page de badges associées.
- `classes/AiActIconCatalog.php`
  - **Table de base de données :** Aucune.
  - **Étend `ObjectModel` :** Non.
  - **Méthodes publiques clés :** Fournit une liste ou un catalogue d'icônes disponibles pour une utilisation dans les mises en page de badges, s'intégrant souvent à Font Awesome ou à des bibliothèques d'icônes similaires.
- `classes/AiActShortcode.php`
  - **Table de base de données :** Aucune.
  - **Étend `ObjectModel` :** Non.
  - **Méthodes publiques clés :** Traite et rend les shortcodes personnalisés intégrés dans le contenu, en les remplaçant par des éléments de divulgation d'IA.
- `classes/AiActTagRule.php`
  - **Table de base de données :** `ps_myaiactpro_tag_rule` (ou similaire pour les balises/règles personnalisées)
  - **Étend `ObjectModel` :** Oui.
  - **Champs `$definition` :** `id_myaiactpro_tag_rule`, `name`, `description`, `badge_layout_id`, `active`.
  - **Méthodes publiques clés :** Gère les règles ou balises personnalisées qui peuvent être appliquées aux produits pour des divulgations d'IA plus spécifiques au-delà d'un simple drapeau « généré par l'IA ».
- `classes/index.php`
  - **Table de base de données :** Aucune.
  - **Étend `ObjectModel` :** Non.
  - **Méthodes publiques clés :** Généralement un fichier vide pour empêcher la liste des répertoires.

### 4.4 Actifs JavaScript (`views/js/`)

- `lib/searchTool/views/js/autocomplete.js`
  - **Portée :** Back-office (probablement pour la recherche de produits en gestion de masse).
  - **Description :** Fournit une fonctionnalité d'autocomplétion pour les champs de saisie, généralement utilisée dans les formulaires d'administration pour rechercher des produits, des catégories ou d'autres entités.
- `views/js/admin_api.js`
  - **Portée :** Back-office (onglet API et intégrations).
  - **Description :** Gère les interactions côté client pour l'interface de gestion des clés API, y compris la génération de nouvelles clés, la révocation de clés et l'affichage des modales de documentation API.
- `views/js/admin_icon_picker.js`
  - **Portée :** Back-office (Studio de mise en page).
  - **Description :** Gère l'interface de sélection d'icônes dans le Studio de mise en page, permettant aux administrateurs de parcourir et de sélectionner des icônes pour les badges.
- `views/js/admin_layouts.js`
  - **Portée :** Back-office (Studio de mise en page).
  - **Description :** Alimente l'interface du Studio de mise en page, gérant les mises à jour d'aperçu en temps réel, les ajustements de style (couleurs, ombres, dégradés) et les soumissions de formulaires pour les mises en page de badges.
- `views/js/front.js`
  - **Portée :** Front-office.
  - **Description :** Contient la logique côté client pour l'affichage et l'interaction avec les éléments de divulgation d'IA sur le front office. Cela peut inclure :
    - L'initialisation des info-bulles ou des popovers de badges.
    - La gestion des événements de clic sur les badges pour révéler plus d'informations ou naviguer vers la page de politique d'IA.
    - L'assurance de la réactivité mobile des éléments de divulgation.
- `views/js/tinymce_ai_button.js`
  - **Portée :** Back-office (éditeur de produit/CMS).
  - **Description :** Intègre un bouton personnalisé dans l'éditeur TinyMCE (utilisé pour les descriptions de produits et les pages CMS) pour insérer facilement des shortcodes de la loi sur l'IA.

### 4.5 Feuilles de style CSS (`views/css/`)

- `lib/searchTool/views/css/autocomplete.css`
  - **Portée :** Back-office.
  - **Description :** Styles pour les champs de saisie de recherche à autocomplétion et leurs résultats déroulants, utilisés dans les formulaires d'administration.
- `views/css/admin.css`
  - **Portée :** Style des formulaires d'administration du Back-office.
  - **Description :** Contient les règles de style générales pour les interfaces Back Office du module, y compris la page de configuration, la gestion en masse, les journaux d'audit et le studio de mise en page. Les développeurs peuvent remplacer des classes comme `.myaiactpro-admin-form`, `.myaiactpro-layout-preview`, etc.
- `views/css/front.css`
  - **Portée :** Style client du Front-office.
  - **Description :** Fournit le style par défaut pour les badges de divulgation d'IA, les bannières et d'autres éléments du front-office. Les sélecteurs de classe CSS clés que les développeurs peuvent remplacer dans leur thème incluent :
    - `.myaiactpro-badge` (pour le conteneur principal du badge)
    - `.myaiactpro-badge-icon` (pour l'icône dans le badge)
    - `.myaiactpro-badge-text` (pour le texte dans le badge)
    - `.myaiactpro-banner` (pour la bannière de divulgation à l'échelle du site)
    - `.myaiactpro-additional-info` (pour les blocs d'informations supplémentaires)
    - `.myaiactpro-human-fallback` (pour les messages de repli humain)

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)

- `hook/additional_info.tpl`
  - **Hook :** Potentiellement `displayProductExtraContent` ou un hook personnalisé.
  - **Sortie :** Rend un bloc d'informations supplémentaires sur la page produit, souvent utilisé pour des divulgations détaillées sur l'IA ou des liens vers la politique.
- `hook/ai_badge.tpl`
  - **Hook :** `displayProductListReviews`, `displayProductButtons`, `displayProductPriceBlock`, ou des hooks personnalisés.
  - **Sortie :** Rend le badge de divulgation de l'IA sur les pages de produits ou les listes, en utilisant la mise en page sélectionnée.
- `hook/banner.tpl`
  - **Hook :** `displayHeader`, `displayFooter`.
  - **Sortie :** Rend la bannière de divulgation de l'IA à l'échelle du site.
- `hook/human_fallback.tpl`
  - **Hook :** Potentiellement `displayProductExtraContent` ou un hook personnalisé.
  - **Sortie :** Rend le message de repli humain sur les pages pertinentes.
- `hook/shortcode_badge.tpl`
  - **Hook :** Rendu dynamiquement par la classe `AiActShortcode`.
  - **Sortie :** Rend un badge IA spécifique lorsqu'un shortcode est utilisé dans le contenu.

#### Modèles d'administration (`views/templates/admin/`)

- `admin/api.tpl`
  - **Objectif :** Rend le panneau de configuration API et Intégrations, y compris la gestion des clés API et la documentation.
- `admin/bulk_intro.tpl`
  - **Objectif :** Fournit un message d'introduction ou des instructions pour l'écran de gestion de produits en masse.
- `admin/configure.tpl`
  - **Objectif :** Le modèle de configuration principal du module, rendu par `getContent()`, contenant les paramètres généraux, les bascules de fonctionnalités et les liens vers d'autres écrans d'administration.
- `admin/configure_shell.tpl`
  - **Objectif :** Un modèle d'enveloppe ou de shell pour la page de configuration principale, offrant une mise en page cohérente.
- `admin/cron_box.tpl`
  - **Objectif :** Affiche des informations relatives à la configuration de la tâche CRON, y compris la commande CRON.
- `admin/layouts_form.tpl`
  - **Objectif :** Rend le formulaire de création ou de modification d'une mise en page de badge IA dans le Studio de mise en page.
- `admin/layouts_list.tpl`
  - **Objectif :** Affiche la liste des mises en page de badges IA existantes dans le Studio de mise en page.
- `admin/mass_settings.tpl`
  - **Objectif :** Rend l'interface pour appliquer des paramètres ou des actions en masse aux produits, utilisée dans le contrôleur de gestion en masse.
- `admin/overrides_entity.tpl`
  - **Objectif :** Probablement pour gérer des remplacements ou des exceptions spécifiques pour les règles de la loi sur l'IA par entité (par exemple, par catégorie, par fabricant).
- `admin/overrides_fields.tpl`
  - **Objectif :** Rend les champs de formulaire pour définir les règles de remplacement.
- `admin/overrides_list.tpl`
  - **Objectif :** Affiche une liste des règles de remplacement configurées.
- `admin/partials/gradient_editor.tpl`
  - **Objectif :** Un modèle partiel pour le sélecteur/éditeur de couleur de dégradé utilisé dans le Studio de mise en page.
- `admin/partials/icon_picker.tpl`
  - **Objectif :** Un modèle partiel pour l'interface de sélection d'icônes utilisée dans le Studio de mise en page.
- `admin/partials/shadow_editor.tpl`
  - **Objectif :** Un modèle partiel pour l'éditeur d'effets d'ombre utilisé dans le Studio de mise en page.
- `admin/product_tab.tpl`
  - **Objectif :** Rend le contenu de l'onglet dédié « Conformité à la loi sur l'IA » dans la page d'édition de produit de PrestaShop.
- `admin/shortcodes.tpl`
  - **Objectif :** Affiche la liste des shortcodes disponibles et leurs instructions d'utilisation.
- `admin/_api_documentation_modal.tpl`
  - **Objectif :** Rend le contenu d'une fenêtre modale affichant la documentation de l'API.

#### Modèles Front-office (`views/templates/front/`)

- Aucun explicitement listé comme modèle de page autonome, ce qui indique que le contenu du front-office est principalement rendu via des hooks.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

- `ps_myaiactpro_api_key` : Stocke les clés API pour l'API REST du module.
  - `id_myaiactpro_api_key` (PK)
  - `key_value` (VARCHAR)
  - `description` (TEXT)
  - `active` (TINYINT)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_myaiactpro_audit_log` : Enregistre les événements liés à la loi sur l'IA.
  - `id_myaiactpro_audit_log` (PK)
  - `id_employee` (INT)
  - `id_customer` (INT)
  - `id_product` (INT)
  - `action` (VARCHAR)
  - `details` (TEXT)
  - `ip_address` (VARCHAR)
  - `date_add` (DATETIME)
- `ps_myaiactpro_badge_layout` : Stocke les mises en page visuelles personnalisées pour les badges IA.
  - `id_myaiactpro_badge_layout` (PK)
  - `name` (VARCHAR)
  - `type` (VARCHAR)
  - `icon_class` (VARCHAR)
  - `text_content` (VARCHAR)
  - `styles_json` (TEXT)
  - `active` (TINYINT)
- `ps_myaiactpro_product_flag` : Lie les produits à leur statut généré par l'IA et à la mise en page de badge choisie.
  - `id_product` (PK, INT)
  - `is_ai_generated` (TINYINT)
  - `id_myaiactpro_badge_layout` (INT, FK vers `ps_myaiactpro_badge_layout`)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_myaiactpro_tag_rule` : Stocke les règles de balises personnalisées de la loi sur l'IA.
  - `id_myaiactpro_tag_rule` (PK)
  - `name` (VARCHAR)
  - `description` (TEXT)
  - `badge_layout_id` (INT, FK vers `ps_myaiactpro_badge_layout`)
  - `active` (TINYINT)
- Enregistrements de configuration dans `ps_configuration` : Les paramètres du module sont stockés ici (par exemple, `MYAIACTPRO_ENABLED`, `MYAIACTPRO_BADGE_LAYOUT_ID`, `MYAIACTPRO_POLICY_LINK`).

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique | Modèles rendus |
| --- | --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Injecter CSS/JS, rendre la bannière supérieure. | `hook/banner.tpl` (si configuré) |
| `displayFooter` | En bas de chaque page. | Rendre la bannière inférieure, injecter JS. | `hook/banner.tpl` (si configuré) |
| `displayProductAdditionalInfo` | Sur la page produit, généralement sous la description. | Afficher des informations supplémentaires de divulgation IA. | `hook/additional_info.tpl`, `hook/human_fallback.tpl` |
| `displayProductListReviews` | Dans les listes de produits, près du nom/image du produit. | Afficher le badge IA sur les vignettes de produits. | `hook/ai_badge.tpl` |
| `displayProductButtons` | Sur la page produit, près du bouton "ajouter au panier". | Afficher le badge IA sur la page produit. | `hook/ai_badge.tpl` |
| `displayAdminProductsExtra` | Dans la page d'édition de produit du Back Office. | Ajouter un onglet dédié pour les paramètres de la loi sur l'IA. | `admin/product_tab.tpl` |
| `actionProductUpdate` | Après la mise à jour d'un produit dans le Back Office. | Mettre à jour les drapeaux/statuts de la loi sur l'IA pour le produit. | N/A |
| `actionProductDelete` | Après la suppression d'un produit. | Nettoyer les données associées à la loi sur l'IA. | N/A |
| `actionFrontControllerSetMedia` | Avant que le contrôleur frontal ne rende le contenu. | Enregistrer le CSS/JS du front-office. | N/A |
| `actionAdminControllerSetMedia` | Avant que le contrôleur d'administration ne rende le contenu. | Enregistrer le CSS/JS du back-office. | N/A |
| `actionRegisterShortcode` | Lors de l'installation/mise à jour du module. | Enregistre les shortcodes personnalisés pour l'analyse du contenu. | N/A |
| `displayBackOfficeHeader` | Dans la section `<head>` de chaque page d'administration. | Injecter le CSS/JS d'administration. | N/A |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant le module « My AI Act Pro - Artificial Intelligence Compliance ».
