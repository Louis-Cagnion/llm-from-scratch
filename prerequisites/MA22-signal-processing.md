# MA22. Signal processing

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Mathematics | 5. Applied mathematics | MA06, MA07, MA11, MA08 | none directly (used by L14, L32, L63 to L66) |

## Why this module

Rotary position embeddings assign a frequency to each pair of dimensions, and extending a model's context (NTK scaling, YaRN) is reasoning about wavelengths. JPEG images are stored as discrete cosine transforms, convolutions appear in vision encoders and in Mamba, and resizing an image without artifacts requires sampling theory. This module gives the frequency view of signals.

## Objectives

After this module, you can analyze signals in time and frequency, compute discrete Fourier and cosine transforms by hand and with a fast algorithm, use convolutions, and resample signals without aliasing.

## Competences evaluated

1. Describe periodic signals by frequency, period, phase and amplitude, and decompose them into sines and cosines.
2. Compute Fourier series coefficients of simple periodic functions.
3. Compute the discrete Fourier transform of a short sequence by hand, and its inverse, using roots of unity.
4. Explain the fast Fourier transform (Cooley-Tukey, divide and conquer) and its O(n log n) cost.
5. Compute the discrete cosine transform and explain why it compacts energy (basis of JPEG).
6. Compute discrete convolutions and correlations, state the convolution theorem, and use it to convolve with the FFT.
7. Design simple filters (moving average, low-pass) and interpret their frequency response.
8. State the sampling theorem, explain aliasing, and choose a resampling filter for downscaling.
9. Relate rotary position embeddings to frequencies and wavelengths, and explain what changing the base or interpolating positions does to them.

## Notions, in learning order

1. **Signals**: continuous and discrete signals, periodic signals, sinusoids, complex exponentials (from MA06).
2. **Fourier series**: coefficients, convergence (informally), spectra.
3. **Discrete Fourier transform**: definition with roots of unity, inverse, properties (linearity, shifts, symmetry).
4. **Fast Fourier transform**: radix-2 Cooley-Tukey, cost.
5. **Discrete cosine transform**: definition, energy compaction, 2D DCT on image blocks.
6. **Convolution and correlation**: discrete definitions, properties, the convolution theorem.
7. **Filters**: impulse response, frequency response, low-pass and high-pass filters.
8. **Sampling**: the sampling theorem, aliasing, anti-aliasing, resampling filters.
9. **Frequencies in Transformers**: sinusoidal position encodings, rotary embeddings as rotations at different frequencies, wavelengths and context extension.

## Practice

- DFT and convolution computations by hand on sequences of length 4 and 8.
- Explaining on paper what happens to the wavelengths of rotary embeddings when the context is doubled.
- Once IN06 is validated: a recursive FFT written from scratch and checked against the direct DFT, a 2D DCT applied to an 8 × 8 block, and a resampling experiment that shows aliasing on a synthetic image, written to an SVG or to a hand-encoded image file later.

## Evaluation format

One written session, about 2 hours: around 12 exercises covering every competence, including one DFT by hand and one aliasing analysis. Pass mark 100 %.

## References

- Alan V. Oppenheim and Ronald W. Schafer, *Discrete-Time Signal Processing* (book, not free).
- Steven W. Smith, *The Scientist and Engineer's Guide to Digital Signal Processing* (free book).
- Jianlin Su et al., *RoFormer: Enhanced Transformer with Rotary Position Embedding* (2021, free paper).
