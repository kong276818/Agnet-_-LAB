# ReAct: Synergizing Reasoning and Acting in Language Models

> 논문: [ReAct: Synergizing Reasoning and Acting in Language Models](https://arxiv.org/abs/2210.03629)  
> 저자: Shinn et al. (2022)  
> 목적: LLM의 **추론(Reasoning)**과 **행동(Acting)** 능력을 결합해 상호작용적이고 신뢰성 있는 문제 해결 능력 강화

---

## 개요

기존의 LLM 연구는 추론 능력 (예: Chain-of-Thought)과 행동 생성 능력을 별도로 다루었습니다.  
**ReAct**는 인간의 사고와 유사한 형태로 **"생각(Thought)"과 "행동(Action)"을 결합**하여, LLM이 외부 환경과 상호작용하며 **더 정확하고 유연한 문제 해결**을 수행하도록 설계된 새로운 접근 방식입니다.

---

## 🔑 핵심 개념

### Thought-Action-Observation 순환 구조
- **Thought**: 내적 추론 및 계획을 언어로 표현 (환경 영향 X)
- **Action**: 외부 API 또는 툴과 상호작용
- **Observation**: Action 이후 외부로부터 받은 피드백

### Reason ↔ Act 시너지
- **Reason to Act**: 추론이 행동 계획, 예외 처리 등에 기여
- **Act to Reason**: 행동이 외부 정보 획득 → 추론 강화

### 강화된 Action Space
- 기존 행동 공간 외에 **언어 공간(Language Action)** 도 포함
- 언어 기반 Thought는 직접 행동은 아니지만 추론에 핵심적 기여

---

##  주요 실험 결과

| 벤치마크 | 성능 향상 | 설명 |
|----------|-----------|------|
| **HotpotQA / FEVER** | 사실 오류(Hallucination) 개선 | 위키 API 활용하여 정확도 향상 |
| **ALFWorld** | +34% 성공률 | IM 및 RL보다 우수한 행동 기반 탐색 |
| **WebShop** | +10% 성공률 | 고정된 프롬프트에서도 학습 없이 높은 성능 |
| **ReAct vs CoT-SC** | 향상된 성능 | 내부 지식 + 외부 정보 통합 가능 |

---

## 🆚 비교 요약

| 접근 방식 | 장점 | 단점 | ReAct와의 차이 |
|-----------|------|------|----------------|
| **Standard Prompting** | 단순함 | 복잡한 문제 해결 불가 | Thought/Action 결여 |
| **Chain-of-Thought (CoT)** | 복잡한 추론 가능 | 외부 정보 활용 불가 | 정적 추론, 상호작용 없음 |
| **Act-only** | 환경 조작 가능 | 고수준 계획 부족 | 추론 기반 계획 없음 |
| **WebGPT** | 웹 연동 정보 활용 | RL 기반 비용 높음 | 추론 과정을 명시적으로 학습 |
| **SayCan** | 로봇 행동 제어 | 추론 과정 부족 | 추론과 행동 동시 가능 |
| **Inner Monologue** | 목표 상기 가능 | 유연성 부족 | 다양한 형태의 추론 수행 가능 |

---

## ⚠️ 제한 사항 및 향후 연구

- 프롬프팅 방식의 한계 → 향후 학습 기반 확장 필요
- 다양한 태스크에 대한 일반화 실험 필요
- **강화 학습과의 결합** 가능성 유망

---

## 🧩 결론

**ReAct**는 LLM의 **추론**과 **행동**을 유기적으로 결합함으로써 다음을 실현합니다:

- 외부 환경과의 실시간 상호작용
- Chain-of-Thought 한계 극복 (Hallucination 방지)
- 더 나은 **해석 가능성**, **진단 가능성**, **성능 일관성**
- 인간 유사 사고를 갖춘 **에이전트형 LLM** 구현 기반

---

## 📚 참고

- 논문: https://arxiv.org/abs/2210.03629
- 관련 코드: https://github.com/ysymyth/ReAct

---https://danjookkong.tistory.com/55 정리 사이트

> 이 문서는 [ReAct 논문](https://arxiv.org/abs/2210.03629)에 기반한 비공식 요약입니다.
