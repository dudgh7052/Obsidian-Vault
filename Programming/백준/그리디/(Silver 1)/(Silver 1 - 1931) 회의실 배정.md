---
tags:
  - Baekjoon
  - Greedy
---
https://www.acmicpc.net/problem/1931
### 핵심
- 끝나는 시간을 기준으로 오름차순 정렬 후 시작 시간을 기준으로 오름차순 정렬
- https://bokhead.tistory.com/39

```C#
using System.IO;

StreamReader _sr = new StreamReader(Console.OpenStandardInput());
StreamWriter _sw = new StreamWriter(Console.OpenStandardOutput());

// 가장 빨리 끝나는 회의를 선택하여 가장 많은 회의 구하기
int N = int.Parse(_sr.ReadLine());
List<Meeting> m_meetingList = new List<Meeting>();
Meeting m_currentMeeting = new Meeting(0, 0);

int[] _input = new int[2];
int m_meetingCount = 0; // 총 회의 카운트

// 한 줄 씩 회의 List에 넣기
for (int i = 0; i < N; i++)
{
    _input = Array.ConvertAll(_sr.ReadLine().Split(), int.Parse);
    m_meetingList.Add(new Meeting(_input[0], _input[1]));
}

// 끝나는 시간을 기준으로 오름차순 정렬 후, 시작 시간을 기준으로 오름차순 정렬
m_meetingList = m_meetingList.OrderBy(x => x.m_endTime).ThenBy(x => x.m_startTime).ToList(); 

for (int i = 0; i < m_meetingList.Count; i++)
{
    // 현재 회의의 종료 시간이 다음 회의의 시작 시간보다 작거나 같은지를 체크
    if (m_currentMeeting.m_endTime <= m_meetingList[i].m_startTime)
    {
        m_currentMeeting = m_meetingList[i];
        m_meetingCount++;
    }
}

_sw.WriteLine(m_meetingCount);

_sr.Close();
_sw.Close();

/// <summary>
/// 회의
/// </summary>
public class Meeting
{
    public Meeting(int argStartTime, int argEndTime)
    {
        m_startTime = argStartTime;
        m_endTime = argEndTime;
    }

    public int m_startTime;
    public int m_endTime;
}
```