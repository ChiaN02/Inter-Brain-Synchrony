# Inter-Brain Synchrony with fNIRS and GSR

*Bachelor's Thesis in Biomedical Engineering, University of Pisa, Academic Year 2024/2025*

How the brain activity of two people synchronizes when they **cooperate** or **compete**, measured with **fNIRS** and **GSR**.

**Author:** Chiara Nasoni

**Supervisor:** Prof. Alberto Greco · **Co-supervisor:** Ing. Gianluca Rho

## 📄 Documents

- [`THESIS.pdf`](THESIS.pdf): full thesis (in Italian)
- [`PRESENTATION.pdf`](PRESENTATION.pdf): slides of the thesis defence (in Italian)

## 🔎 What it is about

When people interact, their physiological signals (breathing, heart rate, skin conductance, brain activity) tend to align. This is called **interpersonal physiological synchrony (IPS)**, and it can tell us something about empathy and cooperation in a more objective way than questionnaires.

The usual tools for measuring it on several people at once (EEG, ECG, fMRI) have limits: noise, low spatial resolution, high costs or information limited to the heart.

The thesis analyses the study by Park et al. (2022), the first to combine:

- **fNIRS** (functional near-infrared spectroscopy), to measure brain activity in the prefrontal cortex
- **GSR** (galvanic skin response), to measure the activity of the autonomic nervous system through skin conductance

## 🧪 The experiment

- 56 participants in 28 pairs of strangers (9 male-male, 11 male-female, 8 female-female), separated by a barrier
- Cognitive tasks at three difficulty levels: **easy** (press for odd numbers), **2-back** and **3-back**
- Two interaction modes:
  - **Cooperation**: both participants press the button at the same time, within 0.1 s
  - **Competition**: each participant tries to press before the other
- fNIRS recorded with a NIRSIT LITE headband (15 channels on the prefrontal cortex)
- GSR recorded with a Shimmer sensor on the index and middle finger of the right hand

## ⚙️ Analysis

| Signal | Processing | Metric |
|---|---|---|
| fNIRS | ΔHbO, band-pass Butterworth filter to remove breathing and heartbeat artifacts | **RIBS** (Relative Inter-Brain Synchronization): Wavelet Transform Coherence during the task compared to rest |
| GSR | Low-pass filter | **aGSR**: mean skin conductance during the task |

Statistics: linear mixed-effects models (difficulty, gender pairing and their interaction as fixed effects, pair as random effect), α = 0.05, FDR correction across channels.

## 📊 Results

- **Cooperation**: brain synchrony grows with task difficulty, with significant effects on channels Ch01, Ch02, Ch04, Ch06 and Ch14
- **Competition**: no significant effect of difficulty or gender pairing on brain synchrony
- **GSR**: difficulty has no significant effect, while gender pairing does in both modes (p < 0.001)

Limits: familiarity between participants is not considered, and the controlled setting leaves no room for spontaneous interaction.

**Brain synchrony is not just mental workload: it grows with the need to coordinate with the other person.**

## 📚 Main reference

Park, J., Shin, J., Jeong, J. (2022). *Inter-brain synchrony levels according to task execution modes and difficulty levels: an fNIRS/GSR study.* IEEE Transactions on Neural Systems and Rehabilitation Engineering, 30, 194-204.
