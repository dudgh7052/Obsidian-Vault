---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/5635
```C#
List<Info> _list = new List<Info>();

int N = int.Parse(Console.ReadLine());
while (N-- > 0)
{
    string[] _input = Console.ReadLine().Split();
    _list.Add(new Info(_input[0], int.Parse(_input[3]), int.Parse(_input[2]), int.Parse(_input[1])));
}

List<Info> _sortedList = _list.OrderBy(x => x.Year).ThenBy(x => x.Month).ThenBy(x => x.Day).ToList();

Console.WriteLine("{0}\n{1}", _sortedList[_sortedList.Count - 1].Name, _sortedList[0].Name);

class Info
{
    public Info(string argName, int argYear, int argMonth, int argDay)
    {
        Name = argName;
        Year = argYear;
        Month = argMonth;
        Day = argDay;
    }

    public string Name { get; set; }
    public int Year { get; set; }
    public int Month { get; set; }
    public int Day { get; set; }
}
```