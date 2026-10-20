---
title: "Prestashop Popup Pro - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Prestashop Popup Pro par MyPresta.eu."
sidebar:
  label: "Prestashop Popup Pro - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Prestashop Popup Pro sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/prestashop-popup-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/prestashop-popup-pro/)
>
> ---


# Prestashop Popup Pro

## 1. Exigences et compatibilité

Pour garantir le bon fonctionnement du module Prestashop Popup Pro sur votre boutique, veuillez vérifier les exigences suivantes :

- **Versions PrestaShop prises en charge** : PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour le fonctionnement général de PrestaShop et devraient être disponibles sur tout environnement d'hébergement moderne. Aucune extension spéciale ou inhabituelle n'est nécessaire pour ce module.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

La page de configuration principale de Prestashop Popup Pro est l'endroit où vous définissez tout ce qui concerne votre pop-up : son contenu, son apparence et son comportement.

**Onglet Paramètres généraux**

-   **Activer Popup Pro :**
    *   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour l'ensemble du module.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Le module commencera à afficher des pop-ups selon vos autres paramètres.
        *   *Lorsqu'il est désactivé :* Aucun pop-up n'apparaîtra sur votre boutique, quelles que soient les autres configurations.
    *   **Valeur recommandée :** OUI (lorsque vous souhaitez utiliser des pop-ups).
    *   **Scénario / exemple marchand :** Vous menez une campagne et souhaitez activer votre pop-up. Vous l'activez. Après la campagne, vous le désactivez sans perdre vos paramètres.
-   **Contenu du pop-up (Éditeur HTML) :**
    *   **Ce que fait ce paramètre :** C'est le cœur de votre pop-up. C'est un éditeur HTML puissant où vous concevez ce qui apparaît dans la fenêtre du pop-up. Vous pouvez ajouter du texte, des images, des liens, des vidéos et même intégrer des formulaires (par exemple, inscription à la newsletter).
    *   **Effet de la modification de ce paramètre :** Toute modification ici met à jour directement le contenu visuel affiché à vos clients dans le pop-up.
    *   **Valeur recommandée :** Votre message promotionnel, image ou appel à l'action souhaité.
    *   **Scénario / exemple marchand :** Vous souhaitez annoncer une réduction de 15 %. Vous taperiez "Obtenez 15 % de réduction sur votre première commande ! Utilisez le code : SAVE15" et ajouteriez peut-être une image de produits populaires.
-   **Largeur du pop-up (px) :**
    *   **Ce que fait ce paramètre :** Définit la largeur de votre fenêtre pop-up en pixels.
    *   **Effet de la modification de ce paramètre :**
        *   *Augmenter la valeur :* Rend le pop-up plus large.
        *   *Diminuer la valeur :* Rend le pop-up plus étroit.
    *   **Valeur recommandée :** Commencez par `600px` à `800px` pour le bureau, puis ajustez en fonction de votre contenu et de votre design.
    *   **Scénario / exemple marchand :** Vous avez une grande image de bannière dans votre pop-up. Vous pourriez définir la largeur à `800px` pour vous assurer que l'image s'affiche bien. Pour un simple message texte, `400px` pourrait suffire.
-   **Hauteur du pop-up (px) :**
    *   **Ce que fait ce paramètre :** Définit la hauteur de votre fenêtre pop-up en pixels.
    *   **Effet de la modification de ce paramètre :**
        *   *Augmenter la valeur :* Rend le pop-up plus grand.
        *   *Diminuer la valeur :* Rend le pop-up plus petit.
    *   **Valeur recommandée :** `auto` (laisser vide) ou une valeur en pixels spécifique si votre contenu a une hauteur fixe.
    *   **Scénario / exemple marchand :** Si le contenu de votre pop-up est dynamique ou court, le laisser vide (`auto`) permet au pop-up d'ajuster sa hauteur pour s'adapter au contenu. Si vous avez une vidéo qui nécessite un rapport d'aspect spécifique, vous pourriez définir une hauteur fixe.
-   **Afficher le pop-up sur :**
    *   **Ce que fait ce paramètre :** Détermine *quand* le pop-up apparaît.
    *   **Effet de la modification de ce paramètre :**
        *   *Chargement de la page :* Le pop-up apparaît après le chargement de la page.
        *   *Intention de sortie :* Le pop-up apparaît lorsque la souris de l'utilisateur se déplace en dehors de la fenêtre du navigateur (indiquant qu'il pourrait partir).
        *   *Défilement :* Le pop-up apparaît après que l'utilisateur ait fait défiler un certain pourcentage de la page.
        *   *Délai :* Le pop-up apparaît après un nombre de secondes spécifié.
    *   **Valeur recommandée :** Dépend de votre objectif. "Intention de sortie" est souvent efficace pour capturer les visiteurs qui abandonnent. "Chargement de la page" avec un court délai (par exemple, 3-5 secondes) est bon pour les annonces générales.
    *   **Scénario / exemple marchand :** Pour réduire l'abandon de panier, vous choisiriez "Intention de sortie" et offririez un code de réduction. Pour annoncer une nouvelle gamme de produits, vous pourriez utiliser "Chargement de la page" avec un délai de 3 secondes.
-   **Délai avant l'apparition du pop-up (secondes) :**
    *   **Ce que fait ce paramètre :** Si "Afficher le pop-up sur" est défini sur "Chargement de la page" ou "Délai", cela spécifie le nombre de secondes à attendre avant que le pop-up ne s'affiche.
    *   **Effet de la modification de ce paramètre :** Une valeur plus élevée signifie que le pop-up apparaît plus tard, donnant au client plus de temps pour naviguer. Une valeur plus faible signifie qu'il apparaît plus tôt.
    *   **Valeur recommandée :** `3` à `5` secondes. Trop rapide peut être intrusif, trop lent pourrait manquer le client.
    *   **Scénario / exemple marchand :** Vous voulez donner aux clients un moment pour voir votre page d'accueil avant d'afficher une inscription à la newsletter. Vous définissez cela à `5` secondes.
-   **Fréquence du pop-up (jours) :**
    *   **Ce que fait ce paramètre :** Contrôle la fréquence à laquelle un client *de retour* voit le pop-up. Une fois qu'un client ferme le pop-up, ce paramètre détermine combien de jours s'écoulent avant qu'il ne le revoie.
    *   **Effet de la modification de ce paramètre :**
        *   *0 :* Le pop-up apparaît à chaque visite (peut être ennuyeux).
        *   *Valeur plus élevée :* Le pop-up apparaît moins fréquemment pour les visiteurs de retour.
    *   **Valeur recommandée :** `7` à `30` jours. Évitez d'ennuyer vos clients fidèles.
    *   **Scénario / exemple marchand :** Vous organisez une vente d'un mois. Vous définissez cela à `7` jours afin que les clients soient rappelés chaque semaine, mais pas à chaque visite.
-   **Afficher le pop-up sur les appareils mobiles :**
    *   **Ce que fait ce paramètre :** Active ou désactive l'affichage du pop-up sur les smartphones et les tablettes.
    *   **Effet de la modification de ce paramètre :**
        *   *Activé :* Le pop-up apparaît sur les appareils mobiles, s'adaptant de manière réactive.
        *   *Désactivé :* Le pop-up n'apparaîtra que sur les ordinateurs de bureau.
    *   **Valeur recommandée :** OUI, mais assurez-vous que le contenu de votre pop-up est adapté aux mobiles.
    *   **Scénario / exemple marchand :** Vous avez un pop-up simple, basé sur du texte, qui s'affiche bien sur mobile. Vous l'activez pour atteindre tous vos clients. Si votre pop-up contient des images ou des formulaires complexes qui ne s'affichent pas correctement sur mobile, vous pourriez le désactiver.
-   **Couleur de fond du pop-up :**
    *   **Ce que fait ce paramètre :** Définit la couleur de fond de la fenêtre pop-up elle-même.
    *   **Effet de la modification de ce paramètre :** Modifie la couleur visuelle derrière votre contenu.
    *   **Valeur recommandée :** Une couleur qui complète votre marque et met en valeur votre contenu. Souvent blanc (`#FFFFFF`) ou une couleur neutre claire.
    *   **Scénario / exemple marchand :** Votre marque utilise beaucoup de bleu. Vous pourriez choisir un fond bleu clair pour le pop-up pour correspondre.
-   **Couleur de la bordure du pop-up :**
    *   **Ce que fait ce paramètre :** Définit la couleur de la bordure autour de la fenêtre pop-up.
    *   **Effet de la modification de ce paramètre :** Modifie la couleur visuelle du bord du pop-up.
    *   **Valeur recommandée :** Souvent une couleur subtile, ou transparente si vous préférez sans bordure.
    *   **Scénario / exemple marchand :** Vous voulez un look épuré, vous définissez donc cela sur un gris très clair ou transparent.
-   **Largeur de la bordure du pop-up (px) :**
    *   **Ce que fait ce paramètre :** Définit l'épaisseur de la bordure autour de la fenêtre pop-up.
    *   **Effet de la modification de ce paramètre :** Une valeur plus élevée rend la bordure plus épaisse.
    *   **Valeur recommandée :** `0` à `2` pixels pour un effet subtil.
    *   **Scénario / exemple marchand :** Vous voulez un pop-up très défini, vous définissez donc une bordure de `2px`. Pour un design minimaliste, vous le définissez à `0`.
-   **Rayon de la bordure du pop-up (px) :**
    *   **Ce que fait ce paramètre :** Contrôle l'arrondi des coins du pop-up.
    *   **Effet de la modification de ce paramètre :**
        *   *0 :* Coins nets et carrés.
        *   *Valeur plus élevée :* Coins plus arrondis.
    *   **Valeur recommandée :** `0` à `10` pixels pour un look moderne.
    *   **Scénario / exemple marchand :** Vous voulez que votre pop-up ait des bords doux et modernes, vous définissez donc cela à `8px`.
-   **Couleur de fond de la superposition :**
    *   **Ce que fait ce paramètre :** Définit la couleur de la couche semi-transparente qui apparaît *derrière* le pop-up, assombrissant le reste du contenu de votre boutique.
    *   **Effet de la modification de ce paramètre :** Modifie la couleur de la superposition. Souvent une couleur sombre avec transparence.
    *   **Valeur recommandée :** Noir (`#000000`) avec une certaine transparence (par exemple, `rgba(0,0,0,0.7)` si vous pouvez saisir du RGBA).
    *   **Scénario / exemple marchand :** Vous voulez que le pop-up soit la seule chose à laquelle on prête attention, vous choisissez donc une superposition sombre, presque opaque.
-   **Opacité de la superposition (0-100) :**
    *   **Ce que fait ce paramètre :** Contrôle la transparence ou l'opacité de l'arrière-plan de la superposition. `0` est entièrement transparent (invisible), `100` est entièrement opaque (couleur unie).
    *   **Effet de la modification de ce paramètre :**
        *   *Valeur plus élevée :* Plus opaque, arrière-plan plus sombre, plus de focus sur le pop-up.
        *   *Valeur plus faible :* Plus transparent, arrière-plan plus clair, plus de contenu de votre boutique visible.
    *   **Valeur recommandée :** `50` à `80`.
    *   **Scénario / exemple marchand :** Vous voulez légèrement estomper l'arrière-plan mais permettre aux clients de voir votre boutique derrière le pop-up. Vous définissez cela à `60`.
-   **Afficher le bouton de fermeture :**
    *   **Ce que fait ce paramètre :** Active ou désactive la visibilité du bouton de fermeture "X" standard sur le pop-up.
    *   **Effet de la modification de ce paramètre :**
        *   *Activé :* Un bouton de fermeture apparaît, permettant aux clients de fermer facilement le pop-up.
        *   *Désactivé :* Pas de bouton "X". Les clients devront cliquer en dehors du pop-up ou appuyer sur Échap (si activé) pour le fermer.
    *   **Valeur recommandée :** OUI, pour une bonne expérience utilisateur.
    *   **Scénario / exemple marchand :** Vous voulez faciliter la fermeture du pop-up pour les clients, vous activez donc le bouton de fermeture.
-   **Autoriser la fermeture en cliquant à l'extérieur :**
    *   **Ce que fait ce paramètre :** Détermine si un clic n'importe où sur la superposition (en dehors du contenu du pop-up) fermera le pop-up.
    *   **Effet de la modification de ce paramètre :**
        *   *Activé :* Cliquer sur la superposition ferme le pop-up.
        *   *Désactivé :* Seul le bouton de fermeture ou la touche Échap fermera le pop-up.
    *   **Valeur recommandée :** OUI, pour une bonne expérience utilisateur.
    *   **Scénario / exemple marchand :** Vous voulez offrir plusieurs façons aux clients de fermer le pop-up, vous activez donc cela.
-   **Autoriser la fermeture par la touche Échap :**
    *   **Ce que fait ce paramètre :** Détermine si appuyer sur la touche Échap du clavier fermera le pop-up.
    *   **Effet de la modification de ce paramètre :**
        *   *Activé :* La touche Échap ferme le pop-up.
        *   *Désactivé :* La touche Échap n'a aucun effet sur le pop-up.
    *   **Valeur recommandée :** OUI, pour une bonne expérience utilisateur.
    *   **Scénario / exemple marchand :** Vous voulez offrir un moyen accessible aux clients de fermer le pop-up, vous activez donc cela.
-   **CSS personnalisé :**
    *   **Ce que fait ce paramètre :** Vous permet d'ajouter vos propres règles CSS personnalisées pour styliser davantage le pop-up ou son contenu. Ceci est destiné aux utilisateurs avancés ou aux développeurs.
    *   **Effet de la modification de ce paramètre :** Toutes les règles CSS valides que vous ajoutez ici seront appliquées au pop-up, potentiellement en remplaçant les styles par défaut.
    *   **Valeur recommandée :** Laisser vide sauf si vous avez des besoins de style spécifiques.
    *   **Scénario / exemple marchand :** Vous souhaitez modifier la taille de la police d'un paragraphe spécifique à l'intérieur de votre pop-up, ou ajouter un effet d'ombre unique non disponible dans d'autres paramètres. Vous ajouteriez le CSS ici.

**Onglet Paramètres avancés (ou regroupement similaire si disponible)**

-   **Animation du pop-up (Effet d'entrée) :**
    *   **Ce que fait ce paramètre :** Sélectionne un effet d'animation pour l'apparition du pop-up à l'écran.
    *   **Effet de la modification de ce paramètre :** Le pop-up s'animera pour apparaître en utilisant l'effet choisi (par exemple, fondu, glissement vers le bas, zoom).
    *   **Valeur recommandée :** "Fondu" ou "Glissement vers le bas" sont généralement subtils et professionnels.
    *   **Scénario / exemple marchand :** Vous voulez que votre pop-up apparaisse en douceur plutôt que de surgir instantanément, vous choisissez donc "Fondu".
-   **Animation du pop-up (Effet de sortie) :**
    *   **Ce que fait ce paramètre :** Sélectionne un effet d'animation pour la disparition du pop-up de l'écran.
    *   **Effet de la modification de ce paramètre :** Le pop-up s'animera pour disparaître en utilisant l'effet choisi.
    *   **Valeur recommandée :** "Fondu" ou "Glissement vers le haut" pour correspondre à l'effet d'entrée.
    *   **Scénario / exemple marchand :** Pour maintenir une expérience utilisateur cohérente et fluide, vous choisissez "Fondu" comme animation de sortie.
-   **Afficher le pop-up sur des pages spécifiques (URL) :**
    *   **Ce que fait ce paramètre :** Vous permet de spécifier des URL exactes ou des motifs d'URL où le pop-up doit (ou ne doit pas) apparaître.
    *   **Effet de la modification de ce paramètre :** Le pop-up ne s'affichera que sur les pages correspondant à vos critères, ou en sera masqué.
    *   **Valeur recommandée :** Utilisez ceci pour cibler efficacement vos pop-ups.
    *   **Scénario / exemple marchand :** Vous avez une offre spéciale pour une catégorie de produits spécifique. Vous saisiriez l'URL de cette page de catégorie ici pour vous assurer que le pop-up n'apparaît que pour les visiteurs pertinents.
-   **Ne pas afficher le pop-up sur des pages spécifiques (URL) :**
    *   **Ce que fait ce paramètre :** Vous permet de spécifier des URL exactes ou des motifs d'URL où le pop-up ne doit *pas* apparaître.
    *   **Effet de la modification de ce paramètre :** Le pop-up sera masqué des pages correspondant à vos critères.
    *   **Valeur recommandée :** Utilisez ceci pour éviter d'afficher des pop-ups sur des pages sensibles comme le paiement ou la connexion.
    *   **Scénario / exemple marchand :** Vous ne voulez pas que le pop-up interrompe le processus de paiement. Vous ajouteriez l'URL de votre page de paiement (par exemple, `/order`) ici.
-   **Afficher le pop-up pour des groupes de clients spécifiques :**
    *   **Ce que fait ce paramètre :** Restreint la visibilité du pop-up à certains groupes de clients (par exemple, Visiteurs, Clients, Invités, Grossistes).
    *   **Effet de la modification de ce paramètre :** Seuls les clients appartenant aux groupes sélectionnés verront le pop-up.
    *   **Valeur recommandée :** Dépend de votre public cible. "Visiteurs" et "Invités" sont courants pour la génération de leads.
    *   **Scénario / exemple marchand :** Vous avez une offre spéciale exclusivement pour vos clients enregistrés. Vous sélectionneriez "Clients" ici.
-   **Afficher le pop-up pour des langues spécifiques :**
    *   **Ce que fait ce paramètre :** Restreint la visibilité du pop-up aux clients naviguant dans des langues spécifiques.
    *   **Effet de la modification de ce paramètre :** Seuls les clients utilisant la langue sélectionnée verront le pop-up.
    *   **Valeur recommandée :** Toutes les langues, ou des langues spécifiques si le contenu de votre pop-up dépend de la langue.
    *   **Scénario / exemple marchand :** Vous avez un pop-up dont le contenu n'est traduit qu'en anglais et en français. Vous sélectionneriez "Anglais" et "Français" ici.
-   **Afficher le pop-up pour des devises spécifiques :**
    *   **Ce que fait ce paramètre :** Restreint la visibilité du pop-up aux clients naviguant avec des devises spécifiques.
    *   **Effet de la modification de ce paramètre :** Seuls les clients utilisant la devise sélectionnée verront le pop-up.
    *   **Valeur recommandée :** Toutes les devises, ou des devises spécifiques si le contenu de votre pop-up dépend de la devise.
    *   **Scénario / exemple marchand :** Vous avez une offre spéciale uniquement valable pour les clients payant en USD. Vous sélectionneriez "USD" ici.
-   **Afficher le pop-up pour des pays spécifiques :**
    *   **Ce que fait ce paramètre :** Restreint la visibilité du pop-up aux clients de pays spécifiques.
    *   **Effet de la modification de ce paramètre :** Seuls les clients détectés comme étant des pays sélectionnés verront le pop-up.
    *   **Valeur recommandée :** Tous les pays, ou des pays spécifiques pour les campagnes géo-ciblées.
    *   **Scénario / exemple marchand :** Vous menez une promotion exclusivement pour les clients en France. Vous sélectionneriez "France" ici.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Activer Popup Pro | OUI | Interrupteur principal pour activer/désactiver le pop-up. |
| | Contenu du pop-up (Éditeur HTML) | (Vide) | Concevez ce qui apparaît à l'intérieur du pop-up (texte, images, liens). |
| | Largeur du pop-up (px) | 600-800px | Définit la taille horizontale du pop-up. |
| | Hauteur du pop-up (px) | auto (vide) | Définit la taille verticale du pop-up, ou s'ajuste automatiquement. |
| | Afficher le pop-up sur | Intention de sortie / Chargement de la page (délai de 3-5s) | Détermine le déclencheur de l'apparition du pop-up. |
| | Délai avant l'apparition du pop-up (secondes) | 3-5 | Délai avant l'affichage du pop-up (si "Chargement de la page" sélectionné). |
| | Fréquence du pop-up (jours) | 7-30 | Fréquence à laquelle un client de retour voit le pop-up. |
| | Afficher le pop-up sur les appareils mobiles | OUI | Contrôle la visibilité du pop-up sur les téléphones/tablettes. |
| | Couleur de fond du pop-up | #FFFFFF (Blanc) | Couleur de fond de la fenêtre du pop-up. |
| | Couleur de la bordure du pop-up | Transparent / Gris clair | Couleur de la bordure du pop-up. |
| | Largeur de la bordure du pop-up (px) | 0-2 | Épaisseur de la bordure du pop-up. |
| | Rayon de la bordure du pop-up (px) | 0-10 | Arrondi des coins du pop-up. |
| | Couleur de fond de la superposition | #000000 (Noir) | Couleur de l'arrière-plan semi-transparent derrière le pop-up. |
| | Opacité de la superposition (0-100) | 50-80 | Niveau de transparence de la superposition. |
| | Afficher le bouton de fermeture | OUI | Affiche le bouton 'X' pour fermer le pop-up. |
| | Autoriser la fermeture en cliquant à l'extérieur | OUI | Permet de fermer en cliquant sur la superposition. |
| | Autoriser la fermeture par la touche Échap | OUI | Permet de fermer en appuyant sur la touche Échap. |
| | CSS personnalisé | (Vide) | Ajoutez du CSS personnalisé pour un style avancé. |
| | Animation du pop-up (Effet d'entrée) | Fondu / Glissement vers le bas | Effet visuel lorsque le pop-up apparaît. |
| | Animation du pop-up (Effet de sortie) | Fondu / Glissement vers le haut | Effet visuel lorsque le pop-up disparaît. |
| | Afficher le pop-up sur des pages spécifiques (URL) | (Vide) | Afficher le pop-up uniquement sur les URL spécifiées. |
| | Ne pas afficher le pop-up sur des pages spécifiques (URL) | (Vide) | Masquer le pop-up des URL spécifiées (par exemple, paiement). |
| | Afficher le pop-up pour des groupes de clients spécifiques | Tous | Cible le pop-up vers des types de clients spécifiques. |
| | Afficher le pop-up pour des langues spécifiques | Tous | Cible le pop-up vers des langues spécifiques. |
| | Afficher le pop-up pour des devises spécifiques | Tous | Cible le pop-up vers des devises spécifiques. |
| | Afficher le pop-up pour des pays spécifiques | Tous | Cible le pop-up vers des pays spécifiques. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Mon pop-up ne s'affiche pas du tout. Que dois-je vérifier en premier ?**
**R1 :**

1.  **Le module est-il activé ?** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que "Prestashop Popup Pro" est installé et activé.
2.  **"Activer Popup Pro" est-il réglé sur OUI dans la configuration du module ?** C'est l'interrupteur principal.
3.  **Vérifiez vos paramètres "Afficher le pop-up sur" :** S'il est réglé sur "Délai", assurez-vous que le délai n'est pas trop long. Si "Intention de sortie", assurez-vous que vous le déclenchez correctement (en déplaçant la souris hors de la fenêtre du navigateur).
4.  **Videz le cache de votre PrestaShop :** Allez dans **Paramètres avancés > Performances**, faites défiler vers le bas et cliquez sur "Vider le cache". Parfois, d'anciens fichiers mis en cache empêchent les nouveaux paramètres du module de prendre effet.
5.  **Vérifiez les conflits :** Désactivez temporairement d'autres modules de pop-up ou de superposition pour voir s'il y a un conflit.

**Q2 : Mon pop-up a l'air étrange ou cassé sur les appareils mobiles.**
**R2 :**

1.  **"Afficher le pop-up sur les appareils mobiles" est-il activé ?** Sinon, il ne s'affichera pas du tout.
2.  **Examinez votre "Contenu du pop-up" :** Un HTML complexe, des images très grandes ou un contenu non conçu pour les petits écrans peuvent le casser. Essayez de simplifier le contenu ou d'utiliser des images plus petites et optimisées.
3.  **Vérifiez "Largeur du pop-up" et "Hauteur du pop-up" :** Bien que le module soit réactif, des valeurs en pixels fixes peuvent parfois causer des problèmes sur de très petits écrans. Envisagez de laisser "Hauteur du pop-up" vide pour `auto`.
4.  **CSS personnalisé :** Si vous avez ajouté du CSS personnalisé, il pourrait ne pas être adapté aux mobiles. Testez votre CSS à l'aide des outils de développement du navigateur (inspecter l'élément) sur différentes tailles d'écran.

**Q3 : Le pop-up apparaît trop souvent pour mes clients. Comment puis-je contrôler cela ?**
**R3 :**

1.  **Ajustez la "Fréquence du pop-up (jours)" :** C'est le paramètre clé. Un nombre plus élevé signifie que les clients verront le pop-up moins souvent. Par exemple, le régler sur `30` signifie qu'ils ne le verront qu'une fois par mois après l'avoir fermé.
2.  **Considérez votre paramètre "Afficher le pop-up sur" :** S'il est réglé sur "Chargement de la page" avec un court délai, il peut sembler plus intrusif que "Intention de sortie".

**Q4 : Je veux traduire le contenu de mon pop-up en plusieurs langues. Comment faire ?**
**R4 :** L'éditeur HTML "Contenu du pop-up" devrait prendre en charge la saisie multilingue de PrestaShop. Lors de l'édition du contenu, recherchez les onglets ou les listes déroulantes de langue (généralement en haut à droite de l'éditeur) pour basculer entre les langues et fournir un contenu différent pour chacune. Assurez-vous d'avoir les langues souhaitées installées dans PrestaShop. Si l'éditeur n'affiche pas les onglets de langue, vous devrez peut-être saisir le contenu pour chaque langue manuellement en changeant la langue de votre back office.

**Q5 : Le contenu du pop-up est trop petit/grand, ou la police est incorrecte.**
**R5 :**

1.  **Utilisez l'éditeur HTML :** L'éditeur HTML intégré offre généralement des options pour modifier la taille de la police, la couleur et d'autres styles pour votre texte.
2.  **CSS personnalisé :** Pour un contrôle plus précis, utilisez le champ "CSS personnalisé". Par exemple, pour modifier la taille de la police de tout le texte du pop-up, vous pourriez ajouter :

    ```
    .popuppro-content p { font-size: 16px !important;}
    ```

    (Vous devrez peut-être inspecter le pop-up dans votre navigateur pour trouver les sélecteurs CSS corrects comme `.popuppro-content`).

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé du module Prestashop Popup Pro, destiné aux développeurs, webmasters et agences techniques.

### 4.1 Vue d'ensemble de l'architecture

Le module Prestashop Popup Pro suit une architecture de module PrestaShop standard, exploitant principalement la classe `Module` pour sa fonctionnalité principale et `ModuleFrontController` pour les interactions AJAX. Il repose fortement sur JavaScript pour la logique d'affichage front-office, les animations et la gestion des événements (comme l'intention de sortie). La configuration est gérée via la méthode `getContent()` dans le fichier principal du module, stockant les paramètres dans `ps_configuration`. Le module intègre un gestionnaire de modèles Smarty pour une création de contenu flexible et un sélecteur de couleurs pour la personnalisation de l'interface utilisateur.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :
    -   `popuppro/controllers/front/index.php`
        -   **Nom de la classe :** `PopupproIndexModuleFrontController` (probablement, basé sur la convention de nommage des fichiers)
        -   **Classe parente :** `ModuleFrontController`
        -   **Responsabilité :** Ce contrôleur pourrait servir de point d'entrée général ou de solution de repli pour les requêtes front-office liées au module. Il pourrait être responsable du chargement initial des données ou du rendu d'une vue de module de base si aucune action spécifique n'est demandée.
    -   `popuppro/controllers/front/popuploader.php`
        -   **Nom de la classe :** `PopupproPopuploaderModuleFrontController`
        -   **Classe parente :** `ModuleFrontController`
        -   **Responsabilité :** Ce contrôleur est très probablement responsable du chargement dynamique du contenu et de la configuration du pop-up via AJAX. Lorsqu'un utilisateur visite une page, un script JavaScript enverrait une requête AJAX à ce contrôleur pour récupérer le HTML, le style et les paramètres comportementaux du pop-up en fonction de la configuration du module. Il renverrait une charge utile JSON ou HTML.
    -   `popuppro/controllers/front/popupstat.php`
        -   **Nom de la classe :** `PopupproPopupstatModuleFrontController`
        -   **Classe parente :** `ModuleFrontController`
        -   **Responsabilité :** Ce contrôleur est conçu pour gérer les données statistiques liées au pop-up. Il recevrait des requêtes AJAX du JavaScript front-office pour enregistrer les impressions de pop-up, les clics sur le bouton de fermeture ou d'autres interactions, permettant au module de suivre les performances (bien qu'une vue de statistiques dédiée ne soit pas explicitement répertoriée dans les contrôleurs d'administration, ces données pourraient être stockées pour une utilisation future ou une journalisation interne).
-   **Contrôleurs d'administration Back-Office** : Aucun explicitement répertorié, ce qui indique que toute l'administration est gérée via la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

Aucune classe personnalisée ou définition `ObjectModel` n'est répertoriée dans le répertoire `classes/`. Cela suggère que le module stocke principalement sa configuration directement dans la table `ps_configuration` à l'aide de `Configuration::updateValue()` et `Configuration::get()`, et ne gère pas d'entités de données personnalisées complexes nécessitant des tables de base de données dédiées ou un mappage `ObjectModel`.

### 4.4 Actifs JavaScript (`views/js/`)

-   `popuppro/js/popup-engine.js` :
    -   **Portée :** Front-office.
    -   **Détail :** Il s'agit probablement du fichier JavaScript principal responsable des mécanismes fondamentaux du pop-up. Il gérerait la création des éléments DOM du pop-up (la superposition, le conteneur du pop-up, le bouton de fermeture), l'injection du contenu, la gestion des animations (effets d'entrée/sortie) et le positionnement du pop-up à l'écran. Il définit probablement l'objet `PopupPro` principal ou similaire.
-   `popuppro/js/popup-events.js` :
    -   **Portée :** Front-office.
    -   **Détail :** Ce script gérerait tous les écouteurs d'événements qui déclenchent le pop-up. Cela inclut :
        -   `DOMContentLoaded` ou `window.load` pour la configuration initiale.
        -   `setTimeout` pour les pop-ups à délai.
        -   Écouteurs d'événements de défilement pour les pop-ups déclenchés par le défilement.
        -   `mouseleave` ou des événements similaires sur `document.body` pour la détection de l'intention de sortie.
        -   Écouteurs de clic pour le bouton de fermeture et la fermeture par clic à l'extérieur.
        -   Écouteur `keyup` pour la touche Échap.
        -   Appels AJAX à `popuploader.php` pour récupérer le contenu et à `popupstat.php` pour enregistrer les événements.
-   `popuppro/js/popup-scripts.js` :
    -   **Portée :** Front-office.
    -   **Détail :** Ce fichier pourrait contenir des scripts supplémentaires, peut-être plus spécifiques, liés au comportement ou aux interactions du pop-up, gérant éventuellement les soumissions de formulaires dans le pop-up, les mises à jour de contenu dynamique ou l'intégration avec d'autres éléments du front-office.
-   `popuppro/js/script.js` :
    -   **Portée :** Front-office/Back-office (nom générique, pourrait être l'un ou l'autre).
    -   **Détail :** Compte tenu de son nom générique, il pourrait s'agir d'un script utilitaire général, ou il pourrait contenir la logique d'initialisation du pop-up sur le front-office, ou même un script mineur de back-office s'il y est chargé. Il est courant que les modules aient un `script.js` pour le code à usage général.
-   `popuppro/js/tinymce16-force-urls.inc.js`, `popuppro/js/tinymce16.inc.js` :
    -   **Portée :** Back-office.
    -   **Détail :** Ces fichiers sont liés à l'éditeur de texte riche TinyMCE, spécifiquement la version 1.6. Ils sont inclus pour fournir la fonctionnalité d'éditeur HTML pour le champ "Contenu du pop-up" dans la configuration du back-office du module. `tinymce16-force-urls.inc.js` gère probablement la garantie que les URL sont correctement formatées dans l'éditeur.
-   `popuppro/jscolor/jscolor.js` :
    -   **Portée :** Back-office.
    -   **Détail :** Il s'agit de la bibliothèque JavaScript pour la fonctionnalité de sélecteur de couleurs utilisée dans la configuration du back-office (par exemple, pour la couleur de fond du pop-up, la couleur de la bordure, la couleur de la superposition). Elle fournit l'interface interactive de sélection des couleurs.
-   `popuppro/lib/smartyTemplatesManager/js/smartyTemplatesManager.js` :
    -   **Portée :** Back-office.
    -   **Détail :** Ce script fait partie d'une bibliothèque interne pour la gestion des modèles Smarty dans la configuration du module. Il fournit probablement des fonctionnalités pour prévisualiser les modèles, les sélectionner ou insérer dynamiquement du contenu basé sur des modèles dans l'éditeur HTML.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `popuppro/css.css` :
    -   **Portée :** Front-office.
    -   **Détail :** Il s'agit probablement de la feuille de style principale pour le pop-up du front-office, définissant son apparence par défaut : positionnement, taille, bordure, ombre, style du bouton de fermeture et potentiellement des ajustements réactifs.
    -   **Sélecteurs clés :** `.popuppro-overlay`, `.popuppro-popup`, `.popuppro-close-btn`, `.popuppro-content`.
-   `popuppro/lib/smartyTemplatesManager/css/smartyTemplatesManager.css` :
    -   **Portée :** Back-office.
    -   **Détail :** Feuilles de style pour l'interface du gestionnaire de modèles Smarty dans la configuration du back-office du module. Il styliserait la sélection de modèles, les zones de prévisualisation et les éléments d'interface utilisateur associés.
-   `popuppro/popuppro.css` :
    -   **Portée :** Front-office.
    -   **Détail :** Similaire à `css.css`, cela pourrait contenir des styles supplémentaires ou spécifiques pour le pop-up, potentiellement pour différents états d'animation ou des éléments de contenu spécifiques. Il pourrait y avoir un certain chevauchement ou une séparation des préoccupations entre `css.css` et `popuppro.css`.
    -   **Sélecteurs clés :** Probablement similaires à `css.css`, se concentrant sur les principaux composants du pop-up.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** : (Aucun explicitement répertorié dans `views/templates/hook/`, mais `views/header.tpl` est probablement hooké)
    -   `popuppro/views/header.tpl` :
        -   **Hook :** `displayHeader`
        -   **Sortie :** Ce modèle est presque certainement hooké dans `displayHeader`. Il serait responsable de l'injection des fichiers JavaScript et CSS nécessaires dans la section `<head>` du front-office, et potentiellement d'une structure HTML initiale ou de données de configuration à utiliser par JavaScript.
    -   `popuppro/views/header_address.tpl`, `popuppro/views/header_carrier.tpl` :
        -   **Hook :** Potentiellement `displayHeader` ou d'autres hooks spécifiques liés aux informations d'adresse/transporteur.
        -   **Sortie :** Ceux-ci semblent être des modèles d'en-tête spécialisés, éventuellement pour afficher du contenu dynamique lié à l'adresse du client ou aux informations du transporteur *dans* un pop-up, ou pour des scénarios de pop-up spécifiques. Leur utilisation exacte dépendrait de la logique du module.
    -   `popuppro/views/popup.tpl` :
        -   **Hook :** Non directement hooké, mais rendu par JavaScript.
        -   **Sortie :** C'est le modèle principal pour la structure du pop-up du front-office. Il définit le HTML pour la superposition, le conteneur du pop-up, le bouton de fermeture et un espace réservé pour le contenu dynamique chargé via AJAX.
-   **Modèles d'administration (`views/templates/admin/`)** :
    -   `popuppro/views/admin/admin.tpl` :
        -   **Objectif :** Le modèle principal pour la page de configuration du module dans le back office. Il contiendrait la mise en page globale, les onglets et la structure des formulaires de paramètres.
    -   `popuppro/views/admin/boscript.tpl` :
        -   **Objectif :** Modèle JavaScript du back-office. Cela injecte probablement du code JavaScript spécifique nécessaire à la page de configuration de l'administration, tel que l'initialisation de TinyMCE, du sélecteur de couleurs ou la validation de formulaire personnalisée.
    -   `popuppro/views/admin/popup_preview.tpl` :
        -   **Objectif :** Modèle pour afficher un aperçu en direct ou simulé du pop-up dans la configuration du back-office, permettant aux marchands de voir les modifications au fur et à mesure qu'ils les apportent.
    -   `popuppro/views/admin/presets.tpl` :
        -   **Objectif :** Modèle pour gérer ou afficher des modèles ou des styles de pop-up prédéfinis.
    -   `popuppro/views/admin/shadow_editor.tpl` :
        -   **Objectif :** Un modèle spécialisé pour configurer les effets d'ombre pour le pop-up, offrant potentiellement des contrôles avancés au-delà de la simple couleur/opacité.
    -   `popuppro/views/admin/stats.tpl` :
        -   **Objectif :** Si le module collecte des statistiques (comme suggéré par `popupstat.php`), ce modèle serait utilisé pour afficher ces statistiques dans le back office.
    -   `popuppro/views/templates/admin/_configure/helpers/form/form.tpl` :
        -   **Objectif :** Il s'agit d'un modèle de remplacement PrestaShop standard pour la classe `HelperForm`, spécifiquement pour le formulaire de configuration du module. Il permet au module de personnaliser la façon dont son formulaire de paramètres est rendu, en ajoutant potentiellement des champs ou une mise en page personnalisés.
-   **Modèles de la bibliothèque SmartyTemplatesManager (`popuppro/lib/smartyTemplatesManager/tpl/` et `views/`)** :
    -   `popuppro/lib/smartyTemplatesManager/tpl/cartMini.tpl`, `example.tpl`, `freeShippingBar.tpl`, `helloCustomer.tpl`, `lastOrder.tpl`, `productHighlight.tpl`, `showReachedQtyInCart.tpl` :
        -   **Objectif :** Ce sont des modèles de contenu prédéfinis que le marchand peut sélectionner ou utiliser comme point de départ pour le contenu de son pop-up. Ils offrent des cas d'utilisation courants comme les affichages de mini-panier, les annonces de livraison gratuite, les messages de bienvenue, les détails de la dernière commande, les mises en avant de produits ou les messages de quantité atteinte dans le panier. Ceux-ci seraient rendus dynamiquement dans la zone de contenu principale du pop-up.
    -   `popuppro/lib/smartyTemplatesManager/views/buttonManager.tpl`, `buttonManagerNoJs.tpl`, `createTemplateForm.tpl`, `editTemplateForm.tpl`, `mainForm.tpl`, `selectInput.tpl` :
        -   **Objectif :** Ces modèles font partie de la bibliothèque interne Smarty Templates Manager, utilisée dans la configuration du back-office pour gérer et interagir avec les modèles de contenu. Ils fournissent une interface utilisateur pour créer, modifier et sélectionner ces blocs de contenu prédéfinis.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** :
    -   Le module ne semble pas créer de tables SQL personnalisées.
    -   Tous les paramètres de configuration sont stockés dans la table `ps_configuration`. Les noms de configuration clés suivraient généralement le modèle `POPUPPRO_SETTING_NAME`. Exemples :
        -   `POPUPPRO_ENABLED`
        -   `POPUPPRO_CONTENT` (probablement multilingue)
        -   `POPUPPRO_WIDTH`
        -   `POPUPPRO_DISPLAY_ON`
        -   `POPUPPRO_FREQUENCY`
        -   `POPUPPRO_BG_COLOR`
        -   …et ainsi de suite pour toutes les options de configuration.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Exécuté dans la section `<head>` de chaque page du front-office. | Injecte les fichiers CSS et JavaScript nécessaires au fonctionnement du pop-up, et potentiellement initialise des variables JavaScript globales ou des données de configuration. |
| `displayRightColumn` | Exécuté dans la colonne de droite des pages (si activé par le thème). | Bien que la description du module mentionne les "Colonnes", c'est moins probable pour un pop-up plein écran. Si utilisé, il pourrait rendre un déclencheur pour le pop-up ou un élément plus petit, non superposé. |
| `displayLeftColumn` | Exécuté dans la colonne de gauche des pages (si activé par le thème). | Similaire à `displayRightColumn`, moins probable pour le pop-up principal, mais pourrait être utilisé pour un déclencheur. |
| `displayFooter` | Exécuté en bas de chaque page du front-office, avant la balise `</body>` de fermeture. | Pourrait être utilisé pour injecter du JavaScript qui doit s'exécuter après le chargement complet du DOM, ou pour placer la structure HTML du pop-up à la toute fin du document. |
| `displayProductAdditionalInfo` (ou hook de page produit similaire) | Exécuté sur la page produit, généralement sous les détails principaux du produit. | Si le module prend en charge les pop-ups spécifiques aux produits, il pourrait utiliser ce hook pour injecter un déclencheur ou une logique de pop-up spécifique pertinente au produit. |
| `actionFrontControllerSetMedia` | Exécuté lorsqu'un contrôleur frontal définit ses médias (CSS/JS). | Un hook courant pour les modules afin d'enregistrer efficacement leurs actifs (CSS/JS), garantissant qu'ils ne sont chargés qu'en cas de besoin. |

## 5. Support officiel et mises à jour

Pour le support officiel, les mises à jour du module et toute assistance supplémentaire avec votre module Prestashop Popup Pro, veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support dédiée est prête à vous aider à maximiser le potentiel de votre module.
