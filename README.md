# llama3_kids_news
이 프로젝트는 성인용 뉴스 기사를 입력하면, 이를 초등학생이 이해하기 쉬운 뉴스로 자동 변환하는 시스템입니다.
최신 언어 모델 LLaMA3를 활용해 문장을 재작성하며, 크롤링부터 전처리, 유사도 기반 학습 가중치 부여, 파인튜닝, 추론까지 전 과정을 포함합니다.

---

## 🧩 주요 구성
| 모듈                                 | 설명                        |
| ---------------------------------- | ------------------------- |
| `crawl_daum_news.ipynb`               | 다음 뉴스 크롤링 및 저장            |
| `preprocess_keyword_similarity.ipynb` | 키워드 기반 요약 및 문장 유사도 계산     |
| `fill_missing_keywords.ipynb`         | 키워드 누락 행 자동 보완            |
| `train_llama3.ipynb`                  | LLaMA3 모델 파인튜닝 (QLoRA 기반) |
| `infer_llama3.ipynb`                  | 학습된 모델로 어린이용 뉴스 생성        |

---

## 🚀 프로젝트 실행 흐름
1. crawl_daum_news.ipynb 실행 → 뉴스 수집

2. preprocess_keyword_similarity.ipynb 실행 → 키워드 추출, 문장쌍 및 유사도 계산

3. fill_missing_keywords.ipynb → 누락된 키워드 자동 보완

4. Llama3_finetuning.ipynb → 가중치 기반 학습 데이터로 LLaMA3 파인튜닝

5. Llama3_infer.ipynb → 성인 문장을 어린이 문장으로 변환


## 🧠 모델 관련 정보
사용 모델: beomi/Llama-3-Open-Ko-8B (QLoRA 적용)

학습 방식: LoRA (low-rank adaptation) + 가중치 부여

학습 입력: 성인 문장 + 어린이 문장 + 유사도 점수

추론 출력: 어린이 친화적 뉴스
