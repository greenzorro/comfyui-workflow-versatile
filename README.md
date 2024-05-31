# comfyui-workflow-versatile

A general purpose ComfyUI workflow for common use cases.

通用 ComfyUI 工作流程，适用于多种常见用途。

## Download 下载

[⏬ versatile workflow](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/versatile.json)

## Usage 使用

It contains advanced techniques like IPadapter, ControlNet, IC light, LLM prompt generating, removing bg and excels at **text-to-image generating, image blending, style transfer, style exploring, inpainting, outpainting, relighting**.

With so many abilities all in one workflow, you have to understand the principle of Stable Diffusion and ComfyUI to adjust the wiring of nodes for different purposes. The default wiring set is for text-to-image generation.

Make sense of the whole workflow then you'll be able to unleash its full potential.

其中包含 IPadapter、ControlNet、IC light、LLM 提示词生成、背景移除等高级技术，它擅长 **文生图、图像混合、风格迁移、风格探索、局部重绘、扩图、重新打光**。

集如此多种功能于一身，因此你需要了解 Stable Diffusion 和 ComfyUI 的工作原理，才能根据不同目的调整节点的连线。默认的连线配置是文生图。

理解整个工作流程后，才能充分发挥其潜力。

## Prerequisite 使用前提

The nodes you need for my workflow:

我的工作流所需的节点：

- Custom node: ComfyUI_Essentials [https://github.com/cubiq/ComfyUI_essentials.git](https://github.com/cubiq/ComfyUI_essentials.git)
- Custom node: ComfyUI-Easy-Use [https://github.com/yolain/ComfyUI-Easy-Use.git](https://github.com/yolain/ComfyUI-Easy-Use.git)
- Custom node: comfyui_controlnet_aux [https://github.com/Fannovel16/comfyui_controlnet_aux.git](https://github.com/Fannovel16/comfyui_controlnet_aux.git)
- Custom node: ComfyUI-Anyline [https://github.com/TheMistoAI/ComfyUI-Anyline.git](https://github.com/TheMistoAI/ComfyUI-Anyline.git)
- Custom node: ComfyUI_IPAdapter_plus [https://github.com/cubiq/ComfyUI_IPAdapter_plus.git](https://github.com/cubiq/ComfyUI_IPAdapter_plus.git)
- Custom node: ComfyUI-layerdiffuse [https://github.com/huchenlei/ComfyUI-layerdiffuse.git](https://github.com/huchenlei/ComfyUI-layerdiffuse.git)
- Custom node: ComfyUI-IC-Light [https://github.com/huchenlei/ComfyUI-IC-Light.git](https://github.com/huchenlei/ComfyUI-IC-Light.git)
- Custom node: ComfyUI-Tara-LLM-Integration [https://github.com/ronniebasak/ComfyUI-Tara-LL

The models you need for my workflow:

我的工作流所需的模型：

- checkpoints: DreamShaperXL_Lightning.safetensors [https://huggingface.co/Lykon/dreamshaper-xl-lightning/resolve/main/DreamShaperXL_Lightning.safetensors?download=true](https://huggingface.co/Lykon/dreamshaper-xl-lightning/resolve/main/DreamShaperXL_Lightning.safetensors?download=true)
- checkpoints: DreamShaper_8_pruned.safetensors [https://huggingface.co/Lykon/DreamShaper/resolve/main/DreamShaper_8_pruned.safetensors?download=true](https://huggingface.co/Lykon/DreamShaper/resolve/main/DreamShaper_8_pruned.safetensors?download=true)
- checkpoints: dreamshaperXL_lightningInpaint.safetensors [https://civitai.com/api/download/models/450187](https://civitai.com/api/download/models/450187)
- checkpoints: dreamshaper_8Inpainting.safetensors [https://huggingface.co/Lykon/DreamShaper/resolve/main/DreamShaper_8_INPAINTING.inpainting.safetensors?download=true](https://huggingface.co/Lykon/DreamShaper/resolve/main/DreamShaper_8_INPAINTING.inpainting.safetensors?download=true)

- controlnet: mistoLine_rank256.safetensors [https://huggingface.co/TheMistoAI/MistoLine/resolve/main/mistoLine_rank256.safetensors?download=true](https://huggingface.co/TheMistoAI/MistoLine/resolve/main/mistoLine_rank256.safetensors?download=true)
- controlnet: diffusers_xl_canny_full.safetensors [https://huggingface.co/lllyasviel/sd_control_collection/resolve/main/diffusers_xl_canny_full.safetensors?download=true](https://huggingface.co/lllyasviel/sd_control_collection/resolve/main/diffusers_xl_canny_full.safetensors?download=true)
- controlnet: diffusers_xl_depth_full.safetensors [https://huggingface.co/lllyasviel/sd_control_collection/resolve/main/diffusers_xl_depth_full.safetensors?download=true](https://huggingface.co/lllyasviel/sd_control_collection/resolve/main/diffusers_xl_depth_full.safetensors?download=true)

- ipadapter: ip-adapter_sd15.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter_sd15.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter_sd15.safetensors)
- ipadapter: ip-adapter_sd15_light_v11.bin [https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter_sd15_light_v11.bin](https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter_sd15_light_v11.bin)
- ipadapter: ip-adapter-plus_sd15.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter-plus_sd15.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter-plus_sd15.safetensors)
- ipadapter: ip-adapter-plus-face_sd15.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter-plus-face_sd15.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter-plus-face_sd15.safetensors)
- ipadapter: ip-adapter-full-face_sd15.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter-full-face_sd15.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter-full-face_sd15.safetensors)
- ipadapter: ip-adapter_sd15_vit-G.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter_sd15_vit-G.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/models/ip-adapter_sd15_vit-G.safetensors)
- ipadapter: ip-adapter_sdxl_vit-h.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/ip-adapter_sdxl_vit-h.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/ip-adapter_sdxl_vit-h.safetensors)
- ipadapter: ip-adapter-plus_sdxl_vit-h.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/ip-adapter-plus_sdxl_vit-h.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/ip-adapter-plus_sdxl_vit-h.safetensors)
- ipadapter: ip-adapter-plus-face_sdxl_vit-h.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/ip-adapter-plus-face_sdxl_vit-h.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/ip-adapter-plus-face_sdxl_vit-h.safetensors)
- ipadapter: ip-adapter_sdxl.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/ip-adapter_sdxl.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/ip-adapter_sdxl.safetensors)

- clip_vision: CLIP-ViT-bigG-14-laion2B-39B-b160k.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/image_encoder/model.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/image_encoder/model.safetensors)
- clip_vision: CLIP-ViT-H-14-laion2B-s32B-b79K.safetensors [https://huggingface.co/h94/IP-Adapter/resolve/main/models/image_encoder/model.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/models/image_encoder/model.safetensors)

- upscale_models: 4x-UltraSharp.pth [https://huggingface.co/philz1337x/upscaler/resolve/main/4x-UltraSharp.pth?download=true](https://huggingface.co/philz1337x/upscaler/resolve/main/4x-UltraSharp.pth?download=true)

- embeddings: negativeXL_D.safetensors [https://civitai.com/api/download/models/134583](https://civitai.com/api/download/models/134583)
- embeddings: BadDream.pt [https://civitai.com/api/download/models/77169](https://civitai.com/api/download/models/77169)
- embeddings: UnrealisticDream.pt [https://civitai.com/api/download/models/77173](https://civitai.com/api/download/models/77173)

- temp_unet: iclight_sd15_fbc_unet_ldm.safetensors [https://huggingface.co/huchenlei/IC-Light-ldm/resolve/main/iclight_sd15_fbc_unet_ldm.safetensors?download=true](https://huggingface.co/huchenlei/IC-Light-ldm/resolve/main/iclight_sd15_fbc_unet_ldm.safetensors?download=true)
- temp_unet: iclight_sd15_fc_unet_ldm.safetensors [https://huggingface.co/huchenlei/IC-Light-ldm/resolve/main/iclight_sd15_fc_unet_ldm.safetensors?download=true](https://huggingface.co/huchenlei/IC-Light-ldm/resolve/main/iclight_sd15_fc_unet_ldm.safetensors?download=true)

- rembg: RMBG-1.4.pth [https://huggingface.co/briaai/RMBG-1.4/resolve/main/model.pth](https://huggingface.co/briaai/RMBG-1.4/resolve/main/model.pth)

## Citation 感谢

Special thanks to [Comflowy](https://github.com/6174/comflowy) which lead me to the wonderful world of Stable Diffusion and ComfyUI! It is a comprehensive tutorial for beginners to learn Stable Diffusion. My workflow is essentially an implementation of most techniques in the tutorial.

感谢 [Comflowy](https://github.com/6174/comflowy)，它引领我进入 Stable Diffusion 和 ComfyUI 的神奇世界！它是一套全面的 Stable Diffusion 入门教程。我的工作流，基本上就是把其中教的技巧实现出来了。
