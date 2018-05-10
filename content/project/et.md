+++
title = "Erosion Thickness: Simplifying Medial Axes in 3D"
date = 2018-05-09T23:22:19-05:00
draft = false

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["medial-axis"]

# Project summary to display on homepage.
summary = ""

# Optional image to display on homepage.
image_preview = ""

# Optional external URL for project (replaces project detail page).
external_link = ""

# Does the project detail page use math formatting?
math = true

# Does the project detail page use source code highlighting?
highlight = true

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
[header]
image = ""
caption = ""

+++

## Abstract
While playing a fundamental role in shape understanding, the medial axis is known to be sensitive to small boundary perturbations. Methods for pruning the medial axis are usually guided by some measure of significance. The majority of significance measures over the medial axes of 3D shapes are locally defined and hence unable to capture the scale of features. We introduce a global significance measure that generalizes in 3D the classical Erosion Thickness (ET) measure over the medial axes of 2D shapes. We give precise definition of ET in 3D, analyze its properties, and present an efficient approximation algorithm with bounded error on a piecewise linear medial axis. Experiments showed that ET outperforms local measures in differentiating small boundary noise from prominent shape features, and it is significantly faster to compute than existing global measures. We demonstrate the utility of ET in extracting clean, shape-revealing and topology-preserving skeletons of 3D shapes.

[`pdf (author version)`](#) [`code`](#), [`readme`](#)