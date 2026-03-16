# Kim Wonbeom / 김원범  

## About Me

C# 기반 **State-Driven Logic**으로 공정 상태 전이와 예외 처리 구조를 설계하고  
자동화 생산 라인 경험을 바탕으로 **Process Simulation System**을 개발하고 있습니다.

공정 시뮬레이션 프로젝트에서  **ASP.NET Core + SQLite 서버 연동 구조**를 구현하여  
공정 상태 데이터를 관리하고 **Unity 환경에서 시각화**했습니다.

---

## Core Project

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
- Fault / Stop / Resume 복구 구조 구현
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

### Language & Tool
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
