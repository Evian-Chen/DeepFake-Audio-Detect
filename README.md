# DeepFake Audio Detection 
## Overview
This is a small project of stanCode SC201 poster session done in January 2023. Also, it's done by four members: Ching-yuan Pai, Yipin Peng, Andy Chen and me. We tried to build a model that can detect the authenticity of an audio file. The whole presentation of this project was also recorded and uploded on stanCode official YouTube account.

## Dataset - ASVspoof2019
ASVspoof is a challenge hold in bi-annual which aim to promote the design of contermeasure to protect automatic speaker verification system from manipulation. 
> The ASVspoof 2019 database encompasses two partitions for the assessment of logical access (LA) and physical access (PA) scenarios. Both are derived from the VCTK base corpus which includes speech data captured from 107 speakers (46 males, 61 females). Both LA and PA databases are themselves partitioned into three datasets, namely training, development and evaluation which comprise the speech from 20 (8 male, 12 female), 10 (4 male, 6 female) and 48 (21 male, 27 female) speakers respectively. The three partitions are disjoint in terms of speakers, and the recording conditions for all source data are identical. While the training and development sets contain spoofing attacks generated with the same algorithms/conditions (designated as known attacks), the evaluation set also contains attacks generated with different algorithms/conditions (designated as unknown attacks). 

(excerpted from ASVspoof 2019 README.txt) 

## Methodology
* Firstly, we converted FLAC file to WAV file and used pytorch module to generate waveform and spectrogram, which characterizes in three features: frequency, time and intensity. Those features can be shown by varying the color or brightness.
![image](https://github.com/Evian-Chen/DeepFake-Audio-Detect/blob/main/PA_T_0005450.png)
![image](https://github.com/Evian-Chen/DeepFake-Audio-Detect/blob/main/PA_T_0006390.png)

* Since this dataset contains 200,000 audio files, we found it extreamly time-consuming to load to G-drive, so we unzipped the folder on colab to avoid run-time error.
* After, we set up two models for LA and PA dataset respectively.
  * For LA dataset, we built a VGG-like model, which is 27 layers, to train and successfully achieved the accuracy of 91%.
  * For PA dataset, we use ResNet50, which can be pre-trained by 1000 classifications dataset, and it achieved the accuracy of 95%.

## references
<a href="https://arxiv.org/abs/1512.03385">Deep Residual Learning for Image Recognition</a>

<a href="https://www.asvspoof.org/database">ASVspoof2019 Dataset</a>

<a href="https://youtu.be/EPhzvGlP_jY?si=Kdd6X0hgM7Wltv59"> poster recording </a>
