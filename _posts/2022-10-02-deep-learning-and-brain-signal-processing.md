---
title: '[En] Can deep learning conquer brain signal processing?'
date: 2022-10-02
permalink: /posts/en/2022/10/deep-learning-and-brain-signal-processing/
tags:
  - EEG
  - Neuroscience
  - Deep learning
  - English
---

![Poster](/images/post/dl_and_eeg.jpeg){: width="800" }<br>
Deep learning (DL), the science based on the idea of how the brain works. 
Since Hinton claimed that he understood how the brain works and invented deep learning, the related sciences have changed their approaches dramatically. In 2012, the AlexNet, developed by Hinton's students, achieved SOTA results in image processing. Since then, traditional image feature extraction methods have gradually been forgotten. Nowaday, when someone talks about image processing, people immediately think of large-scale deep learning networks with stacked CNN layers.

Until 2016, Deep learning had a strong development, conquering many fields and becoming famous thanks to the event that AlphaGo beat humans in the game of Go. Ironically, it is still an unfamiliar term in its origin, neuroscience. Brain-computer interfaces (BCI) is a promising area of ​​neuroscience and is also the name of a very comprehensive book series on brain signal processing. Two sets of BCI books, volume 1 and volume 2, were released by WILEY in 2016, with 4 chapters on brain signal processing, 1 chapter on machine learning applications. But, they have no word about DL.

DL gradually proved itself in EEG research in the following years. In 2017, Akara et al. introduced DeepSleepNet. They demonstrate that without using any manual data preprocessing, signal processing, or specialized sleep knowledge, DL models can achieve accuracy comparable to traditional expert-based models. Their model just purely uses CNN, RNN layers. Methods that combine signal processing and DL are also of interest. In 2020 Nicolas et al. introduced Recurrent Event Detector (RED) architecture with 2 versions RED-time and RED-CWT. RED-Time uses CNN layers with small kennels for local feature extraction and feeds into Bidirectional LSTM for time course learning. RED-CWT has a similar architecture but adds a Continuous Wavelet Transform layer to the input to extract time-frequency information. The experimental results of these two models have basically similar performances.

As with image processing, the new DL-based models gradually eliminate the need for domain knowledge. In 2020, the research team from the University of Zurich (Skorucak et al.) still uses the expertise of brain waves such as alpha and beta waves and detects the theta/alpha ratio as a golden feature for predicting micro-sleeps. The same research group by 2021 has published a new study, using only CNN techniques, residual connection, etc. pure DL techniques and giving much superior results.

In 2021 the Facebook research group (Chehab, Defossez et al.) also published a study in learning the characteristics of MEG signals. All they use are LSTM layers sandwiched between the CNN and CNN transpose layers. Upgrading this study, Defossez et al. recently published their research using DL. We've come very close to understanding how the brain reflects speech.

Finally, in 2021, WILEY also published Call for Book Chapter with a new title for volume 3 of the BCI: Using Deep Learning Applications series. In the future, researchers in BCI and neuroscience would have to have a greater understanding of deep learning, perhaps even more than anatomy or biology.


REFERENCES
-----

Maureen Clerc, Laurent Bougrain, Fabien Lotte (2016), Brain–Computer Interfaces 1: Foundations and Methods, Print ISBN:9781848218260, Online ISBN:9781119144977, DOI:10.1002/9781119144977

Maureen Clerc, Laurent Bougrain, Fabien Lotte (2016), Brain-Computer Interfaces 2: Technology and Applications, ISBN: 978-1-848-21963-2

Supratak, Akara & Dong, Hao & Wu, Chao & Guo, Yike. (2017). DeepSleepNet: a Model for Automatic Sleep Stage Scoring based on Raw Single-Channel EEG. IEEE Transactions on Neural Systems and Rehabilitation Engineering. PP. 10.1109/TNSRE.2017.2721116. 

Tapia-Rivas, Nicolás & Estevez, Pablo. (2020). RED: Deep Recurrent Neural Networks for Sleep EEG Event Detection. 	arXiv:2005.07795 

Jelena Skorucak, Anneke Hertig-Godeschalk, David R Schreier, Alexander Malafeev, Johannes Mathis, Peter Achermann, Automatic detection of microsleep episodes with feature-based machine learning, Sleep, Volume 43, Issue 1, January 2020, zsz225, https://doi.org/10.1093/sleep/zsz225

Malafeev A, Hertig-Godeschalk A, Schreier DR, Skorucak J, Mathis J and Achermann P (2021) Automatic Detection of Microsleep Episodes With Deep Learning. Front. Neurosci. 15:564098. doi: 10.3389/fnins.2021.564098

Chehab, Omar & Defossez, Alexandre & Loiseau, Jean-Christophe & Gramfort, Alexandre & King, Jean-Rémi. (2021). Deep Recurrent Encoder: A scalable end-to-end network to model brain signals. 

Défossez, Alexandre & Caucheteux, Charlotte & Rapin, Jérémy & Kabeli, Ori & King, Jean-Rémi. (2022). Decoding speech from non-invasive brain recordings. 

Wiley-BCI-2021: Brain-Computer Interface: Using Deep Learning Applications, Call for Book Chapter - Scrivener Publishing - WILEY, https://easychair.org/cfp/WILEY-BCI2021