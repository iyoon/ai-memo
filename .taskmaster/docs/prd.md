# 📝 PRD: **Memora** – AI 음성 메모장 웹서비스

---

## 1. Overview

**Memora**는 AI 기반 웹 메모 애플리케이션으로, 사용자의 음성 또는 텍스트 입력을 받아 **AI가 자동으로 요약 및 분류**해주는 기능을 제공합니다. **STT(Speech-to-Text) 기술**을 통해 빠른 음성 메모 작성이 가능하며, 모든 데이터는 **웹 애플리케이션의 데이터베이스에 저장**됩니다.

### 🧩 개발 배경 및 목적

기존 메모 서비스는 사용자의 메모를 단순 저장하는 데 그치는 경우가 많아, 시간이 지날수록 중요한 정보를 찾기 어렵고 효율적인 활용이 어려워집니다. 특히 회의록, 아이디어, 공부 내용 등 다양한 형태의 메모를 빠르게 작성하고 구조화하는 것이 점점 더 중요해지고 있습니다.

### 🎯 제공 가치

- **AI 요약**: 긴 메모를 간결한 핵심 요약으로 제공
- **카테고리 분류**: 자동 분류 기능을 통한 체계적인 메모 정리
- **STT 기반 음성 입력**: 빠른 음성 기반 메모 작성 가능
- **웹 접근성**: 설치 없이 브라우저에서 사용 가능

---

## 2. Core Features

### 📝 텍스트 메모 작성

- **기능**: 사용자가 직접 웹에서 텍스트 입력
- **중요성**: 기본적인 메모 작성 기능으로 모든 사용자에게 필수
- **동작 방식**: React 기반 텍스트 에디터, 실시간 저장

### 🎤 음성 입력 (STT 변환)

- **기능**: 마이크 입력을 실시간 텍스트로 변환
- **중요성**: 빠른 메모 작성과 접근성을 크게 향상
- **동작 방식**: Web Speech API 또는 외부 STT 서비스 연동

### 🤖 AI 요약

- **기능**: 긴 메모 내용을 간결하게 요약
- **중요성**: 핵심 가치 제안으로 사용자 경험을 혁신
- **동작 방식**: OpenAI API 또는 유사 AI 서비스 활용

### 🏷️ 자동 카테고리 분류

- **기능**: 메모 내용을 주제 기반으로 자동 분류
- **중요성**: 체계적인 메모 관리와 검색 효율성 향상
- **동작 방식**: AI 분류 모델을 통한 자동 태깅

### 🔍 검색 기능

- **기능**: 키워드, 작성일, 카테고리별 검색 가능
- **중요성**: 저장된 메모의 효율적인 검색과 활용
- **동작 방식**: 데이터베이스 인덱싱과 풀텍스트 검색

### 💾 데이터베이스 저장

- **기능**: 모든 메모는 서버의 DB에 저장
- **중요성**: 데이터 영속성과 다중 기기 동기화
- **동작 방식**: PostgreSQL 또는 MongoDB 활용

### 📊 사용자 통계

- **기능**: 작성 빈도, 사용 패턴 등 분석 정보 제공
- **중요성**: 사용자 인사이트와 서비스 개선
- **동작 방식**: 데이터 분석 및 시각화 라이브러리 활용

---

## 3. User Experience

### 👥 User Personas

#### 👩‍💼 직장인 / 프리랜서

- **특징**: 회의나 작업 중 웹에서 빠르게 메모하고, 자동 정리되길 원함
- **사용 패턴**: 업무 시간 중 집중적 사용, 회의록 작성
- **요구사항**: 빠른 입력, 정확한 분류, 검색 편의성

#### 🎓 대학생

- **특징**: 노트북을 통해 수업 내용을 음성/텍스트로 기록하고 정리하길 원함
- **사용 패턴**: 수업 시간 중 음성 녹음, 복습 시 검색
- **요구사항**: 음성 인식 정확도, 카테고리별 정리

#### 👨‍👩‍👧‍👦 일반 사용자

- **특징**: 웹에서 손쉽게 일상 메모를 작성하고 필요할 때 검색하길 원함
- **사용 패턴**: 간헐적 사용, 다양한 주제의 메모
- **요구사항**: 직관적 UI, 간단한 사용법

### 🔄 Key User Flows

#### 📌 시나리오: 웹에서 회의 내용을 음성으로 메모

1. 사용자가 웹 앱을 실행해 로그인
2. '새 메모' 버튼 클릭 → 음성 녹음 시작
3. STT 기술로 실시간 텍스트 변환
4. 메모 저장 시, 자동으로 AI 요약 및 카테고리 분류
5. 전체 메모와 요약본이 웹 화면에 동시 표시됨
6. 데이터는 자체 데이터베이스에 저장되어 웹에서 언제든지 확인 가능

### 🎨 UI/UX Considerations

- **반응형 디자인**: 모바일, 태블릿, 데스크톱 지원
- **직관적 인터페이스**: 최소한의 클릭으로 메모 작성
- **실시간 피드백**: 음성 인식 상태, 저장 진행률 표시
- **접근성**: 키보드 네비게이션, 스크린 리더 지원

---

## 4. Technical Architecture

### 🏗️ System Components

#### Frontend & Backend (Next.js 14)

- **Next.js 14 (App Router)**: 풀스택 React 프레임워크
- **TypeScript**: 타입 안정성
- **TailwindCSS**: 유틸리티 기반 CSS 프레임워크
- **Web Speech API**: 브라우저 내장 STT
- **React Query**: 서버 상태 관리

#### Database & Authentication

- **Supabase**: PostgreSQL 기반 BaaS (Backend as a Service)
- **DrizzleORM**: 타입 안전한 ORM
- **Supabase Auth**: 내장 인증 시스템
- **Supabase Storage**: 파일 업로드 및 저장

#### AI Services

- **Anthropic Claude API**: 텍스트 요약 및 분류
- **Web Speech API**: 브라우저 내장 실시간 음성 인식

### 📊 Data Models

#### User

```typescript
{
  id: string;
  email: string;
  name: string;
  createdAt: Date;
  updatedAt: Date;
}
```

#### Memo

```typescript
{
  id: string
  userId: string
  title: string
  content: string
  summary: string
  category: string
  tags: string[]
  audioUrl?: string
  createdAt: Date
  updatedAt: Date
}
```

#### Category

```typescript
{
  id: string;
  name: string;
  color: string;
  userId: string;
  createdAt: Date;
}
```

### 🔌 APIs and Integrations

#### Internal APIs

- `POST /api/memos`: 메모 생성
- `GET /api/memos`: 메모 목록 조회
- `PUT /api/memos/:id`: 메모 수정
- `DELETE /api/memos/:id`: 메모 삭제
- `POST /api/memos/:id/summarize`: AI 요약 생성
- `POST /api/memos/:id/categorize`: 카테고리 분류

#### External Integrations

- **Anthropic Claude API**: 텍스트 요약 및 분류
- **Web Speech API**: 브라우저 내장 실시간 음성 인식
- **Supabase**: 데이터베이스, 인증, 파일 저장

### 🏢 Infrastructure Requirements

#### Development

- **Node.js 18+**: 런타임 환경
- **Supabase**: 데이터베이스 및 인증
- **DrizzleORM**: 타입 안전한 ORM
- **TypeScript**: 개발 환경

#### Production

- **Vercel**: Next.js 최적화 배포 플랫폼
- **Supabase**: 데이터베이스, 인증, 파일 저장
- **Vercel Analytics**: 성능 모니터링

---

## 5. Development Roadmap

### 🚀 Phase 1: MVP (Minimum Viable Product)

#### Core Features

- **기본 웹 애플리케이션 구조**

  - Next.js 프로젝트 설정
  - 기본 레이아웃 및 라우팅
  - 사용자 인증 시스템

- **텍스트 메모 작성**

  - 메모 작성 폼
  - 메모 목록 표시
  - 기본 CRUD 기능

- **데이터베이스 연동**
  - Supabase 설정
  - DrizzleORM 설정
  - 기본 데이터 모델 구현

#### Success Criteria

- 사용자가 텍스트 메모를 작성하고 저장할 수 있음
- 메모 목록을 조회하고 수정/삭제할 수 있음
- 기본적인 사용자 인증이 작동함

### 🔧 Phase 2: AI Integration

#### AI Features

- **AI 요약 기능**

  - Anthropic Claude API 연동
  - 메모 저장 시 자동 요약 생성
  - 요약 결과 표시 UI

- **자동 카테고리 분류**
  - AI 기반 카테고리 분류
  - 사용자 정의 카테고리 지원
  - 분류 결과 시각화

#### Success Criteria

- 메모 저장 시 자동으로 AI 요약이 생성됨
- 메모가 자동으로 적절한 카테고리에 분류됨
- 사용자가 카테고리를 수정할 수 있음

### 🎤 Phase 3: Voice Input

#### STT Features

- **음성 입력 기능**

  - Web Speech API 구현
  - 실시간 음성 인식
  - 음성 녹음 UI

- **음성 파일 처리**
  - 오디오 파일 업로드
  - 서버 사이드 STT 처리
  - 음성 파일 저장 및 관리

#### Success Criteria

- 사용자가 음성으로 메모를 작성할 수 있음
- 실시간으로 음성이 텍스트로 변환됨
- 음성 파일을 업로드하여 처리할 수 있음

### 🔍 Phase 4: Search & Analytics

#### Advanced Features

- **고급 검색 기능**

  - 풀텍스트 검색
  - 필터링 및 정렬
  - 검색 결과 하이라이팅

- **사용자 통계**
  - 사용 패턴 분석
  - 메모 작성 통계
  - 시각화 대시보드

#### Success Criteria

- 사용자가 다양한 조건으로 메모를 검색할 수 있음
- 개인화된 사용 통계를 확인할 수 있음
- 직관적인 검색 인터페이스가 제공됨

---

## 6. Logical Dependency Chain

### 🏗️ Foundation First (Phase 1)

1. **프로젝트 설정 및 기본 구조**

   - Next.js 프로젝트 초기화
   - TypeScript 설정
   - 기본 라우팅 구조

2. **데이터베이스 및 백엔드**

   - PostgreSQL 데이터베이스 설정
   - Prisma ORM 설정
   - 기본 API 엔드포인트 구현

3. **사용자 인증**

   - JWT 기반 인증 시스템
   - 로그인/회원가입 페이지
   - 보호된 라우트 구현

4. **기본 CRUD 기능**
   - 메모 작성/수정/삭제
   - 메모 목록 표시
   - 기본 UI 컴포넌트

### 🎯 Quick Win - Visible Frontend (Phase 1)

- **즉시 사용 가능한 웹 인터페이스** 구축
- **기본 텍스트 메모 기능**으로 핵심 가치 증명
- **반응형 디자인**으로 다양한 기기 지원

### 🔄 Progressive Enhancement (Phase 2-4)

- **AI 기능 추가**로 차별화된 가치 제공
- **음성 입력**으로 사용성 향상
- **고급 기능**으로 완성도 높은 제품 완성

---

## 7. Risks and Mitigations

### 🛠️ Technical Challenges

#### AI API 의존성

- **위험**: OpenAI API 비용 및 가용성
- **완화책**:
  - 다중 AI 제공자 지원 (Claude, Gemini)
  - 로컬 AI 모델 대안 검토
  - API 사용량 모니터링 및 최적화

#### 음성 인식 정확도

- **위험**: Web Speech API의 제한적 성능
- **완화책**:
  - Google Speech-to-Text API 대안 제공
  - 사용자 피드백을 통한 개선
  - 다국어 지원 단계적 구현

#### 실시간 성능

- **위험**: 대용량 데이터 처리 시 성능 저하
- **완화책**:
  - 데이터베이스 인덱싱 최적화
  - 페이지네이션 및 무한 스크롤
  - Redis 캐싱 전략

### 🎯 MVP Scope Management

#### 핵심 기능 우선순위

- **Phase 1**: 기본 텍스트 메모 기능에 집중
- **Phase 2**: AI 기능으로 차별화
- **Phase 3**: 음성 입력으로 사용성 향상
- **Phase 4**: 고급 기능으로 완성

#### 기술적 복잡도 관리

- **단계적 구현**: 각 단계별로 완성도 높은 기능 제공
- **사용자 피드백**: 각 단계 완료 후 피드백 수집
- **유연한 계획**: 피드백에 따른 계획 조정

### 💰 Resource Constraints

#### 개발 리소스

- **위험**: 단일 개발자로 인한 개발 속도 제한
- **완화책**:
  - 명확한 우선순위 설정
  - 재사용 가능한 컴포넌트 설계
  - 오픈소스 라이브러리 적극 활용

#### 인프라 비용

- **위험**: AI API 및 호스팅 비용 증가
- **완화책**:
  - 무료 티어 활용 (Vercel, Supabase)
  - 사용량 기반 과금 모델
  - 비용 모니터링 시스템 구축

---

## 8. Appendix

### 📚 Research Findings

#### AI 메모장 시장 분석

- **Notion AI**: 텍스트 기반 AI 메모
- **Otter.ai**: 음성 중심 회의록
- **기회**: 웹 기반 통합 솔루션 부족

#### 기술 스택 선정 근거

- **Next.js 14**: 풀스택 개발 및 SEO 최적화
- **TypeScript**: 타입 안정성으로 버그 감소
- **Supabase**: 개발 속도 향상 및 확장성
- **DrizzleORM**: 타입 안전한 데이터베이스 접근
- **Anthropic Claude**: 고품질 AI 요약 및 분류

### 📋 Technical Specifications

#### 성능 요구사항

- **페이지 로딩**: 3초 이내
- **음성 인식**: 실시간 (1초 이내)
- **AI 요약**: 10초 이내
- **동시 사용자**: 100명 지원

#### 보안 요구사항

- **데이터 암호화**: 저장 및 전송 시
- **사용자 인증**: JWT 기반
- **API 보안**: Rate limiting, CORS 설정

#### 접근성 요구사항

- **WCAG 2.1 AA**: 웹 접근성 준수
- **키보드 네비게이션**: 전체 기능 지원
- **스크린 리더**: ARIA 라벨 및 구조

---

## ✅ 결론 및 향후 과제

Memora는 브라우저 기반에서 음성과 텍스트로 빠르게 메모하고, AI가 자동으로 요약 및 분류해주는 웹 메모장입니다. 초기 버전에서는 핵심 기능인 **STT 기반 음성 메모**, **AI 요약**, **카테고리 분류**에 집중하고, 사용자 피드백을 바탕으로 검색 고도화 및 시각화 통계 기능을 순차적으로 확장할 예정입니다.

**개발 우선순위**: Phase 1의 기본 텍스트 메모 기능부터 시작하여 단계적으로 AI 기능과 음성 입력을 추가하여 완성도 높은 제품을 만들어 나갈 것입니다.
