---
title: "Kunden-Fotogalerie – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Kunden-Fotogalerie von MyPresta.eu."
sidebar:
  label: "Kunden-Fotogalerie – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Customer Photo Gallery auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/customer-photo-gallery.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/customer-photo-gallery/)
>
> ---


# Kunden-Fotogalerie

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst und alle Modulinteraktionen erforderlich. Stellen Sie sicher, dass Ihr Server über ausreichend Speicherplatz verfügt, um hochgeladene Fotos und Videos zu speichern.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul Kunden-Fotogalerie, auf dem Sie alle Funktionen und deren Darstellung in Ihrem Shop steuern.

| Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- |
| **JPEG-Uploads zulassen** | JA | **Was diese Einstellung bewirkt:** Steuert, ob Kunden Bilder im JPEG-Format hochladen können.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Kunden können .jpg- und .jpeg-Dateien hochladen.   *Wenn deaktiviert:* JPEG-Dateien werden beim Hochladen abgelehnt.   **Empfohlener Wert:** JA (JPEG ist ein sehr gängiges Bildformat).   **Händlerszenario:** Wenn Sie Bildtypen aus bestimmten Qualitäts- oder Branding-Gründen einschränken möchten, könnten Sie einige Formate deaktivieren. |
| **GIF-Uploads zulassen** | JA | **Was diese Einstellung bewirkt:** Steuert, ob Kunden Bilder im GIF-Format hochladen können.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Kunden können .gif-Dateien hochladen.   *Wenn deaktiviert:* GIF-Dateien werden abgelehnt.   **Empfohlener Wert:** JA (GIFs können für einfache Animationen oder transparente Hintergründe nützlich sein). |
| **PNG-Uploads zulassen** | JA | **Was diese Einstellung bewirkt:** Steuert, ob Kunden Bilder im PNG-Format hochladen können.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Kunden können .png-Dateien hochladen.   *Wenn deaktiviert:* PNG-Dateien werden abgelehnt.   **Empfohlener Wert:** JA (PNG ist hervorragend für Bilder mit Transparenz und hoher Qualität). |
| **BMP-Uploads zulassen** | NEIN | **Was diese Einstellung bewirkt:** Steuert, ob Kunden Bilder im BMP-Format hochladen können.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Kunden können .bmp-Dateien hochladen.   *Wenn deaktiviert:* BMP-Dateien werden abgelehnt.   **Empfohlener Wert:** NEIN (BMP-Dateien sind typischerweise sehr groß und unkomprimiert, nicht ideal für die Webnutzung).   **Händlerszenario:** Nur aktivieren, wenn Sie einen spezifischen Bedarf an unkomprimierten Bildern haben, aber beachten Sie die Auswirkungen auf den Serverspeicher und die Seitenladezeiten. |
| **Paginierung aktivieren** | JA | **Was diese Einstellung bewirkt:** Legt fest, ob die Galerieseiten eine Paginierung verwenden (z. B. „Seite 1 von 5“).   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Galerieinhalte werden auf mehrere Seiten aufgeteilt, was die Ladezeiten für große Galerien verbessert.   *Wenn deaktiviert:* Alle Galerieinhalte werden auf einer einzigen Seite geladen, was bei vielen Fotos langsam sein kann.   **Empfohlener Wert:** JA.   **Händlerszenario:** Wesentlich für die Verwaltung großer Galerien und ein reibungsloses Benutzererlebnis. |
| **Nicht angemeldeten Benutzern das Hochladen erlauben** | NEIN | **Was diese Einstellung bewirkt:** Ermöglicht Besuchern, die nicht in einem Kundenkonto angemeldet sind, Fotos hochzuladen.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Gäste können Fotos hochladen. Dies kann die Beiträge erhöhen, aber auch zu mehr Spam oder irrelevanten Inhalten führen.   *Wenn deaktiviert:* Nur angemeldete Kunden können Fotos hochladen, was ein gewisses Maß an Verantwortlichkeit gewährleistet.   **Empfohlener Wert:** NEIN (es sei denn, Sie haben eine strenge Moderation eingerichtet).   **Händlerszenario:** Wenn Sie die Beiträge maximieren möchten und bereit sind zu moderieren, aktivieren Sie dies. Andernfalls lassen Sie es deaktiviert, um die Qualitätskontrolle aufrechtzuerhalten. |
| **Maximale Dateigröße (MB)** | 5 | **Was diese Einstellung bewirkt:** Legt die maximale Größe (in Megabyte) für einen einzelnen Bild-Upload fest.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn auf einen höheren Wert eingestellt:* Kunden können größere, potenziell qualitativ hochwertigere Bilder hochladen, dies verbraucht jedoch mehr Serverspeicher und Bandbreite.   *Wenn auf einen niedrigeren Wert eingestellt:* Beschränkt die Dateigröße, spart Serverressourcen, kann aber die Bildqualität einschränken.   **Empfohlener Wert:** 5-10 MB ist normalerweise ausreichend für weboptimierte Bilder.   **Händlerszenario:** Balance zwischen Bildqualität und Serverressourcen. Zu niedrig, und Kunden könnten frustriert sein; zu hoch, und Ihre Hosting-Kosten könnten steigen. |
| **Produkt-Tab aktivieren** | NEIN | **Was diese Einstellung bewirkt:** Zeigt einen dedizierten „Kundenfotos“-Tab auf Produktseiten an.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Ein neuer Tab erscheint auf Produktseiten, der Fotos anzeigt, die speziell mit diesem Produkt in Verbindung stehen.   *Wenn deaktiviert:* Kein dedizierter Tab für Kundenfotos auf Produktseiten.   **Empfohlener Wert:** JA (wenn Sie produktspezifische UGC anzeigen möchten).   **Händlerszenario:** Großartig für Produkte, bei denen visuelle Testimonials sehr wirkungsvoll sind, wie Mode oder Wohnkultur. |
| **Position des Produkt-Tabs (Modul-Hook)** | displayProductExtraContent | **Was diese Einstellung bewirkt:** Bestimmt, wo der Produkt-Tab auf der Produktseite eingehängt wird.   **Auswirkung der Änderung dieser Einstellung:** Ändert die visuelle Platzierung des „Kundenfotos“-Tabs auf der Produktseite.   **Empfohlener Wert:** `displayProductExtraContent` oder `displayProductTab`.   **Händlerszenario:** Testen Sie verschiedene Hooks, um die beste visuelle Integration mit Ihrem Theme zu finden. |
| **Im Produkt-Footer anzeigen** | NEIN | **Was diese Einstellung bewirkt:** Zeigt einen Block mit Kundenfotos im Footer-Bereich von Produktseiten an.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Ein kleiner Galerieblock erscheint am unteren Rand der Produktseiten.   *Wenn deaktiviert:* Keine Kundenfotos im Produktseiten-Footer.   **Empfohlener Wert:** NEIN (es sei denn, Sie haben einen spezifischen Designbedarf).   **Händlerszenario:** Kann verwendet werden, um das Browsen oder Cross-Selling zu fördern, indem verwandte Kundenfotos angezeigt werden. |
| **Im Kundenkonto anzeigen** | JA | **Was diese Einstellung bewirkt:** Fügt einen Link zu „Meine Fotos“ im Kundenkonto-Dashboard hinzu.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Angemeldete Kunden sehen einen Link zur Verwaltung ihrer hochgeladenen Fotos.   *Wenn deaktiviert:* Kunden können ihren Fotoverwaltungsbereich nicht einfach über ihr Konto erreichen.   **Empfohlener Wert:** JA.   **Händlerszenario:** Wesentlich für Kunden, um ihre Beiträge zu verwalten. |
| **Im Mein Konto-Block anzeigen** | JA | **Was diese Einstellung bewirkt:** Fügt einen Link zu „Meine Fotos“ im „Mein Konto“-Block hinzu (normalerweise in der linken/rechten Spalte oder im Footer).   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Ein Link erscheint im Schnellzugriffs-„Mein Konto“-Block.   *Wenn deaktiviert:* Kein Link im „Mein Konto“-Block.   **Empfohlener Wert:** JA.   **Händlerszenario:** Bietet einen weiteren bequemen Zugangspunkt für Kunden, um ihre Fotos zu verwalten. |
| **Miniaturansicht Höhe (px)** | 100 | **Was diese Einstellung bewirkt:** Legt die Höhe der generierten Miniaturansichten für Galeriebilder fest.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn auf einen höheren Wert eingestellt:* Größere Miniaturansichten, potenziell klarer, nehmen aber mehr Platz ein.   *Wenn auf einen niedrigeren Wert eingestellt:* Kleinere Miniaturansichten, spart Platz, aber weniger Details.   **Empfohlener Wert:** 100-150px.   **Händlerszenario:** Anpassen, um zum Design Ihres Themes zu passen und ein visuell ansprechendes Galerie-Layout zu gewährleisten. |
| **Miniaturansicht Breite (px)** | 100 | **Was diese Einstellung bewirkt:** Legt die Breite der generierten Miniaturansichten für Galeriebilder fest.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn auf einen höheren Wert eingestellt:* Größere Miniaturansichten.   *Wenn auf einen niedrigeren Wert eingestellt:* Kleinere Miniaturansichten.   **Empfohlener Wert:** 100-150px.   **Händlerszenario:** Anpassen, um zum Design Ihres Themes zu passen und ein visuell ansprechendes Galerie-Layout zu gewährleisten. |
| **Foto-Upload-Formular aktivieren** | JA | **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit des Foto-Upload-Formulars auf der Galerieseite.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Kunden können das Upload-Formular sehen und verwenden.   *Wenn deaktiviert:* Das Upload-Formular ist ausgeblendet, wodurch neue Beiträge verhindert werden.   **Empfohlener Wert:** JA (es sei denn, Sie möchten vorübergehend neue Uploads stoppen).   **Händlerszenario:** Deaktivieren, wenn Sie einen Wettbewerb mit einer Einreichungsfrist durchführen oder Uploads für Wartungsarbeiten pausieren müssen. |
| **Galerie-Link anzeigen** | JA | **Was diese Einstellung bewirkt:** Fügt einen Link zur Haupt-Fotogalerieseite in die Navigation Ihres Shops ein.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Ein Link (z. B. „Kunden-Galerie“) erscheint im gewählten Hook.   *Wenn deaktiviert:* Der Link zur Hauptgalerieseite ist ausgeblendet.   **Empfohlener Wert:** JA.   **Händlerszenario:** Wesentlich für Kunden, um die Galerie zu finden und zu durchsuchen. |
| **In rechter Spalte anzeigen** | NEIN | **Was diese Einstellung bewirkt:** Zeigt einen Block mit aktuellen Kundenfotos in der rechten Spalte Ihres Shops an.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Ein Block erscheint in der rechten Spalte.   *Wenn deaktiviert:* Kein Block in der rechten Spalte.   **Empfohlener Wert:** NEIN (kann das Layout überladen, hängt aber von Ihrem Theme ab).   **Händlerszenario:** Nützlich, wenn Ihr Theme ausreichend Platz in der rechten Spalte bietet und Sie aktuelle Beiträge hervorheben möchten. |
| **In linker Spalte anzeigen** | NEIN | **Was diese Einstellung bewirkt:** Zeigt einen Block mit aktuellen Kundenfotos in der linken Spalte Ihres Shops an.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Ein Block erscheint in der linken Spalte.   *Wenn deaktiviert:* Kein Block in der linken Spalte.   **Empfohlener Wert:** NEIN (kann das Layout überladen, hängt aber von Ihrem Theme ab).   **Händlerszenario:** Ähnlich wie bei der rechten Spalte, verwenden Sie es, wenn Ihr Theme es gut unterstützt. |
| **Benachrichtigungen aktivieren** | JA | **Was diese Einstellung bewirkt:** Sendet E-Mail-Benachrichtigungen an den Shop-Administrator, wenn neue Fotos hochgeladen werden.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Sie erhalten eine E-Mail für jeden neuen Upload, was eine schnelle Moderation ermöglicht.   *Wenn deaktiviert:* Keine E-Mail-Benachrichtigungen.   **Empfohlener Wert:** JA.   **Händlerszenario:** Entscheidend für eine zeitnahe Moderation und um sicherzustellen, dass nur geeignete Inhalte angezeigt werden. |
| **Anzahl der Fotos auf der Startseite** | 8 | **Was diese Einstellung bewirkt:** Legt fest, wie viele Kundenfotos im Startseitenblock angezeigt werden.   **Auswirkung der Änderung dieser Einstellung:** Ändert die Anzahl der auf der Startseite angezeigten Fotos.   **Empfohlener Wert:** 6-12, abhängig von Ihrem Startseiten-Layout.   **Händlerszenario:** Anpassen, um zum Design Ihrer Startseite zu passen, ohne die Seite zu überladen. |
| **Reihenfolge der Fotos auf der Startseite** | Neueste zuerst | **Was diese Einstellung bewirkt:** Bestimmt die Sortierreihenfolge der auf der Startseite angezeigten Fotos.   **Auswirkung der Änderung dieser Einstellung:** Fotos können nach neuesten, ältesten, beliebtesten usw. sortiert werden.   **Empfohlener Wert:** Neueste zuerst oder Beliebteste.   **Händlerszenario:** „Neueste zuerst“ hält den Inhalt frisch; „Beliebteste“ hebt ansprechende Inhalte hervor. |
| **Foto-Wettbewerbsmodus aktivieren** | NEIN | **Was diese Einstellung bewirkt:** Aktiviert Funktionen zur Durchführung eines Fotowettbewerbs, möglicherweise einschließlich Abstimmungs- und Preismechanismen.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Zusätzliche wettbewerbsbezogene Optionen können erscheinen, und die Galerie könnte die Abstimmung betonen.   *Wenn deaktiviert:* Standard-Galeriemodus.   **Empfohlener Wert:** NEIN (es sei denn, es wird aktiv ein Wettbewerb durchgeführt).   **Händlerszenario:** Verwenden Sie dies, wenn Sie eine spezifische Kampagne zur Sammlung von Fotos durchführen und Benutzer mit Abstimmungen einbinden möchten. |
| **Produkte aus Galerie ausschließen** | (Produkt-IDs) | **Was diese Einstellung bewirkt:** Ermöglicht die Angabe von Produkt-IDs, für die KEINE Kundenfotos auf ihren Produktseiten angezeigt werden sollen.   **Auswirkung der Änderung dieser Einstellung:** Fotos für diese spezifischen Produkte werden nicht im Produkt-Tab/Footer angezeigt, auch wenn die Haupt-Produkt-Tab-Einstellung aktiviert ist.   **Empfohlener Wert:** Leer lassen, es sei denn, es ist notwendig.   **Händlerszenario:** Wenn Sie sensible Produkte haben oder Produkte, bei denen Kundenfotos irrelevant oder unangemessen sind, können Sie diese ausschließen. |
| **Sichtbarkeit des Kundenkonto-Links** | JA | **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit des Links „Meine Fotos“ im Kundenkonto-Dashboard.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Link ist sichtbar.   *Wenn deaktiviert:* Link ist ausgeblendet.   **Empfohlener Wert:** JA.   **Händlerszenario:** Für die Bequemlichkeit des Kunden aktiviert lassen. |
| **Sichtbarkeit des Mein Konto-Block-Links** | JA | **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit des Links „Meine Fotos“ im „Mein Konto“-Block (z. B. in Spalten).   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Link ist sichtbar.   *Wenn deaktiviert:* Link ist ausgeblendet.   **Empfohlener Wert:** JA.   **Händlerszenario:** Für die Bequemlichkeit des Kunden aktiviert lassen. |
| **Abstimmung für Fotos aktivieren** | JA | **Was diese Einstellung bewirkt:** Ermöglicht Kunden (und optional Gästen), über hochgeladene Fotos abzustimmen.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Abstimmungsschaltflächen/Sterne erscheinen neben den Fotos.   *Wenn deaktiviert:* Keine Abstimmungsfunktion.   **Empfohlener Wert:** JA (erhöht die Interaktion).   **Händlerszenario:** Verwenden Sie dies, um beliebte Fotos zu identifizieren, Wettbewerbe durchzuführen oder einfach die Interaktion zu fördern. |
| **Typ des Abstimmungssystems** | Sterne | **Was diese Einstellung bewirkt:** Wählt den visuellen Stil des Abstimmungssystems (z. B. Sterne, Daumen hoch/runter).   **Auswirkung der Änderung dieser Einstellung:** Ändert das Aussehen des Abstimmungsmechanismus.   **Empfohlener Wert:** Sterne (im Allgemeinen intuitiver).   **Händlerszenario:** Wählen Sie den Stil, der am besten zur Ästhetik Ihres Shops passt. |
| **Nicht angemeldeten Benutzern das Abstimmen erlauben** | NEIN | **Was diese Einstellung bewirkt:** Ermöglicht Besuchern, die nicht angemeldet sind, über Fotos abzustimmen.   **Auswirkung der Änderung dieser Einstellung:**   *Wenn aktiviert:* Gäste können abstimmen. Dies kann die Teilnahme erhöhen, könnte aber anfällig für Missbrauch sein.   *Wenn deaktiviert:* Nur angemeldete Kunden können abstimmen.   **Empfohlener Wert:** NEIN (um Stimmmanipulation zu verhindern).   **Händlerszenario:** Nur aktivieren, wenn Sie maximale Teilnahme über strenge Stimm-Integrität stellen. |

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | CG\_ALLOW\_JPEG | JA | JPEG-Bild-Uploads zulassen. |
| Modulkonfiguration | CG\_ALLOW\_GIF | JA | GIF-Bild-Uploads zulassen. |
| Modulkonfiguration | CG\_ALLOW\_PNG | JA | PNG-Bild-Uploads zulassen. |
| Modulkonfiguration | CG\_ALLOW\_BMP | NEIN | BMP-Bild-Uploads zulassen (große Dateien). |
| Modulkonfiguration | CG\_PAGINATION | JA | Paginierung für Galerieseiten aktivieren. |
| Modulkonfiguration | CG\_ALLOW\_UNLOGGED | NEIN | Gästen das Hochladen von Fotos erlauben. |
| Modulkonfiguration | CG\_MAX\_FILE\_SIZE | 5 MB | Maximale Dateigröße für Uploads. |
| Modulkonfiguration | CG\_PRODUCTTAB | NEIN | Kundenfotos in einem Produkt-Tab anzeigen. |
| Modulkonfiguration | cg\_productTabM | displayProductExtraContent | Hook für die Platzierung des Produkt-Tabs. |
| Modulkonfiguration | CG\_PRODUCTFOOTER | NEIN | Fotos im Produkt-Footer anzeigen. |
| Modulkonfiguration | CG\_CUSTOMERACCOUNT | JA | Link „Meine Fotos“ im Kundenkonto anzeigen. |
| Modulkonfiguration | CG\_MYACCOUNTBLOCK | JA | Link „Meine Fotos“ im Mein Konto-Block anzeigen. |
| Modulkonfiguration | CG\_THUMBHEIGHT | 100 | Höhe der generierten Miniaturansichten. |
| Modulkonfiguration | CG\_THUMBWIDTH | 100 | Breite der generierten Miniaturansichten. |
| Modulkonfiguration | CG\_FUPLOADON | JA | Foto-Upload-Formular aktivieren. |
| Modulkonfiguration | CG\_GALLERY | JA | Link zur Hauptgalerieseite anzeigen. |
| Modulkonfiguration | CG\_RIGHTCOL | NEIN | Fotos in der rechten Spalte anzeigen. |
| Modulkonfiguration | CG\_LEFTCOL | NEIN | Fotos in der linken Spalte anzeigen. |
| Modulkonfiguration | CG\_NTF | JA | Admin-E-Mail-Benachrichtigungen für neue Uploads senden. |
| Modulkonfiguration | cg\_hpg\_nb | 8 | Anzahl der Fotos auf der Startseite. |
| Modulkonfiguration | cg\_hpg\_o | Neueste zuerst | Reihenfolge der Fotos auf der Startseite. |
| Modulkonfiguration | cg\_contest | NEIN | Foto-Wettbewerbsmodus aktivieren. |
| Modulkonfiguration | cg\_excludeproduct | (leer) | Produkt-IDs, die von der Galerie ausgeschlossen werden sollen. |
| Modulkonfiguration | CG\_CUSTOMERACCOUNTV | JA | Sichtbarkeit des Links „Meine Fotos“ im Kundenkonto. |
| Modulkonfiguration | CG\_MYACCOUNTBLOCKV | JA | Sichtbarkeit des Links „Meine Fotos“ im Mein Konto-Block. |
| Modulkonfiguration | CG\_voting | JA | Abstimmung für Fotos aktivieren. |
| Modulkonfiguration | CG\_VOTE\_STAR | Sterne | Visueller Stil des Abstimmungssystems. |
| Modulkonfiguration | cg\_unl\_voting | NEIN | Nicht angemeldeten Benutzern das Abstimmen erlauben. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine hochgeladenen Fotos erscheinen nicht in der Galerie.**
**A:**

- **Modulkonfiguration prüfen:** Stellen Sie sicher, dass „Foto-Upload-Formular aktivieren“ (`CG_FUPLOADON`) auf JA gesetzt ist.
- **Dateityp & -größe:** Überprüfen Sie, ob der hochgeladene Dateityp (JPEG, PNG, GIF, BMP) in den Moduleinstellungen erlaubt ist und dass die Dateigröße innerhalb des Limits für die „Maximale Dateigröße“ (`CG_MAX_FILE_SIZE`) liegt.
- **Moderation:** Das Modul könnte eine interne Moderationswarteschlange haben (obwohl nicht explizit als Einstellung aufgeführt, haben viele Galerie-Module dies). Überprüfen Sie, ob es einen Admin-Bereich gibt, um Fotos zu genehmigen/abzulehnen.
- **Berechtigungen:** Stellen Sie sicher, dass das Verzeichnis `img/customersgallery/` (oder ein ähnlicher Pfad, in dem Bilder gespeichert werden) auf Ihrem Server Schreibberechtigungen hat (normalerweise 755 oder 777, obwohl 777 weniger sicher ist).
- **Cache leeren:** Gehen Sie im PrestaShop Back Office zu **Erweiterte Einstellungen > Performance** und leeren Sie den Smarty-Cache, den Browser-Cache und den Modul-Cache.

**F2: Der Galerie-Link oder -Block wird in meinem Shop nicht angezeigt.**
**A:**

- **Modul-Hooks:** Überprüfen Sie die Konfigurationsseite des Moduls. Stellen Sie sicher, dass „Galerie-Link anzeigen“ (`CG_GALLERY`), „In rechter Spalte anzeigen“ (`CG_RIGHTCOL`), „In linker Spalte anzeigen“ (`CG_LEFTCOL`) usw. für die erwarteten Positionen aktiviert sind.
- **Hook-Verwaltung:** Gehen Sie im PrestaShop Back Office zu **Design > Positionen** (oder **Module > Positionen** in älteren Versionen). Suchen Sie nach dem Modul („Kunden-Fotogalerie“) und stellen Sie sicher, dass es an den richtigen `display`-Positionen eingehängt ist (z. B. `displayHeader`, `displayHome`, `displayRightColumn`). Falls nicht, „Transplantieren Sie ein Modul“ an den gewünschten Hook.
- **Theme-Kompatibilität:** Einige benutzerdefinierte Themes können Standard-Hook-Positionen überschreiben. Wenn das Modul trotz korrekter Einhängung nicht angezeigt wird, sind möglicherweise geringfügige Theme-Anpassungen erforderlich. Kontaktieren Sie Ihren Theme-Entwickler oder den MyPresta.eu-Support.
- **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache, nachdem Sie Änderungen an Modulpositionen oder -einstellungen vorgenommen haben.

**F3: Fotos auf Produktseiten werden nicht in einem Tab angezeigt.**
**A:**

- **Produkt-Tab aktivieren:** Stellen Sie sicher, dass `CG_PRODUCTTAB` in der Modulkonfiguration auf JA gesetzt ist.
- **Produkt-Tab-Hook:** Überprüfen Sie, ob `cg_productTabM` auf einen geeigneten Hook wie `displayProductExtraContent` oder `displayProductTab` gesetzt ist.
- **Produktausschluss:** Überprüfen Sie `cg_excludeproduct`, um sicherzustellen, dass das Produkt, das Sie anzeigen, dort nicht aufgeführt ist.
- **Verknüpfte Fotos:** Stellen Sie sicher, dass tatsächlich Fotos hochgeladen und mit diesem spezifischen Produkt verknüpft sind.
- **Cache leeren:** Leeren Sie alle Caches.

**F4: Das Abstimmungssystem funktioniert nicht oder ist nicht sichtbar.**
**A:**

- **Abstimmung aktivieren:** Stellen Sie sicher, dass „Abstimmung für Fotos aktivieren“ (`CG_voting`) auf JA gesetzt ist.
- **Nicht angemeldete Benutzer:** Wenn Gäste nicht abstimmen können, überprüfen Sie „Nicht angemeldeten Benutzern das Abstimmen erlauben“ (`cg_unl_voting`).
- **CSS-Konflikte:** Manchmal kann Theme-CSS Modulelemente ausblenden oder verzerren. Verwenden Sie die Entwicklertools Ihres Browsers (F12), um den Bereich zu untersuchen und nach widersprüchlichen Stilen zu suchen.
- **JavaScript-Fehler:** Überprüfen Sie die Konsole Ihres Browsers (F12 > Tab „Konsole“) auf JavaScript-Fehler, die die Abstimmungsfunktion möglicherweise blockieren.

**F5: Wie übersetze ich den Text des Moduls in andere Sprachen?**
**A:**

- Gehen Sie im PrestaShop Back Office zu **International > Übersetzungen**.
- Wählen Sie „Übersetzungen installierter Module“.
- Wählen Sie Ihr Theme, die Sprache, in die Sie übersetzen möchten, und dann „Kunden-Fotogalerie“ aus der Modulliste.
- Sie können dann alle Front-Office- und Back-Office-Strings des Moduls übersetzen.
- Denken Sie daran, Ihre Änderungen zu speichern und den Cache zu leeren.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul Kunden-Fotogalerie folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich Front-Controller für Benutzerinteraktionen und Smarty-Templates für die Darstellung nutzt. Es integriert sich mit verschiedenen Display-Hooks, um Galeriefunktionen im gesamten Shop einzubetten. Obwohl es in der bereitgestellten Inventur keine expliziten benutzerdefinierten `ObjectModel`-Klassen definiert, verwendet es wahrscheinlich `Configuration` für Einstellungen und interagiert direkt mit der Datenbank für die Speicherung und Verwaltung von Fotos/Videos. AJAX wird für dynamisches Laden von Inhalten und Interaktionen wie Abstimmungen verwendet.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Diese Controller verwalten alle kundenorientierten Interaktionen und die Datenverarbeitung für die Galerie.

- **`customersgallery/controllers/front/ajax.php`**

  - **Klassenname:** `CustomersGalleryAjaxModuleFrontController` (erweitert wahrscheinlich `ModuleFrontController`)
  - **Verantwortlichkeit:** Dieser Controller ist das Rückgrat für dynamische Interaktionen ohne vollständige Seitenneuladungen. Er verarbeitet AJAX-Anfragen für Aktionen wie:
    - Einreichen neuer Fotos/Videos.
    - Verarbeiten von Abstimmungen (z. B. Sternebewertungen).
    - Laden weiterer Galerieelemente (Paginierung/Infinite Scroll).
    - Potenziell Moderationsaktionen, wenn ein nicht angemeldeter Benutzer hochlädt und eine Genehmigung erforderlich ist.
    - Gibt JSON-Antworten an das clientseitige JavaScript zurück.
- **`customersgallery/controllers/front/gallery.php`**

  - **Klassenname:** `CustomersGalleryGalleryModuleFrontController` (erweitert wahrscheinlich `ModuleFrontController`)
  - **Verantwortlichkeit:** Dieser Controller ist für die Anzeige der Hauptseite der Kundenfoto- und Videogalerie zuständig.
    - Ruft alle genehmigten Fotos/Videos aus der Datenbank ab.
    - Wendet Paginierungslogik basierend auf den Moduleinstellungen (`CG_PAGINATION`) an.
    - Bereitet Daten für das `gallery.tpl`-Template vor, einschließlich Bildpfaden, Titeln, Beschreibungen und Abstimmungsdaten.
    - Handhabt die Sortierung (z. B. nach neuesten, beliebtesten).
- **`customersgallery/controllers/front/index.php`**

  - **Klassenname:** `CustomersGalleryIndexModuleFrontController` (erweitert wahrscheinlich `ModuleFrontController`)
  - **Verantwortlichkeit:** Dieser Controller könnte als Standard-Einstiegspunkt oder Weiterleitung für den Front-Office-Bereich des Moduls dienen. Er könnte auch für eine einfache Landingpage oder zur Weiterleitung zur Hauptgalerie verwendet werden. In vielen Modulen ist `index.php` in einem Front-Controller-Verzeichnis ein Fallback oder eine einfache Weiterleitung zur Hauptfunktion.
- **`customersgallery/controllers/front/myphotos.php`**

  - **Klassenname:** `CustomersGalleryMyPhotosModuleFrontController` (erweitert wahrscheinlich `ModuleFrontController`)
  - **Verantwortlichkeit:** Dieser Controller verwaltet den Bereich „Meine Fotos“ innerhalb des Kundenkontos.
    - Authentifiziert den angemeldeten Kunden.
    - Ruft alle vom aktuellen Kunden hochgeladenen Fotos ab.
    - Ermöglicht Kunden, ihre eigenen Beiträge anzuzeigen, zu bearbeiten (z. B. Titel, Beschreibung) oder zu löschen.
    - Bereitet Daten für das `my-photos.tpl`-Template vor.
- **`customersgallery/controllers/front/myvideos.php`**

  - **Klassenname:** `CustomersGalleryMyVideosModuleFrontController` (erweitert wahrscheinlich `ModuleFrontController`)
  - **Verantwortlichkeit:** Ähnlich wie `myphotos.php`, aber speziell für die Verwaltung von Videos, die vom aktuellen Kunden hochgeladen wurden.
    - Authentifiziert den angemeldeten Kunden.
    - Ruft alle vom aktuellen Kunden hochgeladenen Videos ab.
    - Ermöglicht Kunden, ihre eigenen Video-Beiträge anzuzeigen, zu bearbeiten oder zu löschen.
    - Bereitet Daten für das `my-videos-16.tpl`-Template vor.

#### Back-Office-Admin-Controller

Das Moduldossier weist keine dedizierten Admin-Controller aus. Die gesamte Back-Office-Konfiguration wird über die `getContent()`-Methode der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` aus. Dies deutet darauf hin, dass das Modul seine Daten wahrscheinlich direkt in der Datei `customersgallery.php` verwaltet oder generische PrestaShop-Datenbankinteraktionsmethoden verwendet.

- **Datenspeicherung:** Metadaten von Fotos und Videos (Pfade, Titel, Benutzer-IDs, Produkt-IDs, Genehmigungsstatus, Abstimmungen) werden wahrscheinlich in benutzerdefinierten Datenbanktabellen gespeichert, die während der Modulinstallation erstellt werden. Die Haupt-PHP-Datei des Moduls (`customersgallery.php`) würde die SQL-Abfragen für diese Tabellen enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

- **`customersgallery/js/customersgallery.js`**

  - **Geltungsbereich:** Front-Office.
  - **Detail:** Dies ist wahrscheinlich die wichtigste benutzerdefinierte JavaScript-Datei für die Galerie. Sie würde enthalten:
    - Event-Listener für Foto-/Video-Uploads (z. B. Formularübermittlung, Datei-Input-Änderungen).
    - AJAX-Aufrufe an `ajax.php` für Uploads, Abstimmungen und das Laden weiterer Inhalte.
    - Clientseitige Validierung für Dateitypen und -größen.
    - Dynamische Aktualisierungen der Galerieanzeige (z. B. Hinzufügen neuer Fotos ohne Seitenaktualisierung).
    - Interaktion mit der Fancybox-Bibliothek für Bild-Lightboxes.
- **`customersgallery/js/fancybox.js`**

  - **Geltungsbereich:** Front-Office.
  - **Detail:** Eine Drittanbieterbibliothek (Fancybox) zum Erstellen eleganter, responsiver Lightboxes für Bilder und Multimedia. Dieses Skript ermöglicht die „Klicken zum Vergrößern“-Funktionalität für Galeriefotos.
- **`customersgallery/js/script.js`**

  - **Geltungsbereich:** Front-Office.
  - **Detail:** Dies könnte ein allgemeines Dienstprogramm-Skript oder ein älteres Skript sein. Es könnte enthalten:
    - Hilfsfunktionen für UI-Interaktionen.
    - Zusätzliche Event-Handler, die nicht spezifisch für die Kernlogik der Galerie sind.
    - Potenziell Skripte im Zusammenhang mit dem Abstimmungsmechanismus oder anderen interaktiven Elementen.
- **`customersgallery/lib/voucherengine/script.js`**

  - **Geltungsbereich:** Front-Office.
  - **Detail:** Dies deutet auf eine Integration mit einer „Gutschein-Engine“ oder einem ähnlichen Belohnungssystem hin. Dieses Skript würde Folgendes verwalten:
    - Logik zur Vergabe von Gutscheinen oder Rabatten bei erfolgreicher Foto-/Video-Einreichung (wenn `cg_contest` aktiviert ist oder ein ähnliches Belohnungssystem vorhanden ist).
    - AJAX-Aufrufe zur Auslösung der Gutscheingenerierung oder -anwendung.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`customersgallery/css/customersgallery.css`**

  - **Geltungsbereich:** Front-Office (Haupt-Galerie-Styling).
  - **Detail:** Enthält die Kern-CSS-Regeln für das Layout, das Erscheinungsbild und die Responsivität der Kunden-Fotogalerie, einschließlich:
    - Rasterlayouts für die Fotoanzeige.
    - Styling für Miniaturansichten, Bildunterschriften und Benutzerinformationen.
    - Stile für das Upload-Formular und die Paginierung.
    - Responsive Anpassungen für verschiedene Bildschirmgrößen.
  - **Wichtige Selektoren:** `.customer-gallery-container`, `.gallery-item`, `.gallery-thumbnail`, `.upload-form`, `.pagination`.
- **`customersgallery/css/fancybox.css`**

  - **Geltungsbereich:** Front-Office.
  - **Detail:** Stylesheet für die Fancybox-Lightbox-Bibliothek, das das Erscheinungsbild der vergrößerten Bilder, Navigationspfeile, des Schließen-Buttons und des Overlays steuert.
  - **Wichtige Selektoren:** `.fancybox-container`, `.fancybox-image`, `.fancybox-caption`.
- **`customersgallery/css/star-black.css`, `star-blue.css`, `star-gold.css`, `star-pink.css`, `star-red.css`, `star-whitered.css`, `star.css`**

  - **Geltungsbereich:** Front-Office.
  - **Detail:** Dies sind verschiedene Farbthemen für das sternbasierte Abstimmungssystem (`CG_VOTE_STAR`). `star.css` ist wahrscheinlich das Basis-Styling, und die anderen bieten Farbüberlagerungen.
  - **Wichtige Selektoren:** `.star-rating`, `.star-rating-control`, `.star-rating-star`.
- **`customersgallery/lib/voucherengine/ps16.css`**

  - **Geltungsbereich:** Front-Office.
  - **Detail:** Dieses Stylesheet ist speziell für die Integration der „Gutschein-Engine“ gedacht und bietet wahrscheinlich Styling für alle Elemente im Zusammenhang mit der Gutscheinanzeige oder -benachrichtigung, möglicherweise mit spezifischen Überschreibungen für PrestaShop 1.6-Themes.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Benutzerdefinierte Templates (`views/templates/custom/`)

Dies sind wahrscheinlich spezifische Formulare oder Komponenten.

- **`customersgallery/views/templates/custom/upload-form.tpl`**
  - **Zweck:** Rendert das HTML-Formular für Kunden zum Hochladen von Fotos.
  - **Variablen:** Enthält wahrscheinlich Felder für Dateieingabe, Titel, Beschreibung und möglicherweise Produktzuordnung.
- **`customersgallery/views/templates/custom/upload-form2.tpl`**
  - **Zweck:** Könnte eine alternative oder aktualisierte Version des Upload-Formulars sein, möglicherweise für Video-Uploads oder ein anderes Layout.

#### Front-Office-Templates (`views/templates/front/`)

Diese Templates rendern die Hauptgalerieseiten und benutzerspezifische Inhalte.

- **`customersgallery/views/templates/front/gallery.tpl`**
  - **Zweck:** Haupt-Template zur Anzeige der Kundenfoto- und Videogalerie.
  - **Variablen:** Durchläuft `$photos`- und `$videos`-Arrays und zeigt Miniaturansichten, Titel und Abstimmungselemente an. Enthält Paginierung.
- **`customersgallery/views/templates/front/gallery2.tpl`**
  - **Zweck:** Könnte ein alternatives Galerie-Layout oder eine spezifische Ansicht für Wettbewerbe sein.
- **`customersgallery/views/templates/front/gallery3.tpl`**
  - **Zweck:** Ein weiteres alternatives Galerie-Layout.
- **`customersgallery/views/templates/front/menu.tpl`**
  - **Zweck:** Rendert ein spezifisches Navigationsmenü für die Galerie, möglicherweise mit Links zu „Meine Fotos“, „Meine Videos“, „Hochladen“ usw.
- **`customersgallery/views/templates/front/my-photos.tpl`**
  - **Zweck:** Zeigt die Liste der vom aktuell angemeldeten Kunden hochgeladenen Fotos an, mit Optionen zum Bearbeiten oder Löschen.
  - **Variablen:** `$customer_photos`-Array.
- **`customersgallery/views/templates/front/my-videos-16.tpl`**
  - **Zweck:** Zeigt die Liste der vom aktuell angemeldeten Kunden hochgeladenen Videos an, speziell für die PrestaShop 1.6-Kompatibilität entwickelt.
  - **Variablen:** `$customer_videos`-Array.
- **`customersgallery/views/templates/front/video-upload.tpl`**
  - **Zweck:** Rendert ein Formular speziell für das Hochladen von Videos, getrennt vom Foto-Upload-Formular.

#### Hook-Templates (`views/templates/hook/`)

Diese Templates sind dafür konzipiert, innerhalb spezifischer PrestaShop-Hooks gerendert zu werden.

- **`customersgallery/views/templates/hook/column-link.tpl`**
  - **Hook:** `displayLeftColumn`, `displayRightColumn`
  - **Zweck:** Rendert einen Block in der linken oder rechten Spalte mit einem Link zur Hauptgalerieseite oder einigen aktuellen Fotos.
- **`customersgallery/views/templates/hook/customer-my-account.tpl`**
  - **Hook:** `displayCustomerAccount`
  - **Zweck:** Fügt einen Link oder Block innerhalb des Kundenkonto-Dashboards hinzu, der typischerweise auf „Meine Fotos“ oder „Meine Videos“ verlinkt.
- **`customersgallery/views/templates/hook/hookHome.tpl`**
  - **Hook:** `displayHome`
  - **Zweck:** Zeigt einen Block mit aktuellen oder beliebten Kundenfotos auf der Startseite des Shops an.
  - **Variablen:** `$homepage_photos`-Array.
- **`customersgallery/views/templates/hook/my-account.tpl`**
  - **Hook:** `displayMyAccountBlock`, `displayMyAccountBlockFooter`
  - **Zweck:** Fügt einen Link zu „Meine Fotos“ innerhalb des „Mein Konto“-Blocks hinzu, der oft in Seitenleisten oder im Footer zu finden ist.
- **`customersgallery/views/templates/hook/productfooter.tpl`**
  - **Hook:** `displayProductFooter`
  - **Zweck:** Rendert einen Block mit Kundenfotos, die mit dem aktuellen Produkt zusammenhängen, im Produktseiten-Footer.
- **`customersgallery/views/templates/hook/tab.tpl`**
  - **Hook:** `displayProductTab`, `displayProductExtraContent`
  - **Zweck:** Rendert den Header des „Kundenfotos“-Tabs auf einer Produktseite.
- **`customersgallery/views/templates/hook/tabContents.tpl`**
  - **Hook:** `displayProductTabContent`, `displayProductExtraContent`
  - **Zweck:** Rendert den eigentlichen Inhalt (die Fotogalerie) innerhalb des „Kundenfotos“-Tabs auf einer Produktseite.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul erstellt wahrscheinlich während der Installation benutzerdefinierte Tabellen. Basierend auf der Funktionalität würden diese Folgendes umfassen:

- **`ps_customersgallery_photos`**:

  - `id_photo` (PRIMÄRSCHLÜSSEL, INT)
  - `id_customer` (INT, FK zu `ps_customer`)
  - `id_product` (INT, FK zu `ps_product`, NULLABLE)
  - `filename` (VARCHAR, Pfad zur Bilddatei)
  - `title` (VARCHAR)
  - `description` (TEXT)
  - `date_add` (DATETIME)
  - `active` (TINYINT, für den Moderationsstatus)
  - `votes` (INT, Gesamtstimmen)
  - `rating` (DECIMAL, Durchschnittsbewertung)
- **`ps_customersgallery_videos`**:

  - `id_video` (PRIMÄRSCHLÜSSEL, INT)
  - `id_customer` (INT, FK zu `ps_customer`)
  - `id_product` (INT, FK zu `ps_product`, NULLABLE)
  - `url` (VARCHAR, für externe Videolinks wie YouTube/Vimeo)
  - `title` (VARCHAR)
  - `description` (TEXT)
  - `date_add` (DATETIME)
  - `active` (TINYINT)
- **`ps_customersgallery_votes`**:

  - `id_vote` (PRIMÄRSCHLÜSSEL, INT)
  - `id_photo` (INT, FK zu `ps_customersgallery_photos`)
  - `id_customer` (INT, FK zu `ps_customer`, NULLABLE für nicht angemeldete Stimmen)
  - `ip_address` (VARCHAR, für nicht angemeldete Stimmen und Missbrauchsprävention)
  - `vote_value` (INT, z. B. 1-5 für Sterne)
  - `date_add` (DATETIME)
- **`ps_configuration`**: Moduleinstellungen (z. B. `CG_ALLOW_JPEG`, `CG_MAX_FILE_SIZE`, `CG_PAGINATION`) werden hier gespeichert.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayProductExtraContent` | Rendert zusätzlichen Inhalt auf der Produktseite, oft für Tabs verwendet. | Zeigt den „Kundenfotos“-Tab und dessen Inhalt auf Produktseiten an. |
| `displayRightColumnProduct` | Rendert Inhalt in der rechten Spalte einer Produktseite. | Zeigt einen Block produktspezifischer Kundenfotos in der rechten Spalte an. |
| `displayCustomerAccount` | Rendert Inhalt im „Mein Konto“-Dashboard des Kunden. | Fügt einen Link oder Block zu „Meine Fotos“ und „Meine Videos“ für den angemeldeten Kunden hinzu. |
| `displayRightColumn` | Rendert Inhalt in der rechten Spalte allgemeiner Shop-Seiten. | Zeigt einen Block aktueller Kundenfotos in der rechten Spalte an. |
| `displayMyAccountBlockFooter` | Rendert Inhalt im Footer des „Mein Konto“-Blocks. | Fügt einen Link zu „Meine Fotos“ im „Mein Konto“-Block hinzu, oft im Footer. |
| `displayProductFooter` | Rendert Inhalt im Footer-Bereich einer Produktseite. | Zeigt einen Block produktspezifischer Kundenfotos im Produkt-Footer an. |
| `displayProductTabContent` | Rendert den Inhalt eines Produkt-Tabs. | Zeigt den Galerieinhalt innerhalb des „Kundenfotos“-Tabs auf Produktseiten an. |
| `displayLeftColumnProduct` | Rendert Inhalt in der linken Spalte einer Produktseite. | Zeigt einen Block produktspezifischer Kundenfotos in der linken Spalte an. |
| `displayLeftColumn` | Rendert Inhalt in der linken Spalte allgemeiner Shop-Seiten. | Zeigt einen Block aktueller Kundenfotos in der linken Spalte an. |
| `displayHome` | Rendert Inhalt auf der Startseite des Shops. | Zeigt einen Block aktueller oder beliebter Kundenfotos auf der Startseite an. |
| `displayHeader` | Rendert Inhalt im `<head>`-Bereich aller Seiten. | Fügt CSS- und JavaScript-Dateien ein, die vom Modul im gesamten Shop benötigt werden. |
| `displayMyAccountBlock` | Rendert Inhalt innerhalb des „Mein Konto“-Blocks (z. B. in Seitenleisten). | Fügt einen Link zu „Meine Fotos“ im „Mein Konto“-Block hinzu. |
| `displayProductTab` | Rendert den Tab-Header für einen Produktseiten-Tab. | Zeigt den Titel des „Kundenfotos“-Tabs auf Produktseiten an. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und professionellen Support besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, den reibungslosen Betrieb und die kontinuierliche Verbesserung Ihrer PrestaShop-Module sicherzustellen.
