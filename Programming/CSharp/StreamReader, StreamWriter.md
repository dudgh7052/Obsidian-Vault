---
tags:
  - CSharp
---
### StreamReader, StreamWriter 사용
- .NET에서 텍스트를 기반으로 한 입출력을 다루는 Class
- 출력 할 데이터가 크거나, 반복적인 입출력 시 사용
- 입력받는 데이터가 클 경우
### 입출력 성능 개선 이유
- 내부적 데이터 임시 저장 버퍼, 버퍼에 데이터를 모아 커다란 블록으로 사용하는 형식 
	- 입출력 작업 횟수 줄임
- Console.ReadLine() 및 Console.WriteLine()은 사용은 간편 -> 대용량 입출력 처리 시 성능 저하
### StreamReader, StreamWriter와 StringBuilder의 조합
![](https://i.imgur.com/QjxuUuA.png)
- ==StreamReader, StreamWriter== 사용으로 ==ReadLine, WriteLine== 쓸 때 보다 ==입출력 성능 개선== 
- ==[[StringBuilder]]==까지 조합하면 최고!

```C#
using System.IO; // System.IO 네임스페이스를 통해 StreamReader, StreamWriter 가져오기

StreamReader _sr = new StreamReader(Console.OpenStandardInput()); // StreamReader 변수 선언 
StreamWriter _sw = new StreamWriter(Console.OpenStandardOutPut()); // StreamWriter 변수 선언

using (StreamReader _sr = new StreamReader(Console.OpenStandardInput())) // StreamReader 변수 선언
{

}

using (StreamWriter _sw = new StreamWriter(Console.OpenStandardOutput())) StreamWriter 변수 선언
{
    
}

string _str = _sr.ReadLine(); // StreamReader의 ReadLine() Method
_sw.WriteLine(_str) // StreamWriter의 WriteLine() Method

_sr.close(); // 닫아주기
_sw.close(); // 닫아주기
```