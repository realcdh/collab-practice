# collab-practice — Git & GitHub 협업 실습 저장소

우리 반이 함께 **`웹사이트 명세서.txt`** 하나를 완성하는 실습용 저장소입니다.
각자 필요한 기능을 **이슈 → 브랜치 → PR → 머지** 흐름으로 명세서에 추가합니다.

## 🚀 실습 순서

### 0) 저장소 복제 — 최초 1회만
```bash
git clone <이 저장소 주소>
cd collab-practice
```

### 1) 이슈 만들기
- **Issues 탭 → New issue** → 내가 맡을 기능을 적기 (템플릿 제공됨)
- 발급된 **이슈 번호(#12)** 를 기억해 두세요.

### 2) 브랜치 만들기
```bash
git switch main
git pull origin main              # 최신 상태로
git switch -c feature/#12-login   # 브랜치 생성 + 이동
```

### 3) 명세서 편집
`웹사이트 명세서.txt` 의 **[2. 기능 목록]** 표시된 자리에 내 기능을 한 줄 추가.

### 4) 커밋 & 푸시
```bash
git add .
git commit -m "feat: 로그인 기능 추가 (#12)"
git push -u origin feature/#12-login
```

### 5) Pull Request
- GitHub에서 **Compare & pull request** → 본문에 `Closes #12` 작성 → 리뷰 요청.

### 6) 컨플릭트 해결 & 머지
- 충돌이 나면 마커(`<<<<<<<` `=======` `>>>>>>>`)를 지우고 **최종본만** 남긴 뒤 머지.
- 머지 후 브랜치 삭제.

### 7) 최신화
```bash
git switch main
git pull origin main              # 병합 결과 동기화
```

## 📏 규칙
- 브랜치 이름: `feature/#이슈번호-기능이름`
- 커밋 메시지: `feat: ...` / `fix: ...` / `docs: ...`
- **`main`에 직접 push 금지 — 반드시 PR로!**

## ❓ 왜 컨플릭트가 날까?
여러 명이 `웹사이트 명세서.txt`의 **비슷한 위치**를 동시에 고치면 Git이 자동으로 합치지
못하고 "누구 코드를 남길지" 물어봅니다. 오늘은 그걸 직접 해결하는 게 핵심입니다.

---
> 강사용: 이 폴더를 GitHub에 올린 뒤(`git remote add origin <url> && git push -u origin main`),
> 학생들에게 저장소 주소를 공유하고 **협업자(Collaborator)** 로 초대하세요.
