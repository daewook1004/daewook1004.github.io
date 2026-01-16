---
title: "PromptBall, Show Me That Play!: Designing a User-Centric System for Personalized Sports Moment Retrieval via Commentary-Driven LLMs"
collection: publications
category: preprints
permalink: /publication/2026-01-01-promptball
excerpt: "Sports fans increasingly demand personalized viewing experiences, yet conventional sports highlight systems remain passive, lack individual customization, and are built upon costly, resource-intensive machine learning pipelines. We introduce PromptBall, a novel, resource-efficient approach that enables prompt-based sports moment retrieval by utilizing a Large Language Model (LLM) with broadcast commentary as an information source. To validate the proposed approach, we designed and implemented an interactive prototype informed by user challenges identified in the preliminary study with 24 participants. Then, we conducted a technical evaluation for moment retrieval accuracy and a comparative within-subject user study (N=32) against a commercial platform. We found that PromptBall empowers users with significantly higher perceived control, facilitating granular, personalized retrieval. Our findings offer design implications and interaction strategies for integrating LLM-based customization into mainstream sports media platforms."
date: 2026-01-01
venue: 'Under Review'
paperurl: '#'
header:
  teaser: /images/PromptBall_teasure.png 
  
---


# 💡 Paper Overview

### 1. 연구 배경 및 문제의식
기존 스포츠 하이라이트 시스템은 플랫폼 공급자가 선별한 장면을 소비하는 **수동적 시청 구조**에 머물러 있음. 또한 자동화된 하이라이트 생성 시스템은  대부분 컴퓨터 비전, 오디오 분석, 머신러닝을 결합한 **고비용·고자원 파이프라인**에 의존하고 있어, 구축과 유지에 막대한 자원과 비용이 소요

반면 실제 스포츠 팬들은 다음과 같은 **개인화된 시청 경험**을 원함.
*   특정 선수의 모든 플레이
*   경기 흐름 속 특정 장면의 맥락
*   결과와 무관한 의미 있는 순간 등

본 연구는 이러한 간극에 주목하여, **비용 효율적이면서도 사용자 주도적인 스포츠 순간 탐색 방식**을 탐구.

<br>

### 2. 제안 시스템: PromptBall
**PromptBall**은 경기의 모든 상황이 언어로 서술된 **방송 중계 코멘터리(Broadcast Commentary)**를 핵심 정보원으로 활용하는 **LLM 기반 스포츠 순간 검색(Moment Retrieval) 시스템**. 비디오를 직접 이해하려는 대신, **“사람이 경기를 이해할 때 사용하는 언어적 서사”**를 LLM이 해석하고 검색하도록 설계함으로써, **자원 효율적(Resource-efficient)** 접근을 제안

<img src="/images/PromptBall%20system%20arc.png" alt="PromptBall System Architecture" style="width:100%; margin-top: 10px; margin-bottom: 20px;"> 

### **System Pipeline**
*   **Commentary Extraction**: 방송 오디오에서 STT를 통해 플레이 단위의 텍스트 코멘터리를 추출
*   **Game Summarization**: LLM이 긴 코멘터리를 이닝 단위로 분석하여 주요 사건 중심의 **구조화된 경기 연대기(Knowledge Base)** 생성

<img src="/images/gameSummarization-prompt.png" alt="Game Summarization Prompt" style="width:100%; margin-top: 10px; margin-bottom: 20px;"> 

*   **Prompt-based Retrieval**: 사용자가 *"OO 선수의 홈런 장면 다 보여줘"*와 같이 자연어로 입력하면, LLM이 요약된 경기 맥락을 바탕으로 관련 장면을 찾아 자동으로 비디오 클립을 구성

<img src="/images/Prompt_MR.png" alt="Prompt-based Retrieval" style="width:100%; margin-top: 10px; margin-bottom: 20px;"> 

<br>

### 3. 주요 설계 전략 
PromptBall은 단순한 검색 정확도를 넘어, **사용자 경험**을 핵심 설계 기준으로 삼았습니다.

*   **DG1. Prompt Scaffolding**  
    프롬프트 작성이 어려운 사용자를 위해 템플릿, 추천 프롬프트, 키워드 버튼 등 **다층적 입력 방식** 제공
*   **DG2. Contextual Support**  
    박스 스코어, 경기 로그, 주요 지표를 인터페이스에 통합하여 사용자가 **경기 맥락을 빠르게 파악**하고 탐색 의도를 형성하도록 지원
*   **DG3. Transparent Interaction**  
    실시간 처리 상태 시각화 및 인터랙티브 타임라인 제공을 통해 **“무엇이 검색되고 있는지”**를 사용자가 이해할 수 있도록 설계

<br>


### 4. 연구 결과 및 기여점 
*   **Technical Feasibility**  
    20개 실제 경기 대상 평가 결과, 주요 이벤트 검색에서 **Precision 0.969**를 기록하며 복잡한 비전 파이프라인 없이도 코멘터리 기반 접근의 실효성을 입증
*   **User Study (N = 32)**  
    상용 플랫폼(Naver Sports)과 비교했을 때, PromptBall을 사용한 참가자들은 보고 싶은 장면을 스스로 고르고 조절할 수 있다고 느꼈다고 응답
*   **Experiential Insight**  
    특히 응원 팀이 패배한 경우에도 사용자가 원하는 장면을 직접 탐색할 수 있어, **경기 결과에 따른 정서적 편향을 완화**하고 일관된 긍정적 시청 경험을 유지하도록 돕는 효과를 확인

<br>
<hr>
# 📄 Paper Download

[<i class="fas fa-file-pdf"></i> Download Paper (PDF)](#){: .btn .btn--primary}




<br>
<hr>

# 🎥 Demo Video

<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; height: auto;">
  <iframe src="https://www.youtube.com/embed/rKI30xEOafA" frameborder="0" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>
