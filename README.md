# MedNER-TR

Turkish Medical Named Entity Recognition System

## Performance

- F1 Score: 99.49%
- Precision: 99.49%
- Recall: 99.49%
- Accuracy: 99.76%

## Links

- Demo: https://huggingface.co/spaces/tugrulkaya/medner-tr-demo
- Model: https://huggingface.co/tugrulkaya/medner-tr

## Quick Start
```python
from transformers import pipeline

ner = pipeline("token-classification", 
               model="tugrulkaya/medner-tr",
               aggregation_strategy="simple")

text = "Hastaya Parol 500mg baslandi."
results = ner(text)
```

## Supported Entities

- ILAC (Medications)
- HASTALIK (Diseases)
- SEMPTOM (Symptoms)
- ORGAN (Organs)
- TEST (Medical Tests)

## Installation
```bash
pip install transformers torch
```

## Examples

### Example 1
```python
text = "Hastaya Parol 500mg baslandi."
results = ner(text)
# Output: ILAC: Parol
```

### Example 2
```python
text = "Hasta ates, oksuruk ile basvurdu."
results = ner(text)
# Output: SEMPTOM: ates, SEMPTOM: oksuruk
```

## License

MIT License - Free for commercial and research use

## Contact

- GitHub: https://github.com/tugrulkaya/medner-tr
- Hugging Face: https://huggingface.co/tugrulkaya/medner-tr
