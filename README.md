# RELATE dataset

## Contents

This dataset consists of the following contents:

- Audio–text pairs

	This dataset includes 2,862 audio–text pairs for training and 7,000 audio–text pairs for validation.
	Each text is written English.
	All audio sample was converted to mono 16-bit 16 kHz audio.

- 11-point semantic-alignment scores between audio and text by each listener

	This dataset includes subjective evaluation scores for semantic alignment between audio and text.
	The semantic-alignment score is on a scale of eleven from 0 (does not match at all.) to 10 (matched exactly).
	Each audio–text pair is evaluated by four listeners, who are native English speakers.

- Average-semantic-alignment scores
	
	This dataset includes average-semantic aligment scores of each audio–text pair.

- Listener ID

	This dataset includes listener IDs who scored the semantic-alignment score between audio and text.

## Download

To download the dataset, please send an email to dataset@xacle.org.
When you send the email, please include "Download dataset" in the subject line.
You can obtain the dataset immediately via an automated reply.


   評価件数 & 9,963 & 7,797 & 7,641 & 5,865 & 4,017 & 2,943\\
    説明文・環境音ペア& 2,862 & 2,598 & 2,649 & 2,334 & 1,281 & 1,185\\
    音の長さ [s] & 28,806 & 26,129 & 26,654 & 23,476 & 12,880 & 11901\\
    聴取者数 & 1,085 & 873 & 864 & 635 & 714 & 525\\
    \wcline{1-7}

## Statistics
![statistics](images/stats_RELATE.png)
|  REL | IS | OS|
|  | Train | Test | Train | Test | Train | Test |
| :--- | ---: | ---: | ---: | ---: | ---: | ---: |
| Evaluations | 9,963 |  7,797 | 7,641 | 5,865 | 4,017 | 2,943 |
| Audio–text pairs | 2,862 |  2,598 | 2,649 | 2,334 | 1,281 | 1,185 |
| Audio duration [s] | 28,806 | 26,129 | 26,654 | 23,476 | 12,880 | 11901 |
| Listeners | 1,085 | 873 | 864 | 635 | 714 | 525|


| | REL | | IS | | OS | |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| | Train | Test | Train | Test | Train | Test |
| 評価件数 | 9,963 | 7,797 | 7,641 | 5,865 | 4,017 | 2,943 |
| 説明文・環境音ペア | 2,862 | 2,598 | 2,649 | 2,334 | 1,281 | 1,185 |
| 音の長さ [s] | 28,806 | 26,129 | 26,654 | 23,476 | 12,880 | 11,901 |
| 聴取者数 | 1,085 | 873 | 864 | 635 | 714 | 525 |

## File format

- [train,validation].csv: There are 4 columns in the each csv file.
	- wave_file_name: The file name of audio.
	- text: The text's corresponding audio.
	- 11-point semantic-alignment score: The evaluation scores for semantic alignment between audio and text by each listener.
	- listener_id: The listener ID who scored the sematic-alignment scores.

- [train_average,validation_average].csv: There are 3 columns in the each csv file.
	- wave_file_name: The file name of audio.
	- text: The text's corresponding audio.
	- average_semantic_alignement_score: The average semantic-alignment scores of each audio-text pair.

## Directory structure

The directory structure of this dataset is as follows:

	XACLE_dataset
	├── meta_data
	│   ├── train_average.csv
	│   ├── train.csv
	│   ├── validation_average.csv
	│   └── validation.csv
	└── wav
		├── train
		│   ├── 00000.wav
		│   ├── 00001.wav
		│   ├── 00002.wav
		│   ├── 	.
		│   ├── 	.
		│   └── 	.
		└── validation
			├── 07500.wav
			├── 07501.wav
			├── 07502.wav
			├── 	.
			├── 	.
			└── 	.

## Citation

Please cite the paper that will be uploaded to arXiv in early November, 2025.

## Acknowledgment

The work was supported by JSPS KAKENHI Grant Number 24K23880, 25K21221, JST Moonshot Grant Number JPMJMS2237.
