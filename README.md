# Power BI Sentiment Analysis with Transformers

This project demonstrates how **sentiment analysis** can be integrated into **Power BI** using **Python** and a **pre-trained transformer model (DistilBERT)** from the Hugging Face ecosystem.

The solution is implemented inside a **Power BI report**, where a Python script is executed in **Power Query** to analyse textual data and generate sentiment labels and confidence scores.

## Files

- `transformers-sentimentanalysis.pbix`  
  Power BI report containing the full workflow:
  - Data loading from CSV
  - Text preprocessing
  - Execution of a Python script in Power Query
  - Sentiment classification using a pre-trained DistilBERT model
  - Generation of sentiment labels and confidence scores
  - Aggregation and visualisation using DAX measures

- `dataset.csv`  
  Dataset containing textual comments used for sentiment analysis.

## Sentiment Analysis Approach

Sentiment classification is performed using the **`sentiment-analysis` pipeline** from the **Transformers** library, which by default loads a **DistilBERT-based model** fine-tuned for sentiment detection.

Core steps:
1. Load the dataset into Power BI
2. Execute a Python script in Power Query
3. Apply the pre-trained sentiment analysis model to each comment
4. Extract sentiment labels and confidence scores
5. Analyse and visualise results using DAX

This approach provides a **context-aware sentiment classification**, suitable for demonstration and exploratory analysis.

## Notes and Limitations

- The transformer model is loaded on each Power Query refresh, which may impact performance.
- This solution is recommended for **small datasets, demos, or academic use**.
- For production environments, external preprocessing or API-based inference is advised.

## License

This project is provided for educational and demonstration purposes.
