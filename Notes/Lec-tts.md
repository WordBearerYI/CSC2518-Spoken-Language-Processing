# ASR and TTS in gegeral

Gerald's Presentation for 2019-03-26 and 2019-04-02

## How to Evaluate Naturalness

### Fredman's test

- Paired test, null hyposthesis(very strong): set A and B comes from the same distrubution. Really easy to be rejected.\
better(weaker) null hypothesis: P(A<B) = P(B<A), equally strong
- paired AB test: A and B system which is better -> can only use binomial sign test
MOS test: Mean Opinion Score

### Measure of Naturalness

- Thurstone's Law of Comparative Judgement / BTL -> scale to (-1, 1)

### Neural TTS Systems

- DeepVoice: end-to-end(not really) TTS by Baidu, Real-time\
    (Also check DeepSpeech2)\
    Grapheme-to-phoneme model:
        trained with teacher forcing, beam search\
    Uses a conditioning network
- Tacotron: end-to-end\
    work on character level\
    Griffin-Lim reconstruction

*Check: 2D convolution, teacher forcing, beam search, DeepSpeech2, QRNN (<https://arxiv.org/abs/1611.01576>), round robin execution of kernel, Bi-directional RNN, attention RNN,  Griffin-Lim reconstruction,*

### Variation of cepstral data

Ideal correction for speech is too ideal

Vesptral Variaition (To obtain mean 0, var 1)

- Cepstral Mean normalization/Vocal tract length vaiantion (VTLN) (*Do VTLN after the power spectrum before mel-warping*)
- Variance Normalization

Histogram variation

Temporal Varartion

- features: volocities (deltas), acceletation (double-delta), direction

### Spectral-Characteristic (VTLN) based Estimation

- Wraping the frequency axis
- Can combine VTLN and Mel wraping together into a single step

Formants have distinctive spectral characteistics (trajectories).\
Pitch-tracking for F0, formant tracking for F1(speaker), F2, F3(breathy and criky sounds, not important for speech recogniation)

### Distrubution-based Estimation - GMM

- For each speaker, find a warping functionst that maps to the cononical(e.g. an average) speaker's distribution

## Noise

Noise may be reduced from spectrual subtraction (used in the magnitude spectrum(square root of power spectrum)\
In the speech pipeline, do speech reduction in the magnitude and then obtian the denoised power spectrum.

Tell Gerald about what I like and don't like about the course by email.