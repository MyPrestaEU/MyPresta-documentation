---
title: "Facebook Login Connect - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Facebook Login Connect von MyPresta.eu."
sidebar:
  label: "Facebook Login Connect - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Facebook Login Connect auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/facebook-login-connect.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/facebook-login-connect/)
>
> ---


# Facebook Login Connect

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für die Kommunikation mit der Facebook-API erforderlich. Diese sind fast immer auf jedem modernen Webhosting verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie einstellen, wie sich der Facebook-Login-Button verhält und wo er erscheint.

#### Allgemeine Einstellungen

- **Facebook Application ID (App ID):**
  - **Was diese Einstellung bewirkt:** Dies ist eine eindeutige Kennung, die von Facebook für Ihre spezifische Anwendung bereitgestellt wird. Sie ist entscheidend für die Kommunikation Ihres Stores mit dem Facebook-Login-System.
  - **Auswirkung einer Änderung dieser Einstellung:** Ohne eine gültige App ID funktioniert der Facebook-Login-Button nicht, da Ihr Store sich nicht bei Facebook authentifizieren kann.
  - **Empfohlener Wert:** Die App ID, die Sie von Ihrem Facebook-Entwicklerkonto erhalten. Dieses Feld darf nicht leer sein.
  - **Händlerszenario / Beispiel:** Sie müssen eine Facebook-App unter [developers.facebook.com](https://developers.facebook.com/) erstellen, um diese ID zu erhalten. Befolgen Sie die Anweisungen von Facebook, um eine grundlegende App einzurichten und Facebook Login zu aktivieren.
- **Standard-Kundengruppe für neue Konten:**
  - **Was diese Einstellung bewirkt:** Wenn ein neuer Kunde sich über Facebook registriert, wird er automatisch dieser Kundengruppe zugewiesen.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn auf „Kunde“ (Standard) eingestellt:* Neue Facebook-Benutzer werden zu regulären Kunden, die den Standardpreisen und Rabatten Ihres Stores unterliegen.
    - *Wenn auf eine benutzerdefinierte Gruppe (z. B. „Großhandel“) eingestellt:* Neue Facebook-Benutzer könnten sofort auf spezielle Preise oder Inhalte zugreifen, wenn diese Gruppe spezifische Regeln hat.
  - **Empfohlener Wert:** `Kunde` (oder Ihre Standard-Kundengruppe für neue Registrierungen).
  - **Händlerszenario / Beispiel:** Wenn Sie eine „VIP“-Kundengruppe mit speziellen Rabatten haben, könnten Sie in Betracht ziehen, neue Facebook-Benutzer zuerst einer Standard-„Kunden“-Gruppe zuzuweisen und sie dann manuell hochzustufen, wenn sie die VIP-Kriterien erfüllen.
- **Willkommens-E-Mail an neue Kunden senden:**
  - **Was diese Einstellung bewirkt:** Steuert, ob PrestaShop seine Standard-Willkommens-E-Mail an Kunden sendet, die sich über Facebook registrieren.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Neue Facebook-Benutzer erhalten eine E-Mail, die ihre Kontoerstellung bestätigt.
    - *Wenn deaktiviert (Nein):* Es wird keine Willkommens-E-Mail gesendet.
  - **Empfohlener Wert:** `Ja`. Es ist gute Praxis, neue Kunden willkommen zu heißen und ihnen ihre Anmeldedaten zur Verfügung zu stellen (auch wenn sie Facebook verwenden, möchten sie vielleicht später ein Passwort festlegen).
  - **Händlerszenario / Beispiel:** Wenn diese Option aktiviert bleibt, fühlen sich neue Kunden willkommen und haben eine Aufzeichnung ihres Kontos, auch wenn sie sich nicht sofort ein Passwort merken müssen.
- **In-App-Browser-Login aktivieren (für mobile Apps):**
  - **Was diese Einstellung bewirkt:** Diese Einstellung ist hauptsächlich für Stores, die über eine dedizierte mobile App (nicht nur einen mobilen Browser) aufgerufen werden. Sie optimiert den Facebook-Login-Flow für In-App-Browser.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Verbessert das Login-Erlebnis für Benutzer, die über eine WebView innerhalb einer mobilen App auf Ihren Store zugreifen.
    - *Wenn deaktiviert:* Es wird der Standard-Browser-Login-Flow verwendet, der in einer dedizierten App weniger nahtlos sein könnte.
  - **Empfohlener Wert:** `Nein`, es sei denn, Sie haben eine spezifische mobile Anwendung, die Ihren PrestaShop-Store einbettet.
  - **Händlerszenario / Beispiel:** Wenn Sie eine native iOS- oder Android-App entwickelt haben, die den Inhalt Ihres PrestaShop-Stores anzeigt, könnte die Aktivierung dieser Option für ein reibungsloses Facebook-Login-Erlebnis innerhalb dieser App erforderlich sein.
- **Facebook-Login im Pop-up-Fenster anzeigen:**
  - **Was diese Einstellung bewirkt:** Wenn Ihr Theme ein Pop-up-Fenster für die Anmeldung verwendet, ermöglicht diese Option, dass der Facebook-Login-Button in diesem Pop-up erscheint.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Facebook-Login-Button ist innerhalb des Login-Pop-ups Ihres Themes verfügbar.
    - *Wenn deaktiviert:* Der Button erscheint nur auf Standard-Login-Seiten oder anderen Hook-Positionen.
  - **Empfohlener Wert:** `Ja`, wenn Ihr Theme ein Login-Pop-up verwendet.
  - **Händlerszenario / Beispiel:** Viele moderne Themes verwenden ein schnelles Login-Pop-up, das über den Header zugänglich ist. Die Aktivierung dieser Option macht die Facebook-Login-Option dort sofort sichtbar.
- **Sprache des Facebook-Login-Buttons:**
  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, die Sprache für den Facebook-Login-Button und verwandte Nachrichten festzulegen.
  - **Auswirkung einer Änderung dieser Einstellung:** Der Button-Text und alle von Facebook generierten Aufforderungen erscheinen in der ausgewählten Sprache.
  - **Empfohlener Wert:** `Standard PrestaShop Sprache` (passend zur Hauptsprache Ihres Stores) oder `Automatisch erkennen`, falls verfügbar.
  - **Händlerszenario / Beispiel:** Wenn Ihr Store in mehreren Sprachen betrieben wird, möchten Sie dies möglicherweise so einstellen, dass es der aktuellen Front-Office-Sprache entspricht, um ein konsistentes Benutzererlebnis zu gewährleisten.
- **Facebook erlauben, Benutzer zu identifizieren (Erweitert):**
  - **Was diese Einstellung bewirkt:** Dies ist eine erweiterte Einstellung im Zusammenhang mit der Identitätsverfolgung von Facebook. Sie ermöglicht es Facebook, Benutzer auf Ihrer Website potenziell für Werbezwecke zu verfolgen.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kann mehr Daten für Facebook-Werbung liefern, könnte aber je nach lokalen Vorschriften (z. B. DSGVO) Auswirkungen auf den Datenschutz haben.
    - *Wenn deaktiviert:* Begrenzt die Fähigkeit von Facebook, Benutzer auf Ihrer Website zu verfolgen.
  - **Empfohlener Wert:** `Nein`, es sei denn, Sie haben eine spezifische Marketingstrategie, die dies erfordert, und haben die Einhaltung des Datenschutzes berücksichtigt.
  - **Händlerszenario / Beispiel:** Konsultieren Sie Ihr Marketingteam und Ihre Rechtsabteilung, bevor Sie dies aktivieren, insbesondere wenn Sie in Regionen mit strengen Datenschutzgesetzen tätig sind.

#### Anzeigeoptionen (Wo der Facebook-Login-Button angezeigt werden soll)

Diese Einstellungen steuern, in welchen spezifischen Bereichen (Hooks) Ihres PrestaShop-Stores der Facebook-Login-Button angezeigt wird. Sie können jeden Hook einzeln aktivieren oder deaktivieren.

- **Im oberen Bereich anzeigen (fbl\_displayTop):**
  - **Was diese Einstellung bewirkt:** Zeigt den Button im obersten Bereich Ihres Stores an, oft in der Nähe der Suchleiste oder des Logos.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* Button erscheint im Header.
    - *Deaktiviert:* Button ist im Header ausgeblendet.
  - **Empfohlener Wert:** `Ja`, für hohe Sichtbarkeit.
- **In der oberen Spalte anzeigen (fbl\_displaytopColumn):**
  - **Was diese Einstellung bewirkt:** Zeigt den Button im Hauptinhaltsbereich an, normalerweise über den Hauptproduktlisten oder Inhalten auf der Startseite.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* Button erscheint im oberen Inhaltsbereich.
    - *Deaktiviert:* Button ist in diesem Bereich ausgeblendet.
  - **Empfohlener Wert:** `Nein`, es sei denn, Sie möchten einen sehr prominenten Button auf der Startseite.
- **Auf der Startseite anzeigen (fbl\_displayHome):**
  - **Was diese Einstellung bewirkt:** Zeigt den Button speziell auf der Startseite Ihres Stores an.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* Button erscheint auf der Startseite.
    - *Deaktiviert:* Button ist auf der Startseite ausgeblendet.
  - **Empfohlener Wert:** `Ja`, um eine sofortige Registrierung zu fördern.
- **In der Navigation anzeigen (fbl\_displayNav):**
  - **Was diese Einstellung bewirkt:** Zeigt den Button in der Hauptnavigationsleiste an, oft neben den Links „Mein Konto“ oder „Kontakt“.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* Button erscheint in der Navigation.
    - *Deaktiviert:* Button ist in der Navigation ausgeblendet.
  - **Empfohlener Wert:** `Ja`, für einfachen Zugriff von jeder Seite.
- **In Navigation 1 anzeigen (fbl\_displayNav1):**
  - **Was diese Einstellung bewirkt:** Ähnlich wie `displayNav`, zielt aber auf einen spezifischen Navigations-Hook ab, den einige Themes verwenden (oft für die oberste Leiste).
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* Button erscheint im ersten Navigationsbereich.
    - *Deaktiviert:* Button ist in diesem Bereich ausgeblendet.
  - **Empfohlener Wert:** `Ja`, wenn Ihr Theme diesen Hook verwendet und Sie den Button dort haben möchten.
- **In Navigation 2 anzeigen (fbl\_displayNav2):**
  - **Was diese Einstellung bewirkt:** Ähnlich wie `displayNav`, zielt aber auf einen zweiten Navigations-Hook ab, den einige Themes verwenden (oft für die Hauptnavigationsleiste).
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* Button erscheint im zweiten Navigationsbereich.
    - *Deaktiviert:* Button ist in diesem Bereich ausgeblendet.
  - **Empfohlener Wert:** `Ja`, wenn Ihr Theme diesen Hook verwendet und Sie den Button dort haben möchten.
- **Im Warenkorb anzeigen (fbl\_displayShoppingCart):**
  - **Was diese Einstellung bewirkt:** Zeigt den Button auf der Warenkorb-Übersichtsseite an.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* Button erscheint auf der Warenkorbseite, ermöglicht schnelles Login vor dem Checkout.
    - *Deaktiviert:* Button ist auf der Warenkorbseite ausgeblendet.
  - **Empfohlener Wert:** `Ja`, um den Checkout für wiederkehrende Kunden zu vereinfachen.
- **Nach dem Kunden-Login-Formular anzeigen (fbl\_displayCustomerLoginFormAfter):**
  - **Was diese Einstellung bewirkt:** Zeigt den Button direkt unter dem Standard-PrestaShop-Login-Formular an.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* Button erscheint als alternative Anmeldemethode auf der Login-Seite.
    - *Deaktiviert:* Button ist in diesem Bereich ausgeblendet.
  - **Empfohlener Wert:** `Ja`, dies ist ein erstklassiger Ort für alternative Login-Optionen.
- **Im oberen Bereich der persönlichen Informationen anzeigen (fbl\_displayPersonalInformationTop):**
  - **Was diese Einstellung bewirkt:** Zeigt den Button oben im Abschnitt „Persönliche Informationen“ während der Kontoerstellung oder -bearbeitung an.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* Button erscheint auf der Seite mit den persönlichen Informationen.
    - *Deaktiviert:* Button ist in diesem Bereich ausgeblendet.
  - **Empfohlener Wert:** `Ja`, um Facebook-Login als Alternative zum Ausfüllen des Formulars anzubieten.
- **Im Warenkorb Extra anzeigen (fbl\_displayShoppingCartExtra):**
  - **Was diese Einstellung bewirkt:** Zeigt den Button in einem zusätzlichen Bereich auf der Warenkorbseite an, der oft für zusätzliche Module oder Informationen verwendet wird.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* Button erscheint im zusätzlichen Warenkorbbereich.
    - *Deaktiviert:* Button ist in diesem Bereich ausgeblendet.
  - **Empfohlener Wert:** `Nein`, es sei denn, Ihr Theme verwendet diesen Hook speziell für Login-Optionen.
- **In der linken Spalte anzeigen (fbl\_displayLeftColumn):**
  - **Was diese Einstellung bewirkt:** Zeigt den Button in der linken Seitenleiste Ihres Stores an (falls Ihr Theme eine hat).
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* Button erscheint in der linken Spalte.
    - *Deaktiviert:* Button ist in der linken Spalte ausgeblendet.
  - **Empfohlener Wert:** `Nein`, es sei denn, Sie möchten ihn prominent in der Seitenleiste anzeigen.
- **In der rechten Spalte anzeigen (fbl\_displayRightColumn):**
  - **Was diese Einstellung bewirkt:** Zeigt den Button in der rechten Seitenleiste Ihres Stores an (falls Ihr Theme eine hat).
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* Button erscheint in der rechten Spalte.
    - *Deaktiviert:* Button ist in der rechten Spalte ausgeblendet.
  - **Empfohlener Wert:** `Nein`, es sei denn, Sie möchten ihn prominent in der Seitenleiste anzeigen.
- **Im Kontoerstellungsformular anzeigen (fbl\_displayCreateAccountForm):**
  - **Was diese Einstellung bewirkt:** Zeigt den Button direkt im Standard-PrestaShop-Kontoerstellungsformular an.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* Button erscheint als alternative Registrierungsmethode auf der Kontoerstellungsseite.
    - *Deaktiviert:* Button ist in diesem Bereich ausgeblendet.
  - **Empfohlener Wert:** `Ja`, dies ist ein entscheidender Ort, um die Registrierung zu vereinfachen.
- **Im oberen Bereich der Kontoerstellung anzeigen (fbl\_displayCreateAccountTop):**
  - **Was diese Einstellung bewirkt:** Zeigt den Button ganz oben auf der Kontoerstellungsseite an, über den Formularfeldern.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* Button erscheint oben auf der Kontoerstellungsseite.
    - *Deaktiviert:* Button ist in diesem Bereich ausgeblendet.
  - **Empfohlener Wert:** `Ja`, für maximale Sichtbarkeit auf der Registrierungsseite.
- **Im Footer anzeigen (fbl\_displayFooter):**
  - **Was diese Einstellung bewirkt:** Zeigt den Button im Footer-Bereich Ihres Stores an.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* Button erscheint im Footer.
    - *Deaktiviert:* Button ist im Footer ausgeblendet.
  - **Empfohlener Wert:** `Nein`, im Allgemeinen kein primärer Ort für Login-Buttons.
- **Im Header anzeigen (fbl\_displayHeader):**
  - **Was diese Einstellung bewirkt:** Zeigt den Button im Header-Bereich Ihres Stores an. Dies ist eine sehr häufige und effektive Platzierung.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* Button erscheint im Header.
    - *Deaktiviert:* Button ist im Header ausgeblendet.
  - **Empfohlener Wert:** `Ja`, für hohe Sichtbarkeit auf allen Seiten.
- **In Dashboard Zone Eins anzeigen (fbl\_displayDashboardZoneOne):**
  - **Was diese Einstellung bewirkt:** Dieser Hook dient typischerweise zur Anzeige von Inhalten auf dem Kunden-Account-Dashboard.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* Button erscheint auf dem Kunden-Dashboard.
    - *Deaktiviert:* Button ist in diesem Bereich ausgeblendet.
  - **Empfohlener Wert:** `Nein`, da Kunden bereits angemeldet sind, wenn sie ihr Dashboard sehen.
- **Im Pop-up-Login anzeigen (fbl\_popuplogin):**
  - **Was diese Einstellung bewirkt:** Zielt speziell auf Themes ab, die ein Pop-up-Modal für die Anmeldung verwenden.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* Button erscheint innerhalb des Login-Pop-ups.
    - *Deaktiviert:* Button ist im Login-Pop-up ausgeblendet.
  - **Empfohlener Wert:** `Ja`, wenn Ihr Theme ein Login-Pop-up verwendet.
- **Facebook-Login anzeigen (fbl\_fblogin):**
  - **Was diese Einstellung bewirkt:** Dies ist ein generischer Hook für den Facebook-Login-Button. Er kann intern vom Modul oder von Themes für eine benutzerdefinierte Platzierung verwendet werden.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* Button erscheint in diesem generischen Hook.
    - *Deaktiviert:* Button ist in diesem Hook ausgeblendet.
  - **Empfohlener Wert:** `Ja`, wenn andere spezifische Hooks nicht funktionieren oder wenn Sie einen Fallback wünschen.

#### Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Facebook Application ID (App ID) | *Ihre Facebook App ID* | Wesentlich für die Verbindung zu Facebook; Button funktioniert ohne sie nicht. |
| Modulkonfiguration | Standard-Kundengruppe für neue Konten | Kunde | Weist neuen Facebook-Benutzern eine spezifische Kundengruppe zu. |
| Modulkonfiguration | Willkommens-E-Mail an neue Kunden senden | Ja | Bestimmt, ob neue Facebook-Registrierungen eine Willkommens-E-Mail erhalten. |
| Modulkonfiguration | In-App-Browser-Login aktivieren | Nein | Optimiert den Login für dedizierte mobile Apps (nicht mobile Browser). |
| Modulkonfiguration | Facebook-Login im Pop-up-Fenster anzeigen | Ja (wenn Theme Pop-up verwendet) | Zeigt den Button im Login-Pop-up des Themes an. |
| Modulkonfiguration | Sprache des Facebook-Login-Buttons | Standard PrestaShop Sprache | Legt die Sprache für den Facebook-Button und die Aufforderungen fest. |
| Modulkonfiguration | Facebook erlauben, Benutzer zu identifizieren | Nein | Erweiterte Tracking-Option; Rechts-/Marketingberatung einholen. |
| Modulkonfiguration | Im oberen Bereich anzeigen (fbl\_displayTop) | Ja | Zeigt den Button im Header an. |
| Modulkonfiguration | In der oberen Spalte anzeigen (fbl\_displaytopColumn) | Nein | Zeigt den Button im Hauptinhaltsbereich an, normalerweise über den Listen. |
| Modulkonfiguration | Auf der Startseite anzeigen (fbl\_displayHome) | Ja | Zeigt den Button speziell auf der Startseite an. |
| Modulkonfiguration | In der Navigation anzeigen (fbl\_displayNav) | Ja | Zeigt den Button in der Hauptnavigationsleiste an. |
| Modulkonfiguration | In Navigation 1 anzeigen (fbl\_displayNav1) | Ja (wenn Theme verwendet) | Zeigt den Button in einem spezifischen oberen Navigationsbereich an. |
| Modulkonfiguration | In Navigation 2 anzeigen (fbl\_displayNav2) | Ja (wenn Theme verwendet) | Zeigt den Button in einem spezifischen Hauptnavigationsbereich an. |
| Modulkonfiguration | Im Warenkorb anzeigen (fbl\_displayShoppingCart) | Ja | Zeigt den Button auf der Warenkorb-Übersichtsseite an. |
| Modulkonfiguration | Nach dem Kunden-Login-Formular anzeigen | Ja | Zeigt den Button unter dem Standard-Login-Formular an. |
| Modulkonfiguration | Im oberen Bereich der persönlichen Informationen anzeigen | Ja | Zeigt den Button oben auf der Seite mit den persönlichen Informationen an. |
| Modulkonfiguration | Im Warenkorb Extra anzeigen | Nein | Zeigt den Button in einem zusätzlichen Warenkorbbereich an. |
| Modulkonfiguration | In der linken Spalte anzeigen (fbl\_displayLeftColumn) | Nein | Zeigt den Button in der linken Seitenleiste an. |
| Modulkonfiguration | In der rechten Spalte anzeigen (fbl\_displayRightColumn) | Nein | Zeigt den Button in der rechten Seitenleiste an. |
| Modulkonfiguration | Im Kontoerstellungsformular anzeigen | Ja | Zeigt den Button im Kontoerstellungsformular an. |
| Modulkonfiguration | Im oberen Bereich der Kontoerstellung anzeigen | Ja | Zeigt den Button oben auf der Kontoerstellungsseite an. |
| Modulkonfiguration | Im Footer anzeigen (fbl\_displayFooter) | Nein | Zeigt den Button im Footer an. |
| Modulkonfiguration | Im Header anzeigen (fbl\_displayHeader) | Ja | Zeigt den Button im Header-Bereich an. |
| Modulkonfiguration | In Dashboard Zone Eins anzeigen | Nein | Zeigt den Button auf dem Kunden-Account-Dashboard an. |
| Modulkonfiguration | Im Pop-up-Login anzeigen (fbl\_popuplogin) | Ja (wenn Theme Pop-up verwendet) | Zeigt den Button im Login-Pop-up-Modal an. |
| Modulkonfiguration | Facebook-Login anzeigen (fbl\_fblogin) | Ja | Generischer Hook für den Facebook-Login-Button. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Der Facebook-Login-Button erscheint, aber nichts passiert, wenn ich darauf klicke, oder es wird ein Fehler angezeigt.**
A1: Dies deutet fast immer auf ein Problem mit Ihrer Facebook App ID oder der Facebook App-Konfiguration selbst hin.
- **Überprüfen Sie Ihre Facebook App ID:** Gehen Sie in Ihrer Modulkonfiguration in PrestaShop und vergewissern Sie sich, dass die „Facebook Application ID“ korrekt eingegeben ist.
- **Überprüfen Sie Ihre Facebook App-Einstellungen:** Melden Sie sich bei [developers.facebook.com](https://developers.facebook.com/) an.
- Stellen Sie sicher, dass Ihre App „Live“ ist (nicht im Entwicklungsmodus).
- Gehen Sie zu „Facebook Login“ > „Einstellungen“ und stellen Sie sicher, dass „Client OAuth Login“ und „Web OAuth Login“ aktiviert sind.
- Unter „Gültige OAuth-Umleitungs-URIs“ *müssen* Sie die vollständige Domain Ihres Stores hinzufügen (z. B. `https://www.ihrshop.com/`). Manchmal müssen Sie auch `https://www.ihrshop.com/module/fblogin/index` oder `https://www.ihrshop.com/module/fblogin/loginloader` hinzufügen, abhängig von Ihrer PrestaShop-Version und URL-Struktur.
- Stellen Sie sicher, dass Ihre „Datenschutzrichtlinien-URL“ und „Nutzungsbedingungen-URL“ in den „Grundeinstellungen“ Ihrer Facebook App festgelegt sind.
- **Cache leeren:** Leeren Sie nach jeder Änderung Ihren PrestaShop-Cache (Erweiterte Einstellungen > Leistung > Cache leeren).

**F2: Neue Kunden registrieren sich über Facebook, aber ihre Namen oder E-Mails werden nicht korrekt angezeigt.**
A2: Das Modul zieht öffentliche Profilinformationen von Facebook.
- Stellen Sie sicher, dass der Kunde Ihrer App die Berechtigung erteilt hat, auf sein grundlegendes Profil und seine E-Mail zuzugreifen.
- Die Facebook-API liefert den Vornamen, Nachnamen und die E-Mail-Adresse. Wenn diese fehlen oder falsch sind, liegt dies normalerweise an den Datenschutzeinstellungen des Kunden auf Facebook oder einem seltenen API-Fehler.
- Das Modul erstellt ein neues Konto, wenn keine passende E-Mail gefunden wird. Wenn eine E-Mail bereits in Ihrer PrestaShop-Datenbank existiert, sollte das Modul versuchen, den Benutzer in dieses bestehende Konto einzuloggen.

**F3: Der Facebook-Button erscheint nicht an der erwarteten Stelle, selbst nachdem ich den Hook aktiviert habe.**
A3:
- **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache (Erweiterte Einstellungen > Leistung > Cache leeren), nachdem Sie Hook-Einstellungen geändert haben.
- **Theme-Kompatibilität:** Einige benutzerdefinierte Themes könnten Standard-PrestaShop-Hooks überschreiben oder einzigartige Strukturen haben. Wenn der Button nicht erscheint, zeigt Ihr Theme diesen spezifischen Hook möglicherweise nicht aktiv an. Möglicherweise müssen Sie Ihren Theme-Entwickler oder einen Webmaster konsultieren, um ihn manuell in die `.tpl`-Dateien Ihres Themes zu integrieren.
- **Modulpositionen überprüfen:** Gehen Sie zu Design > Positionen (oder Module > Positionen in älteren Versionen) und suchen Sie nach `fblogin`. Stellen Sie sicher, dass das Modul an den gewünschten Positionen „gehookt“ ist. Wenn nicht, können Sie ein Modul manuell an den richtigen Hook „transplantieren“.

**F4: Können Kunden, die sich mit Facebook registriert haben, später ein Passwort festlegen, um sich direkt anzumelden?**
A4: Ja. Sobald ein Konto über Facebook erstellt wurde, ist es ein Standard-PrestaShop-Kundenkonto.
- Kunden können den Link „Passwort vergessen“ auf der Login-Seite Ihres Stores verwenden. Sie erhalten eine E-Mail, um ein neues Passwort festzulegen, wodurch sie sich direkt mit ihrer E-Mail und dem neuen Passwort anmelden können, auch ohne Facebook.

**F5: Unterstützt dieses Modul mehrere Sprachen für den Button?**
A5: Ja, das Modul verfügt über eine Einstellung für die „Sprache des Facebook-Login-Buttons“. Sie können sie so einstellen, dass sie der Standardsprache Ihres Stores entspricht, oder in einigen Fällen kann das Facebook SDK die Browsersprache des Benutzers automatisch erkennen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul `Facebook Login Connect` integriert das JavaScript SDK von Facebook, um die Benutzerauthentifizierung zu erleichtern. Es arbeitet hauptsächlich durch das Einhaken in verschiedene Front-Office-Anzeigepunkte, um den Facebook-Login-Button zu rendern. Nach einem erfolgreichen Facebook-Login verarbeitet ein Front-Controller den Callback, ruft Benutzerdaten von Facebook ab und meldet entweder einen bestehenden PrestaShop-Kunden an oder erstellt einen neuen. Anschließend leitet es den Benutzer zu seiner Kontoseite oder der Startseite weiter. Das Modul nutzt die `Module`-Klasse von PrestaShop für die Konfiguration und Hook-Verwaltung, mit minimalen benutzerdefinierten Klassen, wobei es sich stark auf die Hauptdatei `fblogin.php` für die Kernlogik verlässt.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/index.php`
    - **Klassenname:** `FbloginIndexModuleFrontController`
    - **Elternklasse:** `ModuleFrontController`
    - **Verantwortlichkeit:** Dieser Controller fungiert als primärer Callback-Endpunkt für den Authentifizierungsprozess von Facebook. Nachdem sich ein Benutzer erfolgreich über Facebook angemeldet hat, leitet Facebook zu diesem Controller um. Er verarbeitet den Abruf des Facebook-Zugriffstokens, ruft Benutzerprofildaten (Name, E-Mail) ab und meldet dann entweder einen bestehenden PrestaShop-Kunden an oder erstellt einen neuen. Anschließend leitet er den Benutzer zu seiner Kontoseite oder der Startseite weiter.
  - `controllers/front/loginloader.php`
    - **Klassenname:** `FbloginLoginloaderModuleFrontController`
    - **Elternklasse:** `ModuleFrontController`
    - **Verantwortlichkeit:** Dieser Controller ist wahrscheinlich ein Fallback oder ein alternativer Einstiegspunkt für den Facebook-Login-Prozess, der möglicherweise für spezifische Szenarien oder ältere PrestaShop-Versionen verwendet wird. Er würde ähnliche Authentifizierungs- und Benutzerverwaltungsaufgaben wie `index.php` ausführen.
- **Back-Office-Admin-Controller**:

  - Keine. Die gesamte Konfiguration wird innerhalb der `getContent()`-Methode der Hauptmoduldatei behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Keine. Das Modul definiert keine benutzerdefinierten `ObjectModel`-Klassen oder andere Kern-Business-Logik-Klassen im Verzeichnis `classes/`. Die gesamte Kernlogik ist in der `Fblogin`-Klasse in `fblogin.php` gekapselt.

### 4.4 JavaScript-Assets (`views/js/`)

- `views/js/fblogin4.js`
  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Dieses Skript ist für die Initialisierung des Facebook JavaScript SDK verantwortlich. Es lädt das SDK, richtet die `FB.init`-Konfiguration (einschließlich der App ID und der gewünschten Berechtigungen) ein und verarbeitet den `FB.login`-Aufruf, wenn der Facebook-Login-Button geklickt wird. Es lauscht wahrscheinlich auf das `auth.statusChange`-Ereignis, um Anmelde-/Abmeldezustände zu erkennen und leitet den Benutzer nach erfolgreicher Authentifizierung zum entsprechenden PrestaShop-Front-Controller (`index.php` oder `loginloader.php`) weiter. Es verwaltet auch die Anzeige des Facebook-Login-Buttons und seine Interaktion.

### 4.5 CSS-Stylesheets (`views/css/`)

- `css.css`
  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Dies ist wahrscheinlich ein generisches Stylesheet für das Modul, das grundlegende Stile für den Facebook-Login-Button und alle zugehörigen UI-Elemente bereitstellt.
- `views/css/fblogin.css`
  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Bietet spezifische Styling-Regeln für den Facebook-Login-Button und seinen Container, um ein konsistentes Erscheinungsbild über verschiedene Themes hinweg zu gewährleisten. Es könnte Stile für Button-Größe, Farbe, Hover-Effekte und Ausrichtung enthalten.
- `views/css/fblogin17.css`
  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Dieses Stylesheet enthält wahrscheinlich spezifische Überschreibungen oder zusätzliche Stile, die auf PrestaShop 1.7.x und neuere Versionen zugeschnitten sind, um potenzielle Layout- oder Styling-Unterschiede in neueren Theme-Strukturen zu berücksichtigen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - `createAccountForm.tpl`: Rendert den Facebook-Login-Button innerhalb des Standard-Kontoerstellungsformulars.
  - `createAccountTop.tpl`: Rendert den Facebook-Login-Button oben auf der Kontoerstellungsseite.
  - `dashboardZoneOne.tpl`: Rendert den Facebook-Login-Button in Zone Eins des Kunden-Dashboards (weniger üblich für den Login, aber verfügbar).
  - `displayCustomerLoginFormAfter.tpl`: Rendert den Facebook-Login-Button direkt nach dem Standard-Kunden-Login-Formular.
  - `displayNav.tpl`: Rendert den Facebook-Login-Button in der Hauptnavigationsleiste.
  - `displayPersonalInformationTop.tpl`: Rendert den Facebook-Login-Button oben auf der Seite mit den persönlichen Informationen.
  - `displayPopUpLogin.tpl`: Rendert den Facebook-Login-Button innerhalb eines Pop-up-Login-Modals des Themes.
  - `fblogin.tpl`: Ein generisches Template für den Facebook-Login-Button, das möglicherweise von `displayfblogin` oder als Fallback verwendet wird.
  - `footer.tpl`: Rendert den Facebook-Login-Button im Footer des Stores.
  - `header.tpl`: Rendert den Facebook-Login-Button im Header des Stores.
  - `home.tpl`: Rendert den Facebook-Login-Button auf der Startseite.
  - `leftcolumn.tpl`: Rendert den Facebook-Login-Button in der linken Seitenleiste.
  - `rightcolumn.tpl`: Rendert den Facebook-Login-Button in der rechten Seitenleiste.
  - `shoppingCart.tpl`: Rendert den Facebook-Login-Button auf der Warenkorbseite.
  - `shoppingCartExtra.tpl`: Rendert den Facebook-Login-Button in einem zusätzlichen Bereich der Warenkorbseite.
  - `top.tpl`: Rendert den Facebook-Login-Button im obersten Bereich des Stores.
  - `topColumn.tpl`: Rendert den Facebook-Login-Button im Hauptinhaltsbereich, typischerweise über den Produktlisten.
- **Admin-Templates (`views/templates/admin/`)**:

  - Keine. Die Modulkonfiguration wird direkt über `getContent()` in `fblogin.php` unter Verwendung von Standard-PrestaShop-Formularhelfern gerendert.
- **Front-Office-Templates (`views/templates/front/`)**:

  - Keine. Die gesamte Front-Office-Anzeige wird über Hook-Templates abgewickelt.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie `FBL_APPID`, `FBL_GROUPID`, `FBL_POPUP_LOGIN`, `FBL_DISPLAYTOP` usw. gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayRightColumn` | Rendert Inhalte in der rechten Seitenleiste. | Zeigt den Facebook-Login-Button in der rechten Spalte an. |
| `displaypopuplogin` | Rendert Inhalte innerhalb eines Login-Pop-ups des Themes. | Zeigt den Facebook-Login-Button im Login-Pop-up an. |
| `displayCreateAccountForm` | Rendert Inhalte innerhalb des Kundenkonto-Erstellungsformulars. | Zeigt den Facebook-Login-Button als alternative Registrierungsmethode an. |
| `displayPersonalInformationTop` | Rendert Inhalte oben auf der Seite mit den persönlichen Informationen. | Zeigt den Facebook-Login-Button für schnelle Registrierung/Login an. |
| `displayTop` | Rendert Inhalte im obersten Bereich des Stores. | Zeigt den Facebook-Login-Button in der oberen Leiste des Headers an. |
| `displayCreateAccountTop` | Rendert Inhalte oben auf der Kontoerstellungsseite. | Zeigt den Facebook-Login-Button über dem Registrierungsformular an. |
| `displayHeader` | Rendert Inhalte im `<head>`-Bereich des HTML und potenziell sichtbare Header-Elemente. | Fügt das Facebook SDK JavaScript ein und zeigt den Login-Button im Header an. |
| `displayNav` | Rendert Inhalte in der Hauptnavigationsleiste. | Zeigt den Facebook-Login-Button in der Navigation an. |
| `displayDashboardZoneOne` | Rendert Inhalte in der ersten Zone des Kunden-Dashboards. | Zeigt den Facebook-Login-Button an (weniger üblich für eingeloggte Benutzer). |
| `displayNav2` | Rendert Inhalte in einer sekundären Navigationsleiste (Theme-abhängig). | Zeigt den Facebook-Login-Button in der sekundären Navigation an. |
| `displayShoppingCart` | Rendert Inhalte auf der Warenkorb-Übersichtsseite. | Zeigt den Facebook-Login-Button für schnelles Login vor dem Checkout an. |
| `displayTopColumn` | Rendert Inhalte im Hauptinhaltsbereich, typischerweise über den Listen. | Zeigt den Facebook-Login-Button in der oberen Inhaltsspalte an. |
| `displayFooter` | Rendert Inhalte im Footer des Stores. | Zeigt den Facebook-Login-Button im Footer an. |
| `displayfblogin` | Ein vom Modul selbst definierter benutzerdefinierter Hook. | Bietet einen flexiblen Punkt für Themes zur Integration des Facebook-Login-Buttons. |
| `displayHome` | Rendert Inhalte auf der Startseite des Stores. | Zeigt den Facebook-Login-Button auf der Startseite an. |
| `displayLeftColumn` | Rendert Inhalte in der linken Seitenleiste. | Zeigt den Facebook-Login-Button in der linken Spalte an. |
| `displayCustomerLoginFormAfter` | Rendert Inhalte direkt nach dem Standard-Kunden-Login-Formular. | Zeigt den Facebook-Login-Button als alternative Anmeldemethode an. |
| `displayShoppingCartExtra` | Rendert Inhalte in einem zusätzlichen Bereich der Warenkorbseite. | Zeigt den Facebook-Login-Button in einem zusätzlichen Warenkorbbereich an. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum Modul „Facebook Login Connect“ zur Verfügung.
