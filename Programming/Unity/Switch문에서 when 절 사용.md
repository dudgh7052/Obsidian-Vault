---
tags:
  - Unity
  - CSharp
---
```C#
switch (argInput.normalized)
{
    case Vector2 v when v.Equals(Vector2.down):
        IsDirType = DirType.TYPE.Down;
        IsTargetPos += Vector3.down;
        break;
    case Vector2 v when v.Equals(Vector2.left):
        IsDirType = DirType.TYPE.Left;
        IsTargetPos += Vector3.left;
        break;
    case Vector2 v when v.Equals(Vector2.right):
        IsDirType = DirType.TYPE.Right;
        IsTargetPos += Vector3.right;
        break;
    case Vector2 v when v.Equals(Vector2.up):
        IsDirType = DirType.TYPE.Up;
        IsTargetPos += Vector3.up;
        break;
}
```