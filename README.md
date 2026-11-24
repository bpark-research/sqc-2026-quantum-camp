# 2026 서울퀀텀캠퍼스 양자컴퓨팅 활용과정 겨울캠프 · 실습 자료

**Day 3–4 실습 노트북** (CUDA-Q) · 연세대학교 박병규

| 날짜 | 주제 | 노트북 |
|---|---|---|
| 12/2 (수) | CUDA-Q 기반 양자 보행 (Quantum Walk) | [`day3-quantum-walk/day3_quantum_walk.ipynb`](day3-quantum-walk/day3_quantum_walk.ipynb) |
| 12/3 (목) | CUDA-Q 기반 Quantum-HPC 하이브리드 AI | [`day4-hybrid-ai/day4_hybrid_ai.ipynb`](day4-hybrid-ai/day4_hybrid_ai.ipynb) |

### 풀이 노트북 (`solutions/`)
빈칸이 모두 채워져 있고, 실행 결과와 그래프까지 들어 있는 완성본입니다.
- [`solutions/day3_quantum_walk_solution.ipynb`](solutions/day3_quantum_walk_solution.ipynb)
- [`solutions/day4_hybrid_ai_solution.ipynb`](solutions/day4_hybrid_ai_solution.ipynb)

언제 열어 볼지는 여러분이 정하세요. 막혔을 때 참고해도 좋고, 내 결과와 비교해 봐도 좋습니다.
다만 🤔 질문은 풀이를 보기 전에 먼저 스스로 예측해 볼 때 가장 많이 배울 수 있습니다.

## 노트북 사용법
- 위에서부터 셀을 하나씩 실행하세요 (`Shift + Enter`).
- ✏️ 표시가 있는 셀은 `___` 부분을 채우거나 숫자를 바꿔 보는 셀입니다.
- 🤔 표시는 실행 전에 결과를 먼저 예측해 보는 질문입니다.

## 실행 방법

### 1) 캠프 현장: QuREKA
강사의 안내에 따라 QuREKA 노트북 환경에서 이 저장소의 노트북을 열어 실행합니다.

### 2) 내 컴퓨터 (Linux, 또는 Windows의 WSL)
Python **3.11 이상**이 필요합니다. (`python3 --version`으로 확인)
```bash
git clone https://github.com/bpark-research/sqc-2026-quantum-camp.git
cd sqc-2026-quantum-camp
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt jupyterlab
jupyter lab
```
NVIDIA GPU가 있으면 CUDA-Q가 자동으로 GPU 시뮬레이터(`nvidia`)를 사용합니다.

#### 설치가 안 될 때
- **`Your CUDA version (...) is too old`** 오류: 서버에 오래된 CUDA 툴킷이 함께 깔려 있으면 cudaq가 버전을 잘못 감지합니다. GPU 드라이버가 지원하는 CUDA 버전(`nvidia-smi` 오른쪽 위)에 맞는 패키지를 직접 설치하세요.
  ```bash
  pip install cuda-quantum-cu13==0.17.0   # CUDA 13.x 드라이버
  pip install cuda-quantum-cu12==0.17.0   # CUDA 12.x 드라이버
  pip install numpy scipy matplotlib networkx jupyterlab
  ```
- **Python 버전이 낮다는 오류**: 서버에 `python3.11` ~ `python3.13`이 있으면 그것으로 venv를 만드세요. (예: `python3.13 -m venv .venv`)

> macOS에서는 CUDA-Q를 pip로 바로 설치할 수 없습니다. 아래 Colab을 이용하세요.

### 3) Google Colab
노트북을 Colab에서 연 뒤, 맨 위에 새 셀을 만들어 아래를 먼저 실행하세요.
```python
!pip install cudaq networkx
```

## 참고
- 실습 데이터(Day 4의 분자 데이터와 후보 분자)는 교육용으로 만든 **가상 데이터**입니다.
- 실제 양자컴퓨터(QPU) 실행 셀은 기본적으로 꺼져 있습니다. 현장에서 강사의 안내를 따르세요.
- 문의: 캠프 운영진(SDT) 또는 강사
