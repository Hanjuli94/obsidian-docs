[[Obsidian#How we're different|your data is always yours to own and control]]를 믿습니다. 노트는 일반 텍스트 파일을 기반으로 하는 공개 형식인 마크다운 방식으로 저장되므로 앞으로 텍스트 파일을 처리할 수 있는 모든 컴퓨터에서 읽을 수 있어야 합니다. Obsidian으로 노트를 여는 동안에도 다른 소프트웨어의 노트를 자유롭게 편집할 수 있습니다.

### vault당 데이터

그러나 소프트웨어에서 필요한 일부 데이터는 마크다운에 저장되지 않습니다. Obsidian은 사용자가 만든 모든 vault의 루트에 `.obsidian`이라는 디렉터리를 만듭니다. 여기에는 사용자 지정 핫키 및 사용하도록 설정된 플러그인을 포함한 구성이 포함됩니다. `.`로 시작하는 모든 디렉토리는 대부분의 시스템에서 보이지 않으므로 시도하지 않으면 볼 수 없습니다. 이 디렉토리를 삭제하면 데이터는 손실되지 않지만 사용자 지정 설정은 손실됩니다. Obsidian에서 해당 vault를 다시 열면 재생성됩니다. `git`을 사용하는 경우 `.obsidian/workspace`은 창과 열린 파일을 저장하지만 포함된 이슈들은 관찰하지 않기 때문에 `무시`하는 것이 가장 좋습니다.

### 시스템 디렉터리

Obsidian은 시스템 디렉터리에 일부 정보를 저장합니다. 운영 체제마다 다릅니다. Mac에서는 `/Users/yourusername/Library/Application Support/obsidian`이고 윈도우에서는  `%APPDATA%\Obsidian\`입니다. Linux에서 `$XDG_CONFIG_HOME/Obsidian/` 또는 `~/.config/Obsidian/`입니다. 따라서 이 디렉터리에 볼트를 만들지 않는 것이 좋습니다.

이 외에도 운영 체제에서 허용하는 모든 곳에서 볼트를 만들 수 있습니다. Obsidian 파일은 Dropbox, iCloud, OneDrive, Git 및 지금까지 시도한 모든 동기화 서비스와 잘 동기화됩니다.

### 심볼릭 링크

v0.11.1부터 Obsidian은 심볼릭 링크와 junctions를 인식합니다. 공식적으로 사용을 권장하지는 않지만 유효한 사용 사례가 있습니다. 개인의 책임으로 사용하십시오.

심볼릭 링크를 사용하는 데는 많은 함정이 있으며, 그 중 일부는 데이터 손실, 파일 손상 또는 Obsidian 충돌과 같은 심각한 결과를 초래할 수 있습니다.

다음은 염두에 두어야 할 몇 가지 제한 사항 또는 문제입니다.

- 무한 루프로 인해 Obsidian이 충돌하는 것을 방지하기 위해 Symlink 루프는 허용되지 않습니다.
- Symlink 대상은 vault 루트 또는 다른 심볼링크 대상과 완전히 분리되어야 합니다. 분리란 한 폴더에 다른 폴더가 없거나 그 반대의 경우를 의미합니다. Obsidian은 vault의 상위 폴더 또는 vault의 한 폴더에서 같은 vault의 다른 폴더로 심볼 링크를 무시합니다. vault에 파일이 중복되어 링크가 모호해지는 것을 방지하기 위한 안전 장치입니다.
- Symlink는 Obsidian 동기화 또는 _다른 종류의 동기화_에서는 잘 동작되지 않을 수 있습니다. Symlink의 대상 자체가 다른 Obsidian vault에 의해 동기화되는 디렉토리인 경우, 동기화 충돌 또는 데이터 손실이 발생할 수 있습니다. 일부 동기화 도구(예: git)는 Symlink를 따르지 않고 Symlink _지점_을 동기화하므로 다른 사용자와 vault를 공유할 경우 바람직하지 않은 결과가 발생할 수 있습니다.
- Obsidian의 파일 관리자는 장치 경계를 넘어 파일을 이동할 수 없으므로 vault와 다른 드라이브의 폴더에 심볼링하면 Obsidian의 파일 탐색기를 사용하여 해당 폴더와 다른 폴더 간에 파일을 끌어 올 수 없습니다. (이러한 이동에는 OS의 탐색기를 사용해야 하며, Obsidian은 이동을 삭제 및 새 파일 생성으로 간주합니다. 또한 해당 파일의 경로에 의존하는 링크를 업데이트하지 _않습니다_ .)
- (폴더 Symlink와는 반대로) 파일 Symlink는 작동할 수 있지만, 현재 공식적으로 지원되지는 않습니다. Obsidian 외부에서 수행된 변경은 감시되지 않으므로 파일을 직접 변경하면 Obsidian이 변경 사항을 감지하지 못하고 검색 색인을 업데이트하지 않습니다.
- 무엇을 하고 있는지 정말로 알지 못한 경우, vault 간에 공유하기 위해 `.obsidian/` 디렉터리에 있는 것들을 심볼링하면 ** 설정이 손상될 가능성이 높습니다. ** 이 방법을 사용한다면 최소한 지원이라도 받는것을 권고합니다.
