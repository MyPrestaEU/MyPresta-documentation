---
title: "Galerie Photo Client - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Galerie Photo Client par MyPresta.eu."
sidebar:
  label: "Galerie Photo Client - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Customer Photo Gallery sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/customer-photo-gallery.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/customer-photo-gallery/)
>
> ---


# Galerie Photo Client

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et toute interaction avec les modules. Assurez-vous que votre serveur dispose d'un espace disque suffisant pour stocker les photos et vidéos téléchargées.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module Galerie Photo Client, où vous contrôlez toutes ses fonctionnalités et son apparence dans votre boutique.

| Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- |
| **Autoriser les téléchargements JPEG** | OUI | **Ce que fait ce paramètre :** Contrôle si les clients peuvent télécharger des images au format JPEG.   **Effet de la modification de ce paramètre :**   *Si activé :* Les clients peuvent télécharger des fichiers .jpg et .jpeg.   *Si désactivé :* Les fichiers JPEG seront rejetés lors du téléchargement.   **Valeur recommandée :** OUI (JPEG est un format d'image très courant).   **Scénario marchand :** Si vous souhaitez restreindre les types d'images pour des raisons spécifiques de qualité ou de marque, vous pouvez désactiver certains formats. |
| **Autoriser les téléchargements GIF** | OUI | **Ce que fait ce paramètre :** Contrôle si les clients peuvent télécharger des images au format GIF.   **Effet de la modification de ce paramètre :**   *Si activé :* Les clients peuvent télécharger des fichiers .gif.   *Si désactivé :* Les fichiers GIF seront rejetés.   **Valeur recommandée :** OUI (les GIF peuvent être utiles pour des animations simples ou des arrière-plans transparents). |
| **Autoriser les téléchargements PNG** | OUI | **Ce que fait ce paramètre :** Contrôle si les clients peuvent télécharger des images au format PNG.   **Effet de la modification de ce paramètre :**   *Si activé :* Les clients peuvent télécharger des fichiers .png.   *Si désactivé :* Les fichiers PNG seront rejetés.   **Valeur recommandée :** OUI (le PNG est excellent pour les images avec transparence et de haute qualité). |
| **Autoriser les téléchargements BMP** | NON | **Ce que fait ce paramètre :** Contrôle si les clients peuvent télécharger des images au format BMP.   **Effet de la modification de ce paramètre :**   *Si activé :* Les clients peuvent télécharger des fichiers .bmp.   *Si désactivé :* Les fichiers BMP seront rejetés.   **Valeur recommandée :** NON (les fichiers BMP sont généralement très volumineux et non compressés, pas idéaux pour une utilisation web).   **Scénario marchand :** N'activez que si vous avez un besoin spécifique d'images non compressées, mais soyez conscient de l'impact sur le stockage du serveur et les temps de chargement des pages. |
| **Activer la pagination** | OUI | **Ce que fait ce paramètre :** Détermine si les pages de la galerie utiliseront la pagination (par exemple, "Page 1 sur 5").   **Effet de la modification de ce paramètre :**   *Si activé :* Le contenu de la galerie est divisé en plusieurs pages, améliorant les temps de chargement pour les grandes galeries.   *Si désactivé :* Tout le contenu de la galerie se charge sur une seule page, ce qui peut être lent pour de nombreuses photos.   **Valeur recommandée :** OUI.   **Scénario marchand :** Essentiel pour gérer de grandes galeries et offrir une expérience utilisateur fluide. |
| **Autoriser les utilisateurs non connectés à télécharger** | NON | **Ce que fait ce paramètre :** Permet aux visiteurs qui ne sont pas connectés à un compte client de télécharger des photos.   **Effet de la modification de ce paramètre :**   *Si activé :* Les invités peuvent télécharger des photos. Cela peut augmenter les contributions mais peut également entraîner plus de spam ou de contenu non pertinent.   *Si désactivé :* Seuls les clients connectés peuvent télécharger des photos, assurant un certain niveau de responsabilité.   **Valeur recommandée :** NON (sauf si vous avez une modération stricte en place).   **Scénario marchand :** Si vous souhaitez maximiser les contributions et êtes prêt à modérer, activez ceci. Sinon, laissez-le désactivé pour maintenir le contrôle qualité. |
| **Taille maximale du fichier (Mo)** | 5 | **Ce que fait ce paramètre :** Définit la taille maximale (en mégaoctets) pour le téléchargement d'un seul fichier image.   **Effet de la modification de ce paramètre :**   *Si défini sur une valeur plus élevée :* Les clients peuvent télécharger des images plus grandes, potentiellement de meilleure qualité, mais cela consomme plus d'espace serveur et de bande passante.   *Si défini sur une valeur plus basse :* Restreint la taille du fichier, économisant les ressources du serveur mais limitant potentiellement la qualité de l'image.   **Valeur recommandée :** 5-10 Mo est généralement suffisant pour les images optimisées pour le web.   **Scénario marchand :** Équilibrez la qualité de l'image avec les ressources du serveur. Trop bas, et les clients pourraient être frustrés ; trop haut, et vos coûts d'hébergement pourraient augmenter. |
| **Activer l'onglet produit** | NON | **Ce que fait ce paramètre :** Affiche un onglet dédié "Photos des clients" sur les pages produits.   **Effet de la modification de ce paramètre :**   *Si activé :* Un nouvel onglet apparaît sur les pages produits, présentant des photos spécifiquement liées à ce produit.   *Si désactivé :* Pas d'onglet dédié pour les photos des clients sur les pages produits.   **Valeur recommandée :** OUI (si vous souhaitez afficher du CGU spécifique au produit).   **Scénario marchand :** Idéal pour les produits où les témoignages visuels ont un impact élevé, comme la mode ou la décoration intérieure. |
| **Position de l'onglet produit (Hook du module)** | displayProductExtraContent | **Ce que fait ce paramètre :** Détermine où l'onglet produit est accroché sur la page produit.   **Effet de la modification de ce paramètre :** Modifie le placement visuel de l'onglet "Photos des clients" sur la page produit.   **Valeur recommandée :** `displayProductExtraContent` ou `displayProductTab`.   **Scénario marchand :** Testez différents hooks pour trouver la meilleure intégration visuelle avec votre thème. |
| **Afficher dans le pied de page du produit** | NON | **Ce que fait ce paramètre :** Affiche un bloc de photos de clients dans la zone de pied de page des pages produits.   **Effet de la modification de ce paramètre :**   *Si activé :* Un petit bloc de galerie apparaît en bas des pages produits.   *Si désactivé :* Pas de photos de clients dans le pied de page du produit.   **Valeur recommandée :** NON (sauf si vous avez un besoin de conception spécifique).   **Scénario marchand :** Peut être utilisé pour encourager la navigation ou la vente croisée en affichant des photos de clients connexes. |
| **Afficher dans le compte client** | OUI | **Ce que fait ce paramètre :** Ajoute un lien vers "Mes photos" dans le tableau de bord du compte client.   **Effet de la modification de ce paramètre :**   *Si activé :* Les clients connectés voient un lien pour gérer leurs photos téléchargées.   *Si désactivé :* Les clients ne peuvent pas facilement accéder à leur zone de gestion de photos depuis leur compte.   **Valeur recommandée :** OUI.   **Scénario marchand :** Essentiel pour que les clients gèrent leurs contributions. |
| **Afficher dans le bloc Mon compte** | OUI | **Ce que fait ce paramètre :** Ajoute un lien vers "Mes photos" dans le bloc "Mon compte" (généralement dans la colonne gauche/droite ou le pied de page).   **Effet de la modification de ce paramètre :**   *Si activé :* Un lien apparaît dans le bloc d'accès rapide "Mon compte".   *Si désactivé :* Pas de lien dans le bloc "Mon compte".   **Valeur recommandée :** OUI.   **Scénario marchand :** Fournit un autre point d'accès pratique pour que les clients gèrent leurs photos. |
| **Hauteur des miniatures (px)** | 100 | **Ce que fait ce paramètre :** Définit la hauteur des miniatures générées pour les images de la galerie.   **Effet de la modification de ce paramètre :**   *Si défini sur une valeur plus élevée :* Miniatures plus grandes, potentiellement plus claires mais occupant plus d'espace.   *Si défini sur une valeur plus basse :* Miniatures plus petites, économisant de l'espace mais moins de détails.   **Valeur recommandée :** 100-150px.   **Scénario marchand :** Ajustez pour s'adapter à la conception de votre thème et assurer une disposition de galerie visuellement attrayante. |
| **Largeur des miniatures (px)** | 100 | **Ce que fait ce paramètre :** Définit la largeur des miniatures générées pour les images de la galerie.   **Effet de la modification de ce paramètre :**   *Si défini sur une valeur plus élevée :* Miniatures plus grandes.   *Si défini sur une valeur plus basse :* Miniatures plus petites.   **Valeur recommandée :** 100-150px.   **Scénario marchand :** Ajustez pour s'adapter à la conception de votre thème et assurer une disposition de galerie visuellement attrayante. |
| **Activer le formulaire de téléchargement de photos** | OUI | **Ce que fait ce paramètre :** Contrôle la visibilité du formulaire de téléchargement de photos sur la page de la galerie.   **Effet de la modification de ce paramètre :**   *Si activé :* Les clients peuvent voir et utiliser le formulaire de téléchargement.   *Si désactivé :* Le formulaire de téléchargement est masqué, empêchant de nouvelles soumissions.   **Valeur recommandée :** OUI (sauf si vous souhaitez temporairement arrêter les nouveaux téléchargements).   **Scénario marchand :** Désactivez si vous organisez un concours avec une date limite de soumission ou si vous devez suspendre les téléchargements pour maintenance. |
| **Afficher le lien de la galerie** | OUI | **Ce que fait ce paramètre :** Ajoute un lien vers la page principale de la galerie de photos dans la navigation de votre boutique.   **Effet de la modification de ce paramètre :**   *Si activé :* Un lien (par exemple, "Galerie client") apparaît dans le hook choisi.   *Si désactivé :* Le lien vers la page principale de la galerie est masqué.   **Valeur recommandée :** OUI.   **Scénario marchand :** Essentiel pour que les clients trouvent et parcourent la galerie. |
| **Afficher dans la colonne de droite** | NON | **Ce que fait ce paramètre :** Affiche un bloc avec des photos de clients récentes dans la colonne de droite de votre boutique.   **Effet de la modification de ce paramètre :**   *Si activé :* Un bloc apparaît dans la colonne de droite.   *Si désactivé :* Pas de bloc dans la colonne de droite.   **Valeur recommandée :** NON (peut encombrer la mise en page, mais dépend de votre thème).   **Scénario marchand :** Utile si votre thème a beaucoup d'espace dans la colonne de droite et que vous souhaitez mettre en évidence les contributions récentes. |
| **Afficher dans la colonne de gauche** | NON | **Ce que fait ce paramètre :** Affiche un bloc avec des photos de clients récentes dans la colonne de gauche de votre boutique.   **Effet de la modification de ce paramètre :**   *Si activé :* Un bloc apparaît dans la colonne de gauche.   *Si désactivé :* Pas de bloc dans la colonne de gauche.   **Valeur recommandée :** NON (peut encombrer la mise en page, mais dépend de votre thème).   **Scénario marchand :** Similaire à la colonne de droite, utilisez si votre thème le supporte bien. |
| **Activer les notifications** | OUI | **Ce que fait ce paramètre :** Envoie des notifications par e-mail à l'administrateur de la boutique lorsque de nouvelles photos sont téléchargées.   **Effet de la modification de ce paramètre :**   *Si activé :* Vous recevez un e-mail pour chaque nouveau téléchargement, permettant une modération rapide.   *Si désactivé :* Pas de notifications par e-mail.   **Valeur recommandée :** OUI.   **Scénario marchand :** Crucial pour une modération rapide et pour s'assurer que seul le contenu approprié est affiché. |
| **Nombre de photos sur la page d'accueil** | 8 | **Ce que fait ce paramètre :** Définit le nombre de photos de clients affichées dans le bloc de la page d'accueil.   **Effet de la modification de ce paramètre :** Modifie la quantité de photos affichées sur la page d'accueil.   **Valeur recommandée :** 6-12, selon la mise en page de votre page d'accueil.   **Scénario marchand :** Ajustez pour s'adapter à la conception de votre page d'accueil sans surcharger la page. |
| **Ordre des photos sur la page d'accueil** | Les plus récentes en premier | **Ce que fait ce paramètre :** Détermine l'ordre de tri des photos affichées sur la page d'accueil.   **Effet de la modification de ce paramètre :** Les photos peuvent être classées par les plus récentes, les plus anciennes, les plus populaires, etc.   **Valeur recommandée :** Les plus récentes en premier ou Les plus populaires.   **Scénario marchand :** "Les plus récentes en premier" maintient le contenu frais ; "Les plus populaires" met en évidence le contenu engageant. |
| **Activer le mode concours photo** | NON | **Ce que fait ce paramètre :** Active les fonctionnalités pour organiser un concours photo, incluant potentiellement des mécanismes de vote et de prix.   **Effet de la modification de ce paramètre :**   *Si activé :* Des options supplémentaires liées au concours peuvent apparaître, et la galerie peut mettre l'accent sur le vote.   *Si désactivé :* Mode galerie standard.   **Valeur recommandée :** NON (sauf si vous organisez activement un concours).   **Scénario marchand :** Utilisez ceci lorsque vous souhaitez lancer une campagne spécifique pour collecter des photos et engager les utilisateurs avec le vote. |
| **Exclure des produits de la galerie** | (ID des produits) | **Ce que fait ce paramètre :** Vous permet de spécifier les ID de produits pour lesquels les photos des clients ne doivent PAS être affichées sur leurs pages produits.   **Effet de la modification de ce paramètre :** Les photos de ces produits spécifiques n'apparaîtront pas dans l'onglet/pied de page du produit, même si le paramètre principal de l'onglet produit est activé.   **Valeur recommandée :** Laissez vide sauf si nécessaire.   **Scénario marchand :** Si vous avez des produits sensibles, ou des produits pour lesquels les photos des clients sont non pertinentes ou inappropriées, vous pouvez les exclure. |
| **Visibilité du lien du compte client** | OUI | **Ce que fait ce paramètre :** Contrôle la visibilité du lien "Mes photos" dans le tableau de bord du compte client.   **Effet de la modification de ce paramètre :**   *Si activé :* Le lien est visible.   *Si désactivé :* Le lien est masqué.   **Valeur recommandée :** OUI.   **Scénario marchand :** Laissez activé pour la commodité du client. |
| **Visibilité du lien du bloc Mon compte** | OUI | **Ce que fait ce paramètre :** Contrôle la visibilité du lien "Mes photos" dans le bloc "Mon compte" (par exemple, dans les colonnes).   **Effet de la modification de ce paramètre :**   *Si activé :* Le lien est visible.   *Si désactivé :* Le lien est masqué.   **Valeur recommandée :** OUI.   **Scénario marchand :** Laissez activé pour la commodité du client. |
| **Activer le vote pour les photos** | OUI | **Ce que fait ce paramètre :** Permet aux clients (et éventuellement aux invités) de voter sur les photos téléchargées.   **Effet de la modification de ce paramètre :**   *Si activé :* Des boutons/étoiles de vote apparaissent à côté des photos.   *Si désactivé :* Pas de fonctionnalité de vote.   **Valeur recommandée :** OUI (augmente l'engagement).   **Scénario marchand :** Utilisez pour identifier les photos populaires, organiser des concours ou simplement encourager l'interaction. |
| **Type de système de vote** | Étoiles | **Ce que fait ce paramètre :** Choisit le style visuel du système de vote (par exemple, étoiles, pouces haut/bas).   **Effet de la modification de ce paramètre :** Modifie l'apparence du mécanisme de vote.   **Valeur recommandée :** Étoiles (généralement plus intuitif).   **Scénario marchand :** Sélectionnez le style qui correspond le mieux à l'esthétique de votre boutique. |
| **Autoriser les utilisateurs non connectés à voter** | NON | **Ce que fait ce paramètre :** Permet aux visiteurs non connectés de voter sur les photos.   **Effet de la modification de ce paramètre :**   *Si activé :* Les invités peuvent voter. Cela peut augmenter la participation mais peut être susceptible d'abus.   *Si désactivé :* Seuls les clients connectés peuvent voter.   **Valeur recommandée :** NON (pour éviter la manipulation des votes).   **Scénario marchand :** N'activez que si vous privilégiez la participation maximale à une intégrité stricte des votes. |

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | CG\_ALLOW\_JPEG | OUI | Autoriser les téléchargements d'images JPEG. |
| Configuration du module | CG\_ALLOW\_GIF | OUI | Autoriser les téléchargements d'images GIF. |
| Configuration du module | CG\_ALLOW\_PNG | OUI | Autoriser les téléchargements d'images PNG. |
| Configuration du module | CG\_ALLOW\_BMP | NON | Autoriser les téléchargements d'images BMP (fichiers volumineux). |
| Configuration du module | CG\_PAGINATION | OUI | Activer la pagination pour les pages de la galerie. |
| Configuration du module | CG\_ALLOW\_UNLOGGED | NON | Autoriser les invités à télécharger des photos. |
| Configuration du module | CG\_MAX\_FILE\_SIZE | 5 Mo | Taille maximale des fichiers pour les téléchargements. |
| Configuration du module | CG\_PRODUCTTAB | NON | Afficher les photos des clients dans un onglet produit. |
| Configuration du module | cg\_productTabM | displayProductExtraContent | Hook pour le placement de l'onglet produit. |
| Configuration du module | CG\_PRODUCTFOOTER | NON | Afficher les photos dans le pied de page du produit. |
| Configuration du module | CG\_CUSTOMERACCOUNT | OUI | Afficher le lien "Mes photos" dans le compte client. |
| Configuration du module | CG\_MYACCOUNTBLOCK | OUI | Afficher le lien "Mes photos" dans le bloc Mon compte. |
| Configuration du module | CG\_THUMBHEIGHT | 100 | Hauteur des miniatures générées. |
| Configuration du module | CG\_THUMBWIDTH | 100 | Largeur des miniatures générées. |
| Configuration du module | CG\_FUPLOADON | OUI | Activer le formulaire de téléchargement de photos. |
| Configuration du module | CG\_GALLERY | OUI | Afficher le lien vers la page principale de la galerie. |
| Configuration du module | CG\_RIGHTCOL | NON | Afficher les photos dans la colonne de droite. |
| Configuration du module | CG\_LEFTCOL | NON | Afficher les photos dans la colonne de gauche. |
| Configuration du module | CG\_NTF | OUI | Envoyer des notifications par e-mail à l'administrateur pour les nouveaux téléchargements. |
| Configuration du module | cg\_hpg\_nb | 8 | Nombre de photos sur la page d'accueil. |
| Configuration du module | cg\_hpg\_o | Les plus récentes en premier | Ordre des photos sur la page d'accueil. |
| Configuration du module | cg\_contest | NON | Activer le mode concours photo. |
| Configuration du module | cg\_excludeproduct | (vide) | ID des produits à exclure de la galerie. |
| Configuration du module | CG\_CUSTOMERACCOUNTV | OUI | Visibilité du lien "Mes photos" dans le compte client. |
| Configuration du module | CG\_MYACCOUNTBLOCKV | OUI | Visibilité du lien "Mes photos" dans le bloc Mon compte. |
| Configuration du module | CG\_voting | OUI | Activer le vote pour les photos. |
| Configuration du module | CG\_VOTE\_STAR | Étoiles | Style visuel du système de vote. |
| Configuration du module | cg\_unl\_voting | NON | Autoriser les utilisateurs non connectés à voter. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Mes photos téléchargées n'apparaissent pas dans la galerie.**
**R :**

-   **Vérifiez la configuration du module :** Assurez-vous que "Activer le formulaire de téléchargement de photos" (`CG_FUPLOADON`) est réglé sur OUI.
-   **Type et taille de fichier :** Vérifiez que le type de fichier téléchargé (JPEG, PNG, GIF, BMP) est autorisé dans les paramètres du module et que la taille du fichier est dans la limite de la "Taille maximale du fichier" (`CG_MAX_FILE_SIZE`).
-   **Modération :** Le module peut avoir une file d'attente de modération interne (bien que non explicitement listée comme un paramètre, de nombreux modules de galerie en ont une). Vérifiez s'il existe une section d'administration pour approuver/rejeter les photos.
-   **Permissions :** Assurez-vous que le répertoire `img/customersgallery/` (ou un chemin similaire où les images sont stockées) sur votre serveur a les permissions d'écriture (généralement 755 ou 777, bien que 777 soit moins sécurisé).
-   **Videz le cache :** Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop et videz le cache Smarty, le cache du navigateur et le cache du module.

**Q2 : Le lien ou le bloc de la galerie n'apparaît pas dans ma boutique.**
**R :**

-   **Hooks du module :** Vérifiez la page de configuration du module. Assurez-vous que "Afficher le lien de la galerie" (`CG_GALLERY`), "Afficher dans la colonne de droite" (`CG_RIGHTCOL`), "Afficher dans la colonne de gauche" (`CG_LEFTCOL`), etc., sont activés pour les emplacements que vous attendez.
-   **Gestion des hooks :** Allez dans **Design > Positions** (ou **Modules > Positions** dans les versions antérieures) dans votre Back Office PrestaShop. Recherchez le module ("Galerie Photo Client") et assurez-vous qu'il est accroché aux bonnes positions `display` (par exemple, `displayHeader`, `displayHome`, `displayRightColumn`). Si ce n'est pas le cas, "Greffer un module" au hook souhaité.
-   **Compatibilité du thème :** Certains thèmes personnalisés peuvent remplacer les positions de hook standard. Si le module n'apparaît pas malgré un accrochage correct, il peut nécessiter des ajustements mineurs du thème. Contactez le développeur de votre thème ou le support MyPresta.eu.
-   **Videz le cache :** Videz toujours votre cache PrestaShop après avoir apporté des modifications aux positions ou aux paramètres du module.

**Q3 : Les photos sur les pages produits n'apparaissent pas dans un onglet.**
**R :**

-   **Activer l'onglet produit :** Assurez-vous que `CG_PRODUCTTAB` est réglé sur OUI dans la configuration du module.
-   **Hook de l'onglet produit :** Vérifiez que `cg_productTabM` est réglé sur un hook approprié comme `displayProductExtraContent` ou `displayProductTab`.
-   **Exclusion de produit :** Vérifiez `cg_excludeproduct` pour vous assurer que le produit que vous consultez n'y est pas listé.
-   **Photos associées :** Assurez-vous qu'il y a réellement des photos téléchargées et associées à ce produit spécifique.
-   **Videz le cache :** Videz tous les caches.

**Q4 : Le système de vote ne fonctionne pas ou n'est pas visible.**
**R :**

-   **Activer le vote :** Assurez-vous que "Activer le vote pour les photos" (`CG_voting`) est réglé sur OUI.
-   **Utilisateurs non connectés :** Si les invités ne peuvent pas voter, vérifiez "Autoriser les utilisateurs non connectés à voter" (`cg_unl_voting`).
-   **Conflits CSS :** Parfois, le CSS du thème peut masquer ou déformer les éléments du module. Utilisez les outils de développement de votre navigateur (F12) pour inspecter la zone et vérifier les styles conflictuels.
-   **Erreurs JavaScript :** Vérifiez la console de votre navigateur (F12 > onglet Console) pour toute erreur JavaScript qui pourrait empêcher le fonctionnement de la fonctionnalité de vote.

**Q5 : Comment traduire le texte du module dans d'autres langues ?**
**R :**

-   Allez dans **International > Traductions** dans votre Back Office PrestaShop.
-   Sélectionnez "Traductions des modules installés".
-   Choisissez votre thème, la langue que vous souhaitez traduire, puis sélectionnez "Galerie Photo Client" dans la liste des modules.
-   Vous pouvez ensuite traduire toutes les chaînes du module pour le front-office et le back-office.
-   N'oubliez pas d'enregistrer vos modifications et de vider le cache.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module Galerie Photo Client suit une architecture de module PrestaShop standard, exploitant principalement les contrôleurs frontaux pour l'interaction utilisateur et les templates Smarty pour le rendu. Il s'intègre à divers hooks d'affichage pour intégrer les fonctionnalités de la galerie dans toute la boutique. Bien qu'il ne définisse pas explicitement de classes `ObjectModel` personnalisées dans l'inventaire fourni, il utilise probablement `Configuration` pour les paramètres et interagit directement avec la base de données pour le stockage et la gestion des photos/vidéos. AJAX est utilisé pour le chargement de contenu dynamique et les interactions comme le vote.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs gèrent toutes les interactions client et le traitement des données pour la galerie.

-   **`customersgallery/controllers/front/ajax.php`**

    -   **Nom de la classe :** `CustomersGalleryAjaxModuleFrontController` (étend probablement `ModuleFrontController`)
    -   **Responsabilité :** Ce contrôleur est l'épine dorsale des interactions dynamiques sans rechargement complet de la page. Il gère les requêtes AJAX pour des actions telles que :
        -   Soumission de nouvelles photos/vidéos.
        -   Traitement des votes (par exemple, évaluations par étoiles).
        -   Chargement de plus d'éléments de galerie (pagination/défilement infini).
        -   Potentiellement des actions de modération si un utilisateur non connecté télécharge et nécessite une approbation.
        -   Renvoie des réponses JSON au JavaScript côté client.
-   **`customersgallery/controllers/front/gallery.php`**

    -   **Nom de la classe :** `CustomersGalleryGalleryModuleFrontController` (étend probablement `ModuleFrontController`)
    -   **Responsabilité :** Ce contrôleur est responsable de l'affichage de la page principale de la galerie de photos et de vidéos des clients.
        -   Récupère toutes les photos/vidéos approuvées de la base de données.
        -   Applique la logique de pagination basée sur les paramètres du module (`CG_PAGINATION`).
        -   Prépare les données pour le template `gallery.tpl`, y compris les chemins d'image, les titres, les descriptions et les données de vote.
        -   Gère le tri (par exemple, par les plus récents, les plus populaires).
-   **`customersgallery/controllers/front/index.php`**

    -   **Nom de la classe :** `CustomersGalleryIndexModuleFrontController` (étend probablement `ModuleFrontController`)
    -   **Responsabilité :** Ce contrôleur peut servir de point d'entrée par défaut ou de redirigeur pour la section front-office du module. Il pourrait également être utilisé pour une simple page de destination ou pour rediriger vers la galerie principale. Dans de nombreux modules, `index.php` dans un répertoire de contrôleur frontal est un fallback ou une simple redirection vers la fonctionnalité principale.
-   **`customersgallery/controllers/front/myphotos.php`**

    -   **Nom de la classe :** `CustomersGalleryMyPhotosModuleFrontController` (étend probablement `ModuleFrontController`)
    -   **Responsabilité :** Ce contrôleur gère la section "Mes photos" dans le compte d'un client.
        -   Authentifie le client connecté.
        -   Récupère toutes les photos téléchargées par le client actuel.
        -   Permet aux clients de visualiser, modifier (par exemple, titre, description) ou supprimer leurs propres soumissions.
        -   Prépare les données pour le template `my-photos.tpl`.
-   **`customersgallery/controllers/front/myvideos.php`**

    -   **Nom de la classe :** `CustomersGalleryMyVideosModuleFrontController` (étend probablement `ModuleFrontController`)
    -   **Responsabilité :** Similaire à `myphotos.php`, mais spécifiquement pour la gestion des vidéos téléchargées par le client actuel.
        -   Authentifie le client connecté.
        -   Récupère toutes les vidéos téléchargées par le client actuel.
        -   Permet aux clients de visualiser, modifier ou supprimer leurs propres soumissions vidéo.
        -   Prépare les données pour le template `my-videos-16.tpl`.

#### Contrôleurs d'administration Back-Office

Le dossier du module n'indique aucun contrôleur d'administration dédié. Toute la configuration du back-office est gérée via la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que le module gère probablement ses données directement dans le fichier `customersgallery.php` ou utilise des méthodes génériques d'interaction avec la base de données de PrestaShop.

-   **Stockage des données :** Les métadonnées des photos et vidéos (chemins, titres, ID utilisateur, ID produit, statut d'approbation, votes) sont probablement stockées dans des tables de base de données personnalisées créées lors de l'installation du module. Le fichier PHP principal du module (`customersgallery.php`) contiendrait les requêtes SQL pour ces tables.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`customersgallery/js/customersgallery.js`**

    -   **Portée :** Front-office.
    -   **Détail :** Il s'agit probablement du fichier JavaScript personnalisé principal pour la galerie. Il contiendrait :
        -   Des écouteurs d'événements pour les téléchargements de photos/vidéos (par exemple, soumission de formulaire, changements d'entrée de fichier).
        -   Des appels AJAX à `ajax.php` pour les téléchargements, le vote et le chargement de plus de contenu.
        -   La validation côté client pour les types et tailles de fichiers.
        -   Des mises à jour dynamiques de l'affichage de la galerie (par exemple, ajout de nouvelles photos sans rafraîchissement de page).
        -   L'interaction avec la bibliothèque Fancybox pour les lightboxes d'images.
-   **`customersgallery/js/fancybox.js`**

    -   **Portée :** Front-office.
    -   **Détail :** Une bibliothèque tierce (Fancybox) pour créer des lightboxes élégantes et réactives pour les images et le multimédia. Ce script active la fonctionnalité "cliquer pour agrandir" pour les photos de la galerie.
-   **`customersgallery/js/script.js`**

    -   **Portée :** Front-office.
    -   **Détail :** Il pourrait s'agir d'un script utilitaire général ou d'un script hérité. Il pourrait contenir :
        -   Des fonctions d'aide pour les interactions de l'interface utilisateur.
        -   Des gestionnaires d'événements supplémentaires non spécifiques à la logique de la galerie principale.
        -   Potentiellement des scripts liés au mécanisme de vote ou à d'autres éléments interactifs.
-   **`customersgallery/lib/voucherengine/script.js`**

    -   **Portée :** Front-office.
    -   **Détail :** Cela suggère une intégration avec un "moteur de bons" ou un système de récompense similaire. Ce script gérerait :
        -   La logique d'attribution de bons ou de réductions lors de la soumission réussie de photos/vidéos (si `cg_contest` est activé ou si un système de récompense similaire est en place).
        -   Les appels AJAX pour déclencher la génération ou l'application de bons.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`customersgallery/css/customersgallery.css`**

    -   **Portée :** Front-office (style principal de la galerie).
    -   **Détail :** Contient les règles CSS de base pour la mise en page, l'apparence et la réactivité de la galerie de photos des clients, y compris :
        -   Les mises en page en grille pour l'affichage des photos.
        -   Le style des miniatures, des légendes et des informations utilisateur.
        -   Les styles pour le formulaire de téléchargement et la pagination.
        -   Les ajustements réactifs pour différentes tailles d'écran.
    -   **Sélecteurs clés :** `.customer-gallery-container`, `.gallery-item`, `.gallery-thumbnail`, `.upload-form`, `.pagination`.
-   **`customersgallery/css/fancybox.css`**

    -   **Portée :** Front-office.
    -   **Détail :** Feuille de style pour la bibliothèque lightbox Fancybox, contrôlant l'apparence des images agrandies, des flèches de navigation, du bouton de fermeture et de la superposition.
    -   **Sélecteurs clés :** `.fancybox-container`, `.fancybox-image`, `.fancybox-caption`.
-   **`customersgallery/css/star-black.css`, `star-blue.css`, `star-gold.css`, `star-pink.css`, `star-red.css`, `star-whitered.css`, `star.css`**

    -   **Portée :** Front-office.
    -   **Détail :** Ce sont différents thèmes de couleurs pour le système de vote par étoiles (`CG_VOTE_STAR`). `star.css` est probablement le style de base, et les autres fournissent des remplacements de couleurs.
    -   **Sélecteurs clés :** `.star-rating`, `.star-rating-control`, `.star-rating-star`.
-   **`customersgallery/lib/voucherengine/ps16.css`**

    -   **Portée :** Front-office.
    -   **Détail :** Cette feuille de style est spécifiquement destinée à l'intégration du "moteur de bons", fournissant probablement le style pour tous les éléments liés à l'affichage ou à la notification des bons, potentiellement avec des remplacements spécifiques pour les thèmes PrestaShop 1.6.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates personnalisés (`views/templates/custom/`)

Ce sont probablement des formulaires ou des composants spécifiques.

-   **`customersgallery/views/templates/custom/upload-form.tpl`**
    -   **Objectif :** Rend le formulaire HTML permettant aux clients de télécharger des photos.
    -   **Variables :** Inclut probablement des champs pour l'entrée de fichier, le titre, la description et potentiellement l'association de produits.
-   **`customersgallery/views/templates/custom/upload-form2.tpl`**
    -   **Objectif :** Pourrait être une version alternative ou mise à jour du formulaire de téléchargement, éventuellement pour les téléchargements de vidéos ou une mise en page différente.

#### Templates Front-Office (`views/templates/front/`)

Ces templates rendent les pages principales de la galerie et le contenu spécifique à l'utilisateur.

-   **`customersgallery/views/templates/front/gallery.tpl`**
    -   **Objectif :** Template principal pour l'affichage de la galerie de photos et de vidéos des clients.
    -   **Variables :** Parcourt les tableaux `$photos` et `$videos`, affichant les miniatures, les titres et les éléments de vote. Inclut la pagination.
-   **`customersgallery/views/templates/front/gallery2.tpl`**
    -   **Objectif :** Pourrait être une mise en page de galerie alternative ou une vue spécifique pour les concours.
-   **`customersgallery/views/templates/front/gallery3.tpl`**
    -   **Objectif :** Une autre mise en page de galerie alternative.
-   **`customersgallery/views/templates/front/menu.tpl`**
    -   **Objectif :** Rend un menu de navigation spécifique à la galerie, potentiellement avec des liens vers "Mes photos", "Mes vidéos", "Télécharger", etc.
-   **`customersgallery/views/templates/front/my-photos.tpl`**
    -   **Objectif :** Affiche la liste des photos téléchargées par le client actuellement connecté, avec des options pour modifier ou supprimer.
    -   **Variables :** Tableau `$customer_photos`.
-   **`customersgallery/views/templates/front/my-videos-16.tpl`**
    -   **Objectif :** Affiche la liste des vidéos téléchargées par le client actuellement connecté, spécifiquement conçue pour la compatibilité PrestaShop 1.6.
    -   **Variables :** Tableau `$customer_videos`.
-   **`customersgallery/views/templates/front/video-upload.tpl`**
    -   **Objectif :** Rend un formulaire spécifiquement pour le téléchargement de vidéos, distinct du formulaire de téléchargement de photos.

#### Templates de hook (`views/templates/hook/`)

Ces templates sont conçus pour être rendus dans des hooks PrestaShop spécifiques.

-   **`customersgallery/views/templates/hook/column-link.tpl`**
    -   **Hook :** `displayLeftColumn`, `displayRightColumn`
    -   **Objectif :** Rend un bloc dans la colonne de gauche ou de droite avec un lien vers la page principale de la galerie ou quelques photos récentes.
-   **`customersgallery/views/templates/hook/customer-my-account.tpl`**
    -   **Hook :** `displayCustomerAccount`
    -   **Objectif :** Ajoute un lien ou un bloc dans le tableau de bord du compte client, renvoyant généralement à "Mes photos" ou "Mes vidéos".
-   **`customersgallery/views/templates/hook/hookHome.tpl`**
    -   **Hook :** `displayHome`
    -   **Objectif :** Affiche un bloc de photos de clients récentes ou populaires sur la page d'accueil de la boutique.
    -   **Variables :** Tableau `$homepage_photos`.
-   **`customersgallery/views/templates/hook/my-account.tpl`**
    -   **Hook :** `displayMyAccountBlock`, `displayMyAccountBlockFooter`
    -   **Objectif :** Ajoute un lien vers "Mes photos" dans le bloc "Mon compte", souvent trouvé dans les colonnes latérales ou le pied de page.
-   **`customersgallery/views/templates/hook/productfooter.tpl`**
    -   **Hook :** `displayProductFooter`
    -   **Objectif :** Rend un bloc de photos de clients liées au produit actuel dans le pied de page de la page produit.
-   **`customersgallery/views/templates/hook/tab.tpl`**
    -   **Hook :** `displayProductTab`, `displayProductExtraContent`
    -   **Objectif :** Rend l'en-tête de l'onglet "Photos des clients" sur une page produit.
-   **`customersgallery/views/templates/hook/tabContents.tpl`**
    -   **Hook :** `displayProductTabContent`, `displayProductExtraContent`
    -   **Objectif :** Rend le contenu réel (la galerie de photos) dans l'onglet "Photos des clients" sur une page produit.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

Le module crée probablement des tables personnalisées lors de l'installation. Basé sur la fonctionnalité, celles-ci incluraient :

-   **`ps_customersgallery_photos`** :

    -   `id_photo` (CLÉ PRIMAIRE, INT)
    -   `id_customer` (INT, FK vers `ps_customer`)
    -   `id_product` (INT, FK vers `ps_product`, NULLABLE)
    -   `filename` (VARCHAR, chemin vers le fichier image)
    -   `title` (VARCHAR)
    -   `description` (TEXT)
    -   `date_add` (DATETIME)
    -   `active` (TINYINT, pour le statut de modération)
    -   `votes` (INT, total des votes)
    -   `rating` (DECIMAL, note moyenne)
-   **`ps_customersgallery_videos`** :

    -   `id_video` (CLÉ PRIMAIRE, INT)
    -   `id_customer` (INT, FK vers `ps_customer`)
    -   `id_product` (INT, FK vers `ps_product`, NULLABLE)
    -   `url` (VARCHAR, pour les liens vidéo externes comme YouTube/Vimeo)
    -   `title` (VARCHAR)
    -   `description` (TEXT)
    -   `date_add` (DATETIME)
    -   `active` (TINYINT)
-   **`ps_customersgallery_votes`** :

    -   `id_vote` (CLÉ PRIMAIRE, INT)
    -   `id_photo` (INT, FK vers `ps_customersgallery_photos`)
    -   `id_customer` (INT, FK vers `ps_customer`, NULLABLE pour les votes non connectés)
    -   `ip_address` (VARCHAR, pour les votes non connectés et la prévention des abus)
    -   `vote_value` (INT, par exemple, 1-5 pour les étoiles)
    -   `date_add` (DATETIME)
-   **`ps_configuration`** : Les paramètres du module (par exemple, `CG_ALLOW_JPEG`, `CG_MAX_FILE_SIZE`, `CG_PAGINATION`) sont stockés ici.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayProductExtraContent` | Rend du contenu additionnel sur la page produit, souvent utilisé pour les onglets. | Affiche l'onglet "Photos des clients" et son contenu sur les pages produits. |
| `displayRightColumnProduct` | Rend du contenu dans la colonne de droite d'une page produit. | Affiche un bloc de photos de clients spécifiques au produit dans la colonne de droite. |
| `displayCustomerAccount` | Rend du contenu dans le tableau de bord "Mon compte" du client. | Ajoute un lien ou un bloc vers "Mes photos" et "Mes vidéos" pour le client connecté. |
| `displayRightColumn` | Rend du contenu dans la colonne de droite des pages générales de la boutique. | Affiche un bloc de photos de clients récentes dans la colonne de droite. |
| `displayMyAccountBlockFooter` | Rend du contenu dans le pied de page du bloc "Mon compte". | Ajoute un lien vers "Mes photos" dans le bloc "Mon compte", souvent dans le pied de page. |
| `displayProductFooter` | Rend du contenu dans la zone de pied de page d'une page produit. | Affiche un bloc de photos de clients spécifiques au produit dans le pied de page du produit. |
| `displayProductTabContent` | Rend le contenu d'un onglet produit. | Affiche le contenu de la galerie dans l'onglet "Photos des clients" sur les pages produits. |
| `displayLeftColumnProduct` | Rend du contenu dans la colonne de gauche d'une page produit. | Affiche un bloc de photos de clients spécifiques au produit dans la colonne de gauche. |
| `displayLeftColumn` | Rend du contenu dans la colonne de gauche des pages générales de la boutique. | Affiche un bloc de photos de clients récentes dans la colonne de gauche. |
| `displayHome` | Rend du contenu sur la page d'accueil de la boutique. | Affiche un bloc de photos de clients récentes ou populaires sur la page d'accueil. |
| `displayHeader` | Rend du contenu dans la section `<head>` de toutes les pages. | Injecte les fichiers CSS et JavaScript requis par le module dans toute la boutique. |
| `displayMyAccountBlock` | Rend du contenu dans le bloc "Mon compte" (par exemple, dans les colonnes latérales). | Ajoute un lien vers "Mes photos" dans le bloc "Mon compte". |
| `displayProductTab` | Rend l'en-tête de l'onglet pour un onglet de page produit. | Affiche le titre de l'onglet "Photos des clients" sur les pages produits. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support professionnel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à assurer le bon fonctionnement et l'amélioration continue de vos modules PrestaShop.
