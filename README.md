<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="description" content="ArtiLatent: Realistic Articulated 3D Object Generation via Structured Latents">
  <meta name="keywords" content="Articulated 3D Modeling, Latent 3D Diffusion Model, 3D Gaussian Splatting, Human-made Articulation">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>ArtiLatent: Realistic Articulated 3D Object Generation via Structured Latents.</title>

  <style>
    .dnerf {
        font-size: 36px; /* Adjust the size as needed */
    }
  </style>

  <!-- Global site tag (gtag.js) - Google Analytics -->
  <!-- <script async src="https://www.googletagmanager.com/gtag/js?id=G-PYVRSFMDRL"></script> -->
  <script>
    window.dataLayer = window.dataLayer || [];

    function gtag() {
      dataLayer.push(arguments);
    }

    gtag('js', new Date());

    gtag('config', 'G-PYVRSFMDRL');
  </script>

  <!-- <link href="https://fonts.googleapis.com/css?family=Google+Sans|Noto+Sans|Castoro" rel="stylesheet"> -->

  <link rel="stylesheet" href="./static/css/bulma.min.css">
  <link rel="stylesheet" href="./static/css/bulma-carousel.min.css">
  <link rel="stylesheet" href="./static/css/bulma-slider.min.css">
  <link rel="stylesheet" href="./static/css/fontawesome.all.min.css">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/jpswalsh/academicons@1/css/academicons.min.css">
  <!-- <link rel="stylesheet" href="./static/css/index.css"> -->
  <link rel="icon" href="./static/images/favicon.svg">

  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
  <script defer src="./static/js/fontawesome.all.min.js"></script>
  <script src="./static/js/bulma-carousel.min.js"></script>
  <script src="./static/js/bulma-slider.min.js"></script>
  <!-- <script src="./static/js/index.js"></script> -->
</head>

<body>

  <nav class="navbar" role="navigation" aria-label="main navigation">
    <div class="navbar-brand">
      <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false">
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
      </a>
    </div>
  </nav>

  <section class="hero">
    <div class="hero-body">
      <div class="container is-max-desktop">
        <div class="columns is-centered">
          <div class="column has-text-centered">
            <h1 class="title is-1 publication-title">
              <span class="dnerf">ArtiLatent: Realistic Articulated 3D Object Generation via Structured Latents</span>
            </h1>
            <div class="is-size-5 publication-authors">
              <span class="author-block">
                <a href="https://chenhonghua.github.io/clay.github.io/">Honghua Chen, </a></span>
              <!--  -->
              <span class="author-block">
                <a href="https://nirvanalan.github.io/">Yushi Lan, </a></span>

              <span class="author-block">
                <a href="https://cyw-3d.github.io/">Yongwei Chen, </a></span>

              <span class="author-block">
                <a href="https://xingangpan.github.io/">Xingang Pan</a></span>
            </div>

            <div class="is-size-5 publication-authors">
              <span class="author-block">S-Lab, Nanyang Technological University, Singapore</span>
            </div>

            <h1 style="font-size:24px;font-weight:bold">SIGGRAPH Asia 2025 (Conference Track)</h1>

            <div class="column has-text-centered">
              <div class="publication-links">
                <!-- PDF Link. -->
                <span class="link-block">
                  <a href="https://arxiv.org/abs/2410.16272" class="external-link button is-normal is-rounded is-dark">
                    <span class="icon">
                      <i class="fas fa-file-pdf"></i>
                    </span>
                    <span>Paper</span>
                  </a>
                </span>
                <!-- Code Link. -->
                <span class="link-block">
                  <a href="file:///Users/honghua/Downloads/MyProjects-main/ArtiLatent/index.html" class="external-link button is-normal is-rounded is-dark">
                    <span class="icon">
                      <i class="fab fa-github"></i>
                    </span>
                    <span>Code</span>
                  </a>
                </span>
                <!-- Dataset Link. -->
                <!-- <span class="link-block">
                  <a href="https://github.com/google/nerfies/releases/tag/0.1"
                    class="external-link button is-normal is-rounded is-dark">
                    <span class="icon">
                      <i class="far fa-images"></i>
                    </span>
                    <span>Data</span> -->
                <!-- </a> -->
              </div>



              <hr style="width:100%;height:0.7px;background-color:rgba(0, 0, 0, 0.665);margin-top:1em">
              
              <font size="5">
                <b>ArtiLatent</b> is a unified generative framework for synthesizing human-made articulated 3D objects with <strong>fine-grained geometry, motion semantics, and realistic appearance</strong>.
              </font>

              <!-- <br>All testing images shown below are never seen by the model in training. -->

            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- <section class="hero teaser">
    <div class="container is-max-desktop">
      <div class="hero-body">
        <video id="teaser" autoplay muted loop playsinline height="100%">
          <source src="./static/videos/teaser.mp4" type="video/mp4">
        </video>
        <h2 class="subtitle has-text-centered">
          <span class="dnerf">Nerfies</span> turns selfie videos from your phone into
          free-viewpoint
          portraits.
        </h2>
      </div>
    </div>
  </section> -->

  <section class="hero is-light is-small">
    <div class="hero-body">
      <div class="container is-max-desktop">
        <!-- <div id="results-carousel" class="carousel results-carousel"> -->

        <div class="columns is-centered has-text-centered">
          <div id="carousel" class="results-carousel">
            <!-- <div class="item" align="center"> -->
            <!-- <img src="static/images/teaser.png" width="100%" alt="overview_image"> -->
            <img src="static/images/teaser.png" width="100%" alt="overview_image">
            <div class="content has-text-justified">
              <p>
                Given a <b>real-world image</b> (a, d, g) as input condition, our framework generates articulated 3D objects with realistic geometry, articulation, and appearance. For each example, we first generate an articulation-aware voxel structure (b, e, h), and then decode it into 3D Gaussian splats that support physically plausible part-level motion (c, f, i). The resulting models exhibit high visual fidelity and motion consistency across various object types.
              </p>
              <!-- </div> -->
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section class="section">

    <div class="container is-max-desktop">

      <div class="container is-max-desktop">

        <section class="section">
          <div class="container is-max-desktop">
            <!-- Abstract. -->
            <div class="columns is-centered has-text-centered">
              <div class="column is-four-fifths">
                <h2 class="title is-3">Abstract</h2>
                <div class="content has-text-justified">
                  <p>
                    We propose ArtiLatent, a generative framework that synthesizes human-made 3D objects with fine-grained geometry, accurate articulation, and realistic appearance. Our approach jointly models part geometry and articulation dynamics by embedding sparse voxel representations and associated articulation properties—including joint type, axis, origin, range, and part category—into a unified latent space via a variational autoencoder. A latent diffusion model is then trained over this space to enable diverse yet physically plausible sampling.
To reconstruct photorealistic 3D shapes, we introduce an articulation-aware Gaussian decoder that accounts for articulation-dependent visibility changes (e.g., revealing the interior of a drawer when opened). By conditioning appearance decoding on articulation state, our method assigns plausible texture features to regions that are typically occluded in static poses, significantly improving visual realism across articulation configurations.
Extensive experiments on furniture-like objects from PartNet-Mobility and ACD datasets demonstrate that ArtiLatent outperforms existing approaches in geometric consistency and appearance fidelity. Our framework provides a scalable solution for articulated 3D object synthesis and manipulation.
                  </p>
                </div>
                <div></div>

                <!-- <div align="center" style="margin-top:10px;" style="margin-bottom:40px;">
                  <img style='height: auto; width: 100%; object-fit: contain' src="static/images/overview.png">
                </div>
                <div class="content has-text-justified">
                  <p>
                    We propose to first learn a 3D latent space, where a monocular image is encoded into the
                    KL-regularized
                    latent space.
                    The encoded 3D latent is decoded by a 3D-aware DiT transformer, and up-sampled towards a high-res
                    tri-plane for rendering supervisions.
                    In the second stage, we perform efficient conditional diffusion learning over the compact latent
                    space.
                  </p>
                </div> -->

              </div>
            </div>

            <img style='height: auto; width: 100%; object-fit: contain' src="static/images/pipeline.png">
            <div class="content has-text-justified">
            <p>
              <strong>The overall architecture of ArtiLatent.</strong>
              Given voxel-level articulation-aware inputs (occupancy, semantics, joint types, bounding boxes, joint parameters, and motion ranges), we encode them into a latent representation using an articulation-aware VAE. A conditional diffusion model samples articulation-aware latent codes under user-specified conditions (\eg, image), which are then decoded into an animatable voxel structure. The final appearance is generated using an articulation-aware Gaussian decoder, producing high-fidelity 3D Gaussian splats with consistent geometry and appearance across motion states.
            </p>
            </div>

      </div>
  </section>



        <div class="columns is-centered">
          <!-- Matting. -->
          <div class="column is-full-width">
            <h2 class="title is-3" style="text-align: center;">Video Demo</h2>
            <div class="columns is-centered">
              <div class="column content">
                <!-- <p>
                  We showcase the reenactment comparison of our method against IDE-3D.
                  Given IDE-3D's segmentation-based nature, utilizing a reference identity with a different
                  shape unavoidably
                  leads to change in the face layout.
                  Nevertheless, Gaussian3Diff integrates a disentangled identity and expression modeling,
                  facilitated by the
                  underlying 3DMM, ensuring the preservation of the input identity through the reeactment
                  process.
                </p> -->

                <div style="display: flex; margin: 0 auto;">

                  <div>
                    <video width="100%" controls loop muted>
                      <source src="static/videos/video_demo_v3.mp4"
                        type="video/mp4">
                    </video>
                  </div>

                </div>

                
              </div>

            </div>
          </div>
        </div>
      
        <br>
  <!-- Concurrent Work. -->
  <div class="columns is-centered">
    <div class="column is-full-width">
      <h2 class="title is-3">Related Links</h2>

      <div class="content has-text-justified">
        <p>
          Our work is inspired by the following work:
        </p>
        <p>
          <a href="https://github.com/microsoft/TRELLIS">TRELLIS</a> is a large 3D asset generation model. It takes in text or image prompts and generates high-quality 3D assets in various formats, such as Radiance Fields, 3D Gaussians, and meshes.
        </p>
        <p>
          <a href="https://github.com/3dlg-hcvc/cage">CAGE</a> addresses the challenge of generating 3D articulated objects in a controllable fashion.
        </p>
        <p>
          <a href="https://github.com/3dlg-hcvc/singapo">SINGAPO</a> is a generative method to reconstruct 3D articulated objects from an image observing the object in the resting state from a random view.
        </p>
      </div>
    </div>
  </div>
  <!--/ Concurrent Work. -->

  </div>
  </section>

  <section class="section" id="BibTeX">
    <div class="container is-max-desktop content">
      <h2 class="title">BibTeX</h2>
      <pre><code>
  @title={ArtiLatent: Realistic Articulated 3D Object Generation via Structured Latents},
  author={Chen, Honghua and Lan, Yushi and Chen, Yongwei and Pan, Xingang},
  booktitle={SIGGRAPH Aisa},
  year={2025}
}</code></pre>
    </div>
  </section>


  <footer class="footer">
    <div class="container">
      <div class="content has-text-centered">
        <!-- <a class="icon-link"
         href="./static/videos/nerfies_paper.pdf">
        <i class="fas fa-file-pdf"></i>
      </a> -->
        <!-- <a class="icon-link" href="https://github.com/keunhong" class="external-link" disabled>
        <i class="fab fa-github"></i>
      </a> -->
      </div>
      <div class="columns is-centered">
        <div class="column is-8">
          <div class="content">
            <!-- <p> -->
            <!-- This website is licensed under a <a rel="license"
                                                href="http://creativecommons.org/licenses/by-sa/4.0/">Creative
            Commons Attribution-ShareAlike 4.0 International License</a>. -->
            <!-- </p> -->
            <p>
              We thank <a href="https://github.com/nerfies/nerfies.github.io">nerfies</a> for sharing this website
              template.
              <!-- Please remember to remove the analytics code included in the header of the website which -->
              <!-- you do not want on your website. -->
            </p>
          </div>
        </div>
      </div>
    </div>
  </footer>

</body>

</html>
