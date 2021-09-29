# Steam BiT: match Steam Banners with Google's BiT

This repository contains Python code to retrieve Steam games with similar store banners, using [Google's BiT][goog-bit-blog].

Image similarity is assessed by the cosine similarity between image features encoded by BiT.

![Similar vertical banners][wiki-cover]

## Model

BiT is a convolutional neural network based on a ResNet architecture:
- pre-trained for classification on ImageNet-1k (1.28M images with 1000 classes) for `BiT-S`, 
- pre-trained for classification on ImageNet-21k (14M images with ~21k classes) for `BiT-M`.

In this repository, the image encoder is a `BiT-R50x1` model, which results from the distillation of a `BiT-M-R152x2`.

## Data

Data consists of **vertical** Steam banners (300x450 resolution), resized to 256x384 resolution.

This is performed with [`rom1504/img2dataset`][img2dataset-github].

## Usage

- To download image data, run [`download_steam_webdataset.ipynb`][download_steam_webdataset-notebook].
[![Open In Colab][colab-badge]][download_steam_webdataset-notebook]

Alternatively, you can find the data as `v0.1` in the ["Releases" section][github-releases] of this repository.

- To match images, run [`match_steam_banners_with_BiT.ipynb`][match_steam_banners_with_BiT-notebook].
[![Open In Colab][colab-badge]][match_steam_banners_with_BiT-notebook]

## References

-   Google's Big Transfer (BiT):
    - [Official blog post][goog-bit-blog]
    - [Official Github repository][goog-bit-code]
    - [Kolesnikov, Alexander, et al. *Big Transfer (BiT): General Visual Representation Learning*. ECCV 2020.][goog-bit-paper]
    - [Beyer, Lucas, et al. *Knowledge distillation: A good teacher is patient and consistent*. arXiv 2021.][goog-bit-distillation-paper]
-   A generic repository to match images:
    - [`match-steam-banners`][banner-repository-generic]: retrieve games with similar banners,
-   My usage of Facebook's DINO:
    - [`steam-DINO`][banner-repository-DINO]: retrieve games with similar banners, using Facebook's DINO (resolution 224),
-   My usage of OpenAI's CLIP:
    - [`steam-CLIP`][banner-repository-CLIP]: retrieve games with similar banners, using OpenAI's CLIP (resolution 224),
    - [`steam-image-search`][natural-language-search]: retrieve games using natural language queries,
    - [`heroku-flask-api`][my-flask-API]: serve the matching results through an API built with Flask on Heroku.

<!-- Definitions -->

[wiki-cover]: <https://github.com/woctezuma/steam-BiT/wiki/img/illustration.jpg>
[download_steam_webdataset-notebook]: <https://colab.research.google.com/github/woctezuma/steam-BiT/blob/main/download_steam_webdataset.ipynb>
[match_steam_banners_with_BiT-notebook]: <https://colab.research.google.com/github/woctezuma/steam-BiT/blob/main/match_steam_banners_with_BiT.ipynb>

[github-releases]: <https://github.com/woctezuma/steam-BiT/releases>
[img2dataset-github]: <https://github.com/rom1504/img2dataset>

[goog-bit-blog]: <https://ai.googleblog.com/2020/05/open-sourcing-bit-exploring-large-scale.html>
[goog-bit-code]: <https://github.com/google-research/big_transfer>
[goog-bit-paper]: <https://arxiv.org/abs/1912.11370>
[goog-bit-distillation-paper]: <https://arxiv.org/abs/2106.05237>

[banner-repository-generic]: <https://github.com/woctezuma/match-steam-banners>

[banner-repository-DINO]: <https://github.com/woctezuma/steam-DINO>

[banner-repository-CLIP]: <https://github.com/woctezuma/steam-CLIP>
[natural-language-search]: <https://github.com/woctezuma/steam-image-search>
[my-flask-API]: <https://github.com/woctezuma/heroku-flask-api>

[colab-badge]: <https://colab.research.google.com/assets/colab-badge.svg>
