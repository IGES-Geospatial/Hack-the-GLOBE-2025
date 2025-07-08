# Hack-the-GLOBE-2025
A collection of work by participants in The University of Texas at Austin's [STEM Enhancement in Earth Science (SEES)](https://www.csr.utexas.edu/education-outreach/high-school-internships/sees/) Hack the GLOBE research experience, 2025. Participants explored, analyzed, and characterized citizen science data from the GLOBE Program in a fast-paced 2-week collaborative crash course in data science. (2025-06-20 through 2025-07-03)

## Overview

**<ins>Problem Statement</ins>**\
In an era of unprecedented data generation, grappling with noisy "big data" has become a central challenge across industries and a key demand on contemporary data scientists: moving beyond mere statistical grouping and noise reduction to sophisticated characterization techniques identifying data clusters that are both mathematically distinct and intuitively understandable and justifiable. These methods not only flag poor quality data but also distinguish meaningful patterns and even interpret noise as signatures of underlying systemic issues. This allows organizations to build more robust and reliable data-driven systems.\
This endeavor is particularly complex when dealing with geolocated data, which carries inherent noise and uncertainty due to collection methods, and when the data's origin and instrumentation are not fully transparent. The inherent inaccuracies and variability of the source geolocated data mean that coordinates cannot be treated as perfectly precise. This necessitates a fundamental shift from exact point-based analysis to approaches that can accommodate or quantify uncertainty, such as appropriately normalized and scaled probabilistic or density-based methods, or by explicitly incorporating uncertainty into distance metrics.\

**<ins>Goal</ins>**\
To expose student participants to modern data science workflows, tools, and mental heuristics in order to empower them to tackle some of the toughest challenges - minimally structured problem spaces with lots of data of uncertain veracity. A hands-on experience to build discretion, critical thinking, and the willingness to re-evaluate one's own interpretations and progress towards a desired objective. Throughout, emphasis is placed on reproducibility, documentation of approaches and findings, and recognizing the utility of interpretable flags to capture and guide their own work and the work of future researchers. The aim of this particular Hack the GLOBE research experience is to serve as a model or template for collaborative analytical efforts that are transferrable to other datasets.

**<ins>Research Experience Objectives</ins>**\
The project is structured around several key objectives to equip students with a robust skillset:

- Mastering Data Quality Assessment and Remediation for Messy Geolocated Data: Students will acquire the skills to diagnose and address common data quality issues, including nulls, outliers, and inconsistencies, with a specific emphasis on their manifestations within spatial datasets, embedded within the context of an iterative data science investigation.
- Familiarization with data profiling and exploratory analytical techniques, and their applicability to unknown datasets.
- Applying Advanced Clustering Techniques: Participants will explore and select clustering algorithms best suited for spatial data characterized by complex structures and inherent noise.
- Developing Interpretable Explanations: A significant focus will be placed on methodologies that enable clear articulation of why specific data points have been flagged, why they may belong to certain unique clusters and how to summarize defining characteristics of a dataset.
- Generating Actionable Data Quality Flags: The key deliverable requires participants to create a repeatable process for assigning interpretable data quality flags to individual observations, thereby reflecting their reliability and highlighting potential issues.

**<ins>Main Deliverables</ins>**\
Well-documented and repeatable code products (in the form of Python Notebooks) that assign interpretable data characterization flags to individual observations, thereby reflecting data reliability and highlighting potential issues. The notebooks themselves will generally follow the following structure:\
- Loading the data
- Data Profiling
- Handling null values
- Characterization of coordinate uncertainty
- Metadata augmentation
- Identifying outliers
- Evaluating inter-column relationships
- Normalization and scaling
- Dimensionality Reduction
- Unsupervised clustering algorithms
- Interpretable flagging

Any one of these stages has sufficient depth and breadth to become the focus of a team's data science research project - and the differences between those chosen foci will be reflected in the final notebooks that are submitted. Collectively, all phases will be addressed and the integration of the whole will provide an even more comprehensive view of the dataset.

## Repository Structure

**<ins>./inputs</ins>**\
A flattened/wide view consisting of 64 columns and 10 tables extracted from the GLOBE database adjacent to the Surface Temperature protocol, with duplicated or sensitive information removed. There are ~725000 rows of data, each representing a single sample collected while following the [GLOBE Surface Temperature Protocol](https://www.globe.gov/web/atmosphere/protocols/surface-temperature). (~12MB .parquet file: mv_surface_temperatures_wide.parquet)

**<ins>./inputs/custom/</ins>**\
Some participants utilized additional datasets to augment their analyses. For easy reproducibility, those datasets have been included in this repository.

**<ins>./notebooks</ins>**\
Participant-generated .ipynb notebook files, developed in response to the proposed problem statement.

**<ins>./outputs</ins>**\
Outputs generated by the notebooks.

**<ins>./scaffolding</ins>**\
A selection of background resources developed and provided to participants.

## Explore the notebooks in a cloud-deployed environment
Participant-submitted notebooks have minimally modified to reference filepaths relative to this repository's structure for easy exploration in the cloud.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/IGES-Geospatial/Hack-the-GLOBE-2025/blob/main)\
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/IGES-Geospatial/Hack-the-GLOBE-2025/main)
*n.b. - the free MyBinder environment, as defined by environment.yml is RAM limited and may not permit easy exploration, but is included for complete reference.

## Future Outputs
- An aggregated analysis notebook synthesized from the combined efforts of all submissions.
- DOI-referenceable archival snapshot of repository (via Zenodo) with authorship credit assigned to contributors via their ORCiD
