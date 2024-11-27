# comfyui-workflow-versatile

[🇬🇧 EN](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/README.md) | [🇨🇳 中文](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/README_ZH_CN.md)

通用 ComfyUI 工作流，适用于多种常见用途。是我应对多种任务的首选工作流。

## 下载

- [⏬ versatile-flux](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/versatile-flux.json)
- [⏬ versatile-sd](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/versatile-sd.json)
- [⏬ versatile-pony](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/versatile-pony.json)

适用于SDXL及SD1.5的万能工作流示例：

![](https://github.com/greenzorro/comfyui-workflow-versatile/blob/main/versatile-sd.png?raw=true)

提示：  
- `versatile-flux` 能力最齐全。
- `versatile-sd` 能力也非常齐全，适合大多数低显存的使用场景。
- Pony diffusion不支持IPadapter。
- 暂无计划推出SD3.5的工作流。

## 使用

以 `versatile-sd` 为例子，其中包含 IPadapter、ControlNet、IC light、LLM 提示词生成、背景移除等高级技术，它擅长 **文生图、图像混合、风格迁移、风格探索、局部重绘、扩图、重新打光**。

集如此多种功能于一身，因此你需要了解 Stable Diffusion 和 ComfyUI 的工作原理，才能根据不同目的调整节点的连线。默认的连线配置是文生图。

理解整个工作流程后，才能充分发挥其潜力。

## 使用前提

### 节点

| Node                         | Link                                                                                                                               |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| ComfyUI_Essentials           | [https://github.com/cubiq/ComfyUI_essentials.git](https://github.com/cubiq/ComfyUI_essentials.git)                                 |
| ComfyUI-Easy-Use             | [https://github.com/yolain/ComfyUI-Easy-Use.git](https://github.com/yolain/ComfyUI-Easy-Use.git)                                   |
| ComfyUI-Custom-Scripts       | [https://github.com/pythongosssss/ComfyUI-Custom-Scripts.git](https://github.com/pythongosssss/ComfyUI-Custom-Scripts.git)         |
| ComfyUI-GGUF                 | [https://github.com/city96/ComfyUI-GGUF.git](https://github.com/city96/ComfyUI-GGUF.git)                                           |
| ComfyUI_IPAdapter_plus       | [https://github.com/cubiq/ComfyUI_IPAdapter_plus.git](https://github.com/cubiq/ComfyUI_IPAdapter_plus.git)                         |
| comfyui_controlnet_aux       | [https://github.com/Fannovel16/comfyui_controlnet_aux.git](https://github.com/Fannovel16/comfyui_controlnet_aux.git)               |
| ComfyUI-Anyline              | [https://github.com/TheMistoAI/ComfyUI-Anyline.git](https://github.com/TheMistoAI/ComfyUI-Anyline.git)                             |
| ComfyUI-layerdiffuse         | [https://github.com/huchenlei/ComfyUI-layerdiffuse.git](https://github.com/huchenlei/ComfyUI-layerdiffuse.git)                     |
| ComfyUI-IC-Light             | [https://github.com/huchenlei/ComfyUI-IC-Light.git](https://github.com/huchenlei/ComfyUI-IC-Light.git)                             |
| ComfyUI_UltimateSDUpscale    | [https://github.com/ssitu/ComfyUI_UltimateSDUpscale.git](https://github.com/ssitu/ComfyUI_UltimateSDUpscale.git)                   |
| ComfyUI-IPAdapter-Flux       | [https://github.com/Shakker-Labs/ComfyUI-IPAdapter-Flux.git](https://github.com/Shakker-Labs/ComfyUI-IPAdapter-Flux.git)           |
| ComfyUI-Tara-LLM-Integration | [https://github.com/ronniebasak/ComfyUI-Tara-LLM-Integration.git](https://github.com/ronniebasak/ComfyUI-Tara-LLM-Integration.git) |

### 模型（SDXL和SD1.5）

| Dir            | Model                                          | Link                                                                                                                                                                                                                                             |
| -------------- | ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| checkpoints    | DreamShaperXL_Lightning.safetensors            | [https://huggingface.co/Lykon/dreamshaper-xl-lightning/resolve/main/DreamShaperXL_Lightning.safetensors?download=true](https://huggingface.co/Lykon/dreamshaper-xl-lightning/resolve/main/DreamShaperXL_Lightning.safetensors?download=true)     |
| checkpoints    | dreamshaperXL_lightningInpaint.safetensors     | [https://civitai.com/api/download/models/450187](https://civitai.com/api/download/models/450187)                                                                                                                                                 |
| checkpoints    | DreamShaper_8_pruned.safetensors               | [https://huggingface.co/Lykon/DreamShaper/resolve/main/DreamShaper_8_pruned.safetensors?download=true](https://huggingface.co/Lykon/DreamShaper/resolve/main/DreamShaper_8_pruned.safetensors?download=true)                                     |
| unet           | iclight_sd15_fbc_unet_ldm.safetensors          | [https://huggingface.co/huchenlei/IC-Light-ldm/resolve/main/iclight_sd15_fbc_unet_ldm.safetensors?download=true](https://huggingface.co/huchenlei/IC-Light-ldm/resolve/main/iclight_sd15_fbc_unet_ldm.safetensors?download=true)                 |
| unet           | iclight_sd15_fc_unet_ldm.safetensors           | [https://huggingface.co/huchenlei/IC-Light-ldm/resolve/main/iclight_sd15_fc_unet_ldm.safetensors?download=true](https://huggingface.co/huchenlei/IC-Light-ldm/resolve/main/iclight_sd15_fc_unet_ldm.safetensors?download=true)                   |
| clip_vision    | CLIP-ViT-bigG-14-laion2B-39B-b160k.safetensors | [https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/image_encoder/model.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/image_encoder/model.safetensors)                                                 |
| embeddings     | negativeXL_D.safetensors                       | [https://civitai.com/api/download/models/134583](https://civitai.com/api/download/models/134583)                                                                                                                                                 |
| embeddings     | BadDream.pt                                    | [https://civitai.com/api/download/models/77169](https://civitai.com/api/download/models/77169)                                                                                                                                                   |
| embeddings     | UnrealisticDream.pt                            | [https://civitai.com/api/download/models/77173](https://civitai.com/api/download/models/77173)                                                                                                                                                   |
| controlnet     | mistoLine_rank256.safetensors                  | [https://huggingface.co/TheMistoAI/MistoLine/resolve/main/mistoLine_rank256.safetensors?download=true](https://huggingface.co/TheMistoAI/MistoLine/resolve/main/mistoLine_rank256.safetensors?download=true)                                     |
| controlnet     | diffusers_xl_canny_full.safetensors            | [https://huggingface.co/lllyasviel/sd_control_collection/resolve/main/diffusers_xl_canny_full.safetensors?download=true](https://huggingface.co/lllyasviel/sd_control_collection/resolve/main/diffusers_xl_canny_full.safetensors?download=true) |
| controlnet     | diffusers_xl_depth_full.safetensors            | [https://huggingface.co/lllyasviel/sd_control_collection/resolve/main/diffusers_xl_depth_full.safetensors?download=true](https://huggingface.co/lllyasviel/sd_control_collection/resolve/main/diffusers_xl_depth_full.safetensors?download=true) |
| ipadapter      | ip-adapter_sdxl.safetensors                    | [https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/ip-adapter_sdxl.safetensors](https://huggingface.co/h94/IP-Adapter/resolve/main/sdxl_models/ip-adapter_sdxl.safetensors)                                                         |
| upscale_models | 4x-UltraSharp.pth                              | [https://huggingface.co/philz1337x/upscaler/resolve/main/4x-UltraSharp.pth?download=true](https://huggingface.co/philz1337x/upscaler/resolve/main/4x-UltraSharp.pth?download=true)                                                               |
| loras          | add-detail-xl.safetensors                      | [https://civitai.com/api/download/models/135867?type=Model&format=SafeTensor](https://civitai.com/api/download/models/135867?type=Model&format=SafeTensor)                                                                                       |

### 模型（Pony）

| Dir         | Model                                                                | Link                                                                                                                                                                                                                                                                   |
| ----------- | -------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| checkpoints | ponyDiffusionV6XL_v6.safetensors                                     | [https://huggingface.co/Magamanny/Pony-Diffusion-V6-XL/resolve/main/ponyDiffusionV6XL_v6StartWithThisOne.safetensors?download=true](https://huggingface.co/Magamanny/Pony-Diffusion-V6-XL/resolve/main/ponyDiffusionV6XL_v6StartWithThisOne.safetensors?download=true) |
| embeddings  | zPDXL3.safetensors                                                   | [https://civitai.com/api/download/models/720175?type=Model&format=SafeTensor](https://civitai.com/api/download/models/720175?type=Model&format=SafeTensor)                                                                                                             |
| embeddings  | zPDXLxxx.pt                                                          | [https://civitai.com/api/download/models/380277?type=Model&format=PickleTensor](https://civitai.com/api/download/models/380277?type=Model&format=PickleTensor)                                                                                                         |
| embeddings  | zPDXLxxx-neg.pt                                                      | [https://civitai.com/api/download/models/380277?type=Negative&format=Other](https://civitai.com/api/download/models/380277?type=Negative&format=Other)                                                                                                                 |
| embeddings  | zPDXLpg.pt                                                           | [https://civitai.com/api/download/models/380285?type=Model&format=PickleTensor](https://civitai.com/api/download/models/380285?type=Model&format=PickleTensor)                                                                                                         |
| embeddings  | zPDXLpg-neg.pt                                                       | [https://civitai.com/api/download/models/380285?type=Negative&format=Other](https://civitai.com/api/download/models/380285?type=Negative&format=Other)                                                                                                                 |
| controlnet  | mistoLine_rank256.safetensors                                        | [https://huggingface.co/TheMistoAI/MistoLine/resolve/main/mistoLine_rank256.safetensors?download=true](https://huggingface.co/TheMistoAI/MistoLine/resolve/main/mistoLine_rank256.safetensors?download=true)                                                           |
| controlnet  | diffusers_xl_canny_full.safetensors                                  | [https://huggingface.co/lllyasviel/sd_control_collection/resolve/main/diffusers_xl_canny_full.safetensors?download=true](https://huggingface.co/lllyasviel/sd_control_collection/resolve/main/diffusers_xl_canny_full.safetensors?download=true)                       |
| controlnet  | diffusers_xl_depth_full.safetensors                                  | [https://huggingface.co/lllyasviel/sd_control_collection/resolve/main/diffusers_xl_depth_full.safetensors?download=true](https://huggingface.co/lllyasviel/sd_control_collection/resolve/main/diffusers_xl_depth_full.safetensors?download=true)                       |
| loras       | Pony_DetailV2.0.safetensors                                          | [https://civitai.com/api/download/models/449738?type=Model&format=SafeTensor](https://civitai.com/api/download/models/449738?type=Model&format=SafeTensor)                                                                                                             |
| loras       | Anime_Style_2_SDXL_LoRA_Pony_Diffusion_V6_XL.safetensors             | [https://civitai.com/api/download/models/333590?type=Model&format=SafeTensor](https://civitai.com/api/download/models/333590?type=Model&format=SafeTensor)                                                                                                             |
| loras       | Smooth_Anime_2_Style_SDXL_LoRA_Pony_Diffusion_V6_XL.safetensors      | [https://civitai.com/api/download/models/333607?type=Model&format=SafeTensor](https://civitai.com/api/download/models/333607?type=Model&format=SafeTensor)                                                                                                             |
| loras       | Anime_Summer_Days_2_Style_SDXL_LoRA_Pony_Diffusion_V6_XL.safetensors | [https://civitai.com/api/download/models/372898?type=Model&format=SafeTensor](https://civitai.com/api/download/models/372898?type=Model&format=SafeTensor)                                                                                                             |
| loras       | Watercolor_Anime_Style_LoRA_Pony_XL_v6.safetensors                   | [https://civitai.com/api/download/models/725772?type=Model&format=SafeTensor](https://civitai.com/api/download/models/725772?type=Model&format=SafeTensor)                                                                                                             |
| loras       | LineArt_Mono_Style_LoRA_Pony_XL_v6.safetensors                       | [https://civitai.com/api/download/models/450029?type=Model&format=SafeTensor](https://civitai.com/api/download/models/450029?type=Model&format=SafeTensor)                                                                                                             |

### 模型（Flux）

| Dir            | Model                               | Link                                                                                                                                                                                                                                                               |
| -------------- | ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| unet           | flux1-dev-Q4_1.gguf                 | [https://huggingface.co/city96/FLUX.1-dev-gguf/resolve/main/flux1-dev-Q4_1.gguf?download=true](https://huggingface.co/city96/FLUX.1-dev-gguf/resolve/main/flux1-dev-Q4_1.gguf?download=true)                                                                       |
| unet           | flux1-dev-Q6_K.gguf                 | [https://huggingface.co/city96/FLUX.1-dev-gguf/resolve/main/flux1-dev-Q6_K.gguf?download=true](https://huggingface.co/city96/FLUX.1-dev-gguf/resolve/main/flux1-dev-Q6_K.gguf?download=true)                                                                       |
| unet           | flux1-fill-dev-fp16-Q4_0-GGUF.gguf  | [https://huggingface.co/SporkySporkness/FLUX.1-Fill-dev-GGUF/resolve/main/flux1-fill-dev-fp16-Q4_0-GGUF.gguf?download=true](https://huggingface.co/SporkySporkness/FLUX.1-Fill-dev-GGUF/resolve/main/flux1-fill-dev-fp16-Q4_0-GGUF.gguf?download=true)             |
| unet           | flux1-canny-dev-fp16-Q4_0-GGUF.gguf | [https://huggingface.co/SporkySporkness/FLUX.1-Canny-dev-GGUF/resolve/main/flux1-canny-dev-fp16-Q4_0-GGUF.gguf?download=true](https://huggingface.co/SporkySporkness/FLUX.1-Canny-dev-GGUF/resolve/main/flux1-canny-dev-fp16-Q4_0-GGUF.gguf?download=true)         |
| unet           | flux1-depth-dev-fp16-Q4_0-GGUF.gguf | [https://huggingface.co/SporkySporkness/FLUX.1-Depth-dev-GGUF/resolve/main/flux1-depth-dev-fp16-Q4_0-GGUF.gguf?download=true](https://huggingface.co/SporkySporkness/FLUX.1-Depth-dev-GGUF/resolve/main/flux1-depth-dev-fp16-Q4_0-GGUF.gguf?download=true)         |
| clip           | clip_l.safetensors                  | [https://huggingface.co/Comfy-Org/stable-diffusion-3.5-fp8/resolve/main/text_encoders/clip_l.safetensors?download=true](https://huggingface.co/Comfy-Org/stable-diffusion-3.5-fp8/resolve/main/text_encoders/clip_l.safetensors?download=true)                     |
| clip           | clip_g.safetensors                  | [https://huggingface.co/Comfy-Org/stable-diffusion-3.5-fp8/resolve/main/text_encoders/clip_g.safetensors?download=true](https://huggingface.co/Comfy-Org/stable-diffusion-3.5-fp8/resolve/main/text_encoders/clip_g.safetensors?download=true)                     |
| clip           | t5xxl_fp8_e4m3fn.safetensors        | [https://huggingface.co/Comfy-Org/stable-diffusion-3.5-fp8/resolve/main/text_encoders/t5xxl_fp8_e4m3fn.safetensors?download=true](https://huggingface.co/Comfy-Org/stable-diffusion-3.5-fp8/resolve/main/text_encoders/t5xxl_fp8_e4m3fn.safetensors?download=true) |
| clip_vision    | sigclip_patch14-384.safetensors     | [https://huggingface.co/google/siglip-so400m-patch14-384/resolve/main/model.safetensors?download=true](https://huggingface.co/google/siglip-so400m-patch14-384/resolve/main/model.safetensors?download=true)                                                       |
| vae            | flux-ae.safetensors                 | [https://huggingface.co/black-forest-labs/FLUX.1-dev/resolve/main/flux-ae.safetensors](https://huggingface.co/black-forest-labs/FLUX.1-dev/resolve/main/flux-ae.safetensors)                                                                                       |
| ipadapter-flux | FLUX.1-dev-IP-Adapter.bin           | [https://huggingface.co/InstantX/FLUX.1-dev-IP-Adapter/resolve/main/ip-adapter.bin?download=true](https://huggingface.co/InstantX/FLUX.1-dev-IP-Adapter/resolve/main/ip-adapter.bin?download=true)                                                                 |
| loras          | film-storyboard.safetensors         | [https://huggingface.co/ali-vilab/In-Context-LoRA/resolve/main/film-storyboard.safetensors?download=true](https://huggingface.co/ali-vilab/In-Context-LoRA/resolve/main/film-storyboard.safetensors?download=true)                                                 |
| loras          | portrait-illustration.safetensors   | [https://huggingface.co/ali-vilab/In-Context-LoRA/resolve/main/portrait-illustration.safetensors?download=true](https://huggingface.co/ali-vilab/In-Context-LoRA/resolve/main/portrait-illustration.safetensors?download=true)                                     |
| loras          | portrait-photography.safetensors    | [https://huggingface.co/ali-vilab/In-Context-LoRA/resolve/main/portrait-photography.safetensors?download=true](https://huggingface.co/ali-vilab/In-Context-LoRA/resolve/main/portrait-photography.safetensors?download=true)                                       |
| loras          | visual-identity-design.safetensors  | [https://huggingface.co/ali-vilab/In-Context-LoRA/resolve/main/visual-identity-design.safetensors?download=true](https://huggingface.co/ali-vilab/In-Context-LoRA/resolve/main/visual-identity-design.safetensors?download=true)                                   |
| loras          | IC_CONSIS_v3_e10.safetensors        | [https://civitai.com/api/download/models/1085884?type=Model&format=SafeTensor](https://civitai.com/api/download/models/1085884?type=Model&format=SafeTensor)                                                                                                       |
| loras          | IC_TRY_ON_v3_e4.safetensors         | [https://civitai.com/api/download/models/1063742?type=Model&format=SafeTensor](https://civitai.com/api/download/models/1063742?type=Model&format=SafeTensor)                                                                                                       |
| loras          | figures_TTP_Migration.safetensors   | [https://huggingface.co/TTPlanet/Migration_Lora_flux/resolve/main/figures_TTP_Migration.safetensors?download=true](https://huggingface.co/TTPlanet/Migration_Lora_flux/resolve/main/figures_TTP_Migration.safetensors?download=true)                               |
| style_models   | flux1-redux-dev.safetensors         | [https://huggingface.co/black-forest-labs/FLUX.1-Redux-dev/resolve/main/flux1-redux-dev.safetensors?download=true](https://huggingface.co/black-forest-labs/FLUX.1-Redux-dev/resolve/main/flux1-redux-dev.safetensors?download=true)                               |

### 模型（其他）

| Dir            | Model             | Link                                                                                                                                                                               |
| -------------- | ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| upscale_models | 4x-UltraSharp.pth | [https://huggingface.co/philz1337x/upscaler/resolve/main/4x-UltraSharp.pth?download=true](https://huggingface.co/philz1337x/upscaler/resolve/main/4x-UltraSharp.pth?download=true) |
| rembg          | RMBG-1.4.pth      | [https://huggingface.co/briaai/RMBG-1.4/resolve/main/model.pth](https://huggingface.co/briaai/RMBG-1.4/resolve/main/model.pth)                                                     |

## 感谢

感谢 [Comflowy](https://github.com/6174/comflowy)，它引领我进入 Stable Diffusion 和 ComfyUI 的奇妙世界！这是一套全面的 Stable Diffusion 入门教程。我的工作流基本上就是把其中教的技巧实现并整合起来而已。
