# Financial News Analysis for Abstractive Summarization and Sentiment Classification

This project addresses the critical challenge of information overload in the financial sector by providing a robust NLP-powered system for automated financial news analysis. We leverage state-of-the-art transformer models to deliver concise, abstractive summaries and accurate sentiment analysis of complex financial articles, enabling professionals like investors, analysts, and traders to make faster, more informed decisions.

The sheer volume and complexity of financial news can impede rapid decision-making. Manual analysis is not only time-consuming but also prone to human error and subjective interpretation. This project automates the process, distilling lengthy articles into their essential insights and classifying their market sentiment.

### Key Features

  **Abstractive Summarization**: Utilizes a fine-tuned **PEGASUS** model to generate human-like summaries of financial texts, focusing on brevity while preserving critical information.

  **Sentiment Analysis**: Employs a fine-tuned **BERT** model to classify financial news sentiment as positive, negative, or neutral with high accuracy.

  **Domain-Specific Tuning**: Both models are fine-tuned on specialized financial datasets—the Gretel Financial Risk Analysis Dataset for summarization and the Financial Phrasebank for sentiment—to capture domain-specific nuances.

  **Proven Performance**: The sentiment model achieves high accuracy (74%) and F1-scores (0.72), and the summarization model shows significant improvements in ROUGE scores after customization.

### Methodology

 The core of this project is the sophisticated application and customization of transformer-based models.

1.  **Data Sourcing and Preprocessing**: We used two primary datasets:

       **Gretel Financial Risk Analysis Dataset**: Over 1,000 articles used for training the summarization model.

       **Financial Phrasebank**: Over 4,800 annotated sentences for sentiment classification.
        Data was rigorously cleaned, tokenized using model-specific tokenizers (PEGASUS and BERT), and standardized to optimize model input

2.  **Model Architecture and Customization**:

       **PEGASUS for Summarization**: We selected PEGASUS for its proven strength in abstractive summarization.  The model was fine-tuned by adjusting hyperparameters and reducing the max token length for output to 150 to ensure conciseness

       **BERT for Sentiment Analysis**: A BERT model was fine-tuned for financial text.  We replaced the final classification layer with a dense output layer with a softmax activation function to predict positive, negative, and neutral classes[cite: 56, 57].  Dropout layers were added to both models to mitigate overfitting[cite: 55, 58].

### Results

Our models demonstrate strong performance in their respective tasks.

   **Sentiment Analysis (BERT)**:

       Accuracy: 74% 
       Precision 0.73 
       Recall 0.72 
       F1-Score 0.72 

   **Summarization (PEGASUS)**: The custom-tuned PEGASUS model achieved strong ROUGE scores, indicating high-quality summary generation.

       ROUGE-1 0.4524 
       ROUGE-2 0.2231 
       ROUGE-L 0.3151 

 While effective, we noted some limitations, such as PEGASUS occasionally omitting key details and BERT struggling to differentiate certain neutral and negative statements[cite: 70]. These provide clear avenues for future work.

### Project Structure

```
.
├── Finacial News Summary and Sentiment Report.pdf
├── Financial News Summarization and Sentiment Presentation.pdf
├── Financial News Summarization.pdf
├── LICENSE
├── project_tree.txt
├── README.md
├── Sentiment Analysis Code .pdf
├── Sentiment_Analysis.ipynb
├── sentiment_analysis.txt
├── TextSummarization.ipynb
└── textsummarization.txt
```

### How to Use

The core logic and implementation can be found in the Jupyter Notebooks:

1.  **Text Summarization**: Open and run the cells in `TextSummarization.ipynb` to see the implementation of the fine-tuned PEGASUS model.
2.  **Sentiment Analysis**: Open and run the cells in `Sentiment_Analysis.ipynb` to see the implementation of the fine-tuned BERT model for sentiment classification.

Ensure you have the required libraries and datasets installed before execution.

### Future Work

 This project establishes a strong foundation for future advancements in financial NLP. Potential next steps include:

   Expanding the training datasets to improve model robustness and nuance detection. Exploring alternative model architectures to enhance performance further. Deploying the system in a real-world, live-trading environment to validate its practical applicability.