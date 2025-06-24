# 🏢 Organization Documentation Repository

> 우리 팀의 개발 문화와 협업 방식을 담은 중앙 문서 저장소입니다.

## 🎯 이 저장소의 목적

- 📋 **표준화**: 일관된 개발 프로세스 확립
- 🤝 **협업 강화**: 명확한 가이드라인으로 효율적인 팀워크
- 📚 **지식 공유**: 팀의 노하우와 경험 축적
- 🚀 **온보딩 가속**: 새 팀원의 빠른 적응 지원

## 📖 핵심 문서

### 🔄 개발 프로세스
| 문서 | 설명 | 상태 |
|------|------|------|
| [Git 워크플로우](../docs/development/git-workflow.md) | 브랜치 전략, PR 프로세스 | ✅ 완료 |
| [커밋 메시지 가이드](../docs/development/commit-message-guide.md) | Conventional Commits 한글 가이드 | ✅ 완료 |
| [코드 리뷰 가이드](../docs/development/code-review.md) | 2인 팀을 위한 리뷰 전략 | ✅ 완료 |
| [PR 템플릿](../.github/pull_request_template.md) | Pull Request 작성 템플릿 | ✅ 완료 |

### 🏁 시작하기 (예정)
| 문서 | 설명 | 상태 |
|------|------|------|
| [온보딩 가이드](../docs/getting-started/onboarding.md) | 새 팀원을 위한 체크리스트 | 📝 예정 |
| [개발 환경 설정](../docs/getting-started/environment-setup.md) | 로컬 환경 구축 가이드 | 📝 예정 |
| [첫 기여하기](../docs/getting-started/first-contribution.md) | 첫 PR 만들기 | 📝 예정 |

### 🏗️ 아키텍처 (예정)
| 문서 | 설명 | 상태 |
|------|------|------|
| [시스템 개요](../docs/architecture/system-overview.md) | 전체 시스템 구조 | 📝 예정 |
| [백엔드 아키텍처](../docs/architecture/backend-architecture.md) | 백엔드 설계 패턴 | 📝 예정 |
| [프론트엔드 아키텍처](../docs/architecture/frontend-architecture.md) | 프론트엔드 구조 | 📝 예정 |

## 🚀 빠른 시작

### 신규 팀원이라면?
1. 📖 [문서 허브](../docs/README.md)에서 전체 문서 구조 파악
2. 🔄 [Git 워크플로우](../docs/development/git-workflow.md) 숙지
3. 📝 [커밋 메시지 가이드](../docs/development/commit-message-guide.md) 확인
4. 👀 [코드 리뷰 가이드](../docs/development/code-review.md) 읽기

### 개발 시작하기
```bash
# 1. 최신 코드 받기
git checkout dev
git pull origin dev

# 2. 작업 브랜치 생성
git checkout -b feat/새로운-기능

# 3. 작업 후 커밋
git add .
git commit -m "feat: 새로운 기능 추가"

# 4. PR 생성
git push origin feat/새로운-기능
# GitHub에서 PR 템플릿에 따라 작성
```

## 🛠️ 개발 도구

### 필수 도구
- **Git**: 버전 관리
- **GitHub**: 코드 저장소 & 협업
- **Discord**: 팀 커뮤니케이션

### 추천 확장 프로그램
- **ESLint**: 코드 품질 체크
- **Prettier**: 코드 포맷팅
- **GitLens**: Git 히스토리 확인

## 📊 팀 규칙

### 브랜치 보호
- `main`, `dev` 브랜치 직접 push 금지
- 모든 변경사항은 PR을 통해서만 머지

### 코드 리뷰
- 모든 PR은 리뷰 필수
- 백엔드 ↔ 프론트엔드 상호 리뷰
- 24시간 내 첫 응답 목표

### 커밋 메시지
- Conventional Commits 형식 준수
- 한글로 명확하게 작성
- 타입: feat, fix, docs, style, refactor, test, chore

## 🤝 기여하기

### 문서 개선
1. 이슈 생성하여 개선사항 제안
2. `docs/문서-개선` 브랜치 생성
3. 수정 후 PR 제출
4. 리뷰 후 머지

### 새 문서 추가
1. 필요성 논의 (이슈 또는 회의)
2. 적절한 카테고리에 문서 작성
3. 목차에 링크 추가
4. PR로 리뷰 요청

## 📞 연락처

- **개발 문의**: Discord #dev-help
- **문서 관련**: 이 저장소에 이슈 생성

## 📈 문서 현황

- ✅ **완료**: 4개 (Git 워크플로우, 커밋 가이드, 코드 리뷰, PR 템플릿)
- 📝 **예정**: 7개 (온보딩, 환경설정, 아키텍처 등)
- 🔄 **지속 업데이트**: 모든 문서는 팀의 성장과 함께 발전

---

<div align="center">
  
**"좋은 문서는 좋은 제품의 시작입니다"**

마지막 업데이트: 2025-06-24

</div>