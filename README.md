# Vilikon adapter catalog

The list of ready-made adapters the IT Specialist in a Vilikon cockpit can take over (`adapter_catalog`,
`adapter_install`). Standard `vilikon.adapter-catalog/1`:

| Field | Meaning |
|---|---|
| `slug` | short name, `^[a-z][a-z0-9-]{1,40}$`; the adapter's `ADAPTER.json` carries the same |
| `name`, `description` | a string or `{"de": …, "en": …}` |
| `keywords` | search words, both languages |
| `repo` | `owner/name` on GitHub; only repositories of this catalog's own account are taken |
| `commit` | the full 40-character commit that was reviewed; exactly this one is copied |
| `version` | shown to the owner |

An instance uses the catalog when its `ADAPTER_CATALOG_URL` points at the raw address of `catalog.json`:

```
https://raw.githubusercontent.com/integrenns-ae/vilikon-adapters/main/catalog.json
```

Installing copies the pinned commit into a repository of the customer's own. The customer owns that copy and runs it
with his own credentials; the vendor never sits between him and the outside system.

## Adding an adapter

1. The adapter repository has an `ADAPTER.json` (`vilikon.adapter/1`: build, start, check path, credentials with
   label and help in both languages, files for English instances) and passes its own tests.
2. Add an entry here with the reviewed commit. A new version of an adapter is a new commit here, nothing else.
