# hs-bill-submissions

Single-file HTML swimlane visualisation of submissions on the Health and Safety at Work Amendment Bill.

## Editing org tile quotes

Every org tile uses a `data-quote` attribute to drive the hover tooltip, e.g.:

```html
<span class="org-tile oppose" data-quote="The carve-out creates a two-tier system.">Acme Co</span>
```

**The attribute value is delimited by double quotes (`"`), so any double quotes that appear inside the quote text will break the HTML and truncate the tooltip.**

### Rule: use single quotes for any quoted term inside a data-quote value

If the original submission uses double quotes around a term (e.g. `"critical risk"`), replace them with single quotes in the attribute:

```html
<!-- WRONG — the inner " closes the attribute early -->
data-quote="The Bill's focus on "critical risks" must not..."

<!-- RIGHT — use single quotes inside the attribute value -->
data-quote="The Bill's focus on 'critical risks' must not..."
```

HTML entities (`&ldquo;`/`&rdquo;`) also work but are harder to read and edit. Prefer single quotes.

### Tile classes

| Class | Meaning | Colour |
|-------|---------|--------|
| `oppose` | Opposed the carve-out | Red |
| `cond` | Wanted significant changes | Orange |
| `support` | Supported the carve-out | Green |
| `unclear` | Did not address this provision | Grey |
| `body` | Union or industry body (black border) | — |

### Legend counts

The legend counts (oppose/cond/support) are hardcoded in the HTML and must be updated manually when tiles are reclassified.
