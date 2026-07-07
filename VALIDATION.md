# Validation

Run the Codex skill validator for each skill folder:

```bash
python <skill-creator>/scripts/quick_validate.py engineer-literature
python <skill-creator>/scripts/quick_validate.py engineer-read-code
python <skill-creator>/scripts/quick_validate.py engineer-figure
```

On Windows, set UTF-8 mode if the validator reads Chinese text with the system default
encoding:

```powershell
$env:PYTHONUTF8='1'
```

Before making the repository public, review bundled third-party images and demo assets
under `engineer-figure/assets/`. If redistribution rights are uncertain, keep only
metadata links and remove the image files from the public release.

