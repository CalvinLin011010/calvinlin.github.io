---
title: COLING 2024 paper sharing talk

event: the 2024 Joint International Conference on Computational Linguistics, Language Resources and Evaluation
event_url: https://lrec-coling-2024.org/

location: Lingotto Conference Centre - Torino (Italia)
address:
  street: Via Nizza, 280
  city: Torino
  region: TO
  postcode: '10126'
  country: Italia

summary: Recorded video of the pre-talk. The recorded video of the live speech will be officially released later.
abstract: 'Joint entity-relation extraction remains a challenging task in information retrieval, given the intrinsic difficulty in modelling the interdependence between named entity recognition (NER) and relation extraction (RE) sub-tasks. Most existing joint extraction models encode entity and relation features in a sequential or parallel manner, allowing for limited one-way interaction. However, it is not yet clear how to capture the interdependence between these two sub-tasks in a synergistic and mutually reinforcing fashion. With this in mind, we propose a novel approach for joint entity-relation extraction, named Synergetic Interaction Network (SINET) which utilizes a cross-task attention mechanism to effectively leverage contextual associations between NER and RE. Specifically, we construct two sets of distinct token representations for NER and RE sub-tasks respectively. Then, both sets of unique representation interact with one another via a cross-task attention mechanism, which exploits associated contextual information produced by concerted efforts of both NER and RE. Experiments on three benchmark datasets demonstrate that the proposed model achieves significantly better performance in joint entity-relation extraction. Moreover, extended analysis validates that the proposed mechanism can indeed leverage the semantic information produced by NER and RE sub-tasks to boost one another in a complementary way. The source code is available to the public online.'

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: '2024-05-23T16:00:00Z' 
date_end: '2024-05-23T17:00:00Z'
all_day: false

# Schedule page publish date (NOT talk date).
# publishDate: '2024-05-01T00:00:00Z'

authors:
  - admin

tags: []

# Is this a featured talk? (true/false)
featured: false

image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/bzdhc5b3Bxs)'
  focal_point: Right

#links:
#  - icon: twitter
#    icon_pack: fab
#    name: Follow
#    url: https://twitter.com/georgecushen
url_code: 'https://github.com/AONE-NLP/RTE-SINET'
url_pdf: 'https://aclanthology.org/2024.lrec-main.1343/'
url_slides: 'https://www.bilibili.com/video/BV1fwWweXEu6'
url_video: 'https://www.bilibili.com/video/BV1fwWweXEu6'

# Markdown Slides (optional).
#   Associate this talk with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects:
  - example
---


## Video

Recorded video of the pre-talk. The recorded video of the live speech will be officially released later.

{{< youtube BV1fwWweXEu6 >}}




