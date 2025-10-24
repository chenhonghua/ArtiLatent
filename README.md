<div align="center">

<h1>
ArtiLatent: Realistic Articulated 3D Object Generation via Structured Latents
</h1>

<a href="https://chenhonghua.github.io/clay.github.io/">Honghua Chen, </a></span>
<span class="author-block">
<a href="https://nirvanalan.github.io/">Yushi Lan, </a></span>
<span class="author-block">
<a href="https://cyw-3d.github.io/">Yongwei Chen, </a></span>
<span class="author-block">
<a href="https://xingangpan.github.io/">Xingang Pan</a></span>


<span class="author-block">S-Lab, Nanyang Technological University, Singapore</span>

</div>



<div id="carousel" class="results-carousel">
<img src="images/teaser.png" width="100%" alt="overview_image">
<div class="content has-text-justified">
    <p>
    <b>ArtiLatent</b> is a unified generative framework for synthesizing human-made articulated 3D objects with <strong>fine-grained geometry, motion semantics, and realistic appearance</strong>.
    </p>
</div>
</div>

<h2 class="title is-3">Abstract</h2>
<div class="content has-text-justified">
    <p>
    We propose ArtiLatent, a generative framework that synthesizes human-made 3D objects with fine-grained geometry, accurate articulation, and realistic appearance. Our approach jointly models part geometry and articulation dynamics by embedding sparse voxel representations and associated articulation properties—including joint type, axis, origin, range, and part category—into a unified latent space via a variational autoencoder. A latent diffusion model is then trained over this space to enable diverse yet physically plausible sampling.
To reconstruct photorealistic 3D shapes, we introduce an articulation-aware Gaussian decoder that accounts for articulation-dependent visibility changes (e.g., revealing the interior of a drawer when opened). By conditioning appearance decoding on articulation state, our method assigns plausible texture features to regions that are typically occluded in static poses, significantly improving visual realism across articulation configurations.
Extensive experiments on furniture-like objects from PartNet-Mobility and ACD datasets demonstrate that ArtiLatent outperforms existing approaches in geometric consistency and appearance fidelity. Our framework provides a scalable solution for articulated 3D object synthesis and manipulation.
    </p>
</div>

<h2 class="title is-3">Pipeline</h2>
<img style='height: auto; width: 100%; object-fit: contain' src="images/pipeline">
<div class="content has-text-justified">
<p>
    <strong>The overall architecture of ArtiLatent</strong>
    Given voxel-level articulation-aware inputs (occupancy, semantics, joint types, bounding boxes, joint parameters, and motion ranges), we encode them into a latent representation using an articulation-aware VAE. A conditional diffusion model samples articulation-aware latent codes under user-specified conditions (\eg, image), which are then decoded into an animatable voxel structure. The final appearance is generated using an articulation-aware Gaussian decoder, producing high-fidelity 3D Gaussian splats with consistent geometry and appearance across motion states.
</p>
</div>


## User Instructions

Official implementation of the paper "ArtiLatent: Realistic Articulated 3D Object Generation via Structured Latents".

Project page is [here](https://chenhonghua.github.io/MyProjects/ArtiLatent/).

We plan to release the code by November 2025. Stay arranged!
