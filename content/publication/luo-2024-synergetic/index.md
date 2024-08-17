---
title: Synergetic Interaction Network with Cross-task Attention for Joint Relational
  Triple Extraction
authors:
- Da Luo
- Run Lin
- Qiao Liu
- Yuxiang Cai
- Xueyi Liu
- Yanglei Gan
- Rui Hou
date: '2024-05-01'
publishDate: '2024-08-17T19:33:19.537342Z'
publication_types:
- paper-conference
publication: '*Proceedings of the 2024 Joint International Conference on Computational
  Linguistics, Language Resources and Evaluation (LREC-COLING 2024)*'
abstract: Joint entity-relation extraction remains a challenging task in information
  retrieval, given the intrinsic difficulty in modelling the interdependence between
  named entity recognition (NER) and relation extraction (RE) sub-tasks. Most existing
  joint extraction models encode entity and relation features in a sequential or parallel
  manner, allowing for limited one-way interaction. However, it is not yet clear how
  to capture the interdependence between these two sub-tasks in a synergistic and
  mutually reinforcing fashion. With this in mind, we propose a novel approach for
  joint entity-relation extraction, named Synergetic Interaction Network (SINET) which
  utilizes a cross-task attention mechanism to effectively leverage contextual associations
  between NER and RE. Specifically, we construct two sets of distinct token representations
  for NER and RE sub-tasks respectively. Then, both sets of unique representation
  interact with one another via a cross-task attention mechanism, which exploits associated
  contextual information produced by concerted efforts of both NER and RE. Experiments
  on three benchmark datasets demonstrate that the proposed model achieves significantly
  better performance in joint entity-relation extraction. Moreover, extended analysis
  validates that the proposed mechanism can indeed leverage the semantic information
  produced by NER and RE sub-tasks to boost one another in a complementary way. The
  source code is available to the public online.

# links:
# - name: ""
#   url: ""
url_pdf: https://aclanthology.org/2024.lrec-main.1343
url_code: 'https://github.com/AONE-NLP/RTE-SINET'
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# links:
# - name: URL
#   url: https://aclanthology.org/2024.lrec-main.1343
---
