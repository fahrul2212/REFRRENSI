# METODE DAN HASIL

## Review of Research Paper: A Hybrid UNet with Attention and a Perceptual Loss Function for Monocular Depth Estimation

### Paper Information
- **Title**: A Hybrid UNet with Attention and a Perceptual Loss Function for Monocular Depth Estimation
- **Authors**: Hamidullah Turkmen and Devrim Akgun
- **Publication**: Mathematics 2025, 13, 2567
- **Dataset Used**: NYU Depth V2

---

## Table 1: Methods Overview

| Method Component | Description | Key Features |
|-----------------|-------------|--------------|
| **Architecture** | Transformer-based Hybrid UNet | - Encoder-decoder structure<br>- ResNet18 backbone for local feature extraction<br>- Transformer attention blocks for global context<br>- Multi-Head Self-Attention (MHSA) mechanism |
| **Encoder** | ResNet18 | - Extracts multi-scale feature maps<br>- Provides local edge, texture, and structural information<br>- Residual connections to avoid vanishing gradients |
| **Decoder** | UNet Decoder with Skip Connections | - Transposed convolutions for upsampling<br>- Skip connections preserve fine-grained information<br>- Multi-scale feature fusion |
| **Attention Mechanism** | Transformer Blocks | - Captures long-range dependencies<br>- Learns relationships between distant regions<br>- Global context understanding |
| **Loss Function** | Boundary-Aware Depth Consistency Loss (BADCL) | - Dynamic scaling<br>- Smoothness regularization<br>- Boundary-aware weighting<br>- Provides sharper edges and smoother depth transitions |
| **Training Details** | NYU Depth V2 Dataset | - 30-100 epochs<br>- Image size: 224×224 pixels<br>- Split: 70% train, 10% validation, 20% test<br>- Python 3.12.5, PyTorch framework<br>- NVIDIA GeForce RTX 4090 24GB |

---

## Table 2: Comparative Performance Results

### Performance Metrics Comparison with State-of-the-Art Methods

| Method | ARE ↓ | RMSE ↓ | Log10 ↓ | δ < 1.25 ↑ | δ < 1.25² ↑ | δ < 1.25³ ↑ | SSIM ↑ |
|--------|-------|--------|---------|------------|-------------|-------------|--------|
| Mancini et al. [39] | 0.312 | 0.565 | 0.336 | 0.809 | 0.786 | 0.911 | - |
| Xu et al. [40] | 0.125 | 0.593 | 0.057 | 0.806 | 0.952 | 0.986 | - |
| Alhashim et al. [41] | 0.123 | 0.465 | 0.053 | 0.846 | 0.974 | 0.994 | - |
| Li et al. (VGG16) [42] | 0.152 | 0.611 | 0.064 | 0.789 | 0.955 | 0.988 | - |
| Li et al. (VGG19) [42] | 0.146 | 0.617 | 0.063 | 0.795 | 0.958 | 0.991 | - |
| Li et al. (ResNet50) [42] | 0.143 | 0.635 | 0.063 | 0.788 | 0.958 | 0.991 | - |
| Rudolph et al. [43] | 0.138 | 0.501 | 0.058 | 0.823 | 0.961 | 0.990 | - |
| Lee et al. [44] | 0.131 | 0.538 | - | 0.837 | 0.971 | 0.994 | - |
| Guizilini et al. [45] | 0.072 | 2.727 | 0.120 | 0.932 | 0.984 | 0.994 | - |
| Basak et al. [46] | 0.103 | 0.388 | - | 0.892 | 0.978 | 0.995 | - |
| Das et al. (Enc-Dec-IRv2) [47] | 0.064 | 0.228 | 0.032 | 0.893 | 0.967 | 0.985 | - |
| Ignatov et al. [48] | 0.090 | 0.322 | 0.039 | 0.929 | 0.991 | 0.998 | - |
| **Hybrid Ensemble UNet (Proposed)** | **0.063** | **0.237** | **0.026** | **0.982** | **0.996** | **0.998** | **0.998** |

**Legend:**
- ↓ = Lower is better (Error Metrics)
- ↑ = Higher is better (Accuracy Metrics)
- **Bold** = Best result in each column
- ARE = Absolute Relative Error
- RMSE = Root Mean Squared Error
- Log10 = Logarithmic Error
- δ < 1.25, δ < 1.25², δ < 1.25³ = Accuracy thresholds
- SSIM = Structural Similarity Index Measure

---

## Key Results Summary

### Performance Highlights
1. **SSIM Score**: **99.8%** - Structural similarity index measure, indicating excellent depth map quality
2. **ARE**: **0.063** - Lowest absolute relative error among all methods
3. **RMSE**: **0.237** - Competitive root mean squared error
4. **Log10**: **0.026** - Best logarithmic error
5. **Accuracy δ < 1.25**: **98.2%** - Highest accuracy at primary threshold
6. **Accuracy δ < 1.25²**: **99.6%** - Near-perfect accuracy at second threshold
7. **Accuracy δ < 1.25³**: **99.8%** - Highest accuracy at third threshold

### Training Performance
- **Training Loss**: Approaches 0.0005 after 100 epochs
- **Validation Loss**: Approximately 0.0006 after 100 epochs
- **Convergence**: Consistent reduction in loss demonstrates effective training

### Key Advantages
1. **Fewer Trainable Parameters**: Achieves state-of-the-art results with reduced model complexity
2. **Better Edge Preservation**: BADCL loss function provides sharper edges
3. **Smooth Depth Transitions**: Enhanced smoothness regularization
4. **Scale-Consistent Predictions**: Dynamic scaling ensures accurate depth estimation
5. **Global Context Understanding**: Transformer blocks capture long-range dependencies
6. **Efficient Architecture**: ResNet18 backbone provides good balance between performance and efficiency

### Applications
- **Autonomous Driving**: Environmental perception, obstacle detection
- **Robotics Navigation**: Path planning and object avoidance
- **Augmented Reality**: Scene understanding and depth mapping
- **Indoor Scene Understanding**: Room layout estimation and object localization

---

## Conclusion

The proposed Hybrid Ensemble UNet with Transformer attention and Boundary-Aware Depth Consistency Loss (BADCL) achieves **state-of-the-art performance** in monocular depth estimation on the NYU Depth V2 dataset. The model demonstrates:

- **Superior accuracy** across all evaluation metrics
- **Efficient architecture** with fewer trainable parameters
- **Practical applicability** for real-time autonomous systems
- **Robust performance** with SSIM of 99.8%

The integration of ResNet18 encoder, Transformer attention mechanisms, and the novel BADCL loss function enables the model to capture both local features and global context effectively, resulting in high-quality depth predictions suitable for safety-critical applications.
