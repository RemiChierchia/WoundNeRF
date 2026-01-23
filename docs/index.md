---
layout: single
author_profile: True
classes: wide
excerpt: "Multi-View Consistent Wound Segmentation With Neural Fields<br/>ISBI 2026"
header:
  overlay_image: #/assets/images/main.png
  overlay_filter: 0.5
  caption: #"Qualitative evaluation of six 3D surface reconstruction methods using our SALVE dataset."
  actions:
    - label: "Paper"
      url: #
    - label: "Code will be released soon."
    #   url: "https://github.com/lebrat/Syn3DWound"
gallery_2v3d:
  - url: /assets/images/2v3d_poster.png
    image_path: /assets/images/2v3d_poster.png
    alt: "Area measurement multi-view inconsistent if rely only on 2D."
    title: "Area measurement multi-view inconsistent if rely only on 2D."
gallery_acquisition:
  - url: /assets/images/acquisition_setup.png
    image_path: /assets/images/acquisition_setup.png
gallery_accuracy:
  - url: /assets/images/accuracy.png
    image_path: /assets/images/accuracy.png
gallery_qualitative1:
  - url: /assets/images/qualitative_iphone_sd_small_2.png
    image_path: /assets/images/qualitative_iphone_sd_small_2.png
gallery_qualitative2:
  - url: /assets/images/qualitative_logitech_pis3_small_2.png
    image_path: /assets/images/qualitative_logitech_pis3_small_2.png
# gallery_pipepline:
#   - url: /assets/images/explaination_pipeline.png
#     image_path: /assets/images/explaination_pipeline.png
#     alt: "From a 3D mesh avatar and segmented wound, Syn3DWound allows to generate a synthetic dataset for 3D wound bed analysis."
#     title: "From a 3D mesh avatar and segmented wound, Syn3DWound allows to generate a synthetic dataset for 3D wound bed analysis."
# gallery_airplane:
#   - url: /assets/images/avion_mongenet.png
#     image_path: /assets/images/avion_mongenet.png
#     alt: "MongeNet mesh discretization by a point cloud"
#     title: "MongeNet mesh discretization by a point cloud"
#   - url: /assets/images/avion_uniform.png
#     image_path: /assets/images/avion_uniform.png
#     alt: "Standard random uniform mesh discretization by a point cloud"
#     title: "Standard random uniform mesh discretization by a point cloud"
paginate: true 
---

## Wbsite coming soon...

<!-- ## Introduction & Motivation
<b>Chronic wounds</b> represent a significant <b>health</b> and <b>economic</b> <b>burden</b> worldwide. Effective treatments <b>require</b> wound clinical <b>measurements</b>, typically <b>performed manually</b> by specialized healthcare professionals.

Wound surface area is typically measured by performing <b>planimetry</b> of the wound bed. These procedures are not only <b>invasive</b> and cause patient <b>discomfort</b> but are also prone to errors due to <b>ambiguous</b> definitions of metrics and variations in professionals’ skill levels.
<!-- Put image -->

<!-- Most <b>existing</b> automatic commercial <b>approaches</b> compute wound measurements solely from <b>2D images</b>, which are perspective-dependent. -->
<!-- put image -->
<!-- {% include gallery id="gallery_2v3d" caption="Area measurement multi-view inconsistent if rely only on 2D." %}

<b>3D analysis</b> of wounds allows for the computation of <b>richer wound biomarkers</b>. However, studies in this direction only considered previous generation 3D reconstruction frameworks, which have recently been surpassed by highly optimized photogrammetric toolboxes and recent neural rendering alternatives, we are talking about <b>NeRF</b> and <b>Gaussian Splatting</b>! -->
<!-- put image? -->

<!-- <b>We introduce</b> a new dataset <b>SALVE</b>, designed to capture common challenges encountered in clinical settings.
It is composed of <b>3</b> silicon phantoms provided by [TraumaSIM](https://traumasim.com.au/) representing <b>common wound types</b>.
We captured videos using <b>2 devices</b> with different image quality and resolution.
To capture 3D <b>ground-truth pointclouds</b> we used the Revopoint POP 3D scanner. -->
<!-- put image -->
<!-- {% include gallery id="gallery_acquisition" caption="Acquisition setup." %}

## Evaluation
<b>We evaluate</b> robust <b>photogrammetry pipelines</b> such as COLMAP and Meshroom and <b>modern neural rendering approaches for 3D reconstruction</b> such as <b>NeRF</b> and <b>Gaussian Splatting</b>.  -->
<!-- put image -->

<!-- We follow a <b>rigorous evaluation protocol</b> that defines metrics and procedures to assess the <b>geometric accuracy and precision</b> of the evaluated reconstruction algorithms. -->
<!-- put image -->
<!-- {% include gallery id="gallery_accuracy" caption="Meshroom, Neuralangelo, and Neus-facto consistently outperform other
methods across various metrics, wound types, and recording devices. Neuralangelo and Neus-facto demonstrate advantages over Meshroom.
Neus-facto reports the best performance in the inter-device evaluation, showing the
most consistent reconstructions." %}

{% include gallery id="gallery_qualitative1" caption="Photogrammetric pipelines often estimate noisy surfaces, due to challenges in stereo matching.
Similarly, Gaussian splatting approaches encounter difficulties due to the Gaussians’
initialization based on the SfM pointcloud." %}
{% include gallery id="gallery_qualitative2" caption="Notablty, Neuralangelo reconstruction’s quality drastically decreases in lower device
quality." %} -->


<!-- Page under developmet! -->






<!-- commented below> -->

<!-- <br/> -->

<!-- <b>If you find this work useful, please cite</b> -->
<!-- ```
@InProceedings{Chierchia_2025_WACV,
    author    = {Chierchia, Remi and Lebrat, Leo and Ahmedt-Aristizabal, David and Salvado, Olivier and Fookes, Clinton and Cruz, Rodrigo Santa},
    title     = {Multi-View Consistent Wound Segmentation With Neural Fields},
    booktitle = {Proceedings of the Winter Conference on Applications of Computer Vision (WACV)},
    month     = {February},
    year      = {2025},
    pages     = {4205-4214}
}
``` -->


## Acknowledgment 
This work was supported by
the MRFF Rapid Applied Research Translation grant
(RARUR000158), CSIRO [AI 4 Missions](https://research.csiro.au/ai4m/ai-is-helping-to-transform-wound-care/) Minimising Antimicrobial Resistance Mission, and Australian Government
Training Research Program (AGRTP) Scholarship.
