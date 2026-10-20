---
title: "MyPazaruvaj - E-mail d'enquête Pazaruvaj - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop MyPazaruvaj - E-mail d'enquête Pazaruvaj par MyPresta.eu."
sidebar:
  label: "MyPazaruvaj - E-mail d'enquête Pazaruvaj - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module MyPazaruvaj - Pazaruvaj survey email sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/mypazaruvaj-pazaruvaj-survey-email.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/mypazaruvaj-pazaruvaj-survey-email/)
>
> ---


# MyPazaruvaj - E-mail d'enquête Pazaruvaj

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5 (Le module est conçu pour être largement compatible avec diverses versions de PHP, jusqu'à la dernière version stable prise en charge par PrestaShop 8 et 9.)
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises par PrestaShop lui-même et sont suffisantes pour ce module. Aucune configuration spéciale de serveur n'est nécessaire.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > MyPazaruvaj)

Ceci est l'écran de configuration principal et unique pour le module MyPazaruvaj. Ici, vous configurerez tous les paramètres nécessaires pour connecter votre boutique à Pazaruvaj.com.

#### **ID de boutique Pazaruvaj.com**

-   **Ce que fait ce paramètre :** Il s'agit de votre identifiant unique fourni par Pazaruvaj.com pour votre boutique en ligne. Il indique à Pazaruvaj à quelle boutique appartiennent les données de commande.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est correctement défini :* Le module enverra avec succès les données de commande à votre profil de boutique Pazaruvaj.com.
    -   *Lorsqu'il est incorrect ou vide :* Pazaruvaj.com ne pourra pas identifier votre boutique, et aucun e-mail d'enquête ne sera envoyé à vos clients.
-   **Valeur recommandée :** Saisissez l'ID de boutique exact qui vous a été fourni par Pazaruvaj.com. Ce champ est obligatoire.
-   **Scénario / exemple de marchand :** Vous avez enregistré votre boutique sur Pazaruvaj.com et ils vous ont donné un ID de boutique comme `12345`. Vous devez saisir `12345` ici pour que l'intégration fonctionne.

#### **Champ d'ID produit Pazaruvaj.com**

-   **Ce que fait ce paramètre :** Cette option détermine quel identifiant de produit de votre boutique PrestaShop doit être envoyé à Pazaruvaj.com. Pazaruvaj.com utilise cet ID pour faire correspondre le produit acheté avec sa liste sur leur plateforme.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est défini sur "ID produit" :* L'ID interne du produit PrestaShop (par exemple, `id_product`) sera envoyé. C'est généralement l'option la plus sûre si votre flux Pazaruvaj.com utilise ces ID.
    -   *Lorsqu'il est défini sur "Référence produit" :* Le code de référence du produit (par exemple, `reference`) sera envoyé. Choisissez cette option si votre flux Pazaruvaj.com fait correspondre les produits par leur référence.
    -   *Lorsqu'il est défini sur "EAN13 produit" :* Le code-barres EAN13 du produit sera envoyé. Utile si votre flux Pazaruvaj.com repose sur les EAN.
    -   *Lorsqu'il est défini sur "UPC produit" :* Le code UPC du produit sera envoyé.
-   **Valeur recommandée :** "ID produit" est souvent la valeur par défaut la plus fiable. Cependant, vous **devez** vérifier quel identifiant votre flux de produits sur Pazaruvaj.com utilise pour faire correspondre les produits. Si votre flux utilise des références de produit, sélectionnez "Référence produit".
-   **Scénario / exemple de marchand :** Si votre flux de produits sur Pazaruvaj.com utilise l'ID interne unique que PrestaShop attribue à chaque produit, vous devez sélectionner "ID produit". Si vous avez téléchargé un flux où chaque produit est identifié par un SKU ou un numéro de référence spécifique (par exemple, `REF-001`), alors sélectionnez "Référence produit".

#### **Activer le consentement pour envoyer des données à Pazaruvaj.com**

-   **Ce que fait ce paramètre :** Ce commutateur contrôle si les clients doivent explicitement accepter que leurs données de commande soient envoyées à Pazaruvaj.com pour l'enquête. Lorsqu'il est activé, une case à cocher apparaît lors du paiement.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (OUI) :* Une case à cocher apparaîtra sur la page de paiement. Seuls les clients qui cochent cette case verront leurs données de commande envoyées à Pazaruvaj.com. Cela aide à la conformité avec le RGPD et d'autres réglementations sur la confidentialité des données.
    -   *Lorsqu'il est désactivé (NON) :* Les données de commande seront envoyées à Pazaruvaj.com pour *toutes* les commandes terminées sans nécessiter le consentement explicite du client. C'est plus simple pour les clients mais pourrait ne pas être conforme à toutes les lois sur la confidentialité dans votre région.
-   **Valeur recommandée :** "OUI" est généralement recommandé pour la conformité avec les réglementations sur la protection des données (comme le RGPD).
-   **Scénario / exemple de marchand :** Pour vous assurer que votre boutique est entièrement conforme aux lois sur la confidentialité, vous activez ce paramètre. Lors du paiement, vos clients verront une case à cocher intitulée quelque chose comme "J'accepte de partager les détails de ma commande avec Pazaruvaj.com pour une enquête d'avis." Ce n'est que s'ils la cochent que les données seront envoyées.

#### **Afficher le consentement sur**

-   **Ce que fait ce paramètre :** Si "Activer le consentement" est défini sur OUI, cette option détermine où la case à cocher de consentement sera affichée sur le front-office de votre boutique.
-   **Effet de la modification de ce paramètre :**
    -   *En-tête, Colonnes, Produit, Pied de page :* La case à cocher de consentement sera affichée dans la zone de hook sélectionnée. Le placement visuel exact dépend de la mise en page de votre thème pour ce hook.
-   **Valeur recommandée :** Choisissez un emplacement proéminent mais non intrusif. Le "Pied de page" ou une "Colonne" spécifique (si votre thème en a une appropriée) sont souvent de bons choix pour les avis liés à la confidentialité. Vous devrez peut-être tester différentes options pour voir ce qui convient le mieux à votre thème.
-   **Scénario / exemple de marchand :** Vous avez activé le consentement. Vous décidez d'afficher la case à cocher de consentement dans le "Pied de page" afin qu'elle soit visible mais ne surcharge pas le flux de paiement principal.

#### **Activer le journal d'erreurs**

-   **Ce que fait ce paramètre :** Ce commutateur contrôle si le module enregistre les erreurs rencontrées lors du processus de transfert de données vers Pazaruvaj.com.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (OUI) :* Le module enregistrera les détails de toute soumission de données échouée dans un fichier journal. C'est inestimable pour le dépannage si les enquêtes ne sont pas envoyées.
    -   *Lorsqu'il est désactivé (NON) :* Aucune information d'erreur ne sera enregistrée, ce qui rendra plus difficile le diagnostic des problèmes.
-   **Valeur recommandée :** "OUI" est fortement recommandé, en particulier lors de la configuration initiale et pour la surveillance continue.
-   **Scénario / exemple de marchand :** Vous n'êtes pas sûr que l'intégration fonctionne parfaitement. Vous activez le journal d'erreurs. Si Pazaruvaj.com ne reçoit pas de données, vous pouvez vérifier le journal pour voir s'il y a des messages d'erreur spécifiques, comme un ID de boutique invalide ou des problèmes de connexion.

#### **Effacer le journal d'erreurs**

-   **Ce que fait ce paramètre :** Ce bouton vous permet de supprimer toutes les entrées du journal d'erreurs du module.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsque cliqué :* Toutes les erreurs précédemment enregistrées sont définitivement supprimées du fichier journal.
-   **Valeur recommandée :** Utilisez ceci après avoir examiné et résolu les problèmes, ou si le fichier journal devient trop volumineux.
-   **Scénario / exemple de marchand :** Vous avez corrigé un problème avec votre ID de boutique Pazaruvaj.com. Vous cliquez sur "Effacer le journal d'erreurs" pour repartir à zéro et vous assurer que seules les nouvelles erreurs pertinentes sont enregistrées.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et Impact |
| --- | --- | --- | --- |
| Config du module | ID de boutique Pazaruvaj.com | Votre ID Pazaruvaj (Obligatoire) | Identifiant unique de votre boutique sur Pazaruvaj.com. Essentiel pour le transfert de données. |
| Config du module | Champ d'ID produit Pazaruvaj.com | ID produit (Vérifier avec le flux Pazaruvaj) | Détermine quel identifiant de produit PrestaShop (ID, Référence, EAN13, UPC) est envoyé à Pazaruvaj.com pour la correspondance des produits. |
| Config du module | Activer le consentement pour envoyer des données à Pazaruvaj.com | OUI (Pour la conformité) | Nécessite le consentement du client via une case à cocher lors du paiement avant d'envoyer des données à Pazaruvaj.com. |
| Config du module | Afficher le consentement sur | Pied de page (Tester pour le meilleur placement) | Spécifie le hook du front-office où la case à cocher de consentement apparaîtra si activée. |
| Config du module | Activer le journal d'erreurs | OUI (Pour le dépannage) | Active l'enregistrement de toutes les erreurs lors de la soumission des données à Pazaruvaj.com. |
| Config du module | Effacer le journal d'erreurs | N/A (Bouton) | Supprime toutes les entrées du journal d'erreurs du module. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes clients ne reçoivent pas d'e-mails d'enquête de Pazaruvaj.com. Que dois-je vérifier ?**
R :

1.  **ID de boutique Pazaruvaj.com :** Vérifiez à nouveau que votre "ID de boutique Pazaruvaj.com" dans la configuration du module est absolument correct et correspond à l'ID fourni par Pazaruvaj.com.
2.  **Journal d'erreurs :** Activez le "Journal d'erreurs" dans la configuration du module et vérifiez les erreurs enregistrées après une commande test. Cela indiquera souvent le problème exact.
3.  **Paramètre de consentement :** Si "Activer le consentement pour envoyer des données à Pazaruvaj.com" est activé, assurez-vous que les clients cochent bien la case à cocher lors du paiement. S'ils ne le font pas, les données ne seront pas envoyées.
4.  **Statut de la commande :** Assurez-vous que la commande atteint un statut "Paiement accepté" ou un statut final similaire dans PrestaShop, car le module se déclenche généralement lors de la finalisation réussie de la commande.
5.  **Compte Pazaruvaj.com :** Connectez-vous à votre compte Pazaruvaj.com pour voir s'il y a des problèmes ou des avertissements de leur côté concernant votre boutique ou votre flux de données.

**Q : La case à cocher de consentement n'apparaît pas sur ma page de paiement.**
R :

1.  **Paramètre "Activer le consentement" :** Tout d'abord, assurez-vous que "Activer le consentement pour envoyer des données à Pazaruvaj.com" est défini sur OUI dans la configuration du module.
2.  **Paramètre "Afficher le consentement sur" :** Vérifiez le hook que vous avez sélectionné pour "Afficher le consentement sur". Si votre thème n'affiche pas activement de contenu dans ce hook spécifique (par exemple, un `displayMyCustomHook` personnalisé), la case à cocher n'apparaîtra pas. Essayez de passer à un hook commun comme `displayFooter` ou `displayHeader` pour tester.
3.  **Compatibilité du thème :** Certains thèmes très personnalisés peuvent remplacer les emplacements de hook standard. Si le problème persiste, vous devrez peut-être demander à un webmaster d'inspecter les fichiers de modèle de votre thème.
4.  **Cache Smarty :** Videz le cache Smarty de votre PrestaShop sous **Paramètres avancés > Performances** (Forcer la compilation et vider le cache).

**Q : J'ai modifié un paramètre, mais rien ne s'est passé sur ma boutique.**
R : Après avoir effectué des modifications dans la configuration du module, videz toujours le cache de votre PrestaShop. Allez dans **Paramètres avancés > Performances**, puis cliquez sur "Vider le cache" et éventuellement "Forcer la compilation" si vous effectuez des modifications liées aux modèles. Le cache de votre navigateur pourrait également avoir besoin d'être vidé (Ctrl+F5 ou Cmd+R).

**Q : Puis-je personnaliser le texte de la case à cocher de consentement ?**
R : Oui, le texte de la case à cocher de consentement est traduisible. Vous pouvez le modifier via le système de traduction de PrestaShop :

1.  Allez dans **International > Traductions**.
2.  Sélectionnez "Traductions des modules installés".
3.  Choisissez votre thème, la langue, puis sélectionnez "MyPazaruvaj".
4.  Vous y trouverez la chaîne de caractères liée au message de consentement et pourrez la modifier.

**Q : Que se passe-t-il si j'ai plusieurs boutiques (multiboutique) activées ?**
R : Le module doit être configuré individuellement pour chaque boutique dans un environnement multiboutique. Assurez-vous de sélectionner le bon contexte de boutique dans le back office de PrestaShop avant de configurer le module pour cette boutique spécifique. Chaque boutique aura probablement son propre ID de boutique Pazaruvaj.com unique.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module MyPazaruvaj.

### 4.1 Vue d'ensemble de l'architecture

Le module MyPazaruvaj suit une architecture de module PrestaShop standard, utilisant principalement la classe `Module` et ses méthodes `install()`, `uninstall()` et `getContent()` pour la configuration. Sa fonctionnalité principale est basée sur les événements, tirant parti des hooks PrestaShop pour intercepter les événements de confirmation de commande et afficher le consentement optionnel. La soumission des données à Pazaruvaj.com est gérée directement dans le fichier PHP principal du module, sans contrôleurs front ou admin dédiés, ce qui en fait une solution légère et efficace.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs front-office ou back-office dédiés. Toute la logique de configuration est gérée dans la méthode `getContent()` du fichier principal du module, et la logique d'affichage du front-office est gérée directement via les templates de hook.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée et n'étend pas `ObjectModel`. Toute la logique est contenue dans la classe principale `MyPazaruvaj` définie dans `mypazaruvaj/index.php`.

La classe principale `MyPazaruvaj` étend `Module` et contient :

-   `__construct()` : Définit les propriétés du module (nom, onglet, version, auteur, `need_instance`, `ps_versions_compliancy`, `bootstrap`).
-   `install()` : Enregistre les hooks nécessaires (`displayOrderConfirmation`, `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`), crée les entrées de configuration et initialise le fichier journal d'erreurs.
-   `uninstall()` : Désenregistre les hooks et supprime les entrées de configuration.
-   `getContent()` : Rend le formulaire de configuration du back-office du module, gère les soumissions de formulaire et met à jour les valeurs de configuration.
-   `hookDisplayOrderConfirmation()` : Le hook principal pour la soumission des données. Il récupère les détails de la commande, les informations client et les données produit, puis construit et envoie la requête à Pazaruvaj.com. Il gère également la vérification de consentement optionnelle.
-   `hookDisplayHeader()`, `hookDisplayFooter()`, `hookDisplayLeftColumn()`, `hookDisplayRightColumn()` : Ces hooks sont utilisés pour afficher la case à cocher de consentement si elle est activée et configurée pour apparaître à ces emplacements. Ils rendent le template `consent.tpl`.
-   `_clearLog()` : Méthode interne pour effacer le fichier journal d'erreurs.
-   `_writeLog()` : Méthode interne pour écrire des messages dans le fichier journal d'erreurs.
-   `_displayForm()` : Méthode interne pour rendre le formulaire de configuration à l'aide de `HelperForm` de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé. Tout style pour la case à cocher de consentement reposerait sur le style par défaut des éléments de formulaire du thème.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** :

    -   `mypazaruvaj/views/templates/hook/consent.tpl` :
        -   **Objectif :** Rend la case à cocher de consentement optionnelle pour l'envoi de données à Pazaruvaj.com.
        -   **Rendu dans les hooks :** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn` (selon la configuration du module).
        -   **Variables :** Vérifie généralement `$consent_enabled` et affiche un champ de formulaire.
        -   **Sortie :** Une simple case à cocher HTML et une étiquette.
    -   `mypazaruvaj/views/templates/hook/displayOrderConfirmation.tpl` :
        -   **Objectif :** Ce modèle est probablement un espace réservé ou utilisé pour la logique interne du module qui n'affiche pas de contenu visible directement au client. La logique principale de soumission des données pour `displayOrderConfirmation` est gérée dans la méthode de hook PHP elle-même, pas nécessairement via une sortie de modèle. Il pourrait être utilisé pour passer des variables ou déclencher du JS si le module en avait. Dans le contexte de ce module, c'est principalement la méthode de hook PHP qui effectue l'action.
-   **Modèles d'administration (`views/templates/admin/`)** :

    -   Ce module n'utilise pas de modèles d'administration dédiés. Le formulaire de configuration est généré par programme à l'aide de `HelperForm` dans `getContent()`.
-   **Modèles de front-office (`views/templates/front/`)** :

    -   Ce module n'inclut aucun modèle de front-office dédié au-delà des modèles de hook.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Ce module ne crée aucune table SQL personnalisée.
    -   Il stocke ses paramètres de configuration dans la table standard `ps_configuration` de PrestaShop.
        -   `MYPAZARUVAJ_SHOP_ID` : Stocke l'ID de boutique Pazaruvaj.com.
        -   `MYPAZARUVAJ_PRODUCT_ID_FIELD` : Stocke le champ d'ID produit sélectionné (par exemple, 'id\_product', 'reference').
        -   `MYPAZARUVAJ_CONSENT_ENABLED` : Booléen (0 ou 1) pour activer/désactiver le consentement.
        -   `MYPAZARUVAJ_CONSENT_HOOK` : Stocke le nom du hook où le consentement est affiché.
        -   `MYPAZARUVAJ_ERROR_LOG_ENABLED` : Booléen (0 ou 1) pour activer/désactiver le journal d'erreurs.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayOrderConfirmation` | Après qu'un client a terminé une commande avec succès. | **Hook principal pour la soumission des données.** Récupère les détails de la commande et du produit, construit la requête Pazaruvaj.com et l'envoie. Vérifie le consentement si activé. |
| `displayHeader` | Dans la section `<head>` ou en haut de chaque page. | Rend `consent.tpl` si configuré pour afficher le consentement ici. |
| `displayFooter` | Dans la section du pied de page de chaque page. | Rend `consent.tpl` si configuré pour afficher le consentement ici. |
| `displayLeftColumn` | Dans la colonne latérale gauche (si active dans le thème). | Rend `consent.tpl` si configuré pour afficher le consentement ici. |
| `displayRightColumn` | Dans la colonne latérale droite (si active dans le thème). | Rend `consent.tpl` si configuré pour afficher le consentement ici. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir concernant le module MyPazaruvaj.
