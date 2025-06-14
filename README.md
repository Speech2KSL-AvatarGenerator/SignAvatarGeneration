# ✋ Sign Language Avatar Generator using ComfyUI

본 프로젝트는 ComfyUI 기반으로 Stable Diffusion + ControlNet + DWPose를 활용하여 **수어 아바타 영상**을 생성하는 파이프라인을 구성한 결과물입니다.

## 구성 모델
- Stable Diffusion v1.5 (`.safetensors`)
- ControlNet (OpenPose)
- DWPose (Pose 추출)

## 사용 도구
- ComfyUI
- Python 3.10
- CUDA 11.x + PyTorch
- OpenPose (기본 or DWPose 기반)


## 폴더
```
sign-avatar-comfyui/
├── workflows/             
│   └── sign_avatar_workflow.json
├── models/                
│   ├── control_v11p_sd15_openpose.pth
│   ├── control_v11p_sd15_softedge.pth
│   ├── add_detail.safetensors
│   ├── lcm-lora-sd15.safetensors
│   ├── vae-ft-mse-840000-ema-pruned.safetensors
│   └── majicMIX_realistic_v6.safetensors
├── input/
│   ├── SCUSHPAKOKSL2200000001.mp4
├── outputs/               
    ├── output_frames/
    └── animated_output_filtered.avi
    └── animated_output0.mp4
    └── AnimateDiff_00001.gif
    └── sign_model_test_news_5sec_output.mp4

```


## 사용법

1. [ComfyUI 설치](https://github.com/comfyanonymous/ComfyUI) 후 실행
2. `workflows/sign_avatar_workflow.json` 파일을 로드
3. 필요한 모델 (`.safetensors`, `.pth`)은 직접 다운로드하여 `models/` 폴더에 넣기
4. 노드 연결 후 실행하여 이미지 또는 영상 생성

## 📦 결과물
<p align="center">
    <img src="https://github.com/user-attachments/assets/8b7ec895-33dc-498d-a78c-490159a7e550" width="45%" />
    <img src="https://github.com/user-attachments/assets/505941af-df9f-4774-a169-35737db9586d" width="45%" />
</p>

## 필요한 모델

| 파일명                                          | 설명                                              | 다운로드 링크                                                                                                                                                                                                                               |
| -------------------------------------------- | ----------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **control\_v11p\_sd15\_openpose.pth**        | 사람의 포즈(Keypoints)를 인식하여 아바타에 반영하는 ControlNet 모델 | 🔗 [https://huggingface.co/lllyasviel/ControlNet-v1-1/resolve/main/control\_v11p\_sd15\_openpose.pth](https://huggingface.co/lllyasviel/ControlNet-v1-1/resolve/main/control_v11p_sd15_openpose.pth)                                  |
| **control\_v11p\_sd15\_softedge.pth**        | 이미지의 외곽선(에지)를 활용하는 ControlNet 모델                | 🔗 [https://huggingface.co/lllyasviel/ControlNet-v1-1/resolve/main/control\_v11p\_sd15\_softedge.pth](https://huggingface.co/lllyasviel/ControlNet-v1-1/resolve/main/control_v11p_sd15_softedge.pth)                                  |
| **add\_detail.safetensors**                  | 얼굴·손 디테일 묘사를 개선하는 LoRA                          | 🔗 [https://civitai.com/api/download/models/13536](https://civitai.com/api/download/models/13536)                                                                                                                                     |
| **lcm-lora-sd15.safetensors**                | 이미지 생성 속도 향상을 위한 LCM LoRA                       | 🔗 [https://huggingface.co/latent-consistency/lcm-lora-sd15/resolve/main/pytorch\_lora\_weights.safetensors](https://huggingface.co/latent-consistency/lcm-lora-sd15/resolve/main/pytorch_lora_weights.safetensors)                   |
| **vae-ft-mse-840000-ema-pruned.safetensors** | 색감, 명암 등을 정교하게 보정해주는 VAE 모델                     | 🔗 [https://huggingface.co/stabilityai/sd-vae-ft-mse-original/resolve/main/vae-ft-mse-840000-ema-pruned.safetensors](https://huggingface.co/stabilityai/sd-vae-ft-mse-original/resolve/main/vae-ft-mse-840000-ema-pruned.safetensors) |
| **majicMIX\_realistic\_v6.safetensors**      | Stable Diffusion용 체크포인트 모델 (현실적 이미지 생성)         | 🔗 [https://civitai.com/api/download/models/130072](https://civitai.com/api/download/models/130072)                                                                                                                                   |


