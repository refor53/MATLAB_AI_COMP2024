# MATLAB_AI_COMP2024
# ONNX to MATLAB Converter

이 스크립트는 ONNX 형식의 ViT 모델을 MATLAB에서 사용할 수 있는 .mat 파일로 변환합니다.

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
