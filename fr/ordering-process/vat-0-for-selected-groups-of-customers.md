---
title: "TVA 0% pour des groupes de clients sélectionnés - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop TVA 0% pour des groupes de clients sélectionnés par MyPresta.eu."
sidebar:
  label: "TVA 0% pour des groupes de clients sélectionnés"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module VAT 0% for selected groups of customers sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/vat-0-for-selected-groups-of-customers.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/vat-0-for-selected-groups-of-customers/)
>
> ---


# TVA 0% pour des groupes de clients sélectionnés

## 1. Exigences et compatibilité
- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises pour PrestaShop lui-même et pour les vérifications de mise à jour du module.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Après l'installation, cliquer sur "Configurer" vous mènera à la page de configuration principale du module "TVA 0% pour des groupes de clients sélectionnés". Cette page est divisée en plusieurs sections.

#### Onglet Paramètres

C'est l'onglet principal où vous définissez quels groupes de clients bénéficieront d'une TVA à 0%.

**1. Groupes de clients qui auront une TVA à 0%**
- **Ce que fait ce paramètre :** C'est le paramètre le plus crucial. Il vous permet de sélectionner un ou plusieurs groupes de clients de votre boutique PrestaShop qui seront exemptés de TVA.
- **Effet de la modification de ce paramètre :**
    - *Lorsqu'un ou plusieurs groupes sont sélectionnés :* Tout client appartenant à *au moins un* des groupes sélectionnés aura tous les prix des produits, les frais de port et les totaux de commande calculés avec une TVA de 0%.
    - *Lorsqu'aucun groupe n'est sélectionné :* Le module n'appliquera aucune exonération de TVA, et tous les clients seront facturés la TVA selon les règles fiscales standard de PrestaShop.
- **Valeur recommandée :** Sélectionnez tous les groupes de clients que vous souhaitez exempter de TVA (par exemple, "Clients en gros", "Clients B2B").
- **Scénario / exemple pour le marchand :** Vous gérez une boutique B2B. Vous avez un groupe de clients appelé "Clients en gros" qui sont toutes des entreprises assujetties à la TVA. Vous sélectionneriez "Clients en gros" dans cette liste. Lorsqu'un client de ce groupe se connecte, il verra tous les prix sans TVA.

**2. Sélectionner une règle de taxe**
- **Ce que fait ce paramètre :** Cette option vous permet de spécifier une règle de taxe particulière que le module doit utiliser lors de l'application de la TVA à 0%. Bien que le module définisse le taux de taxe à 0%, PrestaShop exige souvent qu'une règle de taxe valide soit associée au calcul.
- **Effet de la modification de ce paramètre :**
    - *Lorsqu'une règle de taxe spécifique est sélectionnée :* Le module tentera d'utiliser cette règle de taxe, mais avec un taux de 0%, pour les groupes de clients exemptés. Cela peut être utile pour assurer la compatibilité avec d'autres modules ou des configurations comptables spécifiques qui s'attendent à ce qu'une règle de taxe soit toujours présente.
    - *Lorsque "Aucun" ou aucune règle spécifique n'est sélectionnée (comportement par défaut) :* Le module gérera l'application de la TVA à 0% directement, souvent en remplaçant le taux de taxe par 0% sans adhérer strictement à une règle de taxe prédéfinie, ce qui est généralement suffisant.
- **Valeur recommandée :** Laissez par défaut, sauf si vous rencontrez des problèmes de compatibilité spécifiques avec d'autres modules ou si vous avez une exigence comptable très particulière. Si vous en sélectionnez une, choisissez une règle de taxe générique à 0% si vous en avez une, ou une règle de taxe standard que le module pourra ensuite remplacer par 0%.
- **Scénario / exemple pour le marchand :** Votre comptable exige que toutes les transactions, même celles avec une TVA à 0%, soient liées à un ID de règle de taxe spécifique à des fins de reporting. Vous pourriez créer une règle de taxe "TVA 0% (Exemptée)" dans PrestaShop et la sélectionner ici.

#### Onglet Réparation des hooks
Cet onglet est destiné au dépannage avancé et à la vérification que les hooks du module sont correctement enregistrés.

- **Ce que fait ce paramètre :** Cette section fournit des outils pour réenregistrer les hooks du module au cas où ils seraient désenregistrés ou corrompus, ce qui peut parfois arriver après des changements de thème, des conflits de modules ou des problèmes de base de données.
- **Effet de la modification de ce paramètre :**
    - *Cliquer sur "Réparer les hooks" :* Cette action tentera de réenregistrer tous les hooks nécessaires que le module utilise pour fonctionner correctement. Si le module ne fonctionnait pas comme prévu (par exemple, la TVA n'était pas supprimée), cela pourrait résoudre le problème.
- **Valeur recommandée :** N'utilisez ceci que si vous suspectez que le module ne fonctionne pas correctement (par exemple, la TVA est toujours facturée aux groupes exemptés) et après avoir confirmé que vos paramètres principaux sont corrects.
- **Scénario / exemple pour le marchand :** Vous venez de mettre à jour votre thème PrestaShop, et maintenant vos clients exemptés de TVA sont soudainement facturés la TVA. Vous avez vérifié vos paramètres de groupe, et ils sont corrects. Cliquer sur "Réparer les hooks" ici pourrait résoudre le problème sous-jacent.

#### Onglet Mises à jour
Cet onglet fournit des informations sur les mises à jour du module.

- **Ce que fait ce paramètre :** Cette section vérifie les mises à jour disponibles pour le module et fournit des informations sur votre version actuelle.
- **Effet de la modification de ce paramètre :**
    - *Vérification des mises à jour :* Vous informe si une version plus récente du module est disponible, vous permettant de maintenir votre module à jour avec les dernières fonctionnalités et corrections de bugs.
- **Valeur recommandée :** Vérifiez périodiquement cet onglet pour vous assurer que vous utilisez la dernière version pour des performances et une sécurité optimales.
- **Scénario / exemple pour le marchand :** Vous voulez vous assurer que votre boutique utilise toujours le logiciel le plus stable et le plus sécurisé. Vous visitez cet onglet une fois par mois pour voir s'il y a de nouvelles mises à jour pour vos modules MyPresta.eu.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
|---|---|---|---|
| Page de configuration du module | **Groupes de clients qui auront une TVA à 0%** | Sélectionnez les groupes pertinents (par exemple, "Clients en gros") | Définit quels groupes de clients auront une TVA de 0% appliquée à tous les prix et totaux. |
| Page de configuration du module | **Sélectionner une règle de taxe** | Laissez par défaut (ou sélectionnez une règle de taxe à 0% si nécessaire pour la comptabilité) | Associe le calcul de la TVA à 0% à une règle de taxe spécifique pour la compatibilité ou le reporting. |
| Onglet Réparation des hooks | **Bouton Réparer les hooks** | N'utiliser que pour le dépannage | Réenregistre les hooks du module pour résoudre les problèmes de fonctionnalité (par exemple, la TVA n'est pas supprimée). |
| Onglet Mises à jour | **Vérifier les mises à jour** | Vérifier périodiquement | Informe des mises à jour disponibles du module pour les nouvelles fonctionnalités et les corrections de bugs. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : La TVA est toujours facturée même si j'ai sélectionné le groupe de clients.**
R1 :
*   **Vérifier l'affectation du groupe :** Assurez-vous que le client avec lequel vous testez est bien affecté à l'un des groupes exemptés de TVA sélectionnés. Connectez-vous en tant que client, accédez aux détails de son compte, ou vérifiez dans le Back Office sous `Clients > Clients`.
*   **Configuration du module :** Vérifiez à nouveau que les groupes corrects sont sélectionnés dans la page de configuration du module (`Modules > Gestionnaire de modules > Configurer` pour "TVA 0% pour des groupes de clients sélectionnés").
*   **Cache :** Videz le cache de votre PrestaShop (sous `Paramètres avancés > Performances`) et le cache de votre navigateur. Parfois, d'anciennes données peuvent être affichées.
*   **Réparation des hooks :** Allez dans l'onglet "Réparation des hooks" dans la configuration du module et cliquez sur le bouton "Réparer les hooks". Cela peut résoudre les problèmes où les points d'intégration du module avec PrestaShop auraient pu être désenregistrés.

**Q2 : Ce module affectera-t-il mes règles fiscales existantes pour les clients non exemptés ?**
R2 : Non, ce module est conçu pour *uniquement* appliquer une TVA de 0% aux clients appartenant aux groupes spécifiques que vous sélectionnez. Pour tous les autres clients, vos règles et configurations fiscales standard de PrestaShop s'appliqueront comme d'habitude.

**Q3 : Ce module fonctionne-t-il également pour les frais de port ?**
R3 : Oui, le module est conçu pour appliquer une TVA de 0% à tous les aspects de la commande, y compris les prix des produits, les frais de port et tout autre élément taxable, ce qui se traduit par une valeur totale de commande avec une TVA de 0% pour les groupes de clients sélectionnés.

**Q4 : J'ai un thème personnalisé. Ce module fonctionnera-t-il avec ?**
R4 : Oui, ce module fonctionne en modifiant la logique de calcul de la TVA de PrestaShop via des hooks, plutôt qu'en altérant directement les templates du front-office. Par conséquent, il devrait être compatible avec la plupart des thèmes personnalisés sans problème. Si vous rencontrez des problèmes d'affichage (par exemple, les prix ne se mettent pas à jour), il s'agit probablement d'un problème de cache ou d'un conflit avec un autre module qui modifie également fortement les calculs de TVA.

**Q5 : Comment traduire le texte du module dans d'autres langues ?**
R5 : Si le module introduit de nouvelles chaînes de texte (bien que ce module fonctionne principalement en arrière-plan), vous pouvez les traduire via l'interface de traduction de PrestaShop :
1.  Allez dans `International > Traductions`.
2.  Sélectionnez "Traductions des modules installés".
3.  Choisissez votre thème, la langue, puis sélectionnez "TVA 0% pour des groupes de clients sélectionnés" dans la liste des modules.
4.  Vous pouvez ensuite modifier toutes les chaînes traduisibles.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture
Le module "TVA 0% pour des groupes de clients sélectionnés" fonctionne en exploitant le système de hooks de PrestaShop pour intercepter et modifier les calculs de TVA à différentes étapes du processus de commande. Il utilise principalement les hooks `actionTaxManager` et `actionProductPriceCalculation` pour ajuster dynamiquement le taux de TVA à 0% pour les clients appartenant à des groupes spécifiés. Il inclut également une classe `TaxManager` personnalisée pour gérer la logique de remplacement de la TVA. Le module suit une structure de module PrestaShop standard, avec un fichier de module principal, une classe dédiée à la gestion de la TVA et des templates Smarty pour sa configuration Back Office.

### 4.2 Contrôleurs (`controllers/`)
Ce module n'utilise pas de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la configuration est gérée via la méthode `getContent()` dans le fichier de module principal.

### 4.3 Classes et modèles principaux (`classes/`)

-   **`groupvat/classes/GroupvatTaxManager.php`**
    *   **Nom de la classe :** `GroupvatTaxManager`
    *   **Classe parente :** `TaxManager` (classe `TaxManager` principale de PrestaShop)
    *   **Responsabilité :** Cette classe est le cœur de la fonctionnalité du module. Elle étend la classe `TaxManager` par défaut de PrestaShop pour remplacer son comportement. Sa méthode principale, `getTaxCalculator()`, est cruciale. Lorsqu'un client est identifié comme appartenant à un groupe exempté de TVA, cette classe garantit que le `TaxCalculator` renvoie un taux de TVA de 0%, supprimant ainsi efficacement la TVA des prix. Elle contient également une logique pour vérifier si le client actuel fait partie de l'un des groupes exemptés configurés.
    *   **Méthodes clés :**
        *   `getTaxCalculator(array $params)` : Remplace le calculateur de taxe par défaut pour renvoyer un taux de taxe de 0% si le client fait partie d'un groupe exempté.
        *   `isCustomerInGroup(int $id_customer)` : Méthode d'aide pour déterminer si un ID client donné appartient à l'un des groupes exemptés de TVA configurés.

-   **`groupvat/classes/index.php`**
    *   **Responsabilité :** Fichier `index.php` vide standard pour empêcher l'affichage du contenu du répertoire.

### 4.4 Assets JavaScript (`views/js/`)
Ce module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)
Ce module n'inclut aucun fichier CSS personnalisé. Le style de la configuration du Back Office est géré par le thème d'administration par défaut de PrestaShop.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **`groupvat/views/templates/admin/configure.tpl`**
    *   **Portée :** Configuration de l'administration Back-office.
    *   **Objectif :** C'est le template principal de la page de configuration du module, rendu par `getContent()` dans `groupvat.php`. Il inclut d'autres templates pour des sections spécifiques comme la sélection des groupes de clients et la réparation des hooks. Il enveloppe généralement l'ensemble du formulaire de configuration.

-   **`groupvat/views/templates/admin/customerGroups.tpl`**
    *   **Portée :** Configuration de l'administration Back-office.
    *   **Objectif :** Ce template rend la section où le marchand sélectionne les groupes de clients qui auront une TVA à 0%. Il affiche une liste des groupes de clients disponibles avec des cases à cocher.
    *   **Variables :** Utilise probablement `$groups` (tableau des groupes de clients), `$selected_groups` (tableau des ID des groupes actuellement sélectionnés), `$tax_rules` (tableau des règles de taxe disponibles), `$selected_tax_rule` (ID de la règle de taxe actuellement sélectionnée).

-   **`groupvat/views/templates/admin/hooksRepair.tpl`**
    *   **Portée :** Configuration de l'administration Back-office.
    *   **Objectif :** Ce template rend la section "Réparation des hooks", fournissant un bouton pour réenregistrer les hooks du module.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données :**
    *   Ce module ne crée pas de tables de base de données personnalisées.
    *   Il stocke ses paramètres de configuration dans la table `ps_configuration` de PrestaShop.
        *   `groupvat_groups` : Stocke une liste d'ID de groupes de clients séparés par des virgules, sélectionnés pour l'exonération de TVA.
        *   `groupvat_tax` : Stocke l'ID de la règle de taxe sélectionnée (le cas échéant).
        *   `mypresta_updates` : Stocke les informations relatives aux mises à jour du module.

-   **Table des hooks enregistrés :**

| Nom du hook | Moment d'exécution | Objectif technique |
|---|---|---|
| `actionDispatcher` | Avant qu'un contrôleur ne soit dispatché. | Utilisé pour potentiellement remplacer ou modifier le comportement de dispatch, bien que souvent utilisé pour la configuration générale. |
| `ActionDispatcher` | (Alias de `actionDispatcher`) | Identique à ci-dessus. |
| `actionCartGetPackageShippingCost` | Lors du calcul des frais de port pour un colis dans le panier. | Crucial pour garantir que les frais de port sont également calculés avec une TVA de 0% pour les groupes exemptés. |
| `displayTaxManager` | (Obsolète/moins courant) | Historiquement utilisé pour afficher des informations relatives aux taxes. |
| `ActionGetProductPropertiesAfter` | Après la récupération des propriétés du produit. | Permet la modification des données du produit, y compris le prix et la taxe, avant l'affichage. |
| `taxManager` | (Obsolète/moins courant) | Historiquement utilisé pour la gestion des taxes. |
| `ActionAuthentication` | Après l'authentification d'un client (connexion). | Peut être utilisé pour définir des variables de session ou effectuer des actions basées sur le groupe de clients après la connexion. |
| `ActionTaxManager` | Lors de l'instanciation de la classe `TaxManager` ou de l'appel de ses méthodes. | **Hook principal pour ce module.** Permet au module d'injecter sa classe `GroupvatTaxManager` personnalisée ou de modifier la logique de calcul de la taxe. |
| `ActionPresentCart` | Avant que le panier ne soit présenté à l'utilisateur. | Permet la modification des données du panier, y compris les prix et les totaux, avant le rendu. |
| `ActionProductPriceCalculation` | Pendant le processus de calcul du prix du produit. | **Hook principal pour ce module.** Permet au module de modifier le taux de taxe appliqué aux prix des produits. |
| `actionGetProductPropertiesAfter` | (Alias de `ActionGetProductPropertiesAfter`) | Identique à ci-dessus. |
| `ActionFilterDeliveryOptionList` | Avant l'affichage de la liste des options de livraison. | Permet la modification des options de livraison, affectant potentiellement leurs prix (et donc la taxe). |

## 5. Support officiel et mises à jour
Pour le support officiel, les mises à jour et les dernières versions du module "TVA 0% pour des groupes de clients sélectionnés", veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir.
