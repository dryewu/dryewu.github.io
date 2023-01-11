---
layout: page
title:  Computational Medical Imaging Toolkit
description: A Toolkit for Lifespan Computational Diffusion MRI
img: assets/img/project/COMEDI/fig.png
importance: 1
category: Software
---

    ---
    Wu, Y., Ahmad, S. Huynh, KM., Xu T. & Yap, P. T. (2022). 
    COMEDI: A Toolkit for Lifespan Computational Diffusion MRI
    Proceedings of the International Society of Magnetic Resonance in Medicine (ISMRM)
    ---

Processing and analyzing diffusion MRI (dMRI) data is important for uncovering the neural underpinnings of white matter (WM) development and degeneration across the human lifespan. Here, we introduce a robust and integrative toolkit, called Computational Medical Imaging (COMEDI), for processing, analyzing, and visualizing lifespan dMRI data. 

Diffusion MRI (dMRI) is a primary tool for noninvasive and in vivo investigation of tissue microstructure and white matter (WM) pathways in the human brain1,2. Making sense of dMRI data often involves intensive processing, fine-grained analysis, and multi-perspective visualization. Despite the availability of many software packages for dMRI processing, few are effective for the entire human lifespan, particularly the first years of life where the diffusion characteristics are markedly different from adults. Here, we introduce a robust and integrative dMRI processing toolkit --- Computational Medical Imaging (COMEDI) --- that has been tested on dMRI data spanning the entire human lifespan from birth to 100 years of age. COMEDI covers recent advances in dMRI processing and analysis, including asymmetric fiber orientation distribution functions, cortico-cortical tractography with explicit consideration of gyral bias, advanced microstructural analysis, consistent bundle identification across the human lifespan, dedicated analysis pipelines for baby dMRI, and subject-specific whole-brain parcellation. COMEDI will be made publicly available as a non-commercial software package after the ISMRM meeting to support lifespan dMRI studies.



<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/project/COMEDI/fig1.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Software architecture and design. (a) Uniform I/O for reading/writing common medical image file formats. (b) Interoperable across multiple platforms. (c) Interfaces for integration with other libraries developed with different programming languages.
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/project/COMEDI/fig2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Example results generated with COMEDI: (a) Corticospinal tract; (b) Removal of false-positive streamlines; (c) Removal of outlier streamlines; (d) Streamline smoothing; (e) Hemispheric splitting; (f) Isotropic restricted diffusion; (g) Free water; (h) Anisotropic restricted diffusion; and (j-k) Structural connectivity.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/project/COMEDI/fig3.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Example results generated with COMEDI: (a) Whole-brain tractogram; (b) Slab tractogram visualization; (c) Fiber clustering; (d) Example fiber cluster; (e) Example short-association bundles; (f) Example fiber clusters; (g-h) Slice visualization with volumetric maps; (i) Mapping of endpoints on cortical surface; (j) Visualization of cortico-cortical networks; (k) Visualization of cortical labels; (l) Subcortical parcellation. 
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/project/COMEDI/fig4.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Example results generated with COMEDI: (a) Volume mesh visualization; (b) Multimodal visualization with auto-alignment; (c) Symmetric FODF glyphs; (d) Asymmetric FODF glyphs; (e) Colormaps; (f) Example symmetric and asymmetric FODF glyphs; (g) Chart visualization.
</div>


