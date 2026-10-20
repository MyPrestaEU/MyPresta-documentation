---
title: "Bons de réduction popup responsives - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Bons de réduction popup responsives' par MyPresta.eu."
sidebar:
  label: "Bons de réduction popup responsives - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Responsive popup coupons sur MyPresta.eu](https://mypresta.eu/modules/social-networks/responsive-popup-coupons.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/responsive-popup-coupons/)
>
> ---


# Bons de réduction popup responsives

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 1.6.x, 1.5.x, 1.4.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes et habituellement activées par défaut sur la plupart des environnements d'hébergement.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal où vous définirez tous les paramètres de vos bons de réduction popup.

#### Paramètres généraux

-   **Activer le module :**

    -   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver l'ensemble de la fonctionnalité des bons de réduction popup pour votre boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Le pop-up commencera à apparaître sur les pages sélectionnées selon vos autres paramètres.
        -   *Lorsqu'il est désactivé :* Le pop-up n'apparaîtra nulle part sur votre boutique, quels que soient les autres paramètres.
    -   **Valeur recommandée :** OUI (lorsque vous souhaitez utiliser le module).
    -   **Scénario/exemple pour le marchand :** Vous organisez une promotion de vacances et souhaitez activer le pop-up pour une durée limitée. Vous l'activez au début et le désactivez une fois la promotion terminée.
-   **Afficher sur :**

    -   **Ce que fait ce paramètre :** Cela vous permet de choisir sur quels types de pages le pop-up sera affiché à vos clients.
    -   **Effet de la modification de ce paramètre :**
        -   *Page d'accueil :* Le pop-up apparaît uniquement sur la page principale de votre boutique.
        -   *Pages de catégorie :* Le pop-up apparaît lorsque les clients naviguent dans les catégories de produits.
        -   *Pages produit :* Le pop-up apparaît lorsque les clients consultent les détails des produits individuels.
        -   *Pages CMS :* Le pop-up apparaît sur les pages d'information comme « À propos de nous » ou « Contact ».
        -   *Toutes les pages :* Le pop-up apparaît sur chaque page de votre boutique.
    -   **Valeur recommandée :** Pages produit ou Toutes les pages (selon votre stratégie marketing).
    -   **Scénario/exemple pour le marchand :** Vous souhaitez encourager les achats directement sur les pages produit, vous sélectionnez donc « Pages produit ». Si vous voulez une visibilité maximale, vous pourriez choisir « Toutes les pages ».
-   **Délai (en secondes) avant l'apparition du pop-up :**

    -   **Ce que fait ce paramètre :** Contrôle le temps d'attente du pop-up avant d'apparaître après le chargement d'une page.
    -   **Effet de la modification de ce paramètre :**
        -   *Défini à 0 :* Le pop-up apparaît immédiatement au chargement de la page.
        -   *Défini à 5 :* Le pop-up apparaît 5 secondes après le chargement de la page.
    -   **Valeur recommandée :** 3-5 secondes (permet aux clients de voir le contenu en premier).
    -   **Scénario/exemple pour le marchand :** Vous ne voulez pas submerger les clients immédiatement. Définir un délai de 3 secondes leur donne un moment pour s'orienter avant que l'offre n'apparaisse.
-   **Afficher le pop-up une seule fois par session :**

    -   **Ce que fait ce paramètre :** Détermine si un client verra le pop-up plusieurs fois au cours d'une même visite sur votre boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Une fois qu'un client voit le pop-up (et le ferme potentiellement), il ne le reverra plus tant qu'il n'aura pas fermé son navigateur et démarré une nouvelle session.
        -   *Lorsqu'il est désactivé :* Le pop-up pourrait apparaître chaque fois qu'il visite une page où il est configuré pour s'afficher.
    -   **Valeur recommandée :** OUI (pour éviter d'agacer les clients).
    -   **Scénario/exemple pour le marchand :** Un client visite plusieurs pages produit. Si cette option est activée, il ne voit l'offre de bon de réduction qu'une seule fois, évitant ainsi l'irritation.
-   **Afficher le pop-up une seule fois par client (pour toujours) :**

    -   **Ce que fait ce paramètre :** C'est un paramètre plus permanent, empêchant un client connecté de revoir le pop-up une fois qu'il l'a vu.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Le module se souvient qu'un client spécifique (via son compte) a vu le pop-up et ne le lui affichera plus, même lors de futures sessions.
        -   *Lorsqu'il est désactivé :* La règle « une fois par session » s'applique, ou si celle-ci est désactivée, ils le verront à plusieurs reprises.
    -   **Valeur recommandée :** OUI (pour une expérience moins intrusive pour les clients fidèles).
    -   **Scénario/exemple pour le marchand :** Vous voulez donner à chaque client une chance d'obtenir le bon de réduction, mais ne pas le leur rappeler constamment s'ils l'ont déjà vu ou utilisé.
-   **Afficher le pop-up uniquement pour les invités (clients non connectés) :**

    -   **Ce que fait ce paramètre :** Restreint la visibilité du pop-up aux seuls visiteurs qui ne sont pas connectés à un compte client.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Seuls les visiteurs nouveaux ou de retour non connectés verront le pop-up. Les clients connectés ne le verront pas.
        -   *Lorsqu'il est désactivé :* Les invités et les clients connectés verront le pop-up (sous réserve d'autres règles d'affichage).
    -   **Valeur recommandée :** OUI (souvent, vous voulez convertir de nouveaux visiteurs, pas nécessairement offrir des réductions aux clients fidèles existants).
    -   **Scénario/exemple pour le marchand :** Votre objectif est d'attirer de nouveaux clients ou d'encourager les premiers achats. Vous activez cette option pour cibler votre offre sur les nouveaux clients potentiels.
-   **Afficher le pop-up uniquement pour les groupes de clients sélectionnés :**

    -   **Ce que fait ce paramètre :** Vous permet de cibler des groupes de clients spécifiques (par exemple, « Visiteurs », « Clients », « Invités » ou des groupes personnalisés que vous avez créés) avec le pop-up.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque des groupes spécifiques sont sélectionnés :* Seuls les clients appartenant à ces groupes verront le pop-up.
        -   *Lorsque aucun groupe n'est sélectionné (ou tous sont sélectionnés) :* Tous les clients verront le pop-up (sous réserve d'autres règles).
    -   **Valeur recommandée :** Sélectionnez « Invités » et « Visiteurs » si votre objectif est l'acquisition de nouveaux clients.
    -   **Scénario/exemple pour le marchand :** Vous souhaitez offrir une réduction spéciale uniquement à votre groupe de clients VIP. Vous ne sélectionneriez que ce groupe ici.
-   **Afficher le pop-up uniquement pour les pays sélectionnés :**

    -   **Ce que fait ce paramètre :** Restreint l'apparition du pop-up en fonction de la localisation géographique du client.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque des pays spécifiques sont sélectionnés :* Seuls les clients de ces pays verront le pop-up.
        -   *Lorsque aucun pays n'est sélectionné (ou tous sont sélectionnés) :* Tous les clients verront le pop-up.
    -   **Valeur recommandée :** Sélectionnez des pays spécifiques si vous avez des promotions géo-ciblées, sinon laissez vide.
    -   **Scénario/exemple pour le marchand :** Vous organisez une promotion exclusive pour les clients en France et en Allemagne. Vous ne sélectionneriez que ces deux pays.
-   **Afficher le pop-up uniquement pour les devises sélectionnées :**

    -   **Ce que fait ce paramètre :** Contrôle la visibilité du pop-up en fonction de la devise que le client utilise actuellement sur votre boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque des devises spécifiques sont sélectionnées :* Seuls les clients utilisant ces devises verront le pop-up.
        -   *Lorsque aucune devise n'est sélectionnée (ou toutes sont sélectionnées) :* Tous les clients verront le pop-up.
    -   **Valeur recommandée :** Sélectionnez des devises spécifiques si votre promotion dépend de la devise, sinon laissez vide.
    -   **Scénario/exemple pour le marchand :** Vous avez une offre spéciale pour les clients payant en USD. Vous ne sélectionneriez que l'USD ici.
-   **Afficher le pop-up uniquement pour les langues sélectionnées :**

    -   **Ce que fait ce paramètre :** Détermine si le pop-up apparaît en fonction de la langue que le client a sélectionnée pour votre boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque des langues spécifiques sont sélectionnées :* Seuls les clients consultant votre boutique dans ces langues verront le pop-up.
        -   *Lorsque aucune langue n'est sélectionnée (ou toutes sont sélectionnées) :* Tous les clients verront le pop-up.
    -   **Valeur recommandée :** Sélectionnez des langues spécifiques si le contenu de votre pop-up n'est traduit que pour certaines langues, sinon laissez vide.
    -   **Scénario/exemple pour le marchand :** Votre message pop-up n'est disponible qu'en anglais et en espagnol. Vous sélectionneriez ces deux langues pour vous assurer que les clients voient un message pertinent.

#### Paramètres des bons de réduction

-   **Valeur du bon de réduction :**

    -   **Ce que fait ce paramètre :** Définit le montant ou le pourcentage de réduction offert par le bon de réduction.
    -   **Effet de la modification de ce paramètre :**
        -   *Défini à 10 :* Le bon de réduction offrira une réduction de 10 unités (par exemple, 10 $, 10 €).
        -   *Défini à 15 % :* Le bon de réduction offrira une réduction de 15 %.
    -   **Valeur recommandée :** Une réduction attrayante (par exemple, 10 %, 5 $, 10 €).
    -   **Scénario/exemple pour le marchand :** Vous souhaitez offrir une réduction de 10 %, vous entrez donc « 10 % » ici.
-   **Type de bon de réduction :**

    -   **Ce que fait ce paramètre :** Spécifie si le bon de réduction est un montant fixe ou un pourcentage.
    -   **Effet de la modification de ce paramètre :**
        -   *Pourcentage :* La « Valeur du bon de réduction » sera traitée comme un pourcentage du total de la commande.
        -   *Montant :* La « Valeur du bon de réduction » sera traitée comme une déduction monétaire fixe.
    -   **Valeur recommandée :** Pourcentage (souvent plus attrayant pour des tailles de commande variables).
    -   **Scénario/exemple pour le marchand :** Vous voulez offrir 10 % de réduction, vous sélectionnez donc « Pourcentage ». Si vous voulez offrir une réduction fixe de 5 $, vous sélectionnez « Montant ».
-   **Montant minimum du bon de réduction :**

    -   **Ce que fait ce paramètre :** Définit une valeur de commande minimale que le client doit atteindre pour pouvoir utiliser le bon de réduction.
    -   **Effet de la modification de ce paramètre :**
        -   *Défini à 50 :* Le bon de réduction ne peut être utilisé que si le total du panier est de 50 $ ou plus.
        -   *Défini à 0 (ou vide) :* Aucun montant minimum de commande n'est requis.
    -   **Valeur recommandée :** Un minimum raisonnable pour protéger vos marges, ou 0 si vous voulez encourager tout achat.
    -   **Scénario/exemple pour le marchand :** Vous voulez vous assurer que la réduction n'est appliquée qu'aux commandes de plus de 50 $, vous entrez donc « 50 ».
-   **Expiration du bon de réduction (en jours) :**

    -   **Ce que fait ce paramètre :** Définit le nombre de jours pendant lesquels le code de réduction généré sera valide à partir du moment où il est émis.
    -   **Effet de la modification de ce paramètre :**
        -   *Défini à 7 :* Le bon de réduction expirera 7 jours après que le client l'ait reçu.
        -   *Défini à 0 (ou vide) :* Le bon de réduction n'expirera pas.
    -   **Valeur recommandée :** 7-30 jours (crée une urgence sans être trop restrictif).
    -   **Scénario/exemple pour le marchand :** Vous voulez que les clients utilisent le bon de réduction rapidement, vous définissez donc une expiration de 7 jours.
-   **Description du bon de réduction :**

    -   **Ce que fait ce paramètre :** Fournit un nom descriptif pour le bon de réduction dans votre back office PrestaShop (par exemple, dans la section « Règles panier »). Ceci est pour votre référence interne.
    -   **Effet de la modification de ce paramètre :** Ce texte apparaîtra dans votre panneau d'administration PrestaShop lorsque vous consulterez les règles panier générées, vous aidant à identifier leur origine. Il n'apparaît pas au client.
    -   **Valeur recommandée :** « Bon de réduction Popup - [Date] » ou « Réduction J'aime Facebook ».
    -   **Scénario/exemple pour le marchand :** Vous entrez « Réduction Popup J'aime Facebook » afin de savoir exactement d'où proviennent ces bons de réduction lors de l'examen de vos règles panier.
-   **Livraison gratuite avec le bon de réduction :**

    -   **Ce que fait ce paramètre :** Détermine si le bon de réduction accorde également la livraison gratuite sur la commande.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Le client ne sera pas facturé pour la livraison lors de l'utilisation de ce bon de réduction.
        -   *Lorsqu'il est désactivé :* Les frais de livraison standard s'appliqueront.
    -   **Valeur recommandée :** NON (sauf si vous souhaitez offrir la livraison gratuite comme une forte incitation).
    -   **Scénario/exemple pour le marchand :** Vous voulez offrir une offre très attrayante, vous activez donc la livraison gratuite avec la réduction.
-   **Bon de réduction applicable à des produits spécifiques :**

    -   **Ce que fait ce paramètre :** Vous permet de restreindre l'utilisation du bon de réduction à certains produits de votre boutique uniquement.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque des produits spécifiques sont sélectionnés :* Le bon de réduction ne fonctionnera que si ces produits sont dans le panier.
        -   *Lorsque aucun produit n'est sélectionné :* Le bon de réduction s'applique à tous les produits du panier.
    -   **Valeur recommandée :** Laissez vide sauf si vous avez une promotion de produit spécifique.
    -   **Scénario/exemple pour le marchand :** Vous faites la promotion d'une nouvelle ligne de chaussures. Vous ne sélectionnez que ces chaussures ici, de sorte que le bon de réduction ne fonctionne que pour elles.
-   **Bon de réduction applicable à des catégories spécifiques :**

    -   **Ce que fait ce paramètre :** Vous permet de restreindre l'utilisation du bon de réduction aux produits des catégories spécifiques.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque des catégories spécifiques sont sélectionnées :* Le bon de réduction ne fonctionnera que si des produits de ces catégories sont dans le panier.
        -   *Lorsque aucune catégorie n'est sélectionnée :* Le bon de réduction s'applique à tous les produits.
    -   **Valeur recommandée :** Laissez vide sauf si vous avez une promotion de catégorie spécifique.
    -   **Scénario/exemple pour le marchand :** Vous voulez écouler d'anciens stocks dans votre catégorie « Collection d'été ». Vous sélectionnez cette catégorie ici.
-   **Bon de réduction applicable à des fabricants spécifiques :**

    -   **Ce que fait ce paramètre :** Vous permet de restreindre l'utilisation du bon de réduction aux produits de marques/fabricants spécifiques.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque des fabricants spécifiques sont sélectionnés :* Le bon de réduction ne fonctionnera que si des produits de ces fabricants sont dans le panier.
        -   *Lorsque aucun fabricant n'est sélectionné :* Le bon de réduction s'applique à tous les produits.
    -   **Valeur recommandée :** Laissez vide sauf si vous avez une promotion de marque spécifique.
    -   **Scénario/exemple pour le marchand :** Vous avez un partenariat avec une marque spécifique et souhaitez offrir une réduction uniquement sur leurs produits.

#### Design et contenu du pop-up

-   **Largeur du pop-up (en pixels) :**

    -   **Ce que fait ce paramètre :** Contrôle la taille horizontale de la fenêtre pop-up.
    -   **Effet de la modification de ce paramètre :** Un nombre plus grand rend le pop-up plus large, un nombre plus petit le rend plus étroit.
    -   **Valeur recommandée :** 600px - 800px (pour une bonne visibilité sur ordinateur de bureau, le design responsive gérera le mobile).
    -   **Scénario/exemple pour le marchand :** Vous voulez que le pop-up soit proéminent mais pas trop large, vous le définissez donc à 700px.
-   **Couleur de fond du pop-up :**

    -   **Ce que fait ce paramètre :** Définit la couleur de fond de la fenêtre pop-up.
    -   **Effet de la modification de ce paramètre :** Modifie l'apparence visuelle du pop-up pour correspondre à votre marque ou se démarquer.
    -   **Valeur recommandée :** Une couleur qui contraste bien avec votre texte et votre marque (par exemple, #FFFFFF pour le blanc, #F0F0F0 pour le gris clair).
    -   **Scénario/exemple pour le marchand :** Votre marque utilise beaucoup de bleu, vous choisissez donc un code hexadécimal bleu clair comme #E0F2F7.
-   **Couleur du texte du pop-up :**

    -   **Ce que fait ce paramètre :** Définit la couleur du texte affiché dans le pop-up.
    -   **Effet de la modification de ce paramètre :** Assure la lisibilité par rapport à la couleur de fond choisie.
    -   **Valeur recommandée :** Une couleur qui offre un bon contraste (par exemple, #000000 pour le noir, #333333 pour le gris foncé).
    -   **Scénario/exemple pour le marchand :** Avec un fond clair, vous choisissez une couleur de texte foncée comme #333333 pour une lisibilité optimale.
-   **Couleur de la bordure du pop-up :**

    -   **Ce que fait ce paramètre :** Définit la couleur de la bordure autour de la fenêtre pop-up.
    -   **Effet de la modification de ce paramètre :** Ajoute un cadre visuel au pop-up.
    -   **Valeur recommandée :** Une couleur subtile qui complète votre design ou une couleur forte pour le faire ressortir (par exemple, #CCCCCC pour le gris clair, ou la couleur d'accent de votre marque).
    -   **Scénario/exemple pour le marchand :** Vous voulez un look épuré, vous choisissez donc une bordure grise subtile #DDDDDD.
-   **Largeur de la bordure du pop-up (en pixels) :**

    -   **Ce que fait ce paramètre :** Contrôle l'épaisseur de la bordure du pop-up.
    -   **Effet de la modification de ce paramètre :** Un nombre plus élevé rend la bordure plus épaisse.
    -   **Valeur recommandée :** 1-3px.
    -   **Scénario/exemple pour le marchand :** Vous voulez une bordure fine et élégante, vous la définissez donc à 1px.
-   **Rayon de la bordure du pop-up (en pixels) :**

    -   **Ce que fait ce paramètre :** Contrôle l'arrondi des coins du pop-up.
    -   **Effet de la modification de ce paramètre :**
        -   *Défini à 0 :* Coins nets et carrés.
        -   *Défini à 10 :* Coins légèrement arrondis.
        -   *Défini à 50 (ou plus) :* Coins très arrondis, en forme de pilule.
    -   **Valeur recommandée :** 5-10px (pour un look moderne et doux).
    -   **Scénario/exemple pour le marchand :** Vous préférez une esthétique plus douce, vous définissez donc le rayon de la bordure à 8px.
-   **Ombre du pop-up :**

    -   **Ce que fait ce paramètre :** Ajoute un effet d'ombre autour du pop-up, le faisant apparaître comme flottant au-dessus de la page.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Le pop-up aura une ombre subtile, lui donnant de la profondeur.
        -   *Lorsqu'il est désactivé :* Le pop-up n'aura pas d'ombre.
    -   **Valeur recommandée :** OUI (ajoute une touche professionnelle et moderne).
    -   **Scénario/exemple pour le marchand :** Vous voulez que le pop-up se démarque visuellement de l'arrière-plan, vous activez donc l'ombre.
-   **Couleur du bouton de fermeture du pop-up :**

    -   **Ce que fait ce paramètre :** Définit la couleur du bouton « X » que les clients utilisent pour fermer le pop-up.
    -   **Effet de la modification de ce paramètre :** Assure que le bouton de fermeture est visible et correspond à votre design.
    -   **Valeur recommandée :** Une couleur contrastante pour la visibilité (par exemple, #000000, #FF0000).
    -   **Scénario/exemple pour le marchand :** Vous voulez que le bouton de fermeture soit clairement visible, vous le définissez donc en noir #000000.
-   **Contenu du pop-up (HTML autorisé) :**

    -   **Ce que fait ce paramètre :** C'est ici que vous entrez le message principal et le contenu de votre pop-up. Vous pouvez utiliser le HTML pour formater le texte, ajouter des images et inclure vos boutons de réseaux sociaux.
    -   **Effet de la modification de ce paramètre :** Ce texte et ce HTML seront affichés à l'intérieur du pop-up.
    -   **Valeur recommandée :** Message clair et concis avec un appel à l'action fort. Incluez le code de votre bouton J'aime Facebook ou un widget de réseau social similaire.
    -   **Scénario/exemple pour le marchand :** Vous pourriez entrer : `<p>Aimez-nous sur Facebook et obtenez <strong>10 % de réduction</strong> sur votre prochaine commande !</p><div class="fb-like" data-href="URL_DE_VOTRE_PAGE_FACEBOOK" data-layout="button_count" data-action="like" data-size="large" data-show-faces="false" data-share="false"></div>` (N'oubliez pas de remplacer `URL_DE_VOTRE_PAGE_FACEBOOK`).
-   **Message du bon de réduction du pop-up (HTML autorisé) :**

    -   **Ce que fait ce paramètre :** C'est le message affiché *après* que le client ait effectué l'action requise (par exemple, aimé votre page) et reçu son code de réduction.
    -   **Effet de la modification de ce paramètre :** Ce message apparaîtra dans le pop-up, généralement au-dessus du code de réduction généré.
    -   **Valeur recommandée :** Un message de remerciement et des instructions sur la façon d'utiliser le bon de réduction.
    -   **Scénario/exemple pour le marchand :** Vous pourriez entrer : `<p>Merci de nous avoir aimés ! Voici votre code de réduction exclusif :</p><p>Utilisez le code <strong>{coupon_code}</strong> lors du paiement.</p>` (Le marqueur de position `{coupon_code}` sera automatiquement remplacé).

#### Paramètres avancés

-   **Code CSS personnalisé :**

    -   **Ce que fait ce paramètre :** Vous permet d'ajouter vos propres règles CSS personnalisées pour styliser davantage le pop-up ou remplacer les styles par défaut.
    -   **Effet de la modification de ce paramètre :** Tout CSS que vous entrez ici sera appliqué au pop-up, vous donnant un contrôle précis sur son apparence.
    -   **Valeur recommandée :** Laissez vide sauf si vous avez des besoins de style spécifiques.
    -   **Scénario/exemple pour le marchand :** Vous voulez changer la taille de la police du code de réduction. Vous pourriez ajouter : `.coupon-code { font-size: 24px !important; }`
-   **Code JavaScript personnalisé :**

    -   **Ce que fait ce paramètre :** Vous permet d'ajouter votre propre code JavaScript personnalisé pour interagir avec le pop-up ou l'intégrer à d'autres services.
    -   **Effet de la modification de ce paramètre :** Tout JavaScript que vous entrez ici sera exécuté lorsque le pop-up est affiché ou interagi avec.
    -   **Valeur recommandée :** Laissez vide sauf si vous avez des besoins de script spécifiques (par exemple, le suivi d'événements Google Analytics).
    -   **Scénario/exemple pour le marchand :** Vous voulez envoyer un événement à Google Analytics lorsque le pop-up est affiché. Vous pourriez ajouter : `ga('send', 'event', 'Popup', 'Displayed', 'Coupon Offer');`

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activer le module | OUI | Interrupteur principal pour la fonctionnalité du pop-up. |
| | Afficher sur | Pages produit / Toutes les pages | Sélectionne où le pop-up apparaît (Page d'accueil, Catégorie, Produit, CMS, Toutes). |
| | Délai (en secondes) avant l'apparition du pop-up | 3-5 secondes | Temps avant l'affichage du pop-up après le chargement de la page. |
| | Afficher le pop-up une seule fois par session | OUI | Empêche le pop-up de s'afficher plusieurs fois dans une même session de navigateur. |
| | Afficher le pop-up une seule fois par client (pour toujours) | OUI | Empêche les clients connectés de revoir le pop-up. |
| | Afficher le pop-up uniquement pour les invités | OUI | Cible les visiteurs non connectés. |
| | Afficher le pop-up uniquement pour les groupes de clients sélectionnés | Invités, Visiteurs | Restreint le pop-up à des groupes de clients spécifiques. |
| | Afficher le pop-up uniquement pour les pays sélectionnés | Laisser vide | Restreint le pop-up à des pays spécifiques. |
| | Afficher le pop-up uniquement pour les devises sélectionnées | Laisser vide | Restreint le pop-up à des devises spécifiques. |
| | Afficher le pop-up uniquement pour les langues sélectionnées | Laisser vide | Restreint le pop-up à des langues spécifiques. |
| | Valeur du bon de réduction | ex., 10 % | Le montant ou le pourcentage de réduction. |
| | Type de bon de réduction | Pourcentage / Montant | Définit si le bon est en % ou en montant fixe. |
| | Montant minimum du bon de réduction | 0 (ou valeur raisonnable) | Valeur de commande minimale pour l'utilisation du bon. |
| | Expiration du bon de réduction (en jours) | 7-30 jours | Période de validité du bon de réduction généré. |
| | Description du bon de réduction | « Réduction Popup J'aime Facebook » | Nom interne du bon de réduction dans le BO. |
| | Livraison gratuite avec le bon de réduction | NON | Accorde la livraison gratuite avec le bon de réduction. |
| | Bon de réduction applicable à des produits spécifiques | Laisser vide | Restreint le bon de réduction à des produits spécifiques. |
| | Bon de réduction applicable à des catégories spécifiques | Laisser vide | Restreint le bon de réduction à des catégories spécifiques. |
| | Bon de réduction applicable à des fabricants spécifiques | Laisser vide | Restreint le bon de réduction à des fabricants spécifiques. |
| | Largeur du pop-up (en pixels) | 600px - 800px | Taille horizontale du pop-up. |
| | Couleur de fond du pop-up | #FFFFFF (blanc) | Couleur de fond du pop-up. |
| | Couleur du texte du pop-up | #000000 (noir) | Couleur du texte à l'intérieur du pop-up. |
| | Couleur de la bordure du pop-up | #DDDDDD (gris clair) | Couleur de la bordure du pop-up. |
| | Largeur de la bordure du pop-up (en pixels) | 1-3px | Épaisseur de la bordure du pop-up. |
| | Rayon de la bordure du pop-up (en pixels) | 5-10px | Arrondi des coins du pop-up. |
| | Ombre du pop-up | OUI | Ajoute un effet d'ombre au pop-up. |
| | Couleur du bouton de fermeture du pop-up | #000000 (noir) | Couleur du bouton de fermeture « X ». |
| | Contenu du pop-up (HTML autorisé) | Message engageant + widget social | Contenu principal affiché dans le pop-up. |
| | Message du bon de réduction du pop-up (HTML autorisé) | Message de remerciement + {coupon\_code} | Message affiché après la génération du bon de réduction. |
| | Code CSS personnalisé | Laisser vide | Ajouter des styles CSS personnalisés. |
| | Code JavaScript personnalisé | Laisser vide | Ajouter du JavaScript personnalisé. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Le pop-up n'apparaît pas sur ma boutique. Que dois-je vérifier en premier ?**
R1 :

-   **Le module est-il activé ?** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que « Bons de réduction popup responsives » est installé et activé.
-   **Vérifiez le paramètre « Activer le module » :** Dans la configuration du module, assurez-vous que l'interrupteur « Activer le module » est réglé sur OUI.
-   **Vérifiez les paramètres « Afficher sur » :** Assurez-vous d'avoir sélectionné les types de pages corrects (par exemple, Page d'accueil, Pages produit) où vous vous attendez à ce que le pop-up apparaisse.
-   **Videz votre cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures). Le cache du navigateur pourrait également avoir besoin d'être vidé (Ctrl+F5 ou Cmd+Maj-R).
-   **Vérifiez les conflits :** Désactivez temporairement les autres modules qui pourraient interagir avec les pop-ups ou le contenu de la page pour exclure les conflits.

**Q2 : Le pop-up apparaît, mais le bouton J'aime Facebook (ou un autre widget social) ne fonctionne pas ou ne s'affiche pas correctement.**
R2 :

-   **HTML incorrect :** Vérifiez attentivement le code HTML que vous avez entré dans le champ « Contenu du pop-up ». Même une petite faute de frappe peut le casser. Assurez-vous que l'URL de votre page Facebook est correcte.
-   **SDK Facebook :** Pour que les boutons J'aime Facebook fonctionnent, le SDK JavaScript de Facebook doit être chargé. Les thèmes PrestaShop l'incluent souvent, mais si ce n'est pas le cas, vous devrez peut-être l'ajouter via un code personnalisé ou vous assurer que votre thème le prend en charge.
-   **Bloqueurs de publicités :** Certains bloqueurs de publicités peuvent empêcher le chargement des widgets sociaux. Testez dans une fenêtre de navigation privée sans extensions.

**Q3 : Le code de réduction est généré, mais il ne fonctionne pas lors du paiement.**
R3 :

-   **Vérifiez les paramètres du bon de réduction :** Passez en revue tous les paramètres « Bon de réduction » dans la configuration du module :
    -   **Montant minimum :** La valeur du panier du client est-elle supérieure au « Montant minimum du bon de réduction » ?
    -   **Expiration :** La date d'« Expiration du bon de réduction » est-elle passée ?
    -   **Produits/catégories/fabricants spécifiques :** Le panier du client contient-il les articles requis si ces paramètres sont utilisés ?
    -   **Groupes de clients/pays/devises/langues :** Le client répond-il aux critères définis pour ces restrictions ?
-   **Règles panier PrestaShop :** Le module crée une « Règle panier » dans PrestaShop. Allez dans **Catalogue > Réductions > Règles panier** (ou **Règles de prix > Règles panier** dans les versions antérieures) et recherchez le code de réduction. Vérifiez ses détails pour voir si des restrictions ont été appliquées incorrectement.

**Q4 : Le design du pop-up ne correspond pas parfaitement au thème de ma boutique.**
R4 :

-   **Utilisez les paramètres de design du module :** Ajustez la « Couleur de fond du pop-up », la « Couleur du texte du pop-up », la « Couleur de la bordure du pop-up », la « Largeur de la bordure du pop-up » et le « Rayon de la bordure du pop-up » pour mieux correspondre à votre thème.
-   **CSS personnalisé :** Pour un style plus avancé, utilisez le champ « Code CSS personnalisé » dans la configuration du module. Vous pouvez inspecter les éléments du pop-up à l'aide des outils de développement de votre navigateur (F12) pour trouver les sélecteurs CSS corrects à cibler.
-   **Surcharges de thème :** Si vous êtes à l'aise avec le codage, vous pouvez également surcharger le CSS du module dans le fichier `custom.css` ou `theme.css` de votre thème.

**Q5 : Comment traduire le contenu du pop-up en plusieurs langues ?**
R5 :

-   Les champs « Contenu du pop-up » et « Message du bon de réduction du pop-up » sont généralement conçus pour être saisis une seule fois. Pour un support multilingue, vous devrez utiliser le système de traduction de PrestaShop.
-   Allez dans **International > Traductions**. Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez « Bons de réduction popup responsives ». Vous devriez y trouver les champs de texte à traduire.
-   Si les champs ne sont pas directement traduisibles via l'interface PrestaShop standard, vous devrez peut-être créer des pop-ups distincts pour chaque langue (si le module prend en charge plusieurs instances) ou utiliser une solution personnalisée impliquant des variables Smarty et une logique conditionnelle dans le contenu HTML, ce qui nécessite l'aide d'un développeur.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé du module « Bons de réduction popup responsives » pour les développeurs et les webmasters.

### 4.1 Vue d'ensemble de l'architecture

Le module « Bons de réduction popup responsives » (`popcoupon`) est un module PrestaShop standard principalement implémenté dans son fichier PHP principal, `ajax_popcoupon.php`. Il utilise le système de hooks de PrestaShop pour l'affichage en front-office et la classe `Configuration` pour le stockage des paramètres. La fonctionnalité principale du module implique l'affichage d'un pop-up, la gestion de l'interaction utilisateur (par exemple, action sur les réseaux sociaux) et la génération dynamique de codes `CartRule` (bons de réduction) PrestaShop. Il utilise du JavaScript côté client pour la logique d'affichage et le style du pop-up, et un modèle minimal pour le rendu de la structure du pop-up.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient pas de contrôleurs d'administration Front-Office ou Back-Office dédiés dans des fichiers séparés. Toute la logique de configuration du back-office est gérée dans la méthode `getContent()` de la classe principale du module. L'affichage en front-office est géré via des hooks et du JavaScript côté client.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe `ObjectModel` personnalisée ni d'autres classes PHP principales dans un répertoire `classes/`. Toute la logique est contenue dans le fichier principal du module `ajax_popcoupon.php`. Le module interagit directement avec la classe `Configuration` de PrestaShop pour les paramètres et la classe `CartRule` pour la génération des bons de réduction.

### 4.4 Actifs JavaScript (`views/js/`)

Le module inclut plusieurs fichiers JavaScript :

-   **`popcoupon/jscolor/jscolor.js`**

    -   **Portée :** Back-office.
    -   **Objectif :** Il s'agit d'une bibliothèque JavaScript tierce pour un sélecteur de couleurs. Elle est utilisée dans le formulaire de configuration du back-office du module pour permettre aux marchands de sélectionner facilement les couleurs de fond, de texte, de bordure et du bouton de fermeture du pop-up. Elle se lie aux champs de saisie avec des classes spécifiques pour fournir une interface visuelle de sélection de couleurs.
-   **`popcoupon/lib/voucherengine/script.js`**

    -   **Portée :** Front-office.
    -   **Objectif :** Il s'agit du fichier JavaScript principal responsable de la fonctionnalité du pop-up en front-office.
        -   **Écouteurs d'événements :** Il écoute les événements de chargement de page pour déclencher le pop-up après le délai configuré. Il gère également les événements liés à la fermeture du pop-up (par exemple, en cliquant sur le bouton « X » ou en dehors du pop-up).
        -   **Manipulation du DOM :** Il injecte dynamiquement la structure HTML du pop-up dans la page, gère sa visibilité (afficher/masquer) et met à jour son contenu (par exemple, affichage du code de réduction après une action sociale).
        -   **Appels AJAX :** Il effectue probablement des appels AJAX vers `ajax_popcoupon.php` du module (ou un point d'entrée similaire) pour :
            1.  Vérifier si le pop-up doit être affiché pour l'utilisateur/la session actuelle.
            2.  Générer un code de réduction unique après que l'utilisateur a terminé l'action requise (par exemple, J'aime Facebook).
            3.  Stocker les données utilisateur/session (par exemple, un cookie) pour empêcher l'affichage répété du pop-up en fonction des paramètres de configuration (« une fois par session », « une fois par client »).
        -   **SDK tiers :** Si le « Contenu du pop-up » inclut un bouton J'aime Facebook, ce script pourrait interagir avec le SDK JavaScript de Facebook (s'il est chargé par le thème) pour détecter quand l'action « j'aime » est terminée.
-   **`popcoupon/trusted.js`**

    -   **Portée :** Front-office.
    -   **Objectif :** L'objectif exact de ce fichier n'est pas explicitement défini dans les informations fournies, mais basé sur les pratiques courantes des modules, il pourrait s'agir de :
        -   Un petit script utilitaire pour le suivi ou l'analyse.
        -   Un script lié aux badges de confiance ou aux fonctionnalités de sécurité.
        -   Un script de secours ou supplémentaire pour le fichier `script.js` principal.
        -   Il pourrait contenir une logique liée à la gestion des cookies ou du stockage local pour les fonctionnalités « afficher une seule fois ».

### 4.5 Feuilles de style CSS (`views/css/`)

Le module inclut les fichiers CSS suivants :

-   **`popcoupon/css.css`**

    -   **Portée :** Front-office.
    -   **Objectif :** C'est la feuille de style principale pour la fenêtre pop-up.
        -   **Composants de l'interface utilisateur :** Style le conteneur global du pop-up, son overlay, le bouton de fermeture et potentiellement la zone de contenu.
        -   **Sélecteurs clés :** Les développeurs peuvent s'attendre à des sélecteurs comme `.popcoupon-overlay`, `.popcoupon-modal`, `.popcoupon-close`, etc. Ceux-ci peuvent être surchargés dans le fichier `custom.css` d'un thème personnalisé ou en utilisant le paramètre « Code CSS personnalisé » du module.
        -   **Réactivité :** Contient des requêtes média ou des propriétés flexbox/grid pour garantir que le pop-up s'adapte bien aux différentes tailles d'écran.
-   **`popcoupon/lib/voucherengine/ps16.css`**

    -   **Portée :** Front-office.
    -   **Objectif :** Cette feuille de style contient probablement des ajustements de style spécifiques ou des surcharges adaptés aux thèmes PrestaShop 1.6. Elle pourrait aborder les différences de mise en page ou les styles d'éléments par défaut prévalents dans PS 1.6 pour garantir que le pop-up ait un aspect cohérent sur différentes versions de PrestaShop. Pour PS 1.7/8, certains de ces styles pourraient être surchargés par `css.css` ou le thème lui-même.

### 4.6 Structure du modèle Smarty (`views/templates/`)

Le module utilise un seul modèle Smarty :

-   **`popcoupon/views/header.tpl`**
    -   **Hook :** `displayHeader` (ou similaire, selon la façon dont il est enregistré dans `ajax_popcoupon.php`).
    -   **Objectif :** Ce modèle est probablement responsable de l'injection de la structure HTML nécessaire pour le pop-up (qui est initialement masqué) et potentiellement des actifs JavaScript et CSS dans la section `<head>` ou `<body>` de la page du front-office. Il pourrait contenir :
        -   Le squelette HTML de base pour la modale du pop-up et son overlay.
        -   Une logique conditionnelle pour inclure les fichiers JavaScript et CSS uniquement lorsque le module est activé.
        -   Des espaces réservés pour le contenu dynamique qui sera rempli par JavaScript.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données :**

    -   Ce module ne crée pas de tables SQL personnalisées.
    -   Il stocke ses paramètres de configuration dans la table `ps_configuration` de PrestaShop. Les clés de configuration commenceront généralement par `POPCOUPON_` (par exemple, `POPCOUPON_ENABLED`, `POPCOUPON_DELAY`, `POPCOUPON_VOUCHER_VALUE`).
    -   Il utilise les tables `ps_cart_rule` et `ps_cart_rule_lang` de PrestaShop pour générer et gérer les codes de réduction uniques.
    -   Pour les fonctionnalités « afficher une seule fois par client/session », il utilise probablement des cookies ou des entrées de configuration spécifiques à `ps_customer`.
-   **Table des hooks enregistrés :**

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Injection du CSS, du JavaScript et de la structure HTML initiale (masquée) pour le pop-up. |
| `displayFooter` | À la fin de la section `<body>` de chaque page du front-office. | Hook alternatif pour l'injection de JS/CSS ou du HTML du pop-up, souvent préféré pour les performances. |
| `displayLeftColumn` | Dans la colonne de gauche du front-office. | Moins courant pour les pop-ups, mais pourrait être utilisé pour déclencher ou afficher un élément de pop-up plus petit. |
| `displayRightColumn` | Dans la colonne de droite du front-office. | Similaire à `displayLeftColumn`. |
| `displayProductButtons` | Sur la page produit, près du bouton d'ajout au panier. | Pourrait être utilisé pour déclencher un pop-up spécifique au produit ou afficher une petite offre de bon de réduction. |
| `actionFrontControllerSetMedia` | Lorsqu'un contrôleur frontal définit ses médias (JS/CSS). | Un moyen plus robuste d'enregistrer les actifs JS/CSS, garantissant qu'ils sont chargés correctement. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | (Moins probable pour ce module, mais pourrait être utilisé pour des actions post-achat liées aux bons de réduction). |

*Note : Les hooks exacts utilisés sont déterminés par les méthodes `hook` implémentées dans `ajax_popcoupon.php` (par exemple, `hookDisplayHeader()`). La description du module mentionne « En-tête, Colonnes, Produit ou Pied de page », indiquant qu'il s'enregistre pour au moins un de ces hooks d'affichage.*

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Bons de réduction popup responsives », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour aider les marchands et les développeurs avec tout problème ou question concernant la fonctionnalité et l'intégration du module.
