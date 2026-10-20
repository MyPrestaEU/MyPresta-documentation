---
title: "Banque Nationale Hongroise (MNB) - taux de change - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Banque Nationale Hongroise (MNB) - taux de change par MyPresta.eu."
sidebar:
  label: "Banque Nationale Hongroise (MNB) - taux de change - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Hungarian National Bank (MNB) - currency exchange rates sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/hungarian-national-bank-mnb-currency-exchange-rates.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/hungarian-national-bank-mnb-currency-exchange-rates/)
>
> ---


# Banque Nationale Hongroise (MNB) - taux de change

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour la communication API externe, ce qui est courant pour les modules de taux de change. Assurez-vous que votre environnement d'hébergement les prend en charge.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à l'écran de configuration principal du module. C'est ici que vous définissez la manière dont le module récupère et applique les taux de change.

#### **Paramètres et options**

La page de configuration du module « Banque Nationale Hongroise (MNB) - taux de change » présentera généralement un formulaire avec diverses options pour contrôler son comportement. Bien que les noms de champs spécifiques puissent varier légèrement, la fonctionnalité principale tourne autour de l'activation du processus de mise à jour et de sa planification éventuelle.

1. **Activer les mises à jour des taux de change MNB**

   - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver les mises à jour automatiques des taux de change de la Banque Nationale Hongroise.
   - **Effet de la modification de ce paramètre :**
     - *Lorsqu'il est activé (OUI) :* Le module récupérera périodiquement les derniers taux de change de la MNB et les appliquera aux devises configurées de votre boutique. Cela garantit que vos prix sont toujours à jour.
     - *Lorsqu'il est désactivé (NON) :* Le module cessera de récupérer et d'appliquer les taux de change MNB. Les taux de devise de votre boutique resteront tels qu'ils ont été définis pour la dernière fois (manuellement ou par le module avant sa désactivation).
   - **Valeur recommandée :** OUI
   - **Scénario / exemple de marchand :** Si vous souhaitez que votre boutique reflète automatiquement les derniers taux de change MNB pour le HUF, l'EUR, l'USD, etc., vous devez activer ce paramètre. Si vous préférez gérer les taux manuellement ou utiliser un système différent, vous le désactiveriez.
2. **URL de la tâche Cron (pour les mises à jour automatiques)**

   - **Ce que fait ce paramètre :** Ce champ affiche une URL unique que vous pouvez utiliser pour configurer une « tâche cron » sur votre serveur web. Une tâche cron est une tâche planifiée qui indique à votre serveur de visiter cette URL à intervalles réguliers, déclenchant ainsi le module pour mettre à jour automatiquement les taux de change.
   - **Effet de la modification de ce paramètre :** Ce n'est pas un paramètre que vous modifiez directement, mais plutôt une URL que vous copiez.
     - *Lorsque la tâche cron est configurée :* Votre serveur appellera périodiquement cette URL, et le module exécutera son processus de mise à jour en arrière-plan sans que vous ayez besoin de faire quoi que ce soit.
     - *Lorsque la tâche cron N'EST PAS configurée :* Vous devrez visiter manuellement cette URL dans votre navigateur (ou cliquer sur un bouton « Exécuter la mise à jour maintenant » si disponible) pour déclencher une mise à jour. Ce n'est pas recommandé pour une utilisation régulière.
   - **Valeur recommandée :** Copiez cette URL et configurez une tâche cron sur votre panneau d'hébergement (par exemple, cPanel, Plesk, ou ligne de commande du serveur) pour qu'elle s'exécute au moins une fois par jour, ou plus fréquemment si votre entreprise l'exige.
   - **Scénario / exemple de marchand :** Vous souhaitez que vos taux de change soient mis à jour tous les matins à 3h du matin. Vous copieriez cette URL, iriez à la section « Tâches Cron » de votre panneau de contrôle d'hébergement, et créeriez une nouvelle tâche cron qui exécute `wget -O /dev/null -q "VOTRE_URL_DE_TACHE_CRON_ICI"` (ou une commande similaire) quotidiennement à 3h du matin.
3. **Heure de la dernière mise à jour** (Affichage informatif)

   - **Ce que fait ce paramètre :** Il s'agit d'un champ d'affichage uniquement qui vous indique la dernière fois que les taux de change ont été mis à jour avec succès par le module.
   - **Effet de la modification de ce paramètre :** Ce n'est pas un paramètre configurable. Il fournit simplement un retour d'information sur l'activité du module.
   - **Valeur recommandée :** N/A (informatif)
   - **Scénario / exemple de marchand :** Vous pouvez rapidement vérifier cet horodatage pour confirmer que votre tâche cron s'exécute correctement et que les taux sont mis à jour comme prévu. Si l'heure est ancienne, cela indique un problème avec la configuration de votre tâche cron.

#### **Tableau de référence rapide de la configuration**

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Config du module | Activer les mises à jour des taux de change MNB | OUI | Active/désactive la récupération et l'application automatiques des taux de change MNB. |
| Config du module | URL de la tâche Cron | N/A (Copier et configurer) | URL pour configurer une tâche planifiée (tâche cron) pour les mises à jour automatiques des taux. |
| Config du module | Heure de la dernière mise à jour | N/A (Informatif) | Affiche l'horodatage de la dernière mise à jour réussie des taux de change. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes taux de change ne se mettent pas à jour. Que dois-je faire ?**
R1 :

1. **Vérifiez « Activer les mises à jour des taux de change MNB » :** Assurez-vous que ce paramètre est défini sur OUI dans la configuration du module.
2. **Vérifiez la configuration de la tâche Cron :** La raison la plus courante des non-mises à jour est une tâche cron mal configurée.
   - Assurez-vous d'avoir copié l'« URL de la tâche Cron » exacte du module.
   - Vérifiez les paramètres de la tâche cron dans votre panneau de contrôle d'hébergement (cPanel, Plesk, etc.).
   - Confirmez que la commande est correcte (par exemple, `wget -O /dev/null -q "VOTRE_URL_DE_TACHE_CRON"`).
   - Vérifiez la planification (par exemple, `* * * * *` pour chaque minute, `0 3 * * *` pour 3h du matin tous les jours).
   - Recherchez les journaux d'erreurs liés à la tâche cron dans votre panneau d'hébergement.
3. **Vérifiez l'« Heure de la dernière mise à jour » :** Si cet horodatage est ancien, cela confirme que la tâche cron ne s'exécute pas.
4. **Connectivité du serveur :** Assurez-vous que votre serveur peut établir des connexions sortantes vers des sites web externes (comme l'API de la MNB). Parfois, les pare-feu ou les paramètres de sécurité peuvent bloquer cela. Contactez votre hébergeur si vous suspectez cela.

**Q2 : J'ai activé le module, mais certaines devises ne se mettent pas à jour.**
R2 :

1. **Activation des devises :** Allez dans **International > Devises** dans votre Back Office PrestaShop. Assurez-vous que les devises que vous attendez de voir mises à jour sont activées (actives). Le module ne met à jour que les devises actives.
2. **Support MNB :** La MNB fournit des taux pour des devises spécifiques. Si une devise n'est pas prise en charge par la MNB, le module ne peut pas la mettre à jour. Vous devrez peut-être définir manuellement les taux pour ces devises ou utiliser un autre module pour elles.

**Q3 : Mon thème personnalisé n'affiche pas correctement les prix après la mise à jour.**
R3 : Ce module met principalement à jour les *données* (taux de change) dans la base de données de votre PrestaShop. Il n'affecte pas directement la façon dont les prix sont *affichés* par votre thème. Si vous rencontrez des problèmes d'affichage :

1. **Videz le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty »).
2. **Personnalisation du thème :** Si votre thème a une logique d'affichage des prix fortement personnalisée, cela pourrait interférer. Consultez la documentation de votre thème ou contactez le développeur de votre thème.
3. **Cache du navigateur :** Demandez à vos clients de vider le cache de leur navigateur ou d'essayer un navigateur différent pour exclure les problèmes de cache côté client.

**Q4 : Puis-je annuler manuellement un taux de change après que le module l'ait mis à jour ?**
R4 : Oui, vous le pouvez. Une fois le module exécuté, les taux sont stockés dans la base de données de PrestaShop. Vous pouvez aller dans **International > Devises**, modifier une devise spécifique et ajuster manuellement son taux de change. Cependant, sachez que la prochaine fois que la tâche cron s'exécutera, le module écrasera vos modifications manuelles avec les dernières données de la MNB. Si vous avez besoin d'un contrôle manuel permanent sur une devise spécifique, vous pourriez envisager de désactiver les mises à jour du module pour cette devise (si le module offre un tel paramètre granulaire, ce qui est rare) ou de désactiver complètement le module et de gérer tous les taux manuellement.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Vue d'ensemble de l'architecture

Le module « Banque Nationale Hongroise (MNB) - taux de change » suit une architecture de module PrestaShop standard, se concentrant principalement sur le traitement en arrière-plan. Il utilise la classe `Module` de PrestaShop pour l'installation et la configuration, et `ModuleFrontController` pour gérer l'exécution de la tâche cron. La logique principale implique l'envoi d'une requête HTTP à l'API officielle des taux de change de la MNB (probablement un flux XML), l'analyse de la réponse, puis la mise à jour de la table `ps_currency` dans la base de données PrestaShop.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :

  - `mnbrates/controllers/front/cronjob.php`
    - **Nom de la classe et classe parente** : `MnbratesCronjobModuleFrontController` étendant `ModuleFrontController`
    - **Responsabilité** : Ce contrôleur est le point d'entrée de la tâche cron planifiée. Lorsque son URL est accédée (par exemple, `votreboutique.com/module/mnbrates/cronjob`), il déclenche la logique principale du module pour récupérer et mettre à jour les taux de change. Il gère généralement la requête HTTP, appelle la méthode de mise à jour du module principal et renvoie un simple message de succès/échec ou aucune sortie (pour une exécution cron silencieuse).
  - `mnbrates/controllers/front/index.php`
    - **Nom de la classe et classe parente** : `MnbratesIndexModuleFrontController` étendant `ModuleFrontController`
    - **Responsabilité** : Il s'agit d'un contrôleur de remplacement standard souvent inclus dans les modules. Dans de nombreux cas, il peut simplement rediriger vers la page d'accueil ou servir de solution de repli. Pour ce module spécifique, son objectif principal est probablement d'empêcher l'affichage du répertoire si quelqu'un tente d'accéder directement à `/module/mnbrates/`, ou il pourrait s'agir d'un fichier vestigial. Il est peu probable qu'il contienne la logique métier principale pour les mises à jour des taux de change.
- **Contrôleurs d'administration Back-Office** :

  - Aucun contrôleur d'administration dédié (`controllers/admin/`) n'est identifié. Cela signifie que toute la configuration du back-office est gérée directement dans la méthode `getContent()` du fichier de module principal.

### 4.3 Classes et modèles principaux (`classes/`)

Aucune classe ou modèle personnalisé n'est identifié dans le répertoire `classes/`. Cela suggère que le module effectue probablement ses opérations directement dans le fichier de module principal `cronjob.php`, en utilisant potentiellement l'`ObjectModel` `Currency` de PrestaShop pour mettre à jour les taux.

### 4.4 Actifs JavaScript (`views/js/`)

Aucun fichier JavaScript n'est identifié. Cela confirme la nature axée sur le backend du module, sans composants front-office interactifs ni formulaires back-office complexes nécessitant du JS dynamique.

### 4.5 Feuilles de style CSS (`views/css/`)

Aucun fichier CSS n'est identifié. Cela indique que le module n'introduit aucun style personnalisé pour le front-office ou le back-office. La configuration du back-office héritera des styles de thème d'administration par défaut de PrestaShop.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **Modèles d'administration (`views/templates/admin/`)** :
  - `mnbrates/views/admin.tpl`
    - **Objectif** : Ce modèle est rendu par la méthode `getContent()` du fichier de module principal (`mnbrates/cronjob.php`). Il définit la structure et le contenu de la page de configuration du module dans le Back Office de PrestaShop. Il contiendra les éléments de formulaire pour activer/désactiver les mises à jour, afficher l'URL de la tâche cron et afficher l'horodatage de la dernière mise à jour.
- **Modèles de hook (`views/templates/hook/`)** : Aucun identifié.
- **Modèles front-office (`views/templates/front/`)** : Aucun identifié.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne crée pas de tables SQL personnalisées. Il interagit avec la table `ps_currency` de PrestaShop pour mettre à jour le champ `conversion_rate` pour chaque devise.
  - Les paramètres de configuration (comme `PS_MNBRATES_ENABLED`, `PS_MNBRATES_LAST_UPDATE`) sont stockés dans la table `ps_configuration`.
- **Table des hooks enregistrés** :
  Le module enregistre probablement des hooks lors de sa méthode `install()`. Compte tenu de sa fonctionnalité, le hook le plus crucial est celui de la tâche cron, qui est géré par un contrôleur frontal. D'autres hooks pourraient être à des fins d'information ou pour assurer la compatibilité.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rendu dans la section `<head>` de toutes les pages du front-office. | Peu susceptible d'être utilisé pour la logique principale, éventuellement pour ajouter une balise meta ou un JS/CSS très simple (bien qu'aucun n'ait été identifié). |
| `displayRightColumn` | Rendu dans la colonne de droite des pages où elle est disponible. | Peu susceptible d'être utilisé pour la logique principale, éventuellement pour un petit bloc d'information si le module avait un composant front-office. |
| `displayLeftColumn` | Rendu dans la colonne de gauche des pages où elle est disponible. | Similaire à `displayRightColumn`. |
| `displayFooter` | Rendu dans le pied de page de toutes les pages du front-office. | Similaire à `displayHeader`, mais en bas. |
| `displayProductExtraContent` | Rend du contenu additionnel sur la page produit. | Peu probable pour ce module. |
| `actionModuleInstall` | Exécuté lors de l'installation d'un module. | Enregistre les hooks nécessaires et définit les valeurs de configuration par défaut. |
| `actionModuleUninstall` | Exécuté lors de la désinstallation d'un module. | Nettoie les valeurs de configuration et désenregistre les hooks. |
| `actionModuleUpdate` | Exécuté lors de la mise à jour d'un module. | Gère les changements de schéma ou les migrations de configuration entre les versions. |
| (Implicite) `frontController` dispatch | Lorsque `mnbrates/controllers/front/cronjob.php` est accédé. | Déclenche la logique principale de mise à jour des taux de change. C'est le « hook » principal pour la tâche cron. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Banque Nationale Hongroise (MNB) - taux de change », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe s'engage à garantir le fonctionnement optimal de votre module et que votre boutique bénéficie des fonctionnalités et de la compatibilité les plus récentes.
