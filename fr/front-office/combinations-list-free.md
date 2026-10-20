---
title: "Combinations List Free - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Combinations List Free par MyPresta.eu."
sidebar:
  label: "Combinations List Free - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Combinations List Free sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/combinations-list-free.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/combinations-list-free/)
>
> ---


# Combinations List Free

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour une installation PrestaShop, mais ce module n'a pas d'exigences exotiques spécifiques au-delà d'un environnement PrestaShop standard.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Combinations List Free » dans votre Gestionnaire de modules. Cela vous mènera à l'écran de configuration principal.

#### Paramètres généraux

- **Ce que fait ce paramètre :** Cette section contrôle le comportement général et l'apparence de la liste des combinaisons sur vos pages produits.

  - **Afficher la liste des combinaisons sur la page produit :**

    - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité du module.
    - **Effet de la modification de ce paramètre :**
      - *Lorsqu'il est activé (OUI) :* Le module tentera d'afficher la liste des combinaisons sur les pages produits selon vos autres paramètres.
      - *Lorsqu'il est désactivé (NON) :* Le module sera inactif et vos pages produits reviendront aux sélecteurs de combinaisons par défaut de PrestaShop (menus déroulants).
    - **Valeur recommandée :** OUI (pour utiliser le module).
    - **Scénario/exemple de marchand :** Si vous testez le module ou souhaitez le désactiver temporairement sans le désinstaller, définissez-le sur NON.
  - **Hook pour afficher la liste des combinaisons :**

    - **Ce que fait ce paramètre :** Détermine où la liste des combinaisons apparaîtra sur la page produit. C'est crucial pour intégrer visuellement la liste à votre thème.
    - **Effet de la modification de ce paramètre :**
      - *Lorsqu'il est défini sur `displayProductButtons` (ou un hook similaire lié au produit) :* La liste apparaîtra généralement près du bouton « Ajouter au panier » ou du prix du produit, souvent sous les détails principaux du produit.
      - *Lorsqu'il est défini sur `displayProductExtraContent` (ou un hook similaire lié aux onglets) :* La liste apparaîtra dans un nouvel onglet produit ou un onglet existant, gardant la zone de description principale du produit plus propre.
      - *Lorsqu'il est défini sur `displayFooterProduct` (ou un hook de pied de page similaire) :* La liste apparaîtra tout en bas de la page produit.
    - **Valeur recommandée :** Expérimentez avec différents hooks pour trouver la meilleure intégration visuelle avec votre thème spécifique. `displayProductButtons` ou `displayProductExtraContent` sont des choix courants.
    - **Scénario/exemple de marchand :** Si votre page produit est déjà longue, placer la liste dans un onglet `displayProductExtraContent` peut rendre la page moins encombrée. Si vous voulez que la liste soit immédiatement visible, un hook comme `displayProductButtons` est préférable.
  - **Afficher l'image de la combinaison :**

    - **Ce que fait ce paramètre :** Contrôle si une petite image spécifique à chaque combinaison est affichée dans la liste.
    - **Effet de la modification de ce paramètre :**
      - *Lorsqu'il est activé (OUI) :* Si vous avez téléchargé des images spécifiques pour chaque combinaison de produit, elles apparaîtront à côté de leur combinaison respective dans la liste.
      - *Lorsqu'il est désactivé (NON) :* Seuls le nom, la référence et le prix de la combinaison seront affichés, sans image.
    - **Valeur recommandée :** OUI, si vous avez des images uniques pour les combinaisons. Cela aide considérablement les clients à visualiser le produit exact qu'ils sélectionnent.
    - **Scénario/exemple de marchand :** Pour les vêtements, afficher une image de chemise rouge pour la combinaison « Rouge - Grand » est beaucoup plus clair que du simple texte.
  - **Afficher la référence de la combinaison :**

    - **Ce que fait ce paramètre :** Détermine si le numéro de référence interne de chaque combinaison est affiché.
    - **Effet de la modification de ce paramètre :**
      - *Lorsqu'il est activé (OUI) :* La référence de la combinaison (par exemple, SKU) sera visible dans la liste.
      - *Lorsqu'il est désactivé (NON) :* Le numéro de référence sera masqué.
    - **Valeur recommandée :** OUI, en particulier pour les boutiques B2B ou les produits où les clients commandent souvent par référence.
    - **Scénario/exemple de marchand :** Un client qui commande à nouveau une pièce spécifique peut la connaître par son numéro de référence, ce qui facilite sa recherche.
  - **Afficher le champ de quantité de la combinaison :**

    - **Ce que fait ce paramètre :** Permet aux clients de spécifier la quantité pour chaque combinaison directement dans la liste, plutôt que d'en ajouter une à la fois.
    - **Effet de la modification de ce paramètre :**
      - *Lorsqu'il est activé (OUI) :* Un champ de saisie de quantité (par exemple, une boîte numérique) apparaîtra à côté de chaque combinaison, permettant aux clients de saisir une quantité souhaitée avant de cliquer sur « Ajouter au panier ».
      - *Lorsqu'il est désactivé (NON) :* Le bouton « Ajouter au panier » ajoutera généralement une unité de la combinaison au panier.
    - **Valeur recommandée :** OUI, pour la plupart des boutiques, car cela améliore l'efficacité pour les clients achetant plusieurs unités de la même combinaison.
    - **Scénario/exemple de marchand :** Un client achetant 5 unités de « Bleu - Moyen » et 3 unités de « Vert - Grand » peut le faire rapidement depuis la liste.
  - **Afficher le prix de la combinaison :**

    - **Ce que fait ce paramètre :** Contrôle si le prix de chaque combinaison individuelle est affiché dans la liste.
    - **Effet de la modification de ce paramètre :**
      - *Lorsqu'il est activé (OUI) :* Le prix de chaque combinaison spécifique sera affiché.
      - *Lorsqu'il est désactivé (NON) :* Le prix sera masqué, et les clients pourraient ne voir que le prix principal du produit ou devoir l'inférer.
    - **Valeur recommandée :** OUI. La transparence des prix est cruciale pour la confiance des clients et la prise de décision.
    - **Scénario/exemple de marchand :** Si différentes tailles ou couleurs ont des prix différents, afficher le prix exact de chaque combinaison est essentiel.
  - **Afficher la disponibilité de la combinaison :**

    - **Ce que fait ce paramètre :** Affiche l'état du stock (par exemple, « En stock », « Rupture de stock », « Derniers articles ! ») pour chaque combinaison.
    - **Effet de la modification de ce paramètre :**
      - *Lorsqu'il est activé (OUI) :* Les clients verront l'état de disponibilité de chaque combinaison, ce qui les aidera à prendre des décisions d'achat éclairées.
      - *Lorsqu'il est désactivé (NON) :* L'état du stock ne sera pas affiché dans la liste.
    - **Valeur recommandée :** OUI. Cela empêche les clients d'ajouter des articles en rupture de stock à leur panier, réduisant ainsi la frustration et les paniers abandonnés.
    - **Scénario/exemple de marchand :** Un client peut immédiatement voir que la chemise « Rouge - Grand » est en rupture de stock et choisir « Bleu - Grand » à la place.
  - **Afficher la description de la combinaison :**

    - **Ce que fait ce paramètre :** Si vous avez des descriptions spécifiques pour chaque combinaison, ce paramètre contrôle leur affichage.
    - **Effet de la modification de ce paramètre :**
      - *Lorsqu'il est activé (OUI) :* Toute description unique associée à une combinaison sera affichée dans la liste.
      - *Lorsqu'il est désactivé (NON) :* Les descriptions spécifiques aux combinaisons seront masquées.
    - **Valeur recommandée :** OUI, si vos combinaisons ont des descriptions distinctes qui ajoutent de la valeur à la décision du client.
    - **Scénario/exemple de marchand :** Pour un produit personnalisable, une description de combinaison pourrait détailler les matériaux spécifiques utilisés pour cette variante.
  - **Texte du bouton Ajouter au panier :**

    - **Ce que fait ce paramètre :** Vous permet de personnaliser le texte affiché sur le bouton « Ajouter au panier » pour chaque combinaison.
    - **Effet de la modification de ce paramètre :**
      - *Lorsqu'il est modifié :* Le texte du bouton sera mis à jour avec votre phrase personnalisée.
      - *Lorsqu'il est laissé vide :* Le texte par défaut « Ajouter au panier » (ou le texte par défaut de votre thème) sera utilisé.
    - **Valeur recommandée :** « Ajouter au panier » ou « Acheter maintenant » pour plus de clarté. Gardez-le concis.
    - **Scénario/exemple de marchand :** Vous pourriez le changer en « Sélectionner et acheter » si vous voulez insister sur la sélection avant l'achat.
  - **Afficher les combinaisons sous forme de tableau :**

    - **Ce que fait ce paramètre :** Bascule la présentation visuelle des combinaisons d'une simple liste à un tableau HTML structuré.
    - **Effet de la modification de ce paramètre :**
      - *Lorsqu'il est activé (OUI) :* Les combinaisons seront présentées sous forme de tableau avec des colonnes pour l'image, le nom, la référence, le prix, la quantité et l'ajout au panier. C'est souvent plus compact et organisé pour de nombreuses combinaisons.
      - *Lorsqu'il est désactivé (NON) :* Les combinaisons seront affichées sous forme de liste moins structurée, généralement une combinaison par ligne.
    - **Valeur recommandée :** OUI, dans la plupart des cas, car un tableau offre une meilleure lisibilité et un meilleur alignement, surtout avec de nombreuses options.
    - **Scénario/exemple de marchand :** Si vous avez plus de 20 combinaisons, un tableau facilite grandement le balayage et la comparaison.
  - **Afficher les combinaisons sous forme d'onglet :**

    - **Ce que fait ce paramètre :** Ce paramètre est probablement un détail d'implémentation hérité ou spécifique. Compte tenu du paramètre `Hook pour afficher la liste des combinaisons`, cela pourrait être redondant ou faire référence à un modèle spécifique.
    - **Effet de la modification de ce paramètre :**
      - *Lorsqu'il est activé (OUI) :* Pourrait forcer la liste des combinaisons dans une structure de type onglet, potentiellement en ignorant le hook choisi si ce hook ne crée pas naturellement un onglet.
      - *Lorsqu'il est désactivé (NON) :* L'affichage suivra le hook choisi plus directement.
    - **Valeur recommandée :** Généralement NON, sauf si vous souhaitez spécifiquement un onglet et que votre hook choisi ne le fournit pas. Fiez-vous au paramètre « Hook pour afficher la liste des combinaisons » pour le placement.
    - **Scénario/exemple de marchand :** Si votre thème ne crée pas automatiquement d'onglets pour `displayProductExtraContent`, l'activation de ceci pourrait forcer une apparence de type onglet.

#### 2.1.1 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Afficher la liste des combinaisons sur la page produit | OUI | Interrupteur principal pour activer/désactiver l'affichage front-office du module. |
| Configuration du module | Hook pour afficher la liste des combinaisons | `displayProductButtons` ou `displayProductExtraContent` | Détermine la position exacte de la liste sur la page produit. |
| Configuration du module | Afficher l'image de la combinaison | OUI (si les images existent) | Affiche des images uniques pour chaque combinaison. |
| Configuration du module | Afficher la référence de la combinaison | OUI | Affiche le numéro SKU/référence pour chaque combinaison. |
| Configuration du module | Afficher le champ de quantité de la combinaison | OUI | Permet aux clients de saisir des quantités pour chaque combinaison. |
| Configuration du module | Afficher le prix de la combinaison | OUI | Affiche le prix spécifique pour chaque combinaison. |
| Configuration du module | Afficher la disponibilité de la combinaison | OUI | Affiche l'état du stock (par exemple, « En stock ») pour chaque combinaison. |
| Configuration du module | Afficher la description de la combinaison | OUI (si les descriptions existent) | Affiche des descriptions uniques pour chaque combinaison. |
| Configuration du module | Texte du bouton Ajouter au panier | « Ajouter au panier » | Personnalise le texte sur les boutons « Ajouter au panier ». |
| Configuration du module | Afficher les combinaisons sous forme de tableau | OUI | Présente les combinaisons dans un format de tableau structuré pour une meilleure lisibilité. |
| Configuration du module | Afficher les combinaisons sous forme d'onglet | NON | (Probablement hérité/spécifique) Contrôle l'affichage de type onglet ; préférer le paramètre de hook. |

## 3. Dépannage marchand et Foire Aux Questions (FAQ)

**Q1 : La liste des combinaisons n'apparaît pas sur ma page produit.**
**R1 :**

- Tout d'abord, vérifiez si « Afficher la liste des combinaisons sur la page produit » est défini sur OUI dans la configuration du module.
- Ensuite, vérifiez le paramètre « Hook pour afficher la liste des combinaisons ». Certains thèmes peuvent ne pas rendre tous les hooks PrestaShop standard de la même manière. Essayez de passer à un autre hook (par exemple, `displayProductButtons`, `displayProductExtraContent`, `displayFooterProduct`) pour voir s'il apparaît.
- Assurez-vous que le produit que vous visualisez a bien des combinaisons définies.
- Videz votre cache PrestaShop (Paramètres avancés > Performances > Vider le cache).

**Q2 : Mes images de combinaison n'apparaissent pas dans la liste.**
**R2 :**

- Assurez-vous que « Afficher l'image de la combinaison » est activé dans les paramètres du module.
- Il est crucial que vous ayez téléchargé des images spécifiques pour chaque combinaison dans l'éditeur de produit de PrestaShop (Produit > Onglet Combinaisons > Modifier chaque combinaison > Ajouter une image). Si aucune image spécifique n'est attribuée à une combinaison, elle n'apparaîtra pas.

**Q3 : La liste semble désordonnée ou ne correspond pas au design de mon thème.**
**R3 :**

- Essayez d'activer « Afficher les combinaisons sous forme de tableau » si ce n'est pas déjà fait. Cela offre souvent une mise en page plus structurée et visuellement attrayante.
- Le module utilise son propre CSS. Le CSS de votre thème pourrait le remplacer ou entrer en conflit avec lui. Vous pourriez avoir besoin d'un développeur web pour ajuster le CSS du module (`mycombtabfree.css`) ou ajouter du CSS personnalisé à votre thème pour le styliser à votre goût.
- Expérimentez avec différents hooks. Certains hooks peuvent avoir un meilleur style par défaut de votre thème.

**Q4 : Puis-je traduire le texte du bouton « Ajouter au panier » dans d'autres langues ?**
**R4 :** Oui. Allez dans **International > Traductions** dans votre Back Office PrestaShop. Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez « Combinations List Free » dans le menu déroulant des modules. Vous pourrez alors traduire le texte du bouton et toute autre phrase spécifique au module.

**Q5 : Pourquoi certaines combinaisons affichent-elles « Rupture de stock » alors que j'ai du stock ?**
**R5 :**

- Vérifiez les paramètres de stock de votre produit dans l'éditeur de produit de PrestaShop. Assurez-vous que la combinaison spécifique a une quantité disponible.
- Vérifiez vos paramètres de gestion de stock globaux (Paramètres de la boutique > Paramètres produit > Stock de produits).
- Videz votre cache PrestaShop après avoir effectué des ajustements de stock.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Combinations List Free » (`mycombtabfree`) est un module PrestaShop standard conçu pour améliorer la page produit du front-office. Il fonctionne principalement en s'accrochant à divers points d'affichage de la page produit pour injecter sa structure HTML personnalisée pour les combinaisons de produits. Le module suit un modèle de type MVC de base au sein du framework de module PrestaShop, utilisant une classe de module principale pour la configuration et l'enregistrement des hooks, et des templates Smarty pour le rendu de la sortie du front-office. Il s'appuie sur les fonctionnalités de base existantes de PrestaShop pour récupérer les données de produit et de combinaison.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient aucun contrôleur d'administration Front-Office ou Back-Office personnalisé. Toute la configuration est gérée via la méthode `getContent()` de la classe de module principale, et le rendu du front-office est effectué directement via des hooks.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne contient aucune classe personnalisée ou définition d'`ObjectModel` dans le répertoire `classes/`. Il s'appuie entièrement sur les classes `Product` et `Combination` de PrestaShop pour récupérer et afficher les données.

### 4.4 Actifs JavaScript (`views/js/`)

- **`mycombtabfree/js/atc.js`**
  - **Portée :** Front-office.
  - **Objectif :** Ce script est responsable de la gestion de la fonctionnalité « Ajouter au panier » pour les combinaisons affichées par le module. Il intercepte probablement les événements de clic sur les boutons « Ajouter au panier » personnalisés générés par le module.
  - **Fonctionnalité :**
    - Lie les écouteurs d'événements aux boutons « Ajouter au panier » dans la liste/le tableau des combinaisons.
    - Lorsqu'un bouton est cliqué, il collecte l'`id_product`, l'`id_product_attribute` (ID de combinaison) et potentiellement la quantité du champ de saisie associé.
    - Il effectue ensuite une requête AJAX vers le contrôleur de panier principal de PrestaShop (ou un point de terminaison similaire) pour ajouter la combinaison sélectionnée au panier.
    - Il peut également mettre à jour le bloc panier, afficher des notifications (succès/erreur) ou gérer d'autres retours d'interface utilisateur après l'appel AJAX.
    - Il utilise probablement jQuery ou les événements natifs `prestashop.on` de PrestaShop pour les mises à jour dynamiques.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`mycombtabfree/css/admin.css`**

  - **Portée :** Style du formulaire d'administration du Back-office.
  - **Objectif :** Contient des styles spécifiquement pour la page de configuration du module dans le Back Office de PrestaShop. Cela peut inclure le style des éléments de formulaire, des alertes ou des ajustements de mise en page pour rendre l'interface de configuration conviviale.
  - **Sélecteurs clés :** Cible probablement les éléments dans la sortie `getContent()` du module, tels que `.panel`, `.form-group`, `.alert`, etc., pour assurer une interface utilisateur d'administration cohérente.
- **`mycombtabfree/css/mycombtabfree.css`**

  - **Portée :** Style client du Front-office.
  - **Objectif :** Fournit le style visuel principal pour la liste/le tableau des combinaisons affiché sur la page produit. Cela inclut la mise en page, la typographie, les couleurs et la réactivité.
  - **Sélecteurs clés :**
    - `.mycombtabfree-container` : Conteneur principal pour la liste des combinaisons.
    - `.mycombtabfree-table` : Styles pour l'élément `<table>` lorsque « Afficher les combinaisons sous forme de tableau » est activé.
    - `.mycombtabfree-row`, `.mycombtabfree-cell` : Styles pour les lignes et les cellules du tableau.
    - `.mycombtabfree-image`, `.mycombtabfree-name`, `.mycombtabfree-reference`, `.mycombtabfree-price`, `.mycombtabfree-qty`, `.mycombtabfree-atc` : Styles spécifiques pour chaque élément de données de combinaison.
    - Requêtes média pour les ajustements réactifs sur les petits écrans.
  - **Surcharge du développeur :** Les développeurs peuvent surcharger ces styles dans les fichiers CSS de leur thème personnalisé en utilisant des sélecteurs plus spécifiques ou en modifiant directement ce fichier (bien que cette dernière option ne soit pas recommandée pour la facilité de mise à jour).

### 4.6 Structure des templates Smarty (`views/templates/`)

- **`mycombtabfree/views/templates/admin/configure.tpl`**

  - **Portée :** Panneau de configuration de l'administration.
  - **Objectif :** Rend le formulaire HTML pour les paramètres de configuration du module dans le Back Office de PrestaShop. Ce template est chargé par la méthode `getContent()` de la classe de module principale.
  - **Contenu :** Contient des champs de formulaire (cases à cocher, champs de texte, listes déroulantes) correspondant aux paramètres décrits dans la section 4.1.
- **`mycombtabfree/views/templates/admin/pro-upsell.tpl`**

  - **Portée :** Panneau de configuration de l'administration.
  - **Objectif :** Affiche du contenu promotionnel ou une bannière de vente incitative pour une version « Pro » du module dans la configuration du Back Office. C'est une pratique courante pour les modules gratuits.
- **`mycombtabfree/views/templates/hook/pro-banner.tpl`**

  - **Portée :** Hook Front-office.
  - **Objectif :** Rend une bannière promotionnelle pour la version « Pro » du module, probablement affichée dans un hook Front-office moins intrusif (par exemple, `displayFooter` ou `displayLeftColumn`).
- **`mycombtabfree/views/templates/hook/tab.tpl`**

  - **Portée :** Hook Front-office.
  - **Objectif :** Ce template est probablement utilisé lorsque le paramètre « Afficher les combinaisons sous forme d'onglet » est activé, ou lorsque le module est accroché à une position qui crée naturellement un onglet (par exemple, `displayProductExtraContent`). Il contiendrait la structure d'un onglet produit, dans lequel la liste/le tableau des combinaisons réelles serait rendu.
- **`mycombtabfree/views/templates/hook/table.tpl`**

  - **Portée :** Hook Front-office.
  - **Objectif :** C'est le template principal responsable du rendu de la liste ou du tableau des combinaisons de produits sur le front office. Il itère sur les combinaisons disponibles pour un produit donné et affiche chacune d'elles selon les paramètres de configuration du module (par exemple, affichage de l'image, de la référence, du prix, du champ de quantité, du bouton d'ajout au panier).
  - **Logique :** Contient des boucles Smarty (`{foreach}`) pour itérer sur le tableau `$combinations`, des instructions conditionnelles (`{if}`) pour afficher les éléments en fonction des paramètres du module, et des variables comme `$combination.id_product_attribute`, `$combination.name`, `$combination.price`, etc.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Ce module ne crée aucune table SQL personnalisée.
  - Il stocke ses paramètres de configuration dans la table `ps_configuration` de PrestaShop. Les clés de configuration suivraient généralement un modèle comme `MYCOMBTABFREE_SETTING_NAME`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Utilisé pour enregistrer les actifs CSS (`mycombtabfree.css`) et JavaScript (`atc.js`) pour le front-office. |
| `displayProductButtons` | Près du bouton « Ajouter au panier » sur la page produit. | Un hook courant pour afficher la liste des combinaisons directement sous les détails du produit. |
| `displayProductExtraContent` | Dans la zone des onglets produit sur la page produit. | Permet à la liste des combinaisons d'apparaître dans son propre onglet dédié. |
| `displayFooterProduct` | En bas du contenu de la page produit. | Un autre emplacement possible pour la liste des combinaisons, souvent moins proéminent. |
| `actionFrontControllerSetMedia` | Avant que le contrôleur frontal ne rende sa sortie. | Utilisé pour ajouter des fichiers CSS et JS spécifiques au module à la page. |
| `moduleRoutes` | Lors de l'initialisation de la réécriture d'URL. | (Non explicitement utilisé par ce module, mais un hook courant pour les modules avec des URL personnalisées). |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, les corrections de bugs et le support développeur dédié pour le module « Combinations List Free », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Assurez-vous de télécharger la dernière version compatible avec votre installation PrestaShop depuis votre historique de commandes.
