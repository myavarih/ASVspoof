# Feature Extraction Options for ASVspoof

## 1. MFCC (Mel-Frequency Cepstral Coefficients)
- **Keywords**: MFCC, mel filterbank, cepstral coefficients, DCT
- Classic speech feature; compresses spectrum into perceptually-motivated bands. Less popular in ASVspoof since it discards phase/high-freq artifacts useful for spoof detection.

## 2. LFCC (Linear Frequency Cepstral Coefficients)
- **Keywords**: LFCC, linear filterbank, cepstral analysis
- Like MFCC but linear frequency spacing — preserves high-frequency info better, a long-time ASVspoof baseline feature.

## 3. CQCC (Constant-Q Cepstral Coefficients)
- **Keywords**: CQCC, constant-Q transform, CQT, variable time-frequency resolution
- Official ASVspoof 2015/2017/2019 baseline feature; good at capturing both low-freq and high-freq spoofing artifacts.

## 4. Spectrogram / Log-Spectrogram
- **Keywords**: STFT, spectrogram, log-magnitude spectrogram, time-frequency representation
- Direct 2D representation fed into CNNs; simple and widely used.

## 5. Mel-Spectrogram
- **Keywords**: mel-spectrogram, mel filterbank, log-mel
- Common in TTS/vocoder pipelines too — useful since spoof artifacts often originate here.

## 6. Sinc-Convolution Front-End (learnable filters)
- **Keywords**: SincNet, sinc-convolution, learnable bandpass filters, RawNet
- Not a fixed feature — a trainable first layer that learns filterbank-like representations directly from raw audio (used in RawNet2/AASIST).

## 7. Group Delay / Phase-Based Features
- **Keywords**: group delay, phase spectrum, modified group delay (MGD), instantaneous frequency
- Captures phase information that magnitude-based features (MFCC/LFCC) discard — useful since synthetic speech often has unnatural phase.

## 8. Self-Supervised Learning (SSL) Embeddings
- **Keywords**: wav2vec 2.0, WavLM, HuBERT, XLSR, pretrained speech representations, fine-tuning
- Pretrained transformer embeddings; currently top-performing front-end for generalization to unseen attacks.

## 9. x-vectors / Speaker Embeddings
- **Keywords**: x-vector, ECAPA-TDNN, speaker embedding, d-vector
- Originally for speaker verification, but used as auxiliary features in some spoof detection systems (captures device/channel signatures).

## 10. Pitch / Prosodic Features
- **Keywords**: F0, pitch contour, jitter, shimmer, prosody features
- Captures unnatural pitch patterns common in some TTS/VC outputs; usually combined with other features rather than used alone.
