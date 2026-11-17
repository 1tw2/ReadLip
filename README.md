# ReadLip research repository assembly

This bundle assembles upstream TalkLip with independent ReadLip research modules.
It is **not yet a trained or fully integrated ReadLip reproduction**.
See [README_READLIP.md](README_READLIP.md) and
[TALKLIP_README.md](TALKLIP_README.md) after assembly for dataset, checkpoint, and environment instructions.

## Assemble on your computer

```bash
python scripts/assemble.py --output ReadLip
# Or if you already cloned TalkLip:
python scripts/assemble.py --talklip-path /path/to/TalkLip --output ReadLip
```

Do not run `scripts/assemble.py` from within a destination named `ReadLip`.
Run it in this extracted bundle's root; it creates a **separate** `ReadLip` directory.

## GitHub upload

1. Create an empty repository named `ReadLip` at https://github.com/new
   under account `1tw2` (do not initialize with a README).
2. In a shell:

```bash
cd ReadLip
git init
git branch -M main
git add .
git commit -m "Initial ReadLip research scaffold based on TalkLip"
git remote add origin https://github.com/1tw2/ReadLip.git
git push -u origin main
```

`git` may prompt for authentication; use Git Credential Manager or `gh auth login`,
not your GitHub account password.
