# Vilod JSON Lines Check

Check JSONL and NDJSON exports locally before importing them. The result
contains counts and the first 20 invalid line numbers. It omits record values.

[Download the scripts as ZIP](../../archive/refs/heads/main.zip).

## Quick start

Requires Python 3.10+. Unzip the download and run:

```sh
python jsonl_check.py example.jsonl --objects
```

Use `py` on Windows if Python is registered through the Python launcher.
The sample returns `{"lines": 2, "invalid": 0, "first_invalid_lines": []}`.

Each line must be one valid JSON value. Use `--objects` to reject arrays
and scalars. Blank lines and invalid UTF-8 count as errors.
Exit codes: 0 clean, 1 invalid records, 2 unreadable input or usage error.
The script reads the file line by line and makes no network requests.

MIT license.
