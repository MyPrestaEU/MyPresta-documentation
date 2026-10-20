---
title: "Journal de recherche - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Journal de recherche par MyPresta.eu."
sidebar:
  label: "Journal de recherche - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Search log sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/search-log.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/search-log/)
>
> ---


# Journal de recherche

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune exigence particulière au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Parcours complet de configuration (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Journal de recherche)

Ceci est l'écran de configuration principal du module « Journal de recherche ». Il fournit une interface simple pour activer ou désactiver la fonctionnalité de journalisation.

- **Emplacement du menu :** Back Office > Modules > Gestionnaire de modules > Journal de recherche > Configurer

| Paramètre / Option | Ce que fait ce paramètre | Effet de la modification de ce paramètre | Valeur recommandée | Scénario / exemple pour le marchand |
| :--- | :--- and the Search Log module will start recording customer searches.

### 2.2 Écran d'administration dédié : Gestion du journal de recherche (Back Office > Journal de recherche)

Cet écran vous permet de visualiser et de gérer toutes les requêtes de recherche enregistrées par le module. Il fournit une liste complète de ce que vos clients recherchent.

- **Nom de l'écran et emplacement du menu :** Back Office > **Journal de recherche** (Ceci apparaîtra comme un nouvel élément de menu, généralement sous « Paramètres de la boutique » ou « Paramètres avancés » selon votre version de PrestaShop).

**Actions et paramètres disponibles :**
Cet écran présente généralement une grille (liste) de tous les termes de recherche enregistrés. Pour chaque entrée, vous verrez généralement :

-   **Mot-clé de recherche :** Le terme ou la phrase exacte que le client a tapé dans la barre de recherche.
-   **Nombre de recherches :** Le nombre de fois que ce mot-clé spécifique a été recherché.
-   **Date de la dernière recherche :** La date à laquelle ce mot-clé a été recherché le plus récemment.
-   **Nombre de résultats :** Le nombre de produits trouvés pour ce terme de recherche (ceci est crucial pour identifier les recherches « sans résultats »).

**Vue grille / gestion :**
La grille vous permet de :

-   **Trier :** Cliquez sur les en-têtes de colonne (par exemple, « Mot-clé de recherche », « Nombre de recherches ») pour trier la liste.
-   **Filtrer :** Utilisez les champs de filtre au-dessus des colonnes pour affiner la liste (par exemple, rechercher un mot-clé spécifique ou filtrer par nombre de résultats).
-   **Exporter :** Certaines versions peuvent offrir une option d'exportation pour télécharger les données afin de les analyser davantage dans un tableur.
-   **Supprimer :** Vous pouvez avoir des options pour supprimer des entrées de recherche individuelles ou vider l'intégralité du journal.

**Effet des modifications :**

-   **Visualisation de la liste :** Fournit des informations immédiates sur le comportement de recherche des clients.
-   **Tri/Filtrage :** Vous aide à identifier rapidement les recherches populaires, les recherches sans résultats ou les tendances au fil du temps.
-   **Suppression d'entrées :** Supprime les données du journal. Cela peut être utile pour nettoyer les entrées non pertinentes ou gérer la taille de la base de données, mais il est généralement préférable de conserver les données pour une analyse historique.

**Flux de travail recommandé pour la gestion quotidienne de la boutique :**

1.  **Vérifiez régulièrement cet écran :** Prenez l'habitude de consulter le « Journal de recherche » au moins une fois par semaine.
2.  **Concentrez-vous sur les recherches « Sans résultats » :** Priorisez les mots-clés qui n'ont donné aucun résultat. Ce sont vos plus grandes opportunités :
    - Avez-vous le produit mais il n'est pas correctement indexé ou la description est mauvaise ?
    - Est-ce un produit que vous devriez envisager de stocker ?
    - Est-ce une faute d'orthographe courante que vous pouvez prendre en compte avec des synonymes ?
3.  **Identifiez les recherches populaires :** Voyez ce qui intéresse le plus les clients. Assurez-vous que ces produits sont affichés de manière proéminente, bien décrits et facilement trouvables.
4.  **Analysez les tendances :** Y a-t-il des termes de recherche saisonniers ? De nouvelles idées de produits émergeant des requêtes des clients ?

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| :--- | :--- | :--- | :---
```yaml
title: "Journal de recherche - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Journal de recherche par MyPresta.eu."
sidebar:
  label: "Journal de recherche - Manuel du marchand et guide de configuration"
---

# Journal de recherche

## 1. Ce que fait ce module et pourquoi vous en avez besoin

Le module « Journal de recherche » est un outil d'administration essentiel qui enregistre chaque requête de recherche effectuée par vos clients sur votre boutique PrestaShop. Considérez-le comme une carte au trésor cachée de l'esprit de vos clients !

**Pourquoi vous en avez besoin :**

- **Comprendre la demande des clients :** Découvrez exactement quels produits ou informations vos clients recherchent, même s'ils ne les trouvent pas. Cela révèle une demande non satisfaite et de nouvelles opportunités de produits potentielles.
- **Améliorer le catalogue de produits et le référencement :** Si les clients recherchent fréquemment des termes qui ne donnent aucun résultat, cela indique des lacunes dans vos descriptions de produits, vos balises ou même vos offres de produits. Utilisez ces données pour optimiser les noms de vos produits, leurs descriptions et vos mots-clés SEO.
- **Identifier les produits manquants :** Repérez les termes de recherche populaires qui ne renvoient aucun résultat. C'est un signal clair qu'il vous manque peut-être un produit que vos clients désirent.
- **Améliorer l'expérience utilisateur :** En comprenant les modèles de recherche, vous pouvez affiner la navigation de votre boutique, créer de meilleures catégories et vous assurer que votre moteur de recherche interne fournit des résultats plus pertinents.
- **Augmenter les conversions :** Lorsque les clients trouvent rapidement ce qu'ils cherchent, ils sont plus susceptibles d'effectuer un achat. Ce module vous aide à affiner votre boutique pour répondre à leurs attentes.

Ce module est parfait pour tout détaillant en ligne cherchant à obtenir des informations plus approfondies sur le comportement des clients, à optimiser son catalogue de produits et, finalement, à augmenter ses ventes en offrant une meilleure expérience d'achat.

## 2. Où les clients le voient dans votre boutique (parcours Front-Office)

Le module « Journal de recherche » fonctionne entièrement en arrière-plan. Vos clients ne verront **aucun** changement visuel ni aucun nouvel élément sur le front-office de votre boutique. Il enregistre silencieusement leurs requêtes de recherche lorsqu'ils utilisent la barre de recherche existante de votre boutique.

- **Zones de placement :** Aucune visible.
- **Réactivité mobile :** Non applicable, car il s'agit d'un outil de journalisation backend.
- **Interaction avec l'acheteur :** Les acheteurs interagissent avec votre barre de recherche standard comme d'habitude ; le module enregistre simplement leur saisie.

## 3. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune exigence particulière au-delà d'un environnement d'hébergement PrestaShop standard.

## 4. Guide d'installation rapide et sécurisée

Suivez ces étapes pour installer rapidement et en toute sécurité le module « Journal de recherche » :

1.  **Téléchargez la dernière version depuis votre compte MyPresta.eu :**
    - Connectez-vous à votre compte client sur [Historique des commandes et téléchargements MyPresta.eu](https://mypresta.eu/my-account/orders/).
    - Le module « Journal de recherche » est disponible en plusieurs fichiers de package selon votre version de PrestaShop (par exemple, PrestaShop 8.x, 1.7.x, etc.).
    - Assurez-vous de télécharger le fichier ZIP spécifique désigné pour votre version de PrestaShop. NE DÉCOMPRESSEZ PAS le fichier sur votre ordinateur.
2.  **Ouvrez le Back Office de PrestaShop :**
    - Dans le panneau d'administration de votre boutique, naviguez vers **Modules > Gestionnaire de modules** (ou **Modules** / **Modules & Services** dans les versions antérieures).
3.  **Téléchargez l'archive du module :**
    - Cliquez sur le bouton **« Télécharger un module »** en haut à droite de la page.
    - Faites glisser et déposez votre fichier ZIP téléchargé dans la boîte, ou cliquez sur « sélectionner un fichier » pour le choisir depuis votre disque. PrestaShop vérifiera et installera le module automatiquement.
4.  **Accédez à la configuration du module :**
    - Une fois l'installation terminée, cliquez sur le bouton **« Configurer »** pour commencer à configurer vos options.

:::note
Assurez-vous toujours d'avoir une sauvegarde récente de votre boutique avant d'installer tout nouvel add-on.
:::

## 4. Parcours complet de configuration (chaque paramètre regroupé par écran)

### 4.1 Page de configuration du module (Back Office > Modules > Configurer > Journal de recherche)

Ceci est l'écran de configuration principal du module « Journal de recherche ». Il fournit une interface simple pour activer ou désactiver la fonctionnalité de journalisation.

- **Emplacement du menu :** Back Office > Modules > Gestionnaire de modules > Journal de recherche > Configurer

| Paramètre / Option | Ce que fait ce paramètre | Effet de la modification de ce paramètre | Valeur recommandée | Scénario / exemple pour le marchand |
| :--- | :---
