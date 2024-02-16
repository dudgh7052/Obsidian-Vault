1. AchieveData
```C#
using UnityEngine

[CreateAssetMenu(fileName = "Achieve". menuName = "ScriptableObject/AchieveData")]
public class AchieveData : ScriptableObject
{
   public enum CheckType { OneShot, Always }

   public enum AchieveType { Kill, Level, Time}

   // 상시 체크 타입- 이것에 따라 LateUpdate에서 체크 할지 말지 결정
   public CheckType m_CheckType;

   /// 업적 타입에 따라서 구현
   public AchieveType m_AchieveType;
   
   // Unlock 시 Canvas에 띄울 UI
   public GameObject m_UnlockUI = null;
}
```