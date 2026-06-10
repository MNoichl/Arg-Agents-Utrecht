# Arg-Agents-Utrecht

Slides for **"Agentic LLMs for Argument Mining in Philosophical Texts"** (Max
Noichl & Jan Broersen), HAI-Workshop *Symbolic and Neuro-Symbolic AI: Reasoning
and Learning*, Utrecht, 2026.

The deck is `index.qmd`, rendered with Quarto Reveal.js; the rendered site is
committed (`index.html` + `index_files/`) for hosting. Large local data files
and the unpublished paper draft are excluded via `.gitignore`.

---

# Scholarly Folio Quarto Template

This folder is a Quarto Reveal.js template with a clean academic visual system:
ivory paper, thin warm beige rules, restrained black typography, high-contrast
serif headings, and small-caps sans labels.

The old slide mechanics remain in place. Write semantic Markdown first, then add
the existing `layout="..."` attributes and `data-*` hooks when a slide needs a
specific behavior.

## Render

```bash
quarto render index.qmd
```

Preview over HTTP, especially for iframe and shader slides:

```bash
quarto preview index.qmd
```

## Slide Layouts

Use layout attributes on slide headings:

```markdown
# Talk title {layout="title" data-gp-kicker="MONOLINE FOLIO" data-gp-code="The Case for Clarity"}

# Agenda {layout="outline"}

# Key Points {layout="bullets"}

# A Study in Structure {layout="half" data-gp-fragments="off"}

# Framed Exhibit {layout="exhibit" data-gp-caption="Fig. 1 - Caption text."}

# Literature {layout="references"}
```

Supported layout values are `title`, `outline`, `divider`, `claim`, `bullets`,
`reading`, `quote`, `exhibit`, `half`, `filters`, `table`, and `references`.

## Interaction Hooks

Modal anchors still work:

```markdown
[Open](#){.opens-modal data-modal-type="image" data-modal-url="images/example.png"}
```

Common modal types are `image`, `iframe`, `video`, and `html`.

Use `aside` blocks for the stable footer citation band:

```markdown
::: aside
[@tufte2006; @bringhurst2012]
:::
```

For changing images next to bullet points, keep `layout="half"
data-gp-fragments="off"` and pair manual `fragment` list items with a
`.gp-fragment-stack` of framed figures, as shown in `index.qmd`.

## Source Files

- `_quarto.yml` wires Quarto and Reveal.
- `index.qmd` is the editable template deck.
- `gp-quarto.js` maps Quarto output to template classes and behaviors.
- `gp-template/js/grid-protocol.js` handles folios, running labels, and column automation.
- `gp-template/css/grid-protocol.css` defines the scholarly visual system.
- `gp-quarto.css` contains Quarto-specific parity and modal overrides.

Generated files such as `index.html`, `index_files/`, and `.quarto/` are not the
source of truth.
