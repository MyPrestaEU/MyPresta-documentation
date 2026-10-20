---
title: "Presta Speed Cache - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module Presta Speed Cache de MyPresta.eu pour PrestaShop."
sidebar:
  label: "Presta Speed Cache - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Presta Speed Cache sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/presta-speed-cache.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/presta-speed-cache/)
>
> ---


# Presta Speed Cache

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5 (Le module est conçu pour fonctionner sur cette plage, assurant une large compatibilité tout en prenant en charge les dernières versions stables de PHP.)
- **Exigences d'hébergement** : Les extensions PHP standard comme cURL, JSON et OpenSSL sont requises, ce qui est généralement disponible sur la plupart des environnements d'hébergement modernes. Pour les méthodes de mise en cache avancées comme Redis ou Memcached, ces services doivent être installés et configurés sur votre serveur.

## 2. Présentation complète de la configuration (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est la zone de configuration principale de Presta Speed Cache. Vous y trouverez divers paramètres pour affiner le fonctionnement du cache de votre boutique.

#### Onglet Paramètres généraux

- **Activer le cache :**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal du module. Il active ou désactive la fonctionnalité de mise en cache pour l'ensemble de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module commencera à mettre en cache les pages et à les servir rapidement. Les performances de votre boutique s'amélioreront considérablement.
    - *Lorsqu'il est désactivé :* Le module arrêtera la mise en cache, et votre boutique reviendra à sa vitesse PrestaShop par défaut, qui est généralement plus lente.
  - **Valeur recommandée :** **OUI**. C'est la fonction principale du module.
  - **Scénario / exemple de marchand :** Vous venez d'installer le module et souhaitez activer les avantages de la vitesse. Réglez ceci sur OUI. Si vous dépannez un autre module et soupçonnez que la mise en cache pourrait interférer, vous pourriez le désactiver temporairement.
- **Durée de vie du cache (minutes) :**

  - **Ce que fait ce paramètre :** Détermine combien de temps une page mise en cache reste valide avant que le module ne la considère "obsolète" et la reconstruise.
  - **Effet de la modification de ce paramètre :**
    - *Valeur plus élevée (par exemple, 1440 pour 24 heures) :* Les pages sont servies depuis le cache plus longtemps, réduisant la charge du serveur mais pouvant potentiellement afficher un contenu légèrement obsolète si vous effectuez des modifications fréquentes (par exemple, des mises à jour de prix).
    - *Valeur plus faible (par exemple, 60 pour 1 heure) :* Les pages sont reconstruites plus souvent, assurant un contenu plus frais mais augmentant légèrement la charge du serveur.
  - **Valeur recommandée :** Commencez par **1440** (24 heures). Ajustez en fonction de la fréquence de modification de vos données produit.
  - **Scénario / exemple de marchand :** Si vous mettez à jour les prix ou les descriptions des produits quotidiennement, une durée de vie de 24 heures est acceptable. Si vous organisez des ventes flash avec des changements de prix horaires, vous pourriez réduire cela à 60 ou 120 minutes, ou vous fier aux fonctionnalités d'invalidation automatique.
- **Méthode de stockage du cache :**

  - **Ce que fait ce paramètre :** Sélectionne l'emplacement de stockage des pages mises en cache. Différentes méthodes offrent des niveaux de performance variés et nécessitent des configurations de serveur spécifiques.
  - **Effet de la modification de ce paramètre :**
    - *Système de fichiers (par défaut) :* Met en cache les pages sous forme de fichiers sur le disque de votre serveur. Le plus facile à configurer, bon pour la plupart des boutiques.
    - *Redis :* Stocke le cache en mémoire à l'aide du serveur Redis. Beaucoup plus rapide que le système de fichiers, idéal pour les boutiques à fort trafic. Nécessite que Redis soit installé et configuré sur votre serveur.
    - *Memcached :* Stocke le cache en mémoire à l'aide du serveur Memcached. Similaire à Redis en termes d'avantages de performance, nécessite également une configuration de serveur.
  - **Valeur recommandée :** Commencez par le **Système de fichiers**. Si vous avez une boutique à fort trafic et que votre hébergement le prend en charge, envisagez **Redis** ou **Memcached** pour des performances maximales.
  - **Scénario / exemple de marchand :** Votre boutique se développe rapidement et vous rencontrez des ralentissements occasionnels. Votre hébergeur propose Redis. Le passage à Redis peut améliorer considérablement les performances.
- **Exclure les URL du cache :**

  - **Ce que fait ce paramètre :** Vous permet de spécifier certaines pages ou sections de votre boutique qui ne devraient *jamais* être mises en cache. Ceci est utile pour les pages avec un contenu très dynamique ou sensible.
  - **Effet de la modification de ce paramètre :**
    - *Ajout d'URL :* Ces pages seront toujours générées à nouveau par PrestaShop, garantissant que leur contenu est toujours à jour, mais sacrifiant la vitesse pour ces pages spécifiques.
    - *Laisser vide :* Toutes les pages éligibles seront mises en cache.
  - **Valeur recommandée :** Laissez vide sauf si vous avez des besoins spécifiques. Utilisez avec prudence.
  - **Scénario / exemple de marchand :** Vous avez une page de "Demande de devis" personnalisée qui génère des formulaires uniques basés sur les entrées de l'utilisateur, ou une page avec des mises à jour de stock en temps réel à partir d'une API externe. Vous ajouteriez `/module/votremodule/page_devis` ou `/mises-a-jour-stock` à cette liste.
- **Pré-chauffage du cache :**

  - **Ce que fait ce paramètre :** "Visite" automatiquement les pages de votre boutique en arrière-plan pour pré-remplir le cache, garantissant que même le premier visiteur d'une page bénéficie des avantages de la vitesse.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Votre cache sera peuplé de manière proactive, ce qui entraînera des temps de chargement plus rapides pour tous les visiteurs, même ceux qui visitent une page pour la première fois après l'invalidation du cache. Cela peut légèrement augmenter la charge du serveur pendant le processus de pré-chauffage.
    - *Lorsqu'il est désactivé :* Les pages ne seront mises en cache qu'après la première visite du client.
  - **Valeur recommandée :** **OUI**. Cela garantit des avantages de vitesse maximaux pour tous les utilisateurs.
  - **Scénario / exemple de marchand :** Vous venez de vider votre cache ou de mettre à jour de nombreux produits. L'activation du pré-chauffage garantira que votre boutique est rapide pour les clients immédiatement, plutôt que d'attendre qu'ils visitent chaque page en premier.
- **Optimisation HTML :**

  - **Ce que fait ce paramètre :** Minifie la sortie HTML de vos pages en supprimant les espaces, commentaires et sauts de ligne inutiles. Cela réduit la taille du fichier de la page, ce qui accélère les téléchargements.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le code HTML de votre page sera plus compact, réduisant l'utilisation de la bande passante et accélérant légèrement le rendu de la page. C'est généralement sûr.
    - *Lorsqu'il est désactivé :* Le HTML sera servi tel que généré par PrestaShop, sans minification.
  - **Valeur recommandée :** **OUI**. C'est un gain de performance simple et sûr.
  - **Scénario / exemple de marchand :** Vous voulez tirer le maximum de performances de votre boutique. L'activation de cette option rendra votre HTML plus léger.

#### Onglet Blocs dynamiques

Cette section vous permet de définir des parties de votre page qui ne doivent *pas* être mises en cache, mais plutôt chargées dynamiquement après le chargement de la page principale. Ceci est crucial pour le contenu personnalisé comme le panier d'achat, le statut de connexion ou les sorties de modules spécifiques.

- **Activer les blocs dynamiques :**

  - **Ce que fait ce paramètre :** Active la possibilité de définir des zones spécifiques de votre page qui seront chargées séparément et dynamiquement, même lorsque le reste de la page est servi depuis le cache.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Vous pouvez configurer des modules ou des zones de contenu spécifiques pour qu'ils restent dynamiques, garantissant que le contenu personnalisé est toujours frais.
    - *Lorsqu'il est désactivé :* Tout le contenu sera mis en cache, ce qui pourrait entraîner un contenu dynamique obsolète (par exemple, un panier vide affiché même si des articles ont été ajoutés).
  - **Valeur recommandée :** **OUI**. C'est essentiel pour une boutique mise en cache fonctionnelle.
  - **Scénario / exemple de marchand :** Vous voulez que le panier de votre client affiche toujours le nombre correct d'articles, même si la page produit elle-même est mise en cache.
- **Liste des modules dynamiques :**

  - **Ce que fait ce paramètre :** Il s'agit d'une liste où vous sélectionnez les modules qui doivent *toujours* être rendus dynamiquement, même s'ils sont accrochés à une page mise en cache.
  - **Effet de la modification de ce paramètre :**
    - *Ajout d'un module :* La sortie de ce module sera récupérée à nouveau pour chaque utilisateur, garantissant que son contenu est toujours à jour (par exemple, bloc panier, bloc informations utilisateur).
    - *Suppression d'un module :* La sortie du module sera mise en cache avec le reste de la page, affichant potentiellement des données obsolètes.
  - **Valeur recommandée :** Incluez des modules comme `ps_shoppingcart`, `ps_customeraccountlinks`, `ps_languageselector`, `ps_currencyselector`, et tout autre module qui affiche des informations spécifiques à l'utilisateur ou en temps réel.
  - **Scénario / exemple de marchand :** Vous installez un nouveau module de "Chat en direct" qui doit afficher la disponibilité en temps réel. Vous l'ajouteriez à cette liste pour vous assurer qu'il est toujours dynamique.

#### Onglet Invalidation et purge

Cette section gère comment et quand le cache est vidé ou mis à jour, garantissant que vos clients voient toujours les dernières informations sur les produits.

- **Invalidation automatique du cache :**

  - **Ce que fait ce paramètre :** Lorsqu'il est activé, le module vide automatiquement les pages mises en cache pertinentes chaque fois que vous effectuez des modifications dans votre back office PrestaShop (par exemple, mise à jour d'un produit, d'une catégorie ou d'une page CMS).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Vous n'avez pas à vider manuellement le cache après chaque modification. Le module vide intelligemment uniquement les pages affectées, garantissant que les clients voient les mises à jour rapidement.
    - *Lorsqu'il est désactivé :* Vous devrez vider manuellement l'intégralité du cache après chaque modification importante, ou les clients pourraient voir un contenu obsolète jusqu'à l'expiration de la durée de vie du cache.
  - **Valeur recommandée :** **OUI**. C'est une fonctionnalité cruciale "configurez-le et oubliez-le" pour la fraîcheur des données.
  - **Scénario / exemple de marchand :** Vous mettez à jour le prix d'un produit. Avec l'invalidation automatique, la version mise en cache de cette page produit (et potentiellement de ses pages de catégorie) est vidée, de sorte que les clients voient immédiatement le nouveau prix.
- **Purger le cache lors de la mise à jour du produit :**

  - **Ce que fait ce paramètre :** Contrôle spécifiquement si le cache lié à un produit est vidé lorsque ce produit est mis à jour.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Garantit que toute page affichant le produit mis à jour (page produit, page de catégorie, résultats de recherche) est actualisée dans le cache.
    - *Lorsqu'il est désactivé :* Les mises à jour de produits pourraient ne pas se refléter sur les pages mises en cache avant l'expiration de la durée de vie du cache ou que vous ne le vidiez manuellement.
  - **Valeur recommandée :** **OUI**. Essentiel pour des informations produit précises.
  - **Scénario / exemple de marchand :** Vous modifiez l'image d'un produit. Ce paramètre garantit que la nouvelle image apparaît immédiatement sur la page produit.
- **Purger le cache lors de la mise à jour de la catégorie :**

  - **Ce que fait ce paramètre :** Contrôle si le cache lié à une catégorie est vidé lorsque cette catégorie est mise à jour.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Garantit que les pages de catégorie et potentiellement les pages de produits au sein de cette catégorie sont actualisées.
    - *Lorsqu'il est désactivé :* Les mises à jour de catégorie (par exemple, nom, description, produits assignés) pourraient ne pas se refléter sur les pages mises en cache.
  - **Valeur recommandée :** **OUI**. Important pour la navigation et l'exactitude du contenu des catégories.
  - **Scénario / exemple de marchand :** Vous renommez une catégorie. Cela garantit que le nouveau nom apparaît dans votre navigation et sur la page de catégorie.
- **Purger le cache lors de la mise à jour de la page CMS :**

  - **Ce que fait ce paramètre :** Contrôle si le cache lié à une page CMS est vidé lorsque cette page est mise à jour.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Garantit que les pages CMS mises à jour (par exemple, "À propos de nous", "Conditions générales") sont immédiatement actualisées.
    - *Lorsqu'il est désactivé :* Les mises à jour des pages CMS pourraient ne pas être visibles pour les clients avant l'expiration du cache.
  - **Valeur recommandée :** **OUI**. Important pour l'exactitude du contenu statique.
  - **Scénario / exemple de marchand :** Vous mettez à jour votre page "Politique d'expédition". Cela garantit que les clients voient la dernière version.

#### Onglet Paramètres avancés

- **Activer le mode débogage :**

  - **Ce que fait ce paramètre :** Active un mode spécial qui affiche des informations sur l'état du cache directement sur vos pages du front-office (visible uniquement par vous en tant qu'administrateur).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Vous verrez une petite superposition sur les pages de votre boutique indiquant si la page a été servie depuis le cache, quand elle a été mise en cache et d'autres détails de diagnostic. C'est inestimable pour le dépannage.
    - *Lorsqu'il est désactivé :* Aucune information de débogage n'est affichée.
  - **Valeur recommandée :** **NON** pour les boutiques en production. **OUI** lors de la configuration ou du dépannage.
  - **Scénario / exemple de marchand :** Vous venez de configurer le module et souhaitez vérifier que les pages sont bien mises en cache correctement. Activez le mode débogage, naviguez sur votre boutique et vérifiez la superposition.
- **Activer le débogage en direct :**

  - **Ce que fait ce paramètre :** Fournit un tableau de bord en temps réel dans le back office pour surveiller les succès, les échecs du cache et d'autres métriques de performance.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Vous avez accès à un outil de surveillance puissant pour voir l'efficacité de votre cache.
    - *Lorsqu'il est désactivé :* Aucune statistique de cache en direct n'est collectée ou affichée.
  - **Valeur recommandée :** **OUI** si vous souhaitez surveiller activement les performances. Peut être désactivé si vous préférez une surcharge minimale.
  - **Scénario / exemple de marchand :** Vous souhaitez voir l'impact de votre stratégie de mise en cache au fil du temps, en observant combien de requêtes sont servies depuis le cache par rapport à celles qui sont générées à nouveau.
- **Activer SWR (Stale-While-Revalidate) :**

  - **Ce que fait ce paramètre :** Une stratégie de mise en cache avancée où, si une page mise en cache est expirée, le module sert immédiatement la version *obsolète* (expirée) à l'utilisateur tout en reconstruisant simultanément une nouvelle version en arrière-plan.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les utilisateurs obtiennent presque toujours un chargement de page instantané, même si le cache est expiré. La page peut être légèrement obsolète pendant un instant, mais elle est incroyablement rapide. La nouvelle version remplace l'ancienne pour les visiteurs suivants.
    - *Lorsqu'il est désactivé :* Lorsqu'une page mise en cache expire, le visiteur suivant attendra que la page soit reconstruite, ce qui peut entraîner un léger délai.
  - **Valeur recommandée :** **OUI**. Cela offre le meilleur équilibre entre vitesse et fraîcheur pour la plupart des boutiques.
  - **Scénario / exemple de marchand :** Vous voulez vous assurer que vos clients ne subissent jamais un chargement lent, même si le cache doit être mis à jour. SWR offre cette expérience "toujours rapide".
- **Mettre en cache pour les utilisateurs connectés :**

  - **Ce que fait ce paramètre :** Détermine si les pages doivent être mises en cache même pour les clients qui sont connectés à leur compte.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les utilisateurs connectés bénéficieront également des pages mises en cache, mais le module doit être très intelligent concernant les blocs dynamiques pour garantir que le contenu personnalisé (comme les liens "Mon compte", l'historique des commandes) reste correct.
    - *Lorsqu'il est désactivé :* Les utilisateurs connectés recevront toujours des pages fraîches, non mises en cache. Cela garantit une personnalisation parfaite mais sacrifie la vitesse pour ces utilisateurs.
  - **Valeur recommandée :** **OUI**, mais assurez-vous que vos blocs dynamiques sont correctement configurés pour des modules comme `ps_customeraccountlinks`.
  - **Scénario / exemple de marchand :** Vous voulez que vos clients fidèles et connectés bénéficient également d'une expérience ultra-rapide, pas seulement les invités.
- **Mettre en cache pour les appareils mobiles :**

  - **Ce que fait ce paramètre :** Contrôle si des versions mises en cache séparées des pages sont générées et servies pour les appareils mobiles.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module créera et servira des pages mises en cache optimisées spécifiquement pour les utilisateurs mobiles, ce qui est crucial si votre thème présente des différences significatives entre les mises en page de bureau et mobiles.
    - *Lorsqu'il est désactivé :* Les utilisateurs mobiles recevront soit la version mise en cache de bureau (le cas échéant), soit des pages non mises en cache, ce qui pourrait entraîner un contenu plus lent ou mal rendu.
  - **Valeur recommandée :** **OUI** si votre thème est responsive et s'affiche différemment pour les mobiles.
  - **Scénario / exemple de marchand :** Votre thème utilise des modèles ou des CSS différents pour les mobiles. La mise en cache pour les mobiles garantit qu'ils obtiennent la version correcte et rapide.
- **Activer la purge Edge (Varnish/CDN) :**

  - **Ce que fait ce paramètre :** S'intègre aux systèmes de mise en cache externes comme Varnish ou les réseaux de diffusion de contenu (CDN) pour envoyer des requêtes de purge lorsque votre cache PrestaShop est invalidé. Cela garantit que le CDN vide également son ancien contenu.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Votre CDN servira toujours le contenu le plus frais après vos mises à jour, empêchant les clients de voir d'anciennes versions stockées par le CDN.
    - *Lorsqu'il est désactivé :* Votre CDN pourrait continuer à servir un ancien contenu même après la purge de votre cache PrestaShop, entraînant des incohérences.
  - **Valeur recommandée :** **OUI** si vous utilisez Varnish ou un CDN (comme Cloudflare, Akamai, etc.) qui prend en charge la purge du cache via API.
  - **Scénario / exemple de marchand :** Vous utilisez Cloudflare pour les performances. Lorsque vous mettez à jour un produit, ce paramètre indique à Cloudflare de vider son cache pour ce produit, afin que tous les utilisateurs voient la mise à jour immédiatement.

#### Onglet Outils

Cet onglet fournit des actions manuelles pour la gestion de votre cache.

- **Vider tout le cache :**

  - **Ce que fait ce paramètre :** Ce bouton supprime immédiatement toutes les pages mises en cache générées par Presta Speed Cache.
  - **Effet de la modification de ce paramètre :** Tout le contenu mis en cache est supprimé. La prochaine fois qu'une page est visitée, elle sera générée à nouveau par PrestaShop puis remise en cache. Cela ralentira temporairement votre site jusqu'à ce que le cache se reconstruise.
  - **Valeur recommandée :** Utilisez uniquement lorsque cela est nécessaire (par exemple, après une mise à jour majeure du thème, l'installation d'un module, ou si vous suspectez des problèmes de cache).
  - **Scénario / exemple de marchand :** Vous avez apporté des modifications importantes au CSS de votre thème et souhaitez vous assurer que tous les visiteurs voient le nouveau design immédiatement. Cliquez sur "Vider tout le cache".
- **Lancer le pré-chauffage du cache :**

  - **Ce que fait ce paramètre :** Déclenche manuellement le processus de pré-chauffage du cache, qui visite les pages de votre boutique pour pré-remplir le cache.
  - **Effet de la modification de ce paramètre :** Le module commencera à générer des versions mises en cache de vos pages en arrière-plan. Cela peut prendre un certain temps en fonction de la taille de votre boutique et peut consommer des ressources serveur pendant le processus.
  - **Valeur recommandée :** Utilisez après avoir vidé le cache ou après des importations majeures de produits/catégories pour reconstruire rapidement le cache.
  - **Scénario / exemple de marchand :** Vous venez de vider le cache et souhaitez que votre boutique soit rapide pour les clients le plus rapidement possible.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 Gestion du cache (Back Office > Presta Speed Cache > Gestion du cache)

Cet écran fournit un aperçu détaillé et une interface de gestion pour vos pages mises en cache.

- **Nom de l'écran et emplacement du menu :** Vous pouvez le trouver en naviguant vers **Presta Speed Cache** dans votre menu principal du back office PrestaShop, puis en sélectionnant **Gestion du cache**.
- **Actions et paramètres disponibles :**
  - **Grille de liste du cache :** Ce tableau affiche une liste des pages actuellement mises en cache, y compris des détails tels que l'URL, la date de la dernière mise en cache, sa taille et son statut actuel (par exemple, actif, expiré).
  - **Filtrer et rechercher :** Vous pouvez filtrer la liste par URL, statut ou d'autres critères pour trouver des entrées de cache spécifiques.
  - **Vider le cache sélectionné :** Vous permet de sélectionner des pages mises en cache spécifiques dans la liste et de les vider individuellement.
  - **Vider tout le cache (bouton) :** Un bouton proéminent pour vider l'intégralité du cache, similaire à celui de la page de configuration principale.
  - **Lancer le pré-chauffage (bouton) :** Un bouton proéminent pour lancer manuellement le processus de pré-chauffage du cache.
- **Effet des modifications :**
  - *Vidage des entrées individuelles :* Seules les pages sélectionnées seront supprimées du cache, leur permettant d'être reconstruites lors de la prochaine visite. Ceci est utile pour des mises à jour ciblées sans affecter l'ensemble de la boutique.
  - *Vidage de tout le cache :* Réinitialise l'intégralité du cache, forçant toutes les pages à être reconstruites.
  - *Lancement du pré-chauffage :* Remplit le cache de manière proactive, garantissant un chargement plus rapide pour les visiteurs suivants.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Utilisez cet écran pour surveiller votre cache, identifier les pages qui pourraient ne pas être mises en cache correctement, ou pour effectuer des purges de cache ciblées si vous avez effectué une mise à jour très spécifique que l'invalidation automatique aurait pu manquer.

#### 2.2.2 Tableau de bord (Back Office > Presta Speed Cache > Tableau de bord)

Cet écran fournit un aperçu visuel des performances et des statistiques de votre cache.

- **Nom de l'écran et emplacement du menu :** Vous pouvez le trouver en naviguant vers **Presta Speed Cache** dans votre menu principal du back office PrestaShop, puis en sélectionnant **Tableau de bord**.
- **Actions et paramètres disponibles :**
  - **Métriques de performance :** Affiche des graphiques et des statistiques sur les succès du cache, les échecs du cache, les temps de chargement moyens des pages (avec et sans cache) et d'autres indicateurs de performance pertinents.
  - **État de santé du cache :** Fournit un aperçu rapide de la santé du système de cache, indiquant s'il y a des problèmes ou s'il fonctionne de manière optimale.
  - **Événements d'invalidation récents :** Affiche un journal des invalidations de cache récentes, vous aidant à suivre quand et pourquoi des parties de votre cache ont été vidées.
- **Effet des modifications :** Cet écran est principalement destiné à la surveillance et au reporting. Aucune modification directe de la configuration du cache n'est effectuée ici, mais il vous aide à comprendre l'impact de vos paramètres.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vérifiez régulièrement le tableau de bord pour vous assurer que votre cache fonctionne comme prévu. Recherchez des taux de succès du cache élevés et des temps de chargement faibles. Si vous constatez une baisse soudaine des succès du cache ou une augmentation des temps de chargement, cela pourrait indiquer un problème de configuration ou un problème avec votre serveur.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activer le cache | OUI | Interrupteur principal pour la mise en cache. OUI = boutique plus rapide. |
|  | Durée de vie du cache (minutes) | 1440 (24 heures) | Combien de temps une page reste en cache. Plus élevé = moins de charge serveur, contenu potentiellement plus ancien. |
|  | Méthode de stockage du cache | Système de fichiers | Où le cache est stocké. Système de fichiers (facile), Redis/Memcached (plus rapide, nécessite une configuration serveur). |
|  | Exclure les URL du cache | Vide | URL qui ne doivent jamais être mises en cache (par exemple, pages très dynamiques). |
|  | Pré-chauffage du cache | OUI | Construit le cache de manière proactive en arrière-plan. OUI = plus rapide pour les premiers visiteurs. |
|  | Optimisation HTML | OUI | Minifie le HTML pour des pages plus petites. OUI = léger gain de vitesse. |
|  | Activer les blocs dynamiques | OUI | Permet à un contenu spécifique (panier, connexion) de rester dynamique. OUI = essentiel pour le contenu personnalisé. |
|  | Liste des modules dynamiques | `ps_shoppingcart`, `ps_customeraccountlinks`, etc. | Modules qui doivent toujours être dynamiques. |
|  | Invalidation automatique du cache | OUI | Vide le cache pertinent lors des modifications du back office. OUI = contenu frais sans intervention manuelle. |
|  | Purger le cache lors de la mise à jour du produit | OUI | Vide le cache lié au produit lorsque les produits sont mis à jour. |
|  | Purger le cache lors de la mise à jour de la catégorie | OUI | Vide le cache lié à la catégorie lorsque les catégories sont mises à jour. |
|  | Purger le cache lors de la mise à jour de la page CMS | OUI | Vide le cache lié à la page CMS lorsque les pages CMS sont mises à jour. |
|  | Activer le mode débogage | NON (OUI pour le dépannage) | Affiche les informations du cache sur le front office. |
|  | Activer le débogage en direct | OUI | Fournit des statistiques de cache en temps réel dans le BO. |
|  | Activer SWR (Stale-While-Revalidate) | OUI | Sert le cache obsolète tout en reconstruisant le frais. OUI = toujours rapide. |
|  | Mettre en cache pour les utilisateurs connectés | OUI | Met en cache les pages pour les utilisateurs connectés. |
|  | Mettre en cache pour les appareils mobiles | OUI | Met en cache des versions séparées pour les mobiles. |
|  | Activer la purge Edge (Varnish/CDN) | NON (OUI si utilisation d'un CDN) | S'intègre avec un CDN/Varnish externe pour la purge du cache. |
|  | Vider tout le cache (bouton) | Utiliser si nécessaire | Vide manuellement l'intégralité du cache. |
|  | Lancer le pré-chauffage du cache (bouton) | Utiliser si nécessaire | Déclenche manuellement le pré-remplissage du cache. |
| **Écran de gestion du cache** | Grille de liste du cache | N/A | Affiche et permet la gestion des pages mises en cache individuelles. |
|  | Vider le cache sélectionné | N/A | Vide les entrées de cache spécifiques. |
| **Écran du tableau de bord** | Métriques de performance | N/A | Visualise les succès, les échecs du cache et les temps de chargement. |
|  | État de santé du cache | N/A | Affiche l'état de santé général du système de mise en cache. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : Ma boutique semble cassée ou affiche un ancien contenu après avoir activé le cache. Que dois-je faire ?**
R : Tout d'abord, essayez de vider l'intégralité de votre cache à l'aide du bouton "Vider tout le cache" dans la configuration du module ou sur l'écran "Gestion du cache". Videz également le cache de votre navigateur. Si le problème persiste, vérifiez votre "Liste des modules dynamiques" pour vous assurer que tous les modules affichant du contenu personnalisé ou en temps réel sont inclus. Désactivez temporairement l'"Optimisation HTML" pour voir si cela cause des conflits.

**Q : Mon panier d'achat ne se met pas à jour correctement, ou les utilisateurs semblent parfois déconnectés.**
R : Cela est presque toujours dû au fait que le contenu dynamique n'est pas correctement exclu de la mise en cache. Allez dans l'onglet "Blocs dynamiques" et assurez-vous que les modules comme `ps_shoppingcart`, `ps_customeraccountlinks`, `ps_languageselector` et `ps_currencyselector` sont ajoutés à la "Liste des modules dynamiques". Si vous avez d'autres modules personnalisés qui affichent des données spécifiques à l'utilisateur, ajoutez-les également.

**Q : Mon site web est toujours lent, même avec le module activé.**
R :

1. **Vérifier le mode débogage :** Activez le "Mode débogage" (dans les Paramètres avancés) et naviguez sur votre front office. Indique-t-il que les pages sont servies depuis le cache ("Cache HIT") ? Si vous voyez "Cache MISS", les pages ne sont pas mises en cache.
2. **Vérifier le taux de succès du cache :** Vérifiez le "Tableau de bord" pour votre taux de succès du cache. S'il est faible, examinez vos paramètres "Durée de vie du cache" et "Exclure les URL".
3. **Ressources serveur :** Bien que la mise en cache réduise la charge, votre serveur a toujours besoin de ressources adéquates. Vérifiez votre plan d'hébergement et les journaux du serveur pour d'autres goulots d'étranglement.
4. **Autres optimisations :** La mise en cache est une partie de la vitesse. Assurez-vous que vos images sont optimisées, que votre thème est efficace et que vous n'exécutez pas trop de modules lourds et non optimisés.

**Q : Comment m'assurer que ma boutique multilingue ou multidevise fonctionne correctement avec la mise en cache ?**
R : Presta Speed Cache est conçu pour gérer les boutiques multilingues et multidevises en générant des entrées de cache distinctes pour chaque combinaison. Assurez-vous que vos modules de sélection de langue et de devise sont ajoutés à la "Liste des modules dynamiques". Si vous remarquez des problèmes, activez "Mettre en cache pour les utilisateurs connectés" et "Mettre en cache pour les appareils mobiles" si applicable, car ceux-ci peuvent également affecter la façon dont les différentes versions des pages sont mises en cache.

**Q : J'ai mis à jour un produit, mais les anciennes informations s'affichent toujours sur le front office.**
R :

1. **Invalidation automatique :** Assurez-vous que l'"Invalidation automatique du cache" et la "Purge du cache lors de la mise à jour du produit" sont activées dans l'onglet "Invalidation et purge".
2. **Vidage manuel :** Si les paramètres sont corrects, essayez de vider manuellement le cache pour cette page produit spécifique depuis l'écran "Gestion du cache", ou videz l'intégralité du cache.
3. **CDN/Varnish :** Si vous utilisez un CDN ou Varnish, assurez-vous que l'"Activer la purge Edge" est configuré correctement, car votre CDN pourrait servir une ancienne version.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Presta Speed Cache est une solution de mise en cache hautement optimisée pour PrestaShop, employant une architecture sophistiquée pour offrir de la vitesse sans compromettre le contenu dynamique. Il tire parti du modèle MVC de PrestaShop en surchargeant les classes de base (`Controller`, `FrontController`, `Dispatcher`, `Hook`) pour intercepter les requêtes et les réponses, servant le HTML mis en cache lorsqu'il est disponible. Il utilise un moteur de stockage flexible (Fichier, Redis, Memcached) et implémente des fonctionnalités avancées comme SWR (Stale-While-Revalidate), le rendu de blocs dynamiques via AJAX et l'invalidation intelligente du cache. La conception du module se concentre sur une surcharge minimale et une compatibilité maximale, offrant une couche de mise en cache robuste et extensible.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs gèrent des requêtes AJAX spécifiques ou des tâches d'arrière-plan liées à la mise en cache.

- `prestaspeedcache/controllers/front/api.php`
  - **Nom de la classe et classe parente :** `PrestaSpeedCacheApiModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Gère les requêtes API, principalement pour la récupération de contenu dynamique. Lorsqu'une page mise en cache est servie et qu'elle contient des blocs dynamiques, ce contrôleur est responsable de la livraison du HTML frais pour ces blocs via AJAX. Il reçoit des paramètres identifiant le module et le hook, rend le module et renvoie le HTML.
- `prestaspeedcache/controllers/front/cron.php`
  - **Nom de la classe et classe parente :** `PrestaSpeedCacheCronModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Conçu pour être appelé par une tâche cron côté serveur. Il déclenche des tâches d'arrière-plan telles que le pré-chauffage du cache, le traitement de la file d'attente d'invalidation et d'autres opérations de maintenance. Cela décharge le traitement lourd des requêtes utilisateur.
- `prestaspeedcache/controllers/front/dynamic.php`
  - **Nom de la classe et classe parente :** `PrestaSpeedCacheDynamicModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Similaire à `api.php`, ce contrôleur gère spécifiquement les requêtes pour les blocs de contenu dynamique qui sont chargés de manière asynchrone dans les pages mises en cache. Il garantit que les éléments personnalisés comme le panier ou les informations utilisateur sont toujours à jour.
- `prestaspeedcache/controllers/front/index.php`
  - **Nom de la classe et classe parente :** `PrestaSpeedCacheIndexModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Un contrôleur frontal de substitution ou de secours. Dans de nombreux modules, `index.php` dans `controllers/front` sert de point d'entrée par défaut si aucun autre contrôleur spécifique n'est trouvé. Il peut gérer le routage de base au niveau du module ou simplement rediriger.

#### Contrôleurs d'administration Back-Office

Ces contrôleurs gèrent la configuration et les données du module dans le Back Office de PrestaShop.

- `prestaspeedcache/controllers/admin/AdminPrestaSpeedCacheController.php`
  - **Nom de la classe et classe parente :** `AdminPrestaSpeedCacheController` étend `ModuleAdminController`.
  - **Nom de l'onglet et entité gérée :** Il s'agit du contrôleur administratif principal du module, gérant les entrées de cache et fournissant les vues "Gestion du cache" et "Tableau de bord". Il gère la liste, le filtrage et la suppression des entrées de cache. Il ne gère pas directement une entité `ObjectModel` spécifique, mais interagit plutôt avec le `PscCacheRepository` pour les opérations de cache.
- `prestaspeedcache/controllers/admin/index.php`
  - **Nom de la classe et classe parente :** `AdminPrestaSpeedCacheIndexController` étend `ModuleAdminController`.
  - **Nom de l'onglet et entité gérée :** Similaire à `index.php` du front-office, il s'agit probablement d'un contrôleur de substitution ou par défaut pour la section d'administration du module, garantissant un point d'entrée valide si aucune action spécifique n'est demandée.

### 4.3 Classes et modèles de base (`classes/`)

Le répertoire `classes/` du module contient la logique de base, les services et les structures de données.

- `prestaspeedcache/classes/PscAdminChips.php` : Gère les composants de l'interface utilisateur pour l'interface d'administration.
- `prestaspeedcache/classes/PscAfterDefaults.php` : Gère les paramètres par défaut ou les configurations post-installation.
- `prestaspeedcache/classes/PscAutoload.php` : Autoloader personnalisé pour les classes du module.
- `prestaspeedcache/classes/PscCacheEngine.php` : Le moteur de mise en cache principal, orchestrant les opérations de cache.
- `prestaspeedcache/classes/PscCacheInvalidator.php` : Gère la logique d'invalidation des pages mises en cache en fonction des actions du back office.
- `prestaspeedcache/classes/PscCacheKey.php` : Génère des clés uniques pour les entrées mises en cache basées sur l'URL, le contexte, etc.
- `prestaspeedcache/classes/PscCacheLock.php` : Implémente des mécanismes de verrouillage pour éviter les conditions de concurrence lors de la génération du cache.
- `prestaspeedcache/classes/PscCacheRepository.php` : Gère l'interaction avec le stockage du cache, fournissant une couche d'abstraction.
- `prestaspeedcache/classes/PscCacheStorage.php` : Classe de base abstraite ou interface pour les implémentations de stockage du cache.
- `prestaspeedcache/classes/PscCacheTags.php` : Gère les balises de cache pour une invalidation granulaire (par exemple, toutes les pages liées à l'ID produit 123).
- `prestaspeedcache/classes/PscConfig.php` : Gère les paramètres de configuration du module (lit et écrit dans `ps_configuration`).
- `prestaspeedcache/classes/PscDynamicBlocks.php` : Logique pour identifier et gérer les blocs de contenu dynamique.
- `prestaspeedcache/classes/PscDynamicModules.php` : Gère la liste des modules dont la sortie doit toujours être dynamique.
- `prestaspeedcache/classes/PscEdgePurge.php` : Gère l'intégration avec des systèmes de mise en cache externes (Varnish, CDN) pour la purge.
- `prestaspeedcache/classes/PscFrontAssign.php` : Gère les affectations de variables Smarty pour les modèles du front-office.
- `prestaspeedcache/classes/PscFrontDebug.php` : Logique pour afficher les informations de débogage sur le front office.
- `prestaspeedcache/classes/PscHealth.php` : Fournit des méthodes pour vérifier la santé et l'état du système de mise en cache.
- `prestaspeedcache/classes/PscHtmlOptimizer.php` : Implémente la logique de minification HTML.
- `prestaspeedcache/classes/PscHttpProbe.php` : Utilisé pour les requêtes HTTP internes, par exemple pour le pré-chauffage du cache.
- `prestaspeedcache/classes/PscInstaller.php` : Gère les routines d'installation et de désinstallation du module (tables de base de données, hooks, valeurs par défaut de la configuration).
- `prestaspeedcache/classes/PscInvalidationQueue.php` : Gère une file d'attente de pages à invalider, souvent traitée par cron.
- `prestaspeedcache/classes/PscLiveDebug.php` : Fournit des capacités de débogage et de surveillance en temps réel.
- `prestaspeedcache/classes/PscMetrics.php` : Collecte et rapporte les métriques de performance pour le tableau de bord.
- `prestaspeedcache/classes/PscOps.php` : Méthodes utilitaires opérationnelles générales.
- `prestaspeedcache/classes/PscPresets.php` : Gère les configurations de mise en cache prédéfinies ou les préréglages.
- `prestaspeedcache/classes/PscRequestGuard.php` : Protège contre les requêtes malveillantes ou assure un traitement correct des requêtes.
- `prestaspeedcache/classes/PscTiming.php` : Utilitaire pour mesurer les temps d'exécution.
- `prestaspeedcache/classes/PscTranslate.php` : Gère les traductions du module.
- `prestaspeedcache/classes/PscWarmup.php` : Implémente la logique de pré-chauffage du cache.
- `prestaspeedcache/classes/PscWizard.php` : Guide les utilisateurs à travers la configuration initiale.
- `prestaspeedcache/classes/storage/PscFileStorage.php` : Implémentation concrète pour le stockage du cache basé sur des fichiers.
- `prestaspeedcache/classes/storage/PscMemcachedStorage.php` : Implémentation concrète pour le stockage du cache Memcached.
- `prestaspeedcache/classes/storage/PscRedisStorage.php` : Implémentation concrète pour le stockage du cache Redis.
- `prestaspeedcache/classes/storage/PscStorageFactory.php` : Modèle de fabrique pour créer des instances de stockage de cache appropriées.
- `prestaspeedcache/classes/storage/PscStorageInterface.php` : Interface définissant les méthodes pour les implémentations de stockage du cache.

#### Surcharges (Overrides)

Le module utilise des surcharges pour s'intégrer profondément au comportement de base de PrestaShop.

- `prestaspeedcache/override/classes/controller/Controller.php` : Surcharge la classe de base `Controller`, permettant au module d'intercepter le processus de rendu pour le front et le back office, injectant potentiellement une logique de mise en cache ou des marqueurs de blocs dynamiques.
- `prestaspeedcache/override/classes/controller/FrontController.php` : Surcharge `FrontController` pour gérer spécifiquement les requêtes de pages du front-office, permettant au module de servir du contenu mis en cache ou de préparer les pages pour la mise en cache.
- `prestaspeedcache/override/classes/Dispatcher.php` : Surcharge le `Dispatcher` pour contrôler la façon dont les URL sont routées et traitées, redirigeant potentiellement vers du contenu mis en cache ou déclenchant la génération du cache.
- `prestaspeedcache/override/classes/Hook.php` : Surcharge la classe `Hook` pour permettre le rendu dynamique des modules dans les pages mises en cache, garantissant que des hooks spécifiques sont toujours exécutés à nouveau.

### 4.4 Actifs JavaScript (`views/js/`)

Ces scripts améliorent l'expérience utilisateur dans le front et le back office.

- `prestaspeedcache/views/js/admin.js` :
  - **Portée :** Back-office.
  - **Détails :** Gère les éléments interactifs dans la configuration d'administration du module, tels que le changement d'onglet, les soumissions de formulaires, les appels AJAX pour vider le cache, lancer le pré-chauffage et les mises à jour dynamiques du tableau de bord ou de la liste du cache.
- `prestaspeedcache/views/js/after/lang-currency.js` :
  - **Portée :** Front-office.
  - **Détails :** Probablement un petit script exécuté après le chargement de la page principale, spécifiquement conçu pour garantir que les sélecteurs de langue et de devise (qui sont souvent dynamiques) fonctionnent correctement dans un contexte de page mise en cache. Il pourrait réinitialiser leur comportement ou s'assurer que leur état est cohérent.
- `prestaspeedcache/views/js/dynamic.js` :
  - **Portée :** Front-office.
  - **Détails :** Il s'agit d'un script critique pour les blocs dynamiques. Il identifie les espaces réservés pour le contenu dynamique dans une page mise en cache, effectue des requêtes AJAX (vers les contrôleurs `api.php` ou `dynamic.php`) pour récupérer le HTML frais de ces blocs, puis injecte le contenu dans le DOM. Il garantit que des éléments comme le panier, le statut de connexion, etc., sont toujours à jour.
- `prestaspeedcache/views/js/fo_debug.js` :
  - **Portée :** Front-office (administrateur uniquement lorsque le mode débogage est activé).
  - **Détails :** Affiche la superposition de débogage du cache sur le front office. Il récupère les informations d'état du cache (succès/échec, horodatage, etc.) et les affiche dans un élément visible et non intrusif pour les administrateurs.
- `prestaspeedcache/views/js/psc-dom-mock.js` :
  - **Portée :** Front-office.
  - **Détails :** Potentiellement un script utilitaire qui fournit une couche légère de manipulation ou de simulation du DOM, éventuellement utilisée pendant le processus d'injection de blocs dynamiques pour assurer la compatibilité ou optimiser le rendu.

### 4.5 Feuilles de style CSS (`views/css/`)

- `prestaspeedcache/views/css/admin.css` :
  - **Portée :** Style du formulaire d'administration du back-office.
  - **Détails :** Style les pages de configuration du module, le tableau de bord et les grilles de gestion du cache. Il assure une interface cohérente et conviviale dans le back office de PrestaShop.
  - **Sélecteurs de classe CSS clés :** `prestaspeedcache-dashboard`, `prestaspeedcache-config-form`, `prestaspeedcache-table`, `psc-debug-overlay`.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles d'administration (`views/templates/admin/`)

Ces modèles sont utilisés pour l'interface du back-office du module.

- `prestaspeedcache/views/templates/admin/cache_list.tpl` : Rend le tableau et l'interface pour lister et gérer les pages mises en cache.
- `prestaspeedcache/views/templates/admin/configure.tpl` : Le formulaire de configuration principal du module, contenant tous les paramètres décrits dans la Section 4.1.
- `prestaspeedcache/views/templates/admin/dashboard.tpl` : Affiche les métriques de performance, les graphiques et l'état de santé du cache.
- `prestaspeedcache/views/templates/admin/dynamic_modules.tpl` : L'interface pour sélectionner et gérer les modules qui doivent être rendus dynamiquement.
- `prestaspeedcache/views/templates/admin/live_debug.tpl` : Rend le panneau d'informations de débogage en temps réel dans le back office.
- `prestaspeedcache/views/templates/admin/ops.tpl` : Contient probablement des modèles pour les outils ou actions opérationnels (par exemple, vidage manuel du cache, pré-chauffage).
- `prestaspeedcache/views/templates/admin/tabs.tpl` : Rend la structure de navigation par onglets pour les pages de configuration du module.
- `prestaspeedcache/views/templates/admin/wizard.tpl` : Modèle pour l'assistant de configuration initiale, guidant les utilisateurs à travers la configuration de base.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

Le module utilise principalement la table `ps_configuration` de PrestaShop pour ses paramètres. Pour le stockage du cache, il utilise soit le système de fichiers, soit des services externes (Redis/Memcached). Il peut créer des tables personnalisées pour :

- `ps_prestaspeedcache_cache_tags` : Stocke les relations entre les pages mises en cache et leurs balises associées (par exemple, ID de produit, ID de catégorie) pour une invalidation efficace.
- `ps_prestaspeedcache_invalidation_queue` : Stocke une liste de pages ou de balises qui doivent être invalidées, traitées de manière asynchrone.
- `ps_prestaspeedcache_metrics` : Stocke les métriques de performance pour le tableau de bord.

#### Tableau des hooks enregistrés

Le module enregistre divers hooks pour s'intégrer au cycle de vie de PrestaShop.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Avant le rendu du contenu de la page dans l'en-tête. | Injection de JavaScript du front-office (par exemple, `dynamic.js`, `fo_debug.js`), configuration du contexte initial du cache. |
| `displayFooter` | Avant la balise `</body>` de fermeture. | Injection de scripts supplémentaires, d'informations de débogage ou finalisation des opérations de cache. |
| `displayLeftColumn` | Dans la colonne de gauche du thème. | Potentiellement utilisé pour le rendu dynamique de modules si un module de la colonne de gauche est marqué comme dynamique. |
| `displayRightColumn` | Dans la colonne de droite du thème. | Potentiellement utilisé pour le rendu dynamique de modules si un module de la colonne de droite est marqué comme dynamique. |
| `displayProductAdditionalInfo` | Sur la page produit, sous la description du produit. | Si un module accroché ici est dynamique, son contenu sera récupéré séparément. |
| `actionFrontControllerSetMedia` | Après que les médias (JS/CSS) ont été définis par le contrôleur frontal. | Ajout de JS/CSS spécifiques au module à la page. |
| `actionFrontControllerInit` | Au début de l'exécution d'un contrôleur frontal. | Interception des requêtes pour vérifier le contenu mis en cache ou préparer la mise en cache. |
| `actionDispatcherBefore` | Avant que le dispatcher ne traite la requête. | Interception précoce pour servir le contenu mis en cache ou contourner le dispatching. |
| `actionDispatcherAfter` | Après que le dispatcher a traité la requête. | Finalisation de la génération du cache pour la page actuelle. |
| `actionObjectUpdate` | Lorsqu'un `ObjectModel` est mis à jour (par exemple, Produit, Catégorie, CMS). | Déclenchement de l'invalidation du cache pour les pages affectées. |
| `actionObjectAdd` | Lorsqu'un `ObjectModel` est ajouté. | Déclenchement de l'invalidation du cache pour les pages potentiellement affectées. |
| `actionObjectDelete` | Lorsqu'un `ObjectModel` est supprimé. | Déclenchement de l'invalidation du cache pour les pages affectées. |
| `actionProductUpdate` | Spécifique aux mises à jour de produits. | Invalidation granulaire du cache pour les pages produits. |
| `actionCategoryUpdate` | Spécifique aux mises à jour de catégories. | Invalidation granulaire du cache pour les pages de catégories. |
| `actionCmsUpdate` | Spécifique aux mises à jour de pages CMS. | Invalidation granulaire du cache pour les pages CMS. |
| `actionClearCache` | Lorsque le cache natif de PrestaShop est vidé. | Synchronisation du vidage du cache du module avec celui de PrestaShop. |
| `actionModuleInstall` | Lorsqu'un module est installé. | Potentiellement vidage du cache ou mise à jour de la liste des modules dynamiques. |
| `actionModuleUninstall` | Lorsqu'un module est désinstallé. | Vidage du cache ou suppression du module de la liste dynamique. |
| `actionAdminControllerSetMedia` | Dans les contrôleurs d'administration, après la définition des médias. | Injection de JS/CSS spécifiques à l'administration. |
| `actionAdminControllerPreProcess` | Avant qu'un contrôleur d'administration ne traite sa requête. | Configuration du contexte d'administration pour le module. |
| `actionAdminControllerPostProcess` | Après qu'un contrôleur d'administration a traité sa requête. | Gestion du post-traitement pour les actions d'administration. |
| `actionOutputHTMLBefore` | Avant que la sortie HTML finale ne soit envoyée au navigateur. | Optimisation HTML (minification). |
| `actionOutputHTMLAfter` | Après que la sortie HTML finale est envoyée. | Finalisation du stockage du cache. |
| `actionAjaxDie` | Lorsqu'une requête AJAX appelle `die()`. | Assurer une gestion correcte du cache pour les réponses AJAX. |
| `actionGetContent` | Pour la page de configuration principale du module. | Rendu du formulaire de configuration du module. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à fournir une assistance complète pour garantir que votre module Presta Speed Cache fonctionne de manière optimale.
