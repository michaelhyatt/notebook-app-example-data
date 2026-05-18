# notebook-app-example-data

Public datasets for [Cribl notebook-app](https://github.com/cribl/notebook-app) bundled examples.  
Fetched by **Cribl Search** (`externaldata` / HTTP dataset providers), not via the app pack proxy.

## Base URL (raw GitHub)

```
https://raw.githubusercontent.com/michaelhyatt/notebook-app-example-data/main
```

## Files

| Path | Used by | Notes |
|------|---------|--------|
| `anomaly-detection/daily-min-temperatures.csv` | `Anomaly_Detection_PyOD.ipynb` | From [jbrownlee/Datasets](https://github.com/jbrownlee/Datasets) (attribution in notebook) |
| `malware-hunt/malwarebazaar_ti_lookup.csv` | `Malware_Hash_Threat_Hunt.ipynb` | Teaching TI (md5, signature, families); ≥60% join overlap with `pe_imports_hunt.csv` |
| `malware-hunt/pe_imports_hunt.csv` | `Malware_Hash_Threat_Hunt.ipynb` | Teaching PE import flags keyed by MD5 |
| `malware-hunt/malwarebazaar_recent_sample.csv` | Optional | Subset of [MalwareBazaar `recent`](https://bazaar.abuse.ch/export/csv/recent/) export **without** `#` comment lines (Search-friendly) |

## Regenerating malware-hunt samples

From the notebook-app repo:

```bash
node scripts/build-malware-hunt-samples.mjs
# copies outputs into this repo when EXAMPLE_DATA_REPO=/path/to/this/repo
```

Or sync manually from `notebook-app/public/data/malware-hunt/`.

## License

Example teaching CSVs in `malware-hunt/` are synthetic/curated for demos.  
`daily-min-temperatures.csv` follows the upstream jbrownlee dataset terms.  
`malwarebazaar_recent_sample.csv` is derived from MalwareBazaar public export (see their [ToS](https://bazaar.abuse.ch/faq/#tos)).
