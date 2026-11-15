# Covenant Ledger

A side-by-side reading overlay for the Old Testament (and eventually the full LDS canon) that makes the covenant story explicit: what was promised, what was required, what was broken, what God delivered, and what principle or pattern each passage reveals.

## What it does

- **Read mode**: plain scripture text (KJV, public domain) with color-coded verse borders for breach / delivered / mixed
- **Overlay mode**: text + covenant ledger sidebar
- **Ledger Only mode**: sidebar only, for seeing the covenant story as its own arc
- **Raw JSON mode**: the underlying data, for inspection and extension

## The note schema

Each ledger entry is one JSON object per passage range. See `schema.json` for the full field list and controlled vocabularies.

Key fields beyond the obvious:

- **divine_action / divine_character / divine_motive** — the broad aspects of God, separated from the covenant-specific *delivered* field
- **principle** — one sentence, the distilled takeaway
- **pattern_id** — points at a master pattern registry so the same sequence (e.g., breach → intercession → partial restoration) is tracked consistently across books
- **context** — the ancient Near East background, in the spirit of 'world of the Bible' resources
- **broken** — points at specific commandment verses, not free text, so you can query 'every breach of the first commandment' across the canon
- **confidence** — high / medium / low, separating explicit claims from inference

## Sample coverage

Exodus 32 is tagged as a starting sample: four notes covering the golden calf breach, Moses' intercession, the Levite judgment, and the attempted substitution.

## Roadmap

1. Extend ledger notes through the wilderness period (Numbers 13–14, Deuteronomy 28–30)
2. Add Joshua 1–6 and 24 for the land entry and covenant renewal
3. Parallel Book of Mormon entries on the same covenant threads
4. Build a manifest tracking coverage per book
5. Move from single-file HTML to a structured data + viewer pipeline

## License

Scripture text: King James Version, public domain. Ledger notes and schema: original work.
