# LLM-Speak: Vocabulary to Avoid

Language models tend to reach for the same metaphors and intensifiers in mathematical writing. A reader soon learns to skim them, and they often hide the statement being made. This list records the ones we have seen most often. Use it when drafting and when editing.

None of these words is wrong in itself. Replace one when a plainer word says the same thing, or when it stands in for a statement that should be made outright. When the suggested replacement does not fit, rewrite the sentence so that it says what happens mathematically.

| Avoid | Use instead | Fine when |
|---|---|---|
| actual (the actual) | delete | contrasting with a defined approximation |
| at the price of | at the cost of, but | |
| bridge (noun) | reduction, connection | |
| carries | has, contains | "carries over"; carrying out a calculation |
| charge, charged | count, bound by | a formal amortized argument |
| cheap | low-cost, or give the cost | |
| clean, cleanly | say what is simple | |
| collapse, collapses | reduces to, simplifies to | |
| decisive | main, or delete | |
| deliberately | delete | |
| drive, driving | used in, underlies | |
| earns its keep, earns its place | is useful because… | |
| elbow | breakpoint | |
| endpoint | extreme case, limit, final result | an endpoint of an edge, path, or interval |
| flight, in flight | in progress, pending | |
| genuine, genuinely | delete, or state the property | |
| handoff | transition | |
| harmless | does not affect… | |
| honest | delete, or state the property | |
| is what makes, is what lets | because, so | |
| kill, kills | annihilates, vanishes on | |
| land, lands | lie in, work out | |
| ledger | accounting, table | |
| literal, literally | delete | quoting a statement exactly |
| lives (on, over) | is defined over, lies on | |
| load-bearing | essential | |
| machinery | tools, results | |
| mechanism | reason, construction | a named concept such as mechanism design |
| merely, not merely | delete, or state both claims | |
| native | standard, or define it | |
| pay, pays off, payoff | accounts for, costs | |
| physical | stored, or define it | a defined contrast with "logical" |
| raw | uncorrected, or define it | |
| recipe | procedure | |
| repair | fix, correct | a named algorithm |
| route | approach, method | a path in a network |
| scoped | limited to | |
| sits | lies, is | |
| spine | main argument | |
| supplied | given | "supplied by the author" |
| supplies, supply | gives, provides | |
| survive, survives | remains, still holds | a defined event; "only this term survives" in an expansion |
| suspended | saved across the call | |
| true (the true) | delete | contrasting with an estimate |

## Exceptions

**Defined and standard terms.** Technical terminology always takes priority over this list. A word that the paper defines, or that has an established meaning in the field, stays. Examples include "honest prover," "clean space" in catalytic computing, "faithful flatness," and "witness."

**Words that are fine.** The following resemble the entries above but are acceptable:

- "audit" and "audited," which belong in verifier reports rather than in papers;
- "bookkeeping";
- "buy" and "buys";
- "unpack."

**Ordinary mathematical usage.** "Ingredient," "obstruction," "trick," and "verbatim" are common in human mathematical writing and are not on this list.

**Precise phrases.** "Exactly the" and "rather than" often make a precise claim. Keep them when they do, and cut them when they only add emphasis.

**Other habits that are not signs of LLM writing.** Em dashes, "concretely," "note that," and "tradeoff" are common in human papers. Avoiding them does not make a draft more readable.
