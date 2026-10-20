---
title: "Gutscheine für reduzierte Artikel deaktivieren – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Gutscheine für reduzierte Artikel deaktivieren“ von MyPresta.eu."
sidebar:
  label: "Gutscheine für reduzierte Artikel deaktivieren – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Disable vouchers for items on sale auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/disable-vouchers-for-items-on-sale.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/disable-vouchers-for-items-on-sale/)
>
> ---


# Gutscheine für reduzierte Artikel deaktivieren

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich, die typischerweise in jeder modernen PrestaShop-Hosting-Umgebung verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul „Gutscheine für reduzierte Artikel deaktivieren“. Sie können darauf zugreifen, indem Sie zu **Module > Modul-Manager** navigieren, nach „Gutscheine für reduzierte Artikel deaktivieren“ suchen und dann auf die Schaltfläche „Konfigurieren“ klicken.

#### **Allgemeine Einstellungen**

- **Gutscheine für reduzierte Artikel deaktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der primäre Schalter, um die Kernfunktionalität des Moduls zu aktivieren oder zu deaktivieren.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Wenn der Warenkorb eines Kunden *irgendein* Produkt enthält, das derzeit reduziert ist (einen Sonderpreis hat), wird er daran gehindert, *irgendeinen* Gutscheincode anzuwenden.
    - *Wenn deaktiviert (NEIN):* Das Modul ist inaktiv. Kunden können Gutscheincodes anwenden, auch wenn ihr Warenkorb reduzierte Artikel enthält, was „Doppelrabatte“ ermöglicht.
  - **Empfohlener Wert:** **JA**, wenn Sie Doppelrabatte verhindern und Ihre Margen schützen möchten.
  - **Händlerszenario / Beispiel:** Sie führen einen „Sommer-Sale“ mit 20 % Rabatt auf ausgewählte Artikel durch. Sie haben auch einen „Welcome10“-Gutschein für Neukunden. Wenn diese Einstellung **JA** ist, kann ein Neukunde „Welcome10“ nicht verwenden, wenn sein Warenkorb Artikel aus dem Sommer-Sale enthält.
- **Modul für Codes deaktivieren, die mit beginnen:**

  - **Was diese Einstellung bewirkt:** Dies ermöglicht Ihnen, eine Ausnahme zu erstellen. Wenn ein Gutscheincode mit einer von Ihnen hier definierten spezifischen Zeichenfolge beginnt, gilt die Einschränkung des Moduls *nicht* für diesen Gutschein, selbst wenn reduzierte Artikel im Warenkorb sind.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn eine Zeichenfolge eingegeben wird (z.B. „FREESHIP“):* Jeder Gutscheincode, der mit „FREESHIP“ beginnt (z.B. „FREESHIP2023“, „FREESHIPNOW“), umgeht die Einschränkung des Moduls. Kunden können diese spezifischen Gutscheine auch bei reduzierten Artikeln in ihrem Warenkorb verwenden.
    - *Wenn leer gelassen:* Es werden keine Ausnahmen basierend auf Gutscheincode-Präfixen gemacht. Alle Gutscheine unterliegen der Regel „Gutscheine für reduzierte Artikel deaktivieren“.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben spezifische Gutscheine, die Sie *immer* zulassen möchten, unabhängig von reduzierten Artikeln.
  - **Händlerszenario / Beispiel:** Sie haben einen speziellen „FREESHIP“-Gutschein, der kostenlosen Versand bietet. Sie entscheiden, dass kostenloser Versand immer erlaubt sein sollte, auch bei reduzierten Artikeln, um größere Bestellungen zu fördern. Sie würden „FREESHIP“ in dieses Feld eingeben.
- **Nachricht für Kunden:**

  - **Was diese Einstellung bewirkt:** Dies ist die benutzerdefinierte Nachricht, die Kunden in ihrem Warenkorb sehen, wenn sie versuchen, einen Gutscheincode anzuwenden, aber aufgrund reduzierter Artikel blockiert werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn eine Nachricht eingegeben wird (z.B. „Gutscheine können nicht mit reduzierten Artikeln verwendet werden.“):* Diese genaue Nachricht wird dem Kunden angezeigt.
    - *Wenn leer gelassen:* Das Modul zeigt wahrscheinlich eine Standard- oder generische Fehlermeldung an, die für den Kunden weniger klar sein könnte.
  - **Empfohlener Wert:** Eine klare, höfliche und informative Nachricht.
  - **Händlerszenario / Beispiel:** Sie möchten Kunden klar informieren: „Dieser Gutschein kann nicht angewendet werden, da Ihr Warenkorb bereits reduzierte Artikel enthält. Bitte entfernen Sie reduzierte Artikel oder verwenden Sie einen anderen Gutschein.“

#### **Konfigurations-Schnellreferenztabelle**

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Gutscheine für reduzierte Artikel deaktivieren | JA | Aktiviert/deaktiviert die Kernfunktionalität, um Gutscheine für reduzierte Artikel zu blockieren. |
| Modulkonfiguration | Modul für Codes deaktivieren, die mit beginnen: | Leer lassen | Ermöglicht es spezifischen Gutscheincodes (nach Präfix), die Einschränkungen des Moduls zu umgehen. |
| Modulkonfiguration | Nachricht für Kunden | „Gutscheine können nicht mit reduzierten Artikeln verwendet werden.“ (oder ähnlich) | Passt die Fehlermeldung an, die Kunden angezeigt wird, wenn ein Gutschein blockiert wird. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul aktiviert, aber Kunden können immer noch Gutscheine für reduzierte Artikel verwenden. Was ist falsch?**
A:

1.  **Überprüfen Sie die Einstellung „Gutscheine für reduzierte Artikel deaktivieren“:** Stellen Sie sicher, dass sie in der Modulkonfiguration auf **JA** gesetzt ist.
2.  **Cache leeren:** Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Moduländerungen erfordern manchmal eine Cache-Aktualisierung.
3.  **Verkaufsstatus überprüfen:** Überprüfen Sie nochmals, ob die Produkte, mit denen Sie testen, in PrestaShop tatsächlich als „reduziert“ gekennzeichnet sind (z.B. sie haben einen spezifischen Preis, der sie günstiger macht als ihren regulären Preis).
4.  **Ausnahme für Gutscheincode-Präfix überprüfen:** Wenn Sie eine Zeichenfolge in „Modul für Codes deaktivieren, die mit beginnen:“ eingegeben haben, stellen Sie sicher, dass der Gutschein, den Sie testen, nicht mit dieser Zeichenfolge beginnt.

**F: Das Modul blockiert Gutscheine, aber die Nachricht wird nicht angezeigt oder es wird ein generischer Fehler angezeigt.**
A:

1.  **Nachricht anpassen:** Gehen Sie zur Modulkonfiguration und stellen Sie sicher, dass Sie eine benutzerdefinierte Nachricht im Feld „Nachricht für Kunden“ eingegeben haben.
2.  **Theme-Kompatibilität:** Obwohl das Modul versucht, sich nahtlos zu integrieren, können einige stark angepasste Themes die Standard-PrestaShop-Fehleranzeigemechanismen überschreiben. Wenn die Nachricht nicht angezeigt wird, könnte es sich um ein Front-Office-Theme-Problem handeln. Kontaktieren Sie Ihren Theme-Entwickler oder einen Webmaster für Unterstützung.

**F: Kann ich dieses Modul für bestimmte Kundengruppen oder einzelne Produkte deaktivieren?**
A: Nein, dieses Modul funktioniert global basierend auf dem Vorhandensein *jedes* reduzierten Artikels im Warenkorb. Es bietet keine detaillierte Kontrolle für spezifische Kundengruppen oder Produktausschlüsse über die Ausnahme des Gutscheincode-Präfixes hinaus. Wenn Sie eine komplexere Logik benötigen, ist möglicherweise eine kundenspezifische Entwicklung erforderlich.

**F: Beeinflusst dieses Modul meine SEO oder Produktlisten?**
A: Nein, dieses Modul arbeitet rein auf der Logik der Gutscheinanwendung im Warenkorb. Es ändert keine Produktpreise, Beschreibungen, URLs oder andere Front-Office-Elemente, die die SEO beeinflussen würden.

**F: Ich habe meine PrestaShop-Version aktualisiert, und jetzt funktioniert das Modul nicht mehr.**
A:

1.  **Modulkompatibilität überprüfen:** Stellen Sie sicher, dass Sie die Version des Moduls heruntergeladen und installiert haben, die speziell für Ihre PrestaShop-Version von Ihrem MyPresta.eu-Konto entwickelt wurde.
2.  **Neu installieren/Neu konfigurieren:** Manchmal müssen Module nach einem größeren PrestaShop-Update neu installiert oder neu konfiguriert werden. Versuchen Sie, das Modul zu deinstallieren und dann neu zu installieren (denken Sie daran, Ihre Einstellungen, falls möglich, zu sichern, obwohl dieses Modul minimale Daten hat).
3.  **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache nach jedem Update oder jeder Moduländerung.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Gutscheine für reduzierte Artikel deaktivieren“ (`dvfis`) funktioniert hauptsächlich, indem es den Kern-`CartController` überschreibt, um den Gutscheinanwendungsprozess abzufangen. Es nutzt den PrestaShop-Override-Mechanismus, um seine Logik einzufügen, bevor ein Gutschein validiert und angewendet wird. Die Konfiguration des Moduls wird in `ps_configuration` gespeichert und über die Hauptmodulklasse aufgerufen.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `dvfis/override/controllers/front/CartController.php`
    - **Klassenname & Elternklasse**: `CartController` (überschreibt die Kernklasse `CartController`)
    - **Verantwortlichkeit**: Dies ist die wichtigste Datei. Sie erweitert den Kern-`CartController`, um die Methode `postProcess()` zu ändern. Insbesondere fängt sie die Logik ab, wenn ein Kunde versucht, einen Gutschein hinzuzufügen (`addDiscount()`). Sie prüft, ob das Modul aktiviert ist und ob der Warenkorb Produkte mit einem Sonderpreis enthält. Wenn beide Bedingungen erfüllt sind (und der Gutscheincode keinem Ausschlusspräfix entspricht), verhindert sie das Hinzufügen des Gutscheins und zeigt eine benutzerdefinierte Fehlermeldung an.
  - `dvfis/override/controllers/front/index.php`
    - **Klassenname & Elternklasse**: Keine Klassendatei, typischerweise eine leere Datei oder eine Datei mit einem einfachen `<?php exit;`, um direkte Verzeichnisauflistung zu verhindern. Dies ist eine Standardpraxis für PrestaShop-Override-Verzeichnisse.
- **Back-Office-Admin-Controller**: Keine. Das Modul verwendet die Standardmethode `getContent()` innerhalb seiner Hauptmoduldatei für die Konfiguration.

### 4.3 Kernklassen & Modelle (`classes/`)

Keine. Das Modul definiert keine benutzerdefinierten `ObjectModel`-Klassen oder andere eigenständige PHP-Klassen im Verzeichnis `classes/`. Die gesamte Logik ist in der Hauptmoduldatei und dem `CartController`-Override enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

Keine. Das Modul enthält keine benutzerdefinierten JavaScript-Dateien. Alle Front-Office-Interaktionen werden serverseitig durch den `CartController`-Override behandelt.

### 4.5 CSS-Stylesheets (`views/css/`)

Keine. Das Modul enthält keine benutzerdefinierten CSS-Dateien. Alle dem Kunden angezeigten Nachrichten erben das Styling der Fehler-/Benachrichtigungsmeldungen des aktiven PrestaShop-Themes.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Keine. Das Modul verwendet keine benutzerdefinierten Smarty-Template-Dateien. Fehlermeldungen werden direkt an das `errors`-Array des `CartController` übergeben, die dann vom Standard-Fehleranzeigemechanismus des Themes gerendert werden.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Alle seine Konfigurationseinstellungen werden in der Tabelle `ps_configuration` gespeichert:

  - `DVFIS_MESSAGE`: Speichert die benutzerdefinierte Nachricht für Kunden.
  - `DVFIS_ENABLED`: Speichert den booleschen Wert (0 oder 1) zum Aktivieren/Deaktivieren des Moduls.
  - `DVFIS_STR`: Speichert das Zeichenfolgenpräfix für Gutscheincode-Ausnahmen.
  - `DVFIS_STRV`: (Wahrscheinlich ein veralteter oder interner Versionsschlüssel, nicht direkt vom Benutzer konfigurierbar).
  - `mypresta_updates`, `update_`, `updatev_`: Schlüssel, die mit dem Update-System von MyPresta.eu zusammenhängen.
  - `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Standard-PrestaShop-Konfigurationsschlüssel, die für die Sprachbehandlung in der `getContent()`-Methode des Moduls verwendet werden.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Während der Initialisierung des Back-Office-Controllers | Wird vom Modul verwendet, um eigene CSS-/JS-Dateien (falls vorhanden) im Back Office einzubinden. Im Fall dieses Moduls wird es wahrscheinlich für das Update-System von MyPresta.eu oder die allgemeine Moduleinrichtung verwendet, nicht für benutzerdefiniertes Styling/Scripting. |
| `actionFrontControllerInitAfter` | Nachdem ein Front-Office-Controller initialisiert wurde | Wird vom Modul verwendet, um möglicherweise Aktionen auszuführen oder das Controller-Verhalten früh im Anforderungslebenszyklus zu ändern. Für dieses Modul wird es wahrscheinlich verwendet, um sicherzustellen, dass der `CartController`-Override korrekt geladen und aktiv ist. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Gutscheine für reduzierte Artikel deaktivieren“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen bezüglich der Funktionalität und Kompatibilität des Moduls gerne zur Verfügung.
