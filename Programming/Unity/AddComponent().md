---
tags:
  - Unity
  - CSharp
---
### AddComponent(Type componentType)
- 제네릭 타입으로 넣을 수 없을 경우 활용
- 추가 할 컴포넌트가 명확하지 않을 경우 사용
- [[GetType()]]으로 Type을 먼저 가져와주고 AddComponent()로 컴포넌트 추가해주기
```C#
// System 네임스페이스의 Type의 GetType(string argString)으로 타입 가져오기
System.Type _type = System.Type.GetType("SNJ.Controller." + m_loadType.ToString() + "Controller");
// AddComponent(System.Type argType)으로 컴포넌트 오브젝트에 넣어주기
m_controller = (ParentsController)gameObject.AddComponent(_type);
```

### AddComponent Generic
- 추가 할 컴포넌트가 명확 할 경우 제네릭으로 넣어줌
```C#
// m_controller에 UserController 컴포넌트 추가
m_controller = gameObject.AddComponent<UserController>();
```