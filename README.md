# MexHat: A Dataset for Hate Speech Detection in Mexican Spanish Videos

We release MexHat, a video dataset designed to capture the linguistic and cultural cues for the hate-speech detection task in a Mexican Spanish context. Our dataset comprises around 1k video clips annotated across two tasks: 

+ A **three-way class** evaluation (no negative content, offensive content, and hate-speech content)
+ A **fine-grained class** evaluation including three hate-speech sub-categories

*Disclaimer: This dataset contains sensitive content that may be disturbing to some people.*

## Table of Contents

+ [Data Collection](#data-collection)
+ [Annotation](#annotation)
  + [Instance Examples](#instance-examples)
+ [MexHat](#mexhat)
+ [Extracted Features](#extracted-features)
+ [Paper cite](#paper-cite)

## Data Collection

The videos were filtered and retrieved from the YouTube platform. Three ways of filtering were applied:

1. using hate-speech related words
2. using relevant identified videos as seeds to retrieve similar content
3. identifying playlists of channels with possible hate-speech content

Code available at [https://github.com/iltocl/dcc-hsdvmi-video-dataset](https://github.com/iltocl/dcc-hsdvmi-video-dataset)

## Annotation

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

### Instance Examples
#### not-negative content

![not-negative content](/images/nn_example_frames.PNG)

*transcription*: Hoy yo estoy muy segunda generación. No, solo es horrible. Entre más atrevido y moderno te vieras, era como que estabas entendiendo más la asignatura. A finales de la segunda generación es donde vemos los primeros acercamientos del K-Pop a la moda de lujo. Los primeros idols en captar el interés de estos diseñadores fueron nada menos que CL y G-Dragon. CL tuvo un intercambio muy cercano con Jeremy Scott casi desde el debut de 2NE1 y se convirtió en una de sus musas. En 2013 diseñó los vestuarios para el World Tour de 2NE1.
G-Dragon por su lado trabajó de cerca con Chanel hasta convertirse en embajador de la marca. Y a partir de aquí, es historia. Ahora tenemos más que normalizado y vemos por todos lados a qué idols siendo musas y embajadores de diversas marcas de moda. La segunda generación fueron años de completa experimentación para el K-Pop, resultando en el boom de la industria. Escribieron las reglas y regustucieron las bases para el futuro del género y de la exposición internacional del entretenimiento coreano. En este video quise enfocarme meramente en tocar algunos aspectos creativos, pero por el lado comercial hay un mundo fácil. 

#### negative content
![negative content](/images/of_example_frames.PNG)

*transcription*: ya wey no mames bájale por eso ya ya no la guasía a lo de los bebés no llores bueno porque si pega pero al final de cuentas mira ellos son hermanos ellos pueden ser cariño de siempre yo mi jefa no la tengo a ver niño cuál es el color de la mierda de la caca no es porque a veces cuando estoy enfermo sale así que su puta madre la concha de la... en quién no confiarías si le tuvieras que dar trabajo a alguien a quién se lo dabas a ver niño este es el malo este tiene una pistola te va a saltar va a matar a tu familia a todos amigos va a matar con esta pistola este es el color de diosito de dios en el que crees que te va a matar ¿cuál crees? ¿cuál crees que te va a saltar?

#### hate-speech content
![not-negative content](/images/hs_example_frames.PNG)

*transcription*: Hola soy Bob y junto a mis dos asistentes Charlie y Bert me dedico a construir, restaurar y reparar todo tipo de cosas. Es un trabajo arduo pero alguien tiene que hacerlo. Bob el constructor El día de hoy vino un cliente con la intención de que remodeláramos su casa, ya la vi y el resultado puedo decirles va a quedar fenomenal, es de los casos más sencillos que hemos tenido y gracias a mi equipo de trabajo podremos terminarlo en unos dos o tres días. El día de hoy vine con mi amigo Bob a que chequee mi casa porque quiere unas remodelaciones, la verdad confío mucho en su trabajo, es el mejor. Mi casa necesita remodelaciones, está muy mal la verdad, mira. ¡Guau! Es la casa más culera que he visto. Sí está bien culera. Ni los marranos podrían vivir ahí. ¿Cómo vives en esa posible? Hasta el color es horrible, ¿quién la pintó? ¿un ciego? ¿Quién era Shrek? ¿Pasó un huracán ahí? Shrek vive en un pantano y vive mejor que tú. Me parece que eres re pobre, si tienes para pagar las remodelaciones. Pero bueno, ¿qué dicen chicos? ¿podemos hacerlo?

## MexHat 

The MexHat pkl file is available: [mexhat.pkl](https://drive.google.com/file/d/1gk_B1_2mlQWI94fqFplYC1nTaOGukjES/view?usp=drive_link). The data format corresponds to:

```
key: train
  └── sub_key: vision
  └── sub_key: audio
  └── sub_key: text
  └── sub_key: labels # three-way class
  └── sub_key: labels_hs # fine-grained class
  └── sub_key: labels_bin # these labels were not used for evaluation yet
  └── sub_key: id
key: valid
  └── sub_key: vision
  └── sub_key: audio
  └── sub_key: text
  └── sub_key: labels # three-way class
  └── sub_key: labels_hs # fine-grained class
  └── sub_key: labels_bin # these labels were not used for evaluation yet
  └── sub_key: id
key: test
  └── sub_key: vision
  └── sub_key: audio
  └── sub_key: text
  └── sub_key: labels # three-way class
  └── sub_key: labels_hs # fine-grained class
  └── sub_key: labels_bin # these labels were not used for evaluation yet
  └── sub_key: id
```


## Extracted Features

For each video scene **T**ext, **V**ideo and **A**udio modality features were extracted. 

### Raw Video Scenes
We provide the raw video scenes

### Text
To obtain text modality features, audio was transcribed from the video using [whisper](https://github.com/openai/whisper.git) *(model=“medium”)*. 
Then, transcribed text was processed with [BETO](https://huggingface.co/dccuchile/bert-base-spanish-wwm-uncased) encoder.

### Video
For the video modality, [I3D](https://v-iashin.github.io/video_features/models/i3d/) representations for flow and rgb were obtained. 

### Audio
Audio features were obtained by using the [vggish](https://v-iashin.github.io/video_features/models/vggish/) pretrained model.

### Temporal Dimension Processing
We used a Long Short Term Memory (LSTM) network, followed by an AdaptiveAvgPool1d layer and a Linear fully connected (FC) layer to standardize temporal dimension n to $n = 50$ for all modalities and video clips.

# Paper cite
´´´

´´´
