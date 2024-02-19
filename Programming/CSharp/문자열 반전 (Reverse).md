---
tags:
  - CSharp
  - String
---
### 1. Array.Reverse()
- string - charArray - Array.Reverse(charArray) - new string(charArray)
```C#
public static string Reverse(string argStr)
{
   char[] _charArray = argString.ToCharArray();
   Array.Reverse(_charArray);
   return new string(_charArray);
}
```

### 2. Enumerable.Reverse()
```C#
using System.Linq;

public static string Reverse(string argStr)
{
   return new string(argStr.Reverse().ToArray());
}
```

### 3. StringBuilder.Append()
- for문을 통해서 역순으로 StringBuilder의 Append() 활용해서 넣어주고 Return
```C#
public static string Reverse(sting argStr)
{
   StringBuilder _sb = new StringBuilder();

   for (int i = argStr.Length - 1; i >= 0; i--)
   {
      _sb.Append(argStr[i]);
   }

   return _sb.Tostring();
}
```