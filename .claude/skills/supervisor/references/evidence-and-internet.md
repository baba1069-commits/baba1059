# Evidence and Internet Protocol

## When to browse

Use WebSearch/WebFetch before making a material claim when any of these are true:

- the fact can change over time;
- a current version, price, law, schedule, API, library, product, role-holder, benchmark, news event, standard, or policy matters;
- the domain is niche or the model is materially uncertain;
- the user asks to search, verify, cite, compare, or find latest information;
- a technical implementation depends on current documentation;
- an external benchmark/reference is required for blind comparison.

Do not browse just to pad a response or for pure rewriting/translation where no external fact is needed.

## Source hierarchy

1. User-provided source for claims about that source.
2. Primary/official source for technical, legal, product, policy, scientific, or organizational facts.
3. Reputable secondary source for context or independent reporting.
4. Community sources only when firsthand experience is itself relevant, and label accordingly.

For technical questions, prefer official docs/specifications/repositories over blogs.

## Freshness

Check page publication/update date and the date of the underlying event. When multiple sources disagree, prefer the newest authoritative evidence and explicitly resolve the conflict.

## Claim discipline

Maintain an internal claim ledger for material claims:

```yaml
claim_id: C-001
claim: ...
importance: critical | material | minor
source: ...
status: VERIFIED | INFERRED | DISPUTED | UNVERIFIED
```

A search miss is not proof of nonexistence. A failed tool call is not evidence that the claim is false.

## Internet inside judges

Research agents may use WebSearch/WebFetch independently. For high-impact current claims, do not let one research path be the only evidence if a second independent source can reasonably confirm or challenge it.

## Offline fallback

If web access is unavailable but freshness is necessary, do not fabricate certainty. Narrow, qualify, or mark the specific claim unresolved.
