+++
title = "Voxelcore Readme"
date = 2018-05-08T19:10:35-05:00
draft = false

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["hide"]

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
## Pipeline
************************
{{< figure alt="fig-pipeline" src="/img/vc-pipeline.png" title="Figure 1. Pipeline." >}}

The program can be used to generate a voxelcore for either a given volume (representing a solid shape), or a triangular mesh (representing the surface of a shape) via voxelization. The pipeline is visualized in Figure 1. 


## Preparing input
************************
Input of voxelcore program can be a binary volume (in format .mrc / .sog), or a triangular mesh representing the surface of a shape. The object voxels in the volume should have values > 0, while background voxels <= 0. The pipeline is shown in [Figure 1]({{<relref "#fig-pipeline">}}).

MRC is a standard format for representing 3D CT images. SOG format is a sparse octree representation.

### Convert to MRC
If the user only has a stack of images (e.g. png, tiff), the images need to be preprocessed into a MRC file in the following ways:

- **Interactive programs** such as Paraview and Chimera can open stack of images in common formats, resulting in a volume dataset within the program. This voluem can be then saved as a mrc file.
- **Command line utilities** are available, but only accept certain image formats. For example the [IMOD package](http://bio3d.colorado.edu/imod/doc/program_listing.html#TOP) offers a command line program called *tif2mrc* that converts a stack of tiff images to a mrc file. The user would need to convert their images to tiff to use this utility.
- **Python scripts** can be written to convert datasets represented in even wider input formats to MRC. E.g. [pydicom](https://pydicom.github.io/) can easily parse input in DICOM format, and [mrcfile](https://github.com/ccpem/mrcfile) can write data out to a MRC file.

### Convert to SOG
- **Voxelcore** program itself can produce a SOG file from a MRC file in mode `mrc2sog`:
`voxelcore -md=mrc2sog -mrc=mrc_file_path -sog=sog_output_path`
The original mrc can be deleted if the user has no other intention with it, since the sog file contains complete information about the volume.
- **Polymender** can be used to produce a SOG file from the given triangular mesh (route 2 in Figure 1) (see [Polymender](http://www.cs.wustl.edu/~taoju/code/polymender.htm), or [download the program](http://www.cs.wustl.edu/~taoju/code/PolyMender_1_7_1_exe.rar) and see the readme.txt).


## Producing voxelcore (VC)
************************
### Route 1: from volume to VC
In mode `-md=vol2ma`, the program will read in the specified volume file [figure]({{<ref "#fig-pipeline">}})
### Route 2: from mesh to VC