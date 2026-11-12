# Mini GPT

**Building a Mini GPT from Scratch using PyTorch**

PyTorch를 사용하여 GPT(Generative Pre-trained Transformer)의 핵심 구조를 처음부터 구현하는 프로젝트입니다.

Transformer의 작동 원리를 이해하고, 직접 모델을 구현하고 학습시키면서 언어 모델의 구조와 학습 과정을 탐구합니다.

---

## 1. Project Overview

| 항목           | 내용                       |
| ------------ | ------------------------ |
| Project      | Mini GPT                 |
| Framework    | PyTorch                  |
| Language     | Python                   |
| Environment  | Google Colab             |
| Architecture | Decoder-Only Transformer |
| Dataset      | Tiny Shakespeare         |
| Tokenizer    | Character-level          |
| Training     | From Scratch             |

### Project Goals

- Transformer의 핵심 구조 이해
- Self-Attention 및 Multi-Head Attention 직접 구현
- PyTorch를 활용한 GPT 모델 개발
- 텍스트 데이터 학습 및 생성
- 모델 크기와 학습 횟수에 따른 성능 비교

---

## 2. Model Architecture

본 프로젝트는 GPT와 같은 Decoder-Only Transformer 구조를 기반으로 합니다.

### Architecture Components

1. **Character-level Tokenizer**

   - 문자를 정수로 변환
   - 정수를 다시 문자로 복원

2. **Embedding**

   - Token Embedding
   - Position Embedding

3. **Self-Attention**

   - Query, Key, Value 계산
   - Causal Masking 적용

4. **Multi-Head Attention**

   - 여러 Attention Head를 병렬로 사용

5. **Feed Forward Network**

   - Linear Layer
   - ReLU
   - Dropout

6. **Transformer Block**

   - Layer Normalization
   - Residual Connection
   - Attention 및 Feed Forward

7. **Language Model Head**

   - 다음 토큰의 확률 예측
   - Autoregressive Text Generation

---

## 3. Model Configuration

### Baseline Model

| Parameter           |   Value |
| ------------------- | ------: |
| Vocabulary Size     |      65 |
| Embedding Dimension |     128 |
| Attention Heads     |       4 |
| Transformer Blocks  |       4 |
| Batch Size          |      64 |
| Block Size          |     128 |
| Learning Rate       |  0.0003 |
| Parameters          | 824,897 |

---

## 4. Experiments & Results

현재까지 학습 횟수에 따른 성능을 비교했습니다.

### Training Results

| Metric          | 3,000 Iterations | 10,000 Iterations |
| --------------- | ---------------: | ----------------: |
| Parameters      |          824,897 |           824,897 |
| Train Loss      |           1.5702 |            1.3212 |
| Validation Loss |           1.7422 |            1.5480 |
| Training Time   |       143.77 sec |        408.92 sec |

### Analysis

- 학습 횟수를 증가시키면서 Train Loss 감소
- Validation Loss 약 11.15% 개선
- 동일한 모델 구조와 파라미터 수 유지
- 학습 횟수에 따른 텍스트 생성 품질 변화 확인

---

## 5. Project Structure

```text
mini-GPT/
│
├── notebooks/
│   ├── mini_gpt_baseline_3000.ipynb
│   └── mini_gpt_train_10000.ipynb
│
├── results/
│
├── README.md
│
└── requirements.txt
```

---

## 6. Development Environment

- Python
- PyTorch
- Google Colab
- CUDA / GPU
- GitHub

### Dataset

Tiny Shakespeare

[https://github.com/karpathy/char-rnn](https://github.com/karpathy/char-rnn)

---

## 7. Roadmap

- [x] Tiny Shakespeare 데이터셋 준비
- [x] Character-level Tokenizer 구현
- [x] Self-Attention 구현
- [x] Multi-Head Attention 구현
- [x] Feed Forward Network 구현
- [x] Transformer Block 구현
- [x] GPT Language Model 구현
- [x] 3,000회 학습 실험
- [x] 10,000회 학습 실험
- [ ] 모델 크기 변경 실험
- [ ] Tokenizer 개선
- [ ] 한국어 데이터셋 학습
- [ ] 모델 성능 비교 및 분석

---

## 8. Future Plans

향후 다음과 같은 실험을 진행할 예정입니다.

1. Embedding Dimension 및 Transformer Block 변경
2. 모델 파라미터 수에 따른 성능 비교
3. Character-level과 Subword Tokenizer 비교
4. 한국어 데이터셋을 활용한 언어 모델 학습
5. 모델 구조 및 학습 방법 개선

---

## 9. References

- [Attention Is All You Need (2017)](https://arxiv.org/abs/1706.03762)
- [nanoGPT](https://github.com/karpathy/nanoGPT)
- [PyTorch Documentation](https://pytorch.org/docs/stable/index.html)
- [Tiny Shakespeare Dataset](https://github.com/karpathy/char-rnn)

---

**This project is developed for educational purposes to understand and implement GPT architecture from scratch.**
