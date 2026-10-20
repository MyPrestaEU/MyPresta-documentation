---
title: "Zopim Chat Free - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Zopim Chat Free par MyPresta.eu."
sidebar:
  label: "Zopim Chat Free - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Zopim Chat Free sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/zopim-chat-free.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/zopim-chat-free/)
>
> ---


# Zopim Chat Free

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et toute intégration d'API externe, y compris Zendesk Chat.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Zopim Chat Free)

Ceci est l'écran de configuration principal et unique du module Zopim Chat Free. Ici, vous saisirez votre clé de compte Zendesk Chat (Zopim) et déciderez où le script du widget de chat doit être chargé sur votre boutique.

#### **Clé de compte Zopim**

-   **Ce que fait ce paramètre :** C'est le paramètre le plus crucial. C'est là que vous entrez l'identifiant unique fourni par Zendesk Chat (Zopim) pour votre widget de chat en direct. Cette clé indique au module quel widget de chat charger sur votre site web. Vous pouvez trouver cette clé dans votre tableau de bord Zendesk Chat (généralement sous Paramètres > Widget > Code d'intégration).
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'une clé valide est saisie :* Le widget de chat Zopim associé à votre compte Zendesk Chat apparaîtra sur le front-office de votre boutique, permettant aux clients d'initier des chats.
    *   *Lorsqu'il est laissé vide ou qu'une clé invalide est saisie :* Le widget de chat Zopim n'apparaîtra pas sur votre boutique, et la fonctionnalité de chat en direct sera indisponible.
-   **Valeur recommandée :** Votre clé de compte Zendesk Chat (Zopim) unique.
-   **Scénario / exemple marchand :** Après vous être inscrit à Zendesk Chat, vous recevrez un extrait de code. Dans ce code, vous trouverez une chaîne spécifique (par exemple, `zopim.setAndDefer('account', 'VOTRE_CLE_DE_COMPTE');`). Copiez `VOTRE_CLE_DE_COMPTE` et collez-la ici.

#### **Charger Zopim Chat dans le Hook**

-   **Ce que fait ce paramètre :** Cette option détermine où, dans le code de votre boutique PrestaShop, le script de chat Zopim sera injecté. Bien que le widget de chat lui-même flotte généralement sur l'écran, le placement du script peut parfois affecter la vitesse de chargement ou la compatibilité avec des thèmes spécifiques.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'il est défini sur `displayHeader` (En-tête) :* Le script de chat se chargera très tôt, généralement avant la majeure partie du contenu de votre page. Cela peut faire apparaître le widget de chat rapidement.
    *   *Lorsqu'il est défini sur `displayRightColumn` (Colonne de droite) :* Le script se chargera avec le contenu de la colonne de droite. C'est moins courant pour les widgets de chat et pourrait ne pas être idéal si votre thème n'affiche pas toujours une colonne de droite.
    *   *Lorsqu'il est défini sur `displayLeftColumn` (Colonne de gauche) :* Similaire à la colonne de droite, le script se charge avec le contenu de la colonne de gauche.
    *   *Lorsqu'il est défini sur `displayProductButtons` (Boutons de page produit) :* Le script se chargera spécifiquement sur les pages produit, près de la zone du bouton "Ajouter au panier". Cela peut être utile si vous souhaitez principalement un support de chat sur les pages produit.
    *   *Lorsqu'il est défini sur `displayFooter` (Pied de page) :* Le script se chargera à la toute fin du contenu de votre page. Cela peut améliorer la vitesse de chargement initiale de la page perçue par l'utilisateur, car le contenu principal se charge en premier, et le widget de chat se charge ensuite.
-   **Valeur recommandée :** `displayHeader` ou `displayFooter`. Pour la plupart des boutiques, `displayHeader` garantit que le chat se charge rapidement. Si vous rencontrez des conflits ou souhaitez prioriser le chargement du contenu, `displayFooter` est une bonne alternative.
-   **Scénario / exemple marchand :** Si vos clients posent fréquemment des questions *avant* même de commencer à parcourir les produits, le chargement du chat dans le `displayHeader` garantit qu'il est disponible immédiatement. Si vous remarquez que votre page se charge lentement et que vous soupçonnez le script de chat, passer à `displayFooter` pourrait aider, car le chat se chargera après le contenu principal de la page.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Clé de compte Zopim | Votre clé Zendesk Chat unique | Connecte votre boutique à votre compte Zendesk Chat. Essentiel pour que le widget apparaisse. |
| Page de configuration du module | Charger Zopim Chat dans le Hook | `displayHeader` ou `displayFooter` | Détermine où le script de chat est injecté (En-tête, Colonnes, Produit, Pied de page). Affecte l'ordre de chargement et la compatibilité potentielle avec le thème. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Le widget de chat Zopim n'apparaît pas sur ma boutique. Que dois-je faire ?**
R1 :

1.  **Vérifiez votre clé de compte Zopim :** Allez sur la page de configuration du module et assurez-vous que votre clé de compte Zopim est correctement saisie. Même une seule faute de frappe l'empêchera de se charger.
2.  **Vérifiez le statut de Zendesk Chat :** Connectez-vous à votre tableau de bord Zendesk Chat. Votre widget est-il actif ? Vos agents sont-ils en ligne ?
3.  **Videz le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** dans le back office de votre PrestaShop et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions antérieures). Parfois, d'anciens fichiers mis en cache empêchent les nouvelles modifications du module d'apparaître.
4.  **Vérifiez les conflits de thème :** Passez temporairement au thème PrestaShop par défaut (par exemple, Classic) et voyez si le widget apparaît. Si c'est le cas, votre thème personnalisé pourrait être à l'origine d'un conflit. Contactez le développeur de votre thème ou un webmaster.
5.  **Inspectez la console du navigateur :** Ouvrez les outils de développement de votre navigateur (F12) et vérifiez l'onglet "Console" pour toute erreur JavaScript. Cela peut fournir des indices si le script ne parvient pas à se charger.

**Q2 : Le widget de chat se charge, mais il a l'air étrange ou est mal positionné.**
R2 : Le module injecte le script Zopim, mais le style visuel et le positionnement exact du widget sont largement contrôlés par les paramètres de votre compte Zendesk Chat et le CSS de votre boutique.

1.  **Tableau de bord Zendesk Chat :** Connectez-vous à votre tableau de bord Zendesk Chat et examinez les paramètres d'apparence de votre widget (par exemple, position, couleurs, taille).
2.  **CSS du thème :** Le CSS de votre thème personnalisé pourrait remplacer certains styles Zopim par défaut. Un webmaster peut inspecter l'élément à l'aide des outils de développement du navigateur et identifier les règles CSS conflictuelles.

**Q3 : Puis-je traduire le texte du widget de chat dans différentes langues ?**
R3 : Le module Zopim Chat Free lui-même ne gère pas les traductions pour l'interface du widget. Cette fonctionnalité est gérée directement dans les paramètres de votre compte Zendesk Chat. Zendesk Chat prend en charge plusieurs langues, et vous pouvez configurer le widget pour qu'il s'affiche dans la langue préférée du client en fonction des paramètres de son navigateur ou de votre configuration Zendesk Chat.

**Q4 : Ce module va-t-il ralentir mon site web ?**
R4 : Le module Zopim Chat Free n'injecte que le script Zendesk Chat nécessaire. L'impact sur les performances dépend principalement du service Zendesk Chat lui-même et de votre connexion Internet. Vous pouvez essayer de définir l'option "Charger Zopim Chat dans le Hook" sur `displayFooter` pour vous assurer que le contenu principal de votre page se charge avant le script de chat, ce qui peut améliorer la vitesse de chargement perçue de la page.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique pour les développeurs et les webmasters travaillant avec le module Zopim Chat Free.

### 4.1 Vue d'ensemble de l'architecture

Le module `ZopimFree` est un module PrestaShop simple conçu pour intégrer le widget Zendesk Chat (anciennement Zopim). Il fonctionne principalement en injectant le script d'intégration Zendesk Chat dans le front-office de la boutique PrestaShop. Le module suit une structure de module PrestaShop standard, utilisant la classe `Module` pour l'installation, la désinstallation et la gestion de la configuration via `getContent()`. Il enregistre un seul hook (`displayHeader` par défaut, mais configurable) pour afficher le JavaScript nécessaire.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Aucun. Le module injecte directement le contenu dans les hooks.
-   **Contrôleurs Admin Back-Office** : Aucun. Toute la configuration est gérée dans la méthode `getContent()` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)

-   Aucune classe personnalisée ou définition `ObjectModel` n'est présente dans ce module. Toute la logique réside dans le fichier `zopimfree.php` principal.

### 4.4 Actifs JavaScript (`views/js/`)

-   Aucun fichier JavaScript personnalisé n'est inclus dans ce module. Le module génère le script d'intégration Zendesk Chat directement dans le template, qui charge ensuite le JS nécessaire depuis le CDN de Zendesk.

### 4.5 Feuilles de style CSS (`views/css/`)

-   Aucun fichier CSS personnalisé n'est inclus dans ce module. Le style du widget de chat est géré par le service Zendesk Chat lui-même, avec des remplacements potentiels du thème PrestaShop actif.

### 4.6 Structure du template Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :
    -   `zopimfree/header-new-widget.tpl`
        -   **Hook :** Ce template est conçu pour être rendu dans un hook PrestaShop, spécifiquement celui choisi dans la configuration du module (par exemple, `displayHeader`, `displayFooter`).
        -   **Objectif :** Il contient la balise `<script>` responsable de l'intégration du widget Zendesk Chat. Il insère dynamiquement la `ZOPIMFREE_ACCOUNT_KEY` de la configuration du module dans le script d'initialisation de Zendesk Chat.
        -   **Sortie :** Affiche le code d'intégration standard de Zendesk Chat, qui charge ensuite le widget de chat depuis les serveurs de Zendesk.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :

    -   Le module ne crée aucune table SQL personnalisée.
    -   Il stocke ses paramètres de configuration dans la table `ps_configuration` :
        -   `ZOPIMFREE_ACCOUNT_KEY` : Stocke la clé de compte Zendesk Chat.
        -   `ZOPIMFREE_HOOK` : Stocke le nom du hook où le script doit être injecté (par exemple, `displayHeader`, `displayFooter`).
-   **Table des hooks enregistrés** :

| Nom du Hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Exécuté dans la section `<head>` de chaque page. | Hook par défaut pour injecter le script Zendesk Chat tôt dans le chargement de la page. |
| `displayRightColumn` | Exécuté dans la colonne de droite des pages où il est actif. | Hook alternatif pour l'injection de script, moins courant pour les widgets de chat. |
| `displayLeftColumn` | Exécuté dans la colonne de gauche des pages où il est actif. | Hook alternatif pour l'injection de script, moins courant pour les widgets de chat. |
| `displayProductButtons` | Exécuté sur les pages produits, généralement près du bouton "Ajouter au panier". | Hook spécifique pour injecter le script de chat uniquement sur les pages produits. |
| `displayFooter` | Exécuté juste avant la balise de fermeture `</body>`. | Hook alternatif pour injecter le script Zendesk Chat plus tard dans le chargement de la page, améliorant potentiellement la vitesse de chargement initiale perçue. |

Le module enregistre ces hooks dynamiquement en fonction de la valeur de configuration `ZOPIMFREE_HOOK`. La méthode `install()` enregistre tous les hooks potentiels, et `uninstall()` les désenregistre. La méthode `hook{NomDuHook}` vérifie ensuite la configuration pour décider si elle doit rendre le template.

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, les corrections de bugs et le support développeur pour le module Zopim Chat Free, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Assurez-vous de télécharger la dernière version compatible avec votre installation PrestaShop.
