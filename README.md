#Artwork Similarity Search with DINOv2

>Shambhavi Adhikari,Yeji Kim 

**Overview**

We built a visual artwork similarity search system using DINOv2 to measure whether self-supervised models capture style (brushstrokes, texture) or content (portrait, landscape). Using a 12k-image WikiArt subset, we performed a large-scale retrieval evaluation.

**Method**
- Dataset: 12,000 WikiArt images from 8
- Content labels: Portrait / Landscape / Abstract / Still Life / Cityscape (auto-parsed)
- Models: DINOv2 Base + Large (ensemble + PCA) and ResNet-50 baseline

**Pipeline Improvements:**
- Multi-crop embeddings (8 crops)
- DINOv2 ensemble for stability
- Reciprocal re-ranking for precision

**Results**
- DINOv2 outperforms ResNet-50 across all retrieval metrics.
- Content dominates style for both models:
  - DINOv2 → 17% style-only · 25.2% content-only · 34.5% both
  - ResNet-50 → 17.5% style-only · 23.1% content-only · 28.8% both
  - DINOv2 strongly retrieves similar subjects, less so stylistic matches.

**Key Findings**
- Unexpected content bias: DINOv2 focuses on subjects more than technique.
- Enhancements matter: Multi-crop, ensembles, PCA, and re-ranking significantly improve robustness.
- Hybrid retrieval is ideal: Balancing style + content provides better user control.
  
**Future Work**
- Cross-domain evaluation (sculpture, architecture, non-Western art)

Explainability via attention maps + textual rationales

Reducing multi-crop computational cost
