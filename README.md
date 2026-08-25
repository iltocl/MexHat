# MexHat: A Dataset for Hate Speech Detection in Mexican Spanish Videos

We release MexHat, a video dataset designed to capture the linguistic and cultural cues for the hate-speech detection task in a Mexican Spanish context. Our dataset comprises around 1k video clips annotated across two tasks: 

+ A **three-way class** evaluation (no negative content, offensive content, and hate-speech content)
+ A **fine-grained class** evaluation including three hate-speech sub-categories

*Disclaimer: This dataset contains sensitive content that may be disturbing to some people.*

## Table of Contents
´´´

´´´

## Dataset Details

### Data Collection

The videos were filtered and retrieved from the YouTube platform. Three ways of filtering were applied:

1. using hate-speech related words
2. using relevant identified videos as seeds to retrieve similar content
3. identifying playlists of channels with possible hate-speech content

Code available at [https://github.com/iltocl/dcc-hsdvmi-video-dataset](https://github.com/iltocl/dcc-hsdvmi-video-dataset)

### Annotation

The proposed partitions for the MexHat dataset are shown below:

| Partition | Total | NN | OF | HS | hs1 | hs2 | hs3 |
|-----------|-------|----|----|----|-----|-----|-----|
| test  | 278 | 116 | 123 | 39 | 6 | 15 | 18 |
| train | 824 | 394 | 314 | 116 | 28 | 47 | 41 |
| val   | 276 | 130 | 99 | 47 | 10 | 9 | 28 |
| ALL   | 1378 | 640 | 536 | 202 | 44 | 71 | 87 |

Classes

- NN: not-negative content
- OF: offensive content
- HS: hate speech content

Hate-speech sub classes
- hs1: racism, xenophobia
- hs2: sexism, LGBTQ+
- hs3: others

#### Instance Examples



### Extracted Features
#### Text
Whisper transcriptions
BETO embeddings
#### Video

rgb + flow 
#### Audio
VGGish

# Paper cite
´´´
@misc{mexhat2026,
  author = {},
  title = {MexHat: A Video Dataset for Hate Speech Detection},
  year = {2026},
  howpublished = {},
  note = {}
}   
´´´
