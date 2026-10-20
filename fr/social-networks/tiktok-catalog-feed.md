---
title: "Flux de catalogue TikTok - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Flux de catalogue TikTok par MyPresta.eu."
sidebar:
  label: "Flux de catalogue TikTok - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module TikTok Catalog Feed sur MyPresta.eu](https://mypresta.eu/modules/social-networks/tiktok-catalog-feed.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/tiktok-catalog-feed/)
>
> ---


# Flux de catalogue TikTok

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Assurez-vous que votre serveur peut gérer la génération de fichiers XML/CSV potentiellement volumineux si vous avez un catalogue très étendu.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

Le module Flux de catalogue TikTok fournit une section dédiée dans votre Back Office PrestaShop pour gérer vos flux de produits.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Cet écran de configuration initial vous permet de définir les paramètres de base de votre flux TikTok.

- **Activer le module :**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module sera actif, vous permettant de générer et de gérer les flux de produits TikTok.
    - *Lorsqu'il est désactivé :* Le module cessera de fonctionner, et aucun flux ne pourra être généré ou accédé.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** Vous l'activeriez lorsque vous êtes prêt à commencer à utiliser les publicités TikTok. Vous pourriez le désactiver temporairement si vous devez effectuer une maintenance ou arrêter vos campagnes publicitaires TikTok.
- **Type de génération de flux :**

  - **Ce que fait ce paramètre :** Détermine si le module génère un fichier CSV (Comma Separated Values) ou XML (Extensible Markup Language) pour votre flux de produits. TikTok prend généralement en charge les deux.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur CSV :* L'URL du flux généré fournira un fichier CSV.
    - *Lorsqu'il est défini sur XML :* L'URL du flux généré fournira un fichier XML.
  - **Valeur recommandée :** XML (souvent préféré pour sa nature structurée, mais CSV fonctionne tout aussi bien pour TikTok).
  - **Scénario / exemple de marchand :** Si la documentation de TikTok ou votre agence de publicité recommande un format spécifique, choisissez-le. Sinon, l'un ou l'autre fonctionne.
- **Langue par défaut pour le flux :**

  - **Ce que fait ce paramètre :** Sélectionne la langue principale pour les données de produit dans votre flux. C'est crucial pour cibler des marchés spécifiques sur TikTok.
  - **Effet de la modification de ce paramètre :** Les titres de produits, descriptions et autres champs dépendants de la langue dans le flux seront extraits de votre boutique PrestaShop dans la langue choisie.
  - **Valeur recommandée :** La langue de votre public cible principal sur TikTok (par exemple, l'anglais pour un marché américain, le français pour un marché français).
  - **Scénario / exemple de marchand :** Si vous ciblez des clients en Allemagne, vous sélectionneriez "Allemand" ici pour vous assurer que vos informations produit sont affichées correctement dans leur langue sur TikTok.
- **Devise par défaut pour le flux :**

  - **Ce que fait ce paramètre :** Sélectionne la devise utilisée pour tous les prix des produits dans votre flux. Cela doit correspondre à la devise de votre marché cible.
  - **Effet de la modification de ce paramètre :** Tous les prix du flux seront convertis ou affichés dans la devise sélectionnée.
  - **Valeur recommandée :** La devise de votre public cible principal sur TikTok (par exemple, USD pour un marché américain, EUR pour un marché européen).
  - **Scénario / exemple de marchand :** Si vos publicités TikTok ciblent des clients au Royaume-Uni, vous sélectionneriez "GBP" pour vous assurer que les prix sont affichés en livres sterling.
- **Pays par défaut pour l'expédition :**

  - **Ce que fait ce paramètre :** Définit le pays par défaut utilisé pour calculer les frais d'expédition et la disponibilité dans le flux. C'est important pour que TikTok comprenne où vos produits peuvent être expédiés.
  - **Effet de la modification de ce paramètre :** Les informations d'expédition dans le flux seront basées sur les règles d'expédition du pays sélectionné configurées dans votre boutique PrestaShop.
  - **Valeur recommandée :** Votre pays de destination d'expédition principal.
  - **Scénario / exemple de marchand :** Si la plupart de vos ventes se font en France, vous sélectionneriez "France" ici.
- **Inclure les produits en rupture de stock :**

  - **Ce que fait ce paramètre :** Détermine si les produits actuellement marqués comme "en rupture de stock" dans votre boutique PrestaShop doivent être inclus dans le flux TikTok.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les produits en rupture de stock apparaîtront dans le flux, généralement avec un statut "non disponible".
    - *Lorsqu'il est désactivé :* Les produits en rupture de stock seront entièrement exclus du flux.
  - **Valeur recommandée :** NON (sauf si vous avez une stratégie spécifique pour les précommandes ou les notifications de retour en stock).
  - **Scénario / exemple de marchand :** Généralement, vous souhaitez afficher uniquement les produits disponibles dans vos publicités pour éviter la frustration des clients. Si vous avez un long délai pour les produits personnalisés, vous pourriez les inclure mais les marquer comme "précommande".
- **Exclure des catégories spécifiques :**

  - **Ce que fait ce paramètre :** Vous permet de sélectionner des catégories de produits spécifiques de votre boutique PrestaShop que vous ne souhaitez PAS voir apparaître dans le flux TikTok.
  - **Effet de la modification de ce paramètre :** Les produits appartenant aux catégories sélectionnées seront omis du flux généré.
  - **Valeur recommandée :** Dépend de votre boutique.
  - **Scénario / exemple de marchand :** Vous pourriez exclure des catégories comme "Cartes cadeaux" ou "Services" si ce ne sont pas des produits physiques adaptés aux publicités de catalogue TikTok. Ou, si vous avez une catégorie B2B uniquement, vous l'excluriez des publicités destinées aux consommateurs.
- **Exclure des produits spécifiques :**

  - **Ce que fait ce paramètre :** Fournit un moyen de sélectionner manuellement des produits individuels qui doivent être exclus du flux TikTok, quelle que soit leur catégorie.
  - **Effet de la modification de ce paramètre :** Les produits sélectionnés ne seront pas inclus dans le flux.
  - **Valeur recommandée :** Dépend de votre boutique.
  - **Scénario / exemple de marchand :** Vous pourriez exclure un produit qui fait partie d'une vente flash à durée limitée que vous ne souhaitez pas annoncer sur TikTok, ou un produit qui a des restrictions légales pour la publicité dans certaines régions.
- **Utiliser la description courte du produit :**

  - **Ce que fait ce paramètre :** Détermine si la description courte ou la description complète de vos produits est utilisée dans le flux TikTok.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* La description de produit plus courte et plus concise sera utilisée.
    - *Lorsqu'il est désactivé :* La description de produit plus longue et complète sera utilisée.
  - **Valeur recommandée :** OUI (les descriptions courtes sont souvent meilleures pour les publicités, car les utilisateurs ont une capacité d'attention limitée).
  - **Scénario / exemple de marchand :** Les publicités TikTok bénéficient d'informations concises. L'utilisation de la description courte garantit que votre texte publicitaire est percutant et direct.
- **Exporter les caractéristiques du produit en tant qu'attributs :**

  - **Ce que fait ce paramètre :** S'il est activé, les caractéristiques de vos produits PrestaShop (comme "Matériau", "Couleur", "Taille") seront exportées en tant qu'attributs supplémentaires dans le flux TikTok, fournissant des informations plus détaillées sur le produit.
  - **Effet de la modification de ce paramètre :** Des informations produit plus détaillées seront disponibles pour TikTok pour un meilleur ciblage et affichage des publicités.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** Si vous vendez des vêtements, l'exportation de "Couleur" et "Taille" en tant qu'attributs permet à TikTok d'afficher des publicités plus spécifiques (par exemple, "Robe rouge, Taille M").
- **Exporter les combinaisons de produits (variantes) :**

  - **Ce que fait ce paramètre :** Crucial pour les boutiques avec des produits qui ont des variations (par exemple, un T-shirt disponible en différentes tailles et couleurs). Ce paramètre garantit que chaque combinaison unique est exportée comme un article distinct dans le flux.
  - **Effet de la modification de ce paramètre :** Chaque variante de produit aura sa propre entrée dans le flux, avec son prix, son stock et son image spécifiques, permettant à TikTok d'afficher la variante exacte annoncée.
  - **Valeur recommandée :** OUI (presque toujours, sauf si vous ne vendez que des produits simples sans variations).
  - **Scénario / exemple de marchand :** Si vous vendez une chaussure disponible en tailles 7, 8 et 9, l'activation de cette option garantit que TikTok voit trois produits distincts, chacun avec son propre SKU et sa propre disponibilité.
- **Exporter l'attribut Taille :**

  - **Ce que fait ce paramètre :** Spécifiquement pour les produits avec des combinaisons, ce paramètre garantit que l'attribut "taille" de chaque combinaison est explicitement inclus dans le flux, ce qui est important pour les vêtements et les chaussures.
  - **Effet de la modification de ce paramètre :** La taille de chaque variante de produit sera clairement indiquée dans le flux.
  - **Valeur recommandée :** OUI (surtout pour la mode, les chaussures ou tout produit dépendant de la taille).
  - **Scénario / exemple de marchand :** Pour un magasin de vêtements, cela garantit qu'un "T-shirt bleu grande taille" est correctement identifié par TikTok, et non seulement un "T-shirt bleu".
- **Exporter la date de disponibilité :**

  - **Ce que fait ce paramètre :** Inclut la date de "disponibilité à la commande" pour les produits, ce qui est utile pour les articles en précommande ou les produits avec des dates de sortie futures.
  - **Effet de la modification de ce paramètre :** TikTok recevra des informations sur la date de disponibilité d'un produit.
  - **Valeur recommandée :** OUI (si vous utilisez cette fonctionnalité dans PrestaShop).
  - **Scénario / exemple de marchand :** Si vous lancez un nouveau produit le mois prochain, cela permet à TikTok d'afficher des publicités de "précommande" avec la date de disponibilité correcte.
- **Mappage des catégories de produits Google :**

  - **Ce que fait ce paramètre :** TikTok s'appuie souvent sur la taxonomie étendue des produits de Google. Cette section vous permet de mapper vos catégories PrestaShop aux catégories de produits Google les plus pertinentes. Cela améliore la pertinence et le ciblage des publicités.
  - **Effet de la modification de ce paramètre :** Vos produits seront correctement catégorisés selon la taxonomie de Google dans le flux, que TikTok utilise pour une meilleure compréhension et un meilleur ciblage.
  - **Valeur recommandée :** Mappez autant de catégories que possible.
  - **Scénario / exemple de marchand :** Si vous avez une catégorie PrestaShop "Robes d'été", vous la mapperiez à une catégorie de produits Google comme "Vêtements et accessoires > Vêtements > Robes".
- **Générer l'URL du flux :**

  - **Ce que fait ce paramètre :** Après avoir configuré tous les paramètres, ce bouton génère l'URL unique de votre flux de produits TikTok. C'est cette URL que vous fournirez au Gestionnaire de publicités TikTok.
  - **Effet de la modification de ce paramètre :** Cliquer sur ce bouton affichera l'URL. Le flux à cette URL reflétera tous vos paramètres choisis.
  - **Valeur recommandée :** Cliquez sur ce bouton après avoir finalisé tous les autres paramètres.
  - **Scénario / exemple de marchand :** Une fois que vous avez tout configuré, cliquez sur ce bouton, copiez l'URL et collez-la dans votre Gestionnaire de publicités TikTok lors de la configuration de votre catalogue.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module fournit une section dédiée dans votre Back Office PrestaShop pour gérer et générer vos flux de produits TikTok.

**Nom de l'écran et emplacement du menu :**
Vous pouvez accéder à cette section via le menu principal de PrestaShop : **Catalogue > Flux TikTok**.

Cette section présente généralement un tableau de bord ou une liste des flux générés, vous permettant de gérer différentes configurations de flux si le module prend en charge plusieurs flux (par exemple, pour différentes langues ou devises).

#### 2.2.1 Tableau de bord du flux TikTok (Back Office > Catalogue > Flux TikTok)

C'est le point d'entrée principal pour la gestion de vos flux TikTok.

- **Actions et paramètres disponibles :**

  - **Liste des flux :** Vous verrez un tableau ou une liste de tous vos flux TikTok configurés. Chaque entrée affichera généralement :
    - **Nom du flux :** Un nom descriptif pour votre flux (par exemple, "Flux anglais US", "Flux français EU").
    - **Langue :** La langue des produits dans ce flux.
    - **Devise :** La devise des prix dans ce flux.
    - **Dernière génération :** L'horodatage de la dernière mise à jour du flux.
    - **URL du flux :** Le lien direct vers le fichier de flux généré (CSV ou XML).
    - **Actions :** Boutons pour "Modifier", "Générer maintenant" ou "Supprimer" le flux.
  - **Bouton "Ajouter un nouveau flux" :** Vous permet de créer une nouvelle configuration de flux, potentiellement pour une langue, une devise ou un ensemble d'exclusions de produits différents.
  - **Bouton "Générer tous les flux" :** Une option pratique pour actualiser tous vos flux configurés en une seule fois.
- **Effet des modifications :**

  - **Ajout d'un nouveau flux :** Crée une nouvelle instance de configuration, vous permettant de définir un ensemble de règles distinct (langue, devise, exclusions) pour un flux TikTok distinct. Ceci est utile pour les boutiques multi-pays ou multilingues.
  - **Modification d'un flux :** Vous amène à un formulaire de configuration (similaire à la configuration principale du module, mais spécifique à cette instance de flux) où vous pouvez ajuster ses paramètres.
  - **Génération d'un flux :** Déclenche le module pour traiter votre catalogue de produits en fonction des paramètres du flux et créer/mettre à jour le fichier de flux à son URL unique. Ceci est crucial pour garantir que TikTok dispose toujours des informations produit les plus récentes.
  - **Suppression d'un flux :** Supprime la configuration du flux et son fichier généré associé.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**

  1. **Configuration initiale :** Créez au moins un flux pour votre marché cible principal (par exemple, anglais, USD).
  2. **Configuration multi-marchés :** Si vous ciblez plusieurs pays ou langues, créez un flux distinct pour chacun, en configurant les paramètres de langue, de devise et de pays de manière appropriée.
  3. **Génération régulière :** TikTok extrait généralement les flux selon un calendrier (par exemple, quotidiennement). Vous pouvez cliquer manuellement sur "Générer maintenant" si vous avez apporté des modifications importantes aux produits (nouveaux produits, mises à jour de prix, modifications de stock) et que vous souhaitez que TikTok les reflète immédiatement. Sinon, le module dispose souvent d'un mécanisme de génération automatique ou d'une configuration de tâche cron (voir la section Développeur).
  4. **Surveiller la santé du flux :** Vérifiez régulièrement votre Gestionnaire de publicités TikTok pour détecter toute erreur ou avertissement de flux. Si des problèmes surviennent, examinez les paramètres de votre module et régénérez le flux.

#### 2.2.2 Formulaire de configuration du flux (accessible via "Ajouter un nouveau flux" ou "Modifier" un flux)

Cet écran est l'endroit où vous définissez les paramètres spécifiques pour un flux de produits TikTok individuel. Il reflète de nombreux paramètres trouvés sur la page de configuration principale du module, mais les applique à une seule instance de flux.

- **Champs et colonnes du formulaire :**

  - **Nom du flux :** Un nom unique et descriptif pour ce flux spécifique (par exemple, "Catalogue anglais US", "Catalogue allemand DE").
  - **Langue :** Sélectionnez la langue pour ce flux.
  - **Devise :** Sélectionnez la devise pour ce flux.
  - **Pays :** Sélectionnez le pays par défaut pour l'expédition pour ce flux.
  - **Inclure les produits en rupture de stock :** (Identique à ci-dessus, mais spécifique à ce flux).
  - **Exclure des catégories spécifiques :** (Identique à ci-dessus, mais spécifique à ce flux).
  - **Exclure des produits spécifiques :** (Identique à ci-dessus, mais spécifique à ce flux).
  - **Utiliser la description courte du produit :** (Identique à ci-dessus, mais spécifique à ce flux).
  - **Exporter les caractéristiques du produit en tant qu'attributs :** (Identique à ci-dessus, mais spécifique à ce flux).
  - **Exporter les combinaisons de produits (variantes) :** (Identique à ci-dessus, mais spécifique à ce flux).
  - **Exporter l'attribut Taille :** (Identique à ci-dessus, mais spécifique à ce flux).
  - **Exporter la date de disponibilité :** (Identique à ci-dessus, mais spécifique à ce flux).
  - **Mappage des catégories de produits Google :** (Identique à ci-dessus, mais spécifique à ce flux).
- **Effet des modifications :** L'enregistrement des modifications sur ce formulaire met à jour la configuration du flux spécifique que vous modifiez. Vous devrez ensuite "Générer maintenant" pour ce flux afin d'appliquer les modifications au fichier de flux réel.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Activer le module | OUI | Active/désactive la fonctionnalité du module. |
| | Type de génération de flux | XML | Choisit le format CSV ou XML pour le flux. |
| | Langue par défaut pour le flux | Langue principale de la boutique | Définit la langue pour les données du produit. |
| | Devise par défaut pour le flux | Devise principale de la boutique | Définit la devise pour les prix des produits. |
| | Pays par défaut pour l'expédition | Pays d'expédition principal | Définit le pays par défaut pour les informations d'expédition. |
| | Inclure les produits en rupture de stock | NON | Exclut les articles en rupture de stock du flux. |
| | Exclure des catégories spécifiques | (Aucun) | Omet les produits des catégories sélectionnées. |
| | Exclure des produits spécifiques | (Aucun) | Omet des produits spécifiques du flux. |
| | Utiliser la description courte du produit | OUI | Utilise des descriptions courtes pour la concision. |
| | Exporter les caractéristiques du produit en tant qu'attributs | OUI | Inclut les caractéristiques du produit en tant qu'attributs. |
| | Exporter les combinaisons de produits (variantes) | OUI | Exporte chaque variante de produit comme un article distinct. |
| | Exporter l'attribut Taille | OUI | Inclut l'attribut de taille pour les variantes. |
| | Exporter la date de disponibilité | OUI | Inclut la date de disponibilité du produit. |
| | Mappage des catégories de produits Google | Mapper toutes les catégories pertinentes | Mappe les catégories PrestaShop à la taxonomie de Google pour TikTok. |
| | Générer l'URL du flux | Cliquer après la configuration | Crée/met à jour l'URL unique du flux. |
| **Tableau de bord du flux TikTok** | Ajouter un nouveau flux | N/A | Crée une nouvelle configuration de flux distincte. |
| | Modifier le flux | N/A | Modifie les paramètres d'un flux existant. |
| | Générer maintenant (pour un flux spécifique) | N/A | Met à jour manuellement un seul fichier de flux. |
| | Générer tous les flux | N/A | Met à jour manuellement tous les fichiers de flux configurés. |
| | Supprimer le flux | N/A | Supprime une configuration de flux et son fichier. |
| **Formulaire de configuration du flux** | Nom du flux | Nom descriptif | Identifie le flux spécifique. |
| | (Tous les autres paramètres) | (Comme ci-dessus) | Configure les paramètres pour cette instance de flux individuelle. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q1 : Mes publicités TikTok affichent des prix obsolètes ou des produits en rupture de stock. Que dois-je faire ?**
**R1 :** Cela signifie généralement que votre flux TikTok n'est pas mis à jour assez fréquemment.
1. Allez dans **Catalogue > Flux TikTok** dans votre Back Office PrestaShop.
2. Trouvez le flux pertinent et cliquez sur le bouton "Générer maintenant".
3. Assurez-vous d'avoir une tâche cron configurée pour mettre à jour automatiquement vos flux quotidiennement (recommandé). Vérifiez auprès de votre webmaster ou de votre hébergeur que la tâche cron s'exécute correctement.
4. Vérifiez votre paramètre "Inclure les produits en rupture de stock" dans la configuration du flux. S'il est activé et que vous ne voulez pas d'articles en rupture de stock, désactivez-le.

**Q2 : Certains de mes produits sont manquants dans le flux TikTok.**
**R2 :** Vérifiez les paramètres suivants pour le flux spécifique :
1. **"Exclure des catégories spécifiques" :** Assurez-vous que les catégories des produits manquants ne sont pas sélectionnées ici.
2. **"Exclure des produits spécifiques" :** Assurez-vous que les produits individuels ne sont pas exclus manuellement.
3. **"Inclure les produits en rupture de stock" :** Si les produits sont en rupture de stock et que ce paramètre est désactivé, ils n'apparaîtront pas.
4. **Visibilité du produit :** Assurez-vous que les produits sont actifs et visibles dans votre boutique PrestaShop.

**Q3 : Mes descriptions de produits semblent trop longues ou trop courtes dans le flux TikTok.**
**R3 :** Allez dans la configuration du flux et ajustez le paramètre "Utiliser la description courte du produit" :
- Si les descriptions sont trop longues, activez ce paramètre pour utiliser la description plus courte.
- Si les descriptions sont trop courtes et que vous souhaitez plus de détails, désactivez ce paramètre pour utiliser la description complète.

**Q4 : Comment puis-je mapper efficacement mes catégories aux catégories de produits Google ?**
**R4 :**
1. Accédez à la section "Mappage des catégories de produits Google" dans la configuration de votre flux.
2. Pour chacune de vos catégories PrestaShop, recherchez la catégorie de produits Google la plus pertinente. Soyez aussi précis que possible.
3. Si vous ne trouvez pas de correspondance exacte, choisissez la catégorie plus large la plus proche.
4. Ce mappage aide TikTok à mieux comprendre vos produits pour le ciblage.

**Q5 : J'ai effectué des modifications, mais l'URL du flux affiche toujours d'anciennes données. Quel est le problème ?**
**R5 :** Après avoir apporté des modifications aux paramètres du module ou à la configuration d'un flux spécifique, vous **devez** régénérer le flux. Allez dans **Catalogue > Flux TikTok**, trouvez le flux que vous avez modifié et cliquez sur "Générer maintenant". Si vous avez modifié des paramètres globaux, vous devrez peut-être régénérer tous les flux.

**Q6 : Mon thème personnalisé cause des problèmes d'affichage dans le Back Office pour le module.**
**R6 :** Bien que les composants front-office du module soient invisibles, son interface Back Office pourrait entrer en conflit avec des thèmes d'administration fortement personnalisés.
1. **Vider le cache Smarty :** Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop. Cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions antérieures). Cela résout souvent les petits problèmes d'affichage.
2. **Vérifier les erreurs JavaScript :** Ouvrez la console de développement de votre navigateur (F12) dans le Back Office. Recherchez les erreurs JavaScript. Si vous trouvez des erreurs, contactez le support MyPresta.eu avec les détails de l'erreur.
3. **Changement de thème temporaire :** Si possible, basculez temporairement votre thème Back Office vers le thème PrestaShop par défaut pour voir si le problème persiste. Si cela résout le problème, le conflit est avec votre thème d'administration personnalisé.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de la structure technique du module Flux de catalogue TikTok, destinée aux développeurs et aux webmasters.

### 4.1 Aperçu de l'architecture

Le module Flux de catalogue TikTok suit un modèle MVC (Model-View-Controller) PrestaShop standard, principalement axé sur l'administration du Back Office et la livraison de données au front-office. Il s'appuie sur la classe `Module` de PrestaShop pour l'installation/désinstallation et la configuration, et sur `AdminController` pour la gestion des paramètres de flux. La logique principale tourne autour de la génération dynamique de données produit dans un format CSV ou XML structuré, accessible via un `ModuleFrontController` dédié. Il n'introduit pas de classes `ObjectModel` personnalisées mais interroge directement les données de produit et de catégorie de base de PrestaShop.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs sont responsables de la diffusion du flux de produits réel à TikTok.

- `controllers/front/feed.php`
  - **Nom de la classe et classe parente :** `TiktokfeedFeedModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** C'est le point d'accès principal pour que TikTok récupère le catalogue de produits. Il génère dynamiquement le flux de produits (CSV ou XML) en fonction des paramètres de configuration (langue, devise, exclusions) associés à un ID de flux spécifique. Il gère la récupération des données, le formatage et la sortie sous forme de téléchargement de fichier ou de flux direct. Il est conçu pour être sans état, traitant la requête et renvoyant le flux.
- `controllers/front/index.php`
  - **Nom de la classe et classe parente :** `TiktokfeedIndexModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur est généralement un espace réservé ou un contrôleur de secours. Dans de nombreux modules, `index.php` dans le répertoire du contrôleur frontal peut gérer le routage par défaut ou simplement rediriger. Pour ce module, `feed.php` est le contrôleur frontal critique. Ce `index.php` pourrait ne pas avoir de logique spécifique ou pourrait être utilisé pour une page frontale de module générale si une telle page était implémentée (ce qui n'est pas le cas pour un module de flux).

#### Contrôleurs d'administration Back-Office

Ces contrôleurs gèrent la configuration du module et les paramètres de génération de flux dans le Back Office de PrestaShop.

- `controllers/admin/AdminExportProductsFeedTiktok.php`
  - **Nom de la classe et classe parente :** `AdminExportProductsFeedTiktokController` étend `ModuleAdminController`.
  - **Nom de l'onglet et entité gérée :** Ce contrôleur est responsable de la section principale "Flux TikTok" sous **Catalogue > Flux TikTok**. Il gère la création, la modification et la suppression des configurations de flux individuelles. Il affiche une liste des flux configurés et fournit des formulaires pour leurs paramètres détaillés.
  - **Fonctionnalités clés :**
    - `renderList()` : Affiche le tableau des flux existants.
    - `renderForm()` : Rend le formulaire pour ajouter/modifier un flux, y compris les champs pour la langue, la devise, les exclusions de catégories/produits, le mappage des catégories Google, etc.
    - Gère l'enregistrement et la mise à jour des configurations de flux (`postProcess()`).
    - Déclenche le processus de génération de flux pour des flux spécifiques.
- `controllers/admin/index.php`
  - **Nom de la classe et classe parente :** `AdminTiktokfeedIndexController` étend `ModuleAdminController`.
  - **Nom de l'onglet et entité gérée :** Ce contrôleur sert probablement de point d'entrée principal pour la section d'administration du module, redirigeant potentiellement vers `AdminExportProductsFeedTiktokController` ou fournissant un tableau de bord de haut niveau. Compte tenu de la structure du module, `AdminExportProductsFeedTiktokController` est l'endroit où réside la logique principale de gestion des flux. Ce `index.php` pourrait être pour un aperçu général du module ou une simple redirection.

### 4.3 Classes et modèles de base (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que le module s'appuie principalement sur les classes `ObjectModel` de base de PrestaShop `Product`, `Category`, `Language`, `Currency`, `Carrier` et `Configuration` pour le stockage et la récupération des données. La logique de génération de flux est probablement encapsulée dans le fichier principal du module (`tiktokfeed/index.php`) et le `AdminExportProductsFeedTiktokController`.

### 4.4 Actifs JavaScript (`views/js/`)

- `tiktokfeed/lib/searchTool/views/js/autocomplete.js`
  - **Portée :** Back-office.
  - **Objectif :** Fournit une fonctionnalité d'autocomplétion, probablement utilisée pour sélectionner des produits ou des catégories à exclure, ou pour le mappage des catégories Google. Il lie des écouteurs d'événements aux champs de saisie, effectue des requêtes AJAX pour des suggestions de recherche et met à jour le DOM avec les résultats.
- `tiktokfeed/views/js/admin-app.js`
  - **Portée :** Back-office.
  - **Objectif :** C'est le fichier JavaScript principal pour l'interface Back Office du module. Il gère divers éléments interactifs sur les formulaires de configuration de flux et le tableau de bord. Cela pourrait inclure :
    - La validation des formulaires.
    - Les mises à jour dynamiques basées sur les options sélectionnées (par exemple, afficher/masquer des champs).
    - Les appels AJAX pour enregistrer les paramètres ou déclencher la génération de flux.
    - Les interactions avec les modales fancybox (par exemple, pour la sélection de catégories/produits).

### 4.5 Feuilles de style CSS (`views/css/`)

- `tiktokfeed/lib/searchTool/views/css/autocomplete.css`
  - **Portée :** Style d'administration du Back-office.
  - **Objectif :** Style les listes déroulantes d'autocomplétion et les champs de saisie utilisés par le script `autocomplete.js`, garantissant une expérience de recherche cohérente et conviviale dans les formulaires d'administration.
- `tiktokfeed/views/admin-theme.css`
  - **Portée :** Style d'administration du Back-office.
  - **Objectif :** Fournit des ajustements de style généraux pour l'interface Back Office du module afin de s'intégrer de manière transparente au thème d'administration de PrestaShop. Cela peut inclure des ajustements de mise en page, le style des boutons ou le formatage des tableaux.
- `tiktokfeed/views/css/admin-app.css`
  - **Portée :** Style d'administration du Back-office.
  - **Objectif :** Contient des styles spécifiques pour les composants personnalisés du module, les formulaires et les éléments du tableau de bord dans le Back Office de PrestaShop. Cela peut inclure des styles pour le tableau de liste des flux, les panneaux de configuration et les modales fancybox.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

Le dossier du module ne liste pas explicitement les templates dans un sous-répertoire `hook/`, ce qui implique que le module ne rend pas de contenu directement dans les hooks du front-office. Sa fonction principale est la génération de données, et non l'affichage frontal.

#### Templates d'administration (`views/templates/admin/`)

Ces templates sont utilisés pour rendre l'interface Back Office du module.

- `tiktokfeed/views/templates/admin/dashboard.tpl`
  - **Objectif :** Probablement le template principal du tableau de bord pour la section Flux TikTok, affichant potentiellement un aperçu des flux, leur statut et des actions rapides.
- `tiktokfeed/views/templates/admin/feeds.tpl`
  - **Objectif :** Rend la liste des flux TikTok configurés, généralement un tableau avec des colonnes pour le nom du flux, la langue, la devise, l'URL et les boutons d'action (modifier, générer, supprimer). Ceci est probablement rendu par `AdminExportProductsFeedTiktokController::renderList()`.
- `tiktokfeed/views/templates/admin/form-chrome.tpl`
  - **Objectif :** Un wrapper ou un template partiel utilisé pour fournir un style et une structure cohérents pour les formulaires de configuration du module, incluant potentiellement l'en-tête, le pied de page et les éléments de mise en page générale du formulaire.
- `tiktokfeed/views/templates/admin/layout.tpl`
  - **Objectif :** Un template de mise en page de base pour les pages d'administration du module, définissant la structure globale, y compris l'en-tête, la navigation et les zones de contenu.

#### Autres templates liés à l'administration

Ces templates sont probablement utilisés comme partiels ou pour des composants d'interface utilisateur spécifiques dans les formulaires d'administration.

- `tiktokfeed/lib/searchTool/views/scripts.tpl`
  - **Objectif :** Inclut le JavaScript pour l'outil de recherche, probablement le script `autocomplete.js` et son initialisation.
- `tiktokfeed/views/categories-fancybox.tpl`
  - **Objectif :** Rend le contenu d'une modale Fancybox utilisée pour sélectionner des catégories à exclure ou à mapper.
- `tiktokfeed/views/exclude-products.tpl`
  - **Objectif :** Rend l'interface utilisateur pour la sélection et la gestion des produits à exclure du flux, éventuellement dans une Fancybox ou une section dédiée du formulaire.
- `tiktokfeed/views/google_lang_links.tpl`
  - **Objectif :** Rend les liens ou les éléments d'interface utilisateur liés au mappage des catégories de produits Google, potentiellement pour différentes langues.
- `tiktokfeed/views/returnAlert.tpl`
  - **Objectif :** Un template générique pour afficher des messages/alertes de succès ou d'erreur dans le Back Office.
- `tiktokfeed/views/script-fancybox.tpl`
  - **Objectif :** Inclut le JavaScript pour l'intégration de Fancybox, probablement pour l'ouverture de modales pour la sélection de catégories/produits.
- `tiktokfeed/views/script.tpl`
  - **Objectif :** Un template de script général, éventuellement pour l'initialisation JavaScript à l'échelle du module ou de petits scripts en ligne.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne semble pas créer de tables SQL personnalisées d'après le dossier.
  - Il stocke ses paramètres de configuration (par exemple, type de flux, langue/devise par défaut, listes d'exclusion, mappages de catégories Google) dans la table `ps_configuration` de PrestaShop. Les clés de configuration suivraient généralement un modèle comme `TTF_FEED_TYPE`, `TTF_DEFAULT_LANG`, `TTF_EXCLUDE_CATEGORIES`, etc.
  - Les configurations de flux individuelles (si plusieurs flux sont pris en charge) pourraient être stockées sous forme de tableaux sérialisés dans `ps_configuration` ou potentiellement dans une table personnalisée si le module devait en introduire une (ce qui n'est pas indiqué).
- **Table des hooks enregistrés** :
  La fonction principale du module est la génération de données, et non l'affichage frontal, il n'enregistre donc pas de hooks pour afficher du contenu sur la vitrine (par exemple, `displayHeader`, `displayRightColumn`).
  Il enregistrera cependant les hooks suivants pour sa fonctionnalité principale :

  | Nom du hook | Moment d'exécution | Objectif technique |
  | --- | --- | --- |
  | `actionModuleInstall` | Lors de l'installation du module | Crée des entrées de configuration, enregistre les onglets d'administration. |
  | `actionModuleUninstall` | Lors de la désinstallation du module | Nettoie les entrées de configuration, désenregistre les onglets d'administration. |
  | `actionAdminControllerSetMedia` | Lors du chargement d'un contrôleur d'administration | Met en file d'attente les JS et CSS spécifiques au module pour le Back Office. |
  | `displayBackOfficeHeader` | Rend le contenu dans l'en-tête du Back Office | Potentiellement pour les JS/CSS d'administration globaux ou les notifications. |
  | `actionSchedulerCron` (ou similaire) | Lorsque la tâche cron de PrestaShop s'exécute | Déclenche la génération automatique du flux si configurée. |

### Configuration de la tâche Cron pour la génération automatique de flux

Pour les mises à jour automatiques des flux, vous devrez configurer une tâche cron sur votre serveur pour appeler une URL ou un script spécifique fourni par le module. Cette URL pointe généralement vers un contrôleur frontal qui déclenche la génération du flux.

**Exemple de commande Cron (consultez votre hébergeur pour la syntaxe exacte) :**

Terminal window

```
0 3 \* \* \* wget -q -O /dev/null "https://votreboutique.com/module/tiktokfeed/feed?action=generate\_all&token=VOTRE\_JETON\_SECURISÉ" >/dev/null 2>&1
```

- `0 3 * * *` : Cela planifie l'exécution de la tâche quotidiennement à 3h00 du matin.
- `wget -q -O /dev/null` : Récupère silencieusement l'URL et ignore la sortie.
- `https://votreboutique.com/module/tiktokfeed/feed?action=generate_all&token=VOTRE_JETON_SECURISÉ` : C'est l'URL qui déclenche la génération du flux. Le paramètre `token` est crucial pour la sécurité afin d'empêcher tout accès non autorisé. Le module doit fournir ce jeton dans sa configuration ou sa documentation.
- `>/dev/null 2>&1` : Redirige toutes les sorties vers null, évitant les notifications par e-mail inutiles.

**Important :** L'URL et le jeton exacts seront fournis par le module après la configuration. Utilisez toujours le jeton sécurisé pour protéger votre point d'accès de génération de flux.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel des développeurs, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Assurez-vous d'utiliser la dernière version compatible du module pour votre boutique PrestaShop.
