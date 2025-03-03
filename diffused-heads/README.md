# Diffused Heads 

### [Project](https://mstypulkowski.github.io/diffusedheads/) | [Paper](https://arxiv.org/abs/2301.03396) | [Demo](https://youtu.be/DSipIDj-5q0)

## Setup
Python 3.x environment with [ffmpeg](https://www.ffmpeg.org/) is needed. The rest of the requirements can be installed using:
```
pip install -r requirements.txt
```

## Sampling
Due to LRW license agreement, we are only able to provide a checkpoint of our model trained on CREMA.

The entire test set generated by our method can be downloaded from [here](https://drive.google.com/file/d/1zWSqtV7O4WGkgh6WB55b8Mdg2lXXUudH/view?usp=drive_link).


1. Download and unpack [checkpoints](https://drive.google.com/file/d/1U90egQvzERHclTYPCjZadrEMyF7TAPa-/view?usp=drive_link) (our model and pretrained audio encoder).
   
2. Download and unpack preprocessed CREMA [video](https://drive.google.com/file/d/1rM0FZLGiy-bJcxpv4CTlbUf0FuROubdk/view?usp=drive_link) and [audio](https://drive.google.com/file/d/1uS7Vi8EwarJFGQhsYHDMSkQmaNuiJIVW/view?usp=drive_link) files.
   
3. Specify paths and options in `config_crema.yaml` (check comments in the file).
   
4. Run the script
```
python sample.py
```


## Using your own data
### Audio
You can use audio recordings of your choosing freely. The only requirements are 16 kHz audio rate and a single audio channel. Please note our model is able to generate videos up to 9 seconds long depending on the audio.

### Identity frame
It is highly recommended to use a frame from the provided CREMA videos. This instance of the model was trained on clips with green background only. If you want to use your identity frame anyway, please follow this [repo](https://github.com/DinoMan/face-processor) for face alignment. Additionally, you may want to try segmenting the person and replacing background to green.

## Training
The training code can be found in the branch [train](https://github.com/MStypulkowski/diffused-heads/tree/train). We aplogize for the delay.

## Citation
```
@inproceedings{stypulkowski2024diffused,
  title={Diffused heads: Diffusion models beat gans on talking-face generation},
  author={Stypu{\l}kowski, Micha{\l} and Vougioukas, Konstantinos and He, Sen and Zi{\k{e}}ba, Maciej and Petridis, Stavros and Pantic, Maja},
  booktitle={Proceedings of the IEEE/CVF Winter Conference on Applications of Computer Vision},
  pages={5091--5100},
  year={2024}
}
```

## License
This work is licensed under a
[Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License][cc-by-nc-sa].

[![CC BY-NC-SA 4.0][cc-by-nc-sa-image]][cc-by-nc-sa]

[cc-by-nc-sa]: http://creativecommons.org/licenses/by-nc-sa/4.0/
[cc-by-nc-sa-image]: https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png
[cc-by-nc-sa-shield]: https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg
