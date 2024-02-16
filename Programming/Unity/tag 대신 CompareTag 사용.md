---
tags:
  - Unity
  - CSharp
---
### gameObject.tag 대신 CompareTag
![](https://i.imgur.com/RKpgLbH.png)
```C#
const string m_destroyTag = "Enemy"

void Start()
{
   // 느림
   if (gameObject.tag == m_destroyTag)
   {
      Destroy(gameObject);
   }

   // 빠름
   if (gameObject.CompareTag(m_destoryTag))
   {
      Destroy(gameObject);
   }
}
```

### 속도 차이
![](https://i.imgur.com/I2Gf4vr.png)
- equal을 썼을때보다 1.7 ~ 2.6배 더 빠름