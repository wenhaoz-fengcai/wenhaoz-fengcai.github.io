---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

[Download CV](http://wenhaoz.io/files/Resume.pdf)

Education
======
* Ph.D in Computer Science, University of California, Los Angeles (currently enrolled)
* M.S. in Computer Science, University of Southern California, 2015
* M.S. in Electrical Engineering, University of Southern California, 2017
* B.S. in Electrical Engineering, Harbin Engineering University, 2013



Work experience
======
* Summer 2019: Research Intern @ Alibaba Group
  * Identified the selection bias and data sparsity issues in conventional conversion rate (CVR) estimation
  * Proposed two theoretically unbiased CVR estimators, i.e., Multi-IPW, and Multi-DR, which solves these issues from a causal perspective.
  * Evaluated the proposed models on a public dataset and a production dataset (with 10 Billion data samples), and the results reveal that the proposed method outperform the state-of-the-art CVR models.
  * Drafted paper ”Large-scale Causal Approaches to Debiasing Post-clickConversion Rate Estimation with Multi-taskLearning”, and submitted it to The Web Conference 2020.

Open-source contributions
=====

* Contributions to [Scikit-learn](https://scikit-learn.org/stable/)
  * Solved the compatibility issue with python 3.7.0b5 in version 0.19.2 (Merged pull request [#11256](https://github.com/scikit-learn/scikit-learn/pull/11256))
  * Added a new interface in model selection module (sklearn.model selection) in version 0.21.0. This feature adds more flexibility in identifying the best estimator. (Merged pull requestion [#11354](https://github.com/scikit-learn/scikit-learn/pull/11354))
* Contribution to [wkdict](https://pypi.org/project/wkdict/)
  * Published a dictionary app that sits in CLI enviroment


Publications
======
  <ul>{% for post in site.publications %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
<!-- Talks
======
  <ul>{% for post in site.talks %}
    {% include archive-single-talk-cv.html %}
  {% endfor %}</ul> -->
  
Teaching
======
  <ul>{% for post in site.teaching %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>


<!-- Skills
======
* Programming skills
  * Python
  * Java
  * Ocaml
  * Prolog
  * Scheme
  * C -->
  
<!-- Service and leadership
======
* Currently signed in to 43 different slack teams -->
