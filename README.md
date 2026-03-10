# HeartBit

본 프로젝트인 ‘HeartBit' 는 실시간 거래 데이터를 기반으로 한 모의 투자 거래 플랫폼입니다.<br>
기존 가상자산 거래소 플랫폼인 업비트를 모티브로 하여 실제 거래 서비스 구조를 구현하였습니다.
* **개발 기간**: 2025.12 ~ 2026.02
* **팀 구성**: 총 6명 (**Full 1명**, Backend 3명, Frontend 1명, AI 1명)
* **나의 역할**
  * **Frontend**  (대용량 캔들 데이터의 실시간 렌더링 성능 최적화, STOMP 프로토콜을 이용한 실시간 호가, 체결, 채팅 데이터 동기화, 무한스크롤)
  * Backend  (인증 시스템 및 토큰 재발급 구축)

<br>

## 🛠 기술 스택
### Frontend
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

### Backend
<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <img src="https://img.shields.io/badge/Java-007396?style=flat-square&logo=OpenJDK&logoColor=white">
  <img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=Spring-Boot&logoColor=white">
  <img src="https://img.shields.io/badge/Spring_Security-6DB33F?style=flat-square&logo=Spring-Security&logoColor=white">
  <img src="https://img.shields.io/badge/JWT-000000?style=flat-square&logo=JSON-Web-Tokens&logoColor=white">
  <img src="https://img.shields.io/badge/Spring_Security_Filter_Chain-6DB33F?style=flat-square&logo=Spring-Security&logoColor=white">
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=PostgreSQL&logoColor=white">
  <img src="https://img.shields.io/badge/JPA-59666C?style=flat-square&logo=Hibernate&logoColor=white">
  <img src="https://img.shields.io/badge/RESTful_API-005571?style=flat-square&logoColor=white">
  <img src="https://img.shields.io/badge/Gradle-02303A?style=flat-square&logo=Gradle&logoColor=white">
  <img src="https://img.shields.io/badge/Swagger-85EA2D?style=flat-square&logo=Swagger&logoColor=black">
</div>


<br>

## 🧑‍💻 주요 기여 내용 및 성과

### ✨ 1. 주요 개발 내용
* **인증/인가:** 로그인, 회원가입 페이지 구현
* **거래소 핵심 도메인:** 캔버스 기반 차트, 종목 정보, 호가창 및 시세 확인 기능 구현
* **실시간 소통:** 웹소켓을 활용한 종목별 실시간 채팅 기능 구현
* **자산 및 주문 관리:** 보유 자산 조회, 체결 목록 및 미체결 목록 상태 관리


|전체 화면 |시세|채팅|
|:------:|:---:|:---:|
|<img width="1342" height="796" alt="image" src="https://github.com/user-attachments/assets/18a80419-e9df-4079-bf35-67f1fbd3f3ca" />|<img width="1642" height="960" alt="image" src="https://github.com/user-attachments/assets/02f2536d-839f-48a3-a8b2-a28bc7bdc11b" />|<img width="1810" height="1068" alt="image" src="https://github.com/user-attachments/assets/4cd80618-0246-4e2b-9a8f-0c45516ab049" />|
|**체결 목록**|**미체결 목록**|**보유자산**|
|<img width="575" height="319" alt="image" src="https://github.com/user-attachments/assets/f992292c-5ca7-461c-92ff-1d20397b3408" />|<img width="577" height="318" alt="image" src="https://github.com/user-attachments/assets/41e42e62-8475-48e2-8da5-41cf36c09e77" />|<img width="1813" height="1069" alt="image" src="https://github.com/user-attachments/assets/c675187d-6002-4800-97d7-879dcb436086" />|


<br>

### 🧪 2. 다층적 테스트 파이프라인 구축 (Test Automation)
프론트엔드 코드의 무결성을 보장하고 리팩토링 안정성을 확보하기 위해 3단계 테스트 환경을 구축했습니다.
|단위/통합 테스트 <br> (Vitest)| 시각적 회귀 테스트 <br> (Storybook + Chromatic) | E2E 테스트 자동화 <br> (Cypress) |
|:------:|:---:|:---:|
|<img width="781" height="197" alt="image" src="https://github.com/user-attachments/assets/4d764aff-b458-4431-9639-ddfd31b23299" />|[chromatic 연동 사이트 바로가기](https://69818073f20a97befcbf4016-ywxmkrnypa.chromatic.com/?path=/story/markettableitem--default)|![Video-Project-1](https://github.com/user-attachments/assets/18d7d166-9cdb-4a00-b6e2-9a8452107bdf)|
|주요 비즈니스 로직과 <br> 개별 UI 컴포넌트의 상태 변화를 검증했습니다. | UI 공통 컴포넌트를 독립적으로 문서화하고<br>CI/CD 과정에 Chromatic을 연동하여, 리팩토링 시 발생하는 의도치 않은 UI/레이아웃 깨짐 현상(Side Effect)을 배포 전에 차단했습니다.| 서비스의 가장 핵심인 **'매수/매도'** 결제 플로우를 <br> 실제 브라우저 환경과 동일하게 시나리오화하여 <br> 검증함으로써, 수동 QA 시간을 대폭 단축했습니다.|


<br>

### 🚀 3. 초기 로딩 속도 최적화
* **무한 스크롤 적용:** 대량의 데이터(채팅, 거래 내역 등) 조회 시 무한 스크롤을 도입하여 초기 데이터 로딩 및 DOM 렌더링 부담을 줄였습니다.
* **번들 사이즈 최적화 (초기 메인 번들 81% 경량화):**
    * `React.lazy`를 활용한 라우트 기반 코드 스플리팅(Code Splitting) 적용.
    * Vite 환경에서 `manualChunks` 설정을 통해 무거운 차트 라이브러리와 벤더(Vendor) 코드를 별도 청크로 분리.
    * 빌드 시 Gzip 텍스트 압축(`vite-plugin-compression`)을 활성화하여 브라우저의 다운로드 전송량을 획기적으로 최소화.
 
| 전 |  후  |
|---|---|
|<img width="549" height="61" alt="image" src="https://github.com/user-attachments/assets/3ce2b961-fcd1-40a5-848f-cde7f38500ff" />|<img width="549" height="175" alt="image" src="https://github.com/user-attachments/assets/a985a664-95b0-4c77-9260-a0044f09b60e" />|


<br>

### ⚡4. 렌더링 및 UI/UX 최적화 (TBT, CLS 개선)
* **불필요한 리렌더링 제거:** 보유 자산, 헤더, 시세 등 상태 변경이 적은 컴포넌트에 `React.memo`를 적용하여 불필요한 렌더링 비용을 줄였습니다.
* **무거운 연산 메모이제이션 (TBT 0ms 달성):** 실시간 채팅 수신 시 과거 데이터 배열과 웹소켓 데이터를 합치고 정렬하는 무거운 O(N) 병합 로직을 `useMemo`로 캐싱했습니다. 이를 통해 사용자의 키보드 입력(타이핑) 시 발생하는 잦은 리렌더링 병목 연산을 제거하고 메인 스레드 지연(Total Blocking Time)을 완벽히 해소했습니다.
* **스크롤 보정 및 시각적 덜컥거림 방지 (CLS 개선):** 무한 스크롤로 과거 과거 메시지를 불러오거나 새 메시지가 수신될 때 스크롤이 튀는 현상(Layout Shift)을 방지하기 위해 `useLayoutEffect`를 적용했습니다. 브라우저가 화면을 그리기 직전(Paint 이전)에 동기적으로 스크롤 높이를 계산하고 보정하여 시각적 안정성을 크게 향상시켰습니다.

<br>

#### 1) 보유자산 (Asset) 최적화
| 최적화 전 (Before) | 결과 (After) |
| :--- | :--- |
| <img width="500" alt="보유자산 최적화 전" src="https://github.com/user-attachments/assets/d334c5b8-6393-480a-befb-1506d5ced3d8" /> | <img width="500" alt="보유자산 최적화 결과" src="https://github.com/user-attachments/assets/61308535-e7f6-4dab-95e5-eb7775432602" />|

* **문제** : 웹소켓 데이터 수신 시 `Asset`, `AssetList` 등 하위 컴포넌트 전체가 리렌더링 됨.
* **원인** : 부모 컴포넌트가 `useAssetStore`를 통째로 구독(구조분해 할당)하여, 스토어 값 변경 시 부모부터 자식까지 연쇄적으로 렌더링 됨.
* **해결방법**
  * 구조분해 할당 대신 **Selector 방식** 사용
  * `MyAsset`, `AssetItem`에 **`useShallow`** 적용
  * `Text`, `AssetItem`에 **`React.memo`** 적용

<br>

#### 2) 헤더 (Header) 최적화
| 결과 (After) |
| :--- |
| <img width="500" alt="헤더 최적화 결과" src="https://github.com/user-attachments/assets/d05a2234-bf44-4d15-8d2b-bef4836f6120" />|

* **문제** : 알림 아이콘이나 메뉴 텍스트 클릭 시 로고, 메뉴, 아이콘 등 헤더 영역 전체가 같이 리렌더링 됨.
* **원인** : `open`과 `anchorRect` 상태(State)가 `Header` 컴포넌트 최상단에 묶여 있어, 작은 상태 변경에도 헤더 전체가 렌더링 대상이 됨.
* **해결방법**
  * 알림 관련 로직을 **`IconSection`** 컴포넌트로 분리하여 상태 격리
  * 메뉴 영역을 **`NavBar`** 컴포넌트로 분리
  * 로고를 제외한 메뉴들은 `Link` 대신 **`NavLink`** 로 변경

<br>

#### 3) 채팅 (Chatting) 최적화
| 최적화 전 (Before) | 결과 (After) |
| :--- | :--- |
| <img width="500" alt="채팅 최적화 전" src="https://github.com/user-attachments/assets/90997ec6-3ca2-4e13-a5df-f8e783fa8295" /> | <img width="500" alt="채팅 최적화 결과" src="https://github.com/user-attachments/assets/cf5dc512-8b0e-437d-b8c9-3bbd3db34312" />|
|<img width="500" alt="채팅 최적화 전" src="https://github.com/user-attachments/assets/d3645534-1254-482a-af09-08dcb913cfbf" /> | <img width="500" alt="채팅 최적화 결과" src="https://github.com/user-attachments/assets/fb6b4b18-dcbe-4627-9e89-c5178e151676" /> | 

* **문제**
  * 입력창에 글자를 칠 때마다(타이핑), 그리고 메시지를 보낼 때마다 전체 채팅 목록이 모두 리렌더링 됨.
  * 종목이 바뀔 때마다 채팅 목록과 `MarketPanel`이 모두 리렌더링 됨.
* **원인**
  * `message` 상태가 부모인 `Chatting` 컴포넌트에 존재하여, 글자를 한 번 칠 때마다 부모가 렌더링되고 자식들의 `.map`이 다시 실행됨.
  * `Chatting` 컴포넌트가 선택된 종목 상태(categoryId)를 전역 스토어에서 직접 구독하고 있어, 종목 변경 시 하위 채팅 요소들까지 모두 연쇄적으로 리렌더링되는 구조임.
* **해결방법**
  * 입력창을 **`ChatInput`** 컴포넌트로 분리하여 상태(State) 격리
  * 개별 **`Chat`** 컴포넌트에 **`React.memo`** 적용
  * `handleSendMessage` 함수에 **`useCallback`** 적용
  * `mergedChatList` 병합 로직 최적화

<br>

#### 4) 시세 (Price Info & Chart) 최적화
| 최적화 전 (Before) | 결과 (After) |
| :--- | :--- |
| <img width="500" alt="시세 최적화 전" src="https://github.com/user-attachments/assets/2f6363ed-382d-45d3-8268-294dd9cc6163" />| <img width="500" alt="시세 최적화 결과" src="https://github.com/user-attachments/assets/08641634-614c-48f3-bb62-4f63dd0652c0" />|

* **문제** : 차트 데이터가 최신화될 때마다 상위 및 형제 컴포넌트(`InfoCoin`, `PriceInfo`, `Text`)가 모두 불필요하게 리렌더링 됨.
* **원인** : 상위 컴포넌트(`InfoCoin`)가 웹소켓 차트 스토어를 직접 구독하고 있어, 초당 수차례 들어오는 데이터 수신 시 전체 하위 트리까지 리렌더링이 전파됨.
* **해결방법**
  * 실시간 데이터 업데이트와 병합 작업을 전담하는 **`ChartDataWrapper`** 생성 및 컴포넌트 분리
  * **`InfoCoin`** 컴포넌트에 **`React.memo`** 적용
  * 탭 변경 함수(`handleTab`)에 **`useCallback`** 적용



<br>


## 📊 5. 최적화 결과 (Lighthouse)
적극적인 최적화 적용 결과, 네트워크 다운로드 용량과 웹 핵심 성능 지표(Core Web Vitals)를 개선했습니다.

* **메인 번들 사이즈 최적화:** `797 kB` ➡️ `149 kB` (**약 81% 감소 / 648 kB 경량화**)
* **초기 렌더링 속도 대폭 개선:**
    * **FCP** (First Contentful Paint) : `3.5s` ➡️ **`0.4s`**
    * **LCP** (Largest Contentful Paint) : `6.9s` ➡️ **`0.4s`**
    * **SI** (Speed Index) : `3.7s` ➡️ **`0.9s`**
