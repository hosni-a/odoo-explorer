# Odoo 19 — Module Explorer & Certification Prep

> An interactive, bilingual (EN/FR) learning tool for developers preparing for the **Odoo 19 Functional or Technical Certification**. Explore core modules, drill into models and fields, visualize workflows, and test your knowledge with a built-in quiz engine.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [How to Use](#how-to-use)
- [Modules Covered](#modules-covered)
- [Data Structure](#data-structure)
- [Language Support](#language-support)
- [Quiz Engine](#quiz-engine)
- [File Structure](#file-structure)
- [Customization](#customization)
- [Technical Notes](#technical-notes)

---

## Overview

`odoo19_learning.html` is a **single self-contained HTML file** — no server, no npm, no build step required. Open it in any modern browser and it works offline. It was built for junior and senior Odoo developers who want a fast, structured way to:

- Navigate the standard Odoo 19 module catalog
- Understand the key models, fields, and relationships inside each module
- Visualize state machine workflows (order lifecycle, invoice lifecycle, etc.)
- Review certification tips and common exam gotchas
- Quiz themselves before sitting the Odoo certification exam

---

## Features

| Feature | Details |
|---|---|
| 🌐 Bilingual UI | Full English / French toggle — switches every label, description, field, tip, and quiz question instantly |
| 📚 Learn Mode | Browse 13 core modules with descriptions, models, fields, and workflows |
| 🧩 Model Explorer | Click any module → expand any model → see all fields with type, required flag, and description |
| 🔄 Workflow Viewer | State machine diagram + numbered step-by-step lifecycle for each module |
| 💡 Cert Tips | Curated exam tips per module — common gotchas and tricky distinctions |
| 🧠 Quiz Mode | 27+ bilingual questions, configurable count (5 / 10 / 20 / All), per-module or mixed |
| 🔍 Search & Filter | Real-time search + category filter (Sales, Finance, Inventory, HR, Project, etc.) |
| 📱 Responsive | Works on desktop and tablet screens |
| ⚡ Zero dependencies | No framework, no CDN required (except Google Fonts for typography) |

---

## How to Use

### 1. Open the file

```bash
# Simply open in your browser — no server needed
open odoo19_learning.html
# or double-click the file in your file manager
```

### 2. Learn Mode

1. Browse the module grid — use the **search bar** or **category filters** to narrow down
2. Click any module card to open its detail view
3. Switch between three tabs:
   - **Models** — click a model row to expand its field table
   - **Workflow** — state diagram and lifecycle steps
   - **Cert Tips** — exam-focused notes

### 3. Quiz Mode

1. Click **Quiz** in the top navigation bar
2. Select a module focus (or keep "All modules")
3. Choose the number of questions: 5 / 10 / 20 / All
4. Answer each question — immediate feedback with explanation
5. View your score and result rating at the end

### 4. Switch Language

Click the **EN / FR** toggle in the top-right corner of the navigation bar. The entire interface — including all module data, field descriptions, workflow steps, tips, and quiz questions — switches instantly.

---

## Modules Covered

| Module | Technical Name | Category |
|---|---|---|
| Sales | `sale` | Sales & CRM |
| CRM | `crm` | Sales & CRM |
| Accounting | `account` | Finance |
| Inventory / Stock | `stock` | Inventory |
| Purchase | `purchase` | Inventory |
| Employees (HR) | `hr` | HR |
| Time Off | `hr_holidays` | HR |
| Payroll | `hr_payroll` | HR |
| Manufacturing | `mrp` | Manufacturing |
| Project | `project` | Project |
| Website / eCommerce | `website` | Website |
| Base | `base` | Technical |
| Discuss / Mail | `mail` | Technical |

Each module includes:
- Module description and purpose
- 2–4 key models with full field tables
- Workflow state machine (states + lifecycle steps)
- 3–5 certification exam tips

---

## Data Structure

All data is embedded as plain JavaScript objects inside the HTML file. Each module entry follows this shape:

```js
{
  id: 'sale',          // unique identifier
  icon: '🛒',          // emoji displayed on card
  cat: 'sales',        // category for filtering

  en: {                // English content
    name: 'Sales',
    tn: 'sale',        // technical name (module name in Odoo)
    desc: '...',       // module description

    models: [
      {
        name: 'Sale Order',
        tech: 'sale.order',
        desc: '...',
        fields: [
          { n: 'name', t: 'char', r: 1, d: 'Order reference' },
          //   n = field name
          //   t = field type (char, int, float, bool, date, many2one, one2many, many2many, select, text, binary)
          //   r = required (1 = required, 0 = optional)
          //   d = description
        ]
      }
    ],

    wf: {              // workflow
      title: 'Sales Order Lifecycle',
      states: ['Draft', '→', 'Sent', '→', 'Done'],
      st: ['start', '', '', '', 'end'],   // state CSS class
      steps: [
        { n: '01', t: 'Create Quotation', d: 'Description...' }
      ]
    },

    tips: [
      '⚡ Tip text here...'
    ]
  },

  fr: { /* same structure in French */ }
}
```

Quiz questions follow this structure:

```js
{
  mod: 'sale',         // module id this question belongs to
  en: {
    cat: 'Sales',      // category label shown in quiz
    q: 'Question text?',
    opts: ['Option A', 'Option B', 'Option C', 'Option D'],
    a: 1,              // index of correct answer (0-based)
    expl: 'Explanation with <strong>HTML</strong> allowed.'
  },
  fr: { /* same in French */ }
}
```

---

## Language Support

The tool supports **English** and **French** simultaneously. Switching language updates:

- Navigation labels
- Hero section (title, subtitle, stat labels)
- Search placeholder
- Category filter buttons
- Module card names and descriptions
- Model names, descriptions, and field descriptions (d property)
- Field labels (Field Name / Nom du champ, Required / Obligatoire, etc.)
- Workflow titles, state names, and step titles/descriptions
- Certification tips
- Quiz questions, answer options, and explanations
- Quiz UI labels (Start, Skip, Next, Try Again, result messages)
- Score result feedback (4 levels based on percentage)

To add a new language, duplicate the `en` block inside `T` (the translations object) and the `en` block inside each module/question object.

---

## Quiz Engine

### Question pool

Currently contains **27 questions** covering all 13 modules. Questions are shuffled before each quiz session.

### Scoring levels

| Score | Rating |
|---|---|
| ≥ 90% | 🏆 Outstanding — Ready for certification |
| ≥ 75% | 🎉 Great job — Almost exam-ready |
| ≥ 60% | 💪 Good progress — Focus on weak modules |
| < 60% | 😟 Keep studying — Review the modules |

### Adding questions

Add a new object to the `QS` array in the `<script>` section:

```js
{
  mod: 'account',     // must match a module id
  en: {
    cat: 'Accounting',
    q: 'Your question here?',
    opts: ['A', 'B', 'C', 'D'],
    a: 2,             // correct answer index
    expl: 'Explanation with <strong>key term</strong> highlighted.'
  },
  fr: {
    cat: 'Comptabilité',
    q: 'Votre question ici ?',
    opts: ['A', 'B', 'C', 'D'],
    a: 2,
    expl: 'Explication avec <strong>terme clé</strong> mis en évidence.'
  }
}
```

---

## File Structure

```
odoo19_learning.html     ← entire application (single file)
README.md                ← this file
```

The HTML file is organized internally as:

```
<head>
  CSS styles (all inline, ~350 lines)

<body>
  <nav>              Navigation bar with lang switch
  <div#learn-view>   Module grid + detail view
  <div#quiz-view>    Quiz setup + active quiz + results

<script>
  T = {}             Translation strings (EN + FR)
  MODS = []          Module data (bilingual)
  QS = []            Quiz questions (bilingual)
  // UI functions: setLang, showView, renderGrid, openMod,
  //               showSec, renderModels, renderWF, renderTips,
  //               startQuiz, renderQ, pick, showResults, resetQuiz
```

---

## Customization

### Add a new module

1. Add a new object to the `MODS` array following the data structure above
2. Assign it a `cat` value from: `sales`, `finance`, `inventory`, `hr`, `project`, `website`, `manufacture`, `technical`
3. Add corresponding quiz questions to `QS`

### Add a new category

1. Add the category key and color to `catColors`:
   ```js
   const catColors = { ..., mycat: '#ff0099' };
   ```
2. Add the CSS class:
   ```css
   .cat-mycat { --cc: #ff0099; }
   ```
3. Add the button label to both `T.en.cats` and `T.fr.cats` arrays
4. Add a button in the `buildCats()` function

### Change the color theme

Edit the CSS variables in `:root`:

```css
:root {
  --bg: #0a0c10;        /* page background */
  --surface: #111318;   /* card background */
  --accent: #7c5cfc;    /* primary purple */
  --accent2: #00d4ff;   /* cyan highlight */
  --green: #22c55e;     /* correct answer / start state */
  --red: #ef4444;       /* wrong answer / cancel state */
}
```

---

## Technical Notes

- **No build step** — plain HTML, CSS, and vanilla JavaScript
- **No external dependencies** — Google Fonts is the only external request (can be removed for full offline use by deleting the `<link>` tag and replacing fonts with `system-ui`)
- **Browser support** — Chrome 90+, Firefox 90+, Safari 15+, Edge 90+
- **File size** — ~95 KB (all data + styles + logic)
- **Odoo version** — Data reflects **Odoo 19.0** standard `addons/` folder structure
- **Data accuracy** — Field names and types are sourced from the official Odoo 19 source code and documentation. Always cross-reference with the live source at [github.com/odoo/odoo/tree/19.0/addons](https://github.com/odoo/odoo/tree/19.0/addons)

---

## Contributing

To extend this tool:

1. Open `odoo19_learning.html` in a text editor
2. Locate the `MODS` array for module data or `QS` array for questions
3. Follow the existing data structure
4. Test in a browser before sharing

---

## License

This tool is provided as a free learning resource for the Odoo developer community. Content is based on publicly available Odoo 19 documentation and source code.

Odoo is a trademark of [Odoo S.A.](https://www.odoo.com)