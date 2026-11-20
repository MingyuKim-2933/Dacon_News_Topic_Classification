# Dacon 뉴스 토픽 분류 AI 경진대회

한국어 뉴스 헤드라인으로 기사의 주제를 7가지로 분류하는 DACON 대회 참가 코드입니다. 데이터는 KLUE 벤치마크의 YNAT(연합뉴스 헤드라인 주제 분류) 데이터셋입니다.

## 결과

KoBERT, KoELECTRA, KcELECTRA 세 모델을 같은 조건으로 비교했고, KoBERT가 가장 좋아 최종 제출에 사용했습니다.

- **Public 21 / 256, Private 11 / 256 (상위 5%)**
- 최종 코드: `News_Topic_Classification_KoBERT.ipynb`

![leaderboard](https://user-images.githubusercontent.com/68273065/149282191-a17e998a-5529-43f1-a8fe-0756bfe32ad2.png)

## 노트북 구성

| 파일 | 모델 |
|---|---|
| `News_Topic_Classification_KoBERT.ipynb` | SKT KoBERT (최종 제출) |
| `News_Topic_Classification_KoELECTRA.ipynb` | KoELECTRA |
| `News_Topic_Classification_KcELECTRA.ipynb` | KcELECTRA |

## KoBERT 학습 설정

| 항목 | 값 |
|---|---|
| 최대 길이 | 64 토큰 |
| 배치 | 32 |
| epoch | 10 |
| 학습률 | 4e-5 (AdamW) |
| 스케줄러 | cosine + warmup 10% |
| 분류기 | [CLS] 출력(768) → 드롭아웃 0.5 → Linear(7) |
| 기타 | gradient clipping |

## 실행

Google Colab GPU 환경에서 노트북을 위에서부터 순서대로 실행합니다. 마지막 셀에서 제출용 CSV를 저장합니다. 저장 경로는 본인 Google Drive 경로에 맞게 바꿔야 합니다.

## 기술 스택

Python, PyTorch, KoBERT, KoELECTRA, KcELECTRA, transformers, Google Colab

## 주최

DACON
