---
title: "Importateur Zalando Fashion Connector (FCI) - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Zalando Fashion Connector Importer (FCI) par MyPresta.eu."
sidebar:
  label: "Importateur Zalando Fashion Connector (FCI) - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Zalando Fashion Connector Importer (FCI) sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/zalando-fashion-connector-importer-fci.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/zalando-fashion-connector-importer-fci/)
>
> ---


# Importateur Zalando Fashion Connector (FCI)

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour la plupart des modules PrestaShop et sont habituellement disponibles sur tout environnement d'hébergement moderne.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Zalando Fashion Connector Importer (FCI))

Ceci est l'écran de configuration principal où vous définissez les paramètres de base pour votre flux Zalando.

-   **Ce que fait ce paramètre :** Cette section vous permet de définir les informations essentielles qui seront incluses dans votre flux de produits Zalando.
-   **Effet de la modification de ce paramètre :** Les valeurs que vous définissez ici influenceront directement les données que Zalando reçoit sur vos produits, affectant la façon dont ils sont affichés et gérés sur leur plateforme.

| Paramètre / Option | Ce que fait ce paramètre | Effet de la modification de ce paramètre | Valeur recommandée | Scénario / exemple pour le marchand |
| :------------------- | :----------------------- | :--------------------------------------- | :------------------ | :----------------------------------- |
| **Boutique** | Spécifie le nom de votre boutique tel qu'il doit apparaître sur Zalando. Cela aide Zalando à identifier votre point de vente spécifique. | *Si défini :* Le nom de votre boutique spécifié sera inclus dans le flux de produits. *Si laissé vide :* Zalando pourrait utiliser un identifiant par défaut ou rejeter le flux si un nom de boutique est obligatoire. | Le nom réel de votre boutique (par exemple, « Ma Boutique de Mode ») | Si vous avez plusieurs magasins physiques ou marques, cela aide Zalando à différencier votre inventaire. |
| **EAN (European Article Number)** | Détermine si l'EAN (code-barres) de vos produits doit être inclus dans le flux. Les EAN sont cruciaux pour l'identification des produits. | *Si activé :* Les EAN feront partie du flux, permettant à Zalando de faire correspondre précisément vos produits. *Si désactivé :* Les produits pourraient ne pas être correctement identifiés ou pourraient être rejetés par Zalando si l'EAN est un champ obligatoire. | OUI | Essentiel pour la plupart des listes de produits, en particulier dans la mode, pour assurer une identification unique. |
| **Prix** | Contrôle si le prix de vente du produit est inclus dans le flux. | *Si activé :* Le prix de vente actuel de votre boutique PrestaShop sera envoyé à Zalando. *Si désactivé :* Zalando ne recevra pas de mises à jour de prix, ce qui pourrait entraîner des prix obsolètes sur leur plateforme. | OUI | Crucial pour garantir que les clients voient le prix correct sur Zalando. |
| **Prix de détail** | Détermine si le prix de détail original (souvent le prix « barré » pour les remises) est inclus. | *Si activé :* Le prix original sera envoyé, permettant à Zalando d'afficher des économies ou des promotions. *Si désactivé :* Seul le prix de vente actuel sera envoyé, masquant potentiellement les informations de remise. | OUI (si vous utilisez les prix de détail pour les promotions) | Si vous organisez des soldes, inclure le prix de détail aide à mettre en évidence la remise pour les clients sur Zalando. |
| **Quantité** | Spécifie si la quantité de stock actuelle de vos produits est incluse dans le flux. | *Si activé :* Les niveaux de stock de vos produits seront mis à jour sur Zalando, évitant la survente. *Si désactivé :* Zalando ne recevra pas de mises à jour de stock, ce qui entraînera des divergences potentielles et l'insatisfaction des clients si un article est en rupture de stock. | OUI | Absolument critique pour éviter de vendre des produits que vous n'avez plus en stock. |
| **Nom du produit** | Contrôle si le nom du produit est inclus dans le flux. | *Si activé :* Le nom du produit de votre boutique PrestaShop sera envoyé à Zalando. *Si désactivé :* Les produits pourraient être listés sans nom ou rejetés si c'est un champ obligatoire. | OUI | Essentiel pour que les clients identifient et recherchent vos produits sur Zalando. |
| **ID Client (zf\_client)** | Votre identifiant client unique fourni par Zalando pour l'accès à l'API. | *Si correctement saisi :* Permet au module de s'authentifier auprès des systèmes de Zalando. *Si incorrect ou vide :* La génération et les mises à jour du flux échoueront. | L'ID fourni par Zalando | Vous devez l'obtenir auprès de votre responsable de compte Zalando Connected Retail. |
| **Clé API (zf\_api)** | Votre clé API unique fournie par Zalando pour une communication sécurisée. | *Si correctement saisie :* Permet un transfert de données sécurisé entre votre boutique et Zalando. *Si incorrecte ou vide :* La génération et les mises à jour du flux échoueront en raison de problèmes d'authentification. | La clé fournie par Zalando | Il s'agit d'une information de sécurité ; gardez-la confidentielle et obtenez-la auprès de Zalando. |

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 Configuration de l'exportation de produits (Back Office > Zalando FCI > Exporter les produits)

Cet écran, accessible via le menu du back office de PrestaShop, est l'endroit où vous définissez les paramètres détaillés pour la génération de votre flux de produits pour Zalando. Il permet d'affiner les données incluses et leur formatage.

-   **Nom de l'écran et emplacement du menu :** **Zalando FCI > Exporter les produits** (Ceci apparaîtra comme un nouvel élément de menu dans la navigation de votre Back Office PrestaShop).
-   **Actions et paramètres disponibles :** Cet écran présente un formulaire avec de nombreuses options pour personnaliser votre exportation de produits. Vous y trouverez des champs pour sélectionner les boutiques, les devises, les attributs de produit et les options de filtrage.
-   **Effet des modifications :** Les modifications apportées ici ont un impact direct sur le contenu et la structure du fichier de flux de produits généré. Des paramètres incorrects peuvent entraîner le rejet de votre flux par Zalando ou l'affichage d'informations produit incorrectes.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Initialement, configurez tous les paramètres avec soin selon les spécifications de Zalando et les besoins de votre boutique.
    2.  Générez un flux de test et validez-le auprès de Zalando (si possible) pour vous assurer que toutes les données sont correctes.
    3.  Une fois configuré, vous utiliserez principalement cet écran pour générer le flux manuellement si nécessaire, ou vous configurerez une tâche cron (une tâche planifiée) pour automatiser la génération du flux en fonction de ces paramètres.

| Paramètre / Option | Ce que fait ce paramètre | Effet de la modification de ce paramètre | Valeur recommandée | Scénario / exemple pour le marchand |
| :------------------------------------ | :--------------------------------------- | :--------------------------------------- | :------------------ | :----------------------------------- |
| **Mémoriser les paramètres (zf\_remember\_settings)** | Si activé, le module mémorisera vos derniers paramètres d'exportation choisis pour plus de commodité. | *Si activé :* Vos sélections sur cette page persisteront pour les exportations futures. *Si désactivé :* Les paramètres reviendront aux valeurs par défaut chaque fois que vous visiterez la page. | OUI | Gagne du temps si vous générez fréquemment des flux avec les mêmes paramètres. |
| **Format du fichier d'exportation (zf\_export\_file\_format)** | Sélectionne le format de sortie pour le fichier de flux de produits (par exemple, CSV, XML). | *Si défini :* Le fichier généré sera dans le format choisi. *Si incorrect :* Zalando pourrait ne pas être en mesure de traiter le fichier. | Vérifiez les exigences de Zalando (généralement CSV ou XML) | Zalando spécifiera le format requis pour leur système d'importation. |
| **Type d'exportation (zf\_export\_type)** | Définit le type de produits à exporter (par exemple, tous les produits, seulement les actifs, seulement des catégories spécifiques). | *Si défini :* Seuls les produits correspondant aux critères seront inclus. *Si incorrect :* Vous pourriez exporter trop ou trop peu de produits. | Tous les produits actifs, ou selon l'intégration de Zalando | Si vous ne souhaitez lister qu'un sous-ensemble de votre catalogue sur Zalando. |
| **Boutique (zf\_export\_store)** | Vous permet de sélectionner la boutique PrestaShop (dans une configuration multi-boutiques) à partir de laquelle exporter les produits. | *Si sélectionné :* Les produits de cette boutique spécifique seront exportés. *Si incorrect :* Les produits de la mauvaise boutique pourraient être inclus. | Votre boutique principale, ou la boutique pertinente pour Zalando | Pour les marchands gérant plusieurs boutiques distinctes à partir d'une seule installation PrestaShop. |
| **Délimiteur (zf\_export\_delimiter)** | Spécifie le caractère utilisé pour séparer les champs de données dans le fichier d'exportation (par exemple, virgule, point-virgule). | *Si défini :* Le délimiteur choisi sera utilisé. *Si incorrect :* Le fichier sera illisible par Zalando. | Vérifiez les exigences de Zalando (souvent virgule ou point-virgule) | Crucial pour les fichiers CSV afin de garantir que les données sont correctement analysées. |
| **Devise (zf\_export\_currency)** | Sélectionne la devise pour les prix des produits dans le fichier d'exportation. | *Si sélectionné :* Les prix seront convertis ou affichés dans cette devise. *Si incorrect :* Zalando pourrait afficher des prix erronés ou rejeter le flux. | La devise requise par Zalando (par exemple, EUR) | Si votre boutique opère dans plusieurs devises, assurez-vous d'exporter dans celle que Zalando attend. |
| **Format du nom du produit (zf\_export\_product\_name\_format)** | Définit la façon dont les noms de produits sont formatés (par exemple, inclure le fabricant, les attributs). | *Si défini :* Les noms de produits suivront ce format. *Si incorrect :* Les noms pourraient être peu clairs ou ne pas respecter les directives de Zalando. | Selon les recommandations de Zalando pour la clarté | Pour garantir que les noms de produits sont informatifs et cohérents sur Zalando. |
| **Inclure la taxe (zf\_export\_tax)** | Détermine si les prix des produits dans le flux doivent inclure la taxe. | *Si activé :* Les prix incluront la taxe. *Si désactivé :* Les prix excluront la taxe. | Vérifiez les exigences de Zalando pour l'affichage des prix | Important pour la conformité fiscale et l'affichage correct des prix sur Zalando. |
| **Exporter les prix par pays (zf\_export\_country\_prices)** | Si activé, les prix spécifiques à différents pays seront inclus (si configurés dans PrestaShop). | *Si activé :* Les prix spécifiques au pays seront exportés. *Si désactivé :* Seuls les prix par défaut seront exportés. | OUI (si vous avez des prix spécifiques par pays) | Pour les vendeurs internationaux ayant des stratégies de prix variées par région. |
| **Pays par défaut (PS\_COUNTRY\_DEFAULT)** | Le pays par défaut de votre boutique PrestaShop, utilisé comme valeur de repli pour certains paramètres. | *Si défini :* Fournit un pays de base pour les calculs de prix et de taxes. | Le pays principal de votre boutique | Assure un comportement par défaut cohérent pour les paramètres internationaux. |
| **Exporter uniquement les produits actifs (zf\_export\_active)** | Si activé, seuls les produits actuellement marqués comme « actifs » dans PrestaShop seront exportés. | *Si activé :* Seuls les produits disponibles sont envoyés. *Si désactivé :* Les produits inactifs pourraient être inclus, entraînant des erreurs sur Zalando. | OUI | Empêche la liste de produits que vous ne souhaitez pas vendre ou qui ne sont plus disponibles. |
| **Exporter les fabricants (zf\_export\_manufacturers)** | Si activé, les informations sur le fabricant seront incluses dans le flux. | *Si activé :* Les données du fabricant sont envoyées. *Si désactivé :* Les données du fabricant sont omises. | OUI | Utile pour les clients pour filtrer par marque sur Zalando. |
| **Exporter les fournisseurs (zf\_export\_suppliers)** | Si activé, les informations sur le fournisseur seront incluses dans le flux. | *Si activé :* Les données du fournisseur sont envoyées. *Si désactivé :* Les données du fournisseur sont omises. | NON (sauf si requis par Zalando) | Moins courant pour les flux destinés aux clients, plus pour le suivi interne. |
| **Exporter la catégorie (zf\_export\_category)** | Si activé, les informations sur la catégorie de produit seront incluses. | *Si activé :* Les données de catégorie sont envoyées. *Si désactivé :* Les données de catégorie sont omises. | OUI | Aide Zalando à catégoriser correctement vos produits et facilite la navigation des clients. |
| **Exporter uniquement les produits en stock (zf\_export\_instock)** | Si activé, seuls les produits avec un stock disponible seront exportés. | *Si activé :* Seuls les produits que vous pouvez honorer sont envoyés. *Si désactivé :* Les produits en rupture de stock pourraient être inclus, entraînant des problèmes de survente. | OUI | Crucial pour éviter la déception des clients en raison d'articles indisponibles. |
| **Exclure le prix maximum (zf\_export\_exclude\_price\_max)** | Si activé, les produits au-dessus d'un certain seuil de prix seront exclus du flux. | *Si activé :* Les produits dépassant le prix maximum ne seront pas exportés. *Si désactivé :* Tous les produits, quel que soit leur prix, sont exportés. | NON (sauf si vous avez des articles de grande valeur spécifiques à exclure) | Utile si Zalando a des limites de prix ou si vous ne souhaitez vendre que certaines gammes de prix sur leur plateforme. |
| **Valeur d'exclusion du prix maximum (zf\_export\_exclude\_price\_max\_v)** | La valeur de prix maximale pour le paramètre « Exclure le prix maximum ». | *Si défini :* Définit la limite supérieure de prix pour les produits exportés. | Laisser vide si aucune exclusion par prix maximum | Si vous ne souhaitez vendre que des articles de moins de 500 € sur Zalando, définissez cette valeur à 500. |

#### 2.2.2 Écran d'index d'administration (Back Office > Zalando FCI > Index)

Cet écran sert probablement de page d'accueil ou de vue de gestion simple pour le module, affichant potentiellement des informations ou fournissant des liens rapides.

-   **Nom de l'écran et emplacement du menu :** **Zalando FCI > Index** (Ceci apparaîtra comme un nouvel élément de menu dans la navigation de votre Back Office PrestaShop, souvent le premier élément sous le menu principal du module).
-   **Actions et paramètres disponibles :** Cet écran affiche généralement une grille ou un simple panneau d'information. Il peut afficher la date de la dernière exportation, un lien pour générer le flux, ou le statut général du module. Ce n'est généralement pas un écran pour une configuration détaillée, mais plutôt pour un aperçu ou des actions rapides.
-   **Effet des modifications :** Il n'y a généralement pas de « paramètres » directs à modifier sur cet écran. Son but est plus informatif ou navigationnel.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Utilisez-le comme point d'entrée rapide au module, pour vérifier le statut de votre dernière exportation, ou pour naviguer vers l'écran « Exporter les produits » pour une configuration détaillée et la génération du flux.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| :------------------- | :------------------------------------ | :------------------------------ | :--------------------------------------- |
| **Configuration du module** | Boutique | Nom de votre boutique | Identifie votre boutique sur Zalando. |
| **Configuration du module** | EAN | OUI | Essentiel pour l'identification des produits. |
| **Configuration du module** | Prix | OUI | Assure une tarification correcte sur Zalando. |
| **Configuration du module** | Prix de détail | OUI (si utilisé) | Affiche le prix original pour les promotions. |
| **Configuration du module** | Quantité | OUI | Critique pour des niveaux de stock précis, évite la survente. |
| **Configuration du module** | Nom du produit | OUI | Essentiel pour l'identification et la recherche de produits. |
| **Configuration du module** | ID Client (zf\_client) | Fourni par Zalando | S'authentifie auprès de l'API Zalando. |
| **Configuration du module** | Clé API (zf\_api) | Fourni par Zalando | Sécurise la communication avec l'API Zalando. |
| **Exporter les produits** | Mémoriser les paramètres | OUI | Gagne du temps en conservant les choix d'exportation. |
| **Exporter les produits** | Format du fichier d'exportation | Vérifiez les exigences de Zalando | Définit le type de fichier de sortie. |
| **Exporter les produits** | Type d'exportation | Tous les produits actifs | Contrôle les produits inclus. |
| **Exporter les produits** | Boutique | Votre boutique principale | Sélectionne les produits d'une boutique spécifique (multi-boutiques). |
| **Exporter les produits** | Délimiteur | Vérifiez les exigences de Zalando | Sépare les champs dans les fichiers CSV. |
| **Exporter les produits** | Devise | Requise par Zalando (par exemple, EUR) | Définit la devise pour les prix exportés. |
| **Exporter les produits** | Format du nom du produit | Selon les recommandations de Zalando | Formate les noms de produits pour la clarté. |
| **Exporter les produits** | Inclure la taxe | Vérifiez les exigences de Zalando | Détermine si les prix incluent la taxe. |
| **Exporter les produits** | Exporter les prix par pays | OUI (si applicable) | Inclut les prix spécifiques par pays. |
| **Exporter les produits** | Pays par défaut | Le pays principal de votre boutique | Repli pour les paramètres liés au pays. |
| **Exporter les produits** | Exporter uniquement les produits actifs | OUI | Empêche la liste de produits inactifs. |
| **Exporter les produits** | Exporter les fabricants | OUI | Inclut les informations sur la marque. |
| **Exporter les produits** | Exporter les fournisseurs | NON (sauf si requis) | Inclut les informations sur le fournisseur. |
| **Exporter les produits** | Exporter la catégorie | OUI | Aide Zalando à catégoriser les produits. |
| **Exporter les produits** | Exporter uniquement les produits en stock | OUI | Empêche la liste d'articles en rupture de stock. |
| **Exporter les produits** | Exclure le prix maximum | NON (sauf si nécessaire) | Exclut les produits au-dessus d'un prix défini. |
| **Exporter les produits** | Valeur d'exclusion du prix maximum | Laisser vide si aucune exclusion | Définit le prix maximum pour l'exclusion. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes produits n'apparaissent pas sur Zalando, ou le flux est rejeté. Que dois-je vérifier en premier ?**
R1 :

-   **Vérifier la configuration du module :** Allez dans **Modules > Gestionnaire de modules > Zalando Fashion Connector Importer (FCI) > Configurer**. Assurez-vous que votre « ID Client » et votre « Clé API » sont correctement saisis tels que fournis par Zalando.
-   **Vérifier les paramètres d'exportation :** Naviguez vers **Zalando FCI > Exporter les produits**. Vérifiez que le « Format du fichier d'exportation » et le « Délimiteur » correspondent aux exigences exactes de Zalando. Assurez-vous également que « Exporter uniquement les produits actifs » et « Exporter uniquement les produits en stock » sont activés si vous ne souhaitez envoyer que les articles disponibles.
-   **Valider les données produit :** Assurez-vous que vos produits dans PrestaShop ont des EAN, des noms, des prix et des quantités de stock valides. Des données manquantes ou invalides sont une raison courante de rejet.
-   **Vider le cache :** Parfois, d'anciennes données peuvent persister. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures).

**Q2 : Les prix ou les niveaux de stock sur Zalando ne se mettent pas à jour correctement.**
R2 :

-   **Vérifier la fréquence d'exportation :** À quelle fréquence générez-vous le flux ? Si vous le faites manuellement, vous devez le faire régulièrement. Si vous avez configuré une tâche cron, assurez-vous qu'elle s'exécute à la fréquence souhaitée (par exemple, toutes les heures).
-   **Configuration du module :** Vérifiez à nouveau que « Prix » et « Quantité » sont activés sur l'écran de configuration principal du module.
-   **Temps de traitement de Zalando :** N'oubliez pas que même après avoir généré et envoyé le flux, les systèmes de Zalando ont besoin de temps pour traiter et mettre à jour les données. Cela peut parfois prendre de quelques minutes à plusieurs heures selon leur charge.

**Q3 : J'ai un thème personnalisé, et l'interface d'administration du module semble un peu décalée.**
R3 :

-   L'interface d'administration du module utilise le style PrestaShop standard, mais des incohérences visuelles mineures peuvent survenir avec des thèmes de back-office fortement personnalisés. Cela n'affecte généralement pas la fonctionnalité.
-   Si c'est un problème important, contactez le support MyPresta.eu. Pour des ajustements mineurs, un développeur web peut souvent modifier le fichier `zalandofci/views/admin-theme.css` ou ajouter du CSS personnalisé à votre back office PrestaShop.

**Q4 : Comment configurer une tâche cron pour automatiser la génération du flux ?**
R4 :

-   Les étapes exactes dépendent de votre hébergeur. Vous trouverez généralement une section « Tâches Cron » ou « Tâches planifiées » dans votre panneau de contrôle d'hébergement (par exemple, cPanel, Plesk).
-   Vous aurez besoin de l'URL qui déclenche la génération du flux. Cette URL est généralement fournie sur la page de configuration « Exporter les produits » du module après avoir enregistré vos paramètres, ou elle peut être construite en utilisant le chemin du contrôleur frontal (par exemple, `votreboutique.com/module/zalandofci/feed`).
-   Configurez la tâche cron pour exécuter cette URL à l'intervalle souhaité (par exemple, `wget -q -O /dev/null "http://votreboutique.com/module/zalandofci/feed"`). Si vous n'êtes pas sûr, consultez la documentation ou le support de votre hébergeur.

**Q5 : Le module est installé, mais je ne vois pas « Zalando FCI » dans mon menu du Back Office.**
R5 :

-   **Vider le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** et videz le cache. Parfois, le menu ne se rafraîchit pas immédiatement après l'installation du module.
-   **Vérifier le statut du module :** Allez dans **Modules > Gestionnaire de modules** et recherchez « Zalando Fashion Connector Importer (FCI) ». Assurez-vous qu'il est listé comme « Installé » et « Activé ».
-   **Permissions :** Dans de rares cas, les permissions des employés peuvent restreindre la visibilité du menu. Vérifiez **Administration > Permissions** pour votre profil d'employé.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module Zalando Fashion Connector Importer (FCI) suit une architecture de module PrestaShop standard, tirant parti des principes MVC lorsque cela est applicable. Il se concentre principalement sur l'exportation de données, en utilisant une combinaison de contrôleurs frontaux et d'administration. La logique principale réside dans le fichier du module principal et les contrôleurs d'administration pour la configuration et la génération du flux. Il ne semble pas utiliser de classes `ObjectModel` personnalisées, mais interroge directement la base de données PrestaShop pour les données produit. La fonction principale du module est de générer un flux de données, qui est généralement consommé par un système externe (Zalando) via une tâche planifiée (tâche cron) qui appelle un contrôleur frontal.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs sont accessibles depuis l'URL du front-office et sont généralement utilisés pour générer le flux de produits, souvent déclenchés par une tâche cron.

-   `controllers/front/feed.php`
    -   **Nom de la classe et classe parente** : `ZalandofciFeedModuleFrontController` étendant `ModuleFrontController`.
    -   **Responsabilité** : C'est le point d'accès principal pour la génération du flux de produits. Il répond aux requêtes (généralement des tâches cron) et génère dynamiquement les données produit en fonction de la configuration du module. Il récupère probablement les informations produit (EAN, prix, quantité, nom) et les formate dans la sortie spécifiée (par exemple, CSV, XML) pour Zalando. Ce contrôleur ne rend pas une page visuelle mais produit des données brutes.
-   `controllers/front/index.php`
    -   **Nom de la classe et classe parente** : `ZalandofciIndexModuleFrontController` étendant `ModuleFrontController`.
    -   **Responsabilité** : Ce contrôleur sert probablement de repli ou de simple point d'entrée, redirigeant potentiellement ou affichant un message minimal. Dans de nombreux modules, un contrôleur frontal `index.php` est présent pour empêcher l'affichage du répertoire ou fournir une action par défaut si aucune action spécifique n'est demandée.

#### Contrôleurs d'administration Back-Office

Ces contrôleurs gèrent la configuration du module et les paramètres d'exportation de produits dans le Back Office de PrestaShop.

-   `controllers/admin/AdminExportProductsFci.php`
    -   **Nom de l'onglet et entité gérée** : « Exporter les produits » sous le menu « Zalando FCI ». Ce contrôleur gère la configuration détaillée de l'exportation de produits.
    -   **Responsabilité** : Ce contrôleur gère l'affichage et la soumission du formulaire d'exportation de produits. Il récupère les paramètres de configuration (par exemple, `zf_export_file_format`, `zf_export_type`, `zf_export_currency`, `zf_export_tax`, `zf_export_active`, etc.) de `ps_configuration`, traite les entrées utilisateur et déclenche la logique réelle de récupération et de formatage des données produit pour la génération du flux. Il utilise probablement les méthodes `AdminController` pour le rendu du formulaire (`renderForm`) et la sauvegarde (`postProcess`).
-   `controllers/admin/index.php`
    -   **Nom de l'onglet et entité gérée** : « Index » sous le menu « Zalando FCI ».
    -   **Responsabilité** : Similaire à son homologue front-office, ce contrôleur d'administration sert probablement de page d'accueil ou de simple aperçu. Il peut afficher des informations générales sur le module, des liens rapides vers d'autres pages d'administration ou un message d'état. Il n'est généralement pas impliqué dans la gestion complexe des données, mais plutôt dans la navigation et l'affichage d'informations.

### 4.3 Classes et modèles principaux (`classes/`)

Le dossier du module n'indique aucune classe ou modèle personnalisé dans le répertoire `classes/`. Cela suggère que le module interagit directement avec les classes `ObjectModel` principales de PrestaShop `Product` et `ProductSupplier` (ou similaires) et la classe `Configuration` pour les paramètres. La récupération des données est probablement gérée directement dans les contrôleurs ou le fichier du module principal à l'aide de `Db::getInstance()->executeS()` ou d'objets `DbQuery`.

### 4.4 Actifs JavaScript (`views/js/`)

Le dossier du module n'indique aucun fichier JavaScript personnalisé. Cela implique que la configuration et la fonctionnalité du module sont principalement pilotées côté serveur, avec des interactions front-end dynamiques minimales ou inexistantes dans le Back Office ou le Front Office qui nécessiteraient du JS personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `zalandofci/views/admin-theme.css`
    -   **Portée** : Style des formulaires d'administration du Back Office.
    -   **Principaux composants et conteneurs d'interface utilisateur qu'il stylise** : Cette feuille de style est responsable de la présentation visuelle des formulaires de configuration du module et potentiellement de toutes les grilles ou panneaux d'information personnalisés dans le Back Office de PrestaShop. Elle garantit que l'interface du module s'intègre visuellement au thème d'administration de PrestaShop.
    -   **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger** : Les développeurs peuvent inspecter les pages d'administration du module pour identifier des classes spécifiques (par exemple, `.zalandofci-form`, `.zalandofci-panel`, `.zalandofci-alert`) et les surcharger dans leur thème d'administration personnalisé ou en ajoutant du CSS via un hook `displayBackOfficeHeader`.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :
    -   Le dossier du module ne liste pas explicitement de templates dans un sous-répertoire `hook/`, mais il enregistre des hooks comme `displayHeader`, `displayRightColumn`, `displayProduct`, `displayFooter`. Si une sortie visuelle était prévue pour ces hooks, les templates résideraient généralement ici. Compte tenu de l'objectif du module (flux de données backend), il est probable que ces hooks soient utilisés à des fins techniques (par exemple, ajout de JS/CSS, ou pas du tout utilisés pour la sortie visuelle).
-   **Templates d'administration (`views/templates/admin/`)** :
    -   `zalandofci/views/how-it-works.tpl`
        -   **Objectif** : Ce template fournit probablement un contenu informatif dans le Back Office, éventuellement sur la page de configuration principale ou l'écran « Index », expliquant le fonctionnement du module ou fournissant des instructions de configuration.
    -   `zalandofci/views/returnAlert.tpl`
        -   **Objectif** : Ce template est probablement utilisé pour afficher des messages de succès ou d'erreur (alertes) dans le Back Office après une action (par exemple, enregistrement de la configuration, génération d'un flux).
    -   `zalandofci/views/script.tpl`
        -   **Objectif** : Ce template peut contenir du code JavaScript en ligne ou être utilisé pour inclure des fichiers JS externes de manière conditionnelle dans le Back Office. Il pourrait être utilisé pour un comportement de formulaire dynamique ou pour déclencher des actions spécifiques.
-   **Templates front-office (`views/templates/front/`)** :
    -   Le dossier du module ne liste aucun template front-office spécifique, renforçant l'idée que le module n'a pas de présence visuelle directe côté client de la boutique.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :

    -   Le module ne semble pas créer de tables SQL personnalisées lors de l'installation (méthode `install()`).
    -   Tous les paramètres de configuration spécifiques au module (par exemple, `zf_client`, `zf_api`, `zf_export_file_format`, `zf_remember_settings`, etc.) sont stockés dans la table standard `ps_configuration` de PrestaShop. Ces clés sont préfixées par `zf_` ou `PS_` (pour les paramètres PrestaShop de base utilisés par le module).
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| :------------------------- | :--------------------------------------- | :--------------------------------------- |
| `displayHeader` | Rendu dans la section `<head>` de toutes les pages du front-office. | Potentiellement utilisé pour inclure du CSS ou du JS spécifique au module, bien qu'aucun JS/CSS personnalisé ne soit listé pour le front-office. Pourrait également être utilisé pour des balises méta ou d'autres éléments non visuels. |
| `displayRightColumn` | Rendu dans la colonne de droite des pages qui en ont une. | Peu susceptible d'être utilisé pour une sortie visuelle étant donné l'objectif du module. Pourrait être un hook hérité ou utilisé pour une injection de données très spécifique et non visuelle. |
| `displayProduct` | Rendu sur la page produit. | Peu susceptible d'être utilisé pour une sortie visuelle. Pourrait être utilisé pour ajouter des attributs de données cachés aux éléments du produit pour des scripts externes, bien qu'aucun JS personnalisé ne soit listé. |
| `displayFooter` | Rendu dans la section du pied de page de toutes les pages du front-office. | Similaire à `displayHeader`, pourrait être utilisé pour inclure du JS/CSS ou d'autres éléments non visuels à la fin du chargement de la page. |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses médias (JS/CSS). | Utilisé par `AdminExportProductsFci` pour charger `zalandofci/views/admin-theme.css` pour ses formulaires de configuration. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour télécharger les dernières versions du module Zalando Fashion Connector Importer (FCI), veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité et l'intégration du module.
