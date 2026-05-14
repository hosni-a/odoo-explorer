# 🟣 Odoo 19 Explorer

> Two interactive, bilingual (EN/FR) web tools to explore Odoo 19 standard modules — one for developers, one for clients. No installation, no build step, open in any browser.

---

## 🔗 Live Links

| Tool | URL |
|---|---|
| 🧑‍💻 **Developer Explorer** | [https://hosni-a.github.io/odoo-explorer/](https://hosni-a.github.io/odoo-explorer/) |
| 🤝 **Client Presentation** | [https://hosni-a.github.io/odoo-explorer/odoo19_client.html](https://hosni-a.github.io/odoo-explorer/odoo19_client.html) |
| 📦 **GitHub Repository** | [https://github.com/hosni-a/odoo-explorer](https://github.com/hosni-a/odoo-explorer) |

---

## 📁 Repository Structure

```
odoo-explorer/
├── index.html             ← Developer Explorer (models, fields, workflows, quiz)
├── odoo19_client.html     ← Client Presentation (benefits, processes, tips)
└── README.md              ← This file
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

| Module | Category |
|---|---|
| Sales | Commercial |
| CRM | Commercial |
| Accounting | Finance |
| Inventory & Stock | Logistics |
| Purchase | Logistics |
| Human Resources | HR |
| Time Off & Absences | HR |
| Payroll | HR |
| Projects | Projects |
| Website & E-commerce | Web |
| Manufacturing | Manufacturing |
| Discuss & Messaging | Collaboration |

---

## 🌐 Bilingual Support

Both tools support **English and French** with a toggle button in the navigation bar. Switching language updates every piece of content instantly — no page reload required.

**What gets translated in the Developer Explorer:**
- Navigation, hero section, stat labels, search placeholder
- Category filter names
- Module names, descriptions, model names, field descriptions
- Workflow titles, state names, step titles and descriptions
- Certification tips
- All 27+ quiz questions, answer options, and explanations
- UI buttons and result feedback messages

**What gets translated in the Client Presentation:**
- Navigation, hero section
- Module names, category labels, descriptions
- All benefit titles and descriptions
- Process state names and step descriptions
- Tips content
- All UI labels and buttons

---

## 🚀 How to Use

### Online (recommended)
Just open the live links above — no installation needed.

### Locally
```bash
git clone https://github.com/hosni-a/odoo-explorer.git
cd odoo-explorer
# open either file directly in your browser
open index.html             # Developer version
open odoo19_client.html     # Client version
```

> No server, no npm, no build step. Both files are fully self-contained.

---

## 🛠️ How to Contribute

Both files use plain JavaScript with all data embedded as objects. Adding content is straightforward.

### Add a module to the Developer Explorer

Find the `MODS` array in `index.html` and add a new object following this structure:

```js
{
  id: 'my_module',
  icon: '🔧',
  cat: 'technical',          // sales | finance | inventory | hr | project | website | manufacture | technical
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
      steps: [
        { n: '01', t: 'Step title', d: 'Step description.' }
      ]
    },
    tips: ['⚡ Tip 1', '⚡ Tip 2']
  },
  fr: { /* same structure in French */ }
}
```

### Add a module to the Client Presentation

Find the `MODS` array in `odoo19_client.html` and add a new object:

```js
{
  id: 'my_module',
  icon: '🔧',
  cat: 'tech',               // sales | finance | invt | hr | proj | web | mfg | tech
  cc: '#6b5a3a',             // color hex for the module accent
  fr: {
    name: 'Mon Module',
    catLabel: 'Technique',
    desc: 'Description métier en langage clair...',
    benefits: [
      { ico: '✅', t: 'Titre bénéfice', d: 'Description du bénéfice pour le client.' }
    ],
    states: ['Étape 1', '→', 'Étape 2', '→', 'Terminé'],
    st: ['start', '', '', '', 'end'],
    steps: [
      { n: '1', t: 'Titre étape', d: 'Description de l\'étape.' }
    ],
    tips: ['Conseil pratique 1', 'Conseil pratique 2']
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
    a: 1,                    // index of correct answer (0-based)
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

---

## 📐 Technical Notes

| Property | Value |
|---|---|
| Framework | None — vanilla HTML, CSS, JavaScript |
| External dependencies | Google Fonts only (can be removed for full offline use) |
| Browser support | Chrome 90+, Firefox 90+, Safari 15+, Edge 90+ |
| File sizes | `index.html` ~110 KB · `odoo19_client.html` ~95 KB |
| Odoo version | 19.0 |
| Data source | Odoo 19 official source code and documentation |

To make the tool fully offline, remove the `<link>` tag pointing to Google Fonts and replace font families with `system-ui, sans-serif`.

---

## 📄 License

Free to use and share within the Odoo community. Content is based on publicly available Odoo 19 documentation and source code.

Odoo is a trademark of [Odoo S.A.](https://www.odoo.com)
