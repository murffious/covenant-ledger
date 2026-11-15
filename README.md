# Covenant Bible

A side-by-side reading overlay for the Old Testament (and eventually the full LDS canon) that makes the covenant story explicit: what was promised, what was required, what was broken, what God delivered, and what principle or pattern each passage reveals.

## What it does

- **Read mode**: plain scripture text (KJV, public domain) with color-coded verse borders for breach / delivered / mixed
- **Overlay mode**: text + covenant ledger sidebar
- **Ledger Only mode**: sidebar only, for seeing the covenant story as its own arc
- **Raw JSON mode**: the underlying data (text, ledger, patterns, key verses, manifest), for inspection and extension
- **Restoration mode** (gospel mode, gold/green button): filters the ledger to restoration-themed notes and highlights them, with a restoration thread grouped by theme line showing a KJV key verse and the New Testament fulfillment for each note
- **Theme line filter**: limit notes in any view to one pattern from the registry
- **Coverage manifest**: collapsible table under the toolbar (also in `manifest.json`)

### Restoration filtering rule

A note is restoration-themed when its `pattern_id` points at a registry entry flagged `restoration: true` (listed in `schema.json` → `restoration_patterns`): P004 Promise of Restoration after Exile, P005 New Covenant Written on the Heart, P006 Forerunner before the Lord's Coming, P007 Servant as Covenant Mediator, P009 Scattering and Gathering. To add a note to Restoration mode, give it one of these patterns; to add a new restoration theme, add a registry entry with `restoration: true`.

## The note schema

Each ledger entry is one JSON object per passage range. See `schema.json` for the full field list and controlled vocabularies.

Key fields beyond the obvious:

- **divine_action / divine_character / divine_motive** — the broad aspects of God, separated from the covenant-specific *delivered* field
- **principle** — one sentence, the distilled takeaway
- **pattern_id** — points at a master pattern registry so the same sequence (e.g., breach → intercession → partial restoration) is tracked consistently across books
- **context** — the ancient Near East background, in the spirit of 'world of the Bible' resources
- **broken** — points at specific commandment verses, not free text, so you can query 'every breach of the first commandment' across the canon
- **confidence** — high / medium / low, separating explicit claims from inference

## Coverage

See `manifest.json` (mirrored as `MANIFEST` inside `index.html`, which stays self-contained and opens from `file://`).

- **Exodus 32** (sample): golden calf breach, Moses' intercession, Levite judgment, attempted substitution
- **Restoration thread**: Isaiah 40–43 (comfort, new exodus, first Servant Song) and 11:11–13; Ezekiel 36–37 (new heart, dry bones, two sticks); Jeremiah 31 (gathering, new covenant); Malachi 3–4 (refiner, Elijah); NT fulfillment in Mark 1, Matthew 12, Luke 22
- **Divided kingdom thread**: Genesis 48–49 (Ephraim, Manasseh, Judah), 1 Kings 11–12 (split, Jeroboam's calves), Hosea 5, 2 Kings 17 (fall of Samaria, 722 BC) and 24–25 (fall of Jerusalem, 586 BC), Psalm 78, and the Lehi branch c. 600 BC (1 Nephi 1–2)

Book of Mormon and Doctrine and Covenants references are LDS scripture and are labeled as such in note context, with confidence set accordingly.

## Roadmap

1. Extend ledger notes through the wilderness period (Numbers 13–14, Deuteronomy 28–30)
2. Add Joshua 1–6 and 24 for the land entry and covenant renewal
3. Parallel Book of Mormon entries on the same covenant threads
4. ~~Build a manifest tracking coverage per book~~ (done: `manifest.json`)
5. Move from single-file HTML to a structured data + viewer pipeline

## License

Scripture text: King James Version, public domain. Ledger notes and schema: original work.
