---
tags:
  - Unity
  - UnityEditor
---
### Sprite Resolver 란?
- [[Sprite Library Asset]] 의 스프라이트들을 Category에 맞게 바꿔줘는 Component
- Sprite Library Asset과 짝궁이라 할 수 있다.
![](https://i.imgur.com/CvXVzRp.png)
- 이런 식으로 Sprite Library Asset 내용을 Category - Label로 바꿀 수 있음
- Category = 애니메이션, Label = 애니메이션 인덱스로 보면 편할듯

### Sprite Resolver을 통한 애니메이션
- SpriteResolver의 SetCategoryAndLabel(Category, Label)을 활용하여 변환 가능
```C#
using UnityEngine.U2D.Animation; // SpriteResolver를 사용하기 위해 Using 선언

[SerializedField] private SpriteResolver m_spResolver = null; // SpriteResolver 가져오기
[SerializedField] private float m_sensitivity = 0.2f; // 애니메이션 재생 속도
float m_aniTime = 0.0f; // 현재 애니메이션 재생 시간

int m_spIndex = 0; // 현재 스프라이트 인덱스 저장용(Label)
int m_maxIndex = 4; // 현재 카테고리의 Label 갯수 

void Update()
{
   m_aniTime += Time.deltaTime;
   if (m_aniTime >= m_sensitivity)
   {
      m_aniTime = 0.0f;
      m_spIndex++;
      m_spIndex = m_spIndex % m_maxIndex;
   }
   // SetCategoryAndLabel(string 카테고리 이름, string Label) 통해서 스프라이트 변경
   m_spResolver.SetCategoryAndLabel("해당 카테고리 이름", m_spIndex);
}
```