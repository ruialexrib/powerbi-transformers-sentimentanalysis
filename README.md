<div align="center">

# Power BI Sentiment Analysis with Transformers

### Bringing transformer-based NLP directly into Power BI with Python.

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Transformers](https://img.shields.io/badge/Transformers-Hugging%20Face-FFD21E?style=flat)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![NLP](https://img.shields.io/badge/NLP-Sentiment%20Analysis-blue)
![License](https://img.shields.io/badge/License-MIT-green.svg)

Developed by [Rui Ribeiro](https://github.com/ruialexrib)

</div>

---

## About

This project demonstrates how **Natural Language Processing (NLP)** and **transformer models** can be integrated directly into **Power BI** using Python.

A Python script executed through **Power Query** applies a pre-trained sentiment analysis model from the Hugging Face Transformers ecosystem to textual data. The resulting sentiment labels and confidence scores are then made available inside the Power BI data model for analysis and visualization.

The project provides a compact example of how modern AI capabilities can be incorporated into a traditional Business Intelligence workflow without requiring a separate machine learning application.

## Project Objectives

The project illustrates how to:

- Integrate Python-based NLP into Power BI
- Execute transformer inference during Power Query processing
- Classify textual comments by sentiment
- Generate confidence scores for model predictions
- Make AI-generated results available to the Power BI semantic model
- Analyse and visualize sentiment results using Power BI and DAX

## Sentiment Analysis Approach

Sentiment classification is performed using the `sentiment-analysis` pipeline from the **Hugging Face Transformers** library.

The pipeline uses a pre-trained **DistilBERT-based model** for sequence classification, allowing contextual sentiment analysis without training a model from scratch.

The workflow is:

```text
Text Dataset
     │
     ▼
Power Query
     │
     ▼
Python + Hugging Face Transformers
     │
     ▼
DistilBERT Sentiment Model
     │
     ├── Sentiment Label
     └── Confidence Score
     │
     ▼
Power BI Data Model
     │
     ▼
DAX Analysis & Visualizations
```

## Power BI Integration

The machine learning inference is executed during the Power Query data transformation stage.

The process consists of five main steps:

1. Load the textual dataset into Power BI.
2. Execute the Python script from Power Query.
3. Load the pre-trained transformer sentiment pipeline.
4. Apply the model to each text observation.
5. Return the sentiment label and confidence score to Power BI for further analysis.

This approach makes it possible to enrich BI datasets with NLP-generated features while keeping the analytical workflow inside Power BI.

## Technologies

| Technology | Purpose |
| --- | --- |
| **Power BI** | Data modelling, analysis and visualization |
| **Power Query** | Data preparation and Python integration |
| **Python** | NLP processing and model inference |
| **Hugging Face Transformers** | Pre-trained transformer pipeline |
| **DistilBERT** | Transformer-based sentiment classification |
| **PyTorch** | Deep learning runtime |
| **Pandas** | Data manipulation |
| **DAX** | Analytical calculations inside Power BI |

## Project Structure

```text
powerbi-transformers-sentimentanalysis/
├── src/
│   ├── dataset.csv
│   ├── requirements.txt
│   ├── transformers-sentimentanalysis.ipynb
│   └── transformers-sentimentanalysis.pbix
├── LICENSE
└── README.md
```

### Files

- `src/transformers-sentimentanalysis.pbix` — Power BI report containing the complete workflow.
- `src/transformers-sentimentanalysis.ipynb` — Jupyter Notebook demonstrating the sentiment analysis process.
- `src/dataset.csv` — Sample textual dataset used for sentiment analysis.
- `src/requirements.txt` — Python dependencies required by the project.

## Requirements

The Python dependencies are defined in `src/requirements.txt`:

```text
pandas>=1.5.0
transformers>=4.36.0
torch>=2.0.0
tqdm>=4.64.0
```

Install them with:

```bash
pip install -r src/requirements.txt
```

Power BI must also be configured to use the Python environment where these dependencies are installed.

## Running the Demo

1. Clone the repository.
2. Install the Python dependencies.
3. Configure the Python scripting environment in Power BI Desktop.
4. Open `src/transformers-sentimentanalysis.pbix`.
5. Refresh the Power Query model to execute the sentiment analysis pipeline.
6. Explore the generated sentiment labels and confidence scores in Power BI.

## Notes and Limitations

The transformer model is loaded as part of the Power Query execution process. This is convenient for demonstrations and exploratory analysis but introduces additional processing time during dataset refreshes.

For larger datasets or production scenarios, model inference would normally be moved outside Power BI to a dedicated preprocessing pipeline, model-serving API or other scalable inference architecture.

This implementation is therefore primarily intended for:

- Educational demonstrations
- Business Intelligence prototypes
- Small datasets
- NLP experimentation
- Proof-of-concept integrations between Power BI and transformer models

## License

Distributed under the [MIT License](LICENSE).

Copyright © 2025 [Rui Ribeiro](https://github.com/ruialexrib).
