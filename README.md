# solve memory issue, reference cycle problem
+ by using garbage collector in func ```def render_single_image()```
+ ```gpu_tracker``` make training process very slow, so I remove all of them
+ Another finding is that, if only ``` del render_out_latent``` we can even not use ```torch.cuda.empty_cache()```, the gpu memory used is about 11715MiB
+ all modifications are in LatentPaintTrainer.py and stable_diffusion.py