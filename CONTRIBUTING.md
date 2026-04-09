# CONTRIBUTING

본 문서는 조직 전체 공통 협업 규칙입니다.

## 1. 브랜치 전략

### 기본 브랜치
- `main`: 배포/제출 기준 브랜치
- `dev`: 통합 개발 브랜치

### 작업 브랜치 네이밍
형식:
```bash
타입/이슈번호-설명
```

예시:
```bash
feature/12-recommend-ui
feature/18-inventory-api
fix/27-alcohol-classification-bug
refactor/34-event-router
```

### 브랜치 타입
- `feature`: 기능 개발
- `fix`: 버그 수정
- `refactor`: 리팩토링
- `docs`: 문서 수정
- `test`: 테스트 추가/수정
- `chore`: 설정/빌드/의존성 작업
- `hotfix`: 긴급 수정

## 2. 커밋 메시지 규칙
Conventional Commits 스타일을 사용합니다.

형식:
```bash
type(scope): summary
```

예시:
```bash
feat(fe): 추천 결과 화면 추가
feat(be): 추천 요청 생성 로직 구현
feat(ai): 식재료 분류 모델 학습 코드 추가
fix(be): 재고 수량 갱신 버그 수정
docs(org): git convention 문서 추가
refactor(ai): onnx export 모듈 분리
```

### type 목록
- `feat`: 기능 추가
- `fix`: 버그 수정
- `refactor`: 구조 개선
- `docs`: 문서 변경
- `test`: 테스트 코드
- `chore`: 설정, 패키지, CI 변경
- `style`: 포맷팅만 변경
- `perf`: 성능 개선

### 작성 원칙
- 한 커밋에는 한 가지 논리적 변경만 담습니다.
- 커밋 메시지는 **무엇을 했는지** 중심으로 씁니다.
- `update`, `modify`, `change` 같은 모호한 표현은 지양합니다.

## 3. Pull Request 규칙

### PR 제목
형식:
```bash
[type] 작업 요약
```

예시:
```bash
[feat] 추천 상세 화면 구현
[fix] 재고 갱신 중복 반영 문제 수정
[refactor] 주류 인식 후처리 로직 분리
```

### PR 본문 필수 항목
- 작업 내용
- 변경 이유
- 테스트 방법
- 영향 범위
- 관련 이슈

### 리뷰 규칙
- 최소 1명 이상의 리뷰 승인 후 merge
- 본인이 작성한 PR은 본인이 merge 가능하되, 승인 없이 merge하지 않음
- 큰 PR보다는 작은 단위 PR을 권장

### Merge 규칙
- `main`, `dev` 직접 push 금지
- 기본 merge 방식은 **Squash Merge** 사용
- CI/테스트 실패 상태에서는 merge 금지

## 4. 이슈 규칙
- 기능 추가, 버그 수정, 리팩토링은 가능한 한 이슈 단위로 관리합니다.
- 브랜치, PR, 커밋에 이슈 번호를 연결합니다.

예시:
```bash
feature/22-recipe-ranking
feat(be): 후보 점수화 로직 추가 (#22)
```

## 5. 코드 리뷰 기준
리뷰 시 아래를 우선 확인합니다.
- 책임 분리가 잘 되었는가
- 중복 로직이 없는가
- 네이밍이 명확한가
- 예외 상황이 처리되었는가
- 테스트 가능하게 작성되었는가
- UI/응답 형식이 문서와 일치하는가

## 6. 저장소별 역할 원칙
- `fe`: 사용자 화면, 상태 관리, 입력 보정 UX
- `be`: 이벤트 처리, 재고/추천 오케스트레이션, DB/외부 API 연계
- `ai`: 모델 학습/추론/최적화 및 배포용 inference

## 7. 문서화 원칙
아래 변경은 문서도 함께 갱신합니다.
- 화면 흐름 변경
- API 계약 변경
- 모델 입출력 변경
- 폴더 구조 변경
- 실행 방법 변경
