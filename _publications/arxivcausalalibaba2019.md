---
title: "Large-scale causal approaches to debiasing post-click conversion rate estimation with multi-task learning"
collection: publications
permalink: /publication/arxivcausalalibaba2019
date: 2020-04-20
venue: 'Proceedings of The Web Conference 2020'
paperurl: 'https://dl.acm.org/doi/pdf/10.1145/3366423.3380037'
---
Post-click conversion rate (CVR) estimation is a critical task in e-commerce recommender systems. This task is deemed quite chal- lenging under industrial setting with two major issues: 1) selection bias caused by user self-selection, and 2) data sparsity due to the rare click events. A successful conversion typically has the following sequential events: "exposure → click → conversion". Conventional CVR estimators are trained in the click space, but inference is done in the entire exposure space. They fail to account for the causes of the missing data and treat them as missing at random. Hence, their estimations are highly likely to deviate from the real values by large. In addition, the data sparsity issue can also handicap many indus- trial CVR estimators which usually have large parameter spaces.
In this paper, we propose two principled, efficient and highly effective CVR estimators for industrial CVR estimation, namely, Multi-IPW and Multi-DR. The proposed models approach the CVR estimation from a causal perspective and account for the causes of missing not at random. In addition, our methods are based on the multi-task learning framework and mitigate the data sparsity issue. Extensive experiments on industrial-level datasets show that our methods outperform the state-of-the-art CVR models.