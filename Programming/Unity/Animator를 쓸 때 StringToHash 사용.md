---
tags:
  - Unity
  - CSharp
---
### String 대신 StringToHash를 통해 Int형으로 변환
```C#
static readonly int MoveStateHash = Animator.StringToHash("Move");
static readonly int MoveSpeedHash = Animator.StringToHash("MoveSpeed");
Animator m_animator;

void Start()
{
   m_animator = GetComponent<Animator>();
   
   // 느림
   m_animator.Play("Move");
   m_animator.SetFloat("MoveSpeed", 5.0f);

   // 빠름
   m_animator.Play(MoveStateHash);
   m_animator.SetFloat(MoveSpeedHash, 5.0f);
}
```
- String을 사용해도 내부적으로 StringToHash를 통해 Int형으로 바꿈
- 결국 똑같아지기에 미리 해 놓는 편이 좋음

### Material을 변경 할 경우
```C#
static readonly int ColorPropertyId = Shader.PropertyID("_Color");

void Start()
{
   Material _mat = GetComponent<Renderer>().Material;

   // 느림
   _mat.SetColor("_Color", Color.White);
   
   // 빠름
   _mat.SetColor(ColorPropertyId, Color.White);
}
```