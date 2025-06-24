# 🔄 Git 워크플로우 가이드

> 이 문서는 우리 팀의 Git 브랜치 전략과 협업 방식을 설명합니다.

## 📌 핵심 원칙

1. **main 브랜치**는 항상 배포 가능한 상태를 유지합니다
2. **dev 브랜치**는 개발 및 테스트 환경입니다
3. 모든 기능 개발은 **feature 브랜치**에서 진행합니다
4. 코드 리뷰 없이는 머지하지 않습니다

## 🌳 브랜치 전략

### 메인 브랜치들

#### `main`
- **용도**: Production 배포 브랜치
- **배포**: 자동으로 라이브 환경에 배포됨
- **머지 권한**: PR을 통해서만 가능
- **주의사항**: 직접 push 금지 (팀 규칙)

#### `dev`
- **용도**: 개발 통합 및 테스트 브랜치
- **배포**: 테스트 환경에 자동 배포
- **머지**: feature 브랜치들이 통합되는 곳
- **주의사항**: 직접 push 금지, PR을 통해서만 머지

### 작업 브랜치들

#### `feat/{작업내용}`
- **용도**: 새로운 기능 개발
- **생성**: `dev` 브랜치에서 분기
- **머지**: `dev` 브랜치로 PR
- **예시**: 
  - `feat/user-login`
  - `feat/payment-integration`
  - `feat/dashboard-ui`

#### `fix/{작업내용}`
- **용도**: 일반적인 버그 수정 (긴급하지 않은)
- **생성**: `dev` 브랜치에서 분기
- **머지**: `dev` 브랜치로 PR
- **예시**: 
  - `fix/validation-error`
  - `fix/ui-alignment`
  - `fix/api-response`

#### `hotfix/{작업내용}`
- **용도**: Production 긴급 버그 수정
- **생성**: `dev` 브랜치에서 분기
- **머지**: `dev` 브랜치로 PR → 테스트 후 `main`으로
- **예시**: 
  - `hotfix/critical-login-error`
  - `hotfix/payment-crash`

#### `docs/{작업내용}`
- **용도**: 문서 작성 및 수정
- **생성**: `dev` 브랜치에서 분기
- **머지**: `dev` 브랜치로 PR
- **예시**: 
  - `docs/api-guide`
  - `docs/readme-update`
  - `docs/user-manual`

#### `refactor/{작업내용}`
- **용도**: 코드 리팩토링 (기능 변경 없음)
- **생성**: `dev` 브랜치에서 분기
- **머지**: `dev` 브랜치로 PR
- **예시**: 
  - `refactor/user-service`
  - `refactor/database-queries`
  - `refactor/component-structure`

#### `test/{작업내용}`
- **용도**: 테스트 코드 추가 및 수정
- **생성**: `dev` 브랜치에서 분기
- **머지**: `dev` 브랜치로 PR
- **예시**: 
  - `test/user-api`
  - `test/payment-integration`
  - `test/e2e-scenarios`

#### `chore/{작업내용}`
- **용도**: 빌드, 패키지, 설정 등 기타 작업
- **생성**: `dev` 브랜치에서 분기
- **머지**: `dev` 브랜치로 PR
- **예시**: 
  - `chore/update-dependencies`
  - `chore/ci-config`
  - `chore/eslint-rules`

#### `style/{작업내용}`
- **용도**: 코드 스타일, 포맷팅, UI 스타일 변경
- **생성**: `dev` 브랜치에서 분기
- **머지**: `dev` 브랜치로 PR
- **예시**: 
  - `style/code-formatting`
  - `style/ui-theme`
  - `style/css-refactor`

## 🔄 작업 플로우

### 1. 작업 시작하기

```bash
# 1. dev 브랜치로 이동 및 최신 상태 유지
git checkout dev
git pull origin dev

# 2. 작업 유형에 따른 브랜치 생성
git checkout -b [브랜치타입]/[작업내용]

# 예시들:
git checkout -b feat/user-authentication      # 새 기능
git checkout -b fix/login-validation          # 버그 수정
git checkout -b docs/api-documentation        # 문서 작업
git checkout -b refactor/payment-service      # 리팩토링
git checkout -b test/user-api-tests           # 테스트 추가
git checkout -b chore/update-dependencies     # 의존성 업데이트
git checkout -b style/code-formatting         # 스타일 수정

# 3. 작업 진행 및 커밋
git add .
git commit -m "[타입]: 작업 내용 설명"

# 4. 원격 저장소에 push
git push origin [브랜치명]

# 5. GitHub에서 PR 생성
```

### 2. Pull Request 프로세스

1. **PR 생성**
   - 모든 작업 브랜치 → `dev` 방향으로 PR 생성
   - PR 템플릿에 따라 작성
   - 리뷰어 지정 (백엔드 ↔ 프론트엔드)
   - 라벨 추가 (feat, fix, docs, refactor, test, chore, style)

2. **코드 리뷰**
   - 담당자가 아닌 다른 개발자가 리뷰
   - 피드백 반영 및 수정
   - 필요시 추가 커밋으로 수정사항 반영

3. **머지**
   - 리뷰 승인 후 머지
   - Squash merge 권장 (커밋 정리)
   - 머지 후 원격 브랜치 자동 삭제

### 3. 배포 프로세스

```bash
# 1. dev → main PR 생성
# 2. 최종 테스트 확인
# 3. PR 승인 및 머지
# 4. 자동 배포 확인
```

## 📝 커밋 메시지 규칙

[Conventional Commits](https://www.conventionalcommits.org/) 한글 버전 사용:

```
<타입>: <제목>

[본문]

[꼬리말]
```

### 타입 종류
- `feat`: 새로운 기능
- `fix`: 버그 수정
- `docs`: 문서 수정
- `style`: 코드 포맷팅, 세미콜론 누락 등
- `refactor`: 코드 리팩토링
- `test`: 테스트 코드
- `chore`: 빌드 업무, 패키지 매니저 수정 등

### 예시
```
feat: 사용자 로그인 기능 구현

- JWT 토큰 기반 인증 추가
- 소셜 로그인 (구글, 카카오) 연동
- Remember Me 기능 구현
```

## 🚨 주의사항

### ❌ 하지 말아야 할 것들
1. `main` 또는 `dev` 브랜치에 직접 push
2. 리뷰 없이 PR 머지
3. 테스트 없이 main 브랜치로 머지
4. 대량의 변경사항을 하나의 PR에 포함

### ✅ 꼭 지켜야 할 것들
1. PR 생성 전 최신 dev 브랜치와 동기화
2. 의미있는 커밋 메시지 작성
3. PR 설명 상세히 작성
4. 충돌 발생 시 로컬에서 해결 후 push

## 🆘 문제 상황 대처

### 브랜치 충돌 해결
```bash
# 1. 최신 dev 브랜치 가져오기
git checkout dev
git pull origin dev

# 2. feature 브랜치로 돌아가서 rebase
git checkout feat/내-기능
git rebase dev

# 3. 충돌 해결 후 continue
git add .
git rebase --continue

# 4. 강제 push (주의!)
git push origin feat/내-기능 --force-with-lease
```

### 잘못된 브랜치에서 작업한 경우
```bash
# 1. 현재 변경사항 임시 저장
git stash

# 2. 올바른 브랜치로 이동
git checkout -b [올바른-브랜치-타입]/[작업내용]

# 3. 저장한 변경사항 적용
git stash pop
```

## 📋 브랜치별 작업 예시

### 새 기능 추가 (feat)
```bash
git checkout -b feat/social-login
# OAuth 소셜 로그인 기능 구현
git commit -m "feat: 구글 OAuth 로그인 기능 추가"
```

### 버그 수정 (fix)
```bash
git checkout -b fix/user-validation
# 사용자 입력 검증 버그 수정
git commit -m "fix: 이메일 형식 검증 오류 수정"
```

### 문서 작업 (docs)
```bash
git checkout -b docs/installation-guide
# 설치 가이드 문서 작성
git commit -m "docs: 프로젝트 설치 가이드 추가"
```

### 리팩토링 (refactor)
```bash
git checkout -b refactor/api-structure
# API 구조 개선
git commit -m "refactor: API 라우트 구조 개선"
```

### 테스트 추가 (test)
```bash
git checkout -b test/auth-service
# 인증 서비스 테스트 코드 작성
git commit -m "test: 인증 서비스 유닛 테스트 추가"
```

### 기타 작업 (chore)
```bash
git checkout -b chore/upgrade-react
# React 버전 업그레이드
git commit -m "chore: React 18로 업그레이드"
```

### 스타일 수정 (style)
```bash
git checkout -b style/prettier-config
# 코드 포맷팅 설정
git commit -m "style: Prettier 설정 추가 및 코드 포맷팅"
```

## 📞 도움이 필요하다면?

- Discord **#dev-help** 채널에 질문
- 팀 동료에게 직접 문의
- 이 문서에 없는 상황은 팀 회의에서 논의

---

마지막 업데이트: 2025-06-24