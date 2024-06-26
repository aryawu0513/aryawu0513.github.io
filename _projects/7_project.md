---
layout: page
title: Creative Tracklist Generation
description: Final Project for MIT 6.8610 Quantitative Methods for Natural Language Processing
img: assets/img/songtrack.jpg
importance: 3
category: course projects
---

{% include figure.liquid loading="eager" path="assets/img/songtrack_poster.jpg" title="Example Image" class="img-fluid rounded z-depth-1" %}

<!-- <img src="assets/songtrack_poster.jpg" alt="Poster"> -->

<br>
This study proposes and evaluates&nbsp;models capable of generating song titles given the name of an&nbsp;album. Our goal is to contribute to the evolving landscape of&nbsp;NLP applications in the music industry, offering a creative tool&nbsp;for content generation and exploring novel possibilities for&nbsp;enhancing the artistic process.&nbsp;<br>
<br>
Our research adopts a multifaceted approach to address the challenge of&nbsp;generating song titles from album names, leveraging state-of-the-art language&nbsp;models for creative text generation.<br>

1. GPT-2 with Prompt Engineering:<br>
   The initial phase employs the GPT-2 language model with prompt engineering&nbsp;to directly generate song titles. Training data consists of album name-track&nbsp;name tuples obtained from Last.FM APIs. The GPT-2 model is fine-tuned on this&nbsp;dataset, and various prompts are experimented with to enhance title diversity.<br>

2. T5-GPT-2 Narrative Framework:<br>
   Recognizing the limitations of recurring themes in GPT-2, the second phase&nbsp;attempts to enrich the narrative context by leveraging a T5 model fine-tuned on&nbsp;commongen. With T5, we transform track listings into sentences, which serves&nbsp;as a narrative context mapped with each album’s name. A GPT-2 model is then&nbsp;trained on this dataset, and prompted to produce more varied and contextually&nbsp;rich outputs that are decoded back into a list of song titles.<br>

<br>
