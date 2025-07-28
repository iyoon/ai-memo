# AI Memo - AI 기반 메모 애플리케이션

AI Memo는 Next.js와 TypeScript를 기반으로 한 현대적인 메모 작성 및 관리 애플리케이션입니다.

## 🚀 기술 스택

- **Framework**: Next.js 15.4.4 (App Router)
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **Development Tools**: Taskmaster AI
- **Package Manager**: npm

## 📋 주요 기능

- 📝 메모 작성 및 편집
- 🏷️ 카테고리별 메모 분류
- 🔍 메모 검색 기능
- 💾 자동 저장
- 📱 반응형 디자인

## 🛠️ 개발 환경 설정

### 필수 요구사항

- Node.js 18.0.0 이상
- npm 9.0.0 이상

### 설치 및 실행

1. 저장소 클론
```bash
git clone https://github.com/iyoon/ai-memo.git
cd ai-memo
```

2. 의존성 설치
```bash
npm install
```

3. 개발 서버 실행
```bash
npm run dev
```

4. 브라우저에서 [http://localhost:3000](http://localhost:3000) 접속

## 📁 프로젝트 구조

```
ai-memo/
├── src/
│   └── app/           # Next.js App Router
│       ├── layout.tsx # 루트 레이아웃
│       └── page.tsx   # 메인 페이지
├── public/            # 정적 파일
├── .taskmaster/       # Taskmaster AI 설정
└── package.json       # 프로젝트 설정
```

## 🧪 개발 도구

### Taskmaster AI
이 프로젝트는 Taskmaster AI를 사용하여 개발 워크플로우를 관리합니다.

```bash
# Taskmaster 명령어
npx task-master-ai list    # 작업 목록 확인
npx task-master-ai next    # 다음 작업 확인
```

## 📝 스크립트

- `npm run dev` - 개발 서버 실행
- `npm run build` - 프로덕션 빌드
- `npm run start` - 프로덕션 서버 실행
- `npm run lint` - 코드 린팅

## 🤝 기여하기

1. 이슈 생성 또는 기존 이슈 확인
2. `feature/issue-number` 형식으로 브랜치 생성
3. 코드 작성 및 테스트
4. Pull Request 생성

## 📄 라이선스

이 프로젝트는 MIT 라이선스 하에 배포됩니다.

## 🔗 링크

- [GitHub Repository](https://github.com/iyoon/ai-memo)
- [Next.js Documentation](https://nextjs.org/docs)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
