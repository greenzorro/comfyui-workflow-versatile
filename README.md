# comfyui-workflow-versatile

[🇬🇧 EN](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/README.md) | [🇨🇳 中文](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/README_ZH_CN.md)

A general purpose ComfyUI workflow for common use cases. My go-to workflow for most tasks.

## Download

[⏬ versatile workflow](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/versatile.json)

![](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/versatile.png?raw=true)

## Usage

It contains advanced techniques like IPadapter, ControlNet, IC light, LLM prompt generating, removing bg and excels at **text-to-image generating, image blending, style transfer, style exploring, inpainting, outpainting, relighting**.

With so many abilities all in one workflow, you have to understand the principle of Stable Diffusion and ComfyUI to adjust the wiring of nodes for different purposes. The default wiring set is for text-to-image generation.

Make sense of the whole workflow then you'll be able to unleash its full potential.

## Prerequisite

The nodes you need for my workflow:

- ComfyUI_Essentials [https://github.com/cubiq/ComfyUI_essentials.git](https://github.com/cubiq/ComfyUI_essentials.git)
- ComfyUI-Easy-Use [https://github.com/yolain/ComfyUI-Easy-Use.git](https://github.com/yolain/ComfyUI-Easy-Use.git)
- comfyui_controlnet_aux [https://github.com/Fannovel16/comfyui_controlnet_aux.git](https://github.com/Fannovel16/comfyui_controlnet_aux.git)
- ComfyUI-Anyline [https://github.com/TheMistoAI/ComfyUI-Anyline.git](https://github.com/TheMistoAI/ComfyUI-Anyline.git)
- ComfyUI_IPAdapter_plus [https://github.com/cubiq/ComfyUI_IPAdapter_plus.git](https://github.com/cubiq/ComfyUI_IPAdapter_plus.git)
- ComfyUI-layerdiffuse [https://github.com/huchenlei/ComfyUI-layerdiffuse.git](https://github.com/huchenlei/ComfyUI-layerdiffuse.git)
- ComfyUI-IC-Light [https://github.com/huchenlei/ComfyUI-IC-Light.git](https://github.com/huchenlei/ComfyUI-IC-Light.git)
- ComfyUI-Tara-LLM-Integration [https://github.com/ronniebasak/ComfyUI-Tara-LLM-Integration.git](https://github.com/ronniebasak/ComfyUI-Tara-LLM-Integration.git)

The models you need for my workflow:

**checkpoints**

- DreamShaperXL_Lightning.safetensors [https://huggingface.co/Lykon/dreamshaper-xl-lightning/resolve/main/DreamShaperXL_Lightning.safetensors?download=true](https://huggingface.co/Lykon/dreamshaper-xl-lightning/resolve/main/DreamShaperXL_Lightning.safetensors?download=true)
- DreamShaper_8_pruned.safetensors [https://huggingface.co/Lykon/DreamShaper/resolve/main/DreamShaper_8_pruned.safetensors?download=true](https://huggingface.co/Lykon/DreamShaper/resolve/main/DreamShaper_8_pruned.safetensors?download=true)
- dreamshaperXL_lightningInpaint.safetensors [https://civitai.com/api/download/models/450187](https://civitai.com/api/download/models/450187)
- dreamshaper_8Inpainting.safetensors [https://huggingface.co/Lykon/DreamShaper/resolve/main/DreamShaper_8_INPAINTING.inpainting.safetensors?download=true](https://huggingface.co/Lykon/DreamShaper/resolve/main/DreamShaper_8_INPAINTING.inpainting.safetensors?download=true)

**controlnet**

- mistoLine_rank256.safetensors [https://huggingface.co/TheMistoAI/MistoLine/resolve/main/mistoLine_rank256.safetensors?download=true](https://huggingface.co/TheMistoAI/MistoLine/resolve/main/mistoLine_rank256.safetensors?download=true)
- diffusers_xl_canny_full.safetensors [https://huggingface.co/lllyasviel/sd_control_collection/resolve/main/diffusers_xl_canny_full.safetensors?download=true](https://huggingface.co/lllyasviel/sd_control_collection/resolve/main/diffusers_xl_canny_full.safetensors?download=true)
- diffusers_xl_depth_full.safetensors [https://huggingface.co/lllyasviel/sd_control_collection/resolve/main/diffusers_xl_depth_full.safetensors?download=true](https://huggingface.co/lllyasviel/sd_control_collection/resolve/main/diffusers_xl_depth_full.safetensors?download=true)

**ipadapter**

- ip-adapter_sd15.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter_sd15.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter_sd15.safetensors)
- ip-adapter_sd15_light_v11.bin [https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter_sd15_light_v11.bin](https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter_sd15_light_v11.bin)
- ip-adapter-plus_sd15.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter-plus_sd15.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter-plus_sd15.safetensors)
- ip-adapter-plus-face_sd15.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter-plus-face_sd15.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter-plus-face_sd15.safetensors)
- ip-adapter-full-face_sd15.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter-full-face_sd15.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter-full-face_sd15.safetensors)
- ip-adapter_sd15_vit-G.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter_sd15_vit-G.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter_sd15_vit-G.safetensors)
- ip-adapter_sdxl_vit-h.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/ip-adapter_sdxl_vit-h.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/ip-adapter_sdxl_vit-h.safetensors)
- ip-adapter-plus_sdxl_vit-h.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/ip-adapter-plus_sdxl_vit-h.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/ip-adapter-plus_sdxl_vit-h.safetensors)
- ip-adapter-plus-face_sdxl_vit-h.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/ip-adapter-plus-face_sdxl_vit-h.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/ip-adapter-plus-face_sdxl_vit-h.safetensors)
- ip-adapter_sdxl.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/ip-adapter_sdxl.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/ip-adapter_sdxl.safetensors)

**clip_vision**

- CLIP-ViT-bigG-14-laion2B-39B-b160k.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/image_encoder/model.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/image_encoder/model.safetensors)
- CLIP-ViT-H-14-laion2B-s32B-b79K.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/models/image_encoder/model.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/models/image_encoder/model.safetensors)

**upscale_models**

- 4x-UltraSharp.pth [https://huggingface.co/philz1337x/upscaler/resolve/main/4x-UltraSharp.pth?download=true](https://huggingface.co/philz1337x/upscaler/resolve/main/4x-UltraSharp.pth?download=true)

**embeddings**

- negativeXL_D.safetensors [https://civitai.com/api/download/models/134583](https://civitai.com/api/download/models/134583)
- BadDream.pt [https://civitai.com/api/download/models/77169](https://civitai.com/api/download/models/77169)
- UnrealisticDream.pt [https://civitai.com/api/download/models/77173](https://civitai.com/api/download/models/77173)

**unet**

- iclight_sd15_fbc_unet_ldm.safetensors [https://huggingface.co/huchenlei/IC-Light-ldm/resolve/main/iclight_sd15_fbc_unet_ldm.safetensors?download=true](https://huggingface.co/huchenlei/IC-Light-ldm/resolve/main/iclight_sd15_fbc_unet_ldm.safetensors?download=true)
- iclight_sd15_fc_unet_ldm.safetensors [https://huggingface.co/huchenlei/IC-Light-ldm/resolve/main/iclight_sd15_fc_unet_ldm.safetensors?download=true](https://huggingface.co/huchenlei/IC-Light-ldm/resolve/main/iclight_sd15_fc_unet_ldm.safetensors?download=true)

**rembg**

- RMBG-1.4.pth [https://huggingface.co/briaai/RMBG-1.4/resolve/main/model.pth](https://huggingface.co/briaai/RMBG-1.4/resolve/main/model.pth)

**loras**

- add-detail-xl.safetensors [https://civitai.com/api/download/models/135867?type=Model&format=SafeTensor](https://civitai.com/api/download/models/135867?type=Model&format=SafeTensor)


## Citation

Special thanks to [Comflowy](https://github.com/6174/comflowy) which lead me to the wonderful world of Stable Diffusion and ComfyUI! It is a comprehensive tutorial for beginners to learn Stable Diffusion. My workflow is essentially an implementation and integration of most techniques in the tutorial.