# sanctum-corpus

Generated load artifacts for Sanctum's citation corpus — **data only**.

These files are the published form of the corpus chunk output: a `manifest.json`
index plus, per work, a `<work>.document.json` registry record and
`<work>.part-NNN.jsonl` chunk files. They are produced by the corpus pipeline in
[lyonse98/SANCTUM](https://github.com/lyonse98/SANCTUM) (`scripts/corpus/`,
via `npm run corpus:artifacts`) and consumed by Sanctum's `corpus-ingest`
Supabase edge function, which fetches them from this repo's raw URLs at load
time, embeds every chunk, and upserts them into the corpus database.

**Do not hand-edit these files.** To change the corpus, change the pipeline or
its sources in the SANCTUM repo and regenerate; then replace this repo's
contents with the fresh artifacts.

Layout note: the files live at this repo's root (not in a subdirectory) because
the loader fetches `https://raw.githubusercontent.com/lyonse98/sanctum-corpus/main/<file>`.
