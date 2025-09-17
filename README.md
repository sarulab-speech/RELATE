# RELATE dataset

## Contents

This dataset consists of the following contents:

- Audio–text pairs

	This dataset includes a number of audio-text pairs shown in the table in statistics section below. The audios consist of both natural and synthetic types.
	Each text is written in English.
	All audio sample was converted to mono 16-bit 16 kHz audio.

- 11-point subjective evaluation scores between audio and text by each listener

	This dataset includes three types of subjective evaluation scores for relevance between audio and text.
	- REL score: The overall relevance of the text and audio.
 	- Inclusion of sound event (IS) score: The extent to which the sound events described in the text are included in the audio.
  	- Order of sound event (OS) score: The degree of matching between the time series of sound events described in the text and the audio.

	The score is on a scale of eleven from 0 (does not match at all) to 10 (matched exactly).
	Each audio–text pair is evaluated by four listeners on average, who are native English speakers.

- Listener attributes
  
  	For listener attributes, we gathered information such as age, gender, nationality, birthplace, residence, and experience in audio evaluation.
	The table below shows the questions and options.
	![listener_attributes](images/listener_attributes.png)

| ID | Question | Options |
|---|---|---|
| Q1 | Age | 0-20, 21-30, 31-40, 41-50, 51-60, 61- |
| Q2 | Gender | Male, Female, Non-binary |
| Q3 | What is your nationality? | Choose from pulldown |
| Q4 | Where are you from? | Choose from pulldown |
| Q5 | In which country do you live? | Choose from pulldown |
| Q6 | How many times have you participated in ratings of audio samples? | 0, 1, 2, 3, 4, 5- |
| Q7 | When did you last participate in other ratings of audio samples? | Never, 0-1 month ago, 1-2 months ago, 2-6 months ago, <br>7-12 months ago, 1-5 years ago, Longer ago |
| Q8 | On average, how many times have you heard an audio repeatedly? | 1, 2, 3, 4, 5- |
| Q9 | What type of audio device did you use? | Headphone, Earphone, Others |
| Q10 | Was the surrounding environment quiet during the ratings of audio samples? | Quiet&nbsp;the&nbsp;whole&nbsp;time, Quiet&nbsp;most&nbsp;of&nbsp;the&nbsp;time, Sometimes&nbsp;quiet, Noisy&nbsp;most&nbsp;of&nbsp;the&nbsp;time, Always&nbsp;noisy |
| Q11 | How difficult were the evaluations? | Easy, Not so difficult, Not so easy, Difficult |
| Q12 | Do/did you work in the field of speech or audio technology? | Yes, No |


## Statistics
This table shows the statistics of RELATE dataset.
![statistics](images/stats_RELATE.png)
| | **REL** | | **IS** | | **OS** | |
|---|---|---|---|---|---|---|
| | Train | Test | Train | Test | Train | Test |
| Evaluations | 9,963 | 7,797 | 7,641 | 5,865 | 4,017 | 2,943 |
| Audio-text pairs | 2,862 | 2,598 | 2,649 | 2,334 | 1,281 | 1,185 |
| Audio duration [s] | 28,806 | 26,129 | 26,654 | 23,476 | 12,880 | 11,901 |
| Listeners | 1,085 | 873 | 864 | 635 | 714 | 525 |

<style>
  /* 表の罫線全体を太くする */
  table.custom-table, .custom-table th, .custom-table td {
    border: 2px solid black;
  }
  /* 特定の列の左の線を太くする */
  .custom-table th:nth-child(2), .custom-table td:nth-child(2) {
    border-left: 2px solid black;
  }
  /* 最初の行の下の線を太くする */
  .custom-table tr:first-child {
    border-bottom: 2px solid black;
  }
</style>

<table class="custom-table">
  <thead>
    <tr>
      <th></th>
      <th>**REL**</th>
      <th></th>
      <th>**IS**</th>
      <th></th>
      <th>**OS**</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td></td>
      <td>Train</td>
      <td>Test</td>
      <td>Train</td>
      <td>Test</td>
      <td>Train</td>
      <td>Test</td>
    </tr>
    <tr>
      <td>Evaluations</td>
      <td>9,963</td>
      <td>7,797</td>
      <td>7,641</td>
      <td>5,865</td>
      <td>4,017</td>
      <td>2,943</td>
    </tr>
    </tbody>
</table>

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
	│   ├── train
 	│	│	├── 10176.wav
	│	│	├──   .
    │   │   ├──   .
    │	│   └──   .
	│   └── test
	├── audioldm
 	│	├── train
    │   └── test
 	├── audioldm2
   	│	├── train
    │   └── test
   	├── tango
	│	├── train
    │   └── test
	└── tango2
  	 	├── train
        └── test


## File format

- listener_attributes/[REL, IS_and_OS].csv: There are 13 columns in the each csv file.
	- listener_id: The listener ID who scored the subjective evaluation scores.
	- question[1, 2, ..., 12]: The answer of the question in questionnaire. The answes are quantified, with options assigned a numerical value starting from 1 for the leftmost choice and increasing sequentially.

- scores/REL.csv: There are 8 columns in the each csv file.
	- wavname: The file name of audio.
	- text: The text's corresponding audio.
	- score: The evaluation score. The score range is 0 to 10.
	- listener_id: The listener ID who scored the subjective evaluation scores.
    - audio type: Shows whether the audio is natural or synthetic. If synthetic, contains the name of synthetic model.
    - anchor label: Whether this is an anchor pair (irrelevant audio–text pair for screening) or not.
    - in RELATE dataset: Whether the pair belongs to the train set, validation set or test set in RELATE dataset. "Excluded" if that is an anchor pair or screened.
    - in AudioCaps: Whether the pair belongs to the train set or test set in AudioCaps. "None" if that is an anchor pair.
 
- scores/[IS, OS].csv: There are 7 columns in the each csv file.
	- wavname: The file name of audio.
	- text: The text's corresponding audio.
	- score: The evaluation score. The score range is 0 to 10.
	- listener_id: The listener ID who scored the subjective evaluation scores.
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
df.to_csv("scores/REL_screened.csv", index=False)
```

## Citation
```
Y. Kanamori, Y. Okamoto, T. Takano, S. Takamichi, Y. Saito, H. Saruwatari, "RELATE: Subjective evaluation dataset for automatic evaluation of relevance between text and audio," Proc. INTERSPEECH 2025, pp. 3155-3159, 2025, doi: 10.21437/Interspeech.2025-1830.
```

## Acknowledgment

The work was supported by JSPS KAKENHI Grant Number 23K24895, 24K23880, 25K21221, JST Moonshot Grant Number JPMJMS2237.
