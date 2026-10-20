---
title: "Kundenproduktfotos - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Kundenproduktfotos“ von MyPresta.eu."
sidebar:
  label: "Kundenproduktfotos - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Customer product photos auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/customer-product-photos.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/customer-product-photos/)
>
> ---


# Kundenproduktfotos

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich, die typischerweise in den meisten modernen Hosting-Umgebungen verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Kundenproduktfotos“. Hier finden Sie eine Vielzahl von Einstellungen, um das Verhalten und Aussehen des Moduls in Ihrem Shop zu steuern.

#### Allgemeine Einstellungen

- **JPEG-Dateien zulassen?**
  - **Was diese Einstellung bewirkt:** Legt fest, ob Kunden Bilder im JPEG-Format hochladen können.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können `.jpg`- oder `.jpeg`-Dateien hochladen.
    - *Wenn deaktiviert:* JPEG-Dateien werden beim Hochladen abgelehnt.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Die meisten Fotos werden im JPEG-Format aufgenommen. Wenn diese Option aktiviert bleibt, wird maximale Kompatibilität für Kunden-Uploads gewährleistet.
- **GIF-Dateien zulassen?**
  - **Was diese Einstellung bewirkt:** Legt fest, ob Kunden Bilder im GIF-Format hochladen können.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können `.gif`-Dateien hochladen.
    - *Wenn deaktiviert:* GIF-Dateien werden beim Hochladen abgelehnt.
  - **Empfohlener Wert:** JA (es sei denn, Sie haben einen spezifischen Grund, animierte Bilder zu verbieten)
  - **Händlerszenario / Beispiel:** GIFs können nützlich sein, um kurze Animationen eines Produkts zu zeigen, können aber auch größere Dateien sein. Aktivieren Sie diese Option, wenn Sie sie unterstützen möchten.
- **PNG-Dateien zulassen?**
  - **Was diese Einstellung bewirkt:** Legt fest, ob Kunden Bilder im PNG-Format hochladen können.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können `.png`-Dateien hochladen.
    - *Wenn deaktiviert:* PNG-Dateien werden beim Hochladen abgelehnt.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** PNGs eignen sich hervorragend für Bilder mit Transparenz oder scharfen Grafiken. Es ist ein gängiges Format, daher ist die Aktivierung im Allgemeinen eine gute Idee.
- **BMP-Dateien zulassen?**
  - **Was diese Einstellung bewirkt:** Legt fest, ob Kunden Bilder im BMP-Format hochladen können.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können `.bmp`-Dateien hochladen.
    - *Wenn deaktiviert:* BMP-Dateien werden beim Hochladen abgelehnt.
  - **Empfohlener Wert:** NEIN (es sei denn, es ist speziell erforderlich)
  - **Händlerszenario / Beispiel:** BMP-Dateien sind typischerweise sehr groß und unkomprimiert, was sie für die Webnutzung ungeeignet macht. Das Deaktivieren hilft, Ihre Galerie effizient zu halten.
- **Nicht eingeloggten Kunden das Hochladen von Fotos erlauben?**
  - **Was diese Einstellung bewirkt:** Steuert, ob Besucher, die nicht in einem Kundenkonto angemeldet sind, Fotos hochladen können.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Gäste können Fotos hochladen. Sie werden möglicherweise nach einer E-Mail-Adresse oder einem Namen gefragt.
    - *Wenn deaktiviert:* Nur registrierte und eingeloggte Kunden können Fotos hochladen.
  - **Empfohlener Wert:** JA (wenn Sie maximale Inhaltserstellung wünschen), NEIN (wenn Sie Inhalte an bestimmte Kundenkonten binden möchten)
  - **Händlerszenario / Beispiel:** Wenn Sie benutzergenerierte Inhalte maximieren möchten, ist es vorteilhaft, Gästen das Hochladen zu erlauben. Wenn Sie verfolgen möchten, wer was hochlädt und sie möglicherweise belohnen möchten, ist eine Anmeldung erforderlich.
- **Maximale Dateigröße (in MB)**
  - **Was diese Einstellung bewirkt:** Legt die Obergrenze für die Größe einer Bilddatei fest, die ein Kunde hochladen kann.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf 5 eingestellt:* Kunden können keine Dateien hochladen, die größer als 5 MB sind.
    - *Wenn auf 0 eingestellt:* Keine Begrenzung (obwohl PHP-Serverlimits weiterhin gelten).
  - **Empfohlener Wert:** 2-5 MB
  - **Händlerszenario / Beispiel:** Eine angemessene Begrenzung verhindert, dass Kunden übermäßig große Dateien hochladen, die Ihre Website verlangsamen oder zu viel Serverspeicher verbrauchen könnten. 2-5 MB sind normalerweise ausreichend für hochwertige Webbilder.
- **Miniaturbildhöhe (px)**
  - **Was diese Einstellung bewirkt:** Definiert die Höhe der für die Galerie generierten Miniaturbilder.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf 100 eingestellt:* Alle Miniaturbilder sind 100 Pixel hoch.
    - *Wenn auf 200 eingestellt:* Alle Miniaturbilder sind 200 Pixel hoch.
  - **Empfohlener Wert:** 150-250px (an das Design Ihres Themes anpassen)
  - **Händlerszenario / Beispiel:** Konsistente Miniaturbildgrößen gewährleisten ein sauberes und organisiertes Galerie-Layout. Passen Sie dies an die Ästhetik Ihres Themes an.
- **Miniaturbildbreite (px)**
  - **Was diese Einstellung bewirkt:** Definiert die Breite der für die Galerie generierten Miniaturbilder.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf 100 eingestellt:* Alle Miniaturbilder sind 100 Pixel breit.
    - *Wenn auf 200 eingestellt:* Alle Miniaturbilder sind 200 Pixel breit.
  - **Empfohlener Wert:** 150-250px (an das Design Ihres Themes anpassen)
  - **Händlerszenario / Beispiel:** Ähnlich wie bei der Höhe trägt eine konsistente Breite dazu bei, eine optisch ansprechende Galerie zu erhalten.
- **Fotos pro Seite in der Galerie** (CG\_PAGINATION)
  - **Was diese Einstellung bewirkt:** Steuert, wie viele Kundenfotos auf einer einzelnen Seite in der Hauptgalerieansicht angezeigt werden, bevor die Paginierung einsetzt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf 12 eingestellt:* Die Galerie zeigt 12 Fotos pro Seite.
    - *Wenn auf 24 eingestellt:* Die Galerie zeigt 24 Fotos pro Seite.
  - **Empfohlener Wert:** 12-24
  - **Händlerszenario / Beispiel:** Eine moderate Anzahl verhindert, dass der Benutzer überfordert wird, und hält die Ladezeiten der Seite angemessen. Zu wenige bedeuten mehr Klicks, zu viele können die Seite verlangsamen.
- **Abstimmung für Fotos aktivieren?** (CG\_voting)
  - **Was diese Einstellung bewirkt:** Ermöglicht Kunden, über hochgeladene Fotos abzustimmen, typischerweise mit einem einfachen „Gefällt mir“ oder einer Sternebewertung.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Abstimmungssteuerungen (z. B. Sterne, Daumen hoch) erscheinen neben jedem Foto.
    - *Wenn deaktiviert:* Es werden keine Abstimmungsoptionen angezeigt.
  - **Empfohlener Wert:** JA (fördert die Interaktion)
  - **Händlerszenario / Beispiel:** Das Aktivieren der Abstimmung kann beliebte Fotos hervorheben und mehr Engagement in Ihrer Community fördern.
- **Nicht eingeloggten Kunden das Abstimmen erlauben?** (cg\_unl\_voting)
  - **Was diese Einstellung bewirkt:** Legt fest, ob Besucher, die nicht angemeldet sind, Stimmen für Fotos abgeben können.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Gäste können über Fotos abstimmen.
    - *Wenn deaktiviert:* Nur eingeloggte Kunden können abstimmen.
  - **Empfohlener Wert:** NEIN (um Spam-/Bot-Abstimmungen zu verhindern und ein aussagekräftigeres Engagement zu gewährleisten)
  - **Händlerszenario / Beispiel:** Die Beschränkung der Abstimmung auf eingeloggte Benutzer hilft sicherzustellen, dass die Stimmen von tatsächlichen Kunden stammen und das Risiko der Manipulation verringert wird.
- **Abstimmungsstil** (CG\_VOTE\_STAR, CGV\_voting)
  - **Was diese Einstellung bewirkt:** Wählt den visuellen Stil für den Abstimmungsmechanismus (z. B. verschiedene Sternfarben).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „Schwarze Sterne“ eingestellt:* Die Abstimmung verwendet schwarze Sternsymbole.
    - *Wenn auf „Goldene Sterne“ eingestellt:* Die Abstimmung verwendet goldene Sternsymbole.
  - **Empfohlener Wert:** Goldene Sterne (oft mit Qualität und Bewertungen assoziiert)
  - **Händlerszenario / Beispiel:** Wählen Sie einen Stil, der am besten zum Branding und zur Ästhetik Ihres Shops passt.
- **Wettbewerbsmodus aktivieren?** (cg\_contest)
  - **Was diese Einstellung bewirkt:** Aktiviert Funktionen, die die Durchführung eines Fotowettbewerbs unterstützen, wie z. B. die Anzeige von Gewinnern oder spezifischen Wettbewerbsregeln.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Zusätzliche wettbewerbsbezogene Optionen oder Anzeigen können erscheinen.
    - *Wenn deaktiviert:* Standard-Galerieverhalten.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie führen aktiv einen Wettbewerb durch)
  - **Händlerszenario / Beispiel:** Wenn Sie einen „Bestes Foto“-Wettbewerb veranstalten möchten, aktivieren Sie diese Option, um die Wettbewerbsfunktionen des Moduls zu nutzen.

#### Front-Office-Anzeigeorte

Diese Einstellungen steuern, wo die Kundenfotogalerie und die Upload-Optionen in Ihrem Shop angezeigt werden.

- **Upload-Formular auf Produktseite anzeigen?** (CG\_FUPLOADON)
  - **Was diese Einstellung bewirkt:** Legt fest, ob das Foto-Upload-Formular direkt auf der Produktseite sichtbar ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden sehen ein Formular zum Hochladen von Fotos direkt auf der Produktseite.
    - *Wenn deaktiviert:* Das Upload-Formular erscheint nicht auf der Produktseite; Kunden müssen möglicherweise zu ihrem Konto oder einer dedizierten Galerieseite gehen, um hochzuladen.
  - **Empfohlener Wert:** JA (für maximale Bequemlichkeit und Inhaltserstellung)
  - **Händlerszenario / Beispiel:** Das leicht zugängliche Upload-Formular auf der Produktseite ermutigt mehr Kunden, ihre Fotos direkt nach dem Ansehen des Produkts zu teilen.
- **Galerie auf Produktseite als Tab anzeigen?** (CG\_PRODUCTTAB, cg\_productTabM)
  - **Was diese Einstellung bewirkt:** Integriert die Kundenfotogalerie als neuen Tab auf der Produktseite (z. B. neben „Beschreibung“ oder „Datenblatt“).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein neuer Tab erscheint auf den Produktseiten und zeigt Kundenfotos für dieses spezifische Produkt an.
    - *Wenn deaktiviert:* Die Galerie erscheint nicht als Tab.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Dies ist eine sehr prominente und effektive Möglichkeit, benutzergenerierte Inhalte anzuzeigen, wodurch sie für Käufer leicht auffindbar sind.
- **Galerie auf Produktseite im Footer anzeigen?** (CG\_PRODUCTFOOTER)
  - **Was diese Einstellung bewirkt:** Zeigt einen Bereich mit Kundenfotos im Footer-Bereich der Produktseite an.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Block mit Kundenfotos erscheint unterhalb des Hauptproduktinhalts.
    - *Wenn deaktiviert:* Es erscheinen keine Fotos im Produktseiten-Footer.
  - **Empfohlener Wert:** JA (als zusätzlicher Anzeigepunkt)
  - **Händlerszenario / Beispiel:** Dies bietet eine weitere Möglichkeit, Kundenfotos zu präsentieren, ohne den Hauptproduktinformationsbereich zu überladen.
- **Galerie im Kundenkonto anzeigen?** (CG\_CUSTOMERACCOUNT, CG\_CUSTOMERACCOUNTV)
  - **Was diese Einstellung bewirkt:** Erstellt einen dedizierten Bereich „Meine Fotos“ innerhalb des persönlichen Kontobereichs des Kunden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Angemeldete Kunden sehen einen neuen Link und eine Seite in ihrem Konto, um ihre hochgeladenen Fotos zu verwalten.
    - *Wenn deaktiviert:* Kunden können ihre Fotos nicht über ihr Konto verwalten.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Wesentlich für Kunden, um ihre Beiträge anzuzeigen und zu verwalten, was ein Gefühl der Eigenverantwortung und Gemeinschaft fördert.
- **Link zur Galerie im „Mein Konto“-Block anzeigen?** (CG\_MYACCOUNTBLOCK, CG\_MYACCOUNTBLOCKV)
  - **Was diese Einstellung bewirkt:** Fügt einen Link zum Bereich „Meine Fotos“ (oder zur Hauptgalerie) im „Mein Konto“-Block hinzu, der oft in der linken oder rechten Spalte oder im Footer zu finden ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Schnelllink erscheint für eingeloggte Benutzer.
    - *Wenn deaktiviert:* Der Link ist im Block nicht vorhanden.
  - **Empfohlener Wert:** JA (für einfache Navigation)
  - **Händlerszenario / Beispiel:** Macht es Kunden sehr einfach, von fast jeder Seite auf ihre Fotogalerie zuzugreifen oder neue Fotos hochzuladen.
- **Galerie in der rechten Spalte anzeigen?** (CG\_RIGHTCOL)
  - **Was diese Einstellung bewirkt:** Zeigt einen Block mit Kundenfotos in der rechten Spalte Ihres Shops an.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein dynamischer Block mit Fotos erscheint in der rechten Seitenleiste.
    - *Wenn deaktiviert:* Es erscheinen keine Fotos in der rechten Spalte.
  - **Empfohlener Wert:** NEIN (kann ablenkend sein, nur in Betracht ziehen, wenn Ihr Theme ausreichend Platz bietet)
  - **Händlerszenario / Beispiel:** Nützlich, wenn Sie ein breites Layout haben und Kundeninhalte ständig präsentieren möchten, kann aber manchmal die Seite überladen.
- **Galerie in der linken Spalte anzeigen?** (CG\_LEFTCOL)
  - **Was diese Einstellung bewirkt:** Zeigt einen Block mit Kundenfotos in der linken Spalte Ihres Shops an.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein dynamischer Block mit Fotos erscheint in der linken Seitenleiste.
    - *Wenn deaktiviert:* Es erscheinen keine Fotos in der linken Spalte.
  - **Empfohlener Wert:** NEIN (ähnlich wie rechte Spalte, sparsam verwenden)
  - **Händlerszenario / Beispiel:** Ähnlich wie bei der rechten Spalte, verwenden Sie diese Option, wenn Ihr Theme-Design dies zulässt, ohne die Lesbarkeit zu beeinträchtigen.
- **Galerie auf der Startseite anzeigen?** (CG\_GALLERY, cg\_hpg\_nb, cg\_hpg\_o)
  - **Was diese Einstellung bewirkt:** Zeigt eine Auswahl von Kundenfotos direkt auf der Startseite Ihres Shops an. Möglicherweise haben Sie auch Optionen zur Steuerung der Anzahl der Fotos (cg\_hpg\_nb) und deren Reihenfolge (cg\_hpg\_o).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Bereich mit Kundenfotos erscheint auf der Startseite.
    - *Wenn deaktiviert:* Es werden keine Kundenfotos auf der Startseite angezeigt.
  - **Empfohlener Wert:** JA (sehr empfehlenswert für Engagement)
  - **Händlerszenario / Beispiel:** Die Startseite ist eine erstklassige Immobilie. Die Präsentation von Kundenfotos hier vermittelt neuen Besuchern sofort Vertrauen und Gemeinschaft.
- **Bestimmte Produkte von der Galerie ausschließen?** (cg\_excludeproduct)
  - **Was diese Einstellung bewirkt:** Ermöglicht die Angabe von Produkt-IDs, für die keine Kundenfotos angezeigt oder hochgeladen werden sollen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn Produkt-ID 123 eingegeben wird:* Produkt 123 zeigt keine Kundenfotos an, und Uploads dafür werden deaktiviert.
    - *Wenn leer gelassen:* Alle Produkte sind für Kundenfotos berechtigt.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben sensible oder nicht-visuelle Produkte.
  - **Händlerszenario / Beispiel:** Wenn Sie digitale Produkte oder Dienstleistungen verkaufen, die keine visuelle Komponente haben, oder Produkte, für die Sie keine benutzergenerierten Inhalte wünschen, können Sie diese hier ausschließen.

#### Benachrichtigungen & Updates

- **E-Mail-Benachrichtigungen für neue Uploads aktivieren?** (CG\_NTF)
  - **Was diese Einstellung bewirkt:** Sendet eine E-Mail-Benachrichtigung an den Shop-Administrator, sobald ein neues Kundenfoto hochgeladen wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Sie erhalten eine E-Mail für jeden neuen Upload, sodass Sie schnell moderieren können.
    - *Wenn deaktiviert:* Es werden keine E-Mail-Benachrichtigungen gesendet.
  - **Empfohlener Wert:** JA (wesentlich für Moderation und Qualitätskontrolle)
  - **Händlerszenario / Beispiel:** Das Verfolgen neuer Uploads hilft Ihnen sicherzustellen, dass alle Inhalte angemessen und hochwertig sind, bevor sie weithin sichtbar sind.
- **MyPresta.eu Updates** (mypresta\_updates, update\_, updatev\_)
  - **Was diese Einstellung bewirkt:** Dies ist eine Standardeinstellung in MyPresta.eu-Modulen, um nach verfügbaren Updates zu suchen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul sucht regelmäßig auf MyPresta.eu nach neuen Versionen.
    - *Wenn deaktiviert:* Das Modul sucht nicht automatisch nach Updates.
  - **Empfohlener Wert:** JA (immer auf dem neuesten Stand bleiben für Sicherheit und Funktionen)
  - **Händlerszenario / Beispiel:** Wenn diese Option aktiviert bleibt, werden Sie über neue Funktionen, Fehlerbehebungen und Sicherheitspatches benachrichtigt, wodurch Ihr Shop aktuell und sicher bleibt.

#### Interne/Erweiterte Einstellungen (Normalerweise als Standard belassen)

- **CG\_LAST\_TAB**: Interne Einstellung, um den zuletzt aktiven Tab in der Modulkonfiguration zu speichern.
- **cg\_altered1, cg\_altered2**: Interne Flags, die normalerweise mit Modul-Updates oder Datenmigrationen zusammenhängen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | JPEG-Dateien zulassen? | JA | Ermöglicht Kunden das Hochladen von JPEG-Bildern. |
| Modulkonfiguration | GIF-Dateien zulassen? | JA | Ermöglicht Kunden das Hochladen von GIF-Bildern. |
| Modulkonfiguration | PNG-Dateien zulassen? | JA | Ermöglicht Kunden das Hochladen von PNG-Bildern. |
| Modulkonfiguration | BMP-Dateien zulassen? | NEIN | Verbietet große, unkomprimierte BMP-Bilder. |
| Modulkonfiguration | Nicht eingeloggten Kunden das Hochladen von Fotos erlauben? | JA / NEIN (Händlerwahl) | Steuert Gast-Uploads. |
| Modulkonfiguration | Maximale Dateigröße (in MB) | 2-5 MB | Begrenzt die Upload-Größe, um große Dateien zu verhindern. |
| Modulkonfiguration | Miniaturbildhöhe (px) | 150-250px | Legt eine konsistente Höhe für Galerie-Miniaturbilder fest. |
| Modulkonfiguration | Miniaturbildbreite (px) | 150-250px | Legt eine konsistente Breite für Galerie-Miniaturbilder fest. |
| Modulkonfiguration | Fotos pro Seite in der Galerie | 12-24 | Steuert die Paginierung für die Hauptgalerie. |
| Modulkonfiguration | Abstimmung für Fotos aktivieren? | JA | Ermöglicht Kunden, über Fotos abzustimmen. |
| Modulkonfiguration | Nicht eingeloggten Kunden das Abstimmen erlauben? | NEIN | Verhindert Spam-/Bot-Abstimmungen. |
| Modulkonfiguration | Abstimmungsstil | Goldene Sterne | Legt den visuellen Stil für Abstimmungssymbole fest. |
| Modulkonfiguration | Wettbewerbsmodus aktivieren? | NEIN | Aktiviert wettbewerbsspezifische Funktionen. |
| Modulkonfiguration | Upload-Formular auf Produktseite anzeigen? | JA | Zeigt das Upload-Formular direkt auf Produktseiten an. |
| Modulkonfiguration | Galerie auf Produktseite als Tab anzeigen? | JA | Fügt einen dedizierten Tab für Fotos auf Produktseiten hinzu. |
| Modulkonfiguration | Galerie auf Produktseite im Footer anzeigen? | JA | Zeigt Fotos unterhalb des Produktinhalts an. |
| Modulkonfiguration | Galerie im Kundenkonto anzeigen? | JA | Erstellt einen Bereich „Meine Fotos“ in Kundenkonten. |
| Modulkonfiguration | Link zur Galerie im „Mein Konto“-Block anzeigen? | JA | Fügt einen Schnelllink zur Galerie im „Mein Konto“-Block hinzu. |
| Modulkonfiguration | Galerie in der rechten Spalte anzeigen? | NEIN | Zeigt Fotos in der rechten Seitenleiste an. |
| Modulkonfiguration | Galerie in der linken Spalte anzeigen? | NEIN | Zeigt Fotos in der linken Seitenleiste an. |
| Modulkonfiguration | Galerie auf der Startseite anzeigen? | JA | Zeigt Fotos auf der Startseite des Shops an. |
| Modulkonfiguration | Bestimmte Produkte von der Galerie ausschließen? | Leer lassen | Verhindert Fotos für angegebene Produkte. |
| Modulkonfiguration | E-Mail-Benachrichtigungen für neue Uploads aktivieren? | JA | Sendet dem Administrator eine E-Mail bei neuen Foto-Uploads. |
| Modulkonfiguration | MyPresta.eu Updates | JA | Aktiviert automatische Update-Prüfungen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Kundenfotos werden nach dem Hochladen nicht angezeigt, oder die Galerie sieht leer aus.**
**A1:**

- **Modulkonfiguration prüfen:** Stellen Sie sicher, dass die Anzeigeoptionen (z. B. „Galerie auf Produktseite als Tab anzeigen?“, „Galerie auf der Startseite anzeigen?“) in den Moduleinstellungen aktiviert sind.
- **Cache leeren:** PrestaShop verwendet Caching. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ und „Cache leeren“, falls separate Optionen vorhanden sind). Dies behebt oft Anzeigeprobleme.
- **Bildmoderation:** Einige Module haben einen Genehmigungsprozess. Prüfen Sie, ob es einen Admin-Bereich gibt (obwohl dieses Modul keinen dedizierten Admin-Controller hat, könnte es einen internen Genehmigungsstatus geben), in dem Fotos genehmigt werden müssen, bevor sie live gehen.
- **Dateiberechtigungen:** Stellen Sie sicher, dass Ihr Ordner `img/customersgallery` (oder ein ähnlicher Pfad, in dem Bilder gespeichert werden) die richtigen Schreibberechtigungen hat (normalerweise 755 oder 775). Ihr Hosting-Anbieter kann Ihnen dabei helfen.

**F2: Kunden haben Probleme beim Hochladen von Fotos oder erhalten eine Fehlermeldung.**
**A2:**

- **Dateityp- und Größenbeschränkungen prüfen:** Überprüfen Sie die Einstellungen „JPEG/GIF/PNG/BMP-Dateien zulassen?“ und „Maximale Dateigröße (in MB)“ in der Modulkonfiguration. Stellen Sie sicher, dass die Datei des Kunden den zulässigen Typen entspricht und innerhalb der Größenbeschränkung liegt.
- **Server-PHP-Limits:** Auch wenn das Modul eine große Dateigröße zulässt, kann die PHP-Konfiguration Ihres Servers (z. B. `upload_max_filesize`, `post_max_size` in `php.ini`) eine strengere Begrenzung auferlegen. Wenden Sie sich an Ihren Hosting-Anbieter, um diese Limits zu überprüfen und bei Bedarf zu erhöhen.
- **Browser-Kompatibilität:** Bitten Sie den Kunden, einen anderen Browser zu verwenden oder den Browser-Cache zu leeren.
- **JavaScript-Fehler:** Öffnen Sie die Entwicklerkonsole Ihres Browsers (F12) und suchen Sie während des Upload-Vorgangs nach JavaScript-Fehlern. Dies könnte auf einen Konflikt mit einem anderen Modul oder Theme hinweisen.

**F3: Die Kundenfotos sehen in der Galerie verzerrt oder falsch skaliert aus.**
**A3:**

- **Miniaturbild-Dimensionen:** Passen Sie die Einstellungen „Miniaturbildhöhe (px)“ und „Miniaturbildbreite (px)“ in der Modulkonfiguration an. Experimentieren Sie mit verschiedenen Werten, um herauszufinden, was am besten zu Ihrem Theme passt. Denken Sie daran, Ihren PrestaShop-Cache nach Änderungen zu leeren.
- **CSS-Konflikte:** Das CSS Ihres Themes könnte das Styling des Moduls überschreiben. Verwenden Sie die Entwicklertools Ihres Browsers (F12), um die Elemente zu überprüfen und widersprüchliche CSS-Regeln zu identifizieren. Möglicherweise benötigen Sie einen Webmaster, um benutzerdefiniertes CSS zu Ihrem Theme hinzuzufügen, um dies zu korrigieren.

**F4: Der Link „Meine Fotos“ wird im Kundenkonto oder im „Mein Konto“-Block nicht angezeigt.**
**A4:**

- **Modul-Hooking:** Stellen Sie sicher, dass das Modul korrekt an `displayCustomerAccount` und `displayMyAccountBlock` (oder `displayMyAccountBlockFooter`, je nach Ihrem Theme) gehookt ist. Sie können dies unter **Design > Positionen** (oder **Module > Positionen** in älteren Versionen) überprüfen und nach dem Modul suchen. Wenn es nicht gehookt ist, versuchen Sie, das Modul neu zu installieren oder manuell zu hooken.
- **Modulkonfiguration:** Überprüfen Sie nochmals, ob „Galerie im Kundenkonto anzeigen?“ und „Link zur Galerie im ‚Mein Konto‘-Block anzeigen?“ in den Moduleinstellungen aktiviert sind.
- **Kundenanmeldung:** Der Link „Meine Fotos“ ist nur für eingeloggte Kunden sichtbar. Stellen Sie sicher, dass Sie angemeldet sind, wenn Sie testen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick über das Modul „Kundenproduktfotos“, der für Entwickler und Webmaster gedacht ist, die seine interne Funktionsweise verstehen, sein Verhalten anpassen oder fortgeschrittene Probleme beheben müssen.

### 4.1 Architekturübersicht

Das Modul „Kundenproduktfotos“ folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich Front Controller für die Benutzerinteraktion und Smarty-Templates für die Darstellung nutzt. Es verwendet die Hauptmodulklasse (`customersgallery.php`) für die Konfigurationsverwaltung und Hook-Registrierung. Obwohl es `ObjectModel` nicht für seine Kerndaten erweitert, interagiert es direkt mit der Datenbank zur Speicherung von Fotometadaten und verlässt sich auf das PrestaShop-Dateisystem für die Bildspeicherung. AJAX wird intensiv für das dynamische Laden von Inhalten und Foto-Uploads verwendet, um eine reibungslose Benutzererfahrung ohne vollständige Seitenneuladungen zu gewährleisten.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Diese Controller verwalten alle kundenorientierten Interaktionen, einschließlich der Anzeige von Galerien, der Verwaltung von Benutzerfotos und der Verarbeitung von AJAX-Anfragen.

- **`controllers/front/ajax.php`**
  - **Klassenname:** `CustomersGalleryAjaxModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Dies ist der primäre Endpunkt für alle asynchronen (AJAX) Operationen. Er verarbeitet:
    - Foto-Uploads von der Produktseite oder dem Kundenkonto.
    - Abstimmungsaktionen (Fotos liken/bewerten).
    - Potenziell Bildlösch- oder Moderationsanfragen aus dem Bereich „Meine Fotos“ des Kunden.
    - Gibt JSON-Antworten zurück, die Erfolg oder Misserfolg sowie relevante Daten anzeigen.
- **`controllers/front/gallery.php`**
  - **Klassenname:** `CustomersGalleryGalleryModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Rendert die Haupt-, dedizierte Kundenfotogalerie-Seite. Diese Seite zeigt typischerweise alle genehmigten Kundenfotos an, möglicherweise mit Paginierung und Filteroptionen. Sie ruft Fotodaten aus der Datenbank ab und weist sie dem `gallery.tpl`-Template zu.
- **`controllers/front/index.php`**
  - **Klassenname:** `CustomersGalleryIndexModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Dieser Controller dient wahrscheinlich als Standard- oder Fallback-Einstiegspunkt für die Front-Office-Routen des Moduls. Er könnte bei direktem Zugriff ohne spezifische Parameter zur Hauptgalerie oder zum `myphotos`-Controller weiterleiten.
- **`controllers/front/myphotos.php`**
  - **Klassenname:** `CustomersGalleryMyPhotosModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Verwaltet den Bereich „Meine Fotos“ innerhalb des Kundenkontos. Er zeigt Fotos an, die vom aktuell angemeldeten Kunden hochgeladen wurden, ermöglicht es ihnen, ihre eigenen Fotos zu verwalten (z. B. zu löschen) und bietet möglicherweise eine Upload-Schnittstelle. Er erfordert eine Kundenauthentifizierung.
- **`controllers/front/myvideos.php`**
  - **Klassenname:** `CustomersGalleryMyVideosModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Obwohl der Modulname „Kundenproduktfotos“ lautet, deutet dieser Controller auf eine potenzielle (oder geplante) Funktion für Kunden-Video-Uploads hin. Er würde wahrscheinlich ähnlich wie `myphotos.php` funktionieren, jedoch für Videoinhalte.

#### Back-Office-Admin-Controller

Das Modul verfügt über keine dedizierten Admin-Controller. Die gesamte Konfiguration wird über die `getContent()`-Methode des Hauptmoduls verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul scheint keine benutzerdefinierten Klassen zu definieren, die `ObjectModel` in einem dedizierten `classes/`-Verzeichnis erweitern. Die gesamte Kernlogik für Datenbankinteraktion, Bildverarbeitung und Geschäftsregeln ist wahrscheinlich in der Hauptdatei `customersgallery.php` und den Front-Controllern gekapselt. Dies bedeutet, dass Datenbankoperationen direkt über `Db::getInstance()`-Aufrufe abgewickelt werden.

### 4.4 JavaScript-Assets (`views/js/`)

- **`customersgallery/js/customersgallery.js`**
  - **Geltungsbereich:** Front-Office
  - **Details:** Dies ist das primäre benutzerdefinierte JavaScript für das Modul. Es verarbeitet wahrscheinlich:
    - AJAX-Aufrufe für Foto-Uploads (z. B. Bindung an Formularübermittlungen).
    - AJAX-Aufrufe für Abstimmungsmechanismen.
    - Dynamisches Laden von Galerieinhalten.
    - Clientseitige Validierung für Dateitypen und -größen vor dem Upload.
    - Interaktion mit der Fancybox-Bibliothek für Bild-Lightboxes.
    - Event-Listener für Paginierung, Filterung und andere Galerie-Interaktionen.
- **`customersgallery/js/fancybox.js`**
  - **Geltungsbereich:** Front-Office
  - **Details:** Dies ist eine Drittanbieterbibliothek (Fancybox), die verwendet wird, um Bilder in einem responsiven, eleganten Lightbox-Overlay anzuzeigen, wenn ein Benutzer auf ein Miniaturbild klickt. Sie verwaltet Bildzoom, Navigation zwischen Galeriebildern und die modale Präsentation.
- **`customersgallery/js/script.js`**
  - **Geltungsbereich:** Front-Office
  - **Details:** Dies könnte ein ergänzendes Skript sein, möglicherweise für allgemeine UI-Verbesserungen, spezifische Animationen oder zusätzliche Ereignisbehandlung, die nicht von `customersgallery.js` abgedeckt wird. Es könnte auch Initialisierungsroutinen für andere JS-Komponenten enthalten.
- **`customersgallery/lib/voucherengine/script.js`**
  - **Geltungsbereich:** Front-Office (potenziell)
  - **Details:** Das Vorhandensein von `voucherengine` deutet auf eine potenzielle Integration oder eine separate Funktion zur Generierung/Verwaltung von Gutscheinen hin, möglicherweise als Belohnung für Foto-Uploads oder die Teilnahme an Wettbewerben. Dieses Skript würde die clientseitige Logik für ein solches System verwalten.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`customersgallery/css/customersgallery.css`**
  - **Geltungsbereich:** Front-Office-Kundenstyling
  - **Details:** Dies ist das Haupt-Stylesheet für die Front-Office-Komponenten des Moduls. Es stylt:
    - Das Layout der Fotogalerie (Raster, Flexbox).
    - Einzelne Fotocontainer und Miniaturbilder.
    - Upload-Formulare und Schaltflächen.
    - Paginierungssteuerungen.
    - Abstimmungselemente (falls nicht durch spezifisches Stern-CSS behandelt).
    - Responsive Anpassungen für verschiedene Bildschirmgrößen.
  - **Wichtige CSS-Klassenselektoren:** `.customer-photo-gallery`, `.cg-item`, `.cg-thumbnail`, `.cg-upload-form`, `.cg-vote-stars`
- **`customersgallery/css/fancybox.css`**
  - **Geltungsbereich:** Front-Office-Kundenstyling
  - **Details:** Stylesheet für die Fancybox-Lightbox-Bibliothek, das sicherstellt, dass das Bild-Overlay, die Navigationspfeile, die Schließen-Schaltfläche und die Bildunterschriften visuell konsistent und ansprechend sind.
- **`customersgallery/css/star-black.css`, `star-blue.css`, `star-gold.css`, `star-pink.css`, `star-red.css`, `star-whitered.css`, `star.css`**
  - **Geltungsbereich:** Front-Office-Kundenstyling
  - **Details:** Dies sind spezifische Stylesheets für das sternbasierte Abstimmungssystem. Jede Datei bietet ein anderes Farbschema oder einen anderen visuellen Stil für die Sternsymbole, sodass der Händler ein Design wählen kann, das zu seinem Theme passt. `star.css` ist wahrscheinlich das Basis-Styling, wobei die anderen Farbübersteuerungen bereitstellen.
- **`customersgallery/lib/voucherengine/ps16.css`**
  - **Geltungsbereich:** Front-Office (potenziell)
  - **Details:** Dieses Stylesheet, das sich im Verzeichnis `voucherengine` befindet, deutet auf ein Styling speziell für die Gutschein-bezogenen Funktionen hin, möglicherweise optimiert für PrestaShop 1.6-Themes, aber wahrscheinlich kompatibel oder anpassbar für neuere Versionen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

Diese Templates sind so konzipiert, dass sie gerendert werden, wenn bestimmte PrestaShop-Hooks ausgeführt werden, wodurch der Inhalt des Moduls in verschiedene Teile des Shops integriert wird.

- **`customersgallery/views/templates/hook/column-link.tpl`**
  - **Hook:** `displayLeftColumn`, `displayRightColumn`
  - **Ausgabe:** Ein Link oder Block, der Benutzer zur Hauptkundenfotogalerie oder zu ihrem Bereich „Meine Fotos“ leitet, typischerweise in den Seitenleisten platziert.
- **`customersgallery/views/templates/hook/customer-my-account.tpl`**
  - **Hook:** `displayCustomerAccount`
  - **Ausgabe:** Ein Link oder Block innerhalb der Seite „Mein Konto“ des Kunden, der zu seinem dedizierten Bereich „Meine Fotos“ führt.
- **`customersgallery/views/templates/hook/hookHome.tpl`**
  - **Hook:** `displayHome`
  - **Ausgabe:** Ein Block oder Abschnitt, der eine Auswahl von Kundenfotos auf der Startseite des Shops anzeigt, oft mit den neuesten oder beliebtesten Uploads.
- **`customersgallery/views/templates/hook/my-account.tpl`**
  - **Hook:** `displayMyAccountBlock`, `displayMyAccountBlockFooter`
  - **Ausgabe:** Ein Link zum Bereich „Meine Fotos“, integriert in den Standard-Block „Mein Konto“, der in Spalten oder im Footer für eingeloggte Benutzer erscheint.
- **`customersgallery/views/templates/hook/productfooter.tpl`**
  - **Hook:** `displayProductFooter`, `displayProductExtraContent`
  - **Ausgabe:** Ein Abschnitt, der Kundenfotos für das aktuelle Produkt anzeigt, unterhalb des Hauptproduktinhalts auf der Produktseite.
- **`customersgallery/views/templates/hook/tab.tpl`**
  - **Hook:** `displayProductTab`
  - **Ausgabe:** Der HTML-Code für einen neuen Tab-Header (z. B. „Kundenfotos“), der auf der Produktseite erscheint.
- **`customersgallery/views/templates/hook/tabContents.tpl`**
  - **Hook:** `displayProductTabContent`
  - **Ausgabe:** Der tatsächliche Inhalt, der angezeigt wird, wenn der Tab „Kundenfotos“ auf der Produktseite aktiv ist, und die Galerie sowie möglicherweise das Upload-Formular für dieses spezifische Produkt anzeigt.

#### Benutzerdefinierte Templates (`views/templates/custom/`)

Diese Templates werden wahrscheinlich für spezifische Formulare oder Teile des Upload-Prozesses verwendet.

- **`customersgallery/views/templates/custom/upload-form.tpl`**
  - **Zweck:** Rendert das HTML-Formular, das Kunden zum Hochladen ihrer Produktfotos verwenden. Dies könnte eine einfachere Version oder eine ältere Iteration sein.
- **`customersgallery/views/templates/custom/upload-form2.tpl`**
  - **Zweck:** Wahrscheinlich eine aktualisierte oder alternative Version des Upload-Formulars, möglicherweise mit unterschiedlichem Styling, Funktionen oder Kompatibilität für neuere PrestaShop-Versionen.

#### Front-Office-Templates (`views/templates/front/`)

Diese Templates werden typischerweise von den Front-Controllern des Moduls verwendet, um vollständige Seiten oder bedeutende Abschnitte der Modulfunktionalität zu rendern.

- **`customersgallery/views/templates/front/gallery.tpl`**
  - **Zweck:** Das Haupttemplate für die dedizierte Kundenfotogalerie-Seite, die alle Fotos mit Paginierung anzeigt.
- **`customersgallery/views/templates/front/gallery2.tpl`**
  - **Zweck:** Eine alternative oder aktualisierte Version des Hauptgalerie-Templates, die möglicherweise unterschiedliche Layouts oder Funktionen bietet.
- **`customersgallery/views/templates/front/gallery3.tpl`**
  - **Zweck:** Eine weitere alternative oder aktualisierte Version des Hauptgalerie-Templates. Das Modul könnte je nach Konfiguration oder PrestaShop-Version zwischen diesen wechseln.
- **`customersgallery/views/templates/front/menu.tpl`**
  - **Zweck:** Rendert ein Navigationsmenü, das spezifisch für die Kundenfotogalerie ist, möglicherweise zum Filtern, Sortieren oder Navigieren zwischen „Meine Fotos“ und der Hauptgalerie.
- **`customersgallery/views/templates/front/my-photos.tpl`**
  - **Zweck:** Rendert die Seite „Meine Fotos“ innerhalb des Kundenkontos, die die hochgeladenen Bilder und Verwaltungsoptionen des Kunden anzeigt.
- **`customersgallery/views/templates/front/my-videos-16.tpl`**
  - **Zweck:** Template für den Bereich „Meine Videos“, speziell für PrestaShop 1.6 entworfen oder optimiert, falls die Video-Upload-Funktion aktiviert ist.
- **`customersgallery/views/templates/front/video-upload.tpl`**
  - **Zweck:** Rendert das Formular für Kunden zum Hochladen von Videos, falls diese Funktion aktiv ist.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul definiert keine expliziten benutzerdefinierten SQL-Dateien, aber basierend auf seiner Funktionalität wird es mit der Datenbank interagieren.

- **Benutzerdefinierte Tabellen (wahrscheinlich während `install()` erstellt):**
  - `_customersgallery`: Speichert Metadaten für jedes hochgeladene Foto (z. B. `id_customersgallery`, `id_customer`, `id_product`, `filename`, `date_add`, `approved`, `votes`, `active`).
  - `_customersgallery_vote`: Speichert Datensätze von Kundenstimmen (z. B. `id_customersgallery_vote`, `id_customersgallery`, `id_customer`, `ip_address`, `date_add`).
- **Konfigurationsdatensätze (gespeichert in `ps_configuration`):**
  - `CG_LAST_TAB`, `CG_ALLOW_JPEG`, `CG_ALLOW_GIF`, `CG_ALLOW_PNG`, `CG_ALLOW_BMP`, `mypresta_updates`, `CG_PAGINATION`, `CG_ALLOW_UNLOGGED`, `CG_MAX_FILE_SIZE`, `CG_PRODUCTTAB`, `cg_productTabM`, `CG_PRODUCTFOOTER`, `CG_CUSTOMERACCOUNT`, `CG_MYACCOUNTBLOCK`, `CG_THUMBHEIGHT`, `CG_THUMBWIDTH`, `CG_FUPLOADON`, `CG_GALLERY`, `CG_RIGHTCOL`, `CG_LEFTCOL`, `CG_NTF`, `update_`, `updatev_`, `cg_altered1`, `cg_altered2`, `cg_hpg_nb`, `cg_hpg_o`, `cg_contest`, `cg_excludeproduct`, `CG_CUSTOMERACCOUNTV`, `CG_MYACCOUNTBLOCKV`, `CG_voting`, `CG_VOTE_STAR`, `CGV_voting`, `cg_unl_voting`.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Fügt CSS- und JavaScript-Assets ein, die vom Modul benötigt werden (z. B. `customersgallery.css`, `fancybox.js`, `customersgallery.js`). |
| `displayMyAccountBlock` | Im „Mein Konto“-Block des Kunden (oft in der linken/rechten Spalte oder im Footer). | Fügt einen Link zum Bereich „Meine Fotos“ des Kunden hinzu. |
| `displayLeftColumn` | In der linken Seitenleiste des Shops. | Zeigt einen Block mit Kundenfotos oder einen Link zur Galerie an. |
| `displayRightColumn` | In der rechten Seitenleiste des Shops. | Zeigt einen Block mit Kundenfotos oder einen Link zur Galerie an. |
| `displayHome` | Auf der Startseite des Shops. | Zeigt einen Abschnitt mit Kundenfotos (neueste, beliebteste) an. |
| `displayProductTab` | Auf der Produktseite, zum Hinzufügen neuer Tabs. | Fügt den Tab-Header „Kundenfotos“ hinzu. |
| `displayProductTabContent` | Auf der Produktseite, für den Inhalt eines Tabs. | Zeigt die Kundenfotogalerie und das Upload-Formular innerhalb des Tabs „Kundenfotos“ an. |
| `displayProductFooter` | Am unteren Rand der Produktseite. | Zeigt einen Abschnitt mit Kundenfotos für das aktuelle Produkt an. |
| `displayProductExtraContent` | Ein weiterer Hook für zusätzliche Inhalte auf der Produktseite. | Kann als alternative oder zusätzliche Platzierung für produktspezifische Fotoinhalte verwendet werden. |
| `displayCustomerAccount` | Auf der Seite „Mein Konto“ des Kunden. | Fügt einen Link zum Bereich „Meine Fotos“ für den angemeldeten Kunden hinzu. |
| `displayLeftColumnProduct` | In der linken Spalte speziell auf Produktseiten. | Zeigt einen Block mit Kundenfotos oder einen Link zur Galerie auf Produktseiten an. |
| `displayRightColumnProduct` | In der rechten Spalte speziell auf Produktseiten. | Zeigt einen Block mit Kundenfotos oder einen Link zur Galerie auf Produktseiten an. |
| `displayMyAccountBlockFooter` | In der Footer-Version des „Mein Konto“-Blocks. | Fügt einen Link zum Bereich „Meine Fotos“ des Kunden im Footer hinzu. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | (Potenziell) Könnte verwendet werden, um eine E-Mail an den Kunden auszulösen, die zum Hochladen von Fotos für gekaufte Produkte anregt. |

## 5. Offizieller Support & Updates

Für offiziellen Support, Modul-Updates und weitere Unterstützung bezüglich des Moduls „Kundenproduktfotos“ wenden Sie sich bitte an Ihr MyPresta.eu-Kundenkonto. Sie können sich unter [MyPresta.eu Bestellhistorie & Downloads](https://mypresta.eu/my-account/orders/) anmelden, um auf die neuesten Versionen zuzugreifen und Support-Tickets einzureichen.
