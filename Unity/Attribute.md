---
Created: 2023-12-21
tags:
  - Unity
---
## What is Attribute?
-  유니티 에디터를 커스텀 할 때 사용
#### 1. SerializeField
- [[private]], [[protected]]로 선언된 변수를 [[Inspector]]에 표시
- Property는 SerializeField를 해도 안 나오지만 ==field== 붙여주면 [[Inspector]]에 표시
```C#
[SerializeField] 변수타입 변수명;
[SerializeField] int m_playerHealth;
[SerializeField] AudioClip m_defaultButtonSound;
[field: SerializeField] public int MoveSpeed { get; private set; }
```
인스펙터에 나와있는 사진추가

#### 2. Header
- 변수 위에 타이틀을 설정해 카테고리 분류, [[Inspector]] 외관 정리에 사용
```C#
[Header(설정 할 String)]
[Header("UI Sounds")] // Header 카테고리에 맞는 변수 나열
[SerializeField] AudioClip m_defaultButtonSound;
[SerializeField] AudioClip m_TransactionSound;

[Header("Game Sounds")]
[SerializeField] AudioClip m_victorySound;
[SerializeField] AudioClip m_defeatSound;
[SerializeField] AudioClip m_potionSound;
```
인스펙터에 카테고리 타이틀 뜨는 사진추가