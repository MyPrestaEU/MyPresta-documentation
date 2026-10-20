---
title: "In den Warenkorb nur für angemeldete Benutzer - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „In den Warenkorb nur für angemeldete Benutzer“ von MyPresta.eu."
sidebar:
  label: "In den Warenkorb nur für angemeldete Benutzer - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Add to cart for logged only auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/add-to-cart-for-logged-only.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/add-to-cart-for-logged-only/)
>
> ---


# In den Warenkorb nur für angemeldete Benutzer

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Modul „In den Warenkorb nur für angemeldete Benutzer“, um auf dessen Einstellungen zuzugreifen.

#### **Anzeigen**

- **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Kernfunktionalität des Moduls.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (Ja):* Das Modul ist aktiv. Nicht angemeldete Benutzer werden daran gehindert, Produkte in ihren Warenkorb zu legen, und es wird eine Meldung angezeigt, die sie zur Anmeldung auffordert.
  - *Wenn deaktiviert (Nein):* Das Modul ist inaktiv. Alle Benutzer, ob angemeldet oder nicht, können Produkte gemäß dem Standard-PrestaShop-Verhalten in ihren Warenkorb legen.
- **Empfohlener Wert:** **Ja**, wenn Sie die „nur für angemeldete Benutzer“-Warenkorbregel durchsetzen möchten. **Nein**, wenn Sie die Funktion vorübergehend deaktivieren möchten, ohne das Modul zu deinstallieren.
- **Händlerszenario / Beispiel:** Wenn Sie einen B2B-Shop betreiben und nur Ihre registrierten Geschäftskunden Bestellungen aufgeben lassen möchten, würden Sie dies auf „Ja“ setzen. Wenn Sie Ihren Shop vorübergehend für öffentliches Browsen und Warenkorb-Ergänzungen für eine spezielle Aktion öffnen, könnten Sie dies für diesen Zeitraum auf „Nein“ setzen.

#### **Konfigurations-Schnellreferenztabelle**

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Anzeigen | Ja | Aktiviert/deaktiviert die Kernfunktionalität des Moduls, die das Hinzufügen zum Warenkorb auf angemeldete Benutzer beschränkt. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul aktiviert, aber nicht angemeldete Benutzer können immer noch Produkte in den Warenkorb legen. Was ist falsch?**
A:

1. **Cache leeren:** Das häufigste Problem ist das Caching. Gehen Sie im PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
2. **Modulposition:** Stellen Sie sicher, dass das Modul korrekt eingehängt ist. Obwohl das Modul dies automatisch handhabt, können manchmal Theme-Konflikte stören. Überprüfen Sie die Konfiguration des Moduls und stellen Sie sicher, dass es aktiv ist.
3. **Theme-Kompatibilität:** Sehr selten kann ein stark angepasstes Theme das Standardverhalten der PrestaShop-Schaltflächen überschreiben. Wenn das Leeren des Caches nicht funktioniert, wechseln Sie vorübergehend zum Standard-PrestaShop-Theme (z. B. Classic), um zu sehen, ob das Problem weiterhin besteht. Wenn es sich löst, verursacht Ihr Theme wahrscheinlich einen Konflikt, und Sie müssen möglicherweise einen Entwickler hinzuziehen.

**F: Kann ich die Meldung für nicht angemeldete Benutzer anpassen?**
A: Ja, die Meldung ist in der Regel übersetzbar. Gehen Sie im Back Office zu **International > Übersetzungen**. Wählen Sie „Übersetzungen der installierten Module“, wählen Sie Ihr Theme und dann „In den Warenkorb nur für angemeldete Benutzer“. Dort sollten Sie den Textstring finden, den Sie für jede Sprache ändern können.

**F: Beeinflusst dieses Modul meine SEO?**
A: Nein, dieses Modul beeinflusst hauptsächlich die Funktionalität der Schaltfläche „In den Warenkorb“ für Front-End-Benutzer. Es blockiert Suchmaschinen-Crawler nicht daran, Ihre Produktseiten oder Inhalte zu indizieren. Ihre Produkte bleiben sichtbar und auffindbar.

**F: Was passiert, wenn sich ein Kunde abmeldet, nachdem er Artikel in den Warenkorb gelegt hat?**
A: Das Modul verhindert das *Hinzufügen* zum Warenkorb, wenn der Benutzer nicht angemeldet ist. Wenn sich ein Kunde anmeldet, Artikel hinzufügt und sich dann abmeldet, bleiben die Artikel in der Regel in seinem Warenkorb (seinem Konto zugeordnet) für den Fall, dass er sich wieder anmeldet. Die Einschränkung des Moduls gilt für die Aktion des Hinzufügens neuer Artikel, während man nicht angemeldet ist.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick über das Modul „In den Warenkorb nur für angemeldete Benutzer“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul „In den Warenkorb nur für angemeldete Benutzer“ ist ein leichtgewichtiges PrestaShop-Modul, das hauptsächlich dazu dient, das Verhalten der „In den Warenkorb“-Aktion basierend auf dem Anmeldestatus des Benutzers abzufangen und zu ändern. Dies wird erreicht, indem das Hook-System von PrestaShop genutzt und JavaScript injiziert wird, um die Schaltfläche „In den Warenkorb“ zu deaktivieren oder zu ändern und eine Meldung für nicht angemeldete Benutzer anzuzeigen. Es führt keine neuen Datenbanktabellen oder komplexen Objektmodelle ein, sondern konzentriert sich stattdessen auf die Front-End-Interaktion und bestehende PrestaShop-Kernfunktionen.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird innerhalb der `getContent()`-Methode der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt keine benutzerdefinierten Klassen ein oder erweitert `ObjectModel`. Seine Logik ist hauptsächlich in der Hauptdatei `cartforlogged.php` enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

- **`cartforlogged/views/js/cfl-17500.js`**

  - **Umfang:** Front-Office.
  - **Zweck:** Dieses Skript ist wahrscheinlich für PrestaShop 1.7.x und 8.x Versionen konzipiert (angezeigt durch `17500`). Es zielt auf die Schaltfläche „In den Warenkorb“ (`#add_to_cart button`, `.add-to-cart`) und möglicherweise andere Elemente wie Mengeneingaben ab.
  - **Funktionalität:**
    - Überprüft, ob der Benutzer angemeldet ist (`isLogged`).
    - Wenn nicht angemeldet, deaktiviert es die Schaltfläche „In den Warenkorb“, ändert ihren Text (z. B. in „Nur angemeldete Benutzer…“) und fügt möglicherweise eine CSS-Klasse hinzu, um sie visuell als deaktiviert zu kennzeichnen.
    - Es könnte auch die Formularübermittlung oder AJAX-Aufrufe im Zusammenhang mit dem Hinzufügen von Produkten zum Warenkorb verhindern.
    - Es verwendet wahrscheinlich `prestashop.on('updateCart', ...)` oder ähnliche Event-Listener, um seine Logik nach Warenkorb-Updates oder Seitenänderungen (z. B. wenn Produktattribute geändert werden) erneut anzuwenden.
- **`cartforlogged/views/js/cfl.js`**

  - **Umfang:** Front-Office.
  - **Zweck:** Dieses Skript ist wahrscheinlich eine allgemeinere oder Fallback-Version, möglicherweise für ältere PrestaShop-Versionen (1.5.x, 1.6.x) oder als Basis für das spezifischere `cfl-17500.js`.
  - **Funktionalität:** Ähnlich wie `cfl-17500.js` identifiziert es die Schaltfläche „In den Warenkorb“ (z. B. `#add_to_cart button`, `.exclusive button`), überprüft den Anmeldestatus und deaktiviert die Schaltfläche für nicht angemeldete Benutzer. Es könnte jQuerys `$(document).ready()` und Event-Delegation verwenden, um dynamische Inhalte zu verarbeiten.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`cartforlogged/views/css/cfl.css`**
  - **Umfang:** Front-Office Kunden-Styling.
  - **Zweck:** Bietet grundlegendes Styling für die deaktivierte Schaltfläche „In den Warenkorb“ oder die Meldung, die nicht angemeldeten Benutzern angezeigt wird.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:**
    - `.cfl_disabled_button`: Wird wahrscheinlich auf die Schaltfläche „In den Warenkorb“ angewendet, wenn sie vom Modul deaktiviert wird. Entwickler können dies verwenden, um Hintergrundfarbe, Cursor, Deckkraft usw. zu ändern, um deutlich anzuzeigen, dass sie inaktiv ist.
    - `.cfl_message`: Wenn das Modul ein bestimmtes Nachrichtenelement injiziert, würde diese Klasse es stylen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`cartforlogged/views/templates/admin/json.tpl`**
  - **Umfang:** Admin-Templates.
  - **Zweck:** Dieses Template wird wahrscheinlich intern von der `getContent()`-Methode des Moduls verwendet, um JSON-Daten auszugeben, möglicherweise für AJAX-Anfragen innerhalb der Konfigurationsseite oder für dynamische Inhaltsaktualisierungen. Es ist kein im Front-Office sichtbares Template. Es könnte verwendet werden, um den Konfigurationsstatus oder andere Daten an das JavaScript auf der Admin-Seite zurückzugeben.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfigurationseinstellungen (z. B. `CFL_LOGIN`) in der Standardtabelle `ps_configuration`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Wird verwendet, um CSS- und JavaScript-Assets (`cfl.css`, `cfl.js`, `cfl-17500.js`) einzubinden, die das Verhalten der Schaltfläche „In den Warenkorb“ ändern. |
| `actionCartSave` | Nachdem ein Warenkorb gespeichert oder aktualisiert wurde. | Dieser Hook könnte potenziell verwendet werden, um Warenkorbinhalte neu zu bewerten oder Einschränkungen anzuwenden, aber angesichts der Modulbeschreibung ist seine Hauptfunktion wahrscheinlich die Front-End-JS-Injektion über `displayHeader`. Es könnte ein Fallback oder eine Möglichkeit sein, die serverseitige Validierung sicherzustellen, obwohl die Modulbeschreibung den Client-Side-Aspekt betont. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller geladen wird und seine Medien (JS/CSS) gesetzt werden. | Wird verwendet, um alle notwendigen JavaScript oder CSS für die Back-Office-Konfigurationsseite des Moduls einzubinden. |
| `header` | Ähnlich wie `displayHeader`, oft austauschbar oder für spezifische ältere Themes verwendet. | Wird verwendet, um CSS- und JavaScript-Assets einzubinden, um die Kompatibilität über verschiedene PrestaShop-Versionen und Themes hinweg zu gewährleisten. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „In den Warenkorb nur für angemeldete Benutzer“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
