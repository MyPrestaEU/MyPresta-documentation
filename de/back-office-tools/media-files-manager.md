---
title: "Medien-/Dateimanager – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Medien-/Dateimanager von MyPresta.eu."
sidebar:
  label: "Medien-/Dateimanager – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Media / Files Manager auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/media-files-manager.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/media-files-manager/)
>
> ---


# Medien-/Dateimanager

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Das Modul benötigt Schreibrechte für die von ihm verwalteten Verzeichnisse, was für PrestaShop-Installationen Standard ist.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation werden Sie zur Konfigurationsseite des Moduls weitergeleitet. Diese Seite dient hauptsächlich dazu, den Dateimanager in Ihr PrestaShop-Backoffice zu integrieren und seine Kerneinstellungen zu verwalten.

Der Hauptkonfigurationsbildschirm zeigt die Dateimanager-Oberfläche direkt an. Diese Oberfläche ist ein voll ausgestatteter Dateibrowser, ähnlich dem, den Sie auf Ihrem Computer sehen würden, aber er arbeitet mit Ihren Serverdateien.

**Schlüsselbereiche & Funktionalität innerhalb der Dateimanager-Oberfläche:**

1.  **Navigationspanel (Linke Seitenleiste):**

    - **Was dies tut:** Zeigt eine baumartige Struktur der Verzeichnisse Ihres Servers, typischerweise beginnend mit Ihrem PrestaShop-Stammordner. Sie können auf Ordner klicken, um durch sie zu navigieren.
    - **Auswirkung der Verwendung:** Ermöglicht Ihnen, schnell zwischen verschiedenen Teilen Ihrer PrestaShop-Installation zu wechseln (z.B. `img/p` für Produktbilder, `themes/yourtheme/css` für Stylesheets).
    - **Empfohlener Wert:** Verwenden Sie dies, um zu dem spezifischen Ordner zu navigieren, in dem Sie Dateien verwalten möchten.
2.  **Dateilistenbereich (Hauptpanel):**

    - **Was dies tut:** Zeigt den Inhalt (Dateien und Unterordner) des aktuell ausgewählten Ordners an. Sie sehen Dateinamen, Größen, Typen und Änderungsdaten.
    - **Auswirkung der Verwendung:** Hier führen Sie die meisten Ihrer Dateioperationen durch.
    - **Empfohlener Wert:** Machen Sie sich mit den Symbolen und Informationen vertraut, die für jede Datei angezeigt werden.
3.  **Symbolleiste (Oben im Dateilistenbereich):**

    - **Was dies tut:** Enthält verschiedene Schaltflächen und Tools für Dateioperationen. Gängige Tools sind:
      - **Hochladen:** Dateien von Ihrem Computer in den aktuellen Serverordner hochladen.
      - **Neuer Ordner:** Ein neues Verzeichnis erstellen.
      - **Neue Datei:** Eine neue leere Datei erstellen (z.B. eine `.txt`, `.html` oder `.css` Datei).
      - **Kopieren, Ausschneiden, Einfügen:** Standard-Dateimanipulation.
      - **Umbenennen:** Den Namen einer Datei oder eines Ordners ändern.
      - **Löschen:** Dateien oder Ordner entfernen (mit äußerster Vorsicht verwenden!).
      - **Bearbeiten:** Einen Texteditor für ausgewählte Textdateien öffnen (z.B. `.php`, `.css`, `.js`, `.html`).
      - **Vorschau:** Bilder oder andere unterstützte Dateitypen direkt anzeigen.
      - **Suchen:** Dateien im aktuellen Verzeichnis oder rekursiv finden.
      - **Ansichtsoptionen:** Ändern, wie Dateien angezeigt werden (Liste, Symbole, etc.).
    - **Auswirkung der Verwendung dieser Tools:** Manipuliert direkt Dateien und Ordner auf Ihrem Server.
    - **Empfohlener Wert:** Überprüfen Sie Ihre Auswahl immer zweimal, bevor Sie Aktionen wie „Löschen“ oder „Umbenennen“ ausführen.
4.  **Kontextmenü (Rechtsklick):**

    - **Was dies tut:** Ein Rechtsklick auf eine Datei oder einen Ordner öffnet oft ein kontextsensitives Menü mit schnellem Zugriff auf gängige Operationen wie „Öffnen“, „Bearbeiten“, „Umbenennen“, „Löschen“, „Herunterladen“, „Informationen abrufen“ usw.
    - **Auswirkung der Verwendung:** Bietet eine schnellere Möglichkeit, Aktionen an einzelnen Elementen auszuführen.
    - **Empfohlener Wert:** Erkunden Sie die Rechtsklick-Optionen für verschiedene Dateitypen.

**Spezifische Einstellungen (falls vorhanden, basierend auf `mypresta_updates`, `update_`, `updatev_`):**

Die `getContent()`-Methode des Moduls rendert hauptsächlich die Dateimanager-Oberfläche selbst. Die Konfigurationsschlüssel `mypresta_updates`, `update_` und `updatev_` sind interne Standardschlüssel, die von MyPresta.eu-Modulen verwendet werden, um Update-Benachrichtigungen und Versionsprüfungen zu verwalten. Dies sind keine Einstellungen, mit denen Sie als Händler normalerweise direkt interagieren.

- **Was diese Einstellungen tun:** Dies sind interne Flags, die dem Modul helfen, mit dem MyPresta.eu-Update-Server zu kommunizieren, um nach neuen Versionen zu suchen und Benachrichtigungen in Ihrem PrestaShop-Backoffice anzuzeigen, falls ein Update verfügbar ist.
- **Auswirkung der Änderung dieser Einstellungen:** Sie können diese nicht direkt ändern. Sie werden automatisch vom Modul verwaltet. Wenn sie manuell geändert würden (was nicht empfohlen wird), könnte dies die Fähigkeit des Moduls beeinträchtigen, Sie über neue Versionen zu informieren.
- **Empfohlener Wert:** Belassen Sie sie, wie sie sind. Sie dienen der internen Modulverwaltung.
- **Händlerszenario / Beispiel:** Sie müssen sich darüber keine Gedanken machen. Das Modul informiert Sie automatisch, wenn eine neue Version veröffentlicht wird, und fordert Sie auf, diese von Ihrem MyPresta.eu-Konto herunterzuladen und zu installieren.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Dieses Modul führt keine zusätzlichen dedizierten Admin-Bildschirme oder benutzerdefinierten Controller über seine Hauptkonfigurationsseite hinaus ein. Die gesamte Dateiverwaltungsfunktionalität ist direkt in die Konfigurationsoberfläche des Moduls eingebettet.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht         | Einstellung / Option                               | Standard / Empfohlen | Zweck & Auswirkung
