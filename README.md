# Document-Classification-with-Neural-Networks

## Project Documentation
This project focuses on building an end-to-end text classification system to automatically categorize over 18,000 text documents into 20 distinct classes based on their content. The classification task is designed to handle real-world, noisy text data, where each document is labeled using a class identifier embedded in its filename. The objective is to accurately predict the document’s class using advanced preprocessing techniques and deep learning models.

The development process began with extensive preprocessing to clean and structure the raw text. This included extracting subject lines, removing unwanted metadata (e.g., tags, email headers, special characters), deconstruction of words, and elimination of noisy patterns such as HTML tags, bracketed content, and short/informative-less tokens. Further, Natural Language Processing (NLP) techniques like Named Entity Chunking were applied to group meaningful phrases and filter out person entities. Custom logic was introduced to normalize edge cases in token formats and apply consistent casing and length-based filtering.

Post-cleaning, all processed content (subject, email, and main text) was merged into a single representation for modeling. The dataset was then split into training and testing sets using stratified sampling to preserve class distribution. Tokenization and padding were performed carefully to preserve important symbols (like underscores) and ensure uniform input lengths. Two deep learning architectures were implemented:
* Model-1: A 1D CNN with pre-trained GloVe word embeddings to capture semantic word-level patterns.
* Model-2: A 1D CNN with character-level embeddings, inspired by Char-CNN architectures for deeper granularity and robustness against spelling variations.

Both models were trained using categorical cross-entropy loss, evaluated via accuracy and micro-averaged F1 score, and monitored using TensorBoard. Early stopping and callback mechanisms were employed to optimize training efficiency. The best-performing models were saved for future inference.

This solution provides a scalable, accurate pipeline for multi-class document classification and demonstrates effective use of NLP preprocessing and neural architectures. It has practical applications in email filtering, content moderation, legal document classification, and more, delivering automation and consistency in high-volume text processing environments.
