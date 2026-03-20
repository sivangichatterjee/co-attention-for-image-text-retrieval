# Bidirectional Co-Attention Networks for Enhanced Image-Text Retrieval

This project studies **image-text retrieval** using a **bidirectional co-attention network**. Instead of comparing only global image and text embeddings, the model lets **image patches attend to text tokens** and **text tokens attend to image patches** before pooling. This improves fine-grained cross-modal alignment and leads to better retrieval performance.

## What this project does

The project compares different multimodal fusion strategies for image-text retrieval:

- Vector Concatenation
- CLIP-style Dual Encoder
- Unidirectional Cross-Attention
- Bidirectional Co-Attention

The main idea is that both modalities should refine each other before similarity is computed, rather than being fused too early or processed independently.

## Model

The model uses:

- **ViT-B/16** for image feature extraction
- **BERT-base** for text feature extraction
- a **bidirectional co-attention module**
- residual connections and layer normalization
- **InfoNCE loss** for training

## Dataset

The model is evaluated on **Flickr30k**, a standard benchmark for image-text retrieval.

## Results

The bidirectional co-attention model outperforms all baseline methods on Flickr30k.

| Model | Avg R@1 |
|------|--------:|
| Vector Concatenation | 0.15 |
| Cross-Attention | 30.8 |
| CLIP-style Dual Encoder | 42.5 |
| **Co-Attention (Ours)** | **51.0** |

More detailed retrieval results:

|   Model                 | I2T R@1 | T2I R@1 |
|-------------------------|--------:|--------:|
| Vector Concatenation    | 0.1     | 0.2 |
| Cross-Attention         | 31.0    | 30.5 |
| CLIP-style Dual Encoder | 45.5    | 39.5 |
| **Co-Attention (Ours)** | **53.0** | **49.0** |

Our model improves over the CLIP-style dual encoder by **8.5 points in average R@1** and over unidirectional cross-attention by **20.2 points in average R@1**.

## Why it matters

This project shows that **explicit bidirectional interaction** between image and text features works much better than simple fusion or one-way attention for image-text retrieval. It also provides a more interpretable multimodal fusion mechanism through attention maps.

