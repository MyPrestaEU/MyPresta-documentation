---
title: "Homeslider on top – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Homeslider on top von MyPresta.eu."
sidebar:
  label: "Homeslider on top – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Homeslider on top auf MyPresta.eu kaufen](https://mypresta.eu/modules/slider-slideshow/homeslider-on-top.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/sliders-slideshows/homeslider-on-top/)
>
> ---


# Homeslider on top

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für eine PrestaShop-Installation erforderlich und unterstützen dieses Modul.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Dieses Modul ist extrem einfach konzipiert und fungiert hauptsächlich als „Brücke“, um den *Standard-PrestaShop-Bild-Slider* an einem neuen Ort anzeigen zu können. Daher ist der eigene Konfigurationsbildschirm minimal. Die eigentlichen Slider-Bilder, Links und Einstellungen (wie Geschwindigkeit, Pause bei Hover usw.) werden über das Standard-PrestaShop-Modul „Bild-Slider“ verwaltet.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation von „Homeslider on top“ navigieren Sie zu **Module > Modul-Manager**, suchen nach „Homeslider on top“ und klicken auf „Konfigurieren“.

Sie finden in der Regel eine sehr einfache Konfigurationsoberfläche, die sich hauptsächlich auf das Aktivieren oder Deaktivieren der Kernfunktionalität des Moduls konzentriert.

- **Was diese Einstellung bewirkt:** Diese Einstellung steuert, ob das Modul „Homeslider on top“ aktiv ist und versucht, Ihren Bild-Slider an der vorgesehenen oberen Position anzuzeigen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Das Modul registriert seine Hooks und versucht, den Standard-PrestaShop-Bild-Slider oben in Ihrem Shop zu rendern.
  - *Wenn deaktiviert:* Das Modul funktioniert nicht mehr, und der Bild-Slider erscheint nicht an der oberen Position (er kehrt zu seiner Standardplatzierung zurück, wenn das Standard-Bild-Slider-Modul noch aktiv und an anderer Stelle gehookt ist).
- **Empfohlener Wert:** **JA** (Aktiviert), wenn Ihr Slider oben erscheinen soll.
- **Händlerszenario / Beispiel:** Sie haben gerade eine neue Kollektion auf den Markt gebracht und möchten diese prominent mit einem großen Banner ganz oben auf Ihrer Website präsentieren. Sie würden dieses Modul aktivieren. Wenn Sie später entscheiden, dass Sie den Slider an einer anderen Stelle bevorzugen (z. B. unterhalb des Headers), könnten Sie dieses Modul deaktivieren und das Standard-Bild-Slider-Modul an anderer Stelle neu hooken.

**Wichtiger Hinweis:** Dieses Modul verwaltet *nicht* die Bilder oder Einstellungen des Sliders selbst. Um Slides hinzuzufügen, zu bearbeiten oder zu entfernen oder das Slider-Verhalten zu ändern (wie Übergangsgeschwindigkeit, Auto-Play usw.), müssen Sie zur Konfiguration des Moduls **„Bild-Slider“** gehen (oft zu finden unter **Module > Modul-Manager**, suchen Sie nach „Bild-Slider“ oder „ps\_imageslider“).

### 2.2 Kurzübersichtstabelle zur Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Modul aktiviert/deaktiviert | Aktiviert | Steuert, ob das Modul den Bild-Slider aktiv oben im Shop anzeigt. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Mein Slider wird überhaupt nicht angezeigt, selbst nachdem ich das Modul aktiviert habe.**
A:

1. **Überprüfen Sie das Modul „Bild-Slider“:** Stellen Sie sicher, dass das *Standard-PrestaShop-Modul „Bild-Slider“* (oft `ps_imageslider` genannt) installiert, aktiviert ist und Slides konfiguriert wurden. Dieses Modul „Homeslider on top“ ändert nur die *Position* dieses bestehenden Sliders.
2. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal benötigt PrestaShop eine Cache-Aktualisierung, um neue Modulplatzierungen zu erkennen.
3. **Theme-Kompatibilität:** Obwohl für breite Kompatibilität konzipiert, können einige stark angepasste Themes das Standard-Hook-Verhalten überschreiben. Wenn Probleme weiterhin bestehen, wenden Sie sich an Ihren Theme-Entwickler oder den MyPresta.eu-Support.

**F: Der Slider wird angezeigt, sieht aber seltsam oder falsch ausgerichtet aus.**
A:

1. **Überprüfen Sie die Einstellungen des „Bild-Sliders“:** Stellen Sie sicher, dass die Bilder, die Sie in das *Standard-PrestaShop-Modul „Bild-Slider“* hochgeladen haben, konsistente Abmessungen und eine hohe Qualität aufweisen.
2. **Theme-Styling:** Das CSS Ihres Themes könnte Konflikte verursachen. Dieses Modul kümmert sich hauptsächlich um die Platzierung. Wenn das Styling nicht stimmt, liegt es wahrscheinlich an einem CSS-Problem Ihres Themes, das mit den Standardstilen des Sliders interagiert. Möglicherweise benötigen Sie einen Webentwickler, um das CSS zu überprüfen.

**F: Wie ändere ich die Bilder oder die Geschwindigkeit des Sliders?**
A: Dieses Modul steuert nur die *Platzierung*. Um den tatsächlichen Inhalt (Bilder, Links, Beschreibungen) und das Verhalten (Geschwindigkeit, Auto-Play, Pause bei Hover) des Sliders zu verwalten, müssen Sie zur Konfiguration des Moduls **„Bild-Slider“** gehen (das Standard-PrestaShop-Modul, normalerweise zu finden, indem Sie in **Module > Modul-Manager** nach „Bild-Slider“ suchen).

**F: Kann ich zwei Slider haben, einen oben und einen in der Standardposition?**
A: Dieses Modul verschiebt den *Standard*-PrestaShop-Bild-Slider speziell nach oben. Wenn Sie einen zweiten, unabhängigen Slider wünschen, benötigen Sie ein anderes Modul, das für diesen Zweck entwickelt wurde.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Überblick für Entwickler und Webmaster, die das Modul „Homeslider on top“ verstehen, anpassen oder Fehler beheben möchten.

### 4.1 Architekturübersicht

Das Modul „Homeslider on top“ ist ein leichtgewichtiges PrestaShop-Modul, das hauptsächlich dazu dient, den Anzeigeort des Kernmoduls `ps_imageslider` zu ändern. Dies wird erreicht, indem `ps_imageslider` von seinen Standard-Hooks (wie `displayHome`) abgemeldet und an einem prominenteren Hook, typischerweise `displayHeader`, neu registriert wird. Es führt keine neuen Datenbanktabellen, komplexen Klassen oder umfangreichen Front-Office-Assets ein, was es zu einem einfachen, aber effektiven „Hook-Manager“ für die bestehende Slider-Funktionalität macht.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Die gesamte Konfiguration wird direkt in der Methode `getContent()` der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt keine benutzerdefinierten Klassen oder Modelle ein. Es interagiert mit den Kernfunktionen der PrestaShop-Modulverwaltung.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien. Das JavaScript für die Slider-Funktionalität wird vom Modul `ps_imageslider` selbst bereitgestellt.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Das Styling für den Slider wird vom Modul `ps_imageslider` und/oder dem aktiven PrestaShop-Theme bereitgestellt.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul enthält keine benutzerdefinierten Smarty-Template-Dateien. Es greift auf die vom Modul `ps_imageslider` bereitgestellten Templates zurück.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Seine Konfiguration wird in `ps_configuration` unter Verwendung von Standard-PrestaShop-Konfigurationsschlüsseln gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `install()` | Während der Modulinstallation | Registriert das Modul bei `displayHeader` und meldet `ps_imageslider` möglicherweise von `displayHome` oder anderen Standard-Hooks ab. |
| `uninstall()` | Während der Moduldeinstallation | Meldet das Modul von `displayHeader` ab und registriert `ps_imageslider` möglicherweise wieder bei seinen Standard-Hooks. |
| `displayHeader` | Rendert Inhalte innerhalb des `<head>`-Abschnitts oder ganz oben im `<body>` | Dies ist der primäre Hook, an dem das Modul versucht, den Inhalt von `ps_imageslider` zu rendern. |
| `hookDisplayHeader` | Wenn `displayHeader` aufgerufen wird | Die Methode des Moduls, die ausgeführt wird, wenn `displayHeader` aufgerufen wird. Sie ruft typischerweise `Module::hookDisplayHome()` des Moduls `ps_imageslider` auf, um dessen Inhalt zu rendern. |

Die Kernlogik befindet sich in der Datei `homeslider-on-top.php`, insbesondere in den Methoden `install()`, `uninstall()` und `hookDisplayHeader()`. Die Methode `hookDisplayHeader()` ist entscheidend, da sie dafür verantwortlich ist, den Inhalt des Moduls `ps_imageslider` abzurufen und zu rendern, wenn dieses Modul aktiv ist.

**Schlüssellogik innerhalb von `homeslider-on-top.php`:**

- **`__construct()`**: Richtet grundlegende Modulinformationen ein.
- **`install()`**:
  - Ruft `parent::install()` auf.
  - Registriert das Modul bei `displayHeader`.
  - Versucht entscheidend, das Modul `ps_imageslider` von `displayHome` abzumelden, um eine doppelte Anzeige zu verhindern, und registriert dann `ps_imageslider` bei `displayHeader`, falls es noch nicht dort ist, oder stellt sicher, dass sein Inhalt über die `hookDisplayHeader` dieses Moduls gerendert wird.
- **`uninstall()`**:
  - Ruft `parent::uninstall()` auf.
  - Meldet das Modul von `displayHeader` ab.
  - Registriert `ps_imageslider` wieder bei `displayHome`, um das Standardverhalten wiederherzustellen.
- **`getContent()`**: Verwaltet das Back-Office-Konfigurationsformular des Moduls (das normalerweise sehr einfach ist, oft nur ein Aktivieren/Deaktivieren-Schalter).
- **`hookDisplayHeader()`**:
  - Diese Methode wird ausgeführt, wenn der `displayHeader`-Hook von PrestaShop aufgerufen wird.
  - Sie prüft typischerweise, ob das Modul `ps_imageslider` installiert und aktiviert ist.
  - Wenn ja, ruft sie direkt die Methode `hookDisplayHome()` des Moduls `ps_imageslider` auf, um dessen gerenderten Inhalt abzurufen und zurückzugeben, wodurch die Ausgabe des Sliders effektiv an die Position `displayHeader` „verschoben“ wird.

Entwickler, die dieses Modul anpassen möchten, würden sich hauptsächlich auf die Methode `hookDisplayHeader()` konzentrieren, wenn sie ändern möchten, wie der Inhalt von `ps_imageslider` abgerufen oder umschlossen wird, oder auf die Methoden `install()`/`uninstall()`, wenn sie die beteiligten spezifischen Hooks ändern müssten.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Homeslider on top“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
