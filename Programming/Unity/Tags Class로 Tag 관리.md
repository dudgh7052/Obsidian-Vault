---
tags:
  - Unity
  - CSharp
---
### Tags Class 만들어서 Tag 관리
- 기존에는 바로 "TagName" 으로 넣었음
- 잘못 입력하면 정상적으로 움직이지 않을 수 있기에 Tags Class 만들어서 관리
```C#
private void OnTriggerEnter(Collider other)
{
   if (other.comepareTag("TagName")){} // 기존 방식

   if (other.camepareTag(Tags.g_enemyTag)){} // Tags 클래스 만들어서 태그들 한번에 관리
}

```
### Tags Class 만들기
```C#
using UnityEngine;

public class Tag : MonoBehaviour
{
   public static readonly string g_enemyTag = "Enemy";
   public static readonly string g_bulletTag = "Bullet";
}
```