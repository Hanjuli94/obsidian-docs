---
aliases: front matter
---

프론트 매터라고도 알려진 YAML은 인간 * 및 * Obsidian이 읽을 수 있는 파일 레벨 메타데이터로 설계되었습니다.

프론트 매터는 파일의 첫 번째 줄에서 시작하는 일반 텍스트 속성 섹션입니다. 마크다운 파일에 메타데이터를 추가하는 가장 인기 있는 방법 중 하나이며 Jekyll, Hugo, Gatsby와 같은 정적 제너레이터에 의해 대중화되었습니다.

YAML 블록은 Obsidian(및 기타 앱)에서 읽으려면 시작과 끝에 **triple dash** 가 필요합니다. == 또한 파일의 맨 위에 배치해야 합니다. ==

For example:

```
---
key: value
key2: value2
key3: [one, two, three]
key4:
- four
- five
- six
---
```

0.12.12.에서 기본적으로 지원되는 키는 4가지입니다.
- `tags` ([[Working with tags|more information]])
- `aliases` ([[Add aliases to note|more information]])
- `cssclass`
- `publish` ([[Publish and unpublish notes#Automatically select notes to publish]] and [[Publish and unpublish notes#Ignore notes]])

Obsidian이 계속 발전함에 따라 플러그인 개발자들이 점차적으로 접근하기 쉽게 만들고, 사용자 친화적으로 만들 것입니다.