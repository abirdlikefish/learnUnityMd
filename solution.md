# solution
记录一些遇到的问题和解决方案

## unity2D

### 图层错误

> 1_由多个sprite组成的物体在重叠时会发生图层错误 , 如一个enemy由body和eye组成并通过`sprite renderer`的`sorting layer` 和 `order in layer` 设置 eye 在 body 上 ; 当两个enemy重叠时会出现两个body在下, 两个eye在上的情况 ;

- 设置一个随机的 `gameobject.transform.position.z ` // 无用

### 碰撞体相关
> 2_敌人E和玩家P相互之间不产生碰撞但接触时玩家受伤 , E与E , P与P , EP与场景物体 之间会产生碰撞; 
- 将物理碰撞的碰撞箱 与 攻击被攻击的碰撞箱分开, 攻击被攻击的碰撞箱设为`trigger` , 修改`layer collision matrix`

