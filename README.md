# Review-based Opinion Mining & Summarization for Products

### Installation
To run this project, run the following commands
```
git clone https://github.com/latentghost/Review-based-Opinion-Mining-for-Products
cd Review-based-Opinion-Mining-for-Products
pip install -r requirements.txt
```

### Overview

This project aims to enhance the reliability of online product reviews and provide accurate product descriptions by employing advanced Natural Language Processing (NLP) techniques. We built a custom encoder-only transformer model with a unique “Self & Cross-Categorical Attention” mechanism to distinguish between real and fake reviews on e-commerce platforms. After identifying genuine reviews, we used a fine-tuned BART model to generate a summarized product description. This description is then compared against the seller’s description using semantic text similarity evaluation methods, providing a score that indicates the accuracy of the seller’s description.

### Dataset
- The dataset used for the fake review detection task is the Amazon Product Data, which contains product reviews, and real-fake labels for various products. The dataset is preprocessed to extract relevant information such as product reviews, ratings, product categories, etc. These are then used as features in an Encoder-only Transformer-based model that is able to distinguish between real and fake reviews.
- The dataset used for the second task is the Amazon Product Description dataset, which contains product descriptions and titles for various products. The dataset is preprocessed to extract relevant information such as product descriptions, titles, etc. These are then used as features for a fine-tuned BART model that generates a summarized product description.

### Model Architecture
#### Encoder-only Transformer Model
- The encoder-only transformer model is a custom model that uses a unique “Self & Cross-Categorical Attention” mechanism to distinguish between real and fake reviews. The model takes in product reviews, ratings, and product categories as input features and outputs a binary classification of real or fake review.
- It uses a custom attention mechanism that combines self-attention and cross-categorical attention to capture the relationships between different product categories and reviews. This allows the model to learn the differences between real and fake reviews across different product categories.

#### Fine-tuned BART Model
- The fine-tuned BART model is used to generate a summarized product description based on the input product reviews. The model is fine-tuned on the Amazon Product Description dataset to generate accurate and concise summaries of a combination of all reviews for each product.
- The model takes in product reviews as input and generates a summarized product description as output. The generated description is then compared against the seller’s description using semantic text similarity evaluation methods to provide a score that indicates the accuracy of the seller’s description.

### Training
- The encoder-only transformer model is trained on the Amazon Product Data dataset using a binary cross-entropy loss function and Adam optimizer. The model is trained to distinguish between real and fake reviews with high accuracy.
- Run the follwing command to train the encoder-only transformer model and extract set of real reviews from the entire data:
```
python fakeReviewDetection.py
```
- The fine-tuned BART model is trained on the Amazon Product Description dataset using a sequence-to-sequence loss function and Adam optimizer. The model is trained to generate accurate and concise summaries of product reviews.
- Run the follwing command to generate and evaluate the summaries using the fine-tuned BART model:
```
python extractProductSummary.py
```

### Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change. Please make sure to create a new branch for your changes.

### License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.