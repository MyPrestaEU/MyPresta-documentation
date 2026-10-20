---
title: "Homepage Best Sellers – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Homepage Best Sellers“ von MyPresta.eu."
sidebar:
  label: "Homepage Best Sellers"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Homepage Best Sellers auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/homepage-best-sellers.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/homepage-best-sellers/)
>
> ---


# Homepage Best Sellers

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für einen PrestaShop-Shop erforderlich und ausreichend für dieses Modul. Es sind keine ungewöhnlichen oder erweiterten Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nachdem Sie das Modul „Homepage Best Sellers“ erfolgreich installiert haben, navigieren Sie zu **Module > Modul-Manager**, suchen Sie „Homepage Best Sellers“ und klicken Sie auf die Schaltfläche „Konfigurieren“. Es wird Ihnen ein einfacher, intuitiver Konfigurationsbildschirm präsentiert.

#### Einstellungen & Optionen:

1. **Anzahl der anzuzeigenden Produkte**

   - **Was diese Einstellung bewirkt:** Dies ist die primäre Steuerung für das Modul. Sie bestimmt genau, wie viele Ihrer meistverkauften Produkte im „Bestseller“-Block auf der Startseite Ihres Shops angezeigt werden.
   - **Auswirkungen einer Änderung dieser Einstellung:**
     - *Wenn aktiviert / auf eine höhere Zahl eingestellt (z. B. 10):* Ihre Startseite zeigt mehr meistverkaufte Produkte an. Dies kann großartig für Shops mit einer breiten Palette beliebter Artikel sein und Kunden mehr Auswahl bieten. Beachten Sie jedoch, dass eine sehr hohe Zahl den Block recht lang machen könnte, mehr Scrollen erfordert oder je nach Ihrem Theme Ihr Startseiten-Design potenziell überladen könnte.
     - *Wenn deaktiviert / auf eine niedrigere Zahl eingestellt (z. B. 4):* Es werden weniger meistverkaufte Produkte angezeigt. Dies macht den Block kompakter und fokussierter, was ideal für minimalistische Designs sein kann oder wenn Sie nur die absolut wichtigsten Artikel hervorheben möchten.
   - **Empfohlener Wert:** Ein guter Ausgangspunkt sind in der Regel **4 bis 8 Produkte**. Dies bietet genügend Abwechslung, ohne die Seite zu überladen. Sie sollten mit verschiedenen Zahlen experimentieren, um zu sehen, was am besten zu Ihrem spezifischen PrestaShop-Theme und dem gesamten Startseiten-Layout passt.
   - **Händlerszenario / Beispiel:** Wenn Sie ein Modegeschäft betreiben und eine kuratierte Auswahl Ihrer absolut angesagtesten Artikel zeigen möchten, könnten Sie dies auf `4` einstellen. Wenn Sie ein großes Elektronikgeschäft haben und die Breite Ihrer beliebten Gadgets demonstrieren möchten, könnte eine Einstellung auf `8` oder `10` effektiver sein.
2. **Produktattribute auf der Produktseite anzeigen** (Konfigurationsschlüssel: `PS_ATTRIBUTE_CATEGORY_DISPLAY`)

   - **Was diese Einstellung bewirkt:** Diese Einstellung, falls in der Modulkonfiguration vorhanden, steuert, ob Produktattribute (wie Größe, Farbe, Material usw.) auf der eigentlichen Produktseite angezeigt werden, wenn ein Kunde ein Produkt ansieht. Es ist wichtig zu beachten, dass `PS_ATTRIBUTE_CATEGORY_DISPLAY` typischerweise eine globale PrestaShop-Kerndatei ist und normalerweise nicht von einem spezifischen Modul wie „Bestseller“ verwaltet wird. Wenn es hier erscheint, ist es wahrscheinlich ein Komfort-Link oder ein Modul, das versucht, eine globale Einstellung zu verwalten.
   - **Auswirkungen einer Änderung dieser Einstellung:**
     - *Wenn aktiviert (z. B. „Ja“ oder angekreuzt):* Produktattribute werden auf der Produktseite deutlich sichtbar sein, sodass Kunden spezifische Variationen auswählen können (z. B. „Rot, Größe M“). Dies ist entscheidend für Produkte mit Optionen.
     - *Wenn deaktiviert (z. B. „Nein“ oder nicht angekreuzt):* Produktattribute könnten auf der Produktseite ausgeblendet oder nicht auf die Standardweise angezeigt werden, was Kunden verwirren könnte, die versuchen, Produktvariationen auszuwählen.
   - **Empfohlener Wert:** **JA** (oder aktiviert). Für fast alle E-Commerce-Shops ist es unerlässlich, Produktattribute auf der Produktseite anzuzeigen, damit Kunden Variationen auswählen und fundierte Kaufentscheidungen treffen können.
   - **Händlerszenario / Beispiel:** Wenn Sie Schuhe verkaufen, stellt die Aktivierung dieser Option sicher, dass Kunden „Größe 9, Schwarz“ aus den Optionen auf der Produktseite des Schuhs auswählen können. Eine Deaktivierung würde es ihnen unmöglich machen, ihre gewünschte Größe oder Farbe anzugeben.

#### Interne/Nicht konfigurierbare Einstellungen:

- `update_`, `updatev_`: Dies sind interne Parameter zur Modulversionsverfolgung und Update-Prüfung. Sie sind nicht für die Interaktion des Händlers gedacht, stellen aber sicher, dass das Modul seine Version überprüfen und Sie möglicherweise über Updates informieren kann.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul „Homepage Best Sellers“ ist auf Einfachheit und Effizienz ausgelegt. Es führt **keine** zusätzlichen dedizierten Admin-Bildschirme, benutzerdefinierten Menüpunkte oder komplexe Controller-Ansichten über seine einzelne, unkomplizierte Konfigurationsseite hinaus ein, die über den Modul-Manager zugänglich ist. Die gesamte Verwaltung erfolgt direkt auf diesem einen Bildschirm.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung
