---
tags:
  - CSharp
  - Unity
---
### Singleton Pattern 이란?
- 객체가 여러 차례 생성 되더라도 객체는 하나
- 최초 생성 이후에 생성된 객체는 삭제한다
- 'Instance' [[Property]]를 Static 타입으로 만들어서 전역적으로 해당 컴포넌트의 메서드 등을 사용하게 해줌
```C#
public class Manager : MonoBehaviour
{
   public static Manager Instance { get; private set; }

   private void Awake()
   {
      if (Manager.Instance == null)
      {
         Instance = this;
         DontDestroyOnLoad(gameObject);
      }
      else Destroy(gameObject);
   }
}
```