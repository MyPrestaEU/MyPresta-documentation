---
title: "MyQuill - Éditeur Quill - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop MyQuill - Éditeur Quill par MyPresta.eu."
sidebar:
  label: "MyQuill - Éditeur Quill"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module MyQuill - Quill editor sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/myquill-quill-editor.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/myquill-quill-editor/)
>
> ---


# MyQuill - Éditeur Quill

## 1. Exigences et compatibilité
- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes et généralement activées par défaut sur la plupart des environnements d'hébergement.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Après l'installation, cliquer sur "Configurer" vous mènera à l'écran de configuration principal de MyQuill. C'est ici que vous contrôlez le comportement de l'éditeur Quill dans votre Back Office.

#### **Onglet Paramètres généraux**

**1. Activer l'éditeur MyQuill**
-   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver l'éditeur MyQuill.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (OUI) :* L'éditeur Quill remplacera l'éditeur TinyMCE par défaut dans toutes les zones prises en charge de votre Back Office PrestaShop (par exemple, descriptions de produits, pages CMS, descriptions de catégories).
    -   *Lorsqu'il est désactivé (NON) :* L'éditeur TinyMCE par défaut sera restauré, et les fonctionnalités de MyQuill ne seront pas disponibles.
-   **Valeur recommandée :** **OUI** (pour utiliser les fonctionnalités du module).
-   **Scénario/exemple pour le marchand :** Si vous souhaitez revenir temporairement à TinyMCE pour des tests de compatibilité avec un autre module, vous désactiveriez MyQuill ici. Sinon, gardez-le activé pour profiter de l'éditeur avancé.

**2. Charger l'éditeur Quill sur le Front Office**
-   **Ce que fait ce paramètre :** Détermine si les ressources nécessaires de l'éditeur Quill (CSS, JS) sont chargées sur le front office de votre boutique. Cela n'est généralement nécessaire que si vous avez un thème personnalisé ou un autre module qui utilise Quill sur le front office.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (OUI) :* Les fichiers principaux de Quill seront inclus dans les pages publiques de votre boutique. Cela pourrait légèrement augmenter le temps de chargement des pages, mais est nécessaire si vous affichez du contenu généré par Quill qui nécessite son style ou sa fonctionnalité spécifique sur le front office.
    -   *Lorsqu'il est désactivé (NON) :* Les fichiers principaux de Quill ne seront *pas* chargés sur le front office, ce qui économise de la bande passante et peut potentiellement améliorer la vitesse de chargement des pages.
-   **Valeur recommandée :** **NON** (sauf si vous avez une raison spécifique de le charger, comme une fonctionnalité de thème personnalisée).
-   **Scénario/exemple pour le marchand :** Si vous utilisez un thème personnalisé qui affiche du contenu interactif (comme des accordéons ou des onglets) créé avec MyQuill, et que ces éléments ne s'affichent pas correctement, l'activation de ce paramètre pourrait résoudre le problème. Pour la plupart des boutiques, ce n'est pas nécessaire.

**3. Charger l'éditeur Quill sur le Back Office**
-   **Ce que fait ce paramètre :** Contrôle si les ressources de l'éditeur Quill sont chargées dans votre Back Office PrestaShop. C'est essentiel pour le fonctionnement du module.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (OUI) :* L'éditeur Quill se chargera et fonctionnera correctement dans votre Back Office.
    -   *Lorsqu'il est désactivé (NON) :* L'éditeur Quill ne se chargera pas, et vous verrez probablement une zone d'édition vide ou le TinyMCE par défaut. Cela désactive effectivement la fonctionnalité principale du module dans le Back Office.
-   **Valeur recommandée :** **OUI** (Ceci doit être activé pour que le module fonctionne).
-   **Scénario/exemple pour le marchand :** Vous devriez toujours garder ce paramètre activé. Le désactiver vous empêcherait d'utiliser les fonctionnalités de MyQuill dans le panneau d'administration.

**4. Hauteur de l'éditeur (en pixels)**
-   **Ce que fait ce paramètre :** Définit la hauteur par défaut de la zone de saisie de l'éditeur Quill en pixels.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est défini sur une valeur plus élevée (par exemple, 500px) :* L'éditeur apparaîtra plus grand, vous donnant plus d'espace vertical pour visualiser et modifier votre contenu sans faire défiler.
    -   *Lorsqu'il est défini sur une valeur plus basse (par exemple, 200px) :* L'éditeur sera plus court, ce qui peut être utile pour des sections de contenu plus courtes mais pourrait nécessiter plus de défilement pour des descriptions plus longues.
-   **Valeur recommandée :** **300px** (ou ajustez en fonction de votre préférence pour la longueur de contenu typique).
-   **Scénario/exemple pour le marchand :** Si vous écrivez fréquemment de très longues descriptions de produits, augmenter cela à 400px ou 500px pourrait rendre votre expérience d'édition plus confortable. Pour les titres de pages CMS courts, une hauteur plus petite pourrait suffire.

**5. Options de la barre d'outils de l'éditeur**
-   **Ce que fait ce paramètre :** Cela vous permet de personnaliser les outils qui apparaissent dans la barre d'outils de l'éditeur Quill. Vous pouvez sélectionner ou désélectionner divers boutons et fonctionnalités.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsque des options sont sélectionnées :* Les boutons correspondants (par exemple, gras, italique, image, vidéo, tableau) apparaîtront dans la barre d'outils de l'éditeur, rendant ces fonctions disponibles.
    -   *Lorsque des options sont désélectionnées :* Les boutons correspondants seront masqués de la barre d'outils, empêchant leur utilisation.
-   **Valeur recommandée :** Activez toutes les options initialement, puis désélectionnez les outils que vous êtes certain de ne jamais utiliser pour simplifier la barre d'outils.
-   **Scénario/exemple pour le marchand :** Si vous ne prévoyez jamais d'intégrer des vidéos, vous pouvez désélectionner l'option "YouTube/Vimeo" pour réduire l'encombrement de la barre d'outils. Si vous voulez vous assurer que votre équipe n'utilise que le formatage de base, vous pouvez limiter considérablement les options.

**6. Dossier de téléchargement d'images**
-   **Ce que fait ce paramètre :** Spécifie le dossier par défaut sur votre serveur où les images téléchargées via l'éditeur Quill seront stockées.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est défini sur un chemin spécifique (par exemple, `/img/cms/`) :* Toutes les images téléchargées via l'éditeur iront dans ce dossier.
    -   *Lorsqu'il est laissé par défaut (généralement `/img/cms/` ou similaire) :* Les images seront stockées dans le répertoire d'images CMS standard de PrestaShop.
-   **Valeur recommandée :** Laissez par défaut (`/img/cms/`) sauf si vous avez un besoin organisationnel spécifique de le modifier.
-   **Scénario/exemple pour le marchand :** Si vous souhaitez conserver les images spécifiques aux produits séparées des images des pages CMS, vous pouvez créer un nouveau dossier (par exemple, `/img/products_quill/`) et définir cette option en conséquence. Assurez-vous que le dossier existe et dispose des autorisations d'écriture.

**7. Activer la génération de liens SEO**
-   **Ce que fait ce paramètre :** Active une fonctionnalité qui vous aide à créer des liens optimisés pour le référencement dans votre contenu.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (OUI) :* L'outil de lien dans Quill offrira des options pour générer des liens propres et descriptifs, potentiellement en utilisant les noms de produits ou de catégories comme texte de lien.
    -   *Lorsqu'il est désactivé (NON) :* L'outil de lien se comportera comme un inséreur de lien standard sans améliorations SEO spécifiques.
-   **Valeur recommandée :** **OUI** (pour bénéficier d'une meilleure liaison interne pour le référencement).
-   **Scénario/exemple pour le marchand :** Lors de la création d'un lien vers un produit, au lieu de simplement coller l'URL, cette fonctionnalité pourrait vous aider à générer automatiquement un lien avec le nom du produit comme texte d'ancrage, ce qui est meilleur pour le référencement.

**8. Activer l'intégration YouTube/Vimeo**
-   **Ce que fait ce paramètre :** Vous permet d'intégrer des vidéos de YouTube et Vimeo directement dans votre contenu à l'aide de l'éditeur Quill.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (OUI) :* Un bouton ou une option dédiée apparaîtra dans la barre d'outils pour coller facilement les URL de vidéos et les intégrer.
    -   *Lorsqu'il est désactivé (NON) :* Vous ne pourrez pas utiliser l'outil d'intégration vidéo dédié.
-   **Valeur recommandée :** **OUI** (si vous prévoyez d'utiliser des vidéos dans votre contenu).
-   **Scénario/exemple pour le marchand :** Vous pouvez facilement ajouter une vidéo de démonstration de produit à une description de produit ou une vidéo d'histoire de marque à votre page "À propos de nous".

**9. Activer les tableaux**
-   **Ce que fait ce paramètre :** Ajoute la fonctionnalité de créer et de modifier des tableaux HTML dans l'éditeur Quill.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (OUI) :* Un outil de création de tableau sera disponible dans la barre d'outils, vous permettant d'insérer et de gérer des tableaux (ajouter des lignes/colonnes, fusionner des cellules, etc.).
    -   *Lorsqu'il est désactivé (NON) :* L'outil de tableau sera masqué.
-   **Valeur recommandée :** **OUI** (les tableaux sont utiles pour afficher des données structurées comme des spécifications ou des comparaisons).
-   **Scénario/exemple pour le marchand :** Utilisez des tableaux pour afficher les spécifications de produits, les tableaux comparatifs ou les informations sur les tarifs d'expédition sur une page CMS.

**10. Activer les boutons Bootstrap**
-   **Ce que fait ce paramètre :** Fournit un outil pour insérer facilement des boutons de style Bootstrap dans votre contenu, qui peuvent être utilisés pour des appels à l'action.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (OUI) :* Un outil de bouton apparaîtra, vous permettant de choisir les styles de bouton (primaire, secondaire, succès, etc.) et de les lier.
    -   *Lorsqu'il est désactivé (NON) :* L'outil de bouton sera masqué.
-   **Valeur recommandée :** **OUI** (pour des appels à l'action clairs).
-   **Scénario/exemple pour le marchand :** Ajoutez un bouton "Acheter maintenant" à une bannière promotionnelle sur une page CMS ou un bouton "Télécharger le PDF" aux spécifications techniques d'un produit.

**11. Activer les onglets**
-   **Ce que fait ce paramètre :** Vous permet de créer des sections de contenu à onglets, utiles pour organiser de grandes quantités d'informations de manière compacte.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (OUI) :* Un outil de création d'onglets sera disponible, vous permettant de définir les titres et le contenu de chaque onglet.
    -   *Lorsqu'il est désactivé (NON) :* L'outil d'onglets sera masqué.
-   **Valeur recommandée :** **OUI** (pour une meilleure organisation du contenu).
-   **Scénario/exemple pour le marchand :** Sur une page produit, utilisez des onglets pour "Description", "Spécifications", "Avis" et "Informations de livraison" pour garder la page propre.

**12. Activer les galeries**
-   **Ce que fait ce paramètre :** Intègre une fonctionnalité pour créer de simples galeries d'images dans votre contenu.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (OUI) :* Un outil de galerie apparaîtra, vous permettant de sélectionner plusieurs images et de les organiser en galerie.
    -   *Lorsqu'il est désactivé (NON) :* L'outil de galerie sera masqué.
-   **Valeur recommandée :** **OUI** (pour des affichages d'images visuellement attrayants).
-   **Scénario/exemple pour le marchand :** Présentez plusieurs angles d'un produit ou une collection d'images de style de vie sur une page CMS.

**13. Activer la FAQ (Accordéon)**
-   **Ce que fait ce paramètre :** Ajoute un outil pour créer des sections FAQ interactives à l'aide d'un format accordéon (extensible/réductible).
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (OUI) :* Un outil FAQ sera disponible, vous permettant d'ajouter des paires de questions-réponses que les utilisateurs peuvent développer ou réduire.
    -   *Lorsqu'il est désactivé (NON) :* L'outil FAQ sera masqué.
-   **Valeur recommandée :** **OUI** (excellent pour les pages de support ou les FAQ de produits).
-   **Scénario/exemple pour le marchand :** Créez une page CMS dédiée aux "Questions fréquemment posées" ou ajoutez une petite section FAQ à une page produit pour répondre aux questions courantes des clients.

#### **Bouton Enregistrer**
-   **Ce que cela fait :** Après avoir apporté des modifications aux paramètres de cette page, vous **devez** cliquer sur le bouton "Enregistrer" pour les appliquer.
-   **Effet du clic :** Vos modifications seront stockées dans la base de données, et l'éditeur Quill reflétera ces nouveaux paramètres la prochaine fois que vous l'ouvrirez dans le Back Office.
-   **Action recommandée :** Cliquez toujours sur "Enregistrer" après avoir modifié un paramètre.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

MyQuill s'intègre principalement directement dans les écrans d'édition de contenu PrestaShop existants (comme les formulaires d'édition de produits, de catégories et de pages CMS). Il n'introduit pas de nouveaux éléments de menu de niveau supérieur ni d'écrans de gestion de données dédiés pour son propre contenu. Les contrôleurs "AdminMyquillAjaxController" et "index.php" sont des composants internes gérant les opérations en arrière-plan du module, telles que les téléchargements d'images ou le chargement de contenu dynamique pour les fonctionnalités de l'éditeur.

Par conséquent, il n'y a pas d'écran "AdminMyquill" séparé à gérer. Toutes les interactions se déroulent directement dans les formulaires d'édition de contenu où Quill remplace TinyMCE.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
|---|---|---|---|
| **Page de configuration du module** | Activer l'éditeur MyQuill | OUI | Active/désactive l'éditeur Quill dans le BO. |
| | Charger l'éditeur Quill sur le Front Office | NON | Charge les ressources Quill sur le FO (uniquement si nécessaire par le thème/module). |
| | Charger l'éditeur Quill sur le Back Office | OUI | Charge les ressources Quill dans le BO (essentiel pour le fonctionnement du module). |
| | Hauteur de l'éditeur (en pixels) | 300px | Définit la taille verticale de la fenêtre de l'éditeur. |
| | Options de la barre d'outils de l'éditeur | Toutes activées | Personnalise les outils qui apparaissent dans la barre d'outils de l'éditeur. |
| | Dossier de téléchargement d'images | `/img/cms/` | Spécifie où les images téléchargées sont stockées. |
| | Activer la génération de liens SEO | OUI | Ajoute des fonctionnalités pour créer des liens optimisés pour le référencement. |
| | Activer l'intégration YouTube/Vimeo | OUI | Permet d'intégrer des vidéos de YouTube/Vimeo. |
| | Activer les tableaux | OUI | Ajoute la fonctionnalité de créer et de modifier des tableaux HTML. |
| | Activer les boutons Bootstrap | OUI | Fournit un outil pour insérer des boutons de style Bootstrap. |
| | Activer les onglets | OUI | Permet de créer des sections de contenu à onglets. |
| | Activer les galeries | OUI | Intègre une fonctionnalité pour créer des galeries d'images. |
| | Activer la FAQ (Accordéon) | OUI | Ajoute un outil pour créer des sections FAQ interactives. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Après l'installation de MyQuill, la zone de l'éditeur est vide ou affiche toujours TinyMCE.**
*   **R :** Tout d'abord, assurez-vous que "Activer l'éditeur MyQuill" et "Charger l'éditeur Quill sur le Back Office" sont tous deux réglés sur **OUI** dans la configuration du module. Deuxièmement, videz votre cache PrestaShop : Allez dans **Paramètres avancés > Performances**, puis cliquez sur "Vider le cache" en haut à droite. Videz également le cache de votre navigateur.

**Q2 : Mes images ne se téléchargent pas, ou je ne peux pas les voir après le téléchargement.**
*   **R :** Vérifiez le paramètre "Dossier de téléchargement d'images" dans la configuration de MyQuill. Assurez-vous que le dossier spécifié existe sur votre serveur (par exemple, `/img/cms/`) et qu'il dispose des autorisations d'écriture correctes (généralement 755 ou 775). Si le dossier n'existe pas, créez-le via FTP/SFTP.

**Q3 : Certains boutons de la barre d'outils (par exemple, Tableaux, Vidéos) sont manquants dans l'éditeur.**
*   **R :** Allez sur la page de configuration de MyQuill et vérifiez la section "Options de la barre d'outils de l'éditeur". Assurez-vous que les fonctionnalités spécifiques que vous souhaitez utiliser (par exemple, "Activer les tableaux", "Activer l'intégration YouTube/Vimeo") sont réglées sur **OUI**. Enregistrez vos modifications et videz le cache.

**Q4 : Le contenu créé avec MyQuill (comme les onglets ou les accordéons) ne s'affiche pas correctement sur mon front office.**
*   **R :** Cela se produit souvent si votre thème n'inclut pas le CSS ou le JavaScript nécessaire pour ces éléments interactifs. Essayez d'activer "Charger l'éditeur Quill sur le Front Office" dans la configuration de MyQuill. Si le problème persiste, votre thème pourrait nécessiter des bibliothèques Bootstrap ou JavaScript spécifiques qui ne sont pas chargées par défaut ou qui sont en conflit. Dans ce cas, vous pourriez avoir besoin d'un webmaster pour enquêter.

**Q5 : Comment revenir à l'éditeur TinyMCE par défaut ?**
*   **R :** Allez simplement dans **Modules > Gestionnaire de modules**, trouvez "MyQuill - Éditeur Quill", et cliquez sur le bouton "Désactiver". Tout le contenu précédemment créé avec MyQuill sera toujours là, mais l'interface d'édition reviendra à TinyMCE. Vous pouvez réactiver MyQuill à tout moment.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)
Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture
Le module MyQuill intègre l'éditeur de texte enrichi Quill.js dans le Back Office de PrestaShop, remplaçant le TinyMCE par défaut. Il y parvient en se raccordant au hook `displayBackOfficeHeader` pour injecter ses ressources, puis en utilisant JavaScript pour cibler et initialiser les instances Quill sur les éléments textarea pertinents. Le module offre des fonctionnalités améliorées telles que le téléchargement d'images, l'intégration de vidéos et des blocs de contenu personnalisés (tableaux, onglets, galeries, FAQ) en étendant la fonctionnalité de Quill et en fournissant des points d'accès AJAX pour les opérations côté serveur. Il évite les surcharges de fichiers du cœur, garantissant la compatibilité et une désinstallation facile.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :
    Le module n'inclut aucun contrôleur front-office dédié. Toutes les fonctionnalités front-office liées à l'affichage du contenu généré par Quill sont gérées par le rendu du thème du contenu PrestaShop standard (descriptions de produits, pages CMS, etc.) et le chargement optionnel des ressources front-office de MyQuill via des hooks.

-   **Contrôleurs d'administration Back-Office** :
    *   `controllers/admin/AdminMyquillAjaxController.php`
        *   **Nom de la classe et classe parente** : `AdminMyquillAjaxController` étend `ModuleAdminController`.
        *   **Responsabilité** : Ce contrôleur gère les requêtes AJAX provenant de l'éditeur Quill dans le Back Office. Son rôle principal est de gérer les opérations côté serveur telles que le téléchargement d'images, en s'assurant qu'elles sont correctement stockées dans le répertoire désigné et en renvoyant l'URL pour l'insertion dans l'éditeur. Il peut également gérer d'autres requêtes de données dynamiques pour des plugins Quill spécifiques (par exemple, la récupération de données de produits pour les liens SEO).
    *   `controllers/admin/index.php`
        *   **Nom de la classe et classe parente** : Ce fichier contient généralement une simple instruction `die('Access Denied');` ou une mesure de sécurité similaire.
        *   **Responsabilité** : C'est une pratique standard de PrestaShop d'inclure un fichier `index.php` dans chaque répertoire pour empêcher la liste des répertoires et l'accès direct. Il ne contient aucune logique de contrôleur fonctionnelle pour le module.

### 4.3 Classes et modèles du cœur (`classes/`)
Le module MyQuill n'introduit aucune classe `ObjectModel` personnalisée ni table de base de données. Il fonctionne principalement en remplaçant l'interface de l'éditeur et en stockant sa configuration dans `ps_configuration`. Le contenu créé avec Quill est stocké directement dans les champs de contenu existants de PrestaShop (par exemple, `ps_product_lang.description`, `ps_cms_lang.content`) en tant que HTML standard.

### 4.4 Ressources JavaScript (`views/js/`)

-   `views/js/myquill-admin.js`
    *   **Portée** : Back-office.
    *   **Détail** : Il s'agit du fichier JavaScript administratif principal. Il est responsable de l'initialisation de l'éditeur Quill sur tous les éléments textarea pertinents dans le Back Office de PrestaShop. Il lit les paramètres de configuration du module (hauteur de l'éditeur, options de la barre d'outils, fonctionnalités activées) et construit dynamiquement l'instance Quill avec les modules et gestionnaires appropriés. Il contient également la logique d'intégration des boutons de barre d'outils personnalisés et de gestion de leurs actions (par exemple, ouverture de boîtes de dialogue de téléchargement d'images, insertion d'intégrations vidéo).
-   `views/js/myquill-editor.js`
    *   **Portée** : Back-office.
    *   **Détail** : Ce fichier contient probablement la bibliothèque Quill.js elle-même ou des personnalisations/extensions spécifiques à l'éditeur Quill de base. Il définit le comportement fondamental de l'éditeur, le rendu et l'API.
-   `views/js/myquill-front.js`
    *   **Portée** : Front-office.
    *   **Détail** : Ce script est chargé conditionnellement sur le front office si le paramètre "Charger l'éditeur Quill sur le Front Office" est activé. Il contient le JavaScript nécessaire pour rendre les éléments interactifs créés avec Quill (comme les onglets, les accordéons, les galeries) fonctionnels côté client de la boutique. Il peut inclure des écouteurs pour les événements de clic sur les en-têtes d'onglets ou les titres d'accordéons pour basculer la visibilité du contenu.
-   `views/js/myquill-plugins.js`
    *   **Portée** : Back-office.
    *   **Détail** : Ce fichier encapsule la logique JavaScript pour divers plugins et extensions personnalisés ajoutés à Quill par MyQuill. Cela inclut l'implémentation de fonctionnalités telles que la gestion du téléchargement d'images, l'intégration de vidéos, la création de tableaux, les boutons Bootstrap, les onglets, les galeries et les accordéons FAQ. Il définit la façon dont ces "blots" personnalisés (terme de Quill pour les blocs de contenu personnalisés) sont rendus et comment leurs actions de barre d'outils associées se comportent.
-   `views/js/myquill-pro.js`
    *   **Portée** : Back-office.
    *   **Détail** : Ce fichier contient probablement des fonctionnalités et des améliorations avancées ou "pro" pour l'éditeur Quill, potentiellement basées sur `myquill-plugins.js`. Il pourrait inclure des éléments d'interface utilisateur plus sophistiqués, des options de formatage supplémentaires ou d'autres intégrations spécifiques à la version MyPresta.eu du module.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `views/css/myquill-admin.css`
    *   **Portée** : Style des formulaires d'administration du Back-office.
    *   **Détail** : Contient des styles spécifiques à l'apparence de l'éditeur Quill dans le Back Office de PrestaShop. Cela inclut le style de la barre d'outils, du conteneur de l'éditeur, des boîtes de dialogue personnalisées et garantit que l'éditeur s'intègre visuellement au thème d'administration de PrestaShop.
-   `views/css/myquill-editor.css`
    *   **Portée** : Style des formulaires d'administration du Back-office.
    *   **Détail** : Ce fichier contient probablement le CSS de base de l'éditeur Quill lui-même, définissant les styles de base pour le formatage du texte, les citations, les listes et d'autres éléments Quill standard. Il peut également inclure des styles pour les blots personnalisés (par exemple, tableaux, boutons) lorsqu'ils sont rendus dans l'éditeur.
-   `views/css/myquill-front.css`
    *   **Portée** : Style client du Front-office.
    *   **Détail** : Cette feuille de style est chargée conditionnellement sur le front office si le paramètre correspondant est activé. Elle fournit le CSS nécessaire pour rendre correctement les éléments interactifs créés avec MyQuill (comme les onglets, les accordéons, les galeries) sur la boutique côté client. Les développeurs peuvent remplacer ces styles dans le `custom.css` ou `theme.css` de leur thème pour correspondre à leur marque.
-   `views/css/quill.snow.css`
    *   **Portée** : Style des formulaires d'administration du Back-office.
    *   **Détail** : Il s'agit de la feuille de style standard du thème "Snow" pour Quill.js. Elle fournit l'apparence visuelle par défaut de la barre d'outils et de la zone de contenu de l'éditeur Quill, y compris les icônes, les styles de boutons et le formatage de base. C'est un composant essentiel de Quill.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :
    *   `bo-header.tpl`
        *   **Hook** : `displayBackOfficeHeader`
        *   **Sortie** : Ce template est responsable de l'injection des ressources CSS et JavaScript nécessaires (Quill core, JS/CSS spécifiques au module) dans la section `<head>` des pages du Back Office où l'éditeur est nécessaire. Il inclut dynamiquement les fichiers en fonction de la configuration du module.
-   **Templates d'administration (`views/templates/admin/`)** :
    *   `configure.tpl`
        *   **Sortie** : Ce template rend le formulaire de configuration principal du module MyQuill, accessible via **Modules > Gestionnaire de modules > Configurer**. Il affiche tous les paramètres décrits dans la Section 4.1, y compris les interrupteurs, les champs de saisie et le bouton "Enregistrer".
    *   `preview.tpl`
        *   **Sortie** : Ce template pourrait être utilisé pour une fonctionnalité de prévisualisation dans le Back Office, montrant potentiellement à quoi ressemblerait le contenu généré par Quill sur le front office. Son utilisation exacte dépendrait de l'implémentation interne du module pour la prévisualisation du contenu.

-   **Templates Front-office (`views/templates/front/`)** :
    Le module n'inclut aucun template front-office dédié. Tout le contenu généré par Quill est rendu dans les templates de thème PrestaShop existants (par exemple, `product.tpl`, `cms.tpl`) en insérant la sortie HTML brute de l'éditeur.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** :
    Le module MyQuill ne crée aucune table de base de données personnalisée. Tous ses paramètres de configuration sont stockés dans la table `ps_configuration` en utilisant des clés généralement préfixées par `MYQUILL_`. Le contenu créé avec l'éditeur est stocké dans les tables de contenu PrestaShop standard (par exemple, `ps_product_lang`, `ps_cms_lang`).

-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | But technique |
|---|---|---|
| `displayBackOfficeHeader` | Exécuté dans le `<head>` des pages du Back Office. | Injecte les ressources CSS et JavaScript de MyQuill (éditeur Quill, plugins, styles d'administration) dans le Back Office pour initialiser l'éditeur. |
| `displayHeader` | Exécuté dans le `<head>` des pages du Front Office. | Injecte conditionnellement les ressources CSS et JavaScript front-office de MyQuill si "Charger l'éditeur Quill sur le Front Office" est activé, pour garantir que les éléments interactifs (onglets, accordéons) fonctionnent correctement. |
| `displayFooter` | Exécuté à la fin du `<body>` des pages du Front Office. | Potentiellement utilisé pour injecter des scripts à chargement tardif ou des ressources supplémentaires pour les éléments interactifs front-office, si non géré par `displayHeader`. |
| `displayProductExtraContent` | Exécuté sur la page produit. | Permet d'injecter des blocs de contenu supplémentaires sur la page produit, potentiellement utile pour du contenu personnalisé généré par Quill si le module était étendu pour gérer directement de tels blocs. (Moins susceptible d'être directement utilisé par la fonction de remplacement de l'éditeur de base de MyQuill, mais disponible pour les extensions). |
| `displayLeftColumn` | Exécuté dans la colonne de gauche des pages du Front Office. | Similaire à `displayProductExtraContent`, fournit un hook pour injecter du contenu dans la colonne de gauche. |
| `displayRightColumn` | Exécuté dans la colonne de droite des pages du Front Office. | Similaire à `displayProductExtraContent`, fournit un hook pour injecter du contenu dans la colonne de droite. |

## 5. Support officiel et mises à jour
Pour les dernières mises à jour, corrections de bugs et support officiel du module MyQuill - Éditeur Quill, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Vous pouvez télécharger les dernières versions depuis votre historique de commandes et accéder aux ressources de support directement depuis le site web de MyPresta.eu.
