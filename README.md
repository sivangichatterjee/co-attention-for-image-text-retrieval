# Bidirectional Co-Attention Networks for Enhanced Image-Text Retrieval

This project explores image-text retrieval using a bidirectional co-attention network. Instead of encoding the image and text separately and comparing only global embeddings, the model lets image patches and text tokens attend to each other before pooling. This helps capture fine-grained region-word relationships and improves cross-modal alignment.

## What this project does

The project compares different multimodal fusion strategies for image-text retrieval, including:

- Vector Concatenation
- CLIP-style Dual Encoder
- Unidirectional Cross-Attention
- Bidirectional Co-Attention

The main idea is that both modalities should refine each other. Image features attend to text features, and text features attend to image features, producing better shared representations for retrieval.

## Model

The model uses:

- ViT-B/16 for image feature extraction
- BERT-base for text feature extraction
- A bidirectional co-attention module
- Residual connections and layer normalization
- InfoNCE loss for training

## Dataset

The model is evaluated on Flickr30k, a standard benchmark for image-text retrieval.

## Main Result

The bidirectional co-attention model outperforms the baseline methods in retrieval performance, showing that explicit two-way interaction 
between image and text is more effective than simple fusion or one-way attention.

## Why it matters

This project shows that fine-grained bidirectional interaction between visual and textual features can significantly improve image-text 
retrieval and provide a stronger multimodal fusion strategy than standard baselines.
