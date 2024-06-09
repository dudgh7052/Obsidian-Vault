---
tags:
  - Baekjoon
  - Sort
  - Collection
---
```C#
PriorityQueue<int, int> _heap =  new PriorityQueue<int, int>();

int N = int.Parse(Console.ReadLine());
for (int i = 0; i < N; i++)
{
    int[] _arr = Console.ReadLine().Split().Select(int.Parse).ToArray();
    foreach (int value in _arr)
    {
        _heap.Enqueue(value, value);

        if (_heap.Count > N) _heap.Dequeue();
    }
}

Console.WriteLine(_heap.Peek());
```