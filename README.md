# Kim Wonbeom / 김원범  

Unity와 C# 기반으로 상태 기반 로직 설계와 공정 시뮬레이션 구현을 중심으로 개발하고 있습니다.  
자동화 생산 라인 경험을 바탕으로 공정 흐름을 상태(State) 중심으로 모델링하고,  
이를 ASP.NET Core + SQLite 기반 서버 구조로 확장하여 디지털 트윈 형태의 공정 제어 및 시각화 시스템을 설계하고 있습니다.

---

## Core Project

### Server-Driven Digital Twin Automation Simulation (In Progress)

Unity 기반 공정 자동화 시뮬레이션 프로젝트  
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
- Fault / Stop / Resume 복구 구조 구현
- IsTriggered 기반 Fault 재트리거 방지 설계
- Reset API를 통한 서버 주도 상태 복구 구조

#### Simulation Features

- Queue 기반 BufferZone 시각화
- JSON 로그 기록 시스템 구현
- Desktop / XR 분리 구조 설계 (UI / Camera Layer 분리)

> Unity 단일 실행 구조에서 서버-DB 기반 상태 제어 구조로 확장하여  
> 단순 시각화가 아닌 데이터 중심 공정 제어 시스템으로 재설계했습니다.

- Ongoing improvements: Version control refinement, XR maintenance, scenario expansion

---

## Other Projects

### AR Interactive Storybook  
Unity + ARCore 기반 이미지 트래킹 및 음성 인식(STT) 인터랙션 구현  
- 입력 조건 기반 상태 전이 설계
- 콘텐츠 흐름 제어 로직 분리 구조

GitHub:  
https://github.com/Kimwonbeom0102/AR_Project

---

### Unity 3D Running Game  
- 맵 설계 및 장애물/부스터존 시스템 구현
- 리스폰 및 충돌 처리 로직 설계

GitHub:  
https://github.com/Kimwonbeom0102/Runguys

---

### C# Console Mini Projects  
- Stack 자료구조 구현
- 게시판 구조 설계
- 이벤트 기반 콘솔 앱 실습

GitHub:  
https://github.com/Kimwonbeom0102/mini-projects

---

## Technical Focus

### Language & Backend
- C#
- .NET 8
- ASP.NET Core Web API
- Entity Framework Core
- SQLite

### Architecture & Simulation
- Unity (Simulation / XR Extension Structure)
- State-driven Design
- Event-driven Architecture
- Client-Server Architecture
- REST API
- Fault & Recovery Flow Design
- Process Visualization

---

## Background

- Unity Bootcamp (2024–2025)
- C# Intermediate Studies
- Automation Production Line Experience
