---
title: "Mass price change pro - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Mass price change pro par MyPresta.eu."
sidebar:
  label: "Mass price change pro - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Mass price change pro sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-price-change-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/mass-price-change-pro/)
>
> ---


# Mass price change pro

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.0.0 - 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour le fonctionnement général de PrestaShop et sont suffisantes pour ce module.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

Le module « Mass price change pro » offre une interface complète dans le Back Office de PrestaShop pour définir et exécuter vos changements de prix. Tous les paramètres sont accessibles via la page de configuration principale du module.

### 2.1 Page de configuration du module (Back Office > Modules > Gestionnaire de modules > Mass price change pro > Configurer)

En accédant à la page de configuration du module, vous trouverez une série d'onglets ou de sections conçus pour vous guider tout au long du processus de définition de votre opération de changement de prix.

#### **Onglets / Sections principales :**

La configuration du module est généralement organisée en plusieurs sections clés, souvent présentées sous forme d'onglets ou de blocs distincts sur la page principale. Bien que les libellés exacts puissent varier légèrement entre les versions, la fonctionnalité principale reste cohérente :

1.  **Que faire (WTD) :** Définir le type de changement de prix.
2.  **Produits cibles :** Sélectionner les produits qui seront affectés.
3.  **Contraintes :** Ajouter des conditions supplémentaires pour le ciblage.
4.  **Règles :** Définir des règles de prix spécifiques.
5.  **Aperçu :** Voir l'impact avant d'appliquer.
6.  **Historique :** Examiner les opérations passées.
7.  **Planificateur :** Planifier les changements de prix futurs.
8.  **Import/Export CSV :** Gérer les prix via CSV.
9.  **Configuration Cron :** Configurer les tâches automatisées.

Passons en revue chaque section en détail :

#### **4.1.1 Que faire (WTD)**

Cette section est l'endroit où vous définissez l'action principale de votre changement de prix.

-   **Ce que fait ce paramètre :** Détermine comment les prix des produits seront modifiés. Vous choisissez entre augmenter, diminuer ou définir un nouveau prix, et si cela s'applique au prix de base, au prix spécifique ou à l'impact sur les déclinaisons.
-   **Effet de la modification de ce paramètre :**
    -   *Augmenter d'un pourcentage :* Ajoute un pourcentage du prix actuel au produit.
    -   *Diminuer d'un pourcentage :* Soustrait un pourcentage du prix actuel du produit.
    -   *Augmenter d'un montant fixe :* Ajoute une valeur monétaire spécifique au prix du produit.
    -   *Diminuer d'un montant fixe :* Soustrait une valeur monétaire spécifique du prix du produit.
    -   *Définir un nouveau prix à :* Remplace le prix actuel par une nouvelle valeur spécifiée.
    -   *Appliquer au prix de base :* Modifie le prix principal du produit.
    -   *Appliquer au prix spécifique :* Modifie les prix définis via les règles de « Prix spécifiques » (par exemple, pour les groupes, les pays ou la quantité).
    -   *Appliquer à l'impact sur les déclinaisons :* Modifie l'ajustement de prix pour les déclinaisons de produits (attributs).
-   **Valeur recommandée :** Dépend entièrement de votre objectif commercial. Commencez par un objectif clair (par exemple, « augmenter tous les prix de 5 % ») avant de sélectionner.
-   **Scénario / exemple de marchand :**
    -   *Scénario 1 (Inflation) :* « Je dois augmenter tous les prix de mes produits de 3 % en raison de l'augmentation des coûts des fournisseurs. » -> Sélectionnez « Augmenter d'un pourcentage », entrez « 3 » et choisissez « Appliquer au prix de base ».
    -   *Scénario 2 (Liquidation) :* « Je veux réduire le prix de tous les produits de la catégorie 'Collection d'été' de 5 €. » -> Sélectionnez « Diminuer d'un montant fixe », entrez « 5 » et choisissez « Appliquer au prix de base ».

#### **4.1.2 Produits cibles**

C'est ici que vous sélectionnez précisément *quels* produits seront affectés par le changement de prix.

-   **Ce que fait ce paramètre :** Vous permet de filtrer les produits en fonction de divers critères tels que les catégories, les fabricants, les fournisseurs, les ID de produits spécifiques, ou même les produits sans prix spécifique.
-   **Effet de la modification de ce paramètre :**
    -   *Sélection de catégories :* Seuls les produits des catégories choisies seront pris en compte.
    -   *Sélection de fabricants/fournisseurs :* Seuls les produits de ces marques/sources seront affectés.
    -   *Saisie d'ID de produits :* Seuls les produits exacts que vous listez seront ciblés.
    -   *Filtrage par « Produits sans prix spécifique » :* Utile pour s'assurer que vous ne remplacez pas accidentellement des règles de prix spécifiques existantes.
-   **Valeur recommandée :** Soyez aussi précis que possible pour éviter des changements involontaires. Utilisez plusieurs filtres si nécessaire.
-   **Scénario / exemple de marchand :**
    -   *Scénario 1 (Mise à jour de marque) :* « Mon fournisseur principal, 'Fashionista Co.', a augmenté ses prix. Je dois mettre à jour tous les produits de ce fabricant. » -> Sélectionnez « Fabricant », puis choisissez « Fashionista Co. ».
    -   *Scénario 2 (Stock saisonnier) :* « Je veux mettre en solde tous les produits de la catégorie 'Vêtements d'hiver'. » -> Sélectionnez « Catégorie », puis choisissez « Vêtements d'hiver ».

#### **4.1.3 Contraintes**

Cette section vous permet d'ajouter des conditions encore plus spécifiques à votre ciblage de produits.

-   **Ce que fait ce paramètre :** Fournit des options de filtrage avancées, telles que le ciblage de produits dans une certaine fourchette de prix, de produits avec des caractéristiques ou attributs spécifiques, ou de produits actuellement en stock.
-   **Effet de la modification de ce paramètre :**
    -   *Fourchette de prix :* Seuls les produits dont le prix actuel se situe entre le minimum et le maximum spécifiés seront inclus.
    -   *Caractéristiques/Attributs :* Ciblez les produits qui ont une caractéristique particulière (par exemple, « Couleur : Rouge ») ou un attribut (par exemple, « Taille : XL »).
    -   *En stock uniquement :* Garantit que seuls les produits actuellement disponibles à l'achat sont affectés.
-   **Valeur recommandée :** Utilisez-les pour affiner davantage votre liste cible, en particulier pour les promotions complexes ou les ajustements basés sur l'inventaire.
-   **Scénario / exemple de marchand :**
    -   *Scénario 1 (Vente de produits premium) :* « Je veux offrir une réduction sur les articles de grande valeur. Réduisez les prix de 10 % pour tous les produits de plus de 100 € dans la catégorie 'Électronique'. » -> Dans « Produits cibles », sélectionnez « Électronique ». Dans « Contraintes », définissez la « Fourchette de prix » de « 100 € » à « Max ».
    -   *Scénario 2 (Liquidation de stock spécifique) :* « Je dois liquider toutes les chemises de couleur 'Bleu' qui sont actuellement en stock. » -> Dans « Produits cibles », sélectionnez « Chemises ». Dans « Contraintes », sélectionnez « Attribut : Couleur > Bleu » et « En stock uniquement ».

#### **4.1.4 Règles**

Cette section vous permet de définir une logique de prix plus complexe, pouvant remplacer ou compléter l'action générale « Que faire ».

-   **Ce que fait ce paramètre :** Vous permet de créer des ajustements de prix conditionnels. Par exemple, « Si un produit est dans la Catégorie A, augmentez son prix de 5 %, mais s'il est dans la Catégorie B, diminuez-le de 10 %. »
-   **Effet de la modification de ce paramètre :** Permet des stratégies de prix très nuancées où différents groupes de produits reçoivent des ajustements différents au sein d'une seule opération.
-   **Valeur recommandée :** Utilisez ceci lorsqu'un changement de prix unique et uniforme n'est pas suffisant pour tous les produits ciblés.
-   **Scénario / exemple de marchand :**
    -   *Scénario (Remise échelonnée) :* « Pour les produits de la catégorie 'Accessoires', si leur prix est compris entre 10 € et 50 €, diminuez-le de 5 %. Si leur prix est supérieur à 50 €, diminuez-le de 10 %. » -> Vous configurerez ici plusieurs règles, chacune avec sa propre fourchette de prix et son propre ajustement.

#### **4.1.5 Aperçu**

Avant de valider toute modification, cette section cruciale vous permet de revoir les modifications proposées.

-   **Ce que fait ce paramètre :** Affiche une liste des produits qui seront affectés, montrant leur prix actuel et leur nouveau prix après l'opération.
-   **Effet de la modification de ce paramètre :** Il s'agit d'une section en lecture seule. Elle fournit un filet de sécurité, vous permettant de détecter toute erreur dans votre ciblage ou vos règles avant qu'elles ne soient appliquées à votre boutique en ligne.
-   **Valeur recommandée :** **TOUJOURS** examiner attentivement l'aperçu avant de procéder au changement de prix réel.
-   **Scénario / exemple de marchand :**
    -   *Scénario (Double vérification) :* « J'ai configuré une remise de 10 % pour toutes les 'Robes d'été'. L'aperçu montre une robe qui, je le sais, ne devrait pas être remise. Je peux revenir à 'Produits cibles' ou 'Contraintes' pour affiner ma sélection. »

#### **4.1.6 Historique**

Cette section conserve un enregistrement de toutes les opérations de changement de prix passées.

-   **Ce que fait ce paramètre :** Affiche un journal de qui a effectué quel changement de prix, quand il a été effectué et quel type d'opération il s'agissait.
-   **Effet de la modification de ce paramètre :** Il s'agit d'un journal en lecture seule. Il est inestimable pour l'audit, le dépannage et la compréhension des décisions de prix passées.
-   **Valeur recommandée :** Vérifiez régulièrement l'historique, surtout si plusieurs personnes gèrent la boutique, pour vous assurer que toutes les modifications sont intentionnelles et suivies.
-   **Scénario / exemple de marchand :**
    -   *Scénario (Audit) :* « Un client a signalé un prix incorrect. Je peux vérifier l'historique pour voir si un changement de prix de masse récent aurait pu en être la cause et qui a initié le changement. »

#### **4.1.7 Planificateur**

Planifiez l'exécution automatique de vos changements de prix à une date et une heure futures.

-   **Ce que fait ce paramètre :** Vous permet de définir une opération de changement de prix et de la configurer pour qu'elle s'exécute automatiquement à une date et une heure spécifiées. Vous pouvez également la configurer pour annuler les prix après une certaine période, parfait pour les ventes temporaires.
-   **Effet de la modification de ce paramètre :**
    -   *Exécution planifiée :* Le changement de prix sera appliqué sans intervention manuelle à l'heure choisie.
    -   *Annuler les prix :* Les produits retrouveront leurs prix d'origine (ou un prix différent spécifié) après la fin de la période de vente.
-   **Valeur recommandée :** Essentiel pour gérer les promotions, les ventes saisonnières ou tout changement de prix qui doit être mis en ligne en dehors des heures de bureau.
-   **Scénario / exemple de marchand :**
    -   *Scénario (Vente Black Friday) :* « Je veux appliquer une remise de 20 % à tous les produits à 00h00 le Black Friday et revenir aux prix d'origine à 23h59 le Cyber Monday. » -> Configurez l'opération de remise, planifiez-la pour le Black Friday et ajoutez une planification d'annulation pour le Cyber Monday.

#### **4.1.8 Import/Export CSV**

Gérez les prix de vos produits à l'aide de fichiers CSV pour un contrôle avancé ou une manipulation de données externe.

-   **Ce que fait ce paramètre :**
    -   *Exportation :* Vous permet d'exporter une liste de produits (selon vos critères de ciblage) avec leurs prix actuels dans un fichier CSV.
    -   *Importation :* Vous permet de télécharger un fichier CSV contenant les ID de produits et les nouveaux prix, en appliquant ces modifications à votre boutique.
-   **Effet de la modification de ce paramètre :**
    -   *Exportation :* Fournit une feuille de calcul de vos produits ciblés et de leurs prix, qui peut être modifiée en externe.
    -   *Importation :* Remplace ou met à jour les prix des produits listés dans le CSV, offrant un moyen puissant de gérer de grandes listes de prix complexes.
-   **Valeur recommandée :** Utilisez l'exportation pour une analyse détaillée ou lorsque vous devez effectuer des ajustements de prix très spécifiques et non formulaires qui sont plus faciles à gérer dans une feuille de calcul. Utilisez l'importation lorsque vous avez une liste prédéfinie de nouveaux prix provenant d'un fournisseur ou d'un système externe.
-   **Scénario / exemple de marchand :**
    -   *Scénario (Liste de prix fournisseur) :* « Mon fournisseur m'a envoyé une nouvelle liste de prix pour 500 produits. Au lieu de mettre à jour manuellement chacun d'eux, je peux exporter ma liste de produits actuelle, la faire correspondre à celle du fournisseur, ajuster les prix dans le CSV, puis la réimporter. »

#### **4.1.9 Configuration Cron**

Configurez la tâche cron du module pour les tâches automatisées, en particulier pour les changements de prix planifiés.

-   **Ce que fait ce paramètre :** Fournit la commande ou l'URL nécessaire pour configurer une tâche cron sur votre serveur. Cette tâche cron est essentielle pour que la fonction « Planificateur » fonctionne, car elle vérifie et exécute périodiquement les changements de prix planifiés.
-   **Effet de la modification de ce paramètre :**
    -   *Configuration Cron correcte :* Garantit que vos changements de prix planifiés s'exécutent automatiquement aux heures spécifiées. Sans une tâche cron correctement configurée, les tâches planifiées ne s'exécuteront pas.
-   **Valeur recommandée :** Suivez les instructions fournies par le module pour configurer la tâche cron sur votre serveur d'hébergement. Généralement, cela implique d'ajouter une ligne au crontab de votre serveur. Le module fournit généralement la commande exacte.
-   **Scénario / exemple de marchand :**
    -   *Scénario (Ventes automatisées) :* « J'ai planifié une vente flash pour la semaine prochaine. Pour m'assurer qu'elle commence exactement à l'heure, je dois m'assurer que la tâche cron est correctement configurée et s'exécute toutes les 5 à 15 minutes. » -> Copiez la commande cron fournie et ajoutez-la au gestionnaire cron de votre serveur.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Que faire** | Type d'opération (Augmenter/Diminuer/Définir) | N/A (dépend de l'objectif) | Définit comment les prix sont modifiés (par exemple, +5 %, -10 €, définir à 25 €). |
| | Valeur (Pourcentage/Fixe) | N/A (dépend de l'objectif) | Le montant ou le pourcentage de l'ajustement de prix. |
| | Appliquer à (Base/Spécifique/Déclinaisons) | Prix de base | Détermine le type de prix affecté. |
| **Produits cibles** | Catégories | Sélectionner spécifique | Filtre les produits par catégorie. |
| | Fabricants | Sélectionner spécifique | Filtre les produits par marque. |
| | Fournisseurs | Sélectionner spécifique | Filtre les produits par fournisseur. |
| | ID de produits | Saisir la liste | Cible des produits spécifiques par ID. |
| | Produits sans prix spécifique | Oui/Non | Exclut les produits avec des prix spécifiques existants. |
| **Contraintes** | Fourchette de prix (Min/Max) | N/A (facultatif) | Filtre les produits dans une fourchette de prix. |
| | Caractéristiques / Attributs | Sélectionner spécifique | Filtre les produits par leurs caractéristiques ou attributs. |
| | En stock uniquement | Oui/Non | N'affecte que les produits actuellement en stock. |
| **Règles** | Ajouter une règle | N/A (facultatif) | Définit des ajustements de prix conditionnels basés sur des critères. |
| **Aperçu** | (Tableau en lecture seule) | N/A | Affiche les prix actuels par rapport aux nouveaux prix pour les produits affectés. **Toujours vérifier !** |
| **Historique** | (Journal en lecture seule) | N/A | Enregistre toutes les opérations de changement de prix passées. |
| **Planificateur** | Planifier l'opération | N/A (facultatif) | Définit une date/heure future pour l'exécution automatique des changements de prix. |
| | Annuler les prix | N/A (facultatif) | Planifie une annulation de prix après une période définie. |
| **Import/Export CSV** | Exporter les produits | N/A (facultatif) | Télécharge les données des produits ciblés pour une édition externe. |
| | Importer les prix | N/A (facultatif) | Télécharge un CSV pour appliquer de nouveaux prix aux produits. |
| **Configuration Cron** | Commande Cron | Copier depuis le module | Essentiel pour les tâches planifiées automatisées. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes prix n'ont pas changé après avoir appliqué l'opération. Qu'est-ce qui n'a pas fonctionné ?**
R1 :

-   **Vérifiez l'onglet Historique :** Vérifiez que l'opération a été enregistrée et terminée avec succès.
-   **Videz le cache :** PrestaShop utilise la mise en cache. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ». Votre navigateur peut également mettre en cache d'anciennes données, alors essayez de vider le cache de votre navigateur ou d'afficher la boutique en mode incognito.
-   **Vérifiez le ciblage :** Revoyez vos paramètres « Produits cibles » et « Contraintes ». Avez-vous accidentellement exclu les produits que vous aviez l'intention de modifier ?
-   **Prix spécifiques :** Si vous essayiez de modifier les prix de base mais que les produits ont des prix spécifiques, les prix spécifiques pourraient les remplacer. Vérifiez si votre opération a été configurée pour affecter les « Prix spécifiques » ou le « Prix de base ».

**Q2 : Mon changement de prix planifié ne s'est pas exécuté à l'heure spécifiée.**
R2 :

-   **Tâche Cron :** La raison la plus courante est une tâche cron mal configurée ou non exécutée. Allez dans l'onglet **Configuration Cron** dans la configuration du module. Assurez-vous que la commande cron fournie est correctement ajoutée au crontab de votre serveur et qu'elle s'exécute à la fréquence recommandée (par exemple, toutes les 5 à 15 minutes). Si vous ne savez pas comment faire, contactez votre hébergeur ou un webmaster.
-   **Module activé :** Assurez-vous que le module « Mass price change pro » est toujours activé dans votre Gestionnaire de modules.

**Q3 : J'ai accidentellement changé les mauvais prix. Puis-je annuler les modifications ?**
R3 :

-   **Onglet Historique :** L'onglet « Historique » du module offre souvent une option pour annuler une opération précédente. Recherchez un bouton « Annuler » ou « Revenir » à côté de l'opération spécifique que vous souhaitez annuler.
-   **Sauvegarde de la base de données :** Si une option d'annulation n'est pas disponible ou ne fonctionne pas comme prévu, cela souligne l'importance d'avoir une sauvegarde récente de la base de données. Vous devrez restaurer votre base de données à un point antérieur au changement de prix erroné. **Toujours sauvegarder avant les opérations majeures !**

**Q4 : Le module ne s'affiche pas correctement ou provoque des erreurs après l'installation.**
R4 :

-   **Version de PrestaShop :** Assurez-vous d'avoir téléchargé et installé la version correcte du module pour votre installation PrestaShop spécifique (par exemple, PrestaShop 8.x, 1.7.x).
-   **Compatibilité PHP :** Vérifiez que la version PHP de votre serveur se situe dans la plage prise en charge par le module (PHP 5.6 - 8.5).
-   **Conflits de thème :** Parfois, les thèmes personnalisés peuvent interférer. Passez temporairement au thème PrestaShop par défaut pour voir si le problème est résolu. Si c'est le cas, votre thème pourrait nécessiter des ajustements.
-   **Journaux d'erreurs :** Vérifiez votre mode de débogage PrestaShop (s'il est activé) ou les journaux d'erreurs PHP de votre serveur pour des messages d'erreur spécifiques. Ceux-ci peuvent fournir des indices aux développeurs.

**Q5 : Comment traduire le texte du module dans d'autres langues ?**
R5 :

-   Dans votre Back Office PrestaShop, naviguez vers **International > Traductions**.
-   Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez « Mass price change pro » dans la liste déroulante des modules.
-   Vous pouvez ensuite traduire toutes les chaînes du module dans les langues souhaitées.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module « Mass price change pro ».

### 4.1 Vue d'ensemble de l'architecture

Le module « Mass price change pro » suit une architecture de module PrestaShop standard, exploitant principalement la classe `Module` pour sa fonctionnalité principale et `ModuleFrontController` pour des tâches spécifiques du front-office comme l'exécution cron. Le module s'appuie fortement sur son `index.php` (fichier principal du module) pour la configuration et le traitement du back-office, utilisant des templates Smarty pour le rendu des différentes sections de configuration. Il intègre du JavaScript personnalisé pour des éléments d'interface utilisateur améliorés comme le ciblage de produits et l'autocomplétion, et du CSS pour le style. Bien qu'il ne définisse pas explicitement de classes `ObjectModel` dans l'inventaire fourni, il interagit probablement directement avec les tables `Product`, `SpecificPrice` et `Configuration` du cœur de PrestaShop.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   `controllers/front/cron.php`
    -   **Nom de la classe :** `MassPriceProCronModuleFrontController` (probablement, basé sur la convention de nommage des fichiers)
    -   **Classe parente :** `ModuleFrontController`
    -   **Responsabilité :** Ce contrôleur est conçu pour être appelé par une tâche cron côté serveur. Son rôle principal est d'exécuter les opérations de changement de prix planifiées définies dans la configuration du back-office du module. Il traite des tâches telles que l'application de remises planifiées, l'annulation des prix ou l'exécution d'autres ajustements de prix automatisés. Il renvoie généralement un simple message de succès/échec ou enregistre son activité.
-   `controllers/front/index.php`
    -   **Nom de la classe :** `MassPriceProIndexModuleFrontController` (probablement)
    -   **Classe parente :** `ModuleFrontController`
    -   **Responsabilité :** Ce contrôleur pourrait servir de point d'entrée général pour les actions du module front-office qui ne rentrent pas dans une catégorie spécifique, ou il pourrait être un espace réservé. Compte tenu de la nature du module, il est moins probable qu'il ait des fonctionnalités directement visibles par le client et plus probable qu'il gère les requêtes AJAX en arrière-plan ou la récupération de données spécifiques si nécessaire par les scripts front-end.

#### Contrôleurs d'administration Back-Office

Le module ne semble pas utiliser de fichiers `AdminController` dédiés d'après l'inventaire fourni. Toute la configuration et le traitement du back-office sont probablement gérés directement dans la méthode `getContent()` du fichier principal `masspricepro/index.php`.

### 4.3 Classes et modèles principaux (`classes/`)

D'après l'inventaire fourni, il n'y a pas de classes personnalisées ou de définitions `ObjectModel` dans un répertoire `classes/`. Cela suggère que le module interagit directement avec les classes `ObjectModel` principales de PrestaShop `Product`, `SpecificPrice`, `Category`, `Manufacturer`, `Supplier`, `Configuration` et potentiellement d'autres tables de base de données associées. La logique de changement de prix est probablement encapsulée dans des méthodes de la classe principale `MassPricePro` (dans `index.php`).

### 4.4 Actifs JavaScript (`views/js/`)

-   `masspricepro/lib/searchTool/views/js/autocomplete.js`
    -   **Portée :** Probablement Front-office (si utilisé pour la recherche de produits) et Back-office (pour le ciblage de produits).
    -   **Détails :** Fournit une fonctionnalité d'autocomplétion générique. Il écoute la saisie de l'utilisateur dans les champs de texte, envoie des requêtes AJAX à un point de terminaison backend (éventuellement `controllers/front/index.php` ou un gestionnaire AJAX dédié dans le fichier principal du module), et affiche des suggestions dans une liste déroulante.
-   `masspricepro/views/js/jquery.autocomplete.js`
    -   **Portée :** Probablement Back-office.
    -   **Détails :** Un plugin d'autocomplétion basé sur jQuery. Il pourrait s'agir d'une implémentation spécifique ou d'une dépendance pour les interfaces de sélection de produits du module dans le back-office, par exemple lors du ciblage de produits par nom ou ID. Il gère le rendu de l'interface utilisateur des suggestions et les événements de sélection.
-   `masspricepro/views/js/mpp_pro.js`
    -   **Portée :** Back-office.
    -   **Détails :** Il s'agit probablement du fichier JavaScript principal pour la configuration du back-office du module. Il contiendrait :
        -   Des écouteurs d'événements pour les soumissions de formulaires, les changements d'onglets, les clics sur les boutons (par exemple, « Appliquer les modifications », « Aperçu », « Ajouter une règle »).
        -   Des appels AJAX à la méthode `getContent()` ou à un contrôleur frontal pour le traitement des données (par exemple, génération d'aperçus, enregistrement des paramètres, exécution des changements de prix).
        -   La manipulation du DOM pour afficher/masquer dynamiquement des sections, mettre à jour les tableaux d'aperçu ou gérer les entrées de règles.
        -   La logique de validation pour les champs de formulaire.
-   `masspricepro/views/js/mpp_target_products.js`
    -   **Portée :** Back-office.
    -   **Détails :** Gère spécifiquement la logique de la section « Produits cibles » du module. Cela inclurait :
        -   La gestion de la sélection de catégories, de fabricants, de fournisseurs (par exemple, à l'aide de listes déroulantes à sélection multiple ou d'arborescences).
        -   La gestion de la saisie des ID de produits, potentiellement avec validation.
        -   L'interaction avec les scripts d'autocomplétion pour permettre aux administrateurs de rechercher et de sélectionner des produits.
        -   La mise à jour dynamique de la liste des produits cibles sélectionnés.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `masspricepro/lib/searchTool/views/css/autocomplete.css`
    -   **Portée :** Front-office et Back-office.
    -   **Détails :** Fournit le style pour les listes déroulantes de suggestions d'autocomplétion et les champs de saisie, garantissant qu'ils sont visuellement cohérents et conviviaux.
-   `masspricepro/views/css/mpp_admin.css`
    -   **Portée :** Style du formulaire d'administration du Back-office.
    -   **Détails :** Il s'agit de la feuille de style principale pour l'interface de configuration du module dans le Back Office de PrestaShop. Elle stylise :
        -   La mise en page des onglets/sections de configuration.
        -   Les éléments de formulaire (entrées, boutons, sélecteurs, cases à cocher).
        -   Les tableaux (par exemple, pour l'historique, l'aperçu).
        -   Tous les composants d'interface utilisateur personnalisés spécifiques au module.
        -   Sélecteurs de classe CSS clés que les développeurs peuvent remplacer : `.mpp-container`, `.mpp-tab-content`, `.mpp-form-group`, `.mpp-table`, etc.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates d'administration (`views/templates/admin/`)

Ces templates sont rendus dans la méthode `getContent()` du fichier principal du module pour construire l'interface de configuration du back-office.

-   `constraints.tpl` : Rend la section pour définir des contraintes supplémentaires (par exemple, fourchette de prix, caractéristiques, attributs).
-   `cron_setup.tpl` : Affiche les instructions et la commande pour configurer la tâche cron du serveur.
-   `csv.tpl` : Rend l'interface pour la fonctionnalité d'importation CSV.
-   `csv_export_target.tpl` : Rend l'interface pour la fonctionnalité d'exportation CSV, spécifiquement pour les produits ciblés.
-   `history.tpl` : Affiche le tableau et les détails des opérations de changement de prix passées.
-   `mpp_operation_block.tpl` : Probablement un bloc réutilisable pour définir une seule opération de changement de prix (augmentation/diminution/définition).
-   `mpp_target_block.tpl` : Probablement un bloc réutilisable pour définir les critères de ciblage de produits.
-   `mpp_target_products_full.tpl` : Rend l'interface complète pour la sélection des produits cibles, y compris éventuellement les champs d'autocomplétion et les listes de produits sélectionnés.
-   `preview.tpl` : Affiche le tableau montrant les prix actuels et les nouveaux prix proposés avant l'exécution.
-   `rules.tpl` : Rend l'interface pour définir les règles de tarification conditionnelles.
-   `scheduler.tpl` : Affiche le formulaire pour planifier les changements de prix et les annulations futurs.
-   `target_products.tpl` : Un template plus concis ou alternatif pour le ciblage de produits, potentiellement utilisé dans d'autres sections.
-   `wtd.tpl` : Rend la section « Que faire », où le type principal d'ajustement de prix est sélectionné.

#### Templates de hook (`views/templates/hook/`)

-   `form.tpl` : Ce template est probablement utilisé pour rendre le formulaire de configuration principal ou une partie spécifique de celui-ci lorsque le module est accroché à un hook d'affichage générique (bien que le module utilise principalement `getContent()` pour sa configuration principale). Compte tenu de l'objectif du module, il est peu probable qu'il affiche quoi que ce soit directement sur le front office via des hooks comme `displayHeader` ou `displayFooter`, mais utilise plutôt ces hooks pour charger des actifs ou un traitement interne.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données

Le module ne crée pas de tables SQL personnalisées d'après l'inventaire fourni. Il s'appuie principalement sur les tables principales de PrestaShop :

-   `ps_product` : Pour les prix de base des produits.
-   `ps_product_shop` : Pour les prix des produits spécifiques à la boutique.
-   `ps_specific_price` : Pour les règles de prix spécifiques.
-   `ps_product_attribute`, `ps_product_attribute_shop` : Pour les prix et impacts des déclinaisons.
-   `ps_category_product`, `ps_manufacturer`, `ps_supplier` : Pour le ciblage des produits.
-   `ps_configuration` : Pour stocker les paramètres et les valeurs de configuration du module (par exemple, `MPP_LAST_OPERATION_DATE`, `MPP_CRON_TOKEN`, `MPP_SCHEDULED_TASKS`).

#### Tableau des hooks enregistrés

Le module enregistre probablement des hooks pour s'intégrer au cycle de vie de PrestaShop et afficher des actifs.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Pour charger les CSS spécifiques au module (`mpp_admin.css` si nécessaire pour une raison quelconque, bien qu'improbable pour le front-office) et le JavaScript (`autocomplete.js`, `jquery.autocomplete.js` si utilisé pour la recherche front-end). |
| `actionModuleInstall` | Lors de l'installation du module. | Pour effectuer la configuration initiale, créer des entrées de configuration et enregistrer d'autres hooks. |
| `actionModuleUninstall` | Lors de la désinstallation du module. | Pour nettoyer les entrées de configuration et désenregistrer les hooks. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration est chargé. | Pour charger les CSS spécifiques au Back-office (`mpp_admin.css`) et le JavaScript (`mpp_pro.js`, `mpp_target_products.js`, `autocomplete.js`) pour la page de configuration du module. |
| `actionScheduler` (ou hook personnalisé similaire) | Déclenché par la tâche cron du module. | Pour exécuter les changements de prix planifiés et annuler les opérations. Il s'agit d'un hook interne personnalisé ou d'une méthode appelée par le contrôleur `cron.php`. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Mass price change pro », veuillez vous référer à votre compte client sur MyPresta.eu. Vous pouvez télécharger les nouvelles versions depuis l'historique de vos commandes et accéder aux ressources de support directement via la plateforme.
