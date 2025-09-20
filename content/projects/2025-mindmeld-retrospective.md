## Mindmeld 프로젝트 회고록

### 1. 주요 작업 완료 목록
- 로고 제작 및 디자인 시안 참여
- **컴포넌트 통일 및 디자인 일관성 작업**
  - 웹사이트 전반에 동일한 컴포넌트와 스타일 적용 (DynamicStudyTitle, StudyPoints)
  - 비밀번호 모달 및 검증 기능 추가 (프론트엔드)
  - StudyPoints, DynamicStudyTitle, StudyPasswordModal 공통화
  - CSS 클래스와 prop 네이밍 기준 통일
- **문제 해결 및 디버깅**
- **코드 품질 개선:** 컴포넌트 재사용성 향상 (StudyPoints, DynamicStudyTitle)

### 2. 담당 업무 (UX/UI · Front-End)
- **Atoms**: Button, Input, Toast, Chips, Toggle Switch
- **Molecules**: Password Input, Study Intro, Study Action, Study Point, Search Bar, Share Modal, Popup Modal
- **Organisms**: Habit Modal, Today Habit Modal, Habit Record Table, Study Password Modal, Study Modal
- **Pages**: 스터디 만들기, 스터디 수정하기, 스터디 상세
- **오늘의 습관 (리팩토링)**: 습관 메인 페이지, 수정 모달, Password Modal

### 3. 성과
- FocusPage와 StudyDetailPage를 동일한 UX/UI로 맞추어 **사용자 경험의 일관성** 확보
- StudyPasswordModal을 도입하여 **비밀번호 인증 플로우 표준화**
- StudyPoints, DynamicStudyTitle 등 핵심 컴포넌트 재사용으로 **디자인 시스템 완성도 강화**
- React 에러 및 API 연동 문제 해결로 **프론트엔드 안정성 확보**

### 4. 배운 점
- 단순 기능 구현을 넘어, **디자인과 개발을 연결하는 브릿지 역할**의 중요성 인식
- Git Flow 기반 브랜치 전략을 활용하며 **효율적인 협업 방식** 습득
- React 디버깅, API 검증, UX/UI 일관성 유지 과정을 통해 **실무적 문제 해결 능력** 강화
- 좋은 팀원들과 협업하며 **팀워크와 커뮤니케이션 능력** 향상

### 5. 마무리
- 이번 프로젝트에서 가장 큰 성과는 **UX/UI 일관성과 프론트엔드 품질 개선 기여**
- 다시 한다면, 초기 기획 단계에서 **컴포넌트와 페이지 설계 기준을 더 디테일하게 정의**하고 싶음

> “작은 컴포넌트 하나부터 전체 사용자 경험까지, 끝까지 책임지며 완성도를 높인 프로젝트였습니다. 이번 프로젝트를 통해 혼자보다 함께할 때 더 큰 성과를 낼 수 있다는 것을 배웠습니다. 무엇보다도 끝까지 함께 달려준 팀원들에게 진심으로 감사드립니다.”

