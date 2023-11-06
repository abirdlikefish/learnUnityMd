# inputsystem

## 
- started  
当一个`Action`开始时会触发一次  
- performed  
当一个`Action`的值每次改变时都会触发一次  
- canceled  
当一个`Action`停止时会触发一次  

## 
- (InputActionName).(ActionMapName + "Actions").SetCallbacks(IGamePlayActions instance)  
订阅委托,一个`input action asset`的类同时只能被一个`instance`订阅