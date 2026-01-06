# Andhrica

Fast ISO 15919 transliteration for Indic scripts.

## Supported Scripts

| Code | Script |
|------|--------|
| `te` | Telugu |
| `ta` | Tamil |
| `ml` | Malayalam |
| `kn` | Kannada |
| `or` | Odia |
| `hi` | Hindi (with schwa deletion) |
| `hi+` | Hindi (aggressive schwa deletion) |
| `sa` | Sanskrit (no schwa deletion) |
| `gon` | Gunjala Gondi |

## Installation
```bash
pip install andhrica
```

## Usage
```python
from andhrica import transliterate

# Single string
transliterate("te", "తెలుగు")
# → 'telugu'

# Multiple strings
transliterate("ta", ["தமிழ்", "நன்றி"])
# → ['tamiḻ', 'naṉṟi']
```

### File Processing
```python
from andhrica import transliterate_file
from andhrica.progress import progress_bar, print_stats

stats = transliterate_file(
    "te",
    "input.txt",
    "output.txt",
    on_progress=progress_bar()
)
print_stats(stats)
```

## Output Format

Uses ISO 15919 romanization with standard diacritics:

- `ā ī ū` — long vowels
- `ṭ ḍ ṇ` — retroflex consonants
- `ś ṣ` — sibilants
- `ṅ ñ` — nasals
- `kʰ gʰ ...` — aspirates

## License

MIT
```

---

**.gitignore**:
```
__pycache__/
*.py[cod]
*$py.class
*.so
.Python
build/
dist/
*.egg-info/
.eggs/
*.egg
.venv/
venv/
ENV/
.idea/
.vscode/
*.swp
.DS_Store
