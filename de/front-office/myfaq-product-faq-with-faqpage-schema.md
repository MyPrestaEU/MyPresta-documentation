---
title: MyFAQ - Dokumentation und Benutzerhandbuch
sidebar:
  label: MyFAQ - Dokumentation und Benutzerhandbuch
description: Anleitung zur Einrichtung und zur Fehlersuche für Shops, die MyFAQ bereits haben.
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul MyFAQ: product FAQ with FAQPage schema auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/myfaq-product-faq-with-faqpage-schema.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/myfaq-product-faq-with-faqpage-schema/)
>
> ---


## 1. Anforderungen

Dieses PrestaShop FAQ Modul läuft innerhalb von PrestaShop. Es braucht kein weiteres Modul.

- PrestaShop 1.7.0.0 bis PrestaShop 9. FAQ PrestaShop 8 und FAQ PrestaShop 9 sind dasselbe Paket und dieselben Bildschirme.
- PHP 7.0 oder neuer und mindestens die PHP-Version, die diese PrestaShop-Version verlangt. Installation und die geplante Adresse nutzen `random_bytes`.
- cURL ist nötig, wenn Sie Fragen erzeugen. Ohne cURL stoppt die Erzeugung, und die Fortschrittszeile zeigt `curl_missing`. Die Update-Prüfung nutzt cURL, wenn PHP es bereitstellt, und liest die Adresse direkt, wenn cURL fehlt und der Server entfernte Adressen lesen darf.
- OpenSSL verschlüsselt den gespeicherten KI-Schlüssel. Ohne OpenSSL bleibt der Schlüssel so gespeichert, wie Sie ihn eingeben.
- Kein weiteres Modul ist erforderlich. Die Produktseite des Themes muss die Produktfußzeile oder die zusätzlichen Produkt-Tabs ausgeben, sonst sieht der Kunde das Akkordeon nicht.
- Ein Konto bei OpenAI, Anthropic, Google, DeepSeek oder Mistral brauchen Sie nur für diesen Anbieter. Die kompatible Kachel kann auf Ihren eigenen Server zeigen, etwa Ollama, vLLM oder LM Studio, und dieser Server kann ohne externes Konto laufen.
- Ein externes System brauchen Sie nur, wenn Sie die FAQ-Adresse von außerhalb des Shops aufrufen. Einen Zeitplan brauchen Sie nur, wenn der Server eine Warteschlange fertigschreiben soll, während das Backoffice geschlossen ist.

Ein großer Katalog wird Sprache für Sprache geschrieben. Lassen Sie die Seite **Massengenerierung** offen, bis der Balken 100 % erreicht, oder planen Sie die Adresse von dort. Jeder Aufruf arbeitet etwa 20 Sekunden und stoppt dann, damit das PHP-Zeitlimit nicht greift. Ein Aufruf schreibt höchstens 30 Sprachen.

## 2. Installation

1. Öffnen Sie im Backoffice **Module**, dann **Modul-Manager**.
2. Laden Sie die Zip-Datei hoch und klicken Sie auf **Installieren**.
3. Öffnen Sie **Konfigurieren** bei **MyFAQ**. Die Seite öffnet **Anzeige**. In der Leiste stehen außerdem **Einträge**, **KI**, **Massengenerierung**, **API** und **Updates**.
4. MyFAQ legt keinen eigenen Punkt im linken Menü an. Katalog, Schlüsselliste und Anfrageverlauf sind versteckte Seiten. Das erste Öffnen von **Konfigurieren** legt sie an und gibt dem aktuellen Mitarbeiterprofil das Recht, sie zu öffnen.
5. Die Installation leert den Cache nicht in einem eigenen Schritt. Zeigt die Produktseite nach einem Update noch das alte Layout, leeren Sie den Cache unter **Erweiterte Parameter**, **Leistung**.

Öffnen Sie bei einem Produkt das Produkt und den Block **MyFAQ**. Dort setzen Sie die Platzierung für dieses eine Produkt und schreiben Fragen, die nur dazu gehören.

Zum Abschalten nutzen Sie den Schalter im **Modul-Manager**. Die Produktseite gibt das Akkordeon nicht mehr aus, und die Produktbearbeitung zeigt den MyFAQ-Block nicht mehr. Fragen, Schlüssel und Einstellungen bleiben. Schalten Sie das Modul wieder ein, werden sie wie zuvor verwendet. Das Modul hat keinen eigenen Schalter zum Aktivieren oder Deaktivieren.

Zum Entfernen klicken Sie auf **Deinstallieren** und bestätigen. Die Deinstallation entfernt die versteckten Seiten, Fragen und Antworten, Verknüpfungen, die Platzierung je Produkt, die API-Schlüssel, den Anfrageverlauf, die Erzeugungswarteschlange sowie die Anzeige- und KI-Einstellungen. Die beiden geplanten Adressen hören auf zu funktionieren, weil das Geheimnis darin entfernt wird. Die Moduldateien bleiben auf dem Server, bis Sie das Modul löschen. Eine erneute Installation startet mit leeren Einträgen und den Einstellungen einer frischen Installation. Die alten Fragen kommen nicht zurück. Der Schalter der Update-Prüfung wird dabei nicht gelöscht.

## 3. Konfiguration und tägliche Arbeit

Sie schreiben eine Frage und eine Antwort und verknüpfen den Eintrag mit einem Produkt oder mit etwas, das das Produkt schon hat: einer Kategorie, einem Merkmalswert, einem Attributwert, einem Schlagwort, einer Marke oder einem Lieferanten. Eine passende Verknüpfung genügt. Die FAQ auf der Produktseite ist das Akkordeon: der Shop sammelt jede aktive Übereinstimmung in der Sprache des Kunden, ersetzt die Token und gibt es aus. Einträge, die direkt am Produkt hängen, kommen zuerst. Danach gilt die Position, die Sie setzen.

Die FAQ in der Produktfußzeile steht unter dem Produkt. Der FAQ Tab Produktseite ist dasselbe Akkordeon in einem Tab. Bei einem Produkt können Sie die Fußzeile erzwingen, den Tab erzwingen oder MyFAQ ausblenden. **Ausblenden** entfernt auch den FAQ-Block, den Suchmaschinen lesen. Der Kunde öffnet nur die Fragen. Es gibt kein Formular, mit dem der Kunde eine neue Frage sendet. Der Weg endet, wenn die Produktseite das Akkordeon zeigt, oder wenn die Platzierung **Ausblenden** ist oder kein aktiver Eintrag passt. Dann zeigt dieses Produkt keinen MyFAQ-Block.

Schreiben mit einem Modell ist optional. Anbieter und Schlüssel speichern Sie unter **KI**. Das Speichern erzeugt nichts. **Generieren** an einem Produkt oder **Generierung starten** unter **Massengenerierung** stellt die Arbeit in die Warteschlange. Jede Sprache eines Produkts ist eine Anfrage. **Anhängen** behält die vorhandenen KI-Einträge und fügt neue hinzu. **Nicht gesperrte KI-Einträge ersetzen, die nur mit dem Produkt verknüpft sind** löscht nicht gesperrte KI-Einträge, die nur an diesem Produkt hängen, und schreibt dann neue. Ein Eintrag, den Sie bearbeitet haben, ist gesperrt und bleibt. Ein Eintrag, der auch an einer Kategorie oder einem anderen Ziel hängt, bleibt. Die geplante Adresse liest die Filter von **Massengenerierung** nicht. Sie schließt eine Warteschlange ab, die schon besteht, oder fügt mit der zweiten Adresse jedes aktive Produkt dieses Shops hinzu, das noch keinen KI-Eintrag hat.

Ein externes System ist optional. Unter **API** erzeugen Sie einen Schlüssel, kopieren die Basisadresse und fügen beides in dieses System ein.

Öffnen Sie **Module**, **Modul-Manager**, **MyFAQ**, **Konfigurieren**. Die Zeile unter der Leiste erklärt den offenen Bereich.

### 3.1 Anzeige

![Anzeige](https://mypresta.eu/docs/images/docs/myfaq-configure-display.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt der Abschnitt **Anzeige**.

**Anzeige** ist die Darstellung für den ganzen Shop. Ein einzelnes Produkt kann eine andere Platzierung nutzen.

| Feld | Am Anfang | Wirkung |
|---|---|---|
| **Platzierung** | Produktfußzeile | Shop-Standard für jedes Produkt, das keine eigene Platzierung setzt. **Produktfußzeile** gibt das Akkordeon unter dem Produkt aus. **Produkt-Tab** fügt einen Tab auf der Produktseite hinzu. An einem Produkt können Sie Fußzeile, Tab oder Ausblenden weiterhin erzwingen. Andere Module am selben Hook bleiben dort, wo **Design**, **Positionen** sie setzt. |
| **Tab-Titel** | FAQ in jeder Sprache | Beschriftung des Produkt-Tabs. Sie wird nur genutzt, wenn die Platzierung **Produkt-Tab** ist. Füllen Sie sie in jeder Sprache, in der der Shop verkauft. Eine leere Sprache zeigt FAQ. |
| **Überschrift über der Liste** | FAQ in jeder Sprache | Überschrift über den Fragen, in der Fußzeile und im Tab. Füllen Sie sie je Sprache. Kunden sehen diesen Text. Lassen Sie FAQ stehen, wenn Sie keine eigene Überschrift brauchen. |
| **Übergeordnete Kategorien einbeziehen** | Nein | **Ja** zeigt auch einen Eintrag, der an einem Elternteil der Produktkategorien hängt, sodass eine Verknüpfung die Unterkategorien abdeckt. Der Gang stoppt vor Home, eine Verknüpfung mit Home deckt also nicht den ganzen Katalog ab. **Nein** trifft nur die Kategorien, in denen das Produkt direkt liegt. |
| **Erste Frage öffnen** | Nein | **Ja** klappt die erste Antwort beim Laden der Seite auf. **Nein** lässt jede Antwort zu, bis der Kunde klickt. Kunden ohne JavaScript sehen die Antworten immer. |
| **FAQ-Schema-Markup** | Ja | **Ja** fügt einen schema.org-FAQPage-Block hinzu, gebaut aus den Fragen, die auf diesem Produkt wirklich gezeigt werden, nach dem Ersetzen der Shortcodes. Suchmaschinen können ihn für FAQ-Ergebnisse nutzen. **Nein** gibt die FAQ ohne diesen Block aus. Eine leere Liste und ein ausgeblendetes Produkt geben ihn nie aus. |

Klicken Sie auf **Speichern**. Die Seite zeigt **Gespeichert.**

### 3.2 Einträge

![Einträge](https://mypresta.eu/docs/images/docs/myfaq-configure-entries.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt der Abschnitt **Einträge**.

**Einträge** ist eine Vorschau der Fragen. Die Zeile unter der Leiste sagt, dass dies die 10 zuletzt aktualisierten Einträge sind und dass **Neuer Eintrag** und **Bearbeiten** den Katalog öffnen.

| Feld | Am Anfang | Wirkung |
|---|---|---|
| **Neuer Eintrag** | eine Schaltfläche | Öffnet das Katalogformular für eine neue Frage. |
| **Vollständige Liste anzeigen** | eine Schaltfläche | Öffnet den durchsuchbaren Katalog, in dem Sie die Reihenfolge ändern und einen Eintrag löschen. |
| **Frage** | leer, bis Sie eine speichern | Die Frage in der aktuellen Backoffice-Sprache. **Keine Frage in dieser Sprache** bedeutet, dass diese Sprache keinen Fragetext hat. |
| **Verknüpft mit** | leer | Bis zu vier Verknüpfungen, danach eine Auslassung. |
| **Quelle** | Handgeschrieben bei einem Eintrag, den Sie getippt haben | **KI** oder **Handgeschrieben**. **gesperrt** bedeutet, dass ein späteres Ersetzen diesen Eintrag behält. |
| **Status** | Aktiv bei einem neuen Eintrag | **Aktiv** erscheint auf passenden Produktseiten. **Inaktiv** bleibt im Backoffice und ist im Shop verborgen. |

Die Zahl rechts ist die Anzahl der Einträge, nicht nur der zehn in dieser Vorschau. **Bearbeiten** öffnet diesen Eintrag im Katalog.

Gibt es keine Einträge, sagt die Seite **Noch keine Einträge** und dass der Shop nichts zeigt, bis ein aktiver Eintrag mit einem Produkt, einer Kategorie, einem Merkmal, einem Attribut, einem Schlagwort, einer Marke oder einem Lieferanten verknüpft ist.

### 3.3 Katalog

![Katalog](https://mypresta.eu/docs/images/docs/myfaq-catalogue-list.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt der Abschnitt **Katalog**.

Öffnen Sie **Vollständige Liste anzeigen**. Der Seitentitel ist **FAQ-Einträge**. Der Hinweis oben sagt, dass die Suche Frage, Produktname oder -id, Sprache und die übrigen Verknüpfungen trifft. Die Frage ist die der aktuellen Backoffice-Sprache. Der Produktname öffnet dieses Produkt. **Bearbeiten** öffnet das Formular auf dieser Seite. **Nach oben** und **Nach unten** verschieben den Eintrag. Ziehen Sie die Positionsspalte, um dieselbe Reihenfolge zu setzen. **Löschen** fragt nach Bestätigung. **Aktiv** zeigt den Eintrag oder blendet ihn aus. Gesperrte Einträge bleiben, wenn die KI ein Produkt ersetzt.

Spalten: **ID**, **Frage**, **Produkt**, **Außerdem verknüpft mit**, **Sprachen**, **Shop**, **Quelle**, **Aktiv**, **Gesperrt**, **Position**, **Erstellt**, **Aktualisiert**.

**Shop** zeigt **Alle Shops**, wenn der Eintrag im Kontext aller Shops gespeichert wurde. Sonst zeigt er den Namen dieses Shops. Die Oberfläche eines Shops zeigt Einträge für alle Shops und Einträge, die für diesen Shop gespeichert wurden.

**Quelle** ist **Handgeschrieben** oder **KI**. Filtern Sie diese Spalte mit der Liste. **Aktiv** ist ein Schalter in der Zeile: Klicken Sie ihn, um den Eintrag zu zeigen oder zu verbergen. **Gesperrt** ist eine Markierung, kein Schalter. Das Bearbeiten eines vorhandenen Eintrags sperrt ihn. Ein neuer Eintrag ist nicht gesperrt.

Zeilenaktionen sind **Bearbeiten**, **Nach oben**, **Nach unten** und **Löschen**. **Löschen** fragt **Diesen Eintrag löschen? Er verschwindet aus allen Produkten, die ihn verwendet haben.** **Sammelaktionen** hat **Ausgewählte löschen** und fragt **Ausgewählte Einträge löschen? Sie verschwinden aus allen Produkten, die sie verwendet haben.** Scheitert das Löschen, zeigt die Seite **Der Eintrag konnte nicht gelöscht werden.**

**Neuer Eintrag** in der Werkzeugleiste öffnet ein leeres Formular. **Zurück zum Modul** kehrt zu **Einträge** zurück.

Der Formulartitel ist **Neuer Eintrag** oder **Eintrag bearbeiten**.

| Feld | Am Anfang | Wirkung |
|---|---|---|
| **Frage** | leer | Die Zeile, die der Kunde anklickt, um die Antwort zu öffnen. Das ist die Akkordeon-Überschrift. Schreiben Sie eine Frage je Sprache. Die Hilfe unter dem Feld sagt, dass die Standardsprache erforderlich ist. Die Frage darf Shortcodes enthalten. Sie werden auf der Produktseite ersetzt und als einfacher Text gezeigt. Ist jede Sprache leer, zeigt **Speichern** **Geben Sie in mindestens einer Sprache eine Frage ein.** |
| **Antwort** | leer | Der Text, der erscheint, wenn der Kunde die Frage öffnet. Nutzen Sie den Editor für Absätze und Listen. Shortcodes werden auf der Produktseite ersetzt, das umgebende HTML bleibt. Die Shortcode-Liste sitzt unter diesem Feld: Klicken Sie ein Token, um es an der Cursorposition einzufügen. Füllen Sie jede Sprache, in der Sie verkaufen. Eine leere Sprache wird in dieser Sprache nicht gezeigt. |
| **Shortcodes** | die Token-Schaltflächen | Klicken Sie ein Token, um es dort einzufügen, wo der Cursor steht, in der Frage oder in der Antwort. Der Shop ersetzt es auf der Produktseite durch die Daten dieses Produkts, in Sprache und Währung des Kunden. Der gespeicherte Text behält das Token, eine Preis- oder Namensänderung aktualisiert also jeden Eintrag, der es nutzt. In der Frage ist das Ergebnis einfacher Text. |
| **Aktiv** | Ja | **Ja** zeigt den Eintrag auf passenden Produktseiten und nimmt ihn ins Schema auf. **Nein** behält ihn im Backoffice und verbirgt ihn im Shop. |
| **Produkte** | keine | Tippen Sie einen Produktnamen ins Suchfeld und wählen Sie ihn. Der Eintrag erscheint auf diesen Produkten, auch wenn keine andere Verknüpfung passt. Eine passende Verknüpfung genügt. Speichern ersetzt die bisherigen Verknüpfungen dieses Eintrags. |
| **Kategorien** | keine | Tippen Sie einen Kategorienamen und wählen Sie ihn. Der Eintrag erscheint auf Produkten in diesen Kategorien. Eine Verknüpfung ist eine FAQ für eine ganze Kategorie. Übergeordnete Kategorien zählen nur, wenn diese Option unter **Anzeige** an ist. |
| **Merkmalswerte** | keine | Tippen Sie einen Merkmalswert und wählen Sie ihn, zum Beispiel Baumwolle. Der Eintrag erscheint, wenn das Produkt diesen Wert hat. |
| **Attributwerte** | keine | Tippen Sie einen Attributwert und wählen Sie ihn, zum Beispiel M. Der Eintrag erscheint, wenn irgendeine Variante des Produkts diesen Wert nutzt. |
| **Schlagwörter** | keine | Tippen Sie ein Schlagwort und wählen Sie es. Der Eintrag erscheint, wenn das Produkt dieses Schlagwort in der Sprache der Seite hat. |
| **Marken** | keine | Tippen Sie einen Markennamen und wählen Sie ihn. Der Eintrag erscheint auf Produkten dieser Marken. |
| **Lieferanten** | keine | Tippen Sie einen Lieferantennamen und wählen Sie ihn. Der Eintrag erscheint auf Produkten dieser Lieferanten, einschließlich Standardlieferant und Lieferanten an Varianten. |

**Speichern** ohne Verknüpfung zeigt **Verknüpfen Sie den Eintrag mit mindestens einem Produkt, einer Kategorie, einem Merkmal, Attribut, Schlagwort, einer Marke oder einem Lieferanten.** Kann die Zeile nicht gespeichert werden, zeigt die Seite **Der Eintrag konnte nicht gespeichert werden.** Ein erfolgreiches Speichern bleibt auf dem Formular, und PrestaShop bestätigt die Aktualisierung. **Zurück zur Liste** kehrt zum Katalog zurück.

Der Hinweis auf der Token-Schaltfläche ist Englisch. Der Kunde sieht Folgendes:

| Token | Was der Kunde sieht |
|---|---|
| `[product_name]` | Produktname |
| `[product_reference]` | Referenz |
| `[product_ean13]` | EAN-13 |
| `[product_isbn]` | ISBN |
| `[product_upc]` | UPC |
| `[product_mpn]` | MPN |
| `[product_condition]` | Zustand |
| `[product_price]` | Preis inklusive Steuer, in der Währung des Kunden |
| `[product_price_tax_excl]` | Preis ohne Steuer |
| `[product_price_before_discount]` | Preis vor der Reduzierung |
| `[product_discount_amount]` | Rabattbetrag, leer wenn es keine Reduzierung gibt |
| `[product_discount_percent]` | Rabattprozent, leer wenn es keine Reduzierung gibt |
| `[product_quantity]` | Verfügbare Menge der Standardvariante |
| `[product_availability]` | Verfügbarkeitstext, oder der Text bei fehlendem Bestand, wenn die Menge null ist |
| `[product_minimal_quantity]` | Mindestmenge |
| `[product_manufacturer]` | Marke |
| `[product_supplier]` | Lieferant |
| `[product_category]` | Standardkategorie |
| `[product_categories]` | Alle Kategorien |
| `[product_features]` | Merkmalsliste, Name und Wert |
| `[product_feature id=ID]` | Ein Merkmalswert. Ersetzen Sie ID durch die Merkmalsnummer aus **Katalog**, **Merkmale & Attribute**. |
| `[product_tags]` | Schlagwörter in der aktuellen Sprache |
| `[product_url]` | Produktadresse |
| `[product_weight]` | Gewicht mit der Gewichtseinheit des Shops |
| `[product_description_short]` | Kurzbeschreibung als einfacher Text |
| `[shop_name]` | Shopname |
| `[shop_url]` | Shopadresse |

Die Zeile unter den Schaltflächen lautet: **Klicken Sie auf einen Shortcode, um ihn an der Cursorposition einzufügen. Preise und Namen werden auf der Produktseite in der Währung und Sprache des Kunden ersetzt.** `[product_price]` ist der Shortcode Preis im FAQ. Was der Kunde liest, heißt aktueller Preis in der FAQ Antwort und steht in seiner Währung.

### 3.4 KI

![KI](https://mypresta.eu/docs/images/docs/myfaq-configure-ai.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt der Abschnitt **KI**.

**KI** speichert die Verbindung für den KI FAQ Generator PrestaShop. Die Zeile unter der Leiste sagt, dass Speichern hier nichts erzeugt. Nutzen Sie **Massengenerierung** für viele Produkte oder den Bereich **Faq** an einem Produkt für ein Produkt.

Klicken Sie eine Kachel. Die genutzte Kachel zeigt **Aktiv**. Eine Kachel zeigt **Schlüssel gespeichert**, **Kein Schlüssel** oder **Schlüssel optional** auf der kompatiblen Kachel.

Der Tab in der Leiste heißt **KI**. Die englische Abkürzung AI erscheint in einigen festen Fortschrittssätzen, die weiter unten stehen.

| Kachel | Wohin sie ruft |
|---|---|
| **OpenAI** | GPT-Modelle über die offizielle OpenAI-API. Die Liste beginnt mit `gpt-4o-mini`, `gpt-4o`, `gpt-4.1-mini`, `gpt-4.1`. |
| **Anthropic Claude** | Claude-Modelle über die offizielle Anthropic-API. Die Liste beginnt mit `claude-sonnet-4-5`, `claude-3-5-haiku-latest`, `claude-3-5-sonnet-latest`. |
| **Google Gemini** | Gemini-Modelle über die offizielle Google-API. Die Liste beginnt mit `gemini-2.0-flash`, `gemini-1.5-pro`, `gemini-1.5-flash`. |
| **DeepSeek** | DeepSeek-Modelle über eine OpenAI-kompatible API. Die Liste beginnt mit `deepseek-chat`. |
| **Mistral AI** | Mistral-Modelle über die offizielle API. Die Liste beginnt mit `mistral-small-latest`, `mistral-large-latest`. |
| **OpenAI-compatible / Ollama** | Ihr eigener Server: Ollama, vLLM, LM Studio. Kann vollständig lokal laufen. Die Liste ist leer, bis Sie eine Modell-ID hinzufügen. |

| Feld | Am Anfang | Wirkung |
|---|---|---|
| **Anbieter** | OpenAI | Klicken Sie eine Kachel, um den Dienst zu wählen, der die Fragen schreibt. Die Modellliste wechselt sofort. **Speichern** speichert Anbieter, Schlüssel und Modell. Offizielle Anbieter rufen ihren eigenen Host. Die Basis-URL erscheint nur bei der kompatiblen Kachel. |
| **API-Schlüssel** | leer | Geheimnis vom Konto des Anbieters der gewählten Kachel. Fügen Sie einen neuen Schlüssel ein, um den gespeicherten zu ersetzen. Lassen Sie das Feld leer und speichern Sie, um den schon gespeicherten Schlüssel dieses Anbieters zu behalten. Der Schlüssel wird verschlüsselt, wenn der Server OpenSSL hat. Jede Kachel zeigt, ob ein Schlüssel gespeichert ist. Ein kompatibler lokaler Server, etwa Ollama, darf leer bleiben. |
| **Gespeicherten Schlüssel entfernen** | Nein | **Ja** löscht beim Speichern den gespeicherten Schlüssel des gewählten Anbieters. Nutzen Sie das, wenn Sie einen Schlüssel wechseln oder widerrufen. **Nein** lässt den gespeicherten Schlüssel stehen. Erzeugung ohne Schlüssel scheitert bei offiziellen Anbietern. |
| **Kompatible Basis-URL** | leer | Nur genutzt, wenn die kompatible Kachel gewählt ist. Tragen Sie die API-Wurzel ein, die auf `/v1` endet, zum Beispiel `http://localhost:11434/v1` für Ollama. Offizielle Anbieter ignorieren dieses Feld. Lassen Sie es leer, startet ein Lauf nicht: Die Seite zeigt **Legen Sie vor dem Start eines Laufs die kompatible Basis-URL auf dem Tab KI fest.** |
| **Modell** | `gpt-4o-mini` für OpenAI | Modell-ID, die bei jeder Erzeugung für den gewählten Anbieter gesendet wird. Die Liste enthält die integrierten IDs und die IDs, die Sie im Kasten unter diesem Formular hinzugefügt haben. Eine falsche ID lehnt der Anbieter ab, und diese Sprache wird in der Warteschlange als fehlgeschlagen markiert. Die kompatible Kachel zeigt **Noch kein Modell. Fügen Sie unten eines hinzu.**, bis Sie eines hinzufügen. |
| **Temperatur** | 0.4 | Wie frei das Modell schreibt, von 0 bis 2. 0.4 hält die Antworten nah an den Produktdaten. Ein höherer Wert variiert die Formulierung und kann von den Fakten abweichen. Werte außerhalb von 0 bis 2 werden in diesen Bereich zurückgeholt. Manche Anbieter lehnen diese Einstellung ab. Das Modul versucht es dann einmal ohne sie. |
| **Maximale Tokens** | 2000 | Obergrenze der Länge einer Antwort. 2000 reicht für eine Handvoll kurzer Antworten. Erhöhen Sie den Wert, wenn Antworten abgeschnitten werden. Der Anbieter kann früher aufhören. Sehr hohe Werte kosten mehr und können an das Limit des Anbieters stoßen. Der gespeicherte Wert bleibt zwischen 200 und 8000. |
| **Fragen pro Produkt** | 5 | Wie viele Frage-Antwort-Paare je Produkt und je Sprache angefordert werden. Diese Zahl ist der Standard auf **Massengenerierung** und auf der Produktseite. 5 ist ein praktischer Start. Ein späterer Lauf kann eine andere Zahl nutzen. Der gespeicherte Wert bleibt zwischen 1 und 20. |
| **Zusätzliche Anweisungen** | leer | Optionale Regeln für jeden Prompt: Tonfall, Länge oder Themen, die übersprungen werden sollen. Das Modul weist das Modell bereits an, `[product_name]` und `[product_price]` statt eines festen Namens oder Preises zu schreiben, damit eine spätere Preisänderung korrekt bleibt. Leer lassen, um nur die eingebauten Anweisungen zu verwenden. |

Klicken Sie auf **Speichern**. Die Seite zeigt **Gespeichert.**

**Von Ihnen hinzugefügte Modelle** steht unter dem Formular. Das ist ein eigener Kasten für IDs, die nicht in der integrierten Liste stehen. Umbenennen oder entfernen können Sie nur diese. Integrierte Modelle bleiben in der Liste **Modell** und haben keine Löschen-Schaltfläche.

| Feld | Am Anfang | Wirkung |
|---|---|---|
| **Neue Modell-ID** | leer | Fügt die ID der oben gewählten Anbieterkachel hinzu und wählt sie für den nächsten Lauf. Nur Buchstaben, Ziffern und `.` `_` `:` `/` `@` `-`, bis zu 100 Zeichen. Eine integrierte ID wird abgelehnt. |
| **Modell hinzufügen** | eine Schaltfläche | Speichert diese ID. |
| **Speichern** an einer Zeile, die Sie hinzugefügt haben | die aktuelle ID | Benennt diese ID um. War sie das gewählte Modell, folgt die Auswahl der neuen ID. |
| **Löschen** | eine Schaltfläche an einer Zeile, die Sie hinzugefügt haben | Fragt **Dieses Modell entfernen?** und entfernt diese ID. Eine integrierte ID lässt sich nicht entfernen. |

Solange Sie keines hinzufügen, sagt der Kasten **Für diesen Anbieter gibt es noch kein eigenes Modell. Integrierte IDs bleiben in der Liste oben.**

Meldungen, die Sie hier sehen:

- **Wählen Sie einen Anbieter, bevor Sie ein Modell hinzufügen.**
- **Diese ID ist bereits ein integriertes Modell. Es bleibt in der Liste und kann nicht erneut hinzugefügt werden.**
- **Diese Modell-ID ist ungültig. Verwenden Sie Buchstaben, Ziffern und . _ : / @ -, bis zu 100 Zeichen.**
- **Integrierte Modelle können nicht bearbeitet werden.**
- **Diese ID ist ein integriertes Modell. Geben Sie eine andere ID ein.**
- **Dieses Modell konnte nicht umbenannt werden. Verwenden Sie eine neue ID, die noch nicht in der Liste steht.**
- **Integrierte Modelle können nicht entfernt werden.**
- **Dieses Modell haben Sie nicht selbst hinzugefügt, deshalb blieb es unverändert.**

### 3.5 Massengenerierung

![Massengenerierung](https://mypresta.eu/docs/images/docs/myfaq-configure-bulk.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt der Abschnitt **Massengenerierung**.

**Massengenerierung** stellt viele Produkte in die Warteschlange. Die Zeile unter der Leiste sagt, dass leere Filter ignoriert werden, **Generierung starten** eine Sprache je Anfrage schreibt und diese Seite einen Balken von 0 % bis 100 % zeigt. Die geplante Adresse liest diese Filter nicht.

**Aktive Produkte in diesem Shop** zeigt die Zahl der aktiven Produkte vor jedem Filter. Das ist die Zahl des Shopkatalogs, kein fester Wert des Moduls.

| Feld | Am Anfang | Wirkung |
|---|---|---|
| **Kategorien** | keine angehakt | Haken Sie jede Kategorie an, die enthalten sein soll. Eine Unterkategorie ist nicht enthalten, solange Sie sie nicht auch anhaken. Lassen Sie den Baum leer, um Kategorien zu ignorieren. Ein Produkt in mehreren angehakten Kategorien kommt einmal in die Warteschlange. |
| **Marken** | keine gewählt | Halten Sie Strg oder Cmd und klicken Sie eine oder mehrere Marken. Nur Produkte dieser Marken kommen in die Warteschlange. Lassen Sie die Liste unberührt, um die Marke zu ignorieren. Zusammen mit Kategorien muss das Produkt in einer angehakten Kategorie und in einer dieser Marken liegen. |
| **Lieferanten** | keine gewählt | Halten Sie Strg oder Cmd und klicken Sie einen oder mehrere Lieferanten. Ein Produkt passt, wenn dieser Lieferant der Standardlieferant oder ein zusätzlicher Lieferant ist. Lassen Sie die Liste unberührt, um den Lieferanten zu ignorieren. |
| **Produkte überspringen, die bereits einen KI-Eintrag haben** | Nein | **Ja** lässt Produkte aus, die bereits einen KI-Eintrag haben, der direkt an ihnen hängt. Einträge, die Sie von Hand geschrieben haben, zählen nicht, diese Produkte kommen also weiterhin in die Warteschlange. **Nein** stellt passende Produkte erneut in die Warteschlange. |
| **Produkte überspringen, die bereits irgendeine FAQ haben** | Nein | **Ja** lässt Produkte aus, die bereits irgendeinen direkt verknüpften Eintrag haben, auch von Hand geschriebene. **Nein** wendet nur den KI-Schalter darüber an. |
| **Nur Produkte auf Lager** | Nein | **Ja** behält Produkte mit einer Menge über null, auch eine Variante, die auf Lager ist. **Nein** ignoriert den Bestand. |
| **Nur Produkte mit Titelbild** | Nein | **Ja** überspringt Produkte ohne Titelbild in diesem Shop. **Nein** ignoriert Bilder. |
| **Nur Produkte mit Beschreibung** | Nein | **Ja** behält Produkte, deren Kurz- oder Langbeschreibung in der Standardshop-Sprache gefüllt ist. **Nein** ignoriert den Text. |
| **Basispreis ab** | leer | Katalogpreis ohne Steuer, vor spezifischen Preisen. Leer lassen heißt kein Minimum. Ein Produkt unter diesem Preis fällt heraus. |
| **Basispreis bis** | leer | Katalogpreis ohne Steuer, vor spezifischen Preisen. Leer lassen heißt kein Maximum. Ein Produkt über diesem Preis fällt heraus. |
| **Hinzugefügt seit** | leer | Nur Produkte in die Warteschlange stellen, die an diesem Datum oder später angelegt wurden. Leer lassen ignoriert das Anlagedatum. |
| **Maximale Produkte** | leer | Nach so vielen Produkten aufhören, niedrigste ID zuerst. 0 oder leer heißt keine Obergrenze. Nutzen Sie eine kleine Zahl, um die Filter vor einem vollen Lauf zu prüfen. |
| **Sprachen** | keine gewählt | Halten Sie Strg oder Cmd und klicken Sie die Sprachen, die geschrieben werden sollen. Jede Sprache ist eine Anfrage je Produkt. Lassen Sie die Liste leer, um jede aktive Sprache dieses Shops zu schreiben. Die Namen sind die Sprachen dieses Shops. |
| **Fragen** | 5, die Zahl aus **KI** | Wie viele Paare für jedes Produkt in diesem Lauf geschrieben werden. Überschreibt den Standard vom Tab **KI** nur für diese Warteschlange. Nutzen Sie dieselbe Zahl in jeder Sprache des Produkts. |
| **Vorhandene KI-Einträge des Produkts** | Anhängen | **Anhängen** behält die vorhandenen KI-Einträge und fügt neue hinzu. **Nicht gesperrte KI-Einträge ersetzen, die nur mit dem Produkt verknüpft sind** löscht nicht gesperrte KI-Einträge, die nur an diesem Produkt hängen, einmal je Produkt, und schreibt dann neue. Einträge, die Sie von Hand bearbeitet haben, sind gesperrt und bleiben. Einträge, die auch an einer Kategorie oder einem anderen Ziel hängen, bleiben. |
| **An das Modell senden** | siehe die Karten | Wählen Sie die Produktdaten, die das Modell lesen darf. Eine ausgeschaltete Karte wird nicht gesendet. Ein Lauf speichert diese Karten auch für das nächste Mal. |

Die Karten unter **An das Modell senden** tragen diese englischen Titel. Der Satz unter dem Titel ist der Hinweis auf der Karte.

| Karte | Am Anfang | Hinweis auf der Karte |
|---|---|---|
| **Name and reference** | an | Produkttitel und Referenz. |
| **Short description** | an | Die Zusammenfassung unter dem Titel. |
| **Full description** | an | Die lange Beschreibung von der Produktseite. |
| **Price summary** | an | Aktueller Preis und Preis vor einem Rabatt. |
| **Categories** | an | Standardkategorie und die übrigen Kategorien. |
| **Features** | an | Merkmalsnamen und ihre Werte. |
| **Brand** | an | Markenname. |
| **Attributes and combinations** | aus | Attribute jeder Variante. |
| **Tags** | aus | Schlagwörter in der Sprache, die geschrieben wird. |
| **Supplier** | aus | Name des Standardlieferanten. |
| **Stock and availability** | aus | Menge und Verfügbarkeitsbezeichnung. |
| **Weight and dimensions** | aus | Gewicht, Breite, Höhe und Tiefe. |
| **EAN, ISBN and condition** | aus | EAN, ISBN, UPC, MPN und Zustand. |
| **Attachment titles** | aus | Titel der dem Produkt angehängten Dateien. |
| **Existing questions (avoid duplicates)** | aus | Bereits veröffentlichte Fragen, damit das Modell sie nicht wiederholt. |

**Ausführen** hat zwei Karten.

**In diesem Browser starten.** **Generierung starten** stellt die Produkte in die Warteschlange, die zu den Feldern oben passen, eine Zeile je Sprache. Diese Seite bleibt offen und zeigt den Status hier, dann sendet sie jede Sprache an das Modell. Lassen Sie den Tab offen, bis der Balken fertig ist. Schließen des Tabs stoppt diese Seite. Die Warteschlange bleibt, und die geplante Adresse kann sie abschließen.

Der Balken startet bei **Wird gestartet…** und 0 %. Während er läuft, ist die Zeile die erledigte Zahl, ein Schrägstrich und die Summe. Am Ende steht `Finished.` plus diese Zahl. Eine fehlgeschlagene Sprache fügt `failed` und den letzten Fehlertext des Anbieters hinzu. Passt nichts, zeigt die Seite **Für diese Auswahl passt kein Produkt.** Kann die Warteschlange nicht gespeichert werden, zeigt sie **Die Warteschlange konnte nicht erstellt werden.** Kann der Lauf nicht starten, zeigt die Statuszeile **The run did not start.** Eine Antwort, die die Seite nicht lesen kann, zeigt **That request could not be read.** Ein fehlgeschlagener Schritt zeigt **The generation request failed.** oder den Fehlertext des Anbieters. Diese Fortschrittssätze bleiben in diesem Wortlaut.

**Auf dem Server fortsetzen.** Das ist keine zweite Startschaltfläche. Sie liest Kategorien, Fragenzahl und Anhängen oder Ersetzen aus diesem Formular nicht. Planen Sie eine URL alle paar Minuten. Jeder Aufruf arbeitet etwa 20 Sekunden und stoppt dann.

Kopieren Sie **Eine bestehende Warteschlange abschließen** nach **Generierung starten**, wenn Sie den Tab schließen oder ein Lauf vor dem Ende des Balkens stehen blieb. Diese Adresse schreibt nur Zeilen, die schon in der Warteschlange stehen.

Kopieren Sie **Produkte ohne KI-Eintrag befüllen**, wenn neue Produkte gefüllt werden sollen, ohne diese Seite zu öffnen. Diese Adresse fügt jedes aktive Produkt dieses Shops hinzu, das keinen KI-Eintrag hat, mit der Fragenzahl und der Datenauswahl, die unter **KI** gespeichert sind. Sie hängt immer an und leert dann die Warteschlange.

Halten Sie beide Adressen privat. Sie enthalten das Geheimnis, das den Aufruf autorisiert. **Speichern** auf diesem Formular startet den Lauf nicht. Das tut **Generierung starten**.

Vor einem Lauf verweigert die Seite den Start und zeigt eine dieser Meldungen:

- **Wählen Sie vor dem Start eines Laufs einen Anbieter auf dem Tab KI.**
- **Wählen Sie vor dem Start eines Laufs ein Modell auf dem Tab KI.**
- **Legen Sie vor dem Start eines Laufs die kompatible Basis-URL auf dem Tab KI fest.** Füllen Sie **Kompatible Basis-URL**. Eine leere Adresse startet den Lauf nicht.
- **Speichern Sie vor dem Start eines Laufs einen API-Schlüssel für den ausgewählten Anbieter auf dem Tab KI.**

### 3.6 API

![API](https://mypresta.eu/docs/images/docs/myfaq-configure-api.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt der Abschnitt **API**.

**API** ist für ein System außerhalb des Shops. Die Zeile unter der Leiste sagt, dass Sie hier einen Schlüssel erzeugen, ihm eine Bezeichnung geben und die Basis-URL kopieren. **Vollständige Liste anzeigen** öffnet den Schlüsselkatalog. **Anfrageverlauf** listet jeden Aufruf, mit Parametern und Antwort. **API-Dokumentation** listet jede Aktion.

| Feld | Am Anfang | Wirkung |
|---|---|---|
| **Basis-URL** | die Adresse dieses Shops | Adresse, die ein externes System aufruft. Senden Sie `action` und `api_key` als Abfrageparameter oder als POST-Felder. Der Header `X-Api-Key` wird auch angenommen. Öffnen Sie **API-Dokumentation** für die Parameterliste jeder Aktion. Ein fehlender oder widerrufener Schlüssel wird abgelehnt. |
| **Schlüsselbezeichnung** | leer | Ein Name, damit Sie Schlüssel unterscheiden, zum Beispiel ERP oder Staging. Das ist nicht das Geheimnis. **Schlüssel erzeugen** legt ein neues Geheimnis an und zeigt es in der Tabelle. **Widerrufen** stoppt einen Schlüssel und lässt ihn in der Liste. **Löschen** entfernt diese Zeile und das Geheimnis. Andere Schlüssel arbeiten weiter. Sie können mehr als einen Schlüssel anlegen. |

**Schlüssel erzeugen** fügt den Schlüssel hinzu und kehrt auf diese Seite zurück. Die Vorschau **Bereits ausgestellte Schlüssel** listet die fünf neuesten Schlüssel. Die Zahl ist die volle Anzahl der Schlüssel. Das Geheimnis in dieser Vorschau ist gekürzt. **Vollständige Liste anzeigen** zeigt das ganze Geheimnis, damit Sie es in das andere System kopieren.

| Spalte | Wofür |
|---|---|
| **Bezeichnung** | Der Name, den Sie eingegeben haben. |
| **Schlüssel** | Der Anfang des Geheimnisses in dieser Vorschau. Das ganze Geheimnis steht in der Schlüsselliste. |
| **Status** | **Aktiv** oder **Widerrufen**. |
| **Erstellt** | Wann der Schlüssel erzeugt wurde. |
| **Zuletzt verwendet** | Der letzte angenommene Aufruf, oder **Noch nicht verwendet**. |
| **Verlauf** | Öffnet **Anfrageverlauf** gefiltert auf diesen Schlüssel. |
| **Widerrufen** | Fragt **Diesen Schlüssel widerrufen? Er funktioniert sofort nicht mehr und bleibt in dieser Liste.** Verborgen, wenn der Schlüssel schon widerrufen ist. |
| **Löschen** | Fragt **Diesen Schlüssel löschen? Die Zeile und das Geheimnis werden entfernt. Frühere Anfragen bleiben im Verlauf erhalten.** |

Gibt es keine Schlüssel, sagt die Seite **Noch keine Schlüssel**.

**API-Dokumentation** öffnet ein Fenster. **Kopieren** kopiert die Basis-URL und zeigt danach **OK**. Jede Aktion hat **URL kopieren** und **cURL kopieren**. Ersetzen Sie im Beispiel `YOUR_API_KEY` durch das Geheimnis aus der Schlüsselliste. Das Fenster listet auch **Parameter**, **Pflicht** und **Beschreibung**. **Schließen** verlässt das Fenster.

| Aktion | Was Sie senden | Wirkung |
|---|---|---|
| `list` | `action=list`. Optional `id_product`, `resolved=1`, `page`, `id_shop`. | Liefert Einträge. Mit `id_product` nur Einträge, die direkt an diesem Produkt hängen. Mit `resolved=1` die Menge, die die Produktseite zeigen würde. Ohne Produkt geht `page` durch den Katalog, 50 Einträge je Seite. |
| `get` | `action=get` und `id`. | Liefert einen Eintrag mit jeder Übersetzung und jeder Verknüpfung. |
| `create` | `action=create`, plus eine Frage und mindestens eine Verknüpfung. Optional `id_product`, `id_lang`, `question`, `answer`, `translations`, `assoc`, `active`, `id_shop`. | Legt einen Eintrag an. `id_product` hängt ihn an dieses Produkt. `translations` ist ein JSON-Objekt, dessen Schlüssel die Sprach-ID ist. Shortcodes wie `[product_name]` werden so gespeichert, wie sie sind. `active` ist standardmäßig an. Eine fehlende Frage oder eine fehlende Verknüpfung wird abgelehnt. |
| `update` | `action=update` und `id`, plus nur die Felder, die Sie ändern wollen. | Aktualisiert nur die gesendeten Felder. `replace_assoc=1` ersetzt die Verknüpfungen. Sonst werden `id_product` und `assoc` hinzugefügt. Dieser Aufruf sperrt den Eintrag nicht. |
| `activate` | `action=activate` und `id`. | Zeigt den Eintrag wieder, ohne den Text zu ändern. |
| `deactivate` | `action=deactivate` und `id`. | Blendet den Eintrag aus. Er bleibt im Backoffice und verschwindet von der Produktseite. |
| `delete` | `action=delete` und `id`. | Löscht den Eintrag, seine Übersetzungen und seine Verknüpfungen. |

`assoc` ist eine JSON-Liste von Objekten mit `type` und `id`. Der Typ ist `product`, `category`, `feature_value`, `attribute`, `tag`, `manufacturer` oder `supplier`. Optionales `id_shop` wählt den Shop. Ohne ihn wird der Shop der aufgerufenen Adresse genutzt. GET reicht für einen kurzen Aufruf. Senden Sie dieselben Felder per POST, wenn Frage oder Antwort langes HTML sind.

**Anfrageverlauf** ist eine reine Leseliste mit dem Titel **API-Anfrageverlauf**. Der Hinweis sagt, dass jede Zeile ein Aufruf ist. Suchen Sie in den Feldern unter den Spaltentiteln. **Ansehen** öffnet Parameter und Antwort. Das Geheimnis im gespeicherten Aufruf ist maskiert. Zeilen bleiben, wie sie aufgezeichnet wurden. Sie können keine Zeile hinzufügen, bearbeiten oder löschen. Bei einem Schreibversuch zeigt die Seite **Der Anfrageverlauf ist ein Protokoll der Aufrufe. Öffnen Sie Ansehen, um eine Zeile zu lesen.**

Spalten: **ID**, **Datum**, **Aktion**, **HTTP**, **Schlüssel-ID**, **Schlüssel**, **Details**, **IP**. **API-Schlüssel** in der Werkzeugleiste öffnet den Schlüsselkatalog. **Zurück zum Modul** kehrt zu **API** zurück. Der Einstieg in den Verlauf vom Modul aus setzt einen früheren Filter zurück. **Verlauf** an einem Schlüssel behält den Filter dieses Schlüssels.

Der Schlüsselkatalog heißt **API-Schlüssel**. Der Hinweis sagt, dass das Geheimnis gelistet ist, damit Sie es in das andere System kopieren. **Widerrufen** stoppt diesen Schlüssel und lässt die Zeile stehen. **Löschen** entfernt Zeile und Geheimnis. Frühere Anfragen bleiben im **Anfrageverlauf**. **Schlüssel erzeugen** kehrt zum Tab **API** zurück. Auf dieser Liste gibt es keine Schaltfläche **Neu**. Spalten: **ID**, **Bezeichnung**, **Schlüssel**, **Status**, **Erstellt**, **Zuletzt verwendet**. **Status** liest **Aktiv** oder **Widerrufen**. **Zuletzt verwendet** liest **Noch nicht verwendet** bis zum ersten angenommenen Aufruf. Zeilenaktionen sind **Widerrufen**, **Verlauf** und **Löschen**. **Widerrufen** ist bei einem widerrufenen Schlüssel verborgen und fragt **Diesen Schlüssel widerrufen? Er funktioniert sofort nicht mehr und bleibt in dieser Liste.** **Löschen** fragt **Diesen Schlüssel löschen? Die Zeile und das Geheimnis werden entfernt. Frühere Anfragen bleiben im Verlauf erhalten.** **Sammelaktionen** hat **Ausgewählte widerrufen** und **Ausgewählte löschen**, mit derselben Wirkung für jede angehakte Zeile. Darf der Mitarbeiter nicht bearbeiten, zeigt die Seite **Sie haben keine Berechtigung, dies zu bearbeiten.**

### 3.7 Updates

![Updates](https://mypresta.eu/docs/images/docs/myfaq-configure-updates.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt der Abschnitt **Updates**.

**Updates** prüft bei MyPresta.eu, ob eine neuere Ausgabe vorliegt. Die Prüfung meldet nur eine Version. Das Installieren des Pakets bleibt ein manueller Download von der Modulseite. Der Formulartitel ist **MyPresta-Updates**.

| Feld | Am Anfang | Wirkung |
|---|---|---|
| **Auf Updates prüfen** | eine Schaltfläche **Jetzt prüfen** | Prüft von Hand, ob eine neuere Version dieses Moduls auf den Servern von MyPresta.eu liegt. **Neue Version verfügbar!** bedeutet, dass eine neuere Ausgabe gelistet ist. **Das Modul ist auf dem neuesten Stand!** bedeutet, dass diese Installation zur veröffentlichten Ausgabe passt. Die Schaltfläche lädt keine Zip-Datei hoch. |
| **Update-Benachrichtigungen** | Aktivieren | **Aktivieren** wiederholt diese Prüfung etwa alle drei Tage, während Sie im Backoffice arbeiten. **Deaktivieren** überspringt sie. **Aktivieren** und **Deaktivieren** sind die beiden Wahlmöglichkeiten. |
| **Modulseite** | ein Link namens **MyFAQ** | Direkter Link zur offiziellen Addon-Seite, auf der Sie Änderungen am Modul lesen. |

Klicken Sie auf **Speichern**. Die Seite zeigt **Update-Einstellungen gespeichert.**

Ist eine neuere Ausgabe bekannt, kann das Backoffice **Eine neue Version ist verfügbar, weitere Informationen unter http://MyPresta.eu** und den Link **Weitere Details im Changelog** zeigen. Laden Sie die neue Zip-Datei im **Modul-Manager** hoch.

### 3.8 Ein Produkt

![Ein Produkt](https://mypresta.eu/docs/images/docs/myfaq-product-block.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt der Abschnitt **Ein Produkt**.

Öffnen Sie **Katalog**, **Produkte**, das Produkt, dann den Block **MyFAQ**. Die Überschrift ist **FAQ zu diesem Produkt**. Der Text darunter sagt: Wählen Sie, wo dieses Produkt seine Fragen zeigt, prüfen Sie, was es aus dem Katalog erbt, und schreiben Sie Einträge, die nur hierher gehören. Ist kein Eintrag aktiv oder ist die Platzierung **Ausblenden**, gibt der Shop auf diesem Produkt keinen MyFAQ-Block aus.

Die Tabs sind **FAQ-Einträge**, **Frage und Antwort** und **Mit KI erzeugen**.

**FAQ-Einträge** beginnt mit **Platzierung**.

| Feld | Am Anfang | Wirkung |
|---|---|---|
| **Platzierung** | Shop-Standard verwenden | **Shop-Standard verwenden** folgt **Anzeige**. **Produktfußzeile** oder **Produkt-Tab** erzwingt diesen Ort nur für dieses Produkt. **Ausblenden** entfernt MyFAQ von diesem Produkt, einschließlich des Schema-Blocks. Andere Module am Hook werden nicht verschoben. Ihre Reihenfolge bleibt unter **Design**, **Positionen**. |

**Speichern** zeigt **Gespeichert.**

**FAQ zu diesem Produkt** hat zwei Listen. Die erste ist nur lesbar und kommt von Kategorie, Merkmal, Attribut, Schlagwort, Marke oder Lieferant. Die zweite ist für dieses Produkt gespeichert. Ziehen Sie eine Zeile, um die Reihenfolge zu ändern, nutzen Sie den Schalter, um eine Frage zu zeigen oder zu verbergen, und löschen Sie, um sie zu entfernen.

**Aus dem Katalog** listet Einträge, die gezeigt werden, weil ein anderes Produkt mit derselben Verknüpfung sie auch zeigen würde. Den Text ändern Sie im Modulkatalog. Spalten sind **Frage**, **Status** und **Aktionen**. **Status** ist **Aktiv** oder **Inaktiv**. **Im Katalog bearbeiten** öffnet diesen Eintrag. Ein KI-Eintrag kann **KI** und **gesperrt** zeigen. Ein getippter Eintrag zeigt **Handgeschrieben**. Passt nichts, sagt die Karte **Nichts geerbt**.

**Nur dieses Produkt** listet Fragen, die an diesem Produkt hängen. Der Griff (**Zum Sortieren ziehen**) setzt ihre Reihenfolge auf der Produktseite. Der Schalter zeigt **Aktiv** oder **Inaktiv**. **Bearbeiten** öffnet **Frage und Antwort**. **Löschen** fragt **Diesen Eintrag löschen?** Ist die Liste leer, sagt die Karte **Noch keine FAQ für dieses Produkt** und bietet **Eintrag hinzufügen**. **Keine Frage in dieser Sprache** bedeutet, dass die aktuelle Backoffice-Sprache keinen Fragetext hat. Eine andere Sprache kann einen haben.

**Frage und Antwort** ist **Eintrag hinzufügen** oder **Eintrag bearbeiten**. Der Hinweis sagt, dass nur für dieses Produkt gespeichert wird. Verknüpfungen mit Kategorie, Merkmal und anderen Zielen bleiben auf dem Bildschirm **Einträge**. Die Frage ist im Shop einfacher Text. Die Antwort behält die Formatierung des Editors. Shortcodes sitzen unter der Antwort. Die Sprachschaltfläche rechts schaltet Frage und Antwort gemeinsam um.

| Feld | Am Anfang | Wirkung |
|---|---|---|
| **Frage** | leer | Dieselbe Rolle wie im Katalog. Die Hilfe sagt, dass die Standardsprache erforderlich ist. Ist jede Sprache leer, zeigt der Block **Geben Sie in mindestens einer Sprache eine Frage ein.** |
| **Antwort** | leer | Dieselbe Rolle wie im Katalog. Eine leere Sprache wird in dieser Sprache nicht gezeigt. |
| **Shortcodes** | die Token-Schaltflächen | Dieselben Token wie im Katalog. Klicken Sie eines, um es an der Cursorposition einzufügen. |
| **Aktiv** | Ja | **Ja** zeigt den Eintrag. **Nein** verbirgt ihn im Shop. |

**Speichern** verknüpft den Eintrag nur mit diesem Produkt. Das Bearbeiten einer vorhandenen Zeile sperrt sie, ein späteres Ersetzen behält sie also. Eine neue Zeile ist nicht gesperrt. **Neuer Eintrag** leert das Formular. **Eintrag löschen** entfernt ihn nach **Diesen Eintrag löschen?** Öffnen Sie einen Eintrag, der auch an etwas anderem hängt, zeigt der Block **Dieser Eintrag ist nicht exklusiv für das Produkt.** und speichert nicht darüber. Ändern Sie diesen Eintrag über **Im Katalog bearbeiten**.

Erreicht das Speichern den Shop nicht, zeigt der Block **The save could not reach the shop. Reload the product and try again.**

**Mit KI erzeugen** schreibt Fragen für dieses Produkt aus seinen Katalogdaten, in jeder Shopsprache. Der Lauf geht im Hintergrund weiter. Ein Fortschrittsbalken erscheint hier, nachdem Sie ihn gestartet haben.

| Feld | Am Anfang | Wirkung |
|---|---|---|
| **Fragen** | 5, die Zahl aus **KI** | Wie viele Paare für dieses Produkt geschrieben werden, in jeder Shopsprache. Überschreibt den Standard vom Tab **KI** nur für diesen Lauf. |
| **Vorhandene KI-Einträge des Produkts** | Anhängen | **Anhängen** behält die vorhandenen KI-Einträge und fügt neue hinzu. **Nicht gesperrte KI-Einträge ersetzen, die nur mit dem Produkt verknüpft sind** löscht nicht gesperrte KI-Einträge, die nur an diesem Produkt hängen, und schreibt dann neue. Einträge, die Sie von Hand bearbeitet haben, sind gesperrt und bleiben. |
| **An das Modell senden** | dieselben Karten wie bei der Massengenerierung | Dieselben Karten. Eine ausgeschaltete Karte wird nicht gesendet. Dieser Lauf speichert die Karten für das nächste Mal. |

**Generieren** startet den Lauf. Dieselben vier Meldungen wie unter **Massengenerierung** erscheinen, wenn Anbieter, Modell, kompatible Adresse oder Schlüssel fehlen. Der Balken nutzt denselben Wortlaut: **Wird gestartet…**, dann die Zähler, dann `Finished.` Lassen Sie diese Produktseite offen, bis der Balken fertig ist, oder schließen Sie die Warteschlange mit der Adresse unter **Massengenerierung** ab.

## 4. Shop-Oberfläche

Der Kunde sieht den Block nur auf einer Produktseite.

Ist **Platzierung** **Produktfußzeile**, steht das Akkordeon unter dem Produkt. Die Überschrift ist **Überschrift über der Liste** in der Sprache des Kunden. Jede Frage ist eine Schaltfläche. Die Antwort öffnet sich darunter. **Erste Frage öffnen** auf **Ja** öffnet die erste Antwort beim Laden. Ohne JavaScript ist jede Antwort sichtbar.

Ist **Platzierung** **Produkt-Tab**, fügt das Theme einen Produkt-Tab hinzu. Die Tab-Beschriftung ist **Tab-Titel** in dieser Sprache, oder FAQ, wenn diese Sprache leer ist. Der Tab-Inhalt ist dasselbe Akkordeon und dieselbe Überschrift.

Einträge, die direkt am Produkt hängen, kommen zuerst. Danach gilt die Position aus dem Katalog und aus **Zum Sortieren ziehen** am Produkt. Eine Frage oder eine Antwort, die in der Sprache des Kunden leer ist, wird übersprungen. Nach dem Ersetzen der Token wird auch eine Frage übersprungen, die leer bleibt, oder eine Antwort, in der kein Text mehr steht. Inaktive Einträge werden übersprungen. **Ausblenden** an diesem Produkt gibt nichts aus, auch nicht den Schema-Block.

**FAQ-Schema-Markup** auf **Ja** ist das FAQ Schema PrestaShop im Seitenquelltext: ein schema.org FAQPage Block, gebaut aus den Fragen, die der Kunde öffnen kann, in der Sprache der Seite und mit Verweis auf die Produktadresse. Der Kunde sieht keinen eigenen Schema-Kasten. **Nein**, eine leere Liste oder **Ausblenden** gibt keinen solchen Block aus.

Der Kunde kann keine Frage hinzufügen, bearbeiten oder senden. Es gibt keine Kontoseite für diese Einträge.

Gibt das Theme die Produktfußzeile nicht aus und auch keine zusätzlichen Produkt-Tabs, sieht der Kunde nichts, auch wenn Einträge existieren. Verschieben Sie **MyFAQ** unter **Design**, **Positionen**, auf die Produktfußzeile oder den zusätzlichen Produktinhalt. Andere Module an diesem Hook bleiben in der Reihenfolge, die Sie dort setzen.

An demselben Theme können zwei Fußzeilenpositionen existieren. Das Akkordeon wird einmal ausgegeben.

## 5. Probleme

**Die Produktseite hat kein Akkordeon.** Das Produkt hat keinen aktiven Eintrag in der Sprache des Kunden, Frage oder Antwort ist nach dem Ersetzen der Token leer, oder **Platzierung** für dieses Produkt ist **Ausblenden**. Öffnen Sie das Produkt, setzen Sie **Platzierung** auf **Shop-Standard verwenden**, **Produktfußzeile** oder **Produkt-Tab** und bestätigen Sie einen **Aktiv**-Eintrag. Hat das Theme keine Fußzeile und keine zusätzlichen Tabs, verschieben Sie das Modul unter **Design**, **Positionen**.

**Ein Eintrag an einer übergeordneten Kategorie erscheint nicht.** **Übergeordnete Kategorien einbeziehen** steht auf **Nein**, oder die Verknüpfung ist Home. Setzen Sie **Übergeordnete Kategorien einbeziehen** auf **Ja**. Eine Verknüpfung mit Home deckt den Katalog nicht ab. Haken Sie den Elternteil an, den Sie wirklich wollen, unter Home.

**Der Shop zeigt den Eintrag in einer Sprache und in einer anderen nicht.** Diese Sprache hat eine leere Frage oder eine leere Antwort. Bearbeiten Sie den Eintrag und füllen Sie beides. Die Seite überspringt eine leere Sprache.

**Speichern zeigt „Geben Sie in mindestens einer Sprache eine Frage ein.“** Tippen Sie eine Frage in mindestens einer Sprache und klicken Sie erneut auf **Speichern**.

**Speichern zeigt „Verknüpfen Sie den Eintrag mit mindestens einem Produkt, einer Kategorie, einem Merkmal, Attribut, Schlagwort, einer Marke oder einem Lieferanten.“** Wählen Sie mindestens ein Ergebnis unter **Produkte**, **Kategorien**, **Merkmalswerte**, **Attributwerte**, **Schlagwörter**, **Marken** oder **Lieferanten**.

**Der Produktblock zeigt „Dieser Eintrag ist nicht exklusiv für das Produkt.“** Diese Frage hängt auch an einer Kategorie oder einem anderen Ziel. Klicken Sie auf **Im Katalog bearbeiten** und ändern Sie sie dort.

**Der Produktblock zeigt „The save could not reach the shop. Reload the product and try again.“** Laden Sie das Produkt neu und speichern Sie erneut.

**Generieren tut nichts und zeigt eine Meldung zum Tab KI.** Öffnen Sie **KI**, wählen Sie die Kachel, speichern Sie ein Modell und speichern Sie einen Schlüssel bei einem offiziellen Anbieter. Bei der kompatiblen Kachel füllen Sie **Kompatible Basis-URL**, zum Beispiel `http://localhost:11434/v1` für Ollama. Starten Sie den Lauf dann erneut.

**Generierung starten zeigt „Für diese Auswahl passt kein Produkt.“** Leeren Sie einen Filter oder haken Sie eine Kategorie an, die aktive Produkte enthält. Leere Filter werden ignoriert, der Filter, den Sie gesetzt haben, hat die Produkte also entfernt.

**Der Balken stoppt vor 100 %.** Lassen Sie den Tab offen oder kopieren Sie **Eine bestehende Warteschlange abschließen** und öffnen Sie sie nach Zeitplan. Schließen des Tabs löscht die Warteschlange nicht. Eine Zeile mit `failed` und einer Anbietermeldung bedeutet, dass diese Sprache abgelehnt wurde. Lesen Sie die Meldung, korrigieren Sie Schlüssel oder Modell-ID und starten Sie erneut. **Anhängen** fügt einen weiteren Satz hinzu. **Nicht gesperrte KI-Einträge ersetzen, die nur mit dem Produkt verknüpft sind** entfernt zuerst den nicht gesperrten KI-Satz.

**Die Fortschrittszeile zeigt `curl_missing`.** Der Server hat kein cURL. Bitten Sie den Hoster, es einzuschalten. Die Erzeugung läuft ohne es nicht.

**Ein Hinweis auf eine neuere Version erscheint.** Der Text ist **Eine neue Version ist verfügbar, weitere Informationen unter http://MyPresta.eu**. Öffnen Sie **Updates** und klicken Sie auf **Jetzt prüfen**. Laden Sie die Zip-Datei von der Modulseite und laden Sie sie im **Modul-Manager** hoch. **Deaktivieren** unter **Update-Benachrichtigungen** stoppt den automatischen Hinweis.

**MyFAQ steht nicht im linken Menü.** Das ist so vorgesehen. Öffnen Sie **Module**, **Modul-Manager**, **MyFAQ**, **Konfigurieren**. Katalog, Schlüssel und Verlauf öffnen Sie von dieser Seite. Kann **Konfigurieren** den Katalog nicht öffnen, öffnen Sie **Konfigurieren** einmal als Mitarbeiter, der Module installieren darf. Dieser Besuch legt die versteckten Seiten an und gibt dem aktuellen Profil Zugriff.

**Ein Schlüssel wird abgelehnt.** Der Schlüssel wurde widerrufen, gelöscht oder ohne das volle Geheimnis kopiert. Öffnen Sie **API-Schlüssel**, kopieren Sie den vollen **Schlüssel** einer Zeile **Aktiv**, oder klicken Sie auf **Schlüssel erzeugen**.

**Sie können eine Zeile im Anfrageverlauf nicht löschen.** Die Seite zeigt **Der Anfrageverlauf ist ein Protokoll der Aufrufe. Öffnen Sie Ansehen, um eine Zeile zu lesen.** Nutzen Sie **Ansehen**.

**Sie haben keine Berechtigung, dies zu bearbeiten.** Das Mitarbeiterprofil darf die Schlüsselliste nicht bearbeiten. Öffnen Sie **Konfigurieren** als Administrator oder geben Sie dem Profil Zugriff auf die Modulseiten.

**Die erste Antwort ist geschlossen, obwohl Erste Frage öffnen auf Ja steht.** Der Kunde hat JavaScript aus. Dann ist jede Antwort sichtbar. Mit JavaScript startet nur der erste Eintrag geöffnet.

**Dieselbe Frage erscheint zweimal.** Sie hängt zweimal nur dann, wenn Sie zwei Einträge gespeichert haben. Ein Eintrag wird einmal gezeigt. Prüfen Sie **Nur dieses Produkt** und **Aus dem Katalog** auf zwei verschiedene Zeilen mit demselben Text.

**Ersetzen hat eine alte KI-Frage stehen lassen.** Dieser Eintrag ist gesperrt oder hängt auch an einer Kategorie oder einem anderen Ziel. Gesperrt ist die Markierung an der Zeile. Bearbeiten Sie ihn und löschen Sie ihn, wenn er weg soll.

## 6. Für Entwickler

### 6.1 Überblick

Hauptklasse `myfaq` in `myfaq.php`. Version `1.3.1`. Listenname **MyFAQ**. Autor `mypresta.eu`. Tab `front_office_features`. `ps_versions_compliancy` ist `1.7.0.0` bis `9.99.99`. `need_instance` ist 0. `bootstrap` ist true. `config.xml` nennt noch Version `1.0.0`. Die Klassenversion ist die, die der Shop ausführt.

`getContent()` rendert `MyfaqAdminBo`. Anzeigeeinstellungen sind `Configuration`-Schlüssel. Einträge, Verknüpfungen, Platzierung je Produkt, API-Schlüssel, das Anfrageprotokoll und die KI-Warteschlange sind Tabellen. Die Oberfläche liest Treffer über `MyfaqMatcher`, ersetzt Token mit `MyfaqShortcode` und gibt optional `MyfaqSchema` aus. KI-Aufrufe gehen über `MyfaqAi` und `MyfaqQueue`. Die öffentliche Adresse ist der Front-Controller `api`.

Es gibt kein `enable()` und kein `disable()`.

### 6.2 Dateien

- `myfaq.php` — Installation, Deinstallation, Hooks, Startwerte, Ajax-Einstiege.
- `config.xml` — Paketmetadaten. Die Version dort ist `1.0.0`.
- `lib/MyfaqAdminBo.php` — Backoffice-Formulare, `desc`-Texte, Produktpanel.
- `lib/MyfaqConfig.php` — Anbieter, Modelle, Flags, Verschlüsselung, Cron-Token.
- `lib/MyfaqRepository.php` — Tabellen und Speichern.
- `lib/MyfaqMatcher.php` — welche Einträge ein Produkt zeigt.
- `lib/MyfaqShortcode.php` — Tokenkatalog und Ersetzung.
- `lib/MyfaqSchema.php` — veröffentlicht die JSON-LD FAQ Produktseite.
- `lib/MyfaqAi.php` — HTTP-Aufrufe zum Anbieter. Braucht cURL.
- `lib/MyfaqQueue.php` — Stapel und Warteschlange.
- `lib/MyfaqApi.php` — öffentliche API.
- `lib/MyfaqApiDocumentation.php` — Text des Fensters.
- `lib/updatesChecker.php` — Klasse `myfaqUpdate`.
- `lib/prestashop9compatibility.php` — Helper-Vorlagen, Preis, ID-Listen.
- `lib/searchTool/searchTool.php` — Autovervollständigung der Verknüpfungsfelder.
- `controllers/admin/AdminMyfaqController.php` — nur Ajax: Suche, Produktpanel, Stapelstart, Stapelschritt, Umsortieren.
- `controllers/admin/AdminMyfaqEntriesController.php` — Katalog.
- `controllers/admin/AdminMyfaqKeysController.php` — Schlüssel.
- `controllers/admin/AdminMyfaqLogsController.php` — Anfrageverlauf.
- `controllers/front/api.php` — öffentliche JSON-API.
- `controllers/front/cron.php` — Warteschlangen-Worker.
- `views/templates/admin/tabs.tpl` — Bereichsleiste.
- `views/templates/admin/entries.tpl` — Vorschau der letzten zehn.
- `views/templates/admin/product.tpl` — Block der Produktbearbeitung.
- `views/templates/admin/api.tpl` — Schlüsselvorschau.
- `views/templates/admin/_shortcodes.tpl` — Token-Schaltflächen.
- `views/templates/admin/_api_documentation_modal.tpl` — Aktionsfenster.
- `views/templates/admin/_api_log_modal.tpl` — ein gespeicherter Aufruf.
- `views/templates/hook/product.tpl` — Akkordeon der Oberfläche.
- `views/css/myfaq.css`, `views/js/myfaq.js` — Oberfläche.
- `views/css/myfaq-admin.css`, `views/css/myfaq-controls.css`, `views/js/admin.js` — Backoffice. Mehrere Fortschrittssätze in `admin.js` sind fest Englisch.
- `upgrade/upgrade-1.0.0.php` — ruft `installDb()` auf.
- `key.php` — optional. Wenn vorhanden, sendet die Update-Prüfung den Lizenzwert. Wenn nicht, sendet die Prüfung `nlc`.

### 6.3 Controller

`AdminMyfaq`, `AdminMyfaqEntries`, `AdminMyfaqKeys` und `AdminMyfaqLogs` sind Tabs mit `id_parent` `-1`. Sie erscheinen nicht im Menü. `ensureSearchTab()` legt einen fehlenden Tab an. `grantHiddenTabAccess()` vergibt Ansicht, Hinzufügen, Bearbeiten und Löschen an das Superadmin-Profil und an das aktuelle Mitarbeiterprofil.

`AdminMyfaq` bedient nur Ajax: `SearchTool`, `ProductPanel`, `BulkStart`, `BulkStep`, `Reorder`. Dieselben Aktionen liegen am Modulobjekt, weil Produktpanel und Stapelseite dorthin senden.

`AdminMyfaqEntries` ist der Katalog. **Neuer Eintrag** in der Leiste ist `addmyfaq_item`. Speichern sendet `submitMyfaqItem` und leitet mit `conf=4` weiter. Die Position nutzt die Positionslinks des Helpers.

`AdminMyfaqKeys` hat kein Hinzufügen-Formular. **Schlüssel erzeugen** verlinkt zurück auf `configure=myfaq&mfq_tab=api`. `processRevoke` und der Sammelwiderruf rufen `MyfaqRepository::revokeApiKey`. Löschen ruft `deleteApiKey`.

`AdminMyfaqLogs` lehnt Hinzufügen, Aktualisieren und Löschen ab mit **Der Anfrageverlauf ist ein Protokoll der Aufrufe. Öffnen Sie Ansehen, um eine Zeile zu lesen.** `action=View` liefert die gespeicherte Anfrage und Antwort als JSON für das Fenster. `id_api_key` in der Abfrage füllt den Schlüsselfilter, außer die Liste wird zurückgesetzt.

Der Front-Controller `api` (`module/myfaq/api`) ruft `MyfaqApi::handle()` und liefert JSON. Er setzt den HTTP-Status aus dem Ergebnis. Der Front-Controller `cron` (`module/myfaq/cron`) verlangt `token` gleich `MYFAQ_CRON_TOKEN`. Ein falsches Token liefert `403` und `{"error":"forbidden"}`. `fill_missing=1` ruft `MyfaqQueue::enqueueMissing` für den aktuellen Shop, danach leert die Aktion wartende Zeilen etwa 20 Sekunden lang, höchstens 30 Zeilen. Das JSON ist `ok`, `enqueued_batch`, `processed`, `finished`.

API-Ergebnisse: fehlender oder widerrufener Schlüssel `401` `unauthorized`. Unbekanntes `action` `400` `unknown_action`. Fehlende oder unbekannte ID `400` `missing_id` oder `not_found`. Anlegen ohne Frage `422` `question_required`. Anlegen ohne Verknüpfung `422` `association_required`. Erfolg beim Anlegen `201`. Erfolg bei Aktualisieren, Aktivieren, Deaktivieren und Löschen `200`. Fehlgeschlagenes Schreiben `500`.

`list` mit `id_product` und `resolved=1` nutzt `MyfaqMatcher::forProductAllLangs`. `list` mit `id_product` ohne `resolved` liefert Einträge, die direkt an diesem Produkt hängen. `list` ohne Produkt blättert `MyfaqRepository::listItems` mit 50 je Seite. Aktualisieren nutzt `lock_on_update` false, eine API-Aktualisierung sperrt die Zeile also nicht.

### 6.4 Hooks

Registriert in `install()`:

| Hook | Rolle |
|---|---|
| `displayHeader` | Auf einem Produkt-Controller lädt `views/css/myfaq.css` und `views/js/myfaq.js`. |
| `displayFooterProduct` | Rendert das Akkordeon, wenn die aufgelöste Platzierung `footer` ist. |
| `displayProductFooter` | Dieselbe Ausgabe. Ein statisches Flag gibt den Fußzeilenblock nur einmal je Anfrage aus. |
| `displayProductExtraContent` | Ist die Platzierung `tab`, liefert es ein `ProductExtraContent`. Der Titel ist `MYFAQ_TAB_TITLE` der aktuellen Sprache oder der Quelltext FAQ, wenn dieser Wert leer ist. |
| `displayAdminProductsExtra` | Block der Produktbearbeitung plus CSS und JS. |
| `actionAdminControllerSetMedia` | Admin-CSS und -JS auf der Produktseite, bei `configure=myfaq` und auf den Controllern für Einträge, Schlüssel und Verlauf. |

Das Modul registriert keine eigenen Hooks und ruft `Hook::exec` nicht für einen eigenen Hook. `displayProductExtraContent` liefert ein leeres Array, wenn die Platzierung nicht `tab` ist, wenn das HTML leer ist oder wenn `ProductExtraContent` nicht existiert.

### 6.5 Überschreibungen

Das Modul überschreibt keine PrestaShop-Klasse und keinen Controller.

### 6.6 Datenbank

`MyfaqRepository::installDb()` legt die Tabellen mit `_MYSQL_ENGINE_` und `utf8mb4` an und versucht bei einem Fehler `utf8`. `uninstall()` löscht sie in dieser Reihenfolge: `myfaq_queue`, `myfaq_batch`, `myfaq_api_log`, `myfaq_api_key`, `myfaq_product_display`, `myfaq_assoc`, `myfaq_item_lang`, `myfaq_item`. Die Deinstallation löscht die Tabellen. Eine Neuinstallation stellt die Zeilen nicht wieder her.

| Tabelle | Inhalt |
|---|---|
| `myfaq_item` | `id_item`, `id_shop` (`0` bedeutet alle Shops), `active`, `position`, `source` (`manual` oder `ai`), `locked`, `date_add`, `date_upd`. |
| `myfaq_item_lang` | `id_item`, `id_lang`, `question`, `answer`. |
| `myfaq_assoc` | `id_assoc`, `id_item`, `type`, `id_target`. Eindeutig auf Eintrag, Typ und Ziel. Typen: `product`, `category`, `feature_value`, `attribute`, `tag`, `manufacturer`, `supplier`. |
| `myfaq_product_display` | `id_product`, `id_shop`, `mode` (`inherit`, `footer`, `tab`, `hidden`). |
| `myfaq_api_key` | `id_api_key`, `api_key`, `label`, `active`, `date_add`, `last_used`. |
| `myfaq_api_log` | `id_log`, `id_api_key`, `label`, `action`, `http_code`, `ip`, `request`, `response`, `date_add`. Der gespeicherte Schlüssel ist maskiert. |
| `myfaq_batch` | `id_batch`, `id_shop`, `id_employee`, `status` (`pending`, `running`, `done`), `total`, `done`, `failed`, `options`, `date_add`, `date_upd`. |
| `myfaq_queue` | `id_queue`, `id_batch`, `id_shop`, `id_product`, `id_lang`, `status` (`pending`, `running`, `done`, `error`), `attempts`, `error`, `date_upd`. Eine `running`-Zeile, die älter als fünf Minuten ist, wird auf `pending` gesetzt. |

`ensureApiSchema()` läuft, wenn der API-Tab, die Schlüsselliste, der Verlauf oder ein öffentlicher API-Aufruf geöffnet wird. Es fügt `last_used` hinzu, wenn diese Spalte fehlt, und legt `myfaq_api_log` an, wenn diese Tabelle fehlt.

Das Speichern im Katalog setzt `lock_on_update`, eine Aktualisierung setzt `locked` also auf 1. `source` bleibt bei der Aktualisierung der aktuelle Wert, außer `force_source` ist gesetzt. Eine neue Katalogzeile ist `manual` und nicht gesperrt. Eine Aktualisierung von der Produktseite sperrt ebenfalls. Ein Einfügen von der Produktseite verknüpft nur dieses Produkt und sperrt nicht. KI-Ersetzen löscht Zeilen mit `source` `ai`, `locked` 0 und ohne andere Verknüpfung als dieses Produkt.

`MyfaqMatcher::categoryIds()` fügt Eltern nur hinzu, wenn `MYFAQ_INCLUDE_PARENT_CAT` 1 ist. Der Gang stoppt, wenn `id_parent` kleiner oder gleich 2 ist, oder nach 25 Schritten.

### 6.7 Schlüssel und Übersetzungen

Gesetzt von `installConfig()`. Entfernt von `deleteConfig()` bei der Deinstallation.

| Schlüssel | Wenn er fehlt oder bei der Installation |
|---|---|
| `MYFAQ_DISPLAY` | `footer` |
| `MYFAQ_TAB_TITLE` | `FAQ` je Sprache |
| `MYFAQ_HEADING` | `FAQ` je Sprache |
| `MYFAQ_INCLUDE_PARENT_CAT` | `0` |
| `MYFAQ_SCHEMA` | `1` |
| `MYFAQ_OPEN_FIRST` | `0` |
| `MYFAQ_AI_PROVIDER` | `openai` |
| `MYFAQ_AI_MODEL_OPENAI` | `gpt-4o-mini` |
| `MYFAQ_AI_MODEL_ANTHROPIC`, `MYFAQ_AI_MODEL_GEMINI`, `MYFAQ_AI_MODEL_DEEPSEEK`, `MYFAQ_AI_MODEL_MISTRAL`, `MYFAQ_AI_MODEL_COMPATIBLE` | leer, bis ein Modell gespeichert wird. `MyfaqConfig::model()` liefert dann die erste integrierte ID oder eine leere Zeichenkette für `compatible` |
| `MYFAQ_AI_KEY_` plus Anbieter in Großbuchstaben | leer. Gespeichert mit `MyfaqConfig::encrypt` (`enc:` und AES-256-CBC, Schlüssel `sha256` von `_COOKIE_KEY_`) |
| `MYFAQ_AI_BASE_URL` | leer. `baseUrl('compatible')` nutzt dann `http://localhost:11434/v1`. `aiBlockReason()` lehnt einen Lauf ab, solange dieser Wert leer ist, die Backoffice-Schaltflächen erreichen diesen Ersatz also nicht |
| `MYFAQ_AI_TEMPERATURE` | `0.4`. Das Lesen klemmt auf 0 bis 2 |
| `MYFAQ_AI_MAX_TOKENS` | `2000`. Das Lesen nutzt 2000, wenn der gespeicherte Wert unter 200 liegt, und deckelt bei 8000 |
| `MYFAQ_AI_COUNT` | `5`. Das Lesen nutzt 5, wenn der gespeicherte Wert unter 1 liegt, und deckelt bei 20 |
| `MYFAQ_AI_PROMPT` | leer |
| `MYFAQ_AI_CONTEXT` | JSON von `MyfaqConfig::defaultFlags()`. An: `name`, `description_short`, `description`, `prices`, `categories`, `features`, `manufacturer`. Aus: `combinations`, `tags`, `supplier`, `stock`, `dimensions`, `identifiers`, `attachments`, `existing` |
| `MYFAQ_CUSTOM_MODELS` | `{}` |
| `MYFAQ_CRON_TOKEN` | `bin2hex(random_bytes(16))`. `ensureCronToken()` legt einen an, wenn der Wert leer ist |
| `MYFAQ_BO_TAB` | bei der Installation nicht gesetzt. Der offene Bereich wird bei jedem Rendern gespeichert. Unbekannte Werte fallen auf `display` zurück |

`deleteConfig()` löscht auch jedes `MYFAQ_AI_KEY_*` und `MYFAQ_AI_MODEL_*` für `openai`, `anthropic`, `gemini`, `deepseek`, `mistral`, `compatible`.

Die Deinstallation löscht `mypresta_updates`, `update_myfaq` und `updatev_myfaq` nicht. Sie gehören zur Update-Prüfung. `mypresta_updates` ist aktiv, wenn der Schlüssel fehlt. Der Abstand der automatischen Prüfung ist 259200 Sekunden.

Feldbeschreibungen stehen in `MyfaqAdminBo` (`desc` und die Texte von `sectionBrief`) und in `MyfaqApiDocumentation`. Backoffice-Texte laufen über `$this->l()`. Eine Sprache legen Sie mit `translations/{iso}.php` an. Texte, die nicht über `$this->l()` laufen: die Shortcode-Hinweise in `MyfaqShortcode::catalogue()`, die Namen der Anbieterkacheln, die Kartentitel der Flags in `MyfaqConfig::contextFlagDefs()` und die Fortschrittssätze, die in `views/js/admin.js` feststehen. Die Hinweise der Flag-Karten sind übersetzt. Die Kartentitel der Flags sind die englischen Quelltexte.

`MyfaqConfig::shopScope()` liefert `0`, wenn der Multishop-Kontext alle Shops ist, sonst die aktuelle Shop-ID. Katalogspeichern nutzt diesen Wert. Speichern von der Produktseite nutzt nur die aktuelle Shop-ID.

### 6.8 Erweitern

Überschreiben Sie `views/templates/hook/product.tpl` aus dem Theme unter `themes/{theme}/modules/myfaq/views/templates/hook/product.tpl`. Die zugewiesenen Variablen sind `mfq_items` (`id`, `question`, `answer`), `mfq_heading`, `mfq_open_first` und `mfq_schema`. Überschreiben Sie `views/css/myfaq.css` und `views/js/myfaq.js` auf dieselbe Weise. Das Akkordeon wird nicht gerendert, wenn der Abgleich keine sichtbaren Zeilen liefert, eine Theme-Überschreibung hat dann nichts auszugeben. Bearbeiten Sie die Modulvorlagen nicht an Ort und Stelle, wenn das Theme die Überschreibung tragen kann.

## 7. Hilfe

Modulseite: [https://mypresta.eu/contact.html](https://mypresta.eu/contact.html)

Wenn Sie zu diesem Modul fragen wollen, melden Sie sich im Kundenkonto auf [mypresta.eu](https://mypresta.eu) an, öffnen Sie das Kontaktformular und wählen Sie das Thema **Support for paid modules**. Das Formular sagt, dass für dieses Thema eine Anmeldung nötig ist. Nach der Anmeldung wählen Sie dieses Modul aus der Kaufhistorie.

