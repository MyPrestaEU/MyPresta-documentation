---
title: "Bestellbilder-Uploader – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Bestellbilder-Uploader von MyPresta.eu."
sidebar:
  label: "Bestellbilder-Uploader – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Order images uploader auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/order-images-uploader.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/order-images-uploader/)
>
> ---


# Bestellbilder-Uploader

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Stellen Sie sicher, dass Ihr Server über ausreichende Dateiupload-Limits in `php.ini` verfügt (z. B. `upload_max_filesize`, `post_max_size`), um die Größe der Dateien zu berücksichtigen, die Ihre Kunden möglicherweise hochladen.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Bestellbilder-Uploader)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie das allgemeine Verhalten und Aussehen des Moduls steuern.

#### Allgemeine Einstellungen

- **Modul aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um die gesamte Funktionalität des Moduls ein- oder auszuschalten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Funktionen des Moduls (Upload-Formulare, Dateiverwaltung) sind in Ihrem Front Office und Back Office aktiv.
    - *Wenn deaktiviert:* Alle Modulfunktionen werden für Kunden und Administratoren ausgeblendet, wodurch der Betrieb effektiv pausiert wird.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Wenn Sie das Modul zum ersten Mal einrichten, aktivieren Sie es zum Testen. Wenn Sie Dateiuploads für Wartungsarbeiten vorübergehend deaktivieren müssen, stellen Sie es auf NEIN.
- **Kunden erlauben, Dateien hochzuladen:**

  - **Was diese Einstellung bewirkt:** Legt fest, ob Kunden überhaupt Dateien hochladen dürfen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden sehen Upload-Formulare und können Dateien einreichen.
    - *Wenn deaktiviert:* Kunden sehen keine Upload-Optionen, auch wenn das Modul aktiviert ist.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Wenn Sie das Modul nur für die interne Dateiverwaltung (z. B. Administratoren, die Dateien zu Bestellungen hochladen) verwenden möchten, können Sie dies deaktivieren. Für die meisten Anwendungsfälle müssen Kunden Dateien hochladen, also lassen Sie es aktiviert.
- **Gastkunden erlauben, Dateien hochzuladen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob nicht angemeldete Kunden (Gäste) Dateien hochladen können.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Gäste können Dateien hochladen, die typischerweise ihrem Warenkorb oder ihrer Bestellung während des Checkouts zugeordnet sind.
    - *Wenn deaktiviert:* Nur registrierte und angemeldete Kunden können Dateien hochladen.
  - **Empfohlener Wert:** JA (wenn Sie Gast-Checkout erlauben und Dateien von Gästen benötigen)
  - **Händlerszenario / Beispiel:** Wenn Ihr Shop Gast-Checkout erlaubt und Dateiuploads für Gastbestellungen erfordert (z. B. ein schneller Druckauftrag), aktivieren Sie dies. Wenn Sie Kunden zwingen möchten, sich zu registrieren, um Dateien hochzuladen, deaktivieren Sie es.
- **Kunden erlauben, Dateien zu löschen:**

  - **Was diese Einstellung bewirkt:** Gibt Kunden die Möglichkeit, zuvor hochgeladene Dateien zu entfernen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden sehen eine Option „Löschen“ neben ihren hochgeladenen Dateien in ihrem Konto.
    - *Wenn deaktiviert:* Kunden können hochladen, aber keine Dateien entfernen. Nur Administratoren können sie löschen.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie vertrauen den Kunden, ihre Dateien perfekt zu verwalten)
  - **Händlerszenario / Beispiel:** Bei kundenspezifischen Druckaufträgen möchten Sie dies möglicherweise deaktivieren, um zu verhindern, dass Kunden versehentlich eine Datei löschen, die bereits in Produktion ist. Wenn Dateien temporär oder leicht ersetzbar sind, können Sie es zur Bequemlichkeit des Kunden aktivieren.
- **Kunden erlauben, Dateien herunterzuladen:**

  - **Was diese Einstellung bewirkt:** Legt fest, ob Kunden Dateien herunterladen können, die sie (oder Sie) zu ihren Bestellungen hochgeladen haben.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können auf ihre Dateien klicken, um sie aus ihrer Bestellhistorie herunterzuladen.
    - *Wenn deaktiviert:* Kunden können keine Dateien herunterladen.
  - **Empfohlener Wert:** JA (für Transparenz und Kundenzugang)
  - **Händlerszenario / Beispiel:** Wenn Sie einen Proof oder ein endgültiges Design zur Überprüfung durch den Kunden hochladen, ermöglicht dies ihnen, es herunterzuladen.
- **Kunden erlauben, Dateien zu Bestellungen hochzuladen:**

  - **Was diese Einstellung bewirkt:** Steuert speziell, ob Kunden Dateien *nachdem* eine Bestellung aufgegeben wurde, von ihrer Bestellhistorie-Seite aus hochladen können.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Eine Upload-Option erscheint auf der individuellen Bestelldetailseite des Kunden unter „Mein Konto“.
    - *Wenn deaktiviert:* Kunden können Dateien nur während des Warenkorb-/Checkout-Prozesses oder auf Produktseiten hochladen, nicht zu bestehenden Bestellungen.
  - **Empfohlener Wert:** JA (sehr empfehlenswert für Flexibilität)
  - **Händlerszenario / Beispiel:** Ein Kunde hat vergessen, ein bestimmtes Logo hochzuladen, nachdem er T-Shirts mit individuellem Aufdruck bestellt hat. Wenn dies aktiviert ist, kann er es später problemlos hinzufügen.
- **Kunden erlauben, Dateien zu Warenkörben hochzuladen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob Kunden Dateien hochladen können, während sich ihre Artikel noch im Warenkorb befinden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Eine Upload-Option erscheint auf der Warenkorbseite.
    - *Wenn deaktiviert:* Kunden können keine Dateien zu ihrem Warenkorb hochladen.
  - **Empfohlener Wert:** JA (bequem für Kunden)
  - **Händlerszenario / Beispiel:** Ein Kunde erstellt ein individuelles Fotoalbum. Er kann Fotos direkt in den Warenkorb hochladen, bevor er zur Kasse geht.
- **Kunden erlauben, Dateien zu Produkten hochzuladen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob Kunden Dateien direkt auf einzelnen Produktseiten hochladen können.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Eine Upload-Option erscheint auf den Produktseiten.
    - *Wenn deaktiviert:* Kunden können keine Dateien auf Produktseiten hochladen.
  - **Empfohlener Wert:** JA (für hochgradig anpassbare Produkte)
  - **Händlerszenario / Beispiel:** Für eine personalisierte Tasse kann der Kunde sein gewünschtes Foto direkt auf der Produktseite der Tasse hochladen, bevor er es in den Warenkorb legt.
- **Kunden erlauben, Dateien zum Kundenkonto hochzuladen:**

  - **Was diese Einstellung bewirkt:** Aktiviert einen speziellen Bereich „Meine Dateien“ im Kundenkonto, der es ihnen ermöglicht, Dateien hochzuladen und zu verwalten, die nicht unbedingt an eine bestimmte Bestellung oder einen Warenkorb gebunden sind.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein neuer Menüpunkt „Meine Dateien“ erscheint im Dashboard „Mein Konto“ des Kunden.
    - *Wenn deaktiviert:* Dieser Bereich ist ausgeblendet.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie haben einen spezifischen Bedarf an allgemeiner Dateispeicherung)
  - **Händlerszenario / Beispiel:** Wenn Sie möchten, dass Kunden allgemeine Assets (z. B. ihr Firmenlogo) vorab hochladen, die sie möglicherweise für mehrere zukünftige Bestellungen verwenden, könnte dies nützlich sein. Andernfalls könnte es unnötige Komplexität hinzufügen.
- **Kunden zwingen, Dateien zu Bestellungen hochzuladen:**

  - **Was diese Einstellung bewirkt:** Macht den Dateiupload für den Abschluss einer Bestellung obligatorisch. Wenn keine Dateien hochgeladen werden, kann der Kunde nicht fortfahren.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden werden daran gehindert, den Checkout abzuschließen, bis sie mindestens eine Datei hochgeladen haben.
    - *Wenn deaktiviert:* Der Dateiupload ist optional.
  - **Empfohlener Wert:** NEIN (nur aktivieren, wenn für jede Bestellung absolut kritisch)
  - **Händlerszenario / Beispiel:** Für eine Druckerei, bei der *jede* Bestellung eine Designdatei erfordert, stellt dies sicher, dass keine Bestellung ohne die notwendigen Assets durchgeht. Seien Sie vorsichtig, da dies die Konversionsraten beeinträchtigen kann, wenn nicht jedes Produkt eine Datei erfordert.
- **Kunden zwingen, Dateien zu Produkten hochzuladen:**

  - **Was diese Einstellung bewirkt:** Macht den Dateiupload für das Hinzufügen eines Produkts zum Warenkorb obligatorisch.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können ein Produkt erst dann in den Warenkorb legen, wenn sie mindestens eine Datei für dieses Produkt hochgeladen haben.
    - *Wenn deaktiviert:* Der Dateiupload ist auf der Produktseite optional.
  - **Empfohlener Wert:** NEIN (nur für Produkte aktivieren, die *immer* personalisiert werden)
  - **Händlerszenario / Beispiel:** Für ein Produkt „Gestalten Sie Ihr eigenes T-Shirt“ stellt dies sicher, dass der Kunde sein Design bereitstellt, bevor er es in den Warenkorb legt.
- **Kunden zwingen, Dateien zu Warenkörben hochzuladen:**

  - **Was diese Einstellung bewirkt:** Macht den Dateiupload für die Bearbeitung des gesamten Warenkorbs obligatorisch.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können vom Warenkorb nicht zum Checkout übergehen, bis sie mindestens eine Datei für den Warenkorb hochgeladen haben.
    - *Wenn deaktiviert:* Der Dateiupload ist auf der Warenkorbseite optional.
  - **Empfohlener Wert:** NEIN (mit äußerster Vorsicht verwenden, kann die Konversion stark beeinträchtigen)
  - **Händlerszenario / Beispiel:** Dies wird selten empfohlen, es sei denn, *jede einzelne Bestellung* in Ihrem Shop erfordert einen allgemeinen Dateiupload. Es ist in der Regel besser, Uploads bei Bedarf auf Produkt- oder Bestellebene zu erzwingen.
- **Erlaubte Dateierweiterungen (durch Komma getrennt):**

  - **Was diese Einstellung bewirkt:** Definiert, welche Dateitypen Kunden hochladen dürfen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Bei Änderung:* Nur Dateien mit den angegebenen Erweiterungen (z. B. `jpg,png,gif,pdf`) werden akzeptiert. Jeder andere Dateityp wird abgelehnt.
  - **Empfohlener Wert:** `jpg,jpeg,png,gif,pdf,doc,docx,xls,xlsx,txt` (je nach Bedarf anpassen)
  - **Händlerszenario / Beispiel:** Eine Druckerei könnte `jpg,png,pdf,ai,eps` erlauben. Ein Schmuckgeschäft benötigt möglicherweise nur `jpg,png`. Die Begrenzung der Erweiterungen verbessert die Sicherheit und stellt sicher, dass Sie brauchbare Dateien erhalten.
- **Maximale Dateigröße (in MB):**

  - **Was diese Einstellung bewirkt:** Legt die Obergrenze für die Größe einer einzelnen Datei fest, die ein Kunde hochladen kann.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Bei Änderung:* Dateien, die größer als dieses Limit sind, werden abgelehnt.
  - **Empfohlener Wert:** `10` (oder höher, wenn Sie große Designdateien erwarten)
  - **Händlerszenario / Beispiel:** Wenn Kunden hochauflösende Bilder oder große Designdateien hochladen, können Sie dies auf `50` oder `100` setzen. Beachten Sie, dass sehr große Dateien Uploads verlangsamen und Serverplatz verbrauchen können. Stellen Sie sicher, dass `upload_max_filesize` und `post_max_size` in der `php.ini` Ihres Servers ebenfalls so konfiguriert sind, dass sie diesen Wert unterstützen.
- **Maximale Anzahl von Dateien pro Bestellung:**

  - **Was diese Einstellung bewirkt:** Begrenzt, wie viele einzelne Dateien ein Kunde für eine einzelne Bestellung hochladen kann.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Bei Änderung:* Kunden wird das Hochladen weiterer Dateien untersagt, sobald sie dieses Limit für eine bestimmte Bestellung erreicht haben.
  - **Empfohlener Wert:** `5` (oder höher, wenn viele Dateien erwartet werden)
  - **Händlerszenario / Beispiel:** Wenn ein Kunde 10 verschiedene personalisierte Artikel bestellt und jeder eine Datei benötigt, können Sie dies auf `10` oder `20` setzen. Wenn normalerweise nur ein oder zwei Dateien benötigt werden, verhindert eine niedrigere Zahl Unordnung.
- **Maximale Anzahl von Dateien pro Produkt:**

  - **Was diese Einstellung bewirkt:** Begrenzt, wie viele einzelne Dateien ein Kunde für ein einzelnes Produkt hochladen kann.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Bei Änderung:* Kunden wird das Hochladen weiterer Dateien untersagt, sobald sie dieses Limit für ein bestimmtes Produkt erreicht haben.
  - **Empfohlener Wert:** `1` (wenn jedes Produkt ein Design benötigt) oder `5` (wenn mehrere Winkel/Versionen benötigt werden)
  - **Händlerszenario / Beispiel:** Für ein individuelles Porträt können Sie `3` Dateien erlauben (Vorder-, Seiten-, Rückseitenreferenzfotos). Für einen einfachen Logodruck ist `1` Datei ausreichend.
- **Maximale Anzahl von Dateien pro Warenkorb:**

  - **Was diese Einstellung bewirkt:** Begrenzt, wie viele einzelne Dateien ein Kunde für den gesamten Warenkorb hochladen kann.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Bei Änderung:* Kunden wird das Hochladen weiterer Dateien untersagt, sobald sie dieses Limit für den Warenkorb erreicht haben.
  - **Empfohlener Wert:** `5` (oder höher, wenn viele allgemeine Dateien erwartet werden)
  - **Händlerszenario / Beispiel:** Wenn ein Kunde ein allgemeines Anweisungsdokument hochlädt, das für den gesamten Warenkorb gilt, können Sie dies auf `1` setzen.
- **Upload-Formular auf Produktseite anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, wo das Upload-Formular auf der Produktseite erscheint.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „Im Produkt-Tab“ gesetzt:* Das Upload-Formular erscheint in einem neuen Tab auf der Produktseite (z. B. neben „Beschreibung“ oder „Datenblatt“).
    - *Wenn auf „Unter Produktbeschreibung“ gesetzt:* Das Upload-Formular erscheint direkt unter der Hauptproduktbeschreibung.
    - *Wenn auf „Unter Produktpreis“ gesetzt:* Das Upload-Formular erscheint in der Nähe des Produktpreises, normalerweise über dem Button „In den Warenkorb“.
  - **Empfohlener Wert:** „Im Produkt-Tab“ (für weniger aufdringliche Anzeige) oder „Unter Produktpreis“ (für hohe Sichtbarkeit)
  - **Händlerszenario / Beispiel:** Für ein Produkt, bei dem der Dateiupload entscheidend ist, macht die Platzierung „Unter Produktpreis“ ihn sehr sichtbar. Für weniger kritische Uploads hält ein „Produkt-Tab“ die Hauptproduktinformationen sauber.
- **Upload-Formular auf Warenkorbseite anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, wo das Upload-Formular auf der Warenkorbseite erscheint.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „Im Zusammenfassungsblock“ gesetzt:* Das Upload-Formular erscheint im Hauptbereich der Warenkorbzusammenfassung.
    - *Wenn auf „Unter Warenkorbzusammenfassung“ gesetzt:* Das Upload-Formular erscheint unter der gesamten Warenkorbzusammenfassung.
  - **Empfohlener Wert:** „Unter Warenkorbzusammenfassung“ (bietet oft mehr Platz)
  - **Händlerszenario / Beispiel:** Wenn Kunden eine allgemeine Datei für die gesamte Bestellung hochladen müssen, stellt die klare Platzierung auf der Warenkorbseite sicher, dass sie diese vor dem Checkout nicht übersehen.
- **Upload-Formular auf Bestellhistorie-Seite anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, wo das Upload-Formular auf der individuellen Bestelldetailseite des Kunden erscheint.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „Im Bestelldetails-Block“ gesetzt:* Das Upload-Formular erscheint im Hauptbereich der Bestelldetails.
    - *Wenn auf „Unter Bestelldetails“ gesetzt:* Das Upload-Formular erscheint unter den Bestelldetails.
  - **Empfohlener Wert:** „Im Bestelldetails-Block“ (für eine engere Verbindung zur Bestellung)
  - **Händlerszenario / Beispiel:** Nachdem ein Kunde eine Bestellung aufgegeben hat, kann er die Upload-Option auf seiner Bestellhistorie-Seite leicht finden, um fehlende Dateien hinzuzufügen.
- **Upload-Formular auf „Mein Konto“-Seite anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob ein spezieller Link „Meine Dateien“ im Dashboard „Mein Konto“ des Kunden erscheint.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Link erscheint, der zu einer Seite führt, auf der Kunden allgemeine Dateien verwalten können.
    - *Wenn deaktiviert:* Der Link erscheint nicht.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie haben „Kunden erlauben, Dateien zum Kundenkonto hochzuladen“ aktiviert und benötigen diese Funktion)
  - **Händlerszenario / Beispiel:** Wenn Sie möchten, dass Kunden einen zentralen Ort für alle ihre hochgeladenen Dateien haben, unabhängig von bestimmten Bestellungen, aktivieren Sie dies.
- **Upload-Formular im Footer anzeigen:**

  - **Was diese Einstellung bewirkt:** Fügt einen Link zum Dateiupload-Manager in den Footer Ihres Shops ein.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Link erscheint im Footer und bietet einen weiteren Zugangspunkt zum Dateimanager.
    - *Wenn deaktiviert:* Kein Link im Footer.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie möchten eine hohe Sichtbarkeit für den Dateimanager)
  - **Händlerszenario / Beispiel:** Wenn Dateiuploads ein Kernbestandteil Ihres Geschäfts sind, kann ein Footer-Link sie von jeder Seite aus leicht zugänglich machen.
- **Upload-Formular in der linken Spalte anzeigen:**

  - **Was diese Einstellung bewirkt:** Fügt einen Link zum Dateiupload-Manager in die linke Spalte Ihres Shops ein.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Link erscheint in der linken Spalte.
    - *Wenn deaktiviert:* Kein Link in der linken Spalte.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie möchten eine hohe Sichtbarkeit für den Dateimanager)
  - **Händlerszenario / Beispiel:** Ähnlich wie der Footer bietet dies einen weiteren prominenten Zugangspunkt.
- **Upload-Formular in der rechten Spalte anzeigen:**

  - **Was diese Einstellung bewirkt:** Fügt einen Link zum Dateiupload-Manager in die rechte Spalte Ihres Shops ein.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Link erscheint in der rechten Spalte.
    - *Wenn deaktiviert:* Kein Link in der rechten Spalte.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie möchten eine hohe Sichtbarkeit für den Dateimanager)
  - **Händlerszenario / Beispiel:** Ähnlich wie der Footer und die linke Spalte bietet dies einen weiteren prominenten Zugangspunkt.
- **E-Mail an Kunden bei neuer Datei senden:**

  - **Was diese Einstellung bewirkt:** Steuert, ob eine E-Mail-Benachrichtigung an den Kunden gesendet wird, wenn eine neue Datei von einem Administrator zu seiner Bestellung hochgeladen wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden erhalten eine E-Mail-Benachrichtigung.
    - *Wenn deaktiviert:* Es wird keine E-Mail-Benachrichtigung gesendet.
  - **Empfohlener Wert:** JA (für gute Kundenkommunikation)
  - **Händlerszenario / Beispiel:** Wenn Sie einen Design-Proof zur Überprüfung durch den Kunden hochladen, wird dieser per E-Mail benachrichtigt.
- **E-Mail an Shop-Inhaber bei neuer Datei senden:**

  - **Was diese Einstellung bewirkt:** Steuert, ob eine E-Mail-Benachrichtigung an den Shop-Inhaber (oder die konfigurierte Shop-E-Mail-Adresse) gesendet wird, wenn ein Kunde eine neue Datei hochlädt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Sie (der Shop-Inhaber) erhalten eine E-Mail-Benachrichtigung.
    - *Wenn deaktiviert:* Es wird keine E-Mail-Benachrichtigung gesendet.
  - **Empfohlener Wert:** JA (sehr empfehlenswert für eine zeitnahe Bearbeitung)
  - **Händlerszenario / Beispiel:** Ein Kunde lädt eine kritische Designdatei hoch. Sie erhalten sofort eine E-Mail, sodass Sie die Bestellung ohne Verzögerung bearbeiten können.
- **Dateien an Bestellbestätigungs-E-Mail anhängen:**

  - **Was diese Einstellung bewirkt:** Legt fest, ob vom Kunden hochgeladene Dateien an die Standard-PrestaShop-Bestellbestätigungs-E-Mail angehängt werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Dateien werden als Anhänge in der an den Kunden gesendeten Bestellbestätigungs-E-Mail enthalten sein.
    - *Wenn deaktiviert:* Dateien werden nicht an die E-Mail angehängt.
  - **Empfohlener Wert:** NEIN (es sei denn, die Dateien sind klein und wenige, da große Anhänge E-Mail-Zustellungsprobleme verursachen können)
  - **Händlerszenario / Beispiel:** Wenn Kunden sehr kleine, unkritische Dateien hochladen, können Sie dies aktivieren. Bei größeren oder zahlreichen Dateien ist es besser, die Kunden sie von ihrem Konto herunterladen zu lassen, um E-Mail-Serverprobleme zu vermeiden.
- **Dateien an Kundendienst-E-Mail anhängen:**

  - **Was diese Einstellung bewirkt:** Legt fest, ob vom Kunden hochgeladene Dateien an die E-Mail angehängt werden, die an den Kunden gesendet wird, wenn ein Administrator eine neue Datei hochlädt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Dateien werden als Anhänge in der E-Mail enthalten sein.
    - *Wenn deaktiviert:* Dateien werden nicht an die E-Mail angehängt.
  - **Empfohlener Wert:** NEIN (ähnlich wie bei der Bestellbestätigung, große Anhänge vermeiden)
  - **Händlerszenario / Beispiel:** Wenn Sie einen kleinen Proof für den Kunden hochladen, können Sie dies aktivieren. Bei größeren Dateien leiten Sie sie an, diese von ihrem Konto herunterzuladen.
- **Dateien an Shop-Inhaber-E-Mail anhängen:**

  - **Was diese Einstellung bewirkt:** Legt fest, ob vom Kunden hochgeladene Dateien an die E-Mail angehängt werden, die an den Shop-Inhaber gesendet wird, wenn eine neue Datei von einem Kunden hochgeladen wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Dateien werden als Anhänge in der E-Mail-Benachrichtigung enthalten sein, die Sie erhalten.
    - *Wenn deaktiviert:* Dateien werden nicht an die E-Mail angehängt.
  - **Empfohlener Wert:** NEIN (es sei denn, die Dateien sind klein und wenige, da große Anhänge Ihren Posteingang verstopfen können)
  - **Händlerszenario / Beispiel:** Wenn Sie Dateien lieber direkt aus dem Back Office herunterladen möchten, deaktivieren Sie dies. Wenn Sie nur sehr kleine Dateien erwarten und diese sofort in Ihrem Posteingang haben möchten, aktivieren Sie es.
- **Kommentare für Dateien aktivieren:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Kunden und Administratoren, Kommentare zu jeder hochgeladenen Datei hinzuzufügen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Textfeld erscheint neben jeder Datei zum Hinzufügen von Notizen oder Anweisungen.
    - *Wenn deaktiviert:* Es sind keine Kommentarfelder verfügbar.
  - **Empfohlener Wert:** JA (für bessere Kommunikation und Kontext)
  - **Händlerszenario / Beispiel:** Ein Kunde lädt ein Logo hoch und fügt einen Kommentar hinzu: „Verwenden Sie dieses Logo, aber ändern Sie bitte die Farbe auf Blau.“ Dies liefert wichtigen Kontext.
- **Kommentare für Warenkörbe aktivieren:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Kunden, einen allgemeinen Kommentar zu ihrem Warenkorb hinzuzufügen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Textfeld erscheint auf der Warenkorbseite für allgemeine Warenkorbkommentare.
    - *Wenn deaktiviert:* Kein allgemeines Warenkorb-Kommentarfeld.
  - **Empfohlener Wert:** JA (nützlich für allgemeine Anweisungen)
  - **Händlerszenario / Beispiel:** Ein Kunde könnte einen Kommentar hinzufügen wie: „Bitte stellen Sie sicher, dass alle Artikel zusammen als Geschenk verpackt werden.“
- **Kommentare für Bestellungen aktivieren:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Kunden, einen allgemeinen Kommentar zu ihrer Bestellung hinzuzufügen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Textfeld erscheint auf der Bestelldetailseite für allgemeine Bestellkommentare.
    - *Wenn deaktiviert:* Kein allgemeines Bestellkommentarfeld.
  - **Empfohlener Wert:** JA (nützlich für Anweisungen nach der Bestellung)
  - **Händlerszenario / Beispiel:** Ein Kunde könnte nach dem Aufgeben einer Bestellung einen Kommentar hinzufügen: „Ich benötige dies bitte bis Freitag geliefert.“
- **Kommentare für Produkte aktivieren:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Kunden, einen produktspezifischen Kommentar hinzuzufügen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Textfeld erscheint auf der Produktseite für produktspezifische Kommentare.
    - *Wenn deaktiviert:* Kein produktspezifisches Kommentarfeld.
  - **Empfohlener Wert:** JA (nützlich für Anweisungen zur Produktpersonalisierung)
  - **Händlerszenario / Beispiel:** Ein Kunde, der eine individuelle Gravur bestellt, könnte einen Kommentar hinzufügen: „Gravieren Sie ‚Alles Gute zum Geburtstag John‘ in Schreibschrift.“
- **„Meine Dateien“-Tab im Kundenkonto aktivieren:**

  - **Was diese Einstellung bewirkt:** Fügt einen speziellen „Meine Dateien“-Tab zum Dashboard des Kundenkontos hinzu.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein neuer Tab erscheint, der es Kunden ermöglicht, alle ihre hochgeladenen Dateien an einem Ort anzuzeigen und zu verwalten.
    - *Wenn deaktiviert:* Der Tab ist ausgeblendet.
  - **Empfohlener Wert:** JA (verbessert das Kundenerlebnis durch Zentralisierung der Dateien)
  - **Händlerszenario / Beispiel:** Kunden können alle ihre hochgeladenen Designs, Proofs oder Dokumente an einem bequemen Ort leicht finden.
- **„Meine Dateien“-Tab auf Bestellhistorie-Seite aktivieren:**

  - **Was diese Einstellung bewirkt:** Fügt einen speziellen „Meine Dateien“-Bereich innerhalb der Bestellhistorie-Seite für jede spezifische Bestellung hinzu.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Bereich erscheint innerhalb der Detailseite jeder Bestellung, der Dateien anzeigt, die mit dieser spezifischen Bestellung zusammenhängen.
    - *Wenn deaktiviert:* Dieser Bereich ist ausgeblendet.
  - **Empfohlener Wert:** JA (entscheidend für die bestellspezifische Dateiverwaltung)
  - **Händlerszenario / Beispiel:** Wenn ein Kunde eine frühere Bestellung überprüft, kann er sofort alle Dateien sehen, die er für diese Bestellung hochgeladen hat.
- **„Meine Dateien“-Tab auf Produktseite aktivieren:**

  - **Was diese Einstellung bewirkt:** Fügt einen speziellen „Meine Dateien“-Bereich innerhalb der Produktseite hinzu.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Bereich erscheint auf der Produktseite, der Dateien anzeigt, die mit diesem spezifischen Produkt zusammenhängen.
    *Wenn deaktiviert:* Dieser Bereich ist ausgeblendet.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie haben einen sehr spezifischen Anwendungsfall, da dies Produktseiten überladen kann)
  - **Händlerszenario / Beispiel:** Dies könnte nützlich sein, wenn Kunden häufig dasselbe personalisierte Produkt nachbestellen und auf zuvor hochgeladene Dateien für dieses Produkt verweisen müssen.
- **„Meine Dateien“-Tab auf Warenkorbseite aktivieren:**

  - **Was diese Einstellung bewirkt:** Fügt einen speziellen „Meine Dateien“-Bereich innerhalb der Warenkorbseite hinzu.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Bereich erscheint auf der Warenkorbseite, der Dateien anzeigt, die mit den Artikeln im Warenkorb zusammenhängen.
    *Wenn deaktiviert:* Dieser Bereich ist ausgeblendet.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie haben einen sehr spezifischen Anwendungsfall, da dies Warenkorbseiten überladen kann)
  - **Händlerszenario / Beispiel:** Wenn Kunden eine komplexe Bestellung mit vielen Dateien erstellen, könnte dies einen Überblick über alle Dateien bieten, die derzeit dem Warenkorb zugeordnet sind.
- **Dateiupload-Button auf Produktseite anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit des Buttons „Datei hochladen“ auf Produktseiten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Button ist sichtbar.
    - *Wenn deaktiviert:* Der Button ist ausgeblendet.
  - **Empfohlener Wert:** JA (wenn Sie Produkt-Dateiuploads erlauben)
  - **Händlerszenario / Beispiel:** Wenn Sie möchten, dass Kunden Dateien zur Produktpersonalisierung hochladen, muss dieser Button sichtbar sein.
- **Dateiupload-Button auf Warenkorbseite anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit des Buttons „Datei hochladen“ auf der Warenkorbseite.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Button ist sichtbar.
    - *Wenn deaktiviert:* Der Button ist ausgeblendet.
  - **Empfohlener Wert:** JA (wenn Sie Warenkorb-Dateiuploads erlauben)
  - **Händlerszenario / Beispiel:** Wenn Kunden eine allgemeine Datei für ihre gesamte Bestellung hochladen müssen, muss dieser Button auf der Warenkorbseite sichtbar sein.
- **Dateiupload-Button auf Bestellhistorie-Seite anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit des Buttons „Datei hochladen“ auf der Bestelldetailseite des Kunden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Button ist sichtbar.
    - *Wenn deaktiviert:* Der Button ist ausgeblendet.
  - **Empfohlener Wert:** JA (wenn Sie Dateiuploads nach der Bestellung erlauben)
  - **Händlerszenario / Beispiel:** Wenn Kunden nach dem Aufgeben einer Bestellung Dateien hinzufügen müssen, muss dieser Button auf ihrer Bestellhistorie-Seite sichtbar sein.
- **Dateiupload-Button auf „Mein Konto“-Seite anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit des Buttons „Datei hochladen“ auf der Seite „Mein Konto“ des Kunden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Button ist sichtbar.
    *Wenn deaktiviert:* Der Button ist ausgeblendet.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie haben „Kunden erlauben, Dateien zum Kundenkonto hochzuladen“ aktiviert und benötigen diese Funktion)
  - **Händlerszenario / Beispiel:** Wenn Sie möchten, dass Kunden allgemeine Dateien in ihr Konto hochladen, muss dieser Button sichtbar sein.
- **Dateiupload-Button im Footer anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit des Buttons „Datei hochladen“ im Footer.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Button ist sichtbar.
    *Wenn deaktiviert:* Der Button ist ausgeblendet.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie möchten eine hohe Sichtbarkeit für den Dateimanager)
  - **Händlerszenario / Beispiel:** Wenn Dateiuploads ein Kernbestandteil Ihres Geschäfts sind, kann ein Footer-Button sie von jeder Seite aus leicht zugänglich machen.
- **Dateiupload-Button in der linken Spalte anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit des Buttons „Datei hochladen“ in der linken Spalte.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Button ist sichtbar.
    *Wenn deaktiviert:* Der Button ist ausgeblendet.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie möchten eine hohe Sichtbarkeit für den Dateimanager)
  - **Händlerszenario / Beispiel:** Ähnlich wie der Footer bietet dies einen weiteren prominenten Zugangspunkt.
- **Dateiupload-Button in der rechten Spalte anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit des Buttons „Datei hochladen“ in der rechten Spalte.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Button ist sichtbar.
    *Wenn deaktiviert:* Der Button ist ausgeblendet.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie möchten eine hohe Sichtbarkeit für den Dateimanager)
  - **Händlerszenario / Beispiel:** Ähnlich wie der Footer und die linke Spalte bietet dies einen weiteren prominenten Zugangspunkt.

#### Erweiterte Einstellungen

- **Debug-Modus aktivieren:**

  - **Was diese Einstellung bewirkt:** Aktiviert einen speziellen Modus, der zusätzliche Informationen und Fehlermeldungen anzeigt, hauptsächlich zur Fehlerbehebung.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Detailliertere Fehlermeldungen und Debugging-Informationen können auf dem Bildschirm oder in Protokollen erscheinen.
    - *Wenn deaktiviert:* Normaler Betrieb, Fehler werden unterdrückt oder stillschweigend protokolliert.
  - **Empfohlener Wert:** NEIN (nur bei Fehlerbehebung mit Support aktivieren)
  - **Händlerszenario / Beispiel:** Wenn Sie auf ein Problem stoßen und MyPresta.eu-Support mehr Informationen bereitstellen müssen, werden Sie möglicherweise gebeten, den Debug-Modus zu aktivieren.
- **Dateien löschen, wenn Bestellung gelöscht wird:**

  - **Was diese Einstellung bewirkt:** Entfernt automatisch alle zugehörigen hochgeladenen Dateien, wenn eine Bestellung aus dem PrestaShop Back Office gelöscht wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Dateien werden dauerhaft von Ihrem Server entfernt, wenn eine Bestellung gelöscht wird.
    - *Wenn deaktiviert:* Dateien verbleiben auf dem Server, auch wenn die zugehörige Bestellung gelöscht wird.
  - **Empfohlener Wert:** JA (um Ihren Server sauber zu halten und verwaiste Dateien zu vermeiden)
  - **Händlerszenario / Beispiel:** Wenn Sie häufig Testbestellungen löschen, verhindert dies, dass Ihr Server unnötige Dateien ansammelt.
- **Dateien löschen, wenn Produkt gelöscht wird:**

  - **Was diese Einstellung bewirkt:** Entfernt automatisch alle zugehörigen hochgeladenen Dateien, wenn ein Produkt aus dem PrestaShop Back Office gelöscht wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Dateien werden dauerhaft von Ihrem Server entfernt, wenn ein Produkt gelöscht wird.
    *Wenn deaktiviert:* Dateien verbleiben auf dem Server, auch wenn das zugehörige Produkt gelöscht wird.
  - **Empfohlener Wert:** JA (um Ihren Server sauber zu halten und verwaiste Dateien zu vermeiden)
  - **Händlerszenario / Beispiel:** Wenn Sie alte oder eingestellte Produkte entfernen, stellt dies sicher, dass auch die zugehörigen Dateien bereinigt werden.
- **Dateien löschen, wenn Warenkorb gelöscht wird:**

  - **Was diese Einstellung bewirkt:** Entfernt automatisch alle zugehörigen hochgeladenen Dateien, wenn ein Warenkorb aus dem PrestaShop Back Office gelöscht wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Dateien werden dauerhaft von Ihrem Server entfernt, wenn ein Warenkorb gelöscht wird.
    *Wenn deaktiviert:* Dateien verbleiben auf dem Server, auch wenn der zugehörige Warenkorb gelöscht wird.
  - **Empfohlener Wert:** JA (um Ihren Server sauber zu halten und verwaiste Dateien zu vermeiden)
  - **Händlerszenario / Beispiel:** Warenkörbe sind oft temporär. Dies verhindert, dass Ihr Server Dateien von abgebrochenen Warenkörben ansammelt.
- **Dateien löschen, wenn Kunde gelöscht wird:**

  - **Was diese Einstellung bewirkt:** Entfernt automatisch alle zugehörigen hochgeladenen Dateien, wenn ein Kundenkonto aus dem PrestaShop Back Office gelöscht wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Dateien werden dauerhaft von Ihrem Server entfernt, wenn ein Kunde gelöscht wird.
    *Wenn deaktiviert:* Dateien verbleiben auf dem Server, auch wenn der zugehörige Kunde gelöscht wird.
  - **Empfohlener Wert:** JA (für Datenschutz und Serverhygiene)
  - **Händlerszenario / Beispiel:** Wenn ein Kunde die Löschung seiner Daten beantragt (DSGVO-Konformität), stellt dies sicher, dass auch seine hochgeladenen Dateien gelöscht werden.
- **Dateien löschen, wenn Kundendatei gelöscht wird:**

  - **Was diese Einstellung bewirkt:** Wenn ein Administrator oder Kunde eine bestimmte Datei löscht, steuert diese Einstellung, ob die tatsächliche Datei vom Server entfernt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Datei wird dauerhaft vom Server entfernt.
    *Wenn deaktiviert:* Der Dateieintrag wird aus der Datenbank entfernt, aber die tatsächliche Datei verbleibt auf dem Server (verwaist).
  - **Empfohlener Wert:** JA (immer, um verwaiste Dateien zu verhindern und Speicherplatz zu sparen)
  - **Händlerszenario / Beispiel:** Wenn ein Kunde entscheidet, dass er eine Datei nicht mehr benötigt, wird durch das Löschen auch Serverplatz freigegeben.
- **Benutzerdefiniertes CSS aktivieren:**

  - **Was diese Einstellung bewirkt:** Bietet ein Textfeld, in dem Sie Ihre eigenen CSS-Regeln hinzufügen können, um das Erscheinungsbild der Modulelemente anzupassen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert und CSS hinzugefügt:* Ihre benutzerdefinierten Stile überschreiben oder ergänzen die Standardstile des Moduls.
    *Wenn deaktiviert oder leer:* Das Modul verwendet seine Standardstile.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie haben spezifische Designanforderungen und CSS-Kenntnisse)
  - **Händlerszenario / Beispiel:** Sie möchten die Farbe des Upload-Buttons an die Primärfarbe Ihrer Marke anpassen. Sie würden hier CSS-Regeln hinzufügen.
- **Benutzerdefiniertes CSS:**

  - **Was diese Einstellung bewirkt:** Dies ist das Textfeld, in das Sie Ihren benutzerdefinierten CSS-Code eingeben oder einfügen.
  - **Auswirkung der Änderung dieser Einstellung:** Das visuelle Erscheinungsbild der Modulelemente ändert sich gemäß Ihren CSS-Regeln.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie kennen CSS.
  - **Händlerszenario / Beispiel:** `button.upload-btn { background-color: #ff0000; color: white; }`

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul fügt neue Abschnitte zu Ihrem PrestaShop Back Office hinzu, um hochgeladene Dateien zu verwalten.

#### 2.2.1 Kunden-Dateimanager (Back Office > Bestellungen > Kunden-Dateien)

Dieser Bildschirm bietet Ihnen einen zentralen Ort, um alle von Ihren Kunden hochgeladenen Dateien anzuzeigen und zu verwalten.

- **Bildschirmname & Menüpfad:** **Kunden-Dateien** (zu finden unter dem Menü **Bestellungen** in PrestaShop 1.7/8/9. In älteren Versionen könnte es direkt unter dem Hauptmenü Module oder einem benutzerdefinierten Tab sein).
- **Verfügbare Aktionen & Einstellungen:**
  - **Dateilistentabelle:** Sie sehen eine Tabelle mit allen hochgeladenen Dateien. Jede Zeile zeigt typischerweise:
    - **Dateiname:** Der Name der hochgeladenen Datei.
    - **Kunde:** Der Name des Kunden, der die Datei hochgeladen hat (oder „Gast“, falls zutreffend).
    - **Bestell-ID:** Die ID der Bestellung, der die Datei zugeordnet ist.
    - **Produkt:** Der Produktname, wenn die Datei mit einem bestimmten Produkt verknüpft ist.
    - **Warenkorb-ID:** Die ID des Warenkorbs, dem die Datei zugeordnet ist.
    - **Datum des Uploads:** Wann die Datei hochgeladen wurde.
    - **Größe:** Die Größe der Datei.
    - **Aktionen:** Schaltflächen zum **Herunterladen** der Datei, **Details anzeigen** (einschließlich Kommentare) oder **Löschen** der Datei.
  - **Filtern & Suchen:** Sie können die Liste typischerweise nach Kunde, Bestell-ID filtern oder nach Dateiname suchen, um bestimmte Dateien schnell zu finden.
  - **Massenaktionen:** Optionen zum Auswählen mehrerer Dateien und Ausführen von Aktionen wie Massenlöschung.
- **Auswirkung von Änderungen:**
  - **Herunterladen einer Datei:** Speichert die Datei zur Überprüfung oder Bearbeitung auf Ihrem Computer.
  - **Löschen einer Datei:** Entfernt die Datei aus der Liste und, falls konfiguriert, von Ihrem Server.
  - **Details anzeigen:** Öffnet ein Pop-up oder eine neue Seite mit weiteren Informationen zur Datei, einschließlich aller zugehörigen Kommentare.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Überprüfen Sie diesen Bereich regelmäßig, insbesondere wenn Sie E-Mail-Benachrichtigungen für neue Uploads erhalten.
  2. Verwenden Sie die Filter, um schnell Dateien für bestimmte Bestellungen zu finden, die Sie bearbeiten.
  3. Laden Sie notwendige Dateien für Produktion, Design oder Überprüfung herunter.
  4. Fügen Sie Kommentare zu Dateien hinzu, wenn Sie mit dem Kunden oder Ihrem Team darüber kommunizieren müssen.
  5. Löschen Sie alte oder unnötige Dateien, um Ihren Server sauber zu halten.

#### 2.2.2 Integration der Bestelldetailseite (Back Office > Bestellungen > Bestellungen > Bestellung anzeigen)

Das Modul integriert sich auch direkt in die Standard-PrestaShop-Bestelldetailseite.

- **Bildschirmname & Menüpfad:** Wenn Sie eine bestimmte Bestellung unter **Back Office > Bestellungen > Bestellungen** anzeigen, finden Sie einen neuen Abschnitt oder Tab mit Bezug zu „Kunden-Dateien“ oder „Hochgeladene Dateien“.
- **Verfügbare Aktionen & Einstellungen:**
  - **Dateien für diese Bestellung:** Eine Liste aller Dateien, die speziell für die aktuelle Bestellung vom Kunden oder von einem Administrator hochgeladen wurden.
  - **Neue Datei hochladen:** Eine Option, um selbst als Administrator eine Datei hochzuladen und diese direkt dieser Bestellung zuzuordnen. Dies ist nützlich zum Hochladen von Proofs, finalen Designs oder internen Dokumenten.
  - **Kommentare hinzufügen:** Sie können Kommentare zu einzelnen Dateien oder einen allgemeinen Kommentar zur Bestellung hinzufügen.
  - **Herunterladen/Löschen:** Optionen zum Herunterladen oder Löschen einzelner Dateien, die dieser Bestellung zugeordnet sind.
- **Auswirkung von Änderungen:**
  - **Hochladen einer Datei als Admin:** Die Datei wird Teil der Bestellanhänge und ist für den Kunden in seiner Bestellhistorie sichtbar (falls konfiguriert).
  - **Hinzufügen von Kommentaren:** Bietet Kontext für die Datei oder Bestellung, sichtbar für den Kunden und andere Administratoren.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Wenn Sie eine Bestellung bearbeiten, die Kundendateien erfordert, navigieren Sie zur Bestelldetailseite.
  2. Überprüfen Sie die hochgeladenen Dateien im dafür vorgesehenen Bereich.
  3. Laden Sie Dateien bei Bedarf für die Produktion herunter.
  4. Wenn Sie einen Proof oder ein endgültiges Design erstellen, laden Sie es hier hoch, damit der Kunde darauf zugreifen kann.
  5. Verwenden Sie die Kommentarfelder, um mit dem Kunden zu kommunizieren oder interne Notizen zu hinterlassen.

### 2.3 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Modul aktivieren | JA | Hauptschalter für die Modulfunktionalität. |
| | Kunden erlauben, Dateien hochzuladen | JA | Kunden erlauben, Dateien einzureichen. |
| | Gastkunden erlauben, Dateien hochzuladen | JA | Nicht angemeldeten Benutzern erlauben, hochzuladen. |
| | Kunden erlauben, Dateien zu löschen | NEIN | Kunden daran hindern, Dateien zu entfernen. |
| | Kunden erlauben, Dateien herunterzuladen | JA | Kunden erlauben, ihre Dateien abzurufen. |
| | Kunden erlauben, Dateien zu Bestellungen hochzuladen | JA | Uploads nach der Bestellung über die Bestellhistorie aktivieren. |
| | Kunden erlauben, Dateien zu Warenkörben hochzuladen | JA | Uploads auf der Warenkorbseite aktivieren. |
| | Kunden erlauben, Dateien zu Produkten hochzuladen | JA | Uploads auf einzelnen Produktseiten aktivieren. |
| | Kunden erlauben, Dateien zum Kundenkonto hochzuladen | NEIN | Allgemeine Dateispeicherung in „Mein Konto“ aktivieren. |
| | Kunden zwingen, Dateien zu Bestellungen hochzuladen | NEIN | Dateiupload für den Bestellabschluss obligatorisch machen. |
| | Kunden zwingen, Dateien zu Produkten hochzuladen | NEIN | Dateiupload für das Hinzufügen von Produkten zum Warenkorb obligatorisch machen. |
| | Kunden zwingen, Dateien zu Warenkörben hochzuladen | NEIN | Dateiupload für das Fortfahren vom Warenkorb obligatorisch machen. |
| | Erlaubte Dateierweiterungen | `jpg,jpeg,png,gif,pdf,doc,docx,xls,xlsx,txt` | Dateitypen aus Sicherheits- und Benutzerfreundlichkeitsgründen einschränken. |
| | Maximale Dateigröße (MB) | `10` | Einzelne Dateigröße begrenzen. |
| | Maximale Anzahl von Dateien pro Bestellung | `5` | Dateien pro Bestellung begrenzen. |
| | Maximale Anzahl von Dateien pro Produkt | `1` | Dateien pro Produkt begrenzen. |
| | Maximale Anzahl von Dateien pro Warenkorb | `5` | Dateien pro Warenkorb begrenzen. |
| | Upload-Formular auf Produktseite anzeigen | „Im Produkt-Tab“ oder „Unter Produktpreis“ | Position des Upload-Formulars auf der Produktseite. |
| | Upload-Formular auf Warenkorbseite anzeigen | „Unter Warenkorbzusammenfassung“ | Position des Upload-Formulars auf der Warenkorbseite. |
| | Upload-Formular auf Bestellhistorie-Seite anzeigen | „Im Bestelldetails-Block“ | Position des Upload-Formulars auf der Bestellhistorie-Seite. |
| | Upload-Formular auf „Mein Konto“-Seite anzeigen | NEIN | „Meine Dateien“-Link im Kundenkonto anzeigen/ausblenden. |
| | Upload-Formular im Footer anzeigen | NEIN | „Meine Dateien“-Link im Footer anzeigen/ausblenden. |
| | Upload-Formular in der linken Spalte anzeigen | NEIN | „Meine Dateien“-Link in der linken Spalte anzeigen/ausblenden. |
| | Upload-Formular in der rechten Spalte anzeigen | NEIN | „Meine Dateien“-Link in der rechten Spalte anzeigen/ausblenden. |
| | E-Mail an Kunden bei neuer Datei senden | JA | Kunden benachrichtigen, wenn Admin eine Datei hochlädt. |
| | E-Mail an Shop-Inhaber bei neuer Datei senden | JA | Shop-Inhaber benachrichtigen, wenn Kunde eine Datei hochlädt. |
| | Dateien an Bestellbestätigungs-E-Mail anhängen | NEIN | Hochgeladene Dateien an Bestellbestätigung anhängen. |
| | Dateien an Kundendienst-E-Mail anhängen | NEIN | Hochgeladene Dateien an Kundendienst-E-Mail anhängen. |
| | Dateien an Shop-Inhaber-E-Mail anhängen | NEIN | Hochgeladene Dateien an Shop-Inhaber-Benachrichtigung anhängen. |
| | Kommentare für Dateien aktivieren | JA | Kommentare zu einzelnen Dateien erlauben. |
| | Kommentare für Warenkörbe aktivieren | JA | Allgemeine Kommentare zu Warenkörben erlauben. |
| | Kommentare für Bestellungen aktivieren | JA | Allgemeine Kommentare zu Bestellungen erlauben. |
| | Kommentare für Produkte aktivieren | JA | Kommentare zu einzelnen Produkten erlauben. |
| | „Meine Dateien“-Tab im Kundenkonto aktivieren | JA | Dedizierten „Meine Dateien“-Tab im Kundenkonto anzeigen. |
| | „Meine Dateien“-Tab auf Bestellhistorie-Seite aktivieren | JA | Dateibereich auf der Bestellhistorie-Seite anzeigen. |
| | „Meine Dateien“-Tab auf Produktseite aktivieren | NEIN | Dateibereich auf der Produktseite anzeigen. |
| | „Meine Dateien“-Tab auf Warenkorbseite aktivieren | NEIN | Dateibereich auf der Warenkorbseite anzeigen. |
| | Dateiupload-Button auf Produktseite anzeigen | JA | Sichtbarkeit des Upload-Buttons auf der Produktseite steuern. |
| | Dateiupload-Button auf Warenkorbseite anzeigen | JA | Sichtbarkeit des Upload-Buttons auf der Warenkorbseite steuern. |
| | Dateiupload-Button auf Bestellhistorie-Seite anzeigen | JA | Sichtbarkeit des Upload-Buttons auf der Bestellhistorie-Seite steuern. |
| | Dateiupload-Button auf „Mein Konto“-Seite anzeigen | NEIN | Sichtbarkeit des Upload-Buttons auf der Seite „Mein Konto“ steuern. |
| | Dateiupload-Button im Footer anzeigen | NEIN | Sichtbarkeit des Upload-Buttons im Footer steuern. |
| | Dateiupload-Button in der linken Spalte anzeigen | NEIN | Sichtbarkeit des Upload-Buttons in der linken Spalte steuern. |
| | Dateiupload-Button in der rechten Spalte anzeigen | NEIN | Sichtbarkeit des Upload-Buttons in der rechten Spalte steuern. |
| **Erweiterte Einstellungen** | Debug-Modus aktivieren | NEIN | Detaillierte Fehlermeldungen anzeigen. |
| | Dateien löschen, wenn Bestellung gelöscht wird | JA | Dateien entfernen, wenn zugehörige Bestellung gelöscht wird. |
| | Dateien löschen, wenn Produkt gelöscht wird | JA | Dateien entfernen, wenn zugehöriges Produkt gelöscht wird. |
| | Dateien löschen, wenn Warenkorb gelöscht wird | JA | Dateien entfernen, wenn zugehöriger Warenkorb gelöscht wird. |
| | Dateien löschen, wenn Kunde gelöscht wird | JA | Dateien entfernen, wenn zugehöriger Kunde gelöscht wird. |
| | Dateien löschen, wenn Kundendatei gelöscht wird | JA | Tatsächliche Datei vom Server entfernen, wenn gelöscht. |
| | Benutzerdefiniertes CSS aktivieren | NEIN | Benutzerdefinierte CSS-Eingabe aktivieren. |
| | Benutzerdefiniertes CSS | Leer lassen | Textfeld für benutzerdefinierte CSS-Regeln. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Kunden können keine Dateien hochladen oder erhalten eine Fehlermeldung.**
A1:

- **Modulstatus überprüfen:** Stellen Sie sicher, dass „Modul aktivieren“ und „Kunden erlauben, Dateien hochzuladen“ in der Modulkonfiguration beide auf JA gesetzt sind.
- **Dateityp & -größe:** Überprüfen Sie, ob der Dateityp (Erweiterung) und die Größe innerhalb der von Ihnen festgelegten „Erlaubte Dateierweiterungen“ und „Maximale Dateigröße“ liegen.
- **Server-Limits:** Ihr Hosting-Anbieter hat möglicherweise niedrigere PHP-Upload-Limits (`upload_max_filesize`, `post_max_size` in `php.ini`) als Ihre Moduleinstellungen. Kontaktieren Sie Ihren Host oder Webmaster, um diese bei Bedarf zu erhöhen.
- **Berechtigungen:** Stellen Sie sicher, dass das Upload-Verzeichnis des Moduls (normalerweise `modules/orderfiles/uploads/`) Schreibberechtigungen hat (z. B. 755 oder 777, obwohl 777 aus Sicherheitsgründen im Allgemeinen nicht empfohlen wird).
- **Debug-Modus:** Aktivieren Sie vorübergehend den „Debug-Modus“ in den erweiterten Einstellungen des Moduls und suchen Sie nach spezifischen Fehlermeldungen.

**F2: Das Upload-Formular wird auf meiner Produkt-/Warenkorb-/Bestellseite nicht angezeigt.**
A2:

- **Modulkonfiguration:** Überprüfen Sie die Einstellungen „Upload-Formular anzeigen auf…“ für die spezifische Seite (Produkt, Warenkorb, Bestellhistorie) in der Modulkonfiguration.
- **Hook-Konflikte:** Ein anderes Modul könnte die Anzeige-Hooks stören. Versuchen Sie, andere Module, die Produkt-, Warenkorb- oder Bestellseiten ändern, vorübergehend zu deaktivieren, um zu sehen, ob das Formular erscheint.
- **Theme-Kompatibilität:** Benutzerdefinierte Themes rendern möglicherweise Standard-PrestaShop-Hooks nicht korrekt. Wenn Sie ein benutzerdefiniertes Theme verwenden, müssen Sie möglicherweise einen Webmaster beauftragen, die Hooks des Moduls manuell in Ihre Theme-Dateien zu integrieren.
- **Cache:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Einstellungen > Leistung > Cache leeren) und Ihren Browser-Cache.

**F3: Ich erhalte keine E-Mail-Benachrichtigungen, wenn Kunden Dateien hochladen.**
A3:

- **Modulkonfiguration:** Stellen Sie sicher, dass „E-Mail an Shop-Inhaber bei neuer Datei senden“ auf JA gesetzt ist.
- **Shop-E-Mail:** Überprüfen Sie, ob die E-Mail-Adresse Ihres Shops (PS\_SHOP\_EMAIL in Erweiterte Einstellungen > E-Mail) korrekt konfiguriert ist und funktioniert.
- **E-Mail-Einstellungen:** Überprüfen Sie Ihre PrestaShop-E-Mail-Einstellungen (Erweiterte Einstellungen > E-Mail) und stellen Sie sicher, dass E-Mails erfolgreich gesendet werden (z. B. versuchen Sie, eine Test-E-Mail zu senden).
- **Spam-Ordner:** Überprüfen Sie Ihren Spam- oder Junk-Ordner auf die Benachrichtigungen.
- **Server-Mailer:** Die Mailfunktion Ihres Servers könnte falsch konfiguriert sein. Wenden Sie sich an Ihren Hosting-Anbieter.

**F4: Wie übersetze ich den Text des Moduls in andere Sprachen?**
A4:

- Navigieren Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
- Wählen Sie „Übersetzungen installierter Module“.
- Wählen Sie Ihr Theme, die Sprache, in die Sie übersetzen möchten, und wählen Sie dann „Bestellbilder-Uploader“ aus der Modulliste.
- Sie können dann alle sichtbaren Textzeichenfolgen des Moduls übersetzen.

**F5: Meine hochgeladenen Dateien werden nicht gelöscht, wenn ich eine Bestellung/ein Produkt/einen Kunden lösche.**
A5:

- **Modulkonfiguration:** Stellen Sie sicher, dass die entsprechenden Einstellungen „Dateien löschen, wenn…“ (z. B. „Dateien löschen, wenn Bestellung gelöscht wird“) in den erweiterten Einstellungen des Moduls auf JA gesetzt sind.
- **Manuelles Löschen:** Wenn diese Einstellungen deaktiviert waren, haben sich möglicherweise Dateien angesammelt. Sie müssen möglicherweise das Verzeichnis `modules/orderfiles/uploads/` auf Ihrem Server manuell bereinigen, um alte, verwaiste Dateien zu entfernen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Bestellbilder-Uploader“ folgt einer Standard-PrestaShop-Modularchitektur und nutzt MVC-Prinzipien. Es erweitert die Klasse `Module` für seine Kernfunktionalität und verwendet `ModuleFrontController` und `AdminController` zur Verarbeitung von Front-Office- bzw. Back-Office-Anfragen. Dateiuploads werden über dedizierte Controller und JavaScript verwaltet, um eine reibungslose Benutzererfahrung zu gewährleisten. Die Konfiguration wird in `ps_configuration` gespeichert, und benutzerdefinierte Daten (Dateidatensätze) werden über direkte Datenbankinteraktion oder potenziell ein benutzerdefiniertes `ObjectModel` verwaltet (obwohl in der Bestandsaufnahme keines explizit aufgeführt wurde, verwendet das Modul wahrscheinlich direktes SQL für Dateidatensätze).

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Diese Controller verwalten Kundeninteraktionen und Dateiverwaltung im Frontend.

- `controllers/front/customerfiles.php`
  - **Klassenname & Elternklasse:** `OrderFilesCustomerfilesModuleFrontController` erweitert `ModuleFrontController`
  - **Verantwortlichkeit:** Verwaltet den Bereich „Meine Dateien“ des Kunden, zeigt eine Liste seiner hochgeladenen Dateien an und ermöglicht es ihm, diese anzuzeigen, herunterzuladen und möglicherweise zu löschen. Es verarbeitet wahrscheinlich AJAX-Anfragen für Dateivorgänge in diesem Kontext.
- `controllers/front/download.php`
  - **Klassenname & Elternklasse:** `OrderFilesDownloadModuleFrontController` erweitert `ModuleFrontController`
  - **Verantwortlichkeit:** Verwaltet sichere Dateidownloads. Es überprüft Benutzerberechtigungen (z. B. ob die Datei dem angemeldeten Kunden gehört oder ob der Benutzer ein Administrator ist), bevor die Datei bereitgestellt wird, um unbefugten Zugriff zu verhindern.
- `controllers/front/filesmanager.php`
  - **Klassenname & Elternklasse:** `OrderFilesFilesmanagerModuleFrontController` erweitert `ModuleFrontController`
  - **Verantwortlichkeit:** Dies ist wahrscheinlich ein zentraler Controller für die Hauptdateiverwaltungsoberfläche, der möglicherweise für allgemeine Dateiuploads verwendet wird, die nicht an eine bestimmte Bestellung/ein bestimmtes Produkt gebunden sind, oder als Hub für alle Kundendateien.
- `controllers/front/index.php`
  - **Klassenname & Elternklasse:** `OrderFilesIndexModuleFrontController` erweitert `ModuleFrontController`
  - **Verantwortlichkeit:** Ein Platzhalter oder Standard-Front-Controller. In PrestaShop dient `index.php` in einem Controller-Verzeichnis oft als Fallback oder einfache Weiterleitung.
- `controllers/front/myfiles.php`
  - **Klassenname & Elternklasse:** `OrderFilesMyfilesModuleFrontController` erweitert `ModuleFrontController`
  - **Verantwortlichkeit:** Ähnlich wie `customerfiles.php` verwaltet dieser Controller wahrscheinlich den Bereich „Meine Dateien“ im Kundenkonto und bietet die Oberfläche zum Anzeigen und Verwalten persönlicher Dateien.
- `controllers/front/thumb.php`
  - **Klassenname & Elternklasse:** `OrderFilesThumbModuleFrontController` erweitert `ModuleFrontController`
  - **Verantwortlichkeit:** Generiert und liefert Miniaturansichten für hochgeladene Bilddateien, wodurch die Leistung und Anzeige in Dateilisten verbessert wird.
- `controllers/front/upload.php`
  - **Klassenname & Elternklasse:** `OrderFilesUploadModuleFrontController` erweitert `ModuleFrontController`
  - **Verantwortlichkeit:** Der Kern-Controller für die Verarbeitung aller Dateiupload-Anfragen vom Front Office (Produktseite, Warenkorbseite, Bestellhistorie, „Meine Dateien“). Er verarbeitet die hochgeladene Datei, validiert ihren Typ und ihre Größe, speichert sie auf dem Server und zeichnet ihre Details in der Datenbank auf. Er verarbeitet wahrscheinlich AJAX-Antworten für den Upload-Fortschritt und -Status.

#### Back-Office-Admin-Controller

Diese Controller stellen die administrative Schnittstelle zur Verwaltung hochgeladener Dateien bereit.

- `controllers/admin/customerFiles.php`
  - **Tab-Name und verwaltete Entität:** „Kunden-Dateien“ (unter dem Menü Bestellungen). Verwaltet die Auflistung, Anzeige, das Herunterladen und Löschen aller vom Kunden hochgeladenen Dateien im gesamten Shop. Es bietet eine umfassende Rasteransicht mit Filteroptionen.
- `controllers/admin/index.php`
  - **Klassenname & Elternklasse:** `AdminOrderFilesIndexController` erweitert `ModuleAdminController`
  - **Tab-Name und verwaltete Entität:** Ähnlich wie das Front-Office `index.php` könnte dies ein Platzhalter oder eine einfache Weiterleitung für den Admin-Bereich sein. Die primäre Dateiverwaltung wird von `AdminCustomerFilesController` übernommen.

### 4.3 Kernklassen & Modelle (`classes/`)

Das bereitgestellte Inventar zeigt keine benutzerdefinierten Klassen im Verzeichnis `classes/`. Dies deutet darauf hin, dass das Modul möglicherweise direkte Datenbankabfragen für die Dateiverwaltung verwendet oder Dateiinformationen direkt in `ps_configuration` oder einer benutzerdefinierten Tabelle ohne dediziertes `ObjectModel` speichert. Angesichts der Komplexität der Dateiverwaltung ist es wahrscheinlicher, dass Dateidatensätze in einer benutzerdefinierten Datenbanktabelle gespeichert und über direktes SQL oder eine einfache Hilfsklasse innerhalb der Hauptmoduldatei verwaltet werden.

### 4.4 JavaScript-Assets (`views/js/`)

Diese Skripte verbessern die Benutzererfahrung bei Dateiuploads und -verwaltung.

- `orderfiles/js/jquery.form.js`
  - **Geltungsbereich:** Front-Office und Back-Office (wo immer Formulare über AJAX gesendet werden).
  - **Beschreibung:** Ein jQuery-Plugin zum einfachen Senden von HTML-Formularen über AJAX, einschließlich Dateiuploads. Es verwaltet die Fortschrittsverfolgung und vereinfacht asynchrone Formularübermittlungen.
- `orderfiles/js/orders.js`
  - **Geltungsbereich:** Back-Office (speziell innerhalb von Bestelldetailseiten).
  - **Beschreibung:** Verwaltet wahrscheinlich die AJAX-Funktionalität zum Hochladen von Dateien direkt von der Admin-Bestelldetailseite, zum Anzeigen von Dateien, die einer Bestellung zugeordnet sind, und zum Verwalten von Kommentaren im Bestellkontext.
- `orderfiles/js/script-customers.js`
  - **Geltungsbereich:** Front-Office (Kundenkontoseiten, Bereich „Meine Dateien“).
  - **Beschreibung:** Verwaltet die interaktiven Elemente im Bereich „Meine Dateien“ des Kunden, einschließlich der Anzeige von Dateilisten, der Handhabung von Download-/Löschaktionen und potenziell AJAX-Updates für Dateistatus oder Kommentare.
- `orderfiles/js/script.js`
  - **Geltungsbereich:** Front-Office (Produktseiten, Warenkorbseiten, allgemeine Upload-Formulare).
  - **Beschreibung:** Das Haupt-Front-Office-JavaScript zur Handhabung von Dateiuploads. Es initialisiert wahrscheinlich die Upload-Formulare, verwaltet die Drag-and-Drop-Funktionalität, zeigt den Upload-Fortschritt an, validiert Dateitypen/-größen clientseitig und sendet AJAX-Anfragen an `upload.php`.

### 4.5 CSS-Stylesheets (`views/css/`)

Diese Stylesheets steuern die visuelle Darstellung der Modulelemente.

- `orderfiles/css/ajaxuploader.css`
  - **Geltungsbereich:** Front-Office und Back-Office (wo immer die AJAX-Uploader-Oberfläche verwendet wird).
  - **Beschreibung:** Stile für das Dateiupload-Widget selbst, einschließlich Fortschrittsbalken, Drag-and-Drop-Bereichen und Dateivorschau-Elementen.
  - **Wichtige CSS-Klassenselektoren:** `.ajax-uploader-container`, `.upload-drop-zone`, `.file-list`, `.progress-bar`
- `orderfiles/css/backoffice.css`
  - **Geltungsbereich:** Back-Office (Admin-Controller).
  - **Beschreibung:** Spezifisches Styling für die administrativen Schnittstellen des Moduls, wie die „Kunden-Dateien“-Liste und die Integration in die Bestelldetailseite.
  - **Wichtige CSS-Klassenselektoren:** `.orderfiles-admin-table`, `.orderfiles-order-details-block`
- `orderfiles/css/orderfiles.css`
  - **Geltungsbereich:** Front-Office (allgemeine Modulelemente).
  - **Beschreibung:** Allgemeines Styling für die Front-Office-Komponenten des Moduls, einschließlich Schaltflächen, Dateilisten und Kommentarbereichen auf Produkt-, Warenkorb- und Bestellhistorie-Seiten.
  - **Wichtige CSS-Klassenselektoren:** `.orderfiles-upload-form`, `.orderfiles-file-item`, `.orderfiles-comments`
- `orderfiles/css.css`
  - **Geltungsbereich:** Potenziell globales oder Fallback-Styling.
  - **Beschreibung:** Dies könnte ein älteres oder generisches Stylesheet sein. Entwickler sollten seinen Inhalt überprüfen, um seine spezifische Auswirkung zu verstehen, da `orderfiles.css` beschreibender ist.
  - **Wichtige CSS-Klassenselektoren:** (Erfordert Inspektion)

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

Diese Templates werden über PrestaShop-Hooks gerendert, um Modulinhalte in verschiedene Teile des Shops einzufügen.

- `displayProductPageUploadFormSmall.tpl`: Rendert ein kompaktes Upload-Formular auf der Produktseite.
- `filesmanager-orderhistory.tpl`: Zeigt die Dateimanager-Oberfläche auf der Bestellhistorie-Seite des Kunden an.
- `force-redirect.tpl`: Ein Dienstprogramm-Template, das möglicherweise für Weiterleitungen nach bestimmten Aktionen oder zur Erzwingung von Dateiuploads verwendet wird.
- `header.tpl`: Fügt CSS-/JS-Assets oder anderen notwendigen Code in den `<head>`-Bereich des Front Office ein.
- `my-account-17.tpl`: Rendert den „Meine Dateien“-Link/Tab für PrestaShop 1.7.x und neuere Kundenkonto-Dashboards.
- `my-account.tpl`: Rendert den „Meine Dateien“-Link/Tab für ältere PrestaShop-Versionen (z. B. 1.6.x) Kundenkonto-Dashboards.
- `orderConfirmation.tpl`: Zeigt Dateiupload-Optionen oder eine Zusammenfassung auf der Bestellbestätigungsseite an.
- `product-files-button.tpl`: Rendert den „Datei hochladen“-Button auf der Produktseite.
- `product-files.tpl`: Zeigt eine Liste von Dateien an, die einem Produkt zugeordnet sind, möglicherweise mit Upload-Optionen.
- `shopping-cart-force-files-alert.tpl`: Zeigt eine Warnmeldung an, wenn der Dateiupload auf der Warenkorbseite obligatorisch ist und keine Dateien hochgeladen wurden.
- `shopping-cart-qty-infos-alert.tpl`: Zeigt wahrscheinlich eine Warnmeldung bezüglich der Mengeninformationen im Warenkorb an, möglicherweise im Zusammenhang mit Dateiuploads.
- `shopping-cart.tpl`: Integriert Dateiupload-Funktionalität oder Dateilisten in die Warenkorbseite.
- `tab.tpl`: Ein generisches Tab-Template, das möglicherweise zum Erstellen neuer Tabs auf Produktseiten oder im Kundenkonto verwendet wird.

#### Admin-Templates (`views/templates/admin/`)

Diese Templates werden für die Back-Office-Schnittstellen des Moduls verwendet.

- `admin.tpl`: Das Hauptkonfigurations-Template für die `getContent()`-Methode des Moduls, das das Einstellungsformular rendert.
- `adminOrderDetailUpload.tpl`: Integriert die Dateiupload- und -verwaltungs-Oberfläche direkt in die PrestaShop-Bestelldetailseite im Back Office.
- `boscript.tpl`: Enthält JavaScript-Code speziell für das Back Office, der wahrscheinlich in Admin-Seiten enthalten ist.
- `bulk-delete-files.tpl`: Template für eine Massenlöschungs-Oberfläche oder -Bestätigung.
- `comments_cartfiles.tpl`: Rendert den Kommentarbereich für Dateien, die einem Warenkorb zugeordnet sind.
- `comments_orderfiles.tpl`: Rendert den Kommentarbereich für Dateien, die einer Bestellung zugeordnet sind.
- `comments_productfiles.tpl`: Rendert den Kommentarbereich für Dateien, die einem Produkt zugeordnet sind.
- `customerfilesmanager.tpl`: Das primäre Template für den `AdminCustomerFilesController`, das das Raster aller hochgeladenen Dateien anzeigt.
- `_configure/helpers/list/list_action_details.tpl`: Ein Hilfs-Template zum Anzeigen eines „Details“-Aktionsbuttons in einer Liste.
- `_configure/helpers/list/list_content.tpl`: Ein Hilfs-Template zum Rendern der Inhaltszeilen einer Liste.
- `_configure/prestashopbug/helpers/list/*.tpl`: Diese Templates scheinen spezifische Überschreibungen oder Korrekturen für die Standard-List-Helfer von PrestaShop zu sein, möglicherweise um Kompatibilitätsprobleme zu beheben oder die Listenanzeige für die Admin-Raster des Moduls anzupassen. Sie umfassen `list.tpl`, `list_action_delete.tpl`, `list_action_details.tpl`, `list_content.tpl`, `list_footer.tpl`, `list_header.tpl`.

#### Front-Office-Templates (`views/templates/front/`)

Dies sind eigenständige Templates für dedizierte Front-Office-Seiten.

- `access-denied.tpl`: Zeigt eine Meldung an, wenn ein Kunde versucht, auf eine Datei oder Seite ohne entsprechende Berechtigungen zuzugreifen.
- `customerfilesmanager.tpl`: Das Haupt-Template für die Seite „Meine Dateien“ des Kunden, das seine hochgeladenen Dateien anzeigt.
- `filesmanager.tpl`: Ein allgemeines Dateimanager-Template, das möglicherweise für eine breitere Dateiverwaltungsseite verwendet wird.
- `my-files.tpl`: Ein weiteres Template für den Bereich „Meine Dateien“, wahrscheinlich ähnlich wie `customerfilesmanager.tpl` oder eine spezifische Ansicht darin.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul erstellt wahrscheinlich mindestens eine benutzerdefinierte Datenbanktabelle, um Informationen über die hochgeladenen Dateien zu speichern.

- **`ps_orderfiles_files` (oder ähnlich):**
  - `id_order_file` (Primärschlüssel)
  - `id_customer` (Verknüpfung zu `ps_customer`)
  - `id_order` (Verknüpfung zu `ps_order`)
  - `id_cart` (Verknüpfung zu `ps_cart`)
  - `id_product` (Verknüpfung zu `ps_product`)
  - `filename` (Originalname der Datei)
  - `filepath` (Pfad zur gespeicherten Datei auf dem Server)
  - `file_extension`
  - `file_size`
  - `comment` (Benutzer-/Admin-Kommentare)
  - `date_add`
  - `date_upd`
  - `is_admin_upload` (Boolean, zur Unterscheidung von Kunden- vs. Admin-Uploads)
- **`ps_configuration`:** Speichert alle Moduleinstellungen (z. B. `OF_ALLOW_CUSTOMER_UPLOAD`, `OF_MAX_FILE_SIZE`, `OF_ALLOWED_EXTENSIONS`, `OF_CEMAIL_CUSTOMER`, `OF_CEMAIL_ATTACH` usw.). Diese Schlüssel sind mit `OF_` (Order Files) präfixiert.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Fügt CSS- (`orderfiles.css`, `ajaxuploader.css`) und JavaScript-Dateien (`jquery.form.js`, `script.js`, `script-customers.js`) des Moduls ein. |
| `displayProductAdditionalInfo` (oder ähnlicher Produktseiten-Hook) | Auf der Produktseite, typischerweise unter den Hauptproduktdetails. | Rendert `product-files.tpl` oder `displayProductPageUploadFormSmall.tpl` für produktspezifische Dateiuploads. |
| `displayShoppingCartFooter` (oder ähnlicher Warenkorbseiten-Hook) | Am unteren Rand der Warenkorbzusammenfassung. | Rendert `shopping-cart.tpl` für warenkorbweite Dateiuploads und Warnungen. |
| `displayCustomerAccount` | Im Dashboard „Mein Konto“ des Kunden. | Rendert `my-account.tpl` oder `my-account-17.tpl`, um den „Meine Dateien“-Link hinzuzufügen. |
| `displayMyAccountBlock` | Im Dashboard „Mein Konto“ des Kunden (Alternative für einige Themes). | Rendert `my-account.tpl` oder `my-account-17.tpl`, um den „Meine Dateien“-Link hinzuzufügen. |
| `displayOrderConfirmation` | Auf der Bestellbestätigungsseite nach einem erfolgreichen Kauf. | Rendert `orderConfirmation.tpl`, um Upload-Optionen oder Dateizusammenfassungen anzuzeigen. |
| `displayOrderDetail` | Auf der Bestelldetailseite des Kunden unter „Mein Konto“. | Rendert `filesmanager-orderhistory.tpl`, um Dateien anzuzeigen, die der spezifischen Bestellung zugeordnet sind. |
| `displayLeftColumn` | In der linken Spalte des Front Office. | Rendert `tab.tpl` (oder ähnlich), um einen Link zum Dateimanager anzuzeigen. |
| `displayRightColumn` | In der rechten Spalte des Front Office. | Rendert `tab.tpl` (oder ähnlich), um einen Link zum Dateimanager anzuzeigen. |
| `displayFooter` | Im Footer des Front Office. | Rendert `tab.tpl` (oder ähnlich), um einen Link zum Dateimanager anzuzeigen. |
| `actionObjectOrderAddAfter` | Nachdem eine neue Bestellung erfolgreich in die Datenbank aufgenommen wurde. | Löst E-Mail-Benachrichtigungen an den Shop-Inhaber aus, wenn ein Kunde während des Checkouts Dateien hochgeladen hat. |
| `actionObjectOrderDeleteAfter` | Nachdem eine Bestellung aus der Datenbank gelöscht wurde. | Löst die Dateilöschung vom Server aus, wenn „Dateien löschen, wenn Bestellung gelöscht wird“ aktiviert ist. |
| `actionObjectProductDeleteAfter` | Nachdem ein Produkt aus der Datenbank gelöscht wurde. | Löst die Dateilöschung vom Server aus, wenn „Dateien löschen, wenn Produkt gelöscht wird“ aktiviert ist. |
| `actionObjectCartDeleteAfter` | Nachdem ein Warenkorb aus der Datenbank gelöscht wurde. | Löst die Dateilöschung vom Server aus, wenn „Dateien löschen, wenn Warenkorb gelöscht wird“ aktiviert ist. |
| `actionObjectCustomerDeleteAfter` | Nachdem ein Kunde aus der Datenbank gelöscht wurde. | Löst die Dateilöschung vom Server aus, wenn „Dateien löschen, wenn Kunde gelöscht wird“ aktiviert ist. |
| `actionAdminOrdersControllerSaveAfter` | Nachdem eine Bestellung im Back Office gespeichert/aktualisiert wurde. | Verarbeitet potenziell Admin-Dateiuploads oder Kommentaraktualisierungen von der Bestelldetailseite. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller geladen wird und seine Medien-Assets gesetzt werden. | Fügt CSS- (`backoffice.css`) und JavaScript-Dateien (`orders.js`, `jquery.form.js`, `boscript.tpl`) des Moduls für die Back-Office-Funktionalität ein. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und technischen Support besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum Modul „Bestellbilder-Uploader“ zur Verfügung.
