# Change Database Generator

`build-change-db.py` collects the change entries from the audit topic YAML
files (by default `docs/audit_report/changes/topics`, resolved relative to the
script's location) and creates or updates a JSON database file.

The database file is named `botan-changes.<x.y.z>.json`, where `<x.y.z>` is the
`BOTAN_VERSION` configured in `config/botan.env`. By default it is written to
`docs/database` (created if necessary). If the database file already exists,
its entries are updated in-place: entries found in the topic files replace
their previous state in the database, new entries are appended, and entries no
longer found in the topic files are deleted after asking the user for
confirmation. The confirmation prompt allows applying the answer to all
remaining absent entries ("[Y]es to all" / "[N]o to all"). With
`--non-interactive` absent entries are deleted without confirmation.

The database contains meta information about the targeted Botan version of the
audit followed by the list of change entries. Each change entry directly
reflects the structure of its YAML source entry, except that the `categories`
field is always present as a JSON list: if the YAML entry carries a
`categories` field, its comma separated tags are used; otherwise the name of
the containing topic YAML file (without the `.yml` extension) becomes the only
list entry.

```json
{
  "meta": {
    "botan_version": "3.12.0",
    "botan_ref": "3.12.0",
    "botan_base_ref": "3.11.0"
  },
  "changes": [
    {
      "pr": 5579,
      "merge_commit": "13e5dbb03bb69d61d6b2f5009b58194a314966b6",
      "classification": "unspecified",
      "categories": ["uncategorized"]
    }
  ]
}
```

## Usage

```bash
python3 tools/change-db/build-change-db.py [-t TOPICS_DIR] [-d DATABASE_FILE] [-n] [-v]
```

- `-t/--topics-dir`: overrides the topic YAML input directory
- `-d/--database-file`: overrides the database file location and name
- `-n/--non-interactive`: deletes absent entries without asking for confirmation
- `-v/--verbose`: enables detailed logging
