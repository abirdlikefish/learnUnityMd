# collider

- 当两物体碰撞时,两物体的碰撞函数都会触发碰撞函数; 当两方有任意一方为`trigger`时两方均触发`ontrigger` , 否则均触发`oncollision` 
- 碰撞时会先触发`___enter` 再在下一帧开始触发 `___stay`
- 无论两物体是否已经接触 , 当其中一个的`istrigger`属性变化 , unity会重新检测碰撞并可能再次触发`___enter`函数