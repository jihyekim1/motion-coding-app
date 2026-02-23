# 튜토리얼 관리 가이드 (Tutorial Management Guide)

이 문서는 모션 코딩 프로토타입의 튜토리얼 시스템을 활성화하거나 비활성화하는 방법을 설명합니다. 향후 튜토리얼이 없는 버전을 배포하거나 유지보수할 때 참조하세요.

## 1. 튜토리얼 시스템 개요
현재 시스템은 페이지 로드 시 튜토리얼 오버레이가 먼저 나타나며, 모든 학습 과정을 마치거나 'Skip'을 선택해야 메인 게임 로직이 활성화되는 구조입니다.

## 2. 튜토리얼 비활성화 방법 (순수 게임 버전)

튜토리얼을 제거하고 바로 게임을 시작하려면 `index.html` 파일에서 다음 세 가지 부분을 수정해야 합니다.

### A. JavaScript 변수 수정
`tutorialState.isActive` 값을 `false`로 변경하여 시스템이 튜토리얼 모드가 아님을 수동으로 설정합니다.

```javascript
// index.html 약 1546라인 근처
const tutorialState = {
    isActive: false, // true에서 false로 변경
    currentScene: 1,
    // ... 나머지 코드
};
```

### B. 초기화 코드 수정
페이지 로드 시 튜토리얼을 거치지 않고 바로 'Stage 1'을 불러오도록 주석을 해제합니다.

```javascript
// index.html 약 1765라인 근처
// ── 메인 시스템 초기화 ──
initLogger();
initStage(1); // 주석(//)을 제거하여 즉시 실행
```

### C. UI 요소 숨기기 (CSS/HTML)
튜토리얼 오버레이가 나타나지 않도록 스타일을 수정하거나 HTML 요소를 삭제합니다.

```html
<!-- index.html 약 660라인 근처 -->
<div id="tutorial-overlay" style="display: none;"> <!-- display를 none으로 명시적 설정 -->
```

## 3. 다시 활성화할 때 주의사항
동작 인식 로직(`onResults`)은 현재 튜토리얼과 메인 게임이 하나로 통합되어 있습니다. 튜토리얼을 다시 켤 때는 반드시 `tutorialState.isActive = true` 설정을 확인하여, 인식 결과가 튜토리얼 핸들러로 먼저 전달되도록 해야 합니다.

---
**작성일**: 2026-02-23
**버전**: v1.5 (튜토리얼 고도화 완료 버전)
