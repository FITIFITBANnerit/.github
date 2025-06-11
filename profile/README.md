# BANner it!  | AI 기반 불법 현수막 탐지 및 자동 신고 시스템  

![인공1-05-TEAM FITFIT-PPT](https://github.com/user-attachments/assets/224f194f-e876-4f67-ac32-b20d4a612d0e)

## 📚 목차

- [📝프로젝트 개요](#-프로젝트-개요)
- [📱앱 주요 기능](#-앱-주요-기능)
  - [📸신고 데모](#-신고-데모)   
- [⚙️시스템 구조](#-시스템-구조)
  - [전체 파이프라인 구성](#전체-파이프라인-구성)
  - [AI 파이프라인 구성](#ai-파이프라인-구성)
- [⚙️핵심 기술 스택](#-핵심-기술-스택)
- [📊모델 성능 요약](#-모델-성능-요약)
- [📊주요 개선사항](#주요-개선사항)

  
## 📝 프로젝트 개요

> BANner it! = BAN(금지하다) + Banner(현수막)

**BANner it!** 은 도시 미관을 해치고 보행자 및 운전자의 안전을 위협하는 불법 상업용 현수막을 효율적으로 탐지하고 자동으로 신고할 수 있는 **AI 기반 안드로이드 앱**입니다.

사용자가 사진을 촬영하면 하면, **YOLO를 통한 객체 탐지, OCR 기반 텍스트 추출, LLM을 활용한 텍스트 분류**가 자동으로 수행되어 현수막의 불법 여부가 판단됩니다.

본 프로젝트에서 정의하는 불법 현수막은 **지정 게시대를 벗어나 설치된 상업용 현수막**을 의미합니다.

LLM 모델은 현수막 문구를 분석해 **정치 / 공익 / 상업 / 기타** 의 네 가지 유형으로 분류하고,
이 중 ‘상업’으로 분류된 현수막이 지정 게시대를 벗어난 경우 불법으로 간주하여 자동 신고합니다.

**개발기간** |  2025.03~ 2025.06 

**수상** | 2025 창의설계 경진대회 우수상 (2025.05.30)

### TEAM FITFIT

| 항목 | 정다영 | 장유진 | 박서진 | 이세종 |
|------|--------|--------|--------|--------|
| 역할 | BE / AI(LLM)  | BE / AI(YOLO)  | AI   | FE  / AI(LLM)  |
| GitHub | [<img src="https://avatars.githubusercontent.com/u/92675692?v=4" height=100 width=100>](https://github.com/day024) | [<img src="https://avatars.githubusercontent.com/u/128692567?v=4" height=100 width=100>](https://github.com/yujin24300) | [<img src="https://avatars.githubusercontent.com/u/85439023?v=4" height=100 width=100>](https://github.com/Parkseojin2001) | [<img src="https://avatars.githubusercontent.com/u/78150250?v=4" height=100 width=100>](https://github.com/newpaper818) |


## 📱 앱 주요 기능
<img width="1134" alt="image" src="https://github.com/user-attachments/assets/d749fb8b-d6ed-47e1-96c4-e01449802bc9" />

- 사진 촬영 |  사용자 앱에서 현수막 촬영
- 자동 판별 | AI 파이프라인을 통한 불법 여부 판별
- 신고 및 저장 | 불법 판단 시 즉시 신고, 이력 저장
- 신고 내역 확인 | 앱 내 기록 열람 기능 제공
  

![ezgif-5fb878b1c0ddfd](https://github.com/user-attachments/assets/f37e0ca1-c4f0-4c95-a21a-7be6d5716d24)


### 📸 신고 데모

- 지정게시대에 있는 현수막은 추가 처리를 하지 않고 바로 합법으로 판단내린다.
- 상업 중 불법인 경우 업체명과 전화번호 등의 추가정보를 추출한다. 


| 합법 현수막 (지정게시대) | 합법 현수막 (회전된 경우) | 합법 현수막 (공익) | 불법 현수막 (상업 1) | 불법 현수막 (상업 2) |
|--------------------------|---------------------------|--------------|-----------------------|-----------------------|
| <img src="https://github.com/user-attachments/assets/bb18dcaf-a7d9-4d3d-9a92-bd923348969e" width="200"/> | <img src="https://github.com/user-attachments/assets/96fa338c-a0cd-416b-9aee-a16d0f706b6f" width="200"/> | <img src="https://github.com/user-attachments/assets/6f68b0a5-37ae-47f6-b3b6-32b74a0e0544" width="200"/> | <img src="https://github.com/user-attachments/assets/72b8ba55-9c92-4178-bfd3-621cf0117838" width="200"/> | <img src="https://github.com/user-attachments/assets/1755eeea-0972-468e-ae6e-f77aae98ecb2" width="200"/> | 

## ⚙️ 시스템 구조

### 전체 파이프라인 구성

![image](https://github.com/user-attachments/assets/6849deeb-c174-48a7-b6d4-f8f16359ac53)

### AI 파이프라인 구성

![ai diagram (15)](https://github.com/user-attachments/assets/880338c4-da2e-45a1-9ad2-b8c2f96612ec)


## ⚙️ 핵심 기술 스택

- Frontend
  - Android (Jetpack Compose, MVVM)
    
- Backend
  - java Spring Boot
  - mysql 
    
- AI
  - YOLO11s-seg / PaddleOCR / HyperCLOVAX-SEED-Vision-Instruct-3B  
  - Python, PyTorch

- Infra
  - EC2
  - S3
  - RDS

## AI / dataset
[AI-model-train](https://github.com/FITIFITBANnerit/AI-model-train)

## 📊 모델 성능 요약

![인공1-05-TEAM FITFIT-PPT](https://github.com/user-attachments/assets/4fb7a645-57a0-4f17-a09a-c80eec1a59d2)


## 📊 주요 개선사항

- 버스/간판 등 유사 객체 탐지 오류 → **네거티브 학습 도입**으로 오탐 방지
![image](https://github.com/user-attachments/assets/8d11ed96-8e9e-4ca3-8174-a304fe9ef27d)

- YOLO 탐지 이미지 **Rotation** 적용으로 OCR 정확도 향상
![image](https://github.com/user-attachments/assets/82d1d3b2-431f-4106-b745-b4fb58cd5ea1)


- 프롬프트내 문자 좌표 및 폰트 정보를 활용한 텍스트 의미 강조 → **LLM 정확도 개선**
