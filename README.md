# Citation resolutions

The append-only lookup journal for The Citation Record.

`lookups.jsonl` holds one JSON object per citation lookup. Each record carries
the query, the outcome, the CourtListener cluster it resolved to, the UTC
timestamp of retrieval, and the provenance of the code that produced it:
resolver version, tooling commit, whether that tree was modified, and the API
version queried.

It exists so that a published verification can be checked. A claim that a
citation was verified on a date is only worth something if the record of that
lookup can be reached, and a record can only be reached if it is versioned.

`resolutions.sqlite3` is a regenerable cache and is deliberately not tracked.

Records are appended, never edited. A lookup that needs correcting is re-run
and both records are retained.

Produced by `resolve/` in https://github.com/CitationRecord/tooling
