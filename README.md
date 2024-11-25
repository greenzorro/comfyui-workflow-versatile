# comfyui-workflow-versatile

[🇬🇧 EN](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/README.md) | [🇨🇳 中文](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/README_ZH_CN.md)

A general purpose ComfyUI workflow for common use cases. My go-to workflow for most tasks.

## Download

- [⏬ versatile-sd](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/versatile-sd.json)
- [⏬ versatile-pony](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/versatile-pony.json)

Example of versatile workflow for SDXL and SD1.5:

![](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/versatile-sd.png?raw=true)

NOTES:  
- `versatile-sd` is the most versatile.
- Pony diffusion is incompatible with IPadapter.
- Workflows for Flux on the way.

## Usage

Take `versatile-sd` as an example, it contains advanced techniques like IPadapter, ControlNet, IC light, LLM prompt generating, removing bg and excels at **text-to-image generating, image blending, style transfer, style exploring, inpainting, outpainting, relighting**.

With so many abilities all in one workflow, you have to understand the principle of Stable Diffusion and ComfyUI to adjust the wiring of nodes for different purposes. The default wiring set is for text-to-image generation.

Make sense of the whole workflow then you'll be able to unleash its full potential.

## Prerequisite

### Custom nodes

- ComfyUI_Essentials [https://github.com/cubiq/ComfyUI_essentials.git](https://github.com/cubiq/ComfyUI_essentials.git)
- ComfyUI-Easy-Use [https://github.com/yolain/ComfyUI-Easy-Use.git](https://github.com/yolain/ComfyUI-Easy-Use.git)
- ComfyUI-Custom-Scripts [https://github.com/pythongosssss/ComfyUI-Custom-Scripts.git](https://github.com/pythongosssss/ComfyUI-Custom-Scripts.git)
- ComfyUI_IPAdapter_plus [https://github.com/cubiq/ComfyUI_IPAdapter_plus.git](https://github.com/cubiq/ComfyUI_IPAdapter_plus.git)
- comfyui_controlnet_aux [https://github.com/Fannovel16/comfyui_controlnet_aux.git](https://github.com/Fannovel16/comfyui_controlnet_aux.git)
- ComfyUI-Anyline [https://github.com/TheMistoAI/ComfyUI-Anyline.git](https://github.com/TheMistoAI/ComfyUI-Anyline.git)
- ComfyUI-layerdiffuse [https://github.com/huchenlei/ComfyUI-layerdiffuse.git](https://github.com/huchenlei/ComfyUI-layerdiffuse.git)
- ComfyUI-IC-Light [https://github.com/huchenlei/ComfyUI-IC-Light.git](https://github.com/huchenlei/ComfyUI-IC-Light.git)
- ComfyUI_UltimateSDUpscale [https://github.com/ssitu/ComfyUI_UltimateSDUpscale.git](https://github.com/ssitu/ComfyUI_UltimateSDUpscale.git) --recursive
- ComfyUI-Tara-LLM-Integration [https://github.com/ronniebasak/ComfyUI-Tara-LLM-Integration.git](https://github.com/ronniebasak/ComfyUI-Tara-LLM-Integration.git)

### Models

**checkpoints**

- DreamShaperXL_Lightning.safetensors [https://huggingface.co/Lykon/dreamshaper-xl-lightning/resolve/main/DreamShaperXL_Lightning.safetensors?download=true](https://huggingface.co/Lykon/dreamshaper-xl-lightning/resolve/main/DreamShaperXL_Lightning.safetensors?download=true)
- dreamshaperXL_lightningInpaint.safetensors [https://civitai.com/api/download/models/450187](https://civitai.com/api/download/models/450187)
- DreamShaper_8_pruned.safetensors [https://huggingface.co/Lykon/DreamShaper/resolve/main/DreamShaper_8_pruned.safetensors?download=true](https://huggingface.co/Lykon/DreamShaper/resolve/main/DreamShaper_8_pruned.safetensors?download=true)
- ponyDiffusionV6XL_v6.safetensors [https://huggingface.co/Magamanny/Pony-Diffusion-V6-XL/resolve/main/ponyDiffusionV6XL_v6StartWithThisOne.safetensors?download=true](https://huggingface.co/Magamanny/Pony-Diffusion-V6-XL/resolve/main/ponyDiffusionV6XL_v6StartWithThisOne.safetensors?download=true)

**unet**

- iclight_sd15_fbc_unet_ldm.safetensors [https://huggingface.co/huchenlei/IC-Light-ldm/resolve/main/iclight_sd15_fbc_unet_ldm.safetensors?download=true](https://huggingface.co/huchenlei/IC-Light-ldm/resolve/main/iclight_sd15_fbc_unet_ldm.safetensors?download=true)
- iclight_sd15_fc_unet_ldm.safetensors [https://huggingface.co/huchenlei/IC-Light-ldm/resolve/main/iclight_sd15_fc_unet_ldm.safetensors?download=true](https://huggingface.co/huchenlei/IC-Light-ldm/resolve/main/iclight_sd15_fc_unet_ldm.safetensors?download=true)

**clip_vision**

- CLIP-ViT-bigG-14-laion2B-39B-b160k.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/image_encoder/model.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/image_encoder/model.safetensors)

**embeddings**

- negativeXL_D.safetensors [https://civitai.com/api/download/models/134583](https://civitai.com/api/download/models/134583)
- BadDream.pt [https://civitai.com/api/download/models/77169](https://civitai.com/api/download/models/77169)
- UnrealisticDream.pt [https://civitai.com/api/download/models/77173](https://civitai.com/api/download/models/77173)
- zPDXL3.safetensors [https://civitai.com/api/download/models/720175?type=Model&format=SafeTensor](https://civitai.com/api/download/models/720175?type=Model&format=SafeTensor)
- zPDXLxxx.pt [https://civitai.com/api/download/models/380277?type=Model&format=PickleTensor](https://civitai.com/api/download/models/380277?type=Model&format=PickleTensor)
- zPDXLxxx-neg.pt [https://civitai.com/api/download/models/380277?type=Negative&format=Other](https://civitai.com/api/download/models/380277?type=Negative&format=Other)
- zPDXLpg.pt [https://civitai.com/api/download/models/380285?type=Model&format=PickleTensor](https://civitai.com/api/download/models/380285?type=Model&format=PickleTensor)
- zPDXLpg-neg.pt [https://civitai.com/api/download/models/380285?type=Negative&format=Other](https://civitai.com/api/download/models/380285?type=Negative&format=Other)

**controlnet**

- mistoLine_rank256.safetensors [https://huggingface.co/TheMistoAI/MistoLine/resolve/main/mistoLine_rank256.safetensors?download=true](https://huggingface.co/TheMistoAI/MistoLine/resolve/main/mistoLine_rank256.safetensors?download=true)
- diffusers_xl_canny_full.safetensors [https://huggingface.co/lllyasviel/sd_control_collection/resolve/main/diffusers_xl_canny_full.safetensors?download=true](https://huggingface.co/lllyasviel/sd_control_collection/resolve/main/diffusers_xl_canny_full.safetensors?download=true)
- diffusers_xl_depth_full.safetensors [https://huggingface.co/lllyasviel/sd_control_collection/resolve/main/diffusers_xl_depth_full.safetensors?download=true](https://huggingface.co/lllyasviel/sd_control_collection/resolve/main/diffusers_xl_depth_full.safetensors?download=true)

**ipadapter**

- ip-adapter_sdxl.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/ip-adapter_sdxl.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/ip-adapter_sdxl.safetensors)

**upscale_models**

- 4x-UltraSharp.pth [https://huggingface.co/philz1337x/upscaler/resolve/main/4x-UltraSharp.pth?download=true](https://huggingface.co/philz1337x/upscaler/resolve/main/4x-UltraSharp.pth?download=true)

**loras**

- add-detail-xl.safetensors [https://civitai.com/api/download/models/135867?type=Model&format=SafeTensor](https://civitai.com/api/download/models/135867?type=Model&format=SafeTensor)
- Pony_DetailV2.0.safetensors [https://civitai.com/api/download/models/449738?type=Model&format=SafeTensor](https://civitai.com/api/download/models/449738?type=Model&format=SafeTensor)
- Anime_Style_2_SDXL_LoRA_Pony_Diffusion_V6_XL.safetensors [https://civitai.com/api/download/models/333590?type=Model&format=SafeTensor](https://civitai.com/api/download/models/333590?type=Model&format=SafeTensor)
- Smooth_Anime_2_Style_SDXL_LoRA_Pony_Diffusion_V6_XL.safetensors [https://civitai.com/api/download/models/333607?type=Model&format=SafeTensor](https://civitai.com/api/download/models/333607?type=Model&format=SafeTensor)
- Anime_Summer_Days_2_Style_SDXL_LoRA_Pony_Diffusion_V6_XL.safetensors [https://civitai.com/api/download/models/372898?type=Model&format=SafeTensor](https://civitai.com/api/download/models/372898?type=Model&format=SafeTensor)
- Watercolor_Anime_Style_LoRA_Pony_XL_v6.safetensors [https://civitai.com/api/download/models/725772?type=Model&format=SafeTensor](https://civitai.com/api/download/models/725772?type=Model&format=SafeTensor)
- LineArt_Mono_Style_LoRA_Pony_XL_v6.safetensors [https://civitai.com/api/download/models/450029?type=Model&format=SafeTensor](https://civitai.com/api/download/models/450029?type=Model&format=SafeTensor)

**rembg**

- RMBG-1.4.pth [https://huggingface.co/briaai/RMBG-1.4/resolve/main/model.pth](https://huggingface.co/briaai/RMBG-1.4/resolve/main/model.pth)

## Citation

Special thanks to [Comflowy](https://github.com/6174/comflowy) which lead me to the wonderful world of Stable Diffusion and ComfyUI! It is a comprehensive tutorial for beginners to learn Stable Diffusion. My workflow is essentially an implementation and integration of most techniques in the tutorial.