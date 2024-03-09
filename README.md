# DeepFake Audio Detection 
## Overview
This ia a project of stanCode SC201 poster session done in January 2023. We tried to build a model that can detect the authenticity of an audio file within one month. The whole presentation of this project was also recorded and uploded on stanCode official account.

## Dataset - ASVspoof2019
ASVspoof is a challenge hold in bi-annual which aim to promote the design of contermeasure to protect automatic speaker verification system from manipulation. 
> The ASVspoof 2019 database encompasses two partitions for the assessment of logical access (LA) and physical access (PA) scenarios. Both are derived from the VCTK base corpus which includes speech data captured from 107 speakers (46 males, 61 females). Both LA and PA databases are themselves partitioned into three datasets, namely training, development and evaluation which comprise the speech from 20 (8 male, 12 female), 10 (4 male, 6 female) and 48 (21 male, 27 female) speakers respectively. The three partitions are disjoint in terms of speakers, and the recording conditions for all source data are identical. While the training and development sets contain spoofing attacks generated with the same algorithms/conditions (designated as known attacks), the evaluation set also contains attacks generated with different algorithms/conditions (designated as unknown attacks). 

(excerpted from ASVspoof 2019 README.txt) 

## Methodolof
* Firstly, we converted FLAC file to WAV file, and use pytorch module to generate waveform and spectrumgram.

## references
<a href="https://www.asvspoof.org/database">ASVspoof2019 Dataset</a>

2023/1
