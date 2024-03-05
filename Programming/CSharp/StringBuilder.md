---
tags:
  - CSharp
  - Unity
---
```C#
using System.Text; // System.Text 네임스페이스를 통해 StringBuilder 가져오기

StringBuilder _sb = new StringBuilder(); // 선언
StringBuilder _sb = new StringBuilder("StringBuilder"); // 문자설정 초기 선언
StringBuilder _sb = new StringBuilder("StringBuilder", 25); // 문자설정 및 길이 선언
_sb.Capacity = 25; // Property를 통한 용량 설정

// 추가
_sb.Append("Append Something"); // 추가

// 형식에 맞게 추가
float _health = 100.0f;
_sb.AppendFormat("Health: {0:F2}", _health); // Format에 맞게 추가 1
_sb.AppendFormat($"Health: {_health}"); // Format에 맞게 추가 2

// 지정 위치에 추가
_sb.Insert(4, "Insert Someting");

// 특정 문자열 교체
_sb.Replace("!", "?") // !를 ?로 변경

// 클리어
_sb.Clear();

// 값 비교
_sb.Equals("비교 할 String") // 같으면 True, 아니면 False
```

### StringBuilder는 mutable(가변)타입
- ==String==은 Immutable(불변) ==문자열 갱신이 많으면 적합하지 않음==
- ==StringBuilder==는 Mutable(가변) ==문자열 갱신 많은 곳에 사용==
	- 별도 메모리 생성, 소멸 하지 않고 일정한 버퍼를 갖고 효율 처리

### Unity에서의 활용
```C#
using System.Text;
using UnityEngine.UI;

StringBuilder m_stringBuilder = new StringBuilder();
Text m_scoreText;

void Update()
{
    m_stringBuilder.Append();
    m_score.Text = m_stringBuilder;
}
```
- 재화, 점수, 체력 UI 등 계속 변하는 String에 StringBuilder 사용