# comfyui-workflow-versatile

[🇬🇧 EN](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/README.md) | [🇨🇳 中文](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/README_ZH_CN.md)

通用 ComfyUI 工作流，适用于多种常见用途。是我应对多种任务的首选工作流。

## 下载

- [⏬ versatile-sd](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/versatile-sd.json)
- [⏬ versatile-pony](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/versatile-pony.json)

适用于SDXL及SD1.5的万能工作流示例：

![](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/versatile-sd.png?raw=true)

注意：  
- `versatile-sd` 能力最齐全。
- Pony diffusion不支持IPadapter。
- Flux和SD3.5版的工作流正在搭建中。

## 使用

以 `versatile-sd` 为例子，其中包含 IPadapter、ControlNet、IC light、LLM 提示词生成、背景移除等高级技术，它擅长 **文生图、图像混合、风格迁移、风格探索、局部重绘、扩图、重新打光**。

集如此多种功能于一身，因此你需要了解 Stable Diffusion 和 ComfyUI 的工作原理，才能根据不同目的调整节点的连线。默认的连线配置是文生图。

理解整个工作流程后，才能充分发挥其潜力。

## 使用前提

### 节点

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

### 模型

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

## 感谢

感谢 [Comflowy](https://github.com/6174/comflowy)，它引领我进入 Stable Diffusion 和 ComfyUI 的奇妙世界！这是一套全面的 Stable Diffusion 入门教程。我的工作流基本上就是把其中教的技巧实现并整合起来而已。
