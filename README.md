# 🟣 Odoo 19 Explorer

> Three interactive, bilingual (EN/FR) web tools to explore, present, and build Odoo 19 module presentations — for developers, for clients, and for consultants who want to generate custom presentations without writing a line of code.

---

## 🔗 Live Links

| Tool | URL |
|---|---|
| 🧑‍💻 **Developer Explorer** | [https://hosni-a.github.io/odoo-explorer/](https://hosni-a.github.io/odoo-explorer/) |
| 🤝 **Client Presentation** | [https://hosni-a.github.io/odoo-explorer/odoo19_client.html](https://hosni-a.github.io/odoo-explorer/odoo19_client.html) |
| ⚡ **Module Builder** | [https://hosni-a.github.io/odoo-explorer/odoo_module_builder.html](https://hosni-a.github.io/odoo-explorer/odoo_module_builder.html) |
| 📦 **GitHub Repository** | [https://github.com/hosni-a/odoo-explorer](https://github.com/hosni-a/odoo-explorer) |

---

## 📁 Repository Structure

```
odoo-explorer/
├── index.html                  ← Developer Explorer (models, fields, workflows, quiz)
├── odoo19_client.html          ← Client Presentation (benefits, processes, tips)
├── odoo_module_builder.html    ← Module Builder (generate custom presentations)
└── README.md                   ← This file
```

---

## 🧑‍💻 File 1 — Developer Explorer (`index.html`)

Built for **junior and senior Odoo developers** who want a structured reference on the standard Odoo 19 module catalog.

### Features

| Feature | Details |
|---|---|
| 📚 **Learn Mode** | Browse 13 core modules with full technical descriptions |
| 🧩 **Model Explorer** | Expand any model to see all fields with type, required flag, and description |
| 🔄 **Workflow Viewer** | State machine diagram + numbered lifecycle steps per module |
| 💡 **Cert Tips** | Curated tips per module — tricky distinctions and common gotchas |
| 🧠 **Quiz Mode** | 27+ bilingual questions, configurable count (5/10/20/All), per-module or mixed |
| 🔍 **Search & Filter** | Real-time search + 8 category filters |
| 🌐 **Bilingual** | Full EN / FR toggle — every label, field, tip, and quiz question |

### Modules Covered

| Module | Technical Name | Category |
|---|---|---|
| Sales | `sale` | Sales & CRM |
| CRM | `crm` | Sales & CRM |
| Accounting | `account` | Finance |
| Inventory | `stock` | Inventory |
| Purchase | `purchase` | Inventory |
| Employees | `hr` | HR |
| Time Off | `hr_holidays` | HR |
| Payroll | `hr_payroll` | HR |
| Manufacturing | `mrp` | Manufacturing |
| Project | `project` | Project |
| Website | `website` | Website |
| Base | `base` | Technical |
| Discuss / Mail | `mail` | Technical |

---

## 🤝 File 2 — Client Presentation (`odoo19_client.html`)

Built for **client-facing presentations and demos**. Zero technical jargon — no model names, no field tables, no code. Just clear business value.

### Features

| Feature | Details |
|---|---|
| 🗂️ **Module Cards** | Clean visual grid with business-oriented descriptions |
| ✅ **Benefits** | 4 concrete benefits per module explained in plain language |
| 🔄 **Process View** | Step-by-step workflow explained as a business process |
| 💡 **Good to Know** | Practical tips for getting the most out of each module |
| 🌐 **Bilingual** | Full EN / FR toggle — default language is French |
| 🖥️ **Slide panel** | Detail view opens in a smooth side panel, no page reload |

### Modules Covered

| Module | Nom FR | Category |
|---|---|---|
| Sales | Ventes | Commercial |
| CRM | CRM | Commercial |
| Accounting | Comptabilité | Finance |
| Inventory & Stock | Inventaire & Stock | Logistique |
| Purchase | Achats | Logistique |
| Human Resources | Ressources Humaines | RH |
| Time Off & Absences | Congés & Absences | RH |
| Projects | Projets | Projets |
| Website & E-commerce | Site Web & E-commerce | Web |
| Manufacturing | Fabrication | Fabrication |
| Payroll | Paie | RH |
| Discuss & Messaging | Discussion & Messagerie | Collaboration |

---

## ⚡ File 3 — Module Builder (`odoo_module_builder.html`)

A **visual editor in French** that lets you build fully customized client presentations without writing any code. Fill in the details, click Generate — download a ready-to-use HTML file.

### How it works

1. **Project tab** — Set the page title, H1 headline, subtitle, upload company and client logos (stored as base64), and choose an accent color.
2. **Add Module tab** — Fill in each module: icon, category, name, description, features (benefits), process steps, and tips. Click **Enregistrer le module**.
3. **Live preview** — Every saved module appears as a card on the right side. Edit or delete any module at any time.
4. **Generate** — Click **⚡ Générer HTML** → review the summary → **⬇ Télécharger HTML** to download the generated file.

### Features

| Feature | Details |
|---|---|
| 📋 **12 default modules** | Pre-loaded with all 12 modules from `odoo19_client.html` (French content) |
| ✏️ **Edit / Delete** | Edit any module and update it in place — never creates a duplicate |
| ↺ **Reset defaults** | One click restores all 12 original modules |
| 🖼️ **Logo upload** | Company and client logos embedded as base64 in the generated file — no external links |
| 🎨 **Accent color** | Custom hex color applied throughout the generated presentation |
| 👁️ **Live preview** | Real-time card preview with feature / step / tip counters |
| 🃏 **Hero card stack** | Generated file shows the first 3 modules as a stacked visual in the hero section |
| 🇫🇷 **Interface in French** | Entire builder UI is in French |
| 📄 **Self-contained output** | Generated file is a single HTML file — works offline, no dependencies |

### Generated output

The downloaded HTML file is a complete client presentation styled identically to `odoo19_client.html`, with:

- Your custom title, headline, description, and logos
- Your accent color applied throughout
- All your modules with features, process steps, and tips
- A filterable module grid with search and category filters
- A smooth slide-over detail panel per module
- 3-module card stack in the hero section
- Fully in French

---

## 🌐 Bilingual Support (index.html & odoo19_client.html)

Both the Developer Explorer and Client Presentation support **English and French** simultaneously. Switching language updates every piece of content instantly — no page reload.

**What gets translated in the Developer Explorer:** navigation, hero section, stat labels, category filters, module names, model names, field descriptions, workflow states and steps, certification tips, all 27+ quiz questions and explanations, UI buttons, result feedback.

**What gets translated in the Client Presentation:** navigation, hero, module names, category labels, descriptions, benefit titles and descriptions, process states and steps, tips, all UI labels.

---

## 🚀 How to Use

### Online
Just open the live links above — no installation needed.

### Locally
```bash
git clone https://github.com/hosni-a/odoo-explorer.git
cd odoo-explorer

# Open in browser
open index.html                 # Developer Explorer
open odoo19_client.html         # Client Presentation
open odoo_module_builder.html   # Module Builder
```

> No server, no npm, no build step. All three files are fully self-contained.

---

## 🛠️ How to Contribute

### Add a module to the Developer Explorer

Find the `MODS` array in `index.html`:

```js
{
  id: 'my_module',
  icon: '🔧',
  cat: 'technical',   // sales | finance | inventory | hr | project | website | manufacture | technical
  en: {
    name: 'My Module',
    tn: 'my_module',
    desc: 'What this module does...',
    models: [
      {
        name: 'My Model',
        tech: 'my.model',
        desc: 'Short description',
        fields: [
          { n: 'name', t: 'char', r: 1, d: 'Record name' },
          // t: char | int | float | bool | date | many2one | one2many | many2many | select | text | binary
          // r: 1 = required, 0 = optional
        ]
      }
    ],
    wf: {
      title: 'My Module Lifecycle',
      states: ['Draft', '→', 'Confirmed', '→', 'Done'],
      st: ['start', '', '', '', 'end'],
      steps: [{ n: '01', t: 'Step title', d: 'Step description.' }]
    },
    tips: ['⚡ Tip 1', '⚡ Tip 2']
  },
  fr: { /* same structure in French */ }
}
```

### Add a module to the Client Presentation

Find the `MODS` array in `odoo19_client.html`:

```js
{
  id: 'my_module',
  icon: '🔧',
  cat: 'tech',        // sales | finance | invt | hr | proj | web | mfg | tech
  cc: '#6b5a3a',      // accent color hex
  fr: {
    name: 'Mon Module',
    catLabel: 'Technique',
    desc: 'Description métier en langage clair...',
    benefits: [
      { ico: '✅', t: 'Titre bénéfice', d: 'Description du bénéfice.' }
    ],
    states: ['Étape 1', '→', 'Étape 2', '→', 'Terminé'],
    st: ['start', '', '', '', 'end'],
    steps: [{ n: '1', t: 'Titre étape', d: 'Description.' }],
    tips: ['Conseil pratique 1']
  },
  en: { /* same structure in English */ }
}
```

### Add quiz questions (Developer Explorer only)

Find the `QS` array in `index.html`:

```js
{
  mod: 'my_module',
  en: {
    cat: 'My Category',
    q: 'Your question here?',
    opts: ['Option A', 'Option B', 'Option C', 'Option D'],
    a: 1,             // index of correct answer (0-based)
    expl: 'Explanation with <strong>key term</strong> highlighted.'
  },
  fr: {
    cat: 'Ma Catégorie',
    q: 'Votre question ici ?',
    opts: ['Option A', 'Option B', 'Option C', 'Option D'],
    a: 1,
    expl: 'Explication avec <strong>terme clé</strong> mis en évidence.'
  }
}
```

### Update the Module Builder defaults

The 12 default modules in `odoo_module_builder.html` are stored in the `DEFAULT_MODULES` constant near the top of the `<script>` section. Each module follows this structure:

```js
{
  id: 'sale',
  icon: '🛒',
  cat: 'sales',         // sales | finance | logistics | hr | project | web | mfg | collab
  cc: '#1e3a5f',        // card accent color
  name: 'Ventes',
  desc: 'Description...',
  benefits: [{ ico: '💼', t: 'Titre', d: 'Description.' }],
  steps:    [{ n: '1',   t: 'Titre étape', d: 'Description.' }],
  tips:     ['Conseil pratique...']
}
```

> **Note:** JS property names (`benefits`, `steps`, `tips`) must stay in English even though the content is in French — they are object keys used by the JS code, not display strings.

---

## 📐 Technical Notes

| Property | Value |
|---|---|
| Framework | None — vanilla HTML, CSS, JavaScript |
| External dependencies | Google Fonts only (removable for full offline use) |
| Browser support | Chrome 90+, Firefox 90+, Safari 15+, Edge 90+ |
| File sizes | `index.html` ~110 KB · `odoo19_client.html` ~95 KB · `odoo_module_builder.html` ~95 KB |
| Odoo version | 19.0 |
| Data source | Odoo 19 official source code and documentation |

To make any file fully offline, remove the `<link>` tag pointing to Google Fonts and replace font families with `system-ui, sans-serif`.

---

## 📄 License

Free to use and share within the Odoo community. Content is based on publicly available Odoo 19 documentation and source code.

Odoo is a trademark of [Odoo S.A.](https://www.odoo.com)
