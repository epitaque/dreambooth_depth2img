# Dreambooth with depth2image
This repo adapts the dreambooth script from diffusers to train the [stabilityai/stable-diffusion-2-depth](https://huggingface.co/stabilityai/stable-diffusion-2-depth) model.  
It works by creating a depth map from all the input images, then adds those depth maps as conditioning to the unet.  
Check out the notebook for a demo of how to use the script.  
I used the conda `environment.yaml` from the stable diffusion GitHub repo.  

## NOTICE
At the time of writing, `StableDiffusionDepth2ImgPipeline` is broken in the latest version of diffusers. You might see incorrect depth maps being generated or get some kind of error. Solution:
```
pip uninstall -y transformers
git clone https://github.com/younesbelkada/transformers/tree/add-dpt-hybrid-support
cd transformers
git checkout add-dpt-hybrid
cd ..
pip install -e ./transformers
```
But may want to try the latest version of diffusers and see if it works, they may have fixed it by the time you read this.