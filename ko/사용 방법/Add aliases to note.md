---
aliases: alias, aliases
---

경우에 따라 다른 컨텍스트에서 이름이 여러 개인 동일한 파일을 참조할 수 있습니다. 이 대체 이름들은 우리가 "별칭"이라고 한다.

예를 들어 파트너의 전체 이름, 이름 또는 닉네임으로 파트너를 참조할 수 있습니다. 또는 "인공지능"을 약칭 "AI"로 지칭할 수도 있습니다. 여러 언어를 알고 있는 경우 노트의 나머지 부분이 쓰여진 언어와 동일한 언어로 동일한 개념을 참조할 수 있습니다.

### 별칭 설정

0.9.16부터는, [[YAML front matter]]에서 다음과 같이 "별칭" 속성을 지정할 수 있습니다.

```
---
aliases: [AI, Artificial Intelligence]
---
```

이 섹션을 적용하려면 노트의 맨 위에 배치해야 합니다.

앞으로는 직접 작성하기보다는 사용자 친화적인 방식으로 별칭을 관리하는 방법을 더 고려해야 합니다.

### 별칭이 있는 링크

파일에 별칭을 설정한 후에는 `[[alias]]`를 작성하여 원래 페이지로 연결할 수 있습니다. 리디렉션 아이콘이 자동 완성 목록에 다음과 같이 표시됩니다.

![[Insertalises.png]

보여지는 텍스트가 있는 내부 링크는 다음과 같이 삽입됩니다: `[[Add aliases to note|alias]]`.

참고: 별칭 링크는 다른 소프트웨어도 인식할 수 있도록 상호 운용성을 위해 `[[alias]]`로 삽입되지 **않습니다** .

### 링크되지 않은 멘션 찾기

노트에 별칭을 설정한 후에는 노트의 이름과 별칭을 모두 사용하여 링크되지 않은 언급을 찾을 수 있습니다.

예를 들어, "AI"를 "인공지능"의 별칭으로 설정한 후, [[백링크]] 섹션의 다른 파일에서 "AI"에 대한 언급을 볼 수 있습니다.

이 설명을 연결하기로 결정하면 보여지는 텍스트가 별칭으로 설정된 링크가 만들어집니다. 위의 예에 따르면 "링크" 버튼을 클릭하면 `AI`는 `[[인공지능|AI]]`가 된다.