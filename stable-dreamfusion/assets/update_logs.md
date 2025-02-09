### 2023.3.30
* adopt ideas from [Fantasia3D](https://fantasia3d.github.io/) to concatenate normal and mask as the latent code in a warm up stage, which shows faster convergence of shape.

### 2023.1.30
* Use an MLP to predict the surface normals as in Magic3D to avoid finite difference / second order gradient, generation quality is greatly improved.
* More efficient two-pass raymarching in training inspired by nerfacc.

### 2022.12.3
* Support Stable-diffusion 2.0 base.

### 2022.11.15
* Add the vanilla backbone that is pure-pytorch.

### 2022.10.9
* The shading (partially) starts to work, at least it won't make scene empty. For some prompts, it shows better results (less severe Janus problem). The textureless rendering mode is still disabled.
* Enable shading by default (--warmup_iters 1000).

### 2022.10.5
* Basic reproduction finished.
* Non --cuda_ray, --tcnn are not working, need to fix.
* Shading is not working, disabled in utils.py for now. Surface normals are bad.
* Use an entropy loss to regularize weights_sum (alpha), the original L2 reg always leads to degenerated geometry...