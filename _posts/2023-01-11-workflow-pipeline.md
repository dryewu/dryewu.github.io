---
layout: post
title:  Workflow for diffusion MRI
date:   2023-01-11
description: # march & april, looking forward to summer
tags: pipeline preprocessing baby
categories: projects
giscus_comments: true
---

# Table of contents
- [Table of contents](#table-of-contents)
  - [Automated processing pipeline for diffusion MRI ](#automated-processing-pipeline-for-diffusion-mri-)
  - [Computational medical imaging toolkit ](#computational-medical-imaging-toolkit-)
  - [Fast correction of eddy-current and susceptibility-induced distortions ](#fast-correction-of-eddy-current-and-susceptibility-induced-distortions-)

## Automated processing pipeline for diffusion MRI <a name="pipeline"></a>
Processing baby diffusion MRI (dMRI) data is challenging due to the low and spatially-varying diffusion anisotropy, rendering standard analysis techniques developed for adult data inapplicable [1,2]. Here, we present a fully-automated processing pipeline for baby dMRI, tailored particularly to the data collected in the Baby Connectome Project (BCP).  

The human brain is arguably the most complex system in biology and yet its macroscopic layout is nearly complete by the time of term birth. The infant brain develops rapidly during the ﬁrst years of life, posing signiﬁcant challenges to precise quantiﬁcation of rapid dynamic changes that occur during this critical period of brain development. 

The increasing availability of longitudinal baby MRI data, such as those acquired through the Baby Connectome Project (BCP) [3], affords unprecedented opportunity for precise charting of early brain developmental trajectories in order to understand normative and aberrant growth.

We describe here an automated processing pipeline for baby dMRI, consisting of (i) image quality control (IQC) for distinguishing between good and poor quality data, (ii) anatomy-guided correction for eddy-current and susceptibility-induced distortions, (iii) tissue microstructural analysis, and (iv) reconstruction of white matter (WM) pathways.  


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/post/2023-01-11-workflow-pipeline/pipeline1.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
     Overview of the baby dMRI processing pipeline.
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/post/2023-01-11-workflow-pipeline/pipeline2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    (a) The diffusion-weighted volumes of each subject are quality-annotated as “fail” (red), “questionable” (blue), or “pass” (green); (b-c) Longitudinal development of tissue microstructure in terms of ICVF and ECVF. 	
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/post/2023-01-11-workflow-pipeline/pipeline3.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
     FA, Color FA, and FODFs given by multi-tissue CSD [16] and the proposed method for a 54-day-old infant. Whole-brain tractogram given by FODF-based deterministic tractography (FODF DET) [17], tensor-based fiber assigned by continuous tracking (Tensor FACT) [18], FODF-based probabilistic tractography (FODF PROB) [19], and the proposed ASI-based tractography.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/post/2023-01-11-workflow-pipeline/pipeline4.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Histogram of the lengths of fiber streamlines across 190 scans from 0 to 5 years of age. The streamline length is normalized with respect to the brain size by dividing with the cube root of the brain volume.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/post/2023-01-11-workflow-pipeline/pipeline5.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Six challenging white matter pathways identified by our pipeline for a subject scanned longitudinally.
</div>

<blockquote>
Wu, Y., Ahmad, S., Huynh, KM., Liu, S., Thung, K-H., Lin, W. & Yap, P. T. (2021). 
An Automated Processing Pipeline for Diffusion MRI in the Baby Connectome Project
Proceedings of the International Society of Magnetic Resonance in Medicine (ISMRM)
<b>(Summa Cum Laude Award)</b>
</blockquote>

## Computational medical imaging toolkit <a name="toolkit"></a>
Processing and analyzing diffusion MRI (dMRI) data is important for uncovering the neural underpinnings of white matter (WM) development and degeneration across the human lifespan. Here, we introduce a robust and integrative toolkit, called Computational Medical Imaging (COMEDI), for processing, analyzing, and visualizing lifespan dMRI data.

Diffusion MRI (dMRI) is a primary tool for noninvasive and in vivo investigation of tissue microstructure and white matter (WM) pathways in the human brain1,2. Making sense of dMRI data often involves intensive processing, fine-grained analysis, and multi-perspective visualization. Despite the availability of many software packages for dMRI processing, few are effective for the entire human lifespan, particularly the first years of life where the diffusion characteristics are markedly different from adults. Here, we introduce a robust and integrative dMRI processing toolkit — Computational Medical Imaging (COMEDI) — that has been tested on dMRI data spanning the entire human lifespan from birth to 100 years of age. COMEDI covers recent advances in dMRI processing and analysis, including asymmetric fiber orientation distribution functions, cortico-cortical tractography with explicit consideration of gyral bias, advanced microstructural analysis, consistent bundle identification across the human lifespan, dedicated analysis pipelines for baby dMRI, and subject-specific whole-brain parcellation. COMEDI will be made publicly available as a non-commercial software package after the ISMRM meeting to support lifespan dMRI studies.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/post/2023-01-11-workflow-pipeline/toolkit1.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Software architecture and design. (a) Uniform I/O for reading/writing common medical image file formats. (b) Interoperable across multiple platforms. (c) Interfaces for integration with other libraries developed with different programming languages.
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/post/2023-01-11-workflow-pipeline/toolkit2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Example results generated with COMEDI: (a) Corticospinal tract; (b) Removal of false-positive streamlines; (c) Removal of outlier streamlines; (d) Streamline smoothing; (e) Hemispheric splitting; (f) Isotropic restricted diffusion; (g) Free water; (h) Anisotropic restricted diffusion; and (j-k) Structural connectivity.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/post/2023-01-11-workflow-pipeline/toolkit3.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Example results generated with COMEDI: (a) Whole-brain tractogram; (b) Slab tractogram visualization; (c) Fiber clustering; (d) Example fiber cluster; (e) Example short-association bundles; (f) Example fiber clusters; (g-h) Slice visualization with volumetric maps; (i) Mapping of endpoints on cortical surface; (j) Visualization of cortico-cortical networks; (k) Visualization of cortical labels; (l) Subcortical parcellation. 
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/post/2023-01-11-workflow-pipeline/toolkit4.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Example results generated with COMEDI: (a) Volume mesh visualization; (b) Multimodal visualization with auto-alignment; (c) Symmetric FODF glyphs; (d) Asymmetric FODF glyphs; (e) Colormaps; (f) Example symmetric and asymmetric FODF glyphs; (g) Chart visualization.
</div>


<blockquote>
Wu, Y., Ahmad, S. Huynh, KM., Xu T. & Yap, P. T. (2022). 
COMEDI: A Toolkit for Lifespan Computational Diffusion MRI
Proceedings of the International Society of Magnetic Resonance in Medicine (ISMRM)
</blockquote>

## Fast correction of eddy-current and susceptibility-induced distortions <a name="correction"></a>
Diffusion MRI (dMRI) is typically time consuming as it involves acquiring a series of 3D volumes, each associated with a wave-vector in q-space that determines the diffusion direction and strength. The acquisition time is further increased when “blip-up blip-down” scans are acquired with opposite phase encoding directions (PEDs) to facilitate distortion correction. In this work, we show that geometric distortions can be corrected without acquiring with opposite PEDs for each wave-vector, and hence the acquisition time can be halved. Our method uses complimentary rotation-invariant contrasts across shells of different diffusion weightings. Distortion-free structural T1-/T2-weighted MRI is used as reference for nonlinear registration in correcting the distortions. Signal dropout and pileup are corrected with the help of spherical harmonics. To demonstrate that our method is robust to changes in image appearance, we show that distortion correction with good structural alignment can be achieved within minutes for dMRI data of infants between 1 to 24 months of age.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/post/2023-01-11-workflow-pipeline/correction1.jpeg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Displacement fields associated with two opposite PEDs.
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/post/2023-01-11-workflow-pipeline/correction2.jpeg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    FA maps and non-DW images of the corrected dMRI data of an 18-month-old infant.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/post/2023-01-11-workflow-pipeline/correction3.jpeg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    White matter surface overlaid on the FA maps and T1w image of a 23-monthold infant.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/post/2023-01-11-workflow-pipeline/correction4.jpeg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Spherical mean images for different b-values for a 12-month-old infant subject. Image brightness is adjusted for each shell for visibility.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/post/2023-01-11-workflow-pipeline/correction5.jpeg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Spherical mean images after geometric and intensity correction of the dMRI data of a 12-months-old infant. Image brightness is adjusted for each shell for visibility.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/post/2023-01-11-workflow-pipeline/correction6.jpeg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Quantitative comparison between distortion correction methods.
</div>

<blockquote>
Ahmad, S., Wu, Y., Huynh, K. M., Thung, K. H., Lin, W., Shen, D., ... & UNC/UMN Baby Connectome Project Consortium. (2020,). 
Fast Correction of Eddy-Current and Susceptibility-Induced Distortions Using Rotation-Invariant Contrasts. 
In International Conference on Medical Image Computing and Computer-Assisted Intervention (pp. 34-43). Springer, Cham.
</blockquote>
