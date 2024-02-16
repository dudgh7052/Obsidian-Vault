---
Created: 2023-12-21
tags:
  - Unity
---
### What is GetComponent?
- GetComponent란 [[Object]]에 포함 되어있는 [[Component]]를 할당하기 위한 함수이다.

```C#
ScriptType m_variable = GetComponent<ScriptType>();
ScriptType m_variable = GetComponentsInChildren<ScriptType>(true);
```

[[GetComponent]]<>()로 변수에 스크립트를 할당 할 수 있음.
괄호()안에 true를 넣을 시 [[Hierachy]]에서 비활성화 된 [[Object]]에 있는 [[Script]]도 할당 가능케 함.