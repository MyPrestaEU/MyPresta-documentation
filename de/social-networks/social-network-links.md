---
title: "Social Network Links - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Social Network Links von MyPresta.eu."
sidebar:
  label: "Social Network Links - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Social Network Links auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/social-network-links.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/social-network-links/)
>
> ---


# Social Network Links

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend und auf den meisten Webhosting-Umgebungen vorinstalliert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren > Social Network Links)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul „Social Network Links“. Hier definieren Sie, welche sozialen Netzwerke angezeigt werden sollen und wo sie in Ihrem Shop erscheinen.

**Zugriff:** Navigieren Sie zu **Module > Modul-Manager**, suchen Sie nach „Social Network Links“ und klicken Sie auf „Konfigurieren“.

#### **Allgemeine Einstellungen**

- **Facebook URL:**

  - **Was diese Einstellung bewirkt:** Hier geben Sie die vollständige Webadresse (URL) Ihrer Facebook-Seite ein.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ausgefüllt:* Ein Facebook-Icon erscheint im Modulblock und verlinkt direkt auf die von Ihnen angegebene URL.
    - *Wenn leer:* Es wird kein Facebook-Icon angezeigt.
  - **Empfohlener Wert:** Ihre offizielle Facebook-Seiten-URL (z. B. `https://www.facebook.com/ihrshopname`).
  - **Händlerszenario / Beispiel:** Wenn Ihre Facebook-Seite `https://www.facebook.com/MeinTollerShop` ist, geben Sie diese URL hier ein. Kunden, die auf das Facebook-Icon klicken, werden zu Ihrer Seite weitergeleitet.
- **Twitter URL:**

  - **Was diese Einstellung bewirkt:** Geben Sie die vollständige Webadresse (URL) Ihres Twitter-Profils ein.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ausgefüllt:* Ein Twitter-Icon erscheint und verlinkt auf Ihr Twitter-Profil.
    - *Wenn leer:* Es wird kein Twitter-Icon angezeigt.
  - **Empfohlener Wert:** Ihre offizielle Twitter-Profil-URL (z. B. `https://twitter.com/ihrshopname`).
  - **Händlerszenario / Beispiel:** Wenn Ihr Twitter-Handle `@MeinTollerShop` ist, könnte Ihre URL `https://twitter.com/MeinTollerShop` lauten.
- **YouTube URL:**

  - **Was diese Einstellung bewirkt:** Geben Sie die vollständige Webadresse (URL) Ihres YouTube-Kanals ein.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ausgefüllt:* Ein YouTube-Icon erscheint und verlinkt auf Ihren Kanal.
    - *Wenn leer:* Es wird kein YouTube-Icon angezeigt.
  - **Empfohlener Wert:** Ihre offizielle YouTube-Kanal-URL (z. B. `https://www.youtube.com/channel/ihrekanalid`).
  - **Händlerszenario / Beispiel:** Wenn Sie Produktbewertungsvideos oder Tutorials auf YouTube haben, verlinken Sie hier Ihren Kanal.
- **Google+ URL:**

  - **Was diese Einstellung bewirkt:** Geben Sie die vollständige Webadresse (URL) Ihres Google+-Profils oder Ihrer Seite ein.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ausgefüllt:* Ein Google+-Icon erscheint und verlinkt auf Ihr Profil.
    - *Wenn leer:* Es wird kein Google+-Icon angezeigt.
  - **Empfohlener Wert:** Ihre offizielle Google+-Profil-/Seiten-URL (z. B. `https://plus.google.com/+IhrShopName`).
  - **Händlerszenario / Beispiel:** Obwohl Google+ weitgehend eingestellt ist, können Sie es hier verlinken, wenn Sie noch eine Präsenz pflegen oder ältere Inhalte haben. Andernfalls lassen Sie es leer.
- **RSS URL:**

  - **Was diese Einstellung bewirkt:** Geben Sie die vollständige Webadresse (URL) Ihres RSS-Feeds ein. Dies wird typischerweise für Blogs oder Nachrichtenbereiche verwendet, damit Benutzer Updates abonnieren können.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ausgefüllt:* Ein RSS-Icon erscheint und verlinkt auf Ihren Feed.
    - *Wenn leer:* Es wird kein RSS-Icon angezeigt.
  - **Empfohlener Wert:** Wenn Ihr Shop einen Blog oder Nachrichtenbereich mit einem RSS-Feed hat, geben Sie dessen URL ein (z. B. `https://ihrshop.com/blog/feed`). Andernfalls lassen Sie es leer.
  - **Händlerszenario / Beispiel:** Wenn Sie regelmäßig Blogbeiträge über Ihre Produkte oder Branche veröffentlichen, ermöglicht ein RSS-Feed technikaffinen Kunden, Updates direkt zu erhalten.

#### **Anzeigeeinstellungen**

- **Im Header anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob der Block mit den Social-Network-Links im Header-Bereich Ihres Shops angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Der Social-Links-Block ist oben auf Ihrer Website sichtbar.
    - *Wenn deaktiviert (Nein):* Der Block wird nicht im Header angezeigt.
  - **Empfohlener Wert:** **Ja**, wenn Sie eine hohe Sichtbarkeit für Ihre Social-Links wünschen.
  - **Händlerszenario / Beispiel:** Aktivieren Sie dies, wenn Kunden Ihre soziale Präsenz sofort sehen sollen, wenn sie auf Ihrer Website landen.
- **In linker Spalte anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob der Block mit den Social-Network-Links in der linken Seitenleiste Ihres Shops angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Der Social-Links-Block ist in der linken Spalte sichtbar (sofern Ihr Theme eine hat).
    - *Wenn deaktiviert (Nein):* Der Block wird nicht in der linken Spalte angezeigt.
  - **Empfohlener Wert:** **Nein**, es sei denn, Sie haben einen bestimmten Grund, ihn dort zu platzieren, und Ihr Theme unterstützt eine linke Spalte. Oft wird die rechte Spalte oder der Footer bevorzugt.
  - **Händlerszenario / Beispiel:** Wenn Ihr Theme eine prominente linke Spalte hat und Sie die Links sichtbar halten möchten, während Kunden Kategorien durchsuchen, aktivieren Sie dies.
- **In rechter Spalte anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob der Block mit den Social-Network-Links in der rechten Seitenleiste Ihres Shops angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Der Social-Links-Block ist in der rechten Spalte sichtbar (sofern Ihr Theme eine hat).
    - *Wenn deaktiviert (Nein):* Der Block wird nicht in der rechten Spalte angezeigt.
  - **Empfohlener Wert:** **Ja**, wenn Sie die Links in einer Seitenleiste anzeigen möchten.
  - **Händlerszenario / Beispiel:** Eine gute Option, um Social-Links sichtbar zu halten, ohne den Header oder Footer zu überladen.
- **Im Footer anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob der Block mit den Social-Network-Links im Footer-Bereich Ihres Shops angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Der Social-Links-Block ist am unteren Rand Ihrer Website sichtbar.
    - *Wenn deaktiviert (Nein):* Der Block wird nicht im Footer angezeigt.
  - **Empfohlener Wert:** **Ja**, da der Footer ein Standard- und erwarteter Ort für Social-Media-Links ist.
  - **Händlerszenario / Beispiel:** Aktivieren Sie dies, um einen konsistenten Ort für Social-Links bereitzustellen, den Kunden oft am unteren Rand einer Seite suchen.
- **Auf Produktseite anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob der Block mit den Social-Network-Links auf einzelnen Produktseiten angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Der Social-Links-Block ist auf jeder Produktdetailseite sichtbar.
    - *Wenn deaktiviert (Nein):* Der Block wird nicht auf Produktseiten angezeigt.
  - **Empfohlener Wert:** **Ja**, wenn Sie das Teilen in sozialen Medien oder das Folgen direkt von Produktseiten aus fördern möchten.
  - **Händlerszenario / Beispiel:** Wenn Sie möchten, dass Kunden Ihre sozialen Medien leicht finden, während sie einen Kauf in Betracht ziehen, aktivieren Sie dies.

#### 2.1.1 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Facebook URL | Leer / Ihre Facebook-Seiten-URL | Link zu Ihrem Facebook-Profil. Leer = kein Icon. |
| Modulkonfiguration | Twitter URL | Leer / Ihre Twitter-Profil-URL | Link zu Ihrem Twitter-Profil. Leer = kein Icon. |
| Modulkonfiguration | YouTube URL | Leer / Ihre YouTube-Kanal-URL | Link zu Ihrem YouTube-Kanal. Leer = kein Icon. |
| Modulkonfiguration | Google+ URL | Leer / Ihre Google+-Profil-URL | Link zu Ihrem Google+-Profil. Leer = kein Icon. |
| Modulkonfiguration | RSS URL | Leer / Ihre RSS-Feed-URL | Link zu Ihrem RSS-Feed. Leer = kein Icon. |
| Modulkonfiguration | Im Header anzeigen | Nein / Ja | Social-Links im Header des Shops anzeigen. |
| Modulkonfiguration | In linker Spalte anzeigen | Nein / Nein | Social-Links in der linken Seitenleiste anzeigen. |
| Modulkonfiguration | In rechter Spalte anzeigen | Nein / Ja | Social-Links in der rechten Seitenleiste anzeigen. |
| Modulkonfiguration | Im Footer anzeigen | Nein / Ja | Social-Links im Footer des Shops anzeigen. |
| Modulkonfiguration | Auf Produktseite anzeigen | Nein / Ja | Social-Links auf einzelnen Produktseiten anzeigen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

- **F: Meine Social-Icons werden nach der Konfiguration nicht angezeigt.**

  - **A:** Überprüfen Sie zunächst, ob Sie die vollständigen URLs für Ihre sozialen Netzwerke in der Modulkonfiguration eingegeben haben. Stellen Sie außerdem sicher, dass Sie mindestens eine „Anzeigen in…“-Option ausgewählt haben (z. B. „Im Footer anzeigen“ auf Ja). Leeren Sie schließlich Ihren PrestaShop-Cache unter **Erweiterte Einstellungen > Leistung** (klicken Sie auf die Schaltfläche „Cache leeren“). Manchmal kann auch das Theme-Caching verhindern, dass Änderungen sofort angezeigt werden.
- **F: Die Icons werden angezeigt, sehen aber falsch ausgerichtet aus oder passen nicht zu meinem Theme.**

  - **A:** Das Modul bietet eine grundlegende Formatierung. Wenn Ihr Theme sehr spezifische CSS-Regeln hat, könnten diese die Stile des Moduls überschreiben oder mit ihnen in Konflikt geraten.
    - **Lösung 1 (Basis):** Versuchen Sie, den Cache Ihres Browsers zu leeren (Strg+F5 oder Cmd+R).
    - **Lösung 2 (Erweitert):** Dies erfordert normalerweise, dass ein Webmaster oder Entwickler das CSS Ihres Themes überprüft und möglicherweise benutzerdefinierte CSS-Regeln in die `custom.css`-Datei Ihres Themes hinzufügt, um das Erscheinungsbild anzupassen. Die CSS-Datei des Moduls (`socialnetworklinks.css`) kann als Referenz dienen.
- **F: Kann ich andere nicht aufgeführte soziale Netzwerke hinzufügen (z. B. Instagram, Pinterest)?**

  - **A:** Die aktuelle Version des Moduls unterstützt Facebook, Twitter, YouTube, Google+ und RSS. Um andere Netzwerke hinzuzufügen, wäre eine kundenspezifische Entwicklung erforderlich, um den Code des Moduls zu ändern und neue Icons und Eingabefelder hinzuzufügen. Alternativ suchen Sie nach einem umfassenderen Social-Media-Modul, wenn Sie eine größere Auswahl an Plattformen benötigen.
- **F: Die Links öffnen sich im selben Tab, aber ich möchte, dass sie sich in einem neuen Tab öffnen.**

  - **A:** Standardmäßig ist das Modul so konzipiert, dass Links in einem neuen Tab geöffnet werden (`target="_blank"`). Wenn dies nicht geschieht, kann dies an einem Konflikt mit dem JavaScript Ihres Themes oder einem älteren Browser liegen. Stellen Sie sicher, dass Ihr PrestaShop und Ihr Browser auf dem neuesten Stand sind. Wenn das Problem weiterhin besteht, müsste ein Entwickler den generierten HTML-Code überprüfen.
- **F: Ich habe „In linker/rechter Spalte anzeigen“ aktiviert, aber es erscheint nichts.**

  - **A:** Viele moderne PrestaShop-Themes sind ohne traditionelle linke oder rechte Spalten auf allen Seiten konzipiert, insbesondere auf Produktseiten oder der Startseite. Wenn Ihr Theme diese Spalten nicht rendert, hat das Modul keinen Platz, um seinen Block anzuzeigen. Überprüfen Sie die Dokumentation Ihres Themes oder passen Sie dessen Layout an, um Spalten zu aktivieren, wo Sie das Modul anzeigen möchten. Der Footer und der Header sind im Allgemeinen zuverlässigere Anzeigepositionen über verschiedene Themes hinweg.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Social Network Links“ ist ein unkompliziertes PrestaShop-Modul, das ein grundlegendes MVC-ähnliches Muster innerhalb des Modulumfangs verwendet. Es nutzt hauptsächlich die `Module`-Klasse für seine Kernfunktionalität, Konfiguration und Hook-Registrierung. Die Einstellungen werden direkt in der `ps_configuration`-Tabelle von PrestaShop gespeichert. Die Front-Office-Anzeige des Moduls wird über ein einziges Smarty-Template abgewickelt, das über verschiedene Display-Hooks gerendert wird.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird direkt innerhalb der `getContent()`-Methode der Hauptmodulklasse gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul enthält **keine** benutzerdefinierten Klassen oder `ObjectModel`-Definitionen. Die gesamte Logik ist in der Hauptklasse `SocialNetworkLinks` gekapselt.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält **keine** benutzerdefinierten JavaScript-Dateien. Die Funktionalität zum Öffnen von Links in neuen Tabs wird direkt im HTML des Templates mithilfe von `target="_blank"` gehandhabt.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`socialnetworklinks/css/socialnetworklinks.css`**
  - **Umfang:** Front-Office-Kunden-Styling.
  - **Wichtige UI-Komponenten und Container, die es stylt:** Dieses Stylesheet bietet das grundlegende visuelle Erscheinungsbild für die Social-Media-Icons, einschließlich ihrer Größe, Abstände und potenziellen Hover-Effekte. Es zielt auf den Hauptcontainerblock und einzelne Social-Link-Elemente ab.
  - **Wichtige CSS-Klassenselektoren, die Entwickler in ihrem Theme überschreiben können:**
    - `.socialnetworklinks_block`: Der Hauptcontainer für den Social-Links-Block.
    - `.socialnetworklinks_block ul`: Die ungeordnete Liste, die die Social-Icons enthält.
    - `.socialnetworklinks_block li`: Einzelne Listenelemente für jedes Social-Icon.
    - `.socialnetworklinks_block li a`: Der Anker-Tag für jeden Social-Link.
    - `.socialnetworklinks_block li a i`: Das Icon-Element (z. B. Font Awesome oder ähnliches, je nach Theme).
    - Spezifische Klassen für jedes soziale Netzwerk (z. B. `.facebook`, `.twitter` usw.) können vorhanden sein oder für benutzerdefiniertes Styling pro Netzwerk hinzugefügt werden.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - **`socialnetworklinks/views/front/column.tpl`**:
    - **Hook(s), in denen es gerendert wird:** `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (oder ähnlicher Produktseiten-Hook, abhängig von PrestaShop-Version und Theme).
    - **Visuelle Blockausgabe:** Dieses Template rendert die HTML-Struktur für den Social-Network-Links-Block. Es iteriert durch die konfigurierten Social-Network-URLs und zeigt ein Icon (typischerweise unter Verwendung einer Font-Icon-Bibliothek wie Font Awesome, die normalerweise vom Theme oder PrestaShop-Core bereitgestellt wird) für jeden aktiven Link an. Jedes Icon ist in einem `<a>`-Tag mit `target="_blank"` umschlossen, um den Link in einem neuen Tab zu öffnen.
    - **Verfügbare Variablen:**
      - `$facebook_url`: Die konfigurierte Facebook-URL.
      - `$twitter_url`: Die konfigurierte Twitter-URL.
      - `$youtube_url`: Die konfigurierte YouTube-URL.
      - `$google_url`: Die konfigurierte Google+-URL.
      - `$rss_url`: Die konfigurierte RSS-URL.
      - `$module_dir`: Das Basisverzeichnis des Moduls, nützlich zum Verlinken von Modul-Assets (obwohl in diesem spezifischen Template nicht stark genutzt).

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Alle Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Schlüsseln gespeichert, die mit `SOCIALNETWORKLINKS_` präfixiert sind.

  - `PS_SOCIALNETWORKLINKS_FACEBOOK_URL`
  - `PS_SOCIALNETWORKLINKS_TWITTER_URL`
  - `PS_SOCIALNETWORKLINKS_YOUTUBE_URL`
  - `PS_SOCIALNETWORKLINKS_GOOGLE_URL`
  - `PS_SOCIALNETWORKLINKS_RSS_URL`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_HEADER`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_LEFT_COLUMN`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_RIGHT_COLUMN`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_FOOTER`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_PRODUCT_PAGE`
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Rendert Inhalte innerhalb des `<head>`-Abschnitts oder ganz oben im `<body>`. | Wird verwendet, um den Social-Links-Block im Header des Shops anzuzeigen. |
| `displayLeftColumn` | Rendert Inhalte in der linken Seitenleiste. | Wird verwendet, um den Social-Links-Block in der linken Spalte anzuzeigen. |
| `displayRightColumn` | Rendert Inhalte in der rechten Seitenleiste. | Wird verwendet, um den Social-Links-Block in der rechten Spalte anzuzeigen. |
| `displayFooter` | Rendert Inhalte im Footer des Shops. | Wird verwendet, um den Social-Links-Block im Footer anzuzeigen. |
| `displayProductButtons` (oder ähnlicher Produktseiten-Hook) | Rendert Inhalte auf der Produktseite, oft in der Nähe der Schaltfläche „In den Warenkorb“ oder der Produktbeschreibung. | Wird verwendet, um den Social-Links-Block auf einzelnen Produktseiten anzuzeigen. |
| `moduleRoutes` | (Implizit von PrestaShop für die Modulkonfiguration gehandhabt) | Wird nicht direkt für die Front-Office-Anzeige verwendet, ist aber Teil des Modul-Lebenszyklus. |
| `actionAdminControllerSetMedia` | (Implizit von PrestaShop für die Modulkonfiguration gehandhabt) | Wird verwendet, um CSS/JS im Back Office für die Konfigurationsseite des Moduls zu laden. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Social Network Links“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
