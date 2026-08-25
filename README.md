# MexHat: A Dataset for Hate Speech Detection in Mexican Spanish Videos

We release MexHat, a video dataset designed to capture the linguistic and cultural cues for the hate-speech detection task in a Mexican Spanish context. Our dataset comprises around 1k video clips annotated across two tasks: 

+ A **three-way class** evaluation (no negative content, offensive content, and hate-speech content)
+ A **fine-grained class** evaluation including three hate-speech sub-categories

*Disclaimer: This dataset contains sensitive content that may be disturbing to some people.*

## Table of Contents
´´´

´´´

## Dataset Details


### Statistics
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

### Examples

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
