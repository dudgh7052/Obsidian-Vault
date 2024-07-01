---
tags:
  - Unity
---
### UnityEvent란?
- Unity Editor의 Inspector에서 CSharp의 이벤트와 델리게이터와 다르게 이벤트를 표시 가능
```C#
public UnityEvent m_buttonClickEvent;

public void ButtonClick()
{
	m_buttonClickEvent.Invoke();
}
```

### 커스텀 UnityEvent
- 원래라면 UnityEvent는 매개변수를 받을 수 없지만 커스텀 이벤트를 통해 매개변수를 받을 수 있음
- UnityEvent<매개변수>를 상속해주면 매개변수 타입의 변수를 받을 수 있음
- Serializable 속성을 사용하여야 Inspector에 표시 됨 
```C#
using System;
using UnityEngine.Events;

[Serializable]
public class ItemClickEvent : UnityEvent<ItemConBase> 
{

}
```

### 예시
- 클릭 이벤트를 사용 할 스크립트에 이벤트 선언
- ItemBoxMenu의 SelectItemMenu(ItemConBase) 를 AddListener를 통해서 할당
- 결국 ItemConBase를 가지고 있는 Button을 클릭 시 SelectItemMenu메서드를 불러오게 됨
- AddListener를 통해 구독을 한 후 삭제할때는 RemoveListener(해당 메서드)로 해제해줘야 함
- 메모리 누수 및 예기치 않은 동작을 방지하기 위함 임
```C#
public class ItemConBase : MonoBehaviour
{
	// SelectItemMenu 메서드를 등록 할 이벤트 선언
	public ItemClickEvent m_clickEvent;
	
	// Button에 추가 할 이벤트
	public void ButtonClick()
	{
		if (m_clickEvent == null) return;
		m_clickEvent.Invoke();
	}
}

public class ItemBoxMenu : MonoBehaviour
{
	ameObject m_itemCon = null; // List 형식으로 여러개의 버튼을 관리할수도 있음
	
	void Start()
	{
		GameObject _obj = Instantiate(m_itemConBaseObj);
		// 이벤트 등록
		_obj.GetAddComponent<ItemConBase>().m_clickEvent.AddListener(SelectItemMenu);
		m_itemConList.Add(_obj);
		
		// 나중에 오브젝트 삭제 시 이벤트 해제
		m_itemCon.GetAddComponent<ItemConBase>().m_clickEvent.RemoveListener(SelectItemMenu);
		m_itemCon = null;
	}
	
	public void SelectItemMenu(ItemConBase argItemConBaseSc)
	{
		// ItemConBase를 활용한 내용
	}
}
```

### 결론
- UnityEvent Generic타입으로 클래스 선언
- 사용 할 스크립트에서 이벤트 변수 선언
- Button 클릭에서 사용 할 메서드 선언
- 다른 스크립트의 메서드를 불러오기 위해 AddListener로 구독
- 버튼 클릭 시 다른 스크립트 메서불러옴
