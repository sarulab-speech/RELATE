# RELATE dataset

## Contents

This dataset consists of the following contents:

- Audio–text pairs

	This dataset includes a number of audio-text pairs shown in the table in statistics section below. The audios consist of both natural and synthetic types.
	Each text is written in English.
	All audio sample was converted to mono 16-bit 16 kHz audio.

- 11-point scores between audio and text by each listener

	This dataset includes three types of subjective evaluation scores for relevance between audio and text.
	- REL score: The overall relevance of the text and audio.
 	- Inclusion of sound event (IS) score: The extent to which the sound events described in the text are included in the audio.
  	- Order of sound event (OS) score: The degree of matching between the time series of sound events described in the text and the audio.

	The score is on a scale of eleven from 0 (does not match at all.) to 10 (matched exactly).
	Each audio–text pair is evaluated by four listeners on average, who are native English speakers.

- Listener attributes
  
  	For listener attributes, we gathered information such as age, gender, nationality, birthplace, residence, and experience in audio evaluation.
	The table below shows the questions and options.
	![listener_attributes](images/listener_attributes.png)


## Statistics
This table shows the statistics of RELATE dataset.
![statistics](images/stats_RELATE.png)


## Directory structure

The directory structure of this dataset is as follows:

	RELATE
	├── listener_attributes
	│   ├── REL.csv
	│   └── IS_and_OS.csv 
	└── scores
		├── REL.csv
		├── IS.csv 
		└── OS.csv

  	RELATE_wave
	├── audiocaps
	│   ├── test
 	│	│	├── 10176.wav
	│	│	├──   .
    │   │   ├──   .
    │	│   └──   .
	│   └── train
	├── audioldm
 	│	├── test
    │   └── train
 	├── audioldm2
   	│	├── test
    │   └── train
   	├── tango
	│	├── test
    │   └── train
	└── tango2
  	 	├── test
        └── train


## File format

- listener_attributes/[REL, IS_and_OS].csv: There are 13 columns in the each csv file.
	- listener_id: The file name of audio.
	- question[1, 2, ..., 12]: The answer of the question in questionnaire. The answes are quantified, with options assigned a numerical value starting from 1 for the leftmost choice and increasing sequentially.

- scores/REL.csv: There are 8 columns in the each csv file.
	- wavname: The file name of audio.
	- text: The text's corresponding audio.
	- score: The evaluation score. The score range is 0 to 10.
	- listener_id: The listener ID who scored the sematic-alignment scores.
    - audio type: Shows whether the audio is natural or synthetic. If synthetic, contains the name of synthetic model.
    - anchor label: Whether this is an anchor pair (irrelevant audio–text pair for screening) or not.
    - in RELATE dataset: Whether the pair belongs to the train set, validation set or test set in RELATE dataset. "Excluded" if that is an anchor pair or screened.
    - in AudioCaps: Whether the pair belongs to the train set or test set in AudioCaps. "None" if that is an anchor pair.
 
- scores/[IS, OS].csv: There are 7 columns in the each csv file.
	- wavname: The file name of audio.
	- text: The text's corresponding audio.
	- score: The evaluation score. The score range is 0 to 10.
	- listener_id: The listener ID who scored the sematic-alignment scores.
    - audio type: Shows whether the audio is natural or synthetic. If synthetic, contains the name of synthetic model.
    - anchor label: Whether this is an anchor pair (irrelevant audio–text pair for screening) or not.
    - in AudioCaps: Whether the pair belongs to the train set or test set in AudioCaps. "None" if that is an anchor pair.


## Download wave files
You can download wave files from [here](https://sarulab.sakura.ne.jp/kanamori/RELATE_open_dataset/RELATE_wave.zip)

## Screening of data
You can conduct screening of listeners according to the method in our paper.

```
import pandas as pd
df = pd.read_csv("scores/REL.csv")
df = df[df["in RELATE dataset"]!="excluded"]
```

## Citation

Kanamori, Y., Okamoto, Y., Takano, T., Takamichi, S., Saito, Y., Saruwatari, H. (2025) RELATE: Subjective evaluation dataset for automatic evaluation of relevance between text and audio . Proc. Interspeech 2025, 3155-3159, doi: 10.21437/Interspeech.2025-1830

## Acknowledgment

The work was supported by JSPS KAKENHI Grant Number 23K24895, 24K23880, 25K21221, JST Moonshot Grant Number JPMJMS2237.
