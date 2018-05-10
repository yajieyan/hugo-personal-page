+++
title = "Voxel Core: Computing Medial Axes in 3D"
date = 2018-05-09T23:22:09-05:00
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
We present a novel algorithm for computing the medial axes of 3D shapes. We make the observation that the medial axis of a voxel shape can be simply yet faithfully approximated by the interior Voronoi diagram of the boundary vertices, which we call the voxel core. We further show that voxel cores can approximate the medial axes of any smooth shape with homotopy equivalence and geometric convergence. These insights motivate an algorithm that is simple, efficient, numerically stable, and equipped with theoretical guarantees. Compared with existing voxel-based methods, our method inherits their simplicity but is more scalable and can process significantly larger inputs. Compared with sampling-based methods that offer similar theoretical guarantees, our method produces visually comparable results but more robustly captures the topology of the input shape.

[`pdf (author version)`](#), [`code`](#), [`readme`]({{<ref "project/voxelcore-readme.md">}})