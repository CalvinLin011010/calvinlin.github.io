---
title: Synergistic Anchored Contrastive Pre-training for Few-Shot Relation Extraction
authors:
- Da Luo
- Yanglei Gan
- Rui Hou
- Run Lin
- Qiao Liu
- Yuxiang Cai
- Wannian Gao
date: '2024-03-01'
publishDate: '2024-08-17T19:17:41.879442Z'
publication_types:
- article-journal
publication: '*Proceedings of the AAAI Conference on Artificial Intelligence*'
doi: 10.1609/aaai.v38i17.29838

abstract: Few-shot Relation Extraction (FSRE) aims to extract relational facts from a sparse set of labeled corpora. Recent studies have shown promising results in FSRE by employing Pre-trained Language Models (PLMs) within the framework of supervised contrastive learning, which considers both instances and label facts. However, how to effectively harness massive instance-label pairs to encompass the learned representation with semantic richness in this learning paradigm is not fully explored. To address this gap, we introduce a novel synergistic anchored contrastive pre-training framework. This framework is motivated by the insight that the diverse viewpoints conveyed through instance-label pairs capture incomplete yet complementary intrinsic textual semantics. Specifically, our framework involves a symmetrical contrastive objective that encompasses both sentence-anchored and label-anchored contrastive losses. By combining these two losses, the model establishes a robust and uniform representation space. This space effectively captures the reciprocal alignment of feature distributions among instances and relational facts, simultaneously enhancing the maximization of mutual information across diverse perspectives within the same relation. Experimental results demonstrate that our framework achieves significant performance enhancements compared to baseline models in downstream FSRE tasks. Furthermore, our approach exhibits superior adaptability to handle the challenges of domain shift and zero-shot relation extraction. Our code is available online at https://github.com/AONE-NLP/FSRE-SaCon.

links:
- name: URL
  url: https://ojs.aaai.org/index.php/AAAI/article/view/29838

# links:
# - name: ""
#   url: ""
url_pdf: https://ojs.aaai.org/index.php/AAAI/article/view/29838
url_code: 'https://github.com/AONE-NLP/FSRE-SaCon'
url_dataset: ''
url_poster: 'https://ojs.aaai.org/index.php/AAAI/article/view/29838/31459'
url_project: ''
url_slides: ''
url_source: ''
url_video: ''
---
