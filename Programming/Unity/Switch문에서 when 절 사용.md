---
tags:
  - Unity
  - CSharp
---
- [[Switch문]]는 조건을 상수, bool, string으로만 받을 수 있음
- when 절을 사용해서 좀 더 다양하게 조건 분기를 하여 if,else 문을 대체 할 수 있음
### int형에서의 활용
- when 절을 통해 범위를 지정해서 조건 분기
```C#
int m_num = int.Parse(Console.ReadLine());

switch (m_num)
{
    case int value when value > 10: // 10보다 큰 경우
        Console.WriteLine("Bigger than 10");
        break;
    case int value when value < 10: // 10보다 작은 경우
        Console.WriteLine("Small than 10");
        break;
    case int value when value == 10: // 10과 같은 경우
        Console.WriteLine("Equal 10");
        break;
}       
```

### Vector형에서의 활용
- when 절과 Vector2.Equals(Vector2)를 활용하여 조건 분기
```C#
Vector2 m_input = Vector2.zero;
m_input.x = Input.GetAxisRaw("Horizontal");
m_input.y = Input.GetAxisRaw("Vertical");

switch (m_input.normalized)
{
    // Input이 Vector2.down (0, -1)과 같은 경우
    case Vector2 v when v.Equals(Vector2.down): 
        break;
    // Input이 Vector2.left (-1, 0)과 같은 경우
    case Vector2 v when v.Equals(Vector2.left):
        break;
    // Input이 Vector2.right (1, 0)과 같은 경우
    case Vector2 v when v.Equals(Vector2.right):
        break;
    // Input이 Vector2.up (0, 1)과 같은 경우
    case Vector2 v when v.Equals(Vector2.up):
        break;
}
```