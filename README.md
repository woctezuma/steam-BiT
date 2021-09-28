# Steam BiT: match Steam Banners with GOOG's BiT

This repository contains Python code to retrieve Steam games with similar store banners, using [Google's BiT][goog-bit-blog].

Image similarity is assessed by the cosine similarity between image features encoded by BiT.

![Similar vertical banners][wiki-cover]

## Data

Data consists of **vertical** Steam banners (300x450 resolution).

## Usage

Run [`match_steam_banners_with_BiT.ipynb`][match_steam_banners_with_BiT-notebook].
[![Open In Colab][colab-badge]][match_steam_banners_with_BiT-notebook]

## References

-   Google's Big Transfer (BiT):
    - [Official blog post][goog-bit-blog]
    - [Official Github repository][goog-bit-code]
    - [Kolesnikov, Alexander, et al. *Big Transfer (BiT): General Visual Representation Learning*. arXiv 2020.][goog-bit-paper]
    - [Beyer, Lucas, et al. *Knowledge distillation: A good teacher is patient and consistent*. arXiv 2021.][goog-bit-distillation-paper]
-   My usage of Facebook's DINO:
    - [`steam-DINO`][banner-repository-DINO]: retrieve games with similar banners, using Facebook's DINO (resolution 224),
-   My usage of OpenAI's CLIP:
    - [`steam-CLIP`][banner-repository-CLIP]: retrieve games with similar banners, using OpenAI's CLIP (resolution 224),
    - [`steam-image-search`][natural-language-search]: retrieve games using natural language queries,
    - [`heroku-flask-api`][my-flask-API]: serve the matching results through an API built with Flask on Heroku.

<!-- Definitions -->

[wiki-cover]: <https://github.com/woctezuma/steam-BiT/wiki/img/illustration.jpg>
[match_steam_banners_with_BiT-notebook]: <https://colab.research.google.com/github/woctezuma/steam-BiT/blob/main/match_steam_banners_with_BiT.ipynb>

[goog-bit-blog]: <https://ai.googleblog.com/2020/05/open-sourcing-bit-exploring-large-scale.html>
[goog-bit-code]: <https://github.com/google-research/big_transfer>
[goog-bit-paper]: <https://arxiv.org/abs/1912.11370>
[goog-bit-distillation-paper]: <https://arxiv.org/abs/2106.05237>

[banner-repository-DINO]: <https://github.com/woctezuma/steam-DINO>

[banner-repository-CLIP]: <https://github.com/woctezuma/steam-CLIP>
[natural-language-search]: <https://github.com/woctezuma/steam-image-search>
[my-flask-API]: <https://github.com/woctezuma/heroku-flask-api>

[colab-badge]: <https://colab.research.google.com/assets/colab-badge.svg>
