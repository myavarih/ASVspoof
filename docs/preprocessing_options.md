# Preprocessing Options for Raw-Waveform ASVspoof Models

## 1. Silence Trimming (VAD)
- **Keywords**: voice activity detection, VAD, energy-based trimming, webrtcvad, silero-vad, leading/trailing silence removal
- Removes dead air at start/end of recordings so the model doesn't learn dataset-specific silence patterns.

## 2. Fixed-Length Cropping / Padding
- **Keywords**: fixed-length input, audio cropping, zero-padding, repeat-padding, chunking
- Standardizes input duration (e.g., 4 sec) for batch processing — shape, not content, change.

## 3. Amplitude Normalization
- **Keywords**: peak normalization, RMS normalization, loudness normalization, dBFS scaling
- Equalizes loudness across samples to prevent "volume" from becoming a shortcut feature.

## 4. Resampling
- **Keywords**: sample rate conversion, resampling, 16kHz standardization, sinc interpolation
- Ensures consistent sample rate across mixed-source datasets.

## 5. Data Augmentation (RawBoost-style)
- **Keywords**: RawBoost, additive noise, convolutive noise, impulsive noise, SNR-based noise injection, channel simulation, linear filtering
- Adds noise/channel variation during training to improve robustness — doesn't change labels.

## 6. Reverberation Augmentation
- **Keywords**: reverb, room impulse response (RIR), convolutional reverb, RIR convolution, acoustic simulation
- Simulates different recording environments; use mild/short RIRs to avoid masking spoofing artifacts.

## 7. Codec / Compression Augmentation
- **Keywords**: codec simulation, MP3/AAC/Opus compression, lossy compression artifacts, bitrate reduction
- Simulates real-world transmission/storage degradation (common in ASVspoof 2021/2024 robustness tracks).

## 8. Denoising (optional, exploratory)
- **Keywords**: spectral subtraction, RNNoise, DeepFilterNet, speech enhancement, noise suppression
- Removes background noise — risk: may also remove spoofing artifacts; good for an ablation experiment.

## 9. Pitch / Speed Perturbation
- **Keywords**: pitch shifting, time-stretching, speed perturbation, tempo augmentation
- Less common in ASVspoof literature but standard in general speech augmentation; use cautiously since it can alter prosody-based spoof cues.
