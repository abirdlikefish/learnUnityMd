# solution
记录一些遇到的问题和解决方案

## unity2D

### 图层错误

> 1_由多个sprite组成的物体在重叠时会发生图层错误 , 如一个enemy由body和eye组成并通过`sprite renderer`的`sorting layer` 和 `order in layer` 设置 eye 在 body 上 ; 当两个enemy重叠时会出现两个body在下, 两个eye在上的情况 ;

- 渲染优先级 Camera depth > Sorting Layer > Order in Layer > RenderQueue
- 每个敌人一个单独的camera渲染(开销巨大)
- 设置一个随机的 `gameobject.transform.position.z ` 无效 , unity应该是每个renderlayer渲染完后再在渲染完的画面上渲染下一个layer，单纯改变z坐标无用
- 给每个敌人实例化时设置给定的一组order in layer，比如第n个敌人的身体的orderinlayer是3n，眼睛3n+1 , 嘴巴3n+2。orderinlayer好像没有大小限制，再加上对象池啥的应该就可以了

### 碰撞体相关
> 2_敌人E和玩家P相互之间不产生碰撞但接触时玩家受伤 , E与E , P与P , EP与场景物体 之间会产生碰撞; 
- 将物理碰撞的碰撞箱 与 攻击被攻击的碰撞箱分开, 攻击被攻击的碰撞箱设为`trigger` , 修改`layer collision matrix`


### animatot相关
> 3_animator使用`play`方法播放新动画后`animator.GetCurrentAnimatorStateInfo(0).normalizedTime`在下一帧才会归零
