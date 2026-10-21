# SJ_Vault — Obsidian 동기화 저장소

이 저장소는 Obsidian 볼트를 집 PC와 회사 PC 사이에서 GitHub로 동기화하기 위한 것입니다.

- 저장소: https://github.com/JoeSeongjun/share_obsidian
- 집 PC 볼트 위치: `D:\Obsidian\SJ_Vault`

## 회사 PC에서 처음 설정하기

1. Git 설치 확인 (없으면 https://git-scm.com/download/win)
2. 원하는 위치에 저장소 복제

   ```bash
   git clone https://github.com/JoeSeongjun/share_obsidian SJ_Vault
   ```

   처음 push 할 때 GitHub 로그인 창이 뜨면 브라우저로 로그인하면 됩니다.
3. Obsidian 실행 → "볼트 열기(Open folder as vault)" → 복제한 `SJ_Vault` 폴더 선택
4. 설정 → 커뮤니티 플러그인 → 제한 모드 해제 → `Git` (Obsidian Git) 플러그인 설치 후 활성화
5. Obsidian Git 플러그인 설정 권장값
   - Vault backup interval (minutes): `10` → 10분마다 자동 커밋
   - Auto push interval / Auto pull interval: `10`
   - Pull updates on startup: 켜기
   - Commit message: `vault backup: {{date}}` 그대로 두면 됩니다

## 평소 사용법

- Obsidian Git이 자동으로 pull → commit → push 하므로 보통은 신경 쓸 일이 없습니다.
- 즉시 동기화하고 싶으면 명령 팔레트(Ctrl+P)에서 `Git: Commit all changes` → `Git: Push`
- 다른 PC에서 쓰기 전에 `Git: Pull`을 먼저 하면 충돌을 피할 수 있습니다.
- 같은 노트를 양쪽에서 동시에 수정하면 충돌이 날 수 있습니다. 그때는 노트 안에 `<<<<<<<` 표시가 생기니 원하는 내용만 남기고 저장 후 다시 커밋하세요.

## 주의

- `.obsidian/workspace.json` 등 창 상태 파일은 `.gitignore`로 제외되어 있어 PC마다 다른 레이아웃을 써도 충돌이 나지 않습니다.
- 회사 자료를 넣는다면 저장소를 **Private**으로 설정하세요. (GitHub → Settings → Danger Zone → Change visibility)
