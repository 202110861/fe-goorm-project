# HeartBit

## 🛠 기술 스택
<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=React&logoColor=black">
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=TypeScript&logoColor=white">
  <img src="https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square&logo=Tailwind-CSS&logoColor=white">
  <img src="https://img.shields.io/badge/Tanstack_Query-FF4154?style=flat-square&logo=React-Query&logoColor=white">
  <img src="https://img.shields.io/badge/Zustand-764ABC?style=flat-square&logo=React&logoColor=white">
  <img src="https://img.shields.io/badge/SockJS-010101?style=flat-square&logoColor=white">
  <img src="https://img.shields.io/badge/StompJS-010101?style=flat-square&logoColor=white">
  <img src="https://img.shields.io/badge/TradingView_Lightweight_Charts-131722?style=flat-square&logo=TradingView&logoColor=white">
  <img src="https://img.shields.io/badge/React_Hook_Form-EC5990?style=flat-square&logo=React-Hook-Form&logoColor=white">
  <img src="https://img.shields.io/badge/Yup-222222?style=flat-square&logoColor=white">
  <img src="https://img.shields.io/badge/Vitest-6E9F18?style=flat-square&logo=Vitest&logoColor=white">
  <img src="https://img.shields.io/badge/Cypress-17202C?style=flat-square&logo=Cypress&logoColor=white">
</div>



## 🧑‍💻 주요 기여 내용 및 성과

### ✨ 1. 주요 개발 내용
* **인증/인가:** 로그인, 회원가입 페이지 구현
* **거래소 핵심 도메인:** 캔버스 기반 차트, 종목 정보, 호가창 및 시세 확인 기능 구현
* **실시간 소통:** 웹소켓을 활용한 종목별 실시간 채팅 기능 구현
* **자산 및 주문 관리:** 보유 자산 조회, 체결 목록 및 미체결 목록 상태 관리


|전체 화면 |시세|채팅|
|------|---|---|
|<img width="1342" height="796" alt="image" src="https://github.com/user-attachments/assets/18a80419-e9df-4079-bf35-67f1fbd3f3ca" />|<img width="1642" height="960" alt="image" src="https://github.com/user-attachments/assets/02f2536d-839f-48a3-a8b2-a28bc7bdc11b" />|<img width="1810" height="1068" alt="image" src="https://github.com/user-attachments/assets/4cd80618-0246-4e2b-9a8f-0c45516ab049" />|
|체결 목록|미체결 목록|보유자산|
|<img width="924" height="486" alt="image" src="https://github.com/user-attachments/assets/c975cc6e-1ac3-4328-9462-49c36c763b01" />|<img width="645" height="470" alt="image" src="https://github.com/user-attachments/assets/b339304c-4cf9-4664-aca9-17abeaa5480c" />|<img width="1813" height="1069" alt="image" src="https://github.com/user-attachments/assets/c675187d-6002-4800-97d7-879dcb436086" />|

---

### 🧪 2. 다층적 테스트 파이프라인 구축 (Test Automation)
프론트엔드 코드의 무결성을 보장하고 리팩토링 안정성을 확보하기 위해 3단계 테스트 환경을 구축했습니다.
* **단위/통합 테스트 (Vitest):** 주요 비즈니스 로직과 개별 UI 컴포넌트의 상태 변화를 검증했습니다.
* **시각적 회귀 테스트 (Storybook + Chromatic):** UI 공통 컴포넌트를 독립적으로 문서화하고 CI/CD 과정에 Chromatic을 연동하여, 리팩토링 시 발생하는 의도치 않은 UI/레이아웃 깨짐 현상(Side Effect)을 배포 전에 완벽하게 차단했습니다.
* **E2E 테스트 자동화 (Cypress):** 서비스의 가장 핵심인 **'매수/매도'** 결제 플로우를 실제 브라우저 환경과 동일하게 시나리오화하여 검증함으로써, 수동 QA 시간을 대폭 단축하고 과감한 리팩토링이 가능한 배포 자신감을 확보했습니다.

---

### 🚀 3. 성능 및 렌더링 최적화
사용자 경험(UX) 향상과 Lighthouse 지표 한계 돌파를 위해 로딩 및 렌더링 단계를 집중적으로 최적화했습니다.

#### 📦 3-1. 초기 로딩 속도 최적화
* **무한 스크롤 적용:** 대량의 데이터(채팅, 거래 내역 등) 조회 시 무한 스크롤을 도입하여 초기 데이터 로딩 및 DOM 렌더링 부담을 줄였습니다.
* **번들 사이즈 최적화 (초기 메인 번들 81% 경량화):**
    * `React.lazy`를 활용한 라우트 기반 코드 스플리팅(Code Splitting) 적용.
    * Vite 환경에서 `manualChunks` 설정을 통해 무거운 차트 라이브러리와 벤더(Vendor) 코드를 별도 청크로 분리.
    * 빌드 시 Gzip 텍스트 압축(`vite-plugin-compression`)을 활성화하여 브라우저의 다운로드 전송량을 획기적으로 최소화.

#### ⚡ 3-2. 렌더링 및 UI/UX 최적화 (TBT, CLS 개선)
* **불필요한 리렌더링 제거:** 보유 자산, 헤더, 시세 등 상태 변경이 적은 컴포넌트에 `React.memo`를 적용하여 불필요한 렌더링 비용을 줄였습니다.
* **무거운 연산 메모이제이션 (TBT 0ms 달성):** 실시간 채팅 수신 시 과거 데이터 배열과 웹소켓 데이터를 합치고 정렬하는 무거운 O(N) 병합 로직을 `useMemo`로 캐싱했습니다. 이를 통해 사용자의 키보드 입력(타이핑) 시 발생하는 잦은 리렌더링 병목 연산을 제거하고 메인 스레드 지연(Total Blocking Time)을 완벽히 해소했습니다.
* **스크롤 보정 및 시각적 덜컥거림 방지 (CLS 개선):** 무한 스크롤로 과거 과거 메시지를 불러오거나 새 메시지가 수신될 때 스크롤이 튀는 현상(Layout Shift)을 방지하기 위해 `useLayoutEffect`를 적용했습니다. 브라우저가 화면을 그리기 직전(Paint 이전)에 동기적으로 스크롤 높이를 계산하고 보정하여 시각적 안정성을 크게 향상시켰습니다.

#### 📊 3-3. 최적화 결과 (Lighthouse)
적극적인 최적화 적용 결과, 네트워크 다운로드 용량과 웹 핵심 성능 지표(Core Web Vitals)를 크게 개선했습니다.

* **메인 번들 사이즈 최적화:** `797 kB` ➡️ `149 kB` (**약 81% 감소 / 648 kB 경량화**)
* **초기 렌더링 속도 대폭 개선:**
    * **FCP** (First Contentful Paint) : `3.5s` ➡️ **`0.4s`**
    * **LCP** (Largest Contentful Paint) : `6.9s` ➡️ **`0.4s`**
    * **SI** (Speed Index) : `3.7s` ➡️ **`0.9s`**
