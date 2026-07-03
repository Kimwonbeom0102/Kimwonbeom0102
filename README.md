# Kim Wonbeom / 김원범  

## About Me

C# 기반 **State-Driven Logic**으로 상태 전이와 예외 처리 구조를 설계하고  
자동화 생산 라인 경험을 바탕으로 **Process Simulation System**을 개발하고 있습니다.

공정 시뮬레이션 프로젝트에서  **ASP.NET Core + SQLite 서버 연동 구조**를 구현하여  
공정 상태 데이터를 관리하고 **Unity 환경에서 시각화**했습니다.

---

RFID 기반 물류 자동화 솔루션을 제공하는 기업에서
**하드웨어–소프트웨어–미들웨어 전 영역을 아우르는 RFID 시스템 개발**을 담당하며 커리어를 쌓고 있습니다.
 
### Domain
- RFID Reader / Printer 등 하드웨어 장비 연동
- RFID Tag 프로그래밍 및 데이터 처리
- 웹 기반 물류 자동화 프로세스
### Role
- **Software**: UI/기능 개발, 서버(API) 및 DB 설계·구현
- **Middleware**: 리더기·프린터 등 하드웨어 장비와 소프트웨어 간 통신 구조 설계
- **Data Flow**: RFID Tag 인식 → 미들웨어 처리 → 서버/DB 반영 → 웹 UI 표시로 이어지는 전체 데이터 흐름 관리
### Engineering Focus
- 장비 SDK/DLL 연동 (Reader Inventory 기능 등)
- RFID UID 기반 데이터 구조 설계 (HEX UID / 태그 메모리 분리 처리)
- 물류 프로세스에 맞춘 서버-DB-리더기 네트워크 아키텍처 구성
- 하드웨어 이슈(통신 오류, 인식 지연 등)와 소프트웨어 로직 문제를 함께 진단하는 트러블슈팅 경험

---

## Core Project

### RFID Document Tagging & Retrieval System (Web–DB–Printer Bridge)
Flask 기반 웹 서버와 MySQL DB, RFID 프린터/리더기를 연동하여
문서 발행 시 RFID 태그에 데이터를 인코딩하고, 리딩 시 해당 문서 정보를 자동 조회하는 시스템

#### Architecture Overview
- **Web**: Python(Flask) 기반, 문서 조회 및 발행 요청 처리
- **Bridge Agent**: C#(.NET, VS 2022) 기반, 상시 구동되는 로컬 프린터 중계 프로그램 (직접 설계·개발)
- **Reader Program**: C# 기반, RFID 리더기 DLL(`Inventory32` 등)을 통한 태그 리딩 처리
- **DB**: MySQL, 문서 데이터 및 Tag 값 관리
- 
RFID 프린터가 **USB 연결 시 웹에서 직접 발행 명령을 전달할 수 없는 구조적 제약**이 있었음
(RS232 포트는 웹-장비 간 직접 제어가 가능하지만, USB는 드라이버/권한 구조상 불가능)
→ 이를 해결하기 위해 웹과 프린터 사이에서 명령을 중계하는 **Bridge Agent를 C#으로 직접 개발**

#### Data Flow
1. 웹에서 문서 자료 확인 후 **발행 버튼** 클릭
2. Flask 서버가 해당 문서의 고유 Tag 값을 생성하여 MySQL DB에 저장
3. Bridge Agent가 Tag 값을 수신하여 RFID 프린터로 인코딩된 태그 출력 전달
4. 리더기 프로그램에서 **인벤토리 버튼** 클릭 → 리더기 DLL의 Inventory 함수 호출 → 태그 리딩
5. 리딩된 Tag 값을 기준으로 DB 조회, 매칭되는 문서 정보 반환

---

### Server-Driven Digital Twin Automation Simulation (In Progress)

서버 기반 Status 제어 구조를 적용한 공정 자동화 시뮬레이션 System

GitHub:  
https://github.com/Kimwonbeom0102/digital-twin-automation-sim

#### Architecture Overview

- Unity Client / ASP.NET Core Server / SQLite DB 구조 분리 설계
- REST API 기반 상태 동기화 (ElapsedTime → Scenario 판단 → Zone 상태 반환)
- DTO(Request / Response) 기반 통신 계약 분리
- Polling 기반 상태 동기화 구조 구현

#### State-driven System Design

- Plant / Zone / Robot 단위 State-driven Architecture 설계
- SetState 단일 진입 구조로 상태 전이 책임 중앙화
- Event 기반 공정 흐름 제어 (Spawn → Buffer → PickUp → Robot → Test)
- Fault / Stop / Execute 복구 구조 구현
- IsTriggered 기반 Fault 재트리거 방지 설계
- Reset API를 통한 서버 주도 상태 복구 구조

#### Simulation Features

- Queue 기반 BufferZone 시각화
- JSON 로그 기록 시스템 구현
- Visualization Layer 분리 구조 설계 (Desktop / XR)

기존 단일 실행 시뮬레이션 구조에서 서버–DB 기반 상태 제어 구조로 확장하여
데이터 중심 공정 제어 시스템으로 재설계

Ongoing improvements
- Plant–Zone–Server 상위 계층 구조 재정립
- Fault 및 공정 시나리오 확장
- XR 모드 안정화 및 유지보수

---

## Application Projects

### Inventory Manager
WinForms 기반 재고 관리 프로그램

- 제품 등록 / 수정 / 삭제
- 재고 수량 관리
- 재고 부족 조회
- 검색 및 정렬 기능

GitHub  
https://github.com/Kimwonbeom0102/Manager_Programs/tree/main/InventoryManager

---

### Membership Manager
WinForms 기반 회원 관리 시스템

- 회원 등록 / 수정 / 삭제
- 로그인 기능
- SHA-256 비밀번호 해시 처리
- JSON 데이터 저장

GitHub  
https://github.com/Kimwonbeom0102/MembershipManager

---

## Additional Projects

### AR Interactive Storybook  
- ARCore 기반 이미지 트래킹 및 음성 인식(STT) 인터랙션  
- 입력 조건 기반 상태 전이 설계
- 콘텐츠 흐름 제어 로직 분리 구조

GitHub:  
https://github.com/Kimwonbeom0102/AR_Project

---

### Unity Networking System
- Photon PUN 기반 멀티플레이 시스템
- Player 생성 및 Network Object 동기화 처리
- Room 기반 멀티플레이어 매칭 및 게임 입장 로직 구현
- Network Sync를 활용한 Player 상태 동기화 처리

GitHub:  
https://github.com/Kimwonbeom0102/unity-networking-photon

---

### C# Console Mini Projects  
- Stack / 게시판 / 콘솔 프로그램

GitHub:  
https://github.com/Kimwonbeom0102/mini-projects

---

## Technical Focus

### Language & Engine
- Visual Studio 2022
- C# / .NET 8

### Backend
- ASP.NET Core Web API
- Entity Framework Core
- SQLite

### Architecture & Simulation
- State-driven Architecture  
- Event-driven System  
- Client–Server Architecture  
- REST API
- Fault & Recovery Flow Design
- Process Simulation

### Visualization 
- Unity / XR

---

## Background

- C# / Simulation Development Bootcamp (Unity BootCamp)
- C# Intermediate Studies
- Automation Production Line Experience
- RFID 하드웨어·소프트웨어·미들웨어 실무 경험 (재직 중)
