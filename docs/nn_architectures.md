# Neural Network Architecture Options for ASVspoof

## 1. CNN (2D Convolutional Networks)
- **Keywords**: 2D CNN, VGG-style, ResNet, spectrogram input
- Treats time-frequency features (spectrogram/CQT/LFCC) as images; ResNet/SE-ResNet variants were strong PA/replay detectors.

## 2. Res2Net / SE-Res2Net
- **Keywords**: Res2Net, squeeze-and-excitation, SE-Res2Net, multi-scale feature aggregation
- Multi-scale receptive fields + channel attention; top performer on LFCC/CQT features in several ASVspoof submissions.

## 3. RawNet2 (End-to-End Raw Waveform CNN)
- **Keywords**: RawNet2, sinc-convolution, residual blocks, raw audio CNN
- Sinc-conv front-end + residual CNN blocks + GRU; learns directly from waveform, no handcrafted features.

## 4. Graph Attention Networks (GAT) on Spectro-Temporal Features
- **Keywords**: graph attention network, GAT, RawGAT-ST, spectral-temporal graph
- Models relationships between time and frequency nodes as a graph; captures non-local dependencies missed by CNNs.

## 5. AASIST (Heterogeneous Graph Attention + Max Graph Operation)
- **Keywords**: AASIST, heterogeneous graph attention, HS-GAL, max graph operation, MGO
- Current SOTA-ish single-system baseline; combines spectral and temporal graphs with a fusion ("max graph") layer.

## 6. RNN / LSTM / GRU-based Models
- **Keywords**: LSTM, GRU, bidirectional RNN, sequence modeling
- Used as back-end after CNN front-ends to capture temporal dynamics; less common as standalone now but easy to implement for a course project.

## 7. Transformer / Self-Attention Models
- **Keywords**: transformer encoder, self-attention, multi-head attention, conformer
- Used both as standalone classifiers and as back-ends on top of SSL embeddings (wav2vec2 + transformer head).

## 8. Light CNN (LCNN)
- **Keywords**: Light CNN, LCNN, Max-Feature-Map (MFM) activation
- A long-standing ASVspoof baseline architecture; lightweight, uses MFM activation instead of ReLU for feature selection.

## 9. Capsule Networks
- **Keywords**: capsule network, CapsNet, dynamic routing
- Less common but explored in a few ASVspoof papers for capturing part-whole spatial relationships in spectrograms.

## 10. Siamese / Contrastive Networks
- **Keywords**: Siamese network, contrastive learning, triplet loss, embedding distance
- Learns to compare genuine vs. spoof pairs via embedding distance rather than direct classification; useful for few-shot/unseen attack generalization.

## 11. Ensemble / Fusion Models
- **Keywords**: score fusion, model ensemble, multi-branch network, logistic regression fusion
- Combines multiple architectures/front-ends at the score level — historically very competitive and relatively simple to implement.
