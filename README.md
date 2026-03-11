# MedNER-TR — Turkish Medical NER

Turkish **Medical Named Entity Recognition** model and demo.
Use it to extract medical entities (drug, disease, symptom, test, organ) from Turkish clinical-style text.

## Links

- Demo (Space): https://huggingface.co/spaces/tugrulkaya/medner-tr-demo
- Model: https://huggingface.co/tugrulkaya/medner-tr

## Supported Entities

- **ILAC** — Medications
- **HASTALIK** — Diseases
- **SEMPTOM** — Symptoms
- **ORGAN** — Organs
- **TEST** — Medical tests

## Quick Start

```bash
pip install transformers torch
```

```python
from transformers import pipeline

ner = pipeline(
    "token-classification",
    model="tugrulkaya/medner-tr",
    aggregation_strategy="simple",
)

text = "Hastaya Parol 500mg baslandi."
results = ner(text)
print(results)
```

### Example Outputs (Illustrative)

- `Parol` → `ILAC`
- `ates`, `oksuruk` → `SEMPTOM`

## Performance

> Reported metrics:

- F1: **99.49%**
- Precision: **99.49%**
- Recall: **99.49%**
- Accuracy: **99.76%**

## Notes / Limitations

- Model performance may vary depending on:
  - spelling mistakes / informal writing
  - domain shift (different hospitals / note styles)
  - uncommon abbreviations
- Always validate outputs in clinical workflows.

## License

MIT

## Citation

If you use this project in academic work, please cite:

```bibtex
@misc{mednertr,
  title   = {MedNER-TR: Turkish Medical Named Entity Recognition},
  author  = {Tuğrul Kaya},
  year    = {2026},
  url     = {https://github.com/mtkaya/medner-tr}
}
```

## Contact

- GitHub: https://github.com/mtkaya
- Hugging Face: https://huggingface.co/tugrulkaya
