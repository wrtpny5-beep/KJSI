# 정심씨와 세일씨의 즐거운 답사일기 🧡

## 파일 구성
- `index.html` — 메인 앱
- `manifest.json` — PWA 설정
- `sw.js` — 서비스워커 (오프라인 지원)
- `icon-192.png`, `icon-512.png` — 앱 아이콘 (직접 준비)

## 배포 방법 (무료, 5분)

### 방법 1: GitHub Pages (추천)
1. GitHub 계정 만들기 → 새 저장소 생성
2. 파일 4개 업로드
3. Settings → Pages → Branch: main 선택
4. `https://아이디.github.io/저장소명` 으로 접속

### 방법 2: Netlify (드래그앤드롭)
1. netlify.com 접속
2. 로그인 후 파일 폴더를 통째로 드래그앤드롭
3. 자동으로 URL 생성됨

### 아이콘 만들기
- 192×192, 512×512 PNG 파일 필요
- 무료 제작: https://favicon.io 에서 이모지(🏛️) 선택해서 다운로드
- 파일명: `icon-192.png`, `icon-512.png`

## PWA 설치 방법 (부모님 폰)

### 안드로이드 (크롬)
1. 앱 URL 접속
2. 주소창 오른쪽 ⋮ 메뉴 → "홈 화면에 추가"
3. 이후 앱 아이콘으로 실행하면 브라우저 탭 없이 앱처럼 실행됨

### 아이폰 (사파리)
1. 사파리로 앱 URL 접속
2. 하단 공유 버튼(□↑) → "홈 화면에 추가"
3. 이후 앱 아이콘으로 실행

## Firebase Firestore 보안 규칙
배포 후 Firebase Console → Firestore → 규칙 탭에 아래 붙여넣기:
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /shared/data {
      allow read, write: if true;
    }
  }
}
```
(가족 내부 앱이므로 간단한 규칙으로 충분해요)
