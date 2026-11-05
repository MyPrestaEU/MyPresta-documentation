---
title: "Microsoft Advertising UET Tag & Conversions API - Dokumentation und Benutzerhandbuch"
description: "Konfigurieren Sie das Tracking, prüfen Sie Ereignisse mit der Live-Diagnose und beheben Sie Probleme nach der Modulinstallation."
sidebar:
  label: "Microsoft Advertising UET Tag & Conversions API - Dokumentation und Benutzerhandbuch"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Microsoft Advertising UET Tag & Conversions API auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/microsoft-advertising-uet-tag-conversions-api.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/microsoft-advertising-uet-tag-conversions-api/)
>
> ---


## 1. Anforderungen

Bereiten Sie den Shop, das Microsoft Advertising-Konto und die geplante Aufgabe vor der Konfiguration vor.

- Verwenden Sie PrestaShop 1.7, 8 oder 9.
- Verwenden Sie PHP 7.1–8.x, entsprechend der PHP-Version, die für Ihre PrestaShop-Installation erforderlich ist.
- Aktivieren Sie die PHP-cURL-, JSON-, OpenSSL- und Hash-Erweiterungen.
- Sie verfügen über ein Microsoft Advertising-Konto und eine UET-Tag-ID. Erhalten Sie außerdem ein Conversions-API-Bearer-Token für **Conversions API** oder **UET + CAPI**.
- Zugriff auf CRON haben, wenn Sie CAPI verwenden, da dessen Warteschlange regelmäßig ausgeführt werden muss.
- Konfigurieren Sie ein externes CMP- oder Cookie-Modul, bevor Sie **Require marketing / analytics consent** in **Yes** umwandeln.
- Es ist kein weiteres PrestaShop-Modul erforderlich. Ein Microsoft Merchant Center-Feed-Modul ist optional und kann bei der Ausrichtung von Katalog-IDs helfen.

## 2. Installation

1. Öffnen Sie **Modules > Module Manager**.
2. Klicken Sie auf **Upload a module** und laden Sie die ZIP-Datei hoch.
3. Installieren Sie **Microsoft Advertising UET / Conversions API**.
4. Suchen Sie es in **Module Manager** und klicken Sie auf **Configure**.
5. Füllen Sie **Setup Wizard** aus oder konfigurieren Sie alle Registerkarten manuell.

Das Modul erstellt keinen sichtbaren **Catalog**-Menüpunkt. Sein Datenendpunkt ist eine versteckte Backoffice-Registerkarte, die intern verwendet wird.

Bei der Installation wird der PrestaShop-Cache nicht geleert. Löschen Sie es unter **Advanced Parameters > Performance** nur, wenn alte Assets oder ein alter Konfigurationsbildschirm weiterhin sichtbar sind.

Durch die Deinstallation werden das Ereignisprotokoll, die Multi-Tag-Regeln, die CAPI-Warteschlange, der versteckte Endpunkt und die Modulkonfigurationsschlüssel des Moduls entfernt. Möglicherweise verbleiben Update-Checker-Schlüssel. Die Neuinstallation beginnt mit den Standardeinstellungen und stellt gelöschte Ereignisse oder Regeln nicht wieder her.

## 3. Konfiguration und Backoffice-Arbeit

Öffnen Sie **Modules > Module Manager**, suchen Sie **Microsoft Advertising UET / Conversions API** und klicken Sie auf **Configure**.

Befolgen Sie diesen Vorgang:

1. Vervollständigen Sie **Setup Wizard**.
2. Bestätigen Sie den Kanal und die Anmeldeinformationen in **Tracking mode**.
3. Wählen Sie Signale in **Events** aus.
4. Ordnen Sie die Event-Produkt-IDs Ihrem Feed in **Catalog IDs** zu.
5. Konfigurieren Sie **Privacy & consent**.
6. Definieren Sie das Zahlungs- und Rückerstattungsverhalten in **Order lifecycle**.
7. Fügen Sie **Multi-tag rules** nur für kontextspezifische Anmeldeinformationen hinzu.
8. Planen Sie die angezeigte CRON-URL alle 1–5 Minuten, wenn CAPI aktiv ist.
9. Durchsuchen Sie die Storefront und überprüfen Sie die Ereignisse in **Live Statistics** und **Health & diagnostics**.
10. Bestätigen Sie die Ereignisse in Microsoft Advertising.

Screenshots in diesem Handbuch stammen von einem englischen Backoffice.

### 3.1 Setup-Assistent

Verwenden Sie den Assistenten für die Ersteinrichtung. Es führt Sie durch **Mode**, **Tag ID**, **CAPI token**, **Test** und **Done**.

![Setup Wizard](https://mypresta.eu/docs/images/docs/mybing-wizard.webp)

| Feld | Beim Start | Was es tut |
|---|---|---|
| **Mode** | Nicht ausgewählt | Wählen Sie **UET Tag** für die Browserverfolgung, **Conversions API** für die Serververfolgung oder **UET + CAPI** für beides. Der Dualmodus verwendet eine gemeinsame Ereigniskennung für die Deduplizierung. |
| **Tag ID** | Leer | Fügen Sie die ID aus Microsoft Advertising unter UET-Tag oder Conversion-Tracking ein. Es ist in jedem Modus erforderlich. |
| **CAPI token** | Leer | Fügen Sie im CAPI- oder Dualmodus das Bearer-Token aus dem Abschnitt „Conversions API“ des UET-Tags ein. Behandeln Sie es wie ein Passwort. |
| **Enable Ghost Collector (msclkid / anonymousId sync)** | Ja | Sammeln Sie Microsoft-Klick- und anonyme Besucher-IDs in CAPI-fähigen Modi, ohne UET-Tracking-Aufrufe durchzuführen. Lassen Sie es aktiviert, um eine stärkere Zuordnung und Sitzungskontinuität zu gewährleisten. |
| **Test** | Nicht ausgeführt | Validieren Sie im UET-Modus die Tag-ID und dann eine Storefront-Seitenansicht. Klicken Sie in CAPI-fähigen Modi auf **Send test purchase**, um einen Testkauf für 1 € zu senden. Es kann 10 bis 30 Minuten dauern, bis Microsoft Advertising es anzeigt. |
| **Done** | Unvollständig | Beenden Sie die Einrichtung und öffnen Sie Verknüpfungen zu **Tracking mode**, **Health & Data Quality Coach** oder **Live Statistics**. |

Verwenden Sie **Start over**, um den Assistenten erneut auszuführen. Vorhandene Anmeldeinformationen bleiben bis zur Änderung vorab ausgefüllt.

### 3.2 Tracking-Modus und Anmeldeinformationen

Wählen Sie aus, wie alle Ereignisse Microsoft Advertising erreichen, füllen Sie die für diesen Modus angezeigten Felder aus und klicken Sie auf **Save**.

![Tracking mode and credentials](https://mypresta.eu/docs/images/docs/mybing-tracking-mode.webp)

| Feld | Beim Start | Was es tut |
|---|---|---|
| **Tracking mode** | Nicht ausgewählt | **UET Tag** sendet vom Browser. **Conversions API** stellt Serverereignisse in die Warteschlange. **UET + CAPI** sendet beide mit derselben Ereignis-ID, damit Microsoft sie deduplizieren kann. |
| **Tag ID(s)** | Leer | Geben Sie eine UET-Tag-ID ein und drücken Sie Komma oder Eingabetaste. Die ID ist für UET, CAPI und Dual-Modus erforderlich. |
| **Conversions API token** | Leer | Fügen Sie den Inhabertoken von **Microsoft Advertising > UET tag > Use Conversions API > Copy Token** ein. |
| **CAPI endpoint override (advanced)** | Leer | Lassen Sie das Feld leer, um das Standardziel von Microsoft zu verwenden. Legen Sie es nur fest, wenn Microsoft einen benutzerdefinierten Host für Ihr Konto dokumentiert. |
| **Ghost collector (CAPI)** | Ja | Erfassen Sie `msclkid` und die anonyme Besucher-ID für den CAPI-Abgleich. Es wird kein UET-Tracking aufgerufen. |
| **Bing ID Sync (remarketing)** | Ja | Wenn UET aktiv ist, senden Sie die anonyme Besucher-ID über die Bing-ID-Synchronisierung, um den Remarketing-Zielgruppenabgleich zu verbessern. |

Kopieren Sie für CAPI oder Dual-Modus den angezeigten **CRON URL** in Ihren Planer und führen Sie ihn alle 1–5 Minuten aus.

### 3.3 Ereignisse

Wählen und speichern Sie zunächst einen Tracking-Modus. Aktivieren Sie dann nur die Signale, die Sie benötigen, und klicken Sie auf **Save**.

![Tracked events](https://mypresta.eu/docs/images/docs/mybing-events.webp)

| Feld | Beim Start | Was es tut |
|---|---|---|
| **PAGE_VIEW** | Ja | Zeichnen Sie jeden Laden der Storefront-Seite auf. Es unterstützt Verkehrsberichte und -zuordnung; Durch das Ausschalten werden andere Ereignisse nicht gestoppt. |
| **view_item (+ select_item)** | Ja | Senden Sie `view_item` auf Produktseiten und `select_item`, wenn auf ein Produkt in der Kategorie, Suche oder Bestsellerliste geklickt wird. |
| **view_item_list** | Ja | Senden Sie ungefähr die ersten 20 Produkte aus Kategorie-, Such- und Bestsellerlisten mit IDs, Namen, Preisen und Positionen. Es verfügt über einen eigenen Schalter. |
| **add_to_cart** | Ja | Erfassen Sie Warenkorb-Ergänzungen. UET und Dual-Modus verwenden das native Warenkorbereignis plus optionales CSS-Fallback. Der reine CAPI-Modus verwendet den Serverpfad und benötigt keine CSS-Selektoren. |
| **REMOVE_FROM_CART (Microsoft: Other)** | Ja | Erfassen Sie das Entfernen aus dem Einkaufswagen als **Other**, da Microsoft keinen nativen Typ zum Entfernen aus dem Einkaufswagen hat. |
| **CHECKOUT** | Ja | Wird ausgelöst, wenn der Kunde den Warenkorb oder den Bestellvorgang betritt, und markiert die Kaufabsicht. |
| **CHECKOUT details** | Ja | Fügen Sie Wert-, Währungs- und Produktdaten zu **CHECKOUT** hinzu. Wenn Sie es ausschalten, werden nur minimale Parameter gesendet. |
| **ADD_PAYMENT_INFO (Microsoft: Other)** | Ja | Feuern Sie den Zahlungsschritt als **Other** ab. Verwenden Sie es als optionales Late-Funnel-Signal für Live-Statistiken. |
| **purchase** | Ja | Senden Sie **OffMicrosoftPurchases** mit Bestellwert, Währung und Produktlinien. Eine stabile Client-Deduplizierungs-ID macht Aktualisierungen sicher. Verwenden Sie **Order lifecycle**, um die Zahlung bis zur Zahlung zu verzögern. |
| **SEARCH** | Ja | Erfassen Sie Filialsuchen mit dem Suchbegriff. |
| **ADD_TO_WISHLIST (Microsoft: Other)** | Ja | Erfassen Sie Ergänzungen zur Wunschliste als **Other**, wenn das Design kompatible Steuerelemente bereitstellt. |
| **SIGN_UP (Signup)** | Ja | Senden Sie **Signup**, wenn ein Kundenkonto erstellt wird. |
| **LEAD / SUBSCRIBE (newsletter)** | Ja | Senden Sie **Lead** für Newsletter-Abonnements. Deaktivieren Sie es, wenn ein anderes Tool dieselbe Konvertierung verfolgt. |
| **LEAD (legacy product interest)** | Nein | Behalten Sie das alte Produktinteresse-Lead-Verhalten bei. Lassen Sie es weg, es sei denn, eine historische Kampagne erfordert es; Die Verwendung mit `view_item` kann zu einer Aufblähung der Leitungen führen. |
| **CONTACT** | Ja | Wird ausgelöst, wenn das Kontaktformular gesendet wird, und nutzt dabei die Server- und Browser-Fallback-Erkennung. |
| **REFUND (Microsoft: Other)** | Ja | Wird ausgelöst, wenn eine Bestellung einen konfigurierten Rückerstattungs- oder Stornierungsstatus erreicht. Microsoft erhält es als **Other** zur lokalen Korrektur und Statistik. |
| **Rich product payloads (productId / items)** | Ja | Geben Sie Produkt-IDs, Mengen und Preise an. Wenn Sie es deaktivieren, bleiben nur minimale Wert-/Währungsdaten übrig, außer wenn für Listen- oder Klickereignisse IDs erforderlich sind. Lassen Sie es für den Katalogabgleich aktiviert. |
| **Add to cart CSS selector** | `.add-to-cart` | Identifizieren Sie im UET- und Dual-Modus die Produktseitenschaltfläche, wenn das Design das native Warenkorbereignis nicht auslöst. |
| **Product price CSS selector** | `.current-price span` | Lesen Sie im UET- und Dual-Modus den sichtbaren Fallback-Preis ab. Ein falscher Selektor sendet Null; Kombinieren Sie es bei Bedarf mit **Reformat price string**. |

Aktivieren Sie für CAPI **Advanced matching (email / phone)** und **Ghost collector (CAPI)** für eine bessere Übereinstimmung.

### 3.4 Katalog-IDs und Katalog-ID-Doktor

Stellen Sie sicher, dass die Ereignisprodukt-IDs genau mit Ihrem Microsoft Merchant Center-Feed übereinstimmen, klicken Sie auf **Save** und überprüfen Sie dann **Catalog ID Doctor**.

![Catalog IDs and Catalog ID Doctor](https://mypresta.eu/docs/images/docs/mybing-catalog.webp)

| Feld | Beim Start | Was es tut |
|---|---|---|
| **Product identification** | `id_product` | Wählen Sie die Produkt-ID, Kombinations-ID oder Produkt-ID plus Trennzeichen plus Kombinations-ID. Kombinierte IDs eignen sich für Feeds, die Varianten auflisten. Ein anderes Feedformat verhindert den Abgleich. |
| **Separator** | `-` | Separate Produkt- und Kombinations-IDs im kombinierten Modus. Produkt 12 und Kombination 5 werden zu `12-5`. Verwenden Sie im Feed das gleiche Trennzeichen. |
| **Product ID prefix** | Leer pro Sprache | Fügen Sie vor jeder ID nur dann einen sprachspezifischen Wert hinzu, wenn dieser auch im Feed verwendet wird. |
| **Product ID suffix** | Leer pro Sprache | Fügen Sie nach jeder ID nur dann einen sprachspezifischen Wert hinzu, wenn dieser auch im Feed verwendet wird. |
| **Exclude free products** | Nein | Lassen Sie Nullpreisprodukte aus dem Warenkorb aus und kaufen Sie Produktlinien und Wertberechnungen. |
| **Force currency conversion** | Nein | Konvertieren Sie alle Geldwerte in eine Zielwährung. Nur aktivieren, wenn die Shop-Währung von Microsoft Advertising nicht akzeptiert wird. |
| **Target currency** | Filialabhängige Auswahl | Wählen Sie die Zielwährung aus. Es wird ignoriert, solange die erzwungene Konvertierung deaktiviert ist. |
| **Reformat price string** | Nein | Bereinigen Sie im UET- oder Dual-Modus formatierte Designpreise, bevor sie vom CSS-Add-to-Cart-Fallback gelesen werden. Im reinen CAPI-Modus wird es nicht verwendet. |

**Catalog ID Doctor** zeigt generierte Beispiele aus einem aktiven Produkt und einer Kombination, aktuelle IDs, die in Ereignisdaten gefunden wurden, sowie Hinweise zur ausgewählten Basis-ID, zum Trennzeichen, zum Präfix und zum Suffix. Wenn **No active products found to validate catalog productId values** gemeldet wird, aktivieren Sie ein Produkt und öffnen Sie die Registerkarte erneut.

### 3.5 Datenschutz und Einwilligung

Konfigurieren Sie zunächst eine externe Einwilligungsquelle. Das Modul zeigt kein Cookie-Banner an.

![Privacy and consent](https://mypresta.eu/docs/images/docs/mybing-privacy.webp)

| Feld | Beim Start | Was es tut |
|---|---|---|
| **Require marketing / analytics consent** | Nein | Blockieren Sie UET, CAPI und Ghost, bis die Zustimmung erteilt wird. Ohne angeschlossenes CMP bleibt die Nachverfolgung stumm. |
| **Default consent state** | `auto` | `auto` wartet auf Cookie-, TCF- oder Browser-Ereignis-Zustimmung; `grant` ermöglicht sofort; `revoke` blockiert bis zur Gewährung. Verwenden Sie `auto` mit einem Banner und `grant` nur mit einer entsprechenden Rechtsgrundlage. |
| **IAB TCF 2.x (__tcfapi)** | Ja | Hören Sie einem zertifizierten CMP zu. Zweck 1 plus einer der Zwecke 2, 3 oder 4 schaltet Anzeigen frei und aktualisiert die Einwilligung zur Microsoft UET-Werbespeicherung. |
| **Include logged-in customer ID** | Nein | Fügen Sie die PrestaShop-Kunden-ID als optionales externes ID-Signal zum Anmeldekontext und zur Diagnose hinzu. Geben Sie es in der Datenschutzerklärung an. |
| **Advanced matching (email / phone)** | Nein | Senden Sie E-Mails und verfügbare gehashte E-Mail-/Telefonfelder für eine verbesserte UET- und CAPI-Zuordnung. Stellen Sie sicher, dass die Datenschutzrichtlinie dies abdeckt. Es wird dringend für CAPI empfohlen. |
| **Ignore admin / employee traffic** | Ja | Überspringen Sie die Storefront-Verfolgung, wenn eine Mitarbeitersitzung erkannt wird. |
| **Simple bot filter** | Nein | Überspringen Sie Anfragen, deren Browser-Identifikation einem Bot oder Crawler ähnelt. Das ist heuristisch. |

Konfigurieren Sie für ein EU-Setup das CMP, verwenden Sie `auto`, aktivieren Sie die erforderliche Zustimmung und lassen Sie TCF aktiviert, wenn es unterstützt wird. Testen Sie sowohl „Akzeptieren“ als auch „Ablehnen“ in einem privaten Browser. Der Leitfaden erkennt gängige Marketing-/Statistik-Cookies, sein eigenes Einwilligungs-Cookie und sein TCF-Ergebnis. Cookiebot-Rückrufe werden direkt unterstützt; Andere CMPs können das Zustimmungsereignis des Moduls auslösen.

### 3.6 Auftragslebenszyklus

Steuern Sie, wann Verkäufe und Rückerstattungen in die Conversion-Berichte eingehen.

![Order lifecycle](https://mypresta.eu/docs/images/docs/mybing-orders.webp)

| Feld | Beim Start | Was es tut |
|---|---|---|
| **Purchase only when paid** | Nein | Den Kauf verzögern, bis ein Bestellstatus bezahlt ist. Aktivieren Sie es, wenn unbezahlte Banküberweisungen oder Nachnahmebestellungen die Conversions in die Höhe treiben. |
| **Paid statuses** | Leer | Wählen Sie eine optionale Whitelist mit kostenpflichtigen Status aus. Lassen Sie das Feld leer, um die integrierte kostenpflichtige Flagge von PrestaShop zu verwenden. Eine ausgefüllte Liste wird verwendet, wenn die kostenpflichtige Nachverfolgung aktiviert ist. |
| **Refund / cancel statuses** | Leer | Wählen Sie Staaten aus, die eine Rückerstattung auslösen. „Leer“ verwendet die automatische Erkennung anhand von Statusnamen, die „Rückerstattung“ oder „Stornieren“ enthalten. Das Rückerstattungsereignis muss ebenfalls aktiviert sein. |

Aktivieren Sie bei verspäteter Zahlung die Sendungsverfolgung nur für kostenpflichtige Zahlungen, verschieben Sie eine Testbestellung in den kostenpflichtigen Status und überprüfen Sie, ob der Kauf einmal angezeigt wird.

### 3.7 Multi-Tag-Regeln

Verwenden Sie Regeln, wenn ein Shop, eine Sprache, ein Land oder eine Währung unterschiedliche Anmeldeinformationen erfordert. Die erste passende aktive Regel gewinnt in aufsteigender **Position**-Reihenfolge. Ohne Übereinstimmung werden globale Anmeldeinformationen verwendet.

![Multi-tag rules](https://mypresta.eu/docs/images/docs/mybing-multitag.webp)

Die **Active rules**-Liste zeigt **Tag ID**, CAPI-Token-Quelle, **Shop**, **Language**, **Country**, **Currency**, **Active** und **Actions**. Klicken Sie auf **Delete** und bestätigen Sie, um eine Regel zu entfernen. Es gibt keine Bearbeitungs- oder Massenaktionen; Erstellen Sie eine Regel neu, um sie zu ändern.

| Feld | Beim Start | Was es tut |
|---|---|---|
| **Tag ID (UET)** | Leer | Legen Sie das UET-Tag für passenden Datenverkehr fest. Es darf nur für eine Nur-Token-CAPI-Überschreibung leer sein. |
| **Conversions API token** | Leer | Überschreiben Sie das globale Token. Empty erbt das Token von **Tracking mode**. |
| **Shop** | **All shops** | Beschränken Sie die Regel auf einen Multistore-Shop oder alle Shops. |
| **Language** | **All languages** | Beschränken Sie es auf eine Storefront-Sprache oder alle Sprachen. |
| **Country** | **All countries** | Beschränken Sie es auf den aktuellen Kunden-Land-Kontext. |
| **Currency** | **All currencies** | Beschränken Sie es auf die aktuelle Währung. |
| **Active** | Ja | Aktivieren oder deaktivieren Sie die Regel. Inaktive Regeln werden ignoriert. |
| **Position** | `0` | Legen Sie die Bewertungsreihenfolge fest. Niedrigere Zahlen gewinnen, wenn mehrere Regeln übereinstimmen. |

Klicken Sie auf **Add rule**. **Property rule saved** bestätigt Erfolg. Wenn **Could not save rule — provide a valid Tag ID and/or Conversions API token.** angezeigt wird, korrigieren Sie die Tag-ID oder stellen Sie ein Token bereit.

### 3.8 Live-Statistiken

Öffnen Sie diese Registerkarte in einem Fenster und durchsuchen Sie die Storefront in einem anderen. Ereignisse erscheinen auf der 30-minütigen Echtzeit-Timeline.

![Live Statistics](https://mypresta.eu/docs/images/docs/mybing-live.webp)

**Recovery Radar** zeigt Käufe ohne Add-to-Cart, Add-to-Cart ohne Produktdetailansichten, Rückerstattungen im Vergleich zu Käufen und CAPI/Ghost-Wiederherstellung. Verwenden Sie Ereignis-Kontrollkästchen, um die Zeitleiste zu filtern. PageView ist standardmäßig ausgeblendet. **Pause** stoppt die Abfrage, ohne die Verfolgung zu stoppen, und **Refresh** ruft aktuelle Daten ab.

| Feld | Beim Start | Was es tut |
|---|---|---|
| **Enable live dashboard** | Ja | Schalten Sie die Timeline-Abfrage ein oder aus. Durch Ausschalten wird der Feed angehalten, während die Verfolgung und Gesundheits-/Radaraufzeichnungen fortgesetzt werden. |
| **Also log PageView into the event database** | Nein | Fügen Sie verrauschte PageView-Zeilen zum lokalen Protokoll hinzu. Es steuert nicht das Auslösen von Microsoft PageView oder andere Ereignisprotokolle. Nur zum Debuggen aktivieren. |
| **Keep events for (days)** | `14` | Bereinigen Sie Zeilen, die älter als dieses Alter sind. Akzeptierte Werte sind 1–365; 7–30 ist typisch. |
| **Live poll interval (seconds)** | `5` | Umfrage alle 2–60 Sekunden. Niedrigere Werte sind schneller, führen aber zu mehr Backoffice-Anfragen. |

Verwenden Sie **Purge older than retention**, **Delete failed only** oder **Clear entire event log** zur sofortigen Bereinigung. Das Löschen aller Elemente erfordert eine Bestätigung und kann nicht rückgängig gemacht werden. **Export recent events (CSV)** lädt aktuelle Nicht-PageView-Datensätze herunter.

### 3.9 Gesundheit und Diagnostik

Verwenden Sie diese Registerkarte nach der Einrichtung und immer dann, wenn Konvertierungen fehlen.

![Health and diagnostics](https://mypresta.eu/docs/images/docs/mybing-health.webp)

**Health Score** prüft Modus, Anmeldeinformationen, Warteschlangenaktualität, Ghost, PageView, Zustimmung, TCF, Kauf, Deduplizierung, aktuelle Fehler, Katalogformat und Datenqualität. Lesen Sie jede fehlgeschlagene Prüfung, nicht nur die Bezeichnung **Excellent**, **Good**, **Fair** oder **Needs work**.

Planen Sie für CAPI **CAPI CRON URL** alle 1–5 Minuten ein. Überprüfen Sie **Last CAPI flush**, verarbeitet, gesendet, ausstehend, fehlgeschlagen, Warteschlangensummen und Zeilen, die älter als 10 Minuten sind.

**Data Quality Coach** schätzt die passende Abdeckung aus aktuellen Servernutzlasten oder einem aktuellen Kaufmuster. Es listet vorhandene und fehlende Identifikatoren, erwartete Anstiege, Durchschnittswerte nach Ereignis und Korrekturen auf Shop-Ebene auf. Verbessern Sie die anonyme ID, `msclkid`, den erweiterten E-Mail-/Telefonabgleich und gegebenenfalls die optionale Kunden-ID. Bestätigen Sie die abschließende Diagnose in Microsoft Advertising.

| Feld | Beim Start | Was es tut |
|---|---|---|
| **Enable front debug inspector** | Nein | Zeigen Sie ein schwebendes Storefront-Overlay mit Ereignissen, Payloads, CAPI-Ziel, Warteschlangenstatus und Fehlern an. Schalten Sie es nach dem Test aus. Hängen Sie `?mybing_debug=1` vorübergehend an eine Storefront-URL an, um sie ohne Speichern zu aktivieren. |

Unter **Test & queue**:

- **Send test purchase** sendet eine Testkonvertierung; Überprüfen Sie Microsoft Advertising nach 10–30 Minuten.
- **Test CAPI token** prüft, ob Tag-ID und Token vorhanden sind.
- **Process CAPI queue** führt denselben Warteschlangenpfad wie CRON aus.

**Recent events log** zeigt Ereignis, ID, Kanal, Status, Antwort/Fehler, Datum und Ergebnis. Verwenden Sie **Re-send** für einen sofortigen Versuch oder **Re-add to queue** für den nächsten CRON-Lauf.

**Recent queue rows** zeigt Ereignisdetails, Status, Versuche, letzten Fehler und Aktualisierungszeit an. Verwenden Sie Aktionen pro Zeile oder **Re-send all failed now** und **Re-add all failed to queue**.

### 3.10 Updates

Suchen Sie hier nach einer neueren Modulversion.

![Updates](https://mypresta.eu/docs/images/docs/mybing-updates.webp)

| Feld | Beim Start | Was es tut |
|---|---|---|
| **Manual Check** | Kein Ergebnis | Klicken Sie auf **Check Now**, um den Update-Dienst einmal zu kontaktieren. Es zeigt **Module is up to date!** oder **New version available!**. |
| **Automatic Notifications** | Vorhandene gemeinsame Update-Einstellung | **Enabled** prüft etwa alle drei Tage und kann Mitarbeiter warnen. **Disabled** verlässt das Update-Management-Handbuch. |
| **Product Page** | Link angezeigt | Öffnen Sie die offizielle Modulseite für Versionsinformationen, Dokumentation und Supportzugriff. |

Klicken Sie nach dem Ändern der Benachrichtigungen auf **Save**.

## 4. Schaufenster

Das Modul fügt keinen sichtbaren Storefront-Block, kein Formular, keine Schaltfläche oder keine Kundenkontoseite hinzu. Kunden nutzen die normalen Produkt-, Warenkorb-, Checkout-, Registrierungs-, Newsletter-, Kontakt- und Bestätigungsbildschirme.

Produktseiten enthalten einen versteckten Produktdatenblock, der für die Nachverfolgung verwendet wird. Das sichtbare Thema wird dadurch nicht verändert. Wenn Debug aktiviert ist, wird ein schwebender Inspektor sichtbar; Deaktivieren Sie es nach dem Testen, da es Tracking-Details offenlegt.

Kopieren Sie für CAPI **CAPI CRON URL** von **Tracking mode** oder **Health & diagnostics** in den Hosting-Scheduler und führen Sie ihn alle 1–5 Minuten aus. Die geschützte URL verarbeitet Ereignisse in der Warteschlange und deren Aufbewahrung. Veröffentlichen Sie es nicht, da es einen Zugriffsschlüssel enthält.

Der Storefront-Datenendpunkt wird automatisch für Einwilligungs-, Besucher-IDs-, Warenkorb-, Seitenaufruf-, Checkout-, Kontakt- und Debug-Aktionen aufgerufen. Konstruieren oder öffnen Sie es nicht manuell.

| Sichtbare Nachricht | Was zu tun ist |
|---|---|
| Debug-Inspektor zeigt Zustimmung verweigert | Akzeptieren Sie die Marketingeinwilligung durch das CMP oder reparieren Sie die CMP-Verbindung. |
| Debug-Inspektor zeigt Warteschlange | an Führen Sie CRON oder **Process CAPI queue** aus und überprüfen Sie dann **Health & diagnostics**. |
| Debug-Inspektor zeigt fehlgeschlagen | Lesen Sie die Antwort in **Health & diagnostics**, korrigieren Sie die Anmeldeinformationen oder die Konnektivität und klicken Sie auf **Re-send**. |

## 5. Probleme

| Symptom | Ursache und Wirkung |
|---|---|
| Assistent bleibt unvollständig | Speichern Sie ggf. einen gültigen Modus, eine Tag-ID und ein Token. Führen Sie **Test** aus und beenden Sie **Done**. |
| Es werden keine UET-Ereignisse angezeigt | Speichern Sie eine gültige Tag-ID, schließen Sie UET in den Modus ein, aktivieren Sie das Ereignis, überprüfen Sie die Einwilligung und testen Sie in einer privaten Kundensitzung. |
| **Missing Tag ID and/or Conversions API token** | Geben Sie beides in **Tracking mode** ein, speichern Sie es und führen Sie **Test CAPI token** erneut aus. |
| CAPI-Ereignisse bleiben in der Warteschlange | Planen Sie **CAPI CRON URL** alle 1–5 Minuten, klicken Sie einmal auf **Process CAPI queue** und prüfen Sie **Last CAPI flush**. |
| CAPI-Test oder erneutes Senden schlägt fehl | Lesen Sie **Response / error**, korrigieren Sie Tag-ID/Token/Konnektivität, lassen Sie die Endpunktüberschreibung leer, es sei denn, Microsoft hat eine bereitgestellt, und versuchen Sie es erneut. |
| Das Tracking wird beendet, nachdem eine Einwilligung erforderlich ist | Konfigurieren Sie das externe CMP, verwenden Sie `auto`, verbinden Sie TCF oder seine Rückrufe, akzeptieren Sie dann die Marketingeinwilligung und testen Sie erneut. |
| Katalogprodukte stimmen nicht überein | Richten Sie **Product identification**, Trennzeichen, Präfix und Suffix am Feed aus und überprüfen Sie **Catalog ID Doctor**. |
| Einkäufe erscheinen vor der Zahlung | Aktivieren Sie **Purchase only when paid** und wählen Sie optional die genauen bezahlten Status aus. |
| Bezahlte Bestellungen führen nicht zum Kauf | Aktivieren Sie **purchase** und stellen Sie sicher, dass der Bestellstatus bezahlt oder in **Paid statuses** enthalten ist. |
| Rückerstattungen werden nicht angezeigt | Aktivieren Sie Rückerstattung und wählen Sie das richtige **Refund / cancel statuses** aus. |
| Ihre Tests werden ignoriert | Verwenden Sie einen privaten Browser ohne Mitarbeitersitzung oder deaktivieren Sie **Ignore admin / employee traffic** vorübergehend. |
| Bot-ähnlicher Testverkehr fehlt | Deaktivieren Sie **Simple bot filter** für den Test und stellen Sie es dann bei Bedarf wieder her. |
| UET-Add-to-Cart fehlt | Aktualisieren Sie die Schaltflächen- und Preis-CSS-Selektoren entsprechend dem Thema. |
| Der Wert für „In den Warenkorb“ ist Null oder falsch formatiert | Korrigieren Sie die Preisauswahl und aktivieren Sie bei Bedarf **Reformat price string**. |
| Zahlungsschritt Anderes Ereignis fehlt, obwohl der Schalter auf „Ja“ steht | Das Theme oder der Zahlungsschritt hat den Modulpfad nicht ausgelöst. Behandeln Sie dieses Signal als optional und überprüfen Sie den verbleibenden Trichter. |
| Live-Statistik wartet auf Ereignisse | Aktivieren Sie das Dashboard, setzen Sie es fort, löschen Sie die Filter, klicken Sie auf **Refresh** und durchsuchen Sie als Kunde die Storefront. |
| PageView erreicht Microsoft, ist aber lokal nicht vorhanden | Lokale PageView-Protokollierung vorübergehend aktivieren; es ist standardmäßig deaktiviert. |
| Es werden falsche Multi-Tag-Anmeldeinformationen verwendet | Löschen/erstellen Sie überlappende Regeln und weisen Sie der spezifischsten Regel die niedrigste Position zu. |
| Regel kann nicht gespeichert werden | Geben Sie eine gültige Tag-ID und/oder ein gültiges Token ein und klicken Sie dann auf **Add rule**. |
| Gesundheit warnt vor Datenqualität | Folgen Sie **Highest-impact fixes**, aktivieren Sie Ghost und Advanced Matching, sofern gesetzlich zulässig, und erfassen Sie gültige Checkout-Telefondaten. |
| Modulbildschirm sieht veraltet aus | Cache unter **Advanced Parameters > Performance** leeren und neu laden. |

## 6. Entwicklerreferenz

### 6.1 Architektur

Der technische Name ist `mybing`, Version `1.4.0`. Die Hauptklasse ist `mybing extends Module`; Listenname ist **Microsoft Advertising UET / Conversions API**, Autor `MyPresta.eu`, Kategorie `front_office_features`.

`MybingTrackerFactory` wählt `MybingUetTracker`, `MybingCapiTracker` oder `MybingHybridTracker` aus. `MybingEvents` erstellt Ereignisse; `MybingEventId` generiert und speichert Deduplizierungs-IDs. `MybingProductIdResolver`, `MybingCurrencyHelper` und `MybingUserData` normalisieren Katalog-, Geld- und Identitätsdaten. `MybingCapiClient` erstellt Anfragen, sendet sie und verwaltet Wiederholungsversuche. Leistungsdiagnosen `MybingLiveStats`, `MybingHealthScore`, `MybingDataQualityCoach` und `MybingCatalogDoctor`.

Der Dualmodus teilt eine Ereignis-ID zwischen Browser- und Serverkanälen. Der Standardendpunkt ist `https://capi.uet.microsoft.com/v1/{tagId}/events`. Jeder CRON-Aufruf verarbeitet bis zu 50 Warteschlangenzeilen und wendet eine Aufbewahrung an.

### 6.2 Dateien und Klassen

| Datei oder Klasse | Verantwortung |
|---|---|
| `mybing.php` | Installieren/Deinstallieren, Standardeinstellungen, Formulare, Aktionen, CRON, Frontkonfiguration und Hooks. |
| `classes/MybingTrackerInterface.php` | Tracker-Vertrag. |
| `classes/MybingTrackerFactory.php` | Modus- und Ereigniswechselauflösung. |
| `classes/MybingUetTracker.php` | Browser-Payloads und lokale UET-Datensätze. |
| `classes/MybingCapiTracker.php` | Serverzustellung und Warteschlangen. |
| `classes/MybingHybridTracker.php` | Duale Ausgabe und Deduplizierung. |
| `classes/MybingCapiClient.php` | Payloads, cURL, Antworten, Warteschlange, Wiederholungsversuche und Flush-Zusammenfassungen. |
| `classes/MybingEvents.php` | Umsetzung von Handelsveranstaltungen. |
| `classes/MybingEventMap.php` | Interne Ereigniszuordnung zu Microsoft. |
| `classes/MybingEventId.php` | Ereignis-IDs, Deduplizierung und Reparatur von Ereignistabellen. |
| `classes/MybingUserData.php` | Klick-/Besucher-IDs, Kundendaten, Normalisierung und Hashing. |
| `classes/MybingConsent.php` | Einwilligungserfordernis, Standardeinstellungen, Cookies und TCF. |
| `classes/MybingPropertyRules.php` | Kontextregelschema, Abgleich und Auflösung von Anmeldeinformationen. |
| `classes/MybingProductIdResolver.php` | Katalog-ID-Generierung. |
| `classes/MybingCurrencyHelper.php` | Währungskontext und Umrechnung. |
| `classes/MybingLiveStats.php` | Feed, Zusammenfassungen, Radar, Aufbewahrung und Bereinigung. |
| `classes/MybingHealthScore.php` | Gewichtete Gesundheitsprüfungen und Warteschlangendiagnose. |
| `classes/MybingDataQualityCoach.php` | Schätzungen zur Identitätsabdeckung. |
| `classes/MybingCatalogDoctor.php` | Beispiel- und aktuelle Produkt-IDs. |
| `controllers/admin/AdminMybingAjaxController.php` | Authentifizierte JSON-Backoffice-Brücke. |
| `controllers/front/ajax.php` | Tokengeschützter Tracking-JSON-Endpunkt. |
| `controllers/front/cron.php` | Schlüsselgeschützter JSON-Endpunkt der Warteschlange. |
| `views/js/mybing.js` | Haupteinbände und Versand vorne. |
| `views/js/mybing-tcf.js` | TCF-Zustimmungsbrücke. |
| `views/js/mybing-ghost.js` | Besucher-/Klick-ID-Synchronisierung. |
| `views/js/mybing-debug.js` | Vorderer Inspektor. |
| `views/js/mybing-admin.js`, `mybing-wizard.js`, `mybing-live.js` | Backoffice-Formulare, Assistent und Live-Dashboard. |
| `views/templates/hook/header.tpl` | UET, Zustimmung, Abgleich, Seitenaufruf, Ereignisse, Skript und ID-Synchronisierung. |
| `views/templates/hook/product-details.tpl` | Versteckter Produkt-JSON. |
| `views/templates/hook/displayOrderConfirmation.tpl` | Ausgabe des Browserkaufs. |
| `views/templates/hook/capi-pageview.tpl`, `ghost.tpl`, `debug.tpl` | CAPI-Seitenansicht, Ghost und Inspektorausgabe. |
| `views/templates/hook/payment.tpl` | Zahlungsereignisvorlage, die in 1.4.0 nicht von einem Hook-Handler aufgerufen wird. |
| `sql/install.php`, `sql/uninstall.php` | Benutzerdefinierte Tabellen erstellen/reparieren und löschen. |
| `lib/updateChecker.php` | Manuelle und regelmäßige Aktualisierungsprüfungen. |

### 6.3 Controller

`AdminMybingAjaxController extends ModuleAdminController` wird als versteckte Registerkarte `AdminMybingAjax` mit dem übergeordneten Register `-1` installiert. Es erfordert einen Mitarbeiter und gibt JSON aus. Aktionen: `liveFeed`, `liveRadar`, `liveClear`, `wizardSave`, `wizardTest`, `wizardComplete`, `wizardReset`, `dqReport`/`emqReport` und `exportCsv`.

`MybingAjaxModuleFrontController extends ModuleFrontController` ist nur SSL und JSON. Es akzeptiert den sicheren Schlüssel oder das generierte Front-Token. Aktionen: `ghost`, `consent`, `addToCart`, `removeFromCart`, `wishlist`, `selectItem`, `contact`, `beginCheckout`, `recalculate`, `pageview`, `ping` und nur Debug `inspect`. Zu den Fehlern gehören `invalid_token`, `disabled`, `empty_cart`, `invalid_currency`, `disabled_or_consent`, `debug_off` und `unknown_action`.

`MybingCronModuleFrontController` akzeptiert `key` oder `secure_key`, gibt JSON zurück, gibt HTTP 403 mit `access_denied` für ungültigen Zugriff aus und ruft `runCapiCron()` auf.

`controllers/front/index.php` sendet nur No-Cache-Header und leitet nach oben weiter.

### 6.4 Haken

| Registrierter Haken | Umsetzung |
|---|---|
| `displayHeader` | Filtert den Datenverkehr; Versendet Seiten-, Listen-, Produkt-, Checkout-, Such-, Kontakt- und Newsletter-Signale; rendert UET/Ghost/CAPI-Ausgabe. |
| `displayOrderConfirmation` | Löst die Bestellung auf, verfolgt den zulässigen Kauf und rendert die Browserausgabe. |
| `actionValidateOrder` | Verfolgt den Kauf bei der Erstellung, es sei denn, „Nur kostenpflichtig“ verzögert ihn. |
| `actionOrderStatusPostUpdate` | Verfolgt verspätete bezahlte Käufe und Rückerstattungs-/Stornierungsübergänge. |
| `actionCustomerAccountAdd` | Verfolgt die Anmeldung und speichert die Browserausgabe für die nächste Seite. |
| `actionFrontControllerSetMedia` | Fügt Frontkonfiguration und Haupt-, TCF-, Ghost- und Debug-Assets hinzu. |
| `displayPaymentTop` | Registriert, aber `hookDisplayPaymentTop()` ist in 1.4.0 nicht implementiert. |
| `displayFooter` | Rendert den Debug-Inspektor und den Warteschlangen-Bootstrap, wenn diese aktiviert sind. |
| `actionCartUpdateQuantityBefore`, `actionBeforeCartUpdateQty` | Verfolgen Sie Änderungen der Server-Warenkorbmenge; Letzterer delegiert an ersteren. |
| `actionObjectProductInCartDeleteBefore`, `actionObjectProductInCartDeleteAfter` | Machen Sie einen Snapshot und verfolgen Sie dann die vollständige Löschung der Warenkorbzeile. |
| `displayProductAdditionalInfo` | Rendert versteckte Produktdetails. |
| `actionNewsletterRegistrationAfter` | Verfolgt den Newsletter-Lead. |
| `displayContactContent` | Fügt die ausgeblendete Kontaktmarkierung hinzu. |

Es gibt keine benutzerdefinierten Methoden `enable()` oder `disable()`.

### 6.5 Datenbank

Das eigentliche PrestaShop-Präfix ersetzt `ps_`.

| Tabelle | Inhalt |
|---|---|
| `ps_mybing_events` | Name/ID des Ereignisses, Bestellung/Warenkorb/Shop, Kanal, Nutzlast, Status, HTTP-Code, Antwort, Datum, Suchindizes und eindeutiger Deduplizierungsschlüssel für Ereignis/Name/Shop. |
| `ps_mybing_properties` | Tag, Token, Shop-/Sprach-/Land-/Währungsauswahl, aktiv, Position und Datum. |
| `ps_mybing_queue` | Nutzlast, Versuche, Status, letzter Fehler, Erstellungs-/Aktualisierungsdaten. |

Die Installation wird mit `utf8` wiederholt, wenn `utf8mb4` fehlschlägt. `MybingPropertyRules::ensureSchema()` kann `tag_id` und `access_token` hinzufügen, wenn die Konfiguration geöffnet wird, und ein Legacy-Aktualisierungstoken migrieren. Das Ereignisschema fügt seinen eindeutigen Index sanft hinzu. Bei der Deinstallation werden alle drei Tabellen gelöscht.

### 6.6 Konfigurationsschlüssel

| Schlüssel | Vorgaben und Zweck |
|---|---|
| `MYBING_MODE` | Leer; Tracker-Modus. |
| `MYBING_TAG_ID`, `MYBING_CAPI_TOKEN`, `MYBING_CAPI_ENDPOINT` | Leer; globale Anmeldeinformationen/Ziel. |
| `MYBING_MSCLKID_DAYS`, `MYBING_ID_SYNC` | `90`, `1`; Click-ID Life und ID Sync. |
| `MYBING_PAGEVIEW`, `MYBING_PURCHASE`, `MYBING_PURCHASE_PAID_ONLY` | `1`, `1`, `0`. |
| `MYBING_LEAD`, `MYBING_LEAD_N`, `MYBING_INITIATE`, `MYBING_INITIATE_D` | `0`, `1`, `1`, `1`. |
| `MYBING_SEARCH`, `MYBING_ADDTOCART`, `MYBING_REMOVECART`, `MYBING_WISHLIST` | Alle `1`. |
| `MYBING_ADDPAYMENT`, `MYBING_CONTACT`, `MYBING_REFUND` | Alle `1`. |
| `MYBING_DPA`, `MYBING_VCONTENT`, `MYBING_VIEW_ITEM_LIST`, `MYBING_REG` | Alle `1`. |
| `MYBING_ATTRID`, `MYBING_SEPSIGN`, `MYBING_PREFIX`, `MYBING_SUFIX` | `0`, `-`, leer pro Sprache, leer pro Sprache. |
| `MYBING_EXFREE`, `MYBING_ATC_B`, `MYBING_ATC_PPP`, `MYBING_PREPRICE` | `0`, `.add-to-cart`, `.current-price span`, `0`. |
| `MYBING_CONCURR`, `MYBING_CURRSELECT` | `0`, `0`. |
| `MYBING_CONSENT_REQUIRED`, `MYBING_CONSENT_MODE`, `MYBING_TCF` | `0`, `auto`, `1`. |
| `MYBING_GHOST`, `MYBING_USER_ID`, `MYBING_ENHANCED_CONV` | `1`, `0`, `0`. |
| `MYBING_IGNORE_ADMIN`, `MYBING_BOT_FILTER`, `MYBING_DEBUG` | `1`, `0`, `0`. |
| `MYBING_PAID_STATUSES`, `MYBING_REFUND_STATUSES` | Leere durch Kommas getrennte Status-IDs. |
| `MYBING_STATS_ENABLED`, `MYBING_STATS_RETENTION`, `MYBING_STATS_POLL`, `MYBING_STATS_LOG_PV` | `1`, `14`, `5`, `0`. |
| `MYBING_WIZARD_DONE`, `MYBING_WIZARD_REDO` | `0`, `0`. |
| `MYBING_INSTALL_SQL_WARN`, `MYBING_INSTALL_ERROR` | Laufzeitinstallationsdiagnose. |
| `MYBING_LAST_FLUSH` | Zusammenfassung der Laufzeit-JSON-Flush; nicht in der Deinstallationsschlüsselliste. |

Durch die Einrichtung/Deinstallation werden auch die älteren Versionen `MYBING_CAPI_AUTH_CLIENT_ID`, `MYBING_CAPI_AUTH_CLIENT_SECRET`, `MYBING_CAPI_AUTH_REFRESH_TOKEN`, `MYBING_CAPI_AUTH_ACCESS_TOKEN`, `MYBING_CAPI_AUTH_ACCESS_EXPIRES`, `MYBING_PROFILE_ID`, `MYBING_CAPI_REGION`, `MYBING_CAPI_COUNTRY`, `MYBING_ATC_PC`, `MYBING_ATC_PP`, `MYBING_LINKER_DOMAINS` und `MYBING_ADS_ID` gelöscht. `MYBING_DEBUG_MODE` wird während des Setups gelöscht, fehlt jedoch in der Deinstallationsliste.

Der Updater verwendet `mypresta_updates`, `update_mybing` und `updatev_mybing`; Diese können nach der Deinstallation bestehen bleiben. `mypresta_updates` wird geteilt.

### 6.7 Deinstallation, Übersetzungen und Erweiterung

`uninstall()` löscht den ausgeblendeten Tab, entfernt alle Modultabellen und die Werte von `getConfigurationKeys()` sowie die Installationsdiagnose und ruft anschließend `parent::uninstall()` auf. Updater-Schlüssel oder `MYBING_LAST_FLUSH` werden nicht gelöscht.

Es gibt keine PrestaShop-Überschreibungen. Übersetzungen befinden sich in `translations/{iso}.php`; die meisten UI-Zeichenfolgen verwenden `$this->l()` oder Smarty `{l}`, während Ereignisnamen und einige Klassendiagnosen auf Englisch bleiben.

Themes können unterstützte Hooks neu positionieren und den Inspektor formatieren, aber der Produktblock ist absichtlich ausgeblendet. Behalten Sie Datenattribute und Skripte beim Überschreiben von Hook-Vorlagen bei. Ein benutzerdefinierter CMP kann `mybing.consent` mit der Bewilligung `1` oder `0` versenden oder ein von `MybingConsent` erkanntes Signal bereitstellen.

## 7. Hilfe

Öffnen Sie die Modulseite: https://mypresta.eu/modules/advertising-and-marketing/microsoft-advertising-uet-tag-conversions-api.html

Melden Sie sich bei Ihrem Kundenkonto auf mypresta.eu an, öffnen Sie die Kontaktseite und wählen Sie **Support for paid modules**. Anmeldung ist erforderlich; Wählen Sie dann dieses Modul aus Ihrer Kaufhistorie aus und geben Sie den Tracking-Modus, den sichtbaren Fehler und das Diagnoseergebnis an.
