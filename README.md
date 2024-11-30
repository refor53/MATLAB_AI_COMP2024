# MNIST Classification with ViT model

ViT 모델을 ONNX에서 MATLAB에서 사용할 수 있는 .mat 파일로 변환합니다.
기존에 제공되던 Matlab의 DeepLearning ToolBox의 Vision in Transformer 를 호출하는 대신, 직접 구현하여 모델 구조를 바꿀 수 있도록 구현했습니다.
이후 MNIST 데이터를 분류합니다.

## 사용 데이터
개발 환경(VRAM)의 한계로, MNIST data(32x32)를 기준으로 코드를 작성했습니다.

## 요구사항 

```
bash
pip install -r requirements.txt
```

## 사용법
```
bash
python convert_onnx_to_mat.py --onnx_path ../models/vit_model.onnx --mat_path ../models/vit_weights.mat
```


## 파라미터

- `--onnx_path`: 입력 ONNX 모델 파일 경로
- `--mat_path`: 출력 MATLAB .mat 파일 경로

## 출력 구조

```
변환된 .mat 파일은 다음과 같은 구조를 가집니다:
weights
├── patch_embed
│ ├── proj_weight
│ └── proj_bias
├── cls_token
├── pos_embed
├── blocks (array)
│ ├── attn_weight
│ ├── attn_bias
│ ├── mlp_weight
│ └── mlp_bias
└── norm
├── gamma
└── beta
```
