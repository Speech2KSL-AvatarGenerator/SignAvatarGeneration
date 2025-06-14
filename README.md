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
├── README.md
├── requirements.txt       # 필요 라이브러리 목록 (선택)
├── workflows/             # ComfyUI 워크플로우 저장 파일
│   └── sign_avatar_workflow.json
├── models/                # 모델 가중치 (올리거나, 링크만 제공)
│   ├── stable_diffusion_model.safetensors (optional)
│   └── controlnet_openpose.pth (optional)
├── outputs/               # 예시 생성 이미지나 영상
│   ├── example1.png
│   └── example2.mp4
└── docs/                  # 추가 설명 이미지 또는 구조도 (선택)
    └── pipeline_diagram.png
```

## 사용법

1. [ComfyUI 설치](https://github.com/comfyanonymous/ComfyUI) 후 실행
2. `workflows/sign_avatar_workflow.json` 파일을 로드
3. 필요한 모델 (`.safetensors`, `.pth`)은 직접 다운로드하여 `models/` 폴더에 넣기
4. 노드 연결 후 실행하여 이미지 또는 영상 생성

## 📦 결과물
<p align="center">
  <img src="https://github.com/user-attachments/assets/8d81a8fd-eea2-4fe0-a3c7-c9357699e04f" height="300px" style="display:inline-block; max-width:45%; margin-right:10px;" />
  <img src="https://github.com/user-attachments/assets/92a5146c-9ae3-495f-a2a2-d2be6fb50d36" height="300px" style="display:inline-block; max-width:45%;" />
</p>



