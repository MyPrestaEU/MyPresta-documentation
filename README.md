# MyPresta-documentation

> **Official technical documentation, configuration manuals, and merchant guides for 350+ MyPresta.eu modules for PrestaShop.**

Welcome to the official GitHub documentation mirror for **[MyPresta.eu](https://mypresta.eu)** modules, extensions, and merchant guides.

> 🌐 **Interactive Live Documentation Hub:**  
> Visit the interactive, searchable, and fully indexed documentation hub at **[https://mypresta.eu/docs/](https://mypresta.eu/docs/)**.

---

## 🌍 Language Portals / Wersje Językowe

| Language | Hub Link | Total Articles | Description |
| :--- | :--- | :---: | :--- |
| 🇬🇧 **English** | [Interactive Portal](https://mypresta.eu/docs/) | 353 | Master documentation & setup guides |
| 🇵🇱 **Polski** | [Polski Portal](https://mypresta.eu/docs/pl/) | 352 | Polska instrukcja konfiguracji i podręcznik |
| 🇩🇪 **Deutsch** | [Deutsches Portal](https://mypresta.eu/docs/de/) | 353 | Deutsche Moduldokumentation & Anleitungen |
| 🇫🇷 **Français** | [Portail Français](https://mypresta.eu/docs/fr/) | 353 | Documentation officielle en français |
| 🇪🇸 **Español** | [Portal Español](https://mypresta.eu/docs/es/) | 352 | Manuales y guías de configuración en español |
| 🇮🇹 **Italiano** | [Portale Italiano](https://mypresta.eu/docs/it/) | 353 | Documentazione e guide ufficiali in italiano |

---

## 🛠️ Architecture & Technology Stack

This documentation platform is engineered as an ultra-fast, high-performance static portal using modern Jamstack methodologies:

| Layer | Technology | Details |
| :--- | :--- | :--- |
| **Core Framework** | **[Astro](https://astro.build/)** | Next-generation web framework designed for content-focused websites with zero JavaScript overhead by default. |
| **Docs Framework** | **[Starlight](https://starlight.astro.build/)** | Official Astro documentation engine featuring built-in full-text search, i18n routing, and responsive sidebar navigation. |
| **Architecture** | **Jamstack (SSG)** | 100% pre-rendered static HTML, CSS, and minimal JS compiled for high-speed edge delivery and Nginx hosting. |
| **Content Collections** | **Astro Content Collections** | Strictly typed Markdown (`.md`) files with structured YAML frontmatter validations. |
| **Internationalization** | **Multi-locale Silos** | Native 6-language routing (`en`, `pl`, `de`, `fr`, `es`, `it`) with localized navigation trees and hreflang parity. |
| **Structured Metadata** | **JSON-LD Schemas** | Semantic technical documentation schemas (TechArticle, HowTo) and software application specifications. |
| **Build & Deploy Pipeline** | **Node.js & GitHub Actions** | Automated validation, content collections processing, asset normalization, and multi-branch synchronization. |
| **Management Studio** | **Python Flask + Tailwind** | Local visual studio (`gui.py`) providing live preview, batch AI translations, media asset indexing, and one-click deployment. |

---

## 📁 Repository & Content Structure

```text
MyPresta-documentation/
├── README.md               # Master repository & technology documentation
├── index.md                # Root English documentation hub index
├── advertising-marketing/  # Marketing, promo, banners & popups modules
├── back-office-tools/      # Admin, bulk manager, order & stock management
├── front-office/           # UX, layout, navigation & product card enhancements
├── ordering-process/       # Checkout, cart, one-step checkout & payment flows
├── payment/                # Payment gateways, fee calculators & compliance
├── seo/                    # Schema markup, sitemaps, clean URLs & indexing
├── sliders-slideshows/     # Media carousels, responsive hero banners
├── social-networks/        # Facebook, Instagram, TikTok integrations
├── de/                     # 🇩🇪 German locale silo (all categories & modules)
├── es/                     # 🇪🇸 Spanish locale silo (all categories & modules)
├── fr/                     # 🇫🇷 French locale silo (all categories & modules)
├── it/                     # 🇮🇹 Italian locale silo (all categories & modules)
└── pl/                     # 🇵🇱 Polish locale silo (all categories & modules)
```

---

## 🛒 Need Official Modules, Licenses, or Pro Support?
- **Official Store:** [https://mypresta.eu](https://mypresta.eu)
- **Customer Support & Orders:** [https://mypresta.eu/my-account/orders/](https://mypresta.eu/my-account/orders/)
- **Live Demo & Test Stores:** Available directly on each product's specification page.
