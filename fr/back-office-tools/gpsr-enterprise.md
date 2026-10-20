---
title: "GPSR Enterprise - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop GPSR Enterprise par MyPresta.eu."
sidebar:
  label: "GPSR Enterprise"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module GPSR Enterprise sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/gpsr-enterprise.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/gpsr-enterprise/)
>
> ---


# GPSR Enterprise

## 1. Exigences et Compatibilité

*   **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
*   **Compatibilité PHP** : PHP 7.1 - 8.5
*   **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises et généralement disponibles sur la plupart des environnements d'hébergement modernes.

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

Le module GPSR Enterprise offre un ensemble complet d'options de configuration, réparties sur sa page de configuration principale et plusieurs écrans d'administration dédiés.

### 2.1 Page de configuration du module (Back Office > Modules > Gestionnaire de modules > GPSR Enterprise > Configurer)

C'est l'écran de configuration principal du module, où vous contrôlez son comportement général et son affichage en front-office.

*   **Module activé**
    *   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour l'ensemble du module GPSR Enterprise.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé (Oui) :* Le module sera actif, affichant les informations GPSR sur les pages produit, vous permettant de gérer les entités, les avertissements et les mappages, et activant l'API et les tâches cron.
        *   *Lorsqu'il est désactivé (Non) :* Le module sera complètement inactif. Aucune information GPSR ne sera affichée en front-office, et les fonctionnalités de gestion backend seront indisponibles ou non fonctionnelles.
    *   **Valeur recommandée :** **Oui** (pour utiliser les fonctionnalités du module).
    *   **Scénario / exemple de marchand :** Si vous configurez le module pour la première fois, gardez-le désactivé jusqu'à ce que toutes les configurations soient terminées, puis activez-le pour le mettre en ligne.

*   **Profil de thème de la boutique**
    *   **Ce que fait ce paramètre :** Vous permet de sélectionner le profil de style visuel pour le bloc d'informations GPSR sur vos pages produit, optimisé pour différents thèmes PrestaShop.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur 'Classic' :* Le module utilisera un style optimisé pour le thème PrestaShop Classic par défaut (et de nombreux thèmes compatibles).
        *   *Lorsqu'il est défini sur 'Hummingbird' :* Le module utilisera un style optimisé pour le nouveau thème PrestaShop Hummingbird (PrestaShop 8.1+).
    *   **Valeur recommandée :** Sélectionnez le profil qui correspond le mieux à votre thème PrestaShop actuel. Si vous n'êtes pas sûr, essayez d'abord 'Classic'.
    *   **Scénario / exemple de marchand :** Si votre boutique utilise PrestaShop 8.1+ avec le thème par défaut, choisissez 'Hummingbird' pour la meilleure intégration visuelle. Si vous êtes sur PrestaShop 1.7 ou 8.0 avec le thème Classic, choisissez 'Classic'.

*   **Mode d'affichage**
    *   **Ce que fait ce paramètre :** Contrôle la manière dont le bloc d'informations GPSR est présenté sur la page produit.
    *   **Effet de la modification de ce paramètre :**
        *   *Les options varient (par exemple, 'Onglet', 'Accordéon', 'Bloc') :*
            *   **Onglet :** Les informations GPSR apparaîtront comme un nouvel onglet à côté de "Description", "Détails du produit", etc.
            *   **Accordéon :** Les informations seront présentées dans une section accordéon extensible/réductible.
            *   **Bloc :** Les informations seront affichées comme un bloc statique dans le flux de contenu de la page produit.
    *   **Valeur recommandée :** **Onglet** ou **Accordéon** pour une mise en page de page produit plus propre, surtout si vous avez beaucoup d'informations.
    *   **Scénario / exemple de marchand :** Si vos pages produit sont déjà très longues, l'utilisation d'un mode 'Onglet' ou 'Accordéon' permet de garder la page ordonnée tout en rendant les informations accessibles.

*   **Style visuel**
    *   **Ce que fait ce paramètre :** Définit l'esthétique générale du bloc d'informations GPSR.
    *   **Effet de la modification de ce paramètre :**
        *   *Les options varient (par exemple, 'Défaut', 'Minimal', 'Détaillé') :* Cela modifiera la densité visuelle, l'utilisation d'icônes et la présentation générale des informations.
    *   **Valeur recommandée :** **Défaut** ou **Minimal** pour un look épuré. Expérimentez pour voir ce qui convient le mieux à votre thème.
    *   **Scénario / exemple de marchand :** Si votre thème est très minimaliste, choisir un style visuel 'Minimal' pour le bloc GPSR assurera une meilleure intégration.

*   **Afficher le titre du bloc**
    *   **Ce que fait ce paramètre :** Détermine si un titre est affiché au-dessus du bloc d'informations GPSR sur la page produit.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé (Oui) :* Le texte spécifié dans "Texte du titre du bloc" apparaîtra comme un en-tête.
        *   *Lorsqu'il est désactivé (Non) :* Aucun titre ne sera affiché, ce qui rendra le bloc plus intégré ou dépendra du contexte.
    *   **Valeur recommandée :** **Oui** pour plus de clarté, afin que les clients comprennent immédiatement ce que contient le bloc.
    *   **Scénario / exemple de marchand :** L'activation de cette option avec un titre comme "Informations de sécurité du produit" indique clairement aux clients ce qu'ils consultent.

*   **Texte du titre du bloc**
    *   **Ce que fait ce paramètre :** Vous permet de personnaliser le titre du bloc d'informations GPSR. Ce paramètre ne s'applique que si "Afficher le titre du bloc" est activé.
    *   **Effet de la modification de ce paramètre :** Le texte que vous saisissez ici sera affiché comme en-tête du bloc d'informations GPSR sur la page produit.
    *   **Valeur recommandée :** Un titre clair et descriptif comme "Sécurité et conformité du produit", "Informations de sécurité UE" ou "Détails du passeport produit".
    *   **Scénario / exemple de marchand :** Vous pouvez le définir sur "Informations de sécurité des produits de l'UE" pour communiquer clairement l'objectif du bloc à vos clients européens.

*   **Masquer le bloc si les données sont incomplètes**
    *   **Ce que fait ce paramètre :** Contrôle si le bloc d'informations GPSR est affiché sur la page produit si toutes les données requises (fabricant, personne responsable dans l'UE, avertissements, documents) n'ont pas été entièrement configurées pour ce produit.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé (Oui) :* Si des données GPSR sont manquantes pour un produit, l'intégralité du bloc ne sera pas affichée en front-office. Cela évite d'afficher des informations incomplètes ou trompeuses.
        *   *Lorsqu'il est désactivé (Non) :* Le bloc sera toujours affiché, même si certaines sections sont vides. Cela pourrait afficher un bloc partiellement rempli, ce qui pourrait être déroutant.
    *   **Valeur recommandée :** **Oui** pour maintenir une apparence professionnelle et éviter d'afficher des sections à moitié vides.
    *   **Scénario / exemple de marchand :** Vous êtes toujours en train d'ajouter des données GPSR à tous vos produits. L'activation de cette option garantit que seules les pages produit entièrement conformes affichent le bloc, évitant ainsi la confusion des clients sur les produits en cours de mise à jour.

*   **Afficher l'entité fabricant**
    *   **Ce que fait ce paramètre :** Détermine si les détails de l'entité GPSR du fabricant sont affichés dans le bloc front-office.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé (Oui) :* Le nom, l'adresse et les autres détails configurés du fabricant seront visibles.
        *   *Lorsqu'il est désactivé (Non) :* La section du fabricant sera masquée.
    *   **Valeur recommandée :** **Oui**, car il s'agit d'une exigence GPSR essentielle.
    *   **Scénario / exemple de marchand :** Pour se conformer pleinement au GPSR, vous devez afficher les détails du fabricant. Gardez cette option activée.

*   **Afficher la personne responsable dans l'UE**
    *   **Ce que fait ce paramètre :** Détermine si les détails de l'entité GPSR de la personne responsable dans l'UE sont affichés dans le bloc front-office.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé (Oui) :* Le nom, l'adresse et les autres détails configurés de la personne responsable dans l'UE seront visibles.
        *   *Lorsqu'il est désactivé (Non) :* La section de la personne responsable dans l'UE sera masquée.
    *   **Valeur recommandée :** **Oui**, car il s'agit d'une exigence GPSR essentielle pour les produits vendus dans l'UE.
    *   **Scénario / exemple de marchand :** Si vos produits nécessitent une personne responsable dans l'UE, l'activation de cette option garantit que ses détails sont affichés.

*   **Afficher les avertissements de sécurité**
    *   **Ce que fait ce paramètre :** Détermine si les avertissements de sécurité associés sont affichés dans le bloc front-office.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé (Oui) :* Les avertissements de sécurité configurés pour le produit seront visibles.
        *   *Lorsqu'il est désactivé (Non) :* La section des avertissements de sécurité sera masquée.
    *   **Valeur recommandée :** **Oui** pour informer les clients des dangers potentiels.
    *   **Scénario / exemple de marchand :** Pour les produits avec des instructions de sécurité spécifiques (par exemple, "Tenir hors de portée des enfants"), l'activation de cette option garantit que ces avertissements sont affichés de manière proéminente.

*   **Afficher les documents liés**
    *   **Ce que fait ce paramètre :** Détermine si les liens vers les documents associés (tels que les manuels, les déclarations) sont affichés dans le bloc front-office.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé (Oui) :* Les liens vers les documents téléchargés seront visibles.
        *   *Lorsqu'il est désactivé (Non) :* La section des documents liés sera masquée.
    *   **Valeur recommandée :** **Oui** pour fournir aux clients la documentation essentielle du produit.
    *   **Scénario / exemple de marchand :** Si vous devez fournir une "Déclaration de conformité" ou un manuel d'utilisation détaillé, l'activation de cette option permet aux clients d'accéder facilement à ces fichiers.

*   **Afficher le bouton du passeport produit**
    *   **Ce que fait ce paramètre :** Contrôle la visibilité du bouton "Télécharger le passeport produit" sur la page produit.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé (Oui) :* Un bouton apparaîtra, permettant aux clients de télécharger un PDF contenant toutes les informations GPSR pour le produit.
        *   *Lorsqu'il est désactivé (Non) :* Le bouton ne sera pas affiché.
    *   **Valeur recommandée :** **Oui**, car le passeport produit est une fonctionnalité clé du GPSR.
    *   **Scénario / exemple de marchand :** Pour offrir aux clients un résumé complet et téléchargeable de toutes les informations de sécurité et de conformité, gardez cette option activée.

*   **Partager les mappages entre toutes les boutiques**
    *   **Ce que fait ce paramètre :** (Visible uniquement dans une configuration multi-boutiques) Détermine si les mappages GPSR (comment les entités, les avertissements et les documents sont attribués aux produits, catégories ou fabricants) sont partagés entre toutes vos boutiques PrestaShop.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé (Oui) :* Tous les mappages GPSR que vous créez s'appliqueront à toutes les boutiques de votre environnement multi-boutiques. Cela simplifie la gestion si votre catalogue de produits et vos besoins de conformité sont similaires entre les boutiques.
        *   *Lorsqu'il est désactivé (Non) :* Chaque boutique aura son propre ensemble indépendant de mappages GPSR, permettant des configurations de conformité spécifiques à chaque boutique.
    *   **Valeur recommandée :** **Oui** si vos besoins de conformité sont cohérents entre les boutiques ; sinon, **Non**.
    *   **Scénario / exemple de marchand :** Si vous gérez plusieurs boutiques spécifiques à un pays mais vendez les mêmes produits avec les mêmes exigences de conformité, l'activation de cette option vous fait gagner beaucoup de temps en gérant les mappages une seule fois.

*   **Action lors de l'activation du partage**
    *   **Ce que fait ce paramètre :** (Visible uniquement dans une configuration multi-boutiques, apparaît lorsque "Partager les mappages entre toutes les boutiques" est activé) Définit ce qui se passe avec les mappages existants spécifiques à la boutique lorsque vous passez aux mappages partagés.
    *   **Effet de la modification de ce paramètre :**
        *   *Les options varient (par exemple, 'Fusionner', 'Écraser', 'Conserver la boutique actuelle') :*
            *   **Fusionner :** Tente de combiner les mappages existants de toutes les boutiques en un seul ensemble partagé.
            *   **Écraser :** Remplace tous les mappages existants spécifiques à la boutique par les mappages de la boutique actuellement active.
            *   **Conserver la boutique actuelle :** Utilise les mappages de la boutique actuellement active comme mappages partagés, en ignorant les autres.
    *   **Valeur recommandée :** Choisissez avec soin en fonction de vos données. **Sauvegardez votre base de données** avant de modifier cela !
    *   **Scénario / exemple de marchand :** Si vous avez géré les données GPSR séparément pour chaque boutique et que vous souhaitez maintenant centraliser, vous devrez décider si vous voulez combiner toutes les données, ou si les données d'une boutique doivent devenir la référence.

*   **Action lors de la désactivation du partage**
    *   **Ce que fait ce paramètre :** (Visible uniquement dans une configuration multi-boutiques, apparaît lorsque "Partager les mappages entre toutes les boutiques" est désactivé) Définit ce qui se passe avec les mappages partagés lorsque vous revenez aux mappages spécifiques à la boutique.
    *   **Effet de la modification de ce paramètre :**
        *   *Les options varient (par exemple, 'Dupliquer vers toutes les boutiques', 'Conserver uniquement pour la boutique actuelle') :*
            *   **Dupliquer vers toutes les boutiques :** Les mappages partagés actuels sont copiés vers chaque boutique individuelle, leur permettant d'être modifiés indépendamment par la suite.
            *   **Conserver uniquement pour la boutique actuelle :** Les mappages partagés sont attribués uniquement à la boutique actuellement active, et les autres boutiques commenceront sans mappages GPSR.
    *   **Valeur recommandée :** Choisissez avec soin en fonction de vos données. **Sauvegardez votre base de données** avant de modifier cela !
    *   **Scénario / exemple de marchand :** Si vous décidez de passer des mappages partagés à la gestion individuelle des boutiques, vous devez décider si les données partagées doivent être copiées vers toutes les boutiques comme point de départ, ou si seule la boutique actuelle doit les conserver.

*   **CSS personnalisé**
    *   **Ce que fait ce paramètre :** Fournit une zone de texte où vous pouvez ajouter des règles CSS personnalisées pour styliser davantage le bloc d'informations GPSR sur votre boutique.
    *   **Effet de la modification de ce paramètre :** Tout code CSS valide saisi ici sera appliqué aux éléments front-office du module GPSR, vous permettant d'affiner les couleurs, les polices, l'espacement, etc., pour correspondre parfaitement à votre thème.
    *   **Valeur recommandée :** Laissez vide, sauf si vous avez des besoins de style spécifiques et que vous êtes à l'aise avec le CSS.
    *   **Scénario / exemple de marchand :** Votre thème utilise une nuance de bleu spécifique pour les titres. Vous pouvez ajouter du CSS ici pour vous assurer que le titre du bloc GPSR utilise également ce bleu exact, en maintenant la cohérence visuelle.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module GPSR Enterprise ajoute plusieurs nouveaux éléments de menu sous un menu principal "GPSR Enterprise" dans votre Back Office PrestaShop. Ces écrans sont l'endroit où vous gérez toutes les données de conformité détaillées.

#### 2.2.1 Tableau de bord GPSR Enterprise (Back Office > GPSR Enterprise > Tableau de bord)

Cet écran fournit un aperçu de votre état de conformité GPSR et un accès rapide aux principales zones de gestion.

*   **Actions et paramètres disponibles :**
    *   **Statistiques récapitulatives :** Peut afficher le nombre d'entités configurées, d'avertissements, de produits mappés, etc.
    *   **Liens rapides :** Boutons ou liens pour accéder directement à la gestion des Entités, Avertissements, Mappages, Documents, etc.
    *   **Statut de la tâche Cron :** Informations sur la dernière exécution et le résultat de la tâche cron GPSR (pour la réindexation ou la synchronisation des données).
    *   **Jeton API :** Affiche votre jeton API unique pour les intégrations externes.
    *   **Jeton Cron :** Affiche votre jeton de tâche cron unique pour une exécution sécurisée.
*   **Effet des modifications :** Cet écran est principalement destiné à la surveillance et à la navigation. Les modifications ici (par exemple, la génération de nouveaux jetons API/Cron) ont un impact direct sur la sécurité et la fonctionnalité des intégrations externes et des tâches automatisées.
*   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vérifiez ce tableau de bord périodiquement pour surveiller votre état de conformité et vous assurer que les tâches cron s'exécutent correctement.

#### 2.2.2 Entités (Back Office > GPSR Enterprise > Entités)

Cet écran est l'endroit où vous définissez et gérez les "entités" requises par le GPSR, telles que les fabricants et les personnes responsables dans l'UE.

*   **Actions et paramètres disponibles :**
    *   **Liste des entités :** Un tableau affichant toutes les entités configurées, avec des colonnes pour le nom, le type (Fabricant, Personne responsable dans l'UE), l'adresse, le contact, etc.
    *   **Ajouter une nouvelle entité :** Un bouton pour créer une nouvelle entité.
    *   **Modifier/Supprimer :** Actions pour chaque entité de la liste.
    *   **Formulaire d'entité :** Lors de l'ajout/modification, vous trouverez des champs pour :
        *   **Nom :** Le nom officiel de l'entité.
        *   **Type :** Sélectionnez s'il s'agit d'un Fabricant ou d'une Personne responsable dans l'UE.
        *   **Adresse :** Adresse postale complète.
        *   **Informations de contact :** E-mail, téléphone, site web.
        *   **Champs multilingues :** Certains champs peuvent être traduisibles pour différentes langues.
*   **Effet des modifications :** La création ou la mise à jour d'entités ici les rend disponibles pour la sélection lors du mappage des données GPSR aux produits. Des données d'entité incorrectes ou incomplètes entraîneront une non-conformité.
*   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Avant de mapper les produits, assurez-vous que tous vos fabricants et personnes responsables dans l'UE sont correctement saisis ici. Mettez à jour les détails rapidement s'ils changent.

#### 2.2.3 Avertissements (Back Office > GPSR Enterprise > Avertissements)

Cet écran vous permet de définir et de gérer divers avertissements de sécurité pouvant être associés à vos produits.

*   **Actions et paramètres disponibles :**
    *   **Liste des avertissements :** Un tableau affichant tous les avertissements créés, avec des colonnes pour le titre, l'icône et le contenu.
    *   **Ajouter un nouvel avertissement :** Un bouton pour créer un nouvel avertissement.
    *   **Modifier/Supprimer :** Actions pour chaque avertissement de la liste.
    *   **Formulaire d'avertissement :** Lors de l'ajout/modification, vous trouverez des champs pour :
        *   **Titre :** Un titre court et descriptif pour l'avertissement.
        *   **Icône :** Une option pour sélectionner une icône visuelle pour accompagner l'avertissement (par exemple, un symbole de danger).
        *   **Contenu :** Le texte complet de l'avertissement de sécurité (multilingue).
        *   **Gravité/Type :** (Si disponible) Catégoriser l'avertissement.
*   **Effet des modifications :** Les avertissements créés ici deviennent disponibles pour la sélection lors du mappage des données GPSR aux produits. Ils apparaîtront ensuite sur la page produit du front-office.
*   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Créez d'abord tous les avertissements de sécurité nécessaires ici. Assurez-vous que le contenu est précis et légalement conforme pour toutes les langues que vous prenez en charge.

#### 2.2.4 Documents (Back Office > GPSR Enterprise > Documents)

Cet écran sert à télécharger et à gérer les documents qui doivent être liés aux produits, tels que les déclarations de conformité, les manuels d'utilisation ou les fiches de données de sécurité.

*   **Actions et paramètres disponibles :**
    *   **Liste des documents :** Un tableau affichant les documents téléchargés, avec des colonnes pour le nom, le type de fichier et les produits associés.
    *   **Télécharger un nouveau document :** Un bouton pour télécharger un nouveau fichier.
    *   **Modifier/Supprimer :** Actions pour chaque document.
    *   **Formulaire de document :** Lors du téléchargement/modification, vous trouverez des champs pour :
        *   **Nom :** Un nom descriptif pour le document (multilingue).
        *   **Téléchargement de fichier :** Le fichier réel (par exemple, PDF).
        *   **Type :** (Si disponible) Catégoriser le document (par exemple, "Manuel", "Déclaration").
*   **Effet des modifications :** Les documents téléchargés deviennent disponibles pour la sélection lors du mappage des données GPSR aux produits. Des liens vers ces documents apparaîtront sur la page produit du front-office.
*   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Téléchargez ici toute la documentation produit pertinente. Assurez-vous que les documents sont à jour et correctement nommés pour une identification facile.

#### 2.2.5 Mappages (Back Office > GPSR Enterprise > Mappages)

C'est le cœur de l'automatisation du module, vous permettant de définir comment les données GPSR sont attribuées aux produits en fonction de divers critères. Cette section contient probablement plusieurs sous-sections pour différents types de mappage.

*   **Actions et paramètres disponibles :**
    *   **Mappages globaux :** Appliquer les données GPSR à tous les produits par défaut.
    *   **Mappages de catégories :** Appliquer les données GPSR à tous les produits d'une catégorie spécifique.
    *   **Mappages de fabricants :** Appliquer les données GPSR à tous les produits d'un fabricant spécifique.
    *   **Mappages de produits/combinaisons :** Appliquer les données GPSR à des produits individuels ou à des combinaisons de produits spécifiques (variantes).
    *   **Formulaires de mappage :** Pour chaque type de mappage, vous configurerez :
        *   **Entité fabricant attribuée :** Sélectionnez une entité définie dans la section "Entités".
        *   **Entité personne responsable dans l'UE attribuée :** Sélectionnez une entité définie dans la section "Entités".
        *   **Avertissements attribués :** Sélectionnez un ou plusieurs avertissements définis dans la section "Avertissements".
        *   **Documents attribués :** Sélectionnez un ou plusieurs documents téléchargés dans la section "Documents".
        *   **Règles de priorité/remplacement :** (Si disponible) Définissez comment les mappages de différents niveaux (global, catégorie, fabricant, produit) interagissent et se remplacent mutuellement.
*   **Effet des modifications :** Les modifications ici déterminent directement les informations GPSR affichées sur vos pages produit. Une stratégie de mappage bien structurée réduit considérablement le travail manuel.
*   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Commencez par les mappages globaux, puis affinez avec les mappages de catégories et de fabricants. N'utilisez les mappages de produits/combinaisons que pour les exceptions ou les produits uniques. Révisez régulièrement vos mappages, surtout lors de l'ajout de nouveaux produits ou catégories.

#### 2.2.6 Actions de masse (Back Office > GPSR Enterprise > Actions de masse)

Cet écran fournit des outils pour appliquer les données GPSR à plusieurs produits à la fois, ou pour effectuer des opérations en masse.

*   **Actions et paramètres disponibles :**
    *   **Grille de produits :** Une liste de produits filtrable et consultable.
    *   **Attribution en masse :** Sélectionnez plusieurs produits, puis attribuez une entité fabricant, une personne responsable dans l'UE, des avertissements ou des documents à tous les produits sélectionnés.
    *   **Suppression en masse :** Supprimez les données GPSR des produits sélectionnés.
    *   **Importation/Exportation :** (Si disponible) Outils pour importer des données GPSR à partir d'un fichier CSV ou exporter des données existantes.
*   **Effet des modifications :** Les actions de masse peuvent rapidement mettre à jour les données GPSR pour un grand nombre de produits, ce qui permet de gagner un temps considérable. Utilisez-les avec prudence, car les modifications sont appliquées de manière générale.
*   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Utilisez cette option après la configuration initiale pour appliquer rapidement des données GPSR courantes à de grands ensembles de produits. Également utile pour mettre à jour les données de nombreux produits si une réglementation change.

#### 2.2.7 Matcher (Back Office > GPSR Enterprise > Matcher)

Cet écran aide à identifier les produits qui pourraient manquer de données GPSR ou suggère des mappages potentiels.

*   **Table / Entité gérée :** `gpsr_match_suggestion`
*   **Actions et paramètres disponibles :**
    *   **Liste de suggestions :** Affiche les produits ou groupes de produits que le module identifie comme ayant potentiellement besoin de données GPSR ou ayant des données incomplètes.
    *   **Règles de correspondance :** (Si disponible) Configurez les règles de la manière dont le module suggère des correspondances (par exemple, en fonction de mots-clés du nom du produit, d'attributs existants).
    *   **Appliquer/Ignorer les suggestions :** Actions pour appliquer les données GPSR suggérées ou ignorer la suggestion.
*   **Effet des modifications :** L'application des suggestions mettra à jour les données GPSR pour les produits identifiés. Cela contribue à assurer une conformité complète.
*   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vérifiez périodiquement cet écran pour détecter tout produit qui aurait pu échapper à votre stratégie de mappage.

#### 2.2.8 Journal d'audit (Back Office > GPSR Enterprise > Journal d'audit)

Cet écran fournit un historique des modifications apportées aux données GPSR au sein du module.

*   **Table / Entité gérée :** `gpsr_audit_log`
*   **Actions et paramètres disponibles :**
    *   **Grille de journal :** Un tableau affichant les entrées avec des détails tels que :
        *   **Date/Heure :** Quand la modification a eu lieu.
        *   **Utilisateur :** Quel administrateur a effectué la modification.
        *   **Action :** Quelle action a été effectuée (par exemple, "Entité créée", "Produit mappé", "Avertissement mis à jour").
        *   **Détails :** Spécificités de la modification.
*   **Effet des modifications :** Cet écran est destiné à l'audit et à la surveillance. Aucune modification directe des données GPSR n'est effectuée ici, mais il fournit un enregistrement crucial pour la responsabilité et le dépannage.
*   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Utilisez ce journal pour examiner les modifications, surtout si vous avez plusieurs administrateurs gérant les données GPSR, ou si vous devez résoudre pourquoi certaines données apparaissent (ou n'apparaissent pas) en front-office.

#### 2.2.9 Registre (Back Office > GPSR Enterprise > Registre)

Cet écran fournit probablement un enregistrement plus détaillé et "silencieux" de toutes les données GPSR appliquées aux produits, y compris potentiellement les versions historiques ou un aperçu complet à des fins réglementaires.

*   **Actions et paramètres disponibles :**
    *   **Vue centrée sur le produit :** Un moyen de visualiser toutes les données GPSR associées à un produit spécifique, y compris éventuellement la manière dont elles ont été dérivées (par exemple, d'un mappage de catégorie ou directement attribuées).
    *   **Options d'exportation :** (Si disponible) Exportez le registre complet pour examen externe ou archivage.
*   **Effet des modifications :** Cet écran est principalement destiné aux rapports et à l'examen détaillé. Il ne modifie pas directement les données du front-office mais fournit l'enregistrement de conformité sous-jacent.
*   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Utilisez cette option pour des vérifications de conformité approfondies ou lors de la préparation d'audits réglementaires.

#### 2.2.10 API (Back Office > GPSR Enterprise > API)

Cet écran fournit des informations et des paramètres liés à l'API du module pour les intégrations externes.

*   **Actions et paramètres disponibles :**
    *   **Jeton API :** Affiche le jeton unique requis pour authentifier les requêtes API.
    *   **Générer un nouveau jeton :** Un bouton pour générer un nouveau jeton API (utile pour la sécurité si un jeton est compromis).
    *   **Lien de documentation API :** Un lien vers la documentation technique pour les développeurs sur la façon d'utiliser l'API.
*   **Effet des modifications :** La génération d'un nouveau jeton invalidera l'ancien, ce qui nécessitera la mise à jour de tous les systèmes externes utilisant l'API avec le nouveau jeton.
*   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** N'accédez à cette option que si vous intégrez le module GPSR à des systèmes externes (par exemple, ERP, PIM). Gardez votre jeton API sécurisé.

#### 2.2.11 Cron (Back Office > GPSR Enterprise > Cron)

Cet écran gère les tâches planifiées du module, telles que la réindexation des données GPSR ou la synchronisation des informations.

*   **Actions et paramètres disponibles :**
    *   **URL de la tâche Cron :** L'URL pour déclencher la tâche cron en externe (par exemple, via le service cron de votre hébergeur).
    *   **Jeton Cron :** Le jeton unique pour une exécution sécurisée de la tâche cron.
    *   **Activer/Désactiver Cron :** Un interrupteur pour activer ou désactiver la tâche cron.
    *   **Dernière exécution/Résultat :** Informations sur la dernière exécution de la tâche cron et son résultat.
    *   **Paramètres de réindexation :** Options pour la fréquence et le nombre de produits à réindexer par exécution (par exemple, `GPSR_CRON_REINDEX_OFFSET`, `GPSR_CRON_REINDEX_LIMIT`).
*   **Effet des modifications :** L'activation de la tâche cron garantit que les données GPSR sont régulièrement traitées et mises à jour en arrière-plan, gardant vos informations front-office à jour. Des paramètres cron incorrects peuvent entraîner des données obsolètes ou des problèmes de charge du serveur.
*   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Assurez-vous que la tâche cron est activée et correctement configurée sur votre serveur d'hébergement pour automatiser le traitement des données. Surveillez son statut sur le tableau de bord.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| :------------ | :--------------- | :-------------------- | :--------------- |
| **Configuration du module** | Module activé | Oui | Interrupteur principal pour la fonctionnalité du module. |
| | Profil de thème de la boutique | Correspond à votre thème | Optimise le style visuel pour les thèmes Classic ou Hummingbird. |
| | Mode d'affichage | Onglet / Accordéon | Comment le bloc GPSR apparaît (Onglet, Accordéon, Bloc). |
| | Style visuel | Défaut / Minimal | Esthétique du bloc d'informations GPSR. |
| | Afficher le titre du bloc | Oui | Affiche un titre au-dessus du bloc GPSR. |
| | Texte du titre du bloc | "Sécurité et conformité du produit" | Texte personnalisé pour le titre du bloc. |
| | Masquer le bloc si les données sont incomplètes | Oui | Empêche l'affichage d'informations GPSR incomplètes. |
| | Afficher l'entité fabricant | Oui | Affiche les détails du fabricant. |
| | Afficher la personne responsable dans l'UE | Oui | Affiche les détails de la personne responsable dans l'UE. |
| | Afficher les avertissements de sécurité | Oui | Affiche les avertissements de sécurité du produit. |
| | Afficher les documents liés | Oui | Affiche les liens vers les documents du produit. |
| | Afficher le bouton du passeport produit | Oui | Affiche le bouton pour télécharger le passeport produit PDF. |
| | Partager les mappages entre toutes les boutiques | Oui (si multi-boutique) | Centralise les mappages GPSR pour le multi-boutique. |
| | Action lors de l'activation du partage | (Choix prudent) | Définit la gestion des données lors de l'activation des mappages partagés. |
| | Action lors de la désactivation du partage | (Choix prudent) | Définit la gestion des données lors de la désactivation des mappages partagés. |
| | CSS personnalisé | Vide | Ajoute du CSS personnalisé pour le style du front-office. |
| **Entités** | Ajouter/Modifier une entité | N/A | Définir les fabricants et les personnes responsables dans l'UE. |
| **Avertissements** | Ajouter/Modifier un avertissement | N/A | Créer et gérer les avertissements de sécurité. |
| **Documents** | Télécharger/Gérer un document | N/A | Télécharger et lier les documents liés au produit. |
| **Mappages** | Mappages globaux/catégories/fabricants/produits | N/A | Attribuer les données GPSR en fonction des critères du produit. |
| **Actions de masse** | Attribution/Suppression en masse | N/A | Appliquer/supprimer les données GPSR pour plusieurs produits. |
| **Matcher** | Examiner les suggestions | N/A | Identifie les produits nécessitant des données GPSR. |
| **Journal d'audit** | Afficher le journal | N/A | Suivi des modifications apportées aux données GPSR. |
| **Registre** | Afficher/Exporter les données | N/A | Enregistrement complet des données GPSR du produit. |
| **API** | Jeton API, Générer un nouveau jeton | N/A | Gérer l'accès API pour les intégrations externes. |
| **Cron** | URL de la tâche Cron, Activer/Désactiver | Activé | Automatise le traitement des données GPSR en arrière-plan. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : J'ai tout configuré, mais le bloc GPSR ne s'affiche pas sur mes pages produit.**
R :
1.  **Vérifiez "Module activé" :** Allez dans **Modules > Gestionnaire de modules > GPSR Enterprise > Configurer** et assurez-vous que "Module activé" est réglé sur "Oui".
2.  **Vérifiez "Masquer le bloc si les données sont incomplètes" :** Si cette option est réglée sur "Oui", le bloc ne s'affichera pas si des données requises (fabricant, personne responsable dans l'UE, avertissements, documents) sont manquantes pour ce produit spécifique. Assurez-vous que le produit dispose de données GPSR complètes attribuées via des mappages ou des modifications directes du produit.
3.  **Videz le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions antérieures). Parfois, un ancien contenu mis en cache empêche l'apparition de nouveaux éléments de module.
4.  **Compatibilité du thème :** Assurez-vous que votre paramètre "Profil de thème de la boutique" correspond à votre thème (Classic ou Hummingbird). Si vous avez un thème très personnalisé, il peut y avoir un conflit CSS. Essayez d'ajouter du CSS personnalisé pour forcer la visibilité ou contactez le support.

**Q : Mon bloc d'informations GPSR semble étrange ou mal aligné sur mon site web.**
R :
1.  **Profil du thème :** Vérifiez à nouveau votre paramètre "Profil de thème de la boutique" dans la configuration du module. Assurez-vous qu'il est défini sur le profil correct pour votre thème PrestaShop (Classic ou Hummingbird).
2.  **CSS personnalisé :** Si vous avez du CSS personnalisé dans votre thème ou dans le champ "CSS personnalisé" du module, il pourrait y avoir un conflit. Essayez de supprimer temporairement le CSS personnalisé pour voir si le problème est résolu.
3.  **Cache du navigateur :** Videz le cache de votre navigateur (Ctrl+F5 ou Cmd+R) pour vous assurer que vous voyez le dernier style.
4.  **Contactez le support :** Si le problème persiste, votre thème pourrait avoir un style unique qui nécessite des ajustements spécifiques. Contactez le support MyPresta.eu avec des captures d'écran et le nom de votre thème.

**Q : Comment m'assurer que mes données GPSR sont traduites pour les clients internationaux ?**
R :
1.  **Champs multilingues :** Lors de la création d'**Entités** et d'**Avertissements**, assurez-vous de remplir le contenu pour toutes les langues activées dans votre boutique. Recherchez les drapeaux de langue à côté des champs de saisie.
2.  **Traductions PrestaShop :** Pour les phrases par défaut du module (comme "Télécharger le passeport produit" ou le titre du bloc), allez dans **International > Traductions**, sélectionnez "Traductions des modules installés", choisissez "GPSR Enterprise" et sélectionnez votre langue cible. Traduisez toutes les phrases manquantes à cet endroit.
3.  **Passeport produit :** Le passeport produit PDF généré reflétera la langue des données produit et des avertissements que vous avez saisis.

**Q : La tâche cron ne semble pas s'exécuter, ou mes données ne se mettent pas à jour automatiquement.**
R :
1.  **Cron activé :** Dans l'écran **Cron** du module (Back Office > GPSR Enterprise > Cron), assurez-vous que la tâche cron est activée.
2.  **Configuration Cron de l'hébergement :** Vérifiez que vous avez correctement configuré la tâche cron sur votre serveur d'hébergement en utilisant l'"URL de la tâche Cron" et le "Jeton Cron" fournis. Cela se fait généralement dans le panneau de contrôle de votre hébergement (cPanel, Plesk, etc.). La tâche cron doit être déclenchée périodiquement (par exemple, toutes les heures).
3.  **Statut de la dernière exécution :** Vérifiez "Dernière exécution" et "Dernier résultat" sur l'écran Cron. S'il affiche des erreurs ou ne s'est pas exécuté récemment, il y a un problème avec la configuration cron ou un problème côté serveur.
4.  **Journaux du serveur :** Vérifiez les journaux d'erreurs PHP de votre serveur pour tout message lié à l'exécution de la tâche cron.

**Q : J'ai fait une erreur avec une action de masse et maintenant de nombreux produits ont des données GPSR incorrectes.**
R :
1.  **Journal d'audit :** Vérifiez immédiatement le **Journal d'audit** (Back Office > GPSR Enterprise > Journal d'audit) pour identifier exactement les modifications qui ont été apportées et par qui.
2.  **Annuler manuellement/via les actions de masse :** Selon l'étendue de l'erreur, vous devrez peut-être utiliser à nouveau l'écran **Actions de masse** pour corriger les données, ou modifier manuellement les mappages de produits individuels si seulement quelques-uns ont été affectés.
3.  **Sauvegarde de la base de données :** Si l'erreur est grave et généralisée, et que vous avez une sauvegarde récente de la base de données d'*avant* l'erreur, la restauration de cette sauvegarde pourrait être la solution la plus rapide. C'est pourquoi les sauvegardes régulières sont cruciales.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une plongée approfondie dans la structure technique du module GPSR Enterprise, destinée aux développeurs, webmasters et agences techniques.

### 4.1 Aperçu de l'architecture

Le module GPSR Enterprise adhère au modèle MVC (Modèle-Vue-Contrôleur) de PrestaShop, étendant les fonctionnalités de base et introduisant des entités personnalisées. Il utilise `ObjectModel` pour les interactions avec la base de données, `ModuleFrontController` pour la livraison des données en front-office (API, cron, génération de passeport) et `AdminController` pour la gestion complète du back-office. Le module s'appuie fortement sur les hooks pour l'intégration dans les pages produit et les interfaces administratives, garantissant une solution non intrusive mais puissante. Le mappage des données est hiérarchique, permettant des remplacements globaux, par catégorie, par fabricant et spécifiques aux produits.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

*   `controllers/front/api.php`
    *   **Nom de la classe :** `GpsrEnterpriseApiModuleFrontController`
    *   **Classe parente :** `ModuleFrontController`
    *   **Responsabilité :** Gère les requêtes API pour les données GPSR. Fournit des points d'accès pour que les systèmes externes puissent interroger les informations de sécurité des produits, les entités, les avertissements et les documents. Nécessite une authentification via `GPSR_API_TOKEN`. Renvoie des charges utiles JSON.
*   `controllers/front/cron.php`
    *   **Nom de la classe :** `GpsrEnterpriseCronModuleFrontController`
    *   **Classe parente :** `ModuleFrontController`
    *   **Responsabilité :** Sert de point d'accès pour les tâches planifiées (tâches cron). Déclenche des processus d'arrière-plan comme la réindexation des données GPSR, la synchronisation des mappages ou l'exécution du nettoyage des données. Nécessite une authentification via `GPSR_CRON_TOKEN`.
*   `controllers/front/data.php`
    *   **Nom de la classe :** `GpsrEnterpriseDataModuleFrontController`
    *   **Classe parente :** `ModuleFrontController`
    *   **Responsabilité :** Fournit des points d'accès AJAX pour récupérer dynamiquement les données GPSR sur la page produit du front-office. Ce contrôleur récupère probablement le fabricant spécifique, la personne responsable dans l'UE, les avertissements et les documents pour un ID de produit ou un ID de combinaison donné.
*   `controllers/front/index.php`
    *   **Nom de la classe :** `GpsrEnterpriseIndexModuleFrontController`
    *   **Classe parente :** `ModuleFrontController`
    *   **Responsabilité :** Un contrôleur frontal de substitution ou de remplacement. Souvent utilisé pour le routage de module de base ou pour empêcher l'affichage du contenu du répertoire.
*   `controllers/front/passport.php`
    *   **Nom de la classe :** `GpsrEnterprisePassportModuleFrontController`
    *   **Classe parente :** `ModuleFrontController`
    *   **Responsabilité :** Génère et sert le passeport produit PDF pour un produit spécifié. Il rassemble toutes les données GPSR pertinentes pour le produit et les rend dans un document PDF téléchargeable.

#### Contrôleurs d'administration Back-Office

Tous les contrôleurs d'administration étendent `GpsrAdminController` (une classe de base personnalisée au sein du module) qui à son tour étend `ModuleAdminController`.

*   `controllers/admin/AdminGpsrAuditController.php`
    *   **Nom de l'onglet :** GPSR Enterprise > Journal d'audit
    *   **Entité gérée :** `GpsrAuditLogEntry`
    *   **Responsabilité :** Gère l'affichage et le filtrage de la table `gpsr_audit_log`, enregistrant toutes les modifications importantes apportées au sein du module GPSR.
*   `controllers/admin/AdminGpsrController.php`
    *   **Nom de l'onglet :** GPSR Enterprise (point d'entrée principal)
    *   **Responsabilité :** Sert probablement de tableau de bord principal ou de redirection vers l'écran de configuration/tableau de bord principal du module.
*   `controllers/admin/AdminGpsrDocumentsController.php`
    *   **Nom de l'onglet :** GPSR Enterprise > Documents
    *   **Entité gérée :** `GpsrDocument` (implicite, car aucune classe spécifique n'a été listée, mais elle gère les documents)
    *   **Responsabilité :** Gère le téléchargement, la liste et la gestion des documents liés au GPSR (par exemple, des PDF).
*   `controllers/admin/AdminGpsrEnterpriseController.php`
    *   **Nom de l'onglet :** GPSR Enterprise > Tableau de bord (ou configuration principale)
    *   **Responsabilité :** Gère les principaux paramètres de configuration du module, y compris les jetons API/Cron, les options d'affichage global et le partage multi-boutiques.
*   `controllers/admin/AdminGpsrEntitiesController.php`
    *   **Nom de l'onglet :** GPSR Enterprise > Entités
    *   **Entité gérée :** `GpsrEntity`
    *   **Responsabilité :** Gère la création, la modification et la suppression des entités GPSR (fabricants, personnes responsables dans l'UE).
*   `controllers/admin/AdminGpsrLedgerController.php`
    *   **Nom de l'onglet :** GPSR Enterprise > Registre
    *   **Responsabilité :** Fournit une vue complète et une interface de gestion pour le "registre silencieux" des données GPSR associées aux produits, y compris potentiellement les données historiques.
*   `controllers/admin/AdminGpsrMapBrandsController.php`
    *   **Nom de l'onglet :** GPSR Enterprise > Mappages > Marques
    *   **Entité gérée :** `Manufacturer` (noyau PrestaShop)
    *   **Responsabilité :** Gère les mappages de données GPSR basés sur les fabricants PrestaShop.
*   `controllers/admin/AdminGpsrMapCategoriesController.php`
    *   **Nom de l'onglet :** GPSR Enterprise > Mappages > Catégories
    *   **Entité gérée :** `Category` (noyau PrestaShop)
    *   **Responsabilité :** Gère les mappages de données GPSR basés sur les catégories PrestaShop.
*   `controllers/admin/AdminGpsrMapCombinationsController.php`
    *   **Nom de l'onglet :** GPSR Enterprise > Mappages > Combinaisons
    *   **Entité gérée :** `ProductCombination` (implicite)
    *   **Responsabilité :** Gère les mappages de données GPSR pour des combinaisons d'attributs de produit spécifiques.
*   `controllers/admin/AdminGpsrMapGlobalController.php`
    *   **Nom de l'onglet :** GPSR Enterprise > Mappages > Global
    *   **Responsabilité :** Gère les mappages de données GPSR globaux qui s'appliquent par défaut à tous les produits.
*   `controllers/admin/AdminGpsrMassController.php`
    *   **Nom de l'onglet :** GPSR Enterprise > Actions de masse
    *   **Responsabilité :** Fournit des outils pour l'attribution et la suppression en masse de données GPSR à plusieurs produits.
*   `controllers/admin/AdminGpsrMatcherController.php`
    *   **Nom de l'onglet :** GPSR Enterprise > Matcher
    *   **Entité gérée :** `GpsrMatchSuggestion`
    *   **Responsabilité :** Gère les suggestions pour les produits qui pourraient avoir besoin de données GPSR ou avoir des mappages incomplets.
*   `controllers/admin/AdminGpsrWarningsController.php`
    *   **Nom de l'onglet :** GPSR Enterprise > Avertissements
    *   **Entité gérée :** `GpsrWarning`
    *   **Responsabilité :** Gère la création, la modification et la suppression des avertissements de sécurité.
*   `controllers/admin/index.php`
    *   **Responsabilité :** Fichier `index.php` vide standard de PrestaShop pour empêcher l'affichage du contenu du répertoire.

### 4.3 Classes et modèles de base (`classes/`)

*   `classes/GpsrAdminController.php`
    *   **Responsabilité :** Une classe de base personnalisée pour tous les contrôleurs d'administration du module GPSR. Elle fournit probablement des méthodes, des propriétés et des variables de modèle communes utilisées dans les interfaces back-office du module, garantissant la cohérence et réduisant la duplication de code.
*   `classes/GpsrAuditLogEntry.php`
    *   **Étend :** `ObjectModel`
    *   **Table de base de données :** `ps_gpsr_audit_log`
    *   **Champs `$definition` :** `id_gpsr_audit_log`, `id_employee`, `action`, `object_type`, `object_id`, `details`, `date_add`
    *   **Méthodes publiques clés :** Méthodes pour l'enregistrement des entrées d'audit, la récupération des données de journal.
    *   **Logique métier :** Enregistre chaque action significative effectuée dans le module GPSR pour l'audit et la conformité.
*   `classes/GpsrCompatibility.php`
    *   **Responsabilité :** Gère les couches de compatibilité pour différentes versions de PrestaShop (1.7.x, 8.x, 9.x). Cette classe contient probablement des méthodes statiques pour abstraire les différences spécifiques à la version dans les appels API, les noms de hook ou le rendu des modèles, garantissant que le module fonctionne de manière transparente sur les versions prises en charge.
*   `classes/GpsrEntity.php`
    *   **Étend :** `ObjectModel`
    *   **Table de base de données :** `ps_gpsr_entity` (et `ps_gpsr_entity_lang` pour les champs multilingues)
    *   **Champs `$definition` :** `id_gpsr_entity`, `type`, `name`, `address`, `contact_email`, `contact_phone`, `contact_website`, `active`, `date_add`, `date_upd` (et champs multilingues comme `name_lang`, `address_lang` etc.)
    *   **Méthodes publiques clés :** Méthodes pour les opérations CRUD sur les entités, la récupération des entités par type, l'association des entités avec les produits/mappages.
    *   **Logique métier :** Gère les données des fabricants et des personnes responsables dans l'UE.
*   `classes/GpsrWarning.php`
    *   **Étend :** `ObjectModel`
    *   **Table de base de données :** `ps_gpsr_warning` (et `ps_gpsr_warning_lang` pour les champs multilingues)
    *   **Champs `$definition` :** `id_gpsr_warning`, `icon`, `active`, `date_add`, `date_upd` (et champs multilingues comme `title`, `content`)
    *   **Méthodes publiques clés :** Méthodes pour les opérations CRUD sur les avertissements, la récupération des avertissements par ID, l'association des avertissements avec les produits/mappages.
    *   **Logique métier :** Gère les données des avertissements de sécurité.
*   `classes/index.php`
    *   **Responsabilité :** Fichier `index.php` vide standard de PrestaShop pour empêcher l'affichage du contenu du répertoire.

### 4.4 Actifs JavaScript (`views/js/`)

*   `gpsrenterprise/lib/searchTool/views/js/autocomplete.js`
    *   **Portée :** Probablement Back-office.
    *   **Responsabilité :** Fournit une fonctionnalité d'autocomplétion pour les champs de recherche dans l'interface d'administration, éventuellement pour la sélection de produits, de catégories ou d'entités dans les écrans de mappage.
*   `gpsrenterprise/views/js/admin-api.js`
    *   **Portée :** Back-office (AdminGpsrEnterpriseController, onglet API).
    *   **Responsabilité :** Gère les interactions AJAX pour l'écran de configuration de l'API, telles que la génération de nouveaux jetons API ou l'affichage de modales de documentation API.
*   `gpsrenterprise/views/js/admin-combination-map.js`
    *   **Portée :** Back-office (AdminGpsrMapCombinationsController).
    *   **Responsabilité :** Gère l'interface utilisateur et les appels AJAX pour le mappage des données GPSR à des combinaisons de produits spécifiques. Cela implique probablement le chargement dynamique des listes de combinaisons et la gestion des attributions.
*   `gpsrenterprise/views/js/admin-combination-picker.js`
    *   **Portée :** Back-office (Onglet de page produit, formulaires de mappage).
    *   **Responsabilité :** Fournit un composant d'interface utilisateur pour la sélection de combinaisons de produits, souvent utilisé dans les formulaires de mappage ou l'onglet d'édition de produit.
*   `gpsrenterprise/views/js/admin-country-rules.js`
    *   **Portée :** Back-office (Potentiellement dans les formulaires d'entité ou d'avertissement).
    *   **Responsabilité :** Gère la logique de l'interface utilisateur pour l'application des règles GPSR basées sur des pays spécifiques, si le module prend en charge la conformité spécifique à un pays.
*   `gpsrenterprise/views/js/admin-entity-picker.js`
    *   **Portée :** Back-office (Formulaires de mappage, onglet de page produit).
    *   **Responsabilité :** Fournit un composant d'interface utilisateur pour la sélection d'instances de `GpsrEntity` (fabricants, personnes responsables dans l'UE) à partir d'une liste déroulante ou d'une interface de recherche.
*   `gpsrenterprise/views/js/admin-icon-picker-data.js`
    *   **Portée :** Back-office (Formulaires d'avertissement).
    *   **Responsabilité :** Contient des données (par exemple, un tableau de noms/chemins d'icônes) utilisées par `admin-icon-picker.js`.
*   `gpsrenterprise/views/js/admin-icon-picker.js`
    *   **Portée :** Back-office (Formulaires d'avertissement).
    *   **Responsabilité :** Implémente un composant d'interface utilisateur pour la sélection visuelle d'une icône à associer à un `GpsrWarning`.
*   `gpsrenterprise/views/js/admin-identifier-shortcodes.js`
    *   **Portée :** Back-office (Zones de texte dans les formulaires, par exemple, pour les modèles de passeport produit).
    *   **Responsabilité :** Fournit des fonctionnalités pour insérer des "shortcodes" ou des espaces réservés prédéfinis dans les champs de texte, qui seront remplacés dynamiquement par les données du produit lors du rendu.
*   `gpsrenterprise/views/js/admin-item-picker.js`
    *   **Portée :** Back-office (Formulaires de mappage généraux).
    *   **Responsabilité :** Un composant d'interface utilisateur générique pour la sélection de divers éléments (produits, catégories, documents, avertissements) à partir d'une liste ou d'une recherche.
*   `gpsrenterprise/views/js/admin-mass-grid.js`
    *   **Portée :** Back-office (AdminGpsrMassController).
    *   **Responsabilité :** Gère la grille de produits interactive et la fonctionnalité d'action en masse sur l'écran "Actions de masse".
*   `gpsrenterprise/views/js/admin-product-tab.js`
    *   **Portée :** Back-office (Page d'édition de produit).
    *   **Responsabilité :** Injecte et gère l'onglet GPSR personnalisé sur la page d'édition de produit de PrestaShop, permettant l'attribution directe de données GPSR à des produits individuels.
*   `gpsrenterprise/views/js/adminGpsrDashboard.js`
    *   **Portée :** Back-office (Tableau de bord AdminGpsrController/AdminGpsrEnterpriseController).
    *   **Responsabilité :** Gère les éléments dynamiques et les mises à jour AJAX sur le tableau de bord du module, tels que l'actualisation du statut cron ou l'affichage des statistiques.
*   `gpsrenterprise/views/js/front.js`
    *   **Portée :** Front-office.
    *   **Responsabilité :** JavaScript principal pour le bloc d'informations GPSR du front-office. Gère le chargement dynamique des données (via le contrôleur `data.php`), la fonctionnalité d'onglet/accordéon et potentiellement les interactions avec le bouton du passeport produit.
*   `gpsrenterprise/views/js/gpsr-barcode.js`
    *   **Portée :** Front-office ou Back-office (Génération de passeport produit).
    *   **Responsabilité :** Probablement un script utilitaire pour générer ou afficher des codes-barres, potentiellement utilisé dans le PDF du passeport produit ou pour l'identification du produit.

### 4.5 Feuilles de style CSS (`views/css/`)

*   `gpsrenterprise/lib/searchTool/views/css/autocomplete.css`
    *   **Portée :** Back-office.
    *   **Responsabilité :** Styles pour les champs de recherche d'autocomplétion utilisés dans l'interface d'administration.
*   `gpsrenterprise/views/css/admin-api.css`
    *   **Portée :** Back-office (AdminGpsrEnterpriseController, onglet API).
    *   **Responsabilité :** Styles spécifiques à la configuration de l'API et à l'affichage de la documentation.
*   `gpsrenterprise/views/css/admin-combination-map.css`
    *   **Portée :** Back-office (AdminGpsrMapCombinationsController).
    *   **Responsabilité :** Styles pour l'interface de mappage de combinaisons.
*   `gpsrenterprise/views/css/admin-combination-picker.css`
    *   **Portée :** Back-office.
    *   **Responsabilité :** Styles pour le composant de sélection de combinaison de produits.
*   `gpsrenterprise/views/css/admin-config.css`
    *   **Portée :** Back-office (Page de configuration du module).
    *   **Responsabilité :** Styles généraux pour le formulaire de configuration principal du module.
*   `gpsrenterprise/views/css/admin-country-rules.css`
    *   **Portée :** Back-office.
    *   **Responsabilité :** Styles pour les interfaces de configuration des règles spécifiques aux pays.
*   `gpsrenterprise/views/css/admin-dashboard.css`
    *   **Portée :** Back-office (Tableau de bord AdminGpsrController/AdminGpsrEnterpriseController).
    *   **Responsabilité :** Styles pour le tableau de bord administratif du module.
*   `gpsrenterprise/views/css/admin-help.css`
    *   **Portée :** Back-office.
    *   **Responsabilité :** Styles pour les textes d'aide, les info-bulles ou les sections de documentation dans l'administration.
*   `gpsrenterprise/views/css/admin-item-picker.css`
    *   **Portée :** Back-office.
    *   **Responsabilité :** Styles pour le composant générique de sélection d'éléments.
*   `gpsrenterprise/views/css/admin-list-enhanced.css`
    *   **Portée :** Back-office.
    *   **Responsabilité :** Améliorations du style par défaut des listes/grilles de PrestaShop pour une meilleure lisibilité ou fonctionnalité.
*   `gpsrenterprise/views/css/admin-mass-grid.css`
    *   **Portée :** Back-office (AdminGpsrMassController).
    *   **Responsabilité :** Styles pour la grille de produits des actions de masse.
*   `gpsrenterprise/views/css/admin-nav.css`
    *   **Portée :** Back-office.
    *   **Responsabilité :** Styles pour les onglets de navigation personnalisés du module ou les éléments de menu dans l'administration.
*   `gpsrenterprise/views/css/admin-product-tab.css`
    *   **Portée :** Back-office (Page d'édition de produit).
    *   **Responsabilité :** Styles pour l'onglet GPSR ajouté à la page d'édition de produit de PrestaShop.
*   `gpsrenterprise/views/css/front-classic.css`
    *   **Portée :** Front-office (Thème Classic).
    *   **Responsabilité :** Style spécifique pour le bloc GPSR lorsque le profil de thème "Classic" est sélectionné.
*   `gpsrenterprise/views/css/front-hummingbird.css`
    *   **Portée :** Front-office (Thème Hummingbird).
    *   **Responsabilité :** Style spécifique pour le bloc GPSR lorsque le profil de thème "Hummingbird" est sélectionné.
*   `gpsrenterprise/views/css/front.css`
    *   **Portée :** Front-office.
    *   **Responsabilité :** Style général de base pour le bloc d'informations GPSR sur la boutique, appliqué quel que soit le profil de thème, qui est ensuite potentiellement remplacé par `front-classic.css` ou `front-hummingbird.css`.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)

*   `gpsrenterprise/views/templates/hook/product-gpsr-classic.tpl`
    *   **Hook :** `displayProductAdditionalInfo`, `displayProductExtraContent`, `displayFooterProduct`, `displayReassurance` (selon la configuration)
    *   **Sortie :** Le bloc d'informations GPSR principal pour la page produit du front-office, spécifiquement stylisé pour le profil de thème Classic.
*   `gpsrenterprise/views/templates/hook/product-gpsr-hummingbird.tpl`
    *   **Hook :** `displayProductAdditionalInfo`, `displayProductExtraContent`, `displayFooterProduct`, `displayReassurance` (selon la configuration)
    *   **Sortie :** Le bloc d'informations GPSR principal pour la page produit du front-office, spécifiquement stylisé pour le profil de thème Hummingbird.
*   `gpsrenterprise/views/templates/hook/product-gpsr.tpl`
    *   **Hook :** `displayProductAdditionalInfo`, `displayProductExtraContent`, `displayFooterProduct`, `displayReassurance` (selon la configuration)
    *   **Sortie :** Un modèle générique ou de base pour le bloc d'informations GPSR, qui pourrait inclure une logique pour charger les modèles spécifiques classic ou hummingbird en fonction de la configuration du module.
*   `gpsrenterprise/views/templates/hook/_product-gpsr-attrs.tpl`
    *   **Hook :** Modèle partiel interne.
    *   **Sortie :** Rend des attributs ou des détails spécifiques dans le bloc produit GPSR principal, tels que des avertissements individuels, des détails d'entité ou des liens de document. Ceci est probablement inclus par `product-gpsr.tpl` ou ses variantes spécifiques au thème.

#### Modèles d'administration (`views/templates/admin/`)

*   `gpsrenterprise/lib/searchTool/views/scripts.tpl`
    *   **Sortie :** Contient du JavaScript ou de la logique Smarty pour la fonctionnalité de l'outil de recherche, probablement inclus dans diverses pages d'administration.
*   `gpsrenterprise/views/templates/admin/api.tpl`
    *   **Sortie :** Rend le contenu de l'écran de configuration de l'API, y compris l'affichage du jeton, le bouton de génération et le lien de documentation.
*   `gpsrenterprise/views/templates/admin/back-office.tpl`
    *   **Sortie :** Un modèle général de back-office, éventuellement pour le tableau de bord principal du module ou un wrapper pour d'autres vues d'administration.
*   `gpsrenterprise/views/templates/admin/combination-list.tpl`
    *   **Sortie :** Affiche une liste de combinaisons de produits, utilisée dans les interfaces de mappage ou de sélection.
*   `gpsrenterprise/views/templates/admin/combination-picker.tpl`
    *   **Sortie :** Rend l'interface utilisateur pour la sélection de combinaisons de produits.
*   `gpsrenterprise/views/templates/admin/combination-script.tpl`
    *   **Sortie :** Contient du JavaScript spécifique à la gestion des combinaisons, probablement inclus dans les pages traitant des combinaisons de produits.
*   `gpsrenterprise/views/templates/admin/configure.tpl`
    *   **Sortie :** Rend le formulaire de configuration principal du module (accessible via Modules > Configurer).
*   `gpsrenterprise/views/templates/admin/country-rules-panel.tpl`
    *   **Sortie :** Rend un panneau pour la gestion des règles GPSR spécifiques aux pays.
*   `gpsrenterprise/views/templates/admin/cron.tpl`
    *   **Sortie :** Rend le contenu de l'écran de configuration et de statut de la tâche Cron.
*   `gpsrenterprise/views/templates/admin/dashboard.tpl`
    *   **Sortie :** Rend le tableau de bord principal du module avec des statistiques et des liens rapides.
*   `gpsrenterprise/views/templates/admin/documents.tpl`
    *   **Sortie :** Rend la liste et l'interface de gestion des documents GPSR.
*   `gpsrenterprise/views/templates/admin/entities-list.tpl`
    *   **Sortie :** Affiche la liste des entités GPSR configurées.
*   `gpsrenterprise/views/templates/admin/entities.tpl`
    *   **Sortie :** Modèle wrapper principal pour l'écran de gestion des entités.
*   `gpsrenterprise/views/templates/admin/entity-form.tpl`
    *   **Sortie :** Rend le formulaire pour ajouter ou modifier une `GpsrEntity`.
*   `gpsrenterprise/views/templates/admin/entity-picker.tpl`
    *   **Sortie :** Rend l'interface utilisateur pour la sélection d'une `GpsrEntity`.
*   `gpsrenterprise/views/templates/admin/getCombinations.tpl`
    *   **Sortie :** Un modèle probablement utilisé pour les réponses AJAX afin de charger dynamiquement les combinaisons de produits.
*   `gpsrenterprise/views/templates/admin/item-picker.tpl`
    *   **Sortie :** Rend un composant d'interface utilisateur générique pour la sélection d'éléments.
*   `gpsrenterprise/views/templates/admin/ledger.tpl`
    *   **Sortie :** Rend la vue détaillée du registre GPSR.
*   `gpsrenterprise/views/templates/admin/map-fields.tpl`
    *   **Sortie :** Un modèle partiel contenant des champs communs pour les mappages GPSR (par exemple, sélecteurs d'entités, sélecteurs d'avertissements).
*   `gpsrenterprise/views/templates/admin/map-form-category.tpl`
    *   **Sortie :** Rend le formulaire pour créer/modifier des mappages GPSR au niveau de la catégorie.
*   `gpsrenterprise/views/templates/admin/map-form-combination.tpl`
    *   **Sortie :** Rend le formulaire pour créer/modifier des mappages GPSR au niveau de la combinaison de produits.
*   `gpsrenterprise/views/templates/admin/map-form-global.tpl`
    *   **Sortie :** Rend le formulaire pour créer/modifier des mappages GPSR globaux.
*   `gpsrenterprise/views/templates/admin/map-form-manufacturer.tpl`
    *   **Sortie :** Rend le formulaire pour créer/modifier des mappages GPSR au niveau du fabricant.
*   `gpsrenterprise/views/templates/admin/mappings.tpl`
    *   **Sortie :** Modèle wrapper principal pour la section Mappages, incluant probablement la navigation pour différents types de mappage.
*   `gpsrenterprise/views/templates/admin/mass-grid.tpl`
    *   **Sortie :** Rend la grille de produits et les contrôles d'action de masse pour l'écran "Actions de masse".
*   `gpsrenterprise/views/templates/admin/matcher.tpl`
    *   **Sortie :** Rend l'interface du Matcher GPSR, affichant les suggestions.
*   `gpsrenterprise/views/templates/admin/nav-tabs.tpl`
    *   **Sortie :** Rend les onglets de navigation pour les sections back-office du module (Tableau de bord, Entités, Avertissements, Mappages, etc.).
*   `gpsrenterprise/views/templates/admin/product-preview-card.tpl`
    *   **Sortie :** Rend une petite carte d'aperçu pour un produit, éventuellement utilisée dans les composants de sélection ou les grilles d'actions de masse.
*   `gpsrenterprise/views/templates/admin/product-tab.tpl`
    *   **Sortie :** Rend le contenu de l'onglet GPSR personnalisé sur la page d'édition de produit de PrestaShop.
*   `gpsrenterprise/views/templates/admin/warning-form.tpl`
    *   **Sortie :** Rend le formulaire pour ajouter ou modifier un `GpsrWarning`.
*   `gpsrenterprise/views/templates/admin/warnings-list.tpl`
    *   **Sortie :** Affiche la liste des avertissements GPSR configurés.
*   `gpsrenterprise/views/templates/admin/_api_documentation_modal.tpl`
    *   **Sortie :** Rend le contenu d'une fenêtre modale affichant la documentation de l'API.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

*   `ps_gpsr_audit_log` : Stocke les entrées du journal d'audit pour les modifications apportées au sein du module.
    *   `id_gpsr_audit_log` (PK)
    *   `id_employee` (FK vers `ps_employee`)
    *   `action` (par exemple, 'add', 'edit', 'delete', 'map')
    *   `object_type` (par exemple, 'entity', 'warning', 'product_mapping')
    *   `object_id`
    *   `details` (JSON ou texte pour plus d'informations)
    *   `date_add`
*   `ps_gpsr_entity` : Stocke les détails des fabricants et des personnes responsables dans l'UE.
    *   `id_gpsr_entity` (PK)
    *   `type` (par exemple, 'manufacturer', 'eu_responsible')
    *   `active`
    *   `date_add`, `date_upd`
*   `ps_gpsr_entity_lang` : Champs multilingues pour `ps_gpsr_entity`.
    *   `id_gpsr_entity` (FK)
    *   `id_lang` (FK)
    *   `name`
    *   `address`
    *   `contact_email`
    *   `contact_phone`
    *   `contact_website`
*   `ps_gpsr_warning` : Stocke les définitions des avertissements de sécurité.
    *   `id_gpsr_warning` (PK)
    *   `icon`
    *   `active`
    *   `date_add`, `date_upd`
*   `ps_gpsr_warning_lang` : Champs multilingues pour `ps_gpsr_warning`.
    *   `id_gpsr_warning` (FK)
    *   `id_lang` (FK)
    *   `title`
    *   `content`
*   `ps_gpsr_document` : Stocke les détails des documents téléchargés.
    *   `id_gpsr_document` (PK)
    *   `filename`
    *   `mime_type`
    *   `file_size`
    *   `date_add`, `date_upd`
*   `ps_gpsr_document_lang` : Champs multilingues pour `ps_gpsr_document` (par exemple, `name`).
*   `ps_gpsr_product_mapping` : Attributions directes de données GPSR au niveau du produit.
    *   `id_product` (FK)
    *   `id_product_attribute` (FK, pour les combinaisons)
    *   `id_gpsr_entity_manufacturer` (FK vers `ps_gpsr_entity`)
    *   `id_gpsr_entity_eu_responsible` (FK vers `ps_gpsr_entity`)
    *   `date_add`, `date_upd`
*   `ps_gpsr_product_warning` : Table de jonction pour les relations produit-avertissement.
    *   `id_product` (FK)
    *   `id_product_attribute` (FK)
    *   `id_gpsr_warning` (FK)
*   `ps_gpsr_product_document` : Table de jonction pour les relations produit-document.
    *   `id_product` (FK)
    *   `id_product_attribute` (FK)
    *   `id_gpsr_document` (FK)
*   `ps_gpsr_category_mapping` : Attributions de données GPSR au niveau de la catégorie.
    *   `id_category` (FK)
    *   `id_gpsr_entity_manufacturer`
    *   `id_gpsr_entity_eu_responsible`
*   `ps_gpsr_category_warning` : Table de jonction pour les relations catégorie-avertissement.
*   `ps_gpsr_category_document` : Table de jonction pour les relations catégorie-document.
*   `ps_gpsr_manufacturer_mapping` : Attributions de données GPSR au niveau du fabricant.
    *   `id_manufacturer` (FK)
    *   `id_gpsr_entity_manufacturer`
    *   `id_gpsr_entity_eu_responsible`
*   `ps_gpsr_manufacturer_warning` : Table de jonction pour les relations fabricant-avertissement.
*   `ps_gpsr_manufacturer_document` : Table de jonction pour les relations fabricant-document.
*   `ps_gpsr_global_mapping` : Stocke les données GPSR par défaut globales.
*   `ps_gpsr_match_suggestion` : Stocke les suggestions générées par le matcher.
    *   `id_gpsr_match_suggestion` (PK)
    *   `id_product`
    *   `suggestion_type`
    *   `suggested_data` (JSON)
    *   `date_add`
*   `ps_configuration` : Les paramètres du module sont stockés ici avec des clés comme `GPSR_ENABLED`, `GPSR_CUSTOM_CSS`, `GPSR_API_TOKEN`, `GPSR_CRON_TOKEN`, etc.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| :-------- | :--------------- | :---------------- |
| `actionProductSave` | Après l'enregistrement d'un produit (ajout ou mise à jour). | Déclenche la réévaluation des données GPSR pour le produit, met à jour les mappages ou enregistre les modifications. |
| `actionAfterUpdateProductFormHandler` | Après la mise à jour d'un formulaire produit dans le BO. | Actualise les données GPSR affichées dans l'onglet produit ou déclenche des mises à jour connexes. |
| `actionObjectProductDeleteAfter` | Après la suppression d'un objet produit. | Nettoie les données et mappages GPSR associés pour le produit supprimé. |
| `actionAfterCreateProductFormHandler` | Après la création d'un formulaire produit dans le BO. | Initialise les données GPSR pour un nouveau produit, appliquant potentiellement des mappages par défaut. |
| `displayAfterProductThumbs` | Sur la page produit, après les images du produit. | Rend le bloc d'informations GPSR du front-office. (Le placement dépend du thème/de la configuration) |
| `actionObjectProductAddAfter` | Après l'ajout d'un nouvel objet produit. | Déclenche l'attribution initiale des données GPSR pour le nouveau produit. |
| `displayProductAdditionalInfo` | Sur la page produit, dans la section "Informations supplémentaires". | Rend le bloc d'informations GPSR du front-office, souvent sous forme d'onglet. |
| `displayAdminProductsExtra` | Sur la page d'édition de produit dans le Back Office. | Injecte l'onglet GPSR personnalisé pour la gestion des données spécifiques au produit. |
| `displayBackOfficeHeader` | Dans l'en-tête de chaque page du Back Office. | Charge les CSS/JS spécifiques au module pour les interfaces d'administration, ajoute des éléments de menu. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration définit ses médias (CSS/JS). | Charge les CSS/JS spécifiques au module pour les pages d'administration pertinentes. |
| `displayProductExtraContent` | Sur la page produit, pour les blocs de contenu supplémentaires. | Rend le bloc d'informations GPSR du front-office, offrant un placement flexible. |
| `displayFooterProduct` | Dans la section pied de page de la page produit. | Rend le bloc d'informations GPSR du front-office, souvent sous forme de bloc sous le contenu principal. |
| `displayReassurance` | Dans le bloc de réassurance du produit (par exemple, livraison gratuite, paiement sécurisé). | Rend le bloc d'informations GPSR du front-office, potentiellement sous forme de petit badge ou lien rassurant. |
| `actionProductAttributeUpdate` | Après la mise à jour d'une combinaison de produit (attribut). | Déclenche la réévaluation des données GPSR pour la combinaison spécifique. |
| `actionFrontControllerSetMedia` | Lorsqu'un contrôleur frontal définit ses médias (CSS/JS). | Charge les CSS/JS spécifiques au module pour les pages du front-office où les données GPSR sont affichées. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module GPSR Enterprise, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité ou l'intégration du module.
