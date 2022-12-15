# Dreambooth with depth2image
This repo adapts the dreambooth script from diffusers to train the [stabilityai/stable-diffusion-2-depth](https://huggingface.co/stabilityai/stable-diffusion-2-depth) model.  
It works by creating a depth map from all the input images, then adds those depth maps as conditioning to the unet.  
Check out the notebook for a demo of how to use the script.  
I used the conda `environment.yaml` from the stable diffusion GitHub repo.  

## NOTICE
At the time of writing, `StableDiffusionDepth2ImgPipeline` is supported only on the `main` branch of `transformers`. Install it with the following:
```
pip uninstall -y transformers
pip install git+https://github.com/huggingface/transformers.git@main
```
