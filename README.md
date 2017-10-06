# Arctic Lichen Dataset 

Welcome to the raw dataset of Arctic Lichens! :seedling: :snowflake:

This dataset contains small snippets from the Arctic Circle landscape around Kilpisjarvi in the north of Finland, focusing on the hundreds of lichens lying right under our feet.

Currently Ciaran is using it to create a system of musical notation as a means of understanding the Arctic environment as part of his [Ars Bioarctica Residency](https://bioartsociety.fi/projects/ars-bioarctica).

You can read more about the process of data collection and how this came about [here](www.ciaranframe.com/blog/arctic1).

Data is *not* stored in this repo - the Zenodo link will become avaliable at the completion of the project.

Dataset current version is **version 1.0**.


## Data structure

### Storage

- data
    - Lichen summary file 
   
    - Subfolders 001 - nnn
	    - Base Lichen Image
	    - 360° Photosphere Image
	    - Context Image
	    - Context Video
	    - Lichen Layers
		    - Individual lichen layers
		    - Lichen layers summary file <br />
    - Misc.
        - audio
        - image


### Data folder contents (`data`)

At the top of this file structure, there is an **attributes text file** (`lichenId_attr.txt`), which summarises the various discrete points that have been sampled across the landscape. Every discrete point has been assigned a **Lichen ID**, an arbitrary unique identifier. Attributes are assigned on a line-by-line basis as follows:<br />

| Attribute     | Pos.         | Len.|Type|Description |
|:------------- |:------:| :-----:| :-----:|:-------------|
|ID | 1 | 3 | I| Unique arbitrary identifier
| Position Latitude | 4 | 8 | I| Latitude to six decimal places
| Position Longditude | 12 | 8 | I| Longditude to six decimal places
| Date sampled | 20 | 8 | I| yyyymmdd
| Scale of base image  | 28 |  6 | I | Actual length in mm of base image width
| Direction of base image  | 34 |  3 | I | Camera heading in degrees
| Direction of lichen face  | 37 |  3 | I | Lichen surface heading in degrees
| Angle of lichen face  | 40 |  3 | I | Lichen angle degrees
| Biome | 43 | 20 | A| Environment/biome found in
| Notes | 63 | 200 | A| Any other notes


This file is also stored and formatted as a coll file (`lichenId_attr.coll`) for use in Max/MSP.

Subfolders `001` - `nnn` store data associated with each specific lichen, as outlined below.

### Subfolder contents (`001` - `nnn`)

Each subfolder contains the following:

**Base Lichen Image** (`lichenId_base.jpg`) <br />
The base 1920 x 1080 .jpeg file of lichen that all supporting data is based on. Often this will be a small section of a large surface area of lichen. This image also forms the foundation of Ciaran's musical notation.

**360° Photosphere Image** (`lichenId_360.jpg`) <br />
A 4608 × 2304 panoramic 360°  .jpeg file created using Google StreetView App. This image provides context of the environment in which the lichen exists. Further access to these spheres can be acheived through Jeremy Heleine's [Photo Sphere Viewer](https://github.com/JeremyHeleine/Photo-Sphere-Viewer).

**Context Image** (`lichenId_contextImg.jpg`) <br />
A simple 3024 × 4032 unedited .jpeg file that provides a basic amount of environmental context in which the lichen exists.

**Context Video** (`lichenId_contextVid.mp4`) <br />
A 1920 x 1080 50 FPS unedited .mp4 file of 30 seconds or shorter (with low quality audio) that provides environmental context in which the lichen exists.

**Lichen Layers** (subfolder `lichenId_layer`) <br />
This folder contains
 
* Each individual lichen layer found in the **base lichen image** as an individual 1920 x 1080 .png file with 1920 x 1080 transparency active. Each layer is named `lichenId_layer_001` through `lichenId_layer_nnn` 
* A single associated text file named `lichenId_layer_attr.txt` that describes each of the layers as follows:

| Attribute     | Pos.         | Len.|Type|Description |
|:------------- |:------:| :-----:| :-----:|:-------------|
|ID | 1 | 3 | I| Unique arbitrary layer identifier (refers to .png layer)
| Scientific Name | 4 | 40 | I| Sicentific name of lichen layer
| Common Name | 44 | 40 | I| Sicentific name of lichen layer

* This file is also stored and formatted as a coll file (`lichenId_layer_attr.coll`) for use in Max/MSP.

### Misc folder contents (`misc`)

**Audio** 

Outher audio samples
`audio_attr.txt`

**Image** 

Other images
`image_attr.txt`



