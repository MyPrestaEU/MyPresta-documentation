---
title: "LLMS.txt Generator Pro - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop LLMS.txt Generator Pro par MyPresta.eu."
sidebar:
  label: "LLMS.txt Generator Pro - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module LLMS.txt Generator Pro sur MyPresta.eu](https://mypresta.eu/modules/seo/llmstxt-generator-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/seo/llmstxt-generator-pro/)
>
> ---


# LLMS.txt Generator Pro

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL). Votre serveur doit également autoriser l'écriture de fichiers dans le répertoire racine pour que le fichier `llms.txt` puisse être généré.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > LLMS.txt Generator Pro)

Ceci est le panneau de contrôle principal de votre module LLMS.txt Generator Pro. Ici, vous définirez comment votre fichier `llms.txt` est généré et quel contenu il inclut.

#### Paramètres généraux

- **Activer la génération de LLMS.txt :**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité principale du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module générera et servira le fichier `llms.txt` selon vos paramètres. Les robots d'exploration IA pourront y accéder.
    - *Lorsqu'il est désactivé :* Le fichier `llms.txt` ne sera pas généré ni servi par le module. Les robots d'exploration IA ne recevront pas de directives spécifiques de votre boutique.
  - **Valeur recommandée :** OUI
  - **Scénario/exemple pour le marchand :** Vous venez d'installer le module et souhaitez commencer à guider les robots IA. Activez ceci. Si vous devez temporairement arrêter le guidage IA pour la maintenance, vous pouvez le désactiver ici.
- **Type de fichier LLMS.txt :**

  - **Ce que fait ce paramètre :** Détermine si le fichier `llms.txt` est généré en tant que fichier statique (écrit sur votre serveur) ou servi dynamiquement à la demande.
  - **Effet de la modification de ce paramètre :**
    - *Statique :* Le module écrit un fichier `llms.txt` physique dans le répertoire racine de votre boutique. C'est généralement plus rapide pour les robots IA car cela ne nécessite pas de traitement PHP à chaque requête.
    - *Dynamique :* Le fichier `llms.txt` est généré par le code PHP de PrestaShop chaque fois qu'un robot IA le demande. Cela garantit le contenu le plus à jour mais peut être légèrement plus lent.
  - **Valeur recommandée :** Statique (pour la performance, sauf si vous avez des changements de contenu fréquents et en temps réel qui doivent être reflétés instantanément).
  - **Scénario/exemple pour le marchand :** Pour la plupart des boutiques, statique est suffisant. Si vous avez une boutique à très fort trafic avec des prix de produits ou des stocks en constante évolution, dynamique pourrait être préféré, mais considérez l'impact sur les performances.
- **Générer llms-full.txt :**

  - **Ce que fait ce paramètre :** Contrôle si un fichier `llms-full.txt` supplémentaire et plus complet est également généré. Ce fichier inclut généralement des informations plus détaillées ou moins restreintes que le `llms.txt` standard.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un fichier `llms-full.txt` sera créé à côté de `llms.txt`, offrant aux robots d'exploration IA un ensemble de données plus riche.
    - *Lorsqu'il est désactivé :* Seul le fichier `llms.txt` standard sera généré.
  - **Valeur recommandée :** OUI (pour fournir un maximum de données à l'IA, sauf si vous avez des raisons spécifiques de les restreindre).
  - **Scénario/exemple pour le marchand :** Vous souhaitez que les modèles d'IA aient accès à autant d'informations pertinentes que possible sur vos produits, y compris des détails potentiellement moins critiques mais toujours utiles.
- **Inclure les pages produits :**

  - **Ce que fait ce paramètre :** Détermine si les pages de produits individuelles sont listées dans le fichier `llms.txt`.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les URL de toutes vos pages de produits actives seront incluses, les rendant découvrables par l'IA.
    - *Lorsqu'il est désactivé :* Les pages de produits seront exclues, ce qui signifie que les robots IA ne seront pas explicitement guidés vers elles via `llms.txt`.
  - **Valeur recommandée :** OUI (Les produits sont généralement le cœur d'une boutique e-commerce).
  - **Scénario/exemple pour le marchand :** Vous souhaitez que l'IA aide les clients à trouver des produits spécifiques.
- **Inclure les pages catégories :**

  - **Ce que fait ce paramètre :** Détermine si les pages de catégories (listant des groupes de produits) sont listées dans le fichier `llms.txt`.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les URL de toutes vos pages de catégories actives seront incluses.
    - *Lorsqu'il est désactivé :* Les pages de catégories seront exclues.
  - **Valeur recommandée :** OUI (Les catégories aident l'IA à comprendre la structure de votre boutique).
  - **Scénario/exemple pour le marchand :** Vous souhaitez que l'IA comprenne les différents types de produits que vous vendez et guide les clients vers les sections pertinentes.
- **Inclure les pages CMS :**

  - **Ce que fait ce paramètre :** Détermine si vos pages de système de gestion de contenu (CMS) (par exemple, À propos de nous, Contact, Informations de livraison, Politique de confidentialité) sont listées.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les URL des pages CMS actives seront incluses.
    - *Lorsqu'il est désactivé :* Les pages CMS seront exclues.
  - **Valeur recommandée :** OUI (Important pour que l'IA comprenne votre entreprise et vos politiques).
  - **Scénario/exemple pour le marchand :** Vous souhaitez que l'IA puisse répondre aux questions sur les politiques ou l'historique de votre boutique.
- **Inclure les pages Fabricants/Marques :**

  - **Ce que fait ce paramètre :** Détermine si les pages dédiées à des fabricants ou marques spécifiques sont listées.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les URL des pages de fabricants/marques actives seront incluses.
    - *Lorsqu'il est désactivé :* Les pages de fabricants/marques seront exclues.
  - **Valeur recommandée :** OUI (Si les marques sont importantes pour votre offre de produits).
  - **Scénario/exemple pour le marchand :** Vous vendez des produits de marques connues et souhaitez que l'IA le reconnaisse.
- **Inclure les pages Fournisseurs :**

  - **Ce que fait ce paramètre :** Détermine si les pages dédiées à des fournisseurs spécifiques sont listées. (Moins courant pour la visibilité front-office, souvent utilisé à des fins internes).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les URL des pages de fournisseurs actives seront incluses.
    - *Lorsqu'il est désactivé :* Les pages de fournisseurs seront exclues.
  - **Valeur recommandée :** NON (Sauf si vous promouvez spécifiquement des fournisseurs sur votre front-office).
  - **Scénario/exemple pour le marchand :** Vous avez un modèle commercial unique où les fournisseurs sont visibles publiquement et vous souhaitez que l'IA les indexe.
- **Inclure la page Nouveaux produits :**

  - **Ce que fait ce paramètre :** Détermine si la page de liste "Nouveaux produits" est incluse.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* L'URL de la page des nouveaux produits sera incluse.
    - *Lorsqu'il est désactivé :* La page des nouveaux produits sera exclue.
  - **Valeur recommandée :** OUI (Pour mettre en évidence vos dernières offres auprès de l'IA).
  - **Scénario/exemple pour le marchand :** Vous ajoutez fréquemment de nouveaux produits et souhaitez que l'IA en soit rapidement informée.
- **Inclure la page Meilleures ventes :**

  - **Ce que fait ce paramètre :** Détermine si la page de liste "Meilleures ventes" ou "Top vendeurs" est incluse.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* L'URL de la page des meilleures ventes sera incluse.
    - *Lorsqu'il est désactivé :* La page des meilleures ventes sera exclue.
  - **Valeur recommandée :** OUI (Pour promouvoir vos articles les plus populaires).
  - **Scénario/exemple pour le marchand :** Vous souhaitez que l'IA recommande vos articles les plus vendus aux clients.
- **Inclure la page Promotions :**

  - **Ce que fait ce paramètre :** Détermine si la page de liste "Promotions" ou "En solde" est incluse.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* L'URL de la page des promotions sera incluse.
    - *Lorsqu'il est désactivé :* La page des promotions sera exclue.
  - **Valeur recommandée :** OUI (Pour mettre en évidence vos articles à prix réduits).
  - **Scénario/exemple pour le marchand :** Vous organisez des promotions et souhaitez que l'IA informe les clients des offres actuelles.
- **Inclure la page Contact :**

  - **Ce que fait ce paramètre :** Détermine si la page de contact de votre boutique est incluse.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* L'URL de la page de contact sera incluse.
    - *Lorsqu'il est désactivé :* La page de contact sera exclue.
  - **Valeur recommandée :** OUI (Essentiel pour que l'IA fournisse des informations de service client).
  - **Scénario/exemple pour le marchand :** Vous souhaitez que l'IA puisse indiquer aux clients comment joindre votre équipe de support.
- **Inclure la page Plan du site :**

  - **Ce que fait ce paramètre :** Détermine si la page principale du plan du site de votre boutique (si vous en avez une) est incluse.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* L'URL de la page du plan du site sera incluse.
    - *Lorsqu'il est désactivé :* La page du plan du site sera exclue.
  - **Valeur recommandée :** OUI (Peut aider l'IA à découvrir plus de contenu, similaire aux plans de site des moteurs de recherche).
  - **Scénario/exemple pour le marchand :** Vous souhaitez fournir à l'IA un aperçu complet de la structure de votre boutique.
- **Inclure les URL personnalisées :**

  - **Ce que fait ce paramètre :** Vous permet d'ajouter manuellement des URL spécifiques qui ne sont pas générées automatiquement par PrestaShop mais que vous souhaitez tout de même que l'IA découvre.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Une zone de texte apparaîtra où vous pourrez lister une URL par ligne. Ces URL seront ajoutées à votre fichier `llms.txt`.
    - *Lorsqu'il est désactivé :* Aucune URL personnalisée ne sera ajoutée.
  - **Valeur recommandée :** OUI (Si vous avez des pages statiques importantes ou des articles de blog en dehors de la structure principale de PrestaShop).
  - **Scénario/exemple pour le marchand :** Vous avez un blog séparé sur un sous-domaine ou des pages de destination spécifiques que vous souhaitez que l'IA indexe.
- **Exclure des URL spécifiques :**

  - **Ce que fait ce paramètre :** Vous permet de spécifier manuellement les URL qui ne doivent *pas* être incluses dans le fichier `llms.txt`, même si elles seraient autrement générées.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Une zone de texte apparaîtra où vous pourrez lister une URL par ligne. Ces URL seront explicitement exclues.
    - *Lorsqu'il est désactivé :* Aucune URL ne sera explicitement exclue par ce paramètre.
  - **Valeur recommandée :** À utiliser au besoin pour les pages sensibles ou non pertinentes.
  - **Scénario/exemple pour le marchand :** Vous avez des pages de test internes, des promotions obsolètes ou des pages de données clients sensibles que vous ne voulez absolument pas que l'IA accède.
- **Exclure les produits par catégorie :**

  - **Ce que fait ce paramètre :** Fournit un moyen d'exclure tous les produits appartenant à des catégories spécifiques du fichier `llms.txt`.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Une liste de vos catégories apparaîtra, vous permettant de sélectionner celles à exclure. Tous les produits des catégories sélectionnées seront omis.
    - *Lorsqu'il est désactivé :* Tous les produits seront pris en compte pour l'inclusion, quelle que soit la catégorie.
  - **Valeur recommandée :** À utiliser au besoin.
  - **Scénario/exemple pour le marchand :** Vous vendez à la fois des produits publics et une gamme de produits réservés aux B2B dans une catégorie spécifique que vous ne souhaitez pas que l'IA indexe pour la recherche publique générale.
- **Exclure les produits par fabricant :**

  - **Ce que fait ce paramètre :** Vous permet d'exclure tous les produits de fabricants spécifiques.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Une liste de vos fabricants apparaîtra pour la sélection. Les produits des fabricants sélectionnés seront omis.
    - *Lorsqu'il est désactivé :* Tous les produits seront pris en compte pour l'inclusion, quel que soit le fabricant.
  - **Valeur recommandée :** À utiliser au besoin.
  - **Scénario/exemple pour le marchand :** Vous avez temporairement cessé de vendre des produits d'une marque particulière et ne souhaitez pas que l'IA les affiche, même s'ils sont toujours dans votre catalogue.
- **Exclure les produits par fournisseur :**

  - **Ce que fait ce paramètre :** Vous permet d'exclure tous les produits de fournisseurs spécifiques.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Une liste de vos fournisseurs apparaîtra pour la sélection. Les produits des fournisseurs sélectionnés seront omis.
    - *Lorsqu'il est désactivé :* Tous les produits seront pris en compte pour l'inclusion, quel que soit le fournisseur.
  - **Valeur recommandée :** À utiliser au besoin.
  - **Scénario/exemple pour le marchand :** Vous avez un fournisseur dont les produits ne sont pas destinés à l'indexation publique par l'IA.
- **Exclure les produits par caractéristique :**

  - **Ce que fait ce paramètre :** Vous permet d'exclure des produits en fonction de caractéristiques de produit spécifiques (par exemple, "Couleur : Rouge", "Matériau : Bois").
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Vous pouvez sélectionner des caractéristiques et leurs valeurs. Les produits correspondant à ces caractéristiques seront omis.
    - *Lorsqu'il est désactivé :* Les caractéristiques de produit ne seront pas utilisées pour l'exclusion.
  - **Valeur recommandée :** À utiliser au besoin.
  - **Scénario/exemple pour le marchand :** Vous avez des produits marqués d'une caractéristique "Arrêté" que vous souhaitez masquer à l'IA.
- **Exclure les produits par attribut :**

  - **Ce que fait ce paramètre :** Vous permet d'exclure des produits en fonction d'attributs de produit spécifiques (par exemple, "Taille : XL", "Poids : 1kg").
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Vous pouvez sélectionner des attributs et leurs valeurs. Les produits correspondant à ces attributs seront omis.
    - *Lorsqu'il est désactivé :* Les attributs de produit ne seront pas utilisés pour l'exclusion.
  - **Valeur recommandée :** À utiliser au besoin.
  - **Scénario/exemple pour le marchand :** Vous avez des produits avec une combinaison d'attributs "En rupture de stock" que vous ne souhaitez pas que l'IA affiche.
- **Exclure les produits par fourchette de prix :**

  - **Ce que fait ce paramètre :** Vous permet d'exclure les produits qui se situent dans une fourchette de prix spécifiée.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Vous pouvez saisir un prix minimum et maximum. Les produits dont les prix se situent dans cette fourchette seront omis.
    - *Lorsqu'il est désactivé :* Les prix des produits ne seront pas utilisés pour l'exclusion.
  - **Valeur recommandée :** À utiliser au besoin.
  - **Scénario/exemple pour le marchand :** Vous souhaitez que l'IA n'indexe que vos produits premium (par exemple, exclure les produits de moins de 10 $).
- **Exclure les produits par quantité de stock :**

  - **Ce que fait ce paramètre :** Vous permet d'exclure des produits en fonction de leur quantité de stock actuelle.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Vous pouvez définir une quantité de stock minimale. Les produits dont le stock est inférieur à cette quantité seront omis.
    - *Lorsqu'il est désactivé :* La quantité de stock des produits ne sera pas utilisée pour l'exclusion.
  - **Valeur recommandée :** OUI (Exclure les produits avec 0 stock pour éviter que l'IA ne recommande des articles indisponibles).
  - **Scénario/exemple pour le marchand :** Vous ne voulez pas que l'IA affiche des produits en rupture de stock. Définissez ceci pour exclure les produits avec un stock <= 0.
- **Exclure les produits par visibilité :**

  - **Ce que fait ce paramètre :** Vous permet d'exclure des produits en fonction de leur paramètre de visibilité PrestaShop (par exemple, "Catalogue uniquement", "Recherche uniquement", "Partout").
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Vous pouvez sélectionner les options de visibilité à exclure. Les produits correspondants seront omis.
    - *Lorsqu'il est désactivé :* La visibilité des produits ne sera pas utilisée pour l'exclusion.
  - **Valeur recommandée :** À utiliser au besoin.
  - **Scénario/exemple pour le marchand :** Vous avez des produits définis sur "Catalogue uniquement" (non recherchables) que vous souhaitez également masquer à l'IA.
- **Exclure les produits par statut :**

  - **Ce que fait ce paramètre :** Vous permet d'exclure des produits en fonction de leur statut actif/inactif.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Vous pouvez choisir d'exclure les produits inactifs.
    - *Lorsqu'il est désactivé :* Les produits actifs et inactifs seront pris en compte.
  - **Valeur recommandée :** OUI (Exclure les produits inactifs).
  - **Scénario/exemple pour le marchand :** Vous souhaitez que l'IA n'affiche que les produits actuellement disponibles et actifs.
- **Exclure les produits par date d'ajout :**

  - **Ce que fait ce paramètre :** Vous permet d'exclure des produits en fonction de leur date d'ajout à votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Vous pouvez définir une plage de dates. Les produits ajoutés en dehors de cette plage seront omis.
    - *Lorsqu'il est désactivé :* La date d'ajout du produit ne sera pas utilisée pour l'exclusion.
  - **Valeur recommandée :** À utiliser au besoin.
  - **Scénario/exemple pour le marchand :** Vous souhaitez que l'IA n'indexe que les produits ajoutés au cours de la dernière année.
- **Exclure les produits par date de mise à jour :**

  - **Ce que fait ce paramètre :** Vous permet d'exclure des produits en fonction de leur dernière date de mise à jour.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Vous pouvez définir une plage de dates. Les produits mis à jour en dehors de cette plage seront omis.
    - *Lorsqu'il est désactivé :* La date de mise à jour du produit ne sera pas utilisée pour l'exclusion.
  - **Valeur recommandée :** À utiliser au besoin.
  - **Scénario/exemple pour le marchand :** Vous souhaitez que l'IA n'indexe que les produits qui ont été récemment mis à jour ou révisés.
- **Exclure les produits par ID de produit spécifiques :**

  - **Ce que fait ce paramètre :** Vous permet de saisir manuellement une liste d'ID de produits spécifiques, séparés par des virgules, à exclure.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les produits avec les ID spécifiés seront omis.
    - *Lorsqu'il est désactivé :* Aucun produit ne sera exclu par ID.
  - **Valeur recommandée :** À utiliser au besoin.
  - **Scénario/exemple pour le marchand :** Vous avez quelques produits spécifiques qui sont problématiques ou sensibles et ne doivent jamais être indexés par l'IA.

#### Paramètres avancés

- **Planification de la régénération (Tâche Cron) :**

  - **Ce que fait ce paramètre :** Définit la fréquence à laquelle le fichier `llms.txt` doit être automatiquement régénéré. C'est crucial pour maintenir le fichier à jour sans intervention manuelle.
  - **Effet de la modification de ce paramètre :**
    - *Quotidien / Hebdomadaire / Mensuel :* Le module fournira une URL de tâche cron. Lorsque cette URL est accédée (par exemple, par le service cron de votre hébergeur), le fichier `llms.txt` sera reconstruit.
    - *Manuel :* Vous devrez cliquer manuellement sur le bouton "Générer LLMS.txt" chaque fois que vous souhaitez mettre à jour le fichier.
  - **Valeur recommandée :** Quotidien (pour la plupart des boutiques actives).
  - **Scénario/exemple pour le marchand :** Vous ajoutez de nouveaux produits ou mettez à jour les prix régulièrement. La configuration d'une régénération quotidienne garantit que les robots d'exploration IA obtiennent toujours les dernières informations. Le module affichera l'URL cron que vous devez configurer sur votre serveur.
- **Support multistore :**

  - **Ce que fait ce paramètre :** Si vous utilisez une boutique PrestaShop Multistore, cette option vous permet de générer des fichiers `llms.txt` distincts pour chacune de vos boutiques ou un seul fichier pour toutes les boutiques.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le module respectera votre contexte Multistore et générera des fichiers spécifiques au contenu de chaque boutique.
    - *Désactivé :* Le module pourrait générer un seul fichier basé sur la boutique par défaut ou se comporter de manière inattendue dans un environnement Multistore.
  - **Valeur recommandée :** OUI (si vous utilisez Multistore).
  - **Scénario/exemple pour le marchand :** Vous avez des catalogues de produits ou des langues différents pour chaque boutique de votre configuration Multistore, et vous avez besoin de fichiers `llms.txt` distincts pour chacun.
- **Durée de vie du cache (minutes) :**

  - **Ce que fait ce paramètre :** Détermine la durée pendant laquelle le fichier `llms.txt` généré est mis en cache avant d'être considéré comme "périmé" et de nécessiter une régénération (pour le type de fichier dynamique).
  - **Effet de la modification de ce paramètre :**
    - *Valeur plus élevée :* Régénération moins fréquente, potentiellement plus rapide pour les robots IA mais le contenu pourrait être légèrement plus ancien.
    - *Valeur plus faible :* Régénération plus fréquente, assurant un contenu plus frais mais potentiellement une charge serveur plus élevée.
  - **Valeur recommandée :** 60 (1 heure) pour dynamique, ou non pertinent pour statique.
  - **Scénario/exemple pour le marchand :** Si vous utilisez la génération dynamique et que vos données de produits changent toutes les heures, définissez ceci sur 60. Si les changements sont moins fréquents, vous pouvez l'augmenter.
- **Activer l'analyse et le suivi des robots :**

  - **Ce que fait ce paramètre :** Active une fonctionnalité pour suivre quand les robots IA accèdent à votre fichier `llms.txt`, fournissant des informations sur leur activité.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module enregistrera les accès au fichier `llms.txt`, qui peuvent être consultés dans le tableau de bord du module.
    - *Lorsqu'il est désactivé :* Aucune donnée d'accès aux robots ne sera collectée.
  - **Valeur recommandée :** OUI (Utile pour comprendre l'activité des robots d'exploration IA).
  - **Scénario/exemple pour le marchand :** Vous souhaitez voir à quelle fréquence les modèles d'IA explorent votre boutique et lesquels sont les plus actifs.
- **Bouton Vider le cache :**

  - **Ce que fait ce paramètre :** Un bouton manuel pour vider tous les fichiers `llms.txt` mis en cache.
  - **Effet de la modification de ce paramètre :** Supprime immédiatement tous les fichiers `llms.txt` stockés, forçant une nouvelle régénération lors de la prochaine requête (pour dynamique) ou lorsque le bouton "Générer LLMS.txt" est cliqué (pour statique).
  - **Valeur recommandée :** Cliquez lorsque vous apportez des modifications importantes à vos paramètres ou à votre catalogue de produits et que vous souhaitez vous assurer que le fichier `llms.txt` est immédiatement mis à jour.
  - **Scénario/exemple pour le marchand :** Vous venez d'ajouter une nouvelle gamme de produits majeure et souhaitez que l'IA la découvre immédiatement, vous videz donc le cache et régénérez.
- **Bouton Générer LLMS.txt :**

  - **Ce que fait ce paramètre :** Un bouton manuel pour générer ou régénérer immédiatement le fichier `llms.txt` en fonction de vos paramètres actuels.
  - **Effet de la modification de ce paramètre :** Le module traite votre catalogue et vos paramètres, puis crée ou met à jour le fichier `llms.txt`.
  - **Valeur recommandée :** Cliquez après avoir apporté des modifications de configuration ou lorsque vous avez besoin d'une mise à jour immédiate, surtout si vous utilisez la génération de fichiers statiques.
  - **Scénario/exemple pour le marchand :** Vous avez terminé de configurer toutes vos règles d'exclusion et souhaitez créer le fichier `llms.txt` initial.

#### Remplacements par produit (Page produit admin)

Le module s'intègre également directement dans vos pages d'édition de produits dans le Back Office.

- **Exclure ce produit de LLMS.txt :**
  - **Ce que fait ce paramètre :** Une case à cocher sur les pages de produits individuelles qui vous permet de remplacer les paramètres globaux et d'exclure spécifiquement un seul produit du fichier `llms.txt`.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'elle est cochée :* Ce produit spécifique ne sera pas inclus dans le fichier `llms.txt`, quelles que soient les autres règles d'inclusion globales.
    - *Lorsqu'elle est décochée :* L'inclusion du produit sera déterminée par les paramètres globaux.
  - **Valeur recommandée :** À utiliser au besoin pour des produits spécifiques.
  - **Scénario/exemple pour le marchand :** Vous avez un produit temporairement indisponible, ou un article très spécifique que vous ne souhaitez pas que l'IA promeuve largement.

#### Remplacements par catégorie (Page catégorie admin)

De même, le module s'intègre dans vos pages d'édition de catégories.

- **Exclure cette catégorie de LLMS.txt :**
  - **Ce que fait ce paramètre :** Une case à cocher sur les pages de catégories individuelles qui vous permet de remplacer les paramètres globaux et d'exclure spécifiquement une catégorie entière (et ses produits) du fichier `llms.txt`.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'elle est cochée :* Cette catégorie spécifique et tous les produits qu'elle contient ne seront pas inclus dans le fichier `llms.txt`.
    - *Lorsqu'elle est décochée :* L'inclusion de la catégorie sera déterminée par les paramètres globaux.
  - **Valeur recommandée :** À utiliser au besoin pour des catégories spécifiques.
  - **Scénario/exemple pour le marchand :** Vous avez une catégorie "Liquidation" qui change fréquemment et vous préférez ne pas la faire indexer par l'IA, ou une catégorie à usage interne.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### Tableau de bord (Back Office > Modules > LLMS.txt Generator Pro > Tableau de bord)

- **Nom de l'écran et emplacement du menu :** Cet écran est accessible depuis la page de configuration principale du module, généralement via un onglet ou un lien "Tableau de bord". Il fournit un aperçu de l'activité des robots IA et du statut du module.
- **Actions et paramètres disponibles :**
  - **Analyse du trafic des robots :** Affiche des graphiques ou des tableaux montrant quels robots d'exploration IA (agents utilisateurs) ont accédé à votre fichier `llms.txt`, à quelle fréquence et quand.
  - **Statut de la dernière génération :** Indique la date de la dernière génération du fichier `llms.txt`, sa taille et le nombre d'URL incluses.
  - **Journaux d'erreurs :** Tout problème rencontré lors de la génération sera affiché ici.
- **Effet des modifications :** Cet écran est principalement destiné à la surveillance et au reporting. Les modifications ici sont généralement liées à la visualisation de données, et non à la modification du comportement de la boutique.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vérifiez périodiquement le tableau de bord pour vous assurer que votre fichier `llms.txt` est accédé par les robots IA comme prévu et pour surveiller les erreurs éventuelles. Cela vous aide à comprendre l'impact de votre stratégie de visibilité IA.

#### Aperçu (Back Office > Modules > LLMS.txt Generator Pro > Aperçu)

- **Nom de l'écran et emplacement du menu :** Accessible depuis la page de configuration principale du module, généralement via un onglet ou un lien "Aperçu".
- **Actions et paramètres disponibles :**
  - **Affichage du contenu de LLMS.txt :** Affiche le contenu réel du fichier `llms.txt` qui serait servi aux robots d'exploration IA, basé sur vos paramètres actuels.
  - **Affichage du contenu de llms-full.txt :** Si activé, affiche également le contenu du fichier `llms-full.txt`.
- **Effet des modifications :** Cet écran est destiné à la vérification. Il vous permet de revoir le contenu généré avant qu'il ne soit en ligne ou après avoir apporté des modifications, en vous assurant qu'il répond à vos exigences.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Après avoir apporté des modifications importantes aux paramètres de votre module ou à votre catalogue de produits, utilisez l'écran d'aperçu pour vérifier que les URL correctes sont incluses et exclues.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Config du module | Activer la génération de LLMS.txt | OUI | Active/désactive la fonction principale du module. |
| Config du module | Type de fichier LLMS.txt | Statique | Choisissez statique pour la performance, dynamique pour les mises à jour en temps réel. |
| Config du module | Générer llms-full.txt | OUI | Fournit un fichier plus complet pour l'IA. |
| Config du module | Inclure les pages produits | OUI | Rend les URL des produits découvrables par l'IA. |
| Config du module | Inclure les pages catégories | OUI | Rend les URL des catégories découvrables par l'IA. |
| Config du module | Inclure les pages CMS | OUI | Rend les pages d'information découvrables par l'IA. |
| Config du module | Inclure les pages Fabricants/Marques | OUI | Rend les pages de marques découvrables par l'IA. |
| Config du module | Inclure les pages Fournisseurs | NON | Généralement pas nécessaire pour l'indexation publique par l'IA. |
| Config du module | Inclure la page Nouveaux produits | OUI | Met en évidence les derniers produits pour l'IA. |
| Config du module | Inclure la page Meilleures ventes | OUI | Propose les articles les plus vendus à l'IA. |
| Config du module | Inclure la page Promotions | OUI | Met en évidence les articles à prix réduits pour l'IA. |
| Config du module | Inclure la page Contact | OUI | Fournit les informations de contact à l'IA. |
| Config du module | Inclure la page Plan du site | OUI | Aide l'IA à découvrir plus de contenu. |
| Config du module | Inclure les URL personnalisées | À utiliser au besoin | Ajoute des URL spécifiques, non PrestaShop. |
| Config du module | Exclure des URL spécifiques | À utiliser au besoin | Masque les URL sensibles ou non pertinentes. |
| Config du module | Exclure les produits par catégorie | À utiliser au besoin | Filtre les produits par catégorie. |
| Config du module | Exclure les produits par fabricant | À utiliser au besoin | Filtre les produits par fabricant. |
| Config du module | Exclure les produits par fournisseur | À utiliser au besoin | Filtre les produits par fournisseur. |
| Config du module | Exclure les produits par caractéristique | À utiliser au besoin | Filtre les produits par caractéristiques spécifiques. |
| Config du module | Exclure les produits par attribut | À utiliser au besoin | Filtre les produits par attributs spécifiques. |
| Config du module | Exclure les produits par fourchette de prix | À utiliser au besoin | Filtre les produits dans une fourchette de prix. |
| Config du module | Exclure les produits par quantité de stock | OUI (<=0) | Masque les produits en rupture de stock à l'IA. |
| Config du module | Exclure les produits par visibilité | À utiliser au besoin | Filtre les produits par visibilité PrestaShop. |
| Config du module | Exclure les produits par statut | OUI (inactif) | Masque les produits inactifs à l'IA. |
| Config du module | Exclure les produits par date d'ajout | À utiliser au besoin | Filtre les produits par date de création. |
| Config du module | Exclure les produits par date de mise à jour | À utiliser au besoin | Filtre les produits par date de dernière mise à jour. |
| Config du module | Exclure les produits par ID de produit spécifiques | À utiliser au besoin | Exclut les produits individuels par ID. |
| Config du module | Planification de la régénération (Tâche Cron) | Quotidien | Automatise les mises à jour de `llms.txt`. |
| Config du module | Support multistore | OUI (si applicable) | Permet des fichiers distincts pour chaque boutique. |
| Config du module | Durée de vie du cache (minutes) | 60 (pour dynamique) | Définit la durée de mise en cache du fichier dynamique. |
| Config du module | Activer l'analyse et le suivi des robots | OUI | Surveille l'activité des robots d'exploration IA. |
| Config du module | Bouton Vider le cache | Cliquer au besoin | Force la suppression du cache pour des mises à jour immédiates. |
| Config du module | Bouton Générer LLMS.txt | Cliquer au besoin | Génère manuellement le fichier `llms.txt`. |
| Page d'édition de produit | Exclure ce produit de LLMS.txt | Décoché | Remplace les paramètres globaux pour un seul produit. |
| Page d'édition de catégorie | Exclure cette catégorie de LLMS.txt | Décoché | Remplace les paramètres globaux pour une catégorie entière. |
| Tableau de bord | Analyse du trafic des robots | N/A | Surveille l'accès des robots IA. |
| Tableau de bord | Statut de la dernière génération | N/A | Affiche le statut du fichier `llms.txt`. |
| Aperçu | Affichage du contenu de LLMS.txt | N/A | Affiche le contenu `llms.txt` généré. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : Mon fichier `llms.txt` n'apparaît pas ou ne se met pas à jour.**
R :

1.  **Vérifiez "Activer la génération de LLMS.txt" :** Assurez-vous que cette option est réglée sur OUI dans la configuration du module.
2.  **Vérifiez le type de fichier :** Si réglé sur "Statique", assurez-vous que votre serveur a les permissions d'écriture dans le répertoire racine de PrestaShop. De plus, cliquez manuellement sur le bouton "Générer LLMS.txt".
3.  **Tâche Cron :** Si vous utilisez une tâche cron, vérifiez qu'elle est correctement configurée sur votre hébergement et que l'URL fournie par le module est accessible.
4.  **Vider le cache :** Allez dans **Paramètres avancés > Performances** dans PrestaShop et videz le cache Smarty. Ensuite, essayez de régénérer le fichier `llms.txt`.
5.  **Tableau de bord du module :** Vérifiez le tableau de bord du module pour tout message d'erreur pendant la génération.

**Q : J'ai effectué des modifications, mais le fichier `llms.txt` ne les reflète pas.**
R :

1.  **Régénérez manuellement :** Cliquez sur le bouton "Générer LLMS.txt" dans la configuration du module.
2.  **Synchronisation de la tâche Cron :** Si vous comptez sur une tâche cron, rappelez-vous qu'elle ne s'exécute qu'à intervalles réguliers. Vos modifications apparaîtront après la prochaine exécution planifiée.
3.  **Cache :** Si vous utilisez la génération dynamique, le fichier `llms.txt` peut être mis en cache. Cliquez sur le bouton "Vider le cache" dans le module, ou videz le cache de PrestaShop sous **Paramètres avancés > Performances**.

**Q : Comment savoir si les robots IA utilisent réellement mon fichier `llms.txt` ?**
R : Activez "Activer l'analyse et le suivi des robots" dans les paramètres du module. Le tableau de bord du module vous montrera alors des statistiques sur les agents utilisateurs IA qui ont accédé à votre fichier `llms.txt` et quand.

**Q : Le fichier `llms.txt` est trop volumineux ou inclut trop d'URL non pertinentes.**
R :

1.  **Vérifiez les paramètres d'inclusion :** Parcourez les options "Inclure..." et désactivez tous les types de contenu que vous ne souhaitez pas que l'IA indexe (par exemple, les pages Fournisseurs).
2.  **Utilisez les filtres d'exclusion :** Utilisez largement les filtres "Exclure les produits par..." (Catégorie, Stock, Prix, etc.) et "Exclure des URL spécifiques" pour affiner le contenu.
3.  **Remplacements par produit/catégorie :** Pour des cas très spécifiques, utilisez les cases à cocher d'exclusion sur les pages d'édition de produits et de catégories individuelles.

**Q : Mon thème personnalisé n'affiche pas correctement les fonctionnalités du module (par exemple, champs supplémentaires sur la page produit).**
R : L'intégration du module avec les pages produit/catégorie est standard. Si vous rencontrez des problèmes, il s'agit probablement d'un conflit avec votre thème personnalisé ou un autre module qui modifie fortement les formulaires d'édition produit/catégorie.

1.  **Vérifiez les conflits :** Désactivez temporairement les autres modules qui modifient les pages produit/catégorie pour voir si le problème est résolu.
2.  **Surcharges de thème :** Votre thème peut avoir des surcharges de template qui empêchent l'affichage des champs supplémentaires du module. Contactez le développeur de votre thème ou un expert PrestaShop pour enquêter.
3.  **Vider le cache :** Videz toujours le cache de PrestaShop après des modifications de thème ou de module.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module LLMS.txt Generator Pro suit une architecture de module PrestaShop standard, tirant parti des principes MVC. Il fonctionne principalement via une classe de module principale (`llmstxtpro/index.php`) pour la configuration et la gestion des hooks, et un ensemble de classes dédiées (`classes/`) pour la logique métier, la gestion des données et la génération de fichiers. Les contrôleurs frontaux gèrent la diffusion dynamique de `llms.txt` et l'exécution des tâches cron. La configuration est stockée dans `ps_configuration` et des tables personnalisées.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs sont responsables de la diffusion des fichiers `llms.txt` et `llms-full.txt`, et de la gestion des requêtes de tâches cron.

- `controllers/front/aicatalog.php`
  - **Nom de la classe et classe parente :** `LlmsTxtProAiCatalogModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Gère probablement des requêtes de catalogue IA spécifiques, potentiellement pour des formats de données plus structurés au-delà de `llms.txt`. Il pourrait servir une représentation JSON ou XML du catalogue pour la consommation par l'IA.
- `controllers/front/cron.php`
  - **Nom de la classe et classe parente :** `LlmsTxtProCronModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur est conçu pour être appelé par une tâche cron côté serveur. Lorsqu'il est accédé, il déclenche le processus de régénération de `llms.txt` (et `llms-full.txt`) basé sur la configuration du module. Il renvoie généralement un simple message de succès/échec.
- `controllers/front/index.php`
  - **Nom de la classe et classe parente :** `LlmsTxtProIndexModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Il pourrait s'agir d'un espace réservé ou d'un point d'entrée générique. Compte tenu des autres contrôleurs spécifiques, il est moins probable qu'il ait une fonction directe et unique pour la génération de `llms.txt` elle-même, mais pourrait être utilisé pour le routage général du front-office du module ou des informations.
- `controllers/front/llmsfull.php`
  - **Nom de la classe et classe parente :** `LlmsTxtProLlmsFullModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Lorsque le type de fichier `llms-full.txt` est défini sur dynamique, ce contrôleur sert le contenu du fichier `llms-full.txt`. Il interroge la base de données et génère la liste complète des URL et des données associées.
- `controllers/front/llmstxt.php`
  - **Nom de la classe et classe parente :** `LlmsTxtProLlmsTxtModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Lorsque le type de fichier `llms.txt` est défini sur dynamique, ce contrôleur sert le contenu du fichier `llms.txt` standard. Il interroge la base de données et génère la liste des URL en fonction de la configuration du module et des règles d'exclusion.

#### Contrôleurs d'administration Back-Office

Le module ne semble pas avoir de contrôleurs d'administration personnalisés dédiés (`controllers/admin/`). Toute la configuration est gérée via la méthode `getContent()` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)

- `classes/index.php`
  - **Responsabilité :** Généralement un fichier vide pour empêcher la liste des répertoires, pas une classe fonctionnelle.
- `classes/LlmsTxtProAiCatalog.php`
  - **Responsabilité :** Contient probablement la logique de génération d'un catalogue IA plus structuré (par exemple, JSON-LD, balisage schema.org) qui pourrait être servi par `aicatalog.php`. Il encapsulerait des méthodes pour interroger les données de produits, de catégories et de CMS avec un formatage spécifique à l'IA.
- `classes/LlmsTxtProAnalytics.php`
  - **Responsabilité :** Gère l'enregistrement et la récupération des données d'accès des robots IA. Il interagirait avec une table de base de données personnalisée pour stocker l'agent utilisateur, l'horodatage et les informations du fichier accédé (`llms.txt` ou `llms-full.txt`). Fournit des méthodes pour rapporter ces données au tableau de bord de l'administration.
- `classes/LlmsTxtProConfig.php`
  - **Responsabilité :** Une classe d'aide pour gérer les paramètres de configuration du module. Elle fournirait des méthodes statiques pour obtenir et définir les valeurs de configuration de `Configuration::get()` et `Configuration::updateValue()`, potentiellement avec des valeurs par défaut et un transtypage.
- `classes/LlmsTxtProGenerator.php`
  - **Responsabilité :** C'est la classe de logique principale pour générer le contenu de `llms.txt` et `llms-full.txt`. Elle contient des méthodes pour :
    - Récupérer les produits, catégories, pages CMS, fabricants, fournisseurs, etc.
    - Appliquer tous les filtres d'inclusion et d'exclusion (par catégorie, fabricant, prix, stock, URL personnalisées, etc.).
    - Formater les URL selon la norme `llms.txt`.
    - Gérer l'écriture de fichiers statiques dans le répertoire racine.
    - Potentiellement gérer la mise en cache pour la génération dynamique.
- `classes/LlmsTxtProLogger.php`
  - **Responsabilité :** Une classe utilitaire pour enregistrer les événements, avertissements ou erreurs spécifiques au module. Elle pourrait écrire dans un fichier journal personnalisé ou s'intégrer au journal par défaut de PrestaShop. Utile pour le débogage des problèmes de génération.

### 4.4 Actifs JavaScript (`views/js/`)

- `llmstxtpro/lib/searchTool/views/js/autocomplete.js`
  - **Portée :** Back-office.
  - **Responsabilité :** Fournit une fonctionnalité d'autocomplétion pour les champs de saisie dans la configuration de l'administration, probablement pour la sélection de produits, catégories, fabricants ou URL spécifiques à exclure. Il se lie aux champs de saisie et effectue des appels AJAX pour récupérer des suggestions.
- `llmstxtpro/views/js/adminLlmsTxtProDashboard.js`
  - **Portée :** Back-office (écran Tableau de bord).
  - **Responsabilité :** Gère l'affichage dynamique des données analytiques sur le tableau de bord du module. Il pourrait utiliser AJAX pour récupérer les statistiques de trafic des robots de `LlmsTxtProAnalytics` et les rendre à l'aide de bibliothèques de graphiques ou de tableaux de données.

### 4.5 Feuilles de style CSS (`views/css/`)

- `llmstxtpro/lib/searchTool/views/css/autocomplete.css`
  - **Portée :** Back-office.
  - **Responsabilité :** Style les listes déroulantes et les suggestions d'autocomplétion utilisées dans les formulaires de configuration de l'administration.
- `llmstxtpro/views/css/admin-config.css`
  - **Portée :** Back-office (page de configuration du module).
  - **Responsabilité :** Fournit un style spécifique pour le formulaire de configuration principal du module, assurant une présentation cohérente et conviviale au sein du Back Office de PrestaShop.
- `llmstxtpro/views/css/admin-dashboard.css`
  - **Portée :** Back-office (écran Tableau de bord).
  - **Responsabilité :** Style les éléments du tableau de bord, y compris les graphiques, les tableaux et les indicateurs de statut pour l'analyse du trafic des robots et le statut de génération.
- `llmstxtpro/views/css/admin-searchtool.css`
  - **Portée :** Back-office.
  - **Responsabilité :** Style général pour les composants d'interface utilisateur liés à la recherche dans l'administration, potentiellement partagé avec `autocomplete.css` ou pour d'autres interfaces de recherche/filtrage.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** : La description du module ne liste pas explicitement les templates de hook, suggérant que sa présence en front-office est principalement via le fichier `llms.txt` lui-même, et non des éléments visuels.
- **Templates d'administration (`views/templates/admin/`)** :
  - `llmstxtpro/views/templates/admin/category-extra.tpl`
    - **Objectif :** Rend la case à cocher "Exclure cette catégorie de LLMS.txt" et tous les champs associés sur la page d'édition de catégorie de PrestaShop. Ce template est probablement accroché à `displayAdminProductsExtra` ou similaire.
  - `llmstxtpro/views/templates/admin/configure.tpl`
    - **Objectif :** Le template principal pour la page de configuration du module (méthode `getContent()`). Il rend tous les paramètres généraux, les options d'inclusion/exclusion, les paramètres avancés et les boutons d'action.
  - `llmstxtpro/views/templates/admin/dashboard.tpl`
    - **Objectif :** Rend le tableau de bord d'analyse du module, affichant le trafic des robots, le statut de génération et potentiellement les journaux d'erreurs.
  - `llmstxtpro/views/templates/admin/preview.tpl`
    - **Objectif :** Rend le contenu des fichiers `llms.txt` et `llms-full.txt` générés pour examen dans le Back Office.
  - `llmstxtpro/views/templates/admin/product-extra.tpl`
    - **Objectif :** Rend la case à cocher "Exclure ce produit de LLMS.txt" et tous les champs associés sur la page d'édition de produit de PrestaShop. Ce template est probablement accroché à `displayAdminProductsExtra` ou similaire.
- **Templates Front-office (`views/templates/front/`)** : Aucun n'est explicitement listé, ce qui renforce l'idée que l'interaction front-office du module est principalement machine-à-machine via le fichier `llms.txt`.
- `llmstxtpro/lib/searchTool/views/scripts.tpl`
  - **Objectif :** Inclut probablement les actifs JavaScript et CSS pour l'outil de recherche (par exemple, autocomplete.js, autocomplete.css) dans le contexte d'administration.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :
  - `ps_configuration` : Stocke tous les paramètres de configuration du module (par exemple, `LLMSTXTPRO_ENABLED`, `LLMSTXTPRO_FILE_TYPE`, `LLMSTXTPRO_INCLUDE_PRODUCTS`, `LLMSTXTPRO_EXCLUDE_URLS`, etc.).
  - `ps_llmstxtpro_product_override` : Une table personnalisée pour stocker les paramètres d'exclusion par produit. (Probablement `id_product`, `excluded`).
  - `ps_llmstxtpro_category_override` : Une table personnalisée pour stocker les paramètres d'exclusion par catégorie. (Probablement `id_category`, `excluded`).
  - `ps_llmstxtpro_analytics_log` : Une table personnalisée pour stocker les journaux d'accès des robots (par exemple, `id_llmstxtpro_analytics_log`, `user_agent`, `access_time`, `file_type`).
  - `ps_llmstxtpro_urls` : Potentiellement une table pour mettre en cache les URL générées pour des raisons de performance, en particulier pour la génération de fichiers statiques. (Probablement `id_url`, `url`, `file_type`, `date_add`).
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Avant que le contrôleur d'administration ne rende son contenu. | Injecte les CSS/JS du module pour la configuration de l'administration, le tableau de bord et les champs supplémentaires des produits/catégories. |
| `displayAdminProductsExtra` | Sur la page d'édition de produit. | Rend la case à cocher "Exclure ce produit de LLMS.txt". |
| `displayAdminCategoriesExtra` | Sur la page d'édition de catégorie. | Rend la case à cocher "Exclure cette catégorie de LLMS.txt". |
| `actionModuleInstall` | Lors de l'installation du module. | Crée les tables de base de données, définit les valeurs de configuration par défaut. |
| `actionModuleUninstall` | Lors de la désinstallation du module. | Supprime les tables de base de données et les valeurs de configuration. |
| `displayHeader` | Dans la section `<head>` des pages front-office. | (Moins probable pour ce module, mais pourrait être utilisé pour des balises meta ou des liens spécifiques à l'IA si nécessaire). |
| `displayRightColumn` | Dans la colonne de droite des pages front-office. | (Non directement pertinent pour la génération de `llms.txt`). |
| `displayFooter` | Dans le pied de page des pages front-office. | (Non directement pertinent pour la génération de `llms.txt`). |
| `actionProductUpdate` | Après la mise à jour d'un produit. | Déclenche potentiellement une suppression du cache ou des indicateurs de régénération si `llms.txt` est dynamique. |
| `actionCategoryUpdate` | Après la mise à jour d'une catégorie. | Déclenche potentiellement une suppression du cache ou des indicateurs de régénération. |
| `actionObjectProductAddAfter` | Après l'ajout d'un nouveau produit. | Déclenche potentiellement une suppression du cache ou des indicateurs de régénération. |
| `actionObjectCategoryAddAfter` | Après l'ajout d'une nouvelle catégorie. | Déclenche potentiellement une suppression du cache ou des indicateurs de régénération. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour aider les marchands et les développeurs avec tout problème ou question concernant le module LLMS.txt Generator Pro.
