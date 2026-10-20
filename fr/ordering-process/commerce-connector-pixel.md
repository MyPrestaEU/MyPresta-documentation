---
title: "Pixel Commerce Connector - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Pixel Commerce Connector par MyPresta.eu."
sidebar:
  label: "Pixel Commerce Connector - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Commerce Connector pixel sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/commerce-connector-pixel.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/commerce-connector-pixel/)
>
> ---


# Pixel Commerce Connector

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes pour les modules PrestaShop. Aucune configuration de serveur spéciale n'est généralement nécessaire pour ce module.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Pixel Commerce Connector » pour accéder à ses paramètres.

#### **Identifiant de la boutique**

- **Ce que fait ce paramètre :** Il s'agit de l'identifiant unique que vous a fourni Commerce Connector pour votre boutique ou compte marchand spécifique. Il est crucial pour Commerce Connector d'attribuer correctement les données de vente à votre compte.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur votre ID de boutique correct :* Le pixel se déclenchera avec votre identifiant unique, permettant à Commerce Connector de suivre précisément les ventes de votre boutique.
  - *Lorsqu'il est incorrect ou vide :* Le pixel pourrait ne pas se déclencher correctement, ou les données de vente pourraient être attribuées au mauvais compte, entraînant un suivi inexact et potentiellement une perte d'informations marketing.
- **Valeur recommandée :** Saisissez la chaîne exacte « Identifiant de la boutique » fournie par Commerce Connector. Il s'agit généralement d'une combinaison de lettres et de chiffres.
- **Scénario / exemple marchand :** Commerce Connector vous indique que votre ID de boutique est « MYSTORE12345 ». Vous saisiriez « MYSTORE12345 » dans ce champ. Sans cela, Commerce Connector ne saura pas de quelle boutique provient la vente.

#### **Journaliser les lancements de pixels**

- **Ce que fait ce paramètre :** Ce paramètre contrôle si le module enregistre un journal de chaque fois que le pixel Commerce Connector est lancé (c'est-à-dire, chaque fois qu'un client atteint la page de confirmation de commande et que le pixel tente de se déclencher). Ce journal peut être utile pour le dépannage.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (« Oui ») :* Le module créera un fichier journal (généralement dans le répertoire du module) détaillant chaque lancement de pixel, y compris les détails de la commande. Cela peut vous aider à vérifier si le pixel se déclenche comme prévu.
  - *Lorsqu'il est désactivé (« Non ») :* Aucun fichier journal ne sera généré, ce qui est le paramètre standard pour une boutique en production afin d'économiser de l'espace disque et du traitement.
- **Valeur recommandée :** « Non » pour une boutique en production. N'activez « Oui » que temporairement si vous rencontrez des problèmes et avez besoin de vérifier l'activité du pixel.
- **Scénario / exemple marchand :** Vous soupçonnez que le pixel ne suit pas toutes les ventes. Vous activez « Journaliser les lancements de pixels » sur « Oui », effectuez une commande test, puis vérifiez le fichier journal pour voir si votre commande test a été enregistrée, confirmant que le pixel s'est déclenché. Une fois confirmé, vous le désactivez.

#### **Activer / Désactiver le module**

- **Ce que fait ce paramètre :** Il s'agit d'un interrupteur de module PrestaShop standard qui vous permet d'activer ou de désactiver globalement l'ensemble du module Pixel Commerce Connector.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Le module sera actif, et le pixel Commerce Connector sera injecté dans votre page de confirmation de commande, suivant les ventes.
  - *Lorsqu'il est désactivé :* Le module sera inactif, et le pixel Commerce Connector NE SERA PAS présent sur votre page de confirmation de commande, ce qui signifie qu'aucune vente ne sera suivie via ce module.
- **Valeur recommandée :** « Oui » si vous utilisez activement Commerce Connector pour le suivi des ventes.
- **Scénario / exemple marchand :** Vous avez terminé votre intégration Commerce Connector et souhaitez commencer à suivre les ventes. Vous vous assurez que ce paramètre est sur « Oui ». Si vous suspendez temporairement vos campagnes Commerce Connector, vous pourriez le désactiver pour éviter un déclenchement inutile du pixel.

#### Autres clés de configuration (internes)

Le module utilise également des clés de configuration internes comme `mypresta_updates`, `update_`, `updatev_`, `COMCONN_SIDENT_`, `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`. Celles-ci sont généralement destinées à la gestion interne du module, aux vérifications de mises à jour et à la gestion des langues dans le back office de PrestaShop. Les marchands n'ont généralement pas besoin d'interagir directement avec celles-ci.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Identifiant de la boutique | Votre ID Commerce Connector unique | Crucial pour attribuer les données de vente à votre compte Commerce Connector spécifique. |
| Configuration du module | Journaliser les lancements de pixels | Non | Contrôle si le module crée un fichier journal des déclenchements de pixels. Activer pour le dépannage, désactiver pour la production. |
| Configuration du module | Activer / Désactiver le module | Oui | Active ou désactive globalement l'ensemble du module et son suivi de pixels. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai installé le module, mais Commerce Connector n'affiche aucune vente. Que dois-je faire ?**
R :

1.  **Vérifiez l'« Identifiant de la boutique » :** Allez dans la configuration du module et assurez-vous que votre « Identifiant de la boutique » est saisi correctement et correspond exactement à ce que Commerce Connector a fourni.
2.  **Module activé :** Assurez-vous que le module est activé sur la page de configuration.
3.  **Videz le cache :** Allez dans **Paramètres avancés > Performances** dans votre back office PrestaShop et videz le cache Smarty et tous les caches.
4.  **Achat test :** Effectuez un achat test complet sur votre boutique, en allant jusqu'à la page de confirmation de commande.
5.  **Activez la journalisation :** Activez temporairement « Journaliser les lancements de pixels » dans la configuration du module, effectuez un autre achat test, puis vérifiez le fichier `logFile.tpl` (ou un fichier journal similaire) dans le répertoire du module via FTP pour voir si le lancement du pixel a été enregistré.
6.  **Contactez le support :** Si les problèmes persistent, contactez le support MyPresta.eu avec les détails de votre configuration et toutes les entrées de journal.

**Q : Ce module va-t-il ralentir mon site web ?**
R : Non. Le pixel Commerce Connector est un script très léger qui ne se charge que sur la page de confirmation de commande. Cette page est généralement atteinte après l'expérience d'achat principale, et l'exécution du pixel est minimale, de sorte qu'il n'aura pas d'impact notable sur les performances ou la vitesse de chargement de votre boutique pour les clients.

**Q : Puis-je utiliser ce module avec d'autres pixels de suivi (par exemple, Google Analytics, Facebook Pixel) ?**
R : Oui, absolument. Ce module est conçu pour s'intégrer spécifiquement à Commerce Connector. Il fonctionne indépendamment et n'entrera pas en conflit avec d'autres pixels de suivi ou scripts d'analyse que vous avez installés sur votre boutique PrestaShop.

**Q : Où puis-je trouver le fichier journal si j'active « Journaliser les lancements de pixels » ?**
R : S'il est activé, le fichier journal est généralement généré dans le répertoire du module. Vous auriez besoin d'un accès FTP à votre serveur pour naviguer vers `votre_racine_prestashop/modules/comconn/views/templates/hook/logFile.tpl` (ou un chemin similaire) pour afficher son contenu. N'oubliez pas de désactiver la journalisation une fois le dépannage terminé.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module Pixel Commerce Connector (`comconn`) est un module PrestaShop simple conçu pour injecter un pixel JavaScript spécifique sur la page de confirmation de commande. Il adhère à l'architecture des modules PrestaShop, exploitant principalement le hook `displayOrderConfirmation` pour rendre son script de suivi. La logique du module est contenue dans son fichier PHP principal, la configuration étant gérée via `getContent()` et les templates pour le rendu du pixel et d'un journal optionnel.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. Le module se connecte directement à `displayOrderConfirmation` et rend son contenu via un template.
- **Contrôleurs Admin Back-Office** : Aucun. Toute la configuration est gérée dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles de base (`classes/`)

- Aucun. Le module ne définit aucune classe personnalisée ni aucune instance d'`ObjectModel`. Toute la logique est autonome dans `comconn.php`.

### 4.4 Actifs JavaScript (`views/js/`)

- Aucun. Le module intègre directement le script du pixel Commerce Connector dans son template Smarty, plutôt que de lier des fichiers `.js` externes.

### 4.5 Feuilles de style CSS (`views/css/`)

- Aucun. Le module n'ajoute aucun style personnalisé au front ou au back office.

### 4.6 Structure des templates Smarty (`views/templates/`)

Le module utilise des templates Smarty pour rendre sa sortie.

- **Templates de hook (`views/templates/hook/`)** :

  - `comconn/views/templates/hook/displayOrderConfirmation.tpl`
    - **Hook** : `displayOrderConfirmation`
    - **Objectif** : C'est le template principal responsable du rendu du script du pixel Commerce Connector. Il insère dynamiquement l'« Identifiant de la boutique » (à partir de la configuration `COMCONN_SIDENT`) et les détails de la commande (ID de commande, total, devise, produits) dans le code JavaScript qui déclenche le pixel. Ce template est crucial pour la fonctionnalité principale du module.
  - `comconn/views/templates/hook/logFile.tpl`
    - **Hook** : Non directement hooké, mais utilisé par le mécanisme de journalisation interne du module.
    - **Objectif** : Ce template est utilisé pour formater et stocker les entrées de journal lorsque l'option « Journaliser les lancements de pixels » est activée. Il enregistre les détails de chaque lancement de pixel, y compris l'horodatage, l'ID de commande et les données envoyées à Commerce Connector. Les développeurs peuvent inspecter ce fichier via FTP pour le dépannage.
- **Templates d'administration (`views/templates/admin/`)** : Aucun.
- **Templates Front-office (`views/templates/front/`)** : Aucun.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** : Le module ne crée aucune table de base de données personnalisée. Il stocke ses paramètres de configuration dans la table standard `ps_configuration`.

  - Entrées `PS_CONFIGURATION` :
    - `COMCONN_SIDENT` : Stocke l'ID de boutique Commerce Connector du marchand.
    - `COMCONN_LOG` : Stocke la valeur booléenne (0 ou 1) pour activer/désactiver la journalisation des lancements de pixels.
    - `mypresta_updates`, `update_`, `updatev_` : Clés internes pour les mises à jour et le versionnement du module.
- **Table des hooks enregistrés** :

  | Nom du hook | Moment d'exécution | Objectif technique |
  | --- | --- | --- |
  | `displayOrderConfirmation` | Après qu'un client a terminé avec succès une commande et atteint la page de confirmation. | Injecte le script du pixel Commerce Connector dans la page pour suivre l'achat terminé. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et toute assistance supplémentaire concernant le module « Pixel Commerce Connector », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
