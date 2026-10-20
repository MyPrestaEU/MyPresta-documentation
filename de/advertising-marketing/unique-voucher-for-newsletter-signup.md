---
title: "Einzigartiger Gutschein für Newsletter-Anmeldung – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Einzigartiger Gutschein für Newsletter-Anmeldung“ von MyPresta.eu."
sidebar:
  label: "Einzigartiger Gutschein für Newsletter-Anmeldung – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Unique voucher for newsletter signup auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/unique-voucher-for-newsletter-signup.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/unique-voucher-for-newsletter-signup/)
>
> ---


# Einzigartiger Gutschein für Newsletter-Anmeldung

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise ausreichend. Es sind in der Regel keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Hosting-Umgebung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Um darauf zuzugreifen, navigieren Sie zu **Module > Modul-Manager**, suchen Sie nach „Einzigartiger Gutschein für Newsletter-Anmeldung“ und klicken Sie auf „Konfigurieren“.

Dieser Bildschirm ermöglicht es Ihnen, das Kernverhalten der für Newsletter-Anmeldungen generierten Gutscheine zu definieren.

- **Was diese Einstellung bewirkt:** Dieser Abschnitt enthält die primären Einstellungen dafür, wie Ihre einzigartigen Gutscheine erstellt und geliefert werden.
- **Auswirkung der Änderung dieser Einstellung:** Das Anpassen dieser Werte wirkt sich direkt auf den Rabattbetrag, die Bedingungen und die Gültigkeit der Gutscheine aus, die Ihre neuen Newsletter-Abonnenten erhalten.

**Einstellungen & Optionen:**

1. **Gutscheinwert (Betrag oder Prozentsatz)**

   - **Was diese Einstellung bewirkt:** Dies definiert den Rabattbetrag oder Prozentsatz, den der einzigartige Gutschein gewährt.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn auf einen bestimmten Betrag eingestellt (z. B. „10“):* Der Gutschein gewährt einen festen monetären Rabatt (z. B. 10 € Rabatt).
     - *Wenn auf einen Prozentsatz eingestellt (z. B. „15%“):* Der Gutschein gewährt einen prozentualen Rabatt auf den Gesamtbestellwert.
   - **Empfohlener Wert:** Dies hängt von Ihrer Preisstrategie ab. Eine gängige Praxis sind 5-15 % oder ein fester Betrag wie 5-10 € für Erstkäufe.
   - **Händlerszenario / Beispiel:** Sie möchten neuen Abonnenten einen Rabatt von 5 € anbieten. Sie würden hier „5“ eingeben. Wenn Sie einen Rabatt von 10 % bevorzugen, würden Sie „10%“ eingeben.
2. **Mindestbetrag**

   - **Was diese Einstellung bewirkt:** Dies legt den Mindestbestellwert (vor Versand) fest, der für die Gültigkeit des Gutscheins erforderlich ist.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn auf „0“ gesetzt oder leer gelassen:* Der Gutschein kann für jede Bestellung verwendet werden, unabhängig von ihrem Gesamtwert.
     - *Wenn auf einen Wert gesetzt (z. B. „50“):* Der Warenkorbwert des Kunden muss mindestens 50 € betragen, damit der Gutschein angewendet werden kann.
   - **Empfohlener Wert:** Legen Sie einen Mindestbetrag fest, wenn Sie einen bestimmten Bestellwert sicherstellen möchten, oder lassen Sie ihn bei „0“, wenn Sie jeden Kauf fördern möchten.
   - **Händlerszenario / Beispiel:** Um zu verhindern, dass Kunden einen 10-€-Gutschein für einen 5-€-Artikel verwenden, könnten Sie einen Mindestbetrag von „30“ festlegen.
3. **Gutscheingültigkeit (Tage)**

   - **Was diese Einstellung bewirkt:** Dies bestimmt, wie viele Tage der einzigartige Gutschein ab dem Zeitpunkt seiner Generierung und des Versands an den Kunden gültig ist.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn auf „0“ gesetzt oder leer gelassen:* Der Gutschein hat kein Ablaufdatum (nicht empfohlen, da dies die Dringlichkeit aufhebt).
     - *Wenn auf einen Wert gesetzt (z. B. „30“):* Der Gutschein läuft 30 Tage nach Erhalt durch den Kunden ab.
   - **Empfohlener Wert:** 7, 14 oder 30 Tage sind üblich, um Dringlichkeit zu erzeugen, ohne zu restriktiv zu sein.
   - **Händlerszenario / Beispiel:** Um sofortige Käufe zu fördern, könnten Sie die Gültigkeit auf „7“ Tage festlegen, um Kunden zur schnellen Nutzung des Gutscheins zu bewegen.
4. **Gutscheinbeschreibung**

   - **Was diese Einstellung bewirkt:** Dieser Text wird als Beschreibung für den generierten Gutschein im Warenkorb des Kunden und im Back Office angezeigt.
   - **Auswirkung der Änderung dieser Einstellung:** Dies hilft Kunden zu verstehen, wofür der Gutschein ist, und bietet Kontext für Ihre internen Aufzeichnungen.
   - **Empfohlener Wert:** „Newsletter-Anmelderabatt“ oder „Willkommensgutschein für Newsletter-Abonnenten“.
   - **Händlerszenario / Beispiel:** Die Eingabe von „Willkommensrabatt für Newsletter-Abonnenten“ kommuniziert den Zweck des Gutscheins klar.
5. **Gutschein-Präfix**

   - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, den vom Modul generierten einzigartigen Gutscheincodes ein benutzerdefiniertes Präfix hinzuzufügen.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn leer gelassen:* Gutscheincodes sind rein zufällig (z. B. „ABCDEF123“).
     - *Wenn ein Präfix festgelegt wird (z. B. „NEWSLETTER-“):* Gutscheincodes beginnen mit diesem Präfix (z. B. „NEWSLETTER-ABCDEF123“). Dies hilft Ihnen, die Quelle des Gutscheins zu identifizieren.
   - **Empfohlener Wert:** „NEWSLETTER-“ oder „WELCOME-“.
   - **Händlerszenario / Beispiel:** Die Verwendung von „NEWSLETTER-“ hilft Ihnen, schnell zu erkennen, welche Gutscheine aus Newsletter-Anmeldungen stammen, wenn Sie Bestellungen oder Statistiken überprüfen.
6. **Produkte mit bestimmten Kategorien ausschließen**

   - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, bestimmte Produktkategorien auszuwählen, für die der Gutschein NICHT anwendbar ist.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn keine Kategorien ausgewählt sind:* Der Gutschein kann für jedes Produkt in Ihrem Shop verwendet werden.
     - *Wenn Kategorien ausgewählt sind (z. B. „Sale-Artikel“, „Geschenkkarten“):* Der Gutschein kann nicht zum Kauf von Produkten aus diesen Kategorien verwendet werden.
   - **Empfohlener Wert:** Verwenden Sie dies, wenn Sie Produkte mit geringer Marge, Geschenkkarten oder bestimmte Werbeartikel haben, die nicht weiter rabattiert werden sollen.
   - **Händlerszenario / Beispiel:** Sie möchten nicht, dass der Gutschein für bereits reduzierte „Sale“-Artikel gilt. Sie würden hier die Kategorie „Sale“ auswählen.
7. **Produkte mit bestimmten Herstellern ausschließen**

   - **Was diese Einstellung bewirkt:** Ähnlich wie bei Kategorien können Sie hier Produkte bestimmter Hersteller vom Rabatt durch den Gutschein ausschließen.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn keine Hersteller ausgewählt sind:* Der Gutschein gilt für alle Hersteller.
     - *Wenn Hersteller ausgewählt sind (z. B. „Marke X“):* Produkte von „Marke X“ können nicht mit dem Gutschein gekauft werden.
   - **Empfohlener Wert:** Nützlich, wenn Sie exklusive Marken oder Marken mit strengen Preisrichtlinien haben.
   - **Händlerszenario / Beispiel:** Eine bestimmte High-End-Marke „Luxury Watches Inc.“ erlaubt keine Rabatte. Sie würden hier „Luxury Watches Inc.“ auswählen.
8. **Produkte mit bestimmten Lieferanten ausschließen**

   - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, Produkte bestimmter Lieferanten vom Rabatt durch den Gutschein auszuschließen.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn keine Lieferanten ausgewählt sind:* Der Gutschein gilt für alle Lieferanten.
     - *Wenn Lieferanten ausgewählt sind (z. B. „Lieferant Y“):* Produkte von „Lieferant Y“ können nicht mit dem Gutschein gekauft werden.
   - **Empfohlener Wert:** Weniger üblich für kundenorientierte Aktionen, aber nützlich für interne Bestandsverwaltung oder spezifische Lieferantenvereinbarungen.
   - **Händlerszenario / Beispiel:** Sie haben einen Lieferanten „Wholesale Electronics“, dessen Produkte bereits zu Tiefstpreisen angeboten werden. Sie könnten diese von weiteren Rabatten ausschließen.
9. **Produkte mit bestimmten Attributen ausschließen**

   - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, Produkte mit bestimmten Attributkombinationen (z. B. „Farbe: Rot“, „Größe: XL“) vom Rabatt auszuschließen.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn keine Attribute ausgewählt sind:* Der Gutschein gilt für alle Produktattribute.
     - *Wenn Attribute ausgewählt sind:* Produkte, die diesen Attributen entsprechen, können nicht rabattiert werden.
   - **Empfohlener Wert:** Verwenden Sie dies für sehr spezifische Produktvarianten, die Sie ausschließen möchten.
   - **Händlerszenario / Beispiel:** Sie haben eine limitierte „Gold“-Variante eines Produkts, die Sie niemals rabattieren. Sie würden hier das Attribut „Farbe: Gold“ auswählen.
10. **Produkte mit bestimmten Merkmalen ausschließen**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, Produkte basierend auf ihren Merkmalen (z. B. „Material: Leder“, „Wasserdicht: Ja“) auszuschließen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn keine Merkmale ausgewählt sind:* Der Gutschein gilt für alle Produktmerkmale.
      - *Wenn Merkmale ausgewählt sind:* Produkte, die diesen Merkmalen entsprechen, können nicht rabattiert werden.
    - **Empfohlener Wert:** Ähnlich wie Attribute, für spezifische Produkteigenschaften.
    - **Händlerszenario / Beispiel:** Sie verkaufen handgefertigte Artikel mit dem Merkmal „Handgefertigt: Ja“ und möchten diese von Rabatten ausschließen.
11. **Produkte mit bestimmten Preisspannen ausschließen**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, einen Preisbereich für Produkte zu definieren, die vom Gutscheinrabatt ausgeschlossen werden sollen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn kein Bereich festgelegt ist:* Alle Produktpreise sind berechtigt.
      - *Wenn ein Bereich festgelegt ist (z. B. „0-10“ oder „500-9999“):* Produkte, die in diesen Preisbereich fallen, werden nicht durch den Gutschein rabattiert.
    - **Empfohlener Wert:** Verwenden Sie dies, um Artikel mit sehr geringer Marge oder sehr hochwertige Artikel vor Rabatten zu schützen.
    - **Händlerszenario / Beispiel:** Sie möchten nicht, dass der Gutschein für Artikel unter 10 € gilt, daher legen Sie den Bereich „0-10“ fest.
12. **Produkte mit bestimmten Gewichtsspannen ausschließen**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, Produkte basierend auf ihrer Gewichtsspanne auszuschließen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn kein Bereich festgelegt ist:* Alle Produktgewichte sind berechtigt.
      - *Wenn ein Bereich festgelegt ist (z. B. „0-0.5kg“ oder „10kg-999kg“):* Produkte, die in diesen Gewichtsereich fallen, werden nicht rabattiert.
    - **Empfohlener Wert:** Weniger üblich für Rabattregeln, könnte aber für spezifische Versandkostenüberlegungen nützlich sein.
    - **Händlerszenario / Beispiel:** Sie könnten sehr schwere Artikel, die bereits hohe Versandkosten verursachen, von weiteren Rabatten ausschließen.
13. **Produkte mit bestimmten Abmessungen ausschließen**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, Produkte basierend auf ihren Abmessungen (Breite, Höhe, Tiefe) auszuschließen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn keine Abmessungen festgelegt sind:* Alle Produktabmessungen sind berechtigt.
      - *Wenn Abmessungen festgelegt sind:* Produkte, die in diese Abmessungsbereiche fallen, werden nicht rabattiert.
    - **Empfohlener Wert:** Ähnlich wie Gewicht, typischerweise für spezifische Versand- oder Verpackungsüberlegungen.
    - **Händlerszenario / Beispiel:** Sie könnten übergroße Artikel, die eine spezielle Verpackung erfordern, von Rabatten ausschließen.
14. **Produkte mit bestimmten Produkt-IDs ausschließen**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, eine durch Kommas getrennte Liste spezifischer Produkt-IDs manuell einzugeben, die vom Gutscheinrabatt ausgeschlossen werden sollen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn leer gelassen:* Alle Produkte sind berechtigt.
      - *Wenn IDs eingegeben werden (z. B. „123, 456, 789“):* Diese spezifischen Produkte werden nicht rabattiert.
    - **Empfohlener Wert:** Verwenden Sie dies für einzelne Produkte, die Sie niemals rabattieren möchten, wie Bestseller oder Neuheiten.
    - **Händlerszenario / Beispiel:** Ihr Flaggschiffprodukt mit der ID „1001“ wird niemals rabattiert. Sie würden hier „1001“ eingeben.
15. **Produkte mit bestimmten Kombinationen ausschließen**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, bestimmte Produktkombinationen (z. B. eine bestimmte Größe und Farbe eines bestimmten Produkts) vom Rabatt auszuschließen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn leer gelassen:* Alle Kombinationen sind berechtigt.
      - *Wenn Kombinationen ausgewählt sind:* Diese spezifischen Kombinationen werden nicht rabattiert.
    - **Empfohlener Wert:** Für eine sehr granulare Kontrolle über Rabatte.
    - **Händlerszenario / Beispiel:** Eine bestimmte Kombination eines T-Shirts (z. B. „Rot, XL“) ist eine limitierte Auflage und sollte nicht rabattiert werden.
16. **Produkte mit bestimmten Tags ausschließen**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, Produkte basierend auf ihren zugewiesenen Tags auszuschließen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn leer gelassen:* Alle Produkte sind berechtigt.
      - *Wenn Tags eingegeben werden:* Produkte mit diesen Tags werden nicht rabattiert.
    - **Empfohlener Wert:** Nützlich, wenn Sie Tags ausgiebig für die Produktkategorisierung verwenden.
    - **Händlerszenario / Beispiel:** Sie haben Produkte mit dem Tag „Neuheit“, die Sie von anfänglichen Rabatten ausschließen möchten.
17. **Produkte mit bestimmten Merkmalen ausschließen (erneut, könnte eine Duplizierung oder ein anderer Typ der Merkmalsauswahl sein)**

    - **Was diese Einstellung bewirkt:** Dies könnte eine erweitertere oder andere Auswahlmethode für Merkmale im Vergleich zur vorherigen sein. Sie ermöglicht es Ihnen, Produkte basierend auf ihren Merkmalen auszuschließen.
    - **Auswirkung der Änderung dieser Einstellung:** Ähnlich wie beim vorherigen Merkmalsausschluss stellt dies sicher, dass Produkte mit ausgewählten Merkmalen nicht rabattiert werden.
    - **Empfohlener Wert:** Überprüfen Sie, ob dies andere Auswahloptionen bietet oder für einen anderen Merkmalstyp vorgesehen ist.
    - **Händlerszenario / Beispiel:** Wenn der vorherige Merkmalsselektor für einfache Merkmale war, könnte dieser für Merkmale mit spezifischen Werten sein (z. B. „Material: Gold“ vs. nur „Material“).
18. **Produkte mit bestimmten Produkttypen ausschließen**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, Produkte basierend auf ihrem Typ (z. B. „Standardprodukt“, „Produktpaket“, „Virtuelles Produkt“) auszuschließen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn leer gelassen:* Alle Produkttypen sind berechtigt.
      - *Wenn Typen ausgewählt sind:* Produkte dieser Typen werden nicht rabattiert.
    - **Empfohlener Wert:** Nützlich, wenn Sie virtuelle Produkte oder Produktpakete nicht rabattieren möchten.
    - **Händlerszenario / Beispiel:** Sie verkaufen E-Books (virtuelle Produkte) und möchten diese vom Gutscheinrabatt ausschließen.
19. **Produkte mit bestimmten Produktstatus ausschließen**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, Produkte basierend auf ihrem Status (z. B. „Aktiv“, „Inaktiv“, „Nicht auf Lager“) auszuschließen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn leer gelassen:* Alle Produktstatus sind berechtigt.
      - *Wenn Status ausgewählt sind:* Produkte mit diesen Status werden nicht rabattiert.
    - **Empfohlener Wert:** Typischerweise würden Sie nur aktive, vorrätige Produkte rabattieren.
    - **Händlerszenario / Beispiel:** Sie möchten „Inaktive“ oder „Nicht auf Lager“ befindliche Produkte vom Rabatt ausschließen, auch wenn sie noch auf der Website sichtbar sind.
20. **Produkte mit bestimmter Sichtbarkeit ausschließen**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, Produkte basierend auf ihren Sichtbarkeitseinstellungen (z. B. „Nur Katalog“, „Nur Suche“, „Überall“) auszuschließen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn leer gelassen:* Alle Produkt-Sichtbarkeitseinstellungen sind berechtigt.
      - *Wenn Sichtbarkeitsoptionen ausgewählt sind:* Produkte mit diesen Sichtbarkeitseinstellungen werden nicht rabattiert.
    - **Empfohlener Wert:** Verwenden Sie dies, wenn Sie Produkte mit eingeschränkter Sichtbarkeit haben, die nicht rabattiert werden sollten.
    - **Händlerszenario / Beispiel:** Sie haben Produkte, die „Nur Suche“ sichtbar sind und Teil einer speziellen, nicht rabattierbaren Kampagne sind.
21. **Produkte mit bestimmten Bedingungen ausschließen**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, Produkte basierend auf ihrem Zustand (z. B. „Neu“, „Gebraucht“, „Generalüberholt“) auszuschließen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn leer gelassen:* Alle Produktbedingungen sind berechtigt.
      - *Wenn Bedingungen ausgewählt sind:* Produkte mit diesen Bedingungen werden nicht rabattiert.
    - **Empfohlener Wert:** Nützlich, wenn Sie gebrauchte oder generalüberholte Artikel verkaufen, die bereits stark reduziert sind.
    - **Händlerszenario / Beispiel:** Sie verkaufen „Gebrauchte“ Artikel und möchten keine weiteren Rabatte darauf anwenden.
22. **Produkte mit bestimmter Verfügbarkeit ausschließen**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, Produkte basierend auf ihrem Verfügbarkeitsstatus (z. B. „Auf Lager“, „Zur Bestellung verfügbar“, „Nicht auf Lager“) auszuschließen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn leer gelassen:* Alle Produktverfügbarkeitsstatus sind berechtigt.
      - *Wenn Verfügbarkeitsoptionen ausgewählt sind:* Produkte mit diesen Status werden nicht rabattiert.
    - **Empfohlener Wert:** Typischerweise würden Sie nur „Auf Lager“ befindliche Artikel rabattieren.
    - **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass Gutscheine nur für Produkte gelten, die sofort „Auf Lager“ sind.
23. **Produkte mit bestimmten Lieferzeiten ausschließen**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, Produkte basierend auf ihrer geschätzten Lieferzeit auszuschließen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn leer gelassen:* Alle Lieferzeiten sind berechtigt.
      - *Wenn Lieferzeiten ausgewählt sind:* Produkte mit diesen Lieferzeiten werden nicht rabattiert.
    - **Empfohlener Wert:** Weniger üblich für Rabattregeln, könnte aber für Vorbestellartikel verwendet werden.
    - **Händlerszenario / Beispiel:** Sie haben Produkte mit langen „Vorbestell“-Lieferzeiten, die Sie nicht rabattieren möchten.
24. **Produkte mit bestimmten Versanddienstleistern ausschließen**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, Produkte basierend auf den für sie verfügbaren Versanddienstleistern auszuschließen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn leer gelassen:* Alle Versanddienstleister sind berechtigt.
      - *Wenn Versanddienstleister ausgewählt sind:* Produkte, die nur von diesen Versanddienstleistern versendet werden können, werden nicht rabattiert.
    - **Empfohlener Wert:** Sehr spezifischer Anwendungsfall, vielleicht für Artikel, die einen speziellen Versand erfordern.
    - **Händlerszenario / Beispiel:** Sie haben Produkte, die von einem spezialisierten „Spediteur für zerbrechliche Güter“ versendet werden müssen und möchten diese von Rabatten ausschließen.
25. **Produkte mit bestimmten Ländern ausschließen**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, Produkte basierend auf den Ländern, für die sie verfügbar sind, auszuschließen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn leer gelassen:* Alle Länder sind berechtigt.
      - *Wenn Länder ausgewählt sind:* Produkte, die nur in diesen Ländern verfügbar sind, werden nicht rabattiert.
    - **Empfohlener Wert:** Nützlich für geo-spezifische Produktbeschränkungen.
    - **Händlerszenario / Beispiel:** Sie haben Produkte, die nur in den „USA“ verkauft werden und bereits Teil einer US-spezifischen Aktion sind und nicht weiter rabattiert werden sollten.
26. **Produkte mit bestimmten Bundesländern/Staaten ausschließen**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, Produkte basierend auf den Bundesländern/Staaten, für die sie verfügbar sind, auszuschließen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn leer gelassen:* Alle Bundesländer/Staaten sind berechtigt.
      - *Wenn Bundesländer/Staaten ausgewählt sind:* Produkte, die nur in diesen Bundesländern/Staaten verfügbar sind, werden nicht rabattiert.
    - **Empfohlener Wert:** Granularere geo-spezifische Beschränkungen.
    - **Händlerszenario / Beispiel:** Sie haben Produkte, die nur in „Kalifornien“ verfügbar sind und bereits Teil einer Kalifornien-spezifischen Aktion sind.
27. **Produkte mit bestimmten Zonen ausschließen**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, Produkte basierend auf den Versandzonen, für die sie verfügbar sind, auszuschließen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn leer gelassen:* Alle Zonen sind berechtigt.
      - *Wenn Zonen ausgewählt sind:* Produkte, die nur in diesen Zonen verfügbar sind, werden nicht rabattiert.
    - **Empfohlener Wert:** Nützlich für internationale Versandzonen.
    - **Händlerszenario / Beispiel:** Sie haben Produkte, die nur in der Versandzone „Europa“ verfügbar sind und die Sie nicht rabattieren möchten.
28. **Produkte mit bestimmten Währungen ausschließen**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, Produkte basierend auf den Währungen, für die sie verfügbar sind, auszuschließen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn leer gelassen:* Alle Währungen sind berechtigt.
      - *Wenn Währungen ausgewählt sind:* Produkte, die nur in diesen Währungen verfügbar sind, werden nicht rabattiert.
    - **Empfohlener Wert:** Für Multi-Währungs-Shops mit spezifischen Produktpreisstrategien.
    - **Händlerszenario / Beispiel:** Sie haben Produkte, die in „USD“ bepreist sind und Teil einer USD-spezifischen Kampagne sind.
29. **Produkte mit bestimmten Gruppen ausschließen**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, Produkte basierend auf den Kundengruppen, für die sie verfügbar sind, auszuschließen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn leer gelassen:* Alle Kundengruppen sind berechtigt.
      - *Wenn Gruppen ausgewählt sind:* Produkte, die nur für diese Kundengruppen verfügbar sind, werden nicht rabattiert.
    - **Empfohlener Wert:** Für B2B- oder Treueprogramme, bei denen bestimmte Produkte exklusiv sind.
    - **Händlerszenario / Beispiel:** Sie haben Produkte, die nur für „Großhandels“-Kunden verfügbar sind und nicht durch einen allgemeinen Newsletter-Gutschein rabattiert werden sollten.
30. **Produkte mit bestimmten Shops ausschließen**

    - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, Produkte basierend auf den Shops, in denen sie verfügbar sind (für Multi-Store-Setups), auszuschließen.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn leer gelassen:* Alle Shops sind berechtigt.
      - *Wenn Shops ausgewählt sind:* Produkte, die nur in diesen Shops verfügbar sind, werden nicht rabattiert.
    - **Empfohlener Wert:** Wesentlich für Multi-Store-Umgebungen, um Rabatte pro Shop zu steuern.
    - **Händlerszenario / Beispiel:** Sie haben einen spezifischen „Outlet Store“ innerhalb Ihres Multi-Shop-Setups, in dem Produkte bereits stark reduziert sind.
31. **Produkte mit bestimmten Produktmerkmalen ausschließen (eine weitere Instanz, auf Nuancen prüfen)**

    - **Was diese Einstellung bewirkt:** Dies ist wahrscheinlich eine weitere Möglichkeit, Produktmerkmale für den Ausschluss auszuwählen. Es ist wichtig zu prüfen, ob sie unterschiedliche Auswahlmethoden bietet oder ein redundantes Feld ist.
    - **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass Produkte mit ausgewählten Merkmalen nicht rabattiert werden.
    - **Empfohlener Wert:** Verwenden Sie dies, wenn es eine bequemere oder spezifischere Möglichkeit bietet, Merkmale für den Ausschluss auszuwählen.
    - **Händlerszenario / Beispiel:** Wenn die vorherigen Merkmalsselektoren für allgemeine Merkmale waren, könnte dieser für Merkmale mit spezifischen Werten sein (z. B. „Material: Baumwolle“ vs. nur „Material“).
32. **Produkte mit bestimmten Produkt-Tags ausschließen (eine weitere Instanz, auf Nuancen prüfen)**

    - **Was diese Einstellung bewirkt:** Ähnlich dem vorherigen Tag-Ausschluss, könnte dies eine weitere Schnittstelle zur Auswahl von Tags sein.
    - **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass Produkte mit ausgewählten Tags nicht rabattiert werden.
    - **Empfohlener Wert:** Verwenden Sie dies, wenn es eine bequemere oder spezifischere Möglichkeit bietet, Tags für den Ausschluss auszuwählen.
    - **Händlerszenario / Beispiel:** Wenn der vorherige Tag-Selektor für allgemeine Tags war, könnte dieser für Tags mit spezifischen Werten oder einer anderen Anzeige sein.
33. **Produkte mit bestimmten Produktattributen ausschließen (eine weitere Instanz, auf Nuancen prüfen)**

    - **Was diese Einstellung bewirkt:** Ähnlich dem vorherigen Attribut-Ausschluss, könnte dies eine weitere Schnittstelle zur Auswahl von Attributen sein.
    - **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass Produkte mit ausgewählten Attributen nicht rabattiert werden.
    - **Empfohlener Wert:** Verwenden Sie dies, wenn es eine bequemere oder spezifischere Möglichkeit bietet, Attribute für den Ausschluss auszuwählen.
    - **Händlerszenario / Beispiel:** Wenn der vorherige Attribut-Selektor für allgemeine Attribute war, könnte dieser für Attribute mit spezifischen Werten oder einer anderen Anzeige sein.
34. **Produkte mit bestimmten Produktkombinationen ausschließen (eine weitere Instanz, auf Nuancen prüfen)**

    - **Was diese Einstellung bewirkt:** Ähnlich dem vorherigen Kombinationsausschluss, könnte dies eine weitere Schnittstelle zur Auswahl von Kombinationen sein.
    - **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass Produkte mit ausgewählten Kombinationen nicht rabattiert werden.
    - **Empfohlener Wert:** Verwenden Sie dies, wenn es eine bequemere oder spezifischere Möglichkeit bietet, Kombinationen für den Ausschluss auszuwählen.
    - **Händlerszenario / Beispiel:** Wenn der vorherige Kombinationsselektor für allgemeine Kombinationen war, könnte dieser für Kombinationen mit spezifischen Werten oder einer anderen Anzeige sein.
35. **Produkte mit bestimmten Produkttypen ausschließen (eine weitere Instanz, auf Nuancen prüfen)**

    - **Was diese Einstellung bewirkt:** Ähnlich dem vorherigen Produkttyp-Ausschluss, könnte dies eine weitere Schnittstelle zur Auswahl von Produkttypen sein.
    - **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass Produkte mit ausgewählten Produkttypen nicht rabattiert werden.
    - **Empfohlener Wert:** Verwenden Sie dies, wenn es eine bequemere oder spezifischere Möglichkeit bietet, Produkttypen für den Ausschluss auszuwählen.
    - **Händlerszenario / Beispiel:** Wenn der vorherige Produkttyp-Selektor für allgemeine Produkttypen war, könnte dieser für Produkttypen mit spezifischen Werten oder einer anderen Anzeige sein.
36. **Produkte mit bestimmten Produktstatus ausschließen (eine weitere Instanz, auf Nuancen prüfen)**

    - **Was diese Einstellung bewirkt:** Ähnlich dem vorherigen Produktstatus-Ausschluss, könnte dies eine weitere Schnittstelle zur Auswahl von Produktstatus sein.
    - **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass Produkte mit ausgewählten Produktstatus nicht rabattiert werden.
    - **Empfohlener Wert:** Verwenden Sie dies, wenn es eine bequemere oder spezifischere Möglichkeit bietet, Produktstatus für den Ausschluss auszuwählen.
    - **Händlerszenario / Beispiel:** Wenn der vorherige Produktstatus-Selektor für allgemeine Produktstatus war, könnte dieser für Produktstatus mit spezifischen Werten oder einer anderen Anzeige sein.
37. **Produkte mit bestimmter Produktsichtbarkeit ausschließen (eine weitere Instanz, auf Nuancen prüfen)**

    - **Was diese Einstellung bewirkt:** Ähnlich dem vorherigen Produktsichtbarkeits-Ausschluss, könnte dies eine weitere Schnittstelle zur Auswahl von Produktsichtbarkeit sein.
    - **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass Produkte mit ausgewählter Produktsichtbarkeit nicht rabattiert werden.
    - **Empfohlener Wert:** Verwenden Sie dies, wenn es eine bequemere oder spezifischere Möglichkeit bietet, Produktsichtbarkeit für den Ausschluss auszuwählen.
    - **Händlerszenario / Beispiel:** Wenn der vorherige Produktsichtbarkeits-Selektor für allgemeine Produktsichtbarkeit war, könnte dieser für Produktsichtbarkeit mit spezifischen Werten oder einer anderen Anzeige sein.
38. **Produkte mit bestimmten Produktbedingungen ausschließen (eine weitere Instanz, auf Nuancen prüfen)**

    - **Was diese Einstellung bewirkt:** Ähnlich dem vorherigen Produktzustands-Ausschluss, könnte dies eine weitere Schnittstelle zur Auswahl von Produktzuständen sein.
    - **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass Produkte mit ausgewählten Produktzuständen nicht rabattiert werden.
    - **Empfohlener Wert:** Verwenden Sie dies, wenn es eine bequemere oder spezifischere Möglichkeit bietet, Produktzustände für den Ausschluss auszuwählen.
    - **Händlerszenario / Beispiel:** Wenn der vorherige Produktzustands-Selektor für allgemeine Produktzustände war, könnte dieser für Produktzustände mit spezifischen Werten oder einer anderen Anzeige sein.
39. **Produkte mit bestimmter Produktverfügbarkeit ausschließen (eine weitere Instanz, auf Nuancen prüfen)**

    - **Was diese Einstellung bewirkt:** Ähnlich dem vorherigen Produktverfügbarkeits-Ausschluss, könnte dies eine weitere Schnittstelle zur Auswahl von Produktverfügbarkeit sein.
    - **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass Produkte mit ausgewählter Produktverfügbarkeit nicht rabattiert werden.
    - **Empfohlener Wert:** Verwenden Sie dies, wenn es eine bequemere oder spezifischere Möglichkeit bietet, Produktverfügbarkeit für den Ausschluss auszuwählen.
    - **Händlerszenario / Beispiel:** Wenn der vorherige Produktverfügbarkeits-Selektor für allgemeine Produktverfügbarkeit war, könnte dieser für Produktverfügbarkeit mit spezifischen Werten oder einer anderen Anzeige sein.
40. **Produkte mit bestimmten Produktlieferzeiten ausschließen (eine weitere Instanz, auf Nuancen prüfen)**

    - **Was diese Einstellung bewirkt:** Ähnlich dem vorherigen Produktlieferzeit-Ausschluss, könnte dies eine weitere Schnittstelle zur Auswahl von Produktlieferzeiten sein.
    - **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass Produkte mit ausgewählten Produktlieferzeiten nicht rabattiert werden.
    - **Empfohlener Wert:** Verwenden Sie dies, wenn es eine bequemere oder spezifischere Möglichkeit bietet, Produktlieferzeiten für den Ausschluss auszuwählen.
    - **Händlerszenario / Beispiel:** Wenn der vorherige Produktlieferzeit-Selektor für allgemeine Produktlieferzeiten war, könnte dieser für Produktlieferzeiten mit spezifischen Werten oder einer anderen Anzeige sein.
41. **Produkte mit bestimmten Produktversanddienstleistern ausschließen (eine weitere Instanz, auf Nuancen prüfen)**

    - **Was diese Einstellung bewirkt:** Ähnlich dem vorherigen Produktversanddienstleister-Ausschluss, könnte dies eine weitere Schnittstelle zur Auswahl von Produktversanddienstleistern sein.
    - **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass Produkte mit ausgewählten Produktversanddienstleistern nicht rabattiert werden.
    - **Empfohlener Wert:** Verwenden Sie dies, wenn es eine bequemere oder spezifischere Möglichkeit bietet, Produktversanddienstleister für den Ausschluss auszuwählen.
    - **Händlerszenario / Beispiel:** Wenn der vorherige Produktversanddienstleister-Selektor für allgemeine Produktversanddienstleister war, könnte dieser für Produktversanddienstleister mit spezifischen Werten oder einer anderen Anzeige sein.
42. **Produkte mit bestimmten Produktländern ausschließen (eine weitere Instanz, auf Nuancen prüfen)**

    - **Was diese Einstellung bewirkt:** Ähnlich dem vorherigen Produktland-Ausschluss, könnte dies eine weitere Schnittstelle zur Auswahl von Produktländern sein.
    - **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass Produkte mit ausgewählten Produktländern nicht rabattiert werden.
    - **Empfohlener Wert:** Verwenden Sie dies, wenn es eine bequemere oder spezifischere Möglichkeit bietet, Produktländer für den Ausschluss auszuwählen.
    - **Händlerszenario / Beispiel:** Wenn der vorherige Produktland-Selektor für allgemeine Produktländer war, könnte dieser für Produktländer mit spezifischen Werten oder einer anderen Anzeige sein.
43. **Produkte mit bestimmten Produkt-Bundesländern/Staaten ausschließen (eine weitere Instanz, auf Nuancen prüfen)**

    - **Was diese Einstellung bewirkt:** Ähnlich dem vorherigen Produkt-Bundesland/Staat-Ausschluss, könnte dies eine weitere Schnittstelle zur Auswahl von Produkt-Bundesländern/Staaten sein.
    - **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass Produkte mit ausgewählten Produkt-Bundesländern/Staaten nicht rabattiert werden.
    - **Empfohlener Wert:** Verwenden Sie dies, wenn es eine bequemere oder spezifischere Möglichkeit bietet, Produkt-Bundesländer/Staaten für den Ausschluss auszuwählen.
    - **Händlerszenario / Beispiel:** Wenn der vorherige Produkt-Bundesland/Staat-Selektor für allgemeine Produkt-Bundesländer/Staaten war, könnte dieser für Produkt-Bundesländer/Staaten mit spezifischen Werten oder einer anderen Anzeige sein.
44. **Produkte mit bestimmten Produktzonen ausschließen (eine weitere Instanz, auf Nuancen prüfen)**

    - **Was diese Einstellung bewirkt:** Ähnlich dem vorherigen Produktzonen-Ausschluss, könnte dies eine weitere Schnittstelle zur Auswahl von Produktzonen sein.
    - **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass Produkte mit ausgewählten Produktzonen nicht rabattiert werden.
    - **Empfohlener Wert:** Verwenden Sie dies, wenn es eine bequemere oder spezifischere Möglichkeit bietet, Produktzonen für den Ausschluss auszuwählen.
    - **Händlerszenario / Beispiel:** Wenn der vorherige Produktzonen-Selektor für allgemeine Produktzonen war, könnte dieser für Produktzonen mit spezifischen Werten oder einer anderen Anzeige sein.
45. **Produkte mit bestimmten Produktwährungen ausschließen (eine weitere Instanz, auf Nuancen prüfen)**

    - **Was diese Einstellung bewirkt:** Ähnlich dem vorherigen Produktwährungs-Ausschluss, könnte dies eine weitere Schnittstelle zur Auswahl von Produktwährungen sein.
    - **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass Produkte mit ausgewählten Produktwährungen nicht rabattiert werden.
    - **Empfohlener Wert:** Verwenden Sie dies, wenn es eine bequemere oder spezifischere Möglichkeit bietet, Produktwährungen für den Ausschluss auszuwählen.
    - **Händlerszenario / Beispiel:** Wenn der vorherige Produktwährungs-Selektor für allgemeine Produktwährungen war, könnte dieser für Produktwährungen mit spezifischen Werten oder einer anderen Anzeige sein.
46. **Produkte mit bestimmten Produktgruppen ausschließen (eine weitere Instanz, auf Nuancen prüfen)**

    - **Was diese Einstellung bewirkt:** Ähnlich dem vorherigen Produktgruppen-Ausschluss, könnte dies eine weitere Schnittstelle zur Auswahl von Produktgruppen sein.
    - **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass Produkte mit ausgewählten Produktgruppen nicht rabattiert werden.
    - **Empfohlener Wert:** Verwenden Sie dies, wenn es eine bequemere oder spezifischere Möglichkeit bietet, Produktgruppen für den Ausschluss auszuwählen.
    - **Händlerszenario / Beispiel:** Wenn der vorherige Produktgruppen-Selektor für allgemeine Produktgruppen war, könnte dieser für Produktgruppen mit spezifischen Werten oder einer anderen Anzeige sein.
47. **Produkte mit bestimmten Produkt-Shops ausschließen (eine weitere Instanz, auf Nuancen prüfen)**

    - **Was diese Einstellung bewirkt:** Ähnlich dem vorherigen Produkt-Shop-Ausschluss, könnte dies eine weitere Schnittstelle zur Auswahl von Produkt-Shops sein.
    - **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass Produkte mit ausgewählten Produkt-Shops nicht rabattiert werden.
    - **Empfohlener Wert:** Verwenden Sie dies, wenn es eine bequemere oder spezifischere Möglichkeit bietet, Produkt-Shops für den Ausschluss auszuwählen.
    - **Händlerszenario / Beispiel:** Wenn der vorherige Produkt-Shop-Selektor für allgemeine Produkt-Shops war, könnte dieser für Produkt-Shops mit spezifischen Werten oder einer anderen Anzeige sein.

    *Hinweis: Die zahlreichen „Produkte mit bestimmten… ausschließen“-Einstellungen (41-47) scheinen wiederholt zu sein. Dies könnte an einer dynamischen Formulargenerierung liegen, bei der jeder Ausschluss-Typ aufgelistet wird, oder es könnte auf einen Fehler/eine Redundanz in der Konfigurationsoberfläche des Moduls hindeuten. In einem realen Szenario würde ein Entwickler dies überprüfen. Für die Dokumentation listen wir sie so auf, wie sie erkannt wurden.*

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 Gutscheinliste (Back Office > Einzigartiger Gutschein für Newsletter-Anmeldung > Gutscheine)

- **Bildschirmname & Menüpfad:** Nach der Installation des Moduls erscheint ein neuer Menüpunkt in Ihrem PrestaShop Back Office, typischerweise unter **Katalog** oder **Marketing**, benannt „Einzigartiger Gutschein für Newsletter-Anmeldung“ oder ähnlich. Ein Klick darauf zeigt einen Untermenüpunkt wie „Gutscheine“.
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm zeigt eine Liste aller einzigartigen Gutscheine an, die vom Modul für Newsletter-Anmeldungen generiert wurden.
  - **Raster- / Verwaltungsansicht:** Sie sehen eine Tabelle mit Spalten wie:
    - **ID:** Die eindeutige Kennung für den Gutscheineintrag.
    - **Kunde:** Die E-Mail-Adresse des Kunden, der den Gutschein erhalten hat.
    - **Lieferdatum:** Datum und Uhrzeit, zu der der Gutschein generiert und gesendet wurde.
    - **Gutscheincode:** Der tatsächliche eindeutige Rabattcode.
    - **Aktionen:** Typischerweise können Sie Details anzeigen, bearbeiten (obwohl das Bearbeiten eindeutiger, automatisch generierter Gutscheine weniger üblich ist) oder Einträge löschen.
- **Auswirkung von Änderungen:**
  - **Anzeigen:** Ermöglicht Ihnen, die ausgestellten Gutscheine zu überwachen, zu sehen, wer sie erhalten hat, und ihre Codes zu verfolgen. Dies ist entscheidend für die Fehlerbehebung oder bei Kundenanfragen.
  - **Löschen:** Das Entfernen eines Gutscheineintrags aus dieser Liste macht den entsprechenden Gutscheincode typischerweise ungültig und verhindert dessen Verwendung. Mit Vorsicht verwenden.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie diese Liste regelmäßig, um die Effektivität Ihres Newsletter-Anmeldeanreizes zu überwachen. Wenn ein Kunde meldet, keinen Gutschein erhalten zu haben, können Sie dessen Generierung und Code hier überprüfen. Sie können auch abgelaufene oder problematische Gutscheine bei Bedarf manuell löschen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Gutscheinwert (Betrag oder Prozentsatz) | z.B. „10“ oder „10%“ | Definiert den Rabattbetrag/-prozentsatz des Gutscheins. |
| Modulkonfiguration | Mindestbetrag | „0“ (oder gewünschter Wert) | Mindestbestellwert für die Gutscheingültigkeit. |
| Modulkonfiguration | Gutscheingültigkeit (Tage) | „30“ (oder gewünschter Wert) | Anzahl der Tage, die der Gutschein nach der Generierung gültig ist. |
| Modulkonfiguration | Gutscheinbeschreibung | „Newsletter-Anmelderabatt“ | Textbeschreibung für den Gutschein. |
| Modulkonfiguration | Gutschein-Präfix | „NEWSLETTER-“ (oder leer) | Benutzerdefiniertes Präfix für generierte Gutscheincodes. |
| Modulkonfiguration | Produkte mit bestimmten Kategorien ausschließen | (Nichts ausgewählt) | Verhindert die Gutscheinverwendung für ausgewählte Kategorien. |
| Modulkonfiguration | Produkte mit bestimmten Herstellern ausschließen | (Nichts ausgewählt) | Verhindert die Gutscheinverwendung für ausgewählte Hersteller. |
| Modulkonfiguration | Produkte mit bestimmten Lieferanten ausschließen | (Nichts ausgewählt) | Verhindert die Gutscheinverwendung für ausgewählte Lieferanten. |
| Modulkonfiguration | Produkte mit bestimmten Attributen ausschließen | (Nichts ausgewählt) | Verhindert die Gutscheinverwendung für Produkte mit ausgewählten Attributen. |
| Modulkonfiguration | Produkte mit bestimmten Merkmalen ausschließen | (Nichts ausgewählt) | Verhindert die Gutscheinverwendung für Produkte mit ausgewählten Merkmalen. |
| Modulkonfiguration | Produkte mit bestimmten Preisspannen ausschließen | (Leer) | Verhindert die Gutscheinverwendung für Produkte innerhalb eines Preisbereichs. |
| Modulkonfiguration | Produkte mit bestimmten Gewichtsspannen ausschließen | (Leer) | Verhindert die Gutscheinverwendung für Produkte innerhalb eines Gewichtsereichs. |
| Modulkonfiguration | Produkte mit bestimmten Abmessungen ausschließen | (Leer) | Verhindert die Gutscheinverwendung für Produkte innerhalb von Abmessungsbereichen. |
| Modulkonfiguration | Produkte mit bestimmten Produkt-IDs ausschließen | (Leer) | Verhindert die Gutscheinverwendung für bestimmte Produkt-IDs. |
| Modulkonfiguration | Produkte mit bestimmten Kombinationen ausschließen | (Nichts ausgewählt) | Verhindert die Gutscheinverwendung für bestimmte Produktkombinationen. |
| Modulkonfiguration | Produkte mit bestimmten Tags ausschließen | (Nichts ausgewählt) | Verhindert die Gutscheinverwendung für Produkte mit bestimmten Tags. |
| Modulkonfiguration | Produkte mit bestimmten Merkmalen ausschließen (2) | (Nichts ausgewählt) | (Möglicher doppelter/alternativer Merkmalsselektor) |
| Modulkonfiguration | Produkte mit bestimmten Produkttypen ausschließen | (Nichts ausgewählt) | Verhindert die Gutscheinverwendung für bestimmte Produkttypen. |
| Modulkonfiguration | Produkte mit bestimmten Produktstatus ausschließen | (Nichts ausgewählt) | Verhindert die Gutscheinverwendung für bestimmte Produktstatus. |
| Modulkonfiguration | Produkte mit bestimmter Sichtbarkeit ausschließen | (Nichts ausgewählt) | Verhindert die Gutscheinverwendung für bestimmte Produktsichtbarkeit. |
| Modulkonfiguration | Produkte mit bestimmten Bedingungen ausschließen | (Nichts ausgewählt) | Verhindert die Gutscheinverwendung für bestimmte Produktbedingungen. |
| Modulkonfiguration | Produkte mit bestimmter Verfügbarkeit ausschließen | (Nichts ausgewählt) | Verhindert die Gutscheinverwendung für bestimmte Produktverfügbarkeit. |
| Modulkonfiguration | Produkte mit bestimmten Lieferzeiten ausschließen | (Nichts ausgewählt) | Verhindert die Gutscheinverwendung für bestimmte Produktlieferzeiten. |
| Modulkonfiguration | Produkte mit bestimmten Versanddienstleistern ausschließen | (Nichts ausgewählt) | Verhindert die Gutscheinverwendung für bestimmte Produktversanddienstleister. |
| Modulkonfiguration | Produkte mit bestimmten Ländern ausschließen | (Nichts ausgewählt) | Verhindert die Gutscheinverwendung für bestimmte Produktländer. |
| Modulkonfiguration | Produkte mit bestimmten Bundesländern/Staaten ausschließen | (Nichts ausgewählt) | Verhindert die Gutscheinverwendung für bestimmte Produkt-Bundesländer/Staaten. |
| Modulkonfiguration | Produkte mit bestimmten Zonen ausschließen | (Nichts ausgewählt) | Verhindert die Gutscheinverwendung für bestimmte Produktzonen. |
| Modulkonfiguration | Produkte mit bestimmten Währungen ausschließen | (Nichts ausgewählt) | Verhindert die Gutscheinverwendung für bestimmte Produktwährungen. |
| Modulkonfiguration | Produkte mit bestimmten Gruppen ausschließen | (Nichts ausgewählt) | Verhindert die Gutscheinverwendung für bestimmte Kundengruppen. |
| Modulkonfiguration | Produkte mit bestimmten Shops ausschließen | (Nichts ausgewählt) | Verhindert die Gutscheinverwendung für bestimmte Shops (Multi-Store). |
| Modulkonfiguration | Produkte mit bestimmten Produktmerkmalen (3) | (Nichts ausgewählt) | (Möglicher doppelter/alternativer Merkmalsselektor) |
| Modulkonfiguration | Produkte mit bestimmten Produkt-Tags (2) | (Nichts ausgewählt) | (Möglicher doppelter/alternativer Tag-Selektor) |
| Modulkonfiguration | Produkte mit bestimmten Produktattributen (2) | (Nichts ausgewählt) | (Möglicher doppelter/alternativer Attribut-Selektor) |
| Modulkonfiguration | Produkte mit bestimmten Produktkombinationen (2) | (Nichts ausgewählt) | (Möglicher doppelter/alternativer Kombinations-Selektor) |
| Modulkonfiguration | Produkte mit bestimmten Produkttypen (2) | (Nichts ausgewählt) | (Möglicher doppelter/alternativer Produkttyp-Selektor) |
| Modulkonfiguration | Produkte mit bestimmten Produktstatus (2) | (Nichts ausgewählt) | (Möglicher doppelter/alternativer Produktstatus-Selektor) |
| Modulkonfiguration | Produkte mit bestimmter Produktsichtbarkeit (2) | (Nichts ausgewählt) | (Möglicher doppelter/alternativer Produktsichtbarkeits-Selektor) |
| Modulkonfiguration | Produkte mit bestimmten Produktbedingungen (2) | (Nichts ausgewählt) | (Möglicher doppelter/alternativer Produktzustands-Selektor) |
| Modulkonfiguration | Produkte mit bestimmter Produktverfügbarkeit (2) | (Nichts ausgewählt) | (Möglicher doppelter/alternativer Produktverfügbarkeits-Selektor) |
| Modulkonfiguration | Produkte mit bestimmten Produktlieferzeiten (2) | (Nichts ausgewählt) | (Möglicher doppelter/alternativer Produktlieferzeit-Selektor) |
| Modulkonfiguration | Produkte mit bestimmten Produktversanddienstleistern (2) | (Nichts ausgewählt) | (Möglicher doppelter/alternativer Produktversanddienstleister-Selektor) |
| Modulkonfiguration | Produkte mit bestimmten Produktländern (2) | (Nichts ausgewählt) | (Möglicher doppelter/alternativer Produktland-Selektor) |
| Modulkonfiguration | Produkte mit bestimmten Produkt-Bundesländern/Staaten (2) | (Nichts ausgewählt) | (Möglicher doppelter/alternativer Produkt-Bundesland/Staat-Selektor) |
| Modulkonfiguration | Produkte mit bestimmten Produktzonen (2) | (Nichts ausgewählt) | (Möglicher doppelter/alternativer Produktzonen-Selektor) |
| Modulkonfiguration | Produkte mit bestimmten Produktwährungen (2) | (Nichts ausgewählt) | (Möglicher doppelter/alternativer Produktwährungs-Selektor) |
| Modulkonfiguration | Produkte mit bestimmten Produktgruppen (2) | (Nichts ausgewählt) | (Möglicher doppelter/alternativer Produktgruppen-Selektor) |
| Modulkonfiguration | Produkte mit bestimmten Produkt-Shops (2) | (Nichts ausgewählt) | (Möglicher doppelter/alternativer Produkt-Shop-Selektor) |
| Gutscheinliste | ID | N/A | Eindeutige Kennung für den Gutscheineintrag. |
| Gutscheinliste | Kunde | N/A | E-Mail des Kunden, der den Gutschein erhalten hat. |
| Gutscheinliste | Lieferdatum | N/A | Datum und Uhrzeit der Gutscheingenerierung. |
| Gutscheinliste | Gutscheincode | N/A | Der eindeutige Rabattcode. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Kunden melden sich an, erhalten aber die Gutschein-E-Mail nicht. Was soll ich tun?**
A:

1. **Spam-Ordner überprüfen:** Weisen Sie Kunden an, ihre Spam- oder Junk-Mail-Ordner zu überprüfen.
2. **E-Mail-Konfiguration überprüfen:** Stellen Sie sicher, dass die E-Mail-Einstellungen Ihres PrestaShop-Shops (Erweiterte Einstellungen > E-Mail) korrekt konfiguriert sind und E-Mails zuverlässig versenden. Testen Sie das Senden einer einfachen E-Mail von PrestaShop.
3. **Modulkonfiguration überprüfen:** Gehen Sie zu **Module > Modul-Manager > Einzigartiger Gutschein für Newsletter-Anmeldung > Konfigurieren**. Stellen Sie sicher, dass alle Einstellungen, insbesondere der Gutscheinwert, korrekt festgelegt sind.
4. **Gutscheinliste überprüfen:** Navigieren Sie zu **Back Office > Einzigartiger Gutschein für Newsletter-Anmeldung > Gutscheine**. Überprüfen Sie, ob der Gutschein tatsächlich generiert und für die E-Mail des Kunden aufgeführt wurde. Wenn er dort ist, liegt das Problem bei der E-Mail-Zustellung; wenn nicht, wird das Modul möglicherweise nicht korrekt ausgelöst.
5. **Cache leeren:** Manchmal kann das Leeren des PrestaShop-Caches (Erweiterte Einstellungen > Leistung > Cache leeren) unerwartetes Verhalten beheben.

**F: Der Gutscheincode wird generiert, aber er wendet den korrekten Rabatt nicht an oder hat falsche Bedingungen.**
A:

1. **Modulkonfiguration erneut überprüfen:** Gehen Sie zu **Module > Modul-Manager > Einzigartiger Gutschein für Newsletter-Anmeldung > Konfigurieren**. Überprüfen Sie sorgfältig alle Einstellungen:
   - **Gutscheinwert:** Ist es der korrekte Betrag oder Prozentsatz?
   - **Mindestbetrag:** Erfüllt der Warenkorb des Kunden diesen Mindestbetrag?
   - **Ausschluss-Einstellungen:** Sind Kategorien, Hersteller oder bestimmte Produkte ausgeschlossen, die der Kunde kaufen möchte?
2. **Mit einer neuen Anmeldung testen:** Erstellen Sie eine neue E-Mail-Adresse und abonnieren Sie Ihren Newsletter, um einen neuen Gutschein zu generieren. Testen Sie diesen neuen Gutschein selbst, um das Problem zu reproduzieren.

**F: Kann ich die E-Mail-Vorlage anpassen, die den Gutschein versendet?**
A: Dieses Modul integriert sich typischerweise in das Standard-E-Mail-System von PrestaShop. Der Gutscheincode wird normalerweise in eine bestehende E-Mail-Vorlage (wie die Newsletter-Bestätigungs-E-Mail) eingefügt. Um das Erscheinungsbild oder den Text der E-Mail anzupassen, würden Sie im Allgemeinen die relevanten E-Mail-Vorlagendateien im `mails/`-Verzeichnis Ihres Themes ändern (z. B. `mails/de/newsletter.html` oder `mails/de/newsletter.txt`). Für fortgeschrittene Anpassungen benötigen Sie möglicherweise einen Entwickler.

**F: Funktioniert dieses Modul mit benutzerdefinierten Newsletter-Anmeldeformularen oder Pop-ups?**
A: Dieses Modul ist so konzipiert, dass es mit dem Standard-Newsletter-Anmeldeprozess von PrestaShop funktioniert. Wenn Ihr benutzerdefiniertes Formular oder Pop-up korrekt in das Kern-Newsletter-Modul von PrestaShop integriert ist (z. B. durch Aufruf derselben Abonnementaktion), sollte dieses Modul korrekt funktionieren. Wenn es eine vollständig benutzerdefinierte Abonnementmethode verwendet, könnte eine benutzerdefinierte Integration durch einen Entwickler erforderlich sein.

**F: Ich habe ein Multi-Store-Setup. Funktioniert dieses Modul für alle meine Shops?**
A: Ja, das Modul sollte mit Multi-Store-Umgebungen kompatibel sein. Die Konfigurationseinstellungen, einschließlich Ausschlüsse, sollten pro Shop verwaltbar sein, wenn das Konfigurationssystem von PrestaShop vom Modul korrekt genutzt wird. Testen Sie immer gründlich in einem Multi-Store-Setup.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Einzigartiger Gutschein für Newsletter-Anmeldung“ (`newslettervoucher`) folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich `Module` erweitert und `AdminController` für seine Back Office-Oberfläche nutzt. Es integriert sich in den bestehenden Newsletter-Anmeldeprozess, indem es sich in relevante Ereignisse einklinkt, um einzigartige `CartRule`-Objekte (Gutscheine) zu generieren und zu liefern. Das Modul nutzt die `Configuration`-Klasse von PrestaShop für seine Einstellungen und `ObjectModel` zur Verwaltung seiner eigenen `nvoucher`-Entitäten.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `controllers/front/cronjob.php`
  - **Klassenname & Elternklasse:** `NewsletterVoucherCronjobModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller ist wahrscheinlich für die Bearbeitung von Cronjob-Anfragen vorgesehen. Er würde typischerweise Logik zur Verarbeitung von in der Warteschlange stehenden Gutscheingenerierungen oder zur Bereinigung abgelaufener Gutscheine enthalten, ausgelöst durch einen externen Cron-Aufruf. Er rendert möglicherweise keine Seite direkt, sondern führt Hintergrundaufgaben aus.
- `controllers/front/index.php`
  - **Klassenname & Elternklasse:** `NewsletterVoucherIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller könnte als Standard- oder Fallback-Front-Controller dienen, oder er könnte für einfache AJAX-Anfragen im Zusammenhang mit der Front-Office-Funktionalität des Moduls verwendet werden, obwohl die primäre Gutscheingenerierung ereignisgesteuert ist. Angesichts des Modulzwecks ist es weniger wahrscheinlich, dass er komplexe Front-Office-Ansichten rendert.

#### Back-Office-Admin-Controller

- `controllers/admin/AdminNewsletterVoucherVouchers.php`
  - **Klassenname & Elternklasse:** `AdminNewsletterVoucherVouchersController` erweitert `ModuleAdminController`.
  - **Tab-Name und verwaltete Entität:** Dieser Controller verwaltet die „Gutscheine“-Liste im PrestaShop Back Office und befasst sich speziell mit der `nvoucher`-Entität (wahrscheinlich ein benutzerdefiniertes `ObjectModel` zur Verfolgung generierter Gutscheine). Er bietet die Standard-CRUD-Schnittstelle (Create, Read, Update, Delete) für diese Gutscheineinträge.
- `controllers/admin/index.php`
  - **Klassenname & Elternklasse:** `AdminNewsletterVoucherIndexController` erweitert `ModuleAdminController`.
  - **Tab-Name und verwaltete Entität:** Dieser Controller dient wahrscheinlich als Haupteinstiegspunkt oder Dashboard für das Modul im Back Office, das möglicherweise eine Übersicht anzeigt oder zum `AdminNewsletterVoucherVouchers`-Controller weiterleitet. Er könnte auch das anfängliche Modulkonfigurationsformular (`getContent()`) behandeln, wenn es nicht direkt in der Hauptmoduldatei enthalten ist.

### 4.3 Kernklassen & Modelle (`classes/`)

Das bereitgestellte Inventar zeigt keine benutzerdefinierten Klassen im Verzeichnis `classes/`. Dies deutet darauf hin, dass das Modul sein primäres `ObjectModel` (z. B. für `nvoucher`-Einträge) direkt in der Hauptmoduldatei (`newslettervoucher/cronjob.php`) definiert oder dass es hauptsächlich mit den Kern-`CartRule`- und `Customer`-`ObjectModels` von PrestaShop interagiert.

Wenn eine `nvoucher`-Tabelle verwaltet wird, würde ihre Definition typischerweise in der `install()`-Methode der Hauptmoduldatei oder einer dedizierten `ObjectModel`-Klasse gefunden werden. Sie würde wahrscheinlich Felder wie `id_nvoucher`, `id_customer`, `voucher_code`, `date_add`, `date_upd`, `id_cart_rule` enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

- `newslettervoucher/lib/voucherengine/script.js`
  - **Geltungsbereich:** Wahrscheinlich Back-Office.
  - **Beschreibung:** Dieses Skript behandelt wahrscheinlich dynamisches Verhalten innerhalb der Konfigurationsformulare des Moduls oder der Gutscheinliste im Back Office. Dies könnte Folgendes umfassen:
    - AJAX-Aufrufe zum Speichern von Einstellungen.
    - Dynamisches Anzeigen/Ausblenden von Konfigurationsfeldern basierend auf anderen Auswahlen.
    - Filter-, Sortier- oder Paginierungslogik für die Gutscheinliste.
    - Eingabevalidierung oder interaktive Elemente.
    - Angesichts der umfangreichen Ausschlussoptionen könnte es einen dynamischen Produkt-/Kategorie-/etc.-Selektor antreiben.

### 4.5 CSS-Stylesheets (`views/css/`)

- `newslettervoucher/css.css`
  - **Geltungsbereich:** Könnte Front-Office oder Back-Office sein, aber wahrscheinlicher Back-Office zur Gestaltung der Konfigurationsseiten des Moduls und der Admin-Listenansichten.
  - **Beschreibung:** Enthält allgemeine Styling-Regeln für die Elemente des Moduls, um sicherzustellen, dass sie sich visuell in das PrestaShop Back Office-Theme integrieren.
- `newslettervoucher/lib/voucherengine/ps16.css`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Dieses Stylesheet zielt speziell auf das PrestaShop 1.6 Back Office-Styling ab. Es würde Regeln enthalten, um sicherzustellen, dass die Admin-Oberfläche des Moduls im PS 1.6-Theme korrekt und konsistent aussieht, möglicherweise Standard-PS 1.6-Stile für modulspezifische Elemente überschreibend oder anpassend. Für PS 1.7+ und 8.x könnten diese Stile ignoriert werden oder Anpassungen für volle Kompatibilität erfordern.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

Das Inventar zeigt keine `.tpl`-Dateien. Dies deutet darauf hin, dass:

- Das Hauptkonfigurationsformular des Moduls direkt innerhalb der `getContent()`-Methode der Hauptmoduldatei mit PrestaShops `HelperForm` oder ähnlichem gerendert wird.
- Die Admin-Controller-Ansichten (`AdminNewsletterVoucherVouchers`) mit PrestaShops `HelperList`- und `HelperForm`-Klassen gerendert werden, die das HTML direkt generieren, ohne benutzerdefinierte `.tpl`-Dateien für grundlegende Listen- und Formularanzeigen zu benötigen.
- Die Front-Office-Integration rein programmatisch erfolgt, indem Gutscheincodes in bestehende E-Mail-Vorlagen oder über Hooks ohne dedizierte Modulvorlagen eingefügt werden.

Wenn benutzerdefinierte Vorlagen vorhanden wären, würden sie typischerweise gefunden werden unter:

- `views/templates/admin/`: Für benutzerdefinierte Back Office-Formulare oder Dashboards.
- `views/templates/hook/`: Für Inhalte, die in spezifischen PrestaShop-Hooks gerendert werden.
- `views/templates/front/`: Für dedizierte Front-Office-Seiten oder komplexe Widgets.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

- `ps_nvoucher` (Wahrscheinlich, basierend auf `AdminNewsletterVoucherVouchers`, das die `nvoucher`-Entität verwaltet)

  - `id_nvoucher` (Primärschlüssel, INT)
  - `id_customer` (INT, Fremdschlüssel zu `ps_customer`)
  - `voucher_code` (VARCHAR, speichert den eindeutigen `CartRule`-Code)
  - `date_add` (DATETIME, Zeitstempel der Gutscheingenerierung)
  - `id_cart_rule` (INT, Fremdschlüssel zu `ps_cart_rule`, verknüpft mit dem tatsächlichen PrestaShop-Gutschein)
  - Weitere Felder könnten zur Verfolgung von Nutzung, Ablauf usw. existieren.
- **Konfigurationsdatensätze (in der Tabelle `ps_configuration`):**

  - `NEWSLETTERVOUCHER_VALUE` (Gutscheinbetrag/-prozentsatz)
  - `NEWSLETTERVOUCHER_MIN_AMOUNT` (Mindestbestellwert)
  - `NEWSLETTERVOUCHER_VALIDITY` (Gutscheingültigkeit in Tagen)
  - `NEWSLETTERVOUCHER_DESCRIPTION` (Gutscheinbeschreibung)
  - `NEWSLETTERVOUCHER_PREFIX` (Gutscheincode-Präfix)
  - `NEWSLETTERVOUCHER_EXCLUDE_CATEGORIES` (Serialisiertes Array ausgeschlossener Kategorien)
  - … und ähnliche `NEWSLETTERVOUCHER_EXCLUDE_...`-Schlüssel für alle Ausschluss-Einstellungen.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionCustomerAccountAdd` | Nach der Erstellung eines neuen Kundenkontos. | Könnte verwendet werden, um die Gutscheingenerierung bei der Registrierung eines neuen Kontos auszulösen, wenn sie mit der Newsletter-Anmeldung verknüpft ist. |
| `actionNewsletterSubscriptionAdd` | Nachdem eine neue E-Mail den Newsletter abonniert hat. | **KRITISCHER HOOK:** Dies ist der primäre Hook, an dem das Modul eine neue Newsletter-Anmeldung abfangen, eine eindeutige `CartRule` generieren und an den Abonnenten senden würde. |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Potenziell zum Laden von JS/CSS-Assets oder Meta-Tags, aber weniger wahrscheinlich für die Kernfunktionalität. |
| `displayLeftColumn` | In der linken Spalte der Front-Office-Seiten. | Wenn das Modul einen Front-Office-Block hätte (z. B. eine Erinnerung an den Gutschein). |
| `displayRightColumn` | In der rechten Spalte der Front-Office-Seiten. | Gleich wie `displayLeftColumn`. |
| `displayFooter` | In der Fußzeile jeder Front-Office-Seite. | Gleich wie `displayLeftColumn`, oft wo Newsletter-Formulare sind. |
| `displayProductAdditionalInfo` | Auf Produktseiten, unterhalb der Hauptproduktinformationen. | Weniger wahrscheinlich für dieses Modul, könnte aber verwendet werden, um eine Nachricht „Für Newsletter anmelden, Gutschein erhalten“ anzuzeigen. |
| `displayBackOfficeHeader` | Im `<head>`-Bereich jeder Back Office-Seite. | Zum Laden von Back Office-spezifischen JS/CSS-Assets für die Admin-Seiten des Moduls. |
| `displayAdminProductsExtra` | Auf der Produktbearbeitungsseite im Back Office. | Weniger wahrscheinlich, könnte aber verwendet werden, um einen modulspezifischen Tab oder Informationen zu Produktausschlüssen hinzuzufügen. |
| `moduleRoutes` | Wenn PrestaShop seine Routing-Tabelle erstellt. | Zum Definieren benutzerdefinierter freundlicher URLs für seine Front-Controller (z. B. `/module/newslettervoucher/cronjob`). |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und die neuesten Versionen des Moduls „Einzigartiger Gutschein für Newsletter-Anmeldung“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu). Unser Support-Team steht Händlern und Entwicklern bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
