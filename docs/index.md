---
layout: single
author_profile: True
classes: wide
title: "WoundNeRF: Multi-View Consistent Wound Segmentation With Neural Fields"
excerpt: "ISBI 2026"
header:
  overlay_image: /assets/images/data_augmentation.png
  overlay_filter: 0.5
  caption: "Qualitative comparison 2D predictions vs. our method trained with few views"
  actions:
    - label: "📄 Paper (arXiv)"
      url: "https://arxiv.org/abs/2601.16487"
    - label: "💻 Code — coming soon"
    
gallery_2v3d:
  - url: /assets/images/2d_3d.png
    image_path: /assets/images/2d_3d.png
    alt: "View inconsistency from mapping 2D expert-annotated masks from different viewpoints onto the underlying 3D surface. Overlapping regions are highlighted in magenta, while non-overlapping regions indicate disagreement."
    title: "View inconsistency from mapping 2D expert-annotated masks from different viewpoints onto the underlying 3D surface. Overlapping regions are highlighted in magenta, while non-overlapping regions indicate disagreement."
gallery_method:
  - url: /assets/images/isbi26.png
    image_path: /assets/images/isbi26.png
gallery_qualitative1:
  - url: /assets/images/qualitative1.png
    image_path: /assets/images/qualitative1.png
gallery_accuracy:
  - url: /assets/images/accuracy.png
    image_path: /assets/images/accuracy.png
gallery_robustness:
  - url: /assets/images/robustness.png
    image_path: /assets/images/robustness.png
gallery_qualitative2:
  - url: /assets/images/sparse_views.png
    image_path: /assets/images/sparse_views.png

paginate: true 


---



## Motivation

Chronic wound care remains a major healthcare challenge, requiring regular assessments that are costly and often delayed.  
Most existing automated wound segmentation methods operate in **2D**, leading to inconsistent results across viewpoints and inaccurate 3D measurements.  

{% include gallery id="gallery_2v3d" caption="2D annotation inconsistencies observed when projected onto the same 3D surface. Overlapping regions are highlighted in magenta." width="80%" %}

**WoundNeRF** addresses this by learning a **3D‑consistent wound segmentation field** directly from multi‑view images.



## Approach

Building on advances in Neural Radiance Fields (NeRFs), **WoundNeRF** jointly models wound **appearance, geometry, and semantics** in a unified 3D space.

- Aggregates automatically generated 2D segmentations into a 3D semantic field  
- Enforces **multi‑view consistency** without requiring dense manual labeling  
- Focuses on accurate 3D reconstruction of wound regions rather than hallucination or blending

{% include gallery id="gallery_method" caption="WoundNeRF architecture and training pipeline." %}



## Results

We evaluate WoundNeRF on a **real patient dataset** collected with clinical collaborators.

**Baselines:**
- **2D:** SegFormer MiT‑B5 trained on single‑view annotations  
- **3D/2D:** Multi‑view aggregation following *Wound3DAssist*  

**Our model** produces smoother boundaries, higher recall, and stronger multi‑view coherence.

{% include gallery id="gallery_accuracy" caption="Accuracy comparison across 73 patient videos." width="80%" %}

{% include gallery id="gallery_qualitative1" caption="Qualitative comparison of wound and tissue segmentations. Tissues classes: wound
bed (1), granulation (2), necrotic (3), slough (4), and unknown (5)." width="80%" %}

Even with limited expert annotations (2–4 views), **WoundNeRF** maintains consistent predictions across **50 unseen viewpoints**, dramatically reducing inter‑view variation and noise.

{% include gallery id="gallery_qualitative2" caption="Prediction consistency: 2D model (left) vs WoundNeRF (right). The bottom row displays the corresponding wound segmentation on the 3D mesh extracted from our method." width="80%" %}



## Robustness

When training masks are intentionally perturbed, WoundNeRF remains stable, highlighting strong resistance to noisy supervision.

{% include gallery id="gallery_robustness" caption="Robustness under boundary perturbations." width="65%" %}



## Conclusion

We present **WoundNeRF**, a method for generating **multi‑view consistent wound segmentations**.  
By learning directly in 3D space, it overcomes the topological limitations of 2D segmentation and enables coherent wound reconstruction for clinical use.  

Future work will explore **confidence‑driven segmentation** to reduce misclassified regions and enhance semantic reliability for real‑world healthcare deployment.



## If you find this work useful, please cite:

<div class="highlight highlight-source-bibtex">
  <pre><code class="language-bibtex" data-lang="bibtex">@misc{chierchia2026woundnerf,
      title={Multi-View Consistent Wound Segmentation With Neural Fields}, 
      author={Remi Chierchia and Léo Lebrat and David Ahmedt-Aristizabal and Yulia Arzhaeva and Olivier Salvado and Clinton Fookes and Rodrigo Santa Cruz},
      year={2026},
      eprint={2601.16487},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2601.16487}
}</code></pre>
  
  <div class="highlight-overlay">
    <button class="btn-clipboard" type="button">Copy</button>
  </div>
</div>

<script>
document.querySelectorAll('.btn-clipboard').forEach(button => {
  button.addEventListener('click', function() {
    const code = this.closest('.highlight').querySelector('code').innerText.trim();
    navigator.clipboard.writeText(code).then(() => {
      const original = this.innerText;
      this.innerText = 'Copied!';
      this.style.color = '#1a7f37';
      setTimeout(() => {
        this.innerText = original;
        this.style.color = '';
      }, 2000);
    });
  });
});
</script>

<!-- <b>If interested, check our previous pubblications</b>
- Syn3DWound {project page}{https://lebrat.github.io/Syn3DWound/} {paper}{https://arxiv.org/abs/2311.15836}
- SALVE {project page}{https://remichierchia.github.io/SALVE/} {paper}{https://ieeexplore.ieee.org/abstract/document/10943648}
- Wound3DAssist {paper}{https://arxiv.org/abs/2508.17635}
- NON-INVASIVE 3D WOUND MEASUREMENT WITH RGB-D IMAGING [paper]{https://arxiv.org/pdf/2601.19014} -->

## Related Works

**If interested, check our previous publications:**

<div class="feature__wrap">
  <ul class="feature__list">
    <li>
      <strong>Syn3DWound</strong><br>
      <a href="https://lebrat.github.io/Syn3DWound/">Project Page</a> • 
      <a href="https://arxiv.org/abs/2311.15836">Paper (arXiv)</a> •
      <a href="https://doi.org/10.25919/5rwz-ts17">Dataset</a>
    </li>
    <li>
      <strong>SALVE</strong><br>
      <a href="https://remichierchia.github.io/SALVE/">Project Page</a> • 
      <a href="https://ieeexplore.ieee.org/abstract/document/10943648">Paper (IEEE)</a> •
      <a href="https://doi.org/10.25919/h3mg-xh67">Dataset</a>
    </li>
    <li>
      <strong>Wound3DAssist</strong><br>
      <a href="https://arxiv.org/abs/2508.17635">Paper (arXiv)</a>
    </li>
    <li>
      <strong>Non-Invasive 3D Wound Measurement with RGB-D Imaging</strong><br>
      <a href="https://arxiv.org/pdf/2601.19014">Paper (arXiv)</a>
    </li>
  </ul>
</div>



<!-- ```
@misc{chierchia2026multiviewconsistentwoundsegmentation,
      title={Multi-View Consistent Wound Segmentation With Neural Fields}, 
      author={Remi Chierchia and Léo Lebrat and David Ahmedt-Aristizabal and Yulia Arzhaeva and Olivier Salvado and Clinton Fookes and Rodrigo Santa Cruz},
      year={2026},
      eprint={2601.16487},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2601.16487}, 
}
``` -->
<!-- 
```
@InProceedings{Chierchia_2025_WACV,
    author    = {Chierchia, Remi and Lebrat, Leo and Ahmedt-Aristizabal, David and Salvado, Olivier and Fookes, Clinton and Cruz, Rodrigo Santa},
    title     = {Multi-View Consistent Wound Segmentation With Neural Fields},
    booktitle = {Proceedings of the Winter Conference on Applications of Computer Vision (WACV)},
    month     = {February},
    year      = {2025},
    pages     = {4205-4214}
}
```
-->


## Acknowledgment 
This work was supported by
the MRFF Rapid Applied Research Translation grant
(RARUR000158), CSIRO [AI 4 Missions](https://research.csiro.au/ai4m/ai-is-helping-to-transform-wound-care/) Minimising Antimicrobial Resistance Mission, and Australian Government
Training Research Program (AGRTP) Scholarship.
