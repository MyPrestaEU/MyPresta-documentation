---
title: "Lien pour assigner un client à un groupe - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Lien pour assigner un client à un groupe' par MyPresta.eu."
sidebar:
  label: "Lien pour assigner un client à un groupe"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Link to assign customer to group sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/link-to-assign-customer-to-group.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/link-to-assign-customer-to-group/)
>
> ---


# Lien pour assigner un client à un groupe

## 1. Exigences et compatibilité
-   **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilité PHP** : PHP 5.6 - 8.5
-   **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration spéciale de serveur n'est généralement nécessaire.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Gestionnaire de modules > Configurer Lien pour assigner un client à un groupe)

C'est l'écran de configuration principal et unique du module. Ici, vous pouvez définir comment le module se comporte lors de l'assignation de clients à des groupes.

#### **Changer le groupe par défaut**
-   **Ce que fait ce paramètre :** Ce paramètre détermine si le module doit également assigner le client au groupe de clients "Par défaut" en plus du groupe spécifié dans l'URL.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'activé (OUI) :* Si un client clique sur un lien pour être assigné au "Groupe X", il sera également assigné au groupe "Par défaut". Cela signifie qu'il fera partie à la fois du "Groupe X" et du "Par défaut". Cela peut être utile si votre groupe "Par défaut" a certaines permissions de base ou des réductions que vous voulez toujours que les clients aient, quels que soient les autres groupes qu'ils rejoignent.
    -   *Lorsqu'désactivé (NON) :* Le client ne sera assigné qu'au groupe spécifié dans l'URL (par exemple, "Groupe X"). Il ne sera pas automatiquement ajouté au groupe "Par défaut" à moins qu'il n'en fasse déjà partie ou qu'un autre mécanisme ne l'y ajoute.
-   **Valeur recommandée :** **NON**. Dans la plupart des cas, vous souhaitez assigner les clients à un groupe *spécifique* sans nécessairement les ajouter au groupe "Par défaut", surtout si votre groupe "Par défaut" n'a pas de signification particulière ou si vous souhaitez gérer les groupes plus précisément. Activez ceci uniquement si vous avez une raison spécifique d'inclure toujours le groupe "Par défaut".
-   **Scénario / exemple de marchand :** Vous avez un groupe "VIP" avec des réductions spéciales. Si vous activez ceci, un client cliquant sur un lien VIP sera à la fois dans "VIP" et "Par défaut". Si "Par défaut" a une réduction de 5% sur toute la boutique et "VIP" a une réduction de 15% sur des produits spécifiques, le client bénéficiera des deux là où cela est applicable. Si désactivé, il n'obtiendrait que les avantages "VIP".

#### **Désassigner le client des autres groupes**
-   **Ce que fait ce paramètre :** Ce paramètre contrôle si le module doit retirer le client de *tous les autres* groupes de clients lorsqu'il est assigné à un nouveau groupe via le lien spécial.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'activé (OUI) :* Si un client est actuellement dans le "Groupe A" et le "Groupe B", et clique ensuite sur un lien pour être assigné au "Groupe X", il sera retiré du "Groupe A" et du "Groupe B", et ne restera que dans le "Groupe X" (et potentiellement "Par défaut" si le paramètre précédent est activé). Cela garantit que le client est *uniquement* dans le groupe cible.
    -   *Lorsqu'désactivé (NON) :* Le client sera *ajouté* au nouveau groupe ("Groupe X") mais *restera* dans tous les autres groupes dont il faisait déjà partie (par exemple, "Groupe A", "Groupe B"). Cela permet aux clients d'être membres de plusieurs groupes simultanément.
-   **Valeur recommandée :** **NON**. Permettre aux clients d'être dans plusieurs groupes offre plus de flexibilité pour une segmentation complexe. N'activez ceci que si vous avez besoin de groupes stricts et mutuellement exclusifs (par exemple, un client ne peut être que "Détaillant" OU "Grossiste", jamais les deux).
-   **Scénario / exemple de marchand :**
    -   *Activé (OUI) :* Vous avez les groupes "Client standard" et "Client grossiste". Un client clique sur un lien pour devenir "Grossiste". Si activé, il est retiré de "Client standard" et ne reste que "Grossiste". C'est idéal pour des types de clients clairs et distincts.
    -   *Désactivé (NON) :* Vous avez les groupes "Abonné à la newsletter" et "Membre du programme de fidélité". Un client clique sur un lien pour rejoindre le "Programme de fidélité". Si désactivé, il reste "Abonné à la newsletter" *et* devient "Membre du programme de fidélité". C'est idéal pour des avantages additifs.

#### **Comment créer le lien spécial**
Le module fonctionne en ajoutant un paramètre spécial à n'importe quelle URL de votre boutique. Le format du paramètre est : `?asg={group_id}`

1.  **Trouvez l'ID du groupe :**
    -   Allez dans **Clients > Groupes** dans votre Back Office PrestaShop.
    -   Notez le numéro d'ID à côté du groupe auquel vous souhaitez assigner des clients. Par exemple, si "Grossiste" a un ID de `3`, alors `3` est votre `group_id`.
2.  **Construisez le lien :**
    -   Prenez n'importe quelle URL de votre boutique (par exemple, `https://votreboutique.com/`)
    -   Ajoutez-y `?asg={group_id}`.
    -   **Exemple :** Pour assigner un client au groupe ID `3` (par exemple, "Grossiste") et le rediriger vers votre page d'accueil : `https://votreboutique.com/?asg=3`
    -   **Exemple :** Pour assigner un client au groupe ID `5` (par exemple, "VIP") et le rediriger vers une page produit spécifique : `https://votreboutique.com/fr/produit/123-produit-genial?asg=5`

:::warning
Le paramètre `asg` doit être le *premier* paramètre s'il n'y a pas d'autres paramètres dans l'URL (c'est-à-dire, utilisez `?`). Si l'URL a déjà des paramètres (par exemple, `https://votreboutique.com/categorie/1-vetements?id_category=1`), vous devez utiliser `&` pour ajouter le paramètre `asg` : `https://votreboutique.com/categorie/1-vetements?id_category=1&asg=3`.
:::

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Configuration du module | Changer le groupe par défaut | NON | Si OUI, le client est également ajouté au groupe 'Par défaut'. Si NON, uniquement au groupe spécifié. |
| Configuration du module | Désassigner le client des autres groupes | NON | Si OUI, le client est retiré de tous les autres groupes. Si NON, le client reste dans les groupes existants et est ajouté au nouveau. |

## 3. Dépannage pour le marchand et questions fréquemment posées (FAQ)

**Q : Le client a cliqué sur le lien mais n'a pas été assigné au groupe. Qu'est-ce qui ne va pas ?**
R :
1.  **Client non connecté :** Le module ne fonctionne que pour les clients *connectés*. S'ils n'étaient pas connectés, ils seront simplement redirigés vers la page sans assignation de groupe.
2.  **ID de groupe incorrect :** Vérifiez l'`group_id` dans votre URL par rapport à l'ID réel dans **Clients > Groupes**.
3.  **Paramètre d'URL incorrect :** Assurez-vous d'utiliser `?asg=` pour le premier paramètre et `&asg=` pour les paramètres suivants.
4.  **Module non activé :** Vérifiez que le module est installé et activé dans **Modules > Gestionnaire de modules**.
5.  **Cache :** Videz le cache de votre PrestaShop (Paramètres avancés > Performances > Vider le cache) et le cache de votre navigateur.

**Q : Puis-je assigner un client à plusieurs groupes avec un seul lien ?**
R : Non, le paramètre `asg` ne prend en charge l'assignation qu'à un seul groupe à la fois. Cependant, si "Désassigner le client des autres groupes" est défini sur NON, le client sera *ajouté* au nouveau groupe tout en conservant son appartenance à ses groupes existants.

**Q : Ce module affecte-t-il le référencement (SEO) ?**
R : Non, ce module n'a aucun impact direct sur le référencement de votre boutique. Le paramètre `asg` est un paramètre dynamique que les moteurs de recherche ignorent généralement.

**Q : Que se passe-t-il si un client clique plusieurs fois sur le lien ?**
R : Si le client est déjà dans le groupe cible, rien ne change. S'il ne l'est pas, il y sera assigné. Le module est conçu pour gérer cela avec élégance et sans erreurs.

**Q : Je souhaite retirer un client d'un groupe à l'aide d'un lien. Est-ce possible ?**
R : Non, ce module est conçu uniquement pour *assigner* des clients à des groupes. Il ne fournit pas de fonctionnalité pour retirer des clients de groupes via une URL. Vous devrez le faire manuellement dans le Back Office ou utiliser un autre module/développement personnalisé.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture
Le module "Lien pour assigner un client à un groupe" (`assigntogroup`) est un module PrestaShop léger principalement conçu pour intercepter les requêtes du front-office et modifier les assignations de groupes de clients en fonction d'un paramètre d'URL. Il utilise le système de hooks de PrestaShop (`displayHeader`) pour exécuter sa logique tôt dans le processus de chargement de la page, garantissant que les changements de groupe sont appliqués avant que le contenu de la page ne soit rendu. Il n'introduit pas de contrôleurs, de modèles ou de JavaScript/CSS complexes personnalisés. Sa fonctionnalité principale réside dans la classe principale du module.

### 4.2 Contrôleurs (`controllers/`)
-   **Contrôleurs Front-Office** : Aucun. La logique du module est exécutée via un hook, et non un contrôleur frontal dédié.
-   **Contrôleurs d'administration Back-Office** : Aucun. Toute la configuration est gérée dans la méthode `getContent()` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)
-   Aucune classe ou `ObjectModel` personnalisé n'est défini dans le répertoire `classes/`. Le module interagit directement avec les `ObjectModel`s `Customer` et `Group` de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)
-   Aucun fichier JavaScript n'est inclus avec ce module.

### 4.5 Feuilles de style CSS (`views/css/`)
-   Aucun fichier CSS n'est inclus avec ce module.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :
    *   `assigntogroup/views/templates/hook/form.tpl`
        *   **Objectif** : Ce template est utilisé pour rendre le formulaire de configuration du module dans le Back Office de PrestaShop. Il est rendu par la méthode `getContent()` de la classe principale du module.
        *   **Contenu** : Contient la structure HTML pour les deux interrupteurs de configuration (`asg_unassign`, `asg_default`) et le bouton de soumission du formulaire. Il utilise les éléments de formulaire d'aide standard de PrestaShop.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :
    *   Le module ne crée aucune table SQL personnalisée.
    *   Il stocke ses paramètres de configuration dans la table `ps_configuration` :
        *   `PS_ASG_UNASSIGN` : Stocke la valeur du paramètre "Désassigner le client des autres groupes" (0 ou 1).
        *   `PS_ASG_DEFAULT` : Stocke la valeur du paramètre "Changer le groupe par défaut" (0 ou 1).

-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | Exécuté tôt lors du chargement de la page du front-office, dans la section `<head>`. | C'est le hook principal utilisé par le module. Il vérifie le paramètre d'URL `asg`, vérifie si un client est connecté, puis exécute la logique d'assignation de groupe en fonction des paramètres de configuration du module (`PS_ASG_UNASSIGN`, `PS_ASG_DEFAULT`). |

### 4.8 Fichier PHP principal du module (`assigntogroup/assigntogroup.php`)

C'est le fichier central du module, contenant son installation, sa désinstallation, sa configuration et sa logique principale.

-   **Nom de la classe** : `Assigntogroup`
-   **Classe parente** : `Module`
-   **Méthodes clés** :
    *   `__construct()` : Initialise les métadonnées du module (nom, onglet, version, auteur, etc.).
    *   `install()` :
        *   Enregistre le hook `displayHeader`.
        *   Définit les valeurs de configuration par défaut pour `PS_ASG_UNASSIGN` (0) et `PS_ASG_DEFAULT` (0) dans `ps_configuration`.
        *   Retourne `true` en cas de succès.
    *   `uninstall()` :
        *   Désenregistre le hook `displayHeader`.
        *   Supprime les valeurs de configuration `PS_ASG_UNASSIGN` et `PS_ASG_DEFAULT` de `ps_configuration`.
        *   Retourne `true` en cas de succès.
    *   `getContent()` :
        *   Gère la soumission du formulaire de configuration du Back Office du module.
        *   Met à jour `PS_ASG_UNASSIGN` et `PS_ASG_DEFAULT` dans `ps_configuration` en fonction de l'entrée utilisateur.
        *   Rend le formulaire de configuration à l'aide de `display(__FILE__, 'views/templates/hook/form.tpl')`.
    *   `hookDisplayHeader()` :
        *   **Logique principale** : Cette méthode est exécutée à chaque chargement de page du front-office.
        *   Vérifie si le paramètre GET `asg` est présent et est un entier valide représentant un `id_group`.
        *   Vérifie si un client est connecté (`$this->context->customer->isLogged()`).
        *   Récupère l'objet `Group` cible.
        *   Récupère l'objet `Customer` actuel.
        *   En fonction de la configuration `PS_ASG_UNASSIGN` et `PS_ASG_DEFAULT` :
            *   Gère les associations de groupes du client (`$customer->updateGroup()`).
            *   Ajoute le client au groupe spécifié.
            *   Supprime éventuellement le client des autres groupes.
            *   Ajoute éventuellement le client au groupe par défaut.
        *   Redirige l'utilisateur vers l'URL actuelle sans le paramètre `asg` pour éviter un nouveau traitement lors de l'actualisation.

## 5. Support officiel et mises à jour
Pour les dernières mises à jour, corrections de bugs et support officiel du module "Lien pour assigner un client à un groupe", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité du module.
