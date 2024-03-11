---
tags:
  - Unity
  - CSharp
---
- System namespace에서 GetType(string argTypeStr)으로 Type을 가져올수있음
- [[AddComponent()]]로 컴포넌트를 추가 할 때 사용가능 
```C#
System.Type _type = System.Type.GetType(가져 올 타입 String);

// 예시
// UserController, MobController, NPCController중에서 가져오기 위해 활용
// AddComponent<T>로는 한가지만 가져올 수 있기에 AddComponent(System.Type) 활용한거임
System.Type _type = System.Type.GetType("SNJ.Controller." + m_loadType.ToString() + "Controller");
m_controller = (ParentsController)gameObject.AddComponent(_type);
```