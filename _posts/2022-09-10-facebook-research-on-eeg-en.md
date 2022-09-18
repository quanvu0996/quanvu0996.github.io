---
title: '[En] Facebook's research on decoding speech from EEG (English below)'
date: 2022-09-10
permalink: /posts/en/2022/09/db_research_on_decoding_speech_from_eeg/
tags:
  - EEG
  - Neuroscience
  - Speech decoding
  - English
---

![Facebook research on EEG and speed](/images/post/2022_fb_research_eeg.jpeg){: width="500" }<br>
At the end of August, Facebook/Meta's AI team published a preprint of their research on brain electrical signals (electroencephalogram-EEG).

Speech is a complex activity of intelligence, so studies of how speech is processed in the brain often has to be worked with invasive EEG signals. Skull surgery is needed to place electrodes directly into the brain. This method is somewhat horrible and cannot be widely spread. However, non-invasive EEG signals, measured in the scalp, are often very noisy and weak, and there are differences between individuals, even between sessions of the same person. .
Facebook's research takes a significant step forward in decoding speech from non-invasive EEG signals. The network architecture uses wav2vec 2.0, contrastive training with the CLIP loss function, and notably a set of CNN layers superimposed on Subject layers. The subject layer is described as performing per-electrode parameterization on Fourier space.
Hopefully the source code of this article will be published soon.

Link: [https://lnkd.in/gBhVHBKj](https://lnkd.in/gBhVHBKj)