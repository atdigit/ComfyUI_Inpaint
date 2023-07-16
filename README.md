# ComfyUI_Inpaint
Examples below are accompanied by a [tutorial in my YouTube video](https://youtu.be/4JRnVRTKgh4).

This ComfyUI node setups that let you utilize inpainting (edit some parts of an image) in your ComfyUI AI generation routine.

You can easily utilize schemes below for your custom setups. Simply save and then drag and drop relevant image into your [ComfyUI interface window](https://github.com/comfyanonymous/ComfyUI) with or without ControlNet Inpaint model installed, load png image with or without mask you want to edit, modify some prompts, edit mask (if necessary), press "Queue Prompt" and wait for the AI generation to complete. 

Stable Diffusion models used in this demonstration are [Lyriel](https://civitai.com/models/22922/lyriel?modelVersionId=72396) and [Realistic Vision Inpainting](https://civitai.com/models/4201?modelVersionId=114600).

Video tutorial on how to use ComfyUI, a powerful and modular Stable Diffusion GUI and backend, is [here](https://youtu.be/Ij8k6mBgL3o).
Node setup 1 below is based on the original modular scheme found in [ComfyUI_examples -> Inpainting](https://comfyanonymous.github.io/ComfyUI_examples/inpaint/).

![ComfyUI_00021_](https://github.com/atdigit/ComfyUI_Inpaint/assets/105158639/df90792b-1bc0-4972-b6a0-4b0c5922ab0c)
![Clip_3](https://github.com/atdigit/ComfyUI_Inpaint/assets/105158639/583f0dc1-2cfe-473a-84fb-c0f97ba86404)
![Layer 0](https://github.com/atdigit/ComfyUI_Inpaint/assets/105158639/b55ceb86-2c68-44e0-9284-a841b3f75ff5)
**↑ Node setup 1: Classic SD Inpaint mode (Save portrait and image with hole to your PC and then drag and drop portrait into you ComfyUI interface to load scheme, drag and drop image with hole to "Load image with alpha..." node, then press "Queue Prompt")**

![ComfyUI_00004_](https://github.com/atdigit/ComfyUI_Inpaint/assets/105158639/175a8d55-97fe-41a2-aa3f-70e92e3e7579)
![Clip](https://github.com/atdigit/ComfyUI_Inpaint/assets/105158639/58c08e4a-ac07-4cb9-a297-532e8c673837)
![Layer 1](https://github.com/atdigit/ComfyUI_Inpaint/assets/105158639/c8815b7b-5b80-4bc0-b871-4d30e4f05784)

**↑ Node setup 2: Stable Diffusion with ControlNet classic Inpaint / Outpaint mode (Save kitten muzzle on winter background to your PC and then drag and drop it into your ComfyUI interface, save to your PC an then drag and drop image with white arias to Load Image Node of ControlNet inpaint group, change width and height for outpainting effect if necessary and press "Queue Prompt")**


You can use the [Official ComfyUI Notebook](https://colab.research.google.com/github/comfyanonymous/ComfyUI/blob/master/notebooks/comfyui_colab.ipynb) to run Node Setup 2 generation in Google Colab.
To successfully complete the above schemes be sure you have the following code in the above Colab notebook's second (Checkpoints) cell:
<a name="code_to_copy"></a>
```
!wget -c https://huggingface.co/comfyanonymous/ControlNet-v1-1_fp16_safetensors/resolve/main/control_v11p_sd15_inpaint_fp16.safetensors -P ./models/controlnet/
# Controlnet Preprocessor nodes by Fannovel16
!cd custom_nodes && git clone https://github.com/Fannovel16/comfy_controlnet_preprocessors; cd comfy_controlnet_preprocessors && python install.py
