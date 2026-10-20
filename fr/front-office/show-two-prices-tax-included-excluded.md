---
title: "Afficher deux prix - TTC / HT - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Afficher deux prix - TTC / HT' par MyPresta.eu."
sidebar:
  label: "Afficher deux prix - TTC / HT - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Show two prices - tax included / excluded sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/show-two-prices-tax-included-excluded.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/show-two-prices-tax-included-excluded/)
>
> ---


# Afficher deux prix - TTC / HT

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises pour PrestaShop lui-même et généralement pour le fonctionnement des modules. Aucune exigence d'hébergement spéciale au-delà d'un environnement standard compatible PrestaShop.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module « Afficher deux prix - TTC / HT ». Vous pouvez y accéder en naviguant vers **Modules > Gestionnaire de modules** et en cliquant sur « Configurer » à côté du nom du module.

#### Paramètres généraux

- **Activé / Désactivé (Interrupteur global)**
  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité complète du module dans votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module commencera à afficher les prix TTC et HT selon vos autres paramètres.
    - *Lorsqu'il est désactivé :* Le module cessera d'afficher les informations de prix supplémentaires, et votre boutique reviendra à son comportement d'affichage de prix par défaut.
  - **Valeur recommandée :** Activé (pour utiliser les fonctionnalités du module).
  - **Scénario / exemple pour le marchand :** Si vous effectuez une maintenance ou souhaitez temporairement masquer l'affichage double des prix, vous pouvez le désactiver ici.

#### Paramètres de la page produit

- **Afficher sur la page produit (BF\_PP)**

  - **Ce que fait ce paramètre :** Contrôle si les prix TTC et HT sont affichés sur les pages de détail de chaque produit.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les deux prix apparaîtront sur les pages produit.
    - *Lorsqu'il est désactivé :* Seul le prix PrestaShop par défaut (généralement TTC) sera affiché sur les pages produit.
  - **Valeur recommandée :** Activé (pour offrir une transparence totale).
  - **Scénario / exemple pour le marchand :** Si vous ne souhaitez afficher les prix doubles que sur les listes de catégories mais garder les pages produit plus épurées, vous pourriez désactiver ceci.
- **Masquer le prix TTC sur la page produit (BOTH\_HIDE\_P)**

  - **Ce que fait ce paramètre :** Si « Afficher sur la page produit » est activé, cette option vous permet de masquer le prix TTC, affichant ainsi uniquement le prix HT à côté du prix original (s'il n'est pas masqué).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le prix TTC sera masqué sur les pages produit.
    - *Lorsqu'il est désactivé :* Le prix TTC sera visible sur les pages produit (si « Afficher sur la page produit » est activé).
  - **Valeur recommandée :** Désactivé (sauf si vous avez une raison spécifique de le masquer, par exemple, une boutique axée sur le B2B).
  - **Scénario / exemple pour le marchand :** Une boutique B2B pourrait vouloir mettre l'accent sur les prix HT et masquer le prix TTC pour simplifier la vue pour ses clients professionnels.
- **CSS personnalisé pour la page produit (BF\_PPC)**

  - **Ce que fait ce paramètre :** Vous permet d'ajouter des règles CSS personnalisées spécifiquement pour l'affichage double des prix sur les pages produit. Ceci est destiné aux utilisateurs avancés ou aux webmasters.
  - **Effet de la modification de ce paramètre :** Tout code CSS saisi ici sera appliqué aux éléments de prix du module sur les pages produit, vous permettant de modifier les couleurs, les polices, les tailles ou le positionnement.
  - **Valeur recommandée :** Laisser vide, sauf si vous avez des besoins de style spécifiques.
  - **Scénario / exemple pour le marchand :** Vous pourriez vouloir rendre le prix HT plus petit ou d'une couleur différente du prix TTC pour les différencier visuellement.
- **Forcer le masquage de la page produit (BP\_FORCE\_HIDE)**

  - **Ce que fait ce paramètre :** C'est une option plus agressive pour masquer la sortie du module sur la page produit. Cela peut être utile si la sortie du module entre en conflit avec votre thème ou d'autres modules.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module tentera de masquer de force son affichage de prix sur les pages produit, quels que soient les autres paramètres.
    - *Lorsqu'il est désactivé :* Le module affichera les prix selon les autres paramètres.
  - **Valeur recommandée :** Désactivé (n'activez que si vous rencontrez des problèmes d'affichage).
  - **Scénario / exemple pour le marchand :** Si l'affichage double des prix chevauche un autre élément sur votre page produit, l'activation de cette option pourrait résoudre le conflit.
- **Libellé du prix TTC (BP\_TIN)**

  - **Ce que fait ce paramètre :** Définit le libellé textuel affiché à côté du prix TTC sur les pages produit.
  - **Effet de la modification de ce paramètre :** Modifie le texte du libellé.
  - **Valeur recommandée :** « TTC » ou « TVA incl. »
  - **Scénario / exemple pour le marchand :** Vous pourriez changer cela en « Prix avec TVA » pour plus de clarté dans certaines régions.
- **Libellé du prix HT (BP\_TEX)**

  - **Ce que fait ce paramètre :** Définit le libellé textuel affiché à côté du prix HT sur les pages produit.
  - **Effet de la modification de ce paramètre :** Modifie le texte du libellé.
  - **Valeur recommandée :** « HT » ou « TVA excl. »
  - **Scénario / exemple pour le marchand :** Vous pourriez changer cela en « Prix hors TVA » pour plus de clarté.
- **Libellé du prix TTC original (BP\_O\_TIN)**

  - **Ce que fait ce paramètre :** Définit le libellé textuel pour le prix TTC *original*, particulièrement utile lorsque des prix spécifiques ou des remises sont appliqués.
  - **Effet de la modification de ce paramètre :** Modifie le texte du libellé.
  - **Valeur recommandée :** « Prix original TTC »
  - **Scénario / exemple pour le marchand :** Lorsqu'un produit est en solde, vous pourriez vouloir afficher le prix original avec un libellé spécifique.

#### Paramètres de la page de liste de produits

- **Afficher sur la liste de produits (BF\_PL)**

  - **Ce que fait ce paramètre :** Contrôle si les prix TTC et HT sont affichés sur les pages de liste de produits (catégories, résultats de recherche, modules de la page d'accueil).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les deux prix apparaîtront sur les pages de liste de produits.
    - *Lorsqu'il est désactivé :* Seul le prix PrestaShop par défaut sera affiché sur les pages de liste de produits.
  - **Valeur recommandée :** Activé (pour une transparence constante).
  - **Scénario / exemple pour le marchand :** Si vos pages de catégorie sont très denses, vous pourriez désactiver ceci pour réduire l'encombrement visuel.
- **Masquer le prix TTC sur la liste de produits (BOTH\_HIDE\_PL)**

  - **Ce que fait ce paramètre :** Si « Afficher sur la liste de produits » est activé, cette option vous permet de masquer le prix TTC sur les pages de liste.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le prix TTC sera masqué sur les pages de liste de produits.
    - *Lorsqu'il est désactivé :* Le prix TTC sera visible sur les pages de liste de produits.
  - **Valeur recommandée :** Désactivé (sauf si vous avez une raison spécifique de le masquer).
  - **Scénario / exemple pour le marchand :** Une boutique B2B pourrait vouloir n'afficher que les prix HT sur toutes les listes de produits.
- **CSS personnalisé pour la liste de produits (BF\_PLC)**

  - **Ce que fait ce paramètre :** Vous permet d'ajouter des règles CSS personnalisées spécifiquement pour l'affichage double des prix sur les pages de liste de produits.
  - **Effet de la modification de ce paramètre :** Tout code CSS saisi ici sera appliqué aux éléments de prix du module sur les pages de liste.
  - **Valeur recommandée :** Laisser vide, sauf si vous avez des besoins de style spécifiques.
  - **Scénario / exemple pour le marchand :** Vous pourriez vouloir que le prix HT soit plus petit et grisé sur les pages de catégorie pour que le prix principal (TTC) ressorte davantage.
- **Libellé du prix TTC (BP\_TINL)**

  - **Ce que fait ce paramètre :** Définit le libellé textuel affiché à côté du prix TTC sur les pages de liste de produits.
  - **Effet de la modification de ce paramètre :** Modifie le texte du libellé.
  - **Valeur recommandée :** « TTC » ou « TVA incl. »
  - **Scénario / exemple pour le marchand :** Vous pourriez utiliser un libellé plus court comme « incl. » sur les pages de liste en raison de l'espace limité.
- **Libellé du prix HT (BP\_TEXL)**

  - **Ce que fait ce paramètre :** Définit le libellé textuel affiché à côté du prix HT sur les pages de liste de produits.
  - **Effet de la modification de ce paramètre :** Modifie le texte du libellé.
  - **Valeur recommandée :** « HT » ou « TVA excl. »
  - **Scénario / exemple pour le marchand :** Vous pourriez utiliser un libellé plus court comme « excl. » sur les pages de liste.

#### Règles de visibilité

- **Règle de visibilité (bp\_visibility\_rule)**

  - **Ce que fait ce paramètre :** Détermine comment l'affichage double des prix se comporte en fonction des groupes de clients, des produits spécifiques ou des catégories.
  - **Effet de la modification de ce paramètre :**
    - *Toujours afficher :* Les prix doubles sont toujours affichés pour tous les clients, produits et catégories.
    - *Masquer pour les groupes/produits/catégories sélectionnés :* Les prix doubles sont masqués pour des sélections spécifiques.
    - *Afficher uniquement pour les groupes/produits/catégories sélectionnés :* Les prix doubles sont affichés uniquement pour des sélections spécifiques.
  - **Valeur recommandée :** Toujours afficher (pour une transparence maximale), ou « Afficher uniquement pour les groupes sélectionnés » si vous ciblez spécifiquement les clients B2B.
  - **Scénario / exemple pour le marchand :** Vous pourriez choisir « Afficher uniquement pour les groupes sélectionnés » puis sélectionner votre groupe de « Clients professionnels » pour n'afficher les prix doubles que pour vos clients B2B.
- **Visibilité pour les groupes de clients (actionAdminGroupsControllerSaveAfter)**

  - **Ce que fait ce paramètre :** Vous permet de sélectionner les groupes de clients qui verront l'affichage double des prix, en fonction de la « Règle de visibilité » ci-dessus.
  - **Effet de la modification de ce paramètre :** Seuls les clients appartenant aux groupes sélectionnés verront les prix doubles (si la règle est « Afficher uniquement pour les groupes sélectionnés ») ou ne les verront *pas* (si la règle est « Masquer pour les groupes sélectionnés »).
  - **Valeur recommandée :** Sélectionnez « Tous les groupes de clients » si votre règle est « Toujours afficher ». Sinon, sélectionnez les groupes pertinents.
  - **Scénario / exemple pour le marchand :** Si vous souhaitez que seuls vos groupes « Visiteur » et « Client » voient principalement les prix TTC, mais que le groupe « Professionnel » voie les deux, vous définiriez la règle sur « Afficher uniquement pour les groupes sélectionnés » et sélectionneriez « Professionnel ».
- **Visibilité pour les produits (bp\_visibility\_products)**

  - **Ce que fait ce paramètre :** Vous permet de spécifier des produits individuels pour lesquels l'affichage double des prix doit s'appliquer (ou non s'appliquer), en fonction de la « Règle de visibilité ». Ceci utilise un champ de recherche à saisie semi-automatique.
  - **Effet de la modification de ce paramètre :** L'affichage double des prix sera activé ou désactivé pour les produits sélectionnés selon la règle de visibilité choisie.
  - **Valeur recommandée :** Laisser vide si vous souhaitez que cela s'applique à tous les produits.
  - **Scénario / exemple pour le marchand :** Vous pourriez avoir quelques produits spécifiques où l'affichage des deux prix est source de confusion, vous définiriez donc la règle sur « Masquer pour les produits sélectionnés » et ajouteriez ces produits ici.
- **Visibilité pour les catégories (bp\_visibility\_cat)**

  - **Ce que fait ce paramètre :** Vous permet de spécifier des catégories pour lesquelles l'affichage double des prix doit s'appliquer (ou non s'appliquer), en fonction de la « Règle de visibilité ».
  - **Effet de la modification de ce paramètre :** L'affichage double des prix sera activé ou désactivé pour tous les produits des catégories sélectionnées selon la règle de visibilité choisie.
  - **Valeur recommandée :** Laisser vide si vous souhaitez que cela s'applique à toutes les catégories.
  - **Scénario / exemple pour le marchand :** Si vous vendez à la fois des biens physiques (où la taxe est pertinente) et des produits numériques (où la taxe pourrait être gérée différemment), vous pourriez masquer les prix doubles pour votre catégorie « Téléchargements numériques ».

#### Options d'affichage

- **Afficher les types de prix (BF\_SHOW\_TYPES)**

  - **Ce que fait ce paramètre :** Détermine quels types de prix sont affichés.
  - **Effet de la modification de ce paramètre :**
    - *TTC et HT :* Affiche les deux prix.
    - *Seulement TTC :* Affiche uniquement le prix TTC (le module traite toujours, mais n'affiche qu'un seul).
    - *Seulement HT :* Affiche uniquement le prix HT.
  - **Valeur recommandée :** TTC et HT (pour exploiter la fonctionnalité principale du module).
  - **Scénario / exemple pour le marchand :** Si votre objectif principal est d'afficher les prix HT aux clients B2B, vous pourriez sélectionner « Seulement HT » en conjonction avec une règle de visibilité de groupe de clients.
- **Utiliser le CSS du thème Classic (BF\_CLASSICCSS)**

  - **Ce que fait ce paramètre :** Si votre thème est basé sur le thème Classic par défaut de PrestaShop, l'activation de cette option appliquera des règles CSS spécifiques conçues pour s'intégrer en douceur au style de ce thème.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module chargera une feuille de style dédiée (`classic.css`) pour assurer une meilleure intégration visuelle avec les thèmes basés sur Classic.
    - *Lorsqu'il est désactivé :* Le module utilisera son style par défaut, ce qui pourrait nécessiter un CSS personnalisé pour une intégration parfaite avec les thèmes non-Classic.
  - **Valeur recommandée :** Activer si votre thème est basé sur Classic ou est un thème enfant de Classic. Désactiver sinon.
  - **Scénario / exemple pour le marchand :** Si vous venez d'installer le module et que les prix semblent mal alignés sur votre thème Classic, l'activation de cette option pourrait résoudre le problème.
- **Mon propre CSS (BF\_OWNCSS)**

  - **Ce que fait ce paramètre :** Fournit une zone de texte où vous pouvez saisir votre propre code CSS personnalisé pour remplacer ou ajouter des styles à la sortie du module. Ceci est destiné aux utilisateurs avancés ou aux webmasters.
  - **Effet de la modification de ce paramètre :** Tout code CSS saisi ici sera appliqué globalement aux affichages de prix du module, permettant un contrôle complet du style.
  - **Valeur recommandée :** Laisser vide, sauf si vous avez des besoins de style spécifiques.
  - **Scénario / exemple pour le marchand :** Vous souhaitez modifier la taille de la police des prix affichés ou ajouter une bordure autour d'eux pour les rendre plus proéminents.

#### Paramètres avancés

- **Pourcentage de taxe sur la page produit (BP\_PP\_TPERCENT)**

  - **Ce que fait ce paramètre :** Vous permet d'afficher le pourcentage de taxe sur les pages produit.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le pourcentage de taxe (par exemple, « 20% TVA ») sera affiché à côté des prix.
    - *Désactivé :* Le pourcentage de taxe ne sera pas affiché.
  - **Valeur recommandée :** Désactivé (sauf si vous souhaitez afficher explicitement le taux de taxe).
  - **Scénario / exemple pour le marchand :** Dans les pays où les clients sont très attentifs aux taxes, l'affichage du pourcentage peut ajouter une couche supplémentaire de transparence.
- **Pourcentage de taxe sur la page produit (Hors taxes) (BP\_PP\_TPERCENT\_TEXL)**

  - **Ce que fait ce paramètre :** Similaire à ce qui précède, mais spécifiquement pour l'affichage du prix HT sur les pages produit.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le pourcentage de taxe sera affiché à côté du prix HT.
    - *Désactivé :* Le pourcentage de taxe ne sera pas affiché.
  - **Valeur recommandée :** Désactivé.
  - **Scénario / exemple pour le marchand :** Utile si vous souhaitez mettre en évidence le taux de taxe qui est exclu.
- **Pourcentage de taxe sur la liste de produits (BP\_PL\_TPERCENT)**

  - **Ce que fait ce paramètre :** Vous permet d'afficher le pourcentage de taxe sur les pages de liste de produits.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le pourcentage de taxe sera affiché à côté des prix sur les pages de liste.
    - *Désactivé :* Le pourcentage de taxe ne sera pas affiché.
  - **Valeur recommandée :** Désactivé (pour garder les pages de liste plus épurées).
  - **Scénario / exemple pour le marchand :** Si vos listes de produits ne sont pas trop encombrées, l'affichage du pourcentage de taxe peut être informatif.
- **Pourcentage de taxe sur la liste de produits (Hors taxes) (BP\_PL\_TPERCENT\_TEXL)**

  - **Ce que fait ce paramètre :** Similaire à ce qui précède, mais spécifiquement pour l'affichage du prix HT sur les pages de liste de produits.
  - **Effet de la modification de ce paramètre :**
    - *Activé :* Le pourcentage de taxe sera affiché à côté du prix HT sur les pages de liste.
    - *Désactivé :* Le pourcentage de taxe ne sera pas affiché.
  - **Valeur recommandée :** Désactivé.
  - **Scénario / exemple pour le marchand :** Moins courant, mais pourrait être utilisé pour souligner la composante fiscale qui est supprimée.

#### Paramètres de langue (Internes)

- **PS\_LANG\_DEFAULT, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG**
  - **Ce que fait ce paramètre :** Ce sont des paramètres internes de PrestaShop liés à la langue par défaut et à la langue du formulaire de l'employé. Ils sont affichés ici à titre informatif et ne sont pas directement configurables par le module.
  - **Effet de la modification de ce paramètre :** Non applicable, ce sont des valeurs en lecture seule de votre configuration PrestaShop.
  - **Valeur recommandée :** N/A
  - **Scénario / exemple pour le marchand :** Ces valeurs aident le module à déterminer quelle langue utiliser pour les libellés si vous ne les avez pas explicitement définis pour toutes les langues.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### AdminBothpricesSearchController (Back Office > Modules > Afficher deux prix - TTC / HT > Rechercher des produits)

Cet écran d'administration dédié est utilisé pour gérer le paramètre « Visibilité pour les produits ». Il fournit une interface pour rechercher et sélectionner des produits spécifiques qui doivent être affectés par les règles de visibilité du module.

- **Nom de l'écran et emplacement du menu :** Vous pouvez accéder à cet écran en cliquant sur le lien ou le bouton « Rechercher des produits » dans la page de configuration principale du module, généralement à côté du paramètre « Visibilité pour les produits ».
- **Actions et paramètres disponibles :**
  - **Champ de recherche de produits :** Un champ de texte où vous pouvez taper des noms de produits ou des identifiants pour trouver des produits spécifiques.
  - **Grille des résultats de recherche :** Affiche une liste de produits correspondant à votre requête de recherche.
  - **Boutons Ajouter/Supprimer :** Vous permet d'ajouter ou de supprimer des produits sélectionnés de la liste des produits affectés par la règle de visibilité.
  - **Liste des produits sélectionnés :** Affiche tous les produits actuellement configurés pour la règle de visibilité.
- **Effet des modifications :**
  - L'ajout d'un produit à la liste signifie que l'affichage double des prix du module sera soit affiché *uniquement* pour ce produit, soit *masqué* pour ce produit, selon votre paramètre global de « Règle de visibilité ».
  - La suppression d'un produit signifie qu'il ne sera plus spécifiquement affecté par la règle de visibilité au niveau du produit et reviendra aux paramètres généraux du module.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Accédez à la page de configuration principale du module.
  2. Définissez votre « Règle de visibilité » (par exemple, « Masquer pour les produits sélectionnés »).
  3. Cliquez sur le lien/bouton pour ouvrir l'écran « AdminBothpricesSearchController ».
  4. Utilisez le champ de recherche pour trouver les produits que vous souhaitez inclure dans la règle.
  5. Ajoutez-les à la « Liste des produits sélectionnés ».
  6. Enregistrez vos modifications sur la page de configuration principale du module.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Config du module | Activé / Désactivé | Activé | Interrupteur principal pour la fonctionnalité du module. |
| Config du module | Afficher sur la page produit (BF\_PP) | Activé | Affiche les prix doubles sur les pages de détail des produits. |
| Config du module | Masquer le prix TTC sur la page produit (BOTH\_HIDE\_P) | Désactivé | Masque le prix TTC sur les pages produit. |
| Config du module | CSS personnalisé pour la page produit (BF\_PPC) | Vide | CSS personnalisé pour l'affichage des prix sur la page produit. |
| Config du module | Forcer le masquage de la page produit (BP\_FORCE\_HIDE) | Désactivé | Masque de force la sortie du module sur la page produit. |
| Config du module | Libellé du prix TTC (BP\_TIN) | « TTC » | Libellé du prix TTC sur la page produit. |
| Config du module | Libellé du prix HT (BP\_TEX) | « HT » | Libellé du prix HT sur la page produit. |
| Config du module | Libellé du prix TTC original (BP\_O\_TIN) | « Prix original TTC » | Libellé du prix TTC original sur la page produit. |
| Config du module | Afficher sur la liste de produits (BF\_PL) | Activé | Affiche les prix doubles sur les pages de catégorie/liste. |
| Config du module | Masquer le prix TTC sur la liste de produits (BOTH\_HIDE\_PL) | Désactivé | Masque le prix TTC sur les pages de liste. |
| Config du module | CSS personnalisé pour la liste de produits (BF\_PLC) | Vide | CSS personnalisé pour l'affichage des prix sur la page de liste. |
| Config du module | Libellé du prix TTC (BP\_TINL) | « TTC » | Libellé du prix TTC sur les pages de liste. |
| Config du module | Libellé du prix HT (BP\_TEXL) | « HT » | Libellé du prix HT sur les pages de liste. |
| Config du module | Règle de visibilité (bp\_visibility\_rule) | Toujours afficher | Définit comment les règles de visibilité sont appliquées (afficher/masquer pour les sélectionnés). |
| Config du module | Visibilité pour les groupes de clients | Tous les groupes de clients | Sélectionne les groupes de clients affectés par la règle de visibilité. |
| Config du module | Visibilité pour les produits (bp\_visibility\_products) | Vide | Sélectionne les produits spécifiques affectés par la règle de visibilité. |
| Config du module | Visibilité pour les catégories (bp\_visibility\_cat) | Vide | Sélectionne les catégories spécifiques affectées par la règle de visibilité. |
| Config du module | Afficher les types de prix (BF\_SHOW\_TYPES) | TTC et HT | Détermine quels types de prix sont affichés (les deux, seulement TTC, seulement HT). |
| Config du module | Utiliser le CSS du thème Classic (BF\_CLASSICCSS) | Désactivé (Activer pour les thèmes Classic) | Applique un style spécifique au thème Classic. |
| Config du module | Mon propre CSS (BF\_OWNCSS) | Vide | CSS personnalisé global pour la sortie du module. |
| Config du module | Pourcentage de taxe sur la page produit (BP\_PP\_TPERCENT) | Désactivé | Affiche le pourcentage de taxe sur les pages produit. |
| Config du module | Pourcentage de taxe sur la page produit (Hors taxes) (BP\_PP\_TPERCENT\_TEXL) | Désactivé | Affiche le pourcentage de taxe pour le prix HT sur les pages produit. |
| Config du module | Pourcentage de taxe sur la liste de produits (BP\_PL\_TPERCENT) | Désactivé | Affiche le pourcentage de taxe sur les pages de liste. |
| Config du module | Pourcentage de taxe sur la liste de produits (Hors taxes) (BP\_PL\_TPERCENT\_TEXL) | Désactivé | Affiche le pourcentage de taxe pour le prix HT sur les pages de liste. |
| AdminBothpricesSearchController | Recherche de produits / Ajouter/Supprimer | N/A | Gère la liste des produits pour les règles de visibilité. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Le module est activé, mais je ne vois pas deux prix sur ma boutique.**
R :

- **Vérifier l'activation globale :** Assurez-vous que l'interrupteur principal « Activé / Désactivé » en haut de la configuration du module est réglé sur « Activé ».
- **Vérifier les paramètres spécifiques à la page :** Vérifiez que « Afficher sur la page produit » (BF\_PP) et/ou « Afficher sur la liste de produits » (BF\_PL) sont activés, selon l'endroit où vous vous attendez à voir les prix.
- **Vérifier les règles de visibilité :** Si vous avez défini une « Règle de visibilité », assurez-vous que votre groupe de clients, produit ou catégorie actuel est inclus dans la règle « afficher » ou n'est pas exclu par une règle « masquer ».
- **Vider le cache :** Videz toujours le cache de votre PrestaShop (Paramètres avancés > Performances > Vider le cache) après avoir apporté des modifications à la configuration du module. Videz également le cache de votre navigateur.
- **Conflits de thème :** Certains thèmes très personnalisés peuvent entrer en conflit. Essayez de passer temporairement au thème Classic par défaut de PrestaShop pour voir si les prix apparaissent. Si c'est le cas, il s'agit d'un conflit CSS ou JS lié au thème.

**Q2 : Les prix s'affichent, mais ils semblent mal alignés ou ont un style incorrect.**
R :

- **Utiliser le CSS du thème Classic :** Si votre thème est basé sur le thème Classic par défaut de PrestaShop, essayez d'activer l'option « Utiliser le CSS du thème Classic (BF\_CLASSICCSS) » dans la configuration du module.
- **CSS personnalisé :** Si vous avez un thème personnalisé, vous devrez peut-être ajouter du CSS personnalisé. Utilisez les outils de développement de votre navigateur (F12) pour identifier les classes CSS des éléments de prix du module. Ensuite, utilisez le champ « Mon propre CSS (BF\_OWNCSS) » dans la configuration du module pour ajouter vos règles de style.
- **Position du module :** Assurez-vous que le module est correctement accroché. Bien que le module gère la plupart des hooks automatiquement, des hooks spécifiques au thème peuvent parfois être nécessaires.

**Q3 : Les prix ne se mettent pas à jour lorsque je modifie les attributs du produit (par exemple, taille, couleur) sur la page produit.**
R :

- **Compatibilité du module :** Assurez-vous que votre version de PrestaShop se situe dans la plage prise en charge.
- **Conflits JavaScript :** Cela est souvent causé par des conflits JavaScript avec votre thème ou un autre module. Vérifiez la console de votre navigateur (F12 > onglet Console) pour toute erreur JavaScript lors de la modification des attributs.
- **Surcharges de thème :** Si votre thème surcharge fortement le JavaScript de la page produit par défaut de PrestaShop, cela pourrait empêcher le module de détecter les changements de prix. Contactez le développeur de votre thème ou un webmaster pour obtenir de l'aide.
- **Vider le cache :** Videz le cache de PrestaShop et du navigateur.

**Q4 : Comment traduire les libellés de prix (par exemple, « TTC », « HT ») dans d'autres langues ?**
R :

- Allez dans **International > Traductions** dans votre Back Office PrestaShop.
- Sélectionnez « Traductions des modules installés ».
- Choisissez votre thème.
- Sélectionnez votre langue.
- Trouvez le module « Afficher deux prix - TTC / HT » dans la liste.
- Vous trouverez des champs pour « Libellé du prix TTC », « Libellé du prix HT », etc., pour les pages produit et de liste. Saisissez vos traductions et enregistrez.

**Q5 : Je ne veux afficher les prix hors taxes qu'à des groupes de clients spécifiques (par exemple, B2B). Comment faire ?**
R :

- Dans la configuration du module, définissez **« Règle de visibilité »** sur « Afficher uniquement pour les groupes sélectionnés ».
- Ensuite, sélectionnez le ou les groupes de clients spécifiques (par exemple, « Professionnels », « B2B ») qui devraient voir les prix doubles.
- Facultativement, définissez **« Afficher les types de prix »** sur « Seulement HT » si vous souhaitez masquer complètement le prix TTC pour ces groupes.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Afficher deux prix - TTC / HT » (`bothprices`) est un module PrestaShop standard suivant le modèle MVC. Il étend principalement la classe `Module`, tirant parti du système de hooks de PrestaShop pour injecter des informations de prix et modifier l'affichage. Il utilise un contrôleur d'administration dédié pour la fonctionnalité de recherche de produits et des contrôleurs frontaux pour les interactions AJAX. Le module s'appuie sur les templates Smarty pour le rendu et sur JavaScript/CSS personnalisés pour les mises à jour dynamiques et le style. La configuration est stockée dans `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :

  - `controllers/front/ajax.php`
    - **Nom de la classe et classe parente** : `BothpricesAjaxModuleFrontController` étend `ModuleFrontController`.
    - **Responsabilité** : Gère les requêtes AJAX depuis le front-office, principalement pour la mise à jour dynamique des prix lorsque les attributs du produit sont modifiés. Il récupère probablement les informations sur les produits et calcule les prix en fonction des attributs sélectionnés et du contexte client, renvoyant des données JSON.
  - `controllers/front/index.php`
    - **Nom de la classe et classe parente** : `BothpricesIndexModuleFrontController` étend `ModuleFrontController`.
    - **Responsabilité** : Il s'agit d'un contrôleur de remplacement ou de secours. Dans de nombreux modules, les contrôleurs `index.php` sont utilisés pour le routage de base ou pour empêcher l'affichage du contenu des répertoires. Il pourrait ne pas avoir de logique personnalisée significative au-delà de la distribution de base.
- **Contrôleurs d'administration Back-Office** :

  - `controllers/admin/AdminBothpricesSearchController.php`
    - **Nom de la classe et classe parente** : `AdminBothpricesSearchController` étend `ModuleAdminController`.
    - **Nom de l'onglet et entité gérée** : Ce contrôleur gère la recherche et la sélection de produits pour les règles de visibilité du module. Il ne gère pas directement une `ObjectModel` spécifique mais interagit avec les données `Product` pour la sélection. Il fournit une interface de type grille pour rechercher et ajouter/supprimer des produits de la configuration `bp_visibility_products`.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne semble pas définir de classes `ObjectModel` personnalisées dans le répertoire `classes/`. Il s'appuie probablement sur les classes `Product` et `Configuration` existantes de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

- `bothprices/lib/searchTool/views/js/autocomplete.js`
  - **Portée** : Back-office.
  - **Description** : Fournit une fonctionnalité de saisie semi-automatique pour le champ de recherche de produits dans `AdminBothpricesSearchController`, permettant aux administrateurs de trouver et de sélectionner rapidement des produits pour les règles de visibilité.
- `bothprices/views/js/both-hide-p.js`
  - **Portée** : Front-office (Page produit).
  - **Description** : Contient la logique JavaScript pour masquer le prix TTC spécifiquement sur la page produit, en fonction du paramètre de configuration `BOTH_HIDE_P`. Il cible probablement des éléments DOM spécifiques pour appliquer `display: none` ou un style similaire.
- `bothprices/views/js/both-hide-pl.js`
  - **Portée** : Front-office (Pages de liste de produits).
  - **Description** : Similaire à `both-hide-p.js`, mais pour les pages de liste de produits, masquant le prix TTC en fonction de la configuration `BOTH_HIDE_PL`.
- `bothprices/views/js/bothprices-admin.js`
  - **Portée** : Back-office.
  - **Description** : Contient le JavaScript général pour la page de configuration du back-office du module. Cela peut inclure une logique pour afficher/masquer des champs de configuration en fonction d'autres sélections (par exemple, changements de règles de visibilité), la validation de formulaire ou des appels AJAX pour enregistrer les paramètres.
- `bothprices/views/js/bothprices.js`
  - **Portée** : Front-office (Global).
  - **Description** : Il s'agit du fichier JavaScript principal du front-office. Il est responsable de :
    - L'écoute des événements `prestashop.on('updateProduct', ...)` ou similaires pour détecter les changements d'attributs de produit.
    - L'exécution d'appels AJAX vers `controllers/front/ajax.php` pour récupérer les prix doubles mis à jour.
    - La mise à jour dynamique des prix TTC et HT affichés sur la page produit et potentiellement sur les pages de liste.
    - L'application de CSS ou de classes personnalisées en fonction des paramètres du module.

### 4.5 Feuilles de style CSS (`views/css/`)

- `bothprices/lib/searchTool/views/css/autocomplete.css`
  - **Portée** : Back-office.
  - **Description** : Styles pour la liste déroulante de saisie semi-automatique et les résultats de recherche dans l'interface `AdminBothpricesSearchController`.
- `bothprices/views/css/admin.css`
  - **Portée** : Back-office.
  - **Description** : Style général pour la page de configuration du module dans le Back Office de PrestaShop, assurant une apparence cohérente avec le panneau d'administration.
- `bothprices/views/css/bothprices.css`
  - **Portée** : Front-office (Global).
  - **Description** : Contient les règles CSS par défaut pour l'affichage des prix doubles sur les pages produit et les pages de liste. Cela inclut le formatage de base, le positionnement et la différenciation des deux éléments de prix.
  - **Sélecteurs de classes CSS clés** : Les développeurs peuvent rechercher des classes comme `.bothprices_price_tax_incl`, `.bothprices_price_tax_excl`, `.bothprices_wrapper` à surcharger.
- `bothprices/views/css/classic.css`
  - **Portée** : Front-office (Spécifique au thème Classic).
  - **Description** : Contient des règles CSS supplémentaires ou de surcharge spécifiquement conçues pour améliorer l'intégration visuelle avec le thème Classic par défaut de PrestaShop ou les thèmes basés sur celui-ci. Ce fichier est chargé conditionnellement en fonction du paramètre `BF_CLASSICCSS`.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :
  - `bothprices/views/templates/bothprices.tpl`
    - **Hook** : Probablement rendu dans des hooks comme `displayProductPriceBlock`, `displayProductListReviews`, `displayProductPriceBlock`, `displayProductPriceBlock`, `displayAfterProductThumbs` ou similaires, sur les pages produit et de liste.
    - **Sortie** : Ce template est responsable du rendu de la structure HTML réelle de l'affichage double des prix (prix TTC et HT) avec leurs libellés. Il reçoit les variables de prix de la logique PHP du module.
- **Templates d'administration (`views/templates/admin/`)** :
  - `bothprices/views/templates/admin/configure_shell.tpl`
    - **Hook** : Rendu dans la méthode `getContent()` du module pour la page de configuration principale.
    - **Sortie** : Cela agit comme un wrapper ou une enveloppe pour le formulaire de configuration du module, incluant potentiellement des onglets, des en-têtes et des pieds de page pour l'interface d'administration.
  - `bothprices/views/templates/selectedProducts.tpl`
    - **Hook** : Utilisé par `AdminBothpricesSearchController`.
    - **Sortie** : Rend la liste des produits qui ont été sélectionnés pour les règles de visibilité, généralement sous forme de tableau ou de liste dans l'interface de recherche d'administration.
- **Templates Front-office (`views/templates/front/`)** :
  - `bothprices/views/templates/bothprices-product-page.tpl`
    - **Hook** : Probablement rendu sur la page produit, éventuellement dans `displayProductPriceBlock` ou similaire.
    - **Sortie** : Un template spécifique pour l'affichage double des prix de la page produit, potentiellement avec des informations plus détaillées ou une mise en page différente par rapport aux pages de liste.
- **Templates de bibliothèque (`lib/searchTool/views/scripts.tpl`)** :
  - `bothprices/lib/searchTool/views/scripts.tpl`
    - **Hook** : Probablement inclus dans la vue `AdminBothpricesSearchController`.
    - **Sortie** : Contient des scripts d'initialisation JavaScript ou des variables de configuration pour l'outil de recherche à saisie semi-automatique.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module utilise principalement la table `ps_configuration` de PrestaShop pour stocker ses paramètres. Les clés de configuration incluent : `mypresta_updates`, `update_`, `updatev_`, `BOTH_HIDE_PL_CSS`, `BOTH_HIDE_P_CSS`, `BF_PP`, `BF_PL`, `bp_visibility_rule`, `bp_visibility_products`, `bp_visibility_cat`, `BF_SHOW_TYPES`, `BF_PLC`, `BF_PPC`, `BP_FORCE_HIDE`, `BP_PP_TPERCENT_TEXL`, `BP_PP_TPERCENT`, `BP_PL_TPERCENT_TEXL`, `BP_PL_TPERCENT`, `BOTH_HIDE_PL`, `BOTH_HIDE_P`, `BF_OWNCSS`, `BF_CLASSICCSS`, `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `BP_TIN`, `BP_TIN_L`, `BP_TEX`, `BP_TEX_L`, `BP_TINL`, `BP_TINL_L`, `BP_TEXL`, `BP_TEXL_L`, `BP_O_TIN`, `BP_O_TIN_L`, `BP_O_TEX`.
  - Il ne semble pas créer de tables SQL personnalisées.
- **Table des hooks enregistrés** :

| Nom du hook | Portée | Moment d'exécution | Objectif technique |
| --- | --- | --- | --- |
| `ActionFrontControllerSetMedia` | Front-Office | Avant la sortie du contrôleur, après l'initialisation des médias. | Injecte les actifs CSS et JS du module dans le front-office. |
| `ActionAdminGroupsControllerSaveAfter` | Back-Office | Après qu'un administrateur a enregistré un groupe de clients. | Potentiellement utilisé pour vider le cache ou réévaluer les règles de visibilité liées aux groupes de clients. |
| `ActionAdminControllerSetMedia` | Back-Office | Avant la sortie du contrôleur d'administration, après l'initialisation des médias. | Injecte les actifs CSS et JS du module dans le back-office (par exemple, pour la page de configuration, le contrôleur de recherche). |
| `updateproduct` | Back-Office | Après la mise à jour d'un produit. | Vide les caches pertinents, réévalue les données de prix spécifiques au produit. |
| `ActionProductDelete` | Back-Office | Après la suppression d'un produit. | Nettoie toutes les données spécifiques au module liées au produit supprimé (par exemple, de `bp_visibility_products`). |
| `displayUpdateProduct` | Back-Office | Sur la page d'édition de produit. | Potentiellement injecte des champs ou des informations personnalisés dans le formulaire d'édition de produit. |
| `actionProductUpdate` | Back-Office | Après la mise à jour d'un produit. | Similaire à `updateproduct`, garantit que les données internes du module reflètent les modifications du produit. |
| `displayHeader` | Front-Office | Dans la section `<head>` de chaque page du front-office. | Injecte le CSS et le JS du module pour une disponibilité globale, ou rend un petit extrait. |
| `displayCategoryUpdate` | Back-Office | Sur la page d'édition de catégorie. | Potentiellement injecte des champs ou des informations personnalisés dans le formulaire d'édition de catégorie. |
| `ActionCategoryUpdate` | Back-Office | Après la mise à jour d'une catégorie. | Vide les caches pertinents, réévalue les données de prix spécifiques à la catégorie. |
| `actionProductAdd` | Back-Office | Après l'ajout d'un nouveau produit. | Initialise les données spécifiques au module pour le nouveau produit. |
| `actionObjectSpecificPriceUpdateAfter` | Back-Office | Après la mise à jour d'un prix spécifique (remise). | Garantit que les calculs de prix dynamiques reflètent les nouveaux prix spécifiques. |
| `categoryUpdate` | Back-Office | Après la mise à jour d'une catégorie. | Alias ou doublon de `ActionCategoryUpdate`. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Afficher deux prix - TTC / HT », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question que vous pourriez avoir concernant la fonctionnalité du module.
