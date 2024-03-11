---
tags:
  - Unity
  - UnityEditor
  - Addressable
---
### Import Addressable Package
- Window - Package Manager - Unity Registry
- 'Addressables' 검색 및 Import
### Addressable Group
- Window - Asset Management - Addresables - Groups 열기
- Addressables Groups 창에서 오른쪽 클릭
- Create New Group - Packed Assets
- 이제 넣고싶은 에셋에 가면 Addressable 체크를 해주고 Group에 만들어준 그룹 넣어주기
![](https://i.imgur.com/vYVN4Qv.png)

![](https://i.imgur.com/Bu8THxE.png)

### Addressable 실제 사용
- 'AsyncOperationHandle' 를 사용해 비동기로 불러온다
- 'Result' Property를 활용하여 결과 확인 후 가져오기
```C#
void Start()
{
    StartCoroutine(Setting());
}

IEnumerator Setting()
{
    AsyncOperationHandle<가져올 에셋 타입> _handle = 
        Addressables.LoadAssetAsync<가져올 에셋 타입>(해당 Addressable Path);
    yield return _handle; // 불러올때까지 대기
    // AsyncOperationHandle의 결과가 있는지 체크
    if (_handle.Result != null) 
    {
        m_spLibrary.spriteLibraryAsset = _handle.Result; // 가져온 결과 넣기
        m_spResolver.SetCategoryAndLabel(IsCategory, m_spIndex.ToString());
    }
}
```
- 해당 Addressable Path
![](https://i.imgur.com/5cYdOrA.png)
