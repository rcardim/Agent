# 🐔🕵️‍♀️ Avian Agent

## 📔Project structure:

```text
avian_agent/
├─ pyproject.toml                # or setup.cfg;
├─ requirements.txt
├─ .env                          # GOOGLE_API_KEY, GOOGLE_CX, etc. (don’t commit)
├─ src/
│  └─ avian_agent/
│     ├─ __init__.py
│     ├─ config.py               # settings, API keys, constants
│     ├─ models.py               # Pydantic schemas (Event, SeriesPoint)
│     ├─ logging.py              # unified logger
│     ├─ search/
│     │  ├─ __init__.py
│     │  ├─ rotator.py           # language/day rotation + query plan
│     │  └─ google.py            # Google JSON API client
│     ├─ ingest/
│     │  ├─ __init__.py
│     │  └─ fetch.py             # fetch+parse (trafilatura), PDF handling
│     ├─ extract/
│     │  ├─ __init__.py
│     │  ├─ llm.py               # LLM client (HF local or API), prompt, parser
│     │  └─ regex_fallback.py    # cheap backup extractor
│     ├─ normalize/
│     │  ├─ __init__.py
│     │  └─ events.py            # dedupe/merge, date normalization, QA flags
│     ├─ store/
│     │  ├─ __init__.py
│     │  └─ io.py                # save CSV/Parquet/DuckDB
│     └─ cli.py                  # “glue”: orchestrates the pipeline
├─ plots/
└─ tests/
   ├─ test_rotator.py
   ├─ test_llm_contract.py
   └─ test_normalize.py
```
